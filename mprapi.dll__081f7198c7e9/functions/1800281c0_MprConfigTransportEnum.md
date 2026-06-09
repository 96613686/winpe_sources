# MprConfigTransportEnum

- ea: `0x1800281c0`
- end: `0x180028422`
- name: `MprConfigTransportEnum`
- size: `610`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwLevel, LPBYTE *lplpBuffer, DWORD dwPrefMaxLen, LPDWORD lpdwEntriesRead, LPDWORD lpdwTotalEntries, LPDWORD lpdwResumeHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180022be8`
- `0x180027d5c`
- `0x1800281c0`
- `0x180029414`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002833f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002833f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002823e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002823e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028319`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028327`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028327`

## pseudocode

```c

```
