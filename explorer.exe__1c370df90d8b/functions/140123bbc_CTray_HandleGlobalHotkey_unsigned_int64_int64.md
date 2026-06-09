# CTray::_HandleGlobalHotkey(unsigned __int64,__int64)

- ea: `0x140123bbc`
- end: `0x1401241f8`
- name: `?_HandleGlobalHotkey@CTray@@IEAAX_K_J@Z`
- size: `1596`
- prototype: `void __fastcall(CTray *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `46`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001d860`
- `0x1400a5b40`

## callees

- `0x140006ae0`
- `0x14001eba8`
- `0x1400258a0`
- `0x14002a2d8`
- `0x140074310`
- `0x1400743f4`
- `0x140088180`
- `0x14008bfcc`
- `0x14008e18c`
- `0x14008e284`
- `0x14009377c`
- `0x1400a5b40`
- `0x1400ab3ac`
- `0x1400b53fc`
- `0x1400f3194`
- `0x1400ff094`
- `0x1401040e0`
- `0x14010bd44`
- `0x1401135f8`
- `0x140113750`
- `0x1401137fc`
- `0x14011d2bc`
- `0x14011f838`
- `0x14011fa60`
- `0x14012397c`
- `0x140123acc`
- `0x140123bbc`
- `0x140124200`
- `0x140124280`
- `0x140124364`
- `0x140124510`
- `0x140124590`
- `0x140124710`
- `0x1401247f8`
- `0x1401248e0`
- `0x1401249c4`
- `0x140124a74`
- `0x140124b58`
- `0x140124c68`
- `0x140124d18`
- `0x140125868`
- `0x140125964`
- `0x140125c80`
- `0x140125fdc`
- `0x1401b9450`
- `0x1401db010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x140124151`
- `ntdll!RtlPublishWnfStateData` at `0x140124151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140123f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140124017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140124037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140123f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140124017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140124037`
- `SHELL32!__imp_SHRestricted` at `0x140123e42`
- `SHELL32!__imp_SHRestricted` at `0x140123e42`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123d86`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123dce`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123f0d`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123d86`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123dce`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x140123f0d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140123ec2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x140123ec2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140123de8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140123de8`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceActive` at `0x140123bf2`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceActive` at `0x140123bf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTray::_HandleGlobalHotkey(CTray *this, unsigned __int64 a2, unsigned __int16 a3)
{
  CTray *v6; // rcx
  __int64 v7; // rdx
  CTray *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // edx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  HWND ForegroundWindow; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  DWORD v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  unsigned __int8 v34; // cl
  TrayTelemetry *v35; // rcx
  int v36; // [rsp+20h] [rbp-188h]
  _QWORD v37[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl)
     || !(unsigned int)IsGamingFullScreenExperienceActive()
     || !CTray::_ShouldFilterHotkeyForGamingFullScreenExperience(v6, a2))
    && a2 != *((_QWORD *)this + 78) )
  {
    wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
    v37[0] = &TrayTelemetry::GlobalHotkeyPressedTriggered::`vftable';
    TrayTelemetry::GlobalHotkeyPressedTriggered::StartActivity((TrayTelemetry::GlobalHotkeyPressedTriggered *)v37, a2);
    *((_QWORD *)this + 78) = a2;
    if ( a2 <= 0x237 )
    {
      if ( a2 == 567 )
        goto LABEL_58;
      if ( a2 <= 0x1FD )
      {
        switch ( a2 )
        {
          case 0x1FDuLL:
            if ( !CTray::_IsDesktopInputContext() || SHRestricted(REST_NOFIND) )
              goto LABEL_16;
            v13 = 41094;
            break;
          case 0x1F6uLL:
            if ( CTray::_IsDesktopInputContext() )
              CTray::_RunDlg((HWND *)this, v15, v16);
            goto LABEL_16;
          case 0x1F7uLL:
            if ( !*((_BYTE *)this + 482) && CTray::_IsDesktopInputContext() )
            {
              DwmpActivateLivePreview(0, 0, 0, 2, 0);
              CTray::_MinimizeAll(this, 0, 0);
              SetForegroundWindow(v_hwndDesktop);
              if ( *((_BYTE *)this + 481) || *((_BYTE *)this + 480) )
                CTray::_HandleImmersiveHotKey(this, 1u, v14);
            }
            goto LABEL_16;
          case 0x1F8uLL:
            if ( !*((_BYTE *)this + 482) && CTray::_IsDesktopInputContext() )
            {
              DwmpActivateLivePreview(0, 0, 0, 2, 0);
              CTray::_RestoreWindowPositions(this, 0, 0);
            }
            goto LABEL_16;
          case 0x1F9uLL:
            v13 = 503;
            break;
          case 0x1FAuLL:
            if ( CTray::_IsDesktopInputContext()
              && !(unsigned int)_Restricted(g_hinstCabinet, *((HWND *)this + 1), &POLID_NoSetFolders) )
            {
              _InvokeVerbOnParsingName(*((HWND *)this + 1), v11, v12);
            }
            goto LABEL_16;
          case 0x1FBuLL:
LABEL_58:
            CTray::_HandleSearchPaneHotkey(this, 30, v9, v10);
            goto LABEL_16;
          default:
LABEL_15:
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 133) + 432LL))(
              *((_QWORD *)this + 133),
              (unsigned int)a2,
              a3);
            goto LABEL_16;
        }
        CTray::Command((HWND *)this + 7, v13, 0, 0, 0);
        goto LABEL_16;
      }
      switch ( a2 )
      {
        case 0x1FEuLL:
LABEL_59:
          if ( !CTray::_IsDesktopInputContext() )
            goto LABEL_16;
          v23 = a2;
          break;
        case 0x1FFuLL:
          if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 264LL))(*((_QWORD *)this + 133)) )
          {
            if ( CTray::_IsDesktopInputContext() )
            {
              CurrentThreadId = GetCurrentThreadId();
              Windows::Internal::ComTaskPool::QueueTask__lambda_30c7ccdecf09a0c6b63f0fbf2cd133d0___(
                v26,
                v25,
                CurrentThreadId);
            }
            goto LABEL_16;
          }
          if ( !CTray::_IsDesktopInputContext() )
          {
LABEL_16:
            *((_QWORD *)this + 78) = -1;
            wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v37, 0);
            TrayTelemetry::GlobalHotkeyPressedTriggered::~GlobalHotkeyPressedTriggered((TrayTelemetry::GlobalHotkeyPressedTriggered *)v37);
            return;
          }
          v23 = 511;
          break;
        case 0x200uLL:
          v20 = CTray::_HandleSysPropertiesHotkey(v8);
          v21 = retaddr;
          if ( v20 >= 0 )
            goto LABEL_16;
          v22 = 7266;
