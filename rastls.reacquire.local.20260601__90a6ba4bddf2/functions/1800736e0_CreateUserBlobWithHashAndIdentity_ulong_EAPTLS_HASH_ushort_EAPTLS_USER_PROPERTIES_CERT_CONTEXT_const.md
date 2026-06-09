# CreateUserBlobWithHashAndIdentity(ulong,_EAPTLS_HASH *,ushort *,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const *)

- ea: `0x1800736e0`
- end: `0x1800738ac`
- name: `?CreateUserBlobWithHashAndIdentity@@YAKKPEAU_EAPTLS_HASH@@PEAGPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBU_CERT_CONTEXT@@@Z`
- size: `460`
- prototype: `unsigned int(unsigned int, struct _EAPTLS_HASH *, unsigned __int16 *, struct _EAPTLS_USER_PROPERTIES **, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180074168`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18002e900`
- `0x180036ee8`
- `0x1800736e0`
- `0x18007510c`
- `0x180075a04`
- `0x180076704`
- `0x18007956c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007381a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007388c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007381a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007388c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180073786`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180073786`

## pseudocode

```c

```
