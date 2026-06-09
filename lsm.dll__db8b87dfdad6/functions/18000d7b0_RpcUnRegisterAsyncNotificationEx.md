# RpcUnRegisterAsyncNotificationEx

- ea: `0x18000d7b0`
- end: `0x18000db7c`
- name: `RpcUnRegisterAsyncNotificationEx`
- size: `972`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18000d7b0`
- `0x18000db90`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000db26`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000db26`
- `ntdll!NtQueryInformationProcess` at `0x18000db0a`
- `ntdll!NtQueryInformationProcess` at `0x18000db0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db70`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d91d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000db62`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d91d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000db62`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d8a5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d8a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db4f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d816`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d816`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d888`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d888`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dade`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dade`

## string_xrefs

- `0x18000d988`: `%s with Trace ID 0x%x Completed`
- `0x18000da46`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000d9c2`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcUnRegisterAsyncNotificationEx(__int64 a1)
{
  unsigned int v2; // edi
  RPC_STATUS v3; // eax
  int v4; // ebx
  unsigned int v5; // ebx
  HANDLE v7; // rax
  void *v8; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  struct CTraceBase *v12; // [rsp+30h] [rbp-D0h] BYREF
  void **v13; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  const char *v18; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+80h] [rbp-80h]
  unsigned __int16 v21[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v13 = &CTraceBase::`vftable';
  v15[1] = 1;
  v16 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v13, 1, "RpcUnRegisterAsyncNotificationEx");
    v12 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v12) >= 0 && v12 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v16) >= 0 && v16 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v16 + 32LL))(v16, &pguid);
      v15[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v16 + 24LL))(v16);
      v17 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v13, "RpcUnRegisterAsyncNotificationEx");
    CTraceBase::GenerateTraceID(&pguid, v15);
  }
  else
  {
    CoCreateGuid(&pguid);
    v15[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v17 = 0;
LABEL_4:
  v13 = &CRpcCallTrace::`vftable';
  v18 = "RpcUnRegisterAsyncNotificationEx";
  *(_QWORD *)Pid = -1;
  v20 = 0;
  memset_0(v21, 0, 0x208u);
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v18, v15[0]);
  v2 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v2 = 260;
  *(_QWORD *)Pid = -1;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v2 )
    {
      v7 = OpenProcess(0x400u, 0, Pid[1]);
      v8 = v7;
      if ( v7 )
      {
        InformationProcess = NtQueryInformationProcess(v7, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v4 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v10 = wcsrchr(Str, 0x5Cu);
          if ( v10 )
            v11 = v10 + 1;
          else
            v11 = Str;
          StringCchCopyW(v21, v2, v11);
        }
        CloseHandle(v8);
      }
    }
  }
  if ( v20 )
  {
    if ( v4 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v21);
    }
  }
  v5 = RpcUnRegisterAsyncNotification(a1);
  v13 = &CRpcCallTrace::`vftable';
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v18, v15[0]);
  v13 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v17 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( !TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      GetLastError();
LABEL_46:
      GetLastError();
      return v5;
    }
    if ( !TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
      goto LABEL_46;
  }
  return v5;
}

```

## disassembly

