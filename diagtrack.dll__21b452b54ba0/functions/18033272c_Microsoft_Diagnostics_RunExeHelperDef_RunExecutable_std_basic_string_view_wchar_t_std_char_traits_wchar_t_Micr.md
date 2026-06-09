# Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::EscalationWorkItemState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bool,unsigned __int64 *)

- ea: `0x18033272c`
- end: `0x180335013`
- name: `?RunExecutable@RunExeHelperDef@Diagnostics@Microsoft@@IEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVScenarioInst@23@AEAVEscalationWorkItemState@23@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@_NPEA_K@Z`
- size: `10471`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, PULONG64 CycleTime)`
- caller_count: `1`
- callee_count: `57`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180314c00`

## callees

- `0x180004bec`
- `0x18000bd98`
- `0x18001b510`
- `0x180020e6c`
- `0x18002110c`
- `0x180027c28`
- `0x180027e50`
- `0x18002967c`
- `0x18002abec`
- `0x18002ac10`
- `0x18002b770`
- `0x18002b7c0`
- `0x18002cb04`
- `0x18002df00`
- `0x18003c66c`
- `0x180049d00`
- `0x18004add0`
- `0x18005fb44`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x180069268`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18008abf4`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800b47f0`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800be80c`
- `0x1800c5130`
- `0x1800c582c`
- `0x1800c5d5c`
- `0x1800cf7d8`
- `0x1800d1484`
- `0x1800e9a00`
- `0x1800f7b34`
- `0x180102bbc`
- `0x180129fe0`
- `0x18012f380`
- `0x1801385c0`
- `0x18013cca4`
- `0x180142fcc`
- `0x18016323c`
- `0x1801b2084`
- `0x1801dd408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18033406c`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18033406c`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1803341c3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1803341c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180332b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180332b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333eaf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1803342c4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1803342c4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180333adc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180333adc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803348b7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803348b7`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180332a16`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180332a16`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332850`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332949`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332850`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332949`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180332b29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180332b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180332b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180332b13`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180333ea9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180333ea9`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334514`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803347cb`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803348ff`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334c9a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334e6e`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334514`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803347cb`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803348ff`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334c9a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334e6e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18033434c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18033434c`
- `USERENV!DestroyEnvironmentBlock` at `0x180332e87`
- `USERENV!DestroyEnvironmentBlock` at `0x180334f4d`
- `USERENV!DestroyEnvironmentBlock` at `0x180332e87`
- `USERENV!DestroyEnvironmentBlock` at `0x180334f4d`
- `USERENV!CreateEnvironmentBlock` at `0x180332d0f`
- `USERENV!CreateEnvironmentBlock` at `0x180332d0f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180332c79`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180332c79`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180333809`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180333809`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18033437e`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803345fa`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803349e6`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18033437e`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803345fa`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803349e6`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180333937`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180333937`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180333e90`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180333e90`

## string_xrefs

- `0x180333084`: `ExpandedCommandLine`
- `0x18033278c`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332b57`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332c8b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332d21`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333128`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333149`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333324`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803334d4`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033383f`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333950`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333c65`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333c89`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333ec8`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334094`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803341d9`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803344b4`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803344d5`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033476b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033478c`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803348cd`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334c3a`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334c69`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334ff2`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180335002`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334384`: `RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0`
- `0x180333e37`: `IsValid(childProcessMainThread)`
- `0x180333652`: `Action is running as SYSTEM and targets %temp%.  Redirecting to UTC temp path.\n`
- `0x18033326f`: `Redirecting CiDiag output to UTC temp path.\n`
- `0x180333b04`: `RunExeWithArgsAction_FailedToCreateProcess_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        PULONG64 CycleTime)
{
  __int64 result; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  const char *v14; // r9
  Microsoft::Diagnostics::LifetimeManager *v15; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  const char *v20; // r9
  Microsoft::Diagnostics::LifetimeManager *v21; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v22; // rax
  int v23; // eax
  char v24; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v27; // ebx
  const char *v28; // r9
  const char *v29; // r9
  unsigned int v30; // ebx
  const char *v31; // r9
  unsigned int v32; // ebx
  _OWORD *v33; // rax
  __int64 v34; // rbx
  const char *v35; // r9
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // ebx
  int v45; // r8d
  int v46; // r9d
  WCHAR *v47; // rax
  _QWORD *v48; // rax
  void *appended; // rax
  WCHAR *v50; // rcx
  void *v51; // r8
  void *v52; // rax
  void *v53; // rax
  void *v54; // r8
  HANDLE JobObjectW; // rax
  const char *v56; // r9
  HANDLE v57; // rbx
  unsigned int v58; // ebx
  unsigned int v59; // ebx
  WCHAR *v60; // r8
  const WCHAR *v61; // rdx
  int v62; // eax
  int v63; // eax
  DWORD v64; // ebx
  Microsoft::Diagnostics::LifetimeManager *v65; // rcx
  int v66; // r8d
  int v67; // r9d
  Microsoft::Diagnostics::TelemetryAssert *v68; // rax
  Microsoft::Diagnostics::LifetimeManager *v69; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v70; // rax
  DWORD v71; // eax
  unsigned int v72; // ebx
  HANDLE WaitableTimer; // rdi
  const char *v74; // r9
  unsigned int v75; // ebx
  DWORD v76; // eax
  const char *v77; // r9
  unsigned int v78; // ebx
  __int64 v79; // rdi
  __int64 *v80; // rcx
  DWORD v81; // eax
  int v82; // eax
  int v83; // eax
  const char *v84; // r9
  unsigned int v85; // ebx
  int v86; // ecx
  int v87; // r8d
  int v88; // r9d
  __int128 *v89; // rax
  WCHAR *v90; // rax
  void *v91; // rax
  void *v92; // rax
  int v93; // eax
  _QWORD *v94; // rdx
  int cbSize; // [rsp+20h] [rbp-878h]
  unsigned int cbSizea; // [rsp+20h] [rbp-878h]
  int cbSizeb; // [rsp+20h] [rbp-878h]
  unsigned int cbSizec; // [rsp+20h] [rbp-878h]
  int cbSized; // [rsp+20h] [rbp-878h]
  int cbSizee; // [rsp+20h] [rbp-878h]
  int cbSizef; // [rsp+20h] [rbp-878h]
  int cbSizeg; // [rsp+20h] [rbp-878h]
  __int128 v103; // [rsp+60h] [rbp-838h] BYREF
  DWORD ExitCode; // [rsp+70h] [rbp-828h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-820h] BYREF
  void *phNewToken; // [rsp+80h] [rbp-818h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+88h] [rbp-810h] BYREF
  _BYTE Value[8]; // [rsp+90h] [rbp-808h] BYREF
  HANDLE hProcess; // [rsp+98h] [rbp-800h] BYREF
  unsigned int v110[4]; // [rsp+A0h] [rbp-7F8h] BYREF
  LPVOID Environment[2]; // [rsp+B0h] [rbp-7E8h] BYREF
  LARGE_INTEGER DueTime[2]; // [rsp+C0h] [rbp-7D8h] BYREF
  __int128 v113; // [rsp+D0h] [rbp-7C8h] BYREF
  __int64 v114; // [rsp+E0h] [rbp-7B8h]
  ULONG_PTR Size; // [rsp+E8h] [rbp-7B0h] BYREF
  __int128 v116; // [rsp+F0h] [rbp-7A8h] BYREF
  _BYTE v117[16]; // [rsp+100h] [rbp-798h] BYREF
  _QWORD v118[2]; // [rsp+110h] [rbp-788h] BYREF
  char v119; // [rsp+120h] [rbp-778h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+128h] [rbp-770h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+140h] [rbp-758h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v122; // [rsp+1A8h] [rbp-6F0h]
  _BYTE v123[72]; // [rsp+1B0h] [rbp-6E8h] BYREF
  __int64 v124; // [rsp+1F8h] [rbp-6A0h]
  WCHAR v125[12]; // [rsp+200h] [rbp-698h] BYREF
  unsigned __int64 v126; // [rsp+218h] [rbp-680h]
  _QWORD Src[2]; // [rsp+220h] [rbp-678h] BYREF
  __int64 v128; // [rsp+230h] [rbp-668h]
  unsigned __int64 v129; // [rsp+238h] [rbp-660h]
  WCHAR v130[8]; // [rsp+240h] [rbp-658h] BYREF
  __int64 v131; // [rsp+250h] [rbp-648h]
  unsigned __int64 v132; // [rsp+258h] [rbp-640h]
  HANDLE hJob[4]; // [rsp+260h] [rbp-638h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+280h] [rbp-618h] BYREF
  __int128 v135; // [rsp+2A0h] [rbp-5F8h] BYREF
  __m128i v136; // [rsp+2B0h] [rbp-5E8h]
  LPWSTR lpCommandLine[2]; // [rsp+2C0h] [rbp-5D8h] BYREF
  __m128i si128; // [rsp+2D0h] [rbp-5C8h]
  _QWORD v139[4]; // [rsp+2F0h] [rbp-5A8h] BYREF
  _QWORD JobObjectInformation[2]; // [rsp+310h] [rbp-588h] BYREF
  int v141; // [rsp+320h] [rbp-578h]
  char v142; // [rsp+350h] [rbp-548h]
  _QWORD v143[7]; // [rsp+360h] [rbp-538h] BYREF
  _QWORD *v144; // [rsp+398h] [rbp-500h]
  int v145[282]; // [rsp+3A0h] [rbp-4F8h] BYREF
  int v146[14]; // [rsp+808h] [rbp-90h] BYREF
  HANDLE Handles[2]; // [rsp+840h] [rbp-58h] BYREF
  __int64 v148; // [rsp+850h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+898h] [rbp+0h]

  *(_QWORD *)v110 = a4;
  *(_QWORD *)&v116 = a1;
  v124 = a5;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
      (const char *)0x8007010BLL,
      cbSize);
    std::wstring::_Tidy_deallocate(a5);
    return 2147942667LL;
  }
  try
  {
    std::wstring::wstring(Src, a2);
    Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(Src);
    v9 = Src;
    if ( v129 > 7 )
      v9 = (_QWORD *)Src[0];
    if ( *((_WORD *)v9 + v128 - 1) == 92 )
    {
      v10 = --v128;
      v11 = Src;
      if ( v129 > 7 )
        v11 = (_QWORD *)Src[0];
      *((_WORD *)v11 + v10) = 0;
    }
    ExitCode = 0;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      Value,
      &ExitCode);
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    if ( Size )
      goto LABEL_16;
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
      Environment[0] = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)word_180403672,
        v13,
        (_DWORD)v14,
        (__int64)Environment,
        (__int64)DueTime);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v15);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
    if ( Size )
