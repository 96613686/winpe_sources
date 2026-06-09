# DsRolepCreateInterfaceSDs

- ea: `0x18001530c`
- end: `0x18001556b`
- name: `DsRolepCreateInterfaceSDs`
- size: `607`
- prototype: `char()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001fc28`

## callees

- `0x18001530c`
- `0x180015574`
- `0x1800157cc`
- `0x18002c012`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800153af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015429`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800154ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015506`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800153af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015429`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800154ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015506`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001547f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001547f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800153a2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001541a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800153a2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001541a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800153cc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001544a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800153cc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001544a`
- `api-ms-win-security-base-l1-1-0!AddAuditAccessAce` at `0x1800153fd`
- `api-ms-win-security-base-l1-1-0!AddAuditAccessAce` at `0x1800153fd`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180015383`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180015383`

## pseudocode

```c
char DsRolepCreateInterfaceSDs()
{
  char SecurityDescriptor; // bl
  SIZE_T v1; // rbx
  struct _ACL *v2; // rax
  SIZE_T v3; // rbx
  SIZE_T v4; // rdi
  struct _ACL *v5; // rax
  __int64 i; // rbx
  HLOCAL v7; // rax
  HLOCAL v8; // rax
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &DsRolepBuiltinAdminsSid) < 0 )
    goto LABEL_2;
  DsRolepAllowedSids[0] = (__int64)&DsRolepBuiltinAdminsSid;
  v1 = GetLengthSid(&WORLD_SID) + 20;
  v2 = (struct _ACL *)LocalAlloc(0, v1);
  DsRolepSacl = v2;
  if ( !v2 || !InitializeAcl(v2, v1, 2u) )
    goto LABEL_2;
  SecurityDescriptor = AddAuditAccessAce(DsRolepSacl, 2u, 1u, &WORLD_SID, 1, 1);
  if ( !SecurityDescriptor )
    goto LABEL_17;
  _mm_lfence();
  v3 = GetLengthSid(*(PSID *)DsRolepAllowedSids[0]) + 16;
  v4 = v3;
  v5 = (struct _ACL *)LocalAlloc(0, (unsigned int)v3);
  DsRolepPromoteAcl = v5;
  if ( !v5 || !InitializeAcl(v5, v3, 2u) )
    goto LABEL_2;
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    if ( !AddAccessAllowedAce(DsRolepPromoteAcl, 2u, 0xF0001u, *(PSID *)DsRolepAllowedSids[i]) )
      goto LABEL_2;
  }
  SecurityDescriptor = DsRolepMakeSecurityDescriptor(DsRolepPromoteSD);
  if ( !SecurityDescriptor )
    goto LABEL_17;
  v7 = LocalAlloc(0, v4);
  DsRolepDemoteAcl = v7;
  if ( !v7 )
    goto LABEL_2;
  memcpy_0(v7, DsRolepPromoteAcl, v4);
  SecurityDescriptor = DsRolepMakeSecurityDescriptor(DsRolepDemoteSD);
  if ( !SecurityDescriptor )
    goto LABEL_17;
  v8 = LocalAlloc(0, v4);
  DsRolepCallDsRoleInterfaceAcl = v8;
  if ( !v8 )
  {
LABEL_2:
    SecurityDescriptor = 0;
LABEL_17:
    DsRolepFreeInterfaceSDs();
    return SecurityDescriptor;
  }
  memcpy_0(v8, DsRolepPromoteAcl, v4);
  SecurityDescriptor = DsRolepMakeSecurityDescriptor(DsRolepCallDsRoleInterfaceSD);
  if ( !SecurityDescriptor )
    goto LABEL_17;
  return SecurityDescriptor;
}

