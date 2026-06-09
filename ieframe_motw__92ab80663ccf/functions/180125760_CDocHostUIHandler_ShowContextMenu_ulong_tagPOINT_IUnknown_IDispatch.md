# CDocHostUIHandler::ShowContextMenu(ulong,tagPOINT *,IUnknown *,IDispatch *)

- ea: `0x180125760`
- end: `0x1801263ae`
- name: `?ShowContextMenu@CDocHostUIHandler@@UEAAJKPEAUtagPOINT@@PEAUIUnknown@@PEAUIDispatch@@@Z`
- size: `3150`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, unsigned int, struct tagPOINT *, struct IUnknown *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005030`
- `0x180012490`
- `0x1800144d0`
- `0x18001546c`
- `0x180015644`
- `0x1800166f0`
- `0x1800184f0`
- `0x18001d1a0`
- `0x180024b74`
- `0x18004d964`
- `0x180074e98`
- `0x180078534`
- `0x180092bb0`
- `0x18012307c`
- `0x1801231f4`
- `0x180123800`
- `0x180123d18`
- `0x180125760`
- `0x180127da4`
- `0x180127e40`
- `0x180127eb8`
- `0x180127f08`
- `0x180128598`
- `0x1801f1c8c`
- `0x180265170`
- `0x1803efcf8`
- `0x1803efed4`
- `0x1803effd0`
- `0x1803f02f8`
- `0x1803f1128`
- `0x180424e84`
- `0x18042b6ec`
- `0x18043bccc`
- `0x18043bd74`
- `0x18043df98`
- `0x18053d740`
- `0x180591ef6`
- `0x180591f56`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180125c6c`
- `KERNEL32!GlobalLock` at `0x180125c6c`
- `KERNEL32!GlobalUnlock` at `0x180125d5c`
- `KERNEL32!GlobalUnlock` at `0x180125d5c`
- `KERNEL32!GetCurrentThreadId` at `0x1801262dc`
- `KERNEL32!GetCurrentThreadId` at `0x1801262dc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180125d41`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180125d41`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x180125cfd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x180125cfd`
- `USER32!LoadMenuW` at `0x1801259a9`
- `USER32!LoadMenuW` at `0x1801259a9`
- `USER32!SetMenuItemInfoW` at `0x180125f08`
- `USER32!SetMenuItemInfoW` at `0x180125f08`
- `USER32!DeleteMenu` at `0x180125ad4`
- `USER32!DeleteMenu` at `0x180125aef`
- `USER32!DeleteMenu` at `0x180125b14`
- `USER32!DeleteMenu` at `0x180125b30`
- `USER32!DeleteMenu` at `0x180125b4c`
- `USER32!DeleteMenu` at `0x180125da0`
- `USER32!DeleteMenu` at `0x180125dbc`
- `USER32!DeleteMenu` at `0x180125ad4`
- `USER32!DeleteMenu` at `0x180125aef`
- `USER32!DeleteMenu` at `0x180125b14`
- `USER32!DeleteMenu` at `0x180125b30`
- `USER32!DeleteMenu` at `0x180125b4c`
- `USER32!DeleteMenu` at `0x180125da0`
- `USER32!DeleteMenu` at `0x180125dbc`
- `USER32!GetMenuItemID` at `0x180125df3`
- `USER32!GetMenuItemID` at `0x180125df3`
- `USER32!DestroyMenu` at `0x18012634d`
- `USER32!DestroyMenu` at `0x18012634d`
- `USER32!GetSystemMetrics` at `0x180126082`
- `USER32!GetSystemMetrics` at `0x180126082`
- `USER32!LoadCursorW` at `0x18012605f`
- `USER32!LoadCursorW` at `0x18012605f`
- `USER32!SetCursor` at `0x18012606e`
- `USER32!SetCursor` at `0x18012611a`
- `USER32!SetCursor` at `0x18012606e`
- `USER32!SetCursor` at `0x18012611a`
- `USER32!CheckMenuItem` at `0x180125e5d`
- `USER32!CheckMenuItem` at `0x180125e5d`
- `USER32!EnableMenuItem` at `0x180125e73`
- `USER32!EnableMenuItem` at `0x180125e73`
- `USER32!GetSubMenu` at `0x180125a95`
- `USER32!GetSubMenu` at `0x180125bcd`
- `USER32!GetSubMenu` at `0x180125a95`
- `USER32!GetSubMenu` at `0x180125bcd`
- `USER32!GetMenuItemCount` at `0x180125a73`
- `USER32!GetMenuItemCount` at `0x180125b62`
- `USER32!GetMenuItemCount` at `0x180125dcd`
- `USER32!GetMenuItemCount` at `0x180125e85`
- `USER32!GetMenuItemCount` at `0x180125a73`
- `USER32!GetMenuItemCount` at `0x180125b62`
- `USER32!GetMenuItemCount` at `0x180125dcd`
- `USER32!GetMenuItemCount` at `0x180125e85`
- `ole32!ReleaseStgMedium` at `0x180125d7a`
- `ole32!ReleaseStgMedium` at `0x180125d7a`
- `ole32!OleGetClipboard` at `0x180125bfe`
- `ole32!OleGetClipboard` at `0x180125bfe`
- `OLEAUT32!__imp_VariantClear` at `0x180126294`
- `OLEAUT32!__imp_VariantClear` at `0x180126294`
- `iertutil!CreateUri` at `0x180125cdf`
- `iertutil!CreateUri` at `0x180125cdf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125a0a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125a4f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125aad`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125a0a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125a4f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180125aad`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180126316`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180126316`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801262fb`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801262fb`

## pseudocode

```c
__int64 __fastcall CDocHostUIHandler::ShowContextMenu(
        CDocHostUIHandler *this,
        unsigned int a2,
        struct tagPOINT *a3,
        struct IUnknown *a4,
        struct IDispatch *a5)
{
  int v5; // r15d
  CDocHostUIHandler *v7; // r13
  int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // eax
  CDocHostUIHandler *v15; // rcx
  int v16; // edi
  bool v17; // r12
  int IsPopupWindow; // r14d
  int v19; // edi
  HMENU v20; // rbx
  unsigned int v21; // r13d
  int v22; // esi
  HMENU v23; // rbx
  CDocHostUIHandler *v24; // rcx
  int v25; // r12d
  HMENU SubMenu; // rbx
  char v27; // r14
  char v28; // si
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // rdi
  int UrlSchemeW; // eax
  int v32; // esi
  UINT v33; // edi
  struct IUnknown *v34; // rbx
  HCURSOR CursorW; // rax
  HCURSOR v36; // rdi
  int v37; // ebx
  int v38; // eax
  unsigned __int16 *v39; // r15
  unsigned int v40; // r9d
  unsigned int v41; // ebx
  VARIANTARG *v42; // rdi
  int v43; // ecx
  __int128 *v44; // r14
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // r9d
  DWORD CurrentThreadId; // eax
  unsigned int CurrentProcessManager; // eax
  unsigned int v53; // [rsp+40h] [rbp-C0h] BYREF
  HMENU hMenu; // [rsp+48h] [rbp-B8h] BYREF
  UINT uIDCheckItem[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v56; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A0h] BYREF
  int nPos[2]; // [rsp+68h] [rbp-98h] BYREF
  struct IOleInPlaceFrame *v59; // [rsp+70h] [rbp-90h] BYREF
  IUri *ppURI; // [rsp+78h] [rbp-88h] BYREF
  void *v61; // [rsp+80h] [rbp-80h] BYREF
  HWND v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  STGMEDIUM hMem; // [rsp+98h] [rbp-68h] BYREF
  CDocHostUIHandler *v65; // [rsp+B0h] [rbp-50h]
  __int128 v66; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h]
  __int128 v68; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-20h]
  __int16 v70; // [rsp+E8h] [rbp-18h] BYREF
  int v71; // [rsp+EAh] [rbp-16h]
  __int16 v72; // [rsp+EEh] [rbp-12h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  int v74; // [rsp+F8h] [rbp-8h]
  int v75; // [rsp+FCh] [rbp-4h]
  __int64 v76; // [rsp+100h] [rbp+0h]
  struct _GUID v77; // [rsp+110h] [rbp+10h] BYREF
  __int128 v78; // [rsp+120h] [rbp+20h] BYREF
  __int64 v79; // [rsp+130h] [rbp+30h]
  struct _GUID v80; // [rsp+138h] [rbp+38h] BYREF
  MENUITEMINFOW mii; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v82[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v83; // [rsp+230h] [rbp+130h]
  WCHAR pwzURI[72]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v85; // [rsp+2F0h] [rbp+1F0h]

  v5 = 0;
  *(_QWORD *)&v77.Data1 = a3;
  nPos[0] = a2;
  v7 = this;
  v65 = this;
  *(_QWORD *)&v80.Data1 = a4;
  v67 = 0;
  v79 = 0;
  v62 = 0;
  v57 = 0;
  v63 = 0;
  v66 = 0;
  v59 = 0;
  v78 = 0;
  v61 = 0;
  memset_0(&mii, 0, sizeof(mii));
  *(_QWORD *)uIDCheckItem = 0;
  hMenu = 0;
  if ( (int)CDocHostUIHandler::_GetBrowserFrame(v7, (struct IBrowserFrame **)&hMenu) >= 0 )
  {
    v56 = 0;
    if ( (*(int (__fastcall **)(HMENU, int *))(*(_QWORD *)hMenu + 48LL))(hMenu, &v56) >= 0 && v56 == 1 )
      (*(void (__fastcall **)(HMENU))(*(_QWORD *)hMenu + 168LL))(hMenu);
  }
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&hMenu);
  if ( (unsigned int)SHRestricted2W(1610612743, 0, 0) )
    return 0;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
          a4,
          &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
          &v57);
  if ( !v10 )
  {
    uIDCheckItem[0] = 2126;
    v56 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, UINT *, _QWORD))(*(_QWORD *)v57 + 24LL))(
            v57,
            &CGID_MSHTML,
            1,
            uIDCheckItem,
            0);
    v10 = v56;
    if ( !v56 )
    {
      v53 = 0;
      if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_Activities_NoActivities[0], &v53) >= 0 && !v53 )
      {
        v11 = *((_QWORD *)v7 + 6);
        hMenu = 0;
        if ( (unsigned int)InFullBrowser(v11) )
          IUnknown_QueryServiceForWebBrowserApp(*((_QWORD *)v7 + 6), &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e, &hMenu);
        v56 = CActivityCtxMenuUX::Initialize(
                (CDocHostUIHandler *)((char *)v7 + 88),
                a2,
                a5,
                (struct IWebBrowser2 *)hMenu);
        v10 = v56;
        if ( v56 < 0 )
        {
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&hMenu);
          goto LABEL_132;
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&hMenu);
      }
      if ( uIDCheckItem[1] == 7 )
      {
        v12 = 24641;
      }
      else
      {
        uIDCheckItem[0] = 2127;
        v56 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, UINT *, _QWORD))(*(_QWORD *)v57 + 24LL))(
                v57,
                &CGID_MSHTML,
                1,
                uIDCheckItem,
                0);
        v10 = v56;
        if ( v56 || uIDCheckItem[1] != 7 )
          goto LABEL_132;
        v12 = 24640;
      }
      hMenu = LoadMenuW(g_hinstMUI, (LPCWSTR)v12);
      if ( hMenu )
      {
        v53 = SHRestricted2W(1610612768, 0, 0);
        v13 = v53;
        v14 = SHRestricted2W(1610612748, 0, 0);
        v15 = (CDocHostUIHandler *)*((_QWORD *)v7 + 6);
        v16 = v14;
        LODWORD(ppURI) = v14;
        if ( v15 && (unsigned int)InFullBrowser(v15) )
          v5 = 1;
        v17 = CDocHostUIHandler::_HideOpenWithEdgeInContextMenu(v15);
        if ( IsDualEngineProcess() )
          IsPopupWindow = (unsigned __int8)DualEngine::IsPopupWindow();
        else
          IsPopupWindow = CDocHostUIHandler::_IsTabBrowsingEnabled(v7) == 0;
        if ( v13 || v16 )
        {
          v19 = 0;
        }
        else
        {
          v19 = 0;
          if ( !IsPopupWindow && v5 && !v17 && !IsDualEngineProcess() )
          {
            v20 = hMenu;
LABEL_54:
            v25 = nPos[0];
            if ( nPos[0] == 8 )
            {
              uIDCheckItem[0] = 6004;
              v10 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, UINT *, _QWORD))(*(_QWORD *)v57 + 24LL))(
                      v57,
                      &CGID_MSHTML,
                      1,
                      uIDCheckItem,
                      0);
              if ( uIDCheckItem[1] != 3 )
                goto LABEL_131;
            }
            SubMenu = GetSubMenu(v20, v25);
            if ( !SubMenu )
              goto LABEL_131;
            v27 = 1;
            if ( !v5 )
              goto LABEL_72;
            *(_QWORD *)nPos = 0;
            v28 = 0;
            if ( OleGetClipboard((LPDATAOBJECT *)nPos) >= 0 )
            {
              v73 = 0;
              v74 = 0;
              v70 = 13;
              v75 = -1;
              v71 = 0;
              v72 = 0;
              memset(&hMem, 0, sizeof(hMem));
              v76 = 1;
              if ( (*(int (__fastcall **)(_QWORD, __int16 *, STGMEDIUM *))(**(_QWORD **)nPos + 24LL))(
                     *(_QWORD *)nPos,
                     &v70,
                     &hMem) >= 0 )
              {
                v29 = (const unsigned __int16 *)GlobalLock(hMem.hBitmap);
                v30 = v29;
                if ( v29 )
                {
                  if ( (unsigned int)IEUrlFixupW(v29, pwzURI, 2084) )
                    StringCchCopyW(pwzURI, 0x824u, v30);
                  UrlSchemeW = GetUrlSchemeW(pwzURI);
                  ppURI = 0;
                  if ( (unsigned int)(UrlSchemeW - 1) > 0xFFFFFFFD || CreateUri(pwzURI, 0x3002B84u, 0, &ppURI) < 0 )
                  {
                    StrTrimW(pwzURI, asc_180619510);
                    if ( wcsncmp_0(pwzURI, L": ", 1u) )
                    {
                      if ( !IsPotentialURL(pwzURI, 0) || StrChrW(pwzURI, 0x20u) )
                      {
                        v27 = 0;
                        v28 = 1;
                      }
                    }
                  }
                  GlobalUnlock(hMem.hBitmap);
                  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppURI);
                }
                ReleaseStgMedium(&hMem);
              }
            }
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(nPos);
            if ( v28 )
