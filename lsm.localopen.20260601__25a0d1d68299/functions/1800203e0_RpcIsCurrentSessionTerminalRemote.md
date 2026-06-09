# RpcIsCurrentSessionTerminalRemote

- ea: `0x1800203e0`
- end: `0x180020af5`
- name: `RpcIsCurrentSessionTerminalRemote`
- size: `1813`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x1800203e0`
- `0x180020b00`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020a15`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020a15`
- `ntdll!NtQueryInformationProcess` at `0x1800209f3`
- `ntdll!NtQueryInformationProcess` at `0x1800209f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ae3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800206ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020acf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800206ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020acf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020544`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800206b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020544`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800206b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020693`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800204e0`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800204e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002065a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002065a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a47`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002044c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002044c`
- `RPCRT4!RpcImpersonateClient` at `0x180020505`
- `RPCRT4!RpcImpersonateClient` at `0x180020505`
- `RPCRT4!RpcRevertToSelf` at `0x18002055b`
- `RPCRT4!RpcRevertToSelf` at `0x18002055b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800204b9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800204b9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800209c1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800209c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800205ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800205ca`

## string_xrefs

- `0x180020810`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18002083e`: `OpenThreadToken failed: 0x%x in %s`
- `0x180020a74`: `OpenThreadToken failed: 0x%x in %s`
- `0x180020734`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18002073b`: `CRpcUtils::GetClientToken`
- `0x1800207b4`: `%s with Trace ID 0x%x Completed`
- `0x180020989`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800208d9`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800207f0`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcIsCurrentSessionTerminalRemote(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  RPC_STATUS v5; // eax
  int v6; // ebx
  RPC_STATUS v7; // eax
  signed int IsTerminalRemote; // edi
  HANDLE CurrentThread; // rax
  int v10; // eax
  bool v11; // sf
  void *v12; // rax
  void *v13; // rbx
  unsigned int v14; // r14d
  int v15; // esi
  HANDLE v16; // rcx
  HANDLE v18; // rax
  signed int v19; // eax
  signed int LastError; // eax
  signed int v21; // eax
  HANDLE v22; // rax
  void *v23; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v25; // rax
  wchar_t *v26; // rax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-C4h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  void **v31; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CTraceBase *v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h]
  const char *v36; // [rsp+80h] [rbp-80h]
  DWORD pSessionId; // [rsp+88h] [rbp-78h] BYREF
  unsigned int Pid; // [rsp+8Ch] [rbp-74h] BYREF
  int v39; // [rsp+90h] [rbp-70h]
  unsigned __int16 v40[262]; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t *Str; // [rsp+2A8h] [rbp+1A8h]

  v31 = &CTraceBase::`vftable';
  v33[1] = 1;
  v34 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v31, 1, "RpcIsCurrentSessionTerminalRemote");
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
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v34) >= 0 && v34 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v34 + 32LL))(v34, &pguid);
      v33[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v34 + 24LL))(v34);
      v35 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v31, "RpcIsCurrentSessionTerminalRemote");
    CTraceBase::GenerateTraceID(&pguid, v33);
  }
  else
  {
    CoCreateGuid(&pguid);
    v33[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v35 = 0;
LABEL_4:
  v31 = &CRpcCallTrace::`vftable';
  v36 = "RpcIsCurrentSessionTerminalRemote";
  pSessionId = -1;
  Pid = -1;
  v39 = 0;
  memset_0(v40, 0, 0x208u);
  if ( v39 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v36, v33[0]);
  v4 = g_DebugTraceComponent & 1;
  pSessionId = -1;
  Pid = -1;
  v5 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    ProcessIdToSessionId(Pid, &pSessionId);
    if ( v4 )
    {
      v22 = OpenProcess(0x400u, 0, Pid);
      v23 = v22;
      if ( v22 )
      {
        InformationProcess = NtQueryInformationProcess(v22, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v6 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v25 = wcsrchr(Str, 0x5Cu);
          if ( v25 )
            v26 = v25 + 1;
          else
            v26 = Str;
          StringCchCopyW(v40, 0x104u, v26);
        }
        CloseHandle(v23);
      }
    }
  }
  if ( v39 )
  {
    if ( v6 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid, pSessionId, v40);
    }
  }
  TokenHandle = 0;
  v7 = RpcImpersonateClient(0);
  IsTerminalRemote = v7;
  if ( v7 > 0 )
    IsTerminalRemote = (unsigned __int16)v7 | 0x80070000;
  if ( IsTerminalRemote < 0 )
  {
    _DbgPrintMessage(
      8,
      "RpcImpersonateClient failed: 0x%x in %s",
      (unsigned int)IsTerminalRemote,
      "CRpcUtils::GetClientToken");
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      IsTerminalRemote = 0;
    }
    else
    {
      LastError = GetLastError();
      IsTerminalRemote = LastError;
      if ( LastError > 0 )
        IsTerminalRemote = (unsigned __int16)LastError | 0x80070000;
    }
    v10 = RpcRevertToSelf();
    v11 = v10 < 0;
    if ( v10 > 0 )
    {
      v10 = (unsigned __int16)v10 | 0x80070000;
      v11 = v10 < 0;
    }
    if ( v11 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v10);
      IsTerminalRemote = -2147024891;
    }
    else
    {
      if ( IsTerminalRemote >= 0 )
      {
        v12 = TokenHandle;
LABEL_20:
        v13 = v12;
        goto LABEL_21;
      }
      _DbgPrintMessage(
        8,
        "OpenThreadToken failed: 0x%x in %s",
        (unsigned int)IsTerminalRemote,
        "CRpcUtils::GetClientToken");
    }
  }
  v12 = TokenHandle;
  if ( !TokenHandle )
    goto LABEL_20;
  v13 = 0;
  CloseHandle(TokenHandle);
