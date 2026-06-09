# CAnchorHelper::ExecHelper(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1807779f8`
- end: `0x1807785bd`
- name: `?ExecHelper@CAnchorHelper@@QEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `3013`
- prototype: `__int64 __fastcall(CAnchorHelper *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1807edf70`
- `0x180824d10`
- `0x180e625b0`
- `0x180f2efb0`

## callees

- `0x180003100`
- `0x18003dcd8`
- `0x18006f7c8`
- `0x1800c8ebc`
- `0x1800d28e0`
- `0x1800e4c70`
- `0x1800f87a0`
- `0x180135278`
- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf048`
- `0x1801c0acc`
- `0x1801c0b08`
- `0x1802e5024`
- `0x180300074`
- `0x18030035c`
- `0x1803245bc`
- `0x180369bc0`
- `0x180373d28`
- `0x18049b38c`
- `0x1804acc50`
- `0x1804dd060`
- `0x1804f7e30`
- `0x1805af914`
- `0x1805ccd98`
- `0x18072b37c`
- `0x1807556d0`
- `0x180771b58`
- `0x1807779f8`
- `0x1807da0a0`
- `0x18081e9cc`
- `0x180831088`
- `0x1808353b8`
- `0x1808393c4`
- `0x180851c70`
- `0x18086debc`
- `0x1808c88a0`
- `0x1808ddd98`
- `0x180967074`
- `0x1809b1478`
- `0x180a06c74`
- `0x180a06de8`
- `0x180a06ed0`
- `0x180a06f08`
- `0x180a07624`
- `0x18105abf4`
- `0x18105f300`
- `0x1810944a0`
- `0x1810944f0`
- `0x1810c2d60`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180778128`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180778128`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNICW` at `0x180778482`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNICW` at `0x180778482`
- `USER32!AllowSetForegroundWindow` at `0x180777f3a`
- `USER32!AllowSetForegroundWindow` at `0x180777f3a`
- `iertutil!CreateUri` at `0x18077843e`
- `iertutil!CreateUri` at `0x18077843e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18077826a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18077826a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180778553`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180778553`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180778168`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180778168`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180778147`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180778147`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180777f5b`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180777f5b`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180777f05`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180777f05`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180777f68`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180777f68`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18077817a`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18077817a`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180777f43`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180778172`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180777f43`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180778172`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18077825b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18077825b`
- `OLEAUT32!__imp_SysFreeString` at `0x18077803d`
- `OLEAUT32!__imp_SysFreeString` at `0x180778047`
- `OLEAUT32!__imp_SysFreeString` at `0x18077803d`
- `OLEAUT32!__imp_SysFreeString` at `0x180778047`

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
  WCHAR *v15; // rdx
  CElement *v16; // rax
  __int64 (__usercall **v17)@<rax>(PROPERTYDESC *__hidden@<rcx>, unsigned int@<edx>, void *@<r8>, struct CBase *@<r9>, struct CVoid *); // r9
  __int64 (__usercall **v18)@<rax>(PROPERTYDESC *__hidden@<rcx>, unsigned int@<edx>, void *@<r8>, struct CBase *@<r9>, struct CVoid *); // r8
  CElement *v19; // rax
  CElement *v20; // rax
  unsigned int *v21; // rax
  __int64 (__fastcall ***v22)(_QWORD); // rcx
  struct IUnknown *v23; // rdi
  CElement *v24; // rax
  CDoc *v25; // r13
  void *v26; // r8
  const unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rsi
  void *v29; // r8
  void *v30; // r8
  struct CElement *v32; // rax
  __int64 (__fastcall ***v33)(_QWORD); // rcx
  CElement *v34; // rax
  struct CMarkup *WindowedMarkupContext; // rbx
  CElement *v36; // rax
  struct CDoc *v37; // rax
  struct CElement *v38; // rax
  __int64 (__fastcall ***v39)(_QWORD); // rcx
  CElement *v40; // rax
  CDoc *v41; // rbx
  struct IMshtmlTabBrowserService **v42; // rax
  unsigned int v43; // ebx
  unsigned int v44; // eax
  struct COmWindowProxy *OmWindowProxy; // rax
  struct COmWindowProxy *v46; // r12
  const unsigned __int16 *v47; // rbx
  struct CBase *v48; // rax
  struct CElement *v49; // rax
  CElement *v50; // rax
  struct CMarkup *MarkupPtr; // r13
  char v52; // cl
  unsigned __int64 v53; // r14
  int v54; // r12d
  bool v55; // zf
  __int64 v56; // rax
  __int64 v57; // rax
  const unsigned __int16 *Url; // rax
  CElement *v59; // rax
  const WCHAR *AAid; // rax
  IStream *v61; // rax
  struct IStream *v62; // rbx
  unsigned int CurrentProcessManager; // edi
  unsigned int AuthorityManager; // eax
  unsigned int v65; // r8d
  unsigned int v66; // r9d
  CDoc *v67; // r13
  _DWORD *PrimaryTraceActivity; // rbx
  int v69; // r9d
  struct CElement *v70; // rax
  struct CElement *v71; // rax
  CElement *v72; // rax
  struct CDocument *v73; // rax
  unsigned int v74; // eax
  int v75; // eax
  __int64 (__fastcall ***v76)(_QWORD); // rcx
  __int64 v77; // rax
  const unsigned __int16 *v78; // rdx
  unsigned int v79; // [rsp+20h] [rbp-140h]
  int psa; // [rsp+28h] [rbp-138h]
  struct IUri *pwzUrl; // [rsp+30h] [rbp-130h]
  unsigned int v82; // [rsp+50h] [rbp-110h]
  unsigned int v83; // [rsp+58h] [rbp-108h]
  int v84; // [rsp+60h] [rbp-100h]
  struct IHTMLWindow2 **v85; // [rsp+68h] [rbp-F8h]
  struct IStream *v86; // [rsp+88h] [rbp-D8h]
  struct CElement *v87; // [rsp+90h] [rbp-D0h]
  int *v88; // [rsp+A8h] [rbp-B8h]
  const unsigned __int16 *v89; // [rsp+B8h] [rbp-A8h]
  struct IDispatch *v90; // [rsp+C0h] [rbp-A0h]
  struct IStream *v91; // [rsp+D8h] [rbp-88h]
  LPCWSTR pwzURI; // [rsp+E0h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+E8h] [rbp-78h] BYREF
  IStream *pstm; // [rsp+F0h] [rbp-70h] BYREF
  struct IUri v95; // [rsp+F8h] [rbp-68h] BYREF
  struct IDataObject *v96; // [rsp+100h] [rbp-60h] BYREF
  unsigned __int16 *v97; // [rsp+108h] [rbp-58h] BYREF
  BSTR v98; // [rsp+110h] [rbp-50h] BYREF
  LPWSTR ppwsz; // [rsp+118h] [rbp-48h] BYREF
  unsigned int v100[2]; // [rsp+120h] [rbp-40h] BYREF
  struct _GUID v101; // [rsp+130h] [rbp-30h] BYREF
  struct _GUID v102; // [rsp+140h] [rbp-20h] BYREF
  _BYTE v103[20]; // [rsp+150h] [rbp-10h] BYREF
  int v104; // [rsp+164h] [rbp+4h]
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
        v19 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        if ( *((char *)CElement::Doc(v19) + 4868) < 0 )
        {
          v20 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          v21 = (unsigned int *)CElement::Doc(v20);
          if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v21[1260], v21[1261], v21[1263], v21[1262]) )
            return ContextUrls;
        }
        goto LABEL_24;
      case 15:
        v16 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD, _QWORD))this)(*(_QWORD *)this, 0);
        v17 = &s_propdescCIE9EventListcopy;
        v18 = &s_propdescCElementoncopy;
        break;
      case 16:
        v16 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        v17 = &s_propdescCIE9EventListcut;
        v18 = &s_propdescCElementoncut;
        break;
      case 26:
        goto LABEL_57;
      case 2136:
      case 2137:
LABEL_24:
        if ( !v9 || (unsigned int)_tcsnipre(L"mailto:", 7, v9, -1) )
          return ContextUrls;
        v22 = *(__int64 (__fastcall ****)(_QWORD))this;
        v23 = 0;
        pwzURI = 0;
        v96 = 0;
        v97 = 0;
        v24 = (CElement *)(**v22)(v22);
        v98 = (BSTR)CElement::Doc(v24);
        v25 = (CDoc *)v98;
        if ( v7 != 2273 && v7 != 2268 )
        {
          ContextUrls = CAnchorHelper::GetContextUrls(this, (unsigned __int16 **)&pwzURI, (unsigned __int16 **)&v96);
          if ( (ContextUrls & 0x80000000) != 0 )
          {
LABEL_31:
            v23 = (struct IUnknown *)pwzURI;
LABEL_32:
            v28 = v97;
LABEL_33:
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v23, v26);
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v96, v29);
            MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v28, v30);
            return ContextUrls;
          }
          if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this) )
          {
            v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
            ContextUrls = _HeapAllocString(v27, &v97);
            if ( (ContextUrls & 0x80000000) != 0 )
              goto LABEL_31;
            v10 = v97;
          }
          if ( !IsScriptExecutableUrl(v9) )
          {
            v50 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            MarkupPtr = CElement::GetMarkupPtr(v50);
            v52 = *((_BYTE *)this + 16) & 0x40;
            ppwsz = 0;
            v53 = (-(__int64)(v52 != 0) & 0xFFFFFFFFF0LL) + 0x200000000000014LL;
            if ( v7 == 2137 || v7 == 2435 )
            {
              v55 = v7 == 2137;
              v56 = 0x10004000000LL;
              v54 = 1;
              if ( !v55 )
                v56 = 0x10008000000LL;
              v53 |= v56;
            }
            else
            {
              v54 = 0;
            }
            if ( MarkupPtr )
            {
              v57 = *((_QWORD *)MarkupPtr + 27);
              if ( v57 && (*(_BYTE *)(v57 + 8) & 1) != 0 )
                v53 |= 0x10000000u;
              Url = CMarkup::GetUrl(MarkupPtr);
              if ( IsNeedEdgePage(Url) )
              {
                v59 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
                AAid = CElement::GetAAid(v59);
                if ( !StrCmpICW(L"ContinueInIE", AAid) )
                {
                  pstm = 0;
                  v53 |= 0x100000000000uLL;
                  v61 = SHCreateMemStream(0, 0);
                  TSmartPointer<IDispGeometry>::TransferFrom<IDispTransformedGeometry>(&pstm, v61);
                  v62 = pstm;
                  if ( pstm && IStream_WriteStr(pstm, v9) >= 0 )
                  {
                    CurrentProcessManager = IsoGetCurrentProcessManager();
                    AuthorityManager = IsoGetAuthorityManager();
                    LCIEPostMessageWithStream(AuthorityManager, CurrentProcessManager, v65, v66, v62);
                  }
                  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pstm);
                }
              }
              pstm = 0;
              if ( (int)CMarkup::GetTopmostMarkup(MarkupPtr, &pstm) >= 0 && *((_BYTE *)pstm + 249) )
                v53 |= 0x20000000000uLL;
              if ( CAnchorHelper::IsInvalidCertErrorPage(MarkupPtr) )
              {
                v53 |= 0x20000000u;
                ppwsz = (LPWSTR)CMarkup::GetDwnPost(MarkupPtr);
              }
            }
            v67 = (CDoc *)v98;
            PrimaryTraceActivity = (_DWORD *)CDoc::GetPrimaryTraceActivity(v98);
            if ( PrimaryTraceActivity )
            {
              v103[16] = 0;
              v101 = *CreateUserInputId(&v102);
              ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)v103, &v101);
              v55 = *PrimaryTraceActivity == 1;
              v104 = 3;
              if ( v55
                && (unsigned int)dword_181559C88 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x200000000008LL) )
              {
                *(_QWORD *)v100 = GlobalThreadState();
                *(_QWORD *)&v102.Data1 = IEConfiguration_GetCLSID(268435459);
                LODWORD(bstrString) = 0;
                *(_QWORD *)&v101.Data1 = v53;
                LODWORD(v95.lpVtbl) = IsSpartanApp();
                LODWORD(pstm) = v54;
                LODWORD(v98) = (v53 & 0x4000000) != 0;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                  (unsigned int)&dword_181559C88,
                  (unsigned int)&dword_181519A9C,
                  (_DWORD)PrimaryTraceActivity + 8,
                  v69,
                  (__int64)&pstm,
                  (__int64)&v98,
                  (__int64)&v95,
                  (__int64)&v101,
                  (__int64)&bstrString,
                  (__int64)&v102,
                  (__int64)v100);
              }
              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)v103);
            }
            v70 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            v28 = v97;
            v23 = (struct IUnknown *)pwzURI;
            ContextUrls = CDoc::FollowHyperlink(
                            v67,
                            v9,
                            v97,
                            v70,
                            (struct CDwnPost *)ppwsz,
                            0,
                            pwzUrl,
                            0,
                            0,
                            0,
                            v82,
                            v83,
                            v84,
                            v85,
                            v54,
                            v53,
                            0,
                            v86,
                            v87,
                            pwzURI,
                            0,
                            v88,
                            0,
                            v89,
                            v90,
                            (const unsigned __int16 *)v96,
                            0,
                            v91);
            goto LABEL_33;
          }
          bstrString = 0;
          v98 = 0;
          OmWindowProxy = CAnchorHelper::GetOmWindowProxy(this);
          v23 = (struct IUnknown *)pwzURI;
          v46 = OmWindowProxy;
          if ( pwzURI )
          {
            v47 = pwzURI;
          }
          else
          {
            v48 = (struct CBase *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            GetFullyExpandedUrl(v48, 0, &bstrString, &v98, 0, psa);
            v47 = v98;
            if ( !v98 )
            {
              ContextUrls = -2147024891;
              goto LABEL_65;
            }
          }
          v49 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CDoc::ExecuteScriptURL(v25, v9, v47, v10, v79, v46, (struct IHTMLWindow2 **)pwzUrl, v49);
LABEL_65:
          SysFreeString(bstrString);
          SysFreeString(v98);
          goto LABEL_32;
        }
        v71 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
        ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v71, 0xFFFFFFFF, 0);
        if ( ContextUrls )
          goto LABEL_32;
        if ( v7 == 2273 )
        {
          v72 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          v73 = CElement::Document(v72);
          v74 = CDoc::PrintHandler((CDoc *)v98, v73, 0, pszStr1, 0, 0, 0, 0, 0, 0);
        }
        else
        {
          v75 = CAnchorHelper::GetContextUrls(this, (unsigned __int16 **)&pwzURI, (unsigned __int16 **)&v96);
          v23 = (struct IUnknown *)pwzURI;
          if ( v75 >= 0 )
          {
            pwzURI = 0;
            if ( CreateUri((LPCWSTR)v23, 0x3002B80u, 0, (IUri **)&pwzURI) >= 0 )
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
          v76 = *(__int64 (__fastcall ****)(_QWORD))this;
          pstm = 0;
          if ( *(__int64 (__fastcall **)())(*(_QWORD *)(**v76)(v76) + 1624LL) != _vtguard )
            _report_securityfailure(1);
          v77 = (***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          if ( (*(int (__fastcall **)(__int64, GUID *, IStream **))(*(_QWORD *)v77 + 1536LL))(
                 v77,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pstm) < 0 )
            pstm = 0;
          if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_USE_LEGACY_DOFILEDOWNLOAD_FUNCTION) )
          {
            if ( (_BYTE)v10 )
            {
              pwzURI = 0;
              CStr::Append((CStr *)&pwzURI, L"Referer: ");
              CStr::Append((CStr *)&pwzURI, (const unsigned __int16 *)v23);
              CStr::Append((CStr *)&pwzURI, L"\r\n");
              ppwsz = 0;
              if ( SHStrDupW(pwzURI, &ppwsz) >= 0 )
                ContextUrls = IEFrameHelper::DoFileDownloadEx(
                                (IEFrameHelper *)pszStr1,
                                ppwsz,
                                (unsigned __int16 *)pstm,
                                v23);
              CStr::_Free((CStr *)&pwzURI);
              goto LABEL_116;
            }
            v74 = IEFrameHelper::DoFileDownloadEx((IEFrameHelper *)pszStr1, 0, (unsigned __int16 *)pstm, 0);
          }
          else
          {
            v74 = IEFrameHelper::DoFileDownload((IEFrameHelper *)pszStr1, v78);
          }
        }
        ContextUrls = v74;
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
          v15 = (WCHAR *)v9;
        }
        else
        {
          v14 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v14, 0xFFFFFFFF, 0);
          if ( ContextUrls )
          {
LABEL_15:
            CStr::_Free((CStr *)&pwzURI);
            return ContextUrls;
          }
          v15 = pszStr1;
        }
        ContextUrls = CDoc::AddToFavorites(v13, v15, (unsigned __int16 *)pwzURI);
        goto LABEL_15;
      default:
        if ( v7 == 2262 && v9 )
          return (unsigned int)CAnchorHelper::CopyLinkToClipboard(this, 0);
        return ContextUrls;
    }
