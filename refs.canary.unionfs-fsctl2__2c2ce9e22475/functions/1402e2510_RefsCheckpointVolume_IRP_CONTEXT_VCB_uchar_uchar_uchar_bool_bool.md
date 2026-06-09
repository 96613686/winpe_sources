# RefsCheckpointVolume(_IRP_CONTEXT *,_VCB *,uchar,uchar,uchar,bool *,bool *)

- ea: `0x1402e2510`
- end: `0x1402e2d44`
- name: `?RefsCheckpointVolume@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEEPEA_N2@Z`
- size: `2100`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _VCB *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, char, bool *, bool *)`
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x14028c1bc`
- `0x1402961f4`
- `0x1402c207c`
- `0x1402d30ec`
- `0x1403389e4`

## callees

- `0x140081670`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008fc50`
- `0x14009b130`
- `0x1400b0f74`
- `0x1400ca788`
- `0x1400cd404`
- `0x14011552c`
- `0x140115e50`
- `0x1401e9cc4`
- `0x1401e9ce0`
- `0x1402e2510`
- `0x14031ac80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1402e2cdc`
- `ntoskrnl!KeSetEvent` at `0x140346557`
- `ntoskrnl!KeSetEvent` at `0x1402e2cdc`
- `ntoskrnl!KeSetEvent` at `0x140346557`
- `ntoskrnl!KeResetEvent` at `0x1402e282b`
- `ntoskrnl!KeResetEvent` at `0x1402e282b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e25b6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2790`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2bd8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2cae`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140346528`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e25b6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2790`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2bd8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e2cae`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140346528`
- `ntoskrnl!KeReadStateEvent` at `0x1402e27bc`
- `ntoskrnl!KeReadStateEvent` at `0x1402e27bc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e25c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e27a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e2bee`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e2cc4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034653f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e25c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e27a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e2bee`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e2cc4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034653f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e25ec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e27cf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e283a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e2c04`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e2ceb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034656a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e25ec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e27cf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e283a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e2c04`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e2ceb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034656a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e25f8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e27db`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2846`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2c10`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2cf7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140346576`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e25f8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e27db`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2846`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2c10`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e2cf7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140346576`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e280b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e2918`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e280b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e2918`
- `ntoskrnl!KeInitializeEvent` at `0x1402e2864`
- `ntoskrnl!KeInitializeEvent` at `0x1402e2864`

## pseudocode

```c

```
