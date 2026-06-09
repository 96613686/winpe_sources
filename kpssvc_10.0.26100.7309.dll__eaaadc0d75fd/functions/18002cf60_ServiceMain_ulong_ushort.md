# ServiceMain(ulong,ushort * *)

- ea: `0x18002cf60`
- end: `0x18002d71d`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `1981`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180019dcc`
- `0x18001a868`
- `0x18001a958`
- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18001b1f4`
- `0x180021b10`
- `0x180029e64`
- `0x18002a080`
- `0x18002c99c`
- `0x18002cf60`
- `0x18002d8c4`
- `0x18002d904`
- `0x18002f980`
- `0x18002fd30`
- `0x18003100e`
- `0x180031040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d11f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d182`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d11f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d182`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002d0bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002d0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4af`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18002d003`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18002d003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002d554`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002d554`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002d43b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002d43b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002d494`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002d494`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002d541`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002d541`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002d1ec`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002d1ec`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d2f9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d5e8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d2f9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d5e8`
- `KERNEL32!UnregisterWait` at `0x18002d576`
- `KERNEL32!UnregisterWait` at `0x18002d576`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  ULONG64 *v2; // rbx
  const GUID **v3; // rdi
  const GUID *v4; // r8
  __int64 v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  DWORD LastError; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rdi
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  DWORD v19; // eax
  unsigned int v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  DWORD v28; // [rsp+40h] [rbp-48h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-40h] BYREF
  DWORD *v30; // [rsp+58h] [rbp-30h]
  __int64 v31; // [rsp+60h] [rbp-28h]

  v2 = (ULONG64 *)&WPP_MAIN_CB;
  qword_18003AA28 = 0;
  WPP_MAIN_CB = 0;
  v3 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_KpsDebugTraceControlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_18003AA30 = 1;
  do
  {
    v4 = *v3;
    TraceGuidReg.Guid = v4;
    ++v3;
    TraceGuidReg.RegHandle = 0;
    v2[4] = (ULONG64)v4;
    RegisterTraceGuidsW(WppControlCallback, v2, v4, 1u, &TraceGuidReg, 0, 0, v2 + 1);
    v2 = (ULONG64 *)*v2;
  }
  while ( v2 );
  McGenEventRegister_EventRegister();
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, ServiceStart, v6, 1, &TraceGuidReg);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
      WPP_SF_(v7[2], 26, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
  }
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  hMutex = CreateMutexW(0, 0, 0);
  if ( !hMutex )
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_75;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, LastError);
LABEL_74:
    v10 = WPP_GLOBAL_Control;
LABEL_75:
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = v9;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    if ( hServiceStatus )
    {
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      v10 = WPP_GLOBAL_Control;
    }
    memset_0(&KpsServiceData, 0, 0xA8u);
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
    {
      v28 = v9;
      v30 = &v28;
      v31 = 4;
      McGenEventWrite_EventWriteTransfer(v24, ServiceFailure, v25, 2, &TraceGuidReg);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
      WPP_SF_D(v10[2], 42, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v9);
    McGenEventUnregister_EventUnregister();
    KpsUnloadDebugTrace();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v9);
    return;
  }
  hEvent = CreateEventW(0, 1, 1, 0);
  if ( !hEvent )
  {
    v11 = GetLastError();
    v9 = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v11);
    goto LABEL_73;
  }
  qword_18003AD30 = CreateEventW(0, 1, 0, 0);
  if ( !qword_18003AD30 )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v12);
    goto LABEL_72;
  }
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"KPSSVC", KpsServiceCtrlHandler, 0);
  if ( !hServiceStatus )
  {
    v13 = GetLastError();
    v9 = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_71;
    v15 = 30;
    goto LABEL_35;
  }
  v13 = KpsCheckDomainJoinedMachine();
  v9 = v13;
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_71;
    v15 = 31;
    goto LABEL_35;
  }
  v13 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(KpsServiceData + 192LL))(
          &WaitHandle,
          L"KPSSVC",
          qword_18003AD30,
          KpsServiceStopCallback,
          0,
          24);
  v9 = v13;
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_71;
    v15 = 32;
LABEL_35:
    WPP_SF_D(v14[2], v15, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v13);
LABEL_71:
    CloseHandle(qword_18003AD30);
LABEL_72:
    CloseHandle(hEvent);
LABEL_73:
    CloseHandle(hMutex);
    goto LABEL_74;
  }
  ServiceStatus.dwControlsAccepted = 5;
  ServiceStatus.dwCurrentState = 4;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    v16 = GetLastError();
    v9 = v16;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_70;
    v18 = 33;
    goto LABEL_44;
  }
  v16 = KpsPerfInit();
  v9 = v16;
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_70;
    v18 = 34;
