# GetAppContainerSid(void *,void * *)

- ea: `0x140032754`
- end: `0x14003287a`
- name: `?GetAppContainerSid@@YAJPEAXPEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002dd30`

## callees

- `0x140008168`
- `0x140008188`
- `0x1400322c8`
- `0x1400322dc`
- `0x140032668`
- `0x1400326b0`
- `0x140032754`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400327ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400327ca`

## string_xrefs

- `0x140032776`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`
- `0x140032845`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`
- `0x1400327d9`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall GetAppContainerSid(__int64 a1, void **a2)
{
  __int64 v3; // rbx
  unsigned int LastError; // ebx
  __int64 v5; // rdx
  const char *v7; // r9
  int token_information; // eax
  __int64 v9; // rdx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PSID *TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD v13; // [rsp+50h] [rbp+18h] BYREF

  v3 = a1;
  if ( !a2 )
  {
    LastError = -2147024809;
    v5 = 66;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
      (const char *)LastError,
      ReturnLength);
    return LastError;
  }
  *a2 = 0;
  LODWORD(TokenInformation) = 0;
  v13 = 0;
  if ( !a1 )
    a1 = -6;
  if ( GetTokenInformation((HANDLE)a1, TokenIsAppContainer, &TokenInformation, 4u, &v13) )
  {
    if ( (_DWORD)TokenInformation )
    {
      wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter>::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter>(&TokenInformation);
      token_information = wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(&TokenInformation, v3);
      LastError = token_information;
      if ( token_information >= 0 )
      {
        token_information = CreateCopyOfSid(*TokenInformation, a2);
        LastError = token_information;
        if ( token_information >= 0 )
        {
          wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(&TokenInformation);
          return 0;
        }
        v9 = 78;
      }
      else
      {
        v9 = 76;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
        (const char *)(unsigned int)token_information,
        ReturnLength);
      wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(&TokenInformation);
      return LastError;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x298,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    if ( (LastError & 0x80000000) != 0 )
    {
      v5 = 71;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140032754  mov     [rsp+arg_0], rbx
0x140032759  push    rdi
0x14003275a  sub     rsp, 30h
0x14003275e  mov     rdi, rdx
0x140032761  mov     rbx, rcx
0x140032764  test    rdx, rdx
0x140032767  jnz     short loc_14003278C
0x140032769  mov     ebx, 80070057h
0x14003276e  lea     edx, [rdi+42h]; void *
0x140032771  mov     rcx, [rsp+38h]; this
0x140032776  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14003277d  mov     r9d, ebx; char *
0x140032780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032785  mov     eax, ebx
0x140032787  jmp     loc_14003286F
0x14003278c  mov     r9d, 4; TokenInformationLength
0x140032792  mov     qword ptr [rdx], 0
0x140032799  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1400327a0  mov     dword ptr [rsp+38h+TokenInformation], 0
0x1400327a8  test    rbx, rbx
0x1400327ab  mov     [rsp+38h+arg_10], 0
0x1400327b3  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1400327b8  cmovz   rcx, rax; TokenHandle
0x1400327bc  lea     edx, [r9+19h]; TokenInformationClass
0x1400327c0  lea     rax, [rsp+38h+arg_10]
0x1400327c5  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1400327ca  call    cs:__imp_GetTokenInformation
0x1400327d0  test    eax, eax
0x1400327d2  jnz     short loc_1400327FA
0x1400327d4  mov     rcx, [rsp+38h]; this
0x1400327d9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400327e0  mov     edx, 298h; void *
0x1400327e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400327ea  mov     ebx, eax
0x1400327ec  test    eax, eax
0x1400327ee  jns     short loc_14003286D
0x1400327f0  mov     edx, 47h ; 'G'
0x1400327f5  jmp     loc_140032771
0x1400327fa  cmp     dword ptr [rsp+38h+TokenInformation], 0
0x1400327ff  jz      short loc_14003286D
0x140032801  lea     rcx, [rsp+38h+TokenInformation]
0x140032806  call    ??$?0$00X@?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter>::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter>(void)
0x14003280b  mov     rdx, rbx
0x14003280e  lea     rcx, [rsp+38h+TokenInformation]
0x140032813  call    ??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)
0x140032818  mov     ebx, eax
0x14003281a  test    eax, eax
0x14003281c  jns     short loc_140032825
0x14003281e  mov     edx, 4Ch ; 'L'
0x140032823  jmp     short loc_140032840
0x140032825  mov     rcx, [rsp+38h+TokenInformation]
0x14003282a  mov     rdx, rdi; void **
0x14003282d  mov     rcx, [rcx]; pSourceSid
0x140032830  call    ?CreateCopyOfSid@@YAJPEAXPEAPEAX@Z; CreateCopyOfSid(void *,void * *)
0x140032835  mov     ebx, eax
0x140032837  test    eax, eax
0x140032839  jns     short loc_140032863
0x14003283b  mov     edx, 4Eh ; 'N'; void *
0x140032840  mov     rcx, [rsp+38h]; this
0x140032845  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14003284c  mov     r9d, eax; char *
0x14003284f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032854  lea     rcx, [rsp+38h+TokenInformation]
0x140032859  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(void)
0x14003285e  jmp     loc_140032785
0x140032863  lea     rcx, [rsp+38h+TokenInformation]
0x140032868  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(void)
0x14003286d  xor     eax, eax
0x14003286f  mov     rbx, [rsp+38h+arg_0]
0x140032874  add     rsp, 30h
0x140032878  pop     rdi
0x140032879  retn
```
