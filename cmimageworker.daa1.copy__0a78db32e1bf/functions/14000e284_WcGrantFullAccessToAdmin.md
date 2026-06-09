# WcGrantFullAccessToAdmin

- ea: `0x14000e284`
- end: `0x14000e4b9`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000efd0`

## callees

- `0x1400020b0`
- `0x14000e284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e328`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000e472`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000e472`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000e318`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000e318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e487`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e3a2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e41e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e450`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e3a2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e41e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000e450`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14000e374`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14000e374`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14000e3e8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14000e3e8`

## pseudocode

```c
__int64 __fastcall WcGrantFullAccessToAdmin(
        LPWSTR pObjectName,
        PACL *ppDacl,
        PSECURITY_DESCRIPTOR *ppSecurityDescriptor)
{
  signed int NamedSecurityInfoW; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  struct _ACL *v9; // r8
  PSID psidOwner; // [rsp+60h] [rbp-29h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-21h] BYREF
  PSID ppsidOwner; // [rsp+70h] [rbp-19h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *ppSecurityDescriptor = 0;
  *ppDacl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  psidOwner = 0;
  NewAcl = 0;
  ppsidOwner = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           pObjectName,
                           SE_FILE_OBJECT,
                           5u,
                           &ppsidOwner,
                           0,
                           ppDacl,
                           0,
                           ppSecurityDescriptor);
    v7 = NamedSecurityInfoW;
    v8 = NamedSecurityInfoW <= 0;
    if ( !NamedSecurityInfoW )
    {
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
      v7 = NamedSecurityInfoW;
      v8 = NamedSecurityInfoW <= 0;
      if ( !NamedSecurityInfoW )
      {
        v9 = *ppDacl;
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
        pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
        *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
        pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
        pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
        NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, v9, &NewAcl);
        v7 = NamedSecurityInfoW;
        v8 = NamedSecurityInfoW <= 0;
        if ( !NamedSecurityInfoW )
        {
          NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
          v7 = NamedSecurityInfoW;
          v8 = NamedSecurityInfoW <= 0;
          if ( !NamedSecurityInfoW )
          {
            NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, ppsidOwner, 0, 0, 0);
            v7 = NamedSecurityInfoW;
            v8 = NamedSecurityInfoW <= 0;
            if ( !NamedSecurityInfoW )
            {
              v7 = 0;
              goto LABEL_11;
            }
          }
        }
      }
    }
  }
  else
  {
    NamedSecurityInfoW = GetLastError();
    v7 = NamedSecurityInfoW;
    v8 = NamedSecurityInfoW <= 0;
  }
  if ( !v8 )
    v7 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
LABEL_11:
  if ( psidOwner )
    FreeSid(psidOwner);
  if ( NewAcl )
    LocalFree(NewAcl);
  return v7;
}

```

## disassembly