LABEL_44:
    WPP_SF_D(v17[2], v18, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v16);
LABEL_70:
    UnregisterWait(WaitHandle);
    goto LABEL_71;
  }
  v19 = KpsKerbInit();
  v9 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v19);
    goto LABEL_69;
  }
  v20 = KpsGPInit();
  v9 = v20;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v20);
    goto LABEL_68;
  }
  pcbe.Version = 3;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.Pool = 0;
  pcbe.CleanupGroup = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  ptpp = CreateThreadpool(0);
  if ( !ptpp )
  {
    v21 = GetLastError();
    v9 = v21;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v21);
    goto LABEL_67;
  }
  ptpcg = CreateThreadpoolCleanupGroup();
  if ( !ptpcg )
  {
    v22 = GetLastError();
    v9 = v22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v22);
LABEL_66:
    CloseThreadpool(ptpp);
LABEL_67:
    KpsGPShutdown();
LABEL_68:
    KpsKerbShutdown();
LABEL_69:
    KpsPerfShutdown();
    goto LABEL_70;
  }
  pcbe.Pool = ptpp;
  pcbe.CleanupGroup = ptpcg;
  pcbe.CleanupGroupCancelCallback = 0;
  v23 = KpsHttpStart();
  v9 = v23;
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v23);
    CloseThreadpoolCleanupGroup(ptpcg);
    goto LABEL_66;
  }
  v26 = KpsGPWatchRegKey();
  if ( v26 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_90;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v26);
  }
  v27 = WPP_GLOBAL_Control;
LABEL_90:
  if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 0x20) != 0 )
    WPP_SF_(v27[2], 41, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
}

