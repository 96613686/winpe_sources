# RpcIsCurrentSessionTerminalRemote

- ea: `0x18000e010`
- end: `0x18000e684`
- name: `RpcIsCurrentSessionTerminalRemote`
- size: `1652`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18000e010`
- `0x18000e690`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e5bc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e5bc`
- `ntdll!NtQueryInformationProcess` at `0x18000e5a0`
- `ntdll!NtQueryInformationProcess` at `0x18000e5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e678`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e2c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e66a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e2c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e66a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e156`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e299`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e156`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e282`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e104`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e250`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e250`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5e8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e07c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e07c`
- `RPCRT4!RpcImpersonateClient` at `0x18000e123`
- `RPCRT4!RpcImpersonateClient` at `0x18000e123`
- `RPCRT4!RpcRevertToSelf` at `0x18000e167`
- `RPCRT4!RpcRevertToSelf` at `0x18000e167`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e0e3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e0e3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e574`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e574`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e1d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e1d0`

## string_xrefs

- `0x18000e3d9`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000e401`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000e60f`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000e303`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000e30a`: `CRpcUtils::GetClientToken`
- `0x18000e37d`: `%s with Trace ID 0x%x Completed`
- `0x18000e53c`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000e49c`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000e3b9`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
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
0x18000e010  mov     [rsp-8+arg_10], rbx
0x18000e015  push    rbp
0x18000e016  push    rsi
0x18000e017  push    rdi
0x18000e018  push    r12
0x18000e01a  push    r13
0x18000e01c  push    r14
0x18000e01e  push    r15
0x18000e020  lea     rbp, [rsp-2C0h]
0x18000e028  sub     rsp, 3C0h
0x18000e02f  mov     rax, cs:__security_cookie
0x18000e036  xor     rax, rsp
0x18000e039  mov     [rbp+2F0h+var_40], rax
0x18000e040  mov     r12, rdx
0x18000e043  mov     r15, rcx
0x18000e046  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000e04d  mov     [rsp+3F0h+var_3A0], rax
0x18000e052  mov     esi, 1
0x18000e057  mov     [rsp+3F0h+var_384], esi
0x18000e05b  xor     r13d, r13d
0x18000e05e  mov     [rsp+3F0h+var_380], r13
0x18000e063  lea     rbx, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote"
0x18000e06a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000e071  jnz     loc_18000E44F
0x18000e077  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000e07c  call    cs:__imp_CoCreateGuid
0x18000e082  mov     eax, esi
0x18000e084  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000e08c  add     eax, esi
0x18000e08e  mov     [rsp+3F0h+var_388], eax
0x18000e092  mov     [rsp+3F0h+var_378], r13d
0x18000e097  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000e09e  mov     [rsp+3F0h+var_3A0], rax
0x18000e0a3  mov     [rbp+2F0h+var_370], rbx
0x18000e0a7  or      ebx, 0FFFFFFFFh
0x18000e0aa  mov     [rbp+2F0h+pSessionId], ebx
0x18000e0ad  mov     [rbp+2F0h+Pid], ebx
0x18000e0b0  mov     [rbp+2F0h+var_360], r13d
0x18000e0b4  xor     edx, edx; Val
0x18000e0b6  mov     r8d, 208h; Size
0x18000e0bc  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18000e0c0  call    memset_0
0x18000e0c5  cmp     [rbp+2F0h+var_360], r13d
0x18000e0c9  jnz     loc_18000E33B
0x18000e0cf  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000e0d5  and     edi, esi
0x18000e0d7  mov     [rbp+2F0h+pSessionId], ebx
0x18000e0da  mov     [rbp+2F0h+Pid], ebx
0x18000e0dd  lea     rdx, [rbp+2F0h+Pid]; Pid
0x18000e0e1  xor     ecx, ecx; Binding
0x18000e0e3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e0e9  mov     ebx, eax
0x18000e0eb  mov     r14d, 80070000h
0x18000e0f1  test    eax, eax
0x18000e0f3  jg      loc_18000E2DE
0x18000e0f9  test    ebx, ebx
0x18000e0fb  js      short loc_18000E112
0x18000e0fd  lea     rdx, [rbp+2F0h+pSessionId]; pSessionId
0x18000e101  mov     ecx, [rbp+2F0h+Pid]; dwProcessId
0x18000e104  call    cs:__imp_ProcessIdToSessionId
0x18000e10a  test    edi, edi
0x18000e10c  jnz     loc_18000E569
0x18000e112  cmp     [rbp+2F0h+var_360], r13d
0x18000e116  jnz     loc_18000E393
0x18000e11c  mov     [rsp+3F0h+TokenHandle], r13
0x18000e121  xor     ecx, ecx; BindingHandle
0x18000e123  call    cs:__imp_RpcImpersonateClient
0x18000e129  mov     edi, eax
0x18000e12b  test    eax, eax
0x18000e12d  jg      loc_18000E2F8
0x18000e133  mov     r14d, 8
0x18000e139  test    edi, edi
0x18000e13b  js      loc_18000E303
0x18000e141  call    cs:__imp_GetCurrentThread
0x18000e147  mov     rcx, rax; ThreadHandle
0x18000e14a  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18000e14f  mov     r8d, esi; OpenAsSelf
0x18000e152  lea     edx, [r14+6]; DesiredAccess
0x18000e156  call    cs:__imp_OpenThreadToken
0x18000e15c  test    eax, eax
0x18000e15e  jz      loc_18000E501
0x18000e164  mov     edi, r13d
0x18000e167  call    cs:__imp_RpcRevertToSelf
0x18000e16d  test    eax, eax
0x18000e16f  jg      loc_18000E2E9
0x18000e175  js      loc_18000E5F3
0x18000e17b  test    edi, edi
0x18000e17d  js      loc_18000E60F
0x18000e183  mov     rax, [rsp+3F0h+TokenHandle]
0x18000e188  mov     rbx, rax
0x18000e18b  test    edi, edi
0x18000e18d  js      loc_18000E3CF
0x18000e193  mov     r14d, r13d
0x18000e196  mov     [rsp+3F0h+hObject], r13
0x18000e19b  mov     [rsp+3F0h+TokenInformation], r13d
0x18000e1a0  mov     [rsp+3F0h+var_3B4], r13d
0x18000e1a5  mov     edi, r13d
0x18000e1a8  mov     esi, 4
0x18000e1ad  test    rbx, rbx
0x18000e1b0  jz      loc_18000E282
0x18000e1b6  mov     rcx, rbx; TokenHandle
0x18000e1b9  lea     rax, [rsp+3F0h+var_3B4]
0x18000e1be  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x18000e1c3  mov     r9d, esi; TokenInformationLength
0x18000e1c6  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x18000e1cb  mov     edx, 0Ch; TokenInformationClass
0x18000e1d0  call    cs:__imp_GetTokenInformation
0x18000e1d6  test    eax, eax
0x18000e1d8  jz      loc_18000E51F
0x18000e1de  mov     r14d, [rsp+3F0h+TokenInformation]
0x18000e1e3  mov     rcx, [rsp+3F0h+hObject]; hObject
0x18000e1e8  test    rcx, rcx
0x18000e1eb  jz      short loc_18000E1F3
0x18000e1ed  call    cs:__imp_CloseHandle
0x18000e1f3  test    edi, edi
0x18000e1f5  js      loc_18000E61B
0x18000e1fb  mov     r8, r12
0x18000e1fe  mov     edx, r14d
0x18000e201  mov     rcx, r15
0x18000e204  call    RpcIsTerminalRemote
0x18000e209  mov     edi, eax
0x18000e20b  test    eax, eax
0x18000e20d  js      loc_18000E63B
0x18000e213  mov     esi, 1
0x18000e218  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000e21f  mov     [rsp+3F0h+var_3A0], rax
0x18000e224  cmp     [rbp+2F0h+var_360], r13d
0x18000e228  jnz     loc_18000E367
0x18000e22e  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000e235  mov     [rsp+3F0h+var_3A0], rax
0x18000e23a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000e241  jnz     short loc_18000E2B1
0x18000e243  mov     [rsp+3F0h+var_380], r13
0x18000e248  test    rbx, rbx
0x18000e24b  jz      short loc_18000E256
0x18000e24d  mov     rcx, rbx; hObject
0x18000e250  call    cs:__imp_CloseHandle
0x18000e256  mov     eax, edi
0x18000e258  mov     rcx, [rbp+2F0h+var_40]
0x18000e25f  xor     rcx, rsp; StackCookie
0x18000e262  call    __security_check_cookie
0x18000e267  mov     rbx, [rsp+3F0h+arg_10]
0x18000e26f  add     rsp, 3C0h
0x18000e276  pop     r15
0x18000e278  pop     r14
0x18000e27a  pop     r13
0x18000e27c  pop     r12
0x18000e27e  pop     rdi
0x18000e27f  pop     rsi
0x18000e280  pop     rbp
0x18000e281  retn
0x18000e282  call    cs:__imp_GetCurrentThread
0x18000e288  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x18000e28d  mov     edx, 8; DesiredAccess
0x18000e292  lea     r8d, [rdx-7]; OpenAsSelf
0x18000e296  mov     rcx, rax; ThreadHandle
0x18000e299  call    cs:__imp_OpenThreadToken
0x18000e29f  test    eax, eax
0x18000e2a1  jz      loc_18000E3ED
0x18000e2a7  mov     rcx, [rsp+3F0h+hObject]
0x18000e2ac  jmp     loc_18000E1B9
0x18000e2b1  cmp     [rsp+3F0h+var_378], r13d
0x18000e2b6  jnz     short loc_18000E243
0x18000e2b8  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000e2be  cmp     ecx, 0FFFFFFFFh
0x18000e2c1  jz      short loc_18000E243
0x18000e2c3  xor     edx, edx; lpTlsValue
0x18000e2c5  call    cs:__imp_TlsSetValue
0x18000e2cb  test    eax, eax
0x18000e2cd  jnz     loc_18000E662
0x18000e2d3  call    cs:__imp_GetLastError
0x18000e2d9  jmp     loc_18000E678
0x18000e2de  movzx   ebx, ax
0x18000e2e1  or      ebx, r14d
0x18000e2e4  jmp     loc_18000E0F9
0x18000e2e9  movzx   eax, ax
0x18000e2ec  or      eax, 80070000h
0x18000e2f1  test    eax, eax
0x18000e2f3  jmp     loc_18000E175
0x18000e2f8  movzx   edi, ax
0x18000e2fb  or      edi, r14d
0x18000e2fe  jmp     loc_18000E133
0x18000e303  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000e30a  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000e311  mov     ecx, r14d; int
0x18000e314  mov     r8d, edi
0x18000e317  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e31c  mov     rax, [rsp+3F0h+TokenHandle]
0x18000e321  test    rax, rax
0x18000e324  jz      loc_18000E188
0x18000e32a  mov     rbx, r13
0x18000e32d  mov     rcx, rax; hObject
0x18000e330  call    cs:__imp_CloseHandle
0x18000e336  jmp     loc_18000E18B
0x18000e33b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e342  jz      loc_18000E0CF
0x18000e348  mov     r9d, [rsp+3F0h+var_388]
0x18000e34d  mov     r8, [rbp+2F0h+var_370]
0x18000e351  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000e358  mov     ecx, 2; int
0x18000e35d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e362  jmp     loc_18000E0CF
0x18000e367  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e36e  jz      loc_18000E22E
0x18000e374  mov     r9d, [rsp+3F0h+var_388]
0x18000e379  mov     r8, [rbp+2F0h+var_370]
0x18000e37d  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000e384  mov     ecx, 2; int
0x18000e389  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e38e  jmp     loc_18000E22E
0x18000e393  test    ebx, ebx
0x18000e395  js      loc_18000E421
0x18000e39b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e3a2  jz      loc_18000E11C
0x18000e3a8  lea     rax, [rbp+2F0h+var_35C]
0x18000e3ac  mov     [rsp+3F0h+ReturnLength], rax
0x18000e3b1  mov     r9d, [rbp+2F0h+pSessionId]
0x18000e3b5  mov     r8d, [rbp+2F0h+Pid]
0x18000e3b9  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000e3c0  mov     ecx, 2; int
0x18000e3c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e3ca  jmp     loc_18000E11C
0x18000e3cf  lea     r9, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote"
0x18000e3d6  mov     r8d, edi
0x18000e3d9  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000e3e0  mov     ecx, r14d; int
0x18000e3e3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e3e8  jmp     loc_18000E218
0x18000e3ed  call    cs:__imp_GetLastError
0x18000e3f3  mov     edi, eax
0x18000e3f5  test    eax, eax
0x18000e3f7  jg      short loc_18000E444
0x18000e3f9  test    edi, edi
0x18000e3fb  jns     loc_18000E2A7
0x18000e401  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000e408  mov     r8d, edi
0x18000e40b  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000e412  mov     ecx, 8; int
0x18000e417  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e41c  jmp     loc_18000E1E3
0x18000e421  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e428  jz      loc_18000E11C
0x18000e42e  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000e435  mov     ecx, 2; int
0x18000e43a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e43f  jmp     loc_18000E11C
0x18000e444  movzx   edi, ax
0x18000e447  or      edi, 80070000h
0x18000e44d  jmp     short loc_18000E3F9
0x18000e44f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e456  jz      short loc_18000E476
0x18000e458  mov     [rsp+3F0h+ReturnLength], rbx
0x18000e45d  mov     r9d, esi
0x18000e460  lea     r8, [rsp+3F0h+var_3A0]
0x18000e465  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000e46c  mov     ecx, 2; int
0x18000e471  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e476  mov     [rsp+3F0h+hObject], r13
0x18000e47b  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x18000e480  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e485  test    eax, eax
0x18000e487  js      short loc_18000E4AD
0x18000e489  cmp     [rsp+3F0h+hObject], r13
0x18000e48e  jz      short loc_18000E4AD
0x18000e490  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000e497  jz      short loc_18000E4AD
0x18000e499  mov     r8d, esi
0x18000e49c  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000e4a3  mov     ecx, 2; int
0x18000e4a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e4ad  xor     edx, edx; char *
0x18000e4af  xor     ecx, ecx; lpTlsValue
0x18000e4b1  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000e4b6  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000e4bb  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e4c0  test    eax, eax
0x18000e4c2  js      loc_18000E548
0x18000e4c8  mov     rcx, [rsp+3F0h+var_380]
0x18000e4cd  test    rcx, rcx
0x18000e4d0  jz      short loc_18000E548
0x18000e4d2  mov     rax, [rcx]
0x18000e4d5  lea     rdx, [rsp+3F0h+pguid]
0x18000e4da  mov     rax, [rax+20h]
0x18000e4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e3  mov     rcx, [rsp+3F0h+var_380]
0x18000e4e8  mov     rax, [rcx]
0x18000e4eb  mov     rax, [rax+18h]
0x18000e4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f4  mov     [rsp+3F0h+var_388], eax
0x18000e4f8  mov     [rsp+3F0h+var_378], esi
0x18000e4fc  jmp     loc_18000E097
0x18000e501  call    cs:__imp_GetLastError
0x18000e507  mov     edi, eax
0x18000e509  test    eax, eax
0x18000e50b  jle     loc_18000E167
0x18000e511  movzx   edi, ax
0x18000e514  or      edi, 80070000h
0x18000e51a  jmp     loc_18000E167
0x18000e51f  call    cs:__imp_GetLastError
0x18000e525  mov     edi, eax
  ... truncated ...
```
