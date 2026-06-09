# CONFIG_CACHE::GetFileChanged(CONFIG_FILE *,ushort const *,ushort const *,void *,int *)

- ea: `0x18004f07c`
- end: `0x18004f197`
- name: `?GetFileChanged@CONFIG_CACHE@@QEAAJPEAVCONFIG_FILE@@PEBG1PEAXPEAH@Z`
- size: `283`
- prototype: `__int64 __fastcall(CONFIG_CACHE *this, struct CONFIG_FILE *, const unsigned __int16 *, const unsigned __int16 *, HANDLE hSourceHandle, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180050d98`

## callees

- `0x1800174d0`
- `0x18001753c`
- `0x18004eee8`
- `0x18004f07c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0f5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004f0eb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004f0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f0b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f0c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f0b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f0c2`

## pseudocode

```c

```
