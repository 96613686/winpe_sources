# GetSslStringFromRegistry

- ea: `0x180083e6c`
- end: `0x180083f58`
- name: `GetSslStringFromRegistry`
- size: `236`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180082168`
- `0x180084174`
- `0x180084550`
- `0x1800849e0`
- `0x180084e1c`

## callees

- `0x180083d48`
- `0x180083e6c`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180083ec4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180083ec4`
- `ntoskrnl!ZwQueryValueKey` at `0x180083ef5`
- `ntoskrnl!ZwQueryValueKey` at `0x180083ef5`

## pseudocode

```c

```
