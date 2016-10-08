# A2osX
Multi-Tasking OS for Apple II
## Requires :
Enhanced IIe (65c02 cpu) with 128k, //c, IIgs

## General Information:  
  
Kernel 0.8 is out.
It is confined in Aux LC Bank 1 & 2 to leave enough room at $EOOO for Drivers.
Network drivers, Mouse, DHGR.DRV can load and fit in Aux LC.  
Now it's time to make all external BINs use new API, then GUI development will resume.
  
**A2OSX.BOOT.po** : 140k A2osX boot disk with all binaries  
**A2OSX.DEV.po**  : 140k A2osX disk with ASM binaries, Debug Tools & INClude files  
**A2OSX.SRC.po**  : 800k S-C MASM boot disk with all sources  
  
OApple+1,OApple+2,OApple+3 to switch between screens : Kernel Log, text, DHGR.  
(OApple+shift+1,OApple+shift+2,OApple+shift+3 on FR keyboard)  
  
### **** Developers WANTED ****  

!!! Help on writing this code should be greatly appreciated !!!  

...
In Progress : Document API...
In Progress : moving TCPIP to socket API
...

## SYS/KM* Supported Hardware At Kernel Level (ProDOS):
| KM.Name | Status | Comment |
| ------- | ------ | ------- |
| KM.NSC | Working | No-Slot-Clock |
| KM.RAMWORKS | Working | AE-Ramworks I,II,III |
  
## SBIN,Daemons/Commands:  
| Name | Status | Comment | K.Ver |
| ---- | ------ | ------- | ----- |
| INSDRV | Working | | 0.8 |
| GETTY | Working | | 0.8 |
| LOGIN | In Progress | no auth using /etc/passd yet | 0.8 |
| TCPIP | In Progress | New Socket API. ARP,IP,ICMP,UDP ok, TCP in progress | 0.8 |
| DHCPCLNT | Working | rewritten to use new Socket API | 0.8 |
| SHELL | Working | (See Internal Shell commands) | 0.8 |
  
## DRV,Drivers:  
| Name | Status | Comment | K.Ver |
| ---- | ------ | ------- | ----- |
| Console.DRV | Working | ANSI support in Progress. | 0.8 |
| PIC.DRV | In Progress | Apple "Parallel Interface Card" Driver, renamed from PPIC.DRV|
| SSC.DRV | In Progress | |
| SSC.I.DRV | In Progress | |
| Mouse.DRV | Working | | 0.8 |
| Uthernet.DRV | Working | | 0.8 |
| Uthernet2.DRV | Working | |
| Uther2.AI.DRV | In Progress | With ARP/IP Offloading |
| LanCeGS.DRV | Working | |
| DHGR.DRV | In Progress | except bitblt... | 0.8 |
  
## Internal Shell commands:  
| Name | Status | Comment |
| ---- | ------ | ------- |
| CD | Working | |
| DATE | Working  | |
| ECHO | Working | |
| EXIT | Working  | |
| IF | | |
| PAUSE | Working | |
| READ | | |
| TIME | Working | |
| TYPE | Working | |
| SET | Working  | |
| STARTPROC | Working  | Used in A2osX.startup |
  
## BIN,External Shell commands:  
| Name | Status | Comment | K.Ver |
| ---- | ------ | ------- | ----- |
| MEM | Working | Old dump behavior is now MEMDUMP.  New MEM command displays MEMSTAT (Main, Aux & Kernel Memory) | 0.8 |
| LSDEV | Working | | 0.8 |
| PS | Working | | 0.8 |
| MD | Working | | |
| RM | Working | switches not yet implemented | |
| LS | Working  | BUG: `ls dir` does not list dir content (`ls dir/` works) | |
| CP | Working| switches not yet implemented | |
| ARP | Working | dump ARP cache, setup a static ARP entry | 0.8 |
| PING | Working | | |
| DNSINFO | Working | dump DNS cache, setup a static DNS entry | |
| IPCONFIG | Working | renamed from NETINFO | 0.8 |
| NETSTAT | Working | | 0.8 |
| EDIT | Working | still missing : find/replace | |
| NSCUTIL | Working | Tool for setting time in NSC/DL1216E | |
  
## BIN,External DEV Shell commands:  
| Name | Status | Comment | K.Ver |
| ---- | ------ | ------- | ----- |
| ASM | In Progress | S-C MASM based multi CPU assembler | |
| DEVDUMP |  | | |
| MEMDUMP | Working | | 0.8 |
| RPCDUMP | Working | tool based on UDP socket API, renamed from RPCINFO | |
  
## Misc  
### S-C MASM color scheme for Notepad++  
...drop _Tools/userDefineLang.xml in %APPDATA%\Notepad++  
;-)

