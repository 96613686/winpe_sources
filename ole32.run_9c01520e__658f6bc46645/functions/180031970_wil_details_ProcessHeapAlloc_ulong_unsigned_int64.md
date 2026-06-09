# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180031970`
- end: `0x180031a27`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(unsigned int flags, unsigned __int64 size)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024d34`
- `0x180029f48`
- `0x18002a558`
- `0x18004a608`
- `0x18004a950`
- `0x18004b460`

## callees

- `0x180031970`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800319e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800319e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800319c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800319c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003199b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003199b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031984`

## string_xrefs

- `0x1800319be`: `ntdll.dll`

## pseudocode

```c

```
