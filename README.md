# NFT_Whitelist_Hardhat
Build an NFT collection with a whitelist using Hardhat and Solidity



## Technology Stack

- **Hardhat:** Development environment for Ethereum smart contracts.
- **Solidity:** Programming language for writing smart contracts.
- **OpenZeppelin Contracts:** Library for secure smart contract development.
- **Node.js and npm:** JavaScript runtime and package manager.
- **MetaMask:** Ethereum wallet and browser extension.
- **QuickNode:** Ethereum node provider for development.
- **Etherscan:** Ethereum blockchain explorer and verification tool.



# Crypto Devs NFT Collection - Whitelist DApp and Minting

## Overview

This project demonstrates the creation of an NFT collection named **Crypto Devs** with a whitelist feature using Hardhat and Solidity. The goal is to allow early supporters, who join the whitelist, to have guaranteed access to mint NFTs for free. The project consists of two smart contracts - one for the whitelist and another for the NFT collection.

## Prerequisites

Before starting, ensure that you have the following set up:

1. **Development Wallet:** Create a new wallet for development with no mainnet funds.
2. **Node.js and npm:** Install Node.js and npm on your machine.
3. **MetaMask:** Export a private key from MetaMask for deployment (with no real funds).

## Setup

1. **Initialize Hardhat Project:**
    ```bash
    mkdir whitelist-dapp
    cd whitelist-dapp
    mkdir hardhat
    npm init --yes
    npm install --save-dev hardhat @nomicfoundation/hardhat-toolbox
    npx hardhat
    ```

2. **Create Whitelist Contract:**
    - Create `Whitelist.sol` in `hardhat/contracts` and copy the provided Solidity code.

3. **Write Deployment Script:**
    - Create `deploy.js` in `hardhat/scripts` and copy the provided deployment script.

4. **Environment Variables:**
    - Create a `.env` file in the `hardhat` directory with the following variables:
        ```
        PRIVATE_KEY="YourPrivateKeyHere"
        RPC_URL="YourQuickNodeRpcUrlHere"
        ETHERSCAN_API_KEY="YourEtherscanApiKeyHere"
        ```

5. **Install dotenv:**
    ```bash
    npm install dotenv
    ```

6. **Configure Hardhat:**
    - Update `hardhat.config.js` with network configurations and etherscan API key.

7. **Deploy Whitelist Contract:**
    ```bash
    npx hardhat run scripts/deploy.js --network sepolia
    ```

## Interact with Whitelist

1. **Add Users to Whitelist:**
    - Go to Sepolia Etherscan, find the deployed Whitelist contract, and use the Etherscan interface to call `addAddressToWhitelist` and whitelist addresses.

## Write the NFT Contract

1. **Install OpenZeppelin Contracts:**
    ```bash
    npm install @openzeppelin/contracts
    ```

2. **Create NFT Contract:**
    - Create `CryptoDevs.sol` in `hardhat/contracts` and copy the provided Solidity code.

3. **Write NFT Deployment Script:**
    - Create `deploy-nft.js` in `hardhat/scripts` and copy the provided deployment script.

4. **Deploy NFT Contract:**
    ```bash
    npx hardhat run scripts/deploy-nft.js --network sepolia
    ```

## Test Minting

1. **Whitelisted Mint:**
    - Connect to the NFT contract on Etherscan, go to Write Contract, and call `mint` with payableAmount set to 0. Confirm the transaction.

2. **Non-Whitelisted Mint:**
    - Switch to a different wallet, connect to the NFT contract, and attempt to call `mint` without paying. The transaction should fail.
    - Retry with payableAmount set to 0.01 ETH to simulate a paid mint.

## Conclusion

Congratulations! You've successfully created a whitelist dApp and an NFT collection. Early supporters on the whitelist can now mint NFTs for free, while others need to pay. Experiment with different scenarios and transactions to understand the functionality better.
