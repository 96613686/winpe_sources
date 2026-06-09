# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000efe8`
- end: `0x14000f039`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000c000`
- `0x14000f400`

## callees

- `0x14000efe8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000f022`
- `KERNEL32!GetProcAddress` at `0x14000f022`
- `KERNEL32!GetModuleHandleW` at `0x14000f00a`
- `KERNEL32!GetModuleHandleW` at `0x14000f00a`

## string_xrefs

- `0x14000f001`: `kernelbase.dll`

## pseudocode

```c

```
