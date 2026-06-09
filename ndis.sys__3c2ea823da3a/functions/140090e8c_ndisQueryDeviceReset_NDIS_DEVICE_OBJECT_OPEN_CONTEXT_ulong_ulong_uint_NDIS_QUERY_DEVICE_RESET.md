# ndisQueryDeviceReset(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,ulong,ulong,uint *,_NDIS_QUERY_DEVICE_RESET *)

- ea: `0x140090e8c`
- end: `0x140090fce`
- name: `?ndisQueryDeviceReset@@YAJPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@KKPEAIPEAU_NDIS_QUERY_DEVICE_RESET@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, unsigned int, unsigned int, unsigned int *, struct _NDIS_QUERY_DEVICE_RESET *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14017b220`

## callees

- `0x140013830`
- `0x14001cc80`
- `0x14001e4b0`
- `0x140026280`
- `0x1400412b0`
- `0x140045230`
- `0x1400837ac`
- `0x140090e8c`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140090efd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090f43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090f60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090efd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090f43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090f60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140090ed1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140090ed1`

## pseudocode

```c

```
