# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800060f8`
- end: `0x18000618e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000550c`
- `0x180005eec`
- `0x180006384`
- `0x1800064c0`
- `0x1800170f0`
- `0x18001a764`

## callees

- `0x1800041e4`
- `0x1800060f8`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006141`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006141`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000611d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000611d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000610c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000610c`

## string_xrefs

- `0x18000613a`: `ntdll.dll`

## pseudocode

```c

```
