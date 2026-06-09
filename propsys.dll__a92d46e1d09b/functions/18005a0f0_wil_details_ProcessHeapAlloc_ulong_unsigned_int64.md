# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005a0f0`
- end: `0x18005a186`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004c39c`
- `0x18004ffac`
- `0x1800509fc`
- `0x18005a04c`
- `0x180068c78`
- `0x180068dfc`
- `0x180073300`

## callees

- `0x18005a0f0`
- `0x180071bfc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005a139`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005a139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a104`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a104`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a115`

## string_xrefs

- `0x18005a132`: `ntdll.dll`

## pseudocode

```c

```
