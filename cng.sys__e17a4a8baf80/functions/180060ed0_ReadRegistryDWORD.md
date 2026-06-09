# ReadRegistryDWORD

- ea: `0x180060ed0`
- end: `0x180060f94`
- name: `ReadRegistryDWORD`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180061668`

## callees

- `0x180060ed0`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180060f11`
- `ntoskrnl!RtlInitUnicodeString` at `0x180060f11`
- `ntoskrnl!ZwQueryValueKey` at `0x180060f45`
- `ntoskrnl!ZwQueryValueKey` at `0x180060f45`

## pseudocode

```c

```
