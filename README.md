# Default Router IP Addresses & Local Gateway Reference List

A curated quick-reference table of default private IPv4 gateways, automatic fallback subnets, and local DNS hostnames across consumer, prosumer, and ISP networking hardware.

> **Interactive Lookup:** Looking for a specific hardware revision, regional ISP fiber ONT, or default login credentials? Search the live database at **[RouterIPGuide.com](https://routeripguide.com)**.

---

## 1. Default Gateway Reference Table by Manufacturer

| Manufacturer / Firmware | Primary Default IP | Secondary / Auto-Fallback IP | Local Hostname URL | Default Admin Port |
| :--- | :--- | :--- | :--- | :--- |
| **ASUS** (ASUSWRT) | `192.168.50.1` | `192.168.1.1` / `192.168.29.1` | `http://router.asus.com` | `80` / `8443` |
| **Belkin** | `192.168.2.1` | `10.0.0.1` | `http://router` | `80` |
| **Cudy** | `192.168.10.1` | `192.168.1.1` | `http://cudy.net` | `80` |
| **D-Link** | `192.168.0.1` | `192.168.1.1` | `http://dlinkrouter.local` | `80` |
| **GL.iNet** (OpenWrt) | `192.168.8.1` | `192.168.1.1` | N/A | `80` / `443` |
| **Huawei** (HG / OptiXstar) | `192.168.100.1` | `192.168.1.1` / `192.168.3.1` | N/A | `80` |
| **Linksys** | `192.168.1.1` | `192.168.10.1` | `http://myrouter.local` | `80` |
| **Mercusys** | `192.168.1.1` | `192.168.0.1` | `http://mwlogin.net` | `80` |
| **MikroTik** (RouterOS) | `192.168.88.1` | MAC WinBox Only | N/A | `80` / `8291` |
| **MSI** (RadiX) | `192.168.18.1` | `192.168.1.1` | `http://msirouter.login` | `80` |
| **Netgear** (Nighthawk / Orbi) | `192.168.1.1` | `10.0.0.1` | `http://routerlogin.net` | `80` |
| **Netis** | `192.168.1.1` | `192.168.1.254` | `http://netis.cc` | `80` |
| **Nokia** (G-2425G-A / Fiber ONT) | `192.168.1.254` | `192.168.18.1` | N/A | `80` / `443` |
| **Synology** (SRM) | `192.168.1.1` | `192.168.2.1` | `http://router.synology.com` | `8000` / `8001` |
| **Tenda** | `192.168.0.1` | `192.168.1.1` | `http://tendawifi.com` | `80` |
| **TOTOLINK** | `192.168.0.1` | `192.168.1.1` | `http://itotolink.net` | `80` |
| **TP-Link** (Archer / Deco) | `192.168.0.1` | `192.168.1.1` / `192.168.68.1` | `http://tplinkwifi.net` | `80` |
| **Ubiquiti** (UniFi / EdgeOS) | `192.168.1.1` | `192.168.2.1` | `https://unifi.ui.com` | `443` |
| **ZTE** (ZXHN F670L / F660) | `192.168.1.1` | `192.168.2.1` | N/A | `80` |
| **Zyxel** | `192.168.1.1` | `192.168.1.254` | `http://myrouter` | `80` / `443` |

---

## 2. RFC 1918 Private IPv4 Ranges

All consumer and enterprise local router gateways operate inside the three IANA-reserved RFC 1918 private address blocks:

* **Class A (`10.0.0.0/8`):** `10.0.0.0` – `10.255.255.255` (Commonly used by ISP cable gateways like Xfinity/Arris and Netgear fallback subnets).
* **Class B (`172.16.0.0/12`):** `172.16.0.0` – `172.31.255.255` (Commonly used in corporate VLANs, Docker bridges, and guest captive portals).
* **Class C (`192.168.0.0/16`):** `192.168.0.0` – `192.168.255.255` (Standard default for 90%+ of residential routers).

---

## 3. Troubleshooting Gateway Connection Refused / Unreachable Errors

If your browser returns `ERR_CONNECTION_REFUSED`, `ERR_ADDRESS_UNREACHABLE`, or `ERR_CONNECTION_TIMED_OUT` when connecting to your default IP:

1. **Force Unencrypted HTTP:** Browsers with HTTPS-First Mode enabled will fail on routers lacking local SSL certificates. Explicitly request `http://192.168.1.1`.
2. **Disable Overlay Networks:** Active VPN tunnels (WireGuard, OpenVPN, NordVPN) or Apple iCloud Private Relay route RFC 1918 requests outside the local LAN interface.
3. **Check for Subnet Collisions & IPv6 Link-Local Lockouts:** If your upstream modem and downstream Wi-Fi router share the same subnet, or if your network adapter only resolves an `fe80::` IPv6 gateway, refer to the **[RouterIPGuide Troubleshooting & Subnet Diagnostic Guide](https://routeripguide.com/troubleshooting)** for step-by-step recovery commands.
