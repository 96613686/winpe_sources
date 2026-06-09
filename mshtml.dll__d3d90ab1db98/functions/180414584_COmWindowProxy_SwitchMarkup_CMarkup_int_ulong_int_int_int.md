# COmWindowProxy::SwitchMarkup(CMarkup *,int,ulong,int,int,int)

- ea: `0x180414584`
- end: `0x180415a21`
- name: `?SwitchMarkup@COmWindowProxy@@QEAAJPEAVCMarkup@@HKHHH@Z`
- size: `5277`
- prototype: `__int64 __usercall@<rax>(COmWindowProxy *__hidden this@<rcx>, struct CMarkup *@<rdx>, int@<r8d>, unsigned int@<r9d>, int, int, int)`
- caller_count: `9`
- callee_count: `122`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180109a00`
- `0x1804120e0`
- `0x180426610`
- `0x180545a4c`
- `0x18077dfc0`
- `0x18081672c`
- `0x18082cb60`
- `0x1808cc5b4`
- `0x1808d6244`

## callees

- `0x1800151f0`
- `0x1800501fc`
- `0x180051c00`
- `0x18005e648`
- `0x18008a250`
- `0x1800a89a0`
- `0x1800e7be0`
- `0x1800ea428`
- `0x1800ea64c`
- `0x1801085c4`
- `0x1801086ac`
- `0x180115d48`
- `0x18011853c`
- `0x18011a7c4`
- `0x18011df7c`
- `0x180126598`
- `0x1801296e4`
- `0x180138ce4`
- `0x180149610`
- `0x18014e21c`
- `0x18015a504`
- `0x1801dc4a4`
- `0x180217070`
- `0x18026e920`
- `0x18026ee54`
- `0x18027b474`
- `0x1802a16b4`
- `0x1802c63ec`
- `0x1802cea10`
- `0x1802d2f84`
- `0x180308b5c`
- `0x1803bfa94`
- `0x1803c1b74`
- `0x1803c2240`
- `0x1803c9130`
- `0x1803cada4`
- `0x1803cc580`
- `0x1803e0a10`
- `0x1803e4a58`
- `0x1803e6224`
- `0x1803e706c`
- `0x1803e7198`
- `0x1803fbc80`
- `0x1803fc5f8`
- `0x18040bef8`
- `0x180410438`
- `0x18041189c`
- `0x180414584`
- `0x180475504`
- `0x1804755d4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1804155b2`
- `KERNEL32!GetTickCount` at `0x1804155b2`
- `KERNEL32!GetCurrentThreadId` at `0x18041482a`
- `KERNEL32!GetCurrentThreadId` at `0x18041482a`
- `KERNEL32!LeaveCriticalSection` at `0x180414bc3`
- `KERNEL32!LeaveCriticalSection` at `0x180414bc3`
- `KERNEL32!EnterCriticalSection` at `0x180414ba8`
- `KERNEL32!EnterCriticalSection` at `0x180414ba8`
- `USER32!ValidateRect` at `0x180415028`
- `USER32!ValidateRect` at `0x180415028`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18041555a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18041555a`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180414844`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180414844`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x180414882`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x180414882`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180414861`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180414861`
- `OLEAUT32!__imp_SysFreeString` at `0x180414ffa`
- `OLEAUT32!__imp_SysFreeString` at `0x180414ffa`
- `OLEAUT32!__imp_VariantInit` at `0x180414973`
- `OLEAUT32!__imp_VariantInit` at `0x1804156dd`
- `OLEAUT32!__imp_VariantInit` at `0x180414973`
- `OLEAUT32!__imp_VariantInit` at `0x1804156dd`
- `OLEAUT32!__imp_VariantClear` at `0x1804152cd`
- `OLEAUT32!__imp_VariantClear` at `0x1804152cd`

## string_xrefs

