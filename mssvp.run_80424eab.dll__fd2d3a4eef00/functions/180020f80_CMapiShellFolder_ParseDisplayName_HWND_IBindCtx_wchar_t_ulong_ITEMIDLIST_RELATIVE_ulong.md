# CMapiShellFolder::ParseDisplayName(HWND__ *,IBindCtx *,wchar_t *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180020f80`
- end: `0x180021b66`
- name: `?ParseDisplayName@CMapiShellFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEA_WPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `3046`
- prototype: `__int64 __fastcall(CMapiShellFolder *this, HWND, struct IBindCtx *, wchar_t *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800031c0`
- `0x180003d30`
- `0x180004100`
- `0x180004120`
- `0x180004850`
- `0x180004890`
- `0x1800048c0`
- `0x180004dc0`
- `0x180004f60`
- `0x180005210`
- `0x180006270`
- `0x180014bcc`
- `0x18001869c`
- `0x180018758`
- `0x180018808`
- `0x1800188a8`
- `0x180018b34`
- `0x18001983c`
- `0x1800199b8`
- `0x18001cadc`
- `0x18001cc24`
- `0x18001da94`
- `0x18001e01c`
- `0x180020a48`
- `0x180020f80`
- `0x180021c38`
- `0x18002925c`
- `0x18002ec14`
- `0x180038b28`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021486`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002189c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021486`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002189c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800213dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021406`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800213dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021406`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800210a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800210a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002110a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021224`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002127e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021710`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800217c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002181c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021966`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800219e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021a23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021a99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021ad6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002110a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021224`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002127e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800212d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021710`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800217c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002181c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021966`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800219e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021a23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021a99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021ad6`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x18002108d`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x18002108d`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180021078`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180021078`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800210fe`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800210fe`

## pseudocode

```c
__int64 __fastcall CMapiShellFolder::ParseDisplayName(
        CMapiShellFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        wchar_t *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  const WCHAR *v7; // r15
  __int64 v9; // r12
  __int64 v10; // rax
  HRESULT v12; // edi
  __int64 v13; // rax
  int v14; // r14d
  SIZE_T v15; // rbx
  BYTE *v16; // rax
  struct _ITEMID_CHILD *ItemIdList; // rax
  int lpVtbl; // ebx
  int v19; // ebx
  WCHAR *v20; // rax
  int StringW; // eax
  int v22; // edx
  unsigned int v23; // ebx
  unsigned int v24; // eax
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  char v27; // bl
  _QWORD *v28; // rax
  _QWORD *v29; // rdx
  bool v30; // r15
  int v31; // eax
  int v32; // ebx
  WCHAR *Buffer; // rax
  int v34; // edx
  _QWORD *URL; // rax
  struct IBindCtx *v36; // rcx
  struct _ITEMID_CHILD *v37; // rax
  int v38; // eax
  IUnknown *punk; // [rsp+30h] [rbp-618h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-610h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+40h] [rbp-608h] BYREF
  struct IBindCtx *v42; // [rsp+58h] [rbp-5F0h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, LPITEMIDLIST *); // [rsp+60h] [rbp-5E8h] BYREF
  wchar_t *v44; // [rsp+68h] [rbp-5E0h] BYREF
  struct _ITEMIDLIST_RELATIVE **v45; // [rsp+70h] [rbp-5D8h]
  struct tagPROPVARIANT v46; // [rsp+78h] [rbp-5D0h] BYREF
  unsigned int *v47; // [rsp+90h] [rbp-5B8h]
  _BYTE v48[24]; // [rsp+A0h] [rbp-5A8h] BYREF
  _BYTE v49[24]; // [rsp+B8h] [rbp-590h] BYREF
  _BYTE v50[48]; // [rsp+D0h] [rbp-578h] BYREF
  PROPVARIANT v51[4]; // [rsp+100h] [rbp-548h] BYREF
  void **v52; // [rsp+120h] [rbp-528h] BYREF
  wchar_t *v53; // [rsp+128h] [rbp-520h]
  int cchBufferMax[2]; // [rsp+130h] [rbp-518h]
  __int16 v55; // [rsp+138h] [rbp-510h] BYREF
  void **v56; // [rsp+2C0h] [rbp-388h] BYREF
  wchar_t *v57; // [rsp+2C8h] [rbp-380h]
  __int64 v58; // [rsp+2D0h] [rbp-378h]
  __int16 v59; // [rsp+2D8h] [rbp-370h] BYREF
  void **v60; // [rsp+460h] [rbp-1E8h] BYREF
  wchar_t *v61; // [rsp+468h] [rbp-1E0h]
  __int64 v62; // [rsp+470h] [rbp-1D8h]
  __int16 v63; // [rsp+478h] [rbp-1D0h] BYREF
  void *retaddr; // [rsp+648h] [rbp+0h]

  v7 = a4;
  v44 = a4;
  v42 = a3;
  v45 = a6;
  v47 = a7;
  LODWORD(ppidl) = 0;
  if ( !a6 || !a4 )
    return 2147500035LL;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  if ( !(_DWORD)v10 )
    return 2147942487LL;
  v12 = 0;
  *a6 = 0;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    *a5 = v13;
  }
  if ( !a3 )
    goto LABEL_97;
  v14 = 0;
  punk = 0;
  if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, IUnknown **))a3->lpVtbl->GetObjectParam)(
         a3,
         L"ParseOriginalItem",
         &punk) < 0 )
    goto LABEL_18;
  v14 = 1;
  ppidl = 0;
  v12 = SHGetIDListFromObject(punk, &ppidl);
  if ( v12 >= 0 )
  {
    v15 = ILGetSize(ppidl);
    memset(&pvar, 0, sizeof(pvar));
    v16 = (BYTE *)CoTaskMemAlloc(v15);
    pvar.bstrblobVal.pData = v16;
    if ( v16 )
    {
      pvar.vt = 65;
      pvar.lVal = v15;
      memcpy_0(v16, ppidl, v15);
      v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_DBFolderPidl, &pvar);
    }
    else
    {
      v12 = -2147024882;
    }
    ILFree(ppidl);
    PropVariantClear((PROPVARIANT *)&pvar);
    if ( v12 >= 0 )
    {
LABEL_18:
      v43 = 0;
      if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _QWORD))v42->lpVtbl->GetObjectParam)(
             v42,
             L"ParseWithProperties",
             &v43) >= 0 )
      {
        v14 = 1;
        ppidl = 0;
        v12 = (**v43)(v43, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppidl);
        if ( v12 >= 0 )
        {
          memset(&pvar, 0, sizeof(pvar));
          if ( (*(int (__fastcall **)(LPITEMIDLIST, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)&ppidl->mkid.cb
                                                                                                 + 40LL))(
                 ppidl,
                 &PKEY_ItemType,
                 &pvar) >= 0 )
            v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemType, &pvar);
          PropVariantClear((PROPVARIANT *)&pvar);
          if ( v12 >= 0 )
          {
            memset(&pvar, 0, sizeof(pvar));
            if ( (*(int (__fastcall **)(LPITEMIDLIST, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)&ppidl->mkid.cb + 40LL))(
                   ppidl,
                   &PKEY_ParsingPath,
                   &pvar) >= 0 )
              v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ParsingPath, &pvar);
            PropVariantClear((PROPVARIANT *)&pvar);
            if ( v12 >= 0 )
            {
              memset(&pvar, 0, sizeof(pvar));
              if ( (*(int (__fastcall **)(LPITEMIDLIST, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)&ppidl->mkid.cb + 40LL))(
                     ppidl,
                     &PKEY_ItemPathDisplay,
                     &pvar) >= 0 )
                v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemPathDisplay, &pvar);
              PropVariantClear((PROPVARIANT *)&pvar);
              if ( v12 >= 0 )
              {
                memset(&pvar, 0, sizeof(pvar));
                if ( (*(int (__fastcall **)(LPITEMIDLIST, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)&ppidl->mkid.cb + 40LL))(
                       ppidl,
                       &PKEY_ItemNameDisplay,
                       &pvar) >= 0 )
                  v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemNameDisplay, &pvar);
                PropVariantClear((PROPVARIANT *)&pvar);
              }
            }
          }
        }
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppidl);
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v43);
      if ( v12 >= 0 )
      {
        if ( v14 )
        {
          ItemIdList = CPidlMgr::GetItemIdList((CMapiShellFolder *)((char *)this + 104));
          *v45 = ItemIdList;
          if ( !ItemIdList )
            v12 = -2147024882;
        }
      }
    }
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&punk);
  if ( !v14 )
  {
LABEL_97:
    try
    {
      v57 = (wchar_t *)&v59;
      v58 = 193;
      v59 = 0;
      v56 = &TLMString<192,64,32767>::`vftable';
      v53 = (wchar_t *)&v55;
      *(_QWORD *)cchBufferMax = 193;
      v55 = 0;
      v52 = &TLMString<192,64,32767>::`vftable';
      v61 = (wchar_t *)&v63;
      v62 = 193;
      v63 = 0;
      v60 = &TLMString<192,64,32767>::`vftable';
      if ( CompareStringW(0x7Fu, 1u, v7, -1, L"*", -1) == 2 || CompareStringW(0x7Fu, 1u, v7, -1, L"mapi://", -1) == 2 )
      {
        CMapiUrl::CMapiUrl((CMapiUrl *)v48);
        ATL::CSimpleStringT<wchar_t,0>::SetString(v48, L"mapi", 4);
        v32 = cchBufferMax[0];
        Buffer = CLMString::GetBuffer((CLMString *)&v52, 0);
        LoadStringW(hInstance, 0x6Eu, Buffer, v32);
        CLMString::ReleaseBuffer((CLMString *)&v52, v34);
        memset(&pvar, 0, sizeof(pvar));
        pvar.vt = 3;
        pvar.lVal = 1;
        v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_HasSubfolders, &pvar);
        if ( v12 >= 0 )
        {
          URL = (_QWORD *)CMapiUrl::GetURL(v48, &v44);
          CLMString::operator=(&v56, *URL);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v44);
          if ( CLMString::Last((CLMString *)&v56) == 47 )
            CLMString::Truncate((CLMString *)&v56, HIDWORD(v58) - 1);
          CLMString::operator=(&v60, v53);
        }
        PropVariantClear((PROPVARIANT *)&pvar);
        CMapiUrl::~CMapiUrl((CMapiUrl *)v48);
        goto LABEL_76;
      }
      CLMString::operator=(&v56, v7);
      CMapiUrl::CMapiUrl((CMapiUrl *)v48, v7);
      DecodeFolderName(&punk, v49);
      lpVtbl = (int)punk[-2].lpVtbl;
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
      if ( lpVtbl )
      {
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          &ppidl,
          v50);
        if ( *(int *)ppidl[-6].mkid.abID <= 0 )
        {
          v27 = 6;
          v28 = (_QWORD *)CMapiUrl::StoreWithoutHash(v48, &punk);
          CLMString::operator=(&v60, *v28);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
          CLMString::operator=(&v52, L"/");
          v29 = (_QWORD *)CMapiUrl::StoreWithoutHash(v48, &punk);
          ((void (__fastcall *)(void ***, _QWORD, _QWORD, __int64))v52[4])(
            &v52,
            *v29,
            (unsigned int)cchBufferMax[1],
            0xFFFFFFFFLL);
        }
        else
        {
          v24 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(&ppidl, 47);
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(&ppidl, &punk, v24);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
          v25 = (_QWORD *)DecodeFolderName(&punk, &ppidl);
          CLMString::operator=(&v60, *v25);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
          CLMString::operator=(&v52, L"/");
          v26 = (_QWORD *)CMapiUrl::StoreWithoutHash(v48, &punk);
          ((void (__fastcall *)(void ***, _QWORD, _QWORD, __int64))v52[4])(
            &v52,
            *v26,
            (unsigned int)cchBufferMax[1],
            0xFFFFFFFFLL);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
          CLMString::operator=(&v52, L"/");
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
            &punk,
            v50);
          v27 = 14;
          ((void (__fastcall *)(void ***, IUnknown *, _QWORD, __int64))v52[4])(
            &v52,
            punk,
            (unsigned int)cchBufferMax[1],
            0xFFFFFFFFLL);
        }
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
        v30 = 0;
        if ( v12 >= 0 )
        {
          v27 |= 1u;
          if ( !*(_DWORD *)(*(_QWORD *)CMapiUrl::EntryId(v48, &punk) - 16LL) )
            v30 = 1;
        }
        if ( (v27 & 1) != 0 )
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
        v23 = 0;
        if ( v30 )
        {
          CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, L"MAPI/Folder");
          v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemType, &pvar);
          PropVariantClear((PROPVARIANT *)&pvar);
        }
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&ppidl);
        if ( v12 < 0 )
          goto LABEL_70;
      }
      else
      {
        v19 = cchBufferMax[0];
        v20 = CLMString::GetBuffer((CLMString *)&v52, 0);
        StringW = LoadStringW(hInstance, 0x6Eu, v20, v19);
        v23 = 0;
        if ( !StringW )
          v12 = -2147467259;
        CLMString::ReleaseBuffer((CLMString *)&v52, v22);
        if ( v12 < 0 )
          goto LABEL_70;
        CLMString::operator=(&v60, v53);
      }
      if ( (unsigned int)CMapiUrl::IsUrlThisUsersSID((CMapiUrl *)v48) )
      {
        LODWORD(ppidl) = 0;
        v12 = CMapiSupport::CheckPolicy(L"PreventIndexingOutlook", (int *)&ppidl, 1, 1);
        if ( v12 < 0 )
        {
LABEL_70:
          CMapiUrl::~CMapiUrl((CMapiUrl *)v48);
          v7 = v44;
LABEL_76:
          if ( v12 >= 0 )
          {
            CComPropVariant::CComPropVariant((CComPropVariant *)v51, v57);
            v12 = CPidlMgr::SetProperty(
                    (CMapiShellFolder *)((char *)this + 104),
                    &PKEY_ParsingPath,
                    (struct tagPROPVARIANT *)v51);
            if ( v12 >= 0 )
            {
              CComPropVariant::CComPropVariant((CComPropVariant *)&v46, v53);
              v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemPathDisplay, &v46);
              PropVariantClear((PROPVARIANT *)&v46);
            }
            if ( v12 >= 0 )
            {
              CComPropVariant::CComPropVariant((CComPropVariant *)&v46, v61);
              v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_ItemNameDisplay, &v46);
              PropVariantClear((PROPVARIANT *)&v46);
              if ( v12 >= 0 )
              {
                v36 = v42;
                if ( !v42 )
                  goto LABEL_85;
                v42 = 0;
                if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IBindCtx **))v36->lpVtbl->GetObjectParam)(
                       v36,
                       L"Search Control Panel Folders",
                       &v42) >= 0 )
                {
                  memset(&pvar, 0, sizeof(pvar));
                  pvar.vt = 11;
                  pvar.lVal = -1;
                  v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_AllowFolderEnum, &pvar);
                  PropVariantClear((PROPVARIANT *)&pvar);
                }
                ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v42);
                if ( v12 >= 0 )
                {
LABEL_85:
                  v37 = CPidlMgr::GetItemIdList((CMapiShellFolder *)((char *)this + 104));
                  *v45 = v37;
                  if ( !v37 )
                    v12 = -2147024882;
                }
              }
            }
            PropVariantClear(v51);
          }
          TLMString<192,64,32767>::~TLMString<192,64,32767>(&v60);
          TLMString<192,64,32767>::~TLMString<192,64,32767>(&v52);
          TLMString<192,64,32767>::~TLMString<192,64,32767>(&v56);
          goto LABEL_89;
        }
        v31 = 0;
        if ( !(_DWORD)ppidl )
        {
LABEL_64:
          if ( v31 )
          {
            memset(&pvar, 0, sizeof(pvar));
            pvar.vt = 19;
            pvar.lVal = 0x8000;
            v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_SFGAOFlags, &pvar);
            PropVariantClear((PROPVARIANT *)&pvar);
            if ( v12 >= 0 )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&punk);
              if ( (unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
                                   &punk,
                                   hInstance,
                                   v23) )
              {
                CComPropVariant::CComPropVariant((CComPropVariant *)&v46, (const wchar_t *)punk);
                v12 = CPidlMgr::SetProperty((CMapiShellFolder *)((char *)this + 104), &PKEY_TooltipText, &v46);
                PropVariantClear((PROPVARIANT *)&v46);
              }
              else
              {
                v12 = -2147467259;
              }
              ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&punk);
            }
          }
          goto LABEL_70;
        }
        v23 = 215;
      }
      else
      {
        v23 = 214;
      }
      v31 = 1;
      goto LABEL_64;
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        1508,
        "onecoreuap\\base\\appmodel\\search\\mssvp\\mapishellfolder\\shellfolder.cpp");
    }
  }
