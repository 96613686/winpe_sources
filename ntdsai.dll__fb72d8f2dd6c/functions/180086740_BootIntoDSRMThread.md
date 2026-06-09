# BootIntoDSRMThread

- ea: `0x180086740`
- end: `0x1800872f2`
- name: `BootIntoDSRMThread`
- size: `2994`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180086740`
- `0x180172774`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `DSROLESRV!DsRolepSetDSRMBootMode` at `0x180086ae8`
- `DSROLESRV!DsRolepSetDSRMBootMode` at `0x180086ae8`
- `DSROLESRV!DsRolepEnablePrivilege` at `0x180086d03`
- `DSROLESRV!DsRolepEnablePrivilege` at `0x180086d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e54`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180086e3a`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180086e3a`
- `ntdll!NtShutdownSystem` at `0x18008700e`
- `ntdll!NtShutdownSystem` at `0x18008700e`
- `ntdll!RtlNtStatusToDosError` at `0x180086c90`
- `ntdll!RtlNtStatusToDosError` at `0x180086ceb`
- `ntdll!RtlNtStatusToDosError` at `0x18008719b`
- `ntdll!RtlNtStatusToDosError` at `0x180086c90`
- `ntdll!RtlNtStatusToDosError` at `0x180086ceb`
- `ntdll!RtlNtStatusToDosError` at `0x18008719b`

## pseudocode

```c

```
