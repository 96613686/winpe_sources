# CustomExeThread(CActionThreadData *)

- ea: `0x1801c0f10`
- end: `0x1801c1e3d`
- name: `?CustomExeThread@@YAKPEAVCActionThreadData@@@Z`
- size: `3885`
- prototype: `__int64 __fastcall(struct CActionThreadData *this)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a150`
- `0x18001de18`
- `0x18001e9f8`
- `0x180025560`
- `0x180025904`
- `0x180025a18`
- `0x180035a8c`
- `0x180061334`
- `0x1800620e4`
- `0x1800629b4`
- `0x180066074`
- `0x180068680`
- `0x1800687b8`
- `0x180076e28`
- `0x180079dd0`
- `0x180082fc8`
- `0x180083178`
- `0x1800833ec`
- `0x180085dcc`
- `0x1800b8034`
- `0x1800deab4`
- `0x1800e853c`
- `0x1801561fc`
- `0x180156324`
- `0x1801c0098`
- `0x1801c01a0`
- `0x1801c0f10`
- `0x1801c2bf4`
- `0x1801c36c8`
- `0x1801c42a8`
- `0x1801c42e0`
- `0x1801c65d8`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!wcschr` at `0x1801c12f1`
- `msvcrt!wcschr` at `0x1801c12f1`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c194c`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c1abe`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c1bec`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c194c`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c1abe`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c1bec`
- `ADVAPI32!SetTokenInformation` at `0x1801c18de`
- `ADVAPI32!SetTokenInformation` at `0x1801c18de`
- `ADVAPI32!GetTokenInformation` at `0x1801c18c3`
- `ADVAPI32!GetTokenInformation` at `0x1801c18c3`
- `ADVAPI32!SetThreadToken` at `0x1801c1c46`
- `ADVAPI32!SetThreadToken` at `0x1801c1c46`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c1890`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c19c6`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c1b8e`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c1890`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c19c6`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c1b8e`
- `ADVAPI32!OpenProcessToken` at `0x1801c1863`
- `ADVAPI32!OpenProcessToken` at `0x1801c1863`
- `KERNEL32!CloseHandle` at `0x1801c1968`
- `KERNEL32!CloseHandle` at `0x1801c1a5c`
- `KERNEL32!CloseHandle` at `0x1801c1ad5`
- `KERNEL32!CloseHandle` at `0x1801c1c02`
- `KERNEL32!CloseHandle` at `0x1801c1c0d`
- `KERNEL32!CloseHandle` at `0x1801c1cd5`
- `KERNEL32!CloseHandle` at `0x1801c1d99`
- `KERNEL32!CloseHandle` at `0x1801c1968`
- `KERNEL32!CloseHandle` at `0x1801c1a5c`
- `KERNEL32!CloseHandle` at `0x1801c1ad5`
- `KERNEL32!CloseHandle` at `0x1801c1c02`
- `KERNEL32!CloseHandle` at `0x1801c1c0d`
- `KERNEL32!CloseHandle` at `0x1801c1cd5`
- `KERNEL32!CloseHandle` at `0x1801c1d99`
- `KERNEL32!DebugBreak` at `0x1801c10f8`
- `KERNEL32!DebugBreak` at `0x1801c10f8`
- `KERNEL32!GetLastError` at `0x1801c1a10`
- `KERNEL32!GetLastError` at `0x1801c1b19`
- `KERNEL32!GetLastError` at `0x1801c1a10`
- `KERNEL32!GetLastError` at `0x1801c1b19`
- `KERNEL32!GetCurrentProcess` at `0x1801c1851`
- `KERNEL32!GetCurrentProcess` at `0x1801c1851`
- `KERNEL32!lstrlenW` at `0x1801c12cd`
- `KERNEL32!lstrlenW` at `0x1801c12cd`
- `KERNEL32!SetErrorMode` at `0x1801c18fc`
- `KERNEL32!SetErrorMode` at `0x1801c1958`
- `KERNEL32!SetErrorMode` at `0x1801c1a72`
- `KERNEL32!SetErrorMode` at `0x1801c1aca`
- `KERNEL32!SetErrorMode` at `0x1801c1b9d`
- `KERNEL32!SetErrorMode` at `0x1801c1bf8`
- `KERNEL32!SetErrorMode` at `0x1801c18fc`
- `KERNEL32!SetErrorMode` at `0x1801c1958`
- `KERNEL32!SetErrorMode` at `0x1801c1a72`
- `KERNEL32!SetErrorMode` at `0x1801c1aca`
- `KERNEL32!SetErrorMode` at `0x1801c1b9d`
- `KERNEL32!SetErrorMode` at `0x1801c1bf8`
- `KERNEL32!ResumeThread` at `0x1801c1c95`
- `KERNEL32!ResumeThread` at `0x1801c1c95`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c1784`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c17ab`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c1784`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c17ab`
- `KERNEL32!UpdateProcThreadAttribute` at `0x1801c17e4`
- `KERNEL32!UpdateProcThreadAttribute` at `0x1801c17e4`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x1801c1dce`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x1801c1dce`
- `KERNEL32!TerminateProcess` at `0x1801c1c60`
- `KERNEL32!TerminateProcess` at `0x1801c1c60`
- `KERNEL32!GetExitCodeProcess` at `0x1801c1d78`
- `KERNEL32!GetExitCodeProcess` at `0x1801c1d78`
- `USER32!MsgWaitForMultipleObjects` at `0x1801c1d62`
- `USER32!MsgWaitForMultipleObjects` at `0x1801c1d62`
- `USER32!PeekMessageW` at `0x1801c1d45`
- `USER32!PeekMessageW` at `0x1801c1d45`
- `USER32!TranslateMessage` at `0x1801c1d21`
- `USER32!TranslateMessage` at `0x1801c1d21`
- `USER32!DispatchMessageW` at `0x1801c1d2b`
- `USER32!DispatchMessageW` at `0x1801c1d2b`

## string_xrefs

- `0x1801c148b`: `Failed to Load Services`
- `0x1801c109f`: `ERROR: StringCchCopy failure in CustomExeThread`
- `0x1801c1124`: `ERROR: Failed to initialize impersonate custom action environment block from session environment`
- `0x1801c1146`: `ERROR: Failed to initialize impersonate custom action environment block from process environment`
- `0x1801c13ce`: `ERROR: Failed to apply app compat flags to impersonate environment for custom action %s.`
- `0x1801c136a`: `ERROR: Failed to apply app compat flags to system environment for custom action %s.`
- `0x1801c1a1b`: `SaferComputeTokenFromLevel failed with last error = %d`
- `0x1801c1b24`: `SaferComputeTokenFromLevel failed with last error = %d`

## pseudocode

```c
__int64 __fastcall CustomExeThread(struct CActionThreadData *this)
{
  __int64 *v2; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v3; // r13
  __int64 v4; // rax
  int v5; // r14d
  __int64 v6; // r15
  int v7; // edx
  LPWSTR v8; // rdi
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rax
  const char *v13; // r9
  struct CMsiEnvironmentBlock *SystemEnvironment; // rax
  __int64 (*v15)(void); // rdi
  HWND hwnd; // rbx
  __int64 v17; // rax
  int v18; // eax
  BOOL v19; // ebx
  __int64 (*v20)(void); // rdi
  HWND v21; // rbx
  __int64 v22; // rax
  const wchar_t *i; // rbx
  wchar_t *v24; // rax
  const unsigned __int16 *v25; // rdi
  const unsigned __int16 *j; // rbx
  const unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // r9
  int v29; // eax
  unsigned __int16 v30; // r8
  DWORD v31; // r12d
  char v32; // dl
  char v33; // r10
  __int16 v34; // r9
  const struct IMsiString *v35; // rbx
  void *v36; // r15
  void *v37; // r13
  struct IMsiServices *Services; // rdi
  const unsigned __int16 *v39; // rax
  struct IMsiRecord *v40; // rax
  _QWORD *v41; // rax
  int v42; // eax
  const WCHAR *v43; // rax
  DWORD v44; // eax
  __int64 (__fastcall *v45)(struct IMsiServices *, __int64, __int64); // rdi
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  ULONG_PTR v49; // rdi
  __int64 (__fastcall *v50)(ULONG_PTR, __int64, char *, _BYTE *, char *, __int16 *); // rbx
  __int64 v51; // rax
  __int64 v52; // rax
  int v53; // ecx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v54; // rax
  void *UserToken; // rax
  bool v56; // bl
  void *v57; // rdi
  HANDLE CurrentProcess; // rax
  UINT v59; // ebx
  void *v60; // rcx
  void *AISToken; // rax
  void *v62; // rdi
  DWORD LastError; // eax
  UINT v64; // ebx
  DWORD v65; // eax
  __int64 v66; // rcx
  UINT v67; // ebx
  void *v68; // rax
  __int64 v69; // rdx
  DWORD v70; // ebx
  unsigned int v71; // edx
  bool v72; // cl
  DWORD v73; // ebx
  unsigned int lpProcessInformation; // [rsp+50h] [rbp-B0h]
  void *v76; // [rsp+58h] [rbp-A8h]
  BOOL v77; // [rsp+60h] [rbp-A0h]
  DWORD ExitCode; // [rsp+64h] [rbp-9Ch] BYREF
  char v79; // [rsp+68h] [rbp-98h] BYREF
  char v80; // [rsp+69h] [rbp-97h] BYREF
  bool started; // [rsp+6Ah] [rbp-96h]
  DWORD ReturnLength[2]; // [rsp+70h] [rbp-90h] BYREF
  void *phNewToken; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v84[8]; // [rsp+80h] [rbp-80h] BYREF
  const struct IMsiString *TokenInformation; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  __int16 v87[2]; // [rsp+98h] [rbp-68h] BYREF
  __int16 Value; // [rsp+9Ch] [rbp-64h] BYREF
  ULONG_PTR Size; // [rsp+A0h] [rbp-60h] BYREF
  PWSTR Environment; // [rsp+A8h] [rbp-58h] BYREF
  PWSTR lpEnvironment; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpCurrentDirectory; // [rsp+B8h] [rbp-48h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+C0h] [rbp-40h] BYREF
  struct IMsiServices *v94; // [rsp+D8h] [rbp-28h]
  _QWORD v95[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v97; // [rsp+158h] [rbp+58h]
  struct tagMSG lpString; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR lpCommandLine; // [rsp+190h] [rbp+90h] BYREF
  int v100; // [rsp+198h] [rbp+98h]

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
  v2 = (__int64 *)*((_QWORD *)this + 9);
  StartupInfo.cb = 112;
  Value = -31132;
  v3 = 0;
  ExitCode = 0;
  Environment = 0;
  lpEnvironment = 0;
  v4 = *v2;
  v77 = 0;
  started = 0;
  v95[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *))(v4 + 56))(v2);
  v6 = (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 56LL))(*((_QWORD *)this + 8));
  if ( (*((_DWORD *)this + 2) & 0x30) == 0x20 )
    v7 = v5;
  else
    v7 = v6 + v5 + 3;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&lpCommandLine, (unsigned int)(v7 + 1));
  v8 = lpCommandLine;
  if ( !lpCommandLine )
    goto LABEL_136;
  v9 = v100;
  if ( (*((_DWORD *)this + 2) & 0x30) == 0x20 )
  {
    lpCurrentDirectory = (LPCWSTR)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
  }
  else
  {
    *lpCommandLine = 34;
    v10 = v8 + 1;
    v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8));
    if ( (int)StringCchCopyW(v10, v9 - 1, v11) < 0 )
      goto LABEL_136;
    v10[v6] = 34;
    v9 -= (int)v6 + 2;
    lpCurrentDirectory = 0;
    v8 = &v10[v6 + 1];
    if ( v5 )
    {
      *v8++ = 32;
      --v9;
    }
  }
  v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 80LL))(*((_QWORD *)this + 9));
  if ( (int)StringCchCopyW(v8, v9, v12) < 0 )
  {
    if ( g_dmDiagnosticMode )
    {
      v13 = "ERROR: StringCchCopy failure in CustomExeThread";
LABEL_13:
      DebugString(9, 0, 0, v13, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", lpProcessInformation, v76);
    }
LABEL_136:
    v19 = 0;
    goto LABEL_137;
  }
  if ( g_scServerContext == 2 )
    started = StartImpersonating();
  if ( (*((_DWORD *)this + 2) & 0x10000) != 0 )
    DebugBreak();
  if ( qword_180309788 )
  {
    if ( !CMsiEnvironmentBlock::InitializeFromSource((CMsiEnvironmentBlock *)&Environment, qword_180309788) )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_136;
      v13 = "ERROR: Failed to initialize impersonate custom action environment block from session environment";
      goto LABEL_13;
    }
  }
  else if ( !CMsiEnvironmentBlock::InitializeFromProcessEnvironment(&Environment) )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_136;
    v13 = "ERROR: Failed to initialize impersonate custom action environment block from process environment";
    goto LABEL_13;
  }
  SystemEnvironment = MsiUIMessageContext::GetSystemEnvironment((MsiUIMessageContext *)&g_MessageContext);
  if ( SystemEnvironment )
  {
    if ( !CMsiEnvironmentBlock::InitializeFromSource((CMsiEnvironmentBlock *)&lpEnvironment, SystemEnvironment) )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_136;
      v13 = "ERROR: Failed to initialize system custom action environment block from session environment";
      goto LABEL_13;
    }
  }
  else if ( !CMsiEnvironmentBlock::InitializeFromProcessEnvironment(&lpEnvironment) )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_136;
    v13 = "ERROR: Failed to initialize system custom action environment block from process environment";
    goto LABEL_13;
  }
  if ( *((_BYTE *)this + 136) )
  {
    CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&lpString, 523);
    if ( !lpString.hwnd )
    {
LABEL_34:
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
      goto LABEL_136;
    }
    LODWORD(TokenInformation) = lpString.message;
    *(_WORD *)lpString.hwnd = 0;
    v15 = APPHELP::ApphelpFixMsiPackageExe;
    hwnd = lpString.hwnd;
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 80LL))(*(_QWORD *)this);
    v18 = ((__int64 (__fastcall *)(char *, char *, __int64, HWND, const struct IMsiString **))v15)(
            (char *)this + 140,
            (char *)this + 156,
            v17,
            hwnd,
            &TokenInformation);
    v19 = 0;
    if ( !v18 )
      goto LABEL_41;
    if ( (unsigned int)TokenInformation > lpString.message )
    {
      CTempBuffer<unsigned short,1>::SetSize(&lpString);
      if ( !lpString.hwnd )
      {
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
        goto LABEL_137;
      }
      LODWORD(TokenInformation) = lpString.message;
      *(_WORD *)lpString.hwnd = 0;
      v20 = APPHELP::ApphelpFixMsiPackageExe;
      v21 = lpString.hwnd;
      v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 80LL))(*(_QWORD *)this);
      if ( !((unsigned int (__fastcall *)(char *, char *, __int64, HWND, const struct IMsiString **))v20)(
              (char *)this + 140,
              (char *)this + 156,
              v22,
              v21,
              &TokenInformation)
        || (unsigned int)TokenInformation > lpString.message )
      {
LABEL_41:
        *(_WORD *)lpString.hwnd = 0;
      }
    }
    if ( lstrlenW((LPCWSTR)lpString.hwnd) )
    {
      for ( i = (const wchar_t *)lpString.hwnd; ; i = j + 1 )
      {
        if ( !*i )
          goto LABEL_56;
        v24 = wcschr(i, 0x3Du);
        if ( !v24 )
          goto LABEL_56;
        v25 = v24 + 1;
        *v24 = 0;
        if ( !CMsiEnvironmentBlock::Set((CMsiEnvironmentBlock *)&Environment, i, v24 + 1) )
          break;
        if ( !CMsiEnvironmentBlock::Set((CMsiEnvironmentBlock *)&lpEnvironment, i, v25) )
        {
          if ( !g_dmDiagnosticMode )
            goto LABEL_34;
          v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 80LL))(*(_QWORD *)this);
          v28 = L"ERROR: Failed to apply app compat flags to system environment for custom action %s.";
          goto LABEL_53;
        }
        for ( j = v25; *j; ++j )
          ;
      }
      if ( g_dmDiagnosticMode )
      {
        v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 80LL))(*(_QWORD *)this);
        v28 = L"ERROR: Failed to apply app compat flags to impersonate environment for custom action %s.";
