# IsProtectedSmartCardRootKey

- ea: `0x1800dfe68`
- end: `0x1800e003b`
- name: `IsProtectedSmartCardRootKey`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059d6c`

## callees

- `0x180028d60`
- `0x1800599a8`
- `0x1800bec20`
- `0x1800df0a0`
- `0x1800dfe68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e0008`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800dff73`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800dff73`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800dff25`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800dff25`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dff08`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dffb1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dffd4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dfff2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dff08`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dffb1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dffd4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dfff2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800dfee6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800dfee6`

## pseudocode

```c
__int64 __fastcall IsProtectedSmartCardRootKey(HKEY a1)
{
  __int64 v1; // rcx
  void *SecurityDescriptor; // rsi
  struct _ACL *v3; // rcx
  __int64 v4; // rbx
  unsigned int v5; // edi
  _BYTE *v6; // rcx
  DWORD v7; // ecx
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-50h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+24h] [rbp-4Ch] BYREF
  WINBOOL bDaclDefaulted; // [rsp+28h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-40h] BYREF
  PSID pOwner; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  __int128 v15; // [rsp+48h] [rbp-28h]
  __int64 v16; // [rsp+58h] [rbp-18h]

  pOwner = 0;
  bOwnerDefaulted = 0;
  v15 = 0;
  v16 = 0;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  SecurityDescriptor = (void *)AllocAndGetSecurityDescriptor(a1);
  if ( !SecurityDescriptor
    || !(unsigned int)GetPredefinedSids(v1)
    || !GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    goto LABEL_25;
  }
  if ( !pOwner || !EqualSid(pOwner, ::pOwner) )
  {
    v7 = 1307;
    goto LABEL_24;
  }
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
LABEL_25:
    v5 = 0;
    goto LABEL_26;
  }
  if ( !bDaclPresent )
    goto LABEL_22;
  v3 = pDacl;
  if ( !pDacl || pDacl->AceCount != 3 )
    goto LABEL_22;
  v4 = 0;
  v5 = 1;
  while ( (unsigned int)v4 < 3 )
  {
    pAce = 0;
    if ( !GetAce(v3, v4, &pAce) )
      goto LABEL_22;
    v6 = pAce;
    *((_QWORD *)&v15 + v4) = pAce;
    if ( *v6 || v6[1] != 2 )
      goto LABEL_22;
    v3 = pDacl;
    v4 = (unsigned int)(v4 + 1);
  }
  if ( *(_DWORD *)(v15 + 4) != 983103
    || !EqualSid(pSid1, (PSID)(v15 + 8))
    || *(_DWORD *)(*((_QWORD *)&v15 + 1) + 4LL) != 131097
    || !EqualSid(qword_18015D628, (PSID)(*((_QWORD *)&v15 + 1) + 8LL))
    || *(_DWORD *)(v16 + 4) != 131097
    || !EqualSid(pSid, (PSID)(v16 + 8)) )
  {
LABEL_22:
    v7 = 1336;
LABEL_24:
    SetLastError(v7);
    goto LABEL_25;
  }
LABEL_26:
  PkiDefaultCryptFree(SecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x1800dfe68  mov     [rsp-18h+arg_8], rbx
0x1800dfe6d  mov     [rsp-18h+arg_10], rsi
0x1800dfe72  push    rbp
0x1800dfe73  push    rdi
0x1800dfe74  push    r15
0x1800dfe76  mov     rbp, rsp
0x1800dfe79  sub     rsp, 70h
0x1800dfe7d  mov     rax, cs:__security_cookie
0x1800dfe84  xor     rax, rsp
0x1800dfe87  mov     [rbp+var_10], rax
0x1800dfe8b  xorps   xmm0, xmm0
0x1800dfe8e  mov     [rbp+pOwner], 0
0x1800dfe96  xor     eax, eax
0x1800dfe98  mov     [rbp+bOwnerDefaulted], 0
0x1800dfe9f  movups  [rbp+var_28], xmm0
0x1800dfea3  mov     [rbp+var_18], rax
0x1800dfea7  mov     [rbp+bDaclPresent], 0
0x1800dfeae  mov     [rbp+pDacl], 0
0x1800dfeb6  mov     [rbp+bDaclDefaulted], 0
0x1800dfebd  call    AllocAndGetSecurityDescriptor
0x1800dfec2  mov     rsi, rax
0x1800dfec5  test    rax, rax
0x1800dfec8  jz      loc_1800E000E
0x1800dfece  call    GetPredefinedSids
0x1800dfed3  test    eax, eax
0x1800dfed5  jz      loc_1800E000E
0x1800dfedb  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800dfedf  mov     rcx, rsi; pSecurityDescriptor
0x1800dfee2  lea     rdx, [rbp+pOwner]; pOwner
0x1800dfee6  call    cs:__imp_GetSecurityDescriptorOwner
0x1800dfeec  test    eax, eax
0x1800dfeee  jz      loc_1800E000E
0x1800dfef4  mov     rcx, [rbp+pOwner]; pSid1
0x1800dfef8  test    rcx, rcx
0x1800dfefb  jz      loc_1800E0003
0x1800dff01  mov     rdx, cs:pOwner; pSid2
0x1800dff08  call    cs:__imp_EqualSid
0x1800dff0e  test    eax, eax
0x1800dff10  jz      loc_1800E0003
0x1800dff16  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800dff1a  mov     rcx, rsi; pSecurityDescriptor
0x1800dff1d  lea     r8, [rbp+pDacl]; pDacl
0x1800dff21  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800dff25  call    cs:__imp_GetSecurityDescriptorDacl
0x1800dff2b  test    eax, eax
0x1800dff2d  jz      loc_1800E000E
0x1800dff33  cmp     [rbp+bDaclPresent], 0
0x1800dff37  jz      loc_1800DFFFC
0x1800dff3d  mov     rcx, [rbp+pDacl]; pAcl
0x1800dff41  test    rcx, rcx
0x1800dff44  jz      loc_1800DFFFC
0x1800dff4a  mov     r15d, 3
0x1800dff50  cmp     r15w, [rcx+4]
0x1800dff55  jnz     loc_1800DFFFC
0x1800dff5b  xor     ebx, ebx
0x1800dff5d  lea     edi, [rbx+1]
0x1800dff60  cmp     ebx, r15d
0x1800dff63  jnb     short loc_1800DFF99
0x1800dff65  lea     r8, [rbp+pAce]; pAce
0x1800dff69  mov     [rbp+pAce], 0
0x1800dff71  mov     edx, ebx; dwAceIndex
0x1800dff73  call    cs:__imp_GetAce
0x1800dff79  test    eax, eax
0x1800dff7b  jz      short loc_1800DFFFC
0x1800dff7d  mov     rcx, [rbp+pAce]
0x1800dff81  mov     qword ptr [rbp+rbx*8+var_28], rcx
0x1800dff86  cmp     byte ptr [rcx], 0
0x1800dff89  jnz     short loc_1800DFFFC
0x1800dff8b  cmp     byte ptr [rcx+1], 2
0x1800dff8f  jnz     short loc_1800DFFFC
0x1800dff91  mov     rcx, [rbp+pDacl]
0x1800dff95  add     ebx, edi
0x1800dff97  jmp     short loc_1800DFF60
0x1800dff99  mov     rdx, qword ptr [rbp+var_28]
0x1800dff9d  cmp     dword ptr [rdx+4], 0F003Fh
0x1800dffa4  jnz     short loc_1800DFFFC
0x1800dffa6  mov     rcx, cs:pSid1; pSid1
0x1800dffad  add     rdx, 8; pSid2
0x1800dffb1  call    cs:__imp_EqualSid
0x1800dffb7  test    eax, eax
0x1800dffb9  jz      short loc_1800DFFFC
0x1800dffbb  mov     rdx, qword ptr [rbp+var_28+8]
0x1800dffbf  mov     ebx, 20019h
0x1800dffc4  cmp     [rdx+4], ebx
0x1800dffc7  jnz     short loc_1800DFFFC
0x1800dffc9  mov     rcx, cs:qword_18015D628; pSid1
0x1800dffd0  add     rdx, 8; pSid2
0x1800dffd4  call    cs:__imp_EqualSid
0x1800dffda  test    eax, eax
0x1800dffdc  jz      short loc_1800DFFFC
0x1800dffde  mov     rdx, [rbp+var_18]
0x1800dffe2  cmp     [rdx+4], ebx
0x1800dffe5  jnz     short loc_1800DFFFC
0x1800dffe7  mov     rcx, cs:pSid; pSid1
0x1800dffee  add     rdx, 8; pSid2
0x1800dfff2  call    cs:__imp_EqualSid
0x1800dfff8  test    eax, eax
0x1800dfffa  jnz     short loc_1800E0010
0x1800dfffc  mov     ecx, 538h
0x1800e0001  jmp     short loc_1800E0008
0x1800e0003  mov     ecx, 51Bh; dwErrCode
0x1800e0008  call    cs:__imp_SetLastError
0x1800e000e  xor     edi, edi
0x1800e0010  mov     rcx, rsi; hMem
0x1800e0013  call    PkiDefaultCryptFree
0x1800e0018  mov     eax, edi
0x1800e001a  mov     rcx, [rbp+var_10]
0x1800e001e  xor     rcx, rsp; StackCookie
0x1800e0021  call    __security_check_cookie
0x1800e0026  lea     r11, [rsp+70h+var_s0]
0x1800e002b  mov     rbx, [r11+28h]
0x1800e002f  mov     rsi, [r11+30h]
0x1800e0033  mov     rsp, r11
0x1800e0036  pop     r15
0x1800e0038  pop     rdi
0x1800e0039  pop     rbp
0x1800e003a  retn
```
