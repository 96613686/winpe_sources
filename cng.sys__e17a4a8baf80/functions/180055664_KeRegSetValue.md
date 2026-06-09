# KeRegSetValue

- ea: `0x180055664`
- end: `0x1800556da`
- name: `KeRegSetValue`
- size: `118`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800555b0`
- `0x18007a27c`
- `0x18007ccd8`
- `0x18007cf08`
- `0x18007d160`
- `0x18007e024`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180055688`
- `ntoskrnl!RtlInitUnicodeString` at `0x180055688`
- `ntoskrnl!ZwSetValueKey` at `0x1800556af`
- `ntoskrnl!ZwSetValueKey` at `0x1800556af`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800556bd`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800556bd`

## pseudocode

```c

```
