# COfflineFilesService::QueryItemConnectionState(ushort const *,ulong *,ulong *)

- ea: `0x180007750`
- end: `0x1800079ed`
- name: `?QueryItemConnectionState@COfflineFilesService@@UEAAJPEBGPEAK1@Z`
- size: `669`
- prototype: `int(COfflineFilesService *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800068b0`
- `0x180007230`
- `0x180007750`
- `0x180039610`
- `0x18003c4e8`
- `0x180046ad8`
- `0x180089010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180007835`
- `ntdll!RtlInitUnicodeString` at `0x180007835`
- `ntdll!NtClose` at `0x1800078ad`
- `ntdll!NtClose` at `0x1800078ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800078bd`
- `ntdll!RtlNtStatusToDosError` at `0x1800078bd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007905`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007905`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800077bb`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800077bb`

## pseudocode

```c

```
