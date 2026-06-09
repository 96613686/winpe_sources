# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18001432c`
- end: `0x180014468`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `316`
- prototype: ``
- caller_count: `16`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800224e0`
- `0x18002d7b4`
- `0x18002ece8`
- `0x18003fca0`
- `0x18004d73c`
- `0x18007c5a0`
- `0x1800828f8`
- `0x180082ba8`
- `0x18008a0b4`
- `0x1800966b8`
- `0x1800982f0`
- `0x1800984c4`
- `0x18009cb90`
- `0x18009f318`
- `0x1800b6398`
- `0x1800b966c`

## callees

- `0x180005fac`
- `0x18000937c`
- `0x18000e214`
- `0x18000e234`
- `0x18001432c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014390`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001437c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800143f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001437c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800143f9`

## string_xrefs

- `0x1800143c2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001440e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180014446`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  if ( !a2 )
    a2 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    if ( GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = *a1;
      *a1 = v6;
      if ( v10 )
        operator delete(v10);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                    v8);
      operator delete(v6);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001432c  mov     [rsp+arg_8], rbx
0x180014331  mov     [rsp+arg_10], rsi
0x180014336  push    rdi
0x180014337  sub     rsp, 30h
0x18001433b  mov     rdi, rcx
0x18001433e  mov     rsi, rdx
0x180014341  mov     rcx, [rcx]; Block
0x180014344  and     qword ptr [rdi], 0
0x180014348  test    rcx, rcx
0x18001434b  jz      short loc_180014352
0x18001434d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014352  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180014359  test    rsi, rsi
0x18001435c  cmovz   rsi, rax
0x180014360  and     [rsp+38h+TokenInformationLength], 0
0x180014365  xor     r9d, r9d; TokenInformationLength
0x180014368  lea     rax, [rsp+38h+TokenInformationLength]
0x18001436d  xor     r8d, r8d; TokenInformation
0x180014370  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180014375  mov     rcx, rsi; TokenHandle
0x180014378  lea     edx, [r9+1]; TokenInformationClass
0x18001437c  call    cs:__imp_GetTokenInformation
0x180014383  nop     dword ptr [rax+rax+00h]
0x180014388  test    eax, eax
0x18001438a  jnz     loc_180014441
0x180014390  call    cs:__imp_GetLastError
0x180014397  nop     dword ptr [rax+rax+00h]
0x18001439c  cmp     eax, 7Ah ; 'z'
0x18001439f  jnz     loc_180014441
0x1800143a5  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800143a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800143b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800143b5  mov     rbx, rax
0x1800143b8  test    rax, rax
0x1800143bb  jnz     short loc_1800143DF
0x1800143bd  mov     rcx, [rsp+38h]; this
0x1800143c2  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800143c9  mov     ebx, 8007000Eh
0x1800143ce  mov     edx, 119h; void *
0x1800143d3  mov     r9d, ebx; char *
0x1800143d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800143db  mov     eax, ebx
0x1800143dd  jmp     short loc_180014457
0x1800143df  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800143e4  lea     rax, [rsp+38h+TokenInformationLength]
0x1800143e9  mov     r8, rbx; TokenInformation
0x1800143ec  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800143f1  mov     edx, 1; TokenInformationClass
0x1800143f6  mov     rcx, rsi; TokenHandle
0x1800143f9  call    cs:__imp_GetTokenInformation
0x180014400  nop     dword ptr [rax+rax+00h]
0x180014405  test    eax, eax
0x180014407  jnz     short loc_18001442D
0x180014409  mov     rcx, [rsp+38h]; this
0x18001440e  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014415  mov     edx, 11Ah; void *
0x18001441a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001441f  mov     rcx, rbx; Block
0x180014422  mov     edi, eax
0x180014424  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014429  mov     eax, edi
0x18001442b  jmp     short loc_180014457
0x18001442d  mov     rcx, [rdi]; Block
0x180014430  mov     [rdi], rbx
0x180014433  test    rcx, rcx
0x180014436  jz      short loc_18001443D
0x180014438  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001443d  xor     eax, eax
0x18001443f  jmp     short loc_180014457
0x180014441  mov     rcx, [rsp+38h]; this
0x180014446  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001444d  mov     edx, 117h; void *
0x180014452  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014457  mov     rbx, [rsp+38h+arg_8]
0x18001445c  mov     rsi, [rsp+38h+arg_10]
0x180014461  add     rsp, 30h
0x180014465  pop     rdi
0x180014466  retn
```
