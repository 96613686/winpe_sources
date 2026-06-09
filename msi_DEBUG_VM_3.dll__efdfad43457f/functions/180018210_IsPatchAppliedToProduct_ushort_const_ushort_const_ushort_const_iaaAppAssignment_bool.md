# IsPatchAppliedToProduct(ushort const *,ushort const *,ushort const *,iaaAppAssignment,bool)

- ea: `0x180018210`
- end: `0x180018d01`
- name: `?IsPatchAppliedToProduct@@YA_NPEBG00W4iaaAppAssignment@@_N@Z`
- size: `2801`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015ac0`
- `0x180017b28`
- `0x180018d10`
- `0x180046dbc`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180018210`
- `0x180022120`
- `0x1800227d0`
- `0x1800250d4`
- `0x180071fdc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180018758`
- `ADVAPI32!RegQueryValueExW` at `0x180018800`
- `ADVAPI32!RegQueryValueExW` at `0x18001899d`
- `ADVAPI32!RegQueryValueExW` at `0x180018a23`
- `ADVAPI32!RegQueryValueExW` at `0x180018cde`
- `ADVAPI32!RegQueryValueExW` at `0x180018758`
- `ADVAPI32!RegQueryValueExW` at `0x180018800`
- `ADVAPI32!RegQueryValueExW` at `0x18001899d`
- `ADVAPI32!RegQueryValueExW` at `0x180018a23`
- `ADVAPI32!RegQueryValueExW` at `0x180018cde`
- `ADVAPI32!RegCloseKey` at `0x1800183d9`
- `ADVAPI32!RegCloseKey` at `0x18001845e`
- `ADVAPI32!RegCloseKey` at `0x1800184f1`
- `ADVAPI32!RegCloseKey` at `0x180018549`
- `ADVAPI32!RegCloseKey` at `0x1800185f5`
- `ADVAPI32!RegCloseKey` at `0x18001864d`
- `ADVAPI32!RegCloseKey` at `0x1800186c1`
- `ADVAPI32!RegCloseKey` at `0x18001887a`
- `ADVAPI32!RegCloseKey` at `0x1800188d6`
- `ADVAPI32!RegCloseKey` at `0x1800183d9`
- `ADVAPI32!RegCloseKey` at `0x18001845e`
- `ADVAPI32!RegCloseKey` at `0x1800184f1`
- `ADVAPI32!RegCloseKey` at `0x180018549`
- `ADVAPI32!RegCloseKey` at `0x1800185f5`
- `ADVAPI32!RegCloseKey` at `0x18001864d`
- `ADVAPI32!RegCloseKey` at `0x1800186c1`
- `ADVAPI32!RegCloseKey` at `0x18001887a`
- `ADVAPI32!RegCloseKey` at `0x1800188d6`
- `KERNEL32!InitializeCriticalSection` at `0x180018295`
- `KERNEL32!InitializeCriticalSection` at `0x1800182b9`
- `KERNEL32!InitializeCriticalSection` at `0x180018295`
- `KERNEL32!InitializeCriticalSection` at `0x1800182b9`
- `KERNEL32!DeleteCriticalSection` at `0x180018512`
- `KERNEL32!DeleteCriticalSection` at `0x180018568`
- `KERNEL32!DeleteCriticalSection` at `0x180018616`
- `KERNEL32!DeleteCriticalSection` at `0x18001866c`
- `KERNEL32!DeleteCriticalSection` at `0x18001889b`
- `KERNEL32!DeleteCriticalSection` at `0x180018512`
- `KERNEL32!DeleteCriticalSection` at `0x180018568`
- `KERNEL32!DeleteCriticalSection` at `0x180018616`
- `KERNEL32!DeleteCriticalSection` at `0x18001866c`
- `KERNEL32!DeleteCriticalSection` at `0x18001889b`
- `KERNEL32!LeaveCriticalSection` at `0x1800183ee`
- `KERNEL32!LeaveCriticalSection` at `0x180018475`
- `KERNEL32!LeaveCriticalSection` at `0x180018508`
- `KERNEL32!LeaveCriticalSection` at `0x18001855e`
- `KERNEL32!LeaveCriticalSection` at `0x18001860c`
- `KERNEL32!LeaveCriticalSection` at `0x180018662`
- `KERNEL32!LeaveCriticalSection` at `0x1800186d8`
- `KERNEL32!LeaveCriticalSection` at `0x180018891`
- `KERNEL32!LeaveCriticalSection` at `0x1800183ee`
- `KERNEL32!LeaveCriticalSection` at `0x180018475`
- `KERNEL32!LeaveCriticalSection` at `0x180018508`
- `KERNEL32!LeaveCriticalSection` at `0x18001855e`
- `KERNEL32!LeaveCriticalSection` at `0x18001860c`
- `KERNEL32!LeaveCriticalSection` at `0x180018662`
- `KERNEL32!LeaveCriticalSection` at `0x1800186d8`
- `KERNEL32!LeaveCriticalSection` at `0x180018891`
- `KERNEL32!EnterCriticalSection` at `0x1800183ca`
- `KERNEL32!EnterCriticalSection` at `0x18001844e`
- `KERNEL32!EnterCriticalSection` at `0x1800184e1`
- `KERNEL32!EnterCriticalSection` at `0x18001853a`
- `KERNEL32!EnterCriticalSection` at `0x1800185e3`
- `KERNEL32!EnterCriticalSection` at `0x18001863e`
- `KERNEL32!EnterCriticalSection` at `0x1800186b1`
- `KERNEL32!EnterCriticalSection` at `0x18001886a`
- `KERNEL32!EnterCriticalSection` at `0x1800188c3`
- `KERNEL32!EnterCriticalSection` at `0x1800183ca`
- `KERNEL32!EnterCriticalSection` at `0x18001844e`
- `KERNEL32!EnterCriticalSection` at `0x1800184e1`
- `KERNEL32!EnterCriticalSection` at `0x18001853a`
- `KERNEL32!EnterCriticalSection` at `0x1800185e3`
- `KERNEL32!EnterCriticalSection` at `0x18001863e`
- `KERNEL32!EnterCriticalSection` at `0x1800186b1`
- `KERNEL32!EnterCriticalSection` at `0x18001886a`
- `KERNEL32!EnterCriticalSection` at `0x1800188c3`
- `KERNEL32!GlobalAlloc` at `0x180018958`
- `KERNEL32!GlobalAlloc` at `0x1800189d8`
- `KERNEL32!GlobalAlloc` at `0x180018958`
- `KERNEL32!GlobalAlloc` at `0x1800189d8`
- `KERNEL32!GlobalFree` at `0x180018363`
- `KERNEL32!GlobalFree` at `0x18001843c`
- `KERNEL32!GlobalFree` at `0x180018523`
- `KERNEL32!GlobalFree` at `0x180018577`
- `KERNEL32!GlobalFree` at `0x180018627`
- `KERNEL32!GlobalFree` at `0x18001867b`
- `KERNEL32!GlobalFree` at `0x180018847`
- `KERNEL32!GlobalFree` at `0x1800188ac`
- `KERNEL32!GlobalFree` at `0x1800188f0`
- `KERNEL32!GlobalFree` at `0x180018910`
- `KERNEL32!GlobalFree` at `0x18001891f`
- `KERNEL32!GlobalFree` at `0x180018a6c`
- `KERNEL32!GlobalFree` at `0x180018a9f`
- `KERNEL32!GlobalFree` at `0x180018aae`
- `KERNEL32!GlobalFree` at `0x180018c91`
- `KERNEL32!GlobalFree` at `0x180018363`
- `KERNEL32!GlobalFree` at `0x18001843c`
- `KERNEL32!GlobalFree` at `0x180018523`
- `KERNEL32!GlobalFree` at `0x180018577`
- `KERNEL32!GlobalFree` at `0x180018627`
- `KERNEL32!GlobalFree` at `0x18001867b`
- `KERNEL32!GlobalFree` at `0x180018847`
- `KERNEL32!GlobalFree` at `0x1800188ac`
- `KERNEL32!GlobalFree` at `0x1800188f0`
- `KERNEL32!GlobalFree` at `0x180018910`
- `KERNEL32!GlobalFree` at `0x18001891f`
- `KERNEL32!GlobalFree` at `0x180018a6c`
- `KERNEL32!GlobalFree` at `0x180018a9f`
- `KERNEL32!GlobalFree` at `0x180018aae`
- `KERNEL32!GlobalFree` at `0x180018c91`
- `KERNEL32!lstrcmpiW` at `0x180018b7e`
- `KERNEL32!lstrcmpiW` at `0x180018b7e`

