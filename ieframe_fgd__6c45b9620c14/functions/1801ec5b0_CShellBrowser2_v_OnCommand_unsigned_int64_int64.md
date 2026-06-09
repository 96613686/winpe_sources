# CShellBrowser2::v_OnCommand(unsigned __int64,__int64)

- ea: `0x1801ec5b0`
- end: `0x1801ed921`
- name: `?v_OnCommand@CShellBrowser2@@EEAA_J_K_J@Z`
- size: `4977`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `48`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801e659c`
- `0x1801ee2b0`

## callees

- `0x18000b9e0`
- `0x180011230`
- `0x180015150`
- `0x18004a080`
- `0x18004b560`
- `0x18006f940`
- `0x180075598`
- `0x180091064`
- `0x1800c1b64`
- `0x1800c9f70`
- `0x1801a1b50`
- `0x1801a2270`
- `0x1801a8ab0`
- `0x1801ab514`
- `0x1801ab5a4`
- `0x1801db048`
- `0x1801dce30`
- `0x1801dd51c`
- `0x1801dec94`
- `0x1801e1c84`
- `0x1801e35a0`
- `0x1801e37c8`
- `0x1801e3fcc`
- `0x1801e4548`
- `0x1801e659c`
- `0x1801e697c`
- `0x1801e6aec`
- `0x1801e6c38`
- `0x1801e77e4`
- `0x1801e7c28`
- `0x1801e7cc8`
- `0x1801e9640`
- `0x1801ea504`
- `0x1801ea618`
- `0x1801eb0d4`
- `0x1801eb6b8`
- `0x1801ec5b0`
- `0x1801edec8`
- `0x1803c2618`
- `0x1803eb9d0`
- `0x1803efa90`
- `0x180442e30`
- `0x1804e0cc4`
- `0x180516a5c`
- `0x180524b78`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801ed6c0`
- `KERNEL32!IsDebuggerPresent` at `0x1801ed6c0`
- `KERNEL32!GetLastError` at `0x1801ecc9a`
- `KERNEL32!GetLastError` at `0x1801ecc9a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801ec9b3`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801ed38b`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801ec9b3`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801ed38b`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ecc58`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ecc87`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ecc58`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ecc87`
- `USER32!GetKeyState` at `0x1801ed6a5`
- `USER32!GetKeyState` at `0x1801ed6b5`
- `USER32!GetKeyState` at `0x1801ed6a5`
- `USER32!GetKeyState` at `0x1801ed6b5`
- `USER32!AllowSetForegroundWindow` at `0x1801eccfa`
- `USER32!AllowSetForegroundWindow` at `0x1801ed05e`
- `USER32!AllowSetForegroundWindow` at `0x1801ed184`
- `USER32!AllowSetForegroundWindow` at `0x1801eccfa`
- `USER32!AllowSetForegroundWindow` at `0x1801ed05e`
- `USER32!AllowSetForegroundWindow` at `0x1801ed184`
- `OLEAUT32!__imp_SysFreeString` at `0x1801ecf05`
- `OLEAUT32!__imp_SysFreeString` at `0x1801ed0a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801ecf05`
- `OLEAUT32!__imp_SysFreeString` at `0x1801ed0a6`
- `OLEAUT32!__imp_VariantClear` at `0x1801ecefa`
- `OLEAUT32!__imp_VariantClear` at `0x1801ecefa`
- `SHELL32!__imp_ILFree` at `0x1801eca25`
- `SHELL32!__imp_ILFree` at `0x1801eca25`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801ece0a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801ece0a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ec63e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ed6fc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ec63e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801ed6fc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ec703`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ed8c0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ec703`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801ed8c0`
- `WININET!InternetFortezzaCommand` at `0x1801ec805`
- `WININET!InternetFortezzaCommand` at `0x1801ec805`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801ec910`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801ed08d`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801ec910`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801ed08d`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801ed68b`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801ed68b`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801ec8cb`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801ecfe5`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801ec8cb`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801ecfe5`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801ed09b`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801ed09b`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801ed18a`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801ed674`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801ed18a`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801ed674`

## pseudocode

```c
__int64 __fastcall CShellBrowser2::v_OnCommand(CShellBrowser2 *this, unsigned __int64 a2, HWND a3)
{
  CShellBrowser2 *v6; // rcx
  __int64 v7; // r8
  int v8; // esi
  __int64 v9; // r9
  int v10; // r15d
  __int64 v11; // rdx
  IUnknown *v12; // rcx
  void *v13; // rcx
  DWORD v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  int v17; // eax
  unsigned int v18; // r8d
  bool v19; // al
  ITEMIDLIST *v20; // rcx
  int v21; // r8d
  __int64 v22; // r8
  const GUID *v23; // rdx
  char *v24; // rcx
  void (__fastcall *v25)(char *, const GUID *, __int64, __int64, VARIANTARG *, _QWORD); // rax
  int v26; // edx
  HWND v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // rbx
  struct IEUserBroker **p_ppvOut; // rcx
  __int64 v32; // rcx
  char *v33; // rdi
  unsigned int (__fastcall *v34)(char *, GUID *, __int64); // rax
  bool v35; // si
  int v36; // ebx
  int v37; // ebx
  bool v38; // zf
  unsigned int v39; // edx
  unsigned int v40; // ecx
  __int64 v41; // rcx
  unsigned int PrivacIESettingsMode; // eax
  unsigned int v43; // ecx
  unsigned int CurrentProcessManager; // eax
  unsigned int v45; // r8d
  int v46; // r8d
  GUID *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  int v52; // r8d
  __int64 v53; // rcx
  __int64 v54; // rcx
  int (__fastcall ***v55)(_QWORD, GUID *, struct IBrowserFrame **, __int64); // rcx
  IUnknown *v56; // rcx
  unsigned int v57; // [rsp+20h] [rbp-E0h]
  struct IBrowserFrame *v58; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-B8h] BYREF
  bool v60[8]; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  struct IEUserBroker *v62; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h]
  __int128 v65; // [rsp+88h] [rbp-78h]
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v67[2088]; // [rsp+2B0h] [rbp+1B0h] BYREF

  if ( CShellBrowser2::_ShouldForwardMenu(this, 0x111u, a2, (__int64)a3) )
  {
    CShellBrowser2::_ForwardViewMsg(this, 0x111u, a2, (__int64)a3);
    return 0;
  }
  v8 = 1;
  v9 = 2;
  if ( WORD1(a2) != 1 )
  {
    v10 = 1;
    goto LABEL_15;
  }
  v10 = 2;
  if ( IsDualEngineProcess() )
  {
    if ( (unsigned __int16)a2 <= 0xA233u )
    {
      if ( (_WORD)a2 != 0xA233
        && (unsigned __int16)a2 != 41253
        && (unsigned __int16)a2 != 41330
        && (unsigned __int16)a2 != 41331
        && (unsigned __int16)a2 != 41345
        && (unsigned __int16)a2 != 41436
        && (unsigned __int16)a2 != 41478
        && (unsigned __int16)a2 != 41522 )
      {
        goto LABEL_14;
      }
      goto LABEL_30;
    }
    switch ( (unsigned __int16)a2 )
    {
      case 0xA236u:
      case 0xA237u:
      case 0xA238u:
      case 0xA239u:
        goto LABEL_30;
      case 0xA23Au:
        LOBYTE(v11) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllowF12>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DualEngine_AllowF12>::GetImpl'::`2'::impl,
          v11);
        goto LABEL_30;
      case 0xA23Du:
