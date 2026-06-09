# UnloadUserProfileServer

- ea: `0x180018110`
- end: `0x18001835e`
- name: `UnloadUserProfileServer`
- size: `590`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b540`
- `0x180018110`
- `0x180018bcc`
- `0x180019460`
- `0x180019630`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003ab00`
- `0x18003ac70`
- `0x18003b310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018183`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001816a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001816a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018353`
- `RPCRT4!RpcRevertToSelf` at `0x180018195`
- `RPCRT4!RpcRevertToSelf` at `0x180018195`
- `RPCRT4!RpcImpersonateClient` at `0x18001814c`
- `RPCRT4!RpcImpersonateClient` at `0x18001814c`

## string_xrefs

- `0x1800181bd`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001829b`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x1800182c2`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180018310`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall UnloadUserProfileServer(__int64 a1, HANDLE *a2)
{
  int v3; // edi
  RPC_STATUS v4; // eax
  unsigned int v5; // esi
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  CUserProfile *v8; // rax
  CUserProfile *v9; // rdi
  CUserProfile *v11; // rax
  CUserProfile *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  void *v15; // rcx
  unsigned int LastError; // eax
  int v17; // [rsp+20h] [rbp-38h] BYREF
  __int64 v18; // [rsp+28h] [rbp-30h]
  __int64 v19; // [rsp+30h] [rbp-28h]
  int v20; // [rsp+38h] [rbp-20h]
  __int128 v21; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v17 = 0;
  v3 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v4 = RpcImpersonateClient(0);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)v5,
        v17);
      CThreadContext::~CThreadContext((CThreadContext *)&v17);
      return v5;
    }
  }
  else
  {
    v3 = 1;
    HIDWORD(v19) = 1;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE8,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                  v7);
    v15 = TokenHandle;
    v14 = LastError;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_22;
    goto LABEL_24;
  }
  if ( v3 )
  {
    RpcRevertToSelf();
    HIDWORD(v19) = 0;
  }
  v8 = (CUserProfile *)operator new(0x130u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 || (memset_0(v8, 0, 0x130u), v11 = CUserProfile::CUserProfile(v9), (v12 = v11) == 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x8007000ELL,
      v17);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    CThreadContext::~CThreadContext((CThreadContext *)&v17);
    return 2147942414LL;
  }
  v13 = CUserProfile::Unload(v11, *a2, TokenHandle, 0xFFFFFFFF);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)(unsigned int)v13,
      v17);
    CUserProfile::~CUserProfile(v12);
    operator delete(v12, 0x130u);
    v15 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
LABEL_22:
      CThreadContext::~CThreadContext((CThreadContext *)&v17);
      return v14;
    }
LABEL_24:
    CloseHandle(v15);
    goto LABEL_22;
  }
  CUserProfile::~CUserProfile(v12);
  operator delete(v12, 0x130u);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  CThreadContext::~CThreadContext((CThreadContext *)&v17);
  return 0;
}

