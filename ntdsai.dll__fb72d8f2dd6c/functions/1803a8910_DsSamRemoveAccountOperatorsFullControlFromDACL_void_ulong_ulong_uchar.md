# DsSamRemoveAccountOperatorsFullControlFromDACL(void *,ulong *,ulong *,uchar *)

- ea: `0x1803a8910`
- end: `0x1803a8e00`
- name: `?DsSamRemoveAccountOperatorsFullControlFromDACL@@YAJPEAXPEAK1PEAE@Z`
- size: `1264`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, unsigned int *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803abd40`

## callees

- `0x180006360`
- `0x18000bb80`
- `0x18001e090`
- `0x1803a8910`
- `0x18042addc`
- `0x180453340`
- `0x18047b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1803a8c97`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1803a8c97`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1803a89f3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1803a8bf2`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1803a89f3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1803a8bf2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803a8d20`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803a8d20`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1803a8c45`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1803a8c45`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803a8d3d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803a8d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a8bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a8bfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a8d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a8da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a8d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a8da5`
- `ntdll!RtlEqualSid` at `0x1803a8c84`
- `ntdll!RtlEqualSid` at `0x1803a8c84`
- `ADVAPI32!SetEntriesInAclW` at `0x1803a8d03`
- `ADVAPI32!SetEntriesInAclW` at `0x1803a8d03`

## pseudocode

