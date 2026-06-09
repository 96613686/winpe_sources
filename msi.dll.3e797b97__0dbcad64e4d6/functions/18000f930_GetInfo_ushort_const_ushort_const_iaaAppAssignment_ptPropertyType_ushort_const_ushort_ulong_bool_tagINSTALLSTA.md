# GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)

- ea: `0x18000f930`
- end: `0x180010aad`
- name: `?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z`
- size: `4477`
- prototype: ``
- caller_count: `7`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e5b0`
- `0x18000f600`
- `0x180044560`
- `0x1800490c0`
- `0x1800e7920`
- `0x18013773c`
- `0x18021c600`

## callees

- `0x18000c4bc`
- `0x18000f930`
- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x180039bc4`
- `0x18003a560`
- `0x18003bd60`
- `0x18003c030`
- `0x1800433c0`
- `0x18004c8f0`
- `0x18004cbfc`
- `0x1800560e0`
- `0x1800a57b0`
- `0x1800b8f60`
- `0x18011b27c`
- `0x180121fc0`
- `0x180265202`
- `0x180265240`
- `0x1802652d0`
- `0x180266010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800102d0`
- `msvcrt!_itow_s` at `0x1800102d0`
- `ADVAPI32!RegQueryValueExW` at `0x18000fe98`
- `ADVAPI32!RegQueryValueExW` at `0x18000fe98`
- `ADVAPI32!RegCloseKey` at `0x18000fb67`
- `ADVAPI32!RegCloseKey` at `0x18000fd34`
- `ADVAPI32!RegCloseKey` at `0x18000ff38`
- `ADVAPI32!RegCloseKey` at `0x18000fb67`
- `ADVAPI32!RegCloseKey` at `0x18000fd34`
- `ADVAPI32!RegCloseKey` at `0x18000ff38`
- `KERNEL32!InitializeCriticalSection` at `0x18000f9fa`
- `KERNEL32!InitializeCriticalSection` at `0x18000f9fa`
- `KERNEL32!DeleteCriticalSection` at `0x18000fb98`
- `KERNEL32!DeleteCriticalSection` at `0x18000fb98`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb88`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd55`
- `KERNEL32!LeaveCriticalSection` at `0x18000ff59`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb88`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd55`
- `KERNEL32!LeaveCriticalSection` at `0x18000ff59`
- `KERNEL32!GetLastError` at `0x180010933`
- `KERNEL32!GetLastError` at `0x180010933`
- `KERNEL32!EnterCriticalSection` at `0x18000fb52`
- `KERNEL32!EnterCriticalSection` at `0x18000fd1f`
- `KERNEL32!EnterCriticalSection` at `0x18000ff23`
- `KERNEL32!EnterCriticalSection` at `0x18000fb52`
- `KERNEL32!EnterCriticalSection` at `0x18000fd1f`
- `KERNEL32!EnterCriticalSection` at `0x18000ff23`
- `KERNEL32!lstrlenW` at `0x1800102e0`
- `KERNEL32!lstrlenW` at `0x18001030a`
- `KERNEL32!lstrlenW` at `0x180010a16`
- `KERNEL32!lstrlenW` at `0x1800102e0`
- `KERNEL32!lstrlenW` at `0x18001030a`
- `KERNEL32!lstrlenW` at `0x180010a16`
- `KERNEL32!lstrlenA` at `0x180010231`
- `KERNEL32!lstrlenA` at `0x180010231`
- `KERNEL32!MultiByteToWideChar` at `0x18001027f`
- `KERNEL32!MultiByteToWideChar` at `0x18001096a`
- `KERNEL32!MultiByteToWideChar` at `0x1800109bd`
- `KERNEL32!MultiByteToWideChar` at `0x18001027f`
- `KERNEL32!MultiByteToWideChar` at `0x18001096a`
- `KERNEL32!MultiByteToWideChar` at `0x1800109bd`
- `KERNEL32!GlobalFree` at `0x18000fbae`
- `KERNEL32!GlobalFree` at `0x18000fde8`
- `KERNEL32!GlobalFree` at `0x18000ff12`
- `KERNEL32!GlobalFree` at `0x1800100a9`
- `KERNEL32!GlobalFree` at `0x1800101e4`
- `KERNEL32!GlobalFree` at `0x18001020a`
- `KERNEL32!GlobalFree` at `0x180010322`
- `KERNEL32!GlobalFree` at `0x180010354`
- `KERNEL32!GlobalFree` at `0x1800103b6`
- `KERNEL32!GlobalFree` at `0x18001042a`
- `KERNEL32!GlobalFree` at `0x18001049c`
- `KERNEL32!GlobalFree` at `0x180010509`
- `KERNEL32!GlobalFree` at `0x1800105f0`
- `KERNEL32!GlobalFree` at `0x180010684`
- `KERNEL32!GlobalFree` at `0x1800106a4`
- `KERNEL32!GlobalFree` at `0x1800107bb`
- `KERNEL32!GlobalFree` at `0x180010808`
- `KERNEL32!GlobalFree` at `0x180010820`
- `KERNEL32!GlobalFree` at `0x1800109d5`
- `KERNEL32!GlobalFree` at `0x1800109ed`
- `KERNEL32!GlobalFree` at `0x180010a05`
- `KERNEL32!GlobalFree` at `0x180010a84`
- `KERNEL32!GlobalFree` at `0x18000fbae`
- `KERNEL32!GlobalFree` at `0x18000fde8`
- `KERNEL32!GlobalFree` at `0x18000ff12`
- `KERNEL32!GlobalFree` at `0x1800100a9`
- `KERNEL32!GlobalFree` at `0x1800101e4`
- `KERNEL32!GlobalFree` at `0x18001020a`
- `KERNEL32!GlobalFree` at `0x180010322`
- `KERNEL32!GlobalFree` at `0x180010354`
- `KERNEL32!GlobalFree` at `0x1800103b6`
- `KERNEL32!GlobalFree` at `0x18001042a`
- `KERNEL32!GlobalFree` at `0x18001049c`
- `KERNEL32!GlobalFree` at `0x180010509`
- `KERNEL32!GlobalFree` at `0x1800105f0`
- `KERNEL32!GlobalFree` at `0x180010684`
- `KERNEL32!GlobalFree` at `0x1800106a4`
- `KERNEL32!GlobalFree` at `0x1800107bb`
- `KERNEL32!GlobalFree` at `0x180010808`
- `KERNEL32!GlobalFree` at `0x180010820`
- `KERNEL32!GlobalFree` at `0x1800109d5`
- `KERNEL32!GlobalFree` at `0x1800109ed`
- `KERNEL32!GlobalFree` at `0x180010a05`
- `KERNEL32!GlobalFree` at `0x180010a84`

