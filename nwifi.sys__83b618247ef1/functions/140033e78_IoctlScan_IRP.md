# IoctlScan(_IRP *)

- ea: `0x140033e78`
- end: `0x140034047`
- name: `?IoctlScan@@YAJPEAU_IRP@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cb10`

## callees

- `0x14000d22c`
- `0x140033e78`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140033f00`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033fcf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033f00`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033fcf`
- `ntoskrnl!KeSetEvent` at `0x140033f4a`
- `ntoskrnl!KeSetEvent` at `0x140034001`
- `ntoskrnl!KeSetEvent` at `0x140033f4a`
- `ntoskrnl!KeSetEvent` at `0x140034001`
- `ntoskrnl!IofCompleteRequest` at `0x140034025`
- `ntoskrnl!IofCompleteRequest` at `0x140034025`

## pseudocode

```c

```
