# TX-Fuzz

TX-Fuzz is a package containing helpful functions to create random transactions. 
It can be used to easily access fuzzed transactions from within other programs.

## Fork

This is a fork of tx-fuzz with the following enhancements:
- Configurable faucet
- Configurable private keys (which are the recipients of the fuzzed transactions)

## Usage

```
go run cmd/livefuzzer/main.go
```

Run an execution layer client such as [Geth][1] locally in a standalone bash window.
Tx-fuzz sends transactions to port `8545` by default.

```
geth --http --http.port 8545
```

Run livefuzzer.

```
go run cmd/livefuzzer/main.go spam
```

Tx-fuzz allows for an optional seed parameter to get reproducible fuzz transactions

## Advanced usage
You can optionally specify a seed parameter or a secret key to use as a faucet

```
go run cmd/livefuzzer/main.go spam --seed <seed> --sk <SK>
```

You can set the RPC to use with `--rpc <RPC>`.
