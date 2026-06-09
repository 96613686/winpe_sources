# CIEFrameAuto::_NavigateHelper(IUri *,_ITEMIDLIST_ABSOLUTE *,tagVARIANT *,tagVARIANT const *,tagVARIANT *,tagVARIANT *,IBindCtx *,ushort *,long *)

- ea: `0x18004e60c`
- end: `0x18004f35c`
- name: `?_NavigateHelper@CIEFrameAuto@@IEAAJPEAUIUri@@PEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagVARIANT@@PEBU4@22PEAUIBindCtx@@PEAGPEAJ@Z`
- size: `3408`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, struct IUri *, struct _ITEMIDLIST_ABSOLUTE *, struct tagVARIANT *, const struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct IBindCtx *, unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e3e0`
- `0x1801119b0`
- `0x180111b20`
- `0x180111b90`

## callees

- `0x180005030`
- `0x180007010`
- `0x180014978`
- `0x18004e60c`
- `0x180056d9c`
- `0x18005f340`
- `0x180076d50`
- `0x1800819c0`
- `0x180084110`
- `0x18009282c`
- `0x1800b75a4`
- `0x1800b76a4`
- `0x1800bfc62`
- `0x180102284`
- `0x1801025dc`
- `0x180103688`
- `0x18011195c`
- `0x1801149b8`
- `0x180115648`
- `0x180176124`
- `0x18042afa8`
- `0x180521b58`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18004e86b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18004e86b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNW` at `0x18004e852`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNW` at `0x18004e852`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18004f0e2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18004f0e2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x18004f141`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x18004f141`
- `ole32!CreateBindCtx` at `0x18004f190`
- `ole32!CreateBindCtx` at `0x18004f190`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e88d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e937`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e88d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e937`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e996`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f21d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f29c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f2ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e996`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f21d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f29c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f2ff`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e7ce`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e7ce`
- `OLEAUT32!__imp_VariantClear` at `0x18004e987`
- `OLEAUT32!__imp_VariantClear` at `0x18004e987`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18004ef19`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18004ef19`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004ef06`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004ef06`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004eee2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004eee2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004f200`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004f200`
- `SHELL32!__imp_ILFree` at `0x18004f259`
- `SHELL32!__imp_ILFree` at `0x18004f259`
- `iertutil!CreateUri` at `0x18004ecd8`
- `iertutil!CreateUri` at `0x18004ecd8`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18004ec41`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18004ec41`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18004e828`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18004e828`

## string_xrefs

