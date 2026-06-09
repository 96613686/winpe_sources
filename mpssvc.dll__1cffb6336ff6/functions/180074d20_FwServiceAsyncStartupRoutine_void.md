# FwServiceAsyncStartupRoutine(void *)

- ea: `0x180074d20`
- end: `0x18007518b`
- name: `?FwServiceAsyncStartupRoutine@@YAKPEAX@Z`
- size: `1131`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000177c`
- `0x180001820`
- `0x180009460`
- `0x18000a0c0`
- `0x180017110`
- `0x18004d9b0`
- `0x18005a100`
- `0x18005cf9c`
- `0x1800670c0`
- `0x18006aa00`
- `0x18006b438`
- `0x18006f520`
- `0x180074d20`
- `0x180075194`
- `0x180075510`
- `0x180079360`
- `0x18007ab14`
- `0x18007abec`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180074e60`
- `ntdll!EtwEventWrite` at `0x180074e60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800750b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800750b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180074d48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180074efd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180074d48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180074efd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180075110`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180075110`
- `fwbase!FwHResultToWindowsError` at `0x180075068`
- `fwbase!FwHResultToWindowsError` at `0x180075068`
- `fwbase!FwReportReturnError` at `0x180074da9`
- `fwbase!FwReportReturnError` at `0x180074da9`
- `fwbase!FwCriticalSectionEnter` at `0x180074eb7`
- `fwbase!FwCriticalSectionEnter` at `0x180074eb7`
- `fwbase!FwCriticalSectionLeave` at `0x180074ef5`
- `fwbase!FwCriticalSectionLeave` at `0x180074ef5`

## string_xrefs

- `0x180074f6c`: `mpssvc.dll`
- `0x180074f85`: `mpssvc.dll`
- `0x180074d7f`: `FwServiceAsyncStartupRoutine`
- `0x180074da2`: `FwServiceAsyncStartupRoutine`
- `0x180075031`: `FwServiceAsyncStartupRoutine`
- `0x180074df7`: `FwComponentsInitialize(FW_INTERFACE_COMPONENTS)`
- `0x180074e3b`: `FwServiceChangeState(SERVICE_RUNNING)`
- `0x180074ea4`: `FwComponentsInitialize(FW_ASYNC_COMPONENTS)`

## pseudocode

```c
__int64 __fastcall FwServiceAsyncStartupRoutine(PVOID Parameter)
{
  int v1; // r12d
  ULONGLONG TickCount64; // r14
  int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  int v6; // r15d
  const char *v7; // rdi
  unsigned __int64 v8; // rsi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-59h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  __int64 v18; // [rsp+40h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v20; // [rsp+70h] [rbp-19h]
  __int64 v21; // [rsp+78h] [rbp-11h]
  __int64 *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  __int64 *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]

  v1 = 0;
  TickCount64 = GetTickCount64();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  FwAcquireRPCExclusiveLock("FwServiceAsyncStartupRoutine");
  v3 = FwLock();
  v5 = v3;
  if ( v3 < 0 )
  {
    v6 = 0;
    v7 = 0;
LABEL_6:
    FwReportReturnError("FwServiceAsyncStartupRoutine", (unsigned int)v3, v4);
    goto LABEL_28;
  }
  v6 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  v3 = FwComponentsInitialize(8, off_1800E7310);
  v5 = v3;
  if ( v3 < 0 )
  {
    v7 = "FwComponentsInitialize(FW_INTERFACE_COMPONENTS)";
    goto LABEL_6;
  }
  byte_18012BF61 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  v3 = FwServiceChangeState(4u);
  v5 = v3;
  if ( v3 < 0 )
  {
    v7 = "FwServiceChangeState(SERVICE_RUNNING)";
    goto LABEL_6;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Start_End, 0, 0);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  v3 = FwComponentsInitialize(11, off_1800E75F0);
  v5 = v3;
  if ( v3 < 0 )
  {
    v7 = "FwComponentsInitialize(FW_ASYNC_COMPONENTS)";
    goto LABEL_6;
  }
  FwCriticalSectionEnter(qword_18012BEE8);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  byte_18012BF62 = 1;
  v1 = 1;
  FwCriticalSectionLeave(qword_18012BEE8);
  v7 = 0;
