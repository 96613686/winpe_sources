# GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,CRegHandle &)

- ea: `0x18003f930`
- end: `0x18004088c`
- name: `?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@AEAVCRegHandle@@@Z`
- size: `3932`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003c1d0`
- `0x18003e4c0`
- `0x1800e3d54`
- `0x18013b88c`

## callees

- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x180014160`
- `0x18003c030`
- `0x18003e40c`
- `0x18003ecd4`
- `0x18003f930`
- `0x1800408a0`
- `0x180040908`
- `0x18004cbfc`
- `0x18006cb7c`
- `0x180265202`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003fcbb`
- `ADVAPI32!RegQueryValueExW` at `0x180040138`
- `ADVAPI32!RegQueryValueExW` at `0x180040152`
- `ADVAPI32!RegQueryValueExW` at `0x1800403f7`
- `ADVAPI32!RegQueryValueExW` at `0x18003fcbb`
- `ADVAPI32!RegQueryValueExW` at `0x180040138`
- `ADVAPI32!RegQueryValueExW` at `0x180040152`
- `ADVAPI32!RegQueryValueExW` at `0x1800403f7`
- `ADVAPI32!RegCloseKey` at `0x18003fb0f`
- `ADVAPI32!RegCloseKey` at `0x18003fbd9`
- `ADVAPI32!RegCloseKey` at `0x18003fdd4`
- `ADVAPI32!RegCloseKey` at `0x18003fe67`
- `ADVAPI32!RegCloseKey` at `0x18003fb0f`
- `ADVAPI32!RegCloseKey` at `0x18003fbd9`
- `ADVAPI32!RegCloseKey` at `0x18003fdd4`
- `ADVAPI32!RegCloseKey` at `0x18003fe67`
- `KERNEL32!InitializeCriticalSection` at `0x18003fa14`
- `KERNEL32!InitializeCriticalSection` at `0x180040435`
- `KERNEL32!InitializeCriticalSection` at `0x18003fa14`
- `KERNEL32!InitializeCriticalSection` at `0x180040435`
- `KERNEL32!DeleteCriticalSection` at `0x18003fe00`
- `KERNEL32!DeleteCriticalSection` at `0x18003fe93`
- `KERNEL32!DeleteCriticalSection` at `0x18003fe00`
- `KERNEL32!DeleteCriticalSection` at `0x18003fe93`
- `KERNEL32!LeaveCriticalSection` at `0x18003fb30`
- `KERNEL32!LeaveCriticalSection` at `0x18003fbf9`
- `KERNEL32!LeaveCriticalSection` at `0x18003fdf0`
- `KERNEL32!LeaveCriticalSection` at `0x18003fe83`
- `KERNEL32!LeaveCriticalSection` at `0x18003fb30`
- `KERNEL32!LeaveCriticalSection` at `0x18003fbf9`
- `KERNEL32!LeaveCriticalSection` at `0x18003fdf0`
- `KERNEL32!LeaveCriticalSection` at `0x18003fe83`
- `KERNEL32!EnterCriticalSection` at `0x18003fafa`
- `KERNEL32!EnterCriticalSection` at `0x18003fbc5`
- `KERNEL32!EnterCriticalSection` at `0x18003fdbf`
- `KERNEL32!EnterCriticalSection` at `0x18003fe52`
- `KERNEL32!EnterCriticalSection` at `0x18003fafa`
- `KERNEL32!EnterCriticalSection` at `0x18003fbc5`
- `KERNEL32!EnterCriticalSection` at `0x18003fdbf`
- `KERNEL32!EnterCriticalSection` at `0x18003fe52`
- `KERNEL32!GlobalAlloc` at `0x18004009c`
- `KERNEL32!GlobalAlloc` at `0x1800402ae`
- `KERNEL32!GlobalAlloc` at `0x18004037e`
- `KERNEL32!GlobalAlloc` at `0x1800404c6`
- `KERNEL32!GlobalAlloc` at `0x180040566`
- `KERNEL32!GlobalAlloc` at `0x18004009c`
- `KERNEL32!GlobalAlloc` at `0x1800402ae`
- `KERNEL32!GlobalAlloc` at `0x18004037e`
- `KERNEL32!GlobalAlloc` at `0x1800404c6`
- `KERNEL32!GlobalAlloc` at `0x180040566`
- `KERNEL32!GlobalFree` at `0x18003fa89`
- `KERNEL32!GlobalFree` at `0x18003fb81`
- `KERNEL32!GlobalFree` at `0x18003fe16`
- `KERNEL32!GlobalFree` at `0x18003fea9`
- `KERNEL32!GlobalFree` at `0x18003ff72`
- `KERNEL32!GlobalFree` at `0x1800400bd`
- `KERNEL32!GlobalFree` at `0x1800401eb`
- `KERNEL32!GlobalFree` at `0x180040263`
- `KERNEL32!GlobalFree` at `0x180040296`
- `KERNEL32!GlobalFree` at `0x1800402d5`
- `KERNEL32!GlobalFree` at `0x180040355`
- `KERNEL32!GlobalFree` at `0x180040366`
- `KERNEL32!GlobalFree` at `0x18004062e`
- `KERNEL32!GlobalFree` at `0x180040744`
- `KERNEL32!GlobalFree` at `0x1800407ad`
- `KERNEL32!GlobalFree` at `0x1800407bf`
- `KERNEL32!GlobalFree` at `0x18004086a`
- `KERNEL32!GlobalFree` at `0x18004087b`
- `KERNEL32!GlobalFree` at `0x18003fa89`
- `KERNEL32!GlobalFree` at `0x18003fb81`
- `KERNEL32!GlobalFree` at `0x18003fe16`
- `KERNEL32!GlobalFree` at `0x18003fea9`
- `KERNEL32!GlobalFree` at `0x18003ff72`
- `KERNEL32!GlobalFree` at `0x1800400bd`
- `KERNEL32!GlobalFree` at `0x1800401eb`
- `KERNEL32!GlobalFree` at `0x180040263`
- `KERNEL32!GlobalFree` at `0x180040296`
- `KERNEL32!GlobalFree` at `0x1800402d5`
- `KERNEL32!GlobalFree` at `0x180040355`
- `KERNEL32!GlobalFree` at `0x180040366`
- `KERNEL32!GlobalFree` at `0x18004062e`
- `KERNEL32!GlobalFree` at `0x180040744`
- `KERNEL32!GlobalFree` at `0x1800407ad`
- `KERNEL32!GlobalFree` at `0x1800407bf`
- `KERNEL32!GlobalFree` at `0x18004086a`
- `KERNEL32!GlobalFree` at `0x18004087b`

## string_xrefs

- `0x18003fa5e`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18003ff47`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c
__int64 __fastcall GetAppliedPatchInfoInternal(
        unsigned int a1,
        const WCHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  const WCHAR *v7; // rax
  wchar_t **v8; // rdi
  const WCHAR *v9; // r14
  __int64 v12; // r8
  int v13; // ecx
  int v14; // edx
  int v16; // esi
  char v17; // r14
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  unsigned int CurrentUserStringSID; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v20; // rbx
  __int64 v21; // r9
  PRTL_CRITICAL_SECTION_DEBUG v22; // rcx
  __int64 v23; // r9
  unsigned int v24; // eax
  const WCHAR *v25; // rbx
  HKEY v26; // r14
  unsigned int v27; // esi
  unsigned int v28; // r14d
  __int64 v29; // r8
  __int64 v30; // rdx
  unsigned __int16 *v31; // rbx
  unsigned int *v32; // r9
  PRTL_CRITICAL_SECTION_DEBUG v33; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v34; // rbx
  HKEY *v35; // rax
  unsigned int v36; // r8d
  wchar_t *v37; // rax
  __int64 v38; // rdx
  PRTL_CRITICAL_SECTION_DEBUG v39; // rcx
  DWORD v40; // esi
  DWORD v41; // esi
  BYTE *lpData; // r15
  HKEY v43; // r14
  unsigned int v44; // r14d
  unsigned int v45; // edx
  __int64 v46; // r8
  unsigned int v47; // r14d
  unsigned int v48; // ebx
  HGLOBAL v49; // rbx
  unsigned __int64 v50; // r14
  unsigned __int16 *v51; // rdi
  const unsigned __int16 *v52; // r8
  DWORD v53; // esi
  DWORD v54; // esi
  BYTE *v55; // r15
  __int64 v56; // r8
  int v57; // r14d
  unsigned int v58; // ebx
  int v59; // eax
  const wchar_t *v60; // rcx
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v63; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v64; // [rsp+58h] [rbp-A8h]
  const WCHAR *v65; // [rsp+60h] [rbp-A0h]
  HGLOBAL v66; // [rsp+68h] [rbp-98h] BYREF
  int v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+74h] [rbp-8Ch]
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  HGLOBAL v71; // [rsp+90h] [rbp-70h]
  int v72; // [rsp+98h] [rbp-68h]
  __int16 v73; // [rsp+A0h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION v76; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v77[4]; // [rsp+8E0h] [rbp+7E0h] BYREF
  int v78; // [rsp+8E8h] [rbp+7E8h]
  unsigned __int16 v79[320]; // [rsp+8F0h] [rbp+7F0h] BYREF

  v7 = L"Transforms";
  v8 = &off_1802688A0;
  v9 = a4;
  v64 = a4;
  *(_QWORD *)cbData = a3;
  v65 = a2;
  if ( L"Transforms" )
  {
    while ( 1 )
    {
      v12 = a5 - (_QWORD)v7;
      do
      {
        v13 = *(const WCHAR *)((char *)v7 + v12);
        v14 = *v7 - v13;
        if ( v14 )
          break;
        ++v7;
      }
      while ( v13 );
      if ( !v14 )
        break;
      v7 = v8[4];
      v8 += 4;
      if ( !v7 )
        return 1608;
    }
  }
  if ( !*v8 || (*((_BYTE *)v8 + 28) & 2) == 0 )
    return 1608;
  v71 = &v73;
  v72 = 1;
  v73 = 0;
  *(_OWORD *)hKey = 0;
  InitializeCriticalSection(&CriticalSection);
  v16 = *((_DWORD *)v8 + 6);
  if ( v16 == 4 )
  {
    if ( *(_QWORD *)a7 )
      goto LABEL_34;
    hMem.LockCount = 64;
    hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
    v17 = 1;
    if ( a1 == 2 )
    {
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"S-1-5-18";
    }
    else
    {
      DebugInfo = 0;
      if ( a1 > 1 )
      {
        if ( a1 == 3 )
        {
          CurrentUserStringSID = 2;
          goto LABEL_24;
        }
      }
      else if ( *(_QWORD *)cbData )
      {
        DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)cbData;
      }
      else
      {
        hMem.RecursionCount = 64;
        CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
        if ( CurrentUserStringSID )
        {
          if ( hMem.LockCount <= 64 )
            goto LABEL_16;
          goto LABEL_15;
        }
        DebugInfo = hMem.DebugInfo;
      }
    }
    CurrentUserStringSID = StringCchPrintfW(
                             v77,
                             0x13Eu,
                             L"%s\\%s",
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                             DebugInfo);
    if ( hMem.LockCount <= 64 )
    {
LABEL_16:
      if ( CurrentUserStringSID )
        goto LABEL_24;
      hMem.LockCount = 260;
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      if ( (int)StringCchPrintfW(
                  (unsigned __int16 *)&hMem.OwningThread,
                  0x104u,
                  L"%s\\%s\\%s\\%s",
                  v77,
                  L"Products",
                  v65,
                  L"Patches") >= 0 )
      {
        v20 = hMem.DebugInfo;
        EnterCriticalSection(&CriticalSection);
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
          *(_WORD *)v71 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        v21 = g_samRead;
        if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
          LODWORD(v21) = g_samRead | 0x100;
        CurrentUserStringSID = ((__int64 (__fastcall *)(__int64, PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                                 -2147483646,
                                 v20,
                                 0,
                                 v21,
                                 hKey);
        if ( hMem.LockCount > 260 )
        {
          v22 = hMem.DebugInfo;
LABEL_23:
          GlobalFree(v22);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
      if ( hMem.LockCount <= 260 )
      {
LABEL_97:
        CurrentUserStringSID = 1627;
        goto LABEL_24;
      }
      v39 = hMem.DebugInfo;
LABEL_96:
      GlobalFree(v39);
      goto LABEL_97;
    }
LABEL_15:
    GlobalFree(hMem.DebugInfo);
    goto LABEL_16;
  }
  v17 = 0;
  if ( !v16 )
  {
    if ( a1 == 1 && *(_QWORD *)cbData && !IsCurrentUser(*(wchar_t **)cbData) )
    {
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      return 87;
    }
    LODWORD(hMem.LockSemaphore) = 1;
    hMem.OwningThread = &hMem.SpinCount;
    LOWORD(hMem.SpinCount) = 0;
    *(_OWORD *)&hMem.DebugInfo = 0;
    InitializeCriticalSection(&v76);
    CurrentUserStringSID = OpenSpecificUsersAdvertisedSubKeyPacked(
                             a1,
                             *(const wchar_t **)cbData,
                             (WCHAR *)L"Products",
                             a2,
                             &hMem,
                             0);
    if ( !CurrentUserStringSID )
    {
      CRegHandleStatic::operator&(hKey);
      Type = g_samRead;
      AdjustREGSAM(&Type);
      CurrentUserStringSID = ((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const WCHAR *, _QWORD, _QWORD, __int64))RegOpenKeyAPI)(
                               hMem.DebugInfo,
                               L"Patches",
                               0,
                               Type,
                               v56);
    }
    CRegHandle::~CRegHandle((CRegHandle *)&hMem);
    goto LABEL_24;
  }
  if ( v16 != 3 )
    goto LABEL_92;
  v78 = 318;
  *(_QWORD *)v77 = v79;
  hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
  hMem.LockCount = 64;
  if ( a1 == 2 )
  {
    v33 = (PRTL_CRITICAL_SECTION_DEBUG)L"S-1-5-18";
    goto LABEL_78;
  }
  v33 = 0;
  if ( a1 > 1 )
  {
    if ( a1 == 3 )
    {
      CurrentUserStringSID = 2;
      goto LABEL_84;
    }
LABEL_78:
    CurrentUserStringSID = StringCchPrintfW(
                             v79,
                             0x13Eu,
                             L"%s\\%s",
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                             v33);
    if ( hMem.LockCount <= 64 )
      goto LABEL_80;
    goto LABEL_79;
  }
  if ( *(_QWORD *)cbData )
  {
    v33 = *(PRTL_CRITICAL_SECTION_DEBUG *)cbData;
    goto LABEL_78;
  }
  hMem.RecursionCount = 64;
  CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
  if ( !CurrentUserStringSID )
  {
    v33 = hMem.DebugInfo;
    goto LABEL_78;
  }
  if ( hMem.LockCount > 64 )
LABEL_79:
    GlobalFree(hMem.DebugInfo);
LABEL_80:
  if ( !CurrentUserStringSID )
  {
    hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
    hMem.LockCount = 1024;
    if ( (int)StringCchPrintfW(
                (unsigned __int16 *)&hMem.OwningThread,
                0x400u,
                L"%s\\%s\\%s",
                *(_QWORD *)v77,
                L"Patches",
                v64) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v78 <= 318 )
        goto LABEL_97;
      v39 = *(PRTL_CRITICAL_SECTION_DEBUG *)v77;
      goto LABEL_96;
    }
    v34 = hMem.DebugInfo;
    v35 = (HKEY *)CRegHandleStatic::operator&(hKey);
    CurrentUserStringSID = MsiRegOpen64bitKey(HKEY_LOCAL_MACHINE, &v34->Type, v36, g_samRead, v35);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_84:
  if ( v78 > 318 )
  {
    v22 = *(PRTL_CRITICAL_SECTION_DEBUG *)v77;
    goto LABEL_23;
  }
LABEL_24:
  if ( CurrentUserStringSID == 2 )
  {
    if ( !v17 )
      goto LABEL_205;
  }
  else if ( CurrentUserStringSID )
  {
    goto LABEL_212;
  }
  v9 = v64;
  if ( v16 == 4 && !*(_QWORD *)a7 )
  {
    if ( hKey[0] )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a7 + 40));
      if ( *(_QWORD *)a7 )
      {
        RegCloseKey(*(HKEY *)a7);
        *(_QWORD *)a7 = 0;
        **(_WORD **)(a7 + 16) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a7 + 40));
      v23 = g_samRead;
      if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
        LODWORD(v23) = g_samRead | 0x100;
      v24 = ((__int64 (__fastcall *)(HKEY, const WCHAR *, _QWORD, __int64, __int64))RegOpenKeyAPI)(
              hKey[0],
              v9,
              0,
              v23,
              a7);
      CurrentUserStringSID = v24;
      if ( v24 != 2 )
      {
        if ( !v24 )
          goto LABEL_34;
LABEL_212:
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
        return CurrentUserStringSID;
      }
    }
    if ( !IsPatchAppliedToProduct(v9, v65, *(wchar_t **)cbData, a1, 1) )
      goto LABEL_205;
    v37 = v8[2];
    if ( !v37 )
    {
      if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a6, 1, 0) )
        goto LABEL_159;
      **(_WORD **)a6 = 0;
      goto LABEL_130;
    }
    v38 = 0x7FFFFFFF;
    do
    {
      if ( !*v37 )
        break;
      ++v37;
      --v38;
    }
    while ( v38 );
    if ( v38 )
    {
      if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a6, (unsigned int)(0x7FFFFFFF - v38 + 1), 0)
        || (int)StringCchCopyW(*(unsigned __int16 **)a6, *(int *)(a6 + 8), v8[2]) < 0 )
      {
        goto LABEL_159;
      }
      goto LABEL_130;
    }
