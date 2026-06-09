# RpcWaitAsyncNotificationEx

- ea: `0x18000b1f0`
- end: `0x18000bb2d`
- name: `RpcWaitAsyncNotificationEx`
- size: `2365`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000b1f0`
- `0x18000bb40`
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

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b9c1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ba70`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b9c1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ba70`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000bad2`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000bad2`
- `ntdll!NtQueryInformationProcess` at `0x18000b9a5`
- `ntdll!NtQueryInformationProcess` at `0x18000ba54`
- `ntdll!NtQueryInformationProcess` at `0x18000b9a5`
- `ntdll!NtQueryInformationProcess` at `0x18000ba54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb21`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b594`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b5c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000baf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000bb13`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b594`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b5c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000baf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000bb13`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b30e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b3e7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b30e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b3e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba9c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b265`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b35c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b265`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b35c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b2ed`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b3ca`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b2ed`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b3ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b979`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ba28`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b979`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ba28`

## string_xrefs

- `0x18000b698`: `%s with Trace ID 0x%x Completed`
- `0x18000b6c9`: `%s with Trace ID 0x%x Completed`
- `0x18000b811`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000b8d8`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000b70e`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`
- `0x18000b748`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RpcWaitAsyncNotificationEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // edi
  RPC_STATUS v9; // eax
  int v10; // ebx
  struct IPublicNotification *v11; // rbx
  unsigned int v12; // esi
  RPC_STATUS v13; // eax
  int v14; // edi
  void *v15; // rax
  void *v16; // rdi
  char v17; // al
  int v18; // eax
  int v19; // esi
  const char *v20; // r8
  HANDLE v21; // rax
  void *v22; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v24; // rax
  wchar_t *v25; // rax
  HANDLE v26; // rax
  void *v27; // rsi
  NTSTATUS v28; // eax
  wchar_t *v29; // rax
  wchar_t *v30; // rax
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v32; // [rsp+40h] [rbp-C0h] BYREF
  GUID v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  const char *v37; // [rsp+70h] [rbp-90h]
  DWORD v38; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwProcessId; // [rsp+7Ch] [rbp-84h] BYREF
  int v40; // [rsp+80h] [rbp-80h]
  unsigned __int16 v41[262]; // [rsp+84h] [rbp-7Ch] BYREF
  void **v42; // [rsp+290h] [rbp+190h] BYREF
  GUID pguid; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v44[2]; // [rsp+2A8h] [rbp+1A8h] BYREF
  struct CTraceBase *v45; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v46; // [rsp+2B8h] [rbp+1B8h]
  const char *v47; // [rsp+2C0h] [rbp+1C0h]
  DWORD pSessionId; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned int Pid; // [rsp+2CCh] [rbp+1CCh] BYREF
  int v50; // [rsp+2D0h] [rbp+1D0h]
  unsigned __int16 v51[262]; // [rsp+2D4h] [rbp+1D4h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+4E0h] [rbp+3E0h] BYREF
  wchar_t *Str; // [rsp+4E8h] [rbp+3E8h]

  v42 = &CTraceBase::`vftable';
  v44[1] = 1;
  v45 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v42, 1, "RpcWaitAsyncNotificationEx");
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
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v45) >= 0 && v45 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v45 + 32LL))(v45, &pguid);
      v44[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v45 + 24LL))(v45);
      v46 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v42, "RpcWaitAsyncNotificationEx");
    CTraceBase::GenerateTraceID(&pguid, v44);
  }
  else
  {
    CoCreateGuid(&pguid);
    v44[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v46 = 0;
LABEL_4:
  v42 = &CRpcCallTrace::`vftable';
  v47 = "RpcWaitAsyncNotificationEx";
  pSessionId = -1;
  Pid = -1;
  v50 = 0;
  memset_0(v51, 0, 0x208u);
  if ( v50 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v47, v44[0]);
  v8 = g_DebugTraceComponent & 1;
  pSessionId = -1;
  Pid = -1;
  v9 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    ProcessIdToSessionId(Pid, &pSessionId);
    if ( v8 )
    {
      v21 = OpenProcess(0x400u, 0, Pid);
      v22 = v21;
      if ( v21 )
      {
        InformationProcess = NtQueryInformationProcess(v21, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v10 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v24 = wcsrchr(Str, 0x5Cu);
          if ( v24 )
            v25 = v24 + 1;
          else
            v25 = Str;
          StringCchCopyW(v51, 0x104u, v25);
        }
        CloseHandle(v22);
      }
    }
  }
  if ( v50 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid, pSessionId, v51);
    }
  }
  v11 = 0;
  v32 = &CTraceBase::`vftable';
  v34[1] = 1;
  v35 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v32, 1, "RpcWaitAsyncNotification");
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
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v35) >= 0 && v35 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v35 + 32LL))(v35, &v33);
      v34[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v35 + 24LL))(v35);
      v36 = 1;
      goto LABEL_13;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v32, "RpcWaitAsyncNotification");
    CTraceBase::GenerateTraceID(&v33, v34);
  }
  else
  {
    CoCreateGuid(&v33);
    v34[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v36 = 0;
LABEL_13:
  v32 = &CRpcCallTrace::`vftable';
  v37 = "RpcWaitAsyncNotification";
  v38 = -1;
  dwProcessId = -1;
  v40 = 0;
  memset_0(v41, 0, 0x208u);
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v37, v34[0]);
  v12 = g_DebugTraceComponent & 1;
  v38 = -1;
  dwProcessId = -1;
  v13 = I_RpcBindingInqLocalClientPID(0, &dwProcessId);
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( v14 >= 0 )
  {
    ProcessIdToSessionId(dwProcessId, &v38);
    if ( v12 )
    {
      v26 = OpenProcess(0x400u, 0, dwProcessId);
      v27 = v26;
      if ( v26 )
      {
        v28 = NtQueryInformationProcess(v26, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v14 = v28 | 0x10000000;
        if ( v28 >= 0 )
        {
          v29 = wcsrchr(Str, 0x5Cu);
          if ( v29 )
            v30 = v29 + 1;
          else
            v30 = Str;
          StringCchCopyW(v41, 0x104u, v30);
        }
        CloseHandle(v27);
      }
    }
  }
  if ( v40 )
  {
    if ( v14 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", dwProcessId, v38, v41);
    }
  }
  if ( !a1 )
  {
    v20 = "pAsyncState";
LABEL_49:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v20, "RpcWaitAsyncNotification");
    goto LABEL_33;
  }
  if ( !a2 )
  {
    v20 = "hNotify";
    goto LABEL_49;
  }
  if ( !a3 )
  {
    v20 = "ppSessionChange";
    goto LABEL_49;
  }
  v11 = *(struct IPublicNotification **)(a2 + 1592);
  if ( v11 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*(_QWORD *)(a2 + 1592));
  v15 = operator new(0x670u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( v15 )
  {
    CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(v15);
    *(_QWORD *)v16 = &CAsyncNotifyParams::`vftable';
    *((_QWORD *)v16 + 199) = a1;
    *((_QWORD *)v16 + 200) = a3;
    *((_QWORD *)v16 + 201) = a4;
    *((_DWORD *)v16 + 404) = -2147467263;
    *((_DWORD *)v16 + 405) = 0;
    *((_QWORD *)v16 + 203) = 0;
    *((_QWORD *)v16 + 204) = 0;
    *((_DWORD *)v16 + 410) = 0;
    *((_DWORD *)v16 + 411) = 0;
    if ( *((_DWORD *)v16 + 3) == 1 )
    {
      v17 = _InterlockedIncrement((volatile signed __int32 *)v16 + 8);
      BackTraceHash[0] = 0;
      if ( g_bCaptureObjectStackTrace == 1 )
        RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v16 + 6 * (v17 & 0x1F) + 5, BackTraceHash);
    }
    _InterlockedIncrement64((volatile signed __int64 *)v16 + 3);
    v18 = CAsyncNotifyParams::Initialize((CAsyncNotifyParams *)v16, v11);
    v19 = v18;
    if ( v18 < 0 )
      _DbgPrintMessage(8, "AsyncParams->Initialize failed: 0x%x in %s", v18, "RpcWaitAsyncNotification");
    *((_DWORD *)v16 + 404) = v19;
    if ( v19 < 0 )
      CAsyncNotifyParams::UnsubscribeFromNotifications((CAsyncNotifyParams *)v16);
    CTSPrivateObject<IPublicNotificationCallback>::InternalRelease(v16);
  }
