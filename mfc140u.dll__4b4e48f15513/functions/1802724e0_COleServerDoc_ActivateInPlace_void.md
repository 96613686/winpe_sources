# COleServerDoc::ActivateInPlace(void)

- ea: `0x1802724e0`
- end: `0x180272c1b`
- name: `?ActivateInPlace@COleServerDoc@@QEAAHXZ`
- size: `1851`
- prototype: `int __fastcall(COleServerDoc *this)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x1802651b0`
- `0x180275b30`

## callees

- `0x1800027e0`
- `0x18000e0e0`
- `0x180139860`
- `0x1801d63b0`
- `0x180231d70`
- `0x18025fb10`
- `0x180267fe0`
- `0x1802696a0`
- `0x1802724e0`
- `0x180278450`
- `0x180278600`
- `0x180296d00`
- `0x180296d80`
- `0x1802a9ea0`
- `0x1802b6730`
- `0x1802b67c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetDC` at `0x1802727aa`
- `USER32!GetDC` at `0x1802727aa`
- `USER32!ReleaseDC` at `0x1802727cc`
- `USER32!ReleaseDC` at `0x1802727cc`
- `USER32!WindowFromDC` at `0x1802727bc`
- `USER32!WindowFromDC` at `0x1802727bc`
- `USER32!IsWindowVisible` at `0x180272578`
- `USER32!IsWindowVisible` at `0x180272578`
- `USER32!CopyRect` at `0x1802728a2`
- `USER32!CopyRect` at `0x1802728b3`
- `USER32!CopyRect` at `0x1802728a2`
- `USER32!CopyRect` at `0x1802728b3`
- `USER32!IsRectEmpty` at `0x18027288d`
- `USER32!IsRectEmpty` at `0x1802728e6`
- `USER32!IsRectEmpty` at `0x18027288d`
- `USER32!IsRectEmpty` at `0x1802728e6`
- `USER32!UpdateWindow` at `0x180272a64`
- `USER32!UpdateWindow` at `0x180272a64`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall COleServerDoc::ActivateInPlace(COleServerDoc *this)
{
  IOleClientSite *m_lpClientSite; // rcx
  COleIPFrameWnd *m_pInPlaceFrame; // rax
  CFrameWnd *FirstFrame; // rax
  HWND__ *v6; // rdi
  ATL::CStringData *v7; // r15
  ATL::CStringData *v8; // rbx
  HWND__ *v9; // rdx
  wchar_t *m_pszData; // rdi
  IUnknown *Interface; // rax
  IUnknown *v12; // r14
  ATL::IAtlStringMgr *pStringMgr; // rcx
  ATL::CStringData *v14; // rdx
  CWnd *v15; // rax
  COleIPFrameWnd *v16; // rax
  COleIPFrameWnd *v17; // r15
  IUnknown *v18; // rcx
  IOleInPlaceUIWindow **p_m_lpDocFrame; // r13
  wchar_t *v20; // r12
  HDC DC; // rax
  HWND v22; // rdi
  wchar_t *v23; // rax
  wchar_t *v24; // rax
  BOOL v25; // eax
  const RECT *p_right; // rdx
  BOOL v27; // eax
  const tagRECT *v28; // rdx
  IUnknown *v29; // rdi
  IOleInPlaceUIWindow **p_m_lpFrame; // r12
  wchar_t *v31; // rbx
  COleIPFrameWnd *v32; // rdx
  HWND__ *v33; // rdx
  wchar_t *v34; // rdx
  wchar_t *v35; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strFileType; // [rsp+48h] [rbp-29h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTitle; // [rsp+50h] [rbp-21h] BYREF
  HWND__ *hWndDocument; // [rsp+58h] [rbp-19h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTitleW; // [rsp+60h] [rbp-11h] BYREF
  ATL::CSimpleStringT<wchar_t,1> v40; // [rsp+68h] [rbp-9h] BYREF
  wchar_t *rglpsz; // [rsp+70h] [rbp-1h] BYREF
  tagRECT rcClipRect; // [rsp+78h] [rbp+7h] BYREF
  tagRECT rcPosRect; // [rsp+88h] [rbp+17h] BYREF

  m_lpClientSite = this->m_lpClientSite;
  if ( !m_lpClientSite )
    return 0;
  m_pInPlaceFrame = this->m_pInPlaceFrame;
  if ( m_pInPlaceFrame )
  {
    if ( m_pInPlaceFrame->m_bUIActive )
    {
      m_lpClientSite->ShowObject(m_lpClientSite);
      return 1;
    }
    this->OnDeactivate(this);
  }
  FirstFrame = COleDocument::GetFirstFrame(this);
  if ( !FirstFrame )
    AfxThrowInvalidArgException();
  if ( IsWindowVisible(FirstFrame->m_hWnd) )
    return 0;
  strTitle.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  v6 = (HWND__ *)&afxStringManager.GetNilString(&afxStringManager)[1];
  hWndDocument = v6;
  v7 = afxStringManager.GetNilString(&afxStringManager);
  v8 = v7 + 1;
  v40.m_pszData = (wchar_t *)&v7[1];
  if ( !this->GetFileTypeString(this, &strTitle) )
  {
    if ( _InterlockedDecrement(&v7->nRefs) <= 0 )
      v7->pStringMgr->Free(v7->pStringMgr, v7);
    v9 = v6 - 6;
    goto LABEL_61;
  }
  m_pszData = strTitle.m_pszData;
  rglpsz = (wchar_t *)AfxGetModuleState()->m_lpszCurrentAppName;
  *(_QWORD *)&rcClipRect.left = m_pszData;
  AfxFormatStrings(
    (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&hWndDocument,
    0xE005u,
    (const wchar_t *const *)&rglpsz,
    2);
  Interface = _AfxQueryInterface(this->m_lpClientSite, &IID_IOleInPlaceSite);
  v12 = Interface;
  if ( !Interface )
  {
    if ( _InterlockedDecrement(&v7->nRefs) <= 0 )
    {
      pStringMgr = v7->pStringMgr;
      v14 = v7;
LABEL_59:
      pStringMgr->Free(pStringMgr, v14);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  if ( Interface->__vftable[1].Release(Interface)
    || ((unsigned int (__fastcall *)(IUnknown *))v12->__vftable[2].QueryInterface)(v12) )
  {
$ReleaseAndFail_0:
    v12->Release(v12);
    v14 = v8 - 1;
    if ( _InterlockedDecrement(&v8[-1].nRefs) <= 0 )
    {
      pStringMgr = v14->pStringMgr;
      goto LABEL_59;
    }
LABEL_60:
    v9 = hWndDocument - 6;
LABEL_61:
    if ( _InterlockedDecrement((volatile signed __int32 *)v9 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
    v35 = strTitle.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)strTitle.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
    return 0;
  }
  ((void (__fastcall *)(IUnknown *, ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *))v12->__vftable[1].QueryInterface)(
    v12,
    &strFileType);
  v15 = CWnd::FromHandle((HWND__ *)strFileType.m_pszData);
  v16 = this->CreateInPlaceFrame(this, v15);
  v17 = v16;
  v18 = v12;
  if ( !v16 )
  {
LABEL_56:
    v12->__vftable[3].Release(v18);
    goto $ReleaseAndFail_0;
  }
  this->m_pInPlaceFrame = v16;
  if ( v12->__vftable[2].AddRef(v12) )
  {
$DestroyFrameAndFail_0:
    if ( !this->m_pInPlaceFrame )
      goto $ReleaseAndFail_0;
    this->DestroyInPlaceFrame(this, v17);
    this->m_pInPlaceFrame = 0;
    v18 = v12;
    goto LABEL_56;
  }
  p_m_lpDocFrame = &v17->m_lpDocFrame;
  if ( ((unsigned int (__fastcall *)(IUnknown *, IOleInPlaceFrame **, IOleInPlaceUIWindow **, int *, int *, tagOIFI *))v12->__vftable[2].Release)(
         v12,
         &v17->m_lpFrame,
         &v17->m_lpDocFrame,
         &rcPosRect.right,
         &rcClipRect.right,
         &v17->m_frameInfo)
    || !v17->BuildSharedMenu(v17) )
  {
    goto $DeactivateUIAndFail_0;
  }
  v17->m_lpFrame->GetWindow(v17->m_lpFrame, (HWND__ **)&strFileType);
  v20 = strFileType.m_pszData;
  if ( (unsigned __int64)strFileType.m_pszData <= 0xFFFF )
  {
    DC = GetDC((HWND)strFileType.m_pszData);
    strTitleW.m_pszData = (wchar_t *)DC;
    if ( DC )
    {
      v22 = WindowFromDC(DC);
      ReleaseDC((HWND)v20, (HDC)strTitleW.m_pszData);
      if ( v22 )
        v20 = (wchar_t *)v22;
    }
  }
  strFileType.m_pszData = v20;
  v23 = (wchar_t *)operator new(0x1E0u);
  strTitleW.m_pszData = v23;
  if ( v23 )
    COleCntrFrameWnd::COleCntrFrameWnd((COleCntrFrameWnd *)v23, v17);
  v17->m_pMainFrame = (COleCntrFrameWnd *)v23;
  CWnd::Attach((CWnd *)v23, (HWND__ *)strFileType.m_pszData);
  if ( *p_m_lpDocFrame )
  {
    (*p_m_lpDocFrame)->GetWindow(*p_m_lpDocFrame, (HWND__ **)&strTitleW);
    if ( strTitleW.m_pszData == strFileType.m_pszData )
    {
      if ( *p_m_lpDocFrame )
        (*p_m_lpDocFrame)->Release(*p_m_lpDocFrame);
      *p_m_lpDocFrame = 0;
    }
    else
    {
      v24 = (wchar_t *)operator new(0x1E0u);
      rglpsz = v24;
      if ( v24 )
        COleCntrFrameWnd::COleCntrFrameWnd((COleCntrFrameWnd *)v24, v17);
      v17->m_pDocFrame = (COleCntrFrameWnd *)v24;
      CWnd::Attach((CWnd *)v24, (HWND__ *)strTitleW.m_pszData);
    }
  }
  v25 = IsRectEmpty((const RECT *)&rcPosRect.right);
  p_right = (const RECT *)&rcClipRect.right;
  if ( !v25 )
    p_right = (const RECT *)&rcPosRect.right;
  CopyRect(&v17->m_rectPos, p_right);
  CopyRect(&v17->m_rectClip, (const RECT *)&rcClipRect.right);
  if ( !v17->OnCreateControlBars(v17, v17->m_pMainFrame, v17->m_pDocFrame) )
  {
$DeactivateUIAndFail_0:
    ((void (__fastcall *)(IUnknown *, _QWORD))v12->__vftable[3].AddRef)(v12, 0);
    goto $DestroyFrameAndFail_0;
  }
  v27 = IsRectEmpty((const RECT *)&rcPosRect.right);
  v28 = (const tagRECT *)&rcClipRect.right;
  if ( !v27 )
    v28 = (const tagRECT *)&rcPosRect.right;
  this->OnSetItemRects(this, v28, (const tagRECT *)&rcClipRect.right);
  v29 = CCmdTarget::GetInterface(this, &IID_IOleInPlaceActiveObject);
  ATL::CSimpleStringT<wchar_t,1>::operator=(&v40, (const ATL::CSimpleStringT<wchar_t,0> *)&hWndDocument);
  p_m_lpFrame = &v17->m_lpFrame;
  v31 = v40.m_pszData;
  v17->m_lpFrame->SetActiveObject(v17->m_lpFrame, (IOleInPlaceActiveObject *)v29, v40.m_pszData);
  if ( *p_m_lpDocFrame )
    (*p_m_lpDocFrame)->SetActiveObject(*p_m_lpDocFrame, (IOleInPlaceActiveObject *)v29, v31);
  this->OnShowControlBars(this, this->m_pInPlaceFrame->m_pMainFrame, 1);
  v32 = this->m_pInPlaceFrame;
  if ( v32->m_lpDocFrame )
    this->OnShowControlBars(this, v32->m_pDocFrame, 1);
  CFrameWnd::ShowOwnedWindows(this->m_pInPlaceFrame, 1);
  this->OnResizeBorder(this, 0, *p_m_lpFrame, 1);
  if ( *p_m_lpDocFrame )
    this->OnResizeBorder(this, 0, *p_m_lpDocFrame, 0);
  ((void (__fastcall *)(IOleInPlaceUIWindow *, HMENU__ *, void *, HWND__ *))(*p_m_lpFrame)->__vftable[1].AddRef)(
    *p_m_lpFrame,
    v17->m_hSharedMenu,
    v17->m_hOleMenu,
    v17->m_hWnd);
  this->m_lpClientSite->ShowObject(this->m_lpClientSite);
  CWnd::ShowWindow(v17, 5);
  CWnd::SetFocus(v17);
  UpdateWindow(v17->m_hWnd);
  COleLinkingDoc::UpdateVisibleLock(this, 1, 0);
  this->OnFrameWindowActivate(this, 1);
  v17->m_bUIActive = 1;
  v12->Release(v12);
  if ( _InterlockedDecrement((volatile signed __int32 *)v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 - 3) + 8LL))(*((_QWORD *)v31 - 3));
  v33 = hWndDocument - 6;
  if ( _InterlockedDecrement((volatile signed __int32 *)hWndDocument - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 8LL))(*(_QWORD *)v33);
  v34 = strTitle.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strTitle.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 8LL))(*(_QWORD *)v34);
  return 1;
}

```

## disassembly

```asm
0x1802724e0  mov     rax, rsp
0x1802724e3  mov     [rax+10h], rbx
0x1802724e7  mov     [rax+18h], rsi
0x1802724eb  mov     [rax+20h], rdi
0x1802724ef  push    rbp
0x1802724f0  push    r12
0x1802724f2  push    r13
0x1802724f4  push    r14
0x1802724f6  push    r15
0x1802724f8  lea     rbp, [rax-5Fh]
0x1802724fc  sub     rsp, 0A0h
0x180272503  mov     rax, cs:__security_cookie
0x18027250a  xor     rax, rsp
0x18027250d  mov     [rbp+57h+var_28], rax
0x180272511  mov     rsi, this
0x180272514  mov     this, [this+230h]
0x18027251b  test    this, this
0x18027251e  jz      loc_180272BE6
0x180272524  mov     rax, [rsi+250h]
0x18027252b  test    rax, rax
0x18027252e  jz      short loc_180272563
0x180272530  cmp     dword ptr [rax+1D8h], 0
0x180272537  jz      short loc_180272550
0x180272539  mov     rax, [this]
0x18027253c  mov     rax, [rax+30h]
0x180272540  call    cs:__guard_dispatch_icall_fptr
0x180272546  mov     eax, 1
0x18027254b  jmp     loc_180272BE8
0x180272550  mov     rax, [rsi]
0x180272553  mov     this, rsi
0x180272556  mov     rax, [rax+2E0h]
0x18027255d  call    cs:__guard_dispatch_icall_fptr
0x180272563  mov     this, rsi; this
0x180272566  call    ?GetFirstFrame@COleDocument@@QEAAPEAVCFrameWnd@@XZ; COleDocument::GetFirstFrame(void)
0x18027256b  test    rax, rax
0x18027256e  jz      loc_180272C15
0x180272574  mov     this, [rax+40h]; hWnd
0x180272578  call    cs:__imp_IsWindowVisible
0x18027257e  test    eax, eax
0x180272580  jnz     loc_180272BE6
0x180272586  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18027258d  lea     rbx, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180272594  mov     this, rbx
0x180272597  mov     rax, [rax+18h]
0x18027259b  call    cs:__guard_dispatch_icall_fptr
0x1802725a1  add     rax, 18h
0x1802725a5  mov     [rbp+57h+strTitle.m_pszData], rax
0x1802725a9  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802725b0  mov     this, rbx
0x1802725b3  mov     rax, [rax+18h]
0x1802725b7  call    cs:__guard_dispatch_icall_fptr
0x1802725bd  lea     rdi, [rax+18h]
0x1802725c1  mov     [rbp+57h+hWndDocument], rdi
0x1802725c5  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802725cc  mov     this, rbx
0x1802725cf  mov     rax, [rax+18h]
0x1802725d3  call    cs:__guard_dispatch_icall_fptr
0x1802725d9  mov     r15, rax
0x1802725dc  lea     rbx, [rax+18h]
0x1802725e0  mov     [rbp+57h+var_60.m_pszData], rbx
0x1802725e4  mov     rax, [rsi]
0x1802725e7  lea     rdx, [rbp+57h+strTitle]
0x1802725eb  mov     this, rsi
0x1802725ee  mov     rax, [rax+330h]
0x1802725f5  call    cs:__guard_dispatch_icall_fptr
0x1802725fb  test    eax, eax
0x1802725fd  jnz     short loc_18027262D
0x1802725ff  or      ebx, 0FFFFFFFFh
0x180272602  mov     eax, ebx
0x180272604  lock xadd [r15+10h], eax
0x18027260a  add     eax, ebx
0x18027260c  test    eax, eax
0x18027260e  jg      short loc_180272624
0x180272610  mov     this, [r15]
0x180272613  mov     rax, [this]
0x180272616  mov     rdx, r15
0x180272619  mov     rax, [rax+8]
0x18027261d  call    cs:__guard_dispatch_icall_fptr
0x180272623  nop
0x180272624  lea     rdx, [rdi-18h]
0x180272628  jmp     loc_180272BA3
0x18027262d  mov     rdi, [rbp+57h+strTitle.m_pszData]
0x180272631  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180272636  mov     this, [rax+20h]
0x18027263a  mov     [rbp+57h+rglpsz], this
0x18027263e  mov     qword ptr [rbp+57h+rcClipRect.left], rdi
0x180272642  mov     r9d, 2; nString
0x180272648  lea     r8, [rbp+57h+rglpsz]; rglpsz
0x18027264c  mov     edx, 0E005h; nIDS
0x180272651  lea     this, [rbp+57h+hWndDocument]; rString
0x180272655  call    ?AfxFormatStrings@@YAXAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@IPEBQEB_WH@Z; AfxFormatStrings(ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,uint,wchar_t const * const *,int)
0x18027265a  lea     rdx, IID_IOleInPlaceSite; iid
0x180272661  mov     this, [rsi+230h]; lpUnknown
0x180272668  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x18027266d  mov     r14, rax
0x180272670  test    rax, rax
0x180272673  jnz     short loc_180272695
0x180272675  or      ebx, 0FFFFFFFFh
0x180272678  mov     eax, ebx
0x18027267a  lock xadd [r15+10h], eax
0x180272680  add     eax, ebx
0x180272682  test    eax, eax
0x180272684  jg      loc_180272B9B
0x18027268a  mov     this, [r15]
0x18027268d  mov     rdx, r15
0x180272690  jmp     loc_180272B8D
0x180272695  mov     rax, [rax]
0x180272698  mov     this, r14
0x18027269b  mov     rax, [rax+28h]
0x18027269f  call    cs:__guard_dispatch_icall_fptr
0x1802726a5  test    eax, eax
0x1802726a7  jnz     $ReleaseAndFail_0
0x1802726ad  mov     rax, [r14]
0x1802726b0  mov     this, r14
0x1802726b3  mov     rax, [rax+30h]
0x1802726b7  call    cs:__guard_dispatch_icall_fptr
0x1802726bd  test    eax, eax
0x1802726bf  jnz     $ReleaseAndFail_0
0x1802726c5  mov     rax, [r14]
0x1802726c8  lea     rdx, [rbp+57h+strFileType]
0x1802726cc  mov     this, r14
0x1802726cf  mov     rax, [rax+18h]
0x1802726d3  call    cs:__guard_dispatch_icall_fptr
0x1802726d9  mov     this, [rbp+57h+strFileType.m_pszData]; hWnd
0x1802726dd  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1802726e2  mov     this, [rsi]
0x1802726e5  mov     r8, [this+318h]
0x1802726ec  mov     rdx, rax
0x1802726ef  mov     this, rsi
0x1802726f2  mov     rax, r8
0x1802726f5  call    cs:__guard_dispatch_icall_fptr
0x1802726fb  mov     r15, rax
0x1802726fe  mov     this, r14
0x180272701  test    rax, rax
0x180272704  jz      loc_180272B58
0x18027270a  mov     [rsi+250h], rax
0x180272711  mov     rax, [r14]
0x180272714  mov     rax, [rax+38h]
0x180272718  call    cs:__guard_dispatch_icall_fptr
0x18027271e  test    eax, eax
0x180272720  jnz     $DestroyFrameAndFail_0
0x180272726  mov     rax, [r14]
0x180272729  lea     r13, [r15+208h]
0x180272730  lea     rdi, [r15+200h]
0x180272737  lea     this, [r15+1E0h]
0x18027273e  mov     [rsp+0C0h+var_98], this
0x180272743  lea     this, [rbp+57h+rcClipRect.right]
0x180272747  mov     [rsp+0C0h+var_A0], this
0x18027274c  lea     r9, [rbp+57h+rcPosRect.right]
0x180272750  mov     r8, r13
0x180272753  mov     rdx, rdi
0x180272756  mov     this, r14
0x180272759  mov     rax, [rax+40h]
0x18027275d  call    cs:__guard_dispatch_icall_fptr
0x180272763  test    eax, eax
0x180272765  jnz     $DeactivateUIAndFail_0
0x18027276b  mov     rax, [r15]
0x18027276e  mov     this, r15
0x180272771  mov     rax, [rax+3B0h]
0x180272778  call    cs:__guard_dispatch_icall_fptr
0x18027277e  test    eax, eax
0x180272780  jz      $DeactivateUIAndFail_0
0x180272786  mov     this, [rdi]
0x180272789  mov     rax, [this]
0x18027278c  lea     rdx, [rbp+57h+strFileType]
0x180272790  mov     rax, [rax+18h]
0x180272794  call    cs:__guard_dispatch_icall_fptr
0x18027279a  mov     r12, [rbp+57h+strFileType.m_pszData]
0x18027279e  cmp     r12, 0FFFFh
0x1802727a5  ja      short loc_1802727D9
0x1802727a7  mov     this, r12; hWnd
0x1802727aa  call    cs:__imp_GetDC
0x1802727b0  mov     [rbp+57h+strTitleW.m_pszData], rax
0x1802727b4  test    rax, rax
0x1802727b7  jz      short loc_1802727D9
0x1802727b9  mov     this, rax; hDC
0x1802727bc  call    cs:__imp_WindowFromDC
0x1802727c2  mov     rdi, rax
0x1802727c5  mov     rdx, [rbp+57h+strTitleW.m_pszData]; hDC
0x1802727c9  mov     this, r12; hWnd
0x1802727cc  call    cs:__imp_ReleaseDC
0x1802727d2  test    rdi, rdi
0x1802727d5  cmovnz  r12, rdi
0x1802727d9  mov     [rbp+57h+strFileType.m_pszData], r12
0x1802727dd  mov     edi, 1E0h
0x1802727e2  mov     ecx, edi; nSize
0x1802727e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802727e9  mov     [rbp+57h+strTitleW.m_pszData], rax
0x1802727ed  test    rax, rax
0x1802727f0  jz      short loc_1802727FE
0x1802727f2  mov     rdx, r15; pInPlaceFrame
0x1802727f5  mov     this, rax; this
0x1802727f8  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x1802727fd  nop
0x1802727fe  mov     [r15+210h], rax
0x180272805  mov     rdx, [rbp+57h+strFileType.m_pszData]; hWndNew
0x180272809  mov     this, rax; this
0x18027280c  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x180272811  mov     this, [r13+0]
0x180272815  test    this, this
0x180272818  jz      short loc_180272882
0x18027281a  mov     rax, [this]
0x18027281d  lea     rdx, [rbp+57h+strTitleW]
0x180272821  mov     rax, [rax+18h]
0x180272825  call    cs:__guard_dispatch_icall_fptr
0x18027282b  mov     rax, [rbp+57h+strFileType.m_pszData]
0x18027282f  cmp     [rbp+57h+strTitleW.m_pszData], rax
0x180272833  jz      short loc_180272867
0x180272835  mov     this, rdi; nSize
0x180272838  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18027283d  mov     [rbp+57h+rglpsz], rax
0x180272841  test    rax, rax
0x180272844  jz      short loc_180272852
0x180272846  mov     rdx, r15; pInPlaceFrame
0x180272849  mov     this, rax; this
0x18027284c  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x180272851  nop
0x180272852  mov     [r15+218h], rax
0x180272859  mov     rdx, [rbp+57h+strTitleW.m_pszData]; hWndNew
0x18027285d  mov     this, rax; this
0x180272860  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x180272865  jmp     short loc_180272882
0x180272867  mov     this, [r13+0]
0x18027286b  test    this, this
0x18027286e  jz      short loc_18027287D
0x180272870  mov     rax, [this]
0x180272873  mov     rax, [rax+10h]
0x180272877  call    cs:__guard_dispatch_icall_fptr
0x18027287d  and     qword ptr [r13+0], 0
0x180272882  lea     rdi, [r15+248h]
0x180272889  lea     this, [rbp+57h+rcPosRect.right]; lprc
0x18027288d  call    cs:__imp_IsRectEmpty
0x180272893  mov     this, rdi; lprcDst
0x180272896  test    eax, eax
0x180272898  lea     rdx, [rbp+57h+rcClipRect.right]
0x18027289c  jnz     short loc_1802728A2
0x18027289e  lea     rdx, [rbp+57h+rcPosRect.right]; lprcSrc
0x1802728a2  call    cs:__imp_CopyRect
0x1802728a8  lea     this, [r15+258h]; lprcDst
0x1802728af  lea     rdx, [rbp+57h+rcClipRect.right]; lprcSrc
0x1802728b3  call    cs:__imp_CopyRect
0x1802728b9  mov     rax, [r15]
0x1802728bc  mov     r8, [r15+218h]
0x1802728c3  mov     rdx, [r15+210h]
0x1802728ca  mov     this, r15
0x1802728cd  mov     rax, [rax+390h]
0x1802728d4  call    cs:__guard_dispatch_icall_fptr
0x1802728da  test    eax, eax
0x1802728dc  jz      $DeactivateUIAndFail_0
0x1802728e2  lea     this, [rbp+57h+rcPosRect.right]; lprc
0x1802728e6  call    cs:__imp_IsRectEmpty
0x1802728ec  mov     this, [rsi]
0x1802728ef  mov     r9, [this+300h]
0x1802728f6  lea     r8, [rbp+57h+rcClipRect.right]
0x1802728fa  mov     this, rsi
0x1802728fd  test    eax, eax
0x1802728ff  mov     rax, r9
0x180272902  lea     rdx, [rbp+57h+rcClipRect.right]
0x180272906  jnz     short loc_18027290C
0x180272908  lea     rdx, [rbp+57h+rcPosRect.right]
0x18027290c  call    cs:__guard_dispatch_icall_fptr
0x180272912  lea     rdx, IID_IOleInPlaceActiveObject; iid
0x180272919  mov     this, rsi; this
0x18027291c  call    ?GetInterface@CCmdTarget@@QEAAPEAUIUnknown@@PEBX@Z; CCmdTarget::GetInterface(void const *)
0x180272921  mov     rdi, rax
0x180272924  lea     rdx, [rbp+57h+hWndDocument]; strSrc
0x180272928  lea     this, [rbp+57h+var_60]; this
0x18027292c  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x180272931  lea     r12, [r15+200h]
0x180272938  mov     r9, [r12]
0x18027293c  mov     this, [r9]
0x18027293f  mov     rax, [this+40h]
0x180272943  mov     rbx, [rbp+57h+var_60.m_pszData]
0x180272947  mov     r8, rbx
0x18027294a  mov     rdx, rdi
0x18027294d  mov     this, r9
0x180272950  call    cs:__guard_dispatch_icall_fptr
0x180272956  mov     this, [r13+0]
0x18027295a  test    this, this
0x18027295d  jz      short loc_180272972
0x18027295f  mov     rax, [this]
0x180272962  mov     r8, rbx
0x180272965  mov     rdx, rdi
0x180272968  mov     rax, [rax+40h]
0x18027296c  call    cs:__guard_dispatch_icall_fptr
0x180272972  mov     rax, [rsi]
0x180272975  mov     rdx, [rsi+250h]
0x18027297c  mov     edi, 1
0x180272981  mov     r8d, edi
0x180272984  mov     rdx, [rdx+210h]
0x18027298b  mov     this, rsi
0x18027298e  mov     rax, [rax+2F8h]
0x180272995  call    cs:__guard_dispatch_icall_fptr
0x18027299b  mov     rdx, [rsi+250h]
0x1802729a2  cmp     qword ptr [rdx+208h], 0
0x1802729aa  jz      short loc_1802729C9
0x1802729ac  mov     rax, [rsi]
0x1802729af  mov     r8d, edi
0x1802729b2  mov     rdx, [rdx+218h]
0x1802729b9  mov     this, rsi
  ... truncated ...
```
