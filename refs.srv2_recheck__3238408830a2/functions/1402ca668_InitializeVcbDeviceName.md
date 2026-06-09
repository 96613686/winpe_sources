# InitializeVcbDeviceName

- ea: `0x1402ca668`
- end: `0x1402ca887`
- name: `InitializeVcbDeviceName`
- size: `543`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140324914`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1402ca668`
- `0x14032c400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1402ca79e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ca79e`
- `ntoskrnl!ObQueryNameString` at `0x1402ca69c`
- `ntoskrnl!ObQueryNameString` at `0x1402ca6f2`
- `ntoskrnl!ObQueryNameString` at `0x1402ca69c`
- `ntoskrnl!ObQueryNameString` at `0x1402ca6f2`
- `ntoskrnl!PcwCreateInstance` at `0x1402ca855`
- `ntoskrnl!PcwCreateInstance` at `0x1402ca855`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ca86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140348818`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ca86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140348818`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ca6c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ca6c7`

## string_xrefs

- `0x1402ca74e`: `mount.c`

## pseudocode

```c

```
