# wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x1400322dc`
- end: `0x140032409`
- name: `??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140032754`

## callees

- `0x1400028f4`
- `0x140002d6c`
- `0x140008168`
- `0x140008188`
- `0x1400322dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032340`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140032332`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400323a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140032332`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400323a3`

## string_xrefs

- `0x14003236c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1400323b2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1400323e8`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenAppContainerSid, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation((HANDLE)a2, TokenAppContainerSid, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x1400322dc  mov     [rsp+arg_8], rbx
0x1400322e1  mov     [rsp+arg_10], rsi
0x1400322e6  push    rdi
0x1400322e7  sub     rsp, 30h
0x1400322eb  mov     rbx, rcx
0x1400322ee  mov     rsi, rdx
0x1400322f1  mov     rcx, [rcx]; Block
0x1400322f4  mov     qword ptr [rbx], 0
0x1400322fb  test    rcx, rcx
0x1400322fe  jz      short loc_140032305
0x140032300  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032305  mov     rax, 0FFFFFFFFFFFFFFFAh
0x14003230c  mov     [rsp+38h+TokenInformationLength], 0
0x140032314  test    rsi, rsi
0x140032317  cmovz   rsi, rax
0x14003231b  xor     r9d, r9d; TokenInformationLength
0x14003231e  lea     rax, [rsp+38h+TokenInformationLength]
0x140032323  xor     r8d, r8d; TokenInformation
0x140032326  mov     rcx, rsi; TokenHandle
0x140032329  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x14003232e  lea     edx, [r9+1Fh]; TokenInformationClass
0x140032332  call    cs:__imp_GetTokenInformation
0x140032338  test    eax, eax
0x14003233a  jnz     loc_1400323E3
0x140032340  call    cs:__imp_GetLastError
0x140032346  cmp     eax, 7Ah ; 'z'
0x140032349  jnz     loc_1400323E3
0x14003234f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140032353  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003235a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003235f  mov     rdi, rax
0x140032362  test    rax, rax
0x140032365  jnz     short loc_140032389
0x140032367  mov     rcx, [rsp+38h]; this
0x14003236c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140032373  mov     ebx, 8007000Eh
0x140032378  mov     edx, 119h; void *
0x14003237d  mov     r9d, ebx; char *
0x140032380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032385  mov     eax, ebx
0x140032387  jmp     short loc_1400323F9
0x140032389  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14003238e  lea     rax, [rsp+38h+TokenInformationLength]
0x140032393  mov     r8, rdi; TokenInformation
0x140032396  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x14003239b  mov     edx, 1Fh; TokenInformationClass
0x1400323a0  mov     rcx, rsi; TokenHandle
0x1400323a3  call    cs:__imp_GetTokenInformation
0x1400323a9  test    eax, eax
0x1400323ab  jnz     short loc_1400323CF
0x1400323ad  mov     rcx, [rsp+38h]; this
0x1400323b2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400323b9  mov     edx, 11Ah; void *
0x1400323be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400323c3  mov     rcx, rdi; Block
0x1400323c6  mov     ebx, eax
0x1400323c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400323cd  jmp     short loc_140032385
0x1400323cf  mov     rcx, [rbx]; Block
0x1400323d2  mov     [rbx], rdi
0x1400323d5  test    rcx, rcx
0x1400323d8  jz      short loc_1400323DF
0x1400323da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400323df  xor     eax, eax
0x1400323e1  jmp     short loc_1400323F9
0x1400323e3  mov     rcx, [rsp+38h]; this
0x1400323e8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400323ef  mov     edx, 117h; void *
0x1400323f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400323f9  mov     rbx, [rsp+38h+arg_8]
0x1400323fe  mov     rsi, [rsp+38h+arg_10]
0x140032403  add     rsp, 30h
0x140032407  pop     rdi
0x140032408  retn
```