LABEL_30:
        *((_BYTE *)this + 6992) = 1;
        return 0;
    }
  }
LABEL_14:
  v9 = 2;
LABEL_15:
  if ( (unsigned __int16)(a2 + 24240) <= 5u || (_WORD)a2 == 0xA158 )
  {
    v56 = (IUnknown *)*((_QWORD *)this + 50);
    if ( !v56 )
      return 0;
    v58 = 0;
    if ( IUnknown_QueryService(
           v56,
           &IID_INewWindowManagerCallback,
           &GUID_b5ecdf5d_f3f9_4392_bac5_248961093fa2,
           (void **)&v58) < 0 )
      return 0;
    (*(void (__fastcall **)(struct IBrowserFrame *, _QWORD, __int64))(*(_QWORD *)v58 + 40LL))(
      v58,
      (unsigned __int16)a2,
      41296);
    v13 = v58;
    goto LABEL_282;
  }
  if ( (unsigned __int16)(a2 + 24121) <= 5u )
  {
    v12 = (IUnknown *)*((_QWORD *)this + 50);
    if ( !v12 )
      return 0;
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v12,
           &IID_IPhishingFilterManagerCallback,
           &GUID_1525e844_b912_4558_85cf_b1a3fe27d354,
           &ppvOut) < 0 )
      return 0;
    (*(void (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppvOut + 24LL))(ppvOut, (unsigned __int16)a2, 41415);
LABEL_21:
    v13 = ppvOut;
LABEL_282:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    return 0;
  }
  if ( (unsigned __int16)a2 <= 0xA159u )
  {
    if ( (_WORD)a2 != 0xA159 )
    {
      if ( (unsigned __int16)a2 <= 0xA122u )
      {
        if ( (_WORD)a2 == 0xA122 )
        {
          v18 = 8;
          goto LABEL_67;
        }
        if ( (unsigned __int16)a2 <= 0xA03Bu )
        {
          if ( (_WORD)a2 == 0xA03B )
          {
            v14 = 3;
            goto LABEL_48;
          }
          switch ( (unsigned __int16)a2 )
          {
            case 0xA021u:
              v16 = *((_DWORD *)this + 1588);
              *(_DWORD *)v60 = 0;
              v58 = 0;
              if ( (int)IsoAllocMessageBuffer(v16, (unsigned int *)v60, 0x24u, &v58) >= 0 )
              {
                v17 = (*(__int64 (__fastcall **)(CShellBrowser2 *))(*(_QWORD *)this + 504LL))(this);
                *((_DWORD *)v58 + 8) = v17;
                LCIEPostMessage(*((_DWORD *)this + 1588), *((_DWORD *)this + 1586), 0xC0Cu, 0, *(unsigned int *)v60);
              }
              return 0;
            case 0xA023u:
            case 0xA024u:
            case 0xA025u:
              if ( !(unsigned int)CShellBrowser2::_HasToolbarFocus(this)
                || (v15 = SHSearchMapInt(qword_1805DF6C0, qword_1805DF6D0, 3, (unsigned __int16)a2),
                    (int)IUnknown_Exec(
                           *(_QWORD *)(*((_QWORD *)this + 841) + 48LL * *((int *)this + 1710)),
                           (unsigned int)&CGID_Explorer,
                           v15,
                           0,
                           0,
                           0) < 0) )
              {
                CBaseBrowser2::v_OnCommand(this, a2, (__int64)a3);
              }
              return 0;
            case 0xA030u:
              CShellBrowser2::_CycleFocus(this, 0);
              return 0;
            case 0xA032u:
              CShellBrowser2::_OnBackspace(this, a3, WORD1(a2));
              return 0;
            case 0xA039u:
              v14 = 1;
              goto LABEL_48;
            case 0xA03Au:
              v14 = 2;
LABEL_48:
              InternetFortezzaCommand(v14, *((HWND *)this + 43), 0);
              return 0;
          }
LABEL_247:
          CShellBrowser2::_OnDefault(this, a2, (__int64)a3);
          return 0;
        }
        if ( (unsigned __int16)a2 == 41025
          || (unsigned __int16)a2 == 41026
          || (unsigned __int16)a2 == 41027
          || (unsigned __int16)a2 == 41028 )
        {
          ppvOut = 0;
          if ( (int)CShellBrowser2::_FindActiveTarget(this, (const struct _GUID *)5, &ppvOut) < 0 )
            return 0;
          (*(void (__fastcall **)(void *, _QWORD, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)ppvOut + 32LL))(
            ppvOut,
            0,
            *((unsigned int *)&qword_1805DF6E0[-20512] + (unsigned int)(unsigned __int16)a2 - 1),
            1,
            0,
            0);
          goto LABEL_21;
        }
        if ( (unsigned __int16)a2 != 41030 )
        {
          if ( (unsigned __int16)a2 != 41221 )
          {
            if ( (unsigned __int16)a2 != 41249 )
              goto LABEL_247;
            if ( *((_QWORD *)this + 57) )
            {
              CBaseBrowser2::_CancelPendingView(this);
              return 0;
            }
            v18 = 4;
LABEL_67:
            CBaseBrowser2::NavigateToPidl((CShellBrowser2 *)((char *)this + 8), 0, v18);
            return 0;
          }
          v19 = IsOs_Win8OrGreater();
          LoadStringW(g_hinstMUI, !v19 + 28685, Buffer, 260);
          if ( (int)URLSubstitution(Buffer, v67, 2084, 128) < 0 )
            return 0;
          ppvOut = 0;
          if ( (int)CBaseBrowser2::IEParseDisplayNameEx(
                      (CShellBrowser2 *)((char *)this + 16),
                      0,
                      v67,
                      0,
                      (struct _ITEMIDLIST_ABSOLUTE **)&ppvOut) < 0 )
            return 0;
          (*(void (__fastcall **)(CShellBrowser2 *, void *, __int64))(*(_QWORD *)this + 88LL))(this, ppvOut, 1);
          v20 = (ITEMIDLIST *)ppvOut;
LABEL_71:
          ILFree(v20);
          return 0;
        }
        CShellBrowser2::_PrepareInternetToolbar(this);
        v21 = 10;
LABEL_73:
        IUnknown_Exec(*((_QWORD *)this + 816), (unsigned int)&CGID_PrivCITCommands, v21, 0, 0, 0);
        return 0;
      }
      if ( (unsigned __int16)a2 <= 0xA131u )
      {
        if ( (_WORD)a2 == 0xA131 )
          goto LABEL_87;
        if ( (unsigned __int16)a2 != 41251 )
        {
          switch ( (unsigned __int16)a2 )
          {
            case 0xA125u:
              ppvOut = 0;
              if ( (*(int (__fastcall **)(char *, SID *, GUID *, void **))(*((_QWORD *)this + 4) + 24LL))(
                     (char *)this + 32,
                     &SID_STabWindowManager,
                     &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
                     &ppvOut) >= 0 )
                (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 168LL))(ppvOut, 0);
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
              return 0;
            case 0xA12Au:
              CShellBrowser2::_OnMail(this);
              return 0;
            case 0xA12Bu:
              CShellBrowser2::_ShowDownloadWindowInFrameProcess(this, 0);
              return 0;
            case 0xA12Du:
              CShellBrowser2::_OnNewMessage(v6);
              return 0;
            case 0xA12Eu:
              CShellBrowser2::_SendCurrentPageAsLink(this);
              return 0;
            case 0xA12Fu:
              CShellBrowser2::_SendCurrentPage(this);
              return 0;
          }
          if ( (unsigned __int16)a2 != 41264 )
            goto LABEL_247;
LABEL_87:
          CShellBrowser2::_AddSiteModeToStart(this);
          return 0;
        }
        if ( (unsigned int)SHIsRestricted2W(*((HWND *)this + 43)) )
          return 0;
        v9 = 0xFFFFFFFFLL;
        v22 = 6;
        goto LABEL_98;
      }
      if ( (unsigned __int16)a2 == 41266 )
      {
        CShellBrowser2::_OnDiagnoseConnection(this, v67, v7, Buffer, v57);
        return 0;
      }
      if ( (unsigned __int16)a2 == 41267 )
      {
        CShellBrowser2::_OnClearMyTracks(this);
        return 0;
      }
      if ( (unsigned __int16)a2 != 41268 )
      {
        switch ( (unsigned __int16)a2 )
        {
          case 0xA135u:
            return (*(int (__fastcall **)(char *, const GUID *, __int64))(*((_QWORD *)this + 5) + 32LL))(
                     (char *)this + 40,
                     &CGID_ShellDocView,
                     60);
          case 0xA136u:
            CShellBrowser2::_OnReopenLastTabSet(this);
            return 0;
          case 0xA137u:
            v27 = (HWND)*((_QWORD *)this + 43);
            v28 = SetThreadDpiAwarenessContext(-2);
            v29 = SHFusionDialogBoxParam(
                    g_hinstMUI,
                    (LPCWSTR)0xD125,
                    v27,
                    (DLGPROC)CManageMediaLicensesDialog::ManageMediaLicensesDialogProc,
                    0);
            SetThreadDpiAwarenessContext(v28);
            if ( v29 == -1 )
              GetLastError();
            return 0;
          case 0xA138u:
            v26 = *((_DWORD *)this + 1586);
            LODWORD(ppvOut) = (unsigned __int16)a2;
            TFlatIsoMessage<LCIE_EMULATE7COMMAND>::Post(*((_DWORD *)this + 1588), v26, v7, 2, (__int64)&ppvOut);
            return 0;
        }
        goto LABEL_247;
      }
      ppvOut = 0;
      if ( (int)CShellBrowser2::_GetBrowserFrame(this, (struct IBrowserFrame **)&ppvOut) >= 0 )
      {
        AllowSetForegroundWindow(0xFFFFFFFF);
        IUnknown_Exec((_DWORD)ppvOut, (unsigned int)&CGID_BrowserFrame, 6, 0, 0, 0);
      }
      p_ppvOut = (struct IEUserBroker **)&ppvOut;
LABEL_134:
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(p_ppvOut);
      return 0;
    }
    v32 = *((_QWORD *)this + 807);
    v58 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, struct IBrowserFrame **, __int64, __int64))(*(_QWORD *)v32 + 168LL))(
           v32,
           &v58,
           v7,
           2) )
    {
LABEL_133:
      p_ppvOut = &v58;
      goto LABEL_134;
    }
    ppvOut = 0;
    if ( (*(unsigned int (__fastcall **)(struct IBrowserFrame *, void **))(*(_QWORD *)v58 + 72LL))(v58, &ppvOut)
      || (v33 = (char *)this + 40,
          v34 = *(unsigned int (__fastcall **)(char *, GUID *, __int64))(*((_QWORD *)this + 5) + 32LL),
          memset(&pvarg, 0, sizeof(pvarg)),
          v34((char *)this + 40, &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e, 105))
      || pvarg.vt != 11 )
    {
LABEL_132:
      SysFreeString((BSTR)ppvOut);
      goto LABEL_133;
    }
    bstrString = 0;
    v35 = pvarg.iVal == 0;
    v62 = 0;
    v36 = CoCreateUserBroker(&v62);
    if ( v36 >= 0 )
    {
      *(_QWORD *)v60 = 0;
      v37 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, bool *))(*(_QWORD *)v62 + 48LL))(
              v62,
              &CLSID_CShdocvwBroker,
              &IID_IUnknown,
              v60);
      if ( v37 >= 0 )
      {
        v37 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, BSTR *))v60)(
                *(_QWORD *)v60,
                &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                &bstrString);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v60 + 16LL))(*(_QWORD *)v60);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v62 + 16LL))(v62);
      v38 = v37 == 0;
      if ( v37 < 0 )
        goto LABEL_129;
      v36 = (*(__int64 (__fastcall **)(BSTR, void *, bool))(*(_QWORD *)bstrString + 1288LL))(bstrString, ppvOut, v35);
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    }
    v38 = v36 == 0;
