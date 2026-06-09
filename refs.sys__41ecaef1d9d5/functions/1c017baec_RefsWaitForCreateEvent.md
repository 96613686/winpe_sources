# RefsWaitForCreateEvent

- ea: `0x1c017baec`
- end: `0x1c017bb42`
- name: `RefsWaitForCreateEvent`
- size: `86`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1c015d870`

## callees

- `0x1c017baec`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1c018bcc0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c018bcc0`
- `ntoskrnl!KeClearEvent` at `0x1c017bb2a`
- `ntoskrnl!KeClearEvent` at `0x1c017bb2a`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1c017bb05`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1c017bb05`
- `ntoskrnl!IoCancelIrp` at `0x1c018bc8b`
- `ntoskrnl!IoCancelIrp` at `0x1c018bc8b`
- `ntoskrnl!KeSetEvent` at `0x1c018bca3`
- `ntoskrnl!KeSetEvent` at `0x1c018bca3`

## pseudocode

```c

```