LABEL_21:
  if ( IsTerminalRemote < 0 )
  {
    _DbgPrintMessage(
      8,
      "CRpcUtils::GetClientToken failed: 0x%x in %s",
      IsTerminalRemote,
      "RpcIsCurrentSessionTerminalRemote");
    goto LABEL_30;
  }
  v14 = 0;
  hObject = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  IsTerminalRemote = 0;
  v15 = 4;
  if ( v13 )
  {
    v16 = v13;
LABEL_24:
    if ( GetTokenInformation(v16, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_25;
    v21 = GetLastError();
    IsTerminalRemote = v21;
    if ( v21 > 0 )
      IsTerminalRemote = (unsigned __int16)v21 | 0x80070000;
    if ( IsTerminalRemote >= 0 )
LABEL_25:
      v14 = TokenInformation;
    else
      _DbgPrintMessage(
        8,
        "GetTokenInformation failed: 0x%x in %s",
        (unsigned int)IsTerminalRemote,
        "CUtils::GetUserSessionId");
    goto LABEL_26;
  }
  v18 = GetCurrentThread();
  if ( OpenThreadToken(v18, 8u, 1, &hObject) )
    goto LABEL_36;
  v19 = GetLastError();
  IsTerminalRemote = v19;
  if ( v19 > 0 )
    IsTerminalRemote = (unsigned __int16)v19 | 0x80070000;
  if ( IsTerminalRemote >= 0 )
  {
LABEL_36:
    v16 = hObject;
    goto LABEL_24;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)IsTerminalRemote, "CUtils::GetUserSessionId");
LABEL_26:
  if ( hObject )
    CloseHandle(hObject);
  if ( IsTerminalRemote < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::GetUserSessionId() failed: 0x%x in %s",
      IsTerminalRemote,
      "RpcIsCurrentSessionTerminalRemote");
  }
  else
  {
    IsTerminalRemote = RpcIsTerminalRemote(a1, v14, a2);
    if ( IsTerminalRemote < 0 )
    {
      if ( IsTerminalRemote != -2147022646 )
        v15 = 8;
      _DbgPrintMessage(v15, "RpcIsTerminalRemote() failed with 0x%08x on session %d", IsTerminalRemote, v14);
    }
  }
LABEL_30:
  v31 = &CRpcCallTrace::`vftable';
  if ( v39 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v36, v33[0]);
  v31 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v35 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_32;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_32:
  v34 = 0;
  if ( v13 )
    CloseHandle(v13);
  return (unsigned int)IsTerminalRemote;
}

```

## disassembly

