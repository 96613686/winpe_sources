# CIEFrameAuto::_NavigateHelper(IUri *,_ITEMIDLIST_ABSOLUTE *,tagVARIANT *,tagVARIANT const *,tagVARIANT *,tagVARIANT *,IBindCtx *,ushort *,long *)

- ea: `0x180028b74`
- end: `0x180029868`
- name: `?_NavigateHelper@CIEFrameAuto@@IEAAJPEAUIUri@@PEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagVARIANT@@PEBU4@22PEAUIBindCtx@@PEAGPEAJ@Z`
- size: `3316`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, struct IUri *, struct _ITEMIDLIST_ABSOLUTE *, struct tagVARIANT *, const struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct IBindCtx *, unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028960`
- `0x180105e70`
- `0x180105fd0`
- `0x180106040`

## callees

- `0x18000b9e0`
- `0x1800116ac`
- `0x180028b74`
- `0x18002acc0`
- `0x180053590`
- `0x18005b4b0`
- `0x180071248`
- `0x18007beb0`
- `0x18007dd70`
- `0x18008bdac`
- `0x1800b0e64`
- `0x1800b0f44`
- `0x1800b8f52`
- `0x1800f77fc`
- `0x1800f8788`
- `0x1801045f4`
- `0x180108cf0`
- `0x1801098c4`
- `0x180165044`
- `0x1803f4c14`
- `0x1804e3990`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180028dc1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180028dc1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNW` at `0x180028dae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNW` at `0x180028dae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18002961f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x18002961f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x180029678`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x180029678`
- `ole32!CreateBindCtx` at `0x1800296c1`
- `ole32!CreateBindCtx` at `0x1800296c1`
- `OLEAUT32!__imp_SysAllocString` at `0x180028ddd`
- `OLEAUT32!__imp_SysAllocString` at `0x180028e81`
- `OLEAUT32!__imp_SysAllocString` at `0x180028ddd`
- `OLEAUT32!__imp_SysAllocString` at `0x180028e81`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ed4`
- `OLEAUT32!__imp_SysFreeString` at `0x180029742`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180029812`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ed4`
- `OLEAUT32!__imp_SysFreeString` at `0x180029742`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180029812`
- `OLEAUT32!__imp_SysStringLen` at `0x180028d36`
- `OLEAUT32!__imp_SysStringLen` at `0x180028d36`
- `OLEAUT32!__imp_VariantClear` at `0x180028ecb`
- `OLEAUT32!__imp_VariantClear` at `0x180028ecb`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002945c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002945c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002944f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002944f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180029431`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180029431`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002972b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002972b`
- `SHELL32!__imp_ILFree` at `0x180029778`
- `SHELL32!__imp_ILFree` at `0x180029778`
- `iertutil!CreateUri` at `0x18002922d`
- `iertutil!CreateUri` at `0x18002922d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002917b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002917b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18002916c`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18002919c`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18002916c`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18002919c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180028d8a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180028d8a`

## string_xrefs

- `0x1800294fb`: `BIND_CONTEXT_CREATED_FOR_CALLERURL`

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
  char v37; // al
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
  char IsFrameSharedMemoryFlagSetForCurrentThread; // [rsp+40h] [rbp-C0h]
  int v68; // [rsp+44h] [rbp-BCh] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath[2]; // [rsp+50h] [rbp-B0h] BYREF
  CIEFrameAuto *v71; // [rsp+58h] [rbp-A8h]
  struct _ITEMIDLIST_ABSOLUTE *v72; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v73; // [rsp+68h] [rbp-98h] BYREF
  int v74; // [rsp+70h] [rbp-90h]
  VARIANT *v75; // [rsp+78h] [rbp-88h] BYREF
  LPBC ppbc; // [rsp+80h] [rbp-80h] BYREF
  struct tagVARIANT *v77; // [rsp+90h] [rbp-70h]
  int v78; // [rsp+98h] [rbp-68h]
  void **v79; // [rsp+A0h] [rbp-60h] BYREF
  struct IUri *v80; // [rsp+A8h] [rbp-58h]
  unsigned int v81; // [rsp+B0h] [rbp-50h]
  BSTR pbstr[2]; // [rsp+B8h] [rbp-48h] BYREF
  UINT v83; // [rsp+C8h] [rbp-38h] BYREF
  struct tagVARIANT *v84; // [rsp+D0h] [rbp-30h]
  void *ppvData; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v86; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v87; // [rsp+E8h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+F0h] [rbp-10h] BYREF
  PWSTR v89; // [rsp+F8h] [rbp-8h]
  LPITEMIDLIST pidl; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  DWORD reserved[2]; // [rsp+130h] [rbp+30h]
  _OWORD v93[3]; // [rsp+138h] [rbp+38h] BYREF
  int v94; // [rsp+168h] [rbp+68h]
  WCHAR pszPath[2]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v96[4172]; // [rsp+174h] [rbp+74h] BYREF
  WCHAR pwzURI[2088]; // [rsp+11C0h] [rbp+10C0h] BYREF

  v10 = 0;
  v77 = a6;
  v13 = this;
  v84 = a7;
  v75 = a5;
  *(_QWORD *)reserved = a8;
  v73 = a9;
  ppURI = a4;
  *(_QWORD *)pcchPath = a3;
  v71 = this;
  if ( !*((_QWORD *)this + 55) || !a2 )
    return 2147500037LL;
  lpVtbl = a2->lpVtbl;
  v79 = &CUString::`vftable';
  v80 = 0;
  v83 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)pbstr = 0;
  v81 = 0;
  v72 = 0;
  if ( ((int (__fastcall *)(struct IUri *, GUID *, struct _ITEMIDLIST_ABSOLUTE **))QueryInterface)(
         a2,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v72) >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *, _QWORD, BSTR *, UINT *))(*(_QWORD *)v72 + 224LL))(
            v72,
            v81,
            &pbstr[1],
            &v83);
    (*(void (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *))(*(_QWORD *)v72 + 16LL))(v72);
    goto LABEL_5;
  }
  v16 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))a2->lpVtbl->GetPropertyBSTR)(a2, v81, pbstr, 0);
  if ( v16 < 0 )
  {
LABEL_5:
    if ( v16 < 0 )
      goto LABEL_7;
    goto LABEL_6;
  }
  pbstr[1] = pbstr[0];
  v83 = SysStringLen(pbstr[0]);
