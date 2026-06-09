# PrCreatePropertySet(IMappedStream *,ushort,_GUID const *,_GUID const *,PMemoryAllocator *,ulong,ulong *,ushort *,ulong *,CPropertySetStream * *)

- ea: `0x180030534`
- end: `0x180030744`
- name: `?PrCreatePropertySet@@YAJPEAVIMappedStream@@GPEBU_GUID@@1PEAVPMemoryAllocator@@KPEAKPEAG3PEAPEAVCPropertySetStream@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct IMappedStream *, unsigned __int16, const struct _GUID *, const struct _GUID *, struct PMemoryAllocator *, unsigned int, unsigned int *, unsigned __int16 *, unsigned int *, struct CPropertySetStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800303f4`

## callees

- `0x180030534`
- `0x18003074c`
- `0x180036f50`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030633`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030633`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180030669`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180030669`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18003065f`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18003065f`

## pseudocode

```c

```
