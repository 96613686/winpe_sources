# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180137c94`
- end: `0x180137d4c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `184`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801378f8`
- `0x180138274`
- `0x180138894`
- `0x180139010`

## callees

- `0x180137c94`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180137ca8`
- `KERNEL32!GetProcessHeap` at `0x180137ca8`
- `KERNEL32!HeapAlloc` at `0x180137cbf`
- `KERNEL32!HeapAlloc` at `0x180137cbf`
- `KERNEL32!GetProcAddress` at `0x180137d04`
- `KERNEL32!GetProcAddress` at `0x180137d04`
- `KERNEL32!GetModuleHandleW` at `0x180137ce9`
- `KERNEL32!GetModuleHandleW` at `0x180137ce9`

## string_xrefs

- `0x180137ce2`: `ntdll.dll`

## pseudocode

```c

```
