# PmGetDevicePropertyData(_DEVICE_OBJECT *,_DEVPROPKEY const *,void * *)

- ea: `0x14002443c`
- end: `0x140024545`
- name: `?PmGetDevicePropertyData@@YAJPEAU_DEVICE_OBJECT@@PEBU_DEVPROPKEY@@PEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT Pdo, DEVPROPKEY *PropertyKey, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000df40`
- `0x1400243b0`
- `0x140024420`
- `0x140025d20`

## callees

- `0x14002443c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024523`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024523`
- `ntoskrnl!ExAllocatePool2` at `0x1400244b9`
- `ntoskrnl!ExAllocatePool2` at `0x1400244b9`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14002448e`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140024507`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14002448e`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140024507`

## pseudocode

```c

```
