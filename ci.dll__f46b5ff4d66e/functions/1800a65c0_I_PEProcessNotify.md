# I_PEProcessNotify

- ea: `0x1800a65c0`
- end: `0x1800a65ff`
- name: `I_PEProcessNotify`
- size: `63`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800a65c0`
- `0x1800a6608`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a65de`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a65de`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a65cf`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a65cf`

## pseudocode

```c

```
