# ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)

- ea: `0x1400733f0`
- end: `0x14007355c`
- name: `?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z`
- size: `364`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400825c8`
- `0x14009dc4c`

## callees

- `0x14001cc80`
- `0x14003d920`
- `0x1400733f0`
- `0x140082894`
- `0x1400837ac`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14007345a`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14007345a`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007350c`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007350c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007346d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007346d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140073430`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400734f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140073430`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400734f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073406`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073489`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073406`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073489`

## pseudocode

```c

```
