# MakeVerbList(IOleVerbIterator *,_GUID const &,VerbList * *)

- ea: `0x18009dec4`
- end: `0x18009e3c4`
- name: `?MakeVerbList@@YAJPEAUIOleVerbIterator@@AEBU_GUID@@PEAPEAUVerbList@@@Z`
- size: `1280`
- prototype: `HRESULT __fastcall(IOleVerbIterator *verbIterator, const _GUID *clsid, VerbList **verbList)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009e4c4`

## callees

- `0x18001217c`
- `0x18001a630`
- `0x1800205a0`
- `0x18002c6a0`
- `0x180033bb0`
- `0x180046460`
- `0x18009de04`
- `0x18009dec4`
- `0x1800c8934`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e349`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e349`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009df71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e0a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e0f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009df71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e0a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e0f1`

## string_xrefs

- `0x18009df8e`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009e265`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009e319`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009e38b`: `com\ole32\ole232\stdimpl\oregverb.cpp`

## pseudocode

```c

```
