# SepSddlGetAclForString

- ea: `0x1400834c8`
- end: `0x14008387c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400833e4`

## callees

- `0x140021d00`
- `0x1400832f0`
- `0x1400834c8`
- `0x140083884`
- `0x14008393c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400834f3`
- `ntoskrnl!wcschr` at `0x1400834f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400835aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400835ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400835aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400835ef`
- `ntoskrnl!_wcsnicmp` at `0x14008368c`
- `ntoskrnl!_wcsnicmp` at `0x140083705`
- `ntoskrnl!_wcsnicmp` at `0x14008368c`
- `ntoskrnl!_wcsnicmp` at `0x140083705`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083844`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083844`

## pseudocode

```c

```
