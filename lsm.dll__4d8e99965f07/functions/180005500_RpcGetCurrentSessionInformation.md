# RpcGetCurrentSessionInformation

- ea: `0x180005500`
- end: `0x180005c2c`
- name: `RpcGetCurrentSessionInformation`
- size: `1836`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005500`
- `0x180005cf0`
- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005b41`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005b41`
- `ntdll!NtQueryInformationProcess` at `0x180005b1f`
- `ntdll!NtQueryInformationProcess` at `0x180005b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000592c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000592c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000580c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005c06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000580c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005c06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000566a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800057d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000566a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800057d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000564b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800057b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000564b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800057b3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005608`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180005608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000577a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000588b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000577a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000588b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b70`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000556e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000556e`
- `RPCRT4!RpcImpersonateClient` at `0x18000562d`
- `RPCRT4!RpcImpersonateClient` at `0x18000562d`
- `RPCRT4!RpcRevertToSelf` at `0x180005681`
- `RPCRT4!RpcRevertToSelf` at `0x180005681`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800055e7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800055e7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005af1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005af1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056ee`

## string_xrefs

- `0x180005bbc`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180005950`: `OpenThreadToken failed: 0x%x in %s`
- `0x180005ba6`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000585c`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180005863`: `CRpcUtils::GetClientToken`
- `0x1800058de`: `%s with Trace ID 0x%x Completed`
- `0x180005aa5`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800059e7`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180005916`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005500  mov     [rsp-8+arg_18], rbx
0x180005505  push    rbp
0x180005506  push    rsi
0x180005507  push    rdi
0x180005508  push    r12
0x18000550a  push    r13
0x18000550c  push    r14
0x18000550e  push    r15
0x180005510  lea     rbp, [rsp-2C0h]
0x180005518  sub     rsp, 3C0h
0x18000551f  mov     rax, cs:__security_cookie
0x180005526  xor     rax, rsp
0x180005529  mov     [rbp+2F0h+var_40], rax
0x180005530  mov     r12, r8
0x180005533  mov     r15d, edx
0x180005536  mov     r14, rcx
0x180005539  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180005540  mov     [rsp+3F0h+var_3A0], rsi
0x180005545  mov     [rsp+3F0h+var_384], 1
0x18000554d  xor     r13d, r13d
0x180005550  mov     [rsp+3F0h+var_380], r13
0x180005555  lea     rbx, aRpcgetcurrents_0; "RpcGetCurrentSessionInformation"
0x18000555c  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180005563  jnz     loc_180005994
0x180005569  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000556e  call    cs:__imp_CoCreateGuid
0x180005575  nop     dword ptr [rax+rax+00h]
0x18000557a  mov     eax, 1
0x18000557f  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180005587  inc     eax
0x180005589  mov     [rsp+3F0h+var_388], eax
0x18000558d  mov     [rsp+3F0h+var_378], r13d
0x180005592  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180005599  mov     [rsp+3F0h+var_3A0], rax
0x18000559e  mov     [rbp+2F0h+var_370], rbx
0x1800055a2  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x1800055aa  mov     [rbp+2F0h+var_360], r13d
0x1800055ae  xor     edx, edx; Val
0x1800055b0  mov     r8d, 208h; Size
0x1800055b6  lea     rcx, [rbp+2F0h+var_35C]; void *
0x1800055ba  call    memset_0
0x1800055bf  cmp     [rbp+2F0h+var_360], r13d
0x1800055c3  jnz     loc_18000589C
0x1800055c9  mov     edi, r13d
0x1800055cc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800055d3  jnz     loc_180005ADC
0x1800055d9  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x1800055e1  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x1800055e5  xor     ecx, ecx; Binding
0x1800055e7  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800055ee  nop     dword ptr [rax+rax+00h]
0x1800055f3  mov     ebx, eax
0x1800055f5  test    eax, eax
0x1800055f7  jg      loc_180005831
0x1800055fd  test    ebx, ebx
0x1800055ff  js      short loc_18000561C
0x180005601  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x180005605  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x180005608  call    cs:__imp_ProcessIdToSessionId
0x18000560f  nop     dword ptr [rax+rax+00h]
0x180005614  test    edi, edi
0x180005616  jnz     loc_180005AE6
0x18000561c  cmp     [rbp+2F0h+var_360], r13d
0x180005620  jnz     loc_1800058F4
0x180005626  mov     [rsp+3F0h+TokenHandle], r13
0x18000562b  xor     ecx, ecx; BindingHandle
0x18000562d  call    cs:__imp_RpcImpersonateClient
0x180005634  nop     dword ptr [rax+rax+00h]
0x180005639  mov     edi, eax
0x18000563b  test    eax, eax
0x18000563d  jg      loc_18000584E
0x180005643  test    edi, edi
0x180005645  js      loc_18000585C
0x18000564b  call    cs:__imp_GetCurrentThread
0x180005652  nop     dword ptr [rax+rax+00h]
0x180005657  mov     rcx, rax; ThreadHandle
0x18000565a  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18000565f  mov     edx, 0Eh; DesiredAccess
0x180005664  mov     r8d, 1; OpenAsSelf
0x18000566a  call    cs:__imp_OpenThreadToken
0x180005671  nop     dword ptr [rax+rax+00h]
0x180005676  test    eax, eax
0x180005678  jz      loc_180005A54
0x18000567e  mov     edi, r13d
0x180005681  call    cs:__imp_RpcRevertToSelf
0x180005688  nop     dword ptr [rax+rax+00h]
0x18000568d  test    eax, eax
0x18000568f  jg      loc_18000583F
0x180005695  js      loc_180005B88
0x18000569b  test    edi, edi
0x18000569d  js      loc_180005BA6
0x1800056a3  mov     rax, [rsp+3F0h+TokenHandle]
0x1800056a8  mov     rbx, rax
0x1800056ab  test    edi, edi
0x1800056ad  js      loc_180005BB2
0x1800056b3  mov     esi, r13d
0x1800056b6  mov     [rsp+3F0h+hObject], r13
0x1800056bb  mov     [rsp+3F0h+TokenInformation], r13d
0x1800056c0  mov     [rsp+3F0h+var_3B4], r13d
0x1800056c5  mov     edi, r13d
0x1800056c8  test    rbx, rbx
0x1800056cb  jz      loc_1800057B3
0x1800056d1  mov     rcx, rbx; TokenHandle
0x1800056d4  lea     rax, [rsp+3F0h+var_3B4]
0x1800056d9  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1800056de  mov     r9d, 4; TokenInformationLength
0x1800056e4  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x1800056e9  mov     edx, 0Ch; TokenInformationClass
0x1800056ee  call    cs:__imp_GetTokenInformation
0x1800056f5  nop     dword ptr [rax+rax+00h]
0x1800056fa  test    eax, eax
0x1800056fc  jz      loc_180005A78
0x180005702  mov     esi, [rsp+3F0h+TokenInformation]
0x180005706  mov     rcx, [rsp+3F0h+hObject]; hObject
0x18000570b  test    rcx, rcx
0x18000570e  jz      short loc_18000571C
0x180005710  call    cs:__imp_CloseHandle
0x180005717  nop     dword ptr [rax+rax+00h]
0x18000571c  test    edi, edi
0x18000571e  js      loc_180005BD2
0x180005724  mov     r9, r12
0x180005727  mov     r8d, r15d
0x18000572a  mov     edx, esi
0x18000572c  mov     rcx, r14
0x18000572f  call    RpcGetSessionInformationEx
0x180005734  mov     edi, eax
0x180005736  test    eax, eax
0x180005738  js      loc_180005BDE
0x18000573e  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180005745  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000574c  mov     [rsp+3F0h+var_3A0], rax
0x180005751  cmp     [rbp+2F0h+var_360], 0
0x180005755  jnz     loc_1800058C8
0x18000575b  mov     [rsp+3F0h+var_3A0], rsi
0x180005760  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180005767  jnz     loc_1800057F0
0x18000576d  mov     [rsp+3F0h+var_380], r13
0x180005772  test    rbx, rbx
0x180005775  jz      short loc_180005786
0x180005777  mov     rcx, rbx; hObject
0x18000577a  call    cs:__imp_CloseHandle
0x180005781  nop     dword ptr [rax+rax+00h]
0x180005786  mov     eax, edi
0x180005788  mov     rcx, [rbp+2F0h+var_40]
0x18000578f  xor     rcx, rsp; StackCookie
0x180005792  call    __security_check_cookie
0x180005797  mov     rbx, [rsp+3F0h+arg_18]
0x18000579f  add     rsp, 3C0h
0x1800057a6  pop     r15
0x1800057a8  pop     r14
0x1800057aa  pop     r13
0x1800057ac  pop     r12
0x1800057ae  pop     rdi
0x1800057af  pop     rsi
0x1800057b0  pop     rbp
0x1800057b1  retn
0x1800057b3  call    cs:__imp_GetCurrentThread
0x1800057ba  nop     dword ptr [rax+rax+00h]
0x1800057bf  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x1800057c4  mov     edx, 8; DesiredAccess
0x1800057c9  mov     r8d, 1; OpenAsSelf
0x1800057cf  mov     rcx, rax; ThreadHandle
0x1800057d2  call    cs:__imp_OpenThreadToken
0x1800057d9  nop     dword ptr [rax+rax+00h]
0x1800057de  test    eax, eax
0x1800057e0  jz      loc_18000592C
0x1800057e6  mov     rcx, [rsp+3F0h+hObject]
0x1800057eb  jmp     loc_1800056D4
0x1800057f0  cmp     [rsp+3F0h+var_378], 0
0x1800057f5  jnz     loc_18000576D
0x1800057fb  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180005801  cmp     ecx, 0FFFFFFFFh
0x180005804  jz      loc_18000576D
0x18000580a  xor     edx, edx; lpTlsValue
0x18000580c  call    cs:__imp_TlsSetValue
0x180005813  nop     dword ptr [rax+rax+00h]
0x180005818  test    eax, eax
0x18000581a  jnz     loc_180005BFE
0x180005820  call    cs:__imp_GetLastError
0x180005827  nop     dword ptr [rax+rax+00h]
0x18000582c  jmp     loc_180005C1A
0x180005831  movzx   ebx, ax
0x180005834  or      ebx, 80070000h
0x18000583a  jmp     loc_1800055FD
0x18000583f  movzx   eax, ax
0x180005842  or      eax, 80070000h
0x180005847  test    eax, eax
0x180005849  jmp     loc_180005695
0x18000584e  movzx   edi, ax
0x180005851  or      edi, 80070000h
0x180005857  jmp     loc_180005643
0x18000585c  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180005863  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000586a  mov     r8d, edi
0x18000586d  mov     ecx, 8; int
0x180005872  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005877  mov     rax, [rsp+3F0h+TokenHandle]
0x18000587c  test    rax, rax
0x18000587f  jz      loc_1800056A8
0x180005885  mov     rbx, r13
0x180005888  mov     rcx, rax; hObject
0x18000588b  call    cs:__imp_CloseHandle
0x180005892  nop     dword ptr [rax+rax+00h]
0x180005897  jmp     loc_1800056AB
0x18000589c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800058a3  jz      loc_1800055C9
0x1800058a9  mov     r9d, [rsp+3F0h+var_388]
0x1800058ae  mov     r8, [rbp+2F0h+var_370]
0x1800058b2  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800058b9  mov     ecx, 2; int
0x1800058be  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800058c3  jmp     loc_1800055C9
0x1800058c8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800058cf  jz      loc_18000575B
0x1800058d5  mov     r9d, [rsp+3F0h+var_388]
0x1800058da  mov     r8, [rbp+2F0h+var_370]
0x1800058de  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x1800058e5  mov     ecx, 2; int
0x1800058ea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800058ef  jmp     loc_18000575B
0x1800058f4  test    ebx, ebx
0x1800058f6  js      short loc_180005966
0x1800058f8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800058ff  jz      loc_180005626
0x180005905  lea     rax, [rbp+2F0h+var_35C]
0x180005909  mov     [rsp+3F0h+ReturnLength], rax
0x18000590e  mov     r9d, [rbp+2F0h+Pid]
0x180005912  mov     r8d, [rbp+2F0h+Pid+4]
0x180005916  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000591d  mov     ecx, 2; int
0x180005922  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005927  jmp     loc_180005626
0x18000592c  call    cs:__imp_GetLastError
0x180005933  nop     dword ptr [rax+rax+00h]
0x180005938  mov     edi, eax
0x18000593a  test    eax, eax
0x18000593c  jg      short loc_180005989
0x18000593e  test    edi, edi
0x180005940  jns     loc_1800057E6
0x180005946  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000594d  mov     r8d, edi
0x180005950  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180005957  mov     ecx, 8; int
0x18000595c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005961  jmp     loc_180005706
0x180005966  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000596d  jz      loc_180005626
0x180005973  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000597a  mov     ecx, 2; int
0x18000597f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005984  jmp     loc_180005626
0x180005989  movzx   edi, ax
0x18000598c  or      edi, 80070000h
0x180005992  jmp     short loc_18000593E
0x180005994  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000599b  jz      short loc_1800059BE
0x18000599d  mov     [rsp+3F0h+ReturnLength], rbx
0x1800059a2  mov     r9d, 1
0x1800059a8  lea     r8, [rsp+3F0h+var_3A0]
0x1800059ad  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x1800059b4  mov     ecx, 2; int
0x1800059b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800059be  mov     [rsp+3F0h+hObject], r13
0x1800059c3  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x1800059c8  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800059cd  test    eax, eax
0x1800059cf  js      short loc_1800059F8
0x1800059d1  cmp     [rsp+3F0h+hObject], r13
0x1800059d6  jz      short loc_1800059F8
0x1800059d8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800059df  jz      short loc_1800059F8
0x1800059e1  mov     r8d, 1
0x1800059e7  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x1800059ee  mov     ecx, 2; int
0x1800059f3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800059f8  xor     edx, edx; char *
0x1800059fa  xor     ecx, ecx; lpTlsValue
0x1800059fc  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180005a01  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x180005a06  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180005a0b  test    eax, eax
0x180005a0d  js      loc_180005ABB
0x180005a13  mov     rcx, [rsp+3F0h+var_380]
0x180005a18  test    rcx, rcx
0x180005a1b  jz      loc_180005ABB
0x180005a21  mov     rax, [rcx]
0x180005a24  lea     rdx, [rsp+3F0h+pguid]
0x180005a29  mov     rax, [rax+20h]
0x180005a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a32  mov     rcx, [rsp+3F0h+var_380]
0x180005a37  mov     rax, [rcx]
0x180005a3a  mov     rax, [rax+18h]
0x180005a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a43  mov     [rsp+3F0h+var_388], eax
0x180005a47  mov     [rsp+3F0h+var_378], 1
0x180005a4f  jmp     loc_180005592
0x180005a54  call    cs:__imp_GetLastError
0x180005a5b  nop     dword ptr [rax+rax+00h]
0x180005a60  mov     edi, eax
0x180005a62  test    eax, eax
  ... truncated ...
```
