# FltBuildDefaultSecurityDescriptor

- ea: `0x180053cb0`
- end: `0x180053fa8`
- name: `FltBuildDefaultSecurityDescriptor`
- size: `760`
- prototype: `NTSTATUS __stdcall(PSECURITY_DESCRIPTOR *SecurityDescriptor, ACCESS_MASK DesiredAccess)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180053cb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180053f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x180053f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180053f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x180053f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x180053f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180053f74`
- `ntoskrnl!ExAllocatePool2` at `0x180053d04`
- `ntoskrnl!ExAllocatePool2` at `0x180053d8a`
- `ntoskrnl!ExAllocatePool2` at `0x180053dee`
- `ntoskrnl!ExAllocatePool2` at `0x180053d04`
- `ntoskrnl!ExAllocatePool2` at `0x180053d8a`
- `ntoskrnl!ExAllocatePool2` at `0x180053dee`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180053ce9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180053d73`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180053ce9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180053d73`
- `ntoskrnl!RtlInitializeSid` at `0x180053d2f`
- `ntoskrnl!RtlInitializeSid` at `0x180053dad`
- `ntoskrnl!RtlInitializeSid` at `0x180053d2f`
- `ntoskrnl!RtlInitializeSid` at `0x180053dad`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053d40`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053d5e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053dbe`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053d40`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053d5e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180053dbe`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x180053e0c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x180053e0c`
- `ntoskrnl!RtlCreateAcl` at `0x180053e4a`
- `ntoskrnl!RtlCreateAcl` at `0x180053e4a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x180053e88`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x180053ebb`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x180053e88`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x180053ebb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x180053eeb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x180053eeb`

## pseudocode

```c
NTSTATUS __stdcall FltBuildDefaultSecurityDescriptor(
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        ACCESS_MASK DesiredAccess)
{
  struct _ACL *v2; // rdi
  ULONG v5; // eax
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v7; // rbp
  unsigned __int8 *v8; // rsi
  NTSTATUS Acl; // ebx
  ULONG v10; // eax
  unsigned __int8 *v11; // rax
  unsigned int v12; // r13d
  struct _ACL *v13; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-48h] BYREF

  v2 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v5 = RtlLengthRequiredSid(2u);
  Pool2 = (unsigned __int8 *)ExAllocatePool2(256, v5, 1685278022);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = 0;
LABEL_3:
    Acl = -1073741670;
    goto LABEL_12;
  }
  RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v7, 0) = 32;
  *RtlSubAuthoritySid(v7, 1u) = 544;
  v10 = RtlLengthRequiredSid(1u);
  v11 = (unsigned __int8 *)ExAllocatePool2(256, v10, 1685278022);
  v8 = v11;
  if ( !v11 )
    goto LABEL_3;
  RtlInitializeSid(v11, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v8, 0) = 18;
  v12 = 4 * (v7[1] + v8[1]) + 88;
  v13 = (struct _ACL *)ExAllocatePool2(256, v12, 1685278022);
  v2 = v13;
  if ( !v13 )
    goto LABEL_3;
  Acl = RtlCreateSecurityDescriptor(v13, 1u);
  if ( (int)FltpDbgStatus(Acl) >= 0 )
  {
    Acl = RtlCreateAcl(v2 + 5, v12 - 40, 2u);
    if ( (int)FltpDbgStatus(Acl) >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v2 + 5, 2u, DesiredAccess, v7);
      if ( (int)FltpDbgStatus(Acl) >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v2 + 5, 2u, DesiredAccess, v8);
        if ( (int)FltpDbgStatus(Acl) >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(v2, 1u, v2 + 5, 0);
          if ( (int)FltpDbgStatus(Acl) >= 0 )
            *SecurityDescriptor = v2;
        }
      }
    }
  }
LABEL_12:
  if ( (int)FltpDbgStatus(Acl) < 0 )
  {
    *SecurityDescriptor = 0;
    if ( v2 )
      ExFreePoolWithTag(v2, 0x64734D46u);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0x64734D46u);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x64734D46u);
  return Acl;
}

```

## disassembly

