# CTabWindow::AsyncExec(_GUID const *,ulong,ulong,tagVARIANT *)

- ea: `0x180034a30`
- end: `0x180034ce1`
- name: `?AsyncExec@CTabWindow@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@@Z`
- size: `689`
- prototype: `int(CTabWindow *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *)`
- caller_count: `17`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009dae0`
- `0x18023c484`
- `0x180250050`
- `0x180255250`
- `0x1802567bc`
- `0x1802570a8`
- `0x180257dd0`
- `0x1802594d4`
- `0x180259dc0`
- `0x18025a0c0`
- `0x18025cb64`
- `0x180261280`
- `0x180284024`
- `0x1802846a4`
- `0x18028907c`
- `0x180289114`
- `0x18028bf10`

## callees

- `0x180034a30`
- `0x180034f28`
- `0x1800350e4`
- `0x18008dc44`
- `0x180434b24`

## import_xrefs

- `USER32!GetKeyState` at `0x180034b96`
- `USER32!GetKeyState` at `0x180034b96`
- `USER32!PostMessageW` at `0x180034bea`
- `USER32!PostMessageW` at `0x180034bea`
- `USER32!AllowSetForegroundWindow` at `0x180034ba4`
- `USER32!AllowSetForegroundWindow` at `0x180034ba4`
- `OLEAUT32!__imp_VariantClear` at `0x180034c94`
- `OLEAUT32!__imp_VariantClear` at `0x180034cbe`
- `OLEAUT32!__imp_VariantClear` at `0x180034c94`
- `OLEAUT32!__imp_VariantClear` at `0x180034cbe`
- `OLEAUT32!__imp_VariantCopy` at `0x180034aae`
- `OLEAUT32!__imp_VariantCopy` at `0x180034aae`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180034c01`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180034c01`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180034bbd`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180034bbd`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180034ca4`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180034ca4`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180034c9c`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180034c9c`
- `msIso!__imp_?IsoChangeArtifactOwner@@YAJKK@Z` at `0x180034bd1`
- `msIso!__imp_?IsoChangeArtifactOwner@@YAJKK@Z` at `0x180034bd1`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x180034b0c`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x180034b0c`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x180034c3d`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x180034c3d`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x180034cb4`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x180034cb4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180034b53`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180034b53`

## pseudocode

```c

```
