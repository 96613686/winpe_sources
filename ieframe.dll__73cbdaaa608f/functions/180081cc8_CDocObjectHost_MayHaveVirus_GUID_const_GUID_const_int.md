# CDocObjectHost::_MayHaveVirus(_GUID const &,_GUID const &,int)

- ea: `0x180081cc8`
- end: `0x180082783`
- name: `?_MayHaveVirus@CDocObjectHost@@IEAAJAEBU_GUID@@0H@Z`
- size: `2747`
- prototype: `__int64 __fastcall(CDocObjectHost *__hidden this, const struct _GUID *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a8ef0`

## callees

- `0x18000b9e0`
- `0x18001132c`
- `0x180012310`
- `0x18002acc0`
- `0x180044b10`
- `0x1800567e4`
- `0x180065a9c`
- `0x180081cc8`
- `0x180090e88`
- `0x1800b93a6`
- `0x1800e6a00`
- `0x1800e7208`
- `0x1800e7310`
- `0x1800e7a08`
- `0x1800e9ba4`
- `0x1800eacd0`
- `0x180134e1c`
- `0x180134ec4`
- `0x180134fa0`
- `0x180136ee8`
- `0x180143f18`
- `0x1801de7dc`
- `0x18053afb4`
- `0x18053d830`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180081ee9`
- `SHLWAPI!__imp_StrCmpICW` at `0x180081ee9`
- `msvcrt!_wcsicmp` at `0x1800820fe`
- `msvcrt!_wcsicmp` at `0x18008211f`
- `msvcrt!_wcsicmp` at `0x18008213e`
- `msvcrt!_wcsicmp` at `0x1800820fe`
- `msvcrt!_wcsicmp` at `0x18008211f`
- `msvcrt!_wcsicmp` at `0x18008213e`
- `KERNEL32!LocalFree` at `0x180082735`
- `KERNEL32!LocalFree` at `0x180082735`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180082021`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180082021`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180081fac`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180081fac`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180081fda`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180081fda`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180081dff`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180081dff`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800820c2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180082280`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800820c2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180082280`
- `OLEAUT32!__imp_SysFreeString` at `0x18008233b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008233b`
- `iertutil!CreateUri` at `0x1800822ab`
- `iertutil!CreateUri` at `0x1800822ab`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x180081d79`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x180081e9e`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x180081d79`
- `api-ms-win-downlevel-ole32-l1-1-0!ProgIDFromCLSID` at `0x180081e9e`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180081e5a`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800824b9`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180081e5a`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1800824b9`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1800824c8`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1800824c8`
- `urlmon!QueryAssociations` at `0x180081e22`
- `urlmon!QueryAssociations` at `0x18008220d`
- `urlmon!QueryAssociations` at `0x180081e22`
- `urlmon!QueryAssociations` at `0x18008220d`
- `urlmon!__imp_?IEZoneCheckUrlExW@@YAJPEBGPEAKK1KKKPEAUIInternetSecurityMgrSite@@@Z` at `0x18008246d`
- `urlmon!__imp_?IEZoneCheckUrlExW@@YAJPEBGPEAKK1KKKPEAUIInternetSecurityMgrSite@@@Z` at `0x18008246d`

## string_xrefs

- `0x1800822ee`: `OpenAsReadOnly`
- `0x180082134`: `Application.Manifest`

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
    goto LABEL_156;
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
      goto LABEL_156;
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
            goto LABEL_78;
          }
          LOBYTE(v21) = v8 != 0;
          v53 = v21;
          *((_DWORD *)this + 162) = v30 & 0xF7FFFFFF | ((v21 ^ 1) << 27);
LABEL_49:
          v11 = v21 == 0;
          v26 = v56;
          if ( v11 )
            goto LABEL_78;
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
LABEL_78:
          v34 = v54;
LABEL_79:
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
          goto LABEL_159;
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
LABEL_159:
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
                    goto LABEL_79;
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
          goto LABEL_79;
        v27 = 1;
      }
