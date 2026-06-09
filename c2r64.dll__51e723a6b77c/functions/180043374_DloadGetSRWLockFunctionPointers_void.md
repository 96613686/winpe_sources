# DloadGetSRWLockFunctionPointers(void)

- ea: `0x180043374`
- end: `0x180043412`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800431cc`
- `0x1800432b8`
- `0x180043640`

## callees

- `0x180043374`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800433b8`
- `KERNEL32!GetProcAddress` at `0x1800433d4`
- `KERNEL32!GetProcAddress` at `0x1800433b8`
- `KERNEL32!GetProcAddress` at `0x1800433d4`
- `KERNEL32!GetModuleHandleW` at `0x18004339b`
- `KERNEL32!GetModuleHandleW` at `0x18004339b`

## string_xrefs

- `0x180043394`: `KERNEL32.DLL`

## pseudocode

```c

```
