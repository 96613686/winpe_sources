# FaSetAce

- ea: `0x1800244a4`
- end: `0x1800247ee`
- name: `FaSetAce`
- size: `842`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800243c8`

## callees

- `0x1800244a4`
- `0x1800254e0`
- `0x180026388`
- `0x180026394`
- `0x18002a898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024797`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ba`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002465a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002465a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024606`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024630`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024606`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024630`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800245c1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800245c1`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18002478b`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18002478b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800246bc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800246bc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002476d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002476d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180024754`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180024754`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002451e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002458b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002451e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002458b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002469c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002469c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002472a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002472a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800246ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800246ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800247ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800247b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800247ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800247b4`
- `api-ms-win-security-base-private-l1-1-0!MakeAbsoluteSD2` at `0x1800245a1`
- `api-ms-win-security-base-private-l1-1-0!MakeAbsoluteSD2` at `0x1800245a1`

## pseudocode

```c
DWORD __fastcall FaSetAce(LPCWSTR lpFileName, __int64 a2, int a3, void *a4)
{
  DWORD v7; // eax
  DWORD v8; // ecx
  _WORD *v9; // rbx
  struct _ACL *v10; // rcx
  DWORD v11; // r15d
  DWORD i; // edi
  __int16 LengthSid; // ax
  PACL v14; // r14
  unsigned __int16 v15; // ax
  int v16; // edi
  __int64 v17; // rdi
  struct _ACL *v18; // rax
  PACL pDacl; // [rsp+30h] [rbp-99h] BYREF
  DWORD nLengthNeeded; // [rsp+38h] [rbp-91h] BYREF
  DWORD v22; // [rsp+3Ch] [rbp-8Dh] BYREF
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-89h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+44h] [rbp-85h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-81h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-71h]
  __int16 pAceList; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int16 v29; // [rsp+62h] [rbp-67h] BYREF
  int v30; // [rsp+64h] [rbp-65h]
  _BYTE pDestinationSid[120]; // [rsp+68h] [rbp-61h] BYREF

  pDacl = 0;
  pAclInformation = 0;
  v27 = 0;
  nLengthNeeded = 0;
  v22 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( lpFileName && a4 )
  {
    if ( GetFileSecurityW(lpFileName, 4u, 0, 0, &nLengthNeeded) )
    {
      v7 = nLengthNeeded;
    }
    else
    {
      if ( GetLastError() != 122 )
        return GetLastError();
      v7 = nLengthNeeded;
      if ( nLengthNeeded > 0x10000 )
      {
        v8 = 1336;
LABEL_7:
        SetLastError(v8);
        return GetLastError();
      }
    }
    v22 = v7 + 128;
    v9 = LocalAlloc(0, v7 + 128);
    if ( !v9 )
    {
      v8 = 8;
      goto LABEL_7;
    }
    if ( !GetFileSecurityW(lpFileName, 4u, v9, nLengthNeeded, &nLengthNeeded)
      || !(unsigned int)MakeAbsoluteSD2(v9, &v22) )
    {
LABEL_45:
      LocalFree(v9);
      return GetLastError();
    }
    if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      pDacl = 0;
      goto LABEL_45;
    }
    if ( bDaclPresent )
    {
      v10 = pDacl;
    }
    else
    {
      v10 = 0;
      pDacl = 0;
    }
    if ( v10 )
    {
      if ( !GetAclInformation(v10, &pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_45;
      FapRemoveAcesForTypeAndFlagsAndSid(pDacl);
      if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_45;
      v11 = -1;
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        pAce = 0;
        if ( !GetAce(pDacl, i, &pAce) )
          goto LABEL_45;
        if ( (*((_BYTE *)pAce + 1) & 0x10) != 0 )
        {
          v11 = i;
          break;
        }
      }
    }
    else
    {
      pAclInformation = 0;
      v11 = 0;
      v27 = 0;
    }
    memset_0(&v29, 0, 0x7Eu);
    pAceList = 0;
    LengthSid = GetLengthSid(a4);
    v30 = a3;
    v29 = LengthSid + 8;
    CopySid(0x78u, pDestinationSid, a4);
    v14 = pDacl;
    if ( pDacl )
    {
      v15 = v29;
      v16 = 0;
      if ( v27 >= v29 )
        goto LABEL_38;
      v17 = (unsigned int)v29 + HIDWORD(pAclInformation);
    }
    else
    {
      v17 = v29 + 8LL;
    }
    v18 = (struct _ACL *)LocalAlloc(0, v17);
    v14 = v18;
    if ( !v18 )
    {
      SetLastError(8u);
      goto LABEL_45;
    }
    if ( pDacl )
    {
      memmove_0(v18, pDacl, HIDWORD(pAclInformation));
      v14->AclSize = v17;
    }
    else
    {
      InitializeAcl(v18, v17, 2u);
    }
    v15 = v29;
    v16 = 1;
    pDacl = v14;
LABEL_38:
    if ( AddAce(v14, 2u, v11, &pAceList, v15) )
    {
      if ( SetSecurityDescriptorDacl(v9, 1, pDacl, 0) )
      {
        v9[1] |= 0x100u;
        if ( SetFileSecurityW(lpFileName, 4u, v9) )
          SetLastError(0);
      }
    }
    if ( v16 )
    {
      if ( pDacl )
        LocalFree(pDacl);
    }
    goto LABEL_45;
  }
  return 87;
}

