# FltpSysVolCreateSecurityDescriptor

- ea: `0x180075120`
- end: `0x1800753b8`
- name: `FltpSysVolCreateSecurityDescriptor`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180074ef0`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180075120`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180075291`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007532f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075378`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075291`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007532f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075378`
- `ntoskrnl!ExAllocatePool2` at `0x1800751b4`
- `ntoskrnl!ExAllocatePool2` at `0x1800751b4`
- `ntoskrnl!RtlLengthSid` at `0x180075194`
- `ntoskrnl!RtlLengthSid` at `0x180075194`
- `ntoskrnl!RtlInitializeSid` at `0x18007516a`
- `ntoskrnl!RtlInitializeSid` at `0x180075217`
- `ntoskrnl!RtlInitializeSid` at `0x18007516a`
- `ntoskrnl!RtlInitializeSid` at `0x180075217`
- `ntoskrnl!RtlSubAuthoritySid` at `0x18007517d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180075229`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180075244`
- `ntoskrnl!RtlSubAuthoritySid` at `0x18007517d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180075229`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180075244`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1800751e2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1800751e2`
- `ntoskrnl!RtlCreateAcl` at `0x1800752b3`
- `ntoskrnl!RtlCreateAcl` at `0x1800752b3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x180075347`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x180075347`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x180075260`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x180075260`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1800752fe`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1800752fe`

## pseudocode

```c
__int64 __fastcall FltpSysVolCreateSecurityDescriptor(struct _ACL **a1, _QWORD *a2)
{
  ULONG v4; // esi
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rbx
  __int64 result; // rax
  unsigned int SecurityDescriptor; // edi
  unsigned int Acl; // esi
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-38h] BYREF
  __int64 Sid; // [rsp+38h] [rbp-30h] BYREF
  int v12; // [rsp+40h] [rbp-28h]

  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = 0;
  v12 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitializeSid(&Sid, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(&Sid, 0) = 18;
  v4 = RtlLengthSid(&Sid) + 16;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v4 + 56LL, 1685278022);
  v6 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  SecurityDescriptor = RtlCreateSecurityDescriptor(Pool2, 1u);
  if ( (int)FltpDbgStatus(SecurityDescriptor, "minkernel\\fs\\filtermgr\\filter\\sysvol.c", 270, 0) >= 0
    && (RtlInitializeSid(&v6[5], &IdentifierAuthority, 2u),
        *RtlSubAuthoritySid(&v6[5], 0) = 32,
        *RtlSubAuthoritySid(&v6[5], 1u) = 544,
        SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v6, &v6[5], 0),
        (int)FltpDbgStatus(SecurityDescriptor, "minkernel\\fs\\filtermgr\\filter\\sysvol.c", 288, 0) >= 0) )
  {
    Acl = RtlCreateAcl(v6 + 7, v4, 2u);
    if ( (int)FltpDbgStatus(Acl, "minkernel\\fs\\filtermgr\\filter\\sysvol.c", 302, 0) >= 0
      && (Acl = RtlAddAccessAllowedAceEx(v6 + 7, 2u, 3u, 0x1FFFFFu, &Sid),
          (int)FltpDbgStatus(Acl, "minkernel\\fs\\filtermgr\\filter\\sysvol.c", 314, 0) >= 0)
      && (Acl = RtlSetDaclSecurityDescriptor(v6, 1u, v6 + 7, 0),
          (int)FltpDbgStatus(Acl, "minkernel\\fs\\filtermgr\\filter\\sysvol.c", 322, 0) >= 0) )
    {
      *a1 = v6;
      result = 0;
      *a2 = v6 + 7;
    }
    else
    {
      ExFreePoolWithTag(v6, 0x64734D46u);
      return Acl;
    }
  }
  else
  {
    ExFreePoolWithTag(v6, 0x64734D46u);
    return SecurityDescriptor;
  }
  return result;
}

```

## disassembly

