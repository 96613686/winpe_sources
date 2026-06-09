# CSmbFile::SetSecurity(void *)

- ea: `0x1800ee198`
- end: `0x1800ee46e`
- name: `?SetSecurity@CSmbFile@@IEAAXPEAX@Z`
- size: `726`
- prototype: `void __fastcall(CSmbFile *this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180062f88`

## callees

- `0x180008b70`
- `0x18000f5f0`
- `0x180012b18`
- `0x180014310`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800c7278`
- `0x1800ee198`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800ee203`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800ee203`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800ee21c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800ee21c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800ee23d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800ee23d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800ee268`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800ee268`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800ee2bd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800ee2bd`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ee343`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ee3ae`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ee343`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800ee3ae`

## pseudocode

```c
void __fastcall CSmbFile::SetSecurity(CSmbFile *this, void *a2)
{
  SECURITY_INFORMATION v4; // ebx
  __int16 v5; // ax
  int v6; // eax
  signed int v7; // ebx
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp-79h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+44h] [rbp-75h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-71h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+4Ch] [rbp-6Dh] BYREF
  PACL pSacl; // [rsp+50h] [rbp-69h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-61h] BYREF
  DWORD dwRevision; // [rsp+60h] [rbp-59h] BYREF
  PSID pGroup; // [rsp+68h] [rbp-51h] BYREF
  PSID pOwner; // [rsp+70h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+80h] [rbp-39h] BYREF
  __int128 v18; // [rsp+88h] [rbp-31h]
  signed int v19; // [rsp+98h] [rbp-21h]
  int v20; // [rsp+9Ch] [rbp-1Dh]
  int v21; // [rsp+A0h] [rbp-19h]
  WORD pControl; // [rsp+128h] [rbp+6Fh] BYREF
  WINBOOL bDaclPresent; // [rsp+130h] [rbp+77h] BYREF
  WINBOOL bSaclPresent; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
    pOwner = 0;
    bOwnerDefaulted = 0;
    GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted);
    pGroup = 0;
    bGroupDefaulted = 0;
    GetSecurityDescriptorGroup(a2, &pGroup, &bGroupDefaulted);
    pDacl = 0;
    bDaclPresent = 0;
    bDaclDefaulted = 0;
    GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted);
    if ( !bDaclPresent )
      pDacl = 0;
    pSacl = 0;
    bSaclPresent = 0;
    bSaclDefaulted = 0;
    GetSecurityDescriptorSacl(a2, &bSaclPresent, &pSacl, &bSaclDefaulted);
    if ( !bSaclPresent )
      pSacl = 0;
    v4 = bOwnerDefaulted == 0;
    if ( !bGroupDefaulted )
      v4 |= 2u;
    if ( !bDaclDefaulted )
      v4 |= 4u;
    if ( !bSaclDefaulted )
      v4 |= 8u;
    if ( (v4 & 0xC) != 0 )
    {
      pControl = 0;
      dwRevision = 0;
      GetSecurityDescriptorControl(a2, &pControl, &dwRevision);
      v5 = pControl & 0x1000;
      if ( (pControl & 0x2000) != 0 )
        v6 = v5 != 0 ? -1073741824 : 1610612736;
      else
        v6 = v5 != 0 ? -1879048192 : 805306368;
      v4 |= v6;
    }
    if ( (v4 & 3) != 0 )
    {
      TokenHandle::copyEx((char *)this + 392, &pControl, 3, 2);
      TokenHandle::EnablePrivilege((TokenHandle *)&pControl, 18);
      CNestedImpersonation::CNestedImpersonation(
        (CNestedImpersonation *)&pExceptionObject,
        (const struct TokenHandle *)&pControl);
      v7 = SetNamedSecurityInfoW(
             (LPWSTR)(*((_QWORD *)this + 13) + 12LL),
             SE_FILE_OBJECT,
             v4,
             pOwner,
             pGroup,
             pDacl,
             pSacl);
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
      TokenHandle::Decrement((TokenHandle *)&pControl);
    }
    else
    {
      CNestedImpersonation::CNestedImpersonation(
        (CNestedImpersonation *)&pExceptionObject,
        (CSmbFile *)((char *)this + 392));
      v7 = SetNamedSecurityInfoW(
             (LPWSTR)(*((_QWORD *)this + 13) + 12LL),
             SE_FILE_OBJECT,
             v4,
             pOwner,
             pGroup,
             pDacl,
             pSacl);
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
    }
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
          (unsigned int)v7);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v18 = 0;
      pExceptionObject = &ComError::`vftable';
      v19 = v7;
      v20 = 0;
      v21 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
  }
}

