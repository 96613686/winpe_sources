# RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)

- ea: `0x140302eb0`
- end: `0x1403032e4`
- name: `?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z`
- size: `1076`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned __int8)`
- caller_count: `16`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000e0e0`
- `0x14002ba90`
- `0x140076a40`
- `0x1400a2c60`
- `0x1400ea220`
- `0x14028dacc`
- `0x140290034`
- `0x140293158`
- `0x1402c53f4`
- `0x1402d83ec`
- `0x1402eb144`
- `0x140302e10`
- `0x140305020`
- `0x1403066d0`
- `0x14030bca0`
- `0x1403115a0`

## callees

- `0x140047580`
- `0x140076ad0`
- `0x1400862c0`
- `0x140087380`
- `0x140089a80`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x140302eb0`
- `0x1403032f0`
- `0x140334054`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x140303029`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140303049`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140303029`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140303049`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140303039`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030305c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140303039`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030305c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403030a0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403030c0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403030a0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403030c0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403030ac`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403030cc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403030ac`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403030cc`
- `ntoskrnl!ExReleaseFastResource` at `0x1403032cc`
- `ntoskrnl!ExReleaseFastResource` at `0x1403032cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403032a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403032a7`

## pseudocode

```c

```
