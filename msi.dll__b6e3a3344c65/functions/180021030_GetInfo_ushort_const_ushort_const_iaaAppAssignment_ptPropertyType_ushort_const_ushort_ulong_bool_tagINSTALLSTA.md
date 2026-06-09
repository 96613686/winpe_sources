# GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)

- ea: `0x180021030`
- end: `0x180022113`
- name: `?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z`
- size: `4323`
- prototype: ``
- caller_count: `7`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f190`
- `0x18001fd10`
- `0x180020d40`
- `0x18004b450`
- `0x1801247d8`
- `0x180131bec`
- `0x180212ca4`

## callees

- `0x180013264`
- `0x180013fe4`
- `0x180015690`
- `0x180015950`
- `0x18001ba40`
- `0x180021030`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x180025a18`
- `0x18002e3ec`
- `0x180031f90`
- `0x1800561c0`
- `0x1800efbf8`
- `0x1801140e4`
- `0x18011c130`
- `0x18025ab42`
- `0x18025ab80`
- `0x18025ac10`
- `0x18025c010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800219bd`
- `msvcrt!_itow_s` at `0x1800219bd`
- `ADVAPI32!RegQueryValueExW` at `0x180021593`
- `ADVAPI32!RegQueryValueExW` at `0x180021593`
- `ADVAPI32!RegCloseKey` at `0x1800211a6`
- `ADVAPI32!RegCloseKey` at `0x180021294`
- `ADVAPI32!RegCloseKey` at `0x180021442`
- `ADVAPI32!RegCloseKey` at `0x1800215fa`
- `ADVAPI32!RegCloseKey` at `0x18002165a`
- `ADVAPI32!RegCloseKey` at `0x1800211a6`
- `ADVAPI32!RegCloseKey` at `0x180021294`
- `ADVAPI32!RegCloseKey` at `0x180021442`
- `ADVAPI32!RegCloseKey` at `0x1800215fa`
- `ADVAPI32!RegCloseKey` at `0x18002165a`
- `KERNEL32!InitializeCriticalSection` at `0x1800210f7`
- `KERNEL32!InitializeCriticalSection` at `0x1800210f7`
- `KERNEL32!DeleteCriticalSection` at `0x1800211c6`
- `KERNEL32!DeleteCriticalSection` at `0x1800212b9`
- `KERNEL32!DeleteCriticalSection` at `0x18002161f`
- `KERNEL32!DeleteCriticalSection` at `0x1800211c6`
- `KERNEL32!DeleteCriticalSection` at `0x1800212b9`
- `KERNEL32!DeleteCriticalSection` at `0x18002161f`
- `KERNEL32!LeaveCriticalSection` at `0x1800211bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800212af`
- `KERNEL32!LeaveCriticalSection` at `0x18002145d`
- `KERNEL32!LeaveCriticalSection` at `0x180021615`
- `KERNEL32!LeaveCriticalSection` at `0x180021675`
- `KERNEL32!LeaveCriticalSection` at `0x1800211bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800212af`
- `KERNEL32!LeaveCriticalSection` at `0x18002145d`
- `KERNEL32!LeaveCriticalSection` at `0x180021615`
- `KERNEL32!LeaveCriticalSection` at `0x180021675`
- `KERNEL32!GetLastError` at `0x180021fdb`
- `KERNEL32!GetLastError` at `0x180021fdb`
- `KERNEL32!EnterCriticalSection` at `0x180021197`
- `KERNEL32!EnterCriticalSection` at `0x180021285`
- `KERNEL32!EnterCriticalSection` at `0x180021433`
- `KERNEL32!EnterCriticalSection` at `0x1800215eb`
- `KERNEL32!EnterCriticalSection` at `0x18002164b`
- `KERNEL32!EnterCriticalSection` at `0x180021197`
- `KERNEL32!EnterCriticalSection` at `0x180021285`
- `KERNEL32!EnterCriticalSection` at `0x180021433`
- `KERNEL32!EnterCriticalSection` at `0x1800215eb`
- `KERNEL32!EnterCriticalSection` at `0x18002164b`
- `KERNEL32!lstrlenW` at `0x1800219c7`
- `KERNEL32!lstrlenW` at `0x1800219eb`
- `KERNEL32!lstrlenW` at `0x180022088`
- `KERNEL32!lstrlenW` at `0x1800219c7`
- `KERNEL32!lstrlenW` at `0x1800219eb`
- `KERNEL32!lstrlenW` at `0x180022088`
- `KERNEL32!lstrlenA` at `0x180021937`
- `KERNEL32!lstrlenA` at `0x180021937`
- `KERNEL32!MultiByteToWideChar` at `0x180021975`
- `KERNEL32!MultiByteToWideChar` at `0x180022005`
- `KERNEL32!MultiByteToWideChar` at `0x180022047`
- `KERNEL32!MultiByteToWideChar` at `0x180021975`
- `KERNEL32!MultiByteToWideChar` at `0x180022005`
- `KERNEL32!MultiByteToWideChar` at `0x180022047`
- `KERNEL32!GlobalFree` at `0x1800211d6`
- `KERNEL32!GlobalFree` at `0x1800212c9`
- `KERNEL32!GlobalFree` at `0x1800214ea`
- `KERNEL32!GlobalFree` at `0x18002162f`
- `KERNEL32!GlobalFree` at `0x180021640`
- `KERNEL32!GlobalFree` at `0x1800217b8`
- `KERNEL32!GlobalFree` at `0x180021869`
- `KERNEL32!GlobalFree` at `0x1800218ea`
- `KERNEL32!GlobalFree` at `0x1800218f9`
- `KERNEL32!GlobalFree` at `0x180021916`
- `KERNEL32!GlobalFree` at `0x1800219fd`
- `KERNEL32!GlobalFree` at `0x180021a23`
- `KERNEL32!GlobalFree` at `0x180021a75`
- `KERNEL32!GlobalFree` at `0x180021b04`
- `KERNEL32!GlobalFree` at `0x180021b70`
- `KERNEL32!GlobalFree` at `0x180021bce`
- `KERNEL32!GlobalFree` at `0x180021caa`
- `KERNEL32!GlobalFree` at `0x180021d25`
- `KERNEL32!GlobalFree` at `0x180021d87`
- `KERNEL32!GlobalFree` at `0x180021eac`
- `KERNEL32!GlobalFree` at `0x180021ebb`
- `KERNEL32!GlobalFree` at `0x180021eca`
- `KERNEL32!GlobalFree` at `0x180021f7e`
- `KERNEL32!GlobalFree` at `0x180022059`
- `KERNEL32!GlobalFree` at `0x18002206b`
- `KERNEL32!GlobalFree` at `0x18002207d`
- `KERNEL32!GlobalFree` at `0x1800220f0`
- `KERNEL32!GlobalFree` at `0x1800211d6`
- `KERNEL32!GlobalFree` at `0x1800212c9`
- `KERNEL32!GlobalFree` at `0x1800214ea`
- `KERNEL32!GlobalFree` at `0x18002162f`
- `KERNEL32!GlobalFree` at `0x180021640`
- `KERNEL32!GlobalFree` at `0x1800217b8`
- `KERNEL32!GlobalFree` at `0x180021869`
- `KERNEL32!GlobalFree` at `0x1800218ea`
- `KERNEL32!GlobalFree` at `0x1800218f9`
- `KERNEL32!GlobalFree` at `0x180021916`
- `KERNEL32!GlobalFree` at `0x1800219fd`
- `KERNEL32!GlobalFree` at `0x180021a23`
- `KERNEL32!GlobalFree` at `0x180021a75`
- `KERNEL32!GlobalFree` at `0x180021b04`
- `KERNEL32!GlobalFree` at `0x180021b70`
- `KERNEL32!GlobalFree` at `0x180021bce`
- `KERNEL32!GlobalFree` at `0x180021caa`
- `KERNEL32!GlobalFree` at `0x180021d25`
- `KERNEL32!GlobalFree` at `0x180021d87`
- `KERNEL32!GlobalFree` at `0x180021eac`
- `KERNEL32!GlobalFree` at `0x180021ebb`
- `KERNEL32!GlobalFree` at `0x180021eca`
- `KERNEL32!GlobalFree` at `0x180021f7e`
- `KERNEL32!GlobalFree` at `0x180022059`
- `KERNEL32!GlobalFree` at `0x18002206b`
- `KERNEL32!GlobalFree` at `0x18002207d`
- `KERNEL32!GlobalFree` at `0x1800220f0`