## string_xrefs

- `0x18000fc8a`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800101b5`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18000fc2b`: `InstallProperties`

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
  int v9; // edi
  BYTE *v10; // r12
  unsigned int v11; // esi
  unsigned __int16 *v12; // rbx
  __int64 v13; // r14
  const wchar_t *v14; // r13
  __int64 v15; // rdx
  const struct ProductPropertyW near *const *v16; // r15
  const struct ProductPropertyW near *v17; // rax
  int v18; // ecx
  int v20; // ecx
  const WCHAR *v21; // r14
  unsigned int v22; // eax
  unsigned int ProductAssignmentType; // ebx
  unsigned int v24; // edi
  DWORD v25; // edi
  const unsigned __int16 *v26; // rsi
  HGLOBAL v27; // rbx
  unsigned int v28; // eax
  const wchar_t *v29; // rax
  int v30; // eax
  _DWORD *v31; // rax
  int v32; // edi
  unsigned int v33; // ebx
  _DWORD *v34; // rbx
  unsigned __int64 v35; // rcx
  HGLOBAL v36; // r9
  __int64 v37; // rax
  _WORD *v38; // rdx
  BYTE *v39; // rdx
  bool v40; // cc
  const unsigned __int16 *v41; // rdx
  int v42; // ecx
  int v43; // eax
  size_t *v44; // r8
  int *v45; // rdi
  unsigned int v46; // ecx
  int v47; // eax
  unsigned int v48; // eax
  const wchar_t *v49; // rax
  int v50; // edi
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v54; // [rsp+60h] [rbp-A0h]
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v56; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+78h] [rbp-88h]
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  int v59; // [rsp+80h] [rbp-80h] BYREF
  int i; // [rsp+88h] [rbp-78h]
  int v61; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+A0h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+C8h] [rbp-38h] BYREF
  HGLOBAL v65; // [rsp+F0h] [rbp-10h] BYREF
  int v66; // [rsp+F8h] [rbp-8h]
  int v67; // [rsp+FCh] [rbp-4h]
  wchar_t Buffer[64]; // [rsp+100h] [rbp+0h] BYREF
  HGLOBAL v69; // [rsp+180h] [rbp+80h] BYREF
  int cchWideChar; // [rsp+188h] [rbp+88h]
  _BYTE v71[512]; // [rsp+190h] [rbp+90h] BYREF
  LPCCH lpMultiByteStr; // [rsp+390h] [rbp+290h]
  __int64 v73; // [rsp+398h] [rbp+298h]
  HGLOBAL v74; // [rsp+3A0h] [rbp+2A0h]
  int v75; // [rsp+3A8h] [rbp+2A8h]
  unsigned __int16 v76[320]; // [rsp+3B0h] [rbp+2B0h] BYREF
  HGLOBAL v77; // [rsp+630h] [rbp+530h]
  int v78; // [rsp+638h] [rbp+538h]
  unsigned __int16 v79[264]; // [rsp+640h] [rbp+540h] BYREF
  HGLOBAL v80; // [rsp+850h] [rbp+750h]
  int v81; // [rsp+858h] [rbp+758h]
  unsigned __int16 v82[1024]; // [rsp+860h] [rbp+760h] BYREF

  v9 = a4;
  v10 = a6;
  v11 = a3;
  v56 = a7;
  v12 = a1;
  v61 = a4;
  v57 = a3;
  v62 = a1;
  v59 = a3;
  if ( !a1 )
    return 14;
  v13 = a5;
  if ( !a5 || a6 && !a7 )
    return 14;
  v14 = L"S-1-5-18";
  if ( a3 != 2 )
    v14 = a2;
  v54 = 0;
  for ( i = 0; ; i = 1 )
  {
    LODWORD(hKey.LockSemaphore) = 1;
    hKey.OwningThread = &hKey.SpinCount;
    LOWORD(hKey.SpinCount) = 0;
    *(_OWORD *)&hKey.DebugInfo = 0;
    InitializeCriticalSection(&CriticalSection);
    cchWideChar = 256;
    v16 = &g_ProductPropertyTableW;
    v69 = v71;
    v73 = v13;
    lpMultiByteStr = 0;
    if ( g_ProductPropertyTableW )
    {
      while ( 1 )
      {
        v17 = *v16;
        do
        {
          v18 = *(unsigned __int16 *)((char *)v17 + v13 - (unsigned __int64)*v16);
          v15 = (unsigned int)*(unsigned __int16 *)v17 - v18;
          if ( (_DWORD)v15 )
            break;
          v17 = (const struct ProductPropertyW near *)((char *)v17 + 2);
        }
        while ( v18 );
        if ( !(_DWORD)v15 )
          break;
        v16 += 4;
        if ( !*v16 )
          goto LABEL_13;
      }
    }
    if ( !*v16 || (v9 & *((_DWORD *)v16 + 7)) == 0 )
      goto LABEL_13;
    v20 = *((_DWORD *)v16 + 6);
    v21 = (const WCHAR *)*((_QWORD *)v16 + 1);
    if ( v20 )
    {
      if ( v20 != 1 )
      {
        if ( v9 == 1 )
        {
          LOBYTE(v53) = v54;
          v22 = OpenSpecificSourceListKeyPacked(v12, v15, 0xFFFFFFFFLL, 0, &hKey, 0, v53);
        }
        else
        {
          if ( v9 != 2 )
            goto LABEL_70;
          LOBYTE(v53) = v54;
          v22 = OpenSpecificSourceListKeyPacked(v12, v15, 0xFFFFFFFFLL, 1, &hKey, 0, v53);
        }
        goto LABEL_21;
      }
      if ( a9 == 1 )
        goto LABEL_117;
      if ( v9 == 1 )
      {
        v78 = 260;
        v77 = v79;
        if ( (int)StringCchPrintfW(v79, 0x104u, L"%s\\%s\\%s", L"Products", v12, L"InstallProperties") < 0 )
        {
          if ( v78 > 260 )
            GlobalFree(v77);
          v24 = 1627;
        }
        else
        {
          v25 = g_samRead;
          v26 = (const unsigned __int16 *)v77;
          v74 = v76;
          v75 = 318;
          if ( v14 )
          {
            ProductAssignmentType = StringCchPrintfW(
                                      v76,
                                      0x13Eu,
                                      L"%s\\%s",
                                      L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                      v14);
            goto LABEL_37;
          }
          cbData = 3;
          ProductAssignmentType = GetProductAssignmentType(v12, (enum iaaAppAssignment *)&cbData);
          if ( !ProductAssignmentType )
          {
            v65 = Buffer;
            v66 = 64;
            if ( cbData == 2 )
            {
              v41 = L"S-1-5-18";
              goto LABEL_99;
            }
            v41 = 0;
            if ( cbData > 1 )
            {
              if ( cbData == 3 )
              {
                ProductAssignmentType = 2;
              }
              else
              {
LABEL_99:
                ProductAssignmentType = StringCchPrintfW(
                                          v76,
                                          0x13Eu,
                                          L"%s\\%s",
                                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                                          v41);
                if ( v66 > 64 )
                  goto LABEL_100;
              }
            }
            else
            {
              v67 = 64;
              ProductAssignmentType = GetCurrentUserStringSID(&v65);
              if ( !ProductAssignmentType )
              {
                v41 = (const unsigned __int16 *)v65;
                goto LABEL_99;
              }
              if ( v66 > 64 )
LABEL_100:
                GlobalFree(v65);
            }
          }
LABEL_37:
          if ( ProductAssignmentType )
          {
            if ( v75 <= 318 )
              goto LABEL_48;
            goto LABEL_132;
          }
          v80 = v82;
          v81 = 1024;
          if ( (int)StringCchPrintfW(v82, 0x400u, L"%s\\%s", v74, v26) >= 0 )
          {
            v27 = v80;
            if ( (v25 & 0x20019) != 0 && (v25 & 6) == 0 )
            {
              EnterCriticalSection(&CriticalSection);
              if ( hKey.DebugInfo )
              {
                RegCloseKey((HKEY)hKey.DebugInfo);
                hKey.DebugInfo = 0;
                *(_WORD *)hKey.OwningThread = 0;
              }
              LeaveCriticalSection(&CriticalSection);
              if ( !g_fWoW && g_fWinNT64 && (v25 & 0x100) == 0 )
                v25 |= 0x100u;
              v28 = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, _QWORD, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                      -2147483646,
                      v27,
                      0,
                      v25,
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
              cbData = v25;
              AdjustREGSAM(&cbData);
              v28 = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, _QWORD, _DWORD, DWORD, _QWORD, struct _RTL_CRITICAL_SECTION *, _QWORD))RegCreateKeyAPI)(
                      -2147483646,
                      v27,
                      0,
                      0,
                      0,
                      cbData,
                      0,
                      &hKey,
                      0);
            }
            ProductAssignmentType = v28;
            if ( !v28 && v54 )
              CRegHandleStatic::SetKey((CRegHandleStatic *)&hKey, HKEY_LOCAL_MACHINE, v26);
            if ( v81 > 1024 )
              GlobalFree(v80);
            v80 = v82;
            v81 = 1024;
            if ( v75 <= 318 )
              goto LABEL_48;
LABEL_132:
            GlobalFree(v74);
            goto LABEL_48;
          }
          if ( v81 > 1024 )
            GlobalFree(v80);
          v80 = v82;
          v81 = 1024;
          if ( v75 > 318 )
            GlobalFree(v74);
          ProductAssignmentType = 1627;
LABEL_48:
          if ( v78 > 260 )
            GlobalFree(v77);
          if ( a8 || ProductAssignmentType != 2 )
          {
            if ( ProductAssignmentType )
              goto LABEL_23;
            v29 = (const wchar_t *)CApiConvertString::operator unsigned short const *(&v69);
            v30 = wcscmp_0(v29, L"LocalPackage");
            v11 = v57;
            if ( !v30 )
            {
              if ( v57 == 3 )
              {
                ProductAssignmentType = GetProductAssignmentType(v62, (enum iaaAppAssignment *)&v59);
                if ( ProductAssignmentType )
                  goto LABEL_23;
                v11 = v59;
                v57 = v59;
              }
              if ( !v11 )
                v21 = L"ManagedLocalPackage";
            }
            goto LABEL_58;
          }
          if ( v14 )
            v48 = OpenSpecificUsersAdvertisedSubKeyPacked(v57, v14, (WCHAR *)L"Products", v62, &hKey, v54);
          else
            v48 = OpenAdvertisedProductKeyPacked(v62, &hKey, v54, 0xFFFFFFFFLL, 0);
          ProductAssignmentType = v48;
          if ( !v48 )
          {
LABEL_117:
            if ( cchWideChar > 256 )
              GlobalFree(v69);
LABEL_13:
            cchWideChar = 256;
            v69 = v71;
            CRegHandle::~CRegHandle((CRegHandle *)&hKey);
            return 1608;
          }
LABEL_23:
          v24 = ProductAssignmentType;
          if ( ProductAssignmentType == 2 )
          {
            if ( cchWideChar > 256 )
              GlobalFree(v69);
            cchWideChar = 256;
            v69 = v71;
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
          if ( ProductAssignmentType == 1608 )
            goto LABEL_117;
        }
LABEL_71:
        if ( cchWideChar > 256 )
          GlobalFree(v69);
        cchWideChar = 256;
        v69 = v71;
        CRegHandle::~CRegHandle((CRegHandle *)&hKey);
        return v24;
      }
      if ( v9 != 2 )
        goto LABEL_70;
      if ( ((v11 + 1) & 0xFFFFFFFB) == 0 )
      {
        if ( lstrlenW(v12) == 32 )
        {
          LOBYTE(lpData) = v54;
          v50 = 0;
          if ( (unsigned int)OpenInstalledPatchKeyPackedByAssignmentType(v12, 0, 0, &hKey, (_DWORD)lpData) )
          {
            v50 = 2;
            LOBYTE(lpDataa) = v54;
            ProductAssignmentType = OpenInstalledPatchKeyPackedByAssignmentType(v12, 2, 0, &hKey, lpDataa);
            if ( ProductAssignmentType )
              goto LABEL_23;
          }
          v49 = (const wchar_t *)CApiConvertString::operator unsigned short const *(&v69);
          if ( wcscmp_0(v49, L"LocalPackage") || v50 )
            goto LABEL_58;
          v21 = L"ManagedLocalPackage";
          ProductAssignmentType = 0;
          goto LABEL_22;
        }
LABEL_70:
        v24 = 87;
        goto LABEL_71;
      }
      LOBYTE(lpData) = v54;
      v22 = OpenInstalledPatchKeyPackedByAssignmentType(v12, v11, 0, &hKey, (_DWORD)lpData);
    }
    else
    {
      if ( a8 )
        goto LABEL_117;
      if ( v9 == 1 )
      {
        v22 = v14
            ? OpenSpecificUsersAdvertisedSubKeyPacked(v11, v14, (WCHAR *)L"Products", v12, &hKey, v54)
            : OpenAdvertisedProductKeyPacked(v12, &hKey, v54, 0xFFFFFFFFLL, 0);
      }
      else
      {
        if ( v9 != 2 )
          goto LABEL_70;
        v22 = OpenAdvertisedPatchKeyPacked(v12, &hKey, v54);
      }
    }
