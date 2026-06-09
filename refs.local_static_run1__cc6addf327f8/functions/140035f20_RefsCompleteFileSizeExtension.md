# RefsCompleteFileSizeExtension

- ea: `0x140035f20`
- end: `0x140036661`
- name: `RefsCompleteFileSizeExtension`
- size: `1857`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct DataSCB *@<rdx>, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035df0`
- `0x1400a2c60`
- `0x140328fd0`

## callees

- `0x140035da0`
- `0x140035f20`
- `0x140036670`
- `0x140037e00`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400a6f44`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x140302e10`
- `0x14032cb40`
- `0x140339780`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140036430`
- `ntoskrnl!KeDelayExecutionThread` at `0x140036430`
- `ntoskrnl!KeSetEvent` at `0x14003604d`
- `ntoskrnl!KeSetEvent` at `0x14003604d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003610c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003610c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003620d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003659c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401f4f36`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003620d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003659c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401f4f36`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003621c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400365ab`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f4f45`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003621c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400365ab`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f4f45`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036099`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036260`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036099`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036260`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400360a5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003626c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400360a5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003626c`

## pseudocode

```c

```
