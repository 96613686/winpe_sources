# Win32SecurityDescriptor::GetDescriptor(CInstance *,void * &,void * *)

- ea: `0x1800eeb7c`
- end: `0x1800ef160`
- name: `?GetDescriptor@Win32SecurityDescriptor@@QEAAXPEAVCInstance@@AEAPEAXPEAPEAX@Z`
- size: `1508`
- prototype: `void(Win32SecurityDescriptor *__hidden this, struct CInstance *, void **, void **)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180091708`
- `0x1800cb3b8`
- `0x1800cbadc`
- `0x1800cc808`
- `0x1800cd00c`
- `0x1800ef170`

## callees

- `0x180032fd8`
- `0x18003d7b0`
- `0x18006ef28`
- `0x1800896cc`
- `0x180089784`
- `0x18008bb9c`
- `0x18008bbb6`
- `0x1800ed8e8`
- `0x1800ee448`
- `0x1800eeb7c`
- `0x1800f65dc`
- `0x1800f7234`
- `0x1800f7310`
- `0x1800f92c8`
- `0x1800fc902`

## import_xrefs

- `msvcrt!free` at `0x1800eeee8`
- `msvcrt!free` at `0x1800ef002`
- `msvcrt!free` at `0x1800ef00b`
- `msvcrt!free` at `0x1800ef0e2`
- `msvcrt!free` at `0x1800ef0f3`
- `msvcrt!free` at `0x1800ef101`
- `msvcrt!free` at `0x1800eeee8`
- `msvcrt!free` at `0x1800ef002`
- `msvcrt!free` at `0x1800ef00b`
- `msvcrt!free` at `0x1800ef0e2`
- `msvcrt!free` at `0x1800ef0f3`
- `msvcrt!free` at `0x1800ef101`
- `msvcrt!malloc` at `0x1800eee78`
- `msvcrt!malloc` at `0x1800eeefa`
- `msvcrt!malloc` at `0x1800eef8b`
- `msvcrt!malloc` at `0x1800ef0a0`
- `msvcrt!malloc` at `0x1800eee78`
- `msvcrt!malloc` at `0x1800eeefa`
- `msvcrt!malloc` at `0x1800eef8b`
- `msvcrt!malloc` at `0x1800ef0a0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800eecdf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800eedda`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800eecdf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800eedda`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ef096`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ef0d5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ef096`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ef0d5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800eefec`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800eefec`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800eeedb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800eeedb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800eeea7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800eefbb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800eeea7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800eefbb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800eedf7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800eedf7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800eebda`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800eebda`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800eecfc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800eecfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ef124`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ef124`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800eebfa`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800eebfa`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800eec16`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800eec16`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800eec62`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800eed50`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800eec62`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800eed50`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800eeca7`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800eed95`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800eeca7`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800eed95`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Win32SecurityDescriptor::GetDescriptor(
        Win32SecurityDescriptor *this,
        struct CInstance *a2,
        void **a3,
        void **a4)
{
  struct _ACL *v6; // rsi
  struct MethodContext *MethodContext; // r15
  unsigned int v8; // r12d
  struct _ACL *v9; // rbx
  Win32SecurityDescriptor *v10; // rcx
  Win32SecurityDescriptor *v11; // rcx
  DWORD v12; // edi
  DWORD v13; // edx
  DWORD v14; // edi
  struct _ACL *v15; // rax
  void *v16; // rax
  void *v17; // rdi
  HLOCAL v18; // rax
  HLOCAL *v19; // rbx
  bool v20[4]; // [rsp+20h] [rbp-178h] BYREF
  unsigned __int16 v21[2]; // [rsp+24h] [rbp-174h] BYREF
  DWORD dwBufferLength; // [rsp+28h] [rbp-170h] BYREF
  struct CInstance *v23; // [rsp+30h] [rbp-168h] BYREF
  struct CInstance *v24; // [rsp+38h] [rbp-160h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-150h] BYREF
  int pExceptionObject; // [rsp+58h] [rbp-140h] BYREF
  int v28; // [rsp+5Ch] [rbp-13Ch] BYREF
  int v29; // [rsp+60h] [rbp-138h] BYREF
  int v30; // [rsp+64h] [rbp-134h] BYREF
  int v31; // [rsp+68h] [rbp-130h] BYREF
  PSID pSid; // [rsp+70h] [rbp-128h] BYREF
  int v33; // [rsp+78h] [rbp-120h]
  __int64 v34; // [rsp+80h] [rbp-118h]
  __int64 v35; // [rsp+88h] [rbp-110h]
  __int64 v36; // [rsp+90h] [rbp-108h]
  int v37; // [rsp+98h] [rbp-100h]
  PSID pGroup; // [rsp+A0h] [rbp-F8h] BYREF
  int v39; // [rsp+A8h] [rbp-F0h]
  __int64 v40; // [rsp+B0h] [rbp-E8h]
  __int64 v41; // [rsp+B8h] [rbp-E0h]
  __int64 v42; // [rsp+C0h] [rbp-D8h]
  int v43; // [rsp+C8h] [rbp-D0h]
  _OWORD pSecurityDescriptor[2]; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-A8h]
  void **v46; // [rsp+100h] [rbp-98h] BYREF
  _BYTE v47[144]; // [rsp+108h] [rbp-90h] BYREF
  size_t Size; // [rsp+1A0h] [rbp+8h] BYREF
  void **v49; // [rsp+1B0h] [rbp+18h]
  HLOCAL *v50; // [rsp+1B8h] [rbp+20h]

  v50 = a4;
  v49 = a3;
  Size = (size_t)this;
  v6 = 0;
  *a3 = 0;
  v24 = 0;
  v23 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v45 = 0;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  dwBufferLength = 0;
  v20[0] = 0;
  v21[0] = 0;
  if ( a2 )
  {
    MethodContext = CInstance::GetMethodContext(a2);
    v25 = 0;
    CInstance::GetDWORD(a2, L"ControlFlags", &v25);
    v8 = (unsigned __int16)v25;
    pSid = 0;
    v33 = 8;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    if ( CInstance::GetStatus(a2, L"Owner", v20, v21) && v20[0] && v21[0] != 1 )
    {
      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v24);
      v24 = 0;
      if ( !CInstance::GetEmbeddedObject(a2, L"Owner", &v24, MethodContext)
        || !v24
        || FillSIDFromTrustee(v24, (struct CSid *)&pSid)
        || pSid && IsValidSid(pSid) && !SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, v8 & 1) )
      {
        goto LABEL_46;
      }
    }
    pGroup = 0;
    v39 = 8;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    if ( CInstance::GetStatus(a2, L"Group", v20, v21) && v20[0] && v21[0] != 1 )
    {
      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v23);
      v23 = 0;
      if ( !CInstance::GetEmbeddedObject(a2, L"Group", &v23, MethodContext)
        || !v23
        || FillSIDFromTrustee(v23, (struct CSid *)&pGroup)
        || pGroup && IsValidSid(pGroup) && !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, (v8 >> 1) & 1) )
      {
LABEL_45:
        CSid::~CSid(&pGroup);
LABEL_46:
        CSid::~CSid(&pSid);
        goto LABEL_47;
      }
    }
    v46 = &CDACL::`vftable';
    memset_0(v47, 0, 0x50u);
    v9 = 0;
    LODWORD(Size) = 0;
    if ( Win32SecurityDescriptor::FillDACLFromInstance(v10, a2, (struct CDACL *)&v46, MethodContext)
      || !CDACL::CalculateDACLSize((CDACL *)&v46, (unsigned int *)&Size) )
    {
      goto LABEL_33;
    }
    v12 = Size;
    if ( (unsigned int)Size <= 8 )
    {
      if ( (_DWORD)Size )
        goto LABEL_33;
      v9 = (struct _ACL *)malloc(8u);
      if ( !v9 )
      {
        v28 = 0;
        throw (CHeap_Exception *)&v28;
      }
      v13 = 8;
    }
    else
    {
      v9 = (struct _ACL *)malloc((unsigned int)Size);
      if ( !v9 )
      {
        pExceptionObject = 0;
        throw (CHeap_Exception *)&pExceptionObject;
      }
      v13 = v12;
    }
    InitializeAcl(v9, v13, 2u);
    if ( CDACL::FillDACL((CDACL *)&v46, v9) || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, (v8 >> 3) & 1) )
    {
      free(v9);
LABEL_44:
      v46 = &CDACL::`vftable';
      CDACL::Clear((CDACL *)&v46);
      goto LABEL_45;
    }
LABEL_33:
    v26[0] = &CSACL::`vftable';
    v26[1] = 0;
    LODWORD(Size) = 0;
    if ( Win32SecurityDescriptor::FillSACLFromInstance(v11, a2, (struct CSACL *)v26, MethodContext) )
      goto LABEL_48;
    if ( !(unsigned int)CSACL::CalculateSACLSize((CSACL *)v26, (unsigned int *)&Size) )
      goto LABEL_48;
    v14 = Size;
    if ( (unsigned int)Size <= 8 )
      goto LABEL_48;
    v15 = (struct _ACL *)malloc((unsigned int)Size);
    v6 = v15;
    if ( !v15 )
    {
      v29 = 0;
      throw (CHeap_Exception *)&v29;
    }
    InitializeAcl(v15, v14, 2u);
    if ( !CSACL::FillSACL((CSACL *)v26, v6) && SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v6, (v8 >> 5) & 1) )
    {
LABEL_48:
      MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
      v16 = malloc(dwBufferLength);
      v17 = v16;
      if ( !v16 )
      {
        v30 = 0;
        throw (CHeap_Exception *)&v30;
      }
      if ( !MakeSelfRelativeSD(pSecurityDescriptor, v16, &dwBufferLength) )
      {
        free(v17);
        v17 = 0;
      }
      if ( v9 )
        free(v9);
      if ( v6 )
        free(v6);
      *v49 = v17;
      if ( a4 )
      {
        try
        {
          v18 = LocalAlloc(0x40u, dwBufferLength);
          *a4 = v18;
          if ( !v18 )
          {
            v31 = 0;
            throw (CHeap_Exception *)&v31;
          }
          memcpy_0(v18, v17, dwBufferLength);
        }
        catch ( ... )
        {
          v19 = v50;
          if ( *v50 )
          {
            LocalFree(*v50);
            *v19 = 0;
          }
          throw;
        }
      }
    }
    else
    {
      if ( v9 )
        free(v9);
      free(v6);
    }
    v26[0] = &CSACL::`vftable';
    CSACL::Clear((CSACL *)v26);
    goto LABEL_44;
  }
LABEL_47:
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v23);
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v24);
}

```

