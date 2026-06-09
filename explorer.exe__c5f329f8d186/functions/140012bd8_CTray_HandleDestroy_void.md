# CTray::_HandleDestroy(void)

- ea: `0x140012bd8`
- end: `0x140012f26`
- name: `?_HandleDestroy@CTray@@IEAA_JXZ`
- size: `846`
- prototype: `__int64 __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140019eb0`

## callees

- `0x14000bb20`
- `0x140011214`
- `0x140012bd8`
- `0x140012f2c`
- `0x1400131e8`
- `0x14001321c`
- `0x140018c20`
- `0x140018f40`
- `0x14002072c`
- `0x1400a9764`
- `0x1400ad828`
- `0x1400aef1c`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012ed2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012ed2`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140012d31`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140012d4f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140012d31`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140012d4f`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyDeregister` at `0x140012db6`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyDeregister` at `0x140012db6`
- `USER32!UnregisterHotKey` at `0x140012d8e`
- `USER32!UnregisterHotKey` at `0x140012d8e`
- `SndVolSSO!__imp_?AudioHIDShutdown@@YAXXZ` at `0x140012d63`
- `SndVolSSO!__imp_?AudioHIDShutdown@@YAXXZ` at `0x140012d63`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012c91`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012ca8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012cbf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012cd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012ced`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012c91`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012ca8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012cbf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012cd6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140012ced`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140012eb6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140012ef8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140012eb6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140012ef8`
- `AppResolver!__imp_SHRegisterDarwinLink` at `0x140012d77`
- `AppResolver!__imp_SHRegisterDarwinLink` at `0x140012d77`

## string_xrefs

- `0x140012ca1`: `TaskbarDPI_NotificationArea`
- `0x140012ce6`: `TaskbarMonitor`
- `0x140012cb8`: `TaskbarDPI_Deskband`
- `0x140012c8a`: `TaskbarDPI_AllTaskbars`

## pseudocode

```c
__int64 __fastcall CTray::_HandleDestroy(CTray *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  int i; // edi
  ULONG v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int pvParam; // [rsp+40h] [rbp-38h] BYREF
  __int128 v14; // [rsp+44h] [rbp-34h]
  _BYTE v15[16]; // [rsp+58h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, CTray_Destroy_Info, a3, 1, v15);
  StateCapture::CStateTelemetryHandler::Shutdown((CTray *)((char *)this + 704));
  v4 = *((_QWORD *)this + 21);
  *((_DWORD *)this + 122) = 1;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, const GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 32LL))(
      v4,
      &CGID_ShellServiceObject,
      3,
      0,
      0,
      0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 16LL))(*((_QWORD *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  RemovePropW(*((HWND *)this + 1), L"TaskbarDPI_AllTaskbars");
  RemovePropW(*((HWND *)this + 1), L"TaskbarDPI_NotificationArea");
  RemovePropW(*((HWND *)this + 1), L"TaskbarDPI_Deskband");
  RemovePropW(*((HWND *)this + 1), L"AllowConsentToStealFocus");
  RemovePropW(*((HWND *)this + 1), L"TaskbarMonitor");
  _DestroySavedWindowPositions(*((HLOCAL *)this + 50));
  *((_QWORD *)this + 50) = 0;
  *((_DWORD *)this + 125) = 0;
  pvParam = 20;
  v14 = 0;
  SystemParametersInfoW(0x2Bu, 0x14u, &pvParam, 0);
  HIDWORD(v14) &= ~8u;
  SystemParametersInfoW(0x2Cu, 0x14u, &pvParam, 0);
  if ( *((_DWORD *)this + 58) )
    AudioHIDShutdown();
  SHRegisterDarwinLink(0, 0, 1);
  for ( i = 500; i < 596; ++i )
    UnregisterHotKey(*((HWND *)this + 1), i);
  CTray::_UnregisterTouchpadActions(this);
  v6 = *((_DWORD *)this + 115);
  if ( v6 )
  {
    SHChangeNotifyDeregister(v6);
    *((_DWORD *)this + 115) = 0;
  }
  v7 = *((_QWORD *)this + 69);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, 0);
    v8 = *((_QWORD *)this + 69);
    *((_QWORD *)this + 69) = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 71);
  if ( v9 )
  {
    *((_QWORD *)this + 71) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = *((_QWORD *)this + 70);
  *((_QWORD *)this + 70) = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  CTray::_UnregisterForNotifications(this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 80LL))(*((_QWORD *)this + 133));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::GetImpl'::`2'::impl) )
    goto LABEL_22;
  v11 = *((_QWORD *)this + 110);
  if ( v11 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v11 + 8) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::operator->(
                            (char *)this + 880,
                            v15)
             + 286LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::~test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>(v15);
