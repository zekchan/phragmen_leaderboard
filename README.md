# Phragmen Leaderboard

Nodejs implementation of Phragmén Method for Substrate-base Networks (without edges reduce optimisations). 

Check wiki about method [here](https://wiki.polkadot.network/docs/en/learn-phragmen)

## Install
`npm i phragmen-substrate`

## Use
```
const { ApiPromise, WsProvider } = require('@polkadot/api')
const phragmen = require('phragmen-substrate')

const provider = new WsProvider('wss://cc1-1.polkadot.network');
ApiPromise.create({ provider }).then(api => {
    phragmen.getLeaderboard(20, api).then(result => {
        console.log(JSON.stringify(result))
    })
})
```


## Examples

The example applications runs a simple web server on port 3000, on which you can get the top 20 winners of the election. 
Also create winners json files in results folder.

### To run example
`npm install`

`node ./examples/polkadot/main.js`

or

`node ./examples/kusama/main.js`

### To change network
You can set ws uri in env parameters

`export NODE_WS=ws://127.0.0.1:9944/`

### To change port
You can also set web server port in env parameters

`export SERVER_PORT=3000`

