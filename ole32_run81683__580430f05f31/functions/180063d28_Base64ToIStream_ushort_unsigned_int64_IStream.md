# Base64ToIStream(ushort *,unsigned __int64,IStream * *)

- ea: `0x180063d28`
- end: `0x180063ed0`
- name: `?Base64ToIStream@@YAJPEAG_KPEAPEAUIStream@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(wchar_t *pszEncoded, unsigned __int64 cchEncoded, IStream **ppStream)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180061cf0`

## callees

- `0x180009374`
- `0x180063d28`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180063dbf`
- `KERNELBASE!GlobalAlloc` at `0x180063dbf`
- `KERNELBASE!GlobalFree` at `0x180063e9d`
- `KERNELBASE!GlobalFree` at `0x180063e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063dcd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063e38`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063e87`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063e38`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063e87`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063dee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063dee`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180063e52`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180063e52`
- `ServicingCommon!RtlDecodeBase64LUnicodeStringToLBlob` at `0x180063e17`
- `ServicingCommon!RtlDecodeBase64LUnicodeStringToLBlob` at `0x180063e17`

## pseudocode

```c

```
