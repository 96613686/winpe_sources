# CSharedComponentPatchManager::GetHighestVersionedClientForComponent(IMsiString const &,IMsiString const &,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,bool *,ulong *,ulong *)

- ea: `0x18015d134`
- end: `0x18015df1d`
- name: `?GetHighestVersionedClientForComponent@CSharedComponentPatchManager@@QEAAPEAVIMsiRecord@@AEBVIMsiString@@0PEAPEBV3@11111111PEA_NPEAK3@Z`
- size: `3561`
- prototype: `struct IMsiRecord *__fastcall(CSharedComponentPatchManager *__hidden this, const struct IMsiString *, const struct IMsiString *, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, const struct IMsiString **, bool *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f3a78`
- `0x180215ef8`

## callees

- `0x180019290`
- `0x1800399d0`
- `0x18003bd60`
- `0x18003c030`
- `0x1800408a0`
- `0x180040908`
- `0x1800491f0`
- `0x18008d650`
- `0x1800ae46c`
- `0x1800b164c`
- `0x18015d134`
- `0x18015df24`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18015d473`
- `ADVAPI32!RegEnumKeyExW` at `0x18015d473`
- `KERNEL32!InitializeCriticalSection` at `0x18015d250`
- `KERNEL32!InitializeCriticalSection` at `0x18015d387`
- `KERNEL32!InitializeCriticalSection` at `0x18015d250`
- `KERNEL32!InitializeCriticalSection` at `0x18015d387`
- `KERNEL32!GlobalFree` at `0x18015d8bd`
- `KERNEL32!GlobalFree` at `0x18015d8e2`
- `KERNEL32!GlobalFree` at `0x18015d90d`
- `KERNEL32!GlobalFree` at `0x18015d941`
- `KERNEL32!GlobalFree` at `0x18015d975`
- `KERNEL32!GlobalFree` at `0x18015d9a9`
- `KERNEL32!GlobalFree` at `0x18015d9dd`
- `KERNEL32!GlobalFree` at `0x18015da11`
- `KERNEL32!GlobalFree` at `0x18015da45`
- `KERNEL32!GlobalFree` at `0x18015da79`
- `KERNEL32!GlobalFree` at `0x18015dacc`
- `KERNEL32!GlobalFree` at `0x18015daec`
- `KERNEL32!GlobalFree` at `0x18015db12`
- `KERNEL32!GlobalFree` at `0x18015db41`
- `KERNEL32!GlobalFree` at `0x18015db70`
- `KERNEL32!GlobalFree` at `0x18015db9f`
- `KERNEL32!GlobalFree` at `0x18015dbce`
- `KERNEL32!GlobalFree` at `0x18015dbfd`
- `KERNEL32!GlobalFree` at `0x18015dc2c`
- `KERNEL32!GlobalFree` at `0x18015dc5b`
- `KERNEL32!GlobalFree` at `0x18015de87`
- `KERNEL32!GlobalFree` at `0x18015debb`
- `KERNEL32!GlobalFree` at `0x18015d8bd`
- `KERNEL32!GlobalFree` at `0x18015d8e2`
- `KERNEL32!GlobalFree` at `0x18015d90d`
- `KERNEL32!GlobalFree` at `0x18015d941`
- `KERNEL32!GlobalFree` at `0x18015d975`
- `KERNEL32!GlobalFree` at `0x18015d9a9`
- `KERNEL32!GlobalFree` at `0x18015d9dd`
- `KERNEL32!GlobalFree` at `0x18015da11`
- `KERNEL32!GlobalFree` at `0x18015da45`
- `KERNEL32!GlobalFree` at `0x18015da79`
- `KERNEL32!GlobalFree` at `0x18015dacc`
- `KERNEL32!GlobalFree` at `0x18015daec`
- `KERNEL32!GlobalFree` at `0x18015db12`
- `KERNEL32!GlobalFree` at `0x18015db41`
- `KERNEL32!GlobalFree` at `0x18015db70`
- `KERNEL32!GlobalFree` at `0x18015db9f`
- `KERNEL32!GlobalFree` at `0x18015dbce`
- `KERNEL32!GlobalFree` at `0x18015dbfd`
- `KERNEL32!GlobalFree` at `0x18015dc2c`
- `KERNEL32!GlobalFree` at `0x18015dc5b`
- `KERNEL32!GlobalFree` at `0x18015de87`
- `KERNEL32!GlobalFree` at `0x18015debb`

## string_xrefs

- `0x18015d564`: `SharedComponent`
- `0x18015d51a`: `ComponentVersion`

## pseudocode

```c

```
