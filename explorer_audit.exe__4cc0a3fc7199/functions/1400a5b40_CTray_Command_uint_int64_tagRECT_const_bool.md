# CTray::Command(uint,__int64,tagRECT const *,bool)

- ea: `0x1400a5b40`
- end: `0x1400a6447`
- name: `?Command@CTray@@UEAAXI_JPEBUtagRECT@@_N@Z`
- size: `2311`
- prototype: `void __usercall(CTray *__hidden this@<rcx>, unsigned int@<edx>, __int64@<r8>, const struct tagRECT *@<r9>, bool)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001d860`
- `0x140123bbc`

## callees

- `0x140006cac`
- `0x14000d890`
- `0x140016b10`
- `0x14001eba8`
- `0x14001ef70`
- `0x1400258a0`
- `0x140065a60`
- `0x140074ff0`
- `0x140088aac`
- `0x14008bfcc`
- `0x14008e284`
- `0x1400a5b40`
- `0x1400a69d0`
- `0x1400a6a0c`
- `0x1400ac48c`
- `0x1400ffac8`
- `0x1401040e0`
- `0x140112f5c`
- `0x140113304`
- `0x140113434`
- `0x140113b84`
- `0x140113bcc`
- `0x140115900`
- `0x140116660`
- `0x14011668c`
- `0x140120b8c`
- `0x140122804`
- `0x140122894`
- `0x140122904`
- `0x140122a24`
- `0x1401234ec`
- `0x140123bbc`
- `0x140124c68`
- `0x140125868`
- `0x140125964`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a5d14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a62cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a63b2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a5d14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a62cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a63b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400a5d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400a63f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400a5d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400a63f3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400a5d81`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400a640e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400a5d81`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400a640e`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1400a5ec4`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1400a5ec4`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1400a5ddc`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1400a5ddc`
- `SHELL32!__imp_SHFindComputer` at `0x1400a6339`
- `SHELL32!__imp_SHFindComputer` at `0x1400a6339`
- `SHLWAPI!__imp_SHGetMachineInfo` at `0x1400a6377`
- `SHLWAPI!__imp_SHGetMachineInfo` at `0x1400a6377`
- `USER32!LockWorkStation` at `0x1400a62b2`
- `USER32!LockWorkStation` at `0x1400a62b2`
- `USER32!TileWindows` at `0x1400a5c8e`
- `USER32!TileWindows` at `0x1400a5c8e`
- `USER32!CascadeWindows` at `0x1400a5c59`
- `USER32!CascadeWindows` at `0x1400a5c59`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a5d09`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a62c1`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a63a7`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a5d09`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a62c1`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400a63a7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400a5dc5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400a5dc5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400a60f1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400a614d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400a60f1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400a614d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x1400a5cd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x1400a5cd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400a623c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400a623c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1400a61c2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1400a61c2`
- `WINSTA!WinStationSetInformationW` at `0x1400a6398`
- `WINSTA!WinStationSetInformationW` at `0x1400a6398`

## string_xrefs

- `0x1400a60ff`: `TaskbarAppsVisibleInTabletMode`
- `0x1400a6118`: `TaskbarAppsVisibleInTabletMode`
- `0x1400a608c`: `TaskbarAutoHideInTabletMode`
- `0x1400a60a3`: `TaskbarAutoHideInTabletMode`
- `0x1400a6195`: `SearchboxTaskbarMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTray::Command(HWND *this, unsigned int a2, __int64 a3, const struct tagRECT *a4, bool a5)
{
  unsigned int Error; // r14d
  unsigned int v8; // edx
  __int64 *v9; // rax
  __int64 v10; // rbx
  HWND ForegroundWindow; // rax
  CTray *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r8
  CTray *v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int USDWORDW; // ebx
  __int64 v21; // r8
  __int64 *v22; // rax
  DWORD CurrentThreadId; // eax
  HWND *lpKids; // [rsp+20h] [rbp-E0h]
  bool v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v28[336]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v29[2]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  if ( a2 > 0x1F7 )
  {
    if ( a2 <= 0x270 )
    {
      if ( a2 != 624 )
      {
        switch ( a2 )
        {
          case 0x1FAu:
            UpdateWindow(*(this - 6));
            Sleep(0x64u);
            CTray::OnEndSessionInitiated((CTray *)(this - 7));
            CTray::_DoExitWindows(this - 7, v26, v_hwndDesktop);
            break;
          case 0x205u:
            if ( (byte_140253B83 & 0x10) != 0 )
            {
              McGenEventWrite_EventWriteTransfer(
                &Microsoft_Windows_Shell_Core_Provider_Context,
                &Explorer_ShutdownUX_SelectMenuItem_Stop,
                a3,
                1);
              if ( (byte_140253B83 & 0x10) != 0 )
                McGenEventWrite_EventWriteTransfer(
                  &Microsoft_Windows_Shell_Core_Provider_Context,
                  &Explorer_ShutdownUX_DefaultButtonPress_Stop,
                  v21,
                  1);
            }
            if ( (unsigned int)_AllowLockWorkStation() )
              LockWorkStation();
            break;
          case 0x206u:
            PostMessageW(v_hwndTray, 0x5B4u, 0, 0);
            break;
          case 0x207u:
            CTray::_HandleSearchPaneHotkey(this - 7, 30, a3, a4);
            break;
        }
      }
      return;
    }
    if ( a2 == 625 || a2 == 626 )
      return;
    if ( a2 != 5000 )
    {
      switch ( a2 )
      {
        case 0x1389u:
          if ( SHGetMachineInfo(3, 503, a3, a4) )
            WinStationSetInformationW(0, 0xFFFFFFFFLL, 13, 0, 0);
          break;
        case 0xA030u:
          (*(void (__fastcall **)(HWND, __int64, __int64, const struct tagRECT *))(*(_QWORD *)this[126] + 392LL))(
            this[126],
            503,
            a3,
            a4);
          break;
        case 0xA065u:
          (*(void (__fastcall **)(HWND, __int64, __int64, const struct tagRECT *))(*(_QWORD *)this[126] + 384LL))(
            this[126],
            503,
            a3,
            a4);
          break;
        case 0xA086u:
          SHFindComputer(0, 0, a3, a4);
          break;
      }
      return;
    }
    UpdateWindow(*(this - 6));
    Sleep(0x64u);
    v29[0] = v_hwndDesktop;
    v22 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b7072a96b90f0bbb1a9095c0d19d0d59_____lambda_b7072a96b90f0bbb1a9095c0d19d0d59___(
                       &v27,
                       v29);
    v10 = *v22;
    *v22 = 0;
    if ( v27 )
    {
      v27 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    goto LABEL_116;
  }
  if ( a2 == 503 )
  {
    v13 = 4;
LABEL_53:
    v14 = 0;
    a3 = 0;
    goto LABEL_54;
  }
  if ( a2 <= 0x1A0 )
  {
    if ( a2 == 416 )
    {
      if ( *((_BYTE *)this + 426) )
        return;
      LODWORD(v27) = 1;
      TrayTelemetry::WindowArrangementContextMenu::Start<enum TrayTelemetry::WindowArrangementContextMenuSource>(
        v28,
        &v27,
        a3,
        a4);
      TrayTelemetry::WindowArrangementContextMenu::UndoWindowArrangement((TrayTelemetry::WindowArrangementContextMenu *)v28);
      CTray::_RestoreWindowPositions((CTray *)(this - 7), 0, 0);
      wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v28, 0);
      goto LABEL_57;
    }
    if ( a2 <= 0x197 )
    {
      if ( a2 == 407 )
      {
        if ( !*((_BYTE *)this + 426) )
        {
          if ( a5 )
          {
            if ( !*((_BYTE *)this + 425) && !*((_BYTE *)this + 424)
              || (ForegroundWindow = GetForegroundWindow(), LODWORD(v27) = 0, !ForegroundWindow)
              || (unsigned int)GetWindowBand(ForegroundWindow, &v27) && (_DWORD)v27 == 1 )
            {
              CTray::_RaiseDesktop(this - 7, 3 - (unsigned int)(g_fDesktopRaised != 0), a3, a4);
            }
          }
          else
          {
            CTray::_RaiseDesktop(this - 7, 3 - (unsigned int)(g_fDesktopRaised != 0), a3, a4);
            v25 = g_fDesktopRaised == 0;
            TrayTelemetry::ContextMenuShowDesktop<bool>(&v25);
          }
        }
        return;
      }
      if ( a2 == 401 )
      {
        CTray::_RunDlg((CTray *)(this - 7));
        return;
      }
      if ( a2 != 402 )
      {
        if ( a2 == 403 || a2 - 404 <= 1 )
        {
          Error = 0;
          LODWORD(v27) = 1;
          TrayTelemetry::WindowArrangementContextMenu::Start<enum TrayTelemetry::WindowArrangementContextMenuSource>(
            v28,
            &v27,
            a3,
            a4);
          if ( (unsigned int)CTray::CanTileAnyWindows((CTray *)this) )
          {
            if ( a2 == 403 )
            {
              v8 = 535;
            }
            else
            {
              v8 = 538;
              if ( a2 == 404 )
                v8 = 536;
            }
            CTray::SaveWindowPositions((CTray *)(this - 7), v8);
            CTray::AppBarNotifyAll((CTray *)this, 0, 3u, 0, 1);
            if ( a2 == 403 )
            {
              if ( CascadeWindows(v_hwndDesktop, 0, 0, 0, 0) )
                Error = 0;
              else
                Error = ResultFromKnownLastError();
              TrayTelemetry::WindowArrangementContextMenu::CascadeWindows((TrayTelemetry::WindowArrangementContextMenu *)v28);
            }
            else
            {
              if ( TileWindows(v_hwndDesktop, a2 != 404, 0, 0, 0) )
                Error = 0;
              else
                Error = ResultFromKnownLastError();
              if ( a2 == 404 )
                TrayTelemetry::WindowArrangementContextMenu::WindowsSideBySide((TrayTelemetry::WindowArrangementContextMenu *)v28);
              else
                TrayTelemetry::WindowArrangementContextMenu::ShowWindowsStacked((TrayTelemetry::WindowArrangementContextMenu *)v28);
            }
            *((_DWORD *)this + 41) = 0;
            SetTimer(*(this - 6), 0x12u, 0x1F4u, 0);
            CTray::AppBarNotifyAll((CTray *)this, 0, 3u, 0, 0);
          }
          wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v28, Error);
LABEL_57:
          TrayTelemetry::WindowArrangementContextMenu::~WindowArrangementContextMenu((TrayTelemetry::WindowArrangementContextMenu *)v28);
          return;
        }
        return;
      }
      UpdateWindow(*(this - 6));
      Sleep(0x64u);
      CTray::OnEndSessionInitiated((CTray *)(this - 7));
      CTray::SaveTrayAndDesktop((CTray *)this);
      v29[0] = v_hwndDesktop;
      v9 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1aaafe5cef8d3e2bff0408f882a45e8e_____lambda_1aaafe5cef8d3e2bff0408f882a45e8e___(
                        &v27,
                        v29);
      v10 = *v9;
      *v9 = 0;
      if ( v27 )
      {
        v27 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
      }
LABEL_116:
      CurrentThreadId = GetCurrentThreadId();
      SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return;
    }
    if ( a2 != 408 )
    {
      switch ( a2 )
      {
        case 0x19Au:
          SHCreateThread(_EjectThreadProc, 0, 0x2001u, 0);
          break;
        case 0x19Bu:
          CTray::_ActivateWindowSwitcher((CTray *)(this - 7));
          break;
        case 0x19Du:
          (*(void (__fastcall **)(HWND, const struct tagRECT *))(*(_QWORD *)this[126] + 376LL))(this[126], a4);
          break;
        case 0x19Fu:
          v12 = (CTray *)(this - 7);
          if ( !*((_BYTE *)v12 + 482) )
            CTray::_MinimizeAll(v12, 0, 0);
          break;
      }
      return;
    }
    v13 = 2;
    goto LABEL_53;
  }
  if ( a2 <= 0x1B0 )
  {
    if ( a2 != 432 )
    {
      if ( a2 == 419 )
      {
        v16 = (CTray *)(this - 7);
        if ( !*((_BYTE *)v16 + 482) )
          CTray::_HandleGlobalHotkey(v16, 0x1F7u, 1);
        return;
      }
      if ( a2 != 421 )
      {
        if ( a2 == 424 || a2 == 425 )
        {
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          {
            lpKids = (HWND *)v29;
            McGenEventWrite_EventWriteTransfer(
              &Microsoft_Windows_Shell_Core_Provider_Context,
              &Taskbar_LockState_ChangeNotify_Start,
              a3,
              1);
          }
          (*(void (__fastcall **)(HWND, _QWORD, __int64, const struct tagRECT *, HWND *))(*(_QWORD *)this[126] + 368LL))(
            this[126],
            0,
            a3,
            a4,
            lpKids);
          (*(void (__fastcall **)(HWND))(*(_QWORD *)this[126] + 456LL))(this[126]);
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              &Microsoft_Windows_Shell_Core_Provider_Context,
              &Taskbar_LockState_ChangeNotify_Stop,
              v15,
              1);
        }
        else if ( a2 == 430 )
        {
          (*(void (__fastcall **)(HWND, __int64, __int64, const struct tagRECT *))(*(_QWORD *)this[126] + 400LL))(
            this[126],
            503,
            a3,
            a4);
        }
        return;
      }
      v14 = (__int64)*(this - 6);
      LOBYTE(a3) = 1;
      v13 = 1;
LABEL_54:
      LaunchHelpers::Launch(g_hinstCabinet, v13, a3, v14);
      return;
    }
