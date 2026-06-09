# GetSecurityDescriptor(char *,ulong &,sdSecurityDescriptor,Bool)

- ea: `0x14000580c`
- end: `0x14000629d`
- name: `?GetSecurityDescriptor@@YAKPEADAEAKW4sdSecurityDescriptor@@W4Bool@@@Z`
- size: `2705`
- prototype: `unsigned int __high(char *, unsigned int *, enum sdSecurityDescriptor, enum Bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400011e4`
- `0x1400057a0`
- `0x1400078f0`

## callees

- `0x140003883`
- `0x140003b44`
- `0x140003ba0`
- `0x140003c3c`
- `0x140003c64`
- `0x14000580c`
- `0x140009820`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140006195`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140006195`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1400061eb`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1400061eb`
- `ADVAPI32!AddAccessAllowedAce` at `0x140006093`
- `ADVAPI32!AddAccessAllowedAce` at `0x140006093`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1400061a8`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1400061a8`
- `ADVAPI32!GetLengthSid` at `0x140005fa7`
- `ADVAPI32!GetLengthSid` at `0x140005fa7`
- `ADVAPI32!InitializeAcl` at `0x140006033`
- `ADVAPI32!InitializeAcl` at `0x140006033`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140006140`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140006140`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005905`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005950`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400059a0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400059eb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005a32`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ad2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005b1d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005b69`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005bef`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005c3b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ccb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005d1b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005d62`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005df6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005e42`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ec4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f0e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f5e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005905`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005950`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400059a0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400059eb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005a32`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ad2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005b1d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005b69`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005bef`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005c3b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ccb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005d1b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005d62`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005df6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005e42`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005ec4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f0e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f5e`
- `ADVAPI32!GetAce` at `0x1400060b1`
- `ADVAPI32!GetAce` at `0x1400060b1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140006177`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140006177`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000615e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000615e`
- `KERNEL32!GetLastError` at `0x140005a71`
- `KERNEL32!GetLastError` at `0x140005b8d`
- `KERNEL32!GetLastError` at `0x140005c69`
- `KERNEL32!GetLastError` at `0x140005d94`
- `KERNEL32!GetLastError` at `0x140005e62`
- `KERNEL32!GetLastError` at `0x14000603d`
- `KERNEL32!GetLastError` at `0x1400060c8`
- `KERNEL32!GetLastError` at `0x1400060f7`
- `KERNEL32!GetLastError` at `0x1400061f9`
- `KERNEL32!GetLastError` at `0x140006225`
- `KERNEL32!GetLastError` at `0x140006251`
- `KERNEL32!GetLastError` at `0x140005a71`
- `KERNEL32!GetLastError` at `0x140005b8d`
- `KERNEL32!GetLastError` at `0x140005c69`
- `KERNEL32!GetLastError` at `0x140005d94`
- `KERNEL32!GetLastError` at `0x140005e62`
- `KERNEL32!GetLastError` at `0x14000603d`
- `KERNEL32!GetLastError` at `0x1400060c8`
- `KERNEL32!GetLastError` at `0x1400060f7`
- `KERNEL32!GetLastError` at `0x1400061f9`
- `KERNEL32!GetLastError` at `0x140006225`
- `KERNEL32!GetLastError` at `0x140006251`
- `KERNEL32!GlobalAlloc` at `0x140005fe0`
- `KERNEL32!GlobalAlloc` at `0x140005fe0`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(void *a1, DWORD *a2, int a3)
{
  __int64 v3; // rbx
  __int64 v4; // r14
  PSID *v5; // rsi
  void *v8; // r15
  PSID v9; // r12
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // r14d
  signed int v15; // edi
  PSID *pSid; // rax
  PSID *v17; // rax
  PSID *v18; // rax
  PSID *v19; // rax
  PSID *v20; // rax
  DWORD LastError; // esi
  _QWORD *v22; // rdi
  PSID *v23; // rax
  PSID *v24; // rax
  PSID *v25; // rax
  int v26; // eax
  _QWORD *v27; // rdi
  PSID *v28; // rax
  PSID *v29; // rax
  _QWORD *v30; // rdi
  PSID *v31; // rax
  PSID *v32; // rax
  PSID *v33; // rax
  _QWORD *v34; // rdi
  PSID *v35; // rax
  PSID *v36; // rax
  _QWORD *v37; // rdi
  PSID *v38; // rax
  PSID *v39; // rax
  PSID *v40; // rax
  int v41; // esi
  DWORD LengthSid; // eax
  struct _ACL *p_pAcl; // rax
  _QWORD *v44; // rdi
  _QWORD *v46; // rdi
  signed int i; // edi
  _QWORD *v48; // rdi
  _QWORD *v49; // rdi
  _QWORD *v50; // rdi
  _QWORD *v51; // rdi
  _QWORD *v52; // rdi
  _QWORD *v53; // rdi
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+68h] [rbp-98h]
  _OWORD pSecurityDescriptor[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v59; // [rsp+A0h] [rbp-60h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp-50h] BYREF
  int v61; // [rsp+B8h] [rbp-48h]
  struct _ACL pAcl; // [rsp+C0h] [rbp-40h] BYREF
  PSID v63; // [rsp+2C0h] [rbp+1C0h] BYREF
  DWORD AccessMask[2]; // [rsp+2C8h] [rbp+1C8h]
  void *v65; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v66; // [rsp+2D8h] [rbp+1D8h]
  void *v67; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v68; // [rsp+2E8h] [rbp+1E8h]
  char v69[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v70; // [rsp+2F8h] [rbp+1F8h]
  char v71[8]; // [rsp+300h] [rbp+200h] BYREF
  int v72; // [rsp+308h] [rbp+208h]
  _QWORD v73[8]; // [rsp+310h] [rbp+210h] BYREF

  v3 = 5;
  pSelfRelativeSecurityDescriptor = a1;
  v4 = 5;
  v5 = &v63;
  v8 = 0;
  do
  {
    GetSecurityDescriptor_::_2_::Security::Security(v5);
    v5 += 2;
    --v4;
  }
  while ( v4 );
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v9 = 0;
  *(_DWORD *)v59.Value = 0;
  *(_WORD *)&v59.Value[4] = 256;
  if ( !a3 )
  {
    v38 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v38)
      || (v39 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
          !AllocateAndInitializeSid(&v59, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v39))
      || (v40 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v67),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v40)) )
    {
      LastError = GetLastError();
      v53 = v73;
      do
      {
        v53 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v53);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    v26 = 2031615;
    v66 = -1609433088;
    AccessMask[0] = 2031615;
LABEL_50:
    v8 = v67;
    v68 = v26;
LABEL_51:
    v14 = 3;
    goto LABEL_52;
  }
  v10 = a3 - 1;
  if ( !v10 )
  {
    v35 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v35)
      || (v36 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v36)) )
    {
      LastError = GetLastError();
      v37 = v73;
      do
      {
        v37 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v37);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    AccessMask[0] = 2031615;
    v66 = 2031615;
LABEL_29:
    v8 = v65;
    v14 = 2;
    goto LABEL_52;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v31 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v31)
      || (v32 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v32))
      || (v33 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v67),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, v33)) )
    {
      LastError = GetLastError();
      v34 = v73;
      do
      {
        v34 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v34);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    v9 = v63;
    v8 = v65;
    AccessMask[0] = 1;
    v66 = 1;
    v68 = 1;
    goto LABEL_51;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v28 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v28)
      || (v29 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v29)) )
    {
      LastError = GetLastError();
      v30 = v73;
      do
      {
        v30 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v30);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    v9 = v63;
    AccessMask[0] = 1;
    v66 = 1;
    goto LABEL_29;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v23 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
    if ( !AllocateAndInitializeSid(&v59, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v23)
      || (v24 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v24))
      || (v25 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v67),
          !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v25)) )
    {
      LastError = GetLastError();
      v27 = v73;
      do
      {
        v27 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v27);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    v26 = 0x10000000;
    AccessMask[0] = 131099;
    v66 = 0x10000000;
    goto LABEL_50;
  }
  if ( v13 != 1 )
  {
    v14 = 0;
    v15 = 8;
    goto LABEL_54;
  }
  pSid = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v63);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, pSid)
    || (v17 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v65),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v17))
    || (v18 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v67),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v18))
    || (v19 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(v69),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, v19))
    || (v20 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(v71),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, v20)) )
  {
    LastError = GetLastError();
    v22 = v73;
    do
    {
      v22 -= 2;
      GetSecurityDescriptor_::_2_::Security::_Security(v22);
      --v3;
    }
    while ( v3 );
    return LastError;
  }
  v8 = v67;
  AccessMask[0] = 1;
  v9 = v67;
  v66 = 1;
  v68 = 1;
  v70 = 1;
  v72 = 1;
  v14 = 5;
LABEL_52:
  v41 = 0;
  v15 = 8;
  do
  {
    LengthSid = GetLengthSid(*(PSID *)&AccessMask[4 * v41++ - 2]);
    v15 += LengthSid + 8;
  }
  while ( v41 < v14 );
LABEL_54:
  memset_0(&pAcl, 0, 0x200u);
  v61 = 512;
  p_pAcl = &pAcl;
  pDacl = &pAcl;
  if ( v15 > 512 )
  {
    p_pAcl = (struct _ACL *)GlobalAlloc(0, v15);
    pDacl = p_pAcl;
    v61 = p_pAcl != 0 ? v15 : 0;
    if ( !p_pAcl )
    {
      CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
      v44 = v73;
      do
      {
        v44 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v44);
        --v3;
      }
      while ( v3 );
      return 14;
    }
  }
  if ( !InitializeAcl(p_pAcl, v15, 2u) )
  {
    LastError = GetLastError();
    CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
    v46 = v73;
    do
    {
      v46 -= 2;
      GetSecurityDescriptor_::_2_::Security::_Security(v46);
      --v3;
    }
    while ( v3 );
    return LastError;
  }
  for ( i = 0; i < v14; ++i )
  {
    if ( !AddAccessAllowedAce(pDacl, 2u, AccessMask[4 * i], *(PSID *)&AccessMask[4 * i - 2]) )
    {
      LastError = GetLastError();
      CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
      v49 = v73;
      do
      {
        v49 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v49);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    pAce = 0;
    if ( !GetAce(pDacl, i, &pAce) )
    {
      LastError = GetLastError();
      CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
      v48 = v73;
      do
      {
        v48 -= 2;
        GetSecurityDescriptor_::_2_::Security::_Security(v48);
        --v3;
      }
      while ( v3 );
      return LastError;
    }
    *((_BYTE *)pAce + 1) = 3;
  }
  v57 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)
    || !SetSecurityDescriptorOwner(pSecurityDescriptor, v8, 0)
    || v9 && !SetSecurityDescriptorGroup(pSecurityDescriptor, v9, 0) )
  {
    LastError = GetLastError();
    CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
    v52 = v73;
    do
    {
      v52 -= 2;
      GetSecurityDescriptor_::_2_::Security::_Security(v52);
      --v3;
    }
    while ( v3 );
    return LastError;
  }
  if ( *a2 >= GetSecurityDescriptorLength(pSecurityDescriptor) )
  {
    if ( MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, a2) )
      LastError = 0;
    else
      LastError = GetLastError();
    CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
    v51 = v73;
    do
    {
      v51 -= 2;
      GetSecurityDescriptor_::_2_::Security::_Security(v51);
      --v3;
    }
    while ( v3 );
    return LastError;
  }
  CTempBuffer<char,512>::~CTempBuffer<char,512>(&pDacl);
  v50 = v73;
  do
  {
    v50 -= 2;
    GetSecurityDescriptor_::_2_::Security::_Security(v50);
    --v3;
  }
  while ( v3 );
  return 122;
}

```

