# MprConfigInterfaceTransportEnum

- ea: `0x180025880`
- end: `0x180025ab0`
- name: `MprConfigInterfaceTransportEnum`
- size: `560`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwLevel, LPBYTE *lplpBuffer, DWORD dwPrefMaxLen, LPDWORD lpdwEntriesRead, LPDWORD lpdwTotalEntries, LPDWORD lpdwResumeHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180036870`

## callees

- `0x180009868`
- `0x18002201c`
- `0x180025880`
- `0x180027d5c`
- `0x180029414`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800259dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800259dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800259ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800259ea`

## pseudocode

```c

```
