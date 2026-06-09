# wCreatePackageEx(IDataObject *,_GUID const &,ulong,ulong,ulong,ulong *,tagFORMATETC *,IAdviseSink *,ulong *,IOleClientSite *,IStorage *,int,void * *)

- ea: `0x180082718`
- end: `0x18008297e`
- name: `?wCreatePackageEx@@YAJPEAUIDataObject@@AEBU_GUID@@KKKPEAKPEAUtagFORMATETC@@PEAUIAdviseSink@@2PEAUIOleClientSite@@PEAUIStorage@@HPEAPEAX@Z`
- size: `614`
- prototype: `HRESULT __fastcall(IDataObject *lpSrcDataObj, const _GUID *iid, unsigned int dwFlags, unsigned int renderopt, unsigned int cFormats, unsigned int *rgAdvf, tagFORMATETC *rgFormatEtc, IAdviseSink *lpAdviseSink, unsigned int *rgdwConnection, IOleClientSite *lpClientSite, IStorage *lpStg, int fLink, void **lplpObj)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18003e2b0`
- `0x180083f50`

## callees

- `0x18000aab0`
- `0x18003e020`
- `0x180052390`
- `0x180082718`
- `0x1800842e0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180082855`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180082855`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180082864`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180082942`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180082864`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180082942`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180082832`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180082889`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180082832`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180082889`

## pseudocode

```c

```
