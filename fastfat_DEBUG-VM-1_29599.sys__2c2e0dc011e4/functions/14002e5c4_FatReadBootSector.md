# FatReadBootSector

- ea: `0x14002e5c4`
- end: `0x14002e6a6`
- name: `FatReadBootSector`
- size: `226`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, ULONG Length, PVOID Buffer)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140040674`

## callees

- `0x14002e5c4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002e5fc`
- `ntoskrnl!KeInitializeEvent` at `0x14002e5fc`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14002e633`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14002e633`
- `ntoskrnl!IofCallDriver` at `0x14002e655`
- `ntoskrnl!IofCallDriver` at `0x14002e655`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e67e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e67e`

## pseudocode

```c

```
