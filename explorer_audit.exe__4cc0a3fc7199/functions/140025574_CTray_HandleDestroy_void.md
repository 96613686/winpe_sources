# CTray::_HandleDestroy(void)

- ea: `0x140025574`
- end: `0x14002586d`
- name: `?_HandleDestroy@CTray@@IEAA_JXZ`
- size: `761`
- prototype: `__int64 __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14001d860`

## callees

- `0x140007a10`
- `0x14000d890`
- `0x140015a38`
- `0x14001f04c`
- `0x140025574`
- `0x140025874`
- `0x140025b0c`
- `0x140025b38`
- `0x14007f978`
- `0x1400a3450`
- `0x1400a78ec`
- `0x1400a9284`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140025826`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140025826`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400256af`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400256c7`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400256af`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400256c7`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyDeregister` at `0x140025716`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyDeregister` at `0x140025716`
- `USER32!UnregisterHotKey` at `0x1400256f4`
- `USER32!UnregisterHotKey` at `0x1400256f4`
- `SndVolSSO!__imp_?AudioHIDShutdown@@YAXXZ` at `0x1400256d5`
- `SndVolSSO!__imp_?AudioHIDShutdown@@YAXXZ` at `0x1400256d5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002562d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002563e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002564f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140025660`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140025671`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002562d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002563e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14002564f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140025660`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x140025671`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140025810`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140025846`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140025810`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostQuitMessage` at `0x140025846`
- `AppResolver!__imp_SHRegisterDarwinLink` at `0x1400256e3`
- `AppResolver!__imp_SHRegisterDarwinLink` at `0x1400256e3`

## string_xrefs

- `0x140025637`: `TaskbarDPI_NotificationArea`
- `0x14002566a`: `TaskbarMonitor`
- `0x140025648`: `TaskbarDPI_Deskband`
- `0x140025626`: `TaskbarDPI_AllTaskbars`

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
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, &CTray_Destroy_Info, a3, 1);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::GetImpl'::`2'::impl) )
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
    CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy((char *)this + 688);
  v_hwndTray = 0;
  PostQuitMessage(0);
  return 0;
}

