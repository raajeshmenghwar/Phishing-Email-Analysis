# Phishing Email Analysis

## Introduction

Phishing emails are **fraudulent messages** designed to deceive recipients into revealing **sensitive information**, such as:

- **Login credentials**
- **Financial details**
- **Personal data**

These emails often appear to come from **legitimate sources** but may contain **malicious attachments, phishing links, or deceptive requests** for confidential information.

---

## Common Phishing Techniques

- **Email Spoofing** – Forging the sender’s address to appear legitimate.
- **Social Engineering** – Manipulating users into taking harmful actions.
- **Malicious Attachments** – Files containing malware or ransomware.
- **Phishing Links** – Redirecting users to fake login pages.
- **Business Email Compromise (BEC)** – Impersonating executives to request fund transfers or sensitive data.

---

## Security Measures Against Phishing

1. **Email Authentication** – Implement **SPF, DKIM, and DMARC** to verify email senders.
2. **Security Awareness Training** – Educate employees on recognizing phishing attempts.
3. **Anti-Phishing Tools** – Deploy security solutions for real-time phishing detection.
4. **URL & Attachment Scanning** – Use tools like **VirusTotal** to analyze links and attachments.
5. **Incident Response Plan** – Establish a procedure for handling phishing incidents.

---

# Phishing Email Analysis - Step-by-Step Guide

 **GitHub Repository:** [Phishing Email Analysis](http://github.com/raajeshmenghwar/Phishing-Email-Analysis)

 **Project Report:** [Download PDF Report](https://github.com/raajeshmenghwar/Phishing-Email-Analysis/blob/main/Phising%20Email%20Analysis%20Report.pdf)

---

## Pre-requisites

Before running the analysis, ensure you have the required tools installed.

### 1.  Clone the Repository

```bash
git clone http://github.com/raajeshmenghwar/Phishing-Email-Analysis
cd Phishing-Email-Analysis
```

### 2. Install Python (if not already installed)

```bash
sudo apt update && sudo apt install python3 python3-pip -y
```

### 3.  Install Required Security Tools

### Email-IOC-Extractor (Extract indicators from emails)

```bash
git clone https://github.com/MalwareCube/Email-IOC-Extractor.git
cd Email-IOC-Extractor && pip install -r requirements.txt
```

### Didier Stevens Suite (For analyzing email structures and macros)

```bash
git clone https://github.com/DidierStevens/DidierStevensSuite.git
```

---

## Step 1: Email Header Analysis

Email headers contain metadata that helps determine the **origin, path, and legitimacy** of an email.

### 1.1. Manual Header Analysis

- Examine the `Received:` fields to track the email’s journey.
- Check `Reply-To` and `Return-Path` for potential spoofing.
- Analyze SPF, DKIM, and DMARC authentication results.

### 1.2. Online Email Header Analysis Tools

- [**MHA (Mail Header Analyzer)**](https://mha.azurewebsites.net/)
- [**MXToolbox Email Header Analyzer**](https://mxtoolbox.com/EmailHeaders.aspx)

---

## Step 2: Extracting IOCs from Emails

**Tool:** [Email-IOC-Extractor](https://github.com/MalwareCube/Email-IOC-Extractor.git)

Run the script to extract **headers, IP addresses, URLs, and attachments** from phishing emails:

```bash
python Email-IOC-Extractor/eioc.py samples/challenge1.eml --output docs/email1_iocs.json
```

---

## Step 3: Email Attachment Analysis

### Extract Attachments from Emails

**Tool:** [Didier StevensSuite - emldump.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/emldump.py)

```bash
python DidierStevensSuite/emldump.py samples/challenge1.eml
```

### Scan Attachments for Malware

**Tool:** [VirusTotal](https://www.virustotal.com/gui/home/upload)

### 3.1. Threat Intelligence Lookup

**Tool:** [Talos Intelligence](https://talosintelligence.com/)

---

## Step 4: URL Analysis

Phishing emails often contain **deceptive links** leading to fake login pages or **malware-hosting websites**.

### 4.1. URL Reputation Check

**Tool:** [URLScan.io](https://urlscan.io/)

---

## Step 5: VBA Macro Analysis

Phishing emails sometimes contain **Microsoft Office documents** with **embedded VBA macros** used to execute malicious scripts.

**Tool:** [DidierStevensSuite - oledump.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/oledump.py)

```bash
python DidierStevensSuite/oledump.py suspicious.docm
```

---

# Case Studies on Phishing Attacks

### 1. Colonial Pipeline Attack

A phishing email led to a **ransomware attack** that shut down the **largest U.S. fuel pipeline**.

🔗 [**Read More**](https://abnormalsecurity.com/blog/colonial-pipeline-attack-phishing-email-likely-the-culprit)

### 2. Hedge Fund Closes Due to Phishing Attack

A **Business Email Compromise (BEC) attack** caused a hedge fund to lose **millions** and shut down.

[**Read More**](https://www.secureworld.io/industry-news/hedge-fund-closes-after-bec-cyber-attac)

### 3. Ubiquiti Suffers $46M Cyber Heist

Attackers **spoofed internal emails**, tricking employees into transferring funds.

🔗 [**Read More**](https://krebsonsecurity.com/2015/08/tech-firm-ubiquiti-suffers-46m-cyberheist/)

### 4. Ukraine Power Grid Hack (2015)

Attackers used **phishing emails with malicious attachments** to infect control systems.

🔗 [**Read More**](https://en.wikipedia.org/wiki/2015_Ukraine_power_grid_hack)

---

# Future Enhancements

- Automate phishing detection using **machine learning models**.
- Develop a **dashboard** for visualizing email threats.
- Integrate with **SIEM tools** for real-time phishing monitoring.

---
Follow for more updates and insights:

- **[LinkedIn](https://www.linkedin.com/in/raajeshmenghwar)**
- **[Medium](https://raajeshmenghwar.medium.com)**

**Keep hacking and stay curious!**
