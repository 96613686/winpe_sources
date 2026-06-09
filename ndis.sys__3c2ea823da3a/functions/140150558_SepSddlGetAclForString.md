# SepSddlGetAclForString

- ea: `0x140150558`
- end: `0x14015090c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140150474`

## callees

- `0x1400e65c0`
- `0x140150380`
- `0x140150558`
- `0x140150914`
- `0x1401509cc`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015063a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015067f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015063a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015067f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401508d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401508d4`
- `ntoskrnl!wcschr` at `0x140150583`
- `ntoskrnl!wcschr` at `0x140150583`
- `ntoskrnl!_wcsnicmp` at `0x14015071c`
- `ntoskrnl!_wcsnicmp` at `0x140150795`
- `ntoskrnl!_wcsnicmp` at `0x14015071c`
- `ntoskrnl!_wcsnicmp` at `0x140150795`

## pseudocode

```c

```
