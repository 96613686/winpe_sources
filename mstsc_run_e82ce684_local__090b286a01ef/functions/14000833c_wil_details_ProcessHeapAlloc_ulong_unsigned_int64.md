# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000833c`
- end: `0x1400083d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000814c`
- `0x14000872c`
- `0x140008868`
- `0x1400090e4`

## callees

- `0x14000626c`
- `0x14000833c`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140008385`
- `KERNEL32!GetModuleHandleW` at `0x140008385`
- `KERNEL32!GetProcessHeap` at `0x140008350`
- `KERNEL32!GetProcessHeap` at `0x140008350`
- `KERNEL32!HeapAlloc` at `0x140008361`
- `KERNEL32!HeapAlloc` at `0x140008361`

## string_xrefs

- `0x14000837e`: `ntdll.dll`

## pseudocode

```c

```
