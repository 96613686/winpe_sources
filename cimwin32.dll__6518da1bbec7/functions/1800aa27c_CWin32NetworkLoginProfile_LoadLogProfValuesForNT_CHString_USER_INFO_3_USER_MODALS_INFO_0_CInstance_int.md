# CWin32NetworkLoginProfile::LoadLogProfValuesForNT(CHString &,_USER_INFO_3 *,_USER_MODALS_INFO_0 *,CInstance *,int)

- ea: `0x1800aa27c`
- end: `0x1800aa84f`
- name: `?LoadLogProfValuesForNT@CWin32NetworkLoginProfile@@AEAAXAEAVCHString@@PEAU_USER_INFO_3@@PEAU_USER_MODALS_INFO_0@@PEAVCInstance@@H@Z`
- size: `1491`
- prototype: `void __fastcall(CWin32NetworkLoginProfile *__hidden this, struct CHString *, struct _USER_INFO_3 *, struct _USER_MODALS_INFO_0 *, struct CInstance *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003301c`
- `0x18007ac14`

## callees

- `0x180068384`
- `0x1800aa12c`
- `0x1800aa27c`
- `0x1800aa858`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x1800aa545`
- `msvcrt!_i64tow_s` at `0x1800aa545`
- `msvcrt!time` at `0x1800aa703`
- `msvcrt!time` at `0x1800aa703`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa2e2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa2ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa7aa`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa2e2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa2ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800aa7aa`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800aa322`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800aa322`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa58a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5a1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5b8`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5cf`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa6c3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa6d7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa76d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa781`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa7ee`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa805`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa58a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5a1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5b8`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa5cf`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa6c3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa6d7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa76d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa781`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa7ee`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800aa805`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa2c5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa358`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa61b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa672`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa7cc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa2c5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa358`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa61b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa672`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa7cc`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800aa303`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800aa336`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800aa303`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800aa336`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa5ea`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa641`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa69c`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa71c`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa5ea`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa641`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa69c`
- `framedynos!??0WBEMTime@@QEAA@AEB_J@Z` at `0x1800aa71c`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa5fd`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa654`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa6af`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa72f`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa5fd`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa654`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa6af`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x1800aa72f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800aa553`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800aa553`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa2d8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa381`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3a3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3c5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3e7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa409`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa42b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa450`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa475`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa497`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa4bc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa51f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa79e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa2d8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa381`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3a3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3c5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa3e7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa409`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa42b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa450`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa475`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa497`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa4bc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa51f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800aa79e`
- `framedynos!?SpanExcluding@CHString@@QEBA?AV1@PEBG@Z` at `0x1800aa317`
- `framedynos!?SpanExcluding@CHString@@QEBA?AV1@PEBG@Z` at `0x1800aa317`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa568`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800aa568`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800aa344`
- `framedynos!??YCHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800aa344`
- `framedynos!?SetTimeSpan@CInstance@@QEAA_NPEBGAEBVWBEMTimeSpan@@@Z` at `0x1800aa759`
- `framedynos!?SetTimeSpan@CInstance@@QEAA_NPEBGAEBVWBEMTimeSpan@@@Z` at `0x1800aa759`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa573`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa626`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa67d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa7d7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa810`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa81b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa826`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa573`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa626`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa67d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa7d7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa810`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa81b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800aa826`

## string_xrefs

- `0x1800aa399`: `Comment`
- `0x1800aa377`: `HomeDirectory`
- `0x1800aa3bb`: `ScriptPath`
- `0x1800aa3ff`: `UserComment`
- `0x1800aa4b2`: `HomeDirectoryDrive`
- `0x1800aa763`: `Privileges`

## pseudocode

```c

```
