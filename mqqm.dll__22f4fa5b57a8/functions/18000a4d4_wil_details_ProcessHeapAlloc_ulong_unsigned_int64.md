# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a4d4`
- end: `0x18000a573`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009d7c`
- `0x180009ed8`
- `0x18000b380`
- `0x18000b844`
- `0x18000cc28`

## callees

- `0x18000a4d4`
- `0x1800e4010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a4e8`
- `KERNEL32!GetProcessHeap` at `0x18000a4e8`
- `KERNEL32!HeapAlloc` at `0x18000a4f9`
- `KERNEL32!HeapAlloc` at `0x18000a4f9`
- `KERNEL32!GetModuleHandleW` at `0x18000a51d`
- `KERNEL32!GetModuleHandleW` at `0x18000a51d`
- `KERNEL32!GetProcAddress` at `0x18000a532`
- `KERNEL32!GetProcAddress` at `0x18000a532`

## string_xrefs

- `0x18000a516`: `ntdll.dll`

## pseudocode

```c

```
