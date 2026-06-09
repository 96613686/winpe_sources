# CryptXMLSignHelper(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18001b098`
- end: `0x18001b1ff`
- name: `?CryptXMLSignHelper@@YAJPEBG000PEAPEAG@Z`
- size: `359`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800226a4`
- `0x180022e74`

## callees

- `0x18001b098`
- `0x18001b208`
- `0x18001b5d0`
- `0x18001d1bc`
- `0x18003b750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b198`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b198`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b184`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b184`
- `CRYPT32!CertFreeCertificateChain` at `0x18001b1ad`
- `CRYPT32!CertFreeCertificateChain` at `0x18001b1ad`
- `CRYPT32!CertFreeCertificateContext` at `0x18001b1da`
- `CRYPT32!CertFreeCertificateContext` at `0x18001b1da`
- `CRYPT32!CertCloseStore` at `0x18001b1c4`
- `CRYPT32!CertCloseStore` at `0x18001b1c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b173`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b173`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b154`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b154`

## pseudocode

```c

```
