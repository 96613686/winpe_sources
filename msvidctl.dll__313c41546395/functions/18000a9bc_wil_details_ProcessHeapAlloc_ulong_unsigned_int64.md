# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a9bc`
- end: `0x18000aa5a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a7b4`
- `0x18000b87c`
- `0x18000bc14`
- `0x18000c848`

## callees

- `0x18000a9bc`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000aa1a`
- `KERNEL32!GetProcAddress` at `0x18000aa1a`
- `KERNEL32!GetModuleHandleW` at `0x18000aa05`
- `KERNEL32!GetModuleHandleW` at `0x18000aa05`
- `KERNEL32!HeapAlloc` at `0x18000a9e1`
- `KERNEL32!HeapAlloc` at `0x18000a9e1`
- `KERNEL32!GetProcessHeap` at `0x18000a9d0`
- `KERNEL32!GetProcessHeap` at `0x18000a9d0`

## string_xrefs

- `0x18000a9fe`: `ntdll.dll`

## pseudocode

```c

```
