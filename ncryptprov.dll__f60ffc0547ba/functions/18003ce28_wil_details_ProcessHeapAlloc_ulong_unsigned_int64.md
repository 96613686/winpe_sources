# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003ce28`
- end: `0x18003cedf`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180036d3c`
- `0x18003ca24`
- `0x18003cb50`
- `0x18003db54`
- `0x18003dff4`

## callees

- `0x18003ce28`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ce7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ce7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce3c`

## string_xrefs

- `0x18003ce76`: `ntdll.dll`

## pseudocode

```c

```
