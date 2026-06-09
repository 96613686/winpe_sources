# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x18033e464`
- end: `0x18033e512`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `174`
- prototype: `bool __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18033e5bc`

## callees

- `0x18033e464`
- `0x18035e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18033e4d1`
- `KERNEL32!GetModuleHandleW` at `0x18033e4d1`
- `KERNEL32!GetProcAddress` at `0x18033e4e1`
- `KERNEL32!GetProcAddress` at `0x18033e4e1`

## string_xrefs

- `0x18033e4ca`: `ntdll.dll`
- `0x18033e4da`: `RtlAreLongPathsEnabled`

## pseudocode

```c

```
