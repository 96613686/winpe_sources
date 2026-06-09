# IsUserAnAdminMember(void *)

- ea: `0x18001a1e0`
- end: `0x18001a3be`
- name: `?IsUserAnAdminMember@@YAHPEAX@Z`
- size: `478`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019ba0`
- `0x18001a110`
- `0x18002fc50`

## callees

- `0x18000a9b8`
- `0x18001a1e0`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003a730`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3b3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001a282`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001a282`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a297`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a297`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001a247`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001a247`
- `ntdll!RtlFreeSid` at `0x18001a2c0`
- `ntdll!RtlFreeSid` at `0x18001a32b`
- `ntdll!RtlFreeSid` at `0x18001a37b`
- `ntdll!RtlFreeSid` at `0x18001a2c0`
- `ntdll!RtlFreeSid` at `0x18001a32b`
- `ntdll!RtlFreeSid` at `0x18001a37b`

## string_xrefs

- `0x18001a2e5`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001a30e`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001a335`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001a352`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18001a392`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

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
0x18001a1e0  push    rbp
0x18001a1e2  push    rbx
0x18001a1e3  push    rsi
0x18001a1e4  push    rdi
0x18001a1e5  lea     rbp, [rsp-3Fh]
0x18001a1ea  sub     rsp, 98h
0x18001a1f1  mov     rax, cs:__security_cookie
0x18001a1f8  xor     rax, rsp
0x18001a1fb  mov     [rbp+57h+var_30], rax
0x18001a1ff  xor     esi, esi
0x18001a201  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18001a207  lea     rax, [rbp+57h+SidToCheck]
0x18001a20b  mov     [rbp+57h+IsMember], esi
0x18001a20e  mov     [rsp+0B0h+Sid], rax; Sid
0x18001a213  mov     rbx, rcx
0x18001a216  mov     [rsp+0B0h+SubAuthority7], esi; SubAuthority7
0x18001a21a  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18001a21e  mov     [rsp+0B0h+SubAuthority6], esi; SubAuthority6
0x18001a222  mov     r9d, 220h; SubAuthority1
0x18001a228  mov     [rsp+0B0h+SubAuthority5], esi; SubAuthority5
0x18001a22c  mov     r8d, 20h ; ' '; SubAuthority0
0x18001a232  mov     [rsp+0B0h+SubAuthority4], esi; SubAuthority4
0x18001a236  mov     dl, 2; SubAuthorityCount
0x18001a238  mov     [rsp+0B0h+SubAuthority3], esi; SubAuthority3
0x18001a23c  mov     [rsp+0B0h+SubAuthority2], esi; int
0x18001a240  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x18001a243  mov     [rbp+57h+SidToCheck], rsi
0x18001a247  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001a24d  test    eax, eax
0x18001a24f  js      loc_18001A34E
0x18001a255  mov     rdi, [rbp+57h+SidToCheck]
0x18001a259  lea     rax, [rbp+57h+phNewToken]
0x18001a25d  mov     qword ptr [rsp+0B0h+SubAuthority3], rax; phNewToken
0x18001a262  mov     r9d, 2; ImpersonationLevel
0x18001a268  xor     r8d, r8d; lpTokenAttributes
0x18001a26b  mov     [rsp+0B0h+SubAuthority2], 2; int
0x18001a273  mov     edx, 0Ch; dwDesiredAccess
0x18001a278  mov     [rbp+57h+IsMember], esi
0x18001a27b  mov     rcx, rbx; hExistingToken
0x18001a27e  mov     [rbp+57h+phNewToken], rsi
0x18001a282  call    cs:__imp_DuplicateTokenEx
0x18001a288  test    eax, eax
0x18001a28a  jz      short loc_18001A2E1
0x18001a28c  mov     rcx, [rbp+57h+phNewToken]; TokenHandle
0x18001a290  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001a294  mov     rdx, rdi; SidToCheck
0x18001a297  call    cs:__imp_CheckTokenMembership
0x18001a29d  test    eax, eax
0x18001a29f  jz      loc_18001A38E
0x18001a2a5  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18001a2a9  lea     rax, [rcx-1]
0x18001a2ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a2b1  jbe     loc_18001A3B3
0x18001a2b7  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001a2bb  test    rcx, rcx
0x18001a2be  jz      short loc_18001A2C6
0x18001a2c0  call    cs:__imp_RtlFreeSid
0x18001a2c6  mov     eax, [rbp+57h+IsMember]
0x18001a2c9  mov     rcx, [rbp+57h+var_30]
0x18001a2cd  xor     rcx, rsp; StackCookie
0x18001a2d0  call    __security_check_cookie
0x18001a2d5  add     rsp, 98h
0x18001a2dc  pop     rdi
0x18001a2dd  pop     rsi
0x18001a2de  pop     rbx
0x18001a2df  pop     rbp
0x18001a2e0  retn
0x18001a2e1  mov     rcx, [rbp+5Fh]; this
0x18001a2e5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a2ec  mov     edx, 5Ah ; 'Z'; void *
0x18001a2f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a2f6  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18001a2fa  mov     ebx, eax
0x18001a2fc  lea     rax, [rcx-1]
0x18001a300  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a304  jbe     short loc_18001A383
0x18001a306  test    ebx, ebx
0x18001a308  jns     short loc_18001A2B7
0x18001a30a  mov     rcx, [rbp+5Fh]; this
0x18001a30e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a315  mov     r9d, ebx; char *
0x18001a318  mov     edx, 7Bh ; '{'; void *
0x18001a31d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a322  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001a326  test    rcx, rcx
0x18001a329  jz      short loc_18001A331
0x18001a32b  call    cs:__imp_RtlFreeSid
0x18001a331  mov     rcx, [rbp+5Fh]; this
0x18001a335  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a33c  mov     r9d, ebx; char *
0x18001a33f  mov     edx, 0B8h; void *
0x18001a344  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a349  jmp     loc_18001A2C6
0x18001a34e  mov     rcx, [rbp+5Fh]; this
0x18001a352  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a359  mov     r9d, eax; char *
0x18001a35c  mov     edx, 79h ; 'y'; void *
0x18001a361  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a366  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x18001a36a  mov     ebx, eax
0x18001a36c  test    rcx, rcx
0x18001a36f  jnz     short loc_18001A37B
0x18001a371  test    ebx, ebx
0x18001a373  jns     loc_18001A2C6
0x18001a379  jmp     short loc_18001A331
0x18001a37b  call    cs:__imp_RtlFreeSid
0x18001a381  jmp     short loc_18001A371
0x18001a383  call    cs:__imp_CloseHandle
0x18001a389  jmp     loc_18001A306
0x18001a38e  mov     rcx, [rbp+5Fh]; this
0x18001a392  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a399  mov     edx, 5Fh ; '_'; void *
0x18001a39e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a3a3  lea     rcx, [rbp+57h+phNewToken]
0x18001a3a7  mov     ebx, eax
0x18001a3a9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a3ae  jmp     loc_18001A306
0x18001a3b3  call    cs:__imp_CloseHandle
0x18001a3b9  jmp     loc_18001A2B7
```
