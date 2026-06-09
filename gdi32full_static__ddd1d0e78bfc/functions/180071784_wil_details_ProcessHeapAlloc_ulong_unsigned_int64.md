# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180071784`
- end: `0x18007183c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `184`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007efac`
- `0x180087b50`
- `0x180087c7c`
- `0x180088a0c`
- `0x180088eb8`

## callees

- `0x180071784`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800717f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800717f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800717d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800717d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800717af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800717af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071798`

## string_xrefs

- `0x1800717d2`: `ntdll.dll`

## pseudocode

```c

```
