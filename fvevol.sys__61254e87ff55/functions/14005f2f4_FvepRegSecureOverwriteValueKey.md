# FvepRegSecureOverwriteValueKey

- ea: `0x14005f2f4`
- end: `0x14005f409`
- name: `FvepRegSecureOverwriteValueKey`
- size: `277`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14005edb8`
- `0x14005f15c`
- `0x14005f410`

## callees

- `0x14005f2f4`

## import_xrefs

- `ntoskrnl!ZwFlushKey` at `0x14005f3cc`
- `ntoskrnl!ZwFlushKey` at `0x14005f3cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3f1`
- `ntoskrnl!ZwSetValueKey` at `0x14005f3b7`
- `ntoskrnl!ZwSetValueKey` at `0x14005f3b7`
- `ntoskrnl!ExAllocatePool2` at `0x14005f32c`
- `ntoskrnl!ExAllocatePool2` at `0x14005f32c`
- `ntoskrnl!ZwQueryValueKey` at `0x14005f367`
- `ntoskrnl!ZwQueryValueKey` at `0x14005f367`

## pseudocode

```c

```
