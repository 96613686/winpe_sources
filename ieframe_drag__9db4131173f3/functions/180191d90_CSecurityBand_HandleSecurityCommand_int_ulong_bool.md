# CSecurityBand::_HandleSecurityCommand(int,ulong,bool)

- ea: `0x180191d90`
- end: `0x180192829`
- name: `?_HandleSecurityCommand@CSecurityBand@@AEAAJHK_N@Z`
- size: `2713`
- prototype: `__int64 __fastcall(CSecurityBand *__hidden this, int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018f474`
- `0x18019027c`

## callees

- `0x18000a0f8`
- `0x180038178`
- `0x18004db30`
- `0x18005908c`
- `0x18006ff5c`
- `0x18008e2e4`
- `0x1801354c0`
- `0x1801355ec`
- `0x180135e44`
- `0x18013d35c`
- `0x18013f394`
- `0x180143e5c`
- `0x180144464`
- `0x180144600`
- `0x18018f1f0`
- `0x1801901f4`
- `0x1801903a4`
- `0x180190bf8`
- `0x180191784`
- `0x180191d90`
- `0x1801928b0`
- `0x18019290c`
- `0x180192978`
- `0x180192fe0`
- `0x180193188`
- `0x180247ba0`
- `0x1804038c8`
- `0x1804e6bf0`
- `0x1804eadb8`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180191f4a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180191f63`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801921fd`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180192219`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180191f4a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180191f63`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801921fd`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180192219`
- `USER32!MessageBoxW` at `0x180191f83`
- `USER32!MessageBoxW` at `0x18019223b`
- `USER32!MessageBoxW` at `0x180191f83`
- `USER32!MessageBoxW` at `0x18019223b`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801920b9`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18019218c`
- `SHELL32!__imp_SHCLSIDFromString` at `0x180192372`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801923bf`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801920b9`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18019218c`
- `SHELL32!__imp_SHCLSIDFromString` at `0x180192372`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801923bf`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180192753`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180192753`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180192092`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180192092`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1801927a7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1801927a7`
- `WININET!DeleteUrlCacheEntryW` at `0x180192076`
- `WININET!DeleteUrlCacheEntryW` at `0x180192076`
- `urlmon!__imp_ResetWarnOnIntranetFlag` at `0x180192487`
- `urlmon!__imp_ResetWarnOnIntranetFlag` at `0x180192487`

## pseudocode

```c
__int64 __fastcall CSecurityBand::_HandleSecurityCommand(unsigned __int64 this, int a2, unsigned int a3, char a4)
{
  CSecurityBand *v7; // rdi
  unsigned int v8; // r15d
  __int64 v9; // rdx
  unsigned int v10; // edx
  unsigned int v11; // edx
  __int64 v12; // rcx
  HWND v13; // rax
  unsigned int v14; // edx
  CDocObjectHost *v15; // rcx
  CDocObjectHost *v16; // rcx
  const WCHAR *v17; // rcx
  const unsigned __int16 *v18; // r9
  BOOL v19; // r8d
  CDocObjectHost *v20; // rcx
  unsigned int v21; // edx
  const WCHAR *v22; // rcx
  const unsigned __int16 *v23; // r9
  BOOL v24; // r8d
  CDocObjectHost *v25; // rcx
  HWND DialogParentHwnd; // rax
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  const WCHAR *v31; // rcx
  const WCHAR *v32; // rax
  const WCHAR *v33; // rcx
  const unsigned __int16 *v34; // r9
  BOOL v35; // r8d
  CDocObjectHost *v36; // rcx
  const unsigned __int16 *v37; // rax
  unsigned int v38; // esi
  CDocObjectHost *v39; // rcx
  __int64 v40; // rcx
  unsigned int v41; // ebx
  unsigned int v42; // edx
  const unsigned __int16 *v43; // rdx
  const unsigned __int16 *v44; // rdx
  bool v45; // zf
  const WCHAR *v46; // rcx
  const WCHAR *v47; // rax
  void *p_pclsid; // r9
  void *v49; // r8
  const WCHAR *v50; // rax
  LPCWSTR *p_lpszUrlName; // rdx
  LPCWSTR *v52; // rcx
  const WCHAR *v53; // rcx
  const WCHAR *v54; // rax
  const WCHAR *v55; // rax
  int v56; // eax
  const unsigned __int16 *pvData; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *pvDataa; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *cbDataa; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *cbDatab; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v63; // [rsp+30h] [rbp-D0h]
  int v64; // [rsp+38h] [rbp-C8h]
  int v65; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpszUrlName; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v67; // [rsp+50h] [rbp-B0h] BYREF
  struct tagVARIANT pclsid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Caption[256]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[256]; // [rsp+280h] [rbp+180h] BYREF

  v7 = (CSecurityBand *)this;
  v8 = 0;
  if ( a2 > 37986 )
  {
    if ( a2 <= 38034 )
    {
      if ( a2 == 38034 )
      {
        (*(void (__fastcall **)(__int64, const GUID *, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(this + 16) + 48LL)
                                                                                        + 32LL))(
          *(_QWORD *)(this + 16) + 48LL,
          &CGID_Explorer,
          6,
          0xFFFFFFFFLL,
          0,
          0);
        return v8;
      }
      if ( a2 <= 38008 )
      {
        if ( a2 != 38008 )
        {
          if ( a2 != 37988 )
          {
            if ( a2 != 37989 )
            {
              if ( a2 != 37990 )
              {
                switch ( a2 )
                {
                  case 38001:
                    *(_DWORD *)(this + 8) &= ~0x80000u;
                    *(_DWORD *)(this + 184) &= ~0x80000u;
                    CSecurityBand::ShowHide((CSecurityBand *)this);
                    v11 = 0x2000000;
                    break;
                  case 38002:
                    v9 = 29;
                    goto LABEL_16;
                  case 38004:
                    v11 = 67117059;
                    goto LABEL_23;
                  case 38005:
                    v9 = 33;
                    goto LABEL_16;
                  case 38007:
                    if ( !(unsigned int)CDocObjectHost::OnWpcOverride(*(CDocObjectHost **)(this + 16)) )
                      return v8;
                    v11 = 8195;
                    break;
                  default:
                    return (unsigned int)-2147418113;
                }
                goto LABEL_19;
              }
              goto LABEL_105;
            }
            goto LABEL_106;
          }
LABEL_110:
          v33 = *(const WCHAR **)(this + 104);
          if ( !v33 )
            goto LABEL_61;
          if ( !*((_QWORD *)v7 + 14) )
            goto LABEL_61;
          *(_OWORD *)&pclsid.vt = 0;
          if ( SHCLSIDFromString(v33, (CLSID *)&pclsid) < 0 || a4 )
            goto LABEL_61;
          v63 = (unsigned __int16 *)*((_QWORD *)v7 + 12);
          v32 = (const WCHAR *)*((_QWORD *)v7 + 14);
          goto LABEL_115;
        }
LABEL_129:
        v9 = 49;
        goto LABEL_16;
      }
      if ( a2 == 38010 )
        goto LABEL_129;
      if ( a2 != 38017 )
      {
        if ( a2 != 38018 )
        {
          if ( a2 == 38019 )
          {
            v9 = 42;
            goto LABEL_16;
          }
          if ( a2 == 38022 )
          {
            CDocObjectHost::_RenavigateWebBrowser(*(CDocObjectHost **)(this + 16), 0x9486u);
            return v8;
          }
          if ( a2 != 38023 )
          {
            if ( a2 == 38033 )
            {
              CDocObjectHost::OnFixIESecurity(*(CDocObjectHost **)(this + 16));
              return v8;
            }
            return (unsigned int)-2147418113;
          }
          v38 = a3 & 0xFEFFFFFF;
          goto LABEL_184;
        }
        if ( (unsigned int)CSecurityBand::_UpdateIntranetFlags((CSecurityBand *)this) )
          return v8;
      }
      ResetWarnOnIntranetFlag();
      CSecurityBand::_ReloadPage(v7);
      return v8;
    }
    if ( a2 > 38113 )
    {
      if ( a2 != 38114 )
      {
        if ( a2 == 38417 )
        {
          lpszUrlName = (LPCWSTR)CSecurityBand::_GetDialogParentHwnd((CSecurityBand *)this);
          if ( (int)SuppressDialog((HWND *)&lpszUrlName, 1u) >= 0 )
            ShowLanguageDialogThroughBroker((HWND)lpszUrlName);
          return v8;
        }
        if ( a2 != 38434 )
        {
          switch ( a2 )
          {
            case 38451:
              v9 = 43;
              goto LABEL_16;
            case 38453:
              v9 = 76;
              goto LABEL_16;
            case 57428:
              CSecurityBand::_RefreshPage((CSecurityBand *)this, 0x8000000u);
              v45 = *((_QWORD *)v7 + 13) == 0;
              v53 = &SrcStr;
              v54 = &SrcStr;
              LODWORD(lpszUrlName) = 2;
              if ( !v45 )
                v54 = (const WCHAR *)*((_QWORD *)v7 + 13);
              p_pclsid = &pclsid;
              *(_QWORD *)&pclsid.vt = v54;
              v49 = &v67;
              v55 = (const WCHAR *)*((_QWORD *)v7 + 20);
              p_lpszUrlName = &lpszUrlName;
              v65 = 3414;
              if ( v55 )
                v53 = v55;
              *(_QWORD *)&v67.Data1 = v53;
              v52 = (LPCWSTR *)&v65;
              break;
            case 57429:
              v44 = *(const unsigned __int16 **)(this + 168);
              if ( !v44 )
                return v8;
              CDocObjectHost::_Navigate(*(CDocObjectHost **)(this + 16), v44, 1u);
              v45 = *((_QWORD *)v7 + 13) == 0;
              v46 = &SrcStr;
              v47 = &SrcStr;
              v65 = 1;
              if ( !v45 )
                v47 = (const WCHAR *)*((_QWORD *)v7 + 13);
              p_pclsid = &v67;
              *(_QWORD *)&v67.Data1 = v47;
              v49 = &pclsid;
              v50 = (const WCHAR *)*((_QWORD *)v7 + 20);
              p_lpszUrlName = (LPCWSTR *)&v65;
              LODWORD(lpszUrlName) = 3414;
              if ( v50 )
                v46 = v50;
              *(_QWORD *)&pclsid.vt = v46;
              v52 = &lpszUrlName;
              break;
            default:
              return (unsigned int)-2147418113;
          }
          BrowserTelemetry::IEFrameSecurityBand<int,int,unsigned short const *,unsigned short const *>(
            v52,
            p_lpszUrlName,
            v49,
            p_pclsid);
          return v8;
        }
        v65 = 1;
        v56 = IsProtectedModeProcess();
        if ( v56 )
        {
          if ( v56 == 1 )
            SHSetValueW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\",
              L"DisableIDNPrompt",
              4u,
              &v65,
              4u);
        }
        else
        {
          CIERegistryHelper::SetSingleValue(8199, &v65, 4, 0);
        }
        v38 = a3 & 0xFF7FFFFF;
LABEL_142:
        v39 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
LABEL_185:
        v42 = v38 | 0x80000000;
LABEL_186:
        CDocObjectHost::_HandlePageActionBlocked(v39, v42, 0);
        return v8;
      }
      *(_DWORD *)(this + 12) &= ~0x20u;
    }
    else
    {
      if ( a2 != 38113 )
      {
        switch ( a2 )
        {
          case 38035:
            v9 = 41;
            goto LABEL_16;
          case 38039:
            v43 = *(const unsigned __int16 **)(this + 96);
            if ( v43 )
              CDocObjectHost::_Navigate(*(CDocObjectHost **)(this + 16), v43, 0);
            return v8;
          case 38041:
            v65 = 1;
            CIERegistryHelper::SetSingleValue(8194, &v65, 4, 0);
            v41 = a3 & 0xBFFFFFFF;
            if ( (*((_DWORD *)v7 + 3) & 0xFFFFFFFB) != 0 )
              v41 = a3;
            CheckProtectedModeOff(1);
            v39 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
            v42 = v41 | 0x80000000;
            goto LABEL_186;
          case 38042:
            CSecurityBand::_TurnOnProtectedMode((CSecurityBand *)this);
            return v8;
          case 38044:
            v40 = *(_QWORD *)(this + 16);
            pclsid.vt = 3;
            pclsid.lVal = 0x20000;
            CDocObjectHost::ExecDown((CDocObjectHost *)(v40 + 72), &CGID_MSHTML, 0x3AFCu, 0, &pclsid, 0);
            goto LABEL_26;
          case 38046:
            return v8;
          case 38047:
            v9 = 40;
            goto LABEL_16;
        }
        if ( a2 != 38112 )
          return (unsigned int)-2147418113;
        CSecurityBand::_DisableRequiresActiveXPrompt((CSecurityBand *)this);
        *((_DWORD *)v7 + 3) &= ~0x10u;
        v38 = a3 & 0x3FFFFFFF;
        goto LABEL_142;
      }
      *(_DWORD *)(this + 12) &= ~0x10u;
    }
    v38 = a3 & 0x3FFFFFFF;
LABEL_184:
    v39 = *(CDocObjectHost **)(this + 16);
    goto LABEL_185;
  }
  if ( a2 == 37986 )
    goto LABEL_105;
  if ( a2 > 37746 )
  {
    if ( a2 > 37778 )
    {
      if ( a2 == 37889 || a2 == 37905 || a2 == 37921 || a2 == 37937 || a2 == 37953 )
      {
        LoadStringW(g_hinstMUI, 0x8614u, Caption, 256);
        LoadStringW(g_hinstMUI, 0x8615u, Buffer, 256);
        DialogParentHwnd = CSecurityBand::_GetDialogParentHwnd(v7);
        if ( MessageBoxW(DialogParentHwnd, Caption, Buffer, 1u) != 1 )
          return v8;
        v11 = 0;
        v27 = a2 - 37889;
        if ( v27 )
        {
          v28 = v27 - 16;
          if ( v28 )
          {
            v29 = v28 - 16;
            if ( v29 )
            {
              v30 = v29 - 16;
              if ( v30 )
              {
                if ( v30 == 16 )
                  v11 = 0x1000000;
              }
              else
              {
                v11 = 0x800000;
              }
            }
            else
            {
              v11 = 0x200000;
            }
          }
          else
          {
            v11 = 0x400000;
          }
        }
        else
        {
          v11 = 0x100000;
        }
        goto LABEL_19;
      }
      this = (unsigned int)(a2 - 37969);
      if ( a2 == 37969 )
        goto LABEL_15;
      if ( a2 != 37985 )
        return (unsigned int)-2147418113;
      v22 = (const WCHAR *)*((_QWORD *)v7 + 13);
      if ( v22 )
      {
        *(_OWORD *)&pclsid.vt = 0;
        if ( SHCLSIDFromString(v22, (CLSID *)&pclsid) >= 0 )
        {
          v23 = (const unsigned __int16 *)*((_QWORD *)v7 + 7);
          v24 = *((_DWORD *)v7 + 34) != 0;
          v25 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
          cbDataa = (const unsigned __int16 *)*((_QWORD *)v7 + 12);
          pvDataa = (const unsigned __int16 *)*((_QWORD *)v7 + 6);
          v67 = *(struct _GUID *)&pclsid.vt;
          CDocObjectHost::_ShowActiveXApproval(v25, &v67, v24, v23, pvDataa, cbDataa, 1);
        }
      }
      return v8;
    }
    switch ( a2 )
    {
      case 37778:
        v9 = 47;
        goto LABEL_16;
      case 37761:
        v21 = 1024;
        goto LABEL_64;
      case 37762:
        goto LABEL_62;
      case 37764:
        v17 = *(const WCHAR **)(this + 104);
        if ( v17 )
        {
          if ( *((_QWORD *)v7 + 14) )
          {
            *(_OWORD *)&pclsid.vt = 0;
            if ( SHCLSIDFromString(v17, (CLSID *)&pclsid) >= 0 )
            {
              v18 = (const unsigned __int16 *)*((_QWORD *)v7 + 7);
              v19 = *((_DWORD *)v7 + 34) != 0;
              v20 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
              cbData = (const unsigned __int16 *)*((_QWORD *)v7 + 12);
              pvData = (const unsigned __int16 *)*((_QWORD *)v7 + 6);
              v67 = *(struct _GUID *)&pclsid.vt;
              CDocObjectHost::_ShowActiveXApproval(v20, &v67, v19, v18, pvData, cbData, 0);
            }
          }
        }
        goto LABEL_61;
      case 37765:
        goto LABEL_105;
    }
    if ( a2 != 37767 )
    {
      if ( a2 != 37768 )
      {
        if ( a2 != 37769 )
        {
          if ( a2 != 37777 )
            return (unsigned int)-2147418113;
          v15 = *(CDocObjectHost **)(this + 16);
          if ( v15 )
          {
            CDocObjectHost::SetIgnoreMimeSettings(v15, 3u);
            v16 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
            lpszUrlName = 0;
            if ( !(unsigned int)CDocObjectHost::_GetCurrentPageW(v16, (unsigned __int16 **)&lpszUrlName, 1) )
            {
              DeleteUrlCacheEntryW(lpszUrlName);
              CDocObjectHost::_Navigate(*((CDocObjectHost **)v7 + 2), lpszUrlName, 0);
              CoTaskMemFree((LPVOID)lpszUrlName);
            }
          }
          return v8;
        }
LABEL_105:
        v9 = 20;
        goto LABEL_16;
      }
LABEL_106:
      v31 = *(const WCHAR **)(this + 104);
      if ( !v31 )
        goto LABEL_61;
      *(_OWORD *)&pclsid.vt = 0;
      if ( SHCLSIDFromString(v31, (CLSID *)&pclsid) < 0 || a4 )
        goto LABEL_61;
      v63 = (unsigned __int16 *)*((_QWORD *)v7 + 12);
      v32 = L"*";
LABEL_115:
      v34 = (const unsigned __int16 *)*((_QWORD *)v7 + 7);
      v35 = *((_DWORD *)v7 + 34) != 0;
      v36 = (CDocObjectHost *)*((_QWORD *)v7 + 2);
      cbDatab = v32;
      v37 = (const unsigned __int16 *)*((_QWORD *)v7 + 6);
      v67 = *(struct _GUID *)&pclsid.vt;
      CDocObjectHost::_ShowActiveXDomainApproval(v36, &v67, v35, v34, v37, cbDatab, v63, v64);
LABEL_61:
      v21 = 0;
      this = (unsigned __int64)v7;
LABEL_64:
      CSecurityBand::_NavigateToActionBlockedUrl((CSecurityBand *)this, v21);
      return v8;
    }
    goto LABEL_110;
  }
  if ( a2 == 37746 )
  {
    v9 = 16;
    goto LABEL_16;
  }
  if ( a2 <= 37713 )
  {
    if ( a2 != 37713 )
    {
      switch ( a2 )
      {
        case 0:
          return (unsigned int)ResultFromKnownLastError();
        case 37634:
          goto LABEL_15;
        case 37649:
          v11 = 0x20000;
          goto LABEL_23;
        case 37650:
          v9 = 46;
          goto LABEL_16;
        case 37665:
          v10 = 1;
LABEL_18:
          CSecurityBand::_ActiveXInstallOleCommandDesktop((CSecurityBand *)this, v10);
          v11 = 0x10000;
LABEL_19:
          this = (unsigned __int64)v7;
LABEL_23:
          CSecurityBand::_RefreshPage((CSecurityBand *)this, v11);
          return v8;
      }
      if ( a2 != 37666 )
      {
        if ( a2 != 37667 )
        {
          if ( a2 == 37681 )
          {
LABEL_15:
            v9 = 15;
LABEL_16:
            IELaunchPlatformHelp(this, v9);
            return v8;
          }
          return (unsigned int)-2147418113;
        }
        v10 = 2;
        goto LABEL_18;
      }
LABEL_62:
      v9 = 17;
      goto LABEL_16;
    }
    v12 = *(_QWORD *)(this + 16);
    pclsid.vt = 3;
    pclsid.lVal = 64;
    CDocObjectHost::ExecDown((CDocObjectHost *)(v12 + 72), &CGID_MSHTML, 0x3AFCu, 0, &pclsid, 0);
    CDocObjectHost::OnExecPopupMgrMenuItem((CDocObjectHost *)(*((_QWORD *)v7 + 2) + 136LL), 1u, 0);
LABEL_26:
    ATL::CComVariant::Clear((ATL::CComVariant *)&pclsid);
    return v8;
  }
  switch ( a2 )
  {
    case 37728:
      v14 = 3;
      goto LABEL_42;
    case 37729:
      v14 = 2;
      goto LABEL_42;
    case 37730:
    case 37731:
      v14 = 5;
      goto LABEL_42;
    case 37732:
      v14 = 4;
      goto LABEL_42;
    case 37733:
      v14 = 6;
LABEL_42:
      CDocObjectHost::OnExecPopupMgrMenuItem((CDocObjectHost *)(*(_QWORD *)(this + 16) + 136LL), v14, 0);
      return v8;
  }
  if ( a2 != 37745 )
    return (unsigned int)-2147418113;
  if ( a4
    || (LoadStringW(g_hinstMUI, 0x8612u, Buffer, 256),
        LoadStringW(g_hinstMUI, 0x8613u, Caption, 256),
        v13 = CSecurityBand::_GetDialogParentHwnd(v7),
        MessageBoxW(v13, Buffer, Caption, 0x134u) == 6) )
  {
    v11 = 0x40000;
    goto LABEL_19;
  }
  return v8;
}

