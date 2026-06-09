# MprConfigServerGetInfo

- ea: `0x1800269c0`
- end: `0x180026b10`
- name: `MprConfigServerGetInfo`
- size: `336`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwLevel, LPBYTE *lplpbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18002175c`
- `0x1800269c0`
- `0x180027d5c`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026a88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026a88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026abb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026abb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ac9`

## pseudocode

```c

```
