# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800addd8`
- end: `0x1800adf26`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ac58c`
- `0x1800acf68`

## callees

- `0x180008618`
- `0x18000933c`
- `0x1800addd8`
- `0x1800f77b0`
- `0x1800f82f0`
- `0x1800f876c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ade4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ade4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ade3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800adeac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ade3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800adeac`

## string_xrefs

- `0x1800ade77`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`
- `0x1800adebb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`
- `0x1800adef8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  unsigned int LastError; // edi
  const char *v8; // r9
  void *v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( !a2 )
    a2 = -6;
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      if ( GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        v9 = *a1;
        *a1 = v6;
        if ( v9 )
          operator delete(v9);
        return 0;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\"
                                  "wil\\token_helpers.h",
                    v8);
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
    if ( v6 )
      operator delete(v6);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x117,
           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
           v5);
}

```

## disassembly

```asm
0x1800addd8  mov     [rsp+arg_10], rbx
0x1800adddd  mov     [rsp+arg_18], rsi
0x1800adde2  push    rdi
0x1800adde3  sub     rsp, 40h
0x1800adde7  mov     rax, cs:__security_cookie
0x1800addee  xor     rax, rsp
0x1800addf1  mov     [rsp+48h+var_10], rax
0x1800addf6  mov     rdi, rcx
0x1800addf9  mov     rsi, rdx
0x1800addfc  mov     rcx, [rcx]; Block
0x1800addff  mov     qword ptr [rdi], 0
0x1800ade06  test    rcx, rcx
0x1800ade09  jz      short loc_1800ADE10
0x1800ade0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ade10  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800ade17  mov     [rsp+48h+TokenInformationLength], 0
0x1800ade1f  test    rsi, rsi
0x1800ade22  cmovz   rsi, rax
0x1800ade26  xor     r9d, r9d; TokenInformationLength
0x1800ade29  lea     rax, [rsp+48h+TokenInformationLength]
0x1800ade2e  xor     r8d, r8d; TokenInformation
0x1800ade31  mov     rcx, rsi; TokenHandle
0x1800ade34  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800ade39  lea     edx, [r9+1]; TokenInformationClass
0x1800ade3d  call    cs:__imp_GetTokenInformation
0x1800ade43  test    eax, eax
0x1800ade45  jnz     loc_1800ADEF3
0x1800ade4b  call    cs:__imp_GetLastError
0x1800ade51  cmp     eax, 7Ah ; 'z'
0x1800ade54  jnz     loc_1800ADEF3
0x1800ade5a  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1800ade5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ade65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ade6a  mov     rbx, rax
0x1800ade6d  test    rax, rax
0x1800ade70  jnz     short loc_1800ADE92
0x1800ade72  mov     rcx, [rsp+48h]; this
0x1800ade77  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800ade7e  mov     edi, 8007000Eh
0x1800ade83  mov     edx, 119h; void *
0x1800ade88  mov     r9d, edi; char *
0x1800ade8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ade90  jmp     short loc_1800ADECE
0x1800ade92  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800ade97  lea     rax, [rsp+48h+TokenInformationLength]
0x1800ade9c  mov     r8, rbx; TokenInformation
0x1800ade9f  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x1800adea4  mov     edx, 1; TokenInformationClass
0x1800adea9  mov     rcx, rsi; TokenHandle
0x1800adeac  call    cs:__imp_GetTokenInformation
0x1800adeb2  test    eax, eax
0x1800adeb4  jnz     short loc_1800ADEDD
0x1800adeb6  mov     rcx, [rsp+48h]; this
0x1800adebb  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800adec2  mov     edx, 11Ah; void *
0x1800adec7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800adecc  mov     edi, eax
0x1800adece  test    rbx, rbx
0x1800aded1  jz      short loc_1800ADEEF
0x1800aded3  mov     rcx, rbx; Block
0x1800aded6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800adedb  jmp     short loc_1800ADEEF
0x1800adedd  mov     rcx, [rdi]; Block
0x1800adee0  mov     [rdi], rbx
0x1800adee3  test    rcx, rcx
0x1800adee6  jz      short loc_1800ADEED
0x1800adee8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800adeed  xor     edi, edi
0x1800adeef  mov     eax, edi
0x1800adef1  jmp     short loc_1800ADF09
0x1800adef3  mov     rcx, [rsp+48h]; this
0x1800adef8  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800adeff  mov     edx, 117h; void *
0x1800adf04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800adf09  mov     rcx, [rsp+48h+var_10]
0x1800adf0e  xor     rcx, rsp; StackCookie
0x1800adf11  call    __security_check_cookie
0x1800adf16  mov     rbx, [rsp+48h+arg_10]
0x1800adf1b  mov     rsi, [rsp+48h+arg_18]
0x1800adf20  add     rsp, 40h
0x1800adf24  pop     rdi
0x1800adf25  retn
```
