# ndisReferenceProtocolByName(_UNICODE_STRING const *,_NDIS_PROTOCOL_BLOCK * *,uchar,_NDIS_PT_REFTAG)

- ea: `0x14017b070`
- end: `0x14017b23a`
- name: `?ndisReferenceProtocolByName@@YAJPEBU_UNICODE_STRING@@PEAPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _NDIS_PROTOCOL_BLOCK **, unsigned __int8, enum _NDIS_PT_REFTAG)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a5668`
- `0x140179a68`

## callees

- `0x1400114b0`
- `0x140059c80`
- `0x14005f7e0`
- `0x1400ebce0`
- `0x14017b070`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14017b124`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14017b124`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017b1d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017b1d6`
- `ntoskrnl!ExAllocatePool2` at `0x14017b0f1`
- `ntoskrnl!ExAllocatePool2` at `0x14017b0f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017b1c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017b1c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017b137`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017b137`

## pseudocode

```c

```
