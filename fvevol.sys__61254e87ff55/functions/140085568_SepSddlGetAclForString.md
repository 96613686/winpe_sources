# SepSddlGetAclForString

- ea: `0x140085568`
- end: `0x14008591c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140085484`

## callees

- `0x140023040`
- `0x140085390`
- `0x140085568`
- `0x140085924`
- `0x1400859dc`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140085593`
- `ntoskrnl!wcschr` at `0x140085593`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008564a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008568f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008564a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008568f`
- `ntoskrnl!_wcsnicmp` at `0x14008572c`
- `ntoskrnl!_wcsnicmp` at `0x1400857a5`
- `ntoskrnl!_wcsnicmp` at `0x14008572c`
- `ntoskrnl!_wcsnicmp` at `0x1400857a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400858e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400858e4`

## pseudocode

```c

```
