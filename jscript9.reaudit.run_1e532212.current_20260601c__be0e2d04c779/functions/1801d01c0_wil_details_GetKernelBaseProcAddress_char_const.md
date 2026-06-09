# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1801d01c0`
- end: `0x1801d0214`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `84`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1801cf9dc`
- `0x1801d0800`

## callees

- `0x1801d01c0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1801d01e8`
- `KERNEL32!GetModuleHandleW` at `0x1801d01e8`
- `KERNEL32!GetProcAddress` at `0x1801d0202`
- `KERNEL32!GetProcAddress` at `0x1801d0202`

## string_xrefs

- `0x1801d01e1`: `kernelbase.dll`

## pseudocode

```c

```
