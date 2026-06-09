# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180045f38`
- end: `0x180045fd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003f130`
- `0x18003f3e4`
- `0x180046a24`
- `0x180046c94`
- `0x180047b20`

## callees

- `0x180045f38`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045f4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045f4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180045f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180045f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045f96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045f96`

## string_xrefs

- `0x180045f7a`: `ntdll.dll`

## pseudocode

```c

```
