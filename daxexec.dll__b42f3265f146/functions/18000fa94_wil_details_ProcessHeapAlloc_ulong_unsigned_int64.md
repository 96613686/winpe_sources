# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fa94`
- end: `0x18000fb4b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e58c`
- `0x18000f200`
- `0x180010440`
- `0x180017fdc`
- `0x1800217b8`

## callees

- `0x18000fa94`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fae9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fae9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000faa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000faa8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fabf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fabf`

## string_xrefs

- `0x18000fae2`: `ntdll.dll`

## pseudocode

```c

```