LABEL_129:
    if ( v38 )
    {
      (*(void (__fastcall **)(char *, const GUID *, __int64))(*(_QWORD *)v33 + 32LL))(v33, &CGID_Explorer, 106);
      CShellBrowser2::CEMIEPostRequestCallback::Send((const unsigned __int16 *)ppvOut, v35);
    }
    VariantClear(&pvarg);
    goto LABEL_132;
  }
  if ( (unsigned __int16)a2 > 0xA220u )
  {
    if ( (unsigned __int16)a2 <= 0xA238u )
    {
      if ( (_WORD)a2 == 0xA238 )
        goto LABEL_223;
      switch ( (unsigned __int16)a2 )
      {
        case 0xA223u:
          v24 = (char *)*((_QWORD *)this + 50);
          if ( !v24 )
            return 0;
          v9 = 1;
          v23 = &CGID_ShellDocView;
          v22 = 74;
          goto LABEL_100;
        case 0xA225u:
          v58 = 0;
          if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v58) < 0 )
            goto LABEL_175;
          v46 = 1;
          break;
        case 0xA227u:
          CShellBrowser2::_PrepareInternetToolbar(this);
          v21 = 13;
          goto LABEL_73;
        case 0xA231u:
          v58 = 0;
          if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v58) < 0 )
            goto LABEL_175;
          v46 = 8;
          break;
        default:
          if ( (unsigned __int16)a2 != 41522
            && (unsigned __int16)a2 != 41523
            && (unsigned int)(unsigned __int16)a2 - 41526 > 1 )
          {
            goto LABEL_247;
          }
          if ( ((_WORD)a2 == 0xA232 || (_WORD)a2 == 0xA237) && (unsigned int)SHIsRestricted2W(*((HWND *)this + 43)) )
            return 0;
