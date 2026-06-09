# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400066e8`
- end: `0x140006791`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000645c`
- `0x140006b54`
- `0x140006f08`
- `0x14000ef00`
- `0x140013220`

## callees

- `0x14000439c`
- `0x1400066e8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140006713`
- `KERNEL32!HeapAlloc` at `0x140006713`
- `KERNEL32!GetProcessHeap` at `0x1400066fc`
- `KERNEL32!GetProcessHeap` at `0x1400066fc`
- `KERNEL32!GetModuleHandleW` at `0x14000673d`
- `KERNEL32!GetModuleHandleW` at `0x14000673d`

## string_xrefs

- `0x140006736`: `ntdll.dll`

## pseudocode

```c

```
