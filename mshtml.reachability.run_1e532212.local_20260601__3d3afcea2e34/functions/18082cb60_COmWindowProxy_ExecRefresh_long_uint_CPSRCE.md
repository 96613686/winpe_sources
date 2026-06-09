# COmWindowProxy::ExecRefresh(long,uint,CPSRCE)

- ea: `0x18082cb60`
- end: `0x18082d6dd`
- name: `?ExecRefresh@COmWindowProxy@@QEAAJJIW4CPSRCE@@@Z`
- size: `2941`
- prototype: ``
- caller_count: `8`
- callee_count: `59`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180475bb0`
- `0x1806d4ea8`
- `0x18082ca1c`
- `0x1808cacb0`
- `0x1808d6244`
- `0x180c9b120`
- `0x180e65a00`
- `0x181080e74`

## callees

- `0x180012430`
- `0x18005db20`
- `0x180066940`
- `0x18006b2e8`
- `0x1800ea428`
- `0x1801086ac`
- `0x18011853c`
- `0x1801296e4`
- `0x18012a320`
- `0x18013496c`
- `0x18014e21c`
- `0x18015a55c`
- `0x18015d550`
- `0x180160620`
- `0x1801dc4a4`
- `0x18028dae0`
- `0x180303f98`
- `0x180359018`
- `0x1803bfdac`
- `0x1803c2240`
- `0x1803c6e70`
- `0x1803cada4`
- `0x1803ddae0`
- `0x1803deed0`
- `0x1803e706c`
- `0x1803e864c`
- `0x180402d68`
- `0x180414584`
- `0x18042ba20`
- `0x18053c714`
- `0x18054d498`
- `0x18054d908`
- `0x1805f7f7c`
- `0x1805fdca8`
- `0x18061e8e4`
- `0x18061e934`
- `0x180639ae4`
- `0x1806410bc`
- `0x180641d28`
- `0x1806dc898`
- `0x1806e7dac`
- `0x18073fc60`
- `0x180744f74`
- `0x1807caa78`
- `0x1807ec5c0`
- `0x1807ede24`
- `0x18082cb60`
- `0x18083bed4`
- `0x1808485d8`
- `0x18084ed20`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082ceb6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082d215`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082ceb6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18082d215`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18082cf8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18082cf8e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d388`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3ad`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3d1`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3f5`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d419`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d43e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d388`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3ad`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3d1`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d3f5`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d419`
- `urlmon!CoInternetSetFeatureEnabled` at `0x18082d43e`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18082cd5f`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18082cd5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18082cc69`
- `OLEAUT32!__imp_SysAllocString` at `0x18082cc69`
- `OLEAUT32!__imp_SysFreeString` at `0x18082cca9`
- `OLEAUT32!__imp_SysFreeString` at `0x18082cca9`

## pseudocode

```c
__int64 __fastcall COmWindowProxy::ExecRefresh(__int64 a1, int a2, int a3, int a4)
{
  unsigned int HistoryInternal; // ebx
  CWindow **v6; // r13
  struct CMarkup *v7; // rsi
  struct CDoc *v8; // rdi
  char v9; // r12
  void (__fastcall *v10)(struct CMarkup *); // rax
  OLECHAR *ErrorPageRefreshUrl; // r15
  CWebOCEvents *v12; // rcx
  unsigned __int16 *v13; // r13
  CMarkup *v14; // rcx
  CWindow *v15; // rbx
  CMarkup *v16; // rcx
  struct CDwnPost *ErrorPageDwnPost; // rax
  __int64 v18; // rdx
  struct CMarkup *v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  struct IUnknown *v22; // rcx
  unsigned int v23; // r13d
  CMarkup *v24; // rcx
  CMarkup *v25; // rcx
  int v26; // eax
  bool v27; // zf
  struct CRootElement *v28; // rax
  CElement *ActiveElement; // rax
  CElement *v30; // rax
  struct CTimeManager *TimeManager; // r15
  CMSPerformanceData *v32; // rax
  CMSPerformanceData *v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  CTimeManager *v38; // rcx
  int lpVtbl; // ebx
  int v40; // edx
  int v41; // ecx
  CElement *FrameSite; // rax
  struct CMarkup *WindowedMarkupContext; // rbx
  unsigned __int64 v44; // rcx
  const unsigned __int16 *AAcreatorUrl; // rax
  CMarkup *v46; // rcx
  __int64 v47; // rdx
  struct IUnknown *NonRefdMonikerPtr; // rax
  struct IUnknown *v49; // rbx
  struct IUri *UriRaw; // rax
  CMarkup *v51; // r10
  CLangUtil *v52; // rax
  struct tagVARIANT *v54; // [rsp+28h] [rbp-D8h]
  CMarkup *v55; // [rsp+70h] [rbp-90h] BYREF
  char v56; // [rsp+78h] [rbp-88h]
  struct IDispatch v57; // [rsp+7Ch] [rbp-84h] BYREF
  CMSPerformanceData *v58; // [rsp+88h] [rbp-78h]
  LPSTREAM ppstm; // [rsp+90h] [rbp-70h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v61; // [rsp+A0h] [rbp-60h]
  _BYTE v62[24]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-38h]
  char v64; // [rsp+D8h] [rbp-28h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  _BYTE v68[56]; // [rsp+100h] [rbp+0h] BYREF
  struct COmWindowProxy *v69; // [rsp+138h] [rbp+38h]

  HistoryInternal = 0;
  ppstm = 0;
  v6 = (CWindow **)a1;
  v55 = 0;
  v7 = COmWindowProxy::Markup((COmWindowProxy *)a1);
  v8 = CMarkup::Doc(v7);
  memset_0(v68, 0, 0x58u);
  if ( !v8 || (v9 = 1, *((char *)v8 + 4868) >= 0) )
    v9 = 0;
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)v7 + 984LL) != _vtguard )
    goto LABEL_157;
  v10 = *(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)v7 + 1144LL);
  v61 = 0;
  v58 = 0;
  v10(v7);
  ErrorPageRefreshUrl = CMarkup::GetErrorPageRefreshUrl(v7);
  if ( ErrorPageRefreshUrl )
  {
    v56 = 1;
  }
  else
  {
    v56 = 0;
    ErrorPageRefreshUrl = (OLECHAR *)CMarkup::GetUrl(v7);
  }
  if ( v8 && (*((_DWORD *)v8 + 1216) & 0x4000) != 0 )
  {
    HistoryInternal = -2147467263;
    goto LABEL_150;
  }
  if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ALLOW_REFRESH_WHEN_NAVIGATION_DISABLED)
    || (unsigned int)CWindow::CanNavigate(v6[15]) )
  {
    if ( v9 )
    {
      v13 = SysAllocString(ErrorPageRefreshUrl);
      if ( !v13 )
      {
        HistoryInternal = -2147024882;
        goto LABEL_150;
      }
      LODWORD(v57.lpVtbl) = 0;
      CWebOCEvents::BeforeNavigateRefresh(v12, (struct COmWindowProxy *)a1, v13, (unsigned __int8)a2, 0, (int *)&v57);
      SysFreeString(v13);
      if ( LODWORD(v57.lpVtbl) )
        goto LABEL_150;
      v6 = (CWindow **)a1;
    }
    if ( v56 && CMarkup::Window(v7) )
    {
      v15 = (CWindow *)*((_QWORD *)CMarkup::Window(v14) + 15);
      ErrorPageDwnPost = CMarkup::GetErrorPageDwnPost(v16);
      HistoryInternal = CWindow::FollowHyperlinkHelper(
                          v15,
                          ErrorPageRefreshUrl,
                          0,
                          0x21000u,
                          0,
                          (struct IDispatch *)v54,
                          ErrorPageDwnPost);
      goto LABEL_150;
    }
    if ( !v9
      || (unsigned __int8)IsWebPlatformHostBehaviorSupported<7>(
                            *((unsigned int *)v8 + 1260),
                            *((unsigned int *)v8 + 1261),
                            *((unsigned int *)v8 + 1263),
                            *((unsigned int *)v8 + 1262)) )
    {
      LODWORD(v57.lpVtbl) = 0;
      BYTE4(v57.lpVtbl) = 0;
      HistoryInternal = IsRedirectToBrokerNeeded(ErrorPageRefreshUrl, (const struct tagRedirectionPolicyFlags *)&v57);
      if ( !HistoryInternal )
        HistoryInternal = LCIEHandleBrokerRedirect(ErrorPageRefreshUrl, v8, v19);
    }
    else
    {
      HistoryInternal = 1;
    }
    if ( a2 != 0x2000000 || (unsigned int)COmWindowProxy::_HandleMixedContentRefresh((COmWindowProxy *)v6) )
    {
      if ( (a2 & 0x40000) != 0 )
      {
        v21 = *(_QWORD *)v7;
        LODWORD(v57.lpVtbl) = -1;
        v60 = 0;
        if ( *(__int64 (__fastcall **)())(v21 + 984) != _vtguard )
          _report_securityfailure(1);
        if ( (*(int (__fastcall **)(struct CMarkup *, __int64 *))(v21 + 1008))(v7, &v60) < 0 )
        {
          a2 &= ~0x40000u;
        }
        else
        {
          if ( (*(unsigned int (__fastcall **)(__int64, OLECHAR *, struct IDispatch *, _QWORD))(*(_QWORD *)v60 + 40LL))(
                 v60,
                 ErrorPageRefreshUrl,
                 &v57,
                 0)
            || LODWORD(v57.lpVtbl) )
          {
            a2 &= ~0x40000u;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        }
      }
      if ( v8
        && *((int *)v8 + 1214) >= 0
        && ((a2 & 0x8000) != 0 || (unsigned int)COmWindowProxy::Fire_onbeforeunload((COmWindowProxy *)v6, 0)) )
      {
        if ( (a2 & 0x2000) != 0 )
        {
          v22 = (struct IUnknown *)*((_QWORD *)v8 + 8);
          if ( v22 )
            CTExec(v22, 0, 0x27u, 0, 0, 0);
        }
        LODWORD(v57.lpVtbl) = (unsigned __int8)a2;
        if ( (_BYTE)a2 )
        {
          switch ( (unsigned __int8)a2 )
          {
            case 2u:
              v23 = (unsigned __int8)IEConfiguration_GetBool(268435481, v18, v19, v20) != 0 ? 0x2200 : 0;
              break;
            case 3u:
              v23 = 8208;
              break;
            case 4u:
              v23 = 8704;
              break;
            default:
              v23 = 0;
              break;
          }
        }
        else
        {
          v23 = 512;
        }
        if ( CMarkup::Window(v7)
          && *((_QWORD *)CMarkup::Window(v24) + 15)
          && (*(_BYTE *)(*((_QWORD *)CMarkup::Window(v25) + 15) + 224LL) & 0x40) != 0 )
        {
          v23 |= 0x800000u;
        }
        v26 = IsInIEBrowser(v8);
        v27 = (*((_BYTE *)v8 + 4864) & 4) == 0;
        *((_DWORD *)v8 + 1214) ^= (*((_DWORD *)v8 + 1214) ^ (v26 << 28)) & 0x10000000;
        if ( !v27 )
        {
          v63 = 0;
          v65 = 0;
          v66 = 0;
          v67 = 0;
          v64 = 0;
          v28 = CMarkup::Root(v7);
          CNotification::Initialize(v62, 57, v28, 0, (unsigned __int8)a2, 0);
          CMarkup::Notify(v7, (struct CNotification *)v62, 0);
        }
        HistoryInternal = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( !HistoryInternal )
        {
          HistoryInternal = CMarkup::SaveHistoryInternal(
                              v7,
                              (struct IUnknown *)ppstm,
                              3 - (unsigned int)((a2 & 0x41000) != 0));
          if ( !HistoryInternal )
          {
            HistoryInternal = CMarkup::ExecStop(v7, 0, 0, 0);
            if ( !HistoryInternal )
            {
              if ( (unsigned int)CMarkup::IsPrimaryMarkup(v7) && (*((_DWORD *)v8 + 1216) & 0x800000) == 0 )
              {
                if ( (*((_BYTE *)v8 + 4872) & 8) != 0 )
                  CDoc::ResetIgnoreMimeSettings(v8);
                if ( (a2 & 0x4000) != 0 )
                  CDoc::AddToPrivacyList(v8, &Source, 0, 0x10000u, 1);
                else
                  CDoc::ResetPrivacyList(v8);
              }
              if ( (unsigned int)CMarkup::IsPrimaryMarkup(v7)
                || CDoc::GetActiveElement(v8)
                && (ActiveElement = CDoc::GetActiveElement(v8),
                    (unsigned int)CElement::IsConnectedToThisMarkup(ActiveElement, v7)) )
              {
                *((_DWORD *)v8 + 1214) |= 0x800000u;
                v30 = CMarkup::Root(v7);
                CElement::BecomeCurrent(v30, 0, 0, 0, 0, 0, 0, 1, 0);
                *((_DWORD *)v8 + 1214) &= ~0x800000u;
              }
              TimeManager = CMarkup::GetTimeManager(v7);
              if ( !TimeManager )
                goto LABEL_79;
              v32 = (CMSPerformanceData *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 208);
              if ( v32 )
              {
                v58 = CMSPerformanceData::CMSPerformanceData(v32, TimeManager);
                v33 = v58;
                if ( v58 )
                {
                  CMSPerformanceData::StartNavigation(v58, 1);
LABEL_79:
                  v34 = *(_DWORD *)(a1 + 168);
                  if ( (v34 & 8) != 0 )
                  {
                    *(_DWORD *)(a1 + 168) = v34 & 0xFFFFFFF7;
                    CBase::CLock::CLock((CBase::CLock *)&v60, (struct CBase *)a1);
                    if ( v58 )
                      CMSPerformanceData::Mark(v58, 1);
                    COmWindowProxy::Fire_onunload((COmWindowProxy *)a1);
                    if ( v58 )
                      CMSPerformanceData::Mark(v58, 2);
                    CBase::CLock::~CLock((CBase::CLock *)&v60);
                  }
                  if ( CMarkup::Window(v7) )
                  {
                    HistoryInternal = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm
                                                                                                  + 40LL))(
                                        ppstm,
                                        LI_ZERO,
                                        0,
                                        0);
                    if ( !HistoryInternal )
                    {
                      v69 = CMarkup::Window(v7);
                      HistoryInternal = CDoc::CreateMarkupFromInfo(v8, (const struct CREATEMARKUPINFO *)v68, &v55);
                      if ( !HistoryInternal )
                      {
                        if ( TimeManager )
                        {
                          v38 = (CTimeManager *)*((_QWORD *)v55 + 73);
                          *((_QWORD *)v55 + 73) = TimeManager;
                          ++*((_DWORD *)TimeManager + 2);
                          if ( v38 )
                            CTimeManager::Release(v38);
                          if ( v58 )
                            CMarkup::SetPerfData(v55, v58);
                        }
                        lpVtbl = (int)v57.lpVtbl;
                        if ( LODWORD(v57.lpVtbl) == 2
                          && (unsigned __int8)IEConfiguration_GetBool(268435481, v35, v36, v37) )
                        {
                          v40 = 0x800000;
                        }
                        else
                        {
                          v40 = 0;
                        }
                        *((_DWORD *)v55 + 189) = v40 | *((_DWORD *)v55 + 189) & 0xFF7FFFFF;
                        v41 = 0;
                        *((_DWORD *)v55 + 188) |= 0x100000u;
                        if ( lpVtbl == 3 )
                          v41 = 0x20000;
                        *((_DWORD *)v55 + 189) = *((_DWORD *)v55 + 189) & 0xFFFDFFFF | v41;
                        FrameSite = CWindow::GetFrameSite(*(CWindow **)(a1 + 120));
                        if ( FrameSite )
                        {
                          WindowedMarkupContext = CElement::GetWindowedMarkupContext(FrameSite);
                          (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)v55 + 103) + 40LL))(
                            (char *)v55 + 824,
                            (__int64)WindowedMarkupContext + 824);
                          if ( *((int *)WindowedMarkupContext + 212) >= 90000 )
                          {
                            v44 = ((unsigned __int64)v55 + 832) & -(__int64)((CMarkup *)((char *)v55 + 824) != 0);
                            (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v44 + 8LL))(
                              v44,
                              (__int64)v7 + 824);
                          }
                        }
                        CMarkup::SetMimeType(v55, *((_BYTE *)v7 + 100) & 7, 3);
                        if ( (a2 & 0x7FF0000) != 0 )
                          *((_DWORD *)v55 + 197) |= *((_DWORD *)v7 + 197);
                        if ( (a2 & 0x10000) != 0 )
                          *((_DWORD *)v55 + 197) |= 2u;
                        if ( (a2 & 0x20000) != 0 )
                          *((_DWORD *)v55 + 197) |= 1u;
                        if ( (a2 & 0x80000) != 0 )
                        {
                          *((_DWORD *)v55 + 197) |= 0x40u;
                          CDoc::OnPageActionBlocked(v8, 0x10000u, 1, 0);
                        }
                        if ( (a2 & 0x40000) != 0 )
                        {
                          *((_DWORD *)v8 + 1218) |= 2u;
                          CoInternetSetFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 1u, 0);
                        }
                        if ( (a2 & 0x100000) != 0 )
                        {
                          *((_DWORD *)v8 + 1238) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 8u, 0);
                        }
                        if ( (a2 & 0x400000) != 0 )
                        {
                          *((_DWORD *)v8 + 1239) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x10u, 0);
                        }
                        if ( (a2 & 0x200000) != 0 )
                        {
                          *((_DWORD *)v8 + 1240) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x20u, 0);
                        }
                        if ( (a2 & 0x800000) != 0 )
                        {
                          *((_DWORD *)v8 + 1241) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x40u, 0);
                        }
                        if ( (a2 & 0x1000000) != 0 )
                        {
                          *((_DWORD *)v8 + 1242) = 1;
                          CoInternetSetFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 0x80u, 0);
                        }
                        if ( (a2 & 0x2000000) != 0 )
                          *((_DWORD *)v55 + 197) |= 0x80000u;
                        if ( (a2 & 0x8000000) != 0 )
                          *((_DWORD *)v55 + 197) |= 0x40u;
                        AAcreatorUrl = CMarkup::GetAAcreatorUrl(v7);
                        if ( AAcreatorUrl && *AAcreatorUrl )
                          CMarkup::SetAAcreatorUrl(v55, AAcreatorUrl);
                        v46 = v55;
                        v47 = *((_QWORD *)v55 + 27);
                        if ( v47 )
                        {
                          *(_DWORD *)(v47 + 8) = *(_DWORD *)(*((_QWORD *)v7 + 27) + 8LL)
                                               ^ (*(_DWORD *)(v47 + 8)
                                                ^ *(_DWORD *)(*((_QWORD *)v7 + 27) + 8LL))
                                               & 0xFFFFFFFE;
                          v46 = v55;
                        }
                        *((_BYTE *)v46 + 248) = *((_BYTE *)v7 + 248);
                        *((_BYTE *)v55 + 249) = *((_BYTE *)v7 + 249);
                        *((_BYTE *)v55 + 250) = *((_BYTE *)v7 + 250);
                        if ( (a2 & 0x4000000) != 0 )
                        {
                          *((_DWORD *)v55 + 197) |= 0x100000u;
                        }
                        else if ( (*((_DWORD *)v8 + 1224) & 0x100000) != 0 )
                        {
                          *((_DWORD *)v8 + 1222) |= 0x100000u;
                        }
                        NonRefdMonikerPtr = (struct IUnknown *)CMarkup::GetNonRefdMonikerPtr(v7);
                        v61 = NonRefdMonikerPtr;
                        v49 = NonRefdMonikerPtr;
                        if ( NonRefdMonikerPtr )
                          ((void (__fastcall *)(struct IUnknown *))NonRefdMonikerPtr->lpVtbl->AddRef)(NonRefdMonikerPtr);
                        UriRaw = CMarkup::GetUriRaw(v7);
                        if ( UriRaw )
                          CMarkup::SetUri(v55, UriRaw);
                        *((_BYTE *)v7 + 97) |= 0x40u;
                        COmWindowProxy::SwitchMarkup((COmWindowProxy *)a1, v55, 0, 0, 1, 0, 0);
                        if ( (unsigned int)CMarkup::IsPrimaryMarkup(v55) )
                        {
                          CImplAry::DeleteAll((struct CDoc *)((char *)v8 + 6456));
                          v51 = v55;
                        }
                        HistoryInternal = CMarkup::LoadHistoryInternal(
                                            v51,
                                            ppstm,
                                            0,
                                            v23,
                                            v49,
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
                            *((_BYTE *)v8 + 6680) = 0;
                          if ( (unsigned int)CMarkup::IsPrimaryMarkup(v55) && LODWORD(v57.lpVtbl) == 3 )
                          {
                            v52 = lang();
                            CLangUtil::InvalidateUserLang(v52, 0);
                          }
                        }
                      }
                    }
                  }
                  goto LABEL_150;
                }
              }
              else
              {
                v33 = 0;
              }
              v58 = v33;
              goto LABEL_79;
            }
          }
        }
      }
      else
      {
        if ( (a2 & 0x80000) != 0 )
          CDoc::OnPageActionBlocked(v8, 0x10000u, 0, 0);
        HistoryInternal = 1;
      }
    }
  }
