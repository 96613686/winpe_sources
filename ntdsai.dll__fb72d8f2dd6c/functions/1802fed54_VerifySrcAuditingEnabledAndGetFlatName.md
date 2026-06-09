# VerifySrcAuditingEnabledAndGetFlatName

- ea: `0x1802fed54`
- end: `0x1802fef48`
- name: `VerifySrcAuditingEnabledAndGetFlatName`
- size: `500`
- prototype: `__int64 __fastcall(PLSA_UNICODE_STRING SystemName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1802fb900`

## callees

- `0x1800067d0`
- `0x180021aa3`
- `0x18002a060`
- `0x1802fed54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802fed76`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802fed76`
- `ntdll!RtlNtStatusToDosError` at `0x1802fede5`
- `ntdll!RtlNtStatusToDosError` at `0x1802fee11`
- `ntdll!RtlNtStatusToDosError` at `0x1802fee59`
- `ntdll!RtlNtStatusToDosError` at `0x1802fef06`
- `ntdll!RtlNtStatusToDosError` at `0x1802fede5`
- `ntdll!RtlNtStatusToDosError` at `0x1802fee11`
- `ntdll!RtlNtStatusToDosError` at `0x1802fee59`
- `ntdll!RtlNtStatusToDosError` at `0x1802fef06`
- `ADVAPI32!LsaOpenPolicy` at `0x1802fedd9`
- `ADVAPI32!LsaOpenPolicy` at `0x1802fedd9`
- `ADVAPI32!LsaClose` at `0x1802feef6`
- `ADVAPI32!LsaClose` at `0x1802feef6`
- `ADVAPI32!LsaFreeMemory` at `0x1802fef1d`
- `ADVAPI32!LsaFreeMemory` at `0x1802fef2c`
- `ADVAPI32!LsaFreeMemory` at `0x1802fef1d`
- `ADVAPI32!LsaFreeMemory` at `0x1802fef2c`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1802fee05`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1802fee4d`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1802fee05`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1802fee4d`

## pseudocode

```c

```
