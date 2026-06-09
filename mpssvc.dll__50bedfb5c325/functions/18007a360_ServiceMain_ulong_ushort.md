# ServiceMain(ulong,ushort * *)

- ea: `0x18007a360`
- end: `0x18007a90e`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `1454`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x1800508b4`
- `0x18005da20`
- `0x180061c90`
- `0x18006a710`
- `0x180074b28`
- `0x1800780a4`
- `0x180078770`
- `0x180078b30`
- `0x180078c1c`
- `0x18007a360`
- `0x18007cfa0`
- `0x18007e928`
- `0x1800ec010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18007a3c5`
- `ntdll!EtwEventWrite` at `0x18007a8d4`
- `ntdll!EtwEventWrite` at `0x18007a3c5`
- `ntdll!EtwEventWrite` at `0x18007a8d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a7bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a48b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a48b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7da`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x18007a3a0`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x18007a3a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a8af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a8af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a535`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a58f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a535`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a58f`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18007a5ea`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18007a5ea`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007a439`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007a439`
- `ext-ms-win-networking-mpssvc-l1-1-0!FirewallRuleForDevModeEnabled` at `0x18007a62a`
- `ext-ms-win-networking-mpssvc-l1-1-0!FirewallRuleForDevModeEnabled` at `0x18007a62a`
- `fwbase!FwHResultToWindowsError` at `0x18007a875`
- `fwbase!FwHResultToWindowsError` at `0x18007a875`
- `fwbase!FwReportErrorAsWinError` at `0x18007a46e`
- `fwbase!FwReportErrorAsWinError` at `0x18007a46e`
- `fwbase!FwReportReturnError` at `0x18007a4e4`
- `fwbase!FwReportReturnError` at `0x18007a4e4`
- `fwbase!FwCriticalSectionCreate` at `0x18007a519`
- `fwbase!FwCriticalSectionCreate` at `0x18007a519`

## string_xrefs

- `0x18007a84a`: `mpssvc.dll`
- `0x18007a3df`: `RegisterServiceCtrlHandlerEx`
- `0x18007a45d`: `RegisterServiceCtrlHandlerW`
- `0x18007a467`: `ServiceMain`
- `0x18007a4dd`: `ServiceMain`
- `0x18007a4d4`: `FwCreateCancelableRWLock`
- `0x18007a4fc`: `FwCreateCancelableLock`
- `0x18007a54d`: `CreateEventW`
- `0x18007a560`: `CreateEventW`
- `0x18007a57c`: `FwServiceChangeState`
- `0x18007a6b9`: `FwComponentsInitialize(FW_SYNC_COMPONENTS)`
- `0x18007a7d3`: `CreateThread(FwServiceAsyncStartupRoutine)`
- `0x18007a7e6`: `CreateThread`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  const char *v2; // rdi
  DWORD LastError; // eax
  const char *v4; // rdx
  signed int v5; // ebx
  int CancelableRWLock; // eax
  __int64 v7; // rdx
  int CancelableLock; // eax
  HANDLE EventW; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  const char *v17; // [rsp+80h] [rbp+18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  WerSetFlags(2u);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Start_Begin, 0, 0);
  v2 = "RegisterServiceCtrlHandlerEx";
  _InterlockedExchange(&gFwInitializing, 1);
  _InterlockedExchange(&gFwShuttingdown, 0);
  bShutdownCallbackRegistered = 0;
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwWaitHint = 30000;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"MPSSVC", FwServiceHandler, 0);
  if ( hServiceStatus )
  {
    if ( !qword_180132158 )
    {
      LastError = GetLastError();
      v4 = "RegisterStopCallback";
      goto LABEL_8;
    }
    qword_180132128 = (__int64)&qword_180132120;
    qword_180132120 = (__int64)&qword_180132120;
    CancelableRWLock = FwCreateCancelableRWLock(&Handles);
    v5 = CancelableRWLock;
    if ( CancelableRWLock > 0 )
      v5 = (unsigned __int16)CancelableRWLock | 0x80070000;
    if ( v5 < 0 )
    {
      v2 = "FwCreateCancelableRWLock";
LABEL_15:
      v7 = (unsigned int)v5;
LABEL_16:
      FwReportReturnError("ServiceMain", v7);
      goto LABEL_60;
    }
    v2 = "FwCreateCancelableLock";
    CancelableLock = FwCreateCancelableLock((struct _tag_FW_CANCELABLE_LOCK *)&gFwMain);
    v5 = CancelableLock;
    if ( CancelableLock < 0
      || (CancelableLock = FwCriticalSectionCreate(qword_1801320C8), v5 = CancelableLock, CancelableLock < 0) )
    {
LABEL_18:
      v7 = (unsigned int)CancelableLock;
      goto LABEL_16;
    }
    qword_180132150 = CreateEventW(0, 0, 0, 0);
    if ( !qword_180132150 )
    {
LABEL_21:
      v2 = "CreateEventW";
      LastError = GetLastError();
      v4 = "CreateEventW";
      goto LABEL_8;
    }
    CancelableLock = FwServiceChangeState(2u);
    v5 = CancelableLock;
    if ( CancelableLock < 0 )
    {
      v2 = "FwServiceChangeState";
      goto LABEL_18;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    qword_180132130 = EventW;
    if ( !EventW )
      goto LABEL_21;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
      EventW = qword_180132130;
    }
    WaitHandle = (HANDLE)RegisterWaitForSingleObjectEx(EventW, FwServiceOnControl, 0, 0xFFFFFFFFLL, 0);
    if ( !WaitHandle )
    {
      v2 = "RegisterWaitForSingleObjectEx";
      LastError = GetLastError();
      v4 = "RegisterWaitForSingleObject";
      goto LABEL_8;
    }
    if ( (unsigned __int8)IsFirewallRuleForDevModeEnabledPresent() )
    {
      byte_180132168 = FirewallRuleForDevModeEnabled();
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v11 = 22;
LABEL_37:
          WPP_SF_(*(_QWORD *)(v10 + 16), v11, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
          v10 = WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        goto LABEL_38;
      }
    }
    else
    {
      byte_180132168 = 0;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v11 = 23;
          goto LABEL_37;
        }
LABEL_38:
        if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(v10 + 16), 24, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
      }
    }
    CancelableLock = FwComponentsInitialize(5, off_1800ED410);
    v5 = CancelableLock;
    if ( CancelableLock >= 0 )
    {
      byte_180132140 = 1;
      v12 = ((__int64 (__fastcall *)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))qword_180132158)(
              &qword_180132160,
              L"MPSSVC",
              qword_180132150,
              FwServiceOnShutdownCallback,
              0,
              8);
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      else
        v5 = v12;
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          25,
          WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
          (unsigned int)v12);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v5 >= 0 )
      {
        bShutdownCallbackRegistered = 1;
        if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v13 + 28) & 4) != 0 )
          {
            WPP_SF_(*(_QWORD *)(v13 + 16), 26, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
            v13 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 4) != 0 )
            WPP_SF_(*(_QWORD *)(v13 + 16), 27, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
        }
        hObject = CreateThread(0, 0, FwServiceAsyncStartupRoutine, 0, 0, 0);
        if ( hObject )
        {
          v2 = 0;
          goto LABEL_60;
        }
        v2 = "CreateThread(FwServiceAsyncStartupRoutine)";
        LastError = GetLastError();
        v4 = "CreateThread";
        goto LABEL_8;
      }
      v2 = "SvchostRegStopCallback";
      goto LABEL_15;
    }
    v2 = "FwComponentsInitialize(FW_SYNC_COMPONENTS)";
    goto LABEL_18;
  }
  LastError = GetLastError();
  v4 = "RegisterServiceCtrlHandlerW";
LABEL_8:
  v5 = FwReportErrorAsWinError("ServiceMain", v4, LastError);
LABEL_60:
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    v17 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&v17,
      (unsigned int)&dword_18011438C,
      v14,
      v15,
      (__int64)&v17);
  }
  if ( v5 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(
      "mpssvc.dll",
      (unsigned int)bShutdownCallbackRegistered,
      (unsigned __int8)byte_180132140);
    _InterlockedCompareExchange(&gFwInitializing, 0, 1);
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = FwHResultToWindowsError((unsigned int)v5);
    v16 = FwServiceSetStatus();
    FwAuditLogGenericError(0x13A6u, v16);
    if ( bShutdownCallbackRegistered )
      SetEvent(qword_180132150);
    else
      FwServiceShutdown();
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_Start_End, 0, 0);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
}

```

