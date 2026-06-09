# CSearchAddProviderHelper::_ParseProviderSource(void)

- ea: `0x180087ef8`
- end: `0x180088aed`
- name: `?_ParseProviderSource@CSearchAddProviderHelper@@AEAAJXZ`
- size: `3061`
- prototype: `__int64 __fastcall(CSearchAddProviderHelper *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180267dc4`

## callees

- `0x18000b9e0`
- `0x18001b970`
- `0x1800617b8`
- `0x180064c38`
- `0x18006abd8`
- `0x18006d764`
- `0x180087ef8`
- `0x180089244`
- `0x180089274`
- `0x18008bfc0`
- `0x180092a2c`
- `0x1800fe014`
- `0x18026774c`
- `0x180268538`
- `0x180304114`
- `0x180304164`
- `0x18030b868`
- `0x18044415c`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180087fa9`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800881ea`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088226`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008823a`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008824e`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088283`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088415`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088455`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088577`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008858b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008859f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180087fa9`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800881ea`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088226`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008823a`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008824e`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088283`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088415`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088455`
- `SHLWAPI!__imp_StrCmpICW` at `0x180088577`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008858b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18008859f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180087fd5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180087fd5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x18008806d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1800880e2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1800887cc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x18008806d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1800880e2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1800887cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800882f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180088329`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180088614`
- `OLEAUT32!__imp_SysFreeString` at `0x180088640`
- `OLEAUT32!__imp_SysFreeString` at `0x180088661`
- `OLEAUT32!__imp_SysFreeString` at `0x18008866a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008874c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008876d`
- `OLEAUT32!__imp_SysFreeString` at `0x180088797`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a35`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a49`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a53`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a65`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a77`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a80`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a89`
- `OLEAUT32!__imp_SysFreeString` at `0x180088ab0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800882f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180088329`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800884e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180088614`
- `OLEAUT32!__imp_SysFreeString` at `0x180088640`
- `OLEAUT32!__imp_SysFreeString` at `0x180088661`
- `OLEAUT32!__imp_SysFreeString` at `0x18008866a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008874c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008876d`
- `OLEAUT32!__imp_SysFreeString` at `0x180088797`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a35`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a49`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a53`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a65`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a77`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a80`
- `OLEAUT32!__imp_SysFreeString` at `0x180088a89`
- `OLEAUT32!__imp_SysFreeString` at `0x180088ab0`
- `iertutil!CreateUri` at `0x180088480`
- `iertutil!CreateUri` at `0x1800885ca`
- `iertutil!CreateUri` at `0x1800886df`
- `iertutil!CreateUri` at `0x180088480`
- `iertutil!CreateUri` at `0x1800885ca`
- `iertutil!CreateUri` at `0x1800886df`

## string_xrefs

- `0x180087f5f`: `osd:OpenSearchDescription/osd:Url`
- `0x180088162`: `osd:OpenSearchDescription/osd:Url`
- `0x1800884fa`: `osd:OpenSearchDescription/osd:Image`
- `0x18008840e`: `http://schemas.microsoft.com/Search/2008/`
- `0x180088202`: `template`
- `0x180088262`: `template`
- `0x180088297`: `template`
- `0x1800882b8`: `template`
- `0x180088279`: `application/x-suggestions+xml`
- `0x180088244`: `application/x-suggestions+json`
- `0x180088367`: `osd:OpenSearchDescription/ie:NTSearchResult`
- `0x180088333`: `osd:OpenSearchDescription/ie:PreviewUrl`
- `0x180088087`: `osd:OpenSearchDescription/osd:InputEncoding`
- `0x180088021`: `osd:OpenSearchDescription/osd:ShortName`
- `0x180088230`: `application/atom+xml`
- `0x18008821c`: `application/rss+xml`
- `0x18008838c`: `osd:OpenSearchDescription/ie:NTSearchSuggestion`
- `0x180088379`: `osd:OpenSearchDescription/ie:NTTopResult`
- `0x1800883b7`: `osd:OpenSearchDescription/ie:NTLogo`

## pseudocode

