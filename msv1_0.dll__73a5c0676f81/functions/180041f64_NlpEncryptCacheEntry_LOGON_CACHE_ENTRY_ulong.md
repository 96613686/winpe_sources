# NlpEncryptCacheEntry(_LOGON_CACHE_ENTRY *,ulong)

- ea: `0x180041f64`
- end: `0x180042037`
- name: `?NlpEncryptCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@K@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct _LOGON_CACHE_ENTRY *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004339c`
- `0x18004417c`
- `0x180044788`

## callees

- `0x18002fb50`
- `0x180041f64`

## import_xrefs

- `cryptdll!HMACwithSHA` at `0x180041fe4`
- `cryptdll!HMACwithSHA` at `0x180041fe4`
- `cryptdll!aesCTSEncryptMsg` at `0x180042012`
- `cryptdll!aesCTSEncryptMsg` at `0x180042012`

## pseudocode

```c

```
