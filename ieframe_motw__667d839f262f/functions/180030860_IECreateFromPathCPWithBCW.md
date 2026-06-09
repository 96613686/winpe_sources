# IECreateFromPathCPWithBCW

- ea: `0x180030860`
- end: `0x1800312ff`
- name: `IECreateFromPathCPWithBCW`
- size: `2719`
- prototype: ``
- caller_count: `67`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c4f84`
- `0x1800c8cd0`
- `0x1800d7790`
- `0x1800d7b8c`
- `0x1800d95bc`
- `0x1800d9960`
- `0x1800face8`
- `0x18012e160`
- `0x18012ef54`
- `0x18013302c`
- `0x180145dd4`
- `0x18018bd10`
- `0x1801a4e64`
- `0x1801a7a98`
- `0x1801a7be0`
- `0x1801a8040`
- `0x1801c1c30`
- `0x1801e2408`
- `0x1801fafd0`
- `0x180201d50`
- `0x180202180`
- `0x180202ac0`
- `0x18020b7f0`
- `0x180211d30`
- `0x180238b00`
- `0x1802398c4`
- `0x18023ee78`
- `0x180251418`
- `0x180252970`
- `0x180255390`
- `0x1802607e0`
- `0x180271834`
- `0x18028bcb0`
- `0x180326568`
- `0x1803aafc0`
- `0x1803ac0f0`
- `0x1803ac230`
- `0x1803ac9d0`
- `0x1803acb10`
- `0x1803ad2a0`
- `0x1803ad3e0`
- `0x1803adbb0`
- `0x1803adcf0`
- `0x1803ae490`
- `0x1803ae5d0`
- `0x1803aecf0`
- `0x1803aee30`
- `0x1803af550`
- `0x1803af690`
- `0x1803afd10`

## callees

- `0x18000b9e0`
- `0x180011230`
- `0x180012310`
- `0x180019450`
- `0x18002acc0`
- `0x180030860`
- `0x180031308`
- `0x180031390`
- `0x1800313f8`
- `0x180053590`
- `0x18006c110`
- `0x1800712c4`
- `0x180089be8`
- `0x180093b34`
- `0x1800b83c8`
- `0x1800b9e28`
- `0x180112814`
- `0x18011286c`
- `0x180112974`
- `0x1804de9ac`
- `0x1804e6624`
- `0x1804e66bc`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18003089f`
- `KERNEL32!GetProcessHeap` at `0x18003089f`
- `KERNEL32!HeapAlloc` at `0x1800308b3`
- `KERNEL32!HeapAlloc` at `0x1800308b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180030a3e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180030a97`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180030a3e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180030a97`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18003115b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180031177`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18003115b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180031177`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030e66`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180031107`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030e66`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180031107`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlEscapeW` at `0x180030bb2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlEscapeW` at `0x180030bb2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800312da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800312da`
- `OLEAUT32!__imp_SysStringLen` at `0x18003128f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003128f`
- `SHELL32!SHParseDisplayName` at `0x180030e07`
- `SHELL32!SHParseDisplayName` at `0x180030e07`
- `SHELL32!__imp_ILCombine` at `0x180030db1`
- `SHELL32!__imp_ILCombine` at `0x180030db1`
- `SHELL32!__imp_ILFree` at `0x180030dc6`
- `SHELL32!__imp_ILFree` at `0x180030dc6`
- `iertutil!CreateIUriBuilder` at `0x1800311f4`
- `iertutil!CreateIUriBuilder` at `0x1800311f4`
- `iertutil!CreateUri` at `0x180030b50`
- `iertutil!CreateUri` at `0x180030bc8`
- `iertutil!CreateUri` at `0x180030b50`
- `iertutil!CreateUri` at `0x180030bc8`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180030eea`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180030eea`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030e1f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030e32`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030e1f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030e32`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180030ce7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180030ce7`

## string_xrefs

- `0x180030b10`: `Parse Using IUri`

## pseudocode

```c
__int64 __fastcall IECreateFromPathCPWithBCW(unsigned int a1, WCHAR *a2, IBindCtx *a3, LPITEMIDLIST *a4)
{
  LPITEMIDLIST *v4; // r13
  HANDLE ProcessHeap; // rax
  CDwnCodePage *v9; // rax
  CDwnCodePage *v10; // rax
  int v11; // r15d
  CDwnCodePage *v12; // rbx
  LPBC v13; // rsi
  HRESULT v14; // esi
  __int64 v15; // r14
  __int64 v16; // rbx
  WCHAR v18; // ax
  HRESULT v19; // eax
  UINT nScheme; // ecx
  LPBC v21; // rbx
  struct _ITEMID_CHILD *appended; // r15
  unsigned __int16 v23; // r13
  const WCHAR *v24; // r15
  HRESULT v25; // ebx
  int v26; // edx
  _WORD *v27; // rcx
  BSTR v28; // rbx
  struct IUri *v29; // r12
  int v30; // ebx
  DWORD v31; // eax
  unsigned __int16 v32; // r14
  __int64 v33; // r14
  struct _ITEMID_CHILD *v34; // rax
  BOOL v35; // ebx
  LPITEMIDLIST v36; // rax
  LPITEMIDLIST v37; // rbx
  bool v38; // bl
  HRESULT v39; // eax
  WCHAR *v40; // rcx
  ITEMIDLIST *v41; // rax
  int IsFeatureEnabledInternal; // eax
  int v43; // ebx
  int v44; // ecx
  struct IUri *v45; // rbx
  struct IUri *v46; // rbx
  int v47; // ecx
  struct IUriVtbl *lpVtbl; // rax
  CDummyOleWindow *v49; // rax
  CDummyOleWindow *v50; // rax
  CDummyOleWindow *v51; // r14
  HRESULT IUriBuilder; // ebx
  DWORD v53[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v54; // [rsp+38h] [rbp-C8h]
  struct IUri *v55; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchEscaped; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+4Ch] [rbp-B4h] BYREF
  LPBC ppbc; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pwzURI; // [rsp+58h] [rbp-A8h] BYREF
  ITEMIDLIST *v60; // [rsp+60h] [rbp-A0h]
  LPITEMIDLIST *v61; // [rsp+68h] [rbp-98h]
  IUri *ppURI; // [rsp+70h] [rbp-90h] BYREF
  void **v63; // [rsp+78h] [rbp-88h] BYREF
  struct IUri *v64; // [rsp+80h] [rbp-80h]
  unsigned int v65; // [rsp+88h] [rbp-78h]
  BSTR pbstr; // [rsp+90h] [rbp-70h] BYREF
  BSTR v67; // [rsp+98h] [rbp-68h] BYREF
  UINT v68; // [rsp+A0h] [rbp-60h] BYREF
  struct IBindCtx *v69; // [rsp+A8h] [rbp-58h]
  _QWORD v70[4]; // [rsp+B0h] [rbp-50h] BYREF
  PARSEDURLW ppu; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszStart[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR pszPath[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR pszUrl[2088]; // [rsp+530h] [rbp+430h] BYREF

  v4 = a4;
  v61 = a4;
  ProcessHeap = GetProcessHeap();
  v9 = (CDwnCodePage *)HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v9 )
    std::_Xbad_alloc();
  v10 = CDwnCodePage::CDwnCodePage(v9, a1);
  v11 = 0;
  ppbc = a3;
  *v4 = 0;
  v12 = v10;
  if ( a3 )
  {
    ((void (__fastcall *)(IBindCtx *))a3->lpVtbl->AddRef)(a3);
    goto LABEL_4;
  }
  v14 = CreateBindCtx_0(0, &ppbc);
  if ( v14 >= 0 )
  {
LABEL_4:
    v13 = ppbc;
    if ( v12 )
    {
      v14 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDwnCodePage *))ppbc->lpVtbl->RegisterObjectParam)(
              ppbc,
              L"CDwnCodePage",
              v12);
    }
    else
    {
      v49 = (CDummyOleWindow *)operator new(0x18u);
      if ( !v49 || (v50 = CDummyOleWindow::CDummyOleWindow(v49), (v51 = v50) == 0) )
      {
        v14 = -2147024882;
LABEL_110:
        IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&ppbc);
        goto LABEL_7;
      }
      v14 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyOleWindow *))v13->lpVtbl->RegisterObjectParam)(
              v13,
              L"CDwnCodePage",
              v50);
      (*(void (__fastcall **)(CDummyOleWindow *))(*(_QWORD *)v51 + 16LL))(v51);
    }
    if ( v14 >= 0 )
      goto LABEL_7;
    goto LABEL_110;
  }
