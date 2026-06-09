# CTray::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140019eb0`
- end: `0x14001ad98`
- name: `?v_WndProc@CTray@@MEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3816`
- prototype: `__int64 __fastcall(CTray *__hidden this, HWND, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `0`
- callee_count: `58`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14000a79c`
- `0x14000aae8`
- `0x14000ac60`
- `0x14000b628`
- `0x1400112ac`
- `0x140012594`
- `0x140012bd8`
- `0x140012f50`
- `0x140017960`
- `0x1400179d0`
- `0x140018d08`
- `0x140019430`
- `0x140019560`
- `0x140019eb0`
- `0x14001ada0`
- `0x14001b2c8`
- `0x14001db00`
- `0x14001f618`
- `0x140021d1c`
- `0x1400243d4`
- `0x140044a30`
- `0x140044ed0`
- `0x140067560`
- `0x140067890`
- `0x140067f80`
- `0x14006bfb4`
- `0x140079bc0`
- `0x14008581c`
- `0x140087dd4`
- `0x140088360`
- `0x14008a518`
- `0x14008d048`
- `0x14008e470`
- `0x14008fa50`
- `0x140090b10`
- `0x1400a3364`
- `0x1400a5718`
- `0x1400a5884`
- `0x1400a58b8`
- `0x1400abc30`
- `0x1400b1270`
- `0x1400bb5f8`
- `0x1400e1ea8`
- `0x1400fc47c`
- `0x140117570`
- `0x14012bc18`
- `0x14012e4ac`
- `0x14012e840`
- `0x14012eb60`
- `0x14012ef08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a30f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a30f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a278`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001a173`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001a183`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001a173`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001a183`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001a41b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001a4d2`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001a41b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001a4d2`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001a1d0`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001a484`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001a1d0`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001a484`
- `USER32!ExitWindowsEx` at `0x14001aaf5`
- `USER32!ExitWindowsEx` at `0x14001aaf5`
- `USER32!UnregisterHotKey` at `0x14001a717`
- `USER32!UnregisterHotKey` at `0x14001a717`
- `USER32!SetCursor` at `0x14001a59c`
- `USER32!SetCursor` at `0x14001a59c`
- `USER32!LoadCursorW` at `0x14001a58d`
- `USER32!LoadCursorW` at `0x14001a58d`
- `SndVolSSO!__imp_?AudioHIDProcessMessage@@YAXI_K_J@Z` at `0x14001a5ee`
- `SndVolSSO!__imp_?AudioHIDProcessMessage@@YAXI_K_J@Z` at `0x14001a5ee`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14001a32f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14001a32f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001a9cb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001a9cb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001a374`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001a5c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001a374`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001a5c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001a49f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001a4b4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001a49f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001a4b4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DefWindowProcW` at `0x140019f6b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DefWindowProcW` at `0x140019f6b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x14001a87e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x14001a87e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTray::v_WndProc(HWND *this, HWND a2, __int64 a3, unsigned __int64 a4, LPARAM lParam)
{
  unsigned int v6; // ebx
  LPARAM v9; // rdi
  __int64 result; // rax
  struct tagCOPYDATASTRUCT *v11; // rdi
  char *v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rdi
  __int64 updated; // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  LPVOID v19; // rax
  wil::details::in1diag3 *v20; // rcx
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  struct ITrayUIHost *v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rdi
  AppSaver *v26; // rcx
  int v27; // ebx
  HWND v28; // rdi
  int (__fastcall *v29)(HWND, GUID *, GUID *, LPVOID *); // rbx
  HWND v30; // r8
  HCURSOR CursorW; // rax
  __int64 v32; // rdi
  struct ITrayUIHost *v33; // rdx
  struct ITrayUIHost *v34; // rdx
  struct ITrayUIHost *v35; // rdx
  __int64 v36; // rax
  struct ITrayUIHost *v37; // rdx
  struct ITrayUIHost *v38; // rdx
  __int64 uToleranceDelay; // [rsp+20h] [rbp-40h]
  __int64 v40; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v41; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  char v44; // [rsp+A0h] [rbp+40h] BYREF

  v6 = a3;
  v40 = 0;
  if ( (_DWORD)a3 == 74 )
  {
    v11 = (struct tagCOPYDATASTRUCT *)lParam;
    if ( lParam )
    {
      v12 = (char *)(this + 7);
      if ( !this )
        v12 = 0;
      pv[0] = v12;
      if ( v12 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 304LL))(v12);
      if ( !v11->dwData )
      {
        v14 = CTray::_OnAppBarMessage((CTray *)this, v11);
        if ( v12 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 312LL))(v12);
        return v14;
      }
      if ( (*(unsigned __int8 (__fastcall **)(HWND, unsigned __int64, struct tagCOPYDATASTRUCT *, __int64 *))(*(_QWORD *)this[133] + 248LL))(
             this[133],
             a4,
             v11,
             &v40) )
      {
        v13 = v40;
        if ( v12 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 312LL))(v12);
        return v13;
      }
      DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
    }
    return 0;
  }
  if ( (unsigned int)a3 <= 0x111 )
  {
    if ( (_DWORD)a3 == 273 )
    {
      v32 = lParam;
      if ( !(*(unsigned int (__fastcall **)(HWND, HWND, __int64))(*(_QWORD *)this[133] + 272LL))(this[133], a2, 273) )
      {
        v33 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v33 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v33);
        CTray::Command(this + 7, (unsigned __int16)a4, v32, 0, 1);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
      }
      return v40;
    }
    switch ( (int)a3 )
    {
      case 1:
        v23 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v23 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v23);
        v24 = CTray::_OnCreate((CTray *)this);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
        return v24;
      case 2:
        return CTray::_HandleDestroy((CTray *)this, (__int64)&_ImageBase, a3);
      case 16:
