# NdisOpenAdapterEx

- ea: `0x1401829a0`
- end: `0x140183281`
- name: `NdisOpenAdapterEx`
- size: `2273`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisProtocolHandle, NDIS_HANDLE ProtocolBindingContext, PNDIS_OPEN_PARAMETERS OpenParameters, NDIS_HANDLE BindContext, PNDIS_HANDLE NdisBindingHandle)`
- caller_count: `0`
- callee_count: `32`
- tags: `broker_com_uri`

## callees

- `0x14001cc80`
- `0x14001cf50`
- `0x14001d030`
- `0x140029620`
- `0x14002b980`
- `0x140036a70`
- `0x14003d920`
- `0x1400472e0`
- `0x14004e050`
- `0x14004ee10`
- `0x140053fe0`
- `0x14005a5c0`
- `0x14005b1f0`
- `0x140063630`
- `0x140066ef0`
- `0x14007f2f0`
- `0x14007f480`
- `0x140083b50`
- `0x1400873e0`
- `0x14008e2e8`
- `0x140097df4`
- `0x1400b6e2c`
- `0x1400e6240`
- `0x1401461ac`
- `0x140157dc0`
- `0x140163350`
- `0x140163cc0`
- `0x140164280`
- `0x140168a90`
- `0x140178f70`
- `0x140179270`
- `0x1401829a0`

## import_xrefs

- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140182da6`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140182dea`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140182da6`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140182dea`
- `ntoskrnl!ExAllocatePool2` at `0x140182fc6`
- `ntoskrnl!ExAllocatePool2` at `0x140182fc6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140182e4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183079`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183266`
- `ntoskrnl!KeReleaseSpinLock` at `0x140182e4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183079`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140182e1a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140182e5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018322d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140182e1a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140182e5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018322d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140182eab`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140182eab`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140182ecc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140182ecc`
- `HAL!KeStallExecutionProcessor` at `0x140182ebc`
- `HAL!KeStallExecutionProcessor` at `0x140182ebc`

## pseudocode

```c

```