LABEL_7:
  if ( v12 )
    CDwnCodePage::Release(v12);
  if ( v14 < 0 )
    goto LABEL_17;
  if ( FCK::FEATURE_INTERNET_SHELL_FOLDERS )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_23;
    dword_18065B780 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_INTERNET_SHELL_FOLDERS = 0;
  }
  if ( !dword_18065B780 )
LABEL_23:
    BindCtx_AddObjectParam(ppbc, L"Do not bind to Internet shell folder handlers", 0);
  if ( !a2 )
    goto LABEL_16;
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( a2[v16] );
  if ( !(_DWORD)v16 )
    goto LABEL_16;
  memset(&ppu, 0, sizeof(ppu));
  ppu.cbSize = 40;
  if ( ParseURLW(a2, &ppu) >= 0 && ppu.nScheme == 9 )
  {
    v53[0] = 260;
    v14 = PathCreateFromUrlW(a2, pszPath, v53, 0);
    if ( v14 >= 0 )
    {
      LODWORD(v16) = v53[0];
      a2 = pszPath;
    }
  }
  v18 = *a2;
  pcchPath = 1;
  if ( v18 == 92 || v18 && a2[1] == 58 )
  {
    v11 = 1;
  }
  else
  {
    memset(&ppu, 0, sizeof(ppu));
    ppu.cbSize = 40;
    v19 = ParseURLW(a2, &ppu);
    nScheme = -1;
    if ( v19 >= 0 )
      nScheme = ppu.nScheme;
    LOBYTE(v11) = nScheme == 9;
    if ( nScheme != 9 )
      goto LABEL_32;
  }
  if ( (unsigned int)v16 >= 0x104 || PathCchCanonicalizeEx(pszStart, 0x104u, a2, PATHCCH_NONE) < 0 )
  {
    v14 = -2147024893;
    goto LABEL_17;
  }
  if ( StrChrW(pszStart, 0x2Au) || (a2 = pszStart, StrChrW(pszStart, 0x3Fu)) )
  {
LABEL_16:
    v14 = -2147467259;
    goto LABEL_17;
  }
