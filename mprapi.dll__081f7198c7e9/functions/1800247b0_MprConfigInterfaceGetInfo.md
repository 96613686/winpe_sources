# MprConfigInterfaceGetInfo

- ea: `0x1800247b0`
- end: `0x1800249a8`
- name: `MprConfigInterfaceGetInfo`
- size: `504`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwLevel, LPBYTE *lplpBuffer, LPDWORD lpdwBufferSize)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000a76c`
- `0x1800247b0`
- `0x180027d5c`
- `0x18002ecc4`
- `0x180051112`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024988`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024814`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002487c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002487c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002488a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002488a`

## pseudocode

```c

```
