# CscRegistrypReadULong

- ea: `0x1400218ac`
- end: `0x140021996`
- name: `CscRegistrypReadULong`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002166c`
- `0x1400526cc`
- `0x1400529f8`

## callees

- `0x14001fb20`
- `0x1400218ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400218dd`
- `ntoskrnl!ExAllocatePool2` at `0x1400218dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021942`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021942`
- `ntoskrnl!ZwQueryValueKey` at `0x140021919`
- `ntoskrnl!ZwQueryValueKey` at `0x140021919`

## pseudocode

```c

```
