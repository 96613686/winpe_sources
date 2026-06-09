# URLStream::newStreamDefered(bool,IInternetSecurityManager *,ushort const *,IURLDownloadTask *,ushort const *,ushort const *,ushort const *,IMoniker *,IBindCtx *,ulong,IURLStream * *,bool)

- ea: `0x180026adc`
- end: `0x180026dbc`
- name: `?newStreamDefered@URLStream@@SAJ_NPEAUIInternetSecurityManager@@PEBGPEAUIURLDownloadTask@@222PEAUIMoniker@@PEAUIBindCtx@@KPEAPEAUIURLStream@@0@Z`
- size: `736`
- prototype: `__int64 __fastcall(bool fSecure, IInternetSecurityManager *pSecMgr, const wchar_t *secureBaseURL, IURLDownloadTask *task, wchar_t *relativeURL, wchar_t *baseURL1, const wchar_t *baseURL2, IMoniker *pmk, IBindCtx *lpbc, unsigned int flags, URLStream **ppStream, bool fDTD)`
- caller_count: `3`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800269fc`
- `0x18015f8a0`
- `0x18015fd20`

## callees

- `0x18000ae54`
- `0x180026adc`
- `0x18002b064`
- `0x18003617c`
- `0x180039bc8`
- `0x180063d8c`
- `0x180064030`
- `0x1800848b4`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800a4b0c`
- `0x1800bc3b0`
- `0x1800bc3e8`
- `0x1800c3c0c`
- `0x1801538b4`
- `0x18015bd7c`
- `0x18015bfb8`
- `0x18015c258`
- `0x18015cdb4`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c45`

## pseudocode

```c

```
