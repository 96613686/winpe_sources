# RpcGetCurrentSessionType

- ea: `0x180015750`
- end: `0x180015a1d`
- name: `RpcGetCurrentSessionType`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180014950`
- `0x180014c00`
- `0x180014f40`
- `0x180015750`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001597f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001597f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015999`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800157e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800158ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800157e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800158ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800157ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800158d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800157ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800158d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001586e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001593b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001586e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001593b`
- `RPCRT4!RpcImpersonateClient` at `0x1800157a6`
- `RPCRT4!RpcImpersonateClient` at `0x1800157a6`
- `RPCRT4!RpcRevertToSelf` at `0x1800157f0`
- `RPCRT4!RpcRevertToSelf` at `0x1800157f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015852`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015852`

## string_xrefs

- `0x1800159ea`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180015956`: `OpenThreadToken failed: 0x%x in %s`
- `0x1800159db`: `OpenThreadToken failed: 0x%x in %s`
- `0x18001590f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180015916`: `CRpcUtils::GetClientToken`
- `0x1800159b6`: `GetTokenInformation failed: 0x%x in %s`

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
0x180015750  mov     [rsp-8+arg_10], rbx
0x180015755  mov     [rsp-8+arg_18], rsi
0x18001575a  push    rbp
0x18001575b  push    rdi
0x18001575c  push    r13
0x18001575e  push    r14
0x180015760  push    r15
0x180015762  lea     rbp, [rsp-1B0h]
0x18001576a  sub     rsp, 2B0h
0x180015771  mov     rax, cs:__security_cookie
0x180015778  xor     rax, rsp
0x18001577b  mov     [rbp+1D0h+var_30], rax
0x180015782  mov     r15, rdx
0x180015785  lea     r8, aRpcgetcurrents_2; "RpcGetCurrentSessionType"
0x18001578c  mov     r14, rcx
0x18001578f  xor     edx, edx; int
0x180015791  lea     rcx, [rsp+2D0h+var_280]; this
0x180015796  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18001579b  xor     ecx, ecx; BindingHandle
0x18001579d  mov     [rsp+2D0h+TokenHandle], 0
0x1800157a6  call    cs:__imp_RpcImpersonateClient
0x1800157ac  mov     edi, eax
0x1800157ae  mov     ebx, 80070000h
0x1800157b3  test    eax, eax
0x1800157b5  jle     short loc_1800157BC
0x1800157b7  movzx   edi, ax
0x1800157ba  or      edi, ebx
0x1800157bc  mov     r13d, 8
0x1800157c2  test    edi, edi
0x1800157c4  js      loc_18001590F
0x1800157ca  call    cs:__imp_GetCurrentThread
0x1800157d0  mov     rcx, rax; ThreadHandle
0x1800157d3  lea     r9, [rsp+2D0h+TokenHandle]; TokenHandle
0x1800157d8  lea     edx, [r13+6]; DesiredAccess
0x1800157dc  lea     r8d, [r13-7]; OpenAsSelf
0x1800157e0  call    cs:__imp_OpenThreadToken
0x1800157e6  test    eax, eax
0x1800157e8  jz      loc_18001597F
0x1800157ee  xor     edi, edi
0x1800157f0  call    cs:__imp_RpcRevertToSelf
0x1800157f6  test    eax, eax
0x1800157f8  jg      loc_180015903
0x1800157fe  js      loc_1800159BF
0x180015804  test    edi, edi
0x180015806  js      loc_1800159DB
0x18001580c  mov     rax, [rsp+2D0h+TokenHandle]
0x180015811  mov     rbx, rax
0x180015814  test    edi, edi
0x180015816  js      loc_1800159E7
0x18001581c  xor     esi, esi
0x18001581e  xor     edi, edi
0x180015820  mov     [rsp+2D0h+hObject], rsi
0x180015825  mov     [rsp+2D0h+TokenInformation], esi
0x180015829  mov     dword ptr [rsp+2D0h+TokenHandle], esi
0x18001582d  test    rbx, rbx
0x180015830  jz      loc_1800158D8
0x180015836  mov     rcx, rbx; TokenHandle
0x180015839  mov     r9d, 4; TokenInformationLength
0x18001583f  lea     rax, [rsp+2D0h+TokenHandle]
0x180015844  lea     r8, [rsp+2D0h+TokenInformation]; TokenInformation
0x180015849  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x18001584e  lea     edx, [r9+8]; TokenInformationClass
0x180015852  call    cs:__imp_GetTokenInformation
0x180015858  test    eax, eax
0x18001585a  jz      loc_180015999
0x180015860  mov     esi, [rsp+2D0h+TokenInformation]
0x180015864  mov     rcx, [rsp+2D0h+hObject]; hObject
0x180015869  test    rcx, rcx
0x18001586c  jz      short loc_180015874
0x18001586e  call    cs:__imp_CloseHandle
0x180015874  test    edi, edi
0x180015876  js      loc_1800159F3
0x18001587c  mov     r8, r15
0x18001587f  mov     edx, esi
0x180015881  mov     rcx, r14
0x180015884  call    RpcGetSessionType
0x180015889  mov     edi, eax
0x18001588b  test    eax, eax
0x18001588d  js      loc_1800159FF
0x180015893  lea     rcx, [rsp+2D0h+var_280]; this
0x180015898  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18001589d  test    rbx, rbx
0x1800158a0  jz      short loc_1800158AB
0x1800158a2  mov     rcx, rbx; hObject
0x1800158a5  call    cs:__imp_CloseHandle
0x1800158ab  mov     eax, edi
0x1800158ad  mov     rcx, [rbp+1D0h+var_30]
0x1800158b4  xor     rcx, rsp; StackCookie
0x1800158b7  call    __security_check_cookie
0x1800158bc  lea     r11, [rsp+2D0h+var_20]
0x1800158c4  mov     rbx, [r11+40h]
0x1800158c8  mov     rsi, [r11+48h]
0x1800158cc  mov     rsp, r11
0x1800158cf  pop     r15
0x1800158d1  pop     r14
0x1800158d3  pop     r13
0x1800158d5  pop     rdi
0x1800158d6  pop     rbp
0x1800158d7  retn
0x1800158d8  call    cs:__imp_GetCurrentThread
0x1800158de  lea     r9, [rsp+2D0h+hObject]; TokenHandle
0x1800158e3  mov     r8d, 1; OpenAsSelf
0x1800158e9  mov     rcx, rax; ThreadHandle
0x1800158ec  mov     edx, r13d; DesiredAccess
0x1800158ef  call    cs:__imp_OpenThreadToken
0x1800158f5  test    eax, eax
0x1800158f7  jz      short loc_180015946
0x1800158f9  mov     rcx, [rsp+2D0h+hObject]
0x1800158fe  jmp     loc_180015839
0x180015903  movzx   eax, ax
0x180015906  or      eax, ebx
0x180015908  test    eax, eax
0x18001590a  jmp     loc_1800157FE
0x18001590f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180015916  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18001591d  mov     ecx, r13d; int
0x180015920  mov     r8d, edi
0x180015923  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015928  mov     rax, [rsp+2D0h+TokenHandle]
0x18001592d  test    rax, rax
0x180015930  jz      loc_180015811
0x180015936  xor     ebx, ebx
0x180015938  mov     rcx, rax; hObject
0x18001593b  call    cs:__imp_CloseHandle
0x180015941  jmp     loc_180015814
0x180015946  call    cs:__imp_GetLastError
0x18001594c  mov     edi, eax
0x18001594e  test    eax, eax
0x180015950  jg      short loc_180015974
0x180015952  test    edi, edi
0x180015954  jns     short loc_1800158F9
0x180015956  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18001595d  mov     r8d, edi
0x180015960  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x180015967  mov     ecx, r13d; int
0x18001596a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001596f  jmp     loc_180015864
0x180015974  movzx   edi, ax
0x180015977  or      edi, 80070000h
0x18001597d  jmp     short loc_180015952
0x18001597f  call    cs:__imp_GetLastError
0x180015985  mov     edi, eax
0x180015987  test    eax, eax
0x180015989  jle     loc_1800157F0
0x18001598f  movzx   edi, ax
0x180015992  or      edi, ebx
0x180015994  jmp     loc_1800157F0
0x180015999  call    cs:__imp_GetLastError
0x18001599f  mov     edi, eax
0x1800159a1  test    eax, eax
0x1800159a3  jle     short loc_1800159AE
0x1800159a5  movzx   edi, ax
0x1800159a8  or      edi, 80070000h
0x1800159ae  test    edi, edi
0x1800159b0  jns     loc_180015860
0x1800159b6  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x1800159bd  jmp     short loc_18001595D
0x1800159bf  mov     r8d, eax
0x1800159c2  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x1800159c9  mov     ecx, r13d; int
0x1800159cc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800159d1  mov     edi, 80070005h
0x1800159d6  jmp     loc_180015928
0x1800159db  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x1800159e2  jmp     loc_180015916
0x1800159e7  mov     r8d, edi
0x1800159ea  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x1800159f1  jmp     short loc_180015A09
0x1800159f3  mov     r8d, edi
0x1800159f6  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x1800159fd  jmp     short loc_180015A09
0x1800159ff  mov     r8d, eax
0x180015a02  lea     rdx, aRpcgetsessiont_0; "RpcGetSessionType failed: 0x%x in %s"
0x180015a09  lea     r9, aRpcgetcurrents_2; "RpcGetCurrentSessionType"
0x180015a10  mov     ecx, r13d; int
0x180015a13  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015a18  jmp     loc_180015893
```
