# EnumPatchesForSpecificInstance(ushort const *,ushort const *,iaaAppAssignment,ulong,ushort *,tagMSIPATCHSTATE *,CAPITempBufferRef<ushort> &,bool,ulong)

- ea: `0x18003c1d0`
- end: `0x18003e406`
- name: `?EnumPatchesForSpecificInstance@@YAKPEBG0W4iaaAppAssignment@@KPEAGPEAW4tagMSIPATCHSTATE@@AEAV?$CAPITempBufferRef@G@@_NK@Z`
- size: `8758`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180047380`
- `0x1800e7728`

## callees

- `0x18000c4bc`
- `0x18000f1c0`
- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x180014160`
- `0x1800399d0`
- `0x180039bc4`
- `0x18003bd60`
- `0x18003c030`
- `0x18003c1d0`
- `0x18003e40c`
- `0x18003e4c0`
- `0x18003ecd4`
- `0x18003f930`
- `0x1800408a0`
- `0x180040908`
- `0x18004a014`
- `0x18006c9fc`
- `0x180265240`
- `0x1802652d0`
- `0x180266010`

## import_xrefs

- `msvcrt!wcstol` at `0x18003ca9f`
- `msvcrt!wcstol` at `0x18003d48a`
- `msvcrt!wcstol` at `0x18003ca9f`
- `msvcrt!wcstol` at `0x18003d48a`
- `ADVAPI32!RegEnumKeyExW` at `0x18003c4d4`
- `ADVAPI32!RegEnumKeyExW` at `0x18003c4d4`
- `ADVAPI32!RegCloseKey` at `0x18003c6de`
- `ADVAPI32!RegCloseKey` at `0x18003c809`
- `ADVAPI32!RegCloseKey` at `0x18003c89f`
- `ADVAPI32!RegCloseKey` at `0x18003c91a`
- `ADVAPI32!RegCloseKey` at `0x18003ca26`
- `ADVAPI32!RegCloseKey` at `0x18003cb54`
- `ADVAPI32!RegCloseKey` at `0x18003cbce`
- `ADVAPI32!RegCloseKey` at `0x18003cc43`
- `ADVAPI32!RegCloseKey` at `0x18003cccd`
- `ADVAPI32!RegCloseKey` at `0x18003c6de`
- `ADVAPI32!RegCloseKey` at `0x18003c809`
- `ADVAPI32!RegCloseKey` at `0x18003c89f`
- `ADVAPI32!RegCloseKey` at `0x18003c91a`
- `ADVAPI32!RegCloseKey` at `0x18003ca26`
- `ADVAPI32!RegCloseKey` at `0x18003cb54`
- `ADVAPI32!RegCloseKey` at `0x18003cbce`
- `ADVAPI32!RegCloseKey` at `0x18003cc43`
- `ADVAPI32!RegCloseKey` at `0x18003cccd`
- `KERNEL32!InitializeCriticalSection` at `0x18003c276`
- `KERNEL32!InitializeCriticalSection` at `0x18003c2b3`
- `KERNEL32!InitializeCriticalSection` at `0x18003c2f0`
- `KERNEL32!InitializeCriticalSection` at `0x18003c5a2`
- `KERNEL32!InitializeCriticalSection` at `0x18003c5cf`
- `KERNEL32!InitializeCriticalSection` at `0x18003c7ad`
- `KERNEL32!InitializeCriticalSection` at `0x18003c9c2`
- `KERNEL32!InitializeCriticalSection` at `0x18003d0f7`
- `KERNEL32!InitializeCriticalSection` at `0x18003d134`
- `KERNEL32!InitializeCriticalSection` at `0x18003e2e6`
- `KERNEL32!InitializeCriticalSection` at `0x18003e325`
- `KERNEL32!InitializeCriticalSection` at `0x18003c276`
- `KERNEL32!InitializeCriticalSection` at `0x18003c2b3`
- `KERNEL32!InitializeCriticalSection` at `0x18003c2f0`
- `KERNEL32!InitializeCriticalSection` at `0x18003c5a2`
- `KERNEL32!InitializeCriticalSection` at `0x18003c5cf`
- `KERNEL32!InitializeCriticalSection` at `0x18003c7ad`
- `KERNEL32!InitializeCriticalSection` at `0x18003c9c2`
- `KERNEL32!InitializeCriticalSection` at `0x18003d0f7`
- `KERNEL32!InitializeCriticalSection` at `0x18003d134`
- `KERNEL32!InitializeCriticalSection` at `0x18003e2e6`
- `KERNEL32!InitializeCriticalSection` at `0x18003e325`
- `KERNEL32!DeleteCriticalSection` at `0x18003c846`
- `KERNEL32!DeleteCriticalSection` at `0x18003c8d0`
- `KERNEL32!DeleteCriticalSection` at `0x18003c94b`
- `KERNEL32!DeleteCriticalSection` at `0x18003ca63`
- `KERNEL32!DeleteCriticalSection` at `0x18003cb8d`
- `KERNEL32!DeleteCriticalSection` at `0x18003cbf9`
- `KERNEL32!DeleteCriticalSection` at `0x18003cc6e`
- `KERNEL32!DeleteCriticalSection` at `0x18003c846`
- `KERNEL32!DeleteCriticalSection` at `0x18003c8d0`
- `KERNEL32!DeleteCriticalSection` at `0x18003c94b`
- `KERNEL32!DeleteCriticalSection` at `0x18003ca63`
- `KERNEL32!DeleteCriticalSection` at `0x18003cb8d`
- `KERNEL32!DeleteCriticalSection` at `0x18003cbf9`
- `KERNEL32!DeleteCriticalSection` at `0x18003cc6e`
- `KERNEL32!LeaveCriticalSection` at `0x18003c6ff`
- `KERNEL32!LeaveCriticalSection` at `0x18003c833`
- `KERNEL32!LeaveCriticalSection` at `0x18003c8c0`
- `KERNEL32!LeaveCriticalSection` at `0x18003c93b`
- `KERNEL32!LeaveCriticalSection` at `0x18003ca50`
- `KERNEL32!LeaveCriticalSection` at `0x18003cb7a`
- `KERNEL32!LeaveCriticalSection` at `0x18003cbe9`
- `KERNEL32!LeaveCriticalSection` at `0x18003cc5e`
- `KERNEL32!LeaveCriticalSection` at `0x18003ccee`
- `KERNEL32!LeaveCriticalSection` at `0x18003c6ff`
- `KERNEL32!LeaveCriticalSection` at `0x18003c833`
- `KERNEL32!LeaveCriticalSection` at `0x18003c8c0`
- `KERNEL32!LeaveCriticalSection` at `0x18003c93b`
- `KERNEL32!LeaveCriticalSection` at `0x18003ca50`
- `KERNEL32!LeaveCriticalSection` at `0x18003cb7a`
- `KERNEL32!LeaveCriticalSection` at `0x18003cbe9`
- `KERNEL32!LeaveCriticalSection` at `0x18003cc5e`
- `KERNEL32!LeaveCriticalSection` at `0x18003ccee`
- `KERNEL32!EnterCriticalSection` at `0x18003c6c9`
- `KERNEL32!EnterCriticalSection` at `0x18003c7f1`
- `KERNEL32!EnterCriticalSection` at `0x18003c88a`
- `KERNEL32!EnterCriticalSection` at `0x18003c905`
- `KERNEL32!EnterCriticalSection` at `0x18003ca0e`
- `KERNEL32!EnterCriticalSection` at `0x18003cb38`
- `KERNEL32!EnterCriticalSection` at `0x18003cbb9`
- `KERNEL32!EnterCriticalSection` at `0x18003cc2e`
- `KERNEL32!EnterCriticalSection` at `0x18003ccb8`
- `KERNEL32!EnterCriticalSection` at `0x18003c6c9`
- `KERNEL32!EnterCriticalSection` at `0x18003c7f1`
- `KERNEL32!EnterCriticalSection` at `0x18003c88a`
- `KERNEL32!EnterCriticalSection` at `0x18003c905`
- `KERNEL32!EnterCriticalSection` at `0x18003ca0e`
- `KERNEL32!EnterCriticalSection` at `0x18003cb38`
- `KERNEL32!EnterCriticalSection` at `0x18003cbb9`
- `KERNEL32!EnterCriticalSection` at `0x18003cc2e`
- `KERNEL32!EnterCriticalSection` at `0x18003ccb8`
- `KERNEL32!GlobalAlloc` at `0x18003d5e9`
- `KERNEL32!GlobalAlloc` at `0x18003d5e9`
- `KERNEL32!GlobalFree` at `0x18003c655`
- `KERNEL32!GlobalFree` at `0x18003c862`
- `KERNEL32!GlobalFree` at `0x18003c8e6`
- `KERNEL32!GlobalFree` at `0x18003c961`
- `KERNEL32!GlobalFree` at `0x18003ca7f`
- `KERNEL32!GlobalFree` at `0x18003cba9`
- `KERNEL32!GlobalFree` at `0x18003cc0f`
- `KERNEL32!GlobalFree` at `0x18003cca3`
- `KERNEL32!GlobalFree` at `0x18003cd93`
- `KERNEL32!GlobalFree` at `0x18003cdb2`
- `KERNEL32!GlobalFree` at `0x18003ced4`
- `KERNEL32!GlobalFree` at `0x18003cf24`
- `KERNEL32!GlobalFree` at `0x18003d1f6`
- `KERNEL32!GlobalFree` at `0x18003d355`
- `KERNEL32!GlobalFree` at `0x18003d383`
- `KERNEL32!GlobalFree` at `0x18003d4a9`
- `KERNEL32!GlobalFree` at `0x18003d568`
- `KERNEL32!GlobalFree` at `0x18003d598`
- `KERNEL32!GlobalFree` at `0x18003d6af`
- `KERNEL32!GlobalFree` at `0x18003d6e6`
- `KERNEL32!GlobalFree` at `0x18003d75a`
- `KERNEL32!GlobalFree` at `0x18003d7a4`
- `KERNEL32!GlobalFree` at `0x18003d7fb`
- `KERNEL32!GlobalFree` at `0x18003d851`
- `KERNEL32!GlobalFree` at `0x18003d8de`
- `KERNEL32!GlobalFree` at `0x18003d915`
- `KERNEL32!GlobalFree` at `0x18003d96e`
- `KERNEL32!GlobalFree` at `0x18003da2a`
- `KERNEL32!GlobalFree` at `0x18003dac8`
- `KERNEL32!GlobalFree` at `0x18003daeb`
- `KERNEL32!GlobalFree` at `0x18003db44`
- `KERNEL32!GlobalFree` at `0x18003dbc1`
- `KERNEL32!GlobalFree` at `0x18003dbdb`
- `KERNEL32!GlobalFree` at `0x18003dc32`
- `KERNEL32!GlobalFree` at `0x18003dcbb`
- `KERNEL32!GlobalFree` at `0x18003de10`
- `KERNEL32!GlobalFree` at `0x18003de3f`
- `KERNEL32!GlobalFree` at `0x18003dea1`
- `KERNEL32!GlobalFree` at `0x18003ded9`
- `KERNEL32!GlobalFree` at `0x18003def4`
- `KERNEL32!GlobalFree` at `0x18003df28`
- `KERNEL32!GlobalFree` at `0x18003df62`
- `KERNEL32!GlobalFree` at `0x18003dfcd`
- `KERNEL32!GlobalFree` at `0x18003dfec`
- `KERNEL32!GlobalFree` at `0x18003e0c8`
- `KERNEL32!GlobalFree` at `0x18003e149`
- `KERNEL32!GlobalFree` at `0x18003e1cf`
- `KERNEL32!GlobalFree` at `0x18003e1e7`
- `KERNEL32!GlobalFree` at `0x18003e25a`
- `KERNEL32!GlobalFree` at `0x18003e272`
- `KERNEL32!GlobalFree` at `0x18003e28a`
- `KERNEL32!GlobalFree` at `0x18003e395`
- `KERNEL32!GlobalFree` at `0x18003e3ad`
- `KERNEL32!GlobalFree` at `0x18003e3e1`
- `KERNEL32!GlobalFree` at `0x18003e3f5`
- `KERNEL32!GlobalFree` at `0x18003c655`
- `KERNEL32!GlobalFree` at `0x18003c862`
- `KERNEL32!GlobalFree` at `0x18003c8e6`
- `KERNEL32!GlobalFree` at `0x18003c961`
- `KERNEL32!GlobalFree` at `0x18003ca7f`
- `KERNEL32!GlobalFree` at `0x18003cba9`
- `KERNEL32!GlobalFree` at `0x18003cc0f`
- `KERNEL32!GlobalFree` at `0x18003cca3`
- `KERNEL32!GlobalFree` at `0x18003cd93`
- `KERNEL32!GlobalFree` at `0x18003cdb2`
- `KERNEL32!GlobalFree` at `0x18003ced4`
- `KERNEL32!GlobalFree` at `0x18003cf24`
- `KERNEL32!GlobalFree` at `0x18003d1f6`
- `KERNEL32!GlobalFree` at `0x18003d355`
- `KERNEL32!GlobalFree` at `0x18003d383`
- `KERNEL32!GlobalFree` at `0x18003d4a9`
- `KERNEL32!GlobalFree` at `0x18003d568`
- `KERNEL32!GlobalFree` at `0x18003d598`
- `KERNEL32!GlobalFree` at `0x18003d6af`
- `KERNEL32!GlobalFree` at `0x18003d6e6`
- `KERNEL32!GlobalFree` at `0x18003d75a`
- `KERNEL32!GlobalFree` at `0x18003d7a4`
- `KERNEL32!GlobalFree` at `0x18003d7fb`
- `KERNEL32!GlobalFree` at `0x18003d851`
- `KERNEL32!GlobalFree` at `0x18003d8de`
- `KERNEL32!GlobalFree` at `0x18003d915`
- `KERNEL32!GlobalFree` at `0x18003d96e`
- `KERNEL32!GlobalFree` at `0x18003da2a`
- `KERNEL32!GlobalFree` at `0x18003dac8`
- `KERNEL32!GlobalFree` at `0x18003daeb`
- `KERNEL32!GlobalFree` at `0x18003db44`
- `KERNEL32!GlobalFree` at `0x18003dbc1`
- `KERNEL32!GlobalFree` at `0x18003dbdb`
- `KERNEL32!GlobalFree` at `0x18003dc32`
- `KERNEL32!GlobalFree` at `0x18003dcbb`
- `KERNEL32!GlobalFree` at `0x18003de10`
- `KERNEL32!GlobalFree` at `0x18003de3f`
- `KERNEL32!GlobalFree` at `0x18003dea1`
- `KERNEL32!GlobalFree` at `0x18003ded9`
- `KERNEL32!GlobalFree` at `0x18003def4`
- `KERNEL32!GlobalFree` at `0x18003df28`
- `KERNEL32!GlobalFree` at `0x18003df62`
- `KERNEL32!GlobalFree` at `0x18003dfcd`
- `KERNEL32!GlobalFree` at `0x18003dfec`
- `KERNEL32!GlobalFree` at `0x18003e0c8`
- `KERNEL32!GlobalFree` at `0x18003e149`
- `KERNEL32!GlobalFree` at `0x18003e1cf`

