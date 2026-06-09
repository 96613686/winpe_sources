# IsUserAGuest(void *)

- ea: `0x180003a54`
- end: `0x180003e38`
- name: `?IsUserAGuest@@YAHPEAX@Z`
- size: `996`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fc50`

## callees

- `0x1800035f0`
- `0x180003a54`
- `0x180004170`
- `0x1800041ac`
- `0x180004ff4`
- `0x180006580`
- `0x18000a9b8`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003a730`
- `0x18003e8fc`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003de2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003b02`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003b02`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003b1e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003b1e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003c2f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003c2f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003bf8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003bf8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003be0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003db2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003be0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003db2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180003acf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180003acf`
- `ntdll!RtlFreeSid` at `0x180003b78`
- `ntdll!RtlFreeSid` at `0x180003ca1`
- `ntdll!RtlFreeSid` at `0x180003d19`
- `ntdll!RtlFreeSid` at `0x180003d62`
- `ntdll!RtlFreeSid` at `0x180003b78`
- `ntdll!RtlFreeSid` at `0x180003ca1`
- `ntdll!RtlFreeSid` at `0x180003d19`
- `ntdll!RtlFreeSid` at `0x180003d62`

## string_xrefs

- `0x180003b08`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x180003d3c`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

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
      (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)LastError);
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
      (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)(unsigned int)DomainSidFromDomainRid);
LABEL_27:
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
    goto LABEL_31;
  }
LABEL_30:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x98,
    (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
    (const char *)(unsigned int)Error);
LABEL_31:
  if ( v7 )
    ResultFromHeapFree(v7);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180003a54  push    rbp