```

## disassembly

```asm
0x1800244a4  mov     [rsp-8+arg_8], rbx
0x1800244a9  push    rbp
0x1800244aa  push    rsi
0x1800244ab  push    rdi
0x1800244ac  push    r12
0x1800244ae  push    r13
0x1800244b0  push    r14
0x1800244b2  push    r15
0x1800244b4  lea     rbp, [rsp-27h]
0x1800244b9  sub     rsp, 0F0h
0x1800244c0  mov     rax, cs:__security_cookie
0x1800244c7  xor     rax, rsp
0x1800244ca  mov     [rbp+57h+var_40], rax
0x1800244ce  xor     esi, esi
0x1800244d0  xor     eax, eax
0x1800244d2  mov     [rsp+120h+pDacl], rsi
0x1800244d7  mov     r14, r9
0x1800244da  mov     [rbp+57h+pAclInformation], rax
0x1800244de  mov     r13d, r8d
0x1800244e1  mov     [rbp+57h+var_C8], eax
0x1800244e4  mov     r12, rcx
0x1800244e7  mov     [rsp+120h+nLengthNeeded], esi
0x1800244eb  mov     [rsp+120h+var_E4], esi
0x1800244ef  mov     [rsp+120h+bDaclPresent], esi
0x1800244f3  mov     [rsp+120h+bDaclDefaulted], esi
0x1800244f7  test    rcx, rcx
0x1800244fa  jz      loc_1800247C2
0x180024500  test    r9, r9
0x180024503  jz      loc_1800247C2
0x180024509  lea     rax, [rsp+120h+nLengthNeeded]
0x18002450e  xor     r9d, r9d; nLength
0x180024511  lea     edi, [rsi+4]
0x180024514  mov     [rsp+120h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180024519  mov     edx, edi; RequestedInformation
0x18002451b  xor     r8d, r8d; pSecurityDescriptor
0x18002451e  call    cs:__imp_GetFileSecurityW
0x180024524  test    eax, eax
0x180024526  jnz     short loc_180024552
0x180024528  call    cs:__imp_GetLastError
0x18002452e  cmp     eax, 7Ah ; 'z'
0x180024531  jnz     loc_1800247BA
0x180024537  mov     eax, [rsp+120h+nLengthNeeded]
0x18002453b  cmp     eax, 10000h
0x180024540  jbe     short loc_180024556
0x180024542  mov     ecx, 538h; dwErrCode
0x180024547  call    cs:__imp_SetLastError
0x18002454d  jmp     loc_1800247BA
0x180024552  mov     eax, [rsp+120h+nLengthNeeded]
0x180024556  sub     eax, 0FFFFFF80h
0x180024559  xor     ecx, ecx; uFlags
0x18002455b  mov     edx, eax; uBytes
0x18002455d  mov     [rsp+120h+var_E4], eax
0x180024561  call    cs:__imp_LocalAlloc
0x180024567  mov     rbx, rax
0x18002456a  test    rax, rax
0x18002456d  jnz     short loc_180024574
0x18002456f  lea     ecx, [rax+8]
0x180024572  jmp     short loc_180024547
0x180024574  mov     r9d, [rsp+120h+nLengthNeeded]; nLength
0x180024579  lea     rax, [rsp+120h+nLengthNeeded]
0x18002457e  mov     r8, rbx; pSecurityDescriptor
0x180024581  mov     [rsp+120h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180024586  mov     edx, edi; RequestedInformation
0x180024588  mov     rcx, r12; lpFileName
0x18002458b  call    cs:__imp_GetFileSecurityW
0x180024591  test    eax, eax
0x180024593  jz      loc_1800247B1
0x180024599  lea     rdx, [rsp+120h+var_E4]
0x18002459e  mov     rcx, rbx
0x1800245a1  call    cs:__imp_MakeAbsoluteSD2
0x1800245a7  test    eax, eax
0x1800245a9  jz      loc_1800247B1
0x1800245af  lea     r9, [rsp+120h+bDaclDefaulted]; lpbDaclDefaulted
0x1800245b4  mov     rcx, rbx; pSecurityDescriptor
0x1800245b7  lea     r8, [rsp+120h+pDacl]; pDacl
0x1800245bc  lea     rdx, [rsp+120h+bDaclPresent]; lpbDaclPresent
0x1800245c1  call    cs:__imp_GetSecurityDescriptorDacl
0x1800245c7  test    eax, eax
0x1800245c9  jnz     short loc_1800245D5
0x1800245cb  mov     [rsp+120h+pDacl], rsi
0x1800245d0  jmp     loc_1800247B1
0x1800245d5  cmp     [rsp+120h+bDaclPresent], esi
0x1800245d9  jnz     short loc_1800245E5
0x1800245db  mov     rcx, rsi
0x1800245de  mov     [rsp+120h+pDacl], rcx
0x1800245e3  jmp     short loc_1800245EA
0x1800245e5  mov     rcx, [rsp+120h+pDacl]; pAcl
0x1800245ea  mov     edi, 2
0x1800245ef  test    rcx, rcx
0x1800245f2  jz      loc_18002467C
0x1800245f8  lea     r15d, [rdi+0Ah]
0x1800245fc  mov     r9d, edi; dwAclInformationClass
0x1800245ff  mov     r8d, r15d; nAclInformationLength
0x180024602  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180024606  call    cs:__imp_GetAclInformation
0x18002460c  test    eax, eax
0x18002460e  jz      loc_1800247B1
0x180024614  mov     rcx, [rsp+120h+pDacl]; pAcl
0x180024619  mov     r9, r14
0x18002461c  call    FapRemoveAcesForTypeAndFlagsAndSid
0x180024621  mov     rcx, [rsp+120h+pDacl]; pAcl
0x180024626  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x18002462a  mov     r9d, edi; dwAclInformationClass
0x18002462d  mov     r8d, r15d; nAclInformationLength
0x180024630  call    cs:__imp_GetAclInformation
0x180024636  test    eax, eax
0x180024638  jz      loc_1800247B1
0x18002463e  or      r15d, 0FFFFFFFFh
0x180024642  mov     edi, esi
0x180024644  cmp     edi, dword ptr [rbp+57h+pAclInformation]
0x180024647  jnb     short loc_180024686
0x180024649  mov     rcx, [rsp+120h+pDacl]; pAcl
0x18002464e  lea     r8, [rsp+120h+pAce]; pAce
0x180024653  mov     edx, edi; dwAceIndex
0x180024655  mov     [rsp+120h+pAce], rsi
0x18002465a  call    cs:__imp_GetAce
0x180024660  test    eax, eax
0x180024662  jz      loc_1800247B1
0x180024668  mov     rax, [rsp+120h+pAce]
0x18002466d  test    byte ptr [rax+1], 10h
0x180024671  jnz     short loc_180024677
0x180024673  inc     edi
0x180024675  jmp     short loc_180024644
0x180024677  mov     r15d, edi
0x18002467a  jmp     short loc_180024686
0x18002467c  mov     [rbp+57h+pAclInformation], rsi
0x180024680  mov     r15d, esi
0x180024683  mov     [rbp+57h+var_C8], esi
0x180024686  xor     edx, edx; Val
0x180024688  lea     rcx, [rbp+57h+var_BE]; void *
0x18002468c  lea     r8d, [rdx+7Eh]; Size
0x180024690  call    memset_0
0x180024695  mov     rcx, r14; pSid
0x180024698  mov     [rbp+57h+pAceList], si
0x18002469c  call    cs:__imp_GetLengthSid
0x1800246a2  mov     esi, 8
0x1800246a7  mov     [rbp+57h+var_BC], r13d
0x1800246ab  add     ax, si
0x1800246ae  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x1800246b2  mov     r8, r14; pSourceSid
0x1800246b5  mov     [rbp+57h+var_BE], ax
0x1800246b9  lea     ecx, [rsi+70h]; nDestinationSidLength
0x1800246bc  call    cs:__imp_CopySid
0x1800246c2  mov     r14, [rsp+120h+pDacl]
0x1800246c7  test    r14, r14
0x1800246ca  jz      short loc_1800246DE
0x1800246cc  movzx   eax, [rbp+57h+var_BE]
0x1800246d0  xor     edi, edi
0x1800246d2  cmp     [rbp+57h+var_C8], eax
0x1800246d5  jnb     short loc_18002473E
0x1800246d7  mov     edi, dword ptr [rbp+57h+pAclInformation+4]
0x1800246da  add     edi, eax
0x1800246dc  jmp     short loc_1800246E5
0x1800246de  movzx   edi, [rbp+57h+var_BE]
0x1800246e2  add     rdi, rsi
0x1800246e5  mov     rdx, rdi; uBytes
0x1800246e8  xor     ecx, ecx; uFlags
0x1800246ea  call    cs:__imp_LocalAlloc
0x1800246f0  mov     r14, rax
0x1800246f3  test    rax, rax
0x1800246f6  jnz     short loc_180024705
0x1800246f8  mov     ecx, esi; dwErrCode
0x1800246fa  call    cs:__imp_SetLastError
0x180024700  jmp     loc_1800247B1
0x180024705  mov     rdx, [rsp+120h+pDacl]; Src
0x18002470a  mov     rcx, r14; void *
0x18002470d  test    rdx, rdx
0x180024710  jz      short loc_180024722
0x180024712  mov     r8d, dword ptr [rbp+57h+pAclInformation+4]; Size
0x180024716  call    memmove_0
0x18002471b  mov     [r14+2], di
0x180024720  jmp     short loc_180024730
0x180024722  mov     edx, edi; nAclLength
0x180024724  mov     r8d, 2; dwAclRevision
0x18002472a  call    cs:__imp_InitializeAcl
0x180024730  movzx   eax, [rbp+57h+var_BE]
0x180024734  mov     edi, 1
0x180024739  mov     [rsp+120h+pDacl], r14
0x18002473e  movzx   eax, ax
0x180024741  lea     r9, [rbp+57h+pAceList]; pAceList
0x180024745  mov     r8d, r15d; dwStartingAceIndex
0x180024748  mov     dword ptr [rsp+120h+lpnLengthNeeded], eax; nAceListLength
0x18002474c  mov     edx, 2; dwAceRevision
0x180024751  mov     rcx, r14; pAcl
0x180024754  call    cs:__imp_AddAce
0x18002475a  test    eax, eax
0x18002475c  jz      short loc_18002479D
0x18002475e  mov     r8, [rsp+120h+pDacl]; pDacl
0x180024763  xor     r9d, r9d; bDaclDefaulted
0x180024766  mov     rcx, rbx; pSecurityDescriptor
0x180024769  lea     edx, [r9+1]; bDaclPresent
0x18002476d  call    cs:__imp_SetSecurityDescriptorDacl
0x180024773  test    eax, eax
0x180024775  jz      short loc_18002479D
0x180024777  mov     eax, 100h
0x18002477c  mov     r8, rbx; pSecurityDescriptor
0x18002477f  or      [rbx+2], ax
0x180024783  mov     edx, 4; SecurityInformation
0x180024788  mov     rcx, r12; lpFileName
0x18002478b  call    cs:__imp_SetFileSecurityW
0x180024791  test    eax, eax
0x180024793  jz      short loc_18002479D
0x180024795  xor     ecx, ecx; dwErrCode
0x180024797  call    cs:__imp_SetLastError
0x18002479d  test    edi, edi
0x18002479f  jz      short loc_1800247B1
0x1800247a1  mov     rcx, [rsp+120h+pDacl]; hMem
0x1800247a6  test    rcx, rcx
0x1800247a9  jz      short loc_1800247B1
0x1800247ab  call    cs:__imp_LocalFree
0x1800247b1  mov     rcx, rbx; hMem
0x1800247b4  call    cs:__imp_LocalFree
0x1800247ba  call    cs:__imp_GetLastError
0x1800247c0  jmp     short loc_1800247C7
0x1800247c2  mov     eax, 57h ; 'W'
0x1800247c7  mov     rcx, [rbp+57h+var_40]
0x1800247cb  xor     rcx, rsp; StackCookie
0x1800247ce  call    __security_check_cookie
0x1800247d3  mov     rbx, [rsp+120h+arg_8]
0x1800247db  add     rsp, 0F0h
0x1800247e2  pop     r15
0x1800247e4  pop     r14
0x1800247e6  pop     r13
0x1800247e8  pop     r12
0x1800247ea  pop     rdi
0x1800247eb  pop     rsi
0x1800247ec  pop     rbp
0x1800247ed  retn
```
