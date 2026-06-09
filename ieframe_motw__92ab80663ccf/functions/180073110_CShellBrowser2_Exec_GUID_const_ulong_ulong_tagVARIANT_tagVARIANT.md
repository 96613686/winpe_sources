# CShellBrowser2::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x180073110`
- end: `0x180074c7f`
- name: `?Exec@CShellBrowser2@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `7023`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, const struct _GUID *, unsigned int, unsigned int, VARIANTARG *pvarg, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `71`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005030`
- `0x180023c4c`
- `0x180024bc4`
- `0x180034250`
- `0x18004b960`
- `0x18004d964`
- `0x180071e24`
- `0x180073110`
- `0x180074e98`
- `0x18007a044`
- `0x18007c324`
- `0x180084e10`
- `0x180085898`
- `0x180085b10`
- `0x18008bde4`
- `0x18009d000`
- `0x1800aaa00`
- `0x1800b9bfc`
- `0x1800cfb24`
- `0x1800d1c00`
- `0x180101460`
- `0x1801b8b70`
- `0x1801d7c38`
- `0x1801d7c74`
- `0x1801d7cc8`
- `0x1801e31e8`
- `0x1801f1340`
- `0x1801f2ab4`
- `0x1801f3d88`
- `0x1801f66b0`
- `0x1801f77c8`
- `0x1801f9818`
- `0x1801f99e4`
- `0x1801fa204`
- `0x1801fb048`
- `0x1801fbf18`
- `0x1801fc680`
- `0x1801fc768`
- `0x1801fc95c`
- `0x1801fd32c`
- `0x1801fd4a0`
- `0x1801fd658`
- `0x1801fd8f0`
- `0x1801fd938`
- `0x1801fd970`
- `0x1801fef4c`
- `0x1801ff5ec`
- `0x180202b64`
- `0x180202d98`
- `0x180203094`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800741ea`
- `KERNEL32!GetCurrentThreadId` at `0x1800741ea`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x18007343e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x18007343e`
- `USER32!SetMenuItemInfoW` at `0x1800736a2`
- `USER32!SetMenuItemInfoW` at `0x1800736bf`
- `USER32!SetMenuItemInfoW` at `0x1800736a2`
- `USER32!SetMenuItemInfoW` at `0x1800736bf`
- `USER32!SetTimer` at `0x180073b6f`
- `USER32!SetTimer` at `0x1800741ac`
- `USER32!SetTimer` at `0x180073b6f`
- `USER32!SetTimer` at `0x1800741ac`
- `USER32!KillTimer` at `0x180073b3f`
- `USER32!KillTimer` at `0x180073bdb`
- `USER32!KillTimer` at `0x180074174`
- `USER32!KillTimer` at `0x180074257`
- `USER32!KillTimer` at `0x180073b3f`
- `USER32!KillTimer` at `0x180073bdb`
- `USER32!KillTimer` at `0x180074174`
- `USER32!KillTimer` at `0x180074257`
- `USER32!GetWindowPlacement` at `0x1800737b0`
- `USER32!GetWindowPlacement` at `0x1800737b0`
- `USER32!PostMessageW` at `0x1800731d3`
- `USER32!PostMessageW` at `0x1800731d3`
- `USER32!SendMessageW` at `0x18007331d`
- `USER32!SendMessageW` at `0x180074868`
- `USER32!SendMessageW` at `0x18007331d`
- `USER32!SendMessageW` at `0x180074868`
- `OLEAUT32!__imp_SysAllocString` at `0x180073976`
- `OLEAUT32!__imp_SysAllocString` at `0x180074766`
- `OLEAUT32!__imp_SysAllocString` at `0x180073976`
- `OLEAUT32!__imp_SysAllocString` at `0x180074766`
- `SHELL32!__imp_ILFree` at `0x180073b8f`
- `SHELL32!__imp_ILFree` at `0x180074944`
- `SHELL32!__imp_ILFree` at `0x180074c15`
- `SHELL32!__imp_ILFree` at `0x180073b8f`
- `SHELL32!__imp_ILFree` at `0x180074944`
- `SHELL32!__imp_ILFree` at `0x180074c15`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180074786`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180074786`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800731ad`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180073499`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800731ad`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180073499`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180074205`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180074205`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180073925`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180073925`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180073a1e`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180073a1e`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1800739fd`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1800739fd`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18007383f`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18007383f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007393d`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007393d`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1800738d5`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1800738d5`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800739e9`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800739e9`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x180074229`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x180074229`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1800739dd`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1800739dd`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800747a1`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800747a1`

## string_xrefs

- `0x18007452e`: `CommBar`

## pseudocode

```c
__int64 __fastcall CShellBrowser2::Exec(
        unsigned __int64 this,
        ITEMIDLIST *a2,
        unsigned int a3,
        unsigned int a4,
        VARIANTARG *pvarg,
        struct tagVARIANT *a6)
{
  unsigned int lVal_high; // r13d
  WPARAM v10; // r8
  UINT v11; // edx
  __int64 result; // rax
  _QWORD *v13; // rcx
  LONG lVal; // ecx
  int Instance; // eax
  LPITEMIDLIST v16; // rcx
  WCHAR *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20; // r14
  int v21; // r8d
  bool v22; // dl
  int v23; // eax
  unsigned int v24; // eax
  const char *v25; // rdx
  bool v26; // r9
  __int64 v27; // rcx
  int v28; // eax
  int v29; // edx
  HMENU v30; // rdx
  HMENU v31; // rbx
  UINT v32; // edx
  HWND v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // ecx
  BSTR v36; // rax
  unsigned int CurrentProcessManager; // eax
  bool v38; // zf
  unsigned int v39; // eax
  __int64 v40; // rcx
  CShellBrowser2 *v41; // rcx
  bool v42; // zf
  LONG v43; // edx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned int v46; // eax
  int v47; // edx
  __int64 v48; // rax
  __int64 v49; // rcx
  struct IUnknown *v50; // rcx
  unsigned int v51; // eax
  bool v52; // r10
  unsigned int v53; // eax
  __int64 v54; // r9
  __int64 v55; // r8
  int (__fastcall ***v56)(_QWORD, GUID *, MENUITEMINFOW *); // rcx
  int (__fastcall **v57)(_QWORD, GUID *, MENUITEMINFOW *); // rax
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rcx
  HWND *v63; // r14
  unsigned int ExtensionCommand; // edi
  __int64 v65; // r8
  int v66; // r8d
  int v67; // r9d
  int v68; // edx
  int v69; // ecx
  unsigned int v70; // r15d
  unsigned int v71; // r15d
  unsigned int v72; // r15d
  unsigned int v73; // r15d
  unsigned int v74; // r15d
  unsigned int v75; // r15d
  unsigned int v76; // r15d
  DWORD CurrentThreadId; // eax
  LONG v78; // edx
  __int64 v79; // rcx
  unsigned int v80; // r15d
  unsigned int v81; // r15d
  unsigned int v82; // r15d
  unsigned int v83; // edi
  SHORT iVal; // cx
  LONG v85; // eax
  struct IUnknown *punkVal; // r8
  int IsSameToolbar; // eax
  CShellBrowser2 *v88; // rcx
  unsigned int v89; // edx
  int v90; // eax
  signed int TBar; // eax
  __int64 v92; // rcx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  __int64 (__fastcall ***v94)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  CShellBrowser2 *v95; // rcx
  LPITEMIDLIST v96; // rdi
  __int64 (__fastcall *v97)(LPITEMIDLIST, unsigned __int64, _QWORD); // rbx
  unsigned int HiddenTabCookie; // eax
  unsigned int v99; // eax
  const OLECHAR *v100; // rax
  BSTR v101; // rax
  int v102; // eax
  LONG v103; // edx
  unsigned __int16 *v104; // rsi
  unsigned __int16 *bstrVal; // r15
  LONGLONG v106; // rcx
  unsigned int v107; // eax
  LONGLONG v108; // rcx
  bool v109; // al
  __int64 v110; // rcx
  LONGLONG v111; // rcx
  const struct _GUID *v112; // rdi
  __int64 v113; // rcx
  LONGLONG v114; // rdx
  const struct _ITEMIDLIST_ABSOLUTE *cchBuf; // [rsp+20h] [rbp-E0h]
  unsigned int v116; // [rsp+28h] [rbp-D8h]
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST v118[3]; // [rsp+48h] [rbp-B8h] BYREF
  MENUITEMINFOW mii; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR psz[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszFirst[2088]; // [rsp+2C0h] [rbp+1C0h] BYREF

  LODWORD(pidl) = a4;
  v118[0] = a2;
  lVal_high = 1;
  if ( a2 )
  {
    if ( *(_QWORD *)&CGID_Explorer.Data1 == *(_QWORD *)&a2->mkid.cb
      && *(_QWORD *)CGID_Explorer.Data4 == *(_QWORD *)a2[2].mkid.abID )
    {
      if ( a3 <= 0x68 )
      {
        if ( a3 == 104 )
        {
          CShellBrowser2::_ShowDownloadWindowInFrameProcess((CShellBrowser2 *)(this - 40), 1);
          return 0;
        }
        if ( a3 <= 0x50 )
        {
          if ( a3 != 80 )
          {
            if ( a3 != 2 )
            {
              if ( a3 != 8 )
              {
                if ( a3 == 57 )
                  return ((*(_DWORD *)(this + 700) >> 20) & 1) == 0;
                if ( a3 == 58 )
                {
                  pidl = 0;
                  if ( (int)CShellBrowser2::_GetBrowserFrame(
                              (CShellBrowser2 *)(this - 40),
                              (struct IBrowserFrame **)&pidl) >= 0 )
                    lVal_high = (*(int (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 72LL))(pidl) < 0;
                  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
                  return lVal_high;
                }
                if ( a3 != 62 )
                {
                  if ( a3 != 70 )
                  {
                    if ( a3 == 71 )
                    {
                      SendMessageW(*(HWND *)(this + 304), 0x1Au, a4, pvarg->llVal);
                      return 0;
                    }
                    if ( a3 != 72 )
                      goto LABEL_239;
                    lVal = pvarg->lVal;
                    pidl = 0;
                    Instance = CBrowserWinMsgPackage_GetInstance(lVal, (struct IBrowserAsyncPackage **)&pidl);
                    *(_OWORD *)&pvarg->vt = 0;
                    if ( Instance < 0 )
                    {
                      result = 0;
                      pvarg->pRecInfo = 0;
                    }
                    else
                    {
                      *(_OWORD *)&pvarg->decVal.Lo32 = (unsigned __int64)pidl;
                      pvarg->vt = 13;
                      return CShellBrowser2::_ProcessTranslateAccAsync((CShellBrowser2 *)(this - 40), pvarg);
                    }
                    return result;
                  }
                  pidl = 0;
                  if ( !pvarg || (int)VariantToIDList(pvarg, &pidl) < 0 || !a6 || a6->vt != 11 )
                    return 0;
                  v16 = pidl;
                  a6->iVal = 0;
                  if ( (unsigned int)TryIEShellDelegation(v16, 0) )
                    a6->iVal = -1;
LABEL_163:
                  ILFree(pidl);
                  return 0;
                }
                goto LABEL_73;
              }
              goto LABEL_77;
            }
            v17 = pszFirst;
            v18 = 2084;
            do
            {
              *(_BYTE *)v17 = 0;
              v17 = (WCHAR *)((char *)v17 + 1);
              --v18;
            }
            while ( v18 );
            v19 = *(_QWORD *)(this + 368);
            v20 = 0;
            if ( v19 && (int)IEGetNameAndFlagsEx(v19, 0x8000, 0, (int)pszFirst, 0x824u, 0) >= 0 )
              v20 = pszFirst == StrStrIW(pszFirst, L"microsoft-edge");
            if ( (!*(_QWORD *)(this + 368) || v20) && pvarg && pvarg->vt == 3 && !pvarg->lVal )
            {
              CBaseBrowser2::_CancelPendingNavigationAsync((CBaseBrowser2 *)(this - 40));
              if ( IsDualEngineProcess() )
              {
                CShellBrowser2::_DualEngineOnDeferredCloseCommand((CShellBrowser2 *)(this - 40), 0, 1);
                return 0;
              }
              v10 = 0;
              v11 = 16;
              goto LABEL_10;
            }
LABEL_239:
            v63 = (HWND *)(this - 40);
            ExtensionCommand = CShellBrowser2::_Exec_CCommonBrowser(
                                 (CShellBrowser2 *)(this - 40),
                                 (const struct _GUID *)v118[0],
                                 a3,
                                 (unsigned int)pidl,
                                 pvarg,
                                 a6);
            if ( !v118[0] )
            {
              if ( a3 == 22 )
              {
                CShellBrowser2::_SetTitle((CShellBrowser2 *)(this - 40), 0);
                (*((void (__fastcall **)(unsigned __int64, _QWORD))*v63 + 56))(this - 40, 0);
                ExtensionCommand = 0;
                *(_QWORD *)&mii.cbSize = 0;
                CShellBrowser2::FindToolbar(
                  (CShellBrowser2 *)(this + 6264),
                  L"BrowserBar",
                  &GUID_eb0fe173_1a3a_11d0_89b3_00a0c90a90ac,
                  (void **)&mii);
                if ( *(_QWORD *)&mii.cbSize )
                {
                  IUnknown_Exec(mii.cbSize, 0, 22, (_DWORD)pidl, (__int64)pvarg, (__int64)a6);
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&mii.cbSize + 16LL))(*(_QWORD *)&mii.cbSize);
                }
                v68 = *(_DWORD *)(this + 6304);
                v69 = *(_DWORD *)(this + 6312);
                LODWORD(pidl) = *(_DWORD *)(this + 6424);
                TFlatIsoMessage<LCIE_USERREFRESH>::Post(v69, v68, v66, v67, (__int64)&pidl);
              }
              else if ( a3 == 39 )
              {
                *(_DWORD *)(this + 6456) &= 0xFF9FFFFF;
              }
              return ExtensionCommand;
            }
            if ( CGID_ShellBrowser == *(_QWORD *)v118[0] && *(_QWORD *)v118[0][2].mkid.abID == 0x401B600AA009E96LL )
            {
              ExtensionCommand = 0;
              v70 = a3 - 41092;
              if ( v70 )
              {
                v71 = v70 - 5;
                if ( v71 )
                {
                  v72 = v71 - 7;
                  if ( v72 )
                  {
                    v73 = v72 - 1;
                    if ( v73 )
                    {
                      v74 = v73 - 1;
                      if ( v74 )
                      {
                        v75 = v74 - 1423;
                        if ( v75 )
                        {
                          v76 = v75 - 1;
                          if ( v76 )
                          {
                            if ( v76 == 14 )
                              CShellBrowser2::_OnMouseMove(
                                (CShellBrowser2 *)(this - 40),
                                (int)v118[0],
                                (__int16)HIWORD(pvarg->lVal));
                            else
                              return (unsigned int)-2147221248;
                          }
                          else
                          {
                            v38 = (_DWORD)pidl == 0;
                            *(_BYTE *)(this + 6179) = 0;
                            *(_BYTE *)(this + 6178) = !v38;
                            CBaseBrowser2::_EnsureTabActivityLayeredState((CBaseBrowser2 *)(this - 40));
                          }
                        }
                        else
                        {
                          KillTimer(v63[43], 0x232Eu);
                          if ( *((_DWORD *)v63 + 1556) == 1 )
                          {
                            if ( *((_BYTE *)v63 + 6216) )
                              SetTimer(v63[43], 0x232Fu, 0x7D0u, 0);
                            *((_BYTE *)v63 + 6217) = 1;
                            CBaseBrowser2::_EnsureTabActivityLayeredState((CBaseBrowser2 *)v63);
                            *((_DWORD *)v63 + 1556) = 2;
                            *((_WORD *)v63 + 3114) = 1;
                            if ( !v63[779] )
                            {
                              LODWORD(pidl) = 0;
                              CurrentThreadId = GetCurrentThreadId();
                              if ( (int)LCIEGetTypedComponentFromThread(
                                          0x203u,
                                          CurrentThreadId,
                                          (unsigned int *)&pidl,
                                          0) >= 0 )
                                IsoAddDependency((unsigned int)pidl, (unsigned int)pidl, 1, 57, v63 + 779);
                            }
                          }
                          else
                          {
                            ++*((_WORD *)v63 + 3114);
                          }
                          if ( *((_DWORD *)v63 + 1556) != 2 )
                            KillTimer(v63[43], 0x232Eu);
                        }
                      }
                      else
                      {
                        CShellBrowser2::_RecordLoadedAddon(
                          (CShellBrowser2 *)(this - 40),
                          (const struct _GUID *)pvarg->llVal);
                      }
                    }
                    else if ( pvarg->vt == 23 )
                    {
                      CShellBrowser2::_PostChangeUIState((CShellBrowser2 *)(this - 40), pvarg->cyVal.Lo);
                    }
                  }
                  else
                  {
                    CShellBrowser2::_SaveITbarLayout((CShellBrowser2 *)(this - 40));
                  }
                }
                else if ( pvarg->vt == 3 && (unsigned __int8)IsBrowserFeatureEnabled(512, v118[0], v65, 0) )
                {
                  v78 = pvarg->lVal;
                  *(_DWORD *)(this + 6456) ^= (v78 ^ *(_DWORD *)(this + 6456)) & 1;
                  CLayerParticipant::LayerSetBool((CLayerParticipant *)(this + 192), v78 & 1, 69657, 0);
                  (*((void (__fastcall **)(unsigned __int64, _QWORD))*v63 + 56))(this - 40, 0);
                }
              }
              else if ( a6->vt == 3 )
              {
                a6->lVal = *(_DWORD *)(this + 6456) & 1;
              }
              return ExtensionCommand;
            }
            if ( *(_QWORD *)&CGID_PrivCITCommands.Data1 == *(_QWORD *)v118[0]
              && *(_QWORD *)CGID_PrivCITCommands.Data4 == *(_QWORD *)v118[0][2].mkid.abID )
            {
              v79 = *(_QWORD *)(this + 6488);
              if ( v79 )
                return IUnknown_Exec(v79, v118[0], a3, (_DWORD)pidl, (__int64)pvarg, (__int64)a6);
              return ExtensionCommand;
            }
            if ( *(_QWORD *)&CGID_Explorer.Data1 == *(_QWORD *)v118[0]
              && *(_QWORD *)CGID_Explorer.Data4 == *(_QWORD *)v118[0][2].mkid.abID )
            {
              if ( a3 <= 0x22 )
              {
                switch ( a3 )
                {
                  case 0x22u:
                    if ( pvarg )
                    {
                      if ( pvarg->vt == 13 )
                      {
                        punkVal = pvarg->punkVal;
                        if ( punkVal )
                        {
                          IsSameToolbar = CShellBrowser2::_IsSameToolbar(
                                            (CShellBrowser2 *)(this - 40),
                                            L"BrowserBar",
                                            punkVal);
                          v88 = (CShellBrowser2 *)(this - 40);
                          if ( IsSameToolbar )
                          {
                            v89 = *((_DWORD *)v63 + 1608);
                          }
                          else
                          {
                            v90 = CShellBrowser2::_IsSameToolbar(v88, L"CommBar", pvarg->punkVal);
                            v88 = (CShellBrowser2 *)(this - 40);
                            if ( !v90 )
                            {
                              TBar = CShellBrowser2::_FindTBar(v88, pvarg->punkVal);
                              if ( TBar != -1 )
                              {
                                v92 = *((_QWORD *)v63[841] + 6 * TBar);
                                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v92 + 40LL))(v92, 0);
                              }
                              return 0;
                            }
                            v89 = *((_DWORD *)v63 + 1625);
                          }
                          CShellBrowser2::_SetBrowserBarState(v88, v89, 0, 0, cchBuf, 0, 0);
                        }
                      }
                    }
                    return 0;
                  case 1u:
                    iVal = (__int16)pidl;
                    if ( !(_DWORD)pidl && pvarg && pvarg->vt == 3 )
                    {
                      iVal = pvarg->iVal;
                      lVal_high = (__int16)HIWORD(pvarg->lVal);
                    }
                    else if ( !WORD1(pidl) )
                    {
                      lVal_high = 0;
                    }
                    v85 = CShellBrowser2::v_ShowControl(this - 40, iVal, lVal_high);
                    if ( v85 != -1 && a6 )
                    {
                      a6->vt = 3;
                      a6->lVal = v85;
                    }
                    return 0;
                  case 9u:
                    *(_DWORD *)(this + 6456) |= 0x20u;
                    return 0;
                  case 0x12u:
                    CShellBrowser2::SetMenuSB((CShellBrowser2 *)(this - 40), *(HMENU *)(this + 6336), 0, 0);
                    if ( a6 )
                    {
                      a6->vt = 37;
                      a6->llVal = *(_QWORD *)(this + 6336);
                    }
                    return 0;
                }
                if ( a3 != 29 && a3 != 30 )
                {
                  if ( a3 == 32 )
                  {
                    CShellBrowser2::_SendCurrentPage((CShellBrowser2 *)(this - 40));
                  }
                  else
                  {
                    if ( a3 != 33 )
                      return ExtensionCommand;
                    CShellBrowser2::_SendCurrentPageAsLink((CShellBrowser2 *)(this - 40));
                  }
                  return 0;
                }
                v80 = a3 - 29;
                if ( !v80 )
                {
                  v83 = 41523;
                  goto LABEL_369;
                }
                v81 = v80 - 1;
                if ( !v81 )
                {
                  v83 = 41522;
                  goto LABEL_369;
                }
                v82 = v81 - 17;
                if ( v82 )
                {
                  if ( v82 == 50 )
                  {
LABEL_299:
                    v83 = 41530;
                    goto LABEL_369;
                  }
                  return 0;
                }
LABEL_368:
                v83 = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), &CLSID_DiscussionBand);
                if ( v83 == -1 )
                  return 0;
LABEL_369:
                v104 = 0;
                bstrVal = 0;
                if ( !pvarg )
                  goto LABEL_380;
                if ( (_DWORD)pidl )
                {
                  if ( pvarg->vt != 3 )
                  {
                    if ( pvarg->vt == 8 && pvarg->llVal )
                    {
                      bstrVal = pvarg->bstrVal;
                      goto LABEL_381;
                    }
                    goto LABEL_380;
                  }
                }
                else if ( pvarg->vt != 3 )
                {
                  if ( pvarg->vt == 8 && pvarg->llVal )
                  {
                    v104 = pvarg->bstrVal;
LABEL_381:
                    v118[0] = 0;
                    if ( a6 )
                      VariantToIDList(a6, v118);
                    CShellBrowser2::_SetBrowserBarState((CShellBrowser2 *)v63, v83, 0, lVal_high, cchBuf, v104, bstrVal);
                    ILFree(v118[0]);
                    return 0;
                  }
LABEL_380:
                  lVal_high = -1;
                  goto LABEL_381;
                }
                lVal_high = pvarg->cyVal.Lo;
                goto LABEL_381;
              }
              switch ( a3 )
              {
                case '/':
                  goto LABEL_368;
                case '5':
                  if ( a6 )
                  {
                    a6->vt = 37;
                    a6->llVal = *(_QWORD *)(this + 6328);
                  }
                  return 0;
                case 'L':
                  if ( pvarg && pvarg->vt == 3 && pvarg->lVal > 0 )
                    SendMessageW(*(HWND *)(this + 304), 0x111u, pvarg->uiVal, 0);
                  return 0;
                case 'O':
                  if ( pvarg )
                  {
                    if ( pvarg->vt == 3 )
                    {
                      v103 = pvarg->lVal;
                      if ( v103 > 0 )
                      {
                        pidl = 0;
                        ExtensionCommand = CShellBrowser2::_GetExtensionCommand(
                                             (CShellBrowser2 *)(this - 40),
                                             v103,
                                             (struct IOleCommandTarget **)&pidl);
                        if ( (ExtensionCommand & 0x80000000) == 0 )
                          IUnknown_Exec((_DWORD)pidl, 0, 0, 0, 0, 0);
                        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
                      }
                    }
                  }
                  return ExtensionCommand;
              }
              if ( a3 != 86 )
              {
                if ( a3 != 97 )
                {
                  if ( a3 == 117 )
                  {
                    if ( pvarg )
                    {
                      if ( pvarg->vt == 13 )
                      {
                        llVal = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))pvarg->llVal;
                        if ( llVal )
                        {
                          v118[0] = 0;
                          ExtensionCommand = (**llVal)(llVal, &GUID_5f59b0c4_f563_41f3_b7cb_02ca36c4dbc6, v118);
                          if ( (ExtensionCommand & 0x80000000) == 0 )
                          {
                            v94 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPITEMIDLIST *))(this + 312);
                            pidl = 0;
                            ExtensionCommand = (**v94)(v94, &GUID_79e40311_0a9d_4507_a351_aa290a3e18c5, &pidl);
                            if ( (ExtensionCommand & 0x80000000) == 0 )
                            {
                              if ( (*(_DWORD *)(this + 6456) & 0x10000000) != 0 )
                              {
                                v96 = pidl;
                                v97 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 48LL);
                                HiddenTabCookie = CShellBrowser2::_GetHiddenTabCookie(v95);
                                v99 = v97(v96, this - 40, HiddenTabCookie);
                                *(_DWORD *)(this + 6456) &= ~0x10000000u;
                              }
                              else
                              {
                                v99 = (*(__int64 (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 40LL))(pidl);
                              }
                              ExtensionCommand = v99;
                              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(this - 32) + 144LL))(this - 32);
                            }
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
                          }
                          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(v118);
                        }
                      }
                    }
                  }
                  return ExtensionCommand;
                }
                goto LABEL_299;
              }
              if ( pvarg && pvarg->vt == 8 && *(_QWORD *)(this + 6416) )
              {
                v38 = pvarg->llVal == 0;
                *(_QWORD *)&mii.cbSize = *(_QWORD *)(this + 368);
                *(_QWORD *)&mii.fType = *(_QWORD *)(this + 400);
                v100 = &Default;
                if ( !v38 )
                  v100 = pvarg->bstrVal;
                *(_QWORD *)&mii.wID = v100;
                mii.hSubMenu = (HMENU)psz;
                psz[0] = 0;
                mii.dwItemData = this & -(__int64)(this != 40);
                mii.hbmpChecked = (HBITMAP)260;
                mii.dwTypeData = 0;
                *(_QWORD *)&mii.cch = 0;
                mii.hbmpUnchecked = (HBITMAP)0x100000001LL;
                ExtensionCommand = CreateShortcutInDirEx(&mii);
                if ( (ExtensionCommand & 0x80000000) == 0 )
                {
                  if ( a6 )
                  {
                    *(_OWORD *)&a6->vt = 0;
                    a6->pRecInfo = 0;
                    v101 = SysAllocString(psz);
                    a6->llVal = (LONGLONG)v101;
                    if ( v101 )
                      a6->vt = 8;
                  }
                  if ( (unsigned int)IEConfiguration_GetDWORD(536870929) )
                  {
                    v102 = EfsClientDecryptFile(mii.hSubMenu, 0);
                    ExtensionCommand = v102;
                    if ( v102 > 0 )
                      return (unsigned __int16)v102 | 0x80070000;
                  }
                }
                return ExtensionCommand;
              }
              return (unsigned int)-2147467259;
            }
            if ( *(_QWORD *)&CGID_ShellDocView.Data1 != *(_QWORD *)v118[0]
              || *(_QWORD *)CGID_ShellDocView.Data4 != *(_QWORD *)v118[0][2].mkid.abID )
            {
              if ( *(_QWORD *)&CGID_ExplorerBarDoc.Data1 == *(_QWORD *)v118[0]
                && *(_QWORD *)CGID_ExplorerBarDoc.Data4 == *(_QWORD *)v118[0][2].mkid.abID )
              {
                CShellBrowser2::_ExecAllBands(
                  (CShellBrowser2 *)(this - 40),
                  (const struct _GUID *)v118[0],
                  a3,
                  (unsigned int)pidl,
                  pvarg,
                  a6);
              }
              else if ( *(_QWORD *)&CGID_DocHostCmdPriv.Data1 == *(_QWORD *)v118[0]
                     && *(_QWORD *)CGID_DocHostCmdPriv.Data4 == *(_QWORD *)v118[0][2].mkid.abID )
              {
                if ( a3 == 2 )
                {
                  ExtensionCommand = -2147467259;
                  if ( pvarg->vt == 8 )
                  {
                    v114 = pvarg->llVal;
                    pidl = 0;
                    ExtensionCommand = IEParseDisplayNameWithBCW(0, v114, 0, &pidl);
                    if ( pidl )
                    {
                      ExtensionCommand = (*((__int64 (__fastcall **)(unsigned __int64, LPITEMIDLIST, __int64))*v63 + 11))(
                                           this - 40,
                                           pidl,
                                           1);
                      ILFree(pidl);
                    }
                  }
                }
              }
              else if ( *(_QWORD *)&GUID_a11452bc_e055_4e56_a151_7b16dbb4544e.Data1 == *(_QWORD *)v118[0]
                     && *(_QWORD *)GUID_a11452bc_e055_4e56_a151_7b16dbb4544e.Data4 == *(_QWORD *)v118[0][2].mkid.abID
                     && a3 == 27
                     && pvarg
                     && pvarg->vt == 19 )
              {
                *(_DWORD *)(this + 6804) = pvarg->lVal;
              }
              return ExtensionCommand;
            }
            switch ( a3 )
            {
              case '&':
                CShellBrowser2::_PrepareInternetToolbar((CShellBrowser2 *)(this - 40));
                *(_OWORD *)v118 = 0;
                if ( pvarg->vt == 8 )
                {
                  v111 = pvarg->llVal;
                  if ( !v111 || !(unsigned int)GUIDFromStringW(v111, v118) )
                    return 0;
                  v112 = (const struct _GUID *)v118;
                }
                else
                {
                  if ( pvarg->vt != 37 )
                    return ExtensionCommand;
                  v112 = (const struct _GUID *)pvarg->llVal;
                }
                if ( pvarg->vt != 8
                  || (v113 = *(_QWORD *)(this + 6488)) == 0
                  || (int)IUnknown_Exec(v113, (unsigned int)&CGID_PrivCITCommands, 21, (_DWORD)pidl, (__int64)pvarg, 0) < 0 )
                {
                  CShellBrowser2::_SetBrowserBarState(
                    (CShellBrowser2 *)(this - 40),
                    0xFFFFFFFF,
                    v112,
                    (_DWORD)pidl != 0,
                    cchBuf,
                    0,
                    0);
                }
                return 0;
              case '.':
                if ( (unsigned int)SHIsRestricted2W(*(HWND *)(this + 304)) )
                  return ExtensionCommand;
                v109 = IsOs_Win8OrGreater();
                IELaunchPlatformHelp(v110, !v109 + 18);
                break;
              case '3':
                v108 = pvarg->llVal;
                *(_OWORD *)&mii.cbSize = 0;
                if ( !v108 || !(unsigned int)GUIDFromStringW(v108, &mii) )
                  return (unsigned int)-2147467259;
                a6->vt = 3;
                a6->lVal = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), (const struct _GUID *)&mii);
                break;
              case '8':
                if ( (*(_DWORD *)(this + 6460) || *(_DWORD *)(this + 6392)) && pvarg->vt == 8 )
                {
                  v106 = pvarg->llVal;
                  *(_OWORD *)v118 = 0;
                  if ( v106 )
                  {
                    if ( (unsigned int)GUIDFromStringW(v106, v118) )
                    {
                      v107 = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), (const struct _GUID *)v118);
                      if ( *(_DWORD *)(this + 6460) == v107 || *(_DWORD *)(this + 6392) == v107 )
                        return 0;
                    }
                  }
                }
                return lVal_high;
              case 'L':
                return *(_DWORD *)(this + 6392) == 0;
              default:
                return ExtensionCommand;
            }
            return 0;
          }
