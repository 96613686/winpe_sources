# CTray::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14001d860`
- end: `0x14001e6cc`
- name: `?v_WndProc@CTray@@MEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3692`
- prototype: `__int64 __fastcall(CTray *__hidden this, HWND, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `0`
- callee_count: `58`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140007048`
- `0x140007aa0`
- `0x14000c8b8`
- `0x14000ca10`
- `0x14000d3a0`
- `0x14000de44`
- `0x14000edcc`
- `0x140013150`
- `0x140014a28`
- `0x14001d860`
- `0x14001e6e0`
- `0x14001eba8`
- `0x14001ecc0`
- `0x14001ef70`
- `0x140022d78`
- `0x1400230ec`
- `0x140023b18`
- `0x140023b90`
- `0x140025574`
- `0x1400258a0`
- `0x140031bd4`
- `0x14004a480`
- `0x14004a730`
- `0x140063d40`
- `0x140063ff0`
- `0x14006560c`
- `0x140067ac0`
- `0x140074ff0`
- `0x14007f8dc`
- `0x140081c8c`
- `0x1400838ec`
- `0x140084610`
- `0x140087db4`
- `0x140088aac`
- `0x14008a15c`
- `0x14008bab4`
- `0x14009bdd8`
- `0x14009c4f4`
- `0x14009c708`
- `0x14009c73c`
- `0x1400a5b40`
- `0x1400ab150`
- `0x1400b555c`
- `0x1400da6b8`
- `0x1400f3e94`
- `0x14012070c`
- `0x140122e8c`
- `0x1401231ec`
- `0x1401234ec`
- `0x1401238cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001db75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001db75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001dc87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001dc87`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001db0c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001db16`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001db0c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14001db16`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001dd9c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001de3b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001dd9c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001de3b`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001dbe5`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001ddff`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001dbe5`
- `api-ms-win-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x14001ddff`
- `USER32!ExitWindowsEx` at `0x14001e42e`
- `USER32!ExitWindowsEx` at `0x14001e42e`
- `USER32!UnregisterHotKey` at `0x14001e062`
- `USER32!UnregisterHotKey` at `0x14001e062`
- `USER32!SetCursor` at `0x14001def9`
- `USER32!SetCursor` at `0x14001def9`
- `USER32!LoadCursorW` at `0x14001def0`
- `USER32!LoadCursorW` at `0x14001def0`
- `SndVolSSO!__imp_?AudioHIDProcessMessage@@YAXI_K_J@Z` at `0x14001df3f`
- `SndVolSSO!__imp_?AudioHIDProcessMessage@@YAXI_K_J@Z` at `0x14001df3f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14001db8f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14001db8f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001e30a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001e30a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001dcfb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001df17`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001dcfb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14001df17`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001de14`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001de23`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001de14`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14001de23`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DefWindowProcW` at `0x14001d91b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DefWindowProcW` at `0x14001d91b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x14001e1c3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x14001e1c3`

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
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  LPVOID v21; // rax
  wil::details::in1diag3 *v22; // rcx
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
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v42[2]; // [rsp+50h] [rbp-10h] BYREF
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
      v42[0] = v12;
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
      DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
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
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v33);
        CTray::Command(this + 7, (unsigned __int16)a4, v32, 0, 1);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
      }
      return v40;
    }
    switch ( (int)a3 )
    {
      case 1:
        v23 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v23 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v23);
        v24 = CTray::_OnCreate((CTray *)this);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
        return v24;
      case 2:
        return CTray::_HandleDestroy((CTray *)this, (__int64)&_ImageBase, a3);
      case 16:
LABEL_92:
        v30 = v_hwndDesktop;
        goto LABEL_93;
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
          McTemplateU0qq_EventWriteTransfer(this, &CTray_EndSession_Info, (unsigned int)a4, (unsigned int)lParam);
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
                v42[0] = 0;
                v29 = *(int (__fastcall **)(HWND, GUID *, GUID *, LPVOID *))(*(_QWORD *)v28 + 24LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
                if ( v29(v28, &SID_ViewEventDispatcher, &GUID_030de2aa_3f4c_47de_9c7b_0bada6462586, v42) >= 0 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v42[0] + 24LL))(v42[0]);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
              }
            }
            pv = 0;
            v21 = CoTaskMemAlloc(0x120u);
            if ( !v21 )
              wil::details::in1diag3::FailFastImmediate_Unexpected(v22);
            v42[0] = (LPVOID)tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>(
                               v21,
                               0);
            wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::operator=(
              &pv,
              v42);
            if ( v42[0] )
              tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(v42[0]);
            if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started((char *)pv + 8) )
            {
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(
                                      &pv,
                                      v42)
                       + 275LL) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(v42);
              if ( pv )
                tip2::details::shared_data<1,0,0>::complete_without_lock((char *)pv + 8);
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
            if ( pv )
              tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(pv);
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
          goto LABEL_112;
        CursorW = LoadCursorW(0, (LPCWSTR)0x7F8A);
        SetCursor(CursorW);
        return 1;
      case 72:
        goto LABEL_37;
      case 126:
LABEL_126:
        if ( !*((_DWORD *)this + 122) )
        {
          v35 = (struct ITrayUIHost *)(this + 7);
          if ( !this )
            v35 = 0;
          DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v35);
          *((_DWORD *)this + 18) = 1;
          CTray::_HandleDisplayChange((CTray *)this, a2, v6, a4, uToleranceDelay);
          *((_DWORD *)this + 18) = 0;
          DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
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
        goto LABEL_92;
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
        goto LABEL_139;
      case 1400:
        v36 = *((unsigned int *)this + 170);
LABEL_139:
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
            v18 = UserIdleDetector::BeginCheckUserIdle(this + 100, 0);
            if ( v18 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x15BD,
                (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
                (const char *)(unsigned int)v18,
                uToleranceDelay);
          }
          v19 = LockStateNotifier::NotifyYourPhone(a4 == 0);
          if ( v19 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x15C4,
              (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
              (const char *)(unsigned int)v19,
              uToleranceDelay);
        }
        return v40;
      case 1410:
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 280LL))(this[133]);
        goto LABEL_150;
      case 1425:
LABEL_150:
        SetCoalescableTimer(this[1], 0x18u, 0x2BF20u, 0, 0x2BF20u);
        break;
      case 1458:
        v37 = (struct ITrayUIHost *)(this + 7);
        if ( !this )
          v37 = 0;
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v37);
        CTray::_ApplyRemoteSettings((CTray *)this, a4);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
        return v40;
      case 1460:
        CTray::SaveTrayAndDesktop((CTray *)(this + 7));
        CTray::_DoExitExplorer(this, 2);
        return v40;
      case 1464:
        goto LABEL_126;
      case 1466:
        *((_BYTE *)this + 481) = (_DWORD)a4 != 0;
        return v40;
      case 1467:
        *((_BYTE *)this + 480) = a4 != 0;
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 296LL))(this[133]);
        if ( *((_BYTE *)this + 480) )
        {
          v20 = UserIdleDetector::BeginCheckUserIdle(this + 100, 1);
          if ( v20 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x15EC,
              (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
              (const char *)(unsigned int)v20,
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
        DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v38);
        *((_BYTE *)this + 482) = a4 != 0;
        CTray::_UpdateAssignedAccessTaskbarSetting((CTray *)this);
        (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 304LL))(this[133]);
        DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
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
    DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42, v34);
    CTray::AppBarNotifyAll((CTray *)(this + 7), (HMONITOR)lParam, 1u, (HWND)a4, 0);
    DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard((DeferWorkAreaChangesGuard *)v42);
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
LABEL_93:
            CTray::_DoExitWindows(this, &v44, v30);
            return v40;
          }