```

## disassembly

```asm
0x180018110  mov     rax, rsp
0x180018113  push    rbx
0x180018114  sub     rsp, 50h
0x180018118  mov     rbx, rdx
0x18001811b  test    rdx, rdx
0x18001811e  jz      loc_1800181F8
0x180018124  mov     [rax+8], rbp
0x180018128  xorps   xmm0, xmm0
0x18001812b  xor     ebp, ebp
0x18001812d  mov     [rax+18h], rsi
0x180018131  mov     [rax+20h], rdi
0x180018135  xor     ecx, ecx; BindingHandle
0x180018137  mov     [rax-38h], ebp
0x18001813a  mov     edi, ebp
0x18001813c  mov     [rax-30h], rbp
0x180018140  mov     [rax-28h], rbp
0x180018144  mov     [rax-20h], ebp
0x180018147  movdqu  xmmword ptr [rax-18h], xmm0
0x18001814c  call    cs:__imp_RpcImpersonateClient
0x180018152  mov     esi, eax
0x180018154  test    eax, eax
0x180018156  jnz     loc_180018288
0x18001815c  mov     edi, 1
0x180018161  mov     [rsp+58h+var_24], edi
0x180018165  mov     [rsp+58h+TokenHandle], rbp
0x18001816a  call    cs:__imp_GetCurrentThread
0x180018170  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180018175  mov     edx, 0F01FFh; DesiredAccess
0x18001817a  mov     rcx, rax; ThreadHandle
0x18001817d  mov     r8d, 1; OpenAsSelf
0x180018183  call    cs:__imp_OpenThreadToken
0x180018189  test    eax, eax
0x18001818b  jz      loc_18001830B
0x180018191  test    edi, edi
0x180018193  jz      short loc_18001819F
0x180018195  call    cs:__imp_RpcRevertToSelf
0x18001819b  mov     [rsp+58h+var_24], ebp
0x18001819f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800181a6  mov     ecx, 130h; unsigned __int64
0x1800181ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800181b0  mov     rdi, rax
0x1800181b3  test    rax, rax
0x1800181b6  jnz     short loc_180018203
0x1800181b8  mov     rcx, [rsp+58h]; this
0x1800181bd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800181c4  mov     r9d, 8007000Eh; char *
0x1800181ca  mov     edx, 0EEh; void *
0x1800181cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181d4  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800181d9  lea     rdx, [rcx-1]
0x1800181dd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800181e1  jbe     loc_180018353
0x1800181e7  lea     rcx, [rsp+58h+var_38]; this
0x1800181ec  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800181f1  mov     eax, 8007000Eh
0x1800181f6  jmp     short loc_180018273
0x1800181f8  mov     eax, 80070057h
0x1800181fd  add     rsp, 50h
0x180018201  pop     rbx
0x180018202  retn
0x180018203  xor     edx, edx; Val
0x180018205  mov     r8d, 130h; Size
0x18001820b  mov     rcx, rdi; void *
0x18001820e  call    memset_0
0x180018213  mov     rcx, rdi; this
0x180018216  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x18001821b  mov     rdi, rax
0x18001821e  test    rax, rax
0x180018221  jz      short loc_1800181B8
0x180018223  mov     r8, [rsp+58h+TokenHandle]; void *
0x180018228  mov     r9d, 0FFFFFFFFh; unsigned int
0x18001822e  mov     rdx, [rbx]; hToken
0x180018231  mov     rcx, rax; this
0x180018234  call    ?Unload@CUserProfile@@QEAAJPEAX0K@Z; CUserProfile::Unload(void *,void *,ulong)
0x180018239  mov     ebx, eax
0x18001823b  test    eax, eax
0x18001823d  js      short loc_1800182BD
0x18001823f  mov     rcx, rdi; this
0x180018242  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180018247  mov     edx, 130h; unsigned __int64
0x18001824c  mov     rcx, rdi; void *
0x18001824f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018254  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180018259  lea     rax, [rcx-1]
0x18001825d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018261  jbe     loc_180018348
0x180018267  lea     rcx, [rsp+58h+var_38]; this
0x18001826c  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018271  xor     eax, eax
0x180018273  mov     rsi, [rsp+58h+arg_10]
0x180018278  mov     rbp, [rsp+58h+arg_0]
0x18001827d  mov     rdi, [rsp+58h+arg_18]
0x180018282  add     rsp, 50h
0x180018286  pop     rbx
0x180018287  retn
0x180018288  jg      loc_18001833A
0x18001828e  test    esi, esi
0x180018290  jns     loc_180018165
0x180018296  mov     rcx, [rsp+58h]; this
0x18001829b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800182a2  mov     r9d, esi; char *
0x1800182a5  mov     edx, 0E1h; void *
0x1800182aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800182af  lea     rcx, [rsp+58h+var_38]; this
0x1800182b4  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800182b9  mov     eax, esi
0x1800182bb  jmp     short loc_180018273
0x1800182bd  mov     rcx, [rsp+58h]; this
0x1800182c2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800182c9  mov     r9d, ebx; char *
0x1800182cc  mov     edx, 0F1h; void *
0x1800182d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800182d6  mov     rcx, rdi; this
0x1800182d9  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x1800182de  mov     edx, 130h; unsigned __int64
0x1800182e3  mov     rcx, rdi; void *
0x1800182e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800182eb  mov     rcx, [rsp+58h+TokenHandle]
0x1800182f0  lea     rax, [rcx-1]
0x1800182f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800182f8  jbe     short loc_180018332
0x1800182fa  lea     rcx, [rsp+58h+var_38]; this
0x1800182ff  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018304  mov     eax, ebx
0x180018306  jmp     loc_180018273
0x18001830b  mov     rcx, [rsp+58h]; this
0x180018310  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018317  mov     edx, 0E8h; void *
0x18001831c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018321  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180018326  mov     ebx, eax
0x180018328  lea     rdx, [rcx-1]
0x18001832c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180018330  ja      short loc_1800182FA
0x180018332  call    cs:__imp_CloseHandle
0x180018338  jmp     short loc_1800182FA
0x18001833a  movzx   esi, ax
0x18001833d  or      esi, 80070000h
0x180018343  jmp     loc_18001828E
0x180018348  call    cs:__imp_CloseHandle
0x18001834e  jmp     loc_180018267
0x180018353  call    cs:__imp_CloseHandle
0x180018359  jmp     loc_1800181E7
```
