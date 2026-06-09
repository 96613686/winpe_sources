# LoadUserProfileServer

- ea: `0x18001ba30`
- end: `0x18001bdd2`
- name: `LoadUserProfileServer`
- size: `930`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800084bc`
- `0x18001ba30`
- `0x18001bdd8`
- `0x18001c130`
- `0x18001c358`
- `0x18001c3e4`
- `0x18001c4a0`
- `0x18002df48`
- `0x180030ad0`
- `0x18003c040`
- `0x18003c1b0`
- `0x18003c870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bb37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bb37`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001bd76`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001bd76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bb19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bb19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ba86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ba86`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bd9f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bd9f`
- `RPCRT4!RpcRevertToSelf` at `0x18001bb4f`
- `RPCRT4!RpcRevertToSelf` at `0x18001bc6c`
- `RPCRT4!RpcRevertToSelf` at `0x18001bb4f`
- `RPCRT4!RpcRevertToSelf` at `0x18001bc6c`
- `RPCRT4!RpcImpersonateClient` at `0x18001baf7`
- `RPCRT4!RpcImpersonateClient` at `0x18001baf7`

## string_xrefs

- `0x18001bb7c`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001bc18`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001bce3`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001bd32`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

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
  int pdwType; // [rsp+20h] [rbp-60h]
  int pdwTypea; // [rsp+20h] [rbp-60h]
  int pvData; // [rsp+40h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-38h] BYREF
  int v21; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-28h]
  __int64 v23; // [rsp+60h] [rbp-20h]
  int v24; // [rsp+68h] [rbp-18h]
  __int128 v25; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD v27; // [rsp+B0h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+38h] BYREF

  pcbData = 4;
  v27 = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\Setup",
         L"SystemSetupInProgress",
         0x10000012u,
         &v27,
         &pvData,
         &pcbData) )
  {
    goto LABEL_4;
  }
  if ( v27 != 4 )
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
  v21 = 0;
  v25 = 0;
  Token = 0;
  v23 = 0;
  v24 = 0;
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
      CThreadContext::~CThreadContext((CThreadContext *)&v21);
      return v6;
    }
  }
  else
  {
    v4 = 1;
    HIDWORD(v23) = 1;
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
    CThreadContext::~CThreadContext((CThreadContext *)&v21);
    return LastError;
  }
  if ( v4 )
  {
    RpcRevertToSelf();
    HIDWORD(v23) = 0;
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
      CThreadContext::RevertPrivileges((CThreadContext *)&v21);
      if ( v21 )
      {
        v16 = Token;
        SetThreadToken(0, Token);
        if ( v16 )
          CloseHandle(v16);
      }
      if ( HIDWORD(v23) )
        RpcRevertToSelf();
      if ( (_DWORD)v23 )
        RevertToSelf();
      return LastError;
    }
    CUserProfile::~CUserProfile(v13);
    operator delete(v13, 0x130u);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    CThreadContext::~CThreadContext((CThreadContext *)&v21);
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
    CThreadContext::~CThreadContext((CThreadContext *)&v21);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001ba30  push    rbp
0x18001ba32  push    rbx
0x18001ba33  push    r14
0x18001ba35  mov     rbp, rsp
0x18001ba38  sub     rsp, 80h
0x18001ba3f  lea     rax, [rbp+arg_18]
0x18001ba43  mov     [rbp+arg_18], 4
0x18001ba4a  mov     [rsp+80h+pcbData], rax; pcbData
0x18001ba4f  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x18001ba56  lea     rax, [rbp+var_40]
0x18001ba5a  mov     rbx, rdx
0x18001ba5d  mov     [rsp+80h+pvData], rax; pvData
0x18001ba62  lea     rdx, aSystemSetup; "System\\Setup"
0x18001ba69  lea     rax, [rbp+arg_10]
0x18001ba6d  xor     r14d, r14d
0x18001ba70  mov     r9d, 10000012h; dwFlags
0x18001ba76  mov     [rsp+80h+pdwType], rax; int
0x18001ba7b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ba82  mov     [rbp+arg_10], r14d
0x18001ba86  call    cs:__imp_RegGetValueW
0x18001ba8d  nop     dword ptr [rax+rax+00h]
0x18001ba92  test    eax, eax
0x18001ba94  jnz     short loc_18001BAAA
0x18001ba96  cmp     [rbp+arg_10], 4
0x18001ba9a  jnz     loc_18001BD04
0x18001baa0  cmp     [rbp+var_40], 1
0x18001baa4  jz      loc_18001BD19
0x18001baaa  test    rbx, rbx
0x18001baad  jz      loc_18001BBB8
0x18001bab3  mov     rax, [rbx+8]
0x18001bab7  test    rax, rax
0x18001baba  jz      loc_18001BBB8
0x18001bac0  cmp     [rax+8], r14
0x18001bac4  jz      loc_18001BBB8
0x18001baca  xorps   xmm0, xmm0
0x18001bacd  mov     [rsp+80h+arg_0], rsi
0x18001bad5  mov     [rsp+80h+arg_8], rdi
0x18001badd  xor     ecx, ecx; BindingHandle
0x18001badf  mov     edi, r14d
0x18001bae2  mov     [rbp+var_30], r14d
0x18001bae6  movdqu  [rbp+var_10], xmm0
0x18001baeb  mov     [rbp+Token], r14
0x18001baef  mov     [rbp+var_20], r14
0x18001baf3  mov     [rbp+var_18], r14d
0x18001baf7  call    cs:__imp_RpcImpersonateClient
0x18001bafe  nop     dword ptr [rax+rax+00h]
0x18001bb03  mov     esi, eax
0x18001bb05  test    eax, eax
0x18001bb07  jnz     loc_18001BCD5
0x18001bb0d  mov     edi, 1
0x18001bb12  mov     dword ptr [rbp+var_20+4], edi
0x18001bb15  mov     [rbp+TokenHandle], r14
0x18001bb19  call    cs:__imp_GetCurrentThread
0x18001bb20  nop     dword ptr [rax+rax+00h]
0x18001bb25  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001bb29  mov     edx, 0F01FFh; DesiredAccess
0x18001bb2e  mov     rcx, rax; ThreadHandle
0x18001bb31  mov     r8d, 1; OpenAsSelf
0x18001bb37  call    cs:__imp_OpenThreadToken
0x18001bb3e  nop     dword ptr [rax+rax+00h]
0x18001bb43  test    eax, eax
0x18001bb45  jz      loc_18001BD2E
0x18001bb4b  test    edi, edi
0x18001bb4d  jz      short loc_18001BB5F
0x18001bb4f  call    cs:__imp_RpcRevertToSelf
0x18001bb56  nop     dword ptr [rax+rax+00h]
0x18001bb5b  mov     dword ptr [rbp+var_20+4], r14d
0x18001bb5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bb66  mov     ecx, 130h; unsigned __int64
0x18001bb6b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bb70  mov     rdi, rax
0x18001bb73  test    rax, rax
0x18001bb76  jnz     short loc_18001BBCA
0x18001bb78  mov     rcx, [rbp+18h]; this
0x18001bb7c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001bb83  mov     r9d, 8007000Eh; char *
0x18001bb89  mov     edx, 0B8h; void *
0x18001bb8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb93  mov     rcx, [rbp+TokenHandle]; hObject
0x18001bb97  lea     rdx, [rcx-1]
0x18001bb9b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001bb9f  jbe     loc_18001BDC1
0x18001bba5  lea     rcx, [rbp+var_30]; this
0x18001bba9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001bbae  mov     eax, 8007000Eh
0x18001bbb3  jmp     loc_18001BC84
0x18001bbb8  mov     eax, 80070057h
0x18001bbbd  add     rsp, 80h
0x18001bbc4  pop     r14
0x18001bbc6  pop     rbx
0x18001bbc7  pop     rbp
0x18001bbc8  retn
0x18001bbca  xor     edx, edx; Val
0x18001bbcc  mov     r8d, 130h; Size
0x18001bbd2  mov     rcx, rdi; void *
0x18001bbd5  call    memset_0
0x18001bbda  mov     rcx, rdi; this
0x18001bbdd  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x18001bbe2  mov     rdi, rax
0x18001bbe5  test    rax, rax
0x18001bbe8  jz      short loc_18001BB78
0x18001bbea  mov     r9, [rbx+8]; struct _PROFILEINFOW *
0x18001bbee  mov     rcx, rax; this
0x18001bbf1  mov     r8, [rbp+TokenHandle]; void *
0x18001bbf5  mov     rdx, [rbx]; void *
0x18001bbf8  mov     [rsp+80h+pvData], r14; unsigned __int16 *
0x18001bbfd  mov     dword ptr [rsp+80h+pdwType], 0FFFFFFFFh; int
0x18001bc05  call    ?Load@CUserProfile@@QEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Load(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x18001bc0a  mov     ebx, eax
0x18001bc0c  test    eax, eax
0x18001bc0e  jns     loc_18001BCA1
0x18001bc14  mov     rcx, [rbp+18h]; this
0x18001bc18  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001bc1f  mov     r9d, eax; char *
0x18001bc22  mov     edx, 0C0h; void *
0x18001bc27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc2c  mov     rcx, rdi; this
0x18001bc2f  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001bc34  mov     edx, 130h; unsigned __int64
0x18001bc39  mov     rcx, rdi; void *
0x18001bc3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bc41  mov     rcx, [rbp+TokenHandle]; hObject
0x18001bc45  lea     rax, [rcx-1]
0x18001bc49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bc4d  jbe     loc_18001BD5C
0x18001bc53  lea     rcx, [rbp+var_30]; this
0x18001bc57  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18001bc5c  cmp     [rbp+var_30], r14d
0x18001bc60  jnz     loc_18001BD6D
0x18001bc66  cmp     dword ptr [rbp+var_20+4], r14d
0x18001bc6a  jz      short loc_18001BC78
0x18001bc6c  call    cs:__imp_RpcRevertToSelf
0x18001bc73  nop     dword ptr [rax+rax+00h]
0x18001bc78  cmp     dword ptr [rbp+var_20], r14d
0x18001bc7c  jnz     loc_18001BD9F
0x18001bc82  mov     eax, ebx
0x18001bc84  mov     rsi, [rsp+80h+arg_0]
0x18001bc8c  mov     rdi, [rsp+80h+arg_8]
0x18001bc94  add     rsp, 80h
0x18001bc9b  pop     r14
0x18001bc9d  pop     rbx
0x18001bc9e  pop     rbp
0x18001bc9f  retn
0x18001bca1  mov     rcx, rdi; this
0x18001bca4  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001bca9  mov     edx, 130h; unsigned __int64
0x18001bcae  mov     rcx, rdi; void *
0x18001bcb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bcb6  mov     rcx, [rbp+TokenHandle]; hObject
0x18001bcba  lea     rax, [rcx-1]
0x18001bcbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bcc2  jbe     loc_18001BDB0
0x18001bcc8  lea     rcx, [rbp+var_30]; this
0x18001bccc  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001bcd1  xor     eax, eax
0x18001bcd3  jmp     short loc_18001BC84
0x18001bcd5  jg      short loc_18001BD23
0x18001bcd7  test    esi, esi
0x18001bcd9  jns     loc_18001BB15
0x18001bcdf  mov     rcx, [rbp+18h]; this
0x18001bce3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001bcea  mov     r9d, esi; char *
0x18001bced  mov     edx, 0ABh; void *
0x18001bcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcf7  lea     rcx, [rbp+var_30]; this
0x18001bcfb  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001bd00  mov     eax, esi
0x18001bd02  jmp     short loc_18001BC84
0x18001bd04  cmp     [rbp+arg_18], 4
0x18001bd08  jnz     loc_18001BAAA
0x18001bd0e  cmp     word ptr [rbp+var_40], 31h ; '1'
0x18001bd13  jnz     loc_18001BAAA
0x18001bd19  mov     eax, 80070015h
0x18001bd1e  jmp     loc_18001BC94
0x18001bd23  movzx   esi, ax
0x18001bd26  or      esi, 80070000h
0x18001bd2c  jmp     short loc_18001BCD7
0x18001bd2e  mov     rcx, [rbp+18h]; this
0x18001bd32  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001bd39  mov     edx, 0B2h; void *
0x18001bd3e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bd43  lea     rcx, [rbp+TokenHandle]
0x18001bd47  mov     ebx, eax
0x18001bd49  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001bd4e  lea     rcx, [rbp+var_30]; this
0x18001bd52  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001bd57  jmp     loc_18001BC82
0x18001bd5c  call    cs:__imp_CloseHandle
0x18001bd63  nop     dword ptr [rax+rax+00h]
0x18001bd68  jmp     loc_18001BC53
0x18001bd6d  mov     rdi, [rbp+Token]
0x18001bd71  xor     ecx, ecx; Thread
0x18001bd73  mov     rdx, rdi; Token
0x18001bd76  call    cs:__imp_SetThreadToken
0x18001bd7d  nop     dword ptr [rax+rax+00h]
0x18001bd82  test    rdi, rdi
0x18001bd85  jz      loc_18001BC66
0x18001bd8b  mov     rcx, rdi; hObject
0x18001bd8e  call    cs:__imp_CloseHandle
0x18001bd95  nop     dword ptr [rax+rax+00h]
0x18001bd9a  jmp     loc_18001BC66
0x18001bd9f  call    cs:__imp_RevertToSelf
0x18001bda6  nop     dword ptr [rax+rax+00h]
0x18001bdab  jmp     loc_18001BC82
0x18001bdb0  call    cs:__imp_CloseHandle
0x18001bdb7  nop     dword ptr [rax+rax+00h]
0x18001bdbc  jmp     loc_18001BCC8
0x18001bdc1  call    cs:__imp_CloseHandle
0x18001bdc8  nop     dword ptr [rax+rax+00h]
0x18001bdcd  jmp     loc_18001BBA5
```
