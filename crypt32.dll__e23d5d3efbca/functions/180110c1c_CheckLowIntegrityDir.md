# _CheckLowIntegrityDir

- ea: `0x180110c1c`
- end: `0x180110e16`
- name: `_CheckLowIntegrityDir`
- size: `506`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180110fbc`
- `0x1801111b8`

## callees

- `0x1800bec20`
- `0x180110c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110db6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180110de3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180110de3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110dd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180110c7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180110c7e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180110ccd`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180110ccd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180110d23`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180110d23`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180110ca8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180110ca8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180110d7f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180110d7f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180110dc8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180110dc8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180110d95`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180110d95`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180110cf0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180110cf0`

## pseudocode

```c
__int64 __fastcall CheckLowIntegrityDir(LPCWSTR lpFileName, int *a2)
{
  DWORD v2; // esi
  DWORD LastError; // r15d
  int v6; // r12d
  HLOCAL v7; // rdi
  HLOCAL v8; // rax
  struct _ACL *v9; // rcx
  DWORD AceCount; // r14d
  LPVOID v11; // rax
  unsigned int v12; // ebx
  DWORD nLengthNeeded; // [rsp+60h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+68h] [rbp-11h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+70h] [rbp-9h] BYREF
  WINBOOL bSaclPresent; // [rsp+74h] [rbp-5h] BYREF
  PACL pSacl; // [rsp+78h] [rbp-1h] BYREF
  PSID pSid1; // [rsp+80h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF

  v2 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  pSacl = 0;
  pAce = 0;
  bSaclPresent = 0;
  LastError = 0;
  bSaclDefaulted = 0;
  v6 = 0;
  nLengthNeeded = 1024;
  v7 = LocalAlloc(0x40u, 0x400u);
  if ( !v7 )
    goto LABEL_20;
  while ( !GetFileSecurityW(lpFileName, 0x10u, v7, nLengthNeeded, &nLengthNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_20;
    v8 = LocalReAlloc(v7, nLengthNeeded, 0x40u);
    if ( !v8 )
      goto LABEL_20;
    v7 = v8;
  }
  if ( !GetSecurityDescriptorSacl(v7, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_20;
  v9 = pSacl;
  AceCount = 0;
  if ( pSacl )
    AceCount = pSacl->AceCount;
  v11 = pAce;
  v12 = 1;
  while ( v2 < AceCount )
  {
    if ( !GetAce(v9, v2, &pAce) )
      goto LABEL_20;
    v11 = pAce;
    if ( *(_BYTE *)pAce == 17 )
      break;
    v9 = pSacl;
    v11 = 0;
    pAce = 0;
    ++v2;
  }
  if ( v11 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      if ( EqualSid(pSid1, (char *)pAce + 8) && (*((_BYTE *)pAce + 1) & 3) == 3 )
        v6 = 1;
      goto LABEL_21;
    }
LABEL_20:
    v12 = 0;
    LastError = GetLastError();
  }
LABEL_21:
  if ( pSid1 )
    FreeSid(pSid1);
  if ( v7 )
    LocalFree(v7);
  if ( !v12 )
    SetLastError(LastError);
  *a2 = v6;
  return v12;
}

```

## disassembly