## disassembly

```asm
0x18007a360  push    rbx
0x18007a362  push    rbp
0x18007a363  push    rdi
0x18007a364  push    r15
0x18007a366  sub     rsp, 48h
0x18007a36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a371  lea     rbp, WPP_GLOBAL_Control
0x18007a378  lea     r15, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x18007a37f  cmp     rcx, rbp
0x18007a382  jz      short loc_18007A39B
0x18007a384  test    byte ptr [rcx+1Ch], 8
0x18007a388  jz      short loc_18007A39B
0x18007a38a  mov     rcx, [rcx+10h]
0x18007a38e  mov     edx, 14h
0x18007a393  mov     r8, r15
0x18007a396  call    WPP_SF_
0x18007a39b  mov     ecx, 2; dwFlags
0x18007a3a0  call    cs:__imp_WerSetFlags
0x18007a3a7  nop     dword ptr [rax+rax+00h]
0x18007a3ac  mov     rcx, cs:g_Provider
0x18007a3b3  test    rcx, rcx
0x18007a3b6  jz      short loc_18007A3D1
0x18007a3b8  xor     r9d, r9d
0x18007a3bb  lea     rdx, MPS_SVC_Start_Begin
0x18007a3c2  xor     r8d, r8d
0x18007a3c5  call    cs:__imp_EtwEventWrite
0x18007a3cc  nop     dword ptr [rax+rax+00h]
0x18007a3d1  xor     ecx, ecx
0x18007a3d3  lea     rdx, ?FwServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18007a3da  mov     eax, 1
0x18007a3df  lea     rdi, aRegisterservic_1; "RegisterServiceCtrlHandlerEx"
0x18007a3e6  xchg    eax, cs:?gFwInitializing@@3HC; int volatile gFwInitializing
0x18007a3ec  xchg    ecx, cs:?gFwShuttingdown@@3HC; int volatile gFwShuttingdown
0x18007a3f2  lea     rcx, ServiceName; "MPSSVC"
0x18007a3f9  mov     cs:?bShutdownCallbackRegistered@@3HA, 0; int bShutdownCallbackRegistered
0x18007a403  xor     r8d, r8d; lpContext
0x18007a406  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18007a410  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x18007a41b  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x18007a425  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18007a42f  mov     cs:ServiceStatus.dwWin32ExitCode, 0
0x18007a439  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18007a440  nop     dword ptr [rax+rax+00h]
0x18007a445  mov     cs:hServiceStatus, rax
0x18007a44c  test    rax, rax
0x18007a44f  jnz     short loc_18007A481
0x18007a451  call    cs:__imp_GetLastError
0x18007a458  nop     dword ptr [rax+rax+00h]
0x18007a45d  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerW"
0x18007a464  mov     r8d, eax
0x18007a467  lea     rcx, aServicemain_0; "ServiceMain"
0x18007a46e  call    cs:__imp_FwReportErrorAsWinError
0x18007a475  nop     dword ptr [rax+rax+00h]
0x18007a47a  mov     ebx, eax
0x18007a47c  jmp     loc_18007A7F4
0x18007a481  cmp     cs:qword_180132158, 0
0x18007a489  jnz     short loc_18007A4A0
0x18007a48b  call    cs:__imp_GetLastError
0x18007a492  nop     dword ptr [rax+rax+00h]
0x18007a497  lea     rdx, aRegisterstopca; "RegisterStopCallback"
0x18007a49e  jmp     short loc_18007A464
0x18007a4a0  lea     rax, qword_180132120
0x18007a4a7  lea     rcx, Handles; void *
0x18007a4ae  mov     cs:qword_180132128, rax
0x18007a4b5  mov     cs:qword_180132120, rax
0x18007a4bc  call    FwCreateCancelableRWLock
0x18007a4c1  mov     ebx, eax
0x18007a4c3  test    eax, eax
0x18007a4c5  jle     short loc_18007A4D0
0x18007a4c7  movzx   ebx, ax
0x18007a4ca  or      ebx, 80070000h
0x18007a4d0  test    ebx, ebx
0x18007a4d2  jns     short loc_18007A4F5
0x18007a4d4  lea     rdi, aFwcreatecancel; "FwCreateCancelableRWLock"
0x18007a4db  mov     edx, ebx
0x18007a4dd  lea     rcx, aServicemain_0; "ServiceMain"
0x18007a4e4  call    cs:__imp_FwReportReturnError
0x18007a4eb  nop     dword ptr [rax+rax+00h]
0x18007a4f0  jmp     loc_18007A7F4
0x18007a4f5  lea     rcx, ?gFwMain@@3UFW_MAIN_COMPONENT@@A; struct _tag_FW_CANCELABLE_LOCK *
0x18007a4fc  lea     rdi, aFwcreatecancel_0; "FwCreateCancelableLock"
0x18007a503  call    ?FwCreateCancelableLock@@YAJPEAU_tag_FW_CANCELABLE_LOCK@@@Z; FwCreateCancelableLock(_tag_FW_CANCELABLE_LOCK *)
0x18007a508  mov     ebx, eax
0x18007a50a  test    eax, eax
0x18007a50c  jns     short loc_18007A512
0x18007a50e  mov     edx, eax
0x18007a510  jmp     short loc_18007A4DD
0x18007a512  lea     rcx, qword_1801320C8
0x18007a519  call    cs:__imp_FwCriticalSectionCreate
0x18007a520  nop     dword ptr [rax+rax+00h]
0x18007a525  mov     ebx, eax
0x18007a527  test    eax, eax
0x18007a529  js      short loc_18007A50E
0x18007a52b  xor     r9d, r9d; lpName
0x18007a52e  xor     r8d, r8d; bInitialState
0x18007a531  xor     edx, edx; bManualReset
0x18007a533  xor     ecx, ecx; lpEventAttributes
0x18007a535  call    cs:__imp_CreateEventW
0x18007a53c  nop     dword ptr [rax+rax+00h]
0x18007a541  mov     cs:qword_180132150, rax
0x18007a548  test    rax, rax
0x18007a54b  jnz     short loc_18007A56C
0x18007a54d  lea     rdi, aCreateeventw; "CreateEventW"
0x18007a554  call    cs:__imp_GetLastError
0x18007a55b  nop     dword ptr [rax+rax+00h]
0x18007a560  lea     rdx, aCreateeventw; "CreateEventW"
0x18007a567  jmp     loc_18007A464
0x18007a56c  mov     ecx, 2; unsigned int
0x18007a571  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x18007a576  mov     ebx, eax
0x18007a578  test    eax, eax
0x18007a57a  jns     short loc_18007A585
0x18007a57c  lea     rdi, aFwservicechang; "FwServiceChangeState"
0x18007a583  jmp     short loc_18007A50E
0x18007a585  xor     r9d, r9d; lpName
0x18007a588  xor     r8d, r8d; bInitialState
0x18007a58b  xor     edx, edx; bManualReset
0x18007a58d  xor     ecx, ecx; lpEventAttributes
0x18007a58f  call    cs:__imp_CreateEventW
0x18007a596  nop     dword ptr [rax+rax+00h]
0x18007a59b  mov     cs:qword_180132130, rax
0x18007a5a2  test    rax, rax
0x18007a5a5  jz      short loc_18007A54D
0x18007a5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a5ae  cmp     rcx, rbp
0x18007a5b1  jz      short loc_18007A5D1
0x18007a5b3  test    byte ptr [rcx+1Ch], 4
0x18007a5b7  jz      short loc_18007A5D1
0x18007a5b9  mov     rcx, [rcx+10h]
0x18007a5bd  mov     edx, 15h
0x18007a5c2  mov     r8, r15
0x18007a5c5  call    WPP_SF_
0x18007a5ca  mov     rax, cs:qword_180132130
0x18007a5d1  or      r9d, 0FFFFFFFFh
0x18007a5d5  mov     [rsp+68h+dwCreationFlags], 0
0x18007a5dd  xor     r8d, r8d
0x18007a5e0  lea     rdx, ?FwServiceOnControl@@YAXPEAXE@Z; FwServiceOnControl(void *,uchar)
0x18007a5e7  mov     rcx, rax
0x18007a5ea  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18007a5f1  nop     dword ptr [rax+rax+00h]
0x18007a5f6  mov     cs:WaitHandle, rax
0x18007a5fd  test    rax, rax
0x18007a600  jnz     short loc_18007A621
0x18007a602  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x18007a609  call    cs:__imp_GetLastError
0x18007a610  nop     dword ptr [rax+rax+00h]
0x18007a615  lea     rdx, aRegisterwaitfo_0; "RegisterWaitForSingleObject"
0x18007a61c  jmp     loc_18007A464
0x18007a621  call    IsFirewallRuleForDevModeEnabledPresent
0x18007a626  test    al, al
0x18007a628  jz      short loc_18007A655
0x18007a62a  call    cs:__imp_FirewallRuleForDevModeEnabled
0x18007a631  nop     dword ptr [rax+rax+00h]
0x18007a636  mov     cs:byte_180132168, al
0x18007a63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a643  cmp     rcx, rbp
0x18007a646  jz      short loc_18007A6A2
0x18007a648  test    byte ptr [rcx+1Ch], 4
0x18007a64c  jz      short loc_18007A686
0x18007a64e  mov     edx, 16h
0x18007a653  jmp     short loc_18007A673
0x18007a655  mov     cs:byte_180132168, 0
0x18007a65c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a663  cmp     rcx, rbp
0x18007a666  jz      short loc_18007A6A2
0x18007a668  test    byte ptr [rcx+1Ch], 4
0x18007a66c  jz      short loc_18007A686
0x18007a66e  mov     edx, 17h
0x18007a673  mov     rcx, [rcx+10h]
0x18007a677  mov     r8, r15
0x18007a67a  call    WPP_SF_
0x18007a67f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a686  cmp     rcx, rbp
0x18007a689  jz      short loc_18007A6A2
0x18007a68b  test    byte ptr [rcx+1Ch], 4
0x18007a68f  jz      short loc_18007A6A2
0x18007a691  mov     rcx, [rcx+10h]
0x18007a695  mov     edx, 18h
0x18007a69a  mov     r8, r15
0x18007a69d  call    WPP_SF_
0x18007a6a2  lea     rdx, off_1800ED410
0x18007a6a9  mov     ecx, 5
0x18007a6ae  call    FwComponentsInitialize
0x18007a6b3  mov     ebx, eax
0x18007a6b5  test    eax, eax
0x18007a6b7  jns     short loc_18007A6C5
0x18007a6b9  lea     rdi, aFwcomponentsin_1; "FwComponentsInitialize(FW_SYNC_COMPONEN"...
0x18007a6c0  jmp     loc_18007A50E
0x18007a6c5  mov     r8, cs:qword_180132150
0x18007a6cc  lea     r9, ?FwServiceOnShutdownCallback@@YAXPEAXE@Z; FwServiceOnShutdownCallback(void *,uchar)
0x18007a6d3  mov     rax, cs:qword_180132158
0x18007a6da  lea     rdx, ServiceName; "MPSSVC"
0x18007a6e1  mov     dword ptr [rsp+68h+lpThreadId], 8
0x18007a6e9  lea     rcx, qword_180132160
0x18007a6f0  mov     qword ptr [rsp+68h+dwCreationFlags], 0
0x18007a6f9  mov     cs:byte_180132140, 1
0x18007a700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a705  test    eax, eax
0x18007a707  jg      short loc_18007A70D
0x18007a709  mov     ebx, eax
0x18007a70b  jmp     short loc_18007A716
0x18007a70d  movzx   ebx, ax
0x18007a710  or      ebx, 80070000h
0x18007a716  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a71d  cmp     rcx, rbp
0x18007a720  jz      short loc_18007A743
0x18007a722  test    byte ptr [rcx+1Ch], 4
0x18007a726  jz      short loc_18007A743
0x18007a728  mov     rcx, [rcx+10h]
0x18007a72c  mov     edx, 19h
0x18007a731  mov     r9d, eax
0x18007a734  mov     r8, r15
0x18007a737  call    WPP_SF_d
0x18007a73c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a743  test    ebx, ebx
0x18007a745  jns     short loc_18007A753
0x18007a747  lea     rdi, aSvchostregstop; "SvchostRegStopCallback"
0x18007a74e  jmp     loc_18007A4DB
0x18007a753  mov     cs:?bShutdownCallbackRegistered@@3HA, 1; int bShutdownCallbackRegistered
0x18007a75d  cmp     rcx, rbp
0x18007a760  jz      short loc_18007A79C
0x18007a762  test    byte ptr [rcx+1Ch], 4
0x18007a766  jz      short loc_18007A780
0x18007a768  mov     rcx, [rcx+10h]
0x18007a76c  mov     edx, 1Ah
0x18007a771  mov     r8, r15
0x18007a774  call    WPP_SF_
0x18007a779  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a780  cmp     rcx, rbp
0x18007a783  jz      short loc_18007A79C
0x18007a785  test    byte ptr [rcx+1Ch], 4
0x18007a789  jz      short loc_18007A79C
0x18007a78b  mov     rcx, [rcx+10h]
0x18007a78f  mov     edx, 1Bh
0x18007a794  mov     r8, r15
0x18007a797  call    WPP_SF_
0x18007a79c  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18007a7a5  lea     r8, ?FwServiceAsyncStartupRoutine@@YAKPEAX@Z; lpStartAddress
0x18007a7ac  xor     r9d, r9d; lpParameter
0x18007a7af  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18007a7b7  xor     edx, edx; dwStackSize
0x18007a7b9  xor     ecx, ecx; lpThreadAttributes
0x18007a7bb  call    cs:__imp_CreateThread
0x18007a7c2  nop     dword ptr [rax+rax+00h]
0x18007a7c7  mov     cs:hObject, rax
0x18007a7ce  test    rax, rax
0x18007a7d1  jnz     short loc_18007A7F2
0x18007a7d3  lea     rdi, aCreatethreadFw; "CreateThread(FwServiceAsyncStartupRouti"...
0x18007a7da  call    cs:__imp_GetLastError
0x18007a7e1  nop     dword ptr [rax+rax+00h]
0x18007a7e6  lea     rdx, aCreatethread; "CreateThread"
0x18007a7ed  jmp     loc_18007A464
0x18007a7f2  xor     edi, edi
0x18007a7f4  mov     eax, cs:dword_18012C3B0
0x18007a7fa  cmp     eax, 4
0x18007a7fd  jbe     short loc_18007A83A
0x18007a7ff  mov     rdx, 4000000000000h
0x18007a809  lea     rcx, dword_18012C3B0
0x18007a810  call    _tlgKeywordOn
0x18007a815  test    al, al
0x18007a817  jz      short loc_18007A83A
0x18007a819  lea     rcx, [rsp+68h+arg_10]
0x18007a821  mov     [rsp+68h+arg_10], rdi
0x18007a829  lea     rdx, dword_18011438C
0x18007a830  mov     qword ptr [rsp+68h+dwCreationFlags], rcx
0x18007a835  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007a83a  test    ebx, ebx
0x18007a83c  jns     loc_18007A8E0
0x18007a842  movzx   r8d, cs:byte_180132140; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(result)", "ServiceMain failed")
0x18007a84a  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18007a851  mov     edx, cs:?bShutdownCallbackRegistered@@3HA; int bShutdownCallbackRegistered
0x18007a857  call    MicrosoftTelemetryAssertTriggeredArgs
0x18007a85c  xor     ecx, ecx
0x18007a85e  lea     eax, [rcx+1]
0x18007a861  lock cmpxchg cs:?gFwInitializing@@3HC, ecx; int volatile gFwInitializing
0x18007a869  mov     ecx, ebx
0x18007a86b  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18007a875  call    cs:__imp_FwHResultToWindowsError
0x18007a87c  nop     dword ptr [rax+rax+00h]
0x18007a881  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18007a887  call    ?FwServiceSetStatus@@YAJXZ; FwServiceSetStatus(void)
0x18007a88c  mov     edx, eax; unsigned __int64
0x18007a88e  mov     ecx, 13A6h; unsigned int
0x18007a893  call    FwAuditLogGenericError
0x18007a898  cmp     cs:?bShutdownCallbackRegistered@@3HA, 0; int bShutdownCallbackRegistered
0x18007a89f  jnz     short loc_18007A8A8
0x18007a8a1  call    ?FwServiceShutdown@@YAXXZ; FwServiceShutdown(void)
0x18007a8a6  jmp     short loc_18007A8BB
0x18007a8a8  mov     rcx, cs:qword_180132150; hEvent
0x18007a8af  call    cs:__imp_SetEvent
0x18007a8b6  nop     dword ptr [rax+rax+00h]
0x18007a8bb  mov     rcx, cs:g_Provider
0x18007a8c2  test    rcx, rcx
0x18007a8c5  jz      short loc_18007A8E0
0x18007a8c7  xor     r9d, r9d
0x18007a8ca  lea     rdx, MPS_SVC_Start_End
0x18007a8d1  xor     r8d, r8d
0x18007a8d4  call    cs:__imp_EtwEventWrite
0x18007a8db  nop     dword ptr [rax+rax+00h]
0x18007a8e0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
