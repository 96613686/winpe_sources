# NlInitializeServiceAccounts(void)

- ea: `0x18000da50`
- end: `0x18000db5b`
- name: `?NlInitializeServiceAccounts@@YAJXZ`
- size: `267`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000dfd4`
- `0x180056ab0`
- `0x1800570c0`
- `0x180069a30`

## callees

- `0x18000da50`
- `0x18000dd00`
- `0x18000ddec`
- `0x180056bac`
- `0x1800660e0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000db3f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000db3f`
- `ntdll!RtlEnterCriticalSection` at `0x18000da70`
- `ntdll!RtlEnterCriticalSection` at `0x18000da70`
- `netutils!NetApiBufferFree` at `0x18000db09`
- `netutils!NetApiBufferFree` at `0x18000db23`
- `netutils!NetApiBufferFree` at `0x18000db09`
- `netutils!NetApiBufferFree` at `0x18000db23`

## string_xrefs

- `0x18000daa5`: `!NlGlobalServiceAccountInitialized && IsListEmpty( &NlGlobalServiceAccountList )`
- `0x18000da9e`: `onecore\ds\netapi\svcdlls\logonsrv\server\service.cxx`

## pseudocode

```c

```
