# RefsFsdDeviceControl(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14032ac20`
- end: `0x14032ae41`
- name: `?RefsFsdDeviceControl@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `545`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x140039b60`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x14007dd30`
- `0x14008dbd0`
- `0x14008e5d0`
- `0x1400a648c`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x1402961f4`
- `0x14032ac20`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x14034af30`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14034af30`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032ac8f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032adae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032ac8f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032adae`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14032aca8`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14032aca8`
- `ntoskrnl!IoClearActivityIdThread` at `0x14034afcb`
- `ntoskrnl!IoClearActivityIdThread` at `0x14034afcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032add3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034afd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032add3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034afd7`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14032ac7f`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14032ac7f`

## pseudocode

```c

```
