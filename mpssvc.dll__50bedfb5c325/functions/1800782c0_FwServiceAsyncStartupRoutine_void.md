# FwServiceAsyncStartupRoutine(void *)

- ea: `0x1800782c0`
- end: `0x18007876a`
- name: `?FwServiceAsyncStartupRoutine@@YAKPEAX@Z`
- size: `1194`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001784`
- `0x18000182c`
- `0x180008a80`
- `0x1800097b0`
- `0x1800192e0`
- `0x180050cd8`
- `0x18005f130`
- `0x180061c90`
- `0x18006a710`
- `0x18006da64`
- `0x18006e614`
- `0x1800729c0`
- `0x1800782c0`
- `0x180078770`
- `0x180078b30`
- `0x18007cfa0`
- `0x18007e928`
- `0x18007ea0c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18007840c`
- `ntdll!EtwEventWrite` at `0x18007840c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180078686`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800782e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800784bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800782e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800784bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800786e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800786e8`
- `fwbase!FwHResultToWindowsError` at `0x18007862c`
- `fwbase!FwHResultToWindowsError` at `0x18007862c`
- `fwbase!FwReportReturnError` at `0x18007834f`
- `fwbase!FwReportReturnError` at `0x18007834f`
- `fwbase!FwCriticalSectionEnter` at `0x180078469`
- `fwbase!FwCriticalSectionEnter` at `0x180078469`
- `fwbase!FwCriticalSectionLeave` at `0x1800784ad`
- `fwbase!FwCriticalSectionLeave` at `0x1800784ad`

## string_xrefs

- `0x180078530`: `mpssvc.dll`
- `0x180078549`: `mpssvc.dll`
- `0x180078325`: `FwServiceAsyncStartupRoutine`
- `0x180078348`: `FwServiceAsyncStartupRoutine`
- `0x1800785f5`: `FwServiceAsyncStartupRoutine`
- `0x1800783a3`: `FwComponentsInitialize(FW_INTERFACE_COMPONENTS)`
- `0x1800783e7`: `FwServiceChangeState(SERVICE_RUNNING)`
- `0x180078456`: `FwComponentsInitialize(FW_ASYNC_COMPONENTS)`

## pseudocode

