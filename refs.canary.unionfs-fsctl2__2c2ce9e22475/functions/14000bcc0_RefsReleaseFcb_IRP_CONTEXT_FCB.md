# RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)

- ea: `0x14000bcc0`
- end: `0x14000c053`
- name: `?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `915`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `89`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000ac94`
- `0x14000b324`
- `0x14009a350`
- `0x14009f6cc`
- `0x1400a1490`
- `0x1400a7f90`
- `0x1400b87a0`
- `0x1400d5b60`
- `0x1400d783c`
- `0x1400d8a14`
- `0x1400e785c`
- `0x1400e96c0`
- `0x1400f4428`
- `0x1400faef0`
- `0x1400fcaf0`
- `0x1400fd934`
- `0x1400fd9c4`
- `0x1400fe670`
- `0x140104a40`
- `0x14010ec14`
- `0x1402881c8`
- `0x140288990`
- `0x14028cc8c`
- `0x14028f01c`
- `0x140290854`
- `0x140290de0`
- `0x140291760`
- `0x140293194`
- `0x140295074`
- `0x1402959ec`
- `0x140295e5c`
- `0x140296eb0`
- `0x14029ac5c`
- `0x14029c098`
- `0x14029d218`
- `0x1402a1f34`
- `0x1402a22d0`
- `0x1402a7468`
- `0x1402a75ac`
- `0x1402a8820`
- `0x1402a90cc`
- `0x1402ad28c`
- `0x1402ae1a8`
- `0x1402b0720`
- `0x1402b1350`
- `0x1402b4840`
- `0x1402b5f3c`
- `0x1402b8cd0`
- `0x1402b9514`
- `0x1402b99d4`

## callees

- `0x14000bcc0`
- `0x1400c8644`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000bf70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000bf70`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000bebb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000bebb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000beca`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000beca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bf06`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bf06`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000bf12`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000bf12`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000bda8`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000bdf0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000bda8`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000bdf0`
- `ntoskrnl!ExReleaseFastResource` at `0x14000bdcf`
- `ntoskrnl!ExReleaseFastResource` at `0x14000be24`
- `ntoskrnl!ExReleaseFastResource` at `0x14000bdcf`
- `ntoskrnl!ExReleaseFastResource` at `0x14000be24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c042`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c042`

## pseudocode

```c

```
