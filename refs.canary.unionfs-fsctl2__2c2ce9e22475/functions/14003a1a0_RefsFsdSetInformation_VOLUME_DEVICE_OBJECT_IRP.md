# RefsFsdSetInformation(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14003a1a0`
- end: `0x14003a50c`
- name: `?RefsFsdSetInformation@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `876`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140039b60`
- `0x14003a1a0`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x1400a648c`
- `0x1401e9ce0`
- `0x14028692c`
- `0x140319a38`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14003a256`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003a256`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003a35c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003a35c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a227`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a227`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14003a243`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14003a243`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003a4fb`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003a4fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a3f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a3f0`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003a31b`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14003a31b`
- `ntoskrnl!IoWithinStackLimits` at `0x14003a26d`
- `ntoskrnl!IoWithinStackLimits` at `0x14003a26d`
- `ntoskrnl!KeInitializeEvent` at `0x14003a21b`
- `ntoskrnl!KeInitializeEvent` at `0x14003a21b`

## pseudocode

```c

```
