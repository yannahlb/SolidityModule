# Project: Create a Token
This solidity program is a basic implementation of a token system that demonstrates the process of minting and burning of tokens, as well as how to maintain a balance of tokens for different addresses. The purpose of this program is to act as a simple introduction for managing token supply on the Ethereum blockchain.


## Description

This program is designed for individuals who are new to Solidity and smart contract development. It serves as a foundational introduction to key concepts in token management and demonstrates how to create, store, and manipulate digital assets (tokens) on the Ethereum blockchain. The MyToken contract can be used as a stepping stone for more complex token-based systems in the future, such as decentralized finance (DeFi) platforms, reward systems, or any other blockchain-based applications that require token management. Specifically, the MyToken contract in the program provides two core functionalities: mint and burn.
- The mint function increases the total supply of tokens and assigns them to a specific address.
- The burn function reduces the total supply by removing tokens from a specific address, ensuring the address has enough tokens before the operation.

## Getting Started

### Executing the Program
To run the program, you can use an online Solidity IDE called Remix (https://remix.ethereum.org/) and follow the steps below: 

Go to the Remix website and create a new file by clicking on the "+" icon in the left-hand sidebar. Name the file myToken.sol.

Copy and paste the following code into your new file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables to store token details
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint256 public totalSupply;

    // Mapping to store balances of addresses
    mapping(address => uint256) public balances;

    // Mint function to increase total supply and balance of the given address
    function mint(address _address, uint256 _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to decrease total supply and balance of the given address
    function burn(address _address, uint256 _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
Click on the "Solidity Compiler" tab in the left-hand sidebar. Ensure the "Compiler" version is set to 0.8.18 (or another compatible version). Then click the "Compile MyToken.sol" button.

After successfully compiling, navigate to the "Deploy & Run Transactions" tab. Select the MyToken contract from the dropdown menu, and click the "Deploy" button.

You can interact with the contract by using the mint function to add tokens to an address. Use the burn function to remove tokens from an address, ensuring the address has enough tokens to burn. You can also check balances of any address by using the balances mapping.

## Authors

Reannah Lobaton

@yannahlb
