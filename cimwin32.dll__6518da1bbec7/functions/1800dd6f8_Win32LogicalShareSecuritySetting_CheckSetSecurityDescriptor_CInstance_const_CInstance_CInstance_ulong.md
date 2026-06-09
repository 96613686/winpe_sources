# Win32LogicalShareSecuritySetting::CheckSetSecurityDescriptor(CInstance const &,CInstance *,CInstance *,ulong &)

- ea: `0x1800dd6f8`
- end: `0x1800de0dd`
- name: `?CheckSetSecurityDescriptor@Win32LogicalShareSecuritySetting@@QEAAJAEBVCInstance@@PEAV2@1AEAK@Z`
- size: `2533`
- prototype: `__int64 __fastcall(Win32LogicalShareSecuritySetting *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800de830`

## callees

- `0x1800127e0`
- `0x180013ae0`
- `0x180015c80`
- `0x180021360`
- `0x180021f34`
- `0x1800254f8`
- `0x180032fd8`
- `0x18003d7b0`
- `0x18004cff4`
- `0x18004e8e8`
- `0x18006610c`
- `0x18006ef28`
- `0x1800896cc`
- `0x180089af4`
- `0x1800dbfac`
- `0x1800dbfdc`
- `0x1800dd6f8`
- `0x1800f318c`
- `0x1800f65dc`
- `0x1800f7234`
- `0x1800f7310`
- `0x1800f7c4c`
- `0x1800f8d80`
- `0x1800f92c8`

## import_xrefs

