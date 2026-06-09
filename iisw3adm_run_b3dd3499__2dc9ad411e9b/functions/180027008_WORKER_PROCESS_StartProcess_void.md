# WORKER_PROCESS::StartProcess(void)

- ea: `0x180027008`
- end: `0x180027be8`
- name: `?StartProcess@WORKER_PROCESS@@AEAAJXZ`
- size: `3040`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023c8c`

## callees

- `0x180005878`
- `0x1800168f8`
- `0x18002254c`
- `0x180025540`
- `0x180026764`
- `0x180027008`
- `0x18005f32c`
- `0x18006101a`
- `0x180061032`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002756e`
- `msvcrt!wcschr` at `0x18002756e`
- `msvcrt!wcsrchr` at `0x1800273f2`
- `msvcrt!wcsrchr` at `0x1800273f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002785f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002785f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027af0`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180027b5a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180027b5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180027852`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180027852`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180027add`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180027add`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800279dc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800279dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800276f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800276f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027a44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027a44`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180027a91`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x180027a91`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800274fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800274fe`
- `api-ms-win-core-processtopology-private-l1-1-0!SetProcessGroupAffinity` at `0x180027901`
- `api-ms-win-core-processtopology-private-l1-1-0!SetProcessGroupAffinity` at `0x180027901`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027b89`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027b96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027ba3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027bb0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027bbd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027b89`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027b96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027ba3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027bb0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027bbd`
- `iisutil!PuDbgPrint` at `0x180027389`
- `iisutil!PuDbgPrint` at `0x180027628`
- `iisutil!PuDbgPrint` at `0x1800278ce`
- `iisutil!PuDbgPrint` at `0x180027389`
- `iisutil!PuDbgPrint` at `0x180027628`
- `iisutil!PuDbgPrint` at `0x1800278ce`
- `iisutil!PuDbgPrintError` at `0x1800272c9`
- `iisutil!PuDbgPrintError` at `0x180027958`
- `iisutil!PuDbgPrintError` at `0x180027a30`
- `iisutil!PuDbgPrintError` at `0x180027b2d`
- `iisutil!PuDbgPrintError` at `0x1800272c9`
- `iisutil!PuDbgPrintError` at `0x180027958`
- `iisutil!PuDbgPrintError` at `0x180027a30`
- `iisutil!PuDbgPrintError` at `0x180027b2d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027064`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027071`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002707e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002708b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800270b5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027064`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027071`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002707e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002708b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800270b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027166`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027166`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027184`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271a2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271c0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271de`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027200`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002721e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027184`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271a2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271c0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800271de`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027200`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002721e`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x1800279bc`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x1800279bc`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800270ec`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800270ec`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180027b48`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180027b48`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180027596`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180027596`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18002752c`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18002752c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180027311`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180027311`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18002763a`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18002763a`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18002732f`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18002732f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002723f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002723f`
- `USERENV!CreateEnvironmentBlock` at `0x18002748c`
- `USERENV!CreateEnvironmentBlock` at `0x18002748c`
- `USERENV!LoadUserProfileW` at `0x180027441`
- `USERENV!LoadUserProfileW` at `0x180027441`
- `USERENV!DestroyEnvironmentBlock` at `0x180027aa1`
- `USERENV!DestroyEnvironmentBlock` at `0x180027aa1`
- `USERENV!UnloadUserProfile` at `0x180027a78`
- `USERENV!UnloadUserProfile` at `0x180027a78`

## string_xrefs

