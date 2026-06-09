# IECreateFromPathCPWithBCW

- ea: `0x1800347d0`
- end: `0x1800352e3`
- name: `IECreateFromPathCPWithBCW`
- size: `2835`
- prototype: ``
- caller_count: `67`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cc344`
- `0x1800d04d0`
- `0x1800e0140`
- `0x1800e05a4`
- `0x1800e21d0`
- `0x1800e25a0`
- `0x180105dd4`
- `0x18013bf38`
- `0x18013ce58`
- `0x180141224`
- `0x1801554b8`
- `0x18019f2e0`
- `0x1801b9c0c`
- `0x1801bc9d0`
- `0x1801bcb24`
- `0x1801bcfe0`
- `0x1801d8864`
- `0x1801fb688`
- `0x180215080`
- `0x18021c300`
- `0x18021c770`
- `0x18021d100`
- `0x180226300`
- `0x18022cffc`
- `0x180256170`
- `0x180257034`
- `0x18025cae8`
- `0x180270408`
- `0x180271a50`
- `0x1802746c0`
- `0x180280510`
- `0x1802923e0`
- `0x1802adf64`
- `0x180351ad8`
- `0x1803dd360`
- `0x1803de510`
- `0x1803de650`
- `0x1803dee20`
- `0x1803def60`
- `0x1803df700`
- `0x1803df840`
- `0x1803e0030`
- `0x1803e0170`
- `0x1803e0930`
- `0x1803e0a70`
- `0x1803e11b0`
- `0x1803e12f0`
- `0x1803e1a30`
- `0x1803e1b70`
- `0x1803e2200`

## callees

- `0x180005030`
- `0x180006100`
- `0x180007010`
- `0x1800144d0`
- `0x180015644`
- `0x1800347d0`
- `0x1800352ec`
- `0x180035380`
- `0x1800353f0`
- `0x180056d9c`
- `0x180070630`
- `0x180076974`
- `0x18008faf8`
- `0x18009ad20`
- `0x1800bf0d8`
- `0x1800c0b58`
- `0x18011eafc`
- `0x18011eb50`
- `0x18011ec70`
- `0x18051c514`
- `0x180524bb8`
- `0x180524c50`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18003480f`
- `KERNEL32!GetProcessHeap` at `0x18003480f`
- `KERNEL32!HeapAlloc` at `0x180034829`
- `KERNEL32!HeapAlloc` at `0x180034829`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800349b2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180034a11`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800349b2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180034a11`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180035121`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180035143`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180035121`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180035143`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180034e1a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800350c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180034e1a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800350c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlEscapeW` at `0x180034b3c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlEscapeW` at `0x180034b3c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800352b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800352b8`
- `OLEAUT32!__imp_SysStringLen` at `0x180035267`
- `OLEAUT32!__imp_SysStringLen` at `0x180035267`
- `SHELL32!SHParseDisplayName` at `0x180034da9`
- `SHELL32!SHParseDisplayName` at `0x180034da9`
- `SHELL32!__imp_ILCombine` at `0x180034d47`
- `SHELL32!__imp_ILCombine` at `0x180034d47`
- `SHELL32!__imp_ILFree` at `0x180034d62`
- `SHELL32!__imp_ILFree` at `0x180034d62`
- `iertutil!CreateIUriBuilder` at `0x1800351c6`
- `iertutil!CreateIUriBuilder` at `0x1800351c6`
- `iertutil!CreateUri` at `0x180034ad0`
- `iertutil!CreateUri` at `0x180034b58`
- `iertutil!CreateUri` at `0x180034ad0`
- `iertutil!CreateUri` at `0x180034b58`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180034ea4`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180034ea4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034dc7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034de0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034dc7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034de0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180034c77`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180034c77`

## string_xrefs

