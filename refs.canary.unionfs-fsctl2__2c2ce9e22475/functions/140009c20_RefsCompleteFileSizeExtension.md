# RefsCompleteFileSizeExtension

- ea: `0x140009c20`
- end: `0x14000a361`
- name: `RefsCompleteFileSizeExtension`
- size: `1857`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct DataSCB *@<rdx>, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009af0`
- `0x1400a7f90`
- `0x140325c50`

## callees

- `0x140009aa0`
- `0x140009c20`
- `0x14000a370`
- `0x14000a500`
- `0x140081670`
- `0x14008dbd0`
- `0x1400abbc8`
- `0x1400c8644`
- `0x1400ca788`
- `0x1402fec90`
- `0x14032b940`
- `0x140337a98`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14000a130`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000a130`
- `ntoskrnl!KeSetEvent` at `0x140009d4d`
- `ntoskrnl!KeSetEvent` at `0x140009d4d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140009e0c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140009e0c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140009f0d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000a29c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401ea796`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140009f0d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000a29c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401ea796`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140009f1c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a2ab`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401ea7a5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140009f1c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a2ab`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401ea7a5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009d99`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009f60`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009d99`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009f60`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140009da5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140009f6c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140009da5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140009f6c`

## pseudocode

```c

```
