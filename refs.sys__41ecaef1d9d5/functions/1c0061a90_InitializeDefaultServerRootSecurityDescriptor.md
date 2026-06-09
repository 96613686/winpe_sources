# InitializeDefaultServerRootSecurityDescriptor

- ea: `0x1c0061a90`
- end: `0x1c0062088`
- name: `InitializeDefaultServerRootSecurityDescriptor`
- size: `1528`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c01d97ac`

## callees

- `0x1c000f770`
- `0x1c0061a90`
- `0x1c0068168`
- `0x1c0068960`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061b33`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061b71`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061be0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061c3b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061c93`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061d06`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061d7a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061b33`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061b71`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061be0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061c3b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061c93`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061d06`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0061d7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006200c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006201d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062030`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062041`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c403`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c41b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c433`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0061ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006200c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006201d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062030`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062041`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c3eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c403`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c41b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c433`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c44b`
- `ntoskrnl!ExRaiseStatus` at `0x1c008ead2`
- `ntoskrnl!ExRaiseStatus` at `0x1c008ead2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c0061b4a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c0061b4a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c0061fbe`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c006c3a3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c0061fbe`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c006c3a3`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061b5e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061bcd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061c28`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061c80`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061cf0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061b5e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061bcd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061c28`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061c80`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0061cf0`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061b93`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061c02`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061c5d`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061cb5`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061d28`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061b93`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061c02`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061c5d`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061cb5`
- `ntoskrnl!RtlInitializeSid` at `0x1c0061d28`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061ba4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061bb8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061c13`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061c6e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061cc6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061cdc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061d39`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061ba4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061bb8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061c13`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061c6e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061cc6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061cdc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0061d39`
- `ntoskrnl!RtlCreateAcl` at `0x1c0061d99`
- `ntoskrnl!RtlCreateAcl` at `0x1c0061d99`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c0061f1a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c0061f1a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c0061f44`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c0061f44`
- `ntoskrnl!SeAssignSecurity` at `0x1c0061f8c`
- `ntoskrnl!SeAssignSecurity` at `0x1c0061f8c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c0061f5a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c0061f5a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c0061fa9`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c0061fa9`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061dca`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061dfb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e2c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e5d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e8d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061ebd`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061ef3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061dca`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061dfb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e2c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e5d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061e8d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061ebd`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c0061ef3`

## pseudocode

```c
void InitializeDefaultServerRootSecurityDescriptor()
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  ULONG v1; // eax
  unsigned __int8 *Sid; // r15
  ULONG v3; // eax
  unsigned __int8 *v4; // r12
  ULONG v5; // eax
  unsigned __int8 *v6; // r13
  ULONG v7; // eax
  unsigned __int8 *v8; // r14
  ULONG v9; // eax
  ULONG v10; // ebx
  struct _ACL *v11; // rdi
  NTSTATUS Acl; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS Status; // [rsp+40h] [rbp-A8h]
  unsigned __int8 *P; // [rsp+48h] [rbp-A0h]
  _BYTE SecurityDescriptor[32]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A8h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+B0h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+B8h] [rbp-30h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v17 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 768;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 256;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag((POOL_TYPE)17, 0x20u, 0x4A666552u);
  SeCaptureSubjectContext(PoolWithTag);
  v1 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v1, 0x4A666552u);
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = RtlLengthRequiredSid(1u);
  v6 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v5, 0x4A666552u);
  RtlInitializeSid(v6, &v19, 1u);
  *RtlSubAuthoritySid(v6, 0) = 0;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = RtlLengthRequiredSid(1u);
  P = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v9, 0x4A666552u);
  RtlInitializeSid(P, &v20, 1u);
  *RtlSubAuthoritySid(P, 0) = 0;
  v10 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1] + P[1]) + 232;
  v11 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)17, v10, 0x4A666552u);
  Acl = RtlCreateAcl(v11, v10, 2u);
  Status = Acl;
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, Sid);
    Status = Acl;
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, v4);
      Status = Acl;
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v11, 2u, 0xBu, 0x10000000u, v6);
        Status = Acl;
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, v8);
          Status = Acl;
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v11, 2u, 2u, 4u, v8);
            Status = Acl;
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 2u, v8);
              Status = Acl;
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, P);
                Status = Acl;
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  Status = Acl;
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
                    Status = Acl;
                    if ( Acl >= 0 )
                    {
                      GenericMapping = IoGetFileObjectGenericMapping();
                      Acl = SeAssignSecurity(
                              0,
                              SecurityDescriptor,
                              &::SecurityDescriptor,
                              0,
                              PoolWithTag,
                              GenericMapping,
                              PagedPool);
                      Status = Acl;
                      if ( Acl >= 0 )
                        dword_1C012E0E0 = RtlLengthSecurityDescriptor(::SecurityDescriptor);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(PoolWithTag);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  ExFreePoolWithTag(Sid, 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(P, 0);
  ExFreePoolWithTag(v8, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids,
        (unsigned int)Acl);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    ExRaiseStatus(Status);
  }
}

```

