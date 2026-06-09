# CreateUserBlobWithHashAndIdentity(ulong,_EAPTLS_HASH *,ushort *,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const *)

- ea: `0x18006ec4c`
- end: `0x18006edff`
- name: `?CreateUserBlobWithHashAndIdentity@@YAKKPEAU_EAPTLS_HASH@@PEAGPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBU_CERT_CONTEXT@@@Z`
- size: `435`
- prototype: `unsigned int(unsigned int, struct _EAPTLS_HASH *, unsigned __int16 *, struct _EAPTLS_USER_PROPERTIES **, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18006f550`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18002c710`
- `0x180034324`
- `0x18006ec4c`
- `0x18007042c`
- `0x180070c8c`
- `0x1800718ac`
- `0x18007431c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ede6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ede6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006ecf2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006ecf2`

## pseudocode

```c

```
