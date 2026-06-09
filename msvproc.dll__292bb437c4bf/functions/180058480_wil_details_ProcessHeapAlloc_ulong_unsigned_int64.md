# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180058480`
- end: `0x18005851e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180058274`
- `0x180058b7c`
- `0x180058cb8`
- `0x18005f180`
- `0x18005f5c0`
- `0x18005fa20`
- `0x180063930`
- `0x180070110`

## callees

- `0x180058480`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800584c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800584c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800584de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800584de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800584a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800584a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058494`

## string_xrefs

- `0x1800584c2`: `ntdll.dll`

## pseudocode

```c

```
