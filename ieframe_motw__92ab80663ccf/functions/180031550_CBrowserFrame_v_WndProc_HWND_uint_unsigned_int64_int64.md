# CBrowserFrame::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180031550`
- end: `0x1800326f8`
- name: `?v_WndProc@CBrowserFrame@@MEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4520`
- prototype: `__int64 __fastcall(CBrowserFrame *__hidden this, HWND, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `0`
- callee_count: `66`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800304a4`
- `0x180031550`
- `0x180032700`
- `0x180033920`
- `0x18007587c`
- `0x180084480`
- `0x180085abc`
- `0x1800a3ba0`
- `0x1800a4bdc`
- `0x1800d3a54`
- `0x18019ce6c`
- `0x18019cec4`
- `0x18019cf0c`
- `0x1801e3c48`
- `0x1802520a4`
- `0x1802528c4`
- `0x180253af0`
- `0x180253c50`
- `0x1802571cc`
- `0x1802589d0`
- `0x180259cf8`
- `0x180259e6c`
- `0x180259ef0`
- `0x180259f60`
- `0x18025a19c`
- `0x18025a220`
- `0x18025a2a4`
- `0x18025a6cc`
- `0x18025a8cc`
- `0x18025ab2c`
- `0x18025af20`
- `0x18025b094`
- `0x18025b104`
- `0x18025b4d0`
- `0x18025b848`
- `0x18025baa0`
- `0x18025be54`
- `0x18025c108`
- `0x18025c190`
- `0x18025c384`
- `0x18025c610`
- `0x18025ce10`
- `0x18025d0a0`
- `0x18025d688`
- `0x18025db00`
- `0x18025e364`
- `0x18025f294`
- `0x180260030`
- `0x1802606b0`
- `0x1802607b8`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800315c3`
- `KERNEL32!RaiseException` at `0x18003176e`
- `KERNEL32!RaiseException` at `0x1800315c3`
- `KERNEL32!RaiseException` at `0x18003176e`
- `GDI32!DeleteObject` at `0x180031ba1`
- `GDI32!DeleteObject` at `0x180031d30`
- `GDI32!DeleteObject` at `0x180031e92`
- `GDI32!DeleteObject` at `0x180031ba1`
- `GDI32!DeleteObject` at `0x180031d30`
- `GDI32!DeleteObject` at `0x180031e92`
- `GDI32!CreateRectRgnIndirect` at `0x180031b6c`
- `GDI32!CreateRectRgnIndirect` at `0x180031e5a`
- `GDI32!CreateRectRgnIndirect` at `0x180031b6c`
- `GDI32!CreateRectRgnIndirect` at `0x180031e5a`
- `GDI32!CreateRectRgn` at `0x180031c67`
- `GDI32!CreateRectRgn` at `0x180031c67`
- `USER32!GetWindowRect` at `0x180031b41`
- `USER32!GetWindowRect` at `0x180031e2f`
- `USER32!GetWindowRect` at `0x180031b41`
- `USER32!GetWindowRect` at `0x180031e2f`
- `USER32!GetMonitorInfoW` at `0x18003194f`
- `USER32!GetMonitorInfoW` at `0x18003194f`
- `USER32!GetKeyState` at `0x180031849`
- `USER32!GetKeyState` at `0x180031849`
- `USER32!MapWindowPoints` at `0x180031b5c`
- `USER32!MapWindowPoints` at `0x180031e4a`
- `USER32!MapWindowPoints` at `0x180031b5c`
- `USER32!MapWindowPoints` at `0x180031e4a`
- `USER32!MonitorFromRect` at `0x180031925`
- `USER32!MonitorFromRect` at `0x180031925`
- `USER32!FillRect` at `0x180031bf2`
- `USER32!FillRect` at `0x180031bf2`
- `USER32!GetSystemMenu` at `0x180031884`
- `USER32!GetSystemMenu` at `0x180031884`
- `USER32!GetActiveWindow` at `0x180031cb4`
- `USER32!GetActiveWindow` at `0x180031cb4`
- `USER32!GetWindowDC` at `0x180031ce6`
- `USER32!GetWindowDC` at `0x180031ce6`
- `USER32!GetSysColorBrush` at `0x180031bdc`
- `USER32!GetSysColorBrush` at `0x180031bdc`
- `USER32!IsZoomed` at `0x18003190c`
- `USER32!IsZoomed` at `0x18003190c`
- `USER32!RedrawWindow` at `0x180031b89`
- `USER32!RedrawWindow` at `0x180031e77`
- `USER32!RedrawWindow` at `0x180031b89`
- `USER32!RedrawWindow` at `0x180031e77`
- `USER32!PostMessageW` at `0x1800319e4`
- `USER32!PostMessageW` at `0x180032093`
- `USER32!PostMessageW` at `0x1800322bd`
- `USER32!PostMessageW` at `0x1800319e4`
- `USER32!PostMessageW` at `0x180032093`
- `USER32!PostMessageW` at `0x1800322bd`
- `USER32!ReleaseDC` at `0x180031d18`
- `USER32!ReleaseDC` at `0x180031d18`
- `USER32!DefWindowProcW` at `0x180031679`
- `USER32!DefWindowProcW` at `0x1800318e0`
- `USER32!DefWindowProcW` at `0x180031b04`
- `USER32!DefWindowProcW` at `0x180031c9e`
- `USER32!DefWindowProcW` at `0x180031679`
- `USER32!DefWindowProcW` at `0x1800318e0`
- `USER32!DefWindowProcW` at `0x180031b04`
- `USER32!DefWindowProcW` at `0x180031c9e`
- `USER32!GetWindowLongPtrW` at `0x180031ace`
- `USER32!GetWindowLongPtrW` at `0x180031ace`
- `USER32!SetWindowLongPtrW` at `0x180031aed`
- `USER32!SetWindowLongPtrW` at `0x180031b27`
- `USER32!SetWindowLongPtrW` at `0x180031aed`
- `USER32!SetWindowLongPtrW` at `0x180031b27`
- `UxTheme!IsCompositionActive` at `0x180031ab2`
- `UxTheme!IsCompositionActive` at `0x180031c49`
- `UxTheme!IsCompositionActive` at `0x180031d96`
- `UxTheme!IsCompositionActive` at `0x180031ab2`
- `UxTheme!IsCompositionActive` at `0x180031c49`
- `UxTheme!IsCompositionActive` at `0x180031d96`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1800316f8`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18003170d`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1800316f8`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18003170d`

## pseudocode

```c
unsigned __int64 __fastcall CBrowserFrame::v_WndProc(
        CBrowserFrame *this,
        HWND a2,
        unsigned int a3,
        WPARAM a4,
        LPARAM lParam)
{
  WPARAM v6; // r15
  __int64 v9; // rdx
  CBrowserFrame *v10; // rcx
  LRESULT v11; // rsi
  __int64 v12; // rax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  HMENU SystemMenu; // rbx
  bool v19; // al
  HMONITOR v20; // rax
  CTabWindowManager *v21; // rcx
  bool v22; // al
  LONG_PTR WindowLongPtrW; // rbx
  HRGN RectRgnIndirect; // rbx
  __int64 v25; // rax
  HBRUSH SysColorBrush; // rax
  int v27; // r9d
  __int64 v28; // rax
  HDC v29; // rdi
  struct tagRECT *v30; // r8
  HRGN RectRgn; // rbx
  _DWORD *v32; // rax
  HDC WindowDC; // rax
  char v34; // al
  bool v35; // zf
  int v36; // eax
  __int64 v37; // rcx
  CTabWindowManager *v38; // rcx
  HRGN v39; // rbx
  bool v40; // dl
  struct tagDDENAVIGATESTRUCT *v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  CCommandBar *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rdx
  bool v49; // al
  int v50; // eax
  __int64 v51; // r9
  unsigned int v52; // edx
  unsigned __int64 v53; // r8
  __int64 v54; // rcx
  CTabWindowManager *v55; // rcx
  int v56; // [rsp+40h] [rbp-51h] BYREF
  bool v57; // [rsp+44h] [rbp-4Dh]
  __int64 v58[2]; // [rsp+50h] [rbp-41h] BYREF
  struct tagMONITORINFO Arguments; // [rsp+60h] [rbp-31h] BYREF

  v6 = a4;
  v9 = 3;
  if ( *((_WORD *)this + 121) != 0xF5A0 )
  {
    *(_QWORD *)&Arguments.rcMonitor.top = *((unsigned __int16 *)this + 121);
    *(_QWORD *)&Arguments.rcMonitor.bottom = *((unsigned __int16 *)this + 120);
    *(_QWORD *)&Arguments.cbSize = 62880;
    RaiseException(0xC0000005, 1u, 3u, (const ULONG_PTR *)&Arguments.cbSize);
    v9 = 3;
  }
  v10 = (CBrowserFrame *)*((unsigned __int16 *)this + 120);
  if ( (_WORD)v10 != 0xC075 )
  {
    v15 = *((unsigned __int16 *)this + 121);
    *(_QWORD *)&Arguments.rcMonitor.bottom = *((unsigned __int16 *)this + 120);
    *(_QWORD *)&Arguments.rcMonitor.top = v15;
    *(_QWORD *)&Arguments.cbSize = 62880;
    RaiseException(0xC0000005, 1u, 3u, (const ULONG_PTR *)&Arguments.cbSize);
  }
  v56 = 0;
  v11 = 0;
  v58[0] = 0;
  if ( a3 <= 0x106 )
  {
    if ( a3 == 262 )
    {
      if ( v6 != 32 )
      {
        v45 = *((_QWORD *)this + 41);
        if ( v45 )
          PostMessageW(*(HWND *)(v45 + 48), 0x106u, v6, lParam);
        return v11;
      }
      goto LABEL_22;
    }
    switch ( a3 )
    {
      case 1u:
        if ( !(unsigned int)CBrowserFrame::_OnCreate(this, (HWND)&_ImageBase) )
          return -1;
        return v11;
      case 2u:
        CBrowserFrame::_DeleteActivationRecord(this);
        goto LABEL_188;
      case 3u:
        TLSCallFrameEventHandlers(a3, v6, lParam);
        CBrowserFrame::_HideBalloonTip(this);
        CBrowserFrame::_DismissBrowserAnimation(this);
        v42 = *((_QWORD *)this + 35);
        if ( v42 )
          CTabWindowManager::OnForegroundTabEvent(v42, 9);
        if ( *((_QWORD *)this + 44) )
        {
          v43 = *((_QWORD *)this + 14);
          *(_OWORD *)&Arguments.cbSize = 0;
          (*(void (__fastcall **)(char *, struct tagMONITORINFO *))(v43 + 104))((char *)this + 112, &Arguments);
          v44 = *((_QWORD *)this + 44);
          *(_OWORD *)v58 = *(_OWORD *)&Arguments.cbSize;
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, v58);
        }
        goto LABEL_188;
      case 5u:
        TLSCallFrameEventHandlers(a3, v6, lParam);
        if ( (unsigned int)CBrowserFrame::_CheckFrameSizeTypeChange(this, v6) )
          CBrowserFrame::_NotifyFrameSizeChanged(this);
        v34 = *((_BYTE *)this + 832);
        v57 = v34;
        v35 = v6 == 2;
        if ( v6 == 2 )
        {
          v35 = 1;
          v57 = v34 == 0;
        }
        *((_BYTE *)this + 832) = v35;
        v36 = IsCompositionActive() && v57;
        CBrowserFrame::_OnSize(this, 0, v36);
        goto LABEL_188;
      case 6u:
        CBrowserFrame::_OnActivate(this, (HWND)&_ImageBase, a3, v6, lParam);
        return v11;
      case 0xAu:
        CBrowserFrame::_OnEnable(this, (int)&_ImageBase);
        if ( v6 )
          CInputObjectContainer::RestoreLastFocus((CBrowserFrame *)((char *)this + 16), *((HWND *)this + 1));
        goto LABEL_188;
      case 0xCu:
      case 0x80u:
        if ( !CBrowserFrame::_ShowClientCaption(this) || IsCompositionActive() )
          return DefWindowProcW(a2, a3, v6, lParam);
        WindowLongPtrW = GetWindowLongPtrW(a2, -16);
        SetWindowLongPtrW(a2, -16, WindowLongPtrW & 0xFFFFFFFFEFFFFFFFuLL);
        v11 = DefWindowProcW(a2, a3, v6, lParam);
        if ( WindowLongPtrW )
        {
          SetWindowLongPtrW(a2, -16, WindowLongPtrW);
          *(_OWORD *)&Arguments.cbSize = 0;
          GetWindowRect(a2, (LPRECT)&Arguments);
          MapWindowPoints(0, a2, (LPPOINT)&Arguments, 2u);
          RectRgnIndirect = CreateRectRgnIndirect((const RECT *)&Arguments);
          RedrawWindow(a2, 0, RectRgnIndirect, 0x485u);
          if ( RectRgnIndirect )
            DeleteObject(RectRgnIndirect);
        }
        return v11;
      case 0x10u:
        PostMessageW(a2, 0x46Au, 0, 0);
        return v11;
      case 0x11u:
        if ( (lParam & 1) != 0 )
        {
          v11 = 1;
          v56 = 1;
        }
        goto LABEL_188;
      case 0x14u:
        if ( !*((_DWORD *)this + 154) )
        {
          v25 = *((_QWORD *)this + 14);
          *(_OWORD *)&Arguments.cbSize = 0;
          (*(void (__fastcall **)(char *, struct tagMONITORINFO *))(v25 + 104))((char *)this + 112, &Arguments);
          SysColorBrush = GetSysColorBrush(5);
          FillRect((HDC)v6, (const RECT *)&Arguments, SysColorBrush);
          v28 = *((_QWORD *)this + 41);
          if ( v28 )
          {
            v29 = (HDC)(v28 + 24);
            if ( *(_DWORD *)(v28 + 36) - *(_DWORD *)(v28 + 28) > 0 )
            {
              Theme::DrawRebarBackground((HDC)v6, v29, 0, v27);
              Theme::DrawITBarBackgroundEdges((HDC)v6, v29, v30);
            }
          }
        }
        return 1;
      case 0x15u:
        CBrowserFrame::_OnSettingsChange(this, 0x15u, 0, 0);
LABEL_146:
        CBrowserFrame::_OnThemeChange(this, v6);
        goto LABEL_188;
      case 0x16u:
        CBrowserFrame::_OnEndSession(this, a3, v6, lParam, &v56);
        goto LABEL_188;
      case 0x1Au:
        CBrowserFrame::_OnSettingsChange(this, a3, v6, lParam);
        goto LABEL_188;
      case 0x24u:
        *(_DWORD *)(lParam + 24) = g_dwMinFrameWidth;
        *(_DWORD *)(lParam + 28) = g_dwMinFrameHeight;
        return v11;
      case 0x47u:
        v37 = *((_QWORD *)this + 35);
        if ( v37 )
        {
          CTabWindowManager::ForwardMessageToActiveTab(v37, 33169, 0, 0, 0, 0);
          CTabWindowManager::OnForegroundTabEvent(*((_QWORD *)this + 35), 7);
          v38 = (CTabWindowManager *)*((_QWORD *)this + 35);
          if ( *((_QWORD *)v38 + 28) )
            CTabWindowManager::FakeModalForwardWM_WINDOWPOSCHANGED(v38);
        }
        if ( (*(_BYTE *)(lParam + 32) & 0x20) != 0 )
        {
          if ( *((_BYTE *)this + 833) )
          {
            *(_OWORD *)&Arguments.cbSize = 0;
            GetWindowRect(a2, (LPRECT)&Arguments);
            MapWindowPoints(0, a2, (LPPOINT)&Arguments, 2u);
            v39 = CreateRectRgnIndirect((const RECT *)&Arguments);
            RedrawWindow(a2, 0, v39, 0x505u);
            *((_BYTE *)this + 833) = 0;
            if ( v39 )
              DeleteObject(v39);
          }
          v40 = *(_DWORD *)(*((_QWORD *)this + 34) + 60LL) != 1 && CBrowserFrame::_ShowClientCaption(this);
          CClientCaption::Show((CBrowserFrame *)((char *)this + 752), v40);
        }
        goto LABEL_188;
      case 0x4Au:
        if ( !lParam )
          goto LABEL_22;
        if ( *(_QWORD *)lParam != 1 )
          goto LABEL_22;
        v41 = *(struct tagDDENAVIGATESTRUCT **)(lParam + 16);
        if ( !v41 || *(_DWORD *)(lParam + 8) != 4172 )
          goto LABEL_22;
        return (unsigned __int64)(unsigned int)~CBrowserFrame::_AddNavItemToBuffer(this, v41) >> 31;
      case 0x53u:
        Arguments.rcMonitor.top = 337;
        LOWORD(Arguments.cbSize) = 3;
        (*(void (__fastcall **)(char *, const GUID *, __int64, _QWORD, struct tagMONITORINFO *, _QWORD))(*((_QWORD *)this + 10) + 32LL))(
          (char *)this + 80,
          &CGID_Explorer,
          76,
          0,
          &Arguments,
          0);
        v56 = 1;
        v11 = 1;
        ATL::CComVariant::Clear((ATL::CComVariant *)&Arguments);
        goto LABEL_188;
      case 0x7Bu:
        v11 = CBrowserFrame::_OnContextMenu(this, v6, lParam, 0);
        goto LABEL_188;
      case 0x7Eu:
        CBrowserFrame::_NotifyOrientationChanged(this);
        goto LABEL_188;
      case 0x81u:
        IEDDE_NewWindow(a2);
        goto LABEL_188;
      case 0x82u:
        IEDDE_WindowDestroyed(a2);
        CBrowserFrame::_OnDestroy(this);
        goto LABEL_188;
      case 0x83u:
        LODWORD(v58[0]) = *(_DWORD *)(lParam + 4);
        v56 = 1;
        v11 = DefWindowProcW(a2, a3, v6, lParam);
        if ( CBrowserFrame::_ShowClientCaption(this) )
        {
          *(_DWORD *)(lParam + 4) = v58[0];
          if ( IsZoomed(a2) )
          {
            v20 = MonitorFromRect((LPCRECT)lParam, 1u);
            Arguments.cbSize = 40;
            memset(&Arguments.rcMonitor, 0, 36);
            if ( GetMonitorInfoW(v20, &Arguments) )
            {
              if ( *(_DWORD *)(lParam + 12) >= Arguments.rcMonitor.bottom )
                *(_DWORD *)(lParam + 12) = Arguments.rcMonitor.bottom - 1;
            }
          }
        }
        goto LABEL_188;
      case 0x84u:
        if ( (*(_DWORD *)(*((_QWORD *)this + 34) + 56LL) & 0x200) != 0 )
          goto LABEL_22;
        if ( *((_DWORD *)this + 135) )
        {
          if ( !CBrowserFrame::_ShowClientCaption(this)
            || (v16 = CClientCaption::HitTest((CBrowserFrame *)((char *)this + 752), a2, a3, v6, lParam, v58),
                v11 = v58[0],
                !v16) )
          {
            v11 = 2;
          }
          *((_DWORD *)this + 135) = 0;
        }
        else if ( !CBrowserFrame::_ShowClientCaption(this)
               || (v17 = CClientCaption::HitTest((CBrowserFrame *)((char *)this + 752), a2, a3, v6, lParam, v58),
                   v11 = v58[0],
                   !v17) )
        {
          v56 = 0;
          goto LABEL_22;
        }
        v56 = 1;
        if ( v11 != 3 )
          return v11;
        if ( GetKeyState(2) < 0 )
          v11 = 2;
        goto LABEL_188;
      case 0x85u:
        if ( !CBrowserFrame::_ShowClientCaption(this) || IsCompositionActive() )
          goto LABEL_188;
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        if ( (int)CClientCaption::ValidateFrameNCRegion((CBrowserFrame *)((char *)this + 752), a2, (HRGN)v6, RectRgn) < 0 )
          goto LABEL_81;
        v11 = DefWindowProcW(a2, a3, (WPARAM)RectRgn, lParam);
        v56 = 1;
        v35 = GetActiveWindow() == a2;
        v32 = (_DWORD *)((char *)this + 544);
        if ( v35 )
        {
          v35 = *v32 == 0;
          v58[0] = (__int64)this + 544;
          if ( v35 )
            goto LABEL_79;
        }
        else if ( *v32 )
        {
          v58[0] = (__int64)this + 544;
          goto LABEL_79;
        }
        v35 = *((_BYTE *)this + 833) == 0;
        v58[0] = (__int64)this + 544;
        if ( v35 )
          goto LABEL_81;
LABEL_79:
        WindowDC = GetWindowDC(a2);
        *(_QWORD *)&Arguments.cbSize = WindowDC;
        if ( WindowDC )
        {
          CBrowserFrame::_DrawNCBorders(this, WindowDC, *(_DWORD *)v58[0] != 0);
          ReleaseDC(a2, *(HDC *)&Arguments.cbSize);
        }
LABEL_81:
        if ( RectRgn )
          DeleteObject(RectRgn);
        break;
      case 0x86u:
        v22 = CBrowserFrame::_OnNCActivate(this, a2, 0, v6, lParam, v58);
        v35 = *((_BYTE *)this + 981) == 0;
        v11 = v58[0];
        v56 = v22;
        if ( !v35 )
          v6 = 1;
        goto LABEL_188;
      case 0xA1u:
      case 0xA4u:
      case 0xA7u:
        if ( !g_fHangRecovery )
          goto LABEL_22;
        v21 = (CTabWindowManager *)*((_QWORD *)this + 35);
        if ( !v21 )
          goto LABEL_22;
        if ( CTabWindowManager::AllUnresponsiveBrowserTabsAreDetached(v21, g_cTabWindow_SyncTMO, 0) )
          goto LABEL_188;
        return v11;
      case 0xA5u:
        if ( v6 != 2 )
          goto LABEL_22;
        SystemMenu = GetSystemMenu(*((HWND *)this + 1), 0);
        if ( SystemMenu )
        {
          v19 = CBrowserFrame::_ShowClientCaption(this);
          MergeAndShowSystemMenu(
            SystemMenu,
            *((HWND *)this + 1),
            *((HWND *)this + 1),
            (__int16)lParam,
            SWORD1(lParam),
            v19);
        }
        goto LABEL_188;
      default:
        goto LABEL_22;
    }
    goto LABEL_188;
  }
  if ( a3 <= 0x31E )
  {
    if ( a3 != 798 )
    {
      if ( a3 > 0x20E )
      {
        switch ( a3 )
        {
          case 0x2CBu:
            if ( !(unsigned __int8)IsFlickAnimationSupported()
              || (v6 & 0x1F) != 2
              || (int)v6 >> 16 != 1 && (int)v6 >> 16 != 2 )
            {
              goto LABEL_188;
            }
            PostMessageW(a2, 0x80D8u, ((int)v6 >> 16 != 1) + 1LL, 0);
            v11 = 1;
            break;
          case 0x2E0u:
            CBrowserFrame::_NotifyEffectiveDpiChange(this, a2, (struct tagRECT *)lParam);
            goto LABEL_188;
          case 0x30Fu:
            v50 = CBrowserFrame::_RealizeBrowserPalette(this, v58);
            v11 = v58[0];
            v56 = v50;
            goto LABEL_188;
          case 0x311u:
            CBrowserFrame::_OnSettingsChange(this, a3, v6, 0);
            goto LABEL_188;
          case 0x319u:
            if ( !(unsigned int)CBrowserFrame::_OnAppCommand(this, v6, lParam) )
              goto LABEL_188;
            v11 = 1;
            break;
          case 0x31Au:
            if ( (*(_DWORD *)(*((_QWORD *)this + 34) + 56LL) & 0x200) == 0 )
            {
              CClientCaption::_CalculateButtonMetrics((CBrowserFrame *)((char *)this + 752));
              v49 = HasClientCaption();
              CClientCaption::Show((CBrowserFrame *)((char *)this + 752), v49);
            }
            goto LABEL_146;
          default:
            goto LABEL_22;
        }
        return v11;
      }
      if ( a3 != 526 )
      {
        switch ( a3 )
        {
          case 0x111u:
            if ( !(unsigned int)CBrowserFrame::_OnCommand(this, v6, 0) )
              goto LABEL_188;
            break;
          case 0x112u:
            if ( !(unsigned int)CBrowserFrame::_OnSysCommand(this, v6, lParam) )
              goto LABEL_188;
            break;
          case 0x113u:
            CBrowserFrame::_OnTimer(this, v6);
            goto LABEL_188;
          case 0x127u:
            CBrowserFrame::_OnChangeUIState(this, v6, lParam);
            break;
          case 0x128u:
            CBrowserFrame::_OnUpdateUIState(this, v6, lParam);
            break;
          case 0x129u:
            v11 = *((unsigned __int16 *)this + 472);
            break;
          case 0x20Au:
            goto LABEL_137;
          default:
            goto LABEL_22;
        }
        return v11;
      }
LABEL_137:
      v46 = (CCommandBar *)*((_QWORD *)this + 36);
      if ( !v46 )
        goto LABEL_22;
      if ( CCommandBar::IsEnabledBrowserWheeling(v46) )
      {
        v47 = *((_QWORD *)this + 35);
        if ( v47 )
        {
          v48 = 33175;
          if ( a3 != 522 )
            v48 = 33184;
          CTabWindowManager::ForwardMessageToActiveTab(v47, v48, v6, 0, 3, 0);
          return v11;
        }
      }
      goto LABEL_188;
    }
LABEL_165:
    v51 = 0;
    v52 = 798;
    v53 = -2;
LABEL_187:
    CBrowserFrame::_SendMessageToNavBar(this, v52, v53, v51);
    goto LABEL_188;
  }
  if ( a3 <= 0x80E0 )
  {
    if ( a3 == 32992 )
    {
      CBrowserFrame::_TriggerAeroSnapDestination(this);
      goto LABEL_188;
    }
    if ( a3 > 0x70B )
    {
      switch ( a3 )
      {
        case 0x70Du:
          return CBrowserFrame::_OnAttachInputQueue(v10, v6);
        case 0x8066u:
          v54 = *((_QWORD *)this + 35);
          if ( !v54 )
            goto LABEL_12;
          CTabWindowManager::ForwardMessageToAllTabs(v54, a3, v6, lParam);
          break;
        case 0x80DFu:
          CBrowserFrame::_TriggerAeroSnapSource(this, (HWND)lParam);
          break;
        default:
LABEL_190:
          if ( a3 <= 0x7FFF )
            goto LABEL_12;
LABEL_21:
          if ( a3 < 0x8000 )
            goto LABEL_22;
          goto LABEL_11;
      }
      goto LABEL_188;
    }
    if ( a3 == 1803 )
      return (int)IEDDE_RunDelayedExecute(v10, v9);
    if ( a3 != 799 )
    {
      if ( a3 != 800 )
      {
        if ( a3 == 1797 )
          return CBrowserFrame::_ProcessDDERequest(this, v6, lParam);
LABEL_20:
        if ( a3 < 0x400 )
          goto LABEL_21;
        goto LABEL_190;
      }
      CBrowserFrame::_HandleNewTabPageColorChange(this);
LABEL_188:
      if ( v56 )
        return v11;
      goto LABEL_20;
    }
    goto LABEL_165;
  }
  if ( a3 <= 0x80F2 )
  {
    switch ( a3 )
    {
      case 0x80F2u:
        CLayerParticipant::LayerSetInterface((CBrowserFrame *)((char *)this + 168), 0, 69758, a4);
        goto LABEL_188;
      case 0x80E1u:
        CBrowserFrame::_RepostMouseMove(this);
        goto LABEL_188;
      case 0x80E2u:
        v55 = (CTabWindowManager *)*((_QWORD *)this + 35);
        if ( !v55 )
          goto LABEL_12;
        CTabWindowManager::OnAllTabsClosed(v55);
        goto LABEL_188;
    }
    if ( a3 != 33009 )
      goto LABEL_12;
    CBrowserFrame::_SetFrameIcon(this);
    v52 = 33009;
    goto LABEL_186;
  }
  if ( a3 == 33011 )
  {
    v52 = 33011;
LABEL_186:
    v53 = v6;
    v51 = lParam;
    goto LABEL_187;
  }
  if ( a3 == 33853 )
  {
    CBrowserFrame::_OnTimerFlashServicingInterval(this);
    CBrowserFrame::_StartFlashServicingTimer(this);
    goto LABEL_188;
  }
