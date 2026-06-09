# CscRegistrypWriteString

- ea: `0x140021b04`
- end: `0x140021c36`
- name: `CscRegistrypWriteString`
- size: `306`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400526cc`

## callees

- `0x14001a46c`
- `0x14001f75c`
- `0x140021b04`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140021b68`
- `ntoskrnl!ExAllocatePool2` at `0x140021b68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021bdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021bdb`
- `ntoskrnl!ZwSetValueKey` at `0x140021bbd`
- `ntoskrnl!ZwSetValueKey` at `0x140021bbd`

## pseudocode

```c

```
