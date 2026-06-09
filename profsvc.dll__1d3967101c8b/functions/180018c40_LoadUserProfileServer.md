# LoadUserProfileServer

- ea: `0x180018c40`
- end: `0x180019041`
- name: `LoadUserProfileServer`
- size: `1025`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a9b8`
- `0x180018bcc`
- `0x180018c40`
- `0x180019048`
- `0x1800190f4`
- `0x180019460`
- `0x180019630`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003ab00`
- `0x18003ac70`
- `0x18003b310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018d35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018d35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018fa1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018fdd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180019019`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018fa1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018fdd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180019019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001902b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001902b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018c96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018c96`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018fbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018ffa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019036`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018fbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018ffa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019036`
- `RPCRT4!RpcRevertToSelf` at `0x180018d47`
- `RPCRT4!RpcRevertToSelf` at `0x180018db0`
- `RPCRT4!RpcRevertToSelf` at `0x180018e81`
- `RPCRT4!RpcRevertToSelf` at `0x180018eef`
- `RPCRT4!RpcRevertToSelf` at `0x180018d47`
- `RPCRT4!RpcRevertToSelf` at `0x180018db0`
- `RPCRT4!RpcRevertToSelf` at `0x180018e81`
- `RPCRT4!RpcRevertToSelf` at `0x180018eef`
- `RPCRT4!RpcImpersonateClient` at `0x180018d01`
- `RPCRT4!RpcImpersonateClient` at `0x180018d01`

## string_xrefs

- `0x180018d6e`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180018e2d`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180018f11`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180018f63`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall LoadUserProfileServer(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // edi
  RPC_STATUS v5; // eax
  unsigned int v6; // esi
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  CUserProfile *v9; // rax
  CUserProfile *v10; // rdi
  CUserProfile *v12; // rax
  CUserProfile *v13; // rdi
  int v14; // eax
  unsigned int LastError; // ebx
  HANDLE v16; // rdi
  HANDLE v17; // rbx
  HANDLE v18; // rbx
  int pdwType; // [rsp+20h] [rbp-60h]
  int pdwTypea; // [rsp+20h] [rbp-60h]
  int pvData; // [rsp+40h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-38h] BYREF
  int v23; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-28h]
  __int64 v25; // [rsp+60h] [rbp-20h]
  int v26; // [rsp+68h] [rbp-18h]
  __int128 v27; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD v29; // [rsp+B0h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+38h] BYREF

  pcbData = 4;
  v29 = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\Setup",
         L"SystemSetupInProgress",
         0x10000012u,
         &v29,
         &pvData,
         &pcbData) )
  {
    goto LABEL_4;
  }
  if ( v29 != 4 )
  {
    if ( pcbData != 4 || (_WORD)pvData != 49 )
      goto LABEL_4;
    return 2147942421LL;
  }
  if ( pvData == 1 )
    return 2147942421LL;