```asm
0x180110c1c  mov     [rsp-8+arg_10], rbx
0x180110c21  push    rbp
0x180110c22  push    rsi
0x180110c23  push    rdi
0x180110c24  push    r12
0x180110c26  push    r13
0x180110c28  push    r14
0x180110c2a  push    r15
0x180110c2c  lea     rbp, [rsp-27h]
0x180110c31  sub     rsp, 0A0h
0x180110c38  mov     rax, cs:__security_cookie
0x180110c3f  xor     rax, rsp
0x180110c42  mov     [rbp+57h+var_40], rax
0x180110c46  xor     esi, esi
0x180110c48  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x180110c4e  mov     r13, rdx
0x180110c51  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180110c54  mov     rbx, rcx
0x180110c57  mov     [rbp+57h+pSid1], rsi
0x180110c5b  mov     edx, 400h; uBytes
0x180110c60  mov     [rbp+57h+pSacl], rsi
0x180110c64  lea     r14d, [rsi+40h]
0x180110c68  mov     [rbp+57h+pAce], rsi
0x180110c6c  mov     ecx, r14d; uFlags
0x180110c6f  mov     [rbp+57h+bSaclPresent], esi
0x180110c72  mov     r15d, esi
0x180110c75  mov     [rbp+57h+bSaclDefaulted], esi
0x180110c78  mov     r12d, esi
0x180110c7b  mov     [rbp+57h+nLengthNeeded], edx
0x180110c7e  call    cs:__imp_LocalAlloc
0x180110c84  mov     rdi, rax
0x180110c87  test    rax, rax
0x180110c8a  jz      loc_180110DB4
0x180110c90  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180110c94  lea     rax, [rbp+57h+nLengthNeeded]
0x180110c98  mov     r8, rdi; pSecurityDescriptor
0x180110c9b  mov     [rsp+0D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180110ca0  mov     edx, 10h; RequestedInformation
0x180110ca5  mov     rcx, rbx; lpFileName
0x180110ca8  call    cs:__imp_GetFileSecurityW
0x180110cae  test    eax, eax
0x180110cb0  jnz     short loc_180110CE1
0x180110cb2  call    cs:__imp_GetLastError
0x180110cb8  mov     r15d, eax
0x180110cbb  cmp     eax, 7Ah ; 'z'
0x180110cbe  jnz     loc_180110DB4
0x180110cc4  mov     edx, [rbp+57h+nLengthNeeded]; uBytes
0x180110cc7  mov     r8d, r14d; uFlags
0x180110cca  mov     rcx, rdi; hMem
0x180110ccd  call    cs:__imp_LocalReAlloc
0x180110cd3  test    rax, rax
0x180110cd6  jz      loc_180110DB4
0x180110cdc  mov     rdi, rax
0x180110cdf  jmp     short loc_180110C90
0x180110ce1  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180110ce5  mov     rcx, rdi; pSecurityDescriptor
0x180110ce8  lea     r8, [rbp+57h+pSacl]; pSacl
0x180110cec  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180110cf0  call    cs:__imp_GetSecurityDescriptorSacl
0x180110cf6  test    eax, eax
0x180110cf8  jz      loc_180110DB4
0x180110cfe  mov     rcx, [rbp+57h+pSacl]; pAcl
0x180110d02  mov     r14d, esi
0x180110d05  test    rcx, rcx
0x180110d08  jz      short loc_180110D0F
0x180110d0a  movzx   r14d, word ptr [rcx+4]
0x180110d0f  mov     rax, [rbp+57h+pAce]
0x180110d13  mov     ebx, 1
0x180110d18  cmp     esi, r14d
0x180110d1b  jnb     short loc_180110D48
0x180110d1d  lea     r8, [rbp+57h+pAce]; pAce
0x180110d21  mov     edx, esi; dwAceIndex
0x180110d23  call    cs:__imp_GetAce
0x180110d29  test    eax, eax
0x180110d2b  jz      loc_180110DB2
0x180110d31  mov     rax, [rbp+57h+pAce]
0x180110d35  cmp     byte ptr [rax], 11h
0x180110d38  jz      short loc_180110D48
0x180110d3a  mov     rcx, [rbp+57h+pSacl]
0x180110d3e  xor     eax, eax
0x180110d40  mov     [rbp+57h+pAce], rax
0x180110d44  add     esi, ebx
0x180110d46  jmp     short loc_180110D18
0x180110d48  xor     esi, esi
0x180110d4a  test    rax, rax
0x180110d4d  jz      short loc_180110DBF
0x180110d4f  lea     rax, [rbp+57h+pSid1]
0x180110d53  xor     r9d, r9d; nSubAuthority1
0x180110d56  mov     [rsp+0D0h+pSid], rax; pSid
0x180110d5b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180110d5f  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x180110d63  mov     r8d, 1000h; nSubAuthority0
0x180110d69  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x180110d6d  mov     dl, bl; nSubAuthorityCount
0x180110d6f  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x180110d73  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x180110d77  mov     [rsp+0D0h+nSubAuthority3], esi; nSubAuthority3
0x180110d7b  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], esi; nSubAuthority2
0x180110d7f  call    cs:__imp_AllocateAndInitializeSid
0x180110d85  test    eax, eax
0x180110d87  jz      short loc_180110DB4
0x180110d89  mov     rdx, [rbp+57h+pAce]
0x180110d8d  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180110d91  add     rdx, 8; pSid2
0x180110d95  call    cs:__imp_EqualSid
0x180110d9b  test    eax, eax
0x180110d9d  jz      short loc_180110DBF
0x180110d9f  mov     rax, [rbp+57h+pAce]
0x180110da3  mov     cl, [rax+1]
0x180110da6  and     cl, 3
0x180110da9  cmp     cl, 3
0x180110dac  cmovz   r12d, ebx
0x180110db0  jmp     short loc_180110DBF
0x180110db2  xor     esi, esi
0x180110db4  mov     ebx, esi
0x180110db6  call    cs:__imp_GetLastError
0x180110dbc  mov     r15d, eax
0x180110dbf  mov     rcx, [rbp+57h+pSid1]; pSid
0x180110dc3  test    rcx, rcx
0x180110dc6  jz      short loc_180110DCE
0x180110dc8  call    cs:__imp_FreeSid
0x180110dce  test    rdi, rdi
0x180110dd1  jz      short loc_180110DDC
0x180110dd3  mov     rcx, rdi; hMem
0x180110dd6  call    cs:__imp_LocalFree
0x180110ddc  test    ebx, ebx
0x180110dde  jnz     short loc_180110DE9
0x180110de0  mov     ecx, r15d; dwErrCode
0x180110de3  call    cs:__imp_SetLastError
0x180110de9  mov     [r13+0], r12d
0x180110ded  mov     eax, ebx
0x180110def  mov     rcx, [rbp+57h+var_40]
0x180110df3  xor     rcx, rsp; StackCookie
0x180110df6  call    __security_check_cookie
0x180110dfb  mov     rbx, [rsp+0D0h+arg_10]
0x180110e03  add     rsp, 0A0h
0x180110e0a  pop     r15
0x180110e0c  pop     r14
0x180110e0e  pop     r13
0x180110e10  pop     r12
0x180110e12  pop     rdi
0x180110e13  pop     rsi
0x180110e14  pop     rbp
0x180110e15  retn
```
