# CClfsManagedLog::InstallPolicy(_CLFS_MGMT_POLICY *,ulong)

- ea: `0x14006eed4`
- end: `0x14006f143`
- name: `?InstallPolicy@CClfsManagedLog@@QEAAJPEAU_CLFS_MGMT_POLICY@@K@Z`
- size: `623`
- prototype: `__int64 __fastcall(CClfsManagedLog *__hidden this, struct _CLFS_MGMT_POLICY *Src, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14006ec04`
- `0x14006ee10`

## callees

- `0x140017f80`
- `0x140033ea8`
- `0x14005d5f0`
- `0x14006eed4`
- `0x14006f14c`
- `0x140074754`
- `0x14007487c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006ef40`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006ef40`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ef9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f0d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f0e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ef9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f0d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f0e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f0f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f0f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006ef82`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006ef82`

## pseudocode

```c

```
