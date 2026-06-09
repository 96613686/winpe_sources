# wCreatePackageEx(IDataObject *,_GUID const &,ulong,ulong,ulong,ulong *,tagFORMATETC *,IAdviseSink *,ulong *,IOleClientSite *,IStorage *,int,void * *)

- ea: `0x18007c2d0`
- end: `0x18007c550`
- name: `?wCreatePackageEx@@YAJPEAUIDataObject@@AEBU_GUID@@KKKPEAKPEAUtagFORMATETC@@PEAUIAdviseSink@@2PEAUIOleClientSite@@PEAUIStorage@@HPEAPEAX@Z`
- size: `640`
- prototype: `HRESULT __fastcall(IDataObject *lpSrcDataObj, const _GUID *iid, unsigned int dwFlags, unsigned int renderopt, unsigned int cFormats, unsigned int *rgAdvf, tagFORMATETC *rgFormatEtc, IAdviseSink *lpAdviseSink, unsigned int *rgdwConnection, IOleClientSite *lpClientSite, IStorage *lpStg, int fLink, void **lplpObj)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18007db40`
- `0x18007e370`

## callees

- `0x180008d60`
- `0x180046460`
- `0x18007c2d0`
- `0x18007de40`
- `0x18007e700`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007c40e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007c40e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007c423`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007c50d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007c423`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007c50d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007c3e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007c44e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007c3e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007c44e`

## pseudocode

```c

```
