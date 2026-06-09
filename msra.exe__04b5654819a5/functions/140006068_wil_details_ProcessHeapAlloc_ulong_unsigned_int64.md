# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006068`
- end: `0x14000611f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003d74`
- `0x140004120`
- `0x140007d24`
- `0x14000955c`

## callees

- `0x140006068`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400060bd`
- `KERNEL32!GetModuleHandleW` at `0x1400060bd`
- `KERNEL32!GetProcessHeap` at `0x14000607c`
- `KERNEL32!GetProcessHeap` at `0x14000607c`
- `KERNEL32!GetProcAddress` at `0x1400060d8`
- `KERNEL32!GetProcAddress` at `0x1400060d8`
- `KERNEL32!HeapAlloc` at `0x140006093`
- `KERNEL32!HeapAlloc` at `0x140006093`

## string_xrefs

- `0x1400060b6`: `ntdll.dll`

## pseudocode

```c

```
