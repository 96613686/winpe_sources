# InitializeSdFromProcessToken(void * *,_ACL * *)

- ea: `0x180022250`
- end: `0x18002249f`
- name: `?InitializeSdFromProcessToken@@YAJPEAPEAXPEAPEAU_ACL@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(PSID **, struct _ACL **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022314`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800222a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800222a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022295`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002246a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002246a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022479`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002233b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002233b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022458`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022430`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022430`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800223d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800223d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800223c1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800223c1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022357`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022357`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800222d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002230a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022380`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800223aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800222d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002230a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022380`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800223aa`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180022417`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180022417`

## pseudocode

```c
__int64 __fastcall InitializeSdFromProcessToken(PSID **a1, struct _ACL **a2)
{
  PSID *v4; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  __int64 v7; // rsi
  PSID *v8; // rax
  PSID *v9; // rbx
  PSID *v10; // rsi
  struct _ACL *v11; // rax
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+30h] [rbp-38h] BYREF
  DWORD TokenInformationLength; // [rsp+B0h] [rbp+48h] BYREF
  DWORD ReturnLength; // [rsp+B8h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+C0h] [rbp+58h] BYREF
  PACL NewAcl; // [rsp+C8h] [rbp+60h] BYREF

  *a1 = 0;
  *a2 = 0;
  TokenHandle = 0;
  v4 = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_2;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (LastError = GetLastError(), LastError == 122) )
  {
    if ( GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &ReturnLength)
      || (LastError = GetLastError(), LastError == 122) )
    {
      v7 = (TokenInformationLength + 7) & 0xFFFFFFF8;
      v8 = (PSID *)LocalAlloc(0x40u, (unsigned int)v7 + ReturnLength + 40);
      v4 = v8;
      if ( !v8 )
      {
        LastError = 8;
        goto LABEL_17;
      }
      if ( !InitializeSecurityDescriptor(v8, 1u) )
        goto LABEL_2;
      v9 = v4 + 5;
      if ( !GetTokenInformation(TokenHandle, TokenUser, v4 + 5, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_2;
      v10 = (PSID *)((char *)v9 + v7);
      if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v10, ReturnLength, &ReturnLength)
        || !SetSecurityDescriptorOwner(v4, *v9, 0)
        || !SetSecurityDescriptorGroup(v4, *v10, 0) )
      {
        goto LABEL_2;
      }
      pListOfExplicitEntries.grfAccessPermissions = 1;
      *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)qword_180033350;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      LastError = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
      if ( LastError )
        goto LABEL_17;
      if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
      {
LABEL_2:
        LastError = GetLastError();
        goto LABEL_17;
      }
      v11 = NewAcl;
      *a1 = v4;
      v4 = 0;
      *a2 = v11;
      NewAcl = 0;
    }
  }
LABEL_17:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v4 )
    LocalFree(v4);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180022250  push    rbp
0x180022252  push    rbx
0x180022253  push    rsi
0x180022254  push    rdi
0x180022255  push    r12
0x180022257  push    r13
0x180022259  push    r14
0x18002225b  push    r15
0x18002225d  mov     rbp, rsp
0x180022260  sub     rsp, 68h
0x180022264  xor     r12d, r12d
0x180022267  xorps   xmm0, xmm0
0x18002226a  mov     [rcx], r12
0x18002226d  mov     r14, rdx
0x180022270  mov     [rdx], r12
0x180022273  mov     r15, rcx
0x180022276  mov     [rbp+TokenHandle], r12
0x18002227a  mov     edi, r12d
0x18002227d  mov     [rbp+TokenInformationLength], r12d
0x180022281  mov     [rbp+arg_8], r12d
0x180022285  mov     [rbp+NewAcl], r12
0x180022289  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18002228d  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180022291  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180022295  call    cs:__imp_GetCurrentProcess
0x18002229b  mov     rcx, rax; ProcessHandle
0x18002229e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800222a2  lea     edx, [r12+8]; DesiredAccess
0x1800222a7  call    cs:__imp_OpenProcessToken
0x1800222ad  test    eax, eax
0x1800222af  jnz     short loc_1800222BE
0x1800222b1  call    cs:__imp_GetLastError
0x1800222b7  mov     ebx, eax
0x1800222b9  jmp     loc_18002244F
0x1800222be  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800222c2  lea     rax, [rbp+TokenInformationLength]
0x1800222c6  xor     r9d, r9d; TokenInformationLength
0x1800222c9  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800222ce  xor     r8d, r8d; TokenInformation
0x1800222d1  lea     r13d, [r9+1]
0x1800222d5  mov     edx, r13d; TokenInformationClass
0x1800222d8  call    cs:__imp_GetTokenInformation
0x1800222de  test    eax, eax
0x1800222e0  jnz     short loc_1800222F3
0x1800222e2  call    cs:__imp_GetLastError
0x1800222e8  mov     ebx, eax
0x1800222ea  cmp     eax, 7Ah ; 'z'
0x1800222ed  jnz     loc_18002244F
0x1800222f3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800222f7  lea     rax, [rbp+arg_8]
0x1800222fb  xor     r9d, r9d; TokenInformationLength
0x1800222fe  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180022303  xor     r8d, r8d; TokenInformation
0x180022306  lea     edx, [r9+5]; TokenInformationClass
0x18002230a  call    cs:__imp_GetTokenInformation
0x180022310  test    eax, eax
0x180022312  jnz     short loc_180022325
0x180022314  call    cs:__imp_GetLastError
0x18002231a  mov     ebx, eax
0x18002231c  cmp     eax, 7Ah ; 'z'
0x18002231f  jnz     loc_18002244F
0x180022325  mov     esi, [rbp+TokenInformationLength]
0x180022328  mov     ecx, 40h ; '@'; uFlags
0x18002232d  mov     edx, [rbp+arg_8]
0x180022330  add     esi, 7
0x180022333  add     edx, 28h ; '('
0x180022336  and     esi, 0FFFFFFF8h
0x180022339  add     edx, esi; uBytes
0x18002233b  call    cs:__imp_LocalAlloc
0x180022341  mov     rdi, rax
0x180022344  test    rax, rax
0x180022347  jnz     short loc_180022351
0x180022349  lea     ebx, [rax+8]
0x18002234c  jmp     loc_18002244F
0x180022351  mov     edx, r13d; dwRevision
0x180022354  mov     rcx, rdi; pSecurityDescriptor
0x180022357  call    cs:__imp_InitializeSecurityDescriptor
0x18002235d  test    eax, eax
0x18002235f  jz      loc_1800222B1
0x180022365  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180022369  lea     rax, [rbp+TokenInformationLength]
0x18002236d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022371  lea     rbx, [rdi+28h]
0x180022375  mov     r8, rbx; TokenInformation
0x180022378  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002237d  mov     edx, r13d; TokenInformationClass
0x180022380  call    cs:__imp_GetTokenInformation
0x180022386  test    eax, eax
0x180022388  jz      loc_1800222B1
0x18002238e  mov     r9d, [rbp+arg_8]; TokenInformationLength
0x180022392  lea     rax, [rbp+arg_8]
0x180022396  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002239a  add     rsi, rbx
0x18002239d  mov     r8, rsi; TokenInformation
0x1800223a0  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800223a5  mov     edx, 5; TokenInformationClass
0x1800223aa  call    cs:__imp_GetTokenInformation
0x1800223b0  test    eax, eax
0x1800223b2  jz      loc_1800222B1
0x1800223b8  mov     rdx, [rbx]; pOwner
0x1800223bb  xor     r8d, r8d; bOwnerDefaulted
0x1800223be  mov     rcx, rdi; pSecurityDescriptor
0x1800223c1  call    cs:__imp_SetSecurityDescriptorOwner
0x1800223c7  test    eax, eax
0x1800223c9  jz      loc_1800222B1
0x1800223cf  mov     rdx, [rsi]; pGroup
0x1800223d2  xor     r8d, r8d; bGroupDefaulted
0x1800223d5  mov     rcx, rdi; pSecurityDescriptor
0x1800223d8  call    cs:__imp_SetSecurityDescriptorGroup
0x1800223de  test    eax, eax
0x1800223e0  jz      loc_1800222B1
0x1800223e6  mov     eax, 2
0x1800223eb  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r13d
0x1800223ef  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], rax
0x1800223f3  lea     r9, [rbp+NewAcl]; NewAcl
0x1800223f7  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], eax
0x1800223fa  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800223fe  lea     rax, qword_180033350
0x180022405  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], r12
0x180022409  xor     r8d, r8d; OldAcl
0x18002240c  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180022410  mov     ecx, r13d; cCountOfExplicitEntries
0x180022413  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r12
0x180022417  call    cs:__imp_SetEntriesInAclW
0x18002241d  mov     ebx, eax
0x18002241f  test    eax, eax
0x180022421  jnz     short loc_18002244F
0x180022423  mov     r8, [rbp+NewAcl]; pDacl
0x180022427  xor     r9d, r9d; bDaclDefaulted
0x18002242a  mov     edx, r13d; bDaclPresent
0x18002242d  mov     rcx, rdi; pSecurityDescriptor
0x180022430  call    cs:__imp_SetSecurityDescriptorDacl
0x180022436  test    eax, eax
0x180022438  jz      loc_1800222B1
0x18002243e  mov     rax, [rbp+NewAcl]
0x180022442  mov     [r15], rdi
0x180022445  mov     rdi, r12
0x180022448  mov     [r14], rax
0x18002244b  mov     [rbp+NewAcl], r12
0x18002244f  mov     rcx, [rbp+TokenHandle]; hObject
0x180022453  test    rcx, rcx
0x180022456  jz      short loc_180022462
0x180022458  call    cs:__imp_CloseHandle
0x18002245e  mov     [rbp+TokenHandle], r12
0x180022462  test    rdi, rdi
0x180022465  jz      short loc_180022470
0x180022467  mov     rcx, rdi; hMem
0x18002246a  call    cs:__imp_LocalFree
0x180022470  mov     rcx, [rbp+NewAcl]; hMem
0x180022474  test    rcx, rcx
0x180022477  jz      short loc_18002247F
0x180022479  call    cs:__imp_LocalFree
0x18002247f  test    ebx, ebx
0x180022481  jle     short loc_18002248C
0x180022483  movzx   ebx, bx
0x180022486  or      ebx, 80070000h
0x18002248c  mov     eax, ebx
0x18002248e  add     rsp, 68h
0x180022492  pop     r15
0x180022494  pop     r14
0x180022496  pop     r13
0x180022498  pop     r12
0x18002249a  pop     rdi
0x18002249b  pop     rsi
0x18002249c  pop     rbx
0x18002249d  pop     rbp
0x18002249e  retn
```
