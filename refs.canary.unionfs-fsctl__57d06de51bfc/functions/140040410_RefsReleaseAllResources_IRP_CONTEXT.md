# RefsReleaseAllResources(_IRP_CONTEXT *)

- ea: `0x140040410`
- end: `0x140040998`
- name: `?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `1416`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14003db90`
- `0x14003fe20`
- `0x140040b20`
- `0x14028c5d0`
- `0x1402aa028`
- `0x140308620`
- `0x14031c2b0`
- `0x140321a64`
- `0x140330af8`

## callees

- `0x140040410`
- `0x1400c8644`
- `0x140320020`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140040686`
- `ntoskrnl!KeSetEvent` at `0x140040686`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004082a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004082a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004063b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004076d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004063b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004076d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004064a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004077c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004064a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004077c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140040696`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400407ba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140040696`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400407ba`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400406a2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400407c6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400406a2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400407c6`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14004056d`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14004056d`
- `ntoskrnl!ExReleaseFastResource` at `0x140040590`
- `ntoskrnl!ExReleaseFastResource` at `0x1400405ec`
- `ntoskrnl!ExReleaseFastResource` at `0x1400406f4`
- `ntoskrnl!ExReleaseFastResource` at `0x14004096b`
- `ntoskrnl!ExReleaseFastResource` at `0x140040590`
- `ntoskrnl!ExReleaseFastResource` at `0x1400405ec`
- `ntoskrnl!ExReleaseFastResource` at `0x1400406f4`
- `ntoskrnl!ExReleaseFastResource` at `0x14004096b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040852`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040987`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040852`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040987`

## pseudocode

```c

```
