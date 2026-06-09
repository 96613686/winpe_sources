# ClusterShare::CheckShareCreation(CInstance *,CInstance *,ulong &)

- ea: `0x1800cc808`
- end: `0x1800cd004`
- name: `?CheckShareCreation@ClusterShare@@AEAAJPEAVCInstance@@0AEAK@Z`
- size: `2044`
- prototype: `__int64 __fastcall(ClusterShare *__hidden this, struct CInstance *, struct CInstance *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cd9a0`

## callees

- `0x1800127e0`
- `0x180015c80`
- `0x180017680`
- `0x1800254f8`
- `0x18003d7b0`
- `0x18004cff4`
- `0x18004e8e8`
- `0x1800867bc`
- `0x1800cc750`
- `0x1800cc808`
- `0x1800eeb7c`
- `0x1800f3114`
- `0x1800fc902`

## import_xrefs

- `msvcrt!free` at `0x1800cce5a`
- `msvcrt!free` at `0x1800cce5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccba6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cce4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cce4a`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd01`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd19`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd30`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd01`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd19`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ccd30`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc844`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc850`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc85c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc919`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc988`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cca00`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ccc52`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc844`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc850`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc85c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc919`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cc988`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cca00`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ccc52`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc8ac`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc963`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc9ea`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cca5d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ccc6f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc8ac`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc963`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cc9ea`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cca5d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ccc6f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800ccc84`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800ccc84`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ccbbf`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ccbbf`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ccab7`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ccb33`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ccab7`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ccb33`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ccc0a`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ccc0a`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cc8bf`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cc975`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cc8bf`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cc975`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc875`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc932`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc9a1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cca19`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cca80`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccaf1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccb58`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccc2b`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc875`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc932`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cc9a1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cca19`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cca80`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccaf1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccb58`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ccc2b`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800ccbe9`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800ccbe9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc8f0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc8fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc908`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccc98`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccca4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccccf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cccdb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cceae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cceba`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccec5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cced1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccedd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccee9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf25`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf38`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf4b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf61`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf82`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf8e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf9a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfa6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfc6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfd2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfde`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc8f0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc8fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cc908`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccc98`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccca4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccccf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cccdb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cceae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cceba`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccec5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cced1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccedd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccee9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf25`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf38`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf4b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf61`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf82`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf8e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccf9a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfa6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfc6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfd2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ccfde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ccb9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ccb9c`

## string_xrefs

- `0x1800ccb4e`: `Access`
- `0x1800ccbdf`: `Access`
- `0x1800ccc79`: `Win32_SecurityDescriptor`

## pseudocode

```c

```
