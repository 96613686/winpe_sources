# BuildSPDObjectProtection

- ea: `0x18000e550`
- end: `0x18000e973`
- name: `BuildSPDObjectProtection`
- size: `1059`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, PSID pOwner, PSID pGroup, _BYTE *pAce, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aab4`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x18000e550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e64b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e64b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8fc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e79d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e79d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000e76e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000e76e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000e600`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000e600`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000e641`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000e641`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000e857`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000e857`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000e701`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000e701`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000e5a0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000e5a0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000e89e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000e89e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e694`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e694`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000e8f2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000e8f2`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000e776`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000e776`

## pseudocode

```c
__int64 __fastcall BuildSPDObjectProtection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PSID pOwner,
        PSID pGroup,
        _BYTE *pAce,
        _QWORD *a9)
{
  DWORD LastError; // ebx
  struct _ACL *v11; // rsi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  DWORD v15; // r14d
  DWORD LengthSid; // eax
  struct _ACL *v17; // rax
  __int64 v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r12
  DWORD i; // r14d
  DWORD v23; // r8d
  void *v24; // r9
  BOOL v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  void *v28; // rax
  void *v29; // r14
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v32; // [rsp+40h] [rbp-10h]
  DWORD dwBufferLength; // [rsp+90h] [rbp+40h] BYREF
  __int64 v34; // [rsp+98h] [rbp+48h]
  __int64 v35; // [rsp+A8h] [rbp+58h]

  v35 = a4;
  v34 = a2;
  pAce = 0;
  v32 = 0;
  dwBufferLength = 0;
  LastError = 0;
  v11 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 13;
LABEL_6:
      WPP_SF_d(v12[2], v13, WPP_ed468879b1803b25f9bc891025016378_Traceguids, LastError);
LABEL_7:
      *a9 = 0;
      goto LABEL_71;
    }
  }
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 14;
      goto LABEL_6;
    }
  }
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 15;
      goto LABEL_6;
    }
  }
  v14 = a9;
  v15 = 8;
  do
  {
    LengthSid = GetLengthSid(*(PSID *)(a3 + 8LL * (_QWORD)v11));
    v11 = (struct _ACL *)((char *)v11 + 1);
    v15 += LengthSid + 8;
  }
  while ( v11 != (struct _ACL *)2 );
  v17 = (struct _ACL *)IpsecAllocMem(v15);
  v11 = v17;
  if ( !v17 )
  {
    v18 = 14;
    LastError = 14;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v20 = 16;
LABEL_24:
    WPP_SF_d(v19[2], v20, WPP_ed468879b1803b25f9bc891025016378_Traceguids, v18);
LABEL_25:
    *v14 = 0;
    goto LABEL_71;
  }
  if ( !InitializeAcl(v17, v15, 2u) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_25;
      v20 = 17;
LABEL_31:
      v18 = LastError;
      goto LABEL_24;
    }
  }
  v21 = a5;
  for ( i = 0; i < 2; ++i )
  {
    v23 = *(_DWORD *)(v35 + 4LL * i);
    v24 = *(void **)(a3 + 8LL * i);
    if ( *(_BYTE *)(i + v34) )
      v25 = AddAccessDeniedAce(v11, 2u, v23, v24);
    else
      v25 = AddAccessAllowedAce(v11, 2u, v23, v24);
    if ( !v25 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v27 = 18;
LABEL_48:
          WPP_SF_d(v26[2], v27, WPP_ed468879b1803b25f9bc891025016378_Traceguids, LastError);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
    }
    if ( *(_BYTE *)(i + v21) )
    {
      if ( !GetAce(v11, i, (LPVOID *)&pAce) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v27 = 19;
            goto LABEL_48;
          }
          goto LABEL_25;
        }
      }
      if ( !pAce )
      {
        LastError = 1359;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v27 = 20;
          goto LABEL_48;
        }
        goto LABEL_25;
      }
      pAce[1] = *(_BYTE *)(i + v21);
    }
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v11, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v20 = 21;
        goto LABEL_31;
      }
      goto LABEL_25;
    }
  }
  dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  v28 = (void *)IpsecAllocMem(dwBufferLength);
  v29 = v28;
  if ( !v28 )
  {
    v18 = 14;
    LastError = 14;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v20 = 22;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  if ( MakeSelfRelativeSD(pSecurityDescriptor, v28, &dwBufferLength) || (LastError = GetLastError()) == 0 )
  {
    *v14 = v29;
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ed468879b1803b25f9bc891025016378_Traceguids, LastError);
  *v14 = 0;
  IpsecFreeMem(v29);
LABEL_71:
  if ( v11 )
LABEL_74:
    IpsecFreeMem(v11);
  return LastError;
}

```

