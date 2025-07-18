# Quick Start Guide - Tiation Parrot Security AU

Get up and running with Parrot Security OS optimized for Australian users in just a few minutes!

## 🚀 Pre-Installation Checklist

Before you begin, ensure you have:

- [ ] A computer with at least 4GB RAM (8GB recommended)
- [ ] 20GB free disk space (40GB recommended)
- [ ] USB drive (8GB minimum) for installation media
- [ ] Stable internet connection
- [ ] Australian timezone settings preference

## 📥 Download Parrot Security OS

1. Visit the [official Parrot Security website](https://www.parrotsec.org/download/)
2. Download the latest Security Edition ISO
3. Verify the download integrity using the provided checksums

## 🔧 Create Installation Media

### Using Balena Etcher (Recommended)
1. Download [Balena Etcher](https://www.balena.io/etcher/)
2. Select your Parrot Security ISO
3. Select your USB drive
4. Click "Flash" to create bootable media

### Using dd (Linux/macOS)
```bash
sudo dd if=parrot-security-version.iso of=/dev/sdX bs=4M status=progress
```

## 💻 Installation Process

1. **Boot from USB**
   - Insert USB drive and restart your computer
   - Select USB drive from boot menu (usually F12 or F2)

2. **Start Installation**
   - Select "Install Parrot Security"
   - Choose your language (English - Australia recommended)

3. **Australian Localization**
   - **Location**: Australia
   - **Timezone**: Australian Eastern Standard Time (AEST)
   - **Keyboard**: English (Australia)
   - **Locale**: en_AU.UTF-8

4. **Disk Partitioning**
   - For beginners: Use guided partitioning
   - For advanced users: Manual partitioning with separate /home

5. **User Account Setup**
   - Create a strong password
   - Enable automatic login (optional, not recommended for security)

## 🇦🇺 Post-Installation AU Configuration

### Update System
```bash
sudo apt update && sudo apt upgrade -y
```

### Configure Australian Settings
```bash
# Set timezone
sudo timedatectl set-timezone Australia/Sydney

# Update locale
sudo locale-gen en_AU.UTF-8
sudo update-locale LANG=en_AU.UTF-8

# Install Australian spell checking
sudo apt install hunspell-en-au
```

### Network Configuration for Australian ISPs
```bash
# Common Australian DNS servers
echo "nameserver 1.1.1.1" | sudo tee -a /etc/resolv.conf
echo "nameserver 8.8.8.8" | sudo tee -a /etc/resolv.conf
```

## 🔧 Essential Tools Setup

### Install Additional Security Tools
```bash
# Update package list
sudo apt update

# Install essential tools
sudo apt install -y \
    nmap \
    wireshark \
    metasploit-framework \
    john \
    hashcat \
    aircrack-ng \
    burpsuite \
    nikto \
    sqlmap \
    gobuster
```

### Configure Firewall
```bash
# Enable UFW firewall
sudo ufw enable

# Allow essential ports
sudo ufw allow ssh
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

## 🛡️ Security Hardening

### Update System Regularly
```bash
# Create update script
echo '#!/bin/bash
sudo apt update
sudo apt upgrade -y
sudo apt autoremove -y
sudo apt autoclean' > ~/update-system.sh

chmod +x ~/update-system.sh
```

### Enable Automatic Security Updates
```bash
sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades
```

## 📚 Next Steps

1. **Read the [Installation Guide](Installation)** for detailed setup instructions
2. **Review [Australian Compliance](Compliance)** requirements
3. **Explore [Security Tools](Tools)** documentation
4. **Join [Australian Security Community](Australian-Security-Community)**

## 🆘 Troubleshooting

### Common Issues

**Issue**: Boot fails from USB
- **Solution**: Ensure UEFI/Legacy boot mode matches ISO requirements

**Issue**: Network not detected
- **Solution**: Install proprietary drivers post-installation

**Issue**: Display resolution problems
- **Solution**: Install additional display drivers

### Getting Help

- Check our [Support Guide](Support)
- Visit [Parrot Security Forums](https://community.parrotsec.org/)
- Join Australian security meetups

---

## 🇦🇺 Australian Resources

- [ACSC Essential Eight](https://www.cyber.gov.au/acsc/view-all-content/essential-eight)
- [Australian Privacy Principles](https://www.oaic.gov.au/privacy/australian-privacy-principles/)
- [AUSCERT](https://www.auscert.org.au/)
- [BSides Australia](https://www.bsidesau.com/)

*Need more detailed information? Check out our comprehensive [Installation Guide](Installation)!*
