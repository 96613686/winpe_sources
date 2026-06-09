# CClfsManagedLog::UninstallPolicy(_CLFS_MGMT_POLICY_TYPE)

- ea: `0x14005d5f0`
- end: `0x14005d6a7`
- name: `?UninstallPolicy@CClfsManagedLog@@QEAAJW4_CLFS_MGMT_POLICY_TYPE@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(CClfsManagedLog *__hidden this, enum _CLFS_MGMT_POLICY_TYPE)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140050bb0`
- `0x14005d52c`
- `0x14006eed4`

## callees

- `0x14005d5f0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d614`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d614`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d65a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d675`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d65a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d635`

## pseudocode

```c

```
