Dometrain URL Shortner Course

## Infrastructure as code
## Download Azure CLI
### Log into Azure
'''bash
az login or az login --use-device-code
'''
### Create Resource Group
'''bash
az group create --name urlshortner --location westeurope
'''

az deployment group what-if --resource-group urlshortner --template-file infrastructure/main.bicep
az deployment group create --resource-group urlshortner --template-file infrastructure/main.bicep

### Create User for Github Actions
az ad sp create-for-rbac --name "Github-Actions-SP" \
                     --role contributor \
                     --scopes /subscriptions/bedb94a0-a729-4b12-a54e-4bf46fd730d4