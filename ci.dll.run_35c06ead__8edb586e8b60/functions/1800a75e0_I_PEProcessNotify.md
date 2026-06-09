# I_PEProcessNotify

- ea: `0x1800a75e0`
- end: `0x1800a761f`
- name: `I_PEProcessNotify`
- size: `63`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800a75e0`
- `0x1800a7628`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a75fe`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a75fe`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a75ef`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a75ef`

## pseudocode

```c

```
