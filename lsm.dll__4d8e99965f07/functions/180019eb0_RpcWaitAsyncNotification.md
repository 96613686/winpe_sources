# RpcWaitAsyncNotification

- ea: `0x180019eb0`
- end: `0x18001a50a`
- name: `RpcWaitAsyncNotification`
- size: `1626`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180019eb0`
- `0x18001a510`
- `0x18001a6f8`
- `0x18001a900`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a427`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a427`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001a499`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001a4cb`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001a499`
- `ntdll!RtlCaptureStackBackTrace` at `0x18001a4cb`
- `ntdll!NtQueryInformationProcess` at `0x18001a405`
- `ntdll!NtQueryInformationProcess` at `0x18001a405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a1aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a4e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a1aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a4e4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019fbf`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a456`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180019f23`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180019f23`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019f9c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019f9c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a3d7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a3d7`

## string_xrefs

- `0x18001a246`: `%s with Trace ID 0x%x Completed`
- `0x18001a33b`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001a280`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall RpcWaitAsyncNotification(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  struct IPublicNotification *v8; // rbx
  unsigned int v9; // esi
  RPC_STATUS v10; // eax
  int v11; // edi
  void *v12; // rax
  void *v13; // rdi
  char v14; // al
  int v15; // eax
  int v16; // r15d
  char v17; // al
  void **v18; // rax
  const char *v19; // r8
  HANDLE v20; // rax
  void *v21; // r13
  NTSTATUS InformationProcess; // eax
  wchar_t *v23; // rax
  wchar_t *v24; // rax
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  void **v28; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  const char *v33; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+80h] [rbp-80h]
  unsigned __int16 v36[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v4 = a4;
  v27 = a4;
  v8 = 0;
  v28 = &CTraceBase::`vftable';
  v30[1] = 1;
  v31 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v28, 1, "RpcWaitAsyncNotification");
    *(_QWORD *)BackTraceHash = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)BackTraceHash) >= 0
      && *(_QWORD *)BackTraceHash
      && (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    }
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v31) >= 0 && v31 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v31 + 32LL))(v31, &pguid);
      v30[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v31 + 24LL))(v31);
      v32 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v28, "RpcWaitAsyncNotification");
    CTraceBase::GenerateTraceID(&pguid, v30);
  }
  else
  {
    CoCreateGuid(&pguid);
    v30[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v32 = 0;
LABEL_4:
  v28 = &CRpcCallTrace::`vftable';
  v33 = "RpcWaitAsyncNotification";
  *(_QWORD *)Pid = -1;
  v35 = 0;
  memset_0(v36, 0, 0x208u);
  if ( v35 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v33, v30[0]);
  v9 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v9 = 260;
  *(_QWORD *)Pid = -1;
  v10 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v9 )
    {
      v20 = OpenProcess(0x400u, 0, Pid[1]);
      v21 = v20;
      if ( v20 )
      {
        InformationProcess = NtQueryInformationProcess(v20, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v11 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v23 = wcsrchr(Str, 0x5Cu);
          if ( v23 )
            v24 = v23 + 1;
          else
            v24 = Str;
          StringCchCopyW(v36, v9, v24);
        }
        CloseHandle(v21);
      }
      v4 = v27;
    }
  }
  if ( v35 )
  {
    if ( v11 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v36);
    }
  }
  if ( !a1 )
  {
    v19 = "pAsyncState";
LABEL_34:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v19, "RpcWaitAsyncNotification");
    goto LABEL_28;
  }
  if ( !a2 )
  {
    v19 = "hNotify";
    goto LABEL_34;
  }
  if ( !a3 )
  {
    v19 = "ppSessionChange";
    goto LABEL_34;
  }
  v8 = *(struct IPublicNotification **)(a2 + 1592);
  if ( v8 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*(_QWORD *)(a2 + 1592));
  v12 = operator new(0x670u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(v12);
    *(_QWORD *)v13 = &CAsyncNotifyParams::`vftable';
    *((_QWORD *)v13 + 199) = a1;
    *((_QWORD *)v13 + 200) = a3;
    *((_QWORD *)v13 + 201) = v4;
    *((_DWORD *)v13 + 404) = -2147467263;
    *((_DWORD *)v13 + 405) = 0;
    *((_QWORD *)v13 + 203) = 0;
    *((_QWORD *)v13 + 204) = 0;
    *((_DWORD *)v13 + 410) = 0;
    *((_DWORD *)v13 + 411) = 0;
    if ( *((_DWORD *)v13 + 3) == 1 )
    {
      v14 = _InterlockedIncrement((volatile signed __int32 *)v13 + 8);
      BackTraceHash[0] = 0;
      if ( g_bCaptureObjectStackTrace == 1 )
        RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v13 + 6 * (v14 & 0x1F) + 5, BackTraceHash);
    }
    _InterlockedIncrement64((volatile signed __int64 *)v13 + 3);
    v15 = CAsyncNotifyParams::Initialize((CAsyncNotifyParams *)v13, v8);
    v16 = v15;
    if ( v15 < 0 )
    {
      _DbgPrintMessage(8, "AsyncParams->Initialize failed: 0x%x in %s", v15, "RpcWaitAsyncNotification");
      *((_DWORD *)v13 + 404) = v16;
      CAsyncNotifyParams::UnsubscribeFromNotifications((CAsyncNotifyParams *)v13);
    }
    else
    {
      *((_DWORD *)v13 + 404) = v15;
    }
    if ( *((_DWORD *)v13 + 3) == 1 )
    {
      BackTraceHash[0] = 0;
      v17 = _InterlockedIncrement((volatile signed __int32 *)v13 + 8);
      if ( g_bCaptureObjectStackTrace == 1 )
        RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v13 + 6 * (v17 & 0x1F) + 5, BackTraceHash);
    }
    if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 3, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v13 + 40LL))(v13, 1);
  }