```asm
0x14000e284  mov     [rsp-8+arg_18], rbx
0x14000e289  push    rbp
0x14000e28a  push    rsi
0x14000e28b  push    rdi
0x14000e28c  push    r14
0x14000e28e  push    r15
0x14000e290  lea     rbp, [rsp-37h]
0x14000e295  sub     rsp, 0C0h
0x14000e29c  mov     rax, cs:__security_cookie
0x14000e2a3  xor     rax, rsp
0x14000e2a6  mov     [rbp+57h+var_30], rax
0x14000e2aa  xor     r14d, r14d
0x14000e2ad  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14000e2b3  xorps   xmm0, xmm0
0x14000e2b6  mov     [r8], r14
0x14000e2b9  lea     rax, [rbp+57h+psidOwner]
0x14000e2bd  mov     [rdx], r14
0x14000e2c0  mov     [rsp+0E0h+pSid], rax; pSid
0x14000e2c5  mov     rbx, r8
0x14000e2c8  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x14000e2cd  lea     r8d, [r14+20h]; nSubAuthority0
0x14000e2d1  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x14000e2d6  mov     rsi, rdx
0x14000e2d9  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x14000e2de  mov     rdi, rcx
0x14000e2e1  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x14000e2e6  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000e2ea  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x14000e2ef  mov     r9d, 220h; nSubAuthority1
0x14000e2f5  mov     dl, 2; nSubAuthorityCount
0x14000e2f7  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x14000e2fc  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x14000e300  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x14000e304  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x14000e308  mov     [rbp+57h+psidOwner], r14
0x14000e30c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x14000e310  mov     [rbp+57h+NewAcl], r14
0x14000e314  mov     [rbp+57h+ppsidOwner], r14
0x14000e318  call    cs:__imp_AllocateAndInitializeSid
0x14000e31f  nop     dword ptr [rax+rax+00h]
0x14000e324  test    eax, eax
0x14000e326  jnz     short loc_14000E34C
0x14000e328  call    cs:__imp_GetLastError
0x14000e32f  nop     dword ptr [rax+rax+00h]
0x14000e334  mov     ebx, eax
0x14000e336  test    eax, eax
0x14000e338  jle     loc_14000E469
0x14000e33e  movzx   ebx, ax
0x14000e341  or      ebx, 80070000h
0x14000e347  jmp     loc_14000E469
0x14000e34c  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x14000e351  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x14000e355  mov     r8d, 5; SecurityInfo
0x14000e35b  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x14000e360  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x14000e365  mov     rcx, rdi; pObjectName
0x14000e368  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x14000e36d  lea     r15d, [r8-4]
0x14000e371  mov     edx, r15d; ObjectType
0x14000e374  call    cs:__imp_GetNamedSecurityInfoW
0x14000e37b  nop     dword ptr [rax+rax+00h]
0x14000e380  mov     ebx, eax
0x14000e382  test    eax, eax
0x14000e384  jnz     short loc_14000E338
0x14000e386  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x14000e38a  mov     r8d, r15d; SecurityInfo
0x14000e38d  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x14000e392  mov     edx, r15d; ObjectType
0x14000e395  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x14000e39a  mov     rcx, rdi; pObjectName
0x14000e39d  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x14000e3a2  call    cs:__imp_SetNamedSecurityInfoW
0x14000e3a9  nop     dword ptr [rax+rax+00h]
0x14000e3ae  mov     ebx, eax
0x14000e3b0  test    eax, eax
0x14000e3b2  jnz     short loc_14000E338
0x14000e3b4  mov     rax, [rbp+57h+psidOwner]
0x14000e3b8  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x14000e3bc  mov     r8, [rsi]; OldAcl
0x14000e3bf  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x14000e3c3  mov     ecx, r15d; cCountOfExplicitEntries
0x14000e3c6  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x14000e3ca  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x14000e3d1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x14000e3d9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x14000e3dd  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x14000e3e1  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x14000e3e8  call    cs:__imp_SetEntriesInAclW
0x14000e3ef  nop     dword ptr [rax+rax+00h]
0x14000e3f4  mov     ebx, eax
0x14000e3f6  test    eax, eax
0x14000e3f8  jnz     loc_14000E338
0x14000e3fe  mov     rax, [rbp+57h+NewAcl]
0x14000e402  lea     r8d, [r15+3]; SecurityInfo
0x14000e406  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x14000e40b  xor     r9d, r9d; psidOwner
0x14000e40e  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x14000e413  mov     edx, r15d; ObjectType
0x14000e416  mov     rcx, rdi; pObjectName
0x14000e419  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x14000e41e  call    cs:__imp_SetNamedSecurityInfoW
0x14000e425  nop     dword ptr [rax+rax+00h]
0x14000e42a  mov     ebx, eax
0x14000e42c  test    eax, eax
0x14000e42e  jnz     loc_14000E338
0x14000e434  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x14000e438  mov     r8d, r15d; SecurityInfo
0x14000e43b  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x14000e440  mov     edx, r15d; ObjectType
0x14000e443  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x14000e448  mov     rcx, rdi; pObjectName
0x14000e44b  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x14000e450  call    cs:__imp_SetNamedSecurityInfoW
0x14000e457  nop     dword ptr [rax+rax+00h]
0x14000e45c  mov     ebx, eax
0x14000e45e  test    eax, eax
0x14000e460  jnz     loc_14000E338
0x14000e466  mov     ebx, r14d
0x14000e469  mov     rcx, [rbp+57h+psidOwner]; pSid
0x14000e46d  test    rcx, rcx
0x14000e470  jz      short loc_14000E47E
0x14000e472  call    cs:__imp_FreeSid
0x14000e479  nop     dword ptr [rax+rax+00h]
0x14000e47e  mov     rcx, [rbp+57h+NewAcl]; hMem
0x14000e482  test    rcx, rcx
0x14000e485  jz      short loc_14000E493
0x14000e487  call    cs:__imp_LocalFree
0x14000e48e  nop     dword ptr [rax+rax+00h]
0x14000e493  mov     eax, ebx
0x14000e495  mov     rcx, [rbp+57h+var_30]
0x14000e499  xor     rcx, rsp; StackCookie
0x14000e49c  call    __security_check_cookie
0x14000e4a1  mov     rbx, [rsp+0E0h+arg_18]
0x14000e4a9  add     rsp, 0C0h
0x14000e4b0  pop     r15
0x14000e4b2  pop     r14
0x14000e4b4  pop     rdi
0x14000e4b5  pop     rsi
0x14000e4b6  pop     rbp
0x14000e4b7  retn
```
