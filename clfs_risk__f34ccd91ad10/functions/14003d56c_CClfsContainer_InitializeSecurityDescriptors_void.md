# CClfsContainer::InitializeSecurityDescriptors(void)

- ea: `0x14003d56c`
- end: `0x14003db41`
- name: `?InitializeSecurityDescriptors@CClfsContainer@@CAJXZ`
- size: `1493`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003d274`

## callees

- `0x140017e40`
- `0x14003d56c`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003d7d3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003da64`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003d7d3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003da64`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003d780`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003da18`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003d780`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003da18`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003d638`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003d638`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003da90`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007dfdf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003da90`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007dfdf`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d64e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d831`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d865`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d64e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d831`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003d865`
- `ntoskrnl!RtlInitializeSid` at `0x14003d68f`
- `ntoskrnl!RtlInitializeSid` at `0x14003d8ac`
- `ntoskrnl!RtlInitializeSid` at `0x14003d8f4`
- `ntoskrnl!RtlInitializeSid` at `0x14003d68f`
- `ntoskrnl!RtlInitializeSid` at `0x14003d8ac`
- `ntoskrnl!RtlInitializeSid` at `0x14003d8f4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d6a0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d8bd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d8d4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d905`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d6a0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d8bd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d8d4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003d905`
- `ntoskrnl!RtlCreateAcl` at `0x14003d6f0`
- `ntoskrnl!RtlCreateAcl` at `0x14003d965`
- `ntoskrnl!RtlCreateAcl` at `0x14003d6f0`
- `ntoskrnl!RtlCreateAcl` at `0x14003d965`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d71a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d990`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d9bb`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d71a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d990`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003d9bb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d740`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d7ef`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d9df`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d740`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d7ef`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003d9df`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003d766`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003d812`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003da02`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003d766`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003d812`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003da02`
- `ntoskrnl!SeAssignSecurity` at `0x14003d7b2`
- `ntoskrnl!SeAssignSecurity` at `0x14003da47`
- `ntoskrnl!SeAssignSecurity` at `0x14003d7b2`
- `ntoskrnl!SeAssignSecurity` at `0x14003da47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003daa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dacd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003daf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003db0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e013`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e051`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e070`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e08f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003daa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dacd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003daf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003db0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e013`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e051`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e070`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e08f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d60e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d664`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d6ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d84f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d878`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d93d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d60e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d664`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d6ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d84f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d878`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d93d`

## pseudocode

