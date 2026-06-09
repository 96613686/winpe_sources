# IsUserAnAdminMember(void *)

- ea: `0x18001dc00`
- end: `0x18001de13`
- name: `?IsUserAnAdminMember@@YAHPEAX@Z`
- size: `531`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d530`
- `0x18001db10`
- `0x18002ef18`

## callees

- `0x1800084bc`
- `0x18001dc00`
- `0x18002df48`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003bc70`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ddcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ddcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de02`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001dca8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001dca8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001dcc3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001dcc3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001dc67`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001dc67`
- `ntdll!RtlFreeSid` at `0x18001dcf2`
- `ntdll!RtlFreeSid` at `0x18001dd68`
- `ntdll!RtlFreeSid` at `0x18001ddbe`
- `ntdll!RtlFreeSid` at `0x18001dcf2`
- `ntdll!RtlFreeSid` at `0x18001dd68`
- `ntdll!RtlFreeSid` at `0x18001ddbe`

## string_xrefs

- `0x18001dd1e`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001dd4b`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001dd78`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001dd95`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001dde1`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAnAdminMember(HANDLE hExistingToken)
{
  NTSTATUS v2; // eax
  PSID v3; // rdi
  const char *v4; // r9
  const char *v5; // r9
  int LastError; // ebx
  ULONG SubAuthority2; // [rsp+20h] [rbp-39h]
  ULONG SubAuthority2a; // [rsp+20h] [rbp-39h]
  ULONG SubAuthority2b; // [rsp+20h] [rbp-39h]
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  void *phNewToken; // [rsp+68h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  SidToCheck = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( v2 >= 0 )
  {
    v3 = SidToCheck;
    IsMember = 0;
    phNewToken = 0;
    if ( DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      if ( CheckTokenMembership(phNewToken, v3, &IsMember) )
      {
        if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phNewToken);
        goto LABEL_6;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5F,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                    v5);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5A,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                    v4);
      if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phNewToken);
    }
    if ( LastError >= 0 )
    {
LABEL_6:
      if ( SidToCheck )
        RtlFreeSid(SidToCheck);
      return (unsigned int)IsMember;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)LastError,
      SubAuthority2a);
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
LABEL_14:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)LastError,
      SubAuthority2b);
    return (unsigned int)IsMember;
  }
  LastError = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                (const char *)(unsigned int)v2,
                SubAuthority2);
  if ( SidToCheck )
    RtlFreeSid(SidToCheck);
  if ( LastError < 0 )
    goto LABEL_14;
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18001dc00  push    rbp
0x18001dc02  push    rbx
0x18001dc03  push    rsi
0x18001dc04  push    rdi
0x18001dc05  lea     rbp, [rsp-3Fh]
0x18001dc0a  sub     rsp, 98h
0x18001dc11  mov     rax, cs:__security_cookie
0x18001dc18  xor     rax, rsp
0x18001dc1b  mov     [rbp+57h+var_30], rax
0x18001dc1f  xor     esi, esi
0x18001dc21  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18001dc27  lea     rax, [rbp+57h+SidToCheck]
0x18001dc2b  mov     [rbp+57h+IsMember], esi
0x18001dc2e  mov     [rsp+0B0h+Sid], rax; Sid
0x18001dc33  mov     rbx, rcx
0x18001dc36  mov     [rsp+0B0h+SubAuthority7], esi; SubAuthority7
0x18001dc3a  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18001dc3e  mov     [rsp+0B0h+SubAuthority6], esi; SubAuthority6
0x18001dc42  mov     r9d, 220h; SubAuthority1
0x18001dc48  mov     [rsp+0B0h+SubAuthority5], esi; SubAuthority5
0x18001dc4c  mov     r8d, 20h ; ' '; SubAuthority0
0x18001dc52  mov     [rsp+0B0h+SubAuthority4], esi; SubAuthority4
0x18001dc56  mov     dl, 2; SubAuthorityCount
0x18001dc58  mov     [rsp+0B0h+SubAuthority3], esi; SubAuthority3
0x18001dc5c  mov     [rsp+0B0h+SubAuthority2], esi; int
0x18001dc60  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x18001dc63  mov     [rbp+57h+SidToCheck], rsi
0x18001dc67  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001dc6e  nop     dword ptr [rax+rax+00h]
0x18001dc73  test    eax, eax
0x18001dc75  js      loc_18001DD91
0x18001dc7b  mov     rdi, [rbp+57h+SidToCheck]
0x18001dc7f  lea     rax, [rbp+57h+phNewToken]
0x18001dc83  mov     qword ptr [rsp+0B0h+SubAuthority3], rax; phNewToken
0x18001dc88  mov     r9d, 2; ImpersonationLevel
0x18001dc8e  xor     r8d, r8d; lpTokenAttributes
0x18001dc91  mov     [rsp+0B0h+SubAuthority2], 2; int
0x18001dc99  mov     edx, 0Ch; dwDesiredAccess
0x18001dc9e  mov     [rbp+57h+IsMember], esi
0x18001dca1  mov     rcx, rbx; hExistingToken
0x18001dca4  mov     [rbp+57h+phNewToken], rsi
0x18001dca8  call    cs:__imp_DuplicateTokenEx
0x18001dcaf  nop     dword ptr [rax+rax+00h]
0x18001dcb4  test    eax, eax
0x18001dcb6  jz      short loc_18001DD1A
0x18001dcb8  mov     rcx, [rbp+57h+phNewToken]; TokenHandle
0x18001dcbc  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001dcc0  mov     rdx, rdi; SidToCheck
0x18001dcc3  call    cs:__imp_CheckTokenMembership
0x18001dcca  nop     dword ptr [rax+rax+00h]
0x18001dccf  test    eax, eax
0x18001dcd1  jz      loc_18001DDDD
0x18001dcd7  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18001dcdb  lea     rax, [rcx-1]
0x18001dcdf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001dce3  jbe     loc_18001DE02
0x18001dce9  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001dced  test    rcx, rcx
0x18001dcf0  jz      short loc_18001DCFE
0x18001dcf2  call    cs:__imp_RtlFreeSid
0x18001dcf9  nop     dword ptr [rax+rax+00h]
0x18001dcfe  mov     eax, [rbp+57h+IsMember]
0x18001dd01  mov     rcx, [rbp+57h+var_30]
0x18001dd05  xor     rcx, rsp; StackCookie
0x18001dd08  call    __security_check_cookie
0x18001dd0d  add     rsp, 98h
0x18001dd14  pop     rdi
0x18001dd15  pop     rsi
0x18001dd16  pop     rbx
0x18001dd17  pop     rbp
0x18001dd18  retn
0x18001dd1a  mov     rcx, [rbp+5Fh]; this
0x18001dd1e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dd25  mov     edx, 5Ah ; 'Z'; void *
0x18001dd2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001dd2f  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18001dd33  mov     ebx, eax
0x18001dd35  lea     rax, [rcx-1]
0x18001dd39  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001dd3d  jbe     loc_18001DDCC
0x18001dd43  test    ebx, ebx
0x18001dd45  jns     short loc_18001DCE9
0x18001dd47  mov     rcx, [rbp+5Fh]; this
0x18001dd4b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dd52  mov     r9d, ebx; char *
0x18001dd55  mov     edx, 7Bh ; '{'; void *
0x18001dd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd5f  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001dd63  test    rcx, rcx
0x18001dd66  jz      short loc_18001DD74
0x18001dd68  call    cs:__imp_RtlFreeSid
0x18001dd6f  nop     dword ptr [rax+rax+00h]
0x18001dd74  mov     rcx, [rbp+5Fh]; this
0x18001dd78  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dd7f  mov     r9d, ebx; char *
0x18001dd82  mov     edx, 0B8h; void *
0x18001dd87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dd8c  jmp     loc_18001DCFE
0x18001dd91  mov     rcx, [rbp+5Fh]; this
0x18001dd95  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dd9c  mov     r9d, eax; char *
0x18001dd9f  mov     edx, 79h ; 'y'; void *
0x18001dda4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001dda9  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001ddad  mov     ebx, eax
0x18001ddaf  test    rcx, rcx
0x18001ddb2  jnz     short loc_18001DDBE
0x18001ddb4  test    ebx, ebx
0x18001ddb6  jns     loc_18001DCFE
0x18001ddbc  jmp     short loc_18001DD74
0x18001ddbe  call    cs:__imp_RtlFreeSid
0x18001ddc5  nop     dword ptr [rax+rax+00h]
0x18001ddca  jmp     short loc_18001DDB4
0x18001ddcc  call    cs:__imp_CloseHandle
0x18001ddd3  nop     dword ptr [rax+rax+00h]
0x18001ddd8  jmp     loc_18001DD43
0x18001dddd  mov     rcx, [rbp+5Fh]; this
0x18001dde1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dde8  mov     edx, 5Fh ; '_'; void *
0x18001dded  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ddf2  lea     rcx, [rbp+57h+phNewToken]
0x18001ddf6  mov     ebx, eax
0x18001ddf8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ddfd  jmp     loc_18001DD43
0x18001de02  call    cs:__imp_CloseHandle
0x18001de09  nop     dword ptr [rax+rax+00h]
0x18001de0e  jmp     loc_18001DCE9
```