## string_xrefs

- `0x18002139e`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800218bb`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18002133f`: `InstallProperties`

## pseudocode

```c
__int64 __fastcall GetInfo(
        unsigned __int16 *a1,
        const wchar_t *a2,
        int a3,
        int a4,
        __int64 a5,
        BYTE *a6,
        _DWORD *a7,
        char a8,
        int a9)
{
  unsigned int v9; // esi
  BYTE *v10; // r12
  unsigned __int16 *v11; // rbx
  __int64 v12; // rdi
  const wchar_t *v13; // r13
  const struct ProductPropertyW near *const *v14; // r15
  const struct ProductPropertyW near *v15; // rax
  int v16; // ecx
  int v17; // edx
  int v19; // ecx
  const WCHAR *v20; // r14
  unsigned int v21; // eax
  unsigned int ProductAssignmentType; // ebx
  unsigned int v23; // edi
  unsigned int v24; // edi
  const unsigned __int16 *v25; // rsi
  HGLOBAL v26; // rbx
  unsigned int v27; // eax
  const wchar_t *v28; // rax
  int v29; // eax
  _DWORD *v30; // rax
  int v31; // edi
  unsigned int v32; // ebx
  _DWORD *v33; // r14
  unsigned __int64 v34; // rcx
  HGLOBAL v35; // r9
  __int64 v36; // rax
  _WORD *v37; // rdx
  BYTE *v38; // rdx
  bool v39; // cc
  const unsigned __int16 *v40; // rdx
  int v41; // ecx
  int v42; // eax
  size_t *v43; // r8
  int *v44; // rdi
  unsigned int v45; // ecx
  int v46; // eax
  unsigned int v47; // eax
  const wchar_t *v48; // rax
  int v49; // edi
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v53; // [rsp+60h] [rbp-A0h]
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  _DWORD *v55; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+70h] [rbp-90h]
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  int v58; // [rsp+78h] [rbp-88h] BYREF
  int v59; // [rsp+80h] [rbp-80h]
  int i; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 *v61; // [rsp+88h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+B8h] [rbp-48h] BYREF
  HGLOBAL v64; // [rsp+E0h] [rbp-20h] BYREF
  int v65; // [rsp+E8h] [rbp-18h]
  int v66; // [rsp+ECh] [rbp-14h]
  wchar_t Buffer[64]; // [rsp+F0h] [rbp-10h] BYREF
  HGLOBAL v68; // [rsp+170h] [rbp+70h] BYREF
  int cchWideChar; // [rsp+178h] [rbp+78h]
  _BYTE v70[512]; // [rsp+180h] [rbp+80h] BYREF
  LPCCH lpMultiByteStr; // [rsp+380h] [rbp+280h]
  __int64 v72; // [rsp+388h] [rbp+288h]
  HGLOBAL v73; // [rsp+390h] [rbp+290h]
  int v74; // [rsp+398h] [rbp+298h]
  unsigned __int16 v75[320]; // [rsp+3A0h] [rbp+2A0h] BYREF
  HGLOBAL v76; // [rsp+620h] [rbp+520h]
  int v77; // [rsp+628h] [rbp+528h]
  unsigned __int16 v78[264]; // [rsp+630h] [rbp+530h] BYREF
  HGLOBAL v79; // [rsp+840h] [rbp+740h]
  int v80; // [rsp+848h] [rbp+748h]
  unsigned __int16 v81[1024]; // [rsp+850h] [rbp+750h] BYREF

  v9 = a3;
  v10 = a6;
  v11 = a1;
  v55 = a7;
  v59 = a4;
  v56 = a3;
  v61 = a1;
  v58 = a3;
  if ( !a1 )
    return 14;
  v12 = a5;
  if ( !a5 || a6 && !a7 )
    return 14;
  v13 = L"S-1-5-18";
  if ( a3 != 2 )
    v13 = a2;
  v53 = 0;
  for ( i = 0; ; i = 1 )
  {
    LODWORD(hKey.LockSemaphore) = 1;
    *(_OWORD *)&hKey.DebugInfo = 0;
    hKey.OwningThread = &hKey.SpinCount;
    LOWORD(hKey.SpinCount) = 0;
    InitializeCriticalSection(&CriticalSection);
    v68 = v70;
    v14 = &g_ProductPropertyTableW;
    cchWideChar = 256;
    v72 = v12;
    lpMultiByteStr = 0;
    if ( g_ProductPropertyTableW )
    {
      while ( 1 )
      {
        v15 = *v14;
        do
        {
          v16 = *(unsigned __int16 *)((char *)v15 + v12 - (unsigned __int64)*v14);
          v17 = *(unsigned __int16 *)v15 - v16;
          if ( v17 )
            break;
          v15 = (const struct ProductPropertyW near *)((char *)v15 + 2);
        }
        while ( v16 );
        if ( !v17 )
          break;
        v14 += 4;
        if ( !*v14 )
          goto LABEL_13;
      }
    }
    if ( !*v14 || (v59 & *((_DWORD *)v14 + 7)) == 0 )
    {
LABEL_13:
      cchWideChar = 256;
      v68 = v70;
      EnterCriticalSection(&CriticalSection);
      if ( hKey.DebugInfo )
      {
        RegCloseKey((HKEY)hKey.DebugInfo);
        hKey.DebugInfo = 0;
        *(_WORD *)hKey.OwningThread = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( SLODWORD(hKey.LockSemaphore) > 1 )
        GlobalFree(hKey.OwningThread);
      return 1608;
    }
    v19 = *((_DWORD *)v14 + 6);
    v20 = (const WCHAR *)*((_QWORD *)v14 + 1);
    if ( !v19 )
    {
      if ( a8 )
        goto LABEL_127;
      if ( v59 == 1 )
      {
        if ( v13 )
          v21 = OpenSpecificUsersAdvertisedSubKeyPacked(v9, v13, (WCHAR *)L"Products", v11, &hKey, v53);
        else
          v21 = OpenAdvertisedProductKeyPacked(v11, &hKey, v53, 0xFFFFFFFFLL, 0);
      }
      else
      {
        if ( v59 != 2 )
          goto LABEL_80;
        v21 = OpenAdvertisedPatchKeyPacked(v11, &hKey, v53, 0);
      }
      goto LABEL_25;
    }
    if ( v19 != 1 )
    {
      if ( v59 == 1 )
      {
        LOBYTE(v52) = v53;
        v21 = OpenSpecificSourceListKeyPacked(v11, 1, 0xFFFFFFFFLL, 0, &hKey, 0, v52);
      }
      else
      {
        if ( v59 != 2 )
          goto LABEL_80;
        LOBYTE(v52) = v53;
        v21 = OpenSpecificSourceListKeyPacked(v11, 2, 0xFFFFFFFFLL, 1, &hKey, 0, v52);
      }
      goto LABEL_25;
    }
    if ( a9 == 1 )
      goto LABEL_127;
    if ( v59 == 1 )
    {
      v77 = 260;
      v76 = v78;
      if ( (int)StringCchPrintfW(v78, 0x104u, L"%s\\%s\\%s", L"Products", v11, L"InstallProperties") < 0 )
      {
        if ( v77 > 260 )
          GlobalFree(v76);
        v23 = 1627;
        goto LABEL_81;
      }
      v24 = g_samRead;
      v25 = (const unsigned __int16 *)v76;
      v73 = v75;
      v74 = 318;
      if ( v13 )
      {
        ProductAssignmentType = StringCchPrintfW(
                                  v75,
                                  0x13Eu,
                                  L"%s\\%s",
                                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                  v13);
        goto LABEL_41;
      }
      cbData = 3;
      ProductAssignmentType = GetProductAssignmentType(v11, (enum iaaAppAssignment *)&cbData);
      if ( !ProductAssignmentType )
      {
        v64 = Buffer;
        v65 = 64;
        if ( cbData == 2 )
        {
          v40 = L"S-1-5-18";
          goto LABEL_109;
        }
        v40 = 0;
        if ( cbData > 1 )
        {
          if ( cbData != 3 )
          {
LABEL_109:
            ProductAssignmentType = StringCchPrintfW(
                                      v75,
                                      0x13Eu,
                                      L"%s\\%s",
                                      L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                      v40);
            if ( v65 <= 64 )
              goto LABEL_41;
            goto LABEL_110;
          }
          ProductAssignmentType = 2;
        }
        else
        {
          v66 = 64;
          ProductAssignmentType = GetCurrentUserStringSID(&v64);
          if ( !ProductAssignmentType )
          {
            v40 = (const unsigned __int16 *)v64;
            goto LABEL_109;
          }
          if ( v65 > 64 )
LABEL_110:
            GlobalFree(v64);
        }
      }
LABEL_41:
      if ( ProductAssignmentType )
      {
        if ( v74 <= 318 )
          goto LABEL_52;
      }
      else
      {
        v79 = v81;
        v80 = 1024;
        if ( (int)StringCchPrintfW(v81, 0x400u, L"%s\\%s", v73, v25) < 0 )
        {
          if ( v80 > 1024 )
            GlobalFree(v79);
          v79 = v81;
          v80 = 1024;
          if ( v74 > 318 )
            GlobalFree(v73);
          ProductAssignmentType = 1627;
          goto LABEL_52;
        }
        v26 = v79;
        if ( (v24 & 0x20019) != 0 && (v24 & 6) == 0 )
        {
          EnterCriticalSection(&CriticalSection);
          if ( hKey.DebugInfo )
          {
            RegCloseKey((HKEY)hKey.DebugInfo);
            hKey.DebugInfo = 0;
            *(_WORD *)hKey.OwningThread = 0;
          }
          LeaveCriticalSection(&CriticalSection);
          if ( !g_fWoW && g_fWinNT64 && (v24 & 0x100) == 0 )
            v24 |= 0x100u;
          v27 = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, _QWORD, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                  -2147483646,
                  v26,
                  0,
                  v24,
                  &hKey);
        }
        else
        {
          EnterCriticalSection(&CriticalSection);
          if ( hKey.DebugInfo )
          {
            RegCloseKey((HKEY)hKey.DebugInfo);
            hKey.DebugInfo = 0;
            *(_WORD *)hKey.OwningThread = 0;
          }
          LeaveCriticalSection(&CriticalSection);
          if ( !g_fWoW && g_fWinNT64 && (v24 & 0x100) == 0 )
            v24 |= 0x100u;
          v27 = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, _QWORD, _DWORD, unsigned int, _QWORD, struct _RTL_CRITICAL_SECTION *, _QWORD))RegCreateKeyAPI)(
                  -2147483646,
                  v26,
                  0,
                  0,
                  0,
                  v24,
                  0,
                  &hKey,
                  0);
        }
        ProductAssignmentType = v27;
        if ( !v27 && v53 )
          CRegHandleStatic::SetKey((CRegHandleStatic *)&hKey, HKEY_LOCAL_MACHINE, v25);
        if ( v80 > 1024 )
          GlobalFree(v79);
        v79 = v81;
        v80 = 1024;
        if ( v74 <= 318 )
        {
LABEL_52:
          if ( v77 > 260 )
            GlobalFree(v76);
          if ( !a8 && ProductAssignmentType == 2 )
          {
            if ( v13 )
              v47 = OpenSpecificUsersAdvertisedSubKeyPacked(v56, v13, (WCHAR *)L"Products", v61, &hKey, v53);
            else
              v47 = OpenAdvertisedProductKeyPacked(v61, &hKey, v53, 0xFFFFFFFFLL, 0);
            ProductAssignmentType = v47;
            if ( v47 )
            {
LABEL_27:
              v23 = ProductAssignmentType;
              if ( ProductAssignmentType == 2 )
              {
                if ( cchWideChar > 256 )
                  GlobalFree(v68);
                cchWideChar = 256;
                v68 = v70;
                EnterCriticalSection(&CriticalSection);
                if ( hKey.DebugInfo )
                {
                  RegCloseKey((HKEY)hKey.DebugInfo);
                  hKey.DebugInfo = 0;
                  *(_WORD *)hKey.OwningThread = 0;
                }
                LeaveCriticalSection(&CriticalSection);
                DeleteCriticalSection(&CriticalSection);
                if ( SLODWORD(hKey.LockSemaphore) > 1 )
                  GlobalFree(hKey.OwningThread);
                return 1605;
              }
              if ( ProductAssignmentType != 1608 )
                goto LABEL_81;
            }
LABEL_127:
            if ( cchWideChar > 256 )
              GlobalFree(v68);
            cchWideChar = 256;
            v68 = v70;
            CRegHandle::~CRegHandle((CRegHandle *)&hKey);
            return 1608;
          }
          if ( ProductAssignmentType )
            goto LABEL_27;
          v28 = (const wchar_t *)CApiConvertString::operator unsigned short const *(&v68);
          v29 = wcscmp_0(v28, L"LocalPackage");
          v9 = v56;
          if ( !v29 )
          {
            if ( v56 == 3 )
            {
              ProductAssignmentType = GetProductAssignmentType(v61, (enum iaaAppAssignment *)&v58);
              if ( ProductAssignmentType )
                goto LABEL_27;
              v9 = v58;
              v56 = v58;
            }
            if ( !v9 )
              v20 = L"ManagedLocalPackage";
          }
          goto LABEL_62;
        }
      }
      GlobalFree(v73);
      goto LABEL_52;
    }
    if ( v59 != 2 )
      goto LABEL_80;
    if ( ((v9 + 1) & 0xFFFFFFFB) != 0 )
    {
      LOBYTE(lpData) = v53;
      v21 = OpenInstalledPatchKeyPackedByAssignmentType(v11, v9, 0, &hKey, (_DWORD)lpData);
LABEL_25:
      ProductAssignmentType = v21;
      goto LABEL_26;
    }
    if ( lstrlenW(v11) != 32 )
    {
LABEL_80:
      v23 = 87;
LABEL_81:
      if ( cchWideChar > 256 )
        GlobalFree(v68);
      cchWideChar = 256;
      v68 = v70;
      CRegHandle::~CRegHandle((CRegHandle *)&hKey);
      return v23;
    }
    LOBYTE(lpData) = v53;
    v49 = 0;
    if ( (unsigned int)OpenInstalledPatchKeyPackedByAssignmentType(v11, 0, 0, &hKey, (_DWORD)lpData) )
    {
      v49 = 2;
      LOBYTE(lpDataa) = v53;
      ProductAssignmentType = OpenInstalledPatchKeyPackedByAssignmentType(v11, 2, 0, &hKey, lpDataa);
      if ( ProductAssignmentType )
        goto LABEL_27;
    }
    v48 = (const wchar_t *)CApiConvertString::operator unsigned short const *(&v68);
    if ( !wcscmp_0(v48, L"LocalPackage") && !v49 )
    {
      v20 = L"ManagedLocalPackage";
      ProductAssignmentType = 0;
LABEL_26:
      if ( ProductAssignmentType )
        goto LABEL_27;
    }
LABEL_62:
    v30 = v55;
    Type = 0;
    if ( !a6 && !v55 )
      goto LABEL_68;
    v31 = 0;
    while ( 1 )
    {
      cbData = 2 * *v30;
      v32 = RegQueryValueExW((HKEY)hKey.DebugInfo, v20, 0, &Type, a6, &cbData);
      if ( !v32 )
        break;
      if ( v32 == 234 )
      {
        if ( Type - 1 > 1 )
        {
          if ( Type == 4 )
            *v55 = 11;
        }
        else
        {
          *v55 = (cbData >> 1) - 1;
        }
        if ( cchWideChar <= 256 )
          goto LABEL_159;
LABEL_155:
        GlobalFree(v68);
LABEL_159:
        cchWideChar = 256;
        v68 = v70;
        CRegHandle::~CRegHandle((CRegHandle *)&hKey);
        return 234;
      }
      if ( v59 != 2 || wcscmp_0(v20, L"ManagedLocalPackage") || ((v9 + 1) & 0xFFFFFFFB) != 0 || (++v31, v31 >= 2) )
      {
        if ( v32 == 2 )
        {
          if ( a6 )
            *(_WORD *)a6 = 0;
          v39 = cchWideChar <= 256;
          *v55 = 0;
          if ( v39 )
          {
LABEL_168:
            cchWideChar = 256;
            v68 = v70;
            CRegHandle::~CRegHandle((CRegHandle *)&hKey);
            return 0;
          }
LABEL_163:
          GlobalFree(v68);
          goto LABEL_168;
        }
LABEL_121:
        if ( cchWideChar > 256 )
LABEL_122:
          GlobalFree(v68);
LABEL_105:
        cchWideChar = 256;
        v68 = v70;
        CRegHandle::~CRegHandle((CRegHandle *)&hKey);
        return v32;
      }
      v30 = v55;
      v20 = L"LocalPackage";
    }
    if ( Type == 4 )
    {
      if ( !a6 )
      {
        v39 = cchWideChar <= 256;
        *v55 = 11;
        if ( !v39 )
          goto LABEL_122;
        goto LABEL_105;
      }
      v41 = *(_DWORD *)a6;
      v64 = Buffer;
      v65 = 20;
      _itow_s(v41, Buffer, 0x14u, 10);
      v42 = lstrlenW((LPCWSTR)v64);
      v44 = v55;
      v45 = *v55;
      if ( *v55 >= (unsigned int)(v42 + 1) && v45 )
      {
        if ( v45 > 0x7FFFFFFF )
        {
          *(_WORD *)a6 = 0;
          goto LABEL_117;
        }
        if ( StringCopyWorkerW((STRSAFE_LPWSTR)a6, (unsigned int)*v55, v43, (STRSAFE_PCNZWCH)v64, (size_t)lpData) < 0 )
          goto LABEL_117;
        v32 = 0;
      }
      else
      {
LABEL_117:
        v32 = 234;
      }
      v46 = lstrlenW((LPCWSTR)v64);
      v39 = v65 <= 20;
      *v44 = v46;
      if ( !v39 )
        GlobalFree(v64);
      v65 = 20;
      v64 = Buffer;
      goto LABEL_121;
    }
    if ( (*((_BYTE *)v14 + 28) & 4) == 0 )
    {
      *v55 = (cbData >> 1) - 1;
      goto LABEL_68;
    }
    if ( !a6 )
    {
      v39 = cchWideChar <= 256;
      *v55 = 38;
      if ( v39 )
        goto LABEL_168;
      goto LABEL_163;
    }
    v33 = v55;
    if ( *v55 < 0x27u )
    {
      v39 = cchWideChar <= 256;
      *v55 = 38;
      if ( !v39 )
        goto LABEL_155;
      goto LABEL_159;
    }
    v65 = 39;
    v64 = Buffer;
    if ( (unsigned int)UnpackGUID(a6, Buffer, 39, 1) )
      break;
    if ( i )
    {
      DebugString(
        21,
        1u,
        1002,
        *((const unsigned __int16 **)v14 + 1),
        (const unsigned __int16 *)a6,
        (const unsigned __int16 *)hKey.OwningThread,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
      if ( v65 > 39 )
        GlobalFree(v64);
      v64 = Buffer;
      v65 = 39;
      if ( cchWideChar > 256 )
        GlobalFree(v68);
      cchWideChar = 256;
      v68 = v70;
      CRegHandle::~CRegHandle((CRegHandle *)&hKey);
      return 1610;
    }
    v53 = 1;
    if ( v65 > 39 )
      GlobalFree(v64);
    v64 = Buffer;
    v65 = 39;
    if ( cchWideChar > 256 )
      GlobalFree(v68);
    cchWideChar = 256;
    v68 = v70;
    CRegHandle::~CRegHandle((CRegHandle *)&hKey);
    v11 = v61;
    v12 = a5;
  }
  v34 = (unsigned int)*v33;
  v35 = v64;
  if ( !*v33 )
    goto LABEL_96;
  if ( v34 > 0x7FFFFFFF )
  {
    *(_WORD *)a6 = 0;
    goto LABEL_96;
  }
  v36 = 2147483646;
  v37 = v64;
  do
  {
    if ( !v36 )
      break;
    if ( !*v37 )
      break;
    *(_WORD *)v10 = *v37++;
    v10 += 2;
    --v36;
    --v34;
  }
  while ( v34 );
  v38 = v10 - 2;
  if ( v34 )
    v38 = v10;
  *(_WORD *)v38 = 0;
  if ( v34 )
  {
    v39 = v65 <= 39;
    *v33 = 38;
    if ( !v39 )
      GlobalFree(v35);
LABEL_68:
    if ( cchWideChar > 256 )
      GlobalFree(v68);
    cchWideChar = 256;
    v68 = v70;
    EnterCriticalSection(&CriticalSection);
    if ( hKey.DebugInfo )
    {
      RegCloseKey((HKEY)hKey.DebugInfo);
      hKey.DebugInfo = 0;
      *(_WORD *)hKey.OwningThread = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    if ( SLODWORD(hKey.LockSemaphore) > 1 )
      GlobalFree(hKey.OwningThread);
    return 0;
  }
  else
  {
LABEL_96:
    if ( v65 > 39 )
      GlobalFree(v35);
    v64 = Buffer;
    v65 = 39;
    if ( cchWideChar > 256 )
      GlobalFree(v68);
    cchWideChar = 256;
    v68 = v70;
    CRegHandle::~CRegHandle((CRegHandle *)&hKey);
    return 1627;
  }
}

```

