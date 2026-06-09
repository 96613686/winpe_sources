# BaseSetMultiNameInReg

- ea: `0x18006f93c`
- end: `0x18006fa57`
- name: `BaseSetMultiNameInReg`
- size: `283`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, PVOID Data, ULONG DataSize)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006f000`
- `0x18006f1b4`
- `0x18006f684`

## callees

- `0x18006f93c`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18006fa16`
- `ntdll!NtSetValueKey` at `0x18006fa16`
- `ntdll!NtClose` at `0x18006fa3c`
- `ntdll!NtClose` at `0x18006fa3c`
- `ntdll!NtFlushKey` at `0x18006fa2c`
- `ntdll!NtFlushKey` at `0x18006fa2c`
- `ntdll!NtCreateKey` at `0x18006f9d9`
- `ntdll!NtCreateKey` at `0x18006f9d9`
- `ntdll!RtlInitUnicodeString` at `0x18006f97d`
- `ntdll!RtlInitUnicodeString` at `0x18006f9f0`
- `ntdll!RtlInitUnicodeString` at `0x18006f97d`
- `ntdll!RtlInitUnicodeString` at `0x18006f9f0`

## pseudocode

```c

```
