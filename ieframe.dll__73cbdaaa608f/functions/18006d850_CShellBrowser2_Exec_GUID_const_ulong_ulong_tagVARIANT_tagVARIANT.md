# CShellBrowser2::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x18006d850`
- end: `0x18006f2f6`
- name: `?Exec@CShellBrowser2@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `6822`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, const struct _GUID *, unsigned int, unsigned int, VARIANTARG *pvarg, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `70`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18002320c`
- `0x180030340`
- `0x18004a080`
- `0x18004b560`
- `0x18006c684`
- `0x18006d850`
- `0x18006f940`
- `0x180075370`
- `0x1800766c8`
- `0x18007f1c8`
- `0x18007fe04`
- `0x1800800e0`
- `0x180085394`
- `0x180095c40`
- `0x1800a464c`
- `0x1800b3328`
- `0x1800c83cc`
- `0x1800c9f70`
- `0x1800f6730`
- `0x1801a3f80`
- `0x1801c107c`
- `0x1801c10b0`
- `0x1801c10fc`
- `0x1801cb790`
- `0x1801d8980`
- `0x1801da054`
- `0x1801db1bc`
- `0x1801dd940`
- `0x1801de8f0`
- `0x1801e0804`
- `0x1801e09b0`
- `0x1801e1110`
- `0x1801e1e50`
- `0x1801e2c88`
- `0x1801e3374`
- `0x1801e345c`
- `0x1801e363c`
- `0x1801e3fcc`
- `0x1801e412c`
- `0x1801e42c0`
- `0x1801e4548`
- `0x1801e4590`
- `0x1801e45c4`
- `0x1801e5abc`
- `0x1801e6114`
- `0x1801e943c`
- `0x1801e9640`
- `0x1801e9908`
- `0x1801ea454`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18006e8a2`
- `KERNEL32!GetCurrentThreadId` at `0x18006e8a2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x18006db6c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x18006db6c`
- `USER32!SetMenuItemInfoW` at `0x18006ddc4`
- `USER32!SetMenuItemInfoW` at `0x18006dddb`
- `USER32!SetMenuItemInfoW` at `0x18006ddc4`
- `USER32!SetMenuItemInfoW` at `0x18006dddb`
- `USER32!SetTimer` at `0x18006e245`
- `USER32!SetTimer` at `0x18006e86a`
- `USER32!SetTimer` at `0x18006e245`
- `USER32!SetTimer` at `0x18006e86a`
- `USER32!KillTimer` at `0x18006e218`
- `USER32!KillTimer` at `0x18006e2a5`
- `USER32!KillTimer` at `0x18006e838`
- `USER32!KillTimer` at `0x18006e8fd`
- `USER32!KillTimer` at `0x18006e218`
- `USER32!KillTimer` at `0x18006e2a5`
- `USER32!KillTimer` at `0x18006e838`
- `USER32!KillTimer` at `0x18006e8fd`
- `USER32!GetWindowPlacement` at `0x18006dec6`
- `USER32!GetWindowPlacement` at `0x18006dec6`
- `USER32!PostMessageW` at `0x18006d90d`
- `USER32!PostMessageW` at `0x18006d90d`
- `USER32!SendMessageW` at `0x18006da51`
- `USER32!SendMessageW` at `0x18006eef6`
- `USER32!SendMessageW` at `0x18006da51`
- `USER32!SendMessageW` at `0x18006eef6`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e06e`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ee06`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e06e`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ee06`
- `SHELL32!__imp_ILFree` at `0x18006e25f`
- `SHELL32!__imp_ILFree` at `0x18006efcc`
- `SHELL32!__imp_ILFree` at `0x18006f293`
- `SHELL32!__imp_ILFree` at `0x18006e25f`
- `SHELL32!__imp_ILFree` at `0x18006efcc`
- `SHELL32!__imp_ILFree` at `0x18006f293`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18006ee20`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18006ee20`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18006d8ed`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18006dbc1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18006d8ed`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18006dbc1`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18006e8b7`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18006e8b7`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18006e029`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18006e029`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18006e0fa`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18006e0fa`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18006e0df`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18006e0df`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18006df4f`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18006df4f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18006e03b`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18006e03b`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18006dfdf`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18006dfdf`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18006e0d1`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18006e0d1`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x18006e8d5`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x18006e8d5`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18006e0cb`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18006e0cb`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x18006ee35`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x18006ee35`

## string_xrefs

- `0x18006ebce`: `CommBar`

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
  ITEMIDLIST *v38; // rcx
  bool v39; // zf
  unsigned int v40; // eax
  __int64 v41; // rcx
  CShellBrowser2 *v42; // rcx
  bool v43; // zf
  LONG v44; // edx
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned int v47; // eax
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rcx
  struct IUnknown *v51; // rcx
  unsigned int v52; // eax
  bool v53; // r10
  unsigned int v54; // eax
  __int64 v55; // r9
  __int64 v56; // r8
  int (__fastcall ***v57)(_QWORD, GUID *, MENUITEMINFOW *); // rcx
  int (__fastcall **v58)(_QWORD, GUID *, MENUITEMINFOW *); // rax
  unsigned int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rcx
  HWND *v64; // r14
  unsigned int ExtensionCommand; // edi
  __int64 v66; // r8
  int v67; // r8d
  int v68; // r9d
  int v69; // edx
  int v70; // ecx
  unsigned int v71; // r15d
  unsigned int v72; // r15d
  unsigned int v73; // r15d
  unsigned int v74; // r15d
  unsigned int v75; // r15d
  unsigned int v76; // r15d
  unsigned int v77; // r15d
  DWORD CurrentThreadId; // eax
  LONG v79; // edx
  __int64 v80; // rcx
  unsigned int v81; // r15d
  unsigned int v82; // r15d
  unsigned int v83; // r15d
  unsigned int v84; // edi
  SHORT iVal; // cx
  LONG v86; // eax
  struct IUnknown *punkVal; // r8
  int IsSameToolbar; // eax
  CShellBrowser2 *v89; // rcx
  unsigned int v90; // edx
  int v91; // eax
  signed int TBar; // eax
  __int64 v93; // rcx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  __int64 (__fastcall ***v95)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  CShellBrowser2 *v96; // rcx
  LPITEMIDLIST v97; // rdi
  __int64 (__fastcall *v98)(LPITEMIDLIST, unsigned __int64, _QWORD); // rbx
  unsigned int HiddenTabCookie; // eax
  unsigned int v100; // eax
  const WCHAR *v101; // rax
  BSTR v102; // rax
  int v103; // eax
  LONG v104; // edx
  unsigned __int16 *v105; // rsi
  unsigned __int16 *bstrVal; // r15
  LONGLONG v107; // rcx
  unsigned int v108; // eax
  LONGLONG v109; // rcx
  bool v110; // al
  __int64 v111; // rcx
  LONGLONG v112; // rcx
  const struct _GUID *v113; // rdi
  __int64 v114; // rcx
  LONGLONG v115; // rdx
  const struct _ITEMIDLIST_ABSOLUTE *cchBuf; // [rsp+20h] [rbp-E0h]
  unsigned int v117; // [rsp+28h] [rbp-D8h]
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST v119[3]; // [rsp+48h] [rbp-B8h] BYREF
  MENUITEMINFOW mii; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR psz[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszFirst[2088]; // [rsp+2C0h] [rbp+1C0h] BYREF

  LODWORD(pidl) = a4;
  v119[0] = a2;
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
                      goto LABEL_241;
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
                  goto LABEL_164;
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
LABEL_241:
            v64 = (HWND *)(this - 40);
            ExtensionCommand = CShellBrowser2::_Exec_CCommonBrowser(
                                 (CShellBrowser2 *)(this - 40),
                                 (const struct _GUID *)v119[0],
                                 a3,
                                 (unsigned int)pidl,
                                 pvarg,
                                 a6);
            if ( !v119[0] )
            {
              if ( a3 == 22 )
              {
                CShellBrowser2::_SetTitle((CShellBrowser2 *)(this - 40), 0);
                (*((void (__fastcall **)(unsigned __int64, _QWORD))*v64 + 56))(this - 40, 0);
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
                v69 = *(_DWORD *)(this + 6304);
                v70 = *(_DWORD *)(this + 6312);
                LODWORD(pidl) = *(_DWORD *)(this + 6424);
                TFlatIsoMessage<LCIE_USERREFRESH>::Post(v70, v69, v67, v68, (__int64)&pidl);
              }
              else if ( a3 == 39 )
              {
                *(_DWORD *)(this + 6456) &= 0xFF9FFFFF;
              }
              return ExtensionCommand;
            }
            if ( CGID_ShellBrowser == *(_QWORD *)v119[0] && *(_QWORD *)v119[0][2].mkid.abID == 0x401B600AA009E96LL )
            {
              ExtensionCommand = 0;
              v71 = a3 - 41092;
              if ( v71 )
              {
                v72 = v71 - 5;
                if ( v72 )
                {
                  v73 = v72 - 7;
                  if ( v73 )
                  {
                    v74 = v73 - 1;
                    if ( v74 )
                    {
                      v75 = v74 - 1;
                      if ( v75 )
                      {
                        v76 = v75 - 1423;
                        if ( v76 )
                        {
                          v77 = v76 - 1;
                          if ( v77 )
                          {
                            if ( v77 == 14 )
                              CShellBrowser2::_OnMouseMove(
                                (CShellBrowser2 *)(this - 40),
                                (int)v119[0],
                                (__int16)HIWORD(pvarg->lVal));
                            else
                              return (unsigned int)-2147221248;
                          }
                          else
                          {
                            v39 = (_DWORD)pidl == 0;
                            *(_BYTE *)(this + 6179) = 0;
                            *(_BYTE *)(this + 6178) = !v39;
                            CBaseBrowser2::_EnsureTabActivityLayeredState((CBaseBrowser2 *)(this - 40));
                          }
                        }
                        else
                        {
                          KillTimer(v64[43], 0x232Eu);
                          if ( *((_DWORD *)v64 + 1556) == 1 )
                          {
                            if ( *((_BYTE *)v64 + 6216) )
                              SetTimer(v64[43], 0x232Fu, 0x7D0u, 0);
                            *((_BYTE *)v64 + 6217) = 1;
                            CBaseBrowser2::_EnsureTabActivityLayeredState((CBaseBrowser2 *)v64);
                            *((_DWORD *)v64 + 1556) = 2;
                            *((_WORD *)v64 + 3114) = 1;
                            if ( !v64[779] )
                            {
                              LODWORD(pidl) = 0;
                              CurrentThreadId = GetCurrentThreadId();
                              if ( (int)LCIEGetTypedComponentFromThread(
                                          0x203u,
                                          CurrentThreadId,
                                          (unsigned int *)&pidl,
                                          0) >= 0 )
                                IsoAddDependency((unsigned int)pidl, (unsigned int)pidl, 1, 57, v64 + 779);
                            }
                          }
                          else
                          {
                            ++*((_WORD *)v64 + 3114);
                          }
                          if ( *((_DWORD *)v64 + 1556) != 2 )
                            KillTimer(v64[43], 0x232Eu);
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
                else if ( pvarg->vt == 3 && (unsigned __int8)IsBrowserFeatureEnabled(512, v119[0], v66, 0) )
                {
                  v79 = pvarg->lVal;
                  *(_DWORD *)(this + 6456) ^= (v79 ^ *(_DWORD *)(this + 6456)) & 1;
                  CLayerParticipant::LayerSetBool((CLayerParticipant *)(this + 192), v79 & 1, 69657, 0);
                  (*((void (__fastcall **)(unsigned __int64, _QWORD))*v64 + 56))(this - 40, 0);
                }
              }
              else if ( a6->vt == 3 )
              {
                a6->lVal = *(_DWORD *)(this + 6456) & 1;
              }
              return ExtensionCommand;
            }
            if ( *(_QWORD *)&CGID_PrivCITCommands.Data1 == *(_QWORD *)v119[0]
              && *(_QWORD *)CGID_PrivCITCommands.Data4 == *(_QWORD *)v119[0][2].mkid.abID )
            {
              v80 = *(_QWORD *)(this + 6488);
              if ( v80 )
                return IUnknown_Exec(v80, v119[0], a3, (_DWORD)pidl, (__int64)pvarg, (__int64)a6);
              return ExtensionCommand;
            }
            if ( *(_QWORD *)&CGID_Explorer.Data1 == *(_QWORD *)v119[0]
              && *(_QWORD *)CGID_Explorer.Data4 == *(_QWORD *)v119[0][2].mkid.abID )
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
                          v89 = (CShellBrowser2 *)(this - 40);
                          if ( IsSameToolbar )
                          {
                            v90 = *((_DWORD *)v64 + 1608);
                          }
                          else
                          {
                            v91 = CShellBrowser2::_IsSameToolbar(v89, L"CommBar", pvarg->punkVal);
                            v89 = (CShellBrowser2 *)(this - 40);
                            if ( !v91 )
                            {
                              TBar = CShellBrowser2::_FindTBar(v89, pvarg->punkVal);
                              if ( TBar != -1 )
                              {
                                v93 = *((_QWORD *)v64[841] + 6 * TBar);
                                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 40LL))(v93, 0);
                              }
                              return 0;
                            }
                            v90 = *((_DWORD *)v64 + 1625);
                          }
                          CShellBrowser2::_SetBrowserBarState(v89, v90, 0, 0, cchBuf, 0, 0);
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
                    v86 = CShellBrowser2::v_ShowControl(this - 40, iVal, lVal_high);
                    if ( v86 != -1 && a6 )
                    {
                      a6->vt = 3;
                      a6->lVal = v86;
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
                v81 = a3 - 29;
                if ( !v81 )
                {
                  v84 = 41523;
                  goto LABEL_371;
                }
                v82 = v81 - 1;
                if ( !v82 )
                {
                  v84 = 41522;
                  goto LABEL_371;
                }
                v83 = v82 - 17;
                if ( v83 )
                {
                  if ( v83 == 50 )
                  {
LABEL_301:
                    v84 = 41530;
                    goto LABEL_371;
                  }
                  return 0;
                }
LABEL_370:
                v84 = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), &CLSID_DiscussionBand);
                if ( v84 == -1 )
                  return 0;
LABEL_371:
                v105 = 0;
                bstrVal = 0;
                if ( !pvarg )
                  goto LABEL_382;
                if ( (_DWORD)pidl )
                {
                  if ( pvarg->vt != 3 )
                  {
                    if ( pvarg->vt == 8 && pvarg->llVal )
                    {
                      bstrVal = pvarg->bstrVal;
                      goto LABEL_383;
                    }
                    goto LABEL_382;
                  }
                }
                else if ( pvarg->vt != 3 )
                {
                  if ( pvarg->vt == 8 && pvarg->llVal )
                  {
                    v105 = pvarg->bstrVal;
LABEL_383:
                    v119[0] = 0;
                    if ( a6 )
                      VariantToIDList(a6, v119);
                    CShellBrowser2::_SetBrowserBarState((CShellBrowser2 *)v64, v84, 0, lVal_high, cchBuf, v105, bstrVal);
                    ILFree(v119[0]);
                    return 0;
                  }
LABEL_382:
                  lVal_high = -1;
                  goto LABEL_383;
                }
                lVal_high = pvarg->cyVal.Lo;
                goto LABEL_383;
              }
              switch ( a3 )
              {
                case '/':
                  goto LABEL_370;
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
                      v104 = pvarg->lVal;
                      if ( v104 > 0 )
                      {
                        pidl = 0;
                        ExtensionCommand = CShellBrowser2::_GetExtensionCommand(
                                             (CShellBrowser2 *)(this - 40),
                                             v104,
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
                          v119[0] = 0;
                          ExtensionCommand = (**llVal)(llVal, &GUID_5f59b0c4_f563_41f3_b7cb_02ca36c4dbc6, v119);
                          if ( (ExtensionCommand & 0x80000000) == 0 )
                          {
                            v95 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPITEMIDLIST *))(this + 312);
                            pidl = 0;
                            ExtensionCommand = (**v95)(v95, &GUID_79e40311_0a9d_4507_a351_aa290a3e18c5, &pidl);
                            if ( (ExtensionCommand & 0x80000000) == 0 )
                            {
                              if ( (*(_DWORD *)(this + 6456) & 0x10000000) != 0 )
                              {
                                v97 = pidl;
                                v98 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 48LL);
                                HiddenTabCookie = CShellBrowser2::_GetHiddenTabCookie(v96);
                                v100 = v98(v97, this - 40, HiddenTabCookie);
                                *(_DWORD *)(this + 6456) &= ~0x10000000u;
                              }
                              else
                              {
                                v100 = (*(__int64 (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 40LL))(pidl);
                              }
                              ExtensionCommand = v100;
                              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(this - 32) + 144LL))(this - 32);
                            }
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
                          }
                          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(v119);
                        }
                      }
                    }
                  }
                  return ExtensionCommand;
                }
                goto LABEL_301;
              }
              if ( pvarg && pvarg->vt == 8 && *(_QWORD *)(this + 6416) )
              {
                v39 = pvarg->llVal == 0;
                *(_QWORD *)&mii.cbSize = *(_QWORD *)(this + 368);
                *(_QWORD *)&mii.fType = *(_QWORD *)(this + 400);
                v101 = &SrcStr;
                if ( !v39 )
                  v101 = pvarg->bstrVal;
                *(_QWORD *)&mii.wID = v101;
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
                    v102 = SysAllocString(psz);
                    a6->llVal = (LONGLONG)v102;
                    if ( v102 )
                      a6->vt = 8;
                  }
                  if ( (unsigned int)IEConfiguration_GetDWORD(536870929) )
                  {
                    v103 = EfsClientDecryptFile(mii.hSubMenu, 0);
                    ExtensionCommand = v103;
                    if ( v103 > 0 )
                      return (unsigned __int16)v103 | 0x80070000;
                  }
                }
                return ExtensionCommand;
              }
              return (unsigned int)-2147467259;
            }
            if ( *(_QWORD *)&CGID_ShellDocView.Data1 != *(_QWORD *)v119[0]
              || *(_QWORD *)CGID_ShellDocView.Data4 != *(_QWORD *)v119[0][2].mkid.abID )
            {
              if ( *(_QWORD *)&CGID_ExplorerBarDoc.Data1 == *(_QWORD *)v119[0]
                && *(_QWORD *)CGID_ExplorerBarDoc.Data4 == *(_QWORD *)v119[0][2].mkid.abID )
              {
                CShellBrowser2::_ExecAllBands(
                  (CShellBrowser2 *)(this - 40),
                  (const struct _GUID *)v119[0],
                  a3,
                  (unsigned int)pidl,
                  pvarg,
                  a6);
              }
              else if ( *(_QWORD *)&CGID_DocHostCmdPriv.Data1 == *(_QWORD *)v119[0]
                     && *(_QWORD *)CGID_DocHostCmdPriv.Data4 == *(_QWORD *)v119[0][2].mkid.abID )
              {
                if ( a3 == 2 )
                {
                  ExtensionCommand = -2147467259;
                  if ( pvarg->vt == 8 )
                  {
                    v115 = pvarg->llVal;
                    pidl = 0;
                    ExtensionCommand = IEParseDisplayNameWithBCW(0, v115, 0, &pidl);
                    if ( pidl )
                    {
                      ExtensionCommand = (*((__int64 (__fastcall **)(unsigned __int64, LPITEMIDLIST, __int64))*v64 + 11))(
                                           this - 40,
                                           pidl,
                                           1);
                      ILFree(pidl);
                    }
                  }
                }
              }
              else if ( *(_QWORD *)&GUID_a11452bc_e055_4e56_a151_7b16dbb4544e.Data1 == *(_QWORD *)v119[0]
                     && *(_QWORD *)GUID_a11452bc_e055_4e56_a151_7b16dbb4544e.Data4 == *(_QWORD *)v119[0][2].mkid.abID
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
                *(_OWORD *)v119 = 0;
                if ( pvarg->vt == 8 )
                {
                  v112 = pvarg->llVal;
                  if ( !v112 || !(unsigned int)GUIDFromStringW(v112, v119) )
                    return 0;
                  v113 = (const struct _GUID *)v119;
                }
                else
                {
                  if ( pvarg->vt != 37 )
                    return ExtensionCommand;
                  v113 = (const struct _GUID *)pvarg->llVal;
                }
                if ( pvarg->vt != 8
                  || (v114 = *(_QWORD *)(this + 6488)) == 0
                  || (int)IUnknown_Exec(v114, (unsigned int)&CGID_PrivCITCommands, 21, (_DWORD)pidl, (__int64)pvarg, 0) < 0 )
                {
                  CShellBrowser2::_SetBrowserBarState(
                    (CShellBrowser2 *)(this - 40),
                    0xFFFFFFFF,
                    v113,
                    (_DWORD)pidl != 0,
                    cchBuf,
                    0,
                    0);
                }
                return 0;
              case '.':
                if ( (unsigned int)SHIsRestricted2W(*(HWND *)(this + 304)) )
                  return ExtensionCommand;
                v110 = IsOs_Win8OrGreater();
                IELaunchPlatformHelp(v111, !v110 + 18);
                break;
              case '3':
                v109 = pvarg->llVal;
                *(_OWORD *)&mii.cbSize = 0;
                if ( !v109 || !(unsigned int)GUIDFromStringW(v109, &mii) )
                  return (unsigned int)-2147467259;
                a6->vt = 3;
                a6->lVal = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), (const struct _GUID *)&mii);
                break;
              case '8':
                if ( (*(_DWORD *)(this + 6460) || *(_DWORD *)(this + 6392)) && pvarg->vt == 8 )
                {
                  v107 = pvarg->llVal;
                  *(_OWORD *)v119 = 0;
                  if ( v107 )
                  {
                    if ( (unsigned int)GUIDFromStringW(v107, v119) )
                    {
                      v108 = CShellBrowser2::_InfoCLSIDToIdm((CShellBrowser2 *)(this - 40), (const struct _GUID *)v119);
                      if ( *(_DWORD *)(this + 6460) == v108 || *(_DWORD *)(this + 6392) == v108 )
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
            goto LABEL_241;
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
          goto LABEL_241;
        }
        switch ( a3 )
        {
          case 'W':
            if ( pvarg || !a6 || a6->vt != 37 )
              goto LABEL_241;
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
              goto LABEL_241;
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
            goto LABEL_241;
          default:
            if ( a3 != 102 || !pvarg || pvarg->vt != 11 )
              goto LABEL_241;
            v21 = 69639;
            v22 = pvarg->iVal == 0xFFFF;
            break;
        }
        CLayerParticipant::LayerSetBool((CLayerParticipant *)(this + 192), v22, v21, 0);
        goto LABEL_241;
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
            goto LABEL_241;
          case 0x7Au:
            if ( a6 && a6->vt == 11 )
            {
              a6->iVal = -((*(_DWORD *)(this + 6456) & 0x40000000) != 0);
              return 0;
            }
            goto LABEL_241;
          case 0x7Cu:
            CShellBrowser2::_CorrelatedVtabClose((CShellBrowser2 *)(this - 40), pvarg);
            return 0;
          case 0x81u:
            CShellBrowser2::_SendImageCookieToFrame((CShellBrowser2 *)(this - 40), pvarg);
            goto LABEL_241;
          case 0x82u:
            LCIE2ChangeComponentSharedFlagBit(*(_DWORD *)(this + 6304), 1, 6u);
            CurrentProcessManager = IsoGetCurrentProcessManager();
            LCIEChangeComponentSharedFlagBit(CurrentProcessManager, 1, 0);
            LCIEPostMessageWithoutBuffer(*(_DWORD *)(this + 6308), *(_DWORD *)(this + 6304), 0xD57u, 0);
            *(_DWORD *)(this + 6456) |= 0x80000u;
            *(_BYTE *)(this + 6928) = 1;
            goto LABEL_241;
        }
        if ( a3 - 137 > 1 )
          goto LABEL_241;
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
              goto LABEL_241;
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
        goto LABEL_241;
      }
      if ( !a6 )
        goto LABEL_241;
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
        goto LABEL_241;
      pidl = 0;
      if ( !pvarg || (int)VariantToIDList(pvarg, &pidl) < 0 )
        return 0;
      v38 = pidl;
      if ( !pidl || !pidl->mkid.cb )
      {
LABEL_165:
        ILFree(v38);
        return 0;
      }
      if ( *(_QWORD *)(this + 6512) )
      {
        KillTimer(*(HWND *)(this + 304), 0x64u);
        v38 = pidl;
      }
      if ( (unsigned int)Pidl_Set(this + 6512, v38) && !SetTimer(*(HWND *)(this + 304), 0x64u, 0x1F4u, 0) )
        Pidl_Set(this + 6512, 0);
LABEL_164:
      v38 = pidl;
      goto LABEL_165;
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
      goto LABEL_241;
    }
    if ( *(_QWORD *)&CGID_ShellDocView.Data1 != *(_QWORD *)&a2->mkid.cb
      || *(_QWORD *)CGID_ShellDocView.Data4 != *(_QWORD *)a2[2].mkid.abID )
    {
      goto LABEL_241;
    }
    if ( a3 > 0x7A )
    {
      if ( a3 > 0x9D )
      {
        if ( a3 == 158 )
        {
          v63 = *(_QWORD *)(this + 6648);
          if ( v63 )
            (*(void (__fastcall **)(__int64, VARIANTARG *, __int64, _QWORD))(*(_QWORD *)v63 + 32LL))(v63, pvarg, 3, 0);
        }
        else
        {
          if ( a3 != 161 && a3 != 162 )
          {
            if ( a3 == 181 )
            {
              v54 = TLSGetTabId();
              v56 = 42;
            }
            else
            {
              if ( a3 != 182 )
              {
                if ( a3 == 183 )
                {
                  v51 = *(struct IUnknown **)(this + 336);
                  *(_QWORD *)&mii.cbSize = 0;
                  GetTopWBConnectionPoints(v51, (struct IConnectionPoint **)&mii, 0);
                  v52 = TLSGetTabId();
                  TryLogHttpStatusCodeChange(
                    v52,
                    v53,
                    *(HWND *)(this + 6536),
                    *(struct IWebBrowser2 **)(this + 328),
                    (LONG)pvarg);
                  ATL::CComPtr<IConnectionPoint>::~CComPtr<IConnectionPoint>(&mii);
                }
                goto LABEL_241;
              }
              v54 = TLSGetTabId();
              v56 = 43;
            }
            LOBYTE(v55) = 1;
            CSuggestedSites::LogSuggestedSitesUIEvent(v54, *(_QWORD *)(this + 6536), v56, v55);
            goto LABEL_241;
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
                  v57 = (int (__fastcall ***)(_QWORD, GUID *, MENUITEMINFOW *))pvarg->llVal;
                  if ( v57 )
                  {
                    v58 = *v57;
                    *(_QWORD *)&mii.cbSize = 0;
                    if ( (*v58)(v57, &GUID_57440f87_4899_4a16_9168_0466e43a4a48, &mii) >= 0 )
                    {
                      v59 = TLSGetTabId();
                      CSuggestedSites::LogSuggestedSitesUIEventNavElementNoCheck(
                        v59,
                        *(HWND *)(this + 6536),
                        *(struct IElementDOMInfo **)&mii.cbSize,
                        a3 == 162);
                      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)&mii.cbSize + 16LL))(
                        *(_QWORD *)&mii.cbSize,
                        v60,
                        v61,
                        v62);
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_241;
      }
      if ( a3 == 157 )
      {
        v50 = *(_QWORD *)(this + 6648);
        if ( v50 )
          (*(void (__fastcall **)(__int64, ITEMIDLIST *, __int64, _QWORD))(*(_QWORD *)v50 + 24LL))(v50, a2, 3, 0);
        goto LABEL_241;
      }
      if ( a3 != 123 && a3 != 127 )
      {
        switch ( a3 )
        {
          case 0x81u:
            v49 = *(_QWORD *)(this - 40);
            memset(&mii, 0, 24);
            v47 = (*(__int64 (__fastcall **)(unsigned __int64, ITEMIDLIST *, __int64, _QWORD))(v49 + 504))(
                    this - 40,
                    a2,
                    3,
                    0);
            v48 = 2005;
            break;
          case 0x83u:
            goto LABEL_213;
          case 0x89u:
            CShellBrowser2::OnBrowserNavigateComplete2((CShellBrowser2 *)(this - 40));
            goto LABEL_241;
          case 0x8Au:
            v46 = *(_QWORD *)(this - 40);
            memset(&mii, 0, 24);
            v47 = (*(__int64 (__fastcall **)(unsigned __int64, ITEMIDLIST *, __int64, _QWORD))(v46 + 504))(
                    this - 40,
                    a2,
                    3,
                    0);
            v48 = 2006;
            break;
          default:
            v43 = a3 == 156;
LABEL_212:
            if ( !v43 )
              goto LABEL_241;
            goto LABEL_213;
        }
        LCIEPostDispatchEvent(
          *(_DWORD *)(this + 6312),
          v48,
          (struct tagDISPPARAMS *)&mii,
          *(HWND *)(this + 6536),
          v47,
          v117);
        goto LABEL_241;
      }
    }
    else
    {
      if ( a3 == 122 )
        goto LABEL_213;
      if ( a3 > 0x68 )
      {
        if ( a3 == 108 || a3 == 109 || a3 == 110 )
          goto LABEL_213;
        if ( a3 == 111 )
        {
          if ( pvarg->vt != 3 )
            goto LABEL_241;
          v44 = pvarg->lVal;
          if ( v44 <= 0 || a4 != 1 || !a6 )
            goto LABEL_241;
          v36 = (BSTR)CShellBrowser2::_MenuPopulateToolbars((CShellBrowser2 *)(this - 40), v44);
          a6->vt = 37;
          goto LABEL_135;
        }
        v40 = a3 - 118;
        v39 = a3 == 118;
      }
      else
      {
        switch ( a3 )
        {
          case 0x68u:
            goto LABEL_213;
          case 1u:
          case 2u:
          case 0x11u:
          case 0x32u:
            if ( pvarg )
            {
              if ( pvarg->vt == 3 && pvarg->lVal == -5501 )
              {
                v41 = *(_QWORD *)(this + 328);
                LOWORD(mii.cbSize) = 0;
                if ( v41 )
                {
                  if ( (*(int (__fastcall **)(__int64, MENUITEMINFOW *, __int64, _QWORD))(*(_QWORD *)v41 + 456LL))(
                         v41,
                         &mii,
                         3,
                         0) >= 0 )
                  {
                    v42 = (CShellBrowser2 *)(this - 40);
                    if ( LOWORD(mii.cbSize) )
                      CShellBrowser2::_DecrNetSessionCount(v42);
                    else
                      CShellBrowser2::_IncrNetSessionCount(v42);
                  }
                }
              }
            }
            goto LABEL_241;
          case 0x61u:
            goto LABEL_213;
        }
        v40 = a3 - 98;
        v39 = a3 == 98;
      }
      if ( !v39 )
      {
        v43 = v40 == 1;
        goto LABEL_212;
      }
    }
LABEL_213:
    v45 = *(_QWORD *)(this + 360);
    if ( v45 )
      return (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD, _QWORD, VARIANTARG *, struct tagVARIANT *))(*(_QWORD *)v45 + 32LL))(
               v45,
               &CGID_ShellDocView,
               a3,
               a4,
               pvarg,
               a6);
    goto LABEL_241;
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
    goto LABEL_241;
  }
  if ( !(unsigned int)CShellBrowser2::_HasToolbarFocus((CShellBrowser2 *)(this - 40)) )
    goto LABEL_241;
  v13 = (_QWORD *)(*(_QWORD *)(this + 6688) + 48LL * *(int *)(this + 6800));
  if ( !v13 )
    goto LABEL_241;
  result = IUnknown_Exec(*v13, 0, a3, a4, (__int64)pvarg, (__int64)a6);
  if ( (int)result < 0 )
    goto LABEL_241;
  return result;
}

```

