# WcGrantFullAccessToAdmin

- ea: `0x1800ab688`
- end: `0x1800ab8bd`
- name: `WcGrantFullAccessToAdmin`
- size: `565`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PACL *ppDacl, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800ac1f0`

## callees

- `0x180004f70`
- `0x1800ab688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab72c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab72c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab88b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab88b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ab876`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ab876`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ab71c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ab71c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800ab7ec`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800ab7ec`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab7a6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab822`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab854`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab7a6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab822`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ab854`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800ab778`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800ab778`

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
0x1800ab688  mov     [rsp-8+arg_18], rbx
0x1800ab68d  push    rbp
0x1800ab68e  push    rsi
0x1800ab68f  push    rdi
0x1800ab690  push    r14
0x1800ab692  push    r15
0x1800ab694  lea     rbp, [rsp-37h]
0x1800ab699  sub     rsp, 0C0h
0x1800ab6a0  mov     rax, cs:__security_cookie
0x1800ab6a7  xor     rax, rsp
0x1800ab6aa  mov     [rbp+57h+var_30], rax
0x1800ab6ae  xor     r14d, r14d
0x1800ab6b1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800ab6b7  xorps   xmm0, xmm0
0x1800ab6ba  mov     [r8], r14
0x1800ab6bd  lea     rax, [rbp+57h+psidOwner]
0x1800ab6c1  mov     [rdx], r14
0x1800ab6c4  mov     [rsp+0E0h+pSid], rax; pSid
0x1800ab6c9  mov     rbx, r8
0x1800ab6cc  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x1800ab6d1  lea     r8d, [r14+20h]; nSubAuthority0
0x1800ab6d5  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x1800ab6da  mov     rsi, rdx
0x1800ab6dd  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x1800ab6e2  mov     rdi, rcx
0x1800ab6e5  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x1800ab6ea  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800ab6ee  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x1800ab6f3  mov     r9d, 220h; nSubAuthority1
0x1800ab6f9  mov     dl, 2; nSubAuthorityCount
0x1800ab6fb  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x1800ab700  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800ab704  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800ab708  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800ab70c  mov     [rbp+57h+psidOwner], r14
0x1800ab710  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800ab714  mov     [rbp+57h+NewAcl], r14
0x1800ab718  mov     [rbp+57h+ppsidOwner], r14
0x1800ab71c  call    cs:__imp_AllocateAndInitializeSid
0x1800ab723  nop     dword ptr [rax+rax+00h]
0x1800ab728  test    eax, eax
0x1800ab72a  jnz     short loc_1800AB750
0x1800ab72c  call    cs:__imp_GetLastError
0x1800ab733  nop     dword ptr [rax+rax+00h]
0x1800ab738  mov     ebx, eax
0x1800ab73a  test    eax, eax
0x1800ab73c  jle     loc_1800AB86D
0x1800ab742  movzx   ebx, ax
0x1800ab745  or      ebx, 80070000h
0x1800ab74b  jmp     loc_1800AB86D
0x1800ab750  mov     qword ptr [rsp+0E0h+nSubAuthority5], rbx; ppSecurityDescriptor
0x1800ab755  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x1800ab759  mov     r8d, 5; SecurityInfo
0x1800ab75f  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; ppSacl
0x1800ab764  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi; ppDacl
0x1800ab769  mov     rcx, rdi; pObjectName
0x1800ab76c  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; ppsidGroup
0x1800ab771  lea     r15d, [r8-4]
0x1800ab775  mov     edx, r15d; ObjectType
0x1800ab778  call    cs:__imp_GetNamedSecurityInfoW
0x1800ab77f  nop     dword ptr [rax+rax+00h]
0x1800ab784  mov     ebx, eax
0x1800ab786  test    eax, eax
0x1800ab788  jnz     short loc_1800AB73C
0x1800ab78a  mov     r9, [rbp+57h+psidOwner]; psidOwner
0x1800ab78e  mov     r8d, r15d; SecurityInfo
0x1800ab791  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800ab796  mov     edx, r15d; ObjectType
0x1800ab799  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x1800ab79e  mov     rcx, rdi; pObjectName
0x1800ab7a1  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800ab7a6  call    cs:__imp_SetNamedSecurityInfoW
0x1800ab7ad  nop     dword ptr [rax+rax+00h]
0x1800ab7b2  mov     ebx, eax
0x1800ab7b4  test    eax, eax
0x1800ab7b6  jnz     short loc_1800AB73C
0x1800ab7b8  mov     rax, [rbp+57h+psidOwner]
0x1800ab7bc  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800ab7c0  mov     r8, [rsi]; OldAcl
0x1800ab7c3  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800ab7c7  mov     ecx, r15d; cCountOfExplicitEntries
0x1800ab7ca  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800ab7ce  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800ab7d5  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800ab7dd  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x1800ab7e1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x1800ab7e5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x1800ab7ec  call    cs:__imp_SetEntriesInAclW
0x1800ab7f3  nop     dword ptr [rax+rax+00h]
0x1800ab7f8  mov     ebx, eax
0x1800ab7fa  test    eax, eax
0x1800ab7fc  jnz     loc_1800AB73C
0x1800ab802  mov     rax, [rbp+57h+NewAcl]
0x1800ab806  lea     r8d, [r15+3]; SecurityInfo
0x1800ab80a  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800ab80f  xor     r9d, r9d; psidOwner
0x1800ab812  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x1800ab817  mov     edx, r15d; ObjectType
0x1800ab81a  mov     rcx, rdi; pObjectName
0x1800ab81d  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800ab822  call    cs:__imp_SetNamedSecurityInfoW
0x1800ab829  nop     dword ptr [rax+rax+00h]
0x1800ab82e  mov     ebx, eax
0x1800ab830  test    eax, eax
0x1800ab832  jnz     loc_1800AB73C
0x1800ab838  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x1800ab83c  mov     r8d, r15d; SecurityInfo
0x1800ab83f  mov     qword ptr [rsp+0E0h+nSubAuthority4], r14; pSacl
0x1800ab844  mov     edx, r15d; ObjectType
0x1800ab847  mov     qword ptr [rsp+0E0h+nSubAuthority3], r14; pDacl
0x1800ab84c  mov     rcx, rdi; pObjectName
0x1800ab84f  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; psidGroup
0x1800ab854  call    cs:__imp_SetNamedSecurityInfoW
0x1800ab85b  nop     dword ptr [rax+rax+00h]
0x1800ab860  mov     ebx, eax
0x1800ab862  test    eax, eax
0x1800ab864  jnz     loc_1800AB73C
0x1800ab86a  mov     ebx, r14d
0x1800ab86d  mov     rcx, [rbp+57h+psidOwner]; pSid
0x1800ab871  test    rcx, rcx
0x1800ab874  jz      short loc_1800AB882
0x1800ab876  call    cs:__imp_FreeSid
0x1800ab87d  nop     dword ptr [rax+rax+00h]
0x1800ab882  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800ab886  test    rcx, rcx
0x1800ab889  jz      short loc_1800AB897
0x1800ab88b  call    cs:__imp_LocalFree
0x1800ab892  nop     dword ptr [rax+rax+00h]
0x1800ab897  mov     eax, ebx
0x1800ab899  mov     rcx, [rbp+57h+var_30]
0x1800ab89d  xor     rcx, rsp; StackCookie
0x1800ab8a0  call    __security_check_cookie
0x1800ab8a5  mov     rbx, [rsp+0E0h+arg_18]
0x1800ab8ad  add     rsp, 0C0h
0x1800ab8b4  pop     r15
0x1800ab8b6  pop     r14
0x1800ab8b8  pop     rdi
0x1800ab8b9  pop     rsi
0x1800ab8ba  pop     rbp
0x1800ab8bb  retn
```
