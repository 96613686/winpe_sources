# RefsDeactivateUsnJournal(_IRP_CONTEXT *,_VCB *,_SCB *)

- ea: `0x140104a40`
- end: `0x140104eb2`
- name: `?RefsDeactivateUsnJournal@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@@Z`
- size: `1138`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _VCB *, struct _SCB *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1400fb1b0`
- `0x1402e346c`

## callees

- `0x140008c10`
- `0x14000bcc0`
- `0x140038f80`
- `0x14007b700`
- `0x14008faf0`
- `0x1400913a0`
- `0x14009bb80`
- `0x1400b0128`
- `0x140104a40`
- `0x140104eb8`
- `0x1401ea140`
- `0x14028d780`
- `0x1402e593c`
- `0x140332cec`
- `0x140335b2c`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140104a9e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140104d73`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140104a9e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140104d73`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140104b11`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140104d01`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140104b11`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140104d01`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104aad`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104ba2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104bd0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104aad`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104ba2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140104bd0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104ac3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104bb2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104be3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104ac3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104bb2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140104be3`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140104c98`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140104c98`
- `ntoskrnl!CcPurgeCacheSection` at `0x140104dd8`
- `ntoskrnl!CcPurgeCacheSection` at `0x140104dd8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104c04`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104c2f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104c04`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140104c2f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104ae3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104c10`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104c3b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104ae3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104c10`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140104c3b`
- `ntoskrnl!ExReleaseFastResource` at `0x140104b00`
- `ntoskrnl!ExReleaseFastResource` at `0x140104b56`
- `ntoskrnl!ExReleaseFastResource` at `0x140104d46`
- `ntoskrnl!ExReleaseFastResource` at `0x140104e8a`
- `ntoskrnl!ExReleaseFastResource` at `0x140104b00`
- `ntoskrnl!ExReleaseFastResource` at `0x140104b56`
- `ntoskrnl!ExReleaseFastResource` at `0x140104d46`
- `ntoskrnl!ExReleaseFastResource` at `0x140104e8a`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140104b2f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140104d1f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140104b2f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140104d1f`

## pseudocode

```c

```
