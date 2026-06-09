# CDocObjectHost::_MayHaveVirus(_GUID const &,_GUID const &,int)

- ea: `0x18008818c`
- end: `0x180088cdd`
- name: `?_MayHaveVirus@CDocObjectHost@@IEAAJAEBU_GUID@@0H@Z`
- size: `2897`
- prototype: `__int64 __fastcall(CDocObjectHost *__hidden this, const struct _GUID *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800af534`

## callees

- `0x180005030`
- `0x180007010`
- `0x180015644`
- `0x1800423a4`
- `0x180046a50`
- `0x18005a24c`
- `0x1800692fc`
- `0x18008818c`
- `0x180097dfc`
- `0x1800c00d6`
- `0x1800f0228`
- `0x1800f0a9c`
- `0x1800f0bb0`
- `0x1800f1310`
- `0x1800f381c`
- `0x1800f4aa8`
- `0x1801435d4`
- `0x1801436b0`
- `0x1801437a0`
- `0x180145958`
- `0x1801533b8`
- `0x180154c0c`
- `0x1801f7694`
- `0x18057d9fc`
- `0x180580664`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800883cb`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800883cb`
- `msvcrt!_wcsicmp` at `0x180088616`
- `msvcrt!_wcsicmp` at `0x18008863d`
- `msvcrt!_wcsicmp` at `0x180088660`
- `msvcrt!_wcsicmp` at `0x180088616`
- `msvcrt!_wcsicmp` at `0x18008863d`
- `msvcrt!_wcsicmp` at `0x180088660`
- `KERNEL32!LocalFree` at `0x180088c88`
- `KERNEL32!LocalFree` at `0x180088c88`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180088519`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180088519`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180088494`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180088494`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1800884cc`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1800884cc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800882c9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800882c9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800885c0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800887ac`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800885c0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800887ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180088873`
- `OLEAUT32!__imp_SysFreeString` at `0x180088873`
- `iertutil!CreateUri` at `0x1800887dd`
- `iertutil!CreateUri` at `0x1800887dd`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x18008823d`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x18008837a`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x18008823d`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x18008837a`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180088330`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180088a00`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180088330`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180088a00`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x180088a15`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x180088a15`
- `urlmon!QueryAssociations` at `0x1800882f2`
- `urlmon!QueryAssociations` at `0x180088733`
- `urlmon!QueryAssociations` at `0x1800882f2`
- `urlmon!QueryAssociations` at `0x180088733`
- `urlmon!__imp_?IEZoneCheckUrlExW@@YAJPEBGPEAKK1KKKPEAUIInternetSecurityMgrSite@@@Z` at `0x1800889ae`
- `urlmon!__imp_?IEZoneCheckUrlExW@@YAJPEBGPEAKK1KKKPEAUIInternetSecurityMgrSite@@@Z` at `0x1800889ae`

## string_xrefs

- `0x180088826`: `OpenAsReadOnly`
- `0x180088656`: `Application.Manifest`

## pseudocode

```c
__int64 __fastcall CDocObjectHost::_MayHaveVirus(
        CDocObjectHost *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        int a4)
{
  IID v4; // xmm0
  WCHAR *v8; // r14
  unsigned int v9; // r12d
  unsigned int v10; // eax
  bool v11; // zf
  int v12; // esi
  __int64 v13; // rax
  BOOL v14; // edi
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rcx
  int v17; // edi
  const WCHAR *v18; // rcx
  LPWSTR ExtensionW; // rax
  unsigned __int16 *v20; // rdi
  unsigned int v21; // r15d
  unsigned int v22; // edi
  int v23; // eax
  int v24; // ecx
  BOOL v25; // esi
  const wchar_t *v26; // r15
  int v27; // r13d
  int v28; // eax
  unsigned __int16 *v29; // rdx
  int v30; // ecx
  _WORD *v31; // rax
  int v32; // edi
  const wchar_t *v33; // rcx
  int v34; // edi
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  int ExtensionFromURL; // eax
  int v38; // eax
  const unsigned __int16 *v39; // r8
  unsigned int DownloadDlgOptionsFromBinding; // r15d
  unsigned int v41; // r12d
  int (__fastcall ***v42)(_QWORD, GUID *, IUri **); // rcx
  unsigned int UrlAction; // eax
  bool v44; // sf
  unsigned int v45; // r9d
  unsigned int v46; // eax
  unsigned int MayOpenSafeOpenDialog; // eax
  char v48; // al
  LPSTREAM *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v53; // [rsp+A0h] [rbp-80h] BYREF
  int v54; // [rsp+A4h] [rbp-7Ch] BYREF
  void *ppv; // [rsp+A8h] [rbp-78h] BYREF
  unsigned __int16 *v56; // [rsp+B0h] [rbp-70h]
  LPCWSTR pszStr2; // [rsp+B8h] [rbp-68h] BYREF
  int v58; // [rsp+C0h] [rbp-60h]
  int v59; // [rsp+C4h] [rbp-5Ch]
  IUri *ppURI; // [rsp+C8h] [rbp-58h] BYREF
  DWORD cbData[2]; // [rsp+D0h] [rbp-50h] BYREF
  LPOLESTR lpszProgID; // [rsp+D8h] [rbp-48h] BYREF
  DWORD Type; // [rsp+E0h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+E4h] [rbp-3Ch] BYREF
  LPCWSTR pwzURI; // [rsp+E8h] [rbp-38h]
  int v66; // [rsp+F0h] [rbp-30h]
  int v67; // [rsp+F4h] [rbp-2Ch]
  HKEY hKey; // [rsp+F8h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+100h] [rbp-20h] BYREF
  LPOLESTR v70; // [rsp+108h] [rbp-18h] BYREF
  unsigned __int16 *v71; // [rsp+110h] [rbp-10h]
  unsigned __int16 *v72; // [rsp+118h] [rbp-8h]
  WCHAR pszSrch[264]; // [rsp+120h] [rbp+0h] BYREF
  unsigned __int16 v74[2088]; // [rsp+330h] [rbp+210h] BYREF

  v4 = *a2;
  v66 = a4;
  *(_QWORD *)cbData = 0;
  v8 = 0;
  pszStr2 = 0;
  v9 = -2147467259;
  v10 = *((_DWORD *)this + 162) & 0x20;
  lpszProgID = 0;
  v11 = (*((_DWORD *)this + 535) & 0x100) == 0;
  v70 = 0;
  v67 = v10 >> 5;
  *((IID *)this + 134) = v4;
  if ( !v11 )
    goto LABEL_157;
  v12 = 0;
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_IEXMLDocument.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_IEXMLDocument.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_IEXMLDocument.Data4;
  v14 = v13 == 0;
  if ( ProgIDFromCLSID(a2, &lpszProgID) >= 0 || v14 )
  {
    if ( lpszProgID )
    {
      v12 = IsHtmlProgID(lpszProgID);
      if ( !v12 )
        goto LABEL_8;
    }
    else
    {
      if ( !v14 )
        goto LABEL_8;
      v12 = 1;
    }
    *((_DWORD *)this + 535) |= 0x800u;
    v28 = *((_DWORD *)this + 162);
    if ( (v28 & 0x10000000) == 0 && (*((_DWORD *)this + 535) & 0x400) == 0 )
    {
      v9 = 0;
      *((_DWORD *)this + 162) = v28 | 0x8000000;
      goto LABEL_157;
    }
  }
LABEL_8:
  if ( (int)CDocObjectHost::_GetCurrentPage(this, v74, 0x824u, 1) >= 0 )
  {
    v15 = (unsigned __int16 *)*((_QWORD *)this + 260);
    v16 = v74;
    v54 = 0;
    v17 = 0;
    pwzURI = v74;
    if ( v15 )
    {
      if ( *v15 )
        v16 = v15;
      pwzURI = v16;
    }
    v18 = (const WCHAR *)*((_QWORD *)this + 261);
    if ( v18 )
    {
      ExtensionW = PathFindExtensionW(v18);
      *(_QWORD *)cbData = ExtensionW;
      v8 = ExtensionW;
      if ( *ExtensionW )
      {
        if ( (int)QueryAssociations(1, 2, ExtensionW, &pszStr2) >= 0 )
        {
          v54 = 1;
          v17 = IsHtmlProgID(pszStr2);
        }
      }
    }
    if ( v12
      || v17
      || !(unsigned int)IsIExploreProcess()
      || LCIEIsComponentSharedFlagValueSet_FromComponentThread(0x1000000u) )
    {
      v20 = 0;
      v11 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1;
      v59 = 0;
      LODWORD(ppv) = 0;
      v58 = 0;
      v72 = 0;
      v71 = 0;
      if ( !v11 || *(_QWORD *)a3->Data4 != *(_QWORD *)GUID_NULL.Data4 )
      {
        if ( ProgIDFromCLSID(a3, &v70) >= 0 )
          v20 = v70;
        v71 = v20;
      }
      v56 = lpszProgID;
      if ( lpszProgID )
      {
        v21 = 0;
        v53 = 0;
        if ( !v54 )
        {
          v30 = *((_DWORD *)this + 162);
          v25 = 0;
          if ( (v30 & 0x10000000) == 0 )
          {
            v26 = lpszProgID;
            goto LABEL_79;
          }
          LOBYTE(v21) = v8 != 0;
          v53 = v21;
          *((_DWORD *)this + 162) = v30 & 0xF7FFFFFF | ((v21 ^ 1) << 27);
LABEL_49:
          v11 = v21 == 0;
          v26 = v56;
          if ( v11 )
            goto LABEL_79;
LABEL_50:
          v27 = (int)ppv;
          goto LABEL_51;
        }
        v22 = RestrictShellExecute(v8);
        v23 = StrCmpICW(lpszProgID, pszStr2);
        v24 = *((_DWORD *)this + 162);
        v25 = v23 != 0;
        if ( (v24 & 0x10000000) != 0 )
        {
          v26 = pszStr2;
          v27 = 1;
          v56 = (unsigned __int16 *)pszStr2;
          *((_DWORD *)this + 162) = v24 & 0xF7FFFFFF;
          goto LABEL_51;
        }
        if ( !v23 )
        {
          v26 = v56;
          *((_DWORD *)this + 162) = v24 & 0xF7FFFFFF;
LABEL_79:
          v34 = v54;
LABEL_80:
          if ( (unsigned int)IsRelatedMime(*((const unsigned __int16 **)this + 262), a2)
            && (unsigned int)MIME_GetExtensionW(*((_QWORD *)this + 262), pszSrch, 260) )
          {
            *((_QWORD *)this + 263) = StrDupW(pszSrch);
          }
          if ( v34 )
          {
            ppURI = 0;
            if ( CreateUri(pwzURI, 0x3002B80u, 0, &ppURI) >= 0 )
            {
              bstrString = 0;
              if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &bstrString) >= 0 )
              {
                v38 = *((_DWORD *)this + 163);
                v54 = 0;
                if ( (v38 & 0x400) == 0 || (v39 = L"OpenAsReadOnly", (v38 & 0x800) == 0) )
                  v39 = 0;
                if ( (int)CDownloadUtilities::ExtensionHandlerSupportsDirectInvoke(
                            bstrString,
                            pszStr2,
                            v39,
                            (enum DIRECT_INVOKE_OPTIONS *)&v54) >= 0
                  && (v54 & 1) != 0
                  && ((*((_DWORD *)this + 163) & 0x400) != 0 || (v54 & 2) != 0) )
                {
                  *((_DWORD *)this + 162) &= ~0x8000000u;
                  v58 = 1;
                }
              }
              SysFreeString(bstrString);
            }
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
          }
          goto LABEL_50;
        }
        hKey = 0;
        Type = 0;
        *(_DWORD *)Data = 0;
        cbData[0] = 4;
        if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, lpszProgID, 0, 1u, &hKey) )
          goto LABEL_160;
        if ( !RegQueryValueExW(hKey, L"PreferExecuteOnMismatch", 0, &Type, Data, cbData) && Type == 4 && *(_DWORD *)Data )
        {
          v29 = (unsigned __int16 *)pszStr2;
          v25 = 0;
          *((_DWORD *)this + 162) &= ~0x8000000u;
          v21 = v22;
          LODWORD(ppv) = 1;
        }
        else
        {
          v29 = v56;
        }
        v56 = v29;
        v53 = v21;
        RegCloseKey(hKey);
        if ( !(_DWORD)ppv )
        {
LABEL_160:
          if ( (unsigned int)IsLinked(pszStr2, a2, v8) )
          {
            *((_DWORD *)this + 162) &= ~0x8000000u;
            v25 = 0;
          }
          else
          {
            v72 = (unsigned __int16 *)pszStr2;
          }
          goto LABEL_49;
        }
        v26 = v56;
        v27 = (int)ppv;
      }
      else
      {
        v34 = v54;
        v35 = *((_DWORD *)this + 162);
        if ( !v54 )
        {
          v56 = 0;
          v53 = 1;
          v25 = 1;
          v26 = 0;
          if ( (v35 & 0x10000000) == 0 && !*((_QWORD *)this + 261) )
          {
            if ( pwzURI )
            {
              ExtensionFromURL = CDownloadUtilities::GetExtensionFromURL(
                                   pwzURI,
                                   *((_DWORD *)this + 156),
                                   (unsigned __int16 **)cbData);
              v8 = *(WCHAR **)cbData;
              if ( ExtensionFromURL )
              {
                v59 = 1;
                if ( (int)QueryAssociations(1, 2, *(_QWORD *)cbData, &pszStr2) >= 0 )
                {
                  if ( (unsigned int)IsLinked(pszStr2, a2, v8) )
                  {
                    v26 = pszStr2;
                    v25 = 0;
                    v56 = (unsigned __int16 *)pszStr2;
                    v53 = 0;
                    goto LABEL_80;
                  }
                }
              }
            }
          }
          goto LABEL_50;
        }
        v26 = pszStr2;
        v25 = 0;
        v53 = 0;
        v36 = pszStr2;
        v56 = (unsigned __int16 *)pszStr2;
        *((_DWORD *)this + 162) = v35 & 0xF7FFFFFF;
        if ( (unsigned int)IsLinked(v36, a2, v8) && (*((_DWORD *)this + 162) & 0x10000000) == 0 )
          goto LABEL_80;
        v27 = 1;
      }
