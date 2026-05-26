# StudyBuddy - Cloud Server Documentation

**Student:** Md Mohibur Rahman Rahi  
**Student ID:** 35719994  
**Domain:** [https://studybuddy1.xyz](https://studybuddy1.xyz)  
**IP Address:** 3.107.51.105  
**Video Explainer:** [Link to be added]

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Server Provisioning (AWS EC2)](#server-provisioning-aws-ec2)
3. [Web Server Setup (Apache)](#web-server-setup-apache)
4. [Domain Name Configuration](#domain-name-configuration)
5. [SSL/TLS Setup (Let's Encrypt)](#ssltls-setup-lets-encrypt)
6. [Custom Script - JavaScript Task List](#custom-script---javascript-task-list)
7. [Maintenance & Renewal](#maintenance--renewal)
8. [References](#references)

---

## Project Overview

StudyBuddy is a personal learning dashboard hosted on AWS EC2 (Infrastructure as a Service). It helps students track study goals, deadlines, and quick notes through a clean web interface. The server runs Ubuntu 24.04 LTS with Apache, and includes a custom JavaScript task list that saves data in the browser using localStorage.

**Tech Stack:**
- Ubuntu Server 24.04 LTS
- Apache Web Server
- HTML, CSS, JavaScript
- Let's Encrypt SSL/TLS
- AWS EC2 (t3.micro)

---

## Server Provisioning (AWS EC2)

### Step 1: Launch EC2 Instance

1. Navigate to AWS EC2 Console > **Launch Instance**
2. **Name:** `ICTwebserver`
3. **AMI:** Ubuntu Server 24.04 LTS (Free tier eligible)
4. **Instance Type:** t3.micro (Free tier eligible)
5. **Key Pair:** Create new `ICT171-key`, download `.pem` file
6. **Network Settings:**
   - Allow SSH (port 22) from My IP
   - Allow HTTP (port 80) from Anywhere (0.0.0.0/0)
   - Allow HTTPS (port 443) from Anywhere (0.0.0.0/0)
7. **Storage:** 8 GiB gp3 (default)
8. Click **Launch Instance**

### Step 2: Connect via SSH

```bash
ssh -i "ICT171-key.pem" ubuntu@<public-ip>
