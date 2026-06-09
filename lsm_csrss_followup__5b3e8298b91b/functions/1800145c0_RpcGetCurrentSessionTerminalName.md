# RpcGetCurrentSessionTerminalName

- ea: `0x1800145c0`
- end: `0x180014946`
- name: `RpcGetCurrentSessionTerminalName`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074c0`
- `0x1800145c0`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x180015090`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014655`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800147ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014655`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800147ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001463f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800147e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001463f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800147e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014875`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014875`
- `RPCRT4!RpcImpersonateClient` at `0x18001461b`
- `RPCRT4!RpcImpersonateClient` at `0x18001461b`
- `RPCRT4!RpcRevertToSelf` at `0x180014665`
- `RPCRT4!RpcRevertToSelf` at `0x180014665`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800146c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800146c8`

## string_xrefs

- `0x180014816`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180014894`: `OpenThreadToken failed: 0x%x in %s`
- `0x180014919`: `OpenThreadToken failed: 0x%x in %s`
- `0x180014849`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180014850`: `CRpcUtils::GetClientToken`
- `0x1800148f4`: `GetTokenInformation failed: 0x%x in %s`

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
0x1800145c0  mov     [rsp-8+arg_0], rbx
0x1800145c5  mov     [rsp-8+arg_10], rsi
0x1800145ca  push    rbp
0x1800145cb  push    rdi
0x1800145cc  push    r13
0x1800145ce  push    r14
0x1800145d0  push    r15
0x1800145d2  lea     rbp, [rsp-1C0h]
0x1800145da  sub     rsp, 2C0h
0x1800145e1  mov     rax, cs:__security_cookie
0x1800145e8  xor     rax, rsp
0x1800145eb  mov     [rbp+1E0h+var_30], rax
0x1800145f2  mov     r15, rdx
0x1800145f5  xor     edi, edi
0x1800145f7  mov     [rsp+2E0h+var_290], rdi
0x1800145fc  mov     [rsp+2E0h+var_298], rdi
0x180014601  lea     r8, aRpcgetcurrents; "RpcGetCurrentSessionTerminalName"
0x180014608  xor     edx, edx; int
0x18001460a  lea     rcx, [rsp+2E0h+var_280]; this
0x18001460f  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180014614  mov     [rsp+2E0h+TokenHandle], rdi
0x180014619  xor     ecx, ecx; BindingHandle
0x18001461b  call    cs:__imp_RpcImpersonateClient
0x180014621  mov     esi, eax
0x180014623  mov     ebx, 80070000h
0x180014628  test    eax, eax
0x18001462a  jle     short loc_180014631
0x18001462c  movzx   esi, ax
0x18001462f  or      esi, ebx
0x180014631  mov     r13d, 8
0x180014637  test    esi, esi
0x180014639  js      loc_180014849
0x18001463f  call    cs:__imp_GetCurrentThread
0x180014645  mov     rcx, rax; ThreadHandle
0x180014648  lea     r9, [rsp+2E0h+TokenHandle]; TokenHandle
0x18001464d  lea     edx, [r13+6]; DesiredAccess
0x180014651  lea     r8d, [r13-7]; OpenAsSelf
0x180014655  call    cs:__imp_OpenThreadToken
0x18001465b  test    eax, eax
0x18001465d  jz      loc_1800148BD
0x180014663  xor     esi, esi
0x180014665  call    cs:__imp_RpcRevertToSelf
0x18001466b  test    eax, eax
0x18001466d  jg      loc_18001483D
0x180014673  js      loc_1800148FD
0x180014679  test    esi, esi
0x18001467b  js      loc_180014919
0x180014681  mov     rax, [rsp+2E0h+TokenHandle]
0x180014686  mov     rbx, rax
0x180014689  test    esi, esi
0x18001468b  js      loc_180014813
0x180014691  xor     r14d, r14d
0x180014694  mov     [rsp+2E0h+hObject], rdi
0x180014699  mov     [rsp+2E0h+TokenInformation], edi
0x18001469d  mov     dword ptr [rsp+2E0h+TokenHandle], edi
0x1800146a1  xor     esi, esi
0x1800146a3  test    rbx, rbx
0x1800146a6  jz      loc_1800147E8
0x1800146ac  mov     rcx, rbx; TokenHandle
0x1800146af  lea     rax, [rsp+2E0h+TokenHandle]
0x1800146b4  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x1800146b9  mov     r9d, 4; TokenInformationLength
0x1800146bf  lea     r8, [rsp+2E0h+TokenInformation]; TokenInformation
0x1800146c4  lea     edx, [r9+8]; TokenInformationClass
0x1800146c8  call    cs:__imp_GetTokenInformation
0x1800146ce  test    eax, eax
0x1800146d0  jz      loc_1800148D7
0x1800146d6  mov     r14d, [rsp+2E0h+TokenInformation]
0x1800146db  mov     rcx, [rsp+2E0h+hObject]; hObject
0x1800146e0  test    rcx, rcx
0x1800146e3  jz      short loc_1800146EB
0x1800146e5  call    cs:__imp_CloseHandle
0x1800146eb  test    esi, esi
0x1800146ed  js      loc_180014831
0x1800146f3  mov     [rsp+2E0h+hObject], rdi
0x1800146f8  lea     rcx, [rsp+2E0h+hObject]; struct ISessionManagerInternal **
0x1800146fd  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180014702  mov     rdi, [rsp+2E0h+hObject]
0x180014707  mov     rax, [rdi]
0x18001470a  lea     rdx, [rsp+2E0h+var_290]
0x18001470f  mov     rcx, rdi
0x180014712  mov     rax, [rax+18h]
0x180014716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471b  mov     esi, eax
0x18001471d  test    eax, eax
0x18001471f  js      loc_180014925
0x180014725  mov     rcx, [rsp+2E0h+var_290]
0x18001472a  mov     rax, [rcx]
0x18001472d  lea     r8, [rsp+2E0h+var_298]
0x180014732  mov     edx, r14d
0x180014735  mov     rax, [rax+18h]
0x180014739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001473e  mov     esi, eax
0x180014740  test    eax, eax
0x180014742  js      loc_18001492E
0x180014748  mov     rdx, r15
0x18001474b  mov     rcx, [rsp+2E0h+var_298]
0x180014750  call    RpcGetTerminalName
0x180014755  mov     esi, eax
0x180014757  test    eax, eax
0x180014759  js      loc_180014937
0x18001475f  lea     rcx, [rsp+2E0h+var_280]; this
0x180014764  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180014769  nop
0x18001476a  mov     rcx, [rsp+2E0h+var_298]
0x18001476f  test    rcx, rcx
0x180014772  jz      short loc_180014781
0x180014774  mov     rax, [rcx]
0x180014777  mov     rax, [rax+10h]
0x18001477b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014780  nop
0x180014781  mov     rcx, [rsp+2E0h+var_290]
0x180014786  test    rcx, rcx
0x180014789  jz      short loc_180014798
0x18001478b  mov     rax, [rcx]
0x18001478e  mov     rax, [rax+10h]
0x180014792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014797  nop
0x180014798  test    rdi, rdi
0x18001479b  jz      short loc_1800147AD
0x18001479d  mov     rax, [rdi]
0x1800147a0  mov     rcx, rdi
0x1800147a3  mov     rax, [rax+10h]
0x1800147a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ac  nop
0x1800147ad  test    rbx, rbx
0x1800147b0  jz      short loc_1800147BB
0x1800147b2  mov     rcx, rbx; hObject
0x1800147b5  call    cs:__imp_CloseHandle
0x1800147bb  mov     eax, esi
0x1800147bd  mov     rcx, [rbp+1E0h+var_30]
0x1800147c4  xor     rcx, rsp; StackCookie
0x1800147c7  call    __security_check_cookie
0x1800147cc  lea     r11, [rsp+2E0h+var_20]
0x1800147d4  mov     rbx, [r11+30h]
0x1800147d8  mov     rsi, [r11+40h]
0x1800147dc  mov     rsp, r11
0x1800147df  pop     r15
0x1800147e1  pop     r14
0x1800147e3  pop     r13
0x1800147e5  pop     rdi
0x1800147e6  pop     rbp
0x1800147e7  retn
0x1800147e8  call    cs:__imp_GetCurrentThread
0x1800147ee  lea     r9, [rsp+2E0h+hObject]; TokenHandle
0x1800147f3  mov     r8d, 1; OpenAsSelf
0x1800147f9  mov     edx, r13d; DesiredAccess
0x1800147fc  mov     rcx, rax; ThreadHandle
0x1800147ff  call    cs:__imp_OpenThreadToken
0x180014805  test    eax, eax
0x180014807  jz      short loc_180014880
0x180014809  mov     rcx, [rsp+2E0h+hObject]
0x18001480e  jmp     loc_1800146AF
0x180014813  mov     r8d, esi
0x180014816  lea     rdx, aCrpcutilsGetcl_3; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18001481d  lea     r9, aRpcgetcurrents; "RpcGetCurrentSessionTerminalName"
0x180014824  mov     ecx, r13d; int
0x180014827  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001482c  jmp     loc_18001475F
0x180014831  mov     r8d, esi
0x180014834  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x18001483b  jmp     short loc_18001481D
0x18001483d  movzx   eax, ax
0x180014840  or      eax, ebx
0x180014842  test    eax, eax
0x180014844  jmp     loc_180014673
0x180014849  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180014850  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x180014857  mov     ecx, r13d; int
0x18001485a  mov     r8d, esi
0x18001485d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014862  mov     rax, [rsp+2E0h+TokenHandle]
0x180014867  test    rax, rax
0x18001486a  jz      loc_180014686
0x180014870  xor     ebx, ebx
0x180014872  mov     rcx, rax; hObject
0x180014875  call    cs:__imp_CloseHandle
0x18001487b  jmp     loc_180014689
0x180014880  call    cs:__imp_GetLastError
0x180014886  mov     esi, eax
0x180014888  test    eax, eax
0x18001488a  jg      short loc_1800148B2
0x18001488c  test    esi, esi
0x18001488e  jns     loc_180014809
0x180014894  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18001489b  mov     r8d, esi
0x18001489e  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x1800148a5  mov     ecx, r13d; int
0x1800148a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800148ad  jmp     loc_1800146DB
0x1800148b2  movzx   esi, ax
0x1800148b5  or      esi, 80070000h
0x1800148bb  jmp     short loc_18001488C
0x1800148bd  call    cs:__imp_GetLastError
0x1800148c3  mov     esi, eax
0x1800148c5  test    eax, eax
0x1800148c7  jle     loc_180014665
0x1800148cd  movzx   esi, ax
0x1800148d0  or      esi, ebx
0x1800148d2  jmp     loc_180014665
0x1800148d7  call    cs:__imp_GetLastError
0x1800148dd  mov     esi, eax
0x1800148df  test    eax, eax
0x1800148e1  jle     short loc_1800148EC
0x1800148e3  movzx   esi, ax
0x1800148e6  or      esi, 80070000h
0x1800148ec  test    esi, esi
0x1800148ee  jns     loc_1800146D6
0x1800148f4  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x1800148fb  jmp     short loc_18001489B
0x1800148fd  mov     r8d, eax
0x180014900  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x180014907  mov     ecx, r13d; int
0x18001490a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001490f  mov     esi, 80070005h
0x180014914  jmp     loc_180014862
0x180014919  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180014920  jmp     loc_180014850
0x180014925  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18001492c  jmp     short loc_18001493E
0x18001492e  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x180014935  jmp     short loc_18001493E
0x180014937  lea     rdx, aRpcgetterminal; "RpcGetTerminalName failed: 0x%x in %s"
0x18001493e  mov     r8d, eax
0x180014941  jmp     loc_18001481D
```
