# RefsDeleteUsnJournal(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402e765c`
- end: `0x1402e7d9d`
- name: `?RefsDeleteUsnJournal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `1857`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140323dd8`

## callees

- `0x14000e0e0`
- `0x14007cdb0`
- `0x140085570`
- `0x1400862c0`
- `0x1400a6f70`
- `0x1400adddc`
- `0x1400d0fd8`
- `0x1401098a0`
- `0x14028debc`
- `0x1402e765c`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e7ab7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e7b1f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e7ab7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e7b1f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e7aca`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e7b32`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e7aca`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e7b32`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402e76d9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402e76d9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7c58`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7c84`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140349594`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7c58`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7c84`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140349594`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e7c64`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e7c90`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403495a0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e7c64`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e7c90`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403495a0`

## pseudocode

```c

```
