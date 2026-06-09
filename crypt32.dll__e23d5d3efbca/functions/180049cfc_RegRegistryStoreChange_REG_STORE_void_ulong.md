# RegRegistryStoreChange(_REG_STORE *,void *,ulong)

- ea: `0x180049cfc`
- end: `0x180049f09`
- name: `?RegRegistryStoreChange@@YAHPEAU_REG_STORE@@PEAXK@Z`
- size: `525`
- prototype: `__int64 __fastcall(PVOID pv, HANDLE hSourceHandle, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800480a8`
- `0x18004933c`
- `0x1800499f0`
- `0x180049cdc`

## callees

- `0x180049cfc`
- `0x18004a210`
- `0x180059df8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801180e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801180e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049e5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049e5f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180049da6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180049da6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049e88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049e88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049e91`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180049ec0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180049ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e55`

## pseudocode

```c

```
