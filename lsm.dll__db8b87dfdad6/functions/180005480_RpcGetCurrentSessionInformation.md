# RpcGetCurrentSessionInformation

- ea: `0x180005480`
- end: `0x180005b13`
- name: `RpcGetCurrentSessionInformation`
- size: `1683`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005480`
- `0x180005bd0`
- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005a40`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005a40`
- `ntdll!NtQueryInformationProcess` at `0x180005a24`
- `ntdll!NtQueryInformationProcess` at `0x180005a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b07`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000573b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005af9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000573b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005af9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800055cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000570b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800055cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000570b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800055b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800056f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800055b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800056f2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000557c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000557c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a69`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800054ee`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800054ee`
- `RPCRT4!RpcImpersonateClient` at `0x18000559b`
- `RPCRT4!RpcImpersonateClient` at `0x18000559b`
- `RPCRT4!RpcRevertToSelf` at `0x1800055dd`
- `RPCRT4!RpcRevertToSelf` at `0x1800055dd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005561`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180005561`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800059fc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800059fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005644`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005644`

## string_xrefs

- `0x180005aaf`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180005867`: `OpenThreadToken failed: 0x%x in %s`
- `0x180005a99`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000577f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180005786`: `CRpcUtils::GetClientToken`
- `0x1800057fb`: `%s with Trace ID 0x%x Completed`
- `0x1800059b0`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800058fe`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180005833`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcGetCurrentSessionInformation(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v6; // edi
  RPC_STATUS v7; // eax
  int v8; // ebx
  RPC_STATUS v9; // eax
  signed int v10; // edi
  HANDLE CurrentThread; // rax
  int v12; // eax
  bool v13; // sf
  void *v14; // rax
  void *v15; // rbx
  unsigned int v16; // esi
  HANDLE v17; // rcx
  int SessionInformation; // eax
  HANDLE v20; // rax
  signed int v21; // eax
  signed int LastError; // eax
  signed int v23; // eax
  HANDLE v24; // rax
  void *v25; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-C4h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  void **v33; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CTraceBase *v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  const char *v38; // [rsp+80h] [rbp-80h]
  unsigned int Pid[2]; // [rsp+88h] [rbp-78h] BYREF
  int v40; // [rsp+90h] [rbp-70h]
  unsigned __int16 v41[262]; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t *Str; // [rsp+2A8h] [rbp+1A8h]

  v33 = &CTraceBase::`vftable';
  v35[1] = 1;
  v36 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v33, 1, "RpcGetCurrentSessionInformation");
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
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v36) >= 0 && v36 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v36 + 32LL))(v36, &pguid);
      v35[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v36 + 24LL))(v36);
      v37 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v33, "RpcGetCurrentSessionInformation");
    CTraceBase::GenerateTraceID(&pguid, v35);
  }
  else
  {
    CoCreateGuid(&pguid);
    v35[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v37 = 0;
LABEL_4:
  v33 = &CRpcCallTrace::`vftable';
  v38 = "RpcGetCurrentSessionInformation";
  *(_QWORD *)Pid = -1;
  v40 = 0;
  memset_0(v41, 0, 0x208u);
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v38, v35[0]);
  v6 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v6 = 260;
  *(_QWORD *)Pid = -1;
  v7 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v6 )
    {
      v24 = OpenProcess(0x400u, 0, Pid[1]);
      v25 = v24;
      if ( v24 )
      {
        InformationProcess = NtQueryInformationProcess(v24, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v8 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v27 = wcsrchr(Str, 0x5Cu);
          if ( v27 )
            v28 = v27 + 1;
          else
            v28 = Str;
          StringCchCopyW(v41, v6, v28);
        }
        CloseHandle(v25);
      }
    }
  }
  if ( v40 )
  {
    if ( v8 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v41);
    }
  }
  TokenHandle = 0;
  v9 = RpcImpersonateClient(0);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v10, "CRpcUtils::GetClientToken");
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v10 = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    v12 = RpcRevertToSelf();
    v13 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v13 = v12 < 0;
    }
    if ( v13 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v12);
      v10 = -2147024891;
    }
    else
    {
      if ( v10 >= 0 )
      {
        v14 = TokenHandle;
LABEL_22:
        v15 = v14;
        goto LABEL_23;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v10, "CRpcUtils::GetClientToken");
    }
  }
  v14 = TokenHandle;
  if ( !TokenHandle )
    goto LABEL_22;
  v15 = 0;
  CloseHandle(TokenHandle);
LABEL_23:
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", v10, "RpcGetCurrentSessionInformation");
    goto LABEL_33;
  }
  v16 = 0;
  hObject = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v10 = 0;
  if ( v15 )
  {
    v17 = v15;
LABEL_26:
    if ( GetTokenInformation(v17, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_27;
    v23 = GetLastError();
    v10 = v23;
    if ( v23 > 0 )
      v10 = (unsigned __int16)v23 | 0x80070000;
    if ( v10 >= 0 )
LABEL_27:
      v16 = TokenInformation;
    else
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v10, "CUtils::GetUserSessionId");
    goto LABEL_28;
  }
  v20 = GetCurrentThread();
  if ( OpenThreadToken(v20, 8u, 1, &hObject) )
    goto LABEL_39;
  v21 = GetLastError();
  v10 = v21;
  if ( v21 > 0 )
    v10 = (unsigned __int16)v21 | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_39:
    v17 = hObject;
    goto LABEL_26;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v10, "CUtils::GetUserSessionId");
LABEL_28:
  if ( hObject )
    CloseHandle(hObject);
  if ( v10 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::GetUserSessionId() failed: 0x%x in %s",
      (unsigned int)v10,
      "RpcGetCurrentSessionInformation");
  }
  else
  {
    SessionInformation = RpcGetSessionInformationEx(a1, v16, a2, a3);
    v10 = SessionInformation;
    if ( SessionInformation < 0 )
      _DbgPrintMessage(
        8,
        "RpcGetSessionInformationEx failed: 0x%x in %s",
        (unsigned int)SessionInformation,
        "RpcGetCurrentSessionInformation");
  }
LABEL_33:
  v33 = &CRpcCallTrace::`vftable';
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v38, v35[0]);
  v33 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v37 && CTraceBase::g_TLSIndex != -1 )
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
  v36 = 0;
  if ( v15 )
    CloseHandle(v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005480  mov     [rsp-8+arg_18], rbx
0x180005485  push    rbp
0x180005486  push    rsi
0x180005487  push    rdi
0x180005488  push    r12
0x18000548a  push    r13
0x18000548c  push    r14
0x18000548e  push    r15
0x180005490  lea     rbp, [rsp-2C0h]
0x180005498  sub     rsp, 3C0h
0x18000549f  mov     rax, cs:__security_cookie
0x1800054a6  xor     rax, rsp
0x1800054a9  mov     [rbp+2F0h+var_40], rax
0x1800054b0  mov     r12, r8
0x1800054b3  mov     r15d, edx
0x1800054b6  mov     r14, rcx
0x1800054b9  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800054c0  mov     [rsp+3F0h+var_3A0], rsi
0x1800054c5  mov     [rsp+3F0h+var_384], 1
0x1800054cd  xor     r13d, r13d
0x1800054d0  mov     [rsp+3F0h+var_380], r13
0x1800054d5  lea     rbx, aRpcgetcurrents_0; "RpcGetCurrentSessionInformation"
0x1800054dc  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x1800054e3  jnz     loc_1800058AB
0x1800054e9  lea     rcx, [rsp+3F0h+pguid]; pguid
0x1800054ee  call    cs:__imp_CoCreateGuid
0x1800054f4  mov     eax, 1
0x1800054f9  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180005501  inc     eax
0x180005503  mov     [rsp+3F0h+var_388], eax
0x180005507  mov     [rsp+3F0h+var_378], r13d
0x18000550c  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180005513  mov     [rsp+3F0h+var_3A0], rax
0x180005518  mov     [rbp+2F0h+var_370], rbx
0x18000551c  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180005524  mov     [rbp+2F0h+var_360], r13d
0x180005528  xor     edx, edx; Val
0x18000552a  mov     r8d, 208h; Size
0x180005530  lea     rcx, [rbp+2F0h+var_35C]; void *
0x180005534  call    memset_0
0x180005539  cmp     [rbp+2F0h+var_360], r13d
0x18000553d  jnz     loc_1800057B9
0x180005543  mov     edi, r13d
0x180005546  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000554d  jnz     loc_1800059E7
0x180005553  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000555b  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x18000555f  xor     ecx, ecx; Binding
0x180005561  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180005567  mov     ebx, eax
0x180005569  test    eax, eax
0x18000556b  jg      loc_180005754
0x180005571  test    ebx, ebx
0x180005573  js      short loc_18000558A
0x180005575  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x180005579  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000557c  call    cs:__imp_ProcessIdToSessionId
0x180005582  test    edi, edi
0x180005584  jnz     loc_1800059F1
0x18000558a  cmp     [rbp+2F0h+var_360], r13d
0x18000558e  jnz     loc_180005811
0x180005594  mov     [rsp+3F0h+TokenHandle], r13
0x180005599  xor     ecx, ecx; BindingHandle
0x18000559b  call    cs:__imp_RpcImpersonateClient
0x1800055a1  mov     edi, eax
0x1800055a3  test    eax, eax
0x1800055a5  jg      loc_180005771
0x1800055ab  test    edi, edi
0x1800055ad  js      loc_18000577F
0x1800055b3  call    cs:__imp_GetCurrentThread
0x1800055b9  mov     rcx, rax; ThreadHandle
0x1800055bc  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x1800055c1  mov     edx, 0Eh; DesiredAccess
0x1800055c6  mov     r8d, 1; OpenAsSelf
0x1800055cc  call    cs:__imp_OpenThreadToken
0x1800055d2  test    eax, eax
0x1800055d4  jz      loc_18000596B
0x1800055da  mov     edi, r13d
0x1800055dd  call    cs:__imp_RpcRevertToSelf
0x1800055e3  test    eax, eax
0x1800055e5  jg      loc_180005762
0x1800055eb  js      loc_180005A7B
0x1800055f1  test    edi, edi
0x1800055f3  js      loc_180005A99
0x1800055f9  mov     rax, [rsp+3F0h+TokenHandle]
0x1800055fe  mov     rbx, rax
0x180005601  test    edi, edi
0x180005603  js      loc_180005AA5
0x180005609  mov     esi, r13d
0x18000560c  mov     [rsp+3F0h+hObject], r13
0x180005611  mov     [rsp+3F0h+TokenInformation], r13d
0x180005616  mov     [rsp+3F0h+var_3B4], r13d
0x18000561b  mov     edi, r13d
0x18000561e  test    rbx, rbx
0x180005621  jz      loc_1800056F2
0x180005627  mov     rcx, rbx; TokenHandle
0x18000562a  lea     rax, [rsp+3F0h+var_3B4]
0x18000562f  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x180005634  mov     r9d, 4; TokenInformationLength
0x18000563a  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x18000563f  mov     edx, 0Ch; TokenInformationClass
0x180005644  call    cs:__imp_GetTokenInformation
0x18000564a  test    eax, eax
0x18000564c  jz      loc_180005989
0x180005652  mov     esi, [rsp+3F0h+TokenInformation]
0x180005656  mov     rcx, [rsp+3F0h+hObject]; hObject
0x18000565b  test    rcx, rcx
0x18000565e  jz      short loc_180005666
0x180005660  call    cs:__imp_CloseHandle
0x180005666  test    edi, edi
0x180005668  js      loc_180005AC5
0x18000566e  mov     r9, r12
0x180005671  mov     r8d, r15d
0x180005674  mov     edx, esi
0x180005676  mov     rcx, r14
0x180005679  call    RpcGetSessionInformationEx
0x18000567e  mov     edi, eax
0x180005680  test    eax, eax
0x180005682  js      loc_180005AD1
0x180005688  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000568f  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180005696  mov     [rsp+3F0h+var_3A0], rax
0x18000569b  cmp     [rbp+2F0h+var_360], 0
0x18000569f  jnz     loc_1800057E5
0x1800056a5  mov     [rsp+3F0h+var_3A0], rsi
0x1800056aa  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x1800056b1  jnz     short loc_180005723
0x1800056b3  mov     [rsp+3F0h+var_380], r13
0x1800056b8  test    rbx, rbx
0x1800056bb  jz      short loc_1800056C6
0x1800056bd  mov     rcx, rbx; hObject
0x1800056c0  call    cs:__imp_CloseHandle
0x1800056c6  mov     eax, edi
0x1800056c8  mov     rcx, [rbp+2F0h+var_40]
0x1800056cf  xor     rcx, rsp; StackCookie
0x1800056d2  call    __security_check_cookie
0x1800056d7  mov     rbx, [rsp+3F0h+arg_18]
0x1800056df  add     rsp, 3C0h
0x1800056e6  pop     r15
0x1800056e8  pop     r14
0x1800056ea  pop     r13
0x1800056ec  pop     r12
0x1800056ee  pop     rdi
0x1800056ef  pop     rsi
0x1800056f0  pop     rbp
0x1800056f1  retn
0x1800056f2  call    cs:__imp_GetCurrentThread
0x1800056f8  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x1800056fd  mov     edx, 8; DesiredAccess
0x180005702  mov     r8d, 1; OpenAsSelf
0x180005708  mov     rcx, rax; ThreadHandle
0x18000570b  call    cs:__imp_OpenThreadToken
0x180005711  test    eax, eax
0x180005713  jz      loc_180005849
0x180005719  mov     rcx, [rsp+3F0h+hObject]
0x18000571e  jmp     loc_18000562A
0x180005723  cmp     [rsp+3F0h+var_378], 0
0x180005728  jnz     short loc_1800056B3
0x18000572a  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180005730  cmp     ecx, 0FFFFFFFFh
0x180005733  jz      loc_1800056B3
0x180005739  xor     edx, edx; lpTlsValue
0x18000573b  call    cs:__imp_TlsSetValue
0x180005741  test    eax, eax
0x180005743  jnz     loc_180005AF1
0x180005749  call    cs:__imp_GetLastError
0x18000574f  jmp     loc_180005B07
0x180005754  movzx   ebx, ax
0x180005757  or      ebx, 80070000h
0x18000575d  jmp     loc_180005571
0x180005762  movzx   eax, ax
0x180005765  or      eax, 80070000h
0x18000576a  test    eax, eax
0x18000576c  jmp     loc_1800055EB
0x180005771  movzx   edi, ax
0x180005774  or      edi, 80070000h
0x18000577a  jmp     loc_1800055AB
0x18000577f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180005786  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000578d  mov     r8d, edi
0x180005790  mov     ecx, 8; int
0x180005795  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000579a  mov     rax, [rsp+3F0h+TokenHandle]
0x18000579f  test    rax, rax
0x1800057a2  jz      loc_1800055FE
0x1800057a8  mov     rbx, r13
0x1800057ab  mov     rcx, rax; hObject
0x1800057ae  call    cs:__imp_CloseHandle
0x1800057b4  jmp     loc_180005601
0x1800057b9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800057c0  jz      loc_180005543
0x1800057c6  mov     r9d, [rsp+3F0h+var_388]
0x1800057cb  mov     r8, [rbp+2F0h+var_370]
0x1800057cf  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800057d6  mov     ecx, 2; int
0x1800057db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800057e0  jmp     loc_180005543
0x1800057e5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800057ec  jz      loc_1800056A5
0x1800057f2  mov     r9d, [rsp+3F0h+var_388]
0x1800057f7  mov     r8, [rbp+2F0h+var_370]
0x1800057fb  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x180005802  mov     ecx, 2; int
0x180005807  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000580c  jmp     loc_1800056A5
0x180005811  test    ebx, ebx
0x180005813  js      short loc_18000587D
0x180005815  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000581c  jz      loc_180005594
0x180005822  lea     rax, [rbp+2F0h+var_35C]
0x180005826  mov     [rsp+3F0h+ReturnLength], rax
0x18000582b  mov     r9d, [rbp+2F0h+Pid]
0x18000582f  mov     r8d, [rbp+2F0h+Pid+4]
0x180005833  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000583a  mov     ecx, 2; int
0x18000583f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005844  jmp     loc_180005594
0x180005849  call    cs:__imp_GetLastError
0x18000584f  mov     edi, eax
0x180005851  test    eax, eax
0x180005853  jg      short loc_1800058A0
0x180005855  test    edi, edi
0x180005857  jns     loc_180005719
0x18000585d  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x180005864  mov     r8d, edi
0x180005867  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000586e  mov     ecx, 8; int
0x180005873  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005878  jmp     loc_180005656
0x18000587d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180005884  jz      loc_180005594
0x18000588a  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180005891  mov     ecx, 2; int
0x180005896  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000589b  jmp     loc_180005594
0x1800058a0  movzx   edi, ax
0x1800058a3  or      edi, 80070000h
0x1800058a9  jmp     short loc_180005855
0x1800058ab  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800058b2  jz      short loc_1800058D5
0x1800058b4  mov     [rsp+3F0h+ReturnLength], rbx
0x1800058b9  mov     r9d, 1
0x1800058bf  lea     r8, [rsp+3F0h+var_3A0]
0x1800058c4  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x1800058cb  mov     ecx, 2; int
0x1800058d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800058d5  mov     [rsp+3F0h+hObject], r13
0x1800058da  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x1800058df  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800058e4  test    eax, eax
0x1800058e6  js      short loc_18000590F
0x1800058e8  cmp     [rsp+3F0h+hObject], r13
0x1800058ed  jz      short loc_18000590F
0x1800058ef  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800058f6  jz      short loc_18000590F
0x1800058f8  mov     r8d, 1
0x1800058fe  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180005905  mov     ecx, 2; int
0x18000590a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000590f  xor     edx, edx; char *
0x180005911  xor     ecx, ecx; lpTlsValue
0x180005913  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180005918  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000591d  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180005922  test    eax, eax
0x180005924  js      loc_1800059C6
0x18000592a  mov     rcx, [rsp+3F0h+var_380]
0x18000592f  test    rcx, rcx
0x180005932  jz      loc_1800059C6
0x180005938  mov     rax, [rcx]
0x18000593b  lea     rdx, [rsp+3F0h+pguid]
0x180005940  mov     rax, [rax+20h]
0x180005944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005949  mov     rcx, [rsp+3F0h+var_380]
0x18000594e  mov     rax, [rcx]
0x180005951  mov     rax, [rax+18h]
0x180005955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595a  mov     [rsp+3F0h+var_388], eax
0x18000595e  mov     [rsp+3F0h+var_378], 1
0x180005966  jmp     loc_18000550C
0x18000596b  call    cs:__imp_GetLastError
0x180005971  mov     edi, eax
0x180005973  test    eax, eax
0x180005975  jle     loc_1800055DD
0x18000597b  movzx   edi, ax
0x18000597e  or      edi, 80070000h
0x180005984  jmp     loc_1800055DD
0x180005989  call    cs:__imp_GetLastError
0x18000598f  mov     edi, eax
0x180005991  test    eax, eax
0x180005993  jle     short loc_18000599E
0x180005995  movzx   edi, ax
0x180005998  or      edi, 80070000h
0x18000599e  test    edi, edi
0x1800059a0  jns     loc_180005652
0x1800059a6  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x1800059ad  mov     r8d, edi
0x1800059b0  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x1800059b7  mov     ecx, 8; int
0x1800059bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
  ... truncated ...
```
