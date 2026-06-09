# CUI::UIMainWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180062200`
- end: `0x180063512`
- name: `?UIMainWndProc@CUI@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4882`
- prototype: `__int64 __fastcall(CUI *__hidden this, HWND, UINT Msg, HWND, LPARAM lParam)`
- caller_count: `1`
- callee_count: `38`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180062180`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18005fe84`
- `0x180060180`
- `0x180062200`
- `0x180072290`
- `0x18009defc`
- `0x1800a3fcc`
- `0x1800cff5c`
- `0x1800d011c`
- `0x1800d0210`
- `0x1800ebae0`
- `0x1800f63b8`
- `0x1800f7748`
- `0x1800ff614`
- `0x1800ff654`
- `0x180102240`
- `0x1801023ec`
- `0x180130604`
- `0x1801a7220`
- `0x1803cdfcc`
- `0x1804be3d0`
- `0x1804bf784`
- `0x1804c0d80`
- `0x1804c1e7c`
- `0x1804c4080`
- `0x1804c4550`
- `0x1804c482c`
- `0x1804c50ec`
- `0x1804c51cc`
- `0x1804c53e8`
- `0x1804c9630`
- `0x1804cba48`
- `0x1804edc28`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180062488`
- `KERNEL32!GetLastError` at `0x180062488`
- `GDI32!DeleteObject` at `0x18006250d`
- `GDI32!DeleteObject` at `0x18006250d`
- `GDI32!SelectObject` at `0x1800624d6`
- `GDI32!SelectObject` at `0x180062504`
- `GDI32!SelectObject` at `0x1800624d6`
- `GDI32!SelectObject` at `0x180062504`
- `GDI32!PatBlt` at `0x180062456`
- `GDI32!PatBlt` at `0x180062456`
- `GDI32!Rectangle` at `0x1800624f8`
- `GDI32!Rectangle` at `0x1800624f8`
- `GDI32!CreateSolidBrush` at `0x1800624c7`
- `GDI32!CreateSolidBrush` at `0x1800624c7`
- `GDI32!PtInRegion` at `0x180062d7f`
- `GDI32!PtInRegion` at `0x180062d7f`
- `USER32!MoveWindow` at `0x180062816`
- `USER32!MoveWindow` at `0x180062816`
- `USER32!SetFocus` at `0x180062627`
- `USER32!SetFocus` at `0x180062627`
- `USER32!GetCursorPos` at `0x180062332`
- `USER32!GetCursorPos` at `0x180062d69`
- `USER32!GetCursorPos` at `0x180062332`
- `USER32!GetCursorPos` at `0x180062d69`
- `USER32!EndPaint` at `0x18006251a`
- `USER32!EndPaint` at `0x18006251a`
- `USER32!BeginPaint` at `0x1800623c0`
- `USER32!BeginPaint` at `0x1800623c0`
- `USER32!DefWindowProcW` at `0x180062e07`
- `USER32!DefWindowProcW` at `0x180062e07`
- `USER32!GetWindowRect` at `0x180062eb0`
- `USER32!GetWindowRect` at `0x180062eb0`
- `USER32!KillTimer` at `0x180062360`
- `USER32!KillTimer` at `0x180062cc5`
- `USER32!KillTimer` at `0x180062360`
- `USER32!KillTimer` at `0x180062cc5`
- `USER32!SetWindowPos` at `0x1800628e6`
- `USER32!SetWindowPos` at `0x180062a35`
- `USER32!SetWindowPos` at `0x180062f61`
- `USER32!SetWindowPos` at `0x180063080`
- `USER32!SetWindowPos` at `0x1800628e6`
- `USER32!SetWindowPos` at `0x180062a35`
- `USER32!SetWindowPos` at `0x180062f61`
- `USER32!SetWindowPos` at `0x180063080`
- `USER32!GetWindowLongW` at `0x180062f7b`
- `USER32!GetWindowLongW` at `0x180062f7b`
- `USER32!GetClientRect` at `0x1800623da`
- `USER32!GetClientRect` at `0x180062401`
- `USER32!GetClientRect` at `0x1800623da`
- `USER32!GetClientRect` at `0x180062401`
- `USER32!IsWindowVisible` at `0x1800625c1`
- `USER32!IsWindowVisible` at `0x1800625c1`
- `USER32!GetSysColor` at `0x1800624bf`
- `USER32!GetSysColor` at `0x1800624bf`
- `USER32!GetSystemMenu` at `0x18006325d`
- `USER32!GetSystemMenu` at `0x18006325d`
- `USER32!EnableMenuItem` at `0x1800632da`
- `USER32!EnableMenuItem` at `0x1800632da`
- `USER32!SetWindowPlacement` at `0x1800629f1`
- `USER32!SetWindowPlacement` at `0x1800629f1`
- `USER32!GetWindowPlacement` at `0x18006294c`
- `USER32!GetWindowPlacement` at `0x18006294c`
- `USER32!LockWindowUpdate` at `0x1800628b7`
- `USER32!LockWindowUpdate` at `0x180062930`
- `USER32!LockWindowUpdate` at `0x18006299f`
- `USER32!LockWindowUpdate` at `0x180062a3d`
- `USER32!LockWindowUpdate` at `0x1800628b7`
- `USER32!LockWindowUpdate` at `0x180062930`
- `USER32!LockWindowUpdate` at `0x18006299f`
- `USER32!LockWindowUpdate` at `0x180062a3d`
- `USER32!SetScrollPos` at `0x1800634be`
- `USER32!SetScrollPos` at `0x1800634be`

## pseudocode

```c
LRESULT __fastcall CUI::UIMainWndProc(CUI *this, HWND a2, UINT Msg, HWND a4, LPARAM lParam)
{
  __int64 v9; // r13
  __int64 v10; // rdx
  HKEY v11; // rcx
  __int64 v12; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  UINT v14; // edx
  unsigned int v15; // eax
  HDC v16; // r14
  HWND v17; // rcx
  DWORD LastError; // ebx
  unsigned int v19; // eax
  COLORREF SysColor; // eax
  HBRUSH SolidBrush; // rdi
  HGDIOBJ v22; // rbx
  unsigned int v23; // eax
  __int64 v24; // rcx
  HWND v25; // rdi
  unsigned int v26; // eax
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rcx
  unsigned int v31; // eax
  int v32; // eax
  CUI *v33; // rcx
  int v34; // r8d
  int v35; // r9d
  int v36; // r14d
  HWND v37; // rcx
  COP *v38; // rcx
  __int64 v39; // rcx
  HWND v40; // rcx
  int v41; // edi
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  _QWORD *v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rcx
  unsigned int v48; // eax
  bool v49; // zf
  unsigned int v50; // edx
  unsigned int v51; // eax
  unsigned int v52; // eax
  int v53; // ecx
  unsigned int v54; // eax
  int v55; // ecx
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  __int64 v60; // rcx
  unsigned int v61; // eax
  __int64 v62; // rcx
  int v63; // r14d
  int v64; // r15d
  unsigned int v65; // r12d
  unsigned int v66; // r8d
  unsigned int v67; // ecx
  unsigned int v68; // eax
  unsigned int SystemMetrics; // edi
  unsigned int v70; // esi
  HMONITOR v71; // rax
  unsigned int v72; // ecx
  unsigned int v73; // eax
  int ShouldZoom; // eax
  COP *v75; // r8
  unsigned int v76; // eax
  unsigned int v77; // eax
  __int64 v78; // rdx
  unsigned int v79; // eax
  unsigned int v80; // eax
  HMENU SystemMenu; // rdi
  int IsFullScreen; // eax
  const wchar_t *v83; // rbx
  unsigned int v84; // eax
  unsigned int v85; // eax
  int v86; // eax
  int v87; // ecx
  int v88; // edx
  int v89; // eax
  int v90; // r8d
  int v91; // edx
  unsigned int v92; // eax
  int v93; // eax
  int v94; // ecx
  int v95; // edx
  int v96; // eax
  __int64 v97; // rcx
  int Y[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v100; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT v101; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPOINT Point[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-90h] BYREF
  struct tagMONITORINFO v104; // [rsp+80h] [rbp-80h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+B0h] [rbp-50h] BYREF

  v9 = 0;
  Rect = 0;
  memset_0(&Paint, 0, sizeof(Paint));
  v100 = 0;
  v11 = WPP_GLOBAL_Control;
  LOBYTE(v12) = 5;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
      CurrentThreadActivityIdPrefix,
      Msg);
    v11 = WPP_GLOBAL_Control;
    LOBYTE(v12) = 5;
  }
  v100 = 0;
  if ( Msg > 0x113 )
  {
    if ( Msg != 276 )
    {
      if ( Msg != 277 )
      {
        if ( Msg == 279 )
        {
          SystemMenu = GetSystemMenu(a2, 0);
          if ( SystemMenu )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              IsFullScreen = CUI::UI_IsFullScreen(this);
              v83 = L"TRUE";
              if ( !IsFullScreen )
                v83 = (const wchar_t *)L"FALSE";
              v84 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                (unsigned int)&WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
                v84,
                (__int64)v83);
            }
            EnableMenuItem(SystemMenu, 0xF010u, 1u);
          }
          return v9;
        }
        if ( Msg == 530 )
        {
          if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
          {
            v80 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v80);
          }
          CCD::CD_DecoupleSimpleNotification(
            *((CCD **)this + 340),
            1u,
            this,
            (void (*)(void *, unsigned __int64))CUI::MACROGENERATED_Static_NotifyInputEvent,
            0x212u);
          return v9;
        }
        if ( Msg == 533 )
        {
          if ( !*((_DWORD *)this + 748) )
            return v9;
          if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
          {
            v77 = RdpWppGetCurrentThreadActivityIdPrefix();
            v78 = 32;
            goto LABEL_221;
          }
        }
        else
        {
          if ( Msg == 561 )
          {
            if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
            {
              v79 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v79);
            }
            *((_DWORD *)this + 748) = 1;
            CCD::CD_DecoupleSimpleNotification(
              *((CCD **)this + 340),
              1u,
              this,
              (void (*)(void *, unsigned __int64))CUI::MACROGENERATED_Static_NotifyInputEvent,
              0x231u);
            return v9;
          }
          if ( Msg != 562 )
          {
            if ( Msg == 785 )
            {
              if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
              {
                v76 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v76);
              }
              COP::OnPaletteChanged(*((COP **)this + 341), a2, a4);
            }
            else
            {
              if ( Msg != 32799 )
                goto LABEL_173;
              Y[1] = WORD1(lParam);
              Y[0] = (unsigned __int16)lParam;
              if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
              {
                v61 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DLD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  41,
                  &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
                  v61,
                  (unsigned __int16)lParam,
                  WORD1(lParam));
              }
              if ( !*((_DWORD *)this + 776) )
              {
                v62 = *((_QWORD *)this + 360);
                Point[0].x = 100;
                (*(void (__fastcall **)(__int64, const char *, struct tagPOINT *))(*(_QWORD *)v62 + 96LL))(
                  v62,
                  "ZoomLevel",
                  Point);
                GetWindowRect(*((HWND *)this + 17), &Rect);
                v63 = Rect.right - Rect.left;
                v64 = Rect.bottom - Rect.top;
                v65 = CUI::UICalculateVisibleScrollBars(this, Rect.right - Rect.left, Rect.bottom - Rect.top);
                if ( !(unsigned int)CUI::UI_ShouldZoom(this) )
                {
                  v63 = (unsigned __int16)lParam;
                  v64 = WORD1(lParam);
                }
                v66 = v64 * Point[0].x;
                v67 = v63 * Point[0].x / 0x64u;
                *((_DWORD *)this + 193) = v67;
                *((_DWORD *)this + 195) = v67;
                *((_DWORD *)this + 194) = v66 / 0x64;
                *((_DWORD *)this + 196) = v66 / 0x64;
                CUI::UIRecalcMaxMainWindowSize(this);
                SetWindowPos(*((HWND *)this + 18), 0, 0, 0, *((_DWORD *)this + 193), *((_DWORD *)this + 194), 0x616u);
                CUI::EnsureContainerWindowMatchesOrientation(this);
                if ( (GetWindowLongW(*((HWND *)this + 17), -16) & 0x1000000) == 0 && !v65 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    v68 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      42,
                      &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
                      v68);
                  }
                  SystemMetrics = xGetSystemMetrics(78);
                  v70 = xGetSystemMetrics(79);
                  if ( *((_DWORD *)this + 540) )
                  {
                    memset(&v104, 0, sizeof(v104));
                    if ( xGetSystemMetrics(80) )
                    {
                      v71 = xMonitorFromWindow(*((HWND *)this + 19), 0);
                      if ( v71 )
                      {
                        v104.cbSize = 40;
                        if ( xGetMonitorInfo(v71, &v104) )
                        {
                          SystemMetrics = v104.rcMonitor.right - v104.rcMonitor.left;
                          v70 = v104.rcMonitor.bottom - v104.rcMonitor.top;
                        }
                      }
                    }
                  }
                  v72 = *((_DWORD *)this + 197);
                  v73 = *((_DWORD *)this + 198);
                  if ( v73 >= v70 )
                    v73 = v70;
                  if ( v72 >= SystemMetrics )
                    v72 = SystemMetrics;
                  SetWindowPos(*((HWND *)this + 17), 0, 0, 0, v72, v73, 0x616u);
                  if ( *((_DWORD *)this + 270) )
                  {
                    v101 = *(struct tagRECT *)((char *)this + 1084);
                    CUI::SetCroppedViewRect(this, &v101);
                  }
                }
                CUI::UIRecalculateScrollbars(this);
                v12 = *((_QWORD *)this + 341);
                if ( v12 )
                {
                  ShouldZoom = CUI::UI_ShouldZoom(this);
                  COP::EnableZoom(v75, ShouldZoom);
                }
              }
              CUI::UI_OnDesktopSizeChange(this, *(_QWORD *)Y, v12);
            }
            return v9;
          }
          if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
          {
            v77 = RdpWppGetCurrentThreadActivityIdPrefix();
            v78 = 33;
LABEL_221:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v78, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v77);
          }
        }
        *((_DWORD *)this + 748) = 0;
        CCD::CD_DecoupleSimpleNotification(
          *((CCD **)this + 340),
          1u,
          this,
          (void (*)(void *, unsigned __int64))CUI::MACROGENERATED_Static_NotifyInputEvent,
          0x232u);
        return v9;
      }
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        v85 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v85);
      }
      if ( !(_WORD)a4 )
      {
        *((_DWORD *)this + 202) -= 10;
        goto LABEL_255;
      }
      switch ( (unsigned __int16)a4 )
      {
        case 1u:
          *((_DWORD *)this + 202) += 10;
          goto LABEL_255;
        case 2u:
          *((_DWORD *)this + 202) -= *((_DWORD *)this + 192) >> 1;
          goto LABEL_255;
        case 3u:
          *((_DWORD *)this + 202) += *((_DWORD *)this + 192) >> 1;
          goto LABEL_255;
        case 5u:
          v86 = WORD1(a4);
          break;
        case 6u:
          *((_DWORD *)this + 202) = 0;
          goto LABEL_255;
        case 7u:
          v86 = *((_DWORD *)this + 200);
          break;
        default:
LABEL_255:
          v87 = *((_DWORD *)this + 200);
          v88 = *((_DWORD *)this + 202);
          v89 = v88;
          if ( v88 >= v87 )
            v89 = *((_DWORD *)this + 200);
          if ( v89 >= 0 )
          {
            if ( v88 < v87 )
              v87 = *((_DWORD *)this + 202);
          }
          else
          {
            v87 = 0;
          }
          *((_DWORD *)this + 202) = v87;
          CUI::UIMoveContainerWindow(this);
          v90 = *((_DWORD *)this + 202);
          v91 = 1;
LABEL_288:
          SetScrollPos(a2, v91, v90, 1);
LABEL_289:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowInfoService>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowInfoService>::GetImpl'::`2'::impl) )
          {
            v97 = *((_QWORD *)this + 362);
            if ( v97 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 152LL))(v97);
          }
          return v9;
      }
      *((_DWORD *)this + 202) = v86;
      goto LABEL_255;
    }
    if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    {
      v92 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v92);
    }
    if ( !(_WORD)a4 )
    {
      *((_DWORD *)this + 201) -= 10;
      goto LABEL_281;
    }
    switch ( (unsigned __int16)a4 )
    {
      case 1u:
        *((_DWORD *)this + 201) += 10;
        goto LABEL_281;
      case 2u:
        *((_DWORD *)this + 201) -= *((_DWORD *)this + 191) >> 1;
        goto LABEL_281;
      case 3u:
        *((_DWORD *)this + 201) += *((_DWORD *)this + 191) >> 1;
        goto LABEL_281;
      case 5u:
        v93 = WORD1(a4);
        break;
      case 6u:
        *((_DWORD *)this + 201) = 0;
        goto LABEL_281;
      case 7u:
        v93 = *((_DWORD *)this + 199);
        break;
      default:
LABEL_281:
        v94 = *((_DWORD *)this + 199);
        v95 = *((_DWORD *)this + 201);
        v96 = v95;
        if ( v95 >= v94 )
          v96 = *((_DWORD *)this + 199);
        if ( v96 >= 0 )
        {
          if ( v95 < v94 )
            v94 = *((_DWORD *)this + 201);
        }
        else
        {
          v94 = 0;
        }
        *((_DWORD *)this + 201) = v94;
        CUI::UIMoveContainerWindow(this);
        v90 = *((_DWORD *)this + 201);
        v91 = 0;
        goto LABEL_288;
    }
    *((_DWORD *)this + 201) = v93;
    goto LABEL_281;
  }
  switch ( Msg )
  {
    case 0x113u:
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        v57 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v57, a4);
        v11 = WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)this + 713) )
      {
        if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        {
          v58 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v58, a4);
        }
      }
      else if ( a4 == (HWND)205 )
      {
        KillTimer(a2, 0xCDu);
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v59 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v59);
        }
        v60 = *((_QWORD *)this + 360);
        Point[0].x = 1;
        (*(void (__fastcall **)(__int64, const char *, struct tagPOINT *))(*(_QWORD *)v60 + 120LL))(
          v60,
          "BBarEnabled",
          Point);
        if ( Point[0].x )
        {
          if ( *((_QWORD *)this + 352) )
          {
            *(_QWORD *)Y = 0;
            *((_DWORD *)this + 702) = -4095;
            *((_DWORD *)this + 703) = -4095;
            CUI::UIRecomputeBBarHotzone(this);
            GetCursorPos((LPPOINT)Y);
            if ( PtInRegion(*((HRGN *)this + 352), Y[0], Y[1]) )
              CUI::UI_OnBBarHotzoneTimerFired(this, *(struct tagPOINT *)Y);
          }
        }
      }
      else if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) )
      {
        WPP_SF_I(*((_QWORD *)v11 + 2), 205, v12, a4);
      }
      return v9;
    case 1u:
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v46);
      }
      v47 = *((_QWORD *)this + 345);
      *((_DWORD *)this + 278) = 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v47 + 104LL))(v47, &v100, v12);
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v48 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v48);
      }
      *((_QWORD *)this + 17) = a2;
      if ( !*((_DWORD *)this + 776) )
      {
        if ( *((_DWORD *)this + 540) )
        {
          v52 = xGetSystemMetrics(78);
          v53 = v100;
          if ( (unsigned int)v100 >= v52 )
            v53 = xGetSystemMetrics(78);
          *((_DWORD *)this + 193) = v53;
          v54 = xGetSystemMetrics(79);
          v55 = HIDWORD(v100);
          if ( HIDWORD(v100) >= v54 )
            v55 = xGetSystemMetrics(79);
          *((_DWORD *)this + 194) = v55;
        }
        else
        {
          v49 = (unsigned int)CUI::UI_IsZoomSupported(this) == 0;
          v51 = *((_DWORD *)this + 190);
          if ( v49 )
          {
            if ( (unsigned int)v100 < v50 )
              v50 = v100;
            if ( HIDWORD(v100) < v51 )
              v51 = HIDWORD(v100);
          }
          *((_DWORD *)this + 193) = v50;
          *((_DWORD *)this + 194) = v51;
        }
        CUI::UIRecalcMaxMainWindowSize(this);
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v56 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v56);
      }
      *(_QWORD *)((char *)this + 804) = 0;
      return v9;
    case 2u:
      v14 = 2;
      return DefWindowProcW(a2, v14, (WPARAM)a4, lParam);
    case 5u:
      v28 = *((_DWORD *)this + 278);
      if ( v28 != 1 )
      {
        if ( v28 == 2 && *((_DWORD *)this + 542) )
        {
          CUI::UISuppressScreenUpdate(this, 0);
          *((_DWORD *)this + 542) = 0;
        }
        goto LABEL_76;
      }
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
          v29,
          (__int16)lParam,
          SWORD1(lParam));
      }
      if ( (unsigned __int64)a4 > 2 )
        goto LABEL_76;
      v30 = *((_QWORD *)this + 359);
      Y[0] = 0;
      if ( (*(int (__fastcall **)(__int64, const char *, int *))(*(_QWORD *)v30 + 120LL))(
             v30,
             "SuppressWhenMinimized",
             Y) < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v31);
        }
        goto LABEL_76;
      }
      if ( !Y[0] )
      {
LABEL_76:
        *((_DWORD *)this + 192) = WORD1(lParam);
        *((_DWORD *)this + 191) = (unsigned __int16)lParam;
        v32 = CUI::UI_ShouldZoom(this);
        v36 = v32;
        if ( *((_DWORD *)this + 776) || v32 )
        {
          v37 = (HWND)*((_QWORD *)this + 18);
          *((_DWORD *)this + 194) = v34;
          *((_DWORD *)this + 193) = v35;
          MoveWindow(v37, 0, 0, v35, v34, 1);
        }
        else if ( !*((_DWORD *)this + 777) )
        {
          CUI::EnsureContainerWindowMatchesOrientation(v33);
        }
        v38 = (COP *)*((_QWORD *)this + 341);
        if ( v38 )
          COP::EnableZoom(v38, v36);
        if ( (unsigned int)CUI::UI_IsCoreInitialized(this) )
        {
          CUI::UI_NotifyOfDesktopSizeChange(this, lParam);
          (*(void (__fastcall **)(_QWORD, LPARAM, _QWORD))(**((_QWORD **)this + 369) + 72LL))(
            *((_QWORD *)this + 369),
            lParam,
            0);
        }
        v39 = *((_QWORD *)this + 378);
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
        if ( *((_DWORD *)this + 540) )
        {
          if ( !a4 )
          {
            v40 = (HWND)*((_QWORD *)this + 17);
            Point[0].x = 0;
            Y[0] = 0;
            v41 = CClientUtilsWin32::MonitorTopLeftFromHwnd(v40, (unsigned int *)Point, (unsigned int *)Y);
            LockWindowUpdate(*((HWND *)this + 17));
            if ( v41 < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v42 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
                  v42,
                  v41);
              }
            }
            else
            {
              SetWindowPos(*((HWND *)this + 17), 0, Point[0].x, Y[0], 0, 0, 0x615u);
            }
            LockWindowUpdate(0);
          }
          return v9;
        }
        GetWindowPlacement(*((HWND *)this + 17), (WINDOWPLACEMENT *)this + 16);
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v43);
        }
        if ( a4 == (HWND)2 )
        {
          LockWindowUpdate(*((HWND *)this + 17));
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v44 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v44);
          }
          CUI::UISetMinMaxPlacement(this);
          SetWindowPlacement(*((HWND *)this + 17), (const WINDOWPLACEMENT *)this + 16);
          CUI::UIRecalcMaxMainWindowSize(this);
          v45 = (_QWORD *)CUI::UIGetMaximizedWindowSize(this, Point);
          SetWindowPos(*((HWND *)this + 17), 0, 0, 0, *v45, HIDWORD(*v45), 0x616u);
          LockWindowUpdate(0);
        }
        if ( !*((_DWORD *)this + 707) )
        {
          *((_DWORD *)this + 707) = 1;
          CUI::UIRecalculateScrollbars(this);
          *((_DWORD *)this + 707) = 0;
        }
        goto LABEL_289;
      }
      if ( (_DWORD)lParam )
      {
        if ( a4 != (HWND)2 )
        {
          if ( a4 )
            goto LABEL_75;
          CUI::UIRecomputeBBarHotzone(this);
        }
        if ( *((_DWORD *)this + 542) )
        {
          CUI::UISuppressScreenUpdate(this, 0);
          *((_DWORD *)this + 542) = 0;
        }
        goto LABEL_76;
      }
