# GetSecurityDescriptor(char *,ulong &,sdSecurityDescriptor,Bool)

- ea: `0x18014c8cc`
- end: `0x18014d252`
- name: `?GetSecurityDescriptor@@YAKPEADAEAKW4sdSecurityDescriptor@@W4Bool@@@Z`
- size: `2438`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180036bb0`
- `0x1800798e4`
- `0x1800882b0`
- `0x180092930`
- `0x18012be04`
- `0x18014c81c`
- `0x1801ea40c`

## callees

- `0x180019cc0`
- `0x1800817f8`
- `0x18014c8cc`
- `0x18014d258`
- `0x18014d280`
- `0x18014d28c`
- `0x18014fcb8`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x18014d069`
- `ADVAPI32!InitializeAcl` at `0x18014d069`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014c9b8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca03`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca52`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca9d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cae4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cb6d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cbb4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cc03`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cc6e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ccbd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cd2c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cd7b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cdc6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ce36`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ce85`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cef7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cf41`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cf90`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014c9b8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca03`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca52`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ca9d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cae4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cb6d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cbb4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cc03`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cc6e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ccbd`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cd2c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cd7b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cdc6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ce36`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014ce85`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cef7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cf41`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014cf90`
- `ADVAPI32!GetLengthSid` at `0x18014cffa`
- `ADVAPI32!GetLengthSid` at `0x18014cffa`
- `ADVAPI32!AddAccessAllowedAce` at `0x18014d0a2`
- `ADVAPI32!AddAccessAllowedAce` at `0x18014d0a2`
- `ADVAPI32!GetAce` at `0x18014d0c6`
- `ADVAPI32!GetAce` at `0x18014d0c6`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18014d101`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18014d101`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18014d125`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18014d125`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18014d144`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18014d144`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18014d164`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18014d164`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18014d179`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18014d179`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18014d1af`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18014d1af`
- `KERNEL32!GetLastError` at `0x18014cb24`
- `KERNEL32!GetLastError` at `0x18014d1c3`
- `KERNEL32!GetLastError` at `0x18014d1ff`
- `KERNEL32!GetLastError` at `0x18014cb24`
- `KERNEL32!GetLastError` at `0x18014d1c3`
- `KERNEL32!GetLastError` at `0x18014d1ff`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(void *a1, DWORD *a2, int a3, int a4)
{
  __int64 v4; // r13
  __int64 v5; // rsi
  PSID *v7; // rdi
  int v9; // edi
  PSID v10; // r15
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  signed int v15; // ebx
  int v16; // esi
  void *v17; // r14
  PSID *pSid; // rax
  PSID *v19; // rax
  PSID *v20; // rax
  PSID *v21; // rax
  PSID *v22; // rax
  DWORD LastError; // ebx
  PSID *v24; // rax
  PSID *v25; // rax
  PSID *v26; // rax
  PSID *v27; // rax
  PSID *v28; // rax
  PSID *v29; // rax
  PSID *v30; // rax
  PSID *v31; // rax
  PSID *v32; // rax
  PSID *v33; // rax
  DWORD v34; // edx
  PSID *v35; // rax
  PSID *v36; // rax
  PSID *v37; // rax
  DWORD LengthSid; // eax
  struct _ACL *p_pAcl; // rcx
  signed int i; // ebx
  DWORD SecurityDescriptorLength; // eax
  DWORD v43; // edi
  __int64 *v44; // rbx
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  LPDWORD lpdwBufferLength; // [rsp+68h] [rbp-98h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+70h] [rbp-90h]
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v51; // [rsp+A8h] [rbp-58h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp-50h] BYREF
  int v53; // [rsp+B8h] [rbp-48h]
  struct _ACL pAcl; // [rsp+C0h] [rbp-40h] BYREF
  PSID v55; // [rsp+2C0h] [rbp+1C0h] BYREF
  DWORD AccessMask[2]; // [rsp+2C8h] [rbp+1C8h]
  void *v57; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v58; // [rsp+2D8h] [rbp+1D8h]
  void *v59; // [rsp+2E0h] [rbp+1E0h] BYREF
  DWORD v60; // [rsp+2E8h] [rbp+1E8h]
  char v61[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v62; // [rsp+2F8h] [rbp+1F8h]
  char v63[8]; // [rsp+300h] [rbp+200h] BYREF
  int v64; // [rsp+308h] [rbp+208h]
  __int64 v65; // [rsp+310h] [rbp+210h] BYREF

  v4 = 5;
  lpdwBufferLength = a2;
  v5 = 5;
  pSelfRelativeSecurityDescriptor = a1;
  v7 = &v55;
  do
  {
    GetSecurityDescriptor_::_2_::Security::Security(v7);
    v7 += 2;
    --v5;
  }
  while ( v5 );
  v9 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v10 = 0;
  *(_DWORD *)v51.Value = 0;
  *(_WORD *)&v51.Value[4] = 256;
  if ( a3 )
  {
    v11 = a3 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
        v29 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v29) )
          goto LABEL_16;
        v30 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v30) )
          goto LABEL_16;
        v31 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v59);
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, v31) )
          goto LABEL_16;
        v10 = v55;
        v17 = v57;
        AccessMask[0] = 1;
        v58 = 1;
        v60 = 1;
        goto LABEL_39;
      }
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 != 1 )
          {
            v15 = 8;
            v16 = 0;
            v17 = 0;
            goto LABEL_42;
          }
          pSid = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
          if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, pSid) )
          {
            v19 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
            if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v19) )
            {
              v20 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v59);
              if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v20) )
              {
                v21 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(v61);
                if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, v21) )
                {
                  v22 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(v63);
                  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, v22) )
                  {
                    v17 = v59;
                    AccessMask[0] = 1;
                    v10 = v59;
                    v58 = 1;
                    v60 = 1;
                    v62 = 1;
                    v64 = 1;
                    v16 = 5;
                    goto LABEL_40;
                  }
                }
              }
            }
          }
LABEL_16:
          LastError = GetLastError();
          goto LABEL_67;
        }
        v24 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
        if ( !AllocateAndInitializeSid(&v51, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v24) )
          goto LABEL_16;
        v25 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v25) )
          goto LABEL_16;
        v26 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v59);
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v26) )
          goto LABEL_16;
        AccessMask[0] = 131099;
        v58 = 0x10000000;
        v60 = 0x10000000;
        goto LABEL_38;
      }
      v27 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v27) )
        goto LABEL_16;
      v28 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v28) )
        goto LABEL_16;
      v10 = v55;
      v17 = v57;
      AccessMask[0] = 1;
      v58 = 1;
    }
    else
    {
      v32 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v32) )
        goto LABEL_16;
      v33 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v33) )
        goto LABEL_16;
      v17 = v57;
      v34 = 0x10000000;
      if ( !a4 )
        v34 = 2031615;
      AccessMask[0] = v34;
      v58 = v34;
    }
    v16 = 2;
    goto LABEL_40;
  }
  v35 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v55);
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v35) )
  {
    v36 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v57);
    if ( AllocateAndInitializeSid(&v51, 1u, 0, 0, 0, 0, 0, 0, 0, 0, v36) )
    {
      v37 = (PSID *)GetSecurityDescriptor_::_2_::CSIDPointer::operator&(&v59);
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v37) )
      {
        v58 = -1609433088;
        AccessMask[0] = a4 != 0 ? 0x10000000 : 2031615;
        v60 = AccessMask[0];
LABEL_38:
        v17 = v59;
LABEL_39:
        v16 = 3;
LABEL_40:
        v15 = 8;
        do
        {
          LengthSid = GetLengthSid(*(PSID *)&AccessMask[4 * v9++ - 2]);
          v15 += LengthSid + 8;
        }
        while ( v9 < v16 );
LABEL_42:
        memset_0(&pAcl, 0, 0x200u);
        v53 = 512;
        p_pAcl = &pAcl;
        pDacl = &pAcl;
        if ( v15 <= 512 || (CTempBuffer<char,512>::SetSize(&pDacl, (unsigned int)v15), (p_pAcl = pDacl) != 0) )
        {
          if ( !InitializeAcl(p_pAcl, v15, 2u) )
            goto LABEL_64;
          for ( i = 0; i < v16; ++i )
          {
            if ( !AddAccessAllowedAce(pDacl, 2u, AccessMask[4 * i], *(PSID *)&AccessMask[4 * i - 2]) )
              goto LABEL_64;
            pAce = 0;
            if ( !GetAce(pDacl, i, &pAce) )
              goto LABEL_64;
            *((_BYTE *)pAce + 1) = 3;
          }
          v49 = 0;
          memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
          if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
            || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)
            || !SetSecurityDescriptorOwner(pSecurityDescriptor, v17, 0)
            || v10 && !SetSecurityDescriptorGroup(pSecurityDescriptor, v10, 0) )
          {
            goto LABEL_64;
          }
          SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          if ( *lpdwBufferLength < SecurityDescriptorLength )
          {
            if ( v53 > 512 )
              operator delete(pDacl);
            LastError = 122;
            goto LABEL_67;
          }
          if ( MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, lpdwBufferLength) )
            LastError = 0;
          else
LABEL_64:
            LastError = GetLastError();
          if ( v53 > 512 )
            operator delete(pDacl);
        }
        else
        {
          if ( v53 > 512 )
            operator delete(0);
          LastError = 14;
        }
LABEL_67:
        `vector destructor iterator'(&v55, 0x10u, 5u, GetSecurityDescriptor_::_2_::Security::_Security);
        return LastError;
      }
    }
  }
  v43 = GetLastError();
  v44 = &v65;
  do
  {
    v44 -= 2;
    GetSecurityDescriptor_::_2_::Security::_Security(v44);
    --v4;
  }
  while ( v4 );
  return v43;
}