```c
__int64 __fastcall FwServiceAsyncStartupRoutine(PVOID Parameter)
{
  int v1; // r12d
  ULONGLONG TickCount64; // r14
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // r15d
  const char *v6; // rdi
  unsigned __int64 v7; // rsi
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // [rsp+30h] [rbp-59h] BYREF
  __int64 v14; // [rsp+38h] [rbp-51h] BYREF
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v17; // [rsp+70h] [rbp-19h]
  __int64 v18; // [rsp+78h] [rbp-11h]
  __int64 *v19; // [rsp+80h] [rbp-9h]
  __int64 v20; // [rsp+88h] [rbp-1h]
  __int64 *v21; // [rsp+90h] [rbp+7h]
  __int64 v22; // [rsp+98h] [rbp+Fh]

  v1 = 0;
  TickCount64 = GetTickCount64();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  FwAcquireRPCExclusiveLock("FwServiceAsyncStartupRoutine");
  v3 = FwLock();
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 0;
    v6 = 0;
LABEL_6:
    FwReportReturnError("FwServiceAsyncStartupRoutine", (unsigned int)v3);
    goto LABEL_28;
  }
  v5 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  v3 = FwComponentsInitialize(8, off_1800ED250);
  v4 = v3;
  if ( v3 < 0 )
  {
    v6 = "FwComponentsInitialize(FW_INTERFACE_COMPONENTS)";
    goto LABEL_6;
  }
  byte_180132141 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  v3 = FwServiceChangeState(4u);
  v4 = v3;
  if ( v3 < 0 )
  {
    v6 = "FwServiceChangeState(SERVICE_RUNNING)";
    goto LABEL_6;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Start_End, 0, 0);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  v3 = FwComponentsInitialize(11, off_1800ED530);
  v4 = v3;
  if ( v3 < 0 )
  {
    v6 = "FwComponentsInitialize(FW_ASYNC_COMPONENTS)";
    goto LABEL_6;
  }
  FwCriticalSectionEnter(qword_1801320C8);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  byte_180132142 = 1;
  v1 = 1;
  FwCriticalSectionLeave(qword_1801320C8);
  v6 = 0;
LABEL_28:
  v7 = GetTickCount64() - TickCount64;
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v13) = v4;
    v14 = (__int64)v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v14,
      (__int64)&v13);
  }
  if ( (v4 & 0x80000000) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v4, (unsigned __int8)byte_180132141);
  if ( v7 > 0x493E0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v7, v4);
  if ( (unsigned int)dword_18012C458 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_18012C458, 0x400000000000LL) )
  {
    LODWORD(v13) = v4;
    v21 = &v13;
    v14 = v7;
    v19 = &v14;
    v15 = 0x1000000;
    v17 = &v15;
    v22 = 4;
    v20 = 8;
    v18 = 8;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_18012C458, (int)&byte_18011433B, 0, 0, 5u, &v16);
  }
  if ( v5 )
    FwUnlockInternal(0, "FwServiceAsyncStartupRoutine");
  FwReleaseExclusiveCancelableRWLock((struct FW_CANCELABLE_RW_LOCK_ *)&Handles);
  _InterlockedCompareExchange(&gFwInitializing, 0, 1);
  if ( (v4 & 0x80000000) != 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = FwHResultToWindowsError(v4);
    v4 = FwServiceSetStatus();
  }
  if ( !v1 )
  {
    FwAuditLogGenericError(0x13A6u, v4);
    SetEvent(qword_180132150);
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v4;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_53;
    v11 = 35;
    goto LABEL_52;
  }
  FwServiceOnControl(0, 0);
  FwAuditLogGenericSuccess(0x13A0u);
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v13) = GetCurrentProcessId();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18012C3B0,
      (unsigned int)word_18011443A,
      v8,
      v9,
      (__int64)&v13);
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
    {
LABEL_53:
      if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(v10 + 16), 36, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
      return v4;
    }
    v11 = 34;
LABEL_52:
    WPP_SF_(*(_QWORD *)(v10 + 16), v11, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
    v10 = WPP_GLOBAL_Control;
    goto LABEL_53;
  }
  return v4;
}

```

## disassembly

