# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x18006fdd8`
- end: `0x18006ff43`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `363`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `9`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001d724`
- `0x18002d48c`
- `0x1800423b0`
- `0x180043ad8`
- `0x180044878`
- `0x180044958`
- `0x18004e514`
- `0x18004fc9c`
- `0x18005d80c`

## callees

- `0x18006fdd8`
- `0x18006ff4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fe28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fefd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fe28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fefd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fe37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fe37`
- `CRYPT32!CertCloseStore` at `0x18006ff1c`
- `CRYPT32!CertCloseStore` at `0x18006ff1c`
- `CRYPT32!CertFreeCertificateContext` at `0x18006ff2a`
- `CRYPT32!CertFreeCertificateContext` at `0x18006ff2a`
- `DMCmnUtils!HexStringToBinary` at `0x18006fe15`
- `DMCmnUtils!HexStringToBinary` at `0x18006fe61`
- `DMCmnUtils!HexStringToBinary` at `0x18006fe15`
- `DMCmnUtils!HexStringToBinary` at `0x18006fe61`

## pseudocode

```c

```
