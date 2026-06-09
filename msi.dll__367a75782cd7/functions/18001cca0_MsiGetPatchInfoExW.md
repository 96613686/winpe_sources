# MsiGetPatchInfoExW

- ea: `0x18001cca0`
- end: `0x18001d95a`
- name: `MsiGetPatchInfoExW`
- size: `3258`
- prototype: `UINT __stdcall(LPCWSTR szPatchCode, LPCWSTR szProductCode, LPCWSTR szUserSid, MSIINSTALLCONTEXT dwContext, LPCWSTR szProperty, LPWSTR lpValue, LPDWORD pcchValue)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004cb90`
- `0x1800eb9f0`
- `0x18016b780`
- `0x18018a850`

## callees

- `0x180017a84`
- `0x180017b28`
- `0x18001cca0`
- `0x18001d960`
- `0x1800221b0`
- `0x180025a18`
- `0x1800321f8`
- `0x18005de7c`
- `0x180064a78`
- `0x1800a9d48`
- `0x180157094`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18001d02a`
- `ADVAPI32!SetThreadToken` at `0x18001d56d`
- `ADVAPI32!SetThreadToken` at `0x18001d659`
- `ADVAPI32!SetThreadToken` at `0x18001d6e3`
- `ADVAPI32!SetThreadToken` at `0x18001d7be`
- `ADVAPI32!SetThreadToken` at `0x18001d7da`
- `ADVAPI32!SetThreadToken` at `0x18001d89b`
- `ADVAPI32!SetThreadToken` at `0x18001d8f9`
- `ADVAPI32!SetThreadToken` at `0x18001d02a`
- `ADVAPI32!SetThreadToken` at `0x18001d56d`
- `ADVAPI32!SetThreadToken` at `0x18001d659`
- `ADVAPI32!SetThreadToken` at `0x18001d6e3`
- `ADVAPI32!SetThreadToken` at `0x18001d7be`
- `ADVAPI32!SetThreadToken` at `0x18001d7da`
- `ADVAPI32!SetThreadToken` at `0x18001d89b`
- `ADVAPI32!SetThreadToken` at `0x18001d8f9`
- `ADVAPI32!OpenThreadToken` at `0x18001cf37`
- `ADVAPI32!OpenThreadToken` at `0x18001cfcc`
- `ADVAPI32!OpenThreadToken` at `0x18001d11d`
- `ADVAPI32!OpenThreadToken` at `0x18001d1b5`
- `ADVAPI32!OpenThreadToken` at `0x18001d4b8`
- `ADVAPI32!OpenThreadToken` at `0x18001cf37`
- `ADVAPI32!OpenThreadToken` at `0x18001cfcc`
- `ADVAPI32!OpenThreadToken` at `0x18001d11d`
- `ADVAPI32!OpenThreadToken` at `0x18001d1b5`
- `ADVAPI32!OpenThreadToken` at `0x18001d4b8`
- `ADVAPI32!OpenProcessToken` at `0x18001cf66`
- `ADVAPI32!OpenProcessToken` at `0x18001cfff`
- `ADVAPI32!OpenProcessToken` at `0x18001d150`
- `ADVAPI32!OpenProcessToken` at `0x18001d1e8`
- `ADVAPI32!OpenProcessToken` at `0x18001d4eb`
- `ADVAPI32!OpenProcessToken` at `0x18001cf66`
- `ADVAPI32!OpenProcessToken` at `0x18001cfff`
- `ADVAPI32!OpenProcessToken` at `0x18001d150`
- `ADVAPI32!OpenProcessToken` at `0x18001d1e8`
- `ADVAPI32!OpenProcessToken` at `0x18001d4eb`
- `KERNEL32!CloseHandle` at `0x18001d03e`
- `KERNEL32!CloseHandle` at `0x18001d55a`
- `KERNEL32!CloseHandle` at `0x18001d581`
- `KERNEL32!CloseHandle` at `0x18001d5ba`
- `KERNEL32!CloseHandle` at `0x18001d5dd`
- `KERNEL32!CloseHandle` at `0x18001d66d`
- `KERNEL32!CloseHandle` at `0x18001d68a`
- `KERNEL32!CloseHandle` at `0x18001d03e`
- `KERNEL32!CloseHandle` at `0x18001d55a`
- `KERNEL32!CloseHandle` at `0x18001d581`
- `KERNEL32!CloseHandle` at `0x18001d5ba`
- `KERNEL32!CloseHandle` at `0x18001d5dd`
- `KERNEL32!CloseHandle` at `0x18001d66d`
- `KERNEL32!CloseHandle` at `0x18001d68a`
- `KERNEL32!LeaveCriticalSection` at `0x18001cd52`
- `KERNEL32!LeaveCriticalSection` at `0x18001d0d3`
- `KERNEL32!LeaveCriticalSection` at `0x18001d388`
- `KERNEL32!LeaveCriticalSection` at `0x18001d53d`
- `KERNEL32!LeaveCriticalSection` at `0x18001cd52`
- `KERNEL32!LeaveCriticalSection` at `0x18001d0d3`
- `KERNEL32!LeaveCriticalSection` at `0x18001d388`
- `KERNEL32!LeaveCriticalSection` at `0x18001d53d`
- `KERNEL32!GetLastError` at `0x18001cd6c`
- `KERNEL32!GetLastError` at `0x18001cd6c`
- `KERNEL32!EnterCriticalSection` at `0x18001cd36`
- `KERNEL32!EnterCriticalSection` at `0x18001d0c0`
- `KERNEL32!EnterCriticalSection` at `0x18001d375`
- `KERNEL32!EnterCriticalSection` at `0x18001cd36`
- `KERNEL32!EnterCriticalSection` at `0x18001d0c0`
- `KERNEL32!EnterCriticalSection` at `0x18001d375`
- `KERNEL32!GetCurrentThread` at `0x18001cf1e`
- `KERNEL32!GetCurrentThread` at `0x18001cfb3`
- `KERNEL32!GetCurrentThread` at `0x18001d104`
- `KERNEL32!GetCurrentThread` at `0x18001d19c`
- `KERNEL32!GetCurrentThread` at `0x18001d49f`
- `KERNEL32!GetCurrentThread` at `0x18001cf1e`
- `KERNEL32!GetCurrentThread` at `0x18001cfb3`
- `KERNEL32!GetCurrentThread` at `0x18001d104`
- `KERNEL32!GetCurrentThread` at `0x18001d19c`
- `KERNEL32!GetCurrentThread` at `0x18001d49f`
- `KERNEL32!GetCurrentProcess` at `0x18001cf53`
- `KERNEL32!GetCurrentProcess` at `0x18001cfec`
- `KERNEL32!GetCurrentProcess` at `0x18001d13d`
- `KERNEL32!GetCurrentProcess` at `0x18001d1d5`
- `KERNEL32!GetCurrentProcess` at `0x18001d4d8`
- `KERNEL32!GetCurrentProcess` at `0x18001cf53`
- `KERNEL32!GetCurrentProcess` at `0x18001cfec`
- `KERNEL32!GetCurrentProcess` at `0x18001d13d`
- `KERNEL32!GetCurrentProcess` at `0x18001d1d5`
- `KERNEL32!GetCurrentProcess` at `0x18001d4d8`
- `KERNEL32!lstrlenW` at `0x18001ceac`
- `KERNEL32!lstrlenW` at `0x18001d060`
- `KERNEL32!lstrlenW` at `0x18001ceac`
- `KERNEL32!lstrlenW` at `0x18001d060`
- `KERNEL32!GlobalFree` at `0x18001d33c`
- `KERNEL32!GlobalFree` at `0x18001d33c`
- `KERNEL32!lstrcmpiW` at `0x18001d811`
- `KERNEL32!lstrcmpiW` at `0x18001d82e`
- `KERNEL32!lstrcmpiW` at `0x18001d811`
- `KERNEL32!lstrcmpiW` at `0x18001d82e`
- `KERNEL32!TlsSetValue` at `0x18001cd7f`
- `KERNEL32!TlsSetValue` at `0x18001d0f0`
- `KERNEL32!TlsSetValue` at `0x18001d39d`
- `KERNEL32!TlsSetValue` at `0x18001cd7f`
- `KERNEL32!TlsSetValue` at `0x18001d0f0`
- `KERNEL32!TlsSetValue` at `0x18001d39d`
- `KERNEL32!TlsGetValue` at `0x18001cd5a`
- `KERNEL32!TlsGetValue` at `0x18001cd5a`
- `KERNEL32!TlsAlloc` at `0x18001d51f`
- `KERNEL32!TlsAlloc` at `0x18001d51f`
- `USER32!CharUpperW` at `0x18001ce0f`
- `USER32!CharUpperW` at `0x18001ce6a`
- `USER32!CharUpperW` at `0x18001ce0f`
- `USER32!CharUpperW` at `0x18001ce6a`

## string_xrefs

- `0x18001d3d0`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18001d6a4`: `MsiGetPatchInfoExW is returning: %d`
- `0x18001d756`: `Entering MsiGetPatchInfoExW. szPatchCode: %s, szProductCode: %s, szUserSid: %s, dwContext: %d, szProperty: %s`

