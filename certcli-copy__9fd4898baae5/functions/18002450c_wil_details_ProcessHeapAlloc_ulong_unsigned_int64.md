# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002450c`
- end: `0x1800245aa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024130`
- `0x1800242c8`
- `0x180025278`
- `0x1800254a4`
- `0x180026f18`

## callees

- `0x18002450c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024555`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024555`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002456a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002456a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024520`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024531`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024531`

## string_xrefs

- `0x18002454e`: `ntdll.dll`

## pseudocode

```c

```
