# Interactive dashboard for visualization and analysis
=======
# Airline Insights Dashboard

An interactive Power BI project that transforms airline booking, passenger, and flight data into a clear operational dashboard. The report explores airline popularity, flight punctuality, customer booking behavior, and destination demand while demonstrating data preparation, modeling, DAX, interactive filtering, publishing, and row-level security.

## Project Overview

The dashboard was created to help users quickly answer questions such as:

- Which airlines carry the most passengers?
- Which airlines record the most delayed or cancelled flights?
- What proportion of tickets are confirmed, cancelled, or pending?
- Which destinations are most popular?
- How do airline and destination selections affect the reported metrics?

## Dashboard Preview

The final **Airline Insights Dashboard** contains four main analytical areas:

1. **Flight Punctuality and Delays** - compares flight conditions across airlines.
2. **Most Popular Airlines** - ranks airlines by passenger volume.
3. **Most Popular Destinations** - maps passenger demand across destinations.
4. **Customer Booking Behavior** - summarizes confirmed, cancelled, and pending bookings.

The report also includes KPI cards, charts, tables, and slicers that respond to airline and destination selections.

## Data Sources

The model uses three related datasets:

- **Flight Information** - flight, airline, destination, and flight-condition details.
- **Passenger Information** - passenger records connected to individual flights.
- **Ticket Information** - ticket records and booking-status information.

## Data Preparation

Power Query was used to inspect and prepare the datasets before analysis. The workflow included:

- reviewing column names and data types;
- cleaning and organizing the three source tables;
- preparing fields for relationships and reporting; and
- creating an enhanced table for additional analysis.

## Data Model

The flight table acts as the central table in the model. Active relationships connect:

- `Passenger Information` to `Flight Information`; and
- `Ticket Information` to `Flight Information`.

This structure allows passenger and ticket metrics to be analyzed by airline, destination, and flight attributes.

## DAX and Calculated Outputs

The project demonstrates DAX through:

- passenger counts for individual flights;
- a total tickets booked measure; and
- a filtered table containing flights rated as `Best`.

One measure shown in the project is:

```DAX
TotalTicketsBooked =
    CALCULATE(
        COUNT('Ticket_Information - ticket_information'[TicketID])
    )
```

## Visualizations and Interactivity

The report uses:

- column and bar charts for airline comparisons;
- a pie chart for booking-status composition;
- a map for geographic destination demand;
- KPI cards for passengers, flights, and tickets;
- tables for record-level detail; and
- airline and destination slicers for cross-filtering.

Selecting a destination or airline updates the related visuals and KPI cards, enabling focused comparisons without changing the underlying report.

## Example Findings

The completed dashboard indicates that:

- Airline B has the highest number of delayed or cancelled flights in the sample.
- Airline A carries the most passengers, followed by Airlines D and C.
- Confirmed bookings form the largest booking-status category.
- Los Angeles and Phoenix are among the most frequently selected destinations in the sample.

These findings are based on the demonstration dataset and should not be interpreted as real-world airline performance.

## Power BI Service and Security

The project includes deployment to Power BI Service and demonstrates row-level security. An **Airline A Role** applies a filter so assigned users can view only Airline A data:

```DAX
[Airline] = "Airline A"
```

## Tools and Skills Demonstrated

- Microsoft Power BI Desktop
- Power Query
- Data cleaning and transformation
- Relational data modeling
- DAX measures and calculated tables
- Data visualization and dashboard design
- Interactive filters and slicers
- Power BI Service
- Row-level security (RLS)

## Project Walkthrough

A video demonstration is available on YouTube:

[Watch the Power BI project walkthrough](https://youtu.be/mefW5NlOx74)

## Repository Contents

The supplied project archive contains a PDF walkthrough of the report. To make the dashboard reproducible, future versions of the repository could also include the Power BI `.pbix` file, source datasets, a data dictionary, and dashboard screenshots.

## Author

**Simrat Kaur Khalsa**

>>>>>>> d30a446 (Initial commit: Airline Insights Power BI dashboard)
