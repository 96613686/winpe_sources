# DpiIndirectEscapeAccessCheck(void)

- ea: `0x1403d17d4`
- end: `0x1403d1ca2`
- name: `?DpiIndirectEscapeAccessCheck@@YAJXZ`
- size: `1230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1403d10ac`

## callees

- `0x1400a0100`
- `0x1403d17d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c30`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c72`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c30`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1c72`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1863`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1889`
- `ntoskrnl!ExAllocatePool2` at `0x1403d18b3`
- `ntoskrnl!ExAllocatePool2` at `0x1403d18d8`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1a5a`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1863`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1889`
- `ntoskrnl!ExAllocatePool2` at `0x1403d18b3`
- `ntoskrnl!ExAllocatePool2` at `0x1403d18d8`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1a5a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1403d180a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1403d180a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1403d1832`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1403d1832`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1843`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1875`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d189f`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d18c4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1843`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1875`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d189f`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d18c4`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1922`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1967`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1922`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1967`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1933`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d194b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1978`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1933`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d194b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1978`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a04`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a16`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a28`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a3a`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a04`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a16`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a28`
- `ntoskrnl!RtlLengthSid` at `0x1403d1a3a`
- `ntoskrnl!RtlCreateAcl` at `0x1403d1a7c`
- `ntoskrnl!RtlCreateAcl` at `0x1403d1a7c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1aa3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1aca`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1af1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1b18`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1aa3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1aca`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1af1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1b18`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1403d1b3b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1403d1b3b`
- `ntoskrnl!SeAccessCheck` at `0x1403d1ba4`
- `ntoskrnl!SeAccessCheck` at `0x1403d1ba4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1403d1c1a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1403d1c1a`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d19b2`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d19f5`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d19b2`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d19f5`
- `watchdog!WdLogSingleEntry1` at `0x1403d1bdc`
- `watchdog!WdLogSingleEntry1` at `0x1403d1c00`
- `watchdog!WdLogSingleEntry1` at `0x1403d1bdc`
- `watchdog!WdLogSingleEntry1` at `0x1403d1c00`

## pseudocode

