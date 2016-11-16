### Virtual-Machine (系統虛擬機架構分類)

##Process VM 虛擬程序:
只能模擬執行一個Process的行為，可能是為了支援舊 Architecture 上的 Application。 ex: Apple Rosetta
也可能是為了可以在多個平台上執行 ex: Java Virtual Machine
![Process VM](http://i.imgur.com/LjMoeLJ.jpg)

##System VM 虛擬系統:
擬的是一個完整的OS, 需要更複雜的處理。 ex: VMWare, Xen, KVM
![System VM](http://i.imgur.com/IM0OiSU.jpg)

System VM區分為**Hosted Architecture(寄居架構)**及及**Bare Metal Architecture(裸金屬架構)**

#Hosted Architecture

操作系统之上安装和運行虛擬化程序，依賴於主機操作系統對設備的支持和物理資源的管理。
簡單來說就是，將VMM 建立在一個本地OS上。

*優點:簡單、方便實現。
*缺點:安裝和運行應用程序依賴於主機操作系統對設備的支持，性能有耗損。
*例子:Vitual PC, Virtual Box, VMware Workstation 7, KVM, OpenNebula, OpenStack, and Proxmox Virtual Server。

![Hosted Architecture](http://i.imgur.com/ZZGb2ZU.png)

#Bare Metal Architecture
實體層的虛擬化，類似一個操作於虛擬合心上的操作系統。

直接在硬件上面安装虛擬化軟件VMM (或Hypervisor)，依賴**虛擬層內核**和**服務器控制台**進行管理。
在模擬層(負責虛擬機器的指令翻譯)和硬體之間不需要任何原型主機作業系統運行在硬體上的一種新虛擬技術;虛擬化變得更加地高效率 。


*優點:虛擬機不依賴於操作系統，可以支持多種操作系統，多種應用，更加靈活。
*缺點:虛擬層核心開發難度較大。
*例子:VMware ESX, Hyper‐V R2, Citrix XenServer, Xen, and KVM(後期)。

![Bare Metal Architecture](http://i.imgur.com/rx0dBNP.png)

備註:**VMM (Virtual Machine Monitor)監視 VM 的運作狀況**