## pseudocode

```c
UINT __stdcall MsiGetPatchInfoExW(
        LPCWSTR szPatchCode,
        LPCWSTR szProductCode,
        LPCWSTR szUserSid,
        MSIINSTALLCONTEXT dwContext,
        LPCWSTR szProperty,
        LPWSTR lpValue,
        LPDWORD pcchValue)
{
  void *v7; // r12
  char v8; // r13
  int v11; // eax
  const unsigned __int16 *v12; // r15
  DWORD v13; // ebx
  __int64 v14; // rbx
  __int64 v15; // rcx
  WCHAR *v16; // r8
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // r8
  WCHAR *v21; // rcx
  __int64 v22; // rcx
  LPCWSTR v23; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  int v27; // eax
  HANDLE v28; // rax
  HANDLE v29; // rax
  void *v30; // rdx
  DWORD v31; // ebx
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  __int64 v36; // rcx
  LPCWSTR v37; // rax
  LPCWSTR v38; // r11
  LPCWSTR v39; // r14
  unsigned int v40; // ebx
  int v41; // ecx
  __int64 v42; // rax
  UINT AppliedPatchInfoInternal; // edi
  int v44; // eax
  DWORD v45; // ebx
  __int64 *v46; // r8
  unsigned int v47; // r9d
  __int64 *v48; // rdx
  __int16 *v49; // r10
  __int64 v50; // rax
  int v51; // ecx
  __int64 v52; // rax
  __int16 *v53; // r9
  unsigned int v54; // edx
  __int64 v55; // rax
  HANDLE v56; // rax
  HANDLE v57; // rax
  BOOL v58; // ebx
  int v59; // r15d
  BOOL v60; // ebx
  BOOL v61; // ebx
  LPCWSTR v62; // rdi
  BOOL v63; // ebx
  const unsigned __int16 *v64; // r8
  const unsigned __int16 *v65; // r10
  const unsigned __int16 *v66; // rcx
  const unsigned __int16 *v67; // rax
  wchar_t *v68; // rbx
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpString1; // [rsp+70h] [rbp-90h]
  LPDWORD v72; // [rsp+78h] [rbp-88h]
  LPWSTR v73; // [rsp+80h] [rbp-80h]
  LPVOID Value; // [rsp+88h] [rbp-78h] BYREF
  char v75; // [rsp+90h] [rbp-70h]
  LPCWSTR v76; // [rsp+98h] [rbp-68h]
  HGLOBAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  int v78; // [rsp+A8h] [rbp-58h]
  int v79; // [rsp+ACh] [rbp-54h]
  _BYTE v80[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v81; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v82; // [rsp+C2h] [rbp-3Eh]
  __int128 v83; // [rsp+D2h] [rbp-2Eh]
  __int128 v84; // [rsp+E2h] [rbp-1Eh]
  __int128 v85; // [rsp+F2h] [rbp-Eh]
  __int16 v86; // [rsp+110h] [rbp+10h] BYREF
  __int128 v87; // [rsp+112h] [rbp+12h]
  __int128 v88; // [rsp+122h] [rbp+22h]
  __int128 v89; // [rsp+132h] [rbp+32h]
  __int128 v90; // [rsp+142h] [rbp+42h]
  WCHAR sz[40]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v92[40]; // [rsp+1B0h] [rbp+B0h] BYREF

  v7 = 0;
  v73 = lpValue;
  v8 = 0;
  v72 = pcchValue;
  v11 = dword_180306D40;
  v12 = (const unsigned __int16 *)(int)dwContext;
  lpString1 = szUserSid;
  v76 = szProperty;
  Value = 0;
  v75 = 0;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v58 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v58;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v11 = dword_180306D40;
  }
  if ( g_scServerContext != 2 && v11 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v13 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1
      && (g_dwImpersonationSlot = TlsAlloc(), v13 = g_dwImpersonationSlot, g_dwImpersonationSlot == -1) )
    {
      LeaveCriticalSection(&g_csImpersonationLock);
    }
    else
    {
      LeaveCriticalSection(&g_csImpersonationLock);
      Value = TlsGetValue(v13);
      v7 = Value;
      if ( Value || !GetLastError() )
      {
        TlsSetValue(v13, (LPVOID)0xFFFFFFFF80000000LL);
        v8 = 1;
        v75 = 1;
      }
    }
  }
  if ( g_dmDiagnosticMode )
  {
    v64 = lpString1;
    v65 = szProperty;
    v66 = szProductCode;
    if ( !szProperty )
      v65 = L"NULL";
    v67 = szPatchCode;
    if ( !lpString1 )
      v64 = L"NULL";
    if ( !szProductCode )
      v66 = L"NULL";
    if ( !szPatchCode )
      v67 = L"NULL";
    DebugString(
      9,
      0,
      0,
      L"Entering MsiGetPatchInfoExW. szPatchCode: %s, szProductCode: %s, szUserSid: %s, dwContext: %d, szProperty: %s",
      v67,
      v66,
      v64,
      v12,
      v65,
      L"(NULL)",
      0,
      0);
  }
  if ( (((_DWORD)v12 - 1) & 0xFFFFFFFC) != 0 || (_DWORD)v12 == 3 )
    goto LABEL_42;
  v14 = 2147483646;
  if ( szProductCode )
  {
    v15 = 2147483646;
    v16 = sz;
    v17 = 39;
    do
    {
      if ( !v15 )
        break;
      if ( !*szProductCode )
        break;
      *v16++ = *szProductCode++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
    if ( !v17 )
    {
      v27 = dword_180306D40;
      if ( dword_180306D40 != -1 )
      {
LABEL_70:
        if ( v27 == 1 && g_scServerContext != 2 )
        {
          EnterCriticalSection(&g_csImpersonationLock);
          v31 = g_dwImpersonationSlot;
          LeaveCriticalSection(&g_csImpersonationLock);
          if ( v31 != -1 )
          {
            if ( v8 )
              TlsSetValue(v31, v7);
          }
        }
        return 87;
      }
      TokenHandle = (void *)-1LL;
      v28 = GetCurrentThread();
      if ( OpenThreadToken(v28, 4u, 1, &TokenHandle) )
      {
        if ( !SetThreadToken(0, 0) )
          ExitProcessIfNotClient();
      }
      else
      {
        TokenHandle = (void *)-1LL;
      }
      hObject = 0;
      v29 = GetCurrentProcess();
      if ( !OpenProcessToken(v29, 8u, &hObject) )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_56;
LABEL_87:
        DebugString(
          9,
          0,
          0,
          L"Could not determine if the process is running as local system or not.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
        goto LABEL_56;
      }
LABEL_159:
      v63 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v63;
LABEL_56:
      v30 = TokenHandle;
      if ( TokenHandle == (void *)-1LL )
        goto LABEL_81;
      goto LABEL_57;
    }
    CharUpperW(sz);
    szProductCode = sz;
  }
  if ( szPatchCode )
  {
    v19 = 39;
    v20 = v92;
    do
    {
      if ( !v14 )
        break;
      if ( !*szPatchCode )
        break;
      *v20++ = *szPatchCode++;
      --v14;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    if ( v19 )
    {
      CharUpperW(v92);
      szPatchCode = v92;
      goto LABEL_29;
    }
    v27 = dword_180306D40;
    if ( dword_180306D40 != -1 )
      goto LABEL_70;
    TokenHandle = (void *)-1LL;
    v34 = GetCurrentThread();
    if ( OpenThreadToken(v34, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v35 = GetCurrentProcess();
    if ( !OpenProcessToken(v35, 8u, &hObject) )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_56;
      goto LABEL_87;
    }
    goto LABEL_159;
  }
LABEL_29:
  if ( !szProductCode )
    goto LABEL_42;
  v22 = 39;
  v23 = szProductCode;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v22;
  }
  while ( v22 );
  if ( !v22
    || v22 != 1
    || lstrlenW(szProductCode) != 38
    || *szProductCode != 123
    || szProductCode[9] != 45
    || szProductCode[14] != 45
    || szProductCode[19] != 45
    || szProductCode[24] != 45
    || szProductCode[37] != 125 )
  {
    goto LABEL_42;
  }
  if ( !szPatchCode )
    goto LABEL_69;
  v36 = 39;
  v37 = szPatchCode;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  if ( !v36
    || v36 != 1
    || lstrlenW(szPatchCode) != 38
    || *szPatchCode != 123
    || szPatchCode[9] != 45
    || szPatchCode[14] != 45
    || szPatchCode[19] != 45
    || szPatchCode[24] != 45
    || szPatchCode[37] != 125 )
  {
LABEL_69:
    v27 = dword_180306D40;
    if ( dword_180306D40 != -1 )
      goto LABEL_70;
    TokenHandle = (void *)-1LL;
    v32 = GetCurrentThread();
    if ( OpenThreadToken(v32, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v33 = GetCurrentProcess();
    if ( OpenProcessToken(v33, 8u, &hObject) )
    {
      v60 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v60;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v30 = TokenHandle;
    if ( TokenHandle == (void *)-1LL )
    {
LABEL_81:
      v27 = dword_180306D40;
      goto LABEL_70;
    }
LABEL_57:
    if ( !SetThreadToken(0, v30) )
      ExitProcessIfNotClient();
    CloseHandle(TokenHandle);
    goto LABEL_81;
  }
  v38 = lpString1;
  if ( lpString1 )
  {
    if ( (_DWORD)v12 == 4 )
      goto LABEL_42;
    if ( !*lpString1 )
      goto LABEL_42;
    if ( !lstrcmpiW(lpString1, L"S-1-5-18") )
      goto LABEL_42;
    v68 = (wchar_t *)lpString1;
    if ( !lstrcmpiW(lpString1, L"S-1-1-0") )
      goto LABEL_42;
    if ( !IsCurrentUser(v68) && !IsAdmin() )
    {
      CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(&Value);
      return 5;
    }
    v38 = v68;
  }
  v39 = v76;
  if ( !v76 || !*v76 || !v72 && v73 )
  {
LABEL_42:
    CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(&Value);
    return 87;
  }
  v78 = 1;
  hMem = v80;
  v79 = 1;
  if ( (_DWORD)v12 == 4 )
  {
    v40 = 2;
  }
  else
  {
    v59 = (_DWORD)v12 - 1;
    if ( v59 )
    {
      if ( v59 == 1 )
        v40 = 1;
      else
        v40 = 3;
    }
    else
    {
      v40 = 0;
    }
  }
  if ( v40 == 3 )
    goto LABEL_103;
  v81 = 0;
  v41 = 0;
  v82 = 0;
  v86 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  while ( v41 < 38 )
  {
    v42 = v41++;
    if ( !szProductCode[v42] )
      goto LABEL_103;
  }
  if ( *szProductCode != 123 || szProductCode[37] != 125 )
    goto LABEL_103;
  v46 = qword_18026F6C0;
  v47 = 0;
  v48 = qword_18026F6C0;
  v49 = &v81;
  while ( v48 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v47 >= 0x21 )
      goto LABEL_103;
    v50 = *(unsigned __int8 *)v48;
    v48 = (__int64 *)((char *)v48 + 1);
    *v49++ = szProductCode[v50];
    ++v47;
  }
  if ( v47 >= 0x21 )
    goto LABEL_103;
  *v49 = 0;
  v51 = 0;
  while ( v51 < 38 )
  {
    v52 = v51++;
    if ( !szPatchCode[v52] )
      goto LABEL_103;
  }
  if ( *szPatchCode != 123 || szPatchCode[37] != 125 )
    goto LABEL_103;
  v53 = &v86;
  v54 = 0;
  while ( v46 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v54 >= 0x21 )
      goto LABEL_103;
    v55 = *(unsigned __int8 *)v46;
    v46 = (__int64 *)((char *)v46 + 1);
    *v53++ = szPatchCode[v55];
    ++v54;
  }
  if ( v54 < 0x21 )
  {
    *v53 = 0;
    if ( (unsigned __int8)IsProductInstalledOrAdvertised(&v81, v38, v40) )
    {
      v62 = lpString1;
      if ( (unsigned __int8)PatchWasRoamed(v40, &v81, lpString1, &v86) )
      {
        AppliedPatchInfoInternal = 1647;
      }
      else
      {
        AppliedPatchInfoInternal = GetAppliedPatchInfoInternal(v40, &v81, v62, &v86, v39, &hMem);
        if ( !AppliedPatchInfoInternal )
        {
          v79 = 1;
          AppliedPatchInfoInternal = SafeFillOutputBufferW(v73, v72, &hMem);
        }
      }
    }
    else
    {
      AppliedPatchInfoInternal = 1605;
    }
  }
  else
  {
LABEL_103:
    AppliedPatchInfoInternal = 87;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"MsiGetPatchInfoExW is returning: %d",
      (const unsigned __int16 *)AppliedPatchInfoInternal,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( v78 > 1 )
    GlobalFree(hMem);
  v78 = 1;
  hMem = v80;
  v44 = dword_180306D40;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    v56 = GetCurrentThread();
    if ( OpenThreadToken(v56, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v57 = GetCurrentProcess();
    if ( OpenProcessToken(v57, 8u, &hObject) )
    {
      v61 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v61;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v44 = dword_180306D40;
  }
  if ( v44 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v45 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v45 != -1 )
    {
      if ( v8 )
        TlsSetValue(v45, v7);
    }
  }
  return AppliedPatchInfoInternal;
}

```

