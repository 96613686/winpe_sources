# RpcGetCurrentSessionTerminalName

- ea: `0x18000e210`
- end: `0x18000e5e5`
- name: `RpcGetCurrentSessionTerminalName`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18000e210`
- `0x18000e8b0`
- `0x18000ec10`
- `0x18000f260`
- `0x18000f320`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e570`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e2b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e480`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e2b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e480`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4fc`
- `RPCRT4!RpcImpersonateClient` at `0x18000e26b`
- `RPCRT4!RpcImpersonateClient` at `0x18000e26b`
- `RPCRT4!RpcRevertToSelf` at `0x18000e2c7`
- `RPCRT4!RpcRevertToSelf` at `0x18000e2c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e330`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e330`

## string_xrefs

- `0x18000e49d`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000e527`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000e5b8`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000e4d0`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000e4d7`: `CRpcUtils::GetClientToken`
- `0x18000e593`: `GetTokenInformation failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetCurrentSessionTerminalName(__int64 a1, __int64 a2)
{
  HANDLE v3; // rdi
  RPC_STATUS v4; // eax
  signed int v5; // esi
  HANDLE CurrentThread; // rax
  int v7; // eax
  bool v8; // sf
  void *v9; // rax
  void *v10; // rbx
  unsigned int v11; // r14d
  HANDLE v12; // rcx
  int TerminalName; // eax
  HANDLE v15; // rax
  __int64 v16; // r8
  const char *v17; // rdx
  signed int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[592]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  v25 = 0;
  v24 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v26, 0, "RpcGetCurrentSessionTerminalName");
  TokenHandle = 0;
  v4 = RpcImpersonateClient(0);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v5, "CRpcUtils::GetClientToken");
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    v7 = RpcRevertToSelf();
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v7);
      v5 = -2147024891;
    }
    else
    {
      if ( v5 >= 0 )
      {
        v9 = TokenHandle;
LABEL_11:
        v10 = v9;
        goto LABEL_12;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v5, "CRpcUtils::GetClientToken");
    }
  }
  v9 = TokenHandle;
  if ( !TokenHandle )
    goto LABEL_11;
  v10 = 0;
  CloseHandle(TokenHandle);
LABEL_12:
  if ( v5 < 0 )
  {
    v16 = (unsigned int)v5;
    v17 = "CRpcUtils::GetClientToken failed: 0x%x in %s";
    goto LABEL_35;
  }
  v11 = 0;
  hObject = 0;
  TokenInformation = 0;
  LODWORD(TokenHandle) = 0;
  v5 = 0;
  if ( v10 )
  {
    v12 = v10;
LABEL_15:
    if ( GetTokenInformation(v12, TokenSessionId, &TokenInformation, 4u, (PDWORD)&TokenHandle) )
      goto LABEL_16;
    v20 = GetLastError();
    v5 = v20;
    if ( v20 > 0 )
      v5 = (unsigned __int16)v20 | 0x80070000;
    if ( v5 >= 0 )
LABEL_16:
      v11 = TokenInformation;
    else
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", (unsigned int)v5, "CUtils::GetUserSessionId");
    goto LABEL_17;
  }
  v15 = GetCurrentThread();
  if ( OpenThreadToken(v15, 8u, 1, &hObject) )
    goto LABEL_33;
  v18 = GetLastError();
  v5 = v18;
  if ( v18 > 0 )
    v5 = (unsigned __int16)v18 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_33:
    v12 = hObject;
    goto LABEL_15;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v5, "CUtils::GetUserSessionId");
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::GetUserSessionId() failed: 0x%x in %s",
      (unsigned int)v5,
      "RpcGetCurrentSessionTerminalName");
    goto LABEL_23;
  }
  hObject = 0;
  ISessionManagerInternal::GetInstanceOfSessionManagerInternal((struct ISessionManagerInternal **)&hObject);
  v3 = hObject;
  TerminalName = (*(__int64 (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)hObject + 24LL))(hObject, &v25);
  v5 = TerminalName;
  if ( TerminalName < 0 )
  {
    v17 = "GetSessionList failed: 0x%x in %s";
  }
  else
  {
    TerminalName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, v11, &v24);
    v5 = TerminalName;
    if ( TerminalName < 0 )
    {
      v17 = "FindSessionById failed: 0x%x in %s";
    }
    else
    {
      TerminalName = RpcGetTerminalName(v24, a2);
      v5 = TerminalName;
      if ( TerminalName >= 0 )
        goto LABEL_23;
      v17 = "RpcGetTerminalName failed: 0x%x in %s";
    }
  }
  v16 = (unsigned int)TerminalName;
LABEL_35:
  _DbgPrintMessage(8, v17, v16, "RpcGetCurrentSessionTerminalName");
LABEL_23:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v26);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v3 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v10 )
    CloseHandle(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e210  mov     [rsp-8+arg_0], rbx
0x18000e215  mov     [rsp-8+arg_10], rsi
0x18000e21a  push    rbp
0x18000e21b  push    rdi
0x18000e21c  push    r13
0x18000e21e  push    r14
0x18000e220  push    r15
0x18000e222  lea     rbp, [rsp-1C0h]
0x18000e22a  sub     rsp, 2C0h
0x18000e231  mov     rax, cs:__security_cookie
0x18000e238  xor     rax, rsp
0x18000e23b  mov     [rbp+1E0h+var_30], rax
0x18000e242  mov     r15, rdx
0x18000e245  xor     edi, edi
0x18000e247  mov     [rsp+2E0h+var_290], rdi
0x18000e24c  mov     [rsp+2E0h+var_298], rdi
0x18000e251  lea     r8, aRpcgetcurrents; "RpcGetCurrentSessionTerminalName"
0x18000e258  xor     edx, edx; int
0x18000e25a  lea     rcx, [rsp+2E0h+var_280]; this
0x18000e25f  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18000e264  mov     [rsp+2E0h+TokenHandle], rdi
0x18000e269  xor     ecx, ecx; BindingHandle
0x18000e26b  call    cs:__imp_RpcImpersonateClient
0x18000e272  nop     dword ptr [rax+rax+00h]
0x18000e277  mov     esi, eax
0x18000e279  mov     ebx, 80070000h
0x18000e27e  test    eax, eax
0x18000e280  jle     short loc_18000E287
0x18000e282  movzx   esi, ax
0x18000e285  or      esi, ebx
0x18000e287  mov     r13d, 8
0x18000e28d  test    esi, esi
0x18000e28f  js      loc_18000E4D0
0x18000e295  call    cs:__imp_GetCurrentThread
0x18000e29c  nop     dword ptr [rax+rax+00h]
0x18000e2a1  mov     rcx, rax; ThreadHandle
0x18000e2a4  lea     r9, [rsp+2E0h+TokenHandle]; TokenHandle
0x18000e2a9  lea     edx, [r13+6]; DesiredAccess
0x18000e2ad  lea     r8d, [r13-7]; OpenAsSelf
0x18000e2b1  call    cs:__imp_OpenThreadToken
0x18000e2b8  nop     dword ptr [rax+rax+00h]
0x18000e2bd  test    eax, eax
0x18000e2bf  jz      loc_18000E550
0x18000e2c5  xor     esi, esi
0x18000e2c7  call    cs:__imp_RpcRevertToSelf
0x18000e2ce  nop     dword ptr [rax+rax+00h]
0x18000e2d3  test    eax, eax
0x18000e2d5  jg      loc_18000E4C4
0x18000e2db  js      loc_18000E59C
0x18000e2e1  test    esi, esi
0x18000e2e3  js      loc_18000E5B8
0x18000e2e9  mov     rax, [rsp+2E0h+TokenHandle]
0x18000e2ee  mov     rbx, rax
0x18000e2f1  test    esi, esi
0x18000e2f3  js      loc_18000E49A
0x18000e2f9  xor     r14d, r14d
0x18000e2fc  mov     [rsp+2E0h+hObject], rdi
0x18000e301  mov     [rsp+2E0h+TokenInformation], edi
0x18000e305  mov     dword ptr [rsp+2E0h+TokenHandle], edi
0x18000e309  xor     esi, esi
0x18000e30b  test    rbx, rbx
0x18000e30e  jz      loc_18000E463
0x18000e314  mov     rcx, rbx; TokenHandle
0x18000e317  lea     rax, [rsp+2E0h+TokenHandle]
0x18000e31c  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x18000e321  mov     r9d, 4; TokenInformationLength
0x18000e327  lea     r8, [rsp+2E0h+TokenInformation]; TokenInformation
0x18000e32c  lea     edx, [r9+8]; TokenInformationClass
0x18000e330  call    cs:__imp_GetTokenInformation
0x18000e337  nop     dword ptr [rax+rax+00h]
0x18000e33c  test    eax, eax
0x18000e33e  jz      loc_18000E570
0x18000e344  mov     r14d, [rsp+2E0h+TokenInformation]
0x18000e349  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000e34e  test    rcx, rcx
0x18000e351  jz      short loc_18000E35F
0x18000e353  call    cs:__imp_CloseHandle
0x18000e35a  nop     dword ptr [rax+rax+00h]
0x18000e35f  test    esi, esi
0x18000e361  js      loc_18000E4B8
0x18000e367  mov     [rsp+2E0h+hObject], rdi
0x18000e36c  lea     rcx, [rsp+2E0h+hObject]; struct ISessionManagerInternal **
0x18000e371  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18000e376  mov     rdi, [rsp+2E0h+hObject]
0x18000e37b  mov     rax, [rdi]
0x18000e37e  lea     rdx, [rsp+2E0h+var_290]
0x18000e383  mov     rcx, rdi
0x18000e386  mov     rax, [rax+18h]
0x18000e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38f  mov     esi, eax
0x18000e391  test    eax, eax
0x18000e393  js      loc_18000E5C4
0x18000e399  mov     rcx, [rsp+2E0h+var_290]
0x18000e39e  mov     rax, [rcx]
0x18000e3a1  lea     r8, [rsp+2E0h+var_298]
0x18000e3a6  mov     edx, r14d
0x18000e3a9  mov     rax, [rax+18h]
0x18000e3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b2  mov     esi, eax
0x18000e3b4  test    eax, eax
0x18000e3b6  js      loc_18000E5CD
0x18000e3bc  mov     rdx, r15
0x18000e3bf  mov     rcx, [rsp+2E0h+var_298]
0x18000e3c4  call    RpcGetTerminalName
0x18000e3c9  mov     esi, eax
0x18000e3cb  test    eax, eax
0x18000e3cd  js      loc_18000E5D6
0x18000e3d3  lea     rcx, [rsp+2E0h+var_280]; this
0x18000e3d8  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18000e3dd  nop
0x18000e3de  mov     rcx, [rsp+2E0h+var_298]
0x18000e3e3  test    rcx, rcx
0x18000e3e6  jz      short loc_18000E3F5
0x18000e3e8  mov     rax, [rcx]
0x18000e3eb  mov     rax, [rax+10h]
0x18000e3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3f4  nop
0x18000e3f5  mov     rcx, [rsp+2E0h+var_290]
0x18000e3fa  test    rcx, rcx
0x18000e3fd  jz      short loc_18000E40C
0x18000e3ff  mov     rax, [rcx]
0x18000e402  mov     rax, [rax+10h]
0x18000e406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40b  nop
0x18000e40c  test    rdi, rdi
0x18000e40f  jz      short loc_18000E421
0x18000e411  mov     rax, [rdi]
0x18000e414  mov     rcx, rdi
0x18000e417  mov     rax, [rax+10h]
0x18000e41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e420  nop
0x18000e421  test    rbx, rbx
0x18000e424  jz      short loc_18000E435
0x18000e426  mov     rcx, rbx; hObject
0x18000e429  call    cs:__imp_CloseHandle
0x18000e430  nop     dword ptr [rax+rax+00h]
0x18000e435  mov     eax, esi
0x18000e437  mov     rcx, [rbp+1E0h+var_30]
0x18000e43e  xor     rcx, rsp; StackCookie
0x18000e441  call    __security_check_cookie
0x18000e446  lea     r11, [rsp+2E0h+var_20]
0x18000e44e  mov     rbx, [r11+30h]
0x18000e452  mov     rsi, [r11+40h]
0x18000e456  mov     rsp, r11
0x18000e459  pop     r15
0x18000e45b  pop     r14
0x18000e45d  pop     r13
0x18000e45f  pop     rdi
0x18000e460  pop     rbp
0x18000e461  retn
0x18000e463  call    cs:__imp_GetCurrentThread
0x18000e46a  nop     dword ptr [rax+rax+00h]
0x18000e46f  lea     r9, [rsp+2E0h+hObject]; TokenHandle
0x18000e474  mov     r8d, 1; OpenAsSelf
0x18000e47a  mov     edx, r13d; DesiredAccess
0x18000e47d  mov     rcx, rax; ThreadHandle
0x18000e480  call    cs:__imp_OpenThreadToken
0x18000e487  nop     dword ptr [rax+rax+00h]
0x18000e48c  test    eax, eax
0x18000e48e  jz      short loc_18000E50D
0x18000e490  mov     rcx, [rsp+2E0h+hObject]
0x18000e495  jmp     loc_18000E317
0x18000e49a  mov     r8d, esi
0x18000e49d  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000e4a4  lea     r9, aRpcgetcurrents; "RpcGetCurrentSessionTerminalName"
0x18000e4ab  mov     ecx, r13d; int
0x18000e4ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e4b3  jmp     loc_18000E3D3
0x18000e4b8  mov     r8d, esi
0x18000e4bb  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x18000e4c2  jmp     short loc_18000E4A4
0x18000e4c4  movzx   eax, ax
0x18000e4c7  or      eax, ebx
0x18000e4c9  test    eax, eax
0x18000e4cb  jmp     loc_18000E2DB
0x18000e4d0  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000e4d7  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000e4de  mov     ecx, r13d; int
0x18000e4e1  mov     r8d, esi
0x18000e4e4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e4e9  mov     rax, [rsp+2E0h+TokenHandle]
0x18000e4ee  test    rax, rax
0x18000e4f1  jz      loc_18000E2EE
0x18000e4f7  xor     ebx, ebx
0x18000e4f9  mov     rcx, rax; hObject
0x18000e4fc  call    cs:__imp_CloseHandle
0x18000e503  nop     dword ptr [rax+rax+00h]
0x18000e508  jmp     loc_18000E2F1
0x18000e50d  call    cs:__imp_GetLastError
0x18000e514  nop     dword ptr [rax+rax+00h]
0x18000e519  mov     esi, eax
0x18000e51b  test    eax, eax
0x18000e51d  jg      short loc_18000E545
0x18000e51f  test    esi, esi
0x18000e521  jns     loc_18000E490
0x18000e527  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000e52e  mov     r8d, esi
0x18000e531  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000e538  mov     ecx, r13d; int
0x18000e53b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e540  jmp     loc_18000E349
0x18000e545  movzx   esi, ax
0x18000e548  or      esi, 80070000h
0x18000e54e  jmp     short loc_18000E51F
0x18000e550  call    cs:__imp_GetLastError
0x18000e557  nop     dword ptr [rax+rax+00h]
0x18000e55c  mov     esi, eax
0x18000e55e  test    eax, eax
0x18000e560  jle     loc_18000E2C7
0x18000e566  movzx   esi, ax
0x18000e569  or      esi, ebx
0x18000e56b  jmp     loc_18000E2C7
0x18000e570  call    cs:__imp_GetLastError
0x18000e577  nop     dword ptr [rax+rax+00h]
0x18000e57c  mov     esi, eax
0x18000e57e  test    eax, eax
0x18000e580  jle     short loc_18000E58B
0x18000e582  movzx   esi, ax
0x18000e585  or      esi, 80070000h
0x18000e58b  test    esi, esi
0x18000e58d  jns     loc_18000E344
0x18000e593  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x18000e59a  jmp     short loc_18000E52E
0x18000e59c  mov     r8d, eax
0x18000e59f  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18000e5a6  mov     ecx, r13d; int
0x18000e5a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5ae  mov     esi, 80070005h
0x18000e5b3  jmp     loc_18000E4E9
0x18000e5b8  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000e5bf  jmp     loc_18000E4D7
0x18000e5c4  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18000e5cb  jmp     short loc_18000E5DD
0x18000e5cd  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18000e5d4  jmp     short loc_18000E5DD
0x18000e5d6  lea     rdx, aRpcgetterminal; "RpcGetTerminalName failed: 0x%x in %s"
0x18000e5dd  mov     r8d, eax
0x18000e5e0  jmp     loc_18000E4A4
```
