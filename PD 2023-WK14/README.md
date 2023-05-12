# Challenge by: Alfred Chan

We've got a guest contributor this week! Alfred is part of DS28 at the Data School.

In this week's Preppin’ Data Challenge you are required to examine and compile a report on all countries’ trading data. The report should contain information of the import and export data. 

Another request is to make sure the import and export can be visualised on a map so some additional spatial data is needed.

We are going to use a public data from the World Integrated Trade Solutions to examine the trade data across countries.

Link to the website: https://wits.worldbank.org/datadownload.aspx?lang=en  

## Part 1
# Input the data

- Input the world trade data, pull in all countries’ files
- Make sure Prep reads the first line of the file as header
- Update the data role of the Reporter and Partner fields from string to Country/ Region (some countries will not be recognised, but we will keep them in)
- Get the country code for each country from the file path E.g AFG for Afghanistan 
- Keep Import and Export data only
- Remove “World”, “European Union”, “"Occ.Pal.Terr" and "Other Asia, nes" in the Reporter column as they are not countries
- Remove “…”, “Special Category” and “World” in the Partner column
- Remove file path
- Make sure all years are in the same column
- Name it “Year” and change data type to date 
- Change the pivoted value to number (decimal) and pivot them up as column using Indicator as column names

## Part 2
- Input the Countries geo data
- Remove unnecessary columns
- Get the latitude and longitude from the “geo_point_2d” column 
- First coordinate as Latitude, second as Longitude
- Make sure the data type is number(decimal)
- Join the countries geo data to the trade data
- Make sure no record from the trade data is lost from the join
- Remove countries name and code fields from the geo data
- After getting the latitude and longitude for the reporting country, we now need to get the same for partner countries as well
- Get the country code for the partner country and join with geo data again to get the coordinates for the partner countries
- Add suffix “_Partner” to the latitude and longitude of partners
- Output the data.

# Output - 15 fields 
- Year
- Reporter
- Reporter Country Code
- Reporter Latitude
- Reporter Longitude
- Partner 
- Country Code_Partner
- Latitude_Partner
- Longitude_Partner
- Product Categories
- Indicator Type
- Trade (US$ Mil)-Top 5 Export Partner
- Trade (US$ Mil)-Top 5 Import Partner
- Partner share(%)-Top 5 Export Partner
- Partner share(%)-Top 5 Import Partner
- 43,898 rows (43,899 including headers)