LABEL_51:
      v31 = (_WORD *)*((_QWORD *)this + 263);
      if ( (!v31 || !*v31) && !v59 && v8 && *v8 )
        *((_QWORD *)this + 263) = StrDupW(v8);
      v32 = *((_DWORD *)this + 184);
      if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_BLOCK_CLICKONCE) )
      {
        v33 = (const wchar_t *)*((_QWORD *)this + 262);
        if ( v33 )
        {
          if ( !_wcsicmp(v33, L"application/x-ms-application") )
            goto LABEL_154;
        }
        if ( v8 && *v8 && !_wcsicmp(v8, L".application") || v26 && !_wcsicmp(v26, L"Application.Manifest") )
          goto LABEL_154;
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
            goto LABEL_160;
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
LABEL_160:
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
LABEL_143:
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
        goto LABEL_154;
      }
      switch ( v32 )
      {
        case 1:
          *((_DWORD *)this + 162) |= 0x20u;
          if ( v27 || v41 || v58 )
            goto LABEL_125;
          if ( (*((_DWORD *)this + 163) & 0x200) == 0 )
            CDocObjectHost::_SetDownloadNotification(this);
          break;
        case 2:
          goto LABEL_143;
        case 5:
          *((_DWORD *)this + 162) &= ~0x200u;
          if ( v27 || v41 || v58 )
            goto LABEL_125;
          break;
        case 4358:
          goto LABEL_126;
        case 4402:
LABEL_125:
          *((_BYTE *)this + 2162) = 1;
LABEL_126:
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
          goto LABEL_143;
        default:
          goto LABEL_143;
      }
      v9 = 0;
LABEL_154:
      if ( v59 )
        LocalFree(v8);
    }
  }
LABEL_156:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v70);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpszProgID);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszStr2);
  return v9;
}

