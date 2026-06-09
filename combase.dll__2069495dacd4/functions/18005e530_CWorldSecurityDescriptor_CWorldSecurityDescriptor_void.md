# CWorldSecurityDescriptor::CWorldSecurityDescriptor(void)

- ea: `0x18005e530`
- end: `0x18005e84f`
- name: `??0CWorldSecurityDescriptor@@QEAA@XZ`
- size: `799`
- prototype: `void __fastcall(CWorldSecurityDescriptor *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005e4c8`

## callees

- `0x18005e530`
- `0x18005ede0`
- `0x1801999b0`

## import_xrefs

- `ntdll!RtlInitializeSidEx` at `0x18005e709`
- `ntdll!RtlInitializeSidEx` at `0x18005e709`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e584`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e584`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e71d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e72c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e742`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e754`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e71d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e72c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e742`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e754`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e818`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e818`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005e608`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005e608`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005e5aa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005e5aa`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005e63c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005e64d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005e63c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005e64d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e667`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e680`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e69d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e667`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e680`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005e69d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7d0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7e9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e802`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7d0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e7e9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005e802`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e760`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e76c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e77f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e792`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e760`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e76c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e77f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e792`
- `api-ms-win-security-base-l1-2-0!GetAppContainerAce` at `0x18005e630`
- `api-ms-win-security-base-l1-2-0!GetAppContainerAce` at `0x18005e630`

## pseudocode

```c
void __fastcall CWorldSecurityDescriptor::CWorldSecurityDescriptor(CWorldSecurityDescriptor *this)
{
  _ACL *acl; // r12
  int v3; // edi
  int v4; // esi
  DWORD LengthSid; // ebx
  DWORD v6; // ebx
  int bDaclPresent; // [rsp+70h] [rbp-90h] BYREF
  int bDaclDefaulted; // [rsp+74h] [rbp-8Ch] BYREF
  _ACL *pGlobalSecDacl; // [rsp+78h] [rbp-88h] BYREF
  void *appContainerAce; // [rsp+80h] [rbp-80h] BYREF
  _SID_IDENTIFIER_AUTHORITY SidApplicationAuthority; // [rsp+88h] [rbp-78h] BYREF
  _SID_IDENTIFIER_AUTHORITY SidWorldAuthority; // [rsp+90h] [rbp-70h] BYREF
  _SID_IDENTIFIER_AUTHORITY SidNTAuthority; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 abSidEveryone[12]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 abSidAnonymous[12]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 abSidAnyPackage[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 abSidComCapability[48]; // [rsp+D0h] [rbp-30h] BYREF

  *(_WORD *)&SidWorldAuthority.Value[4] = 256;
  *(_DWORD *)SidWorldAuthority.Value = 0;
  *(_DWORD *)SidNTAuthority.Value = 0;
  acl = 0;
  *(_WORD *)&SidNTAuthority.Value[4] = 1280;
  *(_DWORD *)SidApplicationAuthority.Value = 0;
  *(_WORD *)&SidApplicationAuthority.Value[4] = 3840;
  InitializeSecurityDescriptor(this, 1u);
  if ( !gC2Security.m_bProtectionMode || !InitializeAcl((PACL)this->_acl, 0x90u, 2u) )
    goto LABEL_29;
  acl = (_ACL *)this->_acl;
  if ( IsRunningInDCOMLAUNCH() )
  {
    v4 = 0;
  }
  else
  {
    if ( gSecDesc )
    {
      bDaclPresent = 0;
      pGlobalSecDacl = 0;
      bDaclDefaulted = 1;
      v3 = 0;
      if ( GetSecurityDescriptorDacl(gSecDesc, &bDaclPresent, &pGlobalSecDacl, &bDaclDefaulted)
        && bDaclPresent
        && pGlobalSecDacl )
      {
        appContainerAce = 0;
        v3 = GetAppContainerAce(pGlobalSecDacl, 0, &appContainerAce, 0);
      }
      v4 = v3;
      goto LABEL_10;
    }
    v4 = 1;
  }
  v3 = 1;
LABEL_10:
  if ( GetSidLengthRequired(1u) <= 0xC
    && GetSidLengthRequired(2u) <= 0x10
    && InitializeSid(abSidEveryone, &SidWorldAuthority, 1u)
    && InitializeSid(abSidAnonymous, &SidNTAuthority, 1u)
    && (!v3 || InitializeSid(abSidAnyPackage, &SidApplicationAuthority, 2u))
    && (!v4 || (int)RtlInitializeSidEx(abSidComCapability, &SidApplicationAuthority, 10) >= 0) )
  {
    *GetSidSubAuthority(abSidEveryone, 0) = 0;
    *GetSidSubAuthority(abSidAnonymous, 0) = 7;
    if ( v3 )
    {
      *GetSidSubAuthority(abSidAnyPackage, 0) = 2;
      *GetSidSubAuthority(abSidAnyPackage, 1u) = 1;
    }
    LengthSid = GetLengthSid(abSidAnonymous);
    v6 = GetLengthSid(abSidEveryone) + LengthSid + 32;
    if ( v3 )
      v6 += GetLengthSid(abSidAnyPackage) + 12;
    if ( v4 )
      v6 += GetLengthSid(abSidComCapability) + 12;
    if ( v6 <= 0x90 )
    {
      AddAccessAllowedAce((PACL)this->_acl, 2u, 0xEFF3FFFF, abSidEveryone);
      AddAccessAllowedAce((PACL)this->_acl, 2u, 0xEFF3FFFF, abSidAnonymous);
      if ( v3 )
        AddAccessAllowedAce((PACL)this->_acl, 2u, 0x80000000, abSidAnyPackage);
      if ( v4 )
        AddAccessAllowedAce((PACL)this->_acl, 2u, 0x80000000, abSidComCapability);
    }
  }
LABEL_29:
  SetSecurityDescriptorDacl(this, 1, acl, 0);
}

```

## disassembly

```asm
0x18005e530  push    rbp
0x18005e532  push    rbx
0x18005e533  push    rsi
0x18005e534  push    rdi
0x18005e535  push    r12
0x18005e537  push    r13
0x18005e539  push    r14
0x18005e53b  push    r15
0x18005e53d  lea     rbp, [rsp-18h]
0x18005e542  sub     rsp, 118h
0x18005e549  mov     rax, cs:__security_cookie
0x18005e550  xor     rax, rsp
0x18005e553  mov     [rbp+50h+var_50], rax
0x18005e557  xor     r13d, r13d
0x18005e55a  mov     word ptr [rbp+50h+SidWorldAuthority.Value+4], 100h
0x18005e560  mov     r15, this
0x18005e563  mov     dword ptr [rbp+50h+SidWorldAuthority.Value], r13d
0x18005e567  mov     dword ptr [rbp+50h+SidNTAuthority.Value], r13d
0x18005e56b  mov     r12d, r13d
0x18005e56e  mov     word ptr [rbp+50h+SidNTAuthority.Value+4], 500h
0x18005e574  lea     ebx, [r13+1]
0x18005e578  mov     dword ptr [rbp+50h+SidApplicationAuthority.Value], r13d
0x18005e57c  mov     edx, ebx; dwRevision
0x18005e57e  mov     word ptr [rbp+50h+SidApplicationAuthority.Value+4], 0F00h
0x18005e584  call    cs:__imp_InitializeSecurityDescriptor
0x18005e58a  mov     ecx, eax
0x18005e58c  lea     r14, [r15+28h]
0x18005e590  mov     eax, cs:?gC2Security@@3VC2Security@@A.m_bProtectionMode; C2Security gC2Security ...
0x18005e596  test    eax, eax
0x18005e598  jz      loc_18005E80D
0x18005e59e  mov     edx, 90h; nAclLength
0x18005e5a3  lea     r8d, [r13+2]; dwAclRevision
0x18005e5a7  mov     this, r14; pAcl
0x18005e5aa  call    cs:__imp_InitializeAcl
0x18005e5b0  mov     ecx, eax
0x18005e5b2  mov     eax, cs:?gC2Security@@3VC2Security@@A.m_bProtectionMode; C2Security gC2Security ...
0x18005e5b8  test    eax, eax
0x18005e5ba  jz      loc_18005E80D
0x18005e5c0  test    ecx, ecx
0x18005e5c2  jz      loc_18005E80D
0x18005e5c8  mov     r12, r14
0x18005e5cb  call    ?IsRunningInDCOMLAUNCH@@YAHXZ; IsRunningInDCOMLAUNCH(void)
0x18005e5d0  test    eax, eax
0x18005e5d2  jnz     loc_18005E84A
0x18005e5d8  mov     this, cs:?gSecDesc@@3PEAU_SECURITY_DESCRIPTOR@@EA; pSecurityDescriptor
0x18005e5df  test    this, this
0x18005e5e2  jz      loc_18005E841
0x18005e5e8  lea     r9, [rsp+150h+bDaclDefaulted]; lpbDaclDefaulted
0x18005e5ed  mov     [rsp+150h+bDaclPresent], r13d
0x18005e5f2  lea     r8, [rsp+150h+pGlobalSecDacl]; pDacl
0x18005e5f7  mov     [rsp+150h+pGlobalSecDacl], r13
0x18005e5fc  lea     rdx, [rsp+150h+bDaclPresent]; lpbDaclPresent
0x18005e601  mov     [rsp+150h+bDaclDefaulted], ebx
0x18005e605  mov     edi, r13d
0x18005e608  call    cs:__imp_GetSecurityDescriptorDacl
0x18005e60e  test    eax, eax
0x18005e610  jz      short loc_18005E638
0x18005e612  cmp     [rsp+150h+bDaclPresent], r13d
0x18005e617  jz      short loc_18005E638
0x18005e619  mov     this, [rsp+150h+pGlobalSecDacl]
0x18005e61e  test    this, this
0x18005e621  jz      short loc_18005E638
0x18005e623  xor     r9d, r9d
0x18005e626  mov     [rbp+50h+appContainerAce], r13
0x18005e62a  lea     r8, [rbp+50h+appContainerAce]
0x18005e62e  xor     edx, edx
0x18005e630  call    cs:__imp_GetAppContainerAce
0x18005e636  mov     edi, eax
0x18005e638  mov     esi, edi
0x18005e63a  mov     cl, bl; nSubAuthorityCount
0x18005e63c  call    cs:__imp_GetSidLengthRequired
0x18005e642  cmp     eax, 0Ch
0x18005e645  ja      loc_18005E80D
0x18005e64b  mov     cl, 2; nSubAuthorityCount
0x18005e64d  call    cs:__imp_GetSidLengthRequired
0x18005e653  cmp     eax, 10h
0x18005e656  ja      loc_18005E80D
0x18005e65c  mov     r8b, bl; nSubAuthorityCount
0x18005e65f  lea     rdx, [rbp+50h+SidWorldAuthority]; pIdentifierAuthority
0x18005e663  lea     this, [rbp+50h+abSidEveryone]; Sid
0x18005e667  call    cs:__imp_InitializeSid
0x18005e66d  test    eax, eax
0x18005e66f  jz      loc_18005E80D
0x18005e675  mov     r8b, bl; nSubAuthorityCount
0x18005e678  lea     rdx, [rbp+50h+SidNTAuthority]; pIdentifierAuthority
0x18005e67c  lea     this, [rbp+50h+abSidAnonymous]; Sid
0x18005e680  call    cs:__imp_InitializeSid
0x18005e686  test    eax, eax
0x18005e688  jz      loc_18005E80D
0x18005e68e  test    edi, edi
0x18005e690  jz      short loc_18005E6AB
0x18005e692  mov     r8b, 2; nSubAuthorityCount
0x18005e695  lea     rdx, [rbp+50h+SidApplicationAuthority]; pIdentifierAuthority
0x18005e699  lea     this, [rbp+50h+abSidAnyPackage]; Sid
0x18005e69d  call    cs:__imp_InitializeSid
0x18005e6a3  test    eax, eax
0x18005e6a5  jz      loc_18005E80D
0x18005e6ab  test    esi, esi
0x18005e6ad  jz      short loc_18005E717
0x18005e6af  mov     [rsp+150h+var_F0], 3B1B1798h
0x18005e6b7  lea     rdx, [rbp+50h+SidApplicationAuthority]
0x18005e6bb  mov     [rsp+150h+var_F8], 0D81FA686h
0x18005e6c3  lea     this, [rbp+50h+abSidComCapability]
0x18005e6c7  mov     [rsp+150h+var_100], 92435208h
0x18005e6cf  mov     r9d, 3
0x18005e6d5  mov     [rsp+150h+var_108], 681A32E7h
0x18005e6dd  mov     [rsp+150h+var_110], 6CB6D59Dh
0x18005e6e5  mov     [rsp+150h+var_118], 0FF77B663h
0x18005e6ed  mov     [rsp+150h+var_120], 3418BB9Ah
0x18005e6f5  lea     r8d, [r9+7]
0x18005e6f9  mov     [rsp+150h+var_128], 8F6027A1h
0x18005e701  mov     [rsp+150h+var_130], 400h
0x18005e709  call    cs:__imp_RtlInitializeSidEx
0x18005e70f  test    eax, eax
0x18005e711  js      loc_18005E80D
0x18005e717  xor     edx, edx; nSubAuthority
0x18005e719  lea     this, [rbp+50h+abSidEveryone]; pSid
0x18005e71d  call    cs:__imp_GetSidSubAuthority
0x18005e723  xor     edx, edx; nSubAuthority
0x18005e725  lea     this, [rbp+50h+abSidAnonymous]; pSid
0x18005e729  mov     [rax], r13d
0x18005e72c  call    cs:__imp_GetSidSubAuthority
0x18005e732  mov     dword ptr [rax], 7
0x18005e738  test    edi, edi
0x18005e73a  jz      short loc_18005E75C
0x18005e73c  xor     edx, edx; nSubAuthority
0x18005e73e  lea     this, [rbp+50h+abSidAnyPackage]; pSid
0x18005e742  call    cs:__imp_GetSidSubAuthority
0x18005e748  mov     edx, ebx; nSubAuthority
0x18005e74a  lea     this, [rbp+50h+abSidAnyPackage]; pSid
0x18005e74e  mov     dword ptr [rax], 2
0x18005e754  call    cs:__imp_GetSidSubAuthority
0x18005e75a  mov     [rax], ebx
0x18005e75c  lea     this, [rbp+50h+abSidAnonymous]; pSid
0x18005e760  call    cs:__imp_GetLengthSid
0x18005e766  lea     this, [rbp+50h+abSidEveryone]; pSid
0x18005e76a  mov     ebx, eax
0x18005e76c  call    cs:__imp_GetLengthSid
0x18005e772  add     ebx, 20h ; ' '
0x18005e775  add     ebx, eax
0x18005e777  test    edi, edi
0x18005e779  jz      short loc_18005E78A
0x18005e77b  lea     this, [rbp+50h+abSidAnyPackage]; pSid
0x18005e77f  call    cs:__imp_GetLengthSid
0x18005e785  add     ebx, 0Ch
0x18005e788  add     ebx, eax
0x18005e78a  test    esi, esi
0x18005e78c  jz      short loc_18005E79D
0x18005e78e  lea     this, [rbp+50h+abSidComCapability]; pSid
0x18005e792  call    cs:__imp_GetLengthSid
0x18005e798  add     eax, 0Ch
0x18005e79b  add     ebx, eax
0x18005e79d  cmp     ebx, 90h
0x18005e7a3  ja      short loc_18005E808
0x18005e7a5  mov     ebx, 0EFF3FFFFh
0x18005e7aa  lea     r9, [rbp+50h+abSidEveryone]; pSid
0x18005e7ae  mov     r8d, ebx; AccessMask
0x18005e7b1  mov     edx, 2; dwAceRevision
0x18005e7b6  mov     this, r14; pAcl
0x18005e7b9  call    cs:__imp_AddAccessAllowedAce
0x18005e7bf  mov     r8d, ebx; AccessMask
0x18005e7c2  lea     r9, [rbp+50h+abSidAnonymous]; pSid
0x18005e7c6  mov     ebx, 2
0x18005e7cb  mov     this, r14; pAcl
0x18005e7ce  mov     edx, ebx; dwAceRevision
0x18005e7d0  call    cs:__imp_AddAccessAllowedAce
0x18005e7d6  test    edi, edi
0x18005e7d8  jz      short loc_18005E7EF
0x18005e7da  lea     r9, [rbp+50h+abSidAnyPackage]; pSid
0x18005e7de  mov     r8d, 80000000h; AccessMask
0x18005e7e4  mov     edx, ebx; dwAceRevision
0x18005e7e6  mov     this, r14; pAcl
0x18005e7e9  call    cs:__imp_AddAccessAllowedAce
0x18005e7ef  test    esi, esi
0x18005e7f1  jz      short loc_18005E808
0x18005e7f3  lea     r9, [rbp+50h+abSidComCapability]; pSid
0x18005e7f7  mov     r8d, 80000000h; AccessMask
0x18005e7fd  mov     edx, ebx; dwAceRevision
0x18005e7ff  mov     this, r14; pAcl
0x18005e802  call    cs:__imp_AddAccessAllowedAce
0x18005e808  mov     ebx, 1
0x18005e80d  xor     r9d, r9d; bDaclDefaulted
0x18005e810  mov     r8, r12; pDacl
0x18005e813  mov     edx, ebx; bDaclPresent
0x18005e815  mov     this, r15; pSecurityDescriptor
0x18005e818  call    cs:__imp_SetSecurityDescriptorDacl
0x18005e81e  mov     rax, r15
0x18005e821  mov     this, [rbp+50h+var_50]
0x18005e825  xor     this, rsp; StackCookie
0x18005e828  call    __security_check_cookie
0x18005e82d  add     rsp, 118h
0x18005e834  pop     r15
0x18005e836  pop     r14
0x18005e838  pop     r13
0x18005e83a  pop     r12
0x18005e83c  pop     rdi
0x18005e83d  pop     rsi
0x18005e83e  pop     rbx
0x18005e83f  pop     rbp
0x18005e840  retn
0x18005e841  mov     esi, ebx
0x18005e843  mov     edi, ebx
0x18005e845  jmp     loc_18005E63A
0x18005e84a  mov     esi, r13d
0x18005e84d  jmp     short loc_18005E843
```
