# GetDomainControllerConnectionInfo(void *,int,ulong,ushort const *,_GPOINFO *,int,COMPARTMENT_ID,_NET_LUID_LH *,ushort * *,sockaddr_storage * *,ldap * *,IConnectivityInfo * *,ulong *)

- ea: `0x18001bc88`
- end: `0x18001c308`
- name: `?GetDomainControllerConnectionInfo@@YAKPEAXHKPEBGPEAU_GPOINFO@@HW4COMPARTMENT_ID@@PEAT_NET_LUID_LH@@PEAPEAGPEAPEAUsockaddr_storage@@PEAPEAUldap@@PEAPEAVIConnectivityInfo@@PEAK@Z`
- size: `1664`
- prototype: `unsigned int(void *, int, unsigned int, const unsigned __int16 *, struct _GPOINFO *, int, enum COMPARTMENT_ID, union _NET_LUID_LH *, unsigned __int16 **, struct sockaddr_storage **, struct ldap **, struct IConnectivityInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x1800183d4`
- `0x18001ae40`
- `0x18001ae60`
- `0x18001b490`
- `0x18001bc88`
- `0x18001d6e8`
- `0x1800246a8`
- `0x18002c690`
- `0x18005334c`
- `0x180053510`
- `0x18005ba50`
- `0x180075ec0`
- `0x180076734`
- `0x1800990ac`
- `0x18009bb7c`
- `0x1800a76b0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c184`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c0d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c28e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c28e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bd31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bd31`
- `netutils!NetApiBufferFree` at `0x18001bfe3`
- `netutils!NetApiBufferFree` at `0x18001c2ae`
- `netutils!NetApiBufferFree` at `0x18001bfe3`
- `netutils!NetApiBufferFree` at `0x18001c2ae`
- `logoncli!DsGetDcNameW` at `0x18001bd76`
- `logoncli!DsGetDcNameW` at `0x18001bd76`

## string_xrefs

- `0x18001c016`: `GetDomainControllerConnectionInfo: Failed to get User Sid`
- `0x18001c046`: `GetDomainControllerConnectionInfo: Failed to get User Sid`
- `0x18001c1a6`: `GetDomainControllerConnectionInfo: Failed to impersonate user`
- `0x18001c1cc`: `GetDomainControllerConnectionInfo: Failed to impersonate user`

## pseudocode

```c

```
