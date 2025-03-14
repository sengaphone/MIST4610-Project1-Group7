# MIST4610-Project1-Group7

## Team Name

61608 Group 7

## Team Members

- Allmond, Chandler [@Chandler Allmond](https://github.com/chandlerallmond)
- Barton, Nick [@Nick Barton](https://github.com/nicholasbarton1)
- Kamdar, Manav [@Manav Kamdar](https://github.com/manavk2004)
- Sengaphone, Vincent [@Vincent Sengaphone](https://github.com/sengaphone)
- Wilson, Landon [@Landon Wilson](https://github.com/landonnn0)

## Problem Description

Retail technology businesses, such as Best Buy, face challenges in efficiently managing inventory, sales transactions, and product categorization. Without an organized database system, these businesses may encounter difficulties such as:
- Overstocking or understocking due to poor inventory tracking.
- Inefficient sales tracking, leading to unclear insights on employee performance and product demand.
- Difficulty in categorizing products, which slows down retrieval and impacts customer service.
- Lack of visibility into sales trends, making it harder for management to optimize stock levels and pricing strategies.

To address these challenges, the Electronic Product Database is designed as a comprehensive inventory and sales tracking system. This database will:
- Store detailed product information, including descriptions, pricing, warranty periods, and brand associations.
- Track real-time inventory status, restock dates, and reorder quantities.
- Facilitate sales transactions, recording employee sales contributions, transaction amounts, and payment methods.
- Enable sales analysis, allowing management to identify top-selling products, evaluate employee performance, and forecast future demand.

By implementing this database, businesses can improve inventory accuracy, sales efficiency, and data-driven decision-making to enhance overall operations.

## Data Model

The Electronic Product Database is designed to manage the inventory and sales of an electronics retail business. This data model provides a structured way to store and retrieve information about electronic products, their availability, and their categorization. The electronic_product table serves as the core of the model, linking products to their respective brands and categories through the brand_name and type_of_device tables. Additionally, the inventory table ensures that stock levels and restocking requirements are efficiently tracked, preventing shortages and optimizing supply chain operations.

The sales transaction process is handled through the sales_transaction and sales_transaction_product tables, which record transaction details, payment methods, and the number of products sold. Each sale is associated with an employee, stored in the employee table, allowing management to track individual employee contributions to sales. This structure ensures that every transaction is linked to both the products being sold and the employees processing the sales, making it easier to evaluate performance and analyze revenue trends.

By integrating inventory, sales, and employee management, this database provides businesses with real-time insights into product performance, stock availability, and financial transactions. The structured relationships between tables allow for streamlined data retrieval, enabling managers to make data-driven decisions regarding restocking, sales strategies, and employee performance evaluations. This system ultimately helps improve operational efficiency, profitability, and customer satisfaction by ensuring that products are always available and transactions are accurately recorded.

<img width="900" alt="Screenshot 2025-03-13 at 12 19 05 PM" src="https://github.com/user-attachments/assets/c6c8cd46-78a9-4456-b608-b9e2f40262f3" />

## Data Dictionary
<img width="900" alt="Screenshot 2025-03-13 at 12 20 06 PM" src="https://github.com/user-attachments/assets/dc9f1a92-b577-40d0-bfab-adac8ece3084" />
<img width="900" alt="Screenshot 2025-03-13 at 12 20 22 PM" src="https://github.com/user-attachments/assets/77e83dca-8f99-437c-a9ae-e250dee4787d" />
<img width="900" alt="Screenshot 2025-03-13 at 12 20 39 PM" src="https://github.com/user-attachments/assets/b33d44a1-c8c7-43f5-880e-77b2926b1a32" />
<img width="900" alt="Screenshot 2025-03-13 at 12 20 50 PM" src="https://github.com/user-attachments/assets/90d96c14-706e-4d7e-98c9-3f65ccdbc981" />
<img width="900" alt="Screenshot 2025-03-13 at 12 21 05 PM" src="https://github.com/user-attachments/assets/f8dc6c0c-543f-46c5-b660-ed8cfe772f25" />
<img width="900" alt="Screenshot 2025-03-13 at 12 23 04 PM" src="https://github.com/user-attachments/assets/b37241b5-5a6b-4382-91ed-12f8ffc8e35d" />
<img width="900" alt="Screenshot 2025-03-13 at 12 23 12 PM" src="https://github.com/user-attachments/assets/4f63523c-ec80-4cac-a3c6-45fa87eab643" />

## Queries

1. Low Stock / High Stock Alert

This query identifies products with low stock levels and high stock levels to help businesses manage inventory efficiently. The low stock alert retrieves products with a stock quantity of 30 or less, ensuring that managers restock them before they run out. The high stock alert retrieves products with a stock quantity greater than 50, helping managers avoid excessive inventory that could lead to high storage costs or markdowns. Both queries order the results in ascending order of stock quantity for better visibility.

<img width="900" alt="Screenshot 2025-03-14 at 11 49 47 AM" src="https://github.com/user-attachments/assets/ddaefcb3-d5b4-4674-9d11-184f393adc1d" />

Managers can use this query to maintain balanced stock levels by ensuring that fast-selling products are restocked in time while preventing overstocking of slow-moving items. This helps businesses reduce waste, improve cash flow, and optimize inventory space, leading to better profitability and operational efficiency.

2. Best Selling Products

This query retrieves the top 5 best-selling products based on the total quantity sold. The results are sorted in descending order by sales volume.

<img width="900" alt="Screenshot 2025-03-14 at 11 51 50 AM" src="https://github.com/user-attachments/assets/67cf0392-f729-492b-a506-6c93e98f42c4" />

Managers can identify high-demand products, allowing them to prioritize restocking and promotional efforts.

3. Total Revenue by Product Category

This query calculates the total sales revenue for each product category while filtering out categories that generate less than the average revenue of all categories. It first groups transactions by product category to compute total revenue and then applies a HAVING clause to retain only those categories that exceed the average revenue. A subquery is used to determine the overall average category revenue, ensuring that the analysis focuses on high-performing product categories.

<img width="900" alt="Screenshot 2025-03-14 at 11 53 23 AM" src="https://github.com/user-attachments/assets/67fae300-db5a-4ce9-9470-0f39a68c9e23" />

Managers can use this query to identify high-performing product categories that generate above-average revenue. By filtering out lower-performing categories, businesses can allocate more resources to profitable categories, optimize inventory planning, and adjust marketing strategies for better financial outcomes.

4. Top 3 most profitable brands

If a store wanted to maximize revenue by stocking the brands from which consumers were purchasing most from, this code would be beneficial to visualize which brands sat at the top of the revenue chart.

<img width="900" alt="Screenshot 2025-03-14 at 11 55 30 AM" src="https://github.com/user-attachments/assets/5f0aee76-fac4-4b87-92b7-3ba096ea0fca" />

This query joins the sales transaction, sales transaction for products, electronic product, and brand name tables then groups it by brand name then order by total revenue. Then we set the limit to 3 in order to show only the top 3 brands by revenue.

5. Query 5

Query 5 shows show each of the employee’s sales performance and gives basic information including their name and employee id

<img width="900" alt="Screenshot 2025-03-14 at 11 56 39 AM" src="https://github.com/user-attachments/assets/37da92ba-bc84-4261-8944-d8c2f3e3182f" />

Managers can use this to gauge whether employees are meeting the standards that the company has set for itself. Having a clear and concise table showing the level of performance each employee brings into the company can allow managers to pinpoint those who may need extra assistance, and give the proper guidance for success. Comparing the performance of each employee overtime can allow the managers to make logical decisions to keep employees, fire employees, give bonuses, etc.

6. Monthly Sales Trends

This query displays the year, month, and total sales revenue for each month. The results are grouped by month and sorted in descending order to show the most recent months first.

<img width="900" alt="Screenshot 2025-03-14 at 11 58 18 AM" src="https://github.com/user-attachments/assets/10c92a66-400f-4328-887e-5766953d7d62" />

Managers can use this query to analyze sales trends over time, identifying seasonal patterns and peak sales months. This insight helps businesses make data-driven decisions about inventory management, pricing strategies, and marketing campaigns to maximize revenue.

7. Total Sales Transactions

This query retrieves the total number of transactions in the system.

<img width="900" alt="Screenshot 2025-03-14 at 11 59 05 AM" src="https://github.com/user-attachments/assets/afc545aa-557b-4d05-b381-f063e85f6b11" />

Gives managers a quick snapshot of overall sales activity.

8. List of All Employees

Retrieves basic employee details, sorted alphabetically by last name.

<img width="900" alt="Screenshot 2025-03-14 at 11 59 56 AM" src="https://github.com/user-attachments/assets/7099a2d5-e9fa-481f-851b-1241f138c3b6" />

Provides a quick reference for employee records.

9. Most Used Payment Method

Finds the most frequently used payment methods.

<img width="900" alt="Screenshot 2025-03-14 at 12 00 32 PM" src="https://github.com/user-attachments/assets/49fccf85-428b-4a47-8857-ab21377bcf6d" />

Helps managers analyze customer payment preferences.

10. 10th Query

The 10th query shows the average transaction value of each customer, meaning the average amount that a customer will spend.

<img width="900" alt="Screenshot 2025-03-14 at 12 01 21 PM" src="https://github.com/user-attachments/assets/96b6d1d9-c89a-4be0-8f7a-709eb0b6789e" />

While this code is quite simple, managers can use this in a variety of ways. Taking a sample set of a few months and using it as a barometer for the following months can allow managers to see if there are fluctuations in the amount that customers usually spend. If significant fluctuations occur during certain parts of the year, managers can conclude that their product/service may have a seasonality component to it. If suddenly consumers start spending less, there may be new competition that has entered the market that the manager may be unaware of. If consumers are buying a lot of product, but there’s a disconnect with the transaction value, the product simply may not be priced high enough

## Database Information

<img width="900" alt="Screenshot 2025-03-14 at 12 03 13 PM" src="https://github.com/user-attachments/assets/f5e2b2c4-2835-43b0-8f10-7224cfb01ebd" />

Database name on server: ha_group7_crn61608