0x180003a56  push    rbx
0x180003a57  push    rsi
0x180003a58  push    rdi
0x180003a59  push    r12
0x180003a5b  push    r13
0x180003a5d  push    r14
0x180003a5f  push    r15
0x180003a61  lea     rbp, [rsp-1Fh]
0x180003a66  sub     rsp, 98h
0x180003a6d  mov     rax, cs:__security_cookie
0x180003a74  xor     rax, rsp
0x180003a77  mov     [rbp+57h+var_50], rax
0x180003a7b  xor     r13d, r13d
0x180003a7e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180003a84  lea     rax, [rbp+57h+SidToCheck]
0x180003a88  mov     [rbp+57h+IsMember], r13d
0x180003a8c  mov     [rsp+0D0h+Sid], rax; Sid
0x180003a91  mov     r12, rcx
0x180003a94  mov     [rsp+0D0h+SubAuthority7], r13d; SubAuthority7
0x180003a99  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180003a9d  mov     [rsp+0D0h+SubAuthority6], r13d; SubAuthority6
0x180003aa2  lea     edi, [r13+2]
0x180003aa6  mov     [rsp+0D0h+SubAuthority5], r13d; SubAuthority5
0x180003aab  lea     r8d, [r13+20h]; SubAuthority0
0x180003aaf  mov     [rsp+0D0h+SubAuthority4], r13d; SubAuthority4
0x180003ab4  mov     dl, dil; SubAuthorityCount
0x180003ab7  mov     [rsp+0D0h+SubAuthority3], r13d; SubAuthority3
0x180003abc  mov     r9d, 222h; SubAuthority1
0x180003ac2  mov     [rsp+0D0h+SubAuthority2], r13d; int
0x180003ac7  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x180003acb  mov     [rbp+57h+SidToCheck], r13
0x180003acf  call    cs:__imp_RtlAllocateAndInitializeSid
0x180003ad5  test    eax, eax
0x180003ad7  js      loc_180003D38
0x180003add  mov     rbx, [rbp+57h+SidToCheck]
0x180003ae1  lea     rax, [rbp+57h+phNewToken]
0x180003ae5  mov     qword ptr [rsp+0D0h+SubAuthority3], rax; phNewToken
0x180003aea  lea     edx, [rdi+0Ah]; dwDesiredAccess
0x180003aed  mov     r9d, edi; ImpersonationLevel
0x180003af0  mov     [rsp+0D0h+SubAuthority2], edi; int
0x180003af4  xor     r8d, r8d; lpTokenAttributes
0x180003af7  mov     [rbp+57h+IsMember], r13d
0x180003afb  mov     rcx, r12; hExistingToken
0x180003afe  mov     [rbp+57h+phNewToken], r13
0x180003b02  call    cs:__imp_DuplicateTokenEx
0x180003b08  lea     r14, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003b0f  test    eax, eax
0x180003b11  jz      short loc_180003B42
0x180003b13  mov     rcx, [rbp+57h+phNewToken]; TokenHandle
0x180003b17  lea     r8, [rbp+57h+IsMember]; IsMember
0x180003b1b  mov     rdx, rbx; SidToCheck
0x180003b1e  call    cs:__imp_CheckTokenMembership
0x180003b24  test    eax, eax
0x180003b26  jz      loc_180003DED
0x180003b2c  mov     rcx, [rbp+57h+phNewToken]; hObject
0x180003b30  lea     rax, [rcx-1]
0x180003b34  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003b38  ja      short loc_180003B6F
0x180003b3a  call    cs:__imp_CloseHandle
0x180003b40  jmp     short loc_180003B6F
0x180003b42  mov     rcx, [rbp+5Fh]; this
0x180003b46  mov     r8, r14; unsigned int
0x180003b49  mov     edx, 5Ah ; 'Z'; void *
0x180003b4e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003b53  mov     rcx, [rbp+57h+phNewToken]; hObject
0x180003b57  mov     ebx, eax
0x180003b59  lea     rax, [rcx-1]
0x180003b5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003b61  jbe     loc_180003DE2
0x180003b67  test    ebx, ebx
0x180003b69  js      loc_180003CFC
0x180003b6f  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003b73  test    rcx, rcx
0x180003b76  jz      short loc_180003B88
0x180003b78  call    cs:__imp_RtlFreeSid
0x180003b7e  jmp     short loc_180003B88
0x180003b80  test    ebx, ebx
0x180003b82  js      loc_180003D1F
0x180003b88  cmp     [rbp+57h+IsMember], r13d
0x180003b8c  jnz     loc_180003CCF
0x180003b92  mov     edi, 0C8h
0x180003b97  mov     rbx, r13
0x180003b9a  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180003b9d  call    cs:__imp_GetProcessHeap
0x180003ba3  mov     r8d, edi; dwBytes
0x180003ba6  mov     edx, 8; dwFlags
0x180003bab  mov     rcx, rax; hHeap
0x180003bae  call    cs:__imp_HeapAlloc
0x180003bb4  mov     [rbp+57h+SidToCheck], rax
0x180003bb8  mov     rsi, rax
0x180003bbb  test    rax, rax
0x180003bbe  jz      loc_180003CA9
0x180003bc4  mov     r9d, dword ptr [rbp+57h+IdentifierAuthority.Value]; TokenInformationLength
0x180003bc8  lea     rax, [rbp+57h+IdentifierAuthority]
0x180003bcc  mov     r15d, 1
0x180003bd2  mov     qword ptr [rsp+0D0h+SubAuthority2], rax; int
0x180003bd7  mov     edx, r15d; TokenInformationClass
0x180003bda  mov     r8, rsi; TokenInformation
0x180003bdd  mov     rcx, r12; TokenHandle
0x180003be0  call    cs:__imp_GetTokenInformation
0x180003be6  test    eax, eax
0x180003be8  jz      loc_180003D6D
0x180003bee  mov     edi, r13d
0x180003bf1  test    edi, edi
0x180003bf3  js      short loc_180003C43
0x180003bf5  mov     rcx, [rsi]; pSid
0x180003bf8  call    cs:__imp_GetLengthSid
0x180003bfe  mov     edi, eax
0x180003c00  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x180003c03  call    cs:__imp_GetProcessHeap
0x180003c09  mov     r8d, edi; dwBytes
0x180003c0c  mov     edx, 8; dwFlags
0x180003c11  mov     rcx, rax; hHeap
0x180003c14  call    cs:__imp_HeapAlloc
0x180003c1a  mov     r15, rax
0x180003c1d  test    rax, rax
0x180003c20  jz      loc_180003CF2
0x180003c26  mov     r8, [rsi]; pSourceSid
0x180003c29  mov     rdx, rax; pDestinationSid
0x180003c2c  mov     ecx, dword ptr [rbp+57h+IdentifierAuthority.Value]; nDestinationSidLength
0x180003c2f  call    cs:__imp_CopySid
0x180003c35  test    eax, eax
0x180003c37  jz      loc_180003DC6
0x180003c3d  mov     edi, r13d
0x180003c40  mov     rbx, r15
0x180003c43  test    rsi, rsi
0x180003c46  jz      short loc_180003C64
0x180003c48  call    cs:__imp_GetProcessHeap
0x180003c4e  mov     r8, rsi; lpMem
0x180003c51  xor     edx, edx; dwFlags
0x180003c53  mov     rcx, rax; hHeap
0x180003c56  call    cs:__imp_HeapFree
0x180003c5c  test    eax, eax
0x180003c5e  jz      loc_180003E0E
0x180003c64  test    edi, edi
0x180003c66  js      short loc_180003CAE
0x180003c68  lea     r8, [rbp+57h+SidToCheck]; void **
0x180003c6c  mov     [rbp+57h+SidToCheck], r13
0x180003c70  mov     rcx, rbx; Sid
0x180003c73  call    ?GetDomainSidFromDomainRid@@YAJPEAXKPEAPEAX@Z; GetDomainSidFromDomainRid(void *,ulong,void * *)
0x180003c78  test    eax, eax
0x180003c7a  js      loc_180003E18
0x180003c80  mov     rdx, [rbp+57h+SidToCheck]; void *
0x180003c84  lea     r8, [rbp+57h+IsMember]; int *
0x180003c88  mov     rcx, r12; void *
0x180003c8b  call    ?CheckTokenForSidMembership@@YAJPEAX0PEAH@Z; CheckTokenForSidMembership(void *,void *,int *)
0x180003c90  test    eax, eax
0x180003c92  js      loc_180003E1F
0x180003c98  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003c9c  test    rcx, rcx
0x180003c9f  jz      short loc_180003CC2
0x180003ca1  call    cs:__imp_RtlFreeSid
0x180003ca7  jmp     short loc_180003CC2
0x180003ca9  mov     edi, 8007000Eh
0x180003cae  mov     rcx, [rbp+5Fh]; this
0x180003cb2  mov     r9d, edi; char *
0x180003cb5  mov     r8, r14; unsigned int
0x180003cb8  mov     edx, 98h; void *
0x180003cbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003cc2  test    rbx, rbx
0x180003cc5  jz      short loc_180003CCF
0x180003cc7  mov     rcx, rbx; lpMem
0x180003cca  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180003ccf  mov     eax, [rbp+57h+IsMember]
0x180003cd2  mov     rcx, [rbp+57h+var_50]
0x180003cd6  xor     rcx, rsp; StackCookie
0x180003cd9  call    __security_check_cookie
0x180003cde  add     rsp, 98h
0x180003ce5  pop     r15
0x180003ce7  pop     r14
0x180003ce9  pop     r13
0x180003ceb  pop     r12
0x180003ced  pop     rdi
0x180003cee  pop     rsi
0x180003cef  pop     rbx
0x180003cf0  pop     rbp
0x180003cf1  retn
0x180003cf2  mov     edi, 8007000Eh
0x180003cf7  jmp     loc_180003C43
0x180003cfc  mov     rcx, [rbp+5Fh]; this
0x180003d00  mov     r9d, ebx; char *
0x180003d03  mov     r8, r14; unsigned int
0x180003d06  mov     edx, 7Bh ; '{'; void *
0x180003d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d10  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003d14  test    rcx, rcx
0x180003d17  jz      short loc_180003D1F
0x180003d19  call    cs:__imp_RtlFreeSid
0x180003d1f  mov     rcx, [rbp+5Fh]; this
0x180003d23  mov     r9d, ebx; char *
0x180003d26  mov     r8, r14; unsigned int
0x180003d29  mov     edx, 93h; void *
0x180003d2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003d33  jmp     loc_180003B88
0x180003d38  mov     rcx, [rbp+5Fh]; this
0x180003d3c  lea     r14, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003d43  mov     r8, r14; unsigned int
0x180003d46  mov     r9d, eax; char *
0x180003d49  mov     edx, 79h ; 'y'; void *
0x180003d4e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180003d53  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180003d57  mov     ebx, eax
0x180003d59  test    rcx, rcx
0x180003d5c  jz      loc_180003B80
0x180003d62  call    cs:__imp_RtlFreeSid
0x180003d68  jmp     loc_180003B80
0x180003d6d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003d72  mov     edi, eax
0x180003d74  cmp     eax, 8007007Ah
0x180003d79  jnz     loc_180003BF1
0x180003d7f  mov     edx, dword ptr [rbp+57h+IdentifierAuthority.Value]; dwBytes
0x180003d82  lea     r8, [rbp+57h+SidToCheck]; void **
0x180003d86  mov     rcx, rsi; lpMem
0x180003d89  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180003d8e  mov     rsi, [rbp+57h+SidToCheck]
0x180003d92  mov     edi, eax
0x180003d94  test    eax, eax
0x180003d96  js      loc_180003C43
0x180003d9c  mov     r9d, dword ptr [rbp+57h+IdentifierAuthority.Value]; TokenInformationLength
0x180003da0  lea     rax, [rbp+57h+IdentifierAuthority]
0x180003da4  mov     r8, rsi; TokenInformation
0x180003da7  mov     qword ptr [rsp+0D0h+SubAuthority2], rax; ReturnLength
0x180003dac  mov     edx, r15d; TokenInformationClass
0x180003daf  mov     rcx, r12; TokenHandle
0x180003db2  call    cs:__imp_GetTokenInformation
0x180003db8  mov     ecx, eax; int
0x180003dba  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180003dbf  mov     edi, eax
0x180003dc1  jmp     loc_180003BF1
0x180003dc6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003dcb  mov     edi, eax
0x180003dcd  test    eax, eax
0x180003dcf  jns     loc_180003C40
0x180003dd5  mov     rcx, r15; lpMem
0x180003dd8  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180003ddd  jmp     loc_180003C43
0x180003de2  call    cs:__imp_CloseHandle
0x180003de8  jmp     loc_180003B67
0x180003ded  mov     rcx, [rbp+5Fh]; this
0x180003df1  mov     r8, r14; unsigned int
0x180003df4  mov     edx, 5Fh ; '_'; void *
0x180003df9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003dfe  lea     rcx, [rbp+57h+phNewToken]
0x180003e02  mov     ebx, eax
0x180003e04  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003e09  jmp     loc_180003B67
0x180003e0e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003e13  jmp     loc_180003C64
0x180003e18  mov     edx, 9Bh
0x180003e1d  jmp     short loc_180003E24
0x180003e1f  mov     edx, 9Dh; void *
0x180003e24  mov     rcx, [rbp+5Fh]; this
0x180003e28  mov     r9d, eax; char *
0x180003e2b  mov     r8, r14; unsigned int
0x180003e2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003e33  jmp     loc_180003C98
```
