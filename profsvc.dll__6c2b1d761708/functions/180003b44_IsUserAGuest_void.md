# IsUserAGuest(void *)

- ea: `0x180003b44`
- end: `0x180003f9b`
- name: `?IsUserAGuest@@YAHPEAX@Z`
- size: `1111`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ef18`

## callees

- `0x180003650`
- `0x180003b44`
- `0x180005370`
- `0x180005aec`
- `0x1800084bc`
- `0x180011c00`
- `0x18001214c`
- `0x18002df48`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003bc70`
- `0x18003fff4`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003cc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003cc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f3f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003bf8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003bf8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003c1a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003c1a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003d61`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003d61`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003d18`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003d18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003cfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003cfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f09`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180003bbf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180003bbf`
- `ntdll!RtlFreeSid` at `0x180003c80`
- `ntdll!RtlFreeSid` at `0x180003de5`
- `ntdll!RtlFreeSid` at `0x180003e64`
- `ntdll!RtlFreeSid` at `0x180003eb3`
- `ntdll!RtlFreeSid` at `0x180003c80`
- `ntdll!RtlFreeSid` at `0x180003de5`
- `ntdll!RtlFreeSid` at `0x180003e64`
- `ntdll!RtlFreeSid` at `0x180003eb3`

## string_xrefs

- `0x180003c04`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x180003e8d`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAGuest(void *a1)
{
  NTSTATUS v2; // eax
  PSID v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  int LastError; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  PSID *v9; // rsi
  unsigned int v10; // edx
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v13; // rax
  void *v14; // rax
  void *v15; // r15
  HANDLE v16; // rax
  int DomainSidFromDomainRid; // eax
  int v19; // eax
  BOOL TokenInformation; // eax
  __int64 v21; // rdx
  int SubAuthority2; // [rsp+20h] [rbp-59h]
  int SubAuthority2a; // [rsp+20h] [rbp-59h]
  PSID SidToCheck; // [rsp+60h] [rbp-19h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-11h] BYREF
  void *phNewToken; // [rsp+70h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  SidToCheck = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x222u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( v2 >= 0 )
  {
    v3 = SidToCheck;
    IsMember = 0;
    phNewToken = 0;
    if ( DuplicateTokenEx(a1, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      if ( CheckTokenMembership(phNewToken, v3, &IsMember) )
      {
        if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phNewToken);
        goto LABEL_9;
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
LABEL_9:
      if ( SidToCheck )
        RtlFreeSid(SidToCheck);
      goto LABEL_12;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)LastError,
      SubAuthority2a);
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
LABEL_37:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)LastError,
      SubAuthority2a);
    goto LABEL_12;
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
    goto LABEL_37;
LABEL_12:
  if ( IsMember )
    return (unsigned int)IsMember;
  v7 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 200;
  ProcessHeap = GetProcessHeap();
  SidToCheck = HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v9 = (PSID *)SidToCheck;
  if ( !SidToCheck )
  {
    Error = -2147024882;
    goto LABEL_30;
  }
  if ( GetTokenInformation(
         a1,
         TokenUser,
         SidToCheck,
         *(DWORD *)IdentifierAuthority.Value,
         (PDWORD)IdentifierAuthority.Value) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v19 = ResultFromHeapReAlloc(v9, *(unsigned int *)IdentifierAuthority.Value, &SidToCheck);
      v9 = (PSID *)SidToCheck;
      Error = v19;
      if ( v19 < 0 )
        goto LABEL_21;
      TokenInformation = GetTokenInformation(
                           a1,
                           TokenUser,
                           SidToCheck,
                           *(DWORD *)IdentifierAuthority.Value,
                           (PDWORD)IdentifierAuthority.Value);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v9);
    *(_DWORD *)IdentifierAuthority.Value = LengthSid;
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 8u, LengthSid);
    v15 = v14;
    if ( v14 )
    {
      if ( CopySid(*(DWORD *)IdentifierAuthority.Value, v14, *v9) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          ResultFromHeapFree(v15);
          goto LABEL_21;
        }
      }
      v7 = v15;
    }
    else
    {
      Error = -2147024882;
    }
  }
