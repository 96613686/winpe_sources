# GetSecurityDescriptor(char *,ulong &,sdSecurityDescriptor,Bool)

- ea: `0x1801473c0`
- end: `0x180147c87`
- name: `?GetSecurityDescriptor@@YAKPEADAEAKW4sdSecurityDescriptor@@W4Bool@@@Z`
- size: `2247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001036c`
- `0x18006cc60`
- `0x18007b894`
- `0x1800916b4`
- `0x180127748`
- `0x180147314`
- `0x1801e142c`

## callees

- `0x1800620e4`
- `0x18006c0cc`
- `0x1801473c0`
- `0x180147c90`
- `0x180147cb0`
- `0x180147cbc`
- `0x18014a65c`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x180147ae5`
- `ADVAPI32!InitializeAcl` at `0x180147ae5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801474ac`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801474f1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014753a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014757f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801475c0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014763d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014767e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801476c7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014772c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147775`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801477de`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147827`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014786c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801478d6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014791f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014798b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801479cf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147a18`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801474ac`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801474f1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014753a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014757f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801475c0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014763d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014767e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801476c7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014772c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147775`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801477de`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147827`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014786c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801478d6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014791f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18014798b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801479cf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180147a18`
- `ADVAPI32!GetLengthSid` at `0x180147a7c`
- `ADVAPI32!GetLengthSid` at `0x180147a7c`
- `ADVAPI32!AddAccessAllowedAce` at `0x180147b18`
- `ADVAPI32!AddAccessAllowedAce` at `0x180147b18`
- `ADVAPI32!GetAce` at `0x180147b36`
- `ADVAPI32!GetAce` at `0x180147b36`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180147b6b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180147b6b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180147b89`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180147b89`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180147b9e`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180147b9e`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180147bb8`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180147bb8`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180147bc7`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180147bc7`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180147bf7`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180147bf7`
- `KERNEL32!GetLastError` at `0x1801475fa`
- `KERNEL32!GetLastError` at `0x180147c05`
- `KERNEL32!GetLastError` at `0x180147c3b`
- `KERNEL32!GetLastError` at `0x1801475fa`
- `KERNEL32!GetLastError` at `0x180147c05`
- `KERNEL32!GetLastError` at `0x180147c3b`

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
0x1801473c0  mov     [rsp-8+arg_10], rbx
0x1801473c5  push    rbp
0x1801473c6  push    rsi
0x1801473c7  push    rdi
0x1801473c8  push    r12
0x1801473ca  push    r13
0x1801473cc  push    r14
0x1801473ce  push    r15
0x1801473d0  lea     rbp, [rsp-220h]
0x1801473d8  sub     rsp, 320h
0x1801473df  mov     rax, cs:__security_cookie
0x1801473e6  xor     rax, rsp
0x1801473e9  mov     [rbp+250h+var_40], rax
0x1801473f0  mov     r13d, 5
0x1801473f6  mov     [rsp+350h+lpdwBufferLength], rdx
0x1801473fb  mov     esi, r13d
0x1801473fe  mov     [rsp+350h+pSelfRelativeSecurityDescriptor], rcx
0x180147403  mov     r12d, r9d
0x180147406  lea     rdi, [rbp+250h+var_90]
0x18014740d  mov     ebx, r8d
0x180147410  mov     rcx, rdi
0x180147413  call    _GetSecurityDescriptor____2___Security__Security
0x180147418  add     rdi, 10h
0x18014741c  sub     rsi, 1
0x180147420  jnz     short loc_180147410
0x180147422  xor     edi, edi
0x180147424  mov     word ptr [rbp+250h+pIdentifierAuthority.Value+4], 500h
0x18014742a  mov     dword ptr [rbp+250h+pIdentifierAuthority.Value], edi
0x18014742d  mov     r15d, edi
0x180147430  mov     dword ptr [rbp+250h+var_2A8.Value], edi
0x180147433  mov     word ptr [rbp+250h+var_2A8.Value+4], 100h
0x180147439  lea     esi, [rdi+1]
0x18014743c  test    ebx, ebx
0x18014743e  jz      loc_180147954
0x180147444  sub     ebx, esi
0x180147446  jz      loc_18014789F
0x18014744c  sub     ebx, esi
0x18014744e  jz      loc_1801477A7
0x180147454  sub     ebx, esi
0x180147456  jz      loc_1801476F5
0x18014745c  sub     ebx, esi
0x18014745e  jz      loc_180147607
0x180147464  cmp     ebx, esi
0x180147466  jz      short loc_180147475
0x180147468  lea     ebx, [rdi+8]
0x18014746b  mov     esi, edi
0x18014746d  mov     r14d, edi
0x180147470  jmp     loc_180147A8F
0x180147475  lea     rcx, [rbp+250h+var_90]
0x18014747c  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147481  mov     [rsp+350h+pSid], rax; pSid
0x180147486  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014748a  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014748e  xor     r9d, r9d; nSubAuthority1
0x180147491  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147495  mov     dl, sil; nSubAuthorityCount
0x180147498  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014749c  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801474a0  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801474a4  lea     r8d, [r9+4]; nSubAuthority0
0x1801474a8  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801474ac  call    cs:__imp_AllocateAndInitializeSid
0x1801474b2  test    eax, eax
0x1801474b4  jz      loc_1801475FA
0x1801474ba  lea     rcx, [rbp+250h+var_80]
0x1801474c1  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1801474c6  mov     [rsp+350h+pSid], rax; pSid
0x1801474cb  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1801474cf  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x1801474d3  xor     r9d, r9d; nSubAuthority1
0x1801474d6  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x1801474da  mov     dl, sil; nSubAuthorityCount
0x1801474dd  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x1801474e1  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801474e5  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801474e9  lea     r8d, [r9+12h]; nSubAuthority0
0x1801474ed  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801474f1  call    cs:__imp_AllocateAndInitializeSid
0x1801474f7  test    eax, eax
0x1801474f9  jz      loc_1801475FA
0x1801474ff  lea     rcx, [rbp+250h+var_70]
0x180147506  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x18014750b  mov     [rsp+350h+pSid], rax; pSid
0x180147510  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x180147514  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147518  mov     r9d, 220h; nSubAuthority1
0x18014751e  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147522  mov     r8d, 20h ; ' '; nSubAuthority0
0x180147528  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014752c  mov     dl, 2; nSubAuthorityCount
0x18014752e  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147532  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147536  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014753a  call    cs:__imp_AllocateAndInitializeSid
0x180147540  test    eax, eax
0x180147542  jz      loc_1801475FA
0x180147548  lea     rcx, [rbp+250h+var_60]
0x18014754f  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147554  mov     [rsp+350h+pSid], rax; pSid
0x180147559  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014755d  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147561  xor     r9d, r9d; nSubAuthority1
0x180147564  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147568  mov     dl, sil; nSubAuthorityCount
0x18014756b  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014756f  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147573  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147577  lea     r8d, [r9+13h]; nSubAuthority0
0x18014757b  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014757f  call    cs:__imp_AllocateAndInitializeSid
0x180147585  test    eax, eax
0x180147587  jz      short loc_1801475FA
0x180147589  lea     rcx, [rbp+250h+var_50]
0x180147590  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147595  mov     [rsp+350h+pSid], rax; pSid
0x18014759a  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014759e  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x1801475a2  xor     r9d, r9d; nSubAuthority1
0x1801475a5  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x1801475a9  mov     dl, sil; nSubAuthorityCount
0x1801475ac  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x1801475b0  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801475b4  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801475b8  lea     r8d, [r9+14h]; nSubAuthority0
0x1801475bc  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801475c0  call    cs:__imp_AllocateAndInitializeSid
0x1801475c6  test    eax, eax
0x1801475c8  jz      short loc_1801475FA
0x1801475ca  mov     r14, [rbp+250h+var_70]
0x1801475d1  mov     [rbp+250h+AccessMask], esi
0x1801475d7  mov     r15, r14
0x1801475da  mov     [rbp+250h+var_78], esi
0x1801475e0  mov     [rbp+250h+var_68], esi
0x1801475e6  mov     [rbp+250h+var_58], esi
0x1801475ec  mov     [rbp+250h+var_48], esi
0x1801475f2  mov     esi, r13d
0x1801475f5  jmp     loc_180147A69
0x1801475fa  call    cs:__imp_GetLastError
0x180147600  mov     ebx, eax
0x180147602  jmp     loc_180147C1C
0x180147607  lea     rcx, [rbp+250h+var_90]
0x18014760e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147613  mov     [rsp+350h+pSid], rax; pSid
0x180147618  lea     rcx, [rbp+250h+var_2A8]; pIdentifierAuthority
0x18014761c  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147620  xor     r9d, r9d; nSubAuthority1
0x180147623  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147627  xor     r8d, r8d; nSubAuthority0
0x18014762a  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014762e  mov     dl, sil; nSubAuthorityCount
0x180147631  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147635  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147639  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014763d  call    cs:__imp_AllocateAndInitializeSid
0x180147643  test    eax, eax
0x180147645  jz      short loc_1801475FA
0x180147647  lea     rcx, [rbp+250h+var_80]
0x18014764e  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147653  mov     [rsp+350h+pSid], rax; pSid
0x180147658  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014765c  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147660  xor     r9d, r9d; nSubAuthority1
0x180147663  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147667  mov     dl, sil; nSubAuthorityCount
0x18014766a  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014766e  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147672  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147676  lea     r8d, [r9+12h]; nSubAuthority0
0x18014767a  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014767e  call    cs:__imp_AllocateAndInitializeSid
0x180147684  test    eax, eax
0x180147686  jz      loc_1801475FA
0x18014768c  lea     rcx, [rbp+250h+var_70]
0x180147693  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147698  mov     [rsp+350h+pSid], rax; pSid
0x18014769d  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1801476a1  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x1801476a5  mov     r9d, 220h; nSubAuthority1
0x1801476ab  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x1801476af  mov     r8d, 20h ; ' '; nSubAuthority0
0x1801476b5  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x1801476b9  mov     dl, 2; nSubAuthorityCount
0x1801476bb  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801476bf  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801476c3  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801476c7  call    cs:__imp_AllocateAndInitializeSid
0x1801476cd  test    eax, eax
0x1801476cf  jz      loc_1801475FA
0x1801476d5  mov     edx, 10000000h
0x1801476da  mov     [rbp+250h+AccessMask], 2001Bh
0x1801476e4  mov     [rbp+250h+var_78], edx
0x1801476ea  mov     [rbp+250h+var_68], edx
0x1801476f0  jmp     loc_180147A5D
0x1801476f5  lea     rcx, [rbp+250h+var_90]
0x1801476fc  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147701  mov     [rsp+350h+pSid], rax; pSid
0x180147706  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014770a  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014770e  xor     r9d, r9d; nSubAuthority1
0x180147711  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147715  mov     dl, sil; nSubAuthorityCount
0x180147718  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014771c  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147720  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147724  lea     r8d, [r9+12h]; nSubAuthority0
0x180147728  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014772c  call    cs:__imp_AllocateAndInitializeSid
0x180147732  test    eax, eax
0x180147734  jz      loc_1801475FA
0x18014773a  lea     rcx, [rbp+250h+var_80]
0x180147741  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147746  mov     [rsp+350h+pSid], rax; pSid
0x18014774b  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014774f  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147753  mov     r9d, 220h; nSubAuthority1
0x180147759  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014775d  mov     r8d, 20h ; ' '; nSubAuthority0
0x180147763  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x180147767  mov     dl, 2; nSubAuthorityCount
0x180147769  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014776d  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147771  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x180147775  call    cs:__imp_AllocateAndInitializeSid
0x18014777b  test    eax, eax
0x18014777d  jz      loc_1801475FA
0x180147783  mov     r15, [rbp+250h+var_90]
0x18014778a  mov     r14, [rbp+250h+var_80]
0x180147791  mov     [rbp+250h+AccessMask], esi
0x180147797  mov     [rbp+250h+var_78], esi
0x18014779d  mov     esi, 2
0x1801477a2  jmp     loc_180147A69
0x1801477a7  lea     rcx, [rbp+250h+var_90]
0x1801477ae  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1801477b3  mov     [rsp+350h+pSid], rax; pSid
0x1801477b8  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1801477bc  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x1801477c0  xor     r9d, r9d; nSubAuthority1
0x1801477c3  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x1801477c7  mov     dl, sil; nSubAuthorityCount
0x1801477ca  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x1801477ce  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801477d2  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801477d6  lea     r8d, [r9+12h]; nSubAuthority0
0x1801477da  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801477de  call    cs:__imp_AllocateAndInitializeSid
0x1801477e4  test    eax, eax
0x1801477e6  jz      loc_1801475FA
0x1801477ec  lea     rcx, [rbp+250h+var_80]
0x1801477f3  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1801477f8  mov     [rsp+350h+pSid], rax; pSid
0x1801477fd  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x180147801  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x180147805  mov     r9d, 220h; nSubAuthority1
0x18014780b  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x18014780f  mov     r8d, 20h ; ' '; nSubAuthority0
0x180147815  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x180147819  mov     dl, 2; nSubAuthorityCount
0x18014781b  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x18014781f  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147823  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x180147827  call    cs:__imp_AllocateAndInitializeSid
0x18014782d  test    eax, eax
0x18014782f  jz      loc_1801475FA
0x180147835  lea     rcx, [rbp+250h+var_70]
0x18014783c  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x180147841  mov     [rsp+350h+pSid], rax; pSid
0x180147846  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18014784a  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x18014784e  xor     r9d, r9d; nSubAuthority1
0x180147851  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x180147855  mov     dl, sil; nSubAuthorityCount
0x180147858  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x18014785c  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x180147860  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x180147864  lea     r8d, [r9+4]; nSubAuthority0
0x180147868  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x18014786c  call    cs:__imp_AllocateAndInitializeSid
0x180147872  test    eax, eax
0x180147874  jz      loc_1801475FA
0x18014787a  mov     r15, [rbp+250h+var_90]
0x180147881  mov     r14, [rbp+250h+var_80]
0x180147888  mov     [rbp+250h+AccessMask], esi
0x18014788e  mov     [rbp+250h+var_78], esi
0x180147894  mov     [rbp+250h+var_68], esi
0x18014789a  jmp     loc_180147A64
0x18014789f  lea     rcx, [rbp+250h+var_90]
0x1801478a6  call    _GetSecurityDescriptor____2___CSIDPointer__operator_
0x1801478ab  mov     [rsp+350h+pSid], rax; pSid
0x1801478b0  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x1801478b4  mov     [rsp+350h+nSubAuthority7], edi; nSubAuthority7
0x1801478b8  xor     r9d, r9d; nSubAuthority1
0x1801478bb  mov     [rsp+350h+nSubAuthority6], edi; nSubAuthority6
0x1801478bf  mov     dl, sil; nSubAuthorityCount
0x1801478c2  mov     [rsp+350h+nSubAuthority5], edi; nSubAuthority5
0x1801478c6  mov     [rsp+350h+nSubAuthority4], edi; nSubAuthority4
0x1801478ca  mov     [rsp+350h+nSubAuthority3], edi; nSubAuthority3
0x1801478ce  lea     r8d, [r9+12h]; nSubAuthority0
0x1801478d2  mov     [rsp+350h+nSubAuthority2], edi; nSubAuthority2
0x1801478d6  call    cs:__imp_AllocateAndInitializeSid
0x1801478dc  test    eax, eax
  ... truncated ...
```
