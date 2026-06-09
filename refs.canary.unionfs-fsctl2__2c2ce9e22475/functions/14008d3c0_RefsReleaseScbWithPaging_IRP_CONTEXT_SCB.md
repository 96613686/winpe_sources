# RefsReleaseScbWithPaging(_IRP_CONTEXT *,_SCB *)

- ea: `0x14008d3c0`
- end: `0x14008d7f5`
- name: `?RefsReleaseScbWithPaging@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@@Z`
- size: `1077`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140295074`
- `0x1402fc810`
- `0x140314de0`
- `0x14033a130`

## callees

- `0x14008d3c0`
- `0x1400c8644`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008d710`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008d710`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14008d65b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14008d65b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14008d66a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14008d66a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14008d6a6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14008d6a6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14008d6b2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14008d6b2`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14008d4bf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14008d4bf`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d428`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d4e6`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d59c`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d428`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d4e6`
- `ntoskrnl!ExReleaseFastResource` at `0x14008d59c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d436`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d7e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d436`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d7e4`

## pseudocode

```c

```
