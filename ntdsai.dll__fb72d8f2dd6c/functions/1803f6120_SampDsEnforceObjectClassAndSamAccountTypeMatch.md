# SampDsEnforceObjectClassAndSamAccountTypeMatch

- ea: `0x1803f6120`
- end: `0x1803f6936`
- name: `SampDsEnforceObjectClassAndSamAccountTypeMatch`
- size: `2070`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006330`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x18003da6c`
- `0x1801654f8`
- `0x1803f4a94`
- `0x1803f5098`
- `0x1803f6120`
- `0x1803faa00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803f6677`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803f6677`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f66db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f66db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f6911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f6911`
- `ntdll!RtlInitUnicodeString` at `0x1803f666b`
- `ntdll!RtlInitUnicodeString` at `0x1803f66c8`
- `ntdll!RtlInitUnicodeString` at `0x1803f66f4`
- `ntdll!RtlInitUnicodeString` at `0x1803f666b`
- `ntdll!RtlInitUnicodeString` at `0x1803f66c8`
- `ntdll!RtlInitUnicodeString` at `0x1803f66f4`
- `SAMSRV!SampWriteEventLog` at `0x1803f6729`
- `SAMSRV!SampWriteEventLog` at `0x1803f6729`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x1803f6643`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x1803f6643`

## string_xrefs

- `0x1803f6658`: `computer`

## pseudocode

```c

```
