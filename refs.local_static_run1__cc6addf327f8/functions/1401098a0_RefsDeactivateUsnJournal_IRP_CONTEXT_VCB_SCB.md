# RefsDeactivateUsnJournal(_IRP_CONTEXT *,_VCB *,_SCB *)

- ea: `0x1401098a0`
- end: `0x140109d12`
- name: `?RefsDeactivateUsnJournal@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@@Z`
- size: `1138`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _VCB *, struct _SCB *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x140100070`
- `0x1402e765c`

## callees

- `0x140037820`
- `0x14004ffc0`
- `0x140071ba0`
- `0x1400894e0`
- `0x14008ad80`
- `0x140095370`
- `0x140096ed0`
- `0x1400abb88`
- `0x1401098a0`
- `0x140109d18`
- `0x1401f4400`
- `0x140294714`
- `0x1402e9b2c`
- `0x1403349ac`
- `0x140337814`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1401098fe`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140109bd3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1401098fe`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140109bd3`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140109971`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140109b61`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140109971`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140109b61`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14010990d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140109a02`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140109a30`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14010990d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140109a02`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140109a30`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109923`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109a12`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109a43`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109923`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109a12`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140109a43`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140109af8`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140109af8`
- `ntoskrnl!CcPurgeCacheSection` at `0x140109c38`
- `ntoskrnl!CcPurgeCacheSection` at `0x140109c38`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109937`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109a64`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109a8f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109937`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109a64`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140109a8f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109943`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109a70`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109a9b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109943`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109a70`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140109a9b`
- `ntoskrnl!ExReleaseFastResource` at `0x140109960`
- `ntoskrnl!ExReleaseFastResource` at `0x1401099b6`
- `ntoskrnl!ExReleaseFastResource` at `0x140109ba6`
- `ntoskrnl!ExReleaseFastResource` at `0x140109cea`
- `ntoskrnl!ExReleaseFastResource` at `0x140109960`
- `ntoskrnl!ExReleaseFastResource` at `0x1401099b6`
- `ntoskrnl!ExReleaseFastResource` at `0x140109ba6`
- `ntoskrnl!ExReleaseFastResource` at `0x140109cea`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14010998f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140109b7f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14010998f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140109b7f`

## pseudocode

```c

```
