# RefsReleaseAllExclusiveFcbs(_IRP_CONTEXT &,_FCB *)

- ea: `0x140077f00`
- end: `0x140078381`
- name: `?RefsReleaseAllExclusiveFcbs@@YAXAEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1153`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1402a75ac`
- `0x140301810`
- `0x1403321d8`
- `0x140332ea0`
- `0x14033b490`

## callees

- `0x140077f00`
- `0x1400c8644`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078246`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078246`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140078184`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140078184`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078193`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140078193`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400781d3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400781d3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400781df`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400781df`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140078045`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400780a0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140078045`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400780a0`
- `ntoskrnl!ExReleaseFastResource` at `0x14007806c`
- `ntoskrnl!ExReleaseFastResource` at `0x1400780dc`
- `ntoskrnl!ExReleaseFastResource` at `0x14007806c`
- `ntoskrnl!ExReleaseFastResource` at `0x1400780dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078370`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078370`

## pseudocode

```c

```