```

## disassembly

```asm
0x18001530c  mov     [rsp+arg_0], rbx
0x180015311  push    rdi
0x180015312  sub     rsp, 70h
0x180015316  mov     rax, cs:__security_cookie
0x18001531d  xor     rax, rsp
0x180015320  mov     [rsp+78h+var_10], rax
0x180015325  lea     rbx, DsRolepBuiltinAdminsSid
0x18001532c  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], 0
0x180015334  mov     [rsp+78h+Sid], rbx; Sid
0x180015339  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x18001533e  mov     [rsp+78h+SubAuthority7], 0; SubAuthority7
0x180015346  mov     r9d, 220h; SubAuthority1
0x18001534c  mov     [rsp+78h+SubAuthority6], 0; SubAuthority6
0x180015354  mov     r8d, 20h ; ' '; SubAuthority0
0x18001535a  mov     [rsp+78h+SubAuthority5], 0; SubAuthority5
0x180015362  mov     dl, 2; SubAuthorityCount
0x180015364  mov     [rsp+78h+SubAuthority4], 0; SubAuthority4
0x18001536c  mov     [rsp+78h+SubAuthority3], 0; SubAuthority3
0x180015374  mov     [rsp+78h+SubAuthority2], 0; SubAuthority2
0x18001537c  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 500h
0x180015383  call    cs:__imp_RtlAllocateAndInitializeSid
0x180015389  test    eax, eax
0x18001538b  jns     short loc_180015394
0x18001538d  xor     bl, bl
0x18001538f  jmp     loc_180015549
0x180015394  lea     rcx, WORLD_SID; pSid
0x18001539b  mov     cs:DsRolepAllowedSids, rbx
0x1800153a2  call    cs:__imp_GetLengthSid
0x1800153a8  xor     ecx, ecx; uFlags
0x1800153aa  lea     ebx, [rax+14h]
0x1800153ad  mov     edx, ebx; uBytes
0x1800153af  call    cs:__imp_LocalAlloc
0x1800153b5  mov     cs:DsRolepSacl, rax
0x1800153bc  test    rax, rax
0x1800153bf  jz      short loc_18001538D
0x1800153c1  mov     r8d, 2; dwAclRevision
0x1800153c7  mov     edx, ebx; nAclLength
0x1800153c9  mov     rcx, rax; pAcl
0x1800153cc  call    cs:__imp_InitializeAcl
0x1800153d2  test    eax, eax
0x1800153d4  jz      short loc_18001538D
0x1800153d6  mov     rcx, cs:DsRolepSacl; pAcl
0x1800153dd  lea     r9, WORLD_SID; pSid
0x1800153e4  mov     edx, 2; dwAceRevision
0x1800153e9  mov     [rsp+78h+SubAuthority3], 1; bAuditFailure
0x1800153f1  mov     [rsp+78h+SubAuthority2], 1; bAuditSuccess
0x1800153f9  lea     r8d, [rdx-1]; dwAccessMask
0x1800153fd  call    cs:__imp_AddAuditAccessAce
0x180015403  mov     ebx, eax
0x180015405  test    al, al
0x180015407  jz      loc_180015549
0x18001540d  lfence
0x180015410  mov     rcx, cs:DsRolepAllowedSids
0x180015417  mov     rcx, [rcx]; pSid
0x18001541a  call    cs:__imp_GetLengthSid
0x180015420  xor     ecx, ecx; uFlags
0x180015422  lea     ebx, [rax+10h]
0x180015425  mov     edx, ebx; uBytes
0x180015427  mov     edi, ebx
0x180015429  call    cs:__imp_LocalAlloc
0x18001542f  mov     cs:DsRolepPromoteAcl, rax
0x180015436  test    rax, rax
0x180015439  jz      loc_18001538D
0x18001543f  mov     r8d, 2; dwAclRevision
0x180015445  mov     edx, ebx; nAclLength
0x180015447  mov     rcx, rax; pAcl
0x18001544a  call    cs:__imp_InitializeAcl
0x180015450  test    eax, eax
0x180015452  jz      loc_18001538D
0x180015458  xor     ebx, ebx
0x18001545a  cmp     ebx, 1
0x18001545d  jnb     short loc_180015491
0x18001545f  mov     rcx, cs:DsRolepPromoteAcl; pAcl
0x180015466  lea     rax, DsRolepAllowedSids
0x18001546d  mov     r9, [rax+rbx*8]
0x180015471  mov     edx, 2; dwAceRevision
0x180015476  mov     r8d, 0F0001h; AccessMask
0x18001547c  mov     r9, [r9]; pSid
0x18001547f  call    cs:__imp_AddAccessAllowedAce
0x180015485  test    eax, eax
0x180015487  jz      loc_18001538D
0x18001548d  inc     ebx
0x18001548f  jmp     short loc_18001545A
0x180015491  mov     r9, cs:DsRolepSacl
0x180015498  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x18001549f  mov     r8, cs:DsRolepPromoteAcl
0x1800154a6  call    DsRolepMakeSecurityDescriptor
0x1800154ab  mov     bl, al
0x1800154ad  test    al, al
0x1800154af  jz      loc_180015549
0x1800154b5  mov     rdx, rdi; uBytes
0x1800154b8  xor     ecx, ecx; uFlags
0x1800154ba  call    cs:__imp_LocalAlloc
0x1800154c0  mov     cs:DsRolepDemoteAcl, rax
0x1800154c7  mov     rbx, rax
0x1800154ca  test    rax, rax
0x1800154cd  jz      loc_18001538D
0x1800154d3  mov     rdx, cs:DsRolepPromoteAcl; Src
0x1800154da  mov     r8, rdi; Size
0x1800154dd  mov     rcx, rax; void *
0x1800154e0  call    memcpy_0
0x1800154e5  mov     r9, cs:DsRolepSacl
0x1800154ec  lea     rcx, DsRolepDemoteSD; pSecurityDescriptor
0x1800154f3  mov     r8, rbx
0x1800154f6  call    DsRolepMakeSecurityDescriptor
0x1800154fb  mov     bl, al
0x1800154fd  test    al, al
0x1800154ff  jz      short loc_180015549
0x180015501  mov     rdx, rdi; uBytes
0x180015504  xor     ecx, ecx; uFlags
0x180015506  call    cs:__imp_LocalAlloc
0x18001550c  mov     cs:DsRolepCallDsRoleInterfaceAcl, rax
0x180015513  mov     rbx, rax
0x180015516  test    rax, rax
0x180015519  jz      loc_18001538D
0x18001551f  mov     rdx, cs:DsRolepPromoteAcl; Src
0x180015526  mov     r8, rdi; Size
0x180015529  mov     rcx, rax; void *
0x18001552c  call    memcpy_0
0x180015531  xor     r9d, r9d
0x180015534  lea     rcx, DsRolepCallDsRoleInterfaceSD; pSecurityDescriptor
0x18001553b  mov     r8, rbx
0x18001553e  call    DsRolepMakeSecurityDescriptor
0x180015543  mov     bl, al
0x180015545  test    al, al
0x180015547  jnz     short loc_18001554E
0x180015549  call    DsRolepFreeInterfaceSDs
0x18001554e  mov     al, bl
0x180015550  mov     rcx, [rsp+78h+var_10]
0x180015555  xor     rcx, rsp; StackCookie
0x180015558  call    __security_check_cookie
0x18001555d  mov     rbx, [rsp+78h+arg_0]
0x180015565  add     rsp, 70h
0x180015569  pop     rdi
0x18001556a  retn
```
