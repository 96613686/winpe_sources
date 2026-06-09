# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18006215c`
- end: `0x180062213`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004cb24`
- `0x180061940`
- `0x180061d4c`
- `0x180061e84`
- `0x180062478`
- `0x1800625c4`

## callees

- `0x18006215c`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800621b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800621b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800621cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800621cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062170`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062170`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062187`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062187`

## string_xrefs

- `0x1800621aa`: `ntdll.dll`

## pseudocode

```c

```
