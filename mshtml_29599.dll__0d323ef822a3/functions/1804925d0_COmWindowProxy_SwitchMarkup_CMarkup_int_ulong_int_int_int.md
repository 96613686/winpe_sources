# COmWindowProxy::SwitchMarkup(CMarkup *,int,ulong,int,int,int)

- ea: `0x1804925d0`
- end: `0x180493a1e`
- name: `?SwitchMarkup@COmWindowProxy@@QEAAJPEAVCMarkup@@HKHHH@Z`
- size: `5198`
- prototype: `__int64 __usercall@<rax>(COmWindowProxy *__hidden this@<rcx>, struct CMarkup *@<rdx>, int@<r8d>, unsigned int@<r9d>, int, int, int)`
- caller_count: `9`
- callee_count: `122`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180109630`
- `0x1801365c4`
- `0x180493ae0`
- `0x18069c3f4`
- `0x1807736a0`
- `0x18080c558`
- `0x1808261bc`
- `0x180826508`
- `0x1808c3268`

## callees

- `0x180012c04`
- `0x1800148b0`
- `0x180023974`
- `0x1800ad370`
- `0x1800c2b18`
- `0x1800c81dc`
- `0x1800c8e80`
- `0x1800e2b08`
- `0x1800e45d8`
- `0x1800f5454`
- `0x18011b198`
- `0x18011f0ac`
- `0x180135194`
- `0x180135278`
- `0x180142704`
- `0x180144d1c`
- `0x180146f6c`
- `0x18014a898`
- `0x180154a54`
- `0x1801c0acc`
- `0x18021f090`
- `0x180222bb0`
- `0x180223a8c`
- `0x18022408c`
- `0x180226148`
- `0x180227848`
- `0x1802e59bc`
- `0x1802e97e0`
- `0x1802eb020`
- `0x1802fbf18`
- `0x18034bea8`
- `0x18034cec4`
- `0x180357e7c`
- `0x180373368`
- `0x1803e2554`
- `0x1803ea960`
- `0x1803eeed4`
- `0x180439b78`
- `0x18043c328`
- `0x18043c548`
- `0x180491d9c`
- `0x1804925d0`
- `0x1804f594c`
- `0x1804f7e30`
- `0x1804f8b0c`
- `0x1804fa440`
- `0x1804fa5e0`
- `0x1804fcdc0`
- `0x180505794`
- `0x180517578`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1804935bb`
- `KERNEL32!GetTickCount` at `0x1804935bb`
- `KERNEL32!GetCurrentThreadId` at `0x180492875`
- `KERNEL32!GetCurrentThreadId` at `0x180492875`
- `KERNEL32!LeaveCriticalSection` at `0x180492bea`
- `KERNEL32!LeaveCriticalSection` at `0x180492bea`
- `KERNEL32!EnterCriticalSection` at `0x180492bd5`
- `KERNEL32!EnterCriticalSection` at `0x180492bd5`
- `USER32!ValidateRect` at `0x180493043`
- `USER32!ValidateRect` at `0x180493043`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180493569`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180493569`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180492889`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180492889`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1804928bb`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x1804928bb`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z` at `0x1804928a0`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z` at `0x1804928a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18049301b`
- `OLEAUT32!__imp_SysFreeString` at `0x18049301b`
- `OLEAUT32!__imp_VariantInit` at `0x1804929a6`
- `OLEAUT32!__imp_VariantInit` at `0x1804936e0`
- `OLEAUT32!__imp_VariantInit` at `0x1804929a6`
- `OLEAUT32!__imp_VariantInit` at `0x1804936e0`
- `OLEAUT32!__imp_VariantClear` at `0x1804932e2`
- `OLEAUT32!__imp_VariantClear` at `0x1804932e2`

## string_xrefs

- `0x18049291e`: `COmWindowProxy::SwitchMarkup - fPrimarySwitch=%d dwTravelLogFlags=0x%08lX pWindowOld=0x%08lX pMarkupOld=0x%08lX OldUrl=%S pMarkupNew=0x%08lX NewUrl=%S`

## pseudocode

