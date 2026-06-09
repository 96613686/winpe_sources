# wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_GROUPS_AND_PRIVILEGES,wil::details::token_info_deleter> &,void *)

- ea: `0x140032410`
- end: `0x14003252c`
- name: `??$get_token_information_nothrow@U_TOKEN_GROUPS_AND_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_GROUPS_AND_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003292c`

## callees

- `0x1400028f4`
- `0x140002d6c`
- `0x140008168`
- `0x140008188`
- `0x140032410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032464`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140032456`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400324cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140032456`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400324cb`

## string_xrefs

- `0x140032490`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1400324da`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x140032510`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation(
         (HANDLE)0xFFFFFFFFFFFFFFFALL,
         TokenGroupsAndPrivileges,
         0,
         0,
         (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
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
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenGroupsAndPrivileges,
          v5,
          TokenInformationLength,
          (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x140032410  mov     [rsp+arg_0], rbx
0x140032415  mov     [rsp+TokenInformationLength], rdx
0x14003241a  push    rdi
0x14003241b  sub     rsp, 30h
0x14003241f  mov     rbx, rcx
0x140032422  mov     rcx, [rcx]; Block
0x140032425  mov     qword ptr [rbx], 0
0x14003242c  test    rcx, rcx
0x14003242f  jz      short loc_140032436
0x140032431  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032436  xor     r9d, r9d; TokenInformationLength
0x140032439  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x140032441  lea     rax, [rsp+38h+TokenInformationLength]
0x140032446  xor     r8d, r8d; TokenInformation
0x140032449  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x14003244e  lea     edx, [r9+0Dh]; TokenInformationClass
0x140032452  lea     rcx, [r9-6]; TokenHandle
0x140032456  call    cs:__imp_GetTokenInformation
0x14003245c  test    eax, eax
0x14003245e  jnz     loc_14003250B
0x140032464  call    cs:__imp_GetLastError
0x14003246a  cmp     eax, 7Ah ; 'z'
0x14003246d  jnz     loc_14003250B
0x140032473  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x140032477  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003247e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140032483  mov     rdi, rax
0x140032486  test    rax, rax
0x140032489  jnz     short loc_1400324AD
0x14003248b  mov     rcx, [rsp+38h]; this
0x140032490  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140032497  mov     ebx, 8007000Eh
0x14003249c  mov     edx, 119h; void *
0x1400324a1  mov     r9d, ebx; char *
0x1400324a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400324a9  mov     eax, ebx
0x1400324ab  jmp     short loc_140032521
0x1400324ad  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1400324b2  lea     rax, [rsp+38h+TokenInformationLength]
0x1400324b7  mov     r8, rdi; TokenInformation
0x1400324ba  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1400324bf  mov     edx, 0Dh; TokenInformationClass
0x1400324c4  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1400324cb  call    cs:__imp_GetTokenInformation
0x1400324d1  test    eax, eax
0x1400324d3  jnz     short loc_1400324F7
0x1400324d5  mov     rcx, [rsp+38h]; this
0x1400324da  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400324e1  mov     edx, 11Ah; void *
0x1400324e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400324eb  mov     rcx, rdi; Block
0x1400324ee  mov     ebx, eax
0x1400324f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400324f5  jmp     short loc_1400324A9
0x1400324f7  mov     rcx, [rbx]; Block
0x1400324fa  mov     [rbx], rdi
0x1400324fd  test    rcx, rcx
0x140032500  jz      short loc_140032507
0x140032502  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032507  xor     eax, eax
0x140032509  jmp     short loc_140032521
0x14003250b  mov     rcx, [rsp+38h]; this
0x140032510  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140032517  mov     edx, 117h; void *
0x14003251c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140032521  mov     rbx, [rsp+38h+arg_0]
0x140032526  add     rsp, 30h
0x14003252a  pop     rdi
0x14003252b  retn
```