LABEL_72:
              DeleteMenu(SubMenu, 0x8EDu, 0);
            if ( v27 )
              DeleteMenu(SubMenu, 0x8EEu, 0);
            v32 = 0;
            if ( GetMenuItemCount(SubMenu) > 0 )
            {
              while ( 1 )
              {
                uIDCheckItem[0] = GetMenuItemID(SubMenu, v32);
                if ( uIDCheckItem[0] )
                  break;
LABEL_83:
                if ( ++v32 >= GetMenuItemCount(SubMenu) )
                {
                  v7 = v65;
                  goto LABEL_85;
                }
              }
              (*(void (__fastcall **)(__int64, const GUID *, __int64, UINT *, _QWORD))(*(_QWORD *)v57 + 24LL))(
                v57,
                &CGID_MSHTML,
                1,
                uIDCheckItem,
                0);
              if ( uIDCheckItem[1] == 1 )
                goto LABEL_81;
              if ( uIDCheckItem[1] != 3 )
              {
                if ( uIDCheckItem[1] == 7 )
                {
                  v33 = 8;
                  goto LABEL_82;
                }
                if ( uIDCheckItem[1] != 11 )
                {
LABEL_81:
                  v33 = 3;
LABEL_82:
                  CheckMenuItem(SubMenu, uIDCheckItem[0], v33);
                  EnableMenuItem(SubMenu, uIDCheckItem[0], v33);
                  goto LABEL_83;
                }
              }
              v33 = 0;
              goto LABEL_82;
            }
