# KeRegSetValue

- ea: `0x18004bff4`
- end: `0x18004c06a`
- name: `KeRegSetValue`
- size: `118`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, const WCHAR *, ULONG, void *, ULONG DataSize)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18004bf40`
- `0x180070adc`
- `0x180073538`
- `0x180073768`
- `0x1800739c0`
- `0x180074884`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004c018`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c018`
- `ntoskrnl!ZwSetValueKey` at `0x18004c03f`
- `ntoskrnl!ZwSetValueKey` at `0x18004c03f`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004c04d`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004c04d`

## pseudocode

```c

```
