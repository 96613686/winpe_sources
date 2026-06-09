# KerbCreateSmartCardLogonSessionFromCertContextEx(_CERT_CONTEXT const * *,_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,uchar *,ulong,ulong,_KERB_LOGON_SESSION * *,_UNICODE_STRING *,_LUID *)

- ea: `0x18005f7fc`
- end: `0x18005fab6`
- name: `?KerbCreateSmartCardLogonSessionFromCertContextEx@@YAJPEAPEBU_CERT_CONTEXT@@PEAU_LUID@@PEAU_UNICODE_STRING@@2EPEAEKKPEAPEAU_KERB_LOGON_SESSION@@21@Z`
- size: `698`
- prototype: `int(const struct _CERT_CONTEXT **, struct _LUID *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8, unsigned __int8 *, unsigned int, unsigned int, struct _KERB_LOGON_SESSION **, struct _UNICODE_STRING *, struct _LUID *)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800083b4`
- `0x180025680`
- `0x18005b210`
- `0x1800b7a24`

## callees

- `0x1800068d0`
- `0x180008e18`
- `0x1800093f0`
- `0x18000a630`
- `0x18000b300`
- `0x180032f70`
- `0x180048cf0`
- `0x18004960c`
- `0x18005f7fc`
- `0x18005fabc`
- `0x1800603d8`
- `0x180060ce4`
- `0x1800744cf`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa39`
- `ntdll!RtlEnterCriticalSection` at `0x18005f995`
- `ntdll!RtlEnterCriticalSection` at `0x18005f995`
- `ntdll!RtlLeaveCriticalSection` at `0x18005f9c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18005f9c3`
- `CRYPT32!CertFreeCertificateContext` at `0x18005f877`
- `CRYPT32!CertFreeCertificateContext` at `0x18005f877`

## string_xrefs

- `0x18005fa4c`: `KerbCreateSmartCardLogonSessionFromCertContextEx`

## pseudocode

```c

```