## string_xrefs

- `0x18003c624`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18003cd1b`: `InstallProperties`

## pseudocode

```c
__int64 __fastcall EnumPatchesForSpecificInstance(
        const WCHAR *a1,
        wchar_t *a2,
        unsigned int a3,
        int a4,
        WCHAR *a5,
        int *a6,
        __int64 a7,
        char a8,
        int a9)
{
  int v10; // r13d
  char v12; // r14
  unsigned int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // r9
  int v17; // ecx
  int v18; // ebx
  DWORD v19; // r15d
  unsigned int v20; // r14d
  int v21; // r12d
  LPWSTR v22; // rax
  __int64 v23; // rcx
  LPWSTR v24; // rdi
  const unsigned __int16 *v25; // rcx
  int CurrentUserStringSID; // ebx
  HGLOBAL v27; // rbx
  __int64 v28; // r9
  wchar_t *v29; // rbx
  int AppliedPatchInfoInternal; // ebx
  int v31; // eax
  int v32; // ebx
  const WCHAR *v33; // rdi
  __int64 v34; // r9
  _WORD *v35; // r8
  int v36; // ebx
  __int64 v37; // r15
  __int64 v38; // r14
  unsigned __int16 *v39; // rdi
  WCHAR *v40; // r10
  LPWSTR v41; // rcx
  __int64 v42; // rdx
  LPWSTR v43; // r8
  __int64 v44; // rax
  LPWSTR v45; // rcx
  const WCHAR *v47; // rdx
  unsigned __int16 *v48; // rax
  int v49; // edx
  unsigned int v50; // r13d
  int Value; // esi
  const WCHAR *v52; // rsi
  HKEY *v53; // rax
  unsigned int v54; // r8d
  int lpReserved; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  char v58; // [rsp+60h] [rbp-A0h]
  unsigned int v59; // [rsp+64h] [rbp-9Ch]
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v61; // [rsp+70h] [rbp-90h]
  int v62; // [rsp+78h] [rbp-88h]
  wchar_t *String1; // [rsp+80h] [rbp-80h]
  DWORD Type; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-74h] BYREF
  int v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  LPWSTR lpsz; // [rsp+A0h] [rbp-60h]
  int *v69; // [rsp+A8h] [rbp-58h]
  HGLOBAL v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B8h] [rbp-48h]
  int v72; // [rsp+BCh] [rbp-44h]
  _WORD v73[4]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *String; // [rsp+C8h] [rbp-38h]
  int v75; // [rsp+D0h] [rbp-30h]
  int v76; // [rsp+D4h] [rbp-2Ch]
  _BYTE v77[24]; // [rsp+D8h] [rbp-28h] BYREF
  HKEY v78[2]; // [rsp+F0h] [rbp-10h] BYREF
  HGLOBAL v79; // [rsp+100h] [rbp+0h] BYREF
  int v80; // [rsp+108h] [rbp+8h]
  __int16 v81; // [rsp+110h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION v82; // [rsp+118h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION v83; // [rsp+150h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION v84; // [rsp+178h] [rbp+78h] BYREF
  LPWSTR lpName; // [rsp+1B0h] [rbp+B0h]
  signed int v86; // [rsp+1B8h] [rbp+B8h]
  int v87; // [rsp+1BCh] [rbp+BCh]
  _BYTE v88[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _RTL_CRITICAL_SECTION v89; // [rsp+210h] [rbp+110h] BYREF
  struct _RTL_CRITICAL_SECTION v90; // [rsp+238h] [rbp+138h] BYREF
  HKEY v91[2]; // [rsp+260h] [rbp+160h] BYREF
  HGLOBAL v92; // [rsp+270h] [rbp+170h]
  int v93; // [rsp+278h] [rbp+178h]
  __int16 v94; // [rsp+280h] [rbp+180h] BYREF
  struct _RTL_CRITICAL_SECTION v95; // [rsp+288h] [rbp+188h] BYREF
  HKEY v96[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 *v97; // [rsp+2C0h] [rbp+1C0h]
  int v98; // [rsp+2C8h] [rbp+1C8h]
  __int16 v99; // [rsp+2D0h] [rbp+1D0h] BYREF
  struct _RTL_CRITICAL_SECTION v100; // [rsp+2D8h] [rbp+1D8h] BYREF
  struct _RTL_CRITICAL_SECTION v101; // [rsp+300h] [rbp+200h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+328h] [rbp+228h] BYREF
  HKEY hKey[2]; // [rsp+350h] [rbp+250h] BYREF
  __int16 *v104; // [rsp+360h] [rbp+260h]
  int v105; // [rsp+368h] [rbp+268h]
  __int16 v106; // [rsp+370h] [rbp+270h] BYREF
  struct _RTL_CRITICAL_SECTION v107; // [rsp+378h] [rbp+278h] BYREF
  HGLOBAL v108; // [rsp+3A0h] [rbp+2A0h]
  int v109; // [rsp+3A8h] [rbp+2A8h]
  unsigned __int16 v110[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  HGLOBAL v111; // [rsp+5C0h] [rbp+4C0h] BYREF
  int v112; // [rsp+5C8h] [rbp+4C8h]
  int v113; // [rsp+5CCh] [rbp+4CCh]
  unsigned __int16 v114[320]; // [rsp+5D0h] [rbp+4D0h] BYREF
  HGLOBAL hMem; // [rsp+850h] [rbp+750h] BYREF
  int v116; // [rsp+858h] [rbp+758h]
  int v117; // [rsp+85Ch] [rbp+75Ch]
  unsigned __int16 v118[1024]; // [rsp+860h] [rbp+760h] BYREF

  lpsz = a5;
  v10 = a3;
  v67 = a7;
  v61 = a1;
  v101.OwningThread = &v101.SpinCount;
  v62 = a4;
  v59 = a3;
  String1 = a2;
  v69 = a6;
  *(_OWORD *)&v101.DebugInfo = 0;
  LODWORD(v101.LockSemaphore) = 1;
  LOWORD(v101.SpinCount) = 0;
  InitializeCriticalSection(&CriticalSection);
  v98 = 1;
  *(_OWORD *)v96 = 0;
  v97 = &v99;
  v99 = 0;
  InitializeCriticalSection(&v100);
  v105 = 1;
  *(_OWORD *)hKey = 0;
  v104 = &v106;
  v106 = 0;
  InitializeCriticalSection(&v107);
  LODWORD(v60) = 0;
  v12 = 1;
  v58 = 1;
  if ( v10 != 1 )
  {
    if ( v10 == 3 )
    {
      v13 = OpenAdvertisedProductKeyPacked(a1, &v101, 0, 0xFFFFFFFFLL, &v60);
      v10 = v60;
      v59 = v60;
      goto LABEL_4;
    }
LABEL_3:
    v13 = OpenSpecificUsersAdvertisedSubKeyPacked(v10, a2, (WCHAR *)L"Products", a1, &v101, 0);
LABEL_4:
    v14 = v13;
    goto LABEL_5;
  }
  if ( !a2 || !*a2 || IsCurrentUser(a2) )
    goto LABEL_3;
  v112 = 261;
  v111 = v114;
  if ( (int)StringCchPrintfW(v114, 0x105u, L"%s\\%s", L"Products", a1) < 0 )
  {
    if ( v112 > 261 )
      GlobalFree(v111);
    v112 = 261;
    v111 = v114;
    goto LABEL_166;
  }
  v12 = 0;
  LOBYTE(lpReservedb) = 0;
  v58 = 0;
  v10 = 1;
  v59 = 1;
  v14 = OpenInstalledUserDataSubKeyPacked(a2, 0, v111, &v101, lpReservedb, g_samRead, 1, 0);
  if ( v112 > 261 )
    GlobalFree(v111);
LABEL_5:
  if ( v14 )
  {
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    CRegHandle::~CRegHandle((CRegHandle *)v96);
    CRegHandle::~CRegHandle((CRegHandle *)&v101);
    if ( v14 == 2 )
      return 1605;
    return v14;
  }
  v15 = CRegHandleStatic::operator&(v96);
  v16 = 131097;
  if ( !g_fWoW && g_fWinNT64 )
    v16 = 131353;
  v14 = ((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const WCHAR *, _QWORD, __int64, __int64))RegOpenKeyAPI)(
          v101.DebugInfo,
          L"Patches",
          0,
          v16,
          v15);
  if ( v14 )
  {
    if ( v14 == 2 )
    {
      v50 = 259;
      if ( !v12 )
        v50 = 1626;
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      CRegHandle::~CRegHandle((CRegHandle *)v96);
      CRegHandle::~CRegHandle((CRegHandle *)&v101);
      return v50;
    }
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    CRegHandle::~CRegHandle((CRegHandle *)v96);
    CRegHandle::~CRegHandle((CRegHandle *)&v101);
    return v14;
  }
  v109 = 260;
  v108 = v110;
  if ( (int)StringCchPrintfW(v110, 0x104u, L"%s\\%s\\%s", L"Products", a1, L"Patches") < 0 )
    goto LABEL_189;
  LOBYTE(lpReserved) = 0;
  v17 = OpenInstalledUserDataSubKeyPacked(a2, a1, v108, hKey, lpReserved, g_samRead, v10, 0);
  v66 = v17;
  if ( a8 )
  {
    if ( a6 )
      *a6 = 1;
    hMem = v118;
    v47 = L"AllPatches";
    v116 = 118;
    LODWORD(v60) = 0;
    if ( v12 )
      v47 = L"Patches";
    v117 = 118;
    if ( (unsigned int)MsiRegQueryValueExW(v96[0], v47, (__int64)&hMem, (__int64)&v60) != 2 )
    {
      if ( v116 > 118 )
        GlobalFree(hMem);
      hMem = v118;
      v116 = 118;
      if ( v109 > 260 )
        GlobalFree(v108);
      v109 = 260;
      v108 = v110;
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      CRegHandle::~CRegHandle((CRegHandle *)v96);
      CRegHandle::~CRegHandle((CRegHandle *)&v101);
      return 1610;
    }
    if ( !v12 )
    {
      if ( v116 > 118 )
        GlobalFree(hMem);
      hMem = v118;
      v116 = 118;
      if ( v109 > 260 )
        GlobalFree(v108);
      v109 = 260;
      v108 = v110;
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      CRegHandle::~CRegHandle((CRegHandle *)v96);
      CRegHandle::~CRegHandle((CRegHandle *)&v101);
      return 1626;
    }
    if ( v116 > 118 )
      GlobalFree(hMem);
    v116 = 118;
    hMem = v118;
LABEL_197:
    if ( v109 > 260 )
      GlobalFree(v108);
    v109 = 260;
    v108 = v110;
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    CRegHandle::~CRegHandle((CRegHandle *)v96);
    CRegHandle::~CRegHandle((CRegHandle *)&v101);
    return 259;
  }
  v18 = a9;
  if ( v17 && (a9 & 1) == 0 )
    goto LABEL_197;
  v71 = 1;
  v19 = 0;
  lpName = (LPWSTR)v88;
  LODWORD(v60) = 0;
  v20 = 0;
  v70 = v73;
  Type = 0;
  v86 = 33;
  if ( !v58 || (v21 = 0, (a9 & 1) == 0) )
    v21 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                if ( v20 )
                {
                  CAPITempBuffer<unsigned short,1>::Destroy(&v70);
                  if ( v86 > 33 )
                    GlobalFree(lpName);
                  if ( v109 > 260 )
                    GlobalFree(v108);
                  v109 = 260;
                  v108 = v110;
                  CRegHandle::~CRegHandle((CRegHandle *)hKey);
                  CRegHandle::~CRegHandle((CRegHandle *)v96);
                  CRegHandle::~CRegHandle((CRegHandle *)&v101);
                  return v20;
                }
                if ( v21 )
                {
                  cchName = v86;
                  v20 = RegEnumKeyExW(hKey[0], v19, lpName, &cchName, 0, 0, 0, 0);
                  *(_WORD *)v70 = 0;
                }
                else
                {
                  v72 = 1;
                  v87 = 33;
                  v20 = MsiRegEnumValueW(v96[0], v19, (int)lpReserveda, &Type, (DWORD)&v70);
                }
                if ( v20 != 2 )
                  break;
                v20 = 259;
LABEL_181:
                v18 &= ~1u;
                a9 = v18;
                if ( !v21 && !v66 && v18 )
                {
                  v20 = 0;
                  v21 = 1;
                  v19 = 0;
                }
              }
              if ( v20 == 259 )
                goto LABEL_181;
              if ( !v20 )
                break;
              v20 = 1610;
            }
            v22 = lpName;
            ++v19;
            if ( lpName )
            {
              v23 = 33;
              do
              {
                if ( !*v22 )
                  break;
                ++v22;
                --v23;
              }
              while ( v23 );
              if ( v23 && v23 == 1 )
                break;
            }
          }
          String = (wchar_t *)v77;
          v75 = 12;
          v76 = 12;
          if ( v59 != 3 )
            break;
          v20 = 1610;
        }
        if ( v61 )
          break;
