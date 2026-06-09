# IsPatchAppliedToProduct(ushort const *,ushort const *,ushort const *,iaaAppAssignment,bool)

- ea: `0x18003ecd4`
- end: `0x18003f91c`
- name: `?IsPatchAppliedToProduct@@YA_NPEBG00W4iaaAppAssignment@@_N@Z`
- size: `3144`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003c1d0`
- `0x18003e4c0`
- `0x18003f930`
- `0x1800e3c4c`

## callees

- `0x180010ac0`
- `0x180011280`
- `0x180013b7c`
- `0x18003c030`
- `0x18003e40c`
- `0x18003ecd4`
- `0x18006cb7c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003f2e3`
- `ADVAPI32!RegQueryValueExW` at `0x18003f391`
- `ADVAPI32!RegQueryValueExW` at `0x18003f57c`
- `ADVAPI32!RegQueryValueExW` at `0x18003f60e`
- `ADVAPI32!RegQueryValueExW` at `0x18003f8f0`
- `ADVAPI32!RegQueryValueExW` at `0x18003f2e3`
- `ADVAPI32!RegQueryValueExW` at `0x18003f391`
- `ADVAPI32!RegQueryValueExW` at `0x18003f57c`
- `ADVAPI32!RegQueryValueExW` at `0x18003f60e`
- `ADVAPI32!RegQueryValueExW` at `0x18003f8f0`
- `ADVAPI32!RegCloseKey` at `0x18003eeb5`
- `ADVAPI32!RegCloseKey` at `0x18003ef52`
- `ADVAPI32!RegCloseKey` at `0x18003eff7`
- `ADVAPI32!RegCloseKey` at `0x18003f06d`
- `ADVAPI32!RegCloseKey` at `0x18003f137`
- `ADVAPI32!RegCloseKey` at `0x18003f1ad`
- `ADVAPI32!RegCloseKey` at `0x18003f240`
- `ADVAPI32!RegCloseKey` at `0x18003f41d`
- `ADVAPI32!RegCloseKey` at `0x18003f497`
- `ADVAPI32!RegCloseKey` at `0x18003eeb5`
- `ADVAPI32!RegCloseKey` at `0x18003ef52`
- `ADVAPI32!RegCloseKey` at `0x18003eff7`
- `ADVAPI32!RegCloseKey` at `0x18003f06d`
- `ADVAPI32!RegCloseKey` at `0x18003f137`
- `ADVAPI32!RegCloseKey` at `0x18003f1ad`
- `ADVAPI32!RegCloseKey` at `0x18003f240`
- `ADVAPI32!RegCloseKey` at `0x18003f41d`
- `ADVAPI32!RegCloseKey` at `0x18003f497`
- `KERNEL32!InitializeCriticalSection` at `0x18003ed59`
- `KERNEL32!InitializeCriticalSection` at `0x18003ed83`
- `KERNEL32!InitializeCriticalSection` at `0x18003ed59`
- `KERNEL32!InitializeCriticalSection` at `0x18003ed83`
- `KERNEL32!DeleteCriticalSection` at `0x18003f024`
- `KERNEL32!DeleteCriticalSection` at `0x18003f098`
- `KERNEL32!DeleteCriticalSection` at `0x18003f164`
- `KERNEL32!DeleteCriticalSection` at `0x18003f1d8`
- `KERNEL32!DeleteCriticalSection` at `0x18003f44a`
- `KERNEL32!DeleteCriticalSection` at `0x18003f024`
- `KERNEL32!DeleteCriticalSection` at `0x18003f098`
- `KERNEL32!DeleteCriticalSection` at `0x18003f164`
- `KERNEL32!DeleteCriticalSection` at `0x18003f1d8`
- `KERNEL32!DeleteCriticalSection` at `0x18003f44a`
- `KERNEL32!LeaveCriticalSection` at `0x18003eed0`
- `KERNEL32!LeaveCriticalSection` at `0x18003ef6f`
- `KERNEL32!LeaveCriticalSection` at `0x18003f014`
- `KERNEL32!LeaveCriticalSection` at `0x18003f088`
- `KERNEL32!LeaveCriticalSection` at `0x18003f154`
- `KERNEL32!LeaveCriticalSection` at `0x18003f1c8`
- `KERNEL32!LeaveCriticalSection` at `0x18003f25d`
- `KERNEL32!LeaveCriticalSection` at `0x18003f43a`
- `KERNEL32!LeaveCriticalSection` at `0x18003eed0`
- `KERNEL32!LeaveCriticalSection` at `0x18003ef6f`
- `KERNEL32!LeaveCriticalSection` at `0x18003f014`
- `KERNEL32!LeaveCriticalSection` at `0x18003f088`
- `KERNEL32!LeaveCriticalSection` at `0x18003f154`
- `KERNEL32!LeaveCriticalSection` at `0x18003f1c8`
- `KERNEL32!LeaveCriticalSection` at `0x18003f25d`
- `KERNEL32!LeaveCriticalSection` at `0x18003f43a`
- `KERNEL32!EnterCriticalSection` at `0x18003eea0`
- `KERNEL32!EnterCriticalSection` at `0x18003ef3c`
- `KERNEL32!EnterCriticalSection` at `0x18003efe1`
- `KERNEL32!EnterCriticalSection` at `0x18003f058`
- `KERNEL32!EnterCriticalSection` at `0x18003f11f`
- `KERNEL32!EnterCriticalSection` at `0x18003f198`
- `KERNEL32!EnterCriticalSection` at `0x18003f22a`
- `KERNEL32!EnterCriticalSection` at `0x18003f407`
- `KERNEL32!EnterCriticalSection` at `0x18003f47e`
- `KERNEL32!EnterCriticalSection` at `0x18003eea0`
- `KERNEL32!EnterCriticalSection` at `0x18003ef3c`
- `KERNEL32!EnterCriticalSection` at `0x18003efe1`
- `KERNEL32!EnterCriticalSection` at `0x18003f058`
- `KERNEL32!EnterCriticalSection` at `0x18003f11f`
- `KERNEL32!EnterCriticalSection` at `0x18003f198`
- `KERNEL32!EnterCriticalSection` at `0x18003f22a`
- `KERNEL32!EnterCriticalSection` at `0x18003f407`
- `KERNEL32!EnterCriticalSection` at `0x18003f47e`
- `KERNEL32!GlobalAlloc` at `0x18003f531`
- `KERNEL32!GlobalAlloc` at `0x18003f5bd`
- `KERNEL32!GlobalAlloc` at `0x18003f531`
- `KERNEL32!GlobalAlloc` at `0x18003f5bd`
- `KERNEL32!GlobalFree` at `0x18003ee33`
- `KERNEL32!GlobalFree` at `0x18003ef24`
- `KERNEL32!GlobalFree` at `0x18003f03b`
- `KERNEL32!GlobalFree` at `0x18003f0ad`
- `KERNEL32!GlobalFree` at `0x18003f17b`
- `KERNEL32!GlobalFree` at `0x18003f1ed`
- `KERNEL32!GlobalFree` at `0x18003f3de`
- `KERNEL32!GlobalFree` at `0x18003f461`
- `KERNEL32!GlobalFree` at `0x18003f4b7`
- `KERNEL32!GlobalFree` at `0x18003f4dd`
- `KERNEL32!GlobalFree` at `0x18003f4f2`
- `KERNEL32!GlobalFree` at `0x18003f65d`
- `KERNEL32!GlobalFree` at `0x18003f696`
- `KERNEL32!GlobalFree` at `0x18003f6ab`
- `KERNEL32!GlobalFree` at `0x18003f89d`
- `KERNEL32!GlobalFree` at `0x18003ee33`
- `KERNEL32!GlobalFree` at `0x18003ef24`
- `KERNEL32!GlobalFree` at `0x18003f03b`
- `KERNEL32!GlobalFree` at `0x18003f0ad`
- `KERNEL32!GlobalFree` at `0x18003f17b`
- `KERNEL32!GlobalFree` at `0x18003f1ed`
- `KERNEL32!GlobalFree` at `0x18003f3de`
- `KERNEL32!GlobalFree` at `0x18003f461`
- `KERNEL32!GlobalFree` at `0x18003f4b7`
- `KERNEL32!GlobalFree` at `0x18003f4dd`
- `KERNEL32!GlobalFree` at `0x18003f4f2`
- `KERNEL32!GlobalFree` at `0x18003f65d`
- `KERNEL32!GlobalFree` at `0x18003f696`
- `KERNEL32!GlobalFree` at `0x18003f6ab`
- `KERNEL32!GlobalFree` at `0x18003f89d`
- `KERNEL32!lstrcmpiW` at `0x18003f784`
- `KERNEL32!lstrcmpiW` at `0x18003f784`

## string_xrefs

- `0x18003ee08`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c
bool __fastcall IsPatchAppliedToProduct(const WCHAR *a1, const WCHAR *a2, wchar_t *a3, int a4, char a5)
{
  const WCHAR *v7; // r14
  const WCHAR *v8; // r15
  bool v9; // bl
  bool v10; // di
  const unsigned __int16 *v11; // rcx
  int v12; // r12d
  int v13; // r12d
  int CurrentUserStringSID; // edi
  HGLOBAL v15; // rdi
  __int64 v16; // r9
  int v17; // edi
  __int64 v18; // r9
  unsigned int v20; // edi
  __int64 v21; // r8
  DWORD v22; // r10d
  __int64 v23; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  __int64 v25; // r9
  HKEY v26; // r14
  LSTATUS v27; // eax
  unsigned int v28; // edi
  unsigned int v29; // edx
  DWORD v30; // r9d
  __int64 v31; // r8
  HKEY v32; // r15
  LSTATUS v33; // r14d
  DWORD v34; // edx
  DWORD v35; // edi
  DWORD v36; // edi
  BYTE *v37; // rsi
  DWORD v38; // edi
  DWORD v39; // edi
  BYTE *v40; // rsi
  const WCHAR *v41; // rdi
  const WCHAR *v42; // rax
  __int64 v43; // rdx
  unsigned int v44; // edi
  DWORD v45; // esi
  int v46; // edi
  DWORD v47; // esi
  bool v48; // cc
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v51; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpString2; // [rsp+58h] [rbp-A8h]
  HKEY v54[2]; // [rsp+60h] [rbp-A0h] BYREF
  HGLOBAL v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+78h] [rbp-88h]
  __int16 v57; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION v58; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE lpData; // [rsp+B0h] [rbp-50h] BYREF
  int v60; // [rsp+B8h] [rbp-48h]
  int v61; // [rsp+BCh] [rbp-44h]
  BYTE Data[80]; // [rsp+C0h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+110h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+138h] [rbp+38h] BYREF
  HGLOBAL hMem; // [rsp+160h] [rbp+60h] BYREF
  int v66; // [rsp+168h] [rbp+68h]
  int v67; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 v68[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v69[320]; // [rsp+380h] [rbp+280h] BYREF

  *(_QWORD *)lpcbData = a2;
  lpString2 = a1;
  v7 = a2;
  v8 = a1;
  if ( a1 && a2 )
  {
    v9 = 1;
    v10 = 0;
    if ( a4 == 1 && a3 && *a3 )
      v10 = !IsCurrentUser(a3);
    LODWORD(hKey.LockSemaphore) = 1;
    *(_OWORD *)&hKey.DebugInfo = 0;
    hKey.OwningThread = &hKey.SpinCount;
    LOWORD(hKey.SpinCount) = 0;
    InitializeCriticalSection(&CriticalSection);
    v56 = 1;
    *(_OWORD *)v54 = 0;
    v55 = &v57;
    v57 = 0;
    InitializeCriticalSection(&v58);
    v60 = 33;
    lpData = Data;
    if ( v10 || (unsigned int)OpenSpecificUsersAdvertisedSubKeyPacked(a4, a3, (WCHAR *)L"Products", v7, &hKey, 0) )
      goto LABEL_6;
    EnterCriticalSection(&v58);
    if ( v54[0] )
    {
      RegCloseKey(v54[0]);
      v54[0] = 0;
      *(_WORD *)v55 = 0;
    }
    LeaveCriticalSection(&v58);
    v25 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      v25 = g_samRead | 0x100;
    if ( (unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const WCHAR *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                         hKey.DebugInfo,
                         L"Patches",
                         0,
                         v25,
                         v54) )
    {
LABEL_6:
      v66 = 64;
      v11 = 0;
      hMem = v68;
      if ( a4 && (v12 = a4 - 1) != 0 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 == 1 )
            goto LABEL_76;
        }
        else
        {
          v11 = L"S-1-5-18";
        }
      }
      else if ( a3 )
      {
        v11 = a3;
      }
      else
      {
        v67 = 64;
        CurrentUserStringSID = GetCurrentUserStringSID(&hMem);
        if ( CurrentUserStringSID )
        {
LABEL_11:
          if ( v66 > 64 )
            GlobalFree(hMem);
          if ( !CurrentUserStringSID )
          {
            hMem = v68;
            v66 = 260;
            if ( (int)StringCchPrintfW(v68, 0x104u, L"%s\\%s\\%s\\%s", v69, L"Products", v7, L"Patches") < 0 )
            {
              if ( v66 > 260 )
                GlobalFree(hMem);
            }
            else
            {
              v15 = hMem;
              EnterCriticalSection(&CriticalSection);
              if ( hKey.DebugInfo )
              {
                RegCloseKey((HKEY)hKey.DebugInfo);
                hKey.DebugInfo = 0;
                *(_WORD *)hKey.OwningThread = 0;
              }
              LeaveCriticalSection(&CriticalSection);
              v16 = g_samRead;
              if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
                v16 = g_samRead | 0x100;
              v17 = ((__int64 (__fastcall *)(__int64, HGLOBAL, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
                      -2147483646,
                      v15,
                      0,
                      v16,
                      &hKey);
              if ( v66 > 260 )
                GlobalFree(hMem);
              if ( !v17 )
              {
                EnterCriticalSection(&v58);
                if ( v54[0] )
                {
                  RegCloseKey(v54[0]);
                  v54[0] = 0;
                  *(_WORD *)v55 = 0;
                }
                LeaveCriticalSection(&v58);
                v18 = g_samRead;
                if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
                  v18 = g_samRead | 0x100;
                if ( !(unsigned int)((__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, const WCHAR *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                                      hKey.DebugInfo,
                                      v8,
                                      0,
                                      v18,
                                      v54) )
                {
                  if ( !a5 )
                  {
                    if ( v60 > 33 )
                      GlobalFree(lpData);
                    v60 = 33;
                    lpData = Data;
                    EnterCriticalSection(&v58);
                    if ( v54[0] )
                    {
                      RegCloseKey(v54[0]);
                      v54[0] = 0;
                      *(_WORD *)v55 = 0;
                    }
                    LeaveCriticalSection(&v58);
                    DeleteCriticalSection(&v58);
                    if ( v56 > 1 )
                      GlobalFree(v55);
                    v56 = 1;
                    v55 = &v57;
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
                    return v9;
                  }
                  Type = 0;
                  cbData = 0;
                  lpcbData[0] = 4;
                  if ( RegQueryValueExW(v54[0], L"State", 0, &Type, (LPBYTE)&cbData, lpcbData) || Type != 4 )
                  {
                    v48 = v60 <= 33;
LABEL_152:
                    if ( !v48 )
                      GlobalFree(lpData);
                    v9 = 0;
                    goto LABEL_107;
                  }
                  v9 = cbData == 1;
LABEL_105:
                  if ( v60 > 33 )
                    GlobalFree(lpData);
LABEL_107:
                  v60 = 33;
                  lpData = Data;
                  CRegHandle::~CRegHandle((CRegHandle *)v54);
                  CRegHandle::~CRegHandle((CRegHandle *)&hKey);
                  return v9;
                }
              }
            }
          }
LABEL_76:
          if ( v60 > 33 )
            GlobalFree(lpData);
          v60 = 33;
          lpData = Data;
          EnterCriticalSection(&v58);
          if ( v54[0] )
          {
            RegCloseKey(v54[0]);
            v54[0] = 0;
            *(_WORD *)v55 = 0;
          }
          LeaveCriticalSection(&v58);
          DeleteCriticalSection(&v58);
          if ( v56 > 1 )
            GlobalFree(v55);
          v56 = 1;
          v55 = &v57;
          EnterCriticalSection(&CriticalSection);
          DebugInfo = hKey.DebugInfo;
          if ( !hKey.DebugInfo )
            goto LABEL_52;
          goto LABEL_51;
        }
        v11 = (const unsigned __int16 *)hMem;
      }
      CurrentUserStringSID = StringCchPrintfW(
                               v69,
                               0x13Eu,
                               L"%s\\%s",
                               L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
                               v11);
      goto LABEL_11;
    }
    v26 = v54[0];
    cbData = 2 * v60;
    v61 = 33;
    Type = 0;
    v27 = RegQueryValueExW(v54[0], v8, 0, &Type, lpData, &cbData);
    if ( v27 != 234 )
      goto LABEL_60;
    v35 = cbData;
    if ( Type - 1 > 1 )
    {
      if ( Type != 7 )
        goto LABEL_89;
      v35 = cbData + 4;
    }
    else
    {
      v35 = cbData + 2;
    }
    cbData = v35;
LABEL_89:
    v36 = v35 >> 1;
    if ( (int)v36 > v61 )
    {
      v37 = (BYTE *)GlobalAlloc(0, 2LL * v36);
      if ( !v37 )
        goto LABEL_104;
    }
    else
    {
      v37 = Data;
    }
    if ( lpData != Data )
      GlobalFree(lpData);
    lpData = v37;
    v60 = v36;
    v27 = RegQueryValueExW(v26, v8, 0, 0, v37, &cbData);
LABEL_60:
    if ( !v27 )
    {
      if ( Type - 1 > 1 )
      {
        if ( Type != 7 )
          goto LABEL_68;
        v28 = 2;
      }
      else
      {
        v28 = 1;
      }
      v29 = 0;
      v30 = cbData >> 1;
      v31 = (cbData >> 1) - 1;
      do
      {
        if ( (int)v31 < 0 )
          break;
        if ( *(_WORD *)&lpData[2 * v31] )
          break;
        ++v29;
        v31 = (unsigned int)(v31 - 1);
      }
      while ( v29 < v28 );
      if ( v28 <= v29 )
      {
LABEL_68:
        if ( !a5 )
          goto LABEL_105;
        v32 = v54[0];
        v51 = 0;
        cbData = 2 * v60;
        v61 = 33;
        Type = 0;
        v33 = RegQueryValueExW(v54[0], L"Patches", 0, &Type, lpData, &cbData);
        if ( v33 != 234 )
          goto LABEL_70;
        v38 = cbData;
        if ( Type - 1 > 1 )
        {
          if ( Type != 7 )
            goto LABEL_98;
          v38 = cbData + 4;
        }
        else
        {
          v38 = cbData + 2;
        }
        cbData = v38;
LABEL_98:
        v39 = v38 >> 1;
        if ( (int)v39 > v61 )
        {
          v40 = (BYTE *)GlobalAlloc(0, 2LL * v39);
          if ( !v40 )
            goto LABEL_44;
        }
        else
        {
          v40 = Data;
        }
        if ( lpData != Data )
          GlobalFree(lpData);
        lpData = v40;
        v60 = v39;
        v33 = RegQueryValueExW(v32, L"Patches", 0, &v51, v40, &cbData);
LABEL_70:
        v34 = Type;
        if ( v33 )
          goto LABEL_43;
        if ( Type - 1 <= 1 )
        {
          v20 = 1;
        }
        else
        {
          if ( Type != 7 )
            goto LABEL_43;
          v20 = 2;
        }
        v21 = 0;
        v22 = cbData >> 1;
        v23 = (cbData >> 1) - 1;
        do
        {
          if ( (int)v23 < 0 )
            break;
          if ( *(_WORD *)&lpData[2 * v23] )
            break;
          v21 = (unsigned int)(v21 + 1);
          v23 = (unsigned int)(v23 - 1);
        }
        while ( (unsigned int)v21 < v20 );
        if ( v20 > (unsigned int)v21 )
        {
          v46 = v20 - v21;
          v47 = v22 + v46;
          if ( v22 + v46 > v60 )
          {
            LOBYTE(v21) = 1;
            if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&lpData, v47, v21) )
              goto LABEL_44;
            v34 = Type;
          }
          if ( v46 )
          {
            do
              *(_WORD *)&lpData[2 * (v47 - v46--)] = 0;
            while ( v46 );
            v34 = Type;
            v51 = Type;
            goto LABEL_121;
          }
        }
LABEL_43:
        v51 = v34;
        if ( v33 )
          goto LABEL_44;
LABEL_121:
        if ( v34 == 7 )
        {
          v41 = (const WCHAR *)lpData;
          v8 = lpString2;
          while ( *v41 )
          {
            v42 = v41;
            v43 = 33;
            do
            {
              if ( !*v42 )
                break;
              ++v42;
              --v43;
            }
            while ( v43 );
            if ( !v43 || ((33 - v43) & -(__int64)(v43 != 0)) != 0x20 )
            {
              v48 = v60 <= 33;
              goto LABEL_152;
            }
            if ( !lstrcmpiW(v41, v8) )
              goto LABEL_105;
            v41 += 33;
          }
          goto LABEL_104;
        }
LABEL_44:
        if ( v60 > 33 )
          GlobalFree(lpData);
        v60 = 33;
        lpData = Data;
        EnterCriticalSection(&v58);
        if ( v54[0] )
        {
          RegCloseKey(v54[0]);
          v54[0] = 0;
          *(_WORD *)v55 = 0;
        }
        LeaveCriticalSection(&v58);
        DeleteCriticalSection(&v58);
        if ( v56 > 1 )
          GlobalFree(v55);
        v56 = 1;
        v55 = &v57;
        EnterCriticalSection(&CriticalSection);
        DebugInfo = hKey.DebugInfo;
        if ( !hKey.DebugInfo )
          goto LABEL_52;
LABEL_51:
        RegCloseKey((HKEY)DebugInfo);
        hKey.DebugInfo = 0;
        *(_WORD *)hKey.OwningThread = 0;
LABEL_52:
        LeaveCriticalSection(&CriticalSection);
        DeleteCriticalSection(&CriticalSection);
        if ( SLODWORD(hKey.LockSemaphore) > 1 )
          GlobalFree(hKey.OwningThread);
        return 0;
      }
      v44 = v28 - v29;
      v45 = v30 + v44;
      if ( v30 + v44 <= v60
        || (LOBYTE(v31) = 1, (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&lpData, v45, v31)) )
      {
        for ( ; v44; --v44 )
          *(_WORD *)&lpData[2 * (v45 - v44)] = 0;
        goto LABEL_68;
      }
    }
LABEL_104:
    v7 = *(const WCHAR **)lpcbData;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x18003ecd4  mov     [rsp-8+arg_18], rbx
0x18003ecd9  push    rbp
0x18003ecda  push    rsi
0x18003ecdb  push    rdi
0x18003ecdc  push    r12
0x18003ecde  push    r13
0x18003ece0  push    r14
0x18003ece2  push    r15
0x18003ece4  lea     rbp, [rsp-510h]
0x18003ecec  sub     rsp, 610h
0x18003ecf3  mov     rax, cs:__security_cookie
0x18003ecfa  xor     rax, rsp
0x18003ecfd  mov     [rbp+540h+var_40], rax
0x18003ed04  xor     esi, esi
0x18003ed06  mov     qword ptr [rsp+640h+var_5F0], rdx
0x18003ed0b  mov     [rsp+640h+lpString2], rcx
0x18003ed10  mov     r12d, r9d
0x18003ed13  mov     r13, r8
0x18003ed16  mov     r14, rdx
0x18003ed19  mov     r15, rcx
0x18003ed1c  test    rcx, rcx
0x18003ed1f  jz      loc_18003F1F9
0x18003ed25  test    rdx, rdx
0x18003ed28  jz      loc_18003F1F9
0x18003ed2e  lea     ebx, [rsi+1]
0x18003ed31  movzx   edi, sil
0x18003ed35  cmp     r9d, ebx
0x18003ed38  jz      loc_18003F79E
0x18003ed3e  xorps   xmm0, xmm0
0x18003ed41  mov     [rbp+540h+var_518], ebx
0x18003ed44  lea     rax, [rbp+540h+var_510]
0x18003ed48  movdqa  xmmword ptr [rbp+540h+hKey], xmm0
0x18003ed4d  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003ed51  mov     [rbp+540h+var_520], rax
0x18003ed55  mov     [rbp+540h+var_510], si
0x18003ed59  call    cs:__imp_InitializeCriticalSection
0x18003ed60  nop     dword ptr [rax+rax+00h]
0x18003ed65  xorps   xmm0, xmm0
0x18003ed68  mov     [rsp+640h+var_5C8], ebx
0x18003ed6c  lea     rax, [rbp+540h+var_5C0]
0x18003ed70  movdqa  xmmword ptr [rsp+640h+var_5E0], xmm0
0x18003ed76  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003ed7a  mov     [rsp+640h+var_5D0], rax
0x18003ed7f  mov     [rbp+540h+var_5C0], si
0x18003ed83  call    cs:__imp_InitializeCriticalSection
0x18003ed8a  nop     dword ptr [rax+rax+00h]
0x18003ed8f  mov     [rbp+540h+var_588], 21h ; '!'
0x18003ed96  lea     rax, [rbp+540h+Data]
0x18003ed9a  mov     [rbp+540h+var_590], rax
0x18003ed9e  test    dil, dil
0x18003eda1  jnz     short loc_18003EDCE
0x18003eda3  lea     rax, [rbp+540h+hKey]
0x18003eda7  mov     byte ptr [rsp+640h+lpcbData], sil
0x18003edac  mov     r9, r14
0x18003edaf  mov     [rsp+640h+lpData], rax
0x18003edb4  lea     r8, aProducts; "Products"
0x18003edbb  mov     rdx, r13
0x18003edbe  mov     ecx, r12d
0x18003edc1  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18003edc6  test    eax, eax
0x18003edc8  jz      loc_18003F226
0x18003edce  lea     rax, [rbp+540h+var_4D0]
0x18003edd2  mov     edx, 40h ; '@'
0x18003edd7  mov     [rbp+540h+var_4D8], edx
0x18003edda  mov     rcx, rsi
0x18003eddd  mov     [rbp+540h+hMem], rax
0x18003ede1  test    r12d, r12d
0x18003ede4  jz      loc_18003F66E
0x18003edea  sub     r12d, ebx
0x18003eded  jz      loc_18003F66E
0x18003edf3  sub     r12d, ebx
0x18003edf6  jnz     loc_18003F85E
0x18003edfc  lea     rcx, aS1518_0; "S-1-5-18"
0x18003ee03  mov     [rsp+640h+lpData], rcx
0x18003ee08  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ee0f  lea     rcx, [rbp+540h+var_2C0]; unsigned __int16 *
0x18003ee16  mov     edx, 13Eh; unsigned __int64
0x18003ee1b  lea     r8, aSS_0; "%s\\%s"
0x18003ee22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ee27  mov     edi, eax
0x18003ee29  cmp     [rbp+540h+var_4D8], 40h ; '@'
0x18003ee2d  jle     short loc_18003EE3F
0x18003ee2f  mov     rcx, [rbp+540h+hMem]; hMem
0x18003ee33  call    cs:__imp_GlobalFree
0x18003ee3a  nop     dword ptr [rax+rax+00h]
0x18003ee3f  test    edi, edi
0x18003ee41  jnz     loc_18003F3EA
0x18003ee47  lea     rax, [rbp+540h+var_4D0]
0x18003ee4b  mov     r12d, 104h
0x18003ee51  mov     [rbp+540h+hMem], rax
0x18003ee55  lea     r9, [rbp+540h+var_2C0]
0x18003ee5c  lea     rax, ValueName; "Patches"
0x18003ee63  mov     [rbp+540h+var_4D8], r12d
0x18003ee67  mov     [rsp+640h+var_610], rax
0x18003ee6c  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18003ee73  lea     rax, aProducts; "Products"
0x18003ee7a  mov     [rsp+640h+lpcbData], r14
0x18003ee7f  mov     edx, r12d; unsigned __int64
0x18003ee82  mov     [rsp+640h+lpData], rax
0x18003ee87  lea     rcx, [rbp+540h+var_4D0]; unsigned __int16 *
0x18003ee8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ee90  test    eax, eax
0x18003ee92  js      loc_18003F3D4
0x18003ee98  mov     rdi, [rbp+540h+hMem]
0x18003ee9c  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003eea0  call    cs:__imp_EnterCriticalSection
0x18003eea7  nop     dword ptr [rax+rax+00h]
0x18003eeac  mov     rcx, [rbp+540h+hKey]; hKey
0x18003eeb0  test    rcx, rcx
0x18003eeb3  jz      short loc_18003EECC
0x18003eeb5  call    cs:__imp_RegCloseKey
0x18003eebc  nop     dword ptr [rax+rax+00h]
0x18003eec1  mov     rax, [rbp+540h+var_520]
0x18003eec5  mov     [rbp+540h+hKey], rsi
0x18003eec9  mov     [rax], si
0x18003eecc  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003eed0  call    cs:__imp_LeaveCriticalSection
0x18003eed7  nop     dword ptr [rax+rax+00h]
0x18003eedc  cmp     cs:?g_fWoW@@3_NA, sil; bool g_fWoW
0x18003eee3  mov     r14d, 100h
0x18003eee9  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003eef0  jz      loc_18003F6BC
0x18003eef6  lea     rax, [rbp+540h+hKey]
0x18003eefa  xor     r8d, r8d
0x18003eefd  mov     [rsp+640h+lpData], rax
0x18003ef02  mov     rdx, rdi
0x18003ef05  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003ef0c  mov     rcx, 0FFFFFFFF80000002h
0x18003ef13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef18  mov     edi, eax
0x18003ef1a  cmp     [rbp+540h+var_4D8], r12d
0x18003ef1e  jle     short loc_18003EF30
0x18003ef20  mov     rcx, [rbp+540h+hMem]; hMem
0x18003ef24  call    cs:__imp_GlobalFree
0x18003ef2b  nop     dword ptr [rax+rax+00h]
0x18003ef30  test    edi, edi
0x18003ef32  jnz     loc_18003F3EA
0x18003ef38  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003ef3c  call    cs:__imp_EnterCriticalSection
0x18003ef43  nop     dword ptr [rax+rax+00h]
0x18003ef48  mov     rcx, [rsp+640h+var_5E0]; hKey
0x18003ef4d  test    rcx, rcx
0x18003ef50  jz      short loc_18003EF6B
0x18003ef52  call    cs:__imp_RegCloseKey
0x18003ef59  nop     dword ptr [rax+rax+00h]
0x18003ef5e  mov     rax, [rsp+640h+var_5D0]
0x18003ef63  mov     [rsp+640h+var_5E0], rsi
0x18003ef68  mov     [rax], si
0x18003ef6b  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003ef6f  call    cs:__imp_LeaveCriticalSection
0x18003ef76  nop     dword ptr [rax+rax+00h]
0x18003ef7b  cmp     cs:?g_fWoW@@3_NA, sil; bool g_fWoW
0x18003ef82  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x18003ef89  jz      loc_18003F6DA
0x18003ef8f  mov     rcx, [rbp+540h+hKey]
0x18003ef93  lea     rax, [rsp+640h+var_5E0]
0x18003ef98  mov     [rsp+640h+lpData], rax
0x18003ef9d  xor     r8d, r8d
0x18003efa0  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18003efa7  mov     rdx, r15
0x18003efaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efaf  test    eax, eax
0x18003efb1  jnz     loc_18003F3EA
0x18003efb7  cmp     [rbp+540h+arg_20], sil
0x18003efbe  jnz     loc_18003F8B8
0x18003efc4  cmp     [rbp+540h+var_588], 21h ; '!'
0x18003efc8  jg      loc_18003F4B3
0x18003efce  lea     rax, [rbp+540h+Data]
0x18003efd2  mov     [rbp+540h+var_588], 21h ; '!'
0x18003efd9  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003efdd  mov     [rbp+540h+var_590], rax
0x18003efe1  call    cs:__imp_EnterCriticalSection
0x18003efe8  nop     dword ptr [rax+rax+00h]
0x18003efed  mov     rcx, [rsp+640h+var_5E0]; hKey
0x18003eff2  test    rcx, rcx
0x18003eff5  jz      short loc_18003F010
0x18003eff7  call    cs:__imp_RegCloseKey
0x18003effe  nop     dword ptr [rax+rax+00h]
0x18003f003  mov     rax, [rsp+640h+var_5D0]
0x18003f008  mov     [rsp+640h+var_5E0], rsi
0x18003f00d  mov     [rax], si
0x18003f010  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003f014  call    cs:__imp_LeaveCriticalSection
0x18003f01b  nop     dword ptr [rax+rax+00h]
0x18003f020  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003f024  call    cs:__imp_DeleteCriticalSection
0x18003f02b  nop     dword ptr [rax+rax+00h]
0x18003f030  cmp     [rsp+640h+var_5C8], ebx
0x18003f034  jle     short loc_18003F047
0x18003f036  mov     rcx, [rsp+640h+var_5D0]; hMem
0x18003f03b  call    cs:__imp_GlobalFree
0x18003f042  nop     dword ptr [rax+rax+00h]
0x18003f047  lea     rax, [rbp+540h+var_5C0]
0x18003f04b  mov     [rsp+640h+var_5C8], ebx
0x18003f04f  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f053  mov     [rsp+640h+var_5D0], rax
0x18003f058  call    cs:__imp_EnterCriticalSection
0x18003f05f  nop     dword ptr [rax+rax+00h]
0x18003f064  mov     rcx, [rbp+540h+hKey]; hKey
0x18003f068  test    rcx, rcx
0x18003f06b  jz      short loc_18003F084
0x18003f06d  call    cs:__imp_RegCloseKey
0x18003f074  nop     dword ptr [rax+rax+00h]
0x18003f079  mov     rcx, [rbp+540h+var_520]
0x18003f07d  mov     [rbp+540h+hKey], rsi
0x18003f081  mov     [rcx], si
0x18003f084  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f088  call    cs:__imp_LeaveCriticalSection
0x18003f08f  nop     dword ptr [rax+rax+00h]
0x18003f094  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f098  call    cs:__imp_DeleteCriticalSection
0x18003f09f  nop     dword ptr [rax+rax+00h]
0x18003f0a4  cmp     [rbp+540h+var_518], ebx
0x18003f0a7  jle     short loc_18003F0B9
0x18003f0a9  mov     rcx, [rbp+540h+var_520]; hMem
0x18003f0ad  call    cs:__imp_GlobalFree
0x18003f0b4  nop     dword ptr [rax+rax+00h]
0x18003f0b9  mov     al, bl
0x18003f0bb  jmp     loc_18003F1FB
0x18003f0c0  mov     edi, ebx
0x18003f0c2  mov     r10d, [rsp+640h+cbData]
0x18003f0c7  mov     r8d, esi
0x18003f0ca  shr     r10d, 1
0x18003f0cd  lea     r9d, [r10-1]
0x18003f0d1  test    r9d, r9d
0x18003f0d4  js      short loc_18003F0EC
0x18003f0d6  mov     rax, [rbp+540h+var_590]
0x18003f0da  cmp     [rax+r9*2], si
0x18003f0df  jnz     short loc_18003F0EC
0x18003f0e1  add     r8d, ebx
0x18003f0e4  sub     r9d, ebx
0x18003f0e7  cmp     r8d, edi
0x18003f0ea  jb      short loc_18003F0D1
0x18003f0ec  cmp     edi, r8d
0x18003f0ef  ja      loc_18003F833
0x18003f0f5  mov     [rsp+640h+var_5F8], edx
0x18003f0f9  test    r14d, r14d
0x18003f0fc  jz      loc_18003F724
0x18003f102  cmp     [rbp+540h+var_588], 21h ; '!'
0x18003f106  jg      loc_18003F4D9
0x18003f10c  lea     rax, [rbp+540h+Data]
0x18003f110  mov     [rbp+540h+var_588], 21h ; '!'
0x18003f117  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003f11b  mov     [rbp+540h+var_590], rax
0x18003f11f  call    cs:__imp_EnterCriticalSection
0x18003f126  nop     dword ptr [rax+rax+00h]
0x18003f12b  mov     rcx, [rsp+640h+var_5E0]; hKey
0x18003f130  xor     edi, edi
0x18003f132  test    rcx, rcx
0x18003f135  jz      short loc_18003F150
0x18003f137  call    cs:__imp_RegCloseKey
0x18003f13e  nop     dword ptr [rax+rax+00h]
0x18003f143  mov     rax, [rsp+640h+var_5D0]
0x18003f148  mov     [rsp+640h+var_5E0], rdi
0x18003f14d  mov     [rax], di
0x18003f150  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003f154  call    cs:__imp_LeaveCriticalSection
0x18003f15b  nop     dword ptr [rax+rax+00h]
0x18003f160  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18003f164  call    cs:__imp_DeleteCriticalSection
0x18003f16b  nop     dword ptr [rax+rax+00h]
0x18003f170  cmp     [rsp+640h+var_5C8], ebx
0x18003f174  jle     short loc_18003F187
0x18003f176  mov     rcx, [rsp+640h+var_5D0]; hMem
0x18003f17b  call    cs:__imp_GlobalFree
0x18003f182  nop     dword ptr [rax+rax+00h]
0x18003f187  lea     rax, [rbp+540h+var_5C0]
0x18003f18b  mov     [rsp+640h+var_5C8], ebx
0x18003f18f  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f193  mov     [rsp+640h+var_5D0], rax
0x18003f198  call    cs:__imp_EnterCriticalSection
0x18003f19f  nop     dword ptr [rax+rax+00h]
0x18003f1a4  mov     rcx, [rbp+540h+hKey]; hKey
0x18003f1a8  test    rcx, rcx
0x18003f1ab  jz      short loc_18003F1C4
0x18003f1ad  call    cs:__imp_RegCloseKey
0x18003f1b4  nop     dword ptr [rax+rax+00h]
0x18003f1b9  mov     rax, [rbp+540h+var_520]
0x18003f1bd  mov     [rbp+540h+hKey], rdi
0x18003f1c1  mov     [rax], di
0x18003f1c4  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f1c8  call    cs:__imp_LeaveCriticalSection
0x18003f1cf  nop     dword ptr [rax+rax+00h]
0x18003f1d4  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18003f1d8  call    cs:__imp_DeleteCriticalSection
0x18003f1df  nop     dword ptr [rax+rax+00h]
0x18003f1e4  cmp     [rbp+540h+var_518], ebx
0x18003f1e7  jle     short loc_18003F1F9
0x18003f1e9  mov     rcx, [rbp+540h+var_520]; hMem
0x18003f1ed  call    cs:__imp_GlobalFree
0x18003f1f4  nop     dword ptr [rax+rax+00h]
0x18003f1f9  xor     al, al
0x18003f1fb  mov     rcx, [rbp+540h+var_40]
0x18003f202  xor     rcx, rsp; StackCookie
0x18003f205  call    __security_check_cookie
0x18003f20a  mov     rbx, [rsp+640h+arg_18]
0x18003f212  add     rsp, 610h
0x18003f219  pop     r15
0x18003f21b  pop     r14
0x18003f21d  pop     r13
  ... truncated ...
```
