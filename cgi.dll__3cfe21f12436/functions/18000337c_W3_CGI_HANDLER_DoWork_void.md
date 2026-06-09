# W3_CGI_HANDLER::DoWork(void)

- ea: `0x18000337c`
- end: `0x18000433d`
- name: `?DoWork@W3_CGI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ`
- size: `4033`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000259c`
- `0x180004678`

## callees

- `0x180003088`
- `0x18000337c`
- `0x1800045fc`
- `0x1800057b0`
- `0x180005914`
- `0x180005a54`
- `0x180005cfc`
- `0x180006114`
- `0x180006214`
- `0x1800069b4`
- `0x180006e52`
- `0x180006e90`
- `0x180006f20`
- `0x180008010`

## import_xrefs

- `msvcrt!wcschr` at `0x180003996`
- `msvcrt!wcschr` at `0x180003996`
- `msvcrt!wcscspn` at `0x180003c5e`
- `msvcrt!wcscspn` at `0x180003c5e`
- `msvcrt!wcsrchr` at `0x180003d47`
- `msvcrt!wcsrchr` at `0x180003d47`
- `msvcrt!_wcsnicmp` at `0x180003d63`
- `msvcrt!_wcsnicmp` at `0x180003d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000363f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000363f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000403b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000403b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000414f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000415d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000414f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000415d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180003f98`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180003f98`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180004028`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180004028`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003e3b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003e3b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800040a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800040a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004197`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004197`
- `iisutil!MakePathCanonicalizationProof` at `0x180003e03`
- `iisutil!MakePathCanonicalizationProof` at `0x180003e03`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003b3a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003b7c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003b3a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003b7c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180003bba`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180003bba`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003659`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003ad9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b16`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b4a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004207`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004302`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003659`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003ad9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b16`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b4a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004207`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004302`
- `iisutil!PuDbgPrint` at `0x1800039d1`
- `iisutil!PuDbgPrint` at `0x180003e82`
- `iisutil!PuDbgPrint` at `0x18000406c`
- `iisutil!PuDbgPrint` at `0x1800041db`
- `iisutil!PuDbgPrint` at `0x1800039d1`
- `iisutil!PuDbgPrint` at `0x180003e82`
- `iisutil!PuDbgPrint` at `0x18000406c`
- `iisutil!PuDbgPrint` at `0x1800041db`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003ab3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003ab3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000364c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003666`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003a41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003ae3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003b54`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800041fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004214`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800042f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000430f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000364c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003666`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003a41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003ae3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003b54`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800041fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004214`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800042f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000430f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003b96`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003b96`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800033e2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000344b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a12`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800033e2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000344b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a12`

## string_xrefs

