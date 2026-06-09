# CBrowserFrame::_FrameLCIEWndProc(uint,unsigned __int64,__int64,int *)

- ea: `0x1800304a4`
- end: `0x180030f56`
- name: `?_FrameLCIEWndProc@CBrowserFrame@@IEAA_JI_K_JPEAH@Z`
- size: `2738`
- prototype: `__int64 __usercall@<rax>(CBrowserFrame *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `70`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180031550`

## callees

- `0x180005030`
- `0x1800096a0`
- `0x1800304a4`
- `0x180030f5c`
- `0x180031264`
- `0x180081ee8`
- `0x180094b68`
- `0x18009b188`
- `0x1800a0fcc`
- `0x1801d06f0`
- `0x1801d3874`
- `0x1801d38e0`
- `0x180244f7c`
- `0x180245044`
- `0x180251f4c`
- `0x1802555c4`
- `0x1802556d4`
- `0x180255bc8`
- `0x180255c8c`
- `0x180255d34`
- `0x180255dd0`
- `0x180255e6c`
- `0x180255edc`
- `0x180256010`
- `0x1802560e0`
- `0x180256170`
- `0x1802566e0`
- `0x180256844`
- `0x180256a54`
- `0x180256c7c`
- `0x180256eb4`
- `0x180257034`
- `0x18025722c`
- `0x180257274`
- `0x180257470`
- `0x180257554`
- `0x180257608`
- `0x180257980`
- `0x180257a14`
- `0x180257ba4`
- `0x180257cbc`
- `0x180257dfc`
- `0x180257ea0`
- `0x180257f30`
- `0x1802580d0`
- `0x1802581dc`
- `0x180258260`
- `0x180258328`
- `0x1802583a8`
- `0x180258434`

## import_xrefs

