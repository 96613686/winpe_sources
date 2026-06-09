# _CryptSetSidDaclAce

- ea: `0x180007994`
- end: `0x180007bd8`
- name: `_CryptSetSidDaclAce`
- size: `580`
- prototype: `__int64 __fastcall(void *, __int64, DWORD, __int64, PSID pSid1, int *, ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001100`
- `0x180004e70`

## callees

- `0x180005200`
- `0x180007994`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ac6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ac6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180007b63`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180007b63`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180007b1d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180007b89`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180007b1d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180007b89`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180007ae9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180007ae9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007ab1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007ab1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180007a68`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180007b40`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180007a68`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180007b40`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180007a3c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180007a3c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007a07`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007a07`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007a85`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007a85`

## pseudocode

```c
__int64 __fastcall CryptSetSidDaclAce(void *a1, __int64 a2, DWORD a3, __int64 a4, PSID pSid1, int *a6, ACL **a7)
{
  ACL *v8; // rbx
  DWORD v9; // ecx
  int v10; // r14d
  int v11; // r15d
  DWORD v12; // esi
  unsigned int v13; // edi
  _BYTE *v14; // rax
  DWORD LengthSid; // eax
  DWORD v16; // esi
  ACL *v17; // rax
  DWORD i; // esi
  LPVOID pAce; // [rsp+30h] [rbp-50h] BYREF
  int v21; // [rsp+38h] [rbp-48h]
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  BOOL bDaclDefaulted; // [rsp+48h] [rbp-38h] BYREF
  BOOL bDaclPresent; // [rsp+4Ch] [rbp-34h] BYREF
  int *v25; // [rsp+50h] [rbp-30h]
  ACL **v26; // [rsp+58h] [rbp-28h]
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v28; // [rsp+68h] [rbp-18h]

  v25 = a6;
  v26 = a7;
  v8 = 0;
  v21 = 0;
  pAclInformation = 0;
  v28 = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    goto LABEL_32;
  if ( !pDacl )
  {
    v9 = 1336;
LABEL_4:
    SetLastError(v9);
LABEL_32:
    v13 = 0;
    PkiFree(v8);
    v8 = 0;
    goto LABEL_33;
  }
  if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
    goto LABEL_32;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 1;
  while ( v12 < (unsigned int)pAclInformation )
  {
    pAce = 0;
    if ( !GetAce(pDacl, v12, &pAce) )
      goto LABEL_32;
    v14 = pAce;
    if ( !*(_BYTE *)pAce )
    {
      if ( EqualSid(pSid1, (char *)pAce + 8) )
      {
        v21 = 1;
        goto LABEL_33;
      }
      v14 = pAce;
    }
    if ( (v14[1] & 0x10) != 0 )
      v10 = 1;
    if ( *v14 == 1 )
      v11 = 1;
    ++v12;
  }
  LengthSid = GetLengthSid(pSid1);
  v16 = LengthSid + HIDWORD(pAclInformation) + 8;
  v17 = (ACL *)LocalAlloc(0x40u, v16);
  v8 = v17;
  if ( !v17 )
  {
    v9 = -2147024882;
    goto LABEL_4;
  }
  if ( !InitializeAcl(v17, v16, 2u) )
    goto LABEL_32;
  if ( !v10 )
    a3 &= ~0x10u;
  if ( !v11 && !AddAccessAllowedAceEx(v8, 2u, a3, 0x1200A9u, pSid1) )
    goto LABEL_32;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    pAce = 0;
    if ( !GetAce(pDacl, i, &pAce) || !AddAce(v8, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      goto LABEL_32;
  }
  if ( v11 && !AddAccessAllowedAceEx(v8, 2u, a3, 0x1200A9u, pSid1) )
    goto LABEL_32;
LABEL_33:
  *v25 = v21;
  *v26 = v8;
  return v13;
}

```

## disassembly