LABEL_21:
    ProductAssignmentType = v22;
LABEL_22:
    if ( ProductAssignmentType )
      goto LABEL_23;
LABEL_58:
    v31 = v56;
    Type = 0;
    if ( !a6 && !v56 )
      goto LABEL_64;
    v32 = 0;
LABEL_60:
    cbData = 2 * *v31;
    v33 = RegQueryValueExW((HKEY)hKey.DebugInfo, v21, 0, &Type, a6, &cbData);
    if ( v33 )
      break;
    if ( Type == 4 )
    {
      if ( !a6 )
      {
        v40 = cchWideChar <= 256;
        *v56 = 11;
        if ( v40 )
        {
LABEL_95:
          cchWideChar = 256;
          v69 = v71;
          CRegHandle::~CRegHandle((CRegHandle *)&hKey);
          return v33;
        }
LABEL_112:
        GlobalFree(v69);
        goto LABEL_95;
      }
      v42 = *(_DWORD *)a6;
      v65 = Buffer;
      v66 = 20;
      _itow_s(v42, Buffer, 0x14u, 10);
      v43 = lstrlenW((LPCWSTR)v65);
      v45 = v56;
      v46 = *v56;
      if ( *v56 >= (unsigned int)(v43 + 1) && v46 )
      {
        if ( v46 > 0x7FFFFFFF )
        {
          *(_WORD *)a6 = 0;
        }
        else if ( StringCopyWorkerW((STRSAFE_LPWSTR)a6, (unsigned int)*v56, v44, (STRSAFE_PCNZWCH)v65, (size_t)lpData) >= 0 )
        {
          v33 = 0;
          goto LABEL_108;
        }
      }
      v33 = 234;
LABEL_108:
      v47 = lstrlenW((LPCWSTR)v65);
      v40 = v66 <= 20;
      *v45 = v47;
      if ( !v40 )
        GlobalFree(v65);
      v66 = 20;
      v65 = Buffer;
LABEL_111:
      if ( cchWideChar <= 256 )
        goto LABEL_95;
      goto LABEL_112;
    }
    if ( (*((_BYTE *)v16 + 28) & 4) == 0 )
    {
      *v56 = (cbData >> 1) - 1;
      goto LABEL_64;
    }
    if ( !a6 )
    {
      v40 = cchWideChar <= 256;
      *v56 = 38;
      if ( !v40 )
        goto LABEL_152;
      goto LABEL_65;
    }
    v34 = v56;
    if ( *v56 < 0x27u )
    {
      v40 = cchWideChar <= 256;
      *v56 = 38;
      if ( !v40 )
        goto LABEL_144;
      goto LABEL_148;
    }
    v66 = 39;
    v65 = Buffer;
    if ( (unsigned int)UnpackGUID(a6, Buffer, 39, 1) )
    {
      v35 = (unsigned int)*v34;
      v36 = v65;
      if ( *v34 )
      {
        if ( v35 > 0x7FFFFFFF )
        {
          *(_WORD *)a6 = 0;
        }
        else
        {
          v37 = 2147483646;
          v38 = v65;
          do
          {
            if ( !v37 )
              break;
            if ( !*v38 )
              break;
            *(_WORD *)v10 = *v38++;
            v10 += 2;
            --v37;
            --v35;
          }
          while ( v35 );
          v39 = v10 - 2;
          if ( v35 )
            v39 = v10;
          *(_WORD *)v39 = 0;
          if ( v35 )
          {
            v40 = v66 <= 39;
            *v34 = 38;
            if ( !v40 )
              GlobalFree(v36);
LABEL_64:
            if ( cchWideChar > 256 )
              goto LABEL_152;
            goto LABEL_65;
          }
        }
      }
      if ( v66 > 39 )
        GlobalFree(v36);
      v65 = Buffer;
      v66 = 39;
      if ( cchWideChar > 256 )
        GlobalFree(v69);
      cchWideChar = 256;
      v69 = v71;
      CRegHandle::~CRegHandle((CRegHandle *)&hKey);
      return 1627;
    }
    if ( i )
    {
      DebugString(
        21,
        1u,
        0x3EAu,
        *((const unsigned __int16 **)v16 + 1),
        (const unsigned __int16 *)a6,
        (const unsigned __int16 *)hKey.OwningThread,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
      if ( v66 > 39 )
        GlobalFree(v65);
      v65 = Buffer;
      v66 = 39;
      if ( cchWideChar > 256 )
        GlobalFree(v69);
      cchWideChar = 256;
      v69 = v71;
      CRegHandle::~CRegHandle((CRegHandle *)&hKey);
      return 1610;
    }
    v54 = 1;
    if ( v66 > 39 )
      GlobalFree(v65);
    v65 = Buffer;
    v66 = 39;
    if ( cchWideChar > 256 )
      GlobalFree(v69);
    cchWideChar = 256;
    v69 = v71;
    CRegHandle::~CRegHandle((CRegHandle *)&hKey);
    v12 = v62;
    v9 = v61;
    v13 = a5;
  }
  if ( v33 == 234 )
  {
    if ( Type - 1 > 1 )
    {
      if ( Type == 4 )
        *v56 = 11;
    }
    else
    {
      *v56 = (cbData >> 1) - 1;
    }
    if ( cchWideChar > 256 )
LABEL_144:
      GlobalFree(v69);
LABEL_148:
    cchWideChar = 256;
    v69 = v71;
    CRegHandle::~CRegHandle((CRegHandle *)&hKey);
    return 234;
  }
  if ( v61 == 2 && !wcscmp_0(v21, L"ManagedLocalPackage") && ((v11 + 1) & 0xFFFFFFFB) == 0 && ++v32 < 2 )
  {
    v31 = v56;
    v21 = L"LocalPackage";
    goto LABEL_60;
  }
  if ( v33 != 2 )
    goto LABEL_111;
  if ( a6 )
    *(_WORD *)a6 = 0;
  v40 = cchWideChar <= 256;
  *v56 = 0;
  if ( !v40 )