- `0x18004efbe`: `BIND_CONTEXT_CREATED_FOR_CALLERURL`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_NavigateHelper(
        CIEFrameAuto *this,
        struct IUri *a2,
        struct _ITEMIDLIST_ABSOLUTE *a3,
        IUri *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6,
        struct tagVARIANT *a7,
        struct IBindCtx *a8,
        unsigned __int16 *a9,
        int *a10)
{
  struct IBindStatusCallback *v10; // rdi
  CIEFrameAuto *v13; // r15
  struct IUriVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUri *, const IID *const, void **); // rax
  int v16; // ebx
  signed int v17; // r14d
  LONGLONG llVal; // r13
  HRESULT v19; // ebx
  PWSTR v20; // rax
  BSTR v21; // rax
  OLECHAR *v22; // r15
  void *v23; // r9
  int v24; // r15d
  int v25; // r12d
  unsigned int lpVtbl_low; // esi
  int v27; // edx
  int v28; // ecx
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  int v32; // ecx
  int *v33; // r10
  CIEFrameAuto *v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // r9
  char IsFrameSharedMemoryFlagSetForCurrentThread; // al
  const unsigned __int16 *v38; // r8
  bool *v39; // rdx
  int v40; // eax
  SAFEARRAY *v41; // rsi
  unsigned int v42; // ebx
  unsigned __int16 *bstrVal; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  UINT Elemsize; // eax
  unsigned int v46; // edx
  int v47; // ecx
  unsigned int v48; // ebx
  bool v49; // cf
  struct IBindCtx *v50; // r14
  __int64 v51; // rax
  HRESULT v52; // eax
  __int16 v53; // di
  void *v54; // rax
  CIEFrameAuto *v55; // r12
  struct _ITEMIDLIST_ABSOLUTE *v56; // r15
  LPCWSTR LocationW; // r15
  __int64 v58; // r8
  LPBC v59; // rcx
  struct IUri *v60; // rcx
  BOOL v61; // edi
  struct IUri *v63; // rcx
  BOOL v64; // ebx
  int varIn; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+28h] [rbp-D8h]
  int v67; // [rsp+40h] [rbp-C0h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath[2]; // [rsp+50h] [rbp-B0h] BYREF
  CIEFrameAuto *v70; // [rsp+58h] [rbp-A8h]
  struct _ITEMIDLIST_ABSOLUTE *v71; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v72; // [rsp+68h] [rbp-98h] BYREF
  int v73; // [rsp+70h] [rbp-90h]
  VARIANT *v74; // [rsp+78h] [rbp-88h] BYREF
  LPBC ppbc; // [rsp+80h] [rbp-80h] BYREF
  struct tagVARIANT *v76; // [rsp+90h] [rbp-70h]
  int v77; // [rsp+98h] [rbp-68h]
  void **v78; // [rsp+A0h] [rbp-60h] BYREF
  struct IUri *v79; // [rsp+A8h] [rbp-58h]
  unsigned int v80; // [rsp+B0h] [rbp-50h]
  BSTR pbstr[2]; // [rsp+B8h] [rbp-48h] BYREF
  UINT v82; // [rsp+C8h] [rbp-38h] BYREF
  struct tagVARIANT *v83; // [rsp+D0h] [rbp-30h]
  void *ppvData; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v85; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v86; // [rsp+E8h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+F0h] [rbp-10h] BYREF
  PWSTR v88; // [rsp+F8h] [rbp-8h]
  LPITEMIDLIST pidl; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  DWORD reserved[2]; // [rsp+130h] [rbp+30h]
  _OWORD v92[3]; // [rsp+138h] [rbp+38h] BYREF
  int v93; // [rsp+168h] [rbp+68h]
  WCHAR pszPath[2]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v95[4172]; // [rsp+174h] [rbp+74h] BYREF
  WCHAR pwzURI[2088]; // [rsp+11C0h] [rbp+10C0h] BYREF

  v10 = 0;
  v76 = a6;
  v13 = this;
  v83 = a7;
  v74 = a5;
  *(_QWORD *)reserved = a8;
  v72 = a9;
  ppURI = a4;
  *(_QWORD *)pcchPath = a3;
  v70 = this;
  if ( !*((_QWORD *)this + 55) || !a2 )
    return 2147500037LL;
  lpVtbl = a2->lpVtbl;
  v78 = &CUString::`vftable';
  v79 = 0;
  v82 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)pbstr = 0;
  v80 = 0;
  v71 = 0;
  if ( ((int (__fastcall *)(struct IUri *, GUID *, struct _ITEMIDLIST_ABSOLUTE **))QueryInterface)(
         a2,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v71) >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *, _QWORD, BSTR *, UINT *))(*(_QWORD *)v71 + 224LL))(
            v71,
            v80,
            &pbstr[1],
            &v82);
    (*(void (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *))(*(_QWORD *)v71 + 16LL))(v71);
    goto LABEL_5;
  }
  v16 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))a2->lpVtbl->GetPropertyBSTR)(a2, v80, pbstr, 0);
  if ( v16 < 0 )
  {
LABEL_5:
    if ( v16 < 0 )
      goto LABEL_7;
    goto LABEL_6;
  }
  pbstr[1] = pbstr[0];
  v82 = SysStringLen(pbstr[0]);
LABEL_6:
  v79 = a2;
  ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
LABEL_7:
  if ( v16 == 1 )
    v16 = CUString::Set((CUString *)&v78, a2, Uri_PROPERTY_RAW_URI);
  if ( v16 || !v82 )
  {
    v63 = v79;
    v78 = &CUString::`vftable';
    v64 = v79 != 0;
    if ( v79 || v80 != 11 )
    {
      if ( pbstr[0] )
      {
        SysFreeString(pbstr[0]);
        v63 = v79;
        pbstr[0] = 0;
      }
      pbstr[1] = 0;
      v82 = 0;
      if ( v64 && v63 )
        ((void (__fastcall *)(struct IUri *))v63->lpVtbl->Release)(v63);
    }
    return 2147500037LL;
  }
  pidl = 0;
  v17 = 0;
  ppbc = 0;
  llVal = 0;
  ppvData = 0;
  v19 = -2147467259;
  v73 = 0;
  v88 = 0;
  if ( !v74 )
    goto LABEL_34;
  if ( v74->vt == 16392 )
  {
    llVal = *v74->pllVal;
  }
  else
  {
    if ( v74->vt != 8 )
      goto LABEL_34;
    llVal = v74->llVal;
  }
  if ( llVal )
  {
    if ( *(_WORD *)llVal )
    {
      ppvOut = 0;
      v85 = 0;
      v86 = 0;
      v19 = IUnknown_QueryService(
              (IUnknown *)v13 + 26,
              &IID_ITargetFrame2,
              &GUID_86d52e11_94a8_11d0_82af_00c04fd5ae38,
              &ppvOut);
      if ( v19 >= 0 )
      {
        if ( !StrCmpNW((PCWSTR)llVal, L"_[", 2) )
        {
          v20 = StrChrW((PCWSTR)llVal, 0x5Du);
          v88 = v20;
          if ( v20 )
          {
            v88 = v20 + 1;
            llVal = (LONGLONG)SysAllocString(v20 + 1);
            if ( !llVal )
            {
              v19 = -2147024882;
              goto LABEL_159;
            }
          }
        }
        v67 = 0;
        v19 = (*(__int64 (__fastcall **)(void *, LONGLONG, __int64, __int64 *))(*(_QWORD *)ppvOut + 104LL))(
                ppvOut,
                llVal,
                1,
                &v85);
        if ( v19 >= 0 )
        {
          if ( v85 )
          {
            v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v85)(
                    v85,
                    &GUID_0002df05_0000_0000_c000_000000000046,
                    &v86);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            if ( v19 >= 0 )
            {
              *(_OWORD *)&pvarg.decVal.Lo32 = 0u;
              *(_QWORD *)&pvarg.vt = 8;
              v21 = SysAllocString(pbstr[1]);
              v22 = v21;
              if ( !v21 )
                goto LABEL_159;
              v19 = (*(__int64 (__fastcall **)(__int64, BSTR, IUri *, VARIANTARG *, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)v86 + 88LL))(
                      v86,
                      v21,
                      a4,
                      &pvarg,
                      v76,
                      v83);
              VariantClear(&pvarg);
              SysFreeString(v22);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
              v13 = v70;
              v67 = 1;
            }
          }
          else
          {
            if ( !*(_WORD *)llVal )
              llVal = (LONGLONG)L"_desktop";
            v17 = 2;
            v73 = 1;
            v19 = -2147467259;
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        if ( v67 )
          goto LABEL_159;
      }
    }
  }
LABEL_34:
  v71 = 0;
  v23 = 0;
  if ( v19 < 0 )
  {
    if ( *(_QWORD *)pcchPath )
    {
      v23 = *(void **)pcchPath;
      v71 = *(struct _ITEMIDLIST_ABSOLUTE **)pcchPath;
    }
    else
    {
      v19 = CIEFrameAuto::_PidlFromIUriEtc(v13, 0, a2, v72, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( v19 < 0 )
        goto LABEL_159;
      v23 = pidl;
      v71 = (struct _ITEMIDLIST_ABSOLUTE *)pidl;
    }
  }
  v24 = 0;
  v25 = 0;
  lpVtbl_low = 0;
  if ( !ppURI )
    goto LABEL_73;
  if ( LOWORD(ppURI->lpVtbl) == 3 )
  {
    lpVtbl_low = (unsigned int)ppURI[1].lpVtbl;
  }
  else
  {
    if ( LOWORD(ppURI->lpVtbl) != 2 )
      goto LABEL_46;
    lpVtbl_low = SLOWORD(ppURI[1].lpVtbl);
  }
  if ( (lpVtbl_low & 0x100) != 0 )
    v17 |= 0x80000000;
LABEL_46:
  v27 = v17 | 0x2000000;
  if ( (lpVtbl_low & 0x200) == 0 )
    v27 = v17;
  v28 = v27 | 0x400000;
  if ( (lpVtbl_low & 0x400) == 0 )
    v28 = v27;
  v29 = v28 | 2;
  if ( (lpVtbl_low & 1) == 0 )
    v29 = v28;
  v30 = v29 | 0x20;
  if ( (lpVtbl_low & 2) == 0 )
    v30 = v29;
  v17 = v30 | 0x100000;
  v31 = (lpVtbl_low & 4) != 0 ? 0x2200 : 0;
  if ( (lpVtbl_low & 0x400000) == 0 )
    v17 = v30;
  if ( (lpVtbl_low & 8) != 0 )
    v31 |= 0x20u;
  v32 = v31 | 0x400;
  if ( (lpVtbl_low & 0x40) == 0 )
    v32 = v31;
  v24 = v32 | 0x800000;
  if ( (lpVtbl_low & 0x80u) == 0 )
    v24 = v32;
  v25 = (lpVtbl_low >> 12) & 8;
  if ( (lpVtbl_low & 2) != 0 )
    v17 |= 0x8000000u;
  if ( !(unsigned int)IsURLChild(v23, 1) )
    goto LABEL_73;
  v67 = (int)v33;
  if ( (lpVtbl_low & 0x10) == 0 )
  {
    if ( a10 )
    {
      v34 = v70;
      if ( *a10 != -2146697203
        || (int)_GetSearchInfo(*((struct IServiceProvider **)v70 + 61), 0, &v67, 0, v33) < 0
        || !v67 )
      {
        goto LABEL_74;
      }
      goto LABEL_72;
    }
LABEL_73:
    v34 = v70;
    goto LABEL_74;
  }
  v34 = v70;
LABEL_72:
  v17 |= 0x20000000u;
LABEL_74:
  v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, WCHAR *, __int64))(**((_QWORD **)v34 + 55)
                                                                                           + 80LL))(
          *((_QWORD *)v34 + 55),
          v71,
          pwzURI,
          0x8000);
  if ( v19 < 0 )
    goto LABEL_159;
  LODWORD(v72) = 0;
  *(_QWORD *)pcchPath = 0;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, DWORD *))v70 + 55))(
         *((_QWORD *)v70 + 55),
         &GUID_6bd38a1c_7310_4e76_8567_927d8f72ef27,
         pcchPath) >= 0 )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)pcchPath + 64LL))(*(_QWORD *)pcchPath, &v72);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pcchPath);
  if ( (_DWORD)v72 )
  {
LABEL_107:
    v41 = 0;
    v72 = 0;
    v42 = 0;
    if ( v83 )
    {
      if ( v83->vt == 16392 )
      {
        bstrVal = (unsigned __int16 *)*v83->pllVal;
LABEL_112:
        v72 = bstrVal;
        goto LABEL_113;
      }
      if ( v83->vt == 8 )
      {
        bstrVal = v83->bstrVal;
        goto LABEL_112;
      }
    }
LABEL_113:
    if ( v76 && (v76->vt & 0x2000) != 0 )
    {
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v76->llVal;
      if ( (v76->vt & 0x4000) != 0 )
        p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
      v41 = (SAFEARRAY *)p_llVal->llVal;
      if ( v41 )
      {
        if ( SafeArrayAccessData(v41, &ppvData) >= 0 )
        {
          LODWORD(ppURI) = 0;
          SafeArrayGetUBound(v41, 1u, (LONG *)&ppURI);
          LODWORD(ppURI) = (_DWORD)ppURI + 1;
          Elemsize = SafeArrayGetElemsize(v41);
          v42 = (_DWORD)ppURI * Elemsize;
          if ( !((_DWORD)ppURI * Elemsize) )
            ppvData = 0;
        }
      }
      else
      {
        v41 = 0;
      }
    }
    if ( !v72 && !ppvData && (v17 & 0x20000022) == 0 && !v24 && !v25 )
    {
      v46 = ((v17 & 0x100000 | 0x800u) >> 11) | 0x2000000;
      if ( (v17 & 0x2000000) == 0 )
        v46 = (v17 & 0x100000 | 0x800u) >> 11;
      v47 = v46 | 0x800000;
      if ( (v17 & 0x200000) == 0 )
        v47 = v46;
      v48 = v47 | 0x10000000;
      v49 = (v17 & 0x400000) != 0;
      v50 = *(struct IBindCtx **)reserved;
      if ( !v49 )
        v48 = v47;
      if ( *(_QWORD *)reserved )
      {
        v51 = **(_QWORD **)reserved;
        v74 = 0;
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANT **))(v51 + 80))(
               *(_QWORD *)reserved,
               L"BIND_CONTEXT_CREATED_FOR_CALLERURL",
               &v74) >= 0 )
          (*(void (__fastcall **)(VARIANT *))(*(_QWORD *)&v74->vt + 16LL))(v74);
        else
          CIEFrameAuto::_SetPendingNavigateContext(v70, v50, 0);
      }
      v52 = CIEFrameAuto::_BrowseObject(v70, v71, v48);
      goto LABEL_138;
    }
    v53 = -((*((_DWORD *)v70 + 119) & 1) != 0);
    LOWORD(ppURI) = -((*((_DWORD *)v70 + 119) & 2) != 0);
    v74 = (VARIANT *)ppvData;
    v54 = operator new(0x48u);
    if ( v54 )
    {
      v77 = 0;
      LOWORD(v66) = (_WORD)ppURI;
      v76 = (struct tagVARIANT *)__PAIR64__(v25, v24);
      LOWORD(varIn) = v53;
      v10 = (struct IBindStatusCallback *)CStubBindStatusCallbackEx::CStubBindStatusCallbackEx(
                                            v54,
                                            v72,
                                            v74,
                                            v42,
                                            varIn,
                                            v66);
      if ( v10 )
      {
        v55 = v70;
        v56 = v71;
        pcchPath[0] = 2087;
        v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, WCHAR *, __int64))(**((_QWORD **)v70 + 55)
                                                                                                 + 80LL))(
                *((_QWORD *)v70 + 55),
                v71,
                pszPath,
                0x8000);
        if ( v19 >= 0
          || PathCreateFromUrlW(pbstr[1], pszPath, pcchPath, 0) >= 0
          && pszPath[0] == 92
          && pszPath[1] == 92
          && (v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, _BYTE *, __int64))(**((_QWORD **)v55 + 55) + 80LL))(
                      *((_QWORD *)v55 + 55),
                      v56,
                      v95,
                      0x4000),
              v19 >= 0) )
        {
          LocationW = UrlGetLocationW(pszPath);
          if ( LocationW )
          {
            v58 = -1;
            do
              ++v58;
            while ( LocationW[v58] );
            memmove_0((void *)(LocationW + 1), LocationW, 2 * v58 + 2);
            *LocationW++ = 0;
          }
          if ( *(_QWORD *)reserved )
          {
            ppbc = *(LPBC *)reserved;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)reserved + 8LL))(*(_QWORD *)reserved);
