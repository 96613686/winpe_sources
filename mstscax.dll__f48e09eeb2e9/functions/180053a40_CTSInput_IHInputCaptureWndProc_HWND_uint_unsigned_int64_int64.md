# CTSInput::IHInputCaptureWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180053a40`
- end: `0x180054fc8`
- name: `?IHInputCaptureWndProc@CTSInput@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `5512`
- prototype: `__int64 __fastcall(CTSInput *__hidden this, HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800539c0`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180053a40`
- `0x18007c7dc`
- `0x18008d38c`
- `0x180098c30`
- `0x18009f2f8`
- `0x1800a7470`
- `0x1800e9b1c`
- `0x1800eebc4`
- `0x1800f7748`
- `0x180130604`
- `0x18014be28`
- `0x18014cd78`
- `0x18014ce80`
- `0x18014cfa0`
- `0x18014e42c`
- `0x18014e568`
- `0x180152be0`
- `0x180153324`
- `0x1801533e0`
- `0x180153894`
- `0x1801539e4`
- `0x180153b68`
- `0x180154358`
- `0x18019db40`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180054a6b`
- `KERNEL32!TlsSetValue` at `0x180054a6b`
- `KERNEL32!GetModuleHandleExW` at `0x180054acb`
- `KERNEL32!GetModuleHandleExW` at `0x180054acb`
- `KERNEL32!GetLastError` at `0x180054976`
- `KERNEL32!GetLastError` at `0x180054ad5`
- `KERNEL32!GetLastError` at `0x180054b6c`
- `KERNEL32!GetLastError` at `0x180054976`
- `KERNEL32!GetLastError` at `0x180054ad5`
- `KERNEL32!GetLastError` at `0x180054b6c`
- `KERNEL32!LoadLibraryExW` at `0x180054cd7`
- `KERNEL32!LoadLibraryExW` at `0x180054d14`
- `KERNEL32!LoadLibraryExW` at `0x180054d73`
- `KERNEL32!LoadLibraryExW` at `0x180054cd7`
- `KERNEL32!LoadLibraryExW` at `0x180054d14`
- `KERNEL32!LoadLibraryExW` at `0x180054d73`
- `KERNEL32!GetProcAddress` at `0x180054cf1`
- `KERNEL32!GetProcAddress` at `0x180054d2c`
- `KERNEL32!GetProcAddress` at `0x180054d8d`
- `KERNEL32!GetProcAddress` at `0x180054cf1`
- `KERNEL32!GetProcAddress` at `0x180054d2c`
- `KERNEL32!GetProcAddress` at `0x180054d8d`
- `KERNEL32!FreeLibrary` at `0x180054cfd`
- `KERNEL32!FreeLibrary` at `0x180054d44`
- `KERNEL32!FreeLibrary` at `0x180054da8`
- `KERNEL32!FreeLibrary` at `0x180054cfd`
- `KERNEL32!FreeLibrary` at `0x180054d44`
- `KERNEL32!FreeLibrary` at `0x180054da8`
- `KERNEL32!GetCurrentThreadId` at `0x1800549ed`
- `KERNEL32!GetCurrentThreadId` at `0x1800549ed`
- `USER32!GetKeyState` at `0x1800542d7`
- `USER32!GetKeyState` at `0x1800543ee`
- `USER32!GetKeyState` at `0x18005450e`
- `USER32!GetKeyState` at `0x18005459e`
- `USER32!GetKeyState` at `0x1800542d7`
- `USER32!GetKeyState` at `0x1800543ee`
- `USER32!GetKeyState` at `0x18005450e`
- `USER32!GetKeyState` at `0x18005459e`
- `USER32!MapVirtualKeyW` at `0x180053e28`
- `USER32!MapVirtualKeyW` at `0x180053e49`
- `USER32!MapVirtualKeyW` at `0x180053e6a`
- `USER32!MapVirtualKeyW` at `0x180053ee3`
- `USER32!MapVirtualKeyW` at `0x180053f04`
- `USER32!MapVirtualKeyW` at `0x180053f25`
- `USER32!MapVirtualKeyW` at `0x180054383`
- `USER32!MapVirtualKeyW` at `0x1800543a6`
- `USER32!MapVirtualKeyW` at `0x18005449f`
- `USER32!MapVirtualKeyW` at `0x1800544c1`
- `USER32!MapVirtualKeyW` at `0x18005455f`
- `USER32!MapVirtualKeyW` at `0x1800545ec`
- `USER32!MapVirtualKeyW` at `0x180053e28`
- `USER32!MapVirtualKeyW` at `0x180053e49`
- `USER32!MapVirtualKeyW` at `0x180053e6a`
- `USER32!MapVirtualKeyW` at `0x180053ee3`
- `USER32!MapVirtualKeyW` at `0x180053f04`
- `USER32!MapVirtualKeyW` at `0x180053f25`
- `USER32!MapVirtualKeyW` at `0x180054383`
- `USER32!MapVirtualKeyW` at `0x1800543a6`
- `USER32!MapVirtualKeyW` at `0x18005449f`
- `USER32!MapVirtualKeyW` at `0x1800544c1`
- `USER32!MapVirtualKeyW` at `0x18005455f`
- `USER32!MapVirtualKeyW` at `0x1800545ec`
- `USER32!EndPaint` at `0x1800541db`
- `USER32!EndPaint` at `0x1800541db`
- `USER32!BeginPaint` at `0x1800541ce`
- `USER32!BeginPaint` at `0x1800541ce`
- `USER32!DefWindowProcW` at `0x18005415e`
- `USER32!DefWindowProcW` at `0x18005415e`
- `USER32!GetAsyncKeyState` at `0x180053c74`
- `USER32!GetAsyncKeyState` at `0x180053c8a`
- `USER32!GetAsyncKeyState` at `0x180053c74`
- `USER32!GetAsyncKeyState` at `0x180053c8a`
- `USER32!AttachThreadInput` at `0x1800549ff`
- `USER32!AttachThreadInput` at `0x1800549ff`
- `USER32!GetWindowThreadProcessId` at `0x1800549e5`
- `USER32!GetWindowThreadProcessId` at `0x1800549e5`
- `USER32!SetWindowsHookExW` at `0x180054b3f`
- `USER32!SetWindowsHookExW` at `0x180054b3f`
- `USER32!SetCursor` at `0x1800540fe`
- `USER32!SetCursor` at `0x1800540fe`
- `USER32!UnhookWindowsHookEx` at `0x180054953`
- `USER32!UnhookWindowsHookEx` at `0x180054953`
- `WTSAPI32!WTSUnRegisterSessionNotification` at `0x180054965`
- `WTSAPI32!WTSUnRegisterSessionNotification` at `0x180054965`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x180054b5a`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x180054b5a`

## string_xrefs

- `0x180054cc8`: `user32.dll`

## pseudocode

```c
LRESULT __fastcall CTSInput::IHInputCaptureWndProc(CTSInput *this, HWND a2, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LPARAM v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ebx
  unsigned int v14; // eax
  int v15; // edx
  _BOOL8 v16; // rdi
  __int64 v18; // rcx
  int v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // rbx
  unsigned int v22; // eax
  unsigned __int16 v23; // ax
  unsigned __int16 v24; // ax
  __int16 v25; // ax
  unsigned int v26; // eax
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // ax
  __int16 v29; // ax
  Win32PointerApi *v30; // rcx
  __int64 v31; // rcx
  int v32; // ecx
  __int64 v33; // rbx
  unsigned int v34; // eax
  LPARAM v35; // r9
  UINT v36; // edx
  unsigned int v37; // eax
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // ebx
  unsigned int v42; // eax
  int *v43; // rbx
  int v44; // r12d
  HKEY v45; // rax
  unsigned int v46; // eax
  int v47; // edi
  unsigned int v48; // eax
  unsigned __int16 v49; // ax
  __int16 v50; // ax
  int v51; // r12d
  HKEY v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned __int16 v55; // ax
  unsigned __int16 v56; // ax
  int v57; // edi
  unsigned int v58; // eax
  __int16 v59; // ax
  unsigned int v60; // eax
  unsigned __int16 v61; // ax
  unsigned int v62; // eax
  unsigned int v63; // eax
  __int64 v64; // rdx
  unsigned int v65; // eax
  HKEY v66; // rax
  int v67; // ebx
  int v68; // edi
  unsigned int v69; // eax
  int v70; // ebx
  int v71; // edi
  unsigned int v72; // eax
  int v73; // ebx
  unsigned int v74; // eax
  HHOOK v75; // rcx
  BOOL v76; // eax
  DWORD v77; // ebx
  unsigned int v78; // eax
  DWORD WindowThreadProcessId; // ebx
  DWORD CurrentThreadId; // eax
  HKEY v81; // rax
  unsigned int v82; // eax
  unsigned int v83; // eax
  DWORD LastError; // ebx
  unsigned int v85; // eax
  HHOOK v86; // rax
  BOOL v87; // eax
  DWORD v88; // ebx
  unsigned int v89; // eax
  unsigned int v90; // eax
  int v91; // ebx
  unsigned int v92; // eax
  HMODULE Library; // rax
  HMODULE v94; // rdi
  FARPROC ProcAddress; // rbx
  HMODULE v96; // rax
  HMODULE v97; // rbx
  FARPROC v98; // rax
  HMODULE v99; // rax
  HMODULE v100; // rbx
  FARPROC v101; // rax
  unsigned int v102; // eax
  int v103; // ebx
  unsigned int v104; // eax
  __int64 v105; // rcx
  int v106; // ebx
  unsigned int v107; // eax
  unsigned int v108; // eax
  __int64 v109; // [rsp+28h] [rbp-B9h]
  _BOOL8 v110; // [rsp+40h] [rbp-A1h]
  int v111; // [rsp+48h] [rbp-99h] BYREF
  __int64 v112; // [rsp+50h] [rbp-91h] BYREF
  HMODULE phModule; // [rsp+58h] [rbp-89h] BYREF
  struct tagMSG v114; // [rsp+60h] [rbp-81h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+90h] [rbp-51h] BYREF

  v110 = 0;
  memset(&v114, 0, sizeof(v114));
  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
    || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
  {
    v10 = lParam;
  }
  else
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = lParam;
    WPP_SF_DDqii(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, CurrentThreadActivityIdPrefix, Msg, a2, wParam, lParam);
  }
  if ( *((_DWORD *)this + 252) && Msg - 512 <= 0xE )
  {
    if ( Msg == 513 || Msg == 515 || Msg == 516 || Msg == 518 || Msg == 519 || Msg == 521 )
    {
      v13 = CTSInput::CaptureRelativeMouse(this, Msg);
      if ( v13 >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 30;
    }
    else
    {
      if ( Msg != 523 && Msg != 525 )
        return 0;
      v13 = CTSInput::CaptureRelativeMouse(this, WORD1(wParam));
      if ( v13 >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 31;
    }
    LODWORD(v109) = v13;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
      v14,
      (__int64)"CaptureRelativeMouse failed.",
      v109);
    return 0;
  }
  if ( (unsigned int)CTSInput::IHPostMessageToMainWindow(this, Msg, wParam, v10) )
    return 0;
  LODWORD(v112) = 0;
  if ( Msg == 689 )
  {
    v18 = *((_QWORD *)this + 161);
    v111 = 0;
    (*(void (__fastcall **)(__int64, const char *, int *))(*(_QWORD *)v18 + 120LL))(v18, "WslgModeEnabled", &v111);
    if ( wParam == 8 )
    {
      *((_DWORD *)this + 283) = GetAsyncKeyState(91) & 0x8000;
      LODWORD(v112) = GetAsyncKeyState(92) & 0x8000;
      *((_DWORD *)this + 284) = v112;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v19 = *((_DWORD *)this + 283);
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
          v20,
          v19,
          v112);
        v10 = lParam;
      }
      if ( !v111 )
        *((_DWORD *)this + 197) = 1;
      LODWORD(v112) = 1;
    }
    else if ( wParam == 7 && !*((_DWORD *)this + 334) )
    {
      if ( v111 )
      {
        *((_DWORD *)this + 241) &= 0xFFFFFCFF;
        *(_QWORD *)((char *)this + 1132) = 0;
      }
      else
      {
        *((_DWORD *)this + 287) = 1;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v22);
        }
        v23 = MapVirtualKeyW(0x10u, 0);
        CTSInput::IHInjectKey(this, 0x100u, 0x10u, v23);
        v24 = MapVirtualKeyW(0x10u, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0x10u, v24);
        v25 = MapVirtualKeyW(0x5Bu, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0x5Bu, v25 | 0x8100);
        *((_DWORD *)this + 241) &= ~0x100u;
        *((_DWORD *)this + 283) = 0;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v26);
        }
        v27 = MapVirtualKeyW(0x10u, 0);
        CTSInput::IHInjectKey(this, 0x100u, 0x10u, v27);
        v28 = MapVirtualKeyW(0x10u, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0x10u, v28);
        v29 = MapVirtualKeyW(0x5Cu, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0x5Cu, v29 | 0x8100);
        *((_DWORD *)this + 241) &= ~0x200u;
        *((_DWORD *)this + 284) = 0;
        *((_DWORD *)this + 287) = 0;
      }
    }
    goto LABEL_39;
  }
  if ( Msg - 585 <= 1 )
  {
    v30 = (Win32PointerApi *)*((_QWORD *)this + 178);
    v111 = 0;
    if ( (unsigned int)Win32PointerApi::GetPointerType(
                         v30,
                         (unsigned __int16)wParam,
                         (enum tagRDP_POINTER_INPUT_TYPE *)&v111) )
    {
      if ( v111 == 2 )
      {
        if ( Msg == 585 )
        {
          if ( _InterlockedIncrement((volatile signed __int32 *)this + 409) == 1 )
          {
            v31 = *((_QWORD *)this + 164);
            LODWORD(phModule) = (__int16)v10;
            HIDWORD(phModule) = SWORD1(v10);
            (*(void (__fastcall **)(__int64, HMODULE *))(*(_QWORD *)v31 + 368LL))(v31, &phModule);
          }
          goto LABEL_39;
        }
        if ( Msg == 586 )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 409);
          goto LABEL_67;
        }
      }
    }
  }
  if ( Msg - 581 <= 2 || Msg == 586 )
  {
LABEL_67:
    if ( !(unsigned int)CTSInput::ProcessPointerMessage((CTSInput *)((char *)this + 8), Msg, wParam, a2, 1) )
      goto LABEL_273;
    return v110;
  }
  if ( Msg == 568 )
  {
    CTSInput::ProcessPointerDeviceChange(this, wParam, v10);
    return v110;
  }