## disassembly

```asm
0x18000e550  mov     rax, rsp
0x18000e553  mov     [rax+18h], rbx
0x18000e557  mov     [rax+20h], r9
0x18000e55b  mov     [rax+10h], rdx
0x18000e55f  mov     [rax+8], ecx
0x18000e562  push    rbp
0x18000e563  push    rsi
0x18000e564  push    rdi
0x18000e565  push    r12
0x18000e567  push    r13
0x18000e569  push    r14
0x18000e56b  push    r15
0x18000e56d  mov     rbp, rsp
0x18000e570  sub     rsp, 50h
0x18000e574  xor     r15d, r15d
0x18000e577  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000e57b  xor     eax, eax
0x18000e57d  mov     [rbp+pAce], r15
0x18000e581  xorps   xmm0, xmm0
0x18000e584  mov     [rbp+var_10], rax
0x18000e588  mov     r13, r8
0x18000e58b  mov     [rbp+dwBufferLength], r15d
0x18000e58f  mov     ebx, r15d
0x18000e592  mov     esi, r15d
0x18000e595  lea     edx, [rax+1]; dwRevision
0x18000e598  movups  [rbp+pSecurityDescriptor], xmm0
0x18000e59c  movups  [rbp+var_20], xmm0
0x18000e5a0  call    cs:__imp_InitializeSecurityDescriptor
0x18000e5a6  test    eax, eax
0x18000e5a8  jnz     short loc_18000E5F5
0x18000e5aa  call    cs:__imp_GetLastError
0x18000e5b0  mov     ebx, eax
0x18000e5b2  test    eax, eax
0x18000e5b4  jz      short loc_18000E5F5
0x18000e5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5bd  lea     rax, WPP_GLOBAL_Control
0x18000e5c4  cmp     rcx, rax
0x18000e5c7  jz      short loc_18000E5E6
0x18000e5c9  test    byte ptr [rcx+1Ch], 10h
0x18000e5cd  jz      short loc_18000E5E6
0x18000e5cf  lea     edx, [r15+0Dh]
0x18000e5d3  mov     rcx, [rcx+10h]
0x18000e5d7  lea     r8, WPP_ed468879b1803b25f9bc891025016378_Traceguids
0x18000e5de  mov     r9d, ebx
0x18000e5e1  call    WPP_SF_d
0x18000e5e6  mov     rax, [rbp+arg_40]
0x18000e5ed  mov     [rax], r15
0x18000e5f0  jmp     loc_18000E947
0x18000e5f5  mov     rdx, [rbp+pOwner]; pOwner
0x18000e5f9  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000e5fd  xor     r8d, r8d; bOwnerDefaulted
0x18000e600  call    cs:__imp_SetSecurityDescriptorOwner
0x18000e606  test    eax, eax
0x18000e608  jnz     short loc_18000E636
0x18000e60a  call    cs:__imp_GetLastError
0x18000e610  mov     ebx, eax
0x18000e612  test    eax, eax
0x18000e614  jz      short loc_18000E636
0x18000e616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e61d  lea     rax, WPP_GLOBAL_Control
0x18000e624  cmp     rcx, rax
0x18000e627  jz      short loc_18000E5E6
0x18000e629  test    byte ptr [rcx+1Ch], 10h
0x18000e62d  jz      short loc_18000E5E6
0x18000e62f  mov     edx, 0Eh
0x18000e634  jmp     short loc_18000E5D3
0x18000e636  mov     rdx, [rbp+pGroup]; pGroup
0x18000e63a  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000e63e  xor     r8d, r8d; bGroupDefaulted
0x18000e641  call    cs:__imp_SetSecurityDescriptorGroup
0x18000e647  test    eax, eax
0x18000e649  jnz     short loc_18000E682
0x18000e64b  call    cs:__imp_GetLastError
0x18000e651  mov     ebx, eax
0x18000e653  test    eax, eax
0x18000e655  jz      short loc_18000E682
0x18000e657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e65e  lea     rax, WPP_GLOBAL_Control
0x18000e665  cmp     rcx, rax
0x18000e668  jz      loc_18000E5E6
0x18000e66e  test    byte ptr [rcx+1Ch], 10h
0x18000e672  jz      loc_18000E5E6
0x18000e678  mov     edx, 0Fh
0x18000e67d  jmp     loc_18000E5D3
0x18000e682  mov     rdi, [rbp+arg_40]
0x18000e689  mov     r14d, 8
0x18000e68f  mov     rcx, [r13+rsi*8+0]; pSid
0x18000e694  call    cs:__imp_GetLengthSid
0x18000e69a  add     r14d, 8
0x18000e69e  inc     rsi
0x18000e6a1  add     r14d, eax
0x18000e6a4  cmp     rsi, 2
0x18000e6a8  jnz     short loc_18000E68F
0x18000e6aa  mov     ecx, r14d
0x18000e6ad  call    IpsecAllocMem
0x18000e6b2  mov     rsi, rax
0x18000e6b5  test    rax, rax
0x18000e6b8  jnz     short loc_18000E6F5
0x18000e6ba  lea     r9d, [rax+0Eh]
0x18000e6be  mov     ebx, r9d
0x18000e6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6c8  lea     rax, WPP_GLOBAL_Control
0x18000e6cf  cmp     rcx, rax
0x18000e6d2  jz      short loc_18000E6ED
0x18000e6d4  test    byte ptr [rcx+1Ch], 10h
0x18000e6d8  jz      short loc_18000E6ED
0x18000e6da  lea     edx, [rsi+10h]
0x18000e6dd  mov     rcx, [rcx+10h]
0x18000e6e1  lea     r8, WPP_ed468879b1803b25f9bc891025016378_Traceguids
0x18000e6e8  call    WPP_SF_d
0x18000e6ed  mov     [rdi], r15
0x18000e6f0  jmp     loc_18000E947
0x18000e6f5  mov     r8d, 2; dwAclRevision
0x18000e6fb  mov     edx, r14d; nAclLength
0x18000e6fe  mov     rcx, rsi; pAcl
0x18000e701  call    cs:__imp_InitializeAcl
0x18000e707  test    eax, eax
0x18000e709  jnz     short loc_18000E73A
0x18000e70b  call    cs:__imp_GetLastError
0x18000e711  mov     ebx, eax
0x18000e713  test    eax, eax
0x18000e715  jz      short loc_18000E73A
0x18000e717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e71e  lea     rax, WPP_GLOBAL_Control
0x18000e725  cmp     rcx, rax
0x18000e728  jz      short loc_18000E6ED
0x18000e72a  test    byte ptr [rcx+1Ch], 10h
0x18000e72e  jz      short loc_18000E6ED
0x18000e730  mov     edx, 11h
0x18000e735  mov     r9d, ebx
0x18000e738  jmp     short loc_18000E6DD
0x18000e73a  mov     r12, [rbp+arg_20]
0x18000e73e  mov     r14d, r15d
0x18000e741  cmp     r14d, 2
0x18000e745  jnb     loc_18000E849
0x18000e74b  mov     rax, [rbp+arg_18]
0x18000e74f  mov     edx, 2; dwAceRevision
0x18000e754  mov     r15d, r14d
0x18000e757  mov     rcx, rsi; pAcl
0x18000e75a  mov     r8d, [rax+r15*4]; AccessMask
0x18000e75e  mov     rax, [rbp+arg_8]
0x18000e762  mov     r9, [r13+r15*8+0]; pSid
0x18000e767  cmp     byte ptr [r15+rax], 0
0x18000e76c  jnz     short loc_18000E776
0x18000e76e  call    cs:__imp_AddAccessAllowedAce
0x18000e774  jmp     short loc_18000E77C
0x18000e776  call    cs:__imp_AddAccessDeniedAce
0x18000e77c  test    eax, eax
0x18000e77e  jnz     short loc_18000E78C
0x18000e780  call    cs:__imp_GetLastError
0x18000e786  mov     ebx, eax
0x18000e788  test    eax, eax
0x18000e78a  jnz     short loc_18000E7CB
0x18000e78c  cmp     byte ptr [r15+r12], 0
0x18000e791  jz      short loc_18000E7C3
0x18000e793  lea     r8, [rbp+pAce]; pAce
0x18000e797  mov     edx, r14d; dwAceIndex
0x18000e79a  mov     rcx, rsi; pAcl
0x18000e79d  call    cs:__imp_GetAce
0x18000e7a3  test    eax, eax
0x18000e7a5  jnz     short loc_18000E7B3
0x18000e7a7  call    cs:__imp_GetLastError
0x18000e7ad  mov     ebx, eax
0x18000e7af  test    eax, eax
0x18000e7b1  jnz     short loc_18000E804
0x18000e7b3  mov     rcx, [rbp+pAce]
0x18000e7b7  test    rcx, rcx
0x18000e7ba  jz      short loc_18000E824
0x18000e7bc  mov     al, [r15+r12]
0x18000e7c0  mov     [rcx+1], al
0x18000e7c3  inc     r14d
0x18000e7c6  jmp     loc_18000E741
0x18000e7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d2  lea     rax, WPP_GLOBAL_Control
0x18000e7d9  cmp     rcx, rax
0x18000e7dc  jz      short loc_18000E7FC
0x18000e7de  test    byte ptr [rcx+1Ch], 10h
0x18000e7e2  jz      short loc_18000E7FC
0x18000e7e4  mov     edx, 12h
0x18000e7e9  mov     rcx, [rcx+10h]
0x18000e7ed  lea     r8, WPP_ed468879b1803b25f9bc891025016378_Traceguids
0x18000e7f4  mov     r9d, ebx
0x18000e7f7  call    WPP_SF_d
0x18000e7fc  xor     r15d, r15d
0x18000e7ff  jmp     loc_18000E6ED
0x18000e804  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e80b  lea     rax, WPP_GLOBAL_Control
0x18000e812  cmp     rcx, rax
0x18000e815  jz      short loc_18000E7FC
0x18000e817  test    byte ptr [rcx+1Ch], 10h
0x18000e81b  jz      short loc_18000E7FC
0x18000e81d  mov     edx, 13h
0x18000e822  jmp     short loc_18000E7E9
0x18000e824  mov     ebx, 54Fh
0x18000e829  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e830  lea     rax, WPP_GLOBAL_Control
0x18000e837  cmp     rcx, rax
0x18000e83a  jz      short loc_18000E7FC
0x18000e83c  test    byte ptr [rcx+1Ch], 10h
0x18000e840  jz      short loc_18000E7FC
0x18000e842  mov     edx, 14h
0x18000e847  jmp     short loc_18000E7E9
0x18000e849  xor     r9d, r9d; bDaclDefaulted
0x18000e84c  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000e850  mov     r8, rsi; pDacl
0x18000e853  lea     edx, [r9+1]; bDaclPresent
0x18000e857  call    cs:__imp_SetSecurityDescriptorDacl
0x18000e85d  xor     r15d, r15d
0x18000e860  test    eax, eax
0x18000e862  jnz     short loc_18000E89A
0x18000e864  call    cs:__imp_GetLastError
0x18000e86a  mov     ebx, eax
0x18000e86c  test    eax, eax
0x18000e86e  jz      short loc_18000E89A
0x18000e870  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e877  lea     rax, WPP_GLOBAL_Control
0x18000e87e  cmp     rcx, rax
0x18000e881  jz      loc_18000E6ED
0x18000e887  test    byte ptr [rcx+1Ch], 10h
0x18000e88b  jz      loc_18000E6ED
0x18000e891  lea     edx, [r15+15h]
0x18000e895  jmp     loc_18000E735
0x18000e89a  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000e89e  call    cs:__imp_GetSecurityDescriptorLength
0x18000e8a4  mov     ecx, eax
0x18000e8a6  mov     [rbp+dwBufferLength], ecx
0x18000e8a9  call    IpsecAllocMem
0x18000e8ae  mov     r14, rax
0x18000e8b1  test    rax, rax
0x18000e8b4  jnz     short loc_18000E8E7
0x18000e8b6  lea     r9d, [rax+0Eh]
0x18000e8ba  mov     ebx, r9d
0x18000e8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8c4  lea     rax, WPP_GLOBAL_Control
0x18000e8cb  cmp     rcx, rax
0x18000e8ce  jz      loc_18000E6ED
0x18000e8d4  test    byte ptr [rcx+1Ch], 10h
0x18000e8d8  jz      loc_18000E6ED
0x18000e8de  lea     edx, [r14+16h]
0x18000e8e2  jmp     loc_18000E6DD
0x18000e8e7  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18000e8eb  mov     rdx, r14; pSelfRelativeSecurityDescriptor
0x18000e8ee  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000e8f2  call    cs:__imp_MakeSelfRelativeSD
0x18000e8f8  test    eax, eax
0x18000e8fa  jnz     short loc_18000E94E
0x18000e8fc  call    cs:__imp_GetLastError
0x18000e902  mov     ebx, eax
0x18000e904  test    eax, eax
0x18000e906  jz      short loc_18000E94E
0x18000e908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e90f  lea     rax, WPP_GLOBAL_Control
0x18000e916  cmp     rcx, rax
0x18000e919  jz      short loc_18000E939
0x18000e91b  test    byte ptr [rcx+1Ch], 10h
0x18000e91f  jz      short loc_18000E939
0x18000e921  mov     rcx, [rcx+10h]
0x18000e925  lea     r8, WPP_ed468879b1803b25f9bc891025016378_Traceguids
0x18000e92c  mov     edx, 17h
0x18000e931  mov     r9d, ebx
0x18000e934  call    WPP_SF_d
0x18000e939  mov     rax, r15
0x18000e93c  mov     rcx, r14; lpMem
0x18000e93f  mov     [rdi], rax
0x18000e942  call    IpsecFreeMem
0x18000e947  test    rsi, rsi
0x18000e94a  jz      short loc_18000E959
0x18000e94c  jmp     short loc_18000E951
0x18000e94e  mov     [rdi], r14
0x18000e951  mov     rcx, rsi; lpMem
0x18000e954  call    IpsecFreeMem
0x18000e959  mov     eax, ebx
0x18000e95b  mov     rbx, [rsp+50h+arg_10]
0x18000e963  add     rsp, 50h
0x18000e967  pop     r15
0x18000e969  pop     r14
0x18000e96b  pop     r13
0x18000e96d  pop     r12
0x18000e96f  pop     rdi
0x18000e970  pop     rsi
0x18000e971  pop     rbp
0x18000e972  retn
```