- `0x1804148eb`: `COmWindowProxy::SwitchMarkup - fPrimarySwitch=%d dwTravelLogFlags=0x%08lX pWindowOld=0x%08lX pMarkupOld=0x%08lX OldUrl=%S pMarkupNew=0x%08lX NewUrl=%S`

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
  __int64 (__fastcall *v17)(); // rdx
  int v19; // eax
  DWORD CurrentThreadId; // eax
  int v21; // eax
  unsigned __int16 *v22; // rbx
  const wchar_t *v23; // rax
  int v24; // ebx
  int v25; // ecx
  unsigned int v26; // r9d
  int FrameZone; // eax
  LONG lVal; // ecx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rdx
  CEditRouter *EditRouter; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  struct IUnknown *v34; // rcx
  __int64 v35; // rcx
  void (__fastcall *IEFrameProcAddress)(__int64); // rax
  struct CRootElement *v37; // rax
  struct CElement *LookasidePtr2; // rax
  CElement *v39; // rbx
  struct IFrameContentData *FrameContentData; // rax
  int v41; // edi
  int v42; // edx
  struct CElement *v43; // rax
  CElement *ActiveElement; // rax
  struct CRootElement *v45; // rax
  int v46; // eax
  bool v47; // zf
  BOOL v48; // edi
  const unsigned __int16 *Url; // rbx
  const unsigned __int16 *v50; // rax
  _BYTE *LookasidePtr; // rbx
  CSecurityContext *v52; // rbx
  const unsigned __int16 *v53; // rax
  bool v54; // r12
  struct CScriptCollection *ScriptCollection; // rax
  struct CJScript9Holder *JScript9Holder; // rax
  __int64 v57; // rcx
  __int64 v58; // rcx
  int IsPrimaryMarkup; // ebx
  __int64 v60; // rax
  HWND v61; // rcx
  struct CRootElement *v62; // rax
  CDocument *v63; // rbx
  enum _htmlDesignMode AAdesignMode; // edi
  __int64 v65; // rcx
  int v66; // r8d
  __int64 v67; // rdx
  unsigned int Gwnd; // eax
  int v69; // edx
  int v70; // edx
  int v71; // ecx
  int v72; // edx
  int v73; // ecx
  COmWindowProxy *v74; // rdi
  __int64 v75; // rbx
  const unsigned __int16 *v76; // rax
  CMarkup *v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rbx
  __int64 v80; // rdi
  int i; // ebx
  __int64 v82; // rcx
  __int64 v83; // rcx
  void **v84; // rcx
  _QWORD *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rax
  struct CBase *v89; // rdi
  __int64 v90; // rcx
  __int64 v91; // rax
  struct CJScript9Holder *v92; // rbx
  void **v93; // r13
  int v94; // r12d
  CStr *v95; // rbx
  int v96; // edi
  struct CMarkup *v97; // rax
  int IsPageActionAllowed; // edx
  CDoc *v99; // rcx
  struct CMarkup *v100; // rbx
  __int64 v101; // rdx
  struct IUnknown *v102; // rcx
  int v103; // r10d
  int v104; // edx
  int (__fastcall ***v105)(_QWORD, GUID *, struct IUnknown **); // rcx
  struct CMarkup *v106; // rax
  int (__fastcall ***v107)(_QWORD, GUID *, struct IUnknown **); // rcx
  __int64 v108; // rdx
  int v109; // eax
  void (__fastcall *v110)(struct CMarkup *); // rax
  struct CRootElement *v111; // rax
  CMarkup *v112; // rcx
  CZoomState *v113; // rcx
  bool v114; // al
  CTask *v115; // rcx
  const wchar_t *v116; // [rsp+38h] [rbp-B9h]
  int v117; // [rsp+40h] [rbp-B1h]
  struct IDispatch *v118; // [rsp+48h] [rbp-A9h] BYREF
  struct IUnknown *v119; // [rsp+50h] [rbp-A1h] BYREF
  int IsPrimaryWindow; // [rsp+58h] [rbp-99h]
  unsigned int v121; // [rsp+5Ch] [rbp-95h]
  int v122; // [rsp+60h] [rbp-91h]
  int v123; // [rsp+64h] [rbp-8Dh]
  int v124; // [rsp+68h] [rbp-89h]
  CBaseFT *v125; // [rsp+70h] [rbp-81h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-79h] BYREF
  int IsConnectedToThisMarkup; // [rsp+90h] [rbp-61h]
  __int64 v128; // [rsp+98h] [rbp-59h]
  _BYTE v129[16]; // [rsp+A0h] [rbp-51h] BYREF
  _BYTE v130[24]; // [rsp+B0h] [rbp-41h] BYREF
  __int64 v131; // [rsp+C8h] [rbp-29h]
  char v132; // [rsp+D8h] [rbp-19h]
  __int64 v133; // [rsp+E0h] [rbp-11h]
  __int64 v134; // [rsp+E8h] [rbp-9h]
  __int64 v135; // [rsp+F0h] [rbp-1h]
  struct IUnknown *v137; // [rsp+148h] [rbp+57h] BYREF

  v8 = 0;
  v117 = 0;
  v124 = 0;
  v11 = 0;
  v12 = 0;
  v125 = (CBaseFT *)*((_QWORD *)a2 + 15);
  CBase::CLock::CLock((CBase::CLock *)v129, this);
  v13 = 0;
  v118 = 0;
  v119 = 0;
  if ( (Microsoft_IEEnableBits & 0x40) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, MSHTML_CMARKUP_SWITCHMARKUP_START, a2, a4);
  if ( (*((_DWORD *)a2 + 187) & 0x8000000) == 0 )
    goto LABEL_9;
  if ( v125 )
    _InterlockedIncrement((volatile signed __int32 *)v125 + 4);
  v14 = this;
  v128 = *((_QWORD *)this + 15);
  v11 = v128;
  *(_BYTE *)(v128 + 224) &= ~0x80u;
  *(_BYTE *)(v11 + 224) |= (_BYTE)a3 << 7;
  v15 = CWindow::Doc((CWindow *)v11);
  if ( !v15 )
  {
    v8 = -2147467259;
LABEL_8:
    v13 = (struct IUnknown *)v118;
LABEL_9:
    v16 = v119;
    goto LABEL_10;
  }
  IsPrimaryWindow = CWindow::IsPrimaryWindow((CWindow *)v11);
  if ( v125 )
  {
    v117 = *(_DWORD *)(*((_QWORD *)v125 + 12) + 496LL);
    CBaseFT::Release(v125);
    v125 = 0;
  }
  if ( !a3 || (v19 = v117, v117 == -2146697203) )
  {
    CWindow::ReleaseViewLinkedWebOC((CWindow *)v11);
    v19 = v117;
  }
  if ( (*((_BYTE *)a2 + 98) & 0x40) != 0 || v19 == -2146697203 || (v19 == -2146697192 || v19 == -2146697195) && !a3 )
  {
    *((_DWORD *)a2 + 188) |= 0x4000u;
    goto LABEL_205;
  }
  if ( v19 == -2146697211
    || v19 == -2146697209
    || v19 == -2147024891
    || v19 == -2147467260
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
    LODWORD(v137) = 0;
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)&v137, 0) >= 0
      && !LCIE2IsComponentSharedFlagValueSet((unsigned int)v137, 0x20u) )
    {
      *((_DWORD *)this + 42) &= ~8u;
      LCIE2ChangeComponentSharedFlagBit((unsigned int)v137, 0, 5u);
    }
    v21 = *((_DWORD *)this + 42);
    if ( (v21 & 8) != 0 )
    {
      *((_DWORD *)this + 42) = v21 & 0xFFFFFFF7;
      COmWindowProxy::Fire_onunload(this);
      if ( !CMarkup::Window((CMarkup *)v12) || !*((_QWORD *)a2 + 44) )
        goto LABEL_205;
    }
  }
  v121 = 4;
  v22 = CMarkup::Url(a2);
  v23 = CMarkup::Url((CMarkup *)v12);
  v116 = v22;
  v24 = IsPrimaryWindow;
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "COmWindowProxy::SwitchMarkup - fPrimarySwitch=%d dwTravelLogFlags=0x%08lX pWindowOld=0x%08lX pMarkupOld=0x%08lX OldU"
    "rl=%S pMarkupNew=0x%08lX NewUrl=%S",
    IsPrimaryWindow,
    a4,
    v11,
    v12,
    v23,
    (_DWORD)a2,
    v116);
  if ( (a4 & 1) != 0 )
  {
    v25 = (2 * ((*((_DWORD *)a2 + 188) & 1) == 0)) | 4;
    if ( (a4 & 2) != 0 )
      v25 = 2 * ((*((_DWORD *)a2 + 188) & 1) == 0);
    v26 = v25 | 0x20;
    if ( (*(_BYTE *)(v11 + 226) & 1) == 0 )
      v26 = v25;
    CDoc::UpdateTravelLog(v15, (struct CWindow *)v11, a2, v26);
  }
  if ( !IsPrimaryWindow )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    FrameZone = CMarkup::GetFrameZone((CMarkup *)v12, &pvarg, 1);
    lVal = v121;
    if ( FrameZone >= 0 )
      lVal = pvarg.lVal;
    v121 = lVal;
  }
  CDoc::UpdateInterval(v15, 0);
  v29 = *(_QWORD *)(v12 + 216);
  if ( (*(_BYTE *)(v29 + 8) & 8) != 0 || *((_BYTE *)a2 + 248) )
  {
    v30 = *(const unsigned __int16 **)(v29 + 16);
    if ( v30 )
      CSmartBstr::Set((CSmartBstr *)(*((_QWORD *)a2 + 27) + 16LL), v30);
    *(_DWORD *)(*((_QWORD *)a2 + 27) + 28LL) = *(_DWORD *)(*(_QWORD *)(v12 + 216) + 28LL);
  }
  if ( (unsigned int)CMarkup::HasEditRouter((CMarkup *)v12) )
  {
    EditRouter = CMarkup::GetEditRouter((CMarkup *)v12);
    CEditRouter::Passivate(EditRouter);
  }
  if ( v24 || !CMarkup::GetParentMarkup((CMarkup *)v12) )
  {
    CDoc::NotifySelection(v15, 1, 0);
    CDoc::ReleaseEditor(v15);
    v117 = 0;
    if ( v24 )
    {
      v34 = (struct IUnknown *)*((_QWORD *)v15 + 8);
      if ( v34 )
        CTExec(v34, &CGID_ShellDocView, 0xB3u, 0, 0, 0);
      CView::Unload((struct CDoc *)((char *)v15 + 2264));
      ++*((_DWORD *)v15 + 1390);
    }
  }
  else
  {
    v33 = *(_QWORD *)v12;
    v137 = 0;
    if ( *(__int64 (__fastcall **)())(v33 + 984) != _vtguard )
      _report_securityfailure(1, v32);
    (*(void (__fastcall **)(unsigned __int64, GUID *, struct IUnknown **))(v33 + 1136))(v12, &IID_IUnknown, &v137);
    CDoc::NotifySelection(v15, 15, v137);
    ReleaseInterface(v137);
    v117 = 0;
  }
  if ( *((char *)v15 + 4868) >= 0
    || CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)v15 + 1260)) )
  {
    EnsureIEFrame();
    IEFrameProcAddress = (void (__fastcall *)(__int64))qword_1815C5948;
    if ( qword_1815C5948
      || (IEFrameProcAddress = (void (__fastcall *)(__int64))GetIEFrameProcAddress(234),
          (qword_1815C5948 = (__int64)IEFrameProcAddress) != 0) )
    {
      IEFrameProcAddress(v35);
    }
  }
  if ( v24 )
    CDoc::FlushUndoData(v15);
  CMarkup::ClearUndoData((CMarkup *)v12);
  if ( v24 || CDoc::GetCurrentMarkup(v15) == (struct CMarkup *)v12 )
  {
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_DWORD *)v15 + 1214) ^= (*((_DWORD *)v15 + 1214) ^ ((unsigned int)IsInIEBrowser(v15) << 28)) & 0x10000000;
    if ( (byte_1815BFC79 & 2) == 0 || (*((_DWORD *)v15 + 1219) & 0x2000000) == 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 3536));
      TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v15 + 4728);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 3536));
    }
  }
  CInputManager::ClearCachedNodesOnSwitchMarkup((struct CTreeNode **)v15 + 135, (struct CMarkup *)v12);
  v37 = CMarkup::Root((CMarkup *)v12);
  LookasidePtr2 = (struct CElement *)CElement::GetLookasidePtr2(v37, 0);
  v39 = LookasidePtr2;
  if ( LookasidePtr2 )
  {
    FrameContentData = GetFrameContentData(LookasidePtr2);
    if ( FrameContentData )
    {
      v117 = CMarkup::EnforceRestrictionsFromFrameData(a2, FrameContentData);
      v8 = v117;
      if ( v117 )
        goto LABEL_8;
      v41 = a5;
      goto LABEL_87;
    }
    v41 = a5;
  }
  else
  {
    v41 = a5;
    if ( (*(_DWORD *)(v12 + 756) & 0x100) != 0 && a5 )
    {
      LODWORD(v137) = 0;
      CMarkup::GetSandboxFlags((CMarkup *)v12, (struct SandboxFlags *)&v137);
      v117 = CMarkup::EnforceSandbox(a2, (const struct SandboxFlags *)&v137);
      v8 = v117;
      if ( v117 )
        goto LABEL_8;
LABEL_87:
      v14 = this;
    }
  }
  v42 = *((_DWORD *)v14 + 42)
      ^ ((unsigned __int16)*((_DWORD *)v14 + 42)
       ^ (unsigned __int16)((unsigned __int8)BYTE1(*((_DWORD *)a2 + 189)) << 12))
      & 0x1000;
  *((_DWORD *)v14 + 42) = v42;
  *((_DWORD *)v14 + 42) = v42 & 0xFFFFDFFF | ((*((_DWORD *)a2 + 189) & 0x500) != 256 ? 0x2000 : 0);
  if ( v39 )
  {
    CElement::CLock::CLock(&pvarg, v39, 0);
    v43 = CMarkup::Root(a2);
    v117 = CElement::SetViewSubordinate(v39, v43);
    v8 = v117;
    if ( v117 )
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
    v45 = CMarkup::Root((CMarkup *)v12);
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_QWORD *)v15 + 113) = v45;
  }
  *((_DWORD *)v14 + 42) &= ~0x20u;
  v46 = CMarkup::AccessAllowed(a2, (struct CMarkup *const)v12);
  v47 = *((_BYTE *)a2 + 136) >= 0;
  v122 = v46;
  if ( v47 )
  {
    if ( v46 )
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
        v122 = 1;
    }
    goto LABEL_113;
  }
  if ( !v46 )
    goto LABEL_104;
  v48 = CMarkup::GetDwnPost(a2) != 0;
  Url = CMarkup::GetUrl(a2);
  v50 = CMarkup::GetUrl((const struct CMarkup *const)v12);
  if ( (unsigned int)CDoc::IsSameUrl(v50, &Source, Url, &Source, v48) )
  {
    v41 = 1;
LABEL_113:
    a5 = v41;
    goto LABEL_115;
  }
  v41 = a5;
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
    v52 = *(CSecurityContext **)(v12 + 320);
    v53 = CMarkup::GetUrl((const struct CMarkup *const)v12);
    CSecurityContext::SetOriginalURL(v52, v53);
  }
  if ( *((_BYTE *)a2 + 876) && *((int *)a2 + 212) >= 90000 )
  {
    v54 = v41 != 0;
    ScriptCollection = CMarkup::GetScriptCollection((CMarkup *)v12, 1);
    if ( ScriptCollection
      && *((_QWORD *)ScriptCollection + 8)
      && (JScript9Holder = CScriptCollection::GetJScript9Holder(ScriptCollection)) != 0
      && (*((_BYTE *)JScript9Holder + 412) = 0,
          *((_BYTE *)JScript9Holder + 413) = v41 == 0,
          (v57 = *((_QWORD *)a2 + 15)) != 0) )
    {
      v58 = *(_QWORD *)(v57 + 96);
      LOBYTE(v137) = 1;
      if ( (*(_BYTE *)(v58 + 384) & 1) != 0 )
        *((_BYTE *)JScript9Holder + 414) = 0;
    }
    else
    {
      LOBYTE(v137) = 1;
    }
  }
  else
  {
    LOBYTE(v137) = 0;
    v54 = 0;
  }
  IsPrimaryMarkup = CMarkup::IsPrimaryMarkup((CMarkup *)v12);
  CMarkup::TearDownMarkup((CMarkup *)v12, 1, 1);
  if ( IsPrimaryMarkup )
    CDoc::EraseFrontBufferIfNeeeded(v15);
  v47 = IsPrimaryWindow == 0;
  *(_DWORD *)(*(_QWORD *)(v12 + 320) + 12LL) = 0;
  if ( !v47 )
  {
    if ( (*((_BYTE *)a2 + 760) & 4) != 0 )
    {
      *((_BYTE *)v15 + 937) = 0;
      *((_QWORD *)v15 + 119) = 0;
      SysFreeString(*((BSTR *)v15 + 118));
      *((_QWORD *)v15 + 118) = 0;
    }
    v60 = *((_QWORD *)v15 + 12);
    if ( v60 )
    {
      v61 = *(HWND *)(v60 + 168);
      if ( v61 )
        ValidateRect(v61, 0);
    }
  }
  if ( !CMarkup::Window((CMarkup *)v12) || !*((_QWORD *)a2 + 44) )
    goto LABEL_205;
  v123 = 0;
  if ( IsConnectedToThisMarkup )
  {
    *((_QWORD *)v15 + 112) = 0;
    v62 = CMarkup::Root(a2);
    *((_DWORD *)v15 + 1214) &= ~0x1000000u;
    *((_QWORD *)v15 + 113) = v62;
  }
  v63 = *(CDocument **)(*((_QWORD *)this + 15) + 120LL);
  AAdesignMode = CDocument::GetAAdesignMode(v63);
  if ( (*((_BYTE *)a2 + 752) & 1) != 0 && (*((_DWORD *)v15 + 1216) & 0x800) != 0 )
  {
    v65 = *((_QWORD *)v63 + 3);
    if ( v65 )
    {
      v66 = *(_DWORD *)(v65 + 4);
      if ( v66 > 0 )
      {
        v67 = 0;
        while ( *(_BYTE *)(*(_QWORD *)(v65 + 8) + 24 * v67) != 1 )
        {
          v67 = (unsigned int)(v67 + 1);
          if ( (int)v67 >= v66 )
            goto LABEL_157;
        }
        CDocument::GetXMLExpando(v63, &v118, (struct IDispatch **)&v119);
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
  v69 = IsPrimaryWindow;
  *((_DWORD *)a2 + 187) = *((_DWORD *)a2 + 187) & 0xF3FFFFFF | 0x4000000;
  if ( v69 )
    *((_DWORD *)v15 + 1217) &= ~0x20000000u;
  if ( !CMarkup::Window(a2) )
    *((_DWORD *)a2 + 187) &= ~0x4000000u;
  if ( !v70 || (*((_DWORD *)a2 + 34) & 0x504LL) == 0 )
  {
    CDocument::SetAAdesignMode(*(CDocument **)(*((_QWORD *)this + 15) + 120LL), AAdesignMode);
    v71 = *(_DWORD *)(v12 + 752);
    v72 = *((_DWORD *)a2 + 188);
    if ( ((v72 ^ *(_BYTE *)(v12 + 752)) & 0x80u) != 0 || (((unsigned __int8)v72 ^ (unsigned __int8)v71) & 0x40) != 0 )
      v123 = 1;
    v73 = v72 ^ ((unsigned __int8)v72 ^ (unsigned __int8)v71) & 0x80;
    *((_DWORD *)a2 + 188) = v73;
    *((_DWORD *)a2 + 188) = v73 ^ (*(_DWORD *)(v12 + 752) ^ v73) & 0x40;
  }
  v74 = this;
  *(_QWORD *)(v11 + 104) = a2;
  *((_DWORD *)a2 + 4) += 8;
  COmWindowProxy::OnSetWindow(this);
  CMarkup::UpdateSecurityID(a2);
  if ( (*((_BYTE *)a2 + 136) & 0x20) != 0 )
  {
    v75 = *(_QWORD *)(*((_QWORD *)this + 15) + 136LL);
    if ( v75 )
    {
      COmWindowProxy::GetScriptMarkupContext(this);
      v76 = CMarkup::GetUrl(a2);
      if ( CMarkup::ShouldSourceInheritParentDomain(v77, v76) )
      {
        v78 = *(_QWORD *)(v75 + 128);
        if ( v78 )
          *((_DWORD *)this + 42) ^= (*(_DWORD *)(v78 + 168) ^ *((_DWORD *)this + 42)) & 1;
      }
    }
  }
  v79 = *(_QWORD *)(v12 + 328);
  if ( v79 )
  {
    v80 = *(_QWORD *)(v79 + 8);
    for ( i = *(_DWORD *)(v79 + 4); i; --i )
    {
      v82 = *(_QWORD *)(v80 + 16);
      if ( v82 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 88LL))(v82);
      v80 += 96;
    }
    v74 = this;
  }
  v83 = *(_QWORD *)(v11 + 616);
  if ( v83 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    *(_QWORD *)(v11 + 616) = 0;
  }
  *(_BYTE *)(v11 + 488) = 0;
  VariantClear((VARIANTARG *)(v11 + 464));
  if ( !a5 )
  {
    CDocument::ResetSecurityThunk(*(CDocument **)(*((_QWORD *)v74 + 15) + 120LL));
    v84 = (void **)((char *)v74 + 152);
    if ( !v122 )
      ResetSecurityThunkHelper(v84);
    v85 = (_QWORD *)*((_QWORD *)v74 + 20);
    if ( v85 )
    {
      *v84 = v85;
      *((_QWORD *)v74 + 20) = 0;
      *(_DWORD *)(v85[5] + 20LL) = 3;
    }
  }
  v86 = *(_QWORD *)(v11 + 112);
  if ( v86 )
  {
    v17 = _vtguard;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v86 + 984LL) != _vtguard )
      goto LABEL_264;
    (*(void (**)(void))(*(_QWORD *)v86 + 1152LL))();
    *(_QWORD *)(v11 + 112) = 0;
  }
  v87 = 16;
  if ( (_BYTE)v137 )
  {
    CAryWindowTbl::SafeIterateProxies(
      *(CAryWindowTbl **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 472LL),
      (struct CWindow *)v11,
      (int (*)(struct CWindow *, struct COmWindowProxy *))CAryWindowTbl::ReinitializeProxyVarIterationHandler);
    if ( v54 )
    {
      v88 = *((_QWORD *)v74 + 15);
      v137 = 0;
      v89 = *(struct CBase **)(v88 + 120);
      CJScript9Holder::ReinitializeOrClearObject(v89, a2, 0);
      v90 = *(_QWORD *)(v11 + 104);
      v17 = _vtguard;
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)v90 + 984LL) != _vtguard )
        goto LABEL_264;
      v91 = (*(__int64 (**)(void))(*(_QWORD *)v90 + 1192LL))();
      v92 = (struct CJScript9Holder *)v91;
      if ( v91 )
      {
        v87 = *(_QWORD *)(v91 + 392);
        if ( v87 )
        {
          v87 = *(_QWORD *)(v87 + 40) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v87 )
          {
            v93 = CJScript9Holder::ExtensionRefFromVar((void *)v87);
            v117 = CJScript9Holder::CBaseToVar(v89, v92, (void **)&v137);
            if ( v117 >= 0 )
            {
              v87 = (__int64)v137;
              v93[5] = v137;
            }
            v11 = v128;
          }
        }
      }
    }
  }
  if ( FeatureControlHelper::PublicObjectCaching((FeatureControlHelper *)v87) )
    CWindow::InvalidateReusedObjects((CWindow *)v11);
  CDocument::InvalidateReusedObjects(*(CDocument **)(*((_QWORD *)this + 15) + 120LL));
  *(_BYTE *)(v11 + 225) &= ~0x20u;
  if ( !IsPrimaryWindow )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (int)CMarkup::GetFrameZone(a2, &pvarg, 1) < 0 || v121 < pvarg.lVal )
    {
      v106 = CDoc::PrimaryMarkup(v15);
      if ( v106 )
        *((_DWORD *)v106 + 197) = 0;
    }