```

## disassembly

```asm
0x18014c8cc  mov     [rsp-8+arg_10], rbx
0x18014c8d1  push    rbp
0x18014c8d2  push    rsi
0x18014c8d3  push    rdi
0x18014c8d4  push    r12
0x18014c8d6  push    r13
0x18014c8d8  push    r14
0x18014c8da  push    r15
0x18014c8dc  lea     rbp, [rsp-220h]
0x18014c8e4  sub     rsp, 320h
0x18014c8eb  mov     rax, cs:__security_cookie
0x18014c8f2  xor     rax, rsp
0x18014c8f5  mov     [rbp+250h+var_40], rax
0x18014c8fc  mov     r13d, 5
0x18014c902  mov     [rsp+350h+lpdwBufferLength], rdx
0x18014c907  mov     esi, r13d
0x18014c90a  mov     [rsp+350h+pSelfRelativeSecurityDescriptor], rcx
0x18014c90f  mov     r12d, r9d
0x18014c912  lea     rdi, [rbp+250h+var_90]
0x18014c919  mov     ebx, r8d
0x18014c91c  mov     rcx, rdi
0x18014c91f  call    _GetSecurityDescriptor____2___Security__Security
0x18014c924  add     rdi, 10h
0x18014c928  sub     rsi, 1
0x18014c92c  jnz     short loc_18014C91C
0x18014c92e  xor     edi, edi
0x18014c930  mov     word ptr [rbp+250h+pIdentifierAuthority.Value+4], 500h
0x18014c936  mov     dword ptr [rbp+250h+pIdentifierAuthority.Value], edi
0x18014c939  mov     r15d, edi
0x18014c93c  mov     dword ptr [rbp+250h+var_2A8.Value], edi
0x18014c93f  mov     word ptr [rbp+250h+var_2A8.Value+4], 100h
0x18014c945  lea     esi, [rdi+1]
0x18014c948  test    ebx, ebx
0x18014c94a  jz      loc_18014CEC0
0x18014c950  sub     ebx, esi
0x18014c952  jz      loc_18014CDFF
0x18014c958  sub     ebx, esi
0x18014c95a  jz      loc_18014CCF5
0x18014c960  sub     ebx, esi
0x18014c962  jz      loc_18014CC37
0x18014c968  sub     ebx, esi
0x18014c96a  jz      loc_18014CB37
0x18014c970  cmp     ebx, esi
0x18014c972  jz      short loc_18014C981
0x18014c974  lea     ebx, [rdi+8]
0x18014c977  mov     esi, edi
0x18014c979  mov     r14d, edi
0x18014c97c  jmp     loc_18014D013
0x18014c981  lea     rcx, [rbp+250h+var_90]
0x18014c988  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014c98d  mov     [rsp+350h+pSid], rax; pSid
0x18014c992  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014c996  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014c99a  xor     r9d, r9d; nSubAuthority1
0x18014c99d  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014c9a1  mov     dl, sil; nSubAuthorityCount
0x18014c9a4  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014c9a8  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014c9ac  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014c9b0  lea     r8d, [r9+4]; nSubAuthority0
0x18014c9b4  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014c9b8  call    cs:__imp_AllocateAndInitializeSid
0x18014c9bf  nop     dword ptr [rax+rax+00h]
0x18014c9c4  test    eax, eax
0x18014c9c6  jz      loc_18014CB24
0x18014c9cc  lea     rcx, [rbp+250h+var_80]
0x18014c9d3  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014c9d8  mov     [rsp+350h+pSid], rax; pSid
0x18014c9dd  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014c9e1  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014c9e5  xor     r9d, r9d; nSubAuthority1
0x18014c9e8  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014c9ec  mov     dl, sil; nSubAuthorityCount
0x18014c9ef  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014c9f3  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014c9f7  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014c9fb  lea     r8d, [r9+12h]; nSubAuthority0
0x18014c9ff  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014ca03  call    cs:__imp_AllocateAndInitializeSid
0x18014ca0a  nop     dword ptr [rax+rax+00h]
0x18014ca0f  test    eax, eax
0x18014ca11  jz      loc_18014CB24
0x18014ca17  lea     rcx, [rbp+250h+var_70]
0x18014ca1e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014ca23  mov     [rsp+350h+pSid], rax; pSid
0x18014ca28  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014ca2c  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014ca30  mov     r9d, 220h; nSubAuthority1
0x18014ca36  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014ca3a  mov     r8d, 20h ; ' '; nSubAuthority0
0x18014ca40  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014ca44  mov     dl, 2; nSubAuthorityCount
0x18014ca46  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014ca4a  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014ca4e  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014ca52  call    cs:__imp_AllocateAndInitializeSid
0x18014ca59  nop     dword ptr [rax+rax+00h]
0x18014ca5e  test    eax, eax
0x18014ca60  jz      loc_18014CB24
0x18014ca66  lea     rcx, [rbp+250h+var_60]
0x18014ca6d  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014ca72  mov     [rsp+350h+pSid], rax; pSid
0x18014ca77  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014ca7b  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014ca7f  xor     r9d, r9d; nSubAuthority1
0x18014ca82  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014ca86  mov     dl, sil; nSubAuthorityCount
0x18014ca89  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014ca8d  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014ca91  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014ca95  lea     r8d, [r9+13h]; nSubAuthority0
0x18014ca99  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014ca9d  call    cs:__imp_AllocateAndInitializeSid
0x18014caa4  nop     dword ptr [rax+rax+00h]
0x18014caa9  test    eax, eax
0x18014caab  jz      short loc_18014CB24
0x18014caad  lea     rcx, [rbp+250h+var_50]
0x18014cab4  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cab9  mov     [rsp+350h+pSid], rax; pSid
0x18014cabe  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cac2  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cac6  xor     r9d, r9d; nSubAuthority1
0x18014cac9  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cacd  mov     dl, sil; nSubAuthorityCount
0x18014cad0  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cad4  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cad8  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cadc  lea     r8d, [r9+14h]; nSubAuthority0
0x18014cae0  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cae4  call    cs:__imp_AllocateAndInitializeSid
0x18014caeb  nop     dword ptr [rax+rax+00h]
0x18014caf0  test    eax, eax
0x18014caf2  jz      short loc_18014CB24
0x18014caf4  mov     r14, [rbp+250h+var_70]
0x18014cafb  mov     [rbp+250h+AccessMask], esi
0x18014cb01  mov     r15, r14
0x18014cb04  mov     [rbp+250h+var_78], esi
0x18014cb0a  mov     [rbp+250h+var_68], esi
0x18014cb10  mov     [rbp+250h+var_58], esi
0x18014cb16  mov     [rbp+250h+var_48], esi
0x18014cb1c  mov     esi, r13d
0x18014cb1f  jmp     loc_18014CFE7
0x18014cb24  call    cs:__imp_GetLastError
0x18014cb2b  nop     dword ptr [rax+rax+00h]
0x18014cb30  mov     ebx, eax
0x18014cb32  jmp     loc_18014D1E0
0x18014cb37  lea     rcx, [rbp+250h+var_90]
0x18014cb3e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cb43  mov     [rsp+350h+pSid], rax; pSid
0x18014cb48  lea     rcx, [rbp+250h+var_2A8]; pIdentifierAuthority
0x18014cb4c  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cb50  xor     r9d, r9d; nSubAuthority1
0x18014cb53  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cb57  xor     r8d, r8d; nSubAuthority0
0x18014cb5a  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cb5e  mov     dl, sil; nSubAuthorityCount
0x18014cb61  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cb65  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cb69  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cb6d  call    cs:__imp_AllocateAndInitializeSid
0x18014cb74  nop     dword ptr [rax+rax+00h]
0x18014cb79  test    eax, eax
0x18014cb7b  jz      short loc_18014CB24
0x18014cb7d  lea     rcx, [rbp+250h+var_80]
0x18014cb84  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cb89  mov     [rsp+350h+pSid], rax; pSid
0x18014cb8e  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cb92  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cb96  xor     r9d, r9d; nSubAuthority1
0x18014cb99  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cb9d  mov     dl, sil; nSubAuthorityCount
0x18014cba0  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cba4  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cba8  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cbac  lea     r8d, [r9+12h]; nSubAuthority0
0x18014cbb0  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cbb4  call    cs:__imp_AllocateAndInitializeSid
0x18014cbbb  nop     dword ptr [rax+rax+00h]
0x18014cbc0  test    eax, eax
0x18014cbc2  jz      loc_18014CB24
0x18014cbc8  lea     rcx, [rbp+250h+var_70]
0x18014cbcf  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cbd4  mov     [rsp+350h+pSid], rax; pSid
0x18014cbd9  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cbdd  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cbe1  mov     r9d, 220h; nSubAuthority1
0x18014cbe7  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cbeb  mov     r8d, 20h ; ' '; nSubAuthority0
0x18014cbf1  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cbf5  mov     dl, 2; nSubAuthorityCount
0x18014cbf7  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cbfb  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cbff  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cc03  call    cs:__imp_AllocateAndInitializeSid
0x18014cc0a  nop     dword ptr [rax+rax+00h]
0x18014cc0f  test    eax, eax
0x18014cc11  jz      loc_18014CB24
0x18014cc17  mov     edx, 10000000h
0x18014cc1c  mov     [rbp+250h+AccessMask], 2001Bh
0x18014cc26  mov     [rbp+250h+var_78], edx
0x18014cc2c  mov     [rbp+250h+var_68], edx
0x18014cc32  jmp     loc_18014CFDB
0x18014cc37  lea     rcx, [rbp+250h+var_90]
0x18014cc3e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cc43  mov     [rsp+350h+pSid], rax; pSid
0x18014cc48  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cc4c  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cc50  xor     r9d, r9d; nSubAuthority1
0x18014cc53  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cc57  mov     dl, sil; nSubAuthorityCount
0x18014cc5a  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cc5e  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cc62  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cc66  lea     r8d, [r9+12h]; nSubAuthority0
0x18014cc6a  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cc6e  call    cs:__imp_AllocateAndInitializeSid
0x18014cc75  nop     dword ptr [rax+rax+00h]
0x18014cc7a  test    eax, eax
0x18014cc7c  jz      loc_18014CB24
0x18014cc82  lea     rcx, [rbp+250h+var_80]
0x18014cc89  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cc8e  mov     [rsp+350h+pSid], rax; pSid
0x18014cc93  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cc97  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cc9b  mov     r9d, 220h; nSubAuthority1
0x18014cca1  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cca5  mov     r8d, 20h ; ' '; nSubAuthority0
0x18014ccab  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014ccaf  mov     dl, 2; nSubAuthorityCount
0x18014ccb1  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014ccb5  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014ccb9  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014ccbd  call    cs:__imp_AllocateAndInitializeSid
0x18014ccc4  nop     dword ptr [rax+rax+00h]
0x18014ccc9  test    eax, eax
0x18014cccb  jz      loc_18014CB24
0x18014ccd1  mov     r15, [rbp+250h+var_90]
0x18014ccd8  mov     r14, [rbp+250h+var_80]
0x18014ccdf  mov     [rbp+250h+AccessMask], esi
0x18014cce5  mov     [rbp+250h+var_78], esi
0x18014cceb  mov     esi, 2
0x18014ccf0  jmp     loc_18014CFE7
0x18014ccf5  lea     rcx, [rbp+250h+var_90]
0x18014ccfc  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cd01  mov     [rsp+350h+pSid], rax; pSid
0x18014cd06  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cd0a  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cd0e  xor     r9d, r9d; nSubAuthority1
0x18014cd11  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cd15  mov     dl, sil; nSubAuthorityCount
0x18014cd18  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cd1c  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cd20  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cd24  lea     r8d, [r9+12h]; nSubAuthority0
0x18014cd28  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cd2c  call    cs:__imp_AllocateAndInitializeSid
0x18014cd33  nop     dword ptr [rax+rax+00h]
0x18014cd38  test    eax, eax
0x18014cd3a  jz      loc_18014CB24
0x18014cd40  lea     rcx, [rbp+250h+var_80]
0x18014cd47  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cd4c  mov     [rsp+350h+pSid], rax; pSid
0x18014cd51  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cd55  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cd59  mov     r9d, 220h; nSubAuthority1
0x18014cd5f  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cd63  mov     r8d, 20h ; ' '; nSubAuthority0
0x18014cd69  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cd6d  mov     dl, 2; nSubAuthorityCount
0x18014cd6f  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cd73  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cd77  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cd7b  call    cs:__imp_AllocateAndInitializeSid
0x18014cd82  nop     dword ptr [rax+rax+00h]
0x18014cd87  test    eax, eax
0x18014cd89  jz      loc_18014CB24
0x18014cd8f  lea     rcx, [rbp+250h+var_70]
0x18014cd96  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014cd9b  mov     [rsp+350h+pSid], rax; pSid
0x18014cda0  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014cda4  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014cda8  xor     r9d, r9d; nSubAuthority1
0x18014cdab  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014cdaf  mov     dl, sil; nSubAuthorityCount
0x18014cdb2  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014cdb6  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014cdba  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x18014cdbe  lea     r8d, [r9+4]; nSubAuthority0
0x18014cdc2  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014cdc6  call    cs:__imp_AllocateAndInitializeSid
0x18014cdcd  nop     dword ptr [rax+rax+00h]
0x18014cdd2  test    eax, eax
0x18014cdd4  jz      loc_18014CB24
0x18014cdda  mov     r15, [rbp+250h+var_90]
0x18014cde1  mov     r14, [rbp+250h+var_80]
0x18014cde8  mov     [rbp+250h+AccessMask], esi
0x18014cdee  mov     [rbp+250h+var_78], esi
0x18014cdf4  mov     [rbp+250h+var_68], esi
0x18014cdfa  jmp     loc_18014CFE2
0x18014cdff  lea     rcx, [rbp+250h+var_90]
  ... truncated ...
```
