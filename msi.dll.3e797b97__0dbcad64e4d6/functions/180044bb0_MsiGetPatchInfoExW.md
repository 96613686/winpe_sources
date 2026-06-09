# MsiGetPatchInfoExW

- ea: `0x180044bb0`
- end: `0x1800459b8`
- name: `MsiGetPatchInfoExW`
- size: `3592`
- prototype: `UINT __stdcall(LPCWSTR szPatchCode, LPCWSTR szProductCode, LPCWSTR szUserSid, MSIINSTALLCONTEXT dwContext, LPCWSTR szProperty, LPWSTR lpValue, LPDWORD pcchValue)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180049cf0`
- `0x1800f3a78`
- `0x1801717f0`
- `0x180190f90`

## callees

- `0x18000c4bc`
- `0x180010b58`
- `0x180014e38`
- `0x18003e40c`
- `0x18003e4c0`
- `0x180044bb0`
- `0x1800459c0`
- `0x180045ba4`
- `0x180056370`
- `0x18005e764`
- `0x18015cbac`
- `0x180265240`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180044f9f`
- `ADVAPI32!SetThreadToken` at `0x180045577`
- `ADVAPI32!SetThreadToken` at `0x18004567b`
- `ADVAPI32!SetThreadToken` at `0x180045717`
- `ADVAPI32!SetThreadToken` at `0x1800457f8`
- `ADVAPI32!SetThreadToken` at `0x18004581a`
- `ADVAPI32!SetThreadToken` at `0x1800458ed`
- `ADVAPI32!SetThreadToken` at `0x180045951`
- `ADVAPI32!SetThreadToken` at `0x180044f9f`
- `ADVAPI32!SetThreadToken` at `0x180045577`
- `ADVAPI32!SetThreadToken` at `0x18004567b`
- `ADVAPI32!SetThreadToken` at `0x180045717`
- `ADVAPI32!SetThreadToken` at `0x1800457f8`
- `ADVAPI32!SetThreadToken` at `0x18004581a`
- `ADVAPI32!SetThreadToken` at `0x1800458ed`
- `ADVAPI32!SetThreadToken` at `0x180045951`
- `ADVAPI32!OpenThreadToken` at `0x180044e82`
- `ADVAPI32!OpenThreadToken` at `0x180044f2f`
- `ADVAPI32!OpenThreadToken` at `0x1800450bc`
- `ADVAPI32!OpenThreadToken` at `0x18004516c`
- `ADVAPI32!OpenThreadToken` at `0x18004549e`
- `ADVAPI32!OpenThreadToken` at `0x180044e82`
- `ADVAPI32!OpenThreadToken` at `0x180044f2f`
- `ADVAPI32!OpenThreadToken` at `0x1800450bc`
- `ADVAPI32!OpenThreadToken` at `0x18004516c`
- `ADVAPI32!OpenThreadToken` at `0x18004549e`
- `ADVAPI32!OpenProcessToken` at `0x180044ebd`
- `ADVAPI32!OpenProcessToken` at `0x180044f6e`
- `ADVAPI32!OpenProcessToken` at `0x1800450fb`
- `ADVAPI32!OpenProcessToken` at `0x1800451ab`
- `ADVAPI32!OpenProcessToken` at `0x1800454dd`
- `ADVAPI32!OpenProcessToken` at `0x180044ebd`
- `ADVAPI32!OpenProcessToken` at `0x180044f6e`
- `ADVAPI32!OpenProcessToken` at `0x1800450fb`
- `ADVAPI32!OpenProcessToken` at `0x1800451ab`
- `ADVAPI32!OpenProcessToken` at `0x1800454dd`
- `KERNEL32!CloseHandle` at `0x180044fb9`
- `KERNEL32!CloseHandle` at `0x18004555e`
- `KERNEL32!CloseHandle` at `0x180045591`
- `KERNEL32!CloseHandle` at `0x1800455d0`
- `KERNEL32!CloseHandle` at `0x1800455f9`
- `KERNEL32!CloseHandle` at `0x180045695`
- `KERNEL32!CloseHandle` at `0x1800456b8`
- `KERNEL32!CloseHandle` at `0x180044fb9`
- `KERNEL32!CloseHandle` at `0x18004555e`
- `KERNEL32!CloseHandle` at `0x180045591`
- `KERNEL32!CloseHandle` at `0x1800455d0`
- `KERNEL32!CloseHandle` at `0x1800455f9`
- `KERNEL32!CloseHandle` at `0x180045695`
- `KERNEL32!CloseHandle` at `0x1800456b8`
- `KERNEL32!LeaveCriticalSection` at `0x180044c6c`
- `KERNEL32!LeaveCriticalSection` at `0x180045060`
- `KERNEL32!LeaveCriticalSection` at `0x180045357`
- `KERNEL32!LeaveCriticalSection` at `0x18004553b`
- `KERNEL32!LeaveCriticalSection` at `0x180044c6c`
- `KERNEL32!LeaveCriticalSection` at `0x180045060`
- `KERNEL32!LeaveCriticalSection` at `0x180045357`
- `KERNEL32!LeaveCriticalSection` at `0x18004553b`
- `KERNEL32!GetLastError` at `0x180044c92`
- `KERNEL32!GetLastError` at `0x180044c92`
- `KERNEL32!EnterCriticalSection` at `0x180044c4a`
- `KERNEL32!EnterCriticalSection` at `0x180045047`
- `KERNEL32!EnterCriticalSection` at `0x18004533e`
- `KERNEL32!EnterCriticalSection` at `0x180044c4a`
- `KERNEL32!EnterCriticalSection` at `0x180045047`
- `KERNEL32!EnterCriticalSection` at `0x18004533e`
- `KERNEL32!GetCurrentThread` at `0x180044e63`
- `KERNEL32!GetCurrentThread` at `0x180044f10`
- `KERNEL32!GetCurrentThread` at `0x18004509d`
- `KERNEL32!GetCurrentThread` at `0x18004514d`
- `KERNEL32!GetCurrentThread` at `0x18004547f`
- `KERNEL32!GetCurrentThread` at `0x180044e63`
- `KERNEL32!GetCurrentThread` at `0x180044f10`
- `KERNEL32!GetCurrentThread` at `0x18004509d`
- `KERNEL32!GetCurrentThread` at `0x18004514d`
- `KERNEL32!GetCurrentThread` at `0x18004547f`
- `KERNEL32!GetCurrentProcess` at `0x180044ea4`
- `KERNEL32!GetCurrentProcess` at `0x180044f55`
- `KERNEL32!GetCurrentProcess` at `0x1800450e2`
- `KERNEL32!GetCurrentProcess` at `0x180045192`
- `KERNEL32!GetCurrentProcess` at `0x1800454c4`
- `KERNEL32!GetCurrentProcess` at `0x180044ea4`
- `KERNEL32!GetCurrentProcess` at `0x180044f55`
- `KERNEL32!GetCurrentProcess` at `0x1800450e2`
- `KERNEL32!GetCurrentProcess` at `0x180045192`
- `KERNEL32!GetCurrentProcess` at `0x1800454c4`
- `KERNEL32!lstrlenW` at `0x180044dea`
- `KERNEL32!lstrlenW` at `0x180044fe1`
- `KERNEL32!lstrlenW` at `0x180044dea`
- `KERNEL32!lstrlenW` at `0x180044fe1`
- `KERNEL32!GlobalFree` at `0x1800452ff`
- `KERNEL32!GlobalFree` at `0x1800452ff`
- `KERNEL32!lstrcmpiW` at `0x180045857`
- `KERNEL32!lstrcmpiW` at `0x18004587a`
- `KERNEL32!lstrcmpiW` at `0x180045857`
- `KERNEL32!lstrcmpiW` at `0x18004587a`
- `KERNEL32!TlsSetValue` at `0x180044cab`
- `KERNEL32!TlsSetValue` at `0x180045083`
- `KERNEL32!TlsSetValue` at `0x180045372`
- `KERNEL32!TlsSetValue` at `0x180044cab`
- `KERNEL32!TlsSetValue` at `0x180045083`
- `KERNEL32!TlsSetValue` at `0x180045372`
- `KERNEL32!TlsGetValue` at `0x180044c7a`
- `KERNEL32!TlsGetValue` at `0x180044c7a`
- `KERNEL32!TlsAlloc` at `0x180045517`
- `KERNEL32!TlsAlloc` at `0x180045517`
- `USER32!CharUpperW` at `0x180044d3f`
- `USER32!CharUpperW` at `0x180044da2`
- `USER32!CharUpperW` at `0x180044d3f`
- `USER32!CharUpperW` at `0x180044da2`

## string_xrefs

- `0x1800456d8`: `MsiGetPatchInfoExW is returning: %d`
- `0x180045790`: `Entering MsiGetPatchInfoExW. szPatchCode: %s, szProductCode: %s, szUserSid: %s, dwContext: %d, szProperty: %s`

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
  v11 = dword_180310D00;
  v12 = (const unsigned __int16 *)(int)dwContext;
  lpString1 = szUserSid;
  v76 = szProperty;
  Value = 0;
  v75 = 0;
  if ( dword_180310D00 == -1 )
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
      dword_180310D00 = v58;
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
    v11 = dword_180310D00;
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
      v27 = dword_180310D00;
      if ( dword_180310D00 != -1 )
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
      dword_180310D00 = v63;
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
    v27 = dword_180310D00;
    if ( dword_180310D00 != -1 )
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
    v27 = dword_180310D00;
    if ( dword_180310D00 != -1 )
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
      dword_180310D00 = v60;
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
      v27 = dword_180310D00;
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
      CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall((CForbidTokenChangesDuringCall *)&Value);
      return 5;
    }
    v38 = v68;
  }
  v39 = v76;
  if ( !v76 || !*v76 || !v72 && v73 )
  {
LABEL_42:
    CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall((CForbidTokenChangesDuringCall *)&Value);
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
  v46 = qword_1802796B8;
  v47 = 0;
  v48 = qword_1802796B8;
  v49 = &v81;
  while ( v48 < &qword_1802796D8 )
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
  while ( v46 < &qword_1802796D8 )
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
  v44 = dword_180310D00;
  if ( dword_180310D00 == -1 )
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
      dword_180310D00 = v61;
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
    v44 = dword_180310D00;
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
0x180044bb0  push    rbp
0x180044bb2  push    rbx
0x180044bb3  push    rsi
0x180044bb4  push    rdi
0x180044bb5  push    r12
0x180044bb7  push    r13
0x180044bb9  push    r14
0x180044bbb  push    r15
0x180044bbd  lea     rbp, [rsp-118h]
0x180044bc5  sub     rsp, 218h
0x180044bcc  mov     rax, cs:__security_cookie
0x180044bd3  xor     rax, rsp
0x180044bd6  mov     [rbp+150h+var_50], rax
0x180044bdd  mov     rax, [rbp+150h+lpValue]
0x180044be4  lea     rbx, aNull; "(NULL)"
0x180044beb  mov     r14, [rbp+150h+szProperty]
0x180044bf2  xor     r12d, r12d
0x180044bf5  mov     [rbp+150h+var_1D0], rax
0x180044bf9  xor     r13b, r13b
0x180044bfc  mov     rax, [rbp+150h+pcchValue]
0x180044c03  mov     rdi, rdx
0x180044c06  mov     [rsp+250h+var_1D8], rax
0x180044c0b  mov     rsi, rcx
0x180044c0e  mov     eax, cs:dword_180310D00
0x180044c14  movsxd  r15, r9d
0x180044c17  mov     [rsp+250h+lpString1], r8
0x180044c1c  mov     [rbp+150h+var_1B8], r14
0x180044c20  mov     [rbp+150h+var_1C8], r12
0x180044c24  mov     [rbp+150h+var_1C0], r13b
0x180044c28  cmp     eax, 0FFFFFFFFh
0x180044c2b  jz      loc_180044E5A
0x180044c31  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180044c38  jz      loc_180044CBE
0x180044c3e  cmp     eax, 1
0x180044c41  jnz     short loc_180044CBE
0x180044c43  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044c4a  call    cs:__imp_EnterCriticalSection
0x180044c51  nop     dword ptr [rax+rax+00h]
0x180044c56  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x180044c5c  cmp     ebx, 0FFFFFFFFh
0x180044c5f  jz      loc_180045517
0x180044c65  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044c6c  call    cs:__imp_LeaveCriticalSection
0x180044c73  nop     dword ptr [rax+rax+00h]
0x180044c78  mov     ecx, ebx; dwTlsIndex
0x180044c7a  call    cs:__imp_TlsGetValue
0x180044c81  nop     dword ptr [rax+rax+00h]
0x180044c86  mov     [rbp+150h+var_1C8], rax
0x180044c8a  mov     r12, rax
0x180044c8d  test    rax, rax
0x180044c90  jnz     short loc_180044CA2
0x180044c92  call    cs:__imp_GetLastError
0x180044c99  nop     dword ptr [rax+rax+00h]
0x180044c9e  test    eax, eax
0x180044ca0  jnz     short loc_180044CBE
0x180044ca2  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x180044ca9  mov     ecx, ebx; dwTlsIndex
0x180044cab  call    cs:__imp_TlsSetValue
0x180044cb2  nop     dword ptr [rax+rax+00h]
0x180044cb7  mov     r13b, 1
0x180044cba  mov     [rbp+150h+var_1C0], r13b
0x180044cbe  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180044cc5  jnz     loc_180045777
0x180044ccb  lea     eax, [r15-1]
0x180044ccf  test    eax, 0FFFFFFFCh
0x180044cd4  jnz     loc_180044E28
0x180044cda  cmp     r15d, 3
0x180044cde  jz      loc_180044E28
0x180044ce4  mov     ebx, 7FFFFFFEh
0x180044ce9  mov     r14d, 27h ; '''
0x180044cef  test    rdi, rdi
0x180044cf2  jz      short loc_180044D4F
0x180044cf4  mov     ecx, ebx
0x180044cf6  lea     r8, [rbp+150h+sz]
0x180044cfa  mov     edx, r14d
0x180044cfd  nop     dword ptr [rax]
0x180044d00  test    rcx, rcx
0x180044d03  jz      short loc_180044D22
0x180044d05  movzx   eax, word ptr [rdi]
0x180044d08  test    ax, ax
0x180044d0b  jz      short loc_180044D22
0x180044d0d  mov     [r8], ax
0x180044d11  add     rdi, 2
0x180044d15  add     r8, 2
0x180044d19  dec     rcx
0x180044d1c  sub     rdx, 1
0x180044d20  jnz     short loc_180044D00
0x180044d22  test    rdx, rdx
0x180044d25  lea     rcx, [r8-2]
0x180044d29  cmovnz  rcx, r8
0x180044d2d  xor     eax, eax
0x180044d2f  mov     [rcx], ax
0x180044d32  test    rdx, rdx
0x180044d35  jz      loc_180044EF8
0x180044d3b  lea     rcx, [rbp+150h+sz]; lpsz
0x180044d3f  call    cs:__imp_CharUpperW
0x180044d46  nop     dword ptr [rax+rax+00h]
0x180044d4b  lea     rdi, [rbp+150h+sz]
0x180044d4f  test    rsi, rsi
0x180044d52  jz      short loc_180044DB5
0x180044d54  mov     rdx, r14
0x180044d57  lea     r8, [rbp+150h+var_A0]
0x180044d5e  xchg    ax, ax
0x180044d60  test    rbx, rbx
0x180044d63  jz      short loc_180044D82
0x180044d65  movzx   eax, word ptr [rsi]
0x180044d68  test    ax, ax
0x180044d6b  jz      short loc_180044D82
0x180044d6d  mov     [r8], ax
0x180044d71  add     rsi, 2
0x180044d75  add     r8, 2
0x180044d79  dec     rbx
0x180044d7c  sub     rdx, 1
0x180044d80  jnz     short loc_180044D60
0x180044d82  test    rdx, rdx
0x180044d85  lea     rcx, [r8-2]
0x180044d89  cmovnz  rcx, r8
0x180044d8d  xor     eax, eax
0x180044d8f  mov     [rcx], ax
0x180044d92  test    rdx, rdx
0x180044d95  jz      loc_180045135
0x180044d9b  lea     rcx, [rbp+150h+var_A0]; lpsz
0x180044da2  call    cs:__imp_CharUpperW
0x180044da9  nop     dword ptr [rax+rax+00h]
0x180044dae  lea     rsi, [rbp+150h+var_A0]
0x180044db5  test    rdi, rdi
0x180044db8  jz      short loc_180044E28
0x180044dba  mov     rcx, r14
0x180044dbd  mov     rax, rdi
0x180044dc0  cmp     word ptr [rax], 0
0x180044dc4  jz      short loc_180044DD0
0x180044dc6  add     rax, 2
0x180044dca  sub     rcx, 1
0x180044dce  jnz     short loc_180044DC0
0x180044dd0  xor     eax, eax
0x180044dd2  mov     rdx, r14
0x180044dd5  sub     rdx, rcx
0x180044dd8  test    rcx, rcx
0x180044ddb  cmovz   rdx, rax
0x180044ddf  jz      short loc_180044E28
0x180044de1  cmp     rdx, 26h ; '&'
0x180044de5  jnz     short loc_180044E28
0x180044de7  mov     rcx, rdi; lpString
0x180044dea  call    cs:__imp_lstrlenW
0x180044df1  nop     dword ptr [rax+rax+00h]
0x180044df6  cmp     eax, 26h ; '&'
0x180044df9  jnz     short loc_180044E28
0x180044dfb  cmp     word ptr [rdi], 7Bh ; '{'
0x180044dff  jnz     short loc_180044E28
0x180044e01  cmp     word ptr [rdi+12h], 2Dh ; '-'
0x180044e06  jnz     short loc_180044E28
0x180044e08  cmp     word ptr [rdi+1Ch], 2Dh ; '-'
0x180044e0d  jnz     short loc_180044E28
0x180044e0f  cmp     word ptr [rdi+26h], 2Dh ; '-'
0x180044e14  jnz     short loc_180044E28
0x180044e16  cmp     word ptr [rdi+30h], 2Dh ; '-'
0x180044e1b  jnz     short loc_180044E28
0x180044e1d  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x180044e22  jz      loc_180045214
0x180044e28  lea     rcx, [rbp+150h+var_1C8]; this
0x180044e2c  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x180044e31  mov     eax, 57h ; 'W'
0x180044e36  mov     rcx, [rbp+150h+var_50]
0x180044e3d  xor     rcx, rsp; StackCookie
0x180044e40  call    __security_check_cookie
0x180044e45  add     rsp, 218h
0x180044e4c  pop     r15
0x180044e4e  pop     r14
0x180044e50  pop     r13
0x180044e52  pop     r12
0x180044e54  pop     rdi
0x180044e55  pop     rsi
0x180044e56  pop     rbx
0x180044e57  pop     rbp
0x180044e58  retn
0x180044e5a  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044e63  call    cs:__imp_GetCurrentThread
0x180044e6a  nop     dword ptr [rax+rax+00h]
0x180044e6f  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x180044e74  mov     edx, 4; DesiredAccess
0x180044e79  mov     rcx, rax; ThreadHandle
0x180044e7c  mov     r8d, 1; OpenAsSelf
0x180044e82  call    cs:__imp_OpenThreadToken
0x180044e89  nop     dword ptr [rax+rax+00h]
0x180044e8e  test    eax, eax
0x180044e90  jnz     loc_180045713
0x180044e96  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044e9f  mov     [rsp+250h+hObject], r12
0x180044ea4  call    cs:__imp_GetCurrentProcess
0x180044eab  nop     dword ptr [rax+rax+00h]
0x180044eb0  lea     r8, [rsp+250h+hObject]; TokenHandle
0x180044eb5  mov     edx, 8; DesiredAccess
0x180044eba  mov     rcx, rax; ProcessHandle
0x180044ebd  call    cs:__imp_OpenProcessToken
0x180044ec4  nop     dword ptr [rax+rax+00h]
0x180044ec9  test    eax, eax
0x180044ecb  jnz     loc_18004554C
0x180044ed1  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180044ed8  jnz     loc_180045735
0x180044ede  mov     rdx, [rsp+250h+TokenHandle]; Token
0x180044ee3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180044ee7  jnz     loc_180045575
0x180044eed  mov     eax, cs:dword_180310D00
0x180044ef3  jmp     loc_180044C31
0x180044ef8  mov     eax, cs:dword_180310D00
0x180044efe  cmp     eax, 0FFFFFFFFh
0x180044f01  jnz     loc_18004502A
0x180044f07  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044f10  call    cs:__imp_GetCurrentThread
0x180044f17  nop     dword ptr [rax+rax+00h]
0x180044f1c  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x180044f21  mov     edx, 4; DesiredAccess
0x180044f26  mov     rcx, rax; ThreadHandle
0x180044f29  mov     r8d, 1; OpenAsSelf
0x180044f2f  call    cs:__imp_OpenThreadToken
0x180044f36  nop     dword ptr [rax+rax+00h]
0x180044f3b  test    eax, eax
0x180044f3d  jnz     loc_1800457F4
0x180044f43  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044f4c  mov     [rsp+250h+hObject], 0
0x180044f55  call    cs:__imp_GetCurrentProcess
0x180044f5c  nop     dword ptr [rax+rax+00h]
0x180044f61  lea     r8, [rsp+250h+hObject]; TokenHandle
0x180044f66  mov     edx, 8; DesiredAccess
0x180044f6b  mov     rcx, rax; ProcessHandle
0x180044f6e  call    cs:__imp_OpenProcessToken
0x180044f75  nop     dword ptr [rax+rax+00h]
0x180044f7a  test    eax, eax
0x180044f7c  jnz     loc_1800456A6
0x180044f82  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180044f88  jnz     loc_1800451CB
0x180044f8e  mov     rdx, [rsp+250h+TokenHandle]; Token
0x180044f93  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180044f97  jz      loc_18004512A
0x180044f9d  xor     ecx, ecx; Thread
0x180044f9f  call    cs:__imp_SetThreadToken
0x180044fa6  nop     dword ptr [rax+rax+00h]
0x180044fab  test    eax, eax
0x180044fad  jnz     short loc_180044FB4
0x180044faf  call    ExitProcessIfNotClient
0x180044fb4  mov     rcx, [rsp+250h+TokenHandle]; hObject
0x180044fb9  call    cs:__imp_CloseHandle
0x180044fc0  nop     dword ptr [rax+rax+00h]
0x180044fc5  jmp     loc_18004512A
0x180044fca  sub     r14, rcx
0x180044fcd  xor     eax, eax
0x180044fcf  test    rcx, rcx
0x180044fd2  cmovz   r14, rax
0x180044fd6  jz      short loc_18004501F
0x180044fd8  cmp     r14, 26h ; '&'
0x180044fdc  jnz     short loc_18004501F
0x180044fde  mov     rcx, rsi; lpString
0x180044fe1  call    cs:__imp_lstrlenW
0x180044fe8  nop     dword ptr [rax+rax+00h]
0x180044fed  cmp     eax, r14d
0x180044ff0  jnz     short loc_18004501F
0x180044ff2  cmp     word ptr [rsi], 7Bh ; '{'
0x180044ff6  jnz     short loc_18004501F
0x180044ff8  cmp     word ptr [rsi+12h], 2Dh ; '-'
0x180044ffd  jnz     short loc_18004501F
0x180044fff  cmp     word ptr [rsi+1Ch], 2Dh ; '-'
0x180045004  jnz     short loc_18004501F
0x180045006  cmp     word ptr [rsi+26h], 2Dh ; '-'
0x18004500b  jnz     short loc_18004501F
0x18004500d  cmp     word ptr [rsi+30h], 2Dh ; '-'
0x180045012  jnz     short loc_18004501F
0x180045014  cmp     word ptr [rsi+4Ah], 7Dh ; '}'
0x180045019  jz      loc_18004523C
0x18004501f  mov     eax, cs:dword_180310D00
0x180045025  cmp     eax, 0FFFFFFFFh
0x180045028  jz      short loc_180045094
0x18004502a  cmp     eax, 1
0x18004502d  jnz     loc_180044E31
0x180045033  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004503a  jz      loc_180044E31
0x180045040  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045047  call    cs:__imp_EnterCriticalSection
0x18004504e  nop     dword ptr [rax+rax+00h]
0x180045053  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x180045059  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045060  call    cs:__imp_LeaveCriticalSection
0x180045067  nop     dword ptr [rax+rax+00h]
0x18004506c  cmp     ebx, 0FFFFFFFFh
0x18004506f  jz      loc_180044E31
0x180045075  test    r13b, r13b
0x180045078  jz      loc_180044E31
0x18004507e  mov     rdx, r12; lpTlsValue
0x180045081  mov     ecx, ebx; dwTlsIndex
0x180045083  call    cs:__imp_TlsSetValue
0x18004508a  nop     dword ptr [rax+rax+00h]
0x18004508f  jmp     loc_180044E31
0x180045094  mov     [rsp+250h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004509d  call    cs:__imp_GetCurrentThread
0x1800450a4  nop     dword ptr [rax+rax+00h]
0x1800450a9  lea     r9, [rsp+250h+TokenHandle]; TokenHandle
0x1800450ae  mov     edx, 4; DesiredAccess
0x1800450b3  mov     rcx, rax; ThreadHandle
0x1800450b6  mov     r8d, 1; OpenAsSelf
0x1800450bc  call    cs:__imp_OpenThreadToken
0x1800450c3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
