# ReadRegistryDWORD

- ea: `0x1800575f0`
- end: `0x1800576b4`
- name: `ReadRegistryDWORD`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057d88`

## callees

- `0x1800575f0`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180057631`
- `ntoskrnl!RtlInitUnicodeString` at `0x180057631`
- `ntoskrnl!ZwQueryValueKey` at `0x180057665`
- `ntoskrnl!ZwQueryValueKey` at `0x180057665`

## pseudocode

```c

```
