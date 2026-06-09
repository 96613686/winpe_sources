# CTray::_HandleGlobalHotkey(unsigned __int64,__int64)

- ea: `0x14012f214`
- end: `0x14012f898`
- name: `?_HandleGlobalHotkey@CTray@@IEAAX_K_J@Z`
- size: `1668`
- prototype: `void __fastcall(CTray *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `46`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140019eb0`
- `0x1400abc30`

## callees

- `0x140012f50`
- `0x14001b2c8`
- `0x14003229c`
- `0x140078e4c`
- `0x140078f2c`
- `0x14008dd24`
- `0x140090b64`
- `0x1400918ac`
- `0x1400938ac`
- `0x140093b68`
- `0x140098e54`
- `0x1400abc30`
- `0x1400b1514`
- `0x1400bb4e0`
- `0x1400fb758`
- `0x140107d04`
- `0x14010e160`
- `0x140116088`
- `0x14011de0c`
- `0x14011df74`
- `0x14011e028`
- `0x140128554`
- `0x14012ab24`
- `0x14012ad5c`
- `0x14012efd0`
- `0x14012f124`
- `0x14012f214`
- `0x14012f8a0`
- `0x14012f920`
- `0x14012fa04`
- `0x14012fbd0`
- `0x14012fc50`
- `0x14012fddc`
- `0x14012fec4`
- `0x14012ffac`
- `0x140130090`
- `0x140130140`
- `0x140130224`
- `0x140130348`
- `0x140130400`
- `0x14013103c`
- `0x140131140`
- `0x14013148c`
- `0x140131810`
- `0x1401b78ac`
- `0x1401d9010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x14012f7ea`
- `ntdll!RtlPublishWnfStateData` at `0x14012f7ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f6a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f6ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f6a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14012f6ca`
- `SHELL32!__imp_SHRestricted` at `0x14012f4b3`
- `SHELL32!__imp_SHRestricted` at `0x14012f4b3`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f3e5`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f433`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f58a`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f3e5`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f433`
- `dwmapi!__imp_DwmpActivateLivePreview` at `0x14012f58a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14012f539`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14012f539`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14012f453`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14012f453`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceActive` at `0x14012f24a`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceActive` at `0x14012f24a`

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
0x14012f214  push    rbx
0x14012f216  push    rsi
0x14012f217  push    rdi
0x14012f218  sub     rsp, 190h
0x14012f21f  mov     rax, cs:__security_cookie
0x14012f226  xor     rax, rsp
0x14012f229  mov     [rsp+1A8h+var_28], rax
0x14012f231  mov     rsi, r8
0x14012f234  mov     rdi, rdx
0x14012f237  mov     rbx, rcx
0x14012f23a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x14012f241  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x14012f246  test    al, al
0x14012f248  jz      short loc_14012F26A
0x14012f24a  call    cs:__imp_IsGamingFullScreenExperienceActive
0x14012f251  nop     dword ptr [rax+rax+00h]
0x14012f256  test    eax, eax
0x14012f258  jz      short loc_14012F26A
0x14012f25a  mov     rdx, rdi; unsigned __int64
0x14012f25d  call    ?_ShouldFilterHotkeyForGamingFullScreenExperience@CTray@@IEAA_N_K@Z; CTray::_ShouldFilterHotkeyForGamingFullScreenExperience(unsigned __int64)
0x14012f262  test    al, al
0x14012f264  jnz     loc_14012F34B
0x14012f26a  cmp     rdi, [rbx+270h]
0x14012f271  jz      loc_14012F34B
0x14012f277  lea     rdx, aGlobalhotkeypr; "GlobalHotkeyPressedTriggered"
0x14012f27e  lea     rcx, [rsp+1A8h+var_178]; struct wil::details::IFailureCallback *
0x14012f283  call    ??0?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14012f288  lea     rax, ??_7GlobalHotkeyPressedTriggered@TrayTelemetry@@6B@; const TrayTelemetry::GlobalHotkeyPressedTriggered::`vftable'
0x14012f28f  mov     [rsp+1A8h+var_178], rax
0x14012f294  mov     edx, edi; int
0x14012f296  lea     rcx, [rsp+1A8h+var_178]; this
0x14012f29b  call    ?StartActivity@GlobalHotkeyPressedTriggered@TrayTelemetry@@QEAAXH@Z; TrayTelemetry::GlobalHotkeyPressedTriggered::StartActivity(int)
0x14012f2a0  nop
0x14012f2a1  mov     [rbx+270h], rdi
0x14012f2a8  mov     eax, 237h
0x14012f2ad  cmp     rdi, rax
0x14012f2b0  ja      loc_14012F632
0x14012f2b6  jz      loc_14012F65A; jumptable 000000014012F654 case 570
0x14012f2bc  mov     eax, 1FDh
0x14012f2c1  cmp     rdi, rax
0x14012f2c4  ja      loc_14012F4D1
0x14012f2ca  jz      loc_14012F4A1
0x14012f2d0  mov     rax, rdi
0x14012f2d3  sub     rax, 1F6h
0x14012f2d9  jz      loc_14012F487
0x14012f2df  sub     rax, 1
0x14012f2e3  jz      loc_14012F403
0x14012f2e9  sub     rax, 1
0x14012f2ed  jz      loc_14012F3B5
0x14012f2f3  sub     rax, 1
0x14012f2f7  jz      loc_14012F397
0x14012f2fd  sub     rax, 1
0x14012f301  jz      short loc_14012F367
0x14012f303  cmp     rax, 1
0x14012f307  jz      loc_14012F65A; jumptable 000000014012F654 case 570
0x14012f30d  mov     rcx, [rbx+428h]; jumptable 000000014012F654 default case, cases 571,572,591
0x14012f314  mov     rax, [rcx]
0x14012f317  movzx   r8d, si
0x14012f31b  mov     edx, edi
0x14012f31d  mov     rax, [rax+1B0h]
0x14012f324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012f329  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh; jumptable 000000014012F654 cases 568,569,574
0x14012f334  xor     edx, edx
0x14012f336  lea     rcx, [rsp+1A8h+var_178]
0x14012f33b  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14012f340  nop
0x14012f341  lea     rcx, [rsp+1A8h+var_178]; this
0x14012f346  call    ??1GlobalHotkeyPressedTriggered@TrayTelemetry@@QEAA@XZ; TrayTelemetry::GlobalHotkeyPressedTriggered::~GlobalHotkeyPressedTriggered(void)
0x14012f34b  mov     rcx, [rsp+1A8h+var_28]
0x14012f353  xor     rcx, rsp; StackCookie
0x14012f356  call    __security_check_cookie
0x14012f35b  add     rsp, 190h
0x14012f362  pop     rdi
0x14012f363  pop     rsi
0x14012f364  pop     rbx
0x14012f365  retn
0x14012f367  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f36c  nop
0x14012f36d  test    al, al
0x14012f36f  jz      short loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f371  lea     r8, POLID_NoSetFolders; struct _GUID *
0x14012f378  mov     rdx, [rbx+8]; HWND
0x14012f37c  mov     rcx, cs:g_hinstCabinet; HINSTANCE
0x14012f383  call    ?_Restricted@@YAHPEAUHINSTANCE__@@PEAUHWND__@@AEBU_GUID@@@Z; _Restricted(HINSTANCE__ *,HWND__ *,_GUID const &)
0x14012f388  test    eax, eax
0x14012f38a  jnz     short loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f38c  mov     rcx, [rbx+8]; HWND
0x14012f390  call    ?_InvokeVerbOnParsingName@@YAXPEAUHWND__@@PEBG1@Z; _InvokeVerbOnParsingName(HWND__ *,ushort const *,ushort const *)
0x14012f395  jmp     short loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f397  mov     edx, 1F7h; unsigned int
0x14012f39c  xor     r9d, r9d; struct tagRECT *
0x14012f39f  xor     r8d, r8d; __int64
0x14012f3a2  mov     byte ptr [rsp+1A8h+var_188], r8b; bool
0x14012f3a7  lea     rcx, [rbx+38h]; this
0x14012f3ab  call    ?Command@CTray@@UEAAXI_JPEBUtagRECT@@_N@Z; CTray::Command(uint,__int64,tagRECT const *,bool)
0x14012f3b0  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f3b5  cmp     byte ptr [rbx+1E2h], 0
0x14012f3bc  jnz     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f3c2  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f3c7  test    al, al
0x14012f3c9  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f3cf  mov     qword ptr [rsp+1A8h+var_188], 0
0x14012f3d8  mov     r9d, 2
0x14012f3de  xor     r8d, r8d
0x14012f3e1  xor     edx, edx
0x14012f3e3  xor     ecx, ecx
0x14012f3e5  call    cs:__imp_DwmpActivateLivePreview
0x14012f3ec  nop     dword ptr [rax+rax+00h]
0x14012f3f1  xor     r8d, r8d; void *
0x14012f3f4  xor     edx, edx; int
0x14012f3f6  mov     rcx, rbx; this
0x14012f3f9  call    ?_RestoreWindowPositions@CTray@@IEAAHHPEAX@Z; CTray::_RestoreWindowPositions(int,void *)
0x14012f3fe  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f403  cmp     byte ptr [rbx+1E2h], 0
0x14012f40a  jnz     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f410  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f415  test    al, al
0x14012f417  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f41d  mov     qword ptr [rsp+1A8h+var_188], 0
0x14012f426  mov     r9d, 2
0x14012f42c  xor     r8d, r8d
0x14012f42f  xor     edx, edx
0x14012f431  xor     ecx, ecx
0x14012f433  call    cs:__imp_DwmpActivateLivePreview
0x14012f43a  nop     dword ptr [rax+rax+00h]
0x14012f43f  xor     r8d, r8d; void *
0x14012f442  xor     edx, edx; int
0x14012f444  mov     rcx, rbx; this
0x14012f447  call    ?_MinimizeAll@CTray@@IEAAHHPEAX@Z; CTray::_MinimizeAll(int,void *)
0x14012f44c  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hWnd
0x14012f453  call    cs:__imp_SetForegroundWindow
0x14012f45a  nop     dword ptr [rax+rax+00h]
0x14012f45f  cmp     byte ptr [rbx+1E1h], 0
0x14012f466  jnz     short loc_14012F475
0x14012f468  cmp     byte ptr [rbx+1E0h], 0
0x14012f46f  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f475  mov     edx, 1; unsigned __int64
0x14012f47a  mov     rcx, rbx; this
0x14012f47d  call    ?_HandleImmersiveHotKey@CTray@@QEAAJ_K_J@Z; CTray::_HandleImmersiveHotKey(unsigned __int64,__int64)
0x14012f482  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f487  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f48c  test    al, al
0x14012f48e  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f494  mov     rcx, rbx; this
0x14012f497  call    ?_RunDlg@CTray@@IEAAXXZ; CTray::_RunDlg(void)
0x14012f49c  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f4a1  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f4a6  test    al, al
0x14012f4a8  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f4ae  mov     ecx, 80h; rest
0x14012f4b3  call    cs:__imp_SHRestricted
0x14012f4ba  nop     dword ptr [rax+rax+00h]
0x14012f4bf  test    eax, eax
0x14012f4c1  jnz     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f4c7  mov     edx, 0A086h
0x14012f4cc  jmp     loc_14012F39C
0x14012f4d1  mov     rax, rdi
0x14012f4d4  sub     rax, 1FEh
0x14012f4da  jz      loc_14012F66C; jumptable 000000014012F654 case 590
0x14012f4e0  sub     rax, 1
0x14012f4e4  jz      loc_14012F5DE
0x14012f4ea  sub     rax, 1
0x14012f4ee  jz      loc_14012F5B0
0x14012f4f4  sub     rax, 1
0x14012f4f8  jz      short loc_14012F55A
0x14012f4fa  sub     rax, 2
0x14012f4fe  jz      short loc_14012F517
0x14012f500  cmp     rax, 1
0x14012f504  jnz     def_14012F654; jumptable 000000014012F654 default case, cases 571,572,591
0x14012f50a  mov     rcx, rbx; this
0x14012f50d  call    ?_PeekDesktop@CTray@@IEAAXXZ; CTray::_PeekDesktop(void)
0x14012f512  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f517  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f51c  test    al, al
0x14012f51e  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f524  xor     ecx, ecx
0x14012f526  lea     eax, [rcx+1]
0x14012f529  lock cmpxchg cs:?g_fWinHomeListening@@3JA, ecx; long g_fWinHomeListening
0x14012f531  test    eax, eax
0x14012f533  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f539  call    cs:__imp_GetForegroundWindow
0x14012f540  nop     dword ptr [rax+rax+00h]
0x14012f545  mov     r8, rax
0x14012f548  mov     edx, 1
0x14012f54d  mov     rcx, rbx
0x14012f550  call    ?_ShakeTriggered@CTray@@IEAA_JW4_SHOWDESKTOPTRIGGER@@PEAUHWND__@@@Z; CTray::_ShakeTriggered(_SHOWDESKTOPTRIGGER,HWND__ *)
0x14012f555  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f55a  cmp     byte ptr [rbx+1E2h], 0
0x14012f561  jnz     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f567  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f56c  test    al, al
0x14012f56e  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f574  mov     qword ptr [rsp+1A8h+var_188], 0
0x14012f57d  mov     r9d, 2
0x14012f583  xor     r8d, r8d
0x14012f586  xor     edx, edx
0x14012f588  xor     ecx, ecx
0x14012f58a  call    cs:__imp_DwmpActivateLivePreview
0x14012f591  nop     dword ptr [rax+rax+00h]
0x14012f596  mov     eax, cs:?g_fDesktopRaised@@3HA; int g_fDesktopRaised
0x14012f59c  neg     eax
0x14012f59e  sbb     edx, edx
0x14012f5a0  add     edx, 3
0x14012f5a3  mov     rcx, rbx
0x14012f5a6  call    ?_RaiseDesktop@CTray@@IEAAXW4RAISEDESKTOPFLAGS@@@Z; CTray::_RaiseDesktop(RAISEDESKTOPFLAGS)
0x14012f5ab  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f5b0  call    ?_HandleSysPropertiesHotkey@CTray@@IEAAJXZ; CTray::_HandleSysPropertiesHotkey(void)
0x14012f5b5  mov     rcx, [rsp+1A8h]; this
0x14012f5bd  test    eax, eax
0x14012f5bf  jns     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f5c5  mov     edx, 1C62h; void *
0x14012f5ca  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14012f5d1  mov     r9d, eax; char *
0x14012f5d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14012f5d9  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f5de  mov     rcx, [rbx+428h]
0x14012f5e5  mov     rax, [rcx]
0x14012f5e8  mov     rax, [rax+108h]
0x14012f5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012f5f4  test    eax, eax
0x14012f5f6  jz      short loc_14012F60C
0x14012f5f8  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f5fd  test    al, al
0x14012f5ff  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f605  mov     edx, 1FFh
0x14012f60a  jmp     short loc_14012F67C
0x14012f60c  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; CTray::_IsDesktopInputContext(void)
0x14012f611  test    al, al
0x14012f613  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f619  call    cs:__imp_GetCurrentThreadId
0x14012f620  nop     dword ptr [rax+rax+00h]
0x14012f625  mov     r8d, eax
0x14012f628  call    Windows__Internal__ComTaskPool__QueueTask__lambda_30c7ccdecf09a0c6b63f0fbf2cd133d0___
0x14012f62d  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f632  lea     rax, [rdi-238h]; switch 28 cases
0x14012f639  cmp     rax, 1Bh
0x14012f63d  ja      def_14012F654; jumptable 000000014012F654 default case, cases 571,572,591
0x14012f643  lea     rcx, __ImageBase
0x14012f64a  mov     eax, ds:(jpt_14012F654 - 140000000h)[rcx+rax*4]
0x14012f651  add     rax, rcx
0x14012f654  jmp     rax; switch jump
0x14012f65a  mov     edx, 1Eh; jumptable 000000014012F654 case 570
0x14012f65f  mov     rcx, rbx
0x14012f662  call    ?_HandleSearchPaneHotkey@CTray@@IEAAXW4IMMERSIVE_HOT_KEY_ID@@@Z; CTray::_HandleSearchPaneHotkey(IMMERSIVE_HOT_KEY_ID)
0x14012f667  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f66c  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 000000014012F654 case 590
0x14012f671  test    al, al
0x14012f673  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f679  mov     rdx, rdi
0x14012f67c  mov     rcx, [rbx+428h]
0x14012f683  mov     rax, [rcx]
0x14012f686  mov     rax, [rax+1A8h]
0x14012f68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012f692  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f697  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 000000014012F654 case 573
0x14012f69c  test    al, al
0x14012f69e  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6a4  call    cs:__imp_GetCurrentThreadId
0x14012f6ab  nop     dword ptr [rax+rax+00h]
0x14012f6b0  mov     r8d, eax
0x14012f6b3  call    Windows__Internal__ComTaskPool__QueueTask__lambda_97fcdc8e8faaff62ceab652673eacb4c___
0x14012f6b8  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6bd  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 000000014012F654 case 595
0x14012f6c2  test    al, al
0x14012f6c4  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6ca  call    cs:__imp_GetCurrentThreadId
0x14012f6d1  nop     dword ptr [rax+rax+00h]
0x14012f6d6  mov     r8d, eax
0x14012f6d9  call    Windows__Internal__ComTaskPool__QueueTask__lambda_89cc49141800fc9437804332418ce42a___
0x14012f6de  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6e3  mov     rcx, rbx; jumptable 000000014012F654 cases 575,576,579
0x14012f6e6  call    ?_HandleExpressiveInputHotKey@CTray@@IEAAXXZ; CTray::_HandleExpressiveInputHotKey(void)
0x14012f6eb  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6f0  call    ?_IsDesktopInputContext@CTray@@KA_NXZ; jumptable 000000014012F654 case 577
0x14012f6f5  test    al, al
0x14012f6f7  jz      loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f6fd  mov     rcx, rbx; this
0x14012f700  call    ?_HandleDictationHotKey@CTray@@IEAAXXZ; CTray::_HandleDictationHotKey(void)
0x14012f705  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f70a  mov     rcx, rbx; jumptable 000000014012F654 case 578
0x14012f70d  call    ?_HandleClipboardViewerHotKey@CTray@@IEAAXXZ; CTray::_HandleClipboardViewerHotKey(void)
0x14012f712  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f717  mov     rcx, rbx; jumptable 000000014012F654 case 580
0x14012f71a  call    ?_HandleOfficeHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeHotKey(void)
0x14012f71f  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f724  mov     rcx, rbx; jumptable 000000014012F654 case 582
0x14012f727  call    ?_HandleOfficeLinkedInHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeLinkedInHotKey(void)
0x14012f72c  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f731  mov     rcx, rbx; jumptable 000000014012F654 case 581
0x14012f734  call    ?_HandleOfficeOneDriveHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOneDriveHotKey(void)
0x14012f739  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f73e  mov     rcx, rbx; jumptable 000000014012F654 case 583
0x14012f741  call    ?_HandleOfficeOneNoteHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOneNoteHotKey(void)
0x14012f746  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f74b  mov     rcx, rbx; jumptable 000000014012F654 case 584
0x14012f74e  call    ?_HandleOfficeOutlookHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficeOutlookHotKey(void)
0x14012f753  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
0x14012f758  mov     rcx, rbx; jumptable 000000014012F654 case 585
0x14012f75b  call    ?_HandleOfficePowerPointHotKey@CTray@@IEAAXXZ; CTray::_HandleOfficePowerPointHotKey(void)
0x14012f760  jmp     loc_14012F329; jumptable 000000014012F654 cases 568,569,574
  ... truncated ...
```
