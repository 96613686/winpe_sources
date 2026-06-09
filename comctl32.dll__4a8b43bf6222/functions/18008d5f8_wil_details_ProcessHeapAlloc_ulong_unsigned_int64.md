# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18008d5f8`
- end: `0x18008d696`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18008bee0`
- `0x18008c580`
- `0x18008d940`

## callees

- `0x18008d5f8`
- `0x180090020`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18008d61d`
- `KERNEL32!HeapAlloc` at `0x18008d61d`
- `KERNEL32!GetProcAddress` at `0x18008d656`
- `KERNEL32!GetProcAddress` at `0x18008d656`
- `KERNEL32!GetProcessHeap` at `0x18008d60c`
- `KERNEL32!GetProcessHeap` at `0x18008d60c`
- `KERNEL32!GetModuleHandleW` at `0x18008d641`
- `KERNEL32!GetModuleHandleW` at `0x18008d641`

## string_xrefs

- `0x18008d63a`: `ntdll.dll`

## pseudocode

```c

```
