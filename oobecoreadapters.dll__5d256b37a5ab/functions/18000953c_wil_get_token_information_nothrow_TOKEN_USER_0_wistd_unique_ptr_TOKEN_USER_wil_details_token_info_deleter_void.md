# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18000953c`
- end: `0x180009669`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009b90`
- `0x18004c054`

## callees

- `0x180003230`
- `0x180003ffc`
- `0x1800076b4`
- `0x1800076d4`
- `0x18000953c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009592`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009603`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009592`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009603`

## string_xrefs

- `0x1800095cc`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009612`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009648`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18000953c  mov     [rsp+arg_8], rbx
0x180009541  mov     [rsp+arg_10], rsi
0x180009546  push    rdi
0x180009547  sub     rsp, 30h
0x18000954b  mov     rbx, rcx
0x18000954e  mov     rsi, rdx
0x180009551  mov     rcx, [rcx]; Block
0x180009554  mov     qword ptr [rbx], 0
0x18000955b  test    rcx, rcx
0x18000955e  jz      short loc_180009565
0x180009560  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009565  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000956c  mov     [rsp+38h+TokenInformationLength], 0
0x180009574  test    rsi, rsi
0x180009577  cmovz   rsi, rax
0x18000957b  xor     r9d, r9d; TokenInformationLength
0x18000957e  lea     rax, [rsp+38h+TokenInformationLength]
0x180009583  xor     r8d, r8d; TokenInformation
0x180009586  mov     rcx, rsi; TokenHandle
0x180009589  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000958e  lea     edx, [r9+1]; TokenInformationClass
0x180009592  call    cs:__imp_GetTokenInformation
0x180009598  test    eax, eax
0x18000959a  jnz     loc_180009643
0x1800095a0  call    cs:__imp_GetLastError
0x1800095a6  cmp     eax, 7Ah ; 'z'
0x1800095a9  jnz     loc_180009643
0x1800095af  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800095b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800095ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800095bf  mov     rdi, rax
0x1800095c2  test    rax, rax
0x1800095c5  jnz     short loc_1800095E9
0x1800095c7  mov     rcx, [rsp+38h]; this
0x1800095cc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800095d3  mov     ebx, 8007000Eh
0x1800095d8  mov     edx, 119h; void *
0x1800095dd  mov     r9d, ebx; char *
0x1800095e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095e5  mov     eax, ebx
0x1800095e7  jmp     short loc_180009659
0x1800095e9  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800095ee  lea     rax, [rsp+38h+TokenInformationLength]
0x1800095f3  mov     r8, rdi; TokenInformation
0x1800095f6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800095fb  mov     edx, 1; TokenInformationClass
0x180009600  mov     rcx, rsi; TokenHandle
0x180009603  call    cs:__imp_GetTokenInformation
0x180009609  test    eax, eax
0x18000960b  jnz     short loc_18000962F
0x18000960d  mov     rcx, [rsp+38h]; this
0x180009612  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009619  mov     edx, 11Ah; void *
0x18000961e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009623  mov     rcx, rdi; Block
0x180009626  mov     ebx, eax
0x180009628  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000962d  jmp     short loc_1800095E5
0x18000962f  mov     rcx, [rbx]; Block
0x180009632  mov     [rbx], rdi
0x180009635  test    rcx, rcx
0x180009638  jz      short loc_18000963F
0x18000963a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000963f  xor     eax, eax
0x180009641  jmp     short loc_180009659
0x180009643  mov     rcx, [rsp+38h]; this
0x180009648  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000964f  mov     edx, 117h; void *
0x180009654  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009659  mov     rbx, [rsp+38h+arg_8]
0x18000965e  mov     rsi, [rsp+38h+arg_10]
0x180009663  add     rsp, 30h
0x180009667  pop     rdi
0x180009668  retn
```