LABEL_92:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1627;
  }
LABEL_34:
  v25 = v8[1];
  v63 = 0;
  if ( !v25 )
    v25 = v9;
  if ( !a1 )
  {
    v59 = wcscmp_0(*v8, L"LocalPackage");
    v60 = L"ManagedLocalPackage";
    if ( v59 )
      v60 = v25;
    v25 = v60;
  }
  v67 = 4;
  v66 = Data;
  v68 = 4;
  cbData[0] = 8;
  Type = 0;
  if ( v16 != 4 )
  {
    v43 = hKey[0];
    v27 = RegQueryValueExW(hKey[0], v25, 0, &Type, Data, cbData);
    if ( v27 != 234 )
      goto LABEL_107;
    v53 = cbData[0];
    if ( Type - 1 > 1 )
    {
      if ( Type != 7 )
        goto LABEL_147;
      v53 = cbData[0] + 4;
    }
    else
    {
      v53 = cbData[0] + 2;
    }
    cbData[0] = v53;
LABEL_147:
    v54 = v53 >> 1;
    if ( (int)v54 > v68 )
    {
      v55 = (BYTE *)GlobalAlloc(0, 2LL * v54);
      if ( !v55 )
      {
        v27 = 14;
        goto LABEL_48;
      }
    }
    else
    {
      v55 = Data;
    }
    if ( v66 != Data )
      GlobalFree(v66);
    v66 = v55;
    v67 = v54;
    v27 = RegQueryValueExW(v43, v25, 0, &v63, v55, cbData);
LABEL_107:
    if ( !v27 )
    {
      if ( Type - 1 > 1 )
      {
        if ( Type != 7 )
          goto LABEL_47;
        v44 = 2;
      }
      else
      {
        v44 = 1;
      }
      v45 = 0;
      v46 = (cbData[0] >> 1) - 1;
      do
      {
        if ( (int)v46 < 0 )
          break;
        if ( *((_WORD *)v66 + v46) )
          break;
        ++v45;
        v46 = (unsigned int)(v46 - 1);
      }
      while ( v45 < v44 );
      if ( v44 <= v45 )
        goto LABEL_47;
      v47 = v44 - v45;
      v48 = v47 + (cbData[0] >> 1);
      if ( v48 <= v67 || (LOBYTE(v46) = 1, (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&v66, v48, v46)) )
      {
        for ( ; v47; --v47 )
          *((_WORD *)v66 + v48 - v47) = 0;
        goto LABEL_47;
      }
      v27 = 14;
      goto LABEL_48;
    }
LABEL_47:
    v63 = Type;
    goto LABEL_48;
  }
  v26 = *(HKEY *)a7;
  v27 = RegQueryValueExW(*(HKEY *)a7, v25, 0, &Type, Data, cbData);
  if ( v27 == 234 )
  {
    v40 = cbData[0];
    if ( Type - 1 > 1 )
    {
      if ( Type != 7 )
        goto LABEL_101;
      v40 = cbData[0] + 4;
    }
    else
    {
      v40 = cbData[0] + 2;
    }
    cbData[0] = v40;
LABEL_101:
    v41 = v40 >> 1;
    if ( (int)v41 > v68 )
    {
      lpData = (BYTE *)GlobalAlloc(0, 2LL * v41);
      if ( !lpData )
      {
        v27 = 14;
        goto LABEL_48;
      }
    }
    else
    {
      lpData = Data;
    }
    if ( v66 != Data )
      GlobalFree(v66);
    v66 = lpData;
    v67 = v41;
    v27 = RegQueryValueExW(v26, v25, 0, &v63, lpData, cbData);
  }
  if ( v27 )
    goto LABEL_47;
  if ( Type - 1 <= 1 )
  {
    v28 = 1;
    goto LABEL_42;
  }
  if ( Type != 7 )
    goto LABEL_47;
  v28 = 2;
