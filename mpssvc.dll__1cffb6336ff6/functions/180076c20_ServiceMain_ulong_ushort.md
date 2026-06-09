# ServiceMain(ulong,ushort * *)

- ea: `0x180076c20`
- end: `0x18007715b`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `1339`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18004d58c`
- `0x1800588e8`
- `0x18005cf9c`
- `0x1800670c0`
- `0x180071678`
- `0x180074b3c`
- `0x180075194`
- `0x180075510`
- `0x1800755e0`
- `0x180076c20`
- `0x180079360`
- `0x18007ab14`
- `0x1800e6010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180076c7f`
- `ntdll!EtwEventWrite` at `0x180077128`
- `ntdll!EtwEventWrite` at `0x180076c7f`
- `ntdll!EtwEventWrite` at `0x180077128`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180077027`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180077027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077040`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180076c60`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180076c60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180077109`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180077109`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076dc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076e13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076dc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076e13`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180076e68`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180076e68`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180076ced`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180076ced`
- `ext-ms-win-networking-mpssvc-l1-1-0!FirewallRuleForDevModeEnabled` at `0x180076e9c`
- `ext-ms-win-networking-mpssvc-l1-1-0!FirewallRuleForDevModeEnabled` at `0x180076e9c`
- `fwbase!FwHResultToWindowsError` at `0x1800770d5`
- `fwbase!FwHResultToWindowsError` at `0x1800770d5`
- `fwbase!FwReportReturnError` at `0x180076d80`
- `fwbase!FwReportReturnError` at `0x180076d80`
- `fwbase!FwCriticalSectionCreate` at `0x180076daf`
- `fwbase!FwCriticalSectionCreate` at `0x180076daf`
- `fwbase!FwReportErrorAsWinError` at `0x180076d16`
- `fwbase!FwReportErrorAsWinError` at `0x180076d16`

## string_xrefs

- `0x1800770aa`: `mpssvc.dll`
- `0x180076c93`: `RegisterServiceCtrlHandlerEx`
- `0x180076d05`: `RegisterServiceCtrlHandlerW`
- `0x180076d0f`: `ServiceMain`
- `0x180076d79`: `ServiceMain`
- `0x180076d70`: `FwCreateCancelableRWLock`
- `0x180076d92`: `FwCreateCancelableLock`
- `0x180076dd7`: `CreateEventW`
- `0x180076de4`: `CreateEventW`
- `0x180076e00`: `FwServiceChangeState`
- `0x180076f25`: `FwComponentsInitialize(FW_SYNC_COMPONENTS)`
- `0x180077039`: `CreateThread(FwServiceAsyncStartupRoutine)`
- `0x180077046`: `CreateThread`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  const char *v2; // rdi
  DWORD LastError; // eax
  const char *v4; // rdx
  signed int v5; // ebx
  int CancelableRWLock; // eax
  __int64 v7; // r8
  __int64 v8; // rdx
  int CancelableLock; // eax
  HANDLE EventW; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // eax
  const char *v18; // [rsp+80h] [rbp+18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
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
    if ( !qword_18012BF78 )
    {
      LastError = GetLastError();
      v4 = "RegisterStopCallback";
      goto LABEL_8;
    }
    qword_18012BF48 = (__int64)&qword_18012BF40;
    qword_18012BF40 = (__int64)&qword_18012BF40;
    CancelableRWLock = FwCreateCancelableRWLock(&Handles);
    v5 = CancelableRWLock;
    if ( CancelableRWLock > 0 )
      v5 = (unsigned __int16)CancelableRWLock | 0x80070000;
    if ( v5 < 0 )
    {
      v2 = "FwCreateCancelableRWLock";
LABEL_15:
      v8 = (unsigned int)v5;
LABEL_16:
      FwReportReturnError("ServiceMain", v8, v7);
      goto LABEL_60;
    }
    v2 = "FwCreateCancelableLock";
    CancelableLock = FwCreateCancelableLock((struct _tag_FW_CANCELABLE_LOCK *)&gFwMain);
    v5 = CancelableLock;
    if ( CancelableLock < 0
      || (CancelableLock = FwCriticalSectionCreate(qword_18012BEE8), v5 = CancelableLock, CancelableLock < 0) )
    {
LABEL_18:
      v8 = (unsigned int)CancelableLock;
      goto LABEL_16;
    }
    qword_18012BF70 = CreateEventW(0, 0, 0, 0);
    if ( !qword_18012BF70 )
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
    qword_18012BF50 = EventW;
    if ( !EventW )
      goto LABEL_21;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
      EventW = qword_18012BF50;
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
      byte_18012BF88 = FirewallRuleForDevModeEnabled();
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v12 = 22;
LABEL_37:
          WPP_SF_(*(_QWORD *)(v11 + 16), v12, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
          v11 = WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        goto LABEL_38;
      }
    }
    else
    {
      byte_18012BF88 = 0;
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v12 = 23;
          goto LABEL_37;
        }
LABEL_38:
        if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(v11 + 16), 24, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
      }
    }
    CancelableLock = FwComponentsInitialize(5, off_1800E74D0);
    v5 = CancelableLock;
    if ( CancelableLock >= 0 )
    {
      byte_18012BF60 = 1;
      v13 = ((__int64 (__fastcall *)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))qword_18012BF78)(
              &qword_18012BF80,
              L"MPSSVC",
              qword_18012BF70,
              FwServiceOnShutdownCallback,
              0,
              8);
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      else
        v5 = v13;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          25,
          WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
          (unsigned int)v13);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v5 >= 0 )
      {
        bShutdownCallbackRegistered = 1;
        if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v14 + 28) & 4) != 0 )
          {
            WPP_SF_(*(_QWORD *)(v14 + 16), 26, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
            v14 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 4) != 0 )
            WPP_SF_(*(_QWORD *)(v14 + 16), 27, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
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
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    v18 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)&v18,
      (int)&dword_18010E574,
      v15,
      v16,
      &v18);
  }
  if ( v5 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(
      "mpssvc.dll",
      (unsigned int)bShutdownCallbackRegistered,
      (unsigned __int8)byte_18012BF60);
    _InterlockedCompareExchange(&gFwInitializing, 0, 1);
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = FwHResultToWindowsError((unsigned int)v5);
    v17 = FwServiceSetStatus();
    FwAuditLogGenericError(0x13A6u, v17);
    if ( bShutdownCallbackRegistered )
      SetEvent(qword_18012BF70);
    else
      FwServiceShutdown();
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_Start_End, 0, 0);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
}

```

