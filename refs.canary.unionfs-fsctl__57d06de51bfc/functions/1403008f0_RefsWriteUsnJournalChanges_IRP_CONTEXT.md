# RefsWriteUsnJournalChanges(_IRP_CONTEXT *)

- ea: `0x1403008f0`
- end: `0x140300f5c`
- name: `?RefsWriteUsnJournalChanges@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `1644`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `15`
- callee_count: `13`
- tags: ``

## callers

- `0x1400815e0`
- `0x140291760`
- `0x1402a7204`
- `0x1402a75ac`
- `0x1402c2478`
- `0x1402c2af4`
- `0x1402fec90`
- `0x1403000b0`
- `0x140300f70`
- `0x140301810`
- `0x140308620`
- `0x14030cbe0`
- `0x140314de0`
- `0x1403294a0`
- `0x140332ea0`

## callees

- `0x140010d40`
- `0x1400548b0`
- `0x140081670`
- `0x14008dbd0`
- `0x14009f140`
- `0x1400ac7d4`
- `0x1400ae14c`
- `0x1400aff30`
- `0x1400ca788`
- `0x140114b2c`
- `0x1403008f0`
- `0x140302620`
- `0x140335b2c`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140300a3f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140300a3f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300a63`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300bb2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033ece3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300a63`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140300bb2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033ece3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140300a73`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140300bc2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033ecf3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140300a73`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140300bc2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033ecf3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300a98`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300b6f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300bea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ed10`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300a98`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300b6f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140300bea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ed10`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300aa4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300b7b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300bf6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ed1c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300aa4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300b7b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140300bf6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ed1c`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140300a1f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140300a1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300ed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300f08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300f1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ed86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ed9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300ed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300f08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140300f1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ed86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ed9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300d53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300d7e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300d53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140300d7e`

## pseudocode

```c

```
