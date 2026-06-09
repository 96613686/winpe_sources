# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18004632c`
- end: `0x180046448`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180094c9c`

## callees

- `0x18000395c`
- `0x180003968`
- `0x180008524`
- `0x180008544`
- `0x18004632c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046380`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046372`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800463e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046372`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800463e7`

## string_xrefs

- `0x1800463ac`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800463f6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18004642c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  void *v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = a2;
  v3 = *a1;
  *a1 = 0;
  if ( v3 )
    operator delete(v3);
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
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
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenUser,
          v5,
          TokenInformationLength,
          (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v8);
    operator delete(v5);
    return LastError;
  }
  v9 = *a1;
  *a1 = v5;
  if ( v9 )
    operator delete(v9);
  return 0;
}

```

## disassembly

```asm
0x18004632c  mov     [rsp+arg_0], rbx
0x180046331  mov     [rsp+TokenInformationLength], rdx
0x180046336  push    rdi
0x180046337  sub     rsp, 30h
0x18004633b  mov     rbx, rcx
0x18004633e  mov     rcx, [rcx]; Block
0x180046341  mov     qword ptr [rbx], 0
0x180046348  test    rcx, rcx
0x18004634b  jz      short loc_180046352
0x18004634d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046352  xor     r9d, r9d; TokenInformationLength
0x180046355  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x18004635d  lea     rax, [rsp+38h+TokenInformationLength]
0x180046362  xor     r8d, r8d; TokenInformation
0x180046365  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18004636a  lea     edx, [r9+1]; TokenInformationClass
0x18004636e  lea     rcx, [r9-6]; TokenHandle
0x180046372  call    cs:__imp_GetTokenInformation
0x180046378  test    eax, eax
0x18004637a  jnz     loc_180046427
0x180046380  call    cs:__imp_GetLastError
0x180046386  cmp     eax, 7Ah ; 'z'
0x180046389  jnz     loc_180046427
0x18004638f  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x180046393  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004639a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004639f  mov     rdi, rax
0x1800463a2  test    rax, rax
0x1800463a5  jnz     short loc_1800463C9
0x1800463a7  mov     rcx, [rsp+38h]; this
0x1800463ac  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800463b3  mov     ebx, 8007000Eh
0x1800463b8  mov     edx, 119h; void *
0x1800463bd  mov     r9d, ebx; char *
0x1800463c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800463c5  mov     eax, ebx
0x1800463c7  jmp     short loc_18004643D
0x1800463c9  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800463ce  lea     rax, [rsp+38h+TokenInformationLength]
0x1800463d3  mov     r8, rdi; TokenInformation
0x1800463d6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800463db  mov     edx, 1; TokenInformationClass
0x1800463e0  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800463e7  call    cs:__imp_GetTokenInformation
0x1800463ed  test    eax, eax
0x1800463ef  jnz     short loc_180046413
0x1800463f1  mov     rcx, [rsp+38h]; this
0x1800463f6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800463fd  mov     edx, 11Ah; void *
0x180046402  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046407  mov     rcx, rdi; Block
0x18004640a  mov     ebx, eax
0x18004640c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046411  jmp     short loc_1800463C5
0x180046413  mov     rcx, [rbx]; Block
0x180046416  mov     [rbx], rdi
0x180046419  test    rcx, rcx
0x18004641c  jz      short loc_180046423
0x18004641e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046423  xor     eax, eax
0x180046425  jmp     short loc_18004643D
0x180046427  mov     rcx, [rsp+38h]; this
0x18004642c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046433  mov     edx, 117h; void *
0x180046438  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004643d  mov     rbx, [rsp+38h+arg_0]
0x180046442  add     rsp, 30h
0x180046446  pop     rdi
0x180046447  retn
```
