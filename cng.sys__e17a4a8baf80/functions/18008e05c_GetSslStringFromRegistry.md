# GetSslStringFromRegistry

- ea: `0x18008e05c`
- end: `0x18008e148`
- name: `GetSslStringFromRegistry`
- size: `236`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18008c358`
- `0x18008e364`
- `0x18008e740`
- `0x18008ebd0`
- `0x18008f00c`

## callees

- `0x18008df38`
- `0x18008e05c`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18008e0b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008e0b4`
- `ntoskrnl!ZwQueryValueKey` at `0x18008e0e5`
- `ntoskrnl!ZwQueryValueKey` at `0x18008e0e5`

## pseudocode

```c

```
