# PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)

- ea: `0x140020240`
- end: `0x140020325`
- name: `?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, ULONG MajorFunction, PVOID Buffer, ULONG Length, PLARGE_INTEGER)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c764`
- `0x14001cde0`
- `0x1400210a8`
- `0x140021b3c`
- `0x140021ec8`
- `0x14002208c`
- `0x1400221e4`
- `0x1400222c0`
- `0x140022300`

## callees

- `0x140020240`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002030b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002030b`
- `ntoskrnl!IofCallDriver` at `0x1400202e2`
- `ntoskrnl!IofCallDriver` at `0x1400202e2`
- `ntoskrnl!KeInitializeEvent` at `0x140020272`
- `ntoskrnl!KeInitializeEvent` at `0x140020272`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400202aa`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400202aa`

## pseudocode

```c

```
