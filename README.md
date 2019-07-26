### bitcoin-net
---
https://github.com/mappum/bitcoin-net

```js
var params = require('webcoin-bitcoin').net

var PeerGroup = require('./').PeerGroup
var peers = new PeerGroup(params)

peers.on('peer', (peer) => {
  console.log('connected to peer', peer.socket.remoteAddress)
  
  peer.once('pong', () => console.log('received ping response'))
  peer.send('ping', {
    nonce: require('crypto').pseudoRandomBytes(8)
  })
  console.log('sent ping')
})

peers.connect()

peers.accept((err) => {
  if (err) return console.error(err)
  console.log('accepting incoming connections')
})
```

```
```

```
```


