# NdisCmMakeCallComplete

- ea: `0x1400d0a90`
- end: `0x1400d0cce`
- name: `NdisCmMakeCallComplete`
- size: `574`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, NDIS_HANDLE NdisPartyHandle, NDIS_HANDLE CallMgrPartyContext, PCO_CALL_PARAMETERS CallParameters)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400d0620`

## callees

- `0x140028e00`
- `0x140029620`
- `0x140036610`
- `0x14007bd00`
- `0x1400d0a90`
- `0x1400d0d00`
- `0x1400d10c0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0c11`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0c11`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0bd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0bd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0b05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0b78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0b05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0b78`

## pseudocode

```c

```
