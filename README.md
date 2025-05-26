# 🔐 Cyber Security Internship Task 1

## 📌 Task Objective
Scan the local network to detect live hosts and open ports using Nmap. Analyze the results and identify potential security vulnerabilities.

---

## 🛠️ Tools Used
- **Nmap** for port scanning
- **Kali Linux** as the operating system
- *(Optional)* **Wireshark** for packet analysis

---

## 🌐 Network Information
- **Local IP:** `192.168.73.128`
- **Scanned Subnet:** `192.168.73.0/24`
- **Total Hosts Up:** 4

---

## 🧪 Commands Used
```bash
# TCP SYN Scan with output in text format
sudo nmap -sS 192.168.73.0/24 -oN scan_results.txt

# Save results in XML format
sudo nmap -sS 192.168.73.0/24 -oX scan.xml

# Convert XML to HTML report (optional)
xsltproc scan.xml -o scan_report.html
```

---

## 📄 Scan Summary

### 🟢 Host: 192.168.73.1
- **Open Ports:** 135 (MSRPC), 139 (NetBIOS-SSN), 445 (Microsoft-DS), 903 (VMware ISS), 3000 (PPP), 3001 (Nessus)
- **Risks:** 
  - SMB services (ports 139 & 445) vulnerable to attacks like WannaCry
  - Nessus port may expose security scanner interface

### 🟢 Host: 192.168.73.2
- **Open Port:** 53 (DNS)
- **Risk:** DNS spoofing or amplification if misconfigured

### 🔵 Host: 192.168.73.254
- **Ports:** All filtered

### 🔵 Host: 192.168.73.128 (Your Kali machine)
- **Ports:** All closed — secure

---

## ⚠️ Security Risks Identified
| Port | Service     | Risk Description                                |
|------|-------------|--------------------------------------------------|
| 445  | SMB         | Vulnerable to EternalBlue, WannaCry              |
| 3001 | Nessus      | Potential access to sensitive security scan data |
| 53   | DNS         | Risk of DNS spoofing if not secured              |

---

## 📁 Files Included
- `scan_results.txt` – Raw Nmap output
- `scan_report.html` – HTML formatted report *(optional)*
- `Cybersecurity_Task1_Report.docx` – Final documented report
- `README.md` – This file

---

## ✅ Conclusion
The scan revealed open ports that could expose the network to attacks. It’s recommended to disable unused services and secure essential ones with updated patches and firewall rules.

---

**🔗 Submitted by:** Harshitha Belaganti  
**📅 Date:** May 26, 2025  
