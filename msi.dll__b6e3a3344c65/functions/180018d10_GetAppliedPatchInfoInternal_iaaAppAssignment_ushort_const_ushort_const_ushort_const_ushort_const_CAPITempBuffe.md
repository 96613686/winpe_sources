# GetAppliedPatchInfoInternal(iaaAppAssignment,ushort const *,ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,CRegHandle &)

- ea: `0x180018d10`
- end: `0x180019b59`
- name: `?GetAppliedPatchInfoInternal@@YAKW4iaaAppAssignment@@PEBG111AEAV?$CAPITempBufferRef@G@@AEAVCRegHandle@@@Z`
- size: `3657`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015ac0`
- `0x180017b28`
- `0x180046ec0`
- `0x1801368bc`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180018210`
- `0x180018d10`
- `0x180019b60`
- `0x180019bb4`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x180025560`
- `0x18002cfe0`
- `0x180071fdc`
- `0x18025ab42`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180019061`
- `ADVAPI32!RegQueryValueExW` at `0x18001947c`
- `ADVAPI32!RegQueryValueExW` at `0x180019490`
- `ADVAPI32!RegQueryValueExW` at `0x1800196ff`
- `ADVAPI32!RegQueryValueExW` at `0x180019061`
- `ADVAPI32!RegQueryValueExW` at `0x18001947c`
- `ADVAPI32!RegQueryValueExW` at `0x180019490`
- `ADVAPI32!RegQueryValueExW` at `0x1800196ff`
- `ADVAPI32!RegCloseKey` at `0x180018edd`
- `ADVAPI32!RegCloseKey` at `0x180018f8b`
- `ADVAPI32!RegCloseKey` at `0x18001916a`
- `ADVAPI32!RegCloseKey` at `0x1800191dc`
- `ADVAPI32!RegCloseKey` at `0x180018edd`
- `ADVAPI32!RegCloseKey` at `0x180018f8b`
- `ADVAPI32!RegCloseKey` at `0x18001916a`
- `ADVAPI32!RegCloseKey` at `0x1800191dc`
- `KERNEL32!InitializeCriticalSection` at `0x180018df4`
- `KERNEL32!InitializeCriticalSection` at `0x180019737`
- `KERNEL32!InitializeCriticalSection` at `0x180018df4`
- `KERNEL32!InitializeCriticalSection` at `0x180019737`
- `KERNEL32!DeleteCriticalSection` at `0x18001918a`
- `KERNEL32!DeleteCriticalSection` at `0x1800191fc`
- `KERNEL32!DeleteCriticalSection` at `0x18001918a`
- `KERNEL32!DeleteCriticalSection` at `0x1800191fc`
- `KERNEL32!LeaveCriticalSection` at `0x180018ef8`
- `KERNEL32!LeaveCriticalSection` at `0x180018fa5`
- `KERNEL32!LeaveCriticalSection` at `0x180019180`
- `KERNEL32!LeaveCriticalSection` at `0x1800191f2`
- `KERNEL32!LeaveCriticalSection` at `0x180018ef8`
- `KERNEL32!LeaveCriticalSection` at `0x180018fa5`
- `KERNEL32!LeaveCriticalSection` at `0x180019180`
- `KERNEL32!LeaveCriticalSection` at `0x1800191f2`
- `KERNEL32!EnterCriticalSection` at `0x180018ece`
- `KERNEL32!EnterCriticalSection` at `0x180018f7d`
- `KERNEL32!EnterCriticalSection` at `0x18001915b`
- `KERNEL32!EnterCriticalSection` at `0x1800191cd`
- `KERNEL32!EnterCriticalSection` at `0x180018ece`
- `KERNEL32!EnterCriticalSection` at `0x180018f7d`
- `KERNEL32!EnterCriticalSection` at `0x18001915b`
- `KERNEL32!EnterCriticalSection` at `0x1800191cd`
- `KERNEL32!GlobalAlloc` at `0x1800193ec`
- `KERNEL32!GlobalAlloc` at `0x1800195d4`
- `KERNEL32!GlobalAlloc` at `0x18001968c`
- `KERNEL32!GlobalAlloc` at `0x1800197c2`
- `KERNEL32!GlobalAlloc` at `0x18001985c`
- `KERNEL32!GlobalAlloc` at `0x1800193ec`
- `KERNEL32!GlobalAlloc` at `0x1800195d4`
- `KERNEL32!GlobalAlloc` at `0x18001968c`
- `KERNEL32!GlobalAlloc` at `0x1800197c2`
- `KERNEL32!GlobalAlloc` at `0x18001985c`
- `KERNEL32!GlobalFree` at `0x180018e63`
- `KERNEL32!GlobalFree` at `0x180018f43`
- `KERNEL32!GlobalFree` at `0x18001919a`
- `KERNEL32!GlobalFree` at `0x18001920c`
- `KERNEL32!GlobalFree` at `0x1800192ce`
- `KERNEL32!GlobalFree` at `0x180019407`
- `KERNEL32!GlobalFree` at `0x180019523`
- `KERNEL32!GlobalFree` at `0x180019595`
- `KERNEL32!GlobalFree` at `0x1800195c2`
- `KERNEL32!GlobalFree` at `0x1800195f5`
- `KERNEL32!GlobalFree` at `0x18001966f`
- `KERNEL32!GlobalFree` at `0x18001967a`
- `KERNEL32!GlobalFree` at `0x18001991e`
- `KERNEL32!GlobalFree` at `0x180019a24`
- `KERNEL32!GlobalFree` at `0x180019a7e`
- `KERNEL32!GlobalFree` at `0x180019a92`
- `KERNEL32!GlobalFree` at `0x180019a9e`
- `KERNEL32!GlobalFree` at `0x180019b43`
- `KERNEL32!GlobalFree` at `0x180019b4e`
- `KERNEL32!GlobalFree` at `0x180018e63`
- `KERNEL32!GlobalFree` at `0x180018f43`
- `KERNEL32!GlobalFree` at `0x18001919a`
- `KERNEL32!GlobalFree` at `0x18001920c`
- `KERNEL32!GlobalFree` at `0x1800192ce`
- `KERNEL32!GlobalFree` at `0x180019407`
- `KERNEL32!GlobalFree` at `0x180019523`
- `KERNEL32!GlobalFree` at `0x180019595`
- `KERNEL32!GlobalFree` at `0x1800195c2`
- `KERNEL32!GlobalFree` at `0x1800195f5`
- `KERNEL32!GlobalFree` at `0x18001966f`
- `KERNEL32!GlobalFree` at `0x18001967a`
- `KERNEL32!GlobalFree` at `0x18001991e`
- `KERNEL32!GlobalFree` at `0x180019a24`
- `KERNEL32!GlobalFree` at `0x180019a7e`
- `KERNEL32!GlobalFree` at `0x180019a92`
- `KERNEL32!GlobalFree` at `0x180019a9e`
- `KERNEL32!GlobalFree` at `0x180019b43`
- `KERNEL32!GlobalFree` at `0x180019b4e`