```asm
0x180075120  mov     [rsp+arg_18], rbx
0x180075125  push    rsi
0x180075126  push    r14
0x180075128  push    r15
0x18007512a  sub     rsp, 50h
0x18007512e  mov     rax, cs:__security_cookie
0x180075135  xor     rax, rsp
0x180075138  mov     [rsp+68h+var_20], rax
0x18007513d  xor     eax, eax
0x18007513f  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x180075147  mov     r15, rdx
0x18007514a  mov     [rsp+68h+Sid], rax
0x18007514f  mov     r14, rcx
0x180075152  mov     [rsp+68h+var_28], eax
0x180075156  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x18007515b  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x180075162  lea     rcx, [rsp+68h+Sid]; Sid
0x180075167  mov     r8b, 1; SubAuthorityCount
0x18007516a  call    cs:__imp_RtlInitializeSid
0x180075171  nop     dword ptr [rax+rax+00h]
0x180075176  xor     edx, edx; SubAuthority
0x180075178  lea     rcx, [rsp+68h+Sid]; Sid
0x18007517d  call    cs:__imp_RtlSubAuthoritySid
0x180075184  nop     dword ptr [rax+rax+00h]
0x180075189  lea     rcx, [rsp+68h+Sid]; Sid
0x18007518e  mov     dword ptr [rax], 12h
0x180075194  call    cs:__imp_RtlLengthSid
0x18007519b  nop     dword ptr [rax+rax+00h]
0x1800751a0  mov     ecx, 100h
0x1800751a5  mov     r8d, 64734D46h
0x1800751ab  lea     esi, [rax+10h]
0x1800751ae  mov     edx, esi
0x1800751b0  add     rdx, 38h ; '8'
0x1800751b4  call    cs:__imp_ExAllocatePool2
0x1800751bb  nop     dword ptr [rax+rax+00h]
0x1800751c0  mov     rbx, rax
0x1800751c3  test    rax, rax
0x1800751c6  jnz     short loc_1800751D2
0x1800751c8  mov     eax, 0C000009Ah
0x1800751cd  jmp     loc_180075398
0x1800751d2  mov     edx, 1; Revision
0x1800751d7  mov     [rsp+68h+arg_10], rdi
0x1800751df  mov     rcx, rbx; SecurityDescriptor
0x1800751e2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800751e9  nop     dword ptr [rax+rax+00h]
0x1800751ee  mov     r8d, 10Eh
0x1800751f4  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x1800751fb  mov     ecx, eax
0x1800751fd  xor     r9d, r9d
0x180075200  mov     edi, eax
0x180075202  call    FltpDbgStatus
0x180075207  test    eax, eax
0x180075209  js      short loc_180075289
0x18007520b  mov     r8b, 2; SubAuthorityCount
0x18007520e  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x180075213  lea     rcx, [rbx+28h]; Sid
0x180075217  call    cs:__imp_RtlInitializeSid
0x18007521e  nop     dword ptr [rax+rax+00h]
0x180075223  xor     edx, edx; SubAuthority
0x180075225  lea     rcx, [rbx+28h]; Sid
0x180075229  call    cs:__imp_RtlSubAuthoritySid
0x180075230  nop     dword ptr [rax+rax+00h]
0x180075235  mov     edx, 1; SubAuthority
0x18007523a  lea     rcx, [rbx+28h]; Sid
0x18007523e  mov     dword ptr [rax], 20h ; ' '
0x180075244  call    cs:__imp_RtlSubAuthoritySid
0x18007524b  nop     dword ptr [rax+rax+00h]
0x180075250  xor     r8d, r8d; OwnerDefaulted
0x180075253  lea     rdx, [rbx+28h]; Owner
0x180075257  mov     rcx, rbx; SecurityDescriptor
0x18007525a  mov     dword ptr [rax], 220h
0x180075260  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180075267  nop     dword ptr [rax+rax+00h]
0x18007526c  mov     r8d, 120h
0x180075272  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x180075279  mov     ecx, eax
0x18007527b  xor     r9d, r9d
0x18007527e  mov     edi, eax
0x180075280  call    FltpDbgStatus
0x180075285  test    eax, eax
0x180075287  jns     short loc_1800752A4
0x180075289  mov     edx, 64734D46h; Tag
0x18007528e  mov     rcx, rbx; P
0x180075291  call    cs:__imp_ExFreePoolWithTag
0x180075298  nop     dword ptr [rax+rax+00h]
0x18007529d  mov     eax, edi
0x18007529f  jmp     loc_180075390
0x1800752a4  lea     rdi, [rbx+38h]
0x1800752a8  mov     r8d, 2; AclRevision
0x1800752ae  mov     rcx, rdi; Acl
0x1800752b1  mov     edx, esi; AclLength
0x1800752b3  call    cs:__imp_RtlCreateAcl
0x1800752ba  nop     dword ptr [rax+rax+00h]
0x1800752bf  mov     r8d, 12Eh
0x1800752c5  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x1800752cc  mov     ecx, eax
0x1800752ce  xor     r9d, r9d
0x1800752d1  mov     esi, eax
0x1800752d3  call    FltpDbgStatus
0x1800752d8  test    eax, eax
0x1800752da  js      loc_180075370
0x1800752e0  lea     rax, [rsp+68h+Sid]
0x1800752e5  mov     edx, 2; AceRevision
0x1800752ea  mov     r9d, 1FFFFFh; AccessMask
0x1800752f0  mov     [rsp+68h+var_48], rax; Sid
0x1800752f5  mov     r8d, 3; AceFlags
0x1800752fb  mov     rcx, rdi; Acl
0x1800752fe  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180075305  nop     dword ptr [rax+rax+00h]
0x18007530a  mov     r8d, 13Ah
0x180075310  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x180075317  mov     ecx, eax
0x180075319  xor     r9d, r9d
0x18007531c  mov     esi, eax
0x18007531e  call    FltpDbgStatus
0x180075323  mov     rcx, rbx; SecurityDescriptor
0x180075326  test    eax, eax
0x180075328  jns     short loc_18007533F
0x18007532a  mov     edx, 64734D46h; Tag
0x18007532f  call    cs:__imp_ExFreePoolWithTag
0x180075336  nop     dword ptr [rax+rax+00h]
0x18007533b  mov     eax, esi
0x18007533d  jmp     short loc_180075390
0x18007533f  xor     r9d, r9d; DaclDefaulted
0x180075342  mov     r8, rdi; Dacl
0x180075345  mov     dl, 1; DaclPresent
0x180075347  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18007534e  nop     dword ptr [rax+rax+00h]
0x180075353  mov     r8d, 142h
0x180075359  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x180075360  mov     ecx, eax
0x180075362  xor     r9d, r9d
0x180075365  mov     esi, eax
0x180075367  call    FltpDbgStatus
0x18007536c  test    eax, eax
0x18007536e  jns     short loc_180075388
0x180075370  mov     edx, 64734D46h; Tag
0x180075375  mov     rcx, rbx; P
0x180075378  call    cs:__imp_ExFreePoolWithTag
0x18007537f  nop     dword ptr [rax+rax+00h]
0x180075384  mov     eax, esi
0x180075386  jmp     short loc_180075390
0x180075388  mov     [r14], rbx
0x18007538b  xor     eax, eax
0x18007538d  mov     [r15], rdi
0x180075390  mov     rdi, [rsp+68h+arg_10]
0x180075398  mov     rcx, [rsp+68h+var_20]
0x18007539d  xor     rcx, rsp; StackCookie
0x1800753a0  call    __security_check_cookie
0x1800753a5  mov     rbx, [rsp+68h+arg_18]
0x1800753ad  add     rsp, 50h
0x1800753b1  pop     r15
0x1800753b3  pop     r14
0x1800753b5  pop     rsi
0x1800753b6  retn
```
