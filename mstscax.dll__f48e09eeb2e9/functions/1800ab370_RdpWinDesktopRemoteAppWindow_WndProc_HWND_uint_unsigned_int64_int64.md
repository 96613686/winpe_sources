# RdpWinDesktopRemoteAppWindow::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800ab370`
- end: `0x1800ac9ff`
- name: `?WndProc@RdpWinDesktopRemoteAppWindow@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `5775`
- prototype: `__int64 __fastcall(RdpWinDesktopRemoteAppWindow *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `0`
- callee_count: `44`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002224`
- `0x180002534`
- `0x180002660`
- `0x18000281c`
- `0x1800186a0`
- `0x180039ce4`
- `0x1800829d4`
- `0x180082ad8`
- `0x180091fc8`
- `0x1800ab370`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800f1b88`
- `0x180111e20`
- `0x18019db40`
- `0x1801bc9c8`
- `0x18024c318`
- `0x18024df6c`
- `0x18024f90c`
- `0x18025098c`
- `0x180251684`
- `0x18025220c`
- `0x180252cc4`
- `0x180252ebc`
- `0x180253154`
- `0x1802532e0`
- `0x1802535dc`
- `0x180253940`
- `0x180253a68`
- `0x180253c14`
- `0x180253ff0`
- `0x1802541d0`
- `0x180254264`
- `0x180254318`
- `0x18025536c`
- `0x1802560c4`
- `0x180257854`
- `0x180258000`
- `0x1802593c8`
- `0x180262654`
- `0x1802633e8`
- `0x18027b7d0`
- `0x18027b98c`
- `0x18068c010`

## import_xrefs

- `USER32!GetCapture` at `0x1800ab983`
- `USER32!GetCapture` at `0x1800abfd2`
- `USER32!GetCapture` at `0x1800ac22f`
- `USER32!GetCapture` at `0x1800ab983`
- `USER32!GetCapture` at `0x1800abfd2`
- `USER32!GetCapture` at `0x1800ac22f`
- `USER32!GetCursorPos` at `0x1800ac75f`
- `USER32!GetCursorPos` at `0x1800ac75f`
- `USER32!TrackMouseEvent` at `0x1800ac074`
- `USER32!TrackMouseEvent` at `0x1800ac074`
- `USER32!DefWindowProcW` at `0x1800ab41a`
- `USER32!DefWindowProcW` at `0x1800abf38`
- `USER32!DefWindowProcW` at `0x1800ab41a`
- `USER32!DefWindowProcW` at `0x1800abf38`
- `USER32!SetCapture` at `0x1800ac23d`
- `USER32!SetCapture` at `0x1800ac23d`
- `USER32!WindowFromPoint` at `0x1800ac771`
- `USER32!WindowFromPoint` at `0x1800ac771`
- `USER32!RemovePropW` at `0x1800abb8a`
- `USER32!RemovePropW` at `0x1800abb8a`
- `USER32!ReleaseCapture` at `0x1800ab98e`
- `USER32!ReleaseCapture` at `0x1800abfdd`
- `USER32!ReleaseCapture` at `0x1800ab98e`
- `USER32!ReleaseCapture` at `0x1800abfdd`

## string_xrefs

- `0x1800ac5d0`: `UpdateServerWithGeometry failed`
- `0x1800ac163`: `WM_SYSCOMMAND`
- `0x1800ab913`: `WM_MOVE`
- `0x1800abe93`: `Trigger IHSyncToggleKeys during typing.`
- `0x1800ac7e5`: `InitializeMonitorConfigObj failed`
- `0x1800ac0b8`: `Ignoring mouse move event and not forwarding input to the IH.`
- `0x1800ac673`: `Entering size move`
- `0x1800ac535`: `WM_EXITSIZEMOVE`
- `0x1800ac8b8`: `AppId is set for HWND, now allow taskbarevents`

## pseudocode

```c
__int64 __fastcall RdpWinDesktopRemoteAppWindow::WndProc(
        RdpWinDesktopRemoteAppWindow *this,
        HWND hWnd,
        unsigned int a3,
        unsigned __int64 a4,
        struct _WINDOW_ACTION *lParam)
{
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  LPARAM v15; // r9
  WPARAM v16; // r8
  HWND v17; // rcx
  char v19; // r12
  LRESULT v20; // rbx
  unsigned __int64 v21; // r8
  char v22; // r15
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct tagPOINT *); // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v25; // eax
  Win32PointerApi *v26; // rcx
  _BOOL8 v27; // rdx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // eax
  __int64 v36; // r9
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  HWND v46; // rbx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  int v68; // ecx
  int v69; // r8d
  int v70; // r9d
  BOOL v71; // r8d
  __int64 v72; // rdx
  HWND v73; // rbx
  __int64 v74; // rcx
  const char *v75; // rax
  __int16 *v76; // rdx
  int v77; // r8d
  int v78; // r9d
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  HWND v82; // rbx
  unsigned __int64 v83; // r14
  unsigned __int64 v84; // r14
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  RdpWinDesktopRemoteAppUIManager *v88; // rcx
  int v89; // edi
  unsigned int v90; // eax
  int v91; // r9d
  bool v92; // dl
  _DWORD *v93; // rbx
  int updated; // esi
  unsigned int v95; // eax
  unsigned int SyncAction; // eax
  int v97; // r9d
  int v98; // ecx
  int v99; // r8d
  int v100; // r9d
  HWND v101; // rax
  int v102; // esi
  unsigned int v103; // eax
  int v104; // ecx
  int v105; // r8d
  int v106; // r9d
  int v107; // ecx
  int v108; // r8d
  int v109; // r9d
  __int64 v110; // r14
  int v111; // r8d
  int v112; // r9d
  int v114[2]; // [rsp+28h] [rbp-59h]
  __int64 v115; // [rsp+50h] [rbp-31h] BYREF
  const char *v116; // [rsp+58h] [rbp-29h] BYREF
  struct tagPOINT Point; // [rsp+60h] [rbp-21h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v119[10]; // [rsp+80h] [rbp-1h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl)
    && !*(_DWORD *)(*((_QWORD *)this + 31) + 424LL)
    && ((a3 - 2) & 0xFFFFFF7F) != 0 )
  {
    if ( (unsigned int)dword_1808B7628 > 5 )
    {
      Point.x = *((_DWORD *)this + 12);
      v10 = *((_QWORD *)this + 15);
      LODWORD(v119[0]) = a3;
      LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(v10 + 48))((char *)this + 120);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)word_180861E8A,
        v12,
        v13,
        (__int64)&v115,
        (__int64)&Point,
        (__int64)v119);
    }
    goto LABEL_6;
  }
  v19 = -1;
  v20 = 0;
  v21 = (unsigned __int64)"WndProc";
  v14 = 2;
  v22 = 1;
  if ( a3 - 581 <= 2 || a3 - 585 <= 1 )
  {
    Point = 0;
    v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct tagPOINT *))*((_QWORD *)this + 21);
    *(_OWORD *)&EventTrack.cbSize = 0;
    LODWORD(v115) = (**v23)(v23, &IID_ITSWin32Input, &Point);
    if ( (int)v115 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          165,
          (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"QI for IID_ITSWin32Input failed",
          v115);
      }
      goto LABEL_17;
    }
    if ( !*(_QWORD *)&Point )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          166,
          (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
          v25,
          (__int64)"spWin32Input");
      }
      goto LABEL_17;
    }
    if ( (*(unsigned int (__fastcall **)(struct tagPOINT, struct tagTRACKMOUSEEVENT *))(**(_QWORD **)&Point + 200LL))(
           Point,
           &EventTrack) )
    {
      v26 = (Win32PointerApi *)*((_QWORD *)this + 156);
      if ( v26 )
      {
        if ( a3 - 585 <= 1 )
        {
          LODWORD(v119[0]) = 0;
          if ( (unsigned int)Win32PointerApi::GetPointerType(
                               v26,
                               (unsigned __int16)a4,
                               (enum tagRDP_POINTER_INPUT_TYPE *)v119) )
          {
            if ( LODWORD(v119[0]) == 2 )
            {
              if ( EventTrack.cbSize )
              {
                if ( a3 == 585 )
                {
                  ++*((_DWORD *)this + 314);
                }
                else if ( a3 == 586 )
                {
                  --*((_DWORD *)this + 314);
                }
              }
            }
            else if ( LODWORD(v119[0]) == 3 && EventTrack.dwFlags )
            {
              if ( a3 == 585 )
              {
                ++*((_DWORD *)this + 315);
              }
              else if ( a3 == 586 )
              {
                --*((_DWORD *)this + 315);
              }
            }
            v27 = *((int *)this + 315) > 0 || *((int *)this + 314) > 0;
            (*(void (__fastcall **)(struct tagPOINT, _BOOL8))(**(_QWORD **)&Point + 248LL))(Point, v27);
          }
        }
      }
    }
    if ( *((_DWORD *)this + 303) )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
        v119[0] = "WndProc";
        v116 = "Ignoring pointer event because we just processed a pointer activate for this window";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)byte_180861EDD,
          v29,
          v30,
          (__int64)&v116,
          (__int64)v119,
          (__int64)&v115);
      }
      *((_DWORD *)this + 303) = 0;
    }
    else if ( (*(unsigned int (__fastcall **)(struct tagPOINT, _QWORD, unsigned __int64, HWND, int))(**(_QWORD **)&Point + 224LL))(
                Point,
                a3,
                a4,
                hWnd,
                1) )
    {
LABEL_17:
      TCntPtr<ITSViewerRecorder>::SafeRelease(&Point);
      return v20;
    }
    TCntPtr<ITSViewerRecorder>::SafeRelease(&Point);
    v21 = (unsigned __int64)"WndProc";
    v14 = 2;
  }
  if ( a3 > 0x105 )
  {
    if ( a3 > 0x20C )
    {
      v21 = 675;
      if ( a3 > 0x2A3 )
      {
        if ( a3 == 787 )
        {
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
            *(_QWORD *)&EventTrack.cbSize = "WM_SYSMENU";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (unsigned int)qword_180861A10,
              v111,
              v112,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          return RdpWinDesktopRemoteAppWindow::OnWmSysMenu(this, (__int64)lParam);
        }
        if ( a3 == 838 )
        {
          RdpWinDesktopRemoteAppWindow::OnWmInterceptedWindowAction(this, lParam);
          return v20;
        }
        if ( a3 != 839 )
        {
          if ( a3 == 1774 )
          {
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
              *(_QWORD *)&EventTrack.cbSize = "WndProc";
              v116 = "WM_SYSMENU";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v107,
                (unsigned int)byte_180861A39,
                v108,
                v109,
                (__int64)&v116,
                (__int64)&EventTrack,
                (__int64)&v115);
            }
            return RdpWinDesktopRemoteAppWindow::OnWmRailUiPropertyChanged(this, a4);
          }
          goto LABEL_274;
        }
        v110 = (a4 >> 1) & 1;
        if ( *((_DWORD *)this + 317) != (_DWORD)v110 )
        {
          *((_DWORD *)this + 317) = v110;
          RdpWinDesktopRemoteAppWindow::SyncCloakedState(this, v110);
        }
        return v20;
      }
      if ( a3 == 675 )
      {
        *((_DWORD *)this + 233) = 0;
        Point = 0;
        if ( !*((_DWORD *)this + 234)
          || !GetCursorPos(&Point)
          || (v101 = WindowFromPoint(Point),
              (unsigned int)WindowsRemoteAppLib::CWinManager::IsRailWindow(
                              *((WindowsRemoteAppLib::CWinManager **)this + 10),
                              v101,
                              0)) )
        {
          LODWORD(v14) = 675;
          goto LABEL_7;
        }
        v115 = 0;
        if ( (unsigned int)RdpWinDesktopRemoteAppWindow::IsTrueMultimonMode(this) )
        {
          v102 = RdpWinDesktopRemoteAppWindow::InitializeMonitorConfigObj(this);
          if ( v102 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v103 = RdpWppGetCurrentThreadActivityIdPrefix();
              v114[0] = v102;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                168,
                (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
                v103,
                (__int64)"InitializeMonitorConfigObj failed",
                *(_QWORD *)v114);
            }
            return v20;
          }
          (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 22) + 176LL))(*((_QWORD *)this + 22), &v115);
        }
        WindowsRemoteAppLib::CRailUi::ForwardToIH(
          this,
          0x200u,
          0,
          (unsigned __int16)v115 | (unsigned __int64)(WORD2(v115) << 16),
          0,
          1);
        return v20;
      }
      if ( a3 != 526 )
      {
        switch ( a3 )
        {
          case 0x216u:
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
              *(_QWORD *)&EventTrack.cbSize = "WndProc";
              v116 = "WM_MOVING";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v98,
                (unsigned int)word_180861D1A,
                v99,
                v100,
                (__int64)&v116,
                (__int64)&EventTrack,
                (__int64)&v115);
            }
            return RdpWinDesktopRemoteAppWindow::OnWmMoving(this, v14, (__int64)lParam);
          case 0x231u:
            if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 192LL))(*((_QWORD *)this + 11)) )
            {
              if ( (unsigned int)dword_1808B5850 > 5 )
              {
                *(_QWORD *)&EventTrack.cbSize = "Entering size move";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_1808B5850,
                  (unsigned int)&byte_180861A9F,
                  0,
                  v97,
                  (__int64)&EventTrack);
              }
              RdpWinDesktopRemoteAppWindow::SetLocalMoveSizeStarted(this);
              RdpWinDesktopRemoteAppWindow::KillLocalMovesizeStartTimer(this);
              LODWORD(v14) = 561;
              goto LABEL_7;
            }
            v92 = 1;
            break;
          case 0x232u:
            if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 192LL))(*((_QWORD *)this + 11)) )
            {
              if ( (unsigned int)dword_1808B5850 > 5 )
              {
                *(_QWORD *)&EventTrack.cbSize = "WM_EXITSIZEMOVE";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_1808B5850,
                  (unsigned int)&word_180861ABE,
                  0,
                  v91,
                  (__int64)&EventTrack);
              }
              v93 = (_DWORD *)((char *)this + 900);
              if ( *((_DWORD *)this + 228) )
              {
                RdpWinDesktopRemoteAppWindow::EndLocalMoveSize(this, 0, 1, 0xFFFFFFFFLL, -1, 2);
              }
              else if ( *v93 )
              {
                updated = RdpWinDesktopRemoteAppWindow::UpdateServerWithGeometry(this, 2);
                if ( updated < 0
                  && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v95 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v114[0] = updated;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    169,
                    (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
                    v95,
                    (__int64)"UpdateServerWithGeometry failed",
                    *(_QWORD *)v114);
                }
              }
              *v93 = 0;
              if ( *((_DWORD *)this + 226) )
              {
                SyncAction = RdpWinDesktopRemoteAppWindow::GetSyncAction(this, 0, 0);
                WindowsRemoteAppLib::CRailUi::ForwardToIH(this, 7u, 0, SyncAction | 4LL, 1, 0);
                *((_DWORD *)this + 226) = 0;
              }
              LODWORD(v14) = 562;
              goto LABEL_7;
            }
            v92 = 0;
            break;
          case 0x24Bu:
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
              *(_QWORD *)&EventTrack.cbSize = "WndProc";
              v116 = "WM_POINTERACTIVATE";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v85,
                (unsigned int)byte_180861E19,
                v86,
                v87,
                (__int64)&v116,
                (__int64)&EventTrack,
                (__int64)&v115);
            }
            v88 = (RdpWinDesktopRemoteAppUIManager *)*((_QWORD *)this + 31);
            v20 = 3;
            *((_DWORD *)this + 303) = 0;
            if ( !(unsigned int)RdpWinDesktopRemoteAppUIManager::IsUsingMultipleVirtualDesktops(v88) )
              return v20;
            if ( (unsigned int)RdpWinDesktopRemoteAppWindow::ShouldActivateOnClickActivation(this) )
            {
              if ( (unsigned int)dword_1808B5850 > 5 )
              {
                *(_QWORD *)&EventTrack.cbSize = "Client is using multiple virtual desktops. Forcing top level window acti"
                                                "vation on pointer activation";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_1808B5850,
                  (unsigned int)&dword_180861E4C,
                  0,
                  v9,
                  (__int64)&EventTrack);
              }
              *((_DWORD *)this + 303) = 1;
              v89 = RdpWinDesktopRemoteAppWindow::SendRailOrderActivate(this, 1);
              if ( v89 < 0
                && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v90 = RdpWppGetCurrentThreadActivityIdPrefix();
                v114[0] = v89;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  167,
                  (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
                  v90,
                  (__int64)"SendRailOrderActivate for top level window on pointer activation failed",
                  *(_QWORD *)v114);
              }
              return v20;
            }
            if ( (unsigned int)dword_1808B5850 <= 5 )
              return v20;
            v75 = "Client is using multiple virtual desktops. Not forcing window activation on pointer activation";
            v76 = (__int16 *)byte_180861E6B;
            goto LABEL_231;
          default:
            goto LABEL_274;
        }
        RdpWinDesktopRemoteAppWindow::OnStartStopMoveSize(this, v92);
        return v20;
      }
    }
    else
    {
      if ( a3 == 524 )
        goto LABEL_154;
      if ( a3 <= 0x204 )
      {
        switch ( a3 )
        {
          case 0x204u:
            goto LABEL_181;
          case 0x112u:
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                                (char *)this + 120,
                                2,
                                "WndProc");
              *(_QWORD *)&EventTrack.cbSize = "WndProc";
              v116 = "WM_SYSCOMMAND";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v79,
                (unsigned int)qword_180861D80,
                v80,
                v81,
                (__int64)&v116,
                (__int64)&EventTrack,
                (__int64)&v115);
            }
            return RdpWinDesktopRemoteAppWindow::OnWmSysCommand(this, 0x112u, a4, (__int64)lParam);
          case 0x113u:
            if ( (unsigned int)dword_1808B5850 > 5 )
            {
              LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                                (char *)this + 120,
                                2,
                                "WndProc");
              *(_QWORD *)&EventTrack.cbSize = "WM_TIMER";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)&byte_1808619E7,
                v77,
                v78,
                (__int64)&EventTrack,
                (__int64)&v115);
            }
            RdpWinDesktopRemoteAppWindow::OnWmTimer(this, a4);
            return v20;
        }
        if ( a3 != 512 )
        {
          if ( a3 != 513 )
          {
            if ( a3 != 514 )
              goto LABEL_274;
            goto LABEL_154;
          }
LABEL_181:
          if ( *((_DWORD *)this + 302) )
          {
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              *(_QWORD *)&EventTrack.cbSize = "WndProc";
              v116 = "Ignoring button down because we just processed a click activate for this window";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                0,
                (unsigned int)qword_180861C58,
                (unsigned int)"WndProc",
                v9,
                (__int64)&v116,
                (__int64)&EventTrack);
            }
            *((_DWORD *)this + 302) = 0;
          }
          else
          {
            if ( *((_DWORD *)this + 228) )
              goto LABEL_6;
            v82 = (HWND)*((_QWORD *)this + 6);
            if ( v82 != GetCapture() )
              SetCapture(v82);
            WindowsRemoteAppLib::CRailUi::ForwardToIH(this, a3, a4, (__int64)lParam, 1, 0);
            v20 = a3 == 523;
            if ( a3 != 513 )
            {
              if ( a3 == 516 )
              {
                v22 = 2;
              }
              else if ( a3 == 519 )
              {
                v22 = 4;
              }
              else
              {
                v83 = a4 >> 16;
                if ( (_WORD)v83 == 1 )
                {
                  v22 = 8;
                }
                else if ( (_WORD)v83 == 2 )
                {
                  v22 = 16;
                }
                else
                {
                  v22 = 0;
                }
              }
            }
            *((_BYTE *)this + 1216) |= v22;
          }
          return v20;
        }
        if ( !*((_DWORD *)this + 233) )
        {
          EventTrack.hwndTrack = (HWND)*((_QWORD *)this + 6);
          *(_QWORD *)&EventTrack.dwHoverTime = 0;
          *((_DWORD *)this + 233) = 1;
          EventTrack.cbSize = 24;
          EventTrack.dwFlags = 2;
          TrackMouseEvent(&EventTrack);
        }
        if ( *((_DWORD *)this + 228) )
        {
          LODWORD(v14) = 512;
          goto LABEL_7;
        }
        if ( !*((_DWORD *)this + 314) && !*((_DWORD *)this + 315) )
        {
          WindowsRemoteAppLib::CRailUi::ForwardToIH(this, 0x200u, a4, (__int64)lParam, 1, 0);
          return v20;
        }
        if ( (unsigned int)dword_1808B5850 <= 5 )
          return v20;
        v75 = "Ignoring mouse move event and not forwarding input to the IH.";
        v76 = word_180861B62;
LABEL_231:
        *(_QWORD *)&EventTrack.cbSize = v75;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1808B5850,
          (_DWORD)v76,
          0,
          v9,
          (__int64)&EventTrack);
        return v20;
      }
      switch ( a3 )
      {
        case 0x205u:
          goto LABEL_154;
        case 0x207u:
          goto LABEL_181;
        case 0x208u:
LABEL_154:
          v73 = (HWND)*((_QWORD *)this + 6);
          if ( v73 == GetCapture() )
            ReleaseCapture();
          v20 = 0;
          if ( *((_DWORD *)this + 228) )
          {
            if ( !*((_DWORD *)this + 229)
              || (v74 = *((_QWORD *)this + 30)) != 0
              && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v74 + 40LL))(v74) != 9 )
            {
              RdpWinDesktopRemoteAppWindow::EndLocalMoveSize(
                this,
                0,
                1,
                (unsigned int)(__int16)lParam,
                SWORD1(lParam),
                1);
            }
          }
          else
          {
            WindowsRemoteAppLib::CRailUi::ForwardToIH(this, a3, a4, (__int64)lParam, 1, 0);
            switch ( a3 )
            {
              case 0x202u:
                v19 = -2;
                break;
              case 0x205u:
                v19 = -3;
                break;
              case 0x208u:
                v19 = -5;
                break;
              default:
                v84 = a4 >> 16;
                if ( (_WORD)v84 == 1 )
                {
                  v19 = -9;
                }
                else if ( (_WORD)v84 == 2 )
                {
                  v19 = -17;
                }
                break;
            }
            *((_BYTE *)this + 1216) &= v19;
          }
          LOBYTE(v20) = a3 == 524;
          return v20;
      }
      if ( a3 != 522 )
      {
        if ( a3 != 523 )
          goto LABEL_274;
        goto LABEL_181;
      }
    }
    v16 = a4;
    v15 = (LPARAM)lParam;
    LODWORD(v14) = a3;
    if ( *((_DWORD *)this + 228) )
      goto LABEL_8;
    WindowsRemoteAppLib::CRailUi::ForwardToIH(this, a3, a4, (__int64)lParam, 0, 0);
    return v20;
  }
  if ( a3 == 261 )
    goto LABEL_129;
  if ( a3 > 0x20 )
  {
    if ( a3 <= 0x83 )
    {
      switch ( a3 )
      {
        case 0x83u:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_NCCALCSIZE";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v68,
              (unsigned int)&dword_180861AFC,
              v69,
              v70,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          break;
        case 0x24u:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_GETMINMAXINFO";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v65,
              (unsigned int)&word_180861DE6,
              v66,
              v67,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          return RdpWinDesktopRemoteAppWindow::OnMinMaxInfo(this, (struct tagMINMAXINFO *)lParam);
        case 0x3Du:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_GETOBJECT";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v62,
              (unsigned int)&dword_180861A6C,
              v63,
              v64,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          return RdpWinDesktopRemoteAppWindow::OnWmGetObject(this, a4, (__int64)lParam);
        case 0x46u:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_WINDOWPOSCHANGING";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v59,
              (unsigned int)&dword_180861CB4,
              v60,
              v61,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, unsigned __int64))(**((_QWORD **)this + 11) + 192LL))(
                  *((_QWORD *)this + 11),
                  v14,
                  v21) )
          {
            LODWORD(v14) = 70;
            goto LABEL_7;
          }
          break;
        case 0x47u:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_WINDOWPOSCHANGED";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v56,
              (unsigned int)&byte_180861CE7,
              v57,
              v58,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          RdpWinDesktopRemoteAppWindow::OnWmWindowPosChanged(this, a4, (__int64)lParam);
          LODWORD(v14) = 71;
          goto LABEL_7;
        case 0x82u:
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                              (char *)this + 120,
                              2,
                              "WndProc");
            *(_QWORD *)&EventTrack.cbSize = "WndProc";
            v116 = "WM_NCDESTROY";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v53,
              (unsigned int)&byte_180861B2F,
              v54,
              v55,
              (__int64)&v116,
              (__int64)&EventTrack,
              (__int64)&v115);
          }
          (*(void (__fastcall **)(RdpWinDesktopRemoteAppWindow *, _QWORD, unsigned __int64))(*(_QWORD *)this + 40LL))(
            this,
            0,
            v21);
          RemovePropW(*((HWND *)this + 6), L"NonRudeHWND");
          break;
        default:
          goto LABEL_274;
      }
      return v20;
    }
    v14 = 132;
    if ( a3 == 132 )
    {
      if ( *((_DWORD *)this + 228) )
        return *((_QWORD *)this + 134);
LABEL_66:
      v15 = (LPARAM)lParam;
      v16 = a4;
      v17 = (HWND)*((_QWORD *)this + 6);
      return DefWindowProcW(v17, v14, v16, v15);
    }
    if ( a3 != 256 && a3 != 257 && a3 != 260 )
    {
LABEL_274:
      if ( a3 == *((_DWORD *)this + 235) )
      {
        (*(void (__fastcall **)(RdpWinDesktopRemoteAppWindow *, __int64, unsigned __int64))(*(_QWORD *)this + 88LL))(
          this,
          v14,
          v21);
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v115) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
          *(_QWORD *)&EventTrack.cbSize = "WndProc";
          v116 = "AppId is set for HWND, now allow taskbarevents";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v104,
            (unsigned int)qword_180861938,
            v105,
            v106,
            (__int64)&v116,
            (__int64)&EventTrack,
            (__int64)&v115);
        }
        *((_DWORD *)this + 286) = 1;
        return v20;
      }
LABEL_6:
      LODWORD(v14) = a3;
LABEL_7:
      v15 = (LPARAM)lParam;
      v16 = a4;
LABEL_8:
      v17 = hWnd;
      return DefWindowProcW(v17, v14, v16, v15);
    }
    if ( ((a3 - 256) & 0xFFFFFFFB) == 0 && *((_DWORD *)this + 227) )
    {
      if ( *((_BYTE *)this + 1216) )
      {
        if ( (unsigned int)dword_1808B5850 > 5 )
        {
          *(_QWORD *)&EventTrack.cbSize = "Delay IHSyncToggleKeys because mouse button is down.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)byte_180861B81,
            0,
            v9,
            (__int64)&EventTrack);
        }
      }
      else
      {
        *((_DWORD *)this + 227) = 0;
        if ( (unsigned int)dword_1808B5850 > 5 )
        {
          *(_QWORD *)&EventTrack.cbSize = "Trigger IHSyncToggleKeys during typing.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)byte_180861ADD,
            0,
            v9,
            (__int64)&EventTrack);
        }
        WindowsRemoteAppLib::CRailUi::ForwardToIH(this, 0x8002u, 0, 0, 1, 0);
        v71 = a4 - 20 > 1 && a4 - 144 > 1;
        *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 12LL) = v71;
      }
    }
LABEL_129:
    if ( *((_DWORD *)this + 228)
      || !*(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 12LL) )
    {
      v20 = DefWindowProcW(hWnd, a3, a4, (LPARAM)lParam);
    }
    else
    {
      WindowsRemoteAppLib::CRailUi::ForwardToIH(this, a3, a4, (__int64)lParam, 1, 0);
    }
    v72 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( !*(_DWORD *)(v72 + 12) && ((a3 - 257) & 0xFFFFFFFB) == 0 )
      *(_DWORD *)(v72 + 12) = 1;
    return v20;
  }
  if ( a3 == 32 )
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                        (char *)this + 120,
                        2,
                        "WndProc");
      *(_QWORD *)&EventTrack.cbSize = "WndProc";
      v116 = "WM_SETCURSOR";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v50,
        (unsigned int)byte_180861BD3,
        v51,
        v52,
        (__int64)&v116,
        (__int64)&EventTrack,
        (__int64)&v115);
    }
    return RdpWinDesktopRemoteAppWindow::OnWmSetCursor(this, 0x20u, a4, (__int64)lParam);
  }
  if ( a3 <= 8 )
  {
    switch ( a3 )
    {
      case 8u:
        goto LABEL_61;
      case 1u:
        return RdpWinDesktopRemoteAppWindow::OnWmCreate(this);
      case 3u:
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                            (char *)this + 120,
                            2,
                            "WndProc");
          v116 = "WndProc";
          Point = (struct tagPOINT)"WM_MOVE";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v43,
            (unsigned int)qword_180861BA0,
            v44,
            v45,
            (__int64)&Point,
            (__int64)&v116,
            (__int64)&v115);
        }
        return RdpWinDesktopRemoteAppWindow::OnWmMove(this, v14, (__int64)lParam);
      case 5u:
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                            (char *)this + 120,
                            2,
                            "WndProc");
          v116 = "WndProc";
          Point = (struct tagPOINT)"WM_SIZE";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v40,
            (unsigned int)byte_180861C81,
            v41,
            v42,
            (__int64)&Point,
            (__int64)&v116,
            (__int64)&v115);
        }
        return RdpWinDesktopRemoteAppWindow::OnWmSize(this, a4, v21);
      case 6u:
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                            (char *)this + 120,
                            2,
                            "WndProc");
          v116 = "WndProc";
          Point = (struct tagPOINT)"WM_ACTIVATE";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v37,
            (unsigned int)byte_180861D4D,
            v38,
            v39,
            (__int64)&Point,
            (__int64)&v116,
            (__int64)&v115);
        }
        return RdpWinDesktopRemoteAppWindow::OnWmActivate(this, 6u, a4, (HWND)lParam);
      case 7u:
LABEL_61:
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v115) = *((_DWORD *)this + 284);
          v31 = *((_QWORD *)this + 15);
          Point.x = a3;
          LODWORD(v119[0]) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(v31 + 48))(
                               (char *)this + 120,
                               2,
                               "WndProc");
          v116 = "WndProc";
          *(_QWORD *)&EventTrack.cbSize = "WM_SETFOCUS/WM_KILLFOCUS";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v32,
            (unsigned int)&word_180861C06,
            v33,
            v34,
            (__int64)&EventTrack,
            (__int64)&v116,
            (__int64)v119,
            (__int64)&Point,
            (__int64)&v115);
        }
        LOBYTE(v20) = a3 == 7;
        v35 = RdpWinDesktopRemoteAppWindow::GetSyncAction(this, v20, (HWND)a4);
        v36 = v35 | 4;
        *((_DWORD *)this + 227) = v20;
        if ( a3 != 7 )
          v36 = v35;
        WindowsRemoteAppLib::CRailUi::ForwardToIH(this, a3, a4, v36, 1, 0);
        WindowsRemoteAppLib::CWinManager::EnforceServerZOrderUnder(
          *((WindowsRemoteAppLib::CWinManager **)this + 10),
          this);
        LODWORD(v14) = a3;
        goto LABEL_66;
    }
    goto LABEL_274;
  }
  switch ( a3 )
  {
    case 0xFu:
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        LODWORD(v115) = (*(__int64 (__fastcall **)(char *, __int64, const char *))(*((_QWORD *)this + 15) + 48LL))(
                          (char *)this + 120,
                          2,
                          "WndProc");
        *(_QWORD *)&EventTrack.cbSize = "WndProc";
        v116 = "WM_PAINT";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v47,
          (unsigned int)byte_180861DB3,
          v48,
          v49,
          (__int64)&v116,
          (__int64)&EventTrack,
          (__int64)&v115);
      }
      return RdpWinDesktopRemoteAppWindow::OnWmPaint(this, v14, v21, v9);
    case 0x10u:
      RdpWinDesktopRemoteAppWindow::OnWmSysCommand(this, 0x112u, 0xF060u, 0);
      return v20;
    case 0x14u:
      return 1;
    case 0x1Au:
      if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)this + 21) + 320LL))(
             *((_QWORD *)this + 21),
             2,
             "WndProc") )
      {
        WindowsRemoteAppLib::CRailUi::ForwardToIH(this, 0x8003u, 0, 0, 1, 0);
      }
      break;
    case 0x1Fu:
      v46 = (HWND)*((_QWORD *)this + 6);
      if ( v46 == GetCapture() )
        ReleaseCapture();
      return 0;
    default:
      goto LABEL_274;
  }
  return v20;
}

```

## disassembly

```asm
0x1800ab370  push    rbp
0x1800ab372  push    rbx
0x1800ab373  push    rsi
0x1800ab374  push    rdi
0x1800ab375  push    r12
0x1800ab377  push    r13
0x1800ab379  push    r14
0x1800ab37b  push    r15
0x1800ab37d  lea     rbp, [rsp-17h]
0x1800ab382  sub     rsp, 98h
0x1800ab389  mov     r14, r9
0x1800ab38c  mov     esi, r8d
0x1800ab38f  mov     r13, rdx
0x1800ab392  mov     rdi, rcx
0x1800ab395  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRailV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2> `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl(void)'::`2'::impl
0x1800ab39c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(void)
0x1800ab3a1  xor     ecx, ecx
0x1800ab3a3  test    al, al
0x1800ab3a5  jz      short loc_1800AB425
0x1800ab3a7  mov     rax, [rdi+0F8h]
0x1800ab3ae  cmp     [rax+1A8h], ecx
0x1800ab3b4  jnz     short loc_1800AB425
0x1800ab3b6  lea     eax, [rsi-2]
0x1800ab3b9  test    eax, 0FFFFFF7Fh
0x1800ab3be  jz      short loc_1800AB425
0x1800ab3c0  mov     eax, cs:dword_1808B7628
0x1800ab3c6  cmp     eax, 5
0x1800ab3c9  jbe     short loc_1800AB40E
0x1800ab3cb  mov     eax, [rdi+30h]
0x1800ab3ce  lea     rcx, [rdi+78h]
0x1800ab3d2  mov     [rbp+4Fh+Point.x], eax
0x1800ab3d5  mov     rax, [rcx]
0x1800ab3d8  mov     dword ptr [rbp+4Fh+var_50], esi
0x1800ab3db  mov     rax, [rax+30h]
0x1800ab3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab3e4  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800ab3e7  lea     rdx, word_180861E8A
0x1800ab3ee  lea     rax, [rbp+4Fh+var_50]
0x1800ab3f2  mov     [rsp+0D0h+var_A0], rax
0x1800ab3f7  lea     rax, [rbp+4Fh+Point]
0x1800ab3fb  mov     qword ptr [rsp+0D0h+var_A8], rax
0x1800ab400  lea     rax, [rbp+4Fh+var_80]
0x1800ab404  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800ab409  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab40e  mov     edx, esi; Msg
0x1800ab410  mov     r9, [rbp+4Fh+lParam]; lParam
0x1800ab414  mov     r8, r14; wParam
0x1800ab417  mov     rcx, r13; hWnd
0x1800ab41a  call    cs:__imp_DefWindowProcW
0x1800ab420  jmp     loc_1800AC9E5
0x1800ab425  or      r12d, 0FFFFFFFFh
0x1800ab429  lea     eax, [rsi-245h]
0x1800ab42f  mov     rbx, rcx
0x1800ab432  lea     r8, aWndproc; "WndProc"
0x1800ab439  lea     edx, [r12+3]
0x1800ab43e  lea     r15d, [r12+2]
0x1800ab443  cmp     eax, edx
0x1800ab445  jbe     short loc_1800AB456
0x1800ab447  lea     eax, [rsi-249h]
0x1800ab44d  cmp     eax, r15d
0x1800ab450  ja      loc_1800AB6CC
0x1800ab456  mov     qword ptr [rbp+4Fh+Point.x], rcx
0x1800ab45a  lea     r8, [rbp+4Fh+Point]
0x1800ab45e  mov     rcx, [rdi+0A8h]
0x1800ab465  lea     rdx, IID_ITSWin32Input
0x1800ab46c  xorps   xmm0, xmm0
0x1800ab46f  movdqu  xmmword ptr [rbp+4Fh+EventTrack.cbSize], xmm0
0x1800ab474  mov     rax, [rcx]
0x1800ab477  mov     rax, [rax]
0x1800ab47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab47f  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800ab482  test    eax, eax
0x1800ab484  jns     short loc_1800AB4EE
0x1800ab486  mov     rdx, cs:WPP_GLOBAL_Control
0x1800ab48d  lea     rcx, WPP_GLOBAL_Control
0x1800ab494  cmp     rdx, rcx
0x1800ab497  jz      short loc_1800AB4E0
0x1800ab499  test    byte ptr [rdx+1Ch], 8
0x1800ab49d  jz      short loc_1800AB4E0
0x1800ab49f  mov     ecx, 2
0x1800ab4a4  cmp     [rdx+19h], cl
0x1800ab4a7  jb      short loc_1800AB4E0
0x1800ab4a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab4ae  mov     ecx, dword ptr [rbp+4Fh+var_80]
0x1800ab4b1  lea     r8, WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids
0x1800ab4b8  mov     [rsp+0D0h+var_A8], ecx
0x1800ab4bc  mov     edx, 0A5h
0x1800ab4c1  lea     rcx, aQiForIidItswin; "QI for IID_ITSWin32Input failed"
0x1800ab4c8  mov     r9d, eax
0x1800ab4cb  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x1800ab4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab4d7  mov     rcx, [rcx+10h]
0x1800ab4db  call    WPP_SF_DsD
0x1800ab4e0  lea     rcx, [rbp+4Fh+Point]; void *
0x1800ab4e4  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1800ab4e9  jmp     loc_1800AC9E8
0x1800ab4ee  mov     rcx, qword ptr [rbp+4Fh+Point.x]
0x1800ab4f2  test    rcx, rcx
0x1800ab4f5  jnz     short loc_1800AB54C
0x1800ab4f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800ab4fe  lea     rcx, WPP_GLOBAL_Control
0x1800ab505  cmp     rax, rcx
0x1800ab508  jz      short loc_1800AB4E0
0x1800ab50a  test    byte ptr [rax+1Ch], 8
0x1800ab50e  jz      short loc_1800AB4E0
0x1800ab510  mov     ecx, 2
0x1800ab515  cmp     [rax+19h], cl
0x1800ab518  jb      short loc_1800AB4E0
0x1800ab51a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ab51f  lea     rcx, aSpwin32input; "spWin32Input"
0x1800ab526  mov     edx, 0A6h
0x1800ab52b  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x1800ab530  lea     r8, WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids
0x1800ab537  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab53e  mov     r9d, eax
0x1800ab541  mov     rcx, [rcx+10h]
0x1800ab545  call    WPP_SF_Ds
0x1800ab54a  jmp     short loc_1800AB4E0
0x1800ab54c  mov     rax, [rcx]
0x1800ab54f  lea     rdx, [rbp+4Fh+EventTrack]
0x1800ab553  mov     rax, [rax+0C8h]
0x1800ab55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab55f  test    eax, eax
0x1800ab561  jz      loc_1800AB624
0x1800ab567  mov     rcx, [rdi+4E0h]; this
0x1800ab56e  test    rcx, rcx
0x1800ab571  jz      loc_1800AB624
0x1800ab577  lea     eax, [rsi-249h]
0x1800ab57d  cmp     eax, r15d
0x1800ab580  ja      loc_1800AB624
0x1800ab586  movzx   edx, r14w; unsigned int
0x1800ab58a  lea     r8, [rbp+4Fh+var_50]; enum tagRDP_POINTER_INPUT_TYPE *
0x1800ab58e  mov     dword ptr [rbp+4Fh+var_50], ebx
0x1800ab591  call    ?GetPointerType@Win32PointerApi@@UEAAHIPEAW4tagRDP_POINTER_INPUT_TYPE@@@Z; Win32PointerApi::GetPointerType(uint,tagRDP_POINTER_INPUT_TYPE *)
0x1800ab596  test    eax, eax
0x1800ab598  jz      loc_1800AB624
0x1800ab59e  mov     ecx, 2
0x1800ab5a3  cmp     dword ptr [rbp+4Fh+var_50], ecx
0x1800ab5a6  jnz     short loc_1800AB5CF
0x1800ab5a8  cmp     [rbp+4Fh+EventTrack.cbSize], ebx
0x1800ab5ab  jz      short loc_1800AB5FA
0x1800ab5ad  cmp     esi, 249h
0x1800ab5b3  jnz     short loc_1800AB5BE
0x1800ab5b5  add     [rdi+4E8h], r15d
0x1800ab5bc  jmp     short loc_1800AB5FA
0x1800ab5be  cmp     esi, 24Ah
0x1800ab5c4  jnz     short loc_1800AB5FA
0x1800ab5c6  add     [rdi+4E8h], r12d
0x1800ab5cd  jmp     short loc_1800AB5FA
0x1800ab5cf  cmp     dword ptr [rbp+4Fh+var_50], 3
0x1800ab5d3  jnz     short loc_1800AB5FA
0x1800ab5d5  cmp     [rbp+4Fh+EventTrack.dwFlags], ebx
0x1800ab5d8  jz      short loc_1800AB5FA
0x1800ab5da  cmp     esi, 249h
0x1800ab5e0  jnz     short loc_1800AB5EB
0x1800ab5e2  add     [rdi+4ECh], r15d
0x1800ab5e9  jmp     short loc_1800AB5FA
0x1800ab5eb  cmp     esi, 24Ah
0x1800ab5f1  jnz     short loc_1800AB5FA
0x1800ab5f3  add     [rdi+4ECh], r12d
0x1800ab5fa  mov     rcx, qword ptr [rbp+4Fh+Point.x]
0x1800ab5fe  mov     rax, [rcx]
0x1800ab601  cmp     [rdi+4ECh], ebx
0x1800ab607  jg      short loc_1800AB615
0x1800ab609  cmp     [rdi+4E8h], ebx
0x1800ab60f  jg      short loc_1800AB615
0x1800ab611  xor     edx, edx
0x1800ab613  jmp     short loc_1800AB618
0x1800ab615  mov     edx, r15d
0x1800ab618  mov     rax, [rax+0F8h]
0x1800ab61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab624  cmp     [rdi+4BCh], ebx
0x1800ab62a  jz      short loc_1800AB68F
0x1800ab62c  mov     eax, cs:dword_1808B5850
0x1800ab632  cmp     eax, 4
0x1800ab635  jbe     short loc_1800AB687
0x1800ab637  lea     rcx, [rdi+78h]
0x1800ab63b  mov     rax, [rcx]
0x1800ab63e  mov     rax, [rax+30h]
0x1800ab642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab647  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800ab64a  lea     rdx, byte_180861EDD
0x1800ab651  lea     rax, aWndproc; "WndProc"
0x1800ab658  mov     [rbp+4Fh+var_50], rax
0x1800ab65c  lea     rax, aIgnoringPointe; "Ignoring pointer event because we just "...
0x1800ab663  mov     [rbp+4Fh+var_78], rax
0x1800ab667  lea     rax, [rbp+4Fh+var_80]
0x1800ab66b  mov     [rsp+0D0h+var_A0], rax
0x1800ab670  lea     rax, [rbp+4Fh+var_50]
0x1800ab674  mov     qword ptr [rsp+0D0h+var_A8], rax
0x1800ab679  lea     rax, [rbp+4Fh+var_78]
0x1800ab67d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800ab682  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ab687  mov     [rdi+4BCh], ebx
0x1800ab68d  jmp     short loc_1800AB6B7
0x1800ab68f  mov     rcx, qword ptr [rbp+4Fh+Point.x]
0x1800ab693  mov     r9, r13
0x1800ab696  mov     r8, r14
0x1800ab699  mov     [rsp+0D0h+var_B0], r15d
0x1800ab69e  mov     edx, esi
0x1800ab6a0  mov     rax, [rcx]
0x1800ab6a3  mov     rax, [rax+0E0h]
0x1800ab6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab6af  test    eax, eax
0x1800ab6b1  jnz     loc_1800AB4E0
0x1800ab6b7  lea     rcx, [rbp+4Fh+Point]; void *
0x1800ab6bb  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1800ab6c0  xor     ecx, ecx
0x1800ab6c2  lea     r8, aWndproc; "WndProc"
0x1800ab6c9  lea     edx, [rcx+2]
0x1800ab6cc  mov     eax, 105h
0x1800ab6d1  cmp     esi, eax
0x1800ab6d3  ja      loc_1800ABF79
0x1800ab6d9  mov     r12d, 0Ch
0x1800ab6df  jz      loc_1800ABE3A
0x1800ab6e5  cmp     esi, 20h ; ' '
0x1800ab6e8  ja      loc_1800ABAD1
0x1800ab6ee  jz      loc_1800ABA5D
0x1800ab6f4  cmp     esi, 8
0x1800ab6f7  ja      loc_1800AB95C
0x1800ab6fd  jz      short loc_1800AB72C
0x1800ab6ff  mov     eax, esi
0x1800ab701  sub     eax, r15d
0x1800ab704  jz      loc_1800AB94F
0x1800ab70a  sub     eax, edx
0x1800ab70c  jz      loc_1800AB8E3
0x1800ab712  sub     eax, edx
0x1800ab714  jz      loc_1800AB878
0x1800ab71a  sub     eax, r15d
0x1800ab71d  jz      loc_1800AB804
0x1800ab723  cmp     eax, r15d
0x1800ab726  jnz     loc_1800AC86D
0x1800ab72c  mov     eax, cs:dword_1808B5850
0x1800ab732  cmp     eax, 4
0x1800ab735  jbe     short loc_1800AB7A5
0x1800ab737  mov     eax, [rdi+470h]
0x1800ab73d  lea     rcx, [rdi+78h]
0x1800ab741  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800ab744  mov     rax, [rcx]
0x1800ab747  mov     [rbp+4Fh+Point.x], esi
0x1800ab74a  mov     rax, [rax+30h]
0x1800ab74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab753  mov     dword ptr [rbp+4Fh+var_50], eax
0x1800ab756  lea     rdx, word_180861C06
0x1800ab75d  lea     rax, aWndproc; "WndProc"
0x1800ab764  mov     [rbp+4Fh+var_78], rax
0x1800ab768  lea     rax, aWmSetfocusWmKi; "WM_SETFOCUS/WM_KILLFOCUS"
0x1800ab76f  mov     qword ptr [rbp+4Fh+EventTrack.cbSize], rax
0x1800ab773  lea     rax, [rbp+4Fh+var_80]
0x1800ab777  mov     [rsp+0D0h+var_90], rax
0x1800ab77c  lea     rax, [rbp+4Fh+Point]
0x1800ab780  mov     [rsp+0D0h+var_98], rax
0x1800ab785  lea     rax, [rbp+4Fh+var_50]
0x1800ab789  mov     [rsp+0D0h+var_A0], rax
0x1800ab78e  lea     rax, [rbp+4Fh+var_78]
0x1800ab792  mov     qword ptr [rsp+0D0h+var_A8], rax
0x1800ab797  lea     rax, [rbp+4Fh+EventTrack]
0x1800ab79b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800ab7a0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab7a5  cmp     esi, 7
0x1800ab7a8  mov     r8, r14; HWND
0x1800ab7ab  mov     rcx, rdi; this
0x1800ab7ae  setz    bl
0x1800ab7b1  mov     edx, ebx; int
0x1800ab7b3  call    ?GetSyncAction@RdpWinDesktopRemoteAppWindow@@AEAAKHPEAUHWND__@@@Z; RdpWinDesktopRemoteAppWindow::GetSyncAction(int,HWND__ *)
0x1800ab7b8  mov     r9d, eax
0x1800ab7bb  mov     [rsp+0D0h+var_A8], 0; int
0x1800ab7c3  or      r9d, 4
0x1800ab7c7  mov     [rdi+38Ch], ebx
0x1800ab7cd  cmp     esi, 7
0x1800ab7d0  mov     [rsp+0D0h+var_B0], r15d; int
0x1800ab7d5  mov     r8, r14; unsigned __int64
0x1800ab7d8  mov     edx, esi; unsigned int
0x1800ab7da  cmovnz  r9d, eax; __int64
0x1800ab7de  mov     rcx, rdi; this
0x1800ab7e1  call    ?ForwardToIH@CRailUi@WindowsRemoteAppLib@@IEAAXI_K_JHH@Z; WindowsRemoteAppLib::CRailUi::ForwardToIH(uint,unsigned __int64,__int64,int,int)
0x1800ab7e6  mov     rcx, [rdi+50h]; this
0x1800ab7ea  mov     rdx, rdi; struct RdpWinDesktopRemoteAppWindow *
0x1800ab7ed  call    ?EnforceServerZOrderUnder@CWinManager@WindowsRemoteAppLib@@QEAAJPEAVRdpWinDesktopRemoteAppWindow@@@Z; WindowsRemoteAppLib::CWinManager::EnforceServerZOrderUnder(RdpWinDesktopRemoteAppWindow *)
0x1800ab7f2  mov     edx, esi
0x1800ab7f4  mov     r9, [rbp+4Fh+lParam]
0x1800ab7f8  mov     r8, r14
0x1800ab7fb  mov     rcx, [rdi+30h]
0x1800ab7ff  jmp     loc_1800AB41A
0x1800ab804  mov     eax, cs:dword_1808B5850
0x1800ab80a  cmp     eax, 4
0x1800ab80d  jbe     short loc_1800AB85F
0x1800ab80f  lea     rcx, [rdi+78h]
0x1800ab813  mov     rax, [rcx]
0x1800ab816  mov     rax, [rax+30h]
0x1800ab81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab81f  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800ab822  lea     rdx, byte_180861D4D
0x1800ab829  lea     rax, aWndproc; "WndProc"
0x1800ab830  mov     [rbp+4Fh+var_78], rax
0x1800ab834  lea     rax, aWmActivate; "WM_ACTIVATE"
0x1800ab83b  mov     qword ptr [rbp+4Fh+Point.x], rax
0x1800ab83f  lea     rax, [rbp+4Fh+var_80]
0x1800ab843  mov     [rsp+0D0h+var_A0], rax
0x1800ab848  lea     rax, [rbp+4Fh+var_78]
  ... truncated ...
```
