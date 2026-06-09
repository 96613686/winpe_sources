# TxfActOnFile

- ea: `0x1401dc5e8`
- end: `0x1401dd5a9`
- name: `TxfActOnFile`
- size: `4033`
- prototype: `__int64 __fastcall(__int64, char *, int, int, int, CLFS_LSN *plsn1, __int64)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation`

## callers

- `0x1401d5ad0`
- `0x1401dc54c`
- `0x1402975c8`

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
- `0x140053080`
- `0x140100a0c`
- `0x14013ad80`
- `0x14013c2d0`
- `0x140140380`
- `0x140166514`
- `0x1401913d4`
- `0x140196e30`
- `0x14019a718`
- `0x1401ac080`
- `0x1401c00e0`
- `0x1401db164`
- `0x1401dc5e8`
- `0x1402013e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc6b4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc8f8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc6b4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401dc8f8`
- `ntoskrnl!KeReleaseMutex` at `0x1401dd2d7`
- `ntoskrnl!KeReleaseMutex` at `0x1401dd2d7`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1401dccb8`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1401dccb8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401dd488`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b0b35`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401dd488`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b0b35`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc7ea`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc993`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dca48`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd422`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd4a7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b0b59`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc7ea`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dc993`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dca48`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd422`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401dd4a7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b0b59`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dd04a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dd04a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401dd25a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401dd25a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dc7ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcab8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dce12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcecb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd159`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd270`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dc7ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcab8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dce12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dcecb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd159`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dd270`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dc7c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcd0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dce7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd176`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd4de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0b97`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dc7c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dcd0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dce7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd176`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401dd4de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0b97`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcba6`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcbd7`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dce44`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcba6`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dcbd7`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401dce44`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcfa0`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd0c9`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcfa0`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd0c9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401dd1a7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401dd1a7`

## pseudocode

```c

```
