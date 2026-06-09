# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000c2e4`
- end: `0x14000c382`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000bda8`
- `0x14000becc`
- `0x14000d650`
- `0x14000dad4`
- `0x14000eca8`

## callees

- `0x14000c2e4`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c342`
- `KERNEL32!GetProcAddress` at `0x14000c342`
- `KERNEL32!GetModuleHandleW` at `0x14000c32d`
- `KERNEL32!GetModuleHandleW` at `0x14000c32d`
- `KERNEL32!HeapAlloc` at `0x14000c309`
- `KERNEL32!HeapAlloc` at `0x14000c309`
- `KERNEL32!GetProcessHeap` at `0x14000c2f8`
- `KERNEL32!GetProcessHeap` at `0x14000c2f8`

## string_xrefs

- `0x14000c326`: `ntdll.dll`

## pseudocode

```c

```
