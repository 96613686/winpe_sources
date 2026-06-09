# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d668`
- end: `0x18000d706`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a918`
- `0x18000acf8`
- `0x18000bfe0`
- `0x18000c6e8`
- `0x18000f2a4`
- `0x180011974`

## callees

- `0x18000d668`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d6b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d6b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d6c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d6c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d68d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d68d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d67c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d67c`

## string_xrefs

- `0x18000d6aa`: `ntdll.dll`

## pseudocode

```c

```