LABEL_51:
      v31 = (_WORD *)*((_QWORD *)this + 263);
      if ( (!v31 || !*v31) && !v59 && v8 && *v8 )
        *((_QWORD *)this + 263) = StrDupW(v8);
      v32 = *((_DWORD *)this + 184);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX>::GetImpl'::`2'::impl)
        && !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_BLOCK_CLICKONCE) )
      {
        v33 = (const wchar_t *)*((_QWORD *)this + 262);
        if ( v33 )
        {
          if ( !_wcsicmp(v33, L"application/x-ms-application") )
            goto LABEL_155;
        }
        if ( v8 && *v8 && !_wcsicmp(v8, L".application") || v26 && !_wcsicmp(v26, L"Application.Manifest") )
          goto LABEL_155;
      }
      ppv = 0;
      CDocObjectHost::QueryInterface(this, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      DownloadDlgOptionsFromBinding = CDownloadUtilities::GetDownloadDlgOptionsFromBinding(*((struct IBinding **)this
                                                                                           + 251));
      if ( !DownloadDlgOptionsFromBinding )
        DownloadDlgOptionsFromBinding = CDownloadUtilities::GetDownloadDlgOptionsFromMetaTag((struct IUnknown *)ppv);
      v41 = v53;
      if ( (DownloadDlgOptionsFromBinding & 2) != 0 )
        v41 = 1;
      if ( (*((_DWORD *)this + 162) & 0x200) == 0 )
      {
        v42 = (int (__fastcall ***)(_QWORD, GUID *, IUri **))*((_QWORD *)this + 251);
        if ( v42 )
        {
          ppURI = 0;
          if ( (**v42)(v42, &GUID_79eac9d8_bafa_11ce_8c82_00aa004ba90b, &ppURI) >= 0 )
          {
            v54 = 0;
            v53 = 4;
            ((void (__fastcall *)(IUri *, __int64, int *, unsigned int *, _QWORD, _QWORD))ppURI->lpVtbl->GetPropertyLength)(
              ppURI,
              536870931,
              &v54,
              &v53,
              0,
              0);
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
        }
        if ( v41 || v27 || v58 )
        {
          v32 = 5;
          *((_DWORD *)this + 184) = 5;
        }
        else
        {
          v53 = 0;
          if ( !v8 )
            goto LABEL_161;
          UrlAction = AssocGetUrlAction(v8);
          v44 = (int)IEZoneCheckUrlExW(v74, &v53, 4u, 0, 0, UrlAction, 1u, 0) < 0;
          v46 = v53;
          if ( !v44 )
          {
            v46 = v53 & 0xF;
            v53 = v46;
          }
          if ( v46 == 3 )
          {
            CDownloadUtilities::ProcessStartbindingError(0, 0, 0, v45, -2147024891, pwzURI);
            v32 = 2;
            *((_DWORD *)this + 184) = 2;
          }
          else
          {
LABEL_161:
            if ( !LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
              LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 7u);
            MayOpenSafeOpenDialog = CDownloadUtilities::MayOpenSafeOpenDialog(
                                      *((HWND *)this + 16),
                                      v56,
                                      pwzURI,
                                      0,
                                      *((const unsigned __int16 **)this + 261),
                                      *((unsigned int *)this + 530),
                                      *((_DWORD *)this + 156),
                                      (struct IUnknown *)ppv,
                                      *((struct IOleCommandTarget **)this + 49),
                                      v25,
                                      0,
                                      v72,
                                      v71,
                                      v67,
                                      v66,
                                      -__CFSHR__(*((_DWORD *)this + 162) | (*((_DWORD *)this + 535) << 18), 29),
                                      0,
                                      DownloadDlgOptionsFromBinding,
                                      (unsigned int *)this + 185);
            *((_DWORD *)this + 162) |= 0x200u;
            v32 = MayOpenSafeOpenDialog;
            *((_DWORD *)this + 184) = MayOpenSafeOpenDialog;
          }
        }
      }
      IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&ppv);
      *((_DWORD *)this + 535) &= ~0x400u;
      *((_BYTE *)this + 2162) = 0;
      if ( (*((_BYTE *)this + 640) & 8) != 0 && !*((_QWORD *)this + 50) )
      {
        v32 = 2;
LABEL_144:
        if ( (*((_DWORD *)this + 162) & 0x40000) == 0 )
        {
          v50 = *((_QWORD *)this + 49);
          if ( v50 )
            (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v50 + 32LL))(v50, &CGID_Explorer, 107);
          VirtualTab_NewTabShouldExit(0);
        }
        if ( v32 != 1 && v32 != 4358 && v32 != 5 )
          *((_DWORD *)this + 162) |= 0x8000000u;
        v51 = *((_QWORD *)this + 49);
        if ( v51 )
          (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v51 + 32LL))(v51, &CGID_Explorer, 93);
        v9 = -2147023673;
        goto LABEL_155;
      }
      switch ( v32 )
      {
        case 1:
          *((_DWORD *)this + 162) |= 0x20u;
          if ( v27 || v41 || v58 )
            goto LABEL_126;
          if ( (*((_DWORD *)this + 163) & 0x200) == 0 )
            CDocObjectHost::_SetDownloadNotification(this);
          break;
        case 2:
          goto LABEL_144;
        case 5:
          *((_DWORD *)this + 162) &= ~0x200u;
          if ( v27 || v41 || v58 )
            goto LABEL_126;
          break;
        case 4358:
          goto LABEL_127;
        case 4402:
LABEL_126:
          *((_BYTE *)this + 2162) = 1;
LABEL_127:
          *((_BYTE *)this + 2160) = 1;
          if ( v32 == 4358 || (v48 = 0, v32 == 4402) )
            v48 = 1;
          *((_BYTE *)this + 2161) = v48;
          v49 = (LPSTREAM *)operator new(8u);
          if ( v49 )
            *v49 = 0;
          else
            v49 = 0;
          *((_QWORD *)this + 271) = v49;
          if ( v49 )
            CoMarshalInterThreadInterfaceInStream_0(&IID_IBindCtx, *((LPUNKNOWN *)this + 252), v49);
          goto LABEL_144;
        default:
          goto LABEL_144;
      }
      v9 = 0;
