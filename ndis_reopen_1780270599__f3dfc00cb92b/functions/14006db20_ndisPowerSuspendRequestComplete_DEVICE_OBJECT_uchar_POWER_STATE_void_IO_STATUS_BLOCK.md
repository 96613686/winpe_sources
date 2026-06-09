# ndisPowerSuspendRequestComplete(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *)

- ea: `0x14006db20`
- end: `0x14006ddad`
- name: `?ndisPowerSuspendRequestComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z`
- size: `653`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000dbe0`
- `0x140011190`
- `0x14003dec0`
- `0x1400416b0`
- `0x14006db20`
- `0x14006ddc0`
- `0x1400704f0`
- `0x14008bf70`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14006dbc6`
- `ntoskrnl!KeClearEvent` at `0x14006dbc6`
- `ntoskrnl!KeSetEvent` at `0x14006dbde`
- `ntoskrnl!KeSetEvent` at `0x14006dd83`
- `ntoskrnl!KeSetEvent` at `0x14006dbde`
- `ntoskrnl!KeSetEvent` at `0x14006dd83`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dc6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dd95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dc6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dd95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006db9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006dd61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006db9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006dd61`

## pseudocode

```c

```
