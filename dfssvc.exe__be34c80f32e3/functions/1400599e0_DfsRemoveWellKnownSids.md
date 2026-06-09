# DfsRemoveWellKnownSids

- ea: `0x1400599e0`
- end: `0x140059ce9`
- name: `DfsRemoveWellKnownSids`
- size: `777`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140059558`

## callees

- `0x140001526`
- `0x1400599c4`
- `0x1400599e0`
- `0x140059cf0`

## import_xrefs

- `ntdll!RtlValidAcl` at `0x140059b9c`
- `ntdll!RtlValidAcl` at `0x140059b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059c61`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140059a7b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140059b61`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140059a7b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140059b61`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140059c0d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140059c51`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140059c0d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140059c51`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140059c72`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140059c72`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140059bc4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140059bc4`

## pseudocode

```c
__int64 __fastcall DfsRemoveWellKnownSids(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, _QWORD *a2)
{
  void *v3; // rdi
  struct _ACL *v4; // rsi
  struct _ACL *pSacl; // r12
  void *pPrimaryGroup; // r15
  void *pOwner; // r14
  DWORD LastError; // ebx
  void *v9; // rax
  DWORD dwSaclSize; // [rsp+60h] [rbp-19h] BYREF
  DWORD dwDaclSize; // [rsp+64h] [rbp-15h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwBufferLength; // [rsp+6Ch] [rbp-Dh] BYREF
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v16; // [rsp+90h] [rbp+17h]
  DWORD dwPrimaryGroupSize; // [rsp+F0h] [rbp+77h] BYREF
  DWORD dwOwnerSize; // [rsp+F8h] [rbp+7Fh] BYREF

  dwAbsoluteSecurityDescriptorSize = 40;
  *a2 = 0;
  v16 = 0;
  dwBufferLength = 0;
  dwDaclSize = 0;
  v3 = 0;
  v4 = 0;
  dwSaclSize = 0;
  pSacl = 0;
  dwPrimaryGroupSize = 0;
  pPrimaryGroup = 0;
  dwOwnerSize = 0;
  pOwner = 0;
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  if ( MakeAbsoluteSD(
         pSelfRelativeSecurityDescriptor,
         pAbsoluteSecurityDescriptor,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    goto LABEL_17;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
    goto LABEL_16;
  if ( !dwDaclSize )
    return 5;
  v4 = (struct _ACL *)malloc_0(dwDaclSize);
  if ( !v4 )
    return 8;
  if ( (!dwSaclSize || (pSacl = (struct _ACL *)malloc_0(dwSaclSize)) != 0)
    && (!dwOwnerSize || (pOwner = malloc_0(dwOwnerSize)) != 0)
    && (!dwPrimaryGroupSize || (pPrimaryGroup = malloc_0(dwPrimaryGroupSize)) != 0) )
  {
    dwAbsoluteSecurityDescriptorSize = 40;
    if ( !MakeAbsoluteSD(
            pSelfRelativeSecurityDescriptor,
            pAbsoluteSecurityDescriptor,
            &dwAbsoluteSecurityDescriptorSize,
            v4,
            &dwDaclSize,
            pSacl,
            &dwSaclSize,
            pOwner,
            &dwOwnerSize,
            pPrimaryGroup,
            &dwPrimaryGroupSize) )
    {
      LastError = GetLastError();
LABEL_16:
      if ( LastError )
        goto LABEL_33;
    }
LABEL_17:
    LastError = DfsRemoveWellKnownSidsAcl(v4);
    if ( LastError )
      goto LABEL_33;
    if ( !RtlValidAcl(v4) )
    {
      LastError = 1336;
      goto LABEL_33;
    }
    if ( !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v4, 0) )
    {
      LastError = GetLastError();
      goto LABEL_22;
    }
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength) )
      goto LABEL_32;
    LastError = GetLastError();
    if ( LastError != 122 )
    {
LABEL_22:
      if ( LastError )
      {
        if ( !v3 )
          goto LABEL_33;
LABEL_24:
        DfsDeallocateSecurityData(v3);
        goto LABEL_33;
      }
LABEL_32:
      *a2 = v3;
      goto LABEL_33;
    }
    LastError = 0;
    v9 = malloc_0(dwBufferLength);
    v3 = v9;
    if ( v9 )
    {
      if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v9, &dwBufferLength) )
        LastError = GetLastError();
      if ( !IsValidSecurityDescriptor(v3) )
      {
        LastError = 1338;
        goto LABEL_24;
      }
      goto LABEL_22;
    }
  }
  LastError = 8;
LABEL_33:
  if ( v4 )
    DfsDeallocateSecurityData(v4);
  if ( pSacl )
    DfsDeallocateSecurityData(pSacl);
  if ( pPrimaryGroup )
    DfsDeallocateSecurityData(pPrimaryGroup);
  if ( pOwner )
    DfsDeallocateSecurityData(pOwner);
  return LastError;
}

```

## disassembly

