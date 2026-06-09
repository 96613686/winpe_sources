# GrantAccessToSpecifiedUsers(ushort const *,_TypeFolderAccessNeeded)

- ea: `0x1800f030c`
- end: `0x1800f05ce`
- name: `?GrantAccessToSpecifiedUsers@@YAJPEBGW4_TypeFolderAccessNeeded@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800ee320`

## callees

- `0x1800090c0`
- `0x1800f030c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f042b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f042b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0523`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f059e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f059e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f041b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f041b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f056c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0585`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f056c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0585`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800f0513`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800f0513`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800f04a0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800f04a0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800f0384`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800f0384`

## pseudocode

```c
__int64 __fastcall GrantAccessToSpecifiedUsers(WCHAR *a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  PACL NewAcl; // [rsp+60h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+68h] [rbp-1h] BYREF
  PSID pSid; // [rsp+70h] [rbp+7h] BYREF
  PACL OldAcl; // [rsp+78h] [rbp+Fh] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+47h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  OldAcl = 0;
  hMem = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  pSid = 0;
  NewAcl = 0;
  if ( GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v5 = 56;
LABEL_7:
      WPP_SF_d(v4[2], v5, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v3);
    }
  }
  else if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    pListOfExplicitEntries.grfAccessPermissions = 2;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl) )
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v5 = 60;
        goto LABEL_7;
      }
    }
    else if ( SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0) )
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v5 = 61;
        goto LABEL_7;
      }
    }
    else
    {
      v3 = 0;
    }
  }
  else
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v5 = 57;
      goto LABEL_7;
    }
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  if ( pSid )
    FreeSid(pSid);
  return v3;
}

```

## disassembly

