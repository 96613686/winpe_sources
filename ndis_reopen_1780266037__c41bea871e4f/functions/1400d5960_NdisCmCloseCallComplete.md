# NdisCmCloseCallComplete

- ea: `0x1400d5960`
- end: `0x1400d5ae9`
- name: `NdisCmCloseCallComplete`
- size: `393`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, NDIS_HANDLE NdisPartyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400d5580`

## callees

- `0x1400053e0`
- `0x1400110b0`
- `0x1400d5960`
- `0x1400d5eb0`
- `0x1400d6270`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5a4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5a2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5a70`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5a2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d59d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d59d1`

## pseudocode

```c

```
