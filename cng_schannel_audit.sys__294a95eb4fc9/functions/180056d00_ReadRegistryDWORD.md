# ReadRegistryDWORD

- ea: `0x180056d00`
- end: `0x180056dc4`
- name: `ReadRegistryDWORD`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057498`

## callees

- `0x180056d00`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180056d41`
- `ntoskrnl!RtlInitUnicodeString` at `0x180056d41`
- `ntoskrnl!ZwQueryValueKey` at `0x180056d75`
- `ntoskrnl!ZwQueryValueKey` at `0x180056d75`

## pseudocode

```c

```