LABEL_85:
            v69 = 0;
            v68 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v57 + 32LL))(
                    v57,
                    &CGID_ShellDocView,
                    27);
            if ( v10 )
              goto LABEL_131;
            mii.hSubMenu = (HMENU)*((_QWORD *)&v68 + 1);
            mii.cbSize = 80;
            mii.fMask = 4;
            SetMenuItemInfoW(SubMenu, 0x8F4u, 0, &mii);
            LOWORD(v66) = 37;
            *((_QWORD *)&v66 + 1) = SubMenu;
            LOWORD(v78) = 3;
            DWORD2(v78) = v25;
            v10 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v57 + 32LL))(
                    v57,
                    &CGID_ShellDocView,
                    53,
                    0,
                    &v66,
                    &v78);
            if ( v10 )
            {
LABEL_131:
              DestroyMenu(hMenu);
              goto LABEL_132;
            }
            COwnerDrawPopupMenu::COwnerDrawPopupMenu((COwnerDrawPopupMenu *)v82);
            COwnerDrawPopupMenu::COwnerDrawPopupMenu((COwnerDrawPopupMenu *)pwzURI);
            v10 = COwnerDrawPopupMenu::PopulateFromMenu((COwnerDrawPopupMenu *)v82, SubMenu);
            if ( v10 < 0 )
            {
LABEL_130:
              COwnerDrawPopupMenu::~COwnerDrawPopupMenu((COwnerDrawPopupMenu *)pwzURI);
              COwnerDrawPopupMenu::~COwnerDrawPopupMenu((COwnerDrawPopupMenu *)v82);
              goto LABEL_131;
            }
            v53 = 0;
            if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_Activities_NoActivities[0], &v53) >= 0 && !v53 )
              CActivityCtxMenuUX::AddActivitiesToMenu(
                (CDocHostUIHandler *)((char *)v7 + 88),
                (struct COwnerDrawPopupMenu *)v82,
                (struct COwnerDrawPopupMenu *)pwzURI);
            v34 = *(struct IUnknown **)&v80.Data1;
            if ( (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v80.Data1)(
                   *(_QWORD *)&v80.Data1,
                   &GUID_00000114_0000_0000_c000_000000000046,
                   &v63) >= 0 )
              (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v63 + 24LL))(v63, &v62);
            if ( !v62 )
              goto LABEL_129;
            GetInterfaceFromClientSite(v34, &GUID_bd3f23c0_d43e_11cf_893b_00aa00bdce1a, &v61);
            if ( v61 )
              (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v61 + 64LL))(v61, 0);
            GetInPlaceFrameFromUnknown(v34, &v59);
            if ( v59 )
              ((void (__fastcall *)(struct IOleInPlaceFrame *, _QWORD))v59->lpVtbl->EnableModeless)(v59, 0);
            CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
            v36 = SetCursor(CursorW);
            v37 = GetSystemMetrics(40) != 0 ? 266 : 258;
            v38 = IsBiDiLocalizedSystemEx();
            v39 = *(unsigned __int16 **)&v77.Data1;
            v40 = v37 | 0x8000;
            if ( !v38 )
              v40 = v37;
            v41 = CDocHostUIHandler::_TrackPopupMenuInternal(
                    v7,
                    v59,
                    (struct COwnerDrawPopupMenu *)v82,
                    v40,
                    **(_DWORD **)&v77.Data1 + 2,
                    *(_DWORD *)(*(_QWORD *)&v77.Data1 + 4LL) + 2,
                    v62);
            if ( v61 )
              (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v61 + 64LL))(v61, 1);
            if ( v59 )
              ((void (__fastcall *)(struct IOleInPlaceFrame *, __int64))v59->lpVtbl->EnableModeless)(v59, 1);
            SetCursor(v36);
            v42 = 0;
            if ( !v41 )
            {
LABEL_129:
              v83 = 0;
              v85 = 0;
              goto LABEL_130;
            }
            if ( v41 == 2289 )
            {
              LOBYTE(hMem.pUnkForRelease) = 0;
              v77 = *CreateUserInputId(&v80);
              ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)&hMem, &v77);
              BrowserTelemetry::IEPrintCommandInvoked();
              HIDWORD(hMem.pUnkForRelease) = 3;
              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&hMem);
            }
            else if ( v41 - 2285 <= 1 )
            {
              v53 = 0;
              CurrentThreadId = GetCurrentThreadId();
              if ( (int)GetFrameComponentFromBrowserTabThread(CurrentThreadId, &v53, 0) >= 0 )
              {
                CurrentProcessManager = IsoGetCurrentProcessManager();
                LCIEPostMessageWithoutBuffer(v53, CurrentProcessManager, 0xCD2u, 0);
              }
              goto LABEL_129;
            }
            if ( (unsigned int)CActivityCtxMenuUX::s_IsActivityMenuItemId(v41) )
            {
              CActivityCtxMenuUX::MenuItemExecute((CDocHostUIHandler *)((char *)v7 + 88), v41);
              goto LABEL_129;
            }
            v44 = 0;
            v45 = v43 - 28;
            if ( v45 )
            {
              v46 = v45 - 2108;
              if ( v46 )
              {
                v47 = v46 - 1;
                if ( v47 )
                {
                  v48 = v47 - 2;
                  if ( v48 && v48 != 1765 )
                  {
LABEL_118:
                    (*(void (__fastcall **)(__int64, const GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 32LL))(
                      v57,
                      &CGID_MSHTML,
                      2432,
                      0,
                      0,
                      0);
                    (*(void (__fastcall **)(__int64, const GUID *, _QWORD, _QWORD, __int128 *, VARIANTARG *))(*(_QWORD *)v57 + 32LL))(
                      v57,
                      &CGID_MSHTML,
                      v41,
                      0,
                      v44,
                      v42);
                    if ( v41 == 3904 )
                    {
                      if ( !v42->vt )
                      {
LABEL_125:
                        (*(void (__fastcall **)(__int64, const GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 32LL))(
                          v57,
                          &CGID_MSHTML,
                          2433,
                          0,
                          0,
                          0);
                        goto LABEL_129;
                      }
                      v50 = 0;
                    }
                    else
                    {
                      if ( v41 != 2139 || !v42->vt )
                        goto LABEL_125;
                      v50 = 1;
                    }
                    IUnknown_Exec(*((_QWORD *)v7 + 6), (unsigned int)&CGID_Explorer, 97, v50, (__int64)v42, 0);
                    VariantClear(v42);
                    goto LABEL_125;
                  }
                  v42 = (VARIANTARG *)&v66;
                  v66 = 0;
                  v67 = 0;
                }
              }
            }
            v44 = &v68;
            v49 = *v39 | (v39[2] << 16);
            LOWORD(v68) = 3;
            DWORD2(v68) = v49;
            goto LABEL_118;
          }
        }
        v20 = hMenu;
        if ( GetMenuItemCount(hMenu) > 0 )
        {
          v21 = v53;
          v22 = (int)ppURI;
          do
          {
            v23 = GetSubMenu(v20, v19);
            if ( v23 )
            {
              if ( IsDualEngineProcess() )
                CDocHostUIHandler::_DisableDualEngineContextMenu(v24, v23);
              if ( v21 )
                DeleteMenu(v23, 0x1Bu, 0);
              if ( v22 )
                DeleteMenu(v23, 0x85Bu, 0);
              if ( IsPopupWindow && (unsigned int)IsInternetExplorerApp() )
                DeleteMenu(v23, 0x983u, 0);
              if ( !v5 )
                DeleteMenu(v23, 0xF40u, 0);
              if ( v17 )
                DeleteMenu(v23, 0xF47u, 0);
            }
            v20 = hMenu;
            ++v19;
          }
          while ( v19 < GetMenuItemCount(hMenu) );
          v10 = v56;
          v7 = v65;
        }
        goto LABEL_54;
      }
    }
  }
