# RpcGetCurrentSessionType

- ea: `0x18000db70`
- end: `0x18000de8c`
- name: `RpcGetCurrentSessionType`
- size: `796`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18000db70`
- `0x18000e5f0`
- `0x18000e8b0`
- `0x18000f260`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dc0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dd40`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dc0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dd40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dd23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dd23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd92`
- `RPCRT4!RpcImpersonateClient` at `0x18000dbc6`
- `RPCRT4!RpcImpersonateClient` at `0x18000dbc6`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc22`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dc8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dc8a`

## string_xrefs

- `0x18000de59`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000ddb9`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000de4a`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000dd66`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000dd6d`: `CRpcUtils::GetClientToken`
- `0x18000de25`: `GetTokenInformation failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcGetCurrentSessionType(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  signed int v5; // edi
  HANDLE CurrentThread; // rax
  int v7; // eax
  bool v8; // sf
  void *v9; // rax
  void *v10; // rbx
  unsigned int v11; // esi
  HANDLE v12; // rcx
  int SessionType; // eax
  HANDLE v15; // rax
  signed int v16; // eax
  signed int LastError; // eax
  signed int v18; // eax
  unsigned int TokenInformation; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[592]; // [rsp+50h] [rbp-B0h] BYREF

  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v22, 0, "RpcGetCurrentSessionType");
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
    _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", (unsigned int)v5, "RpcGetCurrentSessionType");
    goto LABEL_21;
  }
  v11 = 0;
  v5 = 0;
  hObject = 0;
  TokenInformation = 0;
  LODWORD(TokenHandle) = 0;
  if ( v10 )
  {
    v12 = v10;
LABEL_15:
    if ( GetTokenInformation(v12, TokenSessionId, &TokenInformation, 4u, (PDWORD)&TokenHandle) )
      goto LABEL_16;
    v18 = GetLastError();
    v5 = v18;
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
    if ( v5 >= 0 )
LABEL_16:
      v11 = TokenInformation;
    else
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", (unsigned int)v5, "CUtils::GetUserSessionId");
    goto LABEL_17;
  }
  v15 = GetCurrentThread();
  if ( OpenThreadToken(v15, 8u, 1, &hObject) )
    goto LABEL_25;
  v16 = GetLastError();
  v5 = v16;
  if ( v16 > 0 )
    v5 = (unsigned __int16)v16 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_25:
    v12 = hObject;
    goto LABEL_15;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v5, "CUtils::GetUserSessionId");
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "CUtils::GetUserSessionId() failed: 0x%x in %s", (unsigned int)v5, "RpcGetCurrentSessionType");
  }
  else
  {
    SessionType = RpcGetSessionType(a1, v11, a2);
    v5 = SessionType;
    if ( SessionType < 0 )
      _DbgPrintMessage(8, "RpcGetSessionType failed: 0x%x in %s", (unsigned int)SessionType, "RpcGetCurrentSessionType");
  }
