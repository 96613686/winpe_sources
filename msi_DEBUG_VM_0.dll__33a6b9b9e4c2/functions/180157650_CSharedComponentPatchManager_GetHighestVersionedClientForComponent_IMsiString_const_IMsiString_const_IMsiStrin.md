# CSharedComponentPatchManager::GetHighestVersionedClientForComponent(IMsiString const &,IMsiString const &,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,bool *,ulong *,ulong *)

- ea: `0x180157650`
- end: `0x1801583a2`
- name: `?GetHighestVersionedClientForComponent@CSharedComponentPatchManager@@QEAAPEAVIMsiRecord@@AEBVIMsiString@@0PEAPEBV3@11111111PEA_NPEAK3@Z`
- size: `3410`
- prototype: `struct IMsiRecord *__fastcall(CSharedComponentPatchManager *__hidden this, const struct IMsiString *, const struct IMsiString *, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, bool *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800eb9f0`
- `0x18020c68c`

## callees

- `0x180015690`
- `0x180015950`
- `0x180019b60`
- `0x180019bb4`
- `0x180043660`
- `0x18004b560`
- `0x180050cf0`
- `0x1800616e0`
- `0x1800a5fc4`
- `0x1800ae018`
- `0x180157650`
- `0x1801583a8`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180157983`
- `ADVAPI32!RegEnumKeyExW` at `0x180157983`
- `KERNEL32!InitializeCriticalSection` at `0x18015776c`
- `KERNEL32!InitializeCriticalSection` at `0x18015789d`
- `KERNEL32!InitializeCriticalSection` at `0x18015776c`
- `KERNEL32!InitializeCriticalSection` at `0x18015789d`
- `KERNEL32!GlobalFree` at `0x180157dc7`
- `KERNEL32!GlobalFree` at `0x180157de6`
- `KERNEL32!GlobalFree` at `0x180157e0b`
- `KERNEL32!GlobalFree` at `0x180157e39`
- `KERNEL32!GlobalFree` at `0x180157e67`
- `KERNEL32!GlobalFree` at `0x180157e95`
- `KERNEL32!GlobalFree` at `0x180157ec3`
- `KERNEL32!GlobalFree` at `0x180157ef1`
- `KERNEL32!GlobalFree` at `0x180157f1f`
- `KERNEL32!GlobalFree` at `0x180157f4d`
- `KERNEL32!GlobalFree` at `0x180157f9a`
- `KERNEL32!GlobalFree` at `0x180157fb4`
- `KERNEL32!GlobalFree` at `0x180157fd4`
- `KERNEL32!GlobalFree` at `0x180157ffd`
- `KERNEL32!GlobalFree` at `0x180158026`
- `KERNEL32!GlobalFree` at `0x18015804f`
- `KERNEL32!GlobalFree` at `0x180158078`
- `KERNEL32!GlobalFree` at `0x1801580a1`
- `KERNEL32!GlobalFree` at `0x1801580ca`
- `KERNEL32!GlobalFree` at `0x1801580f3`
- `KERNEL32!GlobalFree` at `0x180158319`
- `KERNEL32!GlobalFree` at `0x180158347`
- `KERNEL32!GlobalFree` at `0x180157dc7`
- `KERNEL32!GlobalFree` at `0x180157de6`
- `KERNEL32!GlobalFree` at `0x180157e0b`
- `KERNEL32!GlobalFree` at `0x180157e39`
- `KERNEL32!GlobalFree` at `0x180157e67`
- `KERNEL32!GlobalFree` at `0x180157e95`
- `KERNEL32!GlobalFree` at `0x180157ec3`
- `KERNEL32!GlobalFree` at `0x180157ef1`
- `KERNEL32!GlobalFree` at `0x180157f1f`
- `KERNEL32!GlobalFree` at `0x180157f4d`
- `KERNEL32!GlobalFree` at `0x180157f9a`
- `KERNEL32!GlobalFree` at `0x180157fb4`
- `KERNEL32!GlobalFree` at `0x180157fd4`
- `KERNEL32!GlobalFree` at `0x180157ffd`
- `KERNEL32!GlobalFree` at `0x180158026`
- `KERNEL32!GlobalFree` at `0x18015804f`
- `KERNEL32!GlobalFree` at `0x180158078`
- `KERNEL32!GlobalFree` at `0x1801580a1`
- `KERNEL32!GlobalFree` at `0x1801580ca`
- `KERNEL32!GlobalFree` at `0x1801580f3`
- `KERNEL32!GlobalFree` at `0x180158319`
- `KERNEL32!GlobalFree` at `0x180158347`

## string_xrefs

- `0x180157a6e`: `SharedComponent`
- `0x180157a24`: `ComponentVersion`

## pseudocode

```c

```