```c
__int64 __fastcall COmWindowProxy::SwitchMarkup(
        COmWindowProxy *this,
        struct CMarkup *a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7)
{
  unsigned int v8; // r12d
  __int64 v11; // r13
  unsigned __int64 v12; // r15
  struct IUnknown *v13; // rsi
  COmWindowProxy *v14; // r12
  struct CDoc *v15; // rsi
  struct IUnknown *v16; // rbx
  int v18; // eax
  DWORD CurrentThreadId; // eax
  int v20; // eax
  unsigned __int16 *v21; // rbx
  const wchar_t *v22; // rax
  int v23; // ebx
  int v24; // ecx
  unsigned int v25; // r9d
  int FrameZone; // eax
  LONG lVal; // ecx
  __int64 v28; // rdx
  const unsigned __int16 *v29; // rdx
  CEditRouter *EditRouter; // rax
  __int64 v31; // rax
  struct IUnknown *v32; // rcx
  __int64 v33; // rcx
  void (__fastcall *IEFrameProcAddress)(__int64); // rax
  struct CRootElement *v35; // rax
  struct CElement *LookasidePtr2; // rax
  CElement *v37; // rbx
  struct IFrameContentData *FrameContentData; // rax
  int v39; // edi
  int v40; // edx
  struct CElement *v41; // rax
  CElement *ActiveElement; // rax
  struct CRootElement *v43; // rax
  int v44; // eax
  bool v45; // zf
  BOOL v46; // edi
  const unsigned __int16 *Url; // rbx
  const unsigned __int16 *v48; // rax
  _BYTE *LookasidePtr; // rbx
  CSecurityContext *v50; // rbx
  const unsigned __int16 *v51; // rax
  bool v52; // r12
  struct CScriptCollection *ScriptCollection; // rax
  struct CJScript9Holder *JScript9Holder; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  int IsPrimaryMarkup; // ebx
  __int64 v58; // rax
  HWND v59; // rcx
  struct CRootElement *v60; // rax
  CDocument *v61; // rbx
  enum _htmlDesignMode AAdesignMode; // edi
  __int64 v63; // rcx
  int v64; // r8d
  __int64 v65; // rdx
  unsigned int Gwnd; // eax
  int v67; // edx
  int v68; // edx
  int v69; // ecx
  int v70; // edx
  int v71; // ecx
  COmWindowProxy *v72; // rdi
  __int64 v73; // rbx
  const unsigned __int16 *v74; // rax
  CMarkup *v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rbx
  __int64 v78; // rdi
  int i; // ebx
  __int64 v80; // rcx
  __int64 v81; // rcx
  void **v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rax
  struct CBase *v87; // rdi
  __int64 v88; // rcx
  __int64 v89; // rax
  struct CJScript9Holder *v90; // rbx
  void **v91; // r13
  int v92; // r12d
  CStr *v93; // rbx
  int v94; // edi
  struct CMarkup *v95; // rax
  int IsPageActionAllowed; // edx
  CDoc *v97; // rcx
  struct CMarkup *v98; // rbx
  __int64 v99; // rdx
  struct IUnknown *v100; // rcx
  int v101; // r10d
  int v102; // edx
  int (__fastcall ***v103)(_QWORD, GUID *, struct IUnknown **); // rcx
  struct CMarkup *v104; // rax
  int (__fastcall ***v105)(_QWORD, GUID *, struct IUnknown **); // rcx
  int v106; // eax
  void (__fastcall *v107)(struct CMarkup *); // rax
  struct CRootElement *v108; // rax
  CMarkup *v109; // rcx
  CZoomState *v110; // rcx
  bool v111; // al
  CTask *v112; // rcx
  const wchar_t *v113; // [rsp+38h] [rbp-B9h]
  int v114; // [rsp+40h] [rbp-B1h]
  struct IDispatch *v115; // [rsp+48h] [rbp-A9h] BYREF
  struct IUnknown *v116; // [rsp+50h] [rbp-A1h] BYREF
  int IsPrimaryWindow; // [rsp+58h] [rbp-99h]
  unsigned int v118; // [rsp+5Ch] [rbp-95h]
  int v119; // [rsp+60h] [rbp-91h]
  int v120; // [rsp+64h] [rbp-8Dh]
  int v121; // [rsp+68h] [rbp-89h]
  CBaseFT *v122; // [rsp+70h] [rbp-81h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-79h] BYREF
  int IsConnectedToThisMarkup; // [rsp+90h] [rbp-61h]
  __int64 v125; // [rsp+98h] [rbp-59h]
  _BYTE v126[16]; // [rsp+A0h] [rbp-51h] BYREF
  _BYTE v127[24]; // [rsp+B0h] [rbp-41h] BYREF
  __int64 v128; // [rsp+C8h] [rbp-29h]
  char v129; // [rsp+D8h] [rbp-19h]
  __int64 v130; // [rsp+E0h] [rbp-11h]
  __int64 v131; // [rsp+E8h] [rbp-9h]
  __int64 v132; // [rsp+F0h] [rbp-1h]
  struct IUnknown *v134; // [rsp+148h] [rbp+57h] BYREF

  v8 = 0;
  v114 = 0;
  v121 = 0;
  v11 = 0;
  v12 = 0;
  v122 = (CBaseFT *)*((_QWORD *)a2 + 15);
  CBase::CLock::CLock((CBase::CLock *)v126, this);
  v13 = 0;
  v115 = 0;
  v116 = 0;
  if ( (Microsoft_IEEnableBits & 0x40) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, &MSHTML_CMARKUP_SWITCHMARKUP_START, a2, a4);
  if ( (*((_DWORD *)a2 + 187) & 0x8000000) == 0 )
    goto LABEL_9;
  if ( v122 )
    _InterlockedIncrement((volatile signed __int32 *)v122 + 4);
  v14 = this;
  v125 = *((_QWORD *)this + 15);
  v11 = v125;
  *(_BYTE *)(v125 + 224) &= ~0x80u;
  *(_BYTE *)(v11 + 224) |= (_BYTE)a3 << 7;
  v15 = CWindow::Doc((CWindow *)v11);
  if ( !v15 )
  {
    v8 = -2147467259;
LABEL_8:
    v13 = (struct IUnknown *)v115;
LABEL_9:
    v16 = v116;
    goto LABEL_10;
  }
  IsPrimaryWindow = CWindow::IsPrimaryWindow((CWindow *)v11);
  if ( v122 )
  {
    v114 = *(_DWORD *)(*((_QWORD *)v122 + 12) + 496LL);
    CBaseFT::Release(v122);
    v122 = 0;
  }
  if ( !a3 || (v18 = v114, v114 == -2146697203) )
  {
    CWindow::ReleaseViewLinkedWebOC((CWindow *)v11);
    v18 = v114;
  }
  if ( (*((_BYTE *)a2 + 98) & 0x40) != 0 || v18 == -2146697203 || (v18 == -2146697192 || v18 == -2146697195) && !a3 )
  {
    *((_DWORD *)a2 + 188) |= 0x4000u;
    goto LABEL_205;
  }
  if ( v18 == -2146697211
    || v18 == -2146697209
    || v18 == -2147024891
    || v18 == -2147467260
    || (*((_DWORD *)a2 + 188) & 0x200000) != 0 )
  {
    CWindow::ReleaseMarkupPending((CWindow *)v11, a2, 0);
    goto LABEL_205;
  }
  v12 = *(_QWORD *)(v11 + 104);
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)v12 + 984LL) != _vtguard )
    goto LABEL_264;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 1144LL))(*(_QWORD *)(v11 + 104));
  if ( (*((_BYTE *)this + 168) & 8) != 0 )
  {
    LODWORD(v134) = 0;
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)&v134, 0) >= 0
      && !LCIE2IsComponentSharedFlagValueSet((unsigned int)v134, 0x20u) )
    {
      *((_DWORD *)this + 42) &= ~8u;
      LCIE2ChangeComponentSharedFlagBit((unsigned int)v134, 0, 5u);
    }
    v20 = *((_DWORD *)this + 42);
    if ( (v20 & 8) != 0 )
    {
      *((_DWORD *)this + 42) = v20 & 0xFFFFFFF7;
      COmWindowProxy::Fire_onunload(this);
      if ( !CMarkup::Window((CMarkup *)v12) || !*((_QWORD *)a2 + 44) )
        goto LABEL_205;
    }
  }
  v118 = 4;
  v21 = CMarkup::Url(a2);
  v22 = CMarkup::Url((CMarkup *)v12);
  v113 = v21;
  v23 = IsPrimaryWindow;
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "COmWindowProxy::SwitchMarkup - fPrimarySwitch=%d dwTravelLogFlags=0x%08lX pWindowOld=0x%08lX pMarkupOld=0x%08lX OldU"
    "rl=%S pMarkupNew=0x%08lX NewUrl=%S",
    IsPrimaryWindow,
    a4,
    v11,
    v12,
    v22,
    (_DWORD)a2,
    v113);
  if ( (a4 & 1) != 0 )
  {
    v24 = (2 * ((*((_DWORD *)a2 + 188) & 1) == 0)) | 4;
    if ( (a4 & 2) != 0 )
      v24 = 2 * ((*((_DWORD *)a2 + 188) & 1) == 0);
    v25 = v24 | 0x20;
    if ( (*(_BYTE *)(v11 + 226) & 1) == 0 )
      v25 = v24;
    CDoc::UpdateTravelLog(v15, (struct CWindow *)v11, a2, v25);
  }
  if ( !IsPrimaryWindow )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    FrameZone = CMarkup::GetFrameZone((CMarkup *)v12, &pvarg, 1);
    lVal = v118;
    if ( FrameZone >= 0 )
      lVal = pvarg.lVal;
    v118 = lVal;
  }
  CDoc::UpdateInterval(v15, 0);
  v28 = *(_QWORD *)(v12 + 216);
  if ( (*(_BYTE *)(v28 + 8) & 8) != 0 || *((_BYTE *)a2 + 248) )
  {
    v29 = *(const unsigned __int16 **)(v28 + 16);
    if ( v29 )
      CSmartBstr::Set((CSmartBstr *)(*((_QWORD *)a2 + 27) + 16LL), v29);
    *(_DWORD *)(*((_QWORD *)a2 + 27) + 28LL) = *(_DWORD *)(*(_QWORD *)(v12 + 216) + 28LL);
  }
  if ( (unsigned int)CMarkup::HasEditRouter((CMarkup *)v12) )
  {
    EditRouter = CMarkup::GetEditRouter((CMarkup *)v12);
    CEditRouter::Passivate(EditRouter);
  }
  if ( v23 || !CMarkup::GetParentMarkup((CMarkup *)v12) )
  {
    CDoc::NotifySelection(v15, 1, 0);
    CDoc::ReleaseEditor(v15);
    v114 = 0;
    if ( v23 )
    {
      v32 = (struct IUnknown *)*((_QWORD *)v15 + 8);
      if ( v32 )
        CTExec(v32, &CGID_ShellDocView, 0xB3u, 0, 0, 0);
      CView::Unload((struct CDoc *)((char *)v15 + 2264));
      ++*((_DWORD *)v15 + 1390);
    }
  }
  else
  {
    v31 = *(_QWORD *)v12;
    v134 = 0;
    if ( *(__int64 (__fastcall **)())(v31 + 984) != _vtguard )
      _report_securityfailure(1);
    (*(void (__fastcall **)(unsigned __int64, GUID *, struct IUnknown **))(v31 + 1136))(v12, &IID_IUnknown, &v134);
    CDoc::NotifySelection(v15, 15, v134);
    ReleaseInterface(v134);
    v114 = 0;
  }
  if ( *((char *)v15 + 4868) >= 0
    || CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)v15 + 1260)) )
  {
    EnsureIEFrame();
    IEFrameProcAddress = (void (__fastcall *)(__int64))qword_181592878;
    if ( qword_181592878
      || (IEFrameProcAddress = (void (__fastcall *)(__int64))GetIEFrameProcAddress(234),
          (qword_181592878 = (__int64)IEFrameProcAddress) != 0) )
    {
      IEFrameProcAddress(v33);
    }
  }
  if ( v23 )
    CDoc::FlushUndoData(v15);
  CMarkup::ClearUndoData((CMarkup *)v12);
  if ( v23 || CDoc::GetCurrentMarkup(v15) == (struct CMarkup *)v12 )
  {
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_DWORD *)v15 + 1214) ^= (*((_DWORD *)v15 + 1214) ^ ((unsigned int)IsInIEBrowser(v15) << 28)) & 0x10000000;
    if ( (byte_18158CB79 & 2) == 0 || (*((_DWORD *)v15 + 1219) & 0x2000000) == 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 3536));
      TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v15 + 4728);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 3536));
    }
  }
  CInputManager::ClearCachedNodesOnSwitchMarkup((struct CTreeNode **)v15 + 135, (struct CMarkup *)v12);
  v35 = CMarkup::Root((CMarkup *)v12);
  LookasidePtr2 = (struct CElement *)CElement::GetLookasidePtr2(v35, 0);
  v37 = LookasidePtr2;
  if ( LookasidePtr2 )
  {
    FrameContentData = GetFrameContentData(LookasidePtr2);
    if ( FrameContentData )
    {
      v114 = CMarkup::EnforceRestrictionsFromFrameData(a2, FrameContentData);
      v8 = v114;
      if ( v114 )
        goto LABEL_8;
      v39 = a5;
      goto LABEL_87;
    }
    v39 = a5;
  }
  else
  {
    v39 = a5;
    if ( (*(_DWORD *)(v12 + 756) & 0x100) != 0 && a5 )
    {
      LODWORD(v134) = 0;
      CMarkup::GetSandboxFlags((CMarkup *)v12, (struct SandboxFlags *)&v134);
      v114 = CMarkup::EnforceSandbox(a2, (const struct SandboxFlags *)&v134);
      v8 = v114;
      if ( v114 )
        goto LABEL_8;
LABEL_87:
      v14 = this;
    }
  }
  v40 = *((_DWORD *)v14 + 42)
      ^ ((unsigned __int16)*((_DWORD *)v14 + 42)
       ^ (unsigned __int16)((unsigned __int8)BYTE1(*((_DWORD *)a2 + 189)) << 12))
      & 0x1000;
  *((_DWORD *)v14 + 42) = v40;
  *((_DWORD *)v14 + 42) = v40 & 0xFFFFDFFF | ((*((_DWORD *)a2 + 189) & 0x500) != 256 ? 0x2000 : 0);
  if ( v37 )
  {
    CElement::CLock::CLock(&pvarg, v37, 0);
    v41 = CMarkup::Root(a2);
    v114 = CElement::SetViewSubordinate(v37, v41);
    v8 = v114;
    if ( v114 )
    {
      CElement::CLock::~CLock((CElement::CLock *)&pvarg);
      goto LABEL_8;
    }
    CElement::CLock::~CLock((CElement::CLock *)&pvarg);
    v14 = this;
  }
  ActiveElement = CDoc::GetActiveElement(v15);
  IsConnectedToThisMarkup = CElement::IsConnectedToThisMarkup(ActiveElement, (struct CMarkup *)v12);
  if ( IsConnectedToThisMarkup )
  {
    *((_QWORD *)v15 + 112) = 0;
    v43 = CMarkup::Root((CMarkup *)v12);
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_QWORD *)v15 + 113) = v43;
  }
  *((_DWORD *)v14 + 42) &= ~0x20u;
  v44 = CMarkup::AccessAllowed(a2, (struct CMarkup *const)v12);
  v45 = *((_BYTE *)a2 + 136) >= 0;
  v119 = v44;
  if ( v45 )
  {
    if ( v44 )
      goto LABEL_113;
LABEL_104:
    if ( IsPrimaryWindow
      && (*((_DWORD *)v15 + 1215) & 0x8000000) != 0
      && (*((_DWORD *)v15 + 1216) & 0x800) != 0
      && (*((_BYTE *)a2 + 752) & *(_BYTE *)(v12 + 752) & 0x40) != 0 )
    {
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)v12 + 984LL) != _vtguard )
        goto LABEL_264;
      if ( !(*(unsigned int (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 1080LL))(v12) )
        goto LABEL_112;
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)v12 + 984LL) != _vtguard )
        goto LABEL_264;
      if ( !*(_QWORD *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 1088LL))(v12) )
LABEL_112:
        v119 = 1;
    }
    goto LABEL_113;
  }
  if ( !v44 )
    goto LABEL_104;
  v46 = CMarkup::GetDwnPost(a2) != 0;
  Url = CMarkup::GetUrl(a2);
  v48 = CMarkup::GetUrl((const struct CMarkup *const)v12);
  if ( (unsigned int)CDoc::IsSameUrl(v48, &LocaleName, Url, &LocaleName, v46) )
  {
    v39 = 1;
LABEL_113:
    a5 = v39;
    goto LABEL_115;
  }
  v39 = a5;
LABEL_115:
  if ( (*(_DWORD *)(v12 + 748) & 0x8000) != 0 )
    *((_DWORD *)a2 + 187) |= 0x8000u;
  if ( (unsigned int)CMarkup::IsOrphanedMarkup((CMarkup *)v12) )
  {
    CMarkup::SetOrphanedMarkup(a2, 1);
    LookasidePtr = CMarkup::GetLookasidePtr(a2, 6);
    LookasidePtr[20] = LookasidePtr[20] & 0xFE | CMarkup::IsRevivedOrphanedMarkup((CMarkup *)v12);
  }
  if ( !a7 && (*(int *)(v12 + 848) >= 90000 || !(unsigned int)CMarkup::AccessAllowed((CMarkup *)v12, a2)) )
    *(_BYTE *)(v12 + 97) |= 0x40u;
  if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
  {
    v50 = *(CSecurityContext **)(v12 + 320);
    v51 = CMarkup::GetUrl((const struct CMarkup *const)v12);
    CSecurityContext::SetOriginalURL(v50, v51);
  }
  if ( *((_BYTE *)a2 + 876) && *((int *)a2 + 212) >= 90000 )
  {
    v52 = v39 != 0;
    ScriptCollection = CMarkup::GetScriptCollection((CMarkup *)v12, 1);
    if ( ScriptCollection
      && *((_QWORD *)ScriptCollection + 8)
      && (JScript9Holder = CScriptCollection::GetJScript9Holder(ScriptCollection)) != 0
      && (*((_BYTE *)JScript9Holder + 412) = 0,
          *((_BYTE *)JScript9Holder + 413) = v39 == 0,
          (v55 = *((_QWORD *)a2 + 15)) != 0) )
    {
      v56 = *(_QWORD *)(v55 + 96);
      LOBYTE(v134) = 1;
      if ( (*(_BYTE *)(v56 + 384) & 1) != 0 )
        *((_BYTE *)JScript9Holder + 414) = 0;
    }
    else
    {
      LOBYTE(v134) = 1;
    }
  }
  else
  {
    LOBYTE(v134) = 0;
    v52 = 0;
  }
  IsPrimaryMarkup = CMarkup::IsPrimaryMarkup((CMarkup *)v12);
  CMarkup::TearDownMarkup((CMarkup *)v12, 1, 1);
  if ( IsPrimaryMarkup )
    CDoc::EraseFrontBufferIfNeeeded(v15);
  v45 = IsPrimaryWindow == 0;
  *(_DWORD *)(*(_QWORD *)(v12 + 320) + 12LL) = 0;
  if ( !v45 )
  {
    if ( (*((_BYTE *)a2 + 760) & 4) != 0 )
    {
      *((_BYTE *)v15 + 937) = 0;
      *((_QWORD *)v15 + 119) = 0;
      SysFreeString(*((BSTR *)v15 + 118));
      *((_QWORD *)v15 + 118) = 0;
    }
    v58 = *((_QWORD *)v15 + 12);
    if ( v58 )
    {
      v59 = *(HWND *)(v58 + 168);
      if ( v59 )
        ValidateRect(v59, 0);
    }
  }
  if ( !CMarkup::Window((CMarkup *)v12) || !*((_QWORD *)a2 + 44) )
    goto LABEL_205;
  v120 = 0;
  if ( IsConnectedToThisMarkup )
  {
    *((_QWORD *)v15 + 112) = 0;
    v60 = CMarkup::Root(a2);
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_QWORD *)v15 + 113) = v60;
  }
  v61 = *(CDocument **)(*((_QWORD *)this + 15) + 120LL);
  AAdesignMode = CDocument::GetAAdesignMode(v61);
  if ( (*((_BYTE *)a2 + 752) & 1) != 0 && (*((_DWORD *)v15 + 1216) & 0x800) != 0 )
  {
    v63 = *((_QWORD *)v61 + 3);
    if ( v63 )
    {
      v64 = *(_DWORD *)(v63 + 4);
      if ( v64 > 0 )
      {
        v65 = 0;
        while ( *(_BYTE *)(*(_QWORD *)(v63 + 8) + 24 * v65) != 1 )
        {
          v65 = (unsigned int)(v65 + 1);
          if ( (int)v65 >= v64 )
            goto LABEL_157;
        }
        CDocument::GetXMLExpando(v61, &v115, (struct IDispatch **)&v116);
      }
    }
  }
LABEL_157:
  CMarkup::ClearWindow((CMarkup *)v12, a6);
  *((_DWORD *)v15 + 1218) &= ~1u;
  if ( (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)v12) )
    GWKillMethodCall(v15, CDoc::CallOnFirePrivacIEEvent, 0);
  Gwnd = (unsigned int)GetGwnd();
  GWKillMethodCallEx(Gwnd, (_DWORD)v15, (unsigned int)CDoc::OnPrerenderEnabled, 0, 0);
  v67 = IsPrimaryWindow;
  *((_DWORD *)a2 + 187) = *((_DWORD *)a2 + 187) & 0xF3FFFFFF | 0x4000000;
  if ( v67 )
    *((_DWORD *)v15 + 1217) &= ~0x20000000u;
  if ( !CMarkup::Window(a2) )
    *((_DWORD *)a2 + 187) &= ~0x4000000u;
  if ( !v68 || (*((_DWORD *)a2 + 34) & 0x504LL) == 0 )
  {
    CDocument::SetAAdesignMode(*(CDocument **)(*((_QWORD *)this + 15) + 120LL), AAdesignMode);
    v69 = *(_DWORD *)(v12 + 752);
    v70 = *((_DWORD *)a2 + 188);
    if ( ((v70 ^ *(_BYTE *)(v12 + 752)) & 0x80u) != 0 || (((unsigned __int8)v70 ^ (unsigned __int8)v69) & 0x40) != 0 )
      v120 = 1;
    v71 = v70 ^ ((unsigned __int8)v70 ^ (unsigned __int8)v69) & 0x80;
    *((_DWORD *)a2 + 188) = v71;
    *((_DWORD *)a2 + 188) = v71 ^ (*(_DWORD *)(v12 + 752) ^ v71) & 0x40;
  }
  v72 = this;
  *(_QWORD *)(v11 + 104) = a2;
  *((_DWORD *)a2 + 4) += 8;
  COmWindowProxy::OnSetWindow(this);
  CMarkup::UpdateSecurityID(a2);
  if ( (*((_BYTE *)a2 + 136) & 0x20) != 0 )
  {
    v73 = *(_QWORD *)(*((_QWORD *)this + 15) + 136LL);
    if ( v73 )
    {
      COmWindowProxy::GetScriptMarkupContext(this);
      v74 = CMarkup::GetUrl(a2);
      if ( CMarkup::ShouldSourceInheritParentDomain(v75, v74) )
      {
        v76 = *(_QWORD *)(v73 + 128);
        if ( v76 )
          *((_DWORD *)this + 42) ^= (*(_DWORD *)(v76 + 168) ^ *((_DWORD *)this + 42)) & 1;
      }
    }
  }
  v77 = *(_QWORD *)(v12 + 328);
  if ( v77 )
  {
    v78 = *(_QWORD *)(v77 + 8);
    for ( i = *(_DWORD *)(v77 + 4); i; --i )
    {
      v80 = *(_QWORD *)(v78 + 16);
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 88LL))(v80);
      v78 += 96;
    }
    v72 = this;
  }
  v81 = *(_QWORD *)(v11 + 616);
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    *(_QWORD *)(v11 + 616) = 0;
  }
  *(_BYTE *)(v11 + 488) = 0;
  VariantClear((VARIANTARG *)(v11 + 464));
  if ( !a5 )
  {
    CDocument::ResetSecurityThunk(*(CDocument **)(*((_QWORD *)v72 + 15) + 120LL));
    v82 = (void **)((char *)v72 + 152);
    if ( !v119 )
      ResetSecurityThunkHelper(v82);
    v83 = (_QWORD *)*((_QWORD *)v72 + 20);
    if ( v83 )
    {
      *v82 = v83;
      *((_QWORD *)v72 + 20) = 0;
      *(_DWORD *)(v83[5] + 20LL) = 3;
    }
  }
  v84 = *(_QWORD *)(v11 + 112);
  if ( v84 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v84 + 984LL) != _vtguard )
      goto LABEL_264;
    (*(void (**)(void))(*(_QWORD *)v84 + 1152LL))();
    *(_QWORD *)(v11 + 112) = 0;
  }
  v85 = 16;
  if ( (_BYTE)v134 )
  {
    CAryWindowTbl::SafeIterateProxies(
      *(CAryWindowTbl **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 472LL),
      (struct CWindow *)v11,
      (int (*)(struct CWindow *, struct COmWindowProxy *))CAryWindowTbl::ReinitializeProxyVarIterationHandler);
    if ( v52 )
    {
      v86 = *((_QWORD *)v72 + 15);
      v134 = 0;
      v87 = *(struct CBase **)(v86 + 120);
      CJScript9Holder::ReinitializeOrClearObject(v87, a2, 0);
      v88 = *(_QWORD *)(v11 + 104);
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)v88 + 984LL) != _vtguard )
        goto LABEL_264;
      v89 = (*(__int64 (**)(void))(*(_QWORD *)v88 + 1192LL))();
      v90 = (struct CJScript9Holder *)v89;
      if ( v89 )
      {
        v85 = *(_QWORD *)(v89 + 392);
        if ( v85 )
        {
          v85 = *(_QWORD *)(v85 + 40) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v85 )
          {
            v91 = CJScript9Holder::ExtensionRefFromVar((void *)v85);
            v114 = CJScript9Holder::CBaseToVar(v87, v90, (void **)&v134);
            if ( v114 >= 0 )
            {
              v85 = (__int64)v134;
              v91[5] = v134;
            }
            v11 = v125;
          }
        }
      }
    }
  }
  if ( FeatureControlHelper::PublicObjectCaching((FeatureControlHelper *)v85) )
    CWindow::InvalidateReusedObjects((CWindow *)v11);
  CDocument::InvalidateReusedObjects(*(CDocument **)(*((_QWORD *)this + 15) + 120LL));
  *(_BYTE *)(v11 + 225) &= ~0x20u;
  if ( !IsPrimaryWindow )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (int)CMarkup::GetFrameZone(a2, &pvarg, 1) < 0 || v118 < pvarg.lVal )
    {
      v104 = CDoc::PrimaryMarkup(v15);
      if ( v104 )
        *((_DWORD *)v104 + 197) = 0;
    }
LABEL_228:
    v105 = (int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)v15 + 8);
    v134 = 0;
    if ( v105 && (**v105)(v105, &IID_IDocHostUIHandlerPriv, &v134) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *, _QWORD))v134->lpVtbl[1].QueryInterface)(v134, 0);
      ((void (__fastcall *)(struct IUnknown *))v134->lpVtbl->Release)(v134);
    }
    goto LABEL_231;
  }
  if ( (*((_BYTE *)v15 + 16) & 2) != 0 )
  {
    v114 = -2147467259;
LABEL_205:
    v8 = v114;
    goto LABEL_8;
  }
  v92 = 0;
  v93 = (struct CDoc *)((char *)v15 + 4480);
  v94 = 4;
  do
  {
    CStr::_Free(v93);
    *(_QWORD *)v93 = 0;
    v93 = (CStr *)((char *)v93 + 8);
    --v94;
  }
  while ( v94 );
  if ( *((char *)a2 + 756) >= 0 )
  {
    *((_DWORD *)v15 + 1214) &= ~0x4000000u;
    CStr::_Free((struct CDoc *)((char *)v15 + 4520));
    *((_QWORD *)v15 + 565) = 0;
    CStr::_Free((struct CDoc *)((char *)v15 + 4512));
    *((_QWORD *)v15 + 564) = 0;
  }
  *((_DWORD *)v15 + 1216) &= ~0x400000u;
  *((_DWORD *)v15 + 1118) = 4;
  CDoc::UpdateStatusText(v15);
  *((_DWORD *)v15 + 1214) |= 0x20u;
  CDoc::SetUpdateTimer(v15);
  CDoc::DeferUpdateTitle(v15);
  CDoc::Invalidate(v15, 0, 0, 4u);
  *((_DWORD *)v15 + 1245) = 0;
  *((_DWORD *)v15 + 1243) = 0;
  v95 = CDoc::PrimaryMarkup(v15);
  v98 = v95;
  if ( v95 )
    IsPageActionAllowed = CDoc::IsPageActionAllowed(v97, v95, 0x80000u);
  v45 = IsPageActionAllowed == 0;
  v99 = *((_QWORD *)v98 + 40);
  if ( v45 )
  {
    CDoc::SetRootSslState(v15, v99, 0, *((unsigned int *)v15 + 1104), *((_DWORD *)v15 + 1105), 1);
  }
  else
  {
    CDoc::SetRootSslState(v15, v99, 0, 0, 0, 1);
    if ( IsDualEngineProcess() )
    {
      v100 = (struct IUnknown *)*((_QWORD *)v15 + 8);
      if ( v100 )
        CTExec(v100, &CGID_Explorer, 0x87u, 0, 0, 0);
    }
  }
  CDoc::SwitchPageActionBlockedState(v15);
  *((_DWORD *)v15 + 1228) = GetTickCount();
  CDoc::SetIgnoreRootSslErrors(v15, 1, 0);
  *((_DWORD *)v15 + 1107) ^= v102 & (*((_DWORD *)v15 + 1107) ^ v101);
  CDoc::SwitchWPCBlockedUrlList(v15);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 739) + 16LL))(*((_QWORD *)v15 + 739));
  *((_QWORD *)v15 + 739) = *((_QWORD *)v15 + 740);
  *((_QWORD *)v15 + 740) = 0;
  CreatePrivacIEContentLog();
  CMultimediaLog::Reset((struct CDoc *)((char *)v15 + 5928));
  if ( *((_QWORD *)v15 + 8) )
  {
    CDoc::UpdateDocHostUI(v15, 1);
    v103 = (int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)v15 + 8);
    v134 = 0;
    if ( (**v103)(v103, &IID_IDocHostUIHandlerPriv, &v134) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *, __int64))v134->lpVtbl[1].QueryInterface)(v134, 1);
      v92 = 1;
      ((void (__fastcall *)(struct IUnknown *))v134->lpVtbl->Release)(v134);
    }
  }
  if ( !a5 )
    CDoc::ResetEventBits(v15);
  *((_BYTE *)CDoc::EventMgr(v15) + 100) = 1;
  CTridentMediaConsentMgr::Cleanup((struct CDoc *)((char *)v15 + 5368));
  CDoc::AttemptRestoreHardwareDevice(v15);
  if ( !v92 )
    goto LABEL_228;
LABEL_231:
  CMarkup::InitWindow(a2);
  v106 = *((_DWORD *)a2 + 189);
  if ( (v106 & 0x1000000) != 0 )
  {
    *((_DWORD *)a2 + 189) = v106 & 0xFEFFFFFF;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)a2 + 984LL) != _vtguard )
      _report_securityfailure(1);
    v107 = *(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)a2 + 1144LL);
    v121 = 1;
    v107(a2);
    v128 = 0;
    v130 = 0;
    v131 = 0;
    v132 = 0;
    v129 = 0;
    v108 = CMarkup::Root(a2);
    CNotification::Initialize(v127, 96, v108, 0, 0, 0);
    CMarkup::Notify(a2, (struct CNotification *)v127, 0);
    if ( !CMarkup::Window(a2) )
      goto LABEL_205;
  }
  *(_BYTE *)(v11 + 223) |= 1u;
  if ( v120 )
    CMarkup::EnsureFormatCacheChange(a2, 0x20080u);
  if ( (unsigned int)CMarkup::HasIdentityPeerTask(a2) )
    CMarkup::ProcessIdentityPeerTask(v109);
  v16 = v116;
  if ( v115 || v116 )
    CDocument::SetXMLExpando(*(CDocument **)(*((_QWORD *)this + 15) + 120LL), v115, (struct IDispatch *)v116);
  FormsHideTooltip(1, v12);
  if ( IsPrimaryWindow )
  {
    v110 = (CZoomState *)*((_QWORD *)v15 + 649);
    CSmoothScroller::s_cSlowScrolls = 0;
    if ( v110 )
      CZoomState::ClearTransientZoomState(v110);
    *((_DWORD *)v15 + 963) = 1065353216;
    CUnitInfo::UpdateTotalOpticalZoom((struct CDoc *)((char *)v15 + 3632));
    if ( LCIE_IsCurrentTabThreadEmptyTab() )
    {
      if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
        McTemplateU0ppq_EventWriteTransfer(
          (unsigned int)&BERP_IE_Context,
          (unsigned int)&MSHTML_CDOC_HOSTPAINTUPDATENOTIFICATION_IGNOREDREQUEST_INFO,
          (_DWORD)v15,
          (_DWORD)a2,
          11);
    }
    else if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
    {
      McTemplateU0ppq_EventWriteTransfer(
        (unsigned int)&BERP_IE_Context,
        (unsigned int)&MSHTML_CDOC_HOSTPAINTUPDATENOTIFICATION_IGNOREDREQUEST_INFO,
        (_DWORD)v15,
        (_DWORD)a2,
        7);
    }
    CDoc::ClearAtViewportCache(v15);
    v111 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL)
                    + 248LL)
        && CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)v15
                                                                                               + 1260))
        && *((_QWORD *)v15 + 287);
    *((_BYTE *)v15 + 2304) = v111;
    CDoc::UpdateUnitInfo(v15, 0);
    CFlipAheadManager::Reset((struct CDoc *)((char *)v15 + 6688));
    v112 = (CTask *)*((_QWORD *)v15 + 853);
    if ( v112 )
      CTask::SetBlocked(v112, 1);
    if ( *((char *)v15 + 4868) >= 0 )
      CDoc::ForceKeyboardDismiss(v15);
    CDoc::SignalDocumentUriChanged(v15);
    if ( CDoc::HasFocus(v15) )
      CMarkup::FireFocusTelemetry(a2, 1);
  }
  v8 = v114;
  v13 = (struct IUnknown *)v115;
LABEL_10:
  if ( v122 )
    CBaseFT::Release(v122);
  if ( v11 )
    *(_BYTE *)(v11 + 224) &= ~0x80u;
  ReleaseInterface(v13);
  ReleaseInterface(v16);
  if ( v12 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v12 + 984LL) != _vtguard )
      goto LABEL_264;
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 1152LL))(v12);
  }
  CMarkup::UnblockScriptExecutionHelper(a2);
  if ( !v121 )
    goto LABEL_20;
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)a2 + 984LL) != _vtguard )
LABEL_264:
    _report_securityfailure(1);
  (*(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)a2 + 1152LL))(a2);
LABEL_20:
  if ( (Microsoft_IEEnableBits & 0x40) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, &MSHTML_CMARKUP_SWITCHMARKUP_STOP, a2, v8);
  CBase::CLock::~CLock((CBase::CLock *)v126);
  return v8;
}

```

