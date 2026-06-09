# CWin32Desktop::LoadDesktopValuesNT(ushort const *,ushort const *,CInstance *)

- ea: `0x18002fda4`
- end: `0x1800309fd`
- name: `?LoadDesktopValuesNT@CWin32Desktop@@AEAAJPEBG0PEAVCInstance@@@Z`
- size: `3161`
- prototype: `int(CWin32Desktop *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct CInstance *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18003190c`
- `0x18009ce80`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x18002ea18`
- `0x18002f1cc`
- `0x18002f9fc`
- `0x18002fda4`
- `0x180030a04`
- `0x180030c98`
- `0x1800311e8`
- `0x18003a82c`
- `0x18006da44`
- `0x18008bb9c`
- `0x18008c1b0`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wtoi` at `0x18003014c`
- `msvcrt!_wtoi` at `0x1800301da`
- `msvcrt!_wtoi` at `0x180030285`
- `msvcrt!_wtoi` at `0x18003029d`
- `msvcrt!_wtoi` at `0x1800302c3`
- `msvcrt!_wtoi` at `0x180030484`
- `msvcrt!_wtoi` at `0x1800306d4`
- `msvcrt!_wtoi` at `0x1800306ec`
- `msvcrt!_wtoi` at `0x180030712`
- `msvcrt!_wtoi` at `0x18003014c`
- `msvcrt!_wtoi` at `0x1800301da`
- `msvcrt!_wtoi` at `0x180030285`
- `msvcrt!_wtoi` at `0x18003029d`
- `msvcrt!_wtoi` at `0x1800302c3`
- `msvcrt!_wtoi` at `0x180030484`
- `msvcrt!_wtoi` at `0x1800306d4`
- `msvcrt!_wtoi` at `0x1800306ec`
- `msvcrt!_wtoi` at `0x180030712`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002fe10`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002fe10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003098e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003098e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800308a4`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800308a4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800300d1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800301f8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800306a1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800300d1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800301f8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800306a1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030143`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800301d1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003022d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003027c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030294`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800302ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003047b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800306cb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800306e3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030709`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003094a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030143`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800301d1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003022d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003027c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030294`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800302ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003047b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800306cb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800306e3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180030709`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003094a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030167`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800301ed`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800302d9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030497`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003054e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030727`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800308c6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003093e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030167`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800301ed`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800302d9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030497`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003054e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180030727`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800308c6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003093e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800300c6`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180030391`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800303d6`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800304ca`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800300c6`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180030391`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800303d6`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800304ca`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003011a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800301a8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003031f`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180030411`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180030452`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003050b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003011a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800301a8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003031f`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180030411`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180030452`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18003050b`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18002feb5`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800303f5`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18002feb5`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800303f5`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180030213`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180030213`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fdf6`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180030221`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fdf6`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180030221`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003032e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003099d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003032e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003099d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002ff4c`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800300a2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003024b`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003068e`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002ff4c`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800300a2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003024b`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003068e`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z` at `0x18003052a`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z` at `0x18003052a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180030914`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180030914`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800308f9`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180030924`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800308f9`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180030924`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180030876`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180030876`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fdd8`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fde7`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fdd8`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fde7`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18002ff68`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18002ff68`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18003055c`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x1800308dd`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18003055c`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x1800308dd`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002fe7c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002ff17`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002ff2a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18003034c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18003037c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800303a3`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800303ea`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002fe7c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002ff17`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002ff2a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18003034c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18003037c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800303a3`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800303ea`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800300ec`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030134`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030181`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800301c2`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003026d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800302f3`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030366`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800303bd`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003042b`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003046c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800304b1`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800304e4`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800306bc`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800300ec`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030134`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030181`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800301c2`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003026d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800302f3`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030366`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800303bd`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003042b`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18003046c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800304b1`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800304e4`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800306bc`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x180030749`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18003078b`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x180030749`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18003078b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003033a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180030568`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800308e9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800309a9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800309b5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003033a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180030568`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800308e9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800309a9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800309b5`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003088f`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003088f`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18003087e`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18003087e`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1800308b3`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1800308b3`

## string_xrefs