LABEL_28:
  v8 = GetTickCount64() - TickCount64;
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v16) = v5;
    v17 = (__int64)v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&unk_18010E848,
      v9,
      v10,
      (const char **)&v17,
      (__int64)&v16);
  }
  if ( (v5 & 0x80000000) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v5, (unsigned __int8)byte_18012BF61);
  if ( v8 > 0x493E0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v8, v5);
  if ( (unsigned int)dword_180126458 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_180126458, 0x400000000000LL) )
  {
    LODWORD(v16) = v5;
    v24 = &v16;
    v17 = v8;
    v22 = &v17;
    v18 = 0x1000000;
    v20 = &v18;
    v25 = 4;
    v23 = 8;
    v21 = 8;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180126458, (int)&byte_18010E523, 0, 0, 5u, &v19);
  }
  if ( v6 )
    FwUnlockInternal(0, "FwServiceAsyncStartupRoutine");
  FwReleaseExclusiveCancelableRWLock((struct FW_CANCELABLE_RW_LOCK_ *)&Handles);
  _InterlockedCompareExchange(&gFwInitializing, 0, 1);
  if ( (v5 & 0x80000000) != 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = FwHResultToWindowsError(v5);
    v5 = FwServiceSetStatus();
  }
  if ( !v1 )
  {
    FwAuditLogGenericError(0x13A6u, v5);
    SetEvent(qword_18012BF70);
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_53;
    v14 = 35;
    goto LABEL_52;
  }
  FwServiceOnControl(0, 0);
  FwAuditLogGenericSuccess(0x13A0u);
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v16) = GetCurrentProcessId();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)word_18010E622,
      v11,
      v12,
      (__int64)&v16);
  }
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
    {
LABEL_53:
      if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(v13 + 16), 36, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
      return v5;
    }
    v14 = 34;
LABEL_52:
    WPP_SF_(*(_QWORD *)(v13 + 16), v14, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
    v13 = WPP_GLOBAL_Control;
    goto LABEL_53;
  }
  return v5;
}

