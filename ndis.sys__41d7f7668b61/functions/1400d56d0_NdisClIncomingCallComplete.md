# NdisClIncomingCallComplete

- ea: `0x1400d56d0`
- end: `0x1400d57c5`
- name: `NdisClIncomingCallComplete`
- size: `245`
- prototype: `void __stdcall(NDIS_STATUS Status, NDIS_HANDLE NdisVcHandle, PCO_CALL_PARAMETERS CallParameters)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400d5b10`

## callees

- `0x1400d56d0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5756`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d577c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d5756`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d577c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d56f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5766`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d56f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d5766`

## pseudocode

```c

```
