# Power-BI-project-on-Production-and-Sales
Power BI dashboard for Maven Market - Sales, Returns &amp; Performance Analysis
# Maven Market Power BI Report

This project analyzes customer transactions, returns, and product performance using Power BI.

## 📁 Files
- `report.pbix`: Power BI report with data model, DAX measures, and visualizations.

## ✅ Key Components

### 🔸 Part 1: Connecting & Shaping the Data
- Imported 7 CSV files and combined transactions from two years
- Performed column transformations and calculated fields using Power Query
- Cleaned and formatted data, replaced nulls, and created meaningful fields like `full_name`, `birth_year`, `discount_price`, `area_code`
- Created a conditional column named "has_children"
- Used the statistics tools to return the number of distinct product brands, followed by distinct 
product names
- Added a calculated column named "full_address", by merging "store_city", "store_state", and 
"store_country", separated by a comma and space
- Used the date tools in the query editor to add the following columns: 
• Start of Week (starting Sunday) 
• Name of Day 
• Start of Month 
• Name of Month 
• Quarter of Year 
• Year 

### 🔸 Part 2: Data Modeling
- Created a star schema with lookup and fact tables
- Built a snowflake relationship between `Stores` and `Regions`
- Defined proper cardinality and direction
- Hid unnecessary columns from Report View
- Categorized geographical fields for map visuals
- Updated all date fields (across all tables) to the "M/d/yyyy" format using the formatting tools 
in the Modeling tab
- Updated the "product_retail_price", "product_cost", and "discount_price" to Currency ($ 
English) format
-  Categorized "customer_city" as City, "customer_postal_code" 
as Postal Code, and "customer_country" as Country/Region
- Categorized "store_city" as City, "store_state" as State or Province, 
"store_country" as Country/Region, and "full_address" as Address 

### 🔸 Part 3: DAX Measures & Calculated Columns
- In the DATA view, added the following calculated columns: 
• In the Calendar table, add a column named "Weekend"
 
• Equals "Y" for Saturdays or Sundays (otherwise "N")

• In the Calendar table, add a column named "End of Month" 

• Returns the last date of the current month for each row 

• In the Customers table, add a column named "Current Age" 

• Calculated current customer ages using the "birthdate" column and the TODAY() 
function 

• In the Customers table, add a column named "Priority" 

• Equals "High" for customers who own homes and have Golden membership cards 
(otherwise "Standard") 

• In the Customers table, add a column named "Short_Country" 

• Returned the first three characters of the customer country, and converts 
to all uppercase

• In the Customers table, add a column named "House Number" 

• Extracted all characters/numbers before the first space in the "customer_address" 
column (hint: use SEARCH) 

• In the Products table, add a column named "Price_Tier" 

• Equals "High" if the retail price is >$3, "Mid" if the retail price is >$1, and "Low" 
otherwise

• In the Stores table, add a column named "Years_Since_Remodel" 

• Calculated the number of years between the current date (TODAY()) and the last 
remodel date

-In the Report View Created measures for:
1. "Quantity Sold" and "Quantity Returned" to calculate the sum 
of quantity from each data table 
2. "Total Transactions" and "Total Returns" to calculate the 
count of rows from each data table 
3. "Return Rate" to calculate the ratio of quantity returned to 
quantity sold (format as %) 
4."Weekend Transactions" to calculate transactions 
on weekends
5. "% Weekend Transactions" to calculate weekend 
transactions as a percentage of total transactions (format as %)
6.  "All Transactions" and "All Returns" to calculate grand total 
transactions and returns (regardless of filter context)
7.  "Total Revenue" based on transaction quantity and 
product retail price, and format as $
8.  "Total Cost" based on transaction quantity and product 
cost, and format as $
9.  "Total Profit" to calculate total revenue minus total cost, and 
format as $
10. e "Profit Margin" by dividing total profit by total 
revenue calculate total revenue (format as %)
11.  "Unique Products" to calculate the number of unique product 
names in the Products table
12. "YTD Revenue" to calculate year-to-date total revenue, and 
format as $
13.  "60-Day Revenue" to calculate a running revenue total over a 
60-day period, and format as $
14.  "Last Month Transactions", "Last Month Revenue", "Last 
Month Profit", and "Last Month Returns"
15. "Revenue Target" based on a 5% lift over the previous month 
revenue, and format as $ 

### 🔸 Part 4: Report Design & Insights
- Created interactive visuals:
  - Matrix with conditional formatting
  - KPI cards with targets
  - Map and treemap for geographic analysis
  - Column and gauge charts for trend and target tracking
- Implemented bookmarks and drill-through for insight storytelling
- Created a "Notes" page to document key events (e.g. Portland 1000 sales)


## 🧰 Tools Used
- Power BI Desktop
- DAX
- GitHub

![Screenshot (12)](https://github.com/user-attachments/assets/d0662c53-f4ee-453a-9b9f-113f82b7002e)


