# COmWindowProxy::ExecRefresh(long,uint,CPSRCE)

- ea: `0x180826508`
- end: `0x18082704e`
- name: `?ExecRefresh@COmWindowProxy@@QEAAJJIW4CPSRCE@@@Z`
- size: `2886`
- prototype: ``
- caller_count: `8`
- callee_count: `57`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180225dc0`
- `0x1806d3d68`
- `0x180826078`
- `0x1808261bc`
- `0x1808c1ab0`
- `0x180c7b500`
- `0x180e40950`
- `0x181051874`

## callees

- `0x180012c04`
- `0x1800c2b18`
- `0x1800de220`
- `0x1800df4c4`
- `0x18010e97c`
- `0x18011f0ac`
- `0x18011fca0`
- `0x180135278`
- `0x180144d1c`
- `0x180154a54`
- `0x1801bffb8`
- `0x1801cd5ac`
- `0x18021d508`
- `0x180223a8c`
- `0x1802a05ac`
- `0x18030035c`
- `0x18034bea8`
- `0x18034cfe4`
- `0x180369bc0`
- `0x1803741b8`
- `0x18043c328`
- `0x1804925d0`
- `0x1804e140c`
- `0x1804e3194`
- `0x1804e6290`
- `0x1804f594c`
- `0x1804f609c`
- `0x1804fa5e0`
- `0x180517578`
- `0x18051a3bc`
- `0x180555874`
- `0x1805fa7a4`
- `0x1806009e8`
- `0x1806384e0`
- `0x18063be44`
- `0x18064647c`
- `0x180646b8c`
- `0x1806d1a90`
- `0x1806de738`
- `0x180739ec0`
- `0x18073b7c8`
- `0x1807bef9c`
- `0x1807e0564`
- `0x1807e14d0`
- `0x1807f6190`
- `0x180811274`
- `0x180826508`
- `0x1808349dc`
- `0x1808393c4`
- `0x1808456d4`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082685e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180826bb1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082685e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180826bb1`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180826930`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180826930`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d1e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d3d`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d5b`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d79`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d97`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826db6`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d1e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d3d`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d5b`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d79`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826d97`
- `urlmon!CoInternetSetFeatureEnabled` at `0x180826db6`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18082670d`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18082670d`
- `OLEAUT32!__imp_SysAllocString` at `0x180826623`
- `OLEAUT32!__imp_SysAllocString` at `0x180826623`
- `OLEAUT32!__imp_SysFreeString` at `0x18082665d`
- `OLEAUT32!__imp_SysFreeString` at `0x18082665d`

## pseudocode

```c
__int64 __fastcall COmWindowProxy::ExecRefresh(__int64 a1, int a2, int a3, int a4)
{
  unsigned int HistoryInternal; // ebx
  bool v6; // zf
  CWindow **v7; // r13
  CMarkup *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rdi
  char v11; // r12
  void (__fastcall *v12)(CMarkup *); // rax
  OLECHAR *ErrorPageRefreshUrl; // r15
  CWebOCEvents *v14; // rcx
  unsigned __int16 *v15; // r13
  CMarkup *v16; // rcx
  CWindow *v17; // rbx
  CMarkup *v18; // rcx
  struct CDwnPost *ErrorPageDwnPost; // rax
  __int64 v20; // rdx
  struct CMarkup *v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  struct IUnknown *v24; // rcx
  unsigned int v25; // r13d
  CMarkup *v26; // rcx
  CMarkup *v27; // rcx
  int v28; // eax
  struct CRootElement *v29; // rax
  CElement *ActiveElement; // rax
  CElement *v31; // rax
  struct CTimeManager *TimeManager; // r15
  CMSPerformanceData *v33; // rax
  CMSPerformanceData *v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  CTimeManager *v39; // rcx
  int lpVtbl; // ebx
  int v41; // edx
  int v42; // ecx
  CElement *FrameSite; // rax
  struct CMarkup *WindowedMarkupContext; // rbx
  unsigned __int64 v45; // rcx
  const unsigned __int16 *AAcreatorUrl; // rax
  CMarkup *v47; // rcx
  __int64 v48; // rdx
  struct IUnknown *NonRefdMonikerPtr; // rax
  struct IUnknown *v50; // rbx
  struct IUri *UriRaw; // rax
  CMarkup *v52; // r10
  CLangUtil *v53; // rax
  struct tagVARIANT *v55; // [rsp+28h] [rbp-D8h]
  CMarkup *v56; // [rsp+70h] [rbp-90h] BYREF
  char v57; // [rsp+78h] [rbp-88h]
  struct IDispatch v58; // [rsp+7Ch] [rbp-84h] BYREF
  CMSPerformanceData *v59; // [rsp+88h] [rbp-78h]
  LPSTREAM ppstm; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v62; // [rsp+A0h] [rbp-60h]
  _BYTE v63[24]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-38h]
  char v65; // [rsp+D8h] [rbp-28h]
  __int64 v66; // [rsp+E0h] [rbp-20h]
  __int64 v67; // [rsp+E8h] [rbp-18h]
  __int64 v68; // [rsp+F0h] [rbp-10h]
  _BYTE v69[56]; // [rsp+100h] [rbp+0h] BYREF
  struct COmWindowProxy *v70; // [rsp+138h] [rbp+38h]

  HistoryInternal = 0;
  v6 = (*(_BYTE *)(a1 + 16) & 1) == 0;
  v7 = (CWindow **)a1;
  ppstm = 0;
  v56 = 0;
  if ( v6 )
    v8 = *(CMarkup **)(*(_QWORD *)(a1 + 120) + 104LL);
  else
    v8 = 0;
  v9 = *((_QWORD *)v8 + 40);
  v10 = 0;
  if ( v9 )
    v10 = *(_QWORD *)(v9 + 16);
  memset_0(v69, 0, 0x58u);
  if ( !v10 || (v11 = 1, *(char *)(v10 + 4868) >= 0) )
    v11 = 0;
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)v8 + 984LL) != _vtguard )
    goto LABEL_162;
  v12 = *(void (__fastcall **)(CMarkup *))(*(_QWORD *)v8 + 1144LL);
  v62 = 0;
  v59 = 0;
  v12(v8);
  ErrorPageRefreshUrl = CMarkup::GetErrorPageRefreshUrl(v8);
  if ( ErrorPageRefreshUrl )
  {
    v57 = 1;
  }
  else
  {
    v57 = 0;
    ErrorPageRefreshUrl = (OLECHAR *)CMarkup::GetUrl(v8);
  }
  if ( v10 && (*(_DWORD *)(v10 + 4864) & 0x4000) != 0 )
  {
    HistoryInternal = -2147467263;
    goto LABEL_155;
  }
  if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ALLOW_REFRESH_WHEN_NAVIGATION_DISABLED)
    || (unsigned int)CWindow::CanNavigate(v7[15]) )
  {
    if ( v11 )
    {
      v15 = SysAllocString(ErrorPageRefreshUrl);
      if ( !v15 )
      {
        HistoryInternal = -2147024882;
        goto LABEL_155;
      }
      LODWORD(v58.lpVtbl) = 0;
      CWebOCEvents::BeforeNavigateRefresh(v14, (struct COmWindowProxy *)a1, v15, (unsigned __int8)a2, 0, (int *)&v58);
      SysFreeString(v15);
      if ( LODWORD(v58.lpVtbl) )
        goto LABEL_155;
      v7 = (CWindow **)a1;
    }
    if ( v57 && CMarkup::Window(v8) )
    {
      v17 = (CWindow *)*((_QWORD *)CMarkup::Window(v16) + 15);
      ErrorPageDwnPost = CMarkup::GetErrorPageDwnPost(v18);
      HistoryInternal = CWindow::FollowHyperlinkHelper(
                          v17,
                          ErrorPageRefreshUrl,
                          0,
                          0x21000u,
                          0,
                          (struct IDispatch *)v55,
                          ErrorPageDwnPost);
      goto LABEL_155;
    }
    if ( !v11
      || (unsigned __int8)IsWebPlatformHostBehaviorSupported<7>(
                            *(unsigned int *)(v10 + 5040),
                            *(unsigned int *)(v10 + 5044),
                            *(unsigned int *)(v10 + 5052),
                            *(unsigned int *)(v10 + 5048)) )
    {
      LODWORD(v58.lpVtbl) = 0;
      BYTE4(v58.lpVtbl) = 0;
      HistoryInternal = IsRedirectToBrokerNeeded(ErrorPageRefreshUrl, (const struct tagRedirectionPolicyFlags *)&v58);
      if ( !HistoryInternal )
        HistoryInternal = LCIEHandleBrokerRedirect(ErrorPageRefreshUrl, (struct CDoc *)v10, v21);
    }
    else
    {
      HistoryInternal = 1;
    }
    if ( a2 != 0x2000000 || (unsigned int)COmWindowProxy::_HandleMixedContentRefresh((COmWindowProxy *)v7) )
    {
      if ( (a2 & 0x40000) != 0 )
      {
        v23 = *(_QWORD *)v8;
        LODWORD(v58.lpVtbl) = -1;
        v61 = 0;
        if ( *(__int64 (__fastcall **)())(v23 + 984) != _vtguard )
          _report_securityfailure(1);
        if ( (*(int (__fastcall **)(CMarkup *, __int64 *))(v23 + 1008))(v8, &v61) < 0 )
        {
          a2 &= ~0x40000u;
        }
        else
        {
          if ( (*(unsigned int (__fastcall **)(__int64, OLECHAR *, struct IDispatch *, _QWORD))(*(_QWORD *)v61 + 40LL))(
                 v61,
                 ErrorPageRefreshUrl,
                 &v58,
                 0)
            || LODWORD(v58.lpVtbl) )
          {
            a2 &= ~0x40000u;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        }
      }
      if ( v10
        && *(int *)(v10 + 4856) >= 0
        && ((a2 & 0x8000) != 0 || (unsigned int)COmWindowProxy::Fire_onbeforeunload((COmWindowProxy *)v7, 0)) )
      {
        if ( (a2 & 0x2000) != 0 )
        {
          v24 = *(struct IUnknown **)(v10 + 64);
          if ( v24 )
            CTExec(v24, 0, 0x27u, 0, 0, 0);
        }
        LODWORD(v58.lpVtbl) = (unsigned __int8)a2;
        if ( (_BYTE)a2 )
        {
          switch ( (unsigned __int8)a2 )
          {
            case 2u:
              v25 = (unsigned __int8)IEConfiguration_GetBool(268435481, v20, v21, v22) != 0 ? 0x2200 : 0;
              break;
            case 3u:
              v25 = 8208;
              break;
            case 4u:
              v25 = 8704;
              break;
            default:
              v25 = 0;
              break;
          }
        }
        else
        {
          v25 = 512;
        }
        if ( CMarkup::Window(v8)
          && *((_QWORD *)CMarkup::Window(v26) + 15)
          && (*(_BYTE *)(*((_QWORD *)CMarkup::Window(v27) + 15) + 224LL) & 0x40) != 0 )
        {
          v25 |= 0x800000u;
        }
        v28 = IsInIEBrowser((struct CDoc *)v10);
        v6 = (*(_BYTE *)(v10 + 4864) & 4) == 0;
        *(_DWORD *)(v10 + 4856) ^= (*(_DWORD *)(v10 + 4856) ^ (v28 << 28)) & 0x10000000;
        if ( !v6 )
        {
          v64 = 0;
          v66 = 0;
          v67 = 0;
          v68 = 0;
          v65 = 0;
          v29 = CMarkup::Root(v8);
          CNotification::Initialize(v63, 57, v29, 0, (unsigned __int8)a2, 0);
          CMarkup::Notify(v8, (struct CNotification *)v63, 0);
        }
        HistoryInternal = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( !HistoryInternal )
        {
          HistoryInternal = CMarkup::SaveHistoryInternal(
                              v8,
                              (struct IUnknown *)ppstm,
                              3 - (unsigned int)((a2 & 0x41000) != 0));
          if ( !HistoryInternal )
          {
            HistoryInternal = CMarkup::ExecStop(v8, 0, 0, 0);
            if ( !HistoryInternal )
            {
              if ( (unsigned int)CMarkup::IsPrimaryMarkup(v8) && (*(_DWORD *)(v10 + 4864) & 0x800000) == 0 )
              {
                if ( (*(_BYTE *)(v10 + 4872) & 8) != 0 )
                  CDoc::ResetIgnoreMimeSettings((CDoc *)v10);
                if ( (a2 & 0x4000) != 0 )
                  CDoc::AddToPrivacyList((CDoc *)v10, &LocaleName, 0, 0x10000u, 1);
                else
                  CDoc::ResetPrivacyList((CDoc *)v10);
              }
              if ( (unsigned int)CMarkup::IsPrimaryMarkup(v8)
                || CDoc::GetActiveElement((CDoc *)v10)
                && (ActiveElement = CDoc::GetActiveElement((CDoc *)v10),
                    (unsigned int)CElement::IsConnectedToThisMarkup(ActiveElement, v8)) )
              {
                *(_DWORD *)(v10 + 4856) |= 0x800000u;
                v31 = CMarkup::Root(v8);
                CElement::BecomeCurrent(v31, 0, 0, 0, 0, 0, 0, 1, 0);
                *(_DWORD *)(v10 + 4856) &= ~0x800000u;
              }
              TimeManager = CMarkup::GetTimeManager(v8);
              if ( !TimeManager )
                goto LABEL_84;
              v33 = (CMSPerformanceData *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 208);
              if ( v33 )
              {
                v59 = CMSPerformanceData::CMSPerformanceData(v33, TimeManager);
                v34 = v59;
                if ( v59 )
                {
                  CMSPerformanceData::StartNavigation(v59, 1);
LABEL_84:
                  v35 = *(_DWORD *)(a1 + 168);
                  if ( (v35 & 8) != 0 )
                  {
                    *(_DWORD *)(a1 + 168) = v35 & 0xFFFFFFF7;
                    CBase::CLock::CLock((CBase::CLock *)&v61, (struct CBase *)a1);
                    if ( v59 )
                      CMSPerformanceData::Mark(v59, 1);
                    COmWindowProxy::Fire_onunload((COmWindowProxy *)a1);
                    if ( v59 )
                      CMSPerformanceData::Mark(v59, 2);
                    CBase::CLock::~CLock((CBase::CLock *)&v61);
                  }
                  if ( CMarkup::Window(v8) )
                  {
                    HistoryInternal = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm
                                                                                                  + 40LL))(
                                        ppstm,
                                        LI_ZERO,
                                        0,
                                        0);
                    if ( !HistoryInternal )
                    {
                      v70 = CMarkup::Window(v8);
                      HistoryInternal = CDoc::CreateMarkupFromInfo(
                                          (CDoc *)v10,
                                          (const struct CREATEMARKUPINFO *)v69,
                                          &v56);
                      if ( !HistoryInternal )
                      {
                        if ( TimeManager )
                        {
                          v39 = (CTimeManager *)*((_QWORD *)v56 + 73);
                          *((_QWORD *)v56 + 73) = TimeManager;
                          ++*((_DWORD *)TimeManager + 2);
                          if ( v39 )
                            CTimeManager::Release(v39);
                          if ( v59 )
                            CMarkup::SetPerfData(v56, v59);
                        }
                        lpVtbl = (int)v58.lpVtbl;
                        if ( LODWORD(v58.lpVtbl) == 2
                          && (unsigned __int8)IEConfiguration_GetBool(268435481, v36, v37, v38) )
                        {
                          v41 = 0x800000;
                        }
                        else
                        {
                          v41 = 0;
                        }
                        *((_DWORD *)v56 + 189) = v41 | *((_DWORD *)v56 + 189) & 0xFF7FFFFF;
                        v42 = 0;
                        *((_DWORD *)v56 + 188) |= 0x100000u;
                        if ( lpVtbl == 3 )
                          v42 = 0x20000;
                        *((_DWORD *)v56 + 189) = *((_DWORD *)v56 + 189) & 0xFFFDFFFF | v42;
                        FrameSite = CWindow::GetFrameSite(*(CWindow **)(a1 + 120));
                        if ( FrameSite )
                        {
                          WindowedMarkupContext = CElement::GetWindowedMarkupContext(FrameSite);
                          (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)v56 + 103) + 40LL))(
                            (char *)v56 + 824,
                            (__int64)WindowedMarkupContext + 824);
                          if ( *((int *)WindowedMarkupContext + 212) >= 90000 )
                          {
                            v45 = ((unsigned __int64)v56 + 832) & -(__int64)((CMarkup *)((char *)v56 + 824) != 0);
                            (*(void (__fastcall **)(unsigned __int64, _QWORD *))(*(_QWORD *)v45 + 8LL))(
                              v45,
                              (_QWORD *)v8 + 103);
                          }
                        }
                        CMarkup::SetMimeType(v56, *((_BYTE *)v8 + 100) & 7, 3);
                        if ( (a2 & 0x7FF0000) != 0 )
                          *((_DWORD *)v56 + 197) |= *((_DWORD *)v8 + 197);
                        if ( (a2 & 0x10000) != 0 )
                          *((_DWORD *)v56 + 197) |= 2u;
                        if ( (a2 & 0x20000) != 0 )
                          *((_DWORD *)v56 + 197) |= 1u;
                        if ( (a2 & 0x80000) != 0 )
                        {
                          *((_DWORD *)v56 + 197) |= 0x40u;
                          CDoc::OnPageActionBlocked((CDoc *)v10, 0x10000u, 1, 0);
                        }
                        if ( (a2 & 0x40000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4872) |= 2u;
                          CoInternetSetFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 1u, 0);
                        }
                        if ( (a2 & 0x100000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4952) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 8u, 0);
                        }
                        if ( (a2 & 0x400000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4956) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x10u, 0);
                        }
                        if ( (a2 & 0x200000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4960) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x20u, 0);
                        }
                        if ( (a2 & 0x800000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4964) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x40u, 0);
                        }
                        if ( (a2 & 0x1000000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4968) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x80u, 0);
                        }
                        if ( (a2 & 0x2000000) != 0 )
                          *((_DWORD *)v56 + 197) |= 0x80000u;
                        if ( (a2 & 0x8000000) != 0 )
                          *((_DWORD *)v56 + 197) |= 0x40u;
                        AAcreatorUrl = CMarkup::GetAAcreatorUrl(v8);
                        if ( AAcreatorUrl && *AAcreatorUrl )
                          CMarkup::SetAAcreatorUrl(v56, AAcreatorUrl);
                        v47 = v56;
                        v48 = *((_QWORD *)v56 + 27);
                        if ( v48 )
                        {
                          *(_DWORD *)(v48 + 8) = *(_DWORD *)(*((_QWORD *)v8 + 27) + 8LL)
                                               ^ (*(_DWORD *)(v48 + 8)
                                                ^ *(_DWORD *)(*((_QWORD *)v8 + 27) + 8LL))
                                               & 0xFFFFFFFE;
                          v47 = v56;
                        }
                        *((_BYTE *)v47 + 248) = *((_BYTE *)v8 + 248);
                        *((_BYTE *)v56 + 249) = *((_BYTE *)v8 + 249);
                        *((_BYTE *)v56 + 250) = *((_BYTE *)v8 + 250);
                        if ( (a2 & 0x4000000) != 0 )
                        {
                          *((_DWORD *)v56 + 197) |= 0x100000u;
                        }
                        else if ( (*(_DWORD *)(v10 + 4896) & 0x100000) != 0 )
                        {
                          *(_DWORD *)(v10 + 4888) |= 0x100000u;
                        }
                        NonRefdMonikerPtr = (struct IUnknown *)CMarkup::GetNonRefdMonikerPtr(v8);
                        v62 = NonRefdMonikerPtr;
                        v50 = NonRefdMonikerPtr;
                        if ( NonRefdMonikerPtr )
                          ((void (__fastcall *)(struct IUnknown *))NonRefdMonikerPtr->lpVtbl->AddRef)(NonRefdMonikerPtr);
                        UriRaw = CMarkup::GetUriRaw(v8);
                        if ( UriRaw )
                          CMarkup::SetUri(v56, UriRaw);
                        *((_BYTE *)v8 + 97) |= 0x40u;
                        COmWindowProxy::SwitchMarkup((COmWindowProxy *)a1, v56, 0, 0, 1, 0, 0);
                        if ( (unsigned int)CMarkup::IsPrimaryMarkup(v56) )
                        {
                          CImplAry::DeleteAll((CImplAry *)(v10 + 6456));
                          v52 = v56;
                        }
                        HistoryInternal = CMarkup::LoadHistoryInternal(
                                            v52,
                                            ppstm,
                                            0,
                                            v25,
                                            v50,
                                            0,
                                            0,
                                            a3,
                                            a4,
                                            0,
                                            0,
                                            0,
                                            0);
                        if ( !HistoryInternal )
                        {
                          if ( (a2 & 0x4000) == 0 )
                            *(_BYTE *)(v10 + 6680) = 0;
                          if ( (unsigned int)CMarkup::IsPrimaryMarkup(v56) && LODWORD(v58.lpVtbl) == 3 )
                          {
                            v53 = lang();
                            CLangUtil::InvalidateUserLang(v53, 0);
                          }
                        }
                      }
                    }
                  }
                  goto LABEL_155;
                }
              }
              else
              {
                v34 = 0;
              }
              v59 = v34;
              goto LABEL_84;
            }
          }
        }
      }
      else
      {
        if ( (a2 & 0x80000) != 0 )
          CDoc::OnPageActionBlocked((CDoc *)v10, 0x10000u, 0, 0);
        HistoryInternal = 1;
      }
    }
  }