```c
__int64 __fastcall CSearchAddProviderHelper::_ParseProviderSource(CXMLDOMNode **this)
{
  CSearchAddProviderHelper *v1; // rdi
  CXMLDOMNode *v2; // rcx
  struct IXMLDOMDocument *v3; // rax
  struct IXMLDOMDocument *v4; // rsi
  unsigned int v5; // esi
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // r13
  WCHAR *v8; // r12
  OLECHAR *v9; // r15
  struct IUnknown *v10; // rbx
  OLECHAR *v11; // rax
  struct IUnknown *v12; // rbx
  OLECHAR *v13; // rax
  OLECHAR *v14; // rbx
  int v15; // ecx
  OLECHAR *v16; // rbx
  CSearchAddProviderHelper *v17; // rcx
  IUri *v18; // rdi
  WCHAR *v19; // rbx
  __int64 v20; // rax
  CSearchAddProviderHelper *v21; // rcx
  BOOL v22; // eax
  CSearchAddProviderHelper *v23; // rcx
  CSearchAddProviderHelper *v24; // rcx
  __int64 v25; // rax
  OLECHAR *v26; // rdi
  const WCHAR *v27; // rax
  OLECHAR *v28; // rbx
  unsigned __int16 *v29; // rsi
  OLECHAR *v30; // rbx
  const WCHAR *v31; // rax
  OLECHAR *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rax
  const WCHAR *v35; // rax
  __int64 v36; // rax
  CSearchAddProviderHelper *v37; // rsi
  OLECHAR *v38; // rdi
  unsigned __int64 v39; // rdx
  OLECHAR *v40; // rbx
  char v41; // al
  LPCWSTR v43; // [rsp+30h] [rbp-D0h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMNode *v45; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v46; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  LPCWSTR v49; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h]
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMDocument *v52; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v53; // [rsp+80h] [rbp-80h] BYREF
  CSearchAddProviderHelper *v54; // [rsp+88h] [rbp-78h] BYREF
  CSearchAddProviderHelper *v55; // [rsp+90h] [rbp-70h] BYREF
  BSTR v56; // [rsp+98h] [rbp-68h]
  LPCWSTR pszStr1; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v58[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v59[3]; // [rsp+C0h] [rbp-40h] BYREF
  CSearchAddProviderHelper *v60; // [rsp+D8h] [rbp-28h]
  BSTR IEExtendedUrlPropertyHelper; // [rsp+E0h] [rbp-20h]
  BSTR v62; // [rsp+E8h] [rbp-18h]
  BSTR v63; // [rsp+F0h] [rbp-10h]
  BSTR v64; // [rsp+F8h] [rbp-8h]
  BSTR v65; // [rsp+100h] [rbp+0h]
  struct IUnknown *v66[3]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v67[24]; // [rsp+120h] [rbp+20h] BYREF
  BSTR v68; // [rsp+138h] [rbp+38h]
  _QWORD v69[4]; // [rsp+140h] [rbp+40h] BYREF
  int v70; // [rsp+160h] [rbp+60h] BYREF
  int v71; // [rsp+164h] [rbp+64h]
  WCHAR pszPath[264]; // [rsp+1D0h] [rbp+D0h] BYREF

  v1 = (CSearchAddProviderHelper *)this;
  v60 = (CSearchAddProviderHelper *)this;
  v2 = this[75];
  pszStr1 = 0;
  v52 = 0;
  v3 = CXMLDOMNode::ownerDocument(v2);
  ATL::CComPtrBase<IProtectionUtil>::Attach(&v52, v3);
  v4 = v52;
  v45 = 0;
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, struct IXMLDOMNode **))v52->lpVtbl->selectSingleNode)(
    v52,
    L"osd:OpenSearchDescription/osd:Url",
    &v45);
  CXMLDOMNode::CXMLDOMNode((CXMLDOMNode *)v66, v45);
  if ( !CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v66, L"method", (unsigned __int16 **)&pszStr1)
    && !StrCmpICW(pszStr1, L"Post") )
  {
    if ( *((_DWORD *)v1 + 12) )
      ShellMessageBoxW(g_hinstMUI, *((HWND *)v1 + 5), (LPCWSTR)0x30DE, (LPCWSTR)0x3145, 0x40u);
    v5 = 1;
    goto LABEL_124;
  }
  v50 = 0;
  v46 = 0;
  v6 = 0;
  v47 = 0;
  v7 = 0;
  v43 = 0;
  v8 = 0;
  bstrString = 0;
  v9 = 0;
  v56 = 0;
  ATL::AtlComPtrAssign((struct IUnknown **)&v45, 0);
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, struct IXMLDOMNode **))v4->lpVtbl->selectSingleNode)(
    v4,
    L"osd:OpenSearchDescription/osd:ShortName",
    &v45);
  v10 = (struct IUnknown *)v45;
  CXMLDOMNode::Reset((CXMLDOMNode *)v66);
  ATL::AtlComPtrAssign(v66, v10);
  v11 = CXMLDOMNode::innerText((CXMLDOMNode *)v66);
  v62 = v11;
  if ( v11 )
    StrTrimW(v11, L" ");
  ATL::AtlComPtrAssign((struct IUnknown **)&v45, 0);
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, struct IXMLDOMNode **))v4->lpVtbl->selectSingleNode)(
    v4,
    L"osd:OpenSearchDescription/osd:InputEncoding",
    &v45);
  v12 = (struct IUnknown *)v45;
  CXMLDOMNode::Reset((CXMLDOMNode *)v66);
  ATL::AtlComPtrAssign(v66, v12);
  v13 = CXMLDOMNode::innerText((CXMLDOMNode *)v66);
  v68 = v13;
  v14 = v13;
  v48 = 1;
  if ( v13 )
  {
    StrTrimW(v13, L" ");
    ppURI = 0;
    if ( (int)IECreateInstance(
                &CLSID_CMultiLanguage,
                0,
                1u,
                &GUID_4e5868ab_b157_4623_9acc_6a1d9caebe04,
                (LPVOID *)&ppURI) >= 0 )
    {
      memset_0(&v70, 0, 0x6Cu);
      if ( ((int (__fastcall *)(IUri *, OLECHAR *, int *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, v14, &v70) >= 0 )
      {
        v15 = v70;
        if ( v71 )
          v15 = v71;
        v50 = v15;
      }
    }
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
  }
  v16 = 0;
  v55 = 0;
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, CSearchAddProviderHelper **))v4->lpVtbl->selectNodes)(
    v4,
    L"osd:OpenSearchDescription/osd:Url",
    &v55);
  v17 = v55;
  v54 = v55;
  if ( v55 )
  {
    (*(void (__fastcall **)(CSearchAddProviderHelper *))(*(_QWORD *)v55 + 8LL))(v55);
    ppURI = 0;
    v18 = 0;
    CXMLDOMNodeList::next(&v54, v58);
    if ( v58[0] )
    {
      do
      {
        v49 = 0;
        CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v58, L"type", (unsigned __int16 **)&v49);
        v19 = (WCHAR *)v49;
        if ( v49 )
        {
          if ( StrCmpICW(v49, L"text/html") )
          {
            if ( StrCmpICW(v19, L"application/rss+xml") && StrCmpICW(v19, L"application/atom+xml") )
            {
              if ( StrCmpICW(v19, L"application/x-suggestions+json") )
              {
                if ( !StrCmpICW(v19, L"application/x-suggestions+xml") && !v8 )
                {
                  CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v58, L"template", (unsigned __int16 **)&v43);
                  v8 = (WCHAR *)v43;
                }
              }
              else if ( !v7 )
              {
                CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v58, L"template", &v47);
                v7 = v47;
              }
            }
            else if ( !v18 )
            {
              CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v58, L"template", (unsigned __int16 **)&ppURI);
              v18 = ppURI;
            }
          }
          else if ( !v6 )
          {
            CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v58, L"template", (unsigned __int16 **)&v46);
            v6 = (unsigned __int16 *)v46;
          }
        }
        v20 = CXMLDOMNodeList::next(&v54, v67);
        CXMLDOMNode::operator=(v58, v20);
        CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v67);
        SysFreeString(v19);
      }
      while ( v58[0] );
      v4 = v52;
      if ( v6 )
      {
        v16 = 0;
LABEL_37:
        CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v58);
        SysFreeString((BSTR)v18);
        v1 = v60;
        goto LABEL_38;
      }
      v16 = 0;
    }
    if ( v18 )
    {
      v6 = (unsigned __int16 *)v18;
      v18 = 0;
    }
    goto LABEL_37;
  }
LABEL_38:
  IEExtendedUrlPropertyHelper = CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(
                                  v17,
                                  v4,
                                  L"osd:OpenSearchDescription/ie:PreviewUrl");
  v22 = v8 && *v8 || v7 && *v7;
  *((_DWORD *)v1 + 7) = v22;
  v65 = CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(
          v21,
          v4,
          L"osd:OpenSearchDescription/ie:NTSearchResult");
  v64 = CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(v23, v4, L"osd:OpenSearchDescription/ie:NTTopResult");
  v63 = CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(
          v24,
          v4,
          L"osd:OpenSearchDescription/ie:NTSearchSuggestion");
  ATL::AtlComPtrAssign((struct IUnknown **)&v45, 0);
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, struct IXMLDOMNode **))v4->lpVtbl->selectSingleNode)(
    v4,
    L"osd:OpenSearchDescription/ie:NTLogo",
    &v45);
  CXMLDOMNode::CXMLDOMNode((CXMLDOMNode *)v69, v45);
  if ( v69[0] )
  {
    v25 = *(_QWORD *)v69[0];
    v49 = 0;
    if ( !(*(unsigned int (__fastcall **)(_QWORD, LPCWSTR *))(v25 + 312))(v69[0], &v49)
      && !StrCmpICW(v49, L"http://schemas.microsoft.com/Search/2008/") )
    {
      v46 = 0;
      CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v69, L"type", (unsigned __int16 **)&v46);
      v26 = (OLECHAR *)v46;
      if ( v46 && !StrCmpICW(v46, L"image/png") )
      {
        v27 = CXMLDOMNode::innerText((CXMLDOMNode *)v69);
        v46 = 0;
        v28 = (OLECHAR *)v27;
        if ( CreateUri(v27, 0x3002B80u, 0, (IUri **)&v46) >= 0 )
        {
          LODWORD(v43) = -1;
          if ( (*(int (__fastcall **)(LPCWSTR, LPCWSTR *))(*(_QWORD *)v46 + 192LL))(v46, &v43) >= 0
            && ((_DWORD)v43 == 2 || (_DWORD)v43 == 11) )
          {
            v56 = v28;
            v28 = 0;
          }
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v46);
        SysFreeString(v28);
        v16 = 0;
      }
      SysFreeString(v26);
    }
    SysFreeString((BSTR)v49);
  }
  v53 = 0;
  ((void (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, unsigned __int16 **))v4->lpVtbl->selectNodes)(
    v4,
    L"osd:OpenSearchDescription/osd:Image",
    &v53);
  v29 = v53;
  v47 = v53;
  if ( v53 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v53 + 8LL))(v53);
  CXMLDOMNodeList::next(&v47, v59);
  while ( v59[0] )
  {
    v43 = 0;
    CXMLDOMNode::getStringAttribute((CXMLDOMNode *)v59, L"type", (unsigned __int16 **)&v43);
    v30 = (OLECHAR *)v43;
    if ( v43
      && (!StrCmpICW(v43, L"image/x-icon")
       || !StrCmpICW(v30, L"image/icon")
       || !StrCmpICW(v30, L"image/vnd.microsoft.icon")) )
    {
      v31 = CXMLDOMNode::innerText((CXMLDOMNode *)v59);
      ppURI = 0;
      v32 = (OLECHAR *)v31;
      if ( CreateUri(v31, 0x3002B80u, 0, &ppURI) >= 0 )
      {
        LODWORD(v43) = -1;
        if ( ((int (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetScheme)(ppURI, &v43) >= 0
          && ((_DWORD)v43 == 2 || (_DWORD)v43 == 11) )
        {
          bstrString = v32;
          v9 = v32;
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
          SysFreeString(0);
          SysFreeString(v30);
          v16 = 0;
          if ( v32 )
            goto LABEL_87;
          break;
        }
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
      SysFreeString(v32);
    }
    v33 = CXMLDOMNodeList::next(&v47, v67);
    CXMLDOMNode::operator=(v59, v33);
    CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v67);
    SysFreeString(v30);
    v16 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 80LL))(v29);
  v34 = CXMLDOMNodeList::next(&v47, v67);
  CXMLDOMNode::operator=(v59, v34);
  CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v67);
  while ( v59[0] )
  {
    v35 = CXMLDOMNode::innerText((CXMLDOMNode *)v59);
    ppURI = 0;
    v16 = (OLECHAR *)v35;
    if ( CreateUri(v35, 0x3002B80u, 0, &ppURI) >= 0 )
    {
      LODWORD(v43) = -1;
      if ( ((int (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetScheme)(ppURI, &v43) >= 0
        && ((_DWORD)v43 == 2 || (_DWORD)v43 == 11) )
      {
        bstrString = v16;
        v9 = v16;
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
        SysFreeString(0);
        if ( v16 )
        {
          LODWORD(v16) = 0;
          goto LABEL_87;
        }
        break;
      }
    }
    v36 = CXMLDOMNodeList::next(&v47, v67);
    CXMLDOMNode::operator=(v59, v36);
    CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v67);
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
    SysFreeString(v16);
    v16 = 0;
  }
  if ( !v6 )
    goto LABEL_125;
  if ( (int)CSearchUpgradeHelper::s_GetFavoriteIconURL(v6, &bstrString) >= 0 )
  {
    v9 = bstrString;
  }
  else
  {
    SysFreeString(bstrString);
    v9 = v16;
  }
LABEL_87:
  if ( !v6 || *v6 == (_WORD)v16 )
  {
LABEL_125:
    v40 = IEExtendedUrlPropertyHelper;
    v5 = -2147467259;
    v38 = v62;
  }
  else
  {
    LODWORD(v43) = (_DWORD)v16;
    StrTrimW(v6, L" ");
    v37 = v60;
    v38 = v62;
    (*(void (__fastcall **)(_QWORD, __int64, BSTR))(**((_QWORD **)v60 + 74) + 24LL))(*((_QWORD *)v60 + 74), 1, v62);
    (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)v37 + 74) + 24LL))(
      *((_QWORD *)v37 + 74),
      16,
      v6);
    if ( v7 && *v7 != (_WORD)v16 )
      (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)v37 + 74) + 24LL))(
        *((_QWORD *)v37 + 74),
        7,
        v7);
    if ( v8 && *v8 != (_WORD)v16 )
      (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)v37 + 74) + 24LL))(*((_QWORD *)v37 + 74), 18, v8);
    v40 = IEExtendedUrlPropertyHelper;
    if ( IEExtendedUrlPropertyHelper
      && *IEExtendedUrlPropertyHelper
      && CSearchManager::s_DomainsEqual(v6, IEExtendedUrlPropertyHelper) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, OLECHAR *))(**((_QWORD **)v37 + 74) + 24LL))(
        *((_QWORD *)v37 + 74),
        10,
        v40);
    }
    if ( v50 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v37 + 74) + 40LL))(*((_QWORD *)v37 + 74), 0);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD, __int64, OLECHAR *))(**((_QWORD **)v37 + 74) + 24LL))(
        *((_QWORD *)v37 + 74),
        5,
        v9);
    if ( v65 && *v65 )
      (*(void (__fastcall **)(_QWORD, __int64, BSTR))(**((_QWORD **)v37 + 74) + 24LL))(*((_QWORD *)v37 + 74), 19, v65);
    else
      LOBYTE(v48) = 0;
    if ( v64 && *v64 )
      (*(void (__fastcall **)(_QWORD, __int64, BSTR))(**((_QWORD **)v37 + 74) + 24LL))(*((_QWORD *)v37 + 74), 20, v64);
    else
      LOBYTE(v48) = 0;
    if ( v63 && *v63 )
      (*(void (__fastcall **)(_QWORD, __int64, BSTR))(**((_QWORD **)v37 + 74) + 24LL))(*((_QWORD *)v37 + 74), 21, v63);
    if ( v56 && *v56 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, BSTR))(**((_QWORD **)v37 + 74) + 24LL))(*((_QWORD *)v37 + 74), 23, v56);
      v41 = v48;
    }
    else
    {
      v41 = 0;
    }
    if ( v41 && (int)GetRootServicesPath(pszPath, v39) >= 0 && (int)EnsureServicesFolder(pszPath) >= 0 )
      (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)v37 + 74) + 24LL))(
        *((_QWORD *)v37 + 74),
        22,
        pszPath);
    v5 = (unsigned int)v43;
  }
  CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v59);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v47);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v53);
  CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v69);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v54);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v55);
  SysFreeString(v68);
  SysFreeString(v56);
  SysFreeString(v63);
  SysFreeString(v64);
  SysFreeString(v65);
  SysFreeString(v40);
  SysFreeString(v9);
  SysFreeString(v8);
  SysFreeString(v7);
  SysFreeString(v6);
  SysFreeString(v38);
LABEL_124:
  CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v66);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v45);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v52);
  SysFreeString((BSTR)pszStr1);
  return v5;
}

```