```asm
0x180007994  mov     [rsp-38h+arg_8], rbx
0x180007999  push    rbp
0x18000799a  push    rsi
0x18000799b  push    rdi
0x18000799c  push    r12
0x18000799e  push    r13
0x1800079a0  push    r14
0x1800079a2  push    r15
0x1800079a4  mov     rbp, rsp
0x1800079a7  sub     rsp, 80h
0x1800079ae  mov     rax, cs:__security_cookie
0x1800079b5  xor     rax, rsp
0x1800079b8  mov     [rbp+var_10], rax
0x1800079bc  mov     rax, [rbp+arg_28]
0x1800079c0  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800079c4  mov     r13, [rbp+pSid1]
0x1800079c8  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800079cc  mov     [rbp+var_30], rax
0x1800079d0  mov     r12d, r8d
0x1800079d3  mov     rax, [rbp+arg_30]
0x1800079d7  lea     r8, [rbp+pDacl]; pDacl
0x1800079db  mov     [rbp+var_28], rax
0x1800079df  xor     ebx, ebx
0x1800079e1  xor     eax, eax
0x1800079e3  mov     [rbp+var_48], 0
0x1800079ea  mov     [rbp+pAclInformation], rax
0x1800079ee  mov     [rbp+var_18], eax
0x1800079f1  mov     [rbp+pDacl], 0
0x1800079f9  mov     [rbp+bDaclPresent], 0
0x180007a00  mov     [rbp+bDaclDefaulted], 0
0x180007a07  call    cs:__imp_GetSecurityDescriptorDacl
0x180007a0d  test    eax, eax
0x180007a0f  jz      loc_180007B93
0x180007a15  mov     rcx, [rbp+pDacl]; pAcl
0x180007a19  test    rcx, rcx
0x180007a1c  jnz     short loc_180007A2E
0x180007a1e  mov     ecx, 538h; dwErrCode
0x180007a23  call    cs:__imp_SetLastError
0x180007a29  jmp     loc_180007B93
0x180007a2e  mov     r9d, 2; dwAclInformationClass
0x180007a34  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x180007a38  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180007a3c  call    cs:__imp_GetAclInformation
0x180007a42  test    eax, eax
0x180007a44  jz      loc_180007B93
0x180007a4a  xor     r14d, r14d
0x180007a4d  xor     r15d, r15d
0x180007a50  xor     esi, esi
0x180007a52  lea     edi, [rsi+1]
0x180007a55  cmp     esi, dword ptr [rbp+pAclInformation]
0x180007a58  jnb     short loc_180007AAE
0x180007a5a  mov     rcx, [rbp+pDacl]; pAcl
0x180007a5e  lea     r8, [rbp+pAce]; pAce
0x180007a62  mov     edx, esi; dwAceIndex
0x180007a64  mov     [rbp+pAce], rbx
0x180007a68  call    cs:__imp_GetAce
0x180007a6e  test    eax, eax
0x180007a70  jz      loc_180007B93
0x180007a76  mov     rax, [rbp+pAce]
0x180007a7a  cmp     [rax], bl
0x180007a7c  jnz     short loc_180007A93
0x180007a7e  lea     rdx, [rax+8]; pSid2
0x180007a82  mov     rcx, r13; pSid1
0x180007a85  call    cs:__imp_EqualSid
0x180007a8b  test    eax, eax
0x180007a8d  jnz     short loc_180007AA6
0x180007a8f  mov     rax, [rbp+pAce]
0x180007a93  test    byte ptr [rax+1], 10h
0x180007a97  cmovnz  r14d, edi
0x180007a9b  cmp     [rax], dil
0x180007a9e  cmovz   r15d, edi
0x180007aa2  add     esi, edi
0x180007aa4  jmp     short loc_180007A55
0x180007aa6  mov     [rbp+var_48], edi
0x180007aa9  jmp     loc_180007B9F
0x180007aae  mov     rcx, r13; pSid
0x180007ab1  call    cs:__imp_GetLengthSid
0x180007ab7  mov     esi, dword ptr [rbp+pAclInformation+4]
0x180007aba  mov     ecx, 40h ; '@'; uFlags
0x180007abf  add     esi, 8
0x180007ac2  add     esi, eax
0x180007ac4  mov     edx, esi; uBytes
0x180007ac6  call    cs:__imp_LocalAlloc
0x180007acc  mov     rbx, rax
0x180007acf  test    rax, rax
0x180007ad2  jnz     short loc_180007ADE
0x180007ad4  mov     ecx, 8007000Eh
0x180007ad9  jmp     loc_180007A23
0x180007ade  mov     r8d, 2; dwAclRevision
0x180007ae4  mov     edx, esi; nAclLength
0x180007ae6  mov     rcx, rbx; pAcl
0x180007ae9  call    cs:__imp_InitializeAcl
0x180007aef  test    eax, eax
0x180007af1  jz      loc_180007B93
0x180007af7  test    r14d, r14d
0x180007afa  jnz     short loc_180007B00
0x180007afc  and     r12d, 0FFFFFFEFh
0x180007b00  mov     r14d, 1200A9h
0x180007b06  test    r15d, r15d
0x180007b09  jnz     short loc_180007B27
0x180007b0b  mov     r9d, r14d; AccessMask
0x180007b0e  mov     [rsp+80h+pSid], r13; pSid
0x180007b13  mov     r8d, r12d; AceFlags
0x180007b16  lea     edx, [r15+2]; dwAceRevision
0x180007b1a  mov     rcx, rbx; pAcl
0x180007b1d  call    cs:__imp_AddAccessAllowedAceEx
0x180007b23  test    eax, eax
0x180007b25  jz      short loc_180007B93
0x180007b27  xor     esi, esi
0x180007b29  cmp     esi, dword ptr [rbp+pAclInformation]
0x180007b2c  jnb     short loc_180007B71
0x180007b2e  mov     rcx, [rbp+pDacl]; pAcl
0x180007b32  lea     r8, [rbp+pAce]; pAce
0x180007b36  mov     edx, esi; dwAceIndex
0x180007b38  mov     [rbp+pAce], 0
0x180007b40  call    cs:__imp_GetAce
0x180007b46  test    eax, eax
0x180007b48  jz      short loc_180007B93
0x180007b4a  mov     r9, [rbp+pAce]; pAceList
0x180007b4e  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180007b52  mov     edx, 2; dwAceRevision
0x180007b57  mov     rcx, rbx; pAcl
0x180007b5a  movzx   eax, word ptr [r9+2]
0x180007b5f  mov     dword ptr [rsp+80h+pSid], eax; nAceListLength
0x180007b63  call    cs:__imp_AddAce
0x180007b69  test    eax, eax
0x180007b6b  jz      short loc_180007B93
0x180007b6d  add     esi, edi
0x180007b6f  jmp     short loc_180007B29
0x180007b71  test    r15d, r15d
0x180007b74  jz      short loc_180007B9F
0x180007b76  mov     r9d, r14d; AccessMask
0x180007b79  mov     [rsp+80h+pSid], r13; pSid
0x180007b7e  mov     r8d, r12d; AceFlags
0x180007b81  mov     edx, 2; dwAceRevision
0x180007b86  mov     rcx, rbx; pAcl
0x180007b89  call    cs:__imp_AddAccessAllowedAceEx
0x180007b8f  test    eax, eax
0x180007b91  jnz     short loc_180007B9F
0x180007b93  mov     rcx, rbx; hMem
0x180007b96  xor     edi, edi
0x180007b98  call    PkiFree
0x180007b9d  xor     ebx, ebx
0x180007b9f  mov     eax, [rbp+var_48]
0x180007ba2  mov     rcx, [rbp+var_30]
0x180007ba6  mov     [rcx], eax
0x180007ba8  mov     rax, [rbp+var_28]
0x180007bac  mov     [rax], rbx
0x180007baf  mov     eax, edi
0x180007bb1  mov     rcx, [rbp+var_10]
0x180007bb5  xor     rcx, rsp; StackCookie
0x180007bb8  call    __security_check_cookie
0x180007bbd  mov     rbx, [rsp+80h+arg_8]
0x180007bc5  add     rsp, 80h
0x180007bcc  pop     r15
0x180007bce  pop     r14
0x180007bd0  pop     r13
0x180007bd2  pop     r12
0x180007bd4  pop     rdi
0x180007bd5  pop     rsi
0x180007bd6  pop     rbp
0x180007bd7  retn
```
