# Analysing-Smart-City-Bike-Sharing-Data-Using-Power-BI


## Project Overview

Analysed real-time public bike-sharing station data across multiple cities to uncover performance and usage patterns
Performed data cleaning in Power Query — removed columns, split position into latitude/longitude, applied TRIM, CLEAN, PROPER
Built a Star Schema with 1 fact table (Fact_main1) and 3 dimension tables: Date_dim2, Station_dim4, Contract_dim3
Created DAX measures: Total Stations, Total Available Bikes, Total Bike Stands
Designed an interactive Power BI dashboard covering contract performance, time trends, banking features, and geographic distribution


## Tools 

• Power BI

• DAX 

• Power Query


## Data Cleaning & Preparation

1.Removed unnecessary columns
Dropped irrelevant fields using Table.RemoveColumns to reduce noise and improve query performance. Only analytical columns were retained.

2.Split position column into Latitude & Longitude
The combined position column was split using Split Column by Delimiter → Comma → Each occurrence, producing two clean numeric columns: Latitude and Longitude for location-based analysis.

3.Standardised text data
Applied text transformation functions to ensure consistent formatting across all text fields

4.Changed column data types
Ensured correct data types — Latitude/Longitude set to Decimal Number, Date fields to Date/Time, Boolean fields (Banking, Bonus, Status) validated as True/False.

5.Renamed and reorganised columns
Columns were renamed for clarity and consistency (e.g., position.1 → Latitude, position.2 → Longitude) to improve readability in reports and DAX formulas.


## Data Modelling

This is a Star Schema.
• Fact Table:
 Fact_main1

• Dimension Tables 
Date_dim2
Station_dim4
Contract_dim3


## Relationships

•	Date_dim2 (1) → Fact_main1 (*) 
•	Station_dim4 (1) → Fact_main1 (*) 
•	Contract_dim3 (1) → Fact_main1 (*) 
•	This is Many-to-One (*:1)


## Key Insights

•	Total Available Bikes and Bike stands by contact name
•	Count of Station Id by Banking
•	Average Availbale Bikes by Month
•	Total Available Bikes by Contract Name
•	Total Available Bikes By Latitude and Longitude

## Slicers and KPI cards

Implemented slicers for years and KPI cards for Total Stations , Total Available bikes and Total bike stands using DAX measures

## Key Business Insights

•	Bike availability is consistently high across most contracts, indicating strong supply but possible underutilization in some areas.

•	Bike stands are relatively stable compared to bikes, suggesting infrastructure is not scaling at the same pace as bike availability.

•	Monthly trend shows fluctuations with noticeable dips, indicating seasonal or demand-based variation in bike usage.

•	Geographical concentration is heavily centered in Europe, meaning operations are regionally focused with limited global spread.

•	Banking vs Non-banking stations are evenly split (50/50), showing balanced partnership distribution but no dominant model.

•	Certain cities/contracts dominate bike availability, indicating uneven distribution and potential inefficiency in allocation.


## Business Recommendations

•	Optimize bike distribution across low-performing cities instead of maintaining excess supply in already saturated areas.

•	Align bike stands expansion with bike availability, otherwise operational inefficiencies will increase.

•	Investigate seasonal demand patterns and adjust bike allocation dynamically (more bikes during peak months).

•	Expand operations beyond current geographic concentration to reduce regional dependency.

•	Evaluate performance of banking vs non-banking stations to identify which model drives better utilization.

•	Focus on demand-driven allocation rather than uniform distribution to improve efficiency and ROI.


## Conclusion

Bike availability is generally high across cities, but uneven distribution and seasonal fluctuations indicate inefficiencies. Optimizing allocation based on demand and expanding strategically can improve overall system performance and utilization.
