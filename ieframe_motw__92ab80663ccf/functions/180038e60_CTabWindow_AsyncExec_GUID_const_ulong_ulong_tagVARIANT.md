# CTabWindow::AsyncExec(_GUID const *,ulong,ulong,tagVARIANT *)

- ea: `0x180038e60`
- end: `0x180039174`
- name: `?AsyncExec@CTabWindow@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@@Z`
- size: `788`
- prototype: `int(CTabWindow *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *)`
- caller_count: `17`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4950`
- `0x180259ef0`
- `0x18026ef50`
- `0x180274570`
- `0x180275ba8`
- `0x1802764b4`
- `0x1802772c0`
- `0x180278bf4`
- `0x180279558`
- `0x180279860`
- `0x18027c560`
- `0x180281044`
- `0x1802a5d38`
- `0x1802a63b4`
- `0x1802ab08c`
- `0x1802ab128`
- `0x1802ae1d4`

## callees

- `0x180038e60`
- `0x1800393c8`
- `0x180039588`
- `0x18009493c`
- `0x18046f0c4`

## import_xrefs

- `USER32!GetKeyState` at `0x180038fd8`
- `USER32!GetKeyState` at `0x180038fd8`
- `USER32!PostMessageW` at `0x180039044`
- `USER32!PostMessageW` at `0x180039044`
- `USER32!AllowSetForegroundWindow` at `0x180038fec`
- `USER32!AllowSetForegroundWindow` at `0x180038fec`
- `OLEAUT32!__imp_VariantClear` at `0x180039108`
- `OLEAUT32!__imp_VariantClear` at `0x18003914a`
- `OLEAUT32!__imp_VariantClear` at `0x180039108`
- `OLEAUT32!__imp_VariantClear` at `0x18003914a`
- `OLEAUT32!__imp_VariantCopy` at `0x180038ede`
- `OLEAUT32!__imp_VariantCopy` at `0x180038ede`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180039061`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180039061`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18003900b`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18003900b`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180039124`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180039124`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180039116`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180039116`
- `msIso!__imp_?IsoChangeArtifactOwner@@YAJKK@Z` at `0x180039025`
- `msIso!__imp_?IsoChangeArtifactOwner@@YAJKK@Z` at `0x180039025`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x180038f42`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x180038f42`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1800390a3`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1800390a3`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18003913a`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18003913a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180038f8f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180038f8f`

## pseudocode

```c

```
