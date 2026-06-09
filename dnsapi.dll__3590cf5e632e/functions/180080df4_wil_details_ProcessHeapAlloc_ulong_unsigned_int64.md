# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180080df4`
- end: `0x180080eab`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007fd74`
- `0x1800c81f4`
- `0x1800c8320`
- `0x1800c90e8`
- `0x1800c9358`

## callees

- `0x180080df4`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080e64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080e64`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180080e49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180080e49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080e08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080e1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080e1f`

## string_xrefs

- `0x180080e42`: `ntdll.dll`

## pseudocode

```c

```
