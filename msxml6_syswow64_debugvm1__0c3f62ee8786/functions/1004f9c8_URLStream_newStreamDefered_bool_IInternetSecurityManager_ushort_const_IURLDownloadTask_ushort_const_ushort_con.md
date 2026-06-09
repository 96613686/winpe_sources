# URLStream::newStreamDefered(bool,IInternetSecurityManager *,ushort const *,IURLDownloadTask *,ushort const *,ushort const *,ushort const *,IMoniker *,IBindCtx *,ulong,IURLStream * *,bool)

- ea: `0x1004f9c8`
- end: `0x1004fbdd`
- name: `?newStreamDefered@URLStream@@SGJ_NPAUIInternetSecurityManager@@PBGPAUIURLDownloadTask@@222PAUIMoniker@@PAUIBindCtx@@KPAPAUIURLStream@@0@Z`
- size: `533`
- prototype: `HRESULT __userpurge@<eax>(bool fSecure@<cl>, IInternetSecurityManager *pSecMgr@<edx>, const wchar_t *secureBaseURL, IURLDownloadTask *task, const wchar_t *relativeURL, const wchar_t *baseURL1, const wchar_t *baseURL2, IMoniker *pmk, IBindCtx *lpbc, unsigned int flags, IURLStream **ppStream, bool fDTD)`
- caller_count: `3`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004eedb`
- `0x10143470`
- `0x10143a16`

## callees

- `0x1003f548`
- `0x10040dee`
- `0x1004f9c8`
- `0x10054319`
- `0x10054dcb`
- `0x10064cf1`
- `0x10064d24`
- `0x100656cb`
- `0x10065f14`
- `0x10067bc0`
- `0x1006c080`
- `0x10076046`
- `0x100779c5`
- `0x10077a1b`
- `0x101314e1`
- `0x10131656`
- `0x1013d500`
- `0x1013d56a`
- `0x1013d714`
- `0x1013d932`
- `0x1013e234`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1004fa4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1004fa4e`

## pseudocode

```c

```
