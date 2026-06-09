# NetworkListManager::UpdateProfileCategoryAfterConnect(_GUID const &,ulong,_GUID const *,wchar_t const *,int,int *,ulong *)

- ea: `0x1800c6864`
- end: `0x1800c6baa`
- name: `?UpdateProfileCategoryAfterConnect@NetworkListManager@@AEAAJAEBU_GUID@@KPEBU2@PEB_WHPEAHPEAK@Z`
- size: `838`
- prototype: `int(NetworkListManager *__hidden this, const struct _GUID *, unsigned int, const struct _GUID *, const wchar_t *, int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a6020`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180013cac`
- `0x180014e74`
- `0x180015628`
- `0x180015650`
- `0x180019274`
- `0x180020d40`
- `0x1800346a8`
- `0x180035dc4`
- `0x18005b598`
- `0x1800a3b2c`
- `0x1800a88a0`
- `0x1800bf090`
- `0x1800c4084`
- `0x1800c418c`
- `0x1800c6864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6b78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6b78`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c69e8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c69e8`

## string_xrefs

- `0x1800c6a14`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`
- `0x1800c6ac5`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c

```
