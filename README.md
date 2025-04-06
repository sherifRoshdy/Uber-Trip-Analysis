# Uber Trip Analysis with Power BI

## Overview

This project analyzes Uber trip data using Power BI to extract insights related to booking trends, revenue, and trip efficiency. The analysis helps stakeholders make data-driven decisions to optimize pricing models and improve customer satisfaction. The dashboard is designed to provide a comprehensive overview, time-based analysis, and detailed data exploration.

## Data Sources

The dashboard uses two Excel files as semantic models:

-   **Uber Trip Details.xlsx (Fact Table):** Contains detailed information about each Uber trip.
-   **Location Table.xlsx (Dimension Table):** Provides location-specific data, including Location ID, Location, and City.
-   **Calendar Table:** A supplementary table containing dates from the first to the last date in the dataset, facilitating time-based analysis.

### Uber Trip Details.xlsx Schema
*   **Trip ID:** `INT` (Primary Key) - Unique identifier for each trip.
*   **Pickup Time:** `DATETIME` - The date and time when the trip started.
*   **Drop Off Time:** `DATETIME` - The date and time when the trip ended.
*   **passenger_count:** `INT` - Number of passengers in the trip (1-6).
*   **trip_distance:** `FLOAT` - The distance of the trip in millimeters.
*   **PULocationID:** `INT` (Foreign Key) - ID of the pickup location, referencing `Location Table`.
*   **DOLocationID:** `INT` (Foreign Key) - ID of the drop-off location, referencing `Location Table`.
*   **fare_amount:** `FLOAT` - The fare amount in dollars.
*   **Surge Fee:** `FLOAT` - Additional fee added to the original fare in dollars.
*   **Vehicle:** `VARCHAR` - Type of vehicle used for the trip (UberX, UberXL, Uber Comfort, Uber Black, Uber Green).
*   **Payment_type:** `VARCHAR` - Method of payment used (Cash, Uber Pay, Amazon Pay, Google Pay).

### Location Table.xlsx Schema
*   **LocationID:** `INT` (Primary Key) - Unique identifier for each location.
*   **Location:** `VARCHAR` - Name of the location.
*   **City:** `VARCHAR` - City where the location is situated.

## Dashboards

### Dashboard 1: Overview Analysis

This dashboard provides a high-level overview of Uber trip data, focusing on key performance indicators (KPIs) and trends.

#### Key Performance Indicators (KPIs)

1.  **Total Bookings:** Total number of trips booked over a given period.
2.  **Total Booking Value:** Total revenue generated from all bookings.
3.  **Average Booking Value:** Average revenue per booking.
4.  **Total Trip Distance:** Total distance covered by all trips.
5.  **Average Trip Distance:** Average distance traveled per trip.
6.  **Average Trip Time:** Average duration of trips.

#### Visualizations

*   **Measure Selector:** A dynamic selection tool to switch between KPIs, updating visualizations accordingly.
*   **By Payment Type:** Charts showing KPIs segmented by payment method.
*   **By Trip Type (Day/Night):** Charts differentiating between day and night trips.
*   **Vehicle Type Analysis:** A grid table displaying KPIs across different vehicle types, with conditional formatting to highlight performance.
*   **Total Bookings by Day:** A line chart illustrating daily booking trends.
*   **Most Frequent Pickup Point:** Identifies the most common starting locations for trips.
*   **Most Frequent Drop-off Point:** Identifies the most common drop-off locations. This requires activating an inactive relationship in Power BI between Pickup Location and Drop-off Location in the data model.
*   **Farthest Trip:** Highlights the longest trip based on distance traveled.
*   **Total Bookings by Location (Top 5):** Shows the top 5 locations with the highest trip bookings.
*   **Most Preferred Vehicle for Location Pickup:** Determines the most frequently booked vehicle type at each pickup location.

#### Additional Enhancements
*   **Dynamic Title:** Chart titles update based on the selected measure.
*   **Slicers:** Filters for Date, City, and other interactive filters.
**Tooltips:** Display additional details like Average Booking Value or Trip Distance.
*   ![1](https://github.com/user-attachments/assets/8042e89a-7cc1-49a9-a2e8-70ecc7ed9e4b)
### Dashboard 2: Time Analysis

This dashboard focuses on analyzing trip patterns based on time intervals to optimize operations, pricing, and driver availability.

#### Visualizations

*   **Global Dynamic Measure:** A measure selector for Total Bookings, Total Booking Value, and Total Trip Distance that updates all visuals.
*   **By Pickup Time (10-Minute Intervals):** An area chart grouping trip bookings into 10-minute intervals.
*   **By Day Name:** A line chart showing booking trends across Monday to Sunday.
*   **By Hour and Time:** A heatmap (matrix grid) displaying booking trends by hour and day.
    *   Rows: Hours of the Day (0–23)
    *   Columns: Days of the Week (Mon-Sun)
    *   Values: Selected Dynamic Measure (e.g., Total Bookings)

![2](https://github.com/user-attachments/assets/183095eb-71b3-435e-a634-85199fb9928d)


### Dashboard 3: Details Tab

This tab provides in-depth insights and allows users to explore granular data through drill-through functionality.

#### Features

*   **Grid Table with Key Fields:** Displays essential trip details.
*   **Drill-Through Functionality:** Users can right-click on a data point from other visuals and drill through to this tab to see detailed records.
*   **Bookmark for Full Data View:** A "View Full Data" bookmark to toggle between filtered drill-through data and the complete dataset.

![3](https://github.com/user-attachments/assets/2eb3adc1-06d5-4f8f-8cb3-60ebd08927b3)


## Other Implementation Enhancements

*   **Bookmark for Data Details:** A pop-up or side panel explaining key metrics, table descriptions, data source, and refresh frequency.
*   **Clear Slicer Button:** A button to reset all slicer selections in one click.
