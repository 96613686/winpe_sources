# CscRegistrypReadString

- ea: `0x140021704`
- end: `0x1400218a4`
- name: `CscRegistrypReadString`
- size: `416`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14002166c`
- `0x1400529f8`

## callees

- `0x140021704`
- `0x140021d0c`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002176d`
- `ntoskrnl!ExAllocatePool2` at `0x14002176d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400217cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400217cb`
- `ntoskrnl!ZwQueryValueKey` at `0x140021746`
- `ntoskrnl!ZwQueryValueKey` at `0x1400217ac`
- `ntoskrnl!ZwQueryValueKey` at `0x140021746`
- `ntoskrnl!ZwQueryValueKey` at `0x1400217ac`

## pseudocode

```c

```