```c
__int64 DpiIndirectEscapeAccessCheck(void)
{
  ULONG v0; // eax
  void *Pool2; // r15
  ULONG v2; // eax
  void *v3; // rdi
  ULONG v4; // eax
  void *v5; // rsi
  ULONG v6; // eax
  __int64 v7; // rax
  void *v8; // r14
  ULONG v9; // r12d
  ULONG v10; // r12d
  ULONG v11; // r12d
  ULONG v12; // r12d
  struct _ACL *v13; // rax
  struct _ACL *v14; // rbx
  NTSTATUS Acl; // r12d
  BOOLEAN v16; // al
  ACCESS_MASK PreviouslyGrantedAccess[2]; // [rsp+20h] [rbp-89h]
  PPRIVILEGE_SET *Privileges; // [rsp+28h] [rbp-81h]
  PGENERIC_MAPPING GenericMapping; // [rsp+30h] [rbp-79h]
  KPROCESSOR_MODE AccessMode[8]; // [rsp+38h] [rbp-71h]
  PACCESS_MASK GrantedAccess; // [rsp+40h] [rbp-69h]
  int AccessStatus; // [rsp+50h] [rbp-59h] BYREF
  DWORD v24; // [rsp+54h] [rbp-55h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-51h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v27; // [rsp+98h] [rbp-11h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING v29; // [rsp+A8h] [rbp-1h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  v27 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v0 = RtlLengthRequiredSid(2u);
  Pool2 = (void *)ExAllocatePool2(257, v0, 1953656900);
  v2 = RtlLengthRequiredSid(1u);
  v3 = (void *)ExAllocatePool2(257, v2, 1953656900);
  v4 = RtlLengthRequiredSid(6u);
  v5 = (void *)ExAllocatePool2(257, v4, 1953656900);
  v6 = RtlLengthRequiredSid(6u);
  v7 = ExAllocatePool2(257, v6, 1953656900);
  v8 = (void *)v7;
  if ( Pool2 && v3 && v5 && v7 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
    *RtlSubAuthoritySid(Pool2, 0) = 32;
    *RtlSubAuthoritySid(Pool2, 1u) = 544;
    RtlInitializeSid(v3, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(v3, 0) = 18;
    RtlInitializeSidEx(v5, &IdentifierAuthority, 6, 84, 0, 0, 0, 0, 0);
    LODWORD(GrantedAccess) = 2109097600;
    *(_DWORD *)AccessMode = 1466607281;
    LODWORD(GenericMapping) = -1424805804;
    LODWORD(Privileges) = 1617898341;
    PreviouslyGrantedAccess[0] = -123880637;
    RtlInitializeSidEx(
      v8,
      &IdentifierAuthority,
      6,
      80,
      *(_QWORD *)PreviouslyGrantedAccess,
      Privileges,
      GenericMapping,
      *(_QWORD *)AccessMode,
      GrantedAccess);
    v9 = RtlLengthSid(v8);
    v10 = RtlLengthSid(v5) + v9;
    v11 = RtlLengthSid(v3) + v10;
    v12 = RtlLengthSid(Pool2) + 56 + v11;
    v13 = (struct _ACL *)ExAllocatePool2(257, v12, 1953656900);
    v14 = v13;
    if ( v13 )
    {
      Acl = RtlCreateAcl(v13, v12, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v14, 2u, 0x1F0000u, v3);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v14, 2u, 0x1F0000u, Pool2);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v14, 2u, 0x1F0000u, v5);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v14, 2u, 0x1F0000u, v8);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v14, 0);
                if ( Acl >= 0 )
                {
                  v24 = 0;
                  v29.GenericRead = 0x20000;
                  v29.GenericWrite = 0x20000;
                  v29.GenericExecute = 0x20000;
                  v29.GenericAll = 2031616;
                  AccessStatus = 0;
                  v16 = SeAccessCheck(
                          SecurityDescriptor,
                          &SubjectContext,
                          0,
                          0x1F0000u,
                          0,
                          0,
                          &v29,
                          1,
                          &v24,
                          &AccessStatus);
                  Acl = AccessStatus;
                  if ( v16 )
                    Acl = 0;
                }
              }
            }
          }
        }
      }
      ExFreePoolWithTag(v14, 0);
    }
    else
    {
      Acl = -1073741801;
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 1310;
    }
  }
  else
  {
    Acl = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 1319;
  }
  SeReleaseSubjectContext(&SubjectContext);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1403d17d4  push    rbp
0x1403d17d6  push    rbx
0x1403d17d7  push    rsi
0x1403d17d8  push    rdi
0x1403d17d9  push    r12
0x1403d17db  push    r13
0x1403d17dd  push    r14
0x1403d17df  push    r15
0x1403d17e1  lea     rbp, [rsp-1Fh]
0x1403d17e6  sub     rsp, 0C8h
0x1403d17ed  mov     rax, cs:__security_cookie
0x1403d17f4  xor     rax, rsp
0x1403d17f7  mov     [rbp+57h+var_48], rax
0x1403d17fb  xorps   xmm0, xmm0
0x1403d17fe  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1403d1802  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1403d1806  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1403d180a  call    cs:__imp_SeCaptureSubjectContext
0x1403d1811  nop     dword ptr [rax+rax+00h]
0x1403d1816  xor     eax, eax
0x1403d1818  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d181c  xorps   xmm0, xmm0
0x1403d181f  mov     [rbp+57h+var_68], rax
0x1403d1823  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1403d1827  lea     r12d, [rax+1]
0x1403d182b  mov     edx, r12d; Revision
0x1403d182e  movups  [rbp+57h+var_78], xmm0
0x1403d1832  call    cs:__imp_RtlCreateSecurityDescriptor
0x1403d1839  nop     dword ptr [rax+rax+00h]
0x1403d183e  lea     ecx, [r12+1]; SubAuthorityCount
0x1403d1843  call    cs:__imp_RtlLengthRequiredSid
0x1403d184a  nop     dword ptr [rax+rax+00h]
0x1403d184f  mov     r14d, 74727044h
0x1403d1855  mov     r13d, 101h
0x1403d185b  mov     edx, eax
0x1403d185d  mov     r8d, r14d
0x1403d1860  mov     ecx, r13d
0x1403d1863  call    cs:__imp_ExAllocatePool2
0x1403d186a  nop     dword ptr [rax+rax+00h]
0x1403d186f  mov     ecx, r12d; SubAuthorityCount
0x1403d1872  mov     r15, rax
0x1403d1875  call    cs:__imp_RtlLengthRequiredSid
0x1403d187c  nop     dword ptr [rax+rax+00h]
0x1403d1881  mov     edx, eax
0x1403d1883  mov     r8d, r14d
0x1403d1886  mov     ecx, r13d
0x1403d1889  call    cs:__imp_ExAllocatePool2
0x1403d1890  nop     dword ptr [rax+rax+00h]
0x1403d1895  lea     ebx, [r12+5]
0x1403d189a  mov     rdi, rax
0x1403d189d  mov     ecx, ebx; SubAuthorityCount
0x1403d189f  call    cs:__imp_RtlLengthRequiredSid
0x1403d18a6  nop     dword ptr [rax+rax+00h]
0x1403d18ab  mov     edx, eax
0x1403d18ad  mov     r8d, r14d
0x1403d18b0  mov     ecx, r13d
0x1403d18b3  call    cs:__imp_ExAllocatePool2
0x1403d18ba  nop     dword ptr [rax+rax+00h]
0x1403d18bf  mov     ecx, ebx; SubAuthorityCount
0x1403d18c1  mov     rsi, rax
0x1403d18c4  call    cs:__imp_RtlLengthRequiredSid
0x1403d18cb  nop     dword ptr [rax+rax+00h]
0x1403d18d0  mov     edx, eax
0x1403d18d2  mov     r8d, r14d
0x1403d18d5  mov     ecx, r13d
0x1403d18d8  call    cs:__imp_ExAllocatePool2
0x1403d18df  nop     dword ptr [rax+rax+00h]
0x1403d18e4  xor     r13d, r13d
0x1403d18e7  mov     r14, rax
0x1403d18ea  test    r15, r15
0x1403d18ed  jz      loc_1403D1BF4
0x1403d18f3  test    rdi, rdi
0x1403d18f6  jz      loc_1403D1BF4
0x1403d18fc  test    rsi, rsi
0x1403d18ff  jz      loc_1403D1BF4
0x1403d1905  test    rax, rax
0x1403d1908  jz      loc_1403D1BF4
0x1403d190e  mov     r8b, 2; SubAuthorityCount
0x1403d1911  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x1403d1915  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1403d1919  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1403d191f  mov     rcx, r15; Sid
0x1403d1922  call    cs:__imp_RtlInitializeSid
0x1403d1929  nop     dword ptr [rax+rax+00h]
0x1403d192e  xor     edx, edx; SubAuthority
0x1403d1930  mov     rcx, r15; Sid
0x1403d1933  call    cs:__imp_RtlSubAuthoritySid
0x1403d193a  nop     dword ptr [rax+rax+00h]
0x1403d193f  mov     edx, r12d; SubAuthority
0x1403d1942  mov     rcx, r15; Sid
0x1403d1945  mov     dword ptr [rax], 20h ; ' '
0x1403d194b  call    cs:__imp_RtlSubAuthoritySid
0x1403d1952  nop     dword ptr [rax+rax+00h]
0x1403d1957  mov     r8b, r12b; SubAuthorityCount
0x1403d195a  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1403d195e  mov     rcx, rdi; Sid
0x1403d1961  mov     dword ptr [rax], 220h
0x1403d1967  call    cs:__imp_RtlInitializeSid
0x1403d196e  nop     dword ptr [rax+rax+00h]
0x1403d1973  xor     edx, edx; SubAuthority
0x1403d1975  mov     rcx, rdi; Sid
0x1403d1978  call    cs:__imp_RtlSubAuthoritySid
0x1403d197f  nop     dword ptr [rax+rax+00h]
0x1403d1984  mov     [rsp+100h+GrantedAccess], r13
0x1403d1989  lea     r9d, [r12+53h]
0x1403d198e  mov     qword ptr [rsp+100h+AccessMode], r13
0x1403d1993  lea     rdx, [rbp+57h+IdentifierAuthority]
0x1403d1997  mov     [rsp+100h+GenericMapping], r13
0x1403d199c  mov     r8d, ebx
0x1403d199f  mov     [rsp+100h+Privileges], r13
0x1403d19a4  mov     rcx, rsi
0x1403d19a7  mov     dword ptr [rax], 12h
0x1403d19ad  mov     qword ptr [rsp+100h+PreviouslyGrantedAccess], r13
0x1403d19b2  call    cs:__imp_RtlInitializeSidEx
0x1403d19b9  nop     dword ptr [rax+rax+00h]
0x1403d19be  mov     dword ptr [rsp+100h+GrantedAccess], 7DB64680h
0x1403d19c6  lea     r9d, [r12+4Fh]
0x1403d19cb  mov     dword ptr [rsp+100h+AccessMode], 576AA6B1h
0x1403d19d3  lea     rdx, [rbp+57h+IdentifierAuthority]
0x1403d19d7  mov     dword ptr [rsp+100h+GenericMapping], 0AB133054h
0x1403d19df  mov     r8d, ebx
0x1403d19e2  mov     dword ptr [rsp+100h+Privileges], 606F2B65h
0x1403d19ea  mov     rcx, r14
0x1403d19ed  mov     [rsp+100h+PreviouslyGrantedAccess], 0F89DBB43h
0x1403d19f5  call    cs:__imp_RtlInitializeSidEx
0x1403d19fc  nop     dword ptr [rax+rax+00h]
0x1403d1a01  mov     rcx, r14; Sid
0x1403d1a04  call    cs:__imp_RtlLengthSid
0x1403d1a0b  nop     dword ptr [rax+rax+00h]
0x1403d1a10  mov     rcx, rsi; Sid
0x1403d1a13  mov     r12d, eax
0x1403d1a16  call    cs:__imp_RtlLengthSid
0x1403d1a1d  nop     dword ptr [rax+rax+00h]
0x1403d1a22  mov     rcx, rdi; Sid
0x1403d1a25  add     r12d, eax
0x1403d1a28  call    cs:__imp_RtlLengthSid
0x1403d1a2f  nop     dword ptr [rax+rax+00h]
0x1403d1a34  mov     rcx, r15; Sid
0x1403d1a37  add     r12d, eax
0x1403d1a3a  call    cs:__imp_RtlLengthSid
0x1403d1a41  nop     dword ptr [rax+rax+00h]
0x1403d1a46  mov     ecx, 101h
0x1403d1a4b  mov     r8d, 74727044h
0x1403d1a51  add     eax, 38h ; '8'
0x1403d1a54  add     r12d, eax
0x1403d1a57  mov     edx, r12d
0x1403d1a5a  call    cs:__imp_ExAllocatePool2
0x1403d1a61  nop     dword ptr [rax+rax+00h]
0x1403d1a66  mov     rbx, rax
0x1403d1a69  test    rax, rax
0x1403d1a6c  jz      loc_1403D1BCD
0x1403d1a72  lea     r8d, [r13+2]; AclRevision
0x1403d1a76  mov     edx, r12d; AclLength
0x1403d1a79  mov     rcx, rax; Acl
0x1403d1a7c  call    cs:__imp_RtlCreateAcl
0x1403d1a83  nop     dword ptr [rax+rax+00h]
0x1403d1a88  mov     r12d, eax
0x1403d1a8b  test    eax, eax
0x1403d1a8d  js      loc_1403D1BBA
0x1403d1a93  mov     r9, rdi; Sid
0x1403d1a96  lea     edx, [r13+2]; AceRevision
0x1403d1a9a  mov     r8d, 1F0000h; AccessMask
0x1403d1aa0  mov     rcx, rbx; Acl
0x1403d1aa3  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1aaa  nop     dword ptr [rax+rax+00h]
0x1403d1aaf  mov     r12d, eax
0x1403d1ab2  test    eax, eax
0x1403d1ab4  js      loc_1403D1BBA
0x1403d1aba  mov     r9, r15; Sid
0x1403d1abd  lea     edx, [r13+2]; AceRevision
0x1403d1ac1  mov     r8d, 1F0000h; AccessMask
0x1403d1ac7  mov     rcx, rbx; Acl
0x1403d1aca  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1ad1  nop     dword ptr [rax+rax+00h]
0x1403d1ad6  mov     r12d, eax
0x1403d1ad9  test    eax, eax
0x1403d1adb  js      loc_1403D1BBA
0x1403d1ae1  mov     r9, rsi; Sid
0x1403d1ae4  lea     edx, [r13+2]; AceRevision
0x1403d1ae8  mov     r8d, 1F0000h; AccessMask
0x1403d1aee  mov     rcx, rbx; Acl
0x1403d1af1  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1af8  nop     dword ptr [rax+rax+00h]
0x1403d1afd  mov     r12d, eax
0x1403d1b00  test    eax, eax
0x1403d1b02  js      loc_1403D1BBA
0x1403d1b08  mov     r9, r14; Sid
0x1403d1b0b  lea     edx, [r13+2]; AceRevision
0x1403d1b0f  mov     r8d, 1F0000h; AccessMask
0x1403d1b15  mov     rcx, rbx; Acl
0x1403d1b18  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1b1f  nop     dword ptr [rax+rax+00h]
0x1403d1b24  mov     r12d, eax
0x1403d1b27  test    eax, eax
0x1403d1b29  js      loc_1403D1BBA
0x1403d1b2f  xor     r9d, r9d; DaclDefaulted
0x1403d1b32  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d1b36  mov     r8, rbx; Dacl
0x1403d1b39  mov     dl, 1; DaclPresent
0x1403d1b3b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1403d1b42  nop     dword ptr [rax+rax+00h]
0x1403d1b47  mov     r12d, eax
0x1403d1b4a  test    eax, eax
0x1403d1b4c  js      short loc_1403D1BBA
0x1403d1b4e  mov     eax, 20000h
0x1403d1b53  mov     [rbp+57h+var_AC], r13d
0x1403d1b57  mov     [rbp+57h+var_58.GenericRead], eax
0x1403d1b5a  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1403d1b5e  mov     [rbp+57h+var_58.GenericWrite], eax
0x1403d1b61  mov     ecx, 1F0000h
0x1403d1b66  mov     [rbp+57h+var_58.GenericExecute], eax
0x1403d1b69  mov     r9d, ecx; DesiredAccess
0x1403d1b6c  lea     rax, [rbp+57h+var_B0]
0x1403d1b70  mov     [rbp+57h+var_58.GenericAll], ecx
0x1403d1b73  mov     [rsp+100h+AccessStatus], rax; AccessStatus
0x1403d1b78  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d1b7c  lea     rax, [rbp+57h+var_AC]
0x1403d1b80  mov     [rbp+57h+var_B0], r13d
0x1403d1b84  mov     [rsp+100h+GrantedAccess], rax; GrantedAccess
0x1403d1b89  xor     r8d, r8d; SubjectContextLocked
0x1403d1b8c  mov     [rsp+100h+AccessMode], 1; AccessMode
0x1403d1b91  lea     rax, [rbp+57h+var_58]
0x1403d1b95  mov     [rsp+100h+GenericMapping], rax; GenericMapping
0x1403d1b9a  mov     [rsp+100h+Privileges], r13; Privileges
0x1403d1b9f  mov     [rsp+100h+PreviouslyGrantedAccess], r13d; PreviouslyGrantedAccess
0x1403d1ba4  call    cs:__imp_SeAccessCheck
0x1403d1bab  nop     dword ptr [rax+rax+00h]
0x1403d1bb0  mov     r12d, [rbp+57h+var_B0]
0x1403d1bb4  test    al, al
0x1403d1bb6  cmovnz  r12d, r13d
0x1403d1bba  xor     edx, edx; Tag
0x1403d1bbc  mov     rcx, rbx; P
0x1403d1bbf  call    cs:__imp_ExFreePoolWithTag
0x1403d1bc6  nop     dword ptr [rax+rax+00h]
0x1403d1bcb  jmp     short loc_1403D1C16
0x1403d1bcd  mov     rdx, 0FFFFFFFFC0000017h
0x1403d1bd4  mov     r12d, edx
0x1403d1bd7  mov     ecx, 6
0x1403d1bdc  call    cs:__imp_WdLogSingleEntry1
0x1403d1be3  nop     dword ptr [rax+rax+00h]
0x1403d1be8  mov     cs:WdLogGlobalForLineNumber, 51Eh
0x1403d1bf2  jmp     short loc_1403D1C16
0x1403d1bf4  mov     rdx, 0FFFFFFFFC0000017h
0x1403d1bfb  mov     r12d, edx
0x1403d1bfe  mov     ecx, ebx
0x1403d1c00  call    cs:__imp_WdLogSingleEntry1
0x1403d1c07  nop     dword ptr [rax+rax+00h]
0x1403d1c0c  mov     cs:WdLogGlobalForLineNumber, 527h
0x1403d1c16  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1403d1c1a  call    cs:__imp_SeReleaseSubjectContext
0x1403d1c21  nop     dword ptr [rax+rax+00h]
0x1403d1c26  test    r14, r14
0x1403d1c29  jz      short loc_1403D1C3C
0x1403d1c2b  xor     edx, edx; Tag
0x1403d1c2d  mov     rcx, r14; P
0x1403d1c30  call    cs:__imp_ExFreePoolWithTag
0x1403d1c37  nop     dword ptr [rax+rax+00h]
0x1403d1c3c  test    rsi, rsi
0x1403d1c3f  jz      short loc_1403D1C52
0x1403d1c41  xor     edx, edx; Tag
0x1403d1c43  mov     rcx, rsi; P
0x1403d1c46  call    cs:__imp_ExFreePoolWithTag
0x1403d1c4d  nop     dword ptr [rax+rax+00h]
0x1403d1c52  test    rdi, rdi
0x1403d1c55  jz      short loc_1403D1C68
0x1403d1c57  xor     edx, edx; Tag
0x1403d1c59  mov     rcx, rdi; P
0x1403d1c5c  call    cs:__imp_ExFreePoolWithTag
0x1403d1c63  nop     dword ptr [rax+rax+00h]
0x1403d1c68  test    r15, r15
0x1403d1c6b  jz      short loc_1403D1C7E
0x1403d1c6d  xor     edx, edx; Tag
0x1403d1c6f  mov     rcx, r15; P
0x1403d1c72  call    cs:__imp_ExFreePoolWithTag
0x1403d1c79  nop     dword ptr [rax+rax+00h]
0x1403d1c7e  mov     eax, r12d
0x1403d1c81  mov     rcx, [rbp+57h+var_48]
0x1403d1c85  xor     rcx, rsp; StackCookie
0x1403d1c88  call    __security_check_cookie
0x1403d1c8d  add     rsp, 0C8h
0x1403d1c94  pop     r15
0x1403d1c96  pop     r14
0x1403d1c98  pop     r13
0x1403d1c9a  pop     r12
0x1403d1c9c  pop     rdi
0x1403d1c9d  pop     rsi
0x1403d1c9e  pop     rbx
0x1403d1c9f  pop     rbp
0x1403d1ca0  retn
```