## disassembly

```asm
0x18006d850  push    rbp
0x18006d852  push    rbx
0x18006d853  push    rsi
0x18006d854  push    rdi
0x18006d855  push    r12
0x18006d857  push    r13
0x18006d859  push    r14
0x18006d85b  push    r15
0x18006d85d  lea     rbp, [rsp-1228h]
0x18006d865  mov     eax, 1328h
0x18006d86a  call    _alloca_probe
0x18006d86f  sub     rsp, rax
0x18006d872  mov     rax, cs:__security_cookie
0x18006d879  xor     rax, rsp
0x18006d87c  mov     [rbp+1260h+var_50], rax
0x18006d883  mov     r12, [rbp+1260h+arg_28]
0x18006d88a  mov     rsi, rcx
0x18006d88d  mov     rbx, [rbp+1260h+pvarg]
0x18006d894  mov     ecx, 0Bh
0x18006d899  mov     r14d, r9d
0x18006d89c  or      edi, 0FFFFFFFFh
0x18006d89f  xor     r9d, r9d
0x18006d8a2  mov     dword ptr [rsp+1360h+pidl], r14d
0x18006d8a7  mov     [rsp+1360h+var_1318], rdx
0x18006d8ac  mov     r15d, r8d
0x18006d8af  lea     r13d, [rcx-0Ah]
0x18006d8b3  lea     r10d, [rcx-3]
0x18006d8b7  lea     r11d, [rcx+1Ah]
0x18006d8bb  lea     r8d, [rcx-8]
0x18006d8bf  test    rdx, rdx
0x18006d8c2  jnz     loc_18006D96E
0x18006d8c8  mov     eax, r15d
0x18006d8cb  sub     eax, 0Ah
0x18006d8ce  jz      short loc_18006D91A
0x18006d8d0  sub     eax, r13d
0x18006d8d3  jz      short loc_18006D91A
0x18006d8d5  sub     eax, r13d
0x18006d8d8  jz      short loc_18006D91A
0x18006d8da  sub     eax, r13d
0x18006d8dd  jz      short loc_18006D91A
0x18006d8df  sub     eax, 14h
0x18006d8e2  jz      short loc_18006D91A
0x18006d8e4  cmp     eax, 0Ch
0x18006d8e7  jnz     loc_18006E681
0x18006d8ed  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18006d8f3  test    al, al
0x18006d8f5  jz      loc_18006E681
0x18006d8fb  mov     r8d, r13d; wParam
0x18006d8fe  mov     edx, 81A8h; Msg
0x18006d903  mov     rcx, [rsi+130h]; hWnd
0x18006d90a  xor     r9d, r9d; lParam
0x18006d90d  call    cs:__imp_PostMessageW
0x18006d913  xor     eax, eax
0x18006d915  jmp     loc_18006F2D3
0x18006d91a  lea     rcx, [rsi-28h]; this
0x18006d91e  call    ?_HasToolbarFocus@CShellBrowser2@@AEAAHXZ; CShellBrowser2::_HasToolbarFocus(void)
0x18006d923  test    eax, eax
0x18006d925  jz      loc_18006E681
0x18006d92b  movsxd  rax, dword ptr [rsi+1A90h]
0x18006d932  lea     rcx, [rax+rax*2]
0x18006d936  shl     rcx, 4
0x18006d93a  add     rcx, [rsi+1A20h]
0x18006d941  jz      loc_18006E681
0x18006d947  mov     rcx, [rcx]
0x18006d94a  mov     r9d, r14d
0x18006d94d  mov     [rsp+1360h+var_1338], r12
0x18006d952  mov     r8d, r15d
0x18006d955  xor     edx, edx
0x18006d957  mov     qword ptr [rsp+1360h+cchBuf], rbx
0x18006d95c  call    IUnknown_Exec
0x18006d961  test    eax, eax
0x18006d963  js      loc_18006E681
0x18006d969  jmp     loc_18006F2D3
0x18006d96e  mov     rax, qword ptr cs:CGID_Explorer.Data1
0x18006d975  cmp     rax, [rdx]
0x18006d978  jnz     loc_18006E19F
0x18006d97e  mov     rax, qword ptr cs:CGID_Explorer.Data4
0x18006d985  cmp     rax, [rdx+8]
0x18006d989  jnz     loc_18006E19F
0x18006d98f  cmp     r15d, 68h ; 'h'
0x18006d993  ja      loc_18006DE03
0x18006d999  jz      loc_18006DDF2
0x18006d99f  cmp     r15d, 50h ; 'P'
0x18006d9a3  ja      loc_18006DBEA
0x18006d9a9  jz      loc_18006DCBF
0x18006d9af  mov     eax, r15d
0x18006d9b2  sub     eax, 2
0x18006d9b5  jz      loc_18006DB12
0x18006d9bb  sub     eax, 6
0x18006d9be  jz      loc_18006DCBF
0x18006d9c4  sub     eax, 31h ; '1'
0x18006d9c7  jz      loc_18006DAFF
0x18006d9cd  sub     eax, r13d
0x18006d9d0  jz      loc_18006DABD
0x18006d9d6  sub     eax, 4
0x18006d9d9  jz      loc_18006DC89
0x18006d9df  sub     eax, r10d
0x18006d9e2  jz      short loc_18006DA5C
0x18006d9e4  sub     eax, r13d
0x18006d9e7  jz      short loc_18006DA3E
0x18006d9e9  cmp     eax, r13d
0x18006d9ec  jnz     loc_18006E681
0x18006d9f2  mov     ecx, [rbx+8]; unsigned int
0x18006d9f5  lea     rdx, [rsp+1360h+pidl]; struct IBrowserAsyncPackage **
0x18006d9fa  mov     [rsp+1360h+pidl], r9
0x18006d9ff  call    ?CBrowserWinMsgPackage_GetInstance@@YAJKPEAPEAUIBrowserAsyncPackage@@@Z; CBrowserWinMsgPackage_GetInstance(ulong,IBrowserAsyncPackage * *)
0x18006da04  xorps   xmm0, xmm0
0x18006da07  movups  xmmword ptr [rbx], xmm0
0x18006da0a  test    eax, eax
0x18006da0c  js      short loc_18006DA33
0x18006da0e  xor     eax, eax
0x18006da10  lea     rcx, [rsi-28h]; this
0x18006da14  mov     [rbx+10h], rax
0x18006da18  mov     rdx, rbx; pvarg
0x18006da1b  mov     rax, [rsp+1360h+pidl]
0x18006da20  mov     [rbx+8], rax
0x18006da24  mov     word ptr [rbx], 0Dh
0x18006da29  call    ?_ProcessTranslateAccAsync@CShellBrowser2@@AEAAJPEAUtagVARIANT@@@Z; CShellBrowser2::_ProcessTranslateAccAsync(tagVARIANT *)
0x18006da2e  jmp     loc_18006F2D3
0x18006da33  xor     eax, eax
0x18006da35  mov     [rbx+10h], rax
0x18006da39  jmp     loc_18006F2D3
0x18006da3e  mov     r9, [rbx+8]; lParam
0x18006da42  mov     r8, r14; wParam
0x18006da45  mov     rcx, [rsi+130h]; hWnd
0x18006da4c  mov     edx, 1Ah; Msg
0x18006da51  call    cs:__imp_SendMessageW
0x18006da57  jmp     loc_18006D913
0x18006da5c  mov     [rsp+1360h+pidl], r9
0x18006da61  test    rbx, rbx
0x18006da64  jz      loc_18006D913
0x18006da6a  lea     rdx, [rsp+1360h+pidl]
0x18006da6f  mov     rcx, rbx
0x18006da72  call    VariantToIDList
0x18006da77  xor     ebx, ebx
0x18006da79  test    eax, eax
0x18006da7b  js      loc_18006D913
0x18006da81  test    r12, r12
0x18006da84  jz      loc_18006D913
0x18006da8a  lea     ecx, [rbx+0Bh]
0x18006da8d  cmp     [r12], cx
0x18006da92  jnz     loc_18006D913
0x18006da98  mov     rcx, [rsp+1360h+pidl]
0x18006da9d  xor     edx, edx
0x18006da9f  mov     [r12+8], bx
0x18006daa5  call    TryIEShellDelegation
0x18006daaa  test    eax, eax
0x18006daac  jz      loc_18006E25A
0x18006dab2  mov     [r12+8], di
0x18006dab8  jmp     loc_18006E25A
0x18006dabd  lea     rcx, [rsi-28h]; this
0x18006dac1  mov     [rsp+1360h+pidl], r9
0x18006dac6  lea     rdx, [rsp+1360h+pidl]; struct IBrowserFrame **
0x18006dacb  call    ?_GetBrowserFrame@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrame@@@Z; CShellBrowser2::_GetBrowserFrame(IBrowserFrame * *)
0x18006dad0  xor     ebx, ebx
0x18006dad2  test    eax, eax
0x18006dad4  js      short loc_18006DAED
0x18006dad6  mov     rcx, [rsp+1360h+pidl]
0x18006dadb  mov     rax, [rcx]
0x18006dade  mov     rax, [rax+48h]
0x18006dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dae7  test    eax, eax
0x18006dae9  cmovns  r13d, ebx
0x18006daed  lea     rcx, [rsp+1360h+pidl]; void *
0x18006daf2  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18006daf7  mov     eax, r13d
0x18006dafa  jmp     loc_18006F2D3
0x18006daff  mov     eax, [rsi+2BCh]
0x18006db05  shr     eax, 14h
0x18006db08  not     eax
0x18006db0a  and     eax, r13d
0x18006db0d  jmp     loc_18006F2D3
0x18006db12  mov     edx, 824h
0x18006db17  lea     rax, [rbp+1260h+pszFirst]
0x18006db1e  mov     ecx, edx
0x18006db20  mov     [rax], r9b
0x18006db23  add     rax, r13
0x18006db26  sub     rcx, r13
0x18006db29  jnz     short loc_18006DB20
0x18006db2b  mov     rcx, [rsi+170h]; int
0x18006db32  mov     r14b, r9b
0x18006db35  test    rcx, rcx
0x18006db38  jz      short loc_18006DB89
0x18006db3a  mov     [rsp+1360h+var_1338], r9; __int64
0x18006db3f  xor     r8d, r8d; int
0x18006db42  mov     [rsp+1360h+cchBuf], edx; cchBuf
0x18006db46  lea     r9, [rbp+1260h+pszFirst]; int
0x18006db4d  mov     edx, 8000h; int
0x18006db52  call    IEGetNameAndFlagsEx
0x18006db57  xor     r9d, r9d
0x18006db5a  test    eax, eax
0x18006db5c  js      short loc_18006DB83
0x18006db5e  lea     rdx, aMicrosoftEdge; "microsoft-edge"
0x18006db65  lea     rcx, [rbp+1260h+pszFirst]; pszFirst
0x18006db6c  call    cs:__imp_StrStrIW
0x18006db72  lea     rcx, [rbp+1260h+pszFirst]
0x18006db79  cmp     rcx, rax
0x18006db7c  setz    r14b
0x18006db80  xor     r9d, r9d
0x18006db83  mov     r8d, 3
0x18006db89  cmp     [rsi+170h], r9
0x18006db90  jz      short loc_18006DB9B
0x18006db92  test    r14b, r14b
0x18006db95  jz      loc_18006E681
0x18006db9b  test    rbx, rbx
0x18006db9e  jz      loc_18006E681
0x18006dba4  cmp     [rbx], r8w
0x18006dba8  jnz     loc_18006E681
0x18006dbae  cmp     [rbx+8], r9d
0x18006dbb2  jnz     loc_18006E681
0x18006dbb8  lea     rcx, [rsi-28h]; this
0x18006dbbc  call    ?_CancelPendingNavigationAsync@CBaseBrowser2@@IEAAJXZ; CBaseBrowser2::_CancelPendingNavigationAsync(void)
0x18006dbc1  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18006dbc7  test    al, al
0x18006dbc9  jz      short loc_18006DBDE
0x18006dbcb  mov     r8b, r13b; bool
0x18006dbce  lea     rcx, [rsi-28h]; this
0x18006dbd2  xor     edx, edx; bool
0x18006dbd4  call    ?_DualEngineOnDeferredCloseCommand@CShellBrowser2@@AEAAX_N0@Z; CShellBrowser2::_DualEngineOnDeferredCloseCommand(bool,bool)
0x18006dbd9  jmp     loc_18006D913
0x18006dbde  xor     r8d, r8d
0x18006dbe1  lea     edx, [r8+10h]
0x18006dbe5  jmp     loc_18006D903
0x18006dbea  mov     eax, r15d
0x18006dbed  sub     eax, 57h ; 'W'
0x18006dbf0  jz      loc_18006DD5B
0x18006dbf6  sub     eax, r8d
0x18006dbf9  jz      loc_18006DCEB
0x18006dbff  sub     eax, r13d
0x18006dc02  jz      loc_18006DCBF
0x18006dc08  sub     eax, 4
0x18006dc0b  jz      loc_18006DCBF
0x18006dc11  sub     eax, r8d
0x18006dc14  jz      short loc_18006DC89
0x18006dc16  sub     eax, r8d
0x18006dc19  jz      short loc_18006DC48
0x18006dc1b  cmp     eax, r13d
0x18006dc1e  jnz     loc_18006E681
0x18006dc24  test    rbx, rbx
0x18006dc27  jz      loc_18006E681
0x18006dc2d  cmp     [rbx], cx
0x18006dc30  jnz     loc_18006E681
0x18006dc36  cmp     [rbx+8], di
0x18006dc3a  mov     r8d, 11007h
0x18006dc40  setz    dl
0x18006dc43  jmp     loc_18006DD4A
0x18006dc48  mov     rcx, cs:?IEVALUE_PrivacIE_DisableInPrivateBlocking@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking
0x18006dc4f  lea     rdx, [rsp+1360h+mii]
0x18006dc54  mov     [rsp+1360h+mii.cbSize], r9d
0x18006dc59  call    GetBOOL
0x18006dc5e  cmp     [rsp+1360h+mii.cbSize], 0
0x18006dc63  jnz     loc_18006E681
0x18006dc69  mov     eax, [rsi+1938h]
0x18006dc6f  test    r13b, r14b
0x18006dc72  jz      short loc_18006DC83
0x18006dc74  bts     eax, 14h
0x18006dc78  mov     [rsi+1938h], eax
0x18006dc7e  jmp     loc_18006E681
0x18006dc83  btr     eax, 14h
0x18006dc87  jmp     short loc_18006DC78
0x18006dc89  cmp     r15d, 62h ; 'b'
0x18006dc8d  lea     rax, aSbcmdidCancela; "SBCMDID_CANCELANDCLOSE"
0x18006dc94  lea     rdx, aSbcmdidCancela_0; "SBCMDID_CANCELANDFINISH"
0x18006dc9b  cmovnz  rdx, rax; char *
0x18006dc9f  lea     rcx, aCshellbrowser2; "CShellBrowser2::Exec - %s"
0x18006dca6  call    ?Printf@InstrumentationUtils@@YAJPEBDZZ; InstrumentationUtils::Printf(char const *,...)
0x18006dcab  lea     rcx, [rsi-28h]; this
0x18006dcaf  xor     r8d, r8d; unsigned int
0x18006dcb2  mov     rdx, rbx; struct tagVARIANT *
0x18006dcb5  call    ?_CancelAndClose@CShellBrowser2@@AEAAXPEAUtagVARIANT@@K_N@Z; CShellBrowser2::_CancelAndClose(tagVARIANT *,ulong,bool)
0x18006dcba  jmp     loc_18006D913
0x18006dcbf  mov     rcx, [rsi+168h]
0x18006dcc6  test    rcx, rcx
0x18006dcc9  jz      loc_18006E681
0x18006dccf  mov     [rsp+1360h+var_1338], r12
0x18006dcd4  lea     rdx, CGID_Explorer
0x18006dcdb  mov     qword ptr [rsp+1360h+cchBuf], rbx
0x18006dce0  mov     r9d, r14d
0x18006dce3  mov     r8d, r15d
0x18006dce6  jmp     loc_18006DF97
0x18006dceb  test    rbx, rbx
0x18006dcee  jz      loc_18006E681
0x18006dcf4  cmp     [rbx], cx
0x18006dcf7  jnz     loc_18006E681
0x18006dcfd  movsx   edx, word ptr [rbx+8]
0x18006dd01  mov     ecx, [rsi+1938h]
0x18006dd07  lea     eax, ds:0[rdx*8]
0x18006dd0e  xor     eax, ecx
0x18006dd10  and     eax, r10d
0x18006dd13  xor     eax, ecx
0x18006dd15  mov     [rsi+1938h], eax
0x18006dd1b  test    r13b, dl
0x18006dd1e  jz      short loc_18006DD29
0x18006dd20  mov     rdx, [rsi+18B8h]
0x18006dd27  jmp     short loc_18006DD2C
0x18006dd29  mov     rdx, r9; HMENU
0x18006dd2c  lea     rcx, [rsi-28h]; this
0x18006dd30  call    ?_SetMenu@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_SetMenu(HMENU__ *)
0x18006dd35  mov     edx, [rsi+1938h]
0x18006dd3b  mov     r8d, 11021h; int
  ... truncated ...
```
