# RpcGetCurrentSessionCapabilities

- ea: `0x18000c7a0`
- end: `0x18000d08e`
- name: `RpcGetCurrentSessionCapabilities`
- size: `2286`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18000c7a0`
- `0x18000d0a0`
- `0x18000d6c4`
- `0x18000d728`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x18005fcc4`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000cf74`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000cf74`
- `ntdll!NtQueryInformationProcess` at `0x18000cf58`
- `ntdll!NtQueryInformationProcess` at `0x18000cf58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d082`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cc02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d074`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cc02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d074`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c92a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cbcf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c92a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cbcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cbb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cbb6`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000c8a8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000c8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf9e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c81c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c81c`
- `RPCRT4!RpcImpersonateClient` at `0x18000c8f9`
- `RPCRT4!RpcImpersonateClient` at `0x18000c8f9`
- `RPCRT4!RpcRevertToSelf` at `0x18000c93b`
- `RPCRT4!RpcRevertToSelf` at `0x18000c93b`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000c8da`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000c8da`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c88d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000caca`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c88d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000caca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cf30`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cf30`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000c9cd`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000c9cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9a2`

## string_xrefs

- `0x18000cad3`: `Session %d is glass/temp glass/worker`
- `0x18000cfd6`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000cd9e`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000cfca`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000cc77`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000cc7e`: `CRpcUtils::GetClientToken`
- `0x18000cd21`: `%s with Trace ID 0x%x Completed`
- `0x18000cee3`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000ce35`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000cd6a`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
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
                  qword_1800A3150,
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
0x18000c7a0  push    rbp
0x18000c7a2  push    rbx
0x18000c7a3  push    rsi
0x18000c7a4  push    rdi
0x18000c7a5  push    r12
0x18000c7a7  push    r13
0x18000c7a9  push    r14
0x18000c7ab  push    r15
0x18000c7ad  lea     rbp, [rsp-2D8h]
0x18000c7b5  sub     rsp, 3D8h
0x18000c7bc  mov     rax, cs:__security_cookie
0x18000c7c3  xor     rax, rsp
0x18000c7c6  mov     [rbp+310h+var_50], rax
0x18000c7cd  mov     r13, r8
0x18000c7d0  mov     r15d, edx
0x18000c7d3  xor     r12d, r12d
0x18000c7d6  mov     ebx, r12d
0x18000c7d9  mov     edi, r12d
0x18000c7dc  mov     [rsp+410h+var_3B8], r12
0x18000c7e1  mov     [rsp+410h+var_3C0], r12
0x18000c7e6  mov     [rsp+410h+var_3D0], r12
0x18000c7eb  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000c7f2  mov     [rsp+410h+var_3B0], rax
0x18000c7f7  mov     [rsp+410h+var_394], 1
0x18000c7ff  mov     [rbp+310h+var_390], r12
0x18000c803  lea     rsi, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18000c80a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000c811  jnz     loc_18000CDE2
0x18000c817  lea     rcx, [rsp+410h+pguid]; pguid
0x18000c81c  call    cs:__imp_CoCreateGuid
0x18000c822  mov     eax, 1
0x18000c827  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000c82f  inc     eax
0x18000c831  mov     [rsp+410h+var_398], eax
0x18000c835  mov     [rbp+310h+var_388], r12d
0x18000c839  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000c840  mov     [rsp+410h+var_3B0], rax
0x18000c845  mov     [rbp+310h+var_380], rsi
0x18000c849  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000c851  mov     [rbp+310h+var_370], r12d
0x18000c855  xor     edx, edx; Val
0x18000c857  mov     r8d, 208h; Size
0x18000c85d  lea     rcx, [rbp+310h+var_36C]; void *
0x18000c861  call    memset_0
0x18000c866  cmp     [rbp+310h+var_370], ebx
0x18000c869  jnz     loc_18000CCDF
0x18000c86f  mov     r14d, r12d
0x18000c872  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000c879  jnz     loc_18000CF1A
0x18000c87f  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000c887  lea     rdx, [rbp+310h+Pid+4]; Pid
0x18000c88b  xor     ecx, ecx; Binding
0x18000c88d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000c893  mov     esi, eax
0x18000c895  test    eax, eax
0x18000c897  jg      loc_18000CC1B
0x18000c89d  test    esi, esi
0x18000c89f  js      short loc_18000C8B7
0x18000c8a1  lea     rdx, [rbp+310h+Pid]; pSessionId
0x18000c8a5  mov     ecx, [rbp+310h+Pid+4]; dwProcessId
0x18000c8a8  call    cs:__imp_ProcessIdToSessionId
0x18000c8ae  test    r14d, r14d
0x18000c8b1  jnz     loc_18000CF25
0x18000c8b7  cmp     [rbp+310h+var_370], ebx
0x18000c8ba  jnz     loc_18000CD48
0x18000c8c0  mov     [r13+0], r12d
0x18000c8c4  cmp     r15d, 1
0x18000c8c8  jnz     loc_18000CC29
0x18000c8ce  mov     [rsp+410h+ClientLocalFlag], r12d
0x18000c8d3  lea     rdx, [rsp+410h+ClientLocalFlag]; ClientLocalFlag
0x18000c8d8  xor     ecx, ecx; BindingHandle
0x18000c8da  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000c8e0  test    eax, eax
0x18000c8e2  jnz     loc_18000CD37
0x18000c8e8  cmp     [rsp+410h+ClientLocalFlag], ebx
0x18000c8ec  jz      loc_18000CD37
0x18000c8f2  mov     [rsp+410h+TokenHandle], r12
0x18000c8f7  xor     ecx, ecx; BindingHandle
0x18000c8f9  call    cs:__imp_RpcImpersonateClient
0x18000c8ff  mov     esi, eax
0x18000c901  test    eax, eax
0x18000c903  jg      loc_18000CC5D
0x18000c909  test    esi, esi
0x18000c90b  js      loc_18000CC77
0x18000c911  call    cs:__imp_GetCurrentThread
0x18000c917  mov     rcx, rax; ThreadHandle
0x18000c91a  lea     r9, [rsp+410h+TokenHandle]; TokenHandle
0x18000c91f  mov     edx, 0Eh; DesiredAccess
0x18000c924  mov     r8d, 1; OpenAsSelf
0x18000c92a  call    cs:__imp_OpenThreadToken
0x18000c930  test    eax, eax
0x18000c932  jz      loc_18000CE9E
0x18000c938  mov     esi, r12d
0x18000c93b  call    cs:__imp_RpcRevertToSelf
0x18000c941  test    eax, eax
0x18000c943  jg      loc_18000CC4E
0x18000c949  js      loc_18000CFAC
0x18000c94f  test    esi, esi
0x18000c951  js      loc_18000CFCA
0x18000c957  mov     rax, [rsp+410h+TokenHandle]
0x18000c95c  mov     rbx, rax
0x18000c95f  test    esi, esi
0x18000c961  js      loc_18000CFD6
0x18000c967  mov     r14d, r12d
0x18000c96a  mov     [rsp+410h+hObject], r12
0x18000c96f  mov     [rsp+410h+ClientLocalFlag], r12d
0x18000c974  mov     [rsp+410h+var_3DC], r12d
0x18000c979  mov     esi, r12d
0x18000c97c  test    rbx, rbx
0x18000c97f  jz      loc_18000CBB6
0x18000c985  mov     rcx, rbx; TokenHandle
0x18000c988  lea     rax, [rsp+410h+var_3DC]
0x18000c98d  mov     [rsp+410h+ReturnLength], rax; ReturnLength
0x18000c992  mov     r9d, 4; TokenInformationLength
0x18000c998  lea     r8, [rsp+410h+ClientLocalFlag]; TokenInformation
0x18000c99d  mov     edx, 0Ch; TokenInformationClass
0x18000c9a2  call    cs:__imp_GetTokenInformation
0x18000c9a8  test    eax, eax
0x18000c9aa  jz      loc_18000CEBC
0x18000c9b0  mov     r14d, [rsp+410h+ClientLocalFlag]
0x18000c9b5  mov     rcx, [rsp+410h+hObject]; hObject
0x18000c9ba  test    rcx, rcx
0x18000c9bd  jz      short loc_18000C9C5
0x18000c9bf  call    cs:__imp_CloseHandle
0x18000c9c5  test    esi, esi
0x18000c9c7  js      loc_18000CFE2
0x18000c9cd  call    cs:__imp_WTSGetServiceSessionId
0x18000c9d3  cmp     r14d, eax
0x18000c9d6  jz      loc_18000CAF6
0x18000c9dc  mov     [rsp+410h+ClientLocalFlag], 80004001h
0x18000c9e4  mov     rdi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18000c9eb  test    rdi, rdi
0x18000c9ee  jz      loc_18000CFEE
0x18000c9f4  mov     [rsp+410h+ClientLocalFlag], r12d
0x18000c9f9  mov     rax, [rdi]
0x18000c9fc  mov     rcx, rdi
0x18000c9ff  mov     rax, [rax+8]
0x18000ca03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca08  mov     rax, [rdi]
0x18000ca0b  lea     rdx, [rsp+410h+var_3B8]
0x18000ca10  mov     rcx, rdi
0x18000ca13  mov     rax, [rax+18h]
0x18000ca17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca1c  mov     esi, eax
0x18000ca1e  test    eax, eax
0x18000ca20  js      loc_18000CC6B
0x18000ca26  mov     rcx, [rsp+410h+var_3B8]
0x18000ca2b  mov     rax, [rcx]
0x18000ca2e  lea     r8, [rsp+410h+var_3C0]
0x18000ca33  mov     edx, r14d
0x18000ca36  mov     rax, [rax+18h]
0x18000ca3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca3f  mov     esi, eax
0x18000ca41  test    eax, eax
0x18000ca43  js      loc_18000D04E
0x18000ca49  mov     rcx, [rsp+410h+var_3C0]
0x18000ca4e  mov     rax, [rcx]
0x18000ca51  lea     rdx, [rsp+410h+var_3D0]
0x18000ca56  mov     rax, [rax+68h]
0x18000ca5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca5f  mov     esi, eax
0x18000ca61  test    eax, eax
0x18000ca63  js      loc_18000D05D
0x18000ca69  mov     r9, [rsp+410h+var_3D0]
0x18000ca6e  mov     r15d, 80004002h
0x18000ca74  mov     rcx, r12
0x18000ca77  mov     [rsp+410h+hObject], rcx
0x18000ca7c  test    r9, r9
0x18000ca7f  jz      short loc_18000CAA3
0x18000ca81  mov     rax, [r9]
0x18000ca84  lea     r8, [rsp+410h+hObject]
0x18000ca89  lea     rdx, qword_1800A3150
0x18000ca90  mov     rcx, r9
0x18000ca93  mov     rax, [rax]
0x18000ca96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9b  mov     r15d, eax
0x18000ca9e  mov     rcx, [rsp+410h+hObject]
0x18000caa3  test    rcx, rcx
0x18000caa6  jz      short loc_18000CAB5
0x18000caa8  mov     rdx, [rcx]
0x18000caab  mov     rax, [rdx+10h]
0x18000caaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab4  nop
0x18000cab5  test    r15d, r15d
0x18000cab8  js      loc_18000CCAE
0x18000cabe  mov     [rsp+410h+var_3DC], r12d
0x18000cac3  lea     rdx, [rsp+410h+var_3DC]; Pid
0x18000cac8  xor     ecx, ecx; Binding
0x18000caca  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000cad0  mov     r8d, r14d
0x18000cad3  lea     rdx, aSessionDIsGlas; "Session %d is glass/temp glass/worker"
0x18000cada  mov     ecx, 1; int
0x18000cadf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cae4  lea     rdx, [rsp+410h+var_3DC]; volatile unsigned int *
0x18000cae9  lea     rcx, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18000caf0  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x18000caf5  nop
0x18000caf6  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000cafd  mov     [rsp+410h+var_3B0], rax
0x18000cb02  cmp     [rbp+310h+var_370], 0
0x18000cb06  jnz     loc_18000CD0B
0x18000cb0c  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000cb13  mov     [rsp+410h+var_3B0], rax
0x18000cb18  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000cb1f  jnz     loc_18000CBE7
0x18000cb25  mov     [rbp+310h+var_390], r12
0x18000cb29  mov     rcx, [rsp+410h+var_3D0]
0x18000cb2e  test    rcx, rcx
0x18000cb31  jz      short loc_18000CB40
0x18000cb33  mov     rax, [rcx]
0x18000cb36  mov     rax, [rax+10h]
0x18000cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb3f  nop
0x18000cb40  mov     rcx, [rsp+410h+var_3C0]
0x18000cb45  test    rcx, rcx
0x18000cb48  jz      short loc_18000CB57
0x18000cb4a  mov     rax, [rcx]
0x18000cb4d  mov     rax, [rax+10h]
0x18000cb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb56  nop
0x18000cb57  mov     rcx, [rsp+410h+var_3B8]
0x18000cb5c  test    rcx, rcx
0x18000cb5f  jz      short loc_18000CB6E
0x18000cb61  mov     rax, [rcx]
0x18000cb64  mov     rax, [rax+10h]
0x18000cb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb6d  nop
0x18000cb6e  test    rdi, rdi
0x18000cb71  jz      short loc_18000CB83
0x18000cb73  mov     rax, [rdi]
0x18000cb76  mov     rcx, rdi
0x18000cb79  mov     rax, [rax+10h]
0x18000cb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb82  nop
0x18000cb83  test    rbx, rbx
0x18000cb86  jz      short loc_18000CB91
0x18000cb88  mov     rcx, rbx; hObject
0x18000cb8b  call    cs:__imp_CloseHandle
0x18000cb91  mov     eax, esi
0x18000cb93  mov     rcx, [rbp+310h+var_50]
0x18000cb9a  xor     rcx, rsp; StackCookie
0x18000cb9d  call    __security_check_cookie
0x18000cba2  add     rsp, 3D8h
0x18000cba9  pop     r15
0x18000cbab  pop     r14
0x18000cbad  pop     r13
0x18000cbaf  pop     r12
0x18000cbb1  pop     rdi
0x18000cbb2  pop     rsi
0x18000cbb3  pop     rbx
0x18000cbb4  pop     rbp
0x18000cbb5  retn
0x18000cbb6  call    cs:__imp_GetCurrentThread
0x18000cbbc  lea     r9, [rsp+410h+hObject]; TokenHandle
0x18000cbc1  mov     edx, 8; DesiredAccess
0x18000cbc6  mov     r8d, 1; OpenAsSelf
0x18000cbcc  mov     rcx, rax; ThreadHandle
0x18000cbcf  call    cs:__imp_OpenThreadToken
0x18000cbd5  test    eax, eax
0x18000cbd7  jz      loc_18000CD80
0x18000cbdd  mov     rcx, [rsp+410h+hObject]
0x18000cbe2  jmp     loc_18000C988
0x18000cbe7  cmp     [rbp+310h+var_388], 0
0x18000cbeb  jnz     loc_18000CB25
0x18000cbf1  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000cbf7  cmp     ecx, 0FFFFFFFFh
0x18000cbfa  jz      loc_18000CB25
0x18000cc00  xor     edx, edx; lpTlsValue
0x18000cc02  call    cs:__imp_TlsSetValue
0x18000cc08  test    eax, eax
0x18000cc0a  jnz     loc_18000D06C
0x18000cc10  call    cs:__imp_GetLastError
0x18000cc16  jmp     loc_18000D082
0x18000cc1b  movzx   esi, ax
0x18000cc1e  or      esi, 80070000h
0x18000cc24  jmp     loc_18000C89D
0x18000cc29  mov     esi, 80070057h
0x18000cc2e  lea     rdx, aInvalidCapabil; "Invalid capabilities type failed: 0x%x "...
0x18000cc35  mov     r8d, esi
0x18000cc38  lea     r9, aRpcgetcurrents_1; "RpcGetCurrentSessionCapabilities"
0x18000cc3f  mov     ecx, 8; int
0x18000cc44  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cc49  jmp     loc_18000CAF6
0x18000cc4e  movzx   eax, ax
0x18000cc51  or      eax, 80070000h
0x18000cc56  test    eax, eax
0x18000cc58  jmp     loc_18000C949
0x18000cc5d  movzx   esi, ax
0x18000cc60  or      esi, 80070000h
0x18000cc66  jmp     loc_18000C909
0x18000cc6b  mov     r8d, eax
0x18000cc6e  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18000cc75  jmp     short loc_18000CC38
0x18000cc77  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000cc7e  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000cc85  mov     r8d, esi
0x18000cc88  mov     ecx, 8; int
0x18000cc8d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cc92  mov     rax, [rsp+410h+TokenHandle]
0x18000cc97  test    rax, rax
  ... truncated ...
```
