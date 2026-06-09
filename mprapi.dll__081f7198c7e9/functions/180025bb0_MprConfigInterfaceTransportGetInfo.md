# MprConfigInterfaceTransportGetInfo

- ea: `0x180025bb0`
- end: `0x180025c9f`
- name: `MprConfigInterfaceTransportGetInfo`
- size: `239`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, HANDLE hRouterIfTransport, LPBYTE *ppInterfaceInfo, LPDWORD lpdwInterfaceInfoSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180025bb0`
- `0x180027d5c`
- `0x180028898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c53`

## pseudocode

```c

```
