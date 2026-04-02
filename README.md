# 🚀 MuleSoft Bulk Insert Project

## 📌 Overview
This project demonstrates how to perform **bulk insertion of CSV data into a MySQL database** using MuleSoft.

The application reads employee data from a CSV file, transforms it into JSON format, and inserts multiple records into the database using the **Bulk Insert operation**.

---

## 🏗️ Architecture Flow

1. HTTP Request triggers the flow
2. File Connector reads CSV file
3. DataWeave transforms CSV → JSON
4. Database Bulk Insert inserts multiple records
5. Success response returned

---

## ⚙️ Technologies Used
- MuleSoft (Anypoint Studio)
- DataWeave 2.0
- File Connector
- HTTP Listener
- Database Connector (MySQL)

---

## 📂 File Details
- **File Path:**  
  `C:\Users\saivi\Downloads\employees_100.csv`

- The CSV file should contain fields:
  - username
  - id
  - designation
  - salary
  - age

---

## 🌐 API Details

- **Method:** POST  
- **URL:**  
  `http://localhost:8081/bulk-insert`

---

## 🔄 Flow Explanation

### 1. HTTP Listener
- Listens on port `8081`
- Endpoint: `/bulk-insert`

---

### 2. File Read
- Reads CSV file from local system
- Uses File Connector

---

### 3. Data Transformation
- Converts CSV data into JSON format using DataWeave

```dw
%dw 2.0
output application/json
---
payload
