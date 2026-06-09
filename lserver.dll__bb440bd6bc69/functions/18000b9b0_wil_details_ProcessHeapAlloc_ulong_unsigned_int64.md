# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b9b0`
- end: `0x18000ba67`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b624`
- `0x18000ca88`
- `0x18000ce50`
- `0x18000f468`
- `0x1800601f0`

## callees

- `0x18000b9b0`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000b9db`
- `KERNEL32!HeapAlloc` at `0x18000b9db`
- `KERNEL32!GetProcessHeap` at `0x18000b9c4`
- `KERNEL32!GetProcessHeap` at `0x18000b9c4`
- `KERNEL32!GetModuleHandleW` at `0x18000ba05`
- `KERNEL32!GetModuleHandleW` at `0x18000ba05`
- `KERNEL32!GetProcAddress` at `0x18000ba20`
- `KERNEL32!GetProcAddress` at `0x18000ba20`

## string_xrefs

- `0x18000b9fe`: `ntdll.dll`

## pseudocode

```c

```
