# ndisDereferenceProtocol(_NDIS_PROTOCOL_BLOCK *,uchar,_NDIS_PT_REFTAG)

- ea: `0x14005eaa0`
- end: `0x14005eb64`
- name: `?ndisDereferenceProtocol@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z`
- size: `196`
- prototype: `void __fastcall(_NDIS_PROTOCOL_BLOCK *this, unsigned __int8, enum _NDIS_PT_REFTAG)`
- caller_count: `15`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140097860`
- `0x1400a5668`
- `0x1400bb750`
- `0x1400bc9f0`
- `0x140148668`
- `0x14015c200`
- `0x14015cab0`
- `0x1401633a0`
- `0x14016b250`
- `0x14016f090`
- `0x140171510`
- `0x140179a68`
- `0x14017b240`
- `0x14017c1f0`
- `0x140188970`

## callees

- `0x1400110b0`
- `0x140014a50`
- `0x14005eaa0`
- `0x14005eb70`
- `0x14008c780`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400f1902`
- `ntoskrnl!ObfDereferenceObject` at `0x1400f1902`
- `ntoskrnl!KeSetEvent` at `0x1400f1960`
- `ntoskrnl!KeSetEvent` at `0x1400f1960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1938`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1979`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1938`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1979`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400f191e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400f191e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005eb50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005eb50`

## pseudocode

```c

```
