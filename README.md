### Hetzner-how-to

Hetzner how to...

## [fix-jmicron-sata-controller-issues.md] (https://github.com/viosioner-ua/Hetzner-how-to/blob/main/fix-jmicron-sata-controller-issues.md)

Hetzner offers the SX server series, which are equipped with 4 to 14 hard drives, each with a capacity of 16 or 22 TB. The SX135 server comes with 8 drives, making it a good choice for backup storage. Unfortunately, after ordering this server and installing Proxmox Backup Server 4.2, I was only able to use 4 drives that were connected directly to the motherboard. The other 4 drives, connected to JMicron SATA controllers, returned errors even when tested using “hdparm”. Since Hetzner support replaced the controller and cables, hardware errors were ruled out. When testing the disks in the rescue system, all disks operated stably and without errors. Therefore, a comparison of the disk subsystem parameters between the Proxmox kernel and Debian (rescue system) was performed, and discrepancies were identified. The symptoms of the problem and how to resolve it are described step-by-step below.

---