```c
__int64 CClfsContainer::InitializeSecurityDescriptors(void)
{
  unsigned __int8 *v0; // r13
  unsigned __int8 *v1; // r12
  unsigned __int8 *v2; // rsi
  struct _ACL *v3; // r15
  struct _ACL *v4; // r14
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rdi
  ULONG v7; // eax
  unsigned __int8 *v8; // rax
  ULONG v9; // ebx
  struct _ACL *v10; // rax
  NTSTATUS Acl; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  ULONG v13; // eax
  ULONG v14; // eax
  unsigned __int8 *v15; // rax
  ULONG v16; // ebx
  struct _ACL *v17; // rax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  char v20; // [rsp+40h] [rbp-D8h]
  _OWORD ExplicitDescriptor[2]; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+98h] [rbp-80h]
  _BYTE SecurityDescriptor[32]; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v24; // [rsp+C0h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY v25; // [rsp+C8h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+D0h] [rbp-48h] BYREF

  *(_DWORD *)v25.Value = 0;
  *(_WORD *)&v25.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v20 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v24 = 0;
  memset(ExplicitDescriptor, 0, sizeof(ExplicitDescriptor));
  v22 = 0;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(PagedPool, 0x20u, 0x73666C43u);
  SubjectContext = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_24;
  *(_OWORD *)&PoolWithTag->ClientToken = 0;
  *(_OWORD *)&PoolWithTag->PrimaryToken = 0;
  SeCaptureSubjectContext(PoolWithTag);
  v20 = 1;
  v7 = RtlLengthRequiredSid(1u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v7, 0x73666C43u);
  v2 = v8;
  if ( !v8 )
    goto LABEL_24;
  RtlInitializeSid(v8, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v2, 0) = 0;
  v9 = (4 * v2[1] + 35) & 0xFFFFFFF8;
  v10 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v9, 0x73666C43u);
  v4 = v10;
  if ( !v10 )
    goto LABEL_24;
  Acl = RtlCreateAcl(v10, v9, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v4, 2u, 0x10000000u, v2);
    if ( Acl >= 0 )
    {
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
        Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v4, 0);
      if ( Acl >= 0 )
      {
        GenericMapping = IoGetFileObjectGenericMapping();
        Acl = SeAssignSecurity(
                0,
                SecurityDescriptor,
                &CClfsContainer::m_psdNoSecurity,
                0,
                SubjectContext,
                GenericMapping,
                PagedPool);
        if ( Acl >= 0 )
        {
          LODWORD(CClfsContainer::m_cbNoSecurity) = RtlLengthSecurityDescriptor(CClfsContainer::m_psdNoSecurity);
          Acl = RtlCreateSecurityDescriptor(ExplicitDescriptor, 1u);
          if ( Acl >= 0 )
            Acl = RtlSetDaclSecurityDescriptor(ExplicitDescriptor, 1u, 0, 0);
          if ( Acl >= 0 )
          {
            v13 = RtlLengthRequiredSid(2u);
            v0 = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v13, 0x73666C43u);
            v14 = RtlLengthRequiredSid(1u);
            v15 = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v14, 0x73666C43u);
            v1 = v15;
            if ( v0 )
            {
              if ( v15 )
              {
                RtlInitializeSid(v0, &v25, 2u);
                *RtlSubAuthoritySid(v0, 0) = 32;
                *RtlSubAuthoritySid(v0, 1u) = 544;
                RtlInitializeSid(v1, &v25, 1u);
                *RtlSubAuthoritySid(v1, 0) = 18;
                v16 = (4 * (v0[1] + v1[1]) + 55) & 0xFFFFFFF8;
                v17 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v16, 0x73666C43u);
                v3 = v17;
                if ( v17 )
                {
                  Acl = RtlCreateAcl(v17, v16, 2u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlAddAccessAllowedAce(v3, 2u, 0x10000000u, v0);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlAddAccessAllowedAce(v3, 2u, 0x10000000u, v1);
                      if ( Acl >= 0 )
                      {
                        Acl = RtlCreateSecurityDescriptor(ExplicitDescriptor, 1u);
                        if ( Acl >= 0 )
                          Acl = RtlSetDaclSecurityDescriptor(ExplicitDescriptor, 1u, v3, 0);
                        if ( Acl >= 0 )
                        {
                          FileObjectGenericMapping = IoGetFileObjectGenericMapping();
                          Acl = SeAssignSecurity(
                                  0,
                                  ExplicitDescriptor,
                                  &CClfsContainer::m_psdDefaultSecurity,
                                  0,
                                  SubjectContext,
                                  FileObjectGenericMapping,
                                  PagedPool);
                          if ( Acl >= 0 )
                            LODWORD(CClfsContainer::m_cbDefaultSecurity) = RtlLengthSecurityDescriptor(CClfsContainer::m_psdDefaultSecurity);
                        }
                      }
                    }
                  }
                  goto LABEL_25;
                }
              }
            }
LABEL_24:
            Acl = -1073741670;
          }
        }
      }
    }
  }
LABEL_25:
  if ( SubjectContext )
  {
    if ( v20 )
      SeReleaseSubjectContext(SubjectContext);
    ExFreePoolWithTag(SubjectContext, 0);
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0);
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14003d56c  mov     r11, rsp
0x14003d56f  push    rbx
0x14003d570  push    rsi
0x14003d571  push    rdi
0x14003d572  push    r12
0x14003d574  push    r13
0x14003d576  push    r14
0x14003d578  push    r15
0x14003d57a  sub     rsp, 0E0h
0x14003d581  mov     rax, cs:__security_cookie
0x14003d588  xor     rax, rsp
0x14003d58b  mov     [rsp+118h+var_40], rax
0x14003d593  xor     ebx, ebx
0x14003d595  mov     [r11-50h], ebx
0x14003d599  mov     word ptr [r11-4Ch], 500h
0x14003d5a0  mov     [r11-48h], ebx
0x14003d5a4  mov     word ptr [r11-44h], 100h
0x14003d5ab  mov     [rsp+118h+var_D0], rbx
0x14003d5b0  mov     r13d, ebx
0x14003d5b3  mov     [rsp+118h+var_B0], rbx
0x14003d5b8  mov     r12d, ebx
0x14003d5bb  mov     [rsp+118h+var_A8], rbx
0x14003d5c0  mov     esi, ebx
0x14003d5c2  mov     [rsp+118h+var_C8], rbx
0x14003d5c7  mov     r15d, ebx
0x14003d5ca  mov     [rsp+118h+var_B8], rbx
0x14003d5cf  mov     r14d, ebx
0x14003d5d2  mov     [rsp+118h+var_C0], rbx
0x14003d5d7  mov     [rsp+118h+var_D8], bl
0x14003d5db  xorps   xmm0, xmm0
0x14003d5de  xor     eax, eax
0x14003d5e0  movups  xmmword ptr [r11-78h], xmm0
0x14003d5e5  movups  xmmword ptr [r11-68h], xmm0
0x14003d5ea  mov     [r11-58h], rax
0x14003d5ee  xorps   xmm1, xmm1
0x14003d5f1  movups  [rsp+118h+ExplicitDescriptor], xmm1
0x14003d5f6  movups  [rsp+118h+var_90], xmm1
0x14003d5fe  mov     [r11-80h], rax
0x14003d602  lea     edx, [rbx+20h]; NumberOfBytes
0x14003d605  lea     ecx, [rbx+1]; PoolType
0x14003d608  mov     r8d, 73666C43h; Tag
0x14003d60e  call    cs:__imp_ExAllocatePoolWithTag
0x14003d615  nop     dword ptr [rax+rax+00h]
0x14003d61a  mov     rdi, rax
0x14003d61d  mov     [rsp+118h+var_D0], rax
0x14003d622  test    rax, rax
0x14003d625  jz      loc_14003DA78
0x14003d62b  xorps   xmm0, xmm0
0x14003d62e  movups  xmmword ptr [rax], xmm0
0x14003d631  movups  xmmword ptr [rax+10h], xmm0
0x14003d635  mov     rcx, rax; SubjectContext
0x14003d638  call    cs:__imp_SeCaptureSubjectContext
0x14003d63f  nop     dword ptr [rax+rax+00h]
0x14003d644  lea     esi, [rbx+1]
0x14003d647  mov     [rsp+118h+var_D8], sil
0x14003d64c  mov     ecx, esi; SubAuthorityCount
0x14003d64e  call    cs:__imp_RtlLengthRequiredSid
0x14003d655  nop     dword ptr [rax+rax+00h]
0x14003d65a  mov     edx, eax; NumberOfBytes
0x14003d65c  mov     r8d, 73666C43h; Tag
0x14003d662  mov     ecx, esi; PoolType
0x14003d664  call    cs:__imp_ExAllocatePoolWithTag
0x14003d66b  nop     dword ptr [rax+rax+00h]
0x14003d670  mov     rsi, rax
0x14003d673  mov     [rsp+118h+var_C8], rax
0x14003d678  test    rax, rax
0x14003d67b  jz      loc_14003DA78
0x14003d681  mov     r8b, 1; SubAuthorityCount
0x14003d684  lea     rdx, [rsp+118h+IdentifierAuthority]; IdentifierAuthority
0x14003d68c  mov     rcx, rax; Sid
0x14003d68f  call    cs:__imp_RtlInitializeSid
0x14003d696  nop     dword ptr [rax+rax+00h]
0x14003d69b  xor     edx, edx; SubAuthority
0x14003d69d  mov     rcx, rsi; Sid
0x14003d6a0  call    cs:__imp_RtlSubAuthoritySid
0x14003d6a7  nop     dword ptr [rax+rax+00h]
0x14003d6ac  mov     [rax], ebx
0x14003d6ae  movzx   eax, byte ptr [rsi+1]
0x14003d6b2  lea     eax, ds:23h[rax*4]
0x14003d6b9  and     eax, 0FFFFFFF8h
0x14003d6bc  mov     ebx, eax
0x14003d6be  mov     edx, eax; NumberOfBytes
0x14003d6c0  lea     ecx, [r14+1]; PoolType
0x14003d6c4  mov     r8d, 73666C43h; Tag
0x14003d6ca  call    cs:__imp_ExAllocatePoolWithTag
0x14003d6d1  nop     dword ptr [rax+rax+00h]
0x14003d6d6  mov     r14, rax
0x14003d6d9  mov     [rsp+118h+var_C0], rax
0x14003d6de  test    rax, rax
0x14003d6e1  jz      loc_14003DA78
0x14003d6e7  lea     r8d, [r15+2]; AclRevision
0x14003d6eb  mov     edx, ebx; AclLength
0x14003d6ed  mov     rcx, rax; Acl
0x14003d6f0  call    cs:__imp_RtlCreateAcl
0x14003d6f7  nop     dword ptr [rax+rax+00h]
0x14003d6fc  mov     ebx, eax
0x14003d6fe  mov     [rsp+118h+var_D4], eax
0x14003d702  test    eax, eax
0x14003d704  js      loc_14003DA81
0x14003d70a  mov     r9, rsi; Sid
0x14003d70d  lea     edx, [r15+2]; AceRevision
0x14003d711  mov     r8d, 10000000h; AccessMask
0x14003d717  mov     rcx, r14; Acl
0x14003d71a  call    cs:__imp_RtlAddAccessAllowedAce
0x14003d721  nop     dword ptr [rax+rax+00h]
0x14003d726  mov     ebx, eax
0x14003d728  mov     [rsp+118h+var_D4], eax
0x14003d72c  test    eax, eax
0x14003d72e  js      loc_14003DA81
0x14003d734  lea     edx, [r15+1]; Revision
0x14003d738  lea     rcx, [rsp+118h+SecurityDescriptor]; SecurityDescriptor
0x14003d740  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003d747  nop     dword ptr [rax+rax+00h]
0x14003d74c  mov     ebx, eax
0x14003d74e  mov     [rsp+118h+var_D4], eax
0x14003d752  test    eax, eax
0x14003d754  js      short loc_14003D778
0x14003d756  xor     r9d, r9d; DaclDefaulted
0x14003d759  mov     r8, r14; Dacl
0x14003d75c  mov     dl, 1; DaclPresent
0x14003d75e  lea     rcx, [rsp+118h+SecurityDescriptor]; SecurityDescriptor
0x14003d766  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14003d76d  nop     dword ptr [rax+rax+00h]
0x14003d772  mov     ebx, eax
0x14003d774  mov     [rsp+118h+var_D4], eax
0x14003d778  test    ebx, ebx
0x14003d77a  js      loc_14003DA81
0x14003d780  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003d787  nop     dword ptr [rax+rax+00h]
0x14003d78c  mov     [rsp+118h+PoolType], 1; PoolType
0x14003d794  mov     [rsp+118h+GenericMapping], rax; GenericMapping
0x14003d799  mov     [rsp+118h+SubjectContext], rdi; SubjectContext
0x14003d79e  xor     r9d, r9d; IsDirectoryObject
0x14003d7a1  lea     r8, ?m_psdNoSecurity@CClfsContainer@@0PEAXEA; NewDescriptor
0x14003d7a8  lea     rdx, [rsp+118h+SecurityDescriptor]; ExplicitDescriptor
0x14003d7b0  xor     ecx, ecx; ParentDescriptor
0x14003d7b2  call    cs:__imp_SeAssignSecurity
0x14003d7b9  nop     dword ptr [rax+rax+00h]
0x14003d7be  mov     ebx, eax
0x14003d7c0  mov     [rsp+118h+var_D4], eax
0x14003d7c4  test    eax, eax
0x14003d7c6  js      loc_14003DA81
0x14003d7cc  mov     rcx, cs:?m_psdNoSecurity@CClfsContainer@@0PEAXEA; SecurityDescriptor
0x14003d7d3  call    cs:__imp_RtlLengthSecurityDescriptor
0x14003d7da  nop     dword ptr [rax+rax+00h]
0x14003d7df  mov     cs:?m_cbNoSecurity@CClfsContainer@@0KA, eax; ulong CClfsContainer::m_cbNoSecurity
0x14003d7e5  mov     edx, 1; Revision
0x14003d7ea  lea     rcx, [rsp+118h+ExplicitDescriptor]; SecurityDescriptor
0x14003d7ef  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003d7f6  nop     dword ptr [rax+rax+00h]
0x14003d7fb  mov     ebx, eax
0x14003d7fd  mov     [rsp+118h+var_D4], eax
0x14003d801  test    eax, eax
0x14003d803  js      short loc_14003D824
0x14003d805  xor     r9d, r9d; DaclDefaulted
0x14003d808  xor     r8d, r8d; Dacl
0x14003d80b  mov     dl, 1; DaclPresent
0x14003d80d  lea     rcx, [rsp+118h+ExplicitDescriptor]; SecurityDescriptor
0x14003d812  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14003d819  nop     dword ptr [rax+rax+00h]
0x14003d81e  mov     ebx, eax
0x14003d820  mov     [rsp+118h+var_D4], eax
0x14003d824  test    ebx, ebx
0x14003d826  js      loc_14003DA81
0x14003d82c  mov     ecx, 2; SubAuthorityCount
0x14003d831  call    cs:__imp_RtlLengthRequiredSid
0x14003d838  nop     dword ptr [rax+rax+00h]
0x14003d83d  mov     edx, eax; NumberOfBytes
0x14003d83f  mov     r12d, 73666C43h
0x14003d845  mov     r8d, r12d; Tag
0x14003d848  mov     ebx, 1
0x14003d84d  mov     ecx, ebx; PoolType
0x14003d84f  call    cs:__imp_ExAllocatePoolWithTag
0x14003d856  nop     dword ptr [rax+rax+00h]
0x14003d85b  mov     r13, rax
0x14003d85e  mov     [rsp+118h+var_B0], rax
0x14003d863  mov     ecx, ebx; SubAuthorityCount
0x14003d865  call    cs:__imp_RtlLengthRequiredSid
0x14003d86c  nop     dword ptr [rax+rax+00h]
0x14003d871  mov     edx, eax; NumberOfBytes
0x14003d873  mov     r8d, r12d; Tag
0x14003d876  mov     ecx, ebx; PoolType
0x14003d878  call    cs:__imp_ExAllocatePoolWithTag
0x14003d87f  nop     dword ptr [rax+rax+00h]
0x14003d884  mov     r12, rax
0x14003d887  mov     [rsp+118h+var_A8], rax
0x14003d88c  test    r13, r13
0x14003d88f  jz      loc_14003DA78
0x14003d895  test    rax, rax
0x14003d898  jz      loc_14003DA78
0x14003d89e  mov     r8b, 2; SubAuthorityCount
0x14003d8a1  lea     rdx, [rsp+118h+var_50]; IdentifierAuthority
0x14003d8a9  mov     rcx, r13; Sid
0x14003d8ac  call    cs:__imp_RtlInitializeSid
0x14003d8b3  nop     dword ptr [rax+rax+00h]
0x14003d8b8  xor     edx, edx; SubAuthority
0x14003d8ba  mov     rcx, r13; Sid
0x14003d8bd  call    cs:__imp_RtlSubAuthoritySid
0x14003d8c4  nop     dword ptr [rax+rax+00h]
0x14003d8c9  mov     dword ptr [rax], 20h ; ' '
0x14003d8cf  mov     edx, ebx; SubAuthority
0x14003d8d1  mov     rcx, r13; Sid
0x14003d8d4  call    cs:__imp_RtlSubAuthoritySid
0x14003d8db  nop     dword ptr [rax+rax+00h]
0x14003d8e0  mov     dword ptr [rax], 220h
0x14003d8e6  mov     r8b, bl; SubAuthorityCount
0x14003d8e9  lea     rdx, [rsp+118h+var_50]; IdentifierAuthority
0x14003d8f1  mov     rcx, r12; Sid
0x14003d8f4  call    cs:__imp_RtlInitializeSid
0x14003d8fb  nop     dword ptr [rax+rax+00h]
0x14003d900  xor     edx, edx; SubAuthority
0x14003d902  mov     rcx, r12; Sid
0x14003d905  call    cs:__imp_RtlSubAuthoritySid
0x14003d90c  nop     dword ptr [rax+rax+00h]
0x14003d911  mov     dword ptr [rax], 12h
0x14003d917  movzx   ecx, byte ptr [r12+1]
0x14003d91d  movzx   eax, byte ptr [r13+1]
0x14003d922  add     ecx, eax
0x14003d924  lea     eax, ds:37h[rcx*4]
0x14003d92b  and     eax, 0FFFFFFF8h
0x14003d92e  mov     ebx, eax
0x14003d930  mov     edx, eax; NumberOfBytes
0x14003d932  mov     ecx, 1; PoolType
0x14003d937  mov     r8d, 73666C43h; Tag
0x14003d93d  call    cs:__imp_ExAllocatePoolWithTag
0x14003d944  nop     dword ptr [rax+rax+00h]
0x14003d949  mov     r15, rax
0x14003d94c  mov     [rsp+118h+var_B8], rax
0x14003d951  test    rax, rax
0x14003d954  jz      loc_14003DA78
0x14003d95a  mov     r8d, 2; AclRevision
0x14003d960  mov     edx, ebx; AclLength
0x14003d962  mov     rcx, rax; Acl
0x14003d965  call    cs:__imp_RtlCreateAcl
0x14003d96c  nop     dword ptr [rax+rax+00h]
0x14003d971  mov     ebx, eax
0x14003d973  mov     [rsp+118h+var_D4], eax
0x14003d977  test    eax, eax
0x14003d979  js      loc_14003DA81
0x14003d97f  mov     r9, r13; Sid
0x14003d982  mov     edx, 2; AceRevision
0x14003d987  mov     r8d, 10000000h; AccessMask
0x14003d98d  mov     rcx, r15; Acl
0x14003d990  call    cs:__imp_RtlAddAccessAllowedAce
0x14003d997  nop     dword ptr [rax+rax+00h]
0x14003d99c  mov     ebx, eax
0x14003d99e  mov     [rsp+118h+var_D4], eax
0x14003d9a2  test    eax, eax
0x14003d9a4  js      loc_14003DA81
0x14003d9aa  mov     r9, r12; Sid
0x14003d9ad  mov     edx, 2; AceRevision
0x14003d9b2  mov     r8d, 10000000h; AccessMask
0x14003d9b8  mov     rcx, r15; Acl
0x14003d9bb  call    cs:__imp_RtlAddAccessAllowedAce
0x14003d9c2  nop     dword ptr [rax+rax+00h]
0x14003d9c7  mov     ebx, eax
0x14003d9c9  mov     [rsp+118h+var_D4], eax
0x14003d9cd  test    eax, eax
0x14003d9cf  js      loc_14003DA81
0x14003d9d5  mov     edx, 1; Revision
0x14003d9da  lea     rcx, [rsp+118h+ExplicitDescriptor]; SecurityDescriptor
0x14003d9df  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003d9e6  nop     dword ptr [rax+rax+00h]
0x14003d9eb  mov     ebx, eax
0x14003d9ed  mov     [rsp+118h+var_D4], eax
0x14003d9f1  test    eax, eax
0x14003d9f3  js      short loc_14003DA14
0x14003d9f5  xor     r9d, r9d; DaclDefaulted
0x14003d9f8  mov     r8, r15; Dacl
0x14003d9fb  mov     dl, 1; DaclPresent
0x14003d9fd  lea     rcx, [rsp+118h+ExplicitDescriptor]; SecurityDescriptor
0x14003da02  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14003da09  nop     dword ptr [rax+rax+00h]
0x14003da0e  mov     ebx, eax
0x14003da10  mov     [rsp+118h+var_D4], eax
0x14003da14  test    ebx, ebx
0x14003da16  js      short loc_14003DA81
0x14003da18  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003da1f  nop     dword ptr [rax+rax+00h]
0x14003da24  mov     [rsp+118h+PoolType], 1; PoolType
0x14003da2c  mov     [rsp+118h+GenericMapping], rax; GenericMapping
0x14003da31  mov     [rsp+118h+SubjectContext], rdi; SubjectContext
0x14003da36  xor     r9d, r9d; IsDirectoryObject
0x14003da39  lea     r8, ?m_psdDefaultSecurity@CClfsContainer@@0PEAXEA; NewDescriptor
0x14003da40  lea     rdx, [rsp+118h+ExplicitDescriptor]; ExplicitDescriptor
0x14003da45  xor     ecx, ecx; ParentDescriptor
0x14003da47  call    cs:__imp_SeAssignSecurity
0x14003da4e  nop     dword ptr [rax+rax+00h]
0x14003da53  mov     ebx, eax
0x14003da55  mov     [rsp+118h+var_D4], eax
0x14003da59  test    eax, eax
0x14003da5b  js      short loc_14003DA81
0x14003da5d  mov     rcx, cs:?m_psdDefaultSecurity@CClfsContainer@@0PEAXEA; SecurityDescriptor
0x14003da64  call    cs:__imp_RtlLengthSecurityDescriptor
0x14003da6b  nop     dword ptr [rax+rax+00h]
0x14003da70  mov     cs:?m_cbDefaultSecurity@CClfsContainer@@0KA, eax; ulong CClfsContainer::m_cbDefaultSecurity
0x14003da76  jmp     short loc_14003DA81
0x14003da78  mov     ebx, 0C000009Ah
0x14003da7d  mov     [rsp+118h+var_D4], ebx
0x14003da81  test    rdi, rdi
  ... truncated ...
```