```asm
0x18000d7b0  push    rbp
0x18000d7b2  push    rbx
0x18000d7b3  push    rsi
0x18000d7b4  push    rdi
0x18000d7b5  push    r12
0x18000d7b7  push    r13
0x18000d7b9  push    r14
0x18000d7bb  push    r15
0x18000d7bd  lea     rbp, [rsp-2B8h]
0x18000d7c5  sub     rsp, 3B8h
0x18000d7cc  mov     rax, cs:__security_cookie
0x18000d7d3  xor     rax, rsp
0x18000d7d6  mov     [rbp+2F0h+var_50], rax
0x18000d7dd  mov     rsi, rcx
0x18000d7e0  lea     r12, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000d7e7  mov     [rsp+3F0h+var_3B0], r12
0x18000d7ec  mov     ebx, 1
0x18000d7f1  mov     [rsp+3F0h+var_394], ebx
0x18000d7f5  xor     r15d, r15d
0x18000d7f8  mov     [rsp+3F0h+var_390], r15
0x18000d7fd  lea     rdi, aRpcunregistera_0; "RpcUnRegisterAsyncNotificationEx"
0x18000d804  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r15d; int CTraceBase::g_bEnabled
0x18000d80b  jnz     loc_18000D9FB
0x18000d811  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000d816  call    cs:__imp_CoCreateGuid
0x18000d81c  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x18000d824  inc     ebx
0x18000d826  mov     [rsp+3F0h+var_398], ebx
0x18000d82a  mov     [rsp+3F0h+var_388], r15d
0x18000d82f  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000d836  mov     [rsp+3F0h+var_3B0], r13
0x18000d83b  mov     [rsp+3F0h+var_380], rdi
0x18000d840  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d849  mov     [rbp+2F0h+var_370], r15d
0x18000d84d  xor     edx, edx; Val
0x18000d84f  mov     r8d, 208h; Size
0x18000d855  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000d859  call    memset_0
0x18000d85e  cmp     [rbp+2F0h+var_370], r15d
0x18000d862  jnz     loc_18000D944
0x18000d868  mov     edi, r15d
0x18000d86b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d872  jnz     loc_18000DAC8
0x18000d878  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d881  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000d886  xor     ecx, ecx; Binding
0x18000d888  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d88e  mov     ebx, eax
0x18000d890  test    eax, eax
0x18000d892  jg      loc_18000D936
0x18000d898  test    ebx, ebx
0x18000d89a  js      short loc_18000D8B3
0x18000d89c  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000d8a1  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000d8a5  call    cs:__imp_ProcessIdToSessionId
0x18000d8ab  test    edi, edi
0x18000d8ad  jnz     loc_18000DAD2
0x18000d8b3  cmp     [rbp+2F0h+var_370], r15d
0x18000d8b7  jnz     loc_18000D99E
0x18000d8bd  mov     rcx, rsi
0x18000d8c0  call    RpcUnRegisterAsyncNotification
0x18000d8c5  mov     ebx, eax
0x18000d8c7  mov     [rsp+3F0h+var_3B0], r13
0x18000d8cc  cmp     [rbp+2F0h+var_370], 0
0x18000d8d0  jnz     loc_18000D971
0x18000d8d6  mov     [rsp+3F0h+var_3B0], r12
0x18000d8db  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000d8e2  jnz     short loc_18000D909
0x18000d8e4  mov     eax, ebx
0x18000d8e6  mov     rcx, [rbp+2F0h+var_50]
0x18000d8ed  xor     rcx, rsp; StackCookie
0x18000d8f0  call    __security_check_cookie
0x18000d8f5  add     rsp, 3B8h
0x18000d8fc  pop     r15
0x18000d8fe  pop     r14
0x18000d900  pop     r13
0x18000d902  pop     r12
0x18000d904  pop     rdi
0x18000d905  pop     rsi
0x18000d906  pop     rbx
0x18000d907  pop     rbp
0x18000d908  retn
0x18000d909  cmp     [rsp+3F0h+var_388], 0
0x18000d90e  jnz     short loc_18000D8E4
0x18000d910  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000d916  cmp     ecx, 0FFFFFFFFh
0x18000d919  jz      short loc_18000D8E4
0x18000d91b  xor     edx, edx; lpTlsValue
0x18000d91d  call    cs:__imp_TlsSetValue
0x18000d923  test    eax, eax
0x18000d925  jnz     loc_18000DB5A
0x18000d92b  call    cs:__imp_GetLastError
0x18000d931  jmp     loc_18000DB70
0x18000d936  movzx   ebx, ax
0x18000d939  or      ebx, 80070000h
0x18000d93f  jmp     loc_18000D898
0x18000d944  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d94b  jz      loc_18000D868
0x18000d951  mov     r9d, [rsp+3F0h+var_398]
0x18000d956  mov     r8, [rsp+3F0h+var_380]
0x18000d95b  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000d962  mov     ecx, 2; int
0x18000d967  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d96c  jmp     loc_18000D868
0x18000d971  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d978  jz      loc_18000D8D6
0x18000d97e  mov     r9d, [rsp+3F0h+var_398]
0x18000d983  mov     r8, [rsp+3F0h+var_380]
0x18000d988  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000d98f  mov     ecx, 2; int
0x18000d994  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d999  jmp     loc_18000D8D6
0x18000d99e  test    ebx, ebx
0x18000d9a0  js      short loc_18000D9D8
0x18000d9a2  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d9a9  jz      loc_18000D8BD
0x18000d9af  lea     rax, [rbp+2F0h+var_36C]
0x18000d9b3  mov     [rsp+3F0h+ReturnLength], rax
0x18000d9b8  mov     r9d, [rsp+3F0h+Pid]
0x18000d9bd  mov     r8d, [rsp+3F0h+Pid+4]
0x18000d9c2  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000d9c9  mov     ecx, 2; int
0x18000d9ce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d9d3  jmp     loc_18000D8BD
0x18000d9d8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d9df  jz      loc_18000D8BD
0x18000d9e5  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000d9ec  mov     ecx, 2; int
0x18000d9f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d9f6  jmp     loc_18000D8BD
0x18000d9fb  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000da01  jz      short loc_18000DA21
0x18000da03  mov     [rsp+3F0h+ReturnLength], rdi
0x18000da08  mov     r9d, ebx
0x18000da0b  lea     r8, [rsp+3F0h+var_3B0]
0x18000da10  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000da17  mov     ecx, 2; int
0x18000da1c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000da21  mov     [rsp+3F0h+var_3C0], r15
0x18000da26  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000da2b  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000da30  test    eax, eax
0x18000da32  js      short loc_18000DA57
0x18000da34  cmp     [rsp+3F0h+var_3C0], r15
0x18000da39  jz      short loc_18000DA57
0x18000da3b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000da41  jz      short loc_18000DA57
0x18000da43  mov     r8d, ebx
0x18000da46  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000da4d  mov     ecx, 2; int
0x18000da52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000da57  xor     edx, edx; char *
0x18000da59  xor     ecx, ecx; lpTlsValue
0x18000da5b  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000da60  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000da65  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000da6a  test    eax, eax
0x18000da6c  js      short loc_18000DAA7
0x18000da6e  mov     rcx, [rsp+3F0h+var_390]
0x18000da73  test    rcx, rcx
0x18000da76  jz      short loc_18000DAA7
0x18000da78  mov     rax, [rcx]
0x18000da7b  lea     rdx, [rsp+3F0h+pguid]
0x18000da80  mov     rax, [rax+20h]
0x18000da84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da89  mov     rcx, [rsp+3F0h+var_390]
0x18000da8e  mov     rax, [rcx]
0x18000da91  mov     rax, [rax+18h]
0x18000da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da9a  mov     [rsp+3F0h+var_398], eax
0x18000da9e  mov     [rsp+3F0h+var_388], ebx
0x18000daa2  jmp     loc_18000D82F
0x18000daa7  mov     rdx, rdi; char *
0x18000daaa  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000daaf  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000dab4  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000dab9  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000dabe  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000dac3  jmp     loc_18000D82A
0x18000dac8  mov     edi, 104h
0x18000dacd  jmp     loc_18000D878
0x18000dad2  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000dad7  xor     edx, edx; bInheritHandle
0x18000dad9  mov     ecx, 400h; dwDesiredAccess
0x18000dade  call    cs:__imp_OpenProcess
0x18000dae4  mov     r14, rax
0x18000dae7  test    rax, rax
0x18000daea  jz      loc_18000D8B3
0x18000daf0  mov     [rsp+3F0h+ReturnLength], r15; ReturnLength
0x18000daf5  mov     r9d, 110h; ProcessInformationLength
0x18000dafb  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000db02  mov     edx, 1Bh; ProcessInformationClass
0x18000db07  mov     rcx, rax; ProcessHandle
0x18000db0a  call    cs:__imp_NtQueryInformationProcess
0x18000db10  mov     ebx, eax
0x18000db12  or      ebx, 10000000h
0x18000db18  jl      short loc_18000DB4C
0x18000db1a  mov     edx, 5Ch ; '\'; Ch
0x18000db1f  mov     rcx, [rbp+2F0h+Str]; Str
0x18000db26  call    cs:__imp_wcsrchr
0x18000db2c  test    rax, rax
0x18000db2f  jnz     short loc_18000DB3A
0x18000db31  mov     rax, [rbp+2F0h+Str]
0x18000db38  jmp     short loc_18000DB3E
0x18000db3a  add     rax, 2
0x18000db3e  mov     edx, edi; unsigned __int64
0x18000db40  mov     r8, rax; unsigned __int16 *
0x18000db43  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000db47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000db4c  mov     rcx, r14; hObject
0x18000db4f  call    cs:__imp_CloseHandle
0x18000db55  jmp     loc_18000D8B3
0x18000db5a  xor     edx, edx; lpTlsValue
0x18000db5c  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000db62  call    cs:__imp_TlsSetValue
0x18000db68  test    eax, eax
0x18000db6a  jnz     loc_18000D8E4
0x18000db70  call    cs:__imp_GetLastError
0x18000db76  jmp     loc_18000D8E4
```
