# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x1800cdfec`
- end: `0x1800ce150`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800cddfc`

## callees

- `0x1800cdfec`
- `0x1800ce158`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ce052`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ce052`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce108`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce03d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce0f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce03d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce0f3`
- `CRYPT32!CertCloseStore` at `0x1800ce11e`
- `CRYPT32!CertCloseStore` at `0x1800ce11e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ce132`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ce132`
- `DMCmnUtils!HexStringToBinary` at `0x1800ce024`
- `DMCmnUtils!HexStringToBinary` at `0x1800ce07f`
- `DMCmnUtils!HexStringToBinary` at `0x1800ce024`
- `DMCmnUtils!HexStringToBinary` at `0x1800ce07f`

## pseudocode

```c

```
