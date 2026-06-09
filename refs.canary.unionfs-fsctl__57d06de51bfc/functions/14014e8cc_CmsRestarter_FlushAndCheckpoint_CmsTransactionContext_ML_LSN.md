# CmsRestarter::FlushAndCheckpoint(CmsTransactionContext *,_ML_LSN)

- ea: `0x14014e8cc`
- end: `0x14014ebbc`
- name: `?FlushAndCheckpoint@CmsRestarter@@AEAAJPEAVCmsTransactionContext@@T_ML_LSN@@@Z`
- size: `752`
- prototype: `int __high(struct CmsTransactionContext *, union _ML_LSN)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140153770`
- `0x140153df8`

## callees

- `0x1400340e0`
- `0x1400823f8`
- `0x14008d240`
- `0x14014d168`
- `0x14014d324`
- `0x14014d954`
- `0x14014e8cc`
- `0x1401553fc`
- `0x140155654`
- `0x140172840`
- `0x140173040`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14014e940`
- `ntoskrnl!IoGetActivityIdThread` at `0x14014eb59`
- `ntoskrnl!IoGetActivityIdThread` at `0x14014e940`
- `ntoskrnl!IoGetActivityIdThread` at `0x14014eb59`
- `ntoskrnl!KeSetEvent` at `0x14014e982`
- `ntoskrnl!KeSetEvent` at `0x14014e99a`
- `ntoskrnl!KeSetEvent` at `0x14014e982`
- `ntoskrnl!KeSetEvent` at `0x14014e99a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014ea49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014ea49`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014ea5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014ea5a`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14014e90d`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14014e90d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014ea33`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014ea33`

## pseudocode

```c

```