LABEL_154:
            v49 = v73 != 0;
            v73 = -v73;
            v52 = CIEFrameAuto::NavigateHack(
                    (CIEFrameAuto *)((char *)v55 + 104),
                    v17,
                    ppbc,
                    v10,
                    (const unsigned __int16 *)(llVal & -(__int64)v49),
                    pszPath,
                    LocationW);
LABEL_138:
            v19 = v52;
            goto LABEL_157;
          }
          v19 = CreateBindCtx(0, &ppbc);
          if ( v19 >= 0 )
            goto LABEL_154;
        }
LABEL_157:
        if ( v41 )
          SafeArrayUnaccessData(v41);
        goto LABEL_159;
      }
    }
    else
    {
      v10 = 0;
    }
    v19 = -2147024882;
    goto LABEL_157;
  }
  v67 = 0;
  LOBYTE(ppURI) = DualEngine::IsHybridEnterpriseMode();
  pcchPath[0] = DualEngine::GetEngineSwitchingPolicyFlags();
  if ( IsDualEngineProcess() )
    IsFrameSharedMemoryFlagSetForCurrentThread = DualEngine::Internal::IsFrameSharedMemoryFlagSetForCurrentThread(128);
  else
    IsFrameSharedMemoryFlagSetForCurrentThread = 0;
  LOBYTE(v36) = (_BYTE)ppURI;
  LOBYTE(v35) = IsFrameSharedMemoryFlagSetForCurrentThread;
  if ( (unsigned __int8)DualEngine::ShouldUrlContinueNavigationInEdge(pwzURI, v35, pcchPath[0], v36) )
  {
    v38 = 0;
    if ( v83 )
    {
      if ( v83->vt == 16392 )
      {
        v38 = (const unsigned __int16 *)*v83->pllVal;
      }
      else if ( v83->vt == 8 )
      {
        v38 = v83->bstrVal;
      }
    }
    DualEngine::NavigationParams::NavigationParams((DualEngine::NavigationParams *)&pvarg, 0, v38, v76);
    ppURI = 0;
    if ( CreateUri(pwzURI, 0x3002B84u, 0, &ppURI) >= 0 )
    {
      *(_QWORD *)pcchPath = 0;
      if ( CIEFrameAuto::QueryService(
             (CIEFrameAuto *)((char *)v70 + 72),
             (const struct _GUID *)&SID_SDualEngineService,
             &GUID_5c96475e_66b9_48dd_a1bc_0bb3bc7b4010,
             (void **)pcchPath) >= 0 )
      {
        if ( (v17 & 2) != 0 )
        {
          v93 = 0;
          memset(v92, 0, sizeof(v92));
          if ( (lpVtbl_low & 0x300000) != 0 )
            LODWORD(v92[0]) = (unsigned int)ShouldOpenInNewWindow((lpVtbl_low & 0x200000) != 0 ? 0x80000 : 0x40000, v39) != 0
                            ? 3
                            : 0;
          else
            LODWORD(v92[0]) = (lpVtbl_low & 1) != 0 ? 3 : 0;
          (*(void (__fastcall **)(_QWORD, IUri *, _OWORD *, VARIANTARG *))(**(_QWORD **)pcchPath + 32LL))(
            *(_QWORD *)pcchPath,
            ppURI,
            v92,
            &pvarg);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, IUri *, __int64, VARIANTARG *))(**(_QWORD **)pcchPath + 24LL))(
            *(_QWORD *)pcchPath,
            ppURI,
            1,
            &pvarg);
        }
        v67 = 1;
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pcchPath);
    }
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
    DualEngine::NavigationParams::~NavigationParams((DualEngine::NavigationParams *)&pvarg);
    if ( v67 )
      goto LABEL_159;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 3;
  pvarg.lVal = lpVtbl_low;
  if ( (v17 & 2) != 0 )
  {
    lpVtbl_low |= 1u;
    pvarg.lVal = lpVtbl_low;
  }
  if ( v17 < 0 )
    pvarg.lVal = lpVtbl_low | 0x100;
  v40 = CIEFrameAuto::_HandleProtectedModeRedirect(v70, pwzURI, v71, &pvarg, v74, v76, v83);
  v19 = v40;
  if ( !v40 )
    goto LABEL_159;
  if ( v40 == -2147023286 )
  {
    v19 = 0;
  }
  else if ( v40 < 0 )
  {
    goto LABEL_159;
  }
  if ( !v67 )
    goto LABEL_107;
