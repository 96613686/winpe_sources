# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003dd4c`
- end: `0x18003ddea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003dca4`
- `0x18007d978`
- `0x18007daa8`
- `0x18007e250`
- `0x18007e5e8`

## callees

- `0x18003dd4c`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ddaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ddaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003dd95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003dd95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003dd71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003dd71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dd60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dd60`

## string_xrefs

- `0x18003dd8e`: `ntdll.dll`

## pseudocode

```c

```
