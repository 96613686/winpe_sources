# UlQuerySecurity

- ea: `0x140130790`
- end: `0x14013081c`
- name: `UlQuerySecurity`
- size: `140`
- prototype: `__int64 __fastcall(PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR SecurityDescriptor, PULONG Length, PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cd398`

## import_xrefs

- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1401307e0`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x1401307e0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140130804`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140130804`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401307f3`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401307f3`
- `ntoskrnl!SeLockSubjectContext` at `0x1401307c8`
- `ntoskrnl!SeLockSubjectContext` at `0x1401307c8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401307b7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401307b7`

## pseudocode

```c

```