LABEL_155:
      if ( v59 )
        LocalFree(v8);
    }
  }
LABEL_157:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v70);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpszProgID);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszStr2);
  return v9;
}

```

## disassembly

```asm
0x18008818c  mov     [rsp-8+arg_18], rbx
0x180088191  push    rbp
0x180088192  push    rsi
0x180088193  push    rdi
0x180088194  push    r12
0x180088196  push    r13
0x180088198  push    r14
0x18008819a  push    r15
0x18008819c  lea     rbp, [rsp-1270h]
0x1800881a4  mov     eax, 1390h
0x1800881a9  call    _alloca_probe
0x1800881ae  sub     rsp, rax
0x1800881b1  mov     rax, cs:__security_cookie
0x1800881b8  xor     rax, rsp
0x1800881bb  mov     [rbp+12A0h+var_40], rax
0x1800881c2  movups  xmm0, xmmword ptr [rdx]
0x1800881c5  mov     rbx, rcx
0x1800881c8  mov     [rbp+12A0h+var_12D0], r9d
0x1800881cc  xor     ecx, ecx
0x1800881ce  mov     r15, r8
0x1800881d1  mov     r13, rdx
0x1800881d4  mov     qword ptr [rbp+12A0h+cbData], rcx
0x1800881d8  mov     r14d, ecx
0x1800881db  mov     [rbp+12A0h+pszStr2], rcx
0x1800881df  mov     eax, [rbx+288h]
0x1800881e5  mov     r12d, 80004005h
0x1800881eb  and     eax, 20h
0x1800881ee  mov     [rbp+12A0h+lpszProgID], rcx
0x1800881f2  shr     eax, 5
0x1800881f5  test    dword ptr [rbx+85Ch], 100h
0x1800881ff  mov     [rbp+12A0h+var_12B8], rcx
0x180088203  mov     [rbp+12A0h+var_12CC], eax
0x180088206  movdqu  xmmword ptr [rbx+860h], xmm0
0x18008820e  jnz     loc_180088C94
0x180088214  mov     rax, [rdx]
0x180088217  mov     esi, ecx
0x180088219  sub     rax, qword ptr cs:CLSID_IEXMLDocument.Data1
0x180088220  jnz     short loc_18008822D
0x180088222  mov     rax, [rdx+8]
0x180088226  sub     rax, qword ptr cs:CLSID_IEXMLDocument.Data4
0x18008822d  mov     edi, ecx
0x18008822f  lea     rdx, [rbp+12A0h+lpszProgID]; lplpszProgID
0x180088233  test    rax, rax
0x180088236  mov     rcx, r13; clsid
0x180088239  setz    dil
0x18008823d  call    cs:__imp_ProgIDFromCLSID
0x180088244  nop     dword ptr [rax+rax+00h]
0x180088249  xor     edx, edx
0x18008824b  test    eax, eax
0x18008824d  jns     short loc_180088253
0x18008824f  test    edi, edi
0x180088251  jz      short loc_180088271
0x180088253  mov     rcx, [rbp+12A0h+lpszProgID]; pszStr1
0x180088257  test    rcx, rcx
0x18008825a  jz      loc_180088408
0x180088260  call    ?IsHtmlProgID@@YAHPEBG@Z; IsHtmlProgID(ushort const *)
0x180088265  xor     edx, edx
0x180088267  mov     esi, eax
0x180088269  test    eax, eax
0x18008826b  jnz     loc_180088415
0x180088271  mov     r9d, 1; int
0x180088277  lea     rdx, [rbp+12A0h+var_1090]; unsigned __int16 *
0x18008827e  mov     r8d, 824h; unsigned int
0x180088284  mov     rcx, rbx; this
0x180088287  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x18008828c  xor     edx, edx
0x18008828e  test    eax, eax
0x180088290  js      loc_180088C94
0x180088296  mov     rax, [rbx+820h]
0x18008829d  lea     rcx, [rbp+12A0h+var_1090]
0x1800882a4  mov     [rbp+12A0h+var_131C], edx
0x1800882a7  mov     edi, edx
0x1800882a9  mov     [rbp+12A0h+pwzURI], rcx
0x1800882ad  test    rax, rax
0x1800882b0  jz      short loc_1800882BD
0x1800882b2  cmp     [rax], dx
0x1800882b5  cmovnz  rcx, rax
0x1800882b9  mov     [rbp+12A0h+pwzURI], rcx
0x1800882bd  mov     rcx, [rbx+828h]; pszPath
0x1800882c4  test    rcx, rcx
0x1800882c7  jz      short loc_180088318
0x1800882c9  call    cs:__imp_PathFindExtensionW
0x1800882d0  nop     dword ptr [rax+rax+00h]
0x1800882d5  xor     edx, edx
0x1800882d7  mov     qword ptr [rbp+12A0h+cbData], rax
0x1800882db  mov     r14, rax
0x1800882de  cmp     [rax], dx
0x1800882e1  jz      short loc_180088318
0x1800882e3  mov     edx, 2
0x1800882e8  lea     r9, [rbp+12A0h+pszStr2]
0x1800882ec  mov     r8, rax
0x1800882ef  lea     ecx, [rdx-1]
0x1800882f2  call    cs:__imp_QueryAssociations
0x1800882f9  nop     dword ptr [rax+rax+00h]
0x1800882fe  xor     edx, edx
0x180088300  test    eax, eax
0x180088302  js      short loc_180088318
0x180088304  mov     rcx, [rbp+12A0h+pszStr2]; pszStr1
0x180088308  mov     [rbp+12A0h+var_131C], 1
0x18008830f  call    ?IsHtmlProgID@@YAHPEBG@Z; IsHtmlProgID(ushort const *)
0x180088314  mov     edi, eax
0x180088316  xor     edx, edx
0x180088318  test    esi, esi
0x18008831a  jnz     short loc_180088346
0x18008831c  test    edi, edi
0x18008831e  jnz     short loc_180088346
0x180088320  call    ?IsIExploreProcess@@YAHXZ; IsIExploreProcess(void)
0x180088325  xor     edx, edx
0x180088327  test    eax, eax
0x180088329  jz      short loc_180088346
0x18008832b  mov     ecx, 1000000h
0x180088330  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x180088337  nop     dword ptr [rax+rax+00h]
0x18008833c  xor     edx, edx
0x18008833e  test    eax, eax
0x180088340  jz      loc_180088C94
0x180088346  mov     rax, [r15]
0x180088349  mov     rdi, rdx
0x18008834c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180088353  mov     [rbp+12A0h+var_12FC], edx
0x180088356  mov     dword ptr [rbp+12A0h+ppv], edx
0x180088359  mov     [rbp+12A0h+var_1300], edx
0x18008835c  mov     [rbp+12A0h+var_12A8], rdx
0x180088360  mov     [rbp+12A0h+var_12B0], rdx
0x180088364  jnz     short loc_180088373
0x180088366  mov     rax, [r15+8]
0x18008836a  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180088371  jz      short loc_180088393
0x180088373  lea     rdx, [rbp+12A0h+var_12B8]; lplpszProgID
0x180088377  mov     rcx, r15; clsid
0x18008837a  call    cs:__imp_ProgIDFromCLSID
0x180088381  nop     dword ptr [rax+rax+00h]
0x180088386  xor     edx, edx
0x180088388  test    eax, eax
0x18008838a  cmovns  rdi, [rbp+12A0h+var_12B8]
0x18008838f  mov     [rbp+12A0h+var_12B0], rdi
0x180088393  mov     rax, [rbp+12A0h+lpszProgID]
0x180088397  mov     r8d, 0F7FFFFFFh
0x18008839d  mov     [rbp+12A0h+var_1310], rax
0x1800883a1  test    rax, rax
0x1800883a4  jz      loc_18008867B
0x1800883aa  mov     r15d, edx
0x1800883ad  mov     [rbp+12A0h+var_1320], edx
0x1800883b0  cmp     [rbp+12A0h+var_131C], edx
0x1800883b3  jz      loc_18008855A
0x1800883b9  mov     rcx, r14; pszAssoc
0x1800883bc  call    ?RestrictShellExecute@@YAHPEBG@Z; RestrictShellExecute(ushort const *)
0x1800883c1  mov     rdx, [rbp+12A0h+pszStr2]; pszStr2
0x1800883c5  mov     edi, eax
0x1800883c7  mov     rcx, [rbp+12A0h+lpszProgID]; pszStr1
0x1800883cb  call    cs:__imp_StrCmpICW
0x1800883d2  nop     dword ptr [rax+rax+00h]
0x1800883d7  mov     ecx, [rbx+288h]
0x1800883dd  xor     edx, edx
0x1800883df  test    eax, eax
0x1800883e1  mov     esi, edx
0x1800883e3  setnz   sil
0x1800883e7  bt      ecx, 1Ch
0x1800883eb  jnb     short loc_18008844F
0x1800883ed  mov     r15, [rbp+12A0h+pszStr2]
0x1800883f1  lea     r13d, [rdx+1]
0x1800883f5  btr     ecx, 1Bh
0x1800883f9  mov     [rbp+12A0h+var_1310], r15
0x1800883fd  mov     [rbx+288h], ecx
0x180088403  jmp     loc_18008859C
0x180088408  test    edi, edi
0x18008840a  jz      loc_180088271
0x180088410  mov     esi, 1
0x180088415  bts     dword ptr [rbx+85Ch], 0Bh
0x18008841d  mov     eax, [rbx+288h]
0x180088423  bt      eax, 1Ch
0x180088427  jb      loc_180088271
0x18008842d  test    dword ptr [rbx+85Ch], 400h
0x180088437  jnz     loc_180088271
0x18008843d  bts     eax, 1Bh
0x180088441  mov     r12d, edx
0x180088444  mov     [rbx+288h], eax
0x18008844a  jmp     loc_180088C94
0x18008844f  test    eax, eax
0x180088451  jnz     short loc_180088466
0x180088453  mov     r15, [rbp+12A0h+var_1310]
0x180088457  btr     ecx, 1Bh
0x18008845b  mov     [rbx+288h], ecx
0x180088461  jmp     loc_180088774
0x180088466  mov     [rbp+12A0h+hKey], rdx
0x18008846a  lea     rax, [rbp+12A0h+hKey]
0x18008846e  mov     [rbp+12A0h+Type], edx
0x180088471  mov     r9d, 1; samDesired
0x180088477  mov     dword ptr [rbp+12A0h+Data], edx
0x18008847a  xor     r8d, r8d; ulOptions
0x18008847d  mov     rdx, [rbp+12A0h+lpszProgID]; lpSubKey
0x180088481  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180088488  mov     [rsp+13C0h+phkResult], rax; phkResult
0x18008848d  mov     [rbp+12A0h+cbData], 4
0x180088494  call    cs:__imp_RegOpenKeyExW
0x18008849b  nop     dword ptr [rax+rax+00h]
0x1800884a0  test    eax, eax
0x1800884a2  jnz     loc_18008852F
0x1800884a8  mov     rcx, [rbp+12A0h+hKey]; hKey
0x1800884ac  lea     rax, [rbp+12A0h+cbData]
0x1800884b0  mov     [rsp+13C0h+lpcbData], rax; lpcbData
0x1800884b5  lea     r9, [rbp+12A0h+Type]; lpType
0x1800884b9  lea     rax, [rbp+12A0h+Data]
0x1800884bd  xor     r8d, r8d; lpReserved
0x1800884c0  lea     rdx, aPreferexecuteo; "PreferExecuteOnMismatch"
0x1800884c7  mov     [rsp+13C0h+phkResult], rax; lpData
0x1800884cc  call    cs:__imp_RegQueryValueExW
0x1800884d3  nop     dword ptr [rax+rax+00h]
0x1800884d8  xor     ecx, ecx
0x1800884da  test    eax, eax
0x1800884dc  jnz     short loc_180088503
0x1800884de  cmp     [rbp+12A0h+Type], 4
0x1800884e2  jnz     short loc_180088503
0x1800884e4  cmp     dword ptr [rbp+12A0h+Data], ecx
0x1800884e7  jz      short loc_180088503
0x1800884e9  mov     rdx, [rbp+12A0h+pszStr2]
0x1800884ed  mov     esi, ecx
0x1800884ef  btr     dword ptr [rbx+288h], 1Bh
0x1800884f7  mov     r15d, edi
0x1800884fa  mov     dword ptr [rbp+12A0h+ppv], 1
0x180088501  jmp     short loc_180088507
0x180088503  mov     rdx, [rbp+12A0h+var_1310]
0x180088507  mov     edi, dword ptr [rbp+12A0h+ppv]
0x18008850a  mov     rcx, [rbp+12A0h+hKey]; hKey
0x18008850e  mov     dword ptr [rbp+12A0h+ppv], edi
0x180088511  mov     [rbp+12A0h+var_1310], rdx
0x180088515  mov     [rbp+12A0h+var_1320], r15d
0x180088519  call    cs:__imp_RegCloseKey
0x180088520  nop     dword ptr [rax+rax+00h]
0x180088525  xor     edx, edx
0x180088527  test    edi, edi
0x180088529  jnz     loc_18008888F
0x18008852f  mov     rcx, [rbp+12A0h+pszStr2]; unsigned __int16 *
0x180088533  mov     r8, r14; unsigned __int16 *
0x180088536  mov     rdx, r13; struct _GUID *
0x180088539  call    ?IsLinked@@YAHPEBGAEBU_GUID@@0@Z; IsLinked(ushort const *,_GUID const &,ushort const *)
0x18008853e  xor     edx, edx
0x180088540  test    eax, eax
0x180088542  jz      short loc_180088550
0x180088544  btr     dword ptr [rbx+288h], 1Bh
0x18008854c  mov     esi, edx
0x18008854e  jmp     short loc_18008858B
0x180088550  mov     rax, [rbp+12A0h+pszStr2]
0x180088554  mov     [rbp+12A0h+var_12A8], rax
0x180088558  jmp     short loc_18008858B
0x18008855a  mov     ecx, [rbx+288h]
0x180088560  mov     esi, edx
0x180088562  bt      ecx, 1Ch
0x180088566  jnb     loc_180088771
0x18008856c  test    r14, r14
0x18008856f  setnz   r15b
0x180088573  and     ecx, r8d
0x180088576  mov     eax, r15d
0x180088579  mov     [rbp+12A0h+var_1320], r15d
0x18008857d  xor     eax, 1
0x180088580  shl     eax, 1Bh
0x180088583  or      eax, ecx
0x180088585  mov     [rbx+288h], eax
0x18008858b  test    r15d, r15d
0x18008858e  mov     r15, [rbp+12A0h+var_1310]
0x180088592  jz      loc_180088774
0x180088598  mov     r13d, dword ptr [rbp+12A0h+ppv]
0x18008859c  mov     rax, [rbx+838h]
0x1800885a3  test    rax, rax
0x1800885a6  jz      short loc_1800885AD
0x1800885a8  cmp     [rax], dx
0x1800885ab  jnz     short loc_1800885D3
0x1800885ad  cmp     [rbp+12A0h+var_12FC], edx
0x1800885b0  jnz     short loc_1800885D3
0x1800885b2  test    r14, r14
0x1800885b5  jz      short loc_1800885D3
0x1800885b7  cmp     [r14], dx
0x1800885bb  jz      short loc_1800885D3
0x1800885bd  mov     rcx, r14; pszSrch
0x1800885c0  call    cs:__imp_StrDupW
0x1800885c7  nop     dword ptr [rax+rax+00h]
0x1800885cc  mov     [rbx+838h], rax
0x1800885d3  mov     edi, [rbx+2E0h]
0x1800885d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX>::GetImpl(void)'::`2'::impl
0x1800885e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WMP_CLICKONCE_FIX>::__private_IsEnabled(void)
0x1800885e5  test    al, al
0x1800885e7  jz      loc_18008889B
0x1800885ed  lea     rcx, ?FEATURE_BLOCK_CLICKONCE@FCK@@3VCFeatureControlKey@@A; this
0x1800885f4  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800885f9  xor     edx, edx
0x1800885fb  test    eax, eax
0x1800885fd  jnz     loc_18008889B
0x180088603  mov     rcx, [rbx+830h]; String1
0x18008860a  test    rcx, rcx
0x18008860d  jz      short loc_180088628
0x18008860f  lea     rdx, aApplicationXMs_0; "application/x-ms-application"
0x180088616  call    cs:__imp__wcsicmp
0x18008861d  nop     dword ptr [rax+rax+00h]
0x180088622  xor     edx, edx
0x180088624  test    eax, eax
0x180088626  jz      short loc_180088674
0x180088628  test    r14, r14
0x18008862b  jz      short loc_18008864D
0x18008862d  cmp     [r14], dx
0x180088631  jz      short loc_18008864D
  ... truncated ...
```
