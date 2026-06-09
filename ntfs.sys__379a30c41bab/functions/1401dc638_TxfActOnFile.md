# TxfActOnFile

- ea: `0x1401dc638`
- end: `0x1401dd5f9`
- name: `TxfActOnFile`
- size: `4033`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, CLFS_LSN *plsn1, __int64)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation`

## callers

- `0x1401d5b20`
- `0x1401dc59c`
- `0x140297618`

## callees

- `0x140007ea0`
- `0x14000d1e0`
- `0x14000eaa0`
- `0x140010be0`
- `0x140012e70`
- `0x140017480`
- `0x14001c5c0`
- `0x140021590`
- `0x140029d80`
- `0x14002c3d0`
- `0x140034560`
- `0x14003b180`
- `0x1400530f0`
- `0x140100a5c`
- `0x14013add0`
- `0x14013c320`
- `0x1401403d0`
- `0x140166564`
- `0x140191424`
- `0x140196e80`
- `0x14019a768`
- `0x1401ac0d0`
- `0x1401c0130`
- `0x1401db1b4`
- `0x1401dc638`
- `0x140201430`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc704`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc948`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc704`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc948`
- `ntoskrnl!KeReleaseMutex` at `0x1401dd327`
- `ntoskrnl!KeReleaseMutex` at `0x1401dd327`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1401dcd08`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1401dcd08`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401dd4d8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b0b85`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401dd4d8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b0b85`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc83a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc9e3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dca98`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd472`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd4f7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b0ba9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc83a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc9e3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dca98`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd472`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd4f7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b0ba9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dd09a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dd09a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401dd2aa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401dd2aa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dc7fb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcb08`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dce62`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcf1b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd1a9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd2c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dc7fb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcb08`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dce62`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcf1b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd1a9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd2c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dc819`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcd5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcecb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd1c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd52e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0be7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dc819`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcd5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcecb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd1c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd52e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0be7`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcbf6`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcc27`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dce94`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcbf6`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcc27`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dce94`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcff0`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd119`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcff0`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd119`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401dd1f7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401dd1f7`

## pseudocode

```c

```