LABEL_152:
    GlobalFree(v69);
LABEL_65:
  cchWideChar = 256;
  v69 = v71;
  CRegHandle::~CRegHandle((CRegHandle *)&hKey);
  return 0;
}

```

## disassembly

```asm
0x18000f930  push    rbp
0x18000f932  push    rbx
0x18000f933  push    rsi
0x18000f934  push    rdi
0x18000f935  push    r12
0x18000f937  push    r14
0x18000f939  lea     rbp, [rsp-0F78h]
0x18000f941  mov     eax, 1078h
0x18000f946  call    _alloca_probe
0x18000f94b  sub     rsp, rax
0x18000f94e  mov     rax, cs:__security_cookie
0x18000f955  xor     rax, rsp
0x18000f958  mov     [rbp+0FA0h+var_40], rax
0x18000f95f  mov     rax, [rbp+0FA0h+arg_30]
0x18000f966  mov     edi, r9d
0x18000f969  mov     r12, [rbp+0FA0h+arg_28]
0x18000f970  mov     esi, r8d
0x18000f973  mov     [rsp+10A0h+var_1030], rax
0x18000f978  mov     rbx, rcx
0x18000f97b  mov     [rbp+0FA0h+var_1014], r9d
0x18000f97f  mov     [rsp+10A0h+var_1028], r8d
0x18000f984  mov     [rbp+0FA0h+var_1010], rcx
0x18000f988  mov     [rbp+0FA0h+var_1020], r8d
0x18000f98c  test    rcx, rcx
0x18000f98f  jz      loc_180010224
0x18000f995  mov     r14, [rbp+0FA0h+arg_20]
0x18000f99c  test    r14, r14
0x18000f99f  jz      loc_180010224
0x18000f9a5  test    r12, r12
0x18000f9a8  jnz     loc_18001021B
0x18000f9ae  mov     [rsp+10A0h+arg_18], r13
0x18000f9b6  cmp     r8d, 2
0x18000f9ba  lea     r13, aS1518_0; "S-1-5-18"
0x18000f9c1  mov     [rsp+10A0h+var_30], r15
0x18000f9c9  cmovnz  r13, rdx
0x18000f9cd  mov     [rsp+10A0h+var_1040], 0
0x18000f9d2  mov     [rbp+0FA0h+var_1018], 0
0x18000f9d9  lea     rax, [rbp+0FA0h+var_FE0]
0x18000f9dd  mov     [rbp+0FA0h+var_FE8], 1
0x18000f9e4  mov     [rbp+0FA0h+hMem], rax
0x18000f9e8  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000f9ec  xor     eax, eax
0x18000f9ee  xorps   xmm0, xmm0
0x18000f9f1  mov     [rbp+0FA0h+var_FE0], ax
0x18000f9f5  movdqa  xmmword ptr [rbp+0FA0h+hKey], xmm0
0x18000f9fa  call    cs:__imp_InitializeCriticalSection
0x18000fa01  nop     dword ptr [rax+rax+00h]
0x18000fa06  xor     r9d, r9d
0x18000fa09  mov     [rbp+0FA0h+cchWideChar], 100h
0x18000fa13  cmp     cs:?g_ProductPropertyTableW@@3QBUProductPropertyW@@B, r9; ProductPropertyW const near * const g_ProductPropertyTableW
0x18000fa1a  lea     rax, [rbp+0FA0h+var_F10]
0x18000fa21  lea     r15, ?g_ProductPropertyTableW@@3QBUProductPropertyW@@B; ProductPropertyW const near * const g_ProductPropertyTableW
0x18000fa28  mov     [rbp+0FA0h+var_F20], rax
0x18000fa2f  mov     r10, r14
0x18000fa32  mov     [rbp+0FA0h+var_D08], r14
0x18000fa39  mov     [rbp+0FA0h+lpMultiByteStr], r9
0x18000fa40  jz      short loc_18000FAB1
0x18000fa42  test    r9, r9
0x18000fa45  jnz     loc_18001022E
0x18000fa4b  mov     r8, r10
0x18000fa4e  mov     rax, [r15]
0x18000fa51  sub     r8, rax
0x18000fa54  movzx   edx, word ptr [rax]
0x18000fa57  movzx   ecx, word ptr [rax+r8]
0x18000fa5c  sub     edx, ecx
0x18000fa5e  jnz     short loc_18000FA68
0x18000fa60  add     rax, 2
0x18000fa64  test    ecx, ecx
0x18000fa66  jnz     short loc_18000FA54
0x18000fa68  test    edx, edx
0x18000fa6a  jz      short loc_18000FAB1
0x18000fa6c  add     r15, 20h ; ' '
0x18000fa70  cmp     qword ptr [r15], 0
0x18000fa74  jnz     short loc_18000FA42
0x18000fa76  cmp     [rbp+0FA0h+cchWideChar], 100h
0x18000fa80  jg      loc_1800103AF
0x18000fa86  lea     rax, [rbp+0FA0h+var_F10]
0x18000fa8d  mov     [rbp+0FA0h+cchWideChar], 100h
0x18000fa97  lea     rcx, [rbp+0FA0h+hKey]; this
0x18000fa9b  mov     [rbp+0FA0h+var_F20], rax
0x18000faa2  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18000faa7  mov     eax, 648h
0x18000faac  jmp     loc_18000FBBF
0x18000fab1  cmp     qword ptr [r15], 0
0x18000fab5  jz      short loc_18000FA76
0x18000fab7  test    [r15+1Ch], edi
0x18000fabb  jz      short loc_18000FA76
0x18000fabd  mov     ecx, [r15+18h]
0x18000fac1  mov     r14, [r15+8]
0x18000fac5  test    ecx, ecx
0x18000fac7  jnz     loc_18000FBEF
0x18000facd  cmp     [rbp+0FA0h+arg_38], cl
0x18000fad3  jnz     loc_18001039F
0x18000fad9  cmp     edi, 1
0x18000fadc  jnz     loc_18001070A
0x18000fae2  test    r13, r13
0x18000fae5  jz      loc_1800103F1
0x18000faeb  movzx   eax, [rsp+10A0h+var_1040]
0x18000faf0  lea     r8, aProducts; "Products"
0x18000faf7  mov     byte ptr [rsp+10A0h+lpcbData], al
0x18000fafb  mov     r9, rbx
0x18000fafe  lea     rax, [rbp+0FA0h+hKey]
0x18000fb02  mov     rdx, r13
0x18000fb05  mov     ecx, esi
0x18000fb07  mov     [rsp+10A0h+lpData], rax
0x18000fb0c  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18000fb11  mov     ebx, eax
0x18000fb13  test    ebx, ebx
0x18000fb15  jz      loc_18000FE5A
0x18000fb1b  mov     edi, ebx
0x18000fb1d  cmp     ebx, 2
0x18000fb20  jnz     loc_1800108A4
0x18000fb26  cmp     [rbp+0FA0h+cchWideChar], 100h
0x18000fb30  jg      loc_18000FF0B
0x18000fb36  lea     rax, [rbp+0FA0h+var_F10]
0x18000fb3d  mov     [rbp+0FA0h+cchWideChar], 100h
0x18000fb47  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000fb4b  mov     [rbp+0FA0h+var_F20], rax
0x18000fb52  call    cs:__imp_EnterCriticalSection
0x18000fb59  nop     dword ptr [rax+rax+00h]
0x18000fb5e  mov     rcx, [rbp+0FA0h+hKey]; hKey
0x18000fb62  test    rcx, rcx
0x18000fb65  jz      short loc_18000FB84
0x18000fb67  call    cs:__imp_RegCloseKey
0x18000fb6e  nop     dword ptr [rax+rax+00h]
0x18000fb73  mov     rax, [rbp+0FA0h+hMem]
0x18000fb77  xor     ecx, ecx
0x18000fb79  mov     [rbp+0FA0h+hKey], 0
0x18000fb81  mov     [rax], cx
0x18000fb84  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000fb88  call    cs:__imp_LeaveCriticalSection
0x18000fb8f  nop     dword ptr [rax+rax+00h]
0x18000fb94  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000fb98  call    cs:__imp_DeleteCriticalSection
0x18000fb9f  nop     dword ptr [rax+rax+00h]
0x18000fba4  cmp     [rbp+0FA0h+var_FE8], 1
0x18000fba8  jle     short loc_18000FBBA
0x18000fbaa  mov     rcx, [rbp+0FA0h+hMem]; hMem
0x18000fbae  call    cs:__imp_GlobalFree
0x18000fbb5  nop     dword ptr [rax+rax+00h]
0x18000fbba  mov     eax, 645h
0x18000fbbf  mov     r13, [rsp+10A0h+arg_18]
0x18000fbc7  mov     r15, [rsp+10A0h+var_30]
0x18000fbcf  mov     rcx, [rbp+0FA0h+var_40]
0x18000fbd6  xor     rcx, rsp; StackCookie
0x18000fbd9  call    __security_check_cookie
0x18000fbde  add     rsp, 1078h
0x18000fbe5  pop     r14
0x18000fbe7  pop     r12
0x18000fbe9  pop     rdi
0x18000fbea  pop     rsi
0x18000fbeb  pop     rbx
0x18000fbec  pop     rbp
0x18000fbed  retn
0x18000fbef  cmp     ecx, 1
0x18000fbf2  jnz     loc_180010571
0x18000fbf8  cmp     [rbp+0FA0h+arg_40], ecx
0x18000fbfe  jz      loc_18001039F
0x18000fc04  cmp     edi, ecx
0x18000fc06  jnz     loc_18000FFB5
0x18000fc0c  lea     rax, [rbp+0FA0h+var_A60]
0x18000fc13  mov     [rbp+0FA0h+var_A68], 104h
0x18000fc1d  mov     [rbp+0FA0h+var_A70], rax
0x18000fc24  lea     r9, aProducts; "Products"
0x18000fc2b  lea     rax, aInstallpropert; "InstallProperties"
0x18000fc32  mov     edx, 104h; unsigned __int64
0x18000fc37  mov     [rsp+10A0h+lpcbData], rax
0x18000fc3c  lea     r8, aSSS; "%s\\%s\\%s"
0x18000fc43  lea     rcx, [rbp+0FA0h+var_A60]; unsigned __int16 *
0x18000fc4a  mov     [rsp+10A0h+lpData], rbx
0x18000fc4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fc54  test    eax, eax
0x18000fc56  js      loc_1800108B5
0x18000fc5c  mov     edi, cs:?g_samRead@@3KA; ulong g_samRead
0x18000fc62  lea     rax, [rbp+0FA0h+var_CF0]
0x18000fc69  mov     rsi, [rbp+0FA0h+var_A70]
0x18000fc70  mov     [rbp+0FA0h+var_D00], rax
0x18000fc77  mov     [rbp+0FA0h+var_CF8], 13Eh
0x18000fc81  test    r13, r13
0x18000fc84  jz      loc_18001016E
0x18000fc8a  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000fc91  mov     [rsp+10A0h+lpData], r13
0x18000fc96  lea     r8, aSS_0; "%s\\%s"
0x18000fc9d  mov     edx, 13Eh; unsigned __int64
0x18000fca2  lea     rcx, [rbp+0FA0h+var_CF0]; unsigned __int16 *
0x18000fca9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fcae  mov     ebx, eax
0x18000fcb0  test    ebx, ebx
0x18000fcb2  jnz     loc_1800104F2
0x18000fcb8  mov     r9, [rbp+0FA0h+var_D00]
0x18000fcbf  lea     rax, [rbp+0FA0h+var_840]
0x18000fcc6  lea     r8, aSS_0; "%s\\%s"
0x18000fccd  mov     [rbp+0FA0h+var_850], rax
0x18000fcd4  mov     edx, 400h; unsigned __int64
0x18000fcd9  mov     [rbp+0FA0h+var_848], 400h
0x18000fce3  lea     rcx, [rbp+0FA0h+var_840]; unsigned __int16 *
0x18000fcea  mov     [rsp+10A0h+lpData], rsi
0x18000fcef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fcf4  test    eax, eax
0x18000fcf6  js      loc_1800108DE
0x18000fcfc  mov     rbx, [rbp+0FA0h+var_850]
0x18000fd03  test    edi, 20019h
0x18000fd09  setnz   cl
0x18000fd0c  test    dil, 6
0x18000fd10  setz    al
0x18000fd13  test    al, cl
0x18000fd15  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000fd19  jz      loc_18000FF23
0x18000fd1f  call    cs:__imp_EnterCriticalSection
0x18000fd26  nop     dword ptr [rax+rax+00h]
0x18000fd2b  mov     rcx, [rbp+0FA0h+hKey]; hKey
0x18000fd2f  test    rcx, rcx
0x18000fd32  jz      short loc_18000FD51
0x18000fd34  call    cs:__imp_RegCloseKey
0x18000fd3b  nop     dword ptr [rax+rax+00h]
0x18000fd40  mov     rax, [rbp+0FA0h+hMem]
0x18000fd44  xor     ecx, ecx
0x18000fd46  mov     [rbp+0FA0h+hKey], 0
0x18000fd4e  mov     [rax], cx
0x18000fd51  lea     rcx, [rbp+0FA0h+CriticalSection]; lpCriticalSection
0x18000fd55  call    cs:__imp_LeaveCriticalSection
0x18000fd5c  nop     dword ptr [rax+rax+00h]
0x18000fd61  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x18000fd68  jz      loc_180010758
0x18000fd6e  lea     rax, [rbp+0FA0h+hKey]
0x18000fd72  mov     r9d, edi
0x18000fd75  mov     [rsp+10A0h+lpData], rax
0x18000fd7a  xor     r8d, r8d
0x18000fd7d  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18000fd84  mov     rdx, rbx
0x18000fd87  mov     rcx, 0FFFFFFFF80000002h
0x18000fd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd93  mov     ebx, eax
0x18000fd95  test    eax, eax
0x18000fd97  jz      loc_1800100FF
0x18000fd9d  cmp     [rbp+0FA0h+var_848], 400h
0x18000fda7  jg      loc_1800109FE
0x18000fdad  cmp     [rbp+0FA0h+var_CF8], 13Eh
0x18000fdb7  lea     rax, [rbp+0FA0h+var_840]
0x18000fdbe  mov     [rbp+0FA0h+var_850], rax
0x18000fdc5  mov     [rbp+0FA0h+var_848], 400h
0x18000fdcf  jg      loc_180010502
0x18000fdd5  cmp     [rbp+0FA0h+var_A68], 104h
0x18000fddf  jle     short loc_18000FDF4
0x18000fde1  mov     rcx, [rbp+0FA0h+var_A70]; hMem
0x18000fde8  call    cs:__imp_GlobalFree
0x18000fdef  nop     dword ptr [rax+rax+00h]
0x18000fdf4  cmp     [rbp+0FA0h+arg_38], 0
0x18000fdfb  jz      loc_180010365
0x18000fe01  test    ebx, ebx
0x18000fe03  jnz     loc_18000FB1B
0x18000fe09  lea     rcx, [rbp+0FA0h+var_F20]
0x18000fe10  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000fe15  mov     rcx, rax; String1
0x18000fe18  lea     rdx, aLocalpackage_0; "LocalPackage"
0x18000fe1f  call    wcscmp_0
0x18000fe24  mov     esi, [rsp+10A0h+var_1028]
0x18000fe28  test    eax, eax
0x18000fe2a  jnz     short loc_18000FE5A
0x18000fe2c  cmp     esi, 3
0x18000fe2f  jnz     short loc_18000FE4F
0x18000fe31  mov     rcx, [rbp+0FA0h+var_1010]; unsigned __int16 *
0x18000fe35  lea     rdx, [rbp+0FA0h+var_1020]; enum iaaAppAssignment *
0x18000fe39  call    ?GetProductAssignmentType@@YAKPEBGAEAW4iaaAppAssignment@@@Z; GetProductAssignmentType(ushort const *,iaaAppAssignment &)
0x18000fe3e  mov     ebx, eax
0x18000fe40  test    eax, eax
0x18000fe42  jnz     loc_18000FB1B
0x18000fe48  mov     esi, [rbp+0FA0h+var_1020]
0x18000fe4b  mov     [rsp+10A0h+var_1028], esi
0x18000fe4f  test    esi, esi
0x18000fe51  jnz     short loc_18000FE5A
0x18000fe53  lea     r14, aManagedlocalpa; "ManagedLocalPackage"
0x18000fe5a  mov     rax, [rsp+10A0h+var_1030]
0x18000fe5f  mov     [rsp+10A0h+Type], 0
0x18000fe67  test    r12, r12
0x18000fe6a  jz      loc_1800101F5
0x18000fe70  xor     edi, edi
0x18000fe72  mov     eax, [rax]
0x18000fe74  lea     r9, [rsp+10A0h+Type]; lpType
0x18000fe79  mov     rcx, [rbp+0FA0h+hKey]; hKey
0x18000fe7d  add     eax, eax
0x18000fe7f  mov     [rsp+10A0h+cbData], eax
0x18000fe83  xor     r8d, r8d; lpReserved
0x18000fe86  lea     rax, [rsp+10A0h+cbData]
0x18000fe8b  mov     rdx, r14; lpValueName
0x18000fe8e  mov     [rsp+10A0h+lpcbData], rax; lpcbData
0x18000fe93  mov     [rsp+10A0h+lpData], r12; cchToCopy
0x18000fe98  call    cs:__imp_RegQueryValueExW
0x18000fe9f  nop     dword ptr [rax+rax+00h]
0x18000fea4  mov     ebx, eax
0x18000fea6  test    eax, eax
0x18000fea8  jnz     loc_18001051A
0x18000feae  cmp     [rsp+10A0h+Type], 4
0x18000feb3  jz      loc_180010122
0x18000feb9  test    byte ptr [r15+1Ch], 4
0x18000febe  jnz     loc_18000FFFB
0x18000fec4  mov     eax, [rsp+10A0h+cbData]
0x18000fec8  mov     rdi, [rsp+10A0h+var_1030]
0x18000fecd  shr     eax, 1
0x18000fecf  dec     eax
  ... truncated ...
```
