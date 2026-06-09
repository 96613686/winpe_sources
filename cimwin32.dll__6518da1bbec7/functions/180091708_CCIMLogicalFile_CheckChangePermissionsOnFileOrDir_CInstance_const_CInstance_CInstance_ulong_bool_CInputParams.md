# CCIMLogicalFile::CheckChangePermissionsOnFileOrDir(CInstance const &,CInstance *,CInstance *,ulong &,bool,CInputParams &)

- ea: `0x180091708`
- end: `0x180091bed`
- name: `?CheckChangePermissionsOnFileOrDir@CCIMLogicalFile@@AEAAJAEBVCInstance@@PEAV2@1AEAK_NAEAVCInputParams@@@Z`
- size: `1253`
- prototype: `__int64 __fastcall(CCIMLogicalFile *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, unsigned int *, bool, struct CInputParams *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800926dc`

## callees

- `0x180015c80`
- `0x180017680`
- `0x1800230e4`
- `0x18003d7b0`
- `0x180085148`
- `0x180091708`
- `0x180092c10`
- `0x1800eeb7c`

## import_xrefs

- `msvcrt!free` at `0x180091b59`
- `msvcrt!free` at `0x180091b7b`
- `msvcrt!free` at `0x180091b59`
- `msvcrt!free` at `0x180091b7b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180091735`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180091a1b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180091735`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180091a1b`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800917ce`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180091a45`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800917ce`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180091a45`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180091a5b`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180091a5b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18009183e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800919e1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180091a34`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18009183e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800919e1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180091a34`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18009190d`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180091ae7`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18009190d`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180091ae7`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800918fc`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800918fc`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800919c8`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800919c8`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18009182f`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18009182f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180091777`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800917fa`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800918c5`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180091932`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800919fa`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180091777`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800917fa`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800918c5`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180091932`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800919fa`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180091977`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180091977`
- `framedynos!?MakeLower@CHString@@QEAAXXZ` at `0x1800917dd`
- `framedynos!?MakeLower@CHString@@QEAAXXZ` at `0x1800917dd`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x180091874`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x180091874`
- `framedynos!?GetWCHAR@CInstance@@QEBA_NPEBGPEAPEAG@Z` at `0x180091ad5`
- `framedynos!?GetWCHAR@CInstance@@QEBA_NPEBGPEAPEAG@Z` at `0x180091ad5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800917b1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800918a1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091a75`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091a90`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091bc5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800917b1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800918a1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091a75`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091a90`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091bc5`

## string_xrefs

- `0x180091a4f`: `Win32_SecurityDescriptor`
- `0x180091928`: `SecurityDescriptor`
- `0x18009196d`: `SecurityDescriptor`

## pseudocode

```c

```