```

## disassembly

```asm
0x1800ee198  test    rdx, rdx
0x1800ee19b  jz      locret_1800EE46D
0x1800ee1a1  push    rbp
0x1800ee1a2  push    rbx
0x1800ee1a3  push    rsi
0x1800ee1a4  push    rdi
0x1800ee1a5  push    r13
0x1800ee1a7  push    r14
0x1800ee1a9  push    r15
0x1800ee1ab  lea     rbp, [rsp-27h]
0x1800ee1b0  sub     rsp, 0E0h
0x1800ee1b7  mov     rdi, rdx
0x1800ee1ba  mov     rsi, rcx
0x1800ee1bd  xor     r14d, r14d
0x1800ee1c0  lea     r15, WPP_GLOBAL_Control
0x1800ee1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee1ce  cmp     rcx, r15
0x1800ee1d1  jz      short loc_1800EE1F0
0x1800ee1d3  test    dword ptr [rcx+1Ch], 800h
0x1800ee1da  jz      short loc_1800EE1F0
0x1800ee1dc  lea     edx, [r14+1Bh]
0x1800ee1e0  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ee1e7  mov     rcx, [rcx+10h]
0x1800ee1eb  call    WPP_SF_
0x1800ee1f0  mov     [rbp+57h+pOwner], r14
0x1800ee1f4  mov     [rbp+57h+bOwnerDefaulted], r14d
0x1800ee1f8  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800ee1fc  lea     rdx, [rbp+57h+pOwner]; pOwner
0x1800ee200  mov     rcx, rdi; pSecurityDescriptor
0x1800ee203  call    cs:__imp_GetSecurityDescriptorOwner
0x1800ee209  mov     [rbp+57h+pGroup], r14
0x1800ee20d  mov     [rbp+57h+bGroupDefaulted], r14d
0x1800ee211  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x1800ee215  lea     rdx, [rbp+57h+pGroup]; pGroup
0x1800ee219  mov     rcx, rdi; pSecurityDescriptor
0x1800ee21c  call    cs:__imp_GetSecurityDescriptorGroup
0x1800ee222  mov     [rbp+57h+pDacl], r14
0x1800ee226  mov     [rbp+57h+bDaclPresent], r14d
0x1800ee22a  mov     [rbp+57h+bDaclDefaulted], r14d
0x1800ee22e  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800ee232  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800ee236  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x1800ee23a  mov     rcx, rdi; pSecurityDescriptor
0x1800ee23d  call    cs:__imp_GetSecurityDescriptorDacl
0x1800ee243  cmp     [rbp+57h+bDaclPresent], r14d
0x1800ee247  jnz     short loc_1800EE24D
0x1800ee249  mov     [rbp+57h+pDacl], r14
0x1800ee24d  mov     [rbp+57h+pSacl], r14
0x1800ee251  mov     [rbp+57h+bSaclPresent], r14d
0x1800ee255  mov     [rbp+57h+bSaclDefaulted], r14d
0x1800ee259  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x1800ee25d  lea     r8, [rbp+57h+pSacl]; pSacl
0x1800ee261  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x1800ee265  mov     rcx, rdi; pSecurityDescriptor
0x1800ee268  call    cs:__imp_GetSecurityDescriptorSacl
0x1800ee26e  cmp     [rbp+57h+bSaclPresent], r14d
0x1800ee272  jnz     short loc_1800EE278
0x1800ee274  mov     [rbp+57h+pSacl], r14
0x1800ee278  mov     ebx, r14d
0x1800ee27b  mov     r13d, 1
0x1800ee281  cmp     [rbp+57h+bOwnerDefaulted], r14d
0x1800ee285  cmovz   ebx, r13d
0x1800ee289  cmp     [rbp+57h+bGroupDefaulted], r14d
0x1800ee28d  jnz     short loc_1800EE292
0x1800ee28f  or      ebx, 2
0x1800ee292  cmp     [rbp+57h+bDaclDefaulted], r14d
0x1800ee296  jnz     short loc_1800EE29B
0x1800ee298  or      ebx, 4
0x1800ee29b  cmp     [rbp+57h+bSaclDefaulted], r14d
0x1800ee29f  jnz     short loc_1800EE2A4
0x1800ee2a1  or      ebx, 8
0x1800ee2a4  test    bl, 0Ch
0x1800ee2a7  jz      short loc_1800EE2F8
0x1800ee2a9  mov     [rbp+57h+pControl], r14w
0x1800ee2ae  mov     [rbp+57h+dwRevision], r14d
0x1800ee2b2  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x1800ee2b6  lea     rdx, [rbp+57h+pControl]; pControl
0x1800ee2ba  mov     rcx, rdi; pSecurityDescriptor
0x1800ee2bd  call    cs:__imp_GetSecurityDescriptorControl
0x1800ee2c3  mov     ecx, 1000h
0x1800ee2c8  movzx   eax, [rbp+57h+pControl]
0x1800ee2cc  and     ax, cx
0x1800ee2cf  mov     ecx, 2000h
0x1800ee2d4  test    [rbp+57h+pControl], cx
0x1800ee2d8  mov     ecx, 60000000h
0x1800ee2dd  jz      short loc_1800EE2EA
0x1800ee2df  neg     ax
0x1800ee2e2  sbb     eax, eax
0x1800ee2e4  and     eax, ecx
0x1800ee2e6  add     eax, ecx
0x1800ee2e8  jmp     short loc_1800EE2F6
0x1800ee2ea  neg     ax
0x1800ee2ed  sbb     eax, eax
0x1800ee2ef  and     eax, ecx
0x1800ee2f1  add     eax, 30000000h
0x1800ee2f6  or      ebx, eax
0x1800ee2f8  lea     rcx, [rsi+188h]
0x1800ee2ff  mov     r8d, 3
0x1800ee305  test    r8b, bl
0x1800ee308  jnz     short loc_1800EE356
0x1800ee30a  mov     rdx, rcx; struct TokenHandle *
0x1800ee30d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800ee311  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800ee316  mov     rax, [rbp+57h+pSacl]
0x1800ee31a  mov     rdx, [rbp+57h+pDacl]
0x1800ee31e  mov     r8, [rbp+57h+pGroup]
0x1800ee322  mov     rcx, [rsi+68h]
0x1800ee326  add     rcx, 0Ch; pObjectName
0x1800ee32a  mov     [rsp+110h+var_E0], rax; pSacl
0x1800ee32f  mov     [rsp+110h+var_E8], rdx; pDacl
0x1800ee334  mov     [rsp+110h+psidGroup], r8; psidGroup
0x1800ee339  mov     r9, [rbp+57h+pOwner]; psidOwner
0x1800ee33d  mov     r8d, ebx; SecurityInfo
0x1800ee340  mov     edx, r13d; ObjectType
0x1800ee343  call    cs:__imp_SetNamedSecurityInfoW
0x1800ee349  mov     ebx, eax
0x1800ee34b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800ee34f  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800ee354  jmp     short loc_1800EE3C9
0x1800ee356  mov     r9d, 2
0x1800ee35c  lea     rdx, [rbp+57h+pControl]
0x1800ee360  call    ?copyEx@TokenHandle@@QEBA?AV1@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; TokenHandle::copyEx(_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x1800ee365  nop
0x1800ee366  mov     edx, 12h; int
0x1800ee36b  lea     rcx, [rbp+57h+pControl]; this
0x1800ee36f  call    ?EnablePrivilege@TokenHandle@@QEAAXJ@Z; TokenHandle::EnablePrivilege(long)
0x1800ee374  lea     rdx, [rbp+57h+pControl]; struct TokenHandle *
0x1800ee378  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800ee37c  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800ee381  mov     rax, [rbp+57h+pSacl]
0x1800ee385  mov     rdx, [rbp+57h+pDacl]
0x1800ee389  mov     r8, [rbp+57h+pGroup]
0x1800ee38d  mov     rcx, [rsi+68h]
0x1800ee391  add     rcx, 0Ch; pObjectName
0x1800ee395  mov     [rsp+110h+var_E0], rax; pSacl
0x1800ee39a  mov     [rsp+110h+var_E8], rdx; pDacl
0x1800ee39f  mov     [rsp+110h+psidGroup], r8; psidGroup
0x1800ee3a4  mov     r9, [rbp+57h+pOwner]; psidOwner
0x1800ee3a8  mov     r8d, ebx; SecurityInfo
0x1800ee3ab  mov     edx, r13d; ObjectType
0x1800ee3ae  call    cs:__imp_SetNamedSecurityInfoW
0x1800ee3b4  mov     ebx, eax
0x1800ee3b6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800ee3ba  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800ee3bf  nop
0x1800ee3c0  lea     rcx, [rbp+57h+pControl]; this
0x1800ee3c4  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800ee3c9  test    ebx, ebx
0x1800ee3cb  jz      short loc_1800EE432
0x1800ee3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee3d4  cmp     rcx, r15
0x1800ee3d7  jz      short loc_1800EE3F7
0x1800ee3d9  test    byte ptr [rcx+1Ch], 4
0x1800ee3dd  jz      short loc_1800EE3F7
0x1800ee3df  mov     edx, 1Ch
0x1800ee3e4  mov     r9d, ebx
0x1800ee3e7  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ee3ee  mov     rcx, [rcx+10h]
0x1800ee3f2  call    WPP_SF_d
0x1800ee3f7  test    ebx, ebx
0x1800ee3f9  jle     short loc_1800EE404
0x1800ee3fb  movzx   ebx, bx
0x1800ee3fe  or      ebx, 80070000h
0x1800ee404  xorps   xmm0, xmm0
0x1800ee407  movups  [rbp+57h+var_88], xmm0
0x1800ee40b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ee412  mov     [rbp+57h+pExceptionObject], rax
0x1800ee416  mov     [rbp+57h+var_78], ebx
0x1800ee419  mov     [rbp+57h+var_74], r14d
0x1800ee41d  mov     [rbp+57h+var_70], r13d
0x1800ee421  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ee428  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ee42c  call    _CxxThrowException_0
0x1800ee432  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee439  cmp     rcx, r15
0x1800ee43c  jz      short loc_1800EE45C
0x1800ee43e  test    dword ptr [rcx+1Ch], 800h
0x1800ee445  jz      short loc_1800EE45C
0x1800ee447  mov     edx, 1Dh
0x1800ee44c  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800ee453  mov     rcx, [rcx+10h]
0x1800ee457  call    WPP_SF_
0x1800ee45c  add     rsp, 0E0h
0x1800ee463  pop     r15
0x1800ee465  pop     r14
0x1800ee467  pop     r13
0x1800ee469  pop     rdi
0x1800ee46a  pop     rsi
0x1800ee46b  pop     rbx
0x1800ee46c  pop     rbp
0x1800ee46d  retn
```