## string_xrefs

- `0x180018e38`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800192a3`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

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
  void *v22; // rcx
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
  DWORD v39; // esi
  DWORD v40; // esi
  BYTE *lpData; // r15
  HKEY v42; // r14
  unsigned int v43; // r14d
  unsigned int v44; // edx
  __int64 v45; // r8
  unsigned int v46; // r14d
  unsigned int v47; // ebx
  HGLOBAL v48; // rbx
  unsigned __int64 v49; // r14
  unsigned __int16 *v50; // rdi
  const unsigned __int16 *v51; // r8
  DWORD v52; // esi
  DWORD v53; // esi
  BYTE *v54; // r15
  __int64 v55; // r8
  int v56; // r14d
  unsigned int v57; // ebx
  int v58; // eax
  const wchar_t *v59; // rcx
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v62; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v63; // [rsp+58h] [rbp-A8h]
  const WCHAR *v64; // [rsp+60h] [rbp-A0h]
  HGLOBAL v65; // [rsp+68h] [rbp-98h] BYREF
  int v66; // [rsp+70h] [rbp-90h]
  int v67; // [rsp+74h] [rbp-8Ch]
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  HGLOBAL v70; // [rsp+90h] [rbp-70h]
  int v71; // [rsp+98h] [rbp-68h]
  __int16 v72; // [rsp+A0h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION hMem; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION v75; // [rsp+F8h] [rbp-8h] BYREF
  HGLOBAL v76; // [rsp+8E0h] [rbp+7E0h] BYREF
  int v77; // [rsp+8E8h] [rbp+7E8h]
  unsigned __int16 v78[320]; // [rsp+8F0h] [rbp+7F0h] BYREF

  v7 = L"Transforms";
  v8 = &off_18025D350;
  v9 = a4;
  v63 = a4;
  *(_QWORD *)cbData = a3;
  v64 = a2;
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
  v70 = &v72;
  v71 = 1;
  v72 = 0;
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
                             (unsigned __int16 *)&v76,
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
                  &v76,
                  L"Products",
                  v64,
                  L"Patches") >= 0 )
      {
        v20 = hMem.DebugInfo;
        EnterCriticalSection(&CriticalSection);
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
          *(_WORD *)v70 = 0;
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
      if ( hMem.LockCount > 260 )
        GlobalFree(hMem.DebugInfo);
LABEL_96:
      CurrentUserStringSID = 1627;
      goto LABEL_24;
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
    InitializeCriticalSection(&v75);
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
                               v55);
    }
    CRegHandle::~CRegHandle((CRegHandle *)&hMem);
    goto LABEL_24;
  }
  if ( v16 != 3 )
    goto LABEL_92;
  v77 = 318;
  v76 = v78;
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
                             v78,
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
    if ( (int)StringCchPrintfW((unsigned __int16 *)&hMem.OwningThread, 0x400u, L"%s\\%s\\%s", v76, L"Patches", v63) < 0 )
    {
      if ( hMem.LockCount > 1024 )
        GlobalFree(hMem.DebugInfo);
      hMem.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&hMem.OwningThread;
      hMem.LockCount = 1024;
      if ( v77 > 318 )
      {
        GlobalFree(v76);
        CurrentUserStringSID = 1627;
        goto LABEL_24;
      }
      goto LABEL_96;
    }
    v34 = hMem.DebugInfo;
    v35 = (HKEY *)CRegHandleStatic::operator&(hKey);
    CurrentUserStringSID = MsiRegOpen64bitKey(HKEY_LOCAL_MACHINE, &v34->Type, v36, g_samRead, v35);
    if ( hMem.LockCount > 1024 )
      GlobalFree(hMem.DebugInfo);
  }
LABEL_84:
  if ( v77 > 318 )
  {
    v22 = v76;
    goto LABEL_23;
  }
LABEL_24:
  if ( CurrentUserStringSID == 2 )
  {
    if ( !v17 )
      goto LABEL_204;
  }
  else if ( CurrentUserStringSID )
  {
    goto LABEL_211;
  }
  v9 = v63;
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
LABEL_211:
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
        return CurrentUserStringSID;
      }
    }
    if ( !IsPatchAppliedToProduct(v9, v64, *(wchar_t **)cbData, a1, 1) )
      goto LABEL_204;
    v37 = v8[2];
    if ( !v37 )
    {
      if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a6, 1, 0) )
        goto LABEL_158;
      **(_WORD **)a6 = 0;
      goto LABEL_129;
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
        goto LABEL_158;
      }
      goto LABEL_129;
    }
LABEL_92:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1627;
  }
LABEL_34:
  v25 = v8[1];
  v62 = 0;
  if ( !v25 )
    v25 = v9;
  if ( !a1 )
  {
    v58 = wcscmp_0(*v8, L"LocalPackage");
    v59 = L"ManagedLocalPackage";
    if ( v58 )
      v59 = v25;
    v25 = v59;
  }
  v66 = 4;
  v65 = Data;
  v67 = 4;
  cbData[0] = 8;
  Type = 0;
  if ( v16 != 4 )
  {
    v42 = hKey[0];
    v27 = RegQueryValueExW(hKey[0], v25, 0, &Type, Data, cbData);
    if ( v27 != 234 )
      goto LABEL_106;
    v52 = cbData[0];
    if ( Type - 1 > 1 )
    {
      if ( Type != 7 )
        goto LABEL_146;
      v52 = cbData[0] + 4;
    }
    else
    {
      v52 = cbData[0] + 2;
    }
    cbData[0] = v52;
LABEL_146:
    v53 = v52 >> 1;
    if ( (int)v53 > v67 )
    {
      v54 = (BYTE *)GlobalAlloc(0, 2LL * v53);
      if ( !v54 )
      {
        v27 = 14;
        goto LABEL_48;
      }
    }
    else
    {
      v54 = Data;
    }
    if ( v65 != Data )
      GlobalFree(v65);
    v65 = v54;
    v66 = v53;
    v27 = RegQueryValueExW(v42, v25, 0, &v62, v54, cbData);
LABEL_106:
    if ( !v27 )
    {
      if ( Type - 1 > 1 )
      {
        if ( Type != 7 )
          goto LABEL_47;
        v43 = 2;
      }
      else
      {
        v43 = 1;
      }
      v44 = 0;
      v45 = (cbData[0] >> 1) - 1;
      do
      {
        if ( (int)v45 < 0 )
          break;
        if ( *((_WORD *)v65 + v45) )
          break;
        ++v44;
        v45 = (unsigned int)(v45 - 1);
      }
      while ( v44 < v43 );
      if ( v43 <= v44 )
        goto LABEL_47;
      v46 = v43 - v44;
      v47 = v46 + (cbData[0] >> 1);
      if ( v47 <= v66 || (LOBYTE(v45) = 1, (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&v65, v47, v45)) )
      {
        for ( ; v46; --v46 )
          *((_WORD *)v65 + v47 - v46) = 0;
        goto LABEL_47;
      }
      v27 = 14;
      goto LABEL_48;
    }
LABEL_47:
    v62 = Type;
    goto LABEL_48;
  }
  v26 = *(HKEY *)a7;
  v27 = RegQueryValueExW(*(HKEY *)a7, v25, 0, &Type, Data, cbData);
  if ( v27 == 234 )
  {
    v39 = cbData[0];
    if ( Type - 1 > 1 )
    {
      if ( Type != 7 )
        goto LABEL_100;
      v39 = cbData[0] + 4;
    }
    else
    {
      v39 = cbData[0] + 2;
    }
    cbData[0] = v39;
LABEL_100:
    v40 = v39 >> 1;
    if ( (int)v40 > v67 )
    {
      lpData = (BYTE *)GlobalAlloc(0, 2LL * v40);
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
    if ( v65 != Data )
      GlobalFree(v65);
    v65 = lpData;
    v66 = v40;
    v27 = RegQueryValueExW(v26, v25, 0, &v62, lpData, cbData);
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
    if ( *((_WORD *)v65 + v30) )
      break;
    v29 = (unsigned int)(v29 + 1);
    v30 = (unsigned int)(v30 - 1);
  }
  while ( (unsigned int)v29 < v28 );
  if ( v28 <= (unsigned int)v29 )
    goto LABEL_47;
  v56 = v28 - v29;
  v57 = v56 + (cbData[0] >> 1);
  if ( v57 <= v66 || (LOBYTE(v29) = 1, (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&v65, v57, v29)) )
  {
    for ( ; v56; --v56 )
      *((_WORD *)v65 + v57 - v56) = 0;
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
          v48 = GlobalAlloc(0, 2u);
        else
          v48 = (HGLOBAL)(a6 + 16);
        if ( !v48 )
        {
          if ( v66 <= 4 )
            goto LABEL_157;
          goto LABEL_141;
        }
        if ( *(_QWORD *)a6 != a6 + 16 )
          GlobalFree(*(HGLOBAL *)a6);
        *(_QWORD *)a6 = v48;
        *(_DWORD *)(a6 + 8) = 1;
      }
      **(_WORD **)a6 = 0;
      if ( v66 > 4 )
        GlobalFree(v65);
      v66 = 4;
      v65 = Data;
LABEL_129:
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      return 0;
    }
    if ( v66 > 4 )
      GlobalFree(v65);
    v66 = 4;
    v65 = Data;
LABEL_204:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1647;
  }
  if ( v62 == 1 )
  {
    v49 = v66;
    if ( v66 > *(_DWORD *)(a6 + 12) )
      v50 = (unsigned __int16 *)GlobalAlloc(0, 2LL * v66);
    else
      v50 = (unsigned __int16 *)(a6 + 16);
    if ( v50 )
    {
      if ( *(_QWORD *)a6 != a6 + 16 )
        GlobalFree(*(HGLOBAL *)a6);
      v51 = (const unsigned __int16 *)v65;
      *(_QWORD *)a6 = v50;
      *(_DWORD *)(a6 + 8) = v49;
      if ( (int)StringCchCopyW(v50, v49, v51) >= 0 )
        goto LABEL_65;
    }
LABEL_140:
    if ( v66 <= 4 )
    {
LABEL_157:
      v66 = 4;
      v65 = Data;
LABEL_158:
      CRegHandle::~CRegHandle((CRegHandle *)hKey);
      return 14;
    }
LABEL_141:
    GlobalFree(v65);
    goto LABEL_157;
  }
  if ( v62 != 4 )
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
    goto LABEL_140;
  if ( *(_QWORD *)a6 != a6 + 16 )
    GlobalFree(*(HGLOBAL *)a6);
  v32 = (unsigned int *)v65;
  *(_QWORD *)a6 = v31;
  *(_DWORD *)(a6 + 8) = 12;
  if ( (int)StringCchPrintfW(v31, 0xCu, L"%d", *v32) < 0 )
  {
    if ( v66 > 4 )
      GlobalFree(v65);
    v66 = 4;
    v65 = Data;
    EnterCriticalSection(&CriticalSection);
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
      *(_WORD *)v70 = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    if ( v71 > 1 )
      GlobalFree(v70);
    return 14;
  }
LABEL_65:
  if ( v66 > 4 )
    GlobalFree(v65);
  v66 = 4;
  v65 = Data;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)v70 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v71 > 1 )
    GlobalFree(v70);
  return v27;
}

```

