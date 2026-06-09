# SADatSetSecurity(void *)

- ea: `0x180019dac`
- end: `0x180019f2a`
- name: `?SADatSetSecurity@@YAKPEAX@Z`
- size: `382`
- prototype: `unsigned int __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800199e4`

## callees

- `0x180019dac`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019f0a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019f0a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019e26`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019efb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019efb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180019eaf`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180019eaf`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180019edb`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180019edb`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180019e65`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180019e65`

## pseudocode

```c
__int64 __fastcall SADatSetSecurity(HANDLE handle)
{
  DWORD LastError; // eax
  DWORD SecurityInfo; // ebx
  __int64 v4; // rcx
  _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  PACL NewAcl; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  PACL ppDacl; // [rsp+70h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+78h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  ppDacl = 0;
  NewAcl = 0;
  ppSecurityDescriptor = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
LABEL_8:
    SecurityInfo = LastError;
    goto LABEL_9;
  }
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
  if ( !SecurityInfo )
  {
    v4 = 48;
    p_pListOfExplicitEntries = &pListOfExplicitEntries;
    do
    {
      LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
      p_pListOfExplicitEntries = (_EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
      --v4;
    }
    while ( v4 );
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    SecurityInfo = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
    if ( !SecurityInfo )
    {
      LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
      goto LABEL_8;
    }
  }
LABEL_9:
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pSid )
    FreeSid(pSid);
  return SecurityInfo;
}

```

## disassembly

```asm
0x180019dac  push    rbp
0x180019dae  push    rbx
0x180019daf  push    rsi
0x180019db0  push    rdi
0x180019db1  lea     rbp, [rsp-3Fh]
0x180019db6  sub     rsp, 0C8h
0x180019dbd  mov     rax, cs:__security_cookie
0x180019dc4  xor     rax, rsp
0x180019dc7  mov     [rbp+57h+var_28], rax
0x180019dcb  xor     esi, esi
0x180019dcd  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180019dd3  xorps   xmm0, xmm0
0x180019dd6  mov     [rbp+57h+var_78], rsi
0x180019dda  lea     rax, [rbp+57h+var_78]
0x180019dde  mov     [rbp+57h+ppDacl], rsi
0x180019de2  mov     [rsp+0E0h+pSid], rax; pSid
0x180019de7  mov     rdi, rcx
0x180019dea  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x180019dee  lea     r8d, [rsi+0Bh]; nSubAuthority0
0x180019df2  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x180019df6  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180019dfa  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x180019dfe  xor     r9d, r9d; nSubAuthority1
0x180019e01  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x180019e05  mov     dl, 1; nSubAuthorityCount
0x180019e07  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x180019e0b  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x180019e0f  mov     [rbp+57h+NewAcl], rsi
0x180019e13  mov     [rbp+57h+ppSecurityDescriptor], rsi
0x180019e17  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180019e1b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180019e1e  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180019e22  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180019e26  call    cs:__imp_AllocateAndInitializeSid
0x180019e2c  test    eax, eax
0x180019e2e  jnz     short loc_180019E3B
0x180019e30  call    cs:__imp_GetLastError
0x180019e36  jmp     loc_180019EE1
0x180019e3b  xor     r9d, r9d; ppsidOwner
0x180019e3e  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x180019e42  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax; ppSecurityDescriptor
0x180019e47  mov     rcx, rdi; handle
0x180019e4a  lea     rax, [rbp+57h+ppDacl]
0x180019e4e  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; ppSacl
0x180019e53  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; ppDacl
0x180019e58  lea     edx, [r9+1]; ObjectType
0x180019e5c  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; ppsidGroup
0x180019e61  lea     r8d, [r9+4]; SecurityInfo
0x180019e65  call    cs:__imp_GetSecurityInfo
0x180019e6b  mov     ebx, eax
0x180019e6d  test    eax, eax
0x180019e6f  jnz     short loc_180019EE3
0x180019e71  lea     ecx, [rax+30h]
0x180019e74  lea     rax, [rbp+57h+pListOfExplicitEntries]
0x180019e78  mov     [rax], sil
0x180019e7b  inc     rax
0x180019e7e  sub     rcx, 1
0x180019e82  jnz     short loc_180019E78
0x180019e84  mov     rax, [rbp+57h+var_78]
0x180019e88  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180019e8c  mov     r8, [rbp+57h+ppDacl]; OldAcl
0x180019e90  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180019e94  mov     ecx, 1; cCountOfExplicitEntries
0x180019e99  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180019e9d  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180019ea4  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180019eac  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180019eaf  call    cs:__imp_SetEntriesInAclW
0x180019eb5  mov     ebx, eax
0x180019eb7  test    eax, eax
0x180019eb9  jnz     short loc_180019EE3
0x180019ebb  mov     rax, [rbp+57h+NewAcl]
0x180019ebf  lea     edx, [rbx+1]; ObjectType
0x180019ec2  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; pSacl
0x180019ec7  lea     r8d, [rbx+4]; SecurityInfo
0x180019ecb  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x180019ed0  xor     r9d, r9d; psidOwner
0x180019ed3  mov     rcx, rdi; handle
0x180019ed6  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; psidGroup
0x180019edb  call    cs:__imp_SetSecurityInfo
0x180019ee1  mov     ebx, eax
0x180019ee3  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180019ee7  test    rcx, rcx
0x180019eea  jz      short loc_180019EF2
0x180019eec  call    cs:__imp_LocalFree
0x180019ef2  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180019ef6  test    rcx, rcx
0x180019ef9  jz      short loc_180019F01
0x180019efb  call    cs:__imp_LocalFree
0x180019f01  mov     rcx, [rbp+57h+var_78]; pSid
0x180019f05  test    rcx, rcx
0x180019f08  jz      short loc_180019F10
0x180019f0a  call    cs:__imp_FreeSid
0x180019f10  mov     eax, ebx
0x180019f12  mov     rcx, [rbp+57h+var_28]
0x180019f16  xor     rcx, rsp; StackCookie
0x180019f19  call    __security_check_cookie
0x180019f1e  add     rsp, 0C8h
0x180019f25  pop     rdi
0x180019f26  pop     rsi
0x180019f27  pop     rbx
0x180019f28  pop     rbp
0x180019f29  retn
```
