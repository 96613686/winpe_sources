# WcGrantFullAccessToAdmin

- ea: `0x1800aa048`
- end: `0x1800aa27d`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800aabf0`

## callees

- `0x1800053a0`
- `0x1800aa048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa0ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa0ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa24b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa24b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800aa236`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800aa236`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800aa0dc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800aa0dc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa166`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa1e2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa214`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa166`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa1e2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa214`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800aa138`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800aa138`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800aa1ac`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800aa1ac`

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
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+78h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

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
0x1800aa048  mov     [rsp-8+arg_18], rbx
0x1800aa04d  push    rbp
0x1800aa04e  push    rsi
0x1800aa04f  push    rdi
0x1800aa050  push    r14
0x1800aa052  push    r15
0x1800aa054  lea     rbp, [rsp-37h]
0x1800aa059  sub     rsp, 0C0h
0x1800aa060  mov     rax, cs:__security_cookie
0x1800aa067  xor     rax, rsp
0x1800aa06a  mov     [rbp+57h+var_30], rax
0x1800aa06e  xor     r14d, r14d
0x1800aa071  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800aa077  xorps   xmm0, xmm0
0x1800aa07a  mov     [r8], r14
0x1800aa07d  lea     rax, [rbp+57h+psidOwner]
0x1800aa081  mov     [rdx], r14
0x1800aa084  mov     [rsp+0E0h+pSid], rax; pSid
0x1800aa089  mov     rbx, r8
0x1800aa08c  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x1800aa091  lea     r8d, [r14+20h]; nSubAuthority0
0x1800aa095  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x1800aa09a  mov     rsi, rdx
0x1800aa09d  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x1800aa0a2  mov     rdi, rcx
0x1800aa0a5  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x1800aa0aa  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800aa0ae  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x1800aa0b3  mov     r9d, 220h; nSubAuthority1
0x1800aa0b9  mov     dl, 2; nSubAuthorityCount
0x1800aa0bb  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x1800aa0c0  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800aa0c4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800aa0c8  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800aa0cc  mov     [rbp+57h+psidOwner], r14
0x1800aa0d0  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800aa0d4  mov     [rbp+57h+NewAcl], r14
0x1800aa0d8  mov     [rbp+57h+ppsidOwner], r14
0x1800aa0dc  call    cs:__imp_AllocateAndInitializeSid
0x1800aa0e3  nop     dword ptr [rax+rax+00h]
0x1800aa0e8  test    eax, eax
0x1800aa0ea  jnz     short loc_1800AA110
0x1800aa0ec  call    cs:__imp_GetLastError
0x1800aa0f3  nop     dword ptr [rax+rax+00h]
0x1800aa0f8  mov     ebx, eax
0x1800aa0fa  test    eax, eax
0x1800aa0fc  jle     loc_1800AA22D
0x1800aa102  movzx   ebx, ax
0x1800aa105  or      ebx, 80070000h
0x1800aa10b  jmp     loc_1800AA22D
0x1800aa110  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x1800aa115  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x1800aa119  mov     r8d, 5; SecurityInfo
0x1800aa11f  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x1800aa124  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x1800aa129  mov     rcx, rdi; pObjectName
0x1800aa12c  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x1800aa131  lea     r15d, [r8-4]
0x1800aa135  mov     edx, r15d; ObjectType
0x1800aa138  call    cs:__imp_GetNamedSecurityInfoW
0x1800aa13f  nop     dword ptr [rax+rax+00h]
0x1800aa144  mov     ebx, eax
0x1800aa146  test    eax, eax
0x1800aa148  jnz     short loc_1800AA0FC
0x1800aa14a  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x1800aa14e  mov     r8d, r15d; SecurityInfo
0x1800aa151  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800aa156  mov     edx, r15d; ObjectType
0x1800aa159  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x1800aa15e  mov     rcx, rdi; pObjectName
0x1800aa161  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800aa166  call    cs:__imp_SetNamedSecurityInfoW
0x1800aa16d  nop     dword ptr [rax+rax+00h]
0x1800aa172  mov     ebx, eax
0x1800aa174  test    eax, eax
0x1800aa176  jnz     short loc_1800AA0FC
0x1800aa178  mov     rax, [rbp+57h+psidOwner]
0x1800aa17c  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800aa180  mov     r8, [rsi]; OldAcl
0x1800aa183  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800aa187  mov     ecx, r15d; cCountOfExplicitEntries
0x1800aa18a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800aa18e  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800aa195  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800aa19d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x1800aa1a1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x1800aa1a5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x1800aa1ac  call    cs:__imp_SetEntriesInAclW
0x1800aa1b3  nop     dword ptr [rax+rax+00h]
0x1800aa1b8  mov     ebx, eax
0x1800aa1ba  test    eax, eax
0x1800aa1bc  jnz     loc_1800AA0FC
0x1800aa1c2  mov     rax, [rbp+57h+NewAcl]
0x1800aa1c6  lea     r8d, [r15+3]; SecurityInfo
0x1800aa1ca  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800aa1cf  xor     r9d, r9d; psidOwner
0x1800aa1d2  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x1800aa1d7  mov     edx, r15d; ObjectType
0x1800aa1da  mov     rcx, rdi; pObjectName
0x1800aa1dd  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800aa1e2  call    cs:__imp_SetNamedSecurityInfoW
0x1800aa1e9  nop     dword ptr [rax+rax+00h]
0x1800aa1ee  mov     ebx, eax
0x1800aa1f0  test    eax, eax
0x1800aa1f2  jnz     loc_1800AA0FC
0x1800aa1f8  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x1800aa1fc  mov     r8d, r15d; SecurityInfo
0x1800aa1ff  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800aa204  mov     edx, r15d; ObjectType
0x1800aa207  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x1800aa20c  mov     rcx, rdi; pObjectName
0x1800aa20f  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800aa214  call    cs:__imp_SetNamedSecurityInfoW
0x1800aa21b  nop     dword ptr [rax+rax+00h]
0x1800aa220  mov     ebx, eax
0x1800aa222  test    eax, eax
0x1800aa224  jnz     loc_1800AA0FC
0x1800aa22a  mov     ebx, r14d
0x1800aa22d  mov     rcx, [rbp+57h+psidOwner]; pSid
0x1800aa231  test    rcx, rcx
0x1800aa234  jz      short loc_1800AA242
0x1800aa236  call    cs:__imp_FreeSid
0x1800aa23d  nop     dword ptr [rax+rax+00h]
0x1800aa242  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800aa246  test    rcx, rcx
0x1800aa249  jz      short loc_1800AA257
0x1800aa24b  call    cs:__imp_LocalFree
0x1800aa252  nop     dword ptr [rax+rax+00h]
0x1800aa257  mov     eax, ebx
0x1800aa259  mov     rcx, [rbp+57h+var_30]
0x1800aa25d  xor     rcx, rsp; StackCookie
0x1800aa260  call    __security_check_cookie
0x1800aa265  mov     rbx, [rsp+0E0h+arg_18]
0x1800aa26d  add     rsp, 0C0h
0x1800aa274  pop     r15
0x1800aa276  pop     r14
0x1800aa278  pop     rdi
0x1800aa279  pop     rsi
0x1800aa27a  pop     rbp
0x1800aa27b  retn
```