LABEL_228:
    v107 = (int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)v15 + 8);
    v137 = 0;
    if ( v107 && (**v107)(v107, &IID_IDocHostUIHandlerPriv, &v137) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *, _QWORD))v137->lpVtbl[1].QueryInterface)(v137, 0);
      ((void (__fastcall *)(struct IUnknown *))v137->lpVtbl->Release)(v137);
    }
    goto LABEL_231;
  }
  if ( (*((_BYTE *)v15 + 16) & 2) != 0 )
  {
    v117 = -2147467259;
LABEL_205:
    v8 = v117;
    goto LABEL_8;
  }
  v94 = 0;
  v95 = (struct CDoc *)((char *)v15 + 4480);
  v96 = 4;
  do
  {
    CStr::_Free(v95);
    *(_QWORD *)v95 = 0;
    v95 = (CStr *)((char *)v95 + 8);
    --v96;
  }
  while ( v96 );
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
  v97 = CDoc::PrimaryMarkup(v15);
  v100 = v97;
  if ( v97 )
    IsPageActionAllowed = CDoc::IsPageActionAllowed(v99, v97, 0x80000u);
  v47 = IsPageActionAllowed == 0;
  v101 = *((_QWORD *)v100 + 40);
  if ( v47 )
  {
    CDoc::SetRootSslState(v15, v101, 0, *((unsigned int *)v15 + 1104), *((_DWORD *)v15 + 1105), 1);
  }
  else
  {
    CDoc::SetRootSslState(v15, v101, 0, 0, 0, 1);
    if ( IsDualEngineProcess() )
    {
      v102 = (struct IUnknown *)*((_QWORD *)v15 + 8);
      if ( v102 )
        CTExec(v102, &CGID_Explorer, 0x87u, 0, 0, 0);
    }
  }
  CDoc::SwitchPageActionBlockedState(v15);
  *((_DWORD *)v15 + 1228) = GetTickCount();
  CDoc::SetIgnoreRootSslErrors(v15, 1, 0);
  *((_DWORD *)v15 + 1107) ^= v104 & (*((_DWORD *)v15 + 1107) ^ v103);
  CDoc::SwitchWPCBlockedUrlList(v15);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 739) + 16LL))(*((_QWORD *)v15 + 739));
  *((_QWORD *)v15 + 739) = *((_QWORD *)v15 + 740);
  *((_QWORD *)v15 + 740) = 0;
  CreatePrivacIEContentLog();
  CMultimediaLog::Reset((struct CDoc *)((char *)v15 + 5928));
  if ( *((_QWORD *)v15 + 8) )
  {
    CDoc::UpdateDocHostUI(v15, 1);
    v105 = (int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)v15 + 8);
    v137 = 0;
    if ( (**v105)(v105, &IID_IDocHostUIHandlerPriv, &v137) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *, __int64))v137->lpVtbl[1].QueryInterface)(v137, 1);
      v94 = 1;
      ((void (__fastcall *)(struct IUnknown *))v137->lpVtbl->Release)(v137);
    }
  }
  if ( !a5 )
    CDoc::ResetEventBits(v15);
  *((_BYTE *)CDoc::EventMgr(v15) + 100) = 1;
  CTridentMediaConsentMgr::Cleanup((struct CDoc *)((char *)v15 + 5368));
  CDoc::AttemptRestoreHardwareDevice(v15);
  if ( !v94 )
    goto LABEL_228;
