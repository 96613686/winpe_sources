# RefsCompleteFileDeletion(_IRP_CONTEXT *,_FCB *,_SCB *,_CCB *,IndexSCB * &,_LCB * &,REFS_CLEANUP_FLAGS *)

- ea: `0x1402977e8`
- end: `0x140297ba9`
- name: `?RefsCompleteFileDeletion@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@PEAU_CCB@@AEAPEAUIndexSCB@@AEAPEAU_LCB@@PEAUREFS_CLEANUP_FLAGS@@@Z`
- size: `961`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _FCB *@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, struct IndexSCB **, struct _LCB **, struct REFS_CLEANUP_FLAGS *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1403058c0`
- `0x140319010`

## callees

- `0x140037820`
- `0x14008ad80`
- `0x140093bc0`
- `0x140095370`
- `0x1400a8498`
- `0x140114dc0`
- `0x14029764c`
- `0x14029770c`
- `0x1402977e8`
- `0x140302e10`
- `0x1403141f0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402978e2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140297a91`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034597f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402978e2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140297a91`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034597f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402978f1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140297aa0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034598e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402978f1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140297aa0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034598e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029791d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140297acc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403459be`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029791d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140297acc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403459be`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140297929`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140297ad8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403459ca`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140297929`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140297ad8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403459ca`

## pseudocode

```c

```
