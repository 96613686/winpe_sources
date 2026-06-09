# GetSslStringFromRegistry

- ea: `0x180084e5c`
- end: `0x180084f48`
- name: `GetSslStringFromRegistry`
- size: `236`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180083158`
- `0x180085164`
- `0x180085568`
- `0x1800859f8`
- `0x180085e34`

## callees

- `0x180084d38`
- `0x180084e5c`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180084eb4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180084eb4`
- `ntoskrnl!ZwQueryValueKey` at `0x180084ee5`
- `ntoskrnl!ZwQueryValueKey` at `0x180084ee5`

## pseudocode

```c

```
