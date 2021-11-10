# Indian Crypto Geeks Voting DApp
This is the code of our project


## Overview

This is a simple voting web dapp which performs as a voting machine for few persons.

## Dependencies

* ethereumjs-testrpc 
* web3@0.20.1
* solc

Install missing dependencies with [npm](https://www.npmjs.com/). 

```
> git clone https://github.com/soumwadeep/Indian-Crypto-Geeks.git
> cd Indian Crypto Geeks
> npm install 
```

## Usage

After all dependancies are installed, run the `testrpc` service with:
```
node_modules/ethereumjs-testrpc/build/cli.node.js
```

Run the following commands to open the node console then deploy your contract to the test chain

```
soumwadeep:~/indian_crypto_geeks$ node
> Web3 = require('web3')
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)
> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)
> VotingContract = web3.eth.contract(abiDefinition)
> byteCode = compiledCode.contracts[':Voting'].bytecode
> deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
> deployedContract.address
> contractInstance = VotingContract.at(deployedContract.address)
```

Interact with the contract via the html page attached, just open it in your browser.

## Credits

The credits for this code goes to the owners of this repo:Soumwadeep And Shreshtha.