# NdisCmOpenAddressFamilyComplete

- ea: `0x140065ac0`
- end: `0x140065c67`
- name: `NdisCmOpenAddressFamilyComplete`
- size: `423`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisAfHandle, NDIS_HANDLE CallMgrAfContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400cf950`

## callees

- `0x14001cc80`
- `0x1400363f0`
- `0x140065ac0`
- `0x1400cf8d0`
- `0x1400d3320`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140065c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065c56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065b9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065c10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065b9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065c10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065b77`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065b77`

## pseudocode

```c

```