- `0x1800039c5`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180003e69`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180004060`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x1800041c2`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x1800039aa`: `Refusing request for CGI due to " in path\n`
- `0x180003c80`: `Refusing request for command shell due to special characters\n`
- `0x180003e70`: `SetThreadToken failed, error %d\n`
- `0x18000404b`: `CreateProcess failed, error %d\n`
- `0x180003fc3`: `CreateProcessAsUser failed, error %d\n`
- `0x1800041c9`: `CreateTimerQueueTimer failed, error %d\n`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::DoWork(__int64 a1)
{
  struct IHttpContext *v1; // rdi
  __int64 v3; // r12
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rsi
  int (__fastcall ***v7)(_QWORD, GUID **); // rax
  int (__fastcall **v8)(_QWORD, GUID **); // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  void (__fastcall *v11)(__int64 *, _QWORD *); // rax
  _QWORD *v12; // rax
  unsigned int (__fastcall ***v14)(_QWORD); // rax
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, void *); // rax
  __int64 v17; // r15
  __int64 v18; // rbx
  __int64 v19; // rax
  void *v20; // rax
  __int64 v21; // rcx
  void *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 *v30; // r13
  int IsImageEnabled; // ebx
  struct _HTTP_REQUEST_V2 *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // ebx
  signed int LastError; // eax
  __int64 v37; // r8
  struct _HTTP_REQUEST_V2 *v38; // rax
  __int64 v39; // rax
  int v40; // ebx
  const WCHAR *lpCurrentDirectory; // r12
  int v42; // eax
  __int64 (__fastcall *v43)(struct IHttpServer *, __int64, HANDLE, _QWORD, const WCHAR *, HANDLE, int, LPWSTR *, __int64); // rbx
  __int64 v44; // rax
  HANDLE v45; // rcx
  HANDLE v46; // r8
  const wchar_t *v47; // rax
  wchar_t *v48; // rax
  bool v49; // zf
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  DWORD v53; // eax
  signed int v54; // eax
  WCHAR *v55; // r15
  int v56; // r13d
  bool v57; // cf
  signed int v58; // eax
  int (__fastcall ***v59)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v60; // rax
  const struct _GUID *v61; // rdx
  DWORD v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  __int64 v72; // rdx
  const char *v73; // r8
  __int64 v74; // r9
  DWORD bInheritHandles; // [rsp+28h] [rbp-D8h]
  DWORD bInheritHandlesa; // [rsp+28h] [rbp-D8h]
  int v77; // [rsp+60h] [rbp-A0h] BYREF
  int v78; // [rsp+64h] [rbp-9Ch]
  LPWSTR lpCommandLine; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Token; // [rsp+70h] [rbp-90h]
  __int64 v81; // [rsp+78h] [rbp-88h] BYREF
  struct INativeSectionException *v82; // [rsp+80h] [rbp-80h] BYREF
  __int64 v83; // [rsp+88h] [rbp-78h]
  int *v84; // [rsp+90h] [rbp-70h]
  HANDLE hToken; // [rsp+98h] [rbp-68h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-40h] BYREF
  GUID *v88; // [rsp+130h] [rbp+30h] BYREF
  __int128 v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v91; // [rsp+150h] [rbp+50h]
  int v92; // [rsp+158h] [rbp+58h]
  __int16 v93; // [rsp+15Ch] [rbp+5Ch]
  _QWORD v94[4]; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v95; // [rsp+180h] [rbp+80h]
  __int64 v96; // [rsp+188h] [rbp+88h]
  __int128 v97; // [rsp+190h] [rbp+90h]
  int v98; // [rsp+1A0h] [rbp+A0h]
  int v99; // [rsp+1A4h] [rbp+A4h]
  __int64 v100; // [rsp+1A8h] [rbp+A8h]
  GUID **v101; // [rsp+1B0h] [rbp+B0h]
  _BYTE v102[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t *String; // [rsp+1E0h] [rbp+E0h]
  _BYTE v104[32]; // [rsp+1F8h] [rbp+F8h] BYREF
  LPVOID lpEnvironment; // [rsp+218h] [rbp+118h]
  int v106; // [rsp+220h] [rbp+120h]
  __int16 v107; // [rsp+224h] [rbp+124h]
  _BYTE v108[32]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v109; // [rsp+248h] [rbp+148h]
  int v110; // [rsp+258h] [rbp+158h]
  char v111; // [rsp+260h] [rbp+160h] BYREF
  char v112[271]; // [rsp+261h] [rbp+161h] BYREF
  char v113; // [rsp+370h] [rbp+270h] BYREF
  char v114[8191]; // [rsp+371h] [rbp+271h] BYREF
  unsigned __int16 v115[256]; // [rsp+2370h] [rbp+2270h] BYREF
  unsigned __int16 v116[256]; // [rsp+2570h] [rbp+2470h] BYREF
  unsigned __int16 v117[264]; // [rsp+2770h] [rbp+2670h] BYREF

  v1 = *(struct IHttpContext **)(a1 + 48);
  memset_0(v115, 0, sizeof(v115));
  STRU::STRU((STRU *)v102, v115, 0x100u);
  memset_0(v114, 0, sizeof(v114));
  v106 = 0x2000;
  v113 = 0;
  lpEnvironment = &v113;
  v107 = 256;
  memset_0(v116, 0, sizeof(v116));
  STRU::STRU((STRU *)v108, v116, 0x100u);
  v77 = 0;
  v82 = 0;
  v81 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 24LL))(v1);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v5 = *(_QWORD *)v1;
  v83 = v4;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v5 + 32))(v1);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.hStdOutput = (HANDLE)-1LL;
  StartupInfo.hStdInput = (HANDLE)-1LL;
  (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 200LL))(v1);
  v7 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 272LL))(v1);
  v88 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v8 = *v7;
  v89 = 0;
  if ( (*v8)(v7, &v88) >= 0 && DWORD2(v89) )
  {
    v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 272LL))(v1);
    v94[3] = 11;
    v100 = 1;
    v94[1] = 0;
    v94[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v94[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
    v96 = 1;
    v95 = L"GENERAL_CGI_HANDLER";
    v88 = (GUID *)L"ContextId";
    v101 = &v88;
    v10 = *v9;
    v97 = 0;
    v98 = 0;
    v99 = 1;
    v11 = *(void (__fastcall **)(__int64 *, _QWORD *))(v10 + 16);
    LODWORD(v89) = 72;
    *((_QWORD *)&v89 + 1) = 0;
    v90 = 16;
    v91 = 0;
    v11(v9, v94);
  }
  if ( *(_DWORD *)(a1 + 8392) )
  {
    *(_DWORD *)(a1 + 8392) = 0;
    *(_DWORD *)(a1 + 8396) = 1;
    v14 = (unsigned int (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 16LL))(v1);
    if ( !v14 || !(**v14)(v14) )
    {
      IsImageEnabled = -2147014842;
      goto LABEL_24;
    }
LABEL_14:
    v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 160LL))(v1);
    v16 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
    v84 = (int *)(**v16)(v16, g_pCgiHandlerContext);
    if ( (v84[5] & 0x204) == 0 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 536) = 0;
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
        v6,
        403,
        "Forbidden",
        1,
        -2147024891,
        0,
        0);
