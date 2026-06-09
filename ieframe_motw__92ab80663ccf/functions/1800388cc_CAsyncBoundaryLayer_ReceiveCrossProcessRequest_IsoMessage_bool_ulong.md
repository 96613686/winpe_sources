# CAsyncBoundaryLayer::ReceiveCrossProcessRequest(_IsoMessage *,bool,ulong)

- ea: `0x1800388cc`
- end: `0x180038ba4`
- name: `?ReceiveCrossProcessRequest@CAsyncBoundaryLayer@@QEAAJPEAU_IsoMessage@@_NK@Z`
- size: `728`
- prototype: `__int64 __fastcall(CAsyncBoundaryLayer *__hidden this, struct _IsoMessage *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180036070`

## callees

- `0x1800388cc`
- `0x180038bac`
- `0x18003917c`
- `0x180097a54`
- `0x1802bb878`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180038954`
- `KERNEL32!LeaveCriticalSection` at `0x180038a59`
- `KERNEL32!LeaveCriticalSection` at `0x180038b66`
- `KERNEL32!LeaveCriticalSection` at `0x180038954`
- `KERNEL32!LeaveCriticalSection` at `0x180038a59`
- `KERNEL32!LeaveCriticalSection` at `0x180038b66`
- `KERNEL32!EnterCriticalSection` at `0x1800388f8`
- `KERNEL32!EnterCriticalSection` at `0x180038a25`
- `KERNEL32!EnterCriticalSection` at `0x180038b32`
- `KERNEL32!EnterCriticalSection` at `0x1800388f8`
- `KERNEL32!EnterCriticalSection` at `0x180038a25`
- `KERNEL32!EnterCriticalSection` at `0x180038b32`
- `USER32!PostMessageW` at `0x180038a96`
- `USER32!PostMessageW` at `0x180038a96`
- `iertutil!__imp_DPA_Create` at `0x180038912`
- `iertutil!__imp_DPA_Create` at `0x18003892d`
- `iertutil!__imp_DPA_Create` at `0x180038912`
- `iertutil!__imp_DPA_Create` at `0x18003892d`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038a3d`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038b4a`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038a3d`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038b4a`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1800389f0`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038afd`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1800389f0`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038afd`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180038a05`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180038b12`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180038a05`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180038b12`

## pseudocode

```c

```