```asm
0x1400599e0  mov     [rsp-8+arg_0], rbx
0x1400599e5  mov     [rsp-8+arg_8], rdx
0x1400599ea  push    rbp
0x1400599eb  push    rsi
0x1400599ec  push    rdi
0x1400599ed  push    r12
0x1400599ef  push    r13
0x1400599f1  push    r14
0x1400599f3  push    r15
0x1400599f5  lea     rbp, [rsp-27h]
0x1400599fa  sub     rsp, 0A0h
0x140059a01  xor     ebx, ebx
0x140059a03  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x140059a0a  xor     eax, eax
0x140059a0c  mov     [rdx], rbx
0x140059a0f  mov     [rbp+57h+var_40], rax
0x140059a13  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140059a17  xorps   xmm0, xmm0
0x140059a1a  mov     [rbp+57h+dwBufferLength], ebx
0x140059a1d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140059a21  mov     [rbp+57h+dwDaclSize], ebx
0x140059a24  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140059a29  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140059a2d  mov     [rsp+0D0h+pPrimaryGroup], rbx; pPrimaryGroup
0x140059a32  lea     rax, [rbp+57h+dwOwnerSize]
0x140059a36  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140059a3b  xor     r9d, r9d; pDacl
0x140059a3e  mov     [rsp+0D0h+pOwner], rbx; pOwner
0x140059a43  lea     rax, [rbp+57h+dwSaclSize]
0x140059a47  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x140059a4c  mov     r13, rcx
0x140059a4f  lea     rax, [rbp+57h+dwDaclSize]
0x140059a53  mov     [rsp+0D0h+pSacl], rbx; pSacl
0x140059a58  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x140059a5d  mov     edi, ebx
0x140059a5f  mov     esi, ebx
0x140059a61  mov     [rbp+57h+dwSaclSize], ebx
0x140059a64  mov     r12d, ebx
0x140059a67  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x140059a6a  mov     r15d, ebx
0x140059a6d  mov     [rbp+57h+dwOwnerSize], ebx
0x140059a70  mov     r14d, ebx
0x140059a73  movups  [rbp+57h+pAbsoluteSecurityDescriptor], xmm0
0x140059a77  movups  [rbp+57h+var_50], xmm0
0x140059a7b  call    cs:__imp_MakeAbsoluteSD
0x140059a82  nop     dword ptr [rax+rax+00h]
0x140059a87  test    eax, eax
0x140059a89  jnz     loc_140059B87
0x140059a8f  call    cs:__imp_GetLastError
0x140059a96  nop     dword ptr [rax+rax+00h]
0x140059a9b  mov     ebx, eax
0x140059a9d  cmp     eax, 7Ah ; 'z'
0x140059aa0  jnz     loc_140059B7F
0x140059aa6  mov     eax, [rbp+57h+dwDaclSize]
0x140059aa9  test    eax, eax
0x140059aab  jnz     short loc_140059AB5
0x140059aad  lea     ebx, [rax+5]
0x140059ab0  jmp     loc_140059CCB
0x140059ab5  mov     rcx, rax; Size
0x140059ab8  call    malloc_0
0x140059abd  mov     rsi, rax
0x140059ac0  test    rax, rax
0x140059ac3  jnz     short loc_140059ACD
0x140059ac5  lea     ebx, [rax+8]
0x140059ac8  jmp     loc_140059CCB
0x140059acd  mov     eax, [rbp+57h+dwSaclSize]
0x140059ad0  test    eax, eax
0x140059ad2  jz      short loc_140059AED
0x140059ad4  mov     ecx, eax; Size
0x140059ad6  call    malloc_0
0x140059adb  mov     r12, rax
0x140059ade  test    rax, rax
0x140059ae1  jnz     short loc_140059AED
0x140059ae3  mov     ebx, 8
0x140059ae8  jmp     loc_140059C97
0x140059aed  mov     eax, [rbp+57h+dwOwnerSize]
0x140059af0  test    eax, eax
0x140059af2  jz      short loc_140059B03
0x140059af4  mov     ecx, eax; Size
0x140059af6  call    malloc_0
0x140059afb  mov     r14, rax
0x140059afe  test    rax, rax
0x140059b01  jz      short loc_140059AE3
0x140059b03  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x140059b06  test    eax, eax
0x140059b08  jz      short loc_140059B19
0x140059b0a  mov     ecx, eax; Size
0x140059b0c  call    malloc_0
0x140059b11  mov     r15, rax
0x140059b14  test    rax, rax
0x140059b17  jz      short loc_140059AE3
0x140059b19  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140059b1d  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x140059b24  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140059b29  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140059b2d  mov     [rsp+0D0h+pPrimaryGroup], r15; pPrimaryGroup
0x140059b32  lea     rax, [rbp+57h+dwOwnerSize]
0x140059b36  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140059b3b  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140059b3f  mov     [rsp+0D0h+pOwner], r14; pOwner
0x140059b44  lea     rax, [rbp+57h+dwSaclSize]
0x140059b48  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x140059b4d  mov     r9, rsi; pDacl
0x140059b50  lea     rax, [rbp+57h+dwDaclSize]
0x140059b54  mov     [rsp+0D0h+pSacl], r12; pSacl
0x140059b59  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x140059b5c  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x140059b61  call    cs:__imp_MakeAbsoluteSD
0x140059b68  nop     dword ptr [rax+rax+00h]
0x140059b6d  test    eax, eax
0x140059b6f  jnz     short loc_140059B87
0x140059b71  call    cs:__imp_GetLastError
0x140059b78  nop     dword ptr [rax+rax+00h]
0x140059b7d  mov     ebx, eax
0x140059b7f  test    ebx, ebx
0x140059b81  jnz     loc_140059C97
0x140059b87  mov     rcx, rsi; pAcl
0x140059b8a  call    DfsRemoveWellKnownSidsAcl
0x140059b8f  mov     ebx, eax
0x140059b91  test    eax, eax
0x140059b93  jnz     loc_140059C97
0x140059b99  mov     rcx, rsi; Acl
0x140059b9c  call    cs:__imp_RtlValidAcl
0x140059ba3  nop     dword ptr [rax+rax+00h]
0x140059ba8  test    al, al
0x140059baa  jnz     short loc_140059BB6
0x140059bac  mov     ebx, 538h
0x140059bb1  jmp     loc_140059C97
0x140059bb6  xor     r9d, r9d; bDaclDefaulted
0x140059bb9  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x140059bbd  mov     r8, rsi; pDacl
0x140059bc0  lea     edx, [r9+1]; bDaclPresent
0x140059bc4  call    cs:__imp_SetSecurityDescriptorDacl
0x140059bcb  nop     dword ptr [rax+rax+00h]
0x140059bd0  test    eax, eax
0x140059bd2  jnz     short loc_140059C03
0x140059bd4  call    cs:__imp_GetLastError
0x140059bdb  nop     dword ptr [rax+rax+00h]
0x140059be0  mov     ebx, eax
0x140059be2  mov     rax, rdi
0x140059be5  test    ebx, ebx
0x140059be7  jz      loc_140059C90
0x140059bed  test    rax, rax
0x140059bf0  jz      loc_140059C97
0x140059bf6  mov     rcx, rdi
0x140059bf9  call    DfsDeallocateSecurityData
0x140059bfe  jmp     loc_140059C97
0x140059c03  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x140059c07  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x140059c09  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140059c0d  call    cs:__imp_MakeSelfRelativeSD
0x140059c14  nop     dword ptr [rax+rax+00h]
0x140059c19  test    eax, eax
0x140059c1b  jnz     short loc_140059C90
0x140059c1d  call    cs:__imp_GetLastError
0x140059c24  nop     dword ptr [rax+rax+00h]
0x140059c29  mov     ebx, eax
0x140059c2b  cmp     eax, 7Ah ; 'z'
0x140059c2e  jnz     short loc_140059BE2
0x140059c30  mov     ecx, [rbp+57h+dwBufferLength]; Size
0x140059c33  xor     ebx, ebx
0x140059c35  call    malloc_0
0x140059c3a  mov     rdi, rax
0x140059c3d  test    rax, rax
0x140059c40  jz      loc_140059AE3
0x140059c46  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x140059c4a  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x140059c4d  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140059c51  call    cs:__imp_MakeSelfRelativeSD
0x140059c58  nop     dword ptr [rax+rax+00h]
0x140059c5d  test    eax, eax
0x140059c5f  jnz     short loc_140059C6F
0x140059c61  call    cs:__imp_GetLastError
0x140059c68  nop     dword ptr [rax+rax+00h]
0x140059c6d  mov     ebx, eax
0x140059c6f  mov     rcx, rdi; pSecurityDescriptor
0x140059c72  call    cs:__imp_IsValidSecurityDescriptor
0x140059c79  nop     dword ptr [rax+rax+00h]
0x140059c7e  test    eax, eax
0x140059c80  jnz     loc_140059BE2
0x140059c86  mov     ebx, 53Ah
0x140059c8b  jmp     loc_140059BF6
0x140059c90  mov     rax, [rbp+57h+arg_8]
0x140059c94  mov     [rax], rdi
0x140059c97  test    rsi, rsi
0x140059c9a  jz      short loc_140059CA4
0x140059c9c  mov     rcx, rsi
0x140059c9f  call    DfsDeallocateSecurityData
0x140059ca4  test    r12, r12
0x140059ca7  jz      short loc_140059CB1
0x140059ca9  mov     rcx, r12
0x140059cac  call    DfsDeallocateSecurityData
0x140059cb1  test    r15, r15
0x140059cb4  jz      short loc_140059CBE
0x140059cb6  mov     rcx, r15
0x140059cb9  call    DfsDeallocateSecurityData
0x140059cbe  test    r14, r14
0x140059cc1  jz      short loc_140059CCB
0x140059cc3  mov     rcx, r14
0x140059cc6  call    DfsDeallocateSecurityData
0x140059ccb  mov     eax, ebx
0x140059ccd  mov     rbx, [rsp+0D0h+arg_0]
0x140059cd5  add     rsp, 0A0h
0x140059cdc  pop     r15
0x140059cde  pop     r14
0x140059ce0  pop     r13
0x140059ce2  pop     r12
0x140059ce4  pop     rdi
0x140059ce5  pop     rsi
0x140059ce6  pop     rbp
0x140059ce7  retn
```
