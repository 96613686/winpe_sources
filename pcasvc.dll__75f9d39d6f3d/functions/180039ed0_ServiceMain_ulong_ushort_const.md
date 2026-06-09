# ServiceMain(ulong,ushort const * *)

- ea: `0x180039ed0`
- end: `0x18003a1d4`
- name: `?ServiceMain@@YAXKPEAPEBG@Z`
- size: `772`
- prototype: `void __fastcall(__int64, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180012920`
- `0x18001b320`
- `0x1800294a4`
- `0x180039ed0`
- `0x18003a1dc`
- `0x18003a260`
- `0x18003a304`
- `0x18004e21c`
- `0x18007e080`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a039`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a149`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180039fbd`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180039fbd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003a13f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003a13f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180039f6a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180039f6a`

## string_xrefs

- `0x18003a187`: `Service`
- `0x18003a01c`: `ServiceMain`
- `0x18003a061`: `ServiceMain`
- `0x18003a0e8`: `ServiceMain`
- `0x180039f88`: `Failed to register service ctrl handler [%d]`
- `0x18003a176`: `Performance,ServiceInitialize,%llu`
- `0x180039ff0`: `Failed to initialize the service [%d]`
- `0x18003a14f`: `Failed to set service status [%d]`
- `0x18003a15c`: `PcapUpdateServiceStatus`
- `0x18003a05a`: `Failed to create shutdown event [%d]`
- `0x18003a0d7`: `Failed to create wait thread [%d]`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, const unsigned __int16 **a2)
{
  __int64 v2; // rcx
  unsigned __int64 v3; // rdi
  __int64 v4; // r8
  DWORD LastError; // eax
  int v6; // r8d
  const char *v7; // r9
  DWORD v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  void (*v11)(unsigned __int64, unsigned int, void *, const unsigned __int16 *, void *); // rdx
  struct _PCA_SERVICE *v12; // rcx
  void (*v13)(unsigned __int64, int, void *); // r8
  void (*v14)(unsigned __int64, unsigned int, void *, const unsigned __int16 *, void *); // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 (__fastcall *v17)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int); // rax
  unsigned __int64 v18; // rax
  __int128 v19; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-28h] BYREF

  v19 = 0;
  v3 = PcaTimeStart();
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, AE_PCA_ServiceInitialize_Start, v4, 1, v20);
  *(_QWORD *)&g_ServiceStatus.dwCurrentState = 0;
  *(_QWORD *)&g_ServiceStatus.dwServiceSpecificExitCode = 0;
  g_ServiceStatus.dwWaitHint = 0;
  g_ServiceStatus.dwServiceType = 32;
  g_ServiceStatus.dwWin32ExitCode = 0;
  g_ServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"PcaSvc", PcapServiceHandler, 0);
  if ( !g_ServiceStatusHandle )
  {
    LastError = GetLastError();
    v6 = 553;
    v7 = "Failed to register service ctrl handler [%d]";
    goto LABEL_13;
  }
  *(_QWORD *)&v19 = PcaServicePowerEvent;
  *((_QWORD *)&v19 + 1) = &g_Service;
  v8 = PowerRegisterSuspendResumeNotification(2, &v19, &g_PowerRegistration);
  if ( v8 )
  {
    v9 = "Failed to register for power notifications [%d]";
    v10 = 561;
LABEL_19:
    AslLogCallPrintf(1, (unsigned int)"ServiceMain", v10, (_DWORD)v9);
    goto LABEL_20;
  }
  PcapUpdateServiceStatus(2u);
  v8 = PcaServiceInitialize(v12, v11, v13, v14);
  if ( v8 )
  {
    v9 = "Failed to initialize the service [%d]";
    v10 = 577;
    goto LABEL_19;
  }
  if ( (unsigned int)PcapEnableRpcInterface() )
  {
    AslLogCallPrintf(1, (unsigned int)"ServiceMain", 587, (unsigned int)"Failed to enable RPC interface [%d]");
    goto LABEL_24;
  }
  g_StopEventHandle = CreateEventW(0, 1, 0, 0);
  if ( !g_StopEventHandle )
  {
    LastError = GetLastError();
    v6 = 598;
    v7 = "Failed to create shutdown event [%d]";
LABEL_13:
    v8 = LastError;
    AslLogCallPrintf(1, (unsigned int)"ServiceMain", v6, (_DWORD)v7);
    if ( !v8 )
      goto LABEL_24;
LABEL_20:
    PcapHandleServiceShutdown(0, 1u);
    g_ServiceStatus.dwWin32ExitCode = v8;
    PcapUpdateServiceStatus(1u);
    goto LABEL_24;
  }
  v17 = (__int64 (__fastcall *)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))*((_QWORD *)g_SvchostGlobalData + 24);
  if ( !v17 )
  {
    v8 = 1;
    v9 = "Failed to find svchost RegisterStopCallback [%d]";
    v10 = 604;
    goto LABEL_19;
  }
  v8 = v17(&g_WaitHandle, L"PcaSvc", g_StopEventHandle, PcapHandleServiceShutdown, 0, 8);
  if ( v8 )
  {
    v9 = "Failed to create wait thread [%d]";
    v10 = 615;
    goto LABEL_19;
  }
  *(_QWORD *)&g_ServiceStatus.dwCheckPoint = 0;
  g_ServiceStatus.dwControlsAccepted = 133;
  g_ServiceStatus.dwCurrentState = 4;
  if ( !SetServiceStatus(g_ServiceStatusHandle, &g_ServiceStatus) )
  {
    GetLastError();
    AslLogCallPrintf(1, (unsigned int)"PcapUpdateServiceStatus", 309, (unsigned int)"Failed to set service status [%d]");
  }
  v18 = PcaTimeStart();
  PcaTracePrintf("Service", 0, 0, "Performance,ServiceInitialize,%llu", v18 - v3);
