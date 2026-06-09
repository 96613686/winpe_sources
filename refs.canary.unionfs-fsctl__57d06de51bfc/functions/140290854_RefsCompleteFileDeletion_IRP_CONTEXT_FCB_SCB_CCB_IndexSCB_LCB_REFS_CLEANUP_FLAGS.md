# RefsCompleteFileDeletion(_IRP_CONTEXT *,_FCB *,_SCB *,_CCB *,IndexSCB * &,_LCB * &,REFS_CLEANUP_FLAGS *)

- ea: `0x140290854`
- end: `0x140290c15`
- name: `?RefsCompleteFileDeletion@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@PEAU_CCB@@AEAPEAUIndexSCB@@AEAPEAU_LCB@@PEAUREFS_CLEANUP_FLAGS@@@Z`
- size: `961`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _FCB *@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, struct IndexSCB **, struct _LCB **, struct REFS_CLEANUP_FLAGS *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140301810`
- `0x140314de0`

## callees

- `0x140008c10`
- `0x14000bcc0`
- `0x1400913a0`
- `0x140099960`
- `0x1400ad0c8`
- `0x140110650`
- `0x1402906b8`
- `0x140290778`
- `0x140290854`
- `0x1402fec90`
- `0x14030ffc0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x14029094e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140290afd`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140342b10`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14029094e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140290afd`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140342b10`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029095d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140290b0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342b1f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029095d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140290b0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342b1f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140290989`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140290b38`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342b4f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140290989`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140290b38`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342b4f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290995`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290b44`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342b5b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290995`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140290b44`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342b5b`

## pseudocode

```c

```
