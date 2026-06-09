# KeRegSetValue

- ea: `0x18004b564`
- end: `0x18004b5da`
- name: `KeRegSetValue`
- size: `118`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, const WCHAR *, ULONG, void *, ULONG DataSize)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18004b4b0`
- `0x1800700dc`
- `0x180072b38`
- `0x180072d68`
- `0x180072fc0`
- `0x180073e84`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004b588`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004b588`
- `ntoskrnl!ZwSetValueKey` at `0x18004b5af`
- `ntoskrnl!ZwSetValueKey` at `0x18004b5af`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004b5bd`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004b5bd`

## pseudocode

```c

```
