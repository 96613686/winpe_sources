# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180266aa4`
- end: `0x180266b3a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180237100`
- `0x180237254`
- `0x180267574`
- `0x1802677d8`
- `0x180268580`

## callees

- `0x1802643b4`
- `0x180266aa4`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180266aed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180266aed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180266ac9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180266ac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180266ab8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180266ab8`

## string_xrefs

- `0x180266ae6`: `ntdll.dll`

## pseudocode

```c

```
