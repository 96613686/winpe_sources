# ndisQueryDeviceReset(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,ulong,ulong,uint *,_NDIS_QUERY_DEVICE_RESET *)

- ea: `0x1400960c4`
- end: `0x140096206`
- name: `?ndisQueryDeviceReset@@YAJPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@KKPEAIPEAU_NDIS_QUERY_DEVICE_RESET@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, unsigned int, unsigned int, unsigned int *, struct _NDIS_QUERY_DEVICE_RESET *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1401811f0`

## callees

- `0x140010d20`
- `0x140012610`
- `0x14001a3e0`
- `0x14003b290`
- `0x140043c30`
- `0x140049d30`
- `0x140088a2c`
- `0x1400960c4`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140096135`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009617b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140096198`
- `ntoskrnl!KeReleaseSpinLock` at `0x140096135`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009617b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140096198`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140096109`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140096109`

## pseudocode

```c

```
