# IsTokenIntegrityLevelLessThanMedium(void *)

- ea: `0x18001bbd8`
- end: `0x18001bd2d`
- name: `?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z`
- size: `341`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800182f4`

## callees

- `0x180005fac`
- `0x18000937c`
- `0x18000e214`
- `0x18000e234`
- `0x180010a84`
- `0x18001bbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc97`

## string_xrefs

- `0x18001bd1b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001bc6a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001bcac`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001bcda`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsTokenIntegrityLevelLessThanMedium(__int64 a1)
{
  __int64 v1; // rdi
  void *v2; // rbx
  const char *v3; // r9
  void *v4; // rsi
  int LastError; // edi
  const char *v6; // r9
  bool v7; // di
  int ReturnLength; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h]
  void *v13; // [rsp+60h] [rbp+18h]

  v1 = a1;
  v12 = 2;
  v2 = 0;
  v13 = 0;
  if ( !a1 )
    v1 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v1, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v3);
  }
  else
  {
    v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
    {
      if ( GetTokenInformation((HANDLE)v1, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
      {
        v2 = v4;
        v13 = v4;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  v7 = *(_DWORD *)(*(_QWORD *)v2 + 8LL) < 0x2000;
  operator delete(v2);
  return v7;
}

```

## disassembly

```asm
0x18001bbd8  push    rbx
0x18001bbda  push    rsi
0x18001bbdb  push    rdi
0x18001bbdc  sub     rsp, 30h
0x18001bbe0  mov     rdi, rcx
0x18001bbe3  and     [rsp+48h+arg_8], 0
0x18001bbe8  mov     [rsp+48h+arg_8], 2
0x18001bbf0  xor     ebx, ebx
0x18001bbf2  mov     [rsp+48h+arg_10], rbx
0x18001bbf7  lea     rax, [rbx-6]
0x18001bbfb  test    rcx, rcx
0x18001bbfe  cmovz   rdi, rax
0x18001bc02  and     [rsp+48h+TokenInformationLength], ebx
0x18001bc06  lea     rax, [rsp+48h+TokenInformationLength]
0x18001bc0b  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18001bc10  xor     r9d, r9d; TokenInformationLength
0x18001bc13  xor     r8d, r8d; TokenInformation
0x18001bc16  lea     edx, [rbx+19h]; TokenInformationClass
0x18001bc19  mov     rcx, rdi; TokenHandle
0x18001bc1c  call    cs:__imp_GetTokenInformation
0x18001bc23  nop     dword ptr [rax+rax+00h]
0x18001bc28  test    eax, eax
0x18001bc2a  jnz     loc_18001BCD5
0x18001bc30  call    cs:__imp_GetLastError
0x18001bc37  nop     dword ptr [rax+rax+00h]
0x18001bc3c  cmp     eax, 7Ah ; 'z'
0x18001bc3f  jnz     loc_18001BCD5
0x18001bc45  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18001bc49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bc50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bc55  mov     rsi, rax
0x18001bc58  test    rax, rax
0x18001bc5b  jnz     short loc_18001BC7D
0x18001bc5d  mov     rcx, [rsp+48h]; this
0x18001bc62  mov     edi, 8007000Eh
0x18001bc67  mov     r9d, edi; char *
0x18001bc6a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bc71  mov     edx, 119h; void *
0x18001bc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc7b  jmp     short loc_18001BCED
0x18001bc7d  lea     rax, [rsp+48h+TokenInformationLength]
0x18001bc82  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x18001bc87  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001bc8c  mov     r8, rsi; TokenInformation
0x18001bc8f  mov     edx, 19h; TokenInformationClass
0x18001bc94  mov     rcx, rdi; TokenHandle
0x18001bc97  call    cs:__imp_GetTokenInformation
0x18001bc9e  nop     dword ptr [rax+rax+00h]
0x18001bca3  test    eax, eax
0x18001bca5  jnz     short loc_18001BCC9
0x18001bca7  mov     rcx, [rsp+48h]; this
0x18001bcac  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bcb3  mov     edx, 11Ah; void *
0x18001bcb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bcbd  mov     edi, eax
0x18001bcbf  mov     rcx, rsi; Block
0x18001bcc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bcc7  jmp     short loc_18001BCED
0x18001bcc9  mov     rbx, rsi
0x18001bccc  mov     [rsp+48h+arg_10], rbx
0x18001bcd1  xor     edi, edi
0x18001bcd3  jmp     short loc_18001BCED
0x18001bcd5  mov     rcx, [rsp+48h]; this
0x18001bcda  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bce1  mov     edx, 117h; void *
0x18001bce6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bceb  mov     edi, eax
0x18001bced  mov     rcx, [rsp+48h]; this
0x18001bcf2  test    edi, edi
0x18001bcf4  js      short loc_18001BD18
0x18001bcf6  mov     rax, [rbx]
0x18001bcf9  cmp     dword ptr [rax+8], 2000h
0x18001bd00  setl    dil
0x18001bd04  mov     rcx, rbx; Block
0x18001bd07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bd0c  mov     al, dil
0x18001bd0f  add     rsp, 30h
0x18001bd13  pop     rdi
0x18001bd14  pop     rsi
0x18001bd15  pop     rbx
0x18001bd16  retn
0x18001bd18  mov     r9d, edi; char *
0x18001bd1b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bd22  mov     edx, 1C60h; void *
0x18001bd27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
