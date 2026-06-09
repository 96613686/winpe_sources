# CBrowserFrame::_FrameLCIEWndProc(uint,unsigned __int64,__int64,int *)

- ea: `0x180029870`
- end: `0x18002a2bb`
- name: `?_FrameLCIEWndProc@CBrowserFrame@@IEAA_JI_K_JPEAH@Z`
- size: `2635`
- prototype: `__int64 __usercall@<rax>(CBrowserFrame *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `70`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180035840`

## callees

- `0x18000b9e0`
- `0x18000c5c0`
- `0x180028680`
- `0x180029870`
- `0x18002a894`
- `0x18007bee0`
- `0x18008ddf4`
- `0x180093e28`
- `0x180099d10`
- `0x1801ba544`
- `0x1801bd118`
- `0x1801bd178`
- `0x180228680`
- `0x180228738`
- `0x180234d40`
- `0x18023801c`
- `0x180238104`
- `0x1802385cc`
- `0x18023867c`
- `0x180238710`
- `0x18023879c`
- `0x180238824`
- `0x180238890`
- `0x1802389b8`
- `0x180238a70`
- `0x180238b00`
- `0x180238fb8`
- `0x180239110`
- `0x180239304`
- `0x18023951c`
- `0x180239748`
- `0x1802398c4`
- `0x180239aa0`
- `0x180239ae8`
- `0x180239cc0`
- `0x180239d8c`
- `0x180239e34`
- `0x18023a15c`
- `0x18023a1e0`
- `0x18023a360`
- `0x18023a478`
- `0x18023a590`
- `0x18023a628`
- `0x18023a6b0`
- `0x18023a838`
- `0x18023a930`
- `0x18023a9ac`
- `0x18023aa68`
- `0x18023aad8`
- `0x18023ab54`

## import_xrefs