```asm
0x1800f030c  mov     [rsp-8+arg_8], rbx
0x1800f0311  mov     [rsp-8+arg_10], rdi
0x1800f0316  push    rbp
0x1800f0317  lea     rbp, [rsp-57h]
0x1800f031c  sub     rsp, 0C0h
0x1800f0323  mov     rax, cs:__security_cookie
0x1800f032a  xor     rax, rsp
0x1800f032d  mov     [rbp+57h+var_8], rax
0x1800f0331  xor     edi, edi
0x1800f0333  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800f0339  xorps   xmm0, xmm0
0x1800f033c  mov     [rbp+57h+OldAcl], rdi
0x1800f0340  lea     rax, [rbp+57h+hMem]
0x1800f0344  mov     [rbp+57h+hMem], rdi
0x1800f0348  mov     [rsp+0C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800f034d  xor     r9d, r9d; ppsidOwner
0x1800f0350  lea     rax, [rbp+57h+OldAcl]
0x1800f0354  mov     [rsp+0C0h+ppSacl], rdi; ppSacl
0x1800f0359  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x1800f035e  lea     edx, [rdi+1]; ObjectType
0x1800f0361  lea     r8d, [rdi+4]; SecurityInfo
0x1800f0365  mov     [rsp+0C0h+ppsidGroup], rdi; ppsidGroup
0x1800f036a  mov     rbx, rcx
0x1800f036d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800f0370  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800f0374  mov     [rbp+57h+var_50], rdi
0x1800f0378  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800f037c  mov     [rbp+57h+NewAcl], rdi
0x1800f0380  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800f0384  call    cs:__imp_GetNamedSecurityInfoW
0x1800f038b  nop     dword ptr [rax+rax+00h]
0x1800f0390  test    eax, eax
0x1800f0392  jz      short loc_1800F03ED
0x1800f0394  call    cs:__imp_GetLastError
0x1800f039b  nop     dword ptr [rax+rax+00h]
0x1800f03a0  mov     ebx, eax
0x1800f03a2  test    eax, eax
0x1800f03a4  jle     short loc_1800F03AF
0x1800f03a6  movzx   ebx, ax
0x1800f03a9  or      ebx, 80070000h
0x1800f03af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f03b6  lea     rax, WPP_GLOBAL_Control
0x1800f03bd  cmp     rcx, rax
0x1800f03c0  jz      loc_1800F0563
0x1800f03c6  test    byte ptr [rcx+1Ch], 40h
0x1800f03ca  jz      loc_1800F0563
0x1800f03d0  mov     edx, 38h ; '8'
0x1800f03d5  mov     rcx, [rcx+10h]
0x1800f03d9  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f03e0  mov     r9d, ebx
0x1800f03e3  call    WPP_SF_d
0x1800f03e8  jmp     loc_1800F0563
0x1800f03ed  lea     rax, [rbp+57h+var_50]
0x1800f03f1  xor     r9d, r9d; nSubAuthority1
0x1800f03f4  mov     [rsp+0C0h+pSid], rax; pSid
0x1800f03f9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800f03fd  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x1800f0401  mov     dl, 1; nSubAuthorityCount
0x1800f0403  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x1800f0407  mov     dword ptr [rsp+0C0h+ppSecurityDescriptor], edi; nSubAuthority5
0x1800f040b  lea     r8d, [r9+0Bh]; nSubAuthority0
0x1800f040f  mov     dword ptr [rsp+0C0h+ppSacl], edi; nSubAuthority4
0x1800f0413  mov     dword ptr [rsp+0C0h+ppDacl], edi; nSubAuthority3
0x1800f0417  mov     dword ptr [rsp+0C0h+ppsidGroup], edi; nSubAuthority2
0x1800f041b  call    cs:__imp_AllocateAndInitializeSid
0x1800f0422  nop     dword ptr [rax+rax+00h]
0x1800f0427  test    eax, eax
0x1800f0429  jnz     short loc_1800F0471
0x1800f042b  call    cs:__imp_GetLastError
0x1800f0432  nop     dword ptr [rax+rax+00h]
0x1800f0437  mov     ebx, eax
0x1800f0439  test    eax, eax
0x1800f043b  jle     short loc_1800F0446
0x1800f043d  movzx   ebx, ax
0x1800f0440  or      ebx, 80070000h
0x1800f0446  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f044d  lea     rax, WPP_GLOBAL_Control
0x1800f0454  cmp     rcx, rax
0x1800f0457  jz      loc_1800F0563
0x1800f045d  test    byte ptr [rcx+1Ch], 40h
0x1800f0461  jz      loc_1800F0563
0x1800f0467  mov     edx, 39h ; '9'
0x1800f046c  jmp     loc_1800F03D5
0x1800f0471  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x1800f0475  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800f0479  mov     eax, 2
0x1800f047e  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800f0485  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], eax
0x1800f0488  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800f048c  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], rax
0x1800f0490  mov     ecx, 1; cCountOfExplicitEntries
0x1800f0495  mov     rax, [rbp+57h+var_50]
0x1800f0499  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800f049d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x1800f04a0  call    cs:__imp_SetEntriesInAclW
0x1800f04a7  nop     dword ptr [rax+rax+00h]
0x1800f04ac  test    eax, eax
0x1800f04ae  jz      short loc_1800F04F2
0x1800f04b0  call    cs:__imp_GetLastError
0x1800f04b7  nop     dword ptr [rax+rax+00h]
0x1800f04bc  mov     ebx, eax
0x1800f04be  test    eax, eax
0x1800f04c0  jle     short loc_1800F04CB
0x1800f04c2  movzx   ebx, ax
0x1800f04c5  or      ebx, 80070000h
0x1800f04cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f04d2  lea     rax, WPP_GLOBAL_Control
0x1800f04d9  cmp     rcx, rax
0x1800f04dc  jz      loc_1800F0563
0x1800f04e2  test    byte ptr [rcx+1Ch], 40h
0x1800f04e6  jz      short loc_1800F0563
0x1800f04e8  mov     edx, 3Ch ; '<'
0x1800f04ed  jmp     loc_1800F03D5
0x1800f04f2  mov     rax, [rbp+57h+NewAcl]
0x1800f04f6  xor     r9d, r9d; psidOwner
0x1800f04f9  mov     [rsp+0C0h+ppSacl], rdi; pSacl
0x1800f04fe  mov     rcx, rbx; pObjectName
0x1800f0501  mov     [rsp+0C0h+ppDacl], rax; pDacl
0x1800f0506  mov     [rsp+0C0h+ppsidGroup], rdi; psidGroup
0x1800f050b  lea     edx, [r9+1]; ObjectType
0x1800f050f  lea     r8d, [r9+4]; SecurityInfo
0x1800f0513  call    cs:__imp_SetNamedSecurityInfoW
0x1800f051a  nop     dword ptr [rax+rax+00h]
0x1800f051f  test    eax, eax
0x1800f0521  jz      short loc_1800F0561
0x1800f0523  call    cs:__imp_GetLastError
0x1800f052a  nop     dword ptr [rax+rax+00h]
0x1800f052f  mov     ebx, eax
0x1800f0531  test    eax, eax
0x1800f0533  jle     short loc_1800F053E
0x1800f0535  movzx   ebx, ax
0x1800f0538  or      ebx, 80070000h
0x1800f053e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0545  lea     rax, WPP_GLOBAL_Control
0x1800f054c  cmp     rcx, rax
0x1800f054f  jz      short loc_1800F0563
0x1800f0551  test    byte ptr [rcx+1Ch], 40h
0x1800f0555  jz      short loc_1800F0563
0x1800f0557  mov     edx, 3Dh ; '='
0x1800f055c  jmp     loc_1800F03D5
0x1800f0561  mov     ebx, edi
0x1800f0563  mov     rcx, [rbp+57h+hMem]; hMem
0x1800f0567  test    rcx, rcx
0x1800f056a  jz      short loc_1800F057C
0x1800f056c  call    cs:__imp_LocalFree
0x1800f0573  nop     dword ptr [rax+rax+00h]
0x1800f0578  mov     [rbp+57h+hMem], rdi
0x1800f057c  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800f0580  test    rcx, rcx
0x1800f0583  jz      short loc_1800F0595
0x1800f0585  call    cs:__imp_LocalFree
0x1800f058c  nop     dword ptr [rax+rax+00h]
0x1800f0591  mov     [rbp+57h+NewAcl], rdi
0x1800f0595  mov     rcx, [rbp+57h+var_50]; pSid
0x1800f0599  test    rcx, rcx
0x1800f059c  jz      short loc_1800F05AA
0x1800f059e  call    cs:__imp_FreeSid
0x1800f05a5  nop     dword ptr [rax+rax+00h]
0x1800f05aa  mov     eax, ebx
0x1800f05ac  mov     rcx, [rbp+57h+var_8]
0x1800f05b0  xor     rcx, rsp; StackCookie
0x1800f05b3  call    __security_check_cookie
0x1800f05b8  lea     r11, [rsp+0C0h+var_s0]
0x1800f05c0  mov     rbx, [r11+18h]
0x1800f05c4  mov     rdi, [r11+20h]
0x1800f05c8  mov     rsp, r11
0x1800f05cb  pop     rbp
0x1800f05cc  retn
```
