# ETH Token Recover

[![NPM Package](https://img.shields.io/npm/v/eth-token-recover.svg?style=flat-square)](https://www.npmjs.org/package/eth-token-recover)
[![Build Status](https://travis-ci.org/vittominacori/eth-token-recover.svg?branch=master)](https://travis-ci.org/vittominacori/eth-token-recover)
[![Coverage Status](https://coveralls.io/repos/github/vittominacori/eth-token-recover/badge.svg?branch=master)](https://coveralls.io/github/vittominacori/eth-token-recover?branch=master) 

TokenRecover allows the contract owner to recover any ERC20 token sent into the contract for error.

## Motivation

There are lots of tokens lost forever into Smart Contracts (see [OMG](https://etherscan.io/address/0xd26114cd6ee289accf82350c8d8487fedb8a0c07) token balances).   
Each Ethereum contract is a potential token trap for ERC20 tokens. They can't be recovered so it means money losses for end users.

## Code

This repo contains:

* [TokenRecover.sol](https://github.com/vittominacori/eth-token-recover/blob/master/contracts/TokenRecover.sol)

Contract has a `recoverERC20` function that transfers a `_tokens` amount of `_tokenAddress` token to the contract owner.

```solidity
function recoverERC20(address _tokenAddress,  uint256 _tokens) public onlyOwner returns (bool success);
```

Note: only owner can call the `recoverERC20` function so be careful when use on contracts generated from other contracts.

## Install

```bash
npm install eth-token-recover
```


## Usage

```solidity
pragma solidity ^0.4.24;

import "eth-token-recover/contracts/TokenRecover.sol";


contract MyContract is TokenRecover {
  // your stuffs
}
```

## Development

Install Truffle

```bash
npm install -g truffle      // Version 4.1.14+ required.
```

### Install dependencies

```bash
npm install
```

### Linter

Use Solium

```bash
npm run lint:sol
```

Use ESLint

```bash
npm run lint:js
```

Use both and fix

```bash
npm run lint:fix
```

### Compile and test the contracts
 
Open the Truffle console

```bash
truffle develop
```

Compile 

```bash
compile 
```

Test

```bash
test
```

### License

Code released under the [MIT License](https://github.com/vittominacori/eth-token-recover/blob/master/LICENSE).