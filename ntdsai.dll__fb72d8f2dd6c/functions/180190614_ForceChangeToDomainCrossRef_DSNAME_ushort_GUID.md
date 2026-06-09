# ForceChangeToDomainCrossRef(_DSNAME *,ushort *,_GUID *)

- ea: `0x180190614`
- end: `0x180190785`
- name: `?ForceChangeToDomainCrossRef@@YAKPEAU_DSNAME@@PEAGPEAU_GUID@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(struct _DSNAME *, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180194070`

## callees

- `0x1800336a0`
- `0x1800337b4`
- `0x180035b38`
- `0x180037638`
- `0x18003b8d4`
- `0x180173e2c`
- `0x180190614`
- `0x180193c18`
- `0x18039c284`
- `0x18039c448`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801906be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801906d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180190702`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019073b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462aa8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462add`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801906be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801906d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180190702`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019073b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462aa8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462add`
- `ntdll!RtlNtStatusToDosError` at `0x18019067b`
- `ntdll!RtlNtStatusToDosError` at `0x18019067b`
- `ntdll!RtlLengthSid` at `0x1801906a0`
- `ntdll!RtlLengthSid` at `0x1801906a0`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180190753`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180462af5`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180190753`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180462af5`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18019066f`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18019066f`

## pseudocode

```c

```
