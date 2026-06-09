# CDocHostUIHandler::ShowContextMenu(ulong,tagPOINT *,IUnknown *,IDispatch *)

- ea: `0x180118b70`
- end: `0x1801196df`
- name: `?ShowContextMenu@CDocHostUIHandler@@UEAAJKPEAUtagPOINT@@PEAUIUnknown@@PEAUIDispatch@@@Z`
- size: `2927`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, unsigned int, struct tagPOINT *, struct IUnknown *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000f470`
- `0x180011230`
- `0x180012140`
- `0x180012310`
- `0x180013570`
- `0x180015150`
- `0x18001ba58`
- `0x1800231c4`
- `0x18004a080`
- `0x18006f940`
- `0x180073354`
- `0x18008c170`
- `0x1801167b0`
- `0x180116924`
- `0x180116f00`
- `0x1801173d4`
- `0x180118b70`
- `0x18011af48`
- `0x18011afcc`
- `0x18011b03c`
- `0x18011b088`
- `0x18011b788`
- `0x1801d92a4`
- `0x180246ce4`
- `0x1803bd1b8`
- `0x1803bd37c`
- `0x1803bd464`
- `0x1803bd77c`
- `0x1803be59c`
- `0x1803ef2e0`
- `0x1803f52c0`
- `0x1804046e8`
- `0x180404790`
- `0x1804067f4`
- `0x1804fd8d4`
- `0x18054e286`
- `0x18054e2e6`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180119028`
- `KERNEL32!GlobalLock` at `0x180119028`
- `KERNEL32!GlobalUnlock` at `0x180119100`
- `KERNEL32!GlobalUnlock` at `0x180119100`
- `KERNEL32!GetCurrentThreadId` at `0x180119626`
- `KERNEL32!GetCurrentThreadId` at `0x180119626`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1801190eb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1801190eb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801190ad`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801190ad`
- `USER32!LoadMenuW` at `0x180118db9`
- `USER32!LoadMenuW` at `0x180118db9`
- `USER32!SetMenuItemInfoW` at `0x180119276`
- `USER32!SetMenuItemInfoW` at `0x180119276`
- `USER32!DeleteMenu` at `0x180118ec0`
- `USER32!DeleteMenu` at `0x180118ed5`
- `USER32!DeleteMenu` at `0x180118ef4`
- `USER32!DeleteMenu` at `0x180118f0a`
- `USER32!DeleteMenu` at `0x180118f20`
- `USER32!DeleteMenu` at `0x180119138`
- `USER32!DeleteMenu` at `0x18011914e`
- `USER32!DeleteMenu` at `0x180118ec0`
- `USER32!DeleteMenu` at `0x180118ed5`
- `USER32!DeleteMenu` at `0x180118ef4`
- `USER32!DeleteMenu` at `0x180118f0a`
- `USER32!DeleteMenu` at `0x180118f20`
- `USER32!DeleteMenu` at `0x180119138`
- `USER32!DeleteMenu` at `0x18011914e`
- `USER32!GetMenuItemID` at `0x180119179`
- `USER32!GetMenuItemID` at `0x180119179`
- `USER32!DestroyMenu` at `0x180119685`
- `USER32!DestroyMenu` at `0x180119685`
- `USER32!GetSystemMetrics` at `0x1801193de`
- `USER32!GetSystemMetrics` at `0x1801193de`
- `USER32!LoadCursorW` at `0x1801193c7`
- `USER32!LoadCursorW` at `0x1801193c7`
- `USER32!SetCursor` at `0x1801193d0`
- `USER32!SetCursor` at `0x180119470`
- `USER32!SetCursor` at `0x1801193d0`
- `USER32!SetCursor` at `0x180119470`
- `USER32!CheckMenuItem` at `0x1801191dd`
- `USER32!CheckMenuItem` at `0x1801191dd`
- `USER32!EnableMenuItem` at `0x1801191ed`
- `USER32!EnableMenuItem` at `0x1801191ed`
- `USER32!GetSubMenu` at `0x180118e8d`
- `USER32!GetSubMenu` at `0x180118f95`
- `USER32!GetSubMenu` at `0x180118e8d`
- `USER32!GetSubMenu` at `0x180118f95`
- `USER32!GetMenuItemCount` at `0x180118e71`
- `USER32!GetMenuItemCount` at `0x180118f30`
- `USER32!GetMenuItemCount` at `0x180119159`
- `USER32!GetMenuItemCount` at `0x1801191f9`
- `USER32!GetMenuItemCount` at `0x180118e71`
- `USER32!GetMenuItemCount` at `0x180118f30`
- `USER32!GetMenuItemCount` at `0x180119159`
- `USER32!GetMenuItemCount` at `0x1801191f9`
- `ole32!ReleaseStgMedium` at `0x180119118`
- `ole32!ReleaseStgMedium` at `0x180119118`
- `ole32!OleGetClipboard` at `0x180118fc0`
- `ole32!OleGetClipboard` at `0x180118fc0`
- `OLEAUT32!__imp_VariantClear` at `0x1801195e4`
- `OLEAUT32!__imp_VariantClear` at `0x1801195e4`
- `iertutil!CreateUri` at `0x180119095`
- `iertutil!CreateUri` at `0x180119095`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e14`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e53`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e9f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e14`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e53`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180118e9f`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180119654`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180119654`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18011963f`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18011963f`

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
                    StrTrimW(pwzURI, asc_1805D56C0);
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
0x180118b70  push    rbp
0x180118b72  push    rbx
0x180118b73  push    rsi
0x180118b74  push    rdi
0x180118b75  push    r12
0x180118b77  push    r13
0x180118b79  push    r14
0x180118b7b  push    r15
0x180118b7d  lea     rbp, [rsp-11C8h]
0x180118b85  mov     eax, 12C8h
0x180118b8a  call    _alloca_probe
0x180118b8f  sub     rsp, rax
0x180118b92  mov     rax, cs:__security_cookie
0x180118b99  xor     rax, rsp
0x180118b9c  mov     [rbp+1200h+var_50], rax
0x180118ba3  mov     rbx, [rbp+1200h+arg_20]
0x180118baa  xor     r15d, r15d
0x180118bad  xor     eax, eax
0x180118baf  mov     qword ptr [rbp+1200h+var_11F0.Data1], r8
0x180118bb3  mov     r14d, edx
0x180118bb6  mov     [rsp+1300h+nPos], edx
0x180118bba  mov     r13, rcx
0x180118bbd  mov     [rbp+1200h+var_1250], rcx
0x180118bc1  xorps   xmm0, xmm0
0x180118bc4  mov     qword ptr [rbp+1200h+var_11C8.Data1], r9
0x180118bc8  xorps   xmm1, xmm1
0x180118bcb  mov     [rbp+1200h+var_1238], rax
0x180118bcf  lea     r8d, [rax+50h]; Size
0x180118bd3  mov     [rbp+1200h+var_11D0], rax
0x180118bd7  xor     edx, edx; Val
0x180118bd9  mov     [rbp+1200h+var_1278], r15
0x180118bdd  lea     rcx, [rbp+1200h+mii]; void *
0x180118be1  mov     [rsp+1300h+var_12A0], r15
0x180118be6  mov     rdi, r9
0x180118be9  mov     [rbp+1200h+var_1270], r15
0x180118bed  movups  [rbp+1200h+var_1248], xmm0
0x180118bf1  mov     [rsp+1300h+var_1290], r15
0x180118bf6  movups  [rbp+1200h+var_11E0], xmm1
0x180118bfa  mov     [rbp+1200h+var_1280], r15
0x180118bfe  call    memset_0
0x180118c03  lea     rdx, [rsp+1300h+hMenu]; struct IBrowserFrame **
0x180118c08  mov     qword ptr [rsp+1300h+uIDCheckItem], r15
0x180118c0d  mov     rcx, r13; this
0x180118c10  mov     [rsp+1300h+hMenu], r15
0x180118c15  call    ?_GetBrowserFrame@CDocHostUIHandler@@AEAAJPEAPEAUIBrowserFrame@@@Z; CDocHostUIHandler::_GetBrowserFrame(IBrowserFrame * *)
0x180118c1a  lea     r12d, [r15+1]
0x180118c1e  test    eax, eax
0x180118c20  js      short loc_180118C5C
0x180118c22  mov     rcx, [rsp+1300h+hMenu]
0x180118c27  lea     rdx, [rsp+1300h+var_12A8]
0x180118c2c  mov     [rsp+1300h+var_12A8], r15d
0x180118c31  mov     rax, [rcx]
0x180118c34  mov     rax, [rax+30h]
0x180118c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118c3d  test    eax, eax
0x180118c3f  js      short loc_180118C5C
0x180118c41  cmp     [rsp+1300h+var_12A8], r12d
0x180118c46  jnz     short loc_180118C5C
0x180118c48  mov     rcx, [rsp+1300h+hMenu]
0x180118c4d  mov     rax, [rcx]
0x180118c50  mov     rax, [rax+0A8h]
0x180118c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118c5c  lea     rcx, [rsp+1300h+hMenu]; void *
0x180118c61  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180118c66  xor     r8d, r8d
0x180118c69  xor     edx, edx
0x180118c6b  mov     ecx, 60000007h
0x180118c70  call    SHRestricted2W
0x180118c75  test    eax, eax
0x180118c77  jz      short loc_180118C80
0x180118c79  xor     eax, eax
0x180118c7b  jmp     loc_1801196BC
0x180118c80  mov     rax, [rdi]
0x180118c83  lea     r8, [rsp+1300h+var_12A0]
0x180118c88  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x180118c8f  mov     rcx, rdi
0x180118c92  mov     rax, [rax]
0x180118c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118c9a  mov     esi, eax
0x180118c9c  test    eax, eax
0x180118c9e  jnz     loc_18011968B
0x180118ca4  mov     rcx, [rsp+1300h+var_12A0]
0x180118ca9  lea     r9, [rsp+1300h+uIDCheckItem]
0x180118cae  mov     [rsp+1300h+uIDCheckItem], 84Eh
0x180118cb6  lea     rdx, CGID_MSHTML
0x180118cbd  mov     r8d, r12d
0x180118cc0  mov     qword ptr [rsp+1300h+var_12E0], r15
0x180118cc5  mov     rax, [rcx]
0x180118cc8  mov     rax, [rax+18h]
0x180118ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118cd1  mov     [rsp+1300h+var_12A8], eax
0x180118cd5  mov     esi, eax
0x180118cd7  test    eax, eax
0x180118cd9  jnz     loc_18011968B
0x180118cdf  mov     rcx, cs:?IEVALUE_Activities_NoActivities@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Activities_NoActivities
0x180118ce6  lea     rdx, [rsp+1300h+var_12C0]
0x180118ceb  mov     [rsp+1300h+var_12C0], r15d
0x180118cf0  call    GetBOOL
0x180118cf5  test    eax, eax
0x180118cf7  js      short loc_180118D59
0x180118cf9  cmp     [rsp+1300h+var_12C0], r15d
0x180118cfe  jnz     short loc_180118D59
0x180118d00  mov     rcx, [r13+30h]
0x180118d04  mov     [rsp+1300h+hMenu], r15
0x180118d09  call    InFullBrowser
0x180118d0e  test    eax, eax
0x180118d10  jz      short loc_180118D27
0x180118d12  mov     rcx, [r13+30h]
0x180118d16  lea     r8, [rsp+1300h+hMenu]
0x180118d1b  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x180118d22  call    IUnknown_QueryServiceForWebBrowserApp
0x180118d27  mov     r9, [rsp+1300h+hMenu]; struct IWebBrowser2 *
0x180118d2c  lea     rcx, [r13+58h]; this
0x180118d30  mov     r8, rbx; struct IDispatch *
0x180118d33  mov     edx, r14d; unsigned int
0x180118d36  call    ?Initialize@CActivityCtxMenuUX@@QEAAJKPEAUIDispatch@@PEAUIWebBrowser2@@@Z; CActivityCtxMenuUX::Initialize(ulong,IDispatch *,IWebBrowser2 *)
0x180118d3b  mov     [rsp+1300h+var_12A8], eax
0x180118d3f  mov     esi, eax
0x180118d41  lea     rcx, [rsp+1300h+hMenu]; void *
0x180118d46  test    eax, eax
0x180118d48  jns     short loc_180118D54
0x180118d4a  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180118d4f  jmp     loc_18011968B
0x180118d54  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180118d59  cmp     [rsp+1300h+uIDCheckItem+4], 7
0x180118d5e  jnz     short loc_180118D67
0x180118d60  mov     edx, 6041h
0x180118d65  jmp     short loc_180118DB2
0x180118d67  mov     rcx, [rsp+1300h+var_12A0]
0x180118d6c  lea     r9, [rsp+1300h+uIDCheckItem]
0x180118d71  mov     [rsp+1300h+uIDCheckItem], 84Fh
0x180118d79  lea     rdx, CGID_MSHTML
0x180118d80  mov     r8d, r12d
0x180118d83  mov     qword ptr [rsp+1300h+var_12E0], r15
0x180118d88  mov     rax, [rcx]
0x180118d8b  mov     rax, [rax+18h]
0x180118d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118d94  mov     [rsp+1300h+var_12A8], eax
0x180118d98  mov     esi, eax
0x180118d9a  test    eax, eax
0x180118d9c  jnz     loc_18011968B
0x180118da2  cmp     [rsp+1300h+uIDCheckItem+4], 7
0x180118da7  jnz     loc_18011968B
0x180118dad  mov     edx, 6040h; lpMenuName
0x180118db2  mov     rcx, cs:g_hinstMUI; hInstance
0x180118db9  call    cs:__imp_LoadMenuW
0x180118dbf  mov     [rsp+1300h+hMenu], rax
0x180118dc4  test    rax, rax
0x180118dc7  jz      loc_18011968B
0x180118dcd  xor     r8d, r8d
0x180118dd0  xor     edx, edx
0x180118dd2  mov     ecx, 60000020h
0x180118dd7  call    SHRestricted2W
0x180118ddc  xor     r8d, r8d
0x180118ddf  mov     [rsp+1300h+var_12C0], eax
0x180118de3  xor     edx, edx
0x180118de5  mov     ecx, 6000000Ch
0x180118dea  mov     ebx, eax
0x180118dec  call    SHRestricted2W
0x180118df1  mov     rcx, [r13+30h]
0x180118df5  mov     edi, eax
0x180118df7  mov     dword ptr [rsp+1300h+ppURI], eax
0x180118dfb  test    rcx, rcx
0x180118dfe  jz      short loc_180118E0C
0x180118e00  call    InFullBrowser
0x180118e05  test    eax, eax
0x180118e07  jz      short loc_180118E0C
0x180118e09  mov     r15d, r12d
0x180118e0c  call    ?_HideOpenWithEdgeInContextMenu@CDocHostUIHandler@@AEAA_NXZ; CDocHostUIHandler::_HideOpenWithEdgeInContextMenu(void)
0x180118e11  mov     r12b, al
0x180118e14  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180118e1a  test    al, al
0x180118e1c  jz      short loc_180118E29
0x180118e1e  call    DualEngine__IsPopupWindow
0x180118e23  movzx   r14d, al
0x180118e27  jmp     short loc_180118E3A
0x180118e29  mov     rcx, r13; this
0x180118e2c  call    ?_IsTabBrowsingEnabled@CDocHostUIHandler@@AEAAHXZ; CDocHostUIHandler::_IsTabBrowsingEnabled(void)
0x180118e31  xor     r14d, r14d
0x180118e34  test    eax, eax
0x180118e36  setz    r14b
0x180118e3a  test    ebx, ebx
0x180118e3c  jnz     short loc_180118E67
0x180118e3e  test    edi, edi
0x180118e40  jnz     short loc_180118E67
0x180118e42  xor     edi, edi
0x180118e44  test    r14d, r14d
0x180118e47  jnz     short loc_180118E69
0x180118e49  test    r15d, r15d
0x180118e4c  jz      short loc_180118E69
0x180118e4e  test    r12b, r12b
0x180118e51  jnz     short loc_180118E69
0x180118e53  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180118e59  test    al, al
0x180118e5b  jnz     short loc_180118E69
0x180118e5d  mov     rbx, [rsp+1300h+hMenu]
0x180118e62  jmp     loc_180118F48
0x180118e67  xor     edi, edi
0x180118e69  mov     rbx, [rsp+1300h+hMenu]
0x180118e6e  mov     rcx, rbx; hMenu
0x180118e71  call    cs:__imp_GetMenuItemCount
0x180118e77  test    eax, eax
0x180118e79  jle     loc_180118F46
0x180118e7f  mov     r13d, [rsp+1300h+var_12C0]
0x180118e84  mov     esi, dword ptr [rsp+1300h+ppURI]
0x180118e88  mov     edx, edi; nPos
0x180118e8a  mov     rcx, rbx; hMenu
0x180118e8d  call    cs:__imp_GetSubMenu
0x180118e93  mov     rbx, rax
0x180118e96  test    rax, rax
0x180118e99  jz      loc_180118F26
0x180118e9f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180118ea5  test    al, al
0x180118ea7  jz      short loc_180118EB1
0x180118ea9  mov     rdx, rbx; HMENU
0x180118eac  call    ?_DisableDualEngineContextMenu@CDocHostUIHandler@@AEAAXPEAUHMENU__@@@Z; CDocHostUIHandler::_DisableDualEngineContextMenu(HMENU__ *)
0x180118eb1  test    r13d, r13d
0x180118eb4  jz      short loc_180118EC6
0x180118eb6  xor     r8d, r8d; uFlags
0x180118eb9  mov     rcx, rbx; hMenu
0x180118ebc  lea     edx, [r8+1Bh]; uPosition
0x180118ec0  call    cs:__imp_DeleteMenu
0x180118ec6  test    esi, esi
0x180118ec8  jz      short loc_180118EDB
0x180118eca  xor     r8d, r8d; uFlags
0x180118ecd  mov     edx, 85Bh; uPosition
0x180118ed2  mov     rcx, rbx; hMenu
0x180118ed5  call    cs:__imp_DeleteMenu
0x180118edb  test    r14d, r14d
0x180118ede  jz      short loc_180118EFA
0x180118ee0  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180118ee5  test    eax, eax
0x180118ee7  jz      short loc_180118EFA
0x180118ee9  xor     r8d, r8d; uFlags
0x180118eec  mov     edx, 983h; uPosition
0x180118ef1  mov     rcx, rbx; hMenu
0x180118ef4  call    cs:__imp_DeleteMenu
0x180118efa  test    r15d, r15d
0x180118efd  jnz     short loc_180118F10
0x180118eff  xor     r8d, r8d; uFlags
0x180118f02  mov     edx, 0F40h; uPosition
0x180118f07  mov     rcx, rbx; hMenu
0x180118f0a  call    cs:__imp_DeleteMenu
0x180118f10  test    r12b, r12b
0x180118f13  jz      short loc_180118F26
0x180118f15  xor     r8d, r8d; uFlags
0x180118f18  mov     edx, 0F47h; uPosition
0x180118f1d  mov     rcx, rbx; hMenu
0x180118f20  call    cs:__imp_DeleteMenu
0x180118f26  mov     rbx, [rsp+1300h+hMenu]
0x180118f2b  inc     edi
0x180118f2d  mov     rcx, rbx; hMenu
0x180118f30  call    cs:__imp_GetMenuItemCount
0x180118f36  cmp     edi, eax
0x180118f38  jl      loc_180118E88
0x180118f3e  mov     esi, [rsp+1300h+var_12A8]
0x180118f42  mov     r13, [rbp+1200h+var_1250]
0x180118f46  xor     edi, edi
0x180118f48  mov     r12d, [rsp+1300h+nPos]
0x180118f4d  cmp     r12d, 8
0x180118f51  jnz     short loc_180118F8F
0x180118f53  mov     rcx, [rsp+1300h+var_12A0]
0x180118f58  lea     r9, [rsp+1300h+uIDCheckItem]
0x180118f5d  mov     [rsp+1300h+uIDCheckItem], 1774h
0x180118f65  lea     r8d, [r12-7]
0x180118f6a  lea     rdx, CGID_MSHTML
0x180118f71  mov     qword ptr [rsp+1300h+var_12E0], rdi
0x180118f76  mov     rax, [rcx]
0x180118f79  mov     rax, [rax+18h]
0x180118f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118f82  cmp     [rsp+1300h+uIDCheckItem+4], 3
0x180118f87  mov     esi, eax
0x180118f89  jnz     loc_180119680
0x180118f8f  mov     edx, r12d; nPos
0x180118f92  mov     rcx, rbx; hMenu
0x180118f95  call    cs:__imp_GetSubMenu
0x180118f9b  mov     rbx, rax
0x180118f9e  test    rax, rax
0x180118fa1  jz      loc_180119680
0x180118fa7  mov     r14b, 1
0x180118faa  test    r15d, r15d
0x180118fad  jz      loc_18011912D
0x180118fb3  lea     rcx, [rsp+1300h+nPos]; ppDataObj
0x180118fb8  mov     qword ptr [rsp+1300h+nPos], rdi
0x180118fbd  mov     sil, dil
0x180118fc0  call    cs:__imp_OleGetClipboard
0x180118fc6  test    eax, eax
0x180118fc8  js      loc_18011911E
0x180118fce  mov     rcx, qword ptr [rsp+1300h+nPos]
0x180118fd3  lea     r8, [rbp+1200h+hMem]
0x180118fd7  xor     eax, eax
0x180118fd9  mov     [rbp+1200h+var_1210], rdi
0x180118fdd  mov     [rbp+1200h+var_1258], rax
0x180118fe1  lea     rdx, [rbp+1200h+var_1218]
0x180118fe5  mov     eax, 0Dh
0x180118fea  mov     [rbp+1200h+var_1208], edi
0x180118fed  mov     [rbp+1200h+var_1218], ax
0x180118ff1  xorps   xmm0, xmm0
0x180118ff4  xor     eax, eax
0x180118ff6  mov     [rbp+1200h+var_1204], 0FFFFFFFFh
  ... truncated ...
```
