# CAsyncBoundaryLayer::ReceiveCrossProcessRequest(_IsoMessage *,bool,ulong)

- ea: `0x180034518`
- end: `0x18003478d`
- name: `?ReceiveCrossProcessRequest@CAsyncBoundaryLayer@@QEAAJPEAU_IsoMessage@@_NK@Z`
- size: `629`
- prototype: `__int64 __fastcall(CAsyncBoundaryLayer *__hidden this, struct _IsoMessage *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180031fb0`

## callees

- `0x180034518`
- `0x180034794`
- `0x180034ce8`
- `0x180091010`
- `0x180298178`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18003458e`
- `KERNEL32!LeaveCriticalSection` at `0x180034671`
- `KERNEL32!LeaveCriticalSection` at `0x180034756`
- `KERNEL32!LeaveCriticalSection` at `0x18003458e`
- `KERNEL32!LeaveCriticalSection` at `0x180034671`
- `KERNEL32!LeaveCriticalSection` at `0x180034756`
- `KERNEL32!EnterCriticalSection` at `0x180034544`
- `KERNEL32!EnterCriticalSection` at `0x180034649`
- `KERNEL32!EnterCriticalSection` at `0x18003472e`
- `KERNEL32!EnterCriticalSection` at `0x180034544`
- `KERNEL32!EnterCriticalSection` at `0x180034649`
- `KERNEL32!EnterCriticalSection` at `0x18003472e`
- `USER32!PostMessageW` at `0x1800346a8`
- `USER32!PostMessageW` at `0x1800346a8`
- `iertutil!__imp_DPA_Create` at `0x180034558`
- `iertutil!__imp_DPA_Create` at `0x18003456d`
- `iertutil!__imp_DPA_Create` at `0x180034558`
- `iertutil!__imp_DPA_Create` at `0x18003456d`
- `iertutil!__imp_DPA_InsertPtr` at `0x18003465b`
- `iertutil!__imp_DPA_InsertPtr` at `0x180034740`
- `iertutil!__imp_DPA_InsertPtr` at `0x18003465b`
- `iertutil!__imp_DPA_InsertPtr` at `0x180034740`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180034620`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180034705`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180034620`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180034705`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003462f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180034714`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003462f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180034714`

## pseudocode

```c

```