LABEL_39:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePTPRemoting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnablePTPRemoting>::GetImpl'::`2'::impl)
    && Msg - 571 <= 1 )
  {
    v112 = 0;
    phModule = (HMODULE)((char *)this + 1192);
    CTSCriticalSection::Lock((CTSInput *)((char *)this + 1192));
    v21 = 0;
    if ( *((_QWORD *)this + 174) )
    {
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v112);
      v21 = *((_QWORD *)this + 174);
      v112 = v21;
      TCntPtr<IPin>::SafeAddRef(&v112);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&phModule);
    if ( v21 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 104LL))(v21, Msg);
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v112);
    return 0;
  }
  if ( Msg - 512 <= 0xE || Msg - 255 <= 0x14 && (v32 = 1048679, _bittest(&v32, Msg - 255)) || Msg == 675 || (_DWORD)v112 )
  {
    if ( wParam == 18512 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 187) + 72LL))(*((_QWORD *)this + 187), 0, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v108 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v108);
      }
      v114.hwnd = a2;
      v114.message = Msg;
      v114.wParam = wParam;
      v114.lParam = v10;
      CTSInput::internalProcessInput(this, &v114);
    }
    return v110;
  }
  if ( Msg > 0x102 )
  {
    if ( Msg != 259 && Msg != 262 && Msg != 263 && Msg != 274 )
    {
      switch ( Msg )
      {
        case 0x8001u:
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v104 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v104);
          }
          CTSInput::IHHandleLocalLockDesktop(this);
          break;
        case 0x8002u:
          v103 = *((_DWORD *)this + 287);
          *((_DWORD *)this + 287) = 1;
          CTSInput::IHSyncToggleKeys(this);
          *((_DWORD *)this + 287) = v103;
          break;
        case 0x8003u:
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v102 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v102);
          }
          CTSInput::IHCheckPointerInputRemoting(this);
          break;
        default:
          goto LABEL_273;
      }
      return v110;
    }
    goto LABEL_285;
  }
  if ( Msg == 258 )
  {
LABEL_285:
    v105 = *((_QWORD *)this + 183);
    if ( v105 )
    {
      v106 = (*(__int64 (__fastcall **)(__int64, WPARAM, _QWORD))(*(_QWORD *)v105 + 72LL))(v105, wParam, 0);
      if ( v106 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v107 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v107, v106);
      }
      return v110;
    }
    return 0;
  }
  if ( Msg == 1 )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 157), 0);
    CurrentThreadId = GetCurrentThreadId();
    if ( !AttachThreadInput(CurrentThreadId, WindowThreadProcessId, 1) )
    {
      v81 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_222:
        if ( CTSInput::TlsIndex == -1 )
        {
          if ( v81 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v81[7] & 1) != 0 && *((_BYTE *)v81 + 25) >= 3u )
          {
            v90 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v90);
          }
        }
        else if ( TlsSetValue(CTSInput::TlsIndex, this) )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v83 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
              v83,
              this);
          }
          phModule = 0;
          if ( !GetModuleHandleExW(2u, 0, &phModule) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v85 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v109) = LastError;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                39,
                (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
                v85,
                (__int64)"GetModuleHandleExW(GET_MODULE_HANDLE_EX_FLAG_UNCHANGED_REFCOUNT, NULL) failed",
                v109);
            }
          }
          v86 = SetWindowsHookExW(13, CTSInput::IHStaticLowLevelKeyboardProc, phModule, 0);
          *((_QWORD *)this + 166) = v86;
          if ( v86 )
          {
            v87 = WTSRegisterSessionNotification(a2, 0);
            v110 = v87;
            if ( v87 )
            {
              *((_DWORD *)this + 335) = 1;
            }
            else
            {
              v88 = GetLastError();
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v89 = RdpWppGetCurrentThreadActivityIdPrefix();
                LODWORD(v109) = v88;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  40,
                  (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
                  v89,
                  (__int64)"Failed WTSRegisterSessionNotification",
                  v109);
              }
              *((_DWORD *)this + 334) = 0;
            }
            if ( *((_DWORD *)this + 404) )
              *((_DWORD *)this + 335) = 1;
            goto LABEL_248;
          }
        }
        *((_DWORD *)this + 334) = 0;
