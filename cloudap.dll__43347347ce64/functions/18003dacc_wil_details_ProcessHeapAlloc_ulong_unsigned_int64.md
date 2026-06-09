# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003dacc`
- end: `0x18003db62`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016870`
- `0x180028d30`
- `0x18003b72c`
- `0x180045284`
- `0x1800453b4`
- `0x1800458f0`
- `0x180045a2c`

## callees

- `0x18003dacc`
- `0x180043924`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003db15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003db15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003daf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003daf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dae0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dae0`

## string_xrefs

- `0x18003db0e`: `ntdll.dll`

## pseudocode

```c

```