LABEL_231:
  CMarkup::InitWindow(a2);
  v109 = *((_DWORD *)a2 + 189);
  if ( (v109 & 0x1000000) != 0 )
  {
    *((_DWORD *)a2 + 189) = v109 & 0xFEFFFFFF;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)a2 + 984LL) != _vtguard )
      _report_securityfailure(1, v108);
    v110 = *(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)a2 + 1144LL);
    v124 = 1;
    v110(a2);
    v131 = 0;
    v133 = 0;
    v134 = 0;
    v135 = 0;
    v132 = 0;
    v111 = CMarkup::Root(a2);
    CNotification::Initialize(v130, 96, v111, 0, 0, 0);
    CMarkup::Notify(a2, (struct CNotification *)v130, 0);
    if ( !CMarkup::Window(a2) )
      goto LABEL_205;
  }
  *(_BYTE *)(v11 + 223) |= 1u;
  if ( v123 )
    CMarkup::EnsureFormatCacheChange(a2, 0x20080u);
  if ( (unsigned int)CMarkup::HasIdentityPeerTask(a2) )
    CMarkup::ProcessIdentityPeerTask(v112);
  v16 = v119;
  if ( v118 || v119 )
    CDocument::SetXMLExpando(*(CDocument **)(*((_QWORD *)this + 15) + 120LL), v118, (struct IDispatch *)v119);
  FormsHideTooltip(1, v12);
  if ( IsPrimaryWindow )
  {
    v113 = (CZoomState *)*((_QWORD *)v15 + 649);
    CSmoothScroller::s_cSlowScrolls = 0;
    if ( v113 )
      CZoomState::ClearTransientZoomState(v113);
    *((_DWORD *)v15 + 963) = 1065353216;
    CUnitInfo::UpdateTotalOpticalZoom((struct CDoc *)((char *)v15 + 3632));
    if ( LCIE_IsCurrentTabThreadEmptyTab() )
    {
      if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
        McTemplateU0ppq_EventWriteTransfer(
          (unsigned int)&BERP_IE_Context,
          (unsigned int)MSHTML_CDOC_HOSTPAINTUPDATENOTIFICATION_IGNOREDREQUEST_INFO,
          (_DWORD)v15,
          (_DWORD)a2,
          11);
    }
    else if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
    {
      McTemplateU0ppq_EventWriteTransfer(
        (unsigned int)&BERP_IE_Context,
        (unsigned int)MSHTML_CDOC_HOSTPAINTUPDATENOTIFICATION_IGNOREDREQUEST_INFO,
        (_DWORD)v15,
        (_DWORD)a2,
        7);
    }
    CDoc::ClearAtViewportCache(v15);
    v114 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL)
                    + 248LL)
        && CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)v15
                                                                                               + 1260))
        && *((_QWORD *)v15 + 287);
    *((_BYTE *)v15 + 2304) = v114;
    CDoc::UpdateUnitInfo(v15, 0);
    CFlipAheadManager::Reset((struct CDoc *)((char *)v15 + 6688));
    v115 = (CTask *)*((_QWORD *)v15 + 853);
    if ( v115 )
      CTask::SetBlocked(v115, 1);
    if ( *((char *)v15 + 4868) >= 0 )
      CDoc::ForceKeyboardDismiss(v15);
    CDoc::SignalDocumentUriChanged(v15);
    if ( CDoc::HasFocus(v15) )
      CMarkup::FireFocusTelemetry(a2, 1);
  }
  v8 = v117;
  v13 = (struct IUnknown *)v118;