LABEL_248:
        v91 = (*(__int64 (__fastcall **)(_QWORD, const char *, bool))(**((_QWORD **)this + 161) + 32LL))(
                *((_QWORD *)this + 161),
                "EnableWindowsKey",
                *((_QWORD *)this + 166) != 0);
        if ( v91 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v92 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v109) = v91;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
            v92,
            (__int64)"SetBoolProperty(TS_PROP_CORE_ENABLE_WINDOWS_KEY) failed!",
            v109);
        }
        CTSInput::RemoveKeyboardHook(this);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePTPRemoting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnablePTPRemoting>::GetImpl'::`2'::impl) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePTPRemoting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnablePTPRemoting>::GetImpl'::`2'::impl) )
          {
            Library = LoadLibraryExW(L"user32.dll", 0, 0);
            v94 = Library;
            if ( Library )
            {
              ProcAddress = GetProcAddress(Library, (LPCSTR)0xA80);
              FreeLibrary(v94);
              if ( ProcAddress )
              {
                v96 = LoadLibraryExW(L"user32.dll", 0, 0);
                v97 = v96;
                if ( v96 )
                {
                  v98 = GetProcAddress(v96, "RegisterPointerDeviceNotifications");
                  if ( v98 )
                    ((void (__fastcall *)(HWND, _QWORD))v98)(a2, 0);
                  FreeLibrary(v97);
                }
                if ( !(unsigned int)CUT::UT_ReadRegistryInt(&sourceString, L"ForceMouseWheelForTouchpad", 0, 2) )
                {
                  v99 = LoadLibraryExW(L"user32.dll", 0, 0);
                  v100 = v99;
                  if ( v99 )
                  {
                    v101 = GetProcAddress(v99, (LPCSTR)0xA81);
                    if ( v101 )
                      ((void (__fastcall *)(HWND, __int64))v101)(a2, 1);
                    FreeLibrary(v100);
                  }
                }
              }
            }
          }
        }
        return v110;
      }
      v82 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v82);
    }
    v81 = WPP_GLOBAL_Control;
    goto LABEL_222;
  }
  if ( Msg != 2 )
  {
    if ( Msg != 7 )
    {
      if ( Msg != 8 )
      {
        if ( Msg != 15 )
        {
          if ( Msg == 20 )
            return 1;
          if ( Msg == 32 )
          {
            if ( !*((_DWORD *)this + 404) )
            {
              SetCursor(*((HCURSOR *)this + 137));
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v33 = *((_QWORD *)this + 137);
                v34 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  43,
                  &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
                  v34,
                  v33);
              }
            }
            v35 = lParam;
            v36 = 32;
            return DefWindowProcW(a2, v36, wParam, v35);
          }
LABEL_273:
          v35 = v10;
          v36 = Msg;
          return DefWindowProcW(a2, v36, wParam, v35);
        }
        memset_0(&Paint, 0, sizeof(Paint));
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v37 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v37);
        }
        BeginPaint(a2, &Paint);
        EndPaint(a2, &Paint);
        return v110;
      }
      *((_DWORD *)this + 313) = 0;
      if ( *((_DWORD *)this + 290) )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_111;
        }
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        v39 = 47;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_111;
        }
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        v39 = 48;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v38);
LABEL_111:
      v40 = *((_QWORD *)this + 163);
      *((_DWORD *)this + 289) = 0;
      v41 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 712LL))(v40, 0);
      if ( v41 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v109) = v41;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
          v42,
          (__int64)"TriggerFocusChanged Failed",
          v109);
      }
      v43 = (int *)((char *)this + 1148);
      if ( GetKeyState(165) >= 0 )
      {
        v47 = lParam;
      }
      else
      {
        v44 = *v43;
        *v43 = 1;
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v46 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v46);
          v45 = WPP_GLOBAL_Control;
        }
        v47 = lParam;
        if ( !*((_DWORD *)this + 336) || (_DWORD)lParam )
        {
          if ( v45 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v45[7] & 1) != 0 && *((_BYTE *)v45 + 25) >= 4u )
          {
            v48 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v48);
          }
          v49 = MapVirtualKeyW(9u, 0);
          CTSInput::IHInjectKey(this, 0x105u, 9u, v49);
        }
        v50 = MapVirtualKeyW(0xA5u, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0xA5u, v50 | 0x100);
        if ( *((_DWORD *)this + 336) || *((_DWORD *)this + 295) )
          *((_DWORD *)this + 241) &= ~2u;
        *v43 = v44;
      }
      if ( GetKeyState(164) < 0 )
      {
        v43 = (int *)((char *)this + 1148);
        v51 = *((_DWORD *)this + 287);
        *((_DWORD *)this + 287) = 1;
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v53 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v53);
          v52 = WPP_GLOBAL_Control;
        }
        if ( !*((_DWORD *)this + 336) || v47 )
        {
          if ( v52 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v52[7] & 1) != 0 && *((_BYTE *)v52 + 25) >= 4u )
          {
            v54 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v54);
          }
          v55 = MapVirtualKeyW(9u, 0);
          CTSInput::IHInjectKey(this, 0x105u, 9u, v55);
        }
        v56 = MapVirtualKeyW(0xA4u, 0);
        CTSInput::IHInjectKey(this, 0x101u, 0xA4u, v56);
        if ( *((_DWORD *)this + 336) || *((_DWORD *)this + 295) )
          *((_DWORD *)this + 241) &= ~1u;
        *v43 = v51;
      }
      if ( *((_DWORD *)this + 291) )
      {
        v57 = *v43;
        *v43 = 1;
        if ( GetKeyState(163) < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v58 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v58);
          }
          v59 = MapVirtualKeyW(0xA3u, 0);
          CTSInput::IHInjectKey(this, 0x101u, 0xA3u, v59 | 0x100);
          if ( *((_DWORD *)this + 336) )
            *((_DWORD *)this + 241) &= ~0x20u;
        }
        if ( GetKeyState(162) < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v60 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v60);
          }
          v61 = MapVirtualKeyW(0xA2u, 0);
          CTSInput::IHInjectKey(this, 0x101u, 0xA2u, v61);
          if ( *((_DWORD *)this + 336) )
            *((_DWORD *)this + 241) &= ~0x10u;
        }
        *((_DWORD *)this + 291) = 0;
        *v43 = v57;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 165) + 64LL))(
        *((_QWORD *)this + 165),
        0,
        3);
      *((_DWORD *)this + 259) = *((_DWORD *)this + 253);
      CTSInput::ReleaseRelativeMouse(this);
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v62 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v62);
      }
      if ( !*((_DWORD *)this + 265) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 165) + 32LL))(*((_QWORD *)this + 165));
      if ( !*((_DWORD *)this + 365) )
        CTSInput::CiceroRestoreLangBar((CTSInput *)((char *)this + 8));
      CTSInput::RemoveKeyboardHook(this);
      return 0;
    }
    if ( *((_DWORD *)this + 290) )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_185;
      }
      v63 = RdpWppGetCurrentThreadActivityIdPrefix();
      v64 = 57;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_185;
      }
      v63 = RdpWppGetCurrentThreadActivityIdPrefix();
      v64 = 58;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v64, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v63);