LABEL_223:
          v58 = 0;
          if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v58) < 0 )
            goto LABEL_175;
          if ( (unsigned __int16)a2 == 41522 )
          {
            v52 = 3;
            goto LABEL_275;
          }
          if ( (unsigned __int16)a2 == 41523 )
          {
            v52 = 4;
            goto LABEL_275;
          }
          v52 = 3;
          if ( (unsigned __int16)a2 == 41526 )
          {
            v52 = 5;
            goto LABEL_275;
          }
          if ( (unsigned __int16)a2 != 41527 )
          {
            switch ( (unsigned __int16)a2 )
            {
              case 0xA238u:
                v52 = 4;
                break;
              case 0xA239u:
                v52 = 5;
                break;
              case 0xA23Du:
                v52 = 9;
                break;
              default:
                v52 = -1;
LABEL_275:
                memset(&pvarg, 0, sizeof(pvarg));
                pvarg.vt = 11;
                if ( v8 )
                  pvarg.iVal = -1;
                else
                  pvarg.iVal = 0;
                IUnknown_Exec((_DWORD)v58, (unsigned int)&CGID_LinksExplorer, v52, 0, (__int64)&pvarg, 0);
                goto LABEL_175;
            }
          }
          v8 = 0;
          goto LABEL_275;
      }
      v47 = &GUID_d4d21454_070f_4033_88f6_1b8d7ba630a9;
      goto LABEL_174;
    }
    switch ( (unsigned __int16)a2 )
    {
      case 0xA239u:
        goto LABEL_223;
      case 0xA23Au:
        if ( GetKeyState(123) < 0 && GetKeyState(16) >= 0 && IsDebuggerPresent() )
          return 0;
        LODWORD(ppvOut) = 1;
        v60[0] = 0;
        CLayerParticipant::LayerGetBool((CShellBrowser2 *)((char *)this + 232), v60, 69722, 0);
        if ( v60[0] )
          return 0;
        if ( IsDualEngineProcess() )
          return 0;
        GetBOOL((__int64 *)SettingStore::IEVALUE_IEDevTools_Disabled[0], &ppvOut);
        if ( (_DWORD)ppvOut )
          return 0;
        v53 = *((_QWORD *)this + 859);
        if ( !v53
          || (LODWORD(ppvOut) = 0,
              (*(unsigned int (__fastcall **)(__int64, void **))(*(_QWORD *)v53 + 64LL))(v53, &ppvOut))
          || (_DWORD)ppvOut
          || (v54 = *((_QWORD *)this + 859),
              *(_DWORD *)v60 = 0,
              (*(unsigned int (__fastcall **)(__int64, bool *))(*(_QWORD *)v54 + 56LL))(v54, v60))
          || !*(_DWORD *)v60 )
        {
          (*(void (__fastcall **)(char *, const GUID *, __int64))(*((_QWORD *)this + 5) + 32LL))(
            (char *)this + 40,
            &CGID_Explorer,
            97);
        }
        break;
      case 0xA23Du:
        goto LABEL_223;
      case 0xA23Eu:
        break;
      case 0xA5D0u:
        Ext_InPrivate_ToggleToolbarDisabled();
        return 0;
      case 0xA620u:
        CurrentProcessManager = IsoGetCurrentProcessManager();
        v45 = 3182;
        goto LABEL_250;
      case 0xA640u:
        v9 = 0;
        v23 = &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e;
        v22 = 75;
        goto LABEL_99;
      default:
        goto LABEL_247;
    }
    v55 = (int (__fastcall ***)(_QWORD, GUID *, struct IBrowserFrame **, __int64))*((_QWORD *)this + 859);
    if ( v55 )
    {
      v58 = 0;
      if ( (**v55)(v55, &GUID_68284faa_6a48_11d0_8c78_00c04fd918b4, &v58, v9) >= 0 )
      {
        *(_QWORD *)&pvarg.vt = 0;
        pvarg.pRecInfo = (IRecordInfo *)9;
        v64 = 0x80000000LL;
        pvarg.llVal = 256;
        v65 = 0;
        (*(void (__fastcall **)(struct IBrowserFrame *, __int64, VARIANTARG *))(*(_QWORD *)v58 + 24LL))(v58, 1, &pvarg);
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v58);
    }
    return 0;
  }
  if ( (_WORD)a2 == 0xA220 )
  {
    v51 = *((_DWORD *)this + 1624);
    if ( (v51 & 0x2000) != 0 )
      return 0;
    *((_DWORD *)this + 1624) = v51 | 0x2000;
    goto LABEL_208;
  }
  if ( (unsigned __int16)a2 <= 0xA206u )
  {
    if ( (_WORD)a2 != 0xA206 )
    {
      if ( (unsigned __int16)a2 != 41312 )
      {
        if ( (unsigned __int16)a2 == 41414 )
        {
          v43 = 1;
        }
        else
        {
          if ( (unsigned __int16)a2 == 41421 )
          {
            v9 = 0;
            v22 = 84;
LABEL_98:
            v23 = &CGID_Explorer;
LABEL_99:
            v24 = (char *)this + 40;
LABEL_100:
            v25 = *(void (__fastcall **)(char *, const GUID *, __int64, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v24 + 32LL);
LABEL_101:
            v25(v24, v23, v22, v9, 0, 0);
            return 0;
          }
          if ( (unsigned __int16)a2 != 41422 )
          {
            if ( (unsigned __int16)a2 == 41423 )
            {
              *(_DWORD *)v60 = 0;
              if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_ActiveXFiltering_IsEnabled[0], v60) >= 0 )
                SetBOOL((__int64 *)SettingStore::IEVALUE_ActiveXFiltering_IsEnabled[0], 2, *(_DWORD *)v60 == 0);
              return 0;
            }
            if ( (unsigned __int16)a2 != 41436 )
            {
              if ( (unsigned __int16)a2 == 41473 )
              {
                v39 = 6;
              }
              else
              {
                if ( (unsigned __int16)a2 != 41474 )
                  goto LABEL_247;
                v39 = 1;
              }
              CShellBrowser2::v_ShowControl((DWORD_PTR)this, v39, 2);
              return 0;
            }
            v60[0] = 0;
            CLayerParticipant::LayerGetBool((CShellBrowser2 *)((char *)this + 232), v60, 69722, 0);
            if ( v60[0] )
              return 0;
            v40 = *((_DWORD *)this + 1588);
            *(_DWORD *)v60 = 0;
            v58 = 0;
            if ( (int)IsoAllocMessageBuffer(v40, (unsigned int *)v60, 0x106Cu, &v58) < 0 )
              return 0;
            v41 = *((_QWORD *)this + 807);
            v62 = 0;
            bstrString = 0;
            if ( !v41
              || (*(int (__fastcall **)(__int64, struct IEUserBroker **))(*(_QWORD *)v41 + 168LL))(v41, &v62) < 0
              || (*(int (__fastcall **)(struct IEUserBroker *, BSTR *))(*(_QWORD *)v62 + 56LL))(v62, &bstrString) < 0
              || (int)StringCchCopyW((unsigned __int16 *)v58 + 16, 0x824u, bstrString) < 0
              || (AllowSetForegroundWindow(0xFFFFFFFF),
                  *((_DWORD *)v58 + 1050) = v10,
                  (int)LCIEPostMessage(
                         *((_DWORD *)this + 1588),
                         *((_DWORD *)this + 1586),
                         0xC0Fu,
                         0,
                         *(unsigned int *)v60) < 0) )
            {
              IsoFreeMessageBuffer(*(unsigned int *)v60);
            }
            SysFreeString(bstrString);
            p_ppvOut = &v62;
            goto LABEL_134;
          }
          if ( (unsigned int)CTPListCollection::DoesValidBlockingListExist() )
          {
            PrivacIESettingsMode = GetPrivacIESettingsMode();
            CTPListCollection::EnableDisableAllFilters(((PrivacIESettingsMode >> 2) & 1) == 0);
            return 0;
          }
          v43 = 5;
        }
        ShowManageAddonsInFrameProcess(v43, *((HWND *)this + 43));
        return 0;
      }
      *(_DWORD *)v60 = 0;
      GetBOOL((__int64 *)SettingStore::IEVALUE_ReportSiteProblems_NoReportSiteProblems[0], v60);
      if ( *(_DWORD *)v60 )
      {
        IEMessageBox(g_hinstMUI, 0, (const unsigned __int16 *)0xBBF, (const unsigned __int16 *)0x3145, 0x10030u);
        return 0;
      }
      AllowSetForegroundWindow(0xFFFFFFFF);
      CurrentProcessManager = IsoGetCurrentProcessManager();
      v45 = 3399;
LABEL_250:
      LCIEPostMessageWithoutBuffer(*((_DWORD *)this + 1588), CurrentProcessManager, v45, 0);
      return 0;
    }
    if ( (unsigned int)SHIsRestricted2W(*((HWND *)this + 43)) )
      return 0;
    v58 = 0;
    if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v58) < 0 )
    {
LABEL_175:
      p_ppvOut = &v58;
      goto LABEL_134;
    }
    v46 = 4;
    goto LABEL_173;
  }
  switch ( (unsigned __int16)a2 )
  {
    case 0xA209u:
      v58 = 0;
      if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v58) < 0 )
        goto LABEL_175;
      v46 = 5;
