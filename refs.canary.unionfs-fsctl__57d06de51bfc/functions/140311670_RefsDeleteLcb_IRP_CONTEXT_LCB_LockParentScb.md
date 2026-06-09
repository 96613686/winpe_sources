# RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)

- ea: `0x140311670`
- end: `0x14031197c`
- name: `?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z`
- size: `780`
- prototype: `void __high(struct _IRP_CONTEXT *, struct _LCB *, enum LockParentScb)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400fd934`
- `0x1403040a0`
- `0x140310460`
- `0x14031c960`
- `0x14033d970`

## callees

- `0x14008f870`
- `0x1400c8644`
- `0x140311670`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403117e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14031181b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403117e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14031181b`
- `ntoskrnl!KdDebuggerEnabled` at `0x14031192e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403118c2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403118c2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311882`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311882`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403118d1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403118d1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403118fe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403118fe`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031190a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031190a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403117a0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403117a0`

## pseudocode

```c

```
