# NdisMSendNetBufferListsComplete

- ea: `0x14003a6f0`
- end: `0x14003b285`
- name: `NdisMSendNetBufferListsComplete`
- size: `2965`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, PNET_BUFFER_LIST NetBufferList, ULONG SendCompleteFlags)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400639a0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x14002aa30`
- `0x140032cb0`
- `0x14003a2d0`
- `0x14003a6f0`
- `0x14003b290`
- `0x14003bc50`
- `0x140088a2c`
- `0x1400a4d24`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14003af3a`
- `ntoskrnl!KeLowerIrql` at `0x14003af3a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a843`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003acf8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003ad51`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a843`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003acf8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003ad51`
- `ntoskrnl!MmBadPointer` at `0x1400ef228`
- `ntoskrnl!KfRaiseIrql` at `0x14003b06b`
- `ntoskrnl!KfRaiseIrql` at `0x14003b06b`
- `ntoskrnl!IoGetStackLimits` at `0x14003ae40`
- `ntoskrnl!IoGetStackLimits` at `0x14003ae40`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003afb2`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003afb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a79e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b02d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a79e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b02d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a773`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003afda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a773`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003afda`

## pseudocode

```c

```
