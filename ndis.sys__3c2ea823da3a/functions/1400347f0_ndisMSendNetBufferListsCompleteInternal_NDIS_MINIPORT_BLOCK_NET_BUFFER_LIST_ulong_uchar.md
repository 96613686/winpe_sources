# ndisMSendNetBufferListsCompleteInternal(_NDIS_MINIPORT_BLOCK *,_NET_BUFFER_LIST *,ulong,uchar)

- ea: `0x1400347f0`
- end: `0x140034e0f`
- name: `?ndisMSendNetBufferListsCompleteInternal@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_BUFFER_LIST@@KE@Z`
- size: `1567`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NET_BUFFER_LIST *, unsigned int, unsigned __int8)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007080`
- `0x140007190`
- `0x140011570`
- `0x1400118a0`
- `0x140011b90`
- `0x140012580`
- `0x14002e700`
- `0x1400c216c`

## callees

- `0x14000a5a0`
- `0x14000de20`
- `0x1400347f0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140034ce0`
- `ntoskrnl!KfRaiseIrql` at `0x140034ce0`
- `ntoskrnl!KeLowerIrql` at `0x140034bef`
- `ntoskrnl!KeLowerIrql` at `0x140034bef`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400348b6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400348b6`
- `ntoskrnl!IoGetStackLimits` at `0x140034b30`
- `ntoskrnl!IoGetStackLimits` at `0x140034b30`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140034c50`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140034c50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034cc8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034cc8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034c78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034c78`

## pseudocode

```c

```
