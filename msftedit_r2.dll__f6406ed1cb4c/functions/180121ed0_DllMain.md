# DllMain

- ea: `0x180121ed0`
- end: `0x180121f53`
- name: `DllMain`
- size: `131`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18013ccf4`

## callees

- `0x1800de288`
- `0x1800de2e8`
- `0x1800de4e8`
- `0x1800de51c`
- `0x180121ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180121f10`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180121f10`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180121eef`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180121eef`

## pseudocode

```c

```
