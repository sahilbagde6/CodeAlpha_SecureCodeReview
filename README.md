# CodeAlpha_SecureCodeReview

## 🚀 Overview
Secure Coding Review project for CodeAlpha Cyber Security Internship.  
Includes sample vulnerable code, identified vulnerabilities, fixes, and a brief report with recommendations.

---

## 🔍 Contents
- `vulnerable/` — vulnerable sample apps (Python examples)
- `fixed/` — secure versions with fixes applied
- `report/SecureCodeReview_Report.pdf` — findings & remediation steps
- `tools/` — static analyzer configs & scripts (e.g., Bandit for Python)

---

## 🛠 Example Vulnerability Found
**Issue:** SQL Injection in Python `login()` using string formatting  
**Vulnerable code:**
```python
cursor.execute(f"SELECT * FROM users WHERE username='{username}' AND password='{password}'")

Fix:

cursor.execute("SELECT * FROM users WHERE username=? AND password=?", (username, password))
---

✅ Checklist used for review

Input validation & sanitization

Use of parameterized queries / prepared statements

Password storage (use hashing + salt)

No hardcoded secrets

Proper error handling (no stack traces to users)

Use static analysis tools (Bandit / SonarQube)



---

▶️ How to run static scan (Python example)

pip install bandit
bandit -r vulnerable/


---

📄 Report

The report/ folder contains:

Summary of findings (High/Medium/Low)

Repro steps & PoC (if safe)

Recommended fixes & code snippets



---

⚠️ Ethics

Only perform code reviews with permission. Don’t test or exploit live apps without authorization.

🙌 Credits

Prepared under CodeAlpha Cyber Security Internship.
