# CMapiShellFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18001ed10`
- end: `0x18001f14f`
- name: `?BindToObject@CMapiShellFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `1087`
- prototype: `int(CMapiShellFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003a10`
- `0x1800048c0`
- `0x180005210`
- `0x180018808`
- `0x180018b34`
- `0x18001c9fc`
- `0x18001ed10`
- `0x18001f634`
- `0x1800286a0`
- `0x180028884`
- `0x18002925c`
- `0x1800303ac`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001eea2`
- `OLEAUT32!__imp_VariantInit` at `0x18001efab`
- `OLEAUT32!__imp_VariantInit` at `0x18001eea2`
- `OLEAUT32!__imp_VariantInit` at `0x18001efab`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef9c`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ef09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001effb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ef09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001effb`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x18001edb3`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x18001edb3`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18001f0a4`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18001f0a4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001f0de`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001f0de`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMapiShellFolder::BindToObject(
        LPCITEMIDLIST *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        struct IShellFolder *ppv)
{
  void **p_lpVtbl; // r14
  __int64 v11; // rax
  __int64 v13; // rax
  HRESULT Instance; // ebx
  struct IShellFolderVtbl *lpVtbl; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  LPCITEMIDLIST v21; // rdi
  __int64 (__fastcall *v22)(LPCITEMIDLIST, _QWORD, struct IShellFolder **); // rbx
  _QWORD *URL; // rax
  struct IShellFolder *v24; // rax
  struct IShellFolder *v25; // rax
  struct IShellFolder *v26; // rsi
  ITEMIDLIST *v27; // r15
  LPCITEMIDLIST ppidlLast; // [rsp+30h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v30[16]; // [rsp+50h] [rbp-61h] BYREF
  _BYTE v31[160]; // [rsp+60h] [rbp-51h] BYREF

  p_lpVtbl = (void **)&ppv->lpVtbl;
  if ( !ppv )
    return 2147500035LL;
  ppv->lpVtbl = 0;
  v11 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
    v11 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
  if ( !v11 )
    return (unsigned int)CPidlMgr::GetPropertyStoreFromPIDL((CPidlMgr *)this, a2, a4, p_lpVtbl);
  v13 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IDisplayItem.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IDisplayItem.Data1 )
    v13 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IDisplayItem.Data4;
  if ( v13 )
  {
    v16 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IShellFolder.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IShellFolder.Data1 )
      v16 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IShellFolder.Data4;
    if ( !v16 )
      goto LABEL_46;
    v17 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IShellFolder2.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IShellFolder2.Data1 )
      v17 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IShellFolder2.Data4;
    if ( !v17 )
    {
LABEL_46:
      LODWORD(ppv) = 0;
      CMapiSupport::IsOutlookInstalled((int *)&ppv);
      if ( !(_DWORD)ppv )
        return (unsigned int)-2147467259;
      ppv = 0;
      Instance = ATL::CComObject<CMapiShellFolder>::CreateInstance(&ppv);
      if ( Instance < 0 )
        return (unsigned int)Instance;
      v26 = ppv;
      ((void (__fastcall *)(struct IShellFolder *))ppv->lpVtbl->AddRef)(ppv);
      v27 = ILCombine(this[18], (LPCITEMIDLIST)a2);
      if ( v27 )
      {
        ((void (__fastcall *)(struct IShellFolder *, ITEMIDLIST *))v26[1].lpVtbl->EnumObjects)(&v26[1], v27);
        Instance = ((__int64 (__fastcall *)(struct IShellFolder *, const struct _GUID *, void **))v26->lpVtbl->QueryInterface)(
                     v26,
                     a4,
                     p_lpVtbl);
        ILFree(v27);
        if ( a3 )
        {
          ppv = 0;
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IShellFolder **))a3->lpVtbl->GetObjectParam)(
                 a3,
                 L"Search Control Panel Folders",
                 &ppv) >= 0 )
            LODWORD(v26[20].lpVtbl) = 1;
          ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
        }
      }
      else
      {
        Instance = -2147024882;
      }
      lpVtbl = v26->lpVtbl;
LABEL_56:
      ((void (*)(void))lpVtbl->Release)();
      return (unsigned int)Instance;
    }
    v18 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v18 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStream.Data4;
    if ( v18 )
    {
      v19 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStorage.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStorage.Data1 )
        v19 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStorage.Data4;
      if ( v19 )
      {
        Instance = -2147467263;
        v20 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IItemNameLimits.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IItemNameLimits.Data1 )
          v20 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IItemNameLimits.Data4;
        if ( v20 )
          return (unsigned int)Instance;
        return (unsigned int)(*(__int64 (__fastcall **)(LPCITEMIDLIST *, const struct _GUID *, void **))&(*this)->mkid.cb)(
                               this,
                               a4,
                               p_lpVtbl);
      }
      VariantInit(&pvarg);
      Instance = CPidlMgr::PropertyDetailFromPIDL((CPidlMgr *)(this + 13), a2, &PKEY_ParsingPath, 8u, &pvarg);
      if ( Instance < 0 || (unsigned int)IsAttachment(pvarg.bstrVal) )
      {
LABEL_38:
        VariantClear(&pvarg);
        return (unsigned int)Instance;
      }
      ppidlLast = 0;
      Instance = CoCreateInstance(
                   &GUID_1af81e4e_fc45_48ee_b236_a2a663494390,
                   0,
                   4u,
                   &GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67,
                   (LPVOID *)&ppidlLast);
      if ( Instance >= 0 )
      {
        CMapiUrl::CMapiUrl((CMapiUrl *)v31, pvarg.bstrVal);
        ppv = 0;
        v21 = ppidlLast;
        v22 = *(__int64 (__fastcall **)(LPCITEMIDLIST, _QWORD, struct IShellFolder **))(*(_QWORD *)&ppidlLast->mkid.cb
                                                                                      + 48LL);
        URL = (_QWORD *)CMapiUrl::GetURL(v31, v30);
        Instance = v22(v21, *URL, &ppv);
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v30);
        v24 = ppv;
        if ( ppv )
        {
          if ( Instance >= 0 )
          {
            ppv = 0;
            *p_lpVtbl = v24;
          }
        }
        else
        {
          Instance = -2147024894;
        }
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
        CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
      }
    }
    else
    {
      VariantInit(&pvarg);
      if ( CPidlMgr::PropertyDetailFromPIDL((CPidlMgr *)(this + 13), a2, &PKEY_ParsingPath, 8u, &pvarg) < 0 )
      {
        Instance = -2147467263;
        goto LABEL_38;
      }
      ppidlLast = 0;
      Instance = CoCreateInstance(
                   &GUID_1af81e4e_fc45_48ee_b236_a2a663494390,
                   0,
                   4u,
                   &GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67,
                   (LPVOID *)&ppidlLast);
      if ( Instance >= 0 )
      {
        ppv = 0;
        Instance = (*(__int64 (__fastcall **)(LPCITEMIDLIST, LONGLONG, struct IShellFolder **))(*(_QWORD *)&ppidlLast->mkid.cb
                                                                                              + 32LL))(
                     ppidlLast,
                     pvarg.llVal,
                     &ppv);
        if ( Instance >= 0 )
        {
          v25 = ppv;
          ppv = 0;
          *p_lpVtbl = v25;
        }
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
      }
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppidlLast);
    goto LABEL_38;
  }
  ppidlLast = 0;
  ppv = 0;
  Instance = SHBindToFolderIDListParent(
               (IShellFolder *)this,
               (LPCITEMIDLIST)a2,
               &GUID_000214e6_0000_0000_c000_000000000046,
               (void **)&ppv,
               &ppidlLast);
  if ( Instance >= 0 )
  {
    Instance = CreateRelatedItemWithParent(ppv, (const struct _ITEMID_CHILD *)ppidlLast, a4, p_lpVtbl);
    lpVtbl = ppv->lpVtbl;
    goto LABEL_56;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001ed10  push    rbp
0x18001ed12  push    rbx
0x18001ed13  push    rsi
0x18001ed14  push    rdi
0x18001ed15  push    r12
0x18001ed17  push    r13
0x18001ed19  push    r14
0x18001ed1b  push    r15
0x18001ed1d  lea     rbp, [rsp-17h]
0x18001ed22  sub     rsp, 0C8h
0x18001ed29  mov     rdi, r9
0x18001ed2c  mov     r13, r8
0x18001ed2f  mov     r12, rdx
0x18001ed32  mov     r15, rcx
0x18001ed35  mov     r14, [rbp+4Fh+ppv]
0x18001ed39  xor     esi, esi
0x18001ed3b  test    r14, r14
0x18001ed3e  jnz     short loc_18001ED4A
0x18001ed40  mov     eax, 80004003h
0x18001ed45  jmp     loc_18001F13B
0x18001ed4a  mov     [r14], rsi
0x18001ed4d  mov     rax, [r9]
0x18001ed50  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x18001ed57  jnz     short loc_18001ED64
0x18001ed59  mov     rax, [r9+8]
0x18001ed5d  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x18001ed64  test    rax, rax
0x18001ed67  jnz     short loc_18001ED79
0x18001ed69  mov     r9, r14; void **
0x18001ed6c  mov     r8, rdi; struct _GUID *
0x18001ed6f  call    ?GetPropertyStoreFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CPidlMgr::GetPropertyStoreFromPIDL(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18001ed74  jmp     loc_18001EE97
0x18001ed79  mov     rax, [r9]
0x18001ed7c  sub     rax, qword ptr cs:IID_IDisplayItem.Data1
0x18001ed83  jnz     short loc_18001ED90
0x18001ed85  mov     rax, [r9+8]
0x18001ed89  sub     rax, qword ptr cs:IID_IDisplayItem.Data4
0x18001ed90  test    rax, rax
0x18001ed93  jnz     short loc_18001EDE5
0x18001ed95  mov     [rsp+100h+var_D0], rsi
0x18001ed9a  mov     [rbp+4Fh+ppv], rsi
0x18001ed9e  lea     rax, [rsp+100h+var_D0]
0x18001eda3  mov     [rsp+100h+ppidlLast], rax; ppidlLast
0x18001eda8  lea     r9, [rbp+4Fh+ppv]; ppv
0x18001edac  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18001edb3  call    cs:__imp_SHBindToFolderIDListParent
0x18001edb9  mov     ebx, eax
0x18001edbb  test    eax, eax
0x18001edbd  js      loc_18001F139
0x18001edc3  mov     r9, r14; void **
0x18001edc6  mov     r8, rdi; struct _GUID *
0x18001edc9  mov     rdx, [rsp+100h+var_D0]; struct _ITEMID_CHILD *
0x18001edce  mov     rcx, [rbp+4Fh+ppv]; struct IShellFolder *
0x18001edd2  call    ?CreateRelatedItemWithParent@@YAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CreateRelatedItemWithParent(IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)
0x18001edd7  mov     ebx, eax
0x18001edd9  mov     rcx, [rbp+4Fh+ppv]
0x18001eddd  mov     rax, [rcx]
0x18001ede0  jmp     loc_18001F130
0x18001ede5  mov     rax, [r9]
0x18001ede8  sub     rax, qword ptr cs:IID_IShellFolder.Data1
0x18001edef  jnz     short loc_18001EDFC
0x18001edf1  mov     rax, [r9+8]
0x18001edf5  sub     rax, qword ptr cs:IID_IShellFolder.Data4
0x18001edfc  test    rax, rax
0x18001edff  jz      loc_18001F055
0x18001ee05  mov     rax, [r9]
0x18001ee08  sub     rax, qword ptr cs:IID_IShellFolder2.Data1
0x18001ee0f  jnz     short loc_18001EE1C
0x18001ee11  mov     rax, [r9+8]
0x18001ee15  sub     rax, qword ptr cs:IID_IShellFolder2.Data4
0x18001ee1c  test    rax, rax
0x18001ee1f  jz      loc_18001F055
0x18001ee25  mov     rax, [r9]
0x18001ee28  sub     rax, qword ptr cs:IID_IStream.Data1
0x18001ee2f  jnz     short loc_18001EE3C
0x18001ee31  mov     rax, [r9+8]
0x18001ee35  sub     rax, qword ptr cs:IID_IStream.Data4
0x18001ee3c  test    rax, rax
0x18001ee3f  jz      loc_18001EFA7
0x18001ee45  mov     rax, [r9]
0x18001ee48  sub     rax, qword ptr cs:IID_IStorage.Data1
0x18001ee4f  jnz     short loc_18001EE5C
0x18001ee51  mov     rax, [r9+8]
0x18001ee55  sub     rax, qword ptr cs:IID_IStorage.Data4
0x18001ee5c  test    rax, rax
0x18001ee5f  jz      short loc_18001EE9E
0x18001ee61  mov     ebx, 80004001h
0x18001ee66  mov     rax, [r9]
0x18001ee69  sub     rax, qword ptr cs:IID_IItemNameLimits.Data1
0x18001ee70  jnz     short loc_18001EE7D
0x18001ee72  mov     rax, [r9+8]
0x18001ee76  sub     rax, qword ptr cs:IID_IItemNameLimits.Data4
0x18001ee7d  test    rax, rax
0x18001ee80  jnz     loc_18001F139
0x18001ee86  mov     rax, [rcx]
0x18001ee89  mov     r8, r14
0x18001ee8c  mov     rdx, rdi
0x18001ee8f  mov     rax, [rax]
0x18001ee92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee97  mov     ebx, eax
0x18001ee99  jmp     loc_18001F139
0x18001ee9e  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001eea2  call    cs:__imp_VariantInit
0x18001eea8  nop
0x18001eea9  mov     r9d, 8; unsigned __int16
0x18001eeaf  lea     rcx, [r15+68h]; this
0x18001eeb3  lea     rax, [rbp+4Fh+pvarg]
0x18001eeb7  mov     [rsp+100h+ppidlLast], rax; struct tagVARIANT *
0x18001eebc  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001eec3  mov     rdx, r12; struct _ITEMIDLIST_RELATIVE *
0x18001eec6  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001eecb  mov     ebx, eax
0x18001eecd  test    eax, eax
0x18001eecf  js      loc_18001EF98
0x18001eed5  mov     rcx, qword ptr [rbp+4Fh+pvarg+8]; wchar_t *
0x18001eed9  call    ?IsAttachment@@YAHPEB_W@Z; IsAttachment(wchar_t const *)
0x18001eede  test    eax, eax
0x18001eee0  jnz     loc_18001EF98
0x18001eee6  mov     [rsp+100h+var_D0], rsi
0x18001eeeb  lea     rax, [rsp+100h+var_D0]
0x18001eef0  mov     [rsp+100h+ppidlLast], rax; ppv
0x18001eef5  lea     r9, _GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67; riid
0x18001eefc  xor     edx, edx; pUnkOuter
0x18001eefe  lea     r8d, [rdx+4]; dwClsContext
0x18001ef02  lea     rcx, _GUID_1af81e4e_fc45_48ee_b236_a2a663494390; rclsid
0x18001ef09  call    cs:__imp_CoCreateInstance
0x18001ef0f  mov     ebx, eax
0x18001ef11  test    eax, eax
0x18001ef13  js      short loc_18001EF8D
0x18001ef15  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]; wchar_t *
0x18001ef19  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001ef1d  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x18001ef22  nop
0x18001ef23  mov     [rbp+4Fh+ppv], rsi
0x18001ef27  mov     rdi, [rsp+100h+var_D0]
0x18001ef2c  mov     rax, [rdi]
0x18001ef2f  mov     rbx, [rax+30h]
0x18001ef33  lea     rdx, [rbp+4Fh+var_B0]
0x18001ef37  lea     rcx, [rbp+4Fh+var_A0]
0x18001ef3b  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18001ef40  nop
0x18001ef41  lea     r8, [rbp+4Fh+ppv]
0x18001ef45  mov     rdx, [rax]
0x18001ef48  mov     rcx, rdi
0x18001ef4b  mov     rax, rbx
0x18001ef4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef53  mov     ebx, eax
0x18001ef55  lea     rcx, [rbp+4Fh+var_B0]
0x18001ef59  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18001ef5e  mov     rax, [rbp+4Fh+ppv]
0x18001ef62  test    rax, rax
0x18001ef65  jnz     short loc_18001EF6E
0x18001ef67  mov     ebx, 80070002h
0x18001ef6c  jmp     short loc_18001EF79
0x18001ef6e  test    ebx, ebx
0x18001ef70  js      short loc_18001EF79
0x18001ef72  mov     [rbp+4Fh+ppv], rsi
0x18001ef76  mov     [r14], rax
0x18001ef79  lea     rcx, [rbp+4Fh+ppv]
0x18001ef7d  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001ef82  nop
0x18001ef83  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001ef87  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18001ef8c  nop
0x18001ef8d  lea     rcx, [rsp+100h+var_D0]
0x18001ef92  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001ef97  nop
0x18001ef98  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001ef9c  call    cs:__imp_VariantClear
0x18001efa2  jmp     loc_18001F139
0x18001efa7  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001efab  call    cs:__imp_VariantInit
0x18001efb1  nop
0x18001efb2  mov     r9d, 8; unsigned __int16
0x18001efb8  lea     rcx, [r15+68h]; this
0x18001efbc  lea     rax, [rbp+4Fh+pvarg]
0x18001efc0  mov     [rsp+100h+ppidlLast], rax; struct tagVARIANT *
0x18001efc5  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001efcc  mov     rdx, r12; struct _ITEMIDLIST_RELATIVE *
0x18001efcf  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001efd4  test    eax, eax
0x18001efd6  js      short loc_18001F04B
0x18001efd8  mov     [rsp+100h+var_D0], rsi
0x18001efdd  lea     rax, [rsp+100h+var_D0]
0x18001efe2  mov     [rsp+100h+ppidlLast], rax; ppv
0x18001efe7  lea     r9, _GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67; riid
0x18001efee  xor     edx, edx; pUnkOuter
0x18001eff0  lea     r8d, [rdx+4]; dwClsContext
0x18001eff4  lea     rcx, _GUID_1af81e4e_fc45_48ee_b236_a2a663494390; rclsid
0x18001effb  call    cs:__imp_CoCreateInstance
0x18001f001  mov     ebx, eax
0x18001f003  test    eax, eax
0x18001f005  js      short loc_18001F03F
0x18001f007  mov     [rbp+4Fh+ppv], rsi
0x18001f00b  mov     rcx, [rsp+100h+var_D0]
0x18001f010  mov     rax, [rcx]
0x18001f013  lea     r8, [rbp+4Fh+ppv]
0x18001f017  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]
0x18001f01b  mov     rax, [rax+20h]
0x18001f01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f024  mov     ebx, eax
0x18001f026  test    eax, eax
0x18001f028  js      short loc_18001F035
0x18001f02a  mov     rax, [rbp+4Fh+ppv]
0x18001f02e  mov     [rbp+4Fh+ppv], rsi
0x18001f032  mov     [r14], rax
0x18001f035  lea     rcx, [rbp+4Fh+ppv]
0x18001f039  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001f03e  nop
0x18001f03f  lea     rcx, [rsp+100h+var_D0]
0x18001f044  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001f049  jmp     short loc_18001F050
0x18001f04b  mov     ebx, 80004001h
0x18001f050  jmp     loc_18001EF98
0x18001f055  mov     dword ptr [rbp+4Fh+ppv], esi
0x18001f058  lea     rcx, [rbp+4Fh+ppv]; int *
0x18001f05c  call    ?IsOutlookInstalled@CMapiSupport@@SAJPEAH@Z; CMapiSupport::IsOutlookInstalled(int *)
0x18001f061  cmp     dword ptr [rbp+4Fh+ppv], esi
0x18001f064  jnz     short loc_18001F070
0x18001f066  mov     ebx, 80004005h
0x18001f06b  jmp     loc_18001F139
0x18001f070  mov     [rbp+4Fh+ppv], rsi
0x18001f074  lea     rcx, [rbp+4Fh+ppv]
0x18001f078  call    ?CreateInstance@?$CComObject@VCMapiShellFolder@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMapiShellFolder>::CreateInstance(ATL::CComObject<CMapiShellFolder> * *)
0x18001f07d  mov     ebx, eax
0x18001f07f  test    eax, eax
0x18001f081  js      loc_18001F139
0x18001f087  mov     rsi, [rbp+4Fh+ppv]
0x18001f08b  mov     rax, [rsi]
0x18001f08e  mov     rcx, rsi
0x18001f091  mov     rax, [rax+8]
0x18001f095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f09a  mov     rdx, r12; pidl2
0x18001f09d  mov     rcx, [r15+90h]; pidl1
0x18001f0a4  call    cs:__imp_ILCombine
0x18001f0aa  mov     r15, rax
0x18001f0ad  test    rax, rax
0x18001f0b0  jz      short loc_18001F125
0x18001f0b2  lea     rcx, [rsi+8]
0x18001f0b6  mov     rdx, [rcx]
0x18001f0b9  mov     rax, [rdx+20h]
0x18001f0bd  mov     rdx, r15
0x18001f0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0c5  mov     rcx, [rsi]
0x18001f0c8  mov     rax, [rcx]
0x18001f0cb  mov     r8, r14
0x18001f0ce  mov     rdx, rdi
0x18001f0d1  mov     rcx, rsi
0x18001f0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0d9  mov     ebx, eax
0x18001f0db  mov     rcx, r15; pidl
0x18001f0de  call    cs:__imp_ILFree
0x18001f0e4  test    r13, r13
0x18001f0e7  jz      short loc_18001F12A
0x18001f0e9  mov     [rbp+4Fh+ppv], 0
0x18001f0f1  mov     rax, [r13+0]
0x18001f0f5  lea     r8, [rbp+4Fh+ppv]
0x18001f0f9  lea     rdx, aSearchControlP; "Search Control Panel Folders"
0x18001f100  mov     rcx, r13
0x18001f103  mov     rax, [rax+50h]
0x18001f107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f10c  test    eax, eax
0x18001f10e  js      short loc_18001F11A
0x18001f110  mov     dword ptr [rsi+0A0h], 1
0x18001f11a  lea     rcx, [rbp+4Fh+ppv]
0x18001f11e  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001f123  jmp     short loc_18001F12A
0x18001f125  mov     ebx, 8007000Eh
0x18001f12a  mov     rax, [rsi]
0x18001f12d  mov     rcx, rsi
0x18001f130  mov     rax, [rax+10h]
0x18001f134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f139  mov     eax, ebx
0x18001f13b  add     rsp, 0C8h
0x18001f142  pop     r15
0x18001f144  pop     r14
0x18001f146  pop     r13
0x18001f148  pop     r12
0x18001f14a  pop     rdi
0x18001f14b  pop     rsi
0x18001f14c  pop     rbx
0x18001f14d  pop     rbp
0x18001f14e  retn
```
