# DfsInitializeSecurity(void)

- ea: `0x1400331fc`
- end: `0x14003339a`
- name: `?DfsInitializeSecurity@@YAEXZ`
- size: `414`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018e88`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x1400331fc`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x140033257`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140033257`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14003332c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14003332c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14003330f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14003330f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400332f2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400332f2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400332d3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400332d3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400332a6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400332a6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140033275`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140033275`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14003334d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14003334d`

## pseudocode

```c
unsigned __int8 DfsInitializeSecurity(void)
{
  char v0; // bl
  DWORD v2; // edi
  struct _ACL *v3; // rax
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  v0 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pGroup) < 0 )
    return 0;
  v2 = GetLengthSid(pGroup) + 20;
  v3 = (struct _ACL *)operator new(v2);
  pDacl = v3;
  if ( v3 )
  {
    if ( InitializeAcl(v3, v2, 2u)
      && AddAccessAllowedAce(pDacl, 2u, 0x20000u, pGroup)
      && InitializeSecurityDescriptor(qword_140071650, 1u)
      && SetSecurityDescriptorOwner(qword_140071650, pGroup, 0)
      && SetSecurityDescriptorGroup(qword_140071650, pGroup, 0)
      && SetSecurityDescriptorDacl(qword_140071650, 1, pDacl, 0) )
    {
      return 1;
    }
    else if ( pDacl )
    {
      operator delete(pDacl);
      pDacl = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1400331fc  mov     [rsp+arg_0], rbx
0x140033201  push    rdi
0x140033202  sub     rsp, 70h
0x140033206  mov     rax, cs:__security_cookie
0x14003320d  xor     rax, rsp
0x140033210  mov     [rsp+78h+var_10], rax
0x140033215  xor     ebx, ebx
0x140033217  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 500h
0x14003321e  lea     rax, pGroup
0x140033225  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], ebx
0x140033229  mov     [rsp+78h+Sid], rax; Sid
0x14003322e  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x140033233  mov     [rsp+78h+SubAuthority7], ebx; SubAuthority7
0x140033237  mov     r9d, 220h; SubAuthority1
0x14003323d  mov     [rsp+78h+SubAuthority6], ebx; SubAuthority6
0x140033241  lea     r8d, [rbx+20h]; SubAuthority0
0x140033245  mov     [rsp+78h+SubAuthority5], ebx; SubAuthority5
0x140033249  mov     dl, 2; SubAuthorityCount
0x14003324b  mov     [rsp+78h+SubAuthority4], ebx; SubAuthority4
0x14003324f  mov     [rsp+78h+SubAuthority3], ebx; SubAuthority3
0x140033253  mov     [rsp+78h+SubAuthority2], ebx; SubAuthority2
0x140033257  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003325e  nop     dword ptr [rax+rax+00h]
0x140033263  test    eax, eax
0x140033265  jns     short loc_14003326E
0x140033267  xor     al, al
0x140033269  jmp     loc_14003337E
0x14003326e  mov     rcx, cs:pGroup; pSid
0x140033275  call    cs:__imp_GetLengthSid
0x14003327c  nop     dword ptr [rax+rax+00h]
0x140033281  lea     edi, [rax+14h]
0x140033284  mov     ecx, edi; Size
0x140033286  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003328b  mov     cs:pDacl, rax
0x140033292  test    rax, rax
0x140033295  jz      loc_14003337C
0x14003329b  mov     r8d, 2; dwAclRevision
0x1400332a1  mov     edx, edi; nAclLength
0x1400332a3  mov     rcx, rax; pAcl
0x1400332a6  call    cs:__imp_InitializeAcl
0x1400332ad  nop     dword ptr [rax+rax+00h]
0x1400332b2  test    eax, eax
0x1400332b4  jz      loc_140033361
0x1400332ba  mov     r9, cs:pGroup; pSid
0x1400332c1  mov     edx, 2; dwAceRevision
0x1400332c6  mov     rcx, cs:pDacl; pAcl
0x1400332cd  mov     r8d, 20000h; AccessMask
0x1400332d3  call    cs:__imp_AddAccessAllowedAce
0x1400332da  nop     dword ptr [rax+rax+00h]
0x1400332df  test    eax, eax
0x1400332e1  jz      short loc_140033361
0x1400332e3  lea     rdi, qword_140071650
0x1400332ea  mov     edx, 1; dwRevision
0x1400332ef  mov     rcx, rdi; pSecurityDescriptor
0x1400332f2  call    cs:__imp_InitializeSecurityDescriptor
0x1400332f9  nop     dword ptr [rax+rax+00h]
0x1400332fe  test    eax, eax
0x140033300  jz      short loc_140033361
0x140033302  mov     rdx, cs:pGroup; pOwner
0x140033309  xor     r8d, r8d; bOwnerDefaulted
0x14003330c  mov     rcx, rdi; pSecurityDescriptor
0x14003330f  call    cs:__imp_SetSecurityDescriptorOwner
0x140033316  nop     dword ptr [rax+rax+00h]
0x14003331b  test    eax, eax
0x14003331d  jz      short loc_140033361
0x14003331f  mov     rdx, cs:pGroup; pGroup
0x140033326  xor     r8d, r8d; bGroupDefaulted
0x140033329  mov     rcx, rdi; pSecurityDescriptor
0x14003332c  call    cs:__imp_SetSecurityDescriptorGroup
0x140033333  nop     dword ptr [rax+rax+00h]
0x140033338  test    eax, eax
0x14003333a  jz      short loc_140033361
0x14003333c  mov     r8, cs:pDacl; pDacl
0x140033343  xor     r9d, r9d; bDaclDefaulted
0x140033346  mov     rcx, rdi; pSecurityDescriptor
0x140033349  lea     edx, [r9+1]; bDaclPresent
0x14003334d  call    cs:__imp_SetSecurityDescriptorDacl
0x140033354  nop     dword ptr [rax+rax+00h]
0x140033359  test    eax, eax
0x14003335b  jz      short loc_140033361
0x14003335d  mov     bl, 1
0x14003335f  jmp     short loc_14003337C
0x140033361  mov     rax, cs:pDacl
0x140033368  test    rax, rax
0x14003336b  jz      short loc_14003337C
0x14003336d  mov     rcx, rax; Block
0x140033370  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140033375  mov     cs:pDacl, rbx
0x14003337c  mov     al, bl
0x14003337e  mov     rcx, [rsp+78h+var_10]
0x140033383  xor     rcx, rsp; StackCookie
0x140033386  call    __security_check_cookie
0x14003338b  mov     rbx, [rsp+78h+arg_0]
0x140033393  add     rsp, 70h
0x140033397  pop     rdi
0x140033398  retn
```
