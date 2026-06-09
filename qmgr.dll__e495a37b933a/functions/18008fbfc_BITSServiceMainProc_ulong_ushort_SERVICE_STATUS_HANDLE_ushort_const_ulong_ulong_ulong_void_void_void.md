# BITSServiceMainProc(ulong,ushort * *,SERVICE_STATUS_HANDLE__ * (*)(ushort const *,ulong (*)(ulong,ulong,void *,void *),void *))

- ea: `0x18008fbfc`
- end: `0x1800902e2`
- name: `?BITSServiceMainProc@@YAXKPEAPEAGP6APEAUSERVICE_STATUS_HANDLE__@@PEBGP6AKKKPEAX2@Z2@Z@Z`
- size: `1766`
- prototype: `void __fastcall(__int64, unsigned __int16 **, __int64 (*)(void))`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ab6d0`

## callees

- `0x180006640`
- `0x180014a30`
- `0x180041a48`
- `0x180045ea0`
- `0x180046de8`
- `0x18007c6c0`
- `0x18007f860`
- `0x180081600`
- `0x180085890`
- `0x18008fbfc`
- `0x180090524`
- `0x180090560`
- `0x1800983b8`
- `0x180098554`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a8284`
- `0x1800a8a48`
- `0x1800aa554`
- `0x1800aa634`
- `0x1800ab7fc`
- `0x1800b6e64`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `bitsperf!?Initialize@CPerfMon@@QEAAKH@Z` at `0x18008ff9b`
- `bitsperf!?Initialize@CPerfMon@@QEAAKH@Z` at `0x18008ff9b`
- `bitsperf!??0CPerfMon@@QEAA@PEAGPEAU_PERF_ITEM@0@@Z` at `0x18008ff38`
- `bitsperf!??0CPerfMon@@QEAA@PEAGPEAU_PERF_ITEM@0@@Z` at `0x18008ff38`
- `ntdll!DbgPrint` at `0x18008ff56`
- `ntdll!DbgPrint` at `0x18008ffb3`
- `ntdll!DbgPrint` at `0x18008ff56`
- `ntdll!DbgPrint` at `0x18008ffb3`
- `ntdll!EtwUnregisterTraceGuids` at `0x180090295`
- `ntdll!EtwUnregisterTraceGuids` at `0x180090295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fe31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008fe0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008fe0f`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18008fc8c`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18008fc8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090147`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090235`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090147`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090235`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008fdff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008fdff`

## pseudocode

