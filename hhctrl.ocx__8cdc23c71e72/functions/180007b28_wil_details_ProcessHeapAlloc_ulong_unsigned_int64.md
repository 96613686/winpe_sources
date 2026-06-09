# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007b28`
- end: `0x180007bc6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006e64`
- `0x180006f8c`
- `0x180008d94`
- `0x18000928c`
- `0x18000a3d4`

## callees

- `0x180007b28`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007b71`
- `KERNEL32!GetModuleHandleW` at `0x180007b71`
- `KERNEL32!HeapAlloc` at `0x180007b4d`
- `KERNEL32!HeapAlloc` at `0x180007b4d`
- `KERNEL32!GetProcessHeap` at `0x180007b3c`
- `KERNEL32!GetProcessHeap` at `0x180007b3c`
- `KERNEL32!GetProcAddress` at `0x180007b86`
- `KERNEL32!GetProcAddress` at `0x180007b86`

## string_xrefs

- `0x180007b6a`: `ntdll.dll`

## pseudocode

```c

```
