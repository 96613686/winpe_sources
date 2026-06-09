# GetDllProcAddr(_DLL_PROC_ELEMENT *,void * *,void * *)

- ea: `0x180029500`
- end: `0x18002961b`
- name: `?GetDllProcAddr@@YAHPEAU_DLL_PROC_ELEMENT@@PEAPEAX1@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct _DLL_PROC_ELEMENT *, void **, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800288b0`
- `0x180028d9c`
- `0x180029b00`

## callees

- `0x1800258c4`
- `0x180027ba8`
- `0x180029500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002960d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002960d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002951c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002951c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800295da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800295da`

## pseudocode

```c

```
