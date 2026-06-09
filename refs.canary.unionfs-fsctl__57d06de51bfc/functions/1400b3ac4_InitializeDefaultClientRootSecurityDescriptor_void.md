# InitializeDefaultClientRootSecurityDescriptor(void)

- ea: `0x1400b3ac4`
- end: `0x1400b4092`
- name: `?InitializeDefaultClientRootSecurityDescriptor@@YAXXZ`
- size: `1486`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034c36c`

## callees

- `0x14008dbd0`
- `0x1400b3ac4`
- `0x1400ca788`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400b4061`
- `ntoskrnl!ExRaiseStatus` at `0x1400b4061`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b3b58`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b3b58`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b3f85`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401ebb55`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b3f85`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401ebb55`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b3f28`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b3f28`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3b74`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3bea`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3c4c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3cae`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3b74`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3bea`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3c4c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3cae`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3bb0`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3c26`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3c88`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3cea`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3bb0`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3c26`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3c88`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3cea`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3bc1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3bd5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3c37`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3c99`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3cfb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3d0f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3bc1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3bd5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3c37`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3c99`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3cfb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3d0f`
- `ntoskrnl!RtlCreateAcl` at `0x1400b3d70`
- `ntoskrnl!RtlCreateAcl` at `0x1400b3d70`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b3ee5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b3ee5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b3f0c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b3f0c`
- `ntoskrnl!SeAssignSecurity` at `0x1400b3f53`
- `ntoskrnl!SeAssignSecurity` at `0x1400b3f53`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b3f70`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b3f70`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3da1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3dd0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e01`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e30`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e61`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e90`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3ec1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3da1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3dd0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e01`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e30`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e61`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3e90`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3ec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3ff5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb85`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3ff5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb85`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebbe5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3b41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3b8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3c04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3c66`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3cc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3d51`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3b41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3b8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3c04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3c66`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3cc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3d51`

## pseudocode

