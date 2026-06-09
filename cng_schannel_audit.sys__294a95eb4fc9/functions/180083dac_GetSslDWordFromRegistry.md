# GetSslDWordFromRegistry

- ea: `0x180083dac`
- end: `0x180083e65`
- name: `GetSslDWordFromRegistry`
- size: `185`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180081428`
- `0x180082168`
- `0x180084174`
- `0x1800849e0`

## callees

- `0x180083dac`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180083df0`
- `ntoskrnl!RtlInitUnicodeString` at `0x180083df0`
- `ntoskrnl!ZwQueryValueKey` at `0x180083e21`
- `ntoskrnl!ZwQueryValueKey` at `0x180083e21`

## pseudocode

```c

```
