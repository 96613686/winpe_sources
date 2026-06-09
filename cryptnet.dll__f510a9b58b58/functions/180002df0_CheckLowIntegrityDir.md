# _CheckLowIntegrityDir

- ea: `0x180002df0`
- end: `0x180003019`
- name: `_CheckLowIntegrityDir`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003170`

## callees

- `0x180002df0`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003011`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fcf`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180002fe9`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180002fe9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f8e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002e88`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180002e88`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180002ea5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180002ea5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180002ed4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180002ed4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002f4a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002f4a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180002f80`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180002f80`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180002f30`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180002f30`

## pseudocode

```c
__int64 __fastcall CheckLowIntegrityDir(LPCWSTR lpFileName, int *a2)
{
  DWORD LastError; // r12d
  int v5; // r14d
  HLOCAL v6; // rdi
  struct _ACL *v7; // rcx
  DWORD AceCount; // ebx
  LPVOID v9; // rax
  DWORD i; // esi
  unsigned int v11; // ebx
  __int64 result; // rax
  HLOCAL v13; // rax
  DWORD nLengthNeeded; // [rsp+68h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-11h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+78h] [rbp-9h] BYREF
  WINBOOL bSaclPresent; // [rsp+7Ch] [rbp-5h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-1h] BYREF
  PSID pSid; // [rsp+88h] [rbp+7h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  LastError = 0;
  pSid = 0;
  v5 = 0;
  pSacl = 0;
  pAce = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  nLengthNeeded = 1024;
  v6 = LocalAlloc(0x40u, 0x400u);
  if ( !v6 )
    goto LABEL_22;
  while ( !GetFileSecurityW(lpFileName, 0x10u, v6, nLengthNeeded, &nLengthNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_22;
    v13 = LocalReAlloc(v6, nLengthNeeded, 0x40u);
    if ( !v13 )
      goto LABEL_22;
    v6 = v13;
  }
  if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_22;
  v7 = pSacl;
  AceCount = 0;
  if ( pSacl )
    AceCount = pSacl->AceCount;
  v9 = pAce;
  for ( i = 0; i < AceCount; ++i )
  {
    if ( !GetAce(v7, i, &pAce) )
      goto LABEL_22;
    v9 = pAce;
    if ( *(_BYTE *)pAce == 17 )
      break;
    v7 = pSacl;
    v9 = 0;
    pAce = 0;
  }
  v11 = 1;
  if ( v9 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( EqualSid(pSid, (char *)pAce + 8) && (*((_BYTE *)pAce + 1) & 3) == 3 )
        v5 = 1;
      goto LABEL_15;
    }
LABEL_22:
    v11 = 0;
    LastError = GetLastError();
  }
LABEL_15:
  if ( pSid )
    FreeSid(pSid);
  if ( v6 )
    LocalFree(v6);
  if ( !v11 )
    SetLastError(LastError);
  result = v11;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180002df0  mov     r11, rsp
0x180002df3  push    rbp
0x180002df4  push    rbx
0x180002df5  push    r12
0x180002df7  push    r14
0x180002df9  push    r15
0x180002dfb  lea     rbp, [r11-5Fh]
0x180002dff  sub     rsp, 0B0h
0x180002e06  mov     rax, cs:__security_cookie
0x180002e0d  xor     rax, rsp
0x180002e10  mov     [rbp+57h+var_40], rax
0x180002e14  mov     [r11+18h], rsi
0x180002e18  mov     r15, rdx
0x180002e1b  mov     [r11-30h], rdi
0x180002e1f  mov     rbx, rcx
0x180002e22  mov     [r11-38h], r13
0x180002e26  mov     edx, 400h; uBytes
0x180002e2b  xor     r13d, r13d
0x180002e2e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x180002e34  mov     ecx, 40h ; '@'; uFlags
0x180002e39  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180002e3d  mov     r12d, r13d
0x180002e40  mov     [rbp+57h+pSid], r13
0x180002e44  mov     r14d, r13d
0x180002e47  mov     [rbp+57h+pSacl], r13
0x180002e4b  mov     [rbp+57h+pAce], r13
0x180002e4f  mov     [rbp+57h+bSaclPresent], r13d
0x180002e53  mov     [rbp+57h+bSaclDefaulted], r13d
0x180002e57  mov     [rbp+57h+nLengthNeeded], 400h
0x180002e5e  call    cs:__imp_LocalAlloc
0x180002e64  mov     rdi, rax
0x180002e67  test    rax, rax
0x180002e6a  jz      loc_180002FC1
0x180002e70  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180002e74  lea     rax, [rbp+57h+nLengthNeeded]
0x180002e78  mov     r8, rdi; pSecurityDescriptor
0x180002e7b  mov     [rsp+0D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180002e80  mov     edx, 10h; RequestedInformation
0x180002e85  mov     rcx, rbx; lpFileName
0x180002e88  call    cs:__imp_GetFileSecurityW
0x180002e8e  test    eax, eax
0x180002e90  jz      loc_180002FCF
0x180002e96  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180002e9a  mov     rcx, rdi; pSecurityDescriptor
0x180002e9d  lea     r8, [rbp+57h+pSacl]; pSacl
0x180002ea1  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180002ea5  call    cs:__imp_GetSecurityDescriptorSacl
0x180002eab  test    eax, eax
0x180002ead  jz      loc_180002FC1
0x180002eb3  mov     rcx, [rbp+57h+pSacl]; pAcl
0x180002eb7  mov     ebx, r13d
0x180002eba  test    rcx, rcx
0x180002ebd  jz      short loc_180002EC3
0x180002ebf  movzx   ebx, word ptr [rcx+4]
0x180002ec3  mov     rax, [rbp+57h+pAce]
0x180002ec7  mov     esi, r13d
0x180002eca  cmp     esi, ebx
0x180002ecc  jnb     short loc_180002EEF
0x180002ece  lea     r8, [rbp+57h+pAce]; pAce
0x180002ed2  mov     edx, esi; dwAceIndex
0x180002ed4  call    cs:__imp_GetAce
0x180002eda  test    eax, eax
0x180002edc  jz      loc_180002FC1
0x180002ee2  mov     rax, [rbp+57h+pAce]
0x180002ee6  cmp     byte ptr [rax], 11h
0x180002ee9  jnz     loc_180002FFC
0x180002eef  mov     ebx, 1
0x180002ef4  test    rax, rax
0x180002ef7  jz      short loc_180002F67
0x180002ef9  lea     rax, [rbp+57h+pSid]
0x180002efd  xor     r9d, r9d; nSubAuthority1
0x180002f00  mov     [rsp+50h], rax; pSid
0x180002f05  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180002f09  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x180002f0e  mov     r8d, 1000h; nSubAuthority0
0x180002f14  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x180002f19  movzx   edx, bl; nSubAuthorityCount
0x180002f1c  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x180002f21  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180002f26  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180002f2b  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], r13d; nSubAuthority2
0x180002f30  call    cs:__imp_AllocateAndInitializeSid
0x180002f36  test    eax, eax
0x180002f38  jz      loc_180002FC1
0x180002f3e  mov     rdx, [rbp+57h+pAce]
0x180002f42  mov     rcx, [rbp+57h+pSid]; pSid1
0x180002f46  add     rdx, 8; pSid2
0x180002f4a  call    cs:__imp_EqualSid
0x180002f50  test    eax, eax
0x180002f52  jz      short loc_180002F67
0x180002f54  mov     rax, [rbp+57h+pAce]
0x180002f58  movzx   ecx, byte ptr [rax+1]
0x180002f5c  and     cl, 3
0x180002f5f  cmp     cl, 3
0x180002f62  jnz     short loc_180002F67
0x180002f64  mov     r14d, ebx
0x180002f67  mov     rcx, [rbp+57h+pSid]; pSid
0x180002f6b  mov     r13, [rsp+0D0h+var_30]
0x180002f73  mov     rsi, [rsp+0D0h+arg_10]
0x180002f7b  test    rcx, rcx
0x180002f7e  jz      short loc_180002F86
0x180002f80  call    cs:__imp_FreeSid
0x180002f86  test    rdi, rdi
0x180002f89  jz      short loc_180002F94
0x180002f8b  mov     rcx, rdi; hMem
0x180002f8e  call    cs:__imp_LocalFree
0x180002f94  mov     rdi, [rsp+0A8h]
0x180002f9c  test    ebx, ebx
0x180002f9e  jz      short loc_18000300E
0x180002fa0  mov     eax, ebx
0x180002fa2  mov     [r15], r14d
0x180002fa5  mov     rcx, [rbp+57h+var_40]
0x180002fa9  xor     rcx, rsp; StackCookie
0x180002fac  call    __security_check_cookie
0x180002fb1  add     rsp, 0B0h
0x180002fb8  pop     r15
0x180002fba  pop     r14
0x180002fbc  pop     r12
0x180002fbe  pop     rbx
0x180002fbf  pop     rbp
0x180002fc0  retn
0x180002fc1  mov     ebx, r13d
0x180002fc4  call    cs:__imp_GetLastError
0x180002fca  mov     r12d, eax
0x180002fcd  jmp     short loc_180002F67
0x180002fcf  call    cs:__imp_GetLastError
0x180002fd5  mov     r12d, eax
0x180002fd8  cmp     eax, 7Ah ; 'z'
0x180002fdb  jnz     short loc_180002FC1
0x180002fdd  mov     edx, [rbp+57h+nLengthNeeded]; uBytes
0x180002fe0  mov     r8d, 40h ; '@'; uFlags
0x180002fe6  mov     rcx, rdi; hMem
0x180002fe9  call    cs:__imp_LocalReAlloc
0x180002fef  test    rax, rax
0x180002ff2  jz      short loc_180002FC1
0x180002ff4  mov     rdi, rax
0x180002ff7  jmp     loc_180002E70
0x180002ffc  mov     rcx, [rbp+57h+pSacl]
0x180003000  mov     rax, r13
0x180003003  mov     [rbp+57h+pAce], rax
0x180003007  inc     esi
0x180003009  jmp     loc_180002ECA
0x18000300e  mov     ecx, r12d; dwErrCode
0x180003011  call    cs:__imp_SetLastError
0x180003017  jmp     short loc_180002FA0
```
