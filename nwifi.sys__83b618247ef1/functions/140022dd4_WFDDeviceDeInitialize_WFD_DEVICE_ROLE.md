# WFDDeviceDeInitialize(_WFD_DEVICE_ROLE *)

- ea: `0x140022dd4`
- end: `0x140022f00`
- name: `?WFDDeviceDeInitialize@@YAXPEAU_WFD_DEVICE_ROLE@@@Z`
- size: `300`
- prototype: `void __fastcall(struct _WFD_DEVICE_ROLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140079e34`

## callees

- `0x14000d22c`
- `0x140022dd4`
- `0x140022f08`
- `0x140022fbc`
- `0x14007f56c`
- `0x14008a780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140022e71`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022e71`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022eb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022eb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ec7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022e48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022e48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022e14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022e14`

## pseudocode

```c

```
