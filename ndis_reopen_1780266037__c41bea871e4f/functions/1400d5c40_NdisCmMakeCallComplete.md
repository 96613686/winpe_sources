# NdisCmMakeCallComplete

- ea: `0x1400d5c40`
- end: `0x1400d5e7e`
- name: `NdisCmMakeCallComplete`
- size: `574`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, NDIS_HANDLE NdisPartyHandle, NDIS_HANDLE CallMgrPartyContext, PCO_CALL_PARAMETERS CallParameters)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400d57d0`

## callees

- `0x1400053e0`
- `0x14001cf60`
- `0x14002ab60`
- `0x1400815f0`
- `0x1400d5c40`
- `0x1400d5eb0`
- `0x1400d6270`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5dc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5ce6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5d86`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5ce6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5d86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5d28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5d28`

## pseudocode

```c

```