LABEL_86:
        v20 = 1610;
        if ( v75 > 12 )
          GlobalFree(String);
      }
      v24 = lpName;
      v83.OwningThread = &v83.SpinCount;
      LODWORD(v83.LockSemaphore) = 1;
      LOWORD(v83.SpinCount) = 0;
      *(_OWORD *)&v83.DebugInfo = 0;
      InitializeCriticalSection(&v84);
      v80 = 1;
      v79 = &v81;
      v81 = 0;
      *(_OWORD *)v78 = 0;
      InitializeCriticalSection(&v82);
      v111 = v114;
      hMem = v118;
      v112 = 318;
      v116 = 64;
      if ( v59 == 2 )
      {
        v25 = L"S-1-5-18";
        goto LABEL_30;
      }
      v25 = 0;
      if ( v59 > 1 )
        goto LABEL_30;
      if ( String1 )
      {
        v25 = String1;
LABEL_30:
        CurrentUserStringSID = StringCchPrintfW(
                                 v114,
                                 0x13Eu,
                                 L"%s\\%s",
                                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                 v25);
        if ( v116 <= 64 )
          goto LABEL_32;
LABEL_31:
        GlobalFree(hMem);
        goto LABEL_32;
      }
      v117 = 64;
      CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
      if ( !CurrentUserStringSID )
      {
        v25 = (const unsigned __int16 *)hMem;
        goto LABEL_30;
      }
      if ( v116 > 64 )
        goto LABEL_31;