LABEL_51:
          wil::details::in1diag3::_Log_Hr(
            v21,
            (void *)v22,
            (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
            (const char *)(unsigned int)v20,
            v36);
          goto LABEL_16;
        case 0x201uLL:
          if ( !*((_BYTE *)this + 482) && CTray::_IsDesktopInputContext() )
          {
            DwmpActivateLivePreview(0, 0, 0, 2, 0);
            CTray::_RaiseDesktop(this, 3 - (unsigned int)(g_fDesktopRaised != 0), v18, v19);
          }
          goto LABEL_16;
        case 0x203uLL:
          if ( CTray::_IsDesktopInputContext() && _InterlockedCompareExchange(&g_fWinHomeListening, 0, 1) )
          {
            ForegroundWindow = GetForegroundWindow();
            CTray::_ShakeTriggered(this, 1, ForegroundWindow);
          }
          goto LABEL_16;
        case 0x204uLL:
          CTray::_PeekDesktop(this);
          goto LABEL_16;
        default:
          goto LABEL_15;
      }
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 133) + 424LL))(*((_QWORD *)this + 133), v23);
      goto LABEL_16;
    }
    switch ( a2 )
    {
      case 0x238uLL:
      case 0x239uLL:
      case 0x23EuLL:
        goto LABEL_16;
      case 0x23AuLL:
        goto LABEL_58;
      case 0x23DuLL:
        if ( CTray::_IsDesktopInputContext() )
        {
          v27 = GetCurrentThreadId();
          Windows::Internal::ComTaskPool::QueueTask__lambda_97fcdc8e8faaff62ceab652673eacb4c___(v29, v28, v27);
        }
        goto LABEL_16;
      case 0x23FuLL:
      case 0x240uLL:
      case 0x243uLL:
        CTray::_HandleExpressiveInputHotKey(this);
        goto LABEL_16;
      case 0x241uLL:
        if ( CTray::_IsDesktopInputContext() )
          CTray::_HandleDictationHotKey(this);
        goto LABEL_16;
      case 0x242uLL:
        CTray::_HandleClipboardViewerHotKey(this);
        goto LABEL_16;
      case 0x244uLL:
        CTray::_HandleOfficeHotKey(this);
        goto LABEL_16;
      case 0x245uLL:
        CTray::_HandleOfficeOneDriveHotKey(this);
        goto LABEL_16;
      case 0x246uLL:
        CTray::_HandleOfficeLinkedInHotKey(this);
        goto LABEL_16;
      case 0x247uLL:
        CTray::_HandleOfficeOneNoteHotKey(this);
        goto LABEL_16;
      case 0x248uLL:
        CTray::_HandleOfficeOutlookHotKey(this);
        goto LABEL_16;
      case 0x249uLL:
        CTray::_HandleOfficePowerPointHotKey(this);
        goto LABEL_16;
      case 0x24AuLL:
        CTray::_HandleOfficeTeamsHotKey(this);
        goto LABEL_16;
      case 0x24BuLL:
        CTray::_HandleOfficeWordHotKey(this);
        goto LABEL_16;
      case 0x24CuLL:
        CTray::_HandleOfficeExcelHotKey(this);
        goto LABEL_16;
      case 0x24DuLL:
        CTray::_HandleOfficeYammerHotKey(this);
        goto LABEL_16;
      case 0x24EuLL:
        goto LABEL_59;
      case 0x250uLL:
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_LCTest>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_LCTest>::GetImpl'::`2'::impl,
          v7);
        if ( TrayTelemetry::IsEnabled(v34, v33) )
        {
          TrayTelemetry::Instance();
          TrayTelemetry::LiveCaptionsHotkeyHandled_(v35);
        }
        SetRunningState();
        goto LABEL_16;
      case 0x251uLL:
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableHotkeyTracing>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_EnableHotkeyTracing>::GetImpl'::`2'::impl,
          v7);
        v36 = 0;
        v20 = RtlPublishWnfStateData(WNF_SHEL_TRACE_REQUESTED, 0, 0, 0) | 0x10000000;
        v21 = retaddr;
        if ( v20 >= 0 )
          goto LABEL_16;
        v22 = 7376;
        break;
      case 0x252uLL:
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CCW>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_CCW>::GetImpl'::`2'::impl,
          v7);
        goto LABEL_16;
      case 0x253uLL:
        if ( CTray::_IsDesktopInputContext() )
        {
          v30 = GetCurrentThreadId();
          Windows::Internal::ComTaskPool::QueueTask__lambda_89cc49141800fc9437804332418ce42a___(v32, v31, v30);
        }
        goto LABEL_16;
      default:
        goto LABEL_15;
    }
    goto LABEL_51;
  }
}

