# CShellBrowser2::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1801ee2b0`
- end: `0x1801ef0df`
- name: `?v_WndProc@CShellBrowser2@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3631`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, HWND, unsigned int, HMENU, LPARAM lParam)`
- caller_count: `0`
- callee_count: `41`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x180046170`
- `0x180065a9c`
- `0x18006ff5c`
- `0x1800727e0`
- `0x180074a68`
- `0x18007ac2c`
- `0x1800cbd24`
- `0x180132728`
- `0x1801a3a30`
- `0x1801a7130`
- `0x1801cfaf8`
- `0x1801da0fc`
- `0x1801de60c`
- `0x1801df42c`
- `0x1801e1b80`
- `0x1801e1f8c`
- `0x1801e2c88`
- `0x1801e37c8`
- `0x1801e4044`
- `0x1801e4308`
- `0x1801e797c`
- `0x1801e82a8`
- `0x1801e8a74`
- `0x1801e8b48`
- `0x1801e9310`
- `0x1801e9640`
- `0x1801e97c4`
- `0x1801e9be4`
- `0x1801eb0d4`
- `0x1801ec5b0`
- `0x1801eda80`
- `0x1801ee2b0`
- `0x1802999d4`
- `0x18029a9d8`
- `0x1802a3970`
- `0x1803c2618`
- `0x180442288`
- `0x180538dc0`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1801eee39`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x1801eee39`
- `KERNEL32!TlsGetValue` at `0x1801ef051`
- `KERNEL32!TlsGetValue` at `0x1801ef051`
- `KERNEL32!GetCurrentThreadId` at `0x1801ee42b`
- `KERNEL32!GetCurrentThreadId` at `0x1801ee8ea`
- `KERNEL32!GetCurrentThreadId` at `0x1801ee42b`
- `KERNEL32!GetCurrentThreadId` at `0x1801ee8ea`
- `USER32!GetWindowRect` at `0x1801eee57`
- `USER32!GetWindowRect` at `0x1801eee57`
- `USER32!SetWindowPos` at `0x1801eed33`
- `USER32!SetWindowPos` at `0x1801eed33`
- `USER32!InvalidateRect` at `0x1801eeb2c`
- `USER32!InvalidateRect` at `0x1801eeb2c`
- `USER32!KillTimer` at `0x1801ee573`
- `USER32!KillTimer` at `0x1801ee573`
- `USER32!RedrawWindow` at `0x1801eec4b`
- `USER32!RedrawWindow` at `0x1801eec4b`
- `USER32!SendMessageW` at `0x1801ee978`
- `USER32!SendMessageW` at `0x1801eeb65`
- `USER32!SendMessageW` at `0x1801eee95`
- `USER32!SendMessageW` at `0x1801eef90`
- `USER32!SendMessageW` at `0x1801ee978`
- `USER32!SendMessageW` at `0x1801eeb65`
- `USER32!SendMessageW` at `0x1801eee95`
- `USER32!SendMessageW` at `0x1801eef90`
- `USER32!GetWindowThreadProcessId` at `0x1801ee910`
- `USER32!GetWindowThreadProcessId` at `0x1801ee910`
- `USER32!FindWindowExW` at `0x1801ee902`
- `USER32!FindWindowExW` at `0x1801ee902`
- `OLEAUT32!__imp_SysFreeString` at `0x1801eec97`
- `OLEAUT32!__imp_SysFreeString` at `0x1801eec97`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ee65f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801eeb87`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801eef21`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ee65f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801eeb87`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801eef21`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ee60a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ee60a`
- `OLEACC!LresultFromObject` at `0x1801ee626`
- `OLEACC!LresultFromObject` at `0x1801ee626`
- `IMM32!ImmReleaseContext` at `0x1801eeadc`
- `IMM32!ImmReleaseContext` at `0x1801eeadc`
- `IMM32!ImmSetCandidateWindow` at `0x1801eeac4`
- `IMM32!ImmSetCandidateWindow` at `0x1801eeac4`
- `IMM32!ImmSetCompositionWindow` at `0x1801eea8a`
- `IMM32!ImmSetCompositionWindow` at `0x1801eea8a`
- `IMM32!ImmGetCompositionWindow` at `0x1801eea73`
- `IMM32!ImmGetCompositionWindow` at `0x1801eea73`
- `IMM32!ImmGetContext` at `0x1801eea4f`
- `IMM32!ImmGetContext` at `0x1801eea4f`
- `IMM32!ImmGetCandidateWindow` at `0x1801eeaad`
- `IMM32!ImmGetCandidateWindow` at `0x1801eeaad`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801eeda1`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801eeda1`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801eeca9`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801eeca9`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801eefca`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801eefd8`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801eefca`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801eefd8`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801ef02f`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801ef02f`

## pseudocode

```c
LRESULT __fastcall CShellBrowser2::v_WndProc(
        CShellBrowser2 *this,
        HWND a2,
        unsigned int a3,
        IUnknown *a4,
        HMENU lParam)
{
  HMENU v5; // rsi
  WPARAM v7; // rdi
  int v10; // r8d
  int v11; // r9d
  HWND *v12; // rcx
  char v13; // r14
  __int64 v14; // r12
  int v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  IUnknown *v18; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  DWORD v20; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  IUnknown *v22; // rcx
  int v23; // ecx
  unsigned int v24; // edx
  __int64 v25; // rcx
  LRESULT result; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v27; // rdx
  IUnknown *MenuBand; // rax
  unsigned int v29; // edx
  CShellBrowser2 *v30; // rcx
  int ShouldForwardMenu; // eax
  unsigned int v32; // r9d
  __int64 v33; // r14
  int (__fastcall ***v34)(_QWORD, GUID *, void **); // rcx
  __int64 v35; // rcx
  unsigned int j; // ecx
  HWND Window; // r14
  DWORD CurrentThreadId; // r12d
  unsigned int v39; // r8d
  HWND v40; // rdx
  HIMC Context; // rax
  HIMC v42; // rdi
  int i; // esi
  CInternetToolbarHost *v44; // rcx
  HWND v45; // rcx
  __int64 v46; // rax
  HWND v47; // rcx
  bool v48; // al
  IUnknown *v49; // rbx
  __int64 v50; // rcx
  HWND v51; // rcx
  UINT v52; // r9d
  __int64 v53; // rcx
  __int64 v54; // rcx
  UINT v55; // edx
  __int64 v56; // rcx
  struct IsoScope *DefaultScope; // rax
  DWORD v58; // eax
  _QWORD *Value; // rbx
  __int64 v60; // rcx
  bool v61; // [rsp+40h] [rbp-61h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-59h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-51h] BYREF
  __int64 v64; // [rsp+58h] [rbp-49h] BYREF
  tagCOMPOSITIONFORM CompForm; // [rsp+60h] [rbp-41h] BYREF
  tagCANDIDATEFORM Candidate; // [rsp+80h] [rbp-21h] BYREF

  v5 = lParam;
  ppvOut = lParam;
  v7 = (WPARAM)a4;
  punk = a4;
  IEObjectSignature::CSignature<23376>::Validate((char *)this + 6868);
  v12 = (HWND *)*((_QWORD *)this + 814);
  v13 = 0;
  v64 = 0;
  if ( v12 )
  {
    if ( (unsigned int)CInternetToolbarHost::_TranslateMenuMessage(
                         (CInternetToolbarHost *)v12,
                         v12[1],
                         a3,
                         (unsigned __int64 *)&punk,
                         (__int64 *)&ppvOut,
                         &v64) )
      return v64;
    v7 = (WPARAM)punk;
    v5 = (HMENU)ppvOut;
  }
  v14 = 3;
  if ( a3 > 0x8066 )
  {
    if ( a3 <= 0x819C )
    {
      if ( a3 == 33180 )
      {
        if ( v7 )
        {
          SetWindowPos(*((HWND *)this + 43), 0, (unsigned __int16)v5, WORD1(v5), (unsigned __int16)v7, WORD1(v7), 0x10u);
          v13 = 1;
        }
        *((_BYTE *)this + 6930) = v13;
        return 0;
      }
      if ( a3 <= 0x8194 )
      {
        switch ( a3 )
        {
          case 0x8194u:
            if ( v5 )
              CShellBrowser2::_ProcessAsyncExec(this, v7, (unsigned int)v5);
            return 0;
          case 0x80EDu:
            goto LABEL_50;
          case 0x8161u:
            v46 = *((_QWORD *)this + 814);
            if ( v46 )
            {
              v47 = *(HWND *)(v46 + 8);
              if ( v47 )
              {
                SendMessageW(v47, a3, v7, (LPARAM)v5);
                return 0;
              }
            }
            punk = 0;
            if ( (int)CBrowserWinMsgPackage_GetInstance((unsigned int)v5, (struct IBrowserAsyncPackage **)&punk) < 0 )
              return 0;
            v48 = IsDualEngineProcess();
            v49 = punk;
            if ( v48 )
              ((void (__fastcall *)(IUnknown *, __int64))punk->lpVtbl[1].AddRef)(punk, 1);
            lpVtbl = v49->lpVtbl;
            v22 = v49;
            goto LABEL_23;
          case 0x8190u:
            v44 = (CInternetToolbarHost *)*((_QWORD *)this + 814);
            if ( v44 )
              CInternetToolbarHost::OnBrowserFrameActivate(v44, v7, (__int64)v5);
            if ( (_WORD)v7 )
            {
              v45 = (HWND)*((_QWORD *)this + 800);
              if ( v45 )
                InvalidateRect(v45, 0, 1);
            }
            else
            {
              CBaseBrowser2::_HideUrlTip(this);
            }
            CBaseBrowser2::_OnFrameWindowActivateBS(this, (_WORD)v7 != 0);
            return 1;
          case 0x8191u:
            Context = ImmGetContext(*((HWND *)this + 54));
            v42 = Context;
            if ( Context )
            {
              memset(&CompForm, 0, sizeof(CompForm));
              if ( ImmGetCompositionWindow(Context, &CompForm) && CompForm.dwStyle )
                ImmSetCompositionWindow(v42, &CompForm);
              for ( i = 0; i < 4; ++i )
              {
                memset(&Candidate, 0, sizeof(Candidate));
                if ( ImmGetCandidateWindow(v42, i, &Candidate) && Candidate.dwStyle )
                  ImmSetCandidateWindow(v42, &Candidate);
              }
              ImmReleaseContext(*((HWND *)this + 54), v42);
            }
            CBaseBrowser2::_HideUrlTip(this);
            return 0;
          case 0x8192u:
            return 1;
          case 0x8193u:
            CShellBrowser2::_OnUIActivate(this, v7 & 1, v7 & 2, (int)v5);
            return 1;
        }
LABEL_204:
        if ( g_msgMSWheel == a3 )
          return SendMessageW(*((HWND *)this + 54), a3, v7, (LPARAM)v5);
        if ( GetSecurityChangedMsg() == a3 )
        {
          (*(void (__fastcall **)(char *, const GUID *, __int64, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 5) + 32LL))(
            (char *)this + 40,
            &CGID_Explorer,
            78,
            0,
            0,
            0);
          return 0;
        }
        if ( a3 == (unsigned int)IsoGetWindowsMessageNumber(2) || a3 == (unsigned int)IsoGetWindowsMessageNumber(3) )
        {
          CShellBrowser2::_BrowserTab_MsgProc(this, a2, a3, v7, (__int64)v5);
          return 0;
        }
        goto LABEL_210;
      }
      if ( a3 == 33174 )
      {
        if ( v5 == (HMENU)1 )
          *((_DWORD *)this + 1714) = v7;
        else
          *((_DWORD *)this + 1715) = v7;
        if ( *((_DWORD *)this + 1715) && *((_DWORD *)this + 1714) )
        {
          WinList_RevokeAsync();
          *((_DWORD *)this + 1714) = 0;
        }
        return 0;
      }
      if ( a3 != 33175 )
      {
        switch ( a3 )
        {
          case 0x8198u:
            LCIEChangeComponentSharedFlagBit_FromComponentThread(0, 7u);
            break;
          case 0x8199u:
            v53 = *((_QWORD *)this + 46);
            if ( v53 )
            {
              LOWORD(CompForm.dwStyle) = 3;
              CompForm.ptCurrentPos.y = 0;
              (*(void (__fastcall **)(__int64, HMENU, tagCOMPOSITIONFORM *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v53 + 88LL))(
                v53,
                v5,
                &CompForm,
                0,
                0,
                0);
              ATL::CComVariant::Clear((ATL::CComVariant *)&CompForm);
            }
            SysFreeString((BSTR)v5);
            return 0;
          case 0x819Au:
            if ( v7 && (v50 = *((_QWORD *)this + 814)) != 0 )
            {
              v51 = *(HWND *)(v50 + 8);
              v52 = 133;
            }
            else
            {
              v51 = (HWND)*((_QWORD *)this + 43);
              v52 = 389;
            }
            RedrawWindow(v51, 0, 0, v52);
            return 0;
          case 0x819Bu:
            *((_DWORD *)this + 1624) |= 0x8000000u;
            *((_DWORD *)this + 1634) = (_DWORD)v5;
            *((_QWORD *)this + 818) = v7;
            break;
          default:
            goto LABEL_204;
        }
        return 0;
      }
LABEL_180:
      v54 = *((_QWORD *)this + 46);
      if ( v54 && !*((_BYTE *)this + 6672) )
      {
        *((_BYTE *)this + 6672) = 1;
        ppvOut = 0;
        punk = 0;
        if ( (*(int (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v54 + 144LL))(v54, &punk) >= 0
          && punk
          && IUnknown_GetWindow(punk, (HWND *)&ppvOut) >= 0
          && ppvOut )
        {
          *(_OWORD *)&CompForm.dwStyle = 0;
          GetWindowRect((HWND)ppvOut, (LPRECT)&CompForm);
          v55 = 522;
          if ( a3 != 33175 )
            v55 = 526;
          SendMessageW(
            (HWND)ppvOut,
            v55,
            v7,
            (unsigned __int16)(LOWORD(CompForm.dwStyle) + 2)
          | ((unsigned __int16)(LOWORD(CompForm.ptCurrentPos.x) + 2) << 16));
        }
        *((_BYTE *)this + 6672) = 0;
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&punk);
      }
      return 0;
    }
    if ( a3 > 0x81A8 )
    {
      if ( a3 == 33777 )
      {
        v60 = *((_QWORD *)this + 859);
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 96LL))(v60);
        return 0;
      }
      if ( a3 == 33794 )
      {
        if ( v7 || v5 )
          CShellBrowser2::_PrepareInternetToolbar(this);
        return 0;
      }
      if ( a3 != 33795 )
      {
        if ( a3 == 33799 )
        {
          ShowManageAddonsInFrameProcess((unsigned int)v5, (HWND)v7);
          return 0;
        }
        if ( a3 == 33828 )
        {
          CShellBrowser2::_OnThumbnailImageProcessed(this, v7);
          return 0;
        }
        goto LABEL_204;
      }
      v61 = 0;
      punk = 0;
      DefaultScope = IsoGetDefaultScope();
      v58 = (*(__int64 (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 680LL))(DefaultScope, 1);
      Value = TlsGetValue(v58);
      if ( Value && (int)TLSGetAlternateOwnerWindow((HWND *)&punk, &v61) >= 0 && !v61 )
      {
        result = (LRESULT)punk;
        Value[18] = punk;
        return result;
      }
      return v64;
    }
    switch ( a3 )
    {
      case 0x81A8u:
        if ( IsDualEngineProcess() )
          CShellBrowser2::_DualEngineOnDeferredCloseCommand(this, v7 != 0, 0);
        return 0;
      case 0x819Du:
        (*(void (__fastcall **)(CShellBrowser2 *))(*(_QWORD *)this + 8LL))(this);
        return 0;
      case 0x819Eu:
        v56 = *((_QWORD *)this + 50);
        if ( !v56 )
          return 0;
        LOWORD(CompForm.dwStyle) = 11;
        if ( v7 )
          LOWORD(CompForm.ptCurrentPos.y) = -1;
        else
          LOWORD(CompForm.ptCurrentPos.y) = 0;
        (*(void (__fastcall **)(__int64, GUID *, __int64, _QWORD, tagCOMPOSITIONFORM *, _QWORD))(*(_QWORD *)v56 + 32LL))(
          v56,
          &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
          62,
          0,
          &CompForm,
          0);
        break;
      case 0x81A0u:
        goto LABEL_180;
      case 0x81A2u:
        CGlobalImageProcessTaskQueue::DeleteTask(v7);
        return 0;
      case 0x81A3u:
        LOWORD(CompForm.dwStyle) = 3;
        CompForm.ptCurrentPos.y = v7;
        (*(void (__fastcall **)(char *, const GUID *, __int64, _QWORD, tagCOMPOSITIONFORM *, _QWORD))(*((_QWORD *)this + 5) + 32LL))(
          (char *)this + 40,
          &CGID_ShellDocView,
          110,
          (unsigned int)v5,
          &CompForm,
          0);
        break;
      case 0x81A7u:
        v16 = *((_DWORD *)this + 1588);
        v17 = 5120;
        goto LABEL_177;
      default:
        goto LABEL_204;
    }
    ATL::CComVariant::Clear((ATL::CComVariant *)&CompForm);
    return 0;
  }
  if ( a3 == 32870 )
  {
    if ( __PAIR64__(*((unsigned __int8 *)this + 6936), *((_DWORD *)this + 1733)) != __PAIR64__(v5 != 0, v7) )
    {
      *((_DWORD *)this + 1733) = v7;
      *((_BYTE *)this + 6936) = v5 != 0;
    }
    return 0;
  }
  if ( a3 > 0x117 )
  {
    if ( a3 > 0x212 )
    {
      switch ( a3 )
      {
        case 0x2E2u:
          goto LABEL_226;
        case 0x319u:
          for ( j = 0; j < 6; ++j )
          {
            if ( LODWORD(qword_1805DF850[j]) == (WORD1(v5) & 0xFFF) )
              return CShellBrowser2::v_OnCommand(this, WORD2(qword_1805DF850[j]) | (WORD1(v7) << 16), (__int64)v5);
          }
          Window = 0;
          CurrentThreadId = GetCurrentThreadId();
          do
            Window = FindWindowExW(0, Window, L"Internet Explorer_Hidden", 0);
          while ( GetWindowThreadProcessId(Window, 0) != CurrentThreadId && Window );
          if ( Window )
          {
            v39 = 793;
            v40 = Window;
            return CBaseBrowser2::v_WndProc(this, v40, v39, v7, (__int64)v5);
          }
          goto LABEL_210;
        case 0x31Au:
LABEL_226:
          if ( *((_QWORD *)this + 800) )
          {
            ImageList_Destroy(*((HIMAGELIST *)this + 801));
            CShellBrowser2::_CreateZoomButtonImage(this);
            SendMessageW(*((HWND *)this + 800), a3, v7, (LPARAM)v5);
            CShellBrowser2::_RecalcZoomButtonWidth(this);
          }
          goto LABEL_210;
      }
      if ( a3 != 1425 )
      {
        if ( a3 == 32869 )
        {
          v34 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 48);
          ppvOut = 0;
          if ( (**v34)(v34, &GUID_401062ac_2f9c_426e_91a2_4af5bead509f, &ppvOut) >= 0 )
          {
            (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 64LL))(ppvOut, (unsigned int)v7);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
          if ( *((_QWORD *)this + 50)
            && (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ENABLE_WEB_CONTROL_VISUALS) )
          {
            v35 = *((_QWORD *)this + 50);
            memset(&CompForm, 0, 24);
            LOWORD(CompForm.dwStyle) = 3;
            CompForm.ptCurrentPos.y = -1;
            (*(void (__fastcall **)(__int64, const GUID *, __int64, _QWORD, tagCOMPOSITIONFORM *, _QWORD))(*(_QWORD *)v35 + 32LL))(
              v35,
              &CGID_ShellDocView,
              17,
              0,
              &CompForm,
              0);
          }
          return 0;
        }
        goto LABEL_204;
      }
      *((_DWORD *)this + 1624) &= ~0x1000u;
      CBaseBrowser2::UpdateBackForwardState((CShellBrowser2 *)((char *)this + 8));
      return 0;
    }
    if ( a3 != 530 )
    {
      switch ( a3 )
      {
        case 0x11Fu:
          ShouldForwardMenu = CShellBrowser2::_ShouldForwardMenu(this, 0x11Fu, v7, (__int64)v5);
          v30 = this;
          if ( ShouldForwardMenu )
          {
            v29 = 287;
            goto LABEL_57;
          }
          v33 = (v7 >> 16) & 0x10;
          if ( (CShellBrowser2::_OnMenuSelect(this, v7, v5, v32) || !(_DWORD)v33 && (unsigned __int16)v7 > 0x7FFFu)
            && ((*((_BYTE *)this + 6496) & 0x20) == 0 || !(_DWORD)v33) )
          {
            return 0;
          }
          v29 = 287;
LABEL_56:
          v30 = this;
LABEL_57:
          CShellBrowser2::_ForwardViewMsg(v30, v29, v7, (__int64)v5);
          return 0;
        case 0x120u:
          return CShellBrowser2::_ForwardViewMsg(this, 0x120u, v7, (__int64)v5);
        case 0x125u:
          CShellBrowser2::_OnUninitMenuPopup(this, (HMENU)v7);
          return 0;
        case 0x20Au:
        case 0x20Eu:
          return 0;
      }
      if ( a3 != 529 )
        goto LABEL_204;
    }
LABEL_50:
    v29 = a3;
    goto LABEL_56;
  }
  if ( a3 == 279 )
  {
    CShellBrowser2::v_OnInitMenuPopup(this, (HMENU)v7, v10, v11);
    v29 = 279;
    goto LABEL_56;
  }
  if ( a3 <= 0x1A )
  {
    if ( a3 == 26 )
    {
      CShellBrowser2::_OnWmSettingChange(this, v7, (LPARAM)v5);
      goto LABEL_210;
    }
    if ( a3 != 1 )
    {
      switch ( a3 )
      {
        case 3u:
          v25 = *((_QWORD *)this + 859);
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 96LL))(v25);
          goto LABEL_210;
        case 5u:
          v23 = v7 == 1;
          if ( ((*((_DWORD *)this + 1624) >> 10) & 1) != v23 )
          {
            v24 = (v23 << 10) | *((_DWORD *)this + 1624) & 0xFFFFFBFF;
            *((_DWORD *)this + 1624) = v24;
            memset(&CompForm, 0, 24);
            LOWORD(CompForm.dwStyle) = 3;
            CompForm.ptCurrentPos.y = v7 != 1;
            CBaseBrowser2::_PauseOrResumeView(this, (v24 >> 10) & 1);
          }
          goto LABEL_210;
        case 7u:
LABEL_210:
          v39 = a3;
          v40 = a2;
          return CBaseBrowser2::v_WndProc(this, v40, v39, v7, (__int64)v5);
      }
      if ( a3 != 16 )
      {
        if ( a3 != 17 )
        {
          if ( a3 )
            goto LABEL_204;
          goto LABEL_210;
        }
        return 1;
      }
      if ( !(unsigned int)CShellBrowser2::OnClose(this, 1, 1) )
      {
        v15 = *((_DWORD *)this + 1624);
        if ( (v15 & 0x40000) != 0 )
        {
          v16 = *((_DWORD *)this + 1587);
          *((_DWORD *)this + 1624) = v15 & 0xFFFBFFFF;
          v17 = 3105;
LABEL_177:
          LCIEPostMessageWithoutBuffer(v16, *((_DWORD *)this + 1586), v17, 0);
          return 0;
        }
        punk = 0;
        if ( (int)CShellBrowser2::_GetBrowserFrameState(this, (struct IBrowserFrameState **)&punk) >= 0 )
        {
          v18 = punk;
          QueryInterface = punk->lpVtbl[4].QueryInterface;
          v20 = GetCurrentThreadId();
          ((void (__fastcall *)(IUnknown *, _QWORD, __int64))QueryInterface)(v18, v20, 1);
          lpVtbl = v18->lpVtbl;
          v22 = v18;
LABEL_23:
          ((void (__fastcall *)(IUnknown *))lpVtbl->Release)(v22);
        }
      }
      return 0;
    }
    result = CBaseBrowser2::v_WndProc(this, a2, 1u, v7, (__int64)v5);
    v64 = result;
    if ( !result )
      return result;
    CShellBrowser2::OnClose(this, 0, 1);
    CShellBrowser2::_GetMenuBand(this, 1);
    return v64;
  }
  if ( a3 != 33 )
  {
    if ( a3 != 43 && a3 != 44 )
    {
      if ( a3 != 61 )
      {
        if ( a3 == 70 )
        {
          if ( *((_BYTE *)this + 6930) )
            *((_DWORD *)v5 + 8) = (_DWORD)v5[8] & 0xFFFFFD78 | 0x207;
          return 0;
        }
        if ( a3 != 275 )
          goto LABEL_204;
        if ( v7 == 100 )
        {
          KillTimer(*((HWND *)this + 43), 0x64u);
          v27 = (const struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)this + 819);
          if ( v27 )
          {
            if ( *((_QWORD *)this + 799) )
              CShellBrowser2::_DisplayFavoriteStatus(this, v27);
            Pidl_Set((char *)this + 6552, 0);
          }
          return 0;
        }
        goto LABEL_210;
      }
      if ( (_DWORD)v5 != -3 )
        return 0;
      CShellBrowser2::_PrepareInternetToolbar(this);
      ppvOut = 0;
      MenuBand = (IUnknown *)CShellBrowser2::_GetMenuBand(this, 0);
      if ( !MenuBand
        || IUnknown_QueryService(
             MenuBand,
             (const GUID *const)&SID_SMenuBandChild,
             &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
             &ppvOut) < 0 )
      {
        return 0;
      }
      v64 = LresultFromObject(&IID_IAccessible, v7, (LPUNKNOWN)ppvOut);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      return v64;
    }
    CShellBrowser2::_ShouldForwardMenu(this, a3, v7, (__int64)v5);
    goto LABEL_50;
  }
  if ( !IsDualEngineProcess() )
    goto LABEL_210;
  if ( (_DWORD)v5 != 33619970 )
    return 1;
  return v14;
}