LABEL_42:
  v29 = 0;
  v30 = (cbData[0] >> 1) - 1;
  do
  {
    if ( (int)v30 < 0 )
      break;
    if ( *((_WORD *)v66 + v30) )
      break;
    v29 = (unsigned int)(v29 + 1);
    v30 = (unsigned int)(v30 - 1);
  }
  while ( (unsigned int)v29 < v28 );
  if ( v28 <= (unsigned int)v29 )
    goto LABEL_47;
  v57 = v28 - v29;
  v58 = v57 + (cbData[0] >> 1);
  if ( v58 <= v67 || (LOBYTE(v29) = 1, (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&v66, v58, v29)) )
  {
    for ( ; v57; --v57 )
      *((_WORD *)v66 + v58 - v57) = 0;
    goto LABEL_47;
  }
  v27 = 14;
LABEL_48:
  if ( v27 )
  {
    if ( v27 != 2 )
      goto LABEL_64;
    if ( v8[1] )
    {
      if ( !*(_DWORD *)(a6 + 8) )
      {
        if ( *(int *)(a6 + 12) < 1 )
          v49 = GlobalAlloc(0, 2u);
        else
          v49 = (HGLOBAL)(a6 + 16);
        if ( !v49 )
        {
          if ( v67 <= 4 )
            goto LABEL_158;
          goto LABEL_142;
        }
        if ( *(_QWORD *)a6 != a6 + 16 )
          GlobalFree(*(HGLOBAL *)a6);
        *(_QWORD *)a6 = v49;
        *(_DWORD *)(a6 + 8) = 1;
      }
      **(_WORD **)a6 = 0;
      if ( v67 > 4 )
        GlobalFree(v66);
      v67 = 4;
      v66 = Data;
LABEL_130:
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      return 0;
    }
    if ( v67 > 4 )
      GlobalFree(v66);
    v67 = 4;
    v66 = Data;
LABEL_205:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1647;
  }
  if ( v63 == 1 )
  {
    v50 = v67;
    if ( v67 > *(_DWORD *)(a6 + 12) )
      v51 = (unsigned __int16 *)GlobalAlloc(0, 2LL * v67);
    else
      v51 = (unsigned __int16 *)(a6 + 16);
    if ( v51 )
    {
      if ( *(_QWORD *)a6 != a6 + 16 )
        GlobalFree(*(HGLOBAL *)a6);
      v52 = (const unsigned __int16 *)v66;
      *(_QWORD *)a6 = v51;
      *(_DWORD *)(a6 + 8) = v50;
      if ( (int)StringCchCopyW(v51, v50, v52) >= 0 )
        goto LABEL_65;
    }
LABEL_141:
    if ( v67 <= 4 )
    {
LABEL_158:
      v67 = 4;
      v66 = Data;
LABEL_159:
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      return 14;
    }
LABEL_142:
    GlobalFree(v66);
    goto LABEL_158;
  }
  if ( v63 != 4 )
  {
LABEL_64:
    v27 = 1610;
    goto LABEL_65;
  }
  if ( *(int *)(a6 + 12) < 12 )
    v31 = (unsigned __int16 *)GlobalAlloc(0, 0x18u);
  else
    v31 = (unsigned __int16 *)(a6 + 16);
  if ( !v31 )
    goto LABEL_141;
  if ( *(_QWORD *)a6 != a6 + 16 )
    GlobalFree(*(HGLOBAL *)a6);
  v32 = (unsigned int *)v66;
  *(_QWORD *)a6 = v31;
  *(_DWORD *)(a6 + 8) = 12;
  if ( (int)StringCchPrintfW(v31, 0xCu, L"%d", *v32) < 0 )
  {
    if ( v67 > 4 )
      GlobalFree(v66);
    v67 = 4;
    v66 = Data;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v71 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    if ( v72 > 1 )
      GlobalFree(v71);
    return 14;
  }