LABEL_185:
    CTSInput::IHGatherSingleKeyState(this, 91);
    CTSInput::IHGatherSingleKeyState(this, 92);
    CTSInput::ReinsertKeyboardHook(this);
    *((_DWORD *)this + 197) = 1;
    *((_DWORD *)this + 289) = 1;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v65 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids, v65);
    }
    CTSInput::NotifyFocusGained(this, v10);
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v67 = *((_DWORD *)this + 259);
      v68 = *((_DWORD *)this + 262);
      v69 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
        v69,
        v68,
        v67);
      v66 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)this + 262) )
      goto LABEL_197;
    if ( !*((_DWORD *)this + 259) || !*((_DWORD *)this + 258) )
      goto LABEL_199;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 165) + 184LL))(*((_QWORD *)this + 165)) )
LABEL_197:
      CTSInput::CaptureRelativeMouse(this, 0);
    v66 = WPP_GLOBAL_Control;
LABEL_199:
    if ( v66 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v66[7] & 1) != 0 && *((_BYTE *)v66 + 25) >= 4u )
    {
      v70 = *((_DWORD *)this + 252);
      v71 = *((_DWORD *)this + 253);
      v72 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
        v72,
        v71,
        v70);
    }
    if ( !*((_DWORD *)this + 365) )
      CTSInput::CiceroHideLangBar((CTSInput *)((char *)this + 8));
    v73 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 163) + 712LL))(*((_QWORD *)this + 163), 1);
    if ( v73 < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v74 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v109) = v73;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
        v74,
        (__int64)"TriggerFocusChanged Failed",
        v109);
    }
    return 0;
  }
  v75 = (HHOOK)*((_QWORD *)this + 166);
  if ( !v75 )
    return 0;
  UnhookWindowsHookEx(v75);
  *((_QWORD *)this + 166) = 0;
  v76 = WTSUnRegisterSessionNotification(a2);
  v16 = v76;
  if ( !v76 )
  {
    v77 = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v78 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v109) = v77;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids,
        v78,
        (__int64)"Failed WTSRegisterSessionNotification",
        v109);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180053a40  push    rbp
