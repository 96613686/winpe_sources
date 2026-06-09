# KerbVerifyPkAsReply(_KERB_LOGON_SESSION *,KERB_KDC_REQUEST_preauth_data_s *,_KERB_PRIMARY_CREDENTIAL *,ulong,_LARGE_INTEGER *,_UNICODE_STRING *,_KERB_ENCRYPTION_KEY *,_KERB_MESSAGE_BUFFER *,KerbKeyAgreement *)

- ea: `0x1800baae4`
- end: `0x1800bb377`
- name: `?KerbVerifyPkAsReply@@YAJPEAU_KERB_LOGON_SESSION@@PEAUKERB_KDC_REQUEST_preauth_data_s@@PEAU_KERB_PRIMARY_CREDENTIAL@@KPEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_KERB_MESSAGE_BUFFER@@PEAVKerbKeyAgreement@@@Z`
- size: `2195`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct KERB_KDC_REQUEST_preauth_data_s *, struct _KERB_PRIMARY_CREDENTIAL *, unsigned int, union _LARGE_INTEGER *, struct _UNICODE_STRING *, struct _KERB_ENCRYPTION_KEY *, struct _KERB_MESSAGE_BUFFER *, struct KerbKeyAgreement *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b6600`

## callees

- `0x18000169c`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x1800210e0`
- `0x180029c50`
- `0x180032334`
- `0x180035c10`
- `0x180039ac8`
- `0x18003aef0`
- `0x18005f044`
- `0x1800603d8`
- `0x180066994`
- `0x18006c21c`
- `0x18006ebf4`
- `0x18006ecb4`
- `0x180070680`
- `0x18008b70c`
- `0x1800baae4`
- `0x1800bb380`
- `0x1800ee150`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb1f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb1f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800badc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800badc0`
- `ntdll!RtlEnterCriticalSection` at `0x1800badb2`
- `ntdll!RtlEnterCriticalSection` at `0x1800badb2`
- `ntdll!NtQuerySystemTime` at `0x1800bb04f`
- `ntdll!NtQuerySystemTime` at `0x1800bb04f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb24c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb24c`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800bb1e9`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800bb1e9`
- `CRYPT32!CertCloseStore` at `0x1800bada3`
- `CRYPT32!CertCloseStore` at `0x1800bada3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bad5b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bad5b`

## string_xrefs

- `0x1800bb354`: `kerberos.dll`
- `0x1800bb076`: `dhKey already expired\n`
- `0x1800bb2e0`: `%hs - Credential isolation is incompatible with RSA-encrypted AS replies\n`

## pseudocode

```c

```