## string_xrefs

- `0x180018338`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

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
0x180018210  mov     [rsp-8+arg_18], rbx
0x180018215  push    rbp
0x180018216  push    rsi
0x180018217  push    rdi
0x180018218  push    r12
0x18001821a  push    r13
0x18001821c  push    r14
0x18001821e  push    r15
0x180018220  lea     rbp, [rsp-510h]
0x180018228  sub     rsp, 610h
0x18001822f  mov     rax, cs:__security_cookie
0x180018236  xor     rax, rsp
0x180018239  mov     [rbp+540h+var_40], rax
0x180018240  xor     esi, esi
0x180018242  mov     qword ptr [rsp+640h+var_5F0], rdx
0x180018247  mov     [rsp+640h+lpString2], rcx
0x18001824c  mov     r12d, r9d
0x18001824f  mov     r13, r8
0x180018252  mov     r14, rdx
0x180018255  mov     r15, rcx
0x180018258  test    rcx, rcx
0x18001825b  jz      loc_180018681
0x180018261  test    rdx, rdx
0x180018264  jz      loc_180018681
0x18001826a  lea     ebx, [rsi+1]
0x18001826d  movzx   edi, sil
0x180018271  cmp     r9d, ebx
0x180018274  jz      loc_180018B92
0x18001827a  xorps   xmm0, xmm0
0x18001827d  mov     [rbp+540h+var_518], ebx
0x180018280  lea     rax, [rbp+540h+var_510]
0x180018284  movdqa  xmmword ptr [rbp+540h+hKey], xmm0
0x180018289  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18001828d  mov     [rbp+540h+var_520], rax
0x180018291  mov     [rbp+540h+var_510], si
0x180018295  call    cs:__imp_InitializeCriticalSection
0x18001829b  xorps   xmm0, xmm0
0x18001829e  mov     [rsp+640h+var_5C8], ebx
0x1800182a2  lea     rax, [rbp+540h+var_5C0]
0x1800182a6  movdqa  xmmword ptr [rsp+640h+var_5E0], xmm0
0x1800182ac  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x1800182b0  mov     [rsp+640h+var_5D0], rax
0x1800182b5  mov     [rbp+540h+var_5C0], si
0x1800182b9  call    cs:__imp_InitializeCriticalSection
0x1800182bf  mov     [rbp+540h+var_588], 21h ; '!'
0x1800182c6  lea     rax, [rbp+540h+Data]
0x1800182ca  mov     [rbp+540h+var_590], rax
0x1800182ce  test    dil, dil
0x1800182d1  jnz     short loc_1800182FE
0x1800182d3  lea     rax, [rbp+540h+hKey]
0x1800182d7  mov     byte ptr [rsp+640h+lpcbData], sil
0x1800182dc  mov     r9, r14
0x1800182df  mov     [rsp+640h+lpData], rax
0x1800182e4  lea     r8, aProducts; "Products"
0x1800182eb  mov     rdx, r13
0x1800182ee  mov     ecx, r12d
0x1800182f1  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x1800182f6  test    eax, eax
0x1800182f8  jz      loc_1800186AD
0x1800182fe  lea     rax, [rbp+540h+var_4D0]
0x180018302  mov     edx, 40h ; '@'
0x180018307  mov     [rbp+540h+var_4D8], edx
0x18001830a  mov     rcx, rsi
0x18001830d  mov     [rbp+540h+hMem], rax
0x180018311  test    r12d, r12d
0x180018314  jz      loc_180018A77
0x18001831a  sub     r12d, ebx
0x18001831d  jz      loc_180018A77
0x180018323  sub     r12d, ebx
0x180018326  jnz     loc_180018C52
0x18001832c  lea     rcx, aS1518; "S-1-5-18"
0x180018333  mov     [rsp+640h+lpData], rcx
0x180018338  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001833f  lea     rcx, [rbp+540h+var_2C0]; unsigned __int16 *
0x180018346  mov     edx, 13Eh; unsigned __int64
0x18001834b  lea     r8, aSS_0; "%s\\%s"
0x180018352  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018357  mov     edi, eax
0x180018359  cmp     [rbp+540h+var_4D8], 40h ; '@'
0x18001835d  jle     short loc_180018369
0x18001835f  mov     rcx, [rbp+540h+hMem]; hMem
0x180018363  call    cs:__imp_GlobalFree
0x180018369  test    edi, edi
0x18001836b  jnz     loc_18001884D
0x180018371  lea     rax, [rbp+540h+var_4D0]
0x180018375  mov     r12d, 104h
0x18001837b  mov     [rbp+540h+hMem], rax
0x18001837f  lea     r9, [rbp+540h+var_2C0]
0x180018386  lea     rax, ValueName; "Patches"
0x18001838d  mov     [rbp+540h+var_4D8], r12d
0x180018391  mov     [rsp+640h+var_610], rax
0x180018396  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18001839d  lea     rax, aProducts; "Products"
0x1800183a4  mov     [rsp+640h+lpcbData], r14
0x1800183a9  mov     edx, r12d; unsigned __int64
0x1800183ac  mov     [rsp+640h+lpData], rax
0x1800183b1  lea     rcx, [rbp+540h+var_4D0]; unsigned __int16 *
0x1800183b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800183ba  test    eax, eax
0x1800183bc  js      loc_18001883D
0x1800183c2  mov     rdi, [rbp+540h+hMem]
0x1800183c6  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x1800183ca  call    cs:__imp_EnterCriticalSection
0x1800183d0  mov     rcx, [rbp+540h+hKey]; hKey
0x1800183d4  test    rcx, rcx
0x1800183d7  jz      short loc_1800183EA
0x1800183d9  call    cs:__imp_RegCloseKey
0x1800183df  mov     rax, [rbp+540h+var_520]
0x1800183e3  mov     [rbp+540h+hKey], rsi
0x1800183e7  mov     [rax], si
0x1800183ea  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x1800183ee  call    cs:__imp_LeaveCriticalSection
0x1800183f4  cmp     cs:?g_fWoW@@3_NA, sil; bool g_fWoW
0x1800183fb  mov     r14d, 100h
0x180018401  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180018408  jz      loc_180018AB6
0x18001840e  lea     rax, [rbp+540h+hKey]
0x180018412  xor     r8d, r8d
0x180018415  mov     [rsp+640h+lpData], rax
0x18001841a  mov     rdx, rdi
0x18001841d  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180018424  mov     rcx, 0FFFFFFFF80000002h
0x18001842b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018430  mov     edi, eax
0x180018432  cmp     [rbp+540h+var_4D8], r12d
0x180018436  jle     short loc_180018442
0x180018438  mov     rcx, [rbp+540h+hMem]; hMem
0x18001843c  call    cs:__imp_GlobalFree
0x180018442  test    edi, edi
0x180018444  jnz     loc_18001884D
0x18001844a  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18001844e  call    cs:__imp_EnterCriticalSection
0x180018454  mov     rcx, [rsp+640h+var_5E0]; hKey
0x180018459  test    rcx, rcx
0x18001845c  jz      short loc_180018471
0x18001845e  call    cs:__imp_RegCloseKey
0x180018464  mov     rax, [rsp+640h+var_5D0]
0x180018469  mov     [rsp+640h+var_5E0], rsi
0x18001846e  mov     [rax], si
0x180018471  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x180018475  call    cs:__imp_LeaveCriticalSection
0x18001847b  cmp     cs:?g_fWoW@@3_NA, sil; bool g_fWoW
0x180018482  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x180018489  jz      loc_180018AD4
0x18001848f  mov     rcx, [rbp+540h+hKey]
0x180018493  lea     rax, [rsp+640h+var_5E0]
0x180018498  mov     [rsp+640h+lpData], rax
0x18001849d  xor     r8d, r8d
0x1800184a0  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1800184a7  mov     rdx, r15
0x1800184aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184af  test    eax, eax
0x1800184b1  jnz     loc_18001884D
0x1800184b7  cmp     [rbp+540h+arg_20], sil
0x1800184be  jnz     loc_180018CA6
0x1800184c4  cmp     [rbp+540h+var_588], 21h ; '!'
0x1800184c8  jg      loc_1800188EC
0x1800184ce  lea     rax, [rbp+540h+Data]
0x1800184d2  mov     [rbp+540h+var_588], 21h ; '!'
0x1800184d9  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x1800184dd  mov     [rbp+540h+var_590], rax
0x1800184e1  call    cs:__imp_EnterCriticalSection
0x1800184e7  mov     rcx, [rsp+640h+var_5E0]; hKey
0x1800184ec  test    rcx, rcx
0x1800184ef  jz      short loc_180018504
0x1800184f1  call    cs:__imp_RegCloseKey
0x1800184f7  mov     rax, [rsp+640h+var_5D0]
0x1800184fc  mov     [rsp+640h+var_5E0], rsi
0x180018501  mov     [rax], si
0x180018504  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x180018508  call    cs:__imp_LeaveCriticalSection
0x18001850e  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x180018512  call    cs:__imp_DeleteCriticalSection
0x180018518  cmp     [rsp+640h+var_5C8], ebx
0x18001851c  jle     short loc_180018529
0x18001851e  mov     rcx, [rsp+640h+var_5D0]; hMem
0x180018523  call    cs:__imp_GlobalFree
0x180018529  lea     rax, [rbp+540h+var_5C0]
0x18001852d  mov     [rsp+640h+var_5C8], ebx
0x180018531  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x180018535  mov     [rsp+640h+var_5D0], rax
0x18001853a  call    cs:__imp_EnterCriticalSection
0x180018540  mov     rcx, [rbp+540h+hKey]; hKey
0x180018544  test    rcx, rcx
0x180018547  jz      short loc_18001855A
0x180018549  call    cs:__imp_RegCloseKey
0x18001854f  mov     rcx, [rbp+540h+var_520]
0x180018553  mov     [rbp+540h+hKey], rsi
0x180018557  mov     [rcx], si
0x18001855a  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18001855e  call    cs:__imp_LeaveCriticalSection
0x180018564  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x180018568  call    cs:__imp_DeleteCriticalSection
0x18001856e  cmp     [rbp+540h+var_518], ebx
0x180018571  jle     short loc_18001857D
0x180018573  mov     rcx, [rbp+540h+var_520]; hMem
0x180018577  call    cs:__imp_GlobalFree
0x18001857d  mov     al, bl
0x18001857f  jmp     loc_180018683
0x180018584  mov     edi, ebx
0x180018586  mov     r10d, [rsp+640h+cbData]
0x18001858b  mov     r8d, esi
0x18001858e  shr     r10d, 1
0x180018591  lea     r9d, [r10-1]
0x180018595  test    r9d, r9d
0x180018598  js      short loc_1800185B0
0x18001859a  mov     rax, [rbp+540h+var_590]
0x18001859e  cmp     [rax+r9*2], si
0x1800185a3  jnz     short loc_1800185B0
0x1800185a5  add     r8d, ebx
0x1800185a8  sub     r9d, ebx
0x1800185ab  cmp     r8d, edi
0x1800185ae  jb      short loc_180018595
0x1800185b0  cmp     edi, r8d
0x1800185b3  ja      loc_180018C27
0x1800185b9  mov     [rsp+640h+var_5F8], edx
0x1800185bd  test    r14d, r14d
0x1800185c0  jz      loc_180018B1E
0x1800185c6  cmp     [rbp+540h+var_588], 21h ; '!'
0x1800185ca  jg      loc_18001890C
0x1800185d0  lea     rax, [rbp+540h+Data]
0x1800185d4  mov     [rbp+540h+var_588], 21h ; '!'
0x1800185db  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x1800185df  mov     [rbp+540h+var_590], rax
0x1800185e3  call    cs:__imp_EnterCriticalSection
0x1800185e9  mov     rcx, [rsp+640h+var_5E0]; hKey
0x1800185ee  xor     edi, edi
0x1800185f0  test    rcx, rcx
0x1800185f3  jz      short loc_180018608
0x1800185f5  call    cs:__imp_RegCloseKey
0x1800185fb  mov     rax, [rsp+640h+var_5D0]
0x180018600  mov     [rsp+640h+var_5E0], rdi
0x180018605  mov     [rax], di
0x180018608  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x18001860c  call    cs:__imp_LeaveCriticalSection
0x180018612  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x180018616  call    cs:__imp_DeleteCriticalSection
0x18001861c  cmp     [rsp+640h+var_5C8], ebx
0x180018620  jle     short loc_18001862D
0x180018622  mov     rcx, [rsp+640h+var_5D0]; hMem
0x180018627  call    cs:__imp_GlobalFree
0x18001862d  lea     rax, [rbp+540h+var_5C0]
0x180018631  mov     [rsp+640h+var_5C8], ebx
0x180018635  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x180018639  mov     [rsp+640h+var_5D0], rax
0x18001863e  call    cs:__imp_EnterCriticalSection
0x180018644  mov     rcx, [rbp+540h+hKey]; hKey
0x180018648  test    rcx, rcx
0x18001864b  jz      short loc_18001865E
0x18001864d  call    cs:__imp_RegCloseKey
0x180018653  mov     rax, [rbp+540h+var_520]
0x180018657  mov     [rbp+540h+hKey], rdi
0x18001865b  mov     [rax], di
0x18001865e  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x180018662  call    cs:__imp_LeaveCriticalSection
0x180018668  lea     rcx, [rbp+540h+CriticalSection]; lpCriticalSection
0x18001866c  call    cs:__imp_DeleteCriticalSection
0x180018672  cmp     [rbp+540h+var_518], ebx
0x180018675  jle     short loc_180018681
0x180018677  mov     rcx, [rbp+540h+var_520]; hMem
0x18001867b  call    cs:__imp_GlobalFree
0x180018681  xor     al, al
0x180018683  mov     rcx, [rbp+540h+var_40]
0x18001868a  xor     rcx, rsp; StackCookie
0x18001868d  call    __security_check_cookie
0x180018692  mov     rbx, [rsp+640h+arg_18]
0x18001869a  add     rsp, 610h
0x1800186a1  pop     r15
0x1800186a3  pop     r14
0x1800186a5  pop     r13
0x1800186a7  pop     r12
0x1800186a9  pop     rdi
0x1800186aa  pop     rsi
0x1800186ab  pop     rbp
0x1800186ac  retn
0x1800186ad  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x1800186b1  call    cs:__imp_EnterCriticalSection
0x1800186b7  mov     rcx, [rsp+640h+var_5E0]; hKey
0x1800186bc  test    rcx, rcx
0x1800186bf  jz      short loc_1800186D4
0x1800186c1  call    cs:__imp_RegCloseKey
0x1800186c7  mov     rax, [rsp+640h+var_5D0]
0x1800186cc  mov     [rsp+640h+var_5E0], rsi
0x1800186d1  mov     [rax], si
0x1800186d4  lea     rcx, [rbp+540h+var_5B8]; lpCriticalSection
0x1800186d8  call    cs:__imp_LeaveCriticalSection
0x1800186de  cmp     cs:?g_fWoW@@3_NA, sil; bool g_fWoW
0x1800186e5  mov     r9d, cs:?g_samRead@@3KA; ulong g_samRead
0x1800186ec  jz      loc_180018BB7
0x1800186f2  mov     rcx, [rbp+540h+hKey]
0x1800186f6  lea     rax, [rsp+640h+var_5E0]
0x1800186fb  mov     [rsp+640h+lpData], rax
0x180018700  lea     rdx, ValueName; "Patches"
0x180018707  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18001870e  xor     r8d, r8d
0x180018711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018716  test    eax, eax
0x180018718  jnz     loc_1800182FE
0x18001871e  mov     eax, [rbp+540h+var_588]
0x180018721  lea     r9, [rsp+640h+Type]; lpType
  ... truncated ...
```
