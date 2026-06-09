# MprConfigInterfaceTransportGetHandle

- ea: `0x180025ac0`
- end: `0x180025ba1`
- name: `MprConfigInterfaceTransportGetHandle`
- size: `225`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwTransportId, HANDLE *phRouterIfTransport)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036158`

## callees

- `0x18002201c`
- `0x180025ac0`
- `0x180027d5c`
- `0x180029414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025aff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025aff`

## pseudocode

```c

```
