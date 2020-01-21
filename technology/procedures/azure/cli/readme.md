TITLE: Configuring Ubuntu WSL (Windows Subsystem for Linux) on Windows 10 Devices
AUTHOR: Sameet Singh (sameet.singh@stratumtechnology.com)
DATE: 01/21/2020

Have any of you struggled with installing or upgrading the Azure CLI on Ubuntu WSL (Windows Subsystem for Linux)? If so, try the following one liner command that Microsoft updated October of last year. Reference: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt

Note: Be patient when it gets to the 'unpacking azure-cli' step as it takes about 15 minutes to complete depending on your system resources and available memory.

New Installations:
$ curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash

Updating the CLI:
$ sudo apt-get update && sudo apt-get install --only-upgrade -y azure-cli

Repairing Older/Broken Installations in Ubuntu WSL (>= 16.04):
$ sudo apt-get remove -y azure-cli
$ sudo rm /etc/apt/sources.list.d/azure-cli.list
$ sudo rm /etc/apt/trusted.gpg.d/microsoft.asc.gpg
$ sudo apt autoremove
$ sudo apt-get update && sudo apt-get upgrade
$ curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash

If you don't have Ubuntu WSL (Windows Subsystem for Linux) configured on your device, please see the following procedure to get started:
https://docs.microsoft.com/en-us/windows/wsl/install-win10
