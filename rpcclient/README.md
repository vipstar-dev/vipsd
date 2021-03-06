rpcclient
=========

[![Build Status](http://img.shields.io/travis/vipstar-dev/vipsd.svg)](https://travis-ci.org/vipstar-dev/vipsd)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/vipstar-dev/vipsd/rpcclient)

rpcclient implements a Websocket-enabled VIPSTARCOIN JSON-RPC client package written
in [Go](http://golang.org/).  It provides a robust and easy to use client for
interfacing with a VIPSTARCOIN RPC server that uses a vipsd/vipstarcoin core compatible
Bitcoin JSON-RPC API.

## Status

This package is currently under active development.  It is already stable and
the infrastructure is complete.  However, there are still several RPCs left to
implement and the API is not stable yet.

## Documentation

* [API Reference](http://godoc.org/github.com/btcsuite/btcd/rpcclient)
* [btcd Websockets Example](https://github.com/btcsuite/btcd/tree/master/rpcclient/examples/btcdwebsockets)
  Connects to a btcd RPC server using TLS-secured websockets, registers for
  block connected and block disconnected notifications, and gets the current
  block count
* [btcwallet Websockets Example](https://github.com/btcsuite/btcd/tree/master/rpcclient/examples/btcwalletwebsockets)
  Connects to a btcwallet RPC server using TLS-secured websockets, registers for
  notifications about changes to account balances, and gets a list of unspent
  transaction outputs (utxos) the wallet can sign
* [Bitcoin Core HTTP POST Example](https://github.com/btcsuite/btcd/tree/master/rpcclient/examples/bitcoincorehttp)
  Connects to a bitcoin core RPC server using HTTP POST mode with TLS disabled
  and gets the current block count

## Major Features

* Supports Websockets (vipsd/vipswallet) and HTTP POST mode (vipstarcoin core)
* Provides callback and registration functions for vipsd/vipswallet notifications
* Supports vipsd extensions
* Translates to and from higher-level and easier to use Go types
* Offers a synchronous (blocking) and asynchronous API
* When running in Websockets mode (the default):
  * Automatic reconnect handling (can be disabled)
  * Outstanding commands are automatically reissued
  * Registered notifications are automatically reregistered
  * Back-off support on reconnect attempts

## Installation

```bash
$ go get -u github.com/vipstar-dev/vipsd/rpcclient
```

## License

Package rpcclient is licensed under the [copyfree](http://copyfree.org) ISC
License.
