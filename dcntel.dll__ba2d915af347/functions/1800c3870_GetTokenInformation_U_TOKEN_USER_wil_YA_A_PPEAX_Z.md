# ??$GetTokenInformation@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z

- ea: `0x1800c3870`
- end: `0x1800c39b9`
- name: `??$GetTokenInformation@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z`
- size: `329`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c4bc4`
- `0x1800c52e4`

## callees

- `0x180008da4`
- `0x1800097d0`
- `0x180011cc4`
- `0x180011ce4`
- `0x180030554`
- `0x1800c3870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c38c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3930`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c38c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3930`

## string_xrefs

- `0x1800c39a7`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800c3902`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800c393f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800c3975`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
void **__fastcall wil::GetTokenInformation<_TOKEN_USER>(void **a1, __int64 a2)
{
  const char *v3; // r9
  void *v4; // rsi
  int LastError; // ebx
  const char *v6; // r9
  void *v7; // rcx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+5Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  *a1 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v3);
  }
  else
  {
    v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
    {
      if ( GetTokenInformation(
             (HANDLE)0xFFFFFFFFFFFFFFFALL,
             TokenUser,
             v4,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        v7 = *a1;
        *a1 = v4;
        if ( v7 )
          operator delete(v7);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                      v6);
        operator delete(v4);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  return a1;
}

```

## disassembly

```asm
0x1800c3870  mov     rax, rsp
0x1800c3873  mov     [rax+18h], rbx
0x1800c3877  mov     [rax+20h], rsi
0x1800c387b  mov     [rax+10h], rdx
0x1800c387f  mov     [rax+8], rcx
0x1800c3883  push    rdi
0x1800c3884  sub     rsp, 40h
0x1800c3888  mov     rdi, rcx
0x1800c388b  mov     dword ptr [rax-18h], 0
0x1800c3892  mov     dword ptr [rax-18h], 4
0x1800c3899  mov     qword ptr [rcx], 0
0x1800c38a0  mov     dword ptr [rax+10h], 0
0x1800c38a7  lea     rax, [rax+10h]
0x1800c38ab  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800c38b0  xor     r9d, r9d; TokenInformationLength
0x1800c38b3  xor     r8d, r8d; TokenInformation
0x1800c38b6  lea     ebx, [r9+1]
0x1800c38ba  mov     edx, ebx; TokenInformationClass
0x1800c38bc  lea     rcx, [r9-6]; TokenHandle
0x1800c38c0  call    cs:__imp_GetTokenInformation
0x1800c38c6  test    eax, eax
0x1800c38c8  jnz     loc_1800C3970
0x1800c38ce  call    cs:__imp_GetLastError
0x1800c38d4  cmp     eax, 7Ah ; 'z'
0x1800c38d7  jnz     loc_1800C3970
0x1800c38dd  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1800c38e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c38e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c38ed  mov     rsi, rax
0x1800c38f0  test    rax, rax
0x1800c38f3  jnz     short loc_1800C3915
0x1800c38f5  mov     rcx, [rsp+48h]; this
0x1800c38fa  mov     ebx, 8007000Eh
0x1800c38ff  mov     r9d, ebx; char *
0x1800c3902  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c3909  mov     edx, 119h; void *
0x1800c390e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3913  jmp     short loc_1800C3988
0x1800c3915  lea     rax, [rsp+48h+TokenInformationLength]
0x1800c391a  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x1800c391f  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800c3924  mov     r8, rsi; TokenInformation
0x1800c3927  mov     edx, ebx; TokenInformationClass
0x1800c3929  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800c3930  call    cs:__imp_GetTokenInformation
0x1800c3936  test    eax, eax
0x1800c3938  jnz     short loc_1800C395C
0x1800c393a  mov     rcx, [rsp+48h]; this
0x1800c393f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c3946  mov     edx, 11Ah; void *
0x1800c394b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c3950  mov     ebx, eax
0x1800c3952  mov     rcx, rsi; Block
0x1800c3955  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c395a  jmp     short loc_1800C3988
0x1800c395c  mov     rcx, [rdi]; Block
0x1800c395f  mov     [rdi], rsi
0x1800c3962  test    rcx, rcx
0x1800c3965  jz      short loc_1800C396C
0x1800c3967  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c396c  xor     ebx, ebx
0x1800c396e  jmp     short loc_1800C3988
0x1800c3970  mov     rcx, [rsp+48h]; this
0x1800c3975  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c397c  mov     edx, 117h; void *
0x1800c3981  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c3986  mov     ebx, eax
0x1800c3988  mov     rcx, [rsp+48h]; this
0x1800c398d  test    ebx, ebx
0x1800c398f  js      short loc_1800C39A4
0x1800c3991  mov     rax, rdi
0x1800c3994  mov     rbx, [rsp+48h+arg_10]
0x1800c3999  mov     rsi, [rsp+48h+arg_18]
0x1800c399e  add     rsp, 40h
0x1800c39a2  pop     rdi
0x1800c39a3  retn
0x1800c39a4  mov     r9d, ebx; char *
0x1800c39a7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c39ae  mov     edx, 1CBEh; void *
0x1800c39b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
