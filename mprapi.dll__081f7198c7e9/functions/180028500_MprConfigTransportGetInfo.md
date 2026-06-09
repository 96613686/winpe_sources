# MprConfigTransportGetInfo

- ea: `0x180028500`
- end: `0x1800286f2`
- name: `MprConfigTransportGetInfo`
- size: `498`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterTransport, LPBYTE *ppGlobalInfo, LPDWORD lpdwGlobalInfoSize, LPBYTE *ppClientInterfaceInfo, LPDWORD lpdwClientInterfaceInfoSize, LPWSTR *lplpwsDLLPath)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001808c`
- `0x1800181b8`
- `0x18003628c`

## callees

- `0x180027d5c`
- `0x180028500`
- `0x180028898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800285c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800285c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028587`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002867b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002867b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002865f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800286b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002865f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800286b0`

## string_xrefs

- `0x18002862e`: `DLLPath`

## pseudocode

```c

```