```

## disassembly

```asm
0x140123bbc  push    rbx
0x140123bbe  push    rsi
0x140123bbf  push    rdi
0x140123bc0  sub     rsp, 190h
0x140123bc7  mov     rax, cs:__security_cookie
0x140123bce  xor     rax, rsp
0x140123bd1  mov     [rsp+1A8h+var_28], rax
0x140123bd9  mov     rsi, r8
0x140123bdc  mov     rdi, rdx
0x140123bdf  mov     rbx, rcx
0x140123be2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x140123be9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x140123bee  test    al, al
0x140123bf0  jz      short loc_140123C0C
0x140123bf2  call    cs:__imp_IsGamingFullScreenExperienceActive
0x140123bf8  test    eax, eax
0x140123bfa  jz      short loc_140123C0C
0x140123bfc  mov     rdx, rdi; unsigned __int64
0x140123bff  call    ?_ShouldFilterHotkeyForGamingFullScreenExperience@CTray@@IEAA_N_K@Z; CTray::_ShouldFilterHotkeyForGamingFullScreenExperience(unsigned __int64)
0x140123c04  test    al, al
0x140123c06  jnz     loc_140123CED
0x140123c0c  cmp     rdi, [rbx+270h]
0x140123c13  jz      loc_140123CED
0x140123c19  lea     rdx, aGlobalhotkeypr; "GlobalHotkeyPressedTriggered"
0x140123c20  lea     rcx, [rsp+1A8h+var_178]; struct wil::details::IFailureCallback *
0x140123c25  call    ??0?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140123c2a  lea     rax, ??_7GlobalHotkeyPressedTriggered@TrayTelemetry@@6B@; const TrayTelemetry::GlobalHotkeyPressedTriggered::`vftable'
0x140123c31  mov     [rsp+1A8h+var_178], rax
0x140123c36  mov     edx, edi; int
0x140123c38  lea     rcx, [rsp+1A8h+var_178]; this
0x140123c3d  call    ?StartActivity@GlobalHotkeyPressedTriggered@TrayTelemetry@@QEAAXH@Z; TrayTelemetry::GlobalHotkeyPressedTriggered::StartActivity(int)
0x140123c42  nop
0x140123c43  mov     [rbx+270h], rdi
0x140123c4a  mov     eax, 237h
0x140123c4f  cmp     rdi, rax
0x140123c52  ja      loc_140123FA9
0x140123c58  jz      loc_140123FCD; jumptable 0000000140123FCB case 570
0x140123c5e  mov     eax, 1FDh
0x140123c63  cmp     rdi, rax
0x140123c66  ja      loc_140123E5A
0x140123c6c  jz      loc_140123E30
0x140123c72  mov     rax, rdi
0x140123c75  sub     rax, 1F6h
0x140123c7b  jz      loc_140123E16
0x140123c81  sub     rax, 1
0x140123c85  jz      loc_140123D9E
0x140123c8b  sub     rax, 1
0x140123c8f  jz      loc_140123D56
0x140123c95  sub     rax, 1
0x140123c99  jz      loc_140123D38
0x140123c9f  sub     rax, 1
0x140123ca3  jz      short loc_140123D08
0x140123ca5  cmp     rax, 1
0x140123ca9  jz      loc_140123FCD; jumptable 0000000140123FCB case 570
0x140123caf  mov     rcx, [rbx+428h]; jumptable 0000000140123FCB default case, cases 571,572,591
0x140123cb6  mov     rax, [rcx]
0x140123cb9  movzx   r8d, si
0x140123cbd  mov     edx, edi
0x140123cbf  mov     rax, [rax+1B0h]
0x140123cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140123ccb  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh; jumptable 0000000140123FCB cases 568,569,574
0x140123cd6  xor     edx, edx
0x140123cd8  lea     rcx, [rsp+1A8h+var_178]
0x140123cdd  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140123ce2  nop
0x140123ce3  lea     rcx, [rsp+1A8h+var_178]; this
0x140123ce8  call    ??1GlobalHotkeyPressedTriggered@TrayTelemetry@@QEAA@XZ; TrayTelemetry::GlobalHotkeyPressedTriggered::~GlobalHotkeyPressedTriggered(void)
0x140123ced  mov     rcx, [rsp+1A8h+var_28]
0x140123cf5  xor     rcx, rsp; StackCookie
0x140123cf8  call    __security_check_cookie
0x140123cfd  add     rsp, 190h
0x140123d04  pop     rdi
0x140123d05  pop     rsi
0x140123d06  pop     rbx
0x140123d07  retn
0x140123d08  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123d0d  nop
0x140123d0e  test    al, al
0x140123d10  jz      short loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d12  lea     r8, POLID_NoSetFolders; struct _GUID *
0x140123d19  mov     rdx, [rbx+8]; HWND
0x140123d1d  mov     rcx, cs:g_hinstCabinet; HINSTANCE
0x140123d24  call    ?_Restricted@@YAHPEAUHINSTANCE__@@PEAUHWND__@@AEBU_GUID@@@Z; _Restricted(HINSTANCE__ *,HWND__ *,_GUID const &)
0x140123d29  test    eax, eax
0x140123d2b  jnz     short loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d2d  mov     rcx, [rbx+8]; HWND
0x140123d31  call    ?_InvokeVerbOnParsingName@@YAXPEAUHWND__@@PEBG1@Z; _InvokeVerbOnParsingName(HWND__ *,ushort const *,ushort const *)
0x140123d36  jmp     short loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d38  mov     edx, 1F7h; unsigned int
0x140123d3d  xor     r9d, r9d; struct tagRECT *
0x140123d40  xor     r8d, r8d; __int64
0x140123d43  mov     byte ptr [rsp+1A8h+var_188], r8b; bool
0x140123d48  lea     rcx, [rbx+38h]; this
0x140123d4c  call    ?Command@CTray@@UEAAXI_JPEBUtagRECT@@_N@Z; CTray::Command(uint,__int64,tagRECT const *,bool)
0x140123d51  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d56  cmp     byte ptr [rbx+1E2h], 0
0x140123d5d  jnz     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d63  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123d68  test    al, al
0x140123d6a  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d70  mov     qword ptr [rsp+1A8h+var_188], 0
0x140123d79  mov     r9d, 2
0x140123d7f  xor     r8d, r8d
0x140123d82  xor     edx, edx
0x140123d84  xor     ecx, ecx
0x140123d86  call    cs:__imp_DwmpActivateLivePreview
0x140123d8c  xor     r8d, r8d; void *
0x140123d8f  xor     edx, edx; int
0x140123d91  mov     rcx, rbx; this
0x140123d94  call    ?_RestoreWindowPositions@CTray@@IEAAHHPEAX@Z; CTray::_RestoreWindowPositions(int,void *)
0x140123d99  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123d9e  cmp     byte ptr [rbx+1E2h], 0
0x140123da5  jnz     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123dab  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123db0  test    al, al
0x140123db2  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123db8  mov     qword ptr [rsp+1A8h+var_188], 0
0x140123dc1  mov     r9d, 2
0x140123dc7  xor     r8d, r8d
0x140123dca  xor     edx, edx
0x140123dcc  xor     ecx, ecx
0x140123dce  call    cs:__imp_DwmpActivateLivePreview
0x140123dd4  xor     r8d, r8d; void *
0x140123dd7  xor     edx, edx; int
0x140123dd9  mov     rcx, rbx; this
0x140123ddc  call    ?_MinimizeAll@CTray@@IEAAHHPEAX@Z; CTray::_MinimizeAll(int,void *)
0x140123de1  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hWnd
0x140123de8  call    cs:__imp_SetForegroundWindow
0x140123dee  cmp     byte ptr [rbx+1E1h], 0
0x140123df5  jnz     short loc_140123E04
0x140123df7  cmp     byte ptr [rbx+1E0h], 0
0x140123dfe  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e04  mov     edx, 1; unsigned __int64
0x140123e09  mov     rcx, rbx; this
0x140123e0c  call    ?_HandleImmersiveHotKey@CTray@@QEAAJ_K_J@Z; CTray::_HandleImmersiveHotKey(unsigned __int64,__int64)
0x140123e11  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e16  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123e1b  test    al, al
0x140123e1d  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e23  mov     rcx, rbx; this
0x140123e26  call    ?_RunDlg@CTray@@IEAAXXZ; CTray::_RunDlg(void)
0x140123e2b  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e30  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123e35  test    al, al
0x140123e37  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e3d  mov     ecx, 80h; rest
0x140123e42  call    cs:__imp_SHRestricted
0x140123e48  test    eax, eax
0x140123e4a  jnz     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123e50  mov     edx, 0A086h
0x140123e55  jmp     loc_140123D3D
0x140123e5a  mov     rax, rdi
0x140123e5d  sub     rax, 1FEh
0x140123e63  jz      loc_140123FDF; jumptable 0000000140123FCB case 590
0x140123e69  sub     rax, 1
0x140123e6d  jz      loc_140123F5B
0x140123e73  sub     rax, 1
0x140123e77  jz      loc_140123F2D
0x140123e7d  sub     rax, 1
0x140123e81  jz      short loc_140123EDD
0x140123e83  sub     rax, 2
0x140123e87  jz      short loc_140123EA0
0x140123e89  cmp     rax, 1
0x140123e8d  jnz     def_140123FCB; jumptable 0000000140123FCB default case, cases 571,572,591
0x140123e93  mov     rcx, rbx; this
0x140123e96  call    ?_PeekDesktop@CTray@@IEAAXXZ; CTray::_PeekDesktop(void)
0x140123e9b  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123ea0  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123ea5  test    al, al
0x140123ea7  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123ead  xor     ecx, ecx
0x140123eaf  lea     eax, [rcx+1]
0x140123eb2  lock cmpxchg cs:?g_fWinHomeListening@@3JA, ecx; long g_fWinHomeListening
0x140123eba  test    eax, eax
0x140123ebc  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123ec2  call    cs:__imp_GetForegroundWindow
0x140123ec8  mov     r8, rax
0x140123ecb  mov     edx, 1
0x140123ed0  mov     rcx, rbx
0x140123ed3  call    ?_ShakeTriggered@CTray@@IEAA_JW4_SHOWDESKTOPTRIGGER@@PEAUHWND__@@@Z; CTray::_ShakeTriggered(_SHOWDESKTOPTRIGGER,HWND__ *)
0x140123ed8  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123edd  cmp     byte ptr [rbx+1E2h], 0
0x140123ee4  jnz     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123eea  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123eef  test    al, al
0x140123ef1  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123ef7  mov     qword ptr [rsp+1A8h+var_188], 0
0x140123f00  mov     r9d, 2
0x140123f06  xor     r8d, r8d
0x140123f09  xor     edx, edx
0x140123f0b  xor     ecx, ecx
0x140123f0d  call    cs:__imp_DwmpActivateLivePreview
0x140123f13  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x140123f19  neg     eax
0x140123f1b  sbb     edx, edx
0x140123f1d  add     edx, 3
0x140123f20  mov     rcx, rbx
0x140123f23  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x140123f28  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123f2d  call    ?_HandleSysPropertiesHotkey@CTray@@IEAAJXZ; CTray::_HandleSysPropertiesHotkey(void)
0x140123f32  mov     rcx, [rsp+1A8h]; this
0x140123f3a  test    eax, eax
0x140123f3c  jns     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123f42  mov     edx, 1C62h; void *
0x140123f47  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x140123f4e  mov     r9d, eax; char *
0x140123f51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140123f56  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123f5b  mov     rcx, [rbx+428h]
0x140123f62  mov     rax, [rcx]
0x140123f65  mov     rax, [rax+108h]
0x140123f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140123f71  test    eax, eax
0x140123f73  jz      short loc_140123F89
0x140123f75  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123f7a  test    al, al
0x140123f7c  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123f82  mov     edx, 1FFh
0x140123f87  jmp     short loc_140123FEF
0x140123f89  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x140123f8e  test    al, al
0x140123f90  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123f96  call    cs:__imp_GetCurrentThreadId
0x140123f9c  mov     r8d, eax
0x140123f9f  call    Windows__Internal__ComTaskPool__QueueTask__lambda_30c7ccdecf09a0c6b63f0fbf2cd133d0___
0x140123fa4  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123fa9  lea     rax, [rdi-238h]; switch 28 cases
0x140123fb0  cmp     rax, 1Bh
0x140123fb4  ja      def_140123FCB; jumptable 0000000140123FCB default case, cases 571,572,591
0x140123fba  lea     rcx, __ImageBase
0x140123fc1  mov     eax, ds:(jpt_140123FCB - 140000000h)[rcx+rax*4]
0x140123fc8  add     rax, rcx
0x140123fcb  jmp     rax; switch jump
0x140123fcd  mov     edx, 1Eh; jumptable 0000000140123FCB case 570
0x140123fd2  mov     rcx, rbx
0x140123fd5  call    ?_HandleSearchPaneHotkey@CTray@@IEAAXW4IMMERSIVE_HOT_KEY_ID@@@Z; CTray::_HandleSearchPaneHotkey(IMMERSIVE_HOT_KEY_ID)
0x140123fda  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123fdf  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 0000000140123FCB case 590
0x140123fe4  test    al, al
0x140123fe6  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140123fec  mov     rdx, rdi
0x140123fef  mov     rcx, [rbx+428h]
0x140123ff6  mov     rax, [rcx]
0x140123ff9  mov     rax, [rax+1A8h]
0x140124000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140124005  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x14012400a  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 0000000140123FCB case 573
0x14012400f  test    al, al
0x140124011  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124017  call    cs:__imp_GetCurrentThreadId
0x14012401d  mov     r8d, eax
0x140124020  call    Windows__Internal__ComTaskPool__QueueTask__lambda_97fcdc8e8faaff62ceab652673eacb4c___
0x140124025  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x14012402a  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 0000000140123FCB case 595
0x14012402f  test    al, al
0x140124031  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124037  call    cs:__imp_GetCurrentThreadId
0x14012403d  mov     r8d, eax
0x140124040  call    Windows__Internal__ComTaskPool__QueueTask__lambda_89cc49141800fc9437804332418ce42a___
0x140124045  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x14012404a  mov     rcx, rbx; jumptable 0000000140123FCB cases 575,576,579
0x14012404d  call    ?_HandleExpressiveInputHotKey@CTray@@IEAAXXZ; CTray::_HandleExpressiveInputHotKey(void)
0x140124052  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124057  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 0000000140123FCB case 577
0x14012405c  test    al, al
0x14012405e  jz      loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124064  mov     rcx, rbx; this
0x140124067  call    ?_HandleDictationHotKey@CTray@@IEAAXXZ; CTray::_HandleDictationHotKey(void)
0x14012406c  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124071  mov     rcx, rbx; jumptable 0000000140123FCB case 578
0x140124074  call    ?_HandleClipboardViewerHotKey@CTray@@IEAAXXZ; CTray::_HandleClipboardViewerHotKey(void)
0x140124079  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x14012407e  mov     rcx, rbx; jumptable 0000000140123FCB case 580
0x140124081  call    ?_HandleOfficeHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeHotKey(void)
0x140124086  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x14012408b  mov     rcx, rbx; jumptable 0000000140123FCB case 582
0x14012408e  call    ?_HandleOfficeLinkedInHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeLinkedInHotKey(void)
0x140124093  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x140124098  mov     rcx, rbx; jumptable 0000000140123FCB case 581
0x14012409b  call    ?_HandleOfficeOneDriveHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOneDriveHotKey(void)
0x1401240a0  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240a5  mov     rcx, rbx; jumptable 0000000140123FCB case 583
0x1401240a8  call    ?_HandleOfficeOneNoteHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOneNoteHotKey(void)
0x1401240ad  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240b2  mov     rcx, rbx; jumptable 0000000140123FCB case 584
0x1401240b5  call    ?_HandleOfficeOutlookHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOutlookHotKey(void)
0x1401240ba  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240bf  mov     rcx, rbx; jumptable 0000000140123FCB case 585
0x1401240c2  call    ?_HandleOfficePowerPointHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficePowerPointHotKey(void)
0x1401240c7  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240cc  mov     rcx, rbx; jumptable 0000000140123FCB case 586
0x1401240cf  call    ?_HandleOfficeTeamsHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeTeamsHotKey(void)
0x1401240d4  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240d9  mov     rcx, rbx; jumptable 0000000140123FCB case 587
0x1401240dc  call    ?_HandleOfficeWordHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeWordHotKey(void)
0x1401240e1  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240e6  mov     rcx, rbx; jumptable 0000000140123FCB case 588
0x1401240e9  call    ?_HandleOfficeExcelHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeExcelHotKey(void)
0x1401240ee  jmp     loc_140123CCB; jumptable 0000000140123FCB cases 568,569,574
0x1401240f3  mov     rcx, rbx; jumptable 0000000140123FCB case 589
  ... truncated ...
```