LABEL_53:
        DebugString(10, 0, 0, v28, v27, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
LABEL_56:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
  }
  v29 = *((_DWORD *)this + 2);
  v30 = g_wArchitecture;
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  v84[0] = 0;
  v79 = 0;
  v87[0] = -1;
  v31 = ((v29 & 0x80) << 17) | 0x80420;
  v32 = 1;
  v80 = 1;
  v33 = 0;
  v34 = -1;
  if ( g_wArchitecture == 12 )
  {
    Size = 0;
    phNewToken = 0;
    v35 = (const struct IMsiString *)&MsiString::s_NullString;
    TokenInformation = (const struct IMsiString *)&MsiString::s_NullString;
    v36 = &MsiString::s_NullString;
    *(_QWORD *)ReturnLength = &MsiString::s_NullString;
    v37 = &MsiString::s_NullString;
    TokenHandle = &MsiString::s_NullString;
    Services = LoadServices();
    v94 = Services;
    if ( !Services )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Failed to Load Services",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      ExitCode = 1601;
      goto LABEL_70;
    }
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    ExitCode = ExtractExeFromCommandLine(lpCommandLine, &TokenInformation);
    if ( !ExitCode )
    {
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v35 = TokenInformation;
      v39 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)TokenInformation
                                                                                           + 80LL))(TokenInformation);
      v40 = SplitPath(v39, (const struct IMsiString **)ReturnLength, (const struct IMsiString **)&TokenHandle);
      v41 = (_QWORD *)CComPointer<IMsiDatabase>::operator=(&phNewToken, v40);
      v36 = *(void **)ReturnLength;
      if ( *v41 )
      {
        v37 = TokenHandle;
LABEL_70:
        if ( phNewToken || ExitCode )
          ExitCode = 2;
        if ( Services )
          FreeServices();
        (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v35 + 16LL))(v35);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&phNewToken);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Size);
        v29 = *((_DWORD *)this + 2);
        v33 = v79;
        v30 = g_wArchitecture;
        v32 = v80;
        v34 = v87[0];
        v3 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)v95[0];
        goto LABEL_76;
      }
      v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**(_QWORD **)ReturnLength + 200LL))(
              *(_QWORD *)ReturnLength,
              0,
              &Default);
      v37 = TokenHandle;
      if ( v42 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
        *(_QWORD *)ReturnLength = &MsiString::s_NullString;
        v43 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v37 + 80LL))(v37);
        v44 = SearchForExePath(v43, (const struct IMsiString **)ReturnLength);
        v36 = *(void **)ReturnLength;
        ExitCode = v44;
        if ( v44 )
          goto LABEL_70;
      }
      v45 = *(__int64 (__fastcall **)(struct IMsiServices *, __int64, __int64))(*(_QWORD *)Services + 120LL);
      v46 = CComPointer<IEnumMsiRecord>::operator=(&Size);
      v47 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v36 + 80LL))(v36);
      v48 = v45(v94, v47, v46);
      if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&phNewToken, v48) )
      {
        v49 = Size;
        v50 = *(__int64 (__fastcall **)(ULONG_PTR, __int64, char *, _BYTE *, char *, __int16 *))(*(_QWORD *)Size + 456LL);
        v51 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v37 + 80LL))(v37);
        v52 = v50(v49, v51, &v80, v84, &v79, v87);
        CComPointer<IMsiDatabase>::operator=(&phNewToken, v52);
      }
      Services = v94;
    }
    v35 = TokenInformation;
    goto LABEL_70;
  }