- `USER32!SetTimer` at `0x180030ca6`
- `USER32!SetTimer` at `0x180030ca6`
- `USER32!PostMessageW` at `0x180030c83`
- `USER32!PostMessageW` at `0x180030c83`
- `OLEAUT32!__imp_SysFreeString` at `0x18003096b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003096b`
- `iertutil!CreateUri` at `0x180030925`
- `iertutil!CreateUri` at `0x180030925`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1800308ec`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1800308ec`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180030699`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180030699`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180030554`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180030554`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800304f5`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800308cc`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800304f5`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800308cc`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180030f1f`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180030f1f`
- `msIso!__imp_?IsoRemoveTask@@YAJKK@Z` at `0x180030759`
- `msIso!__imp_?IsoRemoveTask@@YAJKK@Z` at `0x180030759`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030511`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030520`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030530`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030540`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030efd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030f0d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030511`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030520`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030530`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030540`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030efd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180030f0d`

## pseudocode

```c
__int64 __fastcall CBrowserFrame::_FrameLCIEWndProc(
        CTabWindowManager **this,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        int *a5)
{
  unsigned int v5; // esi
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  char v11; // r12
  __int64 v12; // rdx
  CBrowserFrame *v13; // rcx
  int WindowsMessageNumber; // r15d
  _BOOL8 v15; // r8
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  struct _GUID *v22; // rax
  unsigned int v23; // r8d
  const struct _GUID *v24; // rax
  unsigned int v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  unsigned int (**v28)(void *); // rbx
  CTabWindowManager *v29; // rbx
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  CBrowserFrame *v41; // rcx
  int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  unsigned int v46; // ebx
  unsigned int v47; // ebx
  CTabWindowManager *v48; // rax
  unsigned int v49; // ebx
  unsigned int v50; // ebx
  unsigned int v51; // ebx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  unsigned int v54; // ebx
  unsigned int v55; // ebx
  unsigned int v56; // ebx
  unsigned int v57; // ebx
  unsigned int v58; // ebx
  unsigned int v59; // ebx
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  unsigned int v62; // ebx
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  unsigned int v65; // ebx
  _DWORD *v66; // rax
  unsigned int v67; // ebx
  unsigned int v68; // ebx
  unsigned int v69; // ebx
  unsigned int v70; // ebx
  unsigned int v71; // ebx
  CTabWindowManager *v72; // rcx
  CTabWindowManager *v73; // rcx
  CTabWindowManager *v74; // rcx
  CTabWindowManager *v75; // rcx
  CTabWindowManager *v76; // rcx
  CTabWindowManager *v77; // rcx
  CTabWindowManager *v78; // rcx
  CTabWindowManager *v79; // rcx
  CTabWindowManager *v80; // rcx
  CTabWindowManager *v81; // rcx
  CTabWindowManager *v82; // rcx
  CTabWindowManager *v83; // rcx
  CTabWindowManager *v84; // rcx
  CTabWindowManager *v85; // rcx
  CTabWindowManager *v86; // rcx
  CDualEngine20BrowserCoupling *v87; // rcx
  CTabWindowManager *v88; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-51h]
  struct _IsoMessage *v91; // [rsp+40h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-29h] BYREF
  IUri *ppURI[2]; // [rsp+50h] [rbp-21h] BYREF
  struct _IsoMessage *v94; // [rsp+E8h] [rbp+77h] BYREF

  v5 = a4;
  if ( a4 )
  {
    v91 = 0;
    if ( (int)IsoGetMessageBufferAddress(a4, 1, 0, &v91, 0) < 0 )
    {
LABEL_193:
      IsoFreeMessageBuffer(v5);
      goto LABEL_194;
    }
    v9 = *((_OWORD *)v91 + 1);
    v10 = *(_OWORD *)GlobalThreadState();
    v11 = *((_BYTE *)GlobalThreadState() + 16);
    *(_OWORD *)GlobalThreadState() = v9;
    *((_BYTE *)GlobalThreadState() + 16) = 1;
    WindowsMessageNumber = IsoGetWindowsMessageNumber(3);
    LOBYTE(v15) = a2 == WindowsMessageNumber;
    if ( a3 <= 0xC47 )
    {
      if ( a3 == 3143 )
      {
        CBrowserFrame::_HandleSysCharAltSpace((CBrowserFrame *)this, v5, v15);
      }
      else if ( a3 > 0xC0E )
      {
        if ( a3 <= 0xC40 )
        {
          if ( a3 == 3136 )
          {
            v48 = this[42];
            if ( v48 && *((_QWORD *)v48 + 3) && *((_BYTE *)v48 + 73) )
              CBrowserFrame::_HandleNewTabPageUserRefresh((CBrowserFrame *)this);
            (*((void (__fastcall **)(char *, GUID *, __int64))this[10] + 4))(
              (char *)this + 80,
              &GUID_d4d21454_070f_4033_88f6_1b8d7ba630a9,
              18);
          }
          else if ( a3 > 0xC15 )
          {
            v43 = a3 - 3095;
            if ( v43 )
            {
              v44 = v43 - 1;
              if ( v44 )
              {
                v45 = v44 - 1;
                if ( v45 )
                {
                  v46 = v45 - 4;
                  if ( v46 )
                  {
                    v47 = v46 - 1;
                    if ( v47 )
                    {
                      if ( v47 == 2 )
                        CBrowserFrame::_HandleEmulate7CheckDomain((CBrowserFrame *)this, v5);
                    }
                    else
                    {
                      CBrowserFrame::_HandleEmulate7FromTab((CBrowserFrame *)this, v5, v15);
                    }
                  }
                  else
                  {
                    CBrowserFrame::_HandleSearchInNewTab((CBrowserFrame *)this, v5, v15);
                  }
                }
                else
                {
                  CBrowserFrame::_HandleChangeUIState((CBrowserFrame *)this, v5, v15);
                }
              }
              else
              {
                CBrowserFrame::_HandleTranslateAccGlobalSignal((CBrowserFrame *)this, v5, v15);
              }
            }
            else
            {
              CBrowserFrame::_HandleFocusNotificationBar((CBrowserFrame *)this, v12);
            }
          }
          else if ( a3 == 3093 )
          {
            CBrowserFrame::_HandleSysCommand((CBrowserFrame *)this, v5, v15);
          }
          else
          {
            v36 = a3 - 3087;
            if ( v36 )
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                v38 = v37 - 1;
                if ( v38 )
                {
                  v39 = v38 - 1;
                  if ( v39 )
                  {
                    v40 = v39 - 1;
                    if ( v40 )
                    {
                      if ( v40 == 1 )
                        CBrowserFrame::_HandleSelectTab((CBrowserFrame *)this, v5, v15);
                    }
                    else
                    {
                      CBrowserFrame::_HandleShowManagedAddOns((CBrowserFrame *)this, v5, v15);
                    }
                  }
                  else
                  {
                    CBrowserFrame::_HandleClsIdCreated(v13, v5, v15);
                  }
                }
                else
                {
                  CBrowserFrame::_HandleAppCommand((CBrowserFrame *)this, v5, v15);
                }
              }
              else
              {
                CBrowserFrame::_HandleEnableAutoCompleteNotification((CBrowserFrame *)this);
              }
            }
            else
            {
              v94 = 0;
              if ( (int)IsoGetMessageBufferAddress(v5, 1, 0, &v94, 0) >= 0
                && (a2 != WindowsMessageNumber || VerifyUntrusted_IsoMessage_ExactSize(v5, 0x106Cu)) )
              {
                CBrowserFrame::_OpenUrlWithEdge(v41, (const unsigned __int16 *)v94 + 16);
                ppURI[0] = 0;
                if ( CreateUri((LPCWSTR)v94 + 16, 0x3002B80u, 0, ppURI) < 0 )
                  goto LABEL_76;
                bstrString = 0;
                v42 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI[0]->lpVtbl->GetHost)(ppURI[0], &bstrString);
                if ( v42 >= 0 )
                  BrowserTelemetry::IEOpenUrlWithEdge<enum OpenWithEdgeFrom &,ATL::CComBSTR &>(
                    (char *)v94 + 4200,
                    &bstrString);
                SysFreeString(bstrString);
                if ( v42 < 0 )
LABEL_76:
                  BrowserTelemetry::IEOpenUrlWithEdge<enum OpenWithEdgeFrom &,unsigned short const (&)[39]>((char *)v94 + 4200);
                ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ppURI);
              }
            }
          }
        }
      }
      else if ( a3 == 3086 )
      {
        CBrowserFrame::_HandleContextMenu((CBrowserFrame *)this, v5, v15);
      }
      else if ( a3 > 0x801 )
      {
        v30 = a3 - 2050;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            v32 = v31 - 1027;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                v34 = v33 - 3;
                if ( v34 )
                {
                  v35 = v34 - 2;
                  if ( v35 )
                  {
                    if ( v35 == 1 )
                      CBrowserFrame::_HandleNotifyITBarHolder((CBrowserFrame *)this, v5, v15);
                  }
                  else
                  {
                    CBrowserFrame::_HandleBrowserClose((CBrowserFrame *)this, v5, v15);
                  }
                }
                else
                {
                  CBrowserFrame::_HandleSetStatusBarState((CBrowserFrame *)this, v5, v15);
                }
              }
              else
              {
                CBrowserFrame::_HandleBrowserCreated((CBrowserFrame *)this, v5);
              }
            }
            else
            {
              CBrowserFrame::_HandleBrowserEvent((CBrowserFrame *)this, v5, v15);
            }
          }
          else
          {
            CBrowserFrame::_HandleActivateFindBar((CBrowserFrame *)this, v5, v15);
          }
        }
        else
        {
          CBrowserFrame::_HandleFavoritesBarChanged((CBrowserFrame *)this, v5, v15);
        }
      }
      else if ( a3 == 2049 )
      {
        CBrowserFrame::_HandleSignalAttention((CBrowserFrame *)this, v5, v15);
      }
      else
      {
        v16 = a3 - 1157;
        if ( v16 )
        {
          v17 = v16 - 76;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                v20 = v19 - 9;
                if ( v20 )
                {
                  v21 = v20 - 1;
                  if ( v21 )
                  {
                    if ( v21 == 1 )
                      CBrowserFrame::_HandleLoadedAddons((CBrowserFrame *)this, v5);
                  }
                  else
                  {
                    v22 = (struct _GUID *)TFlatIsoMessage<_GUID>::VerifyExactSize(v5, v12, v15);
                    if ( v22 )
                      AddonAdvisorUI::ShowActivationDialog(v22, (const struct _GUID *)0xA, v23);
                  }
                }
                else
                {
                  LODWORD(v94) = 0;
                  v24 = (const struct _GUID *)TArrayIsoMessage<_GUID>::VerifyArraySize(v5, &v94, v15);
                  if ( v24 && CAddonAdvisor::s_pAdvisor )
                    CAddonAdvisor::OnUnapprovedAddonsDetected(CAddonAdvisor::s_pAdvisor, v24, (int)v94);
                }
              }
              else
              {
                CBrowserFrame::_HandlePanningFeedbackEnd((CBrowserFrame *)this, v5, v15);
              }
            }
            else
            {
              CBrowserFrame::_HandlePanningFeedbackUpdate((CBrowserFrame *)this, v5, v15);
            }
          }
          else
          {
            CBrowserFrame::_HandlePanningFeedbackBegin((CBrowserFrame *)this, v5, v15);
          }
        }
        else if ( this[35] )
        {
          v25 = LCIEGetPICForIsoMessage(a2, v91);
          if ( v25 )
          {
            if ( v25 >= ((unsigned __int8)IsoArtifactInstanceIntegrityLevel(*((unsigned int *)this + 171)) & 0x7Fu) )
            {
              v26 = TFlatIsoMessage<IsoIdleTaskMsg>::VerifyExactSize(v5);
              if ( v26 )
              {
                switch ( *(_DWORD *)(v26 + 4) )
                {
                  case 0x3EC:
                    v27 = *(_QWORD **)(v26 + 24);
                    LODWORD(lParam) = 0;
                    v28 = (unsigned int (**)(void *))v27[7];
                    if ( (int)CWorkItemQueue::ScheduleWorkItem(v28[2], v27, 0, 0x10000008u, lParam) < 0 )
                      operator delete(v28);
                    break;
                  case 0x3EF:
                    if ( *(_DWORD *)(v26 + 8) == *((_DWORD *)this + 263) )
                      CStorageTelemetry::TraceLogStorageStart();
                    break;
                  case 0x3EA:
                    v29 = this[35];
                    if ( *((_DWORD *)v29 + 118) == *(_DWORD *)(v26 + 8) )
                    {
                      CTabWindowManager::EnsureEmptyTabForActiveTabProcess(this[35]);
                      IsoRemoveTask(*((_DWORD *)v29 + 94), *((_DWORD *)v29 + 118));
                      *((_DWORD *)v29 + 118) = 0;
                    }
                    break;
                }
              }
            }
          }
        }
      }
      goto LABEL_192;
    }
    if ( a3 == 3281 )
    {
      CBrowserFrame::_HandleUrlHoverText((CBrowserFrame *)this, v5, v15);
      goto LABEL_192;
    }
    if ( a3 > 0xCD1 )
    {
      if ( a3 > 0xD13 )
      {
        v67 = a3 - 3354;
        if ( v67 )
        {
          v68 = v67 - 19;
          if ( v68 )
          {
            v69 = v68 - 26;
            if ( v69 )
            {
              v70 = v69 - 137;
              if ( v70 )
              {
                v71 = v70 - 1584;
                if ( v71 )
                {
                  if ( v71 == 7 && *((_BYTE *)this + 1200) )
                  {
                    *((_BYTE *)this + 1200) = 0;
                    CDualEngineSimulatedInputQueue::_ProcessNextItem((CDualEngineSimulatedInputQueue *)(this + 149));
                  }
                }
                else
                {
                  v72 = this[132];
                  if ( v72 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v72 + 7) + 40LL))(
                      *((_QWORD *)v72 + 7),
                      v12,
                      v15);
                  v73 = this[133];
                  if ( v73 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v73 + 7) + 40LL))(
                      *((_QWORD *)v73 + 7),
                      v12,
                      v15);
                  v74 = this[134];
                  if ( v74 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v74 + 7) + 40LL))(
                      *((_QWORD *)v74 + 7),
                      v12,
                      v15);
                  v75 = this[135];
                  if ( v75 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v75 + 7) + 40LL))(
                      *((_QWORD *)v75 + 7),
                      v12,
                      v15);
                  v76 = this[136];
                  if ( v76 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v76 + 7) + 40LL))(
                      *((_QWORD *)v76 + 7),
                      v12,
                      v15);
                  v77 = this[137];
                  if ( v77 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v77 + 7) + 40LL))(
                      *((_QWORD *)v77 + 7),
                      v12,
                      v15);
                  v78 = this[138];
                  if ( v78 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v78 + 7) + 40LL))(
                      *((_QWORD *)v78 + 7),
                      v12,
                      v15);
                  v79 = this[139];
                  if ( v79 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v79 + 7) + 40LL))(
                      *((_QWORD *)v79 + 7),
                      v12,
                      v15);
                  v80 = this[140];
                  if ( v80 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v80 + 7) + 40LL))(
                      *((_QWORD *)v80 + 7),
                      v12,
                      v15);
                  v81 = this[141];
                  if ( v81 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v81 + 7) + 40LL))(
                      *((_QWORD *)v81 + 7),
                      v12,
                      v15);
                  v82 = this[142];
                  if ( v82 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v82 + 11) + 40LL))(
                      *((_QWORD *)v82 + 11),
                      v12,
                      v15);
                  v83 = this[143];
                  if ( v83 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v83 + 11) + 40LL))(
                      *((_QWORD *)v83 + 11),
                      v12,
                      v15);
                  v84 = this[144];
                  if ( v84 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v84 + 11) + 40LL))(
                      *((_QWORD *)v84 + 11),
                      v12,
                      v15);
                  v85 = this[145];
                  if ( v85 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v85 + 11) + 40LL))(
                      *((_QWORD *)v85 + 11),
                      v12,
                      v15);
                  v86 = this[146];
                  if ( v86 )
                    (*(void (__fastcall **)(_QWORD, __int64, _BOOL8))(**((_QWORD **)v86 + 11) + 40LL))(
                      *((_QWORD *)v86 + 11),
                      v12,
                      v15);
                  v87 = this[147];
                  if ( v87 )
                    CDualEngine20BrowserCoupling::OnFinishedSetFocus(v87);
                }
              }
              else
              {
                CBrowserFrame::_HandleSettingPublishChange(v13, v5, v15);
              }
            }
            else
            {
              OpenFeedbackHub(2);
            }
          }
          else
          {
            v88 = this[35];
            if ( v88 )
              CTabWindowManager::EnsureEmptyTabForActiveTabProcess(v88);
          }
        }
        else
        {
          CBrowserFrame::_HandleSetTrackingProtectionData((CBrowserFrame *)this, v5, v15);
        }
      }
      else if ( a3 == 3347 )
      {
        SetTimer((HWND)this[1], 0x5135u, 0x1388u, 0);
      }
      else
      {
        v60 = a3 - 3282;
        if ( v60 )
        {
          v61 = v60 - 11;
          if ( v61 )
          {
            v62 = v61 - 1;
            if ( v62 )
            {
              v63 = v62 - 6;
              if ( v63 )
              {
                v64 = v63 - 1;
                if ( v64 )
                {
                  v65 = v64 - 35;
                  if ( v65 )
                  {
                    if ( v65 == 6 )
                      CBrowserFrame::_OrganizeFavorites((CBrowserFrame *)this);
                  }
                  else
                  {
                    CBrowserFrame::_HandleShowAboutDialog((CBrowserFrame *)this, v5, v15);
                  }
                }
                else
                {
                  v66 = (_DWORD *)TFlatIsoMessage<LCIE_STARTLOWLEVELHOOK_DATA>::VerifyExactSize(v5);
                  if ( v66 )
                    CBrowserFrame::_SetMediaMode((CBrowserFrame *)this, *v66 != 0);
                }
              }
              else
              {
                CBrowserFrame::_HandleTheater((CBrowserFrame *)this, v5, v15);
              }
            }
            else
            {
              CBrowserFrame::_HandleSaveNavTime((CBrowserFrame *)this, v5);
            }
          }
          else
          {
            CBrowserFrame::_HandleSaveLoadTime(v13, v5);
          }
        }
        else
        {
          PostMessageW((HWND)this[1], 0x475u, 0, 0);
        }
      }
      goto LABEL_192;
    }
    if ( a3 > 0xC6F )
    {
      v55 = a3 - 3184;
      if ( !v55 )
      {
        CBrowserFrame::_HandleSetThumbbarButtons((CBrowserFrame *)this, v5, v15);
        goto LABEL_192;
      }
      v56 = v55 - 1;
      if ( !v56 )
      {
        CBrowserFrame::_HandleUpdateButtonStyle((CBrowserFrame *)this, v5, v15);
        goto LABEL_192;
      }
      v57 = v56 - 2;
      if ( !v57 )
      {
        CBrowserFrame::_HandleCreateTabAndNavigate((CBrowserFrame *)this, v5, v15);
        goto LABEL_192;
      }
      v58 = v57 - 2;
      if ( v58 )
      {
        v59 = v58 - 1;
        if ( v59 )
        {
          if ( v59 == 3 )
            CBrowserFrame::_HandleNavigateSelf((CBrowserFrame *)this, v5, v15);
        }
        else
        {
          CBrowserFrame::_HandleSetSiteModeFlashIcon((CBrowserFrame *)this, v5, v15);
        }
        goto LABEL_192;
      }
    }
    else
    {
      if ( a3 == 3183 )
      {
        CBrowserFrame::_HandleUpdateThumbbarButtons((CBrowserFrame *)this, v5, v15);
        goto LABEL_192;
      }
      v49 = a3 - 3159;
      if ( !v49 )
      {
        CBrowserFrame::_SyncLowLevelHookState((CBrowserFrame *)this);
        goto LABEL_192;
      }
      v50 = v49 - 3;
      if ( !v50 )
      {
        CBrowserFrame::_HandleSetSiteModeOverlayIcon((CBrowserFrame *)this, v5, v15);
        goto LABEL_192;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        CBrowserFrame::_HandleSetSiteModeProperties(v13, v5, v15);
        goto LABEL_192;
      }
      v52 = v51 - 1;
      if ( v52 )
      {
        v53 = v52 - 1;
        if ( v53 )
        {
          v54 = v53 - 1;
          if ( v54 )
          {
            if ( v54 == 16 )
              IELaunchAddonPerfAdvisorUI(this[1], 1, 0, 0);
          }
          else
          {
            CBrowserFrame::_HandleCreateSiteModeJumplist(v13, v5, v15);
          }
        }
        else
        {
          CBrowserFrame::_HandleAddSiteModeJumplistItem(v13, v5, v15);
        }
        goto LABEL_192;
      }
      CBrowserFrame::_HandleClearSiteModeJumplist(v13, v5, v15);
    }
    CBrowserFrame::_UpdateDestinationList(v13);
