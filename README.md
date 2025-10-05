# Sales Trend Analysis

This project demonstrates a **monthly sales trend analysis** using SQL on an e-commerce dataset. The analysis calculates **total revenue** and **order volume** for each month, providing insights into sales patterns.

## Dataset

- **Table Name:** `orders`
- **Columns:**
  - `order_id` (INTEGER): Unique identifier for each order
  - `order_date` (DATE): Date of the order
  - `amount` (REAL): Revenue from the order
  - `product_id` (INTEGER): ID of the product sold
- **Rows:** 15 sample entries (for demonstration)

## Tools

- **SQLite** (database)
- **VS Code** (with SQLite extension for running queries)

## SQL Analysis

The analysis uses:

- `SUM(amount)` → total revenue per month  
- `COUNT(DISTINCT order_id)` → number of orders per month  
- `STRFTIME()` → extract year and month from dates  
- `GROUP BY` → aggregate data by year and month  
- `ORDER BY` → sort results chronologically

Example query:

```sql
SELECT 
    STRFTIME('%Y', order_date) AS year,
    STRFTIME('%m', order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_count
FROM orders
GROUP BY year, month
ORDER BY year, month;