- `0x180030125`: `CursorBlinkRate`
- `0x18003015d`: `CursorBlinkRate`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWin32Desktop::LoadDesktopValuesNT(
        CWin32Desktop *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CInstance *a4)
{
  int NT; // r14d
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  __int64 v10; // r15
  __int64 v11; // r8
  const wchar_t *v12; // r9
  unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  wchar_t v15; // r10
  int v16; // eax
  const wchar_t *v17; // rax
  unsigned int v18; // r8d
  int v19; // eax
  const wchar_t *v20; // rax
  unsigned int v21; // eax
  const unsigned __int16 *v22; // rax
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  int v25; // eax
  int v26; // edx
  const wchar_t *v27; // rax
  bool v28; // r8
  bool v29; // r8
  int v30; // eax
  const wchar_t *v31; // rax
  unsigned int v32; // eax
  int v33; // eax
  unsigned int v34; // r8d
  __int64 v35; // rax
  unsigned __int16 *v36; // rcx
  const wchar_t *v37; // r8
  unsigned __int16 *v38; // rcx
  __int64 v39; // rdx
  wchar_t v40; // r9
  const wchar_t *v41; // rax
  const wchar_t *v42; // rax
  int v43; // eax
  unsigned int v44; // edx
  const wchar_t *v45; // rax
  _OWORD *v46; // rax
  _OWORD *v47; // r15
  __int64 v48; // rax
  _WORD *v49; // rcx
  int v50; // ecx
  HDC DC; // rdi
  int DeviceCaps; // eax
  unsigned int v53; // ebx
  const WCHAR *v54; // rax
  unsigned int v55; // ebx
  const WCHAR *v57; // rax
  char v58; // [rsp+20h] [rbp-978h]
  unsigned __int64 v59; // [rsp+28h] [rbp-970h] BYREF
  int v60; // [rsp+30h] [rbp-968h]
  _BYTE v61[8]; // [rsp+38h] [rbp-960h] BYREF
  __int64 v62; // [rsp+40h] [rbp-958h] BYREF
  unsigned int v63; // [rsp+48h] [rbp-950h] BYREF
  _BYTE v64[8]; // [rsp+50h] [rbp-948h] BYREF
  _BYTE v65[8]; // [rsp+58h] [rbp-940h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-938h] BYREF
  unsigned __int16 *v67; // [rsp+68h] [rbp-930h]
  __int64 v68; // [rsp+70h] [rbp-928h]
  unsigned __int16 *v69; // [rsp+78h] [rbp-920h]
  __int64 v70; // [rsp+80h] [rbp-918h]
  __int64 v71; // [rsp+88h] [rbp-910h]
  unsigned __int16 *v72; // [rsp+90h] [rbp-908h]
  __int64 v73; // [rsp+98h] [rbp-900h]
  const wchar_t *v74; // [rsp+A0h] [rbp-8F8h]
  __int64 v75; // [rsp+A8h] [rbp-8F0h]
  __int64 v76; // [rsp+B0h] [rbp-8E8h]
  unsigned __int16 *v77; // [rsp+B8h] [rbp-8E0h]
  __int64 v78; // [rsp+C0h] [rbp-8D8h]
  const wchar_t *v79; // [rsp+C8h] [rbp-8D0h]
  __int64 v80; // [rsp+D0h] [rbp-8C8h]
  __int64 v81; // [rsp+D8h] [rbp-8C0h]
  char *v82; // [rsp+E0h] [rbp-8B8h]
  __int64 v83; // [rsp+E8h] [rbp-8B0h]
  void *v84; // [rsp+F0h] [rbp-8A8h]
  int nNumber[4]; // [rsp+100h] [rbp-898h] BYREF
  _OWORD v86[3]; // [rsp+110h] [rbp-888h] BYREF
  _OWORD v87[2]; // [rsp+140h] [rbp-858h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+160h] [rbp-838h] BYREF
  __int64 v89; // [rsp+278h] [rbp-720h]
  HKEY hKey; // [rsp+280h] [rbp-718h]
  int v91; // [rsp+288h] [rbp-710h]
  _BYTE v92[608]; // [rsp+290h] [rbp-708h] BYREF
  _BYTE v93[608]; // [rsp+4F0h] [rbp-4A8h] BYREF
  unsigned __int16 v94[264]; // [rsp+750h] [rbp-248h] BYREF

  CHString::CHString((CHString *)v61, a2);
  CHString::CHString((CHString *)v65, a3);
  CRegistry::CRegistry((CRegistry *)v92);
  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  v89 = 0;
  v91 = 0;
  hKey = 0;
  v58 = 0;
  try
  {
    if ( a2 )
    {
      NT = CUserHive::LoadNT((CUserHive *)&VersionInformation, a2, v94, 0x104u);
      v60 = NT;
      if ( !NT )
      {
        v58 = 1;
        CHString::operator=(v65, v94);
      }
    }
    else if ( a3 )
    {
      NT = CUserHive::LoadProfile((CUserHive *)&VersionInformation, a3, (struct CHString *)v61);
      v60 = NT;
      if ( !NT && (int)CHString::GetLength((CHString *)v61) > 0 )
      {
        v58 = 1;
        if ( (int)StringCchCopyW(v94, 0x104u, a3) < 0 )
        {
          NT = -2147467259;
          v60 = -2147467259;
        }
      }
    }
    else
    {
      StringCbCopyW(v94, 0x208u, L".DEFAULT");
      CHString::operator=(v61, v94);
      CHString::operator=(v65, v94);
      NT = CRegistry::Open((CRegistry *)v92, HKEY_USERS, L".DEFAULT", 0x20019u);
      v60 = NT;
    }
    if ( CHString::IsEmpty((CHString *)v61) )
      NT = -2147467259;
    v60 = NT;
    if ( !NT )
    {
      v62 = 0;
      v8 = 260;
      v73 = 260;
      v9 = v94;
      v72 = v94;
      while ( 1 )
      {
        if ( !v8 )
        {
          v62 = 0;
          v10 = 2147483646;
          goto LABEL_26;
        }
        if ( !*v9 )
          break;
        v72 = ++v9;
        v73 = --v8;
      }
      v62 = 260 - v8;
      v10 = 2147483646;
      v11 = 2147483646;
      v76 = 2147483646;
      v12 = L"\\Control Panel\\Desktop";
      v74 = L"\\Control Panel\\Desktop";
      v75 = v8;
      v13 = &v94[260 - v8];
      v67 = v13;
      v14 = 0;
      v68 = 0;
      while ( v8 )
      {
        if ( !v11 )
          goto LABEL_24;
        v15 = *v12;
        if ( !*v12 )
          goto LABEL_24;
        v74 = ++v12;
        *v13++ = v15;
        v67 = v13;
        v75 = --v8;
        v76 = --v11;
        v68 = ++v14;
      }
      v67 = --v13;
      v68 = v14 - 1;
LABEL_24:
      *v13 = 0;
LABEL_26:
      NT = CRegistry::Open((CRegistry *)v92, HKEY_USERS, v94, 0x20019u);
      v60 = NT;
      if ( !NT )
      {
        CInstance::SetCHString(a4, L"Name", (const struct CHString *)v61);
        CHString::CHString((CHString *)&v59);
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"CoolSwitch", (struct CHString *)&v59) )
        {
          v16 = operator==(&v59, L"1");
          CInstance::Setbool(a4, L"CoolSwitch", v16 != 0);
        }
        if ( CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"CursorBlinkRate", (struct CHString *)&v59) )
        {
          v18 = 500;
        }
        else
        {
          v17 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
          v18 = _wtoi(v17);
        }
        CInstance::SetDWORD(a4, L"CursorBlinkRate", v18);
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"DragFullWindows", (struct CHString *)&v59) )
        {
          v19 = operator==(&v59, L"1");
          CInstance::Setbool(a4, L"DragFullWindows", v19 != 0);
        }
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"GridGranularity", (struct CHString *)&v59) )
        {
          v20 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
          v21 = _wtoi(v20);
          CInstance::SetDWORD(a4, L"GridGranularity", v21);
        }
        CHString::CHString((CHString *)&v62);
        CHString::Format((CHString *)&v62, L"%s\\WindowMetrics", v94);
        CRegistry::CRegistry((CRegistry *)v93);
        v22 = (const unsigned __int16 *)CHString::operator unsigned short const *(&v62);
        if ( !CRegistry::Open((CRegistry *)v93, HKEY_USERS, v22, 0x20019u) )
        {
          if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v93, L"IconSpacing", (struct CHString *)&v59) )
          {
            v23 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
            if ( _wtoi(v23) >= 0 )
            {
              v27 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
              v26 = _wtoi(v27);
            }
            else
            {
              v24 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
              v25 = _wtoi(v24);
              v26 = ((unsigned int)(((unsigned __int64)(2004318071LL * v25) >> 32) - v25) >> 31)
                  + ((int)(((unsigned __int64)(2004318071LL * v25) >> 32) - v25) >> 3);
            }
            CInstance::SetDWORD(a4, L"IconSpacing", v26 - 32);
          }
          if ( CRegistry::GetCurrentKeyValue((CRegistry *)v93, L"IconTitleWrap", (struct CHString *)&v59) )
            v28 = 1;
          else
            v28 = (unsigned int)operator==(&v59, L"1") != 0;
          CInstance::Setbool(a4, L"IconTitleWrap", v28);
        }
        CRegistry::~CRegistry((CRegistry *)v93);
        CHString::~CHString((CHString *)&v62);
        CHString::operator=(&v59, &Data);
        if ( CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"Pattern", (struct CHString *)&v59) )
          CHString::operator=(&v59, L"(None)");
        CInstance::SetCHString(a4, L"Pattern", (const struct CHString *)&v59);
        CHString::operator=(&v59, &Data);
        if ( CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"SCRNSAVE.EXE", (struct CHString *)&v59) )
          CHString::operator=(&v59, &Data);
        else
          CInstance::SetCHString(a4, L"ScreenSaverExecutable", (const struct CHString *)&v59);
        v29 = CHString::GetLength((CHString *)&v59) > 0;
        CInstance::Setbool(a4, L"ScreenSaverActive", v29);
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"ScreenSaverIsSecure", (struct CHString *)&v59) )
        {
          v30 = operator==(&v59, L"1");
          CInstance::Setbool(a4, L"ScreenSaverSecure", v30 != 0);
        }
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"ScreenSaveTimeOut", (struct CHString *)&v59) )
        {
          v31 = (const wchar_t *)CHString::operator unsigned short const *(&v59);
          v32 = _wtoi(v31);
          CInstance::SetDWORD(a4, L"ScreenSaverTimeout", v32);
        }
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"Wallpaper", (struct CHString *)&v59) )
          CInstance::SetCHString(a4, L"Wallpaper", (const struct CHString *)&v59);
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"TileWallpaper", (struct CHString *)&v59) )
        {
          v33 = operator==(&v59, L"1");
          CInstance::Setbool(a4, L"WallpaperTiled", v33 != 0);
        }
        v63 = 0;
        v34 = !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"WallpaperStyle", &v63) && v63;
        CInstance::SetDWORD(a4, L"WallpaperStretched", v34);
        CRegistry::Close((CRegistry *)v92);
        CHString::~CHString((CHString *)&v59);
      }
      v71 = 0;
      v35 = 260;
      v78 = 260;
      v36 = v94;
      v77 = v94;
      while ( 1 )
      {
        if ( !v35 )
        {
          v71 = 0;
          goto LABEL_76;
        }
        if ( !*v36 )
          break;
        v77 = ++v36;
        v78 = --v35;
      }
      v71 = 260 - v35;
      v81 = 2147483646;
      v37 = L"\\WindowMetrics";
      v79 = L"\\WindowMetrics";
      v80 = v35;
      v38 = &v94[260 - v35];
      v69 = v38;
      v39 = 0;
      v70 = 0;
      while ( v35 )
      {
        if ( !v10 )
          goto LABEL_74;
        v40 = *v37;
        if ( !*v37 )
          goto LABEL_74;
        v79 = ++v37;
        *v38++ = v40;
        v69 = v38;
        v80 = --v35;
        v81 = --v10;
        v70 = ++v39;
      }
      v69 = --v38;
      v70 = v39 - 1;
