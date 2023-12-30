# Checkpoint Cloudguard on Azure vpn-officemode

Advertising checkpoint VPN address pool to peered VNETs and ER

When you deploy checkpoint CloudGuard as a point to site VPN provider on Azure hybrid hub&spoke network your environment may require to not do NAT on the Address Pool destinated to the VPN Office Mode clients.

You will have many alternatives to propagate this VPN network to others VNETs and Onprem networks. In this scenario I had the requiremnt to not use vWAN or Route Server. Tough the alternative was to manipulate the natural behavior of Azure routing.

1 - Added the VPN address Pool to the VNET where the CheckPoint Gateway was deployed, but no subnets was creates using this addess space.
With that the address pool is advertised via BGP for the peered vnets and consequently to the ExpressRoute circuit.
2 - Created a UDR directing the retunig traffic direct to the CheckPoint gateway beckend IP Address. On this scenario the UDR was applyed on the HUB VNET.

   
![AMS_Network_public_v0](https://github.com/rbegito/checkpoint-azure-vpn-officemode/assets/25324391/a2c43d73-f8ee-437f-928b-40c74dbabaa3)

SOON I will update with the scrips...
