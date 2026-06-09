# Base64ToIStream(ushort *,unsigned __int64,IStream * *)

- ea: `0x18005603c`
- end: `0x180056224`
- name: `?Base64ToIStream@@YAJPEAG_KPEAPEAUIStream@@@Z`
- size: `488`
- prototype: `HRESULT __fastcall(wchar_t *pszEncoded, unsigned __int64 cchEncoded, IStream **ppStream)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180053de0`

## callees

- `0x1800077fc`
- `0x18005603c`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800560de`
- `KERNELBASE!GlobalAlloc` at `0x1800560de`
- `KERNELBASE!GlobalFree` at `0x1800561dd`
- `KERNELBASE!GlobalFree` at `0x1800561dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560f2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005616c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800561c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005616c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800561c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056119`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056119`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056189`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056189`
- `ServicingCommon!RtlDecodeBase64LUnicodeStringToLBlob` at `0x180056145`
- `ServicingCommon!RtlDecodeBase64LUnicodeStringToLBlob` at `0x180056145`

## pseudocode

```c

```
