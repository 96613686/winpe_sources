# _CryptSetSidDaclAce

- ea: `0x18005a60c`
- end: `0x18005a7c5`
- name: `_CryptSetSidDaclAce`
- size: `441`
- prototype: `__int64 __fastcall(void *, int, DWORD, DWORD, PSID pSid1, int *, struct _ACL **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a4c4`
- `0x1800a8ce0`

## callees

- `0x180028d60`
- `0x180046e10`
- `0x18005a60c`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7a3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005a6dd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011908a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005a6dd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011908a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005a6ad`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005a6ad`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180119063`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1801190df`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180119063`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1801190df`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801190b1`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801190b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005a75a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005a75a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a686`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a686`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005a6fa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005a6fa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005a782`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005a782`

## pseudocode

```c
__int64 __fastcall CryptSetSidDaclAce(void *a1, int a2, DWORD a3, DWORD a4, PSID pSid1, int *a6, struct _ACL **a7)
{
  struct _ACL *v8; // rbx
  int v9; // r15d
  int v10; // r14d
  DWORD v11; // esi
  unsigned int v12; // edi
  _BYTE *v13; // rax
  DWORD LengthSid; // eax
  DWORD v16; // esi
  struct _ACL *v17; // rax
  DWORD v18; // r15d
  DWORD i; // esi
  LPVOID pAce; // [rsp+30h] [rbp-50h] BYREF
  DWORD AccessMask; // [rsp+38h] [rbp-48h]
  int v22; // [rsp+3Ch] [rbp-44h]
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-38h] BYREF
  WINBOOL bDaclPresent; // [rsp+4Ch] [rbp-34h] BYREF
  int v26; // [rsp+50h] [rbp-30h]
  int *v27; // [rsp+58h] [rbp-28h]
  struct _ACL **v28; // [rsp+60h] [rbp-20h]
  __int64 pAclInformation; // [rsp+68h] [rbp-18h] BYREF
  int v30; // [rsp+70h] [rbp-10h]

  v27 = a6;
  v8 = 0;
  v28 = a7;
  AccessMask = a4;
  v26 = a2;
  pAclInformation = 0;
  v30 = 0;
  v22 = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    goto LABEL_11;
  if ( !pDacl )
  {
    SetLastError(0x538u);
LABEL_11:
    v12 = 0;
    PkiDefaultCryptFree(v8);
    v8 = 0;
    goto LABEL_10;
  }
  if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
    goto LABEL_11;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 1;
  while ( v11 < (unsigned int)pAclInformation )
  {
    pAce = 0;
    if ( !GetAce(pDacl, v11, &pAce) )
      goto LABEL_11;
    v13 = pAce;
    if ( !*(_BYTE *)pAce )
    {
      if ( EqualSid(pSid1, (char *)pAce + 8) )
      {
        v22 = 1;
        goto LABEL_10;
      }
      v13 = pAce;
    }
    if ( (v13[1] & 0x10) != 0 )
      v9 = 1;
    if ( *v13 == 1 )
      v10 = 1;
    ++v11;
  }
  if ( !v26 )
  {
    LengthSid = GetLengthSid(pSid1);
    v16 = LengthSid + HIDWORD(pAclInformation) + 8;
    v17 = (struct _ACL *)PkiZeroAlloc(v16);
    v8 = v17;
    if ( !v17 || !InitializeAcl(v17, v16, 2u) )
      goto LABEL_11;
    if ( !v9 )
      a3 &= ~0x10u;
    v18 = AccessMask;
    if ( !v10 && !AddAccessAllowedAceEx(v8, 2u, a3, AccessMask, pSid1) )
      goto LABEL_11;
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      pAce = 0;
      if ( !GetAce(pDacl, i, &pAce) || !AddAce(v8, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
        goto LABEL_11;
    }
    if ( v10 && !AddAccessAllowedAceEx(v8, 2u, a3, v18, pSid1) )
      goto LABEL_11;
  }
LABEL_10:
  *v27 = v22;
  *v28 = v8;
  return v12;
}

