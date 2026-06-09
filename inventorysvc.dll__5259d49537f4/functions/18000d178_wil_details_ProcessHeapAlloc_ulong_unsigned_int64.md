# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d178`
- end: `0x18000d216`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008318`
- `0x1800086f8`
- `0x18000ad10`
- `0x18000ed44`
- `0x18001125c`

## callees

- `0x18000d178`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d18c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d19d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d19d`

## string_xrefs

- `0x18000d1ba`: `ntdll.dll`

## pseudocode

```c

```
