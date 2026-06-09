# ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)

- ea: `0x180036820`
- end: `0x18003698e`
- name: `?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `366`
- prototype: `int(unsigned int, void *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180032404`

## callees

- `0x180036820`
- `0x18006d0a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003696d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003696d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003692c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003692c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003694b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003694b`
- `CRYPT32!CryptMsgControl` at `0x180036905`
- `CRYPT32!CryptMsgControl` at `0x180036905`
- `CRYPT32!CryptMsgGetParam` at `0x180036875`
- `CRYPT32!CryptMsgGetParam` at `0x180036875`
- `CRYPT32!CertCloseStore` at `0x18003695b`
- `CRYPT32!CertCloseStore` at `0x18003695b`
- `CRYPT32!CertOpenStore` at `0x1800368b8`
- `CRYPT32!CertOpenStore` at `0x1800368b8`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x1800368d1`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x1800368d1`
- `CRYPT32!CertFreeCertificateContext` at `0x18003693d`
- `CRYPT32!CertFreeCertificateContext` at `0x18003693d`

## pseudocode

```c

```
