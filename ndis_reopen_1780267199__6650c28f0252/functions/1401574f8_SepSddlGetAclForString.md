# SepSddlGetAclForString

- ea: `0x1401574f8`
- end: `0x1401578ac`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140157414`

## callees

- `0x1400eb7c0`
- `0x140157320`
- `0x1401574f8`
- `0x1401578b4`
- `0x14015796c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401575da`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015761f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401575da`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015761f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157874`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157874`
- `ntoskrnl!wcschr` at `0x140157523`
- `ntoskrnl!wcschr` at `0x140157523`
- `ntoskrnl!_wcsnicmp` at `0x1401576bc`
- `ntoskrnl!_wcsnicmp` at `0x140157735`
- `ntoskrnl!_wcsnicmp` at `0x1401576bc`
- `ntoskrnl!_wcsnicmp` at `0x140157735`

## pseudocode

```c

```