LABEL_32:
  if ( v14 < 0 )
    goto LABEL_17;
  if ( v11 )
    goto LABEL_78;
  v21 = ppbc;
  appended = 0;
  v69 = ppbc;
  v55 = 0;
  if ( ppbc )
  {
    if ( ((int (__fastcall *)(LPBC, const wchar_t *, struct IUri **))ppbc->lpVtbl->GetObjectParam)(
           ppbc,
           L"Parse Prefer Folder Browsing",
           &v55) >= 0 )
    {
      ((void (__fastcall *)(struct IUri *))v55->lpVtbl->Release)(v55);
LABEL_78:
      v14 = SHParseDisplayName(a2, ppbc, v4, 0, 0);
      if ( v14 == -2147024891
        && (unsigned __int8)IEConfiguration_GetBool(268435482)
        && (unsigned __int8)IEConfiguration_GetBool(536870915) )
      {
        pcchPath = 2085;
        if ( !(unsigned int)IsFileUrlW(a2)
          || (v39 = PathCreateFromUrlW(a2, pszUrl, &pcchPath, 0), v40 = pszUrl, v39 < 0) )
        {
          v40 = a2;
        }
        v60 = 0;
        SHSimpleIDListFromFindData(v40);
        v41 = v60;
        *v4 = v60;
        if ( v41 )
          v14 = 0;
      }
      goto LABEL_17;
    }
    v21 = ppbc;
    v69 = ppbc;
  }
  pwzURI = a2;
  *v4 = 0;
  _RemoveIEHttp(&pwzURI);
  ppURI = 0;
  v23 = 2084;
  v55 = 0;
  if ( !v21
    || ((int (__fastcall *)(LPBC, const wchar_t *, struct IUri **))v21->lpVtbl->GetObjectParam)(
         v21,
         L"Parse Using IUri",
         &v55) < 0
    || (v43 = ((__int64 (__fastcall *)(struct IUri *, GUID *, IUri **))v55->lpVtbl->QueryInterface)(
                v55,
                &GUID_a39ee748_6a27_4817_a6f2_13914bef5890,
                &ppURI),
        ((void (__fastcall *)(struct IUri *))v55->lpVtbl->Release)(v55),
        v43 < 0) )
  {
    v24 = pwzURI;
    if ( (unsigned int)PathIsFilePath(pwzURI) )
      goto LABEL_134;
    v25 = CreateUri(v24, 0x3002B80u, 0, &ppURI);
    if ( v25 < 0 )
    {
      StringCchCopyW(pszUrl, 0x824u, v24);
      if ( (unsigned int)_ValidateURL(pszUrl, 0) )
      {
        if ( !(unsigned int)BindCtx_ContainsObject(v69, L"Parse Internet Dont Escape Spaces") )
        {
          pcchEscaped = 2084;
          UrlEscapeW(pszUrl, pszUrl, &pcchEscaped, 0x4000000u);
        }
        v25 = CreateUri(v24, 0x3002B80u, 0, &ppURI);
      }
      if ( v25 < 0 )
        goto LABEL_134;
    }
    appended = 0;
  }
  pcchEscaped = 0;
  if ( ((int (__fastcall *)(IUri *, __int64, DWORD *, _QWORD))ppURI->lpVtbl->GetPropertyDWORD)(
         ppURI,
         17,
         &pcchEscaped,
         0) >= 0
    && pcchEscaped <= 0x12 )
  {
    v44 = 395268;
    if ( _bittest(&v44, pcchEscaped) )
    {
      v45 = ppURI;
      pwzURI = (LPCWSTR)ppURI;
      v53[0] = 0;
      if ( ((int (__fastcall *)(IUri *, __int64, DWORD *))ppURI->lpVtbl->HasProperty)(ppURI, 5, v53) >= 0 && v53[0] )
      {
        v55 = v45;
        *(_QWORD *)v53 = 0;
        IUriBuilder = CreateIUriBuilder(v45, 0, 0, (IUriBuilder **)v53);
        if ( IUriBuilder >= 0 )
        {
          IUriBuilder = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v53 + 128LL))(*(_QWORD *)v53, 0);
          if ( IUriBuilder >= 0 )
            IUriBuilder = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IUri **))(**(_QWORD **)v53 + 32LL))(
                            *(_QWORD *)v53,
                            0xFFFFFFFFLL,
                            0,
                            0,
                            &v55);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(v53);
        if ( IUriBuilder < 0 )
        {
          v29 = (struct IUri *)pwzURI;
          goto LABEL_72;
        }
      }
      else
      {
        v55 = v45;
        pcchPath = 0;
      }
      v46 = v55;
      v63 = &CUString::`vftable';
      v47 = 0;
      v64 = 0;
      pbstr = 0;
      v54 = 0;
      v67 = 0;
      v68 = 0;
      v65 = 0;
      if ( !v55 )
      {
LABEL_54:
        v53[0] = v47;
        if ( v47 == 1 )
        {
          v31 = CUString::Set((CUString *)&v63, v55, Uri_PROPERTY_RAW_URI);
          v54 = v31;
          v53[0] = v31;
        }
        else
        {
          v31 = v47;
        }
        if ( v31 )
        {
          v29 = (struct IUri *)pwzURI;
LABEL_65:
          v63 = &CUString::`vftable';
          v35 = v64 != 0;
          if ( v64 || v65 != 11 )
          {
            if ( pbstr )
            {
              SysFreeString(pbstr);
              pbstr = 0;
            }
            v67 = 0;
            v68 = 0;
            if ( v35 && v64 )
            {
              ((void (__fastcall *)(struct IUri *))v64->lpVtbl->Release)(v64);
              v64 = 0;
            }
          }
          v65 = 11;
