# WFDDiscoverInvalidateCachedDevices(_ADAPT *)

- ea: `0x14005625c`
- end: `0x1400562ff`
- name: `?WFDDiscoverInvalidateCachedDevices@@YAHPEAU_ADAPT@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140055628`
- `0x140088270`

## callees

- `0x14005625c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400562a3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400562a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400562b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400562b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400562e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400562e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056273`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056273`

## pseudocode

```c

```