LABEL_11:
  if ( a3 <= 0xBFFF )
  {
LABEL_12:
    v12 = CBrowserFrame::_FrameMessagesWndProc(this, a3, v6, lParam, &v56);
LABEL_13:
    v11 = v12;
    goto LABEL_14;
  }
LABEL_22:
  if ( a3 == (unsigned int)IsoGetWindowsMessageNumber(2) || a3 == (unsigned int)IsoGetWindowsMessageNumber(3) )
  {
    v12 = CBrowserFrame::_FrameLCIEWndProc(this, a3, v6, lParam, &v56);
    goto LABEL_13;
  }
  if ( a3 - 49152 <= 0x3FFF )
  {
    v12 = CBrowserFrame::_RegisteredMessagesWndProc(this, a3, v6, lParam, &v56);
    goto LABEL_13;
  }
LABEL_14:
  if ( !v56 )
    return DefWindowProcW(a2, a3, v6, lParam);
  return v11;
}

```

## disassembly

```asm
0x180031550  push    rbp
0x180031552  push    rbx
0x180031553  push    rsi
0x180031554  push    rdi
0x180031555  push    r12
0x180031557  push    r13
0x180031559  push    r14
0x18003155b  push    r15
0x18003155d  lea     rbp, [rsp-17h]
0x180031562  sub     rsp, 0A8h
0x180031569  mov     rax, cs:__security_cookie
0x180031570  xor     rax, rsp
0x180031573  mov     [rbp+4Fh+var_50], rax
0x180031577  movzx   eax, word ptr [rcx+0F2h]
0x18003157e  mov     esi, 0F5A0h
0x180031583  mov     r13, [rbp+4Fh+lParam]
0x180031587  mov     r12, rdx
0x18003158a  mov     r15, r9
0x18003158d  mov     edi, r8d
0x180031590  mov     r14, rcx
0x180031593  mov     edx, 3
0x180031598  mov     ebx, 1
0x18003159d  cmp     ax, si
0x1800315a0  jz      short loc_1800315D4
0x1800315a2  mov     [rbp+4Fh+Arguments+8], rax
0x1800315a6  lea     r9, [rbp+4Fh+Arguments]; lpArguments
0x1800315aa  movzx   eax, word ptr [rcx+0F0h]
0x1800315b1  mov     r8d, edx; nNumberOfArguments
0x1800315b4  mov     ecx, 0C0000005h; dwExceptionCode
0x1800315b9  mov     qword ptr [rbp+4Fh+var_70], rax
0x1800315bd  mov     edx, ebx; dwExceptionFlags
0x1800315bf  mov     [rbp+4Fh+Arguments], rsi
0x1800315c3  call    cs:__imp_RaiseException
0x1800315ca  nop     dword ptr [rax+rax+00h]
0x1800315cf  mov     edx, 3
0x1800315d4  movzx   ecx, word ptr [r14+0F0h]; this
0x1800315dc  mov     eax, 0C075h
0x1800315e1  cmp     cx, ax
0x1800315e4  jnz     loc_18003174C
0x1800315ea  xor     r8d, r8d; __int64
0x1800315ed  mov     [rbp+4Fh+var_A0], r8d
0x1800315f1  mov     esi, r8d
0x1800315f4  mov     [rbp+4Fh+var_90], r8
0x1800315f8  cmp     edi, 106h
0x1800315fe  jbe     loc_1800316AC
0x180031604  cmp     edi, 31Eh
0x18003160a  jbe     loc_1800320A4
0x180031610  cmp     edi, 80E0h
0x180031616  jbe     loc_1800322E4
0x18003161c  cmp     edi, 80F2h
0x180031622  jbe     loc_1800323B2
0x180031628  cmp     edi, 80F3h
0x18003162e  jz      loc_180032422
0x180031634  cmp     edi, 843Dh
0x18003163a  jz      loc_180032410
0x180031640  cmp     edi, 0BFFFh
0x180031646  ja      def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x18003164c  lea     rax, [rbp+4Fh+var_A0]
0x180031650  mov     r9, r13; __int64
0x180031653  mov     r8, r15; unsigned __int64
0x180031656  mov     [rsp+0E0h+var_C0], rax; int *
0x18003165b  mov     edx, edi; unsigned int
0x18003165d  mov     rcx, r14; this
0x180031660  call    ?_FrameMessagesWndProc@CBrowserFrame@@IEAA_JI_K_JPEAH@Z; CBrowserFrame::_FrameMessagesWndProc(uint,unsigned __int64,__int64,int *)
0x180031665  mov     rsi, rax
0x180031668  cmp     [rbp+4Fh+var_A0], 0
0x18003166c  jnz     short loc_180031688
0x18003166e  mov     r9, r13; lParam
0x180031671  mov     r8, r15; wParam
0x180031674  mov     edx, edi; Msg
0x180031676  mov     rcx, r12; hWnd
0x180031679  call    cs:__imp_DefWindowProcW
0x180031680  nop     dword ptr [rax+rax+00h]
0x180031685  mov     rsi, rax
0x180031688  mov     rax, rsi
0x18003168b  mov     rcx, [rbp+4Fh+var_50]
0x18003168f  xor     rcx, rsp; StackCookie
0x180031692  call    __security_check_cookie
0x180031697  add     rsp, 0A8h
0x18003169e  pop     r15
0x1800316a0  pop     r14
0x1800316a2  pop     r13
0x1800316a4  pop     r12
0x1800316a6  pop     rdi
0x1800316a7  pop     rsi
0x1800316a8  pop     rbx
0x1800316a9  pop     rbp
0x1800316aa  retn
0x1800316ac  jz      loc_18003206A
0x1800316b2  lea     eax, [rdi-1]; switch 167 cases
0x1800316b5  cmp     eax, 0A6h
0x1800316ba  ja      short def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x1800316bc  lea     rdx, __ImageBase; int
0x1800316c3  movzx   eax, ds:(byte_1800324C8 - 180000000h)[rdx+rax]
0x1800316cb  mov     ecx, ds:(jpt_1800316D5 - 180000000h)[rdx+rax*4]
0x1800316d2  add     rcx, rdx
0x1800316d5  jmp     rcx; switch jump
0x1800316db  cmp     edi, 400h
0x1800316e1  jnb     loc_180032444
0x1800316e7  cmp     edi, 8000h
0x1800316ed  jnb     loc_180031640
0x1800316f3  mov     ecx, 2; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x1800316f8  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x1800316ff  nop     dword ptr [rax+rax+00h]
0x180031704  cmp     edi, eax
0x180031706  jz      short loc_18003177F
0x180031708  mov     ecx, 3
0x18003170d  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x180031714  nop     dword ptr [rax+rax+00h]
0x180031719  cmp     edi, eax
0x18003171b  jz      short loc_18003177F
0x18003171d  lea     eax, [rdi-0C000h]
0x180031723  cmp     eax, 3FFFh
0x180031728  ja      loc_180031668
0x18003172e  lea     rax, [rbp+4Fh+var_A0]
0x180031732  mov     r9, r13; __int64
0x180031735  mov     r8, r15; unsigned int
0x180031738  mov     [rsp+0E0h+var_C0], rax; int *
0x18003173d  mov     edx, edi; unsigned int
0x18003173f  mov     rcx, r14; this
0x180031742  call    ?_RegisteredMessagesWndProc@CBrowserFrame@@IEAA_JI_K_JPEAH@Z; CBrowserFrame::_RegisteredMessagesWndProc(uint,unsigned __int64,__int64,int *)
0x180031747  jmp     loc_180031665
0x18003174c  movzx   eax, word ptr [r14+0F2h]
0x180031754  lea     r9, [rbp+4Fh+Arguments]; lpArguments
0x180031758  mov     qword ptr [rbp+4Fh+var_70], rcx
0x18003175c  mov     r8d, edx; nNumberOfArguments
0x18003175f  mov     edx, ebx; dwExceptionFlags
0x180031761  mov     [rbp+4Fh+Arguments+8], rax
0x180031765  mov     ecx, 0C0000005h; dwExceptionCode
0x18003176a  mov     [rbp+4Fh+Arguments], rsi
0x18003176e  call    cs:__imp_RaiseException
0x180031775  nop     dword ptr [rax+rax+00h]
0x18003177a  jmp     loc_1800315EA
0x18003177f  lea     rax, [rbp+4Fh+var_A0]
0x180031783  mov     r9, r13; __int64
0x180031786  mov     r8, r15; unsigned __int64
0x180031789  mov     [rsp+0E0h+var_C0], rax; int *
0x18003178e  mov     edx, edi; unsigned int
0x180031790  mov     rcx, r14; this
0x180031793  call    ?_FrameLCIEWndProc@CBrowserFrame@@IEAA_JI_K_JPEAH@Z; CBrowserFrame::_FrameLCIEWndProc(uint,unsigned __int64,__int64,int *)
0x180031798  jmp     loc_180031665
0x18003179d  mov     rax, [r14+110h]; jumptable 00000001800316D5 case 132
0x1800317a4  test    dword ptr [rax+38h], 200h
0x1800317ab  jnz     def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x1800317b1  mov     rcx, r14; this
0x1800317b4  cmp     [r14+21Ch], esi
0x1800317bb  jz      short loc_180031803
0x1800317bd  call    ?_ShowClientCaption@CBrowserFrame@@IEAA_NXZ; CBrowserFrame::_ShowClientCaption(void)
0x1800317c2  test    al, al
0x1800317c4  jz      short loc_1800317F1
0x1800317c6  lea     rax, [rbp+4Fh+var_90]
0x1800317ca  mov     r9, r15; unsigned __int64
0x1800317cd  mov     [rsp+0E0h+var_B8], rax; __int64 *
0x1800317d2  lea     rcx, [r14+2F0h]; this
0x1800317d9  mov     r8d, edi; unsigned int
0x1800317dc  mov     [rsp+0E0h+var_C0], r13; __int64
0x1800317e1  mov     rdx, r12; HWND
0x1800317e4  call    ?HitTest@CClientCaption@@QEAAHPEAUHWND__@@I_K_JPEA_J@Z; CClientCaption::HitTest(HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800317e9  mov     rsi, [rbp+4Fh+var_90]
0x1800317ed  test    eax, eax
0x1800317ef  jnz     short loc_1800317F6
0x1800317f1  mov     esi, 2
0x1800317f6  mov     dword ptr [r14+21Ch], 0
0x180031801  jmp     short loc_180031837
0x180031803  call    ?_ShowClientCaption@CBrowserFrame@@IEAA_NXZ; CBrowserFrame::_ShowClientCaption(void)
0x180031808  test    al, al
0x18003180a  jz      short loc_180031868
0x18003180c  lea     rax, [rbp+4Fh+var_90]
0x180031810  mov     r9, r15; unsigned __int64
0x180031813  mov     [rsp+0E0h+var_B8], rax; __int64 *
0x180031818  lea     rcx, [r14+2F0h]; this
0x18003181f  mov     r8d, edi; unsigned int
0x180031822  mov     [rsp+0E0h+var_C0], r13; __int64
0x180031827  mov     rdx, r12; HWND
0x18003182a  call    ?HitTest@CClientCaption@@QEAAHPEAUHWND__@@I_K_JPEA_J@Z; CClientCaption::HitTest(HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003182f  mov     rsi, [rbp+4Fh+var_90]
0x180031833  test    eax, eax
0x180031835  jz      short loc_180031868
0x180031837  mov     [rbp+4Fh+var_A0], ebx
0x18003183a  cmp     rsi, 3
0x18003183e  jnz     loc_180031688
0x180031844  mov     ecx, 2; nVirtKey
0x180031849  call    cs:__imp_GetKeyState
0x180031850  nop     dword ptr [rax+rax+00h]
0x180031855  test    ax, ax
0x180031858  jns     loc_180032435
0x18003185e  mov     esi, 2
0x180031863  jmp     loc_180032435
0x180031868  mov     [rbp+4Fh+var_A0], 0
0x18003186f  jmp     def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x180031874  cmp     r15, 2; jumptable 00000001800316D5 case 165
0x180031878  jnz     def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x18003187e  mov     rcx, [r14+8]; hWnd
0x180031882  xor     edx, edx; bRevert
0x180031884  call    cs:__imp_GetSystemMenu
0x18003188b  nop     dword ptr [rax+rax+00h]
0x180031890  mov     rbx, rax
0x180031893  test    rax, rax
0x180031896  jz      loc_180032435
0x18003189c  mov     rcx, r14; this
0x18003189f  call    ?_ShowClientCaption@CBrowserFrame@@IEAA_NXZ; CBrowserFrame::_ShowClientCaption(void)
0x1800318a4  mov     r8, [r14+8]; hWnd
0x1800318a8  mov     rcx, r13
0x1800318ab  shr     rcx, 10h
0x1800318af  movsx   edx, cx
0x1800318b2  mov     rcx, rbx; hMenu
0x1800318b5  mov     byte ptr [rsp+0E0h+var_B8], al; bool
0x1800318b9  mov     dword ptr [rsp+0E0h+var_C0], edx; int
0x1800318bd  mov     rdx, r8; hwnd
0x1800318c0  movsx   r9d, r13w; x
0x1800318c4  call    ?MergeAndShowSystemMenu@@YAXPEAUHMENU__@@PEAUHWND__@@1HH_N@Z; MergeAndShowSystemMenu(HMENU__ *,HWND__ *,HWND__ *,int,int,bool)
0x1800318c9  jmp     loc_180032435
0x1800318ce  mov     eax, [r13+4]; jumptable 00000001800316D5 case 131
0x1800318d2  mov     r9, r13; lParam
0x1800318d5  mov     r8, r15; wParam
0x1800318d8  mov     dword ptr [rbp+4Fh+var_90], eax
0x1800318db  mov     edx, edi; Msg
0x1800318dd  mov     rcx, r12; hWnd
0x1800318e0  call    cs:__imp_DefWindowProcW
0x1800318e7  nop     dword ptr [rax+rax+00h]
0x1800318ec  mov     rcx, r14; this
0x1800318ef  mov     [rbp+4Fh+var_A0], ebx
0x1800318f2  mov     rsi, rax
0x1800318f5  call    ?_ShowClientCaption@CBrowserFrame@@IEAA_NXZ; CBrowserFrame::_ShowClientCaption(void)
0x1800318fa  test    al, al
0x1800318fc  jz      loc_180032435
0x180031902  mov     eax, dword ptr [rbp+4Fh+var_90]
0x180031905  mov     rcx, r12; hWnd
0x180031908  mov     [r13+4], eax
0x18003190c  call    cs:__imp_IsZoomed
0x180031913  nop     dword ptr [rax+rax+00h]
0x180031918  test    eax, eax
0x18003191a  jz      loc_180032435
0x180031920  mov     edx, ebx; dwFlags
0x180031922  mov     rcx, r13; lprc
0x180031925  call    cs:__imp_MonitorFromRect
0x18003192c  nop     dword ptr [rax+rax+00h]
0x180031931  xor     ecx, ecx
0x180031933  mov     dword ptr [rbp+4Fh+Arguments], 28h ; '('
0x18003193a  xorps   xmm0, xmm0
0x18003193d  mov     [rbp+4Fh+var_5C], ecx
0x180031940  mov     rcx, rax; hMonitor
0x180031943  lea     rdx, [rbp+4Fh+Arguments]; lpmi
0x180031947  movups  xmmword ptr [rbp+4Fh+Arguments+4], xmm0
0x18003194b  movups  [rbp+4Fh+var_70+4], xmm0
0x18003194f  call    cs:__imp_GetMonitorInfoW
0x180031956  nop     dword ptr [rax+rax+00h]
0x18003195b  test    eax, eax
0x18003195d  jz      loc_180032435
0x180031963  mov     eax, dword ptr [rbp+4Fh+var_70]
0x180031966  cmp     [r13+0Ch], eax
0x18003196a  jl      loc_180032435
0x180031970  dec     eax
0x180031972  mov     [r13+0Ch], eax
0x180031976  jmp     loc_180032435
0x18003197b  cmp     cs:?g_fHangRecovery@@3_NA, sil; jumptable 00000001800316D5 cases 161,164,167
0x180031982  jz      def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x180031988  mov     rcx, [r14+118h]; this
0x18003198f  test    rcx, rcx
0x180031992  jz      def_1800316D5; jumptable 00000001800316D5 default case, cases 4,7-9,11,13-15,18,19,23-25,27-35,37-70,72,73,75-82,84-122,124,125,127,135-160,162,163,166
0x180031998  mov     edx, cs:?g_cTabWindow_SyncTMO@@3KA; unsigned int
0x18003199e  call    ?AllUnresponsiveBrowserTabsAreDetached@CTabWindowManager@@QEAA_NK_N@Z; CTabWindowManager::AllUnresponsiveBrowserTabsAreDetached(ulong,bool)
0x1800319a3  test    al, al
0x1800319a5  jz      loc_180031688
0x1800319ab  jmp     loc_180032435
0x1800319b0  mov     rcx, r12; jumptable 00000001800316D5 case 129
0x1800319b3  call    IEDDE_NewWindow
0x1800319b8  jmp     loc_180032435
0x1800319bd  mov     rcx, r14; jumptable 00000001800316D5 case 1
0x1800319c0  call    ?_OnCreate@CBrowserFrame@@IEAAHPEAUHWND__@@@Z; CBrowserFrame::_OnCreate(HWND__ *)
0x1800319c5  test    eax, eax
0x1800319c7  jnz     loc_180031688
0x1800319cd  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800319d4  jmp     loc_180031688
0x1800319d9  xor     r9d, r9d; jumptable 00000001800316D5 case 16
0x1800319dc  mov     edx, 46Ah; Msg
0x1800319e1  mov     rcx, r12; hWnd
0x1800319e4  call    cs:__imp_PostMessageW
0x1800319eb  nop     dword ptr [rax+rax+00h]
0x1800319f0  jmp     loc_180031688
0x1800319f5  mov     rcx, r14; jumptable 00000001800316D5 case 2
0x1800319f8  call    ?_DeleteActivationRecord@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_DeleteActivationRecord(void)
0x1800319fd  jmp     loc_180032435
0x180031a02  mov     rcx, r12; jumptable 00000001800316D5 case 130
0x180031a05  call    IEDDE_WindowDestroyed
0x180031a0a  mov     rcx, r14; this
0x180031a0d  call    ?_OnDestroy@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_OnDestroy(void)
0x180031a12  jmp     loc_180032435
0x180031a17  lea     rax, [rbp+4Fh+var_90]; jumptable 00000001800316D5 case 134
0x180031a1b  mov     r9, r15; unsigned __int64
0x180031a1e  mov     [rsp+0E0h+var_B8], rax; __int64 *
0x180031a23  mov     rdx, r12; hWnd
0x180031a26  mov     rcx, r14; this
0x180031a29  mov     [rsp+0E0h+var_C0], r13; __int64
0x180031a2e  call    ?_OnNCActivate@CBrowserFrame@@IEAA_NPEAUHWND__@@I_K_JPEA_J@Z; CBrowserFrame::_OnNCActivate(HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180031a33  cmp     [r14+3D5h], sil
0x180031a3a  mov     rsi, [rbp+4Fh+var_90]
0x180031a3e  movzx   eax, al
0x180031a41  mov     [rbp+4Fh+var_A0], eax
0x180031a44  jz      loc_180032435
  ... truncated ...
```
