Create VM using Azure CLI

The Nautilus DevOps team is in the process of migrating some of their workloads to Azure. One of the tasks involves creating a new Virtual Machine (VM) using the Azure CLI. The team does not have access to the Azure portal but can manage Azure resources via the azure-client host (the landing host for this lab).

1) Create a new Azure Virtual Machine named `xfusion-vm` using the Azure CLI.

2) Use the `Ubuntu2204` image and set the VM size to `Standard_B2s`.

3) Make sure the admin username is set to `azureuser` and SSH keys are generated for secure access.

4) Use `Standard_LRS` storage account, disk size must be `30GB` and ensure the VM `devops-vm` is in the running state after creation.


Step 1 — Check existing Resource Groups

```
az group list -o table
```

<img width="637" height="138" alt="image" src="https://github.com/user-attachments/assets/6ce7099a-27a0-4fbe-8bda-2033420704d9" />


Step 2 — Create the Virtual Machine

```
az vm create \
  --resource-group kml_rg_main-353830eb53b14b36 \
  --name xfusion-vm \
  --image Ubuntu2204 \
  --size Standard_B2s \
  --admin-username azureuser \
  --os-disk-size-gb 30 \
  --storage-sku Standard_LRS \
  --generate-ssh-keys
```

<img width="1005" height="580" alt="image" src="https://github.com/user-attachments/assets/79707911-ce3a-49e6-86a2-a49701f8434b" />



Check VM status



<img width="990" height="170" alt="image" src="https://github.com/user-attachments/assets/1a4dbd34-dd09-4b53-a866-1de664244665" />



Explanation of flags

<img width="603" height="771" alt="image" src="https://github.com/user-attachments/assets/8d39706c-2153-4208-ba97-194137481bb9" />

