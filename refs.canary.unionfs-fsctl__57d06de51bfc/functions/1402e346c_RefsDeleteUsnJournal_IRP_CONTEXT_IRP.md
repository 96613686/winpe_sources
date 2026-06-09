# RefsDeleteUsnJournal(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402e346c`
- end: `0x1402e3bad`
- name: `?RefsDeleteUsnJournal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `1857`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140320e78`

## callees

- `0x140041b40`
- `0x140087ee0`
- `0x14008c400`
- `0x14008dbd0`
- `0x1400abbf4`
- `0x1400b1dfc`
- `0x1400ca788`
- `0x140104a40`
- `0x140286ebc`
- `0x1402e346c`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e38c7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e392f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e38c7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e392f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e38da`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e3942`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e38da`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e3942`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402e34e9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402e34e9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e3a68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e3a94`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140346651`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e3a68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e3a94`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140346651`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e3a74`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e3aa0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14034665d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e3a74`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e3aa0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14034665d`

## pseudocode

```c

```
