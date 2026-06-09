# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000babc`
- end: `0x18000bb64`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(wil::details *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aaa8`
- `0x18000b1a0`
- `0x18000b930`
- `0x18000bee8`

## callees

- `0x18000babc`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000baea`
- `KERNEL32!HeapAlloc` at `0x18000baea`
- `KERNEL32!GetProcessHeap` at `0x18000bad9`
- `KERNEL32!GetProcessHeap` at `0x18000bad9`
- `KERNEL32!GetModuleHandleW` at `0x18000bb0e`
- `KERNEL32!GetModuleHandleW` at `0x18000bb0e`
- `KERNEL32!GetProcAddress` at `0x18000bb23`
- `KERNEL32!GetProcAddress` at `0x18000bb23`

## string_xrefs

- `0x18000bb07`: `ntdll.dll`

## pseudocode

```c

```
