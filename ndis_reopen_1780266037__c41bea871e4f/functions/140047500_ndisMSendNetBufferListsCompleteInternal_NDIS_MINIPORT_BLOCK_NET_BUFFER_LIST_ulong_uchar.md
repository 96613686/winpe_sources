# ndisMSendNetBufferListsCompleteInternal(_NDIS_MINIPORT_BLOCK *,_NET_BUFFER_LIST *,ulong,uchar)

- ea: `0x140047500`
- end: `0x140047ea1`
- name: `?ndisMSendNetBufferListsCompleteInternal@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_BUFFER_LIST@@KE@Z`
- size: `2465`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NET_BUFFER_LIST *, unsigned int, unsigned __int8)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400335f0`
- `0x140036190`
- `0x14003bd20`
- `0x14003c160`
- `0x14003cec0`
- `0x140053620`
- `0x140053710`
- `0x1400c759c`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x140047500`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140047bb7`
- `ntoskrnl!KeLowerIrql` at `0x140047bb7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400475c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400479c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140047a1e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400475c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400479c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140047a1e`
- `ntoskrnl!KfRaiseIrql` at `0x140047ce4`
- `ntoskrnl!KfRaiseIrql` at `0x140047ce4`
- `ntoskrnl!IoGetStackLimits` at `0x140047ac1`
- `ntoskrnl!IoGetStackLimits` at `0x140047ac1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140047c2f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140047c2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140047ca6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140047ca6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140047c57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140047c57`

## pseudocode

```c

```
