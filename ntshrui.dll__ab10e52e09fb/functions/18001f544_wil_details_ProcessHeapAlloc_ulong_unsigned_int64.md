# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001f544`
- end: `0x18001f5da`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800150f0`
- `0x180015ba4`
- `0x1800207b0`
- `0x180020914`
- `0x1800295a8`
- `0x180029e50`
- `0x18002a1e8`
- `0x180031fa4`

## callees

- `0x18001f544`
- `0x180028634`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f58d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f58d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f558`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f558`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f569`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f569`

## string_xrefs

- `0x18001f586`: `ntdll.dll`

## pseudocode

```c

```