## disassembly

```asm
0x180087ef8  push    rbp
0x180087efa  push    rbx
0x180087efb  push    rsi
0x180087efc  push    rdi
0x180087efd  push    r12
0x180087eff  push    r13
0x180087f01  push    r14
0x180087f03  push    r15
0x180087f05  lea     rbp, [rsp-2F8h]
0x180087f0d  sub     rsp, 3F8h
0x180087f14  mov     rax, cs:__security_cookie
0x180087f1b  xor     rax, rsp
0x180087f1e  mov     [rbp+330h+var_50], rax
0x180087f25  mov     rdi, rcx
0x180087f28  mov     [rbp+330h+var_358], rcx
0x180087f2c  mov     rcx, [rcx+258h]; this
0x180087f33  xor     ebx, ebx
0x180087f35  mov     [rbp+330h+pszStr1], rbx
0x180087f39  mov     [rsp+430h+var_3B8], rbx
0x180087f3e  call    ?ownerDocument@CXMLDOMNode@@QEAAPEAUIXMLDOMDocument@@XZ; CXMLDOMNode::ownerDocument(void)
0x180087f43  mov     rdx, rax
0x180087f46  lea     rcx, [rsp+430h+var_3B8]
0x180087f4b  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x180087f50  mov     rsi, [rsp+430h+var_3B8]
0x180087f55  lea     r8, [rsp+430h+var_3F0]
0x180087f5a  mov     [rsp+430h+var_3F0], rbx
0x180087f5f  lea     rdx, aOsdOpensearchd_6; "osd:OpenSearchDescription/osd:Url"
0x180087f66  mov     rcx, rsi
0x180087f69  mov     rax, [rsi]
0x180087f6c  mov     rax, [rax+128h]
0x180087f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f78  mov     rdx, [rsp+430h+var_3F0]; struct IXMLDOMNode *
0x180087f7d  lea     rcx, [rbp+330h+var_328]; this
0x180087f81  call    ??0CXMLDOMNode@@QEAA@PEAUIXMLDOMNode@@@Z; CXMLDOMNode::CXMLDOMNode(IXMLDOMNode *)
0x180087f86  lea     r8, [rbp+330h+pszStr1]; unsigned __int16 **
0x180087f8a  lea     rdx, aMethod; "method"
0x180087f91  lea     rcx, [rbp+330h+var_328]; this
0x180087f95  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x180087f9a  test    eax, eax
0x180087f9c  jnz     short loc_180087FE5
0x180087f9e  mov     rcx, [rbp+330h+pszStr1]; pszStr1
0x180087fa2  lea     rdx, aPost_0; "Post"
0x180087fa9  call    cs:__imp_StrCmpICW
0x180087faf  test    eax, eax
0x180087fb1  jnz     short loc_180087FE5
0x180087fb3  cmp     [rdi+30h], ebx
0x180087fb6  jz      short loc_180087FDB
0x180087fb8  mov     rdx, [rdi+28h]; hWnd
0x180087fbc  mov     r9d, 3145h; lpcTitle
0x180087fc2  mov     rcx, cs:g_hinstMUI; hAppInst
0x180087fc9  mov     [rsp+430h+fuStyle], 40h ; '@'; fuStyle
0x180087fd1  lea     r8d, [r9-67h]; lpcText
0x180087fd5  call    cs:__imp_ShellMessageBoxW
0x180087fdb  mov     esi, 1
0x180087fe0  jmp     loc_180088A8F
0x180087fe5  xor     edx, edx; struct IUnknown *
0x180087fe7  mov     [rsp+430h+var_3C8], ebx
0x180087feb  lea     rcx, [rsp+430h+var_3F0]; struct IUnknown **
0x180087ff0  mov     [rsp+430h+var_3E8], rbx
0x180087ff5  mov     r14, rbx
0x180087ff8  mov     [rsp+430h+var_3E0], rbx
0x180087ffd  mov     r13, rbx
0x180088000  mov     [rsp+430h+var_400], rbx
0x180088005  mov     r12, rbx
0x180088008  mov     [rsp+430h+bstrString], rbx
0x18008800d  mov     r15, rbx
0x180088010  mov     [rbp+330h+var_398], rbx
0x180088014  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180088019  mov     rax, [rsi]
0x18008801c  lea     r8, [rsp+430h+var_3F0]
0x180088021  lea     rdx, aOsdOpensearchd_2; "osd:OpenSearchDescription/osd:ShortName"
0x180088028  mov     rcx, rsi
0x18008802b  mov     rax, [rax+128h]
0x180088032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088037  mov     rbx, [rsp+430h+var_3F0]
0x18008803c  lea     rcx, [rbp+330h+var_328]; this
0x180088040  call    ?Reset@CXMLDOMNode@@IEAAXXZ; CXMLDOMNode::Reset(void)
0x180088045  mov     rdx, rbx; struct IUnknown *
0x180088048  lea     rcx, [rbp+330h+var_328]; struct IUnknown **
0x18008804c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180088051  lea     rcx, [rbp+330h+var_328]; this
0x180088055  call    ?innerText@CXMLDOMNode@@QEAAPEAGXZ; CXMLDOMNode::innerText(void)
0x18008805a  mov     [rbp+330h+var_348], rax
0x18008805e  test    rax, rax
0x180088061  jz      short loc_180088073
0x180088063  lea     rdx, pszTrimChars; " "
0x18008806a  mov     rcx, rax; psz
0x18008806d  call    cs:__imp_StrTrimW
0x180088073  xor     edx, edx; struct IUnknown *
0x180088075  lea     rcx, [rsp+430h+var_3F0]; struct IUnknown **
0x18008807a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18008807f  mov     rax, [rsi]
0x180088082  lea     r8, [rsp+430h+var_3F0]
0x180088087  lea     rdx, aOsdOpensearchd_7; "osd:OpenSearchDescription/osd:InputEnco"...
0x18008808e  mov     rcx, rsi
0x180088091  mov     rax, [rax+128h]
0x180088098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008809d  mov     rbx, [rsp+430h+var_3F0]
0x1800880a2  lea     rcx, [rbp+330h+var_328]; this
0x1800880a6  call    ?Reset@CXMLDOMNode@@IEAAXXZ; CXMLDOMNode::Reset(void)
0x1800880ab  mov     rdx, rbx; struct IUnknown *
0x1800880ae  lea     rcx, [rbp+330h+var_328]; struct IUnknown **
0x1800880b2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800880b7  lea     rcx, [rbp+330h+var_328]; this
0x1800880bb  call    ?innerText@CXMLDOMNode@@QEAAPEAGXZ; CXMLDOMNode::innerText(void)
0x1800880c0  mov     [rbp+330h+var_2F8], rax
0x1800880c4  mov     rbx, rax
0x1800880c7  mov     [rsp+430h+var_3D8], 1
0x1800880cf  test    rax, rax
0x1800880d2  jz      loc_180088158
0x1800880d8  lea     rdx, pszTrimChars; " "
0x1800880df  mov     rcx, rax; psz
0x1800880e2  call    cs:__imp_StrTrimW
0x1800880e8  xor     edx, edx; pUnkOuter
0x1800880ea  mov     [rsp+430h+ppURI], r12
0x1800880ef  lea     rax, [rsp+430h+ppURI]
0x1800880f4  lea     r9, _GUID_4e5868ab_b157_4623_9acc_6a1d9caebe04; riid
0x1800880fb  mov     qword ptr [rsp+430h+fuStyle], rax; LPVOID *
0x180088100  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180088107  lea     r8d, [rdx+1]; dwClsContext
0x18008810b  call    IECreateInstance
0x180088110  test    eax, eax
0x180088112  js      short loc_18008814E
0x180088114  xor     edx, edx; Val
0x180088116  lea     rcx, [rbp+330h+var_2D0]; void *
0x18008811a  lea     r8d, [rdx+6Ch]; Size
0x18008811e  call    memset_0
0x180088123  mov     rcx, [rsp+430h+ppURI]
0x180088128  lea     r8, [rbp+330h+var_2D0]
0x18008812c  mov     rdx, rbx
0x18008812f  mov     rax, [rcx]
0x180088132  mov     rax, [rax+38h]
0x180088136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008813b  test    eax, eax
0x18008813d  js      short loc_18008814E
0x18008813f  mov     eax, [rbp+330h+var_2CC]
0x180088142  test    eax, eax
0x180088144  mov     ecx, [rbp+330h+var_2D0]
0x180088147  cmovnz  ecx, eax
0x18008814a  mov     [rsp+430h+var_3C8], ecx
0x18008814e  lea     rcx, [rsp+430h+ppURI]; void *
0x180088153  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180088158  xor     ebx, ebx
0x18008815a  lea     r8, [rbp+330h+var_3A0]
0x18008815e  mov     [rbp+330h+var_3A0], rbx
0x180088162  lea     rdx, aOsdOpensearchd_6; "osd:OpenSearchDescription/osd:Url"
0x180088169  mov     rax, [rsi]
0x18008816c  mov     rcx, rsi
0x18008816f  mov     rax, [rax+120h]
0x180088176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008817b  mov     rcx, [rbp+330h+var_3A0]
0x18008817f  mov     [rbp+330h+var_3A8], rcx
0x180088183  test    rcx, rcx
0x180088186  jz      loc_180088333
0x18008818c  mov     rax, [rcx]
0x18008818f  mov     rax, [rax+8]
0x180088193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088198  lea     rdx, [rbp+330h+var_388]
0x18008819c  mov     [rsp+430h+ppURI], rbx
0x1800881a1  lea     rcx, [rbp+330h+var_3A8]
0x1800881a5  mov     edi, ebx
0x1800881a7  call    ?next@CXMLDOMNodeList@@QEAA?AVCXMLDOMNode@@XZ; CXMLDOMNodeList::next(void)
0x1800881ac  cmp     [rbp+330h+var_388], rbx
0x1800881b0  jz      loc_18008830E
0x1800881b6  xor     esi, esi
0x1800881b8  lea     r8, [rsp+430h+var_3D0]; unsigned __int16 **
0x1800881bd  mov     [rsp+430h+var_3D0], rsi
0x1800881c2  lea     rdx, aType; "type"
0x1800881c9  lea     rcx, [rbp+330h+var_388]; this
0x1800881cd  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x1800881d2  mov     rbx, [rsp+430h+var_3D0]
0x1800881d7  test    rbx, rbx
0x1800881da  jz      loc_1800882CD
0x1800881e0  lea     rdx, pszContentType; "text/html"
0x1800881e7  mov     rcx, rbx; pszStr1
0x1800881ea  call    cs:__imp_StrCmpICW
0x1800881f0  test    eax, eax
0x1800881f2  jnz     short loc_18008821C
0x1800881f4  test    r14, r14
0x1800881f7  jnz     loc_1800882CD
0x1800881fd  lea     r8, [rsp+430h+var_3E8]; unsigned __int16 **
0x180088202  lea     rdx, aTemplate; "template"
0x180088209  lea     rcx, [rbp+330h+var_388]; this
0x18008820d  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x180088212  mov     r14, [rsp+430h+var_3E8]
0x180088217  jmp     loc_1800882CD
0x18008821c  lea     rdx, aApplicationRss; "application/rss+xml"
0x180088223  mov     rcx, rbx; pszStr1
0x180088226  call    cs:__imp_StrCmpICW
0x18008822c  test    eax, eax
0x18008822e  jz      short loc_1800882AE
0x180088230  lea     rdx, aApplicationAto; "application/atom+xml"
0x180088237  mov     rcx, rbx; pszStr1
0x18008823a  call    cs:__imp_StrCmpICW
0x180088240  test    eax, eax
0x180088242  jz      short loc_1800882AE
0x180088244  lea     rdx, aApplicationXSu_0; "application/x-suggestions+json"
0x18008824b  mov     rcx, rbx; pszStr1
0x18008824e  call    cs:__imp_StrCmpICW
0x180088254  test    eax, eax
0x180088256  jnz     short loc_180088279
0x180088258  test    r13, r13
0x18008825b  jnz     short loc_1800882CD
0x18008825d  lea     r8, [rsp+430h+var_3E0]; unsigned __int16 **
0x180088262  lea     rdx, aTemplate; "template"
0x180088269  lea     rcx, [rbp+330h+var_388]; this
0x18008826d  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x180088272  mov     r13, [rsp+430h+var_3E0]
0x180088277  jmp     short loc_1800882CD
0x180088279  lea     rdx, aApplicationXSu; "application/x-suggestions+xml"
0x180088280  mov     rcx, rbx; pszStr1
0x180088283  call    cs:__imp_StrCmpICW
0x180088289  test    eax, eax
0x18008828b  jnz     short loc_1800882CD
0x18008828d  test    r12, r12
0x180088290  jnz     short loc_1800882CD
0x180088292  lea     r8, [rsp+430h+var_400]; unsigned __int16 **
0x180088297  lea     rdx, aTemplate; "template"
0x18008829e  lea     rcx, [rbp+330h+var_388]; this
0x1800882a2  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x1800882a7  mov     r12, [rsp+430h+var_400]
0x1800882ac  jmp     short loc_1800882CD
0x1800882ae  test    rdi, rdi
0x1800882b1  jnz     short loc_1800882CD
0x1800882b3  lea     r8, [rsp+430h+ppURI]; unsigned __int16 **
0x1800882b8  lea     rdx, aTemplate; "template"
0x1800882bf  lea     rcx, [rbp+330h+var_388]; this
0x1800882c3  call    ?getStringAttribute@CXMLDOMNode@@QEAAJPEBGPEAPEAG@Z; CXMLDOMNode::getStringAttribute(ushort const *,ushort * *)
0x1800882c8  mov     rdi, [rsp+430h+ppURI]
0x1800882cd  lea     rdx, [rbp+330h+var_310]
0x1800882d1  lea     rcx, [rbp+330h+var_3A8]
0x1800882d5  call    ?next@CXMLDOMNodeList@@QEAA?AVCXMLDOMNode@@XZ; CXMLDOMNodeList::next(void)
0x1800882da  mov     rdx, rax
0x1800882dd  lea     rcx, [rbp+330h+var_388]
0x1800882e1  call    ??4CXMLDOMNode@@QEAAAEAV0@$$QEAV0@@Z; CXMLDOMNode::operator=(CXMLDOMNode &&)
0x1800882e6  lea     rcx, [rbp+330h+var_310]; this
0x1800882ea  call    ??1CXMLDOMNode@@QEAA@XZ; CXMLDOMNode::~CXMLDOMNode(void)
0x1800882ef  mov     rcx, rbx; bstrString
0x1800882f2  call    cs:__imp_SysFreeString
0x1800882f8  cmp     [rbp+330h+var_388], rsi
0x1800882fc  jnz     loc_1800881B8
0x180088302  mov     rsi, [rsp+430h+var_3B8]
0x180088307  test    r14, r14
0x18008830a  jnz     short loc_18008831B
0x18008830c  xor     ebx, ebx
0x18008830e  test    rdi, rdi
0x180088311  jz      short loc_18008831D
0x180088313  mov     r14, rdi
0x180088316  mov     rdi, rbx
0x180088319  jmp     short loc_18008831D
0x18008831b  xor     ebx, ebx
0x18008831d  lea     rcx, [rbp+330h+var_388]; this
0x180088321  call    ??1CXMLDOMNode@@QEAA@XZ; CXMLDOMNode::~CXMLDOMNode(void)
0x180088326  mov     rcx, rdi; bstrString
0x180088329  call    cs:__imp_SysFreeString
0x18008832f  mov     rdi, [rbp+330h+var_358]
0x180088333  lea     r8, aOsdOpensearchd; "osd:OpenSearchDescription/ie:PreviewUrl"
0x18008833a  mov     rdx, rsi; struct IXMLDOMDocument *
0x18008833d  call    ?_GetIEExtendedUrlPropertyHelper@CSearchAddProviderHelper@@AEAAPEAGPEAUIXMLDOMDocument@@PEBG@Z; CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(IXMLDOMDocument *,ushort const *)
0x180088342  mov     [rbp+330h+var_350], rax
0x180088346  test    r12, r12
0x180088349  jz      short loc_180088352
0x18008834b  cmp     [r12], bx
0x180088350  jnz     short loc_18008835E
0x180088352  test    r13, r13
0x180088355  jz      short loc_180088365
0x180088357  cmp     [r13+0], bx
0x18008835c  jz      short loc_180088365
0x18008835e  mov     eax, 1
0x180088363  jmp     short loc_180088367
0x180088365  mov     eax, ebx
0x180088367  lea     r8, aOsdOpensearchd_1; "osd:OpenSearchDescription/ie:NTSearchRe"...
0x18008836e  mov     [rdi+1Ch], eax
0x180088371  mov     rdx, rsi; struct IXMLDOMDocument *
0x180088374  call    ?_GetIEExtendedUrlPropertyHelper@CSearchAddProviderHelper@@AEAAPEAGPEAUIXMLDOMDocument@@PEBG@Z; CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(IXMLDOMDocument *,ushort const *)
0x180088379  lea     r8, aOsdOpensearchd_4; "osd:OpenSearchDescription/ie:NTTopResul"...
0x180088380  mov     [rbp+330h+var_330], rax
0x180088384  mov     rdx, rsi; struct IXMLDOMDocument *
0x180088387  call    ?_GetIEExtendedUrlPropertyHelper@CSearchAddProviderHelper@@AEAAPEAGPEAUIXMLDOMDocument@@PEBG@Z; CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(IXMLDOMDocument *,ushort const *)
0x18008838c  lea     r8, aOsdOpensearchd_3; "osd:OpenSearchDescription/ie:NTSearchSu"...
0x180088393  mov     [rbp+330h+var_338], rax
0x180088397  mov     rdx, rsi; struct IXMLDOMDocument *
0x18008839a  call    ?_GetIEExtendedUrlPropertyHelper@CSearchAddProviderHelper@@AEAAPEAGPEAUIXMLDOMDocument@@PEBG@Z; CSearchAddProviderHelper::_GetIEExtendedUrlPropertyHelper(IXMLDOMDocument *,ushort const *)
0x18008839f  xor     edx, edx; struct IUnknown *
0x1800883a1  mov     [rbp+330h+var_340], rax
0x1800883a5  lea     rcx, [rsp+430h+var_3F0]; struct IUnknown **
0x1800883aa  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800883af  mov     rax, [rsi]
0x1800883b2  lea     r8, [rsp+430h+var_3F0]
0x1800883b7  lea     rdx, aOsdOpensearchd_0; "osd:OpenSearchDescription/ie:NTLogo"
0x1800883be  mov     rcx, rsi
0x1800883c1  mov     rax, [rax+128h]
0x1800883c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800883cd  mov     rdx, [rsp+430h+var_3F0]; struct IXMLDOMNode *
0x1800883d2  lea     rcx, [rbp+330h+var_2F0]; this
0x1800883d6  call    ??0CXMLDOMNode@@QEAA@PEAUIXMLDOMNode@@@Z; CXMLDOMNode::CXMLDOMNode(IXMLDOMNode *)
0x1800883db  mov     rcx, [rbp+330h+var_2F0]
0x1800883df  test    rcx, rcx
0x1800883e2  jz      loc_1800884EF
0x1800883e8  mov     rax, [rcx]
  ... truncated ...
```
