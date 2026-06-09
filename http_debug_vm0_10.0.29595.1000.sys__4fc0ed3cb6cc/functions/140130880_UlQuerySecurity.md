# UlQuerySecurity

- ea: `0x140130880`
- end: `0x14013090c`
- name: `UlQuerySecurity`
- size: `140`
- prototype: `__int64 __fastcall(PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR SecurityDescriptor, PULONG Length, PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cd2b8`

## import_xrefs

- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1401308d0`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1401308d0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401308f4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401308f4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401308e3`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401308e3`
- `ntoskrnl!SeLockSubjectContext` at `0x1401308b8`
- `ntoskrnl!SeLockSubjectContext` at `0x1401308b8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401308a7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401308a7`

## pseudocode

```c

```