LABEL_28:
  v28 = &CRpcCallTrace::`vftable';
  if ( v35 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v33, v30[0]);
  v18 = &CTraceBase::`vftable';
  v28 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v32 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      LODWORD(v18) = TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0);
      if ( (_DWORD)v18 )
        goto LABEL_30;
    }
    else
    {
      GetLastError();
    }
    LODWORD(v18) = GetLastError();
  }
LABEL_30:
  v31 = 0;
  if ( v8 )
    LODWORD(v18) = (*(__int64 (__fastcall **)(struct IPublicNotification *))(*(_QWORD *)v8 + 16LL))(v8);
  return (int)v18;
}

```

## disassembly

```asm
0x180019eb0  push    rbp
0x180019eb2  push    rbx
0x180019eb3  push    rsi
0x180019eb4  push    rdi
0x180019eb5  push    r12
0x180019eb7  push    r13
0x180019eb9  push    r14
0x180019ebb  push    r15
0x180019ebd  lea     rbp, [rsp-2B8h]
0x180019ec5  sub     rsp, 3B8h
0x180019ecc  mov     rax, cs:__security_cookie
0x180019ed3  xor     rax, rsp
0x180019ed6  mov     [rbp+2F0h+var_50], rax
0x180019edd  mov     r13, r9
0x180019ee0  mov     [rsp+3F0h+var_3B8], r9
0x180019ee5  mov     r12, r8
0x180019ee8  mov     r15, rdx
0x180019eeb  mov     r14, rcx
0x180019eee  xor     edi, edi
0x180019ef0  mov     ebx, edi
0x180019ef2  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180019ef9  mov     [rsp+3F0h+var_3B0], rax
0x180019efe  mov     [rsp+3F0h+var_394], 1
0x180019f06  mov     [rsp+3F0h+var_390], rdi
0x180019f0b  lea     rsi, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x180019f12  cmp     cs:?g_bEnabled@CTraceBase@@0HA, edi; int CTraceBase::g_bEnabled
0x180019f18  jnz     loc_18001A2E8
0x180019f1e  lea     rcx, [rsp+3F0h+pguid]; pguid
0x180019f23  call    cs:__imp_CoCreateGuid
0x180019f2a  nop     dword ptr [rax+rax+00h]
0x180019f2f  mov     eax, 1
0x180019f34  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180019f3c  inc     eax
0x180019f3e  mov     [rsp+3F0h+var_398], eax
0x180019f42  mov     [rsp+3F0h+var_388], edi
0x180019f46  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180019f4d  mov     [rsp+3F0h+var_3B0], rax
0x180019f52  mov     [rsp+3F0h+var_380], rsi
0x180019f57  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180019f60  mov     [rbp+2F0h+var_370], edi
0x180019f63  xor     edx, edx; Val
0x180019f65  mov     r8d, 208h; Size
0x180019f6b  lea     rcx, [rbp+2F0h+var_36C]; void *
0x180019f6f  call    memset_0
0x180019f74  cmp     [rbp+2F0h+var_370], ebx
0x180019f77  jnz     loc_18001A202
0x180019f7d  mov     esi, edi
0x180019f7f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180019f86  jnz     loc_18001A3C1
0x180019f8c  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180019f95  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x180019f9a  xor     ecx, ecx; Binding
0x180019f9c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180019fa3  nop     dword ptr [rax+rax+00h]
0x180019fa8  mov     edi, eax
0x180019faa  test    eax, eax
0x180019fac  jg      loc_18001A1E8
0x180019fb2  test    edi, edi
0x180019fb4  js      short loc_180019FD3
0x180019fb6  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x180019fbb  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x180019fbf  call    cs:__imp_ProcessIdToSessionId
0x180019fc6  nop     dword ptr [rax+rax+00h]
0x180019fcb  test    esi, esi
0x180019fcd  jnz     loc_18001A3CB
0x180019fd3  cmp     [rbp+2F0h+var_370], ebx
0x180019fd6  jnz     loc_18001A25C
0x180019fdc  test    r14, r14
0x180019fdf  jz      loc_18001A16F
0x180019fe5  test    r15, r15
0x180019fe8  jz      loc_18001A46C
0x180019fee  test    r12, r12
0x180019ff1  jz      loc_18001A1F6
0x180019ff7  mov     rbx, [r15+638h]
0x180019ffe  test    rbx, rbx
0x18001a001  jz      short loc_18001A012
0x18001a003  mov     rax, [rbx]
0x18001a006  mov     rcx, rbx
0x18001a009  mov     rax, [rax+8]
0x18001a00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a012  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a019  mov     ecx, 670h; unsigned __int64
0x18001a01e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a023  mov     rdi, rax
0x18001a026  test    rax, rax
0x18001a029  jz      loc_18001A18E
0x18001a02f  mov     rcx, rax
0x18001a032  call    ??0?$CTSPrivateObject@VIPublicNotificationCallback@@@@QEAA@PEBD@Z; CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(char const *)
0x18001a037  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x18001a03e  mov     [rdi], rax
0x18001a041  mov     [rdi+638h], r14
0x18001a048  mov     [rdi+640h], r12
0x18001a04f  mov     [rdi+648h], r13
0x18001a056  mov     dword ptr [rdi+650h], 80004001h
0x18001a060  xor     r12d, r12d
0x18001a063  mov     [rdi+654h], r12d
0x18001a06a  mov     [rdi+658h], r12
0x18001a071  mov     [rdi+660h], r12
0x18001a078  mov     [rdi+668h], r12d
0x18001a07f  mov     [rdi+66Ch], r12d
0x18001a086  cmp     dword ptr [rdi+0Ch], 1
0x18001a08a  jnz     short loc_18001A0AA
0x18001a08c  mov     eax, 1
0x18001a091  lock xadd [rdi+20h], eax
0x18001a096  inc     eax
0x18001a098  mov     [rsp+3F0h+BackTraceHash], r12d
0x18001a09d  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18001a0a4  jz      loc_18001A478
0x18001a0aa  lock inc qword ptr [rdi+18h]
0x18001a0af  mov     rdx, rbx; struct IPublicNotification *
0x18001a0b2  mov     rcx, rdi; this
0x18001a0b5  call    ?Initialize@CAsyncNotifyParams@@QEAAJPEAVIPublicNotification@@@Z; CAsyncNotifyParams::Initialize(IPublicNotification *)
0x18001a0ba  mov     r15d, eax
0x18001a0bd  test    eax, eax
0x18001a0bf  js      loc_18001A296
0x18001a0c5  mov     [rdi+650h], eax
0x18001a0cb  cmp     dword ptr [rdi+0Ch], 1
0x18001a0cf  jnz     short loc_18001A0EF
0x18001a0d1  mov     [rsp+3F0h+BackTraceHash], r12d
0x18001a0d6  mov     eax, 1
0x18001a0db  lock xadd [rdi+20h], eax
0x18001a0e0  inc     eax
0x18001a0e2  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18001a0e9  jz      loc_18001A4AA
0x18001a0ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001a0f6  lock xadd [rdi+18h], rax
0x18001a0fc  cmp     rax, 1
0x18001a100  jz      loc_18001A1CF
0x18001a106  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001a10d  mov     [rsp+3F0h+var_3B0], rax
0x18001a112  cmp     [rbp+2F0h+var_370], 0
0x18001a116  jnz     loc_18001A22F
0x18001a11c  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001a123  mov     [rsp+3F0h+var_3B0], rax
0x18001a128  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001a12f  jnz     short loc_18001A196
0x18001a131  mov     [rsp+3F0h+var_390], r12
0x18001a136  test    rbx, rbx
0x18001a139  jz      short loc_18001A14B
0x18001a13b  mov     rax, [rbx]
0x18001a13e  mov     rcx, rbx
0x18001a141  mov     rax, [rax+10h]
0x18001a145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a14a  nop
0x18001a14b  mov     rcx, [rbp+2F0h+var_50]
0x18001a152  xor     rcx, rsp; StackCookie
0x18001a155  call    __security_check_cookie
0x18001a15a  add     rsp, 3B8h
0x18001a161  pop     r15
0x18001a163  pop     r14
0x18001a165  pop     r13
0x18001a167  pop     r12
0x18001a169  pop     rdi
0x18001a16a  pop     rsi
0x18001a16b  pop     rbx
0x18001a16c  pop     rbp
0x18001a16d  retn
0x18001a16f  lea     r8, aPasyncstate; "pAsyncState"
0x18001a176  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18001a17d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001a184  mov     ecx, 8; int
0x18001a189  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a18e  xor     r12d, r12d
0x18001a191  jmp     loc_18001A106
0x18001a196  cmp     [rsp+3F0h+var_388], 0
0x18001a19b  jnz     short loc_18001A131
0x18001a19d  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001a1a3  cmp     ecx, 0FFFFFFFFh
0x18001a1a6  jz      short loc_18001A131
0x18001a1a8  xor     edx, edx; lpTlsValue
0x18001a1aa  call    cs:__imp_TlsSetValue
0x18001a1b1  nop     dword ptr [rax+rax+00h]
0x18001a1b6  test    eax, eax
0x18001a1b8  jnz     loc_18001A4DC
0x18001a1be  call    cs:__imp_GetLastError
0x18001a1c5  nop     dword ptr [rax+rax+00h]
0x18001a1ca  jmp     loc_18001A4F8
0x18001a1cf  mov     rax, [rdi]
0x18001a1d2  mov     edx, 1
0x18001a1d7  mov     rcx, rdi
0x18001a1da  mov     rax, [rax+28h]
0x18001a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1e3  jmp     loc_18001A106
0x18001a1e8  movzx   edi, ax
0x18001a1eb  or      edi, 80070000h
0x18001a1f1  jmp     loc_180019FB2
0x18001a1f6  lea     r8, aPpsessionchang; "ppSessionChange"
0x18001a1fd  jmp     loc_18001A176
0x18001a202  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a209  jz      loc_180019F7D
0x18001a20f  mov     r9d, [rsp+3F0h+var_398]
0x18001a214  mov     r8, [rsp+3F0h+var_380]
0x18001a219  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18001a220  mov     ecx, 2; int
0x18001a225  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a22a  jmp     loc_180019F7D
0x18001a22f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a236  jz      loc_18001A11C
0x18001a23c  mov     r9d, [rsp+3F0h+var_398]
0x18001a241  mov     r8, [rsp+3F0h+var_380]
0x18001a246  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18001a24d  mov     ecx, 2; int
0x18001a252  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a257  jmp     loc_18001A11C
0x18001a25c  test    edi, edi
0x18001a25e  js      short loc_18001A2C5
0x18001a260  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a267  jz      loc_180019FDC
0x18001a26d  lea     rax, [rbp+2F0h+var_36C]
0x18001a271  mov     [rsp+3F0h+ReturnLength], rax
0x18001a276  mov     r9d, [rsp+3F0h+Pid]
0x18001a27b  mov     r8d, [rsp+3F0h+Pid+4]
0x18001a280  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18001a287  mov     ecx, 2; int
0x18001a28c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a291  jmp     loc_180019FDC
0x18001a296  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18001a29d  mov     r8d, r15d
0x18001a2a0  lea     rdx, aAsyncparamsIni; "AsyncParams->Initialize failed: 0x%x in"...
0x18001a2a7  mov     ecx, 8; int
0x18001a2ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a2b1  mov     [rdi+650h], r15d
0x18001a2b8  mov     rcx, rdi; this
0x18001a2bb  call    ?UnsubscribeFromNotifications@CAsyncNotifyParams@@QEAAJXZ; CAsyncNotifyParams::UnsubscribeFromNotifications(void)
0x18001a2c0  jmp     loc_18001A0CB
0x18001a2c5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a2cc  jz      loc_180019FDC
0x18001a2d2  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18001a2d9  mov     ecx, 2; int
0x18001a2de  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a2e3  jmp     loc_180019FDC
0x18001a2e8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a2ef  jz      short loc_18001A312
0x18001a2f1  mov     [rsp+3F0h+ReturnLength], rsi
0x18001a2f6  mov     r9d, 1
0x18001a2fc  lea     r8, [rsp+3F0h+var_3B0]
0x18001a301  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18001a308  mov     ecx, 2; int
0x18001a30d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a312  mov     qword ptr [rsp+3F0h+BackTraceHash], rdi
0x18001a317  lea     rcx, [rsp+3F0h+BackTraceHash]; struct CTraceBase **
0x18001a31c  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001a321  test    eax, eax
0x18001a323  js      short loc_18001A34C
0x18001a325  cmp     qword ptr [rsp+3F0h+BackTraceHash], rbx
0x18001a32a  jz      short loc_18001A34C
0x18001a32c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a333  jz      short loc_18001A34C
0x18001a335  mov     r8d, 1
0x18001a33b  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18001a342  mov     ecx, 2; int
0x18001a347  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a34c  xor     edx, edx; char *
0x18001a34e  xor     ecx, ecx; lpTlsValue
0x18001a350  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001a355  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18001a35a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001a35f  test    eax, eax
0x18001a361  js      short loc_18001A3A0
0x18001a363  mov     rcx, [rsp+3F0h+var_390]
0x18001a368  test    rcx, rcx
0x18001a36b  jz      short loc_18001A3A0
0x18001a36d  mov     rax, [rcx]
0x18001a370  lea     rdx, [rsp+3F0h+pguid]
0x18001a375  mov     rax, [rax+20h]
0x18001a379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a37e  mov     rcx, [rsp+3F0h+var_390]
0x18001a383  mov     rax, [rcx]
0x18001a386  mov     rax, [rax+18h]
0x18001a38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a38f  mov     [rsp+3F0h+var_398], eax
0x18001a393  mov     [rsp+3F0h+var_388], 1
0x18001a39b  jmp     loc_180019F46
0x18001a3a0  mov     rdx, rsi; char *
0x18001a3a3  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18001a3a8  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001a3ad  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18001a3b2  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18001a3b7  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18001a3bc  jmp     loc_180019F42
0x18001a3c1  mov     esi, 104h
0x18001a3c6  jmp     loc_180019F8C
0x18001a3cb  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18001a3d0  xor     edx, edx; bInheritHandle
0x18001a3d2  mov     ecx, 400h; dwDesiredAccess
0x18001a3d7  call    cs:__imp_OpenProcess
0x18001a3de  nop     dword ptr [rax+rax+00h]
0x18001a3e3  mov     r13, rax
0x18001a3e6  test    rax, rax
0x18001a3e9  jz      short loc_18001A462
0x18001a3eb  mov     [rsp+3F0h+ReturnLength], rbx; ReturnLength
0x18001a3f0  mov     r9d, 110h; ProcessInformationLength
0x18001a3f6  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18001a3fd  mov     edx, 1Bh; ProcessInformationClass
0x18001a402  mov     rcx, rax; ProcessHandle
0x18001a405  call    cs:__imp_NtQueryInformationProcess
0x18001a40c  nop     dword ptr [rax+rax+00h]
0x18001a411  mov     edi, eax
0x18001a413  or      edi, 10000000h
0x18001a419  jl      short loc_18001A453
  ... truncated ...
```
