# NdisCmCloseCallComplete

- ea: `0x1400d07b0`
- end: `0x1400d0939`
- name: `NdisCmCloseCallComplete`
- size: `393`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, NDIS_HANDLE NdisPartyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400d03d0`

## callees

- `0x14001cf50`
- `0x140036610`
- `0x1400d07b0`
- `0x1400d0d00`
- `0x1400d10c0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d089b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d089b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d087d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d08c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d087d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d08c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0821`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0821`

## pseudocode

```c

```
