# <img src="https://upload.wikimedia.org/wikipedia/en/c/cb/Raspberry_Pi_Logo.svg" alt="Raspberry Pi Logo" width="80"/>  Recursive Pi-Hole DNS Server

Deploy a recursive Pi-Hole DNS sinkhole on a Raspberry Pi to improve network security by blocking unwanted ads, tracking domains, and malicious websites. Configure Pi-Hole to filter DNS requests at the network level, preventing devices from accessing harmful or undesirable content. Regularly update blocklists and fine-tune settings to optimize performance, reduce security vulnerabilities, and ensure the protection of all connected devices from potential threats.

---

<img width="887" height="507" alt="Pihole 1 jpg" src="https://github.com/user-attachments/assets/952774b6-bcad-4d5c-8438-3e4c9a3b2a30" />




---

## 📌 Overview

**Pi-Hole** acts as a DNS sinkhole that filters DNS requests and blocks access to unwanted content like ads, trackers, and malicious websites. When integrated with **Unbound**, it resolves DNS queries recursively without relying on external DNS providers, significantly improving privacy and protection from man-in-the-middle attacks.

---

## ⚙️ Installation & Configuration

### 🔧 Raspberry Pi Setup
- Flashed Raspberry Pi OS onto a Raspberry Pi
- Enabled SSH and connected remotely

### 📦 Pi-Hole Installation
```bash
curl -sSL https://install.pi-hole.net | bash
```
Assigned a static IPv4 address for DNS consistency

📚 Blocklist Configuration
To optimize DNS filtering:

Selected curated blocklists targeting:

Ads

Malware

Privacy trackers

Avoided redundant/overlapping lists

Prioritized high-quality, regularly updated sources

Ensured low overhead and smooth performance

🔄 Unbound DNS Integration
Unbound enhances DNS privacy and security by handling all queries locally.

🛠 Setup Steps
Install Unbound:
```bash
sudo apt install unbound -y
```
In Pi-Hole:

Go to Settings > DNS

Set Custom Upstream DNS to 127.0.0.1#5335
![Pi-hole Raspberry Pi Setup](https://discussion.scottibyte.com/uploads/default/original/2X/b/bba61f91e98bde1e0ae7f3fd5c2ea6fd208faea4.png)


🧱 Challenges
🔁 pfSense Setup
Issue: pfSense defaults to external DNS

Fix: Routed DNS through Pi-Hole by:

Assigning Pi-Hole IP as DNS server in pfSense

Adjusting firewall and DNS forwarding rules

📈 Blocklist Overhead
Stricter lists increased latency

Optimized by reducing redundancy and updating only the most effective lists

✅ Outcome
Successfully deployed a recursive Pi-Hole DNS sinkhole with:

Enhanced network-wide security

Faster and more private DNS resolution

Reduced exposure to online threats

Minimal performance overhead








