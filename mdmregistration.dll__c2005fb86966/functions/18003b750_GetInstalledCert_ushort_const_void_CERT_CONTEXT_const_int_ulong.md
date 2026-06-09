# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x18003b750`
- end: `0x18003b8b4`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001b098`
- `0x18002c37c`

## callees

- `0x18003b750`
- `0x18003b8bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b7b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b7b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b86c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b86c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b7a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b7a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b857`
- `DMCmnUtils!HexStringToBinary` at `0x18003b788`
- `DMCmnUtils!HexStringToBinary` at `0x18003b7e3`
- `DMCmnUtils!HexStringToBinary` at `0x18003b788`
- `DMCmnUtils!HexStringToBinary` at `0x18003b7e3`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b896`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b896`
- `CRYPT32!CertCloseStore` at `0x18003b882`
- `CRYPT32!CertCloseStore` at `0x18003b882`

## pseudocode

```c

```
