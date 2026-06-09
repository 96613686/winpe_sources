# LsapUpdateNamesAndCredentialsWorker(_SECURITY_LOGON_TYPE,_LUID *,_UNICODE_STRING *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY *)

- ea: `0x1800043bc`
- end: `0x180004a47`
- name: `?LsapUpdateNamesAndCredentialsWorker@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_LUID@@PEAU_UNICODE_STRING@@PEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `1675`
- prototype: `int(enum _SECURITY_LOGON_TYPE, struct _LUID *, struct _UNICODE_STRING *, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002db0`
- `0x180004140`

## callees

- `0x1800043bc`
- `0x1800093b0`
- `0x180009410`
- `0x180009838`
- `0x18000c300`
- `0x1800268d8`
- `0x18005915c`
- `0x18005c150`
- `0x18005fb34`
- `0x180060888`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800db3d0`
- `0x1800debd4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004795`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004795`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000480c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000480c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004750`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004750`
- `ntdll!RtlReleaseResource` at `0x1800049c4`
- `ntdll!RtlReleaseResource` at `0x1800049c4`
- `ntdll!RtlEqualSid` at `0x180004562`
- `ntdll!RtlEqualSid` at `0x1800045b1`
- `ntdll!RtlEqualSid` at `0x180004562`
- `ntdll!RtlEqualSid` at `0x1800045b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800049fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800049fc`
- `ntdll!RtlEnterCriticalSection` at `0x1800046e3`
- `ntdll!RtlEnterCriticalSection` at `0x180004706`
- `ntdll!RtlEnterCriticalSection` at `0x1800046e3`
- `ntdll!RtlEnterCriticalSection` at `0x180004706`
- `ntdll!RtlEqualUnicodeString` at `0x18000485b`
- `ntdll!RtlEqualUnicodeString` at `0x18000485b`

## pseudocode

```c

```