LABEL_4:
  if ( !a2 )
    return 2147942487LL;
  v3 = *(_QWORD *)(a2 + 8);
  if ( !v3 || !*(_QWORD *)(v3 + 8) )
    return 2147942487LL;
  v4 = 0;
  v23 = 0;
  v27 = 0;
  Token = 0;
  v25 = 0;
  v26 = 0;
  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)v6,
        pdwType);
      CThreadContext::~CThreadContext((CThreadContext *)&v23);
      return v6;
    }
  }
  else
  {
    v4 = 1;
    HIDWORD(v25) = 1;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xB2,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                  v8);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    CThreadContext::~CThreadContext((CThreadContext *)&v23);
    return LastError;
  }
  if ( v4 )
  {
    RpcRevertToSelf();
    HIDWORD(v25) = 0;
  }
  v9 = (CUserProfile *)operator new(0x130u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 && (memset_0(v9, 0, 0x130u), v12 = CUserProfile::CUserProfile(v10), (v13 = v12) != 0) )
  {
    v14 = CUserProfile::Load(v12, *(void **)a2, TokenHandle, *(struct _PROFILEINFOW **)(a2 + 8), 0xFFFFFFFF, 0);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)(unsigned int)v14,
        pdwTypea);
      CUserProfile::~CUserProfile(v13);
      operator delete(v13, 0x130u);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      CThreadContext::RevertPrivileges((CThreadContext *)&v23);
      if ( v23 )
      {
        v16 = Token;
        SetThreadToken(0, Token);
        if ( v16 )
          CloseHandle(v16);
      }
      if ( HIDWORD(v25) )
        RpcRevertToSelf();
      if ( (_DWORD)v25 )
        RevertToSelf();
      return LastError;
    }
    CUserProfile::~CUserProfile(v13);
    operator delete(v13, 0x130u);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    CThreadContext::RevertPrivileges((CThreadContext *)&v23);
    if ( v23 )
    {
      v17 = Token;
      SetThreadToken(0, Token);
      if ( v17 )
        CloseHandle(v17);
    }
    if ( HIDWORD(v25) )
      RpcRevertToSelf();
    if ( (_DWORD)v25 )
      RevertToSelf();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    CThreadContext::RevertPrivileges((CThreadContext *)&v23);
    if ( v23 )
    {
      v18 = Token;
      SetThreadToken(0, Token);
      if ( v18 )
        CloseHandle(v18);
    }
    if ( HIDWORD(v25) )
      RpcRevertToSelf();
    if ( (_DWORD)v25 )
      RevertToSelf();
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180018c40  push    rbp
0x180018c42  push    rbx
0x180018c43  push    r14
0x180018c45  mov     rbp, rsp
0x180018c48  sub     rsp, 80h
0x180018c4f  lea     rax, [rbp+arg_18]
0x180018c53  mov     [rbp+arg_18], 4
0x180018c5a  mov     [rsp+80h+pcbData], rax; pcbData
0x180018c5f  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x180018c66  lea     rax, [rbp+var_40]
0x180018c6a  mov     rbx, rdx
0x180018c6d  mov     [rsp+80h+pvData], rax; pvData
0x180018c72  lea     rdx, aSystemSetup; "System\\Setup"
0x180018c79  lea     rax, [rbp+arg_10]
0x180018c7d  xor     r14d, r14d
0x180018c80  mov     r9d, 10000012h; dwFlags
0x180018c86  mov     [rsp+80h+pdwType], rax; int
0x180018c8b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180018c92  mov     [rbp+arg_10], r14d
0x180018c96  call    cs:__imp_RegGetValueW
0x180018c9c  test    eax, eax
0x180018c9e  jnz     short loc_180018CB4
0x180018ca0  cmp     [rbp+arg_10], 4
0x180018ca4  jnz     loc_180018F35
0x180018caa  cmp     [rbp+var_40], 1
0x180018cae  jz      loc_180018F4A
0x180018cb4  test    rbx, rbx
0x180018cb7  jz      loc_180018DCA
0x180018cbd  mov     rax, [rbx+8]
0x180018cc1  test    rax, rax
0x180018cc4  jz      loc_180018DCA
0x180018cca  cmp     [rax+8], r14
0x180018cce  jz      loc_180018DCA
0x180018cd4  xorps   xmm0, xmm0
0x180018cd7  mov     [rsp+80h+arg_0], rsi
0x180018cdf  mov     [rsp+80h+arg_8], rdi
0x180018ce7  xor     ecx, ecx; BindingHandle
0x180018ce9  mov     edi, r14d
0x180018cec  mov     [rbp+var_30], r14d
0x180018cf0  movdqu  [rbp+var_10], xmm0
0x180018cf5  mov     [rbp+Token], r14
0x180018cf9  mov     [rbp+var_20], r14
0x180018cfd  mov     [rbp+var_18], r14d
0x180018d01  call    cs:__imp_RpcImpersonateClient
0x180018d07  mov     esi, eax
0x180018d09  test    eax, eax
0x180018d0b  jnz     loc_180018F03
0x180018d11  mov     edi, 1
0x180018d16  mov     dword ptr [rbp+var_20+4], edi
0x180018d19  mov     [rbp+TokenHandle], r14
0x180018d1d  call    cs:__imp_GetCurrentThread
0x180018d23  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180018d27  mov     edx, 0F01FFh; DesiredAccess
0x180018d2c  mov     rcx, rax; ThreadHandle
0x180018d2f  mov     r8d, 1; OpenAsSelf
0x180018d35  call    cs:__imp_OpenThreadToken
0x180018d3b  test    eax, eax
0x180018d3d  jz      loc_180018F5F
0x180018d43  test    edi, edi
0x180018d45  jz      short loc_180018D51
0x180018d47  call    cs:__imp_RpcRevertToSelf
0x180018d4d  mov     dword ptr [rbp+var_20+4], r14d
0x180018d51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018d58  mov     ecx, 130h; unsigned __int64
0x180018d5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018d62  mov     rdi, rax
0x180018d65  test    rax, rax
0x180018d68  jnz     short loc_180018DDB
0x180018d6a  mov     rcx, [rbp+18h]; this
0x180018d6e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018d75  mov     r9d, 8007000Eh; char *
0x180018d7b  mov     edx, 0B8h; void *
0x180018d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d85  mov     rcx, [rbp+TokenHandle]; hObject
0x180018d89  lea     rax, [rcx-1]
0x180018d8d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018d91  jbe     loc_180019005
0x180018d97  lea     rcx, [rbp+var_30]; this
0x180018d9b  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180018da0  cmp     [rbp+var_30], r14d
0x180018da4  jnz     loc_180019010
0x180018daa  cmp     dword ptr [rbp+var_20+4], r14d
0x180018dae  jz      short loc_180018DB6
0x180018db0  call    cs:__imp_RpcRevertToSelf
0x180018db6  cmp     dword ptr [rbp+var_20], r14d
0x180018dba  jnz     loc_180019036
0x180018dc0  mov     eax, 8007000Eh
0x180018dc5  jmp     loc_180018E93
0x180018dca  mov     eax, 80070057h
0x180018dcf  add     rsp, 80h
0x180018dd6  pop     r14
0x180018dd8  pop     rbx
0x180018dd9  pop     rbp
0x180018dda  retn
0x180018ddb  xor     edx, edx; Val
0x180018ddd  mov     r8d, 130h; Size
0x180018de3  mov     rcx, rdi; void *
0x180018de6  call    memset_0
0x180018deb  mov     rcx, rdi; this
0x180018dee  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x180018df3  mov     rdi, rax
0x180018df6  test    rax, rax
0x180018df9  jz      loc_180018D6A
0x180018dff  mov     r9, [rbx+8]; struct _PROFILEINFOW *
0x180018e03  mov     rcx, rax; this
0x180018e06  mov     r8, [rbp+TokenHandle]; void *
0x180018e0a  mov     rdx, [rbx]; void *
0x180018e0d  mov     [rsp+80h+pvData], r14; unsigned __int16 *
0x180018e12  mov     dword ptr [rsp+80h+pdwType], 0FFFFFFFFh; int
0x180018e1a  call    ?Load@CUserProfile@@QEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Load(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x180018e1f  mov     ebx, eax
0x180018e21  test    eax, eax
0x180018e23  jns     loc_180018EAF
0x180018e29  mov     rcx, [rbp+18h]; this
0x180018e2d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018e34  mov     r9d, eax; char *
0x180018e37  mov     edx, 0C0h; void *
0x180018e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e41  mov     rcx, rdi; this
0x180018e44  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180018e49  mov     edx, 130h; unsigned __int64
0x180018e4e  mov     rcx, rdi; void *
0x180018e51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018e56  mov     rcx, [rbp+TokenHandle]; hObject
0x180018e5a  lea     rax, [rcx-1]
0x180018e5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018e62  jbe     loc_180018F8D
0x180018e68  lea     rcx, [rbp+var_30]; this
0x180018e6c  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180018e71  cmp     [rbp+var_30], r14d
0x180018e75  jnz     loc_180018F98
0x180018e7b  cmp     dword ptr [rbp+var_20+4], r14d
0x180018e7f  jz      short loc_180018E87
0x180018e81  call    cs:__imp_RpcRevertToSelf
0x180018e87  cmp     dword ptr [rbp+var_20], r14d
0x180018e8b  jnz     loc_180018FBE
0x180018e91  mov     eax, ebx
0x180018e93  mov     rsi, [rsp+80h+arg_0]
0x180018e9b  mov     rdi, [rsp+80h+arg_8]
0x180018ea3  add     rsp, 80h
0x180018eaa  pop     r14
0x180018eac  pop     rbx
0x180018ead  pop     rbp
0x180018eae  retn
0x180018eaf  mov     rcx, rdi; this
0x180018eb2  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180018eb7  mov     edx, 130h; unsigned __int64
0x180018ebc  mov     rcx, rdi; void *
0x180018ebf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018ec4  mov     rcx, [rbp+TokenHandle]; hObject
0x180018ec8  lea     rax, [rcx-1]
0x180018ecc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018ed0  jbe     loc_180018FC9
0x180018ed6  lea     rcx, [rbp+var_30]; this
0x180018eda  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180018edf  cmp     [rbp+var_30], r14d
0x180018ee3  jnz     loc_180018FD4
0x180018ee9  cmp     dword ptr [rbp+var_20+4], r14d
0x180018eed  jz      short loc_180018EF5
0x180018eef  call    cs:__imp_RpcRevertToSelf
0x180018ef5  cmp     dword ptr [rbp+var_20], r14d
0x180018ef9  jnz     loc_180018FFA
0x180018eff  xor     eax, eax
0x180018f01  jmp     short loc_180018E93
0x180018f03  jg      short loc_180018F54
0x180018f05  test    esi, esi
0x180018f07  jns     loc_180018D19
0x180018f0d  mov     rcx, [rbp+18h]; this
0x180018f11  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018f18  mov     r9d, esi; char *
0x180018f1b  mov     edx, 0ABh; void *
0x180018f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f25  lea     rcx, [rbp+var_30]; this
0x180018f29  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018f2e  mov     eax, esi
0x180018f30  jmp     loc_180018E93
0x180018f35  cmp     [rbp+arg_18], 4
0x180018f39  jnz     loc_180018CB4
0x180018f3f  cmp     word ptr [rbp+var_40], 31h ; '1'
0x180018f44  jnz     loc_180018CB4
0x180018f4a  mov     eax, 80070015h
0x180018f4f  jmp     loc_180018EA3
0x180018f54  movzx   esi, ax
0x180018f57  or      esi, 80070000h
0x180018f5d  jmp     short loc_180018F05
0x180018f5f  mov     rcx, [rbp+18h]; this
0x180018f63  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018f6a  mov     edx, 0B2h; void *
0x180018f6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018f74  lea     rcx, [rbp+TokenHandle]
0x180018f78  mov     ebx, eax
0x180018f7a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018f7f  lea     rcx, [rbp+var_30]; this
0x180018f83  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018f88  jmp     loc_180018E91
0x180018f8d  call    cs:__imp_CloseHandle
0x180018f93  jmp     loc_180018E68
0x180018f98  mov     rdi, [rbp+Token]
0x180018f9c  xor     ecx, ecx; Thread
0x180018f9e  mov     rdx, rdi; Token
0x180018fa1  call    cs:__imp_SetThreadToken
0x180018fa7  test    rdi, rdi
0x180018faa  jz      loc_180018E7B
0x180018fb0  mov     rcx, rdi; hObject
0x180018fb3  call    cs:__imp_CloseHandle
0x180018fb9  jmp     loc_180018E7B
0x180018fbe  call    cs:__imp_RevertToSelf
0x180018fc4  jmp     loc_180018E91
0x180018fc9  call    cs:__imp_CloseHandle
0x180018fcf  jmp     loc_180018ED6
0x180018fd4  mov     rbx, [rbp+Token]
0x180018fd8  xor     ecx, ecx; Thread
0x180018fda  mov     rdx, rbx; Token
0x180018fdd  call    cs:__imp_SetThreadToken
0x180018fe3  test    rbx, rbx
0x180018fe6  jz      loc_180018EE9
0x180018fec  mov     rcx, rbx; hObject
0x180018fef  call    cs:__imp_CloseHandle
0x180018ff5  jmp     loc_180018EE9
0x180018ffa  call    cs:__imp_RevertToSelf
0x180019000  jmp     loc_180018EFF
0x180019005  call    cs:__imp_CloseHandle
0x18001900b  jmp     loc_180018D97
0x180019010  mov     rbx, [rbp+Token]
0x180019014  xor     ecx, ecx; Thread
0x180019016  mov     rdx, rbx; Token
0x180019019  call    cs:__imp_SetThreadToken
0x18001901f  test    rbx, rbx
0x180019022  jz      loc_180018DAA
0x180019028  mov     rcx, rbx; hObject
0x18001902b  call    cs:__imp_CloseHandle
0x180019031  jmp     loc_180018DAA
0x180019036  call    cs:__imp_RevertToSelf
0x18001903c  jmp     loc_180018DC0
```
