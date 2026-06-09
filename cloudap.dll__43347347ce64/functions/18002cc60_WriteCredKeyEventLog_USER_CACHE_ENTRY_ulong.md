# WriteCredKeyEventLog(_USER_CACHE_ENTRY *,ulong)

- ea: `0x18002cc60`
- end: `0x18002ce45`
- name: `?WriteCredKeyEventLog@@YAXPEAU_USER_CACHE_ENTRY@@K@Z`
- size: `485`
- prototype: `void __fastcall(struct _USER_CACHE_ENTRY *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010aa0`
- `0x180011960`

## callees

- `0x180024a74`
- `0x18002cc60`
- `0x180042410`

## import_xrefs

- `bcrypt!BCryptKeyDerivation` at `0x18002cd60`
- `bcrypt!BCryptKeyDerivation` at `0x18002cd60`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002cd2e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002cd2e`
- `bcrypt!BCryptDestroyKey` at `0x18002ce0a`
- `bcrypt!BCryptDestroyKey` at `0x18002ce0a`

## pseudocode

```c

```
