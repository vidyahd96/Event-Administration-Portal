import java.util.ArrayList; import java.util.Scanner; class Event
{
 

IMPLEMENTATION
 
private String name; private String date; private String venue;
public Event(String name, String date, String venue)
{
this.name = name; this.date = date; this.venue = venue;
}

public String getName()
{
return name;
}

public String getDate()
{
return date;
}


public String getVenue() { return venue;
}
@Override
public String toString()
 

 
{
return "Event Name: " + name + ", Date: " + date + ", Venue: " + venue;
}
}
public class EventManagementSystem
{
private ArrayList<Event> events; public EventManagementSystem()
{
events = new ArrayList<>();
}
public void addEvent(String name, String date, String venue) { Event event = new Event(name, date, venue); events.add(event);
System.out.println("Event added successfully!");
}
public void displayEvents() { System.out.println("List of Events:"); for (Event event : events) {
System.out.println(event);
}
}
public static void main(String[] args)
{
EventManagementSystem eventManagementSystem = new EventManagementSystem(); Scanner scanner = new Scanner(System.in);
int choice; do {
System.out.println("1. Add Event"); System.out.println("2. Display Events"); System.out.println("3. Exit"); System.out.print("Enter your choice: "); choice = scanner.nextInt();
 

 
switch (choice)
{
case 1:
System.out.print("Enter event name: "); scanner.nextLine(); // Consume newline String name = scanner.nextLine(); System.out.print("Enter event date: "); String date = scanner.nextLine(); System.out.print("Enter event venue: "); String venue = scanner.nextLine();
eventManagementSystem.addEvent(name, date, venue); break;
case 2:
eventManagementSystem.displayEvents(); break;
case 3:
System.out.println("Exiting program..."); break;
default:
System.out.println("Invalid choice. Please try again.");
}
} while (choice != 3); scanner.close();
}
}