## disassembly

```asm
0x1c0061a90  mov     r11, rsp
0x1c0061a93  mov     [r11+8], rbx
0x1c0061a97  mov     [r11+10h], rsi
0x1c0061a9b  mov     [r11+18h], rdi
0x1c0061a9f  mov     [r11+20h], r12
0x1c0061aa3  push    r13
0x1c0061aa5  push    r14
0x1c0061aa7  push    r15
0x1c0061aa9  sub     rsp, 0D0h
0x1c0061ab0  mov     rax, cs:__security_cookie
0x1c0061ab7  xor     rax, rsp
0x1c0061aba  mov     [rsp+0E8h+var_28], rax
0x1c0061ac2  xor     ecx, ecx
0x1c0061ac4  mov     [rsp+0E8h+var_98], rcx
0x1c0061ac9  mov     [rsp+0E8h+var_A4], cl
0x1c0061acd  mov     [rsp+0E8h+var_90], rcx
0x1c0061ad2  mov     [rsp+0E8h+var_88], rcx
0x1c0061ad7  mov     [r11-80h], rcx
0x1c0061adb  mov     [r11-78h], rcx
0x1c0061adf  mov     [r11-70h], rcx
0x1c0061ae3  mov     [rsp+0E8h+P], rcx
0x1c0061ae8  xorps   xmm0, xmm0
0x1c0061aeb  xor     eax, eax
0x1c0061aed  movups  xmmword ptr [r11-68h], xmm0
0x1c0061af2  movups  xmmword ptr [r11-58h], xmm0
0x1c0061af7  mov     [r11-48h], rax
0x1c0061afb  mov     [r11-40h], ecx
0x1c0061aff  mov     word ptr [r11-3Ch], 500h
0x1c0061b06  mov     [r11-38h], ecx
0x1c0061b0a  mov     word ptr [r11-34h], 300h
0x1c0061b11  mov     [r11-30h], ecx
0x1c0061b15  mov     word ptr [r11-2Ch], 100h
0x1c0061b1c  lea     r13d, [rcx+1]
0x1c0061b20  mov     r14d, 4A666552h
0x1c0061b26  mov     r8d, r14d; Tag
0x1c0061b29  lea     ebx, [rcx+20h]
0x1c0061b2c  mov     edx, ebx; NumberOfBytes
0x1c0061b2e  lea     edi, [rcx+11h]
0x1c0061b31  mov     ecx, edi; PoolType
0x1c0061b33  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061b3a  nop     dword ptr [rax+rax+00h]
0x1c0061b3f  mov     rsi, rax
0x1c0061b42  mov     [rsp+0E8h+var_98], rax
0x1c0061b47  mov     rcx, rax; SubjectContext
0x1c0061b4a  call    cs:__imp_SeCaptureSubjectContext
0x1c0061b51  nop     dword ptr [rax+rax+00h]
0x1c0061b56  mov     [rsp+0E8h+var_A4], r13b
0x1c0061b5b  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1c0061b5e  call    cs:__imp_RtlLengthRequiredSid
0x1c0061b65  nop     dword ptr [rax+rax+00h]
0x1c0061b6a  mov     edx, eax; NumberOfBytes
0x1c0061b6c  mov     r8d, r14d; Tag
0x1c0061b6f  mov     ecx, edi; PoolType
0x1c0061b71  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061b78  nop     dword ptr [rax+rax+00h]
0x1c0061b7d  mov     r15, rax
0x1c0061b80  mov     [rsp+0E8h+var_88], rax
0x1c0061b85  mov     r8b, 2; SubAuthorityCount
0x1c0061b88  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1c0061b90  mov     rcx, rax; Sid
0x1c0061b93  call    cs:__imp_RtlInitializeSid
0x1c0061b9a  nop     dword ptr [rax+rax+00h]
0x1c0061b9f  xor     edx, edx; SubAuthority
0x1c0061ba1  mov     rcx, r15; Sid
0x1c0061ba4  call    cs:__imp_RtlSubAuthoritySid
0x1c0061bab  nop     dword ptr [rax+rax+00h]
0x1c0061bb0  mov     [rax], ebx
0x1c0061bb2  mov     edx, r13d; SubAuthority
0x1c0061bb5  mov     rcx, r15; Sid
0x1c0061bb8  call    cs:__imp_RtlSubAuthoritySid
0x1c0061bbf  nop     dword ptr [rax+rax+00h]
0x1c0061bc4  mov     dword ptr [rax], 220h
0x1c0061bca  mov     ecx, r13d; SubAuthorityCount
0x1c0061bcd  call    cs:__imp_RtlLengthRequiredSid
0x1c0061bd4  nop     dword ptr [rax+rax+00h]
0x1c0061bd9  mov     edx, eax; NumberOfBytes
0x1c0061bdb  mov     r8d, r14d; Tag
0x1c0061bde  mov     ecx, edi; PoolType
0x1c0061be0  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061be7  nop     dword ptr [rax+rax+00h]
0x1c0061bec  mov     r12, rax
0x1c0061bef  mov     [rsp+0E8h+var_80], rax
0x1c0061bf4  mov     r8b, r13b; SubAuthorityCount
0x1c0061bf7  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1c0061bff  mov     rcx, rax; Sid
0x1c0061c02  call    cs:__imp_RtlInitializeSid
0x1c0061c09  nop     dword ptr [rax+rax+00h]
0x1c0061c0e  xor     edx, edx; SubAuthority
0x1c0061c10  mov     rcx, r12; Sid
0x1c0061c13  call    cs:__imp_RtlSubAuthoritySid
0x1c0061c1a  nop     dword ptr [rax+rax+00h]
0x1c0061c1f  mov     dword ptr [rax], 12h
0x1c0061c25  mov     ecx, r13d; SubAuthorityCount
0x1c0061c28  call    cs:__imp_RtlLengthRequiredSid
0x1c0061c2f  nop     dword ptr [rax+rax+00h]
0x1c0061c34  mov     edx, eax; NumberOfBytes
0x1c0061c36  mov     r8d, r14d; Tag
0x1c0061c39  mov     ecx, edi; PoolType
0x1c0061c3b  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061c42  nop     dword ptr [rax+rax+00h]
0x1c0061c47  mov     r13, rax
0x1c0061c4a  mov     [rsp+0E8h+var_78], rax
0x1c0061c4f  mov     r8b, 1; SubAuthorityCount
0x1c0061c52  lea     rdx, [rsp+0E8h+var_38]; IdentifierAuthority
0x1c0061c5a  mov     rcx, rax; Sid
0x1c0061c5d  call    cs:__imp_RtlInitializeSid
0x1c0061c64  nop     dword ptr [rax+rax+00h]
0x1c0061c69  xor     edx, edx; SubAuthority
0x1c0061c6b  mov     rcx, r13; Sid
0x1c0061c6e  call    cs:__imp_RtlSubAuthoritySid
0x1c0061c75  nop     dword ptr [rax+rax+00h]
0x1c0061c7a  and     dword ptr [rax], 0
0x1c0061c7d  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1c0061c80  call    cs:__imp_RtlLengthRequiredSid
0x1c0061c87  nop     dword ptr [rax+rax+00h]
0x1c0061c8c  mov     edx, eax; NumberOfBytes
0x1c0061c8e  mov     r8d, r14d; Tag
0x1c0061c91  mov     ecx, edi; PoolType
0x1c0061c93  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061c9a  nop     dword ptr [rax+rax+00h]
0x1c0061c9f  mov     r14, rax
0x1c0061ca2  mov     [rsp+0E8h+var_70], rax
0x1c0061ca7  mov     r8b, 2; SubAuthorityCount
0x1c0061caa  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1c0061cb2  mov     rcx, rax; Sid
0x1c0061cb5  call    cs:__imp_RtlInitializeSid
0x1c0061cbc  nop     dword ptr [rax+rax+00h]
0x1c0061cc1  xor     edx, edx; SubAuthority
0x1c0061cc3  mov     rcx, r14; Sid
0x1c0061cc6  call    cs:__imp_RtlSubAuthoritySid
0x1c0061ccd  nop     dword ptr [rax+rax+00h]
0x1c0061cd2  mov     [rax], ebx
0x1c0061cd4  lea     ebx, [rdi-10h]
0x1c0061cd7  mov     edx, ebx; SubAuthority
0x1c0061cd9  mov     rcx, r14; Sid
0x1c0061cdc  call    cs:__imp_RtlSubAuthoritySid
0x1c0061ce3  nop     dword ptr [rax+rax+00h]
0x1c0061ce8  mov     dword ptr [rax], 221h
0x1c0061cee  mov     ecx, ebx; SubAuthorityCount
0x1c0061cf0  call    cs:__imp_RtlLengthRequiredSid
0x1c0061cf7  nop     dword ptr [rax+rax+00h]
0x1c0061cfc  mov     edx, eax; NumberOfBytes
0x1c0061cfe  mov     r8d, 4A666552h; Tag
0x1c0061d04  mov     ecx, edi; PoolType
0x1c0061d06  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061d0d  nop     dword ptr [rax+rax+00h]
0x1c0061d12  mov     rbx, rax
0x1c0061d15  mov     [rsp+0E8h+P], rax
0x1c0061d1a  mov     r8b, 1; SubAuthorityCount
0x1c0061d1d  lea     rdx, [rsp+0E8h+var_30]; IdentifierAuthority
0x1c0061d25  mov     rcx, rax; Sid
0x1c0061d28  call    cs:__imp_RtlInitializeSid
0x1c0061d2f  nop     dword ptr [rax+rax+00h]
0x1c0061d34  xor     edx, edx; SubAuthority
0x1c0061d36  mov     rcx, rbx; Sid
0x1c0061d39  call    cs:__imp_RtlSubAuthoritySid
0x1c0061d40  nop     dword ptr [rax+rax+00h]
0x1c0061d45  and     dword ptr [rax], 0
0x1c0061d48  movzx   ebx, byte ptr [rbx+1]
0x1c0061d4c  movzx   edx, byte ptr [r14+1]
0x1c0061d51  add     ebx, edx
0x1c0061d53  movzx   edx, byte ptr [r13+1]
0x1c0061d58  add     ebx, edx
0x1c0061d5a  movzx   eax, byte ptr [r12+1]
0x1c0061d60  add     ebx, eax
0x1c0061d62  movzx   eax, byte ptr [r15+1]
0x1c0061d67  add     ebx, eax
0x1c0061d69  lea     ebx, ds:0E8h[rbx*4]
0x1c0061d70  mov     edx, ebx; NumberOfBytes
0x1c0061d72  mov     r8d, 4A666552h; Tag
0x1c0061d78  mov     ecx, edi; PoolType
0x1c0061d7a  call    cs:__imp_ExAllocatePoolWithTag
0x1c0061d81  nop     dword ptr [rax+rax+00h]
0x1c0061d86  mov     rdi, rax
0x1c0061d89  mov     [rsp+0E8h+var_90], rax
0x1c0061d8e  mov     r8d, 2; AclRevision
0x1c0061d94  mov     edx, ebx; AclLength
0x1c0061d96  mov     rcx, rax; Acl
0x1c0061d99  call    cs:__imp_RtlCreateAcl
0x1c0061da0  nop     dword ptr [rax+rax+00h]
0x1c0061da5  mov     ebx, eax
0x1c0061da7  mov     [rsp+0E8h+Status], eax
0x1c0061dab  test    eax, eax
0x1c0061dad  js      loc_1C0061FBB
0x1c0061db3  mov     [rsp+0E8h+Sid], r15; Sid
0x1c0061db8  mov     edx, 2; AceRevision
0x1c0061dbd  mov     r9d, 10000000h; AccessMask
0x1c0061dc3  lea     r8d, [rdx+1]; AceFlags
0x1c0061dc7  mov     rcx, rdi; Acl
0x1c0061dca  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061dd1  nop     dword ptr [rax+rax+00h]
0x1c0061dd6  mov     ebx, eax
0x1c0061dd8  mov     [rsp+0E8h+Status], eax
0x1c0061ddc  test    eax, eax
0x1c0061dde  js      loc_1C0061FBB
0x1c0061de4  mov     [rsp+0E8h+Sid], r12; Sid
0x1c0061de9  mov     edx, 2; AceRevision
0x1c0061dee  mov     r9d, 10000000h; AccessMask
0x1c0061df4  lea     r8d, [rdx+1]; AceFlags
0x1c0061df8  mov     rcx, rdi; Acl
0x1c0061dfb  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061e02  nop     dword ptr [rax+rax+00h]
0x1c0061e07  mov     ebx, eax
0x1c0061e09  mov     [rsp+0E8h+Status], eax
0x1c0061e0d  test    eax, eax
0x1c0061e0f  js      loc_1C0061FBB
0x1c0061e15  mov     [rsp+0E8h+Sid], r13; Sid
0x1c0061e1a  mov     edx, 2; AceRevision
0x1c0061e1f  mov     r9d, 10000000h; AccessMask
0x1c0061e25  lea     r8d, [rdx+9]; AceFlags
0x1c0061e29  mov     rcx, rdi; Acl
0x1c0061e2c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061e33  nop     dword ptr [rax+rax+00h]
0x1c0061e38  mov     ebx, eax
0x1c0061e3a  mov     [rsp+0E8h+Status], eax
0x1c0061e3e  test    eax, eax
0x1c0061e40  js      loc_1C0061FBB
0x1c0061e46  mov     [rsp+0E8h+Sid], r14; Sid
0x1c0061e4b  mov     edx, 2; AceRevision
0x1c0061e50  mov     r9d, 80100020h; AccessMask
0x1c0061e56  lea     r8d, [rdx+1]; AceFlags
0x1c0061e5a  mov     rcx, rdi; Acl
0x1c0061e5d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061e64  nop     dword ptr [rax+rax+00h]
0x1c0061e69  mov     ebx, eax
0x1c0061e6b  mov     [rsp+0E8h+Status], eax
0x1c0061e6f  test    eax, eax
0x1c0061e71  js      loc_1C0061FBB
0x1c0061e77  mov     [rsp+0E8h+Sid], r14; Sid
0x1c0061e7c  mov     eax, 2
0x1c0061e81  lea     r9d, [rax+2]; AccessMask
0x1c0061e85  mov     r8d, eax; AceFlags
0x1c0061e88  mov     edx, eax; AceRevision
0x1c0061e8a  mov     rcx, rdi; Acl
0x1c0061e8d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061e94  nop     dword ptr [rax+rax+00h]
0x1c0061e99  mov     ebx, eax
0x1c0061e9b  mov     [rsp+0E8h+Status], eax
0x1c0061e9f  test    eax, eax
0x1c0061ea1  js      loc_1C0061FBB
0x1c0061ea7  mov     [rsp+0E8h+Sid], r14; Sid
0x1c0061eac  mov     eax, 2
0x1c0061eb1  mov     r9d, eax; AccessMask
0x1c0061eb4  lea     r8d, [rax+1]; AceFlags
0x1c0061eb8  mov     edx, eax; AceRevision
0x1c0061eba  mov     rcx, rdi; Acl
0x1c0061ebd  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061ec4  nop     dword ptr [rax+rax+00h]
0x1c0061ec9  mov     ebx, eax
0x1c0061ecb  mov     [rsp+0E8h+Status], eax
0x1c0061ecf  test    eax, eax
0x1c0061ed1  js      loc_1C0061FBB
0x1c0061ed7  mov     rax, [rsp+0E8h+P]
0x1c0061edc  mov     [rsp+0E8h+Sid], rax; Sid
0x1c0061ee1  mov     edx, 2; AceRevision
0x1c0061ee6  mov     r9d, 80100020h; AccessMask
0x1c0061eec  lea     r8d, [rdx+1]; AceFlags
0x1c0061ef0  mov     rcx, rdi; Acl
0x1c0061ef3  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c0061efa  nop     dword ptr [rax+rax+00h]
0x1c0061eff  mov     ebx, eax
0x1c0061f01  mov     [rsp+0E8h+Status], eax
0x1c0061f05  test    eax, eax
0x1c0061f07  js      loc_1C0061FBB
0x1c0061f0d  mov     edx, 1; Revision
0x1c0061f12  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1c0061f1a  call    cs:__imp_RtlCreateSecurityDescriptor
0x1c0061f21  nop     dword ptr [rax+rax+00h]
0x1c0061f26  mov     ebx, eax
0x1c0061f28  mov     [rsp+0E8h+Status], eax
0x1c0061f2c  test    eax, eax
0x1c0061f2e  js      loc_1C0061FBB
0x1c0061f34  xor     r9d, r9d; DaclDefaulted
0x1c0061f37  mov     r8, rdi; Dacl
0x1c0061f3a  mov     dl, 1; DaclPresent
0x1c0061f3c  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1c0061f44  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1c0061f4b  nop     dword ptr [rax+rax+00h]
0x1c0061f50  mov     ebx, eax
0x1c0061f52  mov     [rsp+0E8h+Status], eax
0x1c0061f56  test    eax, eax
0x1c0061f58  js      short loc_1C0061FBB
0x1c0061f5a  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c0061f61  nop     dword ptr [rax+rax+00h]
0x1c0061f66  mov     [rsp+0E8h+PoolType], 1; PoolType
0x1c0061f6e  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x1c0061f73  mov     [rsp+0E8h+Sid], rsi; SubjectContext
0x1c0061f78  xor     r9d, r9d; IsDirectoryObject
0x1c0061f7b  lea     r8, SecurityDescriptor; NewDescriptor
0x1c0061f82  lea     rdx, [rsp+0E8h+SecurityDescriptor]; ExplicitDescriptor
0x1c0061f8a  xor     ecx, ecx; ParentDescriptor
0x1c0061f8c  call    cs:__imp_SeAssignSecurity
0x1c0061f93  nop     dword ptr [rax+rax+00h]
0x1c0061f98  mov     ebx, eax
0x1c0061f9a  mov     [rsp+0E8h+Status], eax
0x1c0061f9e  test    eax, eax
0x1c0061fa0  js      short loc_1C0061FBB
0x1c0061fa2  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1c0061fa9  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c0061fb0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