LABEL_77:
          v27 = *(_QWORD *)(this + 360);
          if ( !v27 )
            goto LABEL_239;
          v28 = (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD, _QWORD, VARIANTARG *, struct tagVARIANT *))(*(_QWORD *)v27 + 32LL))(
                  v27,
                  &CGID_Explorer,
                  a3,
                  a4,
                  pvarg,
                  a6);
LABEL_121:
          if ( v28 >= 0 )
            return 0;
          goto LABEL_239;
        }
        switch ( a3 )
        {
          case 'W':
            if ( pvarg || !a6 || a6->vt != 37 )
              goto LABEL_239;
            v31 = (HMENU)a6->llVal;
            if ( v31 )
            {
              CShellBrowser2::_AddBrowserBarMenuItems((CShellBrowser2 *)(this - 40), (HMENU)a6->llVal);
              memset_0(&mii, 0, sizeof(mii));
              v32 = *(_DWORD *)(this + 6392);
              mii.cbSize = 80;
              mii.fState = 8;
              mii.fMask = 1;
              SetMenuItemInfoW(v31, v32, 0, &mii);
              SetMenuItemInfoW(v31, *(_DWORD *)(this + 6460), 0, &mii);
            }
            return v31 == 0 ? 0x80004005 : 0;
          case 'Z':
            if ( !pvarg || pvarg->vt != 11 )
              goto LABEL_239;
            v29 = pvarg->iVal;
            *(_DWORD *)(this + 6456) ^= (*(_DWORD *)(this + 6456) ^ (8 * v29)) & 8;
            if ( (v29 & 1) != 0 )
              v30 = *(HMENU *)(this + 6328);
            else
              v30 = 0;
            CShellBrowser2::_SetMenu((CShellBrowser2 *)(this - 40), v30);
            v21 = 69665;
            v22 = (*(_DWORD *)(this + 6456) & 8) != 0;
            break;
          case '[':
          case '_':
            goto LABEL_77;
          case 'b':
LABEL_73:
            v25 = "SBCMDID_CANCELANDFINISH";
            if ( a3 != 98 )
              v25 = "SBCMDID_CANCELANDCLOSE";
            InstrumentationUtils::Printf((InstrumentationUtils *)"CShellBrowser2::Exec - %s", v25, 3, 0);
            goto LABEL_76;
          case 'e':
            mii.cbSize = 0;
            GetBOOL((__int64 *)SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking[0], &mii);
            if ( !mii.cbSize )
            {
              v23 = *(_DWORD *)(this + 6456);
              if ( (a4 & 1) != 0 )
                v24 = v23 | 0x100000;
              else
                v24 = v23 & 0xFFEFFFFF;
              *(_DWORD *)(this + 6456) = v24;
            }
            goto LABEL_239;
          default:
            if ( a3 != 102 || !pvarg || pvarg->vt != 11 )
              goto LABEL_239;
            v21 = 69639;
            v22 = pvarg->iVal == 0xFFFF;
            break;
        }
        CLayerParticipant::LayerSetBool((CLayerParticipant *)(this + 192), v22, v21, 0);
        goto LABEL_239;
      }
      if ( a3 > 0x78 )
      {
        switch ( a3 )
        {
          case 0x79u:
            if ( pvarg && pvarg->vt == 11 )
            {
              *(_DWORD *)(this + 6456) = *(_DWORD *)(this + 6456) & 0xBFFFFFFF | (pvarg->iVal == 0 ? 0x40000000 : 0);
              return 0;
            }
            goto LABEL_239;
          case 0x7Au:
            if ( a6 && a6->vt == 11 )
            {
              a6->iVal = -((*(_DWORD *)(this + 6456) & 0x40000000) != 0);
              return 0;
            }
            goto LABEL_239;
          case 0x7Cu:
            CShellBrowser2::_CorrelatedVtabClose((CShellBrowser2 *)(this - 40), pvarg);
            return 0;
          case 0x81u:
            CShellBrowser2::_SendImageCookieToFrame((CShellBrowser2 *)(this - 40), pvarg);
            goto LABEL_239;
          case 0x82u:
            LCIE2ChangeComponentSharedFlagBit(*(_DWORD *)(this + 6304), 1, 6u);
            CurrentProcessManager = IsoGetCurrentProcessManager();
            LCIEChangeComponentSharedFlagBit(CurrentProcessManager, 1, 0);
            LCIEPostMessageWithoutBuffer(*(_DWORD *)(this + 6308), *(_DWORD *)(this + 6304), 0xD57u, 0);
            *(_DWORD *)(this + 6456) |= 0x80000u;
            *(_BYTE *)(this + 6928) = 1;
            goto LABEL_239;
        }
        if ( a3 - 137 > 1 )
          goto LABEL_239;
        v26 = 1;
LABEL_76:
        CShellBrowser2::_CancelAndClose((CShellBrowser2 *)(this - 40), pvarg, 0, v26);
        return 0;
      }
      if ( a3 != 120 )
      {
        switch ( a3 )
        {
          case 'i':
            if ( !pvarg || pvarg->vt == 3 )
            {
              v35 = *(_DWORD *)(this + 6312);
              LODWORD(pidl) = 0;
              *(_QWORD *)&mii.cbSize = 0;
              if ( (int)IsoAllocMessageBuffer(v35, (unsigned int *)&pidl, 0x24u, (struct _IsoMessage **)&mii) >= 0 )
              {
                *(_DWORD *)(*(_QWORD *)&mii.cbSize + 32LL) = pvarg ? pvarg->lVal : TLSGetTabId();
                if ( (int)LCIEPostMessage(
                            *(_DWORD *)(this + 6312),
                            *(_DWORD *)(this + 6304),
                            0xC14u,
                            0,
                            (unsigned int)pidl) < 0 )
                  IsoRemoveArtifact((unsigned int)pidl);
              }
            }
            return 0;
          case 'j':
            v34 = *(_QWORD *)(this + 360);
            if ( !v34 )
              goto LABEL_239;
            v28 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL))(
                    v34,
                    &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                    9,
                    0,
                    0,
                    0);
            goto LABEL_121;
          case 'k':
            if ( !LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
              GetVirtualTabIDAndBrowserFrameHwndFromIsoComponent((int *)(this + 6912), 0);
            return 0;
          case 'l':
            if ( a6 )
            {
              a6->vt = 3;
              a6->lVal = *(_DWORD *)(this + 6912);
            }
            return 0;
          case 'q':
            if ( pvarg )
            {
              if ( pvarg->vt == 11 )
              {
                *(_BYTE *)(this - 40 + 506) = pvarg->iVal == 0xFFFF;
                if ( !*(_QWORD *)(this + 416) )
                  (*(void (__fastcall **)(unsigned __int64, ITEMIDLIST *, __int64, _QWORD))(*(_QWORD *)(this - 40)
                                                                                          + 480LL))(
                    this - 40,
                    a2,
                    3,
                    0);
              }
            }
            return 0;
          case 's':
            if ( !pvarg )
            {
              if ( a6 )
              {
                if ( a6->vt == 37 )
                {
                  if ( a6->llVal )
                  {
                    v33 = *(HWND *)(this + 6536);
                    memset(&mii, 0, 44);
                    mii.cbSize = 44;
                    if ( GetWindowPlacement(v33, (WINDOWPLACEMENT *)&mii) )
                    {
                      GetFullScreenRect((struct tagRECT *)((char *)&mii.hSubMenu + 4), (struct tagRECT *)a6->llVal);
                      return 0;
                    }
                  }
                }
              }
            }
            break;
          case 't':
            CShellBrowser2::_PrepareInternetToolbar((CShellBrowser2 *)(this - 40));
            return 0;
          case 'w':
            return CShellBrowser2::_CheckHostCandidacy((CShellBrowser2 *)(this - 40), pvarg, a6);
        }
        goto LABEL_239;
      }
      if ( !a6 )
        goto LABEL_239;
      if ( !*(_QWORD *)(this + 6880) )
      {
        a6->vt = 1;
        return 0;
      }
      a6->vt = 8;
      v36 = SysAllocString(*(const OLECHAR **)(this + 6880));