LABEL_173:
      v47 = (GUID *)&CGID_BrowserFrame;
LABEL_174:
      IUnknown_Exec((_DWORD)v58, (_DWORD)v47, v46, 0, 0, 0);
      goto LABEL_175;
    case 0xA20Au:
      if ( (unsigned int)SHIsRestricted2W(*((HWND *)this + 43)) )
        return 0;
      CShellBrowser2::_PrepareInternetToolbar(this);
      v21 = 12;
      goto LABEL_73;
    case 0xA20Bu:
      v58 = 0;
      if ( !LoadStringW(g_hinstMUI, 0xD122u, Buffer, 260)
        || (int)CBaseBrowser2::IEParseDisplayNameEx((CShellBrowser2 *)((char *)this + 16), 0, Buffer, 0, &v58) < 0 )
      {
        return 0;
      }
      (*(void (__fastcall **)(CShellBrowser2 *, struct IBrowserFrame *, __int64))(*(_QWORD *)this + 88LL))(this, v58, 1);
      v20 = (ITEMIDLIST *)v58;
      goto LABEL_71;
    case 0xA20Cu:
      CShellBrowser2::_PrepareInternetToolbar(this);
      v50 = *((_QWORD *)this + 816);
      if ( v50 )
        IUnknown_Exec(v50, (unsigned int)&CGID_PrivCITCommands, 23, 0, 0, 0);
      if ( !*((_QWORD *)this + 815) )
        return 0;
      bstrString = 0;
      if ( (int)CShellBrowser2::_GetBrowserFrame(this, (struct IBrowserFrame **)&bstrString) >= 0 )
      {
        v58 = 0;
        if ( (**(int (__fastcall ***)(BSTR, GUID *, struct IBrowserFrame **))bstrString)(
               bstrString,
               &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
               &v58) >= 0 )
          (*(void (__fastcall **)(struct IBrowserFrame *, const struct _GUID *, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v58 + 32LL))(
            v58,
            &CGID_BrowserFrame,
            0,
            2,
            0,
            0);
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v58);
      }
      p_ppvOut = (struct IEUserBroker **)&bstrString;
      goto LABEL_134;
    case 0xA21Au:
LABEL_208:
      v24 = (char *)this + 40;
      v25 = *(void (__fastcall **)(char *, const GUID *, __int64, __int64, VARIANTARG *, _QWORD))(*((_QWORD *)this + 5)
                                                                                                + 32LL);
      if ( (_WORD)a2 == 0xA220 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 3;
        pvarg.lVal = 8196;
        v25(v24, 0, 22, 2, &pvarg, 0);
        *((_DWORD *)this + 1624) &= ~0x2000u;
        return 0;
      }
      v23 = 0;
      v22 = 23;
      goto LABEL_101;
    case 0xA21Bu:
      if ( !(unsigned int)SHRestricted2W(1610612746, 0, 0) )
      {
        v48 = *((_QWORD *)this + 46);
        *(_WORD *)v60 = 0;
        if ( v48 )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64, bool *))(*(_QWORD *)v48 + 520LL))(v48, v60) )
          {
            if ( *(_WORD *)v60 )
              v49 = 0;
            else
              v49 = -1;
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 46) + 528LL))(*((_QWORD *)this + 46), v49);
          }
        }
      }
      return 0;
  }
  if ( (unsigned __int16)a2 != 41500 )
    goto LABEL_247;
  return 0;
}

```

## disassembly

```asm
0x1801ec5b0  mov     [rsp-8+arg_18], rbx
0x1801ec5b5  push    rbp
0x1801ec5b6  push    rsi
0x1801ec5b7  push    rdi
0x1801ec5b8  push    r12
0x1801ec5ba  push    r13
0x1801ec5bc  push    r14
0x1801ec5be  push    r15
0x1801ec5c0  lea     rbp, [rsp-1210h]
0x1801ec5c8  mov     eax, 1310h
0x1801ec5cd  call    _alloca_probe
0x1801ec5d2  sub     rsp, rax
0x1801ec5d5  mov     rax, cs:__security_cookie
0x1801ec5dc  xor     rax, rsp
0x1801ec5df  mov     [rbp+1240h+var_40], rax
0x1801ec5e6  mov     r12, r8
0x1801ec5e9  mov     r9, r8; __int64
0x1801ec5ec  mov     r8, rdx; unsigned __int64
0x1801ec5ef  mov     rdi, rdx
0x1801ec5f2  mov     esi, 111h
0x1801ec5f7  mov     rbx, rcx
0x1801ec5fa  mov     edx, esi; unsigned int
0x1801ec5fc  call    ?_ShouldForwardMenu@CShellBrowser2@@AEAAHI_K_J@Z; CShellBrowser2::_ShouldForwardMenu(uint,unsigned __int64,__int64)
0x1801ec601  xor     r13d, r13d
0x1801ec604  test    eax, eax
0x1801ec606  jz      short loc_1801EC61D
0x1801ec608  mov     r9, r12; __int64
0x1801ec60b  mov     r8, rdi; unsigned __int64
0x1801ec60e  mov     edx, esi; unsigned int
0x1801ec610  mov     rcx, rbx; this
0x1801ec613  call    ?_ForwardViewMsg@CShellBrowser2@@AEAA_JI_K_J@Z; CShellBrowser2::_ForwardViewMsg(uint,unsigned __int64,__int64)
0x1801ec618  jmp     loc_1801ED8F5
0x1801ec61d  mov     esi, 1
0x1801ec622  mov     r14, rdi
0x1801ec625  shr     r14, 10h
0x1801ec629  lea     r10d, [rsi+2]
0x1801ec62d  lea     r9d, [rsi+1]
0x1801ec631  cmp     r14w, si
0x1801ec635  jnz     loc_1801EC77A
0x1801ec63b  mov     r15d, r9d
0x1801ec63e  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801ec644  test    al, al
0x1801ec646  jz      short loc_1801EC69F
0x1801ec648  mov     eax, 0A233h
0x1801ec64d  cmp     di, ax
0x1801ec650  ja      loc_1801EC735
0x1801ec656  jz      loc_1801EC76E
0x1801ec65c  movzx   eax, di
0x1801ec65f  sub     eax, 0A125h
0x1801ec664  jz      loc_1801EC76E
0x1801ec66a  sub     eax, 4Dh ; 'M'
0x1801ec66d  jz      loc_1801EC76E
0x1801ec673  sub     eax, esi
0x1801ec675  jz      loc_1801EC76E
0x1801ec67b  sub     eax, 0Eh
0x1801ec67e  jz      loc_1801EC76E
0x1801ec684  sub     eax, 5Bh ; '['
0x1801ec687  jz      loc_1801EC76E
0x1801ec68d  sub     eax, 2Ah ; '*'
0x1801ec690  jz      loc_1801EC76E
0x1801ec696  cmp     eax, 2Ch ; ','
0x1801ec699  jz      loc_1801EC76E
0x1801ec69f  mov     r10d, 3
0x1801ec6a5  mov     r9d, r15d
0x1801ec6a8  mov     eax, 5EB0h
0x1801ec6ad  mov     edx, 5; struct _GUID *
0x1801ec6b2  add     eax, edi
0x1801ec6b4  cmp     ax, dx
0x1801ec6b7  jbe     loc_1801ED89C
0x1801ec6bd  mov     eax, 0A158h
0x1801ec6c2  cmp     di, ax
0x1801ec6c5  jz      loc_1801ED89C
0x1801ec6cb  mov     eax, 5E39h
0x1801ec6d0  add     eax, edi
0x1801ec6d2  cmp     ax, dx
0x1801ec6d5  ja      loc_1801EC782
0x1801ec6db  mov     rcx, [rbx+190h]; punk
0x1801ec6e2  test    rcx, rcx
0x1801ec6e5  jz      loc_1801ED8F5
0x1801ec6eb  lea     r9, [rsp+1340h+ppvOut]; ppvOut
0x1801ec6f0  mov     [rsp+1340h+ppvOut], r13
0x1801ec6f5  lea     r8, _GUID_1525e844_b912_4558_85cf_b1a3fe27d354; riid
0x1801ec6fc  lea     rdx, IID_IPhishingFilterManagerCallback; guidService
0x1801ec703  call    cs:__imp_IUnknown_QueryService
0x1801ec709  test    eax, eax
0x1801ec70b  js      loc_1801ED8F5
0x1801ec711  mov     rcx, [rsp+1340h+ppvOut]
0x1801ec716  mov     r8d, 0A1C7h
0x1801ec71c  movzx   edx, di
0x1801ec71f  mov     rax, [rcx]
0x1801ec722  mov     rax, [rax+18h]
0x1801ec726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec72b  mov     rcx, [rsp+1340h+ppvOut]
0x1801ec730  jmp     loc_1801ED8E9
0x1801ec735  movzx   eax, di
0x1801ec738  sub     eax, 0A236h
0x1801ec73d  jz      short loc_1801EC76E
0x1801ec73f  sub     eax, esi
0x1801ec741  jz      short loc_1801EC76E
0x1801ec743  sub     eax, esi
0x1801ec745  jz      short loc_1801EC76E
0x1801ec747  sub     eax, esi
0x1801ec749  jz      short loc_1801EC76E
0x1801ec74b  sub     eax, esi
0x1801ec74d  jz      short loc_1801EC75F
0x1801ec74f  mov     r10d, 3
0x1801ec755  cmp     eax, r10d
0x1801ec758  jz      short loc_1801EC76E
0x1801ec75a  jmp     loc_1801EC6A5
0x1801ec75f  mov     dl, sil
0x1801ec762  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_AllowF12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllowF12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllowF12> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_AllowF12>::GetImpl(void)'::`2'::impl
0x1801ec769  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllowF12@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllowF12>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801ec76e  mov     [rbx+1B50h], sil
0x1801ec775  jmp     loc_1801ED8F5
0x1801ec77a  mov     r15d, esi
0x1801ec77d  jmp     loc_1801EC6A8
0x1801ec782  mov     eax, 0A159h
0x1801ec787  cmp     di, ax
0x1801ec78a  ja      loc_1801ECF1A
0x1801ec790  jz      loc_1801ECD51
0x1801ec796  mov     eax, 0A122h
0x1801ec79b  cmp     di, ax
0x1801ec79e  ja      loc_1801ECABF
0x1801ec7a4  jz      loc_1801ECAB4
0x1801ec7aa  mov     eax, 0A03Bh
0x1801ec7af  cmp     di, ax
0x1801ec7b2  ja      loc_1801EC923
0x1801ec7b8  jz      loc_1801EC91B
0x1801ec7be  movzx   r15d, di
0x1801ec7c2  mov     eax, r15d
0x1801ec7c5  sub     eax, 0A021h
0x1801ec7ca  jz      loc_1801EC8AB
0x1801ec7d0  sub     eax, r9d
0x1801ec7d3  jz      short loc_1801EC833
0x1801ec7d5  sub     eax, esi
0x1801ec7d7  jz      short loc_1801EC833
0x1801ec7d9  sub     eax, esi
0x1801ec7db  jz      short loc_1801EC833
0x1801ec7dd  sub     eax, 0Bh
0x1801ec7e0  jz      short loc_1801EC824
0x1801ec7e2  sub     eax, r9d
0x1801ec7e5  jz      short loc_1801EC810
0x1801ec7e7  sub     eax, 7
0x1801ec7ea  jz      short loc_1801EC7F9
0x1801ec7ec  cmp     eax, esi
0x1801ec7ee  jnz     loc_1801ED64E
0x1801ec7f4  mov     ecx, r9d
0x1801ec7f7  jmp     short loc_1801EC7FB
0x1801ec7f9  mov     ecx, esi; dwCommand
0x1801ec7fb  mov     rdx, [rbx+158h]; hwnd
0x1801ec802  xor     r8d, r8d; dwReserved
0x1801ec805  call    cs:__imp_InternetFortezzaCommand
0x1801ec80b  jmp     loc_1801ED8F5
0x1801ec810  movzx   r8d, r14w; unsigned int
0x1801ec814  mov     rdx, r12; HWND
0x1801ec817  mov     rcx, rbx; this
0x1801ec81a  call    ?_OnBackspace@CShellBrowser2@@AEAAXPEAUHWND__@@I@Z; CShellBrowser2::_OnBackspace(HWND__ *,uint)
0x1801ec81f  jmp     loc_1801ED8F5
0x1801ec824  xor     edx, edx; struct tagMSG *
0x1801ec826  mov     rcx, rbx; this
0x1801ec829  call    ?_CycleFocus@CShellBrowser2@@AEAAJPEAUtagMSG@@@Z; CShellBrowser2::_CycleFocus(tagMSG *)
0x1801ec82e  jmp     loc_1801ED8F5
0x1801ec833  mov     rcx, rbx; this
0x1801ec836  call    ?_HasToolbarFocus@CShellBrowser2@@AEAAHXZ; CShellBrowser2::_HasToolbarFocus(void)
0x1801ec83b  test    eax, eax
0x1801ec83d  jz      short loc_1801EC898
0x1801ec83f  mov     r9d, r15d
0x1801ec842  lea     rdx, qword_1805DF6D0
0x1801ec849  mov     r8d, 3
0x1801ec84f  lea     rcx, qword_1805DF6C0
0x1801ec856  call    SHSearchMapInt
0x1801ec85b  mov     rcx, [rbx+1A48h]
0x1801ec862  lea     rdx, CGID_Explorer
0x1801ec869  mov     r8d, eax
0x1801ec86c  mov     [rsp+1340h+var_1318], r13
0x1801ec871  movsxd  rax, dword ptr [rbx+1AB8h]
0x1801ec878  xor     r9d, r9d
0x1801ec87b  mov     [rsp+1340h+var_1320], r13
0x1801ec880  lea     r10, [rax+rax*2]
0x1801ec884  add     r10, r10
0x1801ec887  mov     rcx, [rcx+r10*8]
0x1801ec88b  call    IUnknown_Exec
0x1801ec890  test    eax, eax
0x1801ec892  jns     loc_1801ED8F5
0x1801ec898  mov     r8, r12; __int64
0x1801ec89b  mov     rdx, rdi; unsigned __int64
0x1801ec89e  mov     rcx, rbx; this
0x1801ec8a1  call    ?v_OnCommand@CBaseBrowser2@@MEAA_J_K_J@Z; CBaseBrowser2::v_OnCommand(unsigned __int64,__int64)
0x1801ec8a6  jmp     loc_1801ED8F5
0x1801ec8ab  mov     ecx, [rbx+18D0h]
0x1801ec8b1  lea     r9, [rsp+1340h+var_1300]
0x1801ec8b6  mov     r8d, 24h ; '$'
0x1801ec8bc  mov     dword ptr [rsp+1340h+var_12F0], r13d
0x1801ec8c1  lea     rdx, [rsp+1340h+var_12F0]
0x1801ec8c6  mov     [rsp+1340h+var_1300], r13
0x1801ec8cb  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x1801ec8d1  test    eax, eax
0x1801ec8d3  js      loc_1801ED8F5
0x1801ec8d9  mov     rax, [rbx]
0x1801ec8dc  mov     rcx, rbx
0x1801ec8df  mov     rax, [rax+1F8h]
0x1801ec8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec8eb  mov     rcx, [rsp+1340h+var_1300]
0x1801ec8f0  xor     r9d, r9d
0x1801ec8f3  mov     r8d, 0C0Ch
0x1801ec8f9  mov     [rcx+20h], eax
0x1801ec8fc  mov     eax, dword ptr [rsp+1340h+var_12F0]
0x1801ec900  mov     edx, [rbx+18C8h]
0x1801ec906  mov     ecx, [rbx+18D0h]
0x1801ec90c  mov     dword ptr [rsp+1340h+var_1320], eax
0x1801ec910  call    cs:__imp_?LCIEPostMessage@@YAJKKKKK@Z; LCIEPostMessage(ulong,ulong,ulong,ulong,ulong)
0x1801ec916  jmp     loc_1801ED8F5
0x1801ec91b  mov     ecx, r10d
0x1801ec91e  jmp     loc_1801EC7FB
0x1801ec923  movzx   r14d, di
0x1801ec927  mov     eax, r14d
0x1801ec92a  sub     eax, 0A041h
0x1801ec92f  jz      loc_1801ECA63
0x1801ec935  sub     eax, esi
0x1801ec937  jz      loc_1801ECA63
0x1801ec93d  sub     eax, esi
0x1801ec93f  jz      loc_1801ECA63
0x1801ec945  sub     eax, esi
0x1801ec947  jz      loc_1801ECA63
0x1801ec94d  sub     eax, r9d
0x1801ec950  jz      loc_1801ECA30
0x1801ec956  sub     eax, 0BFh
0x1801ec95b  jz      short loc_1801EC992
0x1801ec95d  cmp     eax, 1Ch
0x1801ec960  jnz     loc_1801ED64E
0x1801ec966  cmp     [rbx+1C8h], r13
0x1801ec96d  jz      short loc_1801EC97C
0x1801ec96f  mov     rcx, rbx; this
0x1801ec972  call    ?_CancelPendingView@CBaseBrowser2@@IEAAJXZ; CBaseBrowser2::_CancelPendingView(void)
0x1801ec977  jmp     loc_1801ED8F5
0x1801ec97c  mov     r8d, 4; unsigned int
0x1801ec982  xor     edx, edx; struct _ITEMIDLIST_ABSOLUTE *
0x1801ec984  lea     rcx, [rbx+8]; this
0x1801ec988  call    ?NavigateToPidl@CBaseBrowser2@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@K@Z; CBaseBrowser2::NavigateToPidl(_ITEMIDLIST_ABSOLUTE const *,ulong)
0x1801ec98d  jmp     loc_1801ED8F5
0x1801ec992  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x1801ec997  mov     rcx, cs:g_hinstMUI; hInstance
0x1801ec99e  lea     r8, [rbp+1240h+Buffer]; lpBuffer
0x1801ec9a2  movzx   edx, al
0x1801ec9a5  mov     r9d, 104h; cchBufferMax
0x1801ec9ab  xor     edx, esi
0x1801ec9ad  add     edx, 700Dh; uID
0x1801ec9b3  call    cs:__imp_LoadStringW
0x1801ec9b9  mov     r9d, 80h
0x1801ec9bf  lea     rdx, [rbp+1240h+var_1090]
0x1801ec9c6  mov     r8d, 824h
0x1801ec9cc  lea     rcx, [rbp+1240h+Buffer]
0x1801ec9d0  call    URLSubstitution
0x1801ec9d5  test    eax, eax
0x1801ec9d7  js      loc_1801ED8F5
0x1801ec9dd  lea     rax, [rsp+1340h+ppvOut]
0x1801ec9e2  mov     [rsp+1340h+ppvOut], r13
0x1801ec9e7  lea     rcx, [rbx+10h]; this
0x1801ec9eb  mov     [rsp+1340h+var_1320], rax; struct _ITEMIDLIST_ABSOLUTE **
0x1801ec9f0  xor     r9d, r9d; unsigned int
0x1801ec9f3  lea     r8, [rbp+1240h+var_1090]; unsigned __int16 *
0x1801ec9fa  xor     edx, edx; unsigned int
0x1801ec9fc  call    ?IEParseDisplayNameEx@CBaseBrowser2@@UEAAJIPEBGKPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CBaseBrowser2::IEParseDisplayNameEx(uint,ushort const *,ulong,_ITEMIDLIST_ABSOLUTE * *)
0x1801eca01  test    eax, eax
0x1801eca03  js      loc_1801ED8F5
0x1801eca09  mov     rax, [rbx]
0x1801eca0c  mov     r8d, esi
0x1801eca0f  mov     rdx, [rsp+1340h+ppvOut]
0x1801eca14  mov     rcx, rbx
0x1801eca17  mov     rax, [rax+58h]
0x1801eca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eca20  mov     rcx, [rsp+1340h+ppvOut]; pidl
0x1801eca25  call    cs:__imp_ILFree
0x1801eca2b  jmp     loc_1801ED8F5
0x1801eca30  mov     rcx, rbx; this
0x1801eca33  call    ?_PrepareInternetToolbar@CShellBrowser2@@AEAAJXZ; CShellBrowser2::_PrepareInternetToolbar(void)
0x1801eca38  mov     r8d, 0Ah
0x1801eca3e  mov     rcx, [rbx+1980h]
0x1801eca45  lea     rdx, CGID_PrivCITCommands
0x1801eca4c  mov     [rsp+1340h+var_1318], r13
0x1801eca51  xor     r9d, r9d
0x1801eca54  mov     [rsp+1340h+var_1320], r13
0x1801eca59  call    IUnknown_Exec
0x1801eca5e  jmp     loc_1801ED8F5
0x1801eca63  lea     r8, [rsp+1340h+ppvOut]; void **
0x1801eca68  mov     [rsp+1340h+ppvOut], r13
0x1801eca6d  mov     rcx, rbx; this
0x1801eca70  call    ?_FindActiveTarget@CShellBrowser2@@AEAAJAEBU_GUID@@PEAPEAX@Z; CShellBrowser2::_FindActiveTarget(_GUID const &,void * *)
0x1801eca75  test    eax, eax
0x1801eca77  js      loc_1801ED8F5
0x1801eca7d  mov     rcx, [rsp+1340h+ppvOut]
0x1801eca82  lea     r8d, [r14-0A041h]
0x1801eca89  lea     r10, qword_1805DF6E0
0x1801eca90  mov     [rsp+1340h+var_1318], r13
0x1801eca95  mov     r8d, [r10+r8*4]
0x1801eca99  mov     r9d, esi
0x1801eca9c  mov     [rsp+1340h+var_1320], r13
0x1801ecaa1  mov     rdx, [rcx]
0x1801ecaa4  mov     rax, [rdx+20h]
0x1801ecaa8  xor     edx, edx
  ... truncated ...
```
