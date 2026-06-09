# CSecurityBand::_HandleSecurityCommand(int,ulong,bool)

- ea: `0x1801a5950`
- end: `0x1801a6448`
- name: `?_HandleSecurityCommand@CSecurityBand@@AEAAJHK_N@Z`
- size: `2808`
- prototype: `__int64 __fastcall(CSecurityBand *__hidden this, int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a2ddc`
- `0x1801a3d40`

## callees

- `0x18000bc38`
- `0x180033ff0`
- `0x1800511b0`
- `0x18005c660`
- `0x18007587c`
- `0x18009510c`
- `0x180143cf0`
- `0x180143e20`
- `0x1801446c4`
- `0x18014c27c`
- `0x18014e4d4`
- `0x1801532ec`
- `0x180153960`
- `0x180153b14`
- `0x1801a2b40`
- `0x1801a3cb8`
- `0x1801a3e74`
- `0x1801a474c`
- `0x1801a5318`
- `0x1801a5950`
- `0x1801a64d8`
- `0x1801a653c`
- `0x1801a65ac`
- `0x1801a6c70`
- `0x1801a6e3c`
- `0x180266190`
- `0x18043ae0c`
- `0x1805251e4`
- `0x180529a08`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5b0e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5b2d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5deb`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5e0d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5b0e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5b2d`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5deb`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801a5e0d`
- `USER32!MessageBoxW` at `0x1801a5b53`
- `USER32!MessageBoxW` at `0x1801a5e35`
- `USER32!MessageBoxW` at `0x1801a5b53`
- `USER32!MessageBoxW` at `0x1801a5e35`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5c9b`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5d74`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5f72`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5fc5`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5c9b`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5d74`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5f72`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a5fc5`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801a6365`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801a6365`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a5c6e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a5c6e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1801a63bf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1801a63bf`
- `WININET!DeleteUrlCacheEntryW` at `0x1801a5c4c`
- `WININET!DeleteUrlCacheEntryW` at `0x1801a5c4c`
- `urlmon!__imp_ResetWarnOnIntranetFlag` at `0x1801a6093`
- `urlmon!__imp_ResetWarnOnIntranetFlag` at `0x1801a6093`

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
  const OLECHAR *v46; // rcx
  const OLECHAR *v47; // rax
  void *p_pclsid; // r9
  void *v49; // r8
  const OLECHAR *v50; // rax
  LPCWSTR *p_lpszUrlName; // rdx
  LPCWSTR *v52; // rcx
  const OLECHAR *v53; // rcx
  const OLECHAR *v54; // rax
  const OLECHAR *v55; // rax
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
              v53 = &Default;
              v54 = &Default;
              LODWORD(lpszUrlName) = 2;
              if ( !v45 )
                v54 = (const OLECHAR *)*((_QWORD *)v7 + 13);
              p_pclsid = &pclsid;
              *(_QWORD *)&pclsid.vt = v54;
              v49 = &v67;
              v55 = (const OLECHAR *)*((_QWORD *)v7 + 20);
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
              v46 = &Default;
              v47 = &Default;
              v65 = 1;
              if ( !v45 )
                v47 = (const OLECHAR *)*((_QWORD *)v7 + 13);
              p_pclsid = &v67;
              *(_QWORD *)&v67.Data1 = v47;
              v49 = &pclsid;
              v50 = (const OLECHAR *)*((_QWORD *)v7 + 20);
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
0x1801a5950  mov     [rsp-8+arg_8], rbx
0x1801a5955  mov     [rsp-8+arg_18], rsi
0x1801a595a  push    rbp
0x1801a595b  push    rdi
0x1801a595c  push    r12
0x1801a595e  push    r14
0x1801a5960  push    r15
0x1801a5962  lea     rbp, [rsp-390h]
0x1801a596a  sub     rsp, 490h
0x1801a5971  mov     rax, cs:__security_cookie
0x1801a5978  xor     rax, rsp
0x1801a597b  mov     [rbp+3B0h+var_30], rax
0x1801a5982  xor     r12d, r12d
0x1801a5985  mov     eax, 9462h
0x1801a598a  mov     r14b, r9b
0x1801a598d  mov     esi, r8d
0x1801a5990  mov     ebx, edx
0x1801a5992  mov     rdi, rcx
0x1801a5995  mov     r15d, r12d
0x1801a5998  cmp     edx, eax
0x1801a599a  jg      loc_1801A5E9B
0x1801a59a0  jz      loc_1801A5F4E
0x1801a59a6  mov     eax, 9372h
0x1801a59ab  cmp     edx, eax
0x1801a59ad  jg      loc_1801A5BB5
0x1801a59b3  jz      loc_1801A5BAB
0x1801a59b9  mov     eax, 9351h
0x1801a59be  cmp     edx, eax
0x1801a59c0  jg      loc_1801A5AAB
0x1801a59c6  jz      short loc_1801A5A47
0x1801a59c8  test    edx, edx
0x1801a59ca  jz      short loc_1801A5A3A
0x1801a59cc  sub     ebx, 9302h
0x1801a59d2  jz      short loc_1801A59FA
0x1801a59d4  sub     ebx, 0Fh
0x1801a59d7  jz      short loc_1801A5A2B
0x1801a59d9  sub     ebx, 1
0x1801a59dc  jz      short loc_1801A5A24
0x1801a59de  sub     ebx, 0Fh
0x1801a59e1  jz      short loc_1801A5A1D
0x1801a59e3  sub     ebx, 1
0x1801a59e6  jz      loc_1801A5CF4
0x1801a59ec  sub     ebx, 1
0x1801a59ef  jz      short loc_1801A5A09
0x1801a59f1  cmp     ebx, 0Eh
0x1801a59f4  jnz     loc_1801A626B
0x1801a59fa  mov     edx, 0Fh
0x1801a59ff  call    IELaunchPlatformHelp
0x1801a5a04  jmp     loc_1801A6419
0x1801a5a09  mov     edx, 2; unsigned int
0x1801a5a0e  call    ?_ActiveXInstallOleCommandDesktop@CSecurityBand@@AEAAXK@Z; CSecurityBand::_ActiveXInstallOleCommandDesktop(ulong)
0x1801a5a13  mov     edx, 10000h
0x1801a5a18  mov     rcx, rdi; this
0x1801a5a1b  jmp     short loc_1801A5A30
0x1801a5a1d  mov     edx, 1
0x1801a5a22  jmp     short loc_1801A5A0E
0x1801a5a24  mov     edx, 2Eh ; '.'
0x1801a5a29  jmp     short loc_1801A59FF
0x1801a5a2b  mov     edx, 20000h; unsigned int
0x1801a5a30  call    ?_RefreshPage@CSecurityBand@@AEAAXK@Z; CSecurityBand::_RefreshPage(ulong)
0x1801a5a35  jmp     loc_1801A6419
0x1801a5a3a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801a5a3f  mov     r15d, eax
0x1801a5a42  jmp     loc_1801A6419
0x1801a5a47  mov     rcx, [rcx+10h]
0x1801a5a4b  lea     rdx, CGID_MSHTML; struct _GUID *
0x1801a5a52  mov     eax, 3
0x1801a5a57  mov     qword ptr [rsp+4B0h+cbData], r12; struct tagVARIANT *
0x1801a5a5c  mov     word ptr [rsp+4B0h+pclsid.Data1], ax
0x1801a5a61  add     rcx, 48h ; 'H'; this
0x1801a5a65  lea     rax, [rsp+4B0h+pclsid]
0x1801a5a6a  mov     dword ptr [rsp+4B0h+pclsid.Data4], 40h ; '@'
0x1801a5a72  xor     r9d, r9d; unsigned int
0x1801a5a75  mov     [rsp+4B0h+pvData], rax; struct tagVARIANT *
0x1801a5a7a  mov     r8d, 3AFCh; unsigned int
0x1801a5a80  call    ?ExecDown@CDocObjectHost@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z; CDocObjectHost::ExecDown(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1801a5a85  mov     rcx, [rdi+10h]
0x1801a5a89  xor     r8d, r8d; unsigned int
0x1801a5a8c  add     rcx, 88h; this
0x1801a5a93  lea     edx, [r8+1]; unsigned int
0x1801a5a97  call    ?OnExecPopupMgrMenuItem@CDocObjectHost@@UEAAJII@Z; CDocObjectHost::OnExecPopupMgrMenuItem(uint,uint)
0x1801a5a9c  lea     rcx, [rsp+4B0h+pclsid]; this
0x1801a5aa1  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1801a5aa6  jmp     loc_1801A6419
0x1801a5aab  sub     ebx, 9360h
0x1801a5ab1  jz      loc_1801A5B8E
0x1801a5ab7  sub     ebx, 1
0x1801a5aba  jz      loc_1801A5B87
0x1801a5ac0  sub     ebx, 1
0x1801a5ac3  jz      loc_1801A5B80
0x1801a5ac9  sub     ebx, 1
0x1801a5acc  jz      loc_1801A5B80
0x1801a5ad2  sub     ebx, 1
0x1801a5ad5  jz      loc_1801A5B79
0x1801a5adb  sub     ebx, 1
0x1801a5ade  jz      loc_1801A5B72
0x1801a5ae4  cmp     ebx, 0Ch
0x1801a5ae7  jnz     loc_1801A626B
0x1801a5aed  test    r14b, r14b
0x1801a5af0  jnz     short loc_1801A5B68
0x1801a5af2  mov     rcx, cs:g_hinstMUI; hInstance
0x1801a5af9  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x1801a5b00  mov     r14d, 100h
0x1801a5b06  mov     edx, 8612h; uID
0x1801a5b0b  mov     r9d, r14d; cchBufferMax
0x1801a5b0e  call    cs:__imp_LoadStringW
0x1801a5b15  nop     dword ptr [rax+rax+00h]
0x1801a5b1a  mov     rcx, cs:g_hinstMUI; hInstance
0x1801a5b21  lea     r8, [rbp+3B0h+Caption]; lpBuffer
0x1801a5b25  mov     r9d, r14d; cchBufferMax
0x1801a5b28  mov     edx, 8613h; uID
0x1801a5b2d  call    cs:__imp_LoadStringW
0x1801a5b34  nop     dword ptr [rax+rax+00h]
0x1801a5b39  mov     rcx, rdi; this
0x1801a5b3c  call    ?_GetDialogParentHwnd@CSecurityBand@@AEAAPEAUHWND__@@XZ; CSecurityBand::_GetDialogParentHwnd(void)
0x1801a5b41  mov     rcx, rax; hWnd
0x1801a5b44  lea     r9d, [r14+34h]; uType
0x1801a5b48  lea     r8, [rbp+3B0h+Caption]; lpCaption
0x1801a5b4c  lea     rdx, [rbp+3B0h+Buffer]; lpText
0x1801a5b53  call    cs:__imp_MessageBoxW
0x1801a5b5a  nop     dword ptr [rax+rax+00h]
0x1801a5b5f  cmp     eax, 6
0x1801a5b62  jnz     loc_1801A6419
0x1801a5b68  mov     edx, 40000h
0x1801a5b6d  jmp     loc_1801A5A18
0x1801a5b72  mov     edx, 6
0x1801a5b77  jmp     short loc_1801A5B93
0x1801a5b79  mov     edx, 4
0x1801a5b7e  jmp     short loc_1801A5B93
0x1801a5b80  mov     edx, 5
0x1801a5b85  jmp     short loc_1801A5B93
0x1801a5b87  mov     edx, 2
0x1801a5b8c  jmp     short loc_1801A5B93
0x1801a5b8e  mov     edx, 3; unsigned int
0x1801a5b93  mov     rcx, [rcx+10h]
0x1801a5b97  xor     r8d, r8d; unsigned int
0x1801a5b9a  add     rcx, 88h; this
0x1801a5ba1  call    ?OnExecPopupMgrMenuItem@CDocObjectHost@@UEAAJII@Z; CDocObjectHost::OnExecPopupMgrMenuItem(uint,uint)
0x1801a5ba6  jmp     loc_1801A6419
0x1801a5bab  mov     edx, 10h
0x1801a5bb0  jmp     loc_1801A59FF
0x1801a5bb5  mov     eax, 9392h
0x1801a5bba  cmp     ebx, eax
0x1801a5bbc  jg      loc_1801A5D17
0x1801a5bc2  jz      loc_1801A5D0D
0x1801a5bc8  sub     ebx, 9381h
0x1801a5bce  jz      loc_1801A5CFE
0x1801a5bd4  sub     ebx, 1
0x1801a5bd7  jz      loc_1801A5CF4
0x1801a5bdd  sub     ebx, 2
0x1801a5be0  jz      loc_1801A5C7F
0x1801a5be6  sub     ebx, 1
0x1801a5be9  jz      loc_1801A5F4E
0x1801a5bef  sub     ebx, 2
0x1801a5bf2  jz      loc_1801A5FA1
0x1801a5bf8  sub     ebx, 1
0x1801a5bfb  jz      loc_1801A5F58
0x1801a5c01  sub     ebx, 1
0x1801a5c04  jz      loc_1801A5F4E
0x1801a5c0a  cmp     ebx, 8
0x1801a5c0d  jnz     loc_1801A626B
0x1801a5c13  mov     rcx, [rcx+10h]; this
0x1801a5c17  test    rcx, rcx
0x1801a5c1a  jz      loc_1801A6419
0x1801a5c20  lea     edx, [rbx-5]; unsigned int
0x1801a5c23  call    ?SetIgnoreMimeSettings@CDocObjectHost@@QEAAJI@Z; CDocObjectHost::SetIgnoreMimeSettings(uint)
0x1801a5c28  mov     rcx, [rdi+10h]; this
0x1801a5c2c  lea     r8d, [rbx-7]; int
0x1801a5c30  lea     rdx, [rsp+4B0h+lpszUrlName]; unsigned __int16 **
0x1801a5c35  mov     [rsp+4B0h+lpszUrlName], r12
0x1801a5c3a  call    ?_GetCurrentPageW@CDocObjectHost@@IEAAJPEAPEAGH@Z; CDocObjectHost::_GetCurrentPageW(ushort * *,int)
0x1801a5c3f  test    eax, eax
0x1801a5c41  jnz     loc_1801A6419
0x1801a5c47  mov     rcx, [rsp+4B0h+lpszUrlName]; lpszUrlName
0x1801a5c4c  call    cs:__imp_DeleteUrlCacheEntryW
0x1801a5c53  nop     dword ptr [rax+rax+00h]
0x1801a5c58  mov     rdx, [rsp+4B0h+lpszUrlName]; unsigned __int16 *
0x1801a5c5d  xor     r8d, r8d; unsigned int
0x1801a5c60  mov     rcx, [rdi+10h]; this
0x1801a5c64  call    ?_Navigate@CDocObjectHost@@IEAAXPEBGK@Z; CDocObjectHost::_Navigate(ushort const *,ulong)
0x1801a5c69  mov     rcx, [rsp+4B0h+lpszUrlName]; pv
0x1801a5c6e  call    cs:__imp_CoTaskMemFree
0x1801a5c75  nop     dword ptr [rax+rax+00h]
0x1801a5c7a  jmp     loc_1801A6419
0x1801a5c7f  mov     rcx, [rcx+68h]; psz
0x1801a5c83  test    rcx, rcx
0x1801a5c86  jz      short loc_1801A5CED
0x1801a5c88  cmp     [rdi+70h], r12
0x1801a5c8c  jz      short loc_1801A5CED
0x1801a5c8e  xorps   xmm0, xmm0
0x1801a5c91  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x1801a5c96  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x1801a5c9b  call    cs:__imp_SHCLSIDFromString
0x1801a5ca2  nop     dword ptr [rax+rax+00h]
0x1801a5ca7  test    eax, eax
0x1801a5ca9  js      short loc_1801A5CED
0x1801a5cab  mov     rax, [rdi+60h]
0x1801a5caf  lea     rdx, [rsp+4B0h+var_460]; struct _GUID
0x1801a5cb4  cmp     [rdi+88h], r12d
0x1801a5cbb  mov     r8d, r12d
0x1801a5cbe  movaps  xmm0, xmmword ptr [rsp+4B0h+pclsid.Data1]
0x1801a5cc3  mov     r9, [rdi+38h]; unsigned __int16 *
0x1801a5cc7  setnz   r8b; int
0x1801a5ccb  mov     rcx, [rdi+10h]; this
0x1801a5ccf  mov     dword ptr [rsp+4B0h+var_480], r12d; int
0x1801a5cd4  mov     qword ptr [rsp+4B0h+cbData], rax; unsigned __int16 *
0x1801a5cd9  mov     rax, [rdi+30h]
0x1801a5cdd  mov     [rsp+4B0h+pvData], rax; unsigned __int16 *
0x1801a5ce2  movdqa  xmmword ptr [rsp+4B0h+var_460.Data1], xmm0
0x1801a5ce8  call    ?_ShowActiveXApproval@CDocObjectHost@@IEAAXU_GUID@@HPEBG11H@Z; CDocObjectHost::_ShowActiveXApproval(_GUID,int,ushort const *,ushort const *,ushort const *,int)
0x1801a5ced  xor     edx, edx
0x1801a5cef  mov     rcx, rdi; this
0x1801a5cf2  jmp     short loc_1801A5D03
0x1801a5cf4  mov     edx, 11h
0x1801a5cf9  jmp     loc_1801A59FF
0x1801a5cfe  mov     edx, 400h; unsigned int
0x1801a5d03  call    ?_NavigateToActionBlockedUrl@CSecurityBand@@AEAAXK@Z; CSecurityBand::_NavigateToActionBlockedUrl(ulong)
0x1801a5d08  jmp     loc_1801A6419
0x1801a5d0d  mov     edx, 2Fh ; '/'
0x1801a5d12  jmp     loc_1801A59FF
0x1801a5d17  mov     ecx, ebx
0x1801a5d19  mov     esi, 10h
0x1801a5d1e  sub     ecx, 9401h
0x1801a5d24  jz      loc_1801A5DD2
0x1801a5d2a  sub     ecx, esi
0x1801a5d2c  jz      loc_1801A5DD2
0x1801a5d32  sub     ecx, esi
0x1801a5d34  jz      loc_1801A5DD2
0x1801a5d3a  sub     ecx, esi
0x1801a5d3c  jz      loc_1801A5DD2
0x1801a5d42  sub     ecx, esi
0x1801a5d44  jz      loc_1801A5DD2
0x1801a5d4a  sub     ecx, esi
0x1801a5d4c  jz      loc_1801A59FA
0x1801a5d52  cmp     ecx, esi
0x1801a5d54  jnz     loc_1801A626B
0x1801a5d5a  mov     rcx, [rdi+68h]; psz
0x1801a5d5e  test    rcx, rcx
0x1801a5d61  jz      loc_1801A6419
0x1801a5d67  xorps   xmm0, xmm0
0x1801a5d6a  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x1801a5d6f  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x1801a5d74  call    cs:__imp_SHCLSIDFromString
0x1801a5d7b  nop     dword ptr [rax+rax+00h]
0x1801a5d80  test    eax, eax
0x1801a5d82  js      loc_1801A6419
0x1801a5d88  mov     rax, [rdi+60h]
0x1801a5d8c  lea     rdx, [rsp+4B0h+var_460]; struct _GUID
0x1801a5d91  cmp     [rdi+88h], r12d
0x1801a5d98  mov     r8d, r12d
0x1801a5d9b  movaps  xmm0, xmmword ptr [rsp+4B0h+pclsid.Data1]
0x1801a5da0  mov     r9, [rdi+38h]; unsigned __int16 *
0x1801a5da4  setnz   r8b; int
0x1801a5da8  mov     rcx, [rdi+10h]; this
0x1801a5dac  mov     dword ptr [rsp+4B0h+var_480], 1; int
0x1801a5db4  mov     qword ptr [rsp+4B0h+cbData], rax; unsigned __int16 *
0x1801a5db9  mov     rax, [rdi+30h]
0x1801a5dbd  mov     [rsp+4B0h+pvData], rax; unsigned __int16 *
0x1801a5dc2  movdqa  xmmword ptr [rsp+4B0h+var_460.Data1], xmm0
0x1801a5dc8  call    ?_ShowActiveXApproval@CDocObjectHost@@IEAAXU_GUID@@HPEBG11H@Z; CDocObjectHost::_ShowActiveXApproval(_GUID,int,ushort const *,ushort const *,ushort const *,int)
0x1801a5dcd  jmp     loc_1801A6419
0x1801a5dd2  mov     rcx, cs:g_hinstMUI; hInstance
0x1801a5dd9  lea     r8, [rbp+3B0h+Caption]; lpBuffer
0x1801a5ddd  mov     r14d, 100h
0x1801a5de3  mov     edx, 8614h; uID
0x1801a5de8  mov     r9d, r14d; cchBufferMax
0x1801a5deb  call    cs:__imp_LoadStringW
0x1801a5df2  nop     dword ptr [rax+rax+00h]
0x1801a5df7  mov     rcx, cs:g_hinstMUI; hInstance
0x1801a5dfe  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x1801a5e05  mov     r9d, r14d; cchBufferMax
0x1801a5e08  mov     edx, 8615h; uID
0x1801a5e0d  call    cs:__imp_LoadStringW
0x1801a5e14  nop     dword ptr [rax+rax+00h]
0x1801a5e19  mov     rcx, rdi; this
0x1801a5e1c  call    ?_GetDialogParentHwnd@CSecurityBand@@AEAAPEAUHWND__@@XZ; CSecurityBand::_GetDialogParentHwnd(void)
0x1801a5e21  mov     rcx, rax; hWnd
0x1801a5e24  lea     r8, [rbp+3B0h+Buffer]; lpCaption
0x1801a5e2b  mov     r9d, 1; uType
0x1801a5e31  lea     rdx, [rbp+3B0h+Caption]; lpText
0x1801a5e35  call    cs:__imp_MessageBoxW
0x1801a5e3c  nop     dword ptr [rax+rax+00h]
0x1801a5e41  cmp     eax, 1
0x1801a5e44  jnz     loc_1801A6419
0x1801a5e4a  mov     edx, r12d
0x1801a5e4d  sub     ebx, 9401h
0x1801a5e53  jz      short loc_1801A5E91
0x1801a5e55  sub     ebx, esi
0x1801a5e57  jz      short loc_1801A5E87
0x1801a5e59  sub     ebx, esi
0x1801a5e5b  jz      short loc_1801A5E7D
0x1801a5e5d  sub     ebx, esi
0x1801a5e5f  jz      short loc_1801A5E73
0x1801a5e61  cmp     ebx, esi
0x1801a5e63  jnz     loc_1801A5A18
0x1801a5e69  mov     edx, 1000000h
0x1801a5e6e  jmp     loc_1801A5A18
0x1801a5e73  mov     edx, 800000h
0x1801a5e78  jmp     loc_1801A5A18
0x1801a5e7d  mov     edx, 200000h
  ... truncated ...
```