```asm
0x1800203e0  mov     [rsp-8+arg_10], rbx
0x1800203e5  push    rbp
0x1800203e6  push    rsi
0x1800203e7  push    rdi
0x1800203e8  push    r12
0x1800203ea  push    r13
0x1800203ec  push    r14
0x1800203ee  push    r15
0x1800203f0  lea     rbp, [rsp-2C0h]
0x1800203f8  sub     rsp, 3C0h
0x1800203ff  mov     rax, cs:__security_cookie
0x180020406  xor     rax, rsp
0x180020409  mov     [rbp+2F0h+var_40], rax
0x180020410  mov     r12, rdx
0x180020413  mov     r15, rcx
0x180020416  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18002041d  mov     [rsp+3F0h+var_3A0], rax
0x180020422  mov     esi, 1
0x180020427  mov     [rsp+3F0h+var_384], esi
0x18002042b  xor     r13d, r13d
0x18002042e  mov     [rsp+3F0h+var_380], r13
0x180020433  lea     rbx, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote"
0x18002043a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180020441  jnz     loc_18002088C
0x180020447  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18002044c  call    cs:__imp_CoCreateGuid
0x180020453  nop     dword ptr [rax+rax+00h]
0x180020458  mov     eax, esi
0x18002045a  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180020462  add     eax, esi
0x180020464  mov     [rsp+3F0h+var_388], eax
0x180020468  mov     [rsp+3F0h+var_378], r13d
0x18002046d  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180020474  mov     [rsp+3F0h+var_3A0], rax
0x180020479  mov     [rbp+2F0h+var_370], rbx
0x18002047d  or      ebx, 0FFFFFFFFh
0x180020480  mov     [rbp+2F0h+pSessionId], ebx
0x180020483  mov     [rbp+2F0h+Pid], ebx
0x180020486  mov     [rbp+2F0h+var_360], r13d
0x18002048a  xor     edx, edx; Val
0x18002048c  mov     r8d, 208h; Size
0x180020492  lea     rcx, [rbp+2F0h+var_35C]; void *
0x180020496  call    memset_0
0x18002049b  cmp     [rbp+2F0h+var_360], r13d
0x18002049f  jnz     loc_180020772
0x1800204a5  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x1800204ab  and     edi, esi
0x1800204ad  mov     [rbp+2F0h+pSessionId], ebx
0x1800204b0  mov     [rbp+2F0h+Pid], ebx
0x1800204b3  lea     rdx, [rbp+2F0h+Pid]; Pid
0x1800204b7  xor     ecx, ecx; Binding
0x1800204b9  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800204c0  nop     dword ptr [rax+rax+00h]
0x1800204c5  mov     ebx, eax
0x1800204c7  mov     r14d, 80070000h
0x1800204cd  test    eax, eax
0x1800204cf  jg      loc_18002070F
0x1800204d5  test    ebx, ebx
0x1800204d7  js      short loc_1800204F4
0x1800204d9  lea     rdx, [rbp+2F0h+pSessionId]; pSessionId
0x1800204dd  mov     ecx, [rbp+2F0h+Pid]; dwProcessId
0x1800204e0  call    cs:__imp_ProcessIdToSessionId
0x1800204e7  nop     dword ptr [rax+rax+00h]
0x1800204ec  test    edi, edi
0x1800204ee  jnz     loc_1800209B6
0x1800204f4  cmp     [rbp+2F0h+var_360], r13d
0x1800204f8  jnz     loc_1800207CA
0x1800204fe  mov     [rsp+3F0h+TokenHandle], r13
0x180020503  xor     ecx, ecx; BindingHandle
0x180020505  call    cs:__imp_RpcImpersonateClient
0x18002050c  nop     dword ptr [rax+rax+00h]
0x180020511  mov     edi, eax
0x180020513  test    eax, eax
0x180020515  jg      loc_180020729
0x18002051b  mov     r14d, 8
0x180020521  test    edi, edi
0x180020523  js      loc_180020734
0x180020529  call    cs:__imp_GetCurrentThread
0x180020530  nop     dword ptr [rax+rax+00h]
0x180020535  mov     rcx, rax; ThreadHandle
0x180020538  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18002053d  mov     r8d, esi; OpenAsSelf
0x180020540  lea     edx, [r14+6]; DesiredAccess
0x180020544  call    cs:__imp_OpenThreadToken
0x18002054b  nop     dword ptr [rax+rax+00h]
0x180020550  test    eax, eax
0x180020552  jz      loc_180020942
0x180020558  mov     edi, r13d
0x18002055b  call    cs:__imp_RpcRevertToSelf
0x180020562  nop     dword ptr [rax+rax+00h]
0x180020567  test    eax, eax
0x180020569  jg      loc_18002071A
0x18002056f  js      loc_180020A58
0x180020575  test    edi, edi
0x180020577  js      loc_180020A74
0x18002057d  mov     rax, [rsp+3F0h+TokenHandle]
0x180020582  mov     rbx, rax
0x180020585  test    edi, edi
0x180020587  js      loc_180020806
0x18002058d  mov     r14d, r13d
0x180020590  mov     [rsp+3F0h+hObject], r13
0x180020595  mov     [rsp+3F0h+TokenInformation], r13d
0x18002059a  mov     [rsp+3F0h+var_3B4], r13d
0x18002059f  mov     edi, r13d
0x1800205a2  mov     esi, 4
0x1800205a7  test    rbx, rbx
0x1800205aa  jz      loc_180020693
0x1800205b0  mov     rcx, rbx; TokenHandle
0x1800205b3  lea     rax, [rsp+3F0h+var_3B4]
0x1800205b8  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1800205bd  mov     r9d, esi; TokenInformationLength
0x1800205c0  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x1800205c5  mov     edx, 0Ch; TokenInformationClass
0x1800205ca  call    cs:__imp_GetTokenInformation
0x1800205d1  nop     dword ptr [rax+rax+00h]
0x1800205d6  test    eax, eax
0x1800205d8  jz      loc_180020966
0x1800205de  mov     r14d, [rsp+3F0h+TokenInformation]
0x1800205e3  mov     rcx, [rsp+3F0h+hObject]; hObject
0x1800205e8  test    rcx, rcx
0x1800205eb  jz      short loc_1800205F9
0x1800205ed  call    cs:__imp_CloseHandle
0x1800205f4  nop     dword ptr [rax+rax+00h]
0x1800205f9  test    edi, edi
0x1800205fb  js      loc_180020A80
0x180020601  mov     r8, r12
0x180020604  mov     edx, r14d
0x180020607  mov     rcx, r15
0x18002060a  call    RpcIsTerminalRemote
0x18002060f  mov     edi, eax
0x180020611  test    eax, eax
0x180020613  js      loc_180020AA0
0x180020619  mov     esi, 1
0x18002061e  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180020625  mov     [rsp+3F0h+var_3A0], rax
0x18002062a  cmp     [rbp+2F0h+var_360], r13d
0x18002062e  jnz     loc_18002079E
0x180020634  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18002063b  mov     [rsp+3F0h+var_3A0], rax
0x180020640  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180020647  jnz     loc_1800206CE
0x18002064d  mov     [rsp+3F0h+var_380], r13
0x180020652  test    rbx, rbx
0x180020655  jz      short loc_180020666
0x180020657  mov     rcx, rbx; hObject
0x18002065a  call    cs:__imp_CloseHandle
0x180020661  nop     dword ptr [rax+rax+00h]
0x180020666  mov     eax, edi
0x180020668  mov     rcx, [rbp+2F0h+var_40]
0x18002066f  xor     rcx, rsp; StackCookie
0x180020672  call    __security_check_cookie
0x180020677  mov     rbx, [rsp+3F0h+arg_10]
0x18002067f  add     rsp, 3C0h
0x180020686  pop     r15
0x180020688  pop     r14
0x18002068a  pop     r13
0x18002068c  pop     r12
0x18002068e  pop     rdi
0x18002068f  pop     rsi
0x180020690  pop     rbp
0x180020691  retn
0x180020693  call    cs:__imp_GetCurrentThread
0x18002069a  nop     dword ptr [rax+rax+00h]
0x18002069f  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x1800206a4  mov     edx, 8; DesiredAccess
0x1800206a9  lea     r8d, [rdx-7]; OpenAsSelf
0x1800206ad  mov     rcx, rax; ThreadHandle
0x1800206b0  call    cs:__imp_OpenThreadToken
0x1800206b7  nop     dword ptr [rax+rax+00h]
0x1800206bc  test    eax, eax
0x1800206be  jz      loc_180020824
0x1800206c4  mov     rcx, [rsp+3F0h+hObject]
0x1800206c9  jmp     loc_1800205B3
0x1800206ce  cmp     [rsp+3F0h+var_378], r13d
0x1800206d3  jnz     loc_18002064D
0x1800206d9  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x1800206df  cmp     ecx, 0FFFFFFFFh
0x1800206e2  jz      loc_18002064D
0x1800206e8  xor     edx, edx; lpTlsValue
0x1800206ea  call    cs:__imp_TlsSetValue
0x1800206f1  nop     dword ptr [rax+rax+00h]
0x1800206f6  test    eax, eax
0x1800206f8  jnz     loc_180020AC7
0x1800206fe  call    cs:__imp_GetLastError
0x180020705  nop     dword ptr [rax+rax+00h]
0x18002070a  jmp     loc_180020AE3
0x18002070f  movzx   ebx, ax
0x180020712  or      ebx, r14d
0x180020715  jmp     loc_1800204D5
0x18002071a  movzx   eax, ax
0x18002071d  or      eax, 80070000h
0x180020722  test    eax, eax
0x180020724  jmp     loc_18002056F
0x180020729  movzx   edi, ax
0x18002072c  or      edi, r14d
0x18002072f  jmp     loc_18002051B
0x180020734  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18002073b  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x180020742  mov     ecx, r14d; int
0x180020745  mov     r8d, edi
0x180020748  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002074d  mov     rax, [rsp+3F0h+TokenHandle]
0x180020752  test    rax, rax
0x180020755  jz      loc_180020582
0x18002075b  mov     rbx, r13
0x18002075e  mov     rcx, rax; hObject
0x180020761  call    cs:__imp_CloseHandle
0x180020768  nop     dword ptr [rax+rax+00h]
0x18002076d  jmp     loc_180020585
0x180020772  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180020779  jz      loc_1800204A5
0x18002077f  mov     r9d, [rsp+3F0h+var_388]
0x180020784  mov     r8, [rbp+2F0h+var_370]
0x180020788  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18002078f  mov     ecx, 2; int
0x180020794  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020799  jmp     loc_1800204A5
0x18002079e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x1800207a5  jz      loc_180020634
0x1800207ab  mov     r9d, [rsp+3F0h+var_388]
0x1800207b0  mov     r8, [rbp+2F0h+var_370]
0x1800207b4  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x1800207bb  mov     ecx, 2; int
0x1800207c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800207c5  jmp     loc_180020634
0x1800207ca  test    ebx, ebx
0x1800207cc  js      loc_18002085E
0x1800207d2  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x1800207d9  jz      loc_1800204FE
0x1800207df  lea     rax, [rbp+2F0h+var_35C]
0x1800207e3  mov     [rsp+3F0h+ReturnLength], rax
0x1800207e8  mov     r9d, [rbp+2F0h+pSessionId]
0x1800207ec  mov     r8d, [rbp+2F0h+Pid]
0x1800207f0  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x1800207f7  mov     ecx, 2; int
0x1800207fc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020801  jmp     loc_1800204FE
0x180020806  lea     r9, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote"
0x18002080d  mov     r8d, edi
0x180020810  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180020817  mov     ecx, r14d; int
0x18002081a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002081f  jmp     loc_18002061E
0x180020824  call    cs:__imp_GetLastError
0x18002082b  nop     dword ptr [rax+rax+00h]
0x180020830  mov     edi, eax
0x180020832  test    eax, eax
0x180020834  jg      short loc_180020881
0x180020836  test    edi, edi
0x180020838  jns     loc_1800206C4
0x18002083e  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180020845  mov     r8d, edi
0x180020848  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18002084f  mov     ecx, 8; int
0x180020854  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020859  jmp     loc_1800205E3
0x18002085e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180020865  jz      loc_1800204FE
0x18002086b  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180020872  mov     ecx, 2; int
0x180020877  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002087c  jmp     loc_1800204FE
0x180020881  movzx   edi, ax
0x180020884  or      edi, 80070000h
0x18002088a  jmp     short loc_180020836
0x18002088c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180020893  jz      short loc_1800208B3
0x180020895  mov     [rsp+3F0h+ReturnLength], rbx
0x18002089a  mov     r9d, esi
0x18002089d  lea     r8, [rsp+3F0h+var_3A0]
0x1800208a2  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x1800208a9  mov     ecx, 2; int
0x1800208ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800208b3  mov     [rsp+3F0h+hObject], r13
0x1800208b8  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x1800208bd  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800208c2  test    eax, eax
0x1800208c4  js      short loc_1800208EA
0x1800208c6  cmp     [rsp+3F0h+hObject], r13
0x1800208cb  jz      short loc_1800208EA
0x1800208cd  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x1800208d4  jz      short loc_1800208EA
0x1800208d6  mov     r8d, esi
0x1800208d9  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x1800208e0  mov     ecx, 2; int
0x1800208e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800208ea  xor     edx, edx; char *
0x1800208ec  xor     ecx, ecx; lpTlsValue
0x1800208ee  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800208f3  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x1800208f8  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800208fd  test    eax, eax
0x1800208ff  js      loc_180020995
0x180020905  mov     rcx, [rsp+3F0h+var_380]
0x18002090a  test    rcx, rcx
0x18002090d  jz      loc_180020995
0x180020913  mov     rax, [rcx]
0x180020916  lea     rdx, [rsp+3F0h+pguid]
0x18002091b  mov     rax, [rax+20h]
0x18002091f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