LABEL_86:
    LODWORD(v27) = a2 - 432;
    SHRegSetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
      L"SearchboxTaskbarMode",
      a2 - 432);
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"TraySettings");
    TrayTelemetry::TaskbarSearchOptionChanged<unsigned long const &>(&v27);
    return;
  }
  if ( a2 == 433 || a2 == 434 )
    goto LABEL_86;
  if ( a2 != 435 )
  {
    if ( a2 == 440 )
    {
      USDWORDW = SHRegGetUSDWORDW(this, L"TaskbarAppsVisibleInTabletMode", 0, a4);
      v18 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              L"TaskbarAppsVisibleInTabletMode",
              USDWORDW == 0);
      if ( v18 >= 0 )
      {
        SendMessageW(*(this - 6), 0x5CAu, 1u, 0);
        v25 = 0;
        v26[0] = USDWORDW == 0;
        TaskbarAppIconsTelemetry::TaskbarAppIconsSettingChanged<bool,bool>(v26, &v25);
        return;
      }
      v19 = 6986;
    }
    else
    {
      if ( a2 != 443 )
        return;
      v17 = SHRegGetUSDWORDW(this, L"TaskbarAutoHideInTabletMode", 0, a4);
      v18 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              L"TaskbarAutoHideInTabletMode",
              v17 == 0);
      if ( v18 >= 0 )
      {
        SendMessageW(*(this - 6), 0x5CAu, 0xAu, 0);
        return;
      }
      v19 = 6996;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
      (const char *)(unsigned int)v18,
      (int)lpKids);
    return;
  }
  (*(void (__fastcall **)(HWND, __int64, __int64, const struct tagRECT *))(*(_QWORD *)this[126] + 408LL))(
    this[126],
    503,
    a3,
    a4);
}