LABEL_135:
      a6->llVal = (LONGLONG)v36;
      return 0;
    }
    if ( CGID_MenuBandHandler == *(_QWORD *)&a2->mkid.cb && *(_QWORD *)a2[2].mkid.abID == 0xF5E26C00AA0059BCuLL )
    {
      if ( a3 )
        goto LABEL_239;
      pidl = 0;
      if ( !pvarg || (int)VariantToIDList(pvarg, &pidl) < 0 )
        return 0;
      if ( !(unsigned int)ILIsEmpty((const struct _ITEMIDLIST_RELATIVE *)pidl) )
      {
        if ( *(_QWORD *)(this + 6512) )
          KillTimer(*(HWND *)(this + 304), 0x64u);
        if ( (unsigned int)Pidl_Set(this + 6512, pidl) && !SetTimer(*(HWND *)(this + 304), 0x64u, 0x1F4u, 0) )
          Pidl_Set(this + 6512, 0);
      }
      goto LABEL_163;
    }
    if ( *(_QWORD *)&CLSID_IE_MenuBand.Data1 == *(_QWORD *)&a2->mkid.cb
      && *(_QWORD *)CLSID_IE_MenuBand.Data4 == *(_QWORD *)a2[2].mkid.abID )
    {
      if ( a3 == 9 )
      {
        if ( *(_QWORD *)(this + 6512) )
          KillTimer(*(HWND *)(this + 304), 0x64u);
        return 0;
      }
      goto LABEL_239;
    }
    if ( *(_QWORD *)&CGID_ShellDocView.Data1 != *(_QWORD *)&a2->mkid.cb
      || *(_QWORD *)CGID_ShellDocView.Data4 != *(_QWORD *)a2[2].mkid.abID )
    {
      goto LABEL_239;
    }
    if ( a3 > 0x7A )
    {
      if ( a3 > 0x9D )
      {
        if ( a3 == 158 )
        {
          v62 = *(_QWORD *)(this + 6648);
          if ( v62 )
            (*(void (__fastcall **)(__int64, VARIANTARG *, __int64, _QWORD))(*(_QWORD *)v62 + 32LL))(v62, pvarg, 3, 0);
        }
        else
        {
          if ( a3 != 161 && a3 != 162 )
          {
            if ( a3 == 181 )
            {
              v53 = TLSGetTabId();
              v55 = 42;
            }
            else
            {
              if ( a3 != 182 )
              {
                if ( a3 == 183 )
                {
                  v50 = *(struct IUnknown **)(this + 336);
                  *(_QWORD *)&mii.cbSize = 0;
                  GetTopWBConnectionPoints(v50, (struct IConnectionPoint **)&mii, 0);
                  v51 = TLSGetTabId();
                  TryLogHttpStatusCodeChange(
                    v51,
                    v52,
                    *(HWND *)(this + 6536),
                    *(struct IWebBrowser2 **)(this + 328),
                    (LONG)pvarg);
                  ATL::CComPtr<IConnectionPoint>::~CComPtr<IConnectionPoint>(&mii);
                }
                goto LABEL_239;
              }
              v53 = TLSGetTabId();
              v55 = 43;
            }
            LOBYTE(v54) = 1;
            CSuggestedSites::LogSuggestedSitesUIEvent(v53, *(_QWORD *)(this + 6536), v55, v54);
            goto LABEL_239;
          }
          LOBYTE(mii.cbSize) = 0;
          if ( CSuggestedSites::IsDataStreamEnabledCached()
            && (int)OnlineHistorySettings::IsDataStreamEnabledCached((bool *)&mii) >= 0 )
          {
            if ( LOBYTE(mii.cbSize) )
            {
              if ( pvarg )
              {
                if ( pvarg->vt == 13 )
                {
                  v56 = (int (__fastcall ***)(_QWORD, GUID *, MENUITEMINFOW *))pvarg->llVal;
                  if ( v56 )
                  {
                    v57 = *v56;
                    *(_QWORD *)&mii.cbSize = 0;
                    if ( (*v57)(v56, &GUID_57440f87_4899_4a16_9168_0466e43a4a48, &mii) >= 0 )
                    {
                      v58 = TLSGetTabId();
                      CSuggestedSites::LogSuggestedSitesUIEventNavElementNoCheck(
                        v58,
                        *(HWND *)(this + 6536),
                        *(struct IElementDOMInfo **)&mii.cbSize,
                        a3 == 162);
                      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)&mii.cbSize + 16LL))(
                        *(_QWORD *)&mii.cbSize,
                        v59,
                        v60,
                        v61);
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_239;
      }
      if ( a3 == 157 )
      {
        v49 = *(_QWORD *)(this + 6648);
        if ( v49 )
          (*(void (__fastcall **)(__int64, ITEMIDLIST *, __int64, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, a2, 3, 0);
        goto LABEL_239;
      }
      if ( a3 != 123 && a3 != 127 )
      {
        switch ( a3 )
        {
          case 0x81u:
            v48 = *(_QWORD *)(this - 40);
            memset(&mii, 0, 24);
            v46 = (*(__int64 (__fastcall **)(unsigned __int64, ITEMIDLIST *, __int64, _QWORD))(v48 + 504))(
                    this - 40,
                    a2,
                    3,
                    0);
            v47 = 2005;
            break;
          case 0x83u:
            goto LABEL_211;
          case 0x89u:
            CShellBrowser2::OnBrowserNavigateComplete2((CShellBrowser2 *)(this - 40));
            goto LABEL_239;
          case 0x8Au:
            v45 = *(_QWORD *)(this - 40);
            memset(&mii, 0, 24);
            v46 = (*(__int64 (__fastcall **)(unsigned __int64, ITEMIDLIST *, __int64, _QWORD))(v45 + 504))(
                    this - 40,
                    a2,
                    3,
                    0);
            v47 = 2006;
            break;
          default:
            v42 = a3 == 156;
LABEL_210:
            if ( !v42 )
              goto LABEL_239;
            goto LABEL_211;
        }
        LCIEPostDispatchEvent(
          *(_DWORD *)(this + 6312),
          v47,
          (struct tagDISPPARAMS *)&mii,
          *(HWND *)(this + 6536),
          v46,
          v116);
        goto LABEL_239;
      }
    }
    else
    {
      if ( a3 == 122 )
        goto LABEL_211;
      if ( a3 > 0x68 )
      {
        if ( a3 == 108 || a3 == 109 || a3 == 110 )
          goto LABEL_211;
        if ( a3 == 111 )
        {
          if ( pvarg->vt != 3 )
            goto LABEL_239;
          v43 = pvarg->lVal;
          if ( v43 <= 0 || a4 != 1 || !a6 )
            goto LABEL_239;
          v36 = (BSTR)CShellBrowser2::_MenuPopulateToolbars((CShellBrowser2 *)(this - 40), v43);
          a6->vt = 37;
          goto LABEL_135;
        }
        v39 = a3 - 118;
        v38 = a3 == 118;
      }
      else
      {
        switch ( a3 )
        {
          case 0x68u:
            goto LABEL_211;
          case 1u:
          case 2u:
          case 0x11u:
          case 0x32u:
            if ( pvarg )
            {
              if ( pvarg->vt == 3 && pvarg->lVal == -5501 )
              {
                v40 = *(_QWORD *)(this + 328);
                LOWORD(mii.cbSize) = 0;
                if ( v40 )
                {
                  if ( (*(int (__fastcall **)(__int64, MENUITEMINFOW *, __int64, _QWORD))(*(_QWORD *)v40 + 456LL))(
                         v40,
                         &mii,
                         3,
                         0) >= 0 )
                  {
                    v41 = (CShellBrowser2 *)(this - 40);
                    if ( LOWORD(mii.cbSize) )
                      CShellBrowser2::_DecrNetSessionCount(v41);
                    else
                      CShellBrowser2::_IncrNetSessionCount(v41);
                  }
                }
              }
            }
            goto LABEL_239;
          case 0x61u:
            goto LABEL_211;
        }
        v39 = a3 - 98;
        v38 = a3 == 98;
      }
      if ( !v38 )
      {
        v42 = v39 == 1;
        goto LABEL_210;
      }
    }
LABEL_211:
    v44 = *(_QWORD *)(this + 360);
    if ( v44 )
      return (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD, _QWORD, VARIANTARG *, struct tagVARIANT *))(*(_QWORD *)v44 + 32LL))(
               v44,
               &CGID_ShellDocView,
               a3,
               a4,
               pvarg,
               a6);
    goto LABEL_239;
  }
  if ( a3 != 10 && a3 != 11 && a3 != 12 && a3 != 13 && a3 != 33 )
  {
    if ( a3 == 45 && IsDualEngineProcess() )
    {
      v10 = 1;
      v11 = 33192;
LABEL_10:
      PostMessageW(*(HWND *)(this + 304), v11, v10, 0);
      return 0;
    }
    goto LABEL_239;
  }
  if ( !(unsigned int)CShellBrowser2::_HasToolbarFocus((CShellBrowser2 *)(this - 40)) )
    goto LABEL_239;
  v13 = (_QWORD *)(*(_QWORD *)(this + 6688) + 48LL * *(int *)(this + 6800));
  if ( !v13 )
    goto LABEL_239;
  result = IUnknown_Exec(*v13, 0, a3, a4, (__int64)pvarg, (__int64)a6);
  if ( (int)result < 0 )
    goto LABEL_239;
  return result;
}

```

## disassembly

```asm
0x180073110  push    rbp
0x180073112  push    rbx
0x180073113  push    rsi
0x180073114  push    rdi
0x180073115  push    r12
0x180073117  push    r13
0x180073119  push    r14
0x18007311b  push    r15
0x18007311d  lea     rbp, [rsp-1228h]
0x180073125  mov     eax, 1328h
0x18007312a  call    _alloca_probe
0x18007312f  sub     rsp, rax
0x180073132  mov     rax, cs:__security_cookie
0x180073139  xor     rax, rsp
0x18007313c  mov     [rbp+1260h+var_50], rax
0x180073143  mov     r12, [rbp+1260h+arg_28]
0x18007314a  mov     rsi, rcx
0x18007314d  mov     rbx, [rbp+1260h+pvarg]
0x180073154  mov     ecx, 0Bh
0x180073159  mov     r14d, r9d
0x18007315c  or      edi, 0FFFFFFFFh
0x18007315f  xor     r9d, r9d
0x180073162  mov     dword ptr [rsp+1360h+pidl], r14d
0x180073167  mov     [rsp+1360h+var_1318], rdx
0x18007316c  mov     r15d, r8d
0x18007316f  lea     r13d, [rcx-0Ah]
0x180073173  lea     r10d, [rcx-3]
0x180073177  lea     r11d, [rcx+1Ah]
0x18007317b  lea     r8d, [rcx-8]
0x18007317f  test    rdx, rdx
0x180073182  jnz     loc_18007323A
0x180073188  mov     eax, r15d
0x18007318b  sub     eax, 0Ah
0x18007318e  jz      short loc_1800731E6
0x180073190  sub     eax, r13d
0x180073193  jz      short loc_1800731E6
0x180073195  sub     eax, r13d
0x180073198  jz      short loc_1800731E6
0x18007319a  sub     eax, r13d
0x18007319d  jz      short loc_1800731E6
0x18007319f  sub     eax, 14h
0x1800731a2  jz      short loc_1800731E6
0x1800731a4  cmp     eax, 0Ch
0x1800731a7  jnz     loc_180073FBD
0x1800731ad  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800731b4  nop     dword ptr [rax+rax+00h]
0x1800731b9  test    al, al
0x1800731bb  jz      loc_180073FBD
0x1800731c1  mov     r8d, r13d; wParam
0x1800731c4  mov     edx, 81A8h; Msg
0x1800731c9  mov     rcx, [rsi+130h]; hWnd
0x1800731d0  xor     r9d, r9d; lParam
0x1800731d3  call    cs:__imp_PostMessageW
0x1800731da  nop     dword ptr [rax+rax+00h]
0x1800731df  xor     eax, eax
0x1800731e1  jmp     loc_180074C5B
0x1800731e6  lea     rcx, [rsi-28h]; this
0x1800731ea  call    ?_HasToolbarFocus@CShellBrowser2@@AEAAHXZ; CShellBrowser2::_HasToolbarFocus(void)
0x1800731ef  test    eax, eax
0x1800731f1  jz      loc_180073FBD
0x1800731f7  movsxd  rax, dword ptr [rsi+1A90h]
0x1800731fe  lea     rcx, [rax+rax*2]
0x180073202  shl     rcx, 4
0x180073206  add     rcx, [rsi+1A20h]
0x18007320d  jz      loc_180073FBD
0x180073213  mov     rcx, [rcx]
0x180073216  mov     r9d, r14d
0x180073219  mov     [rsp+1360h+var_1338], r12
0x18007321e  mov     r8d, r15d
0x180073221  xor     edx, edx
0x180073223  mov     qword ptr [rsp+1360h+cchBuf], rbx
0x180073228  call    IUnknown_Exec
0x18007322d  test    eax, eax
0x18007322f  js      loc_180073FBD
0x180073235  jmp     loc_180074C5B
0x18007323a  mov     rax, qword ptr cs:CGID_Explorer.Data1
0x180073241  cmp     rax, [rdx]
0x180073244  jnz     loc_180073AC9
0x18007324a  mov     rax, qword ptr cs:CGID_Explorer.Data4
0x180073251  cmp     rax, [rdx+8]
0x180073255  jnz     loc_180073AC9
0x18007325b  cmp     r15d, 68h ; 'h'
0x18007325f  ja      loc_1800736ED
0x180073265  jz      loc_1800736DC
0x18007326b  cmp     r15d, 50h ; 'P'
0x18007326f  ja      loc_1800734C8
0x180073275  jz      loc_18007359D
0x18007327b  mov     eax, r15d
0x18007327e  sub     eax, 2
0x180073281  jz      loc_1800733E4
0x180073287  sub     eax, 6
0x18007328a  jz      loc_18007359D
0x180073290  sub     eax, 31h ; '1'
0x180073293  jz      loc_1800733D1
0x180073299  sub     eax, r13d
0x18007329c  jz      loc_18007338F
0x1800732a2  sub     eax, 4
0x1800732a5  jz      loc_180073567
0x1800732ab  sub     eax, r10d
0x1800732ae  jz      short loc_18007332E
0x1800732b0  sub     eax, r13d
0x1800732b3  jz      short loc_18007330A
0x1800732b5  cmp     eax, r13d
0x1800732b8  jnz     loc_180073FBD
0x1800732be  mov     ecx, [rbx+8]; unsigned int
0x1800732c1  lea     rdx, [rsp+1360h+pidl]; struct IBrowserAsyncPackage **
0x1800732c6  mov     [rsp+1360h+pidl], r9
0x1800732cb  call    ?CBrowserWinMsgPackage_GetInstance@@YAJKPEAPEAUIBrowserAsyncPackage@@@Z; CBrowserWinMsgPackage_GetInstance(ulong,IBrowserAsyncPackage * *)
0x1800732d0  xorps   xmm0, xmm0
0x1800732d3  movups  xmmword ptr [rbx], xmm0
0x1800732d6  test    eax, eax
0x1800732d8  js      short loc_1800732FF
0x1800732da  xor     eax, eax
0x1800732dc  lea     rcx, [rsi-28h]; this
0x1800732e0  mov     [rbx+10h], rax
0x1800732e4  mov     rdx, rbx; pvarg
0x1800732e7  mov     rax, [rsp+1360h+pidl]
0x1800732ec  mov     [rbx+8], rax
0x1800732f0  mov     word ptr [rbx], 0Dh
0x1800732f5  call    ?_ProcessTranslateAccAsync@CShellBrowser2@@AEAAJPEAUtagVARIANT@@@Z; CShellBrowser2::_ProcessTranslateAccAsync(tagVARIANT *)
0x1800732fa  jmp     loc_180074C5B
0x1800732ff  xor     eax, eax
0x180073301  mov     [rbx+10h], rax
0x180073305  jmp     loc_180074C5B
0x18007330a  mov     r9, [rbx+8]; lParam
0x18007330e  mov     r8, r14; wParam
0x180073311  mov     rcx, [rsi+130h]; hWnd
0x180073318  mov     edx, 1Ah; Msg
0x18007331d  call    cs:__imp_SendMessageW
0x180073324  nop     dword ptr [rax+rax+00h]
0x180073329  jmp     loc_1800731DF
0x18007332e  mov     [rsp+1360h+pidl], r9
0x180073333  test    rbx, rbx
0x180073336  jz      loc_1800731DF
0x18007333c  lea     rdx, [rsp+1360h+pidl]
0x180073341  mov     rcx, rbx
0x180073344  call    VariantToIDList
0x180073349  xor     ebx, ebx
0x18007334b  test    eax, eax
0x18007334d  js      loc_1800731DF
0x180073353  test    r12, r12
0x180073356  jz      loc_1800731DF
0x18007335c  lea     ecx, [rbx+0Bh]
0x18007335f  cmp     [r12], cx
0x180073364  jnz     loc_1800731DF
0x18007336a  mov     rcx, [rsp+1360h+pidl]
0x18007336f  xor     edx, edx
0x180073371  mov     [r12+8], bx
0x180073377  call    TryIEShellDelegation
0x18007337c  test    eax, eax
0x18007337e  jz      loc_180073B8A
0x180073384  mov     [r12+8], di
0x18007338a  jmp     loc_180073B8A
0x18007338f  lea     rcx, [rsi-28h]; this
0x180073393  mov     [rsp+1360h+pidl], r9
0x180073398  lea     rdx, [rsp+1360h+pidl]; struct IBrowserFrame **
0x18007339d  call    ?_GetBrowserFrame@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrame@@@Z; CShellBrowser2::_GetBrowserFrame(IBrowserFrame * *)
0x1800733a2  xor     ebx, ebx
0x1800733a4  test    eax, eax
0x1800733a6  js      short loc_1800733BF
0x1800733a8  mov     rcx, [rsp+1360h+pidl]
0x1800733ad  mov     rax, [rcx]
0x1800733b0  mov     rax, [rax+48h]
0x1800733b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733b9  test    eax, eax
0x1800733bb  cmovns  r13d, ebx
0x1800733bf  lea     rcx, [rsp+1360h+pidl]; void *
0x1800733c4  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800733c9  mov     eax, r13d
0x1800733cc  jmp     loc_180074C5B
0x1800733d1  mov     eax, [rsi+2BCh]
0x1800733d7  shr     eax, 14h
0x1800733da  not     eax
0x1800733dc  and     eax, r13d
0x1800733df  jmp     loc_180074C5B
0x1800733e4  mov     edx, 824h
0x1800733e9  lea     rax, [rbp+1260h+pszFirst]
0x1800733f0  mov     ecx, edx
0x1800733f2  mov     [rax], r9b
0x1800733f5  add     rax, r13
0x1800733f8  sub     rcx, r13
0x1800733fb  jnz     short loc_1800733F2
0x1800733fd  mov     rcx, [rsi+170h]; int
0x180073404  mov     r14b, r9b
0x180073407  test    rcx, rcx
0x18007340a  jz      short loc_180073461
0x18007340c  mov     [rsp+1360h+var_1338], r9; __int64
0x180073411  xor     r8d, r8d; int
0x180073414  mov     [rsp+1360h+cchBuf], edx; cchBuf
0x180073418  lea     r9, [rbp+1260h+pszFirst]; int
0x18007341f  mov     edx, 8000h; int
0x180073424  call    IEGetNameAndFlagsEx
0x180073429  xor     r9d, r9d
0x18007342c  test    eax, eax
0x18007342e  js      short loc_18007345B
0x180073430  lea     rdx, aMicrosoftEdge; "microsoft-edge"
0x180073437  lea     rcx, [rbp+1260h+pszFirst]; pszFirst
0x18007343e  call    cs:__imp_StrStrIW
0x180073445  nop     dword ptr [rax+rax+00h]
0x18007344a  lea     rcx, [rbp+1260h+pszFirst]
0x180073451  cmp     rcx, rax
0x180073454  setz    r14b
0x180073458  xor     r9d, r9d
0x18007345b  mov     r8d, 3
0x180073461  cmp     [rsi+170h], r9
0x180073468  jz      short loc_180073473
0x18007346a  test    r14b, r14b
0x18007346d  jz      loc_180073FBD
0x180073473  test    rbx, rbx
0x180073476  jz      loc_180073FBD
0x18007347c  cmp     [rbx], r8w
0x180073480  jnz     loc_180073FBD
0x180073486  cmp     [rbx+8], r9d
0x18007348a  jnz     loc_180073FBD
0x180073490  lea     rcx, [rsi-28h]; this
0x180073494  call    ?_CancelPendingNavigationAsync@CBaseBrowser2@@IEAAJXZ; CBaseBrowser2::_CancelPendingNavigationAsync(void)
0x180073499  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800734a0  nop     dword ptr [rax+rax+00h]
0x1800734a5  test    al, al
0x1800734a7  jz      short loc_1800734BC
0x1800734a9  mov     r8b, r13b; bool
0x1800734ac  lea     rcx, [rsi-28h]; this
0x1800734b0  xor     edx, edx; bool
0x1800734b2  call    ?_DualEngineOnDeferredCloseCommand@CShellBrowser2@@AEAAX_N0@Z; CShellBrowser2::_DualEngineOnDeferredCloseCommand(bool,bool)
0x1800734b7  jmp     loc_1800731DF
0x1800734bc  xor     r8d, r8d
0x1800734bf  lea     edx, [r8+10h]
0x1800734c3  jmp     loc_1800731C9
0x1800734c8  mov     eax, r15d
0x1800734cb  sub     eax, 57h ; 'W'
0x1800734ce  jz      loc_180073639
0x1800734d4  sub     eax, r8d
0x1800734d7  jz      loc_1800735C9
0x1800734dd  sub     eax, r13d
0x1800734e0  jz      loc_18007359D
0x1800734e6  sub     eax, 4
0x1800734e9  jz      loc_18007359D
0x1800734ef  sub     eax, r8d
0x1800734f2  jz      short loc_180073567
0x1800734f4  sub     eax, r8d
0x1800734f7  jz      short loc_180073526
0x1800734f9  cmp     eax, r13d
0x1800734fc  jnz     loc_180073FBD
0x180073502  test    rbx, rbx
0x180073505  jz      loc_180073FBD
0x18007350b  cmp     [rbx], cx
0x18007350e  jnz     loc_180073FBD
0x180073514  cmp     [rbx+8], di
0x180073518  mov     r8d, 11007h
0x18007351e  setz    dl
0x180073521  jmp     loc_180073628
0x180073526  mov     rcx, cs:?IEVALUE_PrivacIE_DisableInPrivateBlocking@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking
0x18007352d  lea     rdx, [rsp+1360h+mii]
0x180073532  mov     [rsp+1360h+mii.cbSize], r9d
0x180073537  call    GetBOOL
0x18007353c  cmp     [rsp+1360h+mii.cbSize], 0
0x180073541  jnz     loc_180073FBD
0x180073547  mov     eax, [rsi+1938h]
0x18007354d  test    r13b, r14b
0x180073550  jz      short loc_180073561
0x180073552  bts     eax, 14h
0x180073556  mov     [rsi+1938h], eax
0x18007355c  jmp     loc_180073FBD
0x180073561  btr     eax, 14h
0x180073565  jmp     short loc_180073556
0x180073567  cmp     r15d, 62h ; 'b'
0x18007356b  lea     rax, aSbcmdidCancela; "SBCMDID_CANCELANDCLOSE"
0x180073572  lea     rdx, aSbcmdidCancela_0; "SBCMDID_CANCELANDFINISH"
0x180073579  cmovnz  rdx, rax; char *
0x18007357d  lea     rcx, aCshellbrowser2; "CShellBrowser2::Exec - %s"
0x180073584  call    ?Printf@InstrumentationUtils@@YAJPEBDZZ; InstrumentationUtils::Printf(char const *,...)
0x180073589  lea     rcx, [rsi-28h]; this
0x18007358d  xor     r8d, r8d; unsigned int
0x180073590  mov     rdx, rbx; struct tagVARIANT *
0x180073593  call    ?_CancelAndClose@CShellBrowser2@@AEAAXPEAUtagVARIANT@@K_N@Z; CShellBrowser2::_CancelAndClose(tagVARIANT *,ulong,bool)
0x180073598  jmp     loc_1800731DF
0x18007359d  mov     rcx, [rsi+168h]
0x1800735a4  test    rcx, rcx
0x1800735a7  jz      loc_180073FBD
0x1800735ad  mov     [rsp+1360h+var_1338], r12
0x1800735b2  lea     rdx, CGID_Explorer
0x1800735b9  mov     qword ptr [rsp+1360h+cchBuf], rbx
0x1800735be  mov     r9d, r14d
0x1800735c1  mov     r8d, r15d
0x1800735c4  jmp     loc_18007388D
0x1800735c9  test    rbx, rbx
0x1800735cc  jz      loc_180073FBD
0x1800735d2  cmp     [rbx], cx
0x1800735d5  jnz     loc_180073FBD
0x1800735db  movsx   edx, word ptr [rbx+8]
0x1800735df  mov     ecx, [rsi+1938h]
0x1800735e5  lea     eax, ds:0[rdx*8]
0x1800735ec  xor     eax, ecx
0x1800735ee  and     eax, r10d
0x1800735f1  xor     eax, ecx
0x1800735f3  mov     [rsi+1938h], eax
0x1800735f9  test    r13b, dl
0x1800735fc  jz      short loc_180073607
0x1800735fe  mov     rdx, [rsi+18B8h]
0x180073605  jmp     short loc_18007360A
  ... truncated ...
```