```

## disassembly

```asm
0x1801ee2b0  push    rbp
0x1801ee2b2  push    rbx
0x1801ee2b3  push    rsi
0x1801ee2b4  push    rdi
0x1801ee2b5  push    r12
0x1801ee2b7  push    r13
0x1801ee2b9  push    r14
0x1801ee2bb  push    r15
0x1801ee2bd  lea     rbp, [rsp-17h]
0x1801ee2c2  sub     rsp, 0B8h
0x1801ee2c9  mov     rax, cs:__security_cookie
0x1801ee2d0  xor     rax, rsp
0x1801ee2d3  mov     [rbp+4Fh+var_50], rax
0x1801ee2d7  mov     rsi, [rbp+4Fh+lParam]
0x1801ee2db  mov     rbx, rcx
0x1801ee2de  add     rcx, 1AD4h
0x1801ee2e5  mov     [rbp+4Fh+ppvOut], rsi
0x1801ee2e9  mov     rdi, r9
0x1801ee2ec  mov     [rbp+4Fh+punk], r9
0x1801ee2f0  mov     r15d, r8d
0x1801ee2f3  mov     r13, rdx
0x1801ee2f6  call    ?Validate@?$CSignature@$0FLFA@@IEObjectSignature@@QEBAXXZ; IEObjectSignature::CSignature<23376>::Validate(void)
0x1801ee2fb  mov     rcx, [rbx+1970h]; this
0x1801ee302  xor     r14d, r14d
0x1801ee305  mov     [rbp+4Fh+var_98], r14
0x1801ee309  test    rcx, rcx
0x1801ee30c  jz      short loc_1801EE340
0x1801ee30e  mov     rdx, [rcx+8]; HWND
0x1801ee312  lea     rax, [rbp+4Fh+var_98]
0x1801ee316  mov     qword ptr [rsp+0F0h+cy], rax; __int64 *
0x1801ee31b  lea     r9, [rbp+4Fh+punk]; unsigned __int64 *
0x1801ee31f  lea     rax, [rbp+4Fh+ppvOut]
0x1801ee323  mov     r8d, r15d; unsigned int
0x1801ee326  mov     [rsp+0F0h+var_D0], rax; __int64 *
0x1801ee32b  call    ?_TranslateMenuMessage@CInternetToolbarHost@@AEAAHPEAUHWND__@@IPEA_KPEA_J2@Z; CInternetToolbarHost::_TranslateMenuMessage(HWND__ *,uint,unsigned __int64 *,__int64 *,__int64 *)
0x1801ee330  test    eax, eax
0x1801ee332  jnz     loc_1801EE640
0x1801ee338  mov     rdi, [rbp+4Fh+punk]
0x1801ee33c  mov     rsi, [rbp+4Fh+ppvOut]
0x1801ee340  mov     ecx, 2
0x1801ee345  mov     eax, 8066h
0x1801ee34a  lea     r12d, [rcx+1]
0x1801ee34e  cmp     r15d, eax
0x1801ee351  ja      loc_1801EE9C2
0x1801ee357  jz      loc_1801EE98B
0x1801ee35d  mov     eax, 117h
0x1801ee362  cmp     r15d, eax
0x1801ee365  ja      loc_1801EE6B6
0x1801ee36b  jz      loc_1801EE693
0x1801ee371  cmp     r15d, 1Ah
0x1801ee375  ja      loc_1801EE52D
0x1801ee37b  jz      loc_1801EE51A
0x1801ee381  mov     eax, r15d
0x1801ee384  sub     eax, 1
0x1801ee387  jz      loc_1801EE4D4
0x1801ee38d  sub     eax, ecx
0x1801ee38f  jz      loc_1801EE4B3
0x1801ee395  sub     eax, ecx
0x1801ee397  jz      loc_1801EE450
0x1801ee39d  sub     eax, ecx
0x1801ee39f  jz      loc_1801EEFE3
0x1801ee3a5  sub     eax, 9
0x1801ee3a8  jz      short loc_1801EE3C1
0x1801ee3aa  cmp     eax, 1
0x1801ee3ad  jz      loc_1801EEA3E
0x1801ee3b3  test    r15d, r15d
0x1801ee3b6  jz      loc_1801EEFE3
0x1801ee3bc  jmp     loc_1801EEF77
0x1801ee3c1  mov     r14d, 1
0x1801ee3c7  mov     rcx, rbx; this
0x1801ee3ca  mov     r8b, r14b; bool
0x1801ee3cd  mov     edx, r14d; int
0x1801ee3d0  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x1801ee3d5  test    eax, eax
0x1801ee3d7  jnz     loc_1801EF0BD
0x1801ee3dd  mov     eax, [rbx+1960h]
0x1801ee3e3  bt      eax, 12h
0x1801ee3e7  jnb     short loc_1801EE404
0x1801ee3e9  mov     ecx, [rbx+18CCh]
0x1801ee3ef  btr     eax, 12h
0x1801ee3f3  mov     [rbx+1960h], eax
0x1801ee3f9  mov     r8d, 0C21h
0x1801ee3ff  jmp     loc_1801EED98
0x1801ee404  lea     rdx, [rbp+4Fh+punk]; struct IBrowserFrameState **
0x1801ee408  mov     [rbp+4Fh+punk], 0
0x1801ee410  mov     rcx, rbx; this
0x1801ee413  call    ?_GetBrowserFrameState@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrameState@@@Z; CShellBrowser2::_GetBrowserFrameState(IBrowserFrameState * *)
0x1801ee418  test    eax, eax
0x1801ee41a  js      loc_1801EF0BD
0x1801ee420  mov     rdi, [rbp+4Fh+punk]
0x1801ee424  mov     rax, [rdi]
0x1801ee427  mov     rbx, [rax+60h]
0x1801ee42b  call    cs:__imp_GetCurrentThreadId
0x1801ee431  mov     r8d, r14d
0x1801ee434  mov     rcx, rdi
0x1801ee437  mov     edx, eax
0x1801ee439  mov     rax, rbx
0x1801ee43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee441  mov     rax, [rdi]
0x1801ee444  mov     rcx, rdi
0x1801ee447  mov     rax, [rax+10h]
0x1801ee44b  jmp     loc_1801EF0B8
0x1801ee450  mov     edx, [rbx+1960h]
0x1801ee456  mov     ecx, r14d
0x1801ee459  mov     r14d, 1
0x1801ee45f  mov     eax, edx
0x1801ee461  cmp     rdi, r14
0x1801ee464  setz    cl
0x1801ee467  shr     eax, 0Ah
0x1801ee46a  and     eax, r14d
0x1801ee46d  cmp     eax, ecx
0x1801ee46f  jz      loc_1801EEFE3
0x1801ee475  btr     edx, 0Ah
0x1801ee479  mov     eax, ecx
0x1801ee47b  shl     eax, 0Ah
0x1801ee47e  xorps   xmm0, xmm0
0x1801ee481  or      edx, eax
0x1801ee483  xor     eax, eax
0x1801ee485  test    ecx, ecx
0x1801ee487  mov     [rbx+1960h], edx
0x1801ee48d  movups  xmmword ptr [rbp+4Fh+CompForm.dwStyle], xmm0
0x1801ee491  mov     qword ptr [rbp+4Fh+CompForm.rcArea.top], rax
0x1801ee495  mov     rcx, rbx; this
0x1801ee498  setz    al
0x1801ee49b  mov     word ptr [rbp+4Fh+CompForm.dwStyle], r12w
0x1801ee4a0  shr     edx, 0Ah
0x1801ee4a3  and     edx, r14d; int
0x1801ee4a6  mov     [rbp+4Fh+CompForm.ptCurrentPos.y], eax
0x1801ee4a9  call    ?_PauseOrResumeView@CBaseBrowser2@@IEAAJH@Z; CBaseBrowser2::_PauseOrResumeView(int)
0x1801ee4ae  jmp     loc_1801EEFE3
0x1801ee4b3  mov     rcx, [rbx+1AD8h]
0x1801ee4ba  test    rcx, rcx
0x1801ee4bd  jz      loc_1801EEFE3
0x1801ee4c3  mov     rax, [rcx]
0x1801ee4c6  mov     rax, [rax+60h]
0x1801ee4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee4cf  jmp     loc_1801EEFE3
0x1801ee4d4  mov     r14d, 1
0x1801ee4da  mov     [rsp+0F0h+var_D0], rsi; __int64
0x1801ee4df  mov     r8d, r14d; unsigned int
0x1801ee4e2  mov     r9, rdi; unsigned __int64
0x1801ee4e5  mov     rdx, r13; HWND
0x1801ee4e8  mov     rcx, rbx; this
0x1801ee4eb  call    ?v_WndProc@CBaseBrowser2@@MEAA_JPEAUHWND__@@I_K_J@Z; CBaseBrowser2::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801ee4f0  mov     [rbp+4Fh+var_98], rax
0x1801ee4f4  test    rax, rax
0x1801ee4f7  jz      loc_1801EF0BF
0x1801ee4fd  mov     r8b, r14b; bool
0x1801ee500  xor     edx, edx; int
0x1801ee502  mov     rcx, rbx; this
0x1801ee505  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x1801ee50a  mov     edx, r14d; int
0x1801ee50d  mov     rcx, rbx; this
0x1801ee510  call    ?_GetMenuBand@CShellBrowser2@@AEAAPEAUIMenuBand@@H@Z; CShellBrowser2::_GetMenuBand(int)
0x1801ee515  jmp     loc_1801EE640
0x1801ee51a  mov     r8, rsi; lParam
0x1801ee51d  mov     rdx, rdi; wParam
0x1801ee520  mov     rcx, rbx; this
0x1801ee523  call    ?_OnWmSettingChange@CShellBrowser2@@AEAAX_K_J@Z; CShellBrowser2::_OnWmSettingChange(unsigned __int64,__int64)
0x1801ee528  jmp     loc_1801EEFE3
0x1801ee52d  mov     eax, r15d
0x1801ee530  sub     eax, 21h ; '!'
0x1801ee533  jz      loc_1801EE65F
0x1801ee539  sub     eax, 0Ah
0x1801ee53c  jz      loc_1801EE649
0x1801ee542  sub     eax, 1
0x1801ee545  jz      loc_1801EE649
0x1801ee54b  sub     eax, 11h
0x1801ee54e  jz      short loc_1801EE5CD
0x1801ee550  sub     eax, 9
0x1801ee553  jz      short loc_1801EE5AC
0x1801ee555  cmp     eax, 0CDh
0x1801ee55a  jnz     loc_1801EEF77
0x1801ee560  lea     edx, [rax-69h]; uIDEvent
0x1801ee563  cmp     rdi, rdx
0x1801ee566  jnz     loc_1801EEFE3
0x1801ee56c  mov     rcx, [rbx+158h]; hWnd
0x1801ee573  call    cs:__imp_KillTimer
0x1801ee579  lea     rdi, [rbx+1998h]
0x1801ee580  mov     rdx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x1801ee583  test    rdx, rdx
0x1801ee586  jz      loc_1801EF0BD
0x1801ee58c  cmp     [rbx+18F8h], r14
0x1801ee593  jz      short loc_1801EE59D
0x1801ee595  mov     rcx, rbx; this
0x1801ee598  call    ?_DisplayFavoriteStatus@CShellBrowser2@@AEAAXPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CShellBrowser2::_DisplayFavoriteStatus(_ITEMIDLIST_ABSOLUTE const *)
0x1801ee59d  xor     edx, edx
0x1801ee59f  mov     rcx, rdi
0x1801ee5a2  call    Pidl_Set
0x1801ee5a7  jmp     loc_1801EF0BD
0x1801ee5ac  cmp     [rbx+1B12h], r14b
0x1801ee5b3  jz      loc_1801EF0BD
0x1801ee5b9  mov     eax, [rsi+20h]
0x1801ee5bc  btr     eax, 7
0x1801ee5c0  or      eax, 207h
0x1801ee5c5  mov     [rsi+20h], eax
0x1801ee5c8  jmp     loc_1801EF0BD
0x1801ee5cd  cmp     esi, 0FFFFFFFDh
0x1801ee5d0  jnz     loc_1801EF0BD
0x1801ee5d6  mov     rcx, rbx; this
0x1801ee5d9  call    ?_PrepareInternetToolbar@CShellBrowser2@@AEAAJXZ; CShellBrowser2::_PrepareInternetToolbar(void)
0x1801ee5de  xor     edx, edx; int
0x1801ee5e0  mov     [rbp+4Fh+ppvOut], r14
0x1801ee5e4  mov     rcx, rbx; this
0x1801ee5e7  call    ?_GetMenuBand@CShellBrowser2@@AEAAPEAUIMenuBand@@H@Z; CShellBrowser2::_GetMenuBand(int)
0x1801ee5ec  test    rax, rax
0x1801ee5ef  jz      loc_1801EF0BD
0x1801ee5f5  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x1801ee5f9  mov     rcx, rax; punk
0x1801ee5fc  lea     r8, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71; riid
0x1801ee603  lea     rdx, SID_SMenuBandChild; guidService
0x1801ee60a  call    cs:__imp_IUnknown_QueryService
0x1801ee610  test    eax, eax
0x1801ee612  js      loc_1801EF0BD
0x1801ee618  mov     r8, [rbp+4Fh+ppvOut]; punk
0x1801ee61c  lea     rcx, IID_IAccessible; riid
0x1801ee623  mov     rdx, rdi; wParam
0x1801ee626  call    cs:__imp_LresultFromObject
0x1801ee62c  mov     rcx, [rbp+4Fh+ppvOut]
0x1801ee630  mov     [rbp+4Fh+var_98], rax
0x1801ee634  mov     rax, [rcx]
0x1801ee637  mov     rax, [rax+10h]
0x1801ee63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee640  mov     rax, [rbp+4Fh+var_98]
0x1801ee644  jmp     loc_1801EF0BF
0x1801ee649  mov     r9, rsi; __int64
0x1801ee64c  mov     r8, rdi; unsigned __int64
0x1801ee64f  mov     edx, r15d; unsigned int
0x1801ee652  mov     rcx, rbx; this
0x1801ee655  call    ?_ShouldForwardMenu@CShellBrowser2@@AEAAHI_K_J@Z; CShellBrowser2::_ShouldForwardMenu(uint,unsigned __int64,__int64)
0x1801ee65a  mov     edx, r15d
0x1801ee65d  jmp     short loc_1801EE6A3
0x1801ee65f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801ee665  test    al, al
0x1801ee667  jz      loc_1801EEFE3
0x1801ee66d  mov     ecx, 2
0x1801ee672  cmp     si, cx
0x1801ee675  jnz     short loc_1801EE685
0x1801ee677  shr     rsi, 10h
0x1801ee67b  mov     eax, 201h
0x1801ee680  cmp     si, ax
0x1801ee683  jz      short loc_1801EE68B
0x1801ee685  mov     r12d, 1
0x1801ee68b  mov     rax, r12
0x1801ee68e  jmp     loc_1801EF0BF
0x1801ee693  mov     rdx, rdi; HMENU
0x1801ee696  mov     rcx, rbx; this
0x1801ee699  call    ?v_OnInitMenuPopup@CShellBrowser2@@AEAA_JPEAUHMENU__@@HH@Z; CShellBrowser2::v_OnInitMenuPopup(HMENU__ *,int,int)
0x1801ee69e  mov     edx, 117h; unsigned int
0x1801ee6a3  mov     rcx, rbx; this
0x1801ee6a6  mov     r9, rsi; __int64
0x1801ee6a9  mov     r8, rdi; unsigned __int64
0x1801ee6ac  call    ?_ForwardViewMsg@CShellBrowser2@@AEAA_JI_K_J@Z; CShellBrowser2::_ForwardViewMsg(uint,unsigned __int64,__int64)
0x1801ee6b1  jmp     loc_1801EF0BD
0x1801ee6b6  mov     eax, 212h
0x1801ee6bb  cmp     r15d, eax
0x1801ee6be  ja      loc_1801EE791
0x1801ee6c4  jz      short loc_1801EE65A
0x1801ee6c6  mov     eax, r15d
0x1801ee6c9  mov     ecx, 11Fh
0x1801ee6ce  sub     eax, ecx
0x1801ee6d0  jz      short loc_1801EE726
0x1801ee6d2  sub     eax, 1
0x1801ee6d5  jz      short loc_1801EE70E
0x1801ee6d7  sub     eax, 5
0x1801ee6da  jz      short loc_1801EE6FE
0x1801ee6dc  sub     eax, 0E5h
0x1801ee6e1  jz      loc_1801EF0BD
0x1801ee6e7  sub     eax, 4
0x1801ee6ea  jz      loc_1801EF0BD
0x1801ee6f0  cmp     eax, r12d
0x1801ee6f3  jz      loc_1801EE65A
0x1801ee6f9  jmp     loc_1801EEF77
0x1801ee6fe  mov     rdx, rdi; HMENU
0x1801ee701  mov     rcx, rbx; this
0x1801ee704  call    ?_OnUninitMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnUninitMenuPopup(HMENU__ *)
0x1801ee709  jmp     loc_1801EF0BD
0x1801ee70e  mov     r9, rsi; __int64
0x1801ee711  mov     r8, rdi; unsigned __int64
0x1801ee714  mov     edx, 120h; unsigned int
0x1801ee719  mov     rcx, rbx; this
0x1801ee71c  call    ?_ForwardViewMsg@CShellBrowser2@@AEAA_JI_K_J@Z; CShellBrowser2::_ForwardViewMsg(uint,unsigned __int64,__int64)
0x1801ee721  jmp     loc_1801EF0BF
0x1801ee726  mov     edx, ecx; unsigned int
0x1801ee728  mov     r9, rsi; __int64
0x1801ee72b  mov     rcx, rbx; this
0x1801ee72e  mov     r8, rdi; unsigned __int64
0x1801ee731  call    ?_ShouldForwardMenu@CShellBrowser2@@AEAAHI_K_J@Z; CShellBrowser2::_ShouldForwardMenu(uint,unsigned __int64,__int64)
0x1801ee736  mov     rcx, rbx; this
0x1801ee739  test    eax, eax
0x1801ee73b  jz      short loc_1801EE747
0x1801ee73d  mov     edx, 11Fh
0x1801ee742  jmp     loc_1801EE6A6
0x1801ee747  mov     r14, rdi
0x1801ee74a  mov     r8, rsi; HMENU
0x1801ee74d  shr     r14, 10h
0x1801ee751  mov     rdx, rdi; wParam
0x1801ee754  and     r14d, 10h
0x1801ee758  call    ?_OnMenuSelect@CShellBrowser2@@AEAA_J_K_JI@Z; CShellBrowser2::_OnMenuSelect(unsigned __int64,__int64,uint)
0x1801ee75d  test    rax, rax
  ... truncated ...
```