LABEL_89:
  if ( v12 >= 0 )
  {
    do
      ++v9;
    while ( v7[v9] );
    if ( v47 )
    {
      v38 = 0;
      if ( v7[v9 - 1] == 47 )
        v38 = 0x20000000;
      *v47 = v38;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180020f80  push    rbx
0x180020f82  push    rsi
0x180020f83  push    rdi
0x180020f84  push    r12
0x180020f86  push    r13
0x180020f88  push    r14
0x180020f8a  push    r15
0x180020f8c  sub     rsp, 610h
0x180020f93  mov     rax, cs:__security_cookie
0x180020f9a  xor     rax, rsp
0x180020f9d  mov     [rsp+648h+var_48], rax
0x180020fa5  mov     r15, r9
0x180020fa8  mov     [rsp+648h+var_5E0], r9
0x180020fad  mov     r9, r8
0x180020fb0  mov     [rsp+648h+var_5F0], r8
0x180020fb5  mov     r13, rcx
0x180020fb8  mov     rdx, [rsp+648h+arg_20]
0x180020fc0  mov     rcx, [rsp+648h+arg_28]
0x180020fc8  mov     [rsp+648h+var_5D8], rcx
0x180020fcd  mov     rax, [rsp+648h+arg_30]
0x180020fd5  mov     [rsp+648h+var_5B8], rax
0x180020fdd  xor     ebx, ebx
0x180020fdf  mov     dword ptr [rsp+648h+ppidl], ebx
0x180020fe3  test    rcx, rcx
0x180020fe6  jz      loc_180021B3E
0x180020fec  test    r15, r15
0x180020fef  jz      loc_180021B3E
0x180020ff5  or      r12, 0FFFFFFFFFFFFFFFFh
0x180020ff9  mov     rax, r12
0x180020ffc  inc     rax
0x180020fff  cmp     [r15+rax*2], bx
0x180021004  jnz     short loc_180020FFC
0x180021006  test    eax, eax
0x180021008  jnz     short loc_180021014
0x18002100a  mov     eax, 80070057h
0x18002100f  jmp     loc_180021B43
0x180021014  mov     edi, ebx
0x180021016  mov     [rcx], rbx
0x180021019  test    rdx, rdx
0x18002101c  jz      short loc_18002102D
0x18002101e  mov     rax, r12
0x180021021  inc     rax
0x180021024  cmp     [r15+rax*2], bx
0x180021029  jnz     short loc_180021021
0x18002102b  mov     [rdx], eax
0x18002102d  test    r9, r9
0x180021030  jz      loc_18002132C
0x180021036  mov     r14d, ebx
0x180021039  mov     [rsp+648h+punk], rbx
0x18002103e  mov     rax, [r8]
0x180021041  lea     r8, [rsp+648h+punk]
0x180021046  lea     rdx, aParseoriginali; "ParseOriginalItem"
0x18002104d  mov     rcx, r9
0x180021050  mov     rax, [rax+50h]
0x180021054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021059  mov     esi, 1
0x18002105e  test    eax, eax
0x180021060  js      loc_180021119
0x180021066  mov     r14d, esi
0x180021069  mov     [rsp+648h+ppidl], rbx
0x18002106e  lea     rdx, [rsp+648h+ppidl]; ppidl
0x180021073  mov     rcx, [rsp+648h+punk]; punk
0x180021078  call    cs:__imp_SHGetIDListFromObject
0x18002107e  mov     edi, eax
0x180021080  test    eax, eax
0x180021082  js      loc_180021312
0x180021088  mov     rcx, [rsp+648h+ppidl]; pidl
0x18002108d  call    cs:__imp_ILGetSize
0x180021093  mov     ebx, eax
0x180021095  xorps   xmm0, xmm0
0x180021098  xor     eax, eax
0x18002109a  movups  xmmword ptr [rsp+648h+pvar], xmm0
0x18002109f  mov     [rsp+648h+var_5F8], rax
0x1800210a4  mov     ecx, ebx; cb
0x1800210a6  call    cs:__imp_CoTaskMemAlloc
0x1800210ac  mov     [rsp+648h+var_5F8], rax
0x1800210b1  test    rax, rax
0x1800210b4  jnz     short loc_1800210BF
0x1800210b6  mov     ebx, 8007000Eh
0x1800210bb  mov     edi, ebx
0x1800210bd  jmp     short loc_1800210F9
0x1800210bf  mov     ecx, 41h ; 'A'
0x1800210c4  mov     word ptr [rsp+648h+pvar], cx
0x1800210c9  mov     dword ptr [rsp+648h+pvar+8], ebx
0x1800210cd  mov     r8, rbx; Size
0x1800210d0  mov     rdx, [rsp+648h+ppidl]; Src
0x1800210d5  mov     rcx, rax; void *
0x1800210d8  call    memcpy_0
0x1800210dd  lea     rcx, [r13+68h]; this
0x1800210e1  lea     r8, [rsp+648h+pvar]; struct tagPROPVARIANT *
0x1800210e6  lea     rdx, PKEY_DBFolderPidl; struct _tagpropertykey *
0x1800210ed  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x1800210f2  mov     edi, eax
0x1800210f4  mov     ebx, 8007000Eh
0x1800210f9  mov     rcx, [rsp+648h+ppidl]; pidl
0x1800210fe  call    cs:__imp_ILFree
0x180021104  nop
0x180021105  lea     rcx, [rsp+648h+pvar]; pvar
0x18002110a  call    cs:__imp_PropVariantClear
0x180021110  test    edi, edi
0x180021112  jns     short loc_18002111E
0x180021114  jmp     loc_180021310
0x180021119  mov     ebx, 8007000Eh
0x18002111e  mov     [rsp+648h+var_5E8], 0
0x180021127  mov     rcx, [rsp+648h+var_5F0]
0x18002112c  mov     rax, [rcx]
0x18002112f  lea     r8, [rsp+648h+var_5E8]
0x180021134  lea     rdx, aParsewithprope; "ParseWithProperties"
0x18002113b  mov     rax, [rax+50h]
0x18002113f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021144  test    eax, eax
0x180021146  js      loc_1800212E6
0x18002114c  mov     r14d, esi
0x18002114f  mov     [rsp+648h+ppidl], 0
0x180021158  mov     rcx, [rsp+648h+var_5E8]
0x18002115d  mov     rax, [rcx]
0x180021160  lea     r8, [rsp+648h+ppidl]
0x180021165  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002116c  mov     rax, [rax]
0x18002116f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021174  mov     edi, eax
0x180021176  test    eax, eax
0x180021178  js      loc_1800212DB
0x18002117e  xorps   xmm0, xmm0
0x180021181  xor     eax, eax
0x180021183  movups  xmmword ptr [rsp+648h+pvar], xmm0
0x180021188  mov     [rsp+648h+var_5F8], rax
0x18002118d  mov     rcx, [rsp+648h+ppidl]
0x180021192  mov     rax, [rcx]
0x180021195  lea     r8, [rsp+648h+pvar]
0x18002119a  lea     rdx, PKEY_ItemType
0x1800211a1  mov     rax, [rax+28h]
0x1800211a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211aa  test    eax, eax
0x1800211ac  js      short loc_1800211C5
0x1800211ae  lea     rcx, [r13+68h]; this
0x1800211b2  lea     r8, [rsp+648h+pvar]; struct tagPROPVARIANT *
0x1800211b7  lea     rdx, PKEY_ItemType; struct _tagpropertykey *
0x1800211be  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x1800211c3  mov     edi, eax
0x1800211c5  lea     rcx, [rsp+648h+pvar]; pvar
0x1800211ca  call    cs:__imp_PropVariantClear
0x1800211d0  test    edi, edi
0x1800211d2  js      loc_1800212DB
0x1800211d8  xorps   xmm0, xmm0
0x1800211db  xor     eax, eax
0x1800211dd  movups  xmmword ptr [rsp+648h+pvar], xmm0
0x1800211e2  mov     [rsp+648h+var_5F8], rax
0x1800211e7  mov     rcx, [rsp+648h+ppidl]
0x1800211ec  mov     rax, [rcx]
0x1800211ef  lea     r8, [rsp+648h+pvar]
0x1800211f4  lea     rdx, PKEY_ParsingPath
0x1800211fb  mov     rax, [rax+28h]
0x1800211ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021204  test    eax, eax
0x180021206  js      short loc_18002121F
0x180021208  lea     rcx, [r13+68h]; this
0x18002120c  lea     r8, [rsp+648h+pvar]; struct tagPROPVARIANT *
0x180021211  lea     rdx, PKEY_ParsingPath; struct _tagpropertykey *
0x180021218  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x18002121d  mov     edi, eax
0x18002121f  lea     rcx, [rsp+648h+pvar]; pvar
0x180021224  call    cs:__imp_PropVariantClear
0x18002122a  test    edi, edi
0x18002122c  js      loc_1800212DB
0x180021232  xorps   xmm0, xmm0
0x180021235  xor     eax, eax
0x180021237  movups  xmmword ptr [rsp+648h+pvar], xmm0
0x18002123c  mov     [rsp+648h+var_5F8], rax
0x180021241  mov     rcx, [rsp+648h+ppidl]
0x180021246  mov     rax, [rcx]
0x180021249  lea     r8, [rsp+648h+pvar]
0x18002124e  lea     rdx, PKEY_ItemPathDisplay
0x180021255  mov     rax, [rax+28h]
0x180021259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002125e  test    eax, eax
0x180021260  js      short loc_180021279
0x180021262  lea     rcx, [r13+68h]; this
0x180021266  lea     r8, [rsp+648h+pvar]; struct tagPROPVARIANT *
0x18002126b  lea     rdx, PKEY_ItemPathDisplay; struct _tagpropertykey *
0x180021272  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180021277  mov     edi, eax
0x180021279  lea     rcx, [rsp+648h+pvar]; pvar
0x18002127e  call    cs:__imp_PropVariantClear
0x180021284  test    edi, edi
0x180021286  js      short loc_1800212DB
0x180021288  xorps   xmm0, xmm0
0x18002128b  xor     eax, eax
0x18002128d  movups  xmmword ptr [rsp+648h+pvar], xmm0
0x180021292  mov     [rsp+648h+var_5F8], rax
0x180021297  mov     rcx, [rsp+648h+ppidl]
0x18002129c  mov     rax, [rcx]
0x18002129f  lea     r8, [rsp+648h+pvar]
0x1800212a4  lea     rdx, PKEY_ItemNameDisplay
0x1800212ab  mov     rax, [rax+28h]
0x1800212af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212b4  test    eax, eax
0x1800212b6  js      short loc_1800212CF
0x1800212b8  lea     rcx, [r13+68h]; this
0x1800212bc  lea     r8, [rsp+648h+pvar]; struct tagPROPVARIANT *
0x1800212c1  lea     rdx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x1800212c8  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x1800212cd  mov     edi, eax
0x1800212cf  lea     rcx, [rsp+648h+pvar]; pvar
0x1800212d4  call    cs:__imp_PropVariantClear
0x1800212da  nop
0x1800212db  lea     rcx, [rsp+648h+ppidl]
0x1800212e0  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800212e5  nop
0x1800212e6  lea     rcx, [rsp+648h+var_5E8]
0x1800212eb  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800212f0  test    edi, edi
0x1800212f2  js      short loc_180021310
0x1800212f4  test    r14d, r14d
0x1800212f7  jz      short loc_180021310
0x1800212f9  lea     rcx, [r13+68h]; this
0x1800212fd  call    ?GetItemIdList@CPidlMgr@@QEAAPEAU_ITEMID_CHILD@@XZ; CPidlMgr::GetItemIdList(void)
0x180021302  mov     rcx, [rsp+648h+var_5D8]
0x180021307  mov     [rcx], rax
0x18002130a  test    rax, rax
0x18002130d  cmovz   edi, ebx
0x180021310  xor     ebx, ebx
0x180021312  lea     rcx, [rsp+648h+punk]
0x180021317  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002131c  test    r14d, r14d
0x18002131f  jz      short loc_180021331
0x180021321  mov     r14d, 2Fh ; '/'
0x180021327  jmp     loc_180021B07
0x18002132c  mov     esi, 1
0x180021331  lea     rax, [rsp+648h+var_370]
0x180021339  mov     [rsp+648h+var_380], rax
0x180021341  mov     [rsp+648h+var_378], 0C1h
0x18002134d  mov     [rsp+648h+var_370], bx
0x180021355  lea     rcx, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18002135c  mov     [rsp+648h+var_388], rcx
0x180021364  lea     rax, [rsp+648h+var_510]
0x18002136c  mov     [rsp+648h+var_520], rax
0x180021374  mov     qword ptr [rsp+648h+cchBufferMax], 0C1h
0x180021380  mov     [rsp+648h+var_510], bx
0x180021388  mov     [rsp+648h+var_528], rcx
0x180021390  lea     rax, [rsp+648h+var_1D0]
0x180021398  mov     [rsp+648h+var_1E0], rax
0x1800213a0  mov     [rsp+648h+var_1D8], 0C1h
0x1800213ac  mov     [rsp+648h+var_1D0], bx
0x1800213b4  mov     [rsp+648h+var_1E8], rcx
0x1800213bc  mov     [rsp+648h+cchCount2], r12d; cchCount2
0x1800213c1  lea     rax, String2; "*"
0x1800213c8  mov     [rsp+648h+lpString2], rax; lpString2
0x1800213cd  mov     r9d, r12d; cchCount1
0x1800213d0  mov     r8, r15; lpString1
0x1800213d3  mov     edx, esi; dwCmpFlags
0x1800213d5  mov     ebx, 7Fh
0x1800213da  mov     ecx, ebx; Locale
0x1800213dc  call    cs:__imp_CompareStringW
0x1800213e2  cmp     eax, 2
0x1800213e5  jz      loc_18002184C
0x1800213eb  mov     [rsp+648h+cchCount2], r12d; cchCount2
0x1800213f0  lea     rax, pszPath; "mapi://"
0x1800213f7  mov     [rsp+648h+lpString2], rax; lpString2
0x1800213fc  mov     r9d, r12d; cchCount1
0x1800213ff  mov     r8, r15; lpString1
0x180021402  mov     edx, esi; dwCmpFlags
0x180021404  mov     ecx, ebx; Locale
0x180021406  call    cs:__imp_CompareStringW
0x18002140c  cmp     eax, 2
0x18002140f  jz      loc_18002184C
0x180021415  mov     rdx, r15
0x180021418  lea     rcx, [rsp+648h+var_388]
0x180021420  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180021425  mov     rdx, r15; wchar_t *
0x180021428  lea     rcx, [rsp+648h+var_5A8]; this
0x180021430  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x180021435  nop
0x180021436  lea     rdx, [rsp+648h+var_590]
0x18002143e  lea     rcx, [rsp+648h+punk]
0x180021443  call    ?DecodeFolderName@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEBV12@@Z; DecodeFolderName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180021448  mov     rax, [rsp+648h+punk]
0x18002144d  mov     ebx, [rax-10h]
0x180021450  lea     rcx, [rsp+648h+punk]
0x180021455  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002145a  test    ebx, ebx
0x18002145c  jnz     short loc_1800214D4
0x18002145e  mov     ebx, [rsp+648h+cchBufferMax]
0x180021465  xor     edx, edx; int
0x180021467  lea     rcx, [rsp+648h+var_528]; this
0x18002146f  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180021474  mov     r9d, ebx; cchBufferMax
0x180021477  mov     r8, rax; lpBuffer
0x18002147a  mov     edx, 6Eh ; 'n'; uID
0x18002147f  mov     rcx, cs:hInstance; hInstance
0x180021486  call    cs:__imp_LoadStringW
0x18002148c  xor     ebx, ebx
0x18002148e  mov     r15d, 80004005h
0x180021494  test    eax, eax
0x180021496  cmovz   edi, r15d
0x18002149a  lea     rcx, [rsp+648h+var_528]; this
0x1800214a2  call    ?ReleaseBuffer@CLMString@@QEAAXH@Z; CLMString::ReleaseBuffer(int)
0x1800214a7  test    edi, edi
0x1800214a9  js      short loc_1800214C9
0x1800214ab  mov     rdx, [rsp+648h+var_520]
  ... truncated ...
```
