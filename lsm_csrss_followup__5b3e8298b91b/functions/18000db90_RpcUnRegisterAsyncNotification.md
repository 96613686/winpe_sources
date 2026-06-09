# RpcUnRegisterAsyncNotification

- ea: `0x18000db90`
- end: `0x18000dffd`
- name: `RpcUnRegisterAsyncNotification`
- size: `1133`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d790`
- `0x18000d7b0`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18000db90`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000df93`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000df93`
- `ntdll!NtQueryInformationProcess` at `0x18000df77`
- `ntdll!NtQueryInformationProcess` at `0x18000df77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dd8b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dfe3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dd8b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dfe3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000dc87`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000dc87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfbd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000dbf9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000dbf9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000dc6a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000dc6a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000df4f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000df4f`

## string_xrefs

- `0x18000ddf6`: `%s with Trace ID 0x%x Completed`
- `0x18000deb6`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000de30`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcUnRegisterAsyncNotification(_QWORD **a1)
{
  __int64 v2; // rbx
  unsigned int v3; // r14d
  RPC_STATUS v4; // eax
  int v5; // edi
  _QWORD *v6; // r14
  unsigned int v7; // edi
  const char *v9; // r8
  HANDLE v10; // rax
  void *v11; // r15
  NTSTATUS InformationProcess; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  struct CTraceBase *v15; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  const char *v21; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v23; // [rsp+80h] [rbp-80h]
  unsigned __int16 v24[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v2 = 0;
  v16 = &CTraceBase::`vftable';
  v18[1] = 1;
  v19 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v16, 1, "RpcUnRegisterAsyncNotification");
    v15 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v15) >= 0 && v15 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v19) >= 0 && v19 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v19 + 32LL))(v19, &pguid);
      v18[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v19 + 24LL))(v19);
      v20 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v16, "RpcUnRegisterAsyncNotification");
    CTraceBase::GenerateTraceID(&pguid, v18);
  }
  else
  {
    CoCreateGuid(&pguid);
    v18[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v20 = 0;
LABEL_4:
  v16 = &CRpcCallTrace::`vftable';
  v21 = "RpcUnRegisterAsyncNotification";
  *(_QWORD *)Pid = -1;
  v23 = 0;
  memset_0(v24, 0, 0x208u);
  if ( v23 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v21, v18[0]);
  v3 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v3 = 260;
  *(_QWORD *)Pid = -1;
  v4 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v3 )
    {
      v10 = OpenProcess(0x400u, 0, Pid[1]);
      v11 = v10;
      if ( v10 )
      {
        InformationProcess = NtQueryInformationProcess(v10, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v5 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v13 = wcsrchr(Str, 0x5Cu);
          if ( v13 )
            v14 = v13 + 1;
          else
            v14 = Str;
          StringCchCopyW(v24, v3, v14);
        }
        CloseHandle(v11);
      }
    }
  }
  if ( v23 )
  {
    if ( v5 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v24);
    }
  }
  if ( !a1 )
  {
    v9 = "phNotify";
LABEL_23:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v9, "RpcUnRegisterAsyncNotification");
    v7 = -2147024809;
    goto LABEL_17;
  }
  v6 = *a1;
  if ( !*a1 )
  {
    v9 = "pNotifyHandle";
    goto LABEL_23;
  }
  v2 = v6[199];
  if ( v2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(v6[199]);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
  (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  *a1 = 0;
LABEL_17:
  v16 = &CRpcCallTrace::`vftable';
  if ( v23 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v21, v18[0]);
  v16 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v20 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_19;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_19:
  v19 = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return v7;
}

```

## disassembly

```asm
0x18000db90  push    rbp
0x18000db92  push    rbx
0x18000db93  push    rsi
0x18000db94  push    rdi
0x18000db95  push    r12
0x18000db97  push    r13
0x18000db99  push    r14
0x18000db9b  push    r15
0x18000db9d  lea     rbp, [rsp-2B8h]
0x18000dba5  sub     rsp, 3B8h
0x18000dbac  mov     rax, cs:__security_cookie
0x18000dbb3  xor     rax, rsp
0x18000dbb6  mov     [rbp+2F0h+var_50], rax
0x18000dbbd  mov     rsi, rcx
0x18000dbc0  xor     r12d, r12d
0x18000dbc3  mov     ebx, r12d
0x18000dbc6  lea     r13, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000dbcd  mov     [rsp+3F0h+var_3B0], r13
0x18000dbd2  mov     edi, 1
0x18000dbd7  mov     [rsp+3F0h+var_394], edi
0x18000dbdb  mov     [rsp+3F0h+var_390], r12
0x18000dbe0  lea     r14, aRpcunregistera; "RpcUnRegisterAsyncNotification"
0x18000dbe7  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000dbee  jnz     loc_18000DE69
0x18000dbf4  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000dbf9  call    cs:__imp_CoCreateGuid
0x18000dbff  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x18000dc07  inc     edi
0x18000dc09  mov     [rsp+3F0h+var_398], edi
0x18000dc0d  mov     [rsp+3F0h+var_388], r12d
0x18000dc12  lea     r15, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000dc19  mov     [rsp+3F0h+var_3B0], r15
0x18000dc1e  mov     [rsp+3F0h+var_380], r14
0x18000dc23  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000dc2c  mov     [rbp+2F0h+var_370], r12d
0x18000dc30  xor     edx, edx; Val
0x18000dc32  mov     r8d, 208h; Size
0x18000dc38  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000dc3c  call    memset_0
0x18000dc41  cmp     [rbp+2F0h+var_370], ebx
0x18000dc44  jnz     loc_18000DDB2
0x18000dc4a  mov     r14d, r12d
0x18000dc4d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000dc54  jnz     loc_18000DF38
0x18000dc5a  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000dc63  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000dc68  xor     ecx, ecx; Binding
0x18000dc6a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000dc70  mov     edi, eax
0x18000dc72  test    eax, eax
0x18000dc74  jg      loc_18000DDA4
0x18000dc7a  test    edi, edi
0x18000dc7c  js      short loc_18000DC96
0x18000dc7e  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000dc83  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000dc87  call    cs:__imp_ProcessIdToSessionId
0x18000dc8d  test    r14d, r14d
0x18000dc90  jnz     loc_18000DF43
0x18000dc96  cmp     [rbp+2F0h+var_370], ebx
0x18000dc99  jnz     loc_18000DE0C
0x18000dc9f  test    rsi, rsi
0x18000dca2  jz      loc_18000DD4E
0x18000dca8  mov     r14, [rsi]
0x18000dcab  test    r14, r14
0x18000dcae  jz      loc_18000DFCF
0x18000dcb4  mov     rbx, [r14+638h]
0x18000dcbb  test    rbx, rbx
0x18000dcbe  jz      short loc_18000DCCF
0x18000dcc0  mov     rax, [rbx]
0x18000dcc3  mov     rcx, rbx
0x18000dcc6  mov     rax, [rax+8]
0x18000dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccf  mov     rax, [rbx]
0x18000dcd2  mov     rcx, rbx
0x18000dcd5  mov     rax, [rax+20h]
0x18000dcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcde  mov     edi, eax
0x18000dce0  mov     rdx, [r14]
0x18000dce3  mov     rcx, r14
0x18000dce6  mov     rax, [rdx+10h]
0x18000dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcef  mov     [rsi], r12
0x18000dcf2  mov     [rsp+3F0h+var_3B0], r15
0x18000dcf7  cmp     [rbp+2F0h+var_370], 0
0x18000dcfb  jnz     loc_18000DDDF
0x18000dd01  mov     [rsp+3F0h+var_3B0], r13
0x18000dd06  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000dd0d  jnz     short loc_18000DD77
0x18000dd0f  mov     [rsp+3F0h+var_390], r12
0x18000dd14  test    rbx, rbx
0x18000dd17  jz      short loc_18000DD29
0x18000dd19  mov     rax, [rbx]
0x18000dd1c  mov     rcx, rbx
0x18000dd1f  mov     rax, [rax+10h]
0x18000dd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd28  nop
0x18000dd29  mov     eax, edi
0x18000dd2b  mov     rcx, [rbp+2F0h+var_50]
0x18000dd32  xor     rcx, rsp; StackCookie
0x18000dd35  call    __security_check_cookie
0x18000dd3a  add     rsp, 3B8h
0x18000dd41  pop     r15
0x18000dd43  pop     r14
0x18000dd45  pop     r13
0x18000dd47  pop     r12
0x18000dd49  pop     rdi
0x18000dd4a  pop     rsi
0x18000dd4b  pop     rbx
0x18000dd4c  pop     rbp
0x18000dd4d  retn
0x18000dd4e  lea     r8, aPhnotify; "phNotify"
0x18000dd55  lea     r9, aRpcunregistera; "RpcUnRegisterAsyncNotification"
0x18000dd5c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000dd63  mov     ecx, 8; int
0x18000dd68  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dd6d  mov     edi, 80070057h
0x18000dd72  jmp     loc_18000DCF2
0x18000dd77  cmp     [rsp+3F0h+var_388], 0
0x18000dd7c  jnz     short loc_18000DD0F
0x18000dd7e  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000dd84  cmp     ecx, 0FFFFFFFFh
0x18000dd87  jz      short loc_18000DD0F
0x18000dd89  xor     edx, edx; lpTlsValue
0x18000dd8b  call    cs:__imp_TlsSetValue
0x18000dd91  test    eax, eax
0x18000dd93  jnz     loc_18000DFDB
0x18000dd99  call    cs:__imp_GetLastError
0x18000dd9f  jmp     loc_18000DFF1
0x18000dda4  movzx   edi, ax
0x18000dda7  or      edi, 80070000h
0x18000ddad  jmp     loc_18000DC7A
0x18000ddb2  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ddb9  jz      loc_18000DC4A
0x18000ddbf  mov     r9d, [rsp+3F0h+var_398]
0x18000ddc4  mov     r8, [rsp+3F0h+var_380]
0x18000ddc9  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000ddd0  mov     ecx, 2; int
0x18000ddd5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ddda  jmp     loc_18000DC4A
0x18000dddf  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000dde6  jz      loc_18000DD01
0x18000ddec  mov     r9d, [rsp+3F0h+var_398]
0x18000ddf1  mov     r8, [rsp+3F0h+var_380]
0x18000ddf6  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000ddfd  mov     ecx, 2; int
0x18000de02  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de07  jmp     loc_18000DD01
0x18000de0c  test    edi, edi
0x18000de0e  js      short loc_18000DE46
0x18000de10  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000de17  jz      loc_18000DC9F
0x18000de1d  lea     rax, [rbp+2F0h+var_36C]
0x18000de21  mov     [rsp+3F0h+ReturnLength], rax
0x18000de26  mov     r9d, [rsp+3F0h+Pid]
0x18000de2b  mov     r8d, [rsp+3F0h+Pid+4]
0x18000de30  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000de37  mov     ecx, 2; int
0x18000de3c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de41  jmp     loc_18000DC9F
0x18000de46  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000de4d  jz      loc_18000DC9F
0x18000de53  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000de5a  mov     ecx, 2; int
0x18000de5f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de64  jmp     loc_18000DC9F
0x18000de69  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000de70  jz      short loc_18000DE90
0x18000de72  mov     [rsp+3F0h+ReturnLength], r14
0x18000de77  mov     r9d, edi
0x18000de7a  lea     r8, [rsp+3F0h+var_3B0]
0x18000de7f  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000de86  mov     ecx, 2; int
0x18000de8b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de90  mov     [rsp+3F0h+var_3C0], r12
0x18000de95  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000de9a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000de9f  test    eax, eax
0x18000dea1  js      short loc_18000DEC7
0x18000dea3  cmp     [rsp+3F0h+var_3C0], rbx
0x18000dea8  jz      short loc_18000DEC7
0x18000deaa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000deb1  jz      short loc_18000DEC7
0x18000deb3  mov     r8d, edi
0x18000deb6  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000debd  mov     ecx, 2; int
0x18000dec2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dec7  xor     edx, edx; char *
0x18000dec9  xor     ecx, ecx; lpTlsValue
0x18000decb  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ded0  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000ded5  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000deda  test    eax, eax
0x18000dedc  js      short loc_18000DF17
0x18000dede  mov     rcx, [rsp+3F0h+var_390]
0x18000dee3  test    rcx, rcx
0x18000dee6  jz      short loc_18000DF17
0x18000dee8  mov     rax, [rcx]
0x18000deeb  lea     rdx, [rsp+3F0h+pguid]
0x18000def0  mov     rax, [rax+20h]
0x18000def4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def9  mov     rcx, [rsp+3F0h+var_390]
0x18000defe  mov     rax, [rcx]
0x18000df01  mov     rax, [rax+18h]
0x18000df05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df0a  mov     [rsp+3F0h+var_398], eax
0x18000df0e  mov     [rsp+3F0h+var_388], edi
0x18000df12  jmp     loc_18000DC12
0x18000df17  mov     rdx, r14; char *
0x18000df1a  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000df1f  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000df24  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000df29  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000df2e  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000df33  jmp     loc_18000DC0D
0x18000df38  mov     r14d, 104h
0x18000df3e  jmp     loc_18000DC5A
0x18000df43  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000df48  xor     edx, edx; bInheritHandle
0x18000df4a  mov     ecx, 400h; dwDesiredAccess
0x18000df4f  call    cs:__imp_OpenProcess
0x18000df55  mov     r15, rax
0x18000df58  test    rax, rax
0x18000df5b  jz      short loc_18000DFC3
0x18000df5d  mov     [rsp+3F0h+ReturnLength], r12; ReturnLength
0x18000df62  mov     r9d, 110h; ProcessInformationLength
0x18000df68  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000df6f  mov     edx, 1Bh; ProcessInformationClass
0x18000df74  mov     rcx, rax; ProcessHandle
0x18000df77  call    cs:__imp_NtQueryInformationProcess
0x18000df7d  mov     edi, eax
0x18000df7f  or      edi, 10000000h
0x18000df85  jl      short loc_18000DFBA
0x18000df87  mov     edx, 5Ch ; '\'; Ch
0x18000df8c  mov     rcx, [rbp+2F0h+Str]; Str
0x18000df93  call    cs:__imp_wcsrchr
0x18000df99  test    rax, rax
0x18000df9c  jnz     short loc_18000DFA7
0x18000df9e  mov     rax, [rbp+2F0h+Str]
0x18000dfa5  jmp     short loc_18000DFAB
0x18000dfa7  add     rax, 2
0x18000dfab  mov     edx, r14d; unsigned __int64
0x18000dfae  mov     r8, rax; unsigned __int16 *
0x18000dfb1  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000dfb5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfba  mov     rcx, r15; hObject
0x18000dfbd  call    cs:__imp_CloseHandle
0x18000dfc3  lea     r15, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000dfca  jmp     loc_18000DC96
0x18000dfcf  lea     r8, aPnotifyhandle; "pNotifyHandle"
0x18000dfd6  jmp     loc_18000DD55
0x18000dfdb  xor     edx, edx; lpTlsValue
0x18000dfdd  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000dfe3  call    cs:__imp_TlsSetValue
0x18000dfe9  test    eax, eax
0x18000dfeb  jnz     loc_18000DD0F
0x18000dff1  call    cs:__imp_GetLastError
0x18000dff7  jmp     loc_18000DD0F
```
