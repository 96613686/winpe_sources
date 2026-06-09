# NdisClIncomingCallComplete

- ea: `0x1400d0520`
- end: `0x1400d0615`
- name: `NdisClIncomingCallComplete`
- size: `245`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, PCO_CALL_PARAMETERS CallParameters)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400d0960`

## callees

- `0x1400d0520`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d05cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d05b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d05b6`

## pseudocode

```c

```