LABEL_75:
      CUI::UISuppressScreenUpdate(this, 1);
      *((_DWORD *)this + 542) = 1;
      goto LABEL_76;
    case 6u:
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v23);
      }
      if ( !(_WORD)a4 || !*((_QWORD *)this + 18) )
        return v9;
      v24 = *((_QWORD *)this + 378);
      if ( v24 && *((_DWORD *)this + 267) )
      {
        v25 = (HWND)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 72LL))(v24, v10, v12);
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          v27 = 20;
LABEL_56:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v26);
        }
      }
      else
      {
        v25 = 0;
        if ( IsWindowVisible(*((HWND *)this + 18)) )
        {
          v25 = (HWND)*((_QWORD *)this + 18);
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            v27 = 21;
            goto LABEL_56;
          }
        }
      }
      if ( !*((_DWORD *)this + 776) && v25 )
        SetFocus(v25);
      return v9;
    case 0xFu:
      if ( v11 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v11[7] & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v15);
      }
      v16 = BeginPaint(a2, &Paint);
      if ( v16 )
      {
        GetClientRect(a2, &Rect);
        if ( *((_DWORD *)this + 278) == 1 )
        {
          v17 = (HWND)*((_QWORD *)this + 18);
          *(_OWORD *)&Point[0].x = 0;
          GetClientRect(v17, (LPRECT)Point);
          if ( Point[1].x < Rect.right || Point[1].y < Rect.bottom )
          {
            if ( (unsigned int)CUI::UI_IsFullScreen(this) )
            {
              if ( !PatBlt(v16, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x42u)
                && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LastError = GetLastError();
                v19 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  29,
                  &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
                  v19,
                  LastError);
              }
            }
            else
            {
              SysColor = GetSysColor(12);
              SolidBrush = CreateSolidBrush(SysColor);
              v22 = SelectObject(v16, SolidBrush);
              Rectangle(v16, Rect.left, Rect.top, Rect.right, Rect.bottom);
              SelectObject(v16, v22);
              DeleteObject(SolidBrush);
            }
          }
        }
        EndPaint(a2, &Paint);
      }
      break;
    case 0x10u:
      CUI::UI_UserRequestedClose(this);
      break;
    case 0x20u:
      if ( (unsigned int)CUI::UI_IsFullScreen(this) )
      {
        Point[0] = 0;
        GetCursorPos(Point);
        CUI::UISetBBarUnhideTimer(this, Point[0].x, Point[0].y);
      }
      else if ( *((_DWORD *)this + 701) )
      {
        KillTimer(*((HWND *)this + 17), 0xCDu);
        *((_DWORD *)this + 701) = 0;
      }
      v14 = 32;
      return DefWindowProcW(a2, v14, (WPARAM)a4, lParam);
    case 0x111u:
      break;
    case 0x112u:
      v14 = 274;
      return DefWindowProcW(a2, v14, (WPARAM)a4, lParam);
    default:
LABEL_173:
      v14 = Msg;
      return DefWindowProcW(a2, v14, (WPARAM)a4, lParam);
  }
  return v9;
}

```

## disassembly

```asm
0x180062200  push    rbp
0x180062202  push    rbx
0x180062203  push    rsi
0x180062204  push    rdi
0x180062205  push    r12
0x180062207  push    r13
0x180062209  push    r14
0x18006220b  push    r15
0x18006220d  lea     rbp, [rsp-18h]
0x180062212  sub     rsp, 118h
0x180062219  mov     rax, cs:__security_cookie
0x180062220  xor     rax, rsp
0x180062223  mov     [rbp+50h+var_50], rax
0x180062227  xor     r12d, r12d
0x18006222a  mov     r14d, r8d
0x18006222d  mov     rsi, rdx
0x180062230  mov     rbx, rcx
0x180062233  xorps   xmm0, xmm0
0x180062236  lea     rcx, [rbp+50h+Paint]; void *
0x18006223a  xor     edx, edx; Val
0x18006223c  mov     rdi, r9
0x18006223f  lea     r8d, [r12+48h]; Size
0x180062244  mov     r13d, r12d
0x180062247  movups  xmmword ptr [rsp+150h+Rect.left], xmm0
0x18006224c  call    memset_0
0x180062251  mov     [rsp+150h+var_108], r12
0x180062256  mov     rcx, cs:WPP_GLOBAL_Control
0x18006225d  lea     r15, WPP_GLOBAL_Control
0x180062264  mov     r8b, 5
0x180062267  cmp     rcx, r15
0x18006226a  jz      short loc_1800622AB
0x18006226c  test    byte ptr [rcx+1Ch], 1
0x180062270  jz      short loc_1800622AB
0x180062272  cmp     [rcx+19h], r8b
0x180062276  jb      short loc_1800622AB
0x180062278  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006227d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062284  lea     edx, [r12+0Fh]
0x180062289  mov     r9d, eax
0x18006228c  mov     [rsp+150h+h], r14d
0x180062291  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x180062298  mov     rcx, [rcx+10h]
0x18006229c  call    WPP_SF_Dd
0x1800622a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800622a8  mov     r8b, 5
0x1800622ab  mov     eax, 113h
0x1800622b0  mov     [rsp+150h+var_108], r12
0x1800622b5  cmp     r14d, eax
0x1800622b8  ja      loc_180062D9F
0x1800622be  jz      loc_180062BF5
0x1800622c4  mov     eax, r14d
0x1800622c7  sub     eax, 1
0x1800622ca  jz      loc_180062A78
0x1800622d0  sub     eax, 1
0x1800622d3  jz      loc_180062A6E
0x1800622d9  sub     eax, 3
0x1800622dc  jz      loc_180062632
0x1800622e2  sub     eax, 1
0x1800622e5  jz      loc_180062525
0x1800622eb  sub     eax, 9
0x1800622ee  jz      loc_180062384
0x1800622f4  sub     eax, 1
0x1800622f7  jz      short loc_180062377
0x1800622f9  sub     eax, 10h
0x1800622fc  jz      short loc_18006231C
0x1800622fe  sub     eax, 0F1h
0x180062303  jz      loc_1800634EF
0x180062309  cmp     eax, 1
0x18006230c  jnz     loc_180062DF7
0x180062312  mov     edx, 112h
0x180062317  jmp     loc_180062DFA
0x18006231c  mov     rcx, rbx; this
0x18006231f  call    ?UI_IsFullScreen@CUI@@QEAAHXZ; CUI::UI_IsFullScreen(void)
0x180062324  test    eax, eax
0x180062326  jz      short loc_18006234B
0x180062328  lea     rcx, [rsp+150h+Point]; lpPoint
0x18006232d  mov     qword ptr [rsp+150h+Point.x], r12
0x180062332  call    cs:__imp_GetCursorPos
0x180062338  mov     r8d, [rsp+150h+Point.y]; int
0x18006233d  mov     rcx, rbx; this
0x180062340  mov     edx, [rsp+150h+Point.x]; int
0x180062344  call    ?UISetBBarUnhideTimer@CUI@@AEAAXJJ@Z; CUI::UISetBBarUnhideTimer(long,long)
0x180062349  jmp     short loc_18006236D
0x18006234b  cmp     [rbx+0AF4h], r12d
0x180062352  jz      short loc_18006236D
0x180062354  mov     rcx, [rbx+88h]; hWnd
0x18006235b  mov     edx, 0CDh; uIDEvent
0x180062360  call    cs:__imp_KillTimer
0x180062366  mov     [rbx+0AF4h], r12d
0x18006236d  mov     edx, 20h ; ' '
0x180062372  jmp     loc_180062DFA
0x180062377  mov     rcx, rbx; this
0x18006237a  call    ?UI_UserRequestedClose@CUI@@QEAAHXZ; CUI::UI_UserRequestedClose(void)
0x18006237f  jmp     loc_1800634EF
0x180062384  cmp     rcx, r15
0x180062387  jz      short loc_1800623B9
0x180062389  test    byte ptr [rcx+1Ch], 1
0x18006238d  jz      short loc_1800623B9
0x18006238f  cmp     [rcx+19h], r8b
0x180062393  jb      short loc_1800623B9
0x180062395  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006239a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623a1  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1800623a8  mov     edx, 1Ch
0x1800623ad  mov     r9d, eax
0x1800623b0  mov     rcx, [rcx+10h]
0x1800623b4  call    WPP_SF_d
0x1800623b9  lea     rdx, [rbp+50h+Paint]; lpPaint
0x1800623bd  mov     rcx, rsi; hWnd
0x1800623c0  call    cs:__imp_BeginPaint
0x1800623c6  mov     r14, rax
0x1800623c9  test    rax, rax
0x1800623cc  jz      loc_1800634EF
0x1800623d2  lea     rdx, [rsp+150h+Rect]; lpRect
0x1800623d7  mov     rcx, rsi; hWnd
0x1800623da  call    cs:__imp_GetClientRect
0x1800623e0  cmp     dword ptr [rbx+458h], 1
0x1800623e7  jnz     loc_180062513
0x1800623ed  mov     rcx, [rbx+90h]; hWnd
0x1800623f4  lea     rdx, [rsp+150h+Point]; lpRect
0x1800623f9  xorps   xmm0, xmm0
0x1800623fc  movups  xmmword ptr [rsp+150h+Point.x], xmm0
0x180062401  call    cs:__imp_GetClientRect
0x180062407  mov     eax, [rsp+150h+Rect.right]
0x18006240b  cmp     [rsp+150h+Point.x+8], eax
0x18006240f  jl      short loc_18006241F
0x180062411  mov     eax, [rsp+150h+Rect.bottom]
0x180062415  cmp     [rsp+150h+Point.y+8], eax
0x180062419  jge     loc_180062513
0x18006241f  mov     rcx, rbx; this
0x180062422  call    ?UI_IsFullScreen@CUI@@QEAAHXZ; CUI::UI_IsFullScreen(void)
0x180062427  test    eax, eax
0x180062429  jz      loc_1800624BA
0x18006242f  mov     eax, [rsp+150h+Rect.bottom]
0x180062433  mov     rcx, r14; hdc
0x180062436  mov     r8d, [rsp+150h+Rect.top]; y
0x18006243b  sub     eax, r8d
0x18006243e  mov     r9d, [rsp+150h+Rect.right]
0x180062443  mov     edx, [rsp+150h+Rect.left]; x
0x180062447  sub     r9d, edx; w
0x18006244a  mov     [rsp+150h+rop], 42h ; 'B'; rop
0x180062452  mov     [rsp+150h+h], eax; h
0x180062456  call    cs:__imp_PatBlt
0x18006245c  test    eax, eax
0x18006245e  jnz     loc_180062513
0x180062464  mov     rax, cs:WPP_GLOBAL_Control
0x18006246b  cmp     rax, r15
0x18006246e  jz      loc_180062513
0x180062474  test    byte ptr [rax+1Ch], 1
0x180062478  jz      loc_180062513
0x18006247e  cmp     byte ptr [rax+19h], 2
0x180062482  jb      loc_180062513
0x180062488  call    cs:__imp_GetLastError
0x18006248e  mov     ebx, eax
0x180062490  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062495  mov     rcx, cs:WPP_GLOBAL_Control
0x18006249c  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1800624a3  mov     edx, 1Dh
0x1800624a8  mov     [rsp+150h+h], ebx
0x1800624ac  mov     r9d, eax
0x1800624af  mov     rcx, [rcx+10h]
0x1800624b3  call    WPP_SF_Dd
0x1800624b8  jmp     short loc_180062513
0x1800624ba  mov     ecx, 0Ch; nIndex
0x1800624bf  call    cs:__imp_GetSysColor
0x1800624c5  mov     ecx, eax; color
0x1800624c7  call    cs:__imp_CreateSolidBrush
0x1800624cd  mov     rdx, rax; h
0x1800624d0  mov     rcx, r14; hdc
0x1800624d3  mov     rdi, rax
0x1800624d6  call    cs:__imp_SelectObject
0x1800624dc  mov     ecx, [rsp+150h+Rect.bottom]
0x1800624e0  mov     rbx, rax
0x1800624e3  mov     r9d, [rsp+150h+Rect.right]; right
0x1800624e8  mov     r8d, [rsp+150h+Rect.top]; top
0x1800624ed  mov     edx, [rsp+150h+Rect.left]; left
0x1800624f1  mov     [rsp+150h+h], ecx; bottom
0x1800624f5  mov     rcx, r14; hdc
0x1800624f8  call    cs:__imp_Rectangle
0x1800624fe  mov     rdx, rbx; h
0x180062501  mov     rcx, r14; hdc
0x180062504  call    cs:__imp_SelectObject
0x18006250a  mov     rcx, rdi; ho
0x18006250d  call    cs:__imp_DeleteObject
0x180062513  lea     rdx, [rbp+50h+Paint]; lpPaint
0x180062517  mov     rcx, rsi; hWnd
0x18006251a  call    cs:__imp_EndPaint
0x180062520  jmp     loc_1800634EF
0x180062525  cmp     rcx, r15
0x180062528  jz      short loc_18006255A
0x18006252a  test    byte ptr [rcx+1Ch], 1
0x18006252e  jz      short loc_18006255A
0x180062530  cmp     byte ptr [rcx+19h], 4
0x180062534  jb      short loc_18006255A
0x180062536  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006253b  mov     rcx, cs:WPP_GLOBAL_Control
0x180062542  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x180062549  mov     edx, 13h
0x18006254e  mov     r9d, eax
0x180062551  mov     rcx, [rcx+10h]
0x180062555  call    WPP_SF_d
0x18006255a  test    di, di
0x18006255d  jz      loc_1800634EF
0x180062563  mov     rax, [rbx+90h]
0x18006256a  test    rax, rax
0x18006256d  jz      loc_1800634EF
0x180062573  mov     rcx, [rbx+0BD0h]
0x18006257a  test    rcx, rcx
0x18006257d  jz      short loc_1800625BB
0x18006257f  cmp     [rbx+42Ch], r12d
0x180062586  jz      short loc_1800625BB
0x180062588  mov     rax, [rcx]
0x18006258b  mov     rax, [rax+48h]
0x18006258f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062594  mov     rdi, rax
0x180062597  mov     rax, cs:WPP_GLOBAL_Control
0x18006259e  cmp     rax, r15
0x1800625a1  jz      short loc_18006260E
0x1800625a3  test    byte ptr [rax+1Ch], 1
0x1800625a7  jz      short loc_18006260E
0x1800625a9  cmp     byte ptr [rax+19h], 4
0x1800625ad  jb      short loc_18006260E
0x1800625af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800625b4  mov     edx, 14h
0x1800625b9  jmp     short loc_1800625F4
0x1800625bb  mov     rcx, rax; hWnd
0x1800625be  mov     rdi, r12
0x1800625c1  call    cs:__imp_IsWindowVisible
0x1800625c7  test    eax, eax
0x1800625c9  jz      short loc_18006260E
0x1800625cb  mov     rdi, [rbx+90h]
0x1800625d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800625d9  cmp     rax, r15
0x1800625dc  jz      short loc_18006260E
0x1800625de  test    byte ptr [rax+1Ch], 1
0x1800625e2  jz      short loc_18006260E
0x1800625e4  cmp     byte ptr [rax+19h], 4
0x1800625e8  jb      short loc_18006260E
0x1800625ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800625ef  mov     edx, 15h
0x1800625f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800625fb  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x180062602  mov     r9d, eax
0x180062605  mov     rcx, [rcx+10h]
0x180062609  call    WPP_SF_d
0x18006260e  cmp     [rbx+0C20h], r12d
0x180062615  jnz     loc_1800634EF
0x18006261b  test    rdi, rdi
0x18006261e  jz      loc_1800634EF
0x180062624  mov     rcx, rdi; hWnd
0x180062627  call    cs:__imp_SetFocus
0x18006262d  jmp     loc_1800634EF
0x180062632  mov     eax, [rbx+458h]
0x180062638  mov     rsi, [rbp+50h+lParam]
0x18006263f  cmp     eax, 1
0x180062642  jnz     loc_1800627CB
0x180062648  mov     rax, rsi
0x18006264b  movsx   r14d, si
0x18006264f  shr     rax, 10h
0x180062653  movsx   r15d, ax
0x180062657  lea     rdx, WPP_GLOBAL_Control
0x18006265e  cmp     rcx, rdx
0x180062661  jz      short loc_18006269D
0x180062663  test    byte ptr [rcx+1Ch], 1
0x180062667  jz      short loc_18006269D
0x180062669  cmp     [rcx+19h], r8b
0x18006266d  jb      short loc_18006269D
0x18006266f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062674  mov     rcx, cs:WPP_GLOBAL_Control
0x18006267b  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x180062682  mov     edx, 17h
0x180062687  mov     [rsp+150h+rop], r15d
0x18006268c  mov     r9d, eax
0x18006268f  mov     [rsp+150h+h], r14d
0x180062694  mov     rcx, [rcx+10h]
0x180062698  call    WPP_SF_DLD
0x18006269d  mov     rax, rdi
0x1800626a0  test    rdi, rdi
0x1800626a3  jz      short loc_1800626B5
0x1800626a5  sub     rax, 1
0x1800626a9  jz      short loc_1800626B5
0x1800626ab  cmp     rax, 1
0x1800626af  jnz     loc_18006275B
0x1800626b5  mov     rcx, [rbx+0B38h]
0x1800626bc  lea     r8, [rsp+150h+Y]
0x1800626c1  mov     [rsp+150h+Y], r12d
0x1800626c6  lea     rdx, aSuppresswhenmi; "SuppressWhenMinimized"
0x1800626cd  mov     rax, [rcx]
0x1800626d0  mov     rax, [rax+78h]
0x1800626d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626d9  test    eax, eax
0x1800626db  jns     short loc_180062722
0x1800626dd  mov     rax, cs:WPP_GLOBAL_Control
0x1800626e4  lea     r15, WPP_GLOBAL_Control
0x1800626eb  cmp     rax, r15
0x1800626ee  jz      short loc_180062762
0x1800626f0  test    byte ptr [rax+1Ch], 1
0x1800626f4  jz      short loc_180062762
0x1800626f6  cmp     byte ptr [rax+19h], 2
0x1800626fa  jb      short loc_180062762
  ... truncated ...
```