```

## disassembly

```asm
0x18005a60c  mov     [rsp-38h+arg_8], rbx
0x18005a611  push    rbp
0x18005a612  push    rsi
0x18005a613  push    rdi
0x18005a614  push    r12
0x18005a616  push    r13
0x18005a618  push    r14
0x18005a61a  push    r15
0x18005a61c  mov     rbp, rsp
0x18005a61f  sub     rsp, 80h
0x18005a626  mov     rax, cs:__security_cookie
0x18005a62d  xor     rax, rsp
0x18005a630  mov     [rbp+var_8], rax
0x18005a634  mov     rax, [rbp+arg_28]
0x18005a638  mov     r12d, r8d
0x18005a63b  mov     r13, [rbp+pSid1]
0x18005a63f  lea     r8, [rbp+pDacl]; pDacl
0x18005a643  mov     [rbp+var_28], rax
0x18005a647  xor     ebx, ebx
0x18005a649  mov     rax, [rbp+arg_30]
0x18005a64d  mov     [rbp+var_20], rax
0x18005a651  xor     eax, eax
0x18005a653  mov     [rbp+AccessMask], r9d
0x18005a657  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18005a65b  mov     [rbp+var_30], edx
0x18005a65e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18005a662  mov     [rbp+pAclInformation], rax
0x18005a666  mov     [rbp+var_10], eax
0x18005a669  mov     [rbp+var_44], 0
0x18005a670  mov     [rbp+pDacl], 0
0x18005a678  mov     [rbp+bDaclPresent], 0
0x18005a67f  mov     [rbp+bDaclDefaulted], 0
0x18005a686  call    cs:__imp_GetSecurityDescriptorDacl
0x18005a68c  test    eax, eax
0x18005a68e  jz      loc_18005A744
0x18005a694  mov     rcx, [rbp+pDacl]; pAcl
0x18005a698  test    rcx, rcx
0x18005a69b  jz      loc_18005A79E
0x18005a6a1  lea     r9d, [rbx+2]; dwAclInformationClass
0x18005a6a5  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18005a6a9  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18005a6ad  call    cs:__imp_GetAclInformation
0x18005a6b3  test    eax, eax
0x18005a6b5  jz      loc_18005A744
0x18005a6bb  xor     r15d, r15d
0x18005a6be  xor     r14d, r14d
0x18005a6c1  xor     esi, esi
0x18005a6c3  lea     edi, [rbx+1]
0x18005a6c6  cmp     esi, dword ptr [rbp+pAclInformation]
0x18005a6c9  jnb     loc_18005A752
0x18005a6cf  mov     rcx, [rbp+pDacl]; pAcl
0x18005a6d3  lea     r8, [rbp+pAce]; pAce
0x18005a6d7  mov     edx, esi; dwAceIndex
0x18005a6d9  mov     [rbp+pAce], rbx
0x18005a6dd  call    cs:__imp_GetAce
0x18005a6e3  test    eax, eax
0x18005a6e5  jz      short loc_18005A744
0x18005a6e7  mov     rax, [rbp+pAce]
0x18005a6eb  cmp     [rax], bl
0x18005a6ed  jnz     loc_18005A7AF
0x18005a6f3  lea     rdx, [rax+8]; pSid2
0x18005a6f7  mov     rcx, r13; pSid1
0x18005a6fa  call    cs:__imp_EqualSid
0x18005a700  test    eax, eax
0x18005a702  jz      loc_18005A7AB
0x18005a708  mov     [rbp+var_44], edi
0x18005a70b  mov     eax, [rbp+var_44]
0x18005a70e  mov     rcx, [rbp+var_28]
0x18005a712  mov     [rcx], eax
0x18005a714  mov     rax, [rbp+var_20]
0x18005a718  mov     [rax], rbx
0x18005a71b  mov     eax, edi
0x18005a71d  mov     rcx, [rbp+var_8]
0x18005a721  xor     rcx, rsp; StackCookie
0x18005a724  call    __security_check_cookie
0x18005a729  mov     rbx, [rsp+80h+arg_8]
0x18005a731  add     rsp, 80h
0x18005a738  pop     r15
0x18005a73a  pop     r14
0x18005a73c  pop     r13
0x18005a73e  pop     r12
0x18005a740  pop     rdi
0x18005a741  pop     rsi
0x18005a742  pop     rbp
0x18005a743  retn
0x18005a744  mov     rcx, rbx; hMem
0x18005a747  xor     edi, edi
0x18005a749  call    PkiDefaultCryptFree
0x18005a74e  xor     ebx, ebx
0x18005a750  jmp     short loc_18005A70B
0x18005a752  cmp     [rbp+var_30], ebx
0x18005a755  jnz     short loc_18005A70B
0x18005a757  mov     rcx, r13; pSid
0x18005a75a  call    cs:__imp_GetLengthSid
0x18005a760  mov     esi, dword ptr [rbp+pAclInformation+4]
0x18005a763  add     esi, 8
0x18005a766  add     esi, eax
0x18005a768  mov     ecx, esi; uBytes
0x18005a76a  call    PkiZeroAlloc
0x18005a76f  mov     rbx, rax
0x18005a772  test    rax, rax
0x18005a775  jz      short loc_18005A744
0x18005a777  mov     r8d, 2; dwAclRevision
0x18005a77d  mov     edx, esi; nAclLength
0x18005a77f  mov     rcx, rax; pAcl
0x18005a782  call    cs:__imp_InitializeAcl
0x18005a788  test    eax, eax
0x18005a78a  jz      short loc_18005A744
0x18005a78c  test    r15d, r15d
0x18005a78f  jnz     loc_180119048
0x18005a795  and     r12d, 0FFFFFFEFh
0x18005a799  jmp     loc_180119048
0x18005a79e  mov     ecx, 538h; dwErrCode
0x18005a7a3  call    cs:__imp_SetLastError
0x18005a7a9  jmp     short loc_18005A744
0x18005a7ab  mov     rax, [rbp+pAce]
0x18005a7af  test    byte ptr [rax+1], 10h
0x18005a7b3  cmovnz  r15d, edi
0x18005a7b7  cmp     [rax], dil
0x18005a7ba  cmovz   r14d, edi
0x18005a7be  add     esi, edi
0x18005a7c0  jmp     loc_18005A6C6
0x180119048  mov     r15d, [rbp+AccessMask]
0x18011904c  test    r14d, r14d
0x18011904f  jnz     short loc_180119071
0x180119051  mov     r9d, r15d; AccessMask
0x180119054  mov     [rsp+80h+pSid], r13; pSid
0x180119059  mov     r8d, r12d; AceFlags
0x18011905c  lea     edx, [r14+2]; dwAceRevision
0x180119060  mov     rcx, rbx; pAcl
0x180119063  call    cs:__imp_AddAccessAllowedAceEx
0x180119069  test    eax, eax
0x18011906b  jz      loc_18005A744
0x180119071  xor     esi, esi
0x180119073  cmp     esi, dword ptr [rbp+pAclInformation]
0x180119076  jnb     short loc_1801190C3
0x180119078  mov     rcx, [rbp+pDacl]; pAcl
0x18011907c  lea     r8, [rbp+pAce]; pAce
0x180119080  mov     edx, esi; dwAceIndex
0x180119082  mov     [rbp+pAce], 0
0x18011908a  call    cs:__imp_GetAce
0x180119090  test    eax, eax
0x180119092  jz      loc_18005A744
0x180119098  mov     r9, [rbp+pAce]; pAceList
0x18011909c  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1801190a0  mov     edx, 2; dwAceRevision
0x1801190a5  mov     rcx, rbx; pAcl
0x1801190a8  movzx   eax, word ptr [r9+2]
0x1801190ad  mov     dword ptr [rsp+80h+pSid], eax; nAceListLength
0x1801190b1  call    cs:__imp_AddAce
0x1801190b7  test    eax, eax
0x1801190b9  jz      loc_18005A744
0x1801190bf  add     esi, edi
0x1801190c1  jmp     short loc_180119073
0x1801190c3  test    r14d, r14d
0x1801190c6  jz      loc_18005A70B
0x1801190cc  mov     r9d, r15d; AccessMask
0x1801190cf  mov     [rsp+80h+pSid], r13; pSid
0x1801190d4  mov     r8d, r12d; AceFlags
0x1801190d7  mov     edx, 2; dwAceRevision
0x1801190dc  mov     rcx, rbx; pAcl
0x1801190df  call    cs:__imp_AddAccessAllowedAceEx
0x1801190e5  test    eax, eax
0x1801190e7  jnz     loc_18005A70B
0x1801190ed  jmp     loc_18005A744
```