LABEL_112:
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
0x14001d860  mov     [rsp-28h+arg_0], rbx
0x14001d865  mov     [rsp-28h+arg_8], rsi
0x14001d86a  push    rbp
0x14001d86b  push    rdi
0x14001d86c  push    r12
0x14001d86e  push    r14
0x14001d870  push    r15
0x14001d872  mov     rbp, rsp
0x14001d875  sub     rsp, 60h
0x14001d879  mov     r14, r9
0x14001d87c  mov     ebx, r8d
0x14001d87f  mov     r15, rdx
0x14001d882  mov     rsi, rcx
0x14001d885  xor     r12d, r12d
0x14001d888  mov     [rbp+var_20], r12
0x14001d88c  cmp     r8d, 4Ah ; 'J'
0x14001d890  jz      loc_14001D972
0x14001d896  cmp     ebx, 111h
0x14001d89c  jbe     loc_14001D9FC
0x14001d8a2  cmp     ebx, 550h
0x14001d8a8  jbe     short loc_14001D923
0x14001d8aa  lea     eax, [r8-551h]; switch 138 cases
0x14001d8b1  cmp     eax, 89h
0x14001d8b6  jbe     loc_14001DA2C
0x14001d8bc  cmp     [rsi+1C8h], ebx; jumptable 000000014001DA2A default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001d8c2  jz      loc_14001E42A
0x14001d8c8  cmp     [rsi+260h], ebx
0x14001d8ce  jz      loc_14001E439
0x14001d8d4  mov     [rbp+arg_10], r12b
0x14001d8d8  mov     rcx, [rsi+428h]
0x14001d8df  mov     rax, [rcx]
0x14001d8e2  lea     rdx, [rbp+arg_10]
0x14001d8e6  mov     qword ptr [rsp+60h+cy], rdx
0x14001d8eb  mov     rdi, [rbp+lParam]
0x14001d8ef  mov     qword ptr [rsp+60h+uToleranceDelay], rdi
0x14001d8f4  mov     r9, r14
0x14001d8f7  mov     r8d, ebx
0x14001d8fa  mov     rdx, r15
0x14001d8fd  mov     rax, [rax+20h]
0x14001d901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d906  mov     [rbp+var_20], rax
0x14001d90a  cmp     [rbp+arg_10], r12b
0x14001d90e  jz      short loc_14001D955
0x14001d910  mov     r9, rdi; lParam
0x14001d913  mov     r8, r14; wParam
0x14001d916  mov     edx, ebx; Msg
0x14001d918  mov     rcx, r15; hWnd
0x14001d91b  call    cs:__imp_DefWindowProcW
0x14001d921  jmp     short loc_14001D959
0x14001d923  jz      loc_14001E0FA
0x14001d929  cmp     ebx, 40Dh
0x14001d92f  ja      loc_14001DAD4
0x14001d935  jz      short def_14001DA2A; jumptable 000000014001DA2A default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001d937  mov     eax, ebx
0x14001d939  sub     eax, 112h
0x14001d93e  jz      loc_14001E01F
0x14001d944  sub     eax, 1
0x14001d947  jnz     loc_14001DA92
0x14001d94d  mov     rdx, r14; unsigned __int64
0x14001d950  call    ?_HandleTimer@CTray@@IEAAX_K@Z; CTray::_HandleTimer(unsigned __int64)
0x14001d955  mov     rax, [rbp+var_20]
0x14001d959  lea     r11, [rsp+60h+var_s0]
0x14001d95e  mov     rbx, [r11+30h]
0x14001d962  mov     rsi, [r11+38h]
0x14001d966  mov     rsp, r11
0x14001d969  pop     r15
0x14001d96b  pop     r14
0x14001d96d  pop     r12
0x14001d96f  pop     rdi
0x14001d970  pop     rbp
0x14001d971  retn
0x14001d972  mov     rdi, [rbp+lParam]
0x14001d976  test    rdi, rdi
0x14001d979  jz      loc_14001E460; jumptable 000000014001DAF5 case 1259
0x14001d97f  lea     rbx, [rcx+38h]
0x14001d983  test    rsi, rsi
0x14001d986  cmovz   rbx, r12
0x14001d98a  mov     [rbp+var_10], rbx
0x14001d98e  test    rbx, rbx
0x14001d991  jz      short loc_14001D9A6
0x14001d993  mov     rax, [rbx]
0x14001d996  mov     rcx, rbx
0x14001d999  mov     rax, [rax+130h]
0x14001d9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d9a5  nop
0x14001d9a6  cmp     qword ptr [rdi], 0
0x14001d9aa  jz      loc_14001DA64
0x14001d9b0  mov     rcx, [rsi+428h]
0x14001d9b7  mov     rax, [rcx]
0x14001d9ba  lea     r9, [rbp+var_20]
0x14001d9be  mov     r8, rdi
0x14001d9c1  mov     rdx, r14
0x14001d9c4  mov     rax, [rax+0F8h]
0x14001d9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d9d0  test    al, al
0x14001d9d2  jz      loc_14001E457
0x14001d9d8  mov     rdi, [rbp+var_20]
0x14001d9dc  test    rbx, rbx
0x14001d9df  jz      short loc_14001D9F4
0x14001d9e1  mov     rcx, [rbx]
0x14001d9e4  mov     rax, [rcx+138h]
0x14001d9eb  mov     rcx, rbx
0x14001d9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d9f3  nop
0x14001d9f4  mov     rax, rdi
0x14001d9f7  jmp     loc_14001D959
0x14001d9fc  jz      loc_14001DF4A
0x14001da02  lea     eax, [r8-1]; switch 255 cases
0x14001da06  cmp     eax, 0FEh
0x14001da0b  ja      def_14001DA2A; jumptable 000000014001DA2A default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001da11  lea     rdx, __ImageBase
0x14001da18  movzx   eax, ds:(byte_14001E494 - 140000000h)[rdx+rax]
0x14001da20  mov     ecx, ds:(jpt_14001DA2A - 140000000h)[rdx+rax*4]
0x14001da27  add     rcx, rdx; this
0x14001da2a  jmp     rcx; switch jump
0x14001da2c  lea     rdx, __ImageBase
0x14001da33  movzx   eax, ds:(byte_14001E600 - 140000000h)[rdx+rax]
0x14001da3b  mov     ecx, ds:(jpt_14001DA45 - 140000000h)[rdx+rax*4]
0x14001da42  add     rcx, rdx
0x14001da45  jmp     rcx; switch jump
0x14001da47  cmp     [rsi+1E2h], r12b; jumptable 000000014001DA45 case 1401
0x14001da4e  jnz     loc_14001D955
0x14001da54  mov     edx, r14d
0x14001da57  mov     rcx, rsi
0x14001da5a  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x14001da5f  jmp     loc_14001D955
0x14001da64  mov     rdx, rdi; struct tagCOPYDATASTRUCT *
0x14001da67  mov     rcx, rsi; this
0x14001da6a  call    ?_OnAppBarMessage@CTray@@IEAA_JPEAUtagCOPYDATASTRUCT@@@Z; CTray::_OnAppBarMessage(tagCOPYDATASTRUCT *)
0x14001da6f  mov     rdi, rax
0x14001da72  test    rbx, rbx
0x14001da75  jz      short loc_14001DA8A
0x14001da77  mov     rcx, [rbx]
0x14001da7a  mov     rax, [rcx+138h]
0x14001da81  mov     rcx, rbx
0x14001da84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da89  nop
0x14001da8a  mov     rax, rdi
0x14001da8d  jmp     loc_14001D959
0x14001da92  sub     eax, 105h
0x14001da97  jnz     loc_14001DFBF
0x14001da9d  mov     rcx, [rsi+428h]; jumptable 000000014001DA2A case 72
0x14001daa4  mov     rax, [rcx]
0x14001daa7  mov     rdi, [rbp+lParam]
0x14001daab  mov     qword ptr [rsp+60h+uToleranceDelay], rdi
0x14001dab0  mov     rdx, r15
0x14001dab3  mov     rax, [rax+100h]
0x14001daba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dabf  mov     r9, rdi; __int64
0x14001dac2  mov     r8, r14; unsigned __int64
0x14001dac5  mov     edx, ebx; unsigned int
0x14001dac7  mov     rcx, rsi; this
0x14001daca  call    ?_HandlePowerStatus@CTray@@IEAAXI_K_J@Z; CTray::_HandlePowerStatus(uint,unsigned __int64,__int64)
0x14001dacf  jmp     loc_14001D910
0x14001dad4  lea     eax, [r8-4E5h]; switch 16 cases
0x14001dadb  cmp     eax, 0Fh
0x14001dade  ja      def_14001DA2A; jumptable 000000014001DA2A default case, cases 3-15,18-21,23-31,33-71,73-125,127-129,131-253
0x14001dae4  lea     rdx, __ImageBase; HWND
0x14001daeb  mov     eax, ds:(jpt_14001DAF5 - 140000000h)[rdx+rax*4]
0x14001daf2  add     rax, rdx
0x14001daf5  jmp     rax; switch jump
0x14001daf7  mov     r9, [rbp+lParam]; jumptable 000000014001DAF5 case 1253
0x14001dafb  mov     r8, r14; struct _ITEMIDLIST_ABSOLUTE *
0x14001dafe  mov     rdx, r15; HWND
0x14001db01  call    ?_UpdateHotkey@CTray@@IEAA_JPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@1@Z; CTray::_UpdateHotkey(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x14001db06  mov     rbx, rax
0x14001db09  mov     rcx, r14; pidl
0x14001db0c  call    cs:__imp_ILFree
0x14001db12  mov     rcx, [rbp+lParam]; pidl
0x14001db16  call    cs:__imp_ILFree
0x14001db1c  mov     rax, rbx
0x14001db1f  jmp     loc_14001D959
0x14001db24  lea     rdx, [rbp+var_10]
0x14001db28  lea     rcx, [rbp+pv]
0x14001db2c  call    ??C?$tip_test@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(void)
0x14001db31  mov     rcx, [rax]
0x14001db34  mov     byte ptr [rcx+113h], 1
0x14001db3b  lea     rcx, [rbp+var_10]
0x14001db3f  call    ??1?$test_data_control@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(void)
0x14001db44  mov     rcx, [rbp+pv]
0x14001db48  test    rcx, rcx
0x14001db4b  jz      short loc_14001DB56
0x14001db4d  add     rcx, 8
0x14001db51  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x14001db56  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x14001db5d  test    rax, rax
0x14001db60  jnz     loc_14001DEB3
0x14001db66  call    tip_details_GetKernelBaseModuleHandle
0x14001db6b  mov     rcx, rax; hModule
0x14001db6e  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x14001db75  call    cs:__imp_GetProcAddress
0x14001db7b  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x14001db82  test    rax, rax
0x14001db85  jnz     loc_14001DEB3
0x14001db8b  mov     rcx, [rsi+8]; hWnd
0x14001db8f  call    cs:__imp_DestroyWindow
0x14001db95  mov     rcx, [rbp+pv]; pv
0x14001db99  test    rcx, rcx
0x14001db9c  jz      loc_14001D955
0x14001dba2  call    ?Release@?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(void)
0x14001dba7  jmp     loc_14001D955
0x14001dbac  mov     rax, [rbp+lParam]; jumptable 000000014001DAF5 case 1267
0x14001dbb0  test    rax, rax
0x14001dbb3  jz      short loc_14001DBC5
0x14001dbb5  cmp     rax, [rcx+250h]
0x14001dbbc  jz      short loc_14001DBC5
0x14001dbbe  mov     [rcx+250h], r12
0x14001dbc5  mov     rax, r12
0x14001dbc8  cmp     [rcx+250h], rax
0x14001dbcf  setz    al
0x14001dbd2  jmp     loc_14001D959
0x14001dbd7  mov     r9, rsi; dwData
0x14001dbda  lea     r8, ?MonitorEnumProc@CTray@@KAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x14001dbe1  xor     edx, edx; lprcClip
0x14001dbe3  xor     ecx, ecx; hdc
0x14001dbe5  call    cs:__imp_EnumDisplayMonitors
0x14001dbeb  xor     edx, edx
0x14001dbed  lea     rcx, [rsi+320h]
0x14001dbf4  call    ?BeginCheckUserIdle@UserIdleDetector@@QEAAJW4CheckUserIdleReason@1@@Z; UserIdleDetector::BeginCheckUserIdle(UserIdleDetector::CheckUserIdleReason)
0x14001dbf9  test    eax, eax
0x14001dbfb  jns     short loc_14001DC15
0x14001dbfd  mov     rcx, [rbp+28h]; this
0x14001dc01  mov     r9d, eax; char *
0x14001dc04  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001dc0b  mov     edx, 15BDh; void *
0x14001dc10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001dc15  mov     ecx, r12d
0x14001dc18  test    r14d, r14d
0x14001dc1b  setz    cl
0x14001dc1e  call    ?NotifyYourPhone@LockStateNotifier@@YAJW4YourPhoneNotificationType@1@@Z; LockStateNotifier::NotifyYourPhone(LockStateNotifier::YourPhoneNotificationType)
0x14001dc23  test    eax, eax
0x14001dc25  jns     loc_14001D955
0x14001dc2b  mov     rcx, [rbp+28h]; this
0x14001dc2f  mov     r9d, eax; char *
0x14001dc32  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001dc39  mov     edx, 15C4h; void *
0x14001dc3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001dc43  jmp     loc_14001D955
0x14001dc48  lea     rcx, [rsi+320h]
0x14001dc4f  mov     edx, 1
0x14001dc54  call    ?BeginCheckUserIdle@UserIdleDetector@@QEAAJW4CheckUserIdleReason@1@@Z; UserIdleDetector::BeginCheckUserIdle(UserIdleDetector::CheckUserIdleReason)
0x14001dc59  test    eax, eax
0x14001dc5b  jns     loc_14001D955
0x14001dc61  mov     rcx, [rbp+28h]; this
0x14001dc65  mov     r9d, eax; char *
0x14001dc68  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001dc6f  mov     edx, 15ECh; void *
0x14001dc74  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001dc79  jmp     loc_14001D955
0x14001dc7e  mov     [rbp+pv], r12
0x14001dc82  mov     ecx, 120h; cb
0x14001dc87  call    cs:__imp_CoTaskMemAlloc
0x14001dc8d  test    rax, rax
0x14001dc90  jz      loc_14001DEAD
0x14001dc96  xor     edx, edx
0x14001dc98  mov     rcx, rax
0x14001dc9b  call    ??0?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>(_GUID *)
0x14001dca0  mov     [rbp+var_10], rax
0x14001dca4  lea     rdx, [rbp+var_10]
0x14001dca8  lea     rcx, [rbp+pv]
0x14001dcac  call    ??4?$com_ptr_t@V?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy> &&)
0x14001dcb1  mov     rcx, [rbp+var_10]; pv
0x14001dcb5  test    rcx, rcx
0x14001dcb8  jz      short loc_14001DCBF
0x14001dcba  call    ?Release@?$merged_data@U_tip_ShellStartupHealthTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>::Release(void)
0x14001dcbf  mov     rcx, [rbp+pv]
0x14001dcc3  add     rcx, 8
0x14001dcc7  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x14001dccc  test    al, al
0x14001dcce  jz      loc_14001DB56
0x14001dcd4  jmp     loc_14001DB24
0x14001dcd9  mov     [rsi+3D8h], r12b
0x14001dce0  cmp     [rsi+3D9h], r12b
0x14001dce7  jnz     loc_14001D955
0x14001dced  lea     rdx, aIsexplorershut; "IsExplorerShuttingDown"
0x14001dcf4  mov     rcx, [rsi+3E0h]; hWnd
0x14001dcfb  call    cs:__imp_RemovePropW
0x14001dd01  jmp     loc_14001D955
0x14001dd06  lea     rdx, [rsi+38h]; jumptable 000000014001DA2A case 1
0x14001dd0a  test    rsi, rsi
0x14001dd0d  cmovz   rdx, r12; struct ITrayUIHost *
0x14001dd11  lea     rcx, [rbp+var_10]; this
0x14001dd15  call    ??0DeferWorkAreaChangesGuard@@QEAA@PEAUITrayUIHost@@@Z; DeferWorkAreaChangesGuard::DeferWorkAreaChangesGuard(ITrayUIHost *)
0x14001dd1a  nop
0x14001dd1b  mov     rcx, rsi; this
0x14001dd1e  call    ?_OnCreate@CTray@@IEAA_JXZ; CTray::_OnCreate(void)
0x14001dd23  mov     rbx, rax
0x14001dd26  lea     rcx, [rbp+var_10]; this
0x14001dd2a  call    ??1DeferWorkAreaChangesGuard@@QEAA@XZ; DeferWorkAreaChangesGuard::~DeferWorkAreaChangesGuard(void)
0x14001dd2f  mov     rax, rbx
0x14001dd32  jmp     loc_14001D959
0x14001dd37  mov     rcx, rsi; jumptable 000000014001DA2A case 2
0x14001dd3a  call    ?_HandleDestroy@CTray@@IEAA_JXZ; CTray::_HandleDestroy(void)
0x14001dd3f  jmp     loc_14001D959
0x14001dd44  test    r14b, 1; jumptable 000000014001DA2A case 17
0x14001dd48  jz      short loc_14001DD84
0x14001dd4a  cmp     [rsi+3D9h], r12b
0x14001dd51  jnz     short loc_14001DD5C
0x14001dd53  lea     rcx, [rsi+38h]; this
0x14001dd57  call    ?SaveTrayAndDesktop@CTray@@UEAAXXZ; CTray::SaveTrayAndDesktop(void)
  ... truncated ...
```