LABEL_192:
    *(_OWORD *)GlobalThreadState() = v10;
    *((_BYTE *)GlobalThreadState() + 16) = v11;
    goto LABEL_193;
  }
LABEL_194:
  *a5 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800304a4  push    rbp
0x1800304a6  push    rbx
0x1800304a7  push    rsi
0x1800304a8  push    rdi
0x1800304a9  push    r12
0x1800304ab  push    r13
0x1800304ad  push    r14
0x1800304af  push    r15
0x1800304b1  lea     rbp, [rsp-17h]
0x1800304b6  sub     rsp, 88h
0x1800304bd  xor     r13d, r13d
0x1800304c0  movaps  [rsp+0C0h+var_50], xmm6
0x1800304c5  movaps  [rsp+0C0h+var_60], xmm7
0x1800304ca  mov     rsi, r9
0x1800304cd  mov     rbx, r8
0x1800304d0  mov     r14d, edx
0x1800304d3  mov     rdi, rcx
0x1800304d6  test    r9, r9
0x1800304d9  jz      loc_180030F2B
0x1800304df  lea     r9, [rbp+4Fh+var_80]
0x1800304e3  mov     [rbp+4Fh+var_80], r13
0x1800304e7  xor     r8d, r8d
0x1800304ea  mov     [rsp+0C0h+lParam], r13
0x1800304ef  lea     edx, [r13+1]
0x1800304f3  mov     ecx, esi
0x1800304f5  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x1800304fc  nop     dword ptr [rax+rax+00h]
0x180030501  test    eax, eax
0x180030503  js      loc_180030F1D
0x180030509  mov     rax, [rbp+4Fh+var_80]
0x18003050d  movups  xmm6, xmmword ptr [rax+10h]
0x180030511  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180030518  nop     dword ptr [rax+rax+00h]
0x18003051d  movups  xmm7, xmmword ptr [rax]
0x180030520  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180030527  nop     dword ptr [rax+rax+00h]
0x18003052c  mov     r12b, [rax+10h]
0x180030530  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180030537  nop     dword ptr [rax+rax+00h]
0x18003053c  movdqu  xmmword ptr [rax], xmm6
0x180030540  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180030547  nop     dword ptr [rax+rax+00h]
0x18003054c  lea     ecx, [r13+3]
0x180030550  mov     byte ptr [rax+10h], 1
0x180030554  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x18003055b  nop     dword ptr [rax+rax+00h]
0x180030560  cmp     r14d, eax
0x180030563  mov     r15d, eax
0x180030566  mov     eax, 0C47h
0x18003056b  setz    r8b; bool
0x18003056f  cmp     ebx, eax
0x180030571  ja      loc_180030A81
0x180030577  jz      loc_180030A72
0x18003057d  mov     eax, 0C0Eh
0x180030582  cmp     ebx, eax
0x180030584  ja      loc_180030825
0x18003058a  jz      loc_180030816
0x180030590  mov     eax, 801h
0x180030595  cmp     ebx, eax
0x180030597  ja      loc_180030780
0x18003059d  jz      loc_180030771
0x1800305a3  sub     ebx, 485h
0x1800305a9  jz      loc_180030670
0x1800305af  sub     ebx, 4Ch ; 'L'
0x1800305b2  jz      loc_180030661
0x1800305b8  sub     ebx, 1
0x1800305bb  jz      loc_180030652
0x1800305c1  sub     ebx, 1
0x1800305c4  jz      short loc_180030643
0x1800305c6  sub     ebx, 9
0x1800305c9  jz      short loc_18003060A
0x1800305cb  sub     ebx, 1
0x1800305ce  jz      short loc_1800305E8
0x1800305d0  cmp     ebx, 1
0x1800305d3  jnz     loc_180030EFD
0x1800305d9  mov     edx, esi; unsigned int
0x1800305db  mov     rcx, rdi; this
0x1800305de  call    ?_HandleLoadedAddons@CBrowserFrame@@IEAAXK@Z; CBrowserFrame::_HandleLoadedAddons(ulong)
0x1800305e3  jmp     loc_180030EFD
0x1800305e8  mov     ecx, esi
0x1800305ea  call    ?VerifyExactSize@?$TFlatIsoMessage@U_GUID@@@@SAPEAU_GUID@@K@Z; TFlatIsoMessage<_GUID>::VerifyExactSize(ulong)
0x1800305ef  test    rax, rax
0x1800305f2  jz      loc_180030EFD
0x1800305f8  mov     edx, 0Ah; struct _GUID *
0x1800305fd  mov     rcx, rax; this
0x180030600  call    ?ShowActivationDialog@AddonAdvisorUI@@YAXAEBU_GUID@@K@Z; AddonAdvisorUI::ShowActivationDialog(_GUID const &,ulong)
0x180030605  jmp     loc_180030EFD
0x18003060a  lea     rdx, [rbp+4Fh+arg_18]
0x18003060e  mov     dword ptr [rbp+4Fh+arg_18], r13d
0x180030612  mov     ecx, esi
0x180030614  call    ?VerifyArraySize@?$TArrayIsoMessage@U_GUID@@@@SAPEAU_GUID@@KPEAK@Z; TArrayIsoMessage<_GUID>::VerifyArraySize(ulong,ulong *)
0x180030619  test    rax, rax
0x18003061c  jz      loc_180030EFD
0x180030622  mov     rcx, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; this
0x180030629  test    rcx, rcx
0x18003062c  jz      loc_180030EFD
0x180030632  mov     r8d, dword ptr [rbp+4Fh+arg_18]; int
0x180030636  mov     rdx, rax; struct _GUID *
0x180030639  call    ?OnUnapprovedAddonsDetected@CAddonAdvisor@@QEAAXQEBU_GUID@@H@Z; CAddonAdvisor::OnUnapprovedAddonsDetected(_GUID const * const,int)
0x18003063e  jmp     loc_180030EFD
0x180030643  mov     edx, esi; unsigned int
0x180030645  mov     rcx, rdi; this
0x180030648  call    ?_HandlePanningFeedbackEnd@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackEnd(ulong,bool)
0x18003064d  jmp     loc_180030EFD
0x180030652  mov     edx, esi; unsigned int
0x180030654  mov     rcx, rdi; this
0x180030657  call    ?_HandlePanningFeedbackUpdate@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackUpdate(ulong,bool)
0x18003065c  jmp     loc_180030EFD
0x180030661  mov     edx, esi; unsigned int
0x180030663  mov     rcx, rdi; this
0x180030666  call    ?_HandlePanningFeedbackBegin@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackBegin(ulong,bool)
0x18003066b  jmp     loc_180030EFD
0x180030670  cmp     [rdi+118h], r13
0x180030677  jz      loc_180030EFD
0x18003067d  mov     rdx, [rbp+4Fh+var_80]; struct _IsoMessage *
0x180030681  mov     ecx, r14d; unsigned int
0x180030684  call    ?LCIEGetPICForIsoMessage@@YAKIPEAU_IsoMessage@@@Z; LCIEGetPICForIsoMessage(uint,_IsoMessage *)
0x180030689  mov     ebx, eax
0x18003068b  test    eax, eax
0x18003068d  jz      loc_180030EFD
0x180030693  mov     ecx, [rdi+2ACh]
0x180030699  call    cs:__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z; IsoArtifactInstanceIntegrityLevel(ulong)
0x1800306a0  nop     dword ptr [rax+rax+00h]
0x1800306a5  and     eax, 7Fh
0x1800306a8  cmp     ebx, eax
0x1800306aa  jb      loc_180030EFD
0x1800306b0  mov     ecx, esi
0x1800306b2  call    ?VerifyExactSize@?$TFlatIsoMessage@UIsoIdleTaskMsg@@@@SAPEAUIsoIdleTaskMsg@@K@Z; TFlatIsoMessage<IsoIdleTaskMsg>::VerifyExactSize(ulong)
0x1800306b7  mov     rcx, rax
0x1800306ba  test    rax, rax
0x1800306bd  jz      loc_180030EFD
0x1800306c3  cmp     dword ptr [rax+4], 3ECh
0x1800306ca  jnz     short loc_180030700
0x1800306cc  mov     rdx, [rax+18h]; void *
0x1800306d0  mov     r9d, 10000008h; unsigned int
0x1800306d6  xor     r8d, r8d; int
0x1800306d9  mov     dword ptr [rsp+0C0h+lParam], r13d; lParam
0x1800306de  mov     rbx, [rdx+38h]
0x1800306e2  mov     rcx, [rbx+10h]; unsigned int (*)(void *)
0x1800306e6  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x1800306eb  test    eax, eax
0x1800306ed  jns     loc_180030EFD
0x1800306f3  mov     rcx, rbx; lpMem
0x1800306f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800306fb  jmp     loc_180030EFD
0x180030700  cmp     dword ptr [rax+4], 3EFh
0x180030707  jnz     short loc_180030722
0x180030709  mov     eax, [rdi+41Ch]
0x18003070f  cmp     [rcx+8], eax
0x180030712  jnz     loc_180030EFD
0x180030718  call    ?TraceLogStorageStart@CStorageTelemetry@@SAXXZ; CStorageTelemetry::TraceLogStorageStart(void)
0x18003071d  jmp     loc_180030EFD
0x180030722  cmp     dword ptr [rax+4], 3EAh
0x180030729  jnz     loc_180030EFD
0x18003072f  mov     rbx, [rdi+118h]
0x180030736  mov     eax, [rax+8]
0x180030739  cmp     [rbx+1D8h], eax
0x18003073f  jnz     loc_180030EFD
0x180030745  mov     rcx, rbx; this
0x180030748  call    ?EnsureEmptyTabForActiveTabProcess@CTabWindowManager@@QEAAJXZ; CTabWindowManager::EnsureEmptyTabForActiveTabProcess(void)
0x18003074d  mov     edx, [rbx+1D8h]
0x180030753  mov     ecx, [rbx+178h]
0x180030759  call    cs:__imp_?IsoRemoveTask@@YAJKK@Z; IsoRemoveTask(ulong,ulong)
0x180030760  nop     dword ptr [rax+rax+00h]
0x180030765  mov     [rbx+1D8h], r13d
0x18003076c  jmp     loc_180030EFD
0x180030771  mov     edx, esi; unsigned int
0x180030773  mov     rcx, rdi; this
0x180030776  call    ?_HandleSignalAttention@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSignalAttention(ulong,bool)
0x18003077b  jmp     loc_180030EFD
0x180030780  sub     ebx, 802h
0x180030786  jz      short loc_180030807
0x180030788  sub     ebx, 1
0x18003078b  jz      short loc_1800307F8
0x18003078d  sub     ebx, 403h
0x180030793  jz      short loc_1800307E9
0x180030795  sub     ebx, 1
0x180030798  jz      short loc_1800307DA
0x18003079a  sub     ebx, 3
0x18003079d  jz      short loc_1800307CB
0x18003079f  sub     ebx, 2
0x1800307a2  jz      short loc_1800307BC
0x1800307a4  cmp     ebx, 1
0x1800307a7  jnz     loc_180030EFD
0x1800307ad  mov     edx, esi; unsigned int
0x1800307af  mov     rcx, rdi; this
0x1800307b2  call    ?_HandleNotifyITBarHolder@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleNotifyITBarHolder(ulong,bool)
0x1800307b7  jmp     loc_180030EFD
0x1800307bc  mov     edx, esi; unsigned int
0x1800307be  mov     rcx, rdi; this
0x1800307c1  call    ?_HandleBrowserClose@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleBrowserClose(ulong,bool)
0x1800307c6  jmp     loc_180030EFD
0x1800307cb  mov     edx, esi; unsigned int
0x1800307cd  mov     rcx, rdi; this
0x1800307d0  call    ?_HandleSetStatusBarState@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSetStatusBarState(ulong,bool)
0x1800307d5  jmp     loc_180030EFD
0x1800307da  mov     edx, esi; unsigned int
0x1800307dc  mov     rcx, rdi; this
0x1800307df  call    ?_HandleBrowserCreated@CBrowserFrame@@IEAAXK@Z; CBrowserFrame::_HandleBrowserCreated(ulong)
0x1800307e4  jmp     loc_180030EFD
0x1800307e9  mov     edx, esi; unsigned int
0x1800307eb  mov     rcx, rdi; this
0x1800307ee  call    ?_HandleBrowserEvent@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleBrowserEvent(ulong,bool)
0x1800307f3  jmp     loc_180030EFD
0x1800307f8  mov     edx, esi; unsigned int
0x1800307fa  mov     rcx, rdi; this
0x1800307fd  call    ?_HandleActivateFindBar@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleActivateFindBar(ulong,bool)
0x180030802  jmp     loc_180030EFD
0x180030807  mov     edx, esi; unsigned int
0x180030809  mov     rcx, rdi; this
0x18003080c  call    ?_HandleFavoritesBarChanged@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleFavoritesBarChanged(ulong,bool)
0x180030811  jmp     loc_180030EFD
0x180030816  mov     edx, esi; unsigned int
0x180030818  mov     rcx, rdi; this
0x18003081b  call    ?_HandleContextMenu@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleContextMenu(ulong,bool)
0x180030820  jmp     loc_180030EFD
0x180030825  mov     eax, 0C40h
0x18003082a  cmp     ebx, eax
0x18003082c  ja      loc_180030EFD
0x180030832  jz      loc_180030A25
0x180030838  mov     eax, 0C15h
0x18003083d  cmp     ebx, eax
0x18003083f  ja      loc_1800309A8
0x180030845  jz      loc_180030999
0x18003084b  sub     ebx, 0C0Fh
0x180030851  jz      short loc_1800308B6
0x180030853  sub     ebx, 1
0x180030856  jz      short loc_1800308A9
0x180030858  sub     ebx, 1
0x18003085b  jz      short loc_18003089A
0x18003085d  sub     ebx, 1
0x180030860  jz      short loc_18003088E
0x180030862  sub     ebx, 1
0x180030865  jz      short loc_18003087F
0x180030867  cmp     ebx, 1
0x18003086a  jnz     loc_180030EFD
0x180030870  mov     edx, esi; unsigned int
0x180030872  mov     rcx, rdi; this
0x180030875  call    ?_HandleSelectTab@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSelectTab(ulong,bool)
0x18003087a  jmp     loc_180030EFD
0x18003087f  mov     edx, esi; unsigned int
0x180030881  mov     rcx, rdi; this
0x180030884  call    ?_HandleShowManagedAddOns@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleShowManagedAddOns(ulong,bool)
0x180030889  jmp     loc_180030EFD
0x18003088e  mov     edx, esi; unsigned int
0x180030890  call    ?_HandleClsIdCreated@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleClsIdCreated(ulong,bool)
0x180030895  jmp     loc_180030EFD
0x18003089a  mov     edx, esi; unsigned int
0x18003089c  mov     rcx, rdi; this
0x18003089f  call    ?_HandleAppCommand@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleAppCommand(ulong,bool)
0x1800308a4  jmp     loc_180030EFD
0x1800308a9  mov     rcx, rdi; this
0x1800308ac  call    ?_HandleEnableAutoCompleteNotification@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_HandleEnableAutoCompleteNotification(void)
0x1800308b1  jmp     loc_180030EFD
0x1800308b6  xor     r8d, r8d
0x1800308b9  mov     [rbp+4Fh+arg_18], r13
0x1800308bd  lea     r9, [rbp+4Fh+arg_18]
0x1800308c1  mov     [rsp+0C0h+lParam], r13
0x1800308c6  mov     ecx, esi
0x1800308c8  lea     edx, [r8+1]
0x1800308cc  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x1800308d3  nop     dword ptr [rax+rax+00h]
0x1800308d8  test    eax, eax
0x1800308da  js      loc_180030EFD
0x1800308e0  cmp     r14d, r15d
0x1800308e3  jnz     short loc_180030900
0x1800308e5  mov     edx, 106Ch
0x1800308ea  mov     ecx, esi
0x1800308ec  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x1800308f3  nop     dword ptr [rax+rax+00h]
0x1800308f8  test    al, al
0x1800308fa  jz      loc_180030EFD
0x180030900  mov     rdx, [rbp+4Fh+arg_18]
0x180030904  add     rdx, 20h ; ' '; unsigned __int16 *
0x180030908  call    ?_OpenUrlWithEdge@CBrowserFrame@@IEAAJPEBG@Z; CBrowserFrame::_OpenUrlWithEdge(ushort const *)
0x18003090d  mov     rcx, [rbp+4Fh+arg_18]
0x180030911  lea     r9, [rbp+4Fh+ppURI]; ppURI
0x180030915  add     rcx, 20h ; ' '; pwzURI
0x180030919  mov     [rbp+4Fh+ppURI], r13
0x18003091d  xor     r8d, r8d; dwReserved
0x180030920  mov     edx, 3002B80h; dwFlags
0x180030925  call    cs:__imp_CreateUri
0x18003092c  nop     dword ptr [rax+rax+00h]
0x180030931  test    eax, eax
0x180030933  js      short loc_18003097B
0x180030935  mov     rcx, [rbp+4Fh+ppURI]
0x180030939  lea     rdx, [rbp+4Fh+bstrString]
0x18003093d  mov     [rbp+4Fh+bstrString], r13
0x180030941  mov     rax, [rcx]
0x180030944  mov     rax, [rax+68h]
0x180030948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003094d  mov     ebx, eax
0x18003094f  test    eax, eax
0x180030951  js      short loc_180030967
0x180030953  mov     rcx, [rbp+4Fh+arg_18]
0x180030957  lea     rdx, [rbp+4Fh+bstrString]
0x18003095b  add     rcx, 1068h
0x180030962  call    ??$IEOpenUrlWithEdge@AEAW4OpenWithEdgeFrom@@AEAVCComBSTR@ATL@@@BrowserTelemetry@@SAXAEAW4OpenWithEdgeFrom@@AEAVCComBSTR@ATL@@@Z; BrowserTelemetry::IEOpenUrlWithEdge<OpenWithEdgeFrom &,ATL::CComBSTR &>(OpenWithEdgeFrom &,ATL::CComBSTR &)
0x180030967  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x18003096b  call    cs:__imp_SysFreeString
  ... truncated ...
```
