# RpcGetCurrentSessionCapabilities

- ea: `0x18001d1c0`
- end: `0x18001db51`
- name: `RpcGetCurrentSessionCapabilities`
- size: `2449`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x18001d1c0`
- `0x18001db60`
- `0x18001e1bc`
- `0x18001e220`
- `0x180029158`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x1800637cc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001da1f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001da1f`
- `ntdll!NtQueryInformationProcess` at `0x18001d9fd`
- `ntdll!NtQueryInformationProcess` at `0x18001d9fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db3f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001d67d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001db2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001d67d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001db2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d36e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d644`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d36e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d644`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d34f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d34f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d625`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001d2d4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001d2d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d72a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d72a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da4f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001d23c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001d23c`
- `RPCRT4!RpcImpersonateClient` at `0x18001d331`
- `RPCRT4!RpcImpersonateClient` at `0x18001d331`
- `RPCRT4!RpcRevertToSelf` at `0x18001d385`
- `RPCRT4!RpcRevertToSelf` at `0x18001d385`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001d30c`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001d30c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d2b3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d52c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d2b3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d52c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d9cf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d9cf`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001d429`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001d429`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d3f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d3f2`

## string_xrefs

- `0x18001da8d`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18001d831`: `OpenThreadToken failed: 0x%x in %s`
- `0x18001da81`: `OpenThreadToken failed: 0x%x in %s`
- `0x18001d53b`: `Session %d is glass/temp glass/worker`
- `0x18001d6fe`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18001d705`: `CRpcUtils::GetClientToken`
- `0x18001d7ae`: `%s with Trace ID 0x%x Completed`
- `0x18001d982`: `GetTokenInformation failed: 0x%x in %s`
- `0x18001d8c8`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001d7f7`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetCurrentSessionCapabilities(__int64 a1, int a2, _DWORD *a3)
{
  void *v5; // rbx
  struct ISessionManagerInternal *v6; // rdi
  unsigned int v7; // r14d
  RPC_STATUS v8; // eax
  int v9; // esi
  RPC_STATUS v10; // eax
  signed int v11; // esi
  HANDLE CurrentThread; // rax
  int v13; // eax
  bool v14; // sf
  void *v15; // rax
  unsigned int v16; // r14d
  HANDLE v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // r15d
  HANDLE v22; // rcx
  const struct _EVENT_DESCRIPTOR *v23; // r8
  HANDLE v25; // rax
  const char *v26; // rdx
  signed int v27; // eax
  signed int LastError; // eax
  signed int v29; // eax
  HANDLE v30; // rax
  void *v31; // r12
  NTSTATUS InformationProcess; // eax
  wchar_t *v33; // rax
  wchar_t *v34; // rax
  CSessionManager *v35; // rax
  struct ISessionManagerInternal *v36; // rax
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  struct ITerminal *v40; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  void **v44; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v46[2]; // [rsp+78h] [rbp-88h] BYREF
  struct CTraceBase *v47; // [rsp+80h] [rbp-80h] BYREF
  int v48; // [rsp+88h] [rbp-78h]
  const char *v49; // [rsp+90h] [rbp-70h]
  unsigned int Pid[2]; // [rsp+98h] [rbp-68h] BYREF
  int v51; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v52[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t *Str; // [rsp+2B8h] [rbp+1B8h]

  v5 = 0;
  v6 = 0;
  v43 = 0;
  v42 = 0;
  v40 = 0;
  v44 = &CTraceBase::`vftable';
  v46[1] = 1;
  v47 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v44, 1, "RpcGetCurrentSessionCapabilities");
    hObject = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)&hObject) >= 0
      && hObject
      && (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    }
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v47) >= 0 && v47 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v47 + 32LL))(v47, &pguid);
      v46[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v47 + 24LL))(v47);
      v48 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v44, "RpcGetCurrentSessionCapabilities");
    CTraceBase::GenerateTraceID(&pguid, v46);
  }
  else
  {
    CoCreateGuid(&pguid);
    v46[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v48 = 0;
LABEL_4:
  v44 = &CRpcCallTrace::`vftable';
  v49 = "RpcGetCurrentSessionCapabilities";
  *(_QWORD *)Pid = -1;
  v51 = 0;
  memset_0(v52, 0, 0x208u);
  if ( v51 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v49, v46[0]);
  v7 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v7 = 260;
  *(_QWORD *)Pid = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v7 )
    {
      v30 = OpenProcess(0x400u, 0, Pid[1]);
      v31 = v30;
      if ( v30 )
      {
        InformationProcess = NtQueryInformationProcess(v30, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v9 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v33 = wcsrchr(Str, 0x5Cu);
          if ( v33 )
            v34 = v33 + 1;
          else
            v34 = Str;
          StringCchCopyW(v52, v7, v34);
        }
        CloseHandle(v31);
      }
    }
  }
  if ( v51 )
  {
    if ( v9 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v52);
    }
  }
  *a3 = 0;
  if ( a2 != 1 )
  {
    v11 = -2147024809;
    v26 = "Invalid capabilities type failed: 0x%x in %s";
LABEL_66:
    _DbgPrintMessage(8, v26, (unsigned int)v11, "RpcGetCurrentSessionCapabilities");
    goto LABEL_46;
  }
  ClientLocalFlag = 0;
  if ( I_RpcBindingIsClientLocal(0, &ClientLocalFlag) || !ClientLocalFlag )
  {
    v11 = -2147024846;
    v26 = "CRpcUtils::IsLocalCall failed: 0x%x in %s";
    goto LABEL_66;
  }
  TokenHandle = 0;
  v10 = RpcImpersonateClient(0);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v11, "CRpcUtils::GetClientToken");
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    v13 = RpcRevertToSelf();
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( v14 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v13);
      v11 = -2147024891;
    }
    else
    {
      if ( v11 >= 0 )
      {
        v15 = TokenHandle;
LABEL_25:
        v5 = v15;
        goto LABEL_26;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v11, "CRpcUtils::GetClientToken");
    }
  }
  v15 = TokenHandle;
  if ( !TokenHandle )
    goto LABEL_25;
  CloseHandle(TokenHandle);
LABEL_26:
  if ( v11 < 0 )
  {
    v26 = "CRpcUtils::GetClientToken failed: 0x%x in %s";
    goto LABEL_66;
  }
  v16 = 0;
  hObject = 0;
  ClientLocalFlag = 0;
  ReturnLength = 0;
  v11 = 0;
  if ( v5 )
  {
    v17 = v5;
  }
  else
  {
    v25 = GetCurrentThread();
    if ( !OpenThreadToken(v25, 8u, 1, &hObject) )
    {
      v27 = GetLastError();
      v11 = v27;
      if ( v27 > 0 )
        v11 = (unsigned __int16)v27 | 0x80070000;
      if ( v11 < 0 )
      {
        _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v11, "CUtils::GetUserSessionId");
        goto LABEL_31;
      }
    }
    v17 = hObject;
  }
  if ( GetTokenInformation(v17, TokenSessionId, &ClientLocalFlag, 4u, &ReturnLength) )
    goto LABEL_30;
  v29 = GetLastError();
  v11 = v29;
  if ( v29 > 0 )
    v11 = (unsigned __int16)v29 | 0x80070000;
  if ( v11 >= 0 )
LABEL_30:
    v16 = ClientLocalFlag;
  else
    _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v11, "CUtils::GetUserSessionId");
LABEL_31:
  if ( hObject )
    CloseHandle(hObject);
  if ( v11 < 0 )
  {
    v26 = "CUtils::GetUserSessionId() failed: 0x%x in %s";
    goto LABEL_66;
  }
  if ( v16 == (unsigned int)WTSGetServiceSessionId() )
    goto LABEL_46;
  ClientLocalFlag = -2147467263;
  v6 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
    goto LABEL_36;
  v6 = 0;
  v35 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v35 )
  {
    v36 = CSessionManager::CSessionManager(v35, (int *)&ClientLocalFlag);
    ISessionManagerInternal::pSMGlobalInstance = v36;
    if ( v36 )
    {
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v36 + 8LL))(v36);
      v6 = ISessionManagerInternal::pSMGlobalInstance;
LABEL_36:
      ClientLocalFlag = 0;
      (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  else
  {
    ISessionManagerInternal::pSMGlobalInstance = 0;
  }
  v18 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, &v43);
  v11 = v18;
  if ( v18 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", (unsigned int)v18, "RpcGetCurrentSessionCapabilities");
  }
  else
  {
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 24LL))(v43, v16, &v42);
    v11 = v19;
    if ( v19 < 0 )
    {
      _DbgPrintMessage(8, "FindSessionById failed: 0x%x in %s", (unsigned int)v19, "RpcGetCurrentSessionCapabilities");
    }
    else
    {
      v20 = (*(__int64 (__fastcall **)(__int64, struct ITerminal **))(*(_QWORD *)v42 + 104LL))(v42, &v40);
      v11 = v20;
      if ( v20 < 0 )
      {
        _DbgPrintMessage(
          8,
          "ptrSession->getTerminal failed: 0x%x in %s",
          (unsigned int)v20,
          "RpcGetCurrentSessionCapabilities");
      }
      else
      {
        v21 = -2147467262;
        v22 = 0;
        hObject = 0;
        if ( v40 )
        {
          v21 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, HANDLE *))v40)(
                  v40,
                  qword_1800A75B0,
                  &hObject);
          v22 = hObject;
        }
        if ( v22 )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v21 >= 0
          || (unsigned int)CTempGlassTerminal::IsTempGlassTerminal(v40)
          || (unsigned int)CWorkerTerminal::IsWorkerTerminal(v40) )
        {
          ReturnLength = 0;
          I_RpcBindingInqLocalClientPID(0, &ReturnLength);
          _DbgPrintMessage(1, "Session %d is glass/temp glass/worker", v16);
          CRpcUtils::DumpRpcCaller("RpcGetCurrentSessionCapabilities", &ReturnLength, v23);
        }
        else
        {
          *a3 = 1;
        }
      }
    }
  }
LABEL_46:
  v44 = &CRpcCallTrace::`vftable';
  if ( v51 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v49, v46[0]);
  v44 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v48 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_48;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_48:
  v47 = 0;
  if ( v40 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v6 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v5 )
    CloseHandle(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001d1c0  push    rbp
0x18001d1c2  push    rbx
0x18001d1c3  push    rsi
0x18001d1c4  push    rdi
0x18001d1c5  push    r12
0x18001d1c7  push    r13
0x18001d1c9  push    r14
0x18001d1cb  push    r15
0x18001d1cd  lea     rbp, [rsp-2D8h]
0x18001d1d5  sub     rsp, 3D8h
0x18001d1dc  mov     rax, cs:__security_cookie
0x18001d1e3  xor     rax, rsp
0x18001d1e6  mov     [rbp+310h+var_50], rax
0x18001d1ed  mov     r13, r8
0x18001d1f0  mov     r15d, edx
0x18001d1f3  xor     r12d, r12d
0x18001d1f6  mov     ebx, r12d
0x18001d1f9  mov     edi, r12d
0x18001d1fc  mov     [rsp+410h+var_3B8], r12
0x18001d201  mov     [rsp+410h+var_3C0], r12
0x18001d206  mov     [rsp+410h+var_3D0], r12
0x18001d20b  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001d212  mov     [rsp+410h+var_3B0], rax
0x18001d217  mov     [rsp+410h+var_394], 1
0x18001d21f  mov     [rbp+310h+var_390], r12
0x18001d223  lea     rsi, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18001d22a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18001d231  jnz     loc_18001D875
0x18001d237  lea     rcx, [rsp+410h+pguid]; pguid
0x18001d23c  call    cs:__imp_CoCreateGuid
0x18001d243  nop     dword ptr [rax+rax+00h]
0x18001d248  mov     eax, 1
0x18001d24d  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18001d255  inc     eax
0x18001d257  mov     [rsp+410h+var_398], eax
0x18001d25b  mov     [rbp+310h+var_388], r12d
0x18001d25f  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001d266  mov     [rsp+410h+var_3B0], rax
0x18001d26b  mov     [rbp+310h+var_380], rsi
0x18001d26f  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001d277  mov     [rbp+310h+var_370], r12d
0x18001d27b  xor     edx, edx; Val
0x18001d27d  mov     r8d, 208h; Size
0x18001d283  lea     rcx, [rbp+310h+var_36C]; void *
0x18001d287  call    memset_0
0x18001d28c  cmp     [rbp+310h+var_370], ebx
0x18001d28f  jnz     loc_18001D76C
0x18001d295  mov     r14d, r12d
0x18001d298  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001d29f  jnz     loc_18001D9B9
0x18001d2a5  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001d2ad  lea     rdx, [rbp+310h+Pid+4]; Pid
0x18001d2b1  xor     ecx, ecx; Binding
0x18001d2b3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001d2ba  nop     dword ptr [rax+rax+00h]
0x18001d2bf  mov     esi, eax
0x18001d2c1  test    eax, eax
0x18001d2c3  jg      loc_18001D6A2
0x18001d2c9  test    esi, esi
0x18001d2cb  js      short loc_18001D2E9
0x18001d2cd  lea     rdx, [rbp+310h+Pid]; pSessionId
0x18001d2d1  mov     ecx, [rbp+310h+Pid+4]; dwProcessId
0x18001d2d4  call    cs:__imp_ProcessIdToSessionId
0x18001d2db  nop     dword ptr [rax+rax+00h]
0x18001d2e0  test    r14d, r14d
0x18001d2e3  jnz     loc_18001D9C4
0x18001d2e9  cmp     [rbp+310h+var_370], ebx
0x18001d2ec  jnz     loc_18001D7D5
0x18001d2f2  mov     [r13+0], r12d
0x18001d2f6  cmp     r15d, 1
0x18001d2fa  jnz     loc_18001D6B0
0x18001d300  mov     [rsp+410h+ClientLocalFlag], r12d
0x18001d305  lea     rdx, [rsp+410h+ClientLocalFlag]; ClientLocalFlag
0x18001d30a  xor     ecx, ecx; BindingHandle
0x18001d30c  call    cs:__imp_I_RpcBindingIsClientLocal
0x18001d313  nop     dword ptr [rax+rax+00h]
0x18001d318  test    eax, eax
0x18001d31a  jnz     loc_18001D7C4
0x18001d320  cmp     [rsp+410h+ClientLocalFlag], ebx
0x18001d324  jz      loc_18001D7C4
0x18001d32a  mov     [rsp+410h+TokenHandle], r12
0x18001d32f  xor     ecx, ecx; BindingHandle
0x18001d331  call    cs:__imp_RpcImpersonateClient
0x18001d338  nop     dword ptr [rax+rax+00h]
0x18001d33d  mov     esi, eax
0x18001d33f  test    eax, eax
0x18001d341  jg      loc_18001D6E4
0x18001d347  test    esi, esi
0x18001d349  js      loc_18001D6FE
0x18001d34f  call    cs:__imp_GetCurrentThread
0x18001d356  nop     dword ptr [rax+rax+00h]
0x18001d35b  mov     rcx, rax; ThreadHandle
0x18001d35e  lea     r9, [rsp+410h+TokenHandle]; TokenHandle
0x18001d363  mov     edx, 0Eh; DesiredAccess
0x18001d368  mov     r8d, 1; OpenAsSelf
0x18001d36e  call    cs:__imp_OpenThreadToken
0x18001d375  nop     dword ptr [rax+rax+00h]
0x18001d37a  test    eax, eax
0x18001d37c  jz      loc_18001D931
0x18001d382  mov     esi, r12d
0x18001d385  call    cs:__imp_RpcRevertToSelf
0x18001d38c  nop     dword ptr [rax+rax+00h]
0x18001d391  test    eax, eax
0x18001d393  jg      loc_18001D6D5
0x18001d399  js      loc_18001DA63
0x18001d39f  test    esi, esi
0x18001d3a1  js      loc_18001DA81
0x18001d3a7  mov     rax, [rsp+410h+TokenHandle]
0x18001d3ac  mov     rbx, rax
0x18001d3af  test    esi, esi
0x18001d3b1  js      loc_18001DA8D
0x18001d3b7  mov     r14d, r12d
0x18001d3ba  mov     [rsp+410h+hObject], r12
0x18001d3bf  mov     [rsp+410h+ClientLocalFlag], r12d
0x18001d3c4  mov     [rsp+410h+var_3DC], r12d
0x18001d3c9  mov     esi, r12d
0x18001d3cc  test    rbx, rbx
0x18001d3cf  jz      loc_18001D625
0x18001d3d5  mov     rcx, rbx; TokenHandle
0x18001d3d8  lea     rax, [rsp+410h+var_3DC]
0x18001d3dd  mov     [rsp+410h+ReturnLength], rax; ReturnLength
0x18001d3e2  mov     r9d, 4; TokenInformationLength
0x18001d3e8  lea     r8, [rsp+410h+ClientLocalFlag]; TokenInformation
0x18001d3ed  mov     edx, 0Ch; TokenInformationClass
0x18001d3f2  call    cs:__imp_GetTokenInformation
0x18001d3f9  nop     dword ptr [rax+rax+00h]
0x18001d3fe  test    eax, eax
0x18001d400  jz      loc_18001D955
0x18001d406  mov     r14d, [rsp+410h+ClientLocalFlag]
0x18001d40b  mov     rcx, [rsp+410h+hObject]; hObject
0x18001d410  test    rcx, rcx
0x18001d413  jz      short loc_18001D421
0x18001d415  call    cs:__imp_CloseHandle
0x18001d41c  nop     dword ptr [rax+rax+00h]
0x18001d421  test    esi, esi
0x18001d423  js      loc_18001DA99
0x18001d429  call    cs:__imp_WTSGetServiceSessionId
0x18001d430  nop     dword ptr [rax+rax+00h]
0x18001d435  cmp     r14d, eax
0x18001d438  jz      loc_18001D55E
0x18001d43e  mov     [rsp+410h+ClientLocalFlag], 80004001h
0x18001d446  mov     rdi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001d44d  test    rdi, rdi
0x18001d450  jz      loc_18001DAA5
0x18001d456  mov     [rsp+410h+ClientLocalFlag], r12d
0x18001d45b  mov     rax, [rdi]
0x18001d45e  mov     rcx, rdi
0x18001d461  mov     rax, [rax+8]
0x18001d465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46a  mov     rax, [rdi]
0x18001d46d  lea     rdx, [rsp+410h+var_3B8]
0x18001d472  mov     rcx, rdi
0x18001d475  mov     rax, [rax+18h]
0x18001d479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d47e  mov     esi, eax
0x18001d480  test    eax, eax
0x18001d482  js      loc_18001D6F2
0x18001d488  mov     rcx, [rsp+410h+var_3B8]
0x18001d48d  mov     rax, [rcx]
0x18001d490  lea     r8, [rsp+410h+var_3C0]
0x18001d495  mov     edx, r14d
0x18001d498  mov     rax, [rax+18h]
0x18001d49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a1  mov     esi, eax
0x18001d4a3  test    eax, eax
0x18001d4a5  js      loc_18001DB05
0x18001d4ab  mov     rcx, [rsp+410h+var_3C0]
0x18001d4b0  mov     rax, [rcx]
0x18001d4b3  lea     rdx, [rsp+410h+var_3D0]
0x18001d4b8  mov     rax, [rax+68h]
0x18001d4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c1  mov     esi, eax
0x18001d4c3  test    eax, eax
0x18001d4c5  js      loc_18001DB14
0x18001d4cb  mov     r9, [rsp+410h+var_3D0]
0x18001d4d0  mov     r15d, 80004002h
0x18001d4d6  mov     rcx, r12
0x18001d4d9  mov     [rsp+410h+hObject], rcx
0x18001d4de  test    r9, r9
0x18001d4e1  jz      short loc_18001D505
0x18001d4e3  mov     rax, [r9]
0x18001d4e6  lea     r8, [rsp+410h+hObject]
0x18001d4eb  lea     rdx, qword_1800A75B0
0x18001d4f2  mov     rcx, r9
0x18001d4f5  mov     rax, [rax]
0x18001d4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4fd  mov     r15d, eax
0x18001d500  mov     rcx, [rsp+410h+hObject]
0x18001d505  test    rcx, rcx
0x18001d508  jz      short loc_18001D517
0x18001d50a  mov     rdx, [rcx]
0x18001d50d  mov     rax, [rdx+10h]
0x18001d511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d516  nop
0x18001d517  test    r15d, r15d
0x18001d51a  js      loc_18001D73B
0x18001d520  mov     [rsp+410h+var_3DC], r12d
0x18001d525  lea     rdx, [rsp+410h+var_3DC]; Pid
0x18001d52a  xor     ecx, ecx; Binding
0x18001d52c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001d533  nop     dword ptr [rax+rax+00h]
0x18001d538  mov     r8d, r14d
0x18001d53b  lea     rdx, aSessionDIsGlas; "Session %d is glass/temp glass/worker"
0x18001d542  mov     ecx, 1; int
0x18001d547  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d54c  lea     rdx, [rsp+410h+var_3DC]; volatile unsigned int *
0x18001d551  lea     rcx, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18001d558  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x18001d55d  nop
0x18001d55e  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001d565  mov     [rsp+410h+var_3B0], rax
0x18001d56a  cmp     [rbp+310h+var_370], 0
0x18001d56e  jnz     loc_18001D798
0x18001d574  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001d57b  mov     [rsp+410h+var_3B0], rax
0x18001d580  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001d587  jnz     loc_18001D662
0x18001d58d  mov     [rbp+310h+var_390], r12
0x18001d591  mov     rcx, [rsp+410h+var_3D0]
0x18001d596  test    rcx, rcx
0x18001d599  jz      short loc_18001D5A8
0x18001d59b  mov     rax, [rcx]
0x18001d59e  mov     rax, [rax+10h]
0x18001d5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a7  nop
0x18001d5a8  mov     rcx, [rsp+410h+var_3C0]
0x18001d5ad  test    rcx, rcx
0x18001d5b0  jz      short loc_18001D5BF
0x18001d5b2  mov     rax, [rcx]
0x18001d5b5  mov     rax, [rax+10h]
0x18001d5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5be  nop
0x18001d5bf  mov     rcx, [rsp+410h+var_3B8]
0x18001d5c4  test    rcx, rcx
0x18001d5c7  jz      short loc_18001D5D6
0x18001d5c9  mov     rax, [rcx]
0x18001d5cc  mov     rax, [rax+10h]
0x18001d5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d5  nop
0x18001d5d6  test    rdi, rdi
0x18001d5d9  jz      short loc_18001D5EB
0x18001d5db  mov     rax, [rdi]
0x18001d5de  mov     rcx, rdi
0x18001d5e1  mov     rax, [rax+10h]
0x18001d5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ea  nop
0x18001d5eb  test    rbx, rbx
0x18001d5ee  jz      short loc_18001D5FF
0x18001d5f0  mov     rcx, rbx; hObject
0x18001d5f3  call    cs:__imp_CloseHandle
0x18001d5fa  nop     dword ptr [rax+rax+00h]
0x18001d5ff  mov     eax, esi
0x18001d601  mov     rcx, [rbp+310h+var_50]
0x18001d608  xor     rcx, rsp; StackCookie
0x18001d60b  call    __security_check_cookie
0x18001d610  add     rsp, 3D8h
0x18001d617  pop     r15
0x18001d619  pop     r14
0x18001d61b  pop     r13
0x18001d61d  pop     r12
0x18001d61f  pop     rdi
0x18001d620  pop     rsi
0x18001d621  pop     rbx
0x18001d622  pop     rbp
0x18001d623  retn
0x18001d625  call    cs:__imp_GetCurrentThread
0x18001d62c  nop     dword ptr [rax+rax+00h]
0x18001d631  lea     r9, [rsp+410h+hObject]; TokenHandle
0x18001d636  mov     edx, 8; DesiredAccess
0x18001d63b  mov     r8d, 1; OpenAsSelf
0x18001d641  mov     rcx, rax; ThreadHandle
0x18001d644  call    cs:__imp_OpenThreadToken
0x18001d64b  nop     dword ptr [rax+rax+00h]
0x18001d650  test    eax, eax
0x18001d652  jz      loc_18001D80D
0x18001d658  mov     rcx, [rsp+410h+hObject]
0x18001d65d  jmp     loc_18001D3D8
0x18001d662  cmp     [rbp+310h+var_388], 0
0x18001d666  jnz     loc_18001D58D
0x18001d66c  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001d672  cmp     ecx, 0FFFFFFFFh
0x18001d675  jz      loc_18001D58D
0x18001d67b  xor     edx, edx; lpTlsValue
0x18001d67d  call    cs:__imp_TlsSetValue
0x18001d684  nop     dword ptr [rax+rax+00h]
0x18001d689  test    eax, eax
0x18001d68b  jnz     loc_18001DB23
0x18001d691  call    cs:__imp_GetLastError
0x18001d698  nop     dword ptr [rax+rax+00h]
0x18001d69d  jmp     loc_18001DB3F
0x18001d6a2  movzx   esi, ax
0x18001d6a5  or      esi, 80070000h
0x18001d6ab  jmp     loc_18001D2C9
0x18001d6b0  mov     esi, 80070057h
0x18001d6b5  lea     rdx, aInvalidCapabil; "Invalid capabilities type failed: 0x%x "...
0x18001d6bc  mov     r8d, esi
0x18001d6bf  lea     r9, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18001d6c6  mov     ecx, 8; int
0x18001d6cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d6d0  jmp     loc_18001D55E
  ... truncated ...
```