LABEL_148:
      W3_CGI_HANDLER::SetCgiStateDoneWithRequest((W3_CGI_HANDLER *)a1);
      STRU::~STRU((STRU *)v108);
      BUFFER::~BUFFER((BUFFER *)v104);
      STRU::~STRU((STRU *)v102);
      return 2;
    }
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)v1 + 184LL))(v1, 0);
    v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 48LL))(v1);
    v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 160LL))(v1);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19) )
    {
      v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 160LL))(v1);
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      Token = (HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 56LL))(v24);
      v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 160LL))(v1);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      v22 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 64LL))(v26);
      v78 = 1;
    }
    else
    {
      v20 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
      v21 = *(_QWORD *)v18;
      Token = v20;
      v22 = (void *)(*(__int64 (__fastcall **)(__int64))(v21 + 40))(v18);
      v78 = 0;
    }
    hToken = v22;
    v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 192LL))(v1);
    v28 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, 0);
    v29 = (const unsigned __int16 *)v17;
    v30 = v28;
    if ( *v28 )
      v29 = v28;
    IsImageEnabled = W3_RESTRICTION_LIST::IsImageEnabled(v29, 0, &v77, &v82, v1);
    if ( IsImageEnabled >= 0 )
    {
      if ( !v77 )
      {
        IsImageEnabled = -2147023636;
        goto LABEL_24;
      }
      if ( *v30 )
      {
        if ( wcschr((const wchar_t *)v17, 0x22u) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
              2069,
              "W3_CGI_HANDLER::DoWork",
              "Refusing request for CGI due to \" in path\n");
LABEL_37:
          IsImageEnabled = -2147024809;
          goto LABEL_24;
        }
        v77 = IsCmdExe(v30);
        memset_0(v117, 0, 0x208u);
        STRU::STRU((STRU *)v94, v117, 0x104u);
        v32 = (struct _HTTP_REQUEST_V2 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
        IsImageEnabled = SetupCmdLine(v32, (struct STRU *)v94);
        if ( IsImageEnabled < 0 )
          goto LABEL_39;
        memset_0(v112, 0, 0x107u);
        v111 = 0;
        v91 = (unsigned __int16 *)&v111;
        v33 = -1;
        v92 = 264;
        v93 = 256;
        do
          ++v33;
        while ( *(_WORD *)(v17 + 2 * v33) );
        v34 = -1;
        do
          ++v34;
        while ( v30[v34] );
        v35 = v34 + v33 + v97;
        if ( !BUFFER::Resize((BUFFER *)&v88, 2 * v35 + 2) )
        {
          LastError = GetLastError();
          IsImageEnabled = LastError;
          if ( LastError > 0 )
            IsImageEnabled = (unsigned __int16)LastError | 0x80070000;
          BUFFER::~BUFFER((BUFFER *)&v88);
          STRU::~STRU((STRU *)v94);
          goto LABEL_24;
        }
        IsImageEnabled = StringCchPrintfW(v91, (unsigned int)(v35 + 1), v30, v17, v95);
        if ( IsImageEnabled < 0 )
          goto LABEL_49;
        v37 = -1;
        do
          ++v37;
        while ( v91[v37] );
        IsImageEnabled = STRU::Copy((STRU *)v102, v91, v37);
        if ( IsImageEnabled < 0 )
        {
LABEL_49:
          BUFFER::~BUFFER((BUFFER *)&v88);
LABEL_39:
          STRU::~STRU((STRU *)v94);
          goto LABEL_24;
        }
        BUFFER::~BUFFER((BUFFER *)&v88);
        STRU::~STRU((STRU *)v94);
      }
      else
      {
        v77 = IsCmdExe((const unsigned __int16 *)v17);
        IsImageEnabled = STRU::Copy((STRU *)v102, L"\"", 1u);
        if ( IsImageEnabled < 0 )
          goto LABEL_24;
        IsImageEnabled = STRU::Append((STRU *)v102, (const unsigned __int16 *)v17);
        if ( IsImageEnabled < 0 )
          goto LABEL_24;
        IsImageEnabled = STRU::Append((STRU *)v102, L"\" ", 2u);
        if ( IsImageEnabled < 0 )
          goto LABEL_24;
        v38 = (struct _HTTP_REQUEST_V2 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
        IsImageEnabled = SetupCmdLine(v38, (struct STRU *)v102);
        if ( IsImageEnabled < 0 )
          goto LABEL_24;
      }
      IsImageEnabled = W3_CGI_HANDLER::SetupChildEnv((W3_CGI_HANDLER *)a1, (struct BUFFER *)v104);
      if ( IsImageEnabled < 0 )
        goto LABEL_24;
      v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 160LL))(v1);
      v40 = 0;
      lpCurrentDirectory = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
      if ( !v77 )
      {
LABEL_71:
        if ( *(_DWORD *)(a1 + 8360) )
          goto LABEL_76;
        v47 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)v1 + 176LL))(v1, 0);
        v48 = wcsrchr(v47, 0x2Fu);
        if ( !v48 || (v49 = _wcsnicmp(v48 + 1, L"nph-", 4u) == 0, v50 = 1, !v49) )
          v50 = 0;
        *(_DWORD *)(a1 + 8360) = v50;
        if ( v50 )
