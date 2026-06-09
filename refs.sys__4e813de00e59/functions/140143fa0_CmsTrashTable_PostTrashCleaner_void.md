# CmsTrashTable::PostTrashCleaner(void)

- ea: `0x140143fa0`
- end: `0x140144145`
- name: `?PostTrashCleaner@CmsTrashTable@@AEAAXXZ`
- size: `421`
- prototype: `void __fastcall(CmsTrashTable *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1400b27b8`
- `0x140143574`
- `0x14014414c`
- `0x1401441e4`
- `0x140144320`

## callees

- `0x140009e10`
- `0x1400801d0`
- `0x140088930`
- `0x14008e230`
- `0x140143fa0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x14014411d`
- `ntoskrnl!IoClearActivityIdThread` at `0x14014411d`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401440c6`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401440c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140144081`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140144081`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401440b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401440b0`
- `ntoskrnl!KeClearEvent` at `0x140144096`
- `ntoskrnl!KeClearEvent` at `0x140144096`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140143fe2`
- `ntoskrnl!ExAcquireFastResourceSharedStarveExclusive` at `0x140143fe2`
- `ntoskrnl!IoTransferActivityId` at `0x1401440df`
- `ntoskrnl!IoTransferActivityId` at `0x1401440f6`
- `ntoskrnl!IoTransferActivityId` at `0x1401440df`
- `ntoskrnl!IoTransferActivityId` at `0x1401440f6`

## pseudocode

```c

```