## disassembly

```asm
0x1800eeb7c  mov     r11, rsp
0x1800eeb7f  mov     [r11+20h], r9
0x1800eeb83  mov     [r11+18h], r8
0x1800eeb87  mov     [r11+8], rcx
0x1800eeb8b  push    rbx
0x1800eeb8c  push    rsi
0x1800eeb8d  push    rdi
0x1800eeb8e  push    r12
0x1800eeb90  push    r13
0x1800eeb92  push    r14
0x1800eeb94  push    r15
0x1800eeb96  sub     rsp, 160h
0x1800eeb9d  mov     r13, r9
0x1800eeba0  mov     r14, rdx
0x1800eeba3  xor     esi, esi
0x1800eeba5  mov     [r8], rsi
0x1800eeba8  mov     [rsp+198h+var_160], rsi
0x1800eebad  mov     [rsp+198h+var_168], rsi
0x1800eebb2  xorps   xmm0, xmm0
0x1800eebb5  xor     eax, eax
0x1800eebb7  movups  [rsp+198h+pSecurityDescriptor], xmm0
0x1800eebbf  movups  [rsp+198h+var_B8], xmm0
0x1800eebc7  mov     [r11-0A8h], rax
0x1800eebce  lea     edi, [rsi+1]
0x1800eebd1  mov     edx, edi; dwRevision
0x1800eebd3  lea     rcx, [r11-0C8h]; pSecurityDescriptor
0x1800eebda  call    cs:__imp_InitializeSecurityDescriptor
0x1800eebe0  mov     [rsp+198h+dwBufferLength], esi
0x1800eebe4  mov     [rsp+198h+var_178], sil
0x1800eebe9  mov     [rsp+198h+var_174], si
0x1800eebee  test    r14, r14
0x1800eebf1  jz      loc_1800EF05F
0x1800eebf7  mov     rcx, r14
0x1800eebfa  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800eec00  mov     r15, rax
0x1800eec03  mov     [rsp+198h+var_158], esi
0x1800eec07  lea     r8, [rsp+198h+var_158]
0x1800eec0c  lea     rdx, aControlflags; "ControlFlags"
0x1800eec13  mov     rcx, r14
0x1800eec16  call    cs:__imp_?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z; CInstance::GetDWORD(ushort const *,ulong &)
0x1800eec1c  movzx   r12d, word ptr [rsp+198h+var_158]
0x1800eec22  mov     [rsp+198h+pSid], rsi
0x1800eec27  mov     [rsp+198h+var_120], 8
0x1800eec2f  mov     [rsp+198h+var_118], rsi
0x1800eec37  mov     [rsp+198h+var_110], rsi
0x1800eec3f  mov     [rsp+198h+var_108], rsi
0x1800eec47  mov     [rsp+198h+var_100], esi
0x1800eec4e  lea     r9, [rsp+198h+var_174]
0x1800eec53  lea     r8, [rsp+198h+var_178]
0x1800eec58  lea     rdx, aOwner; "Owner"
0x1800eec5f  mov     rcx, r14
0x1800eec62  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800eec68  test    al, al
0x1800eec6a  jz      loc_1800EED0A
0x1800eec70  cmp     [rsp+198h+var_178], sil
0x1800eec75  jz      loc_1800EED0A
0x1800eec7b  cmp     [rsp+198h+var_174], di
0x1800eec80  jz      loc_1800EED0A
0x1800eec86  lea     rcx, [rsp+198h+var_160]
0x1800eec8b  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800eec90  mov     [rsp+198h+var_160], rsi
0x1800eec95  mov     r9, r15
0x1800eec98  lea     r8, [rsp+198h+var_160]
0x1800eec9d  lea     rdx, aOwner; "Owner"
0x1800eeca4  mov     rcx, r14
0x1800eeca7  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x1800eecad  test    al, al
0x1800eecaf  jz      loc_1800EF054
0x1800eecb5  mov     rcx, [rsp+198h+var_160]; struct CInstance *
0x1800eecba  test    rcx, rcx
0x1800eecbd  jz      loc_1800EF054
0x1800eecc3  lea     rdx, [rsp+198h+pSid]; struct CSid *
0x1800eecc8  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x1800eeccd  test    eax, eax
0x1800eeccf  jnz     loc_1800EF054
0x1800eecd5  mov     rcx, [rsp+198h+pSid]; pSid
0x1800eecda  test    rcx, rcx
0x1800eecdd  jz      short loc_1800EED0A
0x1800eecdf  call    cs:__imp_IsValidSid
0x1800eece5  test    eax, eax
0x1800eece7  jz      short loc_1800EED0A
0x1800eece9  mov     r8d, r12d
0x1800eecec  and     r8d, edi; bOwnerDefaulted
0x1800eecef  mov     rdx, [rsp+198h+pSid]; pOwner
0x1800eecf4  lea     rcx, [rsp+198h+pSecurityDescriptor]; pSecurityDescriptor
0x1800eecfc  call    cs:__imp_SetSecurityDescriptorOwner
0x1800eed02  test    eax, eax
0x1800eed04  jz      loc_1800EF054
0x1800eed0a  mov     [rsp+198h+pGroup], rsi
0x1800eed12  mov     [rsp+198h+var_F0], 8
0x1800eed1d  mov     [rsp+198h+var_E8], rsi
0x1800eed25  mov     [rsp+198h+var_E0], rsi
0x1800eed2d  mov     [rsp+198h+var_D8], rsi
0x1800eed35  mov     [rsp+198h+var_D0], esi
0x1800eed3c  lea     r9, [rsp+198h+var_174]
0x1800eed41  lea     r8, [rsp+198h+var_178]
0x1800eed46  lea     rdx, aGroup; "Group"
0x1800eed4d  mov     rcx, r14
0x1800eed50  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800eed56  test    al, al
0x1800eed58  jz      loc_1800EEE05
0x1800eed5e  cmp     [rsp+198h+var_178], sil
0x1800eed63  jz      loc_1800EEE05
0x1800eed69  cmp     [rsp+198h+var_174], di
0x1800eed6e  jz      loc_1800EEE05
0x1800eed74  lea     rcx, [rsp+198h+var_168]
0x1800eed79  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800eed7e  mov     [rsp+198h+var_168], rsi
0x1800eed83  mov     r9, r15
0x1800eed86  lea     r8, [rsp+198h+var_168]
0x1800eed8b  lea     rdx, aGroup; "Group"
0x1800eed92  mov     rcx, r14
0x1800eed95  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x1800eed9b  test    al, al
0x1800eed9d  jz      loc_1800EF046
0x1800eeda3  mov     rcx, [rsp+198h+var_168]; struct CInstance *
0x1800eeda8  test    rcx, rcx
0x1800eedab  jz      loc_1800EF046
0x1800eedb1  lea     rdx, [rsp+198h+pGroup]; struct CSid *
0x1800eedb9  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x1800eedbe  test    eax, eax
0x1800eedc0  jnz     loc_1800EF046
0x1800eedc6  mov     ebx, r12d
0x1800eedc9  shr     ebx, 1
0x1800eedcb  and     ebx, edi
0x1800eedcd  mov     rcx, [rsp+198h+pGroup]; pSid
0x1800eedd5  test    rcx, rcx
0x1800eedd8  jz      short loc_1800EEE05
0x1800eedda  call    cs:__imp_IsValidSid
0x1800eede0  test    eax, eax
0x1800eede2  jz      short loc_1800EEE05
0x1800eede4  mov     r8d, ebx; bGroupDefaulted
0x1800eede7  mov     rdx, [rsp+198h+pGroup]; pGroup
0x1800eedef  lea     rcx, [rsp+198h+pSecurityDescriptor]; pSecurityDescriptor
0x1800eedf7  call    cs:__imp_SetSecurityDescriptorGroup
0x1800eedfd  test    eax, eax
0x1800eedff  jz      loc_1800EF046
0x1800eee05  lea     rax, ??_7CDACL@@6B@; const CDACL::`vftable'
0x1800eee0c  mov     [rsp+198h+var_98], rax
0x1800eee14  xor     edx, edx; Val
0x1800eee16  lea     r8d, [rdx+50h]; Size
0x1800eee1a  lea     rcx, [rsp+198h+var_90]; void *
0x1800eee22  call    memset_0
0x1800eee27  nop
0x1800eee28  mov     rbx, rsi
0x1800eee2b  mov     dword ptr [rsp+198h+Size], esi
0x1800eee32  mov     r9, r15; struct MethodContext *
0x1800eee35  lea     r8, [rsp+198h+var_98]; struct CDACL *
0x1800eee3d  mov     rdx, r14; struct CInstance *
0x1800eee40  call    ?FillDACLFromInstance@Win32SecurityDescriptor@@QEAAKPEAVCInstance@@AEAVCDACL@@PEAVMethodContext@@@Z; Win32SecurityDescriptor::FillDACLFromInstance(CInstance *,CDACL &,MethodContext *)
0x1800eee45  test    eax, eax
0x1800eee47  jnz     loc_1800EEF28
0x1800eee4d  lea     rdx, [rsp+198h+Size]; unsigned int *
0x1800eee55  lea     rcx, [rsp+198h+var_98]; this
0x1800eee5d  call    ?CalculateDACLSize@CDACL@@QEAAHPEAK@Z; CDACL::CalculateDACLSize(ulong *)
0x1800eee62  test    eax, eax
0x1800eee64  jz      loc_1800EEF28
0x1800eee6a  mov     edi, dword ptr [rsp+198h+Size]
0x1800eee71  cmp     edi, 8
0x1800eee74  jbe     short loc_1800EEEF3
0x1800eee76  mov     ecx, edi; Size
0x1800eee78  call    cs:__imp_malloc
0x1800eee7e  mov     rbx, rax
0x1800eee81  test    rax, rax
0x1800eee84  jnz     short loc_1800EEE9C
0x1800eee86  mov     [rsp+198h+pExceptionObject], esi
0x1800eee8a  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1800eee91  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x1800eee96  call    _CxxThrowException_0
0x1800eee9c  mov     edx, edi; nAclLength
0x1800eee9e  mov     r8d, 2; dwAclRevision
0x1800eeea4  mov     rcx, rbx; pAcl
0x1800eeea7  call    cs:__imp_InitializeAcl
0x1800eeead  mov     edi, r12d
0x1800eeeb0  shr     edi, 3
0x1800eeeb3  and     edi, 1
0x1800eeeb6  mov     rdx, rbx; pAcl
0x1800eeeb9  lea     rcx, [rsp+198h+var_98]; this
0x1800eeec1  call    ?FillDACL@CDACL@@QEAAKPEAU_ACL@@@Z; CDACL::FillDACL(_ACL *)
0x1800eeec6  test    eax, eax
0x1800eeec8  jnz     short loc_1800EEEE5
0x1800eeeca  mov     r9d, edi; bDaclDefaulted
0x1800eeecd  mov     r8, rbx; pDacl
0x1800eeed0  lea     edx, [rax+1]; bDaclPresent
0x1800eeed3  lea     rcx, [rsp+198h+pSecurityDescriptor]; pSecurityDescriptor
0x1800eeedb  call    cs:__imp_SetSecurityDescriptorDacl
0x1800eeee1  test    eax, eax
0x1800eeee3  jnz     short loc_1800EEF28
0x1800eeee5  mov     rcx, rbx; Block
0x1800eeee8  call    cs:__imp_free
0x1800eeeee  jmp     loc_1800EF029
0x1800eeef3  test    edi, edi
0x1800eeef5  jnz     short loc_1800EEF28
0x1800eeef7  lea     ecx, [rdi+8]; Size
0x1800eeefa  call    cs:__imp_malloc
0x1800eef00  mov     rbx, rax
0x1800eef03  test    rax, rax
0x1800eef06  jnz     short loc_1800EEF1E
0x1800eef08  mov     [rsp+198h+var_13C], esi
0x1800eef0c  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1800eef13  lea     rcx, [rsp+198h+var_13C]; pExceptionObject
0x1800eef18  call    _CxxThrowException_0
0x1800eef1e  mov     edx, 8
0x1800eef23  jmp     loc_1800EEE9E
0x1800eef28  lea     rax, ??_7CSACL@@6B@; const CSACL::`vftable'
0x1800eef2f  mov     [rsp+198h+var_150], rax
0x1800eef34  mov     [rsp+198h+var_148], rsi
0x1800eef39  mov     dword ptr [rsp+198h+Size], 0
0x1800eef44  mov     r9, r15; struct MethodContext *
0x1800eef47  lea     r8, [rsp+198h+var_150]; struct CSACL *
0x1800eef4c  mov     rdx, r14; struct CInstance *
0x1800eef4f  call    ?FillSACLFromInstance@Win32SecurityDescriptor@@QEAAKPEAVCInstance@@AEAVCSACL@@PEAVMethodContext@@@Z; Win32SecurityDescriptor::FillSACLFromInstance(CInstance *,CSACL &,MethodContext *)
0x1800eef54  xor     r14d, r14d
0x1800eef57  test    eax, eax
0x1800eef59  jnz     loc_1800EF087
0x1800eef5f  lea     rdx, [rsp+198h+Size]; unsigned int *
0x1800eef67  lea     rcx, [rsp+198h+var_150]; this
0x1800eef6c  call    ?CalculateSACLSize@CSACL@@QEAAHPEAK@Z; CSACL::CalculateSACLSize(ulong *)
0x1800eef71  test    eax, eax
0x1800eef73  jz      loc_1800EF087
0x1800eef79  mov     edi, dword ptr [rsp+198h+Size]
0x1800eef80  cmp     edi, 8
0x1800eef83  jbe     loc_1800EF087
0x1800eef89  mov     ecx, edi; Size
0x1800eef8b  call    cs:__imp_malloc
0x1800eef91  mov     rsi, rax
0x1800eef94  test    rax, rax
0x1800eef97  jnz     short loc_1800EEFB0
0x1800eef99  mov     [rsp+198h+var_138], r14d
0x1800eef9e  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1800eefa5  lea     rcx, [rsp+198h+var_138]; pExceptionObject
0x1800eefaa  call    _CxxThrowException_0
0x1800eefb0  mov     r8d, 2; dwAclRevision
0x1800eefb6  mov     edx, edi; nAclLength
0x1800eefb8  mov     rcx, rsi; pAcl
0x1800eefbb  call    cs:__imp_InitializeAcl
0x1800eefc1  mov     edi, r12d
0x1800eefc4  shr     edi, 5
0x1800eefc7  and     edi, 1
0x1800eefca  mov     rdx, rsi; struct _ACL *
0x1800eefcd  lea     rcx, [rsp+198h+var_150]; this
0x1800eefd2  call    ?FillSACL@CSACL@@QEAAKPEAU_ACL@@@Z; CSACL::FillSACL(_ACL *)
0x1800eefd7  test    eax, eax
0x1800eefd9  jnz     short loc_1800EEFFA
0x1800eefdb  mov     r9d, edi; bSaclDefaulted
0x1800eefde  mov     r8, rsi; pSacl
0x1800eefe1  lea     edx, [rax+1]; bSaclPresent
0x1800eefe4  lea     rcx, [rsp+198h+pSecurityDescriptor]; pSecurityDescriptor
0x1800eefec  call    cs:__imp_SetSecurityDescriptorSacl
0x1800eeff2  test    eax, eax
0x1800eeff4  jnz     loc_1800EF087
0x1800eeffa  test    rbx, rbx
0x1800eeffd  jz      short loc_1800EF008
0x1800eefff  mov     rcx, rbx; Block
0x1800ef002  call    cs:__imp_free
0x1800ef008  mov     rcx, rsi; Block
0x1800ef00b  call    cs:__imp_free
0x1800ef011  nop
0x1800ef012  lea     rax, ??_7CSACL@@6B@; const CSACL::`vftable'
0x1800ef019  mov     [rsp+198h+var_150], rax
0x1800ef01e  lea     rcx, [rsp+198h+var_150]; this
0x1800ef023  call    ?Clear@CSACL@@QEAAXXZ; CSACL::Clear(void)
0x1800ef028  nop
0x1800ef029  lea     rax, ??_7CDACL@@6B@; const CDACL::`vftable'
0x1800ef030  mov     [rsp+198h+var_98], rax
0x1800ef038  lea     rcx, [rsp+198h+var_98]; this
0x1800ef040  call    ?Clear@CDACL@@QEAAXXZ; CDACL::Clear(void)
0x1800ef045  nop
0x1800ef046  lea     rcx, [rsp+198h+pGroup]; this
0x1800ef04e  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800ef053  nop
0x1800ef054  lea     rcx, [rsp+198h+pSid]; this
0x1800ef059  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800ef05e  nop
0x1800ef05f  lea     rcx, [rsp+198h+var_168]
0x1800ef064  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800ef069  nop
0x1800ef06a  lea     rcx, [rsp+198h+var_160]
0x1800ef06f  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800ef074  add     rsp, 160h
0x1800ef07b  pop     r15
0x1800ef07d  pop     r14
0x1800ef07f  pop     r13
0x1800ef081  pop     r12
0x1800ef083  pop     rdi
0x1800ef084  pop     rsi
0x1800ef085  pop     rbx
0x1800ef086  retn
0x1800ef087  lea     r8, [rsp+198h+dwBufferLength]; lpdwBufferLength
0x1800ef08c  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800ef08e  lea     rcx, [rsp+198h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800ef096  call    cs:__imp_MakeSelfRelativeSD
0x1800ef09c  mov     ecx, [rsp+198h+dwBufferLength]; Size
0x1800ef0a0  call    cs:__imp_malloc
0x1800ef0a6  mov     rdi, rax
0x1800ef0a9  test    rax, rax
0x1800ef0ac  jnz     short loc_1800EF0C5
0x1800ef0ae  mov     [rsp+198h+var_134], r14d
0x1800ef0b3  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1800ef0ba  lea     rcx, [rsp+198h+var_134]; pExceptionObject
  ... truncated ...
```
