# ndisPowerSuspendRequestComplete(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *)

- ea: `0x140067f80`
- end: `0x14006820d`
- name: `?ndisPowerSuspendRequestComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z`
- size: `653`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140014850`
- `0x140019b40`
- `0x14001d030`
- `0x14003ef00`
- `0x140067f80`
- `0x140068220`
- `0x14006ab70`
- `0x140086c80`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140068026`
- `ntoskrnl!KeClearEvent` at `0x140068026`
- `ntoskrnl!KeSetEvent` at `0x14006803e`
- `ntoskrnl!KeSetEvent` at `0x1400681e3`
- `ntoskrnl!KeSetEvent` at `0x14006803e`
- `ntoskrnl!KeSetEvent` at `0x1400681e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400680ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400681f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400680ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400681f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140067ffe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400681c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140067ffe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400681c1`

## pseudocode

```c

```