LABEL_74:
      *v38 = 0;
LABEL_76:
      if ( !CRegistry::Open((CRegistry *)v92, HKEY_USERS, v94, 0x20019u) )
      {
        CHString::CHString((CHString *)v64);
        if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v92, L"BorderWidth", (struct CHString *)v64) )
        {
          v41 = (const wchar_t *)CHString::operator unsigned short const *(v64);
          if ( _wtoi(v41) >= 0 )
          {
            v45 = (const wchar_t *)CHString::operator unsigned short const *(v64);
            v44 = _wtoi(v45);
          }
          else
          {
            v42 = (const wchar_t *)CHString::operator unsigned short const *(v64);
            v43 = _wtoi(v42);
            v44 = ((unsigned int)(((unsigned __int64)(2004318071LL * v43) >> 32) - v43) >> 31)
                + ((int)(((unsigned __int64)(2004318071LL * v43) >> 32) - v43) >> 3);
          }
          CInstance::SetDWORD(a4, L"BorderWidth", v44);
        }
        LODWORD(v59) = 0;
        if ( !CRegistry::GetCurrentBinaryKeyValue((CRegistry *)v92, L"IconFont", 0, (unsigned int *)&v59) )
        {
          v46 = operator new((unsigned int)v59);
          v47 = v46;
          v84 = v46;
          if ( !v46 )
          {
            pExceptionObject = 0;
            throw (CHeap_Exception *)&pExceptionObject;
          }
          try
          {
            if ( !CRegistry::GetCurrentBinaryKeyValue(
                    (CRegistry *)v92,
                    L"IconFont",
                    (unsigned __int8 *)v46,
                    (unsigned int *)&v59)
              && (_DWORD)v59 == 92
              && (unsigned __int8)IsGetDeviceCapsPresent() )
            {
              memset_0(nNumber, 0, 0x5Cu);
              *(_OWORD *)nNumber = *v47;
              v86[0] = v47[1];
              v86[1] = v47[2];
              v86[2] = v47[3];
              v87[0] = v47[4];
              *(_OWORD *)((char *)v87 + 12) = *(_OWORD *)((char *)v47 + 76);
              v48 = 32;
              v83 = 32;
              v49 = (_WORD *)v86 + 6;
              v82 = (char *)v86 + 12;
              while ( v48 && *v49 )
              {
                v82 = (char *)++v49;
                v83 = --v48;
              }
              v50 = 0;
              if ( !v48 )
                v50 = -2147024809;
              if ( v50 >= 0 )
                CInstance::SetWCHARSplat(a4, L"IconTitleFaceName", (const unsigned __int16 *)v86 + 6);
              DC = GetDC(0);
              DeviceCaps = GetDeviceCaps(DC, 90);
              v53 = -MulDiv(nNumber[0], 72, DeviceCaps);
              ReleaseDC(0, DC);
              CInstance::SetDWORD(a4, L"IconTitleSize", v53);
            }
          }
          catch ( ... )
          {
            operator delete(v84);
            throw;
          }
          operator delete(v47);
        }
        CRegistry::Close((CRegistry *)v92);
        CHString::~CHString((CHString *)v64);
      }
      if ( CInstance::IsNull(a4, L"IconTitleFaceName") )
        CInstance::SetCharSplat(a4, L"IconTitleFaceName", L"MS Shell Dlg");
      if ( CInstance::IsNull(a4, L"IconTitleSize") )
        CInstance::SetDWORD(a4, L"IconTitleSize", 8u);
    }
  }
  catch ( ... )
  {
    if ( v58 )
    {
      v57 = (const WCHAR *)CHString::operator unsigned short const *(v65);
      CUserHive::Unload((CUserHive *)&VersionInformation, v57);
    }
    throw;
  }
  v54 = (const WCHAR *)CHString::operator unsigned short const *(v65);
  CUserHive::Unload((CUserHive *)&VersionInformation, v54);
  v55 = WinErrorToWBEMhResult(NT);
  if ( v89 )
    CUserHive::RestorePrivilege((CUserHive *)&VersionInformation);
  if ( hKey )
    RegCloseKey(hKey);
  CRegistry::~CRegistry((CRegistry *)v92);
  CHString::~CHString((CHString *)v65);
  CHString::~CHString((CHString *)v61);
  return v55;
}

