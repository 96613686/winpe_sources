# SepSddlGetAclForString

- ea: `0x140052f18`
- end: `0x1400532cc`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140052e34`

## callees

- `0x140018280`
- `0x140052d40`
- `0x140052f18`
- `0x1400532d4`
- `0x14005338c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140053294`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053294`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140052ffa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005303f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140052ffa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005303f`
- `ntoskrnl!wcschr` at `0x140052f43`
- `ntoskrnl!wcschr` at `0x140052f43`
- `ntoskrnl!_wcsnicmp` at `0x1400530dc`
- `ntoskrnl!_wcsnicmp` at `0x140053155`
- `ntoskrnl!_wcsnicmp` at `0x1400530dc`
- `ntoskrnl!_wcsnicmp` at `0x140053155`

## pseudocode

```c

```