LABEL_16:
      v17 = 1;
    else
      v17 = 0;
    if ( !v17 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v14);
    std::make_unique<unsigned char [0],0>(&lpAttributeList);
    InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size);
    if ( Size )
      goto LABEL_25;
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
      Environment[0] = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&byte_180403637,
        v19,
        (_DWORD)v20,
        (__int64)Environment,
        (__int64)DueTime);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      v22 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v21);
      Microsoft::Diagnostics::TelemetryAssert::Assert(v22);
    }
    if ( Size )
LABEL_25:
      v23 = 1;
    else
      v23 = 0;
    if ( !v23 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v20);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      Value,
      0);
    UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 8u, 0, 0);
    v24 = 0;
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    StartupInfo.dwFlags = 256;
    v122 = lpAttributeList;
    phNewToken = 0;
    v113 = 0;
    v114 = 0;
    v103 = *(_OWORD *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)&DueTime[0].LowPart = *(_OWORD *)std::wstring::operator std::wstring_view(v116 + 128, hJob);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(DueTime, &v103) )
    {
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          byte_1804036AD);
      v24 = 1;
    }
    TokenHandle = 0;
    if ( !v24 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( LastError != 1008 )
        {
          if ( LastError )
          {
            v27 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                    (const char *)LastError,
                    cbSizea);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v113);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            std::wstring::_Tidy_deallocate(Src);
            std::wstring::_Tidy_deallocate(a5);
            return v27;
          }
          else
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v113);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            std::wstring::_Tidy_deallocate(Src);
            std::wstring::_Tidy_deallocate(a5);
            return 0;
          }
        }
      }
    }
    Environment[0] = 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &phNewToken,
        0);
      if ( !DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &phNewToken) )
      {
        v30 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                v29);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v30;
      }
    }
    if ( !CreateEnvironmentBlock(Environment, phNewToken, 0) )
    {
      v32 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v31);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v32;
    }
    *(_QWORD *)&v103 = Environment;
    BYTE8(v103) = 1;
    *(_OWORD *)&DueTime[0].LowPart = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v118);
    v33 = (_OWORD *)std::wstring::operator std::wstring_view(qword_1804635E8, v117);
    try
    {
      *(_OWORD *)hJob = *v33;
      v34 = Microsoft::Diagnostics::Utils::String::AddEnvironmentVariableToBlock(v139);
      if ( &v113 == (__int128 *)v34 )
      {
        DueTime[0].QuadPart = v113;
      }
      else
      {
        std::vector<wchar_t>::_Tidy(&v113);
        DueTime[0] = *(LARGE_INTEGER *)v34;
        *(LARGE_INTEGER *)&v113 = DueTime[0];
        *((_QWORD *)&v113 + 1) = *(_QWORD *)(v34 + 8);
        v114 = *(_QWORD *)(v34 + 16);
        *(_QWORD *)v34 = 0;
        *(_QWORD *)(v34 + 8) = 0;
        *(_QWORD *)(v34 + 16) = 0;
      }
      std::vector<wchar_t>::_Tidy(v139);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    catch ( ... )
    {
      v110[0] = wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x86,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                  v35);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v124);
      return v110[0];
    }
    std::wstring::wstring(lpApplicationName, &Microsoft::Diagnostics::RunExeHelperDef::k_runExeHelperPath);
    v36 = v116 + 128;
    std::wstring::wstring(v130, v116 + 128);
    std::wstring::wstring(v125, a5);
    Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpCommandLine);
    v103 = *(_OWORD *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v36, v117);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v103) )
    {
      v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v125, v117);
      v37 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v103);
      std::wstring::operator=(v125, v37);
      std::wstring::_Tidy_deallocate(JobObjectInformation);
      ExitCode = Microsoft::Diagnostics::AgentManager::ResolveContainerId(v125);
      if ( (ExitCode & 0x80000000) != 0 )
      {
        *(_QWORD *)&v103 = L"RunExeWithArgsAction_FailedToResolveContainerId";
        *((_QWORD *)&v103 + 1) = 47;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v145,
          (unsigned int)&v103,
          0x1000000,
          0,
          0,
          0,
          0);
        *(_QWORD *)&v103 = L"ExeName";
        *((_QWORD *)&v103 + 1) = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v36);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        *(_QWORD *)&v103 = L"ScenarioId";
        *((_QWORD *)&v103 + 1) = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
        *(_QWORD *)&v103 = L"ScenarioInstanceId";
        *((_QWORD *)&v103 + 1) = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
        *(_QWORD *)&v103 = L"ExpandedCommandLine";
        *((_QWORD *)&v103 + 1) = 19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v125);
        *(_QWORD *)&v103 = L"ErrorCode";
        *((_QWORD *)&v103 + 1) = 9;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v145, (int)v146);
        v103 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v110, &v103);
        v38 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v145);
        if ( v38 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA6,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v38,
            cbSizeb);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C51036LL,
          cbSizeb);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v145);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 2277838902LL;
      }
    }
    v39 = *(_QWORD *)v110;
    if ( ((*(_QWORD *)(*(_QWORD *)v110 + 224LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v103 = *(_OWORD *)&Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineNoOutputPath;
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v125, v117);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v103) )
      {
        std::wstring::assign(v125, Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineWithOutputPath);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v39 + 168));
      }
    }
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpApplicationName);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v130);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v125);
    v103 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v117);
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(qword_180463608, v118);
    v40 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v125);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)(unsigned int)v40,
        cbSizea);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v41;
    }
    v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v125, v117);
    v42 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v103);
    std::wstring::operator=(v125, v42);
    std::wstring::_Tidy_deallocate(JobObjectInformation);
    if ( ((*(_QWORD *)(*(_QWORD *)v110 + 224LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      std::wstring::wstring(v139, v125);
      Microsoft::Diagnostics::Utils::FileSystem::GetWindowsTemporaryPath(JobObjectInformation);
      Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath((WCHAR *)hJob);
      v103 = *(_OWORD *)std::wstring::operator std::wstring_view(hJob, v117);
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(JobObjectInformation, v118);
      v43 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v125);
      v44 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v43,
          cbSizea);
        std::wstring::_Tidy_deallocate(hJob);
        std::wstring::_Tidy_deallocate(JobObjectInformation);
        std::wstring::_Tidy_deallocate(v139);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v44;
      }
      if ( (unsigned __int8)std::operator!=<wchar_t>(v125, v139) )
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        {
          v47 = v125;
          if ( v126 > 7 )
            v47 = *(WCHAR **)v125;
          Environment[0] = v47;
          v48 = v139;
          if ( v139[3] > 7u )
            v48 = (_QWORD *)v139[0];
          TokenHandle = v48;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)byte_1804035CB,
            v45,
            v46,
            (__int64)&TokenHandle,
            (__int64)Environment);
        }
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(*(_QWORD *)v110 + 168LL));
      }
      std::wstring::_Tidy_deallocate(hJob);
      std::wstring::_Tidy_deallocate(JobObjectInformation);
      std::wstring::_Tidy_deallocate(v139);
    }
    v103 = *(_OWORD *)std::wstring::operator std::wstring_view(lpApplicationName, v117);
    appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    Microsoft::Diagnostics::WideStringStream::operator<<(appended);
    v50 = v130;
    if ( v132 > 7 )
      v50 = *(WCHAR **)v130;
    if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v50, v131, 0, 32) == -1 )
    {
      v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v130, v117);
      v53 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    }
    else
    {
      Microsoft::Diagnostics::WideStringStream::operator<<(lpCommandLine);
      v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v130, v117);
      v52 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v51);
      v53 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v52);
    }
    Microsoft::Diagnostics::WideStringStream::operator<<(v53);
    v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v125, v118);
    Microsoft::Diagnostics::WideStringStream::AppendString(v54);
    hJob[0] = 0;
    JobObjectW = CreateJobObjectW(0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      hJob,
      JobObjectW);
    v57 = hJob[0];
    if ( (((unsigned __int64)hJob[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v58 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v58;
    }
    memset_0(JobObjectInformation, 0, 0x40u);
    JobObjectInformation[0] = 10000LL * *(_QWORD *)(v116 + 160);
    v141 = 2;
    if ( !SetInformationJobObject(v57, JobObjectBasicLimitInformation, JobObjectInformation, 0x40u) )
    {
      v59 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v59;
    }
    v135 = *(_OWORD *)lpCommandLine;
    v136 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpCommandLine[0]) = 0;
    hProcess = 0;
    TokenHandle = 0;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v60 = (WCHAR *)&v135;
    if ( _mm_srli_si128(v136, 8).m128i_u64[0] > 7 )
      v60 = (WCHAR *)v135;
    v61 = (const WCHAR *)lpApplicationName;
    if ( lpApplicationName[3] > (LPCWSTR)7 )
      v61 = lpApplicationName[0];
    if ( !CreateProcessAsUserW(
            phNewToken,
            v61,
            v60,
            0,
            0,
            1,
            0x8080404u,
            (LPVOID)DueTime[0].QuadPart,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      v62 = GetLastError();
      if ( v62 > 0 )
        v62 = (unsigned __int16)v62 | 0x80070000;
      ExitCode = v62;
      *(_QWORD *)&v103 = L"RunExeWithArgsAction_FailedToCreateProcess_0";
      *((_QWORD *)&v103 + 1) = 44;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v145,
        (unsigned int)&v103,
        0x1000000,
        0,
        0,
        0,
        0);
      *(_QWORD *)&v103 = L"ExeName";
      *((_QWORD *)&v103 + 1) = 7;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v116 + 128);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      *(_QWORD *)&v103 = L"ScenarioId";
      *((_QWORD *)&v103 + 1) = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
      *(_QWORD *)&v103 = L"ScenarioInstanceId";
      *((_QWORD *)&v103 + 1) = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
      *(_QWORD *)&v103 = L"ErrorCode";
      *((_QWORD *)&v103 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v145, (int)v146);
      v103 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v110, &v103);
      v63 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v145);
      if ( v63 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v63,
          cbSized);
      v64 = ExitCode;
      if ( (ExitCode & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)ExitCode,
          cbSized);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v145);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v135);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v64;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hProcess,
      ProcessInformation.hProcess);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      ProcessInformation.hThread);
    if ( (((unsigned __int64)hProcess + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_1804543B0 > 2 )
      {
        DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
        Environment[0] = "IsValid(childProcess)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v65,
          (unsigned int)&unk_180403590,
          v66,
          v67,
          (__int64)Environment,
          (__int64)DueTime);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v68 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v65);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v68);
      }
    }
    if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_1804543B0 > 2 )
      {
        DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
        Environment[0] = "IsValid(childProcessMainThread)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v65,
          (unsigned int)&dword_1804034F4,
          v66,
          v67,
          (__int64)Environment,
          (__int64)DueTime);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v70 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v69);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v70);
      }
    }
    if ( !AssignProcessToJobObject(v57, hProcess) )
    {
      TerminateProcess(ProcessInformation.hProcess, 1u);
      v71 = GetLastError();
      if ( v71 )
      {
        v72 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x133,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                (const char *)v71,
                cbSizec);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v135);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v72;
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v135);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 0;
      }
    }
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    Environment[0] = WaitableTimer;
    if ( (((unsigned __int64)WaitableTimer + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v75 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x139,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v74);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v135);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v75;
    }
    v76 = -10000 * *(_DWORD *)(v116 + 160);
    DueTime[0].HighPart = (-10000LL * (unsigned __int64)*(unsigned int *)(v116 + 160)) >> 32;
    DueTime[0].LowPart = v76;
    if ( !SetWaitableTimer(WaitableTimer, DueTime, 0, 0, 0, 0) )
    {
      v78 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x140,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v77);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v135);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v78;
    }
    ResumeThread(ProcessInformation.hThread);
    v148 = 0;
    Handles[0] = hProcess;
    Handles[1] = WaitableTimer;
    v79 = *(_QWORD *)v110;
    v80 = *(__int64 **)(*(_QWORD *)v110 + 216LL);
    v148 = *v80;
    LODWORD(v80) = (*v80 != 0) + 2;
    v118[0] = &CycleTime;
    v118[1] = &hProcess;
    v119 = 1;
    v81 = WaitForMultipleObjects((DWORD)v80, Handles, 0, 0xFFFFFFFF);
    if ( v81 == 2 )
    {
      if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(hProcess, 0x1388u) )
      {
        TerminateJobObject(v57, 1u);
        *(_QWORD *)&v103 = L"RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0";
        *((_QWORD *)&v103 + 1) = 56;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v145,
          (unsigned int)&v103,
          0x1000000,
          0,
          0,
          0,
          0);
        *(_QWORD *)&v103 = L"ExeName";
        *((_QWORD *)&v103 + 1) = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v116 + 128);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        *(_QWORD *)&v103 = L"ScenarioId";
        *((_QWORD *)&v103 + 1) = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
        *(_QWORD *)&v103 = L"ScenarioInstanceId";
        *((_QWORD *)&v103 + 1) = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
        v103 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v110, &v103);
        v82 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v145);
        if ( v82 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v82,
            cbSizef);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101ALL,
          cbSizef);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v145);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
