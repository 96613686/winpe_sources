# CustomExeThread(CActionThreadData *)

- ea: `0x1801c94b0`
- end: `0x1801ca4da`
- name: `?CustomExeThread@@YAKPEAVCActionThreadData@@@Z`
- size: `4138`
- prototype: `unsigned int __fastcall(struct CActionThreadData *this)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180014160`
- `0x180014528`
- `0x180018ee0`
- `0x180019cc0`
- `0x18001a5b4`
- `0x180027634`
- `0x18002e870`
- `0x180067fec`
- `0x180068150`
- `0x18006d108`
- `0x180077470`
- `0x18009bf74`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800c08f8`
- `0x1800c6b44`
- `0x1800eee44`
- `0x18015bc90`
- `0x18015bdf4`
- `0x1801c8548`
- `0x1801c865c`
- `0x1801c94b0`
- `0x1801cb2bc`
- `0x1801cbc84`
- `0x1801cc900`
- `0x1801cc93c`
- `0x1801ced10`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!wcschr` at `0x1801c989d`
- `msvcrt!wcschr` at `0x1801c989d`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c9f3c`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801ca0d8`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801ca22e`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801c9f3c`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801ca0d8`
- `ADVAPI32!CreateProcessAsUserW` at `0x1801ca22e`
- `ADVAPI32!SetTokenInformation` at `0x1801c9ec2`
- `ADVAPI32!SetTokenInformation` at `0x1801c9ec2`
- `ADVAPI32!GetTokenInformation` at `0x1801c9ea1`
- `ADVAPI32!GetTokenInformation` at `0x1801c9ea1`
- `ADVAPI32!SetThreadToken` at `0x1801ca2a0`
- `ADVAPI32!SetThreadToken` at `0x1801ca2a0`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c9e68`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c9fc8`
- `ADVAPI32!DuplicateTokenEx` at `0x1801ca1c0`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c9e68`
- `ADVAPI32!DuplicateTokenEx` at `0x1801c9fc8`
- `ADVAPI32!DuplicateTokenEx` at `0x1801ca1c0`
- `ADVAPI32!OpenProcessToken` at `0x1801c9e2d`
- `ADVAPI32!OpenProcessToken` at `0x1801c9e2d`
- `KERNEL32!CloseHandle` at `0x1801c9f64`
- `KERNEL32!CloseHandle` at `0x1801ca06a`
- `KERNEL32!CloseHandle` at `0x1801ca0fb`
- `KERNEL32!CloseHandle` at `0x1801ca250`
- `KERNEL32!CloseHandle` at `0x1801ca261`
- `KERNEL32!CloseHandle` at `0x1801ca341`
- `KERNEL32!CloseHandle` at `0x1801ca429`
- `KERNEL32!CloseHandle` at `0x1801c9f64`
- `KERNEL32!CloseHandle` at `0x1801ca06a`
- `KERNEL32!CloseHandle` at `0x1801ca0fb`
- `KERNEL32!CloseHandle` at `0x1801ca250`
- `KERNEL32!CloseHandle` at `0x1801ca261`
- `KERNEL32!CloseHandle` at `0x1801ca341`
- `KERNEL32!CloseHandle` at `0x1801ca429`
- `KERNEL32!DebugBreak` at `0x1801c9698`
- `KERNEL32!DebugBreak` at `0x1801c9698`
- `KERNEL32!GetLastError` at `0x1801ca018`
- `KERNEL32!GetLastError` at `0x1801ca145`
- `KERNEL32!GetLastError` at `0x1801ca018`
- `KERNEL32!GetLastError` at `0x1801ca145`
- `KERNEL32!GetCurrentProcess` at `0x1801c9e15`
- `KERNEL32!GetCurrentProcess` at `0x1801c9e15`
- `KERNEL32!lstrlenW` at `0x1801c9873`
- `KERNEL32!lstrlenW` at `0x1801c9873`
- `KERNEL32!SetErrorMode` at `0x1801c9ee6`
- `KERNEL32!SetErrorMode` at `0x1801c9f4e`
- `KERNEL32!SetErrorMode` at `0x1801ca086`
- `KERNEL32!SetErrorMode` at `0x1801ca0ea`
- `KERNEL32!SetErrorMode` at `0x1801ca1d9`
- `KERNEL32!SetErrorMode` at `0x1801ca240`
- `KERNEL32!SetErrorMode` at `0x1801c9ee6`
- `KERNEL32!SetErrorMode` at `0x1801c9f4e`
- `KERNEL32!SetErrorMode` at `0x1801ca086`
- `KERNEL32!SetErrorMode` at `0x1801ca0ea`
- `KERNEL32!SetErrorMode` at `0x1801ca1d9`
- `KERNEL32!SetErrorMode` at `0x1801ca240`
- `KERNEL32!ResumeThread` at `0x1801ca2fb`
- `KERNEL32!ResumeThread` at `0x1801ca2fb`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c9d36`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c9d63`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c9d36`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1801c9d63`
- `KERNEL32!UpdateProcThreadAttribute` at `0x1801c9da2`
- `KERNEL32!UpdateProcThreadAttribute` at `0x1801c9da2`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x1801ca464`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x1801ca464`
- `KERNEL32!TerminateProcess` at `0x1801ca2c0`
- `KERNEL32!TerminateProcess` at `0x1801ca2c0`
- `KERNEL32!GetExitCodeProcess` at `0x1801ca402`
- `KERNEL32!GetExitCodeProcess` at `0x1801ca402`
- `USER32!MsgWaitForMultipleObjects` at `0x1801ca3e6`
- `USER32!MsgWaitForMultipleObjects` at `0x1801ca3e6`
- `USER32!PeekMessageW` at `0x1801ca3c3`
- `USER32!PeekMessageW` at `0x1801ca3c3`
- `USER32!TranslateMessage` at `0x1801ca393`
- `USER32!TranslateMessage` at `0x1801ca393`
- `USER32!DispatchMessageW` at `0x1801ca3a3`
- `USER32!DispatchMessageW` at `0x1801ca3a3`

