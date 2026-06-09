# CAnchorHelper::ExecHelper(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x180782de8`
- end: `0x180783a18`
- name: `?ExecHelper@CAnchorHelper@@QEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `3120`
- prototype: `__int64 __fastcall(CAnchorHelper *this, const struct _GUID *, unsigned int, __int64, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1807f9ba0`
- `0x18082b690`
- `0x180e887c0`
- `0x180f58570`

## callees

- `0x18000311c`
- `0x180013efc`
- `0x1800170d0`
- `0x18005cb94`
- `0x18005e648`
- `0x18005e684`
- `0x180066940`
- `0x1800c5000`
- `0x1801086ac`
- `0x1801393a8`
- `0x180267cc4`
- `0x180271b28`
- `0x18028eb40`
- `0x1803064d4`
- `0x1803c1b74`
- `0x1803d9ae8`
- `0x1803e7b5c`
- `0x180402a74`
- `0x180402d68`
- `0x18040ac58`
- `0x180410478`
- `0x180422abc`
- `0x180595040`
- `0x1805be6ec`
- `0x18064f7f8`
- `0x1807318dc`
- `0x18075ffac`
- `0x18077c370`
- `0x180782de8`
- `0x1807e50c4`
- `0x18083553c`
- `0x18083bed4`
- `0x180855450`
- `0x180873fac`
- `0x1808d1248`
- `0x1808d1be0`
- `0x1808d2e64`
- `0x1808e9454`
- `0x180974bf4`
- `0x1809c0adc`
- `0x180a18dbc`
- `0x180a18f30`
- `0x180a19018`
- `0x180a19050`
- `0x180a19768`
- `0x18108a910`
- `0x18108f474`
- `0x1810c69e8`
- `0x1810c6a3c`
- `0x1810f65c0`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180783543`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180783543`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNICW` at `0x1807838d1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNICW` at `0x1807838d1`
- `USER32!AllowSetForegroundWindow` at `0x180783331`
- `USER32!AllowSetForegroundWindow` at `0x180783331`
- `iertutil!CreateUri` at `0x180783887`
- `iertutil!CreateUri` at `0x180783887`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1807836a9`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1807836a9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807839a8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807839a8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18078358f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18078358f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180783568`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180783568`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18078335e`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18078335e`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1807832f6`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1807832f6`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180783371`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180783371`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1807835ad`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1807835ad`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180783340`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18078359f`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180783340`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18078359f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180783694`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180783694`
- `OLEAUT32!__imp_SysFreeString` at `0x18078344c`
- `OLEAUT32!__imp_SysFreeString` at `0x18078345c`
- `OLEAUT32!__imp_SysFreeString` at `0x18078344c`
- `OLEAUT32!__imp_SysFreeString` at `0x18078345c`

## pseudocode

```c
__int64 __fastcall CAnchorHelper::ExecHelper(
        CAnchorHelper *this,
        const struct _GUID *a2,
        unsigned int a3,
        __int64 a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6)
{
  int v7; // r12d
  unsigned int ContextUrls; // ebx
  const unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // r14
  __int64 (__fastcall ***v11)(_QWORD); // rcx
  CElement *v12; // rax
  CDoc *v13; // rdi
  struct CElement *v14; // rax
  __int64 v15; // rdx
  void *v16; // r8
  WCHAR *v17; // rdx
  struct CElement ***v18; // rax
  __int64 (__usercall **v19)@<rax>(PROPERTYDESC *__hidden@<rcx>, unsigned int@<edx>, void *@<r8>, struct CBase *@<r9>, struct CVoid *); // r9
  __int64 (__usercall **v20)@<rax>(PROPERTYDESC *__hidden@<rcx>, unsigned int@<edx>, void *@<r8>, struct CBase *@<r9>, struct CVoid *); // r8
  CElement *v21; // rax
  CElement *v22; // rax
  struct CDoc *v23; // rax
  __int64 (__fastcall ***v24)(_QWORD); // rcx
  struct IUnknown *v25; // rdi
  CElement *v26; // rax
  CDoc *v27; // r13
  void *v28; // r8
  const unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rsi
  void *v31; // r8
  void *v32; // r8
  struct CElement *v34; // rax
  __int64 (__fastcall ***v35)(_QWORD); // rcx
  CElement *v36; // rax
  struct CMarkup *WindowedMarkupContext; // rbx
  CElement *v38; // rax
  struct CDoc *v39; // rax
  struct CElement *v40; // rax
  __int64 (__fastcall ***v41)(_QWORD); // rcx
  CElement *v42; // rax
  CDoc *v43; // rbx
  __int64 *v44; // rax
  unsigned int v45; // ebx
  unsigned int v46; // eax
  struct COmWindowProxy *OmWindowProxy; // rax
  struct COmWindowProxy *v48; // r12
  const unsigned __int16 *v49; // rbx
  struct CBase *v50; // rax
  struct CElement *v51; // rax
  CElement *v52; // rax
  struct CMarkup *MarkupPtr; // r13
  char v54; // cl
  unsigned __int64 v55; // r14
  int v56; // r12d
  bool v57; // zf
  __int64 v58; // rax
  __int64 v59; // rax
  const unsigned __int16 *Url; // rax
  CElement *v61; // rax
  const WCHAR *AAid; // rax
  IStream *v63; // rax
  struct IStream *v64; // rbx
  unsigned int CurrentProcessManager; // edi
  unsigned int AuthorityManager; // eax
  unsigned int v67; // r8d
  unsigned int v68; // r9d
  CDoc *v69; // r13
  struct CMarkup *PrimaryTraceActivity; // rbx
  __int64 v71; // r9
  struct CElement *v72; // rax
  struct CElement *v73; // rax
  CElement *v74; // rax
  struct CDocument *v75; // rax
  unsigned int v76; // eax
  int v77; // eax
  __int64 (__fastcall ***v78)(_QWORD); // rcx
  __int64 v79; // rax
  const unsigned __int16 *v80; // rdx
  __int64 v81; // rdx
  void *v82; // r8
  unsigned int v83; // [rsp+20h] [rbp-140h]
  struct IServiceProvider *v84; // [rsp+20h] [rbp-140h]
  struct IUri *pwzUrl; // [rsp+30h] [rbp-130h]
  unsigned int v86; // [rsp+50h] [rbp-110h]
  unsigned int v87; // [rsp+58h] [rbp-108h]
  int v88; // [rsp+60h] [rbp-100h]
  struct IHTMLWindow2 **v89; // [rsp+68h] [rbp-F8h]
  struct IStream *v90; // [rsp+88h] [rbp-D8h]
  struct CElement *v91; // [rsp+90h] [rbp-D0h]
  int *v92; // [rsp+A8h] [rbp-B8h]
  const unsigned __int16 *v93; // [rsp+B8h] [rbp-A8h]
  struct IDispatch *v94; // [rsp+C0h] [rbp-A0h]
  LPCWSTR pwzURI; // [rsp+E0h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+E8h] [rbp-78h] BYREF
  IStream *pstm; // [rsp+F0h] [rbp-70h] BYREF
  struct IUri v98; // [rsp+F8h] [rbp-68h] BYREF
  struct IDataObject *v99; // [rsp+100h] [rbp-60h] BYREF
  unsigned __int16 *v100; // [rsp+108h] [rbp-58h] BYREF
  BSTR v101; // [rsp+110h] [rbp-50h] BYREF
  LPWSTR ppwsz; // [rsp+118h] [rbp-48h] BYREF
  unsigned int v103[2]; // [rsp+120h] [rbp-40h] BYREF
  struct _GUID v104; // [rsp+130h] [rbp-30h] BYREF
  struct _GUID v105; // [rsp+140h] [rbp-20h] BYREF
  _BYTE v106[20]; // [rsp+150h] [rbp-10h] BYREF
  int v107; // [rsp+164h] [rbp+4h]
  WCHAR pszStr1[4096]; // [rsp+170h] [rbp+10h] BYREF

  v7 = CBase::IDMFromCmdID(a2, a3);
  ContextUrls = -2147221248;
  v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  v10 = 0;
  if ( v7 <= 2268 )
  {
    switch ( v7 )
    {
      case 2268:
        v21 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        if ( *((char *)CElement::Doc(v21) + 4868) < 0 )
        {
          v22 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          v23 = CElement::Doc(v22);
          if ( !IsWebPlatformHostBehaviorSupported<6>(*((_DWORD *)v23 + 1260)) )
            return ContextUrls;
        }
        goto LABEL_24;
      case 15:
        v18 = (struct CElement ***)(***(__int64 (__fastcall ****)(_QWORD, _QWORD))this)(*(_QWORD *)this, 0);
        v19 = &s_propdescCIE9EventListcopy;
        v20 = &s_propdescCElementoncopy;
        break;
      case 16:
        v18 = (struct CElement ***)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        v19 = &s_propdescCIE9EventListcut;
        v20 = &s_propdescCElementoncut;
        break;
      case 26:
        goto LABEL_57;
      case 2136:
      case 2137:
LABEL_24:
        if ( !v9 || (unsigned int)_tcsnipre(L"mailto:", 7, v9, -1) )
          return ContextUrls;
        v24 = *(__int64 (__fastcall ****)(_QWORD))this;
        v25 = 0;
        pwzURI = 0;
        v99 = 0;
        v100 = 0;
        v26 = (CElement *)(**v24)(v24);
        v101 = (BSTR)CElement::Doc(v26);
        v27 = (CDoc *)v101;
        if ( v7 != 2273 && v7 != 2268 )
        {
          ContextUrls = CAnchorHelper::GetContextUrls(this, (unsigned __int16 **)&pwzURI, (unsigned __int16 **)&v99);
          if ( (ContextUrls & 0x80000000) != 0 )
          {
LABEL_31:
            v25 = (struct IUnknown *)pwzURI;
LABEL_32:
            v30 = v100;
LABEL_33:
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v25, v28);
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v99, v31);
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v30, v32);
            return ContextUrls;
          }
          if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this) )
          {
            v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
            ContextUrls = _HeapAllocString(v29, &v100);
            if ( (ContextUrls & 0x80000000) != 0 )
              goto LABEL_31;
            v10 = v100;
          }
          if ( !(unsigned int)IsScriptExecutableUrl(v9) )
          {
            v52 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            MarkupPtr = CElement::GetMarkupPtr(v52);
            v54 = *((_BYTE *)this + 16) & 0x40;
            ppwsz = 0;
            v55 = (-(__int64)(v54 != 0) & 0xFFFFFFFFF0LL) + 0x200000000000014LL;
            if ( v7 == 2137 || v7 == 2435 )
            {
              v57 = v7 == 2137;
              v58 = 0x10004000000LL;
              v56 = 1;
              if ( !v57 )
                v58 = 0x10008000000LL;
              v55 |= v58;
            }
            else
            {
              v56 = 0;
            }
            if ( MarkupPtr )
            {
              v59 = *((_QWORD *)MarkupPtr + 27);
              if ( v59 && (*(_BYTE *)(v59 + 8) & 1) != 0 )
                v55 |= 0x10000000u;
              Url = CMarkup::GetUrl(MarkupPtr);
              if ( IsNeedEdgePage(Url) )
              {
                v61 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
                AAid = CElement::GetAAid(v61);
                if ( !StrCmpICW(L"ContinueInIE", AAid) )
                {
                  pstm = 0;
                  v55 |= 0x100000000000uLL;
                  v63 = SHCreateMemStream(0, 0);
                  TSmartPointer<IDispGeometry>::TransferFrom<IDispTransformedGeometry>((__int64 *)&pstm, (__int64)v63);
                  v64 = pstm;
                  if ( pstm && IStream_WriteStr(pstm, v9) >= 0 )
                  {
                    CurrentProcessManager = IsoGetCurrentProcessManager();
                    AuthorityManager = IsoGetAuthorityManager();
                    LCIEPostMessageWithStream(AuthorityManager, CurrentProcessManager, v67, v68, v64);
                  }
                  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&pstm);
                }
              }
              pstm = 0;
              if ( (int)CMarkup::GetTopmostMarkup(MarkupPtr, &pstm) >= 0 && *((_BYTE *)pstm + 249) )
                v55 |= 0x20000000000uLL;
              if ( CAnchorHelper::IsInvalidCertErrorPage(MarkupPtr) )
              {
                v55 |= 0x20000000u;
                ppwsz = (LPWSTR)CMarkup::GetDwnPost(MarkupPtr);
              }
            }
            v69 = (CDoc *)v101;
            PrimaryTraceActivity = CDoc::GetPrimaryTraceActivity((CDoc *)v101);
            if ( PrimaryTraceActivity )
            {
              v106[16] = 0;
              v104 = *CreateUserInputId(&v105);
              ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)v106, &v104);
              v57 = *(_DWORD *)PrimaryTraceActivity == 1;
              v107 = 3;
              if ( v57 && (unsigned int)dword_18158CCA8 > 5 && tlgKeywordOn((__int64)&dword_18158CCA8, 0x200000000008LL) )
              {
                *(_QWORD *)v103 = GlobalThreadState();
                *(_QWORD *)&v105.Data1 = IEConfiguration_GetCLSID(268435459);
                LODWORD(bstrString) = 0;
                *(_QWORD *)&v104.Data1 = v55;
                LODWORD(v98.lpVtbl) = IsSpartanApp();
                LODWORD(pstm) = v56;
                LODWORD(v101) = (v55 & 0x4000000) != 0;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                  (__int64)&dword_18158CCA8,
                  (__int64)&dword_18154CAFC,
                  (__int64)PrimaryTraceActivity + 8,
                  v71,
                  (__int64)&pstm,
                  (__int64)&v101,
                  (__int64)&v98,
                  (__int64)&v104,
                  (__int64)&bstrString,
                  (__int64 *)&v105,
                  (__int64 *)v103);
              }
              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)v106);
            }
            v72 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            v30 = v100;
            v25 = (struct IUnknown *)pwzURI;
            ContextUrls = CDoc::FollowHyperlink(
                            v69,
                            v9,
                            v100,
                            v72,
                            (struct CDwnPost *)ppwsz,
                            0,
                            pwzUrl,
                            0,
                            0,
                            0,
                            v86,
                            v87,
                            v88,
                            v89,
                            v56,
                            v55,
                            0,
                            v90,
                            v91,
                            (unsigned __int16 *)pwzURI,
                            0,
                            v92,
                            0,
                            v93,
                            v94,
                            (unsigned __int16 *)v99,
                            0);
            goto LABEL_33;
          }
          bstrString = 0;
          v101 = 0;
          OmWindowProxy = CAnchorHelper::GetOmWindowProxy(this);
          v25 = (struct IUnknown *)pwzURI;
          v48 = OmWindowProxy;
          if ( pwzURI )
          {
            v49 = pwzURI;
          }
          else
          {
            v50 = (struct CBase *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            GetFullyExpandedUrl(v50, 0, &bstrString, &v101, 0);
            v49 = v101;
            if ( !v101 )
            {
              ContextUrls = -2147024891;
              goto LABEL_65;
            }
          }
          v51 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CDoc::ExecuteScriptURL(v27, v9, v49, v10, v83, v48, (struct IHTMLWindow2 **)pwzUrl, v51);
LABEL_65:
          SysFreeString(bstrString);
          SysFreeString(v101);
          goto LABEL_32;
        }
        v73 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v73, 0xFFFFFFFF, 0);
        if ( ContextUrls )
          goto LABEL_32;
        if ( v7 == 2273 )
        {
          v74 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          v75 = CElement::Document(v74);
          v76 = CDoc::PrintHandler((CDoc *)v101, v75, 0, pszStr1, 0, 0, 0, 0, 0, 0);
        }
        else
        {
          v77 = CAnchorHelper::GetContextUrls(this, (unsigned __int16 **)&pwzURI, (unsigned __int16 **)&v99);
          v25 = (struct IUnknown *)pwzURI;
          if ( v77 >= 0 )
          {
            pwzURI = 0;
            if ( CreateUri((LPCWSTR)v25, 0x3002B80u, 0, (IUri **)&pwzURI) >= 0 )
            {
              LODWORD(bstrString) = 0;
              if ( !(*(unsigned int (__fastcall **)(LPCWSTR, BSTR *))(*(_QWORD *)pwzURI + 192LL))(pwzURI, &bstrString)
                && ((_DWORD)bstrString == 2 || (_DWORD)bstrString == 11 && !StrCmpNICW(pszStr1, L"https:", 6)) )
              {
                LOBYTE(v10) = 1;
              }
              (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pwzURI + 16LL))(pwzURI);
            }
          }
          v78 = *(__int64 (__fastcall ****)(_QWORD))this;
          pstm = 0;
          if ( *(void (**)())(*(_QWORD *)(**v78)(v78) + 1624LL) != _vtguard )
            _report_securityfailure(1u);
          v79 = (***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          if ( (*(int (__fastcall **)(__int64, GUID *, IStream **))(*(_QWORD *)v79 + 1536LL))(
                 v79,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pstm) < 0 )
            pstm = 0;
          if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_USE_LEGACY_DOFILEDOWNLOAD_FUNCTION) )
          {
            if ( (_BYTE)v10 )
            {
              pwzURI = 0;
              CStr::Append((CStr *)&pwzURI, L"Referer: ");
              CStr::Append((CStr *)&pwzURI, (const unsigned __int16 *)v25);
              CStr::Append((CStr *)&pwzURI, L"\r\n");
              ppwsz = 0;
              if ( SHStrDupW(pwzURI, &ppwsz) >= 0 )
                ContextUrls = IEFrameHelper::DoFileDownloadEx(
                                (IEFrameHelper *)pszStr1,
                                ppwsz,
                                (unsigned __int16 *)pstm,
                                v25,
                                (const unsigned __int16 *)v84);
              CStr::_Free((CStr *)&pwzURI, v81, v82);
              goto LABEL_116;
            }
            v76 = IEFrameHelper::DoFileDownloadEx(
                    (IEFrameHelper *)pszStr1,
                    0,
                    (unsigned __int16 *)pstm,
                    0,
                    (const unsigned __int16 *)v84);
          }
          else
          {
            v76 = IEFrameHelper::DoFileDownload((IEFrameHelper *)pszStr1, v80);
          }
        }
        ContextUrls = v76;
LABEL_116:
        if ( !ContextUrls )
          CAnchorHelper::SetVisited(this);
        goto LABEL_32;
      case 2261:
        if ( !v9 )
          return ContextUrls;
        v11 = *(__int64 (__fastcall ****)(_QWORD))this;
        pwzURI = 0;
        v12 = (CElement *)(**v11)(v11);
        v13 = CElement::Doc(v12);
        (*(void (__fastcall **)(_QWORD, LPCWSTR *))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, &pwzURI);
        if ( (unsigned int)GetUrlScheme(v9) - 15 <= 1 )
        {
          v17 = (WCHAR *)v9;
        }
        else
        {
          v14 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v14, 0xFFFFFFFF, 0);
          if ( ContextUrls )
          {
LABEL_15:
            CStr::_Free((CStr *)&pwzURI, v15, v16);
            return ContextUrls;
          }
          v17 = pszStr1;
        }
        ContextUrls = CDoc::AddToFavorites(v13, v17, (unsigned __int16 *)pwzURI);
        goto LABEL_15;
      default:
        if ( v7 == 2262 && v9 )
          return (unsigned int)CAnchorHelper::CopyLinkToClipboard(this, 0);
        return ContextUrls;
    }
LABEL_20:
    LODWORD(bstrString) = 0;
    return CElement::Fire_ondragHelper(
             v18,
             0,
             (const struct PROPERTYDESC_BASIC *)v20,
             (const struct PROPERTYDESC_BASIC *)v19,
             (unsigned int *)&bstrString,
             0)
         ? 0x80040100
         : 0;
  }
  switch ( v7 )
  {
    case 2273:
    case 2435:
      goto LABEL_24;
    case 2500:
    case 2501:
LABEL_57:
      v18 = (struct CElement ***)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
      v19 = &s_propdescCIE9EventListpaste;
      v20 = &s_propdescCElementonpaste;
      goto LABEL_20;
    case 3911:
      v40 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
      if ( (int)CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v40, 0xFFFFFFFF, 0) >= 0 )
      {
        v41 = *(__int64 (__fastcall ****)(_QWORD))this;
        LODWORD(v98.lpVtbl) = 0;
        pwzURI = 0;
        v42 = (CElement *)(**v41)(v41);
        v43 = CElement::Doc(v42);
        if ( v43 )
        {
          v44 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&pwzURI);
          if ( (int)CDoc::GetTabBrowserService(v43, (struct IMshtmlTabBrowserService **)v44) >= 0
            && (*(int (__fastcall **)(LPCWSTR, struct IUri *))(*(_QWORD *)pwzURI + 56LL))(pwzURI, &v98) >= 0 )
          {
            LODWORD(bstrString) = 0;
            v99 = 0;
            if ( (int)IsoAllocMessageBuffer(
                        (unsigned int)v98.lpVtbl,
                        (unsigned int *)&bstrString,
                        0x106Cu,
                        (struct _IsoMessage **)&v99) >= 0 )
            {
              if ( (int)StringCchCopyW((unsigned __int16 *)&v99[4], 0x824u, pszStr1) < 0
                || (LODWORD(v99[525].lpVtbl) = 3,
                    AllowSetForegroundWindow(0xFFFFFFFF),
                    v45 = (unsigned int)bstrString,
                    v46 = IsoGetCurrentProcessManager(),
                    (int)LCIEPostMessage((unsigned int)v98.lpVtbl, v46, 0xC0Fu, 0, v45) < 0) )
              {
                IsoFreeMessageBuffer((unsigned int)bstrString);
              }
            }
          }
        }
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&pwzURI);
      }
      return 0;
    default:
      if ( v7 == 15031 && v9 )
      {
        if ( a6 )
        {
          v34 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v34, 0xFFFFFFFF, 0);
          if ( !ContextUrls )
          {
            v35 = *(__int64 (__fastcall ****)(_QWORD))this;
            v99 = 0;
            v36 = (CElement *)(**v35)(v35);
            WindowedMarkupContext = CElement::GetWindowedMarkupContext(v36);
            v38 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            v39 = CElement::Doc(v38);
            ContextUrls = CopyURLToDataObject(v39, WindowedMarkupContext, pszStr1, &v99);
            if ( (ContextUrls & 0x80000000) == 0 )
            {
              a6->llVal = (LONGLONG)v99;
              a6->vt = 13;
            }
          }
        }
        else
        {
          return (unsigned int)-2147024809;
        }
      }
      break;
  }
  return ContextUrls;
}

```

## disassembly

```asm
0x180782de8  push    rbp
0x180782dea  push    rbx
0x180782deb  push    rsi
0x180782dec  push    rdi
0x180782ded  push    r12
0x180782def  push    r13
0x180782df1  push    r14
0x180782df3  push    r15
0x180782df5  lea     rbp, [rsp-2028h]
0x180782dfd  mov     eax, 2188h
0x180782e02  call    _alloca_probe
0x180782e07  sub     rsp, rax
0x180782e0a  mov     rax, cs:__security_cookie
0x180782e11  xor     rax, rsp
0x180782e14  mov     [rbp+2060h+var_50], rax
0x180782e1b  mov     rdi, [rbp+2060h+arg_28]
0x180782e22  mov     rax, rdx
0x180782e25  mov     rsi, rcx
0x180782e28  mov     edx, r8d; unsigned int
0x180782e2b  mov     rcx, rax; struct _GUID *
0x180782e2e  call    ?IDMFromCmdID@CBase@@SAHPEBU_GUID@@K@Z; CBase::IDMFromCmdID(_GUID const *,ulong)
0x180782e33  mov     rdx, [rsi]
0x180782e36  mov     r12d, eax
0x180782e39  mov     ebx, 80040100h
0x180782e3e  mov     rcx, [rdx]
0x180782e41  mov     rax, [rcx+8]
0x180782e45  mov     rcx, rdx
0x180782e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782e4d  mov     r15, rax
0x180782e50  xor     r14d, r14d
0x180782e53  mov     eax, 8DCh
0x180782e58  cmp     r12d, eax
0x180782e5b  jg      loc_180783146
0x180782e61  jz      loc_180782FCD
0x180782e67  mov     edx, r12d
0x180782e6a  sub     edx, 0Fh
0x180782e6d  jz      loc_180782FAF
0x180782e73  sub     edx, 1
0x180782e76  jz      loc_180782F6C
0x180782e7c  sub     edx, 0Ah
0x180782e7f  jz      loc_18078338E
0x180782e85  sub     edx, 83Eh
0x180782e8b  jz      loc_180783029
0x180782e91  sub     edx, 1
0x180782e94  jz      loc_180783029
0x180782e9a  sub     edx, 7Ch ; '|'
0x180782e9d  jz      short loc_180782EC2
0x180782e9f  cmp     edx, 1
0x180782ea2  jnz     loc_180783120
0x180782ea8  test    r15, r15
0x180782eab  jz      loc_180783120
0x180782eb1  xor     edx, edx; unsigned __int16 *
0x180782eb3  mov     rcx, rsi; this
0x180782eb6  call    ?CopyLinkToClipboard@CAnchorHelper@@QEAAJPEBG@Z; CAnchorHelper::CopyLinkToClipboard(ushort const *)
0x180782ebb  mov     ebx, eax
0x180782ebd  jmp     loc_180783120
0x180782ec2  test    r15, r15
0x180782ec5  jz      loc_180783120
0x180782ecb  mov     rcx, [rsi]
0x180782ece  mov     [rbp+2060h+pwzURI], r14
0x180782ed2  mov     rax, [rcx]
0x180782ed5  mov     rax, [rax]
0x180782ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782edd  mov     rcx, rax; this
0x180782ee0  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180782ee5  mov     rcx, [rsi]
0x180782ee8  mov     rdi, rax
0x180782eeb  mov     rdx, [rcx]
0x180782eee  mov     rax, [rdx+18h]
0x180782ef2  lea     rdx, [rbp+2060h+pwzURI]
0x180782ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782efb  mov     rcx, r15; unsigned __int16 *
0x180782efe  call    ?GetUrlScheme@@YAIPEBG@Z; GetUrlScheme(ushort const *)
0x180782f03  add     eax, 0FFFFFFF1h
0x180782f06  cmp     eax, 1
0x180782f09  jbe     short loc_180782F59
0x180782f0b  mov     rcx, [rsi]
0x180782f0e  mov     rax, [rcx]
0x180782f11  mov     rax, [rax]
0x180782f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782f19  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x180782f1e  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180782f22  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x180782f2a  mov     r8d, 1000h; int
0x180782f30  mov     rdx, r15; unsigned __int16 *
0x180782f33  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x180782f38  xor     ecx, ecx; struct CMarkup *
0x180782f3a  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x180782f3f  mov     ebx, eax
0x180782f41  test    eax, eax
0x180782f43  jz      short loc_180782F53
0x180782f45  lea     rcx, [rbp+2060h+pwzURI]; this
0x180782f49  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180782f4e  jmp     loc_180783120
0x180782f53  lea     rdx, [rbp+2060h+pszStr1]
0x180782f57  jmp     short loc_180782F5C
0x180782f59  mov     rdx, r15; unsigned __int16 *
0x180782f5c  mov     r8, [rbp+2060h+pwzURI]; unsigned __int16 *
0x180782f60  mov     rcx, rdi; this
0x180782f63  call    ?AddToFavorites@CDoc@@QEAAJPEBGPEAG@Z; CDoc::AddToFavorites(ushort const *,ushort *)
0x180782f68  mov     ebx, eax
0x180782f6a  jmp     short loc_180782F45
0x180782f6c  mov     rcx, [rsi]
0x180782f6f  mov     rax, [rcx]
0x180782f72  mov     rax, [rax]
0x180782f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782f7a  lea     r9, s_propdescCIE9EventListcut; struct PROPERTYDESC_BASIC *
0x180782f81  lea     r8, s_propdescCElementoncut; struct PROPERTYDESC_BASIC *
0x180782f88  lea     rcx, [rbp+2060h+bstrString]
0x180782f8c  mov     [rsp+21C0h+psa], r14; struct tagPOINT *
0x180782f91  mov     [rsp+21C0h+var_21A0], rcx; unsigned int *
0x180782f96  xor     edx, edx; int
0x180782f98  mov     rcx, rax; this
0x180782f9b  mov     dword ptr [rbp+2060h+bstrString], r14d
0x180782f9f  call    ?Fire_ondragHelper@CElement@@QEAAHJPEBUPROPERTYDESC_BASIC@@0PEAKPEBUtagPOINT@@@Z; CElement::Fire_ondragHelper(long,PROPERTYDESC_BASIC const *,PROPERTYDESC_BASIC const *,ulong *,tagPOINT const *)
0x180782fa4  neg     eax
0x180782fa6  sbb     ecx, ecx
0x180782fa8  and     ebx, ecx
0x180782faa  jmp     loc_180783120
0x180782faf  mov     rcx, [rsi]
0x180782fb2  mov     rax, [rcx]
0x180782fb5  mov     rax, [rax]
0x180782fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782fbd  lea     r9, s_propdescCIE9EventListcopy
0x180782fc4  lea     r8, s_propdescCElementoncopy
0x180782fcb  jmp     short loc_180782F88
0x180782fcd  mov     rcx, [rsi]
0x180782fd0  mov     rax, [rcx]
0x180782fd3  mov     rax, [rax]
0x180782fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782fdb  mov     rcx, rax; this
0x180782fde  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180782fe3  test    byte ptr [rax+1304h], 80h
0x180782fea  jz      short loc_180783029
0x180782fec  mov     rcx, [rsi]
0x180782fef  mov     rax, [rcx]
0x180782ff2  mov     rax, [rax]
0x180782ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180782ffa  mov     rcx, rax; this
0x180782ffd  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180783002  mov     r9d, [rax+13B8h]
0x180783009  mov     r8d, [rax+13BCh]
0x180783010  mov     edx, [rax+13B4h]
0x180783016  mov     ecx, [rax+13B0h]
0x18078301c  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x180783021  test    al, al
0x180783023  jz      loc_180783120
0x180783029  test    r15, r15
0x18078302c  jz      loc_180783120
0x180783032  or      r9d, 0FFFFFFFFh; int
0x180783036  lea     rcx, aMailto_0; "mailto:"
0x18078303d  mov     r8, r15; unsigned __int16 *
0x180783040  lea     edx, [r9+8]; cchCount2
0x180783044  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x180783049  test    eax, eax
0x18078304b  jnz     loc_180783120
0x180783051  mov     rcx, [rsi]
0x180783054  mov     rdi, r14
0x180783057  mov     [rbp+2060h+pwzURI], r14
0x18078305b  mov     [rbp+2060h+var_20C0], r14
0x18078305f  mov     [rbp+2060h+var_20B8], r14
0x180783063  mov     rax, [rcx]
0x180783066  mov     rax, [rax]
0x180783069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18078306e  mov     rcx, rax; this
0x180783071  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180783076  mov     [rbp+2060h+var_20B0], rax
0x18078307a  mov     r13, rax
0x18078307d  cmp     r12d, 8E1h
0x180783084  jz      loc_1807837C3
0x18078308a  cmp     r12d, 8DCh
0x180783091  jz      loc_1807837C3
0x180783097  lea     r8, [rbp+2060h+var_20C0]; unsigned __int16 **
0x18078309b  mov     rcx, rsi; this
0x18078309e  lea     rdx, [rbp+2060h+pwzURI]; unsigned __int16 **
0x1807830a2  call    ?GetContextUrls@CAnchorHelper@@AEAAJPEAPEAG0@Z; CAnchorHelper::GetContextUrls(ushort * *,ushort * *)
0x1807830a7  mov     ebx, eax
0x1807830a9  test    eax, eax
0x1807830ab  js      short loc_1807830EA
0x1807830ad  mov     rcx, [rsi]
0x1807830b0  mov     rax, [rcx]
0x1807830b3  mov     rax, [rax+10h]
0x1807830b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807830bc  test    rax, rax
0x1807830bf  jz      loc_1807833B3
0x1807830c5  mov     rcx, [rsi]
0x1807830c8  mov     rax, [rcx]
0x1807830cb  mov     rax, [rax+10h]
0x1807830cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807830d4  mov     rcx, rax; Src
0x1807830d7  lea     rdx, [rbp+2060h+var_20B8]; unsigned __int16 **
0x1807830db  call    ?_HeapAllocString@@YAJPEBGPEAPEAG@Z; _HeapAllocString(ushort const *,ushort * *)
0x1807830e0  mov     ebx, eax
0x1807830e2  test    eax, eax
0x1807830e4  jns     loc_1807833AF
0x1807830ea  mov     rdi, [rbp+2060h+pwzURI]
0x1807830ee  mov     rsi, [rbp+2060h+var_20B8]
0x1807830f2  mov     rcx, cs:g_hProcessHeap; this
0x1807830f9  mov     rdx, rdi; void *
0x1807830fc  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180783101  mov     rdx, [rbp+2060h+var_20C0]; void *
0x180783105  mov     rcx, cs:g_hProcessHeap; this
0x18078310c  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180783111  mov     rcx, cs:g_hProcessHeap; this
0x180783118  mov     rdx, rsi; void *
0x18078311b  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180783120  mov     eax, ebx
0x180783122  mov     rcx, [rbp+2060h+var_50]
0x180783129  xor     rcx, rsp; StackCookie
0x18078312c  call    __security_check_cookie
0x180783131  add     rsp, 2188h
0x180783138  pop     r15
0x18078313a  pop     r14
0x18078313c  pop     r13
0x18078313e  pop     r12
0x180783140  pop     rdi
0x180783141  pop     rsi
0x180783142  pop     rbx
0x180783143  pop     rbp
0x180783144  retn
0x180783146  mov     ecx, r12d
0x180783149  sub     ecx, 8E1h
0x18078314f  jz      loc_180783029
0x180783155  sub     ecx, 0A2h
0x18078315b  jz      loc_180783029
0x180783161  sub     ecx, 41h ; 'A'
0x180783164  jz      loc_18078338E
0x18078316a  sub     ecx, 1
0x18078316d  jz      loc_18078338E
0x180783173  sub     ecx, 582h
0x180783179  jz      loc_18078323F
0x18078317f  cmp     ecx, 2B70h
0x180783185  jnz     short loc_180783120
0x180783187  test    r15, r15
0x18078318a  jz      short loc_180783120
0x18078318c  test    rdi, rdi
0x18078318f  jz      loc_180783235
0x180783195  mov     rcx, [rsi]
0x180783198  mov     rax, [rcx]
0x18078319b  mov     rax, [rax]
0x18078319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807831a3  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x1807831a8  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x1807831ac  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x1807831b4  mov     r8d, 1000h; int
0x1807831ba  mov     rdx, r15; unsigned __int16 *
0x1807831bd  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x1807831c2  xor     ecx, ecx; struct CMarkup *
0x1807831c4  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x1807831c9  mov     ebx, eax
0x1807831cb  test    eax, eax
0x1807831cd  jnz     loc_180783120
0x1807831d3  mov     rcx, [rsi]
0x1807831d6  mov     [rbp+2060h+var_20C0], r14
0x1807831da  mov     rax, [rcx]
0x1807831dd  mov     rax, [rax]
0x1807831e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807831e5  mov     rcx, rax; this
0x1807831e8  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x1807831ed  mov     rcx, [rsi]
0x1807831f0  mov     rbx, rax
0x1807831f3  mov     rdx, [rcx]
0x1807831f6  mov     rax, [rdx]
0x1807831f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807831fe  mov     rcx, rax; this
0x180783201  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180783206  lea     r9, [rbp+2060h+var_20C0]; struct IDataObject **
0x18078320a  mov     rdx, rbx; struct CMarkup *
0x18078320d  lea     r8, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180783211  mov     rcx, rax; struct CDoc *
0x180783214  call    ?CopyURLToDataObject@@YAJPEAVCDoc@@PEAVCMarkup@@PEBGPEAPEAUIDataObject@@@Z; CopyURLToDataObject(CDoc *,CMarkup *,ushort const *,IDataObject * *)
0x180783219  mov     ebx, eax
0x18078321b  test    eax, eax
0x18078321d  js      loc_180783120
0x180783223  mov     rax, [rbp+2060h+var_20C0]
0x180783227  mov     [rdi+8], rax
0x18078322b  mov     word ptr [rdi], 0Dh
0x180783230  jmp     loc_180783120
0x180783235  mov     ebx, 80070057h
0x18078323a  jmp     loc_180783120
0x18078323f  mov     rcx, [rsi]
0x180783242  mov     rax, [rcx]
0x180783245  mov     rax, [rax]
0x180783248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18078324d  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x180783252  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180783256  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x18078325e  mov     r8d, 1000h; int
0x180783264  mov     rdx, r15; unsigned __int16 *
0x180783267  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x18078326c  xor     ecx, ecx; struct CMarkup *
0x18078326e  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x180783273  test    eax, eax
0x180783275  js      loc_180783386
0x18078327b  mov     rcx, [rsi]
0x18078327e  mov     dword ptr [rbp+2060h+var_20C8.lpVtbl], r14d
0x180783282  mov     [rbp+2060h+pwzURI], r14
0x180783286  mov     rax, [rcx]
0x180783289  mov     rax, [rax]
0x18078328c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