- `0x180034a90`: `Parse Using IUri`

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
    dword_18069F770 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_INTERNET_SHELL_FOLDERS = 0;
  }
  if ( !dword_18069F770 )
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
0x1800347d0  push    rbp
0x1800347d2  push    rsi
0x1800347d3  push    rdi
0x1800347d4  push    r12
0x1800347d6  push    r13
0x1800347d8  lea     rbp, [rsp-14B0h]
0x1800347e0  mov     eax, 15B0h
0x1800347e5  call    _alloca_probe
0x1800347ea  sub     rsp, rax
0x1800347ed  mov     rax, cs:__security_cookie
0x1800347f4  xor     rax, rsp
0x1800347f7  mov     [rbp+14D0h+var_50], rax
0x1800347fe  mov     r13, r9
0x180034801  mov     [rsp+15D0h+var_1568], r9
0x180034806  mov     rsi, r8
0x180034809  mov     rdi, rdx
0x18003480c  mov     r12d, ecx
0x18003480f  call    cs:__imp_GetProcessHeap
0x180034816  nop     dword ptr [rax+rax+00h]
0x18003481b  mov     edx, 8; dwFlags
0x180034820  mov     r8d, 10h; dwBytes
0x180034826  mov     rcx, rax; hHeap
0x180034829  call    cs:__imp_HeapAlloc
0x180034830  nop     dword ptr [rax+rax+00h]
0x180034835  test    rax, rax
0x180034838  jz      loc_180034974
0x18003483e  mov     [rsp+15D0h+var_28], rbx
0x180034846  mov     edx, r12d; unsigned int
0x180034849  mov     [rsp+15D0h+var_30], r14
0x180034851  mov     rcx, rax; this
0x180034854  mov     [rsp+15D0h+var_38], r15
0x18003485c  call    ??0CDwnCodePage@@QEAA@I@Z; CDwnCodePage::CDwnCodePage(uint)
0x180034861  xor     r15d, r15d
0x180034864  mov     [rsp+15D0h+ppbc], rsi
0x180034869  mov     [r13+0], r15
0x18003486d  mov     rbx, rax
0x180034870  test    rsi, rsi
0x180034873  jz      loc_180034959
0x180034879  mov     rdx, [rsi]
0x18003487c  mov     rcx, rsi
0x18003487f  mov     rax, [rdx+8]
0x180034883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034888  mov     rsi, [rsp+15D0h+ppbc]
0x18003488d  test    rbx, rbx
0x180034890  jz      loc_18003503E
0x180034896  mov     rax, [rsi]
0x180034899  lea     rdx, aCdwncodepage; "CDwnCodePage"
0x1800348a0  mov     r8, rbx
0x1800348a3  mov     rcx, rsi
0x1800348a6  mov     rax, [rax+48h]
0x1800348aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348af  mov     esi, eax
0x1800348b1  test    esi, esi
0x1800348b3  js      loc_180035091
0x1800348b9  test    rbx, rbx
0x1800348bc  jnz     loc_1800350A0
0x1800348c2  test    esi, esi
0x1800348c4  js      short loc_18003490A
0x1800348c6  mov     rcx, cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x1800348cd  test    rcx, rcx
0x1800348d0  jnz     loc_180034EA4
0x1800348d6  mov     eax, cs:dword_18069F770
0x1800348dc  test    eax, eax
0x1800348de  jz      loc_18003497A
0x1800348e4  test    rdi, rdi
0x1800348e7  jz      short loc_180034905
0x1800348e9  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800348f0  mov     rbx, r14
0x1800348f3  inc     rbx
0x1800348f6  cmp     [rdi+rbx*2], r15w
0x1800348fb  jnz     short loc_1800348F3
0x1800348fd  test    ebx, ebx
0x1800348ff  jnz     loc_180034993
0x180034905  mov     esi, 80004005h
0x18003490a  mov     rcx, [rsp+15D0h+ppbc]
0x18003490f  mov     r15, [rsp+15D0h+var_38]
0x180034917  mov     r14, [rsp+15D0h+var_30]
0x18003491f  mov     rbx, [rsp+15D0h+var_28]
0x180034927  test    rcx, rcx
0x18003492a  jz      short loc_180034938
0x18003492c  mov     rax, [rcx]
0x18003492f  mov     rax, [rax+10h]
0x180034933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034938  mov     eax, esi
0x18003493a  mov     rcx, [rbp+14D0h+var_50]
0x180034941  xor     rcx, rsp; StackCookie
0x180034944  call    __security_check_cookie
0x180034949  add     rsp, 15B0h
0x180034950  pop     r13
0x180034952  pop     r12
0x180034954  pop     rdi
0x180034955  pop     rsi
0x180034956  pop     rbp
0x180034957  retn
0x180034959  lea     rdx, [rsp+15D0h+ppbc]; ppbc
0x18003495e  xor     ecx, ecx; reserved
0x180034960  call    CreateBindCtx_0
0x180034965  mov     esi, eax
0x180034967  test    eax, eax
0x180034969  jns     loc_180034888
0x18003496f  jmp     loc_1800348B9
0x180034974  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18003497a  mov     rcx, [rsp+15D0h+ppbc]
0x18003497f  lea     rdx, aDoNotBindToInt; "Do not bind to Internet shell folder ha"...
0x180034986  xor     r8d, r8d
0x180034989  call    BindCtx_AddObjectParam
0x18003498e  jmp     loc_1800348E4
0x180034993  xorps   xmm0, xmm0
0x180034996  lea     rdx, [rbp+14D0h+ppu]; ppu
0x18003499a  xor     eax, eax
0x18003499c  mov     rcx, rdi; pcszURL
0x18003499f  movups  xmmword ptr [rbp+14D0h+ppu.cbSize], xmm0
0x1800349a3  mov     [rbp+14D0h+ppu.cbSize], 28h ; '('
0x1800349aa  movups  xmmword ptr [rbp+14D0h+ppu.cchProtocol], xmm0
0x1800349ae  mov     qword ptr [rbp+14D0h+ppu.cchSuffix], rax
0x1800349b2  call    cs:__imp_ParseURLW
0x1800349b9  nop     dword ptr [rax+rax+00h]
0x1800349be  test    eax, eax
0x1800349c0  js      short loc_1800349CC
0x1800349c2  cmp     [rbp+14D0h+ppu.nScheme], 9
0x1800349c6  jz      loc_1800350AD
0x1800349cc  movzx   eax, word ptr [rdi]
0x1800349cf  mov     ecx, 1
0x1800349d4  mov     [rsp+15D0h+pcchPath], ecx
0x1800349d8  cmp     ax, 5Ch ; '\'
0x1800349dc  jz      loc_1800350ED
0x1800349e2  test    ax, ax
0x1800349e5  jz      short loc_1800349F2
0x1800349e7  cmp     word ptr [rdi+2], 3Ah ; ':'
0x1800349ec  jz      loc_1800350ED
0x1800349f2  xorps   xmm0, xmm0
0x1800349f5  lea     rdx, [rbp+14D0h+ppu]; ppu
0x1800349f9  xor     eax, eax
0x1800349fb  mov     rcx, rdi; pcszURL
0x1800349fe  movups  xmmword ptr [rbp+14D0h+ppu.cbSize], xmm0
0x180034a02  mov     [rbp+14D0h+ppu.cbSize], 28h ; '('
0x180034a09  movups  xmmword ptr [rbp+14D0h+ppu.cchProtocol], xmm0
0x180034a0d  mov     qword ptr [rbp+14D0h+ppu.cchSuffix], rax
0x180034a11  call    cs:__imp_ParseURLW
0x180034a18  nop     dword ptr [rax+rax+00h]
0x180034a1d  test    eax, eax
0x180034a1f  mov     ecx, 0FFFFFFFFh
0x180034a24  cmovns  ecx, [rbp+14D0h+ppu.nScheme]
0x180034a28  cmp     ecx, 9
0x180034a2b  setz    r15b
0x180034a2f  jz      loc_1800350F0
0x180034a35  test    esi, esi
0x180034a37  js      loc_18003490A
0x180034a3d  test    r15d, r15d
0x180034a40  jnz     loc_180034D92
0x180034a46  mov     rbx, [rsp+15D0h+ppbc]
0x180034a4b  xor     r15d, r15d
0x180034a4e  mov     [rbp+14D0h+var_1528], rbx
0x180034a52  mov     [rsp+15D0h+var_1590], r15
0x180034a57  test    rbx, rbx
0x180034a5a  jnz     loc_18003515D
0x180034a60  lea     rcx, [rsp+15D0h+pwzURI]; unsigned __int16 **
0x180034a65  mov     [rsp+15D0h+pwzURI], rdi
0x180034a6a  mov     [r13+0], r15
0x180034a6e  call    ?_RemoveIEHttp@@YAXPEAPEBG@Z; _RemoveIEHttp(ushort const * *)
0x180034a73  mov     [rsp+15D0h+ppURI], r15
0x180034a78  mov     r13d, 824h
0x180034a7e  mov     [rsp+15D0h+var_1590], r15
0x180034a83  test    rbx, rbx
0x180034a86  jz      short loc_180034AAB
0x180034a88  mov     rax, [rbx]
0x180034a8b  lea     r8, [rsp+15D0h+var_1590]
0x180034a90  lea     rdx, aParseUsingIuri; "Parse Using IUri"
0x180034a97  mov     rcx, rbx
0x180034a9a  mov     rax, [rax+50h]
0x180034a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034aa3  test    eax, eax
0x180034aa5  jns     loc_180034ED0
0x180034aab  mov     r15, [rsp+15D0h+pwzURI]
0x180034ab0  mov     rcx, r15
0x180034ab3  call    PathIsFilePath
0x180034ab8  test    eax, eax
0x180034aba  jnz     loc_1800352CD
0x180034ac0  lea     r9, [rsp+15D0h+ppURI]; ppURI
0x180034ac5  xor     r8d, r8d; dwReserved
0x180034ac8  mov     edx, 3002B80h; dwFlags
0x180034acd  mov     rcx, r15; pwzURI
0x180034ad0  call    cs:__imp_CreateUri
0x180034ad7  nop     dword ptr [rax+rax+00h]
0x180034adc  mov     ebx, eax
0x180034ade  test    eax, eax
0x180034ae0  jns     loc_180034B6E
0x180034ae6  mov     r8, r15; unsigned __int16 *
0x180034ae9  lea     rcx, [rbp+14D0h+pszUrl]; unsigned __int16 *
0x180034af0  mov     rdx, r13; unsigned __int64
0x180034af3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034af8  xor     edx, edx; unsigned int
0x180034afa  lea     rcx, [rbp+14D0h+pszUrl]; unsigned __int16 *
0x180034b01  call    ?_ValidateURL@@YAHPEAGK@Z; _ValidateURL(ushort *,ulong)
0x180034b06  test    eax, eax
0x180034b08  jz      short loc_180034B66
0x180034b0a  mov     rcx, [rbp+14D0h+var_1528]
0x180034b0e  lea     rdx, aParseInternetD; "Parse Internet Dont Escape Spaces"
0x180034b15  call    BindCtx_ContainsObject
0x180034b1a  test    eax, eax
0x180034b1c  jnz     short loc_180034B48
0x180034b1e  mov     r9d, 4000000h; dwFlags
0x180034b24  mov     [rsp+15D0h+pcchEscaped], r13d
0x180034b29  lea     r8, [rsp+15D0h+pcchEscaped]; pcchEscaped
0x180034b2e  lea     rdx, [rbp+14D0h+pszUrl]; pszEscaped
0x180034b35  lea     rcx, [rbp+14D0h+pszUrl]; pszUrl
0x180034b3c  call    cs:__imp_UrlEscapeW
0x180034b43  nop     dword ptr [rax+rax+00h]
0x180034b48  lea     r9, [rsp+15D0h+ppURI]; ppURI
0x180034b4d  xor     r8d, r8d; dwReserved
0x180034b50  mov     edx, 3002B80h; dwFlags
0x180034b55  mov     rcx, r15; pwzURI
0x180034b58  call    cs:__imp_CreateUri
0x180034b5f  nop     dword ptr [rax+rax+00h]
0x180034b64  mov     ebx, eax
0x180034b66  test    ebx, ebx
0x180034b68  js      loc_1800352CD
0x180034b6e  xor     r15d, r15d
0x180034b71  jmp     loc_180034F07
0x180034b76  lea     r8, [r14+2]; Size
0x180034b7a  xor     edx, edx; Val
0x180034b7c  mov     rcx, rax; void *
0x180034b7f  call    memset_0
0x180034b84  movzx   edx, r13w
0x180034b88  lea     rcx, [r15+8]
0x180034b8c  mov     [r15], r14w
0x180034b90  mov     r14, r15
0x180034b93  mov     word ptr [r15+2], 8061h
0x180034b9a  mov     [r15+4], r12d
0x180034b9e  test    edx, edx
0x180034ba0  jz      short loc_180034BBA
0x180034ba2  movzx   eax, word ptr [rbx]
0x180034ba5  test    ax, ax
0x180034ba8  jz      short loc_180034C21
0x180034baa  mov     [rcx], ax
0x180034bad  add     rbx, 2
0x180034bb1  add     rcx, 2
0x180034bb5  sub     edx, 1
0x180034bb8  jnz     short loc_180034BA2
0x180034bba  xor     eax, eax
0x180034bbc  mov     [rcx-2], ax
0x180034bc0  cmp     [rsp+15D0h+pcchPath], 0
0x180034bc5  mov     r12, [rsp+15D0h+pwzURI]
0x180034bca  jz      loc_180034C94
0x180034bd0  lea     r9, [rsp+15D0h+var_15A0]; int *
0x180034bd5  mov     r8d, 5; enum __MIDL_IUri_0001
0x180034bdb  mov     rdx, r12; struct IUri *
0x180034bde  lea     rcx, [rbp+14D0h+var_1520]; this
0x180034be2  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180034be7  mov     ebx, [rsp+15D0h+var_15A0]
0x180034beb  test    ebx, ebx
0x180034bed  jnz     short loc_180034C03
0x180034bef  mov     r8, [rbp+14D0h+var_1500]
0x180034bf3  mov     edx, 0BEEF0001h
0x180034bf8  mov     rcx, r14; pidl
0x180034bfb  call    ILAppendHiddenStringW
0x180034c00  mov     r15, rax
0x180034c03  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180034c0a  xor     edx, edx; struct IUri *
0x180034c0c  mov     r8d, 0Bh; enum __MIDL_IUri_0001
0x180034c12  mov     [rbp+14D0h+var_1520], r14
0x180034c16  lea     rcx, [rbp+14D0h+var_1520]; this
0x180034c1a  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180034c1f  jmp     short loc_180034C9F
0x180034c21  xor     eax, eax
0x180034c23  mov     [rcx], ax
0x180034c26  jmp     short loc_180034BC0
0x180034c28  mov     [rsp+15D0h+var_15A0], ecx
0x180034c2c  cmp     ecx, 1
0x180034c2f  jz      loc_18003527B
0x180034c35  mov     eax, ecx
0x180034c37  test    eax, eax
0x180034c39  jnz     loc_1800352A7
0x180034c3f  mov     rbx, [rbp+14D0h+var_1538]
0x180034c43  test    rbx, rbx
0x180034c46  jz      loc_18003529F
0x180034c4c  nop     dword ptr [rax+00h]
0x180034c50  inc     r14
0x180034c53  cmp     word ptr [rbx+r14*2], 0
0x180034c59  jnz     short loc_180034C50
0x180034c5b  inc     r14w
0x180034c5f  cmp     r14w, r13w
0x180034c63  cmovb   r13w, r14w
0x180034c68  lea     eax, [r13+5]
0x180034c6c  add     ax, ax
0x180034c6f  movzx   r14d, ax
0x180034c73  lea     rcx, [r14+2]; cb
0x180034c77  call    cs:__imp_CoTaskMemAlloc
0x180034c7e  nop     dword ptr [rax+rax+00h]
0x180034c83  mov     r15, rax
0x180034c86  test    rax, rax
0x180034c89  jnz     loc_180034B76
0x180034c8f  mov     r12, [rsp+15D0h+pwzURI]
0x180034c94  mov     ebx, [rsp+15D0h+var_1598]
0x180034c98  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180034c9f  test    ebx, ebx
0x180034ca1  jns     loc_180034E87
0x180034ca7  mov     [rsp+15D0h+var_1558], r14
0x180034cac  xor     r14d, r14d
0x180034caf  mov     ebx, r14d
  ... truncated ...
```
