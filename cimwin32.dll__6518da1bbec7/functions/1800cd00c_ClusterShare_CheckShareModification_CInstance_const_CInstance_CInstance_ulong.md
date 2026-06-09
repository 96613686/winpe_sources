# ClusterShare::CheckShareModification(CInstance const &,CInstance *,CInstance *,ulong &)

- ea: `0x1800cd00c`
- end: `0x1800cd5cc`
- name: `?CheckShareModification@ClusterShare@@AEAAJAEBVCInstance@@PEAV2@1AEAK@Z`
- size: `1472`
- prototype: `__int64 __fastcall(ClusterShare *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, unsigned int *)`
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
- `0x1800cd00c`
- `0x1800eeb7c`
- `0x1800f318c`
- `0x1800fc902`

## import_xrefs

- `msvcrt!free` at `0x1800cd489`
- `msvcrt!free` at `0x1800cd489`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cd37f`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cd397`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cd37f`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800cd397`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd049`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd054`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd060`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd11a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd2cf`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd049`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd054`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd060`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd11a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800cd2cf`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd0ab`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd17a`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd2eb`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd0ab`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd17a`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800cd2eb`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cd300`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800cd300`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cd242`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800cd242`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cd1e2`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800cd1e2`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cd288`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800cd288`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cd0be`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800cd0be`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd079`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd133`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd1a1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd207`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd2a8`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd079`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd133`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd1a1`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd207`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800cd2a8`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cd26c`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800cd26c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd0f2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd0fd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd109`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd318`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd323`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd34b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd356`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4c7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4d3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4de`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4ea`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd543`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd54f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd55a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd566`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd58e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd599`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd5a5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd0f2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd0fd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd109`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd318`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd323`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd34b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd356`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4c7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4d3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4de`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd4ea`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd543`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd54f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd55a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd566`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd58e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd599`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800cd5a5`

## string_xrefs

- `0x1800cd1fd`: `Access`
- `0x1800cd262`: `Access`
- `0x1800cd2f5`: `Win32_SecurityDescriptor`

## pseudocode

```c

```
