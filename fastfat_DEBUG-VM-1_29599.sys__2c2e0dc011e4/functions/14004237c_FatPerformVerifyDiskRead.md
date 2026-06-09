# FatPerformVerifyDiskRead

- ea: `0x14004237c`
- end: `0x1400424bd`
- name: `FatPerformVerifyDiskRead`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140042dcc`
- `0x140042ec8`

## callees

- `0x14004237c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400423b3`
- `ntoskrnl!KeInitializeEvent` at `0x1400423b3`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400423ff`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400423ff`
- `ntoskrnl!IofCallDriver` at `0x14004243a`
- `ntoskrnl!IofCallDriver` at `0x14004243a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140042463`
- `ntoskrnl!KeWaitForSingleObject` at `0x140042463`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140042492`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140042492`
- `ntoskrnl!ExRaiseStatus` at `0x14004241b`
- `ntoskrnl!ExRaiseStatus` at `0x1400424a0`
- `ntoskrnl!ExRaiseStatus` at `0x14004241b`
- `ntoskrnl!ExRaiseStatus` at `0x1400424a0`

## pseudocode

```c

```
