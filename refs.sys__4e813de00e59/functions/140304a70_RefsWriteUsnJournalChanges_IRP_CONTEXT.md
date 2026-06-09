# RefsWriteUsnJournalChanges(_IRP_CONTEXT *)

- ea: `0x140304a70`
- end: `0x140305017`
- name: `?RefsWriteUsnJournalChanges@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `1447`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `15`
- callee_count: `12`
- tags: ``

## callers

- `0x140076a40`
- `0x1402986f0`
- `0x1402adf64`
- `0x1402ae30c`
- `0x1402c7d04`
- `0x1402c8380`
- `0x140302e10`
- `0x140304230`
- `0x140305020`
- `0x1403058c0`
- `0x1403066d0`
- `0x14030bca0`
- `0x1403115a0`
- `0x140319010`
- `0x140334b60`

## callees

- `0x14002b340`
- `0x14002b870`
- `0x140076ad0`
- `0x1400862c0`
- `0x140099d90`
- `0x1400a7d04`
- `0x1400ab888`
- `0x1400d0fd8`
- `0x140119f8c`
- `0x140304a70`
- `0x140326a70`
- `0x140337814`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140304cb8`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140304cb8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140304cdc`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140304e28`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341ca3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140304cdc`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140304e28`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341ca3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304cec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304e38`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341cb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304cec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304e38`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341cb3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304d0c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304dea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304e56`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341cd0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304d0c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304dea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304e56`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341cd0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304d18`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304df6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304e62`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341cdc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304d18`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304df6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304e62`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341cdc`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140304c98`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140304c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140304efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140304f17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341d5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140304efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140304f17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341d5f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304b15`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304b3d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304b15`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304b3d`

## pseudocode

```c

```
