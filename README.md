# 📚 SQL Essentials: Functions, Joins & Script Automation

Welcome to the ultimate SQL Cheat Sheet and Script Library! This repository is a helpful reference for SQL enthusiasts, students, and developers looking to sharpen their skills in **MySQL** and **DB2** databases. Whether you're brushing up on your SQL functions or automating database creation with scripts — this guide is for you!

---

## 🔧 SQL Functions Cheat Sheet

A quick reference for frequently used SQL functions:

| **Function** | **Syntax** | **Description** | **Example** |
|-------------|------------|----------------|-------------|
| `COUNT()`   | `SELECT COUNT(column) FROM table WHERE condition;` | Returns the number of rows matching a condition. | `SELECT COUNT(dep_id) FROM employees;` |
| `AVG()`     | `SELECT AVG(column) FROM table WHERE condition;` | Calculates the average of a numeric column. | `SELECT AVG(salary) FROM employees;` |
| `SUM()`     | `SELECT SUM(column) FROM table WHERE condition;` | Returns the total sum of a column. | `SELECT SUM(salary) FROM employees;` |
| `MIN()`     | `SELECT MIN(column) FROM table WHERE condition;` | Returns the smallest value. | `SELECT MIN(salary) FROM employees;` |
| `MAX()`     | `SELECT MAX(column) FROM table WHERE condition;` | Returns the largest value. | `SELECT MAX(salary) FROM employees;` |
| `ROUND()`   | `SELECT ROUND(number, decimals);` | Rounds a number to specified decimals. | `SELECT ROUND(salary) FROM employees;` |
| `LENGTH()`  | `SELECT LENGTH(column) FROM table;` | Returns length of a string (in bytes). | `SELECT LENGTH(f_name) FROM employees;` |
| `UCASE()`   | `SELECT UCASE(column) FROM table;` | Converts text to uppercase. | `SELECT UCASE(f_name) FROM employees;` |
| `LCASE()`   | `SELECT LCASE(column) FROM table;` | Converts text to lowercase. | `SELECT LCASE(f_name) FROM employees;` |
| `DISTINCT`  | `SELECT DISTINCT column FROM table;` | Removes duplicates from result. | `SELECT DISTINCT UCASE(f_name) FROM employees;` |
| `DAY()`     | `SELECT DAY(column) FROM table;` | Returns day from a date column. | `SELECT DAY(b_date) FROM employees WHERE emp_id = 'E1002';` |
| `CURRENT_DATE` | `SELECT CURRENT_DATE;` | Displays the current date. | `SELECT CURRENT_DATE;` |
| `DATEDIFF()` | `SELECT DATEDIFF(date1, date2);` | Calculates the difference between two dates. | `SELECT DATEDIFF(CURRENT_DATE, date_column) FROM table;` |
| `FROM_DAYS()` | `SELECT FROM_DAYS(number);` | Converts days to `YYYY-MM-DD` format. | `SELECT FROM_DAYS(DATEDIFF(CURRENT_DATE, date_column)) FROM table;` |
| `DATE_ADD()` | `SELECT DATE_ADD(date, INTERVAL n type);` | Adds interval to date. | `SELECT DATE_ADD(date, INTERVAL 3 DAY);` |
| `DATE_SUB()` | `SELECT DATE_SUB(date, INTERVAL n type);` | Subtracts interval from date. | `SELECT DATE_SUB(date, INTERVAL 3 DAY);` |

---

## 🔁 Subqueries & Joins

### 🧩 Subquery

```sql
SELECT emp_id, f_name, l_name, salary
FROM employees
WHERE salary < (
  SELECT AVG(salary)
  FROM employees
);
