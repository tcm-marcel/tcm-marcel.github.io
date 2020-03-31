---
layout: default
title: "NAS Internals"
permalink: /nas/
---

## NAS Internals

This is about my NAS that I built and set up. 

### Requirements

1. Keep my important data safe from 
    1. me (accidental deletes, scripts that run crazy)
    1. disk failures
    1. other people (crypto stuff)
1. Allow to roll back on older versions of specific data
1. Automatically retrieve and backup data from other places
    1. Email
    1. Bank statements
    1. Calendar/Contacts
1. Store other data, for which I don't have enough space on my laptop
    1. Fast data delivery over network
1. Run other small services without sacrifying data security and other of the above points
    1. for example: Web picture viewer

Remote access is explicitly not a requirement and should be avoided

### Hardware

* _Mainboard:_ [Asrock J5005-ITX](https://www.asrock.com/mb/Intel/J5005-ITX/index.de.asp)
    * Intel Quad-Core Pentium J5005, 2.8 Ghz)
    * 4 SATA3
    * 4 USB 3.1 Gen1
* _Memory:_ 2x 8GB DDR4 SO-DIMM RAM
* _Drives:_
    * Two mirrored USB sticks with the OS, directly on the Mainboard USB3.0 pin header
        * Sandisk Ultra Fit USB 3.1 64GB
    * One cheap SSD for system dataset and runtime data, allows the data drives to go into standby
        * Samsung 128GB SSD PM871 M.2 SATA, connected using M.2 USB3.0 adapter
    * Two mirrored SATA3 data drives, different models to avoid contemporaneous failure
        * Seagate IronWolf 4TB (ST4000VN008)
        * Seagate BarraCuda Compute 4TB (ST4000DM004)

### Software

* Operating System: [FreeNAS](https://www.freenas.org/) (BSD)
  * Based on secure [FreeBSD](https://www.freebsd.org)
  * [ZFS](https://www.freenas.org/zfs/) on board by default (compared to Debian/Ubuntu)
  * Great UI (almost no terminal interaction necessary)
  * Jails allow great isolation of services without sacrifying data security
