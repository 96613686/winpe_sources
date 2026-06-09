# UnloadUserProfileServer

- ea: `0x18001afd0`
- end: `0x18001b24a`
- name: `UnloadUserProfileServer`
- size: `634`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008fa0`
- `0x18001afd0`
- `0x18001c130`
- `0x18001c358`
- `0x18001c4a0`
- `0x18002df48`
- `0x180030ad0`
- `0x18003c040`
- `0x18003c1b0`
- `0x18003c870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b04f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b04f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b20c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b20c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b239`
- `RPCRT4!RpcRevertToSelf` at `0x18001b067`
- `RPCRT4!RpcRevertToSelf` at `0x18001b067`
- `RPCRT4!RpcImpersonateClient` at `0x18001b00c`
- `RPCRT4!RpcImpersonateClient` at `0x18001b00c`

## string_xrefs

- `0x18001b095`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001b175`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001b19c`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001b1ea`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

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
0x18001afd0  mov     rax, rsp
0x18001afd3  push    rbx
0x18001afd4  sub     rsp, 50h
0x18001afd8  mov     rbx, rdx
0x18001afdb  test    rdx, rdx
0x18001afde  jz      loc_18001B0D0
0x18001afe4  mov     [rax+8], rbp
0x18001afe8  xorps   xmm0, xmm0
0x18001afeb  xor     ebp, ebp
0x18001afed  mov     [rax+18h], rsi
0x18001aff1  mov     [rax+20h], rdi
0x18001aff5  xor     ecx, ecx; BindingHandle
0x18001aff7  mov     [rax-38h], ebp
0x18001affa  mov     edi, ebp
0x18001affc  mov     [rax-30h], rbp
0x18001b000  mov     [rax-28h], rbp
0x18001b004  mov     [rax-20h], ebp
0x18001b007  movdqu  xmmword ptr [rax-18h], xmm0
0x18001b00c  call    cs:__imp_RpcImpersonateClient
0x18001b013  nop     dword ptr [rax+rax+00h]
0x18001b018  mov     esi, eax
0x18001b01a  test    eax, eax
0x18001b01c  jnz     loc_18001B162
0x18001b022  mov     edi, 1
0x18001b027  mov     [rsp+58h+var_24], edi
0x18001b02b  mov     [rsp+58h+TokenHandle], rbp
0x18001b030  call    cs:__imp_GetCurrentThread
0x18001b037  nop     dword ptr [rax+rax+00h]
0x18001b03c  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18001b041  mov     edx, 0F01FFh; DesiredAccess
0x18001b046  mov     rcx, rax; ThreadHandle
0x18001b049  mov     r8d, 1; OpenAsSelf
0x18001b04f  call    cs:__imp_OpenThreadToken
0x18001b056  nop     dword ptr [rax+rax+00h]
0x18001b05b  test    eax, eax
0x18001b05d  jz      loc_18001B1E5
0x18001b063  test    edi, edi
0x18001b065  jz      short loc_18001B077
0x18001b067  call    cs:__imp_RpcRevertToSelf
0x18001b06e  nop     dword ptr [rax+rax+00h]
0x18001b073  mov     [rsp+58h+var_24], ebp
0x18001b077  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b07e  mov     ecx, 130h; unsigned __int64
0x18001b083  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b088  mov     rdi, rax
0x18001b08b  test    rax, rax
0x18001b08e  jnz     short loc_18001B0DC
0x18001b090  mov     rcx, [rsp+58h]; this
0x18001b095  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001b09c  mov     r9d, 8007000Eh; char *
0x18001b0a2  mov     edx, 0EEh; void *
0x18001b0a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b0ac  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001b0b1  lea     rdx, [rcx-1]
0x18001b0b5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001b0b9  jbe     loc_18001B239
0x18001b0bf  lea     rcx, [rsp+58h+var_38]; this
0x18001b0c4  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b0c9  mov     eax, 8007000Eh
0x18001b0ce  jmp     short loc_18001B14C
0x18001b0d0  mov     eax, 80070057h
0x18001b0d5  add     rsp, 50h
0x18001b0d9  pop     rbx
0x18001b0da  retn
0x18001b0dc  xor     edx, edx; Val
0x18001b0de  mov     r8d, 130h; Size
0x18001b0e4  mov     rcx, rdi; void *
0x18001b0e7  call    memset_0
0x18001b0ec  mov     rcx, rdi; this
0x18001b0ef  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x18001b0f4  mov     rdi, rax
0x18001b0f7  test    rax, rax
0x18001b0fa  jz      short loc_18001B090
0x18001b0fc  mov     r8, [rsp+58h+TokenHandle]; void *
0x18001b101  mov     r9d, 0FFFFFFFFh; unsigned int
0x18001b107  mov     rdx, [rbx]; hToken
0x18001b10a  mov     rcx, rax; this
0x18001b10d  call    ?Unload@CUserProfile@@QEAAJPEAX0K@Z; CUserProfile::Unload(void *,void *,ulong)
0x18001b112  mov     ebx, eax
0x18001b114  test    eax, eax
0x18001b116  js      short loc_18001B197
0x18001b118  mov     rcx, rdi; this
0x18001b11b  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001b120  mov     edx, 130h; unsigned __int64
0x18001b125  mov     rcx, rdi; void *
0x18001b128  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b12d  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001b132  lea     rax, [rcx-1]
0x18001b136  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b13a  jbe     loc_18001B228
0x18001b140  lea     rcx, [rsp+58h+var_38]; this
0x18001b145  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b14a  xor     eax, eax
0x18001b14c  mov     rsi, [rsp+58h+arg_10]
0x18001b151  mov     rbp, [rsp+58h+arg_0]
0x18001b156  mov     rdi, [rsp+58h+arg_18]
0x18001b15b  add     rsp, 50h
0x18001b15f  pop     rbx
0x18001b160  retn
0x18001b162  jg      loc_18001B21A
0x18001b168  test    esi, esi
0x18001b16a  jns     loc_18001B02B
0x18001b170  mov     rcx, [rsp+58h]; this
0x18001b175  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001b17c  mov     r9d, esi; char *
0x18001b17f  mov     edx, 0E1h; void *
0x18001b184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b189  lea     rcx, [rsp+58h+var_38]; this
0x18001b18e  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b193  mov     eax, esi
0x18001b195  jmp     short loc_18001B14C
0x18001b197  mov     rcx, [rsp+58h]; this
0x18001b19c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001b1a3  mov     r9d, ebx; char *
0x18001b1a6  mov     edx, 0F1h; void *
0x18001b1ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1b0  mov     rcx, rdi; this
0x18001b1b3  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001b1b8  mov     edx, 130h; unsigned __int64
0x18001b1bd  mov     rcx, rdi; void *
0x18001b1c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b1c5  mov     rcx, [rsp+58h+TokenHandle]
0x18001b1ca  lea     rax, [rcx-1]
0x18001b1ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b1d2  jbe     short loc_18001B20C
0x18001b1d4  lea     rcx, [rsp+58h+var_38]; this
0x18001b1d9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b1de  mov     eax, ebx
0x18001b1e0  jmp     loc_18001B14C
0x18001b1e5  mov     rcx, [rsp+58h]; this
0x18001b1ea  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001b1f1  mov     edx, 0E8h; void *
0x18001b1f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b1fb  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001b200  mov     ebx, eax
0x18001b202  lea     rdx, [rcx-1]
0x18001b206  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001b20a  ja      short loc_18001B1D4
0x18001b20c  call    cs:__imp_CloseHandle
0x18001b213  nop     dword ptr [rax+rax+00h]
0x18001b218  jmp     short loc_18001B1D4
0x18001b21a  movzx   esi, ax
0x18001b21d  or      esi, 80070000h
0x18001b223  jmp     loc_18001B168
0x18001b228  call    cs:__imp_CloseHandle
0x18001b22f  nop     dword ptr [rax+rax+00h]
0x18001b234  jmp     loc_18001B140
0x18001b239  call    cs:__imp_CloseHandle
0x18001b240  nop     dword ptr [rax+rax+00h]
0x18001b245  jmp     loc_18001B0BF
```