LABEL_33:
  v32 = &CRpcCallTrace::`vftable';
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v37, v34[0]);
  v32 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v36 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_35;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_35:
  v35 = 0;
  if ( v11 )
    (*(void (__fastcall **)(struct IPublicNotification *))(*(_QWORD *)v11 + 16LL))(v11);
  v42 = &CRpcCallTrace::`vftable';
  if ( v50 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v47, v44[0]);
  v42 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v46 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( !TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      GetLastError();
LABEL_107:
      GetLastError();
      return;
    }
    if ( !TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
      goto LABEL_107;
  }
}

```

## disassembly

```asm
0x18000b1f0  push    rbp
0x18000b1f2  push    rbx
0x18000b1f3  push    rsi
0x18000b1f4  push    rdi
0x18000b1f5  push    r12
0x18000b1f7  push    r13
0x18000b1f9  push    r14
0x18000b1fb  push    r15
0x18000b1fd  lea     rbp, [rsp-508h]
0x18000b205  sub     rsp, 608h
0x18000b20c  mov     rax, cs:__security_cookie
0x18000b213  xor     rax, rsp
0x18000b216  mov     [rbp+540h+var_50], rax
0x18000b21d  mov     r13, r9
0x18000b220  mov     r15, r8
0x18000b223  mov     r14, rdx
0x18000b226  mov     r12, rcx
0x18000b229  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000b230  mov     [rbp+540h+var_3B0], rax
0x18000b237  mov     ebx, 1
0x18000b23c  mov     [rbp+540h+var_394], ebx
0x18000b242  xor     esi, esi
0x18000b244  mov     [rbp+540h+var_390], rsi
0x18000b24b  lea     rdi, aRpcwaitasyncno; "RpcWaitAsyncNotificationEx"
0x18000b252  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x18000b258  jnz     loc_18000B7C4
0x18000b25e  lea     rcx, [rbp+540h+pguid]; pguid
0x18000b265  call    cs:__imp_CoCreateGuid
0x18000b26b  mov     eax, ebx
0x18000b26d  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000b275  add     eax, ebx
0x18000b277  mov     [rbp+540h+var_398], eax
0x18000b27d  mov     [rbp+540h+var_388], esi
0x18000b283  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000b28a  mov     [rbp+540h+var_3B0], rax
0x18000b291  mov     [rbp+540h+var_380], rdi
0x18000b298  or      eax, 0FFFFFFFFh
0x18000b29b  mov     [rbp+540h+pSessionId], eax
0x18000b2a1  mov     [rbp+540h+Pid], eax
0x18000b2a7  mov     [rbp+540h+var_370], esi
0x18000b2ad  xor     edx, edx; Val
0x18000b2af  mov     r8d, 208h; Size
0x18000b2b5  lea     rcx, [rbp+540h+var_36C]; void *
0x18000b2bc  call    memset_0
0x18000b2c1  cmp     [rbp+540h+var_370], esi
0x18000b2c7  jnz     loc_18000B624
0x18000b2cd  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000b2d3  and     edi, ebx
0x18000b2d5  or      eax, 0FFFFFFFFh
0x18000b2d8  mov     [rbp+540h+pSessionId], eax
0x18000b2de  mov     [rbp+540h+Pid], eax
0x18000b2e4  lea     rdx, [rbp+540h+Pid]; Pid
0x18000b2eb  xor     ecx, ecx; Binding
0x18000b2ed  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000b2f3  mov     ebx, eax
0x18000b2f5  test    eax, eax
0x18000b2f7  jg      loc_18000B5FF
0x18000b2fd  test    ebx, ebx
0x18000b2ff  js      short loc_18000B31C
0x18000b301  lea     rdx, [rbp+540h+pSessionId]; pSessionId
0x18000b308  mov     ecx, [rbp+540h+Pid]; dwProcessId
0x18000b30e  call    cs:__imp_ProcessIdToSessionId
0x18000b314  test    edi, edi
0x18000b316  jnz     loc_18000B96B
0x18000b31c  cmp     [rbp+540h+var_370], esi
0x18000b322  jnz     loc_18000B6DF
0x18000b328  mov     rbx, rsi
0x18000b32b  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000b332  mov     [rsp+640h+var_600], rax
0x18000b337  mov     [rsp+640h+var_5E4], 1
0x18000b33f  mov     [rsp+640h+var_5E0], rsi
0x18000b344  lea     rdi, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000b34b  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x18000b351  jnz     loc_18000B886
0x18000b357  lea     rcx, [rsp+640h+var_5F8]; pguid
0x18000b35c  call    cs:__imp_CoCreateGuid
0x18000b362  mov     eax, 1
0x18000b367  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000b36f  inc     eax
0x18000b371  mov     [rsp+640h+var_5E8], eax
0x18000b375  mov     [rsp+640h+var_5D8], esi
0x18000b379  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000b380  mov     [rsp+640h+var_600], rax
0x18000b385  mov     [rsp+640h+var_5D0], rdi
0x18000b38a  or      edi, 0FFFFFFFFh
0x18000b38d  mov     [rsp+640h+var_5C8], edi
0x18000b391  mov     [rsp+640h+dwProcessId], edi
0x18000b395  mov     [rbp+540h+var_5C0], esi
0x18000b398  xor     edx, edx; Val
0x18000b39a  mov     r8d, 208h; Size
0x18000b3a0  lea     rcx, [rbp+540h+var_5BC]; void *
0x18000b3a4  call    memset_0
0x18000b3a9  cmp     [rbp+540h+var_5C0], esi
0x18000b3ac  jnz     loc_18000B654
0x18000b3b2  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000b3b8  and     esi, 1
0x18000b3bb  mov     [rsp+640h+var_5C8], edi
0x18000b3bf  mov     [rsp+640h+dwProcessId], edi
0x18000b3c3  lea     rdx, [rsp+640h+dwProcessId]; Pid
0x18000b3c8  xor     ecx, ecx; Binding
0x18000b3ca  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000b3d0  mov     edi, eax
0x18000b3d2  test    eax, eax
0x18000b3d4  jg      loc_18000B60D
0x18000b3da  test    edi, edi
0x18000b3dc  js      short loc_18000B3F5
0x18000b3de  lea     rdx, [rsp+640h+var_5C8]; pSessionId
0x18000b3e3  mov     ecx, [rsp+640h+dwProcessId]; dwProcessId
0x18000b3e7  call    cs:__imp_ProcessIdToSessionId
0x18000b3ed  test    esi, esi
0x18000b3ef  jnz     loc_18000BA1C
0x18000b3f5  xor     esi, esi
0x18000b3f7  cmp     [rbp+540h+var_5C0], esi
0x18000b3fa  jnz     loc_18000B724
0x18000b400  test    r12, r12
0x18000b403  jz      loc_18000B5DB
0x18000b409  test    r14, r14
0x18000b40c  jz      loc_18000BAA7
0x18000b412  test    r15, r15
0x18000b415  jz      loc_18000B61B
0x18000b41b  mov     rbx, [r14+638h]
0x18000b422  test    rbx, rbx
0x18000b425  jz      short loc_18000B436
0x18000b427  mov     rax, [rbx]
0x18000b42a  mov     rcx, rbx
0x18000b42d  mov     rax, [rax+8]
0x18000b431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b436  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b43d  mov     ecx, 670h; unsigned __int64
0x18000b442  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b447  mov     rdi, rax
0x18000b44a  test    rax, rax
0x18000b44d  jz      loc_18000B4F9
0x18000b453  mov     rcx, rax
0x18000b456  call    ??0?$CTSPrivateObject@VIPublicNotificationCallback@@@@QEAA@PEBD@Z; CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(char const *)
0x18000b45b  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x18000b462  mov     [rdi], rax
0x18000b465  mov     [rdi+638h], r12
0x18000b46c  mov     [rdi+640h], r15
0x18000b473  mov     [rdi+648h], r13
0x18000b47a  mov     dword ptr [rdi+650h], 80004001h
0x18000b484  mov     [rdi+654h], esi
0x18000b48a  mov     [rdi+658h], rsi
0x18000b491  mov     [rdi+660h], rsi
0x18000b498  mov     [rdi+668h], esi
0x18000b49e  mov     [rdi+66Ch], esi
0x18000b4a4  cmp     dword ptr [rdi+0Ch], 1
0x18000b4a8  jnz     short loc_18000B4C7
0x18000b4aa  mov     eax, 1
0x18000b4af  lock xadd [rdi+20h], eax
0x18000b4b4  inc     eax
0x18000b4b6  mov     [rsp+640h+BackTraceHash], esi
0x18000b4ba  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000b4c1  jz      loc_18000BAB3
0x18000b4c7  lock inc qword ptr [rdi+18h]
0x18000b4cc  mov     rdx, rbx; struct IPublicNotification *
0x18000b4cf  mov     rcx, rdi; this
0x18000b4d2  call    ?Initialize@CAsyncNotifyParams@@QEAAJPEAVIPublicNotification@@@Z; CAsyncNotifyParams::Initialize(IPublicNotification *)
0x18000b4d7  mov     esi, eax
0x18000b4d9  test    eax, eax
0x18000b4db  js      loc_18000B75E
0x18000b4e1  mov     [rdi+650h], esi
0x18000b4e7  test    esi, esi
0x18000b4e9  js      loc_18000BADD
0x18000b4ef  mov     rcx, rdi
0x18000b4f2  call    ?InternalRelease@?$CTSPrivateObject@VIPublicNotificationCallback@@@@AEAAKXZ; CTSPrivateObject<IPublicNotificationCallback>::InternalRelease(void)
0x18000b4f7  xor     esi, esi
0x18000b4f9  lea     rdi, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000b500  mov     [rsp+640h+var_600], rdi
0x18000b505  cmp     [rbp+540h+var_5C0], esi
0x18000b508  jnz     loc_18000B681
0x18000b50e  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000b515  mov     [rsp+640h+var_600], r14
0x18000b51a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x18000b520  jnz     short loc_18000B581
0x18000b522  mov     [rsp+640h+var_5E0], rsi
0x18000b527  test    rbx, rbx
0x18000b52a  jz      short loc_18000B53C
0x18000b52c  mov     rax, [rbx]
0x18000b52f  mov     rcx, rbx
0x18000b532  mov     rax, [rax+10h]
0x18000b536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53b  nop
0x18000b53c  mov     [rbp+540h+var_3B0], rdi
0x18000b543  cmp     [rbp+540h+var_370], esi
0x18000b549  jnz     loc_18000B6AE
0x18000b54f  mov     [rbp+540h+var_3B0], r14
0x18000b556  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x18000b55c  jnz     short loc_18000B5AD
0x18000b55e  mov     rcx, [rbp+540h+var_50]
0x18000b565  xor     rcx, rsp; StackCookie
0x18000b568  call    __security_check_cookie
0x18000b56d  add     rsp, 608h
0x18000b574  pop     r15
0x18000b576  pop     r14
0x18000b578  pop     r13
0x18000b57a  pop     r12
0x18000b57c  pop     rdi
0x18000b57d  pop     rsi
0x18000b57e  pop     rbx
0x18000b57f  pop     rbp
0x18000b580  retn
0x18000b581  cmp     [rsp+640h+var_5D8], esi
0x18000b585  jnz     short loc_18000B522
0x18000b587  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000b58d  cmp     ecx, 0FFFFFFFFh
0x18000b590  jz      short loc_18000B522
0x18000b592  xor     edx, edx; lpTlsValue
0x18000b594  call    cs:__imp_TlsSetValue
0x18000b59a  test    eax, eax
0x18000b59c  jnz     loc_18000BAEA
0x18000b5a2  call    cs:__imp_GetLastError
0x18000b5a8  jmp     loc_18000BB00
0x18000b5ad  cmp     [rbp+540h+var_388], esi
0x18000b5b3  jnz     short loc_18000B55E
0x18000b5b5  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000b5bb  cmp     ecx, 0FFFFFFFFh
0x18000b5be  jz      short loc_18000B55E
0x18000b5c0  xor     edx, edx; lpTlsValue
0x18000b5c2  call    cs:__imp_TlsSetValue
0x18000b5c8  test    eax, eax
0x18000b5ca  jnz     loc_18000BB0B
0x18000b5d0  call    cs:__imp_GetLastError
0x18000b5d6  jmp     loc_18000BB21
0x18000b5db  lea     r8, aPasyncstate; "pAsyncState"
0x18000b5e2  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000b5e9  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000b5f0  mov     ecx, 8; int
0x18000b5f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5fa  jmp     loc_18000B4F9
0x18000b5ff  movzx   ebx, ax
0x18000b602  or      ebx, 80070000h
0x18000b608  jmp     loc_18000B2FD
0x18000b60d  movzx   edi, ax
0x18000b610  or      edi, 80070000h
0x18000b616  jmp     loc_18000B3DA
0x18000b61b  lea     r8, aPpsessionchang; "ppSessionChange"
0x18000b622  jmp     short loc_18000B5E2
0x18000b624  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000b62a  jz      loc_18000B2CD
0x18000b630  mov     r9d, [rbp+540h+var_398]
0x18000b637  mov     r8, [rbp+540h+var_380]
0x18000b63e  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000b645  mov     ecx, 2; int
0x18000b64a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b64f  jmp     loc_18000B2CD
0x18000b654  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b65b  jz      loc_18000B3B2
0x18000b661  mov     r9d, [rsp+640h+var_5E8]
0x18000b666  mov     r8, [rsp+640h+var_5D0]
0x18000b66b  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000b672  mov     ecx, 2; int
0x18000b677  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b67c  jmp     loc_18000B3B2
0x18000b681  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b688  jz      loc_18000B50E
0x18000b68e  mov     r9d, [rsp+640h+var_5E8]
0x18000b693  mov     r8, [rsp+640h+var_5D0]
0x18000b698  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000b69f  mov     ecx, 2; int
0x18000b6a4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b6a9  jmp     loc_18000B50E
0x18000b6ae  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b6b5  jz      loc_18000B54F
0x18000b6bb  mov     r9d, [rbp+540h+var_398]
0x18000b6c2  mov     r8, [rbp+540h+var_380]
0x18000b6c9  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000b6d0  mov     ecx, 2; int
0x18000b6d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b6da  jmp     loc_18000B54F
0x18000b6df  test    ebx, ebx
0x18000b6e1  js      loc_18000B77E
0x18000b6e7  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b6ee  jz      loc_18000B328
0x18000b6f4  lea     rax, [rbp+540h+var_36C]
0x18000b6fb  mov     [rsp+640h+ReturnLength], rax
0x18000b700  mov     r9d, [rbp+540h+pSessionId]
0x18000b707  mov     r8d, [rbp+540h+Pid]
0x18000b70e  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000b715  mov     ecx, 2; int
0x18000b71a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b71f  jmp     loc_18000B328
0x18000b724  test    edi, edi
0x18000b726  js      short loc_18000B7A1
0x18000b728  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b72f  jz      loc_18000B400
0x18000b735  lea     rax, [rbp+540h+var_5BC]
0x18000b739  mov     [rsp+640h+ReturnLength], rax
0x18000b73e  mov     r9d, [rsp+640h+var_5C8]
0x18000b743  mov     r8d, [rsp+640h+dwProcessId]
0x18000b748  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000b74f  mov     ecx, 2; int
0x18000b754  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b759  jmp     loc_18000B400
0x18000b75e  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18000b765  mov     r8d, esi
0x18000b768  lea     rdx, aAsyncparamsIni; "AsyncParams->Initialize failed: 0x%x in"...
0x18000b76f  mov     ecx, 8; int
0x18000b774  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b779  jmp     loc_18000B4E1
  ... truncated ...
```
