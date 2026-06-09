# FvepRegSecureOverwriteValueKey

- ea: `0x14005d274`
- end: `0x14005d389`
- name: `FvepRegSecureOverwriteValueKey`
- size: `277`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14005cd38`
- `0x14005d0dc`
- `0x14005d390`

## callees

- `0x14005d274`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x14005d34c`
- `ntoskrnl!ZwFlushKey` at `0x14005d34c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d371`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d371`
- `ntoskrnl!ZwSetValueKey` at `0x14005d337`
- `ntoskrnl!ZwSetValueKey` at `0x14005d337`
- `ntoskrnl!ExAllocatePool2` at `0x14005d2ac`
- `ntoskrnl!ExAllocatePool2` at `0x14005d2ac`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d2e7`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d2e7`

## pseudocode

```c

```