## disassembly

```asm
0x180021030  push    rbp
0x180021032  push    rbx
0x180021033  push    rsi
0x180021034  push    rdi
0x180021035  push    r12
0x180021037  push    r14
0x180021039  lea     rbp, [rsp-0F68h]
0x180021041  mov     eax, 1068h
0x180021046  call    _alloca_probe
0x18002104b  sub     rsp, rax
0x18002104e  mov     rax, cs:__security_cookie
0x180021055  xor     rax, rsp
0x180021058  mov     [rbp+0F90h+var_40], rax
0x18002105f  mov     r14, [rbp+0F90h+arg_30]
0x180021066  mov     esi, r8d
0x180021069  mov     r12, [rbp+0F90h+arg_28]
0x180021070  mov     rbx, rcx
0x180021073  mov     [rsp+1090h+var_1028], r14
0x180021078  mov     [rbp+0F90h+var_1010], r9d
0x18002107c  mov     [rsp+1090h+var_1020], r8d
0x180021081  mov     [rbp+0F90h+var_1008], rcx
0x180021085  mov     [rsp+1090h+var_1018], r8d
0x18002108a  test    rcx, rcx
0x18002108d  jz      loc_18002192A
0x180021093  mov     rdi, [rbp+0F90h+arg_20]
0x18002109a  test    rdi, rdi
0x18002109d  jz      loc_18002192A
0x1800210a3  test    r12, r12
0x1800210a6  jnz     loc_180021921
0x1800210ac  mov     [rsp+1090h+arg_18], r13
0x1800210b4  cmp     r8d, 2
0x1800210b8  lea     r13, aS1518; "S-1-5-18"
0x1800210bf  mov     [rsp+1090h+var_30], r15
0x1800210c7  cmovnz  r13, rdx
0x1800210cb  mov     [rsp+1090h+var_1030], 0
0x1800210d0  xor     r14d, r14d
0x1800210d3  mov     [rbp+0F90h+var_100C], r14d
0x1800210d7  xorps   xmm0, xmm0
0x1800210da  mov     [rbp+0F90h+var_FE8], 1
0x1800210e1  lea     rax, [rbp+0F90h+var_FE0]
0x1800210e5  movdqa  xmmword ptr [rbp+0F90h+hKey], xmm0
0x1800210ea  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x1800210ee  mov     [rbp+0F90h+hMem], rax
0x1800210f2  mov     [rbp+0F90h+var_FE0], r14w
0x1800210f7  call    cs:__imp_InitializeCriticalSection
0x1800210fd  cmp     cs:?g_ProductPropertyTableW@@3QBUProductPropertyW@@B, 0; ProductPropertyW const near * const g_ProductPropertyTableW
0x180021105  lea     rax, [rbp+0F90h+var_F10]
0x18002110c  mov     [rbp+0F90h+var_F20], rax
0x180021110  lea     r15, ?g_ProductPropertyTableW@@3QBUProductPropertyW@@B; ProductPropertyW const near * const g_ProductPropertyTableW
0x180021117  mov     [rbp+0F90h+cchWideChar], 100h
0x18002111e  mov     r10, rdi
0x180021121  mov     [rbp+0F90h+var_D08], rdi
0x180021128  mov     r9, r14
0x18002112b  mov     [rbp+0F90h+lpMultiByteStr], r14
0x180021132  jz      loc_1800211E6
0x180021138  nop     dword ptr [rax+rax+00000000h]
0x180021140  test    r9, r9
0x180021143  jnz     loc_180021934
0x180021149  mov     r8, r10
0x18002114c  mov     rax, [r15]
0x18002114f  sub     r8, rax
0x180021152  movzx   edx, word ptr [rax]
0x180021155  movzx   ecx, word ptr [rax+r8]
0x18002115a  sub     edx, ecx
0x18002115c  jnz     short loc_180021166
0x18002115e  add     rax, 2
0x180021162  test    ecx, ecx
0x180021164  jnz     short loc_180021152
0x180021166  test    edx, edx
0x180021168  jz      short loc_1800211E6
0x18002116a  add     r15, 20h ; ' '
0x18002116e  cmp     qword ptr [r15], 0
0x180021172  jnz     short loc_180021140
0x180021174  cmp     [rbp+0F90h+cchWideChar], 100h
0x18002117b  jg      loc_1800218F5
0x180021181  lea     rax, [rbp+0F90h+var_F10]
0x180021188  mov     [rbp+0F90h+cchWideChar], 100h
0x18002118f  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x180021193  mov     [rbp+0F90h+var_F20], rax
0x180021197  call    cs:__imp_EnterCriticalSection
0x18002119d  mov     rcx, [rbp+0F90h+hKey]; hKey
0x1800211a1  test    rcx, rcx
0x1800211a4  jz      short loc_1800211B8
0x1800211a6  call    cs:__imp_RegCloseKey
0x1800211ac  mov     rax, [rbp+0F90h+hMem]
0x1800211b0  mov     [rbp+0F90h+hKey], r14
0x1800211b4  mov     [rax], r14w
0x1800211b8  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x1800211bc  call    cs:__imp_LeaveCriticalSection
0x1800211c2  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x1800211c6  call    cs:__imp_DeleteCriticalSection
0x1800211cc  cmp     [rbp+0F90h+var_FE8], 1
0x1800211d0  jle     short loc_1800211DC
0x1800211d2  mov     rcx, [rbp+0F90h+hMem]; hMem
0x1800211d6  call    cs:__imp_GlobalFree
0x1800211dc  mov     eax, 648h
0x1800211e1  jmp     loc_1800212D4
0x1800211e6  cmp     qword ptr [r15], 0
0x1800211ea  jz      short loc_180021174
0x1800211ec  mov     edx, [rbp+0F90h+var_1010]
0x1800211ef  test    [r15+1Ch], edx
0x1800211f3  jz      loc_180021174
0x1800211f9  mov     ecx, [r15+18h]
0x1800211fd  mov     r14, [r15+8]
0x180021201  test    ecx, ecx
0x180021203  jnz     loc_180021303
0x180021209  cmp     [rbp+0F90h+arg_38], cl
0x18002120f  jnz     loc_180021A68
0x180021215  cmp     edx, 1
0x180021218  jnz     loc_180021DDE
0x18002121e  test    r13, r13
0x180021221  jz      loc_180021ACA
0x180021227  movzx   eax, [rsp+1090h+var_1030]
0x18002122c  lea     r8, aProducts; "Products"
0x180021233  mov     byte ptr [rsp+1090h+lpcbData], al
0x180021237  mov     r9, rbx
0x18002123a  lea     rax, [rbp+0F90h+hKey]
0x18002123e  mov     rdx, r13
0x180021241  mov     ecx, esi
0x180021243  mov     [rsp+1090h+lpData], rax
0x180021248  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18002124d  mov     ebx, eax
0x18002124f  test    ebx, ebx
0x180021251  jz      loc_180021555
0x180021257  mov     edi, ebx
0x180021259  cmp     ebx, 2
0x18002125c  jnz     loc_180021F45
0x180021262  cmp     [rbp+0F90h+cchWideChar], 100h
0x180021269  jg      loc_18002163C
0x18002126f  lea     rax, [rbp+0F90h+var_F10]
0x180021276  mov     [rbp+0F90h+cchWideChar], 100h
0x18002127d  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x180021281  mov     [rbp+0F90h+var_F20], rax
0x180021285  call    cs:__imp_EnterCriticalSection
0x18002128b  mov     rcx, [rbp+0F90h+hKey]; hKey
0x18002128f  test    rcx, rcx
0x180021292  jz      short loc_1800212AB
0x180021294  call    cs:__imp_RegCloseKey
0x18002129a  mov     rax, [rbp+0F90h+hMem]
0x18002129e  xor     ecx, ecx
0x1800212a0  mov     [rbp+0F90h+hKey], 0
0x1800212a8  mov     [rax], cx
0x1800212ab  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x1800212af  call    cs:__imp_LeaveCriticalSection
0x1800212b5  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x1800212b9  call    cs:__imp_DeleteCriticalSection
0x1800212bf  cmp     [rbp+0F90h+var_FE8], 1
0x1800212c3  jle     short loc_1800212CF
0x1800212c5  mov     rcx, [rbp+0F90h+hMem]; hMem
0x1800212c9  call    cs:__imp_GlobalFree
0x1800212cf  mov     eax, 645h
0x1800212d4  mov     r13, [rsp+1090h+arg_18]
0x1800212dc  mov     r15, [rsp+1090h+var_30]
0x1800212e4  mov     rcx, [rbp+0F90h+var_40]
0x1800212eb  xor     rcx, rsp; StackCookie
0x1800212ee  call    __security_check_cookie
0x1800212f3  add     rsp, 1068h
0x1800212fa  pop     r14
0x1800212fc  pop     r12
0x1800212fe  pop     rdi
0x1800212ff  pop     rsi
0x180021300  pop     rbx
0x180021301  pop     rbp
0x180021302  retn
0x180021303  cmp     ecx, 1
0x180021306  jnz     loc_180021C30
0x18002130c  cmp     [rbp+0F90h+arg_40], ecx
0x180021312  jz      loc_180021A68
0x180021318  cmp     edx, ecx
0x18002131a  jnz     loc_1800216C6
0x180021320  lea     rax, [rbp+0F90h+var_A60]
0x180021327  mov     [rbp+0F90h+var_A68], 104h
0x180021331  mov     [rbp+0F90h+var_A70], rax
0x180021338  lea     r9, aProducts; "Products"
0x18002133f  lea     rax, aInstallpropert; "InstallProperties"
0x180021346  mov     edx, 104h; unsigned __int64
0x18002134b  mov     [rsp+1090h+lpcbData], rax
0x180021350  lea     r8, aSSS; "%s\\%s\\%s"
0x180021357  lea     rcx, [rbp+0F90h+var_A60]; unsigned __int16 *
0x18002135e  mov     [rsp+1090h+lpData], rbx
0x180021363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021368  test    eax, eax
0x18002136a  js      loc_180021F56
0x180021370  mov     edi, cs:?g_samRead@@3KA; ulong g_samRead
0x180021376  lea     rax, [rbp+0F90h+var_CF0]
0x18002137d  mov     rsi, [rbp+0F90h+var_A70]
0x180021384  mov     [rbp+0F90h+var_D00], rax
0x18002138b  mov     [rbp+0F90h+var_CF8], 13Eh
0x180021395  test    r13, r13
0x180021398  jz      loc_180021874
0x18002139e  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800213a5  mov     [rsp+1090h+lpData], r13
0x1800213aa  lea     r8, aSS_0; "%s\\%s"
0x1800213b1  mov     edx, 13Eh; unsigned __int64
0x1800213b6  lea     rcx, [rbp+0F90h+var_CF0]; unsigned __int16 *
0x1800213bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800213c2  mov     ebx, eax
0x1800213c4  test    ebx, ebx
0x1800213c6  jnz     loc_180021BB7
0x1800213cc  mov     r9, [rbp+0F90h+var_D00]
0x1800213d3  lea     rax, [rbp+0F90h+var_840]
0x1800213da  lea     r8, aSS_0; "%s\\%s"
0x1800213e1  mov     [rbp+0F90h+var_850], rax
0x1800213e8  mov     edx, 400h; unsigned __int64
0x1800213ed  mov     [rbp+0F90h+var_848], 400h
0x1800213f7  lea     rcx, [rbp+0F90h+var_840]; unsigned __int16 *
0x1800213fe  mov     [rsp+1090h+lpData], rsi
0x180021403  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021408  test    eax, eax
0x18002140a  js      loc_180021F89
0x180021410  mov     rbx, [rbp+0F90h+var_850]
0x180021417  test    edi, 20019h
0x18002141d  setnz   cl
0x180021420  test    dil, 6
0x180021424  setz    al
0x180021427  test    al, cl
0x180021429  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x18002142d  jz      loc_18002164B
0x180021433  call    cs:__imp_EnterCriticalSection
0x180021439  mov     rcx, [rbp+0F90h+hKey]; hKey
0x18002143d  test    rcx, rcx
0x180021440  jz      short loc_180021459
0x180021442  call    cs:__imp_RegCloseKey
0x180021448  mov     rax, [rbp+0F90h+hMem]
0x18002144c  xor     ecx, ecx
0x18002144e  mov     [rbp+0F90h+hKey], 0
0x180021456  mov     [rax], cx
0x180021459  lea     rcx, [rbp+0F90h+CriticalSection]; lpCriticalSection
0x18002145d  call    cs:__imp_LeaveCriticalSection
0x180021463  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18002146a  jz      loc_180021E2C
0x180021470  lea     rax, [rbp+0F90h+hKey]
0x180021474  mov     r9d, edi
0x180021477  mov     [rsp+1090h+lpData], rax
0x18002147c  xor     r8d, r8d
0x18002147f  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180021486  mov     rdx, rbx
0x180021489  mov     rcx, 0FFFFFFFF80000002h
0x180021490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021495  mov     ebx, eax
0x180021497  test    eax, eax
0x180021499  jz      loc_1800217FF
0x18002149f  cmp     [rbp+0F90h+var_848], 400h
0x1800214a9  jg      loc_180022076
0x1800214af  cmp     [rbp+0F90h+var_CF8], 13Eh
0x1800214b9  lea     rax, [rbp+0F90h+var_840]
0x1800214c0  mov     [rbp+0F90h+var_850], rax
0x1800214c7  mov     [rbp+0F90h+var_848], 400h
0x1800214d1  jg      loc_180021BC7
0x1800214d7  cmp     [rbp+0F90h+var_A68], 104h
0x1800214e1  jle     short loc_1800214F0
0x1800214e3  mov     rcx, [rbp+0F90h+var_A70]; hMem
0x1800214ea  call    cs:__imp_GlobalFree
0x1800214f0  cmp     [rbp+0F90h+arg_38], 0
0x1800214f7  jz      loc_180021A2E
0x1800214fd  test    ebx, ebx
0x1800214ff  jnz     loc_180021257
0x180021505  lea     rcx, [rbp+0F90h+var_F20]
0x180021509  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18002150e  mov     rcx, rax; String1
0x180021511  lea     rdx, aLocalpackage_0; "LocalPackage"
0x180021518  call    wcscmp_0
0x18002151d  mov     esi, [rsp+1090h+var_1020]
0x180021521  test    eax, eax
0x180021523  jnz     short loc_180021555
0x180021525  cmp     esi, 3
0x180021528  jnz     short loc_18002154A
0x18002152a  mov     rcx, [rbp+0F90h+var_1008]; unsigned __int16 *
0x18002152e  lea     rdx, [rsp+1090h+var_1018]; enum iaaAppAssignment *
0x180021533  call    ?GetProductAssignmentType@@YAKPEBGAEAW4iaaAppAssignment@@@Z; GetProductAssignmentType(ushort const *,iaaAppAssignment &)
0x180021538  mov     ebx, eax
0x18002153a  test    eax, eax
0x18002153c  jnz     loc_180021257
0x180021542  mov     esi, [rsp+1090h+var_1018]
0x180021546  mov     [rsp+1090h+var_1020], esi
0x18002154a  test    esi, esi
0x18002154c  jnz     short loc_180021555
0x18002154e  lea     r14, aManagedlocalpa; "ManagedLocalPackage"
0x180021555  mov     rax, [rsp+1090h+var_1028]
0x18002155a  mov     [rsp+1090h+Type], 0
0x180021562  test    r12, r12
0x180021565  jz      loc_180021904
0x18002156b  xor     edi, edi
0x18002156d  mov     eax, [rax]
0x18002156f  lea     r9, [rsp+1090h+Type]; lpType
0x180021574  mov     rcx, [rbp+0F90h+hKey]; hKey
0x180021578  add     eax, eax
0x18002157a  mov     [rsp+1090h+cbData], eax
0x18002157e  xor     r8d, r8d; lpReserved
0x180021581  lea     rax, [rsp+1090h+cbData]
0x180021586  mov     rdx, r14; lpValueName
0x180021589  mov     [rsp+1090h+lpcbData], rax; lpcbData
0x18002158e  mov     [rsp+1090h+lpData], r12; cchToCopy
0x180021593  call    cs:__imp_RegQueryValueExW
0x180021599  mov     ebx, eax
0x18002159b  test    eax, eax
0x18002159d  jnz     loc_180021BD9
0x1800215a3  cmp     [rsp+1090h+Type], 4
0x1800215a8  jz      loc_180021822
0x1800215ae  test    byte ptr [r15+1Ch], 4
  ... truncated ...
```
