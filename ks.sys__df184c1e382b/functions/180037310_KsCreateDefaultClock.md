# KsCreateDefaultClock

- ea: `0x180037310`
- end: `0x1800373f0`
- name: `KsCreateDefaultClock`
- size: `224`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PKSDEFAULTCLOCK DefaultClock)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003f440`

## callees

- `0x180011c34`
- `0x180012440`
- `0x180037310`
- `0x180037400`
- `0x180051630`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18003739a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003739a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003734a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003734a`

## pseudocode

```c

```
