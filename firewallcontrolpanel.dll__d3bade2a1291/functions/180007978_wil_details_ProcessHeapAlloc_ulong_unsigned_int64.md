# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007978`
- end: `0x180007a16`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006d7c`
- `0x18000777c`
- `0x180007c7c`
- `0x180008014`

## callees

- `0x180007978`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000799d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000799d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798c`

## string_xrefs

- `0x1800079ba`: `ntdll.dll`

## pseudocode

```c

```