LABEL_20:
    LODWORD(bstrString) = 0;
    return (unsigned int)CElement::Fire_ondragHelper(
                           v16,
                           0,
                           (const struct PROPERTYDESC_BASIC *)v18,
                           (const struct PROPERTYDESC_BASIC *)v17,
                           (unsigned int *)&bstrString,
                           0) != 0
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
      v16 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
      v17 = &s_propdescCIE9EventListpaste;
      v18 = &s_propdescCElementonpaste;
      goto LABEL_20;
    case 3911:
      v38 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
      if ( (int)CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v38, 0xFFFFFFFF, 0) >= 0 )
      {
        v39 = *(__int64 (__fastcall ****)(_QWORD))this;
        LODWORD(v95.lpVtbl) = 0;
        pwzURI = 0;
        v40 = (CElement *)(**v39)(v39);
        v41 = CElement::Doc(v40);
        if ( v41 )
        {
          v42 = (struct IMshtmlTabBrowserService **)TSmartPointer<ID3D11Device>::operator&(&pwzURI);
          if ( (int)CDoc::GetTabBrowserService(v41, v42) >= 0
            && (*(int (__fastcall **)(LPCWSTR, struct IUri *))(*(_QWORD *)pwzURI + 56LL))(pwzURI, &v95) >= 0 )
          {
            LODWORD(bstrString) = 0;
            v96 = 0;
            if ( (int)IsoAllocMessageBuffer(
                        (unsigned int)v95.lpVtbl,
                        (unsigned int *)&bstrString,
                        0x106Cu,
                        (struct _IsoMessage **)&v96) >= 0 )
            {
              if ( (int)StringCchCopyW((unsigned __int16 *)&v96[4], 0x824u, pszStr1) < 0
                || (LODWORD(v96[525].lpVtbl) = 3,
                    AllowSetForegroundWindow(0xFFFFFFFF),
                    v43 = (unsigned int)bstrString,
                    v44 = IsoGetCurrentProcessManager(),
                    (int)LCIEPostMessage((unsigned int)v95.lpVtbl, v44, 0xC0Fu, 0, v43) < 0) )
              {
                IsoFreeMessageBuffer((unsigned int)bstrString);
              }
            }
          }
        }
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pwzURI);
      }
      return 0;
    default:
      if ( v7 == 15031 && v9 )
      {
        if ( a6 )
        {
          v32 = (struct CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
          ContextUrls = CMarkup::ExpandUrl(0, v9, 4096, pszStr1, v32, 0xFFFFFFFF, 0);
          if ( !ContextUrls )
          {
            v33 = *(__int64 (__fastcall ****)(_QWORD))this;
            v96 = 0;
            v34 = (CElement *)(**v33)(v33);
            WindowedMarkupContext = CElement::GetWindowedMarkupContext(v34);
            v36 = (CElement *)(***(__int64 (__fastcall ****)(_QWORD))this)(*(_QWORD *)this);
            v37 = CElement::Doc(v36);
            ContextUrls = CopyURLToDataObject(v37, WindowedMarkupContext, pszStr1, &v96);
            if ( (ContextUrls & 0x80000000) == 0 )
            {
              a6->llVal = (LONGLONG)v96;
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
0x1807779f8  push    rbp
0x1807779fa  push    rbx
0x1807779fb  push    rsi
0x1807779fc  push    rdi
0x1807779fd  push    r12
0x1807779ff  push    r13
0x180777a01  push    r14
0x180777a03  push    r15
0x180777a05  lea     rbp, [rsp-2028h]
0x180777a0d  mov     eax, 2188h
0x180777a12  call    _alloca_probe
0x180777a17  sub     rsp, rax
0x180777a1a  mov     rax, cs:__security_cookie
0x180777a21  xor     rax, rsp
0x180777a24  mov     [rbp+2060h+var_50], rax
0x180777a2b  mov     rdi, [rbp+2060h+arg_28]
0x180777a32  mov     rax, rdx
0x180777a35  mov     rsi, rcx
0x180777a38  mov     edx, r8d; unsigned int
0x180777a3b  mov     rcx, rax; struct _GUID *
0x180777a3e  call    ?IDMFromCmdID@CBase@@SAHPEBU_GUID@@K@Z; CBase::IDMFromCmdID(_GUID const *,ulong)
0x180777a43  mov     rdx, [rsi]
0x180777a46  mov     r12d, eax
0x180777a49  mov     ebx, 80040100h
0x180777a4e  mov     rcx, [rdx]
0x180777a51  mov     rax, [rcx+8]
0x180777a55  mov     rcx, rdx
0x180777a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777a5d  mov     r15, rax
0x180777a60  xor     r14d, r14d
0x180777a63  mov     eax, 8DCh
0x180777a68  cmp     r12d, eax
0x180777a6b  jg      loc_180777D55
0x180777a71  jz      loc_180777BDD
0x180777a77  mov     edx, r12d
0x180777a7a  sub     edx, 0Fh
0x180777a7d  jz      loc_180777BBF
0x180777a83  sub     edx, 1
0x180777a86  jz      loc_180777B7C
0x180777a8c  sub     edx, 0Ah
0x180777a8f  jz      loc_180777F7F
0x180777a95  sub     edx, 83Eh
0x180777a9b  jz      loc_180777C39
0x180777aa1  sub     edx, 1
0x180777aa4  jz      loc_180777C39
0x180777aaa  sub     edx, 7Ch ; '|'
0x180777aad  jz      short loc_180777AD2
0x180777aaf  cmp     edx, 1
0x180777ab2  jnz     loc_180777D30
0x180777ab8  test    r15, r15
0x180777abb  jz      loc_180777D30
0x180777ac1  xor     edx, edx; unsigned __int16 *
0x180777ac3  mov     rcx, rsi; this
0x180777ac6  call    ?CopyLinkToClipboard@CAnchorHelper@@QEAAJPEBG@Z; CAnchorHelper::CopyLinkToClipboard(ushort const *)
0x180777acb  mov     ebx, eax
0x180777acd  jmp     loc_180777D30
0x180777ad2  test    r15, r15
0x180777ad5  jz      loc_180777D30
0x180777adb  mov     rcx, [rsi]
0x180777ade  mov     [rbp+2060h+pwzURI], r14
0x180777ae2  mov     rax, [rcx]
0x180777ae5  mov     rax, [rax]
0x180777ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777aed  mov     rcx, rax; this
0x180777af0  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180777af5  mov     rcx, [rsi]
0x180777af8  mov     rdi, rax
0x180777afb  mov     rdx, [rcx]
0x180777afe  mov     rax, [rdx+18h]
0x180777b02  lea     rdx, [rbp+2060h+pwzURI]
0x180777b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777b0b  mov     rcx, r15; unsigned __int16 *
0x180777b0e  call    ?GetUrlScheme@@YAIPEBG@Z; GetUrlScheme(ushort const *)
0x180777b13  add     eax, 0FFFFFFF1h
0x180777b16  cmp     eax, 1
0x180777b19  jbe     short loc_180777B69
0x180777b1b  mov     rcx, [rsi]
0x180777b1e  mov     rax, [rcx]
0x180777b21  mov     rax, [rax]
0x180777b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777b29  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x180777b2e  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180777b32  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x180777b3a  mov     r8d, 1000h; int
0x180777b40  mov     rdx, r15; unsigned __int16 *
0x180777b43  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x180777b48  xor     ecx, ecx; struct CMarkup *
0x180777b4a  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x180777b4f  mov     ebx, eax
0x180777b51  test    eax, eax
0x180777b53  jz      short loc_180777B63
0x180777b55  lea     rcx, [rbp+2060h+pwzURI]; this
0x180777b59  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180777b5e  jmp     loc_180777D30
0x180777b63  lea     rdx, [rbp+2060h+pszStr1]
0x180777b67  jmp     short loc_180777B6C
0x180777b69  mov     rdx, r15; unsigned __int16 *
0x180777b6c  mov     r8, [rbp+2060h+pwzURI]; unsigned __int16 *
0x180777b70  mov     rcx, rdi; this
0x180777b73  call    ?AddToFavorites@CDoc@@QEAAJPEBGPEAG@Z; CDoc::AddToFavorites(ushort const *,ushort *)
0x180777b78  mov     ebx, eax
0x180777b7a  jmp     short loc_180777B55
0x180777b7c  mov     rcx, [rsi]
0x180777b7f  mov     rax, [rcx]
0x180777b82  mov     rax, [rax]
0x180777b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777b8a  lea     r9, s_propdescCIE9EventListcut; struct PROPERTYDESC_BASIC *
0x180777b91  lea     r8, s_propdescCElementoncut; struct PROPERTYDESC_BASIC *
0x180777b98  lea     rcx, [rbp+2060h+bstrString]
0x180777b9c  mov     [rsp+21C0h+psa], r14; struct tagPOINT *
0x180777ba1  mov     [rsp+21C0h+var_21A0], rcx; unsigned int *
0x180777ba6  xor     edx, edx; int
0x180777ba8  mov     rcx, rax; this
0x180777bab  mov     dword ptr [rbp+2060h+bstrString], r14d
0x180777baf  call    ?Fire_ondragHelper@CElement@@QEAAHJPEBUPROPERTYDESC_BASIC@@0PEAKPEBUtagPOINT@@@Z; CElement::Fire_ondragHelper(long,PROPERTYDESC_BASIC const *,PROPERTYDESC_BASIC const *,ulong *,tagPOINT const *)
0x180777bb4  neg     eax
0x180777bb6  sbb     ecx, ecx
0x180777bb8  and     ebx, ecx
0x180777bba  jmp     loc_180777D30
0x180777bbf  mov     rcx, [rsi]
0x180777bc2  mov     rax, [rcx]
0x180777bc5  mov     rax, [rax]
0x180777bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777bcd  lea     r9, s_propdescCIE9EventListcopy
0x180777bd4  lea     r8, s_propdescCElementoncopy
0x180777bdb  jmp     short loc_180777B98
0x180777bdd  mov     rcx, [rsi]
0x180777be0  mov     rax, [rcx]
0x180777be3  mov     rax, [rax]
0x180777be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777beb  mov     rcx, rax; this
0x180777bee  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180777bf3  test    byte ptr [rax+1304h], 80h
0x180777bfa  jz      short loc_180777C39
0x180777bfc  mov     rcx, [rsi]
0x180777bff  mov     rax, [rcx]
0x180777c02  mov     rax, [rax]
0x180777c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777c0a  mov     rcx, rax; this
0x180777c0d  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180777c12  mov     r9d, [rax+13B8h]
0x180777c19  mov     r8d, [rax+13BCh]
0x180777c20  mov     edx, [rax+13B4h]
0x180777c26  mov     ecx, [rax+13B0h]
0x180777c2c  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x180777c31  test    al, al
0x180777c33  jz      loc_180777D30
0x180777c39  test    r15, r15
0x180777c3c  jz      loc_180777D30
0x180777c42  or      r9d, 0FFFFFFFFh; int
0x180777c46  lea     rcx, aMailto_0; "mailto:"
0x180777c4d  mov     r8, r15; unsigned __int16 *
0x180777c50  lea     edx, [r9+8]; cchCount2
0x180777c54  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x180777c59  test    eax, eax
0x180777c5b  jnz     loc_180777D30
0x180777c61  mov     rcx, [rsi]
0x180777c64  mov     rdi, r14
0x180777c67  mov     [rbp+2060h+pwzURI], r14
0x180777c6b  mov     [rbp+2060h+var_20C0], r14
0x180777c6f  mov     [rbp+2060h+var_20B8], r14
0x180777c73  mov     rax, [rcx]
0x180777c76  mov     rax, [rax]
0x180777c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777c7e  mov     rcx, rax; this
0x180777c81  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180777c86  mov     [rbp+2060h+var_20B0], rax
0x180777c8a  mov     r13, rax
0x180777c8d  cmp     r12d, 8E1h
0x180777c94  jz      loc_18077837E
0x180777c9a  cmp     r12d, 8DCh
0x180777ca1  jz      loc_18077837E
0x180777ca7  lea     r8, [rbp+2060h+var_20C0]; unsigned __int16 **
0x180777cab  mov     rcx, rsi; this
0x180777cae  lea     rdx, [rbp+2060h+pwzURI]; unsigned __int16 **
0x180777cb2  call    ?GetContextUrls@CAnchorHelper@@AEAAJPEAPEAG0@Z; CAnchorHelper::GetContextUrls(ushort * *,ushort * *)
0x180777cb7  mov     ebx, eax
0x180777cb9  test    eax, eax
0x180777cbb  js      short loc_180777CFA
0x180777cbd  mov     rcx, [rsi]
0x180777cc0  mov     rax, [rcx]
0x180777cc3  mov     rax, [rax+10h]
0x180777cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777ccc  test    rax, rax
0x180777ccf  jz      loc_180777FA4
0x180777cd5  mov     rcx, [rsi]
0x180777cd8  mov     rax, [rcx]
0x180777cdb  mov     rax, [rax+10h]
0x180777cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777ce4  mov     rcx, rax; Src
0x180777ce7  lea     rdx, [rbp+2060h+var_20B8]; unsigned __int16 **
0x180777ceb  call    ?_HeapAllocString@@YAJPEBGPEAPEAG@Z; _HeapAllocString(ushort const *,ushort * *)
0x180777cf0  mov     ebx, eax
0x180777cf2  test    eax, eax
0x180777cf4  jns     loc_180777FA0
0x180777cfa  mov     rdi, [rbp+2060h+pwzURI]
0x180777cfe  mov     rsi, [rbp+2060h+var_20B8]
0x180777d02  mov     rcx, cs:g_hProcessHeap; this
0x180777d09  mov     rdx, rdi; void *
0x180777d0c  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180777d11  mov     rdx, [rbp+2060h+var_20C0]; void *
0x180777d15  mov     rcx, cs:g_hProcessHeap; this
0x180777d1c  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180777d21  mov     rcx, cs:g_hProcessHeap; this
0x180777d28  mov     rdx, rsi; void *
0x180777d2b  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180777d30  mov     eax, ebx
0x180777d32  mov     rcx, [rbp+2060h+var_50]
0x180777d39  xor     rcx, rsp; StackCookie
0x180777d3c  call    __security_check_cookie
0x180777d41  add     rsp, 2188h
0x180777d48  pop     r15
0x180777d4a  pop     r14
0x180777d4c  pop     r13
0x180777d4e  pop     r12
0x180777d50  pop     rdi
0x180777d51  pop     rsi
0x180777d52  pop     rbx
0x180777d53  pop     rbp
0x180777d54  retn
0x180777d55  mov     ecx, r12d
0x180777d58  sub     ecx, 8E1h
0x180777d5e  jz      loc_180777C39
0x180777d64  sub     ecx, 0A2h
0x180777d6a  jz      loc_180777C39
0x180777d70  sub     ecx, 41h ; 'A'
0x180777d73  jz      loc_180777F7F
0x180777d79  sub     ecx, 1
0x180777d7c  jz      loc_180777F7F
0x180777d82  sub     ecx, 582h
0x180777d88  jz      loc_180777E4E
0x180777d8e  cmp     ecx, 2B70h
0x180777d94  jnz     short loc_180777D30
0x180777d96  test    r15, r15
0x180777d99  jz      short loc_180777D30
0x180777d9b  test    rdi, rdi
0x180777d9e  jz      loc_180777E44
0x180777da4  mov     rcx, [rsi]
0x180777da7  mov     rax, [rcx]
0x180777daa  mov     rax, [rax]
0x180777dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777db2  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x180777db7  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180777dbb  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x180777dc3  mov     r8d, 1000h; int
0x180777dc9  mov     rdx, r15; unsigned __int16 *
0x180777dcc  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x180777dd1  xor     ecx, ecx; struct CMarkup *
0x180777dd3  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x180777dd8  mov     ebx, eax
0x180777dda  test    eax, eax
0x180777ddc  jnz     loc_180777D30
0x180777de2  mov     rcx, [rsi]
0x180777de5  mov     [rbp+2060h+var_20C0], r14
0x180777de9  mov     rax, [rcx]
0x180777dec  mov     rax, [rax]
0x180777def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777df4  mov     rcx, rax; this
0x180777df7  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x180777dfc  mov     rcx, [rsi]
0x180777dff  mov     rbx, rax
0x180777e02  mov     rdx, [rcx]
0x180777e05  mov     rax, [rdx]
0x180777e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777e0d  mov     rcx, rax; this
0x180777e10  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180777e15  lea     r9, [rbp+2060h+var_20C0]; struct IDataObject **
0x180777e19  mov     rdx, rbx; struct CMarkup *
0x180777e1c  lea     r8, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180777e20  mov     rcx, rax; struct CDoc *
0x180777e23  call    ?CopyURLToDataObject@@YAJPEAVCDoc@@PEAVCMarkup@@PEBGPEAPEAUIDataObject@@@Z; CopyURLToDataObject(CDoc *,CMarkup *,ushort const *,IDataObject * *)
0x180777e28  mov     ebx, eax
0x180777e2a  test    eax, eax
0x180777e2c  js      loc_180777D30
0x180777e32  mov     rax, [rbp+2060h+var_20C0]
0x180777e36  mov     [rdi+8], rax
0x180777e3a  mov     word ptr [rdi], 0Dh
0x180777e3f  jmp     loc_180777D30
0x180777e44  mov     ebx, 80070057h
0x180777e49  jmp     loc_180777D30
0x180777e4e  mov     rcx, [rsi]
0x180777e51  mov     rax, [rcx]
0x180777e54  mov     rax, [rax]
0x180777e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180777e5c  mov     [rsp+21C0h+pwzUrl], r14; pwzUrl
0x180777e61  lea     r9, [rbp+2060h+pszStr1]; unsigned __int16 *
0x180777e65  mov     dword ptr [rsp+21C0h+psa], 0FFFFFFFFh; unsigned int
0x180777e6d  mov     r8d, 1000h; int
0x180777e73  mov     rdx, r15; unsigned __int16 *
0x180777e76  mov     [rsp+21C0h+var_21A0], rax; struct CElement *
0x180777e7b  xor     ecx, ecx; struct CMarkup *
0x180777e7d  call    ?ExpandUrl@CMarkup@@SAJPEAV1@PEBGJPEAGPEAVCElement@@K1@Z; CMarkup::ExpandUrl(CMarkup *,ushort const *,long,ushort *,CElement *,ulong,ushort const *)
0x180777e82  test    eax, eax
0x180777e84  js      loc_180777F77
0x180777e8a  mov     rcx, [rsi]
0x180777e8d  mov     dword ptr [rbp+2060h+var_20C8.lpVtbl], r14d
0x180777e91  mov     [rbp+2060h+pwzURI], r14
0x180777e95  mov     rax, [rcx]
0x180777e98  mov     rax, [rax]
0x180777e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
