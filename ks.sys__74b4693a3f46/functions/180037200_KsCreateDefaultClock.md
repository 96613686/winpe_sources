# KsCreateDefaultClock

- ea: `0x180037200`
- end: `0x1800372e0`
- name: `KsCreateDefaultClock`
- size: `224`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PKSDEFAULTCLOCK DefaultClock)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003f450`

## callees

- `0x180011394`
- `0x180011ba0`
- `0x180037200`
- `0x1800372f0`
- `0x180051490`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18003728a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003728a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003723a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003723a`

## pseudocode

```c

```
