# WIPRO - Non-Fungible Token (NFT)

## Intro

This repository contains a NFT Prototype as part of our project at HSLU. It provides an ERC-721 compatible smart contract and four example flows for Node-RED. 

## Installation & Configuration

### Installation

1. Install [Node.js](https://nodejs.org/en/download/package-manager)
1. Install [Node-RED](https://nodered.org/docs/getting-started/local#installing-with-npm) using `sudo npm install -g --unsafe-perm node-red`
1. Manual installation of "node-red-contrib-ethereum" (see separate [repository](https://github.com/timweing/node-red-contrib-ethereum))
	* Only follow the chapter "Installation"
	* Additionally, run `npm install` inside the main folder of the repository
1. Install [Truffle](http://trufflesuite.com/truffle/) using `npm install truffle -g`
1. Download [Ganache](http://trufflesuite.com/ganache/)
1. Download this github repository. In the terminal, go to main directory with package.json inside and run `npm install`
1. Reboot the machine.

### Configuration

#### 1. Setup ganache workspace

1. Start ganache and open a new workplace and give it a meaningful name
1. Click on "Add Project" and choose the file "truffle-config.js" inside the directory "Smart Contract"
1. Switch to the tab "Accounts & Keys"
1. Use the following mnemonic:
	```
	siren suit gift pill insect build expand decade valid roof blind museum
	```
1. Start Workspace by clicking on "Save Workspace"

#### 2. Deploy smart contracts

1. Open a terminal and go to the "Smart Contract" directory
1. Run the following commands:
	```
	truffle compile
	truffle migrate
	``` 
1. The deployed contracts should be visible in ganache in the "Contracts" tab.

## Flows

1. Make sure ganache is started and smart contracts are deployed
1. Start Node-RED using the command ```node-red```
1. Install Node Palette "node-red-contrib-credentials" in Node-RED
1. Import [Flows.json](Node-RED%20Flows/Flows.json) in Node-RED
1. Make sure to update the smart contract addresses in the configuration nodes ("Module" and "Test Token"). You can find these addresses in the "Contracts" Tab in Ganache.
1. Generate API Keys on Pinata Cloud
	* Create Account on [Pinata Cloud](https://app.pinata.cloud/)
	* Create API Keys with API Endpoint Access to "pinFileToIPFS" and "pinJSONToIPFS"
1. Update API Keys in Node-RED
	* Go to Flow "NFT Mint Process" and / or "NFT Use Case"
	* Open Credentials Node and update both variables accordingly
	* Deploy and test authentication using the according inject node
1. Update path in flow "NFT Use Case"
	* Find function node "Update absolute path to folder here"
	* Update the already existing variable "path"
	* Deploy and test using the according inject node
1. Start using the flows as you wish
