#!/bin/bash
#
# name          : lan_device_reset
# desciption    : reset LAN device when windows blocks/hibernate the device 
# autor         : Speefak ( itoss@gmx.de )
# licence       : (CC) BY-NC-SA
# version	: 0.1
#

#Get the PCI-Address of network card (Caution: This works ONLY with ONE NIC)
PCI=`/usr/bin/lspci | /bin/egrep -i 'network|ethernet' | /usr/bin/cut -d' ' -f1`
PCIPATH=`/usr/bin/find /sys -name *\${PCI} | /bin/egrep -i *pci0000*`

/usr/bin/logger -t "ResetNIC" "Resetting PCI NIC ${PCIPATH}"

#Reset the PCI Device completely (like Power-ON/Off)
echo 1 >${PCIPATH}/reset
