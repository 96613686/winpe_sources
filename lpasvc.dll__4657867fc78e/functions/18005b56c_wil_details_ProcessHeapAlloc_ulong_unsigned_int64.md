# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005b56c`
- end: `0x18005b60a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005b0a4`
- `0x18005b1cc`
- `0x18005c680`
- `0x18005cb08`
- `0x18005dc3c`

## callees

- `0x18005b56c`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b5b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b5b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b5ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b5ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b591`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b591`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b580`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b580`

## string_xrefs

- `0x18005b5ae`: `ntdll.dll`

## pseudocode

```c

```