## disassembly

```asm
0x180076c20  push    rbx
0x180076c22  push    rbp
0x180076c23  push    rdi
0x180076c24  push    r15
0x180076c26  sub     rsp, 48h
0x180076c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076c31  lea     rbp, WPP_GLOBAL_Control
0x180076c38  lea     r15, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180076c3f  cmp     rcx, rbp
0x180076c42  jz      short loc_180076C5B
0x180076c44  test    byte ptr [rcx+1Ch], 8
0x180076c48  jz      short loc_180076C5B
0x180076c4a  mov     rcx, [rcx+10h]
0x180076c4e  mov     edx, 14h
0x180076c53  mov     r8, r15
0x180076c56  call    WPP_SF_
0x180076c5b  mov     ecx, 2; dwFlags
0x180076c60  call    cs:__imp_WerSetFlags
0x180076c66  mov     rcx, cs:g_Provider
0x180076c6d  test    rcx, rcx
0x180076c70  jz      short loc_180076C85
0x180076c72  xor     r9d, r9d
0x180076c75  lea     rdx, MPS_SVC_Start_Begin
0x180076c7c  xor     r8d, r8d
0x180076c7f  call    cs:__imp_EtwEventWrite
0x180076c85  xor     ecx, ecx
0x180076c87  lea     rdx, ?FwServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180076c8e  mov     eax, 1
0x180076c93  lea     rdi, aRegisterservic_1; "RegisterServiceCtrlHandlerEx"
0x180076c9a  xchg    eax, cs:?gFwInitializing@@3HC; int volatile gFwInitializing
0x180076ca0  xchg    ecx, cs:?gFwShuttingdown@@3HC; int volatile gFwShuttingdown
0x180076ca6  lea     rcx, ServiceName; "MPSSVC"
0x180076cad  mov     cs:?bShutdownCallbackRegistered@@3HA, 0; int bShutdownCallbackRegistered
0x180076cb7  xor     r8d, r8d; lpContext
0x180076cba  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180076cc4  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x180076ccf  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x180076cd9  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180076ce3  mov     cs:ServiceStatus.dwWin32ExitCode, 0
0x180076ced  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180076cf3  mov     cs:hServiceStatus, rax
0x180076cfa  test    rax, rax
0x180076cfd  jnz     short loc_180076D23
0x180076cff  call    cs:__imp_GetLastError
0x180076d05  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerW"
0x180076d0c  mov     r8d, eax
0x180076d0f  lea     rcx, aServicemain_0; "ServiceMain"
0x180076d16  call    cs:__imp_FwReportErrorAsWinError
0x180076d1c  mov     ebx, eax
0x180076d1e  jmp     loc_180077054
0x180076d23  cmp     cs:qword_18012BF78, 0
0x180076d2b  jnz     short loc_180076D3C
0x180076d2d  call    cs:__imp_GetLastError
0x180076d33  lea     rdx, aRegisterstopca; "RegisterStopCallback"
0x180076d3a  jmp     short loc_180076D0C
0x180076d3c  lea     rax, qword_18012BF40
0x180076d43  lea     rcx, Handles; void *
0x180076d4a  mov     cs:qword_18012BF48, rax
0x180076d51  mov     cs:qword_18012BF40, rax
0x180076d58  call    FwCreateCancelableRWLock
0x180076d5d  mov     ebx, eax
0x180076d5f  test    eax, eax
0x180076d61  jle     short loc_180076D6C
0x180076d63  movzx   ebx, ax
0x180076d66  or      ebx, 80070000h
0x180076d6c  test    ebx, ebx
0x180076d6e  jns     short loc_180076D8B
0x180076d70  lea     rdi, aFwcreatecancel; "FwCreateCancelableRWLock"
0x180076d77  mov     edx, ebx
0x180076d79  lea     rcx, aServicemain_0; "ServiceMain"
0x180076d80  call    cs:__imp_FwReportReturnError
0x180076d86  jmp     loc_180077054
0x180076d8b  lea     rcx, ?gFwMain@@3UFW_MAIN_COMPONENT@@A; struct _tag_FW_CANCELABLE_LOCK *
0x180076d92  lea     rdi, aFwcreatecancel_0; "FwCreateCancelableLock"
0x180076d99  call    ?FwCreateCancelableLock@@YAJPEAU_tag_FW_CANCELABLE_LOCK@@@Z; FwCreateCancelableLock(_tag_FW_CANCELABLE_LOCK *)
0x180076d9e  mov     ebx, eax
0x180076da0  test    eax, eax
0x180076da2  jns     short loc_180076DA8
0x180076da4  mov     edx, eax
0x180076da6  jmp     short loc_180076D79
0x180076da8  lea     rcx, qword_18012BEE8
0x180076daf  call    cs:__imp_FwCriticalSectionCreate
0x180076db5  mov     ebx, eax
0x180076db7  test    eax, eax
0x180076db9  js      short loc_180076DA4
0x180076dbb  xor     r9d, r9d; lpName
0x180076dbe  xor     r8d, r8d; bInitialState
0x180076dc1  xor     edx, edx; bManualReset
0x180076dc3  xor     ecx, ecx; lpEventAttributes
0x180076dc5  call    cs:__imp_CreateEventW
0x180076dcb  mov     cs:qword_18012BF70, rax
0x180076dd2  test    rax, rax
0x180076dd5  jnz     short loc_180076DF0
0x180076dd7  lea     rdi, aCreateeventw; "CreateEventW"
0x180076dde  call    cs:__imp_GetLastError
0x180076de4  lea     rdx, aCreateeventw; "CreateEventW"
0x180076deb  jmp     loc_180076D0C
0x180076df0  mov     ecx, 2; unsigned int
0x180076df5  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x180076dfa  mov     ebx, eax
0x180076dfc  test    eax, eax
0x180076dfe  jns     short loc_180076E09
0x180076e00  lea     rdi, aFwservicechang; "FwServiceChangeState"
0x180076e07  jmp     short loc_180076DA4
0x180076e09  xor     r9d, r9d; lpName
0x180076e0c  xor     r8d, r8d; bInitialState
0x180076e0f  xor     edx, edx; bManualReset
0x180076e11  xor     ecx, ecx; lpEventAttributes
0x180076e13  call    cs:__imp_CreateEventW
0x180076e19  mov     cs:qword_18012BF50, rax
0x180076e20  test    rax, rax
0x180076e23  jz      short loc_180076DD7
0x180076e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180076e2c  cmp     rcx, rbp
0x180076e2f  jz      short loc_180076E4F
0x180076e31  test    byte ptr [rcx+1Ch], 4
0x180076e35  jz      short loc_180076E4F
0x180076e37  mov     rcx, [rcx+10h]
0x180076e3b  mov     edx, 15h
0x180076e40  mov     r8, r15
0x180076e43  call    WPP_SF_
0x180076e48  mov     rax, cs:qword_18012BF50
0x180076e4f  or      r9d, 0FFFFFFFFh
0x180076e53  mov     [rsp+68h+dwCreationFlags], 0
0x180076e5b  xor     r8d, r8d
0x180076e5e  lea     rdx, ?FwServiceOnControl@@YAXPEAXE@Z; FwServiceOnControl(void *,uchar)
0x180076e65  mov     rcx, rax
0x180076e68  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180076e6e  mov     cs:WaitHandle, rax
0x180076e75  test    rax, rax
0x180076e78  jnz     short loc_180076E93
0x180076e7a  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180076e81  call    cs:__imp_GetLastError
0x180076e87  lea     rdx, aRegisterwaitfo_0; "RegisterWaitForSingleObject"
0x180076e8e  jmp     loc_180076D0C
0x180076e93  call    IsFirewallRuleForDevModeEnabledPresent
0x180076e98  test    al, al
0x180076e9a  jz      short loc_180076EC1
0x180076e9c  call    cs:__imp_FirewallRuleForDevModeEnabled
0x180076ea2  mov     cs:byte_18012BF88, al
0x180076ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180076eaf  cmp     rcx, rbp
0x180076eb2  jz      short loc_180076F0E
0x180076eb4  test    byte ptr [rcx+1Ch], 4
0x180076eb8  jz      short loc_180076EF2
0x180076eba  mov     edx, 16h
0x180076ebf  jmp     short loc_180076EDF
0x180076ec1  mov     cs:byte_18012BF88, 0
0x180076ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ecf  cmp     rcx, rbp
0x180076ed2  jz      short loc_180076F0E
0x180076ed4  test    byte ptr [rcx+1Ch], 4
0x180076ed8  jz      short loc_180076EF2
0x180076eda  mov     edx, 17h
0x180076edf  mov     rcx, [rcx+10h]
0x180076ee3  mov     r8, r15
0x180076ee6  call    WPP_SF_
0x180076eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ef2  cmp     rcx, rbp
0x180076ef5  jz      short loc_180076F0E
0x180076ef7  test    byte ptr [rcx+1Ch], 4
0x180076efb  jz      short loc_180076F0E
0x180076efd  mov     rcx, [rcx+10h]
0x180076f01  mov     edx, 18h
0x180076f06  mov     r8, r15
0x180076f09  call    WPP_SF_
0x180076f0e  lea     rdx, off_1800E74D0
0x180076f15  mov     ecx, 5
0x180076f1a  call    FwComponentsInitialize
0x180076f1f  mov     ebx, eax
0x180076f21  test    eax, eax
0x180076f23  jns     short loc_180076F31
0x180076f25  lea     rdi, aFwcomponentsin_1; "FwComponentsInitialize(FW_SYNC_COMPONEN"...
0x180076f2c  jmp     loc_180076DA4
0x180076f31  mov     r8, cs:qword_18012BF70
0x180076f38  lea     r9, ?FwServiceOnShutdownCallback@@YAXPEAXE@Z; FwServiceOnShutdownCallback(void *,uchar)
0x180076f3f  mov     rax, cs:qword_18012BF78
0x180076f46  lea     rdx, ServiceName; "MPSSVC"
0x180076f4d  mov     dword ptr [rsp+68h+lpThreadId], 8
0x180076f55  lea     rcx, qword_18012BF80
0x180076f5c  mov     qword ptr [rsp+68h+dwCreationFlags], 0
0x180076f65  mov     cs:byte_18012BF60, 1
0x180076f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f71  test    eax, eax
0x180076f73  jg      short loc_180076F79
0x180076f75  mov     ebx, eax
0x180076f77  jmp     short loc_180076F82
0x180076f79  movzx   ebx, ax
0x180076f7c  or      ebx, 80070000h
0x180076f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f89  cmp     rcx, rbp
0x180076f8c  jz      short loc_180076FAF
0x180076f8e  test    byte ptr [rcx+1Ch], 4
0x180076f92  jz      short loc_180076FAF
0x180076f94  mov     rcx, [rcx+10h]
0x180076f98  mov     edx, 19h
0x180076f9d  mov     r9d, eax
0x180076fa0  mov     r8, r15
0x180076fa3  call    WPP_SF_d
0x180076fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180076faf  test    ebx, ebx
0x180076fb1  jns     short loc_180076FBF
0x180076fb3  lea     rdi, aSvchostregstop; "SvchostRegStopCallback"
0x180076fba  jmp     loc_180076D77
0x180076fbf  mov     cs:?bShutdownCallbackRegistered@@3HA, 1; int bShutdownCallbackRegistered
0x180076fc9  cmp     rcx, rbp
0x180076fcc  jz      short loc_180077008
0x180076fce  test    byte ptr [rcx+1Ch], 4
0x180076fd2  jz      short loc_180076FEC
0x180076fd4  mov     rcx, [rcx+10h]
0x180076fd8  mov     edx, 1Ah
0x180076fdd  mov     r8, r15
0x180076fe0  call    WPP_SF_
0x180076fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180076fec  cmp     rcx, rbp
0x180076fef  jz      short loc_180077008
0x180076ff1  test    byte ptr [rcx+1Ch], 4
0x180076ff5  jz      short loc_180077008
0x180076ff7  mov     rcx, [rcx+10h]
0x180076ffb  mov     edx, 1Bh
0x180077000  mov     r8, r15
0x180077003  call    WPP_SF_
0x180077008  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x180077011  lea     r8, ?FwServiceAsyncStartupRoutine@@YAKPEAX@Z; lpStartAddress
0x180077018  xor     r9d, r9d; lpParameter
0x18007701b  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180077023  xor     edx, edx; dwStackSize
0x180077025  xor     ecx, ecx; lpThreadAttributes
0x180077027  call    cs:__imp_CreateThread
0x18007702d  mov     cs:hObject, rax
0x180077034  test    rax, rax
0x180077037  jnz     short loc_180077052
0x180077039  lea     rdi, aCreatethreadFw; "CreateThread(FwServiceAsyncStartupRouti"...
0x180077040  call    cs:__imp_GetLastError
0x180077046  lea     rdx, aCreatethread; "CreateThread"
0x18007704d  jmp     loc_180076D0C
0x180077052  xor     edi, edi
0x180077054  mov     eax, cs:dword_1801263B0
0x18007705a  cmp     eax, 4
0x18007705d  jbe     short loc_18007709A
0x18007705f  mov     rdx, 4000000000000h
0x180077069  lea     rcx, dword_1801263B0
0x180077070  call    _tlgKeywordOn
0x180077075  test    al, al
0x180077077  jz      short loc_18007709A
0x180077079  lea     rcx, [rsp+68h+arg_10]
0x180077081  mov     [rsp+68h+arg_10], rdi
0x180077089  lea     rdx, dword_18010E574
0x180077090  mov     qword ptr [rsp+68h+dwCreationFlags], rcx
0x180077095  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007709a  test    ebx, ebx
0x18007709c  jns     loc_18007712E
0x1800770a2  movzx   r8d, cs:byte_18012BF60
0x1800770aa  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800770b1  mov     edx, cs:?bShutdownCallbackRegistered@@3HA; int bShutdownCallbackRegistered
0x1800770b7  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800770bc  xor     ecx, ecx
0x1800770be  lea     eax, [rcx+1]
0x1800770c1  lock cmpxchg cs:?gFwInitializing@@3HC, ecx; int volatile gFwInitializing
0x1800770c9  mov     ecx, ebx
0x1800770cb  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x1800770d5  call    cs:__imp_FwHResultToWindowsError
0x1800770db  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x1800770e1  call    ?FwServiceSetStatus@@YAJXZ; FwServiceSetStatus(void)
0x1800770e6  mov     edx, eax; unsigned __int64
0x1800770e8  mov     ecx, 13A6h; unsigned int
0x1800770ed  call    FwAuditLogGenericError
0x1800770f2  cmp     cs:?bShutdownCallbackRegistered@@3HA, 0; int bShutdownCallbackRegistered
0x1800770f9  jnz     short loc_180077102
0x1800770fb  call    ?FwServiceShutdown@@YAXXZ; FwServiceShutdown(void)
0x180077100  jmp     short loc_18007710F
0x180077102  mov     rcx, cs:qword_18012BF70; hEvent
0x180077109  call    cs:__imp_SetEvent
0x18007710f  mov     rcx, cs:g_Provider
0x180077116  test    rcx, rcx
0x180077119  jz      short loc_18007712E
0x18007711b  xor     r9d, r9d
0x18007711e  lea     rdx, MPS_SVC_Start_End
0x180077125  xor     r8d, r8d
0x180077128  call    cs:__imp_EtwEventWrite
0x18007712e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077135  cmp     rcx, rbp
0x180077138  jz      short loc_180077151
0x18007713a  test    byte ptr [rcx+1Ch], 8
0x18007713e  jz      short loc_180077151
0x180077140  mov     rcx, [rcx+10h]
0x180077144  mov     edx, 1Ch
0x180077149  mov     r8, r15
0x18007714c  call    WPP_SF_
0x180077151  add     rsp, 48h
0x180077155  pop     r15
0x180077157  pop     rdi
0x180077158  pop     rbp
0x180077159  pop     rbx
0x18007715a  retn
```
