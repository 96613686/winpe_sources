# EnumPatchesForSpecificInstance(ushort const *,ushort const *,iaaAppAssignment,ulong,ushort *,tagMSIPATCHSTATE *,CAPITempBufferRef<ushort> &,bool,ulong)

- ea: `0x180015ac0`
- end: `0x180017a7b`
- name: `?EnumPatchesForSpecificInstance@@YAKPEBG0W4iaaAppAssignment@@KPEAGPEAW4tagMSIPATCHSTATE@@AEAV?$CAPITempBufferRef@G@@_NK@Z`
- size: `8123`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004a860`
- `0x18004d5c4`

## callees

- `0x180013264`
- `0x180015690`
- `0x180015950`
- `0x180015ac0`
- `0x180017a84`
- `0x180017b28`
- `0x180018210`
- `0x180018d10`
- `0x180019b60`
- `0x180019bb4`
- `0x180020940`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x180025560`
- `0x180025a18`
- `0x18004ceb0`
- `0x180050cf0`
- `0x180072450`
- `0x18025ab80`
- `0x18025ac10`
- `0x18025c010`

## import_xrefs

- `msvcrt!wcstol` at `0x180016309`
- `msvcrt!wcstol` at `0x180016c40`
- `msvcrt!wcstol` at `0x180016309`
- `msvcrt!wcstol` at `0x180016c40`
- `ADVAPI32!RegEnumKeyExW` at `0x180015df4`
- `ADVAPI32!RegEnumKeyExW` at `0x180015df4`
- `ADVAPI32!RegCloseKey` at `0x180015c4b`
- `ADVAPI32!RegCloseKey` at `0x180015fd8`
- `ADVAPI32!RegCloseKey` at `0x1800160eb`
- `ADVAPI32!RegCloseKey` at `0x180016163`
- `ADVAPI32!RegCloseKey` at `0x1800161c0`
- `ADVAPI32!RegCloseKey` at `0x1800162a8`
- `ADVAPI32!RegCloseKey` at `0x1800163b2`
- `ADVAPI32!RegCloseKey` at `0x18001640e`
- `ADVAPI32!RegCloseKey` at `0x180016465`
- `ADVAPI32!RegCloseKey` at `0x1800164d1`
- `ADVAPI32!RegCloseKey` at `0x180015c4b`
- `ADVAPI32!RegCloseKey` at `0x180015fd8`
- `ADVAPI32!RegCloseKey` at `0x1800160eb`
- `ADVAPI32!RegCloseKey` at `0x180016163`
- `ADVAPI32!RegCloseKey` at `0x1800161c0`
- `ADVAPI32!RegCloseKey` at `0x1800162a8`
- `ADVAPI32!RegCloseKey` at `0x1800163b2`
- `ADVAPI32!RegCloseKey` at `0x18001640e`
- `ADVAPI32!RegCloseKey` at `0x180016465`
- `ADVAPI32!RegCloseKey` at `0x1800164d1`
- `KERNEL32!InitializeCriticalSection` at `0x180015b68`
- `KERNEL32!InitializeCriticalSection` at `0x180015ba0`
- `KERNEL32!InitializeCriticalSection` at `0x180015bd8`
- `KERNEL32!InitializeCriticalSection` at `0x180015eb4`
- `KERNEL32!InitializeCriticalSection` at `0x180015edb`
- `KERNEL32!InitializeCriticalSection` at `0x18001609b`
- `KERNEL32!InitializeCriticalSection` at `0x180016250`
- `KERNEL32!InitializeCriticalSection` at `0x1800168cb`
- `KERNEL32!InitializeCriticalSection` at `0x180016902`
- `KERNEL32!InitializeCriticalSection` at `0x18001797f`
- `KERNEL32!InitializeCriticalSection` at `0x1800179b8`
- `KERNEL32!InitializeCriticalSection` at `0x180015b68`
- `KERNEL32!InitializeCriticalSection` at `0x180015ba0`
- `KERNEL32!InitializeCriticalSection` at `0x180015bd8`
- `KERNEL32!InitializeCriticalSection` at `0x180015eb4`
- `KERNEL32!InitializeCriticalSection` at `0x180015edb`
- `KERNEL32!InitializeCriticalSection` at `0x18001609b`
- `KERNEL32!InitializeCriticalSection` at `0x180016250`
- `KERNEL32!InitializeCriticalSection` at `0x1800168cb`
- `KERNEL32!InitializeCriticalSection` at `0x180016902`
- `KERNEL32!InitializeCriticalSection` at `0x18001797f`
- `KERNEL32!InitializeCriticalSection` at `0x1800179b8`
- `KERNEL32!DeleteCriticalSection` at `0x18001611c`
- `KERNEL32!DeleteCriticalSection` at `0x180016188`
- `KERNEL32!DeleteCriticalSection` at `0x1800161e5`
- `KERNEL32!DeleteCriticalSection` at `0x1800162d9`
- `KERNEL32!DeleteCriticalSection` at `0x1800163df`
- `KERNEL32!DeleteCriticalSection` at `0x18001642d`
- `KERNEL32!DeleteCriticalSection` at `0x180016484`
- `KERNEL32!DeleteCriticalSection` at `0x18001611c`
- `KERNEL32!DeleteCriticalSection` at `0x180016188`
- `KERNEL32!DeleteCriticalSection` at `0x1800161e5`
- `KERNEL32!DeleteCriticalSection` at `0x1800162d9`
- `KERNEL32!DeleteCriticalSection` at `0x1800163df`
- `KERNEL32!DeleteCriticalSection` at `0x18001642d`
- `KERNEL32!DeleteCriticalSection` at `0x180016484`
- `KERNEL32!LeaveCriticalSection` at `0x180015c6a`
- `KERNEL32!LeaveCriticalSection` at `0x180015ff3`
- `KERNEL32!LeaveCriticalSection` at `0x18001610f`
- `KERNEL32!LeaveCriticalSection` at `0x18001617e`
- `KERNEL32!LeaveCriticalSection` at `0x1800161db`
- `KERNEL32!LeaveCriticalSection` at `0x1800162cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800163d2`
- `KERNEL32!LeaveCriticalSection` at `0x180016423`
- `KERNEL32!LeaveCriticalSection` at `0x18001647a`
- `KERNEL32!LeaveCriticalSection` at `0x1800164ec`
- `KERNEL32!LeaveCriticalSection` at `0x180015c6a`
- `KERNEL32!LeaveCriticalSection` at `0x180015ff3`
- `KERNEL32!LeaveCriticalSection` at `0x18001610f`
- `KERNEL32!LeaveCriticalSection` at `0x18001617e`
- `KERNEL32!LeaveCriticalSection` at `0x1800161db`
- `KERNEL32!LeaveCriticalSection` at `0x1800162cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800163d2`
- `KERNEL32!LeaveCriticalSection` at `0x180016423`
- `KERNEL32!LeaveCriticalSection` at `0x18001647a`
- `KERNEL32!LeaveCriticalSection` at `0x1800164ec`
- `KERNEL32!EnterCriticalSection` at `0x180015c39`
- `KERNEL32!EnterCriticalSection` at `0x180015fc9`
- `KERNEL32!EnterCriticalSection` at `0x1800160d9`
- `KERNEL32!EnterCriticalSection` at `0x180016154`
- `KERNEL32!EnterCriticalSection` at `0x1800161b1`
- `KERNEL32!EnterCriticalSection` at `0x180016296`
- `KERNEL32!EnterCriticalSection` at `0x18001639c`
- `KERNEL32!EnterCriticalSection` at `0x1800163ff`
- `KERNEL32!EnterCriticalSection` at `0x180016456`
- `KERNEL32!EnterCriticalSection` at `0x1800164c2`
- `KERNEL32!EnterCriticalSection` at `0x180015c39`
- `KERNEL32!EnterCriticalSection` at `0x180015fc9`
- `KERNEL32!EnterCriticalSection` at `0x1800160d9`
- `KERNEL32!EnterCriticalSection` at `0x180016154`
- `KERNEL32!EnterCriticalSection` at `0x1800161b1`
- `KERNEL32!EnterCriticalSection` at `0x180016296`
- `KERNEL32!EnterCriticalSection` at `0x18001639c`
- `KERNEL32!EnterCriticalSection` at `0x1800163ff`
- `KERNEL32!EnterCriticalSection` at `0x180016456`
- `KERNEL32!EnterCriticalSection` at `0x1800164c2`
- `KERNEL32!GlobalAlloc` at `0x180016d7e`
- `KERNEL32!GlobalAlloc` at `0x180016d7e`
- `KERNEL32!GlobalFree` at `0x180015f5b`
- `KERNEL32!GlobalFree` at `0x180016132`
- `KERNEL32!GlobalFree` at `0x180016198`
- `KERNEL32!GlobalFree` at `0x1800161f5`
- `KERNEL32!GlobalFree` at `0x1800162ef`
- `KERNEL32!GlobalFree` at `0x1800163f5`
- `KERNEL32!GlobalFree` at `0x18001643d`
- `KERNEL32!GlobalFree` at `0x1800164b3`
- `KERNEL32!GlobalFree` at `0x18001658b`
- `KERNEL32!GlobalFree` at `0x1800165a4`
- `KERNEL32!GlobalFree` at `0x1800166be`
- `KERNEL32!GlobalFree` at `0x180016708`
- `KERNEL32!GlobalFree` at `0x1800169be`
- `KERNEL32!GlobalFree` at `0x180016b17`
- `KERNEL32!GlobalFree` at `0x180016b3f`
- `KERNEL32!GlobalFree` at `0x180016c59`
- `KERNEL32!GlobalFree` at `0x180016d09`
- `KERNEL32!GlobalFree` at `0x180016d33`
- `KERNEL32!GlobalFree` at `0x180016e3e`
- `KERNEL32!GlobalFree` at `0x180016e6f`
- `KERNEL32!GlobalFree` at `0x180016edd`
- `KERNEL32!GlobalFree` at `0x180016f21`
- `KERNEL32!GlobalFree` at `0x180016f72`
- `KERNEL32!GlobalFree` at `0x180016fc2`
- `KERNEL32!GlobalFree` at `0x180017049`
- `KERNEL32!GlobalFree` at `0x18001707a`
- `KERNEL32!GlobalFree` at `0x1800170cd`
- `KERNEL32!GlobalFree` at `0x180017183`
- `KERNEL32!GlobalFree` at `0x18001721b`
- `KERNEL32!GlobalFree` at `0x180017238`
- `KERNEL32!GlobalFree` at `0x18001728b`
- `KERNEL32!GlobalFree` at `0x1800172bd`
- `KERNEL32!GlobalFree` at `0x180017336`
- `KERNEL32!GlobalFree` at `0x1800173b9`
- `KERNEL32!GlobalFree` at `0x180017508`
- `KERNEL32!GlobalFree` at `0x180017531`
- `KERNEL32!GlobalFree` at `0x18001758d`
- `KERNEL32!GlobalFree` at `0x1800175bf`
- `KERNEL32!GlobalFree` at `0x1800175d4`
- `KERNEL32!GlobalFree` at `0x180017602`
- `KERNEL32!GlobalFree` at `0x180017636`
- `KERNEL32!GlobalFree` at `0x18001769b`
- `KERNEL32!GlobalFree` at `0x1800176b4`
- `KERNEL32!GlobalFree` at `0x18001778b`
- `KERNEL32!GlobalFree` at `0x180017806`
- `KERNEL32!GlobalFree` at `0x180017886`
- `KERNEL32!GlobalFree` at `0x180017898`
- `KERNEL32!GlobalFree` at `0x180017905`
- `KERNEL32!GlobalFree` at `0x180017917`
- `KERNEL32!GlobalFree` at `0x180017929`
- `KERNEL32!GlobalFree` at `0x180017a22`
- `KERNEL32!GlobalFree` at `0x180017a34`
- `KERNEL32!GlobalFree` at `0x180017a62`
- `KERNEL32!GlobalFree` at `0x180017a70`
- `KERNEL32!GlobalFree` at `0x180015f5b`
- `KERNEL32!GlobalFree` at `0x180016132`
- `KERNEL32!GlobalFree` at `0x180016198`
- `KERNEL32!GlobalFree` at `0x1800161f5`
- `KERNEL32!GlobalFree` at `0x1800162ef`
- `KERNEL32!GlobalFree` at `0x1800163f5`
- `KERNEL32!GlobalFree` at `0x18001643d`
- `KERNEL32!GlobalFree` at `0x1800164b3`
- `KERNEL32!GlobalFree` at `0x18001658b`
- `KERNEL32!GlobalFree` at `0x1800165a4`
- `KERNEL32!GlobalFree` at `0x1800166be`
- `KERNEL32!GlobalFree` at `0x180016708`
- `KERNEL32!GlobalFree` at `0x1800169be`
- `KERNEL32!GlobalFree` at `0x180016b17`
- `KERNEL32!GlobalFree` at `0x180016b3f`
- `KERNEL32!GlobalFree` at `0x180016c59`
- `KERNEL32!GlobalFree` at `0x180016d09`
- `KERNEL32!GlobalFree` at `0x180016d33`
- `KERNEL32!GlobalFree` at `0x180016e3e`
- `KERNEL32!GlobalFree` at `0x180016e6f`
- `KERNEL32!GlobalFree` at `0x180016edd`
- `KERNEL32!GlobalFree` at `0x180016f21`
- `KERNEL32!GlobalFree` at `0x180016f72`
- `KERNEL32!GlobalFree` at `0x180016fc2`
- `KERNEL32!GlobalFree` at `0x180017049`
- `KERNEL32!GlobalFree` at `0x18001707a`
- `KERNEL32!GlobalFree` at `0x1800170cd`
- `KERNEL32!GlobalFree` at `0x180017183`
- `KERNEL32!GlobalFree` at `0x18001721b`
- `KERNEL32!GlobalFree` at `0x180017238`
- `KERNEL32!GlobalFree` at `0x18001728b`
- `KERNEL32!GlobalFree` at `0x1800172bd`
- `KERNEL32!GlobalFree` at `0x180017336`
- `KERNEL32!GlobalFree` at `0x1800173b9`
- `KERNEL32!GlobalFree` at `0x180017508`
- `KERNEL32!GlobalFree` at `0x180017531`
- `KERNEL32!GlobalFree` at `0x18001758d`
- `KERNEL32!GlobalFree` at `0x1800175bf`
- `KERNEL32!GlobalFree` at `0x1800175d4`
- `KERNEL32!GlobalFree` at `0x180017602`
- `KERNEL32!GlobalFree` at `0x180017636`
- `KERNEL32!GlobalFree` at `0x18001769b`

