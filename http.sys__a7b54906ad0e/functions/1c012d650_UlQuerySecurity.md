# UlQuerySecurity

- ea: `0x1c012d650`
- end: `0x1c012d6f0`
- name: `UlQuerySecurity`
- size: `160`
- prototype: `__int64 __fastcall(PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR SecurityDescriptor, PULONG Length, PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0101738`

## import_xrefs

- `ntoskrnl!SeLockSubjectContext` at `0x1c012d690`
- `ntoskrnl!SeLockSubjectContext` at `0x1c012d690`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c012d6bb`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c012d6bb`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c012d67f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c012d67f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c012d6cc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c012d6cc`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1c012d6a8`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1c012d6a8`

## pseudocode

```c

```
