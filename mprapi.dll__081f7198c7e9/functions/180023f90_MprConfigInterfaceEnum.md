# MprConfigInterfaceEnum

- ea: `0x180023f90`
- end: `0x1800241f1`
- name: `MprConfigInterfaceEnum`
- size: `609`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwLevel, LPBYTE *lplpBuffer, DWORD dwPrefMaxLen, LPDWORD lpdwEntriesRead, LPDWORD lpdwTotalEntries, LPDWORD lpdwResumeHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036a0c`

## callees

- `0x180022324`
- `0x180023f90`
- `0x180027d5c`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800240f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800241d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800240f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800241d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024009`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024009`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800240cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800240cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800240d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800240d9`

## pseudocode

```c

```
