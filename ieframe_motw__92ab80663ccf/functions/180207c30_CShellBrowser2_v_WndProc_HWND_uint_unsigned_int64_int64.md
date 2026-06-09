# CShellBrowser2::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180207c30`
- end: `0x180208b28`
- name: `?v_WndProc@CShellBrowser2@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3832`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, HWND, unsigned int, HMENU, LPARAM lParam)`
- caller_count: `0`
- callee_count: `41`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180005030`
- `0x180048190`
- `0x1800692fc`
- `0x18007587c`
- `0x180076ed8`
- `0x180079e24`
- `0x180080558`
- `0x1800d3cd0`
- `0x1801408dc`
- `0x1801b85f0`
- `0x1801bbff0`
- `0x1801e7ad8`
- `0x1801f2b6c`
- `0x1801f749c`
- `0x1801f8350`
- `0x1801fad50`
- `0x1801fb1a0`
- `0x1801fbf18`
- `0x1801fcafc`
- `0x1801fd3a4`
- `0x1801fd6a8`
- `0x180200f6c`
- `0x1802018f4`
- `0x180202130`
- `0x180202208`
- `0x180202a28`
- `0x180202d98`
- `0x180202f34`
- `0x180203380`
- `0x180204920`
- `0x180205ef0`
- `0x1802073b0`
- `0x180207c30`
- `0x1802bd21c`
- `0x1802be374`
- `0x1802c7b2c`
- `0x1803f5428`
- `0x18047ce98`
- `0x18057b568`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18020884b`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18020884b`
- `KERNEL32!TlsGetValue` at `0x180208a93`
- `KERNEL32!TlsGetValue` at `0x180208a93`
- `KERNEL32!GetCurrentThreadId` at `0x180207dab`
- `KERNEL32!GetCurrentThreadId` at `0x18020828c`
- `KERNEL32!GetCurrentThreadId` at `0x180207dab`
- `KERNEL32!GetCurrentThreadId` at `0x18020828c`
- `USER32!GetWindowRect` at `0x18020886f`
- `USER32!GetWindowRect` at `0x18020886f`
- `USER32!SetWindowPos` at `0x180208735`
- `USER32!SetWindowPos` at `0x180208735`
- `USER32!InvalidateRect` at `0x18020850a`
- `USER32!InvalidateRect` at `0x18020850a`
- `USER32!KillTimer` at `0x180207efd`
- `USER32!KillTimer` at `0x180207efd`
- `USER32!RedrawWindow` at `0x18020863b`
- `USER32!RedrawWindow` at `0x18020863b`
- `USER32!SendMessageW` at `0x18020832c`
- `USER32!SendMessageW` at `0x180208549`
- `USER32!SendMessageW` at `0x1802088b3`
- `USER32!SendMessageW` at `0x1802089ba`
- `USER32!SendMessageW` at `0x18020832c`
- `USER32!SendMessageW` at `0x180208549`
- `USER32!SendMessageW` at `0x1802088b3`
- `USER32!SendMessageW` at `0x1802089ba`
- `USER32!GetWindowThreadProcessId` at `0x1802082be`
- `USER32!GetWindowThreadProcessId` at `0x1802082be`
- `USER32!FindWindowExW` at `0x1802082aa`
- `USER32!FindWindowExW` at `0x1802082aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18020868d`
- `OLEAUT32!__imp_SysFreeString` at `0x18020868d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180207ffb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180208571`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180208945`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180207ffb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180208571`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180208945`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180207f9a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180207f9a`
- `OLEACC!LresultFromObject` at `0x180207fbc`
- `OLEACC!LresultFromObject` at `0x180207fbc`
- `IMM32!ImmReleaseContext` at `0x1802084b4`
- `IMM32!ImmReleaseContext` at `0x1802084b4`
- `IMM32!ImmSetCandidateWindow` at `0x180208496`
- `IMM32!ImmSetCandidateWindow` at `0x180208496`
- `IMM32!ImmSetCompositionWindow` at `0x180208450`
- `IMM32!ImmSetCompositionWindow` at `0x180208450`
- `IMM32!ImmGetCompositionWindow` at `0x180208433`
- `IMM32!ImmGetCompositionWindow` at `0x180208433`
- `IMM32!ImmGetContext` at `0x180208409`
- `IMM32!ImmGetContext` at `0x180208409`
- `IMM32!ImmGetCandidateWindow` at `0x180208479`
- `IMM32!ImmGetCandidateWindow` at `0x180208479`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1802087a9`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1802087a9`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1802086a5`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1802086a5`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1802089fa`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180208a0e`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1802089fa`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180208a0e`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x180208a6b`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x180208a6b`

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
            if ( LODWORD(qword_180623710[j]) == (WORD1(v5) & 0xFFF) )
              return CShellBrowser2::v_OnCommand(this, WORD2(qword_180623710[j]) | (WORD1(v7) << 16), (__int64)v5);
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
0x180207c30  push    rbp
0x180207c32  push    rbx
0x180207c33  push    rsi
0x180207c34  push    rdi
0x180207c35  push    r12
0x180207c37  push    r13
0x180207c39  push    r14
0x180207c3b  push    r15
0x180207c3d  lea     rbp, [rsp-17h]
0x180207c42  sub     rsp, 0B8h
0x180207c49  mov     rax, cs:__security_cookie
0x180207c50  xor     rax, rsp
0x180207c53  mov     [rbp+4Fh+var_50], rax
0x180207c57  mov     rsi, [rbp+4Fh+lParam]
0x180207c5b  mov     rbx, rcx
0x180207c5e  add     rcx, 1AD4h
0x180207c65  mov     [rbp+4Fh+ppvOut], rsi
0x180207c69  mov     rdi, r9
0x180207c6c  mov     [rbp+4Fh+punk], r9
0x180207c70  mov     r15d, r8d
0x180207c73  mov     r13, rdx
0x180207c76  call    ?Validate@?$CSignature@$0FLFA@@IEObjectSignature@@QEBAXXZ; IEObjectSignature::CSignature<23376>::Validate(void)
0x180207c7b  mov     rcx, [rbx+1970h]; this
0x180207c82  xor     r14d, r14d
0x180207c85  mov     [rbp+4Fh+var_98], r14
0x180207c89  test    rcx, rcx
0x180207c8c  jz      short loc_180207CC0
0x180207c8e  mov     rdx, [rcx+8]; HWND
0x180207c92  lea     rax, [rbp+4Fh+var_98]
0x180207c96  mov     qword ptr [rsp+0F0h+cy], rax; __int64 *
0x180207c9b  lea     r9, [rbp+4Fh+punk]; unsigned __int64 *
0x180207c9f  lea     rax, [rbp+4Fh+ppvOut]
0x180207ca3  mov     r8d, r15d; unsigned int
0x180207ca6  mov     [rsp+0F0h+var_D0], rax; __int64 *
0x180207cab  call    ?_TranslateMenuMessage@CInternetToolbarHost@@AEAAHPEAUHWND__@@IPEA_KPEA_J2@Z; CInternetToolbarHost::_TranslateMenuMessage(HWND__ *,uint,unsigned __int64 *,__int64 *,__int64 *)
0x180207cb0  test    eax, eax
0x180207cb2  jnz     loc_180207FDC
0x180207cb8  mov     rdi, [rbp+4Fh+punk]
0x180207cbc  mov     rsi, [rbp+4Fh+ppvOut]
0x180207cc0  mov     ecx, 2
0x180207cc5  mov     eax, 8066h
0x180207cca  lea     r12d, [rcx+1]
0x180207cce  cmp     r15d, eax
0x180207cd1  ja      loc_18020837C
0x180207cd7  jz      loc_180208345
0x180207cdd  mov     eax, 117h
0x180207ce2  cmp     r15d, eax
0x180207ce5  ja      loc_180208058
0x180207ceb  jz      loc_180208035
0x180207cf1  cmp     r15d, 1Ah
0x180207cf5  ja      loc_180207EB3
0x180207cfb  jz      loc_180207EA0
0x180207d01  mov     eax, r15d
0x180207d04  sub     eax, 1
0x180207d07  jz      loc_180207E5A
0x180207d0d  sub     eax, ecx
0x180207d0f  jz      loc_180207E39
0x180207d15  sub     eax, ecx
0x180207d17  jz      loc_180207DD6
0x180207d1d  sub     eax, ecx
0x180207d1f  jz      loc_180208A1F
0x180207d25  sub     eax, 9
0x180207d28  jz      short loc_180207D41
0x180207d2a  cmp     eax, 1
0x180207d2d  jz      loc_1802083F8
0x180207d33  test    r15d, r15d
0x180207d36  jz      loc_180208A1F
0x180207d3c  jmp     loc_1802089A1
0x180207d41  mov     r14d, 1
0x180207d47  mov     rcx, rbx; this
0x180207d4a  mov     r8b, r14b; bool
0x180207d4d  mov     edx, r14d; int
0x180207d50  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x180207d55  test    eax, eax
0x180207d57  jnz     loc_180208B05
0x180207d5d  mov     eax, [rbx+1960h]
0x180207d63  bt      eax, 12h
0x180207d67  jnb     short loc_180207D84
0x180207d69  mov     ecx, [rbx+18CCh]
0x180207d6f  btr     eax, 12h
0x180207d73  mov     [rbx+1960h], eax
0x180207d79  mov     r8d, 0C21h
0x180207d7f  jmp     loc_1802087A0
0x180207d84  lea     rdx, [rbp+4Fh+punk]; struct IBrowserFrameState **
0x180207d88  mov     [rbp+4Fh+punk], 0
0x180207d90  mov     rcx, rbx; this
0x180207d93  call    ?_GetBrowserFrameState@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrameState@@@Z; CShellBrowser2::_GetBrowserFrameState(IBrowserFrameState * *)
0x180207d98  test    eax, eax
0x180207d9a  js      loc_180208B05
0x180207da0  mov     rdi, [rbp+4Fh+punk]
0x180207da4  mov     rax, [rdi]
0x180207da7  mov     rbx, [rax+60h]
0x180207dab  call    cs:__imp_GetCurrentThreadId
0x180207db2  nop     dword ptr [rax+rax+00h]
0x180207db7  mov     r8d, r14d
0x180207dba  mov     rcx, rdi
0x180207dbd  mov     edx, eax
0x180207dbf  mov     rax, rbx
0x180207dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207dc7  mov     rax, [rdi]
0x180207dca  mov     rcx, rdi
0x180207dcd  mov     rax, [rax+10h]
0x180207dd1  jmp     loc_180208B00
0x180207dd6  mov     edx, [rbx+1960h]
0x180207ddc  mov     ecx, r14d
0x180207ddf  mov     r14d, 1
0x180207de5  mov     eax, edx
0x180207de7  cmp     rdi, r14
0x180207dea  setz    cl
0x180207ded  shr     eax, 0Ah
0x180207df0  and     eax, r14d
0x180207df3  cmp     eax, ecx
0x180207df5  jz      loc_180208A1F
0x180207dfb  btr     edx, 0Ah
0x180207dff  mov     eax, ecx
0x180207e01  shl     eax, 0Ah
0x180207e04  xorps   xmm0, xmm0
0x180207e07  or      edx, eax
0x180207e09  xor     eax, eax
0x180207e0b  test    ecx, ecx
0x180207e0d  mov     [rbx+1960h], edx
0x180207e13  movups  xmmword ptr [rbp+4Fh+CompForm.dwStyle], xmm0
0x180207e17  mov     qword ptr [rbp+4Fh+CompForm.rcArea.top], rax
0x180207e1b  mov     rcx, rbx; this
0x180207e1e  setz    al
0x180207e21  mov     word ptr [rbp+4Fh+CompForm.dwStyle], r12w
0x180207e26  shr     edx, 0Ah
0x180207e29  and     edx, r14d; int
0x180207e2c  mov     [rbp+4Fh+CompForm.ptCurrentPos.y], eax
0x180207e2f  call    ?_PauseOrResumeView@CBaseBrowser2@@IEAAJH@Z; CBaseBrowser2::_PauseOrResumeView(int)
0x180207e34  jmp     loc_180208A1F
0x180207e39  mov     rcx, [rbx+1AD8h]
0x180207e40  test    rcx, rcx
0x180207e43  jz      loc_180208A1F
0x180207e49  mov     rax, [rcx]
0x180207e4c  mov     rax, [rax+60h]
0x180207e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207e55  jmp     loc_180208A1F
0x180207e5a  mov     r14d, 1
0x180207e60  mov     [rsp+0F0h+var_D0], rsi; __int64
0x180207e65  mov     r8d, r14d; unsigned int
0x180207e68  mov     r9, rdi; unsigned __int64
0x180207e6b  mov     rdx, r13; HWND
0x180207e6e  mov     rcx, rbx; this
0x180207e71  call    ?v_WndProc@CBaseBrowser2@@MEAA_JPEAUHWND__@@I_K_J@Z; CBaseBrowser2::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180207e76  mov     [rbp+4Fh+var_98], rax
0x180207e7a  test    rax, rax
0x180207e7d  jz      loc_180208B07
0x180207e83  mov     r8b, r14b; bool
0x180207e86  xor     edx, edx; int
0x180207e88  mov     rcx, rbx; this
0x180207e8b  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x180207e90  mov     edx, r14d; int
0x180207e93  mov     rcx, rbx; this
0x180207e96  call    ?_GetMenuBand@CShellBrowser2@@AEAAPEAUIMenuBand@@H@Z; CShellBrowser2::_GetMenuBand(int)
0x180207e9b  jmp     loc_180207FDC
0x180207ea0  mov     r8, rsi; lParam
0x180207ea3  mov     rdx, rdi; wParam
0x180207ea6  mov     rcx, rbx; this
0x180207ea9  call    ?_OnWmSettingChange@CShellBrowser2@@AEAAX_K_J@Z; CShellBrowser2::_OnWmSettingChange(unsigned __int64,__int64)
0x180207eae  jmp     loc_180208A1F
0x180207eb3  mov     eax, r15d
0x180207eb6  sub     eax, 21h ; '!'
0x180207eb9  jz      loc_180207FFB
0x180207ebf  sub     eax, 0Ah
0x180207ec2  jz      loc_180207FE5
0x180207ec8  sub     eax, 1
0x180207ecb  jz      loc_180207FE5
0x180207ed1  sub     eax, 11h
0x180207ed4  jz      loc_180207F5D
0x180207eda  sub     eax, 9
0x180207edd  jz      short loc_180207F3C
0x180207edf  cmp     eax, 0CDh
0x180207ee4  jnz     loc_1802089A1
0x180207eea  lea     edx, [rax-69h]; uIDEvent
0x180207eed  cmp     rdi, rdx
0x180207ef0  jnz     loc_180208A1F
0x180207ef6  mov     rcx, [rbx+158h]; hWnd
0x180207efd  call    cs:__imp_KillTimer
0x180207f04  nop     dword ptr [rax+rax+00h]
0x180207f09  lea     rdi, [rbx+1998h]
0x180207f10  mov     rdx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x180207f13  test    rdx, rdx
0x180207f16  jz      loc_180208B05
0x180207f1c  cmp     [rbx+18F8h], r14
0x180207f23  jz      short loc_180207F2D
0x180207f25  mov     rcx, rbx; this
0x180207f28  call    ?_DisplayFavoriteStatus@CShellBrowser2@@AEAAXPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CShellBrowser2::_DisplayFavoriteStatus(_ITEMIDLIST_ABSOLUTE const *)
0x180207f2d  xor     edx, edx
0x180207f2f  mov     rcx, rdi
0x180207f32  call    Pidl_Set
0x180207f37  jmp     loc_180208B05
0x180207f3c  cmp     [rbx+1B12h], r14b
0x180207f43  jz      loc_180208B05
0x180207f49  mov     eax, [rsi+20h]
0x180207f4c  btr     eax, 7
0x180207f50  or      eax, 207h
0x180207f55  mov     [rsi+20h], eax
0x180207f58  jmp     loc_180208B05
0x180207f5d  cmp     esi, 0FFFFFFFDh
0x180207f60  jnz     loc_180208B05
0x180207f66  mov     rcx, rbx; this
0x180207f69  call    ?_PrepareInternetToolbar@CShellBrowser2@@AEAAJXZ; CShellBrowser2::_PrepareInternetToolbar(void)
0x180207f6e  xor     edx, edx; int
0x180207f70  mov     [rbp+4Fh+ppvOut], r14
0x180207f74  mov     rcx, rbx; this
0x180207f77  call    ?_GetMenuBand@CShellBrowser2@@AEAAPEAUIMenuBand@@H@Z; CShellBrowser2::_GetMenuBand(int)
0x180207f7c  test    rax, rax
0x180207f7f  jz      loc_180208B05
0x180207f85  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x180207f89  mov     rcx, rax; punk
0x180207f8c  lea     r8, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71; riid
0x180207f93  lea     rdx, SID_SMenuBandChild; guidService
0x180207f9a  call    cs:__imp_IUnknown_QueryService
0x180207fa1  nop     dword ptr [rax+rax+00h]
0x180207fa6  test    eax, eax
0x180207fa8  js      loc_180208B05
0x180207fae  mov     r8, [rbp+4Fh+ppvOut]; punk
0x180207fb2  lea     rcx, IID_IAccessible; riid
0x180207fb9  mov     rdx, rdi; wParam
0x180207fbc  call    cs:__imp_LresultFromObject
0x180207fc3  nop     dword ptr [rax+rax+00h]
0x180207fc8  mov     rcx, [rbp+4Fh+ppvOut]
0x180207fcc  mov     [rbp+4Fh+var_98], rax
0x180207fd0  mov     rax, [rcx]
0x180207fd3  mov     rax, [rax+10h]
0x180207fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207fdc  mov     rax, [rbp+4Fh+var_98]
0x180207fe0  jmp     loc_180208B07
0x180207fe5  mov     r9, rsi; __int64
0x180207fe8  mov     r8, rdi; unsigned __int64
0x180207feb  mov     edx, r15d; unsigned int
0x180207fee  mov     rcx, rbx; this
0x180207ff1  call    ?_ShouldForwardMenu@CShellBrowser2@@AEAAHI_K_J@Z; CShellBrowser2::_ShouldForwardMenu(uint,unsigned __int64,__int64)
0x180207ff6  mov     edx, r15d
0x180207ff9  jmp     short loc_180208045
0x180207ffb  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180208002  nop     dword ptr [rax+rax+00h]
0x180208007  test    al, al
0x180208009  jz      loc_180208A1F
0x18020800f  mov     ecx, 2
0x180208014  cmp     si, cx
0x180208017  jnz     short loc_180208027
0x180208019  shr     rsi, 10h
0x18020801d  mov     eax, 201h
0x180208022  cmp     si, ax
0x180208025  jz      short loc_18020802D
0x180208027  mov     r12d, 1
0x18020802d  mov     rax, r12
0x180208030  jmp     loc_180208B07
0x180208035  mov     rdx, rdi; HMENU
0x180208038  mov     rcx, rbx; this
0x18020803b  call    ?v_OnInitMenuPopup@CShellBrowser2@@AEAA_JPEAUHMENU__@@HH@Z; CShellBrowser2::v_OnInitMenuPopup(HMENU__ *,int,int)
0x180208040  mov     edx, 117h; unsigned int
0x180208045  mov     rcx, rbx; this
0x180208048  mov     r9, rsi; __int64
0x18020804b  mov     r8, rdi; unsigned __int64
0x18020804e  call    ?_ForwardViewMsg@CShellBrowser2@@AEAA_JI_K_J@Z; CShellBrowser2::_ForwardViewMsg(uint,unsigned __int64,__int64)
0x180208053  jmp     loc_180208B05
0x180208058  mov     eax, 212h
0x18020805d  cmp     r15d, eax
0x180208060  ja      loc_180208133
0x180208066  jz      short loc_180207FF6
0x180208068  mov     eax, r15d
0x18020806b  mov     ecx, 11Fh
0x180208070  sub     eax, ecx
0x180208072  jz      short loc_1802080C8
0x180208074  sub     eax, 1
0x180208077  jz      short loc_1802080B0
0x180208079  sub     eax, 5
0x18020807c  jz      short loc_1802080A0
0x18020807e  sub     eax, 0E5h
0x180208083  jz      loc_180208B05
0x180208089  sub     eax, 4
0x18020808c  jz      loc_180208B05
0x180208092  cmp     eax, r12d
0x180208095  jz      loc_180207FF6
0x18020809b  jmp     loc_1802089A1
0x1802080a0  mov     rdx, rdi; HMENU
0x1802080a3  mov     rcx, rbx; this
0x1802080a6  call    ?_OnUninitMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnUninitMenuPopup(HMENU__ *)
0x1802080ab  jmp     loc_180208B05
0x1802080b0  mov     r9, rsi; __int64
0x1802080b3  mov     r8, rdi; unsigned __int64
0x1802080b6  mov     edx, 120h; unsigned int
0x1802080bb  mov     rcx, rbx; this
0x1802080be  call    ?_ForwardViewMsg@CShellBrowser2@@AEAA_JI_K_J@Z; CShellBrowser2::_ForwardViewMsg(uint,unsigned __int64,__int64)
0x1802080c3  jmp     loc_180208B07
0x1802080c8  mov     edx, ecx; unsigned int
0x1802080ca  mov     r9, rsi; __int64
0x1802080cd  mov     rcx, rbx; this
0x1802080d0  mov     r8, rdi; unsigned __int64
0x1802080d3  call    ?_ShouldForwardMenu@CShellBrowser2@@AEAAHI_K_J@Z; CShellBrowser2::_ShouldForwardMenu(uint,unsigned __int64,__int64)
0x1802080d8  mov     rcx, rbx; this
0x1802080db  test    eax, eax
0x1802080dd  jz      short loc_1802080E9
0x1802080df  mov     edx, 11Fh
0x1802080e4  jmp     loc_180208048
0x1802080e9  mov     r14, rdi
0x1802080ec  mov     r8, rsi; HMENU
  ... truncated ...
```