- `USER32!SetTimer` at `0x18002a024`
- `USER32!SetTimer` at `0x18002a024`
- `USER32!PostMessageW` at `0x18002a007`
- `USER32!PostMessageW` at `0x18002a007`
- `OLEAUT32!__imp_SysFreeString` at `0x180029cf5`
- `OLEAUT32!__imp_SysFreeString` at `0x180029cf5`
- `iertutil!CreateUri` at `0x180029cb5`
- `iertutil!CreateUri` at `0x180029cb5`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180029c82`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180029c82`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180029a41`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180029a41`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180029902`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180029902`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800298c1`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180029c68`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1800298c1`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180029c68`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18002a28b`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18002a28b`
- `msIso!__imp_?IsoRemoveTask@@YAJKK@Z` at `0x180029afb`
- `msIso!__imp_?IsoRemoveTask@@YAJKK@Z` at `0x180029afb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298d7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298e0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298ea`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18002a275`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18002a27f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298d7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298e0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298ea`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800298f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18002a275`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18002a27f`

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
0x180029870  push    rbp
0x180029872  push    rbx
0x180029873  push    rsi
0x180029874  push    rdi
0x180029875  push    r12
0x180029877  push    r13
0x180029879  push    r14
0x18002987b  push    r15
0x18002987d  lea     rbp, [rsp-17h]
0x180029882  sub     rsp, 88h
0x180029889  xor     r13d, r13d
0x18002988c  movaps  [rsp+0C0h+var_50], xmm6
0x180029891  movaps  [rsp+0C0h+var_60], xmm7
0x180029896  mov     rsi, r9
0x180029899  mov     rbx, r8
0x18002989c  mov     r14d, edx
0x18002989f  mov     rdi, rcx
0x1800298a2  test    r9, r9
0x1800298a5  jz      loc_18002A291
0x1800298ab  lea     r9, [rbp+4Fh+var_80]
0x1800298af  mov     [rbp+4Fh+var_80], r13
0x1800298b3  xor     r8d, r8d
0x1800298b6  mov     [rsp+0C0h+lParam], r13
0x1800298bb  lea     edx, [r13+1]
0x1800298bf  mov     ecx, esi
0x1800298c1  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x1800298c7  test    eax, eax
0x1800298c9  js      loc_18002A289
0x1800298cf  mov     rax, [rbp+4Fh+var_80]
0x1800298d3  movups  xmm6, xmmword ptr [rax+10h]
0x1800298d7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800298dd  movups  xmm7, xmmword ptr [rax]
0x1800298e0  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800298e6  mov     r12b, [rax+10h]
0x1800298ea  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800298f0  movdqu  xmmword ptr [rax], xmm6
0x1800298f4  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800298fa  lea     ecx, [r13+3]
0x1800298fe  mov     byte ptr [rax+10h], 1
0x180029902  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x180029908  cmp     r14d, eax
0x18002990b  mov     r15d, eax
0x18002990e  mov     eax, 0C47h
0x180029913  setz    r8b; bool
0x180029917  cmp     ebx, eax
0x180029919  ja      loc_180029E05
0x18002991f  jz      loc_180029DF6
0x180029925  mov     eax, 0C0Eh
0x18002992a  cmp     ebx, eax
0x18002992c  ja      loc_180029BC1
0x180029932  jz      loc_180029BB2
0x180029938  mov     eax, 801h
0x18002993d  cmp     ebx, eax
0x18002993f  ja      loc_180029B1C
0x180029945  jz      loc_180029B0D
0x18002994b  sub     ebx, 485h
0x180029951  jz      loc_180029A18
0x180029957  sub     ebx, 4Ch ; 'L'
0x18002995a  jz      loc_180029A09
0x180029960  sub     ebx, 1
0x180029963  jz      loc_1800299FA
0x180029969  sub     ebx, 1
0x18002996c  jz      short loc_1800299EB
0x18002996e  sub     ebx, 9
0x180029971  jz      short loc_1800299B2
0x180029973  sub     ebx, 1
0x180029976  jz      short loc_180029990
0x180029978  cmp     ebx, 1
0x18002997b  jnz     loc_18002A275
0x180029981  mov     edx, esi; unsigned int
0x180029983  mov     rcx, rdi; this
0x180029986  call    ?_HandleLoadedAddons@CBrowserFrame@@IEAAXK@Z; CBrowserFrame::_HandleLoadedAddons(ulong)
0x18002998b  jmp     loc_18002A275
0x180029990  mov     ecx, esi
0x180029992  call    ?VerifyExactSize@?$TFlatIsoMessage@U_GUID@@@@SAPEAU_GUID@@K@Z; TFlatIsoMessage<_GUID>::VerifyExactSize(ulong)
0x180029997  test    rax, rax
0x18002999a  jz      loc_18002A275
0x1800299a0  mov     edx, 0Ah; struct _GUID *
0x1800299a5  mov     rcx, rax; this
0x1800299a8  call    ?ShowActivationDialog@AddonAdvisorUI@@YAXAEBU_GUID@@K@Z; AddonAdvisorUI::ShowActivationDialog(_GUID const &,ulong)
0x1800299ad  jmp     loc_18002A275
0x1800299b2  lea     rdx, [rbp+4Fh+arg_18]
0x1800299b6  mov     dword ptr [rbp+4Fh+arg_18], r13d
0x1800299ba  mov     ecx, esi
0x1800299bc  call    ?VerifyArraySize@?$TArrayIsoMessage@U_GUID@@@@SAPEAU_GUID@@KPEAK@Z; TArrayIsoMessage<_GUID>::VerifyArraySize(ulong,ulong *)
0x1800299c1  test    rax, rax
0x1800299c4  jz      loc_18002A275
0x1800299ca  mov     rcx, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; this
0x1800299d1  test    rcx, rcx
0x1800299d4  jz      loc_18002A275
0x1800299da  mov     r8d, dword ptr [rbp+4Fh+arg_18]; int
0x1800299de  mov     rdx, rax; struct _GUID *
0x1800299e1  call    ?OnUnapprovedAddonsDetected@CAddonAdvisor@@QEAAXQEBU_GUID@@H@Z; CAddonAdvisor::OnUnapprovedAddonsDetected(_GUID const * const,int)
0x1800299e6  jmp     loc_18002A275
0x1800299eb  mov     edx, esi; unsigned int
0x1800299ed  mov     rcx, rdi; this
0x1800299f0  call    ?_HandlePanningFeedbackEnd@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackEnd(ulong,bool)
0x1800299f5  jmp     loc_18002A275
0x1800299fa  mov     edx, esi; unsigned int
0x1800299fc  mov     rcx, rdi; this
0x1800299ff  call    ?_HandlePanningFeedbackUpdate@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackUpdate(ulong,bool)
0x180029a04  jmp     loc_18002A275
0x180029a09  mov     edx, esi; unsigned int
0x180029a0b  mov     rcx, rdi; this
0x180029a0e  call    ?_HandlePanningFeedbackBegin@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandlePanningFeedbackBegin(ulong,bool)
0x180029a13  jmp     loc_18002A275
0x180029a18  cmp     [rdi+118h], r13
0x180029a1f  jz      loc_18002A275
0x180029a25  mov     rdx, [rbp+4Fh+var_80]; struct _IsoMessage *
0x180029a29  mov     ecx, r14d; unsigned int
0x180029a2c  call    ?LCIEGetPICForIsoMessage@@YAKIPEAU_IsoMessage@@@Z; LCIEGetPICForIsoMessage(uint,_IsoMessage *)
0x180029a31  mov     ebx, eax
0x180029a33  test    eax, eax
0x180029a35  jz      loc_18002A275
0x180029a3b  mov     ecx, [rdi+2ACh]
0x180029a41  call    cs:__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z; IsoArtifactInstanceIntegrityLevel(ulong)
0x180029a47  and     eax, 7Fh
0x180029a4a  cmp     ebx, eax
0x180029a4c  jb      loc_18002A275
0x180029a52  mov     ecx, esi
0x180029a54  call    ?VerifyExactSize@?$TFlatIsoMessage@UIsoIdleTaskMsg@@@@SAPEAUIsoIdleTaskMsg@@K@Z; TFlatIsoMessage<IsoIdleTaskMsg>::VerifyExactSize(ulong)
0x180029a59  mov     rcx, rax
0x180029a5c  test    rax, rax
0x180029a5f  jz      loc_18002A275
0x180029a65  cmp     dword ptr [rax+4], 3ECh
0x180029a6c  jnz     short loc_180029AA2
0x180029a6e  mov     rdx, [rax+18h]; void *
0x180029a72  mov     r9d, 10000008h; unsigned int
0x180029a78  xor     r8d, r8d; int
0x180029a7b  mov     dword ptr [rsp+0C0h+lParam], r13d; lParam
0x180029a80  mov     rbx, [rdx+38h]
0x180029a84  mov     rcx, [rbx+10h]; unsigned int (*)(void *)
0x180029a88  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x180029a8d  test    eax, eax
0x180029a8f  jns     loc_18002A275
0x180029a95  mov     rcx, rbx; lpMem
0x180029a98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029a9d  jmp     loc_18002A275
0x180029aa2  cmp     dword ptr [rax+4], 3EFh
0x180029aa9  jnz     short loc_180029AC4
0x180029aab  mov     eax, [rdi+41Ch]
0x180029ab1  cmp     [rcx+8], eax
0x180029ab4  jnz     loc_18002A275
0x180029aba  call    ?TraceLogStorageStart@CStorageTelemetry@@SAXXZ; CStorageTelemetry::TraceLogStorageStart(void)
0x180029abf  jmp     loc_18002A275
0x180029ac4  cmp     dword ptr [rax+4], 3EAh
0x180029acb  jnz     loc_18002A275
0x180029ad1  mov     rbx, [rdi+118h]
0x180029ad8  mov     eax, [rax+8]
0x180029adb  cmp     [rbx+1D8h], eax
0x180029ae1  jnz     loc_18002A275
0x180029ae7  mov     rcx, rbx; this
0x180029aea  call    ?EnsureEmptyTabForActiveTabProcess@CTabWindowManager@@QEAAJXZ; CTabWindowManager::EnsureEmptyTabForActiveTabProcess(void)
0x180029aef  mov     edx, [rbx+1D8h]
0x180029af5  mov     ecx, [rbx+178h]
0x180029afb  call    cs:__imp_?IsoRemoveTask@@YAJKK@Z; IsoRemoveTask(ulong,ulong)
0x180029b01  mov     [rbx+1D8h], r13d
0x180029b08  jmp     loc_18002A275
0x180029b0d  mov     edx, esi; unsigned int
0x180029b0f  mov     rcx, rdi; this
0x180029b12  call    ?_HandleSignalAttention@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSignalAttention(ulong,bool)
0x180029b17  jmp     loc_18002A275
0x180029b1c  sub     ebx, 802h
0x180029b22  jz      short loc_180029BA3
0x180029b24  sub     ebx, 1
0x180029b27  jz      short loc_180029B94
0x180029b29  sub     ebx, 403h
0x180029b2f  jz      short loc_180029B85
0x180029b31  sub     ebx, 1
0x180029b34  jz      short loc_180029B76
0x180029b36  sub     ebx, 3
0x180029b39  jz      short loc_180029B67
0x180029b3b  sub     ebx, 2
0x180029b3e  jz      short loc_180029B58
0x180029b40  cmp     ebx, 1
0x180029b43  jnz     loc_18002A275
0x180029b49  mov     edx, esi; unsigned int
0x180029b4b  mov     rcx, rdi; this
0x180029b4e  call    ?_HandleNotifyITBarHolder@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleNotifyITBarHolder(ulong,bool)
0x180029b53  jmp     loc_18002A275
0x180029b58  mov     edx, esi; unsigned int
0x180029b5a  mov     rcx, rdi; this
0x180029b5d  call    ?_HandleBrowserClose@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleBrowserClose(ulong,bool)
0x180029b62  jmp     loc_18002A275
0x180029b67  mov     edx, esi; unsigned int
0x180029b69  mov     rcx, rdi; this
0x180029b6c  call    ?_HandleSetStatusBarState@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSetStatusBarState(ulong,bool)
0x180029b71  jmp     loc_18002A275
0x180029b76  mov     edx, esi; unsigned int
0x180029b78  mov     rcx, rdi; this
0x180029b7b  call    ?_HandleBrowserCreated@CBrowserFrame@@IEAAXK@Z; CBrowserFrame::_HandleBrowserCreated(ulong)
0x180029b80  jmp     loc_18002A275
0x180029b85  mov     edx, esi; unsigned int
0x180029b87  mov     rcx, rdi; this
0x180029b8a  call    ?_HandleBrowserEvent@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleBrowserEvent(ulong,bool)
0x180029b8f  jmp     loc_18002A275
0x180029b94  mov     edx, esi; unsigned int
0x180029b96  mov     rcx, rdi; this
0x180029b99  call    ?_HandleActivateFindBar@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleActivateFindBar(ulong,bool)
0x180029b9e  jmp     loc_18002A275
0x180029ba3  mov     edx, esi; unsigned int
0x180029ba5  mov     rcx, rdi; this
0x180029ba8  call    ?_HandleFavoritesBarChanged@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleFavoritesBarChanged(ulong,bool)
0x180029bad  jmp     loc_18002A275
0x180029bb2  mov     edx, esi; unsigned int
0x180029bb4  mov     rcx, rdi; this
0x180029bb7  call    ?_HandleContextMenu@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleContextMenu(ulong,bool)
0x180029bbc  jmp     loc_18002A275
0x180029bc1  mov     eax, 0C40h
0x180029bc6  cmp     ebx, eax
0x180029bc8  ja      loc_18002A275
0x180029bce  jz      loc_180029DA9
0x180029bd4  mov     eax, 0C15h
0x180029bd9  cmp     ebx, eax
0x180029bdb  ja      loc_180029D2C
0x180029be1  jz      loc_180029D1D
0x180029be7  sub     ebx, 0C0Fh
0x180029bed  jz      short loc_180029C52
0x180029bef  sub     ebx, 1
0x180029bf2  jz      short loc_180029C45
0x180029bf4  sub     ebx, 1
0x180029bf7  jz      short loc_180029C36
0x180029bf9  sub     ebx, 1
0x180029bfc  jz      short loc_180029C2A
0x180029bfe  sub     ebx, 1
0x180029c01  jz      short loc_180029C1B
0x180029c03  cmp     ebx, 1
0x180029c06  jnz     loc_18002A275
0x180029c0c  mov     edx, esi; unsigned int
0x180029c0e  mov     rcx, rdi; this
0x180029c11  call    ?_HandleSelectTab@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSelectTab(ulong,bool)
0x180029c16  jmp     loc_18002A275
0x180029c1b  mov     edx, esi; unsigned int
0x180029c1d  mov     rcx, rdi; this
0x180029c20  call    ?_HandleShowManagedAddOns@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleShowManagedAddOns(ulong,bool)
0x180029c25  jmp     loc_18002A275
0x180029c2a  mov     edx, esi; unsigned int
0x180029c2c  call    ?_HandleClsIdCreated@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleClsIdCreated(ulong,bool)
0x180029c31  jmp     loc_18002A275
0x180029c36  mov     edx, esi; unsigned int
0x180029c38  mov     rcx, rdi; this
0x180029c3b  call    ?_HandleAppCommand@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleAppCommand(ulong,bool)
0x180029c40  jmp     loc_18002A275
0x180029c45  mov     rcx, rdi; this
0x180029c48  call    ?_HandleEnableAutoCompleteNotification@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_HandleEnableAutoCompleteNotification(void)
0x180029c4d  jmp     loc_18002A275
0x180029c52  xor     r8d, r8d
0x180029c55  mov     [rbp+4Fh+arg_18], r13
0x180029c59  lea     r9, [rbp+4Fh+arg_18]
0x180029c5d  mov     [rsp+0C0h+lParam], r13
0x180029c62  mov     ecx, esi
0x180029c64  lea     edx, [r8+1]
0x180029c68  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x180029c6e  test    eax, eax
0x180029c70  js      loc_18002A275
0x180029c76  cmp     r14d, r15d
0x180029c79  jnz     short loc_180029C90
0x180029c7b  mov     edx, 106Ch
0x180029c80  mov     ecx, esi
0x180029c82  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x180029c88  test    al, al
0x180029c8a  jz      loc_18002A275
0x180029c90  mov     rdx, [rbp+4Fh+arg_18]
0x180029c94  add     rdx, 20h ; ' '; unsigned __int16 *
0x180029c98  call    ?_OpenUrlWithEdge@CBrowserFrame@@IEAAJPEBG@Z; CBrowserFrame::_OpenUrlWithEdge(ushort const *)
0x180029c9d  mov     rcx, [rbp+4Fh+arg_18]
0x180029ca1  lea     r9, [rbp+4Fh+ppURI]; ppURI
0x180029ca5  add     rcx, 20h ; ' '; pwzURI
0x180029ca9  mov     [rbp+4Fh+ppURI], r13
0x180029cad  xor     r8d, r8d; dwReserved
0x180029cb0  mov     edx, 3002B80h; dwFlags
0x180029cb5  call    cs:__imp_CreateUri
0x180029cbb  test    eax, eax
0x180029cbd  js      short loc_180029CFF
0x180029cbf  mov     rcx, [rbp+4Fh+ppURI]
0x180029cc3  lea     rdx, [rbp+4Fh+bstrString]
0x180029cc7  mov     [rbp+4Fh+bstrString], r13
0x180029ccb  mov     rax, [rcx]
0x180029cce  mov     rax, [rax+68h]
0x180029cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cd7  mov     ebx, eax
0x180029cd9  test    eax, eax
0x180029cdb  js      short loc_180029CF1
0x180029cdd  mov     rcx, [rbp+4Fh+arg_18]
0x180029ce1  lea     rdx, [rbp+4Fh+bstrString]
0x180029ce5  add     rcx, 1068h
0x180029cec  call    ??$IEOpenUrlWithEdge@AEAW4OpenWithEdgeFrom@@AEAVCComBSTR@ATL@@@BrowserTelemetry@@SAXAEAW4OpenWithEdgeFrom@@AEAVCComBSTR@ATL@@@Z; BrowserTelemetry::IEOpenUrlWithEdge<OpenWithEdgeFrom &,ATL::CComBSTR &>(OpenWithEdgeFrom &,ATL::CComBSTR &)
0x180029cf1  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180029cf5  call    cs:__imp_SysFreeString
0x180029cfb  test    ebx, ebx
0x180029cfd  jns     short loc_180029D0F
0x180029cff  mov     rcx, [rbp+4Fh+arg_18]
0x180029d03  add     rcx, 1068h
0x180029d0a  call    ??$IEOpenUrlWithEdge@AEAW4OpenWithEdgeFrom@@AEAY0CH@$$CBG@BrowserTelemetry@@SAXAEAW4OpenWithEdgeFrom@@AEAY0CH@$$CBG@Z; BrowserTelemetry::IEOpenUrlWithEdge<OpenWithEdgeFrom &,ushort const (&)[39]>(OpenWithEdgeFrom &,ushort const (&)[39])
0x180029d0f  lea     rcx, [rbp+4Fh+ppURI]; void *
0x180029d13  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180029d18  jmp     loc_18002A275
0x180029d1d  mov     edx, esi; unsigned int
0x180029d1f  mov     rcx, rdi; this
0x180029d22  call    ?_HandleSysCommand@CBrowserFrame@@IEAAXK_N@Z; CBrowserFrame::_HandleSysCommand(ulong,bool)
  ... truncated ...
```
