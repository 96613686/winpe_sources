# CTray::Command(uint,__int64,tagRECT const *,bool)

- ea: `0x1400abc30`
- end: `0x1400ac524`
- name: `?Command@CTray@@UEAAXI_JPEBUtagRECT@@_N@Z`
- size: `2292`
- prototype: `void __usercall(CTray *__hidden this@<rcx>, unsigned int@<edx>, __int64@<r8>, const struct tagRECT *@<r9>, bool)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140019eb0`
- `0x14012f214`

## callees

- `0x14000bb20`
- `0x140012f50`
- `0x140019430`
- `0x14001b2c8`
- `0x14001c330`
- `0x140079bc0`
- `0x140080ce8`
- `0x14008e470`
- `0x1400918ac`
- `0x140093b68`
- `0x1400abc30`
- `0x1400acaec`
- `0x1400acb28`
- `0x1400b239c`
- `0x1401087c0`
- `0x14010e160`
- `0x14011d63c`
- `0x14011dce4`
- `0x14011e0dc`
- `0x14011e450`
- `0x14011e498`
- `0x1401201ec`
- `0x140120fd0`
- `0x140121000`
- `0x14012c0ec`
- `0x14012dde4`
- `0x14012de74`
- `0x14012dee4`
- `0x14012e004`
- `0x14012eb60`
- `0x14012f214`
- `0x140130348`
- `0x14013103c`
- `0x140131140`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400abe20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ac3e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ac4e0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400abe20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ac3e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ac4e0`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1400abfa5`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1400abfa5`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1400abeb5`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1400abeb5`
- `SHELL32!__imp_SHFindComputer` at `0x1400ac456`
- `SHELL32!__imp_SHFindComputer` at `0x1400ac456`
- `SHLWAPI!__imp_SHGetMachineInfo` at `0x1400ac49a`
- `SHLWAPI!__imp_SHGetMachineInfo` at `0x1400ac49a`
- `USER32!TileWindows` at `0x1400abd88`
- `USER32!TileWindows` at `0x1400abd88`
- `USER32!CascadeWindows` at `0x1400abd4d`
- `USER32!CascadeWindows` at `0x1400abd4d`
- `USER32!LockWorkStation` at `0x1400ac3bd`
- `USER32!LockWorkStation` at `0x1400ac3bd`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400abe0f`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400ac3d2`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400ac4cf`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400abe0f`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400ac3d2`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1400ac4cf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400abe94`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400abe94`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400ac1e0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400ac242`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400ac1e0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1400ac242`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x1400abdd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x1400abdd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400ac341`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400ac341`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1400ac2bf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1400ac2bf`
- `WINSTA!WinStationSetInformationW` at `0x1400ac4bd`
- `WINSTA!WinStationSetInformationW` at `0x1400ac4bd`

## string_xrefs

- `0x1400ac1f4`: `TaskbarAppsVisibleInTabletMode`
- `0x1400ac20d`: `TaskbarAppsVisibleInTabletMode`
- `0x1400ac17b`: `TaskbarAutoHideInTabletMode`
- `0x1400ac192`: `TaskbarAutoHideInTabletMode`
- `0x1400ac292`: `SearchboxTaskbarMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTray::Command(HWND *this, unsigned int a2, __int64 a3, const struct tagRECT *a4, bool a5)
{
  unsigned int Error; // r14d
  unsigned int v8; // edx
  __int64 v9; // rcx
  HWND ForegroundWindow; // rax
  CTray *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r8
  CTray *v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int USDWORDW; // ebx
  __int64 v20; // r8
  __int64 v21; // rcx
  HWND *lpKids; // [rsp+20h] [rbp-E0h]
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[15]; // [rsp+31h] [rbp-CFh] BYREF
  _BYTE v25[336]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[2]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  if ( a2 > 0x1F7 )
  {
    if ( a2 > 0x270 )
    {
      if ( a2 != 625 && a2 != 626 )
      {
        switch ( a2 )
        {
          case 0x1388u:
            UpdateWindow(*(this - 6));
            Sleep(0x64u);
            v26[0] = v_hwndDesktop;
            Windows::Internal::ComTaskPool::QueueTask__lambda_b7072a96b90f0bbb1a9095c0d19d0d59___(v21, v26);
            break;
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
      }
    }
    else if ( a2 != 624 )
    {
      switch ( a2 )
      {
        case 0x1FAu:
          UpdateWindow(*(this - 6));
          Sleep(0x64u);
          CTray::OnEndSessionInitiated((CTray *)(this - 7));
          CTray::_DoExitWindows(this - 7, v24, v_hwndDesktop);
          break;
        case 0x205u:
          if ( (byte_14024FCC3 & 0x10) != 0 )
          {
            McGenEventWrite_EventWriteTransfer(
              &Microsoft_Windows_Shell_Core_Provider_Context,
              Explorer_ShutdownUX_SelectMenuItem_Stop,
              a3,
              1);
            if ( (byte_14024FCC3 & 0x10) != 0 )
              McGenEventWrite_EventWriteTransfer(
                &Microsoft_Windows_Shell_Core_Provider_Context,
                Explorer_ShutdownUX_DefaultButtonPress_Stop,
                v20,
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
  if ( a2 == 503 )
  {
    v12 = 4;
LABEL_51:
    v13 = 0;
    a3 = 0;
    goto LABEL_52;
  }
  if ( a2 <= 0x1A0 )
  {
    if ( a2 == 416 )
    {
      if ( *((_BYTE *)this + 426) )
        return;
      LODWORD(v26[0]) = 1;
      TrayTelemetry::WindowArrangementContextMenu::Start<enum TrayTelemetry::WindowArrangementContextMenuSource>(
        v25,
        v26,
        a3,
        a4);
      TrayTelemetry::WindowArrangementContextMenu::UndoWindowArrangement((TrayTelemetry::WindowArrangementContextMenu *)v25);
      CTray::_RestoreWindowPositions((CTray *)(this - 7), 0, 0);
      wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, 0);
      goto LABEL_55;
    }
    if ( a2 <= 0x197 )
    {
      switch ( a2 )
      {
        case 0x197u:
          if ( !*((_BYTE *)this + 426) )
          {
            if ( a5 )
            {
              if ( !*((_BYTE *)this + 425) && !*((_BYTE *)this + 424)
                || (ForegroundWindow = GetForegroundWindow(), LODWORD(v26[0]) = 0, !ForegroundWindow)
                || (unsigned int)GetWindowBand(ForegroundWindow, v26) && LODWORD(v26[0]) == 1 )
              {
                CTray::_RaiseDesktop(this - 7, 3 - (unsigned int)(g_fDesktopRaised != 0), a3, a4);
              }
            }
            else
            {
              CTray::_RaiseDesktop(this - 7, 3 - (unsigned int)(g_fDesktopRaised != 0), a3, a4);
              v23 = g_fDesktopRaised == 0;
              TrayTelemetry::ContextMenuShowDesktop<bool>(&v23);
            }
          }
          break;
        case 0x191u:
          CTray::_RunDlg((CTray *)(this - 7));
          return;
        case 0x192u:
          UpdateWindow(*(this - 6));
          Sleep(0x64u);
          CTray::OnEndSessionInitiated((CTray *)(this - 7));
          CTray::SaveTrayAndDesktop((CTray *)this);
          v26[0] = v_hwndDesktop;
          Windows::Internal::ComTaskPool::QueueTask__lambda_1aaafe5cef8d3e2bff0408f882a45e8e___(v9, v26);
          return;
        default:
          if ( a2 == 403 || a2 - 404 <= 1 )
          {
            Error = 0;
            LODWORD(v26[0]) = 1;
            TrayTelemetry::WindowArrangementContextMenu::Start<enum TrayTelemetry::WindowArrangementContextMenuSource>(
              v25,
              v26,
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
                TrayTelemetry::WindowArrangementContextMenu::CascadeWindows((TrayTelemetry::WindowArrangementContextMenu *)v25);
              }
              else
              {
                if ( TileWindows(v_hwndDesktop, a2 != 404, 0, 0, 0) )
                  Error = 0;
                else
                  Error = ResultFromKnownLastError();
                if ( a2 == 404 )
                  TrayTelemetry::WindowArrangementContextMenu::WindowsSideBySide((TrayTelemetry::WindowArrangementContextMenu *)v25);
                else
                  TrayTelemetry::WindowArrangementContextMenu::ShowWindowsStacked((TrayTelemetry::WindowArrangementContextMenu *)v25);
              }
              *((_DWORD *)this + 41) = 0;
              SetTimer(*(this - 6), 0x12u, 0x1F4u, 0);
              CTray::AppBarNotifyAll((CTray *)this, 0, 3u, 0, 0);
            }
            wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, Error);
LABEL_55:
            TrayTelemetry::WindowArrangementContextMenu::~WindowArrangementContextMenu((TrayTelemetry::WindowArrangementContextMenu *)v25);
            return;
          }
          break;
      }
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
          v11 = (CTray *)(this - 7);
          if ( !*((_BYTE *)v11 + 482) )
            CTray::_MinimizeAll(v11, 0, 0);
          break;
      }
      return;
    }
    v12 = 2;
    goto LABEL_51;
  }
  if ( a2 <= 0x1B0 )
  {
    if ( a2 != 432 )
    {
      if ( a2 == 419 )
      {
        v15 = (CTray *)(this - 7);
        if ( !*((_BYTE *)v15 + 482) )
          CTray::_HandleGlobalHotkey(v15, 0x1F7u, 1);
        return;
      }
      if ( a2 != 421 )
      {
        if ( a2 == 424 || a2 == 425 )
        {
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          {
            lpKids = (HWND *)v26;
            McGenEventWrite_EventWriteTransfer(
              &Microsoft_Windows_Shell_Core_Provider_Context,
              Taskbar_LockState_ChangeNotify_Start,
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
              Taskbar_LockState_ChangeNotify_Stop,
              v14,
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
      v13 = (__int64)*(this - 6);
      LOBYTE(a3) = 1;
      v12 = 1;
LABEL_52:
      LaunchHelpers::Launch(g_hinstCabinet, v12, a3, v13);
      return;
    }
LABEL_84:
    LODWORD(v26[0]) = a2 - 432;
    SHRegSetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
      L"SearchboxTaskbarMode",
      a2 - 432);
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"TraySettings");
    TrayTelemetry::TaskbarSearchOptionChanged<unsigned long const &>(v26);
    return;
  }
  if ( a2 == 433 || a2 == 434 )
    goto LABEL_84;
  if ( a2 != 435 )
  {
    if ( a2 == 440 )
    {
      USDWORDW = SHRegGetUSDWORDW(this, L"TaskbarAppsVisibleInTabletMode", 0, a4);
      v17 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              L"TaskbarAppsVisibleInTabletMode",
              USDWORDW == 0);
      if ( v17 >= 0 )
      {
        SendMessageW(*(this - 6), 0x5CAu, 1u, 0);
        v23 = 0;
        v24[0] = USDWORDW == 0;
        TaskbarAppIconsTelemetry::TaskbarAppIconsSettingChanged<bool,bool>(v24, &v23);
        return;
      }
      v18 = 6986;
    }
    else
    {
      if ( a2 != 443 )
        return;
      v16 = SHRegGetUSDWORDW(this, L"TaskbarAutoHideInTabletMode", 0, a4);
      v17 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              L"TaskbarAutoHideInTabletMode",
              v16 == 0);
      if ( v17 >= 0 )
      {
        SendMessageW(*(this - 6), 0x5CAu, 0xAu, 0);
        return;
      }
      v18 = 6996;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
      (const char *)(unsigned int)v17,
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
0x1400abc30  push    rbp
0x1400abc32  push    rbx
0x1400abc33  push    rsi
0x1400abc34  push    rdi
0x1400abc35  push    r14
0x1400abc37  lea     rbp, [rsp-0B0h]
0x1400abc3f  sub     rsp, 1B0h
0x1400abc46  mov     rax, cs:__security_cookie
0x1400abc4d  xor     rax, rsp
0x1400abc50  mov     [rbp+0D0h+var_30], rax
0x1400abc57  mov     rdi, r8
0x1400abc5a  mov     ebx, edx
0x1400abc5c  mov     rsi, rcx
0x1400abc5f  mov     edx, 1F7h; unsigned __int64
0x1400abc64  cmp     ebx, edx
0x1400abc66  ja      loc_1400AC2E6
0x1400abc6c  jz      loc_1400AC2DC
0x1400abc72  lea     eax, [rdx-57h]
0x1400abc75  cmp     ebx, eax
0x1400abc77  ja      loc_1400AC031
0x1400abc7d  jz      loc_1400ABFD2
0x1400abc83  lea     eax, [rdx-60h]
0x1400abc86  cmp     ebx, eax
0x1400abc88  ja      loc_1400ABF21
0x1400abc8e  jz      loc_1400ABE6A
0x1400abc94  mov     eax, ebx
0x1400abc96  sub     eax, 191h
0x1400abc9b  jz      loc_1400ABE5C
0x1400abca1  sub     eax, 1
0x1400abca4  jz      loc_1400ABE0B
0x1400abcaa  sub     eax, 1
0x1400abcad  jz      short loc_1400ABCBD
0x1400abcaf  sub     eax, 1
0x1400abcb2  jz      short loc_1400ABCBD
0x1400abcb4  cmp     eax, 1
0x1400abcb7  jnz     loc_1400AC506
0x1400abcbd  xor     edi, edi
0x1400abcbf  mov     r14d, edi
0x1400abcc2  mov     dword ptr [rbp+0D0h+var_40], 1
0x1400abccc  lea     rdx, [rbp+0D0h+var_40]
0x1400abcd3  lea     rcx, [rsp+1D0h+var_190]
0x1400abcd8  call    ??$Start@W4WindowArrangementContextMenuSource@TrayTelemetry@@@WindowArrangementContextMenu@TrayTelemetry@@SA?AV01@$$QEAW4WindowArrangementContextMenuSource@1@@Z; TrayTelemetry::WindowArrangementContextMenu::Start<TrayTelemetry::WindowArrangementContextMenuSource>(TrayTelemetry::WindowArrangementContextMenuSource &&)
0x1400abcdd  nop
0x1400abcde  mov     rcx, rsi; this
0x1400abce1  call    ?CanTileAnyWindows@CTray@@UEAAHXZ; CTray::CanTileAnyWindows(void)
0x1400abce6  test    eax, eax
0x1400abce8  jz      loc_1400ABDF8
0x1400abcee  mov     r14d, 193h
0x1400abcf4  cmp     ebx, r14d
0x1400abcf7  jnz     short loc_1400ABD00
0x1400abcf9  mov     edx, 217h
0x1400abcfe  jmp     short loc_1400ABD11
0x1400abd00  mov     edx, 21Ah
0x1400abd05  lea     eax, [rdx-2]
0x1400abd08  cmp     ebx, 194h
0x1400abd0e  cmovz   edx, eax; unsigned int
0x1400abd11  lea     rcx, [rsi-38h]; this
0x1400abd15  call    ?SaveWindowPositions@CTray@@QEAAXI@Z; CTray::SaveWindowPositions(uint)
0x1400abd1a  mov     [rsp+1D0h+lpKids], 1; __int64
0x1400abd23  xor     r9d, r9d; HWND
0x1400abd26  xor     edx, edx; HMONITOR
0x1400abd28  lea     r8d, [r9+3]; unsigned int
0x1400abd2c  mov     rcx, rsi; this
0x1400abd2f  call    ?AppBarNotifyAll@CTray@@UEAAXPEAUHMONITOR__@@IPEAUHWND__@@_J@Z; CTray::AppBarNotifyAll(HMONITOR__ *,uint,HWND__ *,__int64)
0x1400abd34  mov     [rsp+1D0h+lpKids], rdi; lpKids
0x1400abd39  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hwndParent
0x1400abd40  cmp     ebx, r14d
0x1400abd43  jnz     short loc_1400ABD77
0x1400abd45  xor     r9d, r9d; cKids
0x1400abd48  xor     r8d, r8d; lpRect
0x1400abd4b  xor     edx, edx; wHow
0x1400abd4d  call    cs:__imp_CascadeWindows
0x1400abd54  nop     dword ptr [rax+rax+00h]
0x1400abd59  test    ax, ax
0x1400abd5c  jz      short loc_1400ABD63
0x1400abd5e  mov     r14d, edi
0x1400abd61  jmp     short loc_1400ABD6B
0x1400abd63  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400abd68  mov     r14d, eax
0x1400abd6b  lea     rcx, [rsp+1D0h+var_190]; this
0x1400abd70  call    ?CascadeWindows@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::CascadeWindows(void)
0x1400abd75  jmp     short loc_1400ABDBF
0x1400abd77  mov     edx, edi
0x1400abd79  cmp     ebx, 194h
0x1400abd7f  setnz   dl; wHow
0x1400abd82  xor     r9d, r9d; cKids
0x1400abd85  xor     r8d, r8d; lpRect
0x1400abd88  call    cs:__imp_TileWindows
0x1400abd8f  nop     dword ptr [rax+rax+00h]
0x1400abd94  test    ax, ax
0x1400abd97  jz      short loc_1400ABD9E
0x1400abd99  mov     r14d, edi
0x1400abd9c  jmp     short loc_1400ABDA6
0x1400abd9e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400abda3  mov     r14d, eax
0x1400abda6  lea     rcx, [rsp+1D0h+var_190]; this
0x1400abdab  cmp     ebx, 194h
0x1400abdb1  jnz     short loc_1400ABDBA
0x1400abdb3  call    ?WindowsSideBySide@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::WindowsSideBySide(void)
0x1400abdb8  jmp     short loc_1400ABDBF
0x1400abdba  call    ?ShowWindowsStacked@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::ShowWindowsStacked(void)
0x1400abdbf  mov     [rsi+0A4h], edi
0x1400abdc5  xor     r9d, r9d; lpTimerFunc
0x1400abdc8  lea     edx, [r9+12h]; nIDEvent
0x1400abdcc  mov     r8d, 1F4h; uElapse
0x1400abdd2  mov     rcx, [rsi-30h]; hWnd
0x1400abdd6  call    cs:__imp_SetTimer
0x1400abddd  nop     dword ptr [rax+rax+00h]
0x1400abde2  mov     [rsp+1D0h+lpKids], rdi; __int64
0x1400abde7  xor     r9d, r9d; HWND
0x1400abdea  xor     edx, edx; HMONITOR
0x1400abdec  lea     r8d, [r9+3]; unsigned int
0x1400abdf0  mov     rcx, rsi; this
0x1400abdf3  call    ?AppBarNotifyAll@CTray@@UEAAXPEAUHMONITOR__@@IPEAUHWND__@@_J@Z; CTray::AppBarNotifyAll(HMONITOR__ *,uint,HWND__ *,__int64)
0x1400abdf8  mov     edx, r14d
0x1400abdfb  lea     rcx, [rsp+1D0h+var_190]
0x1400abe00  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400abe05  nop
0x1400abe06  jmp     loc_1400AC022
0x1400abe0b  mov     rcx, [rcx-30h]; hWnd
0x1400abe0f  call    cs:__imp_UpdateWindow
0x1400abe16  nop     dword ptr [rax+rax+00h]
0x1400abe1b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1400abe20  call    cs:__imp_Sleep
0x1400abe27  nop     dword ptr [rax+rax+00h]
0x1400abe2c  lea     rcx, [rsi-38h]; this
0x1400abe30  call    ?OnEndSessionInitiated@CTray@@IEAAXXZ; CTray::OnEndSessionInitiated(void)
0x1400abe35  mov     rcx, rsi; this
0x1400abe38  call    ?SaveTrayAndDesktop@CTray@@UEAAXXZ; CTray::SaveTrayAndDesktop(void)
0x1400abe3d  mov     rax, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; HWND__ * v_hwndDesktop
0x1400abe44  mov     [rbp+0D0h+var_40], rax
0x1400abe4b  lea     rdx, [rbp+0D0h+var_40]
0x1400abe52  call    Windows__Internal__ComTaskPool__QueueTask__lambda_1aaafe5cef8d3e2bff0408f882a45e8e___
0x1400abe57  jmp     loc_1400AC506
0x1400abe5c  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400abe60  call    ?_RunDlg@CTray@@IEAAXXZ; CTray::_RunDlg(void)
0x1400abe65  jmp     loc_1400AC506
0x1400abe6a  xor     edi, edi
0x1400abe6c  cmp     [rcx+1AAh], dil
0x1400abe73  jnz     loc_1400AC506
0x1400abe79  cmp     [rbp+0D0h+arg_20], dil
0x1400abe80  jz      short loc_1400ABEF1
0x1400abe82  cmp     [rcx+1A9h], dil
0x1400abe89  jnz     short loc_1400ABE94
0x1400abe8b  cmp     [rcx+1A8h], dil
0x1400abe92  jz      short loc_1400ABED6
0x1400abe94  call    cs:__imp_GetForegroundWindow
0x1400abe9b  nop     dword ptr [rax+rax+00h]
0x1400abea0  mov     dword ptr [rbp+0D0h+var_40], edi
0x1400abea6  test    rax, rax
0x1400abea9  jz      short loc_1400ABED6
0x1400abeab  lea     rdx, [rbp+0D0h+var_40]
0x1400abeb2  mov     rcx, rax
0x1400abeb5  call    cs:__imp_GetWindowBand
0x1400abebc  nop     dword ptr [rax+rax+00h]
0x1400abec1  test    eax, eax
0x1400abec3  jz      loc_1400AC506
0x1400abec9  cmp     dword ptr [rbp+0D0h+var_40], 1
0x1400abed0  jnz     loc_1400AC506
0x1400abed6  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x1400abedc  neg     eax
0x1400abede  sbb     edx, edx
0x1400abee0  add     edx, 3
0x1400abee3  lea     rcx, [rsi-38h]
0x1400abee7  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x1400abeec  jmp     loc_1400AC506
0x1400abef1  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x1400abef7  neg     eax
0x1400abef9  sbb     edx, edx
0x1400abefb  add     edx, 3
0x1400abefe  add     rcx, 0FFFFFFFFFFFFFFC8h
0x1400abf02  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x1400abf07  cmp     cs:?g_fDesktopRaised@@3HA, edi; int g_fDesktopRaised
0x1400abf0d  setz    [rsp+1D0h+var_1A0]
0x1400abf12  lea     rcx, [rsp+1D0h+var_1A0]
0x1400abf17  call    ??$ContextMenuShowDesktop@_N@TrayTelemetry@@SAX$$QEA_N@Z; TrayTelemetry::ContextMenuShowDesktop<bool>(bool &&)
0x1400abf1c  jmp     loc_1400AC506
0x1400abf21  sub     ebx, 198h
0x1400abf27  jz      loc_1400ABFB6
0x1400abf2d  sub     ebx, 2
0x1400abf30  jz      short loc_1400ABF93
0x1400abf32  sub     ebx, 1
0x1400abf35  jz      short loc_1400ABF85
0x1400abf37  sub     ebx, 2
0x1400abf3a  jz      short loc_1400ABF67
0x1400abf3c  cmp     ebx, 2
0x1400abf3f  jnz     loc_1400AC506
0x1400abf45  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400abf49  xor     edi, edi
0x1400abf4b  cmp     [rcx+1E2h], dil
0x1400abf52  jnz     loc_1400AC506
0x1400abf58  xor     r8d, r8d; void *
0x1400abf5b  xor     edx, edx; int
0x1400abf5d  call    ?_MinimizeAll@CTray@@IEAAHHPEAX@Z; CTray::_MinimizeAll(int,void *)
0x1400abf62  jmp     loc_1400AC506
0x1400abf67  mov     rcx, [rcx+3F0h]
0x1400abf6e  mov     rax, [rcx]
0x1400abf71  mov     rdx, r9
0x1400abf74  mov     rax, [rax+178h]
0x1400abf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400abf80  jmp     loc_1400AC506
0x1400abf85  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400abf89  call    ?_ActivateWindowSwitcher@CTray@@IEAAJXZ; CTray::_ActivateWindowSwitcher(void)
0x1400abf8e  jmp     loc_1400AC506
0x1400abf93  xor     r9d, r9d; pfnCallback
0x1400abf96  xor     edx, edx; pData
0x1400abf98  mov     r8d, 2001h; flags
0x1400abf9e  lea     rcx, ?_EjectThreadProc@@YAKPEAX@Z; pfnThreadProc
0x1400abfa5  call    cs:__imp_SHCreateThread
0x1400abfac  nop     dword ptr [rax+rax+00h]
0x1400abfb1  jmp     loc_1400AC506
0x1400abfb6  mov     edx, 2
0x1400abfbb  xor     r9d, r9d
0x1400abfbe  xor     r8d, r8d
0x1400abfc1  mov     rcx, cs:g_hinstCabinet
0x1400abfc8  call    ?Launch@LaunchHelpers@@YAXPEAUHINSTANCE__@@W4LaunchEntity@1@_NPEAUHWND__@@@Z; LaunchHelpers::Launch(HINSTANCE__ *,LaunchHelpers::LaunchEntity,bool,HWND__ *)
0x1400abfcd  jmp     loc_1400AC506
0x1400abfd2  xor     edi, edi
0x1400abfd4  cmp     [rcx+1AAh], dil
0x1400abfdb  jnz     loc_1400AC506
0x1400abfe1  mov     dword ptr [rbp+0D0h+var_40], 1
0x1400abfeb  lea     rdx, [rbp+0D0h+var_40]
0x1400abff2  lea     rcx, [rsp+1D0h+var_190]
0x1400abff7  call    ??$Start@W4WindowArrangementContextMenuSource@TrayTelemetry@@@WindowArrangementContextMenu@TrayTelemetry@@SA?AV01@$$QEAW4WindowArrangementContextMenuSource@1@@Z; TrayTelemetry::WindowArrangementContextMenu::Start<TrayTelemetry::WindowArrangementContextMenuSource>(TrayTelemetry::WindowArrangementContextMenuSource &&)
0x1400abffc  nop
0x1400abffd  lea     rcx, [rsp+1D0h+var_190]; this
0x1400ac002  call    ?UndoWindowArrangement@WindowArrangementContextMenu@TrayTelemetry@@QEAAXXZ; TrayTelemetry::WindowArrangementContextMenu::UndoWindowArrangement(void)
0x1400ac007  xor     r8d, r8d; void *
0x1400ac00a  xor     edx, edx; int
0x1400ac00c  lea     rcx, [rsi-38h]; this
0x1400ac010  call    ?_RestoreWindowPositions@CTray@@IEAAHHPEAX@Z; CTray::_RestoreWindowPositions(int,void *)
0x1400ac015  xor     edx, edx
0x1400ac017  lea     rcx, [rsp+1D0h+var_190]
0x1400ac01c  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400ac021  nop
0x1400ac022  lea     rcx, [rsp+1D0h+var_190]; this
0x1400ac027  call    ??1WindowArrangementContextMenu@TrayTelemetry@@QEAA@XZ; TrayTelemetry::WindowArrangementContextMenu::~WindowArrangementContextMenu(void)
0x1400ac02c  jmp     loc_1400AC506
0x1400ac031  mov     eax, 1B0h
0x1400ac036  cmp     ebx, eax
0x1400ac038  ja      loc_1400AC147
0x1400ac03e  jz      loc_1400AC284
0x1400ac044  sub     ebx, 1A3h
0x1400ac04a  jz      loc_1400AC126
0x1400ac050  sub     ebx, 2
0x1400ac053  jz      loc_1400AC115
0x1400ac059  sub     ebx, 3
0x1400ac05c  jz      short loc_1400AC082
0x1400ac05e  sub     ebx, 1
0x1400ac061  jz      short loc_1400AC082
0x1400ac063  cmp     ebx, 5
0x1400ac066  jnz     loc_1400AC506
0x1400ac06c  mov     rcx, [rcx+3F0h]
0x1400ac073  mov     rax, [rcx]
0x1400ac076  mov     rax, [rax+190h]
0x1400ac07d  jmp     loc_1400AC478
0x1400ac082  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1400ac089  jz      short loc_1400AC0B0
0x1400ac08b  lea     rax, [rbp+0D0h+var_40]
0x1400ac092  mov     [rsp+1D0h+lpKids], rax
0x1400ac097  mov     r9d, 1
0x1400ac09d  lea     rdx, Taskbar_LockState_ChangeNotify_Start
0x1400ac0a4  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400ac0ab  call    McGenEventWrite_EventWriteTransfer
0x1400ac0b0  mov     rcx, [rsi+3F0h]
0x1400ac0b7  mov     rax, [rcx]
0x1400ac0ba  xor     edx, edx
0x1400ac0bc  mov     rax, [rax+170h]
0x1400ac0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ac0c8  mov     rcx, [rsi+3F0h]
0x1400ac0cf  mov     rax, [rcx]
0x1400ac0d2  mov     rax, [rax+1C8h]
0x1400ac0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ac0de  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1400ac0e5  jz      loc_1400AC506
0x1400ac0eb  lea     rax, [rbp+0D0h+var_40]
0x1400ac0f2  mov     [rsp+1D0h+lpKids], rax
0x1400ac0f7  mov     r9d, 1
0x1400ac0fd  lea     rdx, Taskbar_LockState_ChangeNotify_Stop
0x1400ac104  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400ac10b  call    McGenEventWrite_EventWriteTransfer
0x1400ac110  jmp     loc_1400AC506
0x1400ac115  mov     r9, [rcx-30h]
0x1400ac119  mov     r8b, 1
0x1400ac11c  mov     edx, 1
0x1400ac121  jmp     loc_1400ABFC1
0x1400ac126  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x1400ac12a  xor     edi, edi
0x1400ac12c  cmp     [rcx+1E2h], dil
0x1400ac133  jnz     loc_1400AC506
0x1400ac139  lea     r8d, [rdi+1]; __int64
0x1400ac13d  call    ?_HandleGlobalHotkey@CTray@@IEAAX_K_J@Z; CTray::_HandleGlobalHotkey(unsigned __int64,__int64)
0x1400ac142  jmp     loc_1400AC506
0x1400ac147  mov     eax, ebx
0x1400ac149  sub     eax, 1B1h
0x1400ac14e  jz      loc_1400AC284
0x1400ac154  sub     eax, 1
0x1400ac157  jz      loc_1400AC284
0x1400ac15d  sub     eax, 1
0x1400ac160  jz      loc_1400AC26E
  ... truncated ...
```