- `msvcrt!free` at `0x1800de04a`
- `msvcrt!free` at `0x1800de05d`
- `msvcrt!free` at `0x1800de070`
- `msvcrt!free` at `0x1800de04a`
- `msvcrt!free` at `0x1800de05d`
- `msvcrt!free` at `0x1800de070`
- `msvcrt!malloc` at `0x1800ddcbc`
- `msvcrt!malloc` at `0x1800dddf4`
- `msvcrt!malloc` at `0x1800dde9c`
- `msvcrt!malloc` at `0x1800ddcbc`
- `msvcrt!malloc` at `0x1800dddf4`
- `msvcrt!malloc` at `0x1800dde9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddb61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dde4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddb61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dde4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddec4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dda8f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800ddb38`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dda8f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800ddb38`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800dde92`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ddeba`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800dde92`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800ddeba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800dde45`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800dde45`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800ddd17`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800ddd17`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ddcd7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800dde0f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ddcd7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800dde0f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800ddb55`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800ddb55`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800dd761`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800dd761`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800ddab1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800ddab1`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ddf4b`
- `framedynos!?AllocSysString@CHString@@QEBAPEAGXZ` at `0x1800ddf4b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ddf1f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ddf1f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ddf3d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ddf3d`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd7ac`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd887`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd95e`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ddc22`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ddd96`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd7ac`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd887`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800dd95e`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ddc22`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ddd96`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800dda0b`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800dda0b`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd780`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd835`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd90c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd9d0`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd780`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd835`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd90c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800dd9d0`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd7d6`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd8be`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd98c`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd7d6`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd8be`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800dd98c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800de006`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800de006`

## string_xrefs

- `0x1800dd776`: `Descriptor`
- `0x1800dd7cc`: `Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Win32LogicalShareSecuritySetting::CheckSetSecurityDescriptor(
        Win32LogicalShareSecuritySetting *this,
        const struct CInstance *a2,
        struct CInstance *a3,
        struct CInstance *a4,
        unsigned int *a5)
{
  struct CDACL *v6; // rbx
  unsigned int *v7; // r14
  int v8; // esi
  struct MethodContext *MethodContext; // rbx
  bool EmbeddedObject; // al
  CInstance *v11; // rax
  CInstance *v12; // rdi
  CInstance *v13; // rax
  struct MethodContext *v14; // rbx
  bool v15; // al
  CInstance *v16; // rax
  CInstance *v17; // rdi
  CInstance *v18; // rax
  struct MethodContext *v19; // rbx
  bool v20; // al
  unsigned __int16 v21; // r13
  CInstance *v22; // rax
  CInstance *v23; // rax
  unsigned int v24; // edx
  struct CSACL *v25; // rdi
  __int64 v26; // rcx
  __int16 v27; // cx
  CInstance *v28; // rax
  struct MethodContext *v29; // rax
  unsigned int v30; // eax
  CInstance *v31; // rax
  struct MethodContext *v32; // rax
  unsigned int v33; // eax
  BOOL v34; // r13d
  void *v35; // r12
  unsigned __int16 *v36; // rax
  bool v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned __int16 *v42; // rax
  unsigned int Info; // eax
  __int64 v44; // r8
  __int64 v45; // r9
  unsigned __int16 *v46; // rax
  unsigned __int16 *v47; // rdx
  bool v49[4]; // [rsp+30h] [rbp-138h] BYREF
  unsigned __int16 v50[2]; // [rsp+34h] [rbp-134h] BYREF
  int v51; // [rsp+38h] [rbp-130h]
  struct CInstance *v52; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int8 *v53; // [rsp+48h] [rbp-120h] BYREF
  __int16 v54; // [rsp+50h] [rbp-118h]
  DWORD dwBufferLength; // [rsp+54h] [rbp-114h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-110h]
  PACL pSacl; // [rsp+60h] [rbp-108h]
  struct CResource *v58; // [rsp+68h] [rbp-100h] BYREF
  void *Block; // [rsp+70h] [rbp-F8h]
  struct CInstance *v60; // [rsp+78h] [rbp-F0h] BYREF
  struct CInstance *v61; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v62; // [rsp+88h] [rbp-E0h]
  struct CDACL *v63; // [rsp+90h] [rbp-D8h]
  struct CSACL *v64; // [rsp+98h] [rbp-D0h]
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-A8h]
  PSID pGroup; // [rsp+C8h] [rbp-A0h] BYREF
  int v68; // [rsp+D0h] [rbp-98h]
  __int64 v69; // [rsp+D8h] [rbp-90h]
  __int64 v70; // [rsp+E0h] [rbp-88h]
  __int64 v71; // [rsp+E8h] [rbp-80h]
  int v72; // [rsp+F0h] [rbp-78h]
  PSID pSid; // [rsp+F8h] [rbp-70h] BYREF
  int v74; // [rsp+100h] [rbp-68h]
  __int64 v75; // [rsp+108h] [rbp-60h]
  __int64 v76; // [rsp+110h] [rbp-58h]
  __int64 v77; // [rsp+118h] [rbp-50h]
  int v78; // [rsp+120h] [rbp-48h]
  struct CDACL *v79; // [rsp+128h] [rbp-40h]
  size_t v80; // [rsp+170h] [rbp+8h] BYREF
  CInstance *v81; // [rsp+178h] [rbp+10h]
  size_t Size; // [rsp+188h] [rbp+20h] BYREF

  Size = (size_t)a4;
  v81 = a2;
  v80 = (size_t)this;
  v6 = 0;
  v49[0] = 0;
  v50[0] = 0;
  v7 = a5;
  *a5 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v66 = 0;
  Block = 0;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  v52 = 0;
  if ( !CInstance::GetStatus(a3, L"Descriptor", v49, v50)
    || !v49[0]
    || v50[0] != 13 && v50[0] != 1
    || v50[0] == 1
    || (v8 = 0,
        MethodContext = CInstance::GetMethodContext(a3),
        _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v52),
        v52 = 0,
        EmbeddedObject = CInstance::GetEmbeddedObject(a3, L"Descriptor", &v52, MethodContext),
        v6 = 0,
        !EmbeddedObject) )
  {
    v8 = -2147217400;
    *v7 = 21;
  }
  v61 = 0;
  LOBYTE(Size) = 0;
  if ( v8 >= 0 )
  {
    v11 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
    if ( !CInstance::GetStatus(v11, L"Owner", v49, v50) || !v49[0] || v50[0] != 13 && v50[0] != 1 )
      goto LABEL_17;
    if ( v50[0] == 1 )
    {
      LOBYTE(Size) = 0;
      goto LABEL_18;
    }
    v12 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
    v13 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
    v14 = CInstance::GetMethodContext(v13);
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v61);
    v61 = 0;
    v15 = CInstance::GetEmbeddedObject(v12, L"Owner", &v61, v14);
    v6 = 0;
    if ( v15 )
    {
      LOBYTE(Size) = 1;
    }
    else
    {
LABEL_17:
      *v7 = 21;
      v8 = -2147217400;
    }
  }
