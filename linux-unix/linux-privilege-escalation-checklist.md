---
description: Checklist for privilege escalation in Linux
---

# Checklist - Linux Privilege Escalation

## **Best tool to look for Linux local privilege escalation vectors:** [**LinPEAS**](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS)\*\*\*\*

## [Vulnerable Kernel?](privilege-escalation/#kernel-exploits)

* [ ] Search for kernel **exploits using scripts** \(linux.exploit-suggester.sh, inux-exploit-suggester2.pl, linuxprivcheckser.py\)
* [ ] Use **Google to search** for kernel **exploits**
* [ ] Use **searchsploit to search** for kernel **exploits**
* [ ] **Check** if the [**sudo version** is vulnerable](privilege-escalation/#sudo-version)

## [Vulnerable Processes?](privilege-escalation/#processes)

* [ ] Is  any **unknown software running**?
* [ ] Is any software with **more privileges that it should have running**?
* [ ] Search for **exploits for running processes** \(specially if running of versions\)
* [ ] Can you **read** some interesting **process memory** \(where passwords could be saved\)?

## [Known users/passwords?](privilege-escalation/#users)

* [ ] Try to **use** every **known password** that you have discovered previously to login **with each** possible **user**. Try to login also without password.

## [Interesting Groups?](privilege-escalation/#groups)

* [ ] Check **if** you [**belong** to any **group** that can grant you **root rights**](privilege-escalation/interesting-groups-linux-pe.md).

## [Weird scheduled jobs?](privilege-escalation/#scheduled-jobs)

* [ ] Is the **PATH** being modified by some cron and you can **write** in it?
* [ ] Some **modifiable script** is being **executed** or is inside **modifiable folder**?
* [ ] Is some cron **script calling other** script that is **modifiable** by you? or using **wildcards**?
* [ ] Have you detected that some **script** could be being **executed** very **frequently**? \(every 1, 2 or 5 minutes\)

## [Any sudo command?](privilege-escalation/#commands-with-sudo-and-suid-commands)

* [ ] Can you execute **any comand with sudo**? Can you use it to READ, WRITE or EXECUTE anything as root?
* [ ] Is some **wildcard used**?
* [ ] Is the binary specified **without path**?
* [ ] Is _**env\_keep+=LD\_PRELOAD**_?

## [Any weird suid command?](privilege-escalation/#commands-with-sudo-and-suid-commands)

* [ ] **SUID** any **interesting command**? Can you use it to READ, WRITE or EXECUTE anything as root?
* [ ] Is some **wildcard used**?
* [ ] Is the SUID binary **executing some other binary without specifying the path**? or specifying it?
* [ ] Is it trying to **load .so from writable folders**?

## [Weird capabilities?](privilege-escalation/#capabilities)

* [ ] Has any binary any **uncommon capability**?

## [Open Shell sessions?](privilege-escalation/#open-shell-sessions)

* [ ] screen?
* [ ] tmux?

## [Can you read some sensitive data?](privilege-escalation/#read-sensitive-data)

* [ ] Can you **read** some **interesting files**? \(files with passwords, \*\_history, backups...\)

## [Can you write important files?](privilege-escalation/#writable-files)

* [ ] Are you able to **write files that could grant you more privileges**? \(service conf files, shadow,a script that is executed by other users, libraries...\)

## [Internal open ports?](privilege-escalation/#internal-open-ports)

* [ ] You should check if any undiscovered service is running in some port/interface. Maybe it is running with more privileges that it should or it is vulnerable to some kind of privilege escalation vulnerability.

## [Can you sniff some passwords in the network?](privilege-escalation/#sniffing)

* [ ] Can you **sniff** and get **passwords** from the **network**?

## [Any service missconfigurated? NFS? belongs to docker or lxd?](privilege-escalation/#privesc-exploiting-service-misconfigurations)

1. [ ] Any well known missconfiguration? \([**NFS no\_root\_squash**](privilege-escalation/nfs-no_root_squash-misconfiguration-pe.md)\)

## [Any weird executable in path?](privilege-escalation/#check-for-weird-executables)

If you want to **know** about my **latest modifications**/**additions or you have any suggestion for HackTricks or PEASS**, **join the** [**PEASS & HackTricks telegram group here**](https://t.me/peass)**.**

![](../.gitbook/assets/68747470733a2f2f7777772e6275796d6561636f666665652e636f6d2f6173736574732f696d672f637573746f6d5f696d616765732f6f72616e67655f696d672e706e67%20%284%29.png)

​[**Buy me a coffee here**](https://www.buymeacoffee.com/carlospolop)\*\*\*\*