```c
void InitializeDefaultClientRootSecurityDescriptor(void)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  ULONG v1; // eax
  unsigned __int8 *Sid; // r13
  ULONG v3; // eax
  unsigned __int8 *v4; // r15
  ULONG v5; // eax
  unsigned __int8 *v6; // r12
  ULONG v7; // eax
  unsigned __int8 *v8; // r14
  ULONG v9; // ebx
  struct _ACL *v10; // rdi
  int Acl; // ebx
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v15; // [rsp+98h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-48h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                      (POOL_TYPE)(::PoolType | 0x10),
                                                      0x20u,
                                                      0x4A666552u);
  SeCaptureSubjectContext(PoolWithTag);
  v1 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v1, 0x4A666552u);
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = RtlLengthRequiredSid(1u);
  v6 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v5, 0x4A666552u);
  RtlInitializeSid(v6, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v6, 0) = 11;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1]) + 176;
  v10 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v9, 0x4A666552u);
  Acl = RtlCreateAcl(v10, v9, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v10, 2u, 3u, 0x10000000u, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0x10000000u, v4);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0x10000000u, v4);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xE0010000, v6);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xE0010000, v6);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xA0000000, v8);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xA0000000, v8);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
                    if ( Acl >= 0 )
                    {
                      PoolType = ::PoolType;
                      GenericMapping = IoGetFileObjectGenericMapping();
                      Acl = SeAssignSecurity(
                              0,
                              SecurityDescriptor,
                              &ModificationDescriptor,
                              0,
                              PoolWithTag,
                              GenericMapping,
                              PoolType);
                      if ( Acl >= 0 )
                        dword_1402612C8 = RtlLengthSecurityDescriptor(ModificationDescriptor);
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
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  ExFreePoolWithTag(Sid, 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(v8, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x18ABu);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400b3ac4  mov     r11, rsp
0x1400b3ac7  push    rbx
0x1400b3ac8  push    rsi
0x1400b3ac9  push    rdi
0x1400b3aca  push    r12
0x1400b3acc  push    r13
0x1400b3ace  push    r14
0x1400b3ad0  push    r15
0x1400b3ad2  sub     rsp, 0B0h
0x1400b3ad9  mov     rax, cs:__security_cookie
0x1400b3ae0  xor     rax, rsp
0x1400b3ae3  mov     [rsp+0E8h+var_40], rax
0x1400b3aeb  xor     ecx, ecx
0x1400b3aed  mov     [rsp+0E8h+var_A0], rcx
0x1400b3af2  mov     [rsp+0E8h+var_A8], cl
0x1400b3af6  mov     [rsp+0E8h+var_98], rcx
0x1400b3afb  mov     [rsp+0E8h+var_90], rcx
0x1400b3b00  mov     [rsp+0E8h+var_88], rcx
0x1400b3b05  mov     [r11-80h], rcx
0x1400b3b09  mov     [r11-78h], rcx
0x1400b3b0d  xorps   xmm0, xmm0
0x1400b3b10  xor     eax, eax
0x1400b3b12  movups  [rsp+0E8h+SecurityDescriptor], xmm0
0x1400b3b17  movups  xmmword ptr [r11-60h], xmm0
0x1400b3b1c  mov     [r11-50h], rax
0x1400b3b20  mov     [r11-48h], ecx
0x1400b3b24  mov     word ptr [r11-44h], 500h
0x1400b3b2b  mov     ecx, cs:PoolType
0x1400b3b31  or      ecx, 10h; PoolType
0x1400b3b34  mov     edi, 4A666552h
0x1400b3b39  mov     r8d, edi; Tag
0x1400b3b3c  lea     ebx, [rax+20h]
0x1400b3b3f  mov     edx, ebx; NumberOfBytes
0x1400b3b41  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3b48  nop     dword ptr [rax+rax+00h]
0x1400b3b4d  mov     rsi, rax
0x1400b3b50  mov     [rsp+0E8h+var_A0], rax
0x1400b3b55  mov     rcx, rax; SubjectContext
0x1400b3b58  call    cs:__imp_SeCaptureSubjectContext
0x1400b3b5f  nop     dword ptr [rax+rax+00h]
0x1400b3b64  lea     r12d, [rbx-1Fh]
0x1400b3b68  mov     [rsp+0E8h+var_A8], r12b
0x1400b3b6d  lea     r14d, [rbx-1Eh]
0x1400b3b71  mov     ecx, r14d; SubAuthorityCount
0x1400b3b74  call    cs:__imp_RtlLengthRequiredSid
0x1400b3b7b  nop     dword ptr [rax+rax+00h]
0x1400b3b80  mov     edx, eax; NumberOfBytes
0x1400b3b82  mov     ecx, cs:PoolType
0x1400b3b88  or      ecx, 10h; PoolType
0x1400b3b8b  mov     r8d, edi; Tag
0x1400b3b8e  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3b95  nop     dword ptr [rax+rax+00h]
0x1400b3b9a  mov     r13, rax
0x1400b3b9d  mov     [rsp+0E8h+var_90], rax
0x1400b3ba2  mov     r8b, r14b; SubAuthorityCount
0x1400b3ba5  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b3bad  mov     rcx, rax; Sid
0x1400b3bb0  call    cs:__imp_RtlInitializeSid
0x1400b3bb7  nop     dword ptr [rax+rax+00h]
0x1400b3bbc  xor     edx, edx; SubAuthority
0x1400b3bbe  mov     rcx, r13; Sid
0x1400b3bc1  call    cs:__imp_RtlSubAuthoritySid
0x1400b3bc8  nop     dword ptr [rax+rax+00h]
0x1400b3bcd  mov     [rax], ebx
0x1400b3bcf  mov     edx, r12d; SubAuthority
0x1400b3bd2  mov     rcx, r13; Sid
0x1400b3bd5  call    cs:__imp_RtlSubAuthoritySid
0x1400b3bdc  nop     dword ptr [rax+rax+00h]
0x1400b3be1  mov     dword ptr [rax], 220h
0x1400b3be7  mov     ecx, r12d; SubAuthorityCount
0x1400b3bea  call    cs:__imp_RtlLengthRequiredSid
0x1400b3bf1  nop     dword ptr [rax+rax+00h]
0x1400b3bf6  mov     edx, eax; NumberOfBytes
0x1400b3bf8  mov     ecx, cs:PoolType
0x1400b3bfe  or      ecx, 10h; PoolType
0x1400b3c01  mov     r8d, edi; Tag
0x1400b3c04  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3c0b  nop     dword ptr [rax+rax+00h]
0x1400b3c10  mov     r15, rax
0x1400b3c13  mov     [rsp+0E8h+var_88], rax
0x1400b3c18  mov     r8b, r12b; SubAuthorityCount
0x1400b3c1b  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b3c23  mov     rcx, rax; Sid
0x1400b3c26  call    cs:__imp_RtlInitializeSid
0x1400b3c2d  nop     dword ptr [rax+rax+00h]
0x1400b3c32  xor     edx, edx; SubAuthority
0x1400b3c34  mov     rcx, r15; Sid
0x1400b3c37  call    cs:__imp_RtlSubAuthoritySid
0x1400b3c3e  nop     dword ptr [rax+rax+00h]
0x1400b3c43  mov     dword ptr [rax], 12h
0x1400b3c49  mov     ecx, r12d; SubAuthorityCount
0x1400b3c4c  call    cs:__imp_RtlLengthRequiredSid
0x1400b3c53  nop     dword ptr [rax+rax+00h]
0x1400b3c58  mov     edx, eax; NumberOfBytes
0x1400b3c5a  mov     ecx, cs:PoolType
0x1400b3c60  or      ecx, 10h; PoolType
0x1400b3c63  mov     r8d, edi; Tag
0x1400b3c66  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3c6d  nop     dword ptr [rax+rax+00h]
0x1400b3c72  mov     r12, rax
0x1400b3c75  mov     [rsp+0E8h+var_80], rax
0x1400b3c7a  mov     r8b, 1; SubAuthorityCount
0x1400b3c7d  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b3c85  mov     rcx, rax; Sid
0x1400b3c88  call    cs:__imp_RtlInitializeSid
0x1400b3c8f  nop     dword ptr [rax+rax+00h]
0x1400b3c94  xor     edx, edx; SubAuthority
0x1400b3c96  mov     rcx, r12; Sid
0x1400b3c99  call    cs:__imp_RtlSubAuthoritySid
0x1400b3ca0  nop     dword ptr [rax+rax+00h]
0x1400b3ca5  mov     dword ptr [rax], 0Bh
0x1400b3cab  mov     ecx, r14d; SubAuthorityCount
0x1400b3cae  call    cs:__imp_RtlLengthRequiredSid
0x1400b3cb5  nop     dword ptr [rax+rax+00h]
0x1400b3cba  mov     edx, eax; NumberOfBytes
0x1400b3cbc  mov     ecx, cs:PoolType
0x1400b3cc2  or      ecx, 10h; PoolType
0x1400b3cc5  mov     r8d, edi; Tag
0x1400b3cc8  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3ccf  nop     dword ptr [rax+rax+00h]
0x1400b3cd4  mov     r14, rax
0x1400b3cd7  mov     [rsp+0E8h+var_78], rax
0x1400b3cdc  mov     r8b, 2; SubAuthorityCount
0x1400b3cdf  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b3ce7  mov     rcx, rax; Sid
0x1400b3cea  call    cs:__imp_RtlInitializeSid
0x1400b3cf1  nop     dword ptr [rax+rax+00h]
0x1400b3cf6  xor     edx, edx; SubAuthority
0x1400b3cf8  mov     rcx, r14; Sid
0x1400b3cfb  call    cs:__imp_RtlSubAuthoritySid
0x1400b3d02  nop     dword ptr [rax+rax+00h]
0x1400b3d07  mov     [rax], ebx
0x1400b3d09  lea     edx, [rbx-1Fh]; SubAuthority
0x1400b3d0c  mov     rcx, r14; Sid
0x1400b3d0f  call    cs:__imp_RtlSubAuthoritySid
0x1400b3d16  nop     dword ptr [rax+rax+00h]
0x1400b3d1b  mov     dword ptr [rax], 221h
0x1400b3d21  movzx   ecx, byte ptr [r14+1]
0x1400b3d26  movzx   eax, byte ptr [r12+1]
0x1400b3d2c  add     ecx, eax
0x1400b3d2e  movzx   eax, byte ptr [r15+1]
0x1400b3d33  add     ecx, eax
0x1400b3d35  movzx   eax, byte ptr [r13+1]
0x1400b3d3a  add     ecx, eax
0x1400b3d3c  lea     ebx, ds:0B0h[rcx*4]
0x1400b3d43  mov     edx, ebx; NumberOfBytes
0x1400b3d45  mov     ecx, cs:PoolType
0x1400b3d4b  or      ecx, 10h; PoolType
0x1400b3d4e  mov     r8d, edi; Tag
0x1400b3d51  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3d58  nop     dword ptr [rax+rax+00h]
0x1400b3d5d  mov     rdi, rax
0x1400b3d60  mov     [rsp+0E8h+var_98], rax
0x1400b3d65  mov     r8d, 2; AclRevision
0x1400b3d6b  mov     edx, ebx; AclLength
0x1400b3d6d  mov     rcx, rax; Acl
0x1400b3d70  call    cs:__imp_RtlCreateAcl
0x1400b3d77  nop     dword ptr [rax+rax+00h]
0x1400b3d7c  mov     ebx, eax
0x1400b3d7e  mov     [rsp+0E8h+var_A4], eax
0x1400b3d82  test    eax, eax
0x1400b3d84  js      loc_1400B3F82
0x1400b3d8a  mov     [rsp+0E8h+Sid], r13; Sid
0x1400b3d8f  mov     edx, 2; AceRevision
0x1400b3d94  mov     r9d, 10000000h; AccessMask
0x1400b3d9a  lea     r8d, [rdx+1]; AceFlags
0x1400b3d9e  mov     rcx, rdi; Acl
0x1400b3da1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3da8  nop     dword ptr [rax+rax+00h]
0x1400b3dad  mov     ebx, eax
0x1400b3daf  mov     [rsp+0E8h+var_A4], eax
0x1400b3db3  test    eax, eax
0x1400b3db5  js      loc_1400B3F82
0x1400b3dbb  mov     [rsp+0E8h+Sid], r15; Sid
0x1400b3dc0  mov     r9d, 10000000h; AccessMask
0x1400b3dc6  xor     r8d, r8d; AceFlags
0x1400b3dc9  lea     edx, [r8+2]; AceRevision
0x1400b3dcd  mov     rcx, rdi; Acl
0x1400b3dd0  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3dd7  nop     dword ptr [rax+rax+00h]
0x1400b3ddc  mov     ebx, eax
0x1400b3dde  mov     [rsp+0E8h+var_A4], eax
0x1400b3de2  test    eax, eax
0x1400b3de4  js      loc_1400B3F82
0x1400b3dea  mov     [rsp+0E8h+Sid], r15; Sid
0x1400b3def  mov     edx, 2; AceRevision
0x1400b3df4  mov     r9d, 10000000h; AccessMask
0x1400b3dfa  lea     r8d, [rdx+9]; AceFlags
0x1400b3dfe  mov     rcx, rdi; Acl
0x1400b3e01  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3e08  nop     dword ptr [rax+rax+00h]
0x1400b3e0d  mov     ebx, eax
0x1400b3e0f  mov     [rsp+0E8h+var_A4], eax
0x1400b3e13  test    eax, eax
0x1400b3e15  js      loc_1400B3F82
0x1400b3e1b  mov     [rsp+0E8h+Sid], r12; Sid
0x1400b3e20  mov     r9d, 0E0010000h; AccessMask
0x1400b3e26  xor     r8d, r8d; AceFlags
0x1400b3e29  lea     edx, [r8+2]; AceRevision
0x1400b3e2d  mov     rcx, rdi; Acl
0x1400b3e30  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3e37  nop     dword ptr [rax+rax+00h]
0x1400b3e3c  mov     ebx, eax
0x1400b3e3e  mov     [rsp+0E8h+var_A4], eax
0x1400b3e42  test    eax, eax
0x1400b3e44  js      loc_1400B3F82
0x1400b3e4a  mov     [rsp+0E8h+Sid], r12; Sid
0x1400b3e4f  mov     edx, 2; AceRevision
0x1400b3e54  mov     r9d, 0E0010000h; AccessMask
0x1400b3e5a  lea     r8d, [rdx+9]; AceFlags
0x1400b3e5e  mov     rcx, rdi; Acl
0x1400b3e61  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3e68  nop     dword ptr [rax+rax+00h]
0x1400b3e6d  mov     ebx, eax
0x1400b3e6f  mov     [rsp+0E8h+var_A4], eax
0x1400b3e73  test    eax, eax
0x1400b3e75  js      loc_1400B3F82
0x1400b3e7b  mov     [rsp+0E8h+Sid], r14; Sid
0x1400b3e80  mov     r9d, 0A0000000h; AccessMask
0x1400b3e86  xor     r8d, r8d; AceFlags
0x1400b3e89  lea     edx, [r8+2]; AceRevision
0x1400b3e8d  mov     rcx, rdi; Acl
0x1400b3e90  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3e97  nop     dword ptr [rax+rax+00h]
0x1400b3e9c  mov     ebx, eax
0x1400b3e9e  mov     [rsp+0E8h+var_A4], eax
0x1400b3ea2  test    eax, eax
0x1400b3ea4  js      loc_1400B3F82
0x1400b3eaa  mov     [rsp+0E8h+Sid], r14; Sid
0x1400b3eaf  mov     edx, 2; AceRevision
0x1400b3eb4  mov     r9d, 0A0000000h; AccessMask
0x1400b3eba  lea     r8d, [rdx+9]; AceFlags
0x1400b3ebe  mov     rcx, rdi; Acl
0x1400b3ec1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3ec8  nop     dword ptr [rax+rax+00h]
0x1400b3ecd  mov     ebx, eax
0x1400b3ecf  mov     [rsp+0E8h+var_A4], eax
0x1400b3ed3  test    eax, eax
0x1400b3ed5  js      loc_1400B3F82
0x1400b3edb  mov     edx, 1; Revision
0x1400b3ee0  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1400b3ee5  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b3eec  nop     dword ptr [rax+rax+00h]
0x1400b3ef1  mov     ebx, eax
0x1400b3ef3  mov     [rsp+0E8h+var_A4], eax
0x1400b3ef7  test    eax, eax
0x1400b3ef9  js      loc_1400B3F82
0x1400b3eff  xor     r9d, r9d; DaclDefaulted
0x1400b3f02  mov     r8, rdi; Dacl
0x1400b3f05  mov     dl, 1; DaclPresent
0x1400b3f07  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1400b3f0c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b3f13  nop     dword ptr [rax+rax+00h]
0x1400b3f18  mov     ebx, eax
0x1400b3f1a  mov     [rsp+0E8h+var_A4], eax
0x1400b3f1e  test    eax, eax
0x1400b3f20  js      short loc_1400B3F82
0x1400b3f22  mov     ebx, cs:PoolType
0x1400b3f28  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b3f2f  nop     dword ptr [rax+rax+00h]
0x1400b3f34  mov     [rsp+0E8h+PoolType], ebx; PoolType
0x1400b3f38  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x1400b3f3d  mov     [rsp+0E8h+Sid], rsi; SubjectContext
0x1400b3f42  xor     r9d, r9d; IsDirectoryObject
0x1400b3f45  lea     r8, ModificationDescriptor; NewDescriptor
0x1400b3f4c  lea     rdx, [rsp+0E8h+SecurityDescriptor]; ExplicitDescriptor
0x1400b3f51  xor     ecx, ecx; ParentDescriptor
0x1400b3f53  call    cs:__imp_SeAssignSecurity
0x1400b3f5a  nop     dword ptr [rax+rax+00h]
0x1400b3f5f  mov     ebx, eax
0x1400b3f61  mov     [rsp+0E8h+var_A4], eax
0x1400b3f65  test    eax, eax
0x1400b3f67  js      short loc_1400B3F82
0x1400b3f69  mov     rcx, cs:ModificationDescriptor; SecurityDescriptor
0x1400b3f70  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400b3f77  nop     dword ptr [rax+rax+00h]
0x1400b3f7c  mov     cs:dword_1402612C8, eax
0x1400b3f82  mov     rcx, rsi; SubjectContext
0x1400b3f85  call    cs:__imp_SeReleaseSubjectContext
0x1400b3f8c  nop     dword ptr [rax+rax+00h]
0x1400b3f91  test    rsi, rsi
0x1400b3f94  jz      short loc_1400B3FA7
0x1400b3f96  xor     edx, edx; Tag
0x1400b3f98  mov     rcx, rsi; P
0x1400b3f9b  call    cs:__imp_ExFreePoolWithTag
0x1400b3fa2  nop     dword ptr [rax+rax+00h]
0x1400b3fa7  test    rdi, rdi
0x1400b3faa  jz      short loc_1400B3FBD
0x1400b3fac  xor     edx, edx; Tag
0x1400b3fae  mov     rcx, rdi; P
0x1400b3fb1  call    cs:__imp_ExFreePoolWithTag
0x1400b3fb8  nop     dword ptr [rax+rax+00h]
0x1400b3fbd  xor     edx, edx; Tag
0x1400b3fbf  mov     rcx, r13; P
0x1400b3fc2  call    cs:__imp_ExFreePoolWithTag
0x1400b3fc9  nop     dword ptr [rax+rax+00h]
0x1400b3fce  xor     edx, edx; Tag
0x1400b3fd0  mov     rcx, r15; P
0x1400b3fd3  call    cs:__imp_ExFreePoolWithTag
0x1400b3fda  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