## string_xrefs

- `0x1801c9a3d`: `Failed to Load Services`
- `0x1801c963f`: `ERROR: StringCchCopy failure in CustomExeThread`
- `0x1801c96ca`: `ERROR: Failed to initialize impersonate custom action environment block from session environment`
- `0x1801c96ec`: `ERROR: Failed to initialize impersonate custom action environment block from process environment`
- `0x1801c9980`: `ERROR: Failed to apply app compat flags to impersonate environment for custom action %s.`
- `0x1801c991c`: `ERROR: Failed to apply app compat flags to system environment for custom action %s.`
- `0x1801ca029`: `SaferComputeTokenFromLevel failed with last error = %d`
- `0x1801ca156`: `SaferComputeTokenFromLevel failed with last error = %d`

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
  if ( qword_180313738 )
  {
    if ( !CMsiEnvironmentBlock::InitializeFromSource((CMsiEnvironmentBlock *)&Environment, qword_180313738) )
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
      CTempBuffer<unsigned short,1>::SetSize(&lpString, (unsigned int)TokenInformation);
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
                              xmmword_180313710,
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
                       xmmword_180313710,
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
0x1801c94b0  push    rbp
0x1801c94b2  push    rbx
0x1801c94b3  push    rsi
0x1801c94b4  push    rdi
0x1801c94b5  push    r12
0x1801c94b7  push    r13
0x1801c94b9  push    r14
0x1801c94bb  push    r15
0x1801c94bd  lea     rbp, [rsp-0B8h]
0x1801c94c5  sub     rsp, 1B8h
0x1801c94cc  mov     rax, cs:__security_cookie
0x1801c94d3  xor     rax, rsp
0x1801c94d6  mov     [rbp+0F0h+var_48], rax
0x1801c94dd  xor     eax, eax
0x1801c94df  mov     rsi, rcx
0x1801c94e2  xorps   xmm0, xmm0
0x1801c94e5  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x1801c94e9  xor     edx, edx; Val
0x1801c94eb  lea     rcx, [rbp+0F0h+StartupInfo+4]; void *
0x1801c94ef  movups  xmmword ptr [rbp+0F0h+ProcessInformation.hProcess], xmm0
0x1801c94f3  lea     r8d, [rax+6Ch]; Size
0x1801c94f7  call    memset_0
0x1801c94fc  mov     rcx, [rsi+48h]
0x1801c9500  xor     r12d, r12d
0x1801c9503  mov     eax, 8664h
0x1801c9508  mov     [rbp+0F0h+StartupInfo.cb], 70h ; 'p'
0x1801c950f  mov     [rbp+0F0h+Value], ax
0x1801c9513  mov     r13d, r12d
0x1801c9516  mov     [rsp+1F0h+ExitCode], r12d
0x1801c951b  mov     [rbp+0F0h+Environment], r12
0x1801c951f  mov     [rbp+0F0h+var_140], r12
0x1801c9523  mov     rax, [rcx]
0x1801c9526  mov     [rsp+1F0h+var_190], r12d
0x1801c952b  mov     [rsp+1F0h+var_186], r12b
0x1801c9530  mov     [rbp+0F0h+var_110], r12
0x1801c9534  mov     rax, [rax+38h]
0x1801c9538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c953d  mov     rcx, [rsi+40h]
0x1801c9541  mov     r14d, eax
0x1801c9544  mov     rax, [rcx]
0x1801c9547  mov     rax, [rax+38h]
0x1801c954b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9550  movsxd  r15, eax
0x1801c9553  mov     eax, [rsi+8]
0x1801c9556  and     al, 30h
0x1801c9558  cmp     al, 20h ; ' '
0x1801c955a  jz      short loc_1801C9565
0x1801c955c  lea     edx, [r14+3]
0x1801c9560  add     edx, r15d
0x1801c9563  jmp     short loc_1801C9568
0x1801c9565  mov     edx, r14d
0x1801c9568  inc     edx
0x1801c956a  lea     rcx, [rbp+0F0h+lpCommandLine]
0x1801c9571  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801c9576  mov     rdi, [rbp+0F0h+lpCommandLine]
0x1801c957d  test    rdi, rdi
0x1801c9580  jz      loc_1801CA309
0x1801c9586  mov     eax, [rsi+8]
0x1801c9589  movsxd  rbx, [rbp+0F0h+var_58]
0x1801c9590  and     al, 30h
0x1801c9592  cmp     al, 20h ; ' '
0x1801c9594  jz      short loc_1801C95F9
0x1801c9596  mov     word ptr [rdi], 22h ; '"'
0x1801c959b  add     rdi, 2
0x1801c959f  mov     rcx, [rsi+40h]
0x1801c95a3  mov     rax, [rcx]
0x1801c95a6  mov     rax, [rax+50h]
0x1801c95aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c95af  mov     r8, rax; unsigned __int16 *
0x1801c95b2  lea     rdx, [rbx-1]; unsigned __int64
0x1801c95b6  mov     rcx, rdi; unsigned __int16 *
0x1801c95b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c95be  test    eax, eax
0x1801c95c0  js      loc_1801CA309
0x1801c95c6  mov     word ptr [rdi+r15*2], 22h ; '"'
0x1801c95cd  lea     eax, [r15+2]
0x1801c95d1  lea     rdi, [rdi+r15*2]
0x1801c95d5  movsxd  rcx, eax
0x1801c95d8  sub     rbx, rcx
0x1801c95db  mov     [rbp+0F0h+var_138], r12
0x1801c95df  add     rdi, 2
0x1801c95e3  xor     r15d, r15d
0x1801c95e6  test    r14d, r14d
0x1801c95e9  jz      short loc_1801C9610
0x1801c95eb  mov     word ptr [rdi], 20h ; ' '
0x1801c95f0  add     rdi, 2
0x1801c95f4  dec     rbx
0x1801c95f7  jmp     short loc_1801C9610
0x1801c95f9  mov     rcx, [rsi+40h]
0x1801c95fd  mov     rax, [rcx]
0x1801c9600  mov     rax, [rax+50h]
0x1801c9604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9609  mov     [rbp+0F0h+var_138], rax
0x1801c960d  xor     r15d, r15d
0x1801c9610  mov     rcx, [rsi+48h]
0x1801c9614  mov     rax, [rcx]
0x1801c9617  mov     rax, [rax+50h]
0x1801c961b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9620  mov     r8, rax; unsigned __int16 *
0x1801c9623  mov     rdx, rbx; unsigned __int64
0x1801c9626  mov     rcx, rdi; unsigned __int16 *
0x1801c9629  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c962e  test    eax, eax
0x1801c9630  jns     short loc_1801C967D
0x1801c9632  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c9639  jz      loc_1801CA30C
0x1801c963f  lea     r9, aErrorStringcch_1; "ERROR: StringCchCopy failure in CustomE"...
0x1801c9646  lea     rax, aNull_0; "(NULL)"
0x1801c964d  xor     edx, edx; unsigned __int16
0x1801c964f  mov     [rsp+1F0h+lpStartupInfo], rax; char *
0x1801c9654  xor     r8d, r8d; int
0x1801c9657  mov     [rsp+1F0h+lpCurrentDirectory], rax; char *
0x1801c965c  mov     [rsp+1F0h+lpEnvironment], rax; char *
0x1801c9661  mov     [rsp+1F0h+lpReturnSize], rax; char *
0x1801c9666  lea     ecx, [rdx+9]; int
0x1801c9669  mov     [rsp+1F0h+lpPreviousValue], rax; char *
0x1801c966e  mov     [rsp+1F0h+cbSize], rax; char *
0x1801c9673  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c9678  jmp     loc_1801CA30C
0x1801c967d  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801c9684  jnz     short loc_1801C968F
0x1801c9686  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1801c968b  mov     [rsp+1F0h+var_186], al
0x1801c968f  test    dword ptr [rsi+8], 10000h
0x1801c9696  jz      short loc_1801C96A4
0x1801c9698  call    cs:__imp_DebugBreak
0x1801c969f  nop     dword ptr [rax+rax+00h]
0x1801c96a4  mov     rdx, cs:qword_180313738; struct CMsiEnvironmentBlock *
0x1801c96ab  lea     rcx, [rbp+0F0h+Environment]; Environment
0x1801c96af  test    rdx, rdx
0x1801c96b2  jz      short loc_1801C96D6
0x1801c96b4  call    ?InitializeFromSource@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z; CMsiEnvironmentBlock::InitializeFromSource(CMsiEnvironmentBlock *)
0x1801c96b9  test    al, al
0x1801c96bb  jnz     short loc_1801C96F8
0x1801c96bd  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c96c4  jz      loc_1801CA30C
0x1801c96ca  lea     r9, aErrorFailedToI; "ERROR: Failed to initialize impersonate"...
0x1801c96d1  jmp     loc_1801C9646
0x1801c96d6  call    ?InitializeFromProcessEnvironment@CMsiEnvironmentBlock@@QEAA_NXZ; CMsiEnvironmentBlock::InitializeFromProcessEnvironment(void)
0x1801c96db  test    al, al
0x1801c96dd  jnz     short loc_1801C96F8
0x1801c96df  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c96e6  jz      loc_1801CA30C
0x1801c96ec  lea     r9, aErrorFailedToI_2; "ERROR: Failed to initialize impersonate"...
0x1801c96f3  jmp     loc_1801C9646
0x1801c96f8  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801c96ff  call    ?GetSystemEnvironment@MsiUIMessageContext@@QEAAPEAVCMsiEnvironmentBlock@@XZ; MsiUIMessageContext::GetSystemEnvironment(void)
0x1801c9704  lea     rcx, [rbp+0F0h+var_140]; Environment
0x1801c9708  test    rax, rax
0x1801c970b  jz      short loc_1801C9732
0x1801c970d  mov     rdx, rax; struct CMsiEnvironmentBlock *
0x1801c9710  call    ?InitializeFromSource@CMsiEnvironmentBlock@@QEAA_NPEAV1@@Z; CMsiEnvironmentBlock::InitializeFromSource(CMsiEnvironmentBlock *)
0x1801c9715  test    al, al
0x1801c9717  jnz     short loc_1801C9754
0x1801c9719  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c9720  jz      loc_1801CA30C
0x1801c9726  lea     r9, aErrorFailedToI_1; "ERROR: Failed to initialize system cust"...
0x1801c972d  jmp     loc_1801C9646
0x1801c9732  call    ?InitializeFromProcessEnvironment@CMsiEnvironmentBlock@@QEAA_NXZ; CMsiEnvironmentBlock::InitializeFromProcessEnvironment(void)
0x1801c9737  test    al, al
0x1801c9739  jnz     short loc_1801C9754
0x1801c973b  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c9742  jz      loc_1801CA30C
0x1801c9748  lea     r9, aErrorFailedToI_0; "ERROR: Failed to initialize system cust"...
0x1801c974f  jmp     loc_1801C9646
0x1801c9754  cmp     [rsi+88h], r15b
0x1801c975b  jz      loc_1801C9992
0x1801c9761  mov     edx, 20Bh
0x1801c9766  lea     rcx, [rbp+0F0h+lpString]
0x1801c976a  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801c976f  mov     rcx, [rbp+0F0h+lpString]
0x1801c9773  test    rcx, rcx
0x1801c9776  jnz     short loc_1801C9786
0x1801c9778  lea     rcx, [rbp+0F0h+lpString]
0x1801c977c  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801c9781  jmp     loc_1801CA30C
0x1801c9786  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c9789  mov     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c978c  mov     [rcx], r15w
0x1801c9790  mov     rcx, [rsi]
0x1801c9793  mov     rdi, cs:?ApphelpFixMsiPackageExe@APPHELP@@3P6AHPEAU_GUID@@0PEBGPEAGPEAK@ZEA; int (*APPHELP::ApphelpFixMsiPackageExe)(_GUID *,_GUID *,ushort const *,ushort *,ulong *)
0x1801c979a  mov     rbx, [rbp+0F0h+lpString]
0x1801c979e  mov     rax, [rcx]
0x1801c97a1  mov     rax, [rax+50h]
0x1801c97a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c97aa  lea     rcx, [rbp+0F0h+TokenInformation]
0x1801c97ae  mov     r8, rax
0x1801c97b1  mov     [rsp+1F0h+cbSize], rcx
0x1801c97b6  lea     r14, [rsi+9Ch]
0x1801c97bd  lea     r15, [rsi+8Ch]
0x1801c97c4  mov     r9, rbx
0x1801c97c7  mov     rcx, r15
0x1801c97ca  mov     rdx, r14
0x1801c97cd  mov     rax, rdi
0x1801c97d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c97d5  xor     ebx, ebx
0x1801c97d7  test    eax, eax
0x1801c97d9  jz      loc_1801C985F
0x1801c97df  mov     edx, dword ptr [rbp+0F0h+TokenInformation]
0x1801c97e2  cmp     edx, dword ptr [rbp+0F0h+lpString+8]
0x1801c97e5  jbe     loc_1801C986C
0x1801c97eb  lea     rcx, [rbp+0F0h+lpString]
0x1801c97ef  call    ?SetSize@?$CTempBuffer@G$00@@QEAAXH@Z; CTempBuffer<ushort,1>::SetSize(int)
0x1801c97f4  mov     rcx, [rbp+0F0h+lpString]
0x1801c97f8  test    rcx, rcx
0x1801c97fb  jnz     short loc_1801C980E
0x1801c97fd  lea     rcx, [rbp+0F0h+lpString]
0x1801c9801  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801c9806  xor     r15d, r15d
0x1801c9809  jmp     loc_1801CA30F
0x1801c980e  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c9811  mov     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c9814  mov     [rcx], bx
0x1801c9817  mov     rcx, [rsi]
0x1801c981a  mov     rdi, cs:?ApphelpFixMsiPackageExe@APPHELP@@3P6AHPEAU_GUID@@0PEBGPEAGPEAK@ZEA; int (*APPHELP::ApphelpFixMsiPackageExe)(_GUID *,_GUID *,ushort const *,ushort *,ulong *)
0x1801c9821  mov     rbx, [rbp+0F0h+lpString]
0x1801c9825  mov     rax, [rcx]
0x1801c9828  mov     rax, [rax+50h]
0x1801c982c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9831  lea     rcx, [rbp+0F0h+TokenInformation]
0x1801c9835  mov     r8, rax
0x1801c9838  mov     [rsp+1F0h+cbSize], rcx
0x1801c983d  mov     r9, rbx
0x1801c9840  mov     rcx, r15
0x1801c9843  mov     rdx, r14
0x1801c9846  mov     rax, rdi
0x1801c9849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c984e  xor     r15d, r15d
0x1801c9851  test    eax, eax
0x1801c9853  jz      short loc_1801C9862
0x1801c9855  mov     eax, dword ptr [rbp+0F0h+lpString+8]
0x1801c9858  cmp     dword ptr [rbp+0F0h+TokenInformation], eax
0x1801c985b  jbe     short loc_1801C986F
0x1801c985d  jmp     short loc_1801C9862
0x1801c985f  xor     r15d, r15d
0x1801c9862  mov     rax, [rbp+0F0h+lpString]
0x1801c9866  mov     [rax], r15w
0x1801c986a  jmp     short loc_1801C986F
0x1801c986c  xor     r15d, r15d
0x1801c986f  mov     rcx, [rbp+0F0h+lpString]; lpString
0x1801c9873  call    cs:__imp_lstrlenW
0x1801c987a  nop     dword ptr [rax+rax+00h]
0x1801c987f  test    eax, eax
0x1801c9881  jz      loc_1801C9989
0x1801c9887  mov     rbx, [rbp+0F0h+lpString]
0x1801c988b  cmp     [rbx], r15w
0x1801c988f  jz      loc_1801C9989
0x1801c9895  mov     edx, 3Dh ; '='; Ch
0x1801c989a  mov     rcx, rbx; Str
0x1801c989d  call    cs:__imp_wcschr
0x1801c98a4  nop     dword ptr [rax+rax+00h]
0x1801c98a9  mov     rdi, rax
0x1801c98ac  test    rax, rax
0x1801c98af  jz      loc_1801C9989
0x1801c98b5  add     rdi, 2
0x1801c98b9  mov     [rax], r15w
0x1801c98bd  mov     r8, rdi; unsigned __int16 *
0x1801c98c0  lea     rcx, [rbp+0F0h+Environment]; this
0x1801c98c4  mov     rdx, rbx; unsigned __int16 *
0x1801c98c7  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c98cc  test    al, al
0x1801c98ce  jz      loc_1801C9964
0x1801c98d4  mov     r8, rdi; unsigned __int16 *
0x1801c98d7  lea     rcx, [rbp+0F0h+var_140]; this
0x1801c98db  mov     rdx, rbx; unsigned __int16 *
0x1801c98de  call    ?Set@CMsiEnvironmentBlock@@QEAA_NPEBG0@Z; CMsiEnvironmentBlock::Set(ushort const *,ushort const *)
0x1801c98e3  test    al, al
0x1801c98e5  jz      short loc_1801C9900
0x1801c98e7  mov     rbx, rdi
0x1801c98ea  cmp     [rdi], r15w
0x1801c98ee  jz      short loc_1801C98FA
0x1801c98f0  add     rbx, 2
0x1801c98f4  cmp     [rbx], r15w
0x1801c98f8  jnz     short loc_1801C98F0
0x1801c98fa  add     rbx, 2
0x1801c98fe  jmp     short loc_1801C988B
0x1801c9900  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c9907  jz      loc_1801C9778
0x1801c990d  mov     rcx, [rsi]
0x1801c9910  mov     rax, [rcx]
0x1801c9913  mov     rax, [rax+50h]
0x1801c9917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c991c  lea     r9, aErrorFailedToA_1; "ERROR: Failed to apply app compat flags"...
0x1801c9923  mov     [rsp+1F0h+var_198], r15; void *
0x1801c9928  lea     r14, aNull; "(NULL)"
0x1801c992f  mov     dword ptr [rsp+1F0h+lpProcessInformation], r15d; unsigned int
0x1801c9934  xor     edx, edx; unsigned __int16
0x1801c9936  mov     [rsp+1F0h+lpStartupInfo], r14; unsigned __int16 *
0x1801c993b  xor     r8d, r8d; int
0x1801c993e  mov     [rsp+1F0h+lpCurrentDirectory], r14; unsigned __int16 *
0x1801c9943  mov     [rsp+1F0h+lpEnvironment], r14; unsigned __int16 *
0x1801c9948  mov     [rsp+1F0h+lpReturnSize], r14; unsigned __int16 *
0x1801c994d  lea     ecx, [rdx+0Ah]; int
0x1801c9950  mov     [rsp+1F0h+lpPreviousValue], r14; unsigned __int16 *
0x1801c9955  mov     [rsp+1F0h+cbSize], rax; unsigned __int16 *
0x1801c995a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801c995f  jmp     loc_1801C9778
0x1801c9964  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1801c996b  jz      loc_1801C9778
0x1801c9971  mov     rcx, [rsi]
  ... truncated ...
```