LABEL_150:
  ReleaseInterface((struct IUnknown *)ppstm);
  ReleaseInterface(v61);
  if ( v58 )
    CMSPerformanceData::Release(v58);
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)v7 + 984LL) != _vtguard )
    goto LABEL_157;
  (*(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)v7 + 1152LL))(v7);
  if ( v55 )
  {
    *((_DWORD *)v55 + 188) &= ~0x10000u;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v55 + 984LL) == _vtguard )
    {
      (*(void (**)(void))(*(_QWORD *)v55 + 1152LL))();
      return HistoryInternal;
    }
LABEL_157:
    _report_securityfailure(1);
  }
  return HistoryInternal;
}

```

## disassembly

```asm
0x18082cb60  mov     rax, rsp
0x18082cb63  mov     [rax+10h], rbx
0x18082cb67  mov     [rax+20h], r9d
0x18082cb6b  mov     [rax+18h], r8d
0x18082cb6f  mov     [rax+8], rcx
0x18082cb73  push    rbp
0x18082cb74  push    rsi
0x18082cb75  push    rdi
0x18082cb76  push    r12
0x18082cb78  push    r13
0x18082cb7a  push    r14
0x18082cb7c  push    r15
0x18082cb7e  lea     rbp, [rsp-60h]
0x18082cb83  sub     rsp, 160h
0x18082cb8a  xor     ebx, ebx
0x18082cb8c  mov     r14d, edx
0x18082cb8f  mov     [rbp+90h+ppstm], rbx
0x18082cb93  mov     r13, rcx
0x18082cb96  mov     [rsp+190h+var_120], rbx
0x18082cb9b  call    ?Markup@COmWindowProxy@@QEBAPEAVCMarkup@@XZ; COmWindowProxy::Markup(void)
0x18082cba0  mov     rcx, rax; this
0x18082cba3  mov     rsi, rax
0x18082cba6  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x18082cbab  xor     edx, edx; Val
0x18082cbad  lea     r8d, [rbx+58h]; Size
0x18082cbb1  lea     rcx, [rbp+90h+var_90]; void *
0x18082cbb5  mov     rdi, rax
0x18082cbb8  call    memset_0
0x18082cbbd  test    rdi, rdi
0x18082cbc0  jz      short loc_18082CBCE
0x18082cbc2  test    byte ptr [rdi+1304h], 80h
0x18082cbc9  mov     r12b, 1
0x18082cbcc  jnz     short loc_18082CBD1
0x18082cbce  mov     r12b, bl
0x18082cbd1  mov     rax, [rsi]
0x18082cbd4  lea     rcx, __vtguard
0x18082cbdb  cmp     [rax+3D8h], rcx
0x18082cbe2  jnz     loc_18082D6D2
0x18082cbe8  mov     rax, [rax+478h]
0x18082cbef  mov     rcx, rsi
0x18082cbf2  mov     [rbp+90h+var_F0], rbx
0x18082cbf6  mov     [rbp+90h+var_108], rbx
0x18082cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082cbff  mov     rcx, rsi; this
0x18082cc02  call    ?GetErrorPageRefreshUrl@CMarkup@@QEBAPEAGXZ; CMarkup::GetErrorPageRefreshUrl(void)
0x18082cc07  mov     r15, rax
0x18082cc0a  test    rax, rax
0x18082cc0d  jz      short loc_18082CC16
0x18082cc0f  mov     [rsp+190h+var_118], 1
0x18082cc14  jmp     short loc_18082CC25
0x18082cc16  mov     rcx, rsi; struct CMarkup *
0x18082cc19  mov     [rsp+190h+var_118], bl
0x18082cc1d  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x18082cc22  mov     r15, rax
0x18082cc25  test    rdi, rdi
0x18082cc28  jz      short loc_18082CC40
0x18082cc2a  test    dword ptr [rdi+1300h], 4000h
0x18082cc34  jz      short loc_18082CC40
0x18082cc36  mov     ebx, 80004001h
0x18082cc3b  jmp     loc_18082D640
0x18082cc40  lea     rcx, ?FEATURE_ALLOW_REFRESH_WHEN_NAVIGATION_DISABLED@FCK@@3VCFeatureControlKey@@A; this
0x18082cc47  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18082cc4c  test    eax, eax
0x18082cc4e  jz      short loc_18082CC61
0x18082cc50  mov     rcx, [r13+78h]; this
0x18082cc54  call    ?CanNavigate@CWindow@@QEAAHXZ; CWindow::CanNavigate(void)
0x18082cc59  test    eax, eax
0x18082cc5b  jz      loc_18082D640
0x18082cc61  test    r12b, r12b
0x18082cc64  jz      short loc_18082CCC6
0x18082cc66  mov     rcx, r15; psz
0x18082cc69  call    cs:__imp_SysAllocString
0x18082cc70  nop     dword ptr [rax+rax+00h]
0x18082cc75  mov     r13, rax
0x18082cc78  test    rax, rax
0x18082cc7b  jz      loc_18082CD0F
0x18082cc81  mov     rdx, [rbp+90h+arg_0]; struct COmWindowProxy *
0x18082cc88  lea     rax, [rsp+190h+var_114]
0x18082cc8d  mov     [rsp+190h+var_168], rax; struct IDispatch *
0x18082cc92  mov     r8, r13; unsigned __int16 *
0x18082cc95  movzx   r9d, r14b; unsigned int
0x18082cc99  mov     dword ptr [rsp+190h+var_170], ebx; unsigned int
0x18082cc9d  mov     dword ptr [rsp+190h+var_114.lpVtbl], ebx
0x18082cca1  call    ?BeforeNavigateRefresh@CWebOCEvents@@QEBAXPEAVCOmWindowProxy@@PEAGKKPEAH@Z; CWebOCEvents::BeforeNavigateRefresh(COmWindowProxy *,ushort *,ulong,ulong,int *)
0x18082cca6  mov     rcx, r13; bstrString
0x18082cca9  call    cs:__imp_SysFreeString
0x18082ccb0  nop     dword ptr [rax+rax+00h]
0x18082ccb5  cmp     dword ptr [rsp+190h+var_114.lpVtbl], ebx
0x18082ccb9  jnz     loc_18082D640
0x18082ccbf  mov     r13, [rbp+90h+arg_0]
0x18082ccc6  cmp     [rsp+190h+var_118], bl
0x18082ccca  jz      short loc_18082CD19
0x18082cccc  mov     rcx, rsi; this
0x18082cccf  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082ccd4  test    rax, rax
0x18082ccd7  jz      short loc_18082CD19
0x18082ccd9  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082ccde  mov     rbx, [rax+78h]
0x18082cce2  call    ?GetErrorPageDwnPost@CMarkup@@QEBAPEAVCDwnPost@@XZ; CMarkup::GetErrorPageDwnPost(void)
0x18082cce7  xor     r12d, r12d
0x18082ccea  mov     [rsp+190h+var_160], rax; struct CDwnPost *
0x18082ccef  mov     r9d, 21000h; unsigned __int64
0x18082ccf5  mov     [rsp+190h+var_170], r12; unsigned __int16 *
0x18082ccfa  xor     r8d, r8d; unsigned int
0x18082ccfd  mov     rdx, r15; pwzURI
0x18082cd00  mov     rcx, rbx; this
0x18082cd03  call    ?FollowHyperlinkHelper@CWindow@@QEAAJPEBGK_KPEAGPEAUIDispatch@@PEAVCDwnPost@@@Z; CWindow::FollowHyperlinkHelper(ushort const *,ulong,unsigned __int64,ushort *,IDispatch *,CDwnPost *)
0x18082cd08  mov     ebx, eax
0x18082cd0a  jmp     loc_18082D640
0x18082cd0f  mov     ebx, 8007000Eh
0x18082cd14  jmp     loc_18082D640
0x18082cd19  test    r12b, r12b
0x18082cd1c  jz      short loc_18082CD4B
0x18082cd1e  mov     r9d, [rdi+13B8h]
0x18082cd25  mov     r8d, [rdi+13BCh]
0x18082cd2c  mov     edx, [rdi+13B4h]
0x18082cd32  mov     ecx, [rdi+13B0h]
0x18082cd38  call    ??$IsWebPlatformHostBehaviorSupported@$06@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<7>(WebPlatformHostType,ulong,ulong,ulong)
0x18082cd3d  xor     r12d, r12d
0x18082cd40  test    al, al
0x18082cd42  jnz     short loc_18082CD4E
0x18082cd44  lea     ebx, [r12+1]
0x18082cd49  jmp     short loc_18082CD7E
0x18082cd4b  xor     r12d, r12d
0x18082cd4e  xor     eax, eax
0x18082cd50  lea     rdx, [rsp+190h+var_114]
0x18082cd55  mov     rcx, r15
0x18082cd58  mov     dword ptr [rsp+190h+var_114.lpVtbl], eax
0x18082cd5c  mov     byte ptr [rbp+90h+var_114.lpVtbl+4], al
0x18082cd5f  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x18082cd66  nop     dword ptr [rax+rax+00h]
0x18082cd6b  mov     ebx, eax
0x18082cd6d  test    eax, eax
0x18082cd6f  jnz     short loc_18082CD7E
0x18082cd71  mov     rdx, rdi; this
0x18082cd74  mov     rcx, r15; psz
0x18082cd77  call    ?LCIEHandleBrokerRedirect@@YAJPEBGPEAVCDoc@@PEAVCMarkup@@@Z; LCIEHandleBrokerRedirect(ushort const *,CDoc *,CMarkup *)
0x18082cd7c  mov     ebx, eax
0x18082cd7e  cmp     r14d, 2000000h
0x18082cd85  jnz     short loc_18082CD97
0x18082cd87  mov     rcx, r13; this
0x18082cd8a  call    ?_HandleMixedContentRefresh@COmWindowProxy@@IEAAJXZ; COmWindowProxy::_HandleMixedContentRefresh(void)
0x18082cd8f  test    eax, eax
0x18082cd91  jz      loc_18082D640
0x18082cd97  bt      r14d, 12h
0x18082cd9c  jnb     short loc_18082CE17
0x18082cd9e  mov     rax, [rsi]
0x18082cda1  lea     rcx, __vtguard
0x18082cda8  mov     dword ptr [rsp+190h+var_114.lpVtbl], 0FFFFFFFFh
0x18082cdb0  mov     [rbp+90h+var_F8], r12
0x18082cdb4  cmp     [rax+3D8h], rcx
0x18082cdbb  jnz     loc_18082CE96
0x18082cdc1  mov     rax, [rax+3F0h]
0x18082cdc8  lea     rdx, [rbp+90h+var_F8]
0x18082cdcc  mov     rcx, rsi
0x18082cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082cdd4  test    eax, eax
0x18082cdd6  js      loc_18082CE8F
0x18082cddc  mov     rcx, [rbp+90h+var_F8]
0x18082cde0  lea     r8, [rsp+190h+var_114]
0x18082cde5  xor     r9d, r9d
0x18082cde8  mov     rdx, r15
0x18082cdeb  mov     rax, [rcx]
0x18082cdee  mov     rax, [rax+28h]
0x18082cdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082cdf7  test    eax, eax
0x18082cdf9  jnz     short loc_18082CE02
0x18082cdfb  cmp     dword ptr [rsp+190h+var_114.lpVtbl], r12d
0x18082ce00  jz      short loc_18082CE07
0x18082ce02  btr     r14d, 12h
0x18082ce07  mov     rcx, [rbp+90h+var_F8]
0x18082ce0b  mov     rax, [rcx]
0x18082ce0e  mov     rax, [rax+10h]
0x18082ce12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082ce17  test    rdi, rdi
0x18082ce1a  jz      loc_18082D621
0x18082ce20  cmp     [rdi+12F8h], r12d
0x18082ce27  jl      loc_18082D621
0x18082ce2d  bt      r14d, 0Fh
0x18082ce32  jb      short loc_18082CE46
0x18082ce34  xor     edx, edx; bool
0x18082ce36  mov     rcx, r13; this
0x18082ce39  call    ?Fire_onbeforeunload@COmWindowProxy@@QEAAH_N@Z; COmWindowProxy::Fire_onbeforeunload(bool)
0x18082ce3e  test    eax, eax
0x18082ce40  jz      loc_18082D621
0x18082ce46  bt      r14d, 0Dh
0x18082ce4b  jnb     short loc_18082CE6E
0x18082ce4d  mov     rcx, [rdi+40h]; struct IUnknown *
0x18082ce51  test    rcx, rcx
0x18082ce54  jz      short loc_18082CE6E
0x18082ce56  xor     r9d, r9d; unsigned int
0x18082ce59  mov     [rsp+190h+var_168], r12; struct tagVARIANT *
0x18082ce5e  xor     edx, edx; struct _GUID *
0x18082ce60  mov     [rsp+190h+var_170], r12; struct tagVARIANT *
0x18082ce65  lea     r8d, [r9+27h]; unsigned int
0x18082ce69  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x18082ce6e  movzx   ecx, r14b
0x18082ce72  mov     dword ptr [rsp+190h+var_114.lpVtbl], ecx
0x18082ce76  test    r14b, r14b
0x18082ce79  jz      short loc_18082CED1
0x18082ce7b  sub     ecx, 2
0x18082ce7e  jz      short loc_18082CEB1
0x18082ce80  sub     ecx, 1
0x18082ce83  jz      short loc_18082CEA9
0x18082ce85  cmp     ecx, 1
0x18082ce88  jz      short loc_18082CEA1
0x18082ce8a  mov     r13d, r12d
0x18082ce8d  jmp     short loc_18082CED7
0x18082ce8f  btr     r14d, 12h
0x18082ce94  jmp     short loc_18082CE17
0x18082ce96  mov     ecx, 1
0x18082ce9b  call    __report_securityfailure
0x18082cea1  mov     r13d, 2200h
0x18082cea7  jmp     short loc_18082CED7
0x18082cea9  mov     r13d, 2010h
0x18082ceaf  jmp     short loc_18082CED7
0x18082ceb1  mov     ecx, 10000019h
0x18082ceb6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18082cebd  nop     dword ptr [rax+rax+00h]
0x18082cec2  neg     al
0x18082cec4  mov     r13d, 2200h
0x18082ceca  sbb     ecx, ecx
0x18082cecc  and     r13d, ecx
0x18082cecf  jmp     short loc_18082CED7
0x18082ced1  mov     r13d, 200h
0x18082ced7  mov     rcx, rsi; this
0x18082ceda  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082cedf  test    rax, rax
0x18082cee2  jz      short loc_18082CF06
0x18082cee4  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082cee9  cmp     [rax+78h], r12
0x18082ceed  jz      short loc_18082CF06
0x18082ceef  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18082cef4  mov     rcx, [rax+78h]
0x18082cef8  test    byte ptr [rcx+0E0h], 40h
0x18082ceff  jz      short loc_18082CF06
0x18082cf01  bts     r13d, 17h
0x18082cf06  mov     rcx, rdi; struct CDoc *
0x18082cf09  call    ?IsInIEBrowser@@YAHPEAVCDoc@@@Z; IsInIEBrowser(CDoc *)
0x18082cf0e  mov     ecx, [rdi+12F8h]
0x18082cf14  shl     eax, 1Ch
0x18082cf17  xor     eax, ecx
0x18082cf19  and     eax, 10000000h
0x18082cf1e  xor     eax, ecx
0x18082cf20  test    byte ptr [rdi+1300h], 4
0x18082cf27  mov     [rdi+12F8h], eax
0x18082cf2d  jz      short loc_18082CF83
0x18082cf2f  mov     rcx, rsi; this
0x18082cf32  mov     [rbp+90h+var_C8], r12
0x18082cf36  mov     [rbp+90h+var_B0], 0
0x18082cf3e  mov     [rbp+90h+var_A8], 0
0x18082cf46  mov     [rbp+90h+var_A0], r12
0x18082cf4a  mov     [rbp+90h+var_B8], r12b
0x18082cf4e  call    ?Root@CMarkup@@QEBAPEAVCRootElement@@XZ; CMarkup::Root(void)
0x18082cf53  movzx   edx, r14b
0x18082cf57  lea     rcx, [rbp+90h+var_E0]
0x18082cf5b  xor     r9d, r9d
0x18082cf5e  mov     dword ptr [rsp+190h+var_168], r12d
0x18082cf63  mov     [rsp+190h+var_170], rdx
0x18082cf68  mov     r8, rax
0x18082cf6b  lea     edx, [r9+39h]
0x18082cf6f  call    ?Initialize@CNotification@@QEAAXW4NOTIFYTYPE@@PEAVCElement@@PEAVCTreeNode@@PEAXK@Z; CNotification::Initialize(NOTIFYTYPE,CElement *,CTreeNode *,void *,ulong)
0x18082cf74  xor     r8d, r8d; int
0x18082cf77  lea     rdx, [rbp+90h+var_E0]; struct CNotification *
0x18082cf7b  mov     rcx, rsi; this
0x18082cf7e  call    ?Notify@CMarkup@@QEAAXPEAVCNotification@@J@Z; CMarkup::Notify(CNotification *,long)
0x18082cf83  lea     r8, [rbp+90h+ppstm]; ppstm
0x18082cf87  mov     edx, 1; fDeleteOnRelease
0x18082cf8c  xor     ecx, ecx; hGlobal
0x18082cf8e  call    cs:__imp_CreateStreamOnHGlobal
0x18082cf95  nop     dword ptr [rax+rax+00h]
0x18082cf9a  mov     ebx, eax
0x18082cf9c  test    eax, eax
0x18082cf9e  jnz     loc_18082D640
0x18082cfa4  mov     rdx, [rbp+90h+ppstm]; struct IUnknown *
0x18082cfa8  mov     eax, r14d
0x18082cfab  and     eax, 41000h
0x18082cfb0  mov     rcx, rsi; this
0x18082cfb3  neg     eax
0x18082cfb5  sbb     r8d, r8d
0x18082cfb8  add     r8d, 3; unsigned int
0x18082cfbc  call    ?SaveHistoryInternal@CMarkup@@QEAAJPEAUIStream@@K@Z; CMarkup::SaveHistoryInternal(IStream *,ulong)
0x18082cfc1  mov     ebx, eax
0x18082cfc3  test    eax, eax
0x18082cfc5  jnz     loc_18082D640
0x18082cfcb  xor     r9d, r9d; int
0x18082cfce  xor     r8d, r8d; int
0x18082cfd1  xor     edx, edx; int
0x18082cfd3  mov     rcx, rsi; this
0x18082cfd6  call    ?ExecStop@CMarkup@@QEAAJHHH@Z; CMarkup::ExecStop(int,int,int)
0x18082cfdb  mov     ebx, eax
0x18082cfdd  test    eax, eax
0x18082cfdf  jnz     loc_18082D640
0x18082cfe5  mov     rcx, rsi; this
0x18082cfe8  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x18082cfed  xor     r15d, r15d
0x18082cff0  mov     r12d, 10000h
0x18082cff6  test    eax, eax
0x18082cff8  jz      short loc_18082D042
0x18082cffa  test    dword ptr [rdi+1300h], 800000h
  ... truncated ...
```
