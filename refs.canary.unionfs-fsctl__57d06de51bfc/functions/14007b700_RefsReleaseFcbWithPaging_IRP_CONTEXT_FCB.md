# RefsReleaseFcbWithPaging(_IRP_CONTEXT *,_FCB *)

- ea: `0x14007b700`
- end: `0x14007bb3e`
- name: `?RefsReleaseFcbWithPaging@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1086`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `21`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400d6ee4`
- `0x1400e64e4`
- `0x1400eb1ac`
- `0x1400f1330`
- `0x1400f6f00`
- `0x1400faea4`
- `0x140104a40`
- `0x1402915d4`
- `0x1402a9d08`
- `0x1402ad9cc`
- `0x1402b3dac`
- `0x1402bd964`
- `0x1402c3810`
- `0x1402fb270`
- `0x1402fc810`
- `0x140301810`
- `0x14030a1a0`
- `0x140323f70`
- `0x140328060`
- `0x140336b00`
- `0x14033a130`

## callees

- `0x14007b700`
- `0x1400c8644`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007ba37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007ba37`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007b982`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007b982`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007b991`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007b991`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007b9cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007b9cd`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007b9d9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007b9d9`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14007b7fb`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14007b7fb`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b764`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b822`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b8d8`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b764`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b822`
- `ntoskrnl!ExReleaseFastResource` at `0x14007b8d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b772`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007bb2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b772`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007bb2d`

## pseudocode

```c

```
