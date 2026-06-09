# GetStringFromSockAddr(sockaddr_storage *)

- ea: `0x1800b2b74`
- end: `0x1800b2d80`
- name: `?GetStringFromSockAddr@@YAPEAGPEAUsockaddr_storage@@@Z`
- size: `524`
- prototype: `unsigned __int16 *__fastcall(LPSOCKADDR lpsaAddress)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18005ce5c`

## callees

- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800b2b74`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2c75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2c75`
- `WS2_32!WSAAddressToStringW` at `0x1800b2c49`
- `WS2_32!WSAAddressToStringW` at `0x1800b2cfc`
- `WS2_32!WSAAddressToStringW` at `0x1800b2c49`
- `WS2_32!WSAAddressToStringW` at `0x1800b2cfc`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b2c58`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b2c58`
- `WS2_32!__imp_WSAStartup` at `0x1800b2bbc`
- `WS2_32!__imp_WSAStartup` at `0x1800b2bbc`
- `WS2_32!__imp_WSACleanup` at `0x1800b2d56`
- `WS2_32!__imp_WSACleanup` at `0x1800b2d56`

## pseudocode

```c

```