## string_xrefs

- `0x180015f2a`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180016513`: `InstallProperties`

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
  __int64 v15; // r9
  int v16; // ecx
  int v17; // ebx
  DWORD v18; // r15d
  unsigned int v19; // r14d
  int v20; // r12d
  LPWSTR v21; // rax
  __int64 v22; // rcx
  LPWSTR v23; // rdi
  const unsigned __int16 *v24; // rcx
  int CurrentUserStringSID; // ebx
  HGLOBAL v26; // rbx
  __int64 v27; // r9
  wchar_t *v28; // rbx
  int AppliedPatchInfoInternal; // ebx
  int v30; // eax
  int v31; // ebx
  const WCHAR *v32; // rdi
  __int64 v33; // r9
  _WORD *v34; // r8
  int v35; // ebx
  __int64 v36; // r15
  __int64 v37; // r14
  unsigned __int16 *v38; // rdi
  WCHAR *v39; // r10
  LPWSTR v40; // rcx
  __int64 v41; // rdx
  LPWSTR v42; // r8
  __int64 v43; // rax
  LPWSTR v44; // rcx
  const WCHAR *v46; // rdx
  unsigned __int16 *v47; // rax
  int v48; // edx
  unsigned int v49; // r13d
  int Value; // esi
  const WCHAR *v51; // rsi
  HKEY *v52; // rax
  unsigned int v53; // r8d
  int lpReserved; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  char v57; // [rsp+60h] [rbp-A0h]
  unsigned int v58; // [rsp+64h] [rbp-9Ch]
  __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+78h] [rbp-88h]
  wchar_t *String1; // [rsp+80h] [rbp-80h]
  DWORD Type; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-74h] BYREF
  int v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  LPWSTR lpsz; // [rsp+A0h] [rbp-60h]
  int *v68; // [rsp+A8h] [rbp-58h]
  HGLOBAL v69; // [rsp+B0h] [rbp-50h] BYREF
  int v70; // [rsp+B8h] [rbp-48h]
  int v71; // [rsp+BCh] [rbp-44h]
  _WORD v72[4]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *String; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+D0h] [rbp-30h]
  int v75; // [rsp+D4h] [rbp-2Ch]
  _BYTE v76[24]; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION v77; // [rsp+F0h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION v78; // [rsp+118h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION v79; // [rsp+150h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION v80; // [rsp+178h] [rbp+78h] BYREF
  LPWSTR lpName; // [rsp+1B0h] [rbp+B0h]
  signed int v82; // [rsp+1B8h] [rbp+B8h]
  int v83; // [rsp+1BCh] [rbp+BCh]
  _BYTE v84[80]; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _RTL_CRITICAL_SECTION v85; // [rsp+210h] [rbp+110h] BYREF
  struct _RTL_CRITICAL_SECTION v86; // [rsp+238h] [rbp+138h] BYREF
  struct _RTL_CRITICAL_SECTION v87; // [rsp+260h] [rbp+160h] BYREF
  struct _RTL_CRITICAL_SECTION v88; // [rsp+288h] [rbp+188h] BYREF
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct _RTL_CRITICAL_SECTION v90; // [rsp+2D8h] [rbp+1D8h] BYREF
  struct _RTL_CRITICAL_SECTION v91; // [rsp+300h] [rbp+200h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+328h] [rbp+228h] BYREF
  struct _RTL_CRITICAL_SECTION v93; // [rsp+350h] [rbp+250h] BYREF
  struct _RTL_CRITICAL_SECTION v94; // [rsp+378h] [rbp+278h] BYREF
  HGLOBAL v95; // [rsp+3A0h] [rbp+2A0h]
  int v96; // [rsp+3A8h] [rbp+2A8h]
  unsigned __int16 v97[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  HGLOBAL v98; // [rsp+5C0h] [rbp+4C0h] BYREF
  int v99; // [rsp+5C8h] [rbp+4C8h]
  int v100; // [rsp+5CCh] [rbp+4CCh]
  unsigned __int16 v101[320]; // [rsp+5D0h] [rbp+4D0h] BYREF
  HGLOBAL hMem; // [rsp+850h] [rbp+750h] BYREF
  int v103; // [rsp+858h] [rbp+758h]
  int v104; // [rsp+85Ch] [rbp+75Ch]
  unsigned __int16 v105[1024]; // [rsp+860h] [rbp+760h] BYREF

  lpsz = a5;
  v10 = a3;
  v66 = a7;
  v60 = a1;
  v91.OwningThread = &v91.SpinCount;
  v61 = a4;
  v58 = a3;
  String1 = a2;
  v68 = a6;
  *(_OWORD *)&v91.DebugInfo = 0;
  LODWORD(v91.LockSemaphore) = 1;
  LOWORD(v91.SpinCount) = 0;
  InitializeCriticalSection(&CriticalSection);
  LODWORD(hKey.LockSemaphore) = 1;
  *(_OWORD *)&hKey.DebugInfo = 0;
  hKey.OwningThread = &hKey.SpinCount;
  LOWORD(hKey.SpinCount) = 0;
  InitializeCriticalSection(&v90);
  LODWORD(v93.LockSemaphore) = 1;
  *(_OWORD *)&v93.DebugInfo = 0;
  v93.OwningThread = &v93.SpinCount;
  LOWORD(v93.SpinCount) = 0;
  InitializeCriticalSection(&v94);
  LODWORD(v59) = 0;
  v12 = 1;
  v57 = 1;
  if ( v10 != 1 )
  {
    if ( v10 == 3 )
    {
      v13 = OpenAdvertisedProductKeyPacked(a1, (__int64)&v91, 0, -1, (int *)&v59);
      v10 = v59;
      v58 = v59;
      goto LABEL_4;
    }
LABEL_3:
    v13 = OpenSpecificUsersAdvertisedSubKeyPacked(v10, a2, (WCHAR *)L"Products", a1, &v91, 0);
LABEL_4:
    v14 = v13;
    goto LABEL_5;
  }
  if ( !a2 || !*a2 || IsCurrentUser(a2) )
    goto LABEL_3;
  v99 = 261;
  v98 = v101;
  if ( (int)StringCchPrintfW(v101, 0x105u, L"%s\\%s", L"Products", a1) < 0 )
  {
    if ( v99 > 261 )
      GlobalFree(v98);
    v99 = 261;
    v98 = v101;
    goto LABEL_168;
  }
  v12 = 0;
  LOBYTE(lpReservedb) = 0;
  v57 = 0;
  v10 = 1;
  v58 = 1;
  v14 = OpenInstalledUserDataSubKeyPacked(a2, 0, v98, &v91, lpReservedb, g_samRead, 1, 0);
  if ( v99 > 261 )
    GlobalFree(v98);
LABEL_5:
  if ( v14 )
  {
    CRegHandle::~CRegHandle(&v93);
    CRegHandle::~CRegHandle(&hKey);
    CRegHandle::~CRegHandle(&v91);
    if ( v14 == 2 )
      return 1605;
    return v14;
  }
  EnterCriticalSection(&v90);
  if ( hKey.DebugInfo )
  {
    RegCloseKey((HKEY)hKey.DebugInfo);
    hKey.DebugInfo = 0;
    *(_WORD *)hKey.OwningThread = 0;
  }
  LeaveCriticalSection(&v90);
  v15 = 131097;
  if ( !g_fWoW && g_fWinNT64 )
    v15 = 131353;
  v14 = ((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const WCHAR *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
          v91.DebugInfo,
          L"Patches",
          0,
          v15,
          &hKey);
  if ( v14 )
  {
    if ( v14 == 2 )
    {
      v49 = 259;
      if ( !v12 )
        v49 = 1626;
      CRegHandle::~CRegHandle(&v93);
      CRegHandle::~CRegHandle(&hKey);
      CRegHandle::~CRegHandle(&v91);
      return v49;
    }
    CRegHandle::~CRegHandle(&v93);
    CRegHandle::~CRegHandle(&hKey);
    CRegHandle::~CRegHandle(&v91);
    return v14;
  }
  v95 = v97;
  v96 = 260;
  if ( (int)StringCchPrintfW(v97, 0x104u, L"%s\\%s\\%s", L"Products", a1, L"Patches") < 0 )
    goto LABEL_191;
  LOBYTE(lpReserved) = 0;
  v16 = OpenInstalledUserDataSubKeyPacked(a2, a1, v95, &v93, lpReserved, g_samRead, v10, 0);
  v65 = v16;
  if ( a8 )
  {
    if ( a6 )
      *a6 = 1;
    hMem = v105;
    v46 = L"AllPatches";
    v103 = 118;
    LODWORD(v59) = 0;
    if ( v12 )
      v46 = L"Patches";
    v104 = 118;
    if ( (unsigned int)MsiRegQueryValueExW((HKEY)hKey.DebugInfo, v46, (__int64)&hMem, (__int64)&v59) != 2 )
    {
      if ( v103 > 118 )
        GlobalFree(hMem);
      hMem = v105;
      v103 = 118;
      if ( v96 > 260 )
        GlobalFree(v95);
      v96 = 260;
      v95 = v97;
      CRegHandle::~CRegHandle(&v93);
      CRegHandle::~CRegHandle(&hKey);
      CRegHandle::~CRegHandle(&v91);
      return 1610;
    }
    if ( !v12 )
    {
      if ( v103 > 118 )
        GlobalFree(hMem);
      hMem = v105;
      v103 = 118;
      if ( v96 > 260 )
        GlobalFree(v95);
      v96 = 260;
      v95 = v97;
      CRegHandle::~CRegHandle(&v93);
      CRegHandle::~CRegHandle(&hKey);
      CRegHandle::~CRegHandle(&v91);
      return 1626;
    }
    if ( v103 > 118 )
      GlobalFree(hMem);
    v103 = 118;
    hMem = v105;
LABEL_199:
    if ( v96 > 260 )
      GlobalFree(v95);
    v96 = 260;
    v95 = v97;
    CRegHandle::~CRegHandle(&v93);
    CRegHandle::~CRegHandle(&hKey);
    CRegHandle::~CRegHandle(&v91);
    return 259;
  }
  v17 = a9;
  if ( v16 && (a9 & 1) == 0 )
    goto LABEL_199;
  v70 = 1;
  v18 = 0;
  lpName = (LPWSTR)v84;
  LODWORD(v59) = 0;
  v19 = 0;
  v69 = v72;
  Type = 0;
  v82 = 33;
  if ( !v57 || (v20 = 0, (a9 & 1) == 0) )
    v20 = 1;
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
                if ( v19 )
                {
                  CAPITempBuffer<unsigned short,1>::Destroy(&v69);
                  if ( v82 > 33 )
                    GlobalFree(lpName);
                  if ( v96 > 260 )
                    GlobalFree(v95);
                  v96 = 260;
                  v95 = v97;
                  CRegHandle::~CRegHandle(&v93);
                  CRegHandle::~CRegHandle(&hKey);
                  CRegHandle::~CRegHandle(&v91);
                  return v19;
                }
                if ( v20 )
                {
                  cchName = v82;
                  v19 = RegEnumKeyExW((HKEY)v93.DebugInfo, v18, lpName, &cchName, 0, 0, 0, 0);
                  *(_WORD *)v69 = 0;
                }
                else
                {
                  v71 = 1;
                  v83 = 33;
                  v19 = MsiRegEnumValueW((HKEY)hKey.DebugInfo, v18, (int)lpReserveda, &Type, (DWORD)&v69);
                }
                if ( v19 != 2 )
                  break;
                v19 = 259;
LABEL_183:
                v17 &= ~1u;
                a9 = v17;
                if ( !v20 && !v65 && v17 )
                {
                  v19 = 0;
                  v20 = 1;
                  v18 = 0;
                }
              }
              if ( v19 == 259 )
                goto LABEL_183;
              if ( !v19 )
                break;
              v19 = 1610;
            }
            v21 = lpName;
            ++v18;
            if ( lpName )
            {
              v22 = 33;
              do
              {
                if ( !*v21 )
                  break;
                ++v21;
                --v22;
              }
              while ( v22 );
              if ( v22 && v22 == 1 )
                break;
            }
          }
          String = (wchar_t *)v76;
          v74 = 12;
          v75 = 12;
          if ( v58 != 3 )
            break;
          v19 = 1610;
        }
        if ( v60 )
          break;
LABEL_88:
        v19 = 1610;
        if ( v74 > 12 )
          GlobalFree(String);
      }
      v23 = lpName;
      v79.OwningThread = &v79.SpinCount;
      LODWORD(v79.LockSemaphore) = 1;
      LOWORD(v79.SpinCount) = 0;
      *(_OWORD *)&v79.DebugInfo = 0;
      InitializeCriticalSection(&v80);
      LODWORD(v77.LockSemaphore) = 1;
      v77.OwningThread = &v77.SpinCount;
      LOWORD(v77.SpinCount) = 0;
      *(_OWORD *)&v77.DebugInfo = 0;
      InitializeCriticalSection(&v78);
      v98 = v101;
      hMem = v105;
      v99 = 318;
      v103 = 64;
      if ( v58 == 2 )
      {
        v24 = L"S-1-5-18";
        goto LABEL_32;
      }
      v24 = 0;
      if ( v58 > 1 )
        goto LABEL_32;
      if ( String1 )
      {
        v24 = String1;
LABEL_32:
        CurrentUserStringSID = StringCchPrintfW(
                                 v101,
                                 0x13Eu,
                                 L"%s\\%s",
                                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                 v24);
        if ( v103 <= 64 )
          goto LABEL_34;
LABEL_33:
        GlobalFree(hMem);
        goto LABEL_34;
      }
      v104 = 64;
      CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
      if ( !CurrentUserStringSID )
      {
        v24 = (const unsigned __int16 *)hMem;
        goto LABEL_32;
      }
      if ( v103 > 64 )
        goto LABEL_33;
LABEL_34:
      if ( !CurrentUserStringSID )
      {
        hMem = v105;
        v103 = 1024;
        lpReserveda = (struct _RTL_CRITICAL_SECTION *)L"Products";
        if ( (int)StringCchPrintfW(v105, 0x400u, L"%s\\%s\\%s", v98) < 0 )
        {
          if ( v103 > 1024 )
            GlobalFree(hMem);
          hMem = v105;
          v103 = 1024;
          if ( v99 > 318 )
            GlobalFree(v98);
          goto LABEL_44;
        }
        v26 = hMem;
        EnterCriticalSection(&v80);
        if ( v79.DebugInfo )
        {
          RegCloseKey((HKEY)v79.DebugInfo);
          v79.DebugInfo = 0;
          *(_WORD *)v79.OwningThread = 0;
        }
        LeaveCriticalSection(&v80);
        v27 = g_samRead;
        if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
          LODWORD(v27) = g_samRead | 0x100;
        lpReserveda = &v79;
        CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, __int64))RegOpenKeyAPI)(
                                 -2147483646,
                                 v26,
                                 0,
                                 v27);
        if ( v103 > 1024 )
          GlobalFree(hMem);
      }
      if ( v99 > 318 )
        GlobalFree(v98);
      if ( !CurrentUserStringSID )
      {
        EnterCriticalSection(&v78);
        if ( v77.DebugInfo )
        {
          RegCloseKey((HKEY)v77.DebugInfo);
          v77.DebugInfo = 0;
          *(_WORD *)v77.OwningThread = 0;
        }
        LeaveCriticalSection(&v78);
        v33 = g_samRead;
        if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
          LODWORD(v33) = g_samRead | 0x100;
        lpReserveda = &v77;
        if ( !(unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const unsigned __int16 *, _QWORD, __int64))RegOpenKeyAPI)(
                              v79.DebugInfo,
                              L"InstallProperties",
                              0,
                              v33) )
        {
          CRegHandle::~CRegHandle(&v77);
          CRegHandle::~CRegHandle(&v79);
          v28 = String1;
          goto LABEL_58;
        }
      }
LABEL_44:
      v28 = String1;
      if ( v58 == 1 && String1 && *String1 && !IsCurrentUser(String1) )
        goto LABEL_79;
      LODWORD(v85.LockSemaphore) = 1;
      v85.OwningThread = &v85.SpinCount;
      LOWORD(v85.SpinCount) = 0;
      *(_OWORD *)&v85.DebugInfo = 0;
      InitializeCriticalSection(&v86);
      if ( (unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(v58, v28, (WCHAR *)L"Products", v60, &v85, 0) )
      {
        EnterCriticalSection(&v86);
        if ( v85.DebugInfo )
        {
          RegCloseKey((HKEY)v85.DebugInfo);
          v85.DebugInfo = 0;
          *(_WORD *)v85.OwningThread = 0;
        }
        LeaveCriticalSection(&v86);
        DeleteCriticalSection(&v86);
        if ( SLODWORD(v85.LockSemaphore) > 1 )
          GlobalFree(v85.OwningThread);
LABEL_79:
        EnterCriticalSection(&v78);
        if ( v77.DebugInfo )
        {
          RegCloseKey((HKEY)v77.DebugInfo);
          v77.DebugInfo = 0;
          *(_WORD *)v77.OwningThread = 0;
        }
        LeaveCriticalSection(&v78);
        DeleteCriticalSection(&v78);
        if ( SLODWORD(v77.LockSemaphore) > 1 )
          GlobalFree(v77.OwningThread);
        LODWORD(v77.LockSemaphore) = 1;
        v77.OwningThread = &v77.SpinCount;
        EnterCriticalSection(&v80);
        if ( v79.DebugInfo )
        {
          RegCloseKey((HKEY)v79.DebugInfo);
          v79.DebugInfo = 0;
          *(_WORD *)v79.OwningThread = 0;
        }
        LeaveCriticalSection(&v80);
        DeleteCriticalSection(&v80);
        if ( SLODWORD(v79.LockSemaphore) > 1 )
          GlobalFree(v79.OwningThread);
LABEL_87:
        v17 = a9;
        goto LABEL_88;
      }
      EnterCriticalSection(&v86);
      if ( v85.DebugInfo )
      {
        RegCloseKey((HKEY)v85.DebugInfo);
        v85.DebugInfo = 0;
        *(_WORD *)v85.OwningThread = 0;
      }
      LeaveCriticalSection(&v86);
      DeleteCriticalSection(&v86);
      if ( SLODWORD(v85.LockSemaphore) > 1 )
        GlobalFree(v85.OwningThread);
      LODWORD(v85.LockSemaphore) = 1;
      v85.OwningThread = &v85.SpinCount;
      EnterCriticalSection(&v78);
      if ( v77.DebugInfo )
      {
        RegCloseKey((HKEY)v77.DebugInfo);
        v77.DebugInfo = 0;
        *(_WORD *)v77.OwningThread = 0;
      }
      LeaveCriticalSection(&v78);
      DeleteCriticalSection(&v78);
      if ( SLODWORD(v77.LockSemaphore) > 1 )
        GlobalFree(v77.OwningThread);
      LODWORD(v77.LockSemaphore) = 1;
      v77.OwningThread = &v77.SpinCount;
      EnterCriticalSection(&v80);
      if ( v79.DebugInfo )
      {
        RegCloseKey((HKEY)v79.DebugInfo);
        v79.DebugInfo = 0;
        *(_WORD *)v79.OwningThread = 0;
      }
      LeaveCriticalSection(&v80);
      DeleteCriticalSection(&v80);
      if ( SLODWORD(v79.LockSemaphore) > 1 )
        GlobalFree(v79.OwningThread);
LABEL_58:
      LOBYTE(lpReserveda) = 0;
      if ( !(unsigned __int8)IsPatchAppliedToProduct(v23, v60, v28, v58) )
        goto LABEL_87;
      LODWORD(v87.LockSemaphore) = 1;
      v87.OwningThread = &v87.SpinCount;
      LOWORD(v87.SpinCount) = 0;
      *(_OWORD *)&v87.DebugInfo = 0;
      InitializeCriticalSection(&v88);
      lpReserveda = (struct _RTL_CRITICAL_SECTION *)L"State";
      AppliedPatchInfoInternal = GetAppliedPatchInfoInternal(v58, v60, v28, v23);
      EnterCriticalSection(&v88);
      if ( v87.DebugInfo )
      {
        RegCloseKey((HKEY)v87.DebugInfo);
        v87.DebugInfo = 0;
        *(_WORD *)v87.OwningThread = 0;
      }
      LeaveCriticalSection(&v88);
      DeleteCriticalSection(&v88);
      if ( SLODWORD(v87.LockSemaphore) > 1 )
        GlobalFree(v87.OwningThread);
      if ( AppliedPatchInfoInternal )
        goto LABEL_87;
      v30 = wcstol(String, 0, 10);
      v31 = v30;
      if ( !v30 )
        goto LABEL_87;
      if ( (a9 & v30) == v30 && (v20 || v30 == 1) )
        break;
      if ( v74 > 12 )
        goto LABEL_196;
LABEL_74:
      v17 = a9;
    }
    if ( v58 != 1 )
      goto LABEL_72;
    if ( !v57 )
      goto LABEL_72;
    v32 = lpName;
    if ( String1 )
    {
      if ( *String1 && !IsCurrentUser(String1) )
        goto LABEL_72;
    }
    LODWORD(v79.LockSemaphore) = 1;
    v79.OwningThread = &v79.SpinCount;
    LOWORD(v79.SpinCount) = 0;
    *(_OWORD *)&v79.DebugInfo = 0;
    InitializeCriticalSection(&v80);
    LODWORD(v87.LockSemaphore) = 1;
    v87.OwningThread = &v87.SpinCount;
    LOWORD(v87.SpinCount) = 0;
    *(_OWORD *)&v87.DebugInfo = 0;
    InitializeCriticalSection(&v88);
    if ( (unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(1, String1, (WCHAR *)L"Products", v60, &v79, 0) )
      goto LABEL_267;
    v52 = (HKEY *)CRegHandleStatic::operator&(&v87);
    if ( MsiRegOpen64bitKey((HKEY)v79.DebugInfo, L"Patches", v53, g_samRead, v52) )
      goto LABEL_267;
    v77.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v77.OwningThread;
    *(_QWORD *)&v77.LockCount = 0x2100000021LL;
    Value = MsiRegQueryValueExW((HKEY)v87.DebugInfo, v32, (__int64)&v77, 0);
    if ( v77.LockCount > 33 )
      GlobalFree(v77.DebugInfo);
    if ( Value )
    {
LABEL_267:
      CRegHandle::~CRegHandle(&v87);
      CRegHandle::~CRegHandle(&v79);
      goto LABEL_72;
    }
    v51 = v60;
    v98 = v101;
    v99 = 261;
    v100 = 261;
    if ( (unsigned int)GetAppliedPatchInfoInternal(1, v60, String1, v32, L"LocalPackage", &v98) != 1647 )
      break;
    v103 = 39;
    hMem = v105;
    v77.LockCount = 39;
    v77.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v77.OwningThread;
    if ( !(unsigned int)UnpackGUID(v32, v105, 39, 1) )
      *(_WORD *)hMem = 0;
    if ( !(unsigned int)UnpackGUID(v51, v77.DebugInfo, (unsigned int)v77.LockCount, 1) )
      v77.DebugInfo->Type = 0;
    if ( g_dmDiagnosticMode && (g_dwLogMode & 0x2000) != 0 )
      DebugString(
        5,
        0,
        0,
        L"Detected roamed patch '%s' for product '%s'. This patch will be ignored.",
        (const unsigned __int16 *)hMem,
        &v77.DebugInfo->Type,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( v77.LockCount > 39 )
      GlobalFree(v77.DebugInfo);
    v77.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v77.OwningThread;
    v77.LockCount = 39;
    if ( v103 > 39 )
      GlobalFree(hMem);
    hMem = v105;
    v103 = 39;
    if ( v99 > 261 )
      GlobalFree(v98);
    v99 = 261;
    v98 = v101;
    CRegHandle::~CRegHandle(&v87);
    CRegHandle::~CRegHandle(&v79);
    if ( v74 <= 12 )
      goto LABEL_74;
LABEL_196:
    GlobalFree(String);
    v17 = a9;
  }
  if ( v99 > 261 )
    GlobalFree(v98);
  v99 = 261;
  v98 = v101;
  CRegHandle::~CRegHandle(&v87);
  CRegHandle::~CRegHandle(&v79);
LABEL_72:
  if ( (_DWORD)v59 != v61 )
  {
    LODWORD(v59) = v59 + 1;
    if ( v74 > 12 )
      goto LABEL_196;
    goto LABEL_74;
  }
  if ( v68 )
    *v68 = v31;
  if ( v31 != 1 )
    *(_WORD *)v69 = 0;
  v34 = v69;
  if ( *(_WORD *)v69 )
  {
    v35 = v70;
    goto LABEL_108;
  }
  if ( v69 != v72 )
  {
    v48 = v70;
    if ( v70 <= 1 )
    {
      if ( v70 )
        goto LABEL_145;
    }
    else
    {
      v48 = 1;
      do
      {
LABEL_145:
        --v48;
        v72[v48] = v34[v48];
        v34 = v69;
      }
      while ( v48 );
    }
    if ( v34 != v72 )
      GlobalFree(v34);
  }
  v34 = v72;
  v35 = 1;
  v69 = v72;
  v70 = 1;
LABEL_108:
  v36 = v66;
  v37 = v66 + 16;
  if ( v35 > *(_DWORD *)(v66 + 12) )
  {
    v47 = (unsigned __int16 *)GlobalAlloc(0, 2LL * v35);
    v34 = v69;
    v38 = v47;
  }
  else
  {
    v38 = (unsigned __int16 *)(v66 + 16);
  }
  if ( !v38 )
  {
    if ( v74 > 12 )
      GlobalFree(String);
    v74 = 12;
    String = (wchar_t *)v76;
    CAPITempBuffer<unsigned short,1>::Destroy(&v69);
    if ( v82 > 33 )
      GlobalFree(lpName);
    lpName = (LPWSTR)v84;
    v82 = 33;
    if ( v96 > 260 )
      GlobalFree(v95);
    v96 = 260;
    v95 = v97;
    CRegHandle::~CRegHandle(&v93);
    CRegHandle::~CRegHandle(&hKey);
    CRegHandle::~CRegHandle(&v91);
    return 14;
  }
  if ( *(_QWORD *)v36 != v37 )
  {
    GlobalFree(*(HGLOBAL *)v36);
    v34 = v69;
  }
  *(_QWORD *)v36 = v38;
  *(_DWORD *)(v36 + 8) = v35;
  if ( (int)StringCchCopyW(v38, v35, v34) < 0 )
  {
    if ( v74 > 12 )
      GlobalFree(String);
    String = (wchar_t *)v76;
    v74 = 12;
    if ( v70 > 1 )
      GlobalFree(v69);
    v69 = v72;
    v70 = 1;
    if ( v82 > 33 )
      GlobalFree(lpName);
    lpName = (LPWSTR)v84;
    v82 = 33;
    if ( v96 <= 260 )
      goto LABEL_167;
    goto LABEL_166;
  }
  v39 = lpsz;
  v40 = lpName;
  v41 = 33;
  v42 = lpsz;
  v43 = 2147483646;
  do
  {
    if ( !v43 )
      break;
    if ( !*v40 )
      break;
    *v42++ = *v40++;
    --v43;
    --v41;
  }
  while ( v41 );
  v44 = v42 - 1;
  if ( v41 )
    v44 = v42;
  *v44 = 0;
  if ( v41 )
  {
    CharUpperBuffW(v39, 0x20u);
    if ( v74 > 12 )
      GlobalFree(String);
    String = (wchar_t *)v76;
    v74 = 12;
    if ( v70 > 1 )
      GlobalFree(v69);
    v70 = 1;
    v69 = v72;
    if ( v82 > 33 )
      GlobalFree(lpName);
    v82 = 33;
    lpName = (LPWSTR)v84;
    if ( v96 > 260 )
      GlobalFree(v95);
    v96 = 260;
    v95 = v97;
    CRegHandle::~CRegHandle(&v93);
    CRegHandle::~CRegHandle(&hKey);
    CRegHandle::~CRegHandle(&v91);
    return 0;
  }
  if ( v74 > 12 )
    GlobalFree(String);
  v74 = 12;
  String = (wchar_t *)v76;
  CAPITempBuffer<unsigned short,1>::Destroy(&v69);
  if ( v82 > 33 )
    GlobalFree(lpName);
  v82 = 33;
  lpName = (LPWSTR)v84;
LABEL_191:
  if ( v96 > 260 )
LABEL_166:
    GlobalFree(v95);
LABEL_167:
  v96 = 260;
  v95 = v97;
LABEL_168:
  CRegHandle::~CRegHandle(&v93);
  CRegHandle::~CRegHandle(&hKey);
  CRegHandle::~CRegHandle(&v91);
  return 1627;
}

```

