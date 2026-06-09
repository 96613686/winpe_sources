# URLStream::newStreamDefered(bool,IInternetSecurityManager *,ushort const *,IURLDownloadTask *,ushort const *,ushort const *,ushort const *,IMoniker *,IBindCtx *,ulong,IURLStream * *,bool)

- ea: `0x18003b8d0`
- end: `0x18003bbbd`
- name: `?newStreamDefered@URLStream@@SAJ_NPEAUIInternetSecurityManager@@PEBGPEAUIURLDownloadTask@@222PEAUIMoniker@@PEAUIBindCtx@@KPEAPEAUIURLStream@@0@Z`
- size: `749`
- prototype: `HRESULT __fastcall(bool fSecure, IInternetSecurityManager *pSecMgr, const wchar_t *secureBaseURL, IURLDownloadTask *task, const wchar_t *relativeURL, const wchar_t *baseURL1, const wchar_t *baseURL2, IMoniker *pmk, IBindCtx *lpbc, unsigned int flags, IURLStream **ppStream, bool fDTD)`
- caller_count: `3`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b7f0`
- `0x1801632b0`
- `0x180163770`

## callees

- `0x1800101e4`
- `0x180017480`
- `0x1800353f0`
- `0x1800391e0`
- `0x18003b8d0`
- `0x180083f24`
- `0x18009402c`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800a4308`
- `0x1800acbd0`
- `0x1800bda08`
- `0x1800bda40`
- `0x1800c55c8`
- `0x180156df8`
- `0x18015f5ac`
- `0x18015f7f4`
- `0x18015faa8`
- `0x1801606f4`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b9a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ba3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b9a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ba3f`

## pseudocode

```c

```
