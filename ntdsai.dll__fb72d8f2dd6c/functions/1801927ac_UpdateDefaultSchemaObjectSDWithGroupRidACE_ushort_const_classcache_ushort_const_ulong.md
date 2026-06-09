# UpdateDefaultSchemaObjectSDWithGroupRidACE(ushort const *,_classcache *,ushort const *,ulong)

- ea: `0x1801927ac`
- end: `0x180192ba6`
- name: `?UpdateDefaultSchemaObjectSDWithGroupRidACE@@YAJPEBGPEAU_classcache@@0K@Z`
- size: `1018`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _classcache *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180192bac`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x18001ea60`
- `0x1800334d0`
- `0x180037ce0`
- `0x18003c780`
- `0x1800528dc`
- `0x1800fc54c`
- `0x180161d38`
- `0x180166f10`
- `0x1801923d8`
- `0x1801927ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801928f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801928f1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801929c3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801929c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801927f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801927f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801928af`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801928af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801928b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801928b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180192b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180192b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180192b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180192b76`
- `ntdll!RtlNtStatusToDosError` at `0x180192896`
- `ntdll!RtlNtStatusToDosError` at `0x180192896`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x1801929ab`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x180192a94`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x1801929ab`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x180192a94`

## pseudocode

```c

```