LABEL_18:
  v60 = 0;
  LOBYTE(v80) = 0;
  if ( v8 >= 0 )
  {
    v16 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
    if ( !CInstance::GetStatus(v16, L"Group", v49, v50) )
    {
      v21 = 0;
      goto LABEL_36;
    }
    if ( v49[0] && (v50[0] == 13 || v50[0] == 1) )
    {
      if ( v50[0] == 1 )
      {
        LOBYTE(v80) = 0;
LABEL_27:
        v21 = 0;
        v22 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
        if ( CInstance::GetStatus(v22, L"ControlFlags", v49, v50) && v49[0] && v50[0] == 3 )
        {
          LODWORD(a5) = 0;
          v23 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
          if ( CInstance::GetDWORD(v23, L"ControlFlags", (unsigned int *)&a5) )
          {
            v21 = (unsigned __int16)a5;
            goto LABEL_37;
          }
        }
LABEL_36:
        v8 = -2147217400;
        *v7 = 21;
        goto LABEL_37;
      }
      v17 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
      v18 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
      v19 = CInstance::GetMethodContext(v18);
      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v60);
      v60 = 0;
      v20 = CInstance::GetEmbeddedObject(v17, L"Owner", &v60, v19);
      v6 = 0;
      if ( v20 )
      {
        LOBYTE(v80) = 1;
        goto LABEL_27;
      }
    }
    *v7 = 21;
    v8 = -2147217400;
  }
  v21 = 0;
