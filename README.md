# Managing your Blockchain Identity

``` javascript
var bitcoin = require('bitcoinjs-lib') 
var bitcoinMessage = require('bitcoinjs-message')
```

> sign(message, privateKey, compressed[, network.messagePrefix])

Sign a Bitcoin message
``` javascript
var keyPair = bitcoin.ECPair.fromWIF('L1rVQKRCDyRfZfNwL2rwitnsvNnbEHiSMUPtLEwSC6xhQnEGsZ7x')
var privateKey = keyPair.privateKey
var message = '14iiMkyUM7yskFhkFFaG8C8FW5jpuJQyCi: Udacity rocks!'

var signature = bitcoinMessage.sign(message, privateKey, keyPair.compressed)
console.log(signature.toString('base64'))
// => 'H2YfJfEyulJ249P+N+PXLw1x9ax5kr9SezM0KK3HZ33GAyPAEj3ehSMxHXWMpR7y0gpEmaL1fzjzjM0+gC6gMDE='
```

> verify(message, address, signature[, network.messagePrefix])

Verify a Bitcoin message
``` javascript
var address = '14iiMkyUM7yskFhkFFaG8C8FW5jpuJQyCi'

console.log(bitcoinMessage.verify(message, address, signature))
// => true
```

## LICENSE [MIT](LICENSE)