LABEL_21:
  if ( v9 )
  {
    v16 = GetProcessHeap();
    if ( !HeapFree(v16, 0, v9) )
      ResultFromKnownLastError();
  }
  if ( Error >= 0 )
  {
    SidToCheck = 0;
    DomainSidFromDomainRid = GetDomainSidFromDomainRid(v7, v10, &SidToCheck);
    if ( DomainSidFromDomainRid < 0 )
    {
      v21 = 155;
    }
    else
    {
      DomainSidFromDomainRid = CheckTokenForSidMembership(a1, SidToCheck, &IsMember);
      if ( DomainSidFromDomainRid >= 0 )
        goto LABEL_27;
      v21 = 157;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)DomainSidFromDomainRid,
      SubAuthority2a);
LABEL_27:
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
    goto LABEL_31;
  }
LABEL_30:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x98,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
    (const char *)(unsigned int)Error,
    SubAuthority2a);
LABEL_31:
  if ( v7 )
    ResultFromHeapFree(v7);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180003b44  push    rbp
0x180003b46  push    rbx
0x180003b47  push    rsi
0x180003b48  push    rdi
0x180003b49  push    r12
0x180003b4b  push    r13
0x180003b4d  push    r14
0x180003b4f  push    r15
0x180003b51  lea     rbp, [rsp-1Fh]
0x180003b56  sub     rsp, 98h
0x180003b5d  mov     rax, cs:__security_cookie
0x180003b64  xor     rax, rsp
0x180003b67  mov     [rbp+57h+var_50], rax
0x180003b6b  xor     r13d, r13d
0x180003b6e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180003b74  lea     rax, [rbp+57h+SidToCheck]
0x180003b78  mov     [rbp+57h+IsMember], r13d
0x180003b7c  mov     [rsp+0D0h+Sid], rax; Sid
0x180003b81  mov     r12, rcx
0x180003b84  mov     [rsp+0D0h+SubAuthority7], r13d; SubAuthority7
0x180003b89  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180003b8d  mov     [rsp+0D0h+SubAuthority6], r13d; SubAuthority6
0x180003b92  lea     edi, [r13+2]
0x180003b96  mov     [rsp+0D0h+SubAuthority5], r13d; SubAuthority5
0x180003b9b  lea     r8d, [r13+20h]; SubAuthority0
0x180003b9f  mov     [rsp+0D0h+SubAuthority4], r13d; SubAuthority4
0x180003ba4  mov     dl, dil; SubAuthorityCount
0x180003ba7  mov     [rsp+0D0h+SubAuthority3], r13d; SubAuthority3
0x180003bac  mov     r9d, 222h; SubAuthority1
0x180003bb2  mov     [rsp+0D0h+SubAuthority2], r13d; int
0x180003bb7  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x180003bbb  mov     [rbp+57h+SidToCheck], r13
0x180003bbf  call    cs:__imp_RtlAllocateAndInitializeSid
0x180003bc6  nop     dword ptr [rax+rax+00h]
0x180003bcb  test    eax, eax
0x180003bcd  js      loc_180003E89
0x180003bd3  mov     rbx, [rbp+57h+SidToCheck]
0x180003bd7  lea     rax, [rbp+57h+phNewToken]
0x180003bdb  mov     qword ptr [rsp+0D0h+SubAuthority3], rax; phNewToken
0x180003be0  lea     edx, [rdi+0Ah]; dwDesiredAccess
0x180003be3  mov     r9d, edi; ImpersonationLevel
0x180003be6  mov     [rsp+0D0h+SubAuthority2], edi; int
0x180003bea  xor     r8d, r8d; lpTokenAttributes
0x180003bed  mov     [rbp+57h+IsMember], r13d
0x180003bf1  mov     rcx, r12; hExistingToken
0x180003bf4  mov     [rbp+57h+phNewToken], r13
0x180003bf8  call    cs:__imp_DuplicateTokenEx
0x180003bff  nop     dword ptr [rax+rax+00h]
0x180003c04  lea     r14, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003c0b  test    eax, eax
0x180003c0d  jz      short loc_180003C4A
0x180003c0f  mov     rcx, [rbp+57h+phNewToken]; TokenHandle
0x180003c13  lea     r8, [rbp+57h+IsMember]; IsMember
0x180003c17  mov     rdx, rbx; SidToCheck
0x180003c1a  call    cs:__imp_CheckTokenMembership
0x180003c21  nop     dword ptr [rax+rax+00h]
0x180003c26  test    eax, eax
0x180003c28  jz      loc_180003F50
0x180003c2e  mov     rcx, [rbp+57h+phNewToken]; hObject
0x180003c32  lea     rax, [rcx-1]
0x180003c36  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003c3a  ja      short loc_180003C77
0x180003c3c  call    cs:__imp_CloseHandle
0x180003c43  nop     dword ptr [rax+rax+00h]
0x180003c48  jmp     short loc_180003C77
0x180003c4a  mov     rcx, [rbp+5Fh]; this
0x180003c4e  mov     r8, r14; unsigned int
0x180003c51  mov     edx, 5Ah ; 'Z'; void *
0x180003c56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003c5b  mov     rcx, [rbp+57h+phNewToken]; hObject
0x180003c5f  mov     ebx, eax
0x180003c61  lea     rax, [rcx-1]
0x180003c65  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003c69  jbe     loc_180003F3F
0x180003c6f  test    ebx, ebx
0x180003c71  js      loc_180003E47
0x180003c77  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003c7b  test    rcx, rcx
0x180003c7e  jz      short loc_180003C96
0x180003c80  call    cs:__imp_RtlFreeSid
0x180003c87  nop     dword ptr [rax+rax+00h]
0x180003c8c  jmp     short loc_180003C96
0x180003c8e  test    ebx, ebx
0x180003c90  js      loc_180003E70
0x180003c96  cmp     [rbp+57h+IsMember], r13d
0x180003c9a  jnz     loc_180003E19
0x180003ca0  mov     edi, 0C8h
0x180003ca5  mov     rbx, r13
0x180003ca8  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180003cab  call    cs:__imp_GetProcessHeap
0x180003cb2  nop     dword ptr [rax+rax+00h]
0x180003cb7  mov     r8d, edi; dwBytes
0x180003cba  mov     edx, 8; dwFlags
0x180003cbf  mov     rcx, rax; hHeap
0x180003cc2  call    cs:__imp_HeapAlloc
0x180003cc9  nop     dword ptr [rax+rax+00h]
0x180003cce  mov     [rbp+57h+SidToCheck], rax
0x180003cd2  mov     rsi, rax
0x180003cd5  test    rax, rax
0x180003cd8  jz      loc_180003DF3
0x180003cde  mov     r9d, dword ptr [rbp+57h+IdentifierAuthority.Value]; TokenInformationLength
0x180003ce2  lea     rax, [rbp+57h+IdentifierAuthority]
0x180003ce6  mov     r15d, 1
0x180003cec  mov     qword ptr [rsp+0D0h+SubAuthority2], rax; int
0x180003cf1  mov     edx, r15d; TokenInformationClass
0x180003cf4  mov     r8, rsi; TokenInformation
0x180003cf7  mov     rcx, r12; TokenHandle
0x180003cfa  call    cs:__imp_GetTokenInformation
0x180003d01  nop     dword ptr [rax+rax+00h]
0x180003d06  test    eax, eax
0x180003d08  jz      loc_180003EC4
0x180003d0e  mov     edi, r13d
0x180003d11  test    edi, edi
0x180003d13  js      short loc_180003D7B
0x180003d15  mov     rcx, [rsi]; pSid
0x180003d18  call    cs:__imp_GetLengthSid
0x180003d1f  nop     dword ptr [rax+rax+00h]
0x180003d24  mov     edi, eax
0x180003d26  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180003d29  call    cs:__imp_GetProcessHeap
0x180003d30  nop     dword ptr [rax+rax+00h]
0x180003d35  mov     r8d, edi; dwBytes
0x180003d38  mov     edx, 8; dwFlags
0x180003d3d  mov     rcx, rax; hHeap
0x180003d40  call    cs:__imp_HeapAlloc
0x180003d47  nop     dword ptr [rax+rax+00h]
0x180003d4c  mov     r15, rax
0x180003d4f  test    rax, rax
0x180003d52  jz      loc_180003E3D
0x180003d58  mov     r8, [rsi]; pSourceSid
0x180003d5b  mov     rdx, rax; pDestinationSid
0x180003d5e  mov     ecx, dword ptr [rbp+57h+IdentifierAuthority.Value]; nDestinationSidLength
0x180003d61  call    cs:__imp_CopySid
0x180003d68  nop     dword ptr [rax+rax+00h]
0x180003d6d  test    eax, eax
0x180003d6f  jz      loc_180003F23
0x180003d75  mov     edi, r13d
0x180003d78  mov     rbx, r15
0x180003d7b  test    rsi, rsi
0x180003d7e  jz      short loc_180003DA8
0x180003d80  call    cs:__imp_GetProcessHeap
0x180003d87  nop     dword ptr [rax+rax+00h]
0x180003d8c  mov     r8, rsi; lpMem
0x180003d8f  xor     edx, edx; dwFlags
0x180003d91  mov     rcx, rax; hHeap
0x180003d94  call    cs:__imp_HeapFree
0x180003d9b  nop     dword ptr [rax+rax+00h]
0x180003da0  test    eax, eax
0x180003da2  jz      loc_180003F71
0x180003da8  test    edi, edi
0x180003daa  js      short loc_180003DF8
0x180003dac  lea     r8, [rbp+57h+SidToCheck]; void **
0x180003db0  mov     [rbp+57h+SidToCheck], r13
0x180003db4  mov     rcx, rbx; Sid
0x180003db7  call    ?GetDomainSidFromDomainRid@@YAJPEAXKPEAPEAX@Z; GetDomainSidFromDomainRid(void *,ulong,void * *)
0x180003dbc  test    eax, eax
0x180003dbe  js      loc_180003F7B
0x180003dc4  mov     rdx, [rbp+57h+SidToCheck]; void *
0x180003dc8  lea     r8, [rbp+57h+IsMember]; int *
0x180003dcc  mov     rcx, r12; void *
0x180003dcf  call    ?CheckTokenForSidMembership@@YAJPEAX0PEAH@Z; CheckTokenForSidMembership(void *,void *,int *)
0x180003dd4  test    eax, eax
0x180003dd6  js      loc_180003F82
0x180003ddc  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003de0  test    rcx, rcx
0x180003de3  jz      short loc_180003E0C
0x180003de5  call    cs:__imp_RtlFreeSid
0x180003dec  nop     dword ptr [rax+rax+00h]
0x180003df1  jmp     short loc_180003E0C
0x180003df3  mov     edi, 8007000Eh
0x180003df8  mov     rcx, [rbp+5Fh]; this
0x180003dfc  mov     r9d, edi; char *
0x180003dff  mov     r8, r14; unsigned int
0x180003e02  mov     edx, 98h; void *
0x180003e07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003e0c  test    rbx, rbx
0x180003e0f  jz      short loc_180003E19
0x180003e11  mov     rcx, rbx; lpMem
0x180003e14  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180003e19  mov     eax, [rbp+57h+IsMember]
0x180003e1c  mov     rcx, [rbp+57h+var_50]
0x180003e20  xor     rcx, rsp; StackCookie
0x180003e23  call    __security_check_cookie
0x180003e28  add     rsp, 98h
0x180003e2f  pop     r15
0x180003e31  pop     r14
0x180003e33  pop     r13
0x180003e35  pop     r12
0x180003e37  pop     rdi
0x180003e38  pop     rsi
0x180003e39  pop     rbx
0x180003e3a  pop     rbp
0x180003e3b  retn
0x180003e3d  mov     edi, 8007000Eh
0x180003e42  jmp     loc_180003D7B
0x180003e47  mov     rcx, [rbp+5Fh]; this
0x180003e4b  mov     r9d, ebx; char *
0x180003e4e  mov     r8, r14; unsigned int
0x180003e51  mov     edx, 7Bh ; '{'; void *
0x180003e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e5b  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003e5f  test    rcx, rcx
0x180003e62  jz      short loc_180003E70
0x180003e64  call    cs:__imp_RtlFreeSid
0x180003e6b  nop     dword ptr [rax+rax+00h]
0x180003e70  mov     rcx, [rbp+5Fh]; this
0x180003e74  mov     r9d, ebx; char *
0x180003e77  mov     r8, r14; unsigned int
0x180003e7a  mov     edx, 93h; void *
0x180003e7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003e84  jmp     loc_180003C96
0x180003e89  mov     rcx, [rbp+5Fh]; this
0x180003e8d  lea     r14, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003e94  mov     r8, r14; unsigned int
0x180003e97  mov     r9d, eax; char *
0x180003e9a  mov     edx, 79h ; 'y'; void *
0x180003e9f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180003ea4  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003ea8  mov     ebx, eax
0x180003eaa  test    rcx, rcx
0x180003ead  jz      loc_180003C8E
0x180003eb3  call    cs:__imp_RtlFreeSid
0x180003eba  nop     dword ptr [rax+rax+00h]
0x180003ebf  jmp     loc_180003C8E
0x180003ec4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003ec9  mov     edi, eax
0x180003ecb  cmp     eax, 8007007Ah
0x180003ed0  jnz     loc_180003D11
0x180003ed6  mov     edx, dword ptr [rbp+57h+IdentifierAuthority.Value]; dwBytes
0x180003ed9  lea     r8, [rbp+57h+SidToCheck]; void **
0x180003edd  mov     rcx, rsi; lpMem
0x180003ee0  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180003ee5  mov     rsi, [rbp+57h+SidToCheck]
0x180003ee9  mov     edi, eax
0x180003eeb  test    eax, eax
0x180003eed  js      loc_180003D7B
0x180003ef3  mov     r9d, dword ptr [rbp+57h+IdentifierAuthority.Value]; TokenInformationLength
0x180003ef7  lea     rax, [rbp+57h+IdentifierAuthority]
0x180003efb  mov     r8, rsi; TokenInformation
0x180003efe  mov     qword ptr [rsp+0D0h+SubAuthority2], rax; ReturnLength
0x180003f03  mov     edx, r15d; TokenInformationClass
0x180003f06  mov     rcx, r12; TokenHandle
0x180003f09  call    cs:__imp_GetTokenInformation
0x180003f10  nop     dword ptr [rax+rax+00h]
0x180003f15  mov     ecx, eax; int
0x180003f17  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180003f1c  mov     edi, eax
0x180003f1e  jmp     loc_180003D11
0x180003f23  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003f28  mov     edi, eax
0x180003f2a  test    eax, eax
0x180003f2c  jns     loc_180003D78
0x180003f32  mov     rcx, r15; lpMem
0x180003f35  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180003f3a  jmp     loc_180003D7B
0x180003f3f  call    cs:__imp_CloseHandle
0x180003f46  nop     dword ptr [rax+rax+00h]
0x180003f4b  jmp     loc_180003C6F
0x180003f50  mov     rcx, [rbp+5Fh]; this
0x180003f54  mov     r8, r14; unsigned int
0x180003f57  mov     edx, 5Fh ; '_'; void *
0x180003f5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003f61  lea     rcx, [rbp+57h+phNewToken]
0x180003f65  mov     ebx, eax
0x180003f67  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003f6c  jmp     loc_180003C6F
0x180003f71  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003f76  jmp     loc_180003DA8
0x180003f7b  mov     edx, 9Bh
0x180003f80  jmp     short loc_180003F87
0x180003f82  mov     edx, 9Dh; void *
0x180003f87  mov     rcx, [rbp+5Fh]; this
0x180003f8b  mov     r9d, eax; char *
0x180003f8e  mov     r8, r14; unsigned int
0x180003f91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003f96  jmp     loc_180003DDC
```
