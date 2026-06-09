# RpcWaitAsyncNotificationEx

- ea: `0x180019430`
- end: `0x180019df8`
- name: `RpcWaitAsyncNotificationEx`
- size: `2504`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180019430`
- `0x180019e00`
- `0x18001a510`
- `0x18001a6f8`
- `0x18001a900`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019c4a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019d11`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019c4a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019d11`
- `ntdll!RtlCaptureStackBackTrace` at `0x180019d7f`
- `ntdll!RtlCaptureStackBackTrace` at `0x180019d7f`
- `ntdll!NtQueryInformationProcess` at `0x180019c28`
- `ntdll!NtQueryInformationProcess` at `0x180019cef`
- `ntdll!NtQueryInformationProcess` at `0x180019c28`
- `ntdll!NtQueryInformationProcess` at `0x180019cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001980d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001980d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800197f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019833`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019da5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019dd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800197f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019833`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019da5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019dd2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001955a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019645`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001955a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d43`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800194a5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800194a5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195ae`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019533`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019622`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019533`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180019622`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019bf6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019cbd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019bf6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019cbd`

## string_xrefs

- `0x180019915`: `%s with Trace ID 0x%x Completed`
- `0x180019946`: `%s with Trace ID 0x%x Completed`
- `0x180019a8e`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180019b55`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001998b`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`
- `0x1800199c5`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x180019430  push    rbp
0x180019432  push    rbx
0x180019433  push    rsi
0x180019434  push    rdi
0x180019435  push    r12
0x180019437  push    r13
0x180019439  push    r14
0x18001943b  push    r15
0x18001943d  lea     rbp, [rsp-508h]
0x180019445  sub     rsp, 608h
0x18001944c  mov     rax, cs:__security_cookie
0x180019453  xor     rax, rsp
0x180019456  mov     [rbp+540h+var_50], rax
0x18001945d  mov     r13, r9
0x180019460  mov     r15, r8
0x180019463  mov     r14, rdx
0x180019466  mov     r12, rcx
0x180019469  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180019470  mov     [rbp+540h+var_3B0], rax
0x180019477  mov     ebx, 1
0x18001947c  mov     [rbp+540h+var_394], ebx
0x180019482  xor     esi, esi
0x180019484  mov     [rbp+540h+var_390], rsi
0x18001948b  lea     rdi, aRpcwaitasyncno; "RpcWaitAsyncNotificationEx"
0x180019492  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x180019498  jnz     loc_180019A41
0x18001949e  lea     rcx, [rbp+540h+pguid]; pguid
0x1800194a5  call    cs:__imp_CoCreateGuid
0x1800194ac  nop     dword ptr [rax+rax+00h]
0x1800194b1  mov     eax, ebx
0x1800194b3  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x1800194bb  add     eax, ebx
0x1800194bd  mov     [rbp+540h+var_398], eax
0x1800194c3  mov     [rbp+540h+var_388], esi
0x1800194c9  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800194d0  mov     [rbp+540h+var_3B0], rax
0x1800194d7  mov     [rbp+540h+var_380], rdi
0x1800194de  or      eax, 0FFFFFFFFh
0x1800194e1  mov     [rbp+540h+pSessionId], eax
0x1800194e7  mov     [rbp+540h+Pid], eax
0x1800194ed  mov     [rbp+540h+var_370], esi
0x1800194f3  xor     edx, edx; Val
0x1800194f5  mov     r8d, 208h; Size
0x1800194fb  lea     rcx, [rbp+540h+var_36C]; void *
0x180019502  call    memset_0
0x180019507  cmp     [rbp+540h+var_370], esi
0x18001950d  jnz     loc_1800198A1
0x180019513  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180019519  and     edi, ebx
0x18001951b  or      eax, 0FFFFFFFFh
0x18001951e  mov     [rbp+540h+pSessionId], eax
0x180019524  mov     [rbp+540h+Pid], eax
0x18001952a  lea     rdx, [rbp+540h+Pid]; Pid
0x180019531  xor     ecx, ecx; Binding
0x180019533  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001953a  nop     dword ptr [rax+rax+00h]
0x18001953f  mov     ebx, eax
0x180019541  test    eax, eax
0x180019543  jg      loc_18001987C
0x180019549  test    ebx, ebx
0x18001954b  js      short loc_18001956E
0x18001954d  lea     rdx, [rbp+540h+pSessionId]; pSessionId
0x180019554  mov     ecx, [rbp+540h+Pid]; dwProcessId
0x18001955a  call    cs:__imp_ProcessIdToSessionId
0x180019561  nop     dword ptr [rax+rax+00h]
0x180019566  test    edi, edi
0x180019568  jnz     loc_180019BE8
0x18001956e  cmp     [rbp+540h+var_370], esi
0x180019574  jnz     loc_18001995C
0x18001957a  mov     rbx, rsi
0x18001957d  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180019584  mov     [rsp+640h+var_600], rax
0x180019589  mov     [rsp+640h+var_5E4], 1
0x180019591  mov     [rsp+640h+var_5E0], rsi
0x180019596  lea     rdi, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x18001959d  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x1800195a3  jnz     loc_180019B03
0x1800195a9  lea     rcx, [rsp+640h+var_5F8]; pguid
0x1800195ae  call    cs:__imp_CoCreateGuid
0x1800195b5  nop     dword ptr [rax+rax+00h]
0x1800195ba  mov     eax, 1
0x1800195bf  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x1800195c7  inc     eax
0x1800195c9  mov     [rsp+640h+var_5E8], eax
0x1800195cd  mov     [rsp+640h+var_5D8], esi
0x1800195d1  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800195d8  mov     [rsp+640h+var_600], rax
0x1800195dd  mov     [rsp+640h+var_5D0], rdi
0x1800195e2  or      edi, 0FFFFFFFFh
0x1800195e5  mov     [rsp+640h+var_5C8], edi
0x1800195e9  mov     [rsp+640h+dwProcessId], edi
0x1800195ed  mov     [rbp+540h+var_5C0], esi
0x1800195f0  xor     edx, edx; Val
0x1800195f2  mov     r8d, 208h; Size
0x1800195f8  lea     rcx, [rbp+540h+var_5BC]; void *
0x1800195fc  call    memset_0
0x180019601  cmp     [rbp+540h+var_5C0], esi
0x180019604  jnz     loc_1800198D1
0x18001960a  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180019610  and     esi, 1
0x180019613  mov     [rsp+640h+var_5C8], edi
0x180019617  mov     [rsp+640h+dwProcessId], edi
0x18001961b  lea     rdx, [rsp+640h+dwProcessId]; Pid
0x180019620  xor     ecx, ecx; Binding
0x180019622  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180019629  nop     dword ptr [rax+rax+00h]
0x18001962e  mov     edi, eax
0x180019630  test    eax, eax
0x180019632  jg      loc_18001988A
0x180019638  test    edi, edi
0x18001963a  js      short loc_180019659
0x18001963c  lea     rdx, [rsp+640h+var_5C8]; pSessionId
0x180019641  mov     ecx, [rsp+640h+dwProcessId]; dwProcessId
0x180019645  call    cs:__imp_ProcessIdToSessionId
0x18001964c  nop     dword ptr [rax+rax+00h]
0x180019651  test    esi, esi
0x180019653  jnz     loc_180019CB1
0x180019659  xor     esi, esi
0x18001965b  cmp     [rbp+540h+var_5C0], esi
0x18001965e  jnz     loc_1800199A1
0x180019664  test    r12, r12
0x180019667  jz      loc_180019858
0x18001966d  test    r14, r14
0x180019670  jz      loc_180019D54
0x180019676  test    r15, r15
0x180019679  jz      loc_180019898
0x18001967f  mov     rbx, [r14+638h]
0x180019686  test    rbx, rbx
0x180019689  jz      short loc_18001969A
0x18001968b  mov     rax, [rbx]
0x18001968e  mov     rcx, rbx
0x180019691  mov     rax, [rax+8]
0x180019695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001969a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800196a1  mov     ecx, 670h; unsigned __int64
0x1800196a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800196ab  mov     rdi, rax
0x1800196ae  test    rax, rax
0x1800196b1  jz      loc_18001975D
0x1800196b7  mov     rcx, rax
0x1800196ba  call    ??0?$CTSPrivateObject@VIPublicNotificationCallback@@@@QEAA@PEBD@Z; CTSPrivateObject<IPublicNotificationCallback>::CTSPrivateObject<IPublicNotificationCallback>(char const *)
0x1800196bf  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x1800196c6  mov     [rdi], rax
0x1800196c9  mov     [rdi+638h], r12
0x1800196d0  mov     [rdi+640h], r15
0x1800196d7  mov     [rdi+648h], r13
0x1800196de  mov     dword ptr [rdi+650h], 80004001h
0x1800196e8  mov     [rdi+654h], esi
0x1800196ee  mov     [rdi+658h], rsi
0x1800196f5  mov     [rdi+660h], rsi
0x1800196fc  mov     [rdi+668h], esi
0x180019702  mov     [rdi+66Ch], esi
0x180019708  cmp     dword ptr [rdi+0Ch], 1
0x18001970c  jnz     short loc_18001972B
0x18001970e  mov     eax, 1
0x180019713  lock xadd [rdi+20h], eax
0x180019718  inc     eax
0x18001971a  mov     [rsp+640h+BackTraceHash], esi
0x18001971e  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180019725  jz      loc_180019D60
0x18001972b  lock inc qword ptr [rdi+18h]
0x180019730  mov     rdx, rbx; struct IPublicNotification *
0x180019733  mov     rcx, rdi; this
0x180019736  call    ?Initialize@CAsyncNotifyParams@@QEAAJPEAVIPublicNotification@@@Z; CAsyncNotifyParams::Initialize(IPublicNotification *)
0x18001973b  mov     esi, eax
0x18001973d  test    eax, eax
0x18001973f  js      loc_1800199DB
0x180019745  mov     [rdi+650h], esi
0x18001974b  test    esi, esi
0x18001974d  js      loc_180019D90
0x180019753  mov     rcx, rdi
0x180019756  call    ?InternalRelease@?$CTSPrivateObject@VIPublicNotificationCallback@@@@AEAAKXZ; CTSPrivateObject<IPublicNotificationCallback>::InternalRelease(void)
0x18001975b  xor     esi, esi
0x18001975d  lea     rdi, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180019764  mov     [rsp+640h+var_600], rdi
0x180019769  cmp     [rbp+540h+var_5C0], esi
0x18001976c  jnz     loc_1800198FE
0x180019772  lea     r14, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180019779  mov     [rsp+640h+var_600], r14
0x18001977e  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x180019784  jnz     short loc_1800197E6
0x180019786  mov     [rsp+640h+var_5E0], rsi
0x18001978b  test    rbx, rbx
0x18001978e  jz      short loc_1800197A0
0x180019790  mov     rax, [rbx]
0x180019793  mov     rcx, rbx
0x180019796  mov     rax, [rax+10h]
0x18001979a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001979f  nop
0x1800197a0  mov     [rbp+540h+var_3B0], rdi
0x1800197a7  cmp     [rbp+540h+var_370], esi
0x1800197ad  jnz     loc_18001992B
0x1800197b3  mov     [rbp+540h+var_3B0], r14
0x1800197ba  cmp     cs:?g_bEnabled@CTraceBase@@0HA, esi; int CTraceBase::g_bEnabled
0x1800197c0  jnz     short loc_18001981E
0x1800197c2  mov     rcx, [rbp+540h+var_50]
0x1800197c9  xor     rcx, rsp; StackCookie
0x1800197cc  call    __security_check_cookie
0x1800197d1  add     rsp, 608h
0x1800197d8  pop     r15
0x1800197da  pop     r14
0x1800197dc  pop     r13
0x1800197de  pop     r12
0x1800197e0  pop     rdi
0x1800197e1  pop     rsi
0x1800197e2  pop     rbx
0x1800197e3  pop     rbp
0x1800197e4  retn
0x1800197e6  cmp     [rsp+640h+var_5D8], esi
0x1800197ea  jnz     short loc_180019786
0x1800197ec  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x1800197f2  cmp     ecx, 0FFFFFFFFh
0x1800197f5  jz      short loc_180019786
0x1800197f7  xor     edx, edx; lpTlsValue
0x1800197f9  call    cs:__imp_TlsSetValue
0x180019800  nop     dword ptr [rax+rax+00h]
0x180019805  test    eax, eax
0x180019807  jnz     loc_180019D9D
0x18001980d  call    cs:__imp_GetLastError
0x180019814  nop     dword ptr [rax+rax+00h]
0x180019819  jmp     loc_180019DB9
0x18001981e  cmp     [rbp+540h+var_388], esi
0x180019824  jnz     short loc_1800197C2
0x180019826  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001982c  cmp     ecx, 0FFFFFFFFh
0x18001982f  jz      short loc_1800197C2
0x180019831  xor     edx, edx; lpTlsValue
0x180019833  call    cs:__imp_TlsSetValue
0x18001983a  nop     dword ptr [rax+rax+00h]
0x18001983f  test    eax, eax
0x180019841  jnz     loc_180019DCA
0x180019847  call    cs:__imp_GetLastError
0x18001984e  nop     dword ptr [rax+rax+00h]
0x180019853  jmp     loc_180019DE6
0x180019858  lea     r8, aPasyncstate; "pAsyncState"
0x18001985f  lea     r9, aRpcwaitasyncno_0; "RpcWaitAsyncNotification"
0x180019866  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001986d  mov     ecx, 8; int
0x180019872  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019877  jmp     loc_18001975D
0x18001987c  movzx   ebx, ax
0x18001987f  or      ebx, 80070000h
0x180019885  jmp     loc_180019549
0x18001988a  movzx   edi, ax
0x18001988d  or      edi, 80070000h
0x180019893  jmp     loc_180019638
0x180019898  lea     r8, aPpsessionchang; "ppSessionChange"
0x18001989f  jmp     short loc_18001985F
0x1800198a1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x1800198a7  jz      loc_180019513
0x1800198ad  mov     r9d, [rbp+540h+var_398]
0x1800198b4  mov     r8, [rbp+540h+var_380]
0x1800198bb  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800198c2  mov     ecx, 2; int
0x1800198c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800198cc  jmp     loc_180019513
0x1800198d1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800198d8  jz      loc_18001960A
0x1800198de  mov     r9d, [rsp+640h+var_5E8]
0x1800198e3  mov     r8, [rsp+640h+var_5D0]
0x1800198e8  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800198ef  mov     ecx, 2; int
0x1800198f4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800198f9  jmp     loc_18001960A
0x1800198fe  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180019905  jz      loc_180019772
0x18001990b  mov     r9d, [rsp+640h+var_5E8]
0x180019910  mov     r8, [rsp+640h+var_5D0]
0x180019915  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18001991c  mov     ecx, 2; int
0x180019921  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019926  jmp     loc_180019772
0x18001992b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180019932  jz      loc_1800197B3
0x180019938  mov     r9d, [rbp+540h+var_398]
0x18001993f  mov     r8, [rbp+540h+var_380]
0x180019946  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18001994d  mov     ecx, 2; int
0x180019952  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019957  jmp     loc_1800197B3
0x18001995c  test    ebx, ebx
0x18001995e  js      loc_1800199FB
0x180019964  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001996b  jz      loc_18001957A
0x180019971  lea     rax, [rbp+540h+var_36C]
0x180019978  mov     [rsp+640h+ReturnLength], rax
0x18001997d  mov     r9d, [rbp+540h+pSessionId]
0x180019984  mov     r8d, [rbp+540h+Pid]
0x18001998b  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x180019992  mov     ecx, 2; int
0x180019997  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001999c  jmp     loc_18001957A
0x1800199a1  test    edi, edi
0x1800199a3  js      short loc_180019A1E
0x1800199a5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800199ac  jz      loc_180019664
0x1800199b2  lea     rax, [rbp+540h+var_5BC]
0x1800199b6  mov     [rsp+640h+ReturnLength], rax
0x1800199bb  mov     r9d, [rsp+640h+var_5C8]
0x1800199c0  mov     r8d, [rsp+640h+dwProcessId]
  ... truncated ...
```