```

## disassembly

```asm
0x180074d20  push    rbp
0x180074d22  push    rbx
0x180074d23  push    rsi
0x180074d24  push    rdi
0x180074d25  push    r12
0x180074d27  push    r14
0x180074d29  push    r15
0x180074d2b  lea     rbp, [rsp-27h]
0x180074d30  sub     rsp, 0B0h
0x180074d37  mov     rax, cs:__security_cookie
0x180074d3e  xor     rax, rsp
0x180074d41  mov     [rbp+57h+var_40], rax
0x180074d45  xor     r12d, r12d
0x180074d48  call    cs:__imp_GetTickCount64
0x180074d4e  mov     r14, rax
0x180074d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d58  lea     rsi, WPP_GLOBAL_Control
0x180074d5f  cmp     rcx, rsi
0x180074d62  jz      short loc_180074D7F
0x180074d64  test    byte ptr [rcx+1Ch], 8
0x180074d68  jz      short loc_180074D7F
0x180074d6a  mov     rcx, [rcx+10h]
0x180074d6e  lea     edx, [r12+1Dh]
0x180074d73  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074d7a  call    WPP_SF_
0x180074d7f  lea     rcx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x180074d86  call    ?FwAcquireRPCExclusiveLock@@YAJPEBD@Z; FwAcquireRPCExclusiveLock(char const *)
0x180074d8b  call    FwLock
0x180074d90  mov     ebx, eax
0x180074d92  mov     edi, 4
0x180074d97  test    eax, eax
0x180074d99  jns     short loc_180074DB4
0x180074d9b  xor     r15d, r15d
0x180074d9e  xor     edi, edi
0x180074da0  mov     edx, eax
0x180074da2  lea     rcx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x180074da9  call    cs:__imp_FwReportReturnError
0x180074daf  jmp     loc_180074EFD
0x180074db4  mov     r15d, 1
0x180074dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180074dc1  cmp     rcx, rsi
0x180074dc4  jz      short loc_180074DE0
0x180074dc6  test    [rcx+1Ch], dil
0x180074dca  jz      short loc_180074DE0
0x180074dcc  mov     rcx, [rcx+10h]
0x180074dd0  lea     edx, [r15+1Dh]
0x180074dd4  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074ddb  call    WPP_SF_
0x180074de0  lea     rdx, off_1800E7310
0x180074de7  mov     ecx, 8
0x180074dec  call    FwComponentsInitialize
0x180074df1  mov     ebx, eax
0x180074df3  test    eax, eax
0x180074df5  jns     short loc_180074E00
0x180074df7  lea     rdi, aFwcomponentsin_2; "FwComponentsInitialize(FW_INTERFACE_COM"...
0x180074dfe  jmp     short loc_180074DA0
0x180074e00  mov     cs:byte_18012BF61, r15b
0x180074e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e0e  cmp     rcx, rsi
0x180074e11  jz      short loc_180074E2E
0x180074e13  test    [rcx+1Ch], dil
0x180074e17  jz      short loc_180074E2E
0x180074e19  mov     rcx, [rcx+10h]
0x180074e1d  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074e24  mov     edx, 1Fh
0x180074e29  call    WPP_SF_
0x180074e2e  mov     ecx, edi; unsigned int
0x180074e30  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x180074e35  mov     ebx, eax
0x180074e37  test    eax, eax
0x180074e39  jns     short loc_180074E47
0x180074e3b  lea     rdi, aFwservicechang_0; "FwServiceChangeState(SERVICE_RUNNING)"
0x180074e42  jmp     loc_180074DA0
0x180074e47  mov     rcx, cs:g_Provider
0x180074e4e  test    rcx, rcx
0x180074e51  jz      short loc_180074E66
0x180074e53  xor     r9d, r9d
0x180074e56  lea     rdx, MPS_SVC_Start_End
0x180074e5d  xor     r8d, r8d
0x180074e60  call    cs:__imp_EtwEventWrite
0x180074e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e6d  cmp     rcx, rsi
0x180074e70  jz      short loc_180074E8D
0x180074e72  test    [rcx+1Ch], dil
0x180074e76  jz      short loc_180074E8D
0x180074e78  mov     rcx, [rcx+10h]
0x180074e7c  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074e83  mov     edx, 20h ; ' '
0x180074e88  call    WPP_SF_
0x180074e8d  lea     rdx, off_1800E75F0
0x180074e94  mov     ecx, 0Bh
0x180074e99  call    FwComponentsInitialize
0x180074e9e  mov     ebx, eax
0x180074ea0  test    eax, eax
0x180074ea2  jns     short loc_180074EB0
0x180074ea4  lea     rdi, aFwcomponentsin_0; "FwComponentsInitialize(FW_ASYNC_COMPONE"...
0x180074eab  jmp     loc_180074DA0
0x180074eb0  lea     rcx, qword_18012BEE8
0x180074eb7  call    cs:__imp_FwCriticalSectionEnter
0x180074ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ec4  cmp     rcx, rsi
0x180074ec7  jz      short loc_180074EE4
0x180074ec9  test    [rcx+1Ch], dil
0x180074ecd  jz      short loc_180074EE4
0x180074ecf  mov     rcx, [rcx+10h]
0x180074ed3  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074eda  mov     edx, 21h ; '!'
0x180074edf  call    WPP_SF_
0x180074ee4  lea     rcx, qword_18012BEE8
0x180074eeb  mov     cs:byte_18012BF62, r15b
0x180074ef2  mov     r12d, r15d
0x180074ef5  call    cs:__imp_FwCriticalSectionLeave
0x180074efb  xor     edi, edi
0x180074efd  call    cs:__imp_GetTickCount64
0x180074f03  mov     ecx, cs:dword_1801263B0
0x180074f09  mov     rsi, rax
0x180074f0c  sub     rsi, r14
0x180074f0f  mov     r14d, 4
0x180074f15  cmp     ecx, r14d
0x180074f18  jbe     short loc_180074F60
0x180074f1a  mov     rdx, 4000000000000h
0x180074f24  lea     rcx, dword_1801263B0
0x180074f2b  call    _tlgKeywordOn
0x180074f30  test    al, al
0x180074f32  jz      short loc_180074F60
0x180074f34  lea     rax, [rbp+57h+var_B0]
0x180074f38  mov     dword ptr [rbp+57h+var_B0], ebx
0x180074f3b  mov     [rsp+0E0h+var_B8], rax; __int64
0x180074f40  lea     rdx, unk_18010E848
0x180074f47  lea     rax, [rbp+57h+var_A8]
0x180074f4b  mov     [rbp+57h+var_A8], rdi
0x180074f4f  lea     rcx, dword_1801263B0; int
0x180074f56  mov     qword ptr [rsp+0E0h+var_C0], rax; __int64
0x180074f5b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180074f60  test    ebx, ebx
0x180074f62  jns     short loc_180074F7A
0x180074f64  movzx   r8d, cs:byte_18012BF61
0x180074f6c  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180074f73  mov     edx, ebx
0x180074f75  call    MicrosoftTelemetryAssertTriggeredArgs
0x180074f7a  cmp     rsi, 493E0h
0x180074f81  jbe     short loc_180074F94
0x180074f83  mov     edx, esi
0x180074f85  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180074f8c  mov     r8d, ebx
0x180074f8f  call    MicrosoftTelemetryAssertTriggeredArgs
0x180074f94  mov     eax, cs:dword_180126458
0x180074f9a  test    eax, eax
0x180074f9c  jz      loc_18007502C
0x180074fa2  mov     eax, cs:dword_180126458
0x180074fa8  cmp     eax, 5
0x180074fab  jbe     short loc_18007502C
0x180074fad  mov     rdx, 400000000000h
0x180074fb7  lea     rcx, dword_180126458
0x180074fbe  call    _tlgKeywordOn
0x180074fc3  test    al, al
0x180074fc5  jz      short loc_18007502C
0x180074fc7  lea     rax, [rbp+57h+var_B0]
0x180074fcb  mov     dword ptr [rbp+57h+var_B0], ebx
0x180074fce  mov     [rbp+57h+var_50], rax
0x180074fd2  lea     rdx, byte_18010E523; int
0x180074fd9  lea     rax, [rbp+57h+var_A8]
0x180074fdd  mov     [rbp+57h+var_A8], rsi
0x180074fe1  mov     [rbp+57h+var_60], rax
0x180074fe5  lea     rcx, dword_180126458; int
0x180074fec  lea     rax, [rbp+57h+var_A0]
0x180074ff0  mov     [rbp+57h+var_A0], 1000000h
0x180074ff8  mov     [rbp+57h+var_70], rax
0x180074ffc  xor     r9d, r9d; int
0x180074fff  lea     rax, [rbp+57h+var_90]
0x180075003  mov     [rbp+57h+var_48], r14
0x180075007  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x18007500c  xor     r8d, r8d; int
0x18007500f  mov     [rsp+0E0h+var_C0], 5; ULONG
0x180075017  mov     [rbp+57h+var_58], 8
0x18007501f  mov     [rbp+57h+var_68], 8
0x180075027  call    _tlgWriteTransfer_EventWriteTransfer
0x18007502c  test    r15d, r15d
0x18007502f  jz      short loc_18007503F
0x180075031  lea     rdx, aFwserviceasync; "FwServiceAsyncStartupRoutine"
0x180075038  xor     ecx, ecx; void *
0x18007503a  call    FwUnlockInternal
0x18007503f  lea     rcx, Handles; struct FW_CANCELABLE_RW_LOCK_ *
0x180075046  call    FwReleaseExclusiveCancelableRWLock
0x18007504b  xor     ecx, ecx
0x18007504d  lea     eax, [rcx+1]
0x180075050  lock cmpxchg cs:?gFwInitializing@@3HC, ecx; int volatile gFwInitializing
0x180075058  test    ebx, ebx
0x18007505a  jns     short loc_18007507B
0x18007505c  mov     ecx, ebx
0x18007505e  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x180075068  call    cs:__imp_FwHResultToWindowsError
0x18007506e  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x180075074  call    ?FwServiceSetStatus@@YAJXZ; FwServiceSetStatus(void)
0x180075079  mov     ebx, eax
0x18007507b  test    r12d, r12d
0x18007507e  jz      short loc_1800750FD
0x180075080  xor     edx, edx; unsigned __int8
0x180075082  xor     ecx, ecx; void *
0x180075084  call    ?FwServiceOnControl@@YAXPEAXE@Z; FwServiceOnControl(void *,uchar)
0x180075089  mov     ecx, 13A0h; unsigned int
0x18007508e  call    FwAuditLogGenericSuccess
0x180075093  mov     eax, cs:dword_1801263B0
0x180075099  cmp     eax, r14d
0x18007509c  jbe     short loc_1800750DD
0x18007509e  mov     rdx, 4000000000000h
0x1800750a8  lea     rcx, dword_1801263B0
0x1800750af  call    _tlgKeywordOn
0x1800750b4  test    al, al
0x1800750b6  jz      short loc_1800750DD
0x1800750b8  call    cs:__imp_GetCurrentProcessId
0x1800750be  mov     dword ptr [rbp+57h+var_B0], eax
0x1800750c1  lea     rdx, word_18010E622
0x1800750c8  lea     rax, [rbp+57h+var_B0]
0x1800750cc  lea     rcx, dword_1801263B0
0x1800750d3  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800750d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800750dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800750e4  lea     rdi, WPP_GLOBAL_Control
0x1800750eb  cmp     rcx, rdi
0x1800750ee  jz      short loc_18007516B
0x1800750f0  test    [rcx+1Ch], r14b
0x1800750f4  jz      short loc_18007514B
0x1800750f6  mov     edx, 22h ; '"'
0x1800750fb  jmp     short loc_180075134
0x1800750fd  mov     edx, ebx; unsigned __int64
0x1800750ff  mov     ecx, 13A6h; unsigned int
0x180075104  call    FwAuditLogGenericError
0x180075109  mov     rcx, cs:qword_18012BF70; hEvent
0x180075110  call    cs:__imp_SetEvent
0x180075116  mov     rcx, cs:WPP_GLOBAL_Control
0x18007511d  lea     rdi, WPP_GLOBAL_Control
0x180075124  cmp     rcx, rdi
0x180075127  jz      short loc_18007516B
0x180075129  test    [rcx+1Ch], r14b
0x18007512d  jz      short loc_18007514B
0x18007512f  mov     edx, 23h ; '#'
0x180075134  mov     rcx, [rcx+10h]
0x180075138  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18007513f  call    WPP_SF_
0x180075144  mov     rcx, cs:WPP_GLOBAL_Control
0x18007514b  cmp     rcx, rdi
0x18007514e  jz      short loc_18007516B
0x180075150  test    byte ptr [rcx+1Ch], 8
0x180075154  jz      short loc_18007516B
0x180075156  mov     rcx, [rcx+10h]
0x18007515a  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180075161  mov     edx, 24h ; '$'
0x180075166  call    WPP_SF_
0x18007516b  mov     eax, ebx
0x18007516d  mov     rcx, [rbp+57h+var_40]
0x180075171  xor     rcx, rsp; StackCookie
0x180075174  call    __security_check_cookie
0x180075179  add     rsp, 0B0h
0x180075180  pop     r15
0x180075182  pop     r14
0x180075184  pop     r12
0x180075186  pop     rdi
0x180075187  pop     rsi
0x180075188  pop     rbx
0x180075189  pop     rbp
0x18007518a  retn
```
