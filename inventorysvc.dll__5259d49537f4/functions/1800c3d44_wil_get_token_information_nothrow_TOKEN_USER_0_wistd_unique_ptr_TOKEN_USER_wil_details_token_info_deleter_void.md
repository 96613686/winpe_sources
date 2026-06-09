# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800c3d44`
- end: `0x1800c3e71`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c4840`

## callees

- `0x180003668`
- `0x18000514c`
- `0x18000ec34`
- `0x18000ec54`
- `0x1800c3d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3da8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3d9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3e0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3d9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3e0b`

## string_xrefs

- `0x1800c3dd4`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800c3e1a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800c3e50`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
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
0x1800c3d44  mov     [rsp+arg_8], rbx
0x1800c3d49  mov     [rsp+arg_10], rsi
0x1800c3d4e  push    rdi
0x1800c3d4f  sub     rsp, 30h
0x1800c3d53  mov     rbx, rcx
0x1800c3d56  mov     rsi, rdx
0x1800c3d59  mov     rcx, [rcx]; Block
0x1800c3d5c  mov     qword ptr [rbx], 0
0x1800c3d63  test    rcx, rcx
0x1800c3d66  jz      short loc_1800C3D6D
0x1800c3d68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c3d6d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800c3d74  mov     [rsp+38h+TokenInformationLength], 0
0x1800c3d7c  test    rsi, rsi
0x1800c3d7f  cmovz   rsi, rax
0x1800c3d83  xor     r9d, r9d; TokenInformationLength
0x1800c3d86  lea     rax, [rsp+38h+TokenInformationLength]
0x1800c3d8b  xor     r8d, r8d; TokenInformation
0x1800c3d8e  mov     rcx, rsi; TokenHandle
0x1800c3d91  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800c3d96  lea     edx, [r9+1]; TokenInformationClass
0x1800c3d9a  call    cs:__imp_GetTokenInformation
0x1800c3da0  test    eax, eax
0x1800c3da2  jnz     loc_1800C3E4B
0x1800c3da8  call    cs:__imp_GetLastError
0x1800c3dae  cmp     eax, 7Ah ; 'z'
0x1800c3db1  jnz     loc_1800C3E4B
0x1800c3db7  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800c3dbb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c3dc2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c3dc7  mov     rdi, rax
0x1800c3dca  test    rax, rax
0x1800c3dcd  jnz     short loc_1800C3DF1
0x1800c3dcf  mov     rcx, [rsp+38h]; this
0x1800c3dd4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c3ddb  mov     ebx, 8007000Eh
0x1800c3de0  mov     edx, 119h; void *
0x1800c3de5  mov     r9d, ebx; char *
0x1800c3de8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3ded  mov     eax, ebx
0x1800c3def  jmp     short loc_1800C3E61
0x1800c3df1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800c3df6  lea     rax, [rsp+38h+TokenInformationLength]
0x1800c3dfb  mov     r8, rdi; TokenInformation
0x1800c3dfe  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800c3e03  mov     edx, 1; TokenInformationClass
0x1800c3e08  mov     rcx, rsi; TokenHandle
0x1800c3e0b  call    cs:__imp_GetTokenInformation
0x1800c3e11  test    eax, eax
0x1800c3e13  jnz     short loc_1800C3E37
0x1800c3e15  mov     rcx, [rsp+38h]; this
0x1800c3e1a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c3e21  mov     edx, 11Ah; void *
0x1800c3e26  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c3e2b  mov     rcx, rdi; Block
0x1800c3e2e  mov     ebx, eax
0x1800c3e30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c3e35  jmp     short loc_1800C3DED
0x1800c3e37  mov     rcx, [rbx]; Block
0x1800c3e3a  mov     [rbx], rdi
0x1800c3e3d  test    rcx, rcx
0x1800c3e40  jz      short loc_1800C3E47
0x1800c3e42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c3e47  xor     eax, eax
0x1800c3e49  jmp     short loc_1800C3E61
0x1800c3e4b  mov     rcx, [rsp+38h]; this
0x1800c3e50  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c3e57  mov     edx, 117h; void *
0x1800c3e5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c3e61  mov     rbx, [rsp+38h+arg_8]
0x1800c3e66  mov     rsi, [rsp+38h+arg_10]
0x1800c3e6b  add     rsp, 30h
0x1800c3e6f  pop     rdi
0x1800c3e70  retn
```
