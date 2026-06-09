# RegistryPathWatcher::RegisterNotification(int,ulong)

- ea: `0x18005aa10`
- end: `0x18005ac63`
- name: `?RegisterNotification@RegistryPathWatcher@@QEAAJHK@Z`
- size: `595`
- prototype: `HRESULT __fastcall(RegistryPathWatcher *this, int bWatchSubtree, unsigned int bWatchSubtree)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b644`
- `0x18005daf0`
- `0x180083228`

## callees

- `0x18003a8bc`
- `0x18005aa10`
- `0x18005ac6c`
- `0x18005b454`
- `0x18005b484`
- `0x18005b528`
- `0x18005ce9c`
- `0x18019db88`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005abf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005abf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ac27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005abde`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005aa83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005aa83`

## string_xrefs

- `0x18005aa9f`: `onecore\com\combase\inc\RegistryWatcher.hpp`
- `0x18005aade`: `onecore\com\combase\inc\RegistryWatcher.hpp`
- `0x18005ac06`: `onecore\com\combase\inc\RegistryWatcher.hpp`
- `0x18005ac36`: `onecore\com\combase\inc\RegistryWatcher.hpp`

## pseudocode

```c

```