```

## disassembly

```asm
0x140025574  mov     r11, rsp
0x140025577  mov     [r11+10h], rbx
0x14002557b  mov     [r11+18h], rsi
0x14002557f  push    rdi
0x140025580  sub     rsp, 70h
0x140025584  mov     rax, cs:__security_cookie
0x14002558b  xor     rax, rsp
0x14002558e  mov     [rsp+78h+var_10], rax
0x140025593  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14002559a  mov     rbx, rcx
0x14002559d  jz      short loc_1400255C0
0x14002559f  lea     rax, [r11-20h]
0x1400255a3  mov     r9d, 1
0x1400255a9  lea     rdx, CTray_Destroy_Info
0x1400255b0  mov     [r11-58h], rax
0x1400255b4  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1400255bb  call    McGenEventWrite_EventWriteTransfer
0x1400255c0  lea     rcx, [rbx+2C0h]; this
0x1400255c7  call    ?Shutdown@CStateTelemetryHandler@StateCapture@@QEAAXXZ; StateCapture::CStateTelemetryHandler::Shutdown(void)
0x1400255cc  mov     rcx, [rbx+0A8h]
0x1400255d3  xor     esi, esi
0x1400255d5  mov     dword ptr [rbx+1E8h], 1
0x1400255df  test    rcx, rcx
0x1400255e2  jz      short loc_140025622
0x1400255e4  mov     rax, [rcx]
0x1400255e7  lea     r8d, [rsi+3]
0x1400255eb  mov     [rsp+78h+var_50], rsi
0x1400255f0  lea     rdx, CGID_ShellServiceObject
0x1400255f7  xor     r9d, r9d
0x1400255fa  mov     [rsp+78h+var_58], rsi
0x1400255ff  mov     rax, [rax+20h]
0x140025603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025608  mov     rcx, [rbx+0A8h]
0x14002560f  mov     rax, [rcx]
0x140025612  mov     rax, [rax+10h]
0x140025616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002561b  mov     [rbx+0A8h], rsi
0x140025622  mov     rcx, [rbx+8]; hWnd
0x140025626  lea     rdx, aTaskbardpiAllt; "TaskbarDPI_AllTaskbars"
0x14002562d  call    cs:__imp_RemovePropW
0x140025633  mov     rcx, [rbx+8]; hWnd
0x140025637  lea     rdx, aTaskbardpiNoti; "TaskbarDPI_NotificationArea"
0x14002563e  call    cs:__imp_RemovePropW
0x140025644  mov     rcx, [rbx+8]; hWnd
0x140025648  lea     rdx, aTaskbardpiDesk; "TaskbarDPI_Deskband"
0x14002564f  call    cs:__imp_RemovePropW
0x140025655  mov     rcx, [rbx+8]; hWnd
0x140025659  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x140025660  call    cs:__imp_RemovePropW
0x140025666  mov     rcx, [rbx+8]; hWnd
0x14002566a  lea     rdx, aTaskbarmonitor; "TaskbarMonitor"
0x140025671  call    cs:__imp_RemovePropW
0x140025677  mov     rcx, [rbx+190h]; hMem
0x14002567e  call    ?_DestroySavedWindowPositions@@YAXPEAUWINDOWPOSITIONS@@@Z; _DestroySavedWindowPositions(WINDOWPOSITIONS *)
0x140025683  mov     edi, 14h
0x140025688  mov     [rbx+190h], rsi
0x14002568f  xorps   xmm0, xmm0
0x140025692  mov     [rbx+1F4h], esi
0x140025698  xor     r9d, r9d; fWinIni
0x14002569b  mov     [rsp+78h+pvParam], edi
0x14002569f  lea     r8, [rsp+78h+pvParam]; pvParam
0x1400256a4  mov     edx, edi; uiParam
0x1400256a6  lea     ecx, [rdi+17h]; uiAction
0x1400256a9  movdqu  [rsp+78h+var_34], xmm0
0x1400256af  call    cs:__imp_SystemParametersInfoW
0x1400256b5  and     dword ptr [rsp+78h+var_34+0Ch], 0FFFFFFF7h
0x1400256ba  lea     r8, [rsp+78h+pvParam]; pvParam
0x1400256bf  xor     r9d, r9d; fWinIni
0x1400256c2  lea     ecx, [rdi+18h]; uiAction
0x1400256c5  mov     edx, edi; uiParam
0x1400256c7  call    cs:__imp_SystemParametersInfoW
0x1400256cd  cmp     [rbx+0E8h], esi
0x1400256d3  jz      short loc_1400256DB
0x1400256d5  call    cs:__imp_?AudioHIDShutdown@@YAXXZ; AudioHIDShutdown(void)
0x1400256db  xor     edx, edx
0x1400256dd  xor     ecx, ecx
0x1400256df  lea     r8d, [rdx+1]
0x1400256e3  call    cs:__imp_SHRegisterDarwinLink
0x1400256e9  mov     edi, 1F4h
0x1400256ee  mov     rcx, [rbx+8]; hWnd
0x1400256f2  mov     edx, edi; id
0x1400256f4  call    cs:__imp_UnregisterHotKey
0x1400256fa  inc     edi
0x1400256fc  cmp     edi, 254h
0x140025702  jl      short loc_1400256EE
0x140025704  mov     rcx, rbx; this
0x140025707  call    ?_UnregisterTouchpadActions@CTray@@IEAAXXZ; CTray::_UnregisterTouchpadActions(void)
0x14002570c  mov     ecx, [rbx+1CCh]; ulID
0x140025712  test    ecx, ecx
0x140025714  jz      short loc_140025722
0x140025716  call    cs:__imp_SHChangeNotifyDeregister
0x14002571c  mov     [rbx+1CCh], esi
0x140025722  mov     rcx, [rbx+228h]
0x140025729  test    rcx, rcx
0x14002572c  jz      short loc_14002575B
0x14002572e  mov     rax, [rcx]
0x140025731  xor     edx, edx
0x140025733  mov     rax, [rax+40h]
0x140025737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002573c  mov     rcx, [rbx+228h]
0x140025743  mov     [rbx+228h], rsi
0x14002574a  test    rcx, rcx
0x14002574d  jz      short loc_14002575B
0x14002574f  mov     rax, [rcx]
0x140025752  mov     rax, [rax+10h]
0x140025756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002575b  mov     rcx, [rbx+238h]
0x140025762  test    rcx, rcx
0x140025765  jz      short loc_14002577A
0x140025767  mov     [rbx+238h], rsi
0x14002576e  mov     rax, [rcx]
0x140025771  mov     rax, [rax+10h]
0x140025775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002577a  mov     rcx, [rbx+230h]
0x140025781  mov     [rbx+230h], rsi
0x140025788  test    rcx, rcx
0x14002578b  jz      short loc_140025799
0x14002578d  mov     rax, [rcx]
0x140025790  mov     rax, [rax+10h]
0x140025794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025799  mov     rcx, rbx; this
0x14002579c  call    ?_UnregisterForNotifications@CTray@@IEAAXXZ; CTray::_UnregisterForNotifications(void)
0x1400257a1  mov     rcx, [rbx+428h]
0x1400257a8  mov     rax, [rcx]
0x1400257ab  mov     rax, [rax+50h]
0x1400257af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400257b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest> `wil::Feature<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::GetImpl(void)'::`2'::impl
0x1400257bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TaskbarInitializationTest>::__private_IsEnabled(void)
0x1400257c0  test    al, al
0x1400257c2  jnz     short loc_140025801
0x1400257c4  lea     rdi, [rbx+370h]
0x1400257cb  mov     rcx, [rdi]
0x1400257ce  test    rcx, rcx
0x1400257d1  jz      short loc_14002580E
0x1400257d3  add     rcx, 8
0x1400257d7  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1400257dc  test    al, al
0x1400257de  jz      short loc_14002580E
0x1400257e0  lea     rdx, [rsp+78h+var_20]
0x1400257e5  mov     rcx, rdi
0x1400257e8  call    ??C?$tip_test@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::operator->(void)
0x1400257ed  mov     rcx, [rax]
0x1400257f0  mov     byte ptr [rcx+11Eh], 1
0x1400257f7  lea     rcx, [rsp+78h+var_20]
0x1400257fc  call    ??1?$test_data_control@V?$merged_data@U_tip_PrimaryTaskbarInitialization@TaskbarTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>::~test_data_control<tip2::details::merged_data<TaskbarTip::_tip_PrimaryTaskbarInitialization,TaskbarTip::_tip_PrimaryTaskbarInitialization>>(void)
0x140025801  mov     r8b, 1; bool
0x140025804  xor     edx, edx; bool
0x140025806  mov     rcx, rbx; this
0x140025809  call    ?_TryCompleteTaskbarTests@CTray@@AEAAX_N0@Z; CTray::_TryCompleteTaskbarTests(bool,bool)
0x14002580e  xor     ecx, ecx; nExitCode
0x140025810  call    cs:__imp_PostQuitMessage
0x140025816  cmp     cs:v_hwndTray, rsi
0x14002581d  jz      short loc_14002582C
0x14002581f  lea     rcx, [rbx+158h]; lpCriticalSection
0x140025826  call    cs:__imp_DeleteCriticalSection
0x14002582c  lea     rcx, [rbx+2B0h]
0x140025833  cmp     [rcx], rsi
0x140025836  jz      short loc_14002583D
0x140025838  call    ?Destroy@?$CDSA_Base@UTRAYMONITORINFO@TrayCommon@@@@QEAAHXZ; CDSA_Base<TrayCommon::TRAYMONITORINFO>::Destroy(void)
0x14002583d  xor     ecx, ecx; nExitCode
0x14002583f  mov     cs:v_hwndTray, rsi
0x140025846  call    cs:__imp_PostQuitMessage
0x14002584c  xor     eax, eax
0x14002584e  mov     rcx, [rsp+78h+var_10]
0x140025853  xor     rcx, rsp; StackCookie
0x140025856  call    __security_check_cookie
0x14002585b  lea     r11, [rsp+78h+var_8]
0x140025860  mov     rbx, [r11+18h]
0x140025864  mov     rsi, [r11+20h]
0x140025868  mov     rsp, r11
0x14002586b  pop     rdi
0x14002586c  retn
```
