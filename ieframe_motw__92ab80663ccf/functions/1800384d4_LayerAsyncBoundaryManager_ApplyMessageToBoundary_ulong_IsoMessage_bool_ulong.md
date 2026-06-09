# LayerAsyncBoundaryManager::ApplyMessageToBoundary(ulong,_IsoMessage *,bool,ulong)

- ea: `0x1800384d4`
- end: `0x1800387c2`
- name: `?ApplyMessageToBoundary@LayerAsyncBoundaryManager@@YAJKPEAU_IsoMessage@@_NK@Z`
- size: `750`
- prototype: `int(LayerAsyncBoundaryManager *__hidden this, unsigned int, struct _IsoMessage *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1801f8350`

## callees

- `0x1800384d4`
- `0x180038bac`
- `0x18003917c`
- `0x180039d38`
- `0x18008d394`
- `0x180097a54`
- `0x1802bb878`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180038697`
- `KERNEL32!LeaveCriticalSection` at `0x180038776`
- `KERNEL32!LeaveCriticalSection` at `0x1800387a4`
- `KERNEL32!LeaveCriticalSection` at `0x180038697`
- `KERNEL32!LeaveCriticalSection` at `0x180038776`
- `KERNEL32!LeaveCriticalSection` at `0x1800387a4`
- `KERNEL32!EnterCriticalSection` at `0x1800384fb`
- `KERNEL32!EnterCriticalSection` at `0x18003865f`
- `KERNEL32!EnterCriticalSection` at `0x18003873e`
- `KERNEL32!EnterCriticalSection` at `0x1800384fb`
- `KERNEL32!EnterCriticalSection` at `0x18003865f`
- `KERNEL32!EnterCriticalSection` at `0x18003873e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180038525`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180038553`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180038525`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180038553`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038677`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038756`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038677`
- `iertutil!__imp_DPA_InsertPtr` at `0x180038756`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038626`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038705`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038626`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180038705`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003863b`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003871a`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003863b`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18003871a`

## pseudocode

```c

```
