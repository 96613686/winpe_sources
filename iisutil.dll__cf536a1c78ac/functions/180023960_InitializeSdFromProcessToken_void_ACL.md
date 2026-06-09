# InitializeSdFromProcessToken(void * *,_ACL * *)

- ea: `0x180023960`
- end: `0x180023c1c`
- name: `?InitializeSdFromProcessToken@@YAJPEAPEAXPEAPEAU_ACL@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(PSID **, struct _ACL **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180023960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800239bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800239bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800239a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800239a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023bc2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023b94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023b94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023b30`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023b30`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023b13`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023b13`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023a97`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023a97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800239fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023a38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023ac6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023af6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800239fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023a38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023ac6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023af6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180023b75`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180023b75`

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
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)qword_180035350;
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
0x180023960  push    rbp
0x180023962  push    rbx
0x180023963  push    rsi
0x180023964  push    rdi
0x180023965  push    r12
0x180023967  push    r13
0x180023969  push    r14
0x18002396b  push    r15
0x18002396d  mov     rbp, rsp
0x180023970  sub     rsp, 68h
0x180023974  xor     r12d, r12d
0x180023977  xorps   xmm0, xmm0
0x18002397a  mov     [rcx], r12
0x18002397d  mov     r14, rdx
0x180023980  mov     [rdx], r12
0x180023983  mov     r15, rcx
0x180023986  mov     [rbp+TokenHandle], r12
0x18002398a  mov     edi, r12d
0x18002398d  mov     [rbp+TokenInformationLength], r12d
0x180023991  mov     [rbp+arg_8], r12d
0x180023995  mov     [rbp+NewAcl], r12
0x180023999  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18002399d  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800239a1  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800239a5  call    cs:__imp_GetCurrentProcess
0x1800239ac  nop     dword ptr [rax+rax+00h]
0x1800239b1  mov     rcx, rax; ProcessHandle
0x1800239b4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800239b8  lea     edx, [r12+8]; DesiredAccess
0x1800239bd  call    cs:__imp_OpenProcessToken
0x1800239c4  nop     dword ptr [rax+rax+00h]
0x1800239c9  test    eax, eax
0x1800239cb  jnz     short loc_1800239E0
0x1800239cd  call    cs:__imp_GetLastError
0x1800239d4  nop     dword ptr [rax+rax+00h]
0x1800239d9  mov     ebx, eax
0x1800239db  jmp     loc_180023BB9
0x1800239e0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800239e4  lea     rax, [rbp+TokenInformationLength]
0x1800239e8  xor     r9d, r9d; TokenInformationLength
0x1800239eb  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800239f0  xor     r8d, r8d; TokenInformation
0x1800239f3  lea     r13d, [r9+1]
0x1800239f7  mov     edx, r13d; TokenInformationClass
0x1800239fa  call    cs:__imp_GetTokenInformation
0x180023a01  nop     dword ptr [rax+rax+00h]
0x180023a06  test    eax, eax
0x180023a08  jnz     short loc_180023A21
0x180023a0a  call    cs:__imp_GetLastError
0x180023a11  nop     dword ptr [rax+rax+00h]
0x180023a16  mov     ebx, eax
0x180023a18  cmp     eax, 7Ah ; 'z'
0x180023a1b  jnz     loc_180023BB9
0x180023a21  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023a25  lea     rax, [rbp+arg_8]
0x180023a29  xor     r9d, r9d; TokenInformationLength
0x180023a2c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180023a31  xor     r8d, r8d; TokenInformation
0x180023a34  lea     edx, [r9+5]; TokenInformationClass
0x180023a38  call    cs:__imp_GetTokenInformation
0x180023a3f  nop     dword ptr [rax+rax+00h]
0x180023a44  test    eax, eax
0x180023a46  jnz     short loc_180023A5F
0x180023a48  call    cs:__imp_GetLastError
0x180023a4f  nop     dword ptr [rax+rax+00h]
0x180023a54  mov     ebx, eax
0x180023a56  cmp     eax, 7Ah ; 'z'
0x180023a59  jnz     loc_180023BB9
0x180023a5f  mov     esi, [rbp+TokenInformationLength]
0x180023a62  mov     ecx, 40h ; '@'; uFlags
0x180023a67  mov     edx, [rbp+arg_8]
0x180023a6a  add     esi, 7
0x180023a6d  add     edx, 28h ; '('
0x180023a70  and     esi, 0FFFFFFF8h
0x180023a73  add     edx, esi; uBytes
0x180023a75  call    cs:__imp_LocalAlloc
0x180023a7c  nop     dword ptr [rax+rax+00h]
0x180023a81  mov     rdi, rax
0x180023a84  test    rax, rax
0x180023a87  jnz     short loc_180023A91
0x180023a89  lea     ebx, [rax+8]
0x180023a8c  jmp     loc_180023BB9
0x180023a91  mov     edx, r13d; dwRevision
0x180023a94  mov     rcx, rdi; pSecurityDescriptor
0x180023a97  call    cs:__imp_InitializeSecurityDescriptor
0x180023a9e  nop     dword ptr [rax+rax+00h]
0x180023aa3  test    eax, eax
0x180023aa5  jz      loc_1800239CD
0x180023aab  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180023aaf  lea     rax, [rbp+TokenInformationLength]
0x180023ab3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023ab7  lea     rbx, [rdi+28h]
0x180023abb  mov     r8, rbx; TokenInformation
0x180023abe  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180023ac3  mov     edx, r13d; TokenInformationClass
0x180023ac6  call    cs:__imp_GetTokenInformation
0x180023acd  nop     dword ptr [rax+rax+00h]
0x180023ad2  test    eax, eax
0x180023ad4  jz      loc_1800239CD
0x180023ada  mov     r9d, [rbp+arg_8]; TokenInformationLength
0x180023ade  lea     rax, [rbp+arg_8]
0x180023ae2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023ae6  add     rsi, rbx
0x180023ae9  mov     r8, rsi; TokenInformation
0x180023aec  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180023af1  mov     edx, 5; TokenInformationClass
0x180023af6  call    cs:__imp_GetTokenInformation
0x180023afd  nop     dword ptr [rax+rax+00h]
0x180023b02  test    eax, eax
0x180023b04  jz      loc_1800239CD
0x180023b0a  mov     rdx, [rbx]; pOwner
0x180023b0d  xor     r8d, r8d; bOwnerDefaulted
0x180023b10  mov     rcx, rdi; pSecurityDescriptor
0x180023b13  call    cs:__imp_SetSecurityDescriptorOwner
0x180023b1a  nop     dword ptr [rax+rax+00h]
0x180023b1f  test    eax, eax
0x180023b21  jz      loc_1800239CD
0x180023b27  mov     rdx, [rsi]; pGroup
0x180023b2a  xor     r8d, r8d; bGroupDefaulted
0x180023b2d  mov     rcx, rdi; pSecurityDescriptor
0x180023b30  call    cs:__imp_SetSecurityDescriptorGroup
0x180023b37  nop     dword ptr [rax+rax+00h]
0x180023b3c  test    eax, eax
0x180023b3e  jz      loc_1800239CD
0x180023b44  mov     eax, 2
0x180023b49  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r13d
0x180023b4d  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], rax
0x180023b51  lea     r9, [rbp+NewAcl]; NewAcl
0x180023b55  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], eax
0x180023b58  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180023b5c  lea     rax, qword_180035350
0x180023b63  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], r12
0x180023b67  xor     r8d, r8d; OldAcl
0x180023b6a  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180023b6e  mov     ecx, r13d; cCountOfExplicitEntries
0x180023b71  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r12
0x180023b75  call    cs:__imp_SetEntriesInAclW
0x180023b7c  nop     dword ptr [rax+rax+00h]
0x180023b81  mov     ebx, eax
0x180023b83  test    eax, eax
0x180023b85  jnz     short loc_180023BB9
0x180023b87  mov     r8, [rbp+NewAcl]; pDacl
0x180023b8b  xor     r9d, r9d; bDaclDefaulted
0x180023b8e  mov     edx, r13d; bDaclPresent
0x180023b91  mov     rcx, rdi; pSecurityDescriptor
0x180023b94  call    cs:__imp_SetSecurityDescriptorDacl
0x180023b9b  nop     dword ptr [rax+rax+00h]
0x180023ba0  test    eax, eax
0x180023ba2  jz      loc_1800239CD
0x180023ba8  mov     rax, [rbp+NewAcl]
0x180023bac  mov     [r15], rdi
0x180023baf  mov     rdi, r12
0x180023bb2  mov     [r14], rax
0x180023bb5  mov     [rbp+NewAcl], r12
0x180023bb9  mov     rcx, [rbp+TokenHandle]; hObject
0x180023bbd  test    rcx, rcx
0x180023bc0  jz      short loc_180023BD2
0x180023bc2  call    cs:__imp_CloseHandle
0x180023bc9  nop     dword ptr [rax+rax+00h]
0x180023bce  mov     [rbp+TokenHandle], r12
0x180023bd2  test    rdi, rdi
0x180023bd5  jz      short loc_180023BE6
0x180023bd7  mov     rcx, rdi; hMem
0x180023bda  call    cs:__imp_LocalFree
0x180023be1  nop     dword ptr [rax+rax+00h]
0x180023be6  mov     rcx, [rbp+NewAcl]; hMem
0x180023bea  test    rcx, rcx
0x180023bed  jz      short loc_180023BFB
0x180023bef  call    cs:__imp_LocalFree
0x180023bf6  nop     dword ptr [rax+rax+00h]
0x180023bfb  test    ebx, ebx
0x180023bfd  jle     short loc_180023C08
0x180023bff  movzx   ebx, bx
0x180023c02  or      ebx, 80070000h
0x180023c08  mov     eax, ebx
0x180023c0a  add     rsp, 68h
0x180023c0e  pop     r15
0x180023c10  pop     r14
0x180023c12  pop     r13
0x180023c14  pop     r12
0x180023c16  pop     rdi
0x180023c17  pop     rsi
0x180023c18  pop     rbx
0x180023c19  pop     rbp
0x180023c1a  retn
```