- `0x1800279b5`: `System\CurrentControlSet\Services\WAS\Parameters`
- `0x1800272be`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002736b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180027621`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x1800278a5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180027951`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180027a29`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180027b22`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002729e`: `Creating command line failed\n`
- `0x18002737d`: `Launching worker process with command line of %S\n`
- `0x18002740c`: `NT AUTHORITY\NetworkService`
- `0x180027403`: `NT AUTHORITY\LocalService`
- `0x180027603`: `EnvironmentVariable %S not appended to worker process environment because it is defined in the AppPool config.\n`
- `0x1800278bd`: `New worker process created (ptr: %p; pid: %lu; realpid: %lu)\n`
- `0x1800279ae`: `ApplyThreadAffinityOnWebGarden`
- `0x180027a0c`: `Could not resume thread\n`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::StartProcess(WORKER_PROCESS *this)
{
  unsigned __int16 *v1; // rbx
  const WCHAR *v2; // r13
  struct _STARTUPINFOW *p_StartupInfo; // rax
  WCHAR *v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct _PROCESS_INFORMATION *p_ProcessInformation; // rax
  __int64 v8; // rcx
  struct _SECURITY_ATTRIBUTES *p_SecurityDescriptor; // rax
  int CommandLine; // edi
  signed int v11; // eax
  const char *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  WCHAR *v19; // rcx
  wchar_t *v20; // rax
  WCHAR *v21; // rax
  TOKEN_CACHE_ENTRY *v22; // rcx
  void *PrimaryToken; // rax
  __int64 v24; // rax
  TOKEN_CACHE_ENTRY *v25; // rcx
  void *v26; // rax
  signed int LastError; // eax
  __int64 v28; // rcx
  const wchar_t *v29; // rsi
  __int64 v30; // rax
  const wchar_t *v31; // r13
  wchar_t *v32; // r14
  int v33; // r12d
  const wchar_t *v34; // r15
  __int64 v35; // r14
  __int64 v36; // rax
  bool v37; // zf
  DWORD dwCreationFlags; // esi
  WEB_ADMIN_SERVICE *v39; // r14
  char *v40; // r15
  __int64 v41; // rcx
  DWORD_PTR dwActiveProcessorMask; // rax
  __int64 v43; // r12
  __int64 v44; // rax
  unsigned int v45; // edx
  WORKER_PROCESS *v46; // rcx
  void *lpEnvironment; // r14
  WCHAR *v48; // r12
  TOKEN_CACHE_ENTRY *v49; // rcx
  void *v50; // rax
  signed int v51; // eax
  HANDLE hProcess; // rcx
  signed int v53; // eax
  __int64 v54; // rax
  signed int v55; // eax
  HANDLE hProfile; // rdx
  TOKEN_CACHE_ENTRY *v57; // rcx
  void *v58; // rax
  HANDLE v59; // rcx
  signed int v60; // eax
  LPPROC_THREAD_ATTRIBUTE_LIST v61; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *EnvironmentStringsW; // [rsp+60h] [rbp-A0h]
  LPVOID Environment; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v66; // [rsp+70h] [rbp-90h] BYREF
  int v67; // [rsp+78h] [rbp-88h]
  LPCWSTR lpCurrentDirectory; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+D8h] [rbp-28h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+F0h] [rbp-10h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp+20h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v74; // [rsp+188h] [rbp+88h]
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+190h] [rbp+90h] BYREF
  __int128 v76; // [rsp+198h] [rbp+98h] BYREF
  __int16 v77; // [rsp+1A8h] [rbp+A8h] BYREF
  int v78; // [rsp+1ACh] [rbp+ACh]
  _BYTE v79[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+1D0h] [rbp+D0h]
  _BYTE v81[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  WCHAR *v82; // [rsp+208h] [rbp+108h]
  int v83; // [rsp+218h] [rbp+118h]
  _BYTE v84[32]; // [rsp+220h] [rbp+120h] BYREF
  _WORD *v85; // [rsp+240h] [rbp+140h]
  _BYTE v86[32]; // [rsp+258h] [rbp+158h] BYREF
  LPWSTR lpCommandLine; // [rsp+278h] [rbp+178h]
  _BYTE v88[32]; // [rsp+290h] [rbp+190h] BYREF
  const WCHAR *v89; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v90[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  LPCWSTR lpApplicationName; // [rsp+2E8h] [rbp+1E8h]

  v1 = (unsigned __int16 *)this;
  v66 = (unsigned __int16 *)this;
  memset_0(&StartupInfo, 0, 0x70u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  STRU::STRU((STRU *)v90);
  STRU::STRU((STRU *)v86);
  STRU::STRU((STRU *)v88);
  STRU::STRU((STRU *)v81);
  v2 = 0;
  Environment = 0;
  STRU::STRU((STRU *)v79);
  v78 &= 0xFFFFFFFC;
  lpAttributeList = 0;
  v77 = 0;
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v76 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v84);
  EnvironmentStringsW = 0;
  v67 = 0;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  ProfileInfo.dwSize = 56;
  p_StartupInfo = &StartupInfo;
  v4 = 0;
  v5 = 112;
  do
  {
    LOBYTE(p_StartupInfo->cb) = 0;
    p_StartupInfo = (struct _STARTUPINFOW *)((char *)p_StartupInfo + 1);
    --v5;
  }
  while ( v5 );
  StartupInfo.cb = 112;
  v6 = 24;
  p_ProcessInformation = &ProcessInformation;
  do
  {
    LOBYTE(p_ProcessInformation->hProcess) = 0;
    p_ProcessInformation = (struct _PROCESS_INFORMATION *)((char *)p_ProcessInformation + 1);
    --v6;
  }
  while ( v6 );
  v8 = 24;
  p_SecurityDescriptor = &SecurityDescriptor;
  do
  {
    LOBYTE(p_SecurityDescriptor->nLength) = 0;
    p_SecurityDescriptor = (struct _SECURITY_ATTRIBUTES *)((char *)p_SecurityDescriptor + 1);
    --v8;
  }
  while ( v8 );
  CommandLine = STRU::Copy((STRU *)v79, L"D:P");
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, L"(A;OICI;GA;;;SY)");
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, L"(A;OICI;GA;;;BA)");
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, L"(A;OICI;RC;;;OW)");
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, L"(A;OICI;GA;;;");
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, *(const unsigned __int16 **)(*((_QWORD *)v1 + 8) + 192LL));
  if ( CommandLine < 0 )
    goto LABEL_125;
  CommandLine = STRU::Append((STRU *)v79, L")");
  if ( CommandLine < 0 )
    goto LABEL_125;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          &SecurityDescriptor.lpSecurityDescriptor,
          0) )
    goto LABEL_15;
  SecurityDescriptor.nLength = 24;
  SecurityDescriptor.bInheritHandle = 0;
  CommandLine = WORKER_PROCESS::CreateCommandLine(
                  (WORKER_PROCESS *)v1,
                  (struct STRU *)v90,
                  (struct STRU *)v86,
                  (struct STRU *)v88);
  if ( CommandLine < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_125;
    v12 = "Creating command line failed\n";
    v13 = 3817;
    goto LABEL_20;
  }
  CommandLine = WORKER_PROCESS::ReadDebuggerCmd((WORKER_PROCESS *)v1, (struct STRU *)v81);
  if ( CommandLine < 0 )
  {
    *((_DWORD *)v1 + 116) = 1;
    goto LABEL_125;
  }
  if ( !v83
    || (*((_DWORD *)v1 + 116) = 1, CommandLine = STRU::Append((STRU *)v81, 0x20u), CommandLine >= 0)
    && (CommandLine = STRU::Append((STRU *)v81, (const struct STRU *)v86), CommandLine >= 0) )
  {
    if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        3861,
        "WORKER_PROCESS::StartProcess",
        "Launching worker process with command line of %S\n",
        lpCommandLine);
    v14 = *((_QWORD *)v1 + 8);
    if ( !*(_DWORD *)(v14 + 580) )
      goto LABEL_56;
    ProfileInfo.dwSize = 56;
    ProfileInfo.dwFlags = 1;
    v15 = *(_DWORD *)(v14 + 652);
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 == 1 )
              ProfileInfo.lpUserName = *(LPWSTR *)(*((_QWORD *)v1 + 7) + 56LL);
            goto LABEL_43;
          }
          v19 = (WCHAR *)&SourceString;
          if ( *(_QWORD *)(v14 + 656) )
            v19 = *(WCHAR **)(v14 + 656);
          ProfileInfo.lpUserName = v19;
          v20 = wcsrchr(v19, 0x5Cu);
          if ( !v20 )
            goto LABEL_43;
          v21 = v20 + 1;
        }
        else
        {
          v21 = (WCHAR *)L"NT AUTHORITY\\LocalService";
        }
      }
      else
      {
        v21 = L"NT AUTHORITY\\NetworkService";
      }
    }
    else
    {
      v21 = (WCHAR *)L"NT AUTHORITY\\System";
    }
    ProfileInfo.lpUserName = v21;
LABEL_43:
    v22 = *(TOKEN_CACHE_ENTRY **)(*((_QWORD *)v1 + 8) + 184LL);
    if ( v22 )
      PrimaryToken = TOKEN_CACHE_ENTRY::QueryPrimaryToken(v22);
    else
      PrimaryToken = 0;
    if ( !LoadUserProfileW(PrimaryToken, &ProfileInfo) )
      goto LABEL_15;
    *((_QWORD *)v1 + 56) = ProfileInfo.hProfile;
    v24 = *((_QWORD *)v1 + 8);
    ProfileInfo.hProfile = 0;
    if ( *(_DWORD *)(v24 + 584) )
    {
      v25 = *(TOKEN_CACHE_ENTRY **)(v24 + 184);
      v26 = v25 ? TOKEN_CACHE_ENTRY::QueryPrimaryToken(v25) : 0LL;
      if ( !CreateEnvironmentBlock(&Environment, v26, 1) )
      {
        LastError = GetLastError();
        CommandLine = LastError;
        if ( LastError > 0 )
          CommandLine = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v12 = "Creating environment block failed\n";
          v13 = 3964;
LABEL_20:
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            v13,
            "WORKER_PROCESS::StartProcess",
            CommandLine,
            v12);
          goto LABEL_125;
        }
        goto LABEL_125;
      }
    }
LABEL_56:
    v28 = *((_QWORD *)v1 + 8);
    if ( v28 == -592 || !**(_WORD **)(v28 + 624) )
      goto LABEL_81;
    v4 = (WCHAR *)Environment;
    EnvironmentStringsW = (WCHAR *)Environment;
    if ( Environment )
    {
LABEL_61:
      if ( !MULTISZ::Copy((MULTISZ *)v84, (const struct MULTISZ *)(*((_QWORD *)v1 + 8) + 592LL)) )
      {
        CommandLine = -2147024882;
        goto LABEL_125;
      }
      v29 = v4;
      if ( *v4 )
      {
        do
        {
          v30 = -1;
          do
            ++v30;
          while ( v29[v30] );
          v31 = &v29[v30];
          v32 = wcschr(v29, 0x3Du);
          if ( v32 && *v32 == 61 )
          {
            v33 = 0;
            v34 = MULTISZ::First((MULTISZ *)v84);
            if ( !v34 )
              goto LABEL_78;
            v35 = v32 - v29;
            do
            {
              if ( !wcsncmp_0(v34, v29, (unsigned int)v35) )
                v33 = 1;
              v36 = -1;
              do
                ++v36;
              while ( v34[v36] );
              v34 += v36 + 1;
            }
            while ( *v34 );
            if ( v33 )
            {
              if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
                  4056,
                  "WORKER_PROCESS::StartProcess",
                  "EnvironmentVariable %S not appended to worker process environment because it is defined in the AppPool config.\n",
                  v29);
            }
            else
            {
LABEL_78:
              MULTISZ::FastAppend((MULTISZ *)v84, v29);
            }
          }
          v37 = v31[1] == 0;
          v29 = v31 + 1;
          v2 = 0;
        }
        while ( !v37 );
        v1 = v66;
      }
LABEL_81:
      if ( Environment || (dwCreationFlags = 12, *v85) )
        dwCreationFlags = 1036;
      v39 = g_pWebAdminService;
      v40 = (char *)g_pWebAdminService + 632;
      if ( *((_WORD *)g_pWebAdminService + 332) > 1u || *((_DWORD *)g_pWebAdminService + 167) > 1u )
      {
        v44 = *((_QWORD *)v1 + 7);
        CommandLine = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, char *, LPPROC_THREAD_ATTRIBUTE_LIST *))(**(_QWORD **)(v44 + 512) + 8LL))(
                        *(_QWORD *)(v44 + 512),
                        *(unsigned int *)(*(_QWORD *)(v44 + 88) + 240LL),
                        *(unsigned int *)(*((_QWORD *)v1 + 8) + 224LL),
                        *(_QWORD *)(*(_QWORD *)(v44 + 88) + 232LL),
                        *(_DWORD *)(*(_QWORD *)(v44 + 88) + 244LL),
                        (char *)g_pWebAdminService + 632,
                        &lpAttributeList);
        if ( CommandLine < 0 )
          goto LABEL_124;
        if ( (v78 & 2) != 0 )
        {
          lpCurrentDirectory = (LPCWSTR)131076;
          v66 = (unsigned __int16 *)&v77;
          CommandLine = WORKER_PROCESS::SetProcessThreadAttribute(
                          v46,
                          v45,
                          (unsigned __int64 *const)&lpCurrentDirectory,
                          &v66,
                          &lpAttributeList);
          if ( CommandLine < 0 )
            goto LABEL_124;
          dwCreationFlags |= 0x80000u;
          v74 = lpAttributeList;
        }
      }
      else
      {
        v41 = *((_QWORD *)v1 + 8);
        if ( *(_DWORD *)(v41 + 224) && *(_QWORD *)(v41 + 232) != -1 )
        {
          v78 |= 1u;
          WORD4(v76) = 0;
          dwActiveProcessorMask = *((_QWORD *)g_pWebAdminService + 200);
          v43 = *(_QWORD *)(v41 + 232);
          if ( !dwActiveProcessorMask )
          {
            memset(&SystemInfo, 0, sizeof(SystemInfo));
            GetSystemInfo(&SystemInfo);
            dwActiveProcessorMask = SystemInfo.dwActiveProcessorMask;
            *((_QWORD *)v39 + 200) = SystemInfo.dwActiveProcessorMask;
          }
          *(_QWORD *)&v76 = v43 & dwActiveProcessorMask;
        }
      }
      lpEnvironment = v85;
      lpCurrentDirectory = v89;
      if ( !*v85 )
        lpEnvironment = Environment;
      if ( v83 )
      {
        v48 = v82;
      }
      else
      {
        v48 = lpCommandLine;
        v2 = lpApplicationName;
      }
      v49 = *(TOKEN_CACHE_ENTRY **)(*((_QWORD *)v1 + 8) + 184LL);
      if ( v49 )
        v50 = TOKEN_CACHE_ENTRY::QueryPrimaryToken(v49);
      else
        v50 = 0;
      if ( CreateProcessAsUserW(
             v50,
             v2,
             v48,
             &SecurityDescriptor,
             0,
             0,
             dwCreationFlags,
             lpEnvironment,
             lpCurrentDirectory,
             &StartupInfo,
             &ProcessInformation) )
      {
        if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            4213,
            "WORKER_PROCESS::StartProcess",
            "New worker process created (ptr: %p; pid: %lu; realpid: %lu)\n",
            v1,
            *((_DWORD *)v1 + 18),
            *((_DWORD *)v1 + 19));
        hProcess = ProcessInformation.hProcess;
        *((_DWORD *)v1 + 18) = ProcessInformation.dwProcessId;
        *((_QWORD *)v1 + 10) = hProcess;
        *((_DWORD *)v1 + 26) = 1;
        if ( (v78 & 1) != 0 )
        {
          if ( !(unsigned int)SetProcessGroupAffinity(hProcess, &v76, 0) )
          {
            v53 = GetLastError();
            CommandLine = v53;
            if ( v53 > 0 )
              CommandLine = (unsigned __int16)v53 | 0x80070000;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
                4238,
                "WORKER_PROCESS::StartProcess",
                CommandLine,
                "Could not set process affinity mask\n");
            v54 = *((_QWORD *)v1 + 7);
            v66 = 0;
            v66 = *(unsigned __int16 **)(v54 + 56);
            WEB_ADMIN_SERVICE::LogEvent(
              g_pWebAdminService,
              0x800013C2,
              1u,
              (const unsigned __int16 **const)&v66,
              CommandLine);
            *((_DWORD *)v1 + 54) = 1;
            goto LABEL_124;
          }
        }
        else if ( *((_WORD *)v40 + 16) > 1u
               && (*(_DWORD *)(*((_QWORD *)v1 + 8) + 220LL) == 1
                || ReadDwordParameterValueFromAnyService(
                     L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
                     L"ApplyThreadAffinityOnWebGarden",
                     1u)) )
        {
          *((_DWORD *)v1 + 117) = 1;
        }
        APP_POOL::AddWorkerProcessToJobObject(*((APP_POOL **)v1 + 7), (struct WORKER_PROCESS *)v1);
        if ( ResumeThread(ProcessInformation.hThread) == -1 )
        {
          v55 = GetLastError();
          CommandLine = v55;
          if ( v55 > 0 )
            CommandLine = (unsigned __int16)v55 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
              4298,
              "WORKER_PROCESS::StartProcess",
              CommandLine,
              "Could not resume thread\n");
        }
        goto LABEL_124;
      }
      v51 = GetLastError();
      CommandLine = v51;
      if ( v51 > 0 )
        CommandLine = (unsigned __int16)v51 | 0x80070000;
LABEL_124:
      v4 = EnvironmentStringsW;
      goto LABEL_125;
    }
    EnvironmentStringsW = GetEnvironmentStringsW();
    v4 = EnvironmentStringsW;
    if ( EnvironmentStringsW )
    {
      v67 = 1;
      goto LABEL_61;
    }
LABEL_15:
    v11 = GetLastError();
    CommandLine = v11;
    if ( v11 > 0 )
      CommandLine = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_125:
  if ( SecurityDescriptor.lpSecurityDescriptor )
  {
    LocalFree(SecurityDescriptor.lpSecurityDescriptor);
    SecurityDescriptor.lpSecurityDescriptor = 0;
  }
  hProfile = ProfileInfo.hProfile;
  if ( ProfileInfo.hProfile )
  {
    v57 = *(TOKEN_CACHE_ENTRY **)(*((_QWORD *)v1 + 8) + 184LL);
    if ( v57 )
    {
      v58 = TOKEN_CACHE_ENTRY::QueryPrimaryToken(v57);
      hProfile = ProfileInfo.hProfile;
    }
    else
    {
      v58 = 0;
    }
    UnloadUserProfile(v58, hProfile);
    ProfileInfo.hProfile = 0;
  }
  if ( v67 && v4 )
    FreeEnvironmentStringsW(v4);
  if ( Environment )
  {
    DestroyEnvironmentBlock(Environment);
    Environment = 0;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  if ( CommandLine < 0 )
  {
    v59 = ProcessInformation.hProcess;
    if ( ProcessInformation.hProcess )
    {
      *((_DWORD *)v1 + 18) = 0;
      *((_QWORD *)v1 + 10) = 0;
      *((_DWORD *)v1 + 26) = 0;
      if ( !TerminateProcess(v59, 0xFFFFFFFD) && (g_dwDebugFlags & 0xF) != 0 )
      {
        v60 = GetLastError();
        if ( v60 > 0 )
          v60 = (unsigned __int16)v60 | 0x80070000;
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          4375,
          "WORKER_PROCESS::StartProcess",
          v60,
          "Terminating process failed\n");
      }
      CloseHandle(ProcessInformation.hProcess);
      ProcessInformation.hProcess = 0;
    }
  }
  MULTISZ::~MULTISZ((MULTISZ *)v84);
  if ( lpAttributeList )
  {
    DeleteProcThreadAttributeList(lpAttributeList);
    v61 = lpAttributeList;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v61);
    lpAttributeList = 0;
  }
  STRU::~STRU((STRU *)v79);
  STRU::~STRU((STRU *)v81);
  STRU::~STRU((STRU *)v88);
  STRU::~STRU((STRU *)v86);
  STRU::~STRU((STRU *)v90);
  return (unsigned int)CommandLine;
}

```