LABEL_32:
      if ( !CurrentUserStringSID )
      {
        hMem = v118;
        v116 = 1024;
        lpReserveda = L"Products";
        if ( (int)StringCchPrintfW(v118, 0x400u, L"%s\\%s\\%s", v111) < 0 )
        {
          if ( v116 > 1024 )
            GlobalFree(hMem);
          hMem = v118;
          v116 = 1024;
          if ( v112 > 318 )
            GlobalFree(v111);
          goto LABEL_42;
        }
        v27 = hMem;
        EnterCriticalSection(&v84);
        if ( v83.DebugInfo )
        {
          RegCloseKey((HKEY)v83.DebugInfo);
          v83.DebugInfo = 0;
          *(_WORD *)v83.OwningThread = 0;
        }
        LeaveCriticalSection(&v84);
        v28 = g_samRead;
        if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
          LODWORD(v28) = g_samRead | 0x100;
        lpReserveda = (const unsigned __int16 *)&v83;
        CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, __int64))RegOpenKeyAPI)(
                                 -2147483646,
                                 v27,
                                 0,
                                 v28);
        if ( v116 > 1024 )
          GlobalFree(hMem);
      }
      if ( v112 > 318 )
        GlobalFree(v111);
      if ( !CurrentUserStringSID )
      {
        EnterCriticalSection(&v82);
        if ( v78[0] )
        {
          RegCloseKey(v78[0]);
          v78[0] = 0;
          *(_WORD *)v79 = 0;
        }
        LeaveCriticalSection(&v82);
        v34 = g_samRead;
        if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
          LODWORD(v34) = g_samRead | 0x100;
        lpReserveda = (const unsigned __int16 *)v78;
        if ( !(unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const unsigned __int16 *, _QWORD, __int64))RegOpenKeyAPI)(
                              v83.DebugInfo,
                              L"InstallProperties",
                              0,
                              v34) )
        {
          CRegHandle::~CRegHandle((CRegHandle *)v78);
          CRegHandle::~CRegHandle((CRegHandle *)&v83);
          v29 = String1;
          goto LABEL_56;
        }
      }