LABEL_159:
  if ( v88 && llVal )
    SysFreeString((BSTR)llVal);
  if ( v10 )
    CStubBindStatusCallbackEx::Release((CStubBindStatusCallbackEx *)v10);
  v59 = ppbc;
  if ( ppbc )
  {
    ppbc = 0;
    ((void (__fastcall *)(LPBC))v59->lpVtbl->Release)(v59);
  }
  ILFree(pidl);
  v60 = v79;
  v78 = &CUString::`vftable';
  v61 = v79 != 0;
  if ( v79 || v80 != 11 )
  {
    if ( pbstr[0] )
    {
      SysFreeString(pbstr[0]);
      v60 = v79;
      pbstr[0] = 0;
    }
    pbstr[1] = 0;
    v82 = 0;
    if ( v61 )
    {
      if ( v60 )
        ((void (__fastcall *)(struct IUri *))v60->lpVtbl->Release)(v60);
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18004e60c  push    rbp
0x18004e60e  push    rbx
0x18004e60f  push    rsi
0x18004e610  push    rdi
0x18004e611  push    r12
0x18004e613  push    r13
0x18004e615  push    r14
0x18004e617  push    r15
0x18004e619  lea     rbp, [rsp-2128h]
0x18004e621  mov     eax, 2228h
0x18004e626  call    _alloca_probe
0x18004e62b  sub     rsp, rax
0x18004e62e  mov     rax, cs:__security_cookie
0x18004e635  xor     rax, rsp
0x18004e638  mov     [rbp+2160h+var_50], rax
0x18004e63f  mov     rax, [rbp+2160h+arg_28]
0x18004e646  xor     edi, edi
0x18004e648  mov     r12, r9
0x18004e64b  mov     [rbp+2160h+var_21D0], rax
0x18004e64f  mov     rsi, rdx
0x18004e652  mov     rax, [rbp+2160h+arg_30]
0x18004e659  mov     r15, rcx
0x18004e65c  mov     [rbp+2160h+var_2190], rax
0x18004e660  mov     rax, [rbp+2160h+arg_20]
0x18004e667  mov     [rsp+2260h+var_21E8], rax
0x18004e66c  mov     rax, [rbp+2160h+arg_38]
0x18004e673  mov     qword ptr [rbp+2160h+reserved], rax
0x18004e677  mov     rax, [rbp+2160h+arg_40]
0x18004e67e  mov     [rsp+2260h+var_21F8], rax
0x18004e683  mov     [rsp+2260h+ppURI], r9
0x18004e688  mov     qword ptr [rsp+2260h+pcchPath], r8
0x18004e68d  mov     [rsp+2260h+var_2208], rcx
0x18004e692  cmp     [rcx+1B8h], rdi
0x18004e699  jz      loc_18004F333
0x18004e69f  test    rdx, rdx
0x18004e6a2  jz      loc_18004F333
0x18004e6a8  mov     rax, [rdx]
0x18004e6ab  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x18004e6b2  xorps   xmm0, xmm0
0x18004e6b5  mov     [rbp+2160h+var_21C0], r14
0x18004e6b9  lea     r8, [rsp+2260h+var_2200]
0x18004e6be  mov     [rbp+2160h+var_21B8], rdi
0x18004e6c2  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18004e6c9  mov     [rbp+2160h+var_2198], edi
0x18004e6cc  mov     rax, [rax]
0x18004e6cf  mov     rcx, rsi
0x18004e6d2  movdqu  xmmword ptr [rbp+2160h+pbstr], xmm0
0x18004e6d7  mov     [rbp+2160h+var_21B0], edi
0x18004e6da  mov     [rsp+2260h+var_2200], rdi
0x18004e6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6e4  mov     edx, [rbp+2160h+var_21B0]
0x18004e6e7  test    eax, eax
0x18004e6e9  js      loc_18004E7A6
0x18004e6ef  mov     rcx, [rsp+2260h+var_2200]
0x18004e6f4  lea     r9, [rbp+2160h+var_2198]
0x18004e6f8  lea     r8, [rbp+2160h+pbstr+8]
0x18004e6fc  mov     rax, [rcx]
0x18004e6ff  mov     rax, [rax+0E0h]
0x18004e706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e70b  mov     rcx, [rsp+2260h+var_2200]
0x18004e710  mov     ebx, eax
0x18004e712  mov     rax, [rcx]
0x18004e715  mov     rax, [rax+10h]
0x18004e719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e71e  test    ebx, ebx
0x18004e720  js      short loc_18004E735
0x18004e722  mov     [rbp+2160h+var_21B8], rsi
0x18004e726  mov     rcx, rsi
0x18004e729  mov     rax, [rsi]
0x18004e72c  mov     rax, [rax+8]
0x18004e730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e735  cmp     ebx, 1
0x18004e738  jnz     short loc_18004E74C
0x18004e73a  lea     r8d, [rbx+0Ah]; enum __MIDL_IUri_0001
0x18004e73e  mov     rdx, rsi; struct IUri *
0x18004e741  lea     rcx, [rbp+2160h+var_21C0]; this
0x18004e745  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x18004e74a  mov     ebx, eax
0x18004e74c  xor     r10d, r10d
0x18004e74f  test    ebx, ebx
0x18004e751  jnz     loc_18004F2D0
0x18004e757  cmp     [rbp+2160h+var_2198], r10d
0x18004e75b  jz      loc_18004F2D0
0x18004e761  mov     rax, [rsp+2260h+var_21E8]
0x18004e766  lea     ecx, [r10+8]
0x18004e76a  mov     [rbp+2160h+pidl], r10
0x18004e76e  mov     r14d, r10d
0x18004e771  mov     [rbp+2160h+ppbc], r10
0x18004e775  mov     r13d, r10d
0x18004e778  mov     [rbp+2160h+ppvData], r10
0x18004e77c  mov     ebx, 80004005h
0x18004e781  mov     [rsp+2260h+var_21F0], r10d
0x18004e786  mov     edx, 4008h
0x18004e78b  mov     [rbp+2160h+var_2168], r10
0x18004e78f  test    rax, rax
0x18004e792  jz      loc_18004EA05
0x18004e798  cmp     dx, [rax]
0x18004e79b  jnz     short loc_18004E7E2
0x18004e79d  mov     rax, [rax+8]
0x18004e7a1  mov     r13, [rax]
0x18004e7a4  jmp     short loc_18004E7EF
0x18004e7a6  mov     rax, [rsi]
0x18004e7a9  lea     r8, [rbp+2160h+pbstr]
0x18004e7ad  xor     r9d, r9d
0x18004e7b0  mov     rcx, rsi
0x18004e7b3  mov     rax, [rax+18h]
0x18004e7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7bc  mov     ebx, eax
0x18004e7be  test    eax, eax
0x18004e7c0  js      loc_18004E71E
0x18004e7c6  mov     rcx, [rbp+2160h+pbstr]; pbstr
0x18004e7ca  mov     [rbp+2160h+pbstr+8], rcx
0x18004e7ce  call    cs:__imp_SysStringLen
0x18004e7d5  nop     dword ptr [rax+rax+00h]
0x18004e7da  mov     [rbp+2160h+var_2198], eax
0x18004e7dd  jmp     loc_18004E722
0x18004e7e2  cmp     cx, [rax]
0x18004e7e5  jnz     loc_18004EA05
0x18004e7eb  mov     r13, [rax+8]
0x18004e7ef  test    r13, r13
0x18004e7f2  jz      loc_18004EA05
0x18004e7f8  cmp     [r13+0], r10w
0x18004e7fd  jz      loc_18004EA05
0x18004e803  lea     rcx, [r15+0D0h]; punk
0x18004e80a  mov     [rbp+2160h+ppvOut], r10
0x18004e80e  lea     r9, [rbp+2160h+ppvOut]; ppvOut
0x18004e812  mov     [rbp+2160h+var_2180], r10
0x18004e816  lea     r8, _GUID_86d52e11_94a8_11d0_82af_00c04fd5ae38; riid
0x18004e81d  mov     [rbp+2160h+var_2178], r10
0x18004e821  lea     rdx, IID_ITargetFrame2; guidService
0x18004e828  call    cs:__imp_IUnknown_QueryService
0x18004e82f  nop     dword ptr [rax+rax+00h]
0x18004e834  xor     r10d, r10d
0x18004e837  mov     ebx, eax
0x18004e839  test    eax, eax
0x18004e83b  js      loc_18004EA05
0x18004e841  lea     ebx, [r10+2]
0x18004e845  mov     rcx, r13; psz1
0x18004e848  mov     r8d, ebx; nChar
0x18004e84b  lea     rdx, asc_18061A758; "_["
0x18004e852  call    cs:__imp_StrCmpNW
0x18004e859  nop     dword ptr [rax+rax+00h]
0x18004e85e  xor     r10d, r10d
0x18004e861  test    eax, eax
0x18004e863  jnz     short loc_18004E8AE
0x18004e865  lea     edx, [rbx+5Bh]; wMatch
0x18004e868  mov     rcx, r13; pszStart
0x18004e86b  call    cs:__imp_StrChrW
0x18004e872  nop     dword ptr [rax+rax+00h]
0x18004e877  xor     r10d, r10d
0x18004e87a  mov     [rbp+2160h+var_2168], rax
0x18004e87e  test    rax, rax
0x18004e881  jz      short loc_18004E8AE
0x18004e883  add     rax, rbx
0x18004e886  mov     rcx, rax; psz
0x18004e889  mov     [rbp+2160h+var_2168], rax
0x18004e88d  call    cs:__imp_SysAllocString
0x18004e894  nop     dword ptr [rax+rax+00h]
0x18004e899  xor     r10d, r10d
0x18004e89c  mov     r13, rax
0x18004e89f  test    rax, rax
0x18004e8a2  jnz     short loc_18004E8AE
0x18004e8a4  mov     ebx, 8007000Eh
0x18004e8a9  jmp     loc_18004F20F
0x18004e8ae  mov     rcx, [rbp+2160h+ppvOut]
0x18004e8b2  lea     r9, [rbp+2160h+var_2180]
0x18004e8b6  mov     r8d, 1
0x18004e8bc  mov     [rsp+2260h+var_2220], r10d
0x18004e8c1  mov     rdx, r13
0x18004e8c4  mov     rax, [rcx]
0x18004e8c7  mov     rax, [rax+68h]
0x18004e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8d0  mov     ebx, eax
0x18004e8d2  xor     eax, eax
0x18004e8d4  test    ebx, ebx
0x18004e8d6  js      loc_18004E9E7
0x18004e8dc  mov     rcx, [rbp+2160h+var_2180]
0x18004e8e0  test    rcx, rcx
0x18004e8e3  jz      loc_18004E9C1
0x18004e8e9  mov     rax, [rcx]
0x18004e8ec  lea     r8, [rbp+2160h+var_2178]
0x18004e8f0  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x18004e8f7  mov     rax, [rax]
0x18004e8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8ff  mov     rcx, [rbp+2160h+var_2180]
0x18004e903  mov     ebx, eax
0x18004e905  mov     rax, [rcx]
0x18004e908  mov     rax, [rax+10h]
0x18004e90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e911  xor     ecx, ecx
0x18004e913  test    ebx, ebx
0x18004e915  js      loc_18004E9E7
0x18004e91b  xor     eax, eax
0x18004e91d  xorps   xmm0, xmm0
0x18004e920  movups  xmmword ptr [rbp+2160h+pvarg], xmm0
0x18004e924  mov     qword ptr [rbp+2160h+pvarg+10h], rax
0x18004e928  lea     eax, [rcx+8]
0x18004e92b  mov     qword ptr [rbp+2160h+pvarg+8], rcx
0x18004e92f  mov     rcx, [rbp+2160h+pbstr+8]; psz
0x18004e933  mov     word ptr [rbp+2160h+pvarg], ax
0x18004e937  call    cs:__imp_SysAllocString
0x18004e93e  nop     dword ptr [rax+rax+00h]
0x18004e943  xor     r10d, r10d
0x18004e946  mov     r15, rax
0x18004e949  test    rax, rax
0x18004e94c  jz      loc_18004F20F
0x18004e952  mov     r10, [rbp+2160h+var_2178]
0x18004e956  lea     r9, [rbp+2160h+pvarg]
0x18004e95a  mov     r8, r12
0x18004e95d  mov     rdx, r15
0x18004e960  mov     rcx, [r10]
0x18004e963  mov     rax, [rcx+58h]
0x18004e967  mov     rcx, [rbp+2160h+var_2190]
0x18004e96b  mov     [rsp+2260h+var_2238], rcx
0x18004e970  mov     rcx, [rbp+2160h+var_21D0]
0x18004e974  mov     [rsp+2260h+varIn], rcx
0x18004e979  mov     rcx, r10
0x18004e97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e981  lea     rcx, [rbp+2160h+pvarg]; pvarg
0x18004e985  mov     ebx, eax
0x18004e987  call    cs:__imp_VariantClear
0x18004e98e  nop     dword ptr [rax+rax+00h]
0x18004e993  mov     rcx, r15; bstrString
0x18004e996  call    cs:__imp_SysFreeString
0x18004e99d  nop     dword ptr [rax+rax+00h]
0x18004e9a2  mov     rcx, [rbp+2160h+var_2178]
0x18004e9a6  mov     rax, [rcx]
0x18004e9a9  mov     rax, [rax+10h]
0x18004e9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9b2  mov     r15, [rsp+2260h+var_2208]
0x18004e9b7  mov     [rsp+2260h+var_2220], 1
0x18004e9bf  jmp     short loc_18004E9E7
0x18004e9c1  test    r13, r13
0x18004e9c4  jz      short loc_18004E9CD
0x18004e9c6  cmp     [r13+0], ax
0x18004e9cb  jnz     short loc_18004E9D4
0x18004e9cd  lea     r13, aDesktop; "_desktop"
0x18004e9d4  mov     r14d, 2
0x18004e9da  mov     [rsp+2260h+var_21F0], 1
0x18004e9e2  mov     ebx, 80004005h
0x18004e9e7  mov     rcx, [rbp+2160h+ppvOut]
0x18004e9eb  mov     rax, [rcx]
0x18004e9ee  mov     rax, [rax+10h]
0x18004e9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9f7  xor     r10d, r10d
0x18004e9fa  cmp     [rsp+2260h+var_2220], r10d
0x18004e9ff  jnz     loc_18004F20F
0x18004ea05  mov     [rsp+2260h+var_2200], r10
0x18004ea0a  mov     r9, r10
0x18004ea0d  test    ebx, ebx
0x18004ea0f  jns     short loc_18004EA56
0x18004ea11  mov     rax, qword ptr [rsp+2260h+pcchPath]
0x18004ea16  test    rax, rax
0x18004ea19  jz      short loc_18004EA25
0x18004ea1b  mov     r9, rax
0x18004ea1e  mov     [rsp+2260h+var_2200], rax
0x18004ea23  jmp     short loc_18004EA56
0x18004ea25  mov     r9, [rsp+2260h+var_21F8]; unsigned __int16 *
0x18004ea2a  lea     rax, [rbp+2160h+pidl]
0x18004ea2e  mov     r8, rsi; struct IUri *
0x18004ea31  mov     [rsp+2260h+varIn], rax; struct _ITEMIDLIST_ABSOLUTE **
0x18004ea36  xor     edx, edx; unsigned int
0x18004ea38  mov     rcx, r15; this
0x18004ea3b  call    ?_PidlFromIUriEtc@CIEFrameAuto@@IEAAJIPEAUIUri@@PEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CIEFrameAuto::_PidlFromIUriEtc(uint,IUri *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x18004ea40  xor     r10d, r10d
0x18004ea43  mov     ebx, eax
0x18004ea45  test    eax, eax
0x18004ea47  js      loc_18004F20F
0x18004ea4d  mov     r9, [rbp+2160h+pidl]
0x18004ea51  mov     [rsp+2260h+var_2200], r9
0x18004ea56  mov     rax, [rsp+2260h+ppURI]
0x18004ea5b  mov     r15d, r10d
0x18004ea5e  mov     r12d, r10d
0x18004ea61  mov     esi, r10d
0x18004ea64  mov     ecx, 3
0x18004ea69  test    rax, rax
0x18004ea6c  jz      loc_18004EB94
0x18004ea72  lea     ebx, [rcx-1]
0x18004ea75  cmp     [rax], cx
0x18004ea78  jnz     short loc_18004EA7F
0x18004ea7a  mov     esi, [rax+8]
0x18004ea7d  jmp     short loc_18004EA88
0x18004ea7f  cmp     [rax], bx
0x18004ea82  jnz     short loc_18004EA93
0x18004ea84  movsx   esi, word ptr [rax+8]
0x18004ea88  bt      esi, 8
0x18004ea8c  jnb     short loc_18004EA93
0x18004ea8e  bts     r14d, 1Fh
0x18004ea93  mov     edx, r14d
0x18004ea96  mov     r11d, 400h
0x18004ea9c  bts     edx, 19h
0x18004eaa0  mov     r8d, esi
0x18004eaa3  bt      esi, 9
0x18004eaa7  mov     eax, esi
0x18004eaa9  cmovnb  edx, r14d
0x18004eaad  mov     ecx, edx
0x18004eaaf  bts     ecx, 16h
0x18004eab3  test    r11d, esi
0x18004eab6  cmovz   ecx, edx
0x18004eab9  mov     edx, ecx
  ... truncated ...
```