```

## disassembly

```asm
0x1400a5b40  push    rbp
0x1400a5b42  push    rbx
0x1400a5b43  push    rsi
0x1400a5b44  push    rdi
0x1400a5b45  push    r14
0x1400a5b47  lea     rbp, [rsp-0B0h]
0x1400a5b4f  sub     rsp, 1B0h
0x1400a5b56  mov     rax, cs:__security_cookie
0x1400a5b5d  xor     rax, rsp
0x1400a5b60  mov     [rbp+0D0h+var_30], rax
0x1400a5b67  mov     rdi, r8
0x1400a5b6a  mov     ebx, edx
0x1400a5b6c  mov     rsi, rcx
0x1400a5b6f  mov     edx, 1F7h; unsigned __int64
0x1400a5b74  cmp     ebx, edx
0x1400a5b76  ja      loc_1400A61E1
0x1400a5b7c  jz      loc_1400A61D7
0x1400a5b82  lea     eax, [rdx-57h]
0x1400a5b85  cmp     ebx, eax
0x1400a5b87  ja      loc_1400A5F46
0x1400a5b8d  jz      loc_1400A5EEB
0x1400a5b93  lea     eax, [rdx-60h]
0x1400a5b96  cmp     ebx, eax
0x1400a5b98  ja      loc_1400A5E40
0x1400a5b9e  jz      loc_1400A5D9B
0x1400a5ba4  mov     eax, ebx
0x1400a5ba6  sub     eax, 191h
0x1400a5bab  jz      loc_1400A5D8D
0x1400a5bb1  sub     eax, 1
0x1400a5bb4  jz      loc_1400A5D05
0x1400a5bba  sub     eax, 1
0x1400a5bbd  jz      short loc_1400A5BCD
0x1400a5bbf  sub     eax, 1
0x1400a5bc2  jz      short loc_1400A5BCD
0x1400a5bc4  cmp     eax, 1
0x1400a5bc7  jnz     loc_1400A642A
0x1400a5bcd  xor     edi, edi
0x1400a5bcf  mov     r14d, edi
0x1400a5bd2  mov     dword ptr [rsp+1D0h+var_198], 1
0x1400a5bda  lea     rdx, [rsp+1D0h+var_198]
0x1400a5bdf  lea     rcx, [rsp+1D0h+var_190]
0x1400a5be4  call    ??$Start@W4WindowArrangementContextMenuSource@TrayTelemetry@@@WindowArrangementContextMenu@TrayTelemetry@@SA?AV01@$$QEAW4WindowArrangementContextMenuSource@1@@Z; TrayTelemetry::WindowArrangementContextMenu::Start<TrayTelemetry::WindowArrangementContextMenuSource>(TrayTelemetry::WindowArrangementContextMenuSource &&)
0x1400a5be9  nop
0x1400a5bea  mov     rcx, rsi; this
0x1400a5bed  call    ?CanTileAnyWindows@CTray@@UEAAHXZ; CTray::CanTileAnyWindows(void)
0x1400a5bf2  test    eax, eax
0x1400a5bf4  jz      loc_1400A5CF2
0x1400a5bfa  mov     r14d, 193h
0x1400a5c00  cmp     ebx, r14d
0x1400a5c03  jnz     short loc_1400A5C0C
0x1400a5c05  mov     edx, 217h
0x1400a5c0a  jmp     short loc_1400A5C1D
0x1400a5c0c  mov     edx, 21Ah
0x1400a5c11  lea     eax, [rdx-2]
0x1400a5c14  cmp     ebx, 194h
0x1400a5c1a  cmovz   edx, eax; unsigned int
0x1400a5c1d  lea     rcx, [rsi-38h]; this
0x1400a5c21  call    ?SaveWindowPositions@CTray@@QEAAXI@Z; CTray::SaveWindowPositions(uint)
0x1400a5c26  mov     [rsp+1D0h+lpKids], 1; __int64
0x1400a5c2f  xor     r9d, r9d; HWND
0x1400a5c32  xor     edx, edx; HMONITOR
0x1400a5c34  lea     r8d, [r9+3]; unsigned int
0x1400a5c38  mov     rcx, rsi; this
0x1400a5c3b  call    ?AppBarNotifyAll@CTray@@UEAAXPEAUHMONITOR__@@IPEAUHWND__@@_J@Z; CTray::AppBarNotifyAll(HMONITOR__ *,uint,HWND__ *,__int64)
0x1400a5c40  mov     [rsp+1D0h+lpKids], rdi; lpKids
0x1400a5c45  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hwndParent
0x1400a5c4c  cmp     ebx, r14d
0x1400a5c4f  jnz     short loc_1400A5C7D
0x1400a5c51  xor     r9d, r9d; cKids
0x1400a5c54  xor     r8d, r8d; lpRect
0x1400a5c57  xor     edx, edx; wHow
0x1400a5c59  call    cs:__imp_CascadeWindows
0x1400a5c5f  test    ax, ax
0x1400a5c62  jz      short loc_1400A5C69
0x1400a5c64  mov     r14d, edi
0x1400a5c67  jmp     short loc_1400A5C71
0x1400a5c69  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400a5c6e  mov     r14d, eax
0x1400a5c71  lea     rcx, [rsp+1D0h+var_190]; this
0x1400a5c76  call    ?CascadeWindows@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::CascadeWindows(void)
0x1400a5c7b  jmp     short loc_1400A5CBF
0x1400a5c7d  mov     edx, edi
0x1400a5c7f  cmp     ebx, 194h
0x1400a5c85  setnz   dl; wHow
0x1400a5c88  xor     r9d, r9d; cKids
0x1400a5c8b  xor     r8d, r8d; lpRect
0x1400a5c8e  call    cs:__imp_TileWindows
0x1400a5c94  test    ax, ax
0x1400a5c97  jz      short loc_1400A5C9E
0x1400a5c99  mov     r14d, edi
0x1400a5c9c  jmp     short loc_1400A5CA6
0x1400a5c9e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400a5ca3  mov     r14d, eax
0x1400a5ca6  lea     rcx, [rsp+1D0h+var_190]; this
0x1400a5cab  cmp     ebx, 194h
0x1400a5cb1  jnz     short loc_1400A5CBA
0x1400a5cb3  call    ?WindowsSideBySide@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::WindowsSideBySide(void)
0x1400a5cb8  jmp     short loc_1400A5CBF
0x1400a5cba  call    ?ShowWindowsStacked@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::ShowWindowsStacked(void)
0x1400a5cbf  mov     [rsi+0A4h], edi
0x1400a5cc5  xor     r9d, r9d; lpTimerFunc
0x1400a5cc8  lea     edx, [r9+12h]; nIDEvent
0x1400a5ccc  mov     r8d, 1F4h; uElapse
0x1400a5cd2  mov     rcx, [rsi-30h]; hWnd
0x1400a5cd6  call    cs:__imp_SetTimer
0x1400a5cdc  mov     [rsp+1D0h+lpKids], rdi; __int64
0x1400a5ce1  xor     r9d, r9d; HWND
0x1400a5ce4  xor     edx, edx; HMONITOR
0x1400a5ce6  lea     r8d, [r9+3]; unsigned int
0x1400a5cea  mov     rcx, rsi; this
0x1400a5ced  call    ?AppBarNotifyAll@CTray@@UEAAXPEAUHMONITOR__@@IPEAUHWND__@@_J@Z; CTray::AppBarNotifyAll(HMONITOR__ *,uint,HWND__ *,__int64)
0x1400a5cf2  mov     edx, r14d
0x1400a5cf5  lea     rcx, [rsp+1D0h+var_190]
0x1400a5cfa  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400a5cff  nop
0x1400a5d00  jmp     loc_1400A5F37
0x1400a5d05  mov     rcx, [rcx-30h]; hWnd
0x1400a5d09  call    cs:__imp_UpdateWindow
0x1400a5d0f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1400a5d14  call    cs:__imp_Sleep
0x1400a5d1a  lea     rcx, [rsi-38h]; this
0x1400a5d1e  call    ?OnEndSessionInitiated@CTray@@IEAAXXZ; CTray::OnEndSessionInitiated(void)
0x1400a5d23  mov     rcx, rsi; this
0x1400a5d26  call    ?SaveTrayAndDesktop@CTray@@UEAAXXZ; CTray::SaveTrayAndDesktop(void)
0x1400a5d2b  mov     rax, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; HWND__ * v_hwndDesktop
0x1400a5d32  mov     [rbp+0D0h+var_40], rax
0x1400a5d39  lea     rdx, [rbp+0D0h+var_40]
0x1400a5d40  lea     rcx, [rsp+1D0h+var_198]
0x1400a5d45  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_1aaafe5cef8d3e2bff0408f882a45e8e_____lambda_1aaafe5cef8d3e2bff0408f882a45e8e___
0x1400a5d4a  mov     rbx, [rax]
0x1400a5d4d  xor     edi, edi
0x1400a5d4f  mov     [rax], rdi
0x1400a5d52  mov     rcx, [rsp+1D0h+var_198]
0x1400a5d57  test    rcx, rcx
0x1400a5d5a  jz      short loc_1400A5D66
0x1400a5d5c  mov     [rsp+1D0h+var_198], rdi
0x1400a5d61  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1400a5d66  call    cs:__imp_GetCurrentThreadId
0x1400a5d6c  mov     [rsp+1D0h+var_1A8], rdi
0x1400a5d71  mov     [rsp+1D0h+lpKids], rbx
0x1400a5d76  xor     r9d, r9d
0x1400a5d79  mov     r8d, eax
0x1400a5d7c  xor     edx, edx
0x1400a5d7e  lea     ecx, [rdx+1]
0x1400a5d81  call    cs:__imp_SHTaskPoolQueueTask
0x1400a5d87  nop
0x1400a5d88  jmp     loc_1400A6415
0x1400a5d8d  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400a5d91  call    ?_RunDlg@CTray@@IEAAXXZ; CTray::_RunDlg(void)
0x1400a5d96  jmp     loc_1400A642A
0x1400a5d9b  xor     edi, edi
0x1400a5d9d  cmp     [rcx+1AAh], dil
0x1400a5da4  jnz     loc_1400A642A
0x1400a5daa  cmp     [rbp+0D0h+arg_20], dil
0x1400a5db1  jz      short loc_1400A5E10
0x1400a5db3  cmp     [rcx+1A9h], dil
0x1400a5dba  jnz     short loc_1400A5DC5
0x1400a5dbc  cmp     [rcx+1A8h], dil
0x1400a5dc3  jz      short loc_1400A5DF5
0x1400a5dc5  call    cs:__imp_GetForegroundWindow
0x1400a5dcb  mov     dword ptr [rsp+1D0h+var_198], edi
0x1400a5dcf  test    rax, rax
0x1400a5dd2  jz      short loc_1400A5DF5
0x1400a5dd4  lea     rdx, [rsp+1D0h+var_198]
0x1400a5dd9  mov     rcx, rax
0x1400a5ddc  call    cs:__imp_GetWindowBand
0x1400a5de2  test    eax, eax
0x1400a5de4  jz      loc_1400A642A
0x1400a5dea  cmp     dword ptr [rsp+1D0h+var_198], 1
0x1400a5def  jnz     loc_1400A642A
0x1400a5df5  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x1400a5dfb  neg     eax
0x1400a5dfd  sbb     edx, edx
0x1400a5dff  add     edx, 3
0x1400a5e02  lea     rcx, [rsi-38h]
0x1400a5e06  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x1400a5e0b  jmp     loc_1400A642A
0x1400a5e10  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x1400a5e16  neg     eax
0x1400a5e18  sbb     edx, edx
0x1400a5e1a  add     edx, 3
0x1400a5e1d  add     rcx, 0FFFFFFFFFFFFFFC8h
0x1400a5e21  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x1400a5e26  cmp     cs:?g_fDesktopRaised@@3HA, edi; int g_fDesktopRaised
0x1400a5e2c  setz    [rsp+1D0h+var_1A0]
0x1400a5e31  lea     rcx, [rsp+1D0h+var_1A0]
0x1400a5e36  call    ??$ContextMenuShowDesktop@_N@TrayTelemetry@@SAX$$QEA_N@Z; TrayTelemetry::ContextMenuShowDesktop<bool>(bool &&)
0x1400a5e3b  jmp     loc_1400A642A
0x1400a5e40  sub     ebx, 198h
0x1400a5e46  jz      loc_1400A5ECF
0x1400a5e4c  sub     ebx, 2
0x1400a5e4f  jz      short loc_1400A5EB2
0x1400a5e51  sub     ebx, 1
0x1400a5e54  jz      short loc_1400A5EA4
0x1400a5e56  sub     ebx, 2
0x1400a5e59  jz      short loc_1400A5E86
0x1400a5e5b  cmp     ebx, 2
0x1400a5e5e  jnz     loc_1400A642A
0x1400a5e64  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400a5e68  xor     edi, edi
0x1400a5e6a  cmp     [rcx+1E2h], dil
0x1400a5e71  jnz     loc_1400A642A
0x1400a5e77  xor     r8d, r8d; void *
0x1400a5e7a  xor     edx, edx; int
0x1400a5e7c  call    ?_MinimizeAll@CTray@@IEAAHHPEAX@Z; CTray::_MinimizeAll(int,void *)
0x1400a5e81  jmp     loc_1400A642A
0x1400a5e86  mov     rcx, [rcx+3F0h]
0x1400a5e8d  mov     rax, [rcx]
0x1400a5e90  mov     rdx, r9
0x1400a5e93  mov     rax, [rax+178h]
0x1400a5e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5e9f  jmp     loc_1400A642A
0x1400a5ea4  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400a5ea8  call    ?_ActivateWindowSwitcher@CTray@@IEAAJXZ; CTray::_ActivateWindowSwitcher(void)
0x1400a5ead  jmp     loc_1400A642A
0x1400a5eb2  xor     r9d, r9d; pfnCallback
0x1400a5eb5  xor     edx, edx; pData
0x1400a5eb7  mov     r8d, 2001h; flags
0x1400a5ebd  lea     rcx, ?_EjectThreadProc@@YAKPEAX@Z; pfnThreadProc
0x1400a5ec4  call    cs:__imp_SHCreateThread
0x1400a5eca  jmp     loc_1400A642A
0x1400a5ecf  mov     edx, 2
0x1400a5ed4  xor     r9d, r9d
0x1400a5ed7  xor     r8d, r8d
0x1400a5eda  mov     rcx, cs:g_hinstCabinet
0x1400a5ee1  call    ?Launch@LaunchHelpers@@YAXPEAUHINSTANCE__@@W4LaunchEntity@1@_NPEAUHWND__@@@Z; LaunchHelpers::Launch(HINSTANCE__ *,LaunchHelpers::LaunchEntity,bool,HWND__ *)
0x1400a5ee6  jmp     loc_1400A642A
0x1400a5eeb  xor     edi, edi
0x1400a5eed  cmp     [rcx+1AAh], dil
0x1400a5ef4  jnz     loc_1400A642A
0x1400a5efa  mov     dword ptr [rsp+1D0h+var_198], 1
0x1400a5f02  lea     rdx, [rsp+1D0h+var_198]
0x1400a5f07  lea     rcx, [rsp+1D0h+var_190]
0x1400a5f0c  call    ??$Start@W4WindowArrangementContextMenuSource@TrayTelemetry@@@WindowArrangementContextMenu@TrayTelemetry@@SA?AV01@$$QEAW4WindowArrangementContextMenuSource@1@@Z; TrayTelemetry::WindowArrangementContextMenu::Start<TrayTelemetry::WindowArrangementContextMenuSource>(TrayTelemetry::WindowArrangementContextMenuSource &&)
0x1400a5f11  nop
0x1400a5f12  lea     rcx, [rsp+1D0h+var_190]; this
0x1400a5f17  call    ?UndoWindowArrangement@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::UndoWindowArrangement(void)
0x1400a5f1c  xor     r8d, r8d; void *
0x1400a5f1f  xor     edx, edx; int
0x1400a5f21  lea     rcx, [rsi-38h]; this
0x1400a5f25  call    ?_RestoreWindowPositions@CTray@@IEAAHHPEAX@Z; CTray::_RestoreWindowPositions(int,void *)
0x1400a5f2a  xor     edx, edx
0x1400a5f2c  lea     rcx, [rsp+1D0h+var_190]
0x1400a5f31  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400a5f36  nop
0x1400a5f37  lea     rcx, [rsp+1D0h+var_190]; this
0x1400a5f3c  call    ??1WindowArrangementContextMenu@TrayTelemetry@@QEAA@XZ; TrayTelemetry::WindowArrangementContextMenu::~WindowArrangementContextMenu(void)
0x1400a5f41  jmp     loc_1400A642A
0x1400a5f46  mov     eax, 1B0h
0x1400a5f4b  cmp     ebx, eax
0x1400a5f4d  ja      loc_1400A605C
0x1400a5f53  jz      loc_1400A6189
0x1400a5f59  sub     ebx, 1A3h
0x1400a5f5f  jz      loc_1400A603B
0x1400a5f65  sub     ebx, 2
0x1400a5f68  jz      loc_1400A602A
0x1400a5f6e  sub     ebx, 3
0x1400a5f71  jz      short loc_1400A5F97
0x1400a5f73  sub     ebx, 1
0x1400a5f76  jz      short loc_1400A5F97
0x1400a5f78  cmp     ebx, 5
0x1400a5f7b  jnz     loc_1400A642A
0x1400a5f81  mov     rcx, [rcx+3F0h]
0x1400a5f88  mov     rax, [rcx]
0x1400a5f8b  mov     rax, [rax+190h]
0x1400a5f92  jmp     loc_1400A6355
0x1400a5f97  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1400a5f9e  jz      short loc_1400A5FC5
0x1400a5fa0  lea     rax, [rbp+0D0h+var_40]
0x1400a5fa7  mov     [rsp+1D0h+lpKids], rax
0x1400a5fac  mov     r9d, 1
0x1400a5fb2  lea     rdx, Taskbar_LockState_ChangeNotify_Start
0x1400a5fb9  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400a5fc0  call    McGenEventWrite_EventWriteTransfer
0x1400a5fc5  mov     rcx, [rsi+3F0h]
0x1400a5fcc  mov     rax, [rcx]
0x1400a5fcf  xor     edx, edx
0x1400a5fd1  mov     rax, [rax+170h]
0x1400a5fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5fdd  mov     rcx, [rsi+3F0h]
0x1400a5fe4  mov     rax, [rcx]
0x1400a5fe7  mov     rax, [rax+1C8h]
0x1400a5fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5ff3  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1400a5ffa  jz      loc_1400A642A
0x1400a6000  lea     rax, [rbp+0D0h+var_40]
0x1400a6007  mov     [rsp+1D0h+lpKids], rax
0x1400a600c  mov     r9d, 1
0x1400a6012  lea     rdx, Taskbar_LockState_ChangeNotify_Stop
0x1400a6019  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400a6020  call    McGenEventWrite_EventWriteTransfer
0x1400a6025  jmp     loc_1400A642A
0x1400a602a  mov     r9, [rcx-30h]
0x1400a602e  mov     r8b, 1
0x1400a6031  mov     edx, 1
0x1400a6036  jmp     loc_1400A5EDA
0x1400a603b  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400a603f  xor     edi, edi
0x1400a6041  cmp     [rcx+1E2h], dil
0x1400a6048  jnz     loc_1400A642A
  ... truncated ...
```
