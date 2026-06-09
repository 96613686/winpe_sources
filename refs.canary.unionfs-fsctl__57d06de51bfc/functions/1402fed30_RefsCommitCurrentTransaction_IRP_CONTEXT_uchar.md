# RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)

- ea: `0x1402fed30`
- end: `0x1402ff164`
- name: `?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z`
- size: `1076`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned __int8)`
- caller_count: `16`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000fce0`
- `0x140041b40`
- `0x1400815e0`
- `0x1400a7f90`
- `0x1400e51d8`
- `0x140286acc`
- `0x140289084`
- `0x14028c1bc`
- `0x1402bf6f4`
- `0x1402d34ac`
- `0x1402e6f54`
- `0x1402fec90`
- `0x140300f70`
- `0x140308620`
- `0x14030cbe0`
- `0x1403294a0`

## callees

- `0x1400531a0`
- `0x140054b90`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e280`
- `0x1400c8644`
- `0x1400ca788`
- `0x1402fed30`
- `0x1402ff170`
- `0x140332394`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402feea9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402feec9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402feea9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402feec9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402feeb9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402feedc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402feeb9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402feedc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402fef20`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402fef40`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402fef20`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402fef40`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402fef2c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402fef4c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402fef2c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402fef4c`
- `ntoskrnl!ExReleaseFastResource` at `0x1402ff14c`
- `ntoskrnl!ExReleaseFastResource` at `0x1402ff14c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ff127`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ff127`

## pseudocode

```c

```