LABEL_37:
  pSid = 0;
  v74 = 8;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  if ( v8 >= 0 && (_BYTE)Size )
  {
    if ( FillSIDFromTrustee(v61, (struct CSid *)&pSid) )
    {
      *v7 = 21;
      v8 = -2147217400;
    }
    else if ( pSid && IsValidSid(pSid) && !SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, v21 & 1) )
    {
      *v7 = GetLastError();
      v8 = -2147217404;
    }
  }
  pGroup = 0;
  v68 = 8;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  if ( v8 >= 0 && (_BYTE)v80 )
  {
    if ( FillSIDFromTrustee(v60, (struct CSid *)&pGroup) )
    {
      *v7 = 21;
      v8 = -2147217400;
    }
    else if ( pGroup && IsValidSid(pGroup) )
    {
      v6 = 0;
      if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, (v21 >> 1) & 1) )
      {
        *v7 = GetLastError();
        v8 = -2147217404;
      }
    }
    else
    {
      v6 = 0;
    }
  }
  v24 = 0;
  pDacl = 0;
  LODWORD(Size) = 0;
  v25 = 0;
  pSacl = 0;
  LODWORD(v80) = 0;
  v53 = 0;
  v26 = 0;
  v62 = 0;
  v58 = 0;
  if ( v8 >= 0 )
  {
    try
    {
      if ( (v21 & 4) == 0 )
        goto LABEL_79;
      v6 = (struct CDACL *)operator new(0x58u);
      v79 = v6;
      v24 = 0;
      if ( v6 )
      {
        *(_QWORD *)v6 = &CDACL::`vftable';
        v27 = 0;
        v54 = 0;
        while ( v27 < 10 )
        {
          *((_QWORD *)v6 + ++v27) = 0;
          v54 = v27;
        }
      }
      else
      {
        v6 = 0;
      }
      v63 = v6;
      if ( !v6 )
        goto LABEL_79;
      v28 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
      v29 = CInstance::GetMethodContext(v28);
      v30 = FillDACLFromInstance(v52, v6, v29);
      *v7 = v30;
      if ( v30 )
      {
        if ( v30 == 0x20000000 )
        {
          if ( !CDACL::CreateNullDACL(v6) )
          {
            *v7 = -2147467259;
            v8 = -2147217404;
            v51 = -2147217404;
          }
        }
        else if ( v30 == 0x10000000 )
        {
          CDACL::Clear(v6);
        }
        else
        {
          *v7 = 21;
          v8 = -2147217400;
          v51 = -2147217400;
        }
      }
      if ( !CDACL::CalculateDACLSize(v6, (unsigned int *)&Size) )
      {
        *v7 = 21;
        v8 = -2147217400;
        v51 = -2147217400;
      }
      if ( v8 < 0 || (unsigned int)Size < 8 )
        goto LABEL_79;
      pDacl = (PACL)malloc((unsigned int)Size);
      InitializeAcl(pDacl, Size, 2u);
      LODWORD(Size) = (v21 >> 3) & 1;
      if ( CDACL::FillDACL(v6, pDacl) )
      {
        *v7 = 21;
      }
      else
      {
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, Size) )
          goto LABEL_79;
        *v7 = GetLastError();
      }
      v51 = -2147217400;
      v8 = -2147217400;
LABEL_79:
      if ( (v21 & 0x10) != 0 && v8 >= 0 )
      {
        v25 = (struct CSACL *)operator new(0x10u);
        Size = (size_t)v25;
        if ( v25 )
        {
          *(_QWORD *)v25 = &CSACL::`vftable';
          *((_QWORD *)v25 + 1) = 0;
        }
        else
        {
          v25 = 0;
        }
        v64 = v25;
        if ( v25 )
        {
          v31 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v52);
          v32 = CInstance::GetMethodContext(v31);
          v33 = FillSACLFromInstance(v52, v25, v32);
          *v7 = v33;
          if ( !v33 )
          {
            if ( (unsigned int)CSACL::CalculateSACLSize(v25, (unsigned int *)&v80) )
            {
              if ( (unsigned int)v80 > 8 )
              {
                pSacl = (PACL)malloc((unsigned int)v80);
                InitializeAcl(pSacl, v80, 2u);
                v34 = (v21 >> 5) & 1;
                if ( CSACL::FillSACL(v25, pSacl) )
                {
                  *v7 = 21;
                }
                else if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, pSacl, v34) )
                {
                  *v7 = GetLastError();
                  v8 = -2147217400;
                  v51 = -2147217400;
                }
              }
            }
            else
            {
              *v7 = 21;
              v8 = -2147217400;
              v51 = -2147217400;
            }
          }
        }
        else
        {
          *v7 = -2147467259;
          v8 = -2147217404;
          v51 = -2147217404;
        }
      }
      dwBufferLength = 0;
      if ( v8 < 0 )
      {
        v35 = Block;
      }
      else
      {
        MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
        v35 = malloc(dwBufferLength);
        Block = v35;
        if ( !MakeSelfRelativeSD(pSecurityDescriptor, v35, &dwBufferLength) )
        {
          *v7 = GetLastError();
          v8 = -2147217404;
          v51 = -2147217404;
        }
      }
      if ( v6 )
      {
        CDACL::`scalar deleting destructor'(v6, v24);
        v63 = 0;
      }
      if ( v25 )
      {
        CSACL::`scalar deleting destructor'(v25, v24);
        v64 = 0;
      }
      if ( v8 >= 0 )
      {
        CHString::CHString((CHString *)&v80);
        CInstance::GetCHString(v81, L"Name", (struct CHString *)&v80);
        v36 = CHString::AllocSysString((CHString *)&v80);
        _bstr_t::_bstr_t((_bstr_t *)&Size, v36, v37);
        v38 = CNetAPI32::Init((CNetAPI32 *)&v58);
        *v7 = v38;
        if ( !v38 )
        {
          v42 = (unsigned __int16 *)_bstr_t::operator unsigned short const *(&Size, v39, v40, v41);
          Info = CNetAPI32::NetShareGetInfo((CNetAPI32 *)&v58, 0, v42, 0x1F6u, &v53);
          *v7 = Info;
          if ( !Info )
          {
            v62 = *((_QWORD *)v53 + 8);
            *((_QWORD *)v53 + 8) = v35;
            v46 = (unsigned __int16 *)_bstr_t::operator unsigned short const *(&Size, v53, v44, v45);
            *v7 = CNetAPI32::NetShareSetInfo((CNetAPI32 *)&v58, v47, v46, 0x1F6u, (unsigned __int8 *)v47, 0);
          }
        }
        _bstr_t::_Free((_bstr_t *)&Size);
        CHString::~CHString((CHString *)&v80);
      }
    }
    catch ( ... )
    {
      if ( v53 && v62 )
      {
        *((_QWORD *)v53 + 8) = v62;
        CNetAPI32::NetApiBufferFree((CNetAPI32 *)&v58, v53);
        v53 = 0;
        v62 = 0;
      }
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
      if ( pDacl )
      {
        free(pDacl);
        pDacl = 0;
      }
      if ( pSacl )
      {
        free(pSacl);
        pSacl = 0;
      }
      throw;
    }
    v26 = v62;
  }
  if ( v53 && v26 )
  {
    *((_QWORD *)v53 + 8) = v26;
    CNetAPI32::NetApiBufferFree((CNetAPI32 *)&v58, v53);
    v53 = 0;
  }
  if ( Block )
    free(Block);
  if ( pDacl )
    free(pDacl);
  if ( pSacl )
    free(pSacl);
  if ( v8 == -2147217400 )
    v8 = 0;
  CNetAPI32::~CNetAPI32(&v58);
  CSid::~CSid(&pGroup);
  CSid::~CSid(&pSid);
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v60);
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v61);
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v52);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dd6f8  mov     r11, rsp
0x1800dd6fb  mov     [r11+20h], r9
0x1800dd6ff  mov     [r11+10h], rdx
0x1800dd703  mov     [r11+8], rcx
0x1800dd707  push    rbx
0x1800dd708  push    rsi
0x1800dd709  push    rdi
0x1800dd70a  push    r12
0x1800dd70c  push    r13
0x1800dd70e  push    r14
0x1800dd710  push    r15
0x1800dd712  sub     rsp, 130h
0x1800dd719  mov     rdi, r8
0x1800dd71c  xor     ebx, ebx
0x1800dd71e  mov     [rsp+168h+var_138], bl
0x1800dd722  mov     [rsp+168h+var_134], bx
0x1800dd727  mov     r14, [rsp+168h+arg_20]
0x1800dd72f  mov     [r14], ebx
0x1800dd732  xorps   xmm0, xmm0
0x1800dd735  xor     eax, eax
0x1800dd737  movups  [rsp+168h+pSecurityDescriptor], xmm0
0x1800dd73f  movups  [rsp+168h+var_B8], xmm0
0x1800dd747  mov     [r11-0A8h], rax
0x1800dd74e  mov     [rsp+168h+Block], rbx
0x1800dd753  lea     r13d, [rbx+1]
0x1800dd757  mov     edx, r13d; dwRevision
0x1800dd75a  lea     rcx, [r11-0C8h]; pSecurityDescriptor
0x1800dd761  call    cs:__imp_InitializeSecurityDescriptor
0x1800dd767  mov     [rsp+168h+var_128], rbx
0x1800dd76c  lea     r9, [rsp+168h+var_134]
0x1800dd771  lea     r8, [rsp+168h+var_138]
0x1800dd776  lea     rdx, aDescriptor; "Descriptor"
0x1800dd77d  mov     rcx, rdi
0x1800dd780  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800dd786  test    al, al
0x1800dd788  jz      short loc_1800DD7EE
0x1800dd78a  cmp     [rsp+168h+var_138], bl
0x1800dd78e  jz      short loc_1800DD7EE
0x1800dd790  movzx   eax, [rsp+168h+var_134]
0x1800dd795  cmp     ax, 0Dh
0x1800dd799  jz      short loc_1800DD7A1
0x1800dd79b  cmp     ax, r13w
0x1800dd79f  jnz     short loc_1800DD7EE
0x1800dd7a1  cmp     ax, r13w
0x1800dd7a5  jz      short loc_1800DD7EE
0x1800dd7a7  mov     esi, ebx
0x1800dd7a9  mov     rcx, rdi
0x1800dd7ac  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800dd7b2  mov     rbx, rax
0x1800dd7b5  lea     rcx, [rsp+168h+var_128]
0x1800dd7ba  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800dd7bf  mov     [rsp+168h+var_128], rsi
0x1800dd7c4  mov     r9, rbx
0x1800dd7c7  lea     r8, [rsp+168h+var_128]
0x1800dd7cc  lea     rdx, aDescriptor; "Descriptor"
0x1800dd7d3  mov     rcx, rdi
0x1800dd7d6  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x1800dd7dc  xor     ebx, ebx
0x1800dd7de  lea     r12d, [rbx+15h]
0x1800dd7e2  mov     r15d, 80041008h
0x1800dd7e8  test    al, al
0x1800dd7ea  jz      short loc_1800DD7FA
0x1800dd7ec  jmp     short loc_1800DD800
0x1800dd7ee  mov     r12d, 15h
0x1800dd7f4  mov     r15d, 80041008h
0x1800dd7fa  mov     esi, r15d
0x1800dd7fd  mov     [r14], r12d
0x1800dd800  mov     [rsp+168h+var_E8], rbx
0x1800dd808  mov     byte ptr [rsp+168h+Size], bl
0x1800dd80f  test    esi, esi
0x1800dd811  js      loc_1800DD8DA
0x1800dd817  lea     rcx, [rsp+168h+var_128]
0x1800dd81c  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd821  lea     r9, [rsp+168h+var_134]
0x1800dd826  lea     r8, [rsp+168h+var_138]
0x1800dd82b  lea     rdx, aOwner; "Owner"
0x1800dd832  mov     rcx, rax
0x1800dd835  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800dd83b  test    al, al
0x1800dd83d  jz      loc_1800DD8D4
0x1800dd843  cmp     [rsp+168h+var_138], bl
0x1800dd847  jz      loc_1800DD8D4
0x1800dd84d  movzx   eax, [rsp+168h+var_134]
0x1800dd852  cmp     ax, 0Dh
0x1800dd856  jz      short loc_1800DD85E
0x1800dd858  cmp     ax, r13w
0x1800dd85c  jnz     short loc_1800DD8D4
0x1800dd85e  cmp     ax, r13w
0x1800dd862  jnz     short loc_1800DD86D
0x1800dd864  mov     byte ptr [rsp+168h+Size], bl
0x1800dd86b  jmp     short loc_1800DD8DA
0x1800dd86d  lea     rcx, [rsp+168h+var_128]
0x1800dd872  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd877  mov     rdi, rax
0x1800dd87a  lea     rcx, [rsp+168h+var_128]
0x1800dd87f  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd884  mov     rcx, rax
0x1800dd887  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800dd88d  mov     rbx, rax
0x1800dd890  lea     rcx, [rsp+168h+var_E8]
0x1800dd898  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800dd89d  mov     [rsp+168h+var_E8], 0
0x1800dd8a9  mov     r9, rbx
0x1800dd8ac  lea     r8, [rsp+168h+var_E8]
0x1800dd8b4  lea     rdx, aOwner; "Owner"
0x1800dd8bb  mov     rcx, rdi
0x1800dd8be  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x1800dd8c4  xor     ebx, ebx
0x1800dd8c6  test    al, al
0x1800dd8c8  jz      short loc_1800DD8D4
0x1800dd8ca  mov     byte ptr [rsp+168h+Size], r13b
0x1800dd8d2  jmp     short loc_1800DD8DA
0x1800dd8d4  mov     [r14], r12d
0x1800dd8d7  mov     esi, r15d
0x1800dd8da  mov     [rsp+168h+var_F0], rbx
0x1800dd8df  mov     byte ptr [rsp+168h+arg_0], bl
0x1800dd8e6  test    esi, esi
0x1800dd8e8  js      loc_1800DD9AB
0x1800dd8ee  lea     rcx, [rsp+168h+var_128]
0x1800dd8f3  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd8f8  lea     r9, [rsp+168h+var_134]
0x1800dd8fd  lea     r8, [rsp+168h+var_138]
0x1800dd902  lea     rdx, aGroup; "Group"
0x1800dd909  mov     rcx, rax
0x1800dd90c  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800dd912  test    al, al
0x1800dd914  jz      loc_1800DDA20
0x1800dd91a  cmp     [rsp+168h+var_138], bl
0x1800dd91e  jz      loc_1800DD9A5
0x1800dd924  movzx   eax, [rsp+168h+var_134]
0x1800dd929  cmp     ax, 0Dh
0x1800dd92d  jz      short loc_1800DD935
0x1800dd92f  cmp     ax, r13w
0x1800dd933  jnz     short loc_1800DD9A5
0x1800dd935  cmp     ax, r13w
0x1800dd939  jnz     short loc_1800DD944
0x1800dd93b  mov     byte ptr [rsp+168h+arg_0], bl
0x1800dd942  jmp     short loc_1800DD9A0
0x1800dd944  lea     rcx, [rsp+168h+var_128]
0x1800dd949  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd94e  mov     rdi, rax
0x1800dd951  lea     rcx, [rsp+168h+var_128]
0x1800dd956  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd95b  mov     rcx, rax
0x1800dd95e  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800dd964  mov     rbx, rax
0x1800dd967  lea     rcx, [rsp+168h+var_F0]
0x1800dd96c  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800dd971  mov     [rsp+168h+var_F0], 0
0x1800dd97a  mov     r9, rbx
0x1800dd97d  lea     r8, [rsp+168h+var_F0]
0x1800dd982  lea     rdx, aOwner; "Owner"
0x1800dd989  mov     rcx, rdi
0x1800dd98c  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x1800dd992  xor     ebx, ebx
0x1800dd994  test    al, al
0x1800dd996  jz      short loc_1800DD9A5
0x1800dd998  mov     byte ptr [rsp+168h+arg_0], r13b
0x1800dd9a0  mov     r13d, ebx
0x1800dd9a3  jmp     short loc_1800DD9B2
0x1800dd9a5  mov     [r14], r12d
0x1800dd9a8  mov     esi, r15d
0x1800dd9ab  mov     r13d, ebx
0x1800dd9ae  test    esi, esi
0x1800dd9b0  js      short loc_1800DDA29
0x1800dd9b2  lea     rcx, [rsp+168h+var_128]
0x1800dd9b7  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd9bc  lea     r9, [rsp+168h+var_134]
0x1800dd9c1  lea     r8, [rsp+168h+var_138]
0x1800dd9c6  lea     rdx, aControlflags; "ControlFlags"
0x1800dd9cd  mov     rcx, rax
0x1800dd9d0  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x1800dd9d6  test    al, al
0x1800dd9d8  jz      short loc_1800DDA23
0x1800dd9da  cmp     [rsp+168h+var_138], bl
0x1800dd9de  jz      short loc_1800DDA23
0x1800dd9e0  cmp     [rsp+168h+var_134], 3
0x1800dd9e6  jnz     short loc_1800DDA23
0x1800dd9e8  mov     dword ptr [rsp+168h+arg_20], ebx
0x1800dd9ef  lea     rcx, [rsp+168h+var_128]
0x1800dd9f4  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800dd9f9  lea     r8, [rsp+168h+arg_20]
0x1800dda01  lea     rdx, aControlflags; "ControlFlags"
0x1800dda08  mov     rcx, rax
0x1800dda0b  call    cs:__imp_?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z; CInstance::GetDWORD(ushort const *,ulong &)
0x1800dda11  test    al, al
0x1800dda13  jz      short loc_1800DDA23
0x1800dda15  movzx   r13d, word ptr [rsp+168h+arg_20]
0x1800dda1e  jmp     short loc_1800DDA29
0x1800dda20  mov     r13d, ebx
0x1800dda23  mov     esi, r15d
0x1800dda26  mov     [r14], r12d
0x1800dda29  mov     [rsp+168h+pSid], rbx
0x1800dda31  mov     edi, 8
0x1800dda36  mov     [rsp+168h+var_68], edi
0x1800dda3d  mov     [rsp+168h+var_60], rbx
0x1800dda45  mov     [rsp+168h+var_58], rbx
0x1800dda4d  mov     [rsp+168h+var_50], rbx
0x1800dda55  mov     [rsp+168h+var_48], ebx
0x1800dda5c  test    esi, esi
0x1800dda5e  js      short loc_1800DDAD1
0x1800dda60  cmp     byte ptr [rsp+168h+Size], bl
0x1800dda67  jz      short loc_1800DDAD1
0x1800dda69  lea     rdx, [rsp+168h+pSid]; struct CSid *
0x1800dda71  mov     rcx, [rsp+168h+var_E8]; struct CInstance *
0x1800dda79  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x1800dda7e  test    eax, eax
0x1800dda80  jnz     short loc_1800DDACB
0x1800dda82  mov     rcx, [rsp+168h+pSid]; pSid
0x1800dda8a  test    rcx, rcx
0x1800dda8d  jz      short loc_1800DDAD1
0x1800dda8f  call    cs:__imp_IsValidSid
0x1800dda95  test    eax, eax
0x1800dda97  jz      short loc_1800DDAD1
0x1800dda99  movzx   r8d, r13w
0x1800dda9d  and     r8d, 1; bOwnerDefaulted
0x1800ddaa1  mov     rdx, [rsp+168h+pSid]; pOwner
0x1800ddaa9  lea     rcx, [rsp+168h+pSecurityDescriptor]; pSecurityDescriptor
0x1800ddab1  call    cs:__imp_SetSecurityDescriptorOwner
0x1800ddab7  test    eax, eax
0x1800ddab9  jnz     short loc_1800DDAD1
0x1800ddabb  call    cs:__imp_GetLastError
0x1800ddac1  mov     [r14], eax
0x1800ddac4  mov     esi, 80041004h
0x1800ddac9  jmp     short loc_1800DDAD1
0x1800ddacb  mov     [r14], r12d
0x1800ddace  mov     esi, r15d
0x1800ddad1  mov     [rsp+168h+pGroup], rbx
0x1800ddad9  mov     [rsp+168h+var_98], edi
0x1800ddae0  mov     [rsp+168h+var_90], rbx
0x1800ddae8  mov     [rsp+168h+var_88], rbx
0x1800ddaf0  mov     [rsp+168h+var_80], rbx
0x1800ddaf8  mov     [rsp+168h+var_78], ebx
0x1800ddaff  test    esi, esi
0x1800ddb01  js      short loc_1800DDB7B
0x1800ddb03  cmp     byte ptr [rsp+168h+arg_0], bl
0x1800ddb0a  jz      short loc_1800DDB7B
0x1800ddb0c  lea     rdx, [rsp+168h+pGroup]; struct CSid *
0x1800ddb14  mov     rcx, [rsp+168h+var_F0]; struct CInstance *
0x1800ddb19  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x1800ddb1e  test    eax, eax
0x1800ddb20  jnz     short loc_1800DDB71
0x1800ddb22  movzx   ebx, r13w
0x1800ddb26  shr     ebx, 1
0x1800ddb28  and     ebx, 1
0x1800ddb2b  mov     rcx, [rsp+168h+pGroup]; pSid
0x1800ddb33  test    rcx, rcx
0x1800ddb36  jz      short loc_1800DDB79
0x1800ddb38  call    cs:__imp_IsValidSid
0x1800ddb3e  test    eax, eax
0x1800ddb40  jz      short loc_1800DDB79
0x1800ddb42  mov     r8d, ebx; bGroupDefaulted
0x1800ddb45  mov     rdx, [rsp+168h+pGroup]; pGroup
0x1800ddb4d  lea     rcx, [rsp+168h+pSecurityDescriptor]; pSecurityDescriptor
0x1800ddb55  call    cs:__imp_SetSecurityDescriptorGroup
0x1800ddb5b  xor     ebx, ebx
0x1800ddb5d  test    eax, eax
0x1800ddb5f  jnz     short loc_1800DDB7B
0x1800ddb61  call    cs:__imp_GetLastError
0x1800ddb67  mov     [r14], eax
0x1800ddb6a  mov     esi, 80041004h
0x1800ddb6f  jmp     short loc_1800DDB7B
0x1800ddb71  mov     [r14], r12d
0x1800ddb74  mov     esi, r15d
0x1800ddb77  jmp     short loc_1800DDB7B
0x1800ddb79  xor     ebx, ebx
0x1800ddb7b  xor     edx, edx
0x1800ddb7d  mov     [rsp+168h+pDacl], rdx
0x1800ddb82  mov     dword ptr [rsp+168h+Size], edx
0x1800ddb89  mov     edi, edx
0x1800ddb8b  mov     [rsp+168h+pSacl], rdx
0x1800ddb90  mov     dword ptr [rsp+168h+arg_0], edx
0x1800ddb97  mov     [rsp+168h+var_120], rdx
0x1800ddb9c  mov     ecx, edx
0x1800ddb9e  mov     [rsp+168h+var_E0], rdx
0x1800ddba6  mov     [rsp+168h+var_100], rdx
0x1800ddbab  test    esi, esi
0x1800ddbad  js      loc_1800DE015
0x1800ddbb3  test    r13b, 4
0x1800ddbb7  jz      loc_1800DDD37
0x1800ddbbd  lea     ecx, [rdx+58h]; unsigned __int64
0x1800ddbc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ddbc5  mov     rbx, rax
0x1800ddbc8  mov     [rsp+168h+var_40], rax
0x1800ddbd0  xor     edx, edx
0x1800ddbd2  test    rax, rax
0x1800ddbd5  jz      short loc_1800DDC01
0x1800ddbd7  lea     rax, ??_7CDACL@@6B@; const CDACL::`vftable'
0x1800ddbde  mov     [rbx], rax
0x1800ddbe1  mov     ecx, edx
0x1800ddbe3  mov     [rsp+168h+var_118], dx
0x1800ddbe8  cmp     cx, 0Ah
0x1800ddbec  jge     short loc_1800DDC04
0x1800ddbee  movsx   rax, cx
0x1800ddbf2  mov     [rbx+rax*8+8], rdx
0x1800ddbf7  inc     cx
0x1800ddbfa  mov     [rsp+168h+var_118], cx
0x1800ddbff  jmp     short loc_1800DDBE8
0x1800ddc01  mov     rbx, rdx
0x1800ddc04  mov     [rsp+168h+var_D8], rbx
  ... truncated ...
```
