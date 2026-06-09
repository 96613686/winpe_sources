# MakeVerbList(IOleVerbIterator *,_GUID const &,VerbList * *)

- ea: `0x18004cb14`
- end: `0x18004d01e`
- name: `?MakeVerbList@@YAJPEAUIOleVerbIterator@@AEBU_GUID@@PEAPEAUVerbList@@@Z`
- size: `1290`
- prototype: `HRESULT __fastcall(IOleVerbIterator *verbIterator, const _GUID *clsid, VerbList **verbList)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009baa0`

## callees

- `0x1800185ec`
- `0x18001b0e4`
- `0x18001b810`
- `0x18001e420`
- `0x1800289f8`
- `0x1800470d4`
- `0x18004cb14`
- `0x180052390`
- `0x1800bf6c4`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ceca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cf9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ceca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cf9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cbc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cceb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cd2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cbc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cceb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cd2e`

## string_xrefs

- `0x18004cc14`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18004ce9d`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18004cf71`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18004cfe6`: `com\ole32\ole232\stdimpl\oregverb.cpp`

## pseudocode

```c

```
