# RpcUnRegisterAsyncNotification

- ea: `0x18001b510`
- end: `0x18001b9c0`
- name: `RpcUnRegisterAsyncNotification`
- size: `1200`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b0d0`
- `0x18001b0f0`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x18001b510`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b93e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b93e`
- `ntdll!NtQueryInformationProcess` at `0x18001b91c`
- `ntdll!NtQueryInformationProcess` at `0x18001b91c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b71e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b99a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b71e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b99a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b613`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b613`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b96e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b96e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b579`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b579`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b5f0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b5f0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b8ee`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b8ee`

## string_xrefs

- `0x18001b795`: `%s with Trace ID 0x%x Completed`
- `0x18001b855`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001b7cf`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x18001b510  push    rbp
0x18001b512  push    rbx
0x18001b513  push    rsi
0x18001b514  push    rdi
0x18001b515  push    r12
0x18001b517  push    r13
0x18001b519  push    r14
0x18001b51b  push    r15
0x18001b51d  lea     rbp, [rsp-2B8h]
0x18001b525  sub     rsp, 3B8h
0x18001b52c  mov     rax, cs:__security_cookie
0x18001b533  xor     rax, rsp
0x18001b536  mov     [rbp+2F0h+var_50], rax
0x18001b53d  mov     rsi, rcx
0x18001b540  xor     r12d, r12d
0x18001b543  mov     ebx, r12d
0x18001b546  lea     r13, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001b54d  mov     [rsp+3F0h+var_3B0], r13
0x18001b552  mov     edi, 1
0x18001b557  mov     [rsp+3F0h+var_394], edi
0x18001b55b  mov     [rsp+3F0h+var_390], r12
0x18001b560  lea     r14, aRpcunregistera; "RpcUnRegisterAsyncNotification"
0x18001b567  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18001b56e  jnz     loc_18001B808
0x18001b574  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18001b579  call    cs:__imp_CoCreateGuid
0x18001b580  nop     dword ptr [rax+rax+00h]
0x18001b585  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x18001b58d  inc     edi
0x18001b58f  mov     [rsp+3F0h+var_398], edi
0x18001b593  mov     [rsp+3F0h+var_388], r12d
0x18001b598  lea     r15, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001b59f  mov     [rsp+3F0h+var_3B0], r15
0x18001b5a4  mov     [rsp+3F0h+var_380], r14
0x18001b5a9  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001b5b2  mov     [rbp+2F0h+var_370], r12d
0x18001b5b6  xor     edx, edx; Val
0x18001b5b8  mov     r8d, 208h; Size
0x18001b5be  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18001b5c2  call    memset_0
0x18001b5c7  cmp     [rbp+2F0h+var_370], ebx
0x18001b5ca  jnz     loc_18001B751
0x18001b5d0  mov     r14d, r12d
0x18001b5d3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b5da  jnz     loc_18001B8D7
0x18001b5e0  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001b5e9  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18001b5ee  xor     ecx, ecx; Binding
0x18001b5f0  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001b5f7  nop     dword ptr [rax+rax+00h]
0x18001b5fc  mov     edi, eax
0x18001b5fe  test    eax, eax
0x18001b600  jg      loc_18001B743
0x18001b606  test    edi, edi
0x18001b608  js      short loc_18001B628
0x18001b60a  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18001b60f  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18001b613  call    cs:__imp_ProcessIdToSessionId
0x18001b61a  nop     dword ptr [rax+rax+00h]
0x18001b61f  test    r14d, r14d
0x18001b622  jnz     loc_18001B8E2
0x18001b628  cmp     [rbp+2F0h+var_370], ebx
0x18001b62b  jnz     loc_18001B7AB
0x18001b631  test    rsi, rsi
0x18001b634  jz      loc_18001B6E1
0x18001b63a  mov     r14, [rsi]
0x18001b63d  test    r14, r14
0x18001b640  jz      loc_18001B986
0x18001b646  mov     rbx, [r14+638h]
0x18001b64d  test    rbx, rbx
0x18001b650  jz      short loc_18001B661
0x18001b652  mov     rax, [rbx]
0x18001b655  mov     rcx, rbx
0x18001b658  mov     rax, [rax+8]
0x18001b65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b661  mov     rax, [rbx]
0x18001b664  mov     rcx, rbx
0x18001b667  mov     rax, [rax+20h]
0x18001b66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b670  mov     edi, eax
0x18001b672  mov     rdx, [r14]
0x18001b675  mov     rcx, r14
0x18001b678  mov     rax, [rdx+10h]
0x18001b67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b681  mov     [rsi], r12
0x18001b684  mov     [rsp+3F0h+var_3B0], r15
0x18001b689  cmp     [rbp+2F0h+var_370], 0
0x18001b68d  jnz     loc_18001B77E
0x18001b693  mov     [rsp+3F0h+var_3B0], r13
0x18001b698  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001b69f  jnz     short loc_18001B70A
0x18001b6a1  mov     [rsp+3F0h+var_390], r12
0x18001b6a6  test    rbx, rbx
0x18001b6a9  jz      short loc_18001B6BB
0x18001b6ab  mov     rax, [rbx]
0x18001b6ae  mov     rcx, rbx
0x18001b6b1  mov     rax, [rax+10h]
0x18001b6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6ba  nop
0x18001b6bb  mov     eax, edi
0x18001b6bd  mov     rcx, [rbp+2F0h+var_50]
0x18001b6c4  xor     rcx, rsp; StackCookie
0x18001b6c7  call    __security_check_cookie
0x18001b6cc  add     rsp, 3B8h
0x18001b6d3  pop     r15
0x18001b6d5  pop     r14
0x18001b6d7  pop     r13
0x18001b6d9  pop     r12
0x18001b6db  pop     rdi
0x18001b6dc  pop     rsi
0x18001b6dd  pop     rbx
0x18001b6de  pop     rbp
0x18001b6df  retn
0x18001b6e1  lea     r8, aPhnotify; "phNotify"
0x18001b6e8  lea     r9, aRpcunregistera; "RpcUnRegisterAsyncNotification"
0x18001b6ef  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001b6f6  mov     ecx, 8; int
0x18001b6fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b700  mov     edi, 80070057h
0x18001b705  jmp     loc_18001B684
0x18001b70a  cmp     [rsp+3F0h+var_388], 0
0x18001b70f  jnz     short loc_18001B6A1
0x18001b711  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001b717  cmp     ecx, 0FFFFFFFFh
0x18001b71a  jz      short loc_18001B6A1
0x18001b71c  xor     edx, edx; lpTlsValue
0x18001b71e  call    cs:__imp_TlsSetValue
0x18001b725  nop     dword ptr [rax+rax+00h]
0x18001b72a  test    eax, eax
0x18001b72c  jnz     loc_18001B992
0x18001b732  call    cs:__imp_GetLastError
0x18001b739  nop     dword ptr [rax+rax+00h]
0x18001b73e  jmp     loc_18001B9AE
0x18001b743  movzx   edi, ax
0x18001b746  or      edi, 80070000h
0x18001b74c  jmp     loc_18001B606
0x18001b751  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b758  jz      loc_18001B5D0
0x18001b75e  mov     r9d, [rsp+3F0h+var_398]
0x18001b763  mov     r8, [rsp+3F0h+var_380]
0x18001b768  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18001b76f  mov     ecx, 2; int
0x18001b774  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b779  jmp     loc_18001B5D0
0x18001b77e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b785  jz      loc_18001B693
0x18001b78b  mov     r9d, [rsp+3F0h+var_398]
0x18001b790  mov     r8, [rsp+3F0h+var_380]
0x18001b795  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18001b79c  mov     ecx, 2; int
0x18001b7a1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b7a6  jmp     loc_18001B693
0x18001b7ab  test    edi, edi
0x18001b7ad  js      short loc_18001B7E5
0x18001b7af  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b7b6  jz      loc_18001B631
0x18001b7bc  lea     rax, [rbp+2F0h+var_36C]
0x18001b7c0  mov     [rsp+3F0h+ReturnLength], rax
0x18001b7c5  mov     r9d, [rsp+3F0h+Pid]
0x18001b7ca  mov     r8d, [rsp+3F0h+Pid+4]
0x18001b7cf  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18001b7d6  mov     ecx, 2; int
0x18001b7db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b7e0  jmp     loc_18001B631
0x18001b7e5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b7ec  jz      loc_18001B631
0x18001b7f2  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18001b7f9  mov     ecx, 2; int
0x18001b7fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b803  jmp     loc_18001B631
0x18001b808  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18001b80f  jz      short loc_18001B82F
0x18001b811  mov     [rsp+3F0h+ReturnLength], r14
0x18001b816  mov     r9d, edi
0x18001b819  lea     r8, [rsp+3F0h+var_3B0]
0x18001b81e  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18001b825  mov     ecx, 2; int
0x18001b82a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b82f  mov     [rsp+3F0h+var_3C0], r12
0x18001b834  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18001b839  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001b83e  test    eax, eax
0x18001b840  js      short loc_18001B866
0x18001b842  cmp     [rsp+3F0h+var_3C0], rbx
0x18001b847  jz      short loc_18001B866
0x18001b849  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18001b850  jz      short loc_18001B866
0x18001b852  mov     r8d, edi
0x18001b855  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18001b85c  mov     ecx, 2; int
0x18001b861  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b866  xor     edx, edx; char *
0x18001b868  xor     ecx, ecx; lpTlsValue
0x18001b86a  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001b86f  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18001b874  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001b879  test    eax, eax
0x18001b87b  js      short loc_18001B8B6
0x18001b87d  mov     rcx, [rsp+3F0h+var_390]
0x18001b882  test    rcx, rcx
0x18001b885  jz      short loc_18001B8B6
0x18001b887  mov     rax, [rcx]
0x18001b88a  lea     rdx, [rsp+3F0h+pguid]
0x18001b88f  mov     rax, [rax+20h]
0x18001b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b898  mov     rcx, [rsp+3F0h+var_390]
0x18001b89d  mov     rax, [rcx]
0x18001b8a0  mov     rax, [rax+18h]
0x18001b8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a9  mov     [rsp+3F0h+var_398], eax
0x18001b8ad  mov     [rsp+3F0h+var_388], edi
0x18001b8b1  jmp     loc_18001B598
0x18001b8b6  mov     rdx, r14; char *
0x18001b8b9  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18001b8be  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001b8c3  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18001b8c8  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18001b8cd  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18001b8d2  jmp     loc_18001B593
0x18001b8d7  mov     r14d, 104h
0x18001b8dd  jmp     loc_18001B5E0
0x18001b8e2  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18001b8e7  xor     edx, edx; bInheritHandle
0x18001b8e9  mov     ecx, 400h; dwDesiredAccess
0x18001b8ee  call    cs:__imp_OpenProcess
0x18001b8f5  nop     dword ptr [rax+rax+00h]
0x18001b8fa  mov     r15, rax
0x18001b8fd  test    rax, rax
0x18001b900  jz      short loc_18001B97A
0x18001b902  mov     [rsp+3F0h+ReturnLength], r12; ReturnLength
0x18001b907  mov     r9d, 110h; ProcessInformationLength
0x18001b90d  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18001b914  mov     edx, 1Bh; ProcessInformationClass
0x18001b919  mov     rcx, rax; ProcessHandle
0x18001b91c  call    cs:__imp_NtQueryInformationProcess
0x18001b923  nop     dword ptr [rax+rax+00h]
0x18001b928  mov     edi, eax
0x18001b92a  or      edi, 10000000h
0x18001b930  jl      short loc_18001B96B
0x18001b932  mov     edx, 5Ch ; '\'; Ch
0x18001b937  mov     rcx, [rbp+2F0h+Str]; Str
0x18001b93e  call    cs:__imp_wcsrchr
0x18001b945  nop     dword ptr [rax+rax+00h]
0x18001b94a  test    rax, rax
0x18001b94d  jnz     short loc_18001B958
0x18001b94f  mov     rax, [rbp+2F0h+Str]
0x18001b956  jmp     short loc_18001B95C
0x18001b958  add     rax, 2
0x18001b95c  mov     edx, r14d; unsigned __int64
0x18001b95f  mov     r8, rax; unsigned __int16 *
0x18001b962  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18001b966  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b96b  mov     rcx, r15; hObject
0x18001b96e  call    cs:__imp_CloseHandle
0x18001b975  nop     dword ptr [rax+rax+00h]
0x18001b97a  lea     r15, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001b981  jmp     loc_18001B628
0x18001b986  lea     r8, aPnotifyhandle; "pNotifyHandle"
0x18001b98d  jmp     loc_18001B6E8
0x18001b992  xor     edx, edx; lpTlsValue
0x18001b994  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001b99a  call    cs:__imp_TlsSetValue
0x18001b9a1  nop     dword ptr [rax+rax+00h]
0x18001b9a6  test    eax, eax
0x18001b9a8  jnz     loc_18001B6A1
0x18001b9ae  call    cs:__imp_GetLastError
0x18001b9b5  nop     dword ptr [rax+rax+00h]
0x18001b9ba  jmp     loc_18001B6A1
```
