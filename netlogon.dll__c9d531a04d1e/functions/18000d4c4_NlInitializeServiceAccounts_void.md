# NlInitializeServiceAccounts(void)

- ea: `0x18000d4c4`
- end: `0x18000d5b6`
- name: `?NlInitializeServiceAccounts@@YAJXZ`
- size: `242`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000d9a8`
- `0x180053160`
- `0x1800536e4`
- `0x180064f64`

## callees

- `0x18000d4c4`
- `0x18000d710`
- `0x18000d7e0`
- `0x18005322c`
- `0x180061a74`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000d5a1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d5a1`
- `ntdll!RtlEnterCriticalSection` at `0x18000d4e4`
- `ntdll!RtlEnterCriticalSection` at `0x18000d4e4`
- `netutils!NetApiBufferFree` at `0x18000d577`
- `netutils!NetApiBufferFree` at `0x18000d58b`
- `netutils!NetApiBufferFree` at `0x18000d577`
- `netutils!NetApiBufferFree` at `0x18000d58b`

## string_xrefs

- `0x18000d513`: `!NlGlobalServiceAccountInitialized && IsListEmpty( &NlGlobalServiceAccountList )`
- `0x18000d50c`: `onecore\ds\netapi\svcdlls\logonsrv\server\service.cxx`

## pseudocode

```c

```
