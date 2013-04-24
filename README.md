# Camel ICal component
This small component allows you to use ical invitations and other goodness of these and convert it into Java objects. Thanks to that you may pick up mail attachements in ics format and handle them in way you want.

## Example usage
```java
public class ICalRouteBuilder extends RouteBuilder {
    @Override
    public void configure() throws Exception {
        from("...") // ical string
            .unmarshal(ical()) // now we have net.fortuna.ical4j.model.Calendar object
            .to("...");
        from("...") // ical object
            .marshal(ical()) // ical string
            .to("...");
    }
}
```