LABEL_76:
  v53 = v29;
  if ( !v32 )
  {
    ExitCode = 216;
LABEL_78:
    v19 = v77;
    goto LABEL_137;
  }
  if ( !ExitCode
    && v30 == 12
    && v34 == 12
    && v33
    && g_w64BitCustomActionPlatform != 12
    && (g_w64BitCustomActionPlatform != 0xFFFF || g_wPackagePlatform != 12) )
  {
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    v54 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new(Size);
    v3 = v54;
    if ( !v54 )
      goto LABEL_78;
    if ( !InitializeProcThreadAttributeList(v54, 1u, 0, &Size) )
    {
      operator delete(v3);
      v3 = 0;
      goto LABEL_78;
    }
    if ( !UpdateProcThreadAttribute(v3, 0, 0x20019u, &Value, 2u, 0, 0) )
      goto LABEL_78;
    v29 = *((_DWORD *)this + 2);
    v53 = v29;
    v97 = v3;
  }
  if ( g_scServerContext == 2 )
  {
    if ( *((_BYTE *)this + 125) )
    {
      if ( (v53 & 0xC00) == 0xC00 )
      {
        UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
        phNewToken = 0;
        TokenHandle = 0;
        v56 = 0;
        v57 = UserToken;
        CElevate::CElevate((CElevate *)v95, 1);
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
        {
          if ( TokenHandle )
          {
            if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, &phNewToken) )
            {
              if ( phNewToken )
              {
                LODWORD(TokenInformation) = 0;
                ReturnLength[0] = 0;
                if ( GetTokenInformation(v57, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
                  v56 = SetTokenInformation(phNewToken, TokenSessionId, &TokenInformation, 4u);
              }
            }
          }
        }
        CElevate::~CElevate((CElevate *)v95);
        if ( v56 )
        {
          v59 = SetErrorMode(3u);
          v77 = CreateProcessAsUserW(
                  phNewToken,
                  0,
                  lpCommandLine,
                  0,
                  0,
                  0,
                  v31 | 4,
                  lpEnvironment,
                  lpCurrentDirectory,
                  &StartupInfo,
                  &ProcessInformation);
          SetErrorMode(v59);
        }
        if ( phNewToken )
          CloseHandle(phNewToken);
        v60 = TokenHandle;
        if ( !TokenHandle )
          goto LABEL_129;
        goto LABEL_128;
      }
    }
    else
    {
      v53 = v29;
    }
    if ( (v53 & 0x80000) != 0 )
      AISToken = GetAISToken();
    else
      AISToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    *(_QWORD *)ReturnLength = -1;
    if ( AISToken )
    {
      DuplicateTokenEx(AISToken, 0, 0, SecurityAnonymous, TokenPrimary, (PHANDLE)ReturnLength);
      v62 = *(void **)ReturnLength;
      *(_QWORD *)ReturnLength = -1;
      if ( v62 != (void *)-1LL )
      {
        if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, void *, DWORD *, __int64, _QWORD))ADVAPI32::SaferComputeTokenFromLevel)(
                              xmmword_180309760,
                              v62,
                              ReturnLength,
                              4,
                              0) )
        {
          if ( g_dmDiagnosticMode )
          {
            LastError = GetLastError();
            DebugString(
              9,
              0,
              0,
              L"SaferComputeTokenFromLevel failed with last error = %d",
              (const unsigned __int16 *)LastError,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          *(_QWORD *)ReturnLength = -1;
        }
        CloseHandle(v62);
        if ( *(_QWORD *)ReturnLength != -1 )
        {
          v64 = SetErrorMode(3u);
          v77 = CreateProcessAsUserW(
                  *(HANDLE *)ReturnLength,
                  0,
                  lpCommandLine,
                  0,
                  0,
                  0,
                  v31,
                  Environment,
                  lpCurrentDirectory,
                  &StartupInfo,
                  &ProcessInformation);
          SetErrorMode(v64);
          CloseHandle(*(HANDLE *)ReturnLength);
        }
      }
    }
    goto LABEL_78;
  }
  phNewToken = (void *)-1LL;
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, void **, __int64, _QWORD))ADVAPI32::SaferComputeTokenFromLevel)(
                       xmmword_180309760,
                       0,
                       &phNewToken,
                       4,
                       0) )
  {
    v66 = (__int64)phNewToken;
  }
  else
  {
    if ( g_dmDiagnosticMode )
    {
      v65 = GetLastError();
      DebugString(
        9,
        0,
        0,
        L"SaferComputeTokenFromLevel failed with last error = %d",
        (const unsigned __int16 *)v65,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v66 = -1;
    phNewToken = (void *)-1LL;
  }
  if ( v66 == -1 )
    goto LABEL_78;
  TokenHandle = (void *)-1LL;
  if ( DuplicateTokenEx((HANDLE)v66, 0, 0, SecurityAnonymous, TokenPrimary, &TokenHandle) )
  {
    v67 = SetErrorMode(3u);
    v77 = CreateProcessAsUserW(
            TokenHandle,
            0,
            lpCommandLine,
            0,
            0,
            0,
            v31 | 4,
            Environment,
            lpCurrentDirectory,
            &StartupInfo,
            &ProcessInformation);
    SetErrorMode(v67);
    CloseHandle(TokenHandle);
  }
  v60 = phNewToken;
LABEL_128:
  CloseHandle(v60);
LABEL_129:
  v19 = v77;
  if ( v77 )
  {
    CElevate::CElevate((CElevate *)&TokenHandle, 1);
    if ( (*((_DWORD *)this + 2) & 0x40000) == 0
      || (v68 = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext),
          SetThreadToken(&ProcessInformation.hThread, v68))
      || (unsigned int)IsTerminalServerInstalled() )
    {
      ResumeThread(ProcessInformation.hThread);
    }
    else
    {
      TerminateProcess(ProcessInformation.hProcess, 0xFFFFFFFF);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
    }
    CElevate::~CElevate((CElevate *)&TokenHandle);
  }
LABEL_137:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
  if ( !v19 )
  {
    v69 = 1631;
LABEL_152:
    ExitCode = v69;
    goto LABEL_153;
  }
  CloseHandle(ProcessInformation.hThread);
  if ( *((char *)this + 8) >= 0
    || (v70 = 0, (*((_DWORD *)this + 2) & 0x500) != 1280 && (*((_BYTE *)this + 8) & 0x40) == 0) )
  {
    while ( 1 )
    {
      v70 = MsgWaitForMultipleObjects(1u, &ProcessInformation.hProcess, 0, 0xFFFFFFFF, 0x1CFFu);
      if ( v70 != 1 )
        break;
      memset(&lpString, 0, sizeof(lpString));
      while ( PeekMessageW(&lpString, 0, 0, 0, 1u) )
      {
        TranslateMessage(&lpString);
        DispatchMessageW(&lpString);
      }
    }
    GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
    ThreadLogActionReturn(this, ExitCode);
    if ( (*((_BYTE *)this + 8) & 0x40) != 0 )
      ExitCode = 0;
  }
  CloseHandle(ProcessInformation.hProcess);
  if ( v70 == -1 || (v69 = ExitCode, (*((_DWORD *)this + 2) & 0x20000) == 0) && ExitCode )
  {
    v69 = 1603;
    goto LABEL_152;
  }
LABEL_153:
  ThreadLogActionEnd(this, v69);
  if ( v3 )
  {
    DeleteProcThreadAttributeList(v3);
    operator delete(v3);
  }
  if ( *((char *)this + 8) >= 0 )
    CActionThreadData::`scalar deleting destructor'(this, v71);
  if ( started )
    StopImpersonating(v72);
  v73 = ExitCode;
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpCommandLine);
  CMsiEnvironmentBlock::~CMsiEnvironmentBlock((CMsiEnvironmentBlock *)&lpEnvironment);
  CMsiEnvironmentBlock::~CMsiEnvironmentBlock((CMsiEnvironmentBlock *)&Environment);
  return v73;
}

```

## disassembly

```asm
0x1801c0f10  push    rbp
0x1801c0f12  push    rbx
0x1801c0f13  push    rsi
0x1801c0f14  push    rdi
0x1801c0f15  push    r12
0x1801c0f17  push    r13
0x1801c0f19  push    r14
0x1801c0f1b  push    r15
0x1801c0f1d  lea     rbp, [rsp-0B8h]
0x1801c0f25  sub     rsp, 1B8h
0x1801c0f2c  mov     rax, cs:__security_cookie
0x1801c0f33  xor     rax, rsp
0x1801c0f36  mov     [rbp+0F0h+var_48], rax
0x1801c0f3d  xor     eax, eax
0x1801c0f3f  mov     rsi, rcx
0x1801c0f42  xorps   xmm0, xmm0
0x1801c0f45  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x1801c0f49  xor     edx, edx; Val
0x1801c0f4b  lea     rcx, [rbp+0F0h+StartupInfo+4]; void *
0x1801c0f4f  movups  xmmword ptr [rbp+0F0h+ProcessInformation.hProcess], xmm0
0x1801c0f53  lea     r8d, [rax+6Ch]; Size
0x1801c0f57  call    memset_0
0x1801c0f5c  mov     rcx, [rsi+48h]
0x1801c0f60  xor     r12d, r12d
0x1801c0f63  mov     eax, 8664h
0x1801c0f68  mov     [rbp+0F0h+StartupInfo.cb], 70h ; 'p'
0x1801c0f6f  mov     [rbp+0F0h+Value], ax
0x1801c0f73  mov     r13d, r12d
0x1801c0f76  mov     [rsp+1F0h+ExitCode], r12d
0x1801c0f7b  mov     [rbp+0F0h+Environment], r12
0x1801c0f7f  mov     [rbp+0F0h+var_140], r12
0x1801c0f83  mov     rax, [rcx]
0x1801c0f86  mov     [rsp+1F0h+var_190], r12d
0x1801c0f8b  mov     [rsp+1F0h+var_186], r12b
0x1801c0f90  mov     [rbp+0F0h+var_110], r12
0x1801c0f94  mov     rax, [rax+38h]
0x1801c0f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0f9d  mov     rcx, [rsi+40h]
0x1801c0fa1  mov     r14d, eax
0x1801c0fa4  mov     rax, [rcx]
0x1801c0fa7  mov     rax, [rax+38h]
0x1801c0fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0fb0  movsxd  r15, eax
0x1801c0fb3  mov     eax, [rsi+8]
0x1801c0fb6  and     al, 30h
0x1801c0fb8  cmp     al, 20h ; ' '
0x1801c0fba  jz      short loc_1801C0FC5
0x1801c0fbc  lea     edx, [r14+3]
0x1801c0fc0  add     edx, r15d
0x1801c0fc3  jmp     short loc_1801C0FC8
0x1801c0fc5  mov     edx, r14d
0x1801c0fc8  inc     edx
0x1801c0fca  lea     rcx, [rbp+0F0h+lpCommandLine]
0x1801c0fd1  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801c0fd6  mov     rdi, [rbp+0F0h+lpCommandLine]
0x1801c0fdd  test    rdi, rdi
0x1801c0fe0  jz      loc_1801C1C9D
0x1801c0fe6  mov     eax, [rsi+8]
0x1801c0fe9  movsxd  rbx, [rbp+0F0h+var_58]
0x1801c0ff0  and     al, 30h
0x1801c0ff2  cmp     al, 20h ; ' '
0x1801c0ff4  jz      short loc_1801C1059
0x1801c0ff6  mov     word ptr [rdi], 22h ; '"'
0x1801c0ffb  add     rdi, 2
0x1801c0fff  mov     rcx, [rsi+40h]
0x1801c1003  mov     rax, [rcx]
0x1801c1006  mov     rax, [rax+50h]
0x1801c100a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c100f  mov     r8, rax; unsigned __int16 *
0x1801c1012  lea     rdx, [rbx-1]; unsigned __int64
0x1801c1016  mov     rcx, rdi; unsigned __int16 *
0x1801c1019  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c101e  test    eax, eax
0x1801c1020  js      loc_1801C1C9D
0x1801c1026  mov     word ptr [rdi+r15*2], 22h ; '"'
0x1801c102d  lea     eax, [r15+2]
0x1801c1031  lea     rdi, [rdi+r15*2]
0x1801c1035  movsxd  rcx, eax
0x1801c1038  sub     rbx, rcx
0x1801c103b  mov     [rbp+0F0h+var_138], r12
0x1801c103f  add     rdi, 2
0x1801c1043  xor     r15d, r15d
0x1801c1046  test    r14d, r14d
0x1801c1049  jz      short loc_1801C1070
0x1801c104b  mov     word ptr [rdi], 20h ; ' '
0x1801c1050  add     rdi, 2
0x1801c1054  dec     rbx
0x1801c1057  jmp     short loc_1801C1070
0x1801c1059  mov     rcx, [rsi+40h]
0x1801c105d  mov     rax, [rcx]
0x1801c1060  mov     rax, [rax+50h]
0x1801c1064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c1069  mov     [rbp+0F0h+var_138], rax
0x1801c106d  xor     r15d, r15d
0x1801c1070  mov     rcx, [rsi+48h]
0x1801c1074  mov     rax, [rcx]
0x1801c1077  mov     rax, [rax+50h]
0x1801c107b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c1080  mov     r8, rax; unsigned __int16 *
0x1801c1083  mov     rdx, rbx; unsigned __int64
0x1801c1086  mov     rcx, rdi; unsigned __int16 *
0x1801c1089  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c108e  test    eax, eax
0x1801c1090  jns     short loc_1801C10DD
0x1801c1092  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c1099  jz      loc_1801C1CA0
0x1801c109f  lea     r9, aErrorStringcch_1; "ERROR: StringCchCopy failure in CustomE"...
0x1801c10a6  lea     rax, aNull_0; "(NULL)"
0x1801c10ad  xor     edx, edx; unsigned __int16
0x1801c10af  mov     [rsp+1F0h+lpStartupInfo], rax; char *
0x1801c10b4  xor     r8d, r8d; int
0x1801c10b7  mov     [rsp+1F0h+lpCurrentDirectory], rax; char *
0x1801c10bc  mov     [rsp+1F0h+lpEnvironment], rax; char *
0x1801c10c1  mov     [rsp+1F0h+lpReturnSize], rax; char *
0x1801c10c6  lea     ecx, [rdx+9]; int
0x1801c10c9  mov     [rsp+1F0h+lpPreviousValue], rax; char *
0x1801c10ce  mov     [rsp+1F0h+cbSize], rax; char *
0x1801c10d3  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c10d8  jmp     loc_1801C1CA0
0x1801c10dd  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801c10e4  jnz     short loc_1801C10EF
0x1801c10e6  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1801c10eb  mov     [rsp+1F0h+var_186], al
0x1801c10ef  test    dword ptr [rsi+8], 10000h
0x1801c10f6  jz      short loc_1801C10FE
0x1801c10f8  call    cs:__imp_DebugBreak
0x1801c10fe  mov     rdx, cs:qword_180309788; struct CMsiEnvironmentBlock *
0x1801c1105  lea     rcx, [rbp+0F0h+Environment]; Environment
0x1801c1109  test    rdx, rdx
0x1801c110c  jz      short loc_1801C1130
0x1801c110e  call    ?InitializeFromSource@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z; CMsiEnvironmentBlock::InitializeFromSource(CMsiEnvironmentBlock *)
0x1801c1113  test    al, al
0x1801c1115  jnz     short loc_1801C1152
0x1801c1117  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c111e  jz      loc_1801C1CA0
0x1801c1124  lea     r9, aErrorFailedToI; "ERROR: Failed to initialize impersonate"...
0x1801c112b  jmp     loc_1801C10A6
0x1801c1130  call    ?InitializeFromProcessEnvironment@CMsiEnvironmentBlock@@QEAA_NXZ; CMsiEnvironmentBlock::InitializeFromProcessEnvironment(void)
0x1801c1135  test    al, al
0x1801c1137  jnz     short loc_1801C1152
0x1801c1139  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c1140  jz      loc_1801C1CA0
0x1801c1146  lea     r9, aErrorFailedToI_2; "ERROR: Failed to initialize impersonate"...
0x1801c114d  jmp     loc_1801C10A6
0x1801c1152  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801c1159  call    ?GetSystemEnvironment@MsiUIMessageContext@@QEAAPEAVCMsiEnvironmentBlock@@XZ; MsiUIMessageContext::GetSystemEnvironment(void)
0x1801c115e  lea     rcx, [rbp+0F0h+var_140]; Environment
0x1801c1162  test    rax, rax
0x1801c1165  jz      short loc_1801C118C
0x1801c1167  mov     rdx, rax; struct CMsiEnvironmentBlock *
0x1801c116a  call    ?InitializeFromSource@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z; CMsiEnvironmentBlock::InitializeFromSource(CMsiEnvironmentBlock *)
0x1801c116f  test    al, al
0x1801c1171  jnz     short loc_1801C11AE
0x1801c1173  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c117a  jz      loc_1801C1CA0
0x1801c1180  lea     r9, aErrorFailedToI_1; "ERROR: Failed to initialize system cust"...
0x1801c1187  jmp     loc_1801C10A6
0x1801c118c  call    ?InitializeFromProcessEnvironment@CMsiEnvironmentBlock@@QEAA_NXZ; CMsiEnvironmentBlock::InitializeFromProcessEnvironment(void)
0x1801c1191  test    al, al
0x1801c1193  jnz     short loc_1801C11AE
0x1801c1195  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c119c  jz      loc_1801C1CA0
0x1801c11a2  lea     r9, aErrorFailedToI_0; "ERROR: Failed to initialize system cust"...
0x1801c11a9  jmp     loc_1801C10A6
0x1801c11ae  cmp     [rsi+88h], r15b
0x1801c11b5  jz      loc_1801C13E0
0x1801c11bb  mov     edx, 20Bh
0x1801c11c0  lea     rcx, [rbp+0F0h+lpString]
0x1801c11c4  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801c11c9  mov     rcx, [rbp+0F0h+lpString]
0x1801c11cd  test    rcx, rcx
0x1801c11d0  jnz     short loc_1801C11E0
0x1801c11d2  lea     rcx, [rbp+0F0h+lpString]
0x1801c11d6  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801c11db  jmp     loc_1801C1CA0
0x1801c11e0  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c11e3  mov     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c11e6  mov     [rcx], r15w
0x1801c11ea  mov     rcx, [rsi]
0x1801c11ed  mov     rdi, cs:?ApphelpFixMsiPackageExe@APPHELP@@3P6AHPEAU_GUID@@0PEBGPEAGPEAK@ZEA; int (*APPHELP::ApphelpFixMsiPackageExe)(_GUID *,_GUID *,ushort const *,ushort *,ulong *)
0x1801c11f4  mov     rbx, [rbp+0F0h+lpString]
0x1801c11f8  mov     rax, [rcx]
0x1801c11fb  mov     rax, [rax+50h]
0x1801c11ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c1204  lea     rcx, [rbp+0F0h+TokenInformation]
0x1801c1208  mov     r8, rax
0x1801c120b  mov     [rsp+1F0h+cbSize], rcx
0x1801c1210  lea     r14, [rsi+9Ch]
0x1801c1217  lea     r15, [rsi+8Ch]
0x1801c121e  mov     r9, rbx
0x1801c1221  mov     rcx, r15
0x1801c1224  mov     rdx, r14
0x1801c1227  mov     rax, rdi
0x1801c122a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c122f  xor     ebx, ebx
0x1801c1231  test    eax, eax
0x1801c1233  jz      loc_1801C12B9
0x1801c1239  mov     edx, dword ptr [rbp+0F0h+TokenInformation]
0x1801c123c  cmp     edx, dword ptr [rbp+0F0h+lpString+8]
0x1801c123f  jbe     loc_1801C12C6
0x1801c1245  lea     rcx, [rbp+0F0h+lpString]
0x1801c1249  call    ?SetSize@?$CTempBuffer@G$00@@QEAAXH@Z; CTempBuffer<ushort,1>::SetSize(int)
0x1801c124e  mov     rcx, [rbp+0F0h+lpString]
0x1801c1252  test    rcx, rcx
0x1801c1255  jnz     short loc_1801C1268
0x1801c1257  lea     rcx, [rbp+0F0h+lpString]
0x1801c125b  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801c1260  xor     r15d, r15d
0x1801c1263  jmp     loc_1801C1CA3
0x1801c1268  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c126b  mov     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c126e  mov     [rcx], bx
0x1801c1271  mov     rcx, [rsi]
0x1801c1274  mov     rdi, cs:?ApphelpFixMsiPackageExe@APPHELP@@3P6AHPEAU_GUID@@0PEBGPEAGPEAK@ZEA; int (*APPHELP::ApphelpFixMsiPackageExe)(_GUID *,_GUID *,ushort const *,ushort *,ulong *)
0x1801c127b  mov     rbx, [rbp+0F0h+lpString]
0x1801c127f  mov     rax, [rcx]
0x1801c1282  mov     rax, [rax+50h]
0x1801c1286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c128b  lea     rcx, [rbp+0F0h+TokenInformation]
0x1801c128f  mov     r8, rax
0x1801c1292  mov     [rsp+1F0h+cbSize], rcx
0x1801c1297  mov     r9, rbx
0x1801c129a  mov     rcx, r15
0x1801c129d  mov     rdx, r14
0x1801c12a0  mov     rax, rdi
0x1801c12a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c12a8  xor     r15d, r15d
0x1801c12ab  test    eax, eax
0x1801c12ad  jz      short loc_1801C12BC
0x1801c12af  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c12b2  cmp     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c12b5  jbe     short loc_1801C12C9
0x1801c12b7  jmp     short loc_1801C12BC
0x1801c12b9  xor     r15d, r15d
0x1801c12bc  mov     rax, [rbp+0F0h+lpString]
0x1801c12c0  mov     [rax], r15w
0x1801c12c4  jmp     short loc_1801C12C9
0x1801c12c6  xor     r15d, r15d
0x1801c12c9  mov     rcx, [rbp+0F0h+lpString]; lpString
0x1801c12cd  call    cs:__imp_lstrlenW
0x1801c12d3  test    eax, eax
0x1801c12d5  jz      loc_1801C13D7
0x1801c12db  mov     rbx, [rbp+0F0h+lpString]
0x1801c12df  cmp     [rbx], r15w
0x1801c12e3  jz      loc_1801C13D7
0x1801c12e9  mov     edx, 3Dh ; '='; Ch
0x1801c12ee  mov     rcx, rbx; Str
0x1801c12f1  call    cs:__imp_wcschr
0x1801c12f7  mov     rdi, rax
0x1801c12fa  test    rax, rax
0x1801c12fd  jz      loc_1801C13D7
0x1801c1303  add     rdi, 2
0x1801c1307  mov     [rax], r15w
0x1801c130b  mov     r8, rdi; unsigned __int16 *
0x1801c130e  lea     rcx, [rbp+0F0h+Environment]; this
0x1801c1312  mov     rdx, rbx; unsigned __int16 *
0x1801c1315  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c131a  test    al, al
0x1801c131c  jz      loc_1801C13B2
0x1801c1322  mov     r8, rdi; unsigned __int16 *
0x1801c1325  lea     rcx, [rbp+0F0h+var_140]; this
0x1801c1329  mov     rdx, rbx; unsigned __int16 *
0x1801c132c  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c1331  test    al, al
0x1801c1333  jz      short loc_1801C134E
0x1801c1335  mov     rbx, rdi
0x1801c1338  cmp     [rdi], r15w
0x1801c133c  jz      short loc_1801C1348
0x1801c133e  add     rbx, 2
0x1801c1342  cmp     [rbx], r15w
0x1801c1346  jnz     short loc_1801C133E
0x1801c1348  add     rbx, 2
0x1801c134c  jmp     short loc_1801C12DF
0x1801c134e  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c1355  jz      loc_1801C11D2
0x1801c135b  mov     rcx, [rsi]
0x1801c135e  mov     rax, [rcx]
0x1801c1361  mov     rax, [rax+50h]
0x1801c1365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c136a  lea     r9, aErrorFailedToA_1; "ERROR: Failed to apply app compat flags"...
0x1801c1371  mov     [rsp+1F0h+var_198], r15; void *
0x1801c1376  lea     r14, aNull; "(NULL)"
0x1801c137d  mov     dword ptr [rsp+1F0h+lpProcessInformation], r15d; unsigned int
0x1801c1382  xor     edx, edx; unsigned __int16
0x1801c1384  mov     [rsp+1F0h+lpStartupInfo], r14; unsigned __int16 *
0x1801c1389  xor     r8d, r8d; int
0x1801c138c  mov     [rsp+1F0h+lpCurrentDirectory], r14; unsigned __int16 *
0x1801c1391  mov     [rsp+1F0h+lpEnvironment], r14; unsigned __int16 *
0x1801c1396  mov     [rsp+1F0h+lpReturnSize], r14; unsigned __int16 *
0x1801c139b  lea     ecx, [rdx+0Ah]; int
0x1801c139e  mov     [rsp+1F0h+lpPreviousValue], r14; unsigned __int16 *
0x1801c13a3  mov     [rsp+1F0h+cbSize], rax; unsigned __int16 *
0x1801c13a8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801c13ad  jmp     loc_1801C11D2
0x1801c13b2  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c13b9  jz      loc_1801C11D2
0x1801c13bf  mov     rcx, [rsi]
0x1801c13c2  mov     rax, [rcx]
0x1801c13c5  mov     rax, [rax+50h]
0x1801c13c9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
