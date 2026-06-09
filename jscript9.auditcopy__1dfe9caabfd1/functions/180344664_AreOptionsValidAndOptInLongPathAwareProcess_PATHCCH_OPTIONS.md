# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x180344664`
- end: `0x18034471f`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `187`
- prototype: `char __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x1803447d0`

## callees

- `0x180344664`
- `0x180364010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1803446d1`
- `KERNEL32!GetModuleHandleW` at `0x1803446d1`
- `KERNEL32!GetProcAddress` at `0x1803446e7`
- `KERNEL32!GetProcAddress` at `0x1803446e7`

## string_xrefs

- `0x1803446ca`: `ntdll.dll`
- `0x1803446e0`: `RtlAreLongPathsEnabled`

## pseudocode

```c

```
