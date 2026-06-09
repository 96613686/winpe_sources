# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18004e1c0`
- end: `0x18004e2ed`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029884`

## callees

- `0x18002a948`
- `0x18002aa34`
- `0x18003c5ec`
- `0x18003ca3c`
- `0x18004e1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e224`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e216`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e287`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e216`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e287`

## string_xrefs

- `0x18004e250`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18004e296`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18004e2cc`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rdi
  unsigned int LastError; // ebx
  const char *v9; // r9
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( !a2 )
    a2 = -6;
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
    operator delete(v6);
    return LastError;
  }
  v10 = *a1;
  *a1 = v6;
  if ( v10 )
    operator delete(v10);
  return 0;
}

```

## disassembly

```asm
0x18004e1c0  mov     [rsp+arg_8], rbx
0x18004e1c5  mov     [rsp+arg_10], rsi
0x18004e1ca  push    rdi
0x18004e1cb  sub     rsp, 30h
0x18004e1cf  mov     rbx, rcx
0x18004e1d2  mov     rsi, rdx
0x18004e1d5  mov     rcx, [rcx]; Block
0x18004e1d8  mov     qword ptr [rbx], 0
0x18004e1df  test    rcx, rcx
0x18004e1e2  jz      short loc_18004E1E9
0x18004e1e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e1e9  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18004e1f0  mov     [rsp+38h+TokenInformationLength], 0
0x18004e1f8  test    rsi, rsi
0x18004e1fb  cmovz   rsi, rax
0x18004e1ff  xor     r9d, r9d; TokenInformationLength
0x18004e202  lea     rax, [rsp+38h+TokenInformationLength]
0x18004e207  xor     r8d, r8d; TokenInformation
0x18004e20a  mov     rcx, rsi; TokenHandle
0x18004e20d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18004e212  lea     edx, [r9+1]; TokenInformationClass
0x18004e216  call    cs:__imp_GetTokenInformation
0x18004e21c  test    eax, eax
0x18004e21e  jnz     loc_18004E2C7
0x18004e224  call    cs:__imp_GetLastError
0x18004e22a  cmp     eax, 7Ah ; 'z'
0x18004e22d  jnz     loc_18004E2C7
0x18004e233  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18004e237  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004e23e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004e243  mov     rdi, rax
0x18004e246  test    rax, rax
0x18004e249  jnz     short loc_18004E26D
0x18004e24b  mov     rcx, [rsp+38h]; this
0x18004e250  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004e257  mov     ebx, 8007000Eh
0x18004e25c  mov     edx, 119h; void *
0x18004e261  mov     r9d, ebx; char *
0x18004e264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e269  mov     eax, ebx
0x18004e26b  jmp     short loc_18004E2DD
0x18004e26d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18004e272  lea     rax, [rsp+38h+TokenInformationLength]
0x18004e277  mov     r8, rdi; TokenInformation
0x18004e27a  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18004e27f  mov     edx, 1; TokenInformationClass
0x18004e284  mov     rcx, rsi; TokenHandle
0x18004e287  call    cs:__imp_GetTokenInformation
0x18004e28d  test    eax, eax
0x18004e28f  jnz     short loc_18004E2B3
0x18004e291  mov     rcx, [rsp+38h]; this
0x18004e296  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004e29d  mov     edx, 11Ah; void *
0x18004e2a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e2a7  mov     rcx, rdi; Block
0x18004e2aa  mov     ebx, eax
0x18004e2ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e2b1  jmp     short loc_18004E269
0x18004e2b3  mov     rcx, [rbx]; Block
0x18004e2b6  mov     [rbx], rdi
0x18004e2b9  test    rcx, rcx
0x18004e2bc  jz      short loc_18004E2C3
0x18004e2be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e2c3  xor     eax, eax
0x18004e2c5  jmp     short loc_18004E2DD
0x18004e2c7  mov     rcx, [rsp+38h]; this
0x18004e2cc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004e2d3  mov     edx, 117h; void *
0x18004e2d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e2dd  mov     rbx, [rsp+38h+arg_8]
0x18004e2e2  mov     rsi, [rsp+38h+arg_10]
0x18004e2e7  add     rsp, 30h
0x18004e2eb  pop     rdi
0x18004e2ec  retn
```
