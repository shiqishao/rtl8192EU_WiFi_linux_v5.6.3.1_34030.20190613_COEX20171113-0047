Support Linux kernel version
kernel 2.6.18 ~ 4.17

CPU support
x86/x64

Ubuntu 18.04.2 LTS

Update apt and install gcc/make
1. Update apt
>sudo apt update
2. Install gcc
>sudo apt install gcc
3. Install make
>sudo apt install make 

Check inbox driver:
1. Plug-in adapter and check does adpater work(ex.using network manager to connect, LED blink)
2. If adapter workable, do Block inbox driver, if not, do Install and active module.

Block inbox driver:
1. Find inbox driver name:(usually contain "rtl")
>lsmod | grep "rtl"
ex. > rtl8xxxu <= inbox driver name
2. Block inbox driver when kernel up
>sudo vi /etc/modprobe.d/blacklist.conf
append blacklist inbox driver name in the end of blacklist.conf
ex. blacklist rtl8xxxu
3. Reboot computer
>reboot
4. do Install and active module.

Install and active module:
1. Unzip and change directory
>tar zxvf rtl8192EU_WiFi_linux_v5.6.3.1_34030.20190613_COEX20171113-0047.tar.gz
>cd rtl8192EU_WiFi_linux_v5.6.3.1_34030.20190613_COEX20171113-0047
2. Compile module
>make 
3. Install module
>sudo make install

Uninstall module:
1. Change directory
>cd rtl8192EU_WiFi_linux_v5.6.3.1_34030.20190613_COEX20171113-0047
2. Uninstall module
>sudo make uninstall
3. Clean object code
>make clean

Update kernel notice:
If update kernel, please remove driver and check inbox driver again, detail please follow "Uninstall module" and then "Check inbox driver" again.