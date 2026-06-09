# DpiIndirectEscapeAccessCheck(void)

- ea: `0x1403d1bf8`
- end: `0x1403d20c6`
- name: `?DpiIndirectEscapeAccessCheck@@YAJXZ`
- size: `1230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1403d14cc`

## callees

- `0x1400a0bd0`
- `0x1403d1bf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1fe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2054`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d206a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2080`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2096`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d1fe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2054`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d206a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2080`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d2096`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1c87`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cad`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cd7`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cfc`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1e7e`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1c87`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cad`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cd7`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1cfc`
- `ntoskrnl!ExAllocatePool2` at `0x1403d1e7e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1403d1c2e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1403d1c2e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1403d1c56`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1403d1c56`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1c67`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1c99`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1cc3`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1ce8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1c67`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1c99`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1cc3`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1403d1ce8`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1d46`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1d8b`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1d46`
- `ntoskrnl!RtlInitializeSid` at `0x1403d1d8b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d57`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d6f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d9c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d57`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d6f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1403d1d9c`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e28`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e3a`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e4c`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e5e`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e28`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e3a`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e4c`
- `ntoskrnl!RtlLengthSid` at `0x1403d1e5e`
- `ntoskrnl!RtlCreateAcl` at `0x1403d1ea0`
- `ntoskrnl!RtlCreateAcl` at `0x1403d1ea0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1ec7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1eee`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1f15`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1f3c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1ec7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1eee`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1f15`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1403d1f3c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1403d1f5f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1403d1f5f`
- `ntoskrnl!SeAccessCheck` at `0x1403d1fc8`
- `ntoskrnl!SeAccessCheck` at `0x1403d1fc8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1403d203e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1403d203e`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d1dd6`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d1e19`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d1dd6`
- `ntoskrnl!RtlInitializeSidEx` at `0x1403d1e19`
- `watchdog!WdLogSingleEntry1` at `0x1403d2000`
- `watchdog!WdLogSingleEntry1` at `0x1403d2024`
- `watchdog!WdLogSingleEntry1` at `0x1403d2000`
- `watchdog!WdLogSingleEntry1` at `0x1403d2024`

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
      WdLogSingleEntry1(6, -1073741801);
      WdLogGlobalForLineNumber = 1353;
    }
  }
  else
  {
    Acl = -1073741801;
    WdLogSingleEntry1(6, -1073741801);
    WdLogGlobalForLineNumber = 1362;
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
0x1403d1bf8  push    rbp
0x1403d1bfa  push    rbx
0x1403d1bfb  push    rsi
0x1403d1bfc  push    rdi
0x1403d1bfd  push    r12
0x1403d1bff  push    r13
0x1403d1c01  push    r14
0x1403d1c03  push    r15
0x1403d1c05  lea     rbp, [rsp-1Fh]
0x1403d1c0a  sub     rsp, 0C8h
0x1403d1c11  mov     rax, cs:__security_cookie
0x1403d1c18  xor     rax, rsp
0x1403d1c1b  mov     [rbp+57h+var_48], rax
0x1403d1c1f  xorps   xmm0, xmm0
0x1403d1c22  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1403d1c26  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1403d1c2a  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1403d1c2e  call    cs:__imp_SeCaptureSubjectContext
0x1403d1c35  nop     dword ptr [rax+rax+00h]
0x1403d1c3a  xor     eax, eax
0x1403d1c3c  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d1c40  xorps   xmm0, xmm0
0x1403d1c43  mov     [rbp+57h+var_68], rax
0x1403d1c47  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1403d1c4b  lea     r12d, [rax+1]
0x1403d1c4f  mov     edx, r12d; Revision
0x1403d1c52  movups  [rbp+57h+var_78], xmm0
0x1403d1c56  call    cs:__imp_RtlCreateSecurityDescriptor
0x1403d1c5d  nop     dword ptr [rax+rax+00h]
0x1403d1c62  lea     ecx, [r12+1]; SubAuthorityCount
0x1403d1c67  call    cs:__imp_RtlLengthRequiredSid
0x1403d1c6e  nop     dword ptr [rax+rax+00h]
0x1403d1c73  mov     r14d, 74727044h
0x1403d1c79  mov     r13d, 101h
0x1403d1c7f  mov     edx, eax
0x1403d1c81  mov     r8d, r14d
0x1403d1c84  mov     ecx, r13d
0x1403d1c87  call    cs:__imp_ExAllocatePool2
0x1403d1c8e  nop     dword ptr [rax+rax+00h]
0x1403d1c93  mov     ecx, r12d; SubAuthorityCount
0x1403d1c96  mov     r15, rax
0x1403d1c99  call    cs:__imp_RtlLengthRequiredSid
0x1403d1ca0  nop     dword ptr [rax+rax+00h]
0x1403d1ca5  mov     edx, eax
0x1403d1ca7  mov     r8d, r14d
0x1403d1caa  mov     ecx, r13d
0x1403d1cad  call    cs:__imp_ExAllocatePool2
0x1403d1cb4  nop     dword ptr [rax+rax+00h]
0x1403d1cb9  lea     ebx, [r12+5]
0x1403d1cbe  mov     rdi, rax
0x1403d1cc1  mov     ecx, ebx; SubAuthorityCount
0x1403d1cc3  call    cs:__imp_RtlLengthRequiredSid
0x1403d1cca  nop     dword ptr [rax+rax+00h]
0x1403d1ccf  mov     edx, eax
0x1403d1cd1  mov     r8d, r14d
0x1403d1cd4  mov     ecx, r13d
0x1403d1cd7  call    cs:__imp_ExAllocatePool2
0x1403d1cde  nop     dword ptr [rax+rax+00h]
0x1403d1ce3  mov     ecx, ebx; SubAuthorityCount
0x1403d1ce5  mov     rsi, rax
0x1403d1ce8  call    cs:__imp_RtlLengthRequiredSid
0x1403d1cef  nop     dword ptr [rax+rax+00h]
0x1403d1cf4  mov     edx, eax
0x1403d1cf6  mov     r8d, r14d
0x1403d1cf9  mov     ecx, r13d
0x1403d1cfc  call    cs:__imp_ExAllocatePool2
0x1403d1d03  nop     dword ptr [rax+rax+00h]
0x1403d1d08  xor     r13d, r13d
0x1403d1d0b  mov     r14, rax
0x1403d1d0e  test    r15, r15
0x1403d1d11  jz      loc_1403D2018
0x1403d1d17  test    rdi, rdi
0x1403d1d1a  jz      loc_1403D2018
0x1403d1d20  test    rsi, rsi
0x1403d1d23  jz      loc_1403D2018
0x1403d1d29  test    rax, rax
0x1403d1d2c  jz      loc_1403D2018
0x1403d1d32  mov     r8b, 2; SubAuthorityCount
0x1403d1d35  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r13d
0x1403d1d39  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1403d1d3d  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1403d1d43  mov     rcx, r15; Sid
0x1403d1d46  call    cs:__imp_RtlInitializeSid
0x1403d1d4d  nop     dword ptr [rax+rax+00h]
0x1403d1d52  xor     edx, edx; SubAuthority
0x1403d1d54  mov     rcx, r15; Sid
0x1403d1d57  call    cs:__imp_RtlSubAuthoritySid
0x1403d1d5e  nop     dword ptr [rax+rax+00h]
0x1403d1d63  mov     edx, r12d; SubAuthority
0x1403d1d66  mov     rcx, r15; Sid
0x1403d1d69  mov     dword ptr [rax], 20h ; ' '
0x1403d1d6f  call    cs:__imp_RtlSubAuthoritySid
0x1403d1d76  nop     dword ptr [rax+rax+00h]
0x1403d1d7b  mov     r8b, r12b; SubAuthorityCount
0x1403d1d7e  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1403d1d82  mov     rcx, rdi; Sid
0x1403d1d85  mov     dword ptr [rax], 220h
0x1403d1d8b  call    cs:__imp_RtlInitializeSid
0x1403d1d92  nop     dword ptr [rax+rax+00h]
0x1403d1d97  xor     edx, edx; SubAuthority
0x1403d1d99  mov     rcx, rdi; Sid
0x1403d1d9c  call    cs:__imp_RtlSubAuthoritySid
0x1403d1da3  nop     dword ptr [rax+rax+00h]
0x1403d1da8  mov     [rsp+100h+GrantedAccess], r13
0x1403d1dad  lea     r9d, [r12+53h]
0x1403d1db2  mov     qword ptr [rsp+100h+AccessMode], r13
0x1403d1db7  lea     rdx, [rbp+57h+IdentifierAuthority]
0x1403d1dbb  mov     [rsp+100h+GenericMapping], r13
0x1403d1dc0  mov     r8d, ebx
0x1403d1dc3  mov     [rsp+100h+Privileges], r13
0x1403d1dc8  mov     rcx, rsi
0x1403d1dcb  mov     dword ptr [rax], 12h
0x1403d1dd1  mov     qword ptr [rsp+100h+PreviouslyGrantedAccess], r13
0x1403d1dd6  call    cs:__imp_RtlInitializeSidEx
0x1403d1ddd  nop     dword ptr [rax+rax+00h]
0x1403d1de2  mov     dword ptr [rsp+100h+GrantedAccess], 7DB64680h
0x1403d1dea  lea     r9d, [r12+4Fh]
0x1403d1def  mov     dword ptr [rsp+100h+AccessMode], 576AA6B1h
0x1403d1df7  lea     rdx, [rbp+57h+IdentifierAuthority]
0x1403d1dfb  mov     dword ptr [rsp+100h+GenericMapping], 0AB133054h
0x1403d1e03  mov     r8d, ebx
0x1403d1e06  mov     dword ptr [rsp+100h+Privileges], 606F2B65h
0x1403d1e0e  mov     rcx, r14
0x1403d1e11  mov     [rsp+100h+PreviouslyGrantedAccess], 0F89DBB43h
0x1403d1e19  call    cs:__imp_RtlInitializeSidEx
0x1403d1e20  nop     dword ptr [rax+rax+00h]
0x1403d1e25  mov     rcx, r14; Sid
0x1403d1e28  call    cs:__imp_RtlLengthSid
0x1403d1e2f  nop     dword ptr [rax+rax+00h]
0x1403d1e34  mov     rcx, rsi; Sid
0x1403d1e37  mov     r12d, eax
0x1403d1e3a  call    cs:__imp_RtlLengthSid
0x1403d1e41  nop     dword ptr [rax+rax+00h]
0x1403d1e46  mov     rcx, rdi; Sid
0x1403d1e49  add     r12d, eax
0x1403d1e4c  call    cs:__imp_RtlLengthSid
0x1403d1e53  nop     dword ptr [rax+rax+00h]
0x1403d1e58  mov     rcx, r15; Sid
0x1403d1e5b  add     r12d, eax
0x1403d1e5e  call    cs:__imp_RtlLengthSid
0x1403d1e65  nop     dword ptr [rax+rax+00h]
0x1403d1e6a  mov     ecx, 101h
0x1403d1e6f  mov     r8d, 74727044h
0x1403d1e75  add     eax, 38h ; '8'
0x1403d1e78  add     r12d, eax
0x1403d1e7b  mov     edx, r12d
0x1403d1e7e  call    cs:__imp_ExAllocatePool2
0x1403d1e85  nop     dword ptr [rax+rax+00h]
0x1403d1e8a  mov     rbx, rax
0x1403d1e8d  test    rax, rax
0x1403d1e90  jz      loc_1403D1FF1
0x1403d1e96  lea     r8d, [r13+2]; AclRevision
0x1403d1e9a  mov     edx, r12d; AclLength
0x1403d1e9d  mov     rcx, rax; Acl
0x1403d1ea0  call    cs:__imp_RtlCreateAcl
0x1403d1ea7  nop     dword ptr [rax+rax+00h]
0x1403d1eac  mov     r12d, eax
0x1403d1eaf  test    eax, eax
0x1403d1eb1  js      loc_1403D1FDE
0x1403d1eb7  mov     r9, rdi; Sid
0x1403d1eba  lea     edx, [r13+2]; AceRevision
0x1403d1ebe  mov     r8d, 1F0000h; AccessMask
0x1403d1ec4  mov     rcx, rbx; Acl
0x1403d1ec7  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1ece  nop     dword ptr [rax+rax+00h]
0x1403d1ed3  mov     r12d, eax
0x1403d1ed6  test    eax, eax
0x1403d1ed8  js      loc_1403D1FDE
0x1403d1ede  mov     r9, r15; Sid
0x1403d1ee1  lea     edx, [r13+2]; AceRevision
0x1403d1ee5  mov     r8d, 1F0000h; AccessMask
0x1403d1eeb  mov     rcx, rbx; Acl
0x1403d1eee  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1ef5  nop     dword ptr [rax+rax+00h]
0x1403d1efa  mov     r12d, eax
0x1403d1efd  test    eax, eax
0x1403d1eff  js      loc_1403D1FDE
0x1403d1f05  mov     r9, rsi; Sid
0x1403d1f08  lea     edx, [r13+2]; AceRevision
0x1403d1f0c  mov     r8d, 1F0000h; AccessMask
0x1403d1f12  mov     rcx, rbx; Acl
0x1403d1f15  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1f1c  nop     dword ptr [rax+rax+00h]
0x1403d1f21  mov     r12d, eax
0x1403d1f24  test    eax, eax
0x1403d1f26  js      loc_1403D1FDE
0x1403d1f2c  mov     r9, r14; Sid
0x1403d1f2f  lea     edx, [r13+2]; AceRevision
0x1403d1f33  mov     r8d, 1F0000h; AccessMask
0x1403d1f39  mov     rcx, rbx; Acl
0x1403d1f3c  call    cs:__imp_RtlAddAccessAllowedAce
0x1403d1f43  nop     dword ptr [rax+rax+00h]
0x1403d1f48  mov     r12d, eax
0x1403d1f4b  test    eax, eax
0x1403d1f4d  js      loc_1403D1FDE
0x1403d1f53  xor     r9d, r9d; DaclDefaulted
0x1403d1f56  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d1f5a  mov     r8, rbx; Dacl
0x1403d1f5d  mov     dl, 1; DaclPresent
0x1403d1f5f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1403d1f66  nop     dword ptr [rax+rax+00h]
0x1403d1f6b  mov     r12d, eax
0x1403d1f6e  test    eax, eax
0x1403d1f70  js      short loc_1403D1FDE
0x1403d1f72  mov     eax, 20000h
0x1403d1f77  mov     [rbp+57h+var_AC], r13d
0x1403d1f7b  mov     [rbp+57h+var_58.GenericRead], eax
0x1403d1f7e  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1403d1f82  mov     [rbp+57h+var_58.GenericWrite], eax
0x1403d1f85  mov     ecx, 1F0000h
0x1403d1f8a  mov     [rbp+57h+var_58.GenericExecute], eax
0x1403d1f8d  mov     r9d, ecx; DesiredAccess
0x1403d1f90  lea     rax, [rbp+57h+var_B0]
0x1403d1f94  mov     [rbp+57h+var_58.GenericAll], ecx
0x1403d1f97  mov     [rsp+100h+AccessStatus], rax; AccessStatus
0x1403d1f9c  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1403d1fa0  lea     rax, [rbp+57h+var_AC]
0x1403d1fa4  mov     [rbp+57h+var_B0], r13d
0x1403d1fa8  mov     [rsp+100h+GrantedAccess], rax; GrantedAccess
0x1403d1fad  xor     r8d, r8d; SubjectContextLocked
0x1403d1fb0  mov     [rsp+100h+AccessMode], 1; AccessMode
0x1403d1fb5  lea     rax, [rbp+57h+var_58]
0x1403d1fb9  mov     [rsp+100h+GenericMapping], rax; GenericMapping
0x1403d1fbe  mov     [rsp+100h+Privileges], r13; Privileges
0x1403d1fc3  mov     [rsp+100h+PreviouslyGrantedAccess], r13d; PreviouslyGrantedAccess
0x1403d1fc8  call    cs:__imp_SeAccessCheck
0x1403d1fcf  nop     dword ptr [rax+rax+00h]
0x1403d1fd4  mov     r12d, [rbp+57h+var_B0]
0x1403d1fd8  test    al, al
0x1403d1fda  cmovnz  r12d, r13d
0x1403d1fde  xor     edx, edx; Tag
0x1403d1fe0  mov     rcx, rbx; P
0x1403d1fe3  call    cs:__imp_ExFreePoolWithTag
0x1403d1fea  nop     dword ptr [rax+rax+00h]
0x1403d1fef  jmp     short loc_1403D203A
0x1403d1ff1  mov     rdx, 0FFFFFFFFC0000017h
0x1403d1ff8  mov     r12d, edx
0x1403d1ffb  mov     ecx, 6
0x1403d2000  call    cs:__imp_WdLogSingleEntry1
0x1403d2007  nop     dword ptr [rax+rax+00h]
0x1403d200c  mov     cs:WdLogGlobalForLineNumber, 549h
0x1403d2016  jmp     short loc_1403D203A
0x1403d2018  mov     rdx, 0FFFFFFFFC0000017h
0x1403d201f  mov     r12d, edx
0x1403d2022  mov     ecx, ebx
0x1403d2024  call    cs:__imp_WdLogSingleEntry1
0x1403d202b  nop     dword ptr [rax+rax+00h]
0x1403d2030  mov     cs:WdLogGlobalForLineNumber, 552h
0x1403d203a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1403d203e  call    cs:__imp_SeReleaseSubjectContext
0x1403d2045  nop     dword ptr [rax+rax+00h]
0x1403d204a  test    r14, r14
0x1403d204d  jz      short loc_1403D2060
0x1403d204f  xor     edx, edx; Tag
0x1403d2051  mov     rcx, r14; P
0x1403d2054  call    cs:__imp_ExFreePoolWithTag
0x1403d205b  nop     dword ptr [rax+rax+00h]
0x1403d2060  test    rsi, rsi
0x1403d2063  jz      short loc_1403D2076
0x1403d2065  xor     edx, edx; Tag
0x1403d2067  mov     rcx, rsi; P
0x1403d206a  call    cs:__imp_ExFreePoolWithTag
0x1403d2071  nop     dword ptr [rax+rax+00h]
0x1403d2076  test    rdi, rdi
0x1403d2079  jz      short loc_1403D208C
0x1403d207b  xor     edx, edx; Tag
0x1403d207d  mov     rcx, rdi; P
0x1403d2080  call    cs:__imp_ExFreePoolWithTag
0x1403d2087  nop     dword ptr [rax+rax+00h]
0x1403d208c  test    r15, r15
0x1403d208f  jz      short loc_1403D20A2
0x1403d2091  xor     edx, edx; Tag
0x1403d2093  mov     rcx, r15; P
0x1403d2096  call    cs:__imp_ExFreePoolWithTag
0x1403d209d  nop     dword ptr [rax+rax+00h]
0x1403d20a2  mov     eax, r12d
0x1403d20a5  mov     rcx, [rbp+57h+var_48]
0x1403d20a9  xor     rcx, rsp; StackCookie
0x1403d20ac  call    __security_check_cookie
0x1403d20b1  add     rsp, 0C8h
0x1403d20b8  pop     r15
0x1403d20ba  pop     r14
0x1403d20bc  pop     r13
0x1403d20be  pop     r12
0x1403d20c0  pop     rdi
0x1403d20c1  pop     rsi
0x1403d20c2  pop     rbx
0x1403d20c3  pop     rbp
0x1403d20c4  retn
```