LABEL_24:
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v15, AE_PCA_ServiceInitialize_Stop, v16, 1, v20);
}

```

## disassembly

```asm
0x180039ed0  mov     [rsp+arg_0], rbx
0x180039ed5  mov     [rsp+arg_8], rsi
0x180039eda  push    rdi
0x180039edb  sub     rsp, 70h
0x180039edf  mov     rax, cs:__security_cookie
0x180039ee6  xor     rax, rsp
0x180039ee9  mov     [rsp+78h+var_18], rax
0x180039eee  xorps   xmm0, xmm0
0x180039ef1  movups  [rsp+78h+var_38], xmm0
0x180039ef6  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x180039efb  mov     esi, 1
0x180039f00  mov     rdi, rax
0x180039f03  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, sil
0x180039f0a  jz      short loc_180039F25
0x180039f0c  lea     rax, [rsp+78h+var_28]
0x180039f11  mov     r9d, esi
0x180039f14  lea     rdx, AE_PCA_ServiceInitialize_Start
0x180039f1b  mov     [rsp+78h+var_58], rax
0x180039f20  call    McGenEventWrite_EventWriteTransfer
0x180039f25  xor     r8d, r8d; lpContext
0x180039f28  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180039f33  lea     rdx, ?PcapServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180039f3a  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180039f45  lea     rcx, Annotation; "PcaSvc"
0x180039f4c  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180039f56  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x180039f60  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180039f6a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180039f70  mov     cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceStatusHandle
0x180039f77  test    rax, rax
0x180039f7a  jnz     short loc_180039F94
0x180039f7c  call    cs:__imp_GetLastError
0x180039f82  mov     r8d, 229h
0x180039f88  lea     r9, aFailedToRegist_0; "Failed to register service ctrl handler"...
0x180039f8f  jmp     loc_18003A061
0x180039f94  lea     rax, ?PcaServicePowerEvent@@YAKPEAXK0@Z; PcaServicePowerEvent(void *,ulong,void *)
0x180039f9b  mov     ecx, 2
0x180039fa0  mov     qword ptr [rsp+78h+var_38], rax
0x180039fa5  lea     r8, ?g_PowerRegistration@@3PEAXEA; void * g_PowerRegistration
0x180039fac  lea     rax, ?g_Service@@3U_PCA_SERVICE@@A; _PCA_SERVICE g_Service
0x180039fb3  lea     rdx, [rsp+78h+var_38]
0x180039fb8  mov     qword ptr [rsp+78h+var_38+8], rax
0x180039fbd  call    cs:__imp_PowerRegisterSuspendResumeNotification
0x180039fc3  mov     ebx, eax
0x180039fc5  test    eax, eax
0x180039fc7  jz      short loc_180039FDB
0x180039fc9  lea     r9, aFailedToRegist_4; "Failed to register for power notificati"...
0x180039fd0  mov     r8d, 231h
0x180039fd6  jmp     loc_18003A0E4
0x180039fdb  mov     ecx, 2; unsigned int
0x180039fe0  call    ?PcapUpdateServiceStatus@@YAXK@Z; PcapUpdateServiceStatus(ulong)
0x180039fe5  call    ?PcaServiceInitialize@@YAKPEAU_PCA_SERVICE@@@Z; PcaServiceInitialize(_PCA_SERVICE *)
0x180039fea  mov     ebx, eax
0x180039fec  test    eax, eax
0x180039fee  jz      short loc_18003A002
0x180039ff0  lea     r9, aFailedToInitia_23; "Failed to initialize the service [%d]"
0x180039ff7  mov     r8d, 241h
0x180039ffd  jmp     loc_18003A0E4
0x18003a002  call    ?PcapEnableRpcInterface@@YAJXZ; PcapEnableRpcInterface(void)
0x18003a007  test    eax, eax
0x18003a009  jz      short loc_18003A02F
0x18003a00b  lea     r9, aFailedToEnable_0; "Failed to enable RPC interface [%d]"
0x18003a012  mov     dword ptr [rsp+78h+var_58], eax
0x18003a016  mov     r8d, 24Bh
0x18003a01c  lea     rdx, aServicemain_0; "ServiceMain"
0x18003a023  mov     ecx, esi
0x18003a025  call    AslLogCallPrintf
0x18003a02a  jmp     loc_18003A193
0x18003a02f  xor     r9d, r9d; lpName
0x18003a032  xor     r8d, r8d; bInitialState
0x18003a035  mov     edx, esi; bManualReset
0x18003a037  xor     ecx, ecx; lpEventAttributes
0x18003a039  call    cs:__imp_CreateEventW
0x18003a03f  mov     cs:?g_StopEventHandle@@3PEAXEA, rax; void * g_StopEventHandle
0x18003a046  mov     r8, rax
0x18003a049  test    rax, rax
0x18003a04c  jnz     short loc_18003A07E
0x18003a04e  call    cs:__imp_GetLastError
0x18003a054  mov     r8d, 256h
0x18003a05a  lea     r9, aFailedToCreate_56; "Failed to create shutdown event [%d]"
0x18003a061  lea     rdx, aServicemain_0; "ServiceMain"
0x18003a068  mov     ecx, esi
0x18003a06a  mov     ebx, eax
0x18003a06c  mov     dword ptr [rsp+78h+var_58], eax
0x18003a070  call    AslLogCallPrintf
0x18003a075  test    ebx, ebx
0x18003a077  jnz     short loc_18003A0F6
0x18003a079  jmp     loc_18003A193
0x18003a07e  mov     rax, cs:?g_SvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_SvchostGlobalData
0x18003a085  mov     rax, [rax+0C0h]
0x18003a08c  test    rax, rax
0x18003a08f  jnz     short loc_18003A0A6
0x18003a091  mov     ebx, esi
0x18003a093  mov     dword ptr [rsp+78h+var_58], esi
0x18003a097  lea     r9, aFailedToFindSv; "Failed to find svchost RegisterStopCall"...
0x18003a09e  mov     r8d, 25Ch
0x18003a0a4  jmp     short loc_18003A0E8
0x18003a0a6  mov     [rsp+78h+var_50], 8
0x18003a0ae  lea     r9, ?PcapHandleServiceShutdown@@YAXPEAXE@Z; PcapHandleServiceShutdown(void *,uchar)
0x18003a0b5  lea     rdx, Annotation; "PcaSvc"
0x18003a0bc  mov     [rsp+78h+var_58], 0
0x18003a0c5  lea     rcx, ?g_WaitHandle@@3PEAXEA; void * g_WaitHandle
0x18003a0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0d1  mov     ebx, eax
0x18003a0d3  test    eax, eax
0x18003a0d5  jz      short loc_18003A112
0x18003a0d7  lea     r9, aFailedToCreate_52; "Failed to create wait thread [%d]"
0x18003a0de  mov     r8d, 267h
0x18003a0e4  mov     dword ptr [rsp+78h+var_58], eax
0x18003a0e8  lea     rdx, aServicemain_0; "ServiceMain"
0x18003a0ef  mov     ecx, esi
0x18003a0f1  call    AslLogCallPrintf
0x18003a0f6  mov     dl, sil; unsigned __int8
0x18003a0f9  xor     ecx, ecx; void *
0x18003a0fb  call    ?PcapHandleServiceShutdown@@YAXPEAXE@Z; PcapHandleServiceShutdown(void *,uchar)
0x18003a100  mov     ecx, esi; unsigned int
0x18003a102  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x18003a108  call    ?PcapUpdateServiceStatus@@YAXK@Z; PcapUpdateServiceStatus(ulong)
0x18003a10d  jmp     loc_18003A193
0x18003a112  mov     rcx, cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18003a119  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18003a120  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x18003a12b  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 85h; _SERVICE_STATUS g_ServiceStatus ...
0x18003a135  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_ServiceStatus ...
0x18003a13f  call    cs:__imp_SetServiceStatus
0x18003a145  test    eax, eax
0x18003a147  jnz     short loc_18003A16E
0x18003a149  call    cs:__imp_GetLastError
0x18003a14f  lea     r9, aFailedToSetSer; "Failed to set service status [%d]"
0x18003a156  mov     r8d, 135h
0x18003a15c  lea     rdx, aPcapupdateserv; "PcapUpdateServiceStatus"
0x18003a163  mov     dword ptr [rsp+78h+var_58], eax
0x18003a167  mov     ecx, esi
0x18003a169  call    AslLogCallPrintf
0x18003a16e  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x18003a173  sub     rax, rdi
0x18003a176  lea     r9, aPerformanceSer; "Performance,ServiceInitialize,%llu"
0x18003a17d  xor     r8d, r8d; unsigned int
0x18003a180  mov     [rsp+78h+var_58], rax
0x18003a185  xor     edx, edx; unsigned int
0x18003a187  lea     rcx, aService; "Service"
0x18003a18e  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x18003a193  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, sil
0x18003a19a  jz      short loc_18003A1B5
0x18003a19c  lea     rax, [rsp+78h+var_28]
0x18003a1a1  mov     r9d, esi
0x18003a1a4  lea     rdx, AE_PCA_ServiceInitialize_Stop
0x18003a1ab  mov     [rsp+78h+var_58], rax
0x18003a1b0  call    McGenEventWrite_EventWriteTransfer
0x18003a1b5  mov     rcx, [rsp+78h+var_18]
0x18003a1ba  xor     rcx, rsp; StackCookie
0x18003a1bd  call    __security_check_cookie
0x18003a1c2  lea     r11, [rsp+78h+var_8]
0x18003a1c7  mov     rbx, [r11+10h]
0x18003a1cb  mov     rsi, [r11+18h]
0x18003a1cf  mov     rsp, r11
0x18003a1d2  pop     rdi
0x18003a1d3  retn
```
