# CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)

- ea: `0x180009bf4`
- end: `0x18000a0ee`
- name: `?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z`
- size: `1274`
- prototype: `static int(void **, unsigned int, void *, unsigned __int8)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009644`
- `0x180009ad4`
- `0x18002aa60`

## callees

- `0x1800077a0`
- `0x180009bf4`
- `0x18000a0f4`
- `0x18000a4a0`
- `0x18000acec`
- `0x18004e850`
- `0x18004f318`
- `0x180099530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a06d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009da0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009da0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ec1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ec1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0dd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009d79`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009d79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009cc0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009cc0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180009ca9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180009ca9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180009dec`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180009dec`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180009e18`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180009e47`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180009e18`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180009e47`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180009dc4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180009dc4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009c7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009e83`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009c7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009e83`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009ea4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009ea4`

## string_xrefs

- `0x180009f3e`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x18000a047`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x180009f78`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x18000a01b`: `GetAclInformation 0x%x`
- `0x18000a088`: `InitializeAcl failed: 0x%x`
- `0x18000a0b7`: `SD has NULL DACL, Present %d, Defaulted %d`

## pseudocode

```c
__int64 __fastcall CUtils::AddAceToSecurityDescriptor(void **a1, int a2, void *a3, char a4)
{
  struct _ACL *v6; // r15
  PSECURITY_DESCRIPTOR v7; // r12
  __int16 *v8; // rax
  DWORD LengthSid; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  DWORD v14; // r14d
  struct _ACL *v15; // rax
  DWORD i; // r14d
  unsigned int *v17; // r8
  unsigned int *v18; // r8
  unsigned int v19; // ebx
  signed int v21; // eax
  const char *v22; // rdx
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int LastError; // eax
  signed int v28; // eax
  signed int v29; // eax
  __int16 pAceList; // [rsp+30h] [rbp+0h] BYREF
  unsigned __int16 v31; // [rsp+32h] [rbp+2h]
  int v32; // [rsp+34h] [rbp+4h]
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp+Ch] BYREF
  PACL pDacl; // [rsp+40h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp+18h] BYREF
  DWORD v37; // [rsp+50h] [rbp+20h]
  LPVOID pAce; // [rsp+58h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+60h] [rbp+30h]
  void *v40[6]; // [rsp+68h] [rbp+38h] BYREF
  __int64 pAclInformation; // [rsp+98h] [rbp+68h] BYREF
  int v42; // [rsp+A0h] [rbp+70h]

  v40[3] = a1;
  v40[4] = a3;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  pAclInformation = 0;
  v42 = 0;
  pDacl = 0;
  v6 = 0;
  v40[0] = 0;
  v7 = 0;
  pSecurityDescriptor = 0;
  v8 = (__int16 *)*a1;
  pSelfRelativeSecurityDescriptor = v8;
  v40[5] = v8;
  if ( v8[1] >= 0 )
  {
    _DbgPrintMessage(8, "SD is not Self-Relative");
LABEL_25:
    v19 = -2147023558;
  }
  else
  {
    if ( !GetSecurityDescriptorDacl(v8, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      v22 = "GetSecurityDescriptorDacl failed: 0x%x";
      goto LABEL_34;
    }
    if ( !pDacl )
    {
      _DbgPrintMessage(8, "SD has NULL DACL, Present %d, Defaulted %d", bDaclPresent, bDaclDefaulted);
LABEL_36:
      v19 = 0;
      goto LABEL_26;
    }
    if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      v28 = GetLastError();
      v19 = v28;
      if ( v28 > 0 )
        v19 = (unsigned __int16)v28 | 0x80070000;
      v22 = "GetAclInformation 0x%x";
      goto LABEL_34;
    }
    LengthSid = GetLengthSid(a3);
    v37 = LengthSid;
    LOWORD(v32) = LengthSid + 8;
    pAceList = LengthSid + 8;
    v10 = (unsigned __int16)(LengthSid + 8) + 15LL;
    if ( v10 <= (unsigned __int16)(LengthSid + 8) )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    v40[1] = &pAceList;
    if ( !&pAceList )
      goto LABEL_59;
    pAceList = 0;
    v31 = LengthSid + 8;
    v32 = a2;
    CopySid((unsigned __int16)LengthSid, &bDaclDefaulted, a3);
    if ( a4 )
      HIBYTE(pAceList) |= 0xBu;
    v14 = HIDWORD(pAclInformation) + v31;
    v15 = (struct _ACL *)LocalAlloc(0, v14);
    v6 = v15;
    if ( v15 )
    {
      if ( !InitializeAcl(v15, v14, 2u) )
      {
        v29 = GetLastError();
        v19 = v29;
        if ( v29 > 0 )
          v19 = (unsigned __int16)v29 | 0x80070000;
        v22 = "InitializeAcl failed: 0x%x";
        goto LABEL_34;
      }
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        if ( !GetAce(pDacl, i, &pAce) )
        {
          v26 = GetLastError();
          v19 = v26;
          if ( v26 > 0 )
            v19 = (unsigned __int16)v26 | 0x80070000;
          v22 = "GetAce failed: 0x%x";
          goto LABEL_34;
        }
        if ( !AddAce(v6, 2u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
          goto LABEL_40;
      }
      if ( !AddAce(v6, 2u, i, &pAceList, v31) )
      {
LABEL_40:
        v24 = GetLastError();
        v19 = v24;
        if ( v24 > 0 )
          v19 = (unsigned __int16)v24 | 0x80070000;
        v22 = "AddAce failed: 0x%x";
        goto LABEL_34;
      }
      if ( (unsigned int)CUtils::SelfRelativeToAbsoluteSD(pSelfRelativeSecurityDescriptor, &pSecurityDescriptor, v17) )
      {
        v7 = pSecurityDescriptor;
        if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          if ( SetSecurityDescriptorDacl(v7, 1, v6, 0) )
          {
            if ( pDacl )
              pDacl = (PACL)LocalFree(pDacl);
            v6 = 0;
            if ( !(unsigned int)CUtils::AbsoluteToSelfRelativeSD(v7, v40, v18) )
            {
              _DbgPrintMessage(8, "AbsoluteToSelfRelativeSD failed");
              goto LABEL_25;
            }
            CUtils::CleanupSD(*a1);
            *a1 = v40[0];
            goto LABEL_36;
          }
          v23 = GetLastError();
          v19 = v23;
          if ( v23 > 0 )
            v19 = (unsigned __int16)v23 | 0x80070000;
          v22 = "SetSecurityDescriptorDacl failed: 0x%x";
        }
        else
        {
          v21 = GetLastError();
          v19 = v21;
          if ( v21 > 0 )
            v19 = (unsigned __int16)v21 | 0x80070000;
          v22 = "GetSecurityDescriptorDacl failed: 0x%x";
        }
LABEL_34:
        _DbgPrintMessage(8, v22, v19);
        goto LABEL_26;
      }
      v25 = GetLastError();
      v19 = v25;
      if ( v25 > 0 )
        v19 = (unsigned __int16)v25 | 0x80070000;
      _DbgPrintMessage(8, "SelfRelativeToAbsoluteSD failed: 0x%x", v19);
      v7 = pSecurityDescriptor;
    }
    else
    {
LABEL_59:
      v19 = -2147024882;
    }
  }
LABEL_26:
  if ( v7 )
    CUtils::CleanupSD(v7);
  if ( v6 )
    LocalFree(v6);
  return v19;
}

```

