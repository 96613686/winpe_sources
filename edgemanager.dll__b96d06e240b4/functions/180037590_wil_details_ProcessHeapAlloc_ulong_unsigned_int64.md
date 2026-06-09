# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180037590`
- end: `0x18003762e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021014`
- `0x180037460`
- `0x180037704`
- `0x180037840`
- `0x1800752a8`

## callees

- `0x180037590`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800375d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800375d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800375b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800375b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800375a4`

## string_xrefs

- `0x1800375d2`: `ntdll.dll`

## pseudocode

```c

```