LABEL_76:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 96LL))(v6);
        StartupInfo.lpDesktop = (LPWSTR)&dword_18000ABCC;
        if ( *(_WORD *)(v83 + 816) && *(_DWORD *)(*(_QWORD *)(v83 + 824) + 16LL) )
          v40 = 1;
        if ( (*(_BYTE *)v83 & 1) != 0 )
          v40 = 1;
        IsImageEnabled = W3_CGI_HANDLER::SetupChildPipes((void **)(a1 + 24), (void **)(a1 + 32), &StartupInfo, v40);
        if ( IsImageEnabled < 0 )
          goto LABEL_24;
        v77 = v84[2];
        if ( !*v30 )
        {
          IsImageEnabled = MakePathCanonicalizationProof((const unsigned __int16 *)v17, (struct STRU *)v108);
          if ( IsImageEnabled < 0 )
            goto LABEL_24;
        }
        lpCommandLine = String;
        LODWORD(v83) = v84[3];
        if ( Token && !SetThreadToken(0, Token) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v53 = GetLastError();
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
              2292,
              "W3_CGI_HANDLER::DoWork",
              "SetThreadToken failed, error %d\n",
              v53);
          }
          v54 = GetLastError();
          IsImageEnabled = v54;
          if ( v54 > 0 )
            IsImageEnabled = (unsigned __int16)v54 | 0x80070000;
          goto LABEL_24;
        }
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        if ( *v30 )
        {
          if ( *(_WORD *)v17 == 92 && *(_WORD *)(v17 + 2) == 92 )
          {
            (*(void (__fastcall **)(struct IHttpServer *, __int64, __int64, _QWORD))(*(_QWORD *)g_pGlobalInfo + 24LL))(
              g_pGlobalInfo,
              v51,
              v52,
              0);
            v55 = lpCommandLine;
LABEL_95:
            v56 = 1;
LABEL_101:
            IsImageEnabled = 0;
            if ( (_DWORD)v83 && hToken )
            {
              v57 = v77 != 0;
              v77 = -v77;
              if ( CreateProcessAsUserW(
                     hToken,
                     (LPCWSTR)(v109 & -(__int64)(v110 != 0)),
                     v55,
                     0,
                     0,
                     1,
                     v57 ? 1040 : 1032,
                     lpEnvironment,
                     lpCurrentDirectory,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                goto LABEL_111;
              }
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                bInheritHandles = GetLastError();
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
                  2356,
                  "W3_CGI_HANDLER::DoWork",
                  "CreateProcessAsUser failed, error %d\n",
                  bInheritHandles);
              }
            }
            else
            {
              v57 = v77 != 0;
              v77 = -v77;
              if ( CreateProcessW(
                     (LPCWSTR)(v109 & -(__int64)(v110 != 0)),
                     v55,
                     0,
                     0,
                     1,
                     v57 ? 1040 : 1032,
                     lpEnvironment,
                     lpCurrentDirectory,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                goto LABEL_111;
              }
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                bInheritHandlesa = GetLastError();
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
                  2335,
                  "W3_CGI_HANDLER::DoWork",
                  "CreateProcess failed, error %d\n",
                  bInheritHandlesa);
              }
            }
            v58 = GetLastError();
            IsImageEnabled = v58;
            if ( v58 > 0 )
              IsImageEnabled = (unsigned __int16)v58 | 0x80070000;
LABEL_111:
            if ( v56 )
              (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
            if ( Token )
              RevertToSelf();
            if ( IsImageEnabled >= 0 )
            {
              v59 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 272LL))(v1);
              v88 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
              v89 = 0;
              if ( (**v59)(v59, &v88) >= 0
                && DWORD2(v89)
                && DWORD1(v89) >= 4
                && ((_DWORD)v89 == 32 || (v89 & 0x20) != 0) )
              {
                v60 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 272LL))(v1);
                IISCGIEvents::CGI_LAUNCH::RaiseEvent(v60, v61, v55, IsImageEnabled, ProcessInformation.dwProcessId);
              }
              if ( StartupInfo.hStdInput != (HANDLE)-1LL )
              {
                CloseHandle(StartupInfo.hStdInput);
                StartupInfo.hStdInput = (HANDLE)-1LL;
              }
              CloseHandle(StartupInfo.hStdOutput);
              StartupInfo.hStdOutput = (HANDLE)-1LL;
              CloseHandle(ProcessInformation.hThread);
              *(_QWORD *)(a1 + 40) = ProcessInformation.hProcess;
              if ( !CreateTimerQueueTimer(
                      (PHANDLE)(a1 + 16),
                      0,
                      W3_CGI_HANDLER::CGITerminateProcess,
                      (PVOID)a1,
                      1000 * v84[4],
                      0,
                      8u)
                && (g_dwDebugFlags & 3) != 0 )
              {
                v62 = GetLastError();
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
                  2423,
                  "W3_CGI_HANDLER::DoWork",
                  "CreateTimerQueueTimer failed, error %d\n",
                  v62);
              }
              IsImageEnabled = W3_CGI_HANDLER::CGIStartProcessing((W3_CGI_HANDLER *)a1);
              if ( IsImageEnabled >= 0 )
              {
                STRU::~STRU((STRU *)v108);
                BUFFER::~BUFFER((BUFFER *)v104);
                STRU::~STRU((STRU *)v102);
                return 1;
              }
            }
            goto LABEL_24;
          }
          v55 = lpCommandLine;
        }
        else
        {
          v55 = lpCommandLine;
          if ( *lpCommandLine == 92 && lpCommandLine[1] == 92 )
          {
            (*(void (__fastcall **)(struct IHttpServer *, __int64, __int64, _QWORD))(*(_QWORD *)g_pGlobalInfo + 24LL))(
              g_pGlobalInfo,
              v51,
              v52,
              0);
            goto LABEL_95;
          }
        }
        v56 = 0;
        goto LABEL_101;
      }
      if ( *(_WORD *)v17 == 92 && *(_WORD *)(v17 + 2) == 92 )
        lpCurrentDirectory = 0;
      v42 = wcscspn(String, L"&|(),;%<>");
      if ( String[v42] )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
            2158,
            "W3_CGI_HANDLER::DoWork",
            "Refusing request for command shell due to special characters\n");
        goto LABEL_37;
      }
      lpCommandLine = 0;
      v43 = *(__int64 (__fastcall **)(struct IHttpServer *, __int64, HANDLE, _QWORD, const WCHAR *, HANDLE, int, LPWSTR *, __int64))(*(_QWORD *)g_pGlobalInfo + 64LL);
      v44 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v1 + 272LL))(v1);
      v45 = 0;
      if ( v78 )
      {
        v46 = 0;
        v45 = Token;
      }
      else
      {
        v46 = Token;
      }
      IsImageEnabled = v43(g_pGlobalInfo, v17, v46, 0, lpCurrentDirectory, v45, 1, &lpCommandLine, v44);
      if ( IsImageEnabled >= 0 )
      {
        (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)lpCommandLine + 16LL))(lpCommandLine);
        v40 = 0;
        goto LABEL_71;
      }
    }
