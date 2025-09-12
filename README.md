# Hello Lab

a) Can’t fish (disable network test)

I tested Internet with:

ping 1.1.1.1
ping 8.8.8.8

- When Internet is ON - the command replies, meaning connection works.

- When I disable the network - ping shows “no reply / timeout”.

- This proves packets don’t go out.

- Pressed Ctrl + C to stop the ping.

- Conclusion: Turning off the network makes the lab safe from accidentally scanning outside.

b) Local only (port scan localhost)

Installed tool with:

sudo apt-get install nmap


Scanned my own machine:

sudo nmap -A localhost

- Without daemons, Debian had almost no open ports (safe by default).

- Conclusion: Fresh Linux system does not expose services to the network.

c) Daemon scan (with Apache running)

Installed Apache:

sudo apt-get install apache2
sudo systemctl start apache2

- Scanned again with nmap.

- This time port 80/tcp was open - Apache web server running.

- Difference: Before no open ports, after running Apache the scan shows the service.

- Conclusion: Starting a server program (daemon) opens a door to the system.

d) Bandit game (levels 0–4)

- Level 0 - 1: Logged in with SSH. Password stored in a file.

- Level 1 - 2: File named -, needed cat ./- to open.

- Level 2 - 3: Hidden file, used ls -a.

- Level 3 - 4: File with spaces, needed quotes cat "spaces in this filename".

- Level 4 - 5: In “inhere” folder, found correct file by checking which one was human-readable.

Conclusion: These levels teach you how to deal with tricky filenames, hidden files, and how to find information in Linux.

## Sources

Karvinen, Tero (2021). Install Debian on VirtualBox – Updated 2024

Karvinen, Tero (2020). Command Line Basics Revisited

OverTheWire: Bandit game

UndertheWire: Century game