```

## disassembly

```asm
0x180081cc8  mov     [rsp-8+arg_18], rbx
0x180081ccd  push    rbp
0x180081cce  push    rsi
0x180081ccf  push    rdi
0x180081cd0  push    r12
0x180081cd2  push    r13
0x180081cd4  push    r14
0x180081cd6  push    r15
0x180081cd8  lea     rbp, [rsp-1270h]
0x180081ce0  mov     eax, 1390h
0x180081ce5  call    _alloca_probe
0x180081cea  sub     rsp, rax
0x180081ced  mov     rax, cs:__security_cookie
0x180081cf4  xor     rax, rsp
0x180081cf7  mov     [rbp+12A0h+var_40], rax
0x180081cfe  movups  xmm0, xmmword ptr [rdx]
0x180081d01  mov     rbx, rcx
0x180081d04  mov     [rbp+12A0h+var_12D0], r9d
0x180081d08  xor     ecx, ecx
0x180081d0a  mov     r15, r8
0x180081d0d  mov     r13, rdx
0x180081d10  mov     qword ptr [rbp+12A0h+cbData], rcx
0x180081d14  mov     r14d, ecx
0x180081d17  mov     [rbp+12A0h+pszStr2], rcx
0x180081d1b  mov     eax, [rbx+288h]
0x180081d21  mov     r12d, 80004005h
0x180081d27  and     eax, 20h
0x180081d2a  mov     [rbp+12A0h+lpszProgID], rcx
0x180081d2e  shr     eax, 5
0x180081d31  test    dword ptr [rbx+85Ch], 100h
0x180081d3b  mov     [rbp+12A0h+var_12B8], rcx
0x180081d3f  mov     [rbp+12A0h+var_12CC], eax
0x180081d42  movdqu  xmmword ptr [rbx+860h], xmm0
0x180081d4a  jnz     loc_18008273B
0x180081d50  mov     rax, [rdx]
0x180081d53  mov     esi, ecx
0x180081d55  sub     rax, qword ptr cs:CLSID_IEXMLDocument.Data1
0x180081d5c  jnz     short loc_180081D69
0x180081d5e  mov     rax, [rdx+8]
0x180081d62  sub     rax, qword ptr cs:CLSID_IEXMLDocument.Data4
0x180081d69  mov     edi, ecx
0x180081d6b  lea     rdx, [rbp+12A0h+lpszProgID]; lplpszProgID
0x180081d6f  test    rax, rax
0x180081d72  mov     rcx, r13; clsid
0x180081d75  setz    dil
0x180081d79  call    cs:__imp_ProgIDFromCLSID
0x180081d7f  xor     edx, edx
0x180081d81  test    eax, eax
0x180081d83  jns     short loc_180081D89
0x180081d85  test    edi, edi
0x180081d87  jz      short loc_180081DA7
0x180081d89  mov     rcx, [rbp+12A0h+lpszProgID]; pszStr1
0x180081d8d  test    rcx, rcx
0x180081d90  jz      loc_180081F20
0x180081d96  call    ?IsHtmlProgID@@YAHPEBG@Z; IsHtmlProgID(ushort const *)
0x180081d9b  xor     edx, edx
0x180081d9d  mov     esi, eax
0x180081d9f  test    eax, eax
0x180081da1  jnz     loc_180081F2D
0x180081da7  mov     r9d, 1; int
0x180081dad  lea     rdx, [rbp+12A0h+var_1090]; unsigned __int16 *
0x180081db4  mov     r8d, 824h; unsigned int
0x180081dba  mov     rcx, rbx; this
0x180081dbd  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x180081dc2  xor     edx, edx
0x180081dc4  test    eax, eax
0x180081dc6  js      loc_18008273B
0x180081dcc  mov     rax, [rbx+820h]
0x180081dd3  lea     rcx, [rbp+12A0h+var_1090]
0x180081dda  mov     [rbp+12A0h+var_131C], edx
0x180081ddd  mov     edi, edx
0x180081ddf  mov     [rbp+12A0h+pwzURI], rcx
0x180081de3  test    rax, rax
0x180081de6  jz      short loc_180081DF3
0x180081de8  cmp     [rax], dx
0x180081deb  cmovnz  rcx, rax
0x180081def  mov     [rbp+12A0h+pwzURI], rcx
0x180081df3  mov     rcx, [rbx+828h]; pszPath
0x180081dfa  test    rcx, rcx
0x180081dfd  jz      short loc_180081E42
0x180081dff  call    cs:__imp_PathFindExtensionW
0x180081e05  xor     edx, edx
0x180081e07  mov     qword ptr [rbp+12A0h+cbData], rax
0x180081e0b  mov     r14, rax
0x180081e0e  cmp     [rax], dx
0x180081e11  jz      short loc_180081E42
0x180081e13  mov     edx, 2
0x180081e18  lea     r9, [rbp+12A0h+pszStr2]
0x180081e1c  mov     r8, rax
0x180081e1f  lea     ecx, [rdx-1]
0x180081e22  call    cs:__imp_QueryAssociations
0x180081e28  xor     edx, edx
0x180081e2a  test    eax, eax
0x180081e2c  js      short loc_180081E42
0x180081e2e  mov     rcx, [rbp+12A0h+pszStr2]; pszStr1
0x180081e32  mov     [rbp+12A0h+var_131C], 1
0x180081e39  call    ?IsHtmlProgID@@YAHPEBG@Z; IsHtmlProgID(ushort const *)
0x180081e3e  mov     edi, eax
0x180081e40  xor     edx, edx
0x180081e42  test    esi, esi
0x180081e44  jnz     short loc_180081E6A
0x180081e46  test    edi, edi
0x180081e48  jnz     short loc_180081E6A
0x180081e4a  call    ?IsIExploreProcess@@YAHXZ; IsIExploreProcess(void)
0x180081e4f  xor     edx, edx
0x180081e51  test    eax, eax
0x180081e53  jz      short loc_180081E6A
0x180081e55  mov     ecx, 1000000h
0x180081e5a  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x180081e60  xor     edx, edx
0x180081e62  test    eax, eax
0x180081e64  jz      loc_18008273B
0x180081e6a  mov     rax, [r15]
0x180081e6d  mov     rdi, rdx
0x180081e70  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180081e77  mov     [rbp+12A0h+var_12FC], edx
0x180081e7a  mov     dword ptr [rbp+12A0h+ppv], edx
0x180081e7d  mov     [rbp+12A0h+var_1300], edx
0x180081e80  mov     [rbp+12A0h+var_12A8], rdx
0x180081e84  mov     [rbp+12A0h+var_12B0], rdx
0x180081e88  jnz     short loc_180081E97
0x180081e8a  mov     rax, [r15+8]
0x180081e8e  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180081e95  jz      short loc_180081EB1
0x180081e97  lea     rdx, [rbp+12A0h+var_12B8]; lplpszProgID
0x180081e9b  mov     rcx, r15; clsid
0x180081e9e  call    cs:__imp_ProgIDFromCLSID
0x180081ea4  xor     edx, edx
0x180081ea6  test    eax, eax
0x180081ea8  cmovns  rdi, [rbp+12A0h+var_12B8]
0x180081ead  mov     [rbp+12A0h+var_12B0], rdi
0x180081eb1  mov     rax, [rbp+12A0h+lpszProgID]
0x180081eb5  mov     r8d, 0F7FFFFFFh
0x180081ebb  mov     [rbp+12A0h+var_1310], rax
0x180081ebf  test    rax, rax
0x180081ec2  jz      loc_180082155
0x180081ec8  mov     r15d, edx
0x180081ecb  mov     [rbp+12A0h+var_1320], edx
0x180081ece  cmp     [rbp+12A0h+var_131C], edx
0x180081ed1  jz      loc_18008205C
0x180081ed7  mov     rcx, r14; pszAssoc
0x180081eda  call    ?RestrictShellExecute@@YAHPEBG@Z; RestrictShellExecute(ushort const *)
0x180081edf  mov     rdx, [rbp+12A0h+pszStr2]; pszStr2
0x180081ee3  mov     edi, eax
0x180081ee5  mov     rcx, [rbp+12A0h+lpszProgID]; pszStr1
0x180081ee9  call    cs:__imp_StrCmpICW
0x180081eef  mov     ecx, [rbx+288h]
0x180081ef5  xor     edx, edx
0x180081ef7  test    eax, eax
0x180081ef9  mov     esi, edx
0x180081efb  setnz   sil
0x180081eff  bt      ecx, 1Ch
0x180081f03  jnb     short loc_180081F67
0x180081f05  mov     r15, [rbp+12A0h+pszStr2]
0x180081f09  lea     r13d, [rdx+1]
0x180081f0d  btr     ecx, 1Bh
0x180081f11  mov     [rbp+12A0h+var_1310], r15
0x180081f15  mov     [rbx+288h], ecx
0x180081f1b  jmp     loc_18008209E
0x180081f20  test    edi, edi
0x180081f22  jz      loc_180081DA7
0x180081f28  mov     esi, 1
0x180081f2d  bts     dword ptr [rbx+85Ch], 0Bh
0x180081f35  mov     eax, [rbx+288h]
0x180081f3b  bt      eax, 1Ch
0x180081f3f  jb      loc_180081DA7
0x180081f45  test    dword ptr [rbx+85Ch], 400h
0x180081f4f  jnz     loc_180081DA7
0x180081f55  bts     eax, 1Bh
0x180081f59  mov     r12d, edx
0x180081f5c  mov     [rbx+288h], eax
0x180081f62  jmp     loc_18008273B
0x180081f67  test    eax, eax
0x180081f69  jnz     short loc_180081F7E
0x180081f6b  mov     r15, [rbp+12A0h+var_1310]
0x180081f6f  btr     ecx, 1Bh
0x180081f73  mov     [rbx+288h], ecx
0x180081f79  jmp     loc_180082248
0x180081f7e  mov     [rbp+12A0h+hKey], rdx
0x180081f82  lea     rax, [rbp+12A0h+hKey]
0x180081f86  mov     [rbp+12A0h+Type], edx
0x180081f89  mov     r9d, 1; samDesired
0x180081f8f  mov     dword ptr [rbp+12A0h+Data], edx
0x180081f92  xor     r8d, r8d; ulOptions
0x180081f95  mov     rdx, [rbp+12A0h+lpszProgID]; lpSubKey
0x180081f99  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180081fa0  mov     [rsp+13C0h+phkResult], rax; phkResult
0x180081fa5  mov     [rbp+12A0h+cbData], 4
0x180081fac  call    cs:__imp_RegOpenKeyExW
0x180081fb2  test    eax, eax
0x180081fb4  jnz     short loc_180082031
0x180081fb6  mov     rcx, [rbp+12A0h+hKey]; hKey
0x180081fba  lea     rax, [rbp+12A0h+cbData]
0x180081fbe  mov     [rsp+13C0h+lpcbData], rax; lpcbData
0x180081fc3  lea     r9, [rbp+12A0h+Type]; lpType
0x180081fc7  lea     rax, [rbp+12A0h+Data]
0x180081fcb  xor     r8d, r8d; lpReserved
0x180081fce  lea     rdx, aPreferexecuteo; "PreferExecuteOnMismatch"
0x180081fd5  mov     [rsp+13C0h+phkResult], rax; lpData
0x180081fda  call    cs:__imp_RegQueryValueExW
0x180081fe0  xor     ecx, ecx
0x180081fe2  test    eax, eax
0x180081fe4  jnz     short loc_18008200B
0x180081fe6  cmp     [rbp+12A0h+Type], 4
0x180081fea  jnz     short loc_18008200B
0x180081fec  cmp     dword ptr [rbp+12A0h+Data], ecx
0x180081fef  jz      short loc_18008200B
0x180081ff1  mov     rdx, [rbp+12A0h+pszStr2]
0x180081ff5  mov     esi, ecx
0x180081ff7  btr     dword ptr [rbx+288h], 1Bh
0x180081fff  mov     r15d, edi
0x180082002  mov     dword ptr [rbp+12A0h+ppv], 1
0x180082009  jmp     short loc_18008200F
0x18008200b  mov     rdx, [rbp+12A0h+var_1310]
0x18008200f  mov     edi, dword ptr [rbp+12A0h+ppv]
0x180082012  mov     rcx, [rbp+12A0h+hKey]; hKey
0x180082016  mov     dword ptr [rbp+12A0h+ppv], edi
0x180082019  mov     [rbp+12A0h+var_1310], rdx
0x18008201d  mov     [rbp+12A0h+var_1320], r15d
0x180082021  call    cs:__imp_RegCloseKey
0x180082027  xor     edx, edx
0x180082029  test    edi, edi
0x18008202b  jnz     loc_180082351
0x180082031  mov     rcx, [rbp+12A0h+pszStr2]; unsigned __int16 *
0x180082035  mov     r8, r14; unsigned __int16 *
0x180082038  mov     rdx, r13; struct _GUID *
0x18008203b  call    ?IsLinked@@YAHPEBGAEBU_GUID@@0@Z; IsLinked(ushort const *,_GUID const &,ushort const *)
0x180082040  xor     edx, edx
0x180082042  test    eax, eax
0x180082044  jz      short loc_180082052
0x180082046  btr     dword ptr [rbx+288h], 1Bh
0x18008204e  mov     esi, edx
0x180082050  jmp     short loc_18008208D
0x180082052  mov     rax, [rbp+12A0h+pszStr2]
0x180082056  mov     [rbp+12A0h+var_12A8], rax
0x18008205a  jmp     short loc_18008208D
0x18008205c  mov     ecx, [rbx+288h]
0x180082062  mov     esi, edx
0x180082064  bt      ecx, 1Ch
0x180082068  jnb     loc_180082245
0x18008206e  test    r14, r14
0x180082071  setnz   r15b
0x180082075  and     ecx, r8d
0x180082078  mov     eax, r15d
0x18008207b  mov     [rbp+12A0h+var_1320], r15d
0x18008207f  xor     eax, 1
0x180082082  shl     eax, 1Bh
0x180082085  or      eax, ecx
0x180082087  mov     [rbx+288h], eax
0x18008208d  test    r15d, r15d
0x180082090  mov     r15, [rbp+12A0h+var_1310]
0x180082094  jz      loc_180082248
0x18008209a  mov     r13d, dword ptr [rbp+12A0h+ppv]
0x18008209e  mov     rax, [rbx+838h]
0x1800820a5  test    rax, rax
0x1800820a8  jz      short loc_1800820AF
0x1800820aa  cmp     [rax], dx
0x1800820ad  jnz     short loc_1800820CF
0x1800820af  cmp     [rbp+12A0h+var_12FC], edx
0x1800820b2  jnz     short loc_1800820CF
0x1800820b4  test    r14, r14
0x1800820b7  jz      short loc_1800820CF
0x1800820b9  cmp     [r14], dx
0x1800820bd  jz      short loc_1800820CF
0x1800820bf  mov     rcx, r14; pszSrch
0x1800820c2  call    cs:__imp_StrDupW
0x1800820c8  mov     [rbx+838h], rax
0x1800820cf  mov     edi, [rbx+2E0h]
0x1800820d5  lea     rcx, ?FEATURE_BLOCK_CLICKONCE@FCK@@3VCFeatureControlKey@@A; this
0x1800820dc  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800820e1  xor     edx, edx
0x1800820e3  test    eax, eax
0x1800820e5  jnz     loc_18008235D
0x1800820eb  mov     rcx, [rbx+830h]; String1
0x1800820f2  test    rcx, rcx
0x1800820f5  jz      short loc_18008210A
0x1800820f7  lea     rdx, aApplicationXMs_0; "application/x-ms-application"
0x1800820fe  call    cs:__imp__wcsicmp
0x180082104  xor     edx, edx
0x180082106  test    eax, eax
0x180082108  jz      short loc_18008214E
0x18008210a  test    r14, r14
0x18008210d  jz      short loc_18008212B
0x18008210f  cmp     [r14], dx
0x180082113  jz      short loc_18008212B
0x180082115  lea     rdx, aApplication_0; ".application"
0x18008211c  mov     rcx, r14; String1
0x18008211f  call    cs:__imp__wcsicmp
0x180082125  xor     edx, edx
0x180082127  test    eax, eax
0x180082129  jz      short loc_18008214E
0x18008212b  test    r15, r15
0x18008212e  jz      loc_18008235D
0x180082134  lea     rdx, aApplicationMan; "Application.Manifest"
0x18008213b  mov     rcx, r15; String1
0x18008213e  call    cs:__imp__wcsicmp
0x180082144  xor     edx, edx
0x180082146  test    eax, eax
0x180082148  jnz     loc_18008235D
0x18008214e  xor     esi, esi
  ... truncated ...
```
