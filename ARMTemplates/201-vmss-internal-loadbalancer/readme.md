
# Deployment of a VM Scale Set of Linux VMs behind an load balancer with NAT rules

**NOTE:** This template is a  *modified* copy of the Microsoft [201-vmss-internal-loadbalancer](https://github.com/Azure/azure-quickstart-templates/tree/master/201-vmss-internal-loadbalancer) Azure Quick Start template and is provided here only to support labs on the LODS platform. 




[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLODSContent%2FChallengeLabs_ArmResources%2Fmaster%2FARMTemplates%2F201-vmss-internal-loadbalancer%2Fazuredeploy.json)  [![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https://raw.githubusercontent.com/LODSContent/ChallengeLabs_ArmResources/master/ARMTemplates/201-vmss-internal-loadbalancer/azuredeploy.json)

This template allows you to deploy a VM Scale Set of Linux VMs using the latest patched version of Ubuntu Linux 15.10 or 14.04.4-LTS. These VMs are behind an load balancer with NAT rules. Because the load balancer is internal, you must first ssh into the jumpbox, then ssh from there into a specific VM behind the load balancer. To connect from the load balancer to a VM in the scale set, you would go to the Azure Portal, find the load balancer of your scale set, examine the NAT rules, then connect using the NAT rule you want. For example, if there is a NAT rule on port 50000, you could use the following command from the jumpbox:

ssh -p 50000 {username}@{public-ip-address}

PARAMETER RESTRICTIONS
======================

vmssName must be 3-61 characters in length. It should also be globally unique across all of Azure.
instanceCount must be **4** or less.