LABEL_117:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v135);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 2277838874LL;
      }
    }
    else if ( v81 == 1 )
    {
      TerminateJobObject(v57, 1u);
      *(_QWORD *)&v103 = L"RunExeWithArgsAction_ExeTerminated_0";
      *((_QWORD *)&v103 + 1) = 36;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v145,
        (unsigned int)&v103,
        0x1000000,
        0,
        0,
        0,
        0);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      *(_QWORD *)&v103 = L"ScenarioId";
      *((_QWORD *)&v103 + 1) = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
      *(_QWORD *)&v103 = L"ScenarioInstanceId";
      *((_QWORD *)&v103 + 1) = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
      *(_QWORD *)&v103 = L"ExpandedExeName";
      *((_QWORD *)&v103 + 1) = 15;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v130);
      *(_QWORD *)&v103 = L"MaximumRuntimeMs";
      *((_QWORD *)&v103 + 1) = 16;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v145, (int)v146);
      v103 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v110, &v103);
      v83 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v145);
      if ( v83 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v83,
          cbSizeg);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)0x87C5101ALL,
        cbSizeg);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v145);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      goto LABEL_117;
    }
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      if ( ExitCode == 259 )
      {
        TerminateJobObject(v57, 1u);
        ExitCode = 0;
      }
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
      {
        v110[0] = ExitCode;
        v89 = &v135;
        if ( v136.m128i_i64[1] > 7uLL )
          v89 = (__int128 *)v135;
        DueTime[0].QuadPart = (LONGLONG)v89;
        v90 = v130;
        if ( v132 > 7 )
          v90 = *(WCHAR **)v130;
        *(_QWORD *)&v103 = v90;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v86,
          (unsigned int)&byte_18040352F,
          v87,
          v88,
          (__int64)&v103,
          (__int64)DueTime,
          (__int64)v110);
      }
      v91 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v79 + 168));
      v92 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v91);
      Microsoft::Diagnostics::WideStringStream::operator<<(v92);
      if ( ExitCode )
      {
        if ( !*(_BYTE *)(v116 + 56) )
        {
          *(_QWORD *)&v103 = L"RunExeWithArgsAction_ProcessReturnedNonZeroExitCode";
          *((_QWORD *)&v103 + 1) = 51;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
            (unsigned int)v145,
            (unsigned int)&v103,
            0x1000000,
            0,
            0,
            0,
            0);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
          *(_QWORD *)&v103 = L"ScenarioId";
          *((_QWORD *)&v103 + 1) = 10;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
          *(_QWORD *)&v103 = L"ScenarioInstanceId";
          *((_QWORD *)&v103 + 1) = 18;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v145, (int)v146);
          *(_QWORD *)&v103 = L"ExpandedExeName";
          *((_QWORD *)&v103 + 1) = 15;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v145, v146, &v103, v130);
          *(_QWORD *)&v103 = L"ExitCode";
          *((_QWORD *)&v103 + 1) = 8;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v145, v146, &v103, &ExitCode);
          v103 = 0;
          Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v110, &v103);
          v93 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v145);
          if ( v93 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1B1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              (const char *)(unsigned int)v93,
              cbSizee);
          Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v145);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101DLL,
          cbSizee);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v135);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        result = 2277838877LL;
      }
      else
      {
        v142 = 0;
        v123[64] = 0;
        v143[0] = off_180381998;
        v143[1] = v79;
        v144 = v143;
        *(_QWORD *)&v103 = L"*";
        *((_QWORD *)&v103 + 1) = 1;
        DueTime[0].QuadPart = (LONGLONG)L"*";
        DueTime[1].QuadPart = 1;
        v116 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v117);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(
          (unsigned int)&v116,
          (unsigned int)DueTime,
          (unsigned int)&v103,
          (unsigned int)v143,
          (__int64)v123,
          (__int64)JobObjectInformation);
        if ( v144 )
        {
          v94 = v143;
          LOBYTE(v94) = v144 != v143;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v144 + 32LL))(v144, v94);
        }
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v135);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v125);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v113);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        result = 0;
      }
    }
    else
    {
      v85 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x189,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v84);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v135);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v125);
      std::wstring::_Tidy_deallocate(v130);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v113);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      result = v85;
    }
  }
  catch ( ... )
  {
    v110[0] = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x1C5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                v28);
    std::wstring::_Tidy_deallocate(v124);
    return v110[0];
  }
  return result;
}

