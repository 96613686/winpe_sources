# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x180023fa0`
- end: `0x1800240d3`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180023e0c`

## callees

- `0x180023fa0`
- `0x1800240dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002409e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002409e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ffa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023feb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002408f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023feb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002408f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800240bc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800240bc`
- `CRYPT32!CertCloseStore` at `0x1800240ae`
- `CRYPT32!CertCloseStore` at `0x1800240ae`
- `DMCmnUtils!HexStringToBinary` at `0x180023fd8`
- `DMCmnUtils!HexStringToBinary` at `0x180024021`
- `DMCmnUtils!HexStringToBinary` at `0x180023fd8`
- `DMCmnUtils!HexStringToBinary` at `0x180024021`

## pseudocode

```c

```
