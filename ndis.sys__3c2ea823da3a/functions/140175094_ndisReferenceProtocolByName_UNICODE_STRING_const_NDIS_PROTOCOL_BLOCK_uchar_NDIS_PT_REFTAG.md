# ndisReferenceProtocolByName(_UNICODE_STRING const *,_NDIS_PROTOCOL_BLOCK * *,uchar,_NDIS_PT_REFTAG)

- ea: `0x140175094`
- end: `0x14017525e`
- name: `?ndisReferenceProtocolByName@@YAJPEBU_UNICODE_STRING@@PEAPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _NDIS_PROTOCOL_BLOCK **, unsigned __int8, enum _NDIS_PT_REFTAG)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a0228`
- `0x140173a68`

## callees

- `0x14001d350`
- `0x140054b80`
- `0x14005b1f0`
- `0x1400e6ae0`
- `0x140175094`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140175148`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140175148`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401751fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401751fa`
- `ntoskrnl!ExAllocatePool2` at `0x140175115`
- `ntoskrnl!ExAllocatePool2` at `0x140175115`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401751e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401751e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017515b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017515b`

## pseudocode

```c

```