LABEL_90:
        v30 = v_hwndDesktop;
        goto LABEL_91;
      case 17:
        if ( (a4 & 1) != 0 )
        {
          if ( !*((_BYTE *)this + 985) )
            CTray::SaveTrayAndDesktop((CTray *)(this + 7));
          v25 = 1;
          if ( !(unsigned int)CTray::_DoExitExplorer(this, 1) )
            return 0;
          CTray::OnEndSessionInitiated((CTray *)this);
          return v25;
        }
        v9 = lParam;
        if ( (lParam & 1) != 0 && AppSaver::IsAppRestartEnabled((AppSaver *)this) && !GetSystemMetrics(67) )
          AppSaver::SaveUwpApps(v26);
        CTray::OnEndSessionInitiated((CTray *)this);
        break;
      case 22:
        v27 = lParam;
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McTemplateU0qq_EventWriteTransfer(this, CTray_EndSession_Info, (unsigned int)a4, (unsigned int)lParam);
        if ( a4 )
        {
          if ( v27 < 0 )
          {
            *((_DWORD *)this + 51) = 1;
            EnumDisplayMonitors(0, 0, CTray::MonitorEnumProc, (LPARAM)this);
          }
          CTray::SaveTrayAndDesktop((CTray *)(this + 7));
          ShowWindow(this[1], 0);
          ShowWindow(v_hwndDesktop, 0);
          if ( !*((_DWORD *)this + 122) )
          {
            if ( GetSystemMetrics(0x2000) )
            {
              v28 = this[70];
              if ( v28 )
              {
                pv[0] = 0;
                v29 = *(int (__fastcall **)(HWND, GUID *, GUID *, LPVOID *))(*(_QWORD *)v28 + 24LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pv);
                if ( v29(v28, &SID_ViewEventDispatcher, &GUID_030de2aa_3f4c_47de_9c7b_0bada6462586, pv) >= 0 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 24LL))(pv[0]);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pv);
              }
            }
            v41 = 0;
            v19 = CoTaskMemAlloc(0x120u);
            if ( !v19 )
              wil::details::in1diag3::FailFastImmediate_Unexpected(v20);
            pv[0] = (LPVOID)tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>(
                              v19,
                              0);
            wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::operator=(
              &v41,
              pv);
            if ( pv[0] )
              tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(pv[0]);
            if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started((char *)v41 + 8) )
            {
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(
                                      &v41,
                                      pv)
                       + 275LL) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(pv);
              tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(&v41);
            }
            ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
            if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
              || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
                  ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
                  (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
            {
              ((void (__fastcall *)(_QWORD))ProcAddress)(0);
            }
            DestroyWindow(this[1]);
            if ( v41 )
              tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(v41);
          }
        }
        else
        {
          *((_BYTE *)this + 984) = 0;
          if ( !*((_BYTE *)this + 985) )
            RemovePropW(this[124], L"IsExplorerShuttingDown");
        }
        return v40;
      case 32:
        if ( !*((_DWORD *)this + 62) )
          goto LABEL_110;
        CursorW = LoadCursorW(0, (LPCWSTR)0x7F8A);
        SetCursor(CursorW);
        return 1;
      case 72:
        goto LABEL_37;
      case 126:
LABEL_124:
        if ( !*((_DWORD *)this + 122) )
        {
          v35 = (struct ITrayUIHost *)(this + 7);
          if ( !this )
            v35 = 0;
          DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v35);
          *((_DWORD *)this + 18) = 1;
          CTray::_HandleDisplayChange((CTray *)this, a2, v6, a4, uToleranceDelay);
          *((_DWORD *)this + 18) = 0;
          DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
        }
        return v40;
      case 130:
        RemovePropW(this[124], L"IsExplorerShuttingDown");
        this[124] = 0;
        return v40;
      case 254:
      case 255:
        if ( *((_DWORD *)this + 58) )
          AudioHIDProcessMessage(a3, a4, lParam);
        return v40;
      default:
        goto LABEL_5;
    }
    return DefWindowProcW(a2, v6, a4, v9);
  }
  if ( (unsigned int)a3 > 0x550 )
  {
    switch ( (int)a3 )
    {
      case 1361:
        CTray::_HandleChangeNotify((CTray *)this, (HANDLE)a4, lParam);
        return v40;
      case 1362:
        SetWindowPos((HWND)a4, 0, 0, 0, 0, 0, 0x13u);
        return v40;
      case 1366:
        goto LABEL_90;
      case 1368:
        CTray::_OnDesktopState((CTray *)this, lParam);
        return v40;
      case 1369:
        CTray::_HandleDelayBootStuff((CTray *)this);
        return v40;
      case 1380:
        CTray::CheckWindowPositions((CTray *)this, a4, a3);
        return v40;
      case 1396:
        CTray::_HandleStartupProgress((CTray *)this, a4, lParam);
        return v40;
      case 1397:
        CTray::_HandlePrivateCommand((CTray *)this, lParam);
        return v40;
      case 1399:
        CTray::_FireDesktopSwitchIfReady(this, 4);
        v36 = *((unsigned int *)this + 168);
        goto LABEL_137;
      case 1400:
        v36 = *((unsigned int *)this + 170);
LABEL_137:
        if ( (_DWORD)v36 )
          CTray::_HandleStartupProgress((CTray *)this, 0, v36);
        return v40;
      case 1401:
        if ( !*((_BYTE *)this + 482) )
          CTray::_RaiseDesktop(this, (unsigned int)a4, a3, a4);
        return v40;
      case 1409:
        if ( *((_DWORD *)this + 118) != (_DWORD)a4 )
        {
          *((_DWORD *)this + 118) = a4;
          *((_DWORD *)this + 51) = 0;
          if ( (_DWORD)a4 )
          {
            UserIdleDetector::EndCheckUserIdle((UserIdleDetector *)(this + 100));
          }
          else
          {
            EnumDisplayMonitors(0, 0, CTray::MonitorEnumProc, (LPARAM)this);
            v16 = UserIdleDetector::BeginCheckUserIdle(this + 100, 0);
            if ( v16 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x15BD,
                (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
                (const char *)(unsigned int)v16,
                uToleranceDelay);
          }
          v17 = LockStateNotifier::NotifyYourPhone(a4 == 0);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x15C4,
              (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
              (const char *)(unsigned int)v17,
              uToleranceDelay);
        }
        return v40;
      case 1410:
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 280LL))(this[133]);
        goto LABEL_148;
      case 1425:
LABEL_148:
        SetCoalescableTimer(this[1], 0x18u, 0x2BF20u, 0, 0x2BF20u);
        break;
      case 1458:
        v37 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v37 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v37);
        CTray::_ApplyRemoteSettings((CTray *)this, a4);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
        return v40;
      case 1460:
        CTray::SaveTrayAndDesktop((CTray *)(this + 7));
        CTray::_DoExitExplorer(this, 2);
        return v40;
      case 1464:
        goto LABEL_124;
      case 1466:
        *((_BYTE *)this + 481) = (_DWORD)a4 != 0;
        return v40;
      case 1467:
        *((_BYTE *)this + 480) = a4 != 0;
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 296LL))(this[133]);
        if ( *((_BYTE *)this + 480) )
        {
          v18 = UserIdleDetector::BeginCheckUserIdle(this + 100, 1);
          if ( v18 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x15EC,
              (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
              (const char *)(unsigned int)v18,
              uToleranceDelay);
        }
        return v40;
      case 1469:
        CTray::_FireDesktopSwitchIfReady(this, 2);
        return v40;
      case 1478:
        return g_fDesktopRaised;
      case 1479:
        v38 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v38 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v38);
        *((_BYTE *)this + 482) = a4 != 0;
        CTray::_UpdateAssignedAccessTaskbarSetting((CTray *)this);
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 304LL))(this[133]);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
        return v40;
      case 1495:
        if ( !*((_DWORD *)this + 122) )
          CTray::OnAppBarThreadTerminated((CTray *)this, (HWND)a4);
        return v40;
      case 1496:
        CTray::_FireDesktopSwitchIfReady(this, 16);
        return v40;
      case 1497:
        CTray::UpdateTrayAndDesktopCloaking((CTray *)this);
        if ( !*((_DWORD *)this + 212) && !*((_BYTE *)this + 605) )
          CTray::_FireDesktopSwitchIfReady(this, 0);
        return v40;
      case 1498:
        CTray::_FireDesktopSwitchIfReady(this, 32);
        return v40;
      default:
        goto LABEL_5;
    }
    return v40;
  }
  if ( (_DWORD)a3 == 1360 )
  {
    v34 = (struct ITrayUIHost *)(this + 7);
    if ( !this )
      v34 = 0;
    DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv, v34);
    CTray::AppBarNotifyAll((CTray *)(this + 7), (HMONITOR)lParam, 1u, (HWND)a4, 0);
    DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)pv);
    return v40;
  }
  if ( (unsigned int)a3 <= 0x40D )
  {
    if ( (_DWORD)a3 != 1037 )
    {
      switch ( (_DWORD)a3 )
      {
        case 0x112:
          if ( (a4 & 0xFFF0) == 0xF060 )
          {
            v30 = v_hwndDesktop;
LABEL_91:
            CTray::_DoExitWindows(this, &v44, v30);
            return v40;
          }
LABEL_110:
          v9 = lParam;
          return DefWindowProcW(a2, v6, a4, v9);
        case 0x113:
          CTray::_HandleTimer((CTray *)this, a4);
          return v40;
        case 0x218:
LABEL_37:
          v9 = lParam;
          (*(void (__fastcall **)(HWND, HWND))(*(_QWORD *)this[133] + 256LL))(this[133], a2);
          CTray::_HandlePowerStatus((CTray *)this, v6, a4, v9);
          return DefWindowProcW(a2, v6, a4, v9);
        case 0x2B1:
          return CTray::_OnSessionChange(this, a4, lParam);
        case 0x312:
          if ( !CTray::_SkipNonKeyboardHotkey((CTray *)this, a4, a3) )
          {
            if ( a4 >= 0x1F4 )
              CTray::_HandleGlobalHotkey((CTray *)this, a4, lParam);
            else
              CTray::_HandleHotKey((CTray *)this, (unsigned __int16)a4);
          }
          return v40;
      }
    }
LABEL_5:
    if ( *((_DWORD *)this + 114) == (_DWORD)a3 )
    {
      ExitWindowsEx(0, 0);
    }
    else if ( *((_DWORD *)this + 152) == (_DWORD)a3 )
    {
      (*(void (__fastcall **)(HWND, _QWORD))(*(_QWORD *)this[133] + 312LL))(this[133], (unsigned int)a4);
    }
    v44 = 0;
    v9 = lParam;
    v40 = (*(__int64 (__fastcall **)(HWND, HWND, _QWORD, unsigned __int64, LPARAM, char *))(*(_QWORD *)this[133] + 32LL))(
            this[133],
            a2,
            v6,
            a4,
            lParam,
            &v44);
    if ( !v44 )
      return v40;
    return DefWindowProcW(a2, v6, a4, v9);
  }
  switch ( (int)a3 )
  {
    case 1253:
      updated = CTray::_UpdateHotkey(
                  (CTray *)this,
                  a2,
                  (const struct _ITEMIDLIST_ABSOLUTE *)a4,
                  (const struct _ITEMIDLIST_ABSOLUTE *)lParam);
      ILFree((LPITEMIDLIST)a4);
      ILFree((LPITEMIDLIST)lParam);
      result = updated;
      break;
    case 1254:
      result = CTray::_RegisterHotkey((CTray *)this, a2, a4);
      break;
    case 1255:
      UnregisterHotKey(a2, a4);
      result = 1;
      break;
    case 1256:
      *((_DWORD *)this + 52) = a4 == 0;
      result = 1;
      break;
    case 1257:
      result = CTray::_ShortcutRegisterHotkey((CTray *)this, (HWND)&_ImageBase, a4, lParam);
      break;
    case 1258:
      result = CTray::_ShortcutUnregisterHotkey((CTray *)this, a2, a4);
      break;
    case 1259:
      return 0;
    case 1262:
      result = CTray::_LoadInProc((CTray *)this, (void *)lParam, a4);
      break;
    case 1263:
      result = CTray::QueryUserNotificationState((CTray *)this);
      break;
    case 1264:
      result = CTray::_HandleDesktopVisibilityChanged((CTray *)this, a4, (void *)lParam);
      break;
    case 1266:
      result = CTray::_ShakeTriggered(this, 2, lParam);
      break;
    case 1267:
      if ( lParam && (HWND)lParam != this[74] )
        this[74] = 0;
      result = this[74] == 0;
      break;
    case 1268:
      CTray::SendNavigationSettingsChange((CTray *)this);
      return v40;
    default:
      goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x140019eb0  mov     [rsp-28h+arg_0], rbx
0x140019eb5  mov     [rsp-28h+arg_8], rsi
0x140019eba  push    rbp
0x140019ebb  push    rdi
0x140019ebc  push    r12
0x140019ebe  push    r14
0x140019ec0  push    r15
0x140019ec2  mov     rbp, rsp
0x140019ec5  sub     rsp, 60h
0x140019ec9  mov     r14, r9
0x140019ecc  mov     ebx, r8d
0x140019ecf  mov     r15, rdx
0x140019ed2  mov     rsi, rcx
0x140019ed5  xor     r12d, r12d
0x140019ed8  mov     [rbp+var_20], r12
0x140019edc  cmp     r8d, 4Ah ; 'J'
0x140019ee0  jz      loc_140019FCD
0x140019ee6  cmp     ebx, 111h
0x140019eec  jbe     loc_14001A057
0x140019ef2  cmp     ebx, 550h
0x140019ef8  jbe     short loc_140019F79
0x140019efa  lea     eax, [r8-551h]; switch 138 cases
0x140019f01  cmp     eax, 89h
0x140019f06  jbe     loc_14001A08B
0x140019f0c  cmp     [rsi+1C8h], ebx; jumptable 000000014001A085 default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x140019f12  jz      loc_14001AAF1
0x140019f18  cmp     [rsi+260h], ebx
0x140019f1e  jz      loc_14001AB06
0x140019f24  mov     [rbp+arg_10], r12b
0x140019f28  mov     rcx, [rsi+428h]
0x140019f2f  mov     rax, [rcx]
0x140019f32  lea     rdx, [rbp+arg_10]
0x140019f36  mov     qword ptr [rsp+60h+cy], rdx
0x140019f3b  mov     rdi, [rbp+lParam]
0x140019f3f  mov     qword ptr [rsp+60h+uToleranceDelay], rdi
0x140019f44  mov     r9, r14
0x140019f47  mov     r8d, ebx
0x140019f4a  mov     rdx, r15
0x140019f4d  mov     rax, [rax+20h]
0x140019f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f56  mov     [rbp+var_20], rax
0x140019f5a  cmp     [rbp+arg_10], r12b
0x140019f5e  jz      short loc_140019FAF
0x140019f60  mov     r9, rdi; lParam
0x140019f63  mov     r8, r14; wParam
0x140019f66  mov     edx, ebx; Msg
0x140019f68  mov     rcx, r15; hWnd
0x140019f6b  call    cs:__imp_DefWindowProcW
0x140019f72  nop     dword ptr [rax+rax+00h]
0x140019f77  jmp     short loc_140019FB3
0x140019f79  jz      loc_14001A7B5
0x140019f7f  cmp     ebx, 40Dh
0x140019f85  ja      loc_14001A137
0x140019f8b  jz      def_14001A085; jumptable 000000014001A085 default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x140019f91  mov     eax, ebx
0x140019f93  sub     eax, 112h
0x140019f98  jz      loc_14001A6D4
0x140019f9e  sub     eax, 1
0x140019fa1  jnz     loc_14001A0F5
0x140019fa7  mov     rdx, r14; unsigned __int64
0x140019faa  call    ?_HandleTimer@CTray@@IEAAX_K@Z; CTray::_HandleTimer(unsigned __int64)
0x140019faf  mov     rax, [rbp+var_20]
0x140019fb3  lea     r11, [rsp+60h+var_s0]
0x140019fb8  mov     rbx, [r11+30h]
0x140019fbc  mov     rsi, [r11+38h]
0x140019fc0  mov     rsp, r11
0x140019fc3  pop     r15
0x140019fc5  pop     r14
0x140019fc7  pop     r12
0x140019fc9  pop     rdi
0x140019fca  pop     rbp
0x140019fcb  retn
0x140019fcd  mov     rdi, [rbp+lParam]
0x140019fd1  test    rdi, rdi
0x140019fd4  jz      loc_14001AB2D; jumptable 000000014001A158 case 1259
0x140019fda  lea     rbx, [rcx+38h]
0x140019fde  test    rsi, rsi
0x140019fe1  cmovz   rbx, r12
0x140019fe5  mov     [rbp+pv], rbx
0x140019fe9  test    rbx, rbx
0x140019fec  jz      short loc_14001A001
0x140019fee  mov     rax, [rbx]
0x140019ff1  mov     rcx, rbx
0x140019ff4  mov     rax, [rax+130h]
0x140019ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a000  nop
0x14001a001  cmp     qword ptr [rdi], 0
0x14001a005  jz      loc_14001A0C7
0x14001a00b  mov     rcx, [rsi+428h]
0x14001a012  mov     rax, [rcx]
0x14001a015  lea     r9, [rbp+var_20]
0x14001a019  mov     r8, rdi
0x14001a01c  mov     rdx, r14
0x14001a01f  mov     rax, [rax+0F8h]
0x14001a026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a02b  test    al, al
0x14001a02d  jz      loc_14001AB24
0x14001a033  mov     rdi, [rbp+var_20]
0x14001a037  test    rbx, rbx
0x14001a03a  jz      short loc_14001A04F
0x14001a03c  mov     rcx, [rbx]
0x14001a03f  mov     rax, [rcx+138h]
0x14001a046  mov     rcx, rbx
0x14001a049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a04e  nop
0x14001a04f  mov     rax, rdi
0x14001a052  jmp     loc_140019FB3
0x14001a057  jz      loc_14001A5FF
0x14001a05d  lea     eax, [r8-1]; switch 255 cases
0x14001a061  cmp     eax, 0FEh
0x14001a066  ja      def_14001A085; jumptable 000000014001A085 default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001a06c  lea     rdx, __ImageBase
0x14001a073  movzx   eax, ds:(byte_14001AB60 - 140000000h)[rdx+rax]
0x14001a07b  mov     ecx, ds:(jpt_14001A085 - 140000000h)[rdx+rax*4]
0x14001a082  add     rcx, rdx; this
0x14001a085  jmp     rcx; switch jump
0x14001a08b  lea     rdx, __ImageBase
0x14001a092  movzx   eax, ds:(byte_14001ACCC - 140000000h)[rdx+rax]
0x14001a09a  mov     ecx, ds:(jpt_14001A0A4 - 140000000h)[rdx+rax*4]
0x14001a0a1  add     rcx, rdx
0x14001a0a4  jmp     rcx; switch jump
0x14001a0aa  cmp     [rsi+1E2h], r12b; jumptable 000000014001A0A4 case 1401
0x14001a0b1  jnz     loc_140019FAF
0x14001a0b7  mov     edx, r14d
0x14001a0ba  mov     rcx, rsi
0x14001a0bd  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x14001a0c2  jmp     loc_140019FAF
0x14001a0c7  mov     rdx, rdi; struct tagCOPYDATASTRUCT *
0x14001a0ca  mov     rcx, rsi; this
0x14001a0cd  call    ?_OnAppBarMessage@CTray@@IEAA_JPEAUtagCOPYDATASTRUCT@@@Z; CTray::_OnAppBarMessage(tagCOPYDATASTRUCT *)
0x14001a0d2  mov     rdi, rax
0x14001a0d5  test    rbx, rbx
0x14001a0d8  jz      short loc_14001A0ED
0x14001a0da  mov     rcx, [rbx]
0x14001a0dd  mov     rax, [rcx+138h]
0x14001a0e4  mov     rcx, rbx
0x14001a0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a0ec  nop
0x14001a0ed  mov     rax, rdi
0x14001a0f0  jmp     loc_140019FB3
0x14001a0f5  sub     eax, 105h
0x14001a0fa  jnz     loc_14001A674
0x14001a100  mov     rcx, [rsi+428h]; jumptable 000000014001A085 case 72
0x14001a107  mov     rax, [rcx]
0x14001a10a  mov     rdi, [rbp+lParam]
0x14001a10e  mov     qword ptr [rsp+60h+uToleranceDelay], rdi
0x14001a113  mov     rdx, r15
0x14001a116  mov     rax, [rax+100h]
0x14001a11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a122  mov     r9, rdi; __int64
0x14001a125  mov     r8, r14; unsigned __int64
0x14001a128  mov     edx, ebx; unsigned int
0x14001a12a  mov     rcx, rsi; this
0x14001a12d  call    ?_HandlePowerStatus@CTray@@IEAAXI_K_J@Z; CTray::_HandlePowerStatus(uint,unsigned __int64,__int64)
0x14001a132  jmp     loc_140019F60
0x14001a137  lea     eax, [r8-4E5h]; switch 16 cases
0x14001a13e  cmp     eax, 0Fh
0x14001a141  ja      def_14001A085; jumptable 000000014001A085 default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001a147  lea     rdx, __ImageBase; HWND
0x14001a14e  mov     eax, ds:(jpt_14001A158 - 140000000h)[rdx+rax*4]
0x14001a155  add     rax, rdx
0x14001a158  jmp     rax; switch jump
0x14001a15e  mov     r9, [rbp+lParam]; jumptable 000000014001A158 case 1253
0x14001a162  mov     r8, r14; struct _ITEMIDLIST_ABSOLUTE *
0x14001a165  mov     rdx, r15; HWND
0x14001a168  call    ?_UpdateHotkey@CTray@@IEAA_JPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@1@Z; CTray::_UpdateHotkey(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x14001a16d  mov     rbx, rax
0x14001a170  mov     rcx, r14; pidl
0x14001a173  call    cs:__imp_ILFree
0x14001a17a  nop     dword ptr [rax+rax+00h]
0x14001a17f  mov     rcx, [rbp+lParam]; pidl
0x14001a183  call    cs:__imp_ILFree
0x14001a18a  nop     dword ptr [rax+rax+00h]
0x14001a18f  mov     rax, rbx
0x14001a192  jmp     loc_140019FB3
0x14001a197  mov     rax, [rbp+lParam]; jumptable 000000014001A158 case 1267
0x14001a19b  test    rax, rax
0x14001a19e  jz      short loc_14001A1B0
0x14001a1a0  cmp     rax, [rcx+250h]
0x14001a1a7  jz      short loc_14001A1B0
0x14001a1a9  mov     [rcx+250h], r12
0x14001a1b0  mov     rax, r12
0x14001a1b3  cmp     [rcx+250h], rax
0x14001a1ba  setz    al
0x14001a1bd  jmp     loc_140019FB3
0x14001a1c2  mov     r9, rsi; dwData
0x14001a1c5  lea     r8, ?MonitorEnumProc@CTray@@KAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x14001a1cc  xor     edx, edx; lprcClip
0x14001a1ce  xor     ecx, ecx; hdc
0x14001a1d0  call    cs:__imp_EnumDisplayMonitors
0x14001a1d7  nop     dword ptr [rax+rax+00h]
0x14001a1dc  xor     edx, edx
0x14001a1de  lea     rcx, [rsi+320h]
0x14001a1e5  call    ?BeginCheckUserIdle@UserIdleDetector@@QEAAJW4CheckUserIdleReason@1@@Z; UserIdleDetector::BeginCheckUserIdle(UserIdleDetector::CheckUserIdleReason)
0x14001a1ea  test    eax, eax
0x14001a1ec  jns     short loc_14001A206
0x14001a1ee  mov     rcx, [rbp+28h]; this
0x14001a1f2  mov     r9d, eax; char *
0x14001a1f5  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001a1fc  mov     edx, 15BDh; void *
0x14001a201  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001a206  mov     ecx, r12d
0x14001a209  test    r14d, r14d
0x14001a20c  setz    cl
0x14001a20f  call    ?NotifyYourPhone@LockStateNotifier@@YAJW4YourPhoneNotificationType@1@@Z; LockStateNotifier::NotifyYourPhone(LockStateNotifier::YourPhoneNotificationType)
0x14001a214  test    eax, eax
0x14001a216  jns     loc_140019FAF
0x14001a21c  mov     rcx, [rbp+28h]; this
0x14001a220  mov     r9d, eax; char *
0x14001a223  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001a22a  mov     edx, 15C4h; void *
0x14001a22f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001a234  jmp     loc_140019FAF
0x14001a239  lea     rcx, [rsi+320h]
0x14001a240  mov     edx, 1
0x14001a245  call    ?BeginCheckUserIdle@UserIdleDetector@@QEAAJW4CheckUserIdleReason@1@@Z; UserIdleDetector::BeginCheckUserIdle(UserIdleDetector::CheckUserIdleReason)
0x14001a24a  test    eax, eax
0x14001a24c  jns     loc_140019FAF
0x14001a252  mov     rcx, [rbp+28h]; this
0x14001a256  mov     r9d, eax; char *
0x14001a259  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001a260  mov     edx, 15ECh; void *
0x14001a265  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001a26a  jmp     loc_140019FAF
0x14001a26f  mov     [rbp+var_18], r12
0x14001a273  mov     ecx, 120h; cb
0x14001a278  call    cs:__imp_CoTaskMemAlloc
0x14001a27f  nop     dword ptr [rax+rax+00h]
0x14001a284  test    rax, rax
0x14001a287  jz      loc_14001A54A
0x14001a28d  xor     edx, edx
0x14001a28f  mov     rcx, rax
0x14001a292  call    ??0?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>(_GUID *)
0x14001a297  mov     [rbp+pv], rax
0x14001a29b  lea     rdx, [rbp+pv]
0x14001a29f  lea     rcx, [rbp+var_18]
0x14001a2a3  call    ??4?$com_ptr_t@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy> &&)
0x14001a2a8  mov     rcx, [rbp+pv]; pv
0x14001a2ac  test    rcx, rcx
0x14001a2af  jz      short loc_14001A2B6
0x14001a2b1  call    ?Release@?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(void)
0x14001a2b6  mov     rcx, [rbp+var_18]
0x14001a2ba  add     rcx, 8
0x14001a2be  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x14001a2c3  test    al, al
0x14001a2c5  jz      short loc_14001A2F0
0x14001a2c7  lea     rdx, [rbp+pv]
0x14001a2cb  lea     rcx, [rbp+var_18]
0x14001a2cf  call    ??C?$tip_test@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(void)
0x14001a2d4  mov     rcx, [rax]
0x14001a2d7  mov     byte ptr [rcx+113h], 1
0x14001a2de  lea     rcx, [rbp+pv]
0x14001a2e2  call    ??1?$test_data_control@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(void)
0x14001a2e7  lea     rcx, [rbp+var_18]
0x14001a2eb  call    ?complete@?$tip_test@V?$merged_data@U_tip_GenericLogonTasksStartToUxShownTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(void)
0x14001a2f0  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x14001a2f7  test    rax, rax
0x14001a2fa  jnz     loc_14001A550
0x14001a300  call    tip_details_GetKernelBaseModuleHandle
0x14001a305  mov     rcx, rax; hModule
0x14001a308  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x14001a30f  call    cs:__imp_GetProcAddress
0x14001a316  nop     dword ptr [rax+rax+00h]
0x14001a31b  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x14001a322  test    rax, rax
0x14001a325  jnz     loc_14001A550
0x14001a32b  mov     rcx, [rsi+8]; hWnd
0x14001a32f  call    cs:__imp_DestroyWindow
0x14001a336  nop     dword ptr [rax+rax+00h]
0x14001a33b  mov     rcx, [rbp+var_18]; pv
0x14001a33f  test    rcx, rcx
0x14001a342  jz      loc_140019FAF
0x14001a348  call    ?Release@?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(void)
0x14001a34d  jmp     loc_140019FAF
0x14001a352  mov     [rsi+3D8h], r12b
0x14001a359  cmp     [rsi+3D9h], r12b
0x14001a360  jnz     loc_140019FAF
0x14001a366  lea     rdx, aIsexplorershut; "IsExplorerShuttingDown"
0x14001a36d  mov     rcx, [rsi+3E0h]; hWnd
0x14001a374  call    cs:__imp_RemovePropW
0x14001a37b  nop     dword ptr [rax+rax+00h]
0x14001a380  jmp     loc_140019FAF
0x14001a385  lea     rdx, [rsi+38h]; jumptable 000000014001A085 case 1
0x14001a389  test    rsi, rsi
0x14001a38c  cmovz   rdx, r12; struct ITrayUIHost *
0x14001a390  lea     rcx, [rbp+pv]; this
0x14001a394  call    ??0DeferWorkAreaChangesGuard@@QEAA@PEAUITrayUIHost@@@Z; DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard(ITrayUIHost *)
0x14001a399  nop
0x14001a39a  mov     rcx, rsi; this
0x14001a39d  call    ?_OnCreate@CTray@@IEAA_JXZ; CTray::_OnCreate(void)
0x14001a3a2  mov     rbx, rax
0x14001a3a5  lea     rcx, [rbp+pv]; this
0x14001a3a9  call    ??1DeferWorkAreaChangesGuard@@QEAA@XZ; DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard(void)
0x14001a3ae  mov     rax, rbx
0x14001a3b1  jmp     loc_140019FB3
0x14001a3b6  mov     rcx, rsi; jumptable 000000014001A085 case 2
0x14001a3b9  call    ?_HandleDestroy@CTray@@IEAA_JXZ; CTray::_HandleDestroy(void)
0x14001a3be  jmp     loc_140019FB3
0x14001a3c3  test    r14b, 1; jumptable 000000014001A085 case 17
0x14001a3c7  jz      short loc_14001A403
  ... truncated ...
```
