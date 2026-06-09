# ndisInvokeDeviceReset(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,ulong,_NDIS_INVOKE_DEVICE_RESET *,_NDIS_MP_REFTAG)

- ea: `0x140090d4c`
- end: `0x140090e85`
- name: `?ndisInvokeDeviceReset@@YAJPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@KPEAU_NDIS_INVOKE_DEVICE_RESET@@W4_NDIS_MP_REFTAG@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, unsigned int, struct _NDIS_INVOKE_DEVICE_RESET *, enum _NDIS_MP_REFTAG)`
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
- `0x140090d4c`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140090da6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090e66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090da6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140090e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140090d82`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140090d82`

## pseudocode

```c

```