## disassembly

```asm
0x18001cca0  push    rbp
0x18001cca2  push    rbx
0x18001cca3  push    rsi
0x18001cca4  push    rdi
0x18001cca5  push    r12
0x18001cca7  push    r13
0x18001cca9  push    r14
0x18001ccab  push    r15
0x18001ccad  lea     rbp, [rsp-118h]
0x18001ccb5  sub     rsp, 218h
0x18001ccbc  mov     rax, cs:__security_cookie
0x18001ccc3  xor     rax, rsp
0x18001ccc6  mov     [rbp+150h+var_50], rax
0x18001cccd  mov     rax, [rbp+150h+lpValue]
0x18001ccd4  lea     rbx, aNull; "(NULL)"
0x18001ccdb  mov     r14, [rbp+150h+szProperty]
0x18001cce2  xor     r12d, r12d
0x18001cce5  mov     [rbp+150h+var_1D0], rax
0x18001cce9  xor     r13b, r13b
0x18001ccec  mov     rax, [rbp+150h+pcchValue]
0x18001ccf3  mov     rdi, rdx
0x18001ccf6  mov     [rsp+250h+var_1D8], rax
0x18001ccfb  mov     rsi, rcx
0x18001ccfe  mov     eax, cs:dword_180306D40
0x18001cd04  movsxd  r15, r9d
0x18001cd07  mov     [rsp+250h+lpString1], r8
0x18001cd0c  mov     [rbp+150h+var_1B8], r14
0x18001cd10  mov     [rbp+150h+var_1C8], r12
0x18001cd14  mov     [rbp+150h+var_1C0], r13b
0x18001cd18  cmp     eax, 0FFFFFFFFh
0x18001cd1b  jz      loc_18001CF15
0x18001cd21  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001cd28  jz      short loc_18001CD8C
0x18001cd2a  cmp     eax, 1
0x18001cd2d  jnz     short loc_18001CD8C
0x18001cd2f  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cd36  call    cs:__imp_EnterCriticalSection
0x18001cd3c  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001cd42  cmp     ebx, 0FFFFFFFFh
0x18001cd45  jz      loc_18001D51F
0x18001cd4b  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cd52  call    cs:__imp_LeaveCriticalSection
0x18001cd58  mov     ecx, ebx; dwTlsIndex
0x18001cd5a  call    cs:__imp_TlsGetValue
0x18001cd60  mov     [rbp+150h+var_1C8], rax
0x18001cd64  mov     r12, rax
0x18001cd67  test    rax, rax
0x18001cd6a  jnz     short loc_18001CD76
0x18001cd6c  call    cs:__imp_GetLastError
0x18001cd72  test    eax, eax
0x18001cd74  jnz     short loc_18001CD8C
0x18001cd76  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x18001cd7d  mov     ecx, ebx; dwTlsIndex
0x18001cd7f  call    cs:__imp_TlsSetValue
0x18001cd85  mov     r13b, 1
0x18001cd88  mov     [rbp+150h+var_1C0], r13b
0x18001cd8c  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18001cd93  jnz     loc_18001D73D
0x18001cd99  lea     eax, [r15-1]
0x18001cd9d  test    eax, 0FFFFFFFCh
0x18001cda2  jnz     loc_18001CEE4
0x18001cda8  cmp     r15d, 3
0x18001cdac  jz      loc_18001CEE4
0x18001cdb2  mov     ebx, 7FFFFFFEh
0x18001cdb7  mov     r14d, 27h ; '''
0x18001cdbd  test    rdi, rdi
0x18001cdc0  jz      short loc_18001CE19
0x18001cdc2  mov     ecx, ebx
0x18001cdc4  lea     r8, [rbp+150h+sz]
0x18001cdc8  mov     edx, r14d
0x18001cdcb  nop     dword ptr [rax+rax+00h]
0x18001cdd0  test    rcx, rcx
0x18001cdd3  jz      short loc_18001CDF2
0x18001cdd5  movzx   eax, word ptr [rdi]
0x18001cdd8  test    ax, ax
0x18001cddb  jz      short loc_18001CDF2
0x18001cddd  mov     [r8], ax
0x18001cde1  add     rdi, 2
0x18001cde5  add     r8, 2
0x18001cde9  dec     rcx
0x18001cdec  sub     rdx, 1
0x18001cdf0  jnz     short loc_18001CDD0
0x18001cdf2  test    rdx, rdx
0x18001cdf5  lea     rcx, [r8-2]
0x18001cdf9  cmovnz  rcx, r8
0x18001cdfd  xor     eax, eax
0x18001cdff  mov     [rcx], ax
0x18001ce02  test    rdx, rdx
0x18001ce05  jz      loc_18001CF9B
0x18001ce0b  lea     rcx, [rbp+150h+sz]; lpsz
0x18001ce0f  call    cs:__imp_CharUpperW
0x18001ce15  lea     rdi, [rbp+150h+sz]
0x18001ce19  test    rsi, rsi
0x18001ce1c  jz      short loc_18001CE77
0x18001ce1e  mov     rdx, r14
0x18001ce21  lea     r8, [rbp+150h+var_A0]
0x18001ce28  test    rbx, rbx
0x18001ce2b  jz      short loc_18001CE4A
0x18001ce2d  movzx   eax, word ptr [rsi]
0x18001ce30  test    ax, ax
0x18001ce33  jz      short loc_18001CE4A
0x18001ce35  mov     [r8], ax
0x18001ce39  add     rsi, 2
0x18001ce3d  add     r8, 2
0x18001ce41  dec     rbx
0x18001ce44  sub     rdx, 1
0x18001ce48  jnz     short loc_18001CE28
0x18001ce4a  test    rdx, rdx
0x18001ce4d  lea     rcx, [r8-2]
0x18001ce51  cmovnz  rcx, r8
0x18001ce55  xor     eax, eax
0x18001ce57  mov     [rcx], ax
0x18001ce5a  test    rdx, rdx
0x18001ce5d  jz      loc_18001D184
0x18001ce63  lea     rcx, [rbp+150h+var_A0]; lpsz
0x18001ce6a  call    cs:__imp_CharUpperW
0x18001ce70  lea     rsi, [rbp+150h+var_A0]
0x18001ce77  test    rdi, rdi
0x18001ce7a  jz      short loc_18001CEE4
0x18001ce7c  mov     rcx, r14
0x18001ce7f  mov     rax, rdi
0x18001ce82  cmp     word ptr [rax], 0
0x18001ce86  jz      short loc_18001CE92
0x18001ce88  add     rax, 2
0x18001ce8c  sub     rcx, 1
0x18001ce90  jnz     short loc_18001CE82
0x18001ce92  xor     eax, eax
0x18001ce94  mov     rdx, r14
0x18001ce97  sub     rdx, rcx
0x18001ce9a  test    rcx, rcx
0x18001ce9d  cmovz   rdx, rax
0x18001cea1  jz      short loc_18001CEE4
0x18001cea3  cmp     rdx, 26h ; '&'
0x18001cea7  jnz     short loc_18001CEE4
0x18001cea9  mov     rcx, rdi; lpString
0x18001ceac  call    cs:__imp_lstrlenW
0x18001ceb2  cmp     eax, 26h ; '&'
0x18001ceb5  jnz     short loc_18001CEE4
0x18001ceb7  cmp     word ptr [rdi], 7Bh ; '{'
0x18001cebb  jnz     short loc_18001CEE4
0x18001cebd  cmp     word ptr [rdi+12h], 2Dh ; '-'
0x18001cec2  jnz     short loc_18001CEE4
0x18001cec4  cmp     word ptr [rdi+1Ch], 2Dh ; '-'
0x18001cec9  jnz     short loc_18001CEE4
0x18001cecb  cmp     word ptr [rdi+26h], 2Dh ; '-'
0x18001ced0  jnz     short loc_18001CEE4
0x18001ced2  cmp     word ptr [rdi+30h], 2Dh ; '-'
0x18001ced7  jnz     short loc_18001CEE4
0x18001ced9  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x18001cede  jz      loc_18001D24B
0x18001cee4  lea     rcx, [rbp+150h+var_1C8]; this
0x18001cee8  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x18001ceed  mov     eax, 57h ; 'W'
0x18001cef2  mov     rcx, [rbp+150h+var_50]
0x18001cef9  xor     rcx, rsp; StackCookie
0x18001cefc  call    __security_check_cookie
0x18001cf01  add     rsp, 218h
0x18001cf08  pop     r15
0x18001cf0a  pop     r14
0x18001cf0c  pop     r13
0x18001cf0e  pop     r12
0x18001cf10  pop     rdi
0x18001cf11  pop     rsi
0x18001cf12  pop     rbx
0x18001cf13  pop     rbp
0x18001cf14  retn
0x18001cf15  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cf1e  call    cs:__imp_GetCurrentThread
0x18001cf24  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x18001cf29  mov     edx, 4; DesiredAccess
0x18001cf2e  mov     rcx, rax; ThreadHandle
0x18001cf31  mov     r8d, 1; OpenAsSelf
0x18001cf37  call    cs:__imp_OpenThreadToken
0x18001cf3d  test    eax, eax
0x18001cf3f  jnz     loc_18001D6DF
0x18001cf45  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cf4e  mov     [rsp+250h+hObject], r12
0x18001cf53  call    cs:__imp_GetCurrentProcess
0x18001cf59  lea     r8, [rsp+250h+hObject]; TokenHandle
0x18001cf5e  mov     edx, 8; DesiredAccess
0x18001cf63  mov     rcx, rax; ProcessHandle
0x18001cf66  call    cs:__imp_OpenProcessToken
0x18001cf6c  test    eax, eax
0x18001cf6e  jnz     loc_18001D548
0x18001cf74  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18001cf7b  jnz     loc_18001D6FB
0x18001cf81  mov     rdx, [rsp+250h+TokenHandle]; Token
0x18001cf86  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001cf8a  jnz     loc_18001D56B
0x18001cf90  mov     eax, cs:dword_180306D40
0x18001cf96  jmp     loc_18001CD21
0x18001cf9b  mov     eax, cs:dword_180306D40
0x18001cfa1  cmp     eax, 0FFFFFFFFh
0x18001cfa4  jnz     loc_18001D0A3
0x18001cfaa  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cfb3  call    cs:__imp_GetCurrentThread
0x18001cfb9  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x18001cfbe  mov     edx, 4; DesiredAccess
0x18001cfc3  mov     rcx, rax; ThreadHandle
0x18001cfc6  mov     r8d, 1; OpenAsSelf
0x18001cfcc  call    cs:__imp_OpenThreadToken
0x18001cfd2  test    eax, eax
0x18001cfd4  jnz     loc_18001D7BA
0x18001cfda  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cfe3  mov     [rsp+250h+hObject], 0
0x18001cfec  call    cs:__imp_GetCurrentProcess
0x18001cff2  lea     r8, [rsp+250h+hObject]; TokenHandle
0x18001cff7  mov     edx, 8; DesiredAccess
0x18001cffc  mov     rcx, rax; ProcessHandle
0x18001cfff  call    cs:__imp_OpenProcessToken
0x18001d005  test    eax, eax
0x18001d007  jnz     loc_18001D678
0x18001d00d  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18001d013  jnz     loc_18001D202
0x18001d019  mov     rdx, [rsp+250h+TokenHandle]; Token
0x18001d01e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001d022  jz      loc_18001D179
0x18001d028  xor     ecx, ecx; Thread
0x18001d02a  call    cs:__imp_SetThreadToken
0x18001d030  test    eax, eax
0x18001d032  jnz     short loc_18001D039
0x18001d034  call    ExitProcessIfNotClient
0x18001d039  mov     rcx, [rsp+250h+TokenHandle]; hObject
0x18001d03e  call    cs:__imp_CloseHandle
0x18001d044  jmp     loc_18001D179
0x18001d049  sub     r14, rcx
0x18001d04c  xor     eax, eax
0x18001d04e  test    rcx, rcx
0x18001d051  cmovz   r14, rax
0x18001d055  jz      short loc_18001D098
0x18001d057  cmp     r14, 26h ; '&'
0x18001d05b  jnz     short loc_18001D098
0x18001d05d  mov     rcx, rsi; lpString
0x18001d060  call    cs:__imp_lstrlenW
0x18001d066  cmp     eax, r14d
0x18001d069  jnz     short loc_18001D098
0x18001d06b  cmp     word ptr [rsi], 7Bh ; '{'
0x18001d06f  jnz     short loc_18001D098
0x18001d071  cmp     word ptr [rsi+12h], 2Dh ; '-'
0x18001d076  jnz     short loc_18001D098
0x18001d078  cmp     word ptr [rsi+1Ch], 2Dh ; '-'
0x18001d07d  jnz     short loc_18001D098
0x18001d07f  cmp     word ptr [rsi+26h], 2Dh ; '-'
0x18001d084  jnz     short loc_18001D098
0x18001d086  cmp     word ptr [rsi+30h], 2Dh ; '-'
0x18001d08b  jnz     short loc_18001D098
0x18001d08d  cmp     word ptr [rsi+4Ah], 7Dh ; '}'
0x18001d092  jz      loc_18001D279
0x18001d098  mov     eax, cs:dword_180306D40
0x18001d09e  cmp     eax, 0FFFFFFFFh
0x18001d0a1  jz      short loc_18001D0FB
0x18001d0a3  cmp     eax, 1
0x18001d0a6  jnz     loc_18001CEED
0x18001d0ac  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001d0b3  jz      loc_18001CEED
0x18001d0b9  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d0c0  call    cs:__imp_EnterCriticalSection
0x18001d0c6  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001d0cc  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d0d3  call    cs:__imp_LeaveCriticalSection
0x18001d0d9  cmp     ebx, 0FFFFFFFFh
0x18001d0dc  jz      loc_18001CEED
0x18001d0e2  test    r13b, r13b
0x18001d0e5  jz      loc_18001CEED
0x18001d0eb  mov     rdx, r12; lpTlsValue
0x18001d0ee  mov     ecx, ebx; dwTlsIndex
0x18001d0f0  call    cs:__imp_TlsSetValue
0x18001d0f6  jmp     loc_18001CEED
0x18001d0fb  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001d104  call    cs:__imp_GetCurrentThread
0x18001d10a  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x18001d10f  mov     edx, 4; DesiredAccess
0x18001d114  mov     rcx, rax; ThreadHandle
0x18001d117  mov     r8d, 1; OpenAsSelf
0x18001d11d  call    cs:__imp_OpenThreadToken
0x18001d123  test    eax, eax
0x18001d125  jnz     loc_18001D8F5
0x18001d12b  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001d134  mov     [rsp+250h+hObject], 0
0x18001d13d  call    cs:__imp_GetCurrentProcess
0x18001d143  lea     r8, [rsp+250h+hObject]; TokenHandle
0x18001d148  mov     edx, 8; DesiredAccess
0x18001d14d  mov     rcx, rax; ProcessHandle
0x18001d150  call    cs:__imp_OpenProcessToken
0x18001d156  test    eax, eax
0x18001d158  jnz     loc_18001D5A8
0x18001d15e  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18001d164  jnz     loc_18001D911
0x18001d16a  mov     rdx, [rsp+250h+TokenHandle]
0x18001d16f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001d173  jnz     loc_18001D028
0x18001d179  mov     eax, cs:dword_180306D40
0x18001d17f  jmp     loc_18001D0A3
0x18001d184  mov     eax, cs:dword_180306D40
0x18001d18a  cmp     eax, 0FFFFFFFFh
0x18001d18d  jnz     loc_18001D0A3
0x18001d193  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001d19c  call    cs:__imp_GetCurrentThread
0x18001d1a2  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x18001d1a7  mov     edx, 4; DesiredAccess
  ... truncated ...
```
