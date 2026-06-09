# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180038044`
- end: `0x1800380e2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b2a8`
- `0x180037c48`
- `0x180037d6c`
- `0x1800389ac`
- `0x180038c10`

## callees

- `0x180038044`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003808d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003808d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800380a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800380a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038069`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038058`

## string_xrefs

- `0x180038086`: `ntdll.dll`

## pseudocode

```c

```