```

## disassembly

```asm
0x18002fda4  mov     [rsp+arg_0], rbx
0x18002fda9  push    rsi
0x18002fdaa  push    rdi
0x18002fdab  push    r12
0x18002fdad  push    r14
0x18002fdaf  push    r15
0x18002fdb1  sub     rsp, 970h
0x18002fdb8  mov     rax, cs:__security_cookie
0x18002fdbf  xor     rax, rsp
0x18002fdc2  mov     [rsp+998h+var_38], rax
0x18002fdca  mov     rsi, r9
0x18002fdcd  mov     rbx, r8
0x18002fdd0  mov     r14, rdx
0x18002fdd3  lea     rcx, [rsp+998h+var_960]
0x18002fdd8  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x18002fdde  nop
0x18002fddf  mov     rdx, rbx
0x18002fde2  lea     rcx, [rsp+998h+var_940]
0x18002fde7  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x18002fded  nop
0x18002fdee  lea     rcx, [rsp+998h+var_708]
0x18002fdf6  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18002fdfc  nop
0x18002fdfd  mov     [rsp+998h+VersionInformation.dwOSVersionInfoSize], 114h
0x18002fe08  lea     rcx, [rsp+998h+VersionInformation]; lpVersionInformation
0x18002fe10  call    cs:__imp_GetVersionExW
0x18002fe16  xor     r12d, r12d
0x18002fe19  mov     [rsp+998h+var_720], r12
0x18002fe21  mov     [rsp+998h+var_710], r12d
0x18002fe29  mov     [rsp+998h+hKey], r12
0x18002fe31  mov     [rsp+998h+var_978], r12b
0x18002fe36  test    r14, r14
0x18002fe39  jz      short loc_18002FE87
0x18002fe3b  mov     edi, 104h
0x18002fe40  mov     r9d, edi; unsigned __int64
0x18002fe43  lea     r8, [rsp+998h+var_248]; unsigned __int16 *
0x18002fe4b  mov     rdx, r14; lpAccountName
0x18002fe4e  lea     rcx, [rsp+998h+VersionInformation]; this
0x18002fe56  call    ?LoadNT@CUserHive@@AEAAKPEBGPEAG_K@Z; CUserHive::LoadNT(ushort const *,ushort *,unsigned __int64)
0x18002fe5b  mov     r14d, eax
0x18002fe5e  mov     [rsp+998h+var_968], eax
0x18002fe62  test    eax, eax
0x18002fe64  jnz     loc_18002FF5E
0x18002fe6a  mov     [rsp+998h+var_978], 1
0x18002fe6f  lea     rdx, [rsp+998h+var_248]
0x18002fe77  lea     rcx, [rsp+998h+var_940]
0x18002fe7c  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18002fe82  jmp     loc_18002FF5E
0x18002fe87  test    rbx, rbx
0x18002fe8a  jz      short loc_18002FEF1
0x18002fe8c  lea     r8, [rsp+998h+var_960]; struct CHString *
0x18002fe91  mov     rdx, rbx; lpSubKey
0x18002fe94  lea     rcx, [rsp+998h+VersionInformation]; this
0x18002fe9c  call    ?LoadProfile@CUserHive@@QEAAKPEBGAEAVCHString@@@Z; CUserHive::LoadProfile(ushort const *,CHString &)
0x18002fea1  mov     r14d, eax
0x18002fea4  mov     [rsp+998h+var_968], eax
0x18002fea8  test    eax, eax
0x18002feaa  jnz     loc_18002FF59
0x18002feb0  lea     rcx, [rsp+998h+var_960]
0x18002feb5  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x18002febb  test    eax, eax
0x18002febd  jle     loc_18002FF59
0x18002fec3  mov     [rsp+998h+var_978], 1
0x18002fec8  mov     r8, rbx; unsigned __int16 *
0x18002fecb  mov     edi, 104h
0x18002fed0  mov     edx, edi; unsigned __int64
0x18002fed2  lea     rcx, [rsp+998h+var_248]; unsigned __int16 *
0x18002feda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fedf  mov     ebx, 80004005h
0x18002fee4  test    eax, eax
0x18002fee6  jns     short loc_18002FF63
0x18002fee8  mov     r14d, ebx
0x18002feeb  mov     [rsp+998h+var_968], ebx
0x18002feef  jmp     short loc_18002FF63
0x18002fef1  lea     r8, aDefault; ".DEFAULT"
0x18002fef8  mov     edx, 208h; unsigned __int64
0x18002fefd  lea     rcx, [rsp+998h+var_248]; unsigned __int16 *
0x18002ff05  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ff0a  lea     rdx, [rsp+998h+var_248]
0x18002ff12  lea     rcx, [rsp+998h+var_960]
0x18002ff17  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18002ff1d  lea     rdx, [rsp+998h+var_248]
0x18002ff25  lea     rcx, [rsp+998h+var_940]
0x18002ff2a  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18002ff30  mov     r9d, 20019h
0x18002ff36  lea     r8, aDefault; ".DEFAULT"
0x18002ff3d  mov     rdx, 0FFFFFFFF80000003h
0x18002ff44  lea     rcx, [rsp+998h+var_708]
0x18002ff4c  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18002ff52  mov     r14d, eax
0x18002ff55  mov     [rsp+998h+var_968], eax
0x18002ff59  mov     edi, 104h
0x18002ff5e  mov     ebx, 80004005h
0x18002ff63  lea     rcx, [rsp+998h+var_960]
0x18002ff68  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18002ff6e  test    eax, eax
0x18002ff70  cmovnz  r14d, ebx
0x18002ff74  mov     [rsp+998h+var_968], r14d
0x18002ff79  test    r14d, r14d
0x18002ff7c  jnz     loc_180030945
0x18002ff82  mov     [rsp+998h+var_958], r12
0x18002ff87  mov     rcx, rdi
0x18002ff8a  mov     [rsp+998h+var_900], rcx
0x18002ff92  lea     rax, [rsp+998h+var_248]
0x18002ff9a  mov     [rsp+998h+var_908], rax
0x18002ffa2  test    rcx, rcx
0x18002ffa5  jz      loc_18003007A
0x18002ffab  cmp     [rax], r12w
0x18002ffaf  jz      short loc_18002FFCA
0x18002ffb1  add     rax, 2
0x18002ffb5  mov     [rsp+998h+var_908], rax
0x18002ffbd  dec     rcx
0x18002ffc0  mov     [rsp+998h+var_900], rcx
0x18002ffc8  jmp     short loc_18002FFA2
0x18002ffca  mov     rax, rdi
0x18002ffcd  sub     rax, rcx
0x18002ffd0  mov     [rsp+998h+var_958], rax
0x18002ffd5  mov     r15d, 7FFFFFFEh
0x18002ffdb  mov     r8d, r15d
0x18002ffde  mov     [rsp+998h+var_8E8], r15
0x18002ffe6  lea     r9, aControlPanelDe; "\\Control Panel\\Desktop"
0x18002ffed  mov     [rsp+998h+var_8F8], r9
0x18002fff5  mov     [rsp+998h+var_8F0], rcx
0x18002fffd  lea     rdx, [rsp+998h+var_248]
0x180030005  lea     rdx, [rdx+rax*2]
0x180030009  mov     [rsp+998h+var_930], rdx
0x18003000e  mov     rax, r12
0x180030011  mov     [rsp+998h+var_928], rax
0x180030016  test    rcx, rcx
0x180030019  jz      short loc_180030063
0x18003001b  test    r8, r8
0x18003001e  jz      short loc_180030074
0x180030020  movzx   r10d, word ptr [r9]
0x180030024  test    r10w, r10w
0x180030028  jz      short loc_180030074
0x18003002a  add     r9, 2
0x18003002e  mov     [rsp+998h+var_8F8], r9
0x180030036  mov     [rdx], r10w
0x18003003a  add     rdx, 2
0x18003003e  mov     [rsp+998h+var_930], rdx
0x180030043  dec     rcx
0x180030046  mov     [rsp+998h+var_8F0], rcx
0x18003004e  dec     r8
0x180030051  mov     [rsp+998h+var_8E8], r8
0x180030059  inc     rax
0x18003005c  mov     [rsp+998h+var_928], rax
0x180030061  jmp     short loc_180030016
0x180030063  sub     rdx, 2
0x180030067  mov     [rsp+998h+var_930], rdx
0x18003006c  dec     rax
0x18003006f  mov     [rsp+998h+var_928], rax
0x180030074  mov     [rdx], r12w
0x180030078  jmp     short loc_180030085
0x18003007a  mov     [rsp+998h+var_958], r12
0x18003007f  mov     r15d, 7FFFFFFEh
0x180030085  mov     r9d, 20019h
0x18003008b  lea     r8, [rsp+998h+var_248]
0x180030093  mov     rdx, 0FFFFFFFF80000003h
0x18003009a  lea     rcx, [rsp+998h+var_708]
0x1800300a2  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x1800300a8  mov     r14d, eax
0x1800300ab  mov     [rsp+998h+var_968], eax
0x1800300af  test    eax, eax
0x1800300b1  jnz     loc_18003056E
0x1800300b7  lea     r8, [rsp+998h+var_960]
0x1800300bc  lea     rdx, aName; "Name"
0x1800300c3  mov     rcx, rsi
0x1800300c6  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800300cc  lea     rcx, [rsp+998h+var_970]
0x1800300d1  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800300d7  nop
0x1800300d8  lea     r8, [rsp+998h+var_970]
0x1800300dd  lea     rdx, aCoolswitch; "CoolSwitch"
0x1800300e4  lea     rcx, [rsp+998h+var_708]
0x1800300ec  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800300f2  lea     rbx, a1; "1"
0x1800300f9  test    eax, eax
0x1800300fb  jnz     short loc_180030120
0x1800300fd  mov     rdx, rbx
0x180030100  lea     rcx, [rsp+998h+var_970]
0x180030105  call    ??8@YAHAEBVCHString@@PEBG@Z; operator==(CHString const &,ushort const *)
0x18003010a  test    eax, eax
0x18003010c  setnz   r8b
0x180030110  lea     rdx, aCoolswitch; "CoolSwitch"
0x180030117  mov     rcx, rsi
0x18003011a  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180030120  lea     r8, [rsp+998h+var_970]
0x180030125  lea     rdx, aCursorblinkrat; "CursorBlinkRate"
0x18003012c  lea     rcx, [rsp+998h+var_708]
0x180030134  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18003013a  test    eax, eax
0x18003013c  jnz     short loc_180030157
0x18003013e  lea     rcx, [rsp+998h+var_970]
0x180030143  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180030149  mov     rcx, rax; String
0x18003014c  call    cs:__imp__wtoi
0x180030152  mov     r8d, eax
0x180030155  jmp     short loc_18003015D
0x180030157  mov     r8d, 1F4h
0x18003015d  lea     rdx, aCursorblinkrat; "CursorBlinkRate"
0x180030164  mov     rcx, rsi
0x180030167  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18003016d  lea     r8, [rsp+998h+var_970]
0x180030172  lea     rdx, aDragfullwindow; "DragFullWindows"
0x180030179  lea     rcx, [rsp+998h+var_708]
0x180030181  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x180030187  test    eax, eax
0x180030189  jnz     short loc_1800301AE
0x18003018b  mov     rdx, rbx
0x18003018e  lea     rcx, [rsp+998h+var_970]
0x180030193  call    ??8@YAHAEBVCHString@@PEBG@Z; operator==(CHString const &,ushort const *)
0x180030198  test    eax, eax
0x18003019a  setnz   r8b
0x18003019e  lea     rdx, aDragfullwindow; "DragFullWindows"
0x1800301a5  mov     rcx, rsi
0x1800301a8  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800301ae  lea     r8, [rsp+998h+var_970]
0x1800301b3  lea     rdx, aGridgranularit; "GridGranularity"
0x1800301ba  lea     rcx, [rsp+998h+var_708]
0x1800301c2  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800301c8  test    eax, eax
0x1800301ca  jnz     short loc_1800301F3
0x1800301cc  lea     rcx, [rsp+998h+var_970]
0x1800301d1  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800301d7  mov     rcx, rax; String
0x1800301da  call    cs:__imp__wtoi
0x1800301e0  mov     r8d, eax
0x1800301e3  lea     rdx, aGridgranularit; "GridGranularity"
0x1800301ea  mov     rcx, rsi
0x1800301ed  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800301f3  lea     rcx, [rsp+998h+var_958]
0x1800301f8  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800301fe  nop
0x1800301ff  lea     r8, [rsp+998h+var_248]
0x180030207  lea     rdx, aSWindowmetrics; "%s\\WindowMetrics"
0x18003020e  lea     rcx, [rsp+998h+var_958]
0x180030213  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x180030219  lea     rcx, [rsp+998h+var_4A8]
0x180030221  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180030227  nop
0x180030228  lea     rcx, [rsp+998h+var_958]
0x18003022d  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180030233  mov     r8, rax
0x180030236  mov     rdx, 0FFFFFFFF80000003h
0x18003023d  mov     r9d, 20019h
0x180030243  lea     rcx, [rsp+998h+var_4A8]
0x18003024b  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180030251  test    eax, eax
0x180030253  jnz     loc_180030326
0x180030259  lea     r8, [rsp+998h+var_970]
0x18003025e  lea     rdx, aIconspacing; "IconSpacing"
0x180030265  lea     rcx, [rsp+998h+var_4A8]
0x18003026d  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x180030273  test    eax, eax
0x180030275  jnz     short loc_1800302DF
0x180030277  lea     rcx, [rsp+998h+var_970]
0x18003027c  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180030282  mov     rcx, rax; String
0x180030285  call    cs:__imp__wtoi
0x18003028b  lea     rcx, [rsp+998h+var_970]
0x180030290  test    eax, eax
0x180030292  jns     short loc_1800302BA
0x180030294  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003029a  mov     rcx, rax; String
0x18003029d  call    cs:__imp__wtoi
0x1800302a3  mov     ecx, eax
0x1800302a5  mov     eax, 77777777h
0x1800302aa  imul    ecx
0x1800302ac  sub     edx, ecx
0x1800302ae  sar     edx, 3
0x1800302b1  mov     eax, edx
0x1800302b3  shr     eax, 1Fh
0x1800302b6  add     edx, eax
0x1800302b8  jmp     short loc_1800302CB
0x1800302ba  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800302c0  mov     rcx, rax; String
0x1800302c3  call    cs:__imp__wtoi
0x1800302c9  mov     edx, eax
0x1800302cb  lea     r8d, [rdx-20h]
0x1800302cf  lea     rdx, aIconspacing; "IconSpacing"
0x1800302d6  mov     rcx, rsi
0x1800302d9  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800302df  lea     r8, [rsp+998h+var_970]
0x1800302e4  lea     rdx, aIcontitlewrap; "IconTitleWrap"
0x1800302eb  lea     rcx, [rsp+998h+var_4A8]
0x1800302f3  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800302f9  test    eax, eax
0x1800302fb  jnz     short loc_180030312
0x1800302fd  mov     rdx, rbx
0x180030300  lea     rcx, [rsp+998h+var_970]
0x180030305  call    ??8@YAHAEBVCHString@@PEBG@Z; operator==(CHString const &,ushort const *)
0x18003030a  test    eax, eax
0x18003030c  setnz   r8b
0x180030310  jmp     short loc_180030315
0x180030312  mov     r8b, 1
0x180030315  lea     rdx, aIcontitlewrap; "IconTitleWrap"
0x18003031c  mov     rcx, rsi
0x18003031f  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180030325  nop
0x180030326  lea     rcx, [rsp+998h+var_4A8]
  ... truncated ...
```
