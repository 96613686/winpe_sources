# NdisOpenAdapterEx

- ea: `0x140188970`
- end: `0x140189251`
- name: `NdisOpenAdapterEx`
- size: `2273`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisProtocolHandle, NDIS_HANDLE ProtocolBindingContext, PNDIS_OPEN_PARAMETERS OpenParameters, NDIS_HANDLE BindContext, PNDIS_HANDLE NdisBindingHandle)`
- caller_count: `0`
- callee_count: `32`
- tags: `broker_com_uri`

## callees

- `0x140005840`
- `0x140010d20`
- `0x1400110b0`
- `0x140011190`
- `0x14001fa30`
- `0x14002ab60`
- `0x1400400d0`
- `0x14004bc60`
- `0x140053280`
- `0x140054500`
- `0x140059200`
- `0x14005eaa0`
- `0x14005f7e0`
- `0x140068a00`
- `0x14006ca10`
- `0x140084b80`
- `0x140084d00`
- `0x140088dd0`
- `0x14008c6d0`
- `0x140092d28`
- `0x14009d074`
- `0x1400bc25c`
- `0x1400eb460`
- `0x14014d14c`
- `0x14015ed60`
- `0x14016a2e0`
- `0x14016ac50`
- `0x14016b210`
- `0x14016f980`
- `0x14017ef40`
- `0x14017f240`
- `0x140188970`

## import_xrefs

- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140188d76`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140188dba`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140188d76`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x140188dba`
- `ntoskrnl!ExAllocatePool2` at `0x140188f96`
- `ntoskrnl!ExAllocatePool2` at `0x140188f96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140188e1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140189049`
- `ntoskrnl!KeReleaseSpinLock` at `0x140189236`
- `ntoskrnl!KeReleaseSpinLock` at `0x140188e1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140189049`
- `ntoskrnl!KeReleaseSpinLock` at `0x140189236`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188dea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188e2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401891fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188dea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188e2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401891fd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140188e9c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140188e9c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140188e7b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140188e7b`
- `HAL!KeStallExecutionProcessor` at `0x140188e8c`
- `HAL!KeStallExecutionProcessor` at `0x140188e8c`

## pseudocode

```c

```