```asm
0x1800782c0  push    rbp
0x1800782c2  push    rbx
0x1800782c3  push    rsi
0x1800782c4  push    rdi
0x1800782c5  push    r12
0x1800782c7  push    r14
0x1800782c9  push    r15
0x1800782cb  lea     rbp, [rsp-27h]
0x1800782d0  sub     rsp, 0B0h
0x1800782d7  mov     rax, cs:__security_cookie
0x1800782de  xor     rax, rsp
0x1800782e1  mov     [rbp+57h+var_40], rax
0x1800782e5  xor     r12d, r12d
0x1800782e8  call    cs:__imp_GetTickCount64
0x1800782ef  nop     dword ptr [rax+rax+00h]
0x1800782f4  mov     r14, rax
0x1800782f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800782fe  lea     rsi, WPP_GLOBAL_Control
0x180078305  cmp     rcx, rsi
0x180078308  jz      short loc_180078325
0x18007830a  test    byte ptr [rcx+1Ch], 8
0x18007830e  jz      short loc_180078325
0x180078310  mov     rcx, [rcx+10h]
0x180078314  lea     edx, [r12+1Dh]
0x180078319  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180078320  call    WPP_SF_
0x180078325  lea     rcx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x18007832c  call    ?FwAcquireRPCExclusiveLock@@YAJPEBD@Z; FwAcquireRPCExclusiveLock(char const *)
0x180078331  call    FwLock
0x180078336  mov     ebx, eax
0x180078338  mov     edi, 4
0x18007833d  test    eax, eax
0x18007833f  jns     short loc_180078360
0x180078341  xor     r15d, r15d
0x180078344  xor     edi, edi
0x180078346  mov     edx, eax
0x180078348  lea     rcx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x18007834f  call    cs:__imp_FwReportReturnError
0x180078356  nop     dword ptr [rax+rax+00h]
0x18007835b  jmp     loc_1800784BB
0x180078360  mov     r15d, 1
0x180078366  mov     rcx, cs:WPP_GLOBAL_Control
0x18007836d  cmp     rcx, rsi
0x180078370  jz      short loc_18007838C
0x180078372  test    [rcx+1Ch], dil
0x180078376  jz      short loc_18007838C
0x180078378  mov     rcx, [rcx+10h]
0x18007837c  lea     edx, [r15+1Dh]
0x180078380  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180078387  call    WPP_SF_
0x18007838c  lea     rdx, off_1800ED250
0x180078393  mov     ecx, 8
0x180078398  call    FwComponentsInitialize
0x18007839d  mov     ebx, eax
0x18007839f  test    eax, eax
0x1800783a1  jns     short loc_1800783AC
0x1800783a3  lea     rdi, aFwcomponentsin_2; "FwComponentsInitialize(FW_INTERFACE_COM"...
0x1800783aa  jmp     short loc_180078346
0x1800783ac  mov     cs:byte_180132141, r15b
0x1800783b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800783ba  cmp     rcx, rsi
0x1800783bd  jz      short loc_1800783DA
0x1800783bf  test    [rcx+1Ch], dil
0x1800783c3  jz      short loc_1800783DA
0x1800783c5  mov     rcx, [rcx+10h]
0x1800783c9  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x1800783d0  mov     edx, 1Fh
0x1800783d5  call    WPP_SF_
0x1800783da  mov     ecx, edi; unsigned int
0x1800783dc  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x1800783e1  mov     ebx, eax
0x1800783e3  test    eax, eax
0x1800783e5  jns     short loc_1800783F3
0x1800783e7  lea     rdi, aFwservicechang_0; "FwServiceChangeState(SERVICE_RUNNING)"
0x1800783ee  jmp     loc_180078346
0x1800783f3  mov     rcx, cs:g_Provider
0x1800783fa  test    rcx, rcx
0x1800783fd  jz      short loc_180078418
0x1800783ff  xor     r9d, r9d
0x180078402  lea     rdx, MPS_SVC_Start_End
0x180078409  xor     r8d, r8d
0x18007840c  call    cs:__imp_EtwEventWrite
0x180078413  nop     dword ptr [rax+rax+00h]
0x180078418  mov     rcx, cs:WPP_GLOBAL_Control
0x18007841f  cmp     rcx, rsi
0x180078422  jz      short loc_18007843F
0x180078424  test    [rcx+1Ch], dil
0x180078428  jz      short loc_18007843F
0x18007842a  mov     rcx, [rcx+10h]
0x18007842e  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180078435  mov     edx, 20h ; ' '
0x18007843a  call    WPP_SF_
0x18007843f  lea     rdx, off_1800ED530
0x180078446  mov     ecx, 0Bh
0x18007844b  call    FwComponentsInitialize
0x180078450  mov     ebx, eax
0x180078452  test    eax, eax
0x180078454  jns     short loc_180078462
0x180078456  lea     rdi, aFwcomponentsin_0; "FwComponentsInitialize(FW_ASYNC_COMPONE"...
0x18007845d  jmp     loc_180078346
0x180078462  lea     rcx, qword_1801320C8
0x180078469  call    cs:__imp_FwCriticalSectionEnter
0x180078470  nop     dword ptr [rax+rax+00h]
0x180078475  mov     rcx, cs:WPP_GLOBAL_Control
0x18007847c  cmp     rcx, rsi
0x18007847f  jz      short loc_18007849C
0x180078481  test    [rcx+1Ch], dil
0x180078485  jz      short loc_18007849C
0x180078487  mov     rcx, [rcx+10h]
0x18007848b  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180078492  mov     edx, 21h ; '!'
0x180078497  call    WPP_SF_
0x18007849c  lea     rcx, qword_1801320C8
0x1800784a3  mov     cs:byte_180132142, r15b
0x1800784aa  mov     r12d, r15d
0x1800784ad  call    cs:__imp_FwCriticalSectionLeave
0x1800784b4  nop     dword ptr [rax+rax+00h]
0x1800784b9  xor     edi, edi
0x1800784bb  call    cs:__imp_GetTickCount64
0x1800784c2  nop     dword ptr [rax+rax+00h]
0x1800784c7  mov     ecx, cs:dword_18012C3B0
0x1800784cd  mov     rsi, rax
0x1800784d0  sub     rsi, r14
0x1800784d3  mov     r14d, 4
0x1800784d9  cmp     ecx, r14d
0x1800784dc  jbe     short loc_180078524
0x1800784de  mov     rdx, 4000000000000h
0x1800784e8  lea     rcx, dword_18012C3B0
0x1800784ef  call    _tlgKeywordOn
0x1800784f4  test    al, al
0x1800784f6  jz      short loc_180078524
0x1800784f8  lea     rax, [rbp+57h+var_B0]
0x1800784fc  mov     dword ptr [rbp+57h+var_B0], ebx
0x1800784ff  mov     [rsp+0E0h+var_B8], rax; __int64
0x180078504  lea     rdx, unk_180114660
0x18007850b  lea     rax, [rbp+57h+var_A8]
0x18007850f  mov     [rbp+57h+var_A8], rdi
0x180078513  lea     rcx, dword_18012C3B0; int
0x18007851a  mov     qword ptr [rsp+0E0h+var_C0], rax; __int64
0x18007851f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180078524  test    ebx, ebx
0x180078526  jns     short loc_18007853E
0x180078528  movzx   r8d, cs:byte_180132141; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(result)", "FwServiceAsyncStartupRoutine failed")
0x180078530  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180078537  mov     edx, ebx
0x180078539  call    MicrosoftTelemetryAssertTriggeredArgs
0x18007853e  cmp     rsi, 493E0h
0x180078545  jbe     short loc_180078558
0x180078547  mov     edx, esi; __annotation("Debug", "TelemetryAssert", "FALSE", "FwServiceAsyncStartupRoutine took too long to startup")
0x180078549  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180078550  mov     r8d, ebx
0x180078553  call    MicrosoftTelemetryAssertTriggeredArgs
0x180078558  mov     eax, cs:dword_18012C458
0x18007855e  test    eax, eax
0x180078560  jz      loc_1800785F0
0x180078566  mov     eax, cs:dword_18012C458
0x18007856c  cmp     eax, 5
0x18007856f  jbe     short loc_1800785F0
0x180078571  mov     rdx, 400000000000h
0x18007857b  lea     rcx, dword_18012C458
0x180078582  call    _tlgKeywordOn
0x180078587  test    al, al
0x180078589  jz      short loc_1800785F0
0x18007858b  lea     rax, [rbp+57h+var_B0]
0x18007858f  mov     dword ptr [rbp+57h+var_B0], ebx
0x180078592  mov     [rbp+57h+var_50], rax
0x180078596  lea     rdx, byte_18011433B; int
0x18007859d  lea     rax, [rbp+57h+var_A8]
0x1800785a1  mov     [rbp+57h+var_A8], rsi
0x1800785a5  mov     [rbp+57h+var_60], rax
0x1800785a9  lea     rcx, dword_18012C458; int
0x1800785b0  lea     rax, [rbp+57h+var_A0]
0x1800785b4  mov     [rbp+57h+var_A0], 1000000h
0x1800785bc  mov     [rbp+57h+var_70], rax
0x1800785c0  xor     r9d, r9d; int
0x1800785c3  lea     rax, [rbp+57h+var_90]
0x1800785c7  mov     [rbp+57h+var_48], r14
0x1800785cb  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1800785d0  xor     r8d, r8d; int
0x1800785d3  mov     [rsp+0E0h+var_C0], 5; ULONG
0x1800785db  mov     [rbp+57h+var_58], 8
0x1800785e3  mov     [rbp+57h+var_68], 8
0x1800785eb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800785f0  test    r15d, r15d
0x1800785f3  jz      short loc_180078603
0x1800785f5  lea     rdx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x1800785fc  xor     ecx, ecx; void *
0x1800785fe  call    FwUnlockInternal
0x180078603  lea     rcx, Handles; struct FW_CANCELABLE_RW_LOCK_ *
0x18007860a  call    FwReleaseExclusiveCancelableRWLock
0x18007860f  xor     ecx, ecx
0x180078611  lea     eax, [rcx+1]
0x180078614  lock cmpxchg cs:?gFwInitializing@@3HC, ecx; int volatile gFwInitializing
0x18007861c  test    ebx, ebx
0x18007861e  jns     short loc_180078645
0x180078620  mov     ecx, ebx
0x180078622  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18007862c  call    cs:__imp_FwHResultToWindowsError
0x180078633  nop     dword ptr [rax+rax+00h]
0x180078638  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18007863e  call    ?FwServiceSetStatus@@YAJXZ; FwServiceSetStatus(void)
0x180078643  mov     ebx, eax
0x180078645  test    r12d, r12d
0x180078648  jz      loc_1800786D5
0x18007864e  xor     edx, edx; unsigned __int8
0x180078650  xor     ecx, ecx; void *
0x180078652  call    ?FwServiceOnControl@@YAXPEAXE@Z; FwServiceOnControl(void *,uchar)
0x180078657  mov     ecx, 13A0h; unsigned int
0x18007865c  call    FwAuditLogGenericSuccess
0x180078661  mov     eax, cs:dword_18012C3B0
0x180078667  cmp     eax, r14d
0x18007866a  jbe     short loc_1800786B1
0x18007866c  mov     rdx, 4000000000000h
0x180078676  lea     rcx, dword_18012C3B0
0x18007867d  call    _tlgKeywordOn
0x180078682  test    al, al
0x180078684  jz      short loc_1800786B1
0x180078686  call    cs:__imp_GetCurrentProcessId
0x18007868d  nop     dword ptr [rax+rax+00h]
0x180078692  mov     dword ptr [rbp+57h+var_B0], eax
0x180078695  lea     rdx, word_18011443A
0x18007869c  lea     rax, [rbp+57h+var_B0]
0x1800786a0  lea     rcx, dword_18012C3B0
0x1800786a7  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800786ac  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800786b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786b8  lea     rdi, WPP_GLOBAL_Control
0x1800786bf  cmp     rcx, rdi
0x1800786c2  jz      loc_180078749
0x1800786c8  test    [rcx+1Ch], r14b
0x1800786cc  jz      short loc_180078729
0x1800786ce  mov     edx, 22h ; '"'
0x1800786d3  jmp     short loc_180078712
0x1800786d5  mov     edx, ebx; unsigned __int64
0x1800786d7  mov     ecx, 13A6h; unsigned int
0x1800786dc  call    FwAuditLogGenericError
0x1800786e1  mov     rcx, cs:qword_180132150; hEvent
0x1800786e8  call    cs:__imp_SetEvent
0x1800786ef  nop     dword ptr [rax+rax+00h]
0x1800786f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786fb  lea     rdi, WPP_GLOBAL_Control
0x180078702  cmp     rcx, rdi
0x180078705  jz      short loc_180078749
0x180078707  test    [rcx+1Ch], r14b
0x18007870b  jz      short loc_180078729
0x18007870d  mov     edx, 23h ; '#'
0x180078712  mov     rcx, [rcx+10h]
0x180078716  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x18007871d  call    WPP_SF_
0x180078722  mov     rcx, cs:WPP_GLOBAL_Control
0x180078729  cmp     rcx, rdi
0x18007872c  jz      short loc_180078749
0x18007872e  test    byte ptr [rcx+1Ch], 8
0x180078732  jz      short loc_180078749
0x180078734  mov     rcx, [rcx+10h]
0x180078738  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x18007873f  mov     edx, 24h ; '$'
0x180078744  call    WPP_SF_
0x180078749  mov     eax, ebx
0x18007874b  mov     rcx, [rbp+57h+var_40]
0x18007874f  xor     rcx, rsp; StackCookie
0x180078752  call    __security_check_cookie
0x180078757  add     rsp, 0B0h
0x18007875e  pop     r15
0x180078760  pop     r14
0x180078762  pop     r12
0x180078764  pop     rdi
0x180078765  pop     rsi
0x180078766  pop     rbx
0x180078767  pop     rbp
0x180078768  retn
```
