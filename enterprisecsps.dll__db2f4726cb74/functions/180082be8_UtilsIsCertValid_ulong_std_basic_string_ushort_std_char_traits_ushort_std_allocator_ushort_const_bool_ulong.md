# UtilsIsCertValid(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &,ulong &)

- ea: `0x180082be8`
- end: `0x180082e5c`
- name: `?UtilsIsCertValid@@YAJKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAK@Z`
- size: `628`
- prototype: `__int64 __fastcall(DWORD dwFlags)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180080630`

## callees

- `0x18002031c`
- `0x1800828e0`
- `0x180082be8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082cb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082cb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082c9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082dd9`
- `CRYPT32!CertCloseStore` at `0x180082e23`
- `CRYPT32!CertCloseStore` at `0x180082e23`
- `CRYPT32!CertOpenStore` at `0x180082c35`
- `CRYPT32!CertOpenStore` at `0x180082c35`
- `CRYPT32!CertFreeCertificateContext` at `0x180082e37`
- `CRYPT32!CertFreeCertificateContext` at `0x180082e37`
- `CRYPT32!CertFindCertificateInStore` at `0x180082d29`
- `CRYPT32!CertFindCertificateInStore` at `0x180082d29`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180082d95`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180082d95`
- `ncrypt!NCryptFreeObject` at `0x180082dfd`
- `ncrypt!NCryptFreeObject` at `0x180082dfd`
- `CRYPTSP!CryptReleaseContext` at `0x180082e0d`
- `CRYPTSP!CryptReleaseContext` at `0x180082e0d`
- `DMCmnUtils!HexStringToBinary` at `0x180082c85`
- `DMCmnUtils!HexStringToBinary` at `0x180082cf1`
- `DMCmnUtils!HexStringToBinary` at `0x180082c85`
- `DMCmnUtils!HexStringToBinary` at `0x180082cf1`

## pseudocode

```c

```
