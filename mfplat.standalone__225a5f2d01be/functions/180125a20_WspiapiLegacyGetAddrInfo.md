# WspiapiLegacyGetAddrInfo

- ea: `0x180125a20`
- end: `0x180125d6b`
- name: `WspiapiLegacyGetAddrInfo`
- size: `843`
- prototype: `int __stdcall(const char *pszNodeName, const char *pszServiceName, const struct addrinfo *ptHints, struct addrinfo **pptResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1801259c0`
- `0x180125a20`
- `0x1801261b4`
- `0x180126320`
- `0x180126488`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180125b05`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180125b05`
- `WS2_32!__imp_htonl` at `0x180125c81`
- `WS2_32!__imp_htonl` at `0x180125c81`
- `WS2_32!__imp_htons` at `0x180125b21`
- `WS2_32!__imp_htons` at `0x180125b21`
- `WS2_32!__imp_inet_addr` at `0x180125c20`
- `WS2_32!__imp_inet_addr` at `0x180125c20`
- `WS2_32!__imp_inet_ntoa` at `0x180125cbf`
- `WS2_32!__imp_inet_ntoa` at `0x180125cbf`
- `WS2_32!__imp_getservbyname` at `0x180125b5f`
- `WS2_32!__imp_getservbyname` at `0x180125b95`
- `WS2_32!__imp_getservbyname` at `0x180125b5f`
- `WS2_32!__imp_getservbyname` at `0x180125b95`

## pseudocode

```c

```