LABEL_6:
  v80 = a2;
  ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
LABEL_7:
  if ( v16 == 1 )
    v16 = CUString::Set((CUString *)&v79, a2, Uri_PROPERTY_RAW_URI);
  if ( v16 || !v83 )
  {
    v63 = v80;
    v79 = &CUString::`vftable';
    v64 = v80 != 0;
    if ( v80 || v81 != 11 )
    {
      if ( pbstr[0] )
      {
        SysFreeString(pbstr[0]);
        v63 = v80;
        pbstr[0] = 0;
      }
      pbstr[1] = 0;
      v83 = 0;
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
  v74 = 0;
  v89 = 0;
  if ( !v75 )
    goto LABEL_34;
  if ( v75->vt == 16392 )
  {
    llVal = *v75->pllVal;
  }
  else
  {
    if ( v75->vt != 8 )
      goto LABEL_34;
    llVal = v75->llVal;
  }
  if ( llVal )
  {
    if ( *(_WORD *)llVal )
    {
      ppvOut = 0;
      v86 = 0;
      v87 = 0;
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
          v89 = v20;
          if ( v20 )
          {
            v89 = v20 + 1;
            llVal = (LONGLONG)SysAllocString(v20 + 1);
            if ( !llVal )
            {
              v19 = -2147024882;
              goto LABEL_162;
            }
          }
        }
        v68 = 0;
        v19 = (*(__int64 (__fastcall **)(void *, LONGLONG, __int64, __int64 *))(*(_QWORD *)ppvOut + 104LL))(
                ppvOut,
                llVal,
                1,
                &v86);
        if ( v19 >= 0 )
        {
          if ( v86 )
          {
            v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v86)(
                    v86,
                    &GUID_0002df05_0000_0000_c000_000000000046,
                    &v87);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
            if ( v19 >= 0 )
            {
              *(_OWORD *)&pvarg.decVal.Lo32 = 0u;
              *(_QWORD *)&pvarg.vt = 8;
              v21 = SysAllocString(pbstr[1]);
              v22 = v21;
              if ( !v21 )
                goto LABEL_162;
              v19 = (*(__int64 (__fastcall **)(__int64, BSTR, IUri *, VARIANTARG *, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)v87 + 88LL))(
                      v87,
                      v21,
                      a4,
                      &pvarg,
                      v77,
                      v84);
              VariantClear(&pvarg);
              SysFreeString(v22);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
              v13 = v71;
              v68 = 1;
            }
          }
          else
          {
            if ( !*(_WORD *)llVal )
              llVal = (LONGLONG)L"_desktop";
            v17 = 2;
            v74 = 1;
            v19 = -2147467259;
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        if ( v68 )
          goto LABEL_162;
      }
    }
  }
LABEL_34:
  v72 = 0;
  v23 = 0;
  if ( v19 < 0 )
  {
    if ( *(_QWORD *)pcchPath )
    {
      v23 = *(void **)pcchPath;
      v72 = *(struct _ITEMIDLIST_ABSOLUTE **)pcchPath;
    }
    else
    {
      v19 = CIEFrameAuto::_PidlFromIUriEtc(v13, 0, a2, v73, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( v19 < 0 )
        goto LABEL_162;
      v23 = pidl;
      v72 = (struct _ITEMIDLIST_ABSOLUTE *)pidl;
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
  v68 = (int)v33;
  if ( (lpVtbl_low & 0x10) == 0 )
  {
    if ( a10 )
    {
      v34 = v71;
      if ( *a10 != -2146697203
        || (int)_GetSearchInfo(*((struct IServiceProvider **)v71 + 61), 0, &v68, 0, v33) < 0
        || !v68 )
      {
        goto LABEL_74;
      }
      goto LABEL_72;
    }
LABEL_73:
    v34 = v71;
    goto LABEL_74;
  }
  v34 = v71;
LABEL_72:
  v17 |= 0x20000000u;
LABEL_74:
  v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, WCHAR *, __int64))(**((_QWORD **)v34 + 55)
                                                                                           + 80LL))(
          *((_QWORD *)v34 + 55),
          v72,
          pwzURI,
          0x8000);
  if ( v19 < 0 )
    goto LABEL_162;
  LODWORD(v73) = 0;
  *(_QWORD *)pcchPath = 0;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, DWORD *))v71 + 55))(
         *((_QWORD *)v71 + 55),
         &GUID_6bd38a1c_7310_4e76_8567_927d8f72ef27,
         pcchPath) >= 0 )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)pcchPath + 64LL))(*(_QWORD *)pcchPath, &v73);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pcchPath);
  if ( (_DWORD)v73 )
  {
LABEL_110:
    v41 = 0;
    v73 = 0;
    v42 = 0;
    if ( v84 )
    {
      if ( v84->vt == 16392 )
      {
        bstrVal = (unsigned __int16 *)*v84->pllVal;
LABEL_115:
        v73 = bstrVal;
        goto LABEL_116;
      }
      if ( v84->vt == 8 )
      {
        bstrVal = v84->bstrVal;
        goto LABEL_115;
      }
    }
LABEL_116:
    if ( v77 && (v77->vt & 0x2000) != 0 )
    {
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v77->llVal;
      if ( (v77->vt & 0x4000) != 0 )
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
    if ( !v73 && !ppvData && (v17 & 0x20000022) == 0 && !v24 && !v25 )
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
        v75 = 0;
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANT **))(v51 + 80))(
               *(_QWORD *)reserved,
               L"BIND_CONTEXT_CREATED_FOR_CALLERURL",
               &v75) >= 0 )
          (*(void (__fastcall **)(VARIANT *))(*(_QWORD *)&v75->vt + 16LL))(v75);
        else
          CIEFrameAuto::_SetPendingNavigateContext(v71, v50, 0);
      }
      v52 = CIEFrameAuto::_BrowseObject(v71, v72, v48);
      goto LABEL_141;
    }
    v53 = -((*((_DWORD *)v71 + 119) & 1) != 0);
    LOWORD(ppURI) = -((*((_DWORD *)v71 + 119) & 2) != 0);
    v75 = (VARIANT *)ppvData;
    v54 = operator new(0x48u);
    if ( v54 )
    {
      v78 = 0;
      LOWORD(v66) = (_WORD)ppURI;
      v77 = (struct tagVARIANT *)__PAIR64__(v25, v24);
      LOWORD(varIn) = v53;
      v10 = (struct IBindStatusCallback *)CStubBindStatusCallbackEx::CStubBindStatusCallbackEx(
                                            v54,
                                            v73,
                                            v75,
                                            v42,
                                            varIn,
                                            v66);
      if ( v10 )
      {
        v55 = v71;
        v56 = v72;
        pcchPath[0] = 2087;
        v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, WCHAR *, __int64))(**((_QWORD **)v71 + 55)
                                                                                                 + 80LL))(
                *((_QWORD *)v71 + 55),
                v72,
                pszPath,
                0x8000);
        if ( v19 >= 0
          || PathCreateFromUrlW(pbstr[1], pszPath, pcchPath, 0) >= 0
          && pszPath[0] == 92
          && pszPath[1] == 92
          && (v19 = (*(__int64 (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE *, _BYTE *, __int64))(**((_QWORD **)v55 + 55) + 80LL))(
                      *((_QWORD *)v55 + 55),
                      v56,
                      v96,
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
LABEL_157:
            v49 = v74 != 0;
            v74 = -v74;
            v52 = CIEFrameAuto::NavigateHack(
                    (CIEFrameAuto *)((char *)v55 + 104),
                    v17,
                    ppbc,
                    v10,
                    (const unsigned __int16 *)(llVal & -(__int64)v49),
                    pszPath,
                    LocationW);
LABEL_141:
            v19 = v52;
            goto LABEL_160;
          }
          v19 = CreateBindCtx(0, &ppbc);
          if ( v19 >= 0 )
            goto LABEL_157;
        }
LABEL_160:
        if ( v41 )
          SafeArrayUnaccessData(v41);
        goto LABEL_162;
      }
    }
    else
    {
      v10 = 0;
    }
    v19 = -2147024882;
    goto LABEL_160;
  }
  v68 = 0;
  IsFrameSharedMemoryFlagSetForCurrentThread = 0;
  if ( IsDualEngineProcess() && (unsigned __int8)IEConfiguration_GetBool(268435541) )
    IsFrameSharedMemoryFlagSetForCurrentThread = DualEngine::Internal::IsFrameSharedMemoryFlagSetForCurrentThread(256);
  pcchPath[0] = DualEngine::GetEngineSwitchingPolicyFlags();
  if ( IsDualEngineProcess() )
    v37 = DualEngine::Internal::IsFrameSharedMemoryFlagSetForCurrentThread(128);
  else
    v37 = 0;
  LOBYTE(v36) = IsFrameSharedMemoryFlagSetForCurrentThread;
  LOBYTE(v35) = v37;
  if ( (unsigned __int8)DualEngine::ShouldUrlContinueNavigationInEdge(pwzURI, v35, pcchPath[0], v36) )
  {
    v38 = 0;
    if ( v84 )
    {
      if ( v84->vt == 16392 )
      {
        v38 = (const unsigned __int16 *)*v84->pllVal;
      }
      else if ( v84->vt == 8 )
      {
        v38 = v84->bstrVal;
      }
    }
    DualEngine::NavigationParams::NavigationParams((DualEngine::NavigationParams *)&pvarg, 0, v38, v77);
    ppURI = 0;
    if ( CreateUri(pwzURI, 0x3002B84u, 0, &ppURI) >= 0 )
    {
      *(_QWORD *)pcchPath = 0;
      if ( CIEFrameAuto::QueryService(
             (CIEFrameAuto *)((char *)v71 + 72),
             (const struct _GUID *)&SID_SDualEngineService,
             &GUID_5c96475e_66b9_48dd_a1bc_0bb3bc7b4010,
             (void **)pcchPath) >= 0 )
      {
        if ( (v17 & 2) != 0 )
        {
          v94 = 0;
          memset(v93, 0, sizeof(v93));
          if ( (lpVtbl_low & 0x300000) != 0 )
            LODWORD(v93[0]) = (unsigned int)ShouldOpenInNewWindow((lpVtbl_low & 0x200000) != 0 ? 0x80000 : 0x40000, v39) != 0
                            ? 3
                            : 0;
          else
            LODWORD(v93[0]) = (lpVtbl_low & 1) != 0 ? 3 : 0;
          (*(void (__fastcall **)(_QWORD, IUri *, _OWORD *, VARIANTARG *))(**(_QWORD **)pcchPath + 32LL))(
            *(_QWORD *)pcchPath,
            ppURI,
            v93,
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
        v68 = 1;
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pcchPath);
    }
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
    DualEngine::NavigationParams::~NavigationParams((DualEngine::NavigationParams *)&pvarg);
    if ( v68 )
      goto LABEL_162;
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
  v40 = CIEFrameAuto::_HandleProtectedModeRedirect(v71, pwzURI, v72, &pvarg, v75, v77, v84);
  v19 = v40;
  if ( !v40 )
    goto LABEL_162;
  if ( v40 == -2147023286 )
  {
    v19 = 0;
  }
  else if ( v40 < 0 )
  {
    goto LABEL_162;
  }
  if ( !v68 )
    goto LABEL_110;
LABEL_162:
  if ( v89 && llVal )
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
  v60 = v80;
  v79 = &CUString::`vftable';
  v61 = v80 != 0;
  if ( v80 || v81 != 11 )
  {
    if ( pbstr[0] )
    {
      SysFreeString(pbstr[0]);
      v60 = v80;
      pbstr[0] = 0;
    }
    pbstr[1] = 0;
    v83 = 0;
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
0x180028b74  push    rbp
0x180028b76  push    rbx
0x180028b77  push    rsi
0x180028b78  push    rdi
0x180028b79  push    r12
0x180028b7b  push    r13
0x180028b7d  push    r14
0x180028b7f  push    r15
0x180028b81  lea     rbp, [rsp-2128h]
0x180028b89  mov     eax, 2228h
0x180028b8e  call    _alloca_probe
0x180028b93  sub     rsp, rax
0x180028b96  mov     rax, cs:__security_cookie
0x180028b9d  xor     rax, rsp
0x180028ba0  mov     [rbp+2160h+var_50], rax
0x180028ba7  mov     rax, [rbp+2160h+arg_28]
0x180028bae  xor     edi, edi
0x180028bb0  mov     r12, r9
0x180028bb3  mov     [rbp+2160h+var_21D0], rax
0x180028bb7  mov     rsi, rdx
0x180028bba  mov     rax, [rbp+2160h+arg_30]
0x180028bc1  mov     r15, rcx
0x180028bc4  mov     [rbp+2160h+var_2190], rax
0x180028bc8  mov     rax, [rbp+2160h+arg_20]
0x180028bcf  mov     [rsp+2260h+var_21E8], rax
0x180028bd4  mov     rax, [rbp+2160h+arg_38]
0x180028bdb  mov     qword ptr [rbp+2160h+reserved], rax
0x180028bdf  mov     rax, [rbp+2160h+arg_40]
0x180028be6  mov     [rsp+2260h+var_21F8], rax
0x180028beb  mov     [rsp+2260h+ppURI], r9
0x180028bf0  mov     qword ptr [rsp+2260h+pcchPath], r8
0x180028bf5  mov     [rsp+2260h+var_2208], rcx
0x180028bfa  cmp     [rcx+1B8h], rdi
0x180028c01  jz      loc_180029840
0x180028c07  test    rdx, rdx
0x180028c0a  jz      loc_180029840
0x180028c10  mov     rax, [rdx]
0x180028c13  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180028c1a  xorps   xmm0, xmm0
0x180028c1d  mov     [rbp+2160h+var_21C0], r14
0x180028c21  lea     r8, [rsp+2260h+var_2200]
0x180028c26  mov     [rbp+2160h+var_21B8], rdi
0x180028c2a  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x180028c31  mov     [rbp+2160h+var_2198], edi
0x180028c34  mov     rax, [rax]
0x180028c37  mov     rcx, rsi
0x180028c3a  movdqu  xmmword ptr [rbp+2160h+pbstr], xmm0
0x180028c3f  mov     [rbp+2160h+var_21B0], edi
0x180028c42  mov     [rsp+2260h+var_2200], rdi
0x180028c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c4c  mov     edx, [rbp+2160h+var_21B0]
0x180028c4f  test    eax, eax
0x180028c51  js      loc_180028D0E
0x180028c57  mov     rcx, [rsp+2260h+var_2200]
0x180028c5c  lea     r9, [rbp+2160h+var_2198]
0x180028c60  lea     r8, [rbp+2160h+pbstr+8]
0x180028c64  mov     rax, [rcx]
0x180028c67  mov     rax, [rax+0E0h]
0x180028c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c73  mov     rcx, [rsp+2260h+var_2200]
0x180028c78  mov     ebx, eax
0x180028c7a  mov     rax, [rcx]
0x180028c7d  mov     rax, [rax+10h]
0x180028c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c86  test    ebx, ebx
0x180028c88  js      short loc_180028C9D
0x180028c8a  mov     [rbp+2160h+var_21B8], rsi
0x180028c8e  mov     rcx, rsi
0x180028c91  mov     rax, [rsi]
0x180028c94  mov     rax, [rax+8]
0x180028c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c9d  cmp     ebx, 1
0x180028ca0  jnz     short loc_180028CB4
0x180028ca2  lea     r8d, [rbx+0Ah]; enum __MIDL_IUri_0001
0x180028ca6  mov     rdx, rsi; struct IUri *
0x180028ca9  lea     rcx, [rbp+2160h+var_21C0]; this
0x180028cad  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180028cb2  mov     ebx, eax
0x180028cb4  xor     r10d, r10d
0x180028cb7  test    ebx, ebx
0x180028cb9  jnz     loc_1800297E3
0x180028cbf  cmp     [rbp+2160h+var_2198], r10d
0x180028cc3  jz      loc_1800297E3
0x180028cc9  mov     rax, [rsp+2260h+var_21E8]
0x180028cce  lea     ecx, [r10+8]
0x180028cd2  mov     [rbp+2160h+pidl], r10
0x180028cd6  mov     r14d, r10d
0x180028cd9  mov     [rbp+2160h+ppbc], r10
0x180028cdd  mov     r13d, r10d
0x180028ce0  mov     [rbp+2160h+ppvData], r10
0x180028ce4  mov     ebx, 80004005h
0x180028ce9  mov     [rsp+2260h+var_21F0], r10d
0x180028cee  mov     edx, 4008h
0x180028cf3  mov     [rbp+2160h+var_2168], r10
0x180028cf7  test    rax, rax
0x180028cfa  jz      loc_180028F3D
0x180028d00  cmp     dx, [rax]
0x180028d03  jnz     short loc_180028D44
0x180028d05  mov     rax, [rax+8]
0x180028d09  mov     r13, [rax]
0x180028d0c  jmp     short loc_180028D51
0x180028d0e  mov     rax, [rsi]
0x180028d11  lea     r8, [rbp+2160h+pbstr]
0x180028d15  xor     r9d, r9d
0x180028d18  mov     rcx, rsi
0x180028d1b  mov     rax, [rax+18h]
0x180028d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d24  mov     ebx, eax
0x180028d26  test    eax, eax
0x180028d28  js      loc_180028C86
0x180028d2e  mov     rcx, [rbp+2160h+pbstr]; pbstr
0x180028d32  mov     [rbp+2160h+pbstr+8], rcx
0x180028d36  call    cs:__imp_SysStringLen
0x180028d3c  mov     [rbp+2160h+var_2198], eax
0x180028d3f  jmp     loc_180028C8A
0x180028d44  cmp     cx, [rax]
0x180028d47  jnz     loc_180028F3D
0x180028d4d  mov     r13, [rax+8]
0x180028d51  test    r13, r13
0x180028d54  jz      loc_180028F3D
0x180028d5a  cmp     [r13+0], r10w
0x180028d5f  jz      loc_180028F3D
0x180028d65  lea     rcx, [r15+0D0h]; punk
0x180028d6c  mov     [rbp+2160h+ppvOut], r10
0x180028d70  lea     r9, [rbp+2160h+ppvOut]; ppvOut
0x180028d74  mov     [rbp+2160h+var_2180], r10
0x180028d78  lea     r8, _GUID_86d52e11_94a8_11d0_82af_00c04fd5ae38; riid
0x180028d7f  mov     [rbp+2160h+var_2178], r10
0x180028d83  lea     rdx, IID_ITargetFrame2; guidService
0x180028d8a  call    cs:__imp_IUnknown_QueryService
0x180028d90  xor     r10d, r10d
0x180028d93  mov     ebx, eax
0x180028d95  test    eax, eax
0x180028d97  js      loc_180028F3D
0x180028d9d  lea     ebx, [r10+2]
0x180028da1  mov     rcx, r13; psz1
0x180028da4  mov     r8d, ebx; nChar
0x180028da7  lea     rdx, psz2; "_["
0x180028dae  call    cs:__imp_StrCmpNW
0x180028db4  xor     r10d, r10d
0x180028db7  test    eax, eax
0x180028db9  jnz     short loc_180028DF8
0x180028dbb  lea     edx, [rbx+5Bh]; wMatch
0x180028dbe  mov     rcx, r13; pszStart
0x180028dc1  call    cs:__imp_StrChrW
0x180028dc7  xor     r10d, r10d
0x180028dca  mov     [rbp+2160h+var_2168], rax
0x180028dce  test    rax, rax
0x180028dd1  jz      short loc_180028DF8
0x180028dd3  add     rax, rbx
0x180028dd6  mov     rcx, rax; psz
0x180028dd9  mov     [rbp+2160h+var_2168], rax
0x180028ddd  call    cs:__imp_SysAllocString
0x180028de3  xor     r10d, r10d
0x180028de6  mov     r13, rax
0x180028de9  test    rax, rax
0x180028dec  jnz     short loc_180028DF8
0x180028dee  mov     ebx, 8007000Eh
0x180028df3  jmp     loc_180029734
0x180028df8  mov     rcx, [rbp+2160h+ppvOut]
0x180028dfc  lea     r9, [rbp+2160h+var_2180]
0x180028e00  mov     r8d, 1
0x180028e06  mov     [rsp+2260h+var_221C], r10d
0x180028e0b  mov     rdx, r13
0x180028e0e  mov     rax, [rcx]
0x180028e11  mov     rax, [rax+68h]
0x180028e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e1a  mov     ebx, eax
0x180028e1c  xor     eax, eax
0x180028e1e  test    ebx, ebx
0x180028e20  js      loc_180028F1F
0x180028e26  mov     rcx, [rbp+2160h+var_2180]
0x180028e2a  test    rcx, rcx
0x180028e2d  jz      loc_180028EF9
0x180028e33  mov     rax, [rcx]
0x180028e36  lea     r8, [rbp+2160h+var_2178]
0x180028e3a  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x180028e41  mov     rax, [rax]
0x180028e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e49  mov     rcx, [rbp+2160h+var_2180]
0x180028e4d  mov     ebx, eax
0x180028e4f  mov     rax, [rcx]
0x180028e52  mov     rax, [rax+10h]
0x180028e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e5b  xor     ecx, ecx
0x180028e5d  test    ebx, ebx
0x180028e5f  js      loc_180028F1F
0x180028e65  xor     eax, eax
0x180028e67  xorps   xmm0, xmm0
0x180028e6a  movups  xmmword ptr [rbp+2160h+pvarg], xmm0
0x180028e6e  mov     qword ptr [rbp+2160h+pvarg+10h], rax
0x180028e72  lea     eax, [rcx+8]
0x180028e75  mov     qword ptr [rbp+2160h+pvarg+8], rcx
0x180028e79  mov     rcx, [rbp+2160h+pbstr+8]; psz
0x180028e7d  mov     word ptr [rbp+2160h+pvarg], ax
0x180028e81  call    cs:__imp_SysAllocString
0x180028e87  xor     r10d, r10d
0x180028e8a  mov     r15, rax
0x180028e8d  test    rax, rax
0x180028e90  jz      loc_180029734
0x180028e96  mov     r10, [rbp+2160h+var_2178]
0x180028e9a  lea     r9, [rbp+2160h+pvarg]
0x180028e9e  mov     r8, r12
0x180028ea1  mov     rdx, r15
0x180028ea4  mov     rcx, [r10]
0x180028ea7  mov     rax, [rcx+58h]
0x180028eab  mov     rcx, [rbp+2160h+var_2190]
0x180028eaf  mov     [rsp+2260h+var_2238], rcx
0x180028eb4  mov     rcx, [rbp+2160h+var_21D0]
0x180028eb8  mov     [rsp+2260h+varIn], rcx
0x180028ebd  mov     rcx, r10
0x180028ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ec5  lea     rcx, [rbp+2160h+pvarg]; pvarg
0x180028ec9  mov     ebx, eax
0x180028ecb  call    cs:__imp_VariantClear
0x180028ed1  mov     rcx, r15; bstrString
0x180028ed4  call    cs:__imp_SysFreeString
0x180028eda  mov     rcx, [rbp+2160h+var_2178]
0x180028ede  mov     rax, [rcx]
0x180028ee1  mov     rax, [rax+10h]
0x180028ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eea  mov     r15, [rsp+2260h+var_2208]
0x180028eef  mov     [rsp+2260h+var_221C], 1
0x180028ef7  jmp     short loc_180028F1F
0x180028ef9  test    r13, r13
0x180028efc  jz      short loc_180028F05
0x180028efe  cmp     [r13+0], ax
0x180028f03  jnz     short loc_180028F0C
0x180028f05  lea     r13, aDesktop; "_desktop"
0x180028f0c  mov     r14d, 2
0x180028f12  mov     [rsp+2260h+var_21F0], 1
0x180028f1a  mov     ebx, 80004005h
0x180028f1f  mov     rcx, [rbp+2160h+ppvOut]
0x180028f23  mov     rax, [rcx]
0x180028f26  mov     rax, [rax+10h]
0x180028f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f2f  xor     r10d, r10d
0x180028f32  cmp     [rsp+2260h+var_221C], r10d
0x180028f37  jnz     loc_180029734
0x180028f3d  mov     [rsp+2260h+var_2200], r10
0x180028f42  mov     r9, r10
0x180028f45  test    ebx, ebx
0x180028f47  jns     short loc_180028F8E
0x180028f49  mov     rax, qword ptr [rsp+2260h+pcchPath]
0x180028f4e  test    rax, rax
0x180028f51  jz      short loc_180028F5D
0x180028f53  mov     r9, rax
0x180028f56  mov     [rsp+2260h+var_2200], rax
0x180028f5b  jmp     short loc_180028F8E
0x180028f5d  mov     r9, [rsp+2260h+var_21F8]; unsigned __int16 *
0x180028f62  lea     rax, [rbp+2160h+pidl]
0x180028f66  mov     r8, rsi; struct IUri *
0x180028f69  mov     [rsp+2260h+varIn], rax; struct _ITEMIDLIST_ABSOLUTE **
0x180028f6e  xor     edx, edx; unsigned int
0x180028f70  mov     rcx, r15; this
0x180028f73  call    ?_PidlFromIUriEtc@CIEFrameAuto@@IEAAJIPEAUIUri@@PEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CIEFrameAuto::_PidlFromIUriEtc(uint,IUri *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x180028f78  xor     r10d, r10d
0x180028f7b  mov     ebx, eax
0x180028f7d  test    eax, eax
0x180028f7f  js      loc_180029734
0x180028f85  mov     r9, [rbp+2160h+pidl]
0x180028f89  mov     [rsp+2260h+var_2200], r9
0x180028f8e  mov     rax, [rsp+2260h+ppURI]
0x180028f93  mov     r15d, r10d
0x180028f96  mov     r12d, r10d
0x180028f99  mov     esi, r10d
0x180028f9c  mov     ecx, 3
0x180028fa1  test    rax, rax
0x180028fa4  jz      loc_1800290CC
0x180028faa  lea     ebx, [rcx-1]
0x180028fad  cmp     [rax], cx
0x180028fb0  jnz     short loc_180028FB7
0x180028fb2  mov     esi, [rax+8]
0x180028fb5  jmp     short loc_180028FC0
0x180028fb7  cmp     [rax], bx
0x180028fba  jnz     short loc_180028FCB
0x180028fbc  movsx   esi, word ptr [rax+8]
0x180028fc0  bt      esi, 8
0x180028fc4  jnb     short loc_180028FCB
0x180028fc6  bts     r14d, 1Fh
0x180028fcb  mov     edx, r14d
0x180028fce  mov     r11d, 400h
0x180028fd4  bts     edx, 19h
0x180028fd8  mov     r8d, esi
0x180028fdb  bt      esi, 9
0x180028fdf  mov     eax, esi
0x180028fe1  cmovnb  edx, r14d
0x180028fe5  mov     ecx, edx
0x180028fe7  bts     ecx, 16h
0x180028feb  test    r11d, esi
0x180028fee  cmovz   ecx, edx
0x180028ff1  mov     edx, ecx
0x180028ff3  or      edx, ebx
0x180028ff5  test    sil, 1
0x180028ff9  cmovz   edx, ecx
0x180028ffc  mov     ecx, edx
0x180028ffe  or      ecx, 20h
0x180029001  and     r8d, ebx
0x180029004  mov     ebx, 8
0x180029009  cmovz   ecx, edx
  ... truncated ...
```
