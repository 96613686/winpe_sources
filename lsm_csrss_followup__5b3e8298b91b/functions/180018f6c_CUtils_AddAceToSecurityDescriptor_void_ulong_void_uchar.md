# CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)

- ea: `0x180018f6c`
- end: `0x1800193e7`
- name: `?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z`
- size: `1147`
- prototype: `static int(void **, unsigned int, void *, unsigned __int8)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a20`
- `0x180018e68`
- `0x180028858`

## callees

- `0x1800074c0`
- `0x180018f6c`
- `0x1800193f0`
- `0x180019734`
- `0x180019f28`
- `0x18004b460`
- `0x18004bf08`
- `0x180093fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001925b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001930b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001933d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001935b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001925b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001930b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001933d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001935b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019372`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019100`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800191f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800191f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800190df`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800190df`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001902c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001902c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18001901b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18001901b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180019140`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180019140`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180019166`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001918f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180019166`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001918f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001911e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001911e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180018ff4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800191c5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180018ff4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800191c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800191e0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800191e0`

## string_xrefs

- `0x180019267`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x180019352`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x18001929b`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x18001932c`: `GetAclInformation 0x%x`
- `0x180019387`: `InitializeAcl failed: 0x%x`
- `0x1800193b6`: `SD has NULL DACL, Present %d, Defaulted %d`

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
0x180018f6c  mov     [rsp-8+arg_18], r9b
0x180018f71  mov     [rsp-8+arg_8], edx
0x180018f75  push    rbp
0x180018f76  push    rbx
0x180018f77  push    rsi
0x180018f78  push    rdi
0x180018f79  push    r12
0x180018f7b  push    r13
0x180018f7d  push    r14
0x180018f7f  push    r15
0x180018f81  sub     rsp, 0B8h
0x180018f88  lea     rbp, [rsp+30h]
0x180018f8d  mov     rax, cs:__security_cookie
0x180018f94  xor     rax, rbp
0x180018f97  mov     [rbp+0C0h+var_48], rax
0x180018f9b  mov     r14, r8
0x180018f9e  mov     r13, rcx
0x180018fa1  mov     [rbp+0C0h+var_70], rcx
0x180018fa5  mov     [rbp+0C0h+var_68], r8
0x180018fa9  xor     edi, edi
0x180018fab  mov     [rbp+0C0h+bDaclPresent], edi
0x180018fae  mov     [rbp+0C0h+bDaclDefaulted], edi
0x180018fb1  mov     [rbp+0C0h+pAce], rdi
0x180018fb5  xor     eax, eax
0x180018fb7  mov     [rbp+0C0h+pAclInformation], rax
0x180018fbb  mov     [rbp+0C0h+var_50], eax
0x180018fbe  mov     [rbp+0C0h+pDacl], rdi
0x180018fc2  mov     r15d, edi
0x180018fc5  mov     [rbp+0C0h+var_88], rdi
0x180018fc9  mov     r12d, edi
0x180018fcc  mov     [rbp+0C0h+pSecurityDescriptor], rdi
0x180018fd0  mov     rax, [rcx]
0x180018fd3  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x180018fd7  mov     [rbp+0C0h+var_60], rax
0x180018fdb  cmp     [rax+2], di
0x180018fdf  jge     loc_180019393
0x180018fe5  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x180018fe9  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x180018fed  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x180018ff1  mov     rcx, rax; pSecurityDescriptor
0x180018ff4  call    cs:__imp_GetSecurityDescriptorDacl
0x180018ffa  test    eax, eax
0x180018ffc  jz      loc_18001933D
0x180019002  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180019006  test    rcx, rcx
0x180019009  jz      loc_1800193AE
0x18001900f  lea     r9d, [rdi+2]; dwAclInformationClass
0x180019013  lea     r8d, [rdi+0Ch]; nAclInformationLength
0x180019017  lea     rdx, [rbp+0C0h+pAclInformation]; pAclInformation
0x18001901b  call    cs:__imp_GetAclInformation
0x180019021  test    eax, eax
0x180019023  jz      loc_18001935B
0x180019029  mov     rcx, r14; pSid
0x18001902c  call    cs:__imp_GetLengthSid
0x180019032  mov     r8d, eax
0x180019035  mov     [rbp+0C0h+var_A0], eax
0x180019038  lea     esi, [rdi+8]
0x18001903b  lea     edx, [rsi+rax]
0x18001903e  mov     word ptr [rbp+0C0h+var_BC], dx
0x180019042  mov     [rbp+0C0h+pAceList], dx
0x180019046  movzx   eax, dx
0x180019049  lea     rcx, [rax+0Fh]
0x18001904d  cmp     rcx, rax
0x180019050  ja      short loc_18001905C
0x180019052  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001905c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180019060  mov     rax, rcx
0x180019063  call    _alloca_probe
0x180019068  sub     rsp, rcx
0x18001906b  lea     rbx, [rsp+0F0h+pAceList]
0x180019070  mov     [rbp+0C0h+var_80], rbx
0x180019074  jmp     short loc_1800190B9
0x180019076  call    _o__resetstkoflw_0
0x18001907b  xor     ebx, ebx
0x18001907d  mov     [rbp+0C0h+var_80], rbx
0x180019081  movzx   r8d, [rbp+0C0h+pAceList]
0x180019086  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18001908d  lea     ecx, [rbx+8]; int
0x180019090  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019095  xor     edi, edi
0x180019097  lea     esi, [rbx+8]
0x18001909a  mov     r15d, ebx
0x18001909d  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x1800190a1  mov     r13, [rbp+0C0h+var_70]
0x1800190a5  mov     r14, [rbp+0C0h+var_68]
0x1800190a9  mov     rax, [rbp+0C0h+var_60]
0x1800190ad  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x1800190b1  movzx   edx, word ptr [rbp+0C0h+var_BC]
0x1800190b5  mov     r8d, [rbp+0C0h+var_A0]
0x1800190b9  test    rbx, rbx
0x1800190bc  jz      loc_1800193A4
0x1800190c2  mov     word ptr [rbx], 0
0x1800190c7  mov     [rbx+2], dx
0x1800190cb  mov     eax, [rbp+0C0h+arg_8]
0x1800190d1  mov     [rbx+4], eax
0x1800190d4  lea     rdx, [rbx+8]; pDestinationSid
0x1800190d8  movzx   ecx, r8w; nDestinationSidLength
0x1800190dc  mov     r8, r14; pSourceSid
0x1800190df  call    cs:__imp_CopySid
0x1800190e5  cmp     [rbp+0C0h+arg_18], dil
0x1800190ec  jz      short loc_1800190F2
0x1800190ee  or      byte ptr [rbx+1], 0Bh
0x1800190f2  movzx   r14d, word ptr [rbx+2]
0x1800190f7  add     r14d, dword ptr [rbp+0C0h+pAclInformation+4]
0x1800190fb  mov     edx, r14d; uBytes
0x1800190fe  xor     ecx, ecx; uFlags
0x180019100  call    cs:__imp_LocalAlloc
0x180019106  mov     r15, rax
0x180019109  test    rax, rax
0x18001910c  jz      loc_1800193A4
0x180019112  mov     r8d, 2; dwAclRevision
0x180019118  mov     edx, r14d; nAclLength
0x18001911b  mov     rcx, rax; pAcl
0x18001911e  call    cs:__imp_InitializeAcl
0x180019124  test    eax, eax
0x180019126  jz      loc_180019372
0x18001912c  mov     r14d, edi
0x18001912f  cmp     r14d, dword ptr [rbp+0C0h+pAclInformation]
0x180019133  jnb     short loc_180019179
0x180019135  lea     r8, [rbp+0C0h+pAce]; pAce
0x180019139  mov     edx, r14d; dwAceIndex
0x18001913c  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180019140  call    cs:__imp_GetAce
0x180019146  test    eax, eax
0x180019148  jz      loc_18001930B
0x18001914e  mov     r9, [rbp+0C0h+pAce]; pAceList
0x180019152  movzx   eax, word ptr [r9+2]
0x180019157  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x18001915b  mov     r8d, r14d; dwStartingAceIndex
0x18001915e  mov     edx, 2; dwAceRevision
0x180019163  mov     rcx, r15; pAcl
0x180019166  call    cs:__imp_AddAce
0x18001916c  test    eax, eax
0x18001916e  jz      loc_1800192AF
0x180019174  inc     r14d
0x180019177  jmp     short loc_18001912F
0x180019179  movzx   eax, word ptr [rbx+2]
0x18001917d  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x180019181  mov     r9, rbx; pAceList
0x180019184  mov     r8d, r14d; dwStartingAceIndex
0x180019187  mov     edx, 2; dwAceRevision
0x18001918c  mov     rcx, r15; pAcl
0x18001918f  call    cs:__imp_AddAce
0x180019195  test    eax, eax
0x180019197  jz      loc_1800192AF
0x18001919d  lea     rdx, [rbp+0C0h+pSecurityDescriptor]; void **
0x1800191a1  mov     rcx, [rbp+0C0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800191a5  call    ?SelfRelativeToAbsoluteSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::SelfRelativeToAbsoluteSD(void *,void * *,ulong *)
0x1800191aa  test    eax, eax
0x1800191ac  jz      loc_1800192C4
0x1800191b2  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x1800191b6  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x1800191ba  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x1800191be  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x1800191c2  mov     rcx, r12; pSecurityDescriptor
0x1800191c5  call    cs:__imp_GetSecurityDescriptorDacl
0x1800191cb  test    eax, eax
0x1800191cd  jz      loc_18001925B
0x1800191d3  xor     r9d, r9d; bDaclDefaulted
0x1800191d6  mov     r8, r15; pDacl
0x1800191d9  lea     edx, [r9+1]; bDaclPresent
0x1800191dd  mov     rcx, r12; pSecurityDescriptor
0x1800191e0  call    cs:__imp_SetSecurityDescriptorDacl
0x1800191e6  test    eax, eax
0x1800191e8  jz      loc_18001928F
0x1800191ee  mov     rcx, [rbp+0C0h+pDacl]; hMem
0x1800191f2  test    rcx, rcx
0x1800191f5  jz      short loc_180019201
0x1800191f7  call    cs:__imp_LocalFree
0x1800191fd  mov     [rbp+0C0h+pDacl], rax
0x180019201  mov     r15, rdi
0x180019204  lea     rdx, [rbp+0C0h+var_88]; void **
0x180019208  mov     rcx, r12; pAbsoluteSecurityDescriptor
0x18001920b  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x180019210  test    eax, eax
0x180019212  jnz     short loc_18001927A
0x180019214  lea     rdx, aAbsolutetoself_0; "AbsoluteToSelfRelativeSD failed"
0x18001921b  mov     ecx, esi; int
0x18001921d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019222  mov     ebx, 8007053Ah
0x180019227  test    r12, r12
0x18001922a  jnz     loc_1800193CC
0x180019230  test    r15, r15
0x180019233  jnz     loc_1800193D9
0x180019239  mov     eax, ebx
0x18001923b  mov     rcx, [rbp+0C0h+var_48]
0x18001923f  xor     rcx, rbp; StackCookie
0x180019242  call    __security_check_cookie
0x180019247  lea     rsp, [rbp+88h]
0x18001924e  pop     r15
0x180019250  pop     r14
0x180019252  pop     r13
0x180019254  pop     r12
0x180019256  pop     rdi
0x180019257  pop     rsi
0x180019258  pop     rbx
0x180019259  pop     rbp
0x18001925a  retn
0x18001925b  call    cs:__imp_GetLastError
0x180019261  mov     ebx, eax
0x180019263  test    eax, eax
0x180019265  jg      short loc_1800192A4
0x180019267  lea     rdx, aGetsecuritydes_4; "GetSecurityDescriptorDacl failed: 0x%x"
0x18001926e  mov     ecx, esi; int
0x180019270  mov     r8d, ebx
0x180019273  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019278  jmp     short loc_180019227
0x18001927a  mov     rcx, [r13+0]; hMem
0x18001927e  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180019283  mov     rax, [rbp+0C0h+var_88]
0x180019287  mov     [r13+0], rax
0x18001928b  mov     ebx, edi
0x18001928d  jmp     short loc_180019227
0x18001928f  call    cs:__imp_GetLastError
0x180019295  mov     ebx, eax
0x180019297  test    eax, eax
0x180019299  jg      short loc_1800192EA
0x18001929b  lea     rdx, aSetsecuritydes_2; "SetSecurityDescriptorDacl failed: 0x%x"
0x1800192a2  jmp     short loc_18001926E
0x1800192a4  movzx   ebx, ax
0x1800192a7  or      ebx, 80070000h
0x1800192ad  jmp     short loc_180019267
0x1800192af  call    cs:__imp_GetLastError
0x1800192b5  mov     ebx, eax
0x1800192b7  test    eax, eax
0x1800192b9  jg      short loc_1800192F5
0x1800192bb  lea     rdx, aAddaceFailed0x; "AddAce failed: 0x%x"
0x1800192c2  jmp     short loc_18001926E
0x1800192c4  call    cs:__imp_GetLastError
0x1800192ca  mov     ebx, eax
0x1800192cc  test    eax, eax
0x1800192ce  jg      short loc_180019300
0x1800192d0  mov     r8d, ebx
0x1800192d3  lea     rdx, aSelfrelativeto; "SelfRelativeToAbsoluteSD failed: 0x%x"
0x1800192da  mov     ecx, esi; int
0x1800192dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800192e1  mov     r12, [rbp+0C0h+pSecurityDescriptor]
0x1800192e5  jmp     loc_180019227
0x1800192ea  movzx   ebx, ax
0x1800192ed  or      ebx, 80070000h
0x1800192f3  jmp     short loc_18001929B
0x1800192f5  movzx   ebx, ax
0x1800192f8  or      ebx, 80070000h
0x1800192fe  jmp     short loc_1800192BB
0x180019300  movzx   ebx, ax
0x180019303  or      ebx, 80070000h
0x180019309  jmp     short loc_1800192D0
0x18001930b  call    cs:__imp_GetLastError
0x180019311  mov     ebx, eax
0x180019313  test    eax, eax
0x180019315  jle     short loc_180019320
0x180019317  movzx   ebx, ax
0x18001931a  or      ebx, 80070000h
0x180019320  lea     rdx, aGetaceFailed0x; "GetAce failed: 0x%x"
0x180019327  jmp     loc_18001926E
0x18001932c  lea     rdx, aGetaclinformat_0; "GetAclInformation 0x%x"
0x180019333  mov     ecx, 8
0x180019338  jmp     loc_180019270
0x18001933d  call    cs:__imp_GetLastError
0x180019343  mov     ebx, eax
0x180019345  test    eax, eax
0x180019347  jle     short loc_180019352
0x180019349  movzx   ebx, ax
0x18001934c  or      ebx, 80070000h
0x180019352  lea     rdx, aGetsecuritydes_4; "GetSecurityDescriptorDacl failed: 0x%x"
0x180019359  jmp     short loc_180019333
0x18001935b  call    cs:__imp_GetLastError
0x180019361  mov     ebx, eax
0x180019363  test    eax, eax
0x180019365  jle     short loc_18001932C
0x180019367  movzx   ebx, ax
0x18001936a  or      ebx, 80070000h
0x180019370  jmp     short loc_18001932C
0x180019372  call    cs:__imp_GetLastError
0x180019378  mov     ebx, eax
0x18001937a  test    eax, eax
0x18001937c  jle     short loc_180019387
0x18001937e  movzx   ebx, ax
0x180019381  or      ebx, 80070000h
0x180019387  lea     rdx, aInitializeaclF; "InitializeAcl failed: 0x%x"
0x18001938e  jmp     loc_18001926E
0x180019393  lea     rdx, aSdIsNotSelfRel; "SD is not Self-Relative"
0x18001939a  mov     ecx, 8
0x18001939f  jmp     loc_18001921D
0x1800193a4  mov     ebx, 8007000Eh
0x1800193a9  jmp     loc_180019227
0x1800193ae  mov     r9d, [rbp+0C0h+bDaclDefaulted]
0x1800193b2  mov     r8d, [rbp+0C0h+bDaclPresent]
0x1800193b6  lea     rdx, aSdHasNullDaclP; "SD has NULL DACL, Present %d, Defaulted"...
0x1800193bd  mov     ecx, 8; int
0x1800193c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800193c7  jmp     loc_18001928B
0x1800193cc  mov     rcx, r12; hMem
0x1800193cf  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800193d4  jmp     loc_180019230
0x1800193d9  mov     rcx, r15; hMem
0x1800193dc  call    cs:__imp_LocalFree
0x1800193e2  jmp     loc_180019239
0x1800946a8  push    rbp
0x1800946aa  sub     rsp, 30h
  ... truncated ...
```
