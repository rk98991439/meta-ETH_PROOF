# MyToken
This Solidity program is a token contract that allows minting and burning of tokens. It serves as a basic example for understanding the functionality of token contracts using the Solidity programming language.

# Requirements
1.The contract will have public variables to store details about the token (Token Name, Token Abbreviation, Total Supply).

2.The contract will have a mapping of addresses to balances (address => uint256) to keep track of token balances.

3.There will be a mint function that takes two parameters: an address and a value. This function will increase the total supply by the given value and add the value to the balance of the sender's address.

4.The contract will include a burn function that works the opposite of the mint function. It will take an address and a value, deduct the value from the total supply, and subtract the value from the balance of the sender's address.

5.The burn function will include conditionals to ensure that the balance of the sender is greater than or equal to the amount to be burned.

# Getting Started
Prerequisites
To compile and interact with this contract, you need the following:
1.Solidity compiler (version 0.8.0)
2.Ethereum development environment (e.g., Remix, Truffle, Hardhat)

# Compilation
1.Copy the code from the code block below:

# Code

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken 
{

    // public variables here
    string public tokenName = "MUTH";
    string public tokenAbbrv = "muth";
    uint public totalSupply = 0;

    // mapping variable here

    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
     totalSupply += _value;
     balances [_address] += _value;
    }


    // burn function
    function burn (address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -=_value;
        balances[_address] -=_value;
    }
 }
}

```
2.Paste the code into your Solidity development environment.

# Deployment and Usage
Compile the contract using the Solidity compiler (version 0.8.18).
Deploy the compiled contract to an Ethereum network of your choice.
Interact with the contract using the following functions:
mint(address Address, uint256 value): Mints new tokens by increasing the total supply and adding the specified value to the balance of the specified address.
burn(address Address, uint256 value): Burns tokens by deducting the specified value from the total supply and subtracting it from the balance of the specified address. The function includes a conditional check to ensure that the balance of the sender is greater than or equal to the value being burned.

# Authors

Rohit Kumar
rk98991439@gmail.com

# License
This project is licensed under the MIT License. See the [LICENSE.md](https://license.md/) file. file for details.
