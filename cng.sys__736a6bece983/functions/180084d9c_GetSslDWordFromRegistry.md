# GetSslDWordFromRegistry

- ea: `0x180084d9c`
- end: `0x180084e55`
- name: `GetSslDWordFromRegistry`
- size: `185`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180082418`
- `0x180083158`
- `0x180085164`
- `0x1800859f8`

## callees

- `0x180084d9c`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180084de0`
- `ntoskrnl!RtlInitUnicodeString` at `0x180084de0`
- `ntoskrnl!ZwQueryValueKey` at `0x180084e11`
- `ntoskrnl!ZwQueryValueKey` at `0x180084e11`

## pseudocode

```c

```
