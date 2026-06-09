# MprConfigInterfaceTransportRemove

- ea: `0x180025cb0`
- end: `0x180025d58`
- name: `MprConfigInterfaceTransportRemove`
- size: `168`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, HANDLE hRouterIfTransport)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800255a0`
- `0x180036870`

## callees

- `0x180018470`
- `0x180025cb0`
- `0x180027d5c`
- `0x18002884c`
- `0x18002998c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ce4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ce4`

## pseudocode

```c

```