LABEL_22:
    CTray::_TryCompleteTaskbarTests(this, 0, 1);
  }
  PostQuitMessage(0);
  if ( v_hwndTray )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  if ( *((_QWORD *)this + 86) )
    CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy();
  v_hwndTray = 0;
  PostQuitMessage(0);
  return 0;
}

```

## disassembly

```asm
0x140012bd8  mov     r11, rsp
0x140012bdb  mov     [r11+10h], rbx
0x140012bdf  mov     [r11+18h], rsi
0x140012be3  push    rdi
0x140012be4  sub     rsp, 70h
0x140012be8  mov     rax, cs:__security_cookie
0x140012bef  xor     rax, rsp
0x140012bf2  mov     [rsp+78h+var_10], rax
0x140012bf7  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x140012bfe  mov     rbx, rcx
0x140012c01  jz      short loc_140012C24
0x140012c03  lea     rax, [r11-20h]
0x140012c07  mov     r9d, 1
0x140012c0d  lea     rdx, CTray_Destroy_Info
0x140012c14  mov     [r11-58h], rax
0x140012c18  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140012c1f  call    McGenEventWrite_EventWriteTransfer
0x140012c24  lea     rcx, [rbx+2C0h]; this
0x140012c2b  call    ?Shutdown@CStateTelemetryHandler@StateCapture@@QEAAXXZ; StateCapture::CStateTelemetryHandler::Shutdown(void)
0x140012c30  mov     rcx, [rbx+0A8h]
0x140012c37  xor     esi, esi
0x140012c39  mov     dword ptr [rbx+1E8h], 1
0x140012c43  test    rcx, rcx
0x140012c46  jz      short loc_140012C86
0x140012c48  mov     rax, [rcx]
0x140012c4b  lea     r8d, [rsi+3]
0x140012c4f  mov     [rsp+78h+var_50], rsi
0x140012c54  lea     rdx, CGID_ShellServiceObject
0x140012c5b  xor     r9d, r9d
0x140012c5e  mov     [rsp+78h+var_58], rsi
0x140012c63  mov     rax, [rax+20h]
0x140012c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c6c  mov     rcx, [rbx+0A8h]
0x140012c73  mov     rax, [rcx]
0x140012c76  mov     rax, [rax+10h]
0x140012c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c7f  mov     [rbx+0A8h], rsi
0x140012c86  mov     rcx, [rbx+8]; hWnd
0x140012c8a  lea     rdx, String; "TaskbarDPI_AllTaskbars"
0x140012c91  call    cs:__imp_RemovePropW
0x140012c98  nop     dword ptr [rax+rax+00h]
0x140012c9d  mov     rcx, [rbx+8]; hWnd
0x140012ca1  lea     rdx, aTaskbardpiNoti; "TaskbarDPI_NotificationArea"
0x140012ca8  call    cs:__imp_RemovePropW
0x140012caf  nop     dword ptr [rax+rax+00h]
0x140012cb4  mov     rcx, [rbx+8]; hWnd
0x140012cb8  lea     rdx, aTaskbardpiDesk; "TaskbarDPI_Deskband"
0x140012cbf  call    cs:__imp_RemovePropW
0x140012cc6  nop     dword ptr [rax+rax+00h]
0x140012ccb  mov     rcx, [rbx+8]; hWnd
0x140012ccf  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x140012cd6  call    cs:__imp_RemovePropW
0x140012cdd  nop     dword ptr [rax+rax+00h]
0x140012ce2  mov     rcx, [rbx+8]; hWnd
0x140012ce6  lea     rdx, aTaskbarmonitor; "TaskbarMonitor"
0x140012ced  call    cs:__imp_RemovePropW
0x140012cf4  nop     dword ptr [rax+rax+00h]
0x140012cf9  mov     rcx, [rbx+190h]; hMem
0x140012d00  call    ?_DestroySavedWindowPositions@@YAXPEAUWINDOWPOSITIONS@@@Z; _DestroySavedWindowPositions(WINDOWPOSITIONS *)
0x140012d05  mov     edi, 14h
0x140012d0a  mov     [rbx+190h], rsi
0x140012d11  xorps   xmm0, xmm0
0x140012d14  mov     [rbx+1F4h], esi
0x140012d1a  xor     r9d, r9d; fWinIni
0x140012d1d  mov     [rsp+78h+pvParam], edi
0x140012d21  lea     r8, [rsp+78h+pvParam]; pvParam
0x140012d26  mov     edx, edi; uiParam
0x140012d28  lea     ecx, [rdi+17h]; uiAction
0x140012d2b  movdqu  [rsp+78h+var_34], xmm0
0x140012d31  call    cs:__imp_SystemParametersInfoW
0x140012d38  nop     dword ptr [rax+rax+00h]
0x140012d3d  and     dword ptr [rsp+78h+var_34+0Ch], 0FFFFFFF7h
0x140012d42  lea     r8, [rsp+78h+pvParam]; pvParam
0x140012d47  xor     r9d, r9d; fWinIni
0x140012d4a  lea     ecx, [rdi+18h]; uiAction
0x140012d4d  mov     edx, edi; uiParam
0x140012d4f  call    cs:__imp_SystemParametersInfoW
0x140012d56  nop     dword ptr [rax+rax+00h]
0x140012d5b  cmp     [rbx+0E8h], esi
0x140012d61  jz      short loc_140012D6F
0x140012d63  call    cs:__imp_?AudioHIDShutdown@@YAXXZ; AudioHIDShutdown(void)
0x140012d6a  nop     dword ptr [rax+rax+00h]
0x140012d6f  xor     edx, edx
0x140012d71  xor     ecx, ecx
0x140012d73  lea     r8d, [rdx+1]
0x140012d77  call    cs:__imp_SHRegisterDarwinLink
0x140012d7e  nop     dword ptr [rax+rax+00h]
0x140012d83  mov     edi, 1F4h
0x140012d88  mov     rcx, [rbx+8]; hWnd
0x140012d8c  mov     edx, edi; id
0x140012d8e  call    cs:__imp_UnregisterHotKey
0x140012d95  nop     dword ptr [rax+rax+00h]
0x140012d9a  inc     edi
0x140012d9c  cmp     edi, 254h
0x140012da2  jl      short loc_140012D88
0x140012da4  mov     rcx, rbx; this
0x140012da7  call    ?_UnregisterTouchpadActions@CTray@@IEAAXXZ; CTray::_UnregisterTouchpadActions(void)
0x140012dac  mov     ecx, [rbx+1CCh]; ulID
0x140012db2  test    ecx, ecx
0x140012db4  jz      short loc_140012DC8
0x140012db6  call    cs:__imp_SHChangeNotifyDeregister
0x140012dbd  nop     dword ptr [rax+rax+00h]
0x140012dc2  mov     [rbx+1CCh], esi
0x140012dc8  mov     rcx, [rbx+228h]
0x140012dcf  test    rcx, rcx
0x140012dd2  jz      short loc_140012E01
0x140012dd4  mov     rax, [rcx]
0x140012dd7  xor     edx, edx
0x140012dd9  mov     rax, [rax+40h]
0x140012ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012de2  mov     rcx, [rbx+228h]
0x140012de9  mov     [rbx+228h], rsi
0x140012df0  test    rcx, rcx
0x140012df3  jz      short loc_140012E01
0x140012df5  mov     rax, [rcx]
0x140012df8  mov     rax, [rax+10h]
0x140012dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e01  mov     rcx, [rbx+238h]
0x140012e08  test    rcx, rcx
0x140012e0b  jz      short loc_140012E20
0x140012e0d  mov     [rbx+238h], rsi
0x140012e14  mov     rax, [rcx]
0x140012e17  mov     rax, [rax+10h]
0x140012e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e20  mov     rcx, [rbx+230h]
0x140012e27  mov     [rbx+230h], rsi
0x140012e2e  test    rcx, rcx
0x140012e31  jz      short loc_140012E3F
0x140012e33  mov     rax, [rcx]
0x140012e36  mov     rax, [rax+10h]
0x140012e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e3f  mov     rcx, rbx; this
0x140012e42  call    ?_UnregisterForNotifications@CTray@@IEAAXXZ; CTray::_UnregisterForNotifications(void)
0x140012e47  mov     rcx, [rbx+428h]
0x140012e4e  mov     rax, [rcx]
0x140012e51  mov     rax, [rax+50h]
0x140012e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e5a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest> `wil::Feature<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::GetImpl(void)'::`2'::impl
0x140012e61  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::__private_IsEnabled(void)
0x140012e66  test    al, al
0x140012e68  jnz     short loc_140012EA7
0x140012e6a  lea     rdi, [rbx+370h]
0x140012e71  mov     rcx, [rdi]
0x140012e74  test    rcx, rcx
0x140012e77  jz      short loc_140012EB4
0x140012e79  add     rcx, 8
0x140012e7d  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x140012e82  test    al, al
0x140012e84  jz      short loc_140012EB4
0x140012e86  lea     rdx, [rsp+78h+var_20]
0x140012e8b  mov     rcx, rdi
0x140012e8e  call    ??C?$tip_test@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::operator->(void)
0x140012e93  mov     rcx, [rax]
0x140012e96  mov     byte ptr [rcx+11Eh], 1
0x140012e9d  lea     rcx, [rsp+78h+var_20]
0x140012ea2  call    ??1?$test_data_control@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::~test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>(void)
0x140012ea7  mov     r8b, 1; bool
0x140012eaa  xor     edx, edx; bool
0x140012eac  mov     rcx, rbx; this
0x140012eaf  call    ?_TryCompleteTaskbarTests@CTray@@AEAAX_N0@Z; CTray::_TryCompleteTaskbarTests(bool,bool)
0x140012eb4  xor     ecx, ecx; nExitCode
0x140012eb6  call    cs:__imp_PostQuitMessage
0x140012ebd  nop     dword ptr [rax+rax+00h]
0x140012ec2  cmp     cs:v_hwndTray, rsi
0x140012ec9  jz      short loc_140012EDE
0x140012ecb  lea     rcx, [rbx+158h]; lpCriticalSection
0x140012ed2  call    cs:__imp_DeleteCriticalSection
0x140012ed9  nop     dword ptr [rax+rax+00h]
0x140012ede  lea     rcx, [rbx+2B0h]
0x140012ee5  cmp     [rcx], rsi
0x140012ee8  jz      short loc_140012EEF
0x140012eea  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x140012eef  xor     ecx, ecx; nExitCode
0x140012ef1  mov     cs:v_hwndTray, rsi
0x140012ef8  call    cs:__imp_PostQuitMessage
0x140012eff  nop     dword ptr [rax+rax+00h]
0x140012f04  xor     eax, eax
0x140012f06  mov     rcx, [rsp+78h+var_10]
0x140012f0b  xor     rcx, rsp; StackCookie
0x140012f0e  call    __security_check_cookie
0x140012f13  lea     r11, [rsp+78h+var_8]
0x140012f18  mov     rbx, [r11+18h]
0x140012f1c  mov     rsi, [r11+20h]
0x140012f20  mov     rsp, r11
0x140012f23  pop     rdi
0x140012f24  retn
```
