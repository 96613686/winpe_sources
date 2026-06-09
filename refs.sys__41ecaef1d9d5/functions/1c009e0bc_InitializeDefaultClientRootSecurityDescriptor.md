# InitializeDefaultClientRootSecurityDescriptor

- ea: `0x1c009e0bc`
- end: `0x1c009e730`
- name: `InitializeDefaultClientRootSecurityDescriptor`
- size: `1652`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c01d97ac`

## callees

- `0x1c000f770`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c009e0bc`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e13d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e17f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e1ee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e249`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e2a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e329`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e13d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e17f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e1ee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e249`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e2a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009e329`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e571`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e587`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e704`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e71c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e571`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e587`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e5cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e6ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e704`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009e71c`
- `ntoskrnl!ExRaiseStatus` at `0x1c009e639`
- `ntoskrnl!ExRaiseStatus` at `0x1c009e639`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c009e154`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c009e154`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c009e55b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c009e68c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c009e55b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c009e68c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e16c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e1db`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e236`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e291`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e16c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e1db`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e236`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c009e291`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e1a1`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e210`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e26b`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e2c6`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e1a1`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e210`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e26b`
- `ntoskrnl!RtlInitializeSid` at `0x1c009e2c6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e1b2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e1c6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e221`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e27c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e2d7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e2eb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e1b2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e1c6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e221`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e27c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e2d7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c009e2eb`
- `ntoskrnl!RtlCreateAcl` at `0x1c009e348`
- `ntoskrnl!RtlCreateAcl` at `0x1c009e348`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c009e4bd`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c009e4bd`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c009e4e4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c009e4e4`
- `ntoskrnl!SeAssignSecurity` at `0x1c009e529`
- `ntoskrnl!SeAssignSecurity` at `0x1c009e529`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c009e4fa`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c009e4fa`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c009e546`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c009e546`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e379`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e3a8`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e3d9`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e408`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e439`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e468`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e499`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e379`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e3a8`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e3d9`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e408`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e439`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e468`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c009e499`

## pseudocode

```c
void InitializeDefaultClientRootSecurityDescriptor()
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
  NTSTATUS Acl; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS Status; // [rsp+40h] [rbp-88h]
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-50h] BYREF
  __int64 v15; // [rsp+98h] [rbp-30h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-28h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
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
  RtlInitializeSid(v6, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v6, 0) = 11;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1]) + 176;
  v10 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)17, v9, 0x4A666552u);
  Acl = RtlCreateAcl(v10, v9, 2u);
  Status = Acl;
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v10, 2u, 3u, 0x10000000u, Sid);
    Status = Acl;
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0x10000000u, v4);
      Status = Acl;
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0x10000000u, v4);
        Status = Acl;
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xE0010000, v6);
          Status = Acl;
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xE0010000, v6);
            Status = Acl;
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xA0000000, v8);
              Status = Acl;
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xA0000000, v8);
                Status = Acl;
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  Status = Acl;
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
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
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
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
0x1c009e0bc  mov     r11, rsp
0x1c009e0bf  mov     [r11+8], rbx
0x1c009e0c3  mov     [r11+10h], rsi
0x1c009e0c7  mov     [r11+18h], rdi
0x1c009e0cb  mov     [r11+20h], r12
0x1c009e0cf  push    r13
0x1c009e0d1  push    r14
0x1c009e0d3  push    r15
0x1c009e0d5  sub     rsp, 0B0h
0x1c009e0dc  mov     rax, cs:__security_cookie
0x1c009e0e3  xor     rax, rsp
0x1c009e0e6  mov     [rsp+0C8h+var_20], rax
0x1c009e0ee  xor     ecx, ecx
0x1c009e0f0  mov     [r11-80h], rcx
0x1c009e0f4  mov     [rsp+0C8h+var_84], cl
0x1c009e0f8  mov     [r11-78h], rcx
0x1c009e0fc  mov     [r11-70h], rcx
0x1c009e100  mov     [r11-68h], rcx
0x1c009e104  mov     [r11-60h], rcx
0x1c009e108  mov     [r11-58h], rcx
0x1c009e10c  xorps   xmm0, xmm0
0x1c009e10f  xor     eax, eax
0x1c009e111  movups  [rsp+0C8h+SecurityDescriptor], xmm0
0x1c009e116  movups  xmmword ptr [r11-40h], xmm0
0x1c009e11b  mov     [r11-30h], rax
0x1c009e11f  mov     [r11-28h], ecx
0x1c009e123  mov     word ptr [r11-24h], 500h
0x1c009e12a  mov     r14d, 4A666552h
0x1c009e130  mov     r8d, r14d; Tag
0x1c009e133  lea     ebx, [rcx+20h]
0x1c009e136  mov     edx, ebx; NumberOfBytes
0x1c009e138  lea     edi, [rcx+11h]
0x1c009e13b  mov     ecx, edi; PoolType
0x1c009e13d  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e144  nop     dword ptr [rax+rax+00h]
0x1c009e149  mov     rsi, rax
0x1c009e14c  mov     [rsp+0C8h+var_80], rax
0x1c009e151  mov     rcx, rax; SubjectContext
0x1c009e154  call    cs:__imp_SeCaptureSubjectContext
0x1c009e15b  nop     dword ptr [rax+rax+00h]
0x1c009e160  lea     r12d, [rbx-1Fh]
0x1c009e164  mov     [rsp+0C8h+var_84], r12b
0x1c009e169  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1c009e16c  call    cs:__imp_RtlLengthRequiredSid
0x1c009e173  nop     dword ptr [rax+rax+00h]
0x1c009e178  mov     edx, eax; NumberOfBytes
0x1c009e17a  mov     r8d, r14d; Tag
0x1c009e17d  mov     ecx, edi; PoolType
0x1c009e17f  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e186  nop     dword ptr [rax+rax+00h]
0x1c009e18b  mov     r13, rax
0x1c009e18e  mov     [rsp+0C8h+var_70], rax
0x1c009e193  mov     r8b, 2; SubAuthorityCount
0x1c009e196  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1c009e19e  mov     rcx, rax; Sid
0x1c009e1a1  call    cs:__imp_RtlInitializeSid
0x1c009e1a8  nop     dword ptr [rax+rax+00h]
0x1c009e1ad  xor     edx, edx; SubAuthority
0x1c009e1af  mov     rcx, r13; Sid
0x1c009e1b2  call    cs:__imp_RtlSubAuthoritySid
0x1c009e1b9  nop     dword ptr [rax+rax+00h]
0x1c009e1be  mov     [rax], ebx
0x1c009e1c0  mov     edx, r12d; SubAuthority
0x1c009e1c3  mov     rcx, r13; Sid
0x1c009e1c6  call    cs:__imp_RtlSubAuthoritySid
0x1c009e1cd  nop     dword ptr [rax+rax+00h]
0x1c009e1d2  mov     dword ptr [rax], 220h
0x1c009e1d8  mov     ecx, r12d; SubAuthorityCount
0x1c009e1db  call    cs:__imp_RtlLengthRequiredSid
0x1c009e1e2  nop     dword ptr [rax+rax+00h]
0x1c009e1e7  mov     edx, eax; NumberOfBytes
0x1c009e1e9  mov     r8d, r14d; Tag
0x1c009e1ec  mov     ecx, edi; PoolType
0x1c009e1ee  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e1f5  nop     dword ptr [rax+rax+00h]
0x1c009e1fa  mov     r15, rax
0x1c009e1fd  mov     [rsp+0C8h+var_68], rax
0x1c009e202  mov     r8b, r12b; SubAuthorityCount
0x1c009e205  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1c009e20d  mov     rcx, rax; Sid
0x1c009e210  call    cs:__imp_RtlInitializeSid
0x1c009e217  nop     dword ptr [rax+rax+00h]
0x1c009e21c  xor     edx, edx; SubAuthority
0x1c009e21e  mov     rcx, r15; Sid
0x1c009e221  call    cs:__imp_RtlSubAuthoritySid
0x1c009e228  nop     dword ptr [rax+rax+00h]
0x1c009e22d  mov     dword ptr [rax], 12h
0x1c009e233  mov     ecx, r12d; SubAuthorityCount
0x1c009e236  call    cs:__imp_RtlLengthRequiredSid
0x1c009e23d  nop     dword ptr [rax+rax+00h]
0x1c009e242  mov     edx, eax; NumberOfBytes
0x1c009e244  mov     r8d, r14d; Tag
0x1c009e247  mov     ecx, edi; PoolType
0x1c009e249  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e250  nop     dword ptr [rax+rax+00h]
0x1c009e255  mov     r12, rax
0x1c009e258  mov     [rsp+0C8h+var_60], rax
0x1c009e25d  mov     r8b, 1; SubAuthorityCount
0x1c009e260  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1c009e268  mov     rcx, rax; Sid
0x1c009e26b  call    cs:__imp_RtlInitializeSid
0x1c009e272  nop     dword ptr [rax+rax+00h]
0x1c009e277  xor     edx, edx; SubAuthority
0x1c009e279  mov     rcx, r12; Sid
0x1c009e27c  call    cs:__imp_RtlSubAuthoritySid
0x1c009e283  nop     dword ptr [rax+rax+00h]
0x1c009e288  mov     dword ptr [rax], 0Bh
0x1c009e28e  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1c009e291  call    cs:__imp_RtlLengthRequiredSid
0x1c009e298  nop     dword ptr [rax+rax+00h]
0x1c009e29d  mov     edx, eax; NumberOfBytes
0x1c009e29f  mov     r8d, r14d; Tag
0x1c009e2a2  mov     ecx, edi; PoolType
0x1c009e2a4  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e2ab  nop     dword ptr [rax+rax+00h]
0x1c009e2b0  mov     r14, rax
0x1c009e2b3  mov     [rsp+0C8h+var_58], rax
0x1c009e2b8  mov     r8b, 2; SubAuthorityCount
0x1c009e2bb  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1c009e2c3  mov     rcx, rax; Sid
0x1c009e2c6  call    cs:__imp_RtlInitializeSid
0x1c009e2cd  nop     dword ptr [rax+rax+00h]
0x1c009e2d2  xor     edx, edx; SubAuthority
0x1c009e2d4  mov     rcx, r14; Sid
0x1c009e2d7  call    cs:__imp_RtlSubAuthoritySid
0x1c009e2de  nop     dword ptr [rax+rax+00h]
0x1c009e2e3  mov     [rax], ebx
0x1c009e2e5  lea     edx, [rbx-1Fh]; SubAuthority
0x1c009e2e8  mov     rcx, r14; Sid
0x1c009e2eb  call    cs:__imp_RtlSubAuthoritySid
0x1c009e2f2  nop     dword ptr [rax+rax+00h]
0x1c009e2f7  mov     dword ptr [rax], 221h
0x1c009e2fd  movzx   ebx, byte ptr [r14+1]
0x1c009e302  movzx   eax, byte ptr [r12+1]
0x1c009e308  add     ebx, eax
0x1c009e30a  movzx   eax, byte ptr [r15+1]
0x1c009e30f  add     ebx, eax
0x1c009e311  movzx   eax, byte ptr [r13+1]
0x1c009e316  add     ebx, eax
0x1c009e318  lea     ebx, ds:0B0h[rbx*4]
0x1c009e31f  mov     edx, ebx; NumberOfBytes
0x1c009e321  mov     r8d, 4A666552h; Tag
0x1c009e327  mov     ecx, edi; PoolType
0x1c009e329  call    cs:__imp_ExAllocatePoolWithTag
0x1c009e330  nop     dword ptr [rax+rax+00h]
0x1c009e335  mov     rdi, rax
0x1c009e338  mov     [rsp+0C8h+var_78], rax
0x1c009e33d  mov     r8d, 2; AclRevision
0x1c009e343  mov     edx, ebx; AclLength
0x1c009e345  mov     rcx, rax; Acl
0x1c009e348  call    cs:__imp_RtlCreateAcl
0x1c009e34f  nop     dword ptr [rax+rax+00h]
0x1c009e354  mov     ebx, eax
0x1c009e356  mov     [rsp+0C8h+Status], eax
0x1c009e35a  test    eax, eax
0x1c009e35c  js      loc_1C009E558
0x1c009e362  mov     [rsp+0C8h+Sid], r13; Sid
0x1c009e367  mov     edx, 2; AceRevision
0x1c009e36c  mov     r9d, 10000000h; AccessMask
0x1c009e372  lea     r8d, [rdx+1]; AceFlags
0x1c009e376  mov     rcx, rdi; Acl
0x1c009e379  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e380  nop     dword ptr [rax+rax+00h]
0x1c009e385  mov     ebx, eax
0x1c009e387  mov     [rsp+0C8h+Status], eax
0x1c009e38b  test    eax, eax
0x1c009e38d  js      loc_1C009E558
0x1c009e393  mov     [rsp+0C8h+Sid], r15; Sid
0x1c009e398  mov     r9d, 10000000h; AccessMask
0x1c009e39e  xor     r8d, r8d; AceFlags
0x1c009e3a1  lea     edx, [r8+2]; AceRevision
0x1c009e3a5  mov     rcx, rdi; Acl
0x1c009e3a8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e3af  nop     dword ptr [rax+rax+00h]
0x1c009e3b4  mov     ebx, eax
0x1c009e3b6  mov     [rsp+0C8h+Status], eax
0x1c009e3ba  test    eax, eax
0x1c009e3bc  js      loc_1C009E558
0x1c009e3c2  mov     [rsp+0C8h+Sid], r15; Sid
0x1c009e3c7  mov     edx, 2; AceRevision
0x1c009e3cc  mov     r9d, 10000000h; AccessMask
0x1c009e3d2  lea     r8d, [rdx+9]; AceFlags
0x1c009e3d6  mov     rcx, rdi; Acl
0x1c009e3d9  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e3e0  nop     dword ptr [rax+rax+00h]
0x1c009e3e5  mov     ebx, eax
0x1c009e3e7  mov     [rsp+0C8h+Status], eax
0x1c009e3eb  test    eax, eax
0x1c009e3ed  js      loc_1C009E558
0x1c009e3f3  mov     [rsp+0C8h+Sid], r12; Sid
0x1c009e3f8  mov     r9d, 0E0010000h; AccessMask
0x1c009e3fe  xor     r8d, r8d; AceFlags
0x1c009e401  lea     edx, [r8+2]; AceRevision
0x1c009e405  mov     rcx, rdi; Acl
0x1c009e408  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e40f  nop     dword ptr [rax+rax+00h]
0x1c009e414  mov     ebx, eax
0x1c009e416  mov     [rsp+0C8h+Status], eax
0x1c009e41a  test    eax, eax
0x1c009e41c  js      loc_1C009E558
0x1c009e422  mov     [rsp+0C8h+Sid], r12; Sid
0x1c009e427  mov     edx, 2; AceRevision
0x1c009e42c  mov     r9d, 0E0010000h; AccessMask
0x1c009e432  lea     r8d, [rdx+9]; AceFlags
0x1c009e436  mov     rcx, rdi; Acl
0x1c009e439  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e440  nop     dword ptr [rax+rax+00h]
0x1c009e445  mov     ebx, eax
0x1c009e447  mov     [rsp+0C8h+Status], eax
0x1c009e44b  test    eax, eax
0x1c009e44d  js      loc_1C009E558
0x1c009e453  mov     [rsp+0C8h+Sid], r14; Sid
0x1c009e458  mov     r9d, 0A0000000h; AccessMask
0x1c009e45e  xor     r8d, r8d; AceFlags
0x1c009e461  lea     edx, [r8+2]; AceRevision
0x1c009e465  mov     rcx, rdi; Acl
0x1c009e468  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e46f  nop     dword ptr [rax+rax+00h]
0x1c009e474  mov     ebx, eax
0x1c009e476  mov     [rsp+0C8h+Status], eax
0x1c009e47a  test    eax, eax
0x1c009e47c  js      loc_1C009E558
0x1c009e482  mov     [rsp+0C8h+Sid], r14; Sid
0x1c009e487  mov     edx, 2; AceRevision
0x1c009e48c  mov     r9d, 0A0000000h; AccessMask
0x1c009e492  lea     r8d, [rdx+9]; AceFlags
0x1c009e496  mov     rcx, rdi; Acl
0x1c009e499  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c009e4a0  nop     dword ptr [rax+rax+00h]
0x1c009e4a5  mov     ebx, eax
0x1c009e4a7  mov     [rsp+0C8h+Status], eax
0x1c009e4ab  test    eax, eax
0x1c009e4ad  js      loc_1C009E558
0x1c009e4b3  mov     edx, 1; Revision
0x1c009e4b8  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1c009e4bd  call    cs:__imp_RtlCreateSecurityDescriptor
0x1c009e4c4  nop     dword ptr [rax+rax+00h]
0x1c009e4c9  mov     ebx, eax
0x1c009e4cb  mov     [rsp+0C8h+Status], eax
0x1c009e4cf  test    eax, eax
0x1c009e4d1  js      loc_1C009E558
0x1c009e4d7  xor     r9d, r9d; DaclDefaulted
0x1c009e4da  mov     r8, rdi; Dacl
0x1c009e4dd  mov     dl, 1; DaclPresent
0x1c009e4df  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1c009e4e4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1c009e4eb  nop     dword ptr [rax+rax+00h]
0x1c009e4f0  mov     ebx, eax
0x1c009e4f2  mov     [rsp+0C8h+Status], eax
0x1c009e4f6  test    eax, eax
0x1c009e4f8  js      short loc_1C009E558
0x1c009e4fa  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c009e501  nop     dword ptr [rax+rax+00h]
0x1c009e506  mov     [rsp+0C8h+PoolType], 1; PoolType
0x1c009e50e  mov     [rsp+0C8h+GenericMapping], rax; GenericMapping
0x1c009e513  mov     [rsp+0C8h+Sid], rsi; SubjectContext
0x1c009e518  xor     r9d, r9d; IsDirectoryObject
0x1c009e51b  lea     r8, SecurityDescriptor; NewDescriptor
0x1c009e522  lea     rdx, [rsp+0C8h+SecurityDescriptor]; ExplicitDescriptor
0x1c009e527  xor     ecx, ecx; ParentDescriptor
0x1c009e529  call    cs:__imp_SeAssignSecurity
0x1c009e530  nop     dword ptr [rax+rax+00h]
0x1c009e535  mov     ebx, eax
0x1c009e537  mov     [rsp+0C8h+Status], eax
0x1c009e53b  test    eax, eax
0x1c009e53d  js      short loc_1C009E558
0x1c009e53f  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1c009e546  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c009e54d  nop     dword ptr [rax+rax+00h]
0x1c009e552  mov     cs:dword_1C012E0E0, eax
0x1c009e558  mov     rcx, rsi; SubjectContext
0x1c009e55b  call    cs:__imp_SeReleaseSubjectContext
0x1c009e562  nop     dword ptr [rax+rax+00h]
0x1c009e567  test    rsi, rsi
0x1c009e56a  jz      short loc_1C009E57D
0x1c009e56c  xor     edx, edx; Tag
0x1c009e56e  mov     rcx, rsi; P
0x1c009e571  call    cs:__imp_ExFreePoolWithTag
0x1c009e578  nop     dword ptr [rax+rax+00h]
0x1c009e57d  test    rdi, rdi
0x1c009e580  jz      short loc_1C009E593
0x1c009e582  xor     edx, edx; Tag
0x1c009e584  mov     rcx, rdi; P
0x1c009e587  call    cs:__imp_ExFreePoolWithTag
0x1c009e58e  nop     dword ptr [rax+rax+00h]
0x1c009e593  xor     edx, edx; Tag
0x1c009e595  mov     rcx, r13; P
0x1c009e598  call    cs:__imp_ExFreePoolWithTag
0x1c009e59f  nop     dword ptr [rax+rax+00h]
0x1c009e5a4  xor     edx, edx; Tag
0x1c009e5a6  mov     rcx, r15; P
0x1c009e5a9  call    cs:__imp_ExFreePoolWithTag
0x1c009e5b0  nop     dword ptr [rax+rax+00h]
0x1c009e5b5  xor     edx, edx; Tag
0x1c009e5b7  mov     rcx, r12; P
0x1c009e5ba  call    cs:__imp_ExFreePoolWithTag
0x1c009e5c1  nop     dword ptr [rax+rax+00h]
0x1c009e5c6  xor     edx, edx; Tag
0x1c009e5c8  mov     rcx, r14; P
0x1c009e5cb  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
