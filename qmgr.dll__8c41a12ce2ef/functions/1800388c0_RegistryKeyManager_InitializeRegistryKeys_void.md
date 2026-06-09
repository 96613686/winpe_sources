# RegistryKeyManager::InitializeRegistryKeys(void)

- ea: `0x1800388c0`
- end: `0x180038eb2`
- name: `?InitializeRegistryKeys@RegistryKeyManager@@AEAAJXZ`
- size: `1522`
- prototype: `__int64 __fastcall(RegistryKeyManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180092748`

## callees

- `0x180006640`
- `0x1800377b8`
- `0x1800388c0`
- `0x18005bcf0`
- `0x1800634e0`
- `0x180091acc`
- `0x1800944c0`
- `0x1800960f4`
- `0x1800961b8`
- `0x18009cd0c`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800f9948`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18003893b`
- `ntdll!RtlGetPersistedStateLocation` at `0x180038ca8`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003893b`
- `ntdll!RtlGetPersistedStateLocation` at `0x180038ca8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800388ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800388ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e79`

## pseudocode

```c

```
