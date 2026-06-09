# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x140032534`
- end: `0x140032661`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140032880`

## callees

- `0x1400028f4`
- `0x140002d6c`
- `0x140008168`
- `0x140008188`
- `0x140032534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032598`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003258a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400325fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003258a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400325fb`

## string_xrefs

- `0x1400325c4`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x14003260a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x140032640`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
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
0x140032534  mov     [rsp+arg_8], rbx
0x140032539  mov     [rsp+arg_10], rsi
0x14003253e  push    rdi
0x14003253f  sub     rsp, 30h
0x140032543  mov     rbx, rcx
0x140032546  mov     rsi, rdx
0x140032549  mov     rcx, [rcx]; Block
0x14003254c  mov     qword ptr [rbx], 0
0x140032553  test    rcx, rcx
0x140032556  jz      short loc_14003255D
0x140032558  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003255d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x140032564  mov     [rsp+38h+TokenInformationLength], 0
0x14003256c  test    rsi, rsi
0x14003256f  cmovz   rsi, rax
0x140032573  xor     r9d, r9d; TokenInformationLength
0x140032576  lea     rax, [rsp+38h+TokenInformationLength]
0x14003257b  xor     r8d, r8d; TokenInformation
0x14003257e  mov     rcx, rsi; TokenHandle
0x140032581  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140032586  lea     edx, [r9+19h]; TokenInformationClass
0x14003258a  call    cs:__imp_GetTokenInformation
0x140032590  test    eax, eax
0x140032592  jnz     loc_14003263B
0x140032598  call    cs:__imp_GetLastError
0x14003259e  cmp     eax, 7Ah ; 'z'
0x1400325a1  jnz     loc_14003263B
0x1400325a7  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1400325ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400325b2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400325b7  mov     rdi, rax
0x1400325ba  test    rax, rax
0x1400325bd  jnz     short loc_1400325E1
0x1400325bf  mov     rcx, [rsp+38h]; this
0x1400325c4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400325cb  mov     ebx, 8007000Eh
0x1400325d0  mov     edx, 119h; void *
0x1400325d5  mov     r9d, ebx; char *
0x1400325d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400325dd  mov     eax, ebx
0x1400325df  jmp     short loc_140032651
0x1400325e1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1400325e6  lea     rax, [rsp+38h+TokenInformationLength]
0x1400325eb  mov     r8, rdi; TokenInformation
0x1400325ee  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1400325f3  mov     edx, 19h; TokenInformationClass
0x1400325f8  mov     rcx, rsi; TokenHandle
0x1400325fb  call    cs:__imp_GetTokenInformation
0x140032601  test    eax, eax
0x140032603  jnz     short loc_140032627
0x140032605  mov     rcx, [rsp+38h]; this
0x14003260a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140032611  mov     edx, 11Ah; void *
0x140032616  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003261b  mov     rcx, rdi; Block
0x14003261e  mov     ebx, eax
0x140032620  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032625  jmp     short loc_1400325DD
0x140032627  mov     rcx, [rbx]; Block
0x14003262a  mov     [rbx], rdi
0x14003262d  test    rcx, rcx
0x140032630  jz      short loc_140032637
0x140032632  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032637  xor     eax, eax
0x140032639  jmp     short loc_140032651
0x14003263b  mov     rcx, [rsp+38h]; this
0x140032640  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140032647  mov     edx, 117h; void *
0x14003264c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140032651  mov     rbx, [rsp+38h+arg_8]
0x140032656  mov     rsi, [rsp+38h+arg_10]
0x14003265b  add     rsp, 30h
0x14003265f  pop     rdi
0x140032660  retn
```
