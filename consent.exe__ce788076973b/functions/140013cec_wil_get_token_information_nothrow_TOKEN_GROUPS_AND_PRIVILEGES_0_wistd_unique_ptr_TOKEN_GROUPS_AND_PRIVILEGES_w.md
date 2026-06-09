# wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_GROUPS_AND_PRIVILEGES,wil::details::token_info_deleter> &,void *)

- ea: `0x140013cec`
- end: `0x140013e19`
- name: `??$get_token_information_nothrow@U_TOKEN_GROUPS_AND_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_GROUPS_AND_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000cfdc`

## callees

- `0x14000df54`
- `0x14000fb48`
- `0x140010080`
- `0x140010798`
- `0x140013cec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013d50`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013d42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013db3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013d42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140013db3`

## string_xrefs

- `0x140013d7c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x140013dc2`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x140013df8`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenGroupsAndPrivileges, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
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
  if ( !GetTokenInformation((HANDLE)a2, TokenGroupsAndPrivileges, v6, TokenInformationLength, &TokenInformationLength) )
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
0x140013cec  mov     [rsp+arg_8], rbx
0x140013cf1  mov     [rsp+arg_10], rsi
0x140013cf6  push    rdi
0x140013cf7  sub     rsp, 30h
0x140013cfb  mov     rbx, rcx
0x140013cfe  mov     rsi, rdx
0x140013d01  mov     rcx, [rcx]; Block
0x140013d04  mov     qword ptr [rbx], 0
0x140013d0b  test    rcx, rcx
0x140013d0e  jz      short loc_140013D15
0x140013d10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013d15  mov     rax, 0FFFFFFFFFFFFFFFAh
0x140013d1c  mov     [rsp+38h+TokenInformationLength], 0
0x140013d24  test    rsi, rsi
0x140013d27  cmovz   rsi, rax
0x140013d2b  xor     r9d, r9d; TokenInformationLength
0x140013d2e  lea     rax, [rsp+38h+TokenInformationLength]
0x140013d33  xor     r8d, r8d; TokenInformation
0x140013d36  mov     rcx, rsi; TokenHandle
0x140013d39  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140013d3e  lea     edx, [r9+0Dh]; TokenInformationClass
0x140013d42  call    cs:__imp_GetTokenInformation
0x140013d48  test    eax, eax
0x140013d4a  jnz     loc_140013DF3
0x140013d50  call    cs:__imp_GetLastError
0x140013d56  cmp     eax, 7Ah ; 'z'
0x140013d59  jnz     loc_140013DF3
0x140013d5f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140013d63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140013d6a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140013d6f  mov     rdi, rax
0x140013d72  test    rax, rax
0x140013d75  jnz     short loc_140013D99
0x140013d77  mov     rcx, [rsp+38h]; this
0x140013d7c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140013d83  mov     ebx, 8007000Eh
0x140013d88  mov     edx, 119h; void *
0x140013d8d  mov     r9d, ebx; char *
0x140013d90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013d95  mov     eax, ebx
0x140013d97  jmp     short loc_140013E09
0x140013d99  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140013d9e  lea     rax, [rsp+38h+TokenInformationLength]
0x140013da3  mov     r8, rdi; TokenInformation
0x140013da6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140013dab  mov     edx, 0Dh; TokenInformationClass
0x140013db0  mov     rcx, rsi; TokenHandle
0x140013db3  call    cs:__imp_GetTokenInformation
0x140013db9  test    eax, eax
0x140013dbb  jnz     short loc_140013DDF
0x140013dbd  mov     rcx, [rsp+38h]; this
0x140013dc2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140013dc9  mov     edx, 11Ah; void *
0x140013dce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013dd3  mov     rcx, rdi; Block
0x140013dd6  mov     ebx, eax
0x140013dd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013ddd  jmp     short loc_140013D95
0x140013ddf  mov     rcx, [rbx]; Block
0x140013de2  mov     [rbx], rdi
0x140013de5  test    rcx, rcx
0x140013de8  jz      short loc_140013DEF
0x140013dea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013def  xor     eax, eax
0x140013df1  jmp     short loc_140013E09
0x140013df3  mov     rcx, [rsp+38h]; this
0x140013df8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140013dff  mov     edx, 117h; void *
0x140013e04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013e09  mov     rbx, [rsp+38h+arg_8]
0x140013e0e  mov     rsi, [rsp+38h+arg_10]
0x140013e13  add     rsp, 30h
0x140013e17  pop     rdi
0x140013e18  retn
```