## disassembly

```asm
0x14000580c  mov     [rsp-8+arg_10], rbx
0x140005811  push    rbp
0x140005812  push    rsi
0x140005813  push    rdi
0x140005814  push    r12
0x140005816  push    r13
0x140005818  push    r14
0x14000581a  push    r15
0x14000581c  lea     rbp, [rsp-220h]
0x140005824  sub     rsp, 320h
0x14000582b  mov     rax, cs:__security_cookie
0x140005832  xor     rax, rsp
0x140005835  mov     [rbp+250h+var_40], rax
0x14000583c  mov     ebx, 5
0x140005841  mov     [rsp+350h+pSelfRelativeSecurityDescriptor], rcx
0x140005846  mov     r14d, ebx
0x140005849  lea     rsi, [rbp+250h+var_90]
0x140005850  mov     edi, r8d
0x140005853  mov     r13, rdx
0x140005856  xor     r15d, r15d
0x140005859  mov     rcx, rsi
0x14000585c  call    _GetSecurityDescriptor____2___Security__Security
0x140005861  add     rsi, 10h
0x140005865  sub     r14, 1
0x140005869  jnz     short loc_140005859
0x14000586b  mov     dword ptr [rbp+250h+pIdentifierAuthority.Value], r15d
0x14000586f  mov     r14d, 1
0x140005875  mov     word ptr [rbp+250h+pIdentifierAuthority.Value+4], 500h
0x14000587b  mov     r12, r15
0x14000587e  mov     dword ptr [rbp+250h+var_2B0.Value], r15d
0x140005882  mov     word ptr [rbp+250h+var_2B0.Value+4], 100h
0x140005888  lea     esi, [r14+1]
0x14000588c  test    edi, edi
0x14000588e  jz      loc_140005E87
0x140005894  sub     edi, r14d
0x140005897  jz      loc_140005DB9
0x14000589d  sub     edi, r14d
0x1400058a0  jz      loc_140005C8E
0x1400058a6  sub     edi, r14d
0x1400058a9  jz      loc_140005BB2
0x1400058af  sub     edi, r14d
0x1400058b2  jz      loc_140005A96
0x1400058b8  cmp     edi, r14d
0x1400058bb  jz      short loc_1400058C8
0x1400058bd  mov     r14d, r15d
0x1400058c0  lea     edi, [rsi+6]
0x1400058c3  jmp     loc_140005FB9
0x1400058c8  lea     rcx, [rbp+250h+var_90]
0x1400058cf  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1400058d4  mov     [rsp+350h+pSid], rax; pSid
0x1400058d9  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1400058dd  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x1400058e2  xor     r9d, r9d; nSubAuthority1
0x1400058e5  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x1400058ea  mov     dl, r14b; nSubAuthorityCount
0x1400058ed  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x1400058f2  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x1400058f7  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x1400058fc  lea     r8d, [r9+4]; nSubAuthority0
0x140005900  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005905  call    cs:__imp_AllocateAndInitializeSid
0x14000590b  test    eax, eax
0x14000590d  jz      loc_140005A71
0x140005913  lea     rcx, [rbp+250h+var_80]
0x14000591a  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x14000591f  mov     [rsp+350h+pSid], rax; pSid
0x140005924  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005928  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x14000592d  xor     r9d, r9d; nSubAuthority1
0x140005930  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005935  mov     dl, r14b; nSubAuthorityCount
0x140005938  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x14000593d  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005942  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005947  lea     r8d, [r9+12h]; nSubAuthority0
0x14000594b  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005950  call    cs:__imp_AllocateAndInitializeSid
0x140005956  test    eax, eax
0x140005958  jz      loc_140005A71
0x14000595e  lea     rcx, [rbp+250h+var_70]
0x140005965  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x14000596a  mov     [rsp+350h+pSid], rax; pSid
0x14000596f  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005973  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005978  mov     r9d, 220h; nSubAuthority1
0x14000597e  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005983  mov     r8d, 20h ; ' '; nSubAuthority0
0x140005989  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x14000598e  mov     dl, sil; nSubAuthorityCount
0x140005991  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005996  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x14000599b  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x1400059a0  call    cs:__imp_AllocateAndInitializeSid
0x1400059a6  test    eax, eax
0x1400059a8  jz      loc_140005A71
0x1400059ae  lea     rcx, [rbp+250h+var_60]
0x1400059b5  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1400059ba  mov     [rsp+350h+pSid], rax; pSid
0x1400059bf  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1400059c3  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x1400059c8  xor     r9d, r9d; nSubAuthority1
0x1400059cb  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x1400059d0  mov     dl, r14b; nSubAuthorityCount
0x1400059d3  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x1400059d8  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x1400059dd  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x1400059e2  lea     r8d, [r9+13h]; nSubAuthority0
0x1400059e6  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x1400059eb  call    cs:__imp_AllocateAndInitializeSid
0x1400059f1  test    eax, eax
0x1400059f3  jz      short loc_140005A71
0x1400059f5  lea     rcx, [rbp+250h+var_50]
0x1400059fc  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005a01  mov     [rsp+350h+pSid], rax; pSid
0x140005a06  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005a0a  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005a0f  xor     r9d, r9d; nSubAuthority1
0x140005a12  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005a17  mov     dl, r14b; nSubAuthorityCount
0x140005a1a  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005a1f  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005a24  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005a29  lea     r8d, [r9+14h]; nSubAuthority0
0x140005a2d  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005a32  call    cs:__imp_AllocateAndInitializeSid
0x140005a38  test    eax, eax
0x140005a3a  jz      short loc_140005A71
0x140005a3c  mov     r15, [rbp+250h+var_70]
0x140005a43  mov     [rbp+250h+AccessMask], r14d
0x140005a4a  mov     r12, r15
0x140005a4d  mov     [rbp+250h+var_78], r14d
0x140005a54  mov     [rbp+250h+var_68], r14d
0x140005a5b  mov     [rbp+250h+var_58], r14d
0x140005a62  mov     [rbp+250h+var_48], r14d
0x140005a69  mov     r14d, ebx
0x140005a6c  jmp     loc_140005F94
0x140005a71  call    cs:__imp_GetLastError
0x140005a77  mov     esi, eax
0x140005a79  lea     rdi, [rbp+250h+var_40]
0x140005a80  sub     rdi, 10h
0x140005a84  mov     rcx, rdi
0x140005a87  call    _GetSecurityDescriptor____2___Security___Security
0x140005a8c  sub     rbx, r14
0x140005a8f  jnz     short loc_140005A80
0x140005a91  jmp     loc_140006271
0x140005a96  lea     rcx, [rbp+250h+var_90]
0x140005a9d  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005aa2  mov     [rsp+350h+pSid], rax; pSid
0x140005aa7  lea     rcx, [rbp+250h+var_2B0]; pIdentifierAuthority
0x140005aab  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005ab0  xor     r9d, r9d; nSubAuthority1
0x140005ab3  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005ab8  xor     r8d, r8d; nSubAuthority0
0x140005abb  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005ac0  mov     dl, r14b; nSubAuthorityCount
0x140005ac3  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005ac8  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005acd  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005ad2  call    cs:__imp_AllocateAndInitializeSid
0x140005ad8  test    eax, eax
0x140005ada  jz      loc_140005B8D
0x140005ae0  lea     rcx, [rbp+250h+var_80]
0x140005ae7  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005aec  mov     [rsp+350h+pSid], rax; pSid
0x140005af1  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005af5  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005afa  xor     r9d, r9d; nSubAuthority1
0x140005afd  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005b02  mov     dl, r14b; nSubAuthorityCount
0x140005b05  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005b0a  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005b0f  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005b14  lea     r8d, [r9+12h]; nSubAuthority0
0x140005b18  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005b1d  call    cs:__imp_AllocateAndInitializeSid
0x140005b23  test    eax, eax
0x140005b25  jz      short loc_140005B8D
0x140005b27  lea     rcx, [rbp+250h+var_70]
0x140005b2e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005b33  mov     [rsp+350h+pSid], rax; pSid
0x140005b38  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005b3c  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005b41  mov     r9d, 220h; nSubAuthority1
0x140005b47  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005b4c  mov     r8d, 20h ; ' '; nSubAuthority0
0x140005b52  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005b57  mov     dl, sil; nSubAuthorityCount
0x140005b5a  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005b5f  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005b64  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005b69  call    cs:__imp_AllocateAndInitializeSid
0x140005b6f  test    eax, eax
0x140005b71  jz      short loc_140005B8D
0x140005b73  mov     eax, 10000000h
0x140005b78  mov     [rbp+250h+AccessMask], 2001Bh
0x140005b82  mov     [rbp+250h+var_78], eax
0x140005b88  jmp     loc_140005F81
0x140005b8d  call    cs:__imp_GetLastError
0x140005b93  mov     esi, eax
0x140005b95  lea     rdi, [rbp+250h+var_40]
0x140005b9c  sub     rdi, 10h
0x140005ba0  mov     rcx, rdi
0x140005ba3  call    _GetSecurityDescriptor____2___Security___Security
0x140005ba8  sub     rbx, r14
0x140005bab  jnz     short loc_140005B9C
0x140005bad  jmp     loc_140006271
0x140005bb2  lea     rcx, [rbp+250h+var_90]
0x140005bb9  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005bbe  mov     [rsp+350h+pSid], rax; pSid
0x140005bc3  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005bc7  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005bcc  xor     r9d, r9d; nSubAuthority1
0x140005bcf  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005bd4  mov     dl, r14b; nSubAuthorityCount
0x140005bd7  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005bdc  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005be1  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005be6  lea     r8d, [r9+12h]; nSubAuthority0
0x140005bea  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005bef  call    cs:__imp_AllocateAndInitializeSid
0x140005bf5  test    eax, eax
0x140005bf7  jz      short loc_140005C69
0x140005bf9  lea     rcx, [rbp+250h+var_80]
0x140005c00  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005c05  mov     [rsp+350h+pSid], rax; pSid
0x140005c0a  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005c0e  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005c13  mov     r9d, 220h; nSubAuthority1
0x140005c19  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005c1e  mov     r8d, 20h ; ' '; nSubAuthority0
0x140005c24  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005c29  mov     dl, sil; nSubAuthorityCount
0x140005c2c  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005c31  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005c36  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005c3b  call    cs:__imp_AllocateAndInitializeSid
0x140005c41  test    eax, eax
0x140005c43  jz      short loc_140005C69
0x140005c45  mov     r12, [rbp+250h+var_90]
0x140005c4c  mov     [rbp+250h+AccessMask], r14d
0x140005c53  mov     [rbp+250h+var_78], r14d
0x140005c5a  mov     r15, [rbp+250h+var_80]
0x140005c61  mov     r14d, esi
0x140005c64  jmp     loc_140005F94
0x140005c69  call    cs:__imp_GetLastError
0x140005c6f  mov     esi, eax
0x140005c71  lea     rdi, [rbp+250h+var_40]
0x140005c78  sub     rdi, 10h
0x140005c7c  mov     rcx, rdi
0x140005c7f  call    _GetSecurityDescriptor____2___Security___Security
0x140005c84  sub     rbx, r14
0x140005c87  jnz     short loc_140005C78
0x140005c89  jmp     loc_140006271
0x140005c8e  lea     rcx, [rbp+250h+var_90]
0x140005c95  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005c9a  mov     [rsp+350h+pSid], rax; pSid
0x140005c9f  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005ca3  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005ca8  xor     r9d, r9d; nSubAuthority1
0x140005cab  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005cb0  mov     dl, r14b; nSubAuthorityCount
0x140005cb3  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005cb8  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005cbd  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005cc2  lea     r8d, [r9+12h]; nSubAuthority0
0x140005cc6  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005ccb  call    cs:__imp_AllocateAndInitializeSid
0x140005cd1  test    eax, eax
0x140005cd3  jz      loc_140005D94
0x140005cd9  lea     rcx, [rbp+250h+var_80]
0x140005ce0  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005ce5  mov     [rsp+350h+pSid], rax; pSid
0x140005cea  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005cee  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005cf3  mov     r9d, 220h; nSubAuthority1
0x140005cf9  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005cfe  mov     r8d, 20h ; ' '; nSubAuthority0
0x140005d04  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005d09  mov     dl, sil; nSubAuthorityCount
0x140005d0c  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005d11  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005d16  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005d1b  call    cs:__imp_AllocateAndInitializeSid
0x140005d21  test    eax, eax
0x140005d23  jz      short loc_140005D94
0x140005d25  lea     rcx, [rbp+250h+var_70]
0x140005d2c  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x140005d31  mov     [rsp+350h+pSid], rax; pSid
0x140005d36  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x140005d3a  mov     [rsp+350h+nSubAuthority7], r15d; nSubAuthority7
0x140005d3f  xor     r9d, r9d; nSubAuthority1
0x140005d42  mov     [rsp+350h+nSubAuthority6], r15d; nSubAuthority6
0x140005d47  mov     dl, r14b; nSubAuthorityCount
0x140005d4a  mov     [rsp+350h+nSubAuthority5], r15d; nSubAuthority5
0x140005d4f  mov     [rsp+350h+nSubAuthority4], r15d; nSubAuthority4
0x140005d54  mov     [rsp+350h+nSubAuthority3], r15d; nSubAuthority3
0x140005d59  lea     r8d, [r9+4]; nSubAuthority0
0x140005d5d  mov     [rsp+350h+nSubAuthority2], r15d; nSubAuthority2
0x140005d62  call    cs:__imp_AllocateAndInitializeSid
0x140005d68  test    eax, eax
  ... truncated ...
```