LABEL_65:
  if ( v67 > 4 )
    GlobalFree(v66);
  v67 = 4;
  v66 = Data;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)v71 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v72 > 1 )
    GlobalFree(v71);
  return v27;
}

```

## disassembly

```asm
0x18003f930  push    rbp
0x18003f932  push    rbx
0x18003f933  push    rdi
0x18003f934  push    r12
0x18003f936  push    r13
0x18003f938  push    r14
0x18003f93a  push    r15
0x18003f93c  lea     rbp, [rsp-0A80h]
0x18003f944  sub     rsp, 0B80h
0x18003f94b  mov     rax, cs:__security_cookie
0x18003f952  xor     rax, rsp
0x18003f955  mov     [rbp+0AB0h+var_40], rax
0x18003f95c  mov     rax, cs:off_1802688A0; "Transforms"
0x18003f963  lea     rdi, off_1802688A0; "Transforms"
0x18003f96a  mov     r12, [rbp+0AB0h+arg_28]
0x18003f971  mov     r14, r9
0x18003f974  mov     r15, [rbp+0AB0h+arg_30]
0x18003f97b  mov     rbx, rdx
0x18003f97e  mov     [rsp+0BB0h+var_B58], r9
0x18003f983  mov     r13d, ecx
0x18003f986  mov     qword ptr [rsp+0BB0h+cbData], r8
0x18003f98b  mov     [rsp+0BB0h+var_B50], rdx
0x18003f990  test    rax, rax
0x18003f993  jz      short loc_18003F9DF
0x18003f995  mov     r9, [rbp+0AB0h+arg_20]
0x18003f99c  nop     dword ptr [rax+00h]
0x18003f9a0  mov     r8, r9
0x18003f9a3  sub     r8, rax
0x18003f9a6  nop     word ptr [rax+rax+00000000h]
0x18003f9b0  movzx   edx, word ptr [rax]
0x18003f9b3  movzx   ecx, word ptr [rax+r8]
0x18003f9b8  sub     edx, ecx
0x18003f9ba  jnz     short loc_18003F9C4
0x18003f9bc  add     rax, 2
0x18003f9c0  test    ecx, ecx
0x18003f9c2  jnz     short loc_18003F9B0
0x18003f9c4  test    edx, edx
0x18003f9c6  jz      short loc_18003F9DF
0x18003f9c8  mov     rax, [rdi+20h]
0x18003f9cc  add     rdi, 20h ; ' '
0x18003f9d0  test    rax, rax
0x18003f9d3  jnz     short loc_18003F9A0
0x18003f9d5  mov     eax, 648h
0x18003f9da  jmp     loc_18003FEBF
0x18003f9df  cmp     qword ptr [rdi], 0
0x18003f9e3  jz      short loc_18003F9D5
0x18003f9e5  test    byte ptr [rdi+1Ch], 2
0x18003f9e9  jz      short loc_18003F9D5
0x18003f9eb  lea     rax, [rbp+0AB0h+var_B10]
0x18003f9ef  mov     [rsp+0BB0h+arg_0], rsi
0x18003f9f7  mov     [rbp+0AB0h+var_B20], rax
0x18003f9fb  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003f9ff  xor     eax, eax
0x18003fa01  mov     [rbp+0AB0h+var_B18], 1
0x18003fa08  xorps   xmm0, xmm0
0x18003fa0b  mov     [rbp+0AB0h+var_B10], ax
0x18003fa0f  movdqa  xmmword ptr [rbp+0AB0h+hKey], xmm0
0x18003fa14  call    cs:__imp_InitializeCriticalSection
0x18003fa1b  nop     dword ptr [rax+rax+00h]
0x18003fa20  mov     esi, [rdi+18h]
0x18003fa23  cmp     esi, 4
0x18003fa26  jnz     loc_18003FEF6
0x18003fa2c  cmp     qword ptr [r15], 0
0x18003fa30  jnz     loc_18003FC47
0x18003fa36  mov     dword ptr [rbp+0AB0h+hMem+8], 40h ; '@'
0x18003fa3d  lea     rax, [rbp+0AB0h+var_AD0]
0x18003fa41  mov     [rbp+0AB0h+hMem], rax
0x18003fa45  mov     r14b, 1
0x18003fa48  cmp     r13d, 2
0x18003fa4c  jnz     loc_18004050A
0x18003fa52  lea     rcx, aS1518_0; "S-1-5-18"
0x18003fa59  mov     [rsp+0BB0h+lpData], rcx
0x18003fa5e  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003fa65  lea     rcx, [rbp+0AB0h+var_2D0]; unsigned __int16 *
0x18003fa6c  mov     edx, 13Eh; unsigned __int64
0x18003fa71  lea     r8, aSS_0; "%s\\%s"
0x18003fa78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fa7d  cmp     dword ptr [rbp+0AB0h+hMem+8], 40h ; '@'
0x18003fa81  mov     ebx, eax
0x18003fa83  jle     short loc_18003FA95
0x18003fa85  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x18003fa89  call    cs:__imp_GlobalFree
0x18003fa90  nop     dword ptr [rax+rax+00h]
0x18003fa95  test    ebx, ebx
0x18003fa97  jnz     loc_18003FB8D
0x18003fa9d  lea     rax, [rbp+0AB0h+var_AD0]
0x18003faa1  mov     dword ptr [rbp+0AB0h+hMem+8], 104h
0x18003faa8  mov     [rbp+0AB0h+hMem], rax
0x18003faac  lea     r9, [rbp+0AB0h+var_2D0]
0x18003fab3  lea     rax, ValueName; "Patches"
0x18003faba  mov     edx, 104h; unsigned __int64
0x18003fabf  mov     [rsp+0BB0h+var_B80], rax
0x18003fac4  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18003facb  mov     rax, [rsp+0BB0h+var_B50]
0x18003fad0  lea     rcx, [rbp+0AB0h+var_AD0]; unsigned __int16 *
0x18003fad4  mov     [rsp+0BB0h+lpcbData], rax
0x18003fad9  lea     rax, aProducts; "Products"
0x18003fae0  mov     [rsp+0BB0h+lpData], rax
0x18003fae5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003faea  test    eax, eax
0x18003faec  js      loc_1800400B0
0x18003faf2  mov     rbx, [rbp+0AB0h+hMem]
0x18003faf6  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fafa  call    cs:__imp_EnterCriticalSection
0x18003fb01  nop     dword ptr [rax+rax+00h]
0x18003fb06  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x18003fb0a  test    rcx, rcx
0x18003fb0d  jz      short loc_18003FB2C
0x18003fb0f  call    cs:__imp_RegCloseKey
0x18003fb16  nop     dword ptr [rax+rax+00h]
0x18003fb1b  mov     rax, [rbp+0AB0h+var_B20]
0x18003fb1f  xor     ecx, ecx
0x18003fb21  mov     [rbp+0AB0h+hKey], 0
0x18003fb29  mov     [rax], cx
0x18003fb2c  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fb30  call    cs:__imp_LeaveCriticalSection
0x18003fb37  nop     dword ptr [rax+rax+00h]
0x18003fb3c  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18003fb43  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003fb4a  jz      loc_1800405AA
0x18003fb50  lea     rax, [rbp+0AB0h+hKey]
0x18003fb54  xor     r8d, r8d
0x18003fb57  mov     [rsp+0BB0h+lpData], rax
0x18003fb5c  mov     rdx, rbx
0x18003fb5f  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003fb66  mov     rcx, 0FFFFFFFF80000002h
0x18003fb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb72  cmp     dword ptr [rbp+0AB0h+hMem+8], 104h
0x18003fb79  mov     ebx, eax
0x18003fb7b  jle     short loc_18003FB8D
0x18003fb7d  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x18003fb81  call    cs:__imp_GlobalFree
0x18003fb88  nop     dword ptr [rax+rax+00h]
0x18003fb8d  cmp     ebx, 2
0x18003fb90  jz      loc_1800407D0
0x18003fb96  test    ebx, ebx
0x18003fb98  jnz     loc_1800407DA
0x18003fb9e  mov     r14, [rsp+0BB0h+var_B58]
0x18003fba3  cmp     esi, 4
0x18003fba6  jnz     loc_18003FC47
0x18003fbac  cmp     qword ptr [r15], 0
0x18003fbb0  jnz     loc_18003FC47
0x18003fbb6  cmp     [rbp+0AB0h+hKey], 0
0x18003fbbb  jz      loc_180040022
0x18003fbc1  lea     rcx, [r15+28h]; lpCriticalSection
0x18003fbc5  call    cs:__imp_EnterCriticalSection
0x18003fbcc  nop     dword ptr [rax+rax+00h]
0x18003fbd1  mov     rcx, [r15]; hKey
0x18003fbd4  test    rcx, rcx
0x18003fbd7  jz      short loc_18003FBF5
0x18003fbd9  call    cs:__imp_RegCloseKey
0x18003fbe0  nop     dword ptr [rax+rax+00h]
0x18003fbe5  mov     qword ptr [r15], 0
0x18003fbec  xor     eax, eax
0x18003fbee  mov     rdx, [r15+10h]
0x18003fbf2  mov     [rdx], ax
0x18003fbf5  lea     rcx, [r15+28h]; lpCriticalSection
0x18003fbf9  call    cs:__imp_LeaveCriticalSection
0x18003fc00  nop     dword ptr [rax+rax+00h]
0x18003fc05  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18003fc0c  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003fc13  jz      loc_180040588
0x18003fc19  mov     rcx, [rbp+0AB0h+hKey]
0x18003fc1d  xor     r8d, r8d
0x18003fc20  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003fc27  mov     rdx, r14
0x18003fc2a  mov     [rsp+0BB0h+lpData], r15
0x18003fc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc34  mov     ebx, eax
0x18003fc36  cmp     eax, 2
0x18003fc39  jz      loc_180040022
0x18003fc3f  test    eax, eax
0x18003fc41  jnz     loc_1800407DA
0x18003fc47  mov     rbx, [rdi+8]
0x18003fc4b  test    rbx, rbx
0x18003fc4e  mov     [rsp+0BB0h+var_B60], 0
0x18003fc56  cmovz   rbx, r14
0x18003fc5a  test    r13d, r13d
0x18003fc5d  jz      loc_180040846
0x18003fc63  lea     rax, [rsp+0BB0h+Data]
0x18003fc68  mov     [rsp+0BB0h+var_B40], 4
0x18003fc70  mov     [rsp+0BB0h+var_B48], rax
0x18003fc75  lea     r9, [rsp+0BB0h+Type]; lpType
0x18003fc7a  lea     rax, [rsp+0BB0h+cbData]
0x18003fc7f  mov     [rsp+0BB0h+var_B3C], 4
0x18003fc87  mov     [rsp+0BB0h+lpcbData], rax; lpcbData
0x18003fc8c  xor     r13d, r13d
0x18003fc8f  xor     r8d, r8d; lpReserved
0x18003fc92  mov     [rsp+0BB0h+cbData], 8
0x18003fc9a  mov     [rsp+0BB0h+Type], r13d
0x18003fc9f  lea     rax, [rsp+0BB0h+Data]
0x18003fca4  mov     [rsp+0BB0h+lpData], rax; lpData
0x18003fca9  mov     rdx, rbx; lpValueName
0x18003fcac  cmp     esi, 4
0x18003fcaf  jnz     loc_18004014B
0x18003fcb5  mov     r14, [r15]
0x18003fcb8  mov     rcx, r14; hKey
0x18003fcbb  call    cs:__imp_RegQueryValueExW
0x18003fcc2  nop     dword ptr [rax+rax+00h]
0x18003fcc7  mov     esi, eax
0x18003fcc9  cmp     eax, 0EAh
0x18003fcce  jz      loc_1800400D3
0x18003fcd4  test    esi, esi
0x18003fcd6  jnz     short loc_18003FD1D
0x18003fcd8  mov     ecx, [rsp+0BB0h+Type]
0x18003fcdc  lea     eax, [rcx-1]
0x18003fcdf  cmp     eax, 1
0x18003fce2  ja      loc_18003FEE2
0x18003fce8  mov     r14d, 1
0x18003fcee  mov     ebx, [rsp+0BB0h+cbData]
0x18003fcf2  mov     r8d, r13d
0x18003fcf5  shr     ebx, 1
0x18003fcf7  lea     edx, [rbx-1]
0x18003fcfa  test    edx, edx
0x18003fcfc  js      short loc_18003FD14
0x18003fcfe  mov     rax, [rsp+0BB0h+var_B48]
0x18003fd03  cmp     [rax+rdx*2], r13w
0x18003fd08  jnz     short loc_18003FD14
0x18003fd0a  inc     r8d
0x18003fd0d  dec     edx
0x18003fd0f  cmp     r8d, r14d
0x18003fd12  jb      short loc_18003FCFA
0x18003fd14  cmp     r14d, r8d
0x18003fd17  ja      loc_1800405FD
0x18003fd1d  mov     eax, [rsp+0BB0h+Type]
0x18003fd21  mov     [rsp+0BB0h+var_B60], eax
0x18003fd25  test    esi, esi
0x18003fd27  jnz     loc_1800401FC
0x18003fd2d  mov     eax, [rsp+0BB0h+var_B60]
0x18003fd31  sub     eax, 1
0x18003fd34  jz      loc_1800402FA
0x18003fd3a  cmp     eax, 3
0x18003fd3d  jnz     loc_18003FE2C
0x18003fd43  cmp     dword ptr [r12+0Ch], 0Ch
0x18003fd49  lea     rdi, [r12+10h]
0x18003fd4e  jl      loc_180040095
0x18003fd54  mov     rbx, rdi
0x18003fd57  test    rbx, rbx
0x18003fd5a  jz      loc_180040345
0x18003fd60  mov     rcx, [r12]; hMem
0x18003fd64  cmp     rcx, rdi
0x18003fd67  jnz     loc_1800401EB
0x18003fd6d  mov     r9, [rsp+0BB0h+var_B48]
0x18003fd72  lea     r8, aD; "%d"
0x18003fd79  mov     [r12], rbx
0x18003fd7d  mov     edx, 0Ch; unsigned __int64
0x18003fd82  mov     dword ptr [r12+8], 0Ch
0x18003fd8b  mov     rcx, rbx; unsigned __int16 *
0x18003fd8e  mov     r9d, [r9]
0x18003fd91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fd96  test    eax, eax
0x18003fd98  jns     loc_18003FE31
0x18003fd9e  cmp     [rsp+0BB0h+var_B40], 4
0x18003fda3  jg      loc_1800402D0
0x18003fda9  lea     rax, [rsp+0BB0h+Data]
0x18003fdae  mov     [rsp+0BB0h+var_B40], 4
0x18003fdb6  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fdba  mov     [rsp+0BB0h+var_B48], rax
0x18003fdbf  call    cs:__imp_EnterCriticalSection
0x18003fdc6  nop     dword ptr [rax+rax+00h]
0x18003fdcb  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x18003fdcf  test    rcx, rcx
0x18003fdd2  jz      short loc_18003FDEC
0x18003fdd4  call    cs:__imp_RegCloseKey
0x18003fddb  nop     dword ptr [rax+rax+00h]
0x18003fde0  mov     rax, [rbp+0AB0h+var_B20]
0x18003fde4  mov     [rbp+0AB0h+hKey], r13
0x18003fde8  mov     [rax], r13w
0x18003fdec  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fdf0  call    cs:__imp_LeaveCriticalSection
0x18003fdf7  nop     dword ptr [rax+rax+00h]
0x18003fdfc  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fe00  call    cs:__imp_DeleteCriticalSection
0x18003fe07  nop     dword ptr [rax+rax+00h]
0x18003fe0c  cmp     [rbp+0AB0h+var_B18], 1
0x18003fe10  jle     short loc_18003FE22
0x18003fe12  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x18003fe16  call    cs:__imp_GlobalFree
0x18003fe1d  nop     dword ptr [rax+rax+00h]
0x18003fe22  mov     eax, 0Eh
0x18003fe27  jmp     loc_18003FEB7
0x18003fe2c  mov     esi, 64Ah
0x18003fe31  cmp     [rsp+0BB0h+var_B40], 4
0x18003fe36  jg      loc_180040291
0x18003fe3c  lea     rax, [rsp+0BB0h+Data]
0x18003fe41  mov     [rsp+0BB0h+var_B40], 4
0x18003fe49  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fe4d  mov     [rsp+0BB0h+var_B48], rax
0x18003fe52  call    cs:__imp_EnterCriticalSection
0x18003fe59  nop     dword ptr [rax+rax+00h]
0x18003fe5e  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x18003fe62  test    rcx, rcx
0x18003fe65  jz      short loc_18003FE7F
0x18003fe67  call    cs:__imp_RegCloseKey
0x18003fe6e  nop     dword ptr [rax+rax+00h]
0x18003fe73  mov     rcx, [rbp+0AB0h+var_B20]
0x18003fe77  mov     [rbp+0AB0h+hKey], r13
0x18003fe7b  mov     [rcx], r13w
0x18003fe7f  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18003fe83  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
