# KerbCaptureSuppliedCreds(ulong,_KERB_LOGON_SESSION *,void *,_UNICODE_STRING *,void *,_KERB_PRIMARY_CREDENTIAL * *,ulong *)

- ea: `0x1800adccc`
- end: `0x1800aeb5a`
- name: `?KerbCaptureSuppliedCreds@@YAJKPEAU_KERB_LOGON_SESSION@@PEAXPEAU_UNICODE_STRING@@1PEAPEAU_KERB_PRIMARY_CREDENTIAL@@PEAK@Z`
- size: `3726`
- prototype: `int(unsigned int, struct _KERB_LOGON_SESSION *, void *, struct _UNICODE_STRING *, void *, struct _KERB_PRIMARY_CREDENTIAL **, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting`

## callers

- `0x18005d250`

## callees

- `0x180006550`
- `0x1800068d0`
- `0x1800069a0`
- `0x180007e80`
- `0x1800093f0`
- `0x18000b300`
- `0x18001deb0`
- `0x1800326a0`
- `0x1800378e0`
- `0x18005a838`
- `0x1800638a0`
- `0x180063e44`
- `0x18006ba6c`
- `0x18006d264`
- `0x18006dc2c`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800782ec`
- `0x180078360`
- `0x18008b70c`
- `0x1800adccc`
- `0x1800c48cc`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800ae68f`
- `ntdll!RtlEqualUnicodeString` at `0x1800ae68f`
- `ntdll!RtlFreeUnicodeString` at `0x1800adfe7`
- `ntdll!RtlFreeUnicodeString` at `0x1800adffc`
- `ntdll!RtlFreeUnicodeString` at `0x1800ae01a`
- `ntdll!RtlFreeUnicodeString` at `0x1800ae46b`
- `ntdll!RtlFreeUnicodeString` at `0x1800adfe7`
- `ntdll!RtlFreeUnicodeString` at `0x1800adffc`
- `ntdll!RtlFreeUnicodeString` at `0x1800ae01a`
- `ntdll!RtlFreeUnicodeString` at `0x1800ae46b`
- `ntdll!RtlInitUnicodeString` at `0x1800ae606`
- `ntdll!RtlInitUnicodeString` at `0x1800ae606`
- `ntdll!RtlEnterCriticalSection` at `0x1800ae523`
- `ntdll!RtlEnterCriticalSection` at `0x1800ae523`
- `ntdll!RtlLeaveCriticalSection` at `0x1800adf79`
- `ntdll!RtlLeaveCriticalSection` at `0x1800adf79`
- `CRYPT32!CertFreeCertificateContext` at `0x1800adf37`
- `CRYPT32!CertFreeCertificateContext` at `0x1800adf37`

## string_xrefs

- `0x1800ae0bf`: `Failed to copy auth data from %p client address: 0x%x`
- `0x1800ae356`: `Failed to copy client user name.`
- `0x1800ae39f`: `Failed to copy client Domain name.`
- `0x1800ae3d4`: `Failed to copy client Password name.`

## pseudocode

```c

```