LABEL_42:
      v29 = String1;
      if ( v59 == 1 && String1 && *String1 && !IsCurrentUser(String1) )
        goto LABEL_77;
      LODWORD(v89.LockSemaphore) = 1;
      v89.OwningThread = &v89.SpinCount;
      LOWORD(v89.SpinCount) = 0;
      *(_OWORD *)&v89.DebugInfo = 0;
      InitializeCriticalSection(&v90);
      if ( (unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(v59, v29, (WCHAR *)L"Products", v61, &v89, 0) )
      {
        EnterCriticalSection(&v90);
        if ( v89.DebugInfo )
        {
          RegCloseKey((HKEY)v89.DebugInfo);
          v89.DebugInfo = 0;
          *(_WORD *)v89.OwningThread = 0;
        }
        LeaveCriticalSection(&v90);
        DeleteCriticalSection(&v90);
        if ( SLODWORD(v89.LockSemaphore) > 1 )
          GlobalFree(v89.OwningThread);
LABEL_77:
        EnterCriticalSection(&v82);
        if ( v78[0] )
        {
          RegCloseKey(v78[0]);
          v78[0] = 0;
          *(_WORD *)v79 = 0;
        }
        LeaveCriticalSection(&v82);
        DeleteCriticalSection(&v82);
        if ( v80 > 1 )
          GlobalFree(v79);
        v80 = 1;
        v79 = &v81;
        EnterCriticalSection(&v84);
        if ( v83.DebugInfo )
        {
          RegCloseKey((HKEY)v83.DebugInfo);
          v83.DebugInfo = 0;
          *(_WORD *)v83.OwningThread = 0;
        }
        LeaveCriticalSection(&v84);
        DeleteCriticalSection(&v84);
        if ( SLODWORD(v83.LockSemaphore) > 1 )
          GlobalFree(v83.OwningThread);
LABEL_85:
        v18 = a9;
        goto LABEL_86;
      }
      EnterCriticalSection(&v90);
      if ( v89.DebugInfo )
      {
        RegCloseKey((HKEY)v89.DebugInfo);
        v89.DebugInfo = 0;
        *(_WORD *)v89.OwningThread = 0;
      }
      LeaveCriticalSection(&v90);
      DeleteCriticalSection(&v90);
      if ( SLODWORD(v89.LockSemaphore) > 1 )
        GlobalFree(v89.OwningThread);
      LODWORD(v89.LockSemaphore) = 1;
      v89.OwningThread = &v89.SpinCount;
      EnterCriticalSection(&v82);
      if ( v78[0] )
      {
        RegCloseKey(v78[0]);
        v78[0] = 0;
        *(_WORD *)v79 = 0;
      }
      LeaveCriticalSection(&v82);
      DeleteCriticalSection(&v82);
      if ( v80 > 1 )
        GlobalFree(v79);
      v80 = 1;
      v79 = &v81;
      EnterCriticalSection(&v84);
      if ( v83.DebugInfo )
      {
        RegCloseKey((HKEY)v83.DebugInfo);
        v83.DebugInfo = 0;
        *(_WORD *)v83.OwningThread = 0;
      }
      LeaveCriticalSection(&v84);
      DeleteCriticalSection(&v84);
      if ( SLODWORD(v83.LockSemaphore) > 1 )
        GlobalFree(v83.OwningThread);
LABEL_56:
      LOBYTE(lpReserveda) = 0;
      if ( !(unsigned __int8)IsPatchAppliedToProduct(v24, v61, v29, v59) )
        goto LABEL_85;
      v93 = 1;
      v92 = &v94;
      v94 = 0;
      *(_OWORD *)v91 = 0;
      InitializeCriticalSection(&v95);
      lpReserveda = L"State";
      AppliedPatchInfoInternal = GetAppliedPatchInfoInternal(v59, v61, v29, v24);
      EnterCriticalSection(&v95);
      if ( v91[0] )
      {
        RegCloseKey(v91[0]);
        v91[0] = 0;
        *(_WORD *)v92 = 0;
      }
      LeaveCriticalSection(&v95);
      DeleteCriticalSection(&v95);
      if ( v93 > 1 )
        GlobalFree(v92);
      if ( AppliedPatchInfoInternal )
        goto LABEL_85;
      v31 = wcstol(String, 0, 10);
      v32 = v31;
      if ( !v31 )
        goto LABEL_85;
      if ( (a9 & v31) == v31 && (v21 || v31 == 1) )
        break;
      if ( v75 > 12 )
        goto LABEL_194;
LABEL_72:
      v18 = a9;
    }
    if ( v59 != 1 )
      goto LABEL_70;
    if ( !v58 )
      goto LABEL_70;
    v33 = lpName;
    if ( String1 )
    {
      if ( *String1 && !IsCurrentUser(String1) )
        goto LABEL_70;
    }
    LODWORD(v83.LockSemaphore) = 1;
    v83.OwningThread = &v83.SpinCount;
    LOWORD(v83.SpinCount) = 0;
    *(_OWORD *)&v83.DebugInfo = 0;
    InitializeCriticalSection(&v84);
    v93 = 1;
    v92 = &v94;
    v94 = 0;
    *(_OWORD *)v91 = 0;
    InitializeCriticalSection(&v95);
    if ( (unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(1, String1, (WCHAR *)L"Products", v61, &v83, 0) )
      goto LABEL_265;
    v53 = (HKEY *)CRegHandleStatic::operator&(v91);
    if ( MsiRegOpen64bitKey((HKEY)v83.DebugInfo, L"Patches", v54, g_samRead, v53) )
      goto LABEL_265;
    v78[0] = (HKEY)&v79;
    v78[1] = (HKEY)0x2100000021LL;
    Value = MsiRegQueryValueExW(v91[0], v33, (__int64)v78, 0);
    if ( SLODWORD(v78[1]) > 33 )
      GlobalFree(v78[0]);
    if ( Value )
    {
LABEL_265:
      CRegHandle::~CRegHandle((CRegHandle *)v91);
      CRegHandle::~CRegHandle((CRegHandle *)&v83);
      goto LABEL_70;
    }
    v52 = v61;
    v111 = v114;
    v112 = 261;
    v113 = 261;
    if ( (unsigned int)GetAppliedPatchInfoInternal(1, v61, String1, v33, L"LocalPackage", &v111) != 1647 )
      break;
    v116 = 39;
    hMem = v118;
    LODWORD(v78[1]) = 39;
    v78[0] = (HKEY)&v79;
    if ( !(unsigned int)UnpackGUID(v33, v118, 39, 1) )
      *(_WORD *)hMem = 0;
    if ( !(unsigned int)UnpackGUID(v52, v78[0], LODWORD(v78[1]), 1) )
      *(_WORD *)v78[0] = 0;
    if ( g_dmDiagnosticMode && (g_dwLogMode & 0x2000) != 0 )
      DebugString(
        5,
        0,
        0,
        L"Detected roamed patch '%s' for product '%s'. This patch will be ignored.",
        (const unsigned __int16 *)hMem,
        (const unsigned __int16 *)v78[0],
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( SLODWORD(v78[1]) > 39 )
      GlobalFree(v78[0]);
    v78[0] = (HKEY)&v79;
    LODWORD(v78[1]) = 39;
    if ( v116 > 39 )
      GlobalFree(hMem);
    hMem = v118;
    v116 = 39;
    if ( v112 > 261 )
      GlobalFree(v111);
    v112 = 261;
    v111 = v114;
    CRegHandle::~CRegHandle((CRegHandle *)v91);
    CRegHandle::~CRegHandle((CRegHandle *)&v83);
    if ( v75 <= 12 )
      goto LABEL_72;
LABEL_194:
    GlobalFree(String);
    v18 = a9;
  }
  if ( v112 > 261 )
    GlobalFree(v111);
  v112 = 261;
  v111 = v114;
  CRegHandle::~CRegHandle((CRegHandle *)v91);
  CRegHandle::~CRegHandle((CRegHandle *)&v83);
LABEL_70:
  if ( (_DWORD)v60 != v62 )
  {
    LODWORD(v60) = v60 + 1;
    if ( v75 > 12 )
      goto LABEL_194;
    goto LABEL_72;
  }
  if ( v69 )
    *v69 = v32;
  if ( v32 != 1 )
    *(_WORD *)v70 = 0;
  v35 = v70;
  if ( *(_WORD *)v70 )
  {
    v36 = v71;
    goto LABEL_106;
  }
  if ( v70 != v73 )
  {
    v49 = v71;
    if ( v71 <= 1 )
    {
      if ( v71 )
        goto LABEL_143;
    }
    else
    {
      v49 = 1;
      do
      {
LABEL_143:
        --v49;
        v73[v49] = v35[v49];
        v35 = v70;
      }
      while ( v49 );
    }
    if ( v35 != v73 )
      GlobalFree(v35);
  }
  v35 = v73;
  v36 = 1;
  v70 = v73;
  v71 = 1;
LABEL_106:
  v37 = v67;
  v38 = v67 + 16;
  if ( v36 > *(_DWORD *)(v67 + 12) )
  {
    v48 = (unsigned __int16 *)GlobalAlloc(0, 2LL * v36);
    v35 = v70;
    v39 = v48;
  }
  else
  {
    v39 = (unsigned __int16 *)(v67 + 16);
  }
  if ( !v39 )
  {
    if ( v75 > 12 )
      GlobalFree(String);
    v75 = 12;
    String = (wchar_t *)v77;
    CAPITempBuffer<unsigned short,1>::Destroy(&v70);
    if ( v86 > 33 )
      GlobalFree(lpName);
    lpName = (LPWSTR)v88;
    v86 = 33;
    if ( v109 > 260 )
      GlobalFree(v108);
    v109 = 260;
    v108 = v110;
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    CRegHandle::~CRegHandle((CRegHandle *)v96);
    CRegHandle::~CRegHandle((CRegHandle *)&v101);
    return 14;
  }
  if ( *(_QWORD *)v37 != v38 )
  {
    GlobalFree(*(HGLOBAL *)v37);
    v35 = v70;
  }
  *(_QWORD *)v37 = v39;
  *(_DWORD *)(v37 + 8) = v36;
  if ( (int)StringCchCopyW(v39, v36, v35) < 0 )
  {
    if ( v75 > 12 )
      GlobalFree(String);
    String = (wchar_t *)v77;
    v75 = 12;
    if ( v71 > 1 )
      GlobalFree(v70);
    v70 = v73;
    v71 = 1;
    if ( v86 > 33 )
      GlobalFree(lpName);
    lpName = (LPWSTR)v88;
    v86 = 33;
    if ( v109 <= 260 )
      goto LABEL_165;
    goto LABEL_164;
  }
  v40 = lpsz;
  v41 = lpName;
  v42 = 33;
  v43 = lpsz;
  v44 = 2147483646;
  do
  {
    if ( !v44 )
      break;
    if ( !*v41 )
      break;
    *v43++ = *v41++;
    --v44;
    --v42;
  }
  while ( v42 );
  v45 = v43 - 1;
  if ( v42 )
    v45 = v43;
  *v45 = 0;
  if ( v42 )
  {
    CharUpperBuffW(v40, 0x20u);
    if ( v75 > 12 )
      GlobalFree(String);
    String = (wchar_t *)v77;
    v75 = 12;
    if ( v71 > 1 )
      GlobalFree(v70);
    v71 = 1;
    v70 = v73;
    if ( v86 > 33 )
      GlobalFree(lpName);
    v86 = 33;
    lpName = (LPWSTR)v88;
    if ( v109 > 260 )
      GlobalFree(v108);
    v109 = 260;
    v108 = v110;
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    CRegHandle::~CRegHandle((CRegHandle *)v96);
    CRegHandle::~CRegHandle((CRegHandle *)&v101);
    return 0;
  }
  if ( v75 > 12 )
    GlobalFree(String);
  v75 = 12;
  String = (wchar_t *)v77;
  CAPITempBuffer<unsigned short,1>::Destroy(&v70);
  if ( v86 > 33 )
    GlobalFree(lpName);
  v86 = 33;
  lpName = (LPWSTR)v88;
LABEL_189:
  if ( v109 > 260 )
LABEL_164:
    GlobalFree(v108);
LABEL_165:
  v109 = 260;
  v108 = v110;
LABEL_166:
  CRegHandle::~CRegHandle((CRegHandle *)hKey);
  CRegHandle::~CRegHandle((CRegHandle *)v96);
  CRegHandle::~CRegHandle((CRegHandle *)&v101);
  return 1627;
}