```c
void __fastcall BITSServiceMainProc(__int64 a1, unsigned __int16 **a2, __int64 (*a3)(void))
{
  DWORD LastError; // eax
  DWORD v5; // eax
  signed int v6; // edi
  bool v7; // sf
  HANDLE EventW; // rax
  DWORD v9; // eax
  signed int v10; // edi
  EVENT_LOG *v11; // rcx
  bool v12; // sf
  CPerfMon *v13; // rax
  CPerfMon *v14; // rax
  EVENT_LOG *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // edx
  int v19; // ecx
  ULONGLONG TickCount64; // r13
  bool v21; // di
  unsigned int BitsServiceStartupType; // r15d
  unsigned __int64 v23; // rdx
  unsigned __int8 v24; // cl
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rcx
  int inited; // ecx
  ULONGLONG v29; // rdi
  unsigned int v30; // r15d
  unsigned int BitsServiceShutdownType; // r12d
  unsigned __int64 v32; // rdx
  unsigned __int8 v33; // cl
  unsigned int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rcx
  signed int dwLowDateTime; // r15d
  GlobalInfo *v38; // rdi
  CPerfMon *v39; // rcx
  ULONGLONG v40; // rax
  EVENT_LOG *v41; // rdi
  struct _FILETIME v42; // [rsp+28h] [rbp-290h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-288h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-278h] BYREF
  __int128 v45; // [rsp+48h] [rbp-270h]
  signed int v46; // [rsp+58h] [rbp-260h]
  int v47; // [rsp+5Ch] [rbp-25Ch]
  int v48; // [rsp+60h] [rbp-258h]
  void **v49; // [rsp+A0h] [rbp-218h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-210h]
  int v51; // [rsp+B8h] [rbp-200h]
  int v52; // [rsp+BCh] [rbp-1FCh]
  int v53; // [rsp+C0h] [rbp-1F8h]
  void **v54; // [rsp+100h] [rbp-1B8h] BYREF
  __int128 v55; // [rsp+108h] [rbp-1B0h]
  signed int v56; // [rsp+118h] [rbp-1A0h]
  int v57; // [rsp+11Ch] [rbp-19Ch]
  int v58; // [rsp+120h] [rbp-198h]
  void **v59; // [rsp+160h] [rbp-158h] BYREF
  __int128 v60; // [rsp+168h] [rbp-150h]
  int v61; // [rsp+178h] [rbp-140h]
  int v62; // [rsp+17Ch] [rbp-13Ch]
  int v63; // [rsp+180h] [rbp-138h]
  void **v64; // [rsp+1C0h] [rbp-F8h] BYREF
  __int128 v65; // [rsp+1C8h] [rbp-F0h]
  int v66; // [rsp+1D8h] [rbp-E0h]
  int v67; // [rsp+1DCh] [rbp-DCh]
  int v68; // [rsp+1E0h] [rbp-D8h]
  void **v69; // [rsp+220h] [rbp-98h] BYREF
  __int64 v70; // [rsp+228h] [rbp-90h] BYREF
  DWORD v71; // [rsp+238h] [rbp-80h]

  ++g_ServiceInstance;
  qword_180145538 = 0;
  WPP_MAIN_CB = 0;
  qword_180145540 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = (EVENT_LOG *)&WPP_MAIN_CB;
  WppInitUm(a1, a2);
  v42.dwLowDateTime = GetRedirectionPolicy();
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v42, 4)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, LastError);
  }
  gServiceStatus.dwServiceType = 32;
  gServiceStatus.dwCurrentState = 2;
  gServiceStatus.dwControlsAccepted = 4608;
  *(_OWORD *)&gServiceStatus.dwWin32ExitCode = 0;
  try
  {
    ghServiceHandle = (SERVICE_STATUS_HANDLE)a3();
    if ( !ghServiceHandle )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v5);
      v7 = v6 < 0;
      if ( v6 > 0 )
      {
        v6 = (unsigned __int16)v6 | 0x80070000;
        v7 = v6 < 0;
      }
      if ( v7 )
      {
        v45 = 0;
        pExceptionObject = &ComError::`vftable';
        v46 = v6;
        v47 = 678;
        v48 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
    if ( !g_hInstance )
    {
      v50 = 0;
      v49 = &ComError::`vftable';
      v51 = -2147467259;
      v52 = 683;
      v53 = 1;
      throw (ComError *)&v49;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    EventW = CreateEventW(0, 1, 0, 0);
    auto_HANDLE<0>::operator=(&g_hServiceStopEvent, EventW);
    if ( g_hServiceStopEvent )
    {
      v11 = WPP_GLOBAL_Control;
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v9);
        v11 = WPP_GLOBAL_Control;
      }
      v12 = v10 < 0;
      if ( v10 > 0 )
      {
        v10 = (unsigned __int16)v10 | 0x80070000;
        v12 = v10 < 0;
      }
      if ( v12 )
      {
        v55 = 0;
        v54 = &ComError::`vftable';
        v56 = v10;
        v57 = 697;
        v58 = 1;
        throw (ComError *)&v54;
      }
    }
    if ( v11 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v42 = SystemTimeAsFileTime;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
        *((_QWORD *)v11 + 2),
        34,
        WPP_533829f6437c324cb0547291f5f8d64b_Traceguids,
        SystemTimeAsFileTime);
    }
    CheckIfManualStart();
    g_TestHooksEnabled = 0;
    ReportServiceStartupPhase(3);
    v13 = (CPerfMon *)operator new(0x60u);
    v42 = (struct _FILETIME)v13;
    if ( v13 )
      v14 = CPerfMon::CPerfMon(v13, L"BITS", (struct CPerfMon::_PERF_ITEM *)qword_1801444E0);
    else
      v14 = 0;
    g_pPerfMon = v14;
    if ( v14 )
      goto LABEL_36;
    DbgPrint("new failed on CPerfMon performance object\n");
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    v14 = g_pPerfMon;
    if ( g_pPerfMon )
    {
LABEL_36:
      v16 = CPerfMon::Initialize(v14, 0);
      v17 = v16;
      if ( v16 )
      {
        DbgPrint("PerfMon performance object failed to initialize 0x%x (%d)\n", v16, v16);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v17);
          v15 = WPP_GLOBAL_Control;
        }
        if ( g_pPerfMon )
        {
          CPerfMon::`scalar deleting destructor'(g_pPerfMon, v18);
          v15 = WPP_GLOBAL_Control;
        }
        g_pPerfMon = 0;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
      }
    }
    if ( v15 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v15 + 2), 37, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
    ReportServiceStartupPhase(1);
    v19 = GlobalInfo::Init();
    if ( v19 < 0 )
    {
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v19;
      v62 = 733;
      v63 = 1;
      throw (ComError *)&v59;
    }
    TickCount64 = GetTickCount64();
    v21 = g_IsManualStart != 0;
    BitsServiceStartupType = GetBitsServiceStartupType();
    if ( CTelemetry::IsEnabled(v24, v23) )
    {
      wil::details::static_lazy<CTelemetry>::get(v25, _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
      LOBYTE(v26) = v21;
      CTelemetry::ServiceStartup_(v27, BitsServiceStartupType, v26);
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
    inited = InitQmgr();
    if ( inited < 0 )
    {
      v65 = 0;
      v64 = &ComError::`vftable';
      v66 = inited;
      v67 = 741;
      v68 = 1;
      throw (ComError *)&v64;
    }
    v29 = GetTickCount64();
    v30 = GetBitsServiceStartupType();
    BitsServiceShutdownType = GetBitsServiceShutdownType();
    if ( CTelemetry::IsEnabled(v33, v32) )
    {
      wil::details::static_lazy<CTelemetry>::get(v35, _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
      CTelemetry::ServiceShutdown_(v36, BitsServiceShutdownType, v30, v29 - TickCount64);
    }
    dwLowDateTime = 0;
  }
  catch ( ComError v69 )
  {
    v42.dwLowDateTime = v71;
    ReportStartupFailure(v71);
    v69 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(&v70);
    dwLowDateTime = v42.dwLowDateTime;
  }
  ghServiceHandle = (SERVICE_STATUS_HANDLE)a3();
  if ( !ghServiceHandle )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v5);
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
    {
      v45 = 0;
      pExceptionObject = &ComError::`vftable';
      v46 = v6;
      v47 = 678;
      v48 = 1;
      throw (ComError *)&pExceptionObject;
    }
  }
  if ( !g_hInstance )
  {
    v50 = 0;
    v49 = &ComError::`vftable';
    v51 = -2147467259;
    v52 = 683;
    v53 = 1;
    throw (ComError *)&v49;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  EventW = CreateEventW(0, 1, 0, 0);
  auto_HANDLE<0>::operator=(&g_hServiceStopEvent, EventW);
  if ( g_hServiceStopEvent )
  {
    v11 = WPP_GLOBAL_Control;
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v9);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = v10 < 0;
    if ( v10 > 0 )
    {
      v10 = (unsigned __int16)v10 | 0x80070000;
      v12 = v10 < 0;
    }
    if ( v12 )
    {
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = v10;
      v57 = 697;
      v58 = 1;
      throw (ComError *)&v54;
    }
  }
  if ( v11 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
  {
    v42 = SystemTimeAsFileTime;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
      *((_QWORD *)v11 + 2),
      34,
      WPP_533829f6437c324cb0547291f5f8d64b_Traceguids,
      SystemTimeAsFileTime);
  }
}