## disassembly

```asm
0x180015ac0  mov     [rsp-8+arg_18], rbx
0x180015ac5  push    rbp
0x180015ac6  push    rsi
0x180015ac7  push    rdi
0x180015ac8  push    r12
0x180015aca  push    r13
0x180015acc  push    r14
0x180015ace  push    r15
0x180015ad0  lea     rbp, [rsp-0F70h]
0x180015ad8  mov     eax, 1070h
0x180015add  call    _alloca_probe
0x180015ae2  sub     rsp, rax
0x180015ae5  mov     rax, cs:__security_cookie
0x180015aec  xor     rax, rsp
0x180015aef  mov     [rbp+0FA0h+var_40], rax
0x180015af6  mov     rax, [rbp+0FA0h+arg_20]
0x180015afd  mov     rsi, rcx
0x180015b00  mov     rdi, [rbp+0FA0h+arg_28]
0x180015b07  xorps   xmm0, xmm0
0x180015b0a  mov     [rbp+0FA0h+lpsz], rax
0x180015b0e  xor     r15d, r15d
0x180015b11  mov     rax, [rbp+0FA0h+arg_30]
0x180015b18  mov     r13d, r8d
0x180015b1b  mov     [rbp+0FA0h+var_1008], rax
0x180015b1f  mov     r12, rdx
0x180015b22  lea     rax, [rbp+0FA0h+var_D80]
0x180015b29  mov     [rsp+10A0h+var_1030], rcx
0x180015b2e  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x180015b35  mov     [rbp+0FA0h+var_D90], rax
0x180015b3c  mov     [rsp+10A0h+var_1028], r9d
0x180015b41  mov     [rsp+10A0h+var_103C], r8d
0x180015b46  mov     [rbp+0FA0h+String1], rdx
0x180015b4a  mov     [rbp+0FA0h+var_FF8], rdi
0x180015b4e  movdqa  [rbp+0FA0h+var_DA0], xmm0
0x180015b56  mov     [rbp+0FA0h+var_D88], 1
0x180015b60  mov     [rbp+0FA0h+var_D80], r15w
0x180015b68  call    cs:__imp_InitializeCriticalSection
0x180015b6e  xorps   xmm0, xmm0
0x180015b71  mov     [rbp+0FA0h+var_DD8], 1
0x180015b7b  lea     rax, [rbp+0FA0h+var_DD0]
0x180015b82  movdqa  xmmword ptr [rbp+0FA0h+hKey], xmm0
0x180015b8a  lea     rcx, [rbp+0FA0h+var_DC8]; lpCriticalSection
0x180015b91  mov     [rbp+0FA0h+var_DE0], rax
0x180015b98  mov     [rbp+0FA0h+var_DD0], r15w
0x180015ba0  call    cs:__imp_InitializeCriticalSection
0x180015ba6  xorps   xmm0, xmm0
0x180015ba9  mov     [rbp+0FA0h+var_D38], 1
0x180015bb3  lea     rax, [rbp+0FA0h+var_D30]
0x180015bba  movdqa  xmmword ptr [rbp+0FA0h+var_D50], xmm0
0x180015bc2  lea     rcx, [rbp+0FA0h+var_D28]; lpCriticalSection
0x180015bc9  mov     [rbp+0FA0h+var_D40], rax
0x180015bd0  mov     [rbp+0FA0h+var_D30], r15w
0x180015bd8  call    cs:__imp_InitializeCriticalSection
0x180015bde  mov     dword ptr [rsp+10A0h+var_1038], r15d
0x180015be3  mov     r14b, 1
0x180015be6  mov     [rsp+10A0h+var_1040], r14b
0x180015beb  lea     rbx, aProducts; "Products"
0x180015bf2  cmp     r13d, 1
0x180015bf6  jz      loc_180017796
0x180015bfc  cmp     r13d, 3
0x180015c00  jz      loc_180016EEC
0x180015c06  lea     rax, [rbp+0FA0h+var_DA0]
0x180015c0d  mov     byte ptr [rsp+10A0h+lpClass], r15b
0x180015c12  mov     r9, rsi
0x180015c15  mov     [rsp+10A0h+lpReserved], rax
0x180015c1a  mov     r8, rbx
0x180015c1d  mov     rdx, r12
0x180015c20  mov     ecx, r13d
0x180015c23  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x180015c28  mov     ebx, eax
0x180015c2a  test    ebx, ebx
0x180015c2c  jnz     loc_180017811
0x180015c32  lea     rcx, [rbp+0FA0h+var_DC8]; lpCriticalSection
0x180015c39  call    cs:__imp_EnterCriticalSection
0x180015c3f  mov     rcx, [rbp+0FA0h+hKey]; hKey
0x180015c46  test    rcx, rcx
0x180015c49  jz      short loc_180015C63
0x180015c4b  call    cs:__imp_RegCloseKey
0x180015c51  mov     rax, [rbp+0FA0h+var_DE0]
0x180015c58  mov     [rbp+0FA0h+hKey], r15
0x180015c5f  mov     [rax], r15w
0x180015c63  lea     rcx, [rbp+0FA0h+var_DC8]; lpCriticalSection
0x180015c6a  call    cs:__imp_LeaveCriticalSection
0x180015c70  cmp     cs:?g_fWoW@@3_NA, r15b; bool g_fWoW
0x180015c77  mov     r9d, 20019h
0x180015c7d  jz      loc_180017157
0x180015c83  mov     rcx, qword ptr [rbp+0FA0h+var_DA0]
0x180015c8a  lea     rax, [rbp+0FA0h+hKey]
0x180015c91  mov     [rsp+10A0h+lpReserved], rax
0x180015c96  lea     r15, ValueName; "Patches"
0x180015c9d  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180015ca4  xor     r8d, r8d
0x180015ca7  mov     rdx, r15
0x180015caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015caf  mov     ebx, eax
0x180015cb1  test    eax, eax
0x180015cb3  jnz     loc_1800170D8
0x180015cb9  lea     rax, [rbp+0FA0h+var_CF0]
0x180015cc0  mov     [rsp+10A0h+lpClass], r15
0x180015cc5  lea     r9, aProducts; "Products"
0x180015ccc  mov     [rbp+0FA0h+var_D00], rax
0x180015cd3  lea     r8, aSSS; "%s\\%s\\%s"
0x180015cda  mov     [rbp+0FA0h+var_CF8], 104h
0x180015ce4  mov     edx, 104h; unsigned __int64
0x180015ce9  mov     [rsp+10A0h+lpReserved], rsi
0x180015cee  lea     rcx, [rbp+0FA0h+var_CF0]; unsigned __int16 *
0x180015cf5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015cfa  test    eax, eax
0x180015cfc  js      loc_1800171A3
0x180015d02  mov     eax, cs:?g_samRead@@3KA; ulong g_samRead
0x180015d08  lea     r9, [rbp+0FA0h+var_D50]
0x180015d0f  mov     r8, [rbp+0FA0h+var_D00]
0x180015d16  xor     ebx, ebx
0x180015d18  mov     [rsp+10A0h+lpftLastWriteTime], rbx
0x180015d1d  mov     rdx, rsi
0x180015d20  mov     dword ptr [rsp+10A0h+lpcchClass], r13d
0x180015d25  mov     rcx, r12
0x180015d28  mov     dword ptr [rsp+10A0h+lpClass], eax
0x180015d2c  mov     byte ptr [rsp+10A0h+lpReserved], bl; int
0x180015d30  call    ?OpenInstalledUserDataSubKeyPacked@@YAKPEBG00AEAVCRegHandle@@_NKW4iaaAppAssignment@@PEAW42@@Z; OpenInstalledUserDataSubKeyPacked(ushort const *,ushort const *,ushort const *,CRegHandle &,bool,ulong,iaaAppAssignment,iaaAppAssignment *)
0x180015d35  mov     ecx, eax
0x180015d37  mov     [rbp+0FA0h+var_1010], eax
0x180015d3a  cmp     [rbp+0FA0h+arg_38], bl
0x180015d40  jnz     loc_180016776
0x180015d46  mov     ebx, [rbp+0FA0h+arg_40]
0x180015d4c  mov     eax, ebx
0x180015d4e  and     eax, 1
0x180015d51  test    ecx, ecx
0x180015d53  jnz     loc_1800178D9
0x180015d59  xor     edi, edi
0x180015d5b  mov     [rbp+0FA0h+var_FE8], 1
0x180015d62  lea     rcx, [rbp+0FA0h+var_EE0]
0x180015d69  mov     esi, 21h ; '!'
0x180015d6e  mov     r15d, edi
0x180015d71  mov     [rbp+0FA0h+lpName], rcx
0x180015d78  lea     rcx, [rbp+0FA0h+var_FE0]
0x180015d7c  mov     dword ptr [rsp+10A0h+var_1038], edi
0x180015d80  mov     r14d, edi
0x180015d83  mov     [rbp+0FA0h+var_FF0], rcx
0x180015d87  mov     [rbp+0FA0h+Type], edi
0x180015d8a  mov     [rbp+0FA0h+var_EE8], esi
0x180015d90  cmp     [rsp+10A0h+var_1040], dil
0x180015d95  jz      short loc_180015D9E
0x180015d97  mov     r12d, edi
0x180015d9a  test    eax, eax
0x180015d9c  jnz     short loc_180015DA4
0x180015d9e  mov     r12d, 1
0x180015da4  mov     r13d, 103h
0x180015daa  nop     word ptr [rax+rax+00h]
0x180015db0  test    r14d, r14d
0x180015db3  jnz     loc_180017682
0x180015db9  mov     edx, r15d; dwIndex
0x180015dbc  test    r12d, r12d
0x180015dbf  jz      loc_180016D3E
0x180015dc5  mov     eax, [rbp+0FA0h+var_EE8]
0x180015dcb  lea     r9, [rbp+0FA0h+cchName]; lpcchName
0x180015dcf  mov     r8, [rbp+0FA0h+lpName]; lpName
0x180015dd6  mov     rcx, [rbp+0FA0h+var_D50]; hKey
0x180015ddd  mov     [rsp+10A0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180015de2  mov     [rsp+10A0h+lpcchClass], rdi; lpcchClass
0x180015de7  mov     [rsp+10A0h+lpClass], rdi; lpClass
0x180015dec  mov     [rsp+10A0h+lpReserved], rdi; lpReserved
0x180015df1  mov     [rbp+0FA0h+cchName], eax
0x180015df4  call    cs:__imp_RegEnumKeyExW
0x180015dfa  mov     r14d, eax
0x180015dfd  mov     rax, [rbp+0FA0h+var_FF0]
0x180015e01  mov     [rax], di
0x180015e04  cmp     r14d, 2
0x180015e08  jz      loc_18001711F
0x180015e0e  cmp     r14d, r13d
0x180015e11  jz      loc_180017122
0x180015e17  test    r14d, r14d
0x180015e1a  jnz     loc_1800178E6
0x180015e20  mov     rax, [rbp+0FA0h+lpName]
0x180015e27  inc     r15d
0x180015e2a  test    rax, rax
0x180015e2d  jz      short loc_180015DB0
0x180015e2f  mov     rcx, rsi
0x180015e32  cmp     word ptr [rax], 0
0x180015e36  jz      short loc_180015E42
0x180015e38  add     rax, 2
0x180015e3c  sub     rcx, 1
0x180015e40  jnz     short loc_180015E32
0x180015e42  mov     rdx, rsi
0x180015e45  sub     rdx, rcx
0x180015e48  test    rcx, rcx
0x180015e4b  cmovz   rdx, rdi
0x180015e4f  jz      loc_180015DB0
0x180015e55  cmp     rdx, 20h ; ' '
0x180015e59  jnz     loc_180015DB0
0x180015e5f  cmp     [rsp+10A0h+var_103C], 3
0x180015e64  lea     rax, [rbp+0FA0h+var_FC8]
0x180015e68  mov     [rbp+0FA0h+String], rax
0x180015e6c  mov     [rbp+0FA0h+var_FD0], 0Ch
0x180015e73  mov     [rbp+0FA0h+var_FCC], 0Ch
0x180015e7a  jz      loc_1800178F1
0x180015e80  cmp     [rsp+10A0h+var_1030], 0
0x180015e86  jz      loc_18001649A
0x180015e8c  mov     rdi, [rbp+0FA0h+lpName]
0x180015e93  lea     rax, [rbp+0FA0h+var_F30]
0x180015e97  mov     [rbp+0FA0h+var_F40], rax
0x180015e9b  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x180015e9f  xor     eax, eax
0x180015ea1  mov     [rbp+0FA0h+var_F38], 1
0x180015ea8  xorps   xmm0, xmm0
0x180015eab  mov     [rbp+0FA0h+var_F30], ax
0x180015eaf  movdqa  xmmword ptr [rbp+0FA0h+var_F50], xmm0
0x180015eb4  call    cs:__imp_InitializeCriticalSection
0x180015eba  lea     rax, [rbp+0FA0h+var_F90]
0x180015ebe  mov     [rbp+0FA0h+var_F98], 1
0x180015ec5  mov     [rbp+0FA0h+var_FA0], rax
0x180015ec9  lea     rcx, [rbp+0FA0h+var_F88]; lpCriticalSection
0x180015ecd  xor     eax, eax
0x180015ecf  xorps   xmm0, xmm0
0x180015ed2  mov     [rbp+0FA0h+var_F90], ax
0x180015ed6  movdqa  xmmword ptr [rbp+0FA0h+var_FB0], xmm0
0x180015edb  call    cs:__imp_InitializeCriticalSection
0x180015ee1  mov     edx, [rsp+10A0h+var_103C]
0x180015ee5  lea     rax, [rbp+0FA0h+var_AD0]
0x180015eec  mov     [rbp+0FA0h+var_AE0], rax
0x180015ef3  lea     rax, [rbp+0FA0h+var_840]
0x180015efa  mov     [rbp+0FA0h+hMem], rax
0x180015f01  mov     [rbp+0FA0h+var_AD8], 13Eh
0x180015f0b  mov     [rbp+0FA0h+var_848], 40h ; '@'
0x180015f15  cmp     edx, 2
0x180015f18  jnz     loc_180016D90
0x180015f1e  lea     rcx, aS1518; "S-1-5-18"
0x180015f25  mov     [rsp+10A0h+lpReserved], rcx
0x180015f2a  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180015f31  lea     rcx, [rbp+0FA0h+var_AD0]; unsigned __int16 *
0x180015f38  mov     edx, 13Eh; unsigned __int64
0x180015f3d  lea     r8, aSS_0; "%s\\%s"
0x180015f44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015f49  cmp     [rbp+0FA0h+var_848], 40h ; '@'
0x180015f50  mov     ebx, eax
0x180015f52  jle     short loc_180015F61
0x180015f54  mov     rcx, [rbp+0FA0h+hMem]; hMem
0x180015f5b  call    cs:__imp_GlobalFree
0x180015f61  test    ebx, ebx
0x180015f63  jnz     loc_180016041
0x180015f69  mov     r9, [rbp+0FA0h+var_AE0]
0x180015f70  lea     rax, [rbp+0FA0h+var_840]
0x180015f77  mov     [rbp+0FA0h+hMem], rax
0x180015f7e  lea     r8, aSSS; "%s\\%s\\%s"
0x180015f85  mov     rax, [rsp+10A0h+var_1030]
0x180015f8a  lea     rcx, [rbp+0FA0h+var_840]; unsigned __int16 *
0x180015f91  mov     [rsp+10A0h+lpClass], rax
0x180015f96  mov     edx, 400h; unsigned __int64
0x180015f9b  lea     rax, aProducts; "Products"
0x180015fa2  mov     [rbp+0FA0h+var_848], 400h
0x180015fac  mov     [rsp+10A0h+lpReserved], rax
0x180015fb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015fb6  test    eax, eax
0x180015fb8  js      loc_18001654C
0x180015fbe  mov     rbx, [rbp+0FA0h+hMem]
0x180015fc5  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x180015fc9  call    cs:__imp_EnterCriticalSection
0x180015fcf  mov     rcx, [rbp+0FA0h+var_F50]; hKey
0x180015fd3  test    rcx, rcx
0x180015fd6  jz      short loc_180015FEF
0x180015fd8  call    cs:__imp_RegCloseKey
0x180015fde  mov     rax, [rbp+0FA0h+var_F40]
0x180015fe2  xor     ecx, ecx
0x180015fe4  mov     [rbp+0FA0h+var_F50], 0
0x180015fec  mov     [rax], cx
0x180015fef  lea     rcx, [rbp+0FA0h+var_F28]; lpCriticalSection
0x180015ff3  call    cs:__imp_LeaveCriticalSection
0x180015ff9  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x180016000  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180016007  jz      loc_180016EBB
0x18001600d  lea     rax, [rbp+0FA0h+var_F50]
0x180016011  xor     r8d, r8d
0x180016014  mov     [rsp+10A0h+lpReserved], rax
0x180016019  mov     rdx, rbx
0x18001601c  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180016023  mov     rcx, 0FFFFFFFF80000002h
0x18001602a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001602f  cmp     [rbp+0FA0h+var_848], 400h
0x180016039  mov     ebx, eax
0x18001603b  jg      loc_180017910
0x180016041  cmp     [rbp+0FA0h+var_AD8], 13Eh
0x18001604b  jg      loc_180017922
0x180016051  test    ebx, ebx
0x180016053  jz      loc_1800164BE
0x180016059  cmp     [rsp+10A0h+var_103C], 1
0x18001605e  mov     rbx, [rbp+0FA0h+String1]
0x180016062  jz      loc_180017934
0x180016068  lea     rax, [rbp+0FA0h+var_E70]
0x18001606f  mov     [rbp+0FA0h+var_E78], 1
0x180016079  mov     [rbp+0FA0h+var_E80], rax
0x180016080  lea     rcx, [rbp+0FA0h+var_E68]; lpCriticalSection
0x180016087  xor     eax, eax
0x180016089  xorps   xmm0, xmm0
0x18001608c  mov     [rbp+0FA0h+var_E70], ax
0x180016093  movdqa  xmmword ptr [rbp+0FA0h+var_E90], xmm0
0x18001609b  call    cs:__imp_InitializeCriticalSection
0x1800160a1  mov     r9, [rsp+10A0h+var_1030]
0x1800160a6  lea     rax, [rbp+0FA0h+var_E90]
0x1800160ad  mov     ecx, [rsp+10A0h+var_103C]
0x1800160b1  lea     r8, aProducts; "Products"
  ... truncated ...
```
