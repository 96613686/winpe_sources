# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004d7d0`
- end: `0x18004d86e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003580c`
- `0x180050c9c`
- `0x180050dc0`
- `0x1800519f4`
- `0x180051c1c`

## callees

- `0x18004d7d0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d819`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d82e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d82e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d7f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d7f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d7e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d7e4`

## string_xrefs

- `0x18004d812`: `ntdll.dll`

## pseudocode

```c

```