LABEL_72:
          if ( v55 && v55 != v29 )
            ((void (*)(void))v55->lpVtbl->Release)();
          if ( appended )
          {
            *(&ppu.cchProtocol + 1) = 0;
            ppu.cbSize = 2031636;
            *(GUID *)(&ppu.cbSize + 1) = CLSID_Internet;
            v36 = ILCombine((LPCITEMIDLIST)&ppu, (LPCITEMIDLIST)appended);
            v4 = v61;
            v37 = v36;
            *v61 = v36;
            ILFree((LPITEMIDLIST)appended);
            v38 = v37 != 0;
            goto LABEL_75;
          }
          goto LABEL_134;
        }
        v28 = v67;
        if ( v67 )
        {
          do
            ++v15;
          while ( v67[v15] );
        }
        else
        {
          LOWORD(v15) = 0;
        }
        v32 = v15 + 1;
        if ( v32 < 0x824u )
          v23 = v32;
        v33 = (unsigned __int16)(2 * (v23 + 5));
        v34 = (struct _ITEMID_CHILD *)CoTaskMemAlloc(v33 + 2);
        appended = v34;
        if ( v34 )
        {
          memset_0(v34, 0, v33 + 2);
          v26 = v23;
          v27 = (_WORD *)((char *)appended + 8);
          *(_WORD *)appended = v33;
          *((_WORD *)appended + 1) = -32671;
          *((_DWORD *)appended + 1) = a1;
          if ( v23 )
          {
            while ( *v28 )
            {
              *v27++ = *v28++;
              if ( !--v26 )
                goto LABEL_48;
            }
            *v27 = 0;
          }
          else
          {
LABEL_48:
            *(v27 - 1) = 0;
          }
          v29 = (struct IUri *)pwzURI;
          if ( pcchPath )
          {
            CUString::CUString((CUString *)v70, (struct IUri *)pwzURI, Uri_PROPERTY_FRAGMENT, (int *)v53);
            v30 = v53[0];
            if ( !v53[0] )
              appended = (struct _ITEMID_CHILD *)ILAppendHiddenStringW((LPITEMIDLIST)appended);
            v70[0] = &CUString::`vftable';
            CUString::Set((CUString *)v70, 0, Uri_PROPERTY_RAW_URI);
            goto LABEL_64;
          }
        }
        else
        {
          v29 = (struct IUri *)pwzURI;
        }
        v30 = v54;
LABEL_64:
        if ( v30 >= 0 && appended )
          appended = Win7_AppendHiddenProgID((LPITEMIDLIST)appended, v69);
        goto LABEL_65;
      }
      lpVtbl = v55->lpVtbl;
      *(_QWORD *)v53 = 0;
      if ( ((int (__fastcall *)(struct IUri *, GUID *, DWORD *))lpVtbl->QueryInterface)(
             v55,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             v53) < 0 )
      {
        v54 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v46->lpVtbl->GetPropertyBSTR)(
                v46,
                v65,
                &pbstr,
                0);
        v47 = v54;
        if ( v54 >= 0 )
        {
          v67 = pbstr;
          v68 = SysStringLen(pbstr);
LABEL_104:
          v64 = v46;
          ((void (__fastcall *)(struct IUri *))v46->lpVtbl->AddRef)(v46);
          v47 = v54;
          goto LABEL_54;
        }
      }
      else
      {
        v54 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR *, UINT *))(**(_QWORD **)v53 + 224LL))(
                *(_QWORD *)v53,
                v65,
                &v67,
                &v68);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 16LL))(*(_QWORD *)v53);
        v47 = v54;
      }
      if ( v47 < 0 )
        goto LABEL_54;
      goto LABEL_104;
    }
  }
LABEL_134:
  v4 = v61;
  v38 = 0;
LABEL_75:
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  if ( !v38 )
    goto LABEL_78;
LABEL_17:
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180030860  push    rbp
0x180030862  push    rsi
0x180030863  push    rdi
0x180030864  push    r12
0x180030866  push    r13
0x180030868  lea     rbp, [rsp-14B0h]
0x180030870  mov     eax, 15B0h
0x180030875  call    _alloca_probe
0x18003087a  sub     rsp, rax
0x18003087d  mov     rax, cs:__security_cookie
0x180030884  xor     rax, rsp
0x180030887  mov     [rbp+14D0h+var_50], rax
0x18003088e  mov     r13, r9
0x180030891  mov     [rsp+15D0h+var_1568], r9
0x180030896  mov     rsi, r8
0x180030899  mov     rdi, rdx
0x18003089c  mov     r12d, ecx
0x18003089f  call    cs:__imp_GetProcessHeap
0x1800308a5  mov     edx, 8; dwFlags
0x1800308aa  mov     r8d, 10h; dwBytes
0x1800308b0  mov     rcx, rax; hHeap
0x1800308b3  call    cs:__imp_HeapAlloc
0x1800308b9  test    rax, rax
0x1800308bc  jz      loc_180030A00
0x1800308c2  mov     [rsp+15D0h+var_28], rbx
0x1800308ca  mov     edx, r12d; unsigned int
0x1800308cd  mov     [rsp+15D0h+var_30], r14
0x1800308d5  mov     rcx, rax; this
0x1800308d8  mov     [rsp+15D0h+var_38], r15
0x1800308e0  call    ??0CDwnCodePage@@QEAA@I@Z; CDwnCodePage::CDwnCodePage(uint)
0x1800308e5  xor     r15d, r15d
0x1800308e8  mov     [rsp+15D0h+ppbc], rsi
0x1800308ed  mov     [r13+0], r15
0x1800308f1  mov     rbx, rax
0x1800308f4  test    rsi, rsi
0x1800308f7  jz      loc_1800309E5
0x1800308fd  mov     rdx, [rsi]
0x180030900  mov     rcx, rsi
0x180030903  mov     rax, [rdx+8]
0x180030907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003090c  mov     rsi, [rsp+15D0h+ppbc]
0x180030911  test    rbx, rbx
0x180030914  jz      loc_18003107E
0x18003091a  mov     rax, [rsi]
0x18003091d  lea     rdx, aCdwncodepage; "CDwnCodePage"
0x180030924  mov     r8, rbx
0x180030927  mov     rcx, rsi
0x18003092a  mov     rax, [rax+48h]
0x18003092e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030933  mov     esi, eax
0x180030935  test    esi, esi
0x180030937  js      loc_1800310D1
0x18003093d  test    rbx, rbx
0x180030940  jnz     loc_1800310E0
0x180030946  test    esi, esi
0x180030948  js      short loc_180030997
0x18003094a  mov     rcx, cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x180030951  test    rcx, rcx
0x180030954  jnz     loc_180030EEA
0x18003095a  mov     eax, cs:dword_18065B780
0x180030960  test    eax, eax
0x180030962  jz      loc_180030A06
0x180030968  test    rdi, rdi
0x18003096b  jz      short loc_180030992
0x18003096d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180030974  mov     rbx, r14
0x180030977  nop     word ptr [rax+rax+00000000h]
0x180030980  inc     rbx
0x180030983  cmp     [rdi+rbx*2], r15w
0x180030988  jnz     short loc_180030980
0x18003098a  test    ebx, ebx
0x18003098c  jnz     loc_180030A1F
0x180030992  mov     esi, 80004005h
0x180030997  mov     rcx, [rsp+15D0h+ppbc]
0x18003099c  mov     r15, [rsp+15D0h+var_38]
0x1800309a4  mov     r14, [rsp+15D0h+var_30]
0x1800309ac  mov     rbx, [rsp+15D0h+var_28]
0x1800309b4  test    rcx, rcx
0x1800309b7  jz      short loc_1800309C5
0x1800309b9  mov     rax, [rcx]
0x1800309bc  mov     rax, [rax+10h]
0x1800309c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c5  mov     eax, esi
0x1800309c7  mov     rcx, [rbp+14D0h+var_50]
0x1800309ce  xor     rcx, rsp; StackCookie
0x1800309d1  call    __security_check_cookie
0x1800309d6  add     rsp, 15B0h
0x1800309dd  pop     r13
0x1800309df  pop     r12
0x1800309e1  pop     rdi
0x1800309e2  pop     rsi
0x1800309e3  pop     rbp
0x1800309e4  retn
0x1800309e5  lea     rdx, [rsp+15D0h+ppbc]; ppbc
0x1800309ea  xor     ecx, ecx; reserved
0x1800309ec  call    CreateBindCtx_0
0x1800309f1  mov     esi, eax
0x1800309f3  test    eax, eax
0x1800309f5  jns     loc_18003090C
0x1800309fb  jmp     loc_18003093D
0x180030a00  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180030a06  mov     rcx, [rsp+15D0h+ppbc]
0x180030a0b  lea     rdx, aDoNotBindToInt; "Do not bind to Internet shell folder ha"...
0x180030a12  xor     r8d, r8d
0x180030a15  call    BindCtx_AddObjectParam
0x180030a1a  jmp     loc_180030968
0x180030a1f  xorps   xmm0, xmm0
0x180030a22  lea     rdx, [rbp+14D0h+ppu]; ppu
0x180030a26  xor     eax, eax
0x180030a28  mov     rcx, rdi; pcszURL
0x180030a2b  movups  xmmword ptr [rbp+14D0h+ppu.cbSize], xmm0
0x180030a2f  mov     [rbp+14D0h+ppu.cbSize], 28h ; '('
0x180030a36  movups  xmmword ptr [rbp+14D0h+ppu.cchProtocol], xmm0
0x180030a3a  mov     qword ptr [rbp+14D0h+ppu.cchSuffix], rax
0x180030a3e  call    cs:__imp_ParseURLW
0x180030a44  test    eax, eax
0x180030a46  js      short loc_180030A52
0x180030a48  cmp     [rbp+14D0h+ppu.nScheme], 9
0x180030a4c  jz      loc_1800310ED
0x180030a52  movzx   eax, word ptr [rdi]
0x180030a55  mov     ecx, 1
0x180030a5a  mov     [rsp+15D0h+pcchPath], ecx
0x180030a5e  cmp     ax, 5Ch ; '\'
0x180030a62  jz      loc_180031127
0x180030a68  test    ax, ax
0x180030a6b  jz      short loc_180030A78
0x180030a6d  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180030a72  jz      loc_180031127
0x180030a78  xorps   xmm0, xmm0
0x180030a7b  lea     rdx, [rbp+14D0h+ppu]; ppu
0x180030a7f  xor     eax, eax
0x180030a81  mov     rcx, rdi; pcszURL
0x180030a84  movups  xmmword ptr [rbp+14D0h+ppu.cbSize], xmm0
0x180030a88  mov     [rbp+14D0h+ppu.cbSize], 28h ; '('
0x180030a8f  movups  xmmword ptr [rbp+14D0h+ppu.cchProtocol], xmm0
0x180030a93  mov     qword ptr [rbp+14D0h+ppu.cchSuffix], rax
0x180030a97  call    cs:__imp_ParseURLW
0x180030a9d  test    eax, eax
0x180030a9f  mov     ecx, 0FFFFFFFFh
0x180030aa4  cmovns  ecx, [rbp+14D0h+ppu.nScheme]
0x180030aa8  cmp     ecx, 9
0x180030aab  setz    r15b
0x180030aaf  jz      loc_18003112A
0x180030ab5  test    esi, esi
0x180030ab7  js      loc_180030997
0x180030abd  test    r15d, r15d
0x180030ac0  jnz     loc_180030DF0
0x180030ac6  mov     rbx, [rsp+15D0h+ppbc]
0x180030acb  xor     r15d, r15d
0x180030ace  mov     [rbp+14D0h+var_1528], rbx
0x180030ad2  mov     [rsp+15D0h+var_1590], r15
0x180030ad7  test    rbx, rbx
0x180030ada  jnz     loc_18003118B
0x180030ae0  lea     rcx, [rsp+15D0h+pwzURI]; unsigned __int16 **
0x180030ae5  mov     [rsp+15D0h+pwzURI], rdi
0x180030aea  mov     [r13+0], r15
0x180030aee  call    ?_RemoveIEHttp@@YAXPEAPEBG@Z; _RemoveIEHttp(ushort const * *)
0x180030af3  mov     [rsp+15D0h+ppURI], r15
0x180030af8  mov     r13d, 824h
0x180030afe  mov     [rsp+15D0h+var_1590], r15
0x180030b03  test    rbx, rbx
0x180030b06  jz      short loc_180030B2B
0x180030b08  mov     rax, [rbx]
0x180030b0b  lea     r8, [rsp+15D0h+var_1590]
0x180030b10  lea     rdx, aParseUsingIuri; "Parse Using IUri"
0x180030b17  mov     rcx, rbx
0x180030b1a  mov     rax, [rax+50h]
0x180030b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b23  test    eax, eax
0x180030b25  jns     loc_180030F10
0x180030b2b  mov     r15, [rsp+15D0h+pwzURI]
0x180030b30  mov     rcx, r15
0x180030b33  call    PathIsFilePath
0x180030b38  test    eax, eax
0x180030b3a  jnz     loc_1800312E9
0x180030b40  lea     r9, [rsp+15D0h+ppURI]; ppURI
0x180030b45  xor     r8d, r8d; dwReserved
0x180030b48  mov     edx, 3002B80h; dwFlags
0x180030b4d  mov     rcx, r15; pwzURI
0x180030b50  call    cs:__imp_CreateUri
0x180030b56  mov     ebx, eax
0x180030b58  test    eax, eax
0x180030b5a  jns     short loc_180030BD8
0x180030b5c  mov     r8, r15; unsigned __int16 *
0x180030b5f  lea     rcx, [rbp+14D0h+pszUrl]; unsigned __int16 *
0x180030b66  mov     rdx, r13; unsigned __int64
0x180030b69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030b6e  xor     edx, edx; unsigned int
0x180030b70  lea     rcx, [rbp+14D0h+pszUrl]; unsigned __int16 *
0x180030b77  call    ?_ValidateURL@@YAHPEAGK@Z; _ValidateURL(ushort *,ulong)
0x180030b7c  test    eax, eax
0x180030b7e  jz      short loc_180030BD0
0x180030b80  mov     rcx, [rbp+14D0h+var_1528]
0x180030b84  lea     rdx, aParseInternetD; "Parse Internet Dont Escape Spaces"
0x180030b8b  call    BindCtx_ContainsObject
0x180030b90  test    eax, eax
0x180030b92  jnz     short loc_180030BB8
0x180030b94  mov     r9d, 4000000h; dwFlags
0x180030b9a  mov     [rsp+15D0h+pcchEscaped], r13d
0x180030b9f  lea     r8, [rsp+15D0h+pcchEscaped]; pcchEscaped
0x180030ba4  lea     rdx, [rbp+14D0h+pszUrl]; pszEscaped
0x180030bab  lea     rcx, [rbp+14D0h+pszUrl]; pszUrl
0x180030bb2  call    cs:__imp_UrlEscapeW
0x180030bb8  lea     r9, [rsp+15D0h+ppURI]; ppURI
0x180030bbd  xor     r8d, r8d; dwReserved
0x180030bc0  mov     edx, 3002B80h; dwFlags
0x180030bc5  mov     rcx, r15; pwzURI
0x180030bc8  call    cs:__imp_CreateUri
0x180030bce  mov     ebx, eax
0x180030bd0  test    ebx, ebx
0x180030bd2  js      loc_1800312E9
0x180030bd8  xor     r15d, r15d
0x180030bdb  jmp     loc_180030F47
0x180030be0  lea     r8, [r14+2]; Size
0x180030be4  xor     edx, edx; Val
0x180030be6  mov     rcx, rax; void *
0x180030be9  call    memset_0
0x180030bee  movzx   edx, r13w
0x180030bf2  lea     rcx, [r15+8]
0x180030bf6  mov     [r15], r14w
0x180030bfa  mov     r14, r15
0x180030bfd  mov     word ptr [r15+2], 8061h
0x180030c04  mov     [r15+4], r12d
0x180030c08  test    edx, edx
0x180030c0a  jz      short loc_180030C28
0x180030c0c  nop     dword ptr [rax+00h]
0x180030c10  movzx   eax, word ptr [rbx]
0x180030c13  test    ax, ax
0x180030c16  jz      short loc_180030C8F
0x180030c18  mov     [rcx], ax
0x180030c1b  add     rbx, 2
0x180030c1f  add     rcx, 2
0x180030c23  sub     edx, 1
0x180030c26  jnz     short loc_180030C10
0x180030c28  xor     eax, eax
0x180030c2a  mov     [rcx-2], ax
0x180030c2e  cmp     [rsp+15D0h+pcchPath], 0
0x180030c33  mov     r12, [rsp+15D0h+pwzURI]
0x180030c38  jz      loc_180030CFE
0x180030c3e  lea     r9, [rsp+15D0h+var_15A0]; int *
0x180030c43  mov     r8d, 5; enum __MIDL_IUri_0001
0x180030c49  mov     rdx, r12; struct IUri *
0x180030c4c  lea     rcx, [rbp+14D0h+var_1520]; this
0x180030c50  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180030c55  mov     ebx, [rsp+15D0h+var_15A0]
0x180030c59  test    ebx, ebx
0x180030c5b  jnz     short loc_180030C71
0x180030c5d  mov     r8, [rbp+14D0h+var_1500]
0x180030c61  mov     edx, 0BEEF0001h
0x180030c66  mov     rcx, r14; pidl
0x180030c69  call    ILAppendHiddenStringW
0x180030c6e  mov     r15, rax
0x180030c71  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180030c78  xor     edx, edx; struct IUri *
0x180030c7a  mov     r8d, 0Bh; enum __MIDL_IUri_0001
0x180030c80  mov     [rbp+14D0h+var_1520], r14
0x180030c84  lea     rcx, [rbp+14D0h+var_1520]; this
0x180030c88  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180030c8d  jmp     short loc_180030D09
0x180030c8f  xor     eax, eax
0x180030c91  mov     [rcx], ax
0x180030c94  jmp     short loc_180030C2E
0x180030c96  mov     [rsp+15D0h+var_15A0], ecx
0x180030c9a  cmp     ecx, 1
0x180030c9d  jz      loc_18003129D
0x180030ca3  mov     eax, ecx
0x180030ca5  test    eax, eax
0x180030ca7  jnz     loc_1800312C9
0x180030cad  mov     rbx, [rbp+14D0h+var_1538]
0x180030cb1  test    rbx, rbx
0x180030cb4  jz      loc_1800312C1
0x180030cba  nop     word ptr [rax+rax+00h]
0x180030cc0  inc     r14
0x180030cc3  cmp     word ptr [rbx+r14*2], 0
0x180030cc9  jnz     short loc_180030CC0
0x180030ccb  inc     r14w
0x180030ccf  cmp     r14w, r13w
0x180030cd3  cmovb   r13w, r14w
0x180030cd8  lea     eax, [r13+5]
0x180030cdc  add     ax, ax
0x180030cdf  movzx   r14d, ax
0x180030ce3  lea     rcx, [r14+2]; cb
0x180030ce7  call    cs:__imp_CoTaskMemAlloc
0x180030ced  mov     r15, rax
0x180030cf0  test    rax, rax
0x180030cf3  jnz     loc_180030BE0
0x180030cf9  mov     r12, [rsp+15D0h+pwzURI]
0x180030cfe  mov     ebx, [rsp+15D0h+var_1598]
0x180030d02  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180030d09  test    ebx, ebx
0x180030d0b  jns     loc_180030ECD
0x180030d11  mov     [rsp+15D0h+var_1558], r14
0x180030d16  xor     r14d, r14d
0x180030d19  mov     ebx, r14d
0x180030d1c  mov     eax, r14d
0x180030d1f  cmp     [rbp+14D0h+var_1550], rbx
0x180030d23  setnz   bl
0x180030d26  cmp     [rbp+14D0h+var_1548], 0Bh
0x180030d2a  setnz   al
0x180030d2d  test    ebx, ebx
  ... truncated ...
```
