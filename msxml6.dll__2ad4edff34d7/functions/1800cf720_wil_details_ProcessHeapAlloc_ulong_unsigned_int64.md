# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800cf720`
- end: `0x1800cf7b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(unsigned int flags, unsigned __int64 size)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800b9ebc`
- `0x1800cf238`
- `0x1800cf35c`
- `0x1800cff94`
- `0x1800d010c`

## callees

- `0x1800ccf8c`
- `0x1800cf720`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cf769`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cf769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf745`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf734`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf734`

## string_xrefs

- `0x1800cf762`: `ntdll.dll`

## pseudocode

```c

```
