# basessp::BaseSSP::WSTDecodeSecret(ushort *,void *,_UNICODE_STRING *)

- ea: `0x1800063e4`
- end: `0x18000663e`
- name: `?WSTDecodeSecret@BaseSSP@basessp@@AEAAJPEAGPEAXPEAU_UNICODE_STRING@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, unsigned __int16 *, HANDLE Token, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004404`

## callees

- `0x1800027e4`
- `0x180005960`
- `0x1800063e4`
- `0x180006650`
- `0x18000ebcc`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800064ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800064ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065bd`
- `ntdll!RtlInitUnicodeString` at `0x18000647e`
- `ntdll!RtlInitUnicodeString` at `0x18000647e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000649b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000649b`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800065ad`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18000660d`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800065ad`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18000660d`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180006446`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180006446`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTDecodeSecret(
        basessp::BaseSSP *this,
        unsigned __int16 *a2,
        HANDLE Token,
        struct _UNICODE_STRING *a4)
{
  WCHAR *v4; // rdi
  __int64 v10; // rbp
  unsigned int v11; // ebx
  char v12; // r15
  DWORD v13; // r12d
  unsigned __int8 v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rax
  DWORD LastError; // eax
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF
  DWORD pcchMaxChars; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 0;
  pcchMaxChars = 0;
  pProtectionType = CredUnprotected;
  DestinationString = 0;
  if ( !a4 )
    return 3221225485LL;
  *a4 = 0;
  if ( !a2 )
    return 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( CredIsProtectedW(a2, &pProtectionType) )
  {
    v12 = 0;
    v13 = 0;
    if ( pProtectionType )
    {
      if ( pProtectionType == CredUserProtection )
      {
        if ( Token )
        {
          if ( !SetThreadToken(0, Token) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_e422180f20743fb5cd5d11e667ac2c29_Traceguids,
                LastError);
            }
            return (unsigned int)-1073741555;
          }
        }
        else
        {
          v11 = basessp::WSTGlobalLsaFunctions->ImpersonateClient();
          if ( (v11 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e422180f20743fb5cd5d11e667ac2c29_Traceguids, v11);
            return v11;
          }
        }
        v12 = 1;
      }
      else if ( pProtectionType != CredTrustedProtection )
      {
        goto LABEL_12;
      }
      if ( !CredUnprotectW(0, a2, v10 + 1, 0, &pcchMaxChars) )
      {
        if ( GetLastError() != 122 || !pcchMaxChars )
          goto LABEL_39;
        v13 = 2 * pcchMaxChars;
        v4 = (WCHAR *)basessp::BaseSSP::WSTAllocate(this, 2 * pcchMaxChars);
        if ( !v4 )
        {
          v11 = -1073741670;
          goto LABEL_14;
        }
        if ( !CredUnprotectW(0, a2, v10 + 1, v4, &pcchMaxChars) || pcchMaxChars && v4[pcchMaxChars - 1] )
        {
LABEL_39:
          v11 = -1073741811;
          goto LABEL_14;
        }
      }
LABEL_13:
      RtlInitUnicodeString(&DestinationString, v4);
      v11 = basessp::BaseSSP::WSTDuplicateStringEx(this, a4, &DestinationString, v14);
LABEL_14:
      if ( v12 )
        RevertToSelf();
      if ( v4 && v4 != a2 )
      {
        v15 = v13;
        v16 = v4;
        if ( v13 )
        {
          do
          {
            *(_BYTE *)v16 = 0;
            v16 = (WCHAR *)((char *)v16 + 1);
            --v15;
          }
          while ( v15 );
        }
        basessp::BaseSSP::WSTFree(this, v4);
      }
      return v11;
    }
LABEL_12:
    v4 = a2;
    goto LABEL_13;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x1800063e4  mov     rax, rsp
0x1800063e7  push    rbx
0x1800063e8  push    rbp
0x1800063e9  push    rsi
0x1800063ea  push    rdi
0x1800063eb  push    r12
0x1800063ed  push    r13
0x1800063ef  push    r14
0x1800063f1  push    r15
0x1800063f3  sub     rsp, 58h
0x1800063f7  xor     edi, edi
0x1800063f9  xorps   xmm0, xmm0
0x1800063fc  mov     [rax+20h], edi
0x1800063ff  mov     r14, r9
0x180006402  mov     [rax-68h], edi
0x180006405  mov     rbx, r8
0x180006408  mov     rsi, rdx
0x18000640b  mov     r13, rcx
0x18000640e  movups  xmmword ptr [rax-60h], xmm0
0x180006412  test    r9, r9
0x180006415  jnz     short loc_180006421
0x180006417  mov     eax, 0C000000Dh
0x18000641c  jmp     loc_1800064CF
0x180006421  movups  xmmword ptr [r9], xmm0
0x180006425  test    rsi, rsi
0x180006428  jnz     short loc_180006431
0x18000642a  xor     eax, eax
0x18000642c  jmp     loc_1800064CF
0x180006431  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006435  inc     rbp
0x180006438  cmp     [rdx+rbp*2], di
0x18000643c  jnz     short loc_180006435
0x18000643e  lea     rdx, [rsp+98h+pProtectionType]; pProtectionType
0x180006443  mov     rcx, rsi; pszProtectedCredentials
0x180006446  call    cs:__imp_CredIsProtectedW
0x18000644c  test    eax, eax
0x18000644e  jnz     short loc_180006457
0x180006450  mov     ebx, 0C000000Dh
0x180006455  jmp     short loc_1800064CD
0x180006457  mov     ecx, [rsp+98h+pProtectionType]
0x18000645b  mov     r15b, dil
0x18000645e  mov     r12d, edi
0x180006461  test    ecx, ecx
0x180006463  jz      short loc_180006473
0x180006465  sub     ecx, 1
0x180006468  jz      short loc_1800064E0
0x18000646a  cmp     ecx, 1
0x18000646d  jz      loc_180006594
0x180006473  mov     rdi, rsi
0x180006476  mov     rdx, rdi; SourceString
0x180006479  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x18000647e  call    cs:__imp_RtlInitUnicodeString
0x180006484  lea     r8, [rsp+98h+DestinationString]; struct _UNICODE_STRING *
0x180006489  mov     rdx, r14; struct _UNICODE_STRING *
0x18000648c  mov     rcx, r13; this
0x18000648f  call    ?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z; basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x180006494  mov     ebx, eax
0x180006496  test    r15b, r15b
0x180006499  jz      short loc_1800064A1
0x18000649b  call    cs:__imp_RevertToSelf
0x1800064a1  test    rdi, rdi
0x1800064a4  jz      short loc_1800064CD
0x1800064a6  cmp     rdi, rsi
0x1800064a9  jz      short loc_1800064CD
0x1800064ab  mov     ecx, r12d
0x1800064ae  mov     rax, rdi
0x1800064b1  test    r12d, r12d
0x1800064b4  jz      short loc_1800064C2
0x1800064b6  mov     byte ptr [rax], 0
0x1800064b9  inc     rax
0x1800064bc  sub     rcx, 1
0x1800064c0  jnz     short loc_1800064B6
0x1800064c2  mov     rdx, rdi; void *
0x1800064c5  mov     rcx, r13; this
0x1800064c8  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x1800064cd  mov     eax, ebx
0x1800064cf  add     rsp, 58h
0x1800064d3  pop     r15
0x1800064d5  pop     r14
0x1800064d7  pop     r13
0x1800064d9  pop     r12
0x1800064db  pop     rdi
0x1800064dc  pop     rsi
0x1800064dd  pop     rbp
0x1800064de  pop     rbx
0x1800064df  retn
0x1800064e0  test    rbx, rbx
0x1800064e3  jz      short loc_18000653D
0x1800064e5  mov     rdx, rbx; Token
0x1800064e8  xor     ecx, ecx; Thread
0x1800064ea  call    cs:__imp_SetThreadToken
0x1800064f0  test    eax, eax
0x1800064f2  jnz     loc_180006591
0x1800064f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064ff  lea     rax, WPP_GLOBAL_Control
0x180006506  cmp     rcx, rax
0x180006509  jz      short loc_180006536
0x18000650b  test    byte ptr [rcx+1Ch], 1
0x18000650f  jz      short loc_180006536
0x180006511  call    cs:__imp_GetLastError
0x180006517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000651e  lea     r8, WPP_e422180f20743fb5cd5d11e667ac2c29_Traceguids
0x180006525  mov     edx, 0Ah
0x18000652a  mov     r9d, eax
0x18000652d  mov     rcx, [rcx+10h]
0x180006531  call    WPP_SF_d
0x180006536  mov     ebx, 0C000010Dh
0x18000653b  jmp     short loc_1800064CD
0x18000653d  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x180006544  mov     rax, [rax+58h]
0x180006548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654d  mov     ebx, eax
0x18000654f  test    eax, eax
0x180006551  jns     short loc_180006591
0x180006553  mov     rcx, cs:WPP_GLOBAL_Control
0x18000655a  lea     rax, WPP_GLOBAL_Control
0x180006561  cmp     rcx, rax
0x180006564  jz      loc_1800064CD
0x18000656a  test    byte ptr [rcx+1Ch], 1
0x18000656e  jz      loc_1800064CD
0x180006574  mov     rcx, [rcx+10h]
0x180006578  lea     r8, WPP_e422180f20743fb5cd5d11e667ac2c29_Traceguids
0x18000657f  mov     edx, 0Bh
0x180006584  mov     r9d, ebx
0x180006587  call    WPP_SF_d
0x18000658c  jmp     loc_1800064CD
0x180006591  mov     r15b, 1
0x180006594  lea     rax, [rsp+98h+arg_18]
0x18000659c  xor     r9d, r9d; pszCredentials
0x18000659f  lea     r8d, [rbp+1]; cchProtectedCredentials
0x1800065a3  mov     [rsp+98h+pcchMaxChars], rax; pcchMaxChars
0x1800065a8  mov     rdx, rsi; pszProtectedCredentials
0x1800065ab  xor     ecx, ecx; fAsSelf
0x1800065ad  call    cs:__imp_CredUnprotectW
0x1800065b3  xor     ebx, ebx
0x1800065b5  test    eax, eax
0x1800065b7  jnz     loc_180006476
0x1800065bd  call    cs:__imp_GetLastError
0x1800065c3  cmp     eax, 7Ah ; 'z'
0x1800065c6  jnz     short loc_180006617
0x1800065c8  mov     eax, [rsp+98h+arg_18]
0x1800065cf  test    eax, eax
0x1800065d1  jz      short loc_180006617
0x1800065d3  lea     r12d, [rax+rax]
0x1800065d7  mov     rcx, r13; this
0x1800065da  mov     edx, r12d; unsigned __int64
0x1800065dd  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x1800065e2  mov     rdi, rax
0x1800065e5  test    rax, rax
0x1800065e8  jnz     short loc_1800065F4
0x1800065ea  mov     ebx, 0C000009Ah
0x1800065ef  jmp     loc_180006496
0x1800065f4  lea     rax, [rsp+98h+arg_18]
0x1800065fc  mov     r9, rdi; pszCredentials
0x1800065ff  lea     r8d, [rbp+1]; cchProtectedCredentials
0x180006603  mov     [rsp+98h+pcchMaxChars], rax; pcchMaxChars
0x180006608  mov     rdx, rsi; pszProtectedCredentials
0x18000660b  xor     ecx, ecx; fAsSelf
0x18000660d  call    cs:__imp_CredUnprotectW
0x180006613  test    eax, eax
0x180006615  jnz     short loc_180006621
0x180006617  mov     ebx, 0C000000Dh
0x18000661c  jmp     loc_180006496
0x180006621  mov     eax, [rsp+98h+arg_18]
0x180006628  test    eax, eax
0x18000662a  jz      loc_180006476
0x180006630  dec     eax
0x180006632  cmp     [rdi+rax*2], bx
0x180006636  jz      loc_180006476
0x18000663c  jmp     short loc_180006617
```
