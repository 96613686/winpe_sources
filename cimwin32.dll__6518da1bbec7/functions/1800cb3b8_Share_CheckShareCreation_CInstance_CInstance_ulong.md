# Share::CheckShareCreation(CInstance *,CInstance *,ulong &)

- ea: `0x1800cb3b8`
- end: `0x1800cbad6`
- name: `?CheckShareCreation@Share@@AEAAJPEAVCInstance@@0AEAK@Z`
- size: `1822`
- prototype: `__int64 __fastcall(Share *__hidden this, struct CInstance *, struct CInstance *, unsigned int *)`
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
- `0x1800cb3b8`
- `0x1800cc750`
- `0x1800eeb7c`
- `0x1800f3114`
- `0x1800fc902`

## import_xrefs

- `msvcrt!free` at `0x1800cb974`
- `msvcrt!free` at `0x1800cb974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cb964`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cb964`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cb849`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cb860`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cb849`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cb860`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb3f4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb469`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb4d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb54f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb79d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb3f4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb469`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb4d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb54f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cb79d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb444`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb4b3`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb539`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb5ac`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb7b9`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb444`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb4b3`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb539`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb5ac`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cb7b9`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cb7ce`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cb7ce`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cb70c`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cb70c`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cb606`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cb680`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cb606`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cb680`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cb756`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cb756`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cb457`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cb4c5`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cb457`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cb4c5`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb40d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb482`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb4f1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb568`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb5cf`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb63f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb6a5`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb776`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb40d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb482`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb4f1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb568`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb5cf`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb63f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb6a5`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cb776`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cb736`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cb736`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb7e2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb7ed`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb818`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb823`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9be`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9ca`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9d5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9e1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba1d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba30`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba43`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba59`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba7a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba86`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba9b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbab0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb7e2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb7ed`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb818`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb823`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9be`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9ca`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9d5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cb9e1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba1d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba30`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba43`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba59`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba7a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba86`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cba9b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cbab0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800cb6e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800cb6e9`

## string_xrefs

- `0x1800cb69b`: `Access`
- `0x1800cb72c`: `Access`
- `0x1800cb7c3`: `Win32_SecurityDescriptor`

## pseudocode

```c

```