## disassembly

```asm
0x1804925d0  mov     [rsp-8+arg_10], rbx
0x1804925d5  mov     [rsp-8+arg_0], rcx
0x1804925da  push    rbp
0x1804925db  push    rsi
0x1804925dc  push    rdi
0x1804925dd  push    r12
0x1804925df  push    r13
0x1804925e1  push    r14
0x1804925e3  push    r15
0x1804925e5  lea     rbp, [rsp-0Fh]
0x1804925ea  sub     rsp, 100h
0x1804925f1  mov     r14, rdx
0x1804925f4  xor     r12d, r12d
0x1804925f7  mov     rdx, rcx; struct CBase *
0x1804925fa  mov     [rsp+130h+var_F0], r12d
0x1804925ff  mov     edi, r9d
0x180492602  mov     [rsp+130h+var_C8], r12d
0x180492607  mov     ebx, r8d
0x18049260a  xor     r13d, r13d
0x18049260d  mov     rcx, [r14+78h]
0x180492611  xor     r15d, r15d
0x180492614  mov     [rsp+130h+var_C0], rcx
0x180492619  lea     rcx, [rbp+3Fh+var_90]; this
0x18049261d  call    ??0CLock@CBase@@QEAA@PEAV1@@Z; CBase::CLock::CLock(CBase *)
0x180492622  xor     esi, esi
0x180492624  test    byte ptr cs:Microsoft_IEEnableBits, 40h
0x18049262b  mov     [rsp+130h+var_E8], rsi
0x180492630  mov     [rsp+130h+var_E0], rsi
0x180492635  jz      short loc_180492650
0x180492637  mov     r9d, edi
0x18049263a  lea     rdx, MSHTML_CMARKUP_SWITCHMARKUP_START
0x180492641  mov     r8, r14
0x180492644  lea     rcx, BERP_IE_Context
0x18049264b  call    McTemplateU0pq_EventWriteTransfer
0x180492650  test    dword ptr [r14+2ECh], 8000000h
0x18049265b  jz      short loc_1804926AB
0x18049265d  mov     rax, [rsp+130h+var_C0]
0x180492662  test    rax, rax
0x180492665  jz      short loc_18049266B
0x180492667  lock inc dword ptr [rax+10h]
0x18049266b  mov     r12, [rbp+3Fh+arg_0]
0x18049266f  mov     al, bl
0x180492671  shl     al, 7
0x180492674  mov     r13, [r12+78h]
0x180492679  mov     rcx, r13; this
0x18049267c  mov     [rbp+3Fh+var_98], r13
0x180492680  and     byte ptr [r13+0E0h], 7Fh
0x180492688  or      [r13+0E0h], al
0x18049268f  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180492694  mov     rsi, rax
0x180492697  test    rax, rax
0x18049269a  jnz     loc_180492781
0x1804926a0  mov     r12d, 80004005h
0x1804926a6  mov     rsi, [rsp+130h+var_E8]
0x1804926ab  mov     rbx, [rsp+130h+var_E0]
0x1804926b0  mov     rax, [rsp+130h+var_C0]
0x1804926b5  test    rax, rax
0x1804926b8  jz      short loc_1804926C2
0x1804926ba  mov     rcx, rax; this
0x1804926bd  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x1804926c2  test    r13, r13
0x1804926c5  jz      short loc_1804926CF
0x1804926c7  and     byte ptr [r13+0E0h], 7Fh
0x1804926cf  mov     rcx, rsi; struct IUnknown *
0x1804926d2  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1804926d7  mov     rcx, rbx; struct IUnknown *
0x1804926da  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1804926df  lea     rbx, __vtguard
0x1804926e6  test    r15, r15
0x1804926e9  jz      short loc_18049270A
0x1804926eb  mov     rax, [r15]
0x1804926ee  cmp     [rax+3D8h], rbx
0x1804926f5  jnz     loc_180493A0B
0x1804926fb  mov     rax, [rax+480h]
0x180492702  mov     rcx, r15
0x180492705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18049270a  mov     rcx, r14; this
0x18049270d  call    ?UnblockScriptExecutionHelper@CMarkup@@QEAAJXZ; CMarkup::UnblockScriptExecutionHelper(void)
0x180492712  cmp     [rsp+130h+var_C8], 0
0x180492717  jz      short loc_180492738
0x180492719  mov     rax, [r14]
0x18049271c  cmp     [rax+3D8h], rbx
0x180492723  jnz     loc_180493A0B
0x180492729  mov     rax, [rax+480h]
0x180492730  mov     rcx, r14
0x180492733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180492738  test    byte ptr cs:Microsoft_IEEnableBits, 40h
0x18049273f  jz      short loc_18049275A
0x180492741  mov     r9d, r12d
0x180492744  lea     rdx, MSHTML_CMARKUP_SWITCHMARKUP_STOP
0x18049274b  mov     r8, r14
0x18049274e  lea     rcx, BERP_IE_Context
0x180492755  call    McTemplateU0pq_EventWriteTransfer
0x18049275a  lea     rcx, [rbp+3Fh+var_90]; this
0x18049275e  call    ??1CLock@CBase@@QEAA@XZ; CBase::CLock::~CLock(void)
0x180492763  mov     rbx, [rsp+130h+arg_10]
0x18049276b  mov     eax, r12d
0x18049276e  add     rsp, 100h
0x180492775  pop     r15
0x180492777  pop     r14
0x180492779  pop     r13
0x18049277b  pop     r12
0x18049277d  pop     rdi
0x18049277e  pop     rsi
0x18049277f  pop     rbp
0x180492780  retn
0x180492781  mov     rcx, r13; this
0x180492784  call    ?IsPrimaryWindow@CWindow@@QEAAHXZ; CWindow::IsPrimaryWindow(void)
0x180492789  mov     rcx, [rsp+130h+var_C0]; this
0x18049278e  mov     [rsp+130h+var_D8], eax
0x180492792  test    rcx, rcx
0x180492795  jz      short loc_1804927B1
0x180492797  mov     rax, [rcx+60h]
0x18049279b  mov     eax, [rax+1F0h]
0x1804927a1  mov     [rsp+130h+var_F0], eax
0x1804927a5  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x1804927aa  xor     ecx, ecx
0x1804927ac  mov     [rsp+130h+var_C0], rcx
0x1804927b1  test    ebx, ebx
0x1804927b3  jz      short loc_1804927C0
0x1804927b5  mov     eax, [rsp+130h+var_F0]
0x1804927b9  cmp     eax, 800C000Dh
0x1804927be  jnz     short loc_1804927CC
0x1804927c0  mov     rcx, r13; this
0x1804927c3  call    ?ReleaseViewLinkedWebOC@CWindow@@QEAAXXZ; CWindow::ReleaseViewLinkedWebOC(void)
0x1804927c8  mov     eax, [rsp+130h+var_F0]
0x1804927cc  test    byte ptr [r14+62h], 40h
0x1804927d1  jnz     loc_1804939F2
0x1804927d7  cmp     eax, 800C000Dh
0x1804927dc  jz      loc_1804939F2
0x1804927e2  cmp     eax, 800C0018h
0x1804927e7  jz      short loc_1804927F0
0x1804927e9  cmp     eax, 800C0015h
0x1804927ee  jnz     short loc_1804927F8
0x1804927f0  test    ebx, ebx
0x1804927f2  jz      loc_1804939F2
0x1804927f8  cmp     eax, 800C0005h
0x1804927fd  jz      loc_1804939DF
0x180492803  cmp     eax, 800C0007h
0x180492808  jz      loc_1804939DF
0x18049280e  cmp     eax, 80070005h
0x180492813  jz      loc_1804939DF
0x180492819  cmp     eax, 80004004h
0x18049281e  jz      loc_1804939DF
0x180492824  test    dword ptr [r14+2F0h], 200000h
0x18049282f  jnz     loc_1804939DF
0x180492835  mov     r15, [r13+68h]
0x180492839  lea     rcx, __vtguard
0x180492840  mov     rax, [r15]
0x180492843  cmp     [rax+3D8h], rcx
0x18049284a  jnz     loc_180493A0B
0x180492850  mov     rax, [rax+478h]
0x180492857  mov     rcx, r15
0x18049285a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18049285f  test    byte ptr [r12+0A8h], 8
0x180492868  jz      loc_1804928FE
0x18049286e  mov     dword ptr [rbp+3Fh+arg_8], 0
0x180492875  call    cs:__imp_GetCurrentThreadId
0x18049287b  xor     r9d, r9d
0x18049287e  lea     r8, [rbp+3Fh+arg_8]
0x180492882  mov     edx, eax
0x180492884  mov     ecx, 203h
0x180492889  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18049288f  mov     ebx, 0FFFFFFF7h
0x180492894  test    eax, eax
0x180492896  js      short loc_1804928C1
0x180492898  mov     ecx, dword ptr [rbp+3Fh+arg_8]
0x18049289b  mov     edx, 20h ; ' '
0x1804928a0  call    cs:__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z; LCIE2IsComponentSharedFlagValueSet(ulong,ulong)
0x1804928a6  test    eax, eax
0x1804928a8  jnz     short loc_1804928C1
0x1804928aa  and     [r12+0A8h], ebx
0x1804928b2  lea     r8d, [rax+5]
0x1804928b6  mov     ecx, dword ptr [rbp+3Fh+arg_8]
0x1804928b9  xor     edx, edx
0x1804928bb  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z; LCIE2ChangeComponentSharedFlagBit(ulong,bool,ulong)
0x1804928c1  mov     eax, [r12+0A8h]
0x1804928c9  test    al, 8
0x1804928cb  jz      short loc_1804928FE
0x1804928cd  and     eax, ebx
0x1804928cf  mov     rcx, r12; this
0x1804928d2  mov     [r12+0A8h], eax
0x1804928da  call    ?Fire_onunload@COmWindowProxy@@QEAAXXZ; COmWindowProxy::Fire_onunload(void)
0x1804928df  mov     rcx, r15; this
0x1804928e2  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1804928e7  test    rax, rax
0x1804928ea  jz      loc_18049346E
0x1804928f0  cmp     qword ptr [r14+160h], 0
0x1804928f8  jz      loc_18049346E
0x1804928fe  mov     rcx, r14; this
0x180492901  mov     [rsp+130h+var_D4], 4
0x180492909  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x18049290e  mov     rcx, r15; this
0x180492911  mov     rbx, rax
0x180492914  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x180492919  mov     [rsp+130h+var_F8], rbx
0x18049291e  lea     rcx, aComwindowproxy; "COmWindowProxy::SwitchMarkup - fPrimary"...
0x180492925  mov     ebx, [rsp+130h+var_D8]
0x180492929  mov     r9, r13
0x18049292c  mov     [rsp+130h+var_100], r14
0x180492931  mov     edx, ebx
0x180492933  mov     [rsp+130h+var_108], rax
0x180492938  mov     r8d, edi
0x18049293b  mov     [rsp+130h+var_110], r15
0x180492940  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x180492945  test    dil, 1
0x180492949  jz      short loc_18049298C
0x18049294b  mov     eax, [r14+2F0h]
0x180492952  mov     r8, r14; struct CMarkup *
0x180492955  not     eax
0x180492957  mov     rdx, r13; struct CWindow *
0x18049295a  and     eax, 1
0x18049295d  add     eax, eax
0x18049295f  mov     ecx, eax
0x180492961  or      ecx, 4
0x180492964  test    dil, 2
0x180492968  mov     edi, 1
0x18049296d  cmovnz  ecx, eax
0x180492970  mov     r9d, ecx
0x180492973  or      r9d, 20h
0x180492977  test    [r13+0E2h], dil
0x18049297e  cmovz   r9d, ecx; unsigned int
0x180492982  mov     rcx, rsi; this
0x180492985  call    ?UpdateTravelLog@CDoc@@QEAAXPEAVCWindow@@PEAVCMarkup@@K@Z; CDoc::UpdateTravelLog(CWindow *,CMarkup *,ulong)
0x18049298a  jmp     short loc_180492991
0x18049298c  mov     edi, 1
0x180492991  test    ebx, ebx
0x180492993  jnz     short loc_1804929C9
0x180492995  xorps   xmm0, xmm0
0x180492998  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18049299c  xor     eax, eax
0x18049299e  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x1804929a2  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x1804929a6  call    cs:__imp_VariantInit
0x1804929ac  mov     r8d, edi; int
0x1804929af  lea     rdx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x1804929b3  mov     rcx, r15; this
0x1804929b6  call    ?GetFrameZone@CMarkup@@QEAAJPEAUtagVARIANT@@H@Z; CMarkup::GetFrameZone(tagVARIANT *,int)
0x1804929bb  mov     ecx, [rsp+130h+var_D4]
0x1804929bf  test    eax, eax
0x1804929c1  cmovns  ecx, dword ptr [rbp+3Fh+pvarg+8]
0x1804929c5  mov     [rsp+130h+var_D4], ecx
0x1804929c9  xor     edx, edx; int
0x1804929cb  mov     rcx, rsi; this
0x1804929ce  call    ?UpdateInterval@CDoc@@QEAAXJ@Z; CDoc::UpdateInterval(long)
0x1804929d3  mov     rdx, [r15+0D8h]
0x1804929da  test    byte ptr [rdx+8], 8
0x1804929de  jnz     short loc_1804929EA
0x1804929e0  cmp     byte ptr [r14+0F8h], 0
0x1804929e8  jz      short loc_180492A17
0x1804929ea  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1804929ee  test    rdx, rdx
0x1804929f1  jz      short loc_180492A03
0x1804929f3  mov     rcx, [r14+0D8h]
0x1804929fa  add     rcx, 10h; this
0x1804929fe  call    ?Set@CSmartBstr@@QEAAJPEBG@Z; CSmartBstr::Set(ushort const *)
0x180492a03  mov     rax, [r15+0D8h]
0x180492a0a  mov     rcx, [r14+0D8h]
0x180492a11  mov     eax, [rax+1Ch]
0x180492a14  mov     [rcx+1Ch], eax
0x180492a17  mov     rcx, r15; this
0x180492a1a  call    ?HasEditRouter@CMarkup@@QEAAHXZ; CMarkup::HasEditRouter(void)
0x180492a1f  test    eax, eax
0x180492a21  jz      short loc_180492A33
0x180492a23  mov     rcx, r15; this
0x180492a26  call    ?GetEditRouter@CMarkup@@QEAAPEAVCEditRouter@@XZ; CMarkup::GetEditRouter(void)
0x180492a2b  mov     rcx, rax; this
0x180492a2e  call    ?Passivate@CEditRouter@@QEAAXXZ; CEditRouter::Passivate(void)
0x180492a33  test    ebx, ebx
0x180492a35  jnz     short loc_180492AA9
0x180492a37  mov     rcx, r15; this
0x180492a3a  call    ?GetParentMarkup@CMarkup@@QEBAPEAV1@XZ; CMarkup::GetParentMarkup(void)
0x180492a3f  test    rax, rax
0x180492a42  jz      short loc_180492AA9
0x180492a44  mov     rax, [r15]
0x180492a47  lea     rcx, __vtguard
0x180492a4e  mov     [rbp+3Fh+arg_8], 0
0x180492a56  cmp     [rax+3D8h], rcx
0x180492a5d  jnz     loc_180493A16
0x180492a63  mov     rax, [rax+470h]
0x180492a6a  lea     r8, [rbp+3Fh+arg_8]
0x180492a6e  lea     rdx, IID_IUnknown
0x180492a75  mov     rcx, r15
0x180492a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180492a7d  mov     r8, [rbp+3Fh+arg_8]
0x180492a81  lea     edx, [rbx+0Fh]
0x180492a84  xor     r9d, r9d
0x180492a87  mov     [rsp+130h+var_110], 0
0x180492a90  mov     rcx, rsi
0x180492a93  call    ?NotifySelection@CDoc@@QEAAJW4_EDITOR_NOTIFICATION@@PEAUIUnknown@@KPEAVCElement@@@Z; CDoc::NotifySelection(_EDITOR_NOTIFICATION,IUnknown *,ulong,CElement *)
0x180492a98  mov     rcx, [rbp+3Fh+arg_8]; struct IUnknown *
0x180492a9c  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180492aa1  xor     eax, eax
0x180492aa3  mov     [rsp+130h+var_F0], eax
0x180492aa7  jmp     short loc_180492B0E
0x180492aa9  xor     r9d, r9d
0x180492aac  mov     [rsp+130h+var_110], 0
0x180492ab5  xor     r8d, r8d
0x180492ab8  mov     edx, edi
0x180492aba  mov     rcx, rsi
  ... truncated ...
```