```

## disassembly

```asm
0x18002cf60  mov     [rsp+arg_0], rbx
0x18002cf65  mov     [rsp+arg_8], rbp
0x18002cf6a  mov     [rsp+arg_10], rsi
0x18002cf6f  push    rdi
0x18002cf70  push    r14
0x18002cf72  push    r15
0x18002cf74  sub     rsp, 70h
0x18002cf78  mov     rax, cs:__security_cookie
0x18002cf7f  xor     rax, rsp
0x18002cf82  mov     [rsp+88h+var_20], rax
0x18002cf87  xor     esi, esi
0x18002cf89  lea     rax, WPP_ThisDir_CTLGUID_KpsDebugTraceControlGuid
0x18002cf90  lea     rbx, WPP_MAIN_CB
0x18002cf97  mov     cs:qword_18003AA28, rsi
0x18002cf9e  mov     cs:WPP_MAIN_CB, rsi
0x18002cfa5  lea     rdi, WPP_REGISTRATION_GUIDS
0x18002cfac  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18002cfb3  lea     ebp, [rsi+1]
0x18002cfb6  mov     cs:WPP_GLOBAL_Control, rbx
0x18002cfbd  mov     cs:qword_18003AA30, rbp
0x18002cfc4  mov     r8, [rdi]; ControlGuid
0x18002cfc7  lea     rax, [rbx+8]
0x18002cfcb  mov     [rsp+88h+RegistrationHandle], rax; RegistrationHandle
0x18002cfd0  lea     rcx, WppControlCallback; RequestAddress
0x18002cfd7  mov     [rsp+88h+MofResourceName], rsi; MofResourceName
0x18002cfdc  lea     rax, [rsp+88h+var_40]
0x18002cfe1  mov     [rsp+88h+var_40.Guid], r8
0x18002cfe6  lea     rdi, [rdi+8]
0x18002cfea  mov     [rsp+88h+var_40.RegHandle], rsi
0x18002cfef  mov     r9d, ebp; GuidCount
0x18002cff2  mov     [rsp+88h+MofImagePath], rsi; MofImagePath
0x18002cff7  mov     rdx, rbx; RequestContext
0x18002cffa  mov     [rsp+88h+TraceGuidReg], rax; TraceGuidReg
0x18002cfff  mov     [rbx+20h], r8
0x18002d003  call    cs:__imp_RegisterTraceGuidsW
0x18002d00a  nop     dword ptr [rax+rax+00h]
0x18002d00f  mov     rbx, [rbx]
0x18002d012  test    rbx, rbx
0x18002d015  jnz     short loc_18002CFC4
0x18002d017  call    McGenEventRegister_EventRegister
0x18002d01c  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 8
0x18002d023  jz      short loc_18002D03E
0x18002d025  lea     rax, [rsp+88h+var_40]
0x18002d02a  mov     r9d, ebp
0x18002d02d  lea     rdx, ServiceStart
0x18002d034  mov     [rsp+88h+TraceGuidReg], rax
0x18002d039  call    McGenEventWrite_EventWriteTransfer
0x18002d03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d045  lea     r14, WPP_GLOBAL_Control
0x18002d04c  lea     r15, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002d053  cmp     rcx, r14
0x18002d056  jz      short loc_18002D092
0x18002d058  test    byte ptr [rcx+1Ch], 10h
0x18002d05c  jz      short loc_18002D076
0x18002d05e  mov     rcx, [rcx+10h]
0x18002d062  mov     edx, 19h
0x18002d067  mov     r8, r15
0x18002d06a  call    WPP_SF_
0x18002d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d076  cmp     rcx, r14
0x18002d079  jz      short loc_18002D092
0x18002d07b  test    byte ptr [rcx+1Ch], 20h
0x18002d07f  jz      short loc_18002D092
0x18002d081  mov     rcx, [rcx+10h]
0x18002d085  mov     edx, 1Ah
0x18002d08a  mov     r8, r15
0x18002d08d  call    WPP_SF_
0x18002d092  xor     r8d, r8d; lpName
0x18002d095  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18002d09f  xor     edx, edx; bInitialOwner
0x18002d0a1  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x18002d0ac  xor     ecx, ecx; lpMutexAttributes
0x18002d0ae  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rsi
0x18002d0b5  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x18002d0bc  call    cs:__imp_CreateMutexW
0x18002d0c3  nop     dword ptr [rax+rax+00h]
0x18002d0c8  mov     cs:hMutex, rax
0x18002d0cf  test    rax, rax
0x18002d0d2  jnz     short loc_18002D115
0x18002d0d4  call    cs:__imp_GetLastError
0x18002d0db  nop     dword ptr [rax+rax+00h]
0x18002d0e0  mov     ebx, eax
0x18002d0e2  mov     rdi, cs:WPP_GLOBAL_Control
0x18002d0e9  cmp     rdi, r14
0x18002d0ec  jz      loc_18002D5C2
0x18002d0f2  test    [rdi+1Ch], bpl
0x18002d0f6  jz      loc_18002D5C2
0x18002d0fc  mov     rcx, [rdi+10h]
0x18002d100  mov     edx, 1Bh
0x18002d105  mov     r9d, eax
0x18002d108  mov     r8, r15
0x18002d10b  call    WPP_SF_D
0x18002d110  jmp     loc_18002D5BB
0x18002d115  xor     r9d, r9d; lpName
0x18002d118  mov     r8d, ebp; bInitialState
0x18002d11b  mov     edx, ebp; bManualReset
0x18002d11d  xor     ecx, ecx; lpEventAttributes
0x18002d11f  call    cs:__imp_CreateEventW
0x18002d126  nop     dword ptr [rax+rax+00h]
0x18002d12b  mov     cs:hEvent, rax
0x18002d132  test    rax, rax
0x18002d135  jnz     short loc_18002D178
0x18002d137  call    cs:__imp_GetLastError
0x18002d13e  nop     dword ptr [rax+rax+00h]
0x18002d143  mov     ebx, eax
0x18002d145  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d14c  cmp     rcx, r14
0x18002d14f  jz      loc_18002D5A8
0x18002d155  test    [rcx+1Ch], bpl
0x18002d159  jz      loc_18002D5A8
0x18002d15f  mov     rcx, [rcx+10h]
0x18002d163  mov     edx, 1Ch
0x18002d168  mov     r9d, eax
0x18002d16b  mov     r8, r15
0x18002d16e  call    WPP_SF_D
0x18002d173  jmp     loc_18002D5A8
0x18002d178  xor     r9d, r9d; lpName
0x18002d17b  xor     r8d, r8d; bInitialState
0x18002d17e  mov     edx, ebp; bManualReset
0x18002d180  xor     ecx, ecx; lpEventAttributes
0x18002d182  call    cs:__imp_CreateEventW
0x18002d189  nop     dword ptr [rax+rax+00h]
0x18002d18e  mov     cs:qword_18003AD30, rax
0x18002d195  test    rax, rax
0x18002d198  jnz     short loc_18002D1DB
0x18002d19a  call    cs:__imp_GetLastError
0x18002d1a1  nop     dword ptr [rax+rax+00h]
0x18002d1a6  mov     ebx, eax
0x18002d1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1af  cmp     rcx, r14
0x18002d1b2  jz      loc_18002D595
0x18002d1b8  test    [rcx+1Ch], bpl
0x18002d1bc  jz      loc_18002D595
0x18002d1c2  mov     rcx, [rcx+10h]
0x18002d1c6  mov     edx, 1Dh
0x18002d1cb  mov     r9d, eax
0x18002d1ce  mov     r8, r15
0x18002d1d1  call    WPP_SF_D
0x18002d1d6  jmp     loc_18002D595
0x18002d1db  xor     r8d, r8d; lpContext
0x18002d1de  lea     rdx, ?KpsServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18002d1e5  lea     rcx, ServiceName; "KPSSVC"
0x18002d1ec  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002d1f3  nop     dword ptr [rax+rax+00h]
0x18002d1f8  mov     cs:hServiceStatus, rax
0x18002d1ff  test    rax, rax
0x18002d202  jnz     short loc_18002D236
0x18002d204  call    cs:__imp_GetLastError
0x18002d20b  nop     dword ptr [rax+rax+00h]
0x18002d210  mov     ebx, eax
0x18002d212  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d219  cmp     rcx, r14
0x18002d21c  jz      loc_18002D582
0x18002d222  test    [rcx+1Ch], bpl
0x18002d226  jz      loc_18002D582
0x18002d22c  mov     edx, 1Eh
0x18002d231  jmp     loc_18002D2C3
0x18002d236  call    ?KpsCheckDomainJoinedMachine@@YAKXZ; KpsCheckDomainJoinedMachine(void)
0x18002d23b  mov     ebx, eax
0x18002d23d  test    eax, eax
0x18002d23f  jz      short loc_18002D262
0x18002d241  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d248  cmp     rcx, r14
0x18002d24b  jz      loc_18002D582
0x18002d251  test    [rcx+1Ch], bpl
0x18002d255  jz      loc_18002D582
0x18002d25b  mov     edx, 1Fh
0x18002d260  jmp     short loc_18002D2C3
0x18002d262  mov     rax, cs:?KpsServiceData@@3U_KPS_SERVICE_DATA@@A; _KPS_SERVICE_DATA KpsServiceData
0x18002d269  lea     r9, ?KpsServiceStopCallback@@YAXPEAXE@Z; KpsServiceStopCallback(void *,uchar)
0x18002d270  mov     r8, cs:qword_18003AD30
0x18002d277  lea     rdx, ServiceName; "KPSSVC"
0x18002d27e  mov     dword ptr [rsp+88h+MofImagePath], 18h
0x18002d286  lea     rcx, WaitHandle
0x18002d28d  mov     [rsp+88h+TraceGuidReg], rsi
0x18002d292  mov     rax, [rax+0C0h]
0x18002d299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29e  mov     ebx, eax
0x18002d2a0  test    eax, eax
0x18002d2a2  jz      short loc_18002D2D7
0x18002d2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2ab  cmp     rcx, r14
0x18002d2ae  jz      loc_18002D582
0x18002d2b4  test    [rcx+1Ch], bpl
0x18002d2b8  jz      loc_18002D582
0x18002d2be  mov     edx, 20h ; ' '
0x18002d2c3  mov     rcx, [rcx+10h]
0x18002d2c7  mov     r9d, eax
0x18002d2ca  mov     r8, r15
0x18002d2cd  call    WPP_SF_D
0x18002d2d2  jmp     loc_18002D582
0x18002d2d7  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18002d2de  lea     rdx, ServiceStatus; lpServiceStatus
0x18002d2e5  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x18002d2ef  mov     cs:ServiceStatus.dwCurrentState, 4
0x18002d2f9  call    cs:__imp_SetServiceStatus
0x18002d300  nop     dword ptr [rax+rax+00h]
0x18002d305  test    eax, eax
0x18002d307  jnz     short loc_18002D338
0x18002d309  call    cs:__imp_GetLastError
0x18002d310  nop     dword ptr [rax+rax+00h]
0x18002d315  mov     ebx, eax
0x18002d317  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d31e  cmp     rcx, r14
0x18002d321  jz      loc_18002D56F
0x18002d327  test    [rcx+1Ch], bpl
0x18002d32b  jz      loc_18002D56F
0x18002d331  mov     edx, 21h ; '!'
0x18002d336  jmp     short loc_18002D362
0x18002d338  call    ?KpsPerfInit@@YAKXZ; KpsPerfInit(void)
0x18002d33d  mov     ebx, eax
0x18002d33f  test    eax, eax
0x18002d341  jz      short loc_18002D376
0x18002d343  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d34a  cmp     rcx, r14
0x18002d34d  jz      loc_18002D56F
0x18002d353  test    [rcx+1Ch], bpl
0x18002d357  jz      loc_18002D56F
0x18002d35d  mov     edx, 22h ; '"'
0x18002d362  mov     rcx, [rcx+10h]
0x18002d366  mov     r9d, eax
0x18002d369  mov     r8, r15
0x18002d36c  call    WPP_SF_D
0x18002d371  jmp     loc_18002D56F
0x18002d376  call    ?KpsKerbInit@@YAKXZ; KpsKerbInit(void)
0x18002d37b  mov     ebx, eax
0x18002d37d  test    eax, eax
0x18002d37f  jz      short loc_18002D3B4
0x18002d381  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d388  cmp     rcx, r14
0x18002d38b  jz      loc_18002D56A
0x18002d391  test    [rcx+1Ch], bpl
0x18002d395  jz      loc_18002D56A
0x18002d39b  mov     rcx, [rcx+10h]
0x18002d39f  mov     edx, 23h ; '#'
0x18002d3a4  mov     r9d, eax
0x18002d3a7  mov     r8, r15
0x18002d3aa  call    WPP_SF_D
0x18002d3af  jmp     loc_18002D56A
0x18002d3b4  call    ?KpsGPInit@@YAKXZ; KpsGPInit(void)
0x18002d3b9  mov     ebx, eax
0x18002d3bb  test    eax, eax
0x18002d3bd  jz      short loc_18002D3F2
0x18002d3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3c6  cmp     rcx, r14
0x18002d3c9  jz      loc_18002D565
0x18002d3cf  test    [rcx+1Ch], bpl
0x18002d3d3  jz      loc_18002D565
0x18002d3d9  mov     rcx, [rcx+10h]
0x18002d3dd  mov     edx, 24h ; '$'
0x18002d3e2  mov     r9d, eax
0x18002d3e5  mov     r8, r15
0x18002d3e8  call    WPP_SF_D
0x18002d3ed  jmp     loc_18002D565
0x18002d3f2  xorps   xmm0, xmm0
0x18002d3f5  mov     cs:pcbe.Version, 3
0x18002d3ff  xor     ecx, ecx; reserved
0x18002d401  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x18002d409  mov     cs:pcbe.Pool, rsi
0x18002d410  mov     cs:pcbe.CleanupGroup, rsi
0x18002d417  mov     cs:pcbe.CleanupGroupCancelCallback, rsi
0x18002d41e  mov     cs:pcbe.FinalizationCallback, rsi
0x18002d425  mov     dword ptr cs:pcbe.u, esi
0x18002d42b  mov     cs:pcbe.CallbackPriority, ebp
0x18002d431  mov     cs:pcbe.Size, 48h ; 'H'
0x18002d43b  call    cs:__imp_CreateThreadpool
0x18002d442  nop     dword ptr [rax+rax+00h]
0x18002d447  mov     cs:ptpp, rax
0x18002d44e  test    rax, rax
0x18002d451  jnz     short loc_18002D494
0x18002d453  call    cs:__imp_GetLastError
0x18002d45a  nop     dword ptr [rax+rax+00h]
0x18002d45f  mov     ebx, eax
0x18002d461  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d468  cmp     rcx, r14
0x18002d46b  jz      loc_18002D560
0x18002d471  test    [rcx+1Ch], bpl
0x18002d475  jz      loc_18002D560
0x18002d47b  mov     rcx, [rcx+10h]
0x18002d47f  mov     edx, 25h ; '%'
0x18002d484  mov     r9d, eax
0x18002d487  mov     r8, r15
0x18002d48a  call    WPP_SF_D
0x18002d48f  jmp     loc_18002D560
0x18002d494  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002d49b  nop     dword ptr [rax+rax+00h]
0x18002d4a0  mov     cs:ptpcg, rax
0x18002d4a7  mov     rcx, rax
0x18002d4aa  test    rax, rax
0x18002d4ad  jnz     short loc_18002D4E9
0x18002d4af  call    cs:__imp_GetLastError
0x18002d4b6  nop     dword ptr [rax+rax+00h]
0x18002d4bb  mov     ebx, eax
0x18002d4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4c4  cmp     rcx, r14
0x18002d4c7  jz      loc_18002D54D
0x18002d4cd  test    [rcx+1Ch], bpl
0x18002d4d1  jz      short loc_18002D54D
0x18002d4d3  mov     rcx, [rcx+10h]
0x18002d4d7  mov     edx, 26h ; '&'
  ... truncated ...
```