LABEL_10:
  if ( v125 )
    CBaseFT::Release(v125);
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
  if ( !v124 )
    goto LABEL_20;
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)a2 + 984LL) != _vtguard )
LABEL_264:
    _report_securityfailure(1, v17);
  (*(void (__fastcall **)(struct CMarkup *))(*(_QWORD *)a2 + 1152LL))(a2);
LABEL_20:
  if ( (Microsoft_IEEnableBits & 0x40) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, MSHTML_CMARKUP_SWITCHMARKUP_STOP, a2, v8);
  CBase::CLock::~CLock((CBase::CLock *)v129);
  return v8;
}

```

## disassembly

```asm
0x180414584  mov     [rsp-8+arg_10], rbx
0x180414589  mov     [rsp-8+arg_0], rcx
0x18041458e  push    rbp
0x18041458f  push    rsi
0x180414590  push    rdi
0x180414591  push    r12
0x180414593  push    r13
0x180414595  push    r14
0x180414597  push    r15
0x180414599  lea     rbp, [rsp-0Fh]
0x18041459e  sub     rsp, 100h
0x1804145a5  mov     r14, rdx
0x1804145a8  xor     r12d, r12d
0x1804145ab  mov     rdx, rcx; struct CBase *
0x1804145ae  mov     [rsp+130h+var_F0], r12d
0x1804145b3  mov     edi, r9d
0x1804145b6  mov     [rsp+130h+var_C8], r12d
0x1804145bb  mov     ebx, r8d
0x1804145be  xor     r13d, r13d
0x1804145c1  mov     rcx, [r14+78h]
0x1804145c5  xor     r15d, r15d
0x1804145c8  mov     [rsp+130h+var_C0], rcx
0x1804145cd  lea     rcx, [rbp+3Fh+var_90]; this
0x1804145d1  call    ??0CLock@CBase@@QEAA@PEAV1@@Z; CBase::CLock::CLock(CBase *)
0x1804145d6  xor     esi, esi
0x1804145d8  test    byte ptr cs:Microsoft_IEEnableBits, 40h
0x1804145df  mov     [rsp+130h+var_E8], rsi
0x1804145e4  mov     [rsp+130h+var_E0], rsi
0x1804145e9  jz      short loc_180414604
0x1804145eb  mov     r9d, edi
0x1804145ee  lea     rdx, MSHTML_CMARKUP_SWITCHMARKUP_START
0x1804145f5  mov     r8, r14
0x1804145f8  lea     rcx, BERP_IE_Context
0x1804145ff  call    McTemplateU0pq_EventWriteTransfer
0x180414604  test    dword ptr [r14+2ECh], 8000000h
0x18041460f  jz      short loc_18041465F
0x180414611  mov     rax, [rsp+130h+var_C0]
0x180414616  test    rax, rax
0x180414619  jz      short loc_18041461F
0x18041461b  lock inc dword ptr [rax+10h]
0x18041461f  mov     r12, [rbp+3Fh+arg_0]
0x180414623  mov     al, bl
0x180414625  shl     al, 7
0x180414628  mov     r13, [r12+78h]
0x18041462d  mov     rcx, r13; this
0x180414630  mov     [rbp+3Fh+var_98], r13
0x180414634  and     byte ptr [r13+0E0h], 7Fh
0x18041463c  or      [r13+0E0h], al
0x180414643  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180414648  mov     rsi, rax
0x18041464b  test    rax, rax
0x18041464e  jnz     loc_180414736
0x180414654  mov     r12d, 80004005h
0x18041465a  mov     rsi, [rsp+130h+var_E8]
0x18041465f  mov     rbx, [rsp+130h+var_E0]
0x180414664  mov     rax, [rsp+130h+var_C0]
0x180414669  test    rax, rax
0x18041466c  jz      short loc_180414676
0x18041466e  mov     rcx, rax; this
0x180414671  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180414676  test    r13, r13
0x180414679  jz      short loc_180414683
0x18041467b  and     byte ptr [r13+0E0h], 7Fh
0x180414683  mov     rcx, rsi; struct IUnknown *
0x180414686  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18041468b  mov     rcx, rbx; struct IUnknown *
0x18041468e  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180414693  lea     rbx, __vtguard
0x18041469a  test    r15, r15
0x18041469d  jz      short loc_1804146BE
0x18041469f  mov     rax, [r15]
0x1804146a2  cmp     [rax+3D8h], rbx
0x1804146a9  jnz     loc_180415A0E
0x1804146af  mov     rax, [rax+480h]
0x1804146b6  mov     rcx, r15
0x1804146b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804146be  mov     rcx, r14; this
0x1804146c1  call    ?UnblockScriptExecutionHelper@CMarkup@@QEAAJXZ; CMarkup::UnblockScriptExecutionHelper(void)
0x1804146c6  cmp     [rsp+130h+var_C8], 0
0x1804146cb  jz      short loc_1804146EC
0x1804146cd  mov     rax, [r14]
0x1804146d0  cmp     [rax+3D8h], rbx
0x1804146d7  jnz     loc_180415A0E
0x1804146dd  mov     rax, [rax+480h]
0x1804146e4  mov     rcx, r14
0x1804146e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804146ec  test    byte ptr cs:Microsoft_IEEnableBits, 40h
0x1804146f3  jz      short loc_18041470E
0x1804146f5  mov     r9d, r12d
0x1804146f8  lea     rdx, MSHTML_CMARKUP_SWITCHMARKUP_STOP
0x1804146ff  mov     r8, r14
0x180414702  lea     rcx, BERP_IE_Context
0x180414709  call    McTemplateU0pq_EventWriteTransfer
0x18041470e  lea     rcx, [rbp+3Fh+var_90]; this
0x180414712  call    ??1CLock@CBase@@QEAA@XZ; CBase::CLock::~CLock(void)
0x180414717  mov     rbx, [rsp+130h+arg_10]
0x18041471f  mov     eax, r12d
0x180414722  add     rsp, 100h
0x180414729  pop     r15
0x18041472b  pop     r14
0x18041472d  pop     r13
0x18041472f  pop     r12
0x180414731  pop     rdi
0x180414732  pop     rsi
0x180414733  pop     rbp
0x180414734  retn
0x180414736  mov     rcx, r13; this
0x180414739  call    ?IsPrimaryWindow@CWindow@@QEAAHXZ; CWindow::IsPrimaryWindow(void)
0x18041473e  mov     rcx, [rsp+130h+var_C0]; this
0x180414743  mov     [rsp+130h+var_D8], eax
0x180414747  test    rcx, rcx
0x18041474a  jz      short loc_180414766
0x18041474c  mov     rax, [rcx+60h]
0x180414750  mov     eax, [rax+1F0h]
0x180414756  mov     [rsp+130h+var_F0], eax
0x18041475a  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x18041475f  xor     ecx, ecx
0x180414761  mov     [rsp+130h+var_C0], rcx
0x180414766  test    ebx, ebx
0x180414768  jz      short loc_180414775
0x18041476a  mov     eax, [rsp+130h+var_F0]
0x18041476e  cmp     eax, 800C000Dh
0x180414773  jnz     short loc_180414781
0x180414775  mov     rcx, r13; this
0x180414778  call    ?ReleaseViewLinkedWebOC@CWindow@@QEAAXXZ; CWindow::ReleaseViewLinkedWebOC(void)
0x18041477d  mov     eax, [rsp+130h+var_F0]
0x180414781  test    byte ptr [r14+62h], 40h
0x180414786  jnz     loc_1804159F5
0x18041478c  cmp     eax, 800C000Dh
0x180414791  jz      loc_1804159F5
0x180414797  cmp     eax, 800C0018h
0x18041479c  jz      short loc_1804147A5
0x18041479e  cmp     eax, 800C0015h
0x1804147a3  jnz     short loc_1804147AD
0x1804147a5  test    ebx, ebx
0x1804147a7  jz      loc_1804159F5
0x1804147ad  cmp     eax, 800C0005h
0x1804147b2  jz      loc_1804159E2
0x1804147b8  cmp     eax, 800C0007h
0x1804147bd  jz      loc_1804159E2
0x1804147c3  cmp     eax, 80070005h
0x1804147c8  jz      loc_1804159E2
0x1804147ce  cmp     eax, 80004004h
0x1804147d3  jz      loc_1804159E2
0x1804147d9  test    dword ptr [r14+2F0h], 200000h
0x1804147e4  jnz     loc_1804159E2
0x1804147ea  mov     r15, [r13+68h]
0x1804147ee  lea     rcx, __vtguard
0x1804147f5  mov     rax, [r15]
0x1804147f8  cmp     [rax+3D8h], rcx
0x1804147ff  jnz     loc_180415A0E
0x180414805  mov     rax, [rax+478h]
0x18041480c  mov     rcx, r15
0x18041480f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180414814  test    byte ptr [r12+0A8h], 8
0x18041481d  jz      loc_1804148CB
0x180414823  mov     dword ptr [rbp+3Fh+arg_8], 0
0x18041482a  call    cs:__imp_GetCurrentThreadId
0x180414831  nop     dword ptr [rax+rax+00h]
0x180414836  xor     r9d, r9d
0x180414839  lea     r8, [rbp+3Fh+arg_8]
0x18041483d  mov     edx, eax
0x18041483f  mov     ecx, 203h
0x180414844  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18041484b  nop     dword ptr [rax+rax+00h]
0x180414850  mov     ebx, 0FFFFFFF7h
0x180414855  test    eax, eax
0x180414857  js      short loc_18041488E
0x180414859  mov     ecx, dword ptr [rbp+3Fh+arg_8]
0x18041485c  mov     edx, 20h ; ' '
0x180414861  call    cs:__imp_?LCIE2IsComponentSharedFlagValueSet@@YAJKK@Z; LCIE2IsComponentSharedFlagValueSet(ulong,ulong)
0x180414868  nop     dword ptr [rax+rax+00h]
0x18041486d  test    eax, eax
0x18041486f  jnz     short loc_18041488E
0x180414871  and     [r12+0A8h], ebx
0x180414879  lea     r8d, [rax+5]
0x18041487d  mov     ecx, dword ptr [rbp+3Fh+arg_8]
0x180414880  xor     edx, edx
0x180414882  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit@@YAJK_NK@Z; LCIE2ChangeComponentSharedFlagBit(ulong,bool,ulong)
0x180414889  nop     dword ptr [rax+rax+00h]
0x18041488e  mov     eax, [r12+0A8h]
0x180414896  test    al, 8
0x180414898  jz      short loc_1804148CB
0x18041489a  and     eax, ebx
0x18041489c  mov     rcx, r12; this
0x18041489f  mov     [r12+0A8h], eax
0x1804148a7  call    ?Fire_onunload@COmWindowProxy@@QEAAXXZ; COmWindowProxy::Fire_onunload(void)
0x1804148ac  mov     rcx, r15; this
0x1804148af  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1804148b4  test    rax, rax
0x1804148b7  jz      loc_18041545F
0x1804148bd  cmp     qword ptr [r14+160h], 0
0x1804148c5  jz      loc_18041545F
0x1804148cb  mov     rcx, r14; this
0x1804148ce  mov     [rsp+130h+var_D4], 4
0x1804148d6  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x1804148db  mov     rcx, r15; this
0x1804148de  mov     rbx, rax
0x1804148e1  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x1804148e6  mov     [rsp+130h+var_F8], rbx
0x1804148eb  lea     rcx, aComwindowproxy; "COmWindowProxy::SwitchMarkup - fPrimary"...
0x1804148f2  mov     ebx, [rsp+130h+var_D8]
0x1804148f6  mov     r9, r13
0x1804148f9  mov     [rsp+130h+var_100], r14
0x1804148fe  mov     edx, ebx
0x180414900  mov     [rsp+130h+var_108], rax
0x180414905  mov     r8d, edi
0x180414908  mov     [rsp+130h+var_110], r15
0x18041490d  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x180414912  test    dil, 1
0x180414916  jz      short loc_180414959
0x180414918  mov     eax, [r14+2F0h]
0x18041491f  mov     r8, r14; struct CMarkup *
0x180414922  not     eax
0x180414924  mov     rdx, r13; struct CWindow *
0x180414927  and     eax, 1
0x18041492a  add     eax, eax
0x18041492c  mov     ecx, eax
0x18041492e  or      ecx, 4
0x180414931  test    dil, 2
0x180414935  mov     edi, 1
0x18041493a  cmovnz  ecx, eax
0x18041493d  mov     r9d, ecx
0x180414940  or      r9d, 20h
0x180414944  test    [r13+0E2h], dil
0x18041494b  cmovz   r9d, ecx; unsigned int
0x18041494f  mov     rcx, rsi; this
0x180414952  call    ?UpdateTravelLog@CDoc@@QEAAXPEAVCWindow@@PEAVCMarkup@@K@Z; CDoc::UpdateTravelLog(CWindow *,CMarkup *,ulong)
0x180414957  jmp     short loc_18041495E
0x180414959  mov     edi, 1
0x18041495e  test    ebx, ebx
0x180414960  jnz     short loc_18041499C
0x180414962  xorps   xmm0, xmm0
0x180414965  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180414969  xor     eax, eax
0x18041496b  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18041496f  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180414973  call    cs:__imp_VariantInit
0x18041497a  nop     dword ptr [rax+rax+00h]
0x18041497f  mov     r8d, edi; int
0x180414982  lea     rdx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x180414986  mov     rcx, r15; this
0x180414989  call    ?GetFrameZone@CMarkup@@QEAAJPEAUtagVARIANT@@H@Z; CMarkup::GetFrameZone(tagVARIANT *,int)
0x18041498e  mov     ecx, [rsp+130h+var_D4]
0x180414992  test    eax, eax
0x180414994  cmovns  ecx, dword ptr [rbp+3Fh+pvarg+8]
0x180414998  mov     [rsp+130h+var_D4], ecx
0x18041499c  xor     edx, edx; int
0x18041499e  mov     rcx, rsi; this
0x1804149a1  call    ?UpdateInterval@CDoc@@QEAAXJ@Z; CDoc::UpdateInterval(long)
0x1804149a6  mov     rdx, [r15+0D8h]
0x1804149ad  test    byte ptr [rdx+8], 8
0x1804149b1  jnz     short loc_1804149BD
0x1804149b3  cmp     byte ptr [r14+0F8h], 0
0x1804149bb  jz      short loc_1804149EA
0x1804149bd  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1804149c1  test    rdx, rdx
0x1804149c4  jz      short loc_1804149D6
0x1804149c6  mov     rcx, [r14+0D8h]
0x1804149cd  add     rcx, 10h; this
0x1804149d1  call    ?Set@CSmartBstr@@QEAAJPEBG@Z; CSmartBstr::Set(ushort const *)
0x1804149d6  mov     rax, [r15+0D8h]
0x1804149dd  mov     rcx, [r14+0D8h]
0x1804149e4  mov     eax, [rax+1Ch]
0x1804149e7  mov     [rcx+1Ch], eax
0x1804149ea  mov     rcx, r15; this
0x1804149ed  call    ?HasEditRouter@CMarkup@@QEAAHXZ; CMarkup::HasEditRouter(void)
0x1804149f2  test    eax, eax
0x1804149f4  jz      short loc_180414A06
0x1804149f6  mov     rcx, r15; this
0x1804149f9  call    ?GetEditRouter@CMarkup@@QEAAPEAVCEditRouter@@XZ; CMarkup::GetEditRouter(void)
0x1804149fe  mov     rcx, rax; this
0x180414a01  call    ?Passivate@CEditRouter@@QEAAXXZ; CEditRouter::Passivate(void)
0x180414a06  test    ebx, ebx
0x180414a08  jnz     short loc_180414A7C
0x180414a0a  mov     rcx, r15; this
0x180414a0d  call    ?GetParentMarkup@CMarkup@@QEBAPEAV1@XZ; CMarkup::GetParentMarkup(void)
0x180414a12  test    rax, rax
0x180414a15  jz      short loc_180414A7C
0x180414a17  mov     rax, [r15]
0x180414a1a  lea     rcx, __vtguard
0x180414a21  mov     [rbp+3Fh+arg_8], 0
0x180414a29  cmp     [rax+3D8h], rcx
0x180414a30  jnz     loc_180415A19
0x180414a36  mov     rax, [rax+470h]
0x180414a3d  lea     r8, [rbp+3Fh+arg_8]
0x180414a41  lea     rdx, IID_IUnknown
0x180414a48  mov     rcx, r15
0x180414a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180414a50  mov     r8, [rbp+3Fh+arg_8]
0x180414a54  lea     edx, [rbx+0Fh]
0x180414a57  xor     r9d, r9d
0x180414a5a  mov     [rsp+130h+var_110], 0
0x180414a63  mov     rcx, rsi
0x180414a66  call    ?NotifySelection@CDoc@@QEAAJW4_EDITOR_NOTIFICATION@@PEAUIUnknown@@KPEAVCElement@@@Z; CDoc::NotifySelection(_EDITOR_NOTIFICATION,IUnknown *,ulong,CElement *)
0x180414a6b  mov     rcx, [rbp+3Fh+arg_8]; struct IUnknown *
0x180414a6f  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180414a74  xor     eax, eax
0x180414a76  mov     [rsp+130h+var_F0], eax
0x180414a7a  jmp     short loc_180414AE1
  ... truncated ...
```
