# CMapiShellFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180020180`
- end: `0x1800207d1`
- name: `?GetUIObjectOf@CMapiShellFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `1617`
- prototype: `__int64 __usercall@<rax>(struct IShellFolder2 *this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, const struct _ITEMID_CHILD *const *@<r9>, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003a10`
- `0x180005210`
- `0x180008730`
- `0x180008c80`
- `0x180008d2c`
- `0x1800160dc`
- `0x18001b814`
- `0x18001bb40`
- `0x18001c9fc`
- `0x18001f3bc`
- `0x18001f6d8`
- `0x18001f778`
- `0x180020180`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800204ee`
- `OLEAUT32!__imp_VariantInit` at `0x1800204fa`
- `OLEAUT32!__imp_VariantInit` at `0x18002068e`
- `OLEAUT32!__imp_VariantInit` at `0x18002069a`
- `OLEAUT32!__imp_VariantInit` at `0x1800204ee`
- `OLEAUT32!__imp_VariantInit` at `0x1800204fa`
- `OLEAUT32!__imp_VariantInit` at `0x18002068e`
- `OLEAUT32!__imp_VariantInit` at `0x18002069a`
- `OLEAUT32!__imp_VariantClear` at `0x180020674`
- `OLEAUT32!__imp_VariantClear` at `0x18002067f`
- `OLEAUT32!__imp_VariantClear` at `0x180020750`
- `OLEAUT32!__imp_VariantClear` at `0x180020674`
- `OLEAUT32!__imp_VariantClear` at `0x18002067f`
- `OLEAUT32!__imp_VariantClear` at `0x180020750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020466`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020466`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020319`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020319`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x1800202cb`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x1800202cb`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x180020619`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x180020619`

## string_xrefs

- `0x180020458`: `SHCreateDefaultContextMenu`
- `0x1800205b0`: `AssocCreateForClasses`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMapiShellFolder::GetUIObjectOf(
        struct IShellFolder2 *this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMID_CHILD **a4,
        const struct _GUID *a5,
        unsigned int *a6,
        struct IContextMenu *ppv)
{
  struct IContextMenu *v11; // r15
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  CMessageContextMenu *v20; // rsi
  FARPROC ProcAddress; // rax
  const wchar_t *bstrVal; // rsi
  FARPROC v23; // rax
  __int64 v24; // rax
  CCSCQueryInfo *v25; // rsi
  CExtractIcon *v26; // rsi
  VARIANTARG pvar; // [rsp+40h] [rbp-B1h] BYREF
  __int64 v28; // [rsp+58h] [rbp-99h] BYREF
  void *v29[2]; // [rsp+60h] [rbp-91h] BYREF
  LPCITEMIDLIST ppidlLast[2]; // [rsp+70h] [rbp-81h] BYREF
  HWND v31; // [rsp+80h] [rbp-71h] BYREF
  __int64 v32; // [rsp+88h] [rbp-69h]
  const wchar_t *v33; // [rsp+90h] [rbp-61h]
  struct IShellFolder2 *v34; // [rsp+98h] [rbp-59h]
  __int64 v35; // [rsp+A0h] [rbp-51h]
  const struct _ITEMID_CHILD **v36; // [rsp+A8h] [rbp-49h]
  __int64 v37; // [rsp+B0h] [rbp-41h]
  __int64 v38; // [rsp+B8h] [rbp-39h]
  __int64 v39; // [rsp+C0h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+D0h] [rbp-21h] BYREF

  v11 = ppv;
  if ( !ppv )
    return 2147500035LL;
  ppv->lpVtbl = 0;
  v13 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v13 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v13 && a3 == 1 )
  {
    v29[0] = 0;
    v14 = SHCreateItemWithParentHelper(
            (const struct _ITEMIDLIST_ABSOLUTE *)this[18].lpVtbl,
            0,
            *a4,
            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
            v29);
    if ( v14 >= 0 )
    {
      v28 = 0;
      v14 = (*(__int64 (__fastcall **)(void *, __int64, GUID *, __int64 *))(*(_QWORD *)v29[0] + 64LL))(
              v29[0],
              96,
              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
              &v28);
      if ( v14 >= 0 )
      {
        memset(&pvar, 0, sizeof(pvar));
        v14 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, VARIANTARG *))(*(_QWORD *)v28 + 40LL))(
                v28,
                &PKEY_DBFolderPidl,
                &pvar);
        if ( v14 >= 0 )
        {
          if ( pvar.vt == 65 )
          {
            ppv = 0;
            ppidlLast[0] = 0;
            v14 = SHBindToParent(
                    (LPCITEMIDLIST)pvar.pRecInfo,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    (void **)&ppv,
                    ppidlLast);
            if ( v14 >= 0 )
              v14 = ((__int64 (__fastcall *)(struct IContextMenu *, HWND, __int64, LPCITEMIDLIST *, const struct _GUID *, unsigned int *, struct IContextMenu *))ppv->lpVtbl[1].InvokeCommand)(
                      ppv,
                      a2,
                      1,
                      ppidlLast,
                      a5,
                      a6,
                      v11);
            ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
          }
          else
          {
            v14 = -2147418113;
            if ( !pvar.vt )
              v14 = -2147467262;
          }
        }
        PropVariantClear((PROPVARIANT *)&pvar);
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v28);
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(v29);
    return (unsigned int)v14;
  }
  v15 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
    v15 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
  if ( !v15 )
    goto LABEL_68;
  v16 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
    v16 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
  if ( !v16 )
  {
LABEL_68:
    ppv = 0;
    v14 = ATL::CComObject<CExtractIcon>::CreateInstance(&ppv);
    if ( v14 >= 0 )
    {
      v26 = (CExtractIcon *)ppv;
      ((void (__fastcall *)(struct IContextMenu *))ppv->lpVtbl->AddRef)(ppv);
      v14 = CExtractIcon::Init(v26, this, *a4);
      if ( v14 >= 0 )
        v14 = (**(__int64 (__fastcall ***)(CExtractIcon *, const struct _GUID *, struct IContextMenu *))v26)(
                v26,
                a5,
                v11);
      (*(void (__fastcall **)(CExtractIcon *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return (unsigned int)v14;
  }
  v14 = -2147467262;
  v17 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IQueryInfo.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1 )
    v17 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IQueryInfo.Data4;
  if ( !v17 )
  {
    VariantInit(&pvarg);
    VariantInit(&pvar);
    if ( CPidlMgr::PropertyDetailFromPIDL((CPidlMgr *)&this[13], *a4, &PKEY_TooltipText, 8u, &pvar) >= 0 && pvar.vt == 8 )
    {
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)(pvar.llVal + 2 * v24) );
      if ( v24 )
      {
        ppv = 0;
        v14 = ATL::CComObject<CQueryInfo>::CreateInstance(&ppv);
        if ( v14 >= 0 )
        {
          v25 = (CCSCQueryInfo *)ppv;
          ((void (__fastcall *)(struct IContextMenu *))ppv->lpVtbl->AddRef)(ppv);
          v14 = CCSCQueryInfo::Init(v25, pvar.bstrVal);
          if ( v14 >= 0 )
            v14 = (**(__int64 (__fastcall ***)(CCSCQueryInfo *, const struct _GUID *, struct IContextMenu *))v25)(
                    v25,
                    a5,
                    v11);
          (*(void (__fastcall **)(CCSCQueryInfo *))(*(_QWORD *)v25 + 16LL))(v25);
        }
      }
    }
    goto LABEL_57;
  }
  v18 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1 )
    v18 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4;
  if ( v18 )
  {
    v19 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v19 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( !v19 )
    {
      ppv = 0;
      v14 = ATL::CComObject<CMessageContextMenu>::CreateInstance(&ppv);
      if ( v14 >= 0 )
      {
        v20 = (CMessageContextMenu *)ppv;
        ((void (__fastcall *)(struct IContextMenu *))ppv->lpVtbl->AddRef)(ppv);
        v31 = a2;
        v32 = 0;
        v33 = 0;
        v34 = this;
        v35 = a3;
        v36 = a4;
        v37 = 0;
        v38 = 0;
        v39 = 0;
        ppv = 0;
        if ( AutoLibrary::valid((AutoLibrary *)&g_shell32Helper)
          && (AutoLibrary::load((AutoLibrary *)&g_shell32Helper),
              (ProcAddress = GetProcAddress(qword_180053418, "SHCreateDefaultContextMenu")) != 0) )
        {
          v14 = ((__int64 (__fastcall *)(HWND *, GUID *, struct IContextMenu **))ProcAddress)(
                  &v31,
                  &GUID_000214e4_0000_0000_c000_000000000046,
                  &ppv);
          if ( v14 >= 0 )
          {
            v14 = CMessageContextMenu::Init(v20, (LPCITEMIDLIST)this[18].lpVtbl, a4, a3, ppv);
            if ( v14 >= 0 )
              v14 = (**(__int64 (__fastcall ***)(CMessageContextMenu *, const struct _GUID *, struct IContextMenu *))v20)(
                      v20,
                      a5,
                      v11);
          }
        }
        else
        {
          v14 = -2147024769;
        }
        (*(void (__fastcall **)(CMessageContextMenu *))(*(_QWORD *)v20 + 16LL))(v20);
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
      }
    }
    return (unsigned int)v14;
  }
  VariantInit(&pvarg);
  VariantInit(&pvar);
  v14 = CPidlMgr::PropertyDetailFromPIDL((CPidlMgr *)&this[13], *a4, &PKEY_ItemType, 8u, &pvarg);
  if ( v14 < 0 )
    goto LABEL_57;
  v14 = CPidlMgr::PropertyDetailFromPIDL((CPidlMgr *)&this[13], *a4, &PKEY_ParsingPath, 8u, &pvar);
  if ( v14 < 0 )
    goto LABEL_57;
  if ( (unsigned int)IsAttachment(pvar.bstrVal) )
  {
    bstrVal = L"MAPI/Attachment";
  }
  else
  {
    bstrVal = pvarg.bstrVal;
    if ( pvarg.llVal && *pvarg.bstrVal == 46 )
    {
      ppv = 0;
      *(GUID *)ppidlLast = CLSID_QueryAssociations;
      v14 = AssocCreate((CLSID *)ppidlLast, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, (void **)&ppv);
      if ( v14 >= 0 )
      {
        v14 = ((__int64 (__fastcall *)(struct IContextMenu *, _QWORD, const wchar_t *, _QWORD, _QWORD))ppv->lpVtbl->QueryContextMenu)(
                ppv,
                0,
                bstrVal,
                0,
                0);
        if ( v14 >= 0 )
          v14 = ((__int64 (__fastcall *)(struct IContextMenu *, const struct _GUID *, struct IContextMenu *))ppv->lpVtbl->QueryInterface)(
                  ppv,
                  a5,
                  v11);
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
      goto LABEL_57;
    }
  }
  LODWORD(v31) = 2;
  v32 = 0;
  v33 = bstrVal;
  LODWORD(v34) = 7;
  v35 = 0;
  v36 = (const struct _ITEMID_CHILD **)bstrVal;
  if ( AutoLibrary::valid((AutoLibrary *)&g_shell32Helper)
    && (AutoLibrary::load((AutoLibrary *)&g_shell32Helper),
        (v23 = GetProcAddress(qword_180053418, "AssocCreateForClasses")) != 0) )
  {
    v14 = ((__int64 (__fastcall *)(HWND *, __int64, const struct _GUID *, struct IContextMenu *))v23)(&v31, 2, a5, v11);
  }
  else
  {
    v14 = -2147024769;
  }
LABEL_57:
  VariantClear(&pvar);
  VariantClear(&pvarg);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180020180  mov     [rsp-8+arg_8], rdx
0x180020185  push    rbp
0x180020186  push    rbx
0x180020187  push    rsi
0x180020188  push    rdi
0x180020189  push    r12
0x18002018b  push    r13
0x18002018d  push    r14
0x18002018f  push    r15
0x180020191  lea     rbp, [rsp-7]
0x180020196  sub     rsp, 0F8h
0x18002019d  mov     r14, r9
0x1800201a0  mov     r12d, r8d
0x1800201a3  mov     rsi, rdx
0x1800201a6  mov     r13, rcx
0x1800201a9  mov     r15, [rbp+3Fh+ppv]
0x1800201ad  xor     ecx, ecx
0x1800201af  test    r15, r15
0x1800201b2  jnz     short loc_1800201BE
0x1800201b4  mov     eax, 80004003h
0x1800201b9  jmp     loc_1800207BD
0x1800201be  mov     [r15], rcx
0x1800201c1  mov     rdi, [rbp+3Fh+arg_20]
0x1800201c5  mov     rax, [rdi]
0x1800201c8  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x1800201cf  jnz     short loc_1800201DC
0x1800201d1  mov     rax, [rdi+8]
0x1800201d5  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800201dc  test    rax, rax
0x1800201df  jnz     loc_18002033A
0x1800201e5  cmp     r12d, 1
0x1800201e9  jnz     loc_18002033A
0x1800201ef  mov     [rsp+130h+var_D0], rcx
0x1800201f4  lea     rax, [rsp+130h+var_D0]
0x1800201f9  mov     [rsp+130h+var_110], rax; void **
0x1800201fe  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; struct _GUID *
0x180020205  mov     r8, [r14]; struct _ITEMID_CHILD *
0x180020208  xor     edx, edx; struct IShellFolder *
0x18002020a  mov     rcx, [r13+90h]; struct _ITEMIDLIST_ABSOLUTE *
0x180020211  call    ?SHCreateItemWithParentHelper@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; SHCreateItemWithParentHelper(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)
0x180020216  mov     ebx, eax
0x180020218  xor     r14d, r14d
0x18002021b  test    eax, eax
0x18002021d  js      loc_18002032B
0x180020223  mov     [rsp+130h+var_D8], r14
0x180020228  mov     rcx, [rsp+130h+var_D0]
0x18002022d  mov     rax, [rcx]
0x180020230  lea     r9, [rsp+130h+var_D8]
0x180020235  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002023c  lea     edx, [r12+5Fh]
0x180020241  mov     rax, [rax+40h]
0x180020245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002024a  mov     ebx, eax
0x18002024c  test    eax, eax
0x18002024e  js      loc_180020320
0x180020254  xorps   xmm0, xmm0
0x180020257  xor     eax, eax
0x180020259  movups  xmmword ptr [rsp+130h+pvar], xmm0
0x18002025e  mov     [rsp+130h+pidl], rax
0x180020263  mov     rcx, [rsp+130h+var_D8]
0x180020268  mov     rax, [rcx]
0x18002026b  lea     r8, [rsp+130h+pvar]
0x180020270  lea     rdx, PKEY_DBFolderPidl
0x180020277  mov     rax, [rax+28h]
0x18002027b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020280  mov     ebx, eax
0x180020282  test    eax, eax
0x180020284  js      loc_180020314
0x18002028a  lea     eax, [r12+40h]
0x18002028f  movzx   ecx, word ptr [rsp+130h+pvar]
0x180020294  cmp     ax, cx
0x180020297  jz      short loc_1800202AD
0x180020299  mov     ebx, 8000FFFFh
0x18002029e  mov     eax, 80004002h
0x1800202a3  xor     edx, edx
0x1800202a5  cmp     dx, cx
0x1800202a8  cmovz   ebx, eax
0x1800202ab  jmp     short loc_180020314
0x1800202ad  mov     [rbp+3Fh+ppv], r14
0x1800202b1  mov     [rsp+130h+ppidlLast], r14
0x1800202b6  lea     r9, [rsp+130h+ppidlLast]; ppidlLast
0x1800202bb  lea     r8, [rbp+3Fh+ppv]; ppv
0x1800202bf  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800202c6  mov     rcx, [rsp+130h+pidl]; pidl
0x1800202cb  call    cs:__imp_SHBindToParent
0x1800202d1  mov     ebx, eax
0x1800202d3  test    eax, eax
0x1800202d5  js      short loc_18002030A
0x1800202d7  mov     rcx, [rbp+3Fh+ppv]
0x1800202db  mov     rax, [rcx]
0x1800202de  mov     [rsp+130h+var_100], r15
0x1800202e3  mov     rdx, [rbp+3Fh+arg_28]
0x1800202e7  mov     [rsp+130h+var_108], rdx
0x1800202ec  mov     [rsp+130h+var_110], rdi
0x1800202f1  lea     r9, [rsp+130h+ppidlLast]
0x1800202f6  mov     r8d, 1
0x1800202fc  mov     rdx, rsi
0x1800202ff  mov     rax, [rax+50h]
0x180020303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020308  mov     ebx, eax
0x18002030a  lea     rcx, [rbp+3Fh+ppv]
0x18002030e  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180020313  nop
0x180020314  lea     rcx, [rsp+130h+pvar]; pvar
0x180020319  call    cs:__imp_PropVariantClear
0x18002031f  nop
0x180020320  lea     rcx, [rsp+130h+var_D8]
0x180020325  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002032a  nop
0x18002032b  lea     rcx, [rsp+130h+var_D0]
0x180020330  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180020335  jmp     loc_1800207BB
0x18002033a  mov     rax, [rdi]
0x18002033d  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180020344  jnz     short loc_180020351
0x180020346  mov     rax, [rdi+8]
0x18002034a  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x180020351  test    rax, rax
0x180020354  jz      loc_18002075C
0x18002035a  mov     rax, [rdi]
0x18002035d  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180020364  jnz     short loc_180020371
0x180020366  mov     rax, [rdi+8]
0x18002036a  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180020371  test    rax, rax
0x180020374  jz      loc_18002075C
0x18002037a  mov     ebx, 80004002h
0x18002037f  mov     rax, [rdi]
0x180020382  sub     rax, qword ptr cs:IID_IQueryInfo.Data1
0x180020389  jnz     short loc_180020396
0x18002038b  mov     rax, [rdi+8]
0x18002038f  sub     rax, qword ptr cs:IID_IQueryInfo.Data4
0x180020396  test    rax, rax
0x180020399  jz      loc_18002068A
0x18002039f  mov     rax, [rdi]
0x1800203a2  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1
0x1800203a9  jnz     short loc_1800203B6
0x1800203ab  mov     rax, [rdi+8]
0x1800203af  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4
0x1800203b6  test    rax, rax
0x1800203b9  jz      loc_1800204EA
0x1800203bf  mov     rax, [rdi]
0x1800203c2  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800203c9  jnz     short loc_1800203D6
0x1800203cb  mov     rax, [rdi+8]
0x1800203cf  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800203d6  test    rax, rax
0x1800203d9  jnz     loc_1800207BB
0x1800203df  mov     [rbp+3Fh+ppv], rcx
0x1800203e3  lea     rcx, [rbp+3Fh+ppv]
0x1800203e7  call    ?CreateInstance@?$CComObject@VCMessageContextMenu@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMessageContextMenu>::CreateInstance(ATL::CComObject<CMessageContextMenu> * *)
0x1800203ec  mov     ebx, eax
0x1800203ee  test    eax, eax
0x1800203f0  js      loc_1800207BB
0x1800203f6  mov     rsi, [rbp+3Fh+ppv]
0x1800203fa  mov     rax, [rsi]
0x1800203fd  mov     rcx, rsi
0x180020400  mov     rax, [rax+8]
0x180020404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020409  mov     rax, [rbp+3Fh+arg_8]
0x18002040d  mov     [rbp+3Fh+var_B0], rax
0x180020411  xor     ebx, ebx
0x180020413  mov     [rbp+3Fh+var_A8], rbx
0x180020417  mov     [rbp+3Fh+var_A0], rbx
0x18002041b  mov     [rbp+3Fh+var_98], r13
0x18002041f  mov     dword ptr [rbp+3Fh+var_90], r12d
0x180020423  xor     eax, eax
0x180020425  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x180020428  mov     [rbp+3Fh+var_88], r14
0x18002042c  mov     [rbp+3Fh+var_80], rbx
0x180020430  mov     [rbp+3Fh+var_78], rbx
0x180020434  mov     [rbp+3Fh+var_70], rbx
0x180020438  mov     [rbp+3Fh+ppv], rbx
0x18002043c  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x180020443  call    ?valid@AutoLibrary@@QEAA_NXZ; AutoLibrary::valid(void)
0x180020448  test    al, al
0x18002044a  jz      short loc_1800204C7
0x18002044c  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x180020453  call    ?load@AutoLibrary@@AEAAXXZ; AutoLibrary::load(void)
0x180020458  lea     rdx, aShcreatedefaul; "SHCreateDefaultContextMenu"
0x18002045f  mov     rcx, cs:qword_180053418; hModule
0x180020466  call    cs:__imp_GetProcAddress
0x18002046c  test    rax, rax
0x18002046f  jz      short loc_1800204C7
0x180020471  lea     r8, [rbp+3Fh+ppv]
0x180020475  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x18002047c  lea     rcx, [rbp+3Fh+var_B0]
0x180020480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020485  mov     ebx, eax
0x180020487  test    eax, eax
0x180020489  js      short loc_1800204CC
0x18002048b  mov     rax, [rbp+3Fh+ppv]
0x18002048f  mov     [rsp+130h+var_110], rax; struct IContextMenu *
0x180020494  mov     r9d, r12d; unsigned int
0x180020497  mov     r8, r14; struct _ITEMID_CHILD **
0x18002049a  mov     rdx, [r13+90h]; pidl
0x1800204a1  mov     rcx, rsi; this
0x1800204a4  call    ?Init@CMessageContextMenu@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBQEFBU_ITEMID_CHILD@@IPEAUIContextMenu@@@Z; CMessageContextMenu::Init(_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const * const *,uint,IContextMenu *)
0x1800204a9  mov     ebx, eax
0x1800204ab  test    eax, eax
0x1800204ad  js      short loc_1800204CC
0x1800204af  mov     rax, [rsi]
0x1800204b2  mov     r8, r15
0x1800204b5  mov     rdx, rdi
0x1800204b8  mov     rcx, rsi
0x1800204bb  mov     rax, [rax]
0x1800204be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204c3  mov     ebx, eax
0x1800204c5  jmp     short loc_1800204CC
0x1800204c7  mov     ebx, 8007007Fh
0x1800204cc  mov     rax, [rsi]
0x1800204cf  mov     rcx, rsi
0x1800204d2  mov     rax, [rax+10h]
0x1800204d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204db  nop
0x1800204dc  lea     rcx, [rbp+3Fh+ppv]
0x1800204e0  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800204e5  jmp     loc_1800207BB
0x1800204ea  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800204ee  call    cs:__imp_VariantInit
0x1800204f4  nop
0x1800204f5  lea     rcx, [rsp+130h+pvar]; pvarg
0x1800204fa  call    cs:__imp_VariantInit
0x180020500  nop
0x180020501  mov     esi, 8
0x180020506  mov     r9d, esi; unsigned __int16
0x180020509  lea     rax, [rbp+3Fh+pvarg]
0x18002050d  mov     [rsp+130h+var_110], rax; struct tagVARIANT *
0x180020512  lea     r8, PKEY_ItemType; struct _tagpropertykey *
0x180020519  mov     rdx, [r14]; struct _ITEMIDLIST_RELATIVE *
0x18002051c  lea     rcx, [r13+68h]; this
0x180020520  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x180020525  mov     ebx, eax
0x180020527  xor     r12d, r12d
0x18002052a  test    eax, eax
0x18002052c  js      loc_18002066F
0x180020532  mov     r9d, esi; unsigned __int16
0x180020535  lea     rax, [rsp+130h+pvar]
0x18002053a  mov     [rsp+130h+var_110], rax; struct tagVARIANT *
0x18002053f  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x180020546  mov     rdx, [r14]; struct _ITEMIDLIST_RELATIVE *
0x180020549  lea     rcx, [r13+68h]; this
0x18002054d  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x180020552  mov     ebx, eax
0x180020554  test    eax, eax
0x180020556  js      loc_18002066F
0x18002055c  mov     rcx, [rsp+130h+pvar+8]; wchar_t *
0x180020561  call    ?IsAttachment@@YAHPEB_W@Z; IsAttachment(wchar_t const *)
0x180020566  test    eax, eax
0x180020568  jz      short loc_1800205E5
0x18002056a  lea     rsi, aMapiAttachment; "MAPI/Attachment"
0x180020571  mov     ebx, 2
0x180020576  mov     dword ptr [rbp+3Fh+var_B0], ebx
0x180020579  mov     [rbp+3Fh+var_A8], r12
0x18002057d  mov     [rbp+3Fh+var_A0], rsi
0x180020581  mov     dword ptr [rbp+3Fh+var_98], 7
0x180020588  mov     [rbp+3Fh+var_90], r12
0x18002058c  mov     [rbp+3Fh+var_88], rsi
0x180020590  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x180020597  call    ?valid@AutoLibrary@@QEAA_NXZ; AutoLibrary::valid(void)
0x18002059c  test    al, al
0x18002059e  jz      loc_18002066A
0x1800205a4  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x1800205ab  call    ?load@AutoLibrary@@AEAAXXZ; AutoLibrary::load(void)
0x1800205b0  lea     rdx, aAssoccreatefor; "AssocCreateForClasses"
0x1800205b7  mov     rcx, cs:qword_180053418; hModule
0x1800205be  call    cs:__imp_GetProcAddress
0x1800205c4  test    rax, rax
0x1800205c7  jz      loc_18002066A
0x1800205cd  mov     r9, r15
0x1800205d0  mov     r8, rdi
0x1800205d3  mov     edx, ebx
0x1800205d5  lea     rcx, [rbp+3Fh+var_B0]
0x1800205d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205de  mov     ebx, eax
0x1800205e0  jmp     loc_18002066F
0x1800205e5  mov     rsi, qword ptr [rbp+3Fh+pvarg+8]
0x1800205e9  test    rsi, rsi
0x1800205ec  jz      short loc_180020571
0x1800205ee  cmp     word ptr [rsi], 2Eh ; '.'
0x1800205f2  jnz     loc_180020571
0x1800205f8  mov     [rbp+3Fh+ppv], r12
0x1800205fc  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180020603  movdqu  xmmword ptr [rsp+130h+ppidlLast], xmm0
0x180020609  lea     r8, [rbp+3Fh+ppv]; ppv
0x18002060d  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x180020614  lea     rcx, [rsp+130h+ppidlLast]; clsid
0x180020619  call    cs:__imp_AssocCreate
0x18002061f  mov     ebx, eax
0x180020621  test    eax, eax
0x180020623  js      short loc_18002065F
0x180020625  mov     rcx, [rbp+3Fh+ppv]
0x180020629  mov     rax, [rcx]
0x18002062c  mov     [rsp+130h+var_110], r12
0x180020631  xor     r9d, r9d
0x180020634  mov     r8, rsi
0x180020637  xor     edx, edx
0x180020639  mov     rax, [rax+18h]
0x18002063d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020642  mov     ebx, eax
  ... truncated ...
```
