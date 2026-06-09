# IoctlScan(_IRP *)

- ea: `0x140034098`
- end: `0x140034267`
- name: `?IoctlScan@@YAJPEAU_IRP@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cb00`

## callees

- `0x14000d21c`
- `0x140034098`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140034120`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400341ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x140034120`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400341ef`
- `ntoskrnl!KeSetEvent` at `0x14003416a`
- `ntoskrnl!KeSetEvent` at `0x140034221`
- `ntoskrnl!KeSetEvent` at `0x14003416a`
- `ntoskrnl!KeSetEvent` at `0x140034221`
- `ntoskrnl!IofCompleteRequest` at `0x140034245`
- `ntoskrnl!IofCompleteRequest` at `0x140034245`

## pseudocode

```c

```
