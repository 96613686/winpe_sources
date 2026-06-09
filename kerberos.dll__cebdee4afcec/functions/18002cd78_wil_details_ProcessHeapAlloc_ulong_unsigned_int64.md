# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002cd78`
- end: `0x18002ce19`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180064f68`
- `0x18007604c`
- `0x180076170`
- `0x180076750`
- `0x180076ae8`

## callees

- `0x18002cd78`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cde0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cde0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ce0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ce0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cd9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cd9d`

## string_xrefs

- `0x18002cdd9`: `ntdll.dll`

## pseudocode

```c

```