LABEL_24:
    if ( StartupInfo.hStdInput != (HANDLE)-1LL )
    {
      CloseHandle(StartupInfo.hStdInput);
      StartupInfo.hStdInput = (HANDLE)-1LL;
    }
    if ( StartupInfo.hStdOutput != (HANDLE)-1LL )
    {
      CloseHandle(StartupInfo.hStdOutput);
      StartupInfo.hStdOutput = (HANDLE)-1LL;
    }
    if ( IsImageEnabled >= 0 )
      goto LABEL_148;
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 536) = 0;
    if ( v82 )
    {
      (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v82)(
        v82,
        &IID_IAppHostConfigException,
        &v81);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v6 + 24LL))(
        v6,
        500,
        "Internal Server Error",
        19,
        IsImageEnabled,
        v81,
        0);
      if ( v81 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        v81 = 0;
      }
      (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
      goto LABEL_148;
    }
    v63 = (unsigned __int16)IsImageEnabled;
    if ( (IsImageEnabled & 0x1FFF0000) != 0x70000 )
      v63 = IsImageEnabled;
    v64 = v63 - 2;
    if ( v64 )
    {
      v65 = v64 - 1;
      if ( v65 )
      {
        v66 = v65 - 2;
        if ( !v66 )
        {
LABEL_144:
          v72 = 401;
          v73 = "Unauthorized";
          v74 = 3;
          goto LABEL_147;
        }
        v67 = v66 - 3;
        if ( !v67 )
        {
LABEL_141:
          v72 = 500;
          v73 = "Internal Server Error";
LABEL_146:
          v74 = 0;
          goto LABEL_147;
        }
        v68 = v67 - 115;
        if ( v68 )
        {
          v69 = v68 - 1137;
          if ( v69 )
          {
            v70 = v69 - 54;
            if ( v70 )
            {
              v71 = v70 - 12;
              if ( v71 && v71 != 5 )
                goto LABEL_141;
              goto LABEL_144;
            }
            v72 = 403;
            v73 = "Forbidden";
            v74 = 19;
          }
          else
          {
            v72 = 404;
            v73 = "Not Found";
            v74 = 2;
          }
LABEL_147:
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
            v6,
            v72,
            v73,
            v74,
            IsImageEnabled,
            0,
            0);
          goto LABEL_148;
        }
      }
    }
    v72 = 404;
    v73 = "Not Found";
    goto LABEL_146;
  }
  if ( W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting < W3_CGI_HANDLER::sm_dwMaxCgisExecuting )
  {
LABEL_11:
    _InterlockedAdd((volatile signed __int32 *)&W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting, 1u);
    *(_DWORD *)(a1 + 8396) = 1;
    goto LABEL_14;
  }
  EnterCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  if ( W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting < W3_CGI_HANDLER::sm_dwMaxCgisExecuting )
  {
    LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
    goto LABEL_11;
  }
  v12 = (_QWORD *)qword_18000D6B0;
  if ( *(struct _LIST_ENTRY **)qword_18000D6B0 != &W3_CGI_HANDLER::sm_QueuedCgisListHead )
    __fastfail(3u);
  *(_QWORD *)(a1 + 8376) = &W3_CGI_HANDLER::sm_QueuedCgisListHead;
  *(_QWORD *)(a1 + 8384) = v12;
  *v12 = a1 + 8376;
  qword_18000D6B0 = a1 + 8376;
  *(_DWORD *)(a1 + 8392) = 1;
  LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  STRU::~STRU((STRU *)v108);
  BUFFER::~BUFFER((BUFFER *)v104);
  STRU::~STRU((STRU *)v102);
  return 1;
}