```

## disassembly

```asm
0x18008fbfc  mov     [rsp+arg_0], rbx
0x18008fc01  mov     [rsp+arg_8], rsi
0x18008fc06  push    rdi
0x18008fc07  push    r12
0x18008fc09  push    r13
0x18008fc0b  push    r14
0x18008fc0d  push    r15
0x18008fc0f  sub     rsp, 290h
0x18008fc16  mov     rax, cs:__security_cookie
0x18008fc1d  xor     rax, rsp
0x18008fc20  mov     [rsp+2B8h+var_38], rax
0x18008fc28  mov     rdi, r8
0x18008fc2b  xor     ebx, ebx
0x18008fc2d  mov     [rsp+2B8h+var_298], bl
0x18008fc31  lea     esi, [rbx+1]
0x18008fc34  add     cs:?g_ServiceInstance@@3JA, esi; long g_ServiceInstance
0x18008fc3a  mov     cs:qword_180145538, rbx
0x18008fc41  mov     cs:WPP_MAIN_CB, rbx
0x18008fc48  mov     cs:qword_180145540, 1
0x18008fc53  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18008fc5a  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18008fc61  lea     rax, WPP_MAIN_CB
0x18008fc68  mov     cs:WPP_GLOBAL_Control, rax
0x18008fc6f  call    WppInitUm
0x18008fc74  call    ?GetRedirectionPolicy@@YA?AU_PROCESS_MITIGATION_REDIRECTION_TRUST_POLICY@@XZ; GetRedirectionPolicy(void)
0x18008fc79  mov     dword ptr [rsp+2B8h+var_290], eax
0x18008fc7d  lea     r15d, [rbx+4]
0x18008fc81  mov     r8d, r15d
0x18008fc84  lea     rdx, [rsp+2B8h+var_290]
0x18008fc89  lea     ecx, [rbx+10h]
0x18008fc8c  call    cs:__imp_SetProcessMitigationPolicy
0x18008fc92  test    eax, eax
0x18008fc94  jnz     short loc_18008FCD4
0x18008fc96  lea     r14, WPP_GLOBAL_Control
0x18008fc9d  mov     rax, cs:WPP_GLOBAL_Control
0x18008fca4  cmp     rax, r14
0x18008fca7  jz      short loc_18008FCDB
0x18008fca9  test    [rax+1Ch], r15b
0x18008fcad  jz      short loc_18008FCDB
0x18008fcaf  call    cs:__imp_GetLastError
0x18008fcb5  lea     edx, [rbx+1Fh]
0x18008fcb8  mov     r9d, eax
0x18008fcbb  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008fcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fcc9  mov     rcx, [rcx+10h]
0x18008fccd  call    WPP_SF_d
0x18008fcd2  jmp     short loc_18008FCDB
0x18008fcd4  lea     r14, WPP_GLOBAL_Control
0x18008fcdb  mov     r12d, 20h ; ' '
0x18008fce1  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, r12d; _SERVICE_STATUS gServiceStatus ...
0x18008fce8  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS gServiceStatus ...
0x18008fcf2  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1200h; _SERVICE_STATUS gServiceStatus ...
0x18008fcfc  xorps   xmm0, xmm0
0x18008fcff  movups  xmmword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS gServiceStatus ...
0x18008fd06  xor     r8d, r8d
0x18008fd09  lea     rdx, ?BITSServiceHandler@@YAKKKPEAX0@Z; BITSServiceHandler(ulong,ulong,void *,void *)
0x18008fd10  lea     rcx, ServiceName; "BITS"
0x18008fd17  mov     rax, rdi
0x18008fd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd1f  mov     cs:?ghServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ghServiceHandle
0x18008fd26  test    rax, rax
0x18008fd29  jnz     short loc_18008FDA1
0x18008fd2b  call    cs:__imp_GetLastError
0x18008fd31  mov     edi, eax
0x18008fd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd3a  cmp     rcx, r14
0x18008fd3d  jz      short loc_18008FD5B
0x18008fd3f  test    [rcx+1Ch], r15b
0x18008fd43  jz      short loc_18008FD5B
0x18008fd45  mov     edx, r12d
0x18008fd48  mov     r9d, eax
0x18008fd4b  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008fd52  mov     rcx, [rcx+10h]
0x18008fd56  call    WPP_SF_d
0x18008fd5b  test    edi, edi
0x18008fd5d  jle     short loc_18008FD6A
0x18008fd5f  movzx   edi, di
0x18008fd62  or      edi, 80070000h
0x18008fd68  test    edi, edi
0x18008fd6a  jns     short loc_18008FDA1
0x18008fd6c  xorps   xmm0, xmm0
0x18008fd6f  movups  [rsp+2B8h+var_270], xmm0
0x18008fd74  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008fd7b  mov     [rsp+2B8h+pExceptionObject], rax
0x18008fd80  mov     [rsp+2B8h+var_260], edi
0x18008fd84  mov     [rsp+2B8h+var_25C], 2A6h
0x18008fd8c  mov     [rsp+2B8h+var_258], esi
0x18008fd90  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008fd97  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x18008fd9c  call    _CxxThrowException_0
0x18008fda1  cmp     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x18008fda8  jnz     short loc_18008FDF5
0x18008fdaa  xorps   xmm0, xmm0
0x18008fdad  movups  [rsp+2B8h+var_210], xmm0
0x18008fdb5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008fdbc  mov     [rsp+2B8h+var_218], rax
0x18008fdc4  mov     [rsp+2B8h+var_200], 80004005h
0x18008fdcf  mov     [rsp+2B8h+var_1FC], 2ABh
0x18008fdda  mov     [rsp+2B8h+var_1F8], esi
0x18008fde1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008fde8  lea     rcx, [rsp+2B8h+var_218]; pExceptionObject
0x18008fdf0  call    _CxxThrowException_0
0x18008fdf5  mov     qword ptr [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18008fdfa  lea     rcx, [rsp+2B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008fdff  call    cs:__imp_GetSystemTimeAsFileTime
0x18008fe05  xor     r9d, r9d; lpName
0x18008fe08  xor     r8d, r8d; bInitialState
0x18008fe0b  mov     edx, esi; bManualReset
0x18008fe0d  xor     ecx, ecx; lpEventAttributes
0x18008fe0f  call    cs:__imp_CreateEventW
0x18008fe15  mov     rdx, rax
0x18008fe18  lea     rcx, ?g_hServiceStopEvent@@3V?$auto_HANDLE@$0A@@@A; auto_HANDLE<0> g_hServiceStopEvent
0x18008fe1f  call    ??4?$auto_HANDLE@$0A@@@QEAAAEAV0@PEAX@Z; auto_HANDLE<0>::operator=(void *)
0x18008fe24  cmp     cs:?g_hServiceStopEvent@@3V?$auto_HANDLE@$0A@@@A, rbx; auto_HANDLE<0> g_hServiceStopEvent
0x18008fe2b  jnz     loc_18008FEC2
0x18008fe31  call    cs:__imp_GetLastError
0x18008fe37  mov     edi, eax
0x18008fe39  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fe40  cmp     rcx, r14
0x18008fe43  jz      short loc_18008FE6A
0x18008fe45  test    [rcx+1Ch], r15b
0x18008fe49  jz      short loc_18008FE6A
0x18008fe4b  mov     edx, 21h ; '!'
0x18008fe50  mov     r9d, eax
0x18008fe53  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008fe5a  mov     rcx, [rcx+10h]
0x18008fe5e  call    WPP_SF_d
0x18008fe63  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fe6a  test    edi, edi
0x18008fe6c  jle     short loc_18008FE79
0x18008fe6e  movzx   edi, di
0x18008fe71  or      edi, 80070000h
0x18008fe77  test    edi, edi
0x18008fe79  jns     short loc_18008FEC9
0x18008fe7b  xorps   xmm0, xmm0
0x18008fe7e  movups  [rsp+2B8h+var_1B0], xmm0
0x18008fe86  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008fe8d  mov     [rsp+2B8h+var_1B8], rax
0x18008fe95  mov     [rsp+2B8h+var_1A0], edi
0x18008fe9c  mov     [rsp+2B8h+var_19C], 2B9h
0x18008fea7  mov     [rsp+2B8h+var_198], esi
0x18008feae  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008feb5  lea     rcx, [rsp+2B8h+var_1B8]; pExceptionObject
0x18008febd  call    _CxxThrowException_0
0x18008fec2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fec9  cmp     rcx, r14
0x18008fecc  jz      short loc_18008FEFE
0x18008fece  test    [rcx+1Ch], sil
0x18008fed2  jz      short loc_18008FEFE
0x18008fed4  mov     eax, [rsp+2B8h+SystemTimeAsFileTime.dwHighDateTime]
0x18008fed8  mov     dword ptr [rsp+2B8h+var_290+4], eax
0x18008fedc  mov     eax, [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18008fee0  mov     dword ptr [rsp+2B8h+var_290], eax
0x18008fee4  mov     edx, 22h ; '"'
0x18008fee9  mov     r9, [rsp+2B8h+var_290]
0x18008feee  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008fef5  mov     rcx, [rcx+10h]
0x18008fef9  call    WPP_SF_q
0x18008fefe  call    ?CheckIfManualStart@@YAXXZ; CheckIfManualStart(void)
0x18008ff03  mov     cs:?g_TestHooksEnabled@@3HA, ebx; int g_TestHooksEnabled
0x18008ff09  mov     ecx, 3; int
0x18008ff0e  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x18008ff13  mov     ecx, 60h ; '`'; dwBytes
0x18008ff18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008ff1d  mov     [rsp+2B8h+var_290], rax
0x18008ff22  test    rax, rax
0x18008ff25  jz      short loc_18008FF40
0x18008ff27  lea     r8, qword_1801444E0
0x18008ff2e  lea     rdx, ServiceName; "BITS"
0x18008ff35  mov     rcx, rax
0x18008ff38  call    cs:__imp_??0CPerfMon@@QEAA@PEAGPEAU_PERF_ITEM@0@@Z; CPerfMon::CPerfMon(ushort *,CPerfMon::_PERF_ITEM *)
0x18008ff3e  jmp     short loc_18008FF43
0x18008ff40  mov     rax, rbx
0x18008ff43  mov     cs:?g_pPerfMon@@3PEAVCPerfMon@@EA, rax; CPerfMon * g_pPerfMon
0x18008ff4a  test    rax, rax
0x18008ff4d  jnz     short loc_18008FF96
0x18008ff4f  lea     rcx, aNewFailedOnCpe; "new failed on CPerfMon performance obje"...
0x18008ff56  call    cs:__imp_DbgPrint
0x18008ff5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ff63  cmp     rcx, r14
0x18008ff66  jz      short loc_18008FF8A
0x18008ff68  test    [rcx+1Ch], r15b
0x18008ff6c  jz      short loc_18008FF8A
0x18008ff6e  mov     edx, 23h ; '#'
0x18008ff73  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008ff7a  mov     rcx, [rcx+10h]
0x18008ff7e  call    WPP_SF_
0x18008ff83  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ff8a  mov     rax, cs:?g_pPerfMon@@3PEAVCPerfMon@@EA; CPerfMon * g_pPerfMon
0x18008ff91  test    rax, rax
0x18008ff94  jz      short loc_180090015
0x18008ff96  xor     edx, edx
0x18008ff98  mov     rcx, rax
0x18008ff9b  call    cs:__imp_?Initialize@CPerfMon@@QEAAKH@Z; CPerfMon::Initialize(int)
0x18008ffa1  mov     edi, eax
0x18008ffa3  test    eax, eax
0x18008ffa5  jz      short loc_18009000E
0x18008ffa7  mov     r8d, eax
0x18008ffaa  mov     edx, eax
0x18008ffac  lea     rcx, aPerfmonPerform; "PerfMon performance object failed to in"...
0x18008ffb3  call    cs:__imp_DbgPrint
0x18008ffb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ffc0  cmp     rcx, r14
0x18008ffc3  jz      short loc_18008FFEA
0x18008ffc5  test    [rcx+1Ch], r15b
0x18008ffc9  jz      short loc_18008FFEA
0x18008ffcb  mov     edx, 24h ; '$'
0x18008ffd0  mov     r9d, edi
0x18008ffd3  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18008ffda  mov     rcx, [rcx+10h]
0x18008ffde  call    WPP_SF_d
0x18008ffe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ffea  mov     rax, cs:?g_pPerfMon@@3PEAVCPerfMon@@EA; CPerfMon * g_pPerfMon
0x18008fff1  test    rax, rax
0x18008fff4  jz      short loc_180090005
0x18008fff6  mov     rcx, rax; this
0x18008fff9  call    ??_GCPerfMon@@QEAAPEAXI@Z; CPerfMon::`scalar deleting destructor'(uint)
0x18008fffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180090005  mov     cs:?g_pPerfMon@@3PEAVCPerfMon@@EA, rbx; CPerfMon * g_pPerfMon
0x18009000c  jmp     short loc_180090015
0x18009000e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090015  cmp     rcx, r14
0x180090018  jz      short loc_180090035
0x18009001a  test    [rcx+1Ch], sil
0x18009001e  jz      short loc_180090035
0x180090020  mov     edx, 25h ; '%'
0x180090025  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18009002c  mov     rcx, [rcx+10h]
0x180090030  call    WPP_SF_
0x180090035  mov     ecx, esi; int
0x180090037  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x18009003c  call    ?Init@GlobalInfo@@SAJXZ; GlobalInfo::Init(void)
0x180090041  mov     ecx, eax
0x180090043  test    eax, eax
0x180090045  jns     short loc_18009008E
0x180090047  xorps   xmm0, xmm0
0x18009004a  movups  [rsp+2B8h+var_150], xmm0
0x180090052  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180090059  mov     [rsp+2B8h+var_158], rax
0x180090061  mov     [rsp+2B8h+var_140], ecx
0x180090068  mov     [rsp+2B8h+var_13C], 2DDh
0x180090073  mov     [rsp+2B8h+var_138], esi
0x18009007a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180090081  lea     rcx, [rsp+2B8h+var_158]; pExceptionObject
0x180090089  call    _CxxThrowException_0
0x18009008e  mov     [rsp+2B8h+var_298], sil
0x180090093  call    cs:__imp_GetTickCount64
0x180090099  mov     r13, rax
0x18009009c  cmp     cs:?g_IsManualStart@@3HA, ebx; int g_IsManualStart
0x1800900a2  setnz   dil
0x1800900a6  call    ?GetBitsServiceStartupType@@YA?AW4ServiceStartupType@@XZ; GetBitsServiceStartupType(void)
0x1800900ab  mov     r15d, eax
0x1800900ae  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800900b3  test    al, al
0x1800900b5  jz      short loc_1800900CE
0x1800900b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x1800900be  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x1800900c3  mov     r8b, dil
0x1800900c6  mov     edx, r15d
0x1800900c9  call    ?ServiceStartup_@CTelemetry@@QEAAXW4ServiceStartupType@@_N@Z; CTelemetry::ServiceStartup_(ServiceStartupType,bool)
0x1800900ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800900d5  cmp     rcx, r14
0x1800900d8  jz      short loc_1800900F5
0x1800900da  test    [rcx+1Ch], sil
0x1800900de  jz      short loc_1800900F5
0x1800900e0  mov     edx, 26h ; '&'
0x1800900e5  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x1800900ec  mov     rcx, [rcx+10h]
0x1800900f0  call    WPP_SF_
0x1800900f5  call    ?InitQmgr@@YAJXZ; InitQmgr(void)
0x1800900fa  mov     ecx, eax
0x1800900fc  test    eax, eax
0x1800900fe  jns     short loc_180090147
0x180090100  xorps   xmm0, xmm0
0x180090103  movups  [rsp+2B8h+var_F0], xmm0
0x18009010b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180090112  mov     [rsp+2B8h+var_F8], rax
0x18009011a  mov     [rsp+2B8h+var_E0], ecx
0x180090121  mov     [rsp+2B8h+var_DC], 2E5h
0x18009012c  mov     [rsp+2B8h+var_D8], esi
0x180090133  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18009013a  lea     rcx, [rsp+2B8h+var_F8]; pExceptionObject
0x180090142  call    _CxxThrowException_0
0x180090147  call    cs:__imp_GetTickCount64
0x18009014d  mov     rdi, rax
0x180090150  call    ?GetBitsServiceStartupType@@YA?AW4ServiceStartupType@@XZ; GetBitsServiceStartupType(void)
0x180090155  mov     r15d, eax
0x180090158  call    ?GetBitsServiceShutdownType@@YA?AW4ServiceShutdownType@@XZ; GetBitsServiceShutdownType(void)
0x18009015d  mov     r12d, eax
0x180090160  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x180090165  test    al, al
0x180090167  jz      short loc_180090186
0x180090169  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x180090170  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x180090175  sub     rdi, r13
0x180090178  mov     r9, rdi
0x18009017b  mov     r8d, r15d
0x18009017e  mov     edx, r12d
0x180090181  call    ?ServiceShutdown_@CTelemetry@@QEAAXW4ServiceShutdownType@@W4ServiceStartupType@@_K@Z; CTelemetry::ServiceShutdown_(ServiceShutdownType,ServiceStartupType,unsigned __int64)
0x180090186  mov     r15d, ebx
  ... truncated ...
```
