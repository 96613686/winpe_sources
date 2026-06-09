# AddSidToTokenAcl(void *,void *,ulong)

- ea: `0x180021a1c`
- end: `0x180021d9a`
- name: `?AddSidToTokenAcl@@YAJPEAX0K@Z`
- size: `894`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022240`

## callees

- `0x1800183f8`
- `0x180018438`
- `0x180021a1c`
- `0x180021f54`
- `0x180022130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d25`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180021d1b`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180021d1b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180021d04`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180021d04`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180021b8d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180021c75`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180021b8d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180021c75`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021a99`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021af4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021a99`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021af4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021cec`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021cec`

## pseudocode

```c
__int64 __fastcall AddSidToTokenAcl(HANDLE Handle, void *a2)
{
  PSID v2; // r13
  void *v3; // r12
  PACL v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rax
  signed int LastError; // eax
  struct _ACL *v10; // rdi
  struct _ACL *pSacl; // r14
  void *pOwner; // r15
  unsigned int v13; // edx
  signed int v14; // eax
  void *pPrimaryGroup; // rax
  signed int v16; // eax
  int v17; // eax
  signed int v18; // eax
  DWORD dwOwnerSize; // [rsp+68h] [rbp-39h] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp-31h] BYREF
  int v23; // [rsp+74h] [rbp-2Dh] BYREF
  PACL pAcl; // [rsp+78h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+80h] [rbp-21h]
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+88h] [rbp-19h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+7h]
  DWORD dwDaclSize; // [rsp+110h] [rbp+6Fh] BYREF
  int v30; // [rsp+114h] [rbp+73h]
  DWORD nLengthNeeded; // [rsp+118h] [rbp+77h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+120h] [rbp+7Fh] BYREF

  v30 = HIDWORD(a2);
  v2 = g_pSidWpg;
  v3 = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v27 = 0;
  pAcl = 0;
  nLengthNeeded = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  v5 = 0;
  v23 = 0;
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  GetKernelObjectSecurity(Handle, 4u, 0, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v8 = operator new(nLengthNeeded);
    pSelfRelativeSecurityDescriptor = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    if ( !GetKernelObjectSecurity(Handle, 4u, v8, nLengthNeeded, &nLengthNeeded) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_42;
    }
    v10 = (struct _ACL *)operator new(nLengthNeeded);
    if ( !v10 )
    {
LABEL_10:
      v7 = -2147024882;
LABEL_42:
      operator delete(pSelfRelativeSecurityDescriptor);
      return v7;
    }
    pSacl = 0;
    pOwner = 0;
    dwAbsoluteSecurityDescriptorSize = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( !MakeAbsoluteSD(
            pSelfRelativeSecurityDescriptor,
            0,
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
      dwDaclSize = nLengthNeeded;
      dwAbsoluteSecurityDescriptorSize = 40;
      v14 = GetLastError();
      v7 = v14;
      if ( v14 != 122 )
      {
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_40;
      }
      if ( dwDaclSize > nLengthNeeded )
      {
        operator delete(v10);
        v10 = (struct _ACL *)operator new(dwDaclSize);
        if ( !v10 )
          goto LABEL_10;
      }
      pSacl = (struct _ACL *)operator new(dwSaclSize);
      if ( !pSacl )
      {
        v7 = -2147024882;
LABEL_40:
        operator delete(v10);
        if ( v5 )
          operator delete(v5);
        goto LABEL_42;
      }
      pOwner = operator new(dwOwnerSize);
      if ( !pOwner || (pPrimaryGroup = operator new(dwPrimaryGroupSize), (v3 = pPrimaryGroup) == 0) )
      {
        v7 = -2147024882;
LABEL_35:
        operator delete(pSacl);
LABEL_36:
        if ( pOwner )
          operator delete(pOwner);
        if ( v3 )
          operator delete(v3);
        goto LABEL_40;
      }
      if ( !MakeAbsoluteSD(
              pSelfRelativeSecurityDescriptor,
              pAbsoluteSecurityDescriptor,
              &dwAbsoluteSecurityDescriptorSize,
              v10,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        v16 = GetLastError();
        v7 = v16;
        if ( v16 > 0 )
          v7 = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_35;
      }
    }
    v7 = AllowedAccessExists(v10, v13, v2, &v23);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( v23 )
      {
        v7 = 0;
      }
      else
      {
        v17 = ExpandAcl(v10, nLengthNeeded, &pAcl, v2);
        v5 = pAcl;
        v7 = v17;
        if ( v17 >= 0
          && (!AddAccessAllowedAce(pAcl, 2u, 0xF01FFu, v2)
           || !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v5, 0)
           || !SetKernelObjectSecurity(Handle, 4u, pAbsoluteSecurityDescriptor)) )
        {
          v18 = GetLastError();
          v7 = v18;
          if ( v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
        }
      }
    }
    if ( !pSacl )
      goto LABEL_36;
    goto LABEL_35;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180021a1c  mov     rax, rsp
0x180021a1f  mov     [rax+18h], r8d
0x180021a23  mov     [rax+10h], rdx
0x180021a27  mov     [rax+8], rcx
0x180021a2b  push    rbp
0x180021a2c  push    rbx
0x180021a2d  push    rsi
0x180021a2e  push    rdi
0x180021a2f  push    r12
0x180021a31  push    r13
0x180021a33  push    r14
0x180021a35  push    r15
0x180021a37  lea     rbp, [rax-5Fh]
0x180021a3b  sub     rsp, 0B8h
0x180021a42  mov     r13, cs:?g_pSidWpg@@3PEAXEA; void * g_pSidWpg
0x180021a49  xor     r12d, r12d
0x180021a4c  xor     eax, eax
0x180021a4e  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r12d
0x180021a52  xorps   xmm0, xmm0
0x180021a55  mov     [rbp+57h+var_50], rax
0x180021a59  lea     rax, [rbp+57h+nLengthNeeded]
0x180021a5d  mov     [rbp+57h+pAcl], r12
0x180021a61  lea     edi, [r12+4]
0x180021a66  mov     [rbp+57h+nLengthNeeded], r12d
0x180021a6a  mov     edx, edi; RequestedInformation
0x180021a6c  mov     [rbp+57h+dwDaclSize], r12d
0x180021a70  xor     r9d, r9d; nLength
0x180021a73  mov     [rbp+57h+dwSaclSize], r12d
0x180021a77  xor     r8d, r8d; pSecurityDescriptor
0x180021a7a  mov     [rbp+57h+dwOwnerSize], r12d
0x180021a7e  mov     rbx, rcx
0x180021a81  mov     [rbp+57h+dwPrimaryGroupSize], r12d
0x180021a85  mov     esi, r12d
0x180021a88  mov     [rbp+57h+var_84], r12d
0x180021a8c  movups  [rbp+57h+pAbsoluteSecurityDescriptor], xmm0
0x180021a90  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180021a95  movups  [rbp+57h+var_60], xmm0
0x180021a99  call    cs:__imp_GetKernelObjectSecurity
0x180021a9f  mov     eax, [rbp+57h+nLengthNeeded]
0x180021aa2  test    eax, eax
0x180021aa4  jnz     short loc_180021AC4
0x180021aa6  call    cs:__imp_GetLastError
0x180021aac  mov     ebx, eax
0x180021aae  test    eax, eax
0x180021ab0  jle     loc_180021D84
0x180021ab6  movzx   ebx, ax
0x180021ab9  or      ebx, 80070000h
0x180021abf  jmp     loc_180021D84
0x180021ac4  mov     rcx, rax; Size
0x180021ac7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021acc  mov     [rbp+57h+pSelfRelativeSecurityDescriptor], rax
0x180021ad0  test    rax, rax
0x180021ad3  jnz     short loc_180021ADF
0x180021ad5  mov     ebx, 8007000Eh
0x180021ada  jmp     loc_180021D84
0x180021adf  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180021ae3  lea     rcx, [rbp+57h+nLengthNeeded]
0x180021ae7  mov     [rsp+0F0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180021aec  mov     r8, rax; pSecurityDescriptor
0x180021aef  mov     rcx, rbx; Handle
0x180021af2  mov     edx, edi; RequestedInformation
0x180021af4  call    cs:__imp_GetKernelObjectSecurity
0x180021afa  test    eax, eax
0x180021afc  jnz     short loc_180021B1C
0x180021afe  call    cs:__imp_GetLastError
0x180021b04  mov     ebx, eax
0x180021b06  test    eax, eax
0x180021b08  jle     loc_180021D7B
0x180021b0e  movzx   ebx, ax
0x180021b11  or      ebx, 80070000h
0x180021b17  jmp     loc_180021D7B
0x180021b1c  mov     ecx, [rbp+57h+nLengthNeeded]; Size
0x180021b1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021b24  mov     rdi, rax
0x180021b27  test    rax, rax
0x180021b2a  jnz     short loc_180021B36
0x180021b2c  mov     ebx, 8007000Eh
0x180021b31  jmp     loc_180021D7B
0x180021b36  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180021b3a  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180021b3e  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180021b43  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180021b47  xor     ebx, ebx
0x180021b49  lea     rax, [rbp+57h+dwOwnerSize]
0x180021b4d  mov     [rsp+0F0h+pPrimaryGroup], rbx; pPrimaryGroup
0x180021b52  xor     r9d, r9d; pDacl
0x180021b55  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180021b5a  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180021b5c  mov     [rsp+0F0h+pOwner], rbx; pOwner
0x180021b61  lea     rax, [rbp+57h+dwSaclSize]
0x180021b65  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180021b6a  mov     r14, r12
0x180021b6d  lea     rax, [rbp+57h+dwDaclSize]
0x180021b71  mov     [rsp+0F0h+pSacl], rbx; pSacl
0x180021b76  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpdwDaclSize
0x180021b7b  mov     r15, r12
0x180021b7e  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x180021b81  mov     [rbp+57h+dwDaclSize], ebx
0x180021b84  mov     [rbp+57h+dwSaclSize], ebx
0x180021b87  mov     [rbp+57h+dwOwnerSize], ebx
0x180021b8a  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x180021b8d  call    cs:__imp_MakeAbsoluteSD
0x180021b93  test    eax, eax
0x180021b95  jnz     loc_180021C9D
0x180021b9b  mov     eax, [rbp+57h+nLengthNeeded]
0x180021b9e  mov     [rbp+57h+dwDaclSize], eax
0x180021ba1  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x180021ba8  call    cs:__imp_GetLastError
0x180021bae  mov     ebx, eax
0x180021bb0  cmp     eax, 7Ah ; 'z'
0x180021bb3  jz      short loc_180021BCB
0x180021bb5  test    eax, eax
0x180021bb7  jle     loc_180021D66
0x180021bbd  movzx   ebx, ax
0x180021bc0  or      ebx, 80070000h
0x180021bc6  jmp     loc_180021D66
0x180021bcb  mov     eax, [rbp+57h+nLengthNeeded]
0x180021bce  cmp     [rbp+57h+dwDaclSize], eax
0x180021bd1  jbe     short loc_180021BEF
0x180021bd3  mov     rcx, rdi; Block
0x180021bd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021bdb  mov     ecx, [rbp+57h+dwDaclSize]; Size
0x180021bde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021be3  mov     rdi, rax
0x180021be6  test    rax, rax
0x180021be9  jz      loc_180021B2C
0x180021bef  mov     ecx, [rbp+57h+dwSaclSize]; Size
0x180021bf2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021bf7  mov     r14, rax
0x180021bfa  test    rax, rax
0x180021bfd  jnz     short loc_180021C09
0x180021bff  mov     ebx, 8007000Eh
0x180021c04  jmp     loc_180021D61
0x180021c09  mov     ecx, [rbp+57h+dwOwnerSize]; Size
0x180021c0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c11  mov     r15, rax
0x180021c14  test    rax, rax
0x180021c17  jnz     short loc_180021C23
0x180021c19  mov     ebx, 8007000Eh
0x180021c1e  jmp     loc_180021D3F
0x180021c23  mov     ecx, [rbp+57h+dwPrimaryGroupSize]; Size
0x180021c26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c2b  mov     r12, rax
0x180021c2e  test    rax, rax
0x180021c31  jz      short loc_180021C19
0x180021c33  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180021c37  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180021c3b  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180021c40  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180021c44  mov     [rsp+0F0h+pPrimaryGroup], r12; pPrimaryGroup
0x180021c49  lea     rax, [rbp+57h+dwOwnerSize]
0x180021c4d  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180021c52  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180021c56  mov     [rsp+0F0h+pOwner], r15; pOwner
0x180021c5b  lea     rax, [rbp+57h+dwSaclSize]
0x180021c5f  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180021c64  mov     r9, rdi; pDacl
0x180021c67  lea     rax, [rbp+57h+dwDaclSize]
0x180021c6b  mov     [rsp+0F0h+pSacl], r14; pSacl
0x180021c70  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpdwDaclSize
0x180021c75  call    cs:__imp_MakeAbsoluteSD
0x180021c7b  test    eax, eax
0x180021c7d  jnz     short loc_180021C9D
0x180021c7f  call    cs:__imp_GetLastError
0x180021c85  mov     ebx, eax
0x180021c87  test    eax, eax
0x180021c89  jle     loc_180021D3F
0x180021c8f  movzx   ebx, ax
0x180021c92  or      ebx, 80070000h
0x180021c98  jmp     loc_180021D3F
0x180021c9d  lea     r9, [rbp+57h+var_84]; int *
0x180021ca1  mov     r8, r13; void *
0x180021ca4  mov     rcx, rdi; pAcl
0x180021ca7  call    ?AllowedAccessExists@@YAJPEAU_ACL@@KPEAXPEAH@Z; AllowedAccessExists(_ACL *,ulong,void *,int *)
0x180021cac  mov     ebx, eax
0x180021cae  test    eax, eax
0x180021cb0  js      loc_180021D3A
0x180021cb6  cmp     [rbp+57h+var_84], esi
0x180021cb9  jz      short loc_180021CBF
0x180021cbb  xor     ebx, ebx
0x180021cbd  jmp     short loc_180021D3A
0x180021cbf  mov     edx, [rbp+57h+nLengthNeeded]; unsigned int
0x180021cc2  lea     r8, [rbp+57h+pAcl]; struct _ACL **
0x180021cc6  mov     r9, r13; void *
0x180021cc9  mov     rcx, rdi; pAcl
0x180021ccc  call    ?ExpandAcl@@YAJPEAU_ACL@@KPEAPEAU1@PEAX@Z; ExpandAcl(_ACL *,ulong,_ACL * *,void *)
0x180021cd1  mov     rsi, [rbp+57h+pAcl]
0x180021cd5  mov     ebx, eax
0x180021cd7  test    eax, eax
0x180021cd9  js      short loc_180021D3A
0x180021cdb  mov     r9, r13; pSid
0x180021cde  mov     edx, 2; dwAceRevision
0x180021ce3  mov     r8d, 0F01FFh; AccessMask
0x180021ce9  mov     rcx, rsi; pAcl
0x180021cec  call    cs:__imp_AddAccessAllowedAce
0x180021cf2  test    eax, eax
0x180021cf4  jz      short loc_180021D25
0x180021cf6  xor     r9d, r9d; bDaclDefaulted
0x180021cf9  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x180021cfd  mov     r8, rsi; pDacl
0x180021d00  lea     edx, [r9+1]; bDaclPresent
0x180021d04  call    cs:__imp_SetSecurityDescriptorDacl
0x180021d0a  test    eax, eax
0x180021d0c  jz      short loc_180021D25
0x180021d0e  mov     rcx, [rbp+57h+Handle]; Handle
0x180021d12  lea     r8, [rbp+57h+pAbsoluteSecurityDescriptor]; SecurityDescriptor
0x180021d16  mov     edx, 4; SecurityInformation
0x180021d1b  call    cs:__imp_SetKernelObjectSecurity
0x180021d21  test    eax, eax
0x180021d23  jnz     short loc_180021D3A
0x180021d25  call    cs:__imp_GetLastError
0x180021d2b  mov     ebx, eax
0x180021d2d  test    eax, eax
0x180021d2f  jle     short loc_180021D3A
0x180021d31  movzx   ebx, ax
0x180021d34  or      ebx, 80070000h
0x180021d3a  test    r14, r14
0x180021d3d  jz      short loc_180021D47
0x180021d3f  mov     rcx, r14; Block
0x180021d42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d47  test    r15, r15
0x180021d4a  jz      short loc_180021D54
0x180021d4c  mov     rcx, r15; Block
0x180021d4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d54  test    r12, r12
0x180021d57  jz      short loc_180021D61
0x180021d59  mov     rcx, r12; Block
0x180021d5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d61  test    rdi, rdi
0x180021d64  jz      short loc_180021D6E
0x180021d66  mov     rcx, rdi; Block
0x180021d69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d6e  test    rsi, rsi
0x180021d71  jz      short loc_180021D7B
0x180021d73  mov     rcx, rsi; Block
0x180021d76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d7b  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; Block
0x180021d7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d84  mov     eax, ebx
0x180021d86  add     rsp, 0B8h
0x180021d8d  pop     r15
0x180021d8f  pop     r14
0x180021d91  pop     r13
0x180021d93  pop     r12
0x180021d95  pop     rdi
0x180021d96  pop     rsi
0x180021d97  pop     rbx
0x180021d98  pop     rbp
0x180021d99  retn
```
