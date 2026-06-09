# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d118`
- end: `0x18000d1c1`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c454`
- `0x18000ce8c`
- `0x18000d584`
- `0x18000d938`
- `0x18001dee0`
- `0x1800204f8`

## callees

- `0x18000ad64`
- `0x18000d118`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d16d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d16d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d143`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d12c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d12c`

## string_xrefs

- `0x18000d166`: `ntdll.dll`

## pseudocode

```c

```
