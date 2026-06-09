# RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)

- ea: `0x1403158a0`
- end: `0x140315bac`
- name: `?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z`
- size: `780`
- prototype: `void __high(struct _IRP_CONTEXT *, struct _LCB *, enum LockParentScb)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1401027f4`
- `0x140307728`
- `0x140314690`
- `0x14031fa40`
- `0x1403407b0`

## callees

- `0x140089260`
- `0x1400cedec`
- `0x1403158a0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140315a13`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140315a4b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140315a13`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140315a4b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140315b5e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140315af2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140315af2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315ab2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315ab2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140315b01`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140315b01`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140315b2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140315b2e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140315b3a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140315b3a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403159d0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403159d0`

## pseudocode

```c

```
