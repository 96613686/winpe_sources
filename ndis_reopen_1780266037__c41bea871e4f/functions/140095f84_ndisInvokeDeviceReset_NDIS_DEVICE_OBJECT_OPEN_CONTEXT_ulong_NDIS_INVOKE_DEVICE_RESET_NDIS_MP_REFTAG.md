# ndisInvokeDeviceReset(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,ulong,_NDIS_INVOKE_DEVICE_RESET *,_NDIS_MP_REFTAG)

- ea: `0x140095f84`
- end: `0x1400960bd`
- name: `?ndisInvokeDeviceReset@@YAJPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@KPEAU_NDIS_INVOKE_DEVICE_RESET@@W4_NDIS_MP_REFTAG@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, unsigned int, struct _NDIS_INVOKE_DEVICE_RESET *, enum _NDIS_MP_REFTAG)`
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
- `0x140095f84`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140095fde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140096036`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009609e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140095fde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140096036`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009609e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140095fba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140095fba`

## pseudocode

```c

```