```asm
0x180053cb0  mov     [rsp+arg_10], rbx
0x180053cb5  push    rbp
0x180053cb6  push    rsi
0x180053cb7  push    rdi
0x180053cb8  push    r12
0x180053cba  push    r13
0x180053cbc  push    r14
0x180053cbe  push    r15
0x180053cc0  sub     rsp, 30h
0x180053cc4  mov     rax, cs:__security_cookie
0x180053ccb  xor     rax, rsp
0x180053cce  mov     [rsp+68h+var_40], rax
0x180053cd3  xor     edi, edi
0x180053cd5  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x180053cdc  mov     r15, rcx
0x180053cdf  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], edi
0x180053ce3  mov     r12d, edx
0x180053ce6  lea     ecx, [rdi+2]; SubAuthorityCount
0x180053ce9  call    cs:__imp_RtlLengthRequiredSid
0x180053cf0  nop     dword ptr [rax+rax+00h]
0x180053cf5  mov     ebx, 100h
0x180053cfa  mov     edx, eax
0x180053cfc  mov     ecx, ebx
0x180053cfe  mov     r8d, 64734D46h
0x180053d04  call    cs:__imp_ExAllocatePool2
0x180053d0b  nop     dword ptr [rax+rax+00h]
0x180053d10  mov     rbp, rax
0x180053d13  test    rax, rax
0x180053d16  jnz     short loc_180053D24
0x180053d18  xor     esi, esi
0x180053d1a  mov     ebx, 0C000009Ah
0x180053d1f  jmp     loc_180053F13
0x180053d24  mov     r8b, 2; SubAuthorityCount
0x180053d27  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x180053d2c  mov     rcx, rbp; Sid
0x180053d2f  call    cs:__imp_RtlInitializeSid
0x180053d36  nop     dword ptr [rax+rax+00h]
0x180053d3b  xor     edx, edx; SubAuthority
0x180053d3d  mov     rcx, rbp; Sid
0x180053d40  call    cs:__imp_RtlSubAuthoritySid
0x180053d47  nop     dword ptr [rax+rax+00h]
0x180053d4c  mov     r14d, 1
0x180053d52  mov     rcx, rbp; Sid
0x180053d55  mov     edx, r14d; SubAuthority
0x180053d58  mov     dword ptr [rax], 20h ; ' '
0x180053d5e  call    cs:__imp_RtlSubAuthoritySid
0x180053d65  nop     dword ptr [rax+rax+00h]
0x180053d6a  mov     ecx, r14d; SubAuthorityCount
0x180053d6d  mov     dword ptr [rax], 220h
0x180053d73  call    cs:__imp_RtlLengthRequiredSid
0x180053d7a  nop     dword ptr [rax+rax+00h]
0x180053d7f  mov     edx, eax
0x180053d81  mov     r8d, 64734D46h
0x180053d87  mov     rcx, rbx
0x180053d8a  call    cs:__imp_ExAllocatePool2
0x180053d91  nop     dword ptr [rax+rax+00h]
0x180053d96  mov     rsi, rax
0x180053d99  test    rax, rax
0x180053d9c  jz      loc_180053D1A
0x180053da2  mov     r8b, r14b; SubAuthorityCount
0x180053da5  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x180053daa  mov     rcx, rax; Sid
0x180053dad  call    cs:__imp_RtlInitializeSid
0x180053db4  nop     dword ptr [rax+rax+00h]
0x180053db9  xor     edx, edx; SubAuthority
0x180053dbb  mov     rcx, rsi; Sid
0x180053dbe  call    cs:__imp_RtlSubAuthoritySid
0x180053dc5  nop     dword ptr [rax+rax+00h]
0x180053dca  mov     r8d, 64734D46h
0x180053dd0  mov     rcx, rbx
0x180053dd3  mov     dword ptr [rax], 12h
0x180053dd9  movzx   edx, byte ptr [rsi+1]
0x180053ddd  movzx   eax, byte ptr [rbp+1]
0x180053de1  add     edx, eax
0x180053de3  lea     r13d, ds:58h[rdx*4]
0x180053deb  mov     edx, r13d
0x180053dee  call    cs:__imp_ExAllocatePool2
0x180053df5  nop     dword ptr [rax+rax+00h]
0x180053dfa  mov     rdi, rax
0x180053dfd  test    rax, rax
0x180053e00  jz      loc_180053D1A
0x180053e06  mov     edx, r14d; Revision
0x180053e09  mov     rcx, rax; SecurityDescriptor
0x180053e0c  call    cs:__imp_RtlCreateSecurityDescriptor
0x180053e13  nop     dword ptr [rax+rax+00h]
0x180053e18  mov     r8d, 0F4Bh
0x180053e1e  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180053e25  mov     ecx, eax
0x180053e27  xor     r9d, r9d
0x180053e2a  mov     ebx, eax
0x180053e2c  call    FltpDbgStatus
0x180053e31  test    eax, eax
0x180053e33  js      loc_180053F13
0x180053e39  lea     r14, [rdi+28h]
0x180053e3d  mov     r8d, 2; AclRevision
0x180053e43  mov     rcx, r14; Acl
0x180053e46  lea     edx, [r13-28h]; AclLength
0x180053e4a  call    cs:__imp_RtlCreateAcl
0x180053e51  nop     dword ptr [rax+rax+00h]
0x180053e56  lea     r13, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180053e5d  mov     r8d, 0F57h
0x180053e63  mov     rdx, r13
0x180053e66  mov     ecx, eax
0x180053e68  xor     r9d, r9d
0x180053e6b  mov     ebx, eax
0x180053e6d  call    FltpDbgStatus
0x180053e72  test    eax, eax
0x180053e74  js      loc_180053F13
0x180053e7a  mov     r9, rbp; Sid
0x180053e7d  mov     r8d, r12d; AccessMask
0x180053e80  mov     edx, 2; AceRevision
0x180053e85  mov     rcx, r14; Acl
0x180053e88  call    cs:__imp_RtlAddAccessAllowedAce
0x180053e8f  nop     dword ptr [rax+rax+00h]
0x180053e94  mov     r8d, 0F61h
0x180053e9a  xor     r9d, r9d
0x180053e9d  mov     ecx, eax
0x180053e9f  mov     rdx, r13
0x180053ea2  mov     ebx, eax
0x180053ea4  call    FltpDbgStatus
0x180053ea9  test    eax, eax
0x180053eab  js      short loc_180053F13
0x180053ead  mov     r9, rsi; Sid
0x180053eb0  mov     r8d, r12d; AccessMask
0x180053eb3  mov     edx, 2; AceRevision
0x180053eb8  mov     rcx, r14; Acl
0x180053ebb  call    cs:__imp_RtlAddAccessAllowedAce
0x180053ec2  nop     dword ptr [rax+rax+00h]
0x180053ec7  mov     r8d, 0F6Bh
0x180053ecd  xor     r9d, r9d
0x180053ed0  mov     ecx, eax
0x180053ed2  mov     rdx, r13
0x180053ed5  mov     ebx, eax
0x180053ed7  call    FltpDbgStatus
0x180053edc  test    eax, eax
0x180053ede  js      short loc_180053F13
0x180053ee0  xor     r9d, r9d; DaclDefaulted
0x180053ee3  mov     r8, r14; Dacl
0x180053ee6  mov     dl, 1; DaclPresent
0x180053ee8  mov     rcx, rdi; SecurityDescriptor
0x180053eeb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180053ef2  nop     dword ptr [rax+rax+00h]
0x180053ef7  mov     r8d, 0F79h
0x180053efd  xor     r9d, r9d
0x180053f00  mov     ecx, eax
0x180053f02  mov     rdx, r13
0x180053f05  mov     ebx, eax
0x180053f07  call    FltpDbgStatus
0x180053f0c  test    eax, eax
0x180053f0e  js      short loc_180053F13
0x180053f10  mov     [r15], rdi
0x180053f13  mov     r8d, 0F81h
0x180053f19  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180053f20  xor     r9d, r9d
0x180053f23  mov     ecx, ebx
0x180053f25  call    FltpDbgStatus
0x180053f2a  test    eax, eax
0x180053f2c  jns     short loc_180053F4E
0x180053f2e  mov     qword ptr [r15], 0
0x180053f35  test    rdi, rdi
0x180053f38  jz      short loc_180053F4E
0x180053f3a  mov     edx, 64734D46h; Tag
0x180053f3f  mov     rcx, rdi; P
0x180053f42  call    cs:__imp_ExFreePoolWithTag
0x180053f49  nop     dword ptr [rax+rax+00h]
0x180053f4e  test    rbp, rbp
0x180053f51  jz      short loc_180053F67
0x180053f53  mov     edx, 64734D46h; Tag
0x180053f58  mov     rcx, rbp; P
0x180053f5b  call    cs:__imp_ExFreePoolWithTag
0x180053f62  nop     dword ptr [rax+rax+00h]
0x180053f67  test    rsi, rsi
0x180053f6a  jz      short loc_180053F80
0x180053f6c  mov     edx, 64734D46h; Tag
0x180053f71  mov     rcx, rsi; P
0x180053f74  call    cs:__imp_ExFreePoolWithTag
0x180053f7b  nop     dword ptr [rax+rax+00h]
0x180053f80  mov     eax, ebx
0x180053f82  mov     rcx, [rsp+68h+var_40]
0x180053f87  xor     rcx, rsp; StackCookie
0x180053f8a  call    __security_check_cookie
0x180053f8f  mov     rbx, [rsp+68h+arg_10]
0x180053f97  add     rsp, 30h
0x180053f9b  pop     r15
0x180053f9d  pop     r14
0x180053f9f  pop     r13
0x180053fa1  pop     r12
0x180053fa3  pop     rdi
0x180053fa4  pop     rsi
0x180053fa5  pop     rbp
0x180053fa6  retn
```