0x180053a42  push    rbx
0x180053a43  push    rsi
0x180053a44  push    rdi
0x180053a45  push    r12
0x180053a47  push    r13
0x180053a49  push    r14
0x180053a4b  push    r15
0x180053a4d  lea     rbp, [rsp-17h]
0x180053a52  sub     rsp, 0F8h
0x180053a59  mov     rax, cs:__security_cookie
0x180053a60  xor     rax, rsp
0x180053a63  mov     [rbp+4Fh+var_50], rax
0x180053a67  xorps   xmm0, xmm0
0x180053a6a  xor     r14d, r14d
0x180053a6d  mov     [rsp+130h+var_F0], r14
0x180053a72  mov     r15, r9
0x180053a75  movups  xmmword ptr [rsp+130h+var_D0.hwnd], xmm0
0x180053a7a  mov     edi, r8d
0x180053a7d  mov     r13, rdx
0x180053a80  movups  xmmword ptr [rbp+4Fh+var_D0.wParam], xmm0
0x180053a84  mov     rsi, rcx
0x180053a87  movups  xmmword ptr [rbp+4Fh+var_D0.time], xmm0
0x180053a8b  mov     rax, cs:WPP_GLOBAL_Control
0x180053a92  lea     rcx, WPP_GLOBAL_Control
0x180053a99  cmp     rax, rcx
0x180053a9c  jz      short loc_180053ADB
0x180053a9e  test    byte ptr [rax+1Ch], 1
0x180053aa2  jz      short loc_180053ADB
0x180053aa4  cmp     byte ptr [rax+19h], 5
0x180053aa8  jb      short loc_180053ADB
0x180053aaa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ab6  mov     r9d, eax
0x180053ab9  mov     rbx, [rbp+4Fh+lParam]
0x180053abd  mov     [rsp+130h+var_F8], rbx
0x180053ac2  mov     [rsp+130h+var_100], r15
0x180053ac7  mov     rcx, [rcx+10h]
0x180053acb  mov     [rsp+130h+var_108], r13
0x180053ad0  mov     [rsp+130h+var_110], edi
0x180053ad4  call    WPP_SF_DDqii
0x180053ad9  jmp     short loc_180053ADF
0x180053adb  mov     rbx, [rbp+4Fh+lParam]
0x180053adf  cmp     [rsi+3F0h], r14d
0x180053ae6  jz      loc_180053C12
0x180053aec  lea     eax, [rdi-200h]
0x180053af2  cmp     eax, 0Eh
0x180053af5  ja      loc_180053C12
0x180053afb  mov     eax, edi
0x180053afd  mov     r12d, 2
0x180053b03  sub     eax, 201h
0x180053b08  jz      loc_180053BD4
0x180053b0e  sub     eax, r12d
0x180053b11  jz      loc_180053BD4
0x180053b17  sub     eax, 1
0x180053b1a  jz      loc_180053BD4
0x180053b20  sub     eax, r12d
0x180053b23  jz      loc_180053BD4
0x180053b29  sub     eax, 1
0x180053b2c  jz      loc_180053BD4
0x180053b32  sub     eax, r12d
0x180053b35  jz      loc_180053BD4
0x180053b3b  sub     eax, r12d
0x180053b3e  jz      short loc_180053B45
0x180053b40  cmp     eax, r12d
0x180053b43  jnz     short loc_180053BAE
0x180053b45  shr     r15, 10h
0x180053b49  mov     rcx, rsi; this
0x180053b4c  movzx   edx, r15w; unsigned int
0x180053b50  call    ?CaptureRelativeMouse@CTSInput@@AEAAJI@Z; CTSInput::CaptureRelativeMouse(uint)
0x180053b55  mov     ebx, eax
0x180053b57  test    eax, eax
0x180053b59  jns     short loc_180053BAE
0x180053b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b62  lea     rax, WPP_GLOBAL_Control
0x180053b69  cmp     rcx, rax
0x180053b6c  jz      short loc_180053BAE
0x180053b6e  test    byte ptr [rcx+1Ch], 8
0x180053b72  jz      short loc_180053BAE
0x180053b74  cmp     [rcx+19h], r12b
0x180053b78  jb      short loc_180053BAE
0x180053b7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053b7f  mov     edx, 1Fh
0x180053b84  lea     rcx, aCapturerelativ; "CaptureRelativeMouse failed."
0x180053b8b  mov     dword ptr [rsp+130h+var_108], ebx
0x180053b8f  mov     qword ptr [rsp+130h+var_110], rcx
0x180053b94  lea     r8, WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids
0x180053b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ba2  mov     r9d, eax
0x180053ba5  mov     rcx, [rcx+10h]
0x180053ba9  call    WPP_SF_DsD
0x180053bae  mov     rdi, r14
0x180053bb1  mov     rax, rdi
0x180053bb4  mov     rcx, [rbp+4Fh+var_50]
0x180053bb8  xor     rcx, rsp; StackCookie
0x180053bbb  call    __security_check_cookie
0x180053bc0  add     rsp, 0F8h
0x180053bc7  pop     r15
0x180053bc9  pop     r14
0x180053bcb  pop     r13
0x180053bcd  pop     r12
0x180053bcf  pop     rdi
0x180053bd0  pop     rsi
0x180053bd1  pop     rbx
0x180053bd2  pop     rbp
0x180053bd3  retn
0x180053bd4  mov     edx, edi; unsigned int
0x180053bd6  mov     rcx, rsi; this
0x180053bd9  call    ?CaptureRelativeMouse@CTSInput@@AEAAJI@Z; CTSInput::CaptureRelativeMouse(uint)
0x180053bde  mov     ebx, eax
0x180053be0  test    eax, eax
0x180053be2  jns     short loc_180053BAE
0x180053be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180053beb  lea     rax, WPP_GLOBAL_Control
0x180053bf2  cmp     rcx, rax
0x180053bf5  jz      short loc_180053BAE
0x180053bf7  test    byte ptr [rcx+1Ch], 8
0x180053bfb  jz      short loc_180053BAE
0x180053bfd  cmp     [rcx+19h], r12b
0x180053c01  jb      short loc_180053BAE
0x180053c03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053c08  mov     edx, 1Eh
0x180053c0d  jmp     loc_180053B84
0x180053c12  mov     r9, rbx; lParam
0x180053c15  mov     r8, r15; wParam
0x180053c18  mov     edx, edi; Msg
0x180053c1a  mov     rcx, rsi; this
0x180053c1d  call    ?IHPostMessageToMainWindow@CTSInput@@AEAAHI_K_J@Z; CTSInput::IHPostMessageToMainWindow(uint,unsigned __int64,__int64)
0x180053c22  test    eax, eax
0x180053c24  jnz     short loc_180053BAE
0x180053c26  mov     dword ptr [rsp+130h+var_E0], r14d
0x180053c2b  lea     r14, WPP_eef7886103e431c5c9754a8dcaf7b259_Traceguids
0x180053c32  lea     r12d, [rax+2]
0x180053c36  cmp     edi, 2B1h
0x180053c3c  jnz     loc_180053F63
0x180053c42  mov     rcx, [rsi+508h]
0x180053c49  lea     r8, [rsp+130h+var_E8]
0x180053c4e  mov     [rsp+130h+var_E8], eax
0x180053c52  lea     rdx, aWslgmodeenable; "WslgModeEnabled"
0x180053c59  mov     rax, [rcx]
0x180053c5c  mov     rax, [rax+78h]
0x180053c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c65  cmp     r15, 8
0x180053c69  jnz     loc_180053DA6
0x180053c6f  lea     ecx, [r12+59h]; vKey
0x180053c74  call    cs:__imp_GetAsyncKeyState
0x180053c7a  and     eax, 8000h
0x180053c7f  lea     ecx, [r12+5Ah]; vKey
0x180053c84  mov     [rsi+46Ch], eax
0x180053c8a  call    cs:__imp_GetAsyncKeyState
0x180053c90  and     eax, 8000h
0x180053c95  mov     dword ptr [rsp+130h+var_E0], eax
0x180053c99  mov     [rsi+470h], eax
0x180053c9f  mov     rax, cs:WPP_GLOBAL_Control
0x180053ca6  lea     rcx, WPP_GLOBAL_Control
0x180053cad  cmp     rax, rcx
0x180053cb0  jz      short loc_180053CF4
0x180053cb2  test    byte ptr [rax+1Ch], 1
0x180053cb6  jz      short loc_180053CF4
0x180053cb8  cmp     byte ptr [rax+19h], 5
0x180053cbc  jb      short loc_180053CF4
0x180053cbe  mov     ebx, [rsi+46Ch]
0x180053cc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053cc9  mov     ecx, dword ptr [rsp+130h+var_E0]
0x180053ccd  lea     edx, [r12+1Eh]
0x180053cd2  mov     dword ptr [rsp+130h+var_108], ecx
0x180053cd6  mov     r9d, eax
0x180053cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ce0  mov     r8, r14
0x180053ce3  mov     [rsp+130h+var_110], ebx
0x180053ce7  mov     rcx, [rcx+10h]
0x180053ceb  call    WPP_SF_DLD
0x180053cf0  mov     rbx, [rbp+4Fh+lParam]
0x180053cf4  cmp     [rsp+130h+var_E8], 0
0x180053cf9  jnz     short loc_180053D05
0x180053cfb  mov     dword ptr [rsi+314h], 1
0x180053d05  mov     dword ptr [rsp+130h+var_E0], 1
0x180053d0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnablePTPRemoting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePTPRemoting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePTPRemoting> `wil::Feature<__WilFeatureTraits_Feature_EnablePTPRemoting>::GetImpl(void)'::`2'::impl
0x180053d14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePTPRemoting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePTPRemoting>::__private_IsEnabled(void)
0x180053d19  xor     edx, edx; Val
0x180053d1b  test    al, al
0x180053d1d  jz      loc_18005405D
0x180053d23  lea     eax, [rdi-23Bh]
0x180053d29  cmp     eax, 1
0x180053d2c  ja      loc_18005405D
0x180053d32  lea     rcx, [rsi+4A8h]; this
0x180053d39  mov     [rsp+130h+var_E0], rdx
0x180053d3e  mov     [rsp+130h+phModule], rcx
0x180053d43  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180053d48  xor     r14d, r14d
0x180053d4b  mov     ebx, r14d
0x180053d4e  cmp     [rsi+570h], r14
0x180053d55  jz      short loc_180053D77
0x180053d57  lea     rcx, [rsp+130h+var_E0]; void *
0x180053d5c  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x180053d61  mov     rbx, [rsi+570h]
0x180053d68  lea     rcx, [rsp+130h+var_E0]
0x180053d6d  mov     [rsp+130h+var_E0], rbx
0x180053d72  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x180053d77  lea     rcx, [rsp+130h+phModule]; this
0x180053d7c  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180053d81  test    rbx, rbx
0x180053d84  jz      short loc_180053D97
0x180053d86  mov     rax, [rbx]
0x180053d89  mov     edx, edi
0x180053d8b  mov     rcx, rbx
0x180053d8e  mov     rax, [rax+68h]
0x180053d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d97  lea     rcx, [rsp+130h+var_E0]; void *
0x180053d9c  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x180053da1  jmp     loc_180053BAE
0x180053da6  cmp     r15, 7
0x180053daa  jnz     loc_180053D0D
0x180053db0  xor     eax, eax
0x180053db2  cmp     [rsi+538h], eax
0x180053db8  jnz     loc_180053D0D
0x180053dbe  cmp     [rsp+130h+var_E8], eax
0x180053dc2  jz      short loc_180053DDA
0x180053dc4  and     dword ptr [rsi+3C4h], 0FFFFFCFFh
0x180053dce  mov     [rsi+46Ch], rax
0x180053dd5  jmp     loc_180053D0D
0x180053dda  mov     dword ptr [rsi+47Ch], 1
0x180053de4  mov     rax, cs:WPP_GLOBAL_Control
0x180053deb  lea     rcx, WPP_GLOBAL_Control
0x180053df2  cmp     rax, rcx
0x180053df5  jz      short loc_180053E23
0x180053df7  test    byte ptr [rax+1Ch], 1
0x180053dfb  jz      short loc_180053E23
0x180053dfd  cmp     byte ptr [rax+19h], 5
0x180053e01  jb      short loc_180053E23
0x180053e03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e0f  mov     edx, 21h ; '!'
0x180053e14  mov     r9d, eax
0x180053e17  mov     r8, r14
0x180053e1a  mov     rcx, [rcx+10h]
0x180053e1e  call    WPP_SF_d
0x180053e23  xor     edx, edx; uMapType
0x180053e25  lea     ecx, [rdx+10h]; uCode
0x180053e28  call    cs:__imp_MapVirtualKeyW
0x180053e2e  mov     edx, 100h; unsigned int
0x180053e33  mov     r8d, 10h; unsigned __int64
0x180053e39  mov     r9d, eax; unsigned __int16
0x180053e3c  mov     rcx, rsi; this
0x180053e3f  call    ?IHInjectKey@CTSInput@@AEAAXI_KG@Z; CTSInput::IHInjectKey(uint,unsigned __int64,ushort)
0x180053e44  xor     edx, edx; uMapType
0x180053e46  lea     ecx, [rdx+10h]; uCode
0x180053e49  call    cs:__imp_MapVirtualKeyW
0x180053e4f  mov     edx, 101h; unsigned int
0x180053e54  mov     r8d, 10h; unsigned __int64
0x180053e5a  mov     r9d, eax; unsigned __int16
0x180053e5d  mov     rcx, rsi; this
0x180053e60  call    ?IHInjectKey@CTSInput@@AEAAXI_KG@Z; CTSInput::IHInjectKey(uint,unsigned __int64,ushort)
0x180053e65  xor     edx, edx; uMapType
0x180053e67  lea     ecx, [rdx+5Bh]; uCode
0x180053e6a  call    cs:__imp_MapVirtualKeyW
0x180053e70  mov     r9d, 8100h
0x180053e76  mov     edx, 101h; unsigned int
0x180053e7b  or      r9w, ax; unsigned __int16
0x180053e7f  mov     r8d, 5Bh ; '['; unsigned __int64
0x180053e85  mov     rcx, rsi; this
0x180053e88  call    ?IHInjectKey@CTSInput@@AEAAXI_KG@Z; CTSInput::IHInjectKey(uint,unsigned __int64,ushort)
0x180053e8d  btr     dword ptr [rsi+3C4h], 8
0x180053e95  mov     dword ptr [rsi+46Ch], 0
0x180053e9f  mov     rax, cs:WPP_GLOBAL_Control
0x180053ea6  lea     rcx, WPP_GLOBAL_Control
0x180053ead  cmp     rax, rcx
0x180053eb0  jz      short loc_180053EDE
0x180053eb2  test    byte ptr [rax+1Ch], 1
0x180053eb6  jz      short loc_180053EDE
0x180053eb8  cmp     byte ptr [rax+19h], 5
0x180053ebc  jb      short loc_180053EDE
0x180053ebe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180053eca  mov     edx, 22h ; '"'
0x180053ecf  mov     r9d, eax
0x180053ed2  mov     r8, r14
0x180053ed5  mov     rcx, [rcx+10h]
0x180053ed9  call    WPP_SF_d
0x180053ede  xor     edx, edx; uMapType
0x180053ee0  lea     ecx, [rdx+10h]; uCode
0x180053ee3  call    cs:__imp_MapVirtualKeyW
0x180053ee9  mov     edx, 100h; unsigned int
0x180053eee  mov     r8d, 10h; unsigned __int64
0x180053ef4  mov     r9d, eax; unsigned __int16
0x180053ef7  mov     rcx, rsi; this
0x180053efa  call    ?IHInjectKey@CTSInput@@AEAAXI_KG@Z; CTSInput::IHInjectKey(uint,unsigned __int64,ushort)
0x180053eff  xor     edx, edx; uMapType
0x180053f01  lea     ecx, [rdx+10h]; uCode
0x180053f04  call    cs:__imp_MapVirtualKeyW
0x180053f0a  mov     edx, 101h; unsigned int
0x180053f0f  mov     r8d, 10h; unsigned __int64
0x180053f15  mov     r9d, eax; unsigned __int16
0x180053f18  mov     rcx, rsi; this
0x180053f1b  call    ?IHInjectKey@CTSInput@@AEAAXI_KG@Z; CTSInput::IHInjectKey(uint,unsigned __int64,ushort)
0x180053f20  xor     edx, edx; uMapType
0x180053f22  lea     ecx, [rdx+5Ch]; uCode
0x180053f25  call    cs:__imp_MapVirtualKeyW
0x180053f2b  mov     r9d, 8100h
0x180053f31  mov     edx, 101h; unsigned int
  ... truncated ...
```
