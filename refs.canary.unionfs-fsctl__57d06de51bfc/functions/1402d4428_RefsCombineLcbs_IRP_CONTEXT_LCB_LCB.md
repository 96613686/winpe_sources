# RefsCombineLcbs(_IRP_CONTEXT &,_LCB *,_LCB *)

- ea: `0x1402d4428`
- end: `0x1402d4611`
- name: `?RefsCombineLcbs@@YAXAEAU_IRP_CONTEXT@@PEAU_LCB@@1@Z`
- size: `489`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _LCB *, struct _LCB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14031c960`

## callees

- `0x1400a7a10`
- `0x1400c8644`
- `0x1402d4428`
- `0x14031f610`
- `0x140324500`
- `0x140327670`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d4457`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d4538`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d4457`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d4538`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d4467`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d4548`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d4467`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d4548`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d450a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d45ad`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d450a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d45ad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d4516`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d45b9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d4516`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d45b9`

## pseudocode

```c

```