```

## disassembly

```asm
0x18000337c  push    rbp
0x18000337e  push    rbx
0x18000337f  push    rsi
0x180003380  push    rdi
0x180003381  push    r12
0x180003383  push    r13
0x180003385  push    r14
0x180003387  push    r15
0x180003389  lea     rbp, [rsp-2898h]
0x180003391  mov     eax, 2998h
0x180003396  call    _alloca_probe
0x18000339b  sub     rsp, rax
0x18000339e  mov     rax, cs:__security_cookie
0x1800033a5  xor     rax, rsp
0x1800033a8  mov     [rbp+28D0h+var_50], rax
0x1800033af  mov     rdi, [rcx+30h]
0x1800033b3  mov     r14, rcx
0x1800033b6  mov     esi, 200h
0x1800033bb  lea     rcx, [rbp+28D0h+var_660]; void *
0x1800033c2  mov     r8d, esi; Size
0x1800033c5  xor     edx, edx; Val
0x1800033c7  call    memset_0
0x1800033cc  mov     ebx, 100h
0x1800033d1  lea     rdx, [rbp+28D0h+var_660]
0x1800033d8  mov     r8d, ebx
0x1800033db  lea     rcx, [rbp+28D0h+var_2810]
0x1800033e2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800033e8  xor     edx, edx; Val
0x1800033ea  lea     rcx, [rbp+28D0h+var_265F]; void *
0x1800033f1  mov     r8d, 1FFFh; Size
0x1800033f7  call    memset_0
0x1800033fc  xor     r13d, r13d
0x1800033ff  mov     [rbp+28D0h+var_27B0], 2000h
0x180003409  lea     rax, [rbp+28D0h+var_2660]
0x180003410  mov     [rbp+28D0h+var_2660], r13b
0x180003417  mov     r8d, esi; Size
0x18000341a  mov     [rbp+28D0h+var_27B8], rax
0x180003421  xor     edx, edx; Val
0x180003423  mov     [rbp+28D0h+var_27AC], bx
0x18000342a  lea     rcx, [rbp+28D0h+var_460]; void *
0x180003431  lea     r15d, [r13+1]
0x180003435  call    memset_0
0x18000343a  mov     r8d, ebx
0x18000343d  lea     rdx, [rbp+28D0h+var_460]
0x180003444  lea     rcx, [rbp+28D0h+var_27A8]
0x18000344b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003451  lea     ebx, [r13+68h]
0x180003455  mov     [rsp+29D0h+var_2970], r13d
0x18000345a  mov     r8d, ebx; Size
0x18000345d  mov     [rbp+28D0h+var_2950], r13
0x180003461  xor     edx, edx; Val
0x180003463  mov     [rsp+29D0h+var_2958], r13
0x180003468  lea     rcx, [rbp+28D0h+StartupInfo]; void *
0x18000346c  call    memset_0
0x180003471  mov     rax, [rdi]
0x180003474  mov     rcx, rdi
0x180003477  mov     rax, [rax+18h]
0x18000347b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003480  mov     r12, rax
0x180003483  mov     rcx, [rax]
0x180003486  mov     rax, [rcx+8]
0x18000348a  mov     rcx, r12
0x18000348d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003492  mov     rcx, [rdi]
0x180003495  mov     [rbp+28D0h+var_2948], rax
0x180003499  mov     rax, [rcx+20h]
0x18000349d  mov     rcx, rdi
0x1800034a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a5  mov     r8d, ebx; Size
0x1800034a8  lea     rcx, [rbp+28D0h+StartupInfo]; void *
0x1800034ac  xor     edx, edx; Val
0x1800034ae  mov     rsi, rax
0x1800034b1  call    memset_0
0x1800034b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034ba  mov     [rbp+28D0h+StartupInfo.cb], ebx
0x1800034bd  mov     [rbp+28D0h+StartupInfo.hStdOutput], rax
0x1800034c1  mov     [rbp+28D0h+StartupInfo.hStdInput], rax
0x1800034c5  mov     rcx, [rdi]
0x1800034c8  mov     rax, [rcx+0C8h]
0x1800034cf  mov     rcx, rdi
0x1800034d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d7  mov     rax, [rdi]
0x1800034da  mov     rcx, rdi
0x1800034dd  mov     rax, [rax+110h]
0x1800034e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e9  mov     r8, rax
0x1800034ec  lea     rbx, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800034f3  xorps   xmm0, xmm0
0x1800034f6  mov     [rbp+28D0h+var_28A0], rbx
0x1800034fa  lea     rdx, [rbp+28D0h+var_28A0]
0x1800034fe  mov     rcx, [rax]
0x180003501  movdqu  [rbp+28D0h+var_2898], xmm0
0x180003506  mov     rax, [rcx]
0x180003509  mov     rcx, r8
0x18000350c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003511  test    eax, eax
0x180003513  js      loc_1800035C6
0x180003519  cmp     dword ptr [rbp+28D0h+var_2898+8], r13d
0x18000351d  jz      loc_1800035C6
0x180003523  mov     rax, [rdi]
0x180003526  mov     rcx, rdi
0x180003529  mov     rax, [rax+110h]
0x180003530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003535  mov     rcx, rax
0x180003538  mov     [rbp+28D0h+var_2858], 0Bh
0x180003540  xor     eax, eax
0x180003542  mov     [rbp+28D0h+var_2828], r15
0x180003549  mov     [rbp+28D0h+var_2868], rax
0x18000354d  lea     rdx, [rbp+28D0h+var_2870]
0x180003551  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180003558  mov     [rbp+28D0h+var_2870], rbx
0x18000355c  mov     [rbp+28D0h+var_2860], rax
0x180003560  xorps   xmm0, xmm0
0x180003563  lea     rax, aGeneralCgiHand; "GENERAL_CGI_HANDLER"
0x18000356a  mov     [rbp+28D0h+var_2848], r15
0x180003571  mov     [rbp+28D0h+var_2850], rax
0x180003578  lea     rax, aContextid; "ContextId"
0x18000357f  mov     [rbp+28D0h+var_28A0], rax
0x180003583  lea     rax, [rbp+28D0h+var_28A0]
0x180003587  mov     [rbp+28D0h+var_2820], rax
0x18000358e  mov     rax, [rcx]
0x180003591  movdqa  [rbp+28D0h+var_2840], xmm0
0x180003599  mov     [rbp+28D0h+var_2830], r13d
0x1800035a0  mov     [rbp+28D0h+var_282C], r15d
0x1800035a7  mov     rax, [rax+10h]
0x1800035ab  mov     dword ptr [rbp+28D0h+var_2898], 48h ; 'H'
0x1800035b2  mov     qword ptr [rbp+28D0h+var_2898+8], r13
0x1800035b6  mov     [rbp+28D0h+var_2888], 10h
0x1800035bd  mov     [rbp+28D0h+var_2880], r13
0x1800035c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c6  cmp     [r14+20C8h], r13d
0x1800035cd  jnz     loc_18000368E
0x1800035d3  mov     eax, cs:?sm_dwMaxCgisExecuting@W3_CGI_HANDLER@@0KA; ulong W3_CGI_HANDLER::sm_dwMaxCgisExecuting
0x1800035d9  cmp     cs:?sm_dwCgisCurrentlyExecuting@W3_CGI_HANDLER@@0KA, eax; ulong W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting
0x1800035df  jb      loc_18000367D
0x1800035e5  lea     rbx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION W3_CGI_HANDLER::sm_CgiListLock
0x1800035ec  mov     rcx, rbx; lpCriticalSection
0x1800035ef  call    cs:__imp_EnterCriticalSection
0x1800035f5  mov     eax, cs:?sm_dwMaxCgisExecuting@W3_CGI_HANDLER@@0KA; ulong W3_CGI_HANDLER::sm_dwMaxCgisExecuting
0x1800035fb  cmp     cs:?sm_dwCgisCurrentlyExecuting@W3_CGI_HANDLER@@0KA, eax; ulong W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting
0x180003601  jb      short loc_180003674
0x180003603  mov     rax, cs:qword_18000D6B0
0x18000360a  lea     rdx, ?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x180003611  cmp     [rax], rdx
0x180003614  jz      short loc_18000361D
0x180003616  mov     ecx, 3
0x18000361b  int     29h; Win8: RtlFailFast(ecx)
0x18000361d  lea     rcx, [r14+20B8h]
0x180003624  mov     [rcx], rdx
0x180003627  mov     [rcx+8], rax
0x18000362b  mov     [rax], rcx
0x18000362e  mov     cs:qword_18000D6B0, rcx
0x180003635  mov     rcx, rbx; lpCriticalSection
0x180003638  mov     [r14+20C8h], r15d
0x18000363f  call    cs:__imp_LeaveCriticalSection
0x180003645  lea     rcx, [rbp+28D0h+var_27A8]
0x18000364c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003652  lea     rcx, [rbp+28D0h+var_27D8]
0x180003659  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000365f  lea     rcx, [rbp+28D0h+var_2810]
0x180003666  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000366c  mov     eax, r15d
0x18000366f  jmp     loc_18000431A
0x180003674  mov     rcx, rbx; lpCriticalSection
0x180003677  call    cs:__imp_LeaveCriticalSection
0x18000367d  lock add cs:?sm_dwCgisCurrentlyExecuting@W3_CGI_HANDLER@@0KA, r15d; ulong W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting
0x180003685  mov     [r14+20CCh], r15d
0x18000368c  jmp     short loc_1800036CD
0x18000368e  mov     [r14+20C8h], r13d
0x180003695  mov     rcx, rdi
0x180003698  mov     [r14+20CCh], r15d
0x18000369f  mov     rax, [rdi]
0x1800036a2  mov     rax, [rax+10h]
0x1800036a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ab  mov     rdx, rax
0x1800036ae  test    rax, rax
0x1800036b1  jz      loc_180004224
0x1800036b7  mov     rcx, [rax]
0x1800036ba  mov     rax, [rcx]
0x1800036bd  mov     rcx, rdx
0x1800036c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c5  test    eax, eax
0x1800036c7  jz      loc_180004224
0x1800036cd  mov     rax, [rdi]
0x1800036d0  mov     rcx, rdi
0x1800036d3  mov     rax, [rax+0A0h]
0x1800036da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036df  mov     rdx, rax
0x1800036e2  mov     rcx, [rax]
0x1800036e5  mov     rax, [rcx+18h]
0x1800036e9  mov     rcx, rdx
0x1800036ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f1  mov     rdx, cs:?g_pCgiHandlerContext@@3PEAXEA; void * g_pCgiHandlerContext
0x1800036f8  mov     r8, rax
0x1800036fb  mov     rcx, [rax]
0x1800036fe  mov     rax, [rcx]
0x180003701  mov     rcx, r8
0x180003704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003709  mov     [rbp+28D0h+var_2940], rax
0x18000370d  test    dword ptr [rax+14h], 204h
0x180003714  jnz     short loc_180003753
0x180003716  mov     rax, [rsi]
0x180003719  mov     rcx, rsi
0x18000371c  mov     rax, [rax+8]
0x180003720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003725  mov     [rsp+29D0h+dwCreationFlags], r13d
0x18000372a  lea     r8, aForbidden; "Forbidden"
0x180003731  mov     qword ptr [rsp+29D0h+bInheritHandles], r13
0x180003736  mov     r9d, r15d
0x180003739  mov     edx, 193h
0x18000373e  mov     dword ptr [rsp+29D0h+lpThreadAttributes], 80070005h
0x180003746  mov     [rax+218h], r13w
0x18000374e  jmp     loc_1800042D7
0x180003753  mov     rax, [rdi]
0x180003756  xor     edx, edx
0x180003758  mov     rcx, rdi
0x18000375b  mov     rax, [rax+0B8h]
0x180003762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003767  mov     rcx, [rdi]
0x18000376a  mov     r15, rax
0x18000376d  mov     rax, [rcx+30h]
0x180003771  mov     rcx, rdi
0x180003774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003779  mov     rcx, [rdi]
0x18000377c  mov     rbx, rax
0x18000377f  mov     rax, [rcx+0A0h]
0x180003786  mov     rcx, rdi
0x180003789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378e  mov     rdx, rax
0x180003791  mov     rcx, [rax]
0x180003794  mov     rax, [rcx+10h]
0x180003798  mov     rcx, rdx
0x18000379b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a0  test    rax, rax
0x1800037a3  jnz     short loc_1800037CF
0x1800037a5  mov     rax, [rbx]
0x1800037a8  mov     rcx, rbx
0x1800037ab  mov     rax, [rax+20h]
0x1800037af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b4  mov     rcx, [rbx]
0x1800037b7  mov     [rsp+29D0h+Token], rax
0x1800037bc  mov     rax, [rcx+28h]
0x1800037c0  mov     rcx, rbx
0x1800037c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c8  mov     [rsp+29D0h+var_296C], r13d
0x1800037cd  jmp     short loc_180003848
0x1800037cf  mov     rax, [rdi]
0x1800037d2  mov     rcx, rdi
0x1800037d5  mov     rax, [rax+0A0h]
0x1800037dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e1  mov     rdx, rax
0x1800037e4  mov     rcx, [rax]
0x1800037e7  mov     rax, [rcx+10h]
0x1800037eb  mov     rcx, rdx
0x1800037ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f3  mov     rdx, rax
0x1800037f6  mov     rcx, [rax]
0x1800037f9  mov     rax, [rcx+38h]
0x1800037fd  mov     rcx, rdx
0x180003800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003805  mov     [rsp+29D0h+Token], rax
0x18000380a  mov     rcx, rdi
0x18000380d  mov     rax, [rdi]
0x180003810  mov     rax, [rax+0A0h]
0x180003817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381c  mov     rdx, rax
0x18000381f  mov     rcx, [rax]
0x180003822  mov     rax, [rcx+10h]
0x180003826  mov     rcx, rdx
0x180003829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000382e  mov     rdx, rax
0x180003831  mov     rcx, [rax]
0x180003834  mov     rax, [rcx+40h]
0x180003838  mov     rcx, rdx
0x18000383b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003840  mov     [rsp+29D0h+var_296C], 1
0x180003848  mov     [rbp+28D0h+hToken], rax
0x18000384c  mov     rcx, rdi
0x18000384f  mov     rax, [rdi]
0x180003852  mov     rax, [rax+0C0h]
0x180003859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385e  mov     r8, rax
0x180003861  xor     edx, edx
0x180003863  mov     rcx, [rax]
0x180003866  mov     rax, [rcx+18h]
0x18000386a  mov     rcx, r8
0x18000386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003872  xor     edx, edx; int
0x180003874  mov     [rsp+29D0h+lpThreadAttributes], rdi; struct IHttpContext *
0x180003879  mov     rcx, r15
0x18000387c  lea     r9, [rbp+28D0h+var_2950]; struct INativeSectionException **
0x180003880  lea     r8, [rsp+29D0h+var_2970]; int *
0x180003885  mov     r13, rax
0x180003888  cmp     [rax], dx
0x18000388b  cmovnz  rcx, rax; unsigned __int16 *
0x18000388f  call    ?IsImageEnabled@W3_RESTRICTION_LIST@@SAJPEBGHPEAHPEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z; W3_RESTRICTION_LIST::IsImageEnabled(ushort const *,int,int *,INativeSectionException * *,IHttpContext *)
0x180003894  mov     ebx, eax
0x180003896  xor     eax, eax
0x180003898  test    ebx, ebx
0x18000389a  js      short loc_1800038AB
  ... truncated ...
```