```c
__int64 __fastcall DsSamRemoveAccountOperatorsFullControlFromDACL(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  PACL v6; // rbx
  struct _ACL *v7; // r15
  __int64 v8; // rax
  struct _ACL *v9; // rax
  DWORD *p_dwPrimaryGroupSize; // rdi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  DWORD *v16; // rax
  DWORD *p_dwSaclSize; // rbx
  unsigned __int64 v18; // r14
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  DWORD *v23; // rax
  unsigned int AceCount; // r13d
  unsigned int v25; // r12d
  struct _ACL *v26; // r14
  unsigned __int8 *v27; // rax
  DWORD v28; // eax
  _BYTE v30[32]; // [rsp+0h] [rbp-60h] BYREF
  LPDWORD lpdwSaclSize; // [rsp+30h] [rbp-30h]
  PSID pOwner; // [rsp+38h] [rbp-28h]
  LPDWORD lpdwOwnerSize; // [rsp+40h] [rbp-20h]
  PSID pPrimaryGroup; // [rsp+48h] [rbp-18h]
  LPDWORD lpdwPrimaryGroupSize; // [rsp+50h] [rbp-10h]
  DWORD dwPrimaryGroupSize; // [rsp+60h] [rbp+0h] BYREF
  DWORD dwOwnerSize; // [rsp+64h] [rbp+4h] BYREF
  DWORD dwSaclSize; // [rsp+68h] [rbp+8h] BYREF
  DWORD dwDaclSize; // [rsp+6Ch] [rbp+Ch] BYREF
  PACL pSacl; // [rsp+70h] [rbp+10h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+78h] [rbp+18h] BYREF
  PSID pSid; // [rsp+80h] [rbp+20h] BYREF
  PACL NewAcl; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int8 *v44; // [rsp+90h] [rbp+30h]
  LPDWORD lpdwBufferLength; // [rsp+98h] [rbp+38h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptora; // [rsp+A0h] [rbp+40h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp+50h] BYREF
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+E0h] [rbp+80h] BYREF
  __int64 v49; // [rsp+100h] [rbp+A0h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+108h] [rbp+A8h] BYREF

  pSelfRelativeSecurityDescriptora = pSelfRelativeSecurityDescriptor;
  *a3 = 0;
  v44 = a4;
  lpdwBufferLength = a2;
  v49 = 0;
  lpdwPrimaryGroupSize = &dwPrimaryGroupSize;
  pPrimaryGroup = 0;
  lpdwOwnerSize = &dwOwnerSize;
  pOwner = 0;
  lpdwSaclSize = &dwSaclSize;
  v6 = 0;
  *a4 = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v7 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  dwAbsoluteSecurityDescriptorSize = 40;
  dwDaclSize = 0;
  pSacl = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  MakeAbsoluteSD(
    pSelfRelativeSecurityDescriptor,
    0,
    &dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    lpdwSaclSize,
    pOwner,
    lpdwOwnerSize,
    pPrimaryGroup,
    lpdwPrimaryGroupSize);
  if ( dwDaclSize && (v8 = DSAllocAux(dwDaclSize, 521733528), v7 = (struct _ACL *)v8, dwDaclSize) && !v8
    || dwSaclSize && (v9 = (struct _ACL *)DSAllocAux(dwSaclSize, 521733535), v6 = v9, pSacl = v9, dwSaclSize) && !v9 )
  {
    *a3 = 8;
    goto LABEL_60;
  }
  p_dwPrimaryGroupSize = 0;
  if ( !dwOwnerSize )
    goto LABEL_22;
  v11 = dwOwnerSize;
  if ( dwOwnerSize > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)dwOwnerSize + g_ulAdditionalProbeSize + 8 < dwOwnerSize
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_72;
  }
  v12 = v11 + 23;
  if ( v11 + 23 <= v11 + 8 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
  v14 = alloca(v13);
  v15 = alloca(v13);
  p_dwPrimaryGroupSize = &dwPrimaryGroupSize;
  if ( v30 == (_BYTE *)-96LL || (dwPrimaryGroupSize = 1801679955, (p_dwPrimaryGroupSize = &dwSaclSize) == 0) )
  {
LABEL_72:
    if ( v11 + 8 >= v11 )
    {
      v16 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_dwPrimaryGroupSize = v16;
      if ( v16 )
      {
        *v16 = 1885431112;
        p_dwPrimaryGroupSize = v16 + 2;
      }
    }
  }
  if ( !dwOwnerSize || p_dwPrimaryGroupSize )
  {
LABEL_22:
    p_dwSaclSize = 0;
    if ( dwPrimaryGroupSize )
    {
      v18 = dwPrimaryGroupSize;
      if ( dwPrimaryGroupSize > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)dwPrimaryGroupSize + g_ulAdditionalProbeSize + 8 < dwPrimaryGroupSize
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_71;
      }
      v19 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      p_dwSaclSize = &dwPrimaryGroupSize;
      if ( v30 == (_BYTE *)-96LL || (dwPrimaryGroupSize = 1801679955, (p_dwSaclSize = &dwSaclSize) == 0) )
      {
LABEL_71:
        if ( v18 + 8 >= v18 )
        {
          v23 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_dwSaclSize = v23;
          if ( v23 )
          {
            *v23 = 1885431112;
            p_dwSaclSize = v23 + 2;
          }
        }
      }
      if ( dwPrimaryGroupSize && !p_dwSaclSize )
        goto LABEL_35;
    }
    if ( MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           pAbsoluteSecurityDescriptor,
           &dwAbsoluteSecurityDescriptorSize,
           v7,
           &dwDaclSize,
           pSacl,
           &dwSaclSize,
           p_dwPrimaryGroupSize,
           &dwOwnerSize,
           p_dwSaclSize,
           &dwPrimaryGroupSize) )
    {
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x224u, 0, 0, 0, 0, 0, 0, &pSid) )
      {
LABEL_35:
        *a3 = 8;
        goto LABEL_53;
      }
      if ( !v7 )
        goto LABEL_53;
      AceCount = v7->AceCount;
      if ( !v7->AceCount )
        goto LABEL_53;
      v25 = 0;
      v26 = v7 + 1;
      while ( v25 < AceCount )
      {
        if ( !v26->AclRevision
          && RtlEqualSid(pSid, &v26[1])
          && AreAllAccessesGranted(*(_DWORD *)&v26->AceCount, 0xF01FFu) )
        {
          v27 = v44;
          *v44 = 1;
          goto LABEL_49;
        }
        ++v25;
        v26 = (struct _ACL *)((char *)v26 + v26->AclSize);
      }
      v27 = v44;
LABEL_49:
      if ( !*v27 )
        goto LABEL_53;
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
      pListOfExplicitEntries.grfAccessMode = REVOKE_ACCESS;
      pListOfExplicitEntries.grfAccessPermissions = 983551;
      pListOfExplicitEntries.grfInheritance = 0;
      pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
      pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      v28 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v7, &NewAcl);
      *a3 = v28;
      if ( v28
        || SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, NewAcl, 0)
        && MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, pSelfRelativeSecurityDescriptora, lpdwBufferLength) )
      {
        goto LABEL_53;
      }
    }
    *a3 = GetLastError();
LABEL_53:
    if ( p_dwPrimaryGroupSize && *(p_dwPrimaryGroupSize - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    if ( p_dwSaclSize && *(p_dwSaclSize - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_59;
  }
  *a3 = 8;
LABEL_59:
  v6 = pSacl;
LABEL_60:
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pSid )
    LocalFree(pSid);
  if ( v7 )
    DSFreeAux(v7, 521733685);
  if ( v6 )
    DSFreeAux(v6, 521733689);
  return *a3 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x1803a8910  push    rbp
0x1803a8912  push    rbx
0x1803a8913  push    rsi
0x1803a8914  push    rdi
0x1803a8915  push    r12
0x1803a8917  push    r13
0x1803a8919  push    r14
0x1803a891b  push    r15
0x1803a891d  sub     rsp, 128h
0x1803a8924  lea     rbp, [rsp+60h]
0x1803a8929  mov     rax, cs:__security_cookie
0x1803a8930  xor     rax, rbp
0x1803a8933  mov     [rbp+100h+var_50], rax
0x1803a893a  xor     r13d, r13d
0x1803a893d  mov     [rbp+100h+pSelfRelativeSecurityDescriptor], rcx
0x1803a8941  xorps   xmm0, xmm0
0x1803a8944  mov     [r8], r13d
0x1803a8947  mov     r12, rcx
0x1803a894a  mov     [rbp+100h+var_D0], r9
0x1803a894e  xor     ecx, ecx
0x1803a8950  mov     [rbp+100h+lpdwBufferLength], rdx
0x1803a8954  lea     rax, [rbp+100h+dwPrimaryGroupSize]
0x1803a8958  mov     [rbp+100h+var_60], rcx
0x1803a895f  mov     [rsp+160h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1803a8964  mov     rsi, r8
0x1803a8967  mov     [rsp+160h+pPrimaryGroup], r13; pPrimaryGroup
0x1803a896c  lea     rax, [rbp+100h+dwOwnerSize]
0x1803a8970  mov     [rsp+160h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1803a8975  lea     r8, [rbp+100h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1803a8979  mov     [rsp+160h+pOwner], r13; pOwner
0x1803a897e  lea     rax, [rbp+100h+dwSaclSize]
0x1803a8982  mov     [rsp+160h+lpdwSaclSize], rax; lpdwSaclSize
0x1803a8987  mov     ebx, r13d
0x1803a898a  lea     rax, [rbp+100h+dwDaclSize]
0x1803a898e  mov     [r9], r13b
0x1803a8991  mov     [rsp+160h+pSacl], r13; pSacl
0x1803a8996  xor     r9d, r9d; pDacl
0x1803a8999  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1803a899b  mov     [rsp+160h+lpdwDaclSize], rax; lpdwDaclSize
0x1803a89a0  mov     rcx, r12; pSelfRelativeSecurityDescriptor
0x1803a89a3  mov     [rbp+100h+NewAcl], r13
0x1803a89a7  movups  xmmword ptr [rbp+100h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1803a89ab  mov     dword ptr [rbp+100h+pIdentifierAuthority.Value], r13d
0x1803a89b2  mov     r15d, r13d
0x1803a89b5  movups  xmmword ptr [rbp+100h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1803a89b9  mov     word ptr [rbp+100h+pIdentifierAuthority.Value+4], 500h
0x1803a89c2  movups  xmmword ptr [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1803a89c6  mov     [rbp+100h+pSid], r13
0x1803a89ca  movups  [rbp+100h+pAbsoluteSecurityDescriptor], xmm0
0x1803a89d1  mov     [rbp+100h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x1803a89d8  movups  [rbp+100h+var_70], xmm0
0x1803a89df  mov     [rbp+100h+dwDaclSize], r13d
0x1803a89e3  mov     [rbp+100h+var_F0], rbx
0x1803a89e7  mov     [rbp+100h+dwSaclSize], r13d
0x1803a89eb  mov     [rbp+100h+dwOwnerSize], r13d
0x1803a89ef  mov     [rbp+100h+dwPrimaryGroupSize], r13d
0x1803a89f3  call    cs:__imp_MakeAbsoluteSD
0x1803a89f9  mov     eax, [rbp+100h+dwDaclSize]
0x1803a89fc  test    eax, eax
0x1803a89fe  jz      short loc_1803A8A25
0x1803a8a00  mov     ecx, eax
0x1803a8a02  mov     edx, 1F190598h
0x1803a8a07  call    DSAllocAux
0x1803a8a0c  mov     r15, rax
0x1803a8a0f  cmp     [rbp+100h+dwDaclSize], r13d
0x1803a8a13  jbe     short loc_1803A8A25
0x1803a8a15  test    rax, rax
0x1803a8a18  jnz     short loc_1803A8A25
0x1803a8a1a  mov     dword ptr [rsi], 8
0x1803a8a20  jmp     loc_1803A8D8D
0x1803a8a25  mov     eax, [rbp+100h+dwSaclSize]
0x1803a8a28  test    eax, eax
0x1803a8a2a  jz      short loc_1803A8A4A
0x1803a8a2c  mov     ecx, eax
0x1803a8a2e  mov     edx, 1F19059Fh
0x1803a8a33  call    DSAllocAux
0x1803a8a38  mov     rbx, rax
0x1803a8a3b  mov     [rbp+100h+var_F0], rax
0x1803a8a3f  cmp     [rbp+100h+dwSaclSize], r13d
0x1803a8a43  jbe     short loc_1803A8A4A
0x1803a8a45  test    rax, rax
0x1803a8a48  jz      short loc_1803A8A1A
0x1803a8a4a  mov     eax, [rbp+100h+dwOwnerSize]
0x1803a8a4d  mov     rdi, r13
0x1803a8a50  mov     r14, 0FFFFFFFFFFFFFF0h
0x1803a8a5a  test    eax, eax
0x1803a8a5c  jz      loc_1803A8AFB
0x1803a8a62  cmp     rax, cs:g_ulMaxStackAllocSize
0x1803a8a69  mov     ebx, eax
0x1803a8a6b  ja      short loc_1803A8ABE
0x1803a8a6d  mov     rcx, cs:g_ulAdditionalProbeSize
0x1803a8a74  add     rcx, 8
0x1803a8a78  add     rcx, rax
0x1803a8a7b  cmp     rcx, rax
0x1803a8a7e  jb      short loc_1803A8ABE
0x1803a8a80  call    VerifyStackAvailable
0x1803a8a85  test    eax, eax
0x1803a8a87  jz      short loc_1803A8ABE
0x1803a8a89  lea     rax, [rbx+8]
0x1803a8a8d  lea     rcx, [rax+0Fh]
0x1803a8a91  cmp     rcx, rax
0x1803a8a94  ja      short loc_1803A8A99
0x1803a8a96  mov     rcx, r14
0x1803a8a99  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1803a8a9d  mov     rax, rcx
0x1803a8aa0  call    _alloca_probe
0x1803a8aa5  sub     rsp, rcx
0x1803a8aa8  lea     rdi, [rsp+160h+dwPrimaryGroupSize]
0x1803a8aad  test    rdi, rdi
0x1803a8ab0  jz      short loc_1803A8ABE
0x1803a8ab2  mov     dword ptr [rdi], 6B637453h
0x1803a8ab8  add     rdi, 8
0x1803a8abc  jnz     short loc_1803A8AE5
0x1803a8abe  lea     rcx, [rbx+8]
0x1803a8ac2  cmp     rcx, rbx
0x1803a8ac5  jb      short loc_1803A8AE5
0x1803a8ac7  mov     rax, cs:g_pfnAllocate
0x1803a8ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a8ad3  mov     rdi, rax
0x1803a8ad6  test    rax, rax
0x1803a8ad9  jz      short loc_1803A8AE5
0x1803a8adb  mov     dword ptr [rax], 70616548h
0x1803a8ae1  add     rdi, 8
0x1803a8ae5  cmp     [rbp+100h+dwOwnerSize], r13d
0x1803a8ae9  jbe     short loc_1803A8AFB
0x1803a8aeb  test    rdi, rdi
0x1803a8aee  jnz     short loc_1803A8AFB
0x1803a8af0  mov     dword ptr [rsi], 8
0x1803a8af6  jmp     loc_1803A8D89
0x1803a8afb  mov     eax, [rbp+100h+dwPrimaryGroupSize]
0x1803a8afe  mov     rbx, r13
0x1803a8b01  test    eax, eax
0x1803a8b03  jz      loc_1803A8BAA
0x1803a8b09  cmp     rax, cs:g_ulMaxStackAllocSize
0x1803a8b10  mov     r14d, eax
0x1803a8b13  ja      short loc_1803A8B6D
0x1803a8b15  mov     rcx, cs:g_ulAdditionalProbeSize
0x1803a8b1c  add     rcx, 8
0x1803a8b20  add     rcx, rax
0x1803a8b23  cmp     rcx, rax
0x1803a8b26  jb      short loc_1803A8B6D
0x1803a8b28  call    VerifyStackAvailable
0x1803a8b2d  test    eax, eax
0x1803a8b2f  jz      short loc_1803A8B6D
0x1803a8b31  lea     rax, [r14+8]
0x1803a8b35  lea     rcx, [rax+0Fh]
0x1803a8b39  cmp     rcx, rax
0x1803a8b3c  ja      short loc_1803A8B48
0x1803a8b3e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1803a8b48  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1803a8b4c  mov     rax, rcx
0x1803a8b4f  call    _alloca_probe
0x1803a8b54  sub     rsp, rcx
0x1803a8b57  lea     rbx, [rsp+160h+dwPrimaryGroupSize]
0x1803a8b5c  test    rbx, rbx
0x1803a8b5f  jz      short loc_1803A8B6D
0x1803a8b61  mov     dword ptr [rbx], 6B637453h
0x1803a8b67  add     rbx, 8
0x1803a8b6b  jnz     short loc_1803A8B94
0x1803a8b6d  lea     rcx, [r14+8]
0x1803a8b71  cmp     rcx, r14
0x1803a8b74  jb      short loc_1803A8B94
0x1803a8b76  mov     rax, cs:g_pfnAllocate
0x1803a8b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a8b82  mov     rbx, rax
0x1803a8b85  test    rax, rax
0x1803a8b88  jz      short loc_1803A8B94
0x1803a8b8a  mov     dword ptr [rax], 70616548h
0x1803a8b90  add     rbx, 8
0x1803a8b94  cmp     [rbp+100h+dwPrimaryGroupSize], r13d
0x1803a8b98  jbe     short loc_1803A8BAA
0x1803a8b9a  test    rbx, rbx
0x1803a8b9d  jnz     short loc_1803A8BAA
0x1803a8b9f  mov     dword ptr [rsi], 8
0x1803a8ba5  jmp     loc_1803A8D4F
0x1803a8baa  lea     rax, [rbp+100h+dwPrimaryGroupSize]
0x1803a8bae  mov     r9, r15; pDacl
0x1803a8bb1  mov     [rsp+160h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1803a8bb6  lea     r8, [rbp+100h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1803a8bba  mov     [rsp+160h+pPrimaryGroup], rbx; pPrimaryGroup
0x1803a8bbf  lea     rax, [rbp+100h+dwOwnerSize]
0x1803a8bc3  mov     [rsp+160h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1803a8bc8  lea     rdx, [rbp+100h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1803a8bcf  mov     [rsp+160h+pOwner], rdi; pOwner
0x1803a8bd4  lea     rax, [rbp+100h+dwSaclSize]
0x1803a8bd8  mov     [rsp+160h+lpdwSaclSize], rax; lpdwSaclSize
0x1803a8bdd  mov     rcx, r12; pSelfRelativeSecurityDescriptor
0x1803a8be0  mov     rax, [rbp+100h+var_F0]
0x1803a8be4  mov     [rsp+160h+pSacl], rax; pSacl
0x1803a8be9  lea     rax, [rbp+100h+dwDaclSize]
0x1803a8bed  mov     [rsp+160h+lpdwDaclSize], rax; lpdwDaclSize
0x1803a8bf2  call    cs:__imp_MakeAbsoluteSD
0x1803a8bf8  test    eax, eax
0x1803a8bfa  jnz     short loc_1803A8C09
0x1803a8bfc  call    cs:__imp_GetLastError
0x1803a8c02  mov     [rsi], eax
0x1803a8c04  jmp     loc_1803A8D4F
0x1803a8c09  lea     rax, [rbp+100h+pSid]
0x1803a8c0d  mov     r9d, 224h; nSubAuthority1
0x1803a8c13  mov     [rsp+160h+lpdwPrimaryGroupSize], rax; pSid
0x1803a8c18  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x1803a8c1f  mov     dword ptr [rsp+160h+pPrimaryGroup], r13d; nSubAuthority7
0x1803a8c24  mov     r8d, 20h ; ' '; nSubAuthority0
0x1803a8c2a  mov     dword ptr [rsp+160h+lpdwOwnerSize], r13d; nSubAuthority6
0x1803a8c2f  mov     dl, 2; nSubAuthorityCount
0x1803a8c31  mov     dword ptr [rsp+160h+pOwner], r13d; nSubAuthority5
0x1803a8c36  mov     dword ptr [rsp+160h+lpdwSaclSize], r13d; nSubAuthority4
0x1803a8c3b  mov     dword ptr [rsp+160h+pSacl], r13d; nSubAuthority3
0x1803a8c40  mov     dword ptr [rsp+160h+lpdwDaclSize], r13d; nSubAuthority2
0x1803a8c45  call    cs:__imp_AllocateAndInitializeSid
0x1803a8c4b  test    eax, eax
0x1803a8c4d  jz      loc_1803A8B9F
0x1803a8c53  test    r15, r15
0x1803a8c56  jz      loc_1803A8D4F
0x1803a8c5c  movzx   r13d, word ptr [r15+4]
0x1803a8c61  test    r13d, r13d
0x1803a8c64  jz      loc_1803A8D4C
0x1803a8c6a  xor     r12d, r12d
0x1803a8c6d  lea     r14, [r15+8]
0x1803a8c71  cmp     r12d, r13d
0x1803a8c74  jnb     short loc_1803A8CB7
0x1803a8c76  cmp     byte ptr [r14], 0
0x1803a8c7a  jnz     short loc_1803A8CA1
0x1803a8c7c  mov     rcx, [rbp+100h+pSid]; Sid1
0x1803a8c80  lea     rdx, [r14+8]; Sid2
0x1803a8c84  call    cs:__imp_RtlEqualSid
0x1803a8c8a  test    al, al
0x1803a8c8c  jz      short loc_1803A8CA1
0x1803a8c8e  mov     ecx, [r14+4]; GrantedAccess
0x1803a8c92  mov     edx, 0F01FFh; DesiredAccess
0x1803a8c97  call    cs:__imp_AreAllAccessesGranted
0x1803a8c9d  test    eax, eax
0x1803a8c9f  jnz     short loc_1803A8CAE
0x1803a8ca1  movzx   eax, word ptr [r14+2]
0x1803a8ca6  inc     r12d
0x1803a8ca9  add     r14, rax
0x1803a8cac  jmp     short loc_1803A8C71
0x1803a8cae  mov     rax, [rbp+100h+var_D0]
0x1803a8cb2  mov     byte ptr [rax], 1
0x1803a8cb5  jmp     short loc_1803A8CBB
0x1803a8cb7  mov     rax, [rbp+100h+var_D0]
0x1803a8cbb  xor     r13d, r13d
0x1803a8cbe  cmp     [rax], r13b
0x1803a8cc1  jz      loc_1803A8D4F
0x1803a8cc7  mov     rax, [rbp+100h+pSid]
0x1803a8ccb  lea     r9, [rbp+100h+NewAcl]; NewAcl
0x1803a8ccf  mov     r8, r15; OldAcl
0x1803a8cd2  mov     [rbp+100h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1803a8cd6  lea     rdx, [rbp+100h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1803a8cda  mov     [rbp+100h+pListOfExplicitEntries.grfAccessMode], 4
0x1803a8ce1  lea     ecx, [r13+1]; cCountOfExplicitEntries
0x1803a8ce5  mov     [rbp+100h+pListOfExplicitEntries.grfAccessPermissions], 0F01FFh
0x1803a8cec  mov     [rbp+100h+pListOfExplicitEntries.grfInheritance], r13d
0x1803a8cf0  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x1803a8cf4  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1803a8cfb  mov     [rbp+100h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r13d
0x1803a8cff  mov     [rbp+100h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r13
0x1803a8d03  call    cs:__imp_SetEntriesInAclW
0x1803a8d09  mov     [rsi], eax
0x1803a8d0b  test    eax, eax
0x1803a8d0d  jnz     short loc_1803A8D4F
0x1803a8d0f  mov     r8, [rbp+100h+NewAcl]; pDacl
0x1803a8d13  lea     edx, [rax+1]; bDaclPresent
0x1803a8d16  xor     r9d, r9d; bDaclDefaulted
0x1803a8d19  lea     rcx, [rbp+100h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x1803a8d20  call    cs:__imp_SetSecurityDescriptorDacl
0x1803a8d26  test    eax, eax
0x1803a8d28  jz      loc_1803A8BFC
0x1803a8d2e  mov     r8, [rbp+100h+lpdwBufferLength]; lpdwBufferLength
0x1803a8d32  lea     rcx, [rbp+100h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1803a8d39  mov     rdx, [rbp+100h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1803a8d3d  call    cs:__imp_MakeSelfRelativeSD
0x1803a8d43  test    eax, eax
0x1803a8d45  jnz     short loc_1803A8D4F
0x1803a8d47  jmp     loc_1803A8BFC
0x1803a8d4c  xor     r13d, r13d
0x1803a8d4f  test    rdi, rdi
0x1803a8d52  jz      short loc_1803A8D6C
0x1803a8d54  lea     rcx, [rdi-8]
0x1803a8d58  cmp     dword ptr [rcx], 70616548h
0x1803a8d5e  jnz     short loc_1803A8D6C
0x1803a8d60  mov     rax, cs:g_pfnFree
0x1803a8d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a8d6c  test    rbx, rbx
0x1803a8d6f  jz      short loc_1803A8D89
0x1803a8d71  lea     rcx, [rbx-8]
0x1803a8d75  cmp     dword ptr [rcx], 70616548h
0x1803a8d7b  jnz     short loc_1803A8D89
0x1803a8d7d  mov     rax, cs:g_pfnFree
0x1803a8d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a8d89  mov     rbx, [rbp+100h+var_F0]
0x1803a8d8d  mov     rcx, [rbp+100h+NewAcl]; hMem
0x1803a8d91  test    rcx, rcx
0x1803a8d94  jz      short loc_1803A8D9C
0x1803a8d96  call    cs:__imp_LocalFree
0x1803a8d9c  mov     rcx, [rbp+100h+pSid]; hMem
0x1803a8da0  test    rcx, rcx
0x1803a8da3  jz      short loc_1803A8DAB
0x1803a8da5  call    cs:__imp_LocalFree
0x1803a8dab  test    r15, r15
  ... truncated ...
```
