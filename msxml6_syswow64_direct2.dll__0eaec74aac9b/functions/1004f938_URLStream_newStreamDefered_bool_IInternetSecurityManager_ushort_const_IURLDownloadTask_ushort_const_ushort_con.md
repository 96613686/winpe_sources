# URLStream::newStreamDefered(bool,IInternetSecurityManager *,ushort const *,IURLDownloadTask *,ushort const *,ushort const *,ushort const *,IMoniker *,IBindCtx *,ulong,IURLStream * *,bool)

- ea: `0x1004f938`
- end: `0x1004fb4d`
- name: `?newStreamDefered@URLStream@@SGJ_NPAUIInternetSecurityManager@@PBGPAUIURLDownloadTask@@222PAUIMoniker@@PAUIBindCtx@@KPAPAUIURLStream@@0@Z`
- size: `533`
- prototype: `HRESULT __userpurge@<eax>(bool fSecure@<cl>, IInternetSecurityManager *pSecMgr@<edx>, const wchar_t *secureBaseURL, IURLDownloadTask *task, const wchar_t *relativeURL, const wchar_t *baseURL1, const wchar_t *baseURL2, IMoniker *pmk, IBindCtx *lpbc, unsigned int flags, IURLStream **ppStream, bool fDTD)`
- caller_count: `3`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004ee4b`
- `0x10143580`
- `0x10143b26`

## callees

- `0x1003f4b8`
- `0x10040d5e`
- `0x1004f938`
- `0x10054289`
- `0x10054d3b`
- `0x10064c51`
- `0x10064c84`
- `0x1006562b`
- `0x10065e74`
- `0x10067b20`
- `0x1006bff0`
- `0x10076076`
- `0x100779f5`
- `0x10077a4b`
- `0x101315f1`
- `0x10131766`
- `0x1013d610`
- `0x1013d67a`
- `0x1013d824`
- `0x1013da42`
- `0x1013e344`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1004f9be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1004f9be`

## pseudocode

```c

```