## disassembly

```asm
0x180018d10  push    rbp
0x180018d12  push    rbx
0x180018d13  push    rdi
0x180018d14  push    r12
0x180018d16  push    r13
0x180018d18  push    r14
0x180018d1a  push    r15
0x180018d1c  lea     rbp, [rsp-0A80h]
0x180018d24  sub     rsp, 0B80h
0x180018d2b  mov     rax, cs:__security_cookie
0x180018d32  xor     rax, rsp
0x180018d35  mov     [rbp+0AB0h+var_40], rax
0x180018d3c  mov     rax, cs:off_18025D350; "Transforms"
0x180018d43  lea     rdi, off_18025D350; "Transforms"
0x180018d4a  mov     r12, [rbp+0AB0h+arg_28]
0x180018d51  mov     r14, r9
0x180018d54  mov     r15, [rbp+0AB0h+arg_30]
0x180018d5b  mov     rbx, rdx
0x180018d5e  mov     [rsp+0BB0h+var_B58], r9
0x180018d63  mov     r13d, ecx
0x180018d66  mov     qword ptr [rsp+0BB0h+cbData], r8
0x180018d6b  mov     [rsp+0BB0h+var_B50], rdx
0x180018d70  test    rax, rax
0x180018d73  jz      short loc_180018DBF
0x180018d75  mov     r9, [rbp+0AB0h+arg_20]
0x180018d7c  nop     dword ptr [rax+00h]
0x180018d80  mov     r8, r9
0x180018d83  sub     r8, rax
0x180018d86  nop     word ptr [rax+rax+00000000h]
0x180018d90  movzx   edx, word ptr [rax]
0x180018d93  movzx   ecx, word ptr [rax+r8]
0x180018d98  sub     edx, ecx
0x180018d9a  jnz     short loc_180018DA4
0x180018d9c  add     rax, 2
0x180018da0  test    ecx, ecx
0x180018da2  jnz     short loc_180018D90
0x180018da4  test    edx, edx
0x180018da6  jz      short loc_180018DBF
0x180018da8  mov     rax, [rdi+20h]
0x180018dac  add     rdi, 20h ; ' '
0x180018db0  test    rax, rax
0x180018db3  jnz     short loc_180018D80
0x180018db5  mov     eax, 648h
0x180018dba  jmp     loc_18001921C
0x180018dbf  cmp     qword ptr [rdi], 0
0x180018dc3  jz      short loc_180018DB5
0x180018dc5  test    byte ptr [rdi+1Ch], 2
0x180018dc9  jz      short loc_180018DB5
0x180018dcb  lea     rax, [rbp+0AB0h+var_B10]
0x180018dcf  mov     [rsp+0BB0h+arg_0], rsi
0x180018dd7  mov     [rbp+0AB0h+var_B20], rax
0x180018ddb  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180018ddf  xor     eax, eax
0x180018de1  mov     [rbp+0AB0h+var_B18], 1
0x180018de8  xorps   xmm0, xmm0
0x180018deb  mov     [rbp+0AB0h+var_B10], ax
0x180018def  movdqa  xmmword ptr [rbp+0AB0h+hKey], xmm0
0x180018df4  call    cs:__imp_InitializeCriticalSection
0x180018dfa  mov     esi, [rdi+18h]
0x180018dfd  cmp     esi, 4
0x180018e00  jnz     loc_180019252
0x180018e06  cmp     qword ptr [r15], 0
0x180018e0a  jnz     loc_180018FED
0x180018e10  mov     dword ptr [rbp+0AB0h+hMem+8], 40h ; '@'
0x180018e17  lea     rax, [rbp+0AB0h+var_AD0]
0x180018e1b  mov     [rbp+0AB0h+hMem], rax
0x180018e1f  mov     r14b, 1
0x180018e22  cmp     r13d, 2
0x180018e26  jnz     loc_180019800
0x180018e2c  lea     rcx, aS1518; "S-1-5-18"
0x180018e33  mov     [rsp+0BB0h+lpData], rcx
0x180018e38  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018e3f  lea     rcx, [rbp+0AB0h+var_2D0]; unsigned __int16 *
0x180018e46  mov     edx, 13Eh; unsigned __int64
0x180018e4b  lea     r8, aSS_0; "%s\\%s"
0x180018e52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018e57  cmp     dword ptr [rbp+0AB0h+hMem+8], 40h ; '@'
0x180018e5b  mov     ebx, eax
0x180018e5d  jle     short loc_180018E69
0x180018e5f  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x180018e63  call    cs:__imp_GlobalFree
0x180018e69  test    ebx, ebx
0x180018e6b  jnz     loc_180018F49
0x180018e71  lea     rax, [rbp+0AB0h+var_AD0]
0x180018e75  mov     dword ptr [rbp+0AB0h+hMem+8], 104h
0x180018e7c  mov     [rbp+0AB0h+hMem], rax
0x180018e80  lea     r9, [rbp+0AB0h+var_2D0]
0x180018e87  lea     rax, ValueName; "Patches"
0x180018e8e  mov     edx, 104h; unsigned __int64
0x180018e93  mov     [rsp+0BB0h+var_B80], rax
0x180018e98  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180018e9f  mov     rax, [rsp+0BB0h+var_B50]
0x180018ea4  lea     rcx, [rbp+0AB0h+var_AD0]; unsigned __int16 *
0x180018ea8  mov     [rsp+0BB0h+lpcbData], rax
0x180018ead  lea     rax, aProducts; "Products"
0x180018eb4  mov     [rsp+0BB0h+lpData], rax
0x180018eb9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018ebe  test    eax, eax
0x180018ec0  js      loc_1800193FA
0x180018ec6  mov     rbx, [rbp+0AB0h+hMem]
0x180018eca  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180018ece  call    cs:__imp_EnterCriticalSection
0x180018ed4  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180018ed8  test    rcx, rcx
0x180018edb  jz      short loc_180018EF4
0x180018edd  call    cs:__imp_RegCloseKey
0x180018ee3  mov     rax, [rbp+0AB0h+var_B20]
0x180018ee7  xor     ecx, ecx
0x180018ee9  mov     [rbp+0AB0h+hKey], 0
0x180018ef1  mov     [rax], cx
0x180018ef4  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180018ef8  call    cs:__imp_LeaveCriticalSection
0x180018efe  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x180018f05  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180018f0c  jz      loc_18001989A
0x180018f12  lea     rax, [rbp+0AB0h+hKey]
0x180018f16  xor     r8d, r8d
0x180018f19  mov     [rsp+0BB0h+lpData], rax
0x180018f1e  mov     rdx, rbx
0x180018f21  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180018f28  mov     rcx, 0FFFFFFFF80000002h
0x180018f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f34  cmp     dword ptr [rbp+0AB0h+hMem+8], 104h
0x180018f3b  mov     ebx, eax
0x180018f3d  jle     short loc_180018F49
0x180018f3f  mov     rcx, [rbp+0AB0h+hMem]; hMem
0x180018f43  call    cs:__imp_GlobalFree
0x180018f49  cmp     ebx, 2
0x180018f4c  jz      loc_180019AA9
0x180018f52  test    ebx, ebx
0x180018f54  jnz     loc_180019AB3
0x180018f5a  mov     r14, [rsp+0BB0h+var_B58]
0x180018f5f  cmp     esi, 4
0x180018f62  jnz     loc_180018FED
0x180018f68  cmp     qword ptr [r15], 0
0x180018f6c  jnz     short loc_180018FED
0x180018f6e  cmp     [rbp+0AB0h+hKey], 0
0x180018f73  jz      loc_180019378
0x180018f79  lea     rcx, [r15+28h]; lpCriticalSection
0x180018f7d  call    cs:__imp_EnterCriticalSection
0x180018f83  mov     rcx, [r15]; hKey
0x180018f86  test    rcx, rcx
0x180018f89  jz      short loc_180018FA1
0x180018f8b  call    cs:__imp_RegCloseKey
0x180018f91  mov     qword ptr [r15], 0
0x180018f98  xor     eax, eax
0x180018f9a  mov     rdx, [r15+10h]
0x180018f9e  mov     [rdx], ax
0x180018fa1  lea     rcx, [r15+28h]; lpCriticalSection
0x180018fa5  call    cs:__imp_LeaveCriticalSection
0x180018fab  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x180018fb2  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180018fb9  jz      loc_180019878
0x180018fbf  mov     rcx, [rbp+0AB0h+hKey]
0x180018fc3  xor     r8d, r8d
0x180018fc6  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180018fcd  mov     rdx, r14
0x180018fd0  mov     [rsp+0BB0h+lpData], r15
0x180018fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fda  mov     ebx, eax
0x180018fdc  cmp     eax, 2
0x180018fdf  jz      loc_180019378
0x180018fe5  test    eax, eax
0x180018fe7  jnz     loc_180019AB3
0x180018fed  mov     rbx, [rdi+8]
0x180018ff1  test    rbx, rbx
0x180018ff4  mov     [rsp+0BB0h+var_B60], 0
0x180018ffc  cmovz   rbx, r14
0x180019000  test    r13d, r13d
0x180019003  jz      loc_180019B1F
0x180019009  lea     rax, [rsp+0BB0h+Data]
0x18001900e  mov     [rsp+0BB0h+var_B40], 4
0x180019016  mov     [rsp+0BB0h+var_B48], rax
0x18001901b  lea     r9, [rsp+0BB0h+Type]; lpType
0x180019020  lea     rax, [rsp+0BB0h+cbData]
0x180019025  mov     [rsp+0BB0h+var_B3C], 4
0x18001902d  mov     [rsp+0BB0h+lpcbData], rax; lpcbData
0x180019032  xor     r13d, r13d
0x180019035  xor     r8d, r8d; lpReserved
0x180019038  mov     [rsp+0BB0h+cbData], 8
0x180019040  mov     [rsp+0BB0h+Type], r13d
0x180019045  lea     rax, [rsp+0BB0h+Data]
0x18001904a  mov     [rsp+0BB0h+lpData], rax; lpData
0x18001904f  mov     rdx, rbx; lpValueName
0x180019052  cmp     esi, 4
0x180019055  jnz     loc_180019489
0x18001905b  mov     r14, [r15]
0x18001905e  mov     rcx, r14; hKey
0x180019061  call    cs:__imp_RegQueryValueExW
0x180019067  mov     esi, eax
0x180019069  cmp     eax, 0EAh
0x18001906e  jz      loc_180019417
0x180019074  test    esi, esi
0x180019076  jnz     short loc_1800190BD
0x180019078  mov     ecx, [rsp+0BB0h+Type]
0x18001907c  lea     eax, [rcx-1]
0x18001907f  cmp     eax, 1
0x180019082  ja      loc_18001923E
0x180019088  mov     r14d, 1
0x18001908e  mov     ebx, [rsp+0BB0h+cbData]
0x180019092  mov     r8d, r13d
0x180019095  shr     ebx, 1
0x180019097  lea     edx, [rbx-1]
0x18001909a  test    edx, edx
0x18001909c  js      short loc_1800190B4
0x18001909e  mov     rax, [rsp+0BB0h+var_B48]
0x1800190a3  cmp     [rax+rdx*2], r13w
0x1800190a8  jnz     short loc_1800190B4
0x1800190aa  inc     r8d
0x1800190ad  dec     edx
0x1800190af  cmp     r8d, r14d
0x1800190b2  jb      short loc_18001909A
0x1800190b4  cmp     r14d, r8d
0x1800190b7  ja      loc_1800198ED
0x1800190bd  mov     eax, [rsp+0BB0h+Type]
0x1800190c1  mov     [rsp+0BB0h+var_B60], eax
0x1800190c5  test    esi, esi
0x1800190c7  jnz     loc_18001952E
0x1800190cd  mov     eax, [rsp+0BB0h+var_B60]
0x1800190d1  sub     eax, 1
0x1800190d4  jz      loc_180019614
0x1800190da  cmp     eax, 3
0x1800190dd  jnz     loc_1800191A7
0x1800190e3  cmp     dword ptr [r12+0Ch], 0Ch
0x1800190e9  lea     rdi, [r12+10h]
0x1800190ee  jl      loc_1800193E5
0x1800190f4  mov     rbx, rdi
0x1800190f7  test    rbx, rbx
0x1800190fa  jz      loc_18001965F
0x180019100  mov     rcx, [r12]; hMem
0x180019104  cmp     rcx, rdi
0x180019107  jnz     loc_180019523
0x18001910d  mov     r9, [rsp+0BB0h+var_B48]
0x180019112  lea     r8, aD; "%d"
0x180019119  mov     [r12], rbx
0x18001911d  mov     edx, 0Ch; unsigned __int64
0x180019122  mov     dword ptr [r12+8], 0Ch
0x18001912b  mov     rcx, rbx; unsigned __int16 *
0x18001912e  mov     r9d, [r9]
0x180019131  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019136  test    eax, eax
0x180019138  jns     short loc_1800191AC
0x18001913a  cmp     [rsp+0BB0h+var_B40], 4
0x18001913f  jg      loc_1800195F0
0x180019145  lea     rax, [rsp+0BB0h+Data]
0x18001914a  mov     [rsp+0BB0h+var_B40], 4
0x180019152  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180019156  mov     [rsp+0BB0h+var_B48], rax
0x18001915b  call    cs:__imp_EnterCriticalSection
0x180019161  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x180019165  test    rcx, rcx
0x180019168  jz      short loc_18001917C
0x18001916a  call    cs:__imp_RegCloseKey
0x180019170  mov     rax, [rbp+0AB0h+var_B20]
0x180019174  mov     [rbp+0AB0h+hKey], r13
0x180019178  mov     [rax], r13w
0x18001917c  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x180019180  call    cs:__imp_LeaveCriticalSection
0x180019186  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x18001918a  call    cs:__imp_DeleteCriticalSection
0x180019190  cmp     [rbp+0AB0h+var_B18], 1
0x180019194  jle     short loc_1800191A0
0x180019196  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x18001919a  call    cs:__imp_GlobalFree
0x1800191a0  mov     eax, 0Eh
0x1800191a5  jmp     short loc_180019214
0x1800191a7  mov     esi, 64Ah
0x1800191ac  cmp     [rsp+0BB0h+var_B40], 4
0x1800191b1  jg      loc_1800195BD
0x1800191b7  lea     rax, [rsp+0BB0h+Data]
0x1800191bc  mov     [rsp+0BB0h+var_B40], 4
0x1800191c4  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800191c8  mov     [rsp+0BB0h+var_B48], rax
0x1800191cd  call    cs:__imp_EnterCriticalSection
0x1800191d3  mov     rcx, [rbp+0AB0h+hKey]; hKey
0x1800191d7  test    rcx, rcx
0x1800191da  jz      short loc_1800191EE
0x1800191dc  call    cs:__imp_RegCloseKey
0x1800191e2  mov     rcx, [rbp+0AB0h+var_B20]
0x1800191e6  mov     [rbp+0AB0h+hKey], r13
0x1800191ea  mov     [rcx], r13w
0x1800191ee  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800191f2  call    cs:__imp_LeaveCriticalSection
0x1800191f8  lea     rcx, [rbp+0AB0h+CriticalSection]; lpCriticalSection
0x1800191fc  call    cs:__imp_DeleteCriticalSection
0x180019202  cmp     [rbp+0AB0h+var_B18], 1
0x180019206  jle     short loc_180019212
0x180019208  mov     rcx, [rbp+0AB0h+var_B20]; hMem
0x18001920c  call    cs:__imp_GlobalFree
0x180019212  mov     eax, esi
0x180019214  mov     rsi, [rsp+0BB0h+arg_0]
0x18001921c  mov     rcx, [rbp+0AB0h+var_40]
0x180019223  xor     rcx, rsp; StackCookie
0x180019226  call    __security_check_cookie
0x18001922b  add     rsp, 0B80h
0x180019232  pop     r15
0x180019234  pop     r14
0x180019236  pop     r13
0x180019238  pop     r12
0x18001923a  pop     rdi
  ... truncated ...
```