## disassembly

```asm
0x180009bf4  mov     [rsp-8+arg_18], r9b
0x180009bf9  mov     [rsp-8+arg_8], edx
0x180009bfd  push    rbp
0x180009bfe  push    rbx
0x180009bff  push    rsi
0x180009c00  push    rdi
0x180009c01  push    r12
0x180009c03  push    r13
0x180009c05  push    r14
0x180009c07  push    r15
0x180009c09  sub     rsp, 0B8h
0x180009c10  lea     rbp, [rsp+30h]
0x180009c15  mov     rax, cs:__security_cookie
0x180009c1c  xor     rax, rbp
0x180009c1f  mov     [rbp+0C0h+var_48], rax
0x180009c23  mov     r14, r8
0x180009c26  mov     r13, rcx
0x180009c29  mov     [rbp+0C0h+var_70], rcx
0x180009c2d  mov     [rbp+0C0h+var_68], r8
0x180009c31  xor     edi, edi
0x180009c33  mov     [rbp+0C0h+bDaclPresent], edi
0x180009c36  mov     [rbp+0C0h+bDaclDefaulted], edi
0x180009c39  mov     [rbp+0C0h+pAce], rdi
0x180009c3d  xor     eax, eax
0x180009c3f  mov     [rbp+0C0h+pAclInformation], rax
0x180009c43  mov     [rbp+0C0h+var_50], eax
0x180009c46  mov     [rbp+0C0h+pDacl], rdi
0x180009c4a  mov     r15d, edi
0x180009c4d  mov     [rbp+0C0h+var_88], rdi
0x180009c51  mov     r12d, edi
0x180009c54  mov     [rbp+0C0h+pSecurityDescriptor], rdi
0x180009c58  mov     rax, [rcx]
0x180009c5b  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x180009c5f  mov     [rbp+0C0h+var_60], rax
0x180009c63  cmp     [rax+2], di
0x180009c67  jge     loc_18000A094
0x180009c6d  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x180009c71  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x180009c75  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x180009c79  mov     rcx, rax; pSecurityDescriptor
0x180009c7c  call    cs:__imp_GetSecurityDescriptorDacl
0x180009c83  nop     dword ptr [rax+rax+00h]
0x180009c88  test    eax, eax
0x180009c8a  jz      loc_18000A02C
0x180009c90  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180009c94  test    rcx, rcx
0x180009c97  jz      loc_18000A0AF
0x180009c9d  lea     r9d, [rdi+2]; dwAclInformationClass
0x180009ca1  lea     r8d, [rdi+0Ch]; nAclInformationLength
0x180009ca5  lea     rdx, [rbp+0C0h+pAclInformation]; pAclInformation
0x180009ca9  call    cs:__imp_GetAclInformation
0x180009cb0  nop     dword ptr [rax+rax+00h]
0x180009cb5  test    eax, eax
0x180009cb7  jz      loc_18000A050
0x180009cbd  mov     rcx, r14; pSid
0x180009cc0  call    cs:__imp_GetLengthSid
0x180009cc7  nop     dword ptr [rax+rax+00h]
0x180009ccc  mov     r8d, eax
0x180009ccf  mov     [rbp+0C0h+var_A0], eax
0x180009cd2  lea     esi, [rdi+8]
0x180009cd5  lea     edx, [rsi+rax]
0x180009cd8  mov     word ptr [rbp+0C0h+var_BC], dx
0x180009cdc  mov     [rbp+0C0h+pAceList], dx
0x180009ce0  movzx   eax, dx
0x180009ce3  lea     rcx, [rax+0Fh]
0x180009ce7  cmp     rcx, rax
0x180009cea  ja      short loc_180009CF6
0x180009cec  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180009cf6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009cfa  mov     rax, rcx
0x180009cfd  call    _alloca_probe
0x180009d02  sub     rsp, rcx
0x180009d05  lea     rbx, [rsp+0F0h+pAceList]
0x180009d0a  mov     [rbp+0C0h+var_80], rbx
0x180009d0e  jmp     short loc_180009D53
0x180009d10  call    _o__resetstkoflw_0
0x180009d15  xor     ebx, ebx
0x180009d17  mov     [rbp+0C0h+var_80], rbx
0x180009d1b  movzx   r8d, [rbp+0C0h+pAceList]
0x180009d20  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180009d27  lea     ecx, [rbx+8]; int
0x180009d2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009d2f  xor     edi, edi
0x180009d31  lea     esi, [rbx+8]
0x180009d34  mov     r15d, ebx
0x180009d37  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x180009d3b  mov     r13, [rbp+0C0h+var_70]
0x180009d3f  mov     r14, [rbp+0C0h+var_68]
0x180009d43  mov     rax, [rbp+0C0h+var_60]
0x180009d47  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x180009d4b  movzx   edx, word ptr [rbp+0C0h+var_BC]
0x180009d4f  mov     r8d, [rbp+0C0h+var_A0]
0x180009d53  test    rbx, rbx
0x180009d56  jz      loc_18000A0A5
0x180009d5c  mov     word ptr [rbx], 0
0x180009d61  mov     [rbx+2], dx
0x180009d65  mov     eax, [rbp+0C0h+arg_8]
0x180009d6b  mov     [rbx+4], eax
0x180009d6e  lea     rdx, [rbx+8]; pDestinationSid
0x180009d72  movzx   ecx, r8w; nDestinationSidLength
0x180009d76  mov     r8, r14; pSourceSid
0x180009d79  call    cs:__imp_CopySid
0x180009d80  nop     dword ptr [rax+rax+00h]
0x180009d85  cmp     [rbp+0C0h+arg_18], dil
0x180009d8c  jz      short loc_180009D92
0x180009d8e  or      byte ptr [rbx+1], 0Bh
0x180009d92  movzx   r14d, word ptr [rbx+2]
0x180009d97  add     r14d, dword ptr [rbp+0C0h+pAclInformation+4]
0x180009d9b  mov     edx, r14d; uBytes
0x180009d9e  xor     ecx, ecx; uFlags
0x180009da0  call    cs:__imp_LocalAlloc
0x180009da7  nop     dword ptr [rax+rax+00h]
0x180009dac  mov     r15, rax
0x180009daf  test    rax, rax
0x180009db2  jz      loc_18000A0A5
0x180009db8  mov     r8d, 2; dwAclRevision
0x180009dbe  mov     edx, r14d; nAclLength
0x180009dc1  mov     rcx, rax; pAcl
0x180009dc4  call    cs:__imp_InitializeAcl
0x180009dcb  nop     dword ptr [rax+rax+00h]
0x180009dd0  test    eax, eax
0x180009dd2  jz      loc_18000A06D
0x180009dd8  mov     r14d, edi
0x180009ddb  cmp     r14d, dword ptr [rbp+0C0h+pAclInformation]
0x180009ddf  jnb     short loc_180009E31
0x180009de1  lea     r8, [rbp+0C0h+pAce]; pAce
0x180009de5  mov     edx, r14d; dwAceIndex
0x180009de8  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180009dec  call    cs:__imp_GetAce
0x180009df3  nop     dword ptr [rax+rax+00h]
0x180009df8  test    eax, eax
0x180009dfa  jz      loc_180009FF4
0x180009e00  mov     r9, [rbp+0C0h+pAce]; pAceList
0x180009e04  movzx   eax, word ptr [r9+2]
0x180009e09  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x180009e0d  mov     r8d, r14d; dwStartingAceIndex
0x180009e10  mov     edx, 2; dwAceRevision
0x180009e15  mov     rcx, r15; pAcl
0x180009e18  call    cs:__imp_AddAce
0x180009e1f  nop     dword ptr [rax+rax+00h]
0x180009e24  test    eax, eax
0x180009e26  jz      loc_180009F8C
0x180009e2c  inc     r14d
0x180009e2f  jmp     short loc_180009DDB
0x180009e31  movzx   eax, word ptr [rbx+2]
0x180009e35  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x180009e39  mov     r9, rbx; pAceList
0x180009e3c  mov     r8d, r14d; dwStartingAceIndex
0x180009e3f  mov     edx, 2; dwAceRevision
0x180009e44  mov     rcx, r15; pAcl
0x180009e47  call    cs:__imp_AddAce
0x180009e4e  nop     dword ptr [rax+rax+00h]
0x180009e53  test    eax, eax
0x180009e55  jz      loc_180009F8C
0x180009e5b  lea     rdx, [rbp+0C0h+pSecurityDescriptor]; void **
0x180009e5f  mov     rcx, [rbp+0C0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180009e63  call    ?SelfRelativeToAbsoluteSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::SelfRelativeToAbsoluteSD(void *,void * *,ulong *)
0x180009e68  test    eax, eax
0x180009e6a  jz      loc_180009FA7
0x180009e70  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x180009e74  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x180009e78  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x180009e7c  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x180009e80  mov     rcx, r12; pSecurityDescriptor
0x180009e83  call    cs:__imp_GetSecurityDescriptorDacl
0x180009e8a  nop     dword ptr [rax+rax+00h]
0x180009e8f  test    eax, eax
0x180009e91  jz      loc_180009F2C
0x180009e97  xor     r9d, r9d; bDaclDefaulted
0x180009e9a  mov     r8, r15; pDacl
0x180009e9d  lea     edx, [r9+1]; bDaclPresent
0x180009ea1  mov     rcx, r12; pSecurityDescriptor
0x180009ea4  call    cs:__imp_SetSecurityDescriptorDacl
0x180009eab  nop     dword ptr [rax+rax+00h]
0x180009eb0  test    eax, eax
0x180009eb2  jz      loc_180009F66
0x180009eb8  mov     rcx, [rbp+0C0h+pDacl]; hMem
0x180009ebc  test    rcx, rcx
0x180009ebf  jz      short loc_180009ED1
0x180009ec1  call    cs:__imp_LocalFree
0x180009ec8  nop     dword ptr [rax+rax+00h]
0x180009ecd  mov     [rbp+0C0h+pDacl], rax
0x180009ed1  mov     r15, rdi
0x180009ed4  lea     rdx, [rbp+0C0h+var_88]; void **
0x180009ed8  mov     rcx, r12; pAbsoluteSecurityDescriptor
0x180009edb  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x180009ee0  test    eax, eax
0x180009ee2  jnz     short loc_180009F51
0x180009ee4  lea     rdx, aAbsolutetoself_0; "AbsoluteToSelfRelativeSD failed"
0x180009eeb  mov     ecx, esi; int
0x180009eed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009ef2  mov     ebx, 8007053Ah
0x180009ef7  test    r12, r12
0x180009efa  jnz     loc_18000A0CD
0x180009f00  test    r15, r15
0x180009f03  jnz     loc_18000A0DA
0x180009f09  mov     eax, ebx
0x180009f0b  mov     rcx, [rbp+0C0h+var_48]
0x180009f0f  xor     rcx, rbp; StackCookie
0x180009f12  call    __security_check_cookie
0x180009f17  lea     rsp, [rbp+88h]
0x180009f1e  pop     r15
0x180009f20  pop     r14
0x180009f22  pop     r13
0x180009f24  pop     r12
0x180009f26  pop     rdi
0x180009f27  pop     rsi
0x180009f28  pop     rbx
0x180009f29  pop     rbp
0x180009f2a  retn
0x180009f2c  call    cs:__imp_GetLastError
0x180009f33  nop     dword ptr [rax+rax+00h]
0x180009f38  mov     ebx, eax
0x180009f3a  test    eax, eax
0x180009f3c  jg      short loc_180009F81
0x180009f3e  lea     rdx, aGetsecuritydes_4; "GetSecurityDescriptorDacl failed: 0x%x"
0x180009f45  mov     ecx, esi; int
0x180009f47  mov     r8d, ebx
0x180009f4a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009f4f  jmp     short loc_180009EF7
0x180009f51  mov     rcx, [r13+0]; hMem
0x180009f55  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180009f5a  mov     rax, [rbp+0C0h+var_88]
0x180009f5e  mov     [r13+0], rax
0x180009f62  mov     ebx, edi
0x180009f64  jmp     short loc_180009EF7
0x180009f66  call    cs:__imp_GetLastError
0x180009f6d  nop     dword ptr [rax+rax+00h]
0x180009f72  mov     ebx, eax
0x180009f74  test    eax, eax
0x180009f76  jg      short loc_180009FD3
0x180009f78  lea     rdx, aSetsecuritydes_2; "SetSecurityDescriptorDacl failed: 0x%x"
0x180009f7f  jmp     short loc_180009F45
0x180009f81  movzx   ebx, ax
0x180009f84  or      ebx, 80070000h
0x180009f8a  jmp     short loc_180009F3E
0x180009f8c  call    cs:__imp_GetLastError
0x180009f93  nop     dword ptr [rax+rax+00h]
0x180009f98  mov     ebx, eax
0x180009f9a  test    eax, eax
0x180009f9c  jg      short loc_180009FDE
0x180009f9e  lea     rdx, aAddaceFailed0x; "AddAce failed: 0x%x"
0x180009fa5  jmp     short loc_180009F45
0x180009fa7  call    cs:__imp_GetLastError
0x180009fae  nop     dword ptr [rax+rax+00h]
0x180009fb3  mov     ebx, eax
0x180009fb5  test    eax, eax
0x180009fb7  jg      short loc_180009FE9
0x180009fb9  mov     r8d, ebx
0x180009fbc  lea     rdx, aSelfrelativeto; "SelfRelativeToAbsoluteSD failed: 0x%x"
0x180009fc3  mov     ecx, esi; int
0x180009fc5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009fca  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x180009fce  jmp     loc_180009EF7
0x180009fd3  movzx   ebx, ax
0x180009fd6  or      ebx, 80070000h
0x180009fdc  jmp     short loc_180009F78
0x180009fde  movzx   ebx, ax
0x180009fe1  or      ebx, 80070000h
0x180009fe7  jmp     short loc_180009F9E
0x180009fe9  movzx   ebx, ax
0x180009fec  or      ebx, 80070000h
0x180009ff2  jmp     short loc_180009FB9
0x180009ff4  call    cs:__imp_GetLastError
0x180009ffb  nop     dword ptr [rax+rax+00h]
0x18000a000  mov     ebx, eax
0x18000a002  test    eax, eax
0x18000a004  jle     short loc_18000A00F
0x18000a006  movzx   ebx, ax
0x18000a009  or      ebx, 80070000h
0x18000a00f  lea     rdx, aGetaceFailed0x; "GetAce failed: 0x%x"
0x18000a016  jmp     loc_180009F45
0x18000a01b  lea     rdx, aGetaclinformat_0; "GetAclInformation 0x%x"
0x18000a022  mov     ecx, 8
0x18000a027  jmp     loc_180009F47
0x18000a02c  call    cs:__imp_GetLastError
0x18000a033  nop     dword ptr [rax+rax+00h]
0x18000a038  mov     ebx, eax
0x18000a03a  test    eax, eax
0x18000a03c  jle     short loc_18000A047
0x18000a03e  movzx   ebx, ax
0x18000a041  or      ebx, 80070000h
0x18000a047  lea     rdx, aGetsecuritydes_4; "GetSecurityDescriptorDacl failed: 0x%x"
0x18000a04e  jmp     short loc_18000A022
0x18000a050  call    cs:__imp_GetLastError
0x18000a057  nop     dword ptr [rax+rax+00h]
0x18000a05c  mov     ebx, eax
0x18000a05e  test    eax, eax
0x18000a060  jle     short loc_18000A01B
0x18000a062  movzx   ebx, ax
0x18000a065  or      ebx, 80070000h
0x18000a06b  jmp     short loc_18000A01B
0x18000a06d  call    cs:__imp_GetLastError
0x18000a074  nop     dword ptr [rax+rax+00h]
0x18000a079  mov     ebx, eax
0x18000a07b  test    eax, eax
0x18000a07d  jle     short loc_18000A088
0x18000a07f  movzx   ebx, ax
0x18000a082  or      ebx, 80070000h
0x18000a088  lea     rdx, aInitializeaclF; "InitializeAcl failed: 0x%x"
  ... truncated ...
```
