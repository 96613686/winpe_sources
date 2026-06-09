# CComCat::IsRegistryClassOfCategories(_GUID const &,ulong,_GUID const * const,ulong,_GUID const * const)

- ea: `0x180011830`
- end: `0x180012176`
- name: `?IsRegistryClassOfCategories@CComCat@@SAJAEBU_GUID@@KQEBU2@K1@Z`
- size: `2374`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int cImplemented, const _GUID *rgcatidImpl, unsigned int cRequired, const _GUID *rgcatidReq)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f4c0`
- `0x1800114c0`

## callees

- `0x18000f358`
- `0x180011800`
- `0x180011830`
- `0x18001217c`
- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x18009bb14`
- `0x1800af350`
- `0x1800b14d4`
- `0x1800b1cb0`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012053`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012053`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011ffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011ffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011df1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001213b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011df1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001213b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012151`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011a30`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011a30`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001189d`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180011e50`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001189d`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180011e50`

## string_xrefs

- `0x18001192b`: `com\ole32\comcat\src\comcat.cpp`
- `0x180011e6d`: `com\ole32\comcat\src\comcat.cpp`
- `0x180011f53`: `com\ole32\comcat\src\comcat.cpp`
- `0x180011fa8`: `com\ole32\comcat\src\comcat.cpp`
- `0x180012011`: `com\ole32\comcat\src\comcat.cpp`

## pseudocode

```c
__int64 __fastcall CComCat::IsRegistryClassOfCategories(
        _GUID *clsid,
        unsigned int cImplemented,
        _GUID *rgcatidImpl,
        unsigned int cRequired,
        const _GUID *rgcatidReq)
{
  unsigned int v5; // esi
  unsigned int v7; // edi
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  wchar_t v10; // ax
  wchar_t *v11; // rax
  HRESULT v12; // r15d
  HRESULT v13; // ebx
  unsigned int v14; // edx
  __int64 v16; // rcx
  wchar_t *v17; // rax
  __int64 v18; // r14
  __int64 v19; // r8
  wchar_t *v20; // rdx
  char *v21; // r9
  wchar_t v22; // ax
  wchar_t *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rax
  wchar_t v26; // cx
  wchar_t *v27; // rcx
  unsigned int j; // ebx
  __int64 v29; // rdx
  HKEY v30; // rcx
  __int64 v31; // rax
  wchar_t *v32; // rax
  __int64 v33; // rcx
  const wchar_t *v34; // rdi
  wchar_t *v35; // rdx
  __int64 v36; // rax
  char *v37; // r9
  wchar_t v38; // r8
  wchar_t *v39; // rax
  __int64 v40; // rcx
  wchar_t *v41; // rax
  wchar_t *v42; // rdx
  char *v43; // r12
  wchar_t v44; // ax
  wchar_t *v45; // rax
  _GUID *v46; // rbx
  int v47; // eax
  int v48; // ecx
  HKEY__ *m_ptr; // rcx
  HKEY__ *v50; // rcx
  HRESULT v51; // eax
  IEnterpriseDropTarget *ptr; // rcx
  HRESULT v53; // eax
  unsigned int v54; // esi
  LSTATUS v55; // eax
  CEnumCategoriesOfClass *v56; // rax
  CEnumCategoriesOfClass *v57; // rax
  CEnumCategoriesOfClass *v58; // rbx
  struct IUnknownVtbl *lpVtbl; // rcx
  unsigned int v60; // edx
  unsigned int i; // edx
  const _GUID *v62; // rcx
  __int64 v63; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hkeyClsid; // [rsp+30h] [rbp-D0h] BYREF
  bool v65; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<IEnterpriseDropTarget> v66; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  IEnumGUID *ppenumCatid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int celtFetched; // [rsp+58h] [rbp-A8h] BYREF
  HKEY__ *hkeyImpCat; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v71; // [rsp+68h] [rbp-98h]
  _GUID *v72; // [rsp+70h] [rbp-90h] BYREF
  HKEY__ *hKeyReq; // [rsp+78h] [rbp-88h] BYREF
  _GUID guid[1]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t wszKey[264]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR wszCat[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  void *retaddr; // [rsp+4F8h] [rbp+3F8h]

  hKey = (HKEY)rgcatidImpl;
  v5 = cImplemented;
  celtFetched = cImplemented;
  v72 = clsid;
  v71 = cRequired;
  memset_0(wszKey, 0, 0x208u);
  v7 = 0;
  hkeyClsid.m_ptr = 0;
  if ( (int)InternalRegOpenClassKey(clsid, 131097, &hkeyClsid) < 0 )
    goto LABEL_90;
  if ( v5 - 1 > 0xFFFFFFFD )
  {
    v12 = -2147024774;
    v18 = 2147483646;
LABEL_51:
    if ( v71 == -1 )
      goto LABEL_87;
    hKeyReq = 0;
    v32 = wszKey;
    v33 = 260;
    do
    {
      if ( !*v32 )
        break;
      ++v32;
      --v33;
    }
    while ( v33 );
    v13 = -2147024809;
    if ( v33 )
      v13 = 0;
    v34 = Com::Catalog::Constants::Required_Categories;
    if ( v33 )
    {
      v35 = &wszKey[260 - v33];
      v36 = 2147483646;
      v37 = (char *)((char *)Com::Catalog::Constants::Required_Categories - (char *)v35);
      do
      {
        if ( !v36 )
          break;
        v38 = *(_WORD *)&v37[(_QWORD)v35];
        if ( !v38 )
          break;
        *v35 = v38;
        --v36;
        ++v35;
        --v33;
      }
      while ( v33 );
      v39 = v35 - 1;
      v13 = -2147024774;
      if ( v33 )
      {
        v39 = v35;
        v13 = 0;
      }
      *v39 = 0;
    }
    if ( v13 < 0 )
    {
      v14 = 974;
      goto LABEL_13;
    }
    v40 = 260;
    v41 = wszKey;
    do
    {
      if ( !*v41 )
        break;
      ++v41;
      --v40;
    }
    while ( v40 );
    if ( v40 )
    {
      v42 = &wszKey[260 - v40];
      v43 = (char *)((char *)L"\\" - (char *)v42);
      do
      {
        if ( !v18 )
          break;
        v44 = *(_WORD *)&v43[(_QWORD)v42];
        if ( !v44 )
          break;
        *v42 = v44;
        --v18;
        ++v42;
        --v40;
      }
      while ( v40 );
      v45 = v42 - 1;
      if ( v40 )
      {
        v45 = v42;
        v12 = 0;
      }
      *v45 = 0;
    }
    else
    {
      v12 = -2147024809;
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x3CFu, "com\\ole32\\comcat\\src\\comcat.cpp", v12);
      if ( hkeyClsid.m_ptr )
        RegCloseKey(hkeyClsid.m_ptr);
      return (unsigned int)v12;
    }
    if ( RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, &hKeyReq) )
    {
      m_ptr = hkeyClsid.m_ptr;
      if ( hkeyClsid.m_ptr )
LABEL_94:
        RegCloseKey(m_ptr);
      return 0;
    }
    RegCloseKey(hKeyReq);
    ppenumCatid = 0;
    v66.ptr_ = 0;
    Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v66);
    v46 = v72;
    if ( GetClassInfoWithInprocOrLocalServer(v72, 0, &GUID_00d489b0_06a7_0074_9ce0_065132561673, (void **)&v66.ptr_) < 0 )
    {
      hKey = 0;
      v51 = InternalRegOpenClassKey(v46, 131097, &hKey);
      v13 = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x479u, "com\\ole32\\comcat\\src\\comcat.cpp", v51);
        if ( hKey )
          RegCloseKey(hKey);
        ptr = v66.ptr_;
        if ( v66.ptr_ )
        {
          v66.ptr_ = 0;
          ((void (__fastcall *)(IEnterpriseDropTarget *))ptr->lpVtbl->Release)(ptr);
          v14 = 990;
          goto LABEL_13;
        }
        goto LABEL_142;
      }
      hkeyImpCat = 0;
      v55 = RegOpenKeyExW(hKey, Com::Catalog::Constants::Required_Categories, 0, 0x20019u, &hkeyImpCat);
      if ( !v55 )
      {
        v56 = (CEnumCategoriesOfClass *)HeapAlloc(g_hHeap, 0, 0x40u);
        if ( v56 && (CEnumCategoriesOfClass::CEnumCategoriesOfClass(v56), (v58 = v57) != 0) )
        {
          v57->m_hKey = hkeyImpCat;
          lpVtbl = v57->lpVtbl;
          v57->m_bMapOldKeys = 0;
          if ( ((int (__fastcall *)(CEnumCategoriesOfClass *, GUID *, IEnumGUID **))lpVtbl->QueryInterface)(
                 v57,
                 &IID_IEnumGUID,
                 &ppenumCatid) >= 0 )
          {
            if ( hKey )
              RegCloseKey(hKey);
            Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v66);
LABEL_84:
            celtFetched = 0;
LABEL_85:
            if ( !((unsigned int (__fastcall *)(IEnumGUID *, __int64, _GUID *, unsigned int *))ppenumCatid->lpVtbl[1].QueryInterface)(
                    ppenumCatid,
                    1,
                    guid,
                    &celtFetched) )
            {
              for ( i = 0; i < v71; ++i )
              {
                v62 = &rgcatidReq[i];
                v63 = *(_QWORD *)&guid[0].Data1 - *(_QWORD *)&v62->Data1;
                if ( *(_QWORD *)&guid[0].Data1 == *(_QWORD *)&v62->Data1 )
                  v63 = *(_QWORD *)guid[0].Data4 - *(_QWORD *)v62->Data4;
                if ( !v63 )
                  goto LABEL_85;
              }
              ((void (__fastcall *)(IEnumGUID *))ppenumCatid->lpVtbl->Release)(ppenumCatid);
              v50 = hkeyClsid.m_ptr;
              if ( !hkeyClsid.m_ptr )
                return 1;
              goto LABEL_91;
            }
            ((void (__fastcall *)(IEnumGUID *))ppenumCatid->lpVtbl->Release)(ppenumCatid);
LABEL_87:
            m_ptr = hkeyClsid.m_ptr;
            if ( hkeyClsid.m_ptr )
              goto LABEL_94;
            return 0;
          }
          CEnumCategoriesOfClass::`scalar deleting destructor'(v58, v60);
          if ( hKey )
            RegCloseKey(hKey);
          Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v66);
          v13 = -2147418113;
        }
        else
        {
          RegCloseKey(hkeyImpCat);
          if ( hKey )
            RegCloseKey(hKey);
          Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v66);
          v13 = -2147024882;
        }
LABEL_142:
        v14 = 990;
        goto LABEL_13;
      }
      v13 = wil::details::in1diag3::Return_Win32(retaddr, 0x47Cu, "com\\ole32\\comcat\\src\\comcat.cpp", v55);
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      do
      {
        v47 = *(const wchar_t *)((char *)v34
                               + (char *)Com::Catalog::Constants::Implemented_Categories
                               - (char *)Com::Catalog::Constants::Required_Categories);
        v48 = *v34 - v47;
        if ( v48 )
          break;
        ++v34;
      }
      while ( v47 );
      v72 = (_GUID *)v66.ptr_;
      v65 = v48 == 0;
      v13 = Microsoft::WRL::Details::MakeAndInitialize<CEnumCategoriesOfCatalogClass,IEnumGUID,IComClassCategoryInfo * &,bool &>(
              &ppenumCatid,
              (IComClassCategoryInfo **)&v72,
              &v65);
    }
    Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v66);
    if ( v13 >= 0 )
      goto LABEL_84;
    goto LABEL_142;
  }
  ppenumCatid = 0;
  v8 = 260;
  v9 = wszKey;
  do
  {
    if ( v8 == -2147483386 )
      break;
    v10 = *(wchar_t *)((char *)v9 + (char *)Com::Catalog::Constants::Implemented_Categories - (char *)wszKey);
    if ( !v10 )
      break;
    *v9++ = v10;
    --v8;
  }
  while ( v8 );
  v11 = v9 - 1;
  v12 = -2147024774;
  if ( v8 )
    v11 = v9;
  v13 = -2147024774;
  if ( v8 )
    v13 = 0;
  *v11 = 0;
  if ( !v8 )
  {
    v14 = 875;
LABEL_13:
    wil::details::in1diag3::Return_Hr(retaddr, v14, "com\\ole32\\comcat\\src\\comcat.cpp", v13);
    if ( hkeyClsid.m_ptr )
      RegCloseKey(hkeyClsid.m_ptr);
    return (unsigned int)v13;
  }
  v16 = 260;
  v17 = wszKey;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v13 = -2147024809;
  v18 = 2147483646;
  if ( v16 )
  {
    v19 = 2147483646;
    v20 = &wszKey[260 - v16];
    v21 = (char *)((char *)L"\\" - (char *)v20);
    do
    {
      if ( !v19 )
        break;
      v22 = *(wchar_t *)((char *)v20 + (_QWORD)v21);
      if ( !v22 )
        break;
      *v20 = v22;
      --v19;
      ++v20;
      --v16;
    }
    while ( v16 );
    v23 = v20 - 1;
    v13 = -2147024774;
    if ( v16 )
    {
      v23 = v20;
      v13 = 0;
    }
    *v23 = 0;
  }
  if ( v13 < 0 )
  {
    v14 = 876;
    goto LABEL_13;
  }
  if ( v5 <= 1 )
    goto LABEL_29;
  hkeyImpCat = 0;
  if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, &hkeyImpCat) )
  {
    RegCloseKey(hkeyImpCat);
LABEL_29:
    while ( v7 < v5 )
    {
      if ( !StringFromGUID2((const GUID *const)hKey + v7, wszCat, 261) )
      {
        if ( hkeyClsid.m_ptr )
          RegCloseKey(hkeyClsid.m_ptr);
        return 2147942487LL;
      }
      v24 = 237;
      v25 = &wszKey[23];
      do
      {
        if ( v24 == -2147483409 )
          break;
        v26 = v25[241];
        if ( !v26 )
          break;
        *v25++ = v26;
        --v24;
      }
      while ( v24 );
      v27 = v25 - 1;
      v13 = -2147024774;
      if ( v24 )
      {
        v27 = v25;
        v13 = 0;
      }
      *v27 = 0;
      if ( !v24 )
      {
        v14 = 913;
        goto LABEL_13;
      }
      if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, (PHKEY)&ppenumCatid) )
      {
LABEL_50:
        RegCloseKey((HKEY)ppenumCatid);
        goto LABEL_51;
      }
      ++v7;
    }
    v7 = 0;
  }
LABEL_42:
  if ( v7 >= v5 )
  {
LABEL_90:
    v50 = hkeyClsid.m_ptr;
    if ( !hkeyClsid.m_ptr )
      return 1;
LABEL_91:
    RegCloseKey(v50);
    return 1;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 5 )
    {
      v5 = celtFetched;
      ++v7;
      goto LABEL_42;
    }
    v29 = j;
    v30 = hKey + 4 * v7;
    v31 = *(_QWORD *)v30 - *(_QWORD *)&g_oldkeyinfo[v29].catid.Data1;
    if ( *(_QWORD *)v30 == *(_QWORD *)&g_oldkeyinfo[v29].catid.Data1 )
      v31 = *((_QWORD *)v30 + 1) - *(_QWORD *)g_oldkeyinfo[v29].catid.Data4;
    if ( !v31 )
      break;
LABEL_48:
    ;
  }
  v53 = StringCchCopyW(wszKey, 0x104u, g_oldkeyinfo[v29].szDescription);
  v54 = v53;
  if ( v53 >= 0 )
  {
    if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, (PHKEY)&ppenumCatid) )
      goto LABEL_50;
    goto LABEL_48;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x3ADu, "com\\ole32\\comcat\\src\\comcat.cpp", v53);
  if ( hkeyClsid.m_ptr )
    RegCloseKey(hkeyClsid.m_ptr);
  return v54;
}

```

## disassembly

```asm
0x180011830  mov     [rsp-8+arg_8], rbx
0x180011835  push    rbp
0x180011836  push    rsi
0x180011837  push    rdi
0x180011838  push    r12
0x18001183a  push    r13
0x18001183c  push    r14
0x18001183e  push    r15
0x180011840  lea     rbp, [rsp-3C0h]
0x180011848  sub     rsp, 4C0h
0x18001184f  mov     rax, cs:__security_cookie
0x180011856  xor     rax, rsp
0x180011859  mov     [rbp+3F0h+var_40], rax
0x180011860  mov     [rsp+4F0h+hKey], rgcatidImpl
0x180011865  mov     esi, cImplemented
0x180011867  mov     [rsp+4F0h+celtFetched], cImplemented
0x18001186b  mov     rbx, clsid
0x18001186e  mov     [rsp+4F0h+var_480], clsid
0x180011873  xor     cImplemented, cImplemented; Val
0x180011875  mov     r8d, 208h; Size
0x18001187b  mov     [rsp+4F0h+var_488], cRequired
0x180011880  lea     clsid, [rbp+3F0h+wszKey]; void *
0x180011884  call    memset_0
0x180011889  xor     edi, edi
0x18001188b  lea     rgcatidImpl, [rsp+4F0h+hkeyClsid]
0x180011890  mov     cImplemented, 20019h
0x180011895  mov     [rsp+4F0h+hkeyClsid.m_ptr], rdi
0x18001189a  mov     clsid, rbx
0x18001189d  call    cs:__imp_InternalRegOpenClassKey
0x1800118a4  nop     dword ptr [rax+rax+00h]
0x1800118a9  test    eax, eax
0x1800118ab  js      loc_180011DC7
0x1800118b1  lea     eax, [rsi-1]
0x1800118b4  cmp     eax, 0FFFFFFFDh
0x1800118b7  ja      loc_180011E04
0x1800118bd  mov     cRequired, 104h
0x1800118c3  mov     [rsp+4F0h+ppenumCatid], rdi
0x1800118c8  lea     rgcatidImpl, ?Implemented_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Implemented_Categories
0x1800118cf  mov     cImplemented, cRequired
0x1800118d2  lea     rax, [rbp+3F0h+wszKey]
0x1800118d6  sub     rgcatidImpl, rax
0x1800118d9  lea     clsid, [rbp+3F0h+wszKey]
0x1800118dd  nop     dword ptr [rax]
0x1800118e0  lea     rax, [rdx+7FFFFEFAh]
0x1800118e7  test    rax, rax
0x1800118ea  jz      short loc_180011903
0x1800118ec  movzx   eax, word ptr [rgcatidImpl+clsid]
0x1800118f1  test    ax, ax
0x1800118f4  jz      short loc_180011903
0x1800118f6  mov     [clsid], ax
0x1800118f9  add     clsid, 2
0x1800118fd  sub     rdx, 1
0x180011901  jnz     short loc_1800118E0
0x180011903  test    rdx, rdx
0x180011906  lea     rax, [clsid-2]
0x18001190a  mov     r15d, 8007007Ah
0x180011910  cmovnz  rax, clsid
0x180011914  mov     ebx, r15d
0x180011917  cmovnz  ebx, edi
0x18001191a  mov     [rax], di
0x18001191d  jnz     short loc_18001197D
0x18001191f  mov     cImplemented, 36Bh; lineNumber
0x180011924  mov     clsid, [rbp+3F8h]; callerReturnAddress
0x18001192b  lea     rgcatidImpl, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x180011932  mov     cRequired, ebx; hr
0x180011935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001193a  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x18001193f  test    clsid, clsid
0x180011942  jz      short loc_180011950
0x180011944  call    cs:__imp_RegCloseKey
0x18001194b  nop     dword ptr [rax+rax+00h]
0x180011950  mov     eax, ebx
0x180011952  mov     clsid, [rbp+3F0h+var_40]
0x180011959  xor     clsid, rsp; StackCookie
0x18001195c  call    __security_check_cookie
0x180011961  mov     rbx, [rsp+4F0h+arg_8]
0x180011969  add     rsp, 4C0h
0x180011970  pop     r15
0x180011972  pop     r14
0x180011974  pop     r13
0x180011976  pop     r12
0x180011978  pop     rdi
0x180011979  pop     rsi
0x18001197a  pop     rbp
0x18001197b  retn
0x18001197d  mov     clsid, r9
0x180011980  lea     rax, [rbp+3F0h+wszKey]
0x180011984  cmp     [rax], di
0x180011987  jz      short loc_180011993
0x180011989  add     rax, 2
0x18001198d  sub     clsid, 1
0x180011991  jnz     short loc_180011984
0x180011993  mov     r13d, 80070057h
0x180011999  lea     r12, asc_1800E8258; "\\"
0x1800119a0  test    clsid, clsid
0x1800119a3  mov     ebx, r13d
0x1800119a6  mov     r14d, 7FFFFFFEh
0x1800119ac  cmovnz  ebx, edi
0x1800119af  jz      short loc_1800119FB
0x1800119b1  mov     rax, r9
0x1800119b4  lea     rdx, [rbp+3F0h+wszKey]
0x1800119b8  sub     rax, clsid
0x1800119bb  mov     r9, r12
0x1800119be  mov     r8d, r14d
0x1800119c1  lea     rdx, [rdx+rax*2]
0x1800119c5  sub     r9, rdx
0x1800119c8  test    rgcatidImpl, rgcatidImpl
0x1800119cb  jz      short loc_1800119E7
0x1800119cd  movzx   eax, word ptr [r9+rdx]
0x1800119d2  test    ax, ax
0x1800119d5  jz      short loc_1800119E7
0x1800119d7  mov     [rdx], ax
0x1800119da  dec     rgcatidImpl
0x1800119dd  add     rdx, 2
0x1800119e1  sub     clsid, 1
0x1800119e5  jnz     short loc_1800119C8
0x1800119e7  test    clsid, clsid
0x1800119ea  lea     rax, [rdx-2]
0x1800119ee  mov     ebx, r15d
0x1800119f1  cmovnz  rax, rdx
0x1800119f5  cmovnz  ebx, edi
0x1800119f8  mov     [rax], di
0x1800119fb  test    ebx, ebx
0x1800119fd  js      loc_180011EE4
0x180011a03  cmp     esi, 1
0x180011a06  ja      loc_180011ADF
0x180011a0c  nop     dword ptr [rax+00h]
0x180011a10  cmp     edi, esi
0x180011a12  jnb     loc_180011EEE
0x180011a18  mov     ecx, edi
0x180011a1a  lea     rdx, [rbp+3F0h+wszCat]; lpsz
0x180011a21  shl     clsid, 4
0x180011a25  mov     r8d, 105h; cchMax
0x180011a2b  add     clsid, [rsp+4F0h+hKey]; rguid
0x180011a30  call    cs:__imp_StringFromGUID2
0x180011a37  nop     dword ptr [rax+rax+00h]
0x180011a3c  test    eax, eax
0x180011a3e  jz      loc_180011E20
0x180011a44  lea     rgcatidImpl, [rbp+3F0h+wszCat]
0x180011a4b  mov     cImplemented, 0EDh
0x180011a50  lea     clsid, [rbp+3F0h+wszKey+2Eh]
0x180011a54  sub     rgcatidImpl, clsid
0x180011a57  lea     rax, [rbp+3F0h+wszKey+2Eh]
0x180011a5b  nop     dword ptr [rax+rax+00h]
0x180011a60  lea     clsid, [rdx+7FFFFF11h]
0x180011a67  test    clsid, clsid
0x180011a6a  jz      short loc_180011A83
0x180011a6c  movzx   ecx, word ptr [rgcatidImpl+rax]
0x180011a71  test    cx, cx
0x180011a74  jz      short loc_180011A83
0x180011a76  mov     [rax], cx
0x180011a79  add     rax, 2
0x180011a7d  sub     rdx, 1
0x180011a81  jnz     short loc_180011A60
0x180011a83  test    rdx, rdx
0x180011a86  lea     clsid, [rax-2]
0x180011a8a  mov     ebx, r15d
0x180011a8d  cmovnz  clsid, rax
0x180011a91  xor     eax, eax
0x180011a93  test    rdx, rdx
0x180011a96  cmovnz  ebx, eax
0x180011a99  mov     [clsid], ax
0x180011a9c  jz      short loc_180011AD5
0x180011a9e  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180011aa3  lea     rax, [rsp+4F0h+ppenumCatid]
0x180011aa8  mov     cRequired, 20019h; samDesired
0x180011aae  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180011ab3  xor     r8d, r8d; ulOptions
0x180011ab6  lea     rdx, [rbp+3F0h+wszKey]; lpSubKey
0x180011aba  call    cs:__imp_RegOpenKeyExW
0x180011ac1  nop     dword ptr [rax+rax+00h]
0x180011ac6  test    eax, eax
0x180011ac8  jz      loc_180011B65
0x180011ace  inc     edi
0x180011ad0  jmp     loc_180011A10
0x180011ad5  mov     cImplemented, 391h
0x180011ada  jmp     loc_180011924
0x180011adf  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180011ae4  lea     rax, [rsp+4F0h+hkeyImpCat]
0x180011ae9  mov     cRequired, 20019h; samDesired
0x180011aef  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180011af4  xor     r8d, r8d; ulOptions
0x180011af7  mov     [rsp+4F0h+hkeyImpCat], rdi
0x180011afc  lea     rdx, [rbp+3F0h+wszKey]; lpSubKey
0x180011b00  call    cs:__imp_RegOpenKeyExW
0x180011b07  nop     dword ptr [rax+rax+00h]
0x180011b0c  test    eax, eax
0x180011b0e  jz      loc_180011DB1
0x180011b14  lea     rgcatidImpl, g_oldkeyinfo
0x180011b1b  cmp     edi, esi
0x180011b1d  jnb     loc_180011DC7
0x180011b23  xor     ebx, ebx
0x180011b25  cmp     ebx, 5
0x180011b28  jnb     short loc_180011B5D
0x180011b2a  mov     eax, ebx
0x180011b2c  imul    rdx, rax, 114h
0x180011b33  mov     ecx, edi
0x180011b35  shl     clsid, 4
0x180011b39  add     clsid, [rsp+4F0h+hKey]
0x180011b3e  mov     rax, [clsid]
0x180011b41  sub     rax, [rdx+rgcatidImpl]
0x180011b45  jnz     short loc_180011B50
0x180011b47  mov     rax, [clsid+8]
0x180011b4b  sub     rax, [rdx+rgcatidImpl+8]
0x180011b50  test    rax, rax
0x180011b53  jz      loc_180011EF5
0x180011b59  inc     ebx
0x180011b5b  jmp     short loc_180011B25
0x180011b5d  mov     esi, [rsp+4F0h+celtFetched]
0x180011b61  inc     edi
0x180011b63  jmp     short loc_180011B1B
0x180011b65  mov     clsid, [rsp+4F0h+ppenumCatid]; hKey
0x180011b6a  call    cs:__imp_RegCloseKey
0x180011b71  nop     dword ptr [rax+rax+00h]
0x180011b76  xor     edi, edi
0x180011b78  cmp     [rsp+4F0h+var_488], 0FFFFFFFFh
0x180011b7d  lea     rsi, ?Implemented_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Implemented_Categories
0x180011b84  mov     cImplemented, 104h
0x180011b89  jz      loc_180011DA5
0x180011b8f  mov     [rsp+4F0h+hKeyReq], rdi
0x180011b94  lea     rax, [rbp+3F0h+wszKey]
0x180011b98  mov     ecx, cImplemented
0x180011b9a  nop     word ptr [rax+rax+00h]
0x180011ba0  cmp     word ptr [rax], 0
0x180011ba4  jz      short loc_180011BB0
0x180011ba6  add     rax, 2
0x180011baa  sub     clsid, 1
0x180011bae  jnz     short loc_180011BA0
0x180011bb0  test    clsid, clsid
0x180011bb3  mov     ebx, r13d
0x180011bb6  cmovnz  ebx, edi
0x180011bb9  lea     rdi, ?Required_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Required_Categories
0x180011bc0  jz      loc_180011F84
0x180011bc6  mov     rax, rdx
0x180011bc9  mov     r9, rdi
0x180011bcc  sub     rax, clsid
0x180011bcf  lea     rdx, [rbp+3F0h+wszKey]
0x180011bd3  lea     rdx, [rdx+rax*2]
0x180011bd7  mov     rax, r14
0x180011bda  sub     r9, rdx
0x180011bdd  nop     dword ptr [rax]
0x180011be0  test    rax, rax
0x180011be3  jz      short loc_180011C01
0x180011be5  movzx   r8d, word ptr [rdx+r9]
0x180011bea  test    r8w, r8w
0x180011bee  jz      short loc_180011C01
0x180011bf0  mov     [rdx], r8w
0x180011bf4  dec     rax
0x180011bf7  add     rdx, 2
0x180011bfb  sub     clsid, 1
0x180011bff  jnz     short loc_180011BE0
0x180011c01  test    clsid, clsid
0x180011c04  lea     rax, [rdx-2]
0x180011c08  mov     ebx, r15d
0x180011c0b  cmovnz  rax, rdx
0x180011c0f  xor     r8d, r8d
0x180011c12  test    clsid, clsid
0x180011c15  mov     cImplemented, 104h
0x180011c1a  cmovnz  ebx, r8d
0x180011c1e  mov     [rax], r8w
0x180011c22  test    ebx, ebx
0x180011c24  js      loc_180011F8C
0x180011c2a  mov     clsid, rdx
0x180011c2d  lea     rax, [rbp+3F0h+wszKey]
0x180011c31  cmp     word ptr [rax], 0
0x180011c35  jz      short loc_180011C41
0x180011c37  add     rax, 2
0x180011c3b  sub     clsid, 1
0x180011c3f  jnz     short loc_180011C31
0x180011c41  test    clsid, clsid
0x180011c44  cmovnz  r13d, r8d
0x180011c48  jz      loc_180011F96
0x180011c4e  sub     rdx, clsid
0x180011c51  lea     rdx, [rbp+rdx*2+3F0h+wszKey]
0x180011c56  sub     r12, rdx
0x180011c59  nop     dword ptr [rax+00000000h]
0x180011c60  test    r14, r14
0x180011c63  jz      short loc_180011C7F
0x180011c65  movzx   eax, word ptr [rdx+r12]
0x180011c6a  test    ax, ax
0x180011c6d  jz      short loc_180011C7F
0x180011c6f  mov     [rdx], ax
0x180011c72  dec     r14
0x180011c75  add     rdx, 2
0x180011c79  sub     clsid, 1
0x180011c7d  jnz     short loc_180011C60
0x180011c7f  test    clsid, clsid
0x180011c82  lea     rax, [rdx-2]
0x180011c86  cmovnz  rax, rdx
0x180011c8a  xor     r14d, r14d
0x180011c8d  test    clsid, clsid
0x180011c90  cmovnz  r15d, r14d
0x180011c94  mov     [rax], r14w
0x180011c98  test    r15d, r15d
0x180011c9b  js      loc_180011FA1
0x180011ca1  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180011ca6  lea     rax, [rsp+4F0h+hKeyReq]
0x180011cab  mov     cRequired, 20019h; samDesired
0x180011cb1  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180011cb6  xor     r8d, r8d; ulOptions
  ... truncated ...
```
