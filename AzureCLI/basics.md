To log in to your Azure account, use the following commands:

```
# Log in to Azure
az login
```
```
# Specify tenant ID (if necessary)
az login --tenant TENANT_ID
```

#### Create a Resource Group
```
az group create --name $MY_RESOURCE_GROUP_NAME --location $REGION
```

#### Create a VN.
The following example creates a VM and adds a user account. The --generate-ssh-keys parameter causes the CLI to look for an available ssh key in ~/.ssh. If one is found, that key is used. If not, one is generated and stored in ~/.ssh. The --public-ip-sku Standard parameter ensures that the machine is accessible via a public IP address
```
az vm create --resource-group $MY_RESOURCE_GROUP_NAME --name $MY_VM_NAME --image $MY_VM_IMAGE --admin-username $MY_USERNAME --assign-identity --generate-ssh-keys --public-ip-sku Standard
```

#### To retrive VM IP address
```
az vm show --show-details --resource-group $MY_RESOURCE_GROUP_NAME --name $MY_VM_NAME --query publicIps --output tsv
```

#### To delete a Resource Group
```
az group delete --name <exampleGroup>
```