LABEL_155:
  ReleaseInterface((struct IUnknown *)ppstm);
  ReleaseInterface(v62);
  if ( v59 )
    CMSPerformanceData::Release(v59);
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)v8 + 984LL) != _vtguard )
    goto LABEL_162;
  (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v8 + 1152LL))(v8);
  if ( v56 )
  {
    *((_DWORD *)v56 + 188) &= ~0x10000u;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v56 + 984LL) == _vtguard )
    {
      (*(void (**)(void))(*(_QWORD *)v56 + 1152LL))();
      return HistoryInternal;
    }
LABEL_162:
    _report_securityfailure(1);
  }
  return HistoryInternal;
}

```

## disassembly

```asm
0x180826508  mov     rax, rsp
0x18082650b  mov     [rax+10h], rbx
0x18082650f  mov     [rax+20h], r9d
0x180826513  mov     [rax+18h], r8d
0x180826517  mov     [rax+8], rcx
0x18082651b  push    rbp
0x18082651c  push    rsi
0x18082651d  push    rdi
0x18082651e  push    r12
0x180826520  push    r13
0x180826522  push    r14
0x180826524  push    r15
0x180826526  lea     rbp, [rsp-60h]
0x18082652b  sub     rsp, 160h
0x180826532  xor     ebx, ebx
0x180826534  mov     r14d, edx
0x180826537  test    byte ptr [rcx+10h], 1
0x18082653b  mov     r13, rcx
0x18082653e  mov     [rbp+90h+ppstm], rbx
0x180826542  mov     [rsp+190h+var_120], rbx
0x180826547  jz      short loc_18082654D
0x180826549  mov     esi, ebx
0x18082654b  jmp     short loc_180826555
0x18082654d  mov     rax, [rcx+78h]
0x180826551  mov     rsi, [rax+68h]
0x180826555  mov     rax, [rsi+140h]
0x18082655c  mov     rdi, rbx
0x18082655f  test    rax, rax
0x180826562  jz      short loc_180826568
0x180826564  mov     rdi, [rax+10h]
0x180826568  xor     edx, edx; Val
0x18082656a  lea     rcx, [rbp+90h+var_90]; void *
0x18082656e  lea     r8d, [rdx+58h]; Size
0x180826572  call    memset_0
0x180826577  test    rdi, rdi
0x18082657a  jz      short loc_180826588
0x18082657c  test    byte ptr [rdi+1304h], 80h
0x180826583  mov     r12b, 1
0x180826586  jnz     short loc_18082658B
0x180826588  mov     r12b, bl
0x18082658b  mov     rax, [rsi]
0x18082658e  lea     rcx, __vtguard
0x180826595  cmp     [rax+3D8h], rcx
0x18082659c  jnz     loc_180827043
0x1808265a2  mov     rax, [rax+478h]
0x1808265a9  mov     rcx, rsi
0x1808265ac  mov     [rbp+90h+var_F0], rbx
0x1808265b0  mov     [rbp+90h+var_108], rbx
0x1808265b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808265b9  mov     rcx, rsi; this
0x1808265bc  call    ?GetErrorPageRefreshUrl@CMarkup@@QEBAPEAGXZ; CMarkup::GetErrorPageRefreshUrl(void)
0x1808265c1  mov     r15, rax
0x1808265c4  test    rax, rax
0x1808265c7  jz      short loc_1808265D0
0x1808265c9  mov     [rsp+190h+var_118], 1
0x1808265ce  jmp     short loc_1808265DF
0x1808265d0  mov     rcx, rsi; struct CMarkup *
0x1808265d3  mov     [rsp+190h+var_118], bl
0x1808265d7  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808265dc  mov     r15, rax
0x1808265df  test    rdi, rdi
0x1808265e2  jz      short loc_1808265FA
0x1808265e4  test    dword ptr [rdi+1300h], 4000h
0x1808265ee  jz      short loc_1808265FA
0x1808265f0  mov     ebx, 80004001h
0x1808265f5  jmp     loc_180826FB2
0x1808265fa  lea     rcx, ?FEATURE_ALLOW_REFRESH_WHEN_NAVIGATION_DISABLED@FCK@@3VCFeatureControlKey@@A; this
0x180826601  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180826606  test    eax, eax
0x180826608  jz      short loc_18082661B
0x18082660a  mov     rcx, [r13+78h]; this
0x18082660e  call    ?CanNavigate@CWindow@@QEAAHXZ; CWindow::CanNavigate(void)
0x180826613  test    eax, eax
0x180826615  jz      loc_180826FB2
0x18082661b  test    r12b, r12b
0x18082661e  jz      short loc_180826674
0x180826620  mov     rcx, r15; psz
0x180826623  call    cs:__imp_SysAllocString
0x180826629  mov     r13, rax
0x18082662c  test    rax, rax
0x18082662f  jz      loc_1808266BD
0x180826635  mov     rdx, [rbp+90h+arg_0]; struct COmWindowProxy *
0x18082663c  lea     rax, [rsp+190h+var_114]
0x180826641  mov     [rsp+190h+var_168], rax; struct IDispatch *
0x180826646  mov     r8, r13; unsigned __int16 *
0x180826649  movzx   r9d, r14b; unsigned int
0x18082664d  mov     dword ptr [rsp+190h+var_170], ebx; unsigned int
0x180826651  mov     dword ptr [rsp+190h+var_114.lpVtbl], ebx
0x180826655  call    ?BeforeNavigateRefresh@CWebOCEvents@@QEBAXPEAVCOmWindowProxy@@PEAGKKPEAH@Z; CWebOCEvents::BeforeNavigateRefresh(COmWindowProxy *,ushort *,ulong,ulong,int *)
0x18082665a  mov     rcx, r13; bstrString
0x18082665d  call    cs:__imp_SysFreeString
0x180826663  cmp     dword ptr [rsp+190h+var_114.lpVtbl], ebx
0x180826667  jnz     loc_180826FB2
0x18082666d  mov     r13, [rbp+90h+arg_0]
0x180826674  cmp     [rsp+190h+var_118], bl
0x180826678  jz      short loc_1808266C7
0x18082667a  mov     rcx, rsi; this
0x18082667d  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180826682  test    rax, rax
0x180826685  jz      short loc_1808266C7
0x180826687  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082668c  mov     rbx, [rax+78h]
0x180826690  call    ?GetErrorPageDwnPost@CMarkup@@QEBAPEAVCDwnPost@@XZ; CMarkup::GetErrorPageDwnPost(void)
0x180826695  xor     r12d, r12d
0x180826698  mov     [rsp+190h+var_160], rax; struct CDwnPost *
0x18082669d  mov     r9d, 21000h; unsigned __int64
0x1808266a3  mov     [rsp+190h+var_170], r12; unsigned __int16 *
0x1808266a8  xor     r8d, r8d; unsigned int
0x1808266ab  mov     rdx, r15; pwzURI
0x1808266ae  mov     rcx, rbx; this
0x1808266b1  call    ?FollowHyperlinkHelper@CWindow@@QEAAJPEBGK_KPEAGPEAUIDispatch@@PEAVCDwnPost@@@Z; CWindow::FollowHyperlinkHelper(ushort const *,ulong,unsigned __int64,ushort *,IDispatch *,CDwnPost *)
0x1808266b6  mov     ebx, eax
0x1808266b8  jmp     loc_180826FB2
0x1808266bd  mov     ebx, 8007000Eh
0x1808266c2  jmp     loc_180826FB2
0x1808266c7  test    r12b, r12b
0x1808266ca  jz      short loc_1808266F9
0x1808266cc  mov     r9d, [rdi+13B8h]
0x1808266d3  mov     r8d, [rdi+13BCh]
0x1808266da  mov     edx, [rdi+13B4h]
0x1808266e0  mov     ecx, [rdi+13B0h]
0x1808266e6  call    ??$IsWebPlatformHostBehaviorSupported@$06@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<7>(WebPlatformHostType,ulong,ulong,ulong)
0x1808266eb  xor     r12d, r12d
0x1808266ee  test    al, al
0x1808266f0  jnz     short loc_1808266FC
0x1808266f2  lea     ebx, [r12+1]
0x1808266f7  jmp     short loc_180826726
0x1808266f9  xor     r12d, r12d
0x1808266fc  xor     eax, eax
0x1808266fe  lea     rdx, [rsp+190h+var_114]
0x180826703  mov     rcx, r15
0x180826706  mov     dword ptr [rsp+190h+var_114.lpVtbl], eax
0x18082670a  mov     byte ptr [rbp+90h+var_114.lpVtbl+4], al
0x18082670d  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x180826713  mov     ebx, eax
0x180826715  test    eax, eax
0x180826717  jnz     short loc_180826726
0x180826719  mov     rdx, rdi; this
0x18082671c  mov     rcx, r15; psz
0x18082671f  call    ?LCIEHandleBrokerRedirect@@YAJPEBGPEAVCDoc@@PEAVCMarkup@@@Z; LCIEHandleBrokerRedirect(ushort const *,CDoc *,CMarkup *)
0x180826724  mov     ebx, eax
0x180826726  cmp     r14d, 2000000h
0x18082672d  jnz     short loc_18082673F
0x18082672f  mov     rcx, r13; this
0x180826732  call    ?_HandleMixedContentRefresh@COmWindowProxy@@IEAAJXZ; COmWindowProxy::_HandleMixedContentRefresh(void)
0x180826737  test    eax, eax
0x180826739  jz      loc_180826FB2
0x18082673f  bt      r14d, 12h
0x180826744  jnb     short loc_1808267BF
0x180826746  mov     rax, [rsi]
0x180826749  lea     rcx, __vtguard
0x180826750  mov     dword ptr [rsp+190h+var_114.lpVtbl], 0FFFFFFFFh
0x180826758  mov     [rbp+90h+var_F8], r12
0x18082675c  cmp     [rax+3D8h], rcx
0x180826763  jnz     loc_18082683E
0x180826769  mov     rax, [rax+3F0h]
0x180826770  lea     rdx, [rbp+90h+var_F8]
0x180826774  mov     rcx, rsi
0x180826777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082677c  test    eax, eax
0x18082677e  js      loc_180826837
0x180826784  mov     rcx, [rbp+90h+var_F8]
0x180826788  lea     r8, [rsp+190h+var_114]
0x18082678d  xor     r9d, r9d
0x180826790  mov     rdx, r15
0x180826793  mov     rax, [rcx]
0x180826796  mov     rax, [rax+28h]
0x18082679a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082679f  test    eax, eax
0x1808267a1  jnz     short loc_1808267AA
0x1808267a3  cmp     dword ptr [rsp+190h+var_114.lpVtbl], r12d
0x1808267a8  jz      short loc_1808267AF
0x1808267aa  btr     r14d, 12h
0x1808267af  mov     rcx, [rbp+90h+var_F8]
0x1808267b3  mov     rax, [rcx]
0x1808267b6  mov     rax, [rax+10h]
0x1808267ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808267bf  test    rdi, rdi
0x1808267c2  jz      loc_180826F93
0x1808267c8  cmp     [rdi+12F8h], r12d
0x1808267cf  jl      loc_180826F93
0x1808267d5  bt      r14d, 0Fh
0x1808267da  jb      short loc_1808267EE
0x1808267dc  xor     edx, edx; bool
0x1808267de  mov     rcx, r13; this
0x1808267e1  call    ?Fire_onbeforeunload@COmWindowProxy@@QEAAH_N@Z; COmWindowProxy::Fire_onbeforeunload(bool)
0x1808267e6  test    eax, eax
0x1808267e8  jz      loc_180826F93
0x1808267ee  bt      r14d, 0Dh
0x1808267f3  jnb     short loc_180826816
0x1808267f5  mov     rcx, [rdi+40h]; struct IUnknown *
0x1808267f9  test    rcx, rcx
0x1808267fc  jz      short loc_180826816
0x1808267fe  xor     r9d, r9d; unsigned int
0x180826801  mov     [rsp+190h+var_168], r12; struct tagVARIANT *
0x180826806  xor     edx, edx; struct _GUID *
0x180826808  mov     [rsp+190h+var_170], r12; struct tagVARIANT *
0x18082680d  lea     r8d, [r9+27h]; unsigned int
0x180826811  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x180826816  movzx   ecx, r14b
0x18082681a  mov     dword ptr [rsp+190h+var_114.lpVtbl], ecx
0x18082681e  test    r14b, r14b
0x180826821  jz      short loc_180826873
0x180826823  sub     ecx, 2
0x180826826  jz      short loc_180826859
0x180826828  sub     ecx, 1
0x18082682b  jz      short loc_180826851
0x18082682d  cmp     ecx, 1
0x180826830  jz      short loc_180826849
0x180826832  mov     r13d, r12d
0x180826835  jmp     short loc_180826879
0x180826837  btr     r14d, 12h
0x18082683c  jmp     short loc_1808267BF
0x18082683e  mov     ecx, 1
0x180826843  call    __report_securityfailure
0x180826849  mov     r13d, 2200h
0x18082684f  jmp     short loc_180826879
0x180826851  mov     r13d, 2010h
0x180826857  jmp     short loc_180826879
0x180826859  mov     ecx, 10000019h
0x18082685e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180826864  neg     al
0x180826866  mov     r13d, 2200h
0x18082686c  sbb     ecx, ecx
0x18082686e  and     r13d, ecx
0x180826871  jmp     short loc_180826879
0x180826873  mov     r13d, 200h
0x180826879  mov     rcx, rsi; this
0x18082687c  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180826881  test    rax, rax
0x180826884  jz      short loc_1808268A8
0x180826886  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082688b  cmp     [rax+78h], r12
0x18082688f  jz      short loc_1808268A8
0x180826891  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180826896  mov     rcx, [rax+78h]
0x18082689a  test    byte ptr [rcx+0E0h], 40h
0x1808268a1  jz      short loc_1808268A8
0x1808268a3  bts     r13d, 17h
0x1808268a8  mov     rcx, rdi; struct CDoc *
0x1808268ab  call    ?IsInIEBrowser@@YAHPEAVCDoc@@@Z; IsInIEBrowser(CDoc *)
0x1808268b0  mov     ecx, [rdi+12F8h]
0x1808268b6  shl     eax, 1Ch
0x1808268b9  xor     eax, ecx
0x1808268bb  and     eax, 10000000h
0x1808268c0  xor     eax, ecx
0x1808268c2  test    byte ptr [rdi+1300h], 4
0x1808268c9  mov     [rdi+12F8h], eax
0x1808268cf  jz      short loc_180826925
0x1808268d1  mov     rcx, rsi; this
0x1808268d4  mov     [rbp+90h+var_C8], r12
0x1808268d8  mov     [rbp+90h+var_B0], 0
0x1808268e0  mov     [rbp+90h+var_A8], 0
0x1808268e8  mov     [rbp+90h+var_A0], r12
0x1808268ec  mov     [rbp+90h+var_B8], r12b
0x1808268f0  call    ?Root@CMarkup@@QEBAPEAVCRootElement@@XZ; CMarkup::Root(void)
0x1808268f5  xor     r9d, r9d
0x1808268f8  movzx   ecx, r14b
0x1808268fc  mov     dword ptr [rsp+190h+var_168], r12d
0x180826901  mov     r8, rax
0x180826904  mov     [rsp+190h+var_170], rcx
0x180826909  lea     rcx, [rbp+90h+var_E0]
0x18082690d  lea     edx, [r9+39h]
0x180826911  call    ?Initialize@CNotification@@QEAAXW4NOTIFYTYPE@@PEAVCElement@@PEAVCTreeNode@@PEAXK@Z; CNotification::Initialize(NOTIFYTYPE,CElement *,CTreeNode *,void *,ulong)
0x180826916  xor     r8d, r8d; int
0x180826919  lea     rdx, [rbp+90h+var_E0]; struct CNotification *
0x18082691d  mov     rcx, rsi; this
0x180826920  call    ?Notify@CMarkup@@QEAAXPEAVCNotification@@J@Z; CMarkup::Notify(CNotification *,long)
0x180826925  lea     r8, [rbp+90h+ppstm]; ppstm
0x180826929  mov     edx, 1; fDeleteOnRelease
0x18082692e  xor     ecx, ecx; hGlobal
0x180826930  call    cs:__imp_CreateStreamOnHGlobal
0x180826936  mov     ebx, eax
0x180826938  test    eax, eax
0x18082693a  jnz     loc_180826FB2
0x180826940  mov     rdx, [rbp+90h+ppstm]; struct IUnknown *
0x180826944  mov     eax, r14d
0x180826947  and     eax, 41000h
0x18082694c  mov     rcx, rsi; this
0x18082694f  neg     eax
0x180826951  sbb     r8d, r8d
0x180826954  add     r8d, 3; unsigned int
0x180826958  call    ?SaveHistoryInternal@CMarkup@@QEAAJPEAUIStream@@K@Z; CMarkup::SaveHistoryInternal(IStream *,ulong)
0x18082695d  mov     ebx, eax
0x18082695f  test    eax, eax
0x180826961  jnz     loc_180826FB2
0x180826967  xor     r9d, r9d; int
0x18082696a  xor     r8d, r8d; int
0x18082696d  xor     edx, edx; int
0x18082696f  mov     rcx, rsi; this
0x180826972  call    ?ExecStop@CMarkup@@QEAAJHHH@Z; CMarkup::ExecStop(int,int,int)
0x180826977  mov     ebx, eax
0x180826979  test    eax, eax
0x18082697b  jnz     loc_180826FB2
0x180826981  mov     rcx, rsi; this
0x180826984  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x180826989  xor     r15d, r15d
0x18082698c  mov     r12d, 10000h
0x180826992  test    eax, eax
0x180826994  jz      short loc_1808269DE
  ... truncated ...
```
