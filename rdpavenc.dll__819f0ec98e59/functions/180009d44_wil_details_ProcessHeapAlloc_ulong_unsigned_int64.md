# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009d44`
- end: `0x180009de2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008798`
- `0x180008e10`
- `0x18000a2a4`

## callees

- `0x180009d44`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009da2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009da2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d58`

## string_xrefs

- `0x180009d86`: `ntdll.dll`

## pseudocode

```c

```
