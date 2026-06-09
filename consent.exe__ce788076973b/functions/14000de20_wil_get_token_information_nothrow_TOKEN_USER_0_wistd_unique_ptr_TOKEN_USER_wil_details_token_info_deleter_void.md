# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x14000de20`
- end: `0x14000df4d`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ddc4`
- `0x140019b34`

## callees

- `0x14000de20`
- `0x14000df54`
- `0x14000fb48`
- `0x140010080`
- `0x140010798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000de84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000de84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000de76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000dee7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000de76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000dee7`

## string_xrefs

- `0x14000deb0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x14000def6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x14000df2c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x14000de20  mov     [rsp+arg_8], rbx
0x14000de25  mov     [rsp+arg_10], rsi
0x14000de2a  push    rdi
0x14000de2b  sub     rsp, 30h
0x14000de2f  mov     rbx, rcx
0x14000de32  mov     rsi, rdx
0x14000de35  mov     rcx, [rcx]; Block
0x14000de38  mov     qword ptr [rbx], 0
0x14000de3f  test    rcx, rcx
0x14000de42  jz      short loc_14000DE49
0x14000de44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000de49  mov     rax, 0FFFFFFFFFFFFFFFAh
0x14000de50  mov     [rsp+38h+TokenInformationLength], 0
0x14000de58  test    rsi, rsi
0x14000de5b  cmovz   rsi, rax
0x14000de5f  xor     r9d, r9d; TokenInformationLength
0x14000de62  lea     rax, [rsp+38h+TokenInformationLength]
0x14000de67  xor     r8d, r8d; TokenInformation
0x14000de6a  mov     rcx, rsi; TokenHandle
0x14000de6d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x14000de72  lea     edx, [r9+1]; TokenInformationClass
0x14000de76  call    cs:__imp_GetTokenInformation
0x14000de7c  test    eax, eax
0x14000de7e  jnz     loc_14000DF27
0x14000de84  call    cs:__imp_GetLastError
0x14000de8a  cmp     eax, 7Ah ; 'z'
0x14000de8d  jnz     loc_14000DF27
0x14000de93  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x14000de97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000de9e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000dea3  mov     rdi, rax
0x14000dea6  test    rax, rax
0x14000dea9  jnz     short loc_14000DECD
0x14000deab  mov     rcx, [rsp+38h]; this
0x14000deb0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000deb7  mov     ebx, 8007000Eh
0x14000debc  mov     edx, 119h; void *
0x14000dec1  mov     r9d, ebx; char *
0x14000dec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000dec9  mov     eax, ebx
0x14000decb  jmp     short loc_14000DF3D
0x14000decd  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14000ded2  lea     rax, [rsp+38h+TokenInformationLength]
0x14000ded7  mov     r8, rdi; TokenInformation
0x14000deda  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x14000dedf  mov     edx, 1; TokenInformationClass
0x14000dee4  mov     rcx, rsi; TokenHandle
0x14000dee7  call    cs:__imp_GetTokenInformation
0x14000deed  test    eax, eax
0x14000deef  jnz     short loc_14000DF13
0x14000def1  mov     rcx, [rsp+38h]; this
0x14000def6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000defd  mov     edx, 11Ah; void *
0x14000df02  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000df07  mov     rcx, rdi; Block
0x14000df0a  mov     ebx, eax
0x14000df0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000df11  jmp     short loc_14000DEC9
0x14000df13  mov     rcx, [rbx]; Block
0x14000df16  mov     [rbx], rdi
0x14000df19  test    rcx, rcx
0x14000df1c  jz      short loc_14000DF23
0x14000df1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000df23  xor     eax, eax
0x14000df25  jmp     short loc_14000DF3D
0x14000df27  mov     rcx, [rsp+38h]; this
0x14000df2c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000df33  mov     edx, 117h; void *
0x14000df38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000df3d  mov     rbx, [rsp+38h+arg_8]
0x14000df42  mov     rsi, [rsp+38h+arg_10]
0x14000df47  add     rsp, 30h
0x14000df4b  pop     rdi
0x14000df4c  retn
```
