# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004d578`
- end: `0x18004d616`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800508dc`
- `0x18005cc80`
- `0x18005d010`
- `0x18005d3a8`
- `0x180060cc4`

## callees

- `0x18004d578`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d5c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d5c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d5d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d5d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d59d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d59d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d58c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d58c`

## string_xrefs

- `0x18004d5ba`: `ntdll.dll`

## pseudocode

```c

```
