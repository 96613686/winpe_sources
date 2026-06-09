# Share::CheckShareModification(CInstance const &,CInstance *,CInstance *,ulong &)

- ea: `0x1800cbadc`
- end: `0x1800cbfb8`
- name: `?CheckShareModification@Share@@AEAAJAEBVCInstance@@PEAV2@1AEAK@Z`
- size: `1244`
- prototype: `__int64 __fastcall(Share *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cc590`

## callees

- `0x1800127e0`
- `0x180015c80`
- `0x180017680`
- `0x1800254f8`
- `0x18003d7b0`
- `0x18004cff4`
- `0x18004e8e8`
- `0x1800cbadc`
- `0x1800cc750`
- `0x1800eeb7c`
- `0x1800f318c`
- `0x1800fc902`

## import_xrefs

- `msvcrt!free` at `0x1800cbec1`
- `msvcrt!free` at `0x1800cbec1`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cbde4`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cbde4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbb18`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbb86`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbd36`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbb18`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbb86`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cbd36`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbb62`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbbe6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbd51`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbb62`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbbe6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cbd51`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cbd66`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cbd66`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cbcad`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cbcad`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cbc4e`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cbc4e`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cbcf0`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cbcf0`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cbb74`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cbb74`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbb31`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbb9f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbc0d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbc72`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbd0f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbb31`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbb9f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbc0d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbc72`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cbd0f`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cbcd4`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cbcd4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbd7e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbd89`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbdb0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbdbb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbef4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbeff`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf56`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf61`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf79`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf91`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbd7e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbd89`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbdb0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbdbb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbef4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbeff`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf56`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf61`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf79`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbf91`

## string_xrefs

- `0x1800cbc68`: `Access`
- `0x1800cbcca`: `Access`
- `0x1800cbd5b`: `Win32_SecurityDescriptor`

## pseudocode

```c

```