## disassembly

```asm
0x180027008  push    rbp
0x18002700a  push    rbx
0x18002700b  push    rsi
0x18002700c  push    rdi
0x18002700d  push    r12
0x18002700f  push    r13
0x180027011  push    r14
0x180027013  push    r15
0x180027015  lea     rbp, [rsp-218h]
0x18002701d  sub     rsp, 318h
0x180027024  mov     rax, cs:__security_cookie
0x18002702b  xor     rax, rsp
0x18002702e  mov     [rbp+250h+var_50], rax
0x180027035  mov     rbx, rcx
0x180027038  mov     [rsp+350h+var_2E0], rcx
0x18002703d  mov     edi, 70h ; 'p'
0x180027042  lea     rcx, [rbp+250h+StartupInfo]; void *
0x180027046  mov     r8d, edi; Size
0x180027049  xor     edx, edx; Val
0x18002704b  call    memset_0
0x180027050  xorps   xmm0, xmm0
0x180027053  lea     rcx, [rbp+250h+var_88]
0x18002705a  xor     eax, eax
0x18002705c  movups  xmmword ptr [rbp+250h+ProcessInformation.hProcess], xmm0
0x180027060  mov     qword ptr [rbp+250h+ProcessInformation.dwProcessId], rax
0x180027064  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002706a  lea     rcx, [rbp+250h+var_F8]
0x180027071  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027077  lea     rcx, [rbp+250h+var_C0]
0x18002707e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027084  lea     rcx, [rbp+250h+var_168]
0x18002708b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027091  xorps   xmm0, xmm0
0x180027094  lea     rcx, [rbp+250h+var_1A0]
0x18002709b  xor     eax, eax
0x18002709d  xor     r13d, r13d
0x1800270a0  movups  xmmword ptr [rbp+250h+ProfileInfo.dwSize], xmm0
0x1800270a4  mov     [rbp+250h+ProfileInfo.hProfile], rax
0x1800270a8  movups  xmmword ptr [rbp+250h+ProfileInfo.lpProfilePath], xmm0
0x1800270ac  mov     [rsp+350h+Environment], r13
0x1800270b1  movups  xmmword ptr [rbp+250h+ProfileInfo.lpServerName], xmm0
0x1800270b5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800270bb  and     [rbp+250h+var_1A4], 0FFFFFFFCh
0x1800270c2  lea     rcx, [rbp+250h+var_130]
0x1800270c9  xorps   xmm0, xmm0
0x1800270cc  mov     [rbp+250h+lpAttributeList], r13
0x1800270d3  xor     eax, eax
0x1800270d5  mov     [rbp+250h+var_1A8], r13w
0x1800270dd  movups  xmmword ptr [rbp+250h+SecurityDescriptor], xmm0
0x1800270e1  mov     [rbp+250h+var_268], rax
0x1800270e5  movups  [rbp+250h+var_1B8], xmm0
0x1800270ec  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800270f2  xorps   xmm0, xmm0
0x1800270f5  mov     [rsp+350h+var_2F0], r13
0x1800270fa  lea     r15d, [rdi-38h]
0x1800270fe  mov     [rsp+350h+var_2D8], r13d
0x180027103  movups  xmmword ptr [rbp+250h+ProfileInfo.dwSize], xmm0
0x180027107  mov     [rbp+250h+ProfileInfo.dwSize], r15d
0x18002710b  lea     rax, [rbp+250h+StartupInfo]
0x18002710f  mov     r14d, r13d
0x180027112  mov     [rbp+250h+ProfileInfo.hProfile], r13
0x180027116  movups  xmmword ptr [rbp+250h+ProfileInfo.lpProfilePath], xmm0
0x18002711a  mov     ecx, edi
0x18002711c  lea     r12d, [rdi-6Fh]
0x180027120  movups  xmmword ptr [rbp+250h+ProfileInfo.lpServerName], xmm0
0x180027124  mov     [rax], r13b
0x180027127  add     rax, r12
0x18002712a  sub     rcx, r12
0x18002712d  jnz     short loc_180027124
0x18002712f  lea     esi, [rcx+18h]
0x180027132  mov     [rbp+250h+StartupInfo.cb], edi
0x180027135  mov     ecx, esi
0x180027137  lea     rax, [rbp+250h+ProcessInformation]
0x18002713b  mov     [rax], r13b
0x18002713e  add     rax, r12
0x180027141  sub     rcx, r12
0x180027144  jnz     short loc_18002713B
0x180027146  mov     rcx, rsi
0x180027149  lea     rax, [rbp+250h+SecurityDescriptor]
0x18002714d  mov     [rax], r13b
0x180027150  add     rax, r12
0x180027153  sub     rcx, r12
0x180027156  jnz     short loc_18002714D
0x180027158  lea     rdx, aDP; "D:P"
0x18002715f  lea     rcx, [rbp+250h+var_1A0]
0x180027166  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002716c  mov     edi, eax
0x18002716e  test    eax, eax
0x180027170  js      loc_180027A3B
0x180027176  lea     rdx, aAOiciGaSy; "(A;OICI;GA;;;SY)"
0x18002717d  lea     rcx, [rbp+250h+var_1A0]
0x180027184  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002718a  mov     edi, eax
0x18002718c  test    eax, eax
0x18002718e  js      loc_180027A3B
0x180027194  lea     rdx, aAOiciGaBa; "(A;OICI;GA;;;BA)"
0x18002719b  lea     rcx, [rbp+250h+var_1A0]
0x1800271a2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800271a8  mov     edi, eax
0x1800271aa  test    eax, eax
0x1800271ac  js      loc_180027A3B
0x1800271b2  lea     rdx, aAOiciRcOw; "(A;OICI;RC;;;OW)"
0x1800271b9  lea     rcx, [rbp+250h+var_1A0]
0x1800271c0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800271c6  mov     edi, eax
0x1800271c8  test    eax, eax
0x1800271ca  js      loc_180027A3B
0x1800271d0  lea     rdx, aAOiciGa; "(A;OICI;GA;;;"
0x1800271d7  lea     rcx, [rbp+250h+var_1A0]
0x1800271de  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800271e4  mov     edi, eax
0x1800271e6  test    eax, eax
0x1800271e8  js      loc_180027A3B
0x1800271ee  mov     rdx, [rbx+40h]
0x1800271f2  lea     rcx, [rbp+250h+var_1A0]
0x1800271f9  mov     rdx, [rdx+0C0h]
0x180027200  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180027206  mov     edi, eax
0x180027208  test    eax, eax
0x18002720a  js      loc_180027A3B
0x180027210  lea     rdx, asc_180067C58; ")"
0x180027217  lea     rcx, [rbp+250h+var_1A0]
0x18002721e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180027224  mov     edi, eax
0x180027226  test    eax, eax
0x180027228  js      loc_180027A3B
0x18002722e  mov     rcx, [rbp+250h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180027235  lea     r8, [rbp+250h+SecurityDescriptor+8]; SecurityDescriptor
0x180027239  xor     r9d, r9d; SecurityDescriptorSize
0x18002723c  mov     edx, r12d; StringSDRevision
0x18002723f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180027245  test    eax, eax
0x180027247  jnz     short loc_180027267
0x180027249  call    cs:__imp_GetLastError
0x18002724f  mov     edi, eax
0x180027251  test    eax, eax
0x180027253  jle     loc_180027A3B
0x180027259  movzx   edi, ax
0x18002725c  or      edi, 80070000h
0x180027262  jmp     loc_180027A3B
0x180027267  lea     r9, [rbp+250h+var_C0]; struct STRU *
0x18002726e  mov     dword ptr [rbp+250h+SecurityDescriptor], esi
0x180027271  lea     r8, [rbp+250h+var_F8]; struct STRU *
0x180027278  mov     dword ptr [rbp+250h+var_268], r13d
0x18002727c  lea     rdx, [rbp+250h+var_88]; struct STRU *
0x180027283  mov     rcx, rbx; this
0x180027286  call    ?CreateCommandLine@WORKER_PROCESS@@AEAAJPEAVSTRU@@00@Z; WORKER_PROCESS::CreateCommandLine(STRU *,STRU *,STRU *)
0x18002728b  mov     edi, eax
0x18002728d  test    eax, eax
0x18002728f  jns     short loc_1800272D4
0x180027291  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180027298  jz      loc_180027A3B
0x18002729e  lea     rax, aCreatingComman; "Creating command line failed\n"
0x1800272a5  mov     r8d, 0EE9h
0x1800272ab  mov     rcx, cs:g_pDebug
0x1800272b2  lea     r9, aWorkerProcessS_5; "WORKER_PROCESS::StartProcess"
0x1800272b9  mov     qword ptr [rsp+350h+bInheritHandles], rax
0x1800272be  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800272c5  mov     dword ptr [rsp+350h+lpThreadAttributes], edi
0x1800272c9  call    cs:__imp_PuDbgPrintError
0x1800272cf  jmp     loc_180027A3B
0x1800272d4  lea     rdx, [rbp+250h+var_168]; struct STRU *
0x1800272db  mov     rcx, rbx; this
0x1800272de  call    ?ReadDebuggerCmd@WORKER_PROCESS@@AEAAJPEAVSTRU@@@Z; WORKER_PROCESS::ReadDebuggerCmd(STRU *)
0x1800272e3  mov     edi, eax
0x1800272e5  test    eax, eax
0x1800272e7  jns     short loc_1800272F5
0x1800272e9  mov     [rbx+1D0h], r12d
0x1800272f0  jmp     loc_180027A3B
0x1800272f5  cmp     [rbp+250h+var_138], r13d
0x1800272fc  jz      short loc_18002733F
0x1800272fe  mov     edx, 20h ; ' '
0x180027303  mov     [rbx+1D0h], r12d
0x18002730a  lea     rcx, [rbp+250h+var_168]
0x180027311  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180027317  mov     edi, eax
0x180027319  test    eax, eax
0x18002731b  js      loc_180027A3B
0x180027321  lea     rdx, [rbp+250h+var_F8]
0x180027328  lea     rcx, [rbp+250h+var_168]
0x18002732f  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180027335  mov     edi, eax
0x180027337  test    eax, eax
0x180027339  js      loc_180027A3B
0x18002733f  mov     eax, cs:g_dwDebugFlags
0x180027345  test    eax, 410000h
0x18002734a  setnz   cl
0x18002734d  test    al, 3
0x18002734f  setnz   al
0x180027352  test    al, cl
0x180027354  jz      short loc_18002738F
0x180027356  mov     rax, [rbp+250h+lpCommandLine]
0x18002735d  lea     r9, aWorkerProcessS_5; "WORKER_PROCESS::StartProcess"
0x180027364  mov     rcx, cs:g_pDebug
0x18002736b  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027372  mov     qword ptr [rsp+350h+bInheritHandles], rax
0x180027377  mov     r8d, 0F15h
0x18002737d  lea     rax, aLaunchingWorke; "Launching worker process with command l"...
0x180027384  mov     [rsp+350h+lpThreadAttributes], rax
0x180027389  call    cs:__imp_PuDbgPrint
0x18002738f  mov     rdx, [rbx+40h]
0x180027393  cmp     [rdx+244h], r13d
0x18002739a  jz      loc_1800274CA
0x1800273a0  mov     [rbp+250h+ProfileInfo.dwSize], r15d
0x1800273a4  mov     [rbp+250h+ProfileInfo.dwFlags], r12d
0x1800273a8  mov     ecx, [rdx+28Ch]
0x1800273ae  test    ecx, ecx
0x1800273b0  jz      short loc_180027415
0x1800273b2  sub     ecx, r12d
0x1800273b5  jz      short loc_18002740C
0x1800273b7  sub     ecx, r12d
0x1800273ba  jz      short loc_180027403
0x1800273bc  sub     ecx, r12d
0x1800273bf  jz      short loc_1800273D4
0x1800273c1  cmp     ecx, r12d
0x1800273c4  jnz     short loc_180027420
0x1800273c6  mov     rax, [rbx+38h]
0x1800273ca  mov     rcx, [rax+38h]
0x1800273ce  mov     [rbp+250h+ProfileInfo.lpUserName], rcx
0x1800273d2  jmp     short loc_180027420
0x1800273d4  mov     rax, [rdx+290h]
0x1800273db  lea     rcx, SourceString
0x1800273e2  test    rax, rax
0x1800273e5  mov     edx, 5Ch ; '\'; Ch
0x1800273ea  cmovnz  rcx, rax; Str
0x1800273ee  mov     [rbp+250h+ProfileInfo.lpUserName], rcx
0x1800273f2  call    cs:__imp_wcsrchr
0x1800273f8  test    rax, rax
0x1800273fb  jz      short loc_180027420
0x1800273fd  add     rax, 2
0x180027401  jmp     short loc_18002741C
0x180027403  lea     rax, aNtAuthorityLoc; "NT AUTHORITY\\LocalService"
0x18002740a  jmp     short loc_18002741C
0x18002740c  lea     rax, aNtAuthorityNet; "NT AUTHORITY\\NetworkService"
0x180027413  jmp     short loc_18002741C
0x180027415  lea     rax, aNtAuthoritySys; "NT AUTHORITY\\System"
0x18002741c  mov     [rbp+250h+ProfileInfo.lpUserName], rax
0x180027420  mov     rax, [rbx+40h]
0x180027424  mov     rcx, [rax+0B8h]; this
0x18002742b  test    rcx, rcx
0x18002742e  jz      short loc_180027437
0x180027430  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x180027435  jmp     short loc_18002743A
0x180027437  mov     rax, r13
0x18002743a  lea     rdx, [rbp+250h+ProfileInfo]; lpProfileInfo
0x18002743e  mov     rcx, rax; hToken
0x180027441  call    cs:__imp_LoadUserProfileW
0x180027447  test    eax, eax
0x180027449  jz      loc_180027249
0x18002744f  mov     rax, [rbp+250h+ProfileInfo.hProfile]
0x180027453  mov     [rbx+1C0h], rax
0x18002745a  mov     rax, [rbx+40h]
0x18002745e  mov     [rbp+250h+ProfileInfo.hProfile], r13
0x180027462  cmp     [rax+248h], r13d
0x180027469  jz      short loc_1800274CA
0x18002746b  mov     rcx, [rax+0B8h]; this
0x180027472  test    rcx, rcx
0x180027475  jz      short loc_18002747E
0x180027477  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x18002747c  jmp     short loc_180027481
0x18002747e  mov     rax, r13
0x180027481  mov     r8d, r12d; bInherit
0x180027484  lea     rcx, [rsp+350h+Environment]; lpEnvironment
0x180027489  mov     rdx, rax; hToken
0x18002748c  call    cs:__imp_CreateEnvironmentBlock
0x180027492  test    eax, eax
0x180027494  jnz     short loc_1800274CA
0x180027496  call    cs:__imp_GetLastError
0x18002749c  mov     edi, eax
0x18002749e  test    eax, eax
0x1800274a0  jle     short loc_1800274AB
0x1800274a2  movzx   edi, ax
0x1800274a5  or      edi, 80070000h
0x1800274ab  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800274b2  jz      loc_180027A3B
0x1800274b8  lea     rax, aCreatingEnviro; "Creating environment block failed\n"
0x1800274bf  mov     r8d, 0F7Ch
0x1800274c5  jmp     loc_1800272AB
0x1800274ca  mov     rcx, [rbx+40h]
0x1800274ce  lea     rax, [rcx+250h]
0x1800274d5  test    rax, rax
0x1800274d8  jz      loc_180027664
0x1800274de  mov     rax, [rcx+270h]
0x1800274e5  cmp     [rax], r13w
0x1800274e9  jz      loc_180027664
0x1800274ef  mov     r14, [rsp+350h+Environment]
0x1800274f4  mov     [rsp+350h+var_2F0], r14
0x1800274f9  test    r14, r14
0x1800274fc  jnz     short loc_18002751A
0x1800274fe  call    cs:__imp_GetEnvironmentStringsW
0x180027504  mov     [rsp+350h+var_2F0], rax
0x180027509  mov     r14, rax
0x18002750c  test    rax, rax
0x18002750f  jz      loc_180027249
0x180027515  mov     [rsp+350h+var_2D8], r12d
0x18002751a  mov     rdx, [rbx+40h]
0x18002751e  lea     rcx, [rbp+250h+var_130]
0x180027525  add     rdx, 250h
0x18002752c  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x180027532  test    eax, eax
  ... truncated ...
```