LABEL_132:
  CActivityCtxMenuUX::Cleanup((CDocHostUIHandler *)((char *)v7 + 88));
  IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&v57);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v63);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v59);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v61);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180125760  push    rbp
0x180125762  push    rbx
0x180125763  push    rsi
0x180125764  push    rdi
0x180125765  push    r12
0x180125767  push    r13
0x180125769  push    r14
0x18012576b  push    r15
0x18012576d  lea     rbp, [rsp-11C8h]
0x180125775  mov     eax, 12C8h
0x18012577a  call    _alloca_probe
0x18012577f  sub     rsp, rax
0x180125782  mov     rax, cs:__security_cookie
0x180125789  xor     rax, rsp
0x18012578c  mov     [rbp+1200h+var_50], rax
0x180125793  mov     rbx, [rbp+1200h+arg_20]
0x18012579a  xor     r15d, r15d
0x18012579d  xor     eax, eax
0x18012579f  mov     qword ptr [rbp+1200h+var_11F0.Data1], r8
0x1801257a3  mov     r14d, edx
0x1801257a6  mov     [rsp+1300h+nPos], edx
0x1801257aa  mov     r13, rcx
0x1801257ad  mov     [rbp+1200h+var_1250], rcx
0x1801257b1  xorps   xmm0, xmm0
0x1801257b4  mov     qword ptr [rbp+1200h+var_11C8.Data1], r9
0x1801257b8  xorps   xmm1, xmm1
0x1801257bb  mov     [rbp+1200h+var_1238], rax
0x1801257bf  lea     r8d, [rax+50h]; Size
0x1801257c3  mov     [rbp+1200h+var_11D0], rax
0x1801257c7  xor     edx, edx; Val
0x1801257c9  mov     [rbp+1200h+var_1278], r15
0x1801257cd  lea     rcx, [rbp+1200h+mii]; void *
0x1801257d1  mov     [rsp+1300h+var_12A0], r15
0x1801257d6  mov     rdi, r9
0x1801257d9  mov     [rbp+1200h+var_1270], r15
0x1801257dd  movups  [rbp+1200h+var_1248], xmm0
0x1801257e1  mov     [rsp+1300h+var_1290], r15
0x1801257e6  movups  [rbp+1200h+var_11E0], xmm1
0x1801257ea  mov     [rbp+1200h+var_1280], r15
0x1801257ee  call    memset_0
0x1801257f3  lea     rdx, [rsp+1300h+hMenu]; struct IBrowserFrame **
0x1801257f8  mov     qword ptr [rsp+1300h+uIDCheckItem], r15
0x1801257fd  mov     rcx, r13; this
0x180125800  mov     [rsp+1300h+hMenu], r15
0x180125805  call    ?_GetBrowserFrame@CDocHostUIHandler@@AEAAJPEAPEAUIBrowserFrame@@@Z; CDocHostUIHandler::_GetBrowserFrame(IBrowserFrame * *)
0x18012580a  lea     r12d, [r15+1]
0x18012580e  test    eax, eax
0x180125810  js      short loc_18012584C
0x180125812  mov     rcx, [rsp+1300h+hMenu]
0x180125817  lea     rdx, [rsp+1300h+var_12A8]
0x18012581c  mov     [rsp+1300h+var_12A8], r15d
0x180125821  mov     rax, [rcx]
0x180125824  mov     rax, [rax+30h]
0x180125828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012582d  test    eax, eax
0x18012582f  js      short loc_18012584C
0x180125831  cmp     [rsp+1300h+var_12A8], r12d
0x180125836  jnz     short loc_18012584C
0x180125838  mov     rcx, [rsp+1300h+hMenu]
0x18012583d  mov     rax, [rcx]
0x180125840  mov     rax, [rax+0A8h]
0x180125847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012584c  lea     rcx, [rsp+1300h+hMenu]; void *
0x180125851  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180125856  xor     r8d, r8d
0x180125859  xor     edx, edx
0x18012585b  mov     ecx, 60000007h
0x180125860  call    SHRestricted2W
0x180125865  test    eax, eax
0x180125867  jz      short loc_180125870
0x180125869  xor     eax, eax
0x18012586b  jmp     loc_18012638A
0x180125870  mov     rax, [rdi]
0x180125873  lea     r8, [rsp+1300h+var_12A0]
0x180125878  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x18012587f  mov     rcx, rdi
0x180125882  mov     rax, [rax]
0x180125885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012588a  mov     esi, eax
0x18012588c  test    eax, eax
0x18012588e  jnz     loc_180126359
0x180125894  mov     rcx, [rsp+1300h+var_12A0]
0x180125899  lea     r9, [rsp+1300h+uIDCheckItem]
0x18012589e  mov     [rsp+1300h+uIDCheckItem], 84Eh
0x1801258a6  lea     rdx, CGID_MSHTML
0x1801258ad  mov     r8d, r12d
0x1801258b0  mov     qword ptr [rsp+1300h+var_12E0], r15
0x1801258b5  mov     rax, [rcx]
0x1801258b8  mov     rax, [rax+18h]
0x1801258bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801258c1  mov     [rsp+1300h+var_12A8], eax
0x1801258c5  mov     esi, eax
0x1801258c7  test    eax, eax
0x1801258c9  jnz     loc_180126359
0x1801258cf  mov     rcx, cs:?IEVALUE_Activities_NoActivities@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Activities_NoActivities
0x1801258d6  lea     rdx, [rsp+1300h+var_12C0]
0x1801258db  mov     [rsp+1300h+var_12C0], r15d
0x1801258e0  call    GetBOOL
0x1801258e5  test    eax, eax
0x1801258e7  js      short loc_180125949
0x1801258e9  cmp     [rsp+1300h+var_12C0], r15d
0x1801258ee  jnz     short loc_180125949
0x1801258f0  mov     rcx, [r13+30h]
0x1801258f4  mov     [rsp+1300h+hMenu], r15
0x1801258f9  call    InFullBrowser
0x1801258fe  test    eax, eax
0x180125900  jz      short loc_180125917
0x180125902  mov     rcx, [r13+30h]
0x180125906  lea     r8, [rsp+1300h+hMenu]
0x18012590b  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x180125912  call    IUnknown_QueryServiceForWebBrowserApp
0x180125917  mov     r9, [rsp+1300h+hMenu]; struct IWebBrowser2 *
0x18012591c  lea     rcx, [r13+58h]; this
0x180125920  mov     r8, rbx; struct IDispatch *
0x180125923  mov     edx, r14d; unsigned int
0x180125926  call    ?Initialize@CActivityCtxMenuUX@@QEAAJKPEAUIDispatch@@PEAUIWebBrowser2@@@Z; CActivityCtxMenuUX::Initialize(ulong,IDispatch *,IWebBrowser2 *)
0x18012592b  mov     [rsp+1300h+var_12A8], eax
0x18012592f  mov     esi, eax
0x180125931  lea     rcx, [rsp+1300h+hMenu]; void *
0x180125936  test    eax, eax
0x180125938  jns     short loc_180125944
0x18012593a  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18012593f  jmp     loc_180126359
0x180125944  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180125949  cmp     [rsp+1300h+uIDCheckItem+4], 7
0x18012594e  jnz     short loc_180125957
0x180125950  mov     edx, 6041h
0x180125955  jmp     short loc_1801259A2
0x180125957  mov     rcx, [rsp+1300h+var_12A0]
0x18012595c  lea     r9, [rsp+1300h+uIDCheckItem]
0x180125961  mov     [rsp+1300h+uIDCheckItem], 84Fh
0x180125969  lea     rdx, CGID_MSHTML
0x180125970  mov     r8d, r12d
0x180125973  mov     qword ptr [rsp+1300h+var_12E0], r15
0x180125978  mov     rax, [rcx]
0x18012597b  mov     rax, [rax+18h]
0x18012597f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125984  mov     [rsp+1300h+var_12A8], eax
0x180125988  mov     esi, eax
0x18012598a  test    eax, eax
0x18012598c  jnz     loc_180126359
0x180125992  cmp     [rsp+1300h+uIDCheckItem+4], 7
0x180125997  jnz     loc_180126359
0x18012599d  mov     edx, 6040h; lpMenuName
0x1801259a2  mov     rcx, cs:g_hinstMUI; hInstance
0x1801259a9  call    cs:__imp_LoadMenuW
0x1801259b0  nop     dword ptr [rax+rax+00h]
0x1801259b5  mov     [rsp+1300h+hMenu], rax
0x1801259ba  test    rax, rax
0x1801259bd  jz      loc_180126359
0x1801259c3  xor     r8d, r8d
0x1801259c6  xor     edx, edx
0x1801259c8  mov     ecx, 60000020h
0x1801259cd  call    SHRestricted2W
0x1801259d2  xor     r8d, r8d
0x1801259d5  mov     [rsp+1300h+var_12C0], eax
0x1801259d9  xor     edx, edx
0x1801259db  mov     ecx, 6000000Ch
0x1801259e0  mov     ebx, eax
0x1801259e2  call    SHRestricted2W
0x1801259e7  mov     rcx, [r13+30h]
0x1801259eb  mov     edi, eax
0x1801259ed  mov     dword ptr [rsp+1300h+ppURI], eax
0x1801259f1  test    rcx, rcx
0x1801259f4  jz      short loc_180125A02
0x1801259f6  call    InFullBrowser
0x1801259fb  test    eax, eax
0x1801259fd  jz      short loc_180125A02
0x1801259ff  mov     r15d, r12d
0x180125a02  call    ?_HideOpenWithEdgeInContextMenu@CDocHostUIHandler@@AEAA_NXZ; CDocHostUIHandler::_HideOpenWithEdgeInContextMenu(void)
0x180125a07  mov     r12b, al
0x180125a0a  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180125a11  nop     dword ptr [rax+rax+00h]
0x180125a16  test    al, al
0x180125a18  jz      short loc_180125A25
0x180125a1a  call    DualEngine__IsPopupWindow
0x180125a1f  movzx   r14d, al
0x180125a23  jmp     short loc_180125A36
0x180125a25  mov     rcx, r13; this
0x180125a28  call    ?_IsTabBrowsingEnabled@CDocHostUIHandler@@AEAAHXZ; CDocHostUIHandler::_IsTabBrowsingEnabled(void)
0x180125a2d  xor     r14d, r14d
0x180125a30  test    eax, eax
0x180125a32  setz    r14b
0x180125a36  test    ebx, ebx
0x180125a38  jnz     short loc_180125A69
0x180125a3a  test    edi, edi
0x180125a3c  jnz     short loc_180125A69
0x180125a3e  xor     edi, edi
0x180125a40  test    r14d, r14d
0x180125a43  jnz     short loc_180125A6B
0x180125a45  test    r15d, r15d
0x180125a48  jz      short loc_180125A6B
0x180125a4a  test    r12b, r12b
0x180125a4d  jnz     short loc_180125A6B
0x180125a4f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180125a56  nop     dword ptr [rax+rax+00h]
0x180125a5b  test    al, al
0x180125a5d  jnz     short loc_180125A6B
0x180125a5f  mov     rbx, [rsp+1300h+hMenu]
0x180125a64  jmp     loc_180125B80
0x180125a69  xor     edi, edi
0x180125a6b  mov     rbx, [rsp+1300h+hMenu]
0x180125a70  mov     rcx, rbx; hMenu
0x180125a73  call    cs:__imp_GetMenuItemCount
0x180125a7a  nop     dword ptr [rax+rax+00h]
0x180125a7f  test    eax, eax
0x180125a81  jle     loc_180125B7E
0x180125a87  mov     r13d, [rsp+1300h+var_12C0]
0x180125a8c  mov     esi, dword ptr [rsp+1300h+ppURI]
0x180125a90  mov     edx, edi; nPos
0x180125a92  mov     rcx, rbx; hMenu
0x180125a95  call    cs:__imp_GetSubMenu
0x180125a9c  nop     dword ptr [rax+rax+00h]
0x180125aa1  mov     rbx, rax
0x180125aa4  test    rax, rax
0x180125aa7  jz      loc_180125B58
0x180125aad  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180125ab4  nop     dword ptr [rax+rax+00h]
0x180125ab9  test    al, al
0x180125abb  jz      short loc_180125AC5
0x180125abd  mov     rdx, rbx; HMENU
0x180125ac0  call    ?_DisableDualEngineContextMenu@CDocHostUIHandler@@AEAAXPEAUHMENU__@@@Z; CDocHostUIHandler::_DisableDualEngineContextMenu(HMENU__ *)
0x180125ac5  test    r13d, r13d
0x180125ac8  jz      short loc_180125AE0
0x180125aca  xor     r8d, r8d; uFlags
0x180125acd  mov     rcx, rbx; hMenu
0x180125ad0  lea     edx, [r8+1Bh]; uPosition
0x180125ad4  call    cs:__imp_DeleteMenu
0x180125adb  nop     dword ptr [rax+rax+00h]
0x180125ae0  test    esi, esi
0x180125ae2  jz      short loc_180125AFB
0x180125ae4  xor     r8d, r8d; uFlags
0x180125ae7  mov     edx, 85Bh; uPosition
0x180125aec  mov     rcx, rbx; hMenu
0x180125aef  call    cs:__imp_DeleteMenu
0x180125af6  nop     dword ptr [rax+rax+00h]
0x180125afb  test    r14d, r14d
0x180125afe  jz      short loc_180125B20
0x180125b00  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180125b05  test    eax, eax
0x180125b07  jz      short loc_180125B20
0x180125b09  xor     r8d, r8d; uFlags
0x180125b0c  mov     edx, 983h; uPosition
0x180125b11  mov     rcx, rbx; hMenu
0x180125b14  call    cs:__imp_DeleteMenu
0x180125b1b  nop     dword ptr [rax+rax+00h]
0x180125b20  test    r15d, r15d
0x180125b23  jnz     short loc_180125B3C
0x180125b25  xor     r8d, r8d; uFlags
0x180125b28  mov     edx, 0F40h; uPosition
0x180125b2d  mov     rcx, rbx; hMenu
0x180125b30  call    cs:__imp_DeleteMenu
0x180125b37  nop     dword ptr [rax+rax+00h]
0x180125b3c  test    r12b, r12b
0x180125b3f  jz      short loc_180125B58
0x180125b41  xor     r8d, r8d; uFlags
0x180125b44  mov     edx, 0F47h; uPosition
0x180125b49  mov     rcx, rbx; hMenu
0x180125b4c  call    cs:__imp_DeleteMenu
0x180125b53  nop     dword ptr [rax+rax+00h]
0x180125b58  mov     rbx, [rsp+1300h+hMenu]
0x180125b5d  inc     edi
0x180125b5f  mov     rcx, rbx; hMenu
0x180125b62  call    cs:__imp_GetMenuItemCount
0x180125b69  nop     dword ptr [rax+rax+00h]
0x180125b6e  cmp     edi, eax
0x180125b70  jl      loc_180125A90
0x180125b76  mov     esi, [rsp+1300h+var_12A8]
0x180125b7a  mov     r13, [rbp+1200h+var_1250]
0x180125b7e  xor     edi, edi
0x180125b80  mov     r12d, [rsp+1300h+nPos]
0x180125b85  cmp     r12d, 8
0x180125b89  jnz     short loc_180125BC7
0x180125b8b  mov     rcx, [rsp+1300h+var_12A0]
0x180125b90  lea     r9, [rsp+1300h+uIDCheckItem]
0x180125b95  mov     [rsp+1300h+uIDCheckItem], 1774h
0x180125b9d  lea     r8d, [r12-7]
0x180125ba2  lea     rdx, CGID_MSHTML
0x180125ba9  mov     qword ptr [rsp+1300h+var_12E0], rdi
0x180125bae  mov     rax, [rcx]
0x180125bb1  mov     rax, [rax+18h]
0x180125bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125bba  cmp     [rsp+1300h+uIDCheckItem+4], 3
0x180125bbf  mov     esi, eax
0x180125bc1  jnz     loc_180126348
0x180125bc7  mov     edx, r12d; nPos
0x180125bca  mov     rcx, rbx; hMenu
0x180125bcd  call    cs:__imp_GetSubMenu
0x180125bd4  nop     dword ptr [rax+rax+00h]
0x180125bd9  mov     rbx, rax
0x180125bdc  test    rax, rax
0x180125bdf  jz      loc_180126348
0x180125be5  mov     r14b, 1
0x180125be8  test    r15d, r15d
0x180125beb  jz      loc_180125D95
0x180125bf1  lea     rcx, [rsp+1300h+nPos]; ppDataObj
0x180125bf6  mov     qword ptr [rsp+1300h+nPos], rdi
0x180125bfb  mov     sil, dil
0x180125bfe  call    cs:__imp_OleGetClipboard
0x180125c05  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