```

## disassembly

```asm
0x18033272c  push    rbx
0x18033272e  push    rsi
0x18033272f  push    rdi
0x180332730  push    r12
0x180332732  push    r13
0x180332734  push    r14
0x180332736  push    r15
0x180332738  sub     rsp, 860h
0x18033273f  mov     rax, cs:__security_cookie
0x180332746  xor     rax, rsp
0x180332749  mov     [rsp+898h+var_40], rax
0x180332751  mov     qword ptr [rsp+898h+var_7F8], r9
0x180332759  mov     r15, r8
0x18033275c  mov     qword ptr [rsp+898h+var_7A8], rcx
0x180332764  mov     rsi, [rsp+898h+arg_20]
0x18033276c  mov     [rsp+898h+var_6A0], rsi
0x180332774  xor     ebx, ebx
0x180332776  cmp     [rdx+8], rbx
0x18033277a  jnz     short loc_1803327AD
0x18033277c  mov     rcx, [rsp+898h]; this
0x180332784  mov     ebx, 8007010Bh
0x180332789  mov     r9d, ebx; char *
0x18033278c  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332793  mov     edx, 1Dh; void *
0x180332798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033279d  nop
0x18033279e  mov     rcx, rsi
0x1803327a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803327a6  mov     eax, ebx
0x1803327a8  jmp     loc_180334FCF
0x1803327ad  lea     rcx, [rsp+898h+Src]
0x1803327b5  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1803327ba  nop
0x1803327bb  lea     rcx, [rsp+898h+Src]; Src
0x1803327c3  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x1803327c8  lea     rax, [rsp+898h+Src]
0x1803327d0  cmp     [rsp+898h+var_660], 7
0x1803327d9  cmova   rax, [rsp+898h+Src]
0x1803327e2  mov     rdx, [rsp+898h+var_668]
0x1803327ea  mov     r14d, 1
0x1803327f0  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1803327f6  jnz     short loc_180332821
0x1803327f8  sub     rdx, r14
0x1803327fb  mov     [rsp+898h+var_668], rdx
0x180332803  lea     rcx, [rsp+898h+Src]
0x18033280b  cmp     [rsp+898h+var_660], 7
0x180332814  cmova   rcx, [rsp+898h+Src]
0x18033281d  mov     [rcx+rdx*2], bx
0x180332821  mov     [rsp+898h+ExitCode], ebx
0x180332825  lea     rdx, [rsp+898h+ExitCode]
0x18033282a  lea     rcx, [rsp+898h+Value]
0x180332832  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180332837  nop
0x180332838  mov     [rsp+898h+Size], rbx
0x180332840  lea     r9, [rsp+898h+Size]; lpSize
0x180332848  xor     r8d, r8d; dwFlags
0x18033284b  mov     edx, r14d; dwAttributeCount
0x18033284e  xor     ecx, ecx; lpAttributeList
0x180332850  call    cs:__imp_InitializeProcThreadAttributeList
0x180332856  mov     rdx, [rsp+898h+Size]
0x18033285e  mov     r12d, 2
0x180332864  test    rdx, rdx
0x180332867  jnz     loc_1803328FD
0x18033286d  mov     eax, cs:dword_1804543B0
0x180332873  cmp     eax, r12d
0x180332876  jbe     short loc_1803328BE
0x180332878  lea     r13, aRunexecutable; "RunExecutable"
0x18033287f  mov     qword ptr [rsp+898h+DueTime], r13
0x180332887  lea     rbx, aAttributessize; "attributesSize > 0"
0x18033288e  mov     [rsp+898h+Environment], rbx
0x180332896  lea     rax, [rsp+898h+DueTime]
0x18033289e  mov     [rsp+898h+lpPreviousValue], rax
0x1803328a3  lea     rax, [rsp+898h+Environment]
0x1803328ab  mov     [rsp+898h+cbSize], rax
0x1803328b0  lea     rdx, word_180403672
0x1803328b7  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1803328bc  jmp     short loc_1803328CC
0x1803328be  lea     r13, aRunexecutable; "RunExecutable"
0x1803328c5  lea     rbx, aAttributessize; "attributesSize > 0"
0x1803328cc  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1803328d3  mov     rcx, rdi; this
0x1803328d6  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1803328db  test    al, al
0x1803328dd  jz      short loc_1803328EC
0x1803328df  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1803328e4  mov     rcx, rax; this
0x1803328e7  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1803328ec  mov     rdx, [rsp+898h+Size]
0x1803328f4  test    rdx, rdx
0x1803328f7  jnz     short loc_180332912
0x1803328f9  xor     eax, eax
0x1803328fb  jmp     short loc_180332915
0x1803328fd  lea     r13, aRunexecutable; "RunExecutable"
0x180332904  lea     rbx, aAttributessize; "attributesSize > 0"
0x18033290b  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x180332912  mov     eax, r14d
0x180332915  mov     rcx, [rsp+898h]; this
0x18033291d  test    eax, eax
0x18033291f  jz      loc_180334FF2
0x180332925  lea     rcx, [rsp+898h+lpAttributeList]
0x18033292d  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180332932  nop
0x180332933  lea     r9, [rsp+898h+Size]; lpSize
0x18033293b  xor     r8d, r8d; dwFlags
0x18033293e  mov     edx, r14d; dwAttributeCount
0x180332941  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x180332949  call    cs:__imp_InitializeProcThreadAttributeList
0x18033294f  cmp     [rsp+898h+Size], 0
0x180332958  ja      short loc_1803329C6
0x18033295a  mov     eax, cs:dword_1804543B0
0x180332960  cmp     eax, r12d
0x180332963  jbe     short loc_18033299B
0x180332965  mov     qword ptr [rsp+898h+DueTime], r13
0x18033296d  mov     [rsp+898h+Environment], rbx
0x180332975  lea     rax, [rsp+898h+DueTime]
0x18033297d  mov     [rsp+898h+lpPreviousValue], rax
0x180332982  lea     rax, [rsp+898h+Environment]
0x18033298a  mov     [rsp+898h+cbSize], rax
0x18033298f  lea     rdx, byte_180403637
0x180332996  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18033299b  mov     rcx, rdi; this
0x18033299e  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1803329a3  xor     r13d, r13d
0x1803329a6  test    al, al
0x1803329a8  jz      short loc_1803329B7
0x1803329aa  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1803329af  mov     rcx, rax; this
0x1803329b2  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1803329b7  cmp     [rsp+898h+Size], r13
0x1803329bf  ja      short loc_1803329C9
0x1803329c1  mov     eax, r13d
0x1803329c4  jmp     short loc_1803329CC
0x1803329c6  xor     r13d, r13d
0x1803329c9  mov     eax, r14d
0x1803329cc  mov     rcx, [rsp+898h]; this
0x1803329d4  test    eax, eax
0x1803329d6  jz      loc_180335002
0x1803329dc  xor     edx, edx
0x1803329de  lea     rcx, [rsp+898h+Value]
0x1803329e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1803329eb  mov     [rsp+898h+lpReturnSize], r13; lpReturnSize
0x1803329f0  mov     [rsp+898h+lpPreviousValue], r13; lpPreviousValue
0x1803329f5  mov     [rsp+898h+cbSize], 8; int
0x1803329fe  lea     r9, [rsp+898h+Value]; lpValue
0x180332a06  xor     edx, edx; dwFlags
0x180332a08  mov     r8d, 20002h; Attribute
0x180332a0e  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x180332a16  call    cs:__imp_UpdateProcThreadAttribute
0x180332a1c  mov     ebx, 70h ; 'p'
0x180332a21  mov     r8d, ebx; Size
0x180332a24  xor     edx, edx; Val
0x180332a26  lea     rcx, [rsp+898h+StartupInfo]; void *
0x180332a2e  call    memset_0
0x180332a33  mov     [rsp+898h+StartupInfo.cb], ebx
0x180332a3a  mov     [rsp+898h+StartupInfo.dwFlags], 100h
0x180332a45  mov     rax, [rsp+898h+lpAttributeList]
0x180332a4d  mov     [rsp+898h+var_6F0], rax
0x180332a55  mov     [rsp+898h+phNewToken], r13
0x180332a5d  xorps   xmm0, xmm0
0x180332a60  movdqu  [rsp+898h+var_7C8], xmm0
0x180332a69  mov     [rsp+898h+var_7B8], r13
0x180332a71  mov     bl, r13b
0x180332a74  mov     rcx, qword ptr [rsp+898h+var_7A8]
0x180332a7c  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180332a80  movups  xmm0, xmmword ptr cs:?k_hcsdiagPath@RunExeHelperDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath
0x180332a87  movdqu  [rsp+898h+var_838], xmm0
0x180332a8d  lea     rdx, [rsp+898h+hJob]
0x180332a95  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180332a9a  movups  xmm0, xmmword ptr [rax]
0x180332a9d  movdqu  xmmword ptr [rsp+898h+DueTime], xmm0
0x180332aa6  lea     rdx, [rsp+898h+var_838]
0x180332aab  lea     rcx, [rsp+898h+DueTime]
0x180332ab3  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180332ab8  mov     r13d, 4
0x180332abe  test    eax, eax
0x180332ac0  jnz     short loc_180332AF6
0x180332ac2  mov     eax, cs:dword_1804543B0
0x180332ac8  cmp     eax, r13d
0x180332acb  jbe     short loc_180332AF3
0x180332acd  mov     edx, r13d
0x180332ad0  lea     rcx, dword_1804543B0
0x180332ad7  call    _tlgKeywordOn
0x180332adc  test    al, al
0x180332ade  jz      short loc_180332AF3
0x180332ae0  lea     rdx, byte_1804036AD
0x180332ae7  lea     rcx, dword_1804543B0
0x180332aee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180332af3  mov     bl, r14b
0x180332af6  mov     [rsp+898h+TokenHandle], 0
0x180332aff  test    bl, bl
0x180332b01  jnz     loc_180332C2A
0x180332b07  xor     edx, edx
0x180332b09  lea     rcx, [rsp+898h+TokenHandle]
0x180332b0e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180332b13  call    cs:__imp_GetCurrentThread
0x180332b19  lea     r9, [rsp+898h+TokenHandle]; TokenHandle
0x180332b1e  mov     r8d, r14d; OpenAsSelf
0x180332b21  mov     edx, 0F01FFh; DesiredAccess
0x180332b26  mov     rcx, rax; ThreadHandle
0x180332b29  call    cs:__imp_OpenThreadToken
0x180332b2f  test    eax, eax
0x180332b31  jnz     loc_180332C2A
0x180332b37  call    cs:__imp_GetLastError
0x180332b3d  cmp     eax, 3F0h
0x180332b42  jz      loc_180332C2A
0x180332b48  test    eax, eax
0x180332b4a  jz      short loc_180332BCA
0x180332b4c  mov     rcx, [rsp+898h]; this
0x180332b54  mov     r9d, eax; char *
0x180332b57  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332b5e  mov     edx, 67h ; 'g'; void *
0x180332b63  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180332b68  mov     ebx, eax
0x180332b6a  lea     rcx, [rsp+898h+TokenHandle]
0x180332b6f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332b74  nop
0x180332b75  lea     rcx, [rsp+898h+var_7C8]
0x180332b7d  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332b82  nop
0x180332b83  lea     rcx, [rsp+898h+phNewToken]
0x180332b8b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332b90  nop
0x180332b91  lea     rcx, [rsp+898h+lpAttributeList]
0x180332b99  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332b9e  nop
0x180332b9f  lea     rcx, [rsp+898h+Value]
0x180332ba7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332bac  nop
0x180332bad  lea     rcx, [rsp+898h+Src]
0x180332bb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332bba  nop
0x180332bbb  mov     rcx, rsi
0x180332bbe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332bc3  mov     eax, ebx
0x180332bc5  jmp     loc_180334FCF
0x180332bca  lea     rcx, [rsp+898h+TokenHandle]
0x180332bcf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332bd4  nop
0x180332bd5  lea     rcx, [rsp+898h+var_7C8]
0x180332bdd  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332be2  nop
0x180332be3  lea     rcx, [rsp+898h+phNewToken]
0x180332beb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332bf0  nop
0x180332bf1  lea     rcx, [rsp+898h+lpAttributeList]
0x180332bf9  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332bfe  nop
0x180332bff  lea     rcx, [rsp+898h+Value]
0x180332c07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332c0c  nop
0x180332c0d  lea     rcx, [rsp+898h+Src]
0x180332c15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332c1a  nop
0x180332c1b  mov     rcx, rsi
0x180332c1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332c23  xor     eax, eax
0x180332c25  jmp     loc_180334FCF
0x180332c2a  mov     [rsp+898h+Environment], 0
0x180332c36  mov     rax, [rsp+898h+TokenHandle]
0x180332c3b  dec     rax
0x180332c3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180332c42  ja      loc_180332CFC
0x180332c48  xor     edx, edx
0x180332c4a  lea     rcx, [rsp+898h+phNewToken]
0x180332c52  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180332c57  lea     rax, [rsp+898h+phNewToken]
0x180332c5f  mov     [rsp+898h+lpPreviousValue], rax; phNewToken
0x180332c64  mov     dword ptr [rsp+898h+cbSize], r14d; TokenType
0x180332c69  mov     r9d, r12d; ImpersonationLevel
0x180332c6c  xor     r8d, r8d; lpTokenAttributes
0x180332c6f  mov     edx, 0F01FFh; dwDesiredAccess
0x180332c74  mov     rcx, [rsp+898h+TokenHandle]; hExistingToken
0x180332c79  call    cs:__imp_DuplicateTokenEx
0x180332c7f  test    eax, eax
0x180332c81  jnz     short loc_180332CFC
0x180332c83  mov     rcx, [rsp+898h]; this
0x180332c8b  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332c92  lea     edx, [rax+79h]; void *
0x180332c95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180332c9a  mov     ebx, eax
0x180332c9c  lea     rcx, [rsp+898h+TokenHandle]
0x180332ca1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332ca6  nop
0x180332ca7  lea     rcx, [rsp+898h+var_7C8]
0x180332caf  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332cb4  nop
0x180332cb5  lea     rcx, [rsp+898h+phNewToken]
0x180332cbd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332cc2  nop
0x180332cc3  lea     rcx, [rsp+898h+lpAttributeList]
0x180332ccb  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332cd0  nop
0x180332cd1  lea     rcx, [rsp+898h+Value]
0x180332cd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332cde  nop
0x180332cdf  lea     rcx, [rsp+898h+Src]
0x180332ce7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332cec  nop
0x180332ced  mov     rcx, rsi
0x180332cf0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
