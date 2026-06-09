# I_PEProcessNotify

- ea: `0x1800a7a40`
- end: `0x1800a7a7f`
- name: `I_PEProcessNotify`
- size: `63`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800a7a40`
- `0x1800a7a88`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a7a5e`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a7a5e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a7a4f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a7a4f`

## pseudocode

```c

```
