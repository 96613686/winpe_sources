# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180179588`
- end: `0x180179627`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180178de4`
- `0x180179b5c`
- `0x180179cdc`

## callees

- `0x180179588`
- `0x18023a290`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1801795e6`
- `KERNEL32!GetProcAddress` at `0x1801795e6`
- `KERNEL32!GetModuleHandleW` at `0x1801795d1`
- `KERNEL32!GetModuleHandleW` at `0x1801795d1`
- `KERNEL32!HeapAlloc` at `0x1801795ad`
- `KERNEL32!HeapAlloc` at `0x1801795ad`
- `KERNEL32!GetProcessHeap` at `0x18017959c`
- `KERNEL32!GetProcessHeap` at `0x18017959c`

## string_xrefs

- `0x1801795ca`: `ntdll.dll`

## pseudocode

```c

```
