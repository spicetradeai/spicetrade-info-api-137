# Documentation

All Spice Trade pairs consist of two different tokens.

Results are cached for 5 minutes (or 300 seconds).

## [`/v2/summary`](https://api137.spicetrade.ai/api/v2/summary)

Returns data for the top ~1000 Spice Trade pairs, sorted by reserves. 

### Request

`GET https://api137.spicetrade.ai/api/v2/summary`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // BEP20 token addresses, joined by an underscore
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // last 24h volume denominated in token0
      "quote_volume": "...",          // last 24h volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_USDS": "..."          // liquidity denominated in USDS
    },
    // ...
  }
}
```

## [`/v2/tokens`](https://api137.spicetrade.ai/api/v2/tokens)

Returns the tokens in the top ~1000 pairs on Spice Trade, sorted by reserves.

### Request

`GET https://api137.spicetrade.ai/api/v2/tokens`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x...": {                        // the address of the BEP20 token
      "name": "...",                  // not necessarily included for BEP20 tokens
      "symbol": "...",                // not necessarily included for BEP20 tokens
      "price": "...",                 // price denominated in USD
      "price_USDS": "...",             // price denominated in USDS
    },
    // ...
  }
}
```

## [`/v2/tokens/0x...`](https://api137.spicetrade.ai/api/v2/tokens/0x2f1b1662a895c6ba01a99dcaf56778e7d77e5609)

Returns the token information, based on address.

### Request

`GET https://api137.spicetrade.ai/api/v2/tokens/0x2f1b1662a895c6ba01a99dcaf56778e7d77e5609`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "name": "...",                    // not necessarily included for BEP20 tokens
    "symbol": "...",                  // not necessarily included for BEP20 tokens
    "price": "...",                   // price denominated in USD
    "price_USDS": "...",               // price denominated in USDS
  }
}
```

## [`/v2/pairs`](https://api137.spicetrade.ai/api/v2/pairs)

Returns data for the top ~1000 Spice Trade pairs, sorted by reserves.

### Request

`GET https://api137.spicetrade.ai/api/v2/pairs`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of USDS and BEP20 tokens, joined by an underscore
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_USDS": "..."          // liquidity denominated in USDS
    },
    // ...
  }
}
```