LABEL_21:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v22);
  if ( v10 )
    CloseHandle(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000db70  mov     [rsp-8+arg_10], rbx
0x18000db75  mov     [rsp-8+arg_18], rsi
0x18000db7a  push    rbp
0x18000db7b  push    rdi
0x18000db7c  push    r13
0x18000db7e  push    r14
0x18000db80  push    r15
0x18000db82  lea     rbp, [rsp-1B0h]
0x18000db8a  sub     rsp, 2B0h
0x18000db91  mov     rax, cs:__security_cookie
0x18000db98  xor     rax, rsp
0x18000db9b  mov     [rbp+1D0h+var_30], rax
0x18000dba2  mov     r15, rdx
0x18000dba5  lea     r8, aRpcgetcurrents_2; "RpcGetCurrentSessionType"
0x18000dbac  mov     r14, rcx
0x18000dbaf  xor     edx, edx; int
0x18000dbb1  lea     rcx, [rsp+2D0h+var_280]; this
0x18000dbb6  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18000dbbb  xor     ecx, ecx; BindingHandle
0x18000dbbd  mov     [rsp+2D0h+TokenHandle], 0
0x18000dbc6  call    cs:__imp_RpcImpersonateClient
0x18000dbcd  nop     dword ptr [rax+rax+00h]
0x18000dbd2  mov     edi, eax
0x18000dbd4  mov     ebx, 80070000h
0x18000dbd9  test    eax, eax
0x18000dbdb  jle     short loc_18000DBE2
0x18000dbdd  movzx   edi, ax
0x18000dbe0  or      edi, ebx
0x18000dbe2  mov     r13d, 8
0x18000dbe8  test    edi, edi
0x18000dbea  js      loc_18000DD66
0x18000dbf0  call    cs:__imp_GetCurrentThread
0x18000dbf7  nop     dword ptr [rax+rax+00h]
0x18000dbfc  mov     rcx, rax; ThreadHandle
0x18000dbff  lea     r9, [rsp+2D0h+TokenHandle]; TokenHandle
0x18000dc04  lea     edx, [r13+6]; DesiredAccess
0x18000dc08  lea     r8d, [r13-7]; OpenAsSelf
0x18000dc0c  call    cs:__imp_OpenThreadToken
0x18000dc13  nop     dword ptr [rax+rax+00h]
0x18000dc18  test    eax, eax
0x18000dc1a  jz      loc_18000DDE2
0x18000dc20  xor     edi, edi
0x18000dc22  call    cs:__imp_RpcRevertToSelf
0x18000dc29  nop     dword ptr [rax+rax+00h]
0x18000dc2e  test    eax, eax
0x18000dc30  jg      loc_18000DD5A
0x18000dc36  js      loc_18000DE2E
0x18000dc3c  test    edi, edi
0x18000dc3e  js      loc_18000DE4A
0x18000dc44  mov     rax, [rsp+2D0h+TokenHandle]
0x18000dc49  mov     rbx, rax
0x18000dc4c  test    edi, edi
0x18000dc4e  js      loc_18000DE56
0x18000dc54  xor     esi, esi
0x18000dc56  xor     edi, edi
0x18000dc58  mov     [rsp+2D0h+hObject], rsi
0x18000dc5d  mov     [rsp+2D0h+TokenInformation], esi
0x18000dc61  mov     dword ptr [rsp+2D0h+TokenHandle], esi
0x18000dc65  test    rbx, rbx
0x18000dc68  jz      loc_18000DD23
0x18000dc6e  mov     rcx, rbx; TokenHandle
0x18000dc71  mov     r9d, 4; TokenInformationLength
0x18000dc77  lea     rax, [rsp+2D0h+TokenHandle]
0x18000dc7c  lea     r8, [rsp+2D0h+TokenInformation]; TokenInformation
0x18000dc81  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x18000dc86  lea     edx, [r9+8]; TokenInformationClass
0x18000dc8a  call    cs:__imp_GetTokenInformation
0x18000dc91  nop     dword ptr [rax+rax+00h]
0x18000dc96  test    eax, eax
0x18000dc98  jz      loc_18000DE02
0x18000dc9e  mov     esi, [rsp+2D0h+TokenInformation]
0x18000dca2  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18000dca7  test    rcx, rcx
0x18000dcaa  jz      short loc_18000DCB8
0x18000dcac  call    cs:__imp_CloseHandle
0x18000dcb3  nop     dword ptr [rax+rax+00h]
0x18000dcb8  test    edi, edi
0x18000dcba  js      loc_18000DE62
0x18000dcc0  mov     r8, r15
0x18000dcc3  mov     edx, esi
0x18000dcc5  mov     rcx, r14
0x18000dcc8  call    RpcGetSessionType
0x18000dccd  mov     edi, eax
0x18000dccf  test    eax, eax
0x18000dcd1  js      loc_18000DE6E
0x18000dcd7  lea     rcx, [rsp+2D0h+var_280]; this
0x18000dcdc  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18000dce1  test    rbx, rbx
0x18000dce4  jz      short loc_18000DCF5
0x18000dce6  mov     rcx, rbx; hObject
0x18000dce9  call    cs:__imp_CloseHandle
0x18000dcf0  nop     dword ptr [rax+rax+00h]
0x18000dcf5  mov     eax, edi
0x18000dcf7  mov     rcx, [rbp+1D0h+var_30]
0x18000dcfe  xor     rcx, rsp; StackCookie
0x18000dd01  call    __security_check_cookie
0x18000dd06  lea     r11, [rsp+2D0h+var_20]
0x18000dd0e  mov     rbx, [r11+40h]
0x18000dd12  mov     rsi, [r11+48h]
0x18000dd16  mov     rsp, r11
0x18000dd19  pop     r15
0x18000dd1b  pop     r14
0x18000dd1d  pop     r13
0x18000dd1f  pop     rdi
0x18000dd20  pop     rbp
0x18000dd21  retn
0x18000dd23  call    cs:__imp_GetCurrentThread
0x18000dd2a  nop     dword ptr [rax+rax+00h]
0x18000dd2f  lea     r9, [rsp+2D0h+hObject]; TokenHandle
0x18000dd34  mov     r8d, 1; OpenAsSelf
0x18000dd3a  mov     rcx, rax; ThreadHandle
0x18000dd3d  mov     edx, r13d; DesiredAccess
0x18000dd40  call    cs:__imp_OpenThreadToken
0x18000dd47  nop     dword ptr [rax+rax+00h]
0x18000dd4c  test    eax, eax
0x18000dd4e  jz      short loc_18000DDA3
0x18000dd50  mov     rcx, [rsp+2D0h+hObject]
0x18000dd55  jmp     loc_18000DC71
0x18000dd5a  movzx   eax, ax
0x18000dd5d  or      eax, ebx
0x18000dd5f  test    eax, eax
0x18000dd61  jmp     loc_18000DC36
0x18000dd66  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000dd6d  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000dd74  mov     ecx, r13d; int
0x18000dd77  mov     r8d, edi
0x18000dd7a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dd7f  mov     rax, [rsp+2D0h+TokenHandle]
0x18000dd84  test    rax, rax
0x18000dd87  jz      loc_18000DC49
0x18000dd8d  xor     ebx, ebx
0x18000dd8f  mov     rcx, rax; hObject
0x18000dd92  call    cs:__imp_CloseHandle
0x18000dd99  nop     dword ptr [rax+rax+00h]
0x18000dd9e  jmp     loc_18000DC4C
0x18000dda3  call    cs:__imp_GetLastError
0x18000ddaa  nop     dword ptr [rax+rax+00h]
0x18000ddaf  mov     edi, eax
0x18000ddb1  test    eax, eax
0x18000ddb3  jg      short loc_18000DDD7
0x18000ddb5  test    edi, edi
0x18000ddb7  jns     short loc_18000DD50
0x18000ddb9  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000ddc0  mov     r8d, edi
0x18000ddc3  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000ddca  mov     ecx, r13d; int
0x18000ddcd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ddd2  jmp     loc_18000DCA2
0x18000ddd7  movzx   edi, ax
0x18000ddda  or      edi, 80070000h
0x18000dde0  jmp     short loc_18000DDB5
0x18000dde2  call    cs:__imp_GetLastError
0x18000dde9  nop     dword ptr [rax+rax+00h]
0x18000ddee  mov     edi, eax
0x18000ddf0  test    eax, eax
0x18000ddf2  jle     loc_18000DC22
0x18000ddf8  movzx   edi, ax
0x18000ddfb  or      edi, ebx
0x18000ddfd  jmp     loc_18000DC22
0x18000de02  call    cs:__imp_GetLastError
0x18000de09  nop     dword ptr [rax+rax+00h]
0x18000de0e  mov     edi, eax
0x18000de10  test    eax, eax
0x18000de12  jle     short loc_18000DE1D
0x18000de14  movzx   edi, ax
0x18000de17  or      edi, 80070000h
0x18000de1d  test    edi, edi
0x18000de1f  jns     loc_18000DC9E
0x18000de25  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x18000de2c  jmp     short loc_18000DDC0
0x18000de2e  mov     r8d, eax
0x18000de31  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18000de38  mov     ecx, r13d; int
0x18000de3b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de40  mov     edi, 80070005h
0x18000de45  jmp     loc_18000DD7F
0x18000de4a  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000de51  jmp     loc_18000DD6D
0x18000de56  mov     r8d, edi
0x18000de59  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000de60  jmp     short loc_18000DE78
0x18000de62  mov     r8d, edi
0x18000de65  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x18000de6c  jmp     short loc_18000DE78
0x18000de6e  mov     r8d, eax
0x18000de71  lea     rdx, aRpcgetsessiont_0; "RpcGetSessionType failed: 0x%x in %s"
0x18000de78  lea     r9, aRpcgetcurrents_2; "RpcGetCurrentSessionType"
0x18000de7f  mov     ecx, r13d; int
0x18000de82  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de87  jmp     loc_18000DCD7
```
