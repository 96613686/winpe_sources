# ndisDereferenceProtocol(_NDIS_PROTOCOL_BLOCK *,uchar,_NDIS_PT_REFTAG)

- ea: `0x14005a5c0`
- end: `0x14005a684`
- name: `?ndisDereferenceProtocol@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z`
- size: `196`
- prototype: `void __fastcall(_NDIS_PROTOCOL_BLOCK *this, unsigned __int8, enum _NDIS_PT_REFTAG)`
- caller_count: `15`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400925e0`
- `0x1400a0228`
- `0x1400b6320`
- `0x1400b75c0`
- `0x1401416c8`
- `0x140155260`
- `0x140155b10`
- `0x14015c400`
- `0x1401642c0`
- `0x1401681a0`
- `0x14016a620`
- `0x140173a68`
- `0x140175270`
- `0x140176220`
- `0x1401829a0`

## callees

- `0x14001cf50`
- `0x1400208f0`
- `0x14005a5c0`
- `0x14005a690`
- `0x140087490`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400ec982`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ec982`
- `ntoskrnl!KeSetEvent` at `0x1400ec9e0`
- `ntoskrnl!KeSetEvent` at `0x1400ec9e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec9b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec9f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec9b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec9f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ec99e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ec99e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005a670`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005a670`

## pseudocode

```c

```
