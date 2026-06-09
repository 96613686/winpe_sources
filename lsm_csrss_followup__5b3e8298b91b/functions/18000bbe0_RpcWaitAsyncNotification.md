# RpcWaitAsyncNotification

- ea: `0x18000bbe0`
- end: `0x18000c1e8`
- name: `RpcWaitAsyncNotification`
- size: `1544`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000bbe0`
- `0x18000c1f0`
- `0x18000c3c4`
- `0x18000c5b0`
- `0x18000c700`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000c129`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000c129`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c18f`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c1bb`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c18f`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c1bb`
- `ntdll!NtQueryInformationProcess` at `0x18000c10d`
- `ntdll!NtQueryInformationProcess` at `0x18000c10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000bec7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000c1ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000bec7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000c1ce`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bce3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c152`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c152`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bc53`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bc53`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bcc6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bcc6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c0e5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c0e5`

## string_xrefs

- `0x18000bf54`: `%s with Trace ID 0x%x Completed`
- `0x18000c049`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000bf8e`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x18000bbe0  push    rbp
0x18000bbe2  push    rbx
0x18000bbe3  push    rsi
0x18000bbe4  push    rdi
0x18000bbe5  push    r12
0x18000bbe7  push    r13
0x18000bbe9  push    r14
0x18000bbeb  push    r15
0x18000bbed  lea     rbp, [rsp-2B8h]
0x18000bbf5  sub     rsp, 3B8h
0x18000bbfc  mov     rax, cs:__security_cookie
0x18000bc03  xor     rax, rsp
0x18000bc06  mov     [rbp+2F0h+var_50], rax
0x18000bc0d  mov     r13, r9
0x18000bc10  mov     [rsp+3F0h+var_3B8], r9
0x18000bc15  mov     r12, r8
0x18000bc18  mov     r15, rdx
0x18000bc1b  mov     r14, rcx
0x18000bc1e  xor     edi, edi
0x18000bc20  mov     ebx, edi
0x18000bc22  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000bc29  mov     [rsp+3F0h+var_3B0], rax
0x18000bc2e  mov     [rsp+3F0h+var_394], 1
0x18000bc36  mov     [rsp+3F0h+var_390], rdi
0x18000bc3b  lea     rsi, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000bc42  cmp     cs:?g_bEnabled@CTraceBase@@0HA, edi; int CTraceBase::g_bEnabled
0x18000bc48  jnz     loc_18000BFF6
0x18000bc4e  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000bc53  call    cs:__imp_CoCreateGuid
0x18000bc59  mov     eax, 1
0x18000bc5e  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000bc66  inc     eax
0x18000bc68  mov     [rsp+3F0h+var_398], eax
0x18000bc6c  mov     [rsp+3F0h+var_388], edi
0x18000bc70  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000bc77  mov     [rsp+3F0h+var_3B0], rax
0x18000bc7c  mov     [rsp+3F0h+var_380], rsi
0x18000bc81  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000bc8a  mov     [rbp+2F0h+var_370], edi
0x18000bc8d  xor     edx, edx; Val
0x18000bc8f  mov     r8d, 208h; Size
0x18000bc95  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000bc99  call    memset_0
0x18000bc9e  cmp     [rbp+2F0h+var_370], ebx
0x18000bca1  jnz     loc_18000BF10
0x18000bca7  mov     esi, edi
0x18000bca9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bcb0  jnz     loc_18000C0CF
0x18000bcb6  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000bcbf  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000bcc4  xor     ecx, ecx; Binding
0x18000bcc6  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000bccc  mov     edi, eax
0x18000bcce  test    eax, eax
0x18000bcd0  jg      loc_18000BEF9
0x18000bcd6  test    edi, edi
0x18000bcd8  js      short loc_18000BCF1
0x18000bcda  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000bcdf  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000bce3  call    cs:__imp_ProcessIdToSessionId
0x18000bce9  test    esi, esi
0x18000bceb  jnz     loc_18000C0D9
0x18000bcf1  cmp     [rbp+2F0h+var_370], ebx
0x18000bcf4  jnz     loc_18000BF6A
0x18000bcfa  test    r14, r14
0x18000bcfd  jz      loc_18000BE8C
0x18000bd03  test    r15, r15
0x18000bd06  jz      loc_18000C162
0x18000bd0c  test    r12, r12
0x18000bd0f  jz      loc_18000BF07
0x18000bd15  mov     rbx, [r15+638h]
0x18000bd1c  test    rbx, rbx
0x18000bd1f  jz      short loc_18000BD30
0x18000bd21  mov     rax, [rbx]
0x18000bd24  mov     rcx, rbx
0x18000bd27  mov     rax, [rax+8]
0x18000bd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bd37  mov     ecx, 670h; unsigned __int64
0x18000bd3c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bd41  mov     rdi, rax
0x18000bd44  test    rax, rax
0x18000bd47  jz      loc_18000BEAB
0x18000bd4d  mov     rcx, rax
0x18000bd50  call    ??0?$CTSPrivateObject@VIPublicNotificationCallback@@@@QEAA@PEBD@Z; CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(char const *)
0x18000bd55  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x18000bd5c  mov     [rdi], rax
0x18000bd5f  mov     [rdi+638h], r14
0x18000bd66  mov     [rdi+640h], r12
0x18000bd6d  mov     [rdi+648h], r13
0x18000bd74  mov     dword ptr [rdi+650h], 80004001h
0x18000bd7e  xor     r12d, r12d
0x18000bd81  mov     [rdi+654h], r12d
0x18000bd88  mov     [rdi+658h], r12
0x18000bd8f  mov     [rdi+660h], r12
0x18000bd96  mov     [rdi+668h], r12d
0x18000bd9d  mov     [rdi+66Ch], r12d
0x18000bda4  cmp     dword ptr [rdi+0Ch], 1
0x18000bda8  jnz     short loc_18000BDC8
0x18000bdaa  mov     eax, 1
0x18000bdaf  lock xadd [rdi+20h], eax
0x18000bdb4  inc     eax
0x18000bdb6  mov     [rsp+3F0h+BackTraceHash], r12d
0x18000bdbb  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000bdc2  jz      loc_18000C16E
0x18000bdc8  lock inc qword ptr [rdi+18h]
0x18000bdcd  mov     rdx, rbx; struct IPublicNotification *
0x18000bdd0  mov     rcx, rdi; this
0x18000bdd3  call    ?Initialize@CAsyncNotifyParams@@QEAAJPEAVIPublicNotification@@@Z; CAsyncNotifyParams::Initialize(IPublicNotification *)
0x18000bdd8  mov     r15d, eax
0x18000bddb  test    eax, eax
0x18000bddd  js      loc_18000BFA4
0x18000bde3  mov     [rdi+650h], eax
0x18000bde9  cmp     dword ptr [rdi+0Ch], 1
0x18000bded  jnz     short loc_18000BE0D
0x18000bdef  mov     [rsp+3F0h+BackTraceHash], r12d
0x18000bdf4  mov     eax, 1
0x18000bdf9  lock xadd [rdi+20h], eax
0x18000bdfe  inc     eax
0x18000be00  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000be07  jz      loc_18000C19A
0x18000be0d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000be14  lock xadd [rdi+18h], rax
0x18000be1a  cmp     rax, 1
0x18000be1e  jz      loc_18000BEE0
0x18000be24  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000be2b  mov     [rsp+3F0h+var_3B0], rax
0x18000be30  cmp     [rbp+2F0h+var_370], 0
0x18000be34  jnz     loc_18000BF3D
0x18000be3a  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000be41  mov     [rsp+3F0h+var_3B0], rax
0x18000be46  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000be4d  jnz     short loc_18000BEB3
0x18000be4f  mov     [rsp+3F0h+var_390], r12
0x18000be54  test    rbx, rbx
0x18000be57  jz      short loc_18000BE69
0x18000be59  mov     rax, [rbx]
0x18000be5c  mov     rcx, rbx
0x18000be5f  mov     rax, [rax+10h]
0x18000be63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be68  nop
0x18000be69  mov     rcx, [rbp+2F0h+var_50]
0x18000be70  xor     rcx, rsp; StackCookie
0x18000be73  call    __security_check_cookie
0x18000be78  add     rsp, 3B8h
0x18000be7f  pop     r15
0x18000be81  pop     r14
0x18000be83  pop     r13
0x18000be85  pop     r12
0x18000be87  pop     rdi
0x18000be88  pop     rsi
0x18000be89  pop     rbx
0x18000be8a  pop     rbp
0x18000be8b  retn
0x18000be8c  lea     r8, aPasyncstate; "pAsyncState"
0x18000be93  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000be9a  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000bea1  mov     ecx, 8; int
0x18000bea6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000beab  xor     r12d, r12d
0x18000beae  jmp     loc_18000BE24
0x18000beb3  cmp     [rsp+3F0h+var_388], 0
0x18000beb8  jnz     short loc_18000BE4F
0x18000beba  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000bec0  cmp     ecx, 0FFFFFFFFh
0x18000bec3  jz      short loc_18000BE4F
0x18000bec5  xor     edx, edx; lpTlsValue
0x18000bec7  call    cs:__imp_TlsSetValue
0x18000becd  test    eax, eax
0x18000becf  jnz     loc_18000C1C6
0x18000bed5  call    cs:__imp_GetLastError
0x18000bedb  jmp     loc_18000C1DC
0x18000bee0  mov     rax, [rdi]
0x18000bee3  mov     edx, 1
0x18000bee8  mov     rcx, rdi
0x18000beeb  mov     rax, [rax+28h]
0x18000beef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bef4  jmp     loc_18000BE24
0x18000bef9  movzx   edi, ax
0x18000befc  or      edi, 80070000h
0x18000bf02  jmp     loc_18000BCD6
0x18000bf07  lea     r8, aPpsessionchang; "ppSessionChange"
0x18000bf0e  jmp     short loc_18000BE93
0x18000bf10  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bf17  jz      loc_18000BCA7
0x18000bf1d  mov     r9d, [rsp+3F0h+var_398]
0x18000bf22  mov     r8, [rsp+3F0h+var_380]
0x18000bf27  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000bf2e  mov     ecx, 2; int
0x18000bf33  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bf38  jmp     loc_18000BCA7
0x18000bf3d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bf44  jz      loc_18000BE3A
0x18000bf4a  mov     r9d, [rsp+3F0h+var_398]
0x18000bf4f  mov     r8, [rsp+3F0h+var_380]
0x18000bf54  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000bf5b  mov     ecx, 2; int
0x18000bf60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bf65  jmp     loc_18000BE3A
0x18000bf6a  test    edi, edi
0x18000bf6c  js      short loc_18000BFD3
0x18000bf6e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bf75  jz      loc_18000BCFA
0x18000bf7b  lea     rax, [rbp+2F0h+var_36C]
0x18000bf7f  mov     [rsp+3F0h+ReturnLength], rax
0x18000bf84  mov     r9d, [rsp+3F0h+Pid]
0x18000bf89  mov     r8d, [rsp+3F0h+Pid+4]
0x18000bf8e  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000bf95  mov     ecx, 2; int
0x18000bf9a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bf9f  jmp     loc_18000BCFA
0x18000bfa4  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000bfab  mov     r8d, r15d
0x18000bfae  lea     rdx, aAsyncparamsIni; "AsyncParams->Initialize failed: 0x%x in"...
0x18000bfb5  mov     ecx, 8; int
0x18000bfba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bfbf  mov     [rdi+650h], r15d
0x18000bfc6  mov     rcx, rdi; this
0x18000bfc9  call    ?UnsubscribeFromNotifications@CAsyncNotifyParams@@QEAAJXZ; CAsyncNotifyParams::UnsubscribeFromNotifications(void)
0x18000bfce  jmp     loc_18000BDE9
0x18000bfd3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bfda  jz      loc_18000BCFA
0x18000bfe0  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000bfe7  mov     ecx, 2; int
0x18000bfec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bff1  jmp     loc_18000BCFA
0x18000bff6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bffd  jz      short loc_18000C020
0x18000bfff  mov     [rsp+3F0h+ReturnLength], rsi
0x18000c004  mov     r9d, 1
0x18000c00a  lea     r8, [rsp+3F0h+var_3B0]
0x18000c00f  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000c016  mov     ecx, 2; int
0x18000c01b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c020  mov     qword ptr [rsp+3F0h+BackTraceHash], rdi
0x18000c025  lea     rcx, [rsp+3F0h+BackTraceHash]; struct CTraceBase **
0x18000c02a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000c02f  test    eax, eax
0x18000c031  js      short loc_18000C05A
0x18000c033  cmp     qword ptr [rsp+3F0h+BackTraceHash], rbx
0x18000c038  jz      short loc_18000C05A
0x18000c03a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000c041  jz      short loc_18000C05A
0x18000c043  mov     r8d, 1
0x18000c049  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000c050  mov     ecx, 2; int
0x18000c055  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c05a  xor     edx, edx; char *
0x18000c05c  xor     ecx, ecx; lpTlsValue
0x18000c05e  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000c063  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000c068  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000c06d  test    eax, eax
0x18000c06f  js      short loc_18000C0AE
0x18000c071  mov     rcx, [rsp+3F0h+var_390]
0x18000c076  test    rcx, rcx
0x18000c079  jz      short loc_18000C0AE
0x18000c07b  mov     rax, [rcx]
0x18000c07e  lea     rdx, [rsp+3F0h+pguid]
0x18000c083  mov     rax, [rax+20h]
0x18000c087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c08c  mov     rcx, [rsp+3F0h+var_390]
0x18000c091  mov     rax, [rcx]
0x18000c094  mov     rax, [rax+18h]
0x18000c098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09d  mov     [rsp+3F0h+var_398], eax
0x18000c0a1  mov     [rsp+3F0h+var_388], 1
0x18000c0a9  jmp     loc_18000BC70
0x18000c0ae  mov     rdx, rsi; char *
0x18000c0b1  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000c0b6  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000c0bb  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000c0c0  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000c0c5  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000c0ca  jmp     loc_18000BC6C
0x18000c0cf  mov     esi, 104h
0x18000c0d4  jmp     loc_18000BCB6
0x18000c0d9  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000c0de  xor     edx, edx; bInheritHandle
0x18000c0e0  mov     ecx, 400h; dwDesiredAccess
0x18000c0e5  call    cs:__imp_OpenProcess
0x18000c0eb  mov     r13, rax
0x18000c0ee  test    rax, rax
0x18000c0f1  jz      short loc_18000C158
0x18000c0f3  mov     [rsp+3F0h+ReturnLength], rbx; ReturnLength
0x18000c0f8  mov     r9d, 110h; ProcessInformationLength
0x18000c0fe  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000c105  mov     edx, 1Bh; ProcessInformationClass
0x18000c10a  mov     rcx, rax; ProcessHandle
0x18000c10d  call    cs:__imp_NtQueryInformationProcess
0x18000c113  mov     edi, eax
0x18000c115  or      edi, 10000000h
0x18000c11b  jl      short loc_18000C14F
0x18000c11d  mov     edx, 5Ch ; '\'; Ch
0x18000c122  mov     rcx, [rbp+2F0h+Str]; Str
0x18000c129  call    cs:__imp_wcsrchr
0x18000c12f  test    rax, rax
0x18000c132  jnz     short loc_18000C13D
0x18000c134  mov     rax, [rbp+2F0h+Str]
0x18000c13b  jmp     short loc_18000C141
  ... truncated ...
```