```

## disassembly

```asm
0x18003c1d0  mov     [rsp-8+arg_18], rbx
0x18003c1d5  push    rbp
0x18003c1d6  push    rsi
0x18003c1d7  push    rdi
0x18003c1d8  push    r12
0x18003c1da  push    r13
0x18003c1dc  push    r14
0x18003c1de  push    r15
0x18003c1e0  lea     rbp, [rsp-0F70h]
0x18003c1e8  mov     eax, 1070h
0x18003c1ed  call    _alloca_probe
0x18003c1f2  sub     rsp, rax
0x18003c1f5  mov     rax, cs:__security_cookie
0x18003c1fc  xor     rax, rsp
0x18003c1ff  mov     [rbp+0FA0h+var_40], rax
0x18003c206  mov     rax, [rbp+0FA0h+arg_20]
0x18003c20d  mov     rsi, rcx
0x18003c210  mov     rdi, [rbp+0FA0h+arg_28]
0x18003c217  xorps   xmm0, xmm0
0x18003c21a  mov     [rbp+0FA0h+lpsz], rax
0x18003c21e  xor     ebx, ebx
0x18003c220  mov     rax, [rbp+0FA0h+arg_30]
0x18003c227  mov     r13d, r8d
0x18003c22a  mov     [rbp+0FA0h+var_1008], rax
0x18003c22e  mov     r12, rdx
0x18003c231  lea     rax, [rbp+0FA0h+var_D80]
0x18003c238  mov     [rsp+10A0h+var_1030], rcx
0x18003c23d  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18003c244  mov     [rbp+0FA0h+var_D90], rax
0x18003c24b  mov     [rsp+10A0h+var_1028], r9d
0x18003c250  mov     [rsp+10A0h+var_103C], r8d
0x18003c255  mov     [rbp+0FA0h+String1], rdx
0x18003c259  mov     [rbp+0FA0h+var_FF8], rdi
0x18003c25d  movdqa  [rbp+0FA0h+var_DA0], xmm0
0x18003c265  mov     [rbp+0FA0h+var_D88], 1
0x18003c26f  mov     [rbp+0FA0h+var_D80], bx
0x18003c276  call    cs:__imp_InitializeCriticalSection
0x18003c27d  nop     dword ptr [rax+rax+00h]
0x18003c282  xorps   xmm0, xmm0
0x18003c285  mov     [rbp+0FA0h+var_DD8], 1
0x18003c28f  lea     rax, [rbp+0FA0h+var_DD0]
0x18003c296  movdqa  xmmword ptr [rbp+0FA0h+var_DF0], xmm0
0x18003c29e  lea     rcx, [rbp+0FA0h+var_DC8]; lpCriticalSection
0x18003c2a5  mov     [rbp+0FA0h+var_DE0], rax
0x18003c2ac  mov     [rbp+0FA0h+var_DD0], bx
0x18003c2b3  call    cs:__imp_InitializeCriticalSection
0x18003c2ba  nop     dword ptr [rax+rax+00h]
0x18003c2bf  xorps   xmm0, xmm0
0x18003c2c2  mov     [rbp+0FA0h+var_D38], 1
0x18003c2cc  lea     rax, [rbp+0FA0h+var_D30]
0x18003c2d3  movdqa  xmmword ptr [rbp+0FA0h+hKey], xmm0
0x18003c2db  lea     rcx, [rbp+0FA0h+var_D28]; lpCriticalSection
0x18003c2e2  mov     [rbp+0FA0h+var_D40], rax
0x18003c2e9  mov     [rbp+0FA0h+var_D30], bx
0x18003c2f0  call    cs:__imp_InitializeCriticalSection
0x18003c2f7  nop     dword ptr [rax+rax+00h]
0x18003c2fc  mov     dword ptr [rsp+10A0h+var_1038], ebx
0x18003c300  mov     r14b, 1
0x18003c303  mov     [rsp+10A0h+var_1040], r14b
0x18003c308  lea     r15, aProducts; "Products"
0x18003c30f  cmp     r13d, 1
0x18003c313  jz      loc_18003E0D9
0x18003c319  cmp     r13d, 3
0x18003c31d  jz      loc_18003D76F
0x18003c323  lea     rax, [rbp+0FA0h+var_DA0]
0x18003c32a  mov     byte ptr [rsp+10A0h+lpClass], bl
0x18003c32e  mov     r9, rsi
0x18003c331  mov     [rsp+10A0h+lpReserved], rax
0x18003c336  mov     r8, r15
0x18003c339  mov     rdx, r12
0x18003c33c  mov     ecx, r13d
0x18003c33f  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18003c344  mov     ebx, eax
0x18003c346  test    ebx, ebx
0x18003c348  jnz     loc_18003E15A
0x18003c34e  lea     rcx, [rbp+0FA0h+var_DF0]
0x18003c355  call    ??ICRegHandleStatic@@QEAAPEAPEAUHKEY__@@XZ; CRegHandleStatic::operator&(void)
0x18003c35a  cmp     cs:?g_fWoW@@3_NA, bl; bool g_fWoW
0x18003c360  mov     r9d, 20019h
0x18003c366  jz      loc_18003D9FE
0x18003c36c  mov     rcx, qword ptr [rbp+0FA0h+var_DA0]
0x18003c373  lea     rdx, ValueName; "Patches"
0x18003c37a  mov     [rsp+10A0h+lpReserved], rax
0x18003c37f  xor     r8d, r8d
0x18003c382  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003c389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c38e  mov     ebx, eax
0x18003c390  test    eax, eax
0x18003c392  jnz     loc_18003D97F
0x18003c398  lea     rax, [rbp+0FA0h+var_CF0]
0x18003c39f  mov     [rbp+0FA0h+var_CF8], 104h
0x18003c3a9  mov     [rbp+0FA0h+var_D00], rax
0x18003c3b0  lea     r8, aSSS; "%s\\%s\\%s"
0x18003c3b7  lea     rax, ValueName; "Patches"
0x18003c3be  mov     r9, r15
0x18003c3c1  mov     [rsp+10A0h+lpClass], rax
0x18003c3c6  lea     rcx, [rbp+0FA0h+var_CF0]; unsigned __int16 *
0x18003c3cd  mov     edx, 104h; unsigned __int64
0x18003c3d2  mov     [rsp+10A0h+lpReserved], rsi
0x18003c3d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c3dc  test    eax, eax
0x18003c3de  js      loc_18003DA50
0x18003c3e4  mov     eax, cs:?g_samRead@@3KA; ulong g_samRead
0x18003c3ea  lea     r9, [rbp+0FA0h+hKey]
0x18003c3f1  mov     r8, [rbp+0FA0h+var_D00]
0x18003c3f8  xor     ebx, ebx
0x18003c3fa  mov     [rsp+10A0h+lpftLastWriteTime], rbx
0x18003c3ff  mov     rdx, rsi
0x18003c402  mov     dword ptr [rsp+10A0h+lpcchClass], r13d
0x18003c407  mov     rcx, r12
0x18003c40a  mov     dword ptr [rsp+10A0h+lpClass], eax
0x18003c40e  mov     byte ptr [rsp+10A0h+lpReserved], bl; int
0x18003c412  call    ?OpenInstalledUserDataSubKeyPacked@@YAKPEBG00AEAVCRegHandle@@_NKW4iaaAppAssignment@@PEAW42@@Z; OpenInstalledUserDataSubKeyPacked(ushort const *,ushort const *,ushort const *,CRegHandle &,bool,ulong,iaaAppAssignment,iaaAppAssignment *)
0x18003c417  mov     ecx, eax
0x18003c419  mov     [rbp+0FA0h+var_1010], eax
0x18003c41c  cmp     [rbp+0FA0h+arg_38], bl
0x18003c422  jnz     loc_18003CF99
0x18003c428  mov     ebx, [rbp+0FA0h+arg_40]
0x18003c42e  mov     eax, ebx
0x18003c430  and     eax, 1
0x18003c433  test    ecx, ecx
0x18003c435  jnz     loc_18003E22E
0x18003c43b  xor     edi, edi
0x18003c43d  mov     [rbp+0FA0h+var_FE8], 1
0x18003c444  lea     rcx, [rbp+0FA0h+var_EE0]
0x18003c44b  mov     esi, 21h ; '!'
0x18003c450  mov     r15d, edi
0x18003c453  mov     [rbp+0FA0h+lpName], rcx
0x18003c45a  lea     rcx, [rbp+0FA0h+var_FE0]
0x18003c45e  mov     dword ptr [rsp+10A0h+var_1038], edi
0x18003c462  mov     r14d, edi
0x18003c465  mov     [rbp+0FA0h+var_FF0], rcx
0x18003c469  mov     [rbp+0FA0h+Type], edi
0x18003c46c  mov     [rbp+0FA0h+var_EE8], esi
0x18003c472  cmp     [rsp+10A0h+var_1040], dil
0x18003c477  jz      short loc_18003C480
0x18003c479  mov     r12d, edi
0x18003c47c  test    eax, eax
0x18003c47e  jnz     short loc_18003C486
0x18003c480  mov     r12d, 1
0x18003c486  mov     r13d, 103h
0x18003c48c  nop     dword ptr [rax+00h]
0x18003c490  test    r14d, r14d
0x18003c493  jnz     loc_18003DFB4
0x18003c499  mov     edx, r15d; dwIndex
0x18003c49c  test    r12d, r12d
0x18003c49f  jz      loc_18003D5A9
0x18003c4a5  mov     eax, [rbp+0FA0h+var_EE8]
0x18003c4ab  lea     r9, [rbp+0FA0h+cchName]; lpcchName
0x18003c4af  mov     r8, [rbp+0FA0h+lpName]; lpName
0x18003c4b6  mov     rcx, [rbp+0FA0h+hKey]; hKey
0x18003c4bd  mov     [rsp+10A0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18003c4c2  mov     [rsp+10A0h+lpcchClass], rdi; lpcchClass
0x18003c4c7  mov     [rsp+10A0h+lpClass], rdi; lpClass
0x18003c4cc  mov     [rsp+10A0h+lpReserved], rdi; lpReserved
0x18003c4d1  mov     [rbp+0FA0h+cchName], eax
0x18003c4d4  call    cs:__imp_RegEnumKeyExW
0x18003c4db  nop     dword ptr [rax+rax+00h]
0x18003c4e0  mov     r14d, eax
0x18003c4e3  mov     rax, [rbp+0FA0h+var_FF0]
0x18003c4e7  mov     [rax], di
0x18003c4ea  cmp     r14d, 2
0x18003c4ee  jz      loc_18003D9C6
0x18003c4f4  cmp     r14d, r13d
0x18003c4f7  jz      loc_18003D9C9
0x18003c4fd  test    r14d, r14d
0x18003c500  jnz     loc_18003E23B
0x18003c506  mov     rax, [rbp+0FA0h+lpName]
0x18003c50d  inc     r15d
0x18003c510  test    rax, rax
0x18003c513  jz      loc_18003C490
0x18003c519  mov     rcx, rsi
0x18003c51c  nop     dword ptr [rax+00h]
0x18003c520  cmp     word ptr [rax], 0
0x18003c524  jz      short loc_18003C530
0x18003c526  add     rax, 2
0x18003c52a  sub     rcx, 1
0x18003c52e  jnz     short loc_18003C520
0x18003c530  mov     rdx, rsi
0x18003c533  sub     rdx, rcx
0x18003c536  test    rcx, rcx
0x18003c539  cmovz   rdx, rdi
0x18003c53d  jz      loc_18003C490
0x18003c543  cmp     rdx, 20h ; ' '
0x18003c547  jnz     loc_18003C490
0x18003c54d  cmp     [rsp+10A0h+var_103C], 3
0x18003c552  lea     rax, [rbp+0FA0h+var_FC8]
0x18003c556  mov     [rbp+0FA0h+String], rax
0x18003c55a  mov     [rbp+0FA0h+var_FD0], 0Ch
0x18003c561  mov     [rbp+0FA0h+var_FCC], 0Ch
0x18003c568  jz      loc_18003E246
0x18003c56e  cmp     [rsp+10A0h+var_1030], 0
0x18003c574  jz      loc_18003CC8A
0x18003c57a  mov     rdi, [rbp+0FA0h+lpName]
0x18003c581  lea     rax, [rbp+0FA0h+var_F30]
0x18003c585  mov     [rbp+0FA0h+var_F40], rax
0x18003c589  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x18003c58d  xor     eax, eax
0x18003c58f  mov     [rbp+0FA0h+var_F38], 1
0x18003c596  xorps   xmm0, xmm0
0x18003c599  mov     [rbp+0FA0h+var_F30], ax
0x18003c59d  movdqa  xmmword ptr [rbp+0FA0h+var_F50], xmm0
0x18003c5a2  call    cs:__imp_InitializeCriticalSection
0x18003c5a9  nop     dword ptr [rax+rax+00h]
0x18003c5ae  lea     rax, [rbp+0FA0h+var_F90]
0x18003c5b2  mov     [rbp+0FA0h+var_F98], 1
0x18003c5b9  mov     [rbp+0FA0h+var_FA0], rax
0x18003c5bd  lea     rcx, [rbp+0FA0h+var_F88]; lpCriticalSection
0x18003c5c1  xor     eax, eax
0x18003c5c3  xorps   xmm0, xmm0
0x18003c5c6  mov     [rbp+0FA0h+var_F90], ax
0x18003c5ca  movdqa  xmmword ptr [rbp+0FA0h+var_FB0], xmm0
0x18003c5cf  call    cs:__imp_InitializeCriticalSection
0x18003c5d6  nop     dword ptr [rax+rax+00h]
0x18003c5db  mov     edx, [rsp+10A0h+var_103C]
0x18003c5df  lea     rax, [rbp+0FA0h+var_AD0]
0x18003c5e6  mov     [rbp+0FA0h+var_AE0], rax
0x18003c5ed  lea     rax, [rbp+0FA0h+var_840]
0x18003c5f4  mov     [rbp+0FA0h+hMem], rax
0x18003c5fb  mov     [rbp+0FA0h+var_AD8], 13Eh
0x18003c605  mov     [rbp+0FA0h+var_848], 40h ; '@'
0x18003c60f  cmp     edx, 2
0x18003c612  jnz     loc_18003D601
0x18003c618  lea     rcx, aS1518_0; "S-1-5-18"
0x18003c61f  mov     [rsp+10A0h+lpReserved], rcx
0x18003c624  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003c62b  lea     rcx, [rbp+0FA0h+var_AD0]; unsigned __int16 *
0x18003c632  mov     edx, 13Eh; unsigned __int64
0x18003c637  lea     r8, aSS_0; "%s\\%s"
0x18003c63e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c643  cmp     [rbp+0FA0h+var_848], 40h ; '@'
0x18003c64a  mov     ebx, eax
0x18003c64c  jle     short loc_18003C661
0x18003c64e  mov     rcx, [rbp+0FA0h+hMem]; hMem
0x18003c655  call    cs:__imp_GlobalFree
0x18003c65c  nop     dword ptr [rax+rax+00h]
0x18003c661  test    ebx, ebx
0x18003c663  jnz     loc_18003C753
0x18003c669  mov     r9, [rbp+0FA0h+var_AE0]
0x18003c670  lea     rax, [rbp+0FA0h+var_840]
0x18003c677  mov     [rbp+0FA0h+hMem], rax
0x18003c67e  lea     r8, aSSS; "%s\\%s\\%s"
0x18003c685  mov     rax, [rsp+10A0h+var_1030]
0x18003c68a  lea     rcx, [rbp+0FA0h+var_840]; unsigned __int16 *
0x18003c691  mov     [rsp+10A0h+lpClass], rax
0x18003c696  mov     edx, 400h; unsigned __int64
0x18003c69b  lea     rax, aProducts; "Products"
0x18003c6a2  mov     [rbp+0FA0h+var_848], 400h
0x18003c6ac  mov     [rsp+10A0h+lpReserved], rax
0x18003c6b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c6b6  test    eax, eax
0x18003c6b8  js      loc_18003CD54
0x18003c6be  mov     rbx, [rbp+0FA0h+hMem]
0x18003c6c5  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x18003c6c9  call    cs:__imp_EnterCriticalSection
0x18003c6d0  nop     dword ptr [rax+rax+00h]
0x18003c6d5  mov     rcx, [rbp+0FA0h+var_F50]; hKey
0x18003c6d9  test    rcx, rcx
0x18003c6dc  jz      short loc_18003C6FB
0x18003c6de  call    cs:__imp_RegCloseKey
0x18003c6e5  nop     dword ptr [rax+rax+00h]
0x18003c6ea  mov     rax, [rbp+0FA0h+var_F40]
0x18003c6ee  xor     ecx, ecx
0x18003c6f0  mov     [rbp+0FA0h+var_F50], 0
0x18003c6f8  mov     [rax], cx
0x18003c6fb  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x18003c6ff  call    cs:__imp_LeaveCriticalSection
0x18003c706  nop     dword ptr [rax+rax+00h]
0x18003c70b  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18003c712  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003c719  jz      loc_18003D738
0x18003c71f  lea     rax, [rbp+0FA0h+var_F50]
0x18003c723  xor     r8d, r8d
0x18003c726  mov     [rsp+10A0h+lpReserved], rax
0x18003c72b  mov     rdx, rbx
0x18003c72e  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003c735  mov     rcx, 0FFFFFFFF80000002h
0x18003c73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c741  cmp     [rbp+0FA0h+var_848], 400h
0x18003c74b  mov     ebx, eax
0x18003c74d  jg      loc_18003E26B
0x18003c753  cmp     [rbp+0FA0h+var_AD8], 13Eh
0x18003c75d  jg      loc_18003E283
0x18003c763  test    ebx, ebx
0x18003c765  jz      loc_18003CCB4
0x18003c76b  cmp     [rsp+10A0h+var_103C], 1
0x18003c770  mov     rbx, [rbp+0FA0h+String1]
0x18003c774  jz      loc_18003E29B
0x18003c77a  lea     rax, [rbp+0FA0h+var_E70]
0x18003c781  mov     [rbp+0FA0h+var_E78], 1
0x18003c78b  mov     [rbp+0FA0h+var_E80], rax
0x18003c792  lea     rcx, [rbp+0FA0h+var_E68]; lpCriticalSection
0x18003c799  xor     eax, eax
0x18003c79b  xorps   xmm0, xmm0
0x18003c79e  mov     [rbp+0FA0h+var_E70], ax
0x18003c7a5  movdqa  xmmword ptr [rbp+0FA0h+var_E90], xmm0
0x18003c7ad  call    cs:__imp_InitializeCriticalSection
0x18003c7b4  nop     dword ptr [rax+rax+00h]
0x18003c7b9  mov     r9, [rsp+10A0h+var_1030]
0x18003c7be  lea     rax, [rbp+0FA0h+var_E90]
  ... truncated ...
```
