# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x180015410`
- end: `0x180015575`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001e114`

## callees

- `0x180015410`
- `0x180015608`
- `0x180015628`
- `0x18008c9bc`
- `0x1800a88a0`
- `0x1800a88c4`
- `0x1800a8d64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015474`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800154dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015474`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800154dd`

## string_xrefs

- `0x180015483`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180015524`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180015554`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18001553d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  const char *v4; // r9
  int LastError; // ebx
  void *v6; // rsi
  const char *v7; // r9
  void *v8; // rcx
  int ReturnLength; // [rsp+20h] [rbp-38h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  *a1 = 0;
  if ( !a2 )
    v2 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v4);
    goto LABEL_5;
  }
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
    goto LABEL_14;
  }
  if ( !GetTokenInformation((HANDLE)v2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
    operator delete(v6);
LABEL_5:
    if ( LastError >= 0 )
      return a1;
LABEL_14:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  }
  v8 = *a1;
  *a1 = v6;
  if ( v8 )
    operator delete(v8);
  return a1;
}

```

## disassembly

```asm
0x180015410  mov     [rsp+arg_10], rbx
0x180015415  mov     [rsp+arg_18], rsi
0x18001541a  push    rdi
0x18001541b  sub     rsp, 50h
0x18001541f  mov     rax, cs:__security_cookie
0x180015426  xor     rax, rsp
0x180015429  mov     [rsp+58h+var_10], rax
0x18001542e  mov     rbx, rdx
0x180015431  mov     rdi, rcx
0x180015434  mov     [rsp+58h+var_20], rcx
0x180015439  xor     ecx, ecx
0x18001543b  mov     [rsp+58h+var_28], ecx
0x18001543f  mov     [rsp+58h+var_28], 1
0x180015447  mov     [rdi], rcx
0x18001544a  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180015451  test    rdx, rdx
0x180015454  cmovz   rbx, rax
0x180015458  mov     [rsp+58h+TokenInformationLength], ecx
0x18001545c  lea     rax, [rsp+58h+TokenInformationLength]
0x180015461  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x180015466  xor     r9d, r9d; TokenInformationLength
0x180015469  xor     r8d, r8d; TokenInformation
0x18001546c  mov     edx, 1; TokenInformationClass
0x180015471  mov     rcx, rbx; TokenHandle
0x180015474  call    cs:__imp_GetTokenInformation
0x18001547a  test    eax, eax
0x18001547c  jz      short loc_1800154A0
0x18001547e  mov     rcx, [rsp+58h]; this
0x180015483  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001548a  mov     edx, 117h; void *
0x18001548f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015494  mov     ebx, eax
0x180015496  test    ebx, ebx
0x180015498  js      loc_180015535
0x18001549e  jmp     short loc_1800154F7
0x1800154a0  call    cs:__imp_GetLastError
0x1800154a6  cmp     eax, 7Ah ; 'z'
0x1800154a9  jnz     short loc_18001547E
0x1800154ab  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1800154af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800154b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800154bb  mov     rsi, rax
0x1800154be  test    rax, rax
0x1800154c1  jz      short loc_180015517
0x1800154c3  lea     rax, [rsp+58h+TokenInformationLength]
0x1800154c8  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x1800154cd  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800154d2  mov     r8, rsi; TokenInformation
0x1800154d5  mov     edx, 1; TokenInformationClass
0x1800154da  mov     rcx, rbx; TokenHandle
0x1800154dd  call    cs:__imp_GetTokenInformation
0x1800154e3  test    eax, eax
0x1800154e5  jz      short loc_18001554F
0x1800154e7  mov     rcx, [rdi]; Block
0x1800154ea  mov     [rdi], rsi
0x1800154ed  test    rcx, rcx
0x1800154f0  jz      short loc_1800154F7
0x1800154f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800154f7  mov     rax, rdi
0x1800154fa  mov     rcx, [rsp+58h+var_10]
0x1800154ff  xor     rcx, rsp; StackCookie
0x180015502  call    __security_check_cookie
0x180015507  mov     rbx, [rsp+58h+arg_10]
0x18001550c  mov     rsi, [rsp+58h+arg_18]
0x180015511  add     rsp, 50h
0x180015515  pop     rdi
0x180015516  retn
0x180015517  mov     rcx, [rsp+58h]; this
0x18001551c  mov     ebx, 8007000Eh
0x180015521  mov     r9d, ebx; char *
0x180015524  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001552b  mov     edx, 119h; void *
0x180015530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015535  mov     rcx, [rsp+58h]; this
0x18001553a  mov     r9d, ebx; char *
0x18001553d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015544  mov     edx, 1CBEh; void *
0x180015549  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001554f  mov     rcx, [rsp+58h]; this
0x180015554  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001555b  mov     edx, 11Ah; void *
0x180015560  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015565  mov     ebx, eax
0x180015567  mov     rcx, rsi; Block
0x18001556a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001556f  jmp     loc_180015496
```