```

## disassembly

```asm
0x180191d90  mov     [rsp-8+arg_8], rbx
0x180191d95  mov     [rsp-8+arg_18], rsi
0x180191d9a  push    rbp
0x180191d9b  push    rdi
0x180191d9c  push    r12
0x180191d9e  push    r14
0x180191da0  push    r15
0x180191da2  lea     rbp, [rsp-390h]
0x180191daa  sub     rsp, 490h
0x180191db1  mov     rax, cs:__security_cookie
0x180191db8  xor     rax, rsp
0x180191dbb  mov     [rbp+3B0h+var_30], rax
0x180191dc2  xor     r12d, r12d
0x180191dc5  mov     eax, 9462h
0x180191dca  mov     r14b, r9b
0x180191dcd  mov     esi, r8d
0x180191dd0  mov     ebx, edx
0x180191dd2  mov     rdi, rcx
0x180191dd5  mov     r15d, r12d
0x180191dd8  cmp     edx, eax
0x180191dda  jg      loc_18019229B
0x180191de0  jz      loc_18019234E
0x180191de6  mov     eax, 9372h
0x180191deb  cmp     edx, eax
0x180191ded  jg      loc_180191FDF
0x180191df3  jz      loc_180191FD5
0x180191df9  mov     eax, 9351h
0x180191dfe  cmp     edx, eax
0x180191e00  jg      loc_180191EEB
0x180191e06  jz      short loc_180191E87
0x180191e08  test    edx, edx
0x180191e0a  jz      short loc_180191E7A
0x180191e0c  sub     ebx, 9302h
0x180191e12  jz      short loc_180191E3A
0x180191e14  sub     ebx, 0Fh
0x180191e17  jz      short loc_180191E6B
0x180191e19  sub     ebx, 1
0x180191e1c  jz      short loc_180191E64
0x180191e1e  sub     ebx, 0Fh
0x180191e21  jz      short loc_180191E5D
0x180191e23  sub     ebx, 1
0x180191e26  jz      loc_18019210C
0x180191e2c  sub     ebx, 1
0x180191e2f  jz      short loc_180191E49
0x180191e31  cmp     ebx, 0Eh
0x180191e34  jnz     loc_180192659
0x180191e3a  mov     edx, 0Fh
0x180191e3f  call    IELaunchPlatformHelp
0x180191e44  jmp     loc_1801927FB
0x180191e49  mov     edx, 2; unsigned int
0x180191e4e  call    ?_ActiveXInstallOleCommandDesktop@CSecurityBand@@AEAAXK@Z; CSecurityBand::_ActiveXInstallOleCommandDesktop(ulong)
0x180191e53  mov     edx, 10000h
0x180191e58  mov     rcx, rdi; this
0x180191e5b  jmp     short loc_180191E70
0x180191e5d  mov     edx, 1
0x180191e62  jmp     short loc_180191E4E
0x180191e64  mov     edx, 2Eh ; '.'
0x180191e69  jmp     short loc_180191E3F
0x180191e6b  mov     edx, 20000h; unsigned int
0x180191e70  call    ?_RefreshPage@CSecurityBand@@AEAAXK@Z; CSecurityBand::_RefreshPage(ulong)
0x180191e75  jmp     loc_1801927FB
0x180191e7a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180191e7f  mov     r15d, eax
0x180191e82  jmp     loc_1801927FB
0x180191e87  mov     rcx, [rcx+10h]
0x180191e8b  lea     rdx, CGID_MSHTML; struct _GUID *
0x180191e92  mov     eax, 3
0x180191e97  mov     qword ptr [rsp+4B0h+cbData], r12; struct tagVARIANT *
0x180191e9c  mov     word ptr [rsp+4B0h+pclsid.Data1], ax
0x180191ea1  add     rcx, 48h ; 'H'; this
0x180191ea5  lea     rax, [rsp+4B0h+pclsid]
0x180191eaa  mov     dword ptr [rsp+4B0h+pclsid.Data4], 40h ; '@'
0x180191eb2  xor     r9d, r9d; unsigned int
0x180191eb5  mov     [rsp+4B0h+pvData], rax; struct tagVARIANT *
0x180191eba  mov     r8d, 3AFCh; unsigned int
0x180191ec0  call    ?ExecDown@CDocObjectHost@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z; CDocObjectHost::ExecDown(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x180191ec5  mov     rcx, [rdi+10h]
0x180191ec9  xor     r8d, r8d; unsigned int
0x180191ecc  add     rcx, 88h; this
0x180191ed3  lea     edx, [r8+1]; unsigned int
0x180191ed7  call    ?OnExecPopupMgrMenuItem@CDocObjectHost@@UEAAJII@Z; CDocObjectHost::OnExecPopupMgrMenuItem(uint,uint)
0x180191edc  lea     rcx, [rsp+4B0h+pclsid]; this
0x180191ee1  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180191ee6  jmp     loc_1801927FB
0x180191eeb  sub     ebx, 9360h
0x180191ef1  jz      loc_180191FB8
0x180191ef7  sub     ebx, 1
0x180191efa  jz      loc_180191FB1
0x180191f00  sub     ebx, 1
0x180191f03  jz      loc_180191FAA
0x180191f09  sub     ebx, 1
0x180191f0c  jz      loc_180191FAA
0x180191f12  sub     ebx, 1
0x180191f15  jz      loc_180191FA3
0x180191f1b  sub     ebx, 1
0x180191f1e  jz      short loc_180191F9C
0x180191f20  cmp     ebx, 0Ch
0x180191f23  jnz     loc_180192659
0x180191f29  test    r14b, r14b
0x180191f2c  jnz     short loc_180191F92
0x180191f2e  mov     rcx, cs:g_hinstMUI; hInstance
0x180191f35  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x180191f3c  mov     r14d, 100h
0x180191f42  mov     edx, 8612h; uID
0x180191f47  mov     r9d, r14d; cchBufferMax
0x180191f4a  call    cs:__imp_LoadStringW
0x180191f50  mov     rcx, cs:g_hinstMUI; hInstance
0x180191f57  lea     r8, [rbp+3B0h+Caption]; lpBuffer
0x180191f5b  mov     r9d, r14d; cchBufferMax
0x180191f5e  mov     edx, 8613h; uID
0x180191f63  call    cs:__imp_LoadStringW
0x180191f69  mov     rcx, rdi; this
0x180191f6c  call    ?_GetDialogParentHwnd@CSecurityBand@@AEAAPEAUHWND__@@XZ; CSecurityBand::_GetDialogParentHwnd(void)
0x180191f71  mov     rcx, rax; hWnd
0x180191f74  lea     r9d, [r14+34h]; uType
0x180191f78  lea     r8, [rbp+3B0h+Caption]; lpCaption
0x180191f7c  lea     rdx, [rbp+3B0h+Buffer]; lpText
0x180191f83  call    cs:__imp_MessageBoxW
0x180191f89  cmp     eax, 6
0x180191f8c  jnz     loc_1801927FB
0x180191f92  mov     edx, 40000h
0x180191f97  jmp     loc_180191E58
0x180191f9c  mov     edx, 6
0x180191fa1  jmp     short loc_180191FBD
0x180191fa3  mov     edx, 4
0x180191fa8  jmp     short loc_180191FBD
0x180191faa  mov     edx, 5
0x180191faf  jmp     short loc_180191FBD
0x180191fb1  mov     edx, 2
0x180191fb6  jmp     short loc_180191FBD
0x180191fb8  mov     edx, 3; unsigned int
0x180191fbd  mov     rcx, [rcx+10h]
0x180191fc1  xor     r8d, r8d; unsigned int
0x180191fc4  add     rcx, 88h; this
0x180191fcb  call    ?OnExecPopupMgrMenuItem@CDocObjectHost@@UEAAJII@Z; CDocObjectHost::OnExecPopupMgrMenuItem(uint,uint)
0x180191fd0  jmp     loc_1801927FB
0x180191fd5  mov     edx, 10h
0x180191fda  jmp     loc_180191E3F
0x180191fdf  mov     eax, 9392h
0x180191fe4  cmp     ebx, eax
0x180191fe6  jg      loc_18019212F
0x180191fec  jz      loc_180192125
0x180191ff2  sub     ebx, 9381h
0x180191ff8  jz      loc_180192116
0x180191ffe  sub     ebx, 1
0x180192001  jz      loc_18019210C
0x180192007  sub     ebx, 2
0x18019200a  jz      loc_18019209D
0x180192010  sub     ebx, 1
0x180192013  jz      loc_18019234E
0x180192019  sub     ebx, 2
0x18019201c  jz      loc_18019239B
0x180192022  sub     ebx, 1
0x180192025  jz      loc_180192358
0x18019202b  sub     ebx, 1
0x18019202e  jz      loc_18019234E
0x180192034  cmp     ebx, 8
0x180192037  jnz     loc_180192659
0x18019203d  mov     rcx, [rcx+10h]; this
0x180192041  test    rcx, rcx
0x180192044  jz      loc_1801927FB
0x18019204a  lea     edx, [rbx-5]; unsigned int
0x18019204d  call    ?SetIgnoreMimeSettings@CDocObjectHost@@QEAAJI@Z; CDocObjectHost::SetIgnoreMimeSettings(uint)
0x180192052  mov     rcx, [rdi+10h]; this
0x180192056  lea     r8d, [rbx-7]; int
0x18019205a  lea     rdx, [rsp+4B0h+lpszUrlName]; unsigned __int16 **
0x18019205f  mov     [rsp+4B0h+lpszUrlName], r12
0x180192064  call    ?_GetCurrentPageW@CDocObjectHost@@IEAAJPEAPEAGH@Z; CDocObjectHost::_GetCurrentPageW(ushort * *,int)
0x180192069  test    eax, eax
0x18019206b  jnz     loc_1801927FB
0x180192071  mov     rcx, [rsp+4B0h+lpszUrlName]; lpszUrlName
0x180192076  call    cs:__imp_DeleteUrlCacheEntryW
0x18019207c  mov     rdx, [rsp+4B0h+lpszUrlName]; unsigned __int16 *
0x180192081  xor     r8d, r8d; unsigned int
0x180192084  mov     rcx, [rdi+10h]; this
0x180192088  call    ?_Navigate@CDocObjectHost@@IEAAXPEBGK@Z; CDocObjectHost::_Navigate(ushort const *,ulong)
0x18019208d  mov     rcx, [rsp+4B0h+lpszUrlName]; pv
0x180192092  call    cs:__imp_CoTaskMemFree
0x180192098  jmp     loc_1801927FB
0x18019209d  mov     rcx, [rcx+68h]; psz
0x1801920a1  test    rcx, rcx
0x1801920a4  jz      short loc_180192105
0x1801920a6  cmp     [rdi+70h], r12
0x1801920aa  jz      short loc_180192105
0x1801920ac  xorps   xmm0, xmm0
0x1801920af  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x1801920b4  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x1801920b9  call    cs:__imp_SHCLSIDFromString
0x1801920bf  test    eax, eax
0x1801920c1  js      short loc_180192105
0x1801920c3  mov     rax, [rdi+60h]
0x1801920c7  lea     rdx, [rsp+4B0h+var_460]; struct _GUID
0x1801920cc  cmp     [rdi+88h], r12d
0x1801920d3  mov     r8d, r12d
0x1801920d6  movaps  xmm0, xmmword ptr [rsp+4B0h+pclsid.Data1]
0x1801920db  mov     r9, [rdi+38h]; unsigned __int16 *
0x1801920df  setnz   r8b; int
0x1801920e3  mov     rcx, [rdi+10h]; this
0x1801920e7  mov     dword ptr [rsp+4B0h+var_480], r12d; int
0x1801920ec  mov     qword ptr [rsp+4B0h+cbData], rax; unsigned __int16 *
0x1801920f1  mov     rax, [rdi+30h]
0x1801920f5  mov     [rsp+4B0h+pvData], rax; unsigned __int16 *
0x1801920fa  movdqa  xmmword ptr [rsp+4B0h+var_460.Data1], xmm0
0x180192100  call    ?_ShowActiveXApproval@CDocObjectHost@@IEAAXU_GUID@@HPEBG11H@Z; CDocObjectHost::_ShowActiveXApproval(_GUID,int,ushort const *,ushort const *,ushort const *,int)
0x180192105  xor     edx, edx
0x180192107  mov     rcx, rdi; this
0x18019210a  jmp     short loc_18019211B
0x18019210c  mov     edx, 11h
0x180192111  jmp     loc_180191E3F
0x180192116  mov     edx, 400h; unsigned int
0x18019211b  call    ?_NavigateToActionBlockedUrl@CSecurityBand@@AEAAXK@Z; CSecurityBand::_NavigateToActionBlockedUrl(ulong)
0x180192120  jmp     loc_1801927FB
0x180192125  mov     edx, 2Fh ; '/'
0x18019212a  jmp     loc_180191E3F
0x18019212f  mov     ecx, ebx
0x180192131  mov     esi, 10h
0x180192136  sub     ecx, 9401h
0x18019213c  jz      loc_1801921E4
0x180192142  sub     ecx, esi
0x180192144  jz      loc_1801921E4
0x18019214a  sub     ecx, esi
0x18019214c  jz      loc_1801921E4
0x180192152  sub     ecx, esi
0x180192154  jz      loc_1801921E4
0x18019215a  sub     ecx, esi
0x18019215c  jz      loc_1801921E4
0x180192162  sub     ecx, esi
0x180192164  jz      loc_180191E3A
0x18019216a  cmp     ecx, esi
0x18019216c  jnz     loc_180192659
0x180192172  mov     rcx, [rdi+68h]; psz
0x180192176  test    rcx, rcx
0x180192179  jz      loc_1801927FB
0x18019217f  xorps   xmm0, xmm0
0x180192182  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x180192187  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x18019218c  call    cs:__imp_SHCLSIDFromString
0x180192192  test    eax, eax
0x180192194  js      loc_1801927FB
0x18019219a  mov     rax, [rdi+60h]
0x18019219e  lea     rdx, [rsp+4B0h+var_460]; struct _GUID
0x1801921a3  cmp     [rdi+88h], r12d
0x1801921aa  mov     r8d, r12d
0x1801921ad  movaps  xmm0, xmmword ptr [rsp+4B0h+pclsid.Data1]
0x1801921b2  mov     r9, [rdi+38h]; unsigned __int16 *
0x1801921b6  setnz   r8b; int
0x1801921ba  mov     rcx, [rdi+10h]; this
0x1801921be  mov     dword ptr [rsp+4B0h+var_480], 1; int
0x1801921c6  mov     qword ptr [rsp+4B0h+cbData], rax; unsigned __int16 *
0x1801921cb  mov     rax, [rdi+30h]
0x1801921cf  mov     [rsp+4B0h+pvData], rax; unsigned __int16 *
0x1801921d4  movdqa  xmmword ptr [rsp+4B0h+var_460.Data1], xmm0
0x1801921da  call    ?_ShowActiveXApproval@CDocObjectHost@@IEAAXU_GUID@@HPEBG11H@Z; CDocObjectHost::_ShowActiveXApproval(_GUID,int,ushort const *,ushort const *,ushort const *,int)
0x1801921df  jmp     loc_1801927FB
0x1801921e4  mov     rcx, cs:g_hinstMUI; hInstance
0x1801921eb  lea     r8, [rbp+3B0h+Caption]; lpBuffer
0x1801921ef  mov     r14d, 100h
0x1801921f5  mov     edx, 8614h; uID
0x1801921fa  mov     r9d, r14d; cchBufferMax
0x1801921fd  call    cs:__imp_LoadStringW
0x180192203  mov     rcx, cs:g_hinstMUI; hInstance
0x18019220a  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x180192211  mov     r9d, r14d; cchBufferMax
0x180192214  mov     edx, 8615h; uID
0x180192219  call    cs:__imp_LoadStringW
0x18019221f  mov     rcx, rdi; this
0x180192222  call    ?_GetDialogParentHwnd@CSecurityBand@@AEAAPEAUHWND__@@XZ; CSecurityBand::_GetDialogParentHwnd(void)
0x180192227  mov     rcx, rax; hWnd
0x18019222a  lea     r8, [rbp+3B0h+Buffer]; lpCaption
0x180192231  mov     r9d, 1; uType
0x180192237  lea     rdx, [rbp+3B0h+Caption]; lpText
0x18019223b  call    cs:__imp_MessageBoxW
0x180192241  cmp     eax, 1
0x180192244  jnz     loc_1801927FB
0x18019224a  mov     edx, r12d
0x18019224d  sub     ebx, 9401h
0x180192253  jz      short loc_180192291
0x180192255  sub     ebx, esi
0x180192257  jz      short loc_180192287
0x180192259  sub     ebx, esi
0x18019225b  jz      short loc_18019227D
0x18019225d  sub     ebx, esi
0x18019225f  jz      short loc_180192273
0x180192261  cmp     ebx, esi
0x180192263  jnz     loc_180191E58
0x180192269  mov     edx, 1000000h
0x18019226e  jmp     loc_180191E58
0x180192273  mov     edx, 800000h
0x180192278  jmp     loc_180191E58
0x18019227d  mov     edx, 200000h
0x180192282  jmp     loc_180191E58
0x180192287  mov     edx, 400000h
0x18019228c  jmp     loc_180191E58
0x180192291  mov     edx, 100000h
0x180192296  jmp     loc_180191E58
0x18019229b  mov     eax, 9492h
0x1801922a0  cmp     ebx, eax
0x1801922a2  jg      loc_1801924D8
0x1801922a8  jz      loc_1801924A4
0x1801922ae  mov     eax, 9478h
  ... truncated ...
```
