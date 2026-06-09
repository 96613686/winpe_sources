# BaseSetMultiNameInReg

- ea: `0x180068870`
- end: `0x180068966`
- name: `BaseSetMultiNameInReg`
- size: `246`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, PVOID Data, ULONG DataSize)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180068034`
- `0x1800681b8`
- `0x1800685dc`

## callees

- `0x180068870`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x180068938`
- `ntdll!NtSetValueKey` at `0x180068938`
- `ntdll!NtClose` at `0x180068952`
- `ntdll!NtClose` at `0x180068952`
- `ntdll!NtFlushKey` at `0x180068948`
- `ntdll!NtFlushKey` at `0x180068948`
- `ntdll!NtCreateKey` at `0x180068907`
- `ntdll!NtCreateKey` at `0x180068907`
- `ntdll!RtlInitUnicodeString` at `0x1800688b1`
- `ntdll!RtlInitUnicodeString` at `0x180068918`
- `ntdll!RtlInitUnicodeString` at `0x1800688b1`
- `ntdll!RtlInitUnicodeString` at `0x180068918`

## pseudocode

```c

```
