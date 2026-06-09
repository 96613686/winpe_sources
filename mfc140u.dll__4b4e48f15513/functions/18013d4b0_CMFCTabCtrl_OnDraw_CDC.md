# CMFCTabCtrl::OnDraw(CDC *)

- ea: `0x18013d4b0`
- end: `0x18013e215`
- name: `?OnDraw@CMFCTabCtrl@@UEAAXPEAVCDC@@@Z`
- size: `3429`
- prototype: `void __fastcall(CMFCTabCtrl *this, CDC *pDC)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180009844`
- `0x18001d090`
- `0x18006cab0`
- `0x18013d4b0`
- `0x180231d70`
- `0x1802af110`
- `0x1802af260`
- `0x1802af8a0`
- `0x1802af990`
- `0x1802afbb0`
- `0x1802afc20`
- `0x1802b09d0`
- `0x1802b0a90`
- `0x1802b2690`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!FrameRect` at `0x18013d6fe`
- `USER32!FrameRect` at `0x18013d6fe`
- `USER32!GetClientRect` at `0x18013d557`
- `USER32!GetClientRect` at `0x18013d557`
- `USER32!FillRect` at `0x18013d677`
- `USER32!FillRect` at `0x18013e05f`
- `USER32!FillRect` at `0x18013d677`
- `USER32!FillRect` at `0x18013e05f`
- `USER32!IsRectEmpty` at `0x18013e03e`
- `USER32!IsRectEmpty` at `0x18013e125`
- `USER32!IsRectEmpty` at `0x18013e03e`
- `USER32!IsRectEmpty` at `0x18013e125`
- `USER32!InflateRect` at `0x18013d76d`
- `USER32!InflateRect` at `0x18013d9d2`
- `USER32!InflateRect` at `0x18013d9f7`
- `USER32!InflateRect` at `0x18013db43`
- `USER32!InflateRect` at `0x18013db7f`
- `USER32!InflateRect` at `0x18013dcb9`
- `USER32!InflateRect` at `0x18013e08c`
- `USER32!InflateRect` at `0x18013d76d`
- `USER32!InflateRect` at `0x18013d9d2`
- `USER32!InflateRect` at `0x18013d9f7`
- `USER32!InflateRect` at `0x18013db43`
- `USER32!InflateRect` at `0x18013db7f`
- `USER32!InflateRect` at `0x18013dcb9`
- `USER32!InflateRect` at `0x18013e08c`
- `GDI32!PatBlt` at `0x18013d7c1`
- `GDI32!PatBlt` at `0x18013d7e3`
- `GDI32!PatBlt` at `0x18013d80c`
- `GDI32!PatBlt` at `0x18013d831`
- `GDI32!PatBlt` at `0x18013d87e`
- `GDI32!PatBlt` at `0x18013da3f`
- `GDI32!PatBlt` at `0x18013da61`
- `GDI32!PatBlt` at `0x18013da87`
- `GDI32!PatBlt` at `0x18013daac`
- `GDI32!PatBlt` at `0x18013daea`
- `GDI32!PatBlt` at `0x18013d7c1`
- `GDI32!PatBlt` at `0x18013d7e3`
- `GDI32!PatBlt` at `0x18013d80c`
- `GDI32!PatBlt` at `0x18013d831`
- `GDI32!PatBlt` at `0x18013d87e`
- `GDI32!PatBlt` at `0x18013da3f`
- `GDI32!PatBlt` at `0x18013da61`
- `GDI32!PatBlt` at `0x18013da87`
- `GDI32!PatBlt` at `0x18013daac`
- `GDI32!PatBlt` at `0x18013daea`
- `GDI32!CreateRectRgnIndirect` at `0x18013dcd4`
- `GDI32!CreateRectRgnIndirect` at `0x18013dcd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMFCTabCtrl::OnDraw(CMFCTabCtrl *this, CDC *pDC)
{
  unsigned int v4; // esi
  CMFCVisualManager *Instance; // rax
  int h; // r15d
  int *p_top; // rbx
  int *p_bottom; // r13
  CMFCVisualManager *v9; // r10
  int (__fastcall *OnEraseTabsFrame)(CMFCVisualManager *, CDC *, CRect, const CMFCBaseTabCtrl *); // rax
  int v11; // eax
  HBRUSH m_hObject; // r8
  CMFCVisualManager *v13; // r10
  void (__fastcall *OnEraseTabsArea)(CMFCVisualManager *, CDC *, CRect, const CMFCBaseTabCtrl *); // rax
  CMFCBaseTabCtrl::Location m_location; // ecx
  HBRUSH v16; // r8
  CBrush *v17; // rax
  int *v18; // rax
  int v19; // r12d
  int m_bFlat; // edx
  int v21; // ebx
  int bottom; // r8d
  int top; // eax
  unsigned int v24; // r8d
  unsigned int v25; // r9d
  const tagRECT *p_rgn; // rdx
  int v27; // r12d
  int m_hObject_high; // ebx
  int v29; // r8d
  int v30; // r8d
  int v31; // eax
  CFont *(__fastcall *SelectObject)(CDC *, CFont *); // rbx
  CFont *v33; // r12
  unsigned int (__fastcall *SetTextColor)(CDC *, unsigned int); // rbx
  HRGN v35; // rax
  int v36; // ebx
  __int64 v37; // r15
  int v38; // ecx
  __int64 m_nSize; // rdx
  CMFCTabInfo *v40; // r12
  unsigned int (__fastcall *v41)(CDC *, unsigned int); // rbx
  __int64 m_iActiveTab; // rcx
  CMFCTabInfo *v43; // r15
  CFont *(__fastcall *v44)(CDC *, CFont *); // rbx
  unsigned int (__fastcall *v45)(CDC *, unsigned int); // rbx
  unsigned int v46; // eax
  int left; // ebx
  int v48; // edx
  int v49; // ebx
  unsigned int v50; // eax
  int v51; // r8d
  CFont *v52; // r15
  CFont *(__fastcall *v53)(CDC *, CFont *); // rbx
  HBRUSH v54; // r8
  int v55; // ebx
  int v56; // r8d
  CMFCVisualManager *v57; // r10
  void (__fastcall *OnDrawTabResizeBar)(CMFCVisualManager *, CDC *, CMFCBaseTabCtrl *, int, CRect, CBrush *, CPen *); // rax
  unsigned int clrDark; // [rsp+60h] [rbp-A0h] BYREF
  CPoint result; // [rsp+68h] [rbp-98h] BYREF
  CRgn rgn; // [rsp+70h] [rbp-90h] BYREF
  unsigned int clrHighlight; // [rsp+80h] [rbp-80h] BYREF
  CFont *pFont; // [rsp+88h] [rbp-78h] BYREF
  int y; // [rsp+90h] [rbp-70h]
  unsigned int clrDarkShadow; // [rsp+94h] [rbp-6Ch] BYREF
  CBrush *pbrFace; // [rsp+98h] [rbp-68h] BYREF
  unsigned int clrFace; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int clrBlack; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int clrLight; // [rsp+A8h] [rbp-58h] BYREF
  CPen penBlack; // [rsp+B0h] [rbp-50h] BYREF
  CPen penDark; // [rsp+C0h] [rbp-40h] BYREF
  CBrush *pbrBlack; // [rsp+D0h] [rbp-30h] BYREF
  CFont *v73; // [rsp+D8h] [rbp-28h]
  CPen penHiLight; // [rsp+E0h] [rbp-20h] BYREF
  CRect rectFrame; // [rsp+F0h] [rbp-10h] BYREF
  CRect rectClient; // [rsp+100h] [rbp+0h] BYREF
  CRect rectClip; // [rsp+110h] [rbp+10h] BYREF
  CRect rectTabSplitter; // [rsp+120h] [rbp+20h] BYREF

  v4 = 0;
  pbrFace = 0;
  pbrBlack = 0;
  Instance = CMFCVisualManager::GetInstance();
  Instance->GetTabFrameColors(
    Instance,
    this,
    &clrDark,
    &clrBlack,
    &clrHighlight,
    &clrFace,
    &clrDarkShadow,
    &clrLight,
    &pbrFace,
    &pbrBlack);
  rectClient = 0;
  GetClientRect(this->m_hWnd, &rectClient);
  v73 = CDC::SelectObject(pDC, (CFont *)pbrFace);
  if ( !v73 )
    AfxThrowInvalidArgException();
  CPen::CPen(&penDark, 0, 1, clrDark);
  CPen::CPen(&penBlack, 0, 1, clrBlack);
  CPen::CPen(&penHiLight, 0, 1, clrHighlight);
  pFont = CDC::SelectObject(pDC, (CFont *)&penDark);
  if ( !pFont )
LABEL_133:
    AfxThrowInvalidArgException();
  h = this->GetTabBorderSize(this);
  rgn = (CRgn)rectClient;
  p_top = &this->m_rectTabsArea.top;
  p_bottom = &this->m_rectTabsArea.bottom;
  if ( this->m_location )
    HIDWORD(rgn.m_hObject) = *p_bottom;
  else
    HIDWORD(rgn.__vftable) = *p_top;
  CDC::ExcludeClipRect(pDC, &this->m_rectWndArea);
  v9 = CMFCVisualManager::GetInstance();
  OnEraseTabsFrame = v9->OnEraseTabsFrame;
  rectClip = rectClient;
  v11 = ((__int64 (__fastcall *)(CMFCVisualManager *, CDC *, CRect *, CMFCTabCtrl *))OnEraseTabsFrame)(
          v9,
          pDC,
          &rectClip,
          this);
  result.x = v11;
  if ( !this->m_bDrawFrame && !v11 )
  {
    m_hObject = 0;
    if ( pbrFace )
      m_hObject = (HBRUSH)pbrFace->m_hObject;
    FillRect(pDC->m_hDC, &rectClient, m_hObject);
  }
  v13 = CMFCVisualManager::GetInstance();
  OnEraseTabsArea = v13->OnEraseTabsArea;
  rectClip = (CRect)rgn;
  ((void (__fastcall *)(CMFCVisualManager *, CDC *, CRect *, CMFCTabCtrl *))OnEraseTabsArea)(v13, pDC, &rectClip, this);
  rectFrame = rectClient;
  m_location = this->m_location;
  if ( !h )
  {
    if ( m_location )
      rectFrame.top = *p_bottom - 1;
    else
      rectFrame.bottom = *p_top + 1;
    v16 = 0;
    v17 = pbrBlack;
    if ( !this->m_bFlat )
      v17 = pbrFace;
    if ( v17 )
      v16 = (HBRUSH)v17->m_hObject;
    FrameRect(pDC->m_hDC, &rectFrame, v16);
    goto LABEL_69;
  }
  v18 = &this->m_rectTabsArea.bottom;
  if ( m_location == LOCATION_BOTTOM )
    v18 = &this->m_rectTabsArea.top;
  v19 = *v18;
  y = *v18;
  m_bFlat = this->m_bFlat;
  if ( !m_bFlat )
  {
    if ( m_location )
      rectFrame.top = *p_bottom;
    else
      rectFrame.bottom = *p_top;
  }
  if ( this->m_bFlatFrame )
  {
    rgn = (CRgn)rectFrame;
    if ( m_bFlat )
    {
      if ( m_location )
      {
        v21 = *p_bottom - 1;
        HIDWORD(rgn.__vftable) = v21;
LABEL_31:
        InflateRect(&rectFrame, -1, -1);
        if ( this->m_bDrawFrame
          && !result.x
          && rectFrame.right - rectFrame.left > 0
          && rectFrame.bottom - rectFrame.top > 0 )
        {
          PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.top, h, rectFrame.bottom - rectFrame.top, 0xF00021u);
          PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.top, rectFrame.right - rectFrame.left, h, 0xF00021u);
          PatBlt(pDC->m_hDC, rectFrame.right - h - 1, rectFrame.top, h + 1, rectFrame.bottom - rectFrame.top, 0xF00021u);
          PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.bottom - h, rectFrame.right - rectFrame.left, h, 0xF00021u);
          if ( this->m_location )
          {
            top = this->m_rectWndArea.top;
            bottom = rectFrame.top;
          }
          else
          {
            bottom = this->m_rectWndArea.bottom;
            top = rectFrame.bottom;
          }
          PatBlt(pDC->m_hDC, rectFrame.left, bottom, rectFrame.right - rectFrame.left, top - bottom, 0xF00021u);
          v19 = y;
        }
        if ( this->m_bFlat )
        {
          CDC::SelectObject(pDC, (CFont *)&penBlack);
          CDC::MoveTo(pDC, &result, h + rectFrame.left, v19);
          CDC::LineTo(pDC, rectFrame.right - h, v19);
        }
        CDC::Draw3dRect(pDC, (const tagRECT *)&rgn, clrFace, clrFace);
        if ( !this->GetTabsHeight(this) )
        {
          v24 = clrFace;
          v25 = clrFace;
          p_rgn = (const tagRECT *)&rgn;
LABEL_67:
          CDC::Draw3dRect(pDC, p_rgn, v24, v25);
          goto LABEL_69;
        }
        if ( this->m_bDrawFrame )
          CDC::Draw3dRect(pDC, (const tagRECT *)&rgn, clrDark, clrDark);
        if ( !this->m_bIsOneNoteStyle )
        {
          v27 = LODWORD(rgn.m_hObject) - 1 - h;
          if ( this->m_bDrawFrame )
            v27 = LODWORD(rgn.m_hObject) - 1;
          if ( this->m_location )
          {
            CDC::SelectObject(pDC, (CFont *)&penHiLight);
            CDC::MoveTo(pDC, &result, (int)rgn.__vftable, v21);
            v29 = v21;
          }
          else
          {
            CDC::SelectObject(pDC, (CFont *)&penBlack);
            m_hObject_high = HIDWORD(rgn.m_hObject);
            CDC::MoveTo(pDC, &result, (int)rgn.__vftable, HIDWORD(rgn.m_hObject) - 1);
            v29 = m_hObject_high - 1;
          }
          CDC::LineTo(pDC, v27, v29);
        }
        goto LABEL_69;
      }
      HIDWORD(rgn.m_hObject) = *p_top + 1;
    }
    v21 = HIDWORD(rgn.__vftable);
    goto LABEL_31;
  }
  if ( this->m_bDrawFrame )
  {
    CDC::Draw3dRect(pDC, &rectFrame, clrHighlight, clrDarkShadow);
    InflateRect(&rectFrame, -1, -1);
    CDC::Draw3dRect(pDC, &rectFrame, clrLight, clrDark);
    InflateRect(&rectFrame, -1, -1);
    if ( result.x || rectFrame.right - rectFrame.left <= 0 || rectFrame.bottom - rectFrame.top <= 0 )
    {
      InflateRect(&rectFrame, -2, -2);
      goto LABEL_69;
    }
    PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.top, h, rectFrame.bottom - rectFrame.top, 0xF00021u);
    PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.top, rectFrame.right - rectFrame.left, h, 0xF00021u);
    PatBlt(pDC->m_hDC, rectFrame.right - h, rectFrame.top, h, rectFrame.bottom - rectFrame.top, 0xF00021u);
    PatBlt(pDC->m_hDC, rectFrame.left, rectFrame.bottom - h, rectFrame.right - rectFrame.left, h, 0xF00021u);
    if ( this->m_location )
    {
      v31 = this->m_rectWndArea.top;
      v30 = rectFrame.top;
    }
    else
    {
      v30 = this->m_rectWndArea.bottom;
      v31 = rectFrame.bottom;
    }
    PatBlt(pDC->m_hDC, rectFrame.left, v30, rectFrame.right - rectFrame.left, v31 - v30, 0xF00021u);
    if ( this->m_bFlat )
    {
      CDC::SelectObject(pDC, (CFont *)&penBlack);
      CDC::MoveTo(pDC, &result, h + rectFrame.left, y);
      CDC::LineTo(pDC, rectFrame.right - h, y);
    }
    if ( h > 2 )
      InflateRect(&rectFrame, 2 - h, 2 - h);
    if ( rectFrame.right - rectFrame.left > 0 && rectFrame.bottom - rectFrame.top > 0 )
    {
      v25 = clrHighlight;
      v24 = clrDarkShadow;
      p_rgn = &rectFrame;
      goto LABEL_67;
    }
  }
LABEL_69:
  if ( this->m_bTopEdge && this->m_location == LOCATION_TOP )
  {
    CDC::SelectObject(pDC, (CFont *)&penDark);
    CDC::MoveTo(pDC, &result, rectClient.left, *p_bottom);
    CDC::LineTo(pDC, rectClient.left, rectClient.top);
    CDC::LineTo(pDC, rectClient.right - 1, rectClient.top);
    CDC::LineTo(pDC, rectClient.right - 1, *p_bottom);
  }
  SelectObject = pDC->SelectObject;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  v33 = SelectObject(pDC, &afxGlobalData.fontRegular);
  result = (CPoint)v33;
  if ( !v33 )
    goto LABEL_133;
  CDC::SetBkMode(pDC, 1);
  SetTextColor = pDC->SetTextColor;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  SetTextColor(pDC, afxGlobalData.clrBtnText);
  if ( this->m_rectTabsArea.right - this->m_rectTabsArea.left > 5 && *p_bottom - this->m_rectTabsArea.top > 5 )
  {
    rectClip = this->m_rectTabsArea;
    InflateRect(&rectClip, 1, h);
    rgn.m_hObject = 0;
    rgn.__vftable = (CRgn_vtbl *)CRgn::`vftable';
    v35 = CreateRectRgnIndirect(&rectClip);
    CGdiObject::Attach(&rgn, v35);
    v36 = this->m_iTabsNum - 1;
    if ( v36 >= 0 )
    {
      v37 = v36;
      do
      {
        v38 = v36;
        m_nSize = this->m_arTabIndices.m_nSize;
        if ( m_nSize == this->m_iTabsNum )
        {
          if ( v37 < 0 || v37 >= m_nSize )
            goto LABEL_132;
          v38 = this->m_arTabIndices.m_pData[v37];
        }
        if ( v38 < 0 || v38 >= this->m_arTabs.m_nSize )
          goto LABEL_132;
        v40 = (CMFCTabInfo *)this->m_arTabs.m_pData[v38];
        if ( v40->m_bVisible )
        {
          this->m_iCurTab = v38;
          if ( v38 != this->m_iActiveTab )
          {
            CDC::SelectClipRgn(pDC, &rgn);
            if ( this->m_bFlat )
            {
              CDC::SelectObject(pDC, (CFont *)&penBlack);
              this->DrawFlatTab(this, pDC, v40, 0);
            }
            else
            {
              this->Draw3DTab(this, pDC, v40, 0);
            }
          }
        }
        --v37;
        --v36;
      }
      while ( v36 >= 0 );
      v33 = (CFont *)result;
    }
    if ( this->m_iActiveTab >= 0 )
    {
      v41 = pDC->SetTextColor;
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      v41(pDC, afxGlobalData.clrWindowText);
      m_iActiveTab = this->m_iActiveTab;
      if ( (int)m_iActiveTab < 0 || m_iActiveTab >= this->m_arTabs.m_nSize )
LABEL_132:
        AfxThrowInvalidArgException();
      v43 = (CMFCTabInfo *)this->m_arTabs.m_pData[m_iActiveTab];
      this->m_iCurTab = m_iActiveTab;
      CDC::SelectClipRgn(pDC, &rgn);
      if ( this->m_bFlat )
      {
        CDC::SelectObject(pDC, (CFont *)&this->m_brActiveTab);
        v44 = pDC->SelectObject;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        v44(pDC, &afxGlobalData.fontBold);
        v45 = pDC->SetTextColor;
        v46 = this->GetActiveTabTextColor(this);
        v45(pDC, v46);
        CDC::SelectObject(pDC, (CFont *)&penBlack);
        this->DrawFlatTab(this, pDC, v43, 1);
        left = this->m_rectTabsArea.left;
        v48 = left + 1;
        if ( left + 1 <= v43->m_rect.left + 1 )
          left = v43->m_rect.left;
        v49 = left + 1;
        if ( v43->m_rect.right > v48 )
        {
          v50 = this->GetActiveTabColor(this);
          CPen::CPen((CPen *)&rectTabSplitter, 0, 1, v50);
          CDC::SelectObject(pDC, (CFont *)&rectTabSplitter);
          if ( this->m_location )
          {
            CDC::MoveTo(pDC, &result, v49, v43->m_rect.bottom);
            v51 = v43->m_rect.bottom;
          }
          else
          {
            CDC::MoveTo(pDC, &result, v49, v43->m_rect.top);
            v51 = v43->m_rect.top;
          }
          CDC::LineTo(pDC, v43->m_rect.right, v51);
          v52 = pFont;
          CDC::SelectObject(pDC, pFont);
          *(_QWORD *)&rectTabSplitter.left = CPen::`vftable';
          CGdiObject::~CGdiObject((CGdiObject *)&rectTabSplitter);
          goto LABEL_117;
        }
      }
      else
      {
        if ( this->m_bIsActiveTabBold && (!this->IsMDITabGroup(this) || this->m_bIsActiveInMDITabGroup) )
        {
          v53 = pDC->SelectObject;
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          v53(pDC, &afxGlobalData.fontBold);
        }
        this->Draw3DTab(this, pDC, v43, 1);
      }
    }
    v52 = pFont;
LABEL_117:
    CDC::SelectClipRgn(pDC, 0);
    rgn.__vftable = (CRgn_vtbl *)CRgn::`vftable';
    CGdiObject::~CGdiObject(&rgn);
    goto LABEL_119;
  }
  v52 = pFont;
LABEL_119:
  if ( !IsRectEmpty(&this->m_rectTabSplitter) )
  {
    v54 = 0;
    if ( pbrFace )
      v54 = (HBRUSH)pbrFace->m_hObject;
    FillRect(pDC->m_hDC, &this->m_rectTabSplitter, v54);
    rectTabSplitter = this->m_rectTabSplitter;
    CDC::Draw3dRect(pDC, &rectTabSplitter, clrDarkShadow, clrDark);
    InflateRect(&rectTabSplitter, -1, -1);
    CDC::Draw3dRect(pDC, &rectTabSplitter, clrHighlight, clrDark);
  }
  if ( this->m_bFlat && this->m_nTabsHorzOffset > 0 )
  {
    CDC::SelectObject(pDC, (CFont *)&penDark);
    v55 = this->m_rectTabsArea.left - 1;
    if ( this->m_location )
    {
      CDC::MoveTo(pDC, (CPoint *)&pFont, v55, this->m_rectTabsArea.bottom);
      v56 = this->m_rectTabsArea.top + 2;
    }
    else
    {
      CDC::MoveTo(pDC, (CPoint *)&pFont, v55, this->m_rectTabsArea.top + 1);
      v56 = this->m_rectTabsArea.bottom - 2;
    }
    CDC::LineTo(pDC, v55, v56);
  }
  if ( !IsRectEmpty(&this->m_rectResize) )
  {
    v57 = CMFCVisualManager::GetInstance();
    OnDrawTabResizeBar = v57->OnDrawTabResizeBar;
    LOBYTE(v4) = this->m_ResizeMode == RESIZE_VERT;
    rectClip = this->m_rectResize;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CMFCTabCtrl *, _QWORD, CRect *, CBrush *, CPen *))OnDrawTabResizeBar)(
      v57,
      pDC,
      this,
      v4,
      &rectClip,
      pbrFace,
      &penDark);
  }
  pDC->SelectObject(pDC, v33);
  CDC::SelectObject(pDC, v73);
  CDC::SelectObject(pDC, v52);
  penHiLight.__vftable = (CPen_vtbl *)CPen::`vftable';
  CGdiObject::~CGdiObject(&penHiLight);
  penBlack.__vftable = (CPen_vtbl *)CPen::`vftable';
  CGdiObject::~CGdiObject(&penBlack);
  penDark.__vftable = (CPen_vtbl *)CPen::`vftable';
  CGdiObject::~CGdiObject(&penDark);
}

```

## disassembly

```asm
0x18013d4b0  mov     [rsp-8+arg_10], rbx
0x18013d4b5  push    rbp
0x18013d4b6  push    rsi
0x18013d4b7  push    rdi
0x18013d4b8  push    r12
0x18013d4ba  push    r13
0x18013d4bc  push    r14
0x18013d4be  push    r15
0x18013d4c0  lea     rbp, [rsp-40h]
0x18013d4c5  sub     rsp, 140h
0x18013d4cc  mov     rax, cs:__security_cookie
0x18013d4d3  xor     rax, rsp
0x18013d4d6  mov     [rbp+70h+var_40], rax
0x18013d4da  mov     r14, pDC
0x18013d4dd  mov     rdi, this
0x18013d4e0  xor     esi, esi
0x18013d4e2  mov     [rbp+70h+pbrFace], rsi
0x18013d4e6  mov     [rbp+70h+pbrBlack], rsi
0x18013d4ea  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18013d4ef  mov     r10, rax
0x18013d4f2  mov     this, [rax]
0x18013d4f5  mov     rax, [this+228h]
0x18013d4fc  lea     this, [rbp+70h+pbrBlack]
0x18013d500  mov     [rsp+170h+var_128], this
0x18013d505  lea     this, [rbp+70h+pbrFace]
0x18013d509  mov     [rsp+170h+var_130], this
0x18013d50e  lea     this, [rbp+70h+clrLight]
0x18013d512  mov     [rsp+170h+var_138], this
0x18013d517  lea     this, [rbp+70h+clrDarkShadow]
0x18013d51b  mov     [rsp+170h+var_140], this
0x18013d520  lea     this, [rbp+70h+clrFace]
0x18013d524  mov     qword ptr [rsp+170h+rop], this
0x18013d529  lea     this, [rbp+70h+clrHighlight]
0x18013d52d  mov     qword ptr [rsp+170h+h], this
0x18013d532  lea     r9, [rbp+70h+clrBlack]
0x18013d536  lea     r8, [rsp+170h+clrDark]
0x18013d53b  mov     pDC, rdi
0x18013d53e  mov     this, r10
0x18013d541  call    cs:__guard_dispatch_icall_fptr
0x18013d547  xorps   xmm0, xmm0
0x18013d54a  movdqa  xmmword ptr [rbp+70h+rectClient.left], xmm0
0x18013d54f  lea     pDC, [rbp+70h+rectClient]; lpRect
0x18013d553  mov     this, [rdi+40h]; hWnd
0x18013d557  call    cs:__imp_GetClientRect
0x18013d55d  mov     pDC, [rbp+70h+pbrFace]; pFont
0x18013d561  mov     this, r14; this
0x18013d564  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013d569  mov     [rbp+70h+var_98], rax
0x18013d56d  test    rax, rax
0x18013d570  jz      loc_18013E20F
0x18013d576  mov     r9d, [rsp+170h+clrDark]; crColor
0x18013d57b  xor     edx, edx; nPenStyle
0x18013d57d  lea     r8d, [rsi+1]; nWidth
0x18013d581  lea     this, [rbp+70h+penDark]; this
0x18013d585  call    ??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x18013d58a  nop
0x18013d58b  mov     r9d, [rbp+70h+clrBlack]; crColor
0x18013d58f  xor     edx, edx; nPenStyle
0x18013d591  lea     r8d, [rsi+1]; nWidth
0x18013d595  lea     this, [rbp+70h+penBlack]; this
0x18013d599  call    ??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x18013d59e  nop
0x18013d59f  mov     r9d, [rbp+70h+clrHighlight]; crColor
0x18013d5a3  xor     edx, edx; nPenStyle
0x18013d5a5  lea     r8d, [rsi+1]; nWidth
0x18013d5a9  lea     this, [rbp+70h+penHiLight]; this
0x18013d5ad  call    ??0CPen@@QEAA@HHK@Z; CPen::CPen(int,int,ulong)
0x18013d5b2  nop
0x18013d5b3  lea     pDC, [rbp+70h+penDark]; pFont
0x18013d5b7  mov     this, r14; this
0x18013d5ba  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013d5bf  mov     [rbp+70h+pFont], rax
0x18013d5c3  test    rax, rax
0x18013d5c6  jz      loc_18013E209
0x18013d5cc  mov     rax, [rdi]
0x18013d5cf  mov     this, rdi
0x18013d5d2  mov     rax, [rax+4A0h]
0x18013d5d9  call    cs:__guard_dispatch_icall_fptr
0x18013d5df  mov     r15d, eax
0x18013d5e2  movaps  xmm0, xmmword ptr [rbp+70h+rectClient.left]
0x18013d5e6  movdqa  xmmword ptr [rsp+170h+rgn.__vftable], xmm0
0x18013d5ec  lea     rbx, [rdi+450h]
0x18013d5f3  lea     r13, [rdi+458h]
0x18013d5fa  cmp     [rdi+0F8h], esi
0x18013d600  jnz     short loc_18013D60A
0x18013d602  mov     ecx, [rbx]
0x18013d604  mov     dword ptr [rsp+170h+rgn.__vftable+4], ecx
0x18013d608  jmp     short loc_18013D612
0x18013d60a  mov     eax, [r13+0]
0x18013d60e  mov     dword ptr [rsp+170h+rgn.m_hObject+4], eax
0x18013d612  lea     pDC, [rdi+45Ch]; lpRect
0x18013d619  mov     this, r14; this
0x18013d61c  call    ?ExcludeClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::ExcludeClipRect(tagRECT const *)
0x18013d621  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18013d626  mov     r10, rax
0x18013d629  mov     this, [rax]
0x18013d62c  mov     rax, [this+230h]
0x18013d633  movaps  xmm0, xmmword ptr [rbp+70h+rectClient.left]
0x18013d637  movdqa  xmmword ptr [rbp+70h+rectClip.left], xmm0
0x18013d63c  mov     r9, rdi
0x18013d63f  lea     r8, [rbp+70h+rectClip]
0x18013d643  mov     pDC, r14
0x18013d646  mov     this, r10
0x18013d649  call    cs:__guard_dispatch_icall_fptr
0x18013d64f  mov     [rsp+170h+result.x], eax
0x18013d653  cmp     [rdi+3F0h], esi
0x18013d659  jnz     short loc_18013D67D
0x18013d65b  test    eax, eax
0x18013d65d  jnz     short loc_18013D67D
0x18013d65f  mov     this, [rbp+70h+pbrFace]
0x18013d663  test    this, this
0x18013d666  mov     r8, rsi
0x18013d669  jz      short loc_18013D66F
0x18013d66b  mov     r8, [this+8]; hbr
0x18013d66f  lea     pDC, [rbp+70h+rectClient]; lprc
0x18013d673  mov     this, [r14+8]; hDC
0x18013d677  call    cs:__imp_FillRect
0x18013d67d  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18013d682  mov     r10, rax
0x18013d685  mov     this, [rax]
0x18013d688  mov     rax, [this+1F0h]
0x18013d68f  movaps  xmm0, xmmword ptr [rsp+170h+rgn.__vftable]
0x18013d694  movdqa  xmmword ptr [rbp+70h+rectClip.left], xmm0
0x18013d699  mov     r9, rdi
0x18013d69c  lea     r8, [rbp+70h+rectClip]
0x18013d6a0  mov     pDC, r14
0x18013d6a3  mov     this, r10
0x18013d6a6  call    cs:__guard_dispatch_icall_fptr
0x18013d6ac  movaps  xmm0, xmmword ptr [rbp+70h+rectClient.left]
0x18013d6b0  movdqa  xmmword ptr [rbp+70h+rectFrame.left], xmm0
0x18013d6b5  mov     ecx, [rdi+0F8h]
0x18013d6bb  or      r9d, 0FFFFFFFFh
0x18013d6bf  test    r15d, r15d
0x18013d6c2  jnz     short loc_18013D709
0x18013d6c4  test    ecx, ecx
0x18013d6c6  jnz     short loc_18013D6D1
0x18013d6c8  mov     eax, [rbx]
0x18013d6ca  inc     eax
0x18013d6cc  mov     [rbp+70h+rectFrame.bottom], eax
0x18013d6cf  jmp     short loc_18013D6DA
0x18013d6d1  mov     eax, [r13+0]
0x18013d6d5  dec     eax
0x18013d6d7  mov     [rbp+70h+rectFrame.top], eax
0x18013d6da  mov     r8, rsi
0x18013d6dd  cmp     [rdi+3C0h], esi
0x18013d6e3  mov     rax, [rbp+70h+pbrBlack]
0x18013d6e7  jnz     short loc_18013D6ED
0x18013d6e9  mov     rax, [rbp+70h+pbrFace]
0x18013d6ed  test    rax, rax
0x18013d6f0  jz      short loc_18013D6F6
0x18013d6f2  mov     r8, [rax+8]; hbr
0x18013d6f6  lea     pDC, [rbp+70h+rectFrame]; lprc
0x18013d6fa  mov     this, [r14+8]; hDC
0x18013d6fe  call    cs:__imp_FrameRect
0x18013d704  jmp     loc_18013DB85
0x18013d709  mov     rax, r13
0x18013d70c  test    ecx, ecx
0x18013d70e  cmovz   rax, rbx
0x18013d712  mov     r12d, [rax]
0x18013d715  mov     [rbp+70h+y], r12d
0x18013d719  mov     edx, [rdi+3C0h]
0x18013d71f  test    edx, edx
0x18013d721  jnz     short loc_18013D735
0x18013d723  test    ecx, ecx
0x18013d725  jnz     short loc_18013D72E
0x18013d727  mov     eax, [rbx]
0x18013d729  mov     [rbp+70h+rectFrame.bottom], eax
0x18013d72c  jmp     short loc_18013D735
0x18013d72e  mov     eax, [r13+0]
0x18013d732  mov     [rbp+70h+rectFrame.top], eax
0x18013d735  cmp     [rdi+3E0h], esi
0x18013d73b  jz      loc_18013D9A4
0x18013d741  movaps  xmm0, xmmword ptr [rbp+70h+rectFrame.left]
0x18013d745  movdqa  xmmword ptr [rsp+170h+rgn.__vftable], xmm0
0x18013d74b  test    edx, edx
0x18013d74d  jz      short loc_18013D75F
0x18013d74f  test    ecx, ecx
0x18013d751  jnz     loc_18013D85E
0x18013d757  mov     eax, [rbx]
0x18013d759  inc     eax
0x18013d75b  mov     dword ptr [rsp+170h+rgn.m_hObject+4], eax
0x18013d75f  mov     ebx, dword ptr [rsp+170h+rgn.__vftable+4]
0x18013d763  mov     r8d, r9d; dy
0x18013d766  mov     edx, r9d; dx
0x18013d769  lea     this, [rbp+70h+rectFrame]; lprc
0x18013d76d  call    cs:__imp_InflateRect
0x18013d773  cmp     [rdi+3F0h], esi
0x18013d779  jz      loc_18013D888
0x18013d77f  cmp     [rsp+170h+result.x], esi
0x18013d783  jnz     loc_18013D888
0x18013d789  mov     eax, [rbp+70h+rectFrame.right]
0x18013d78c  mov     edx, [rbp+70h+rectFrame.left]; x
0x18013d78f  sub     eax, edx
0x18013d791  test    eax, eax
0x18013d793  jle     loc_18013D888
0x18013d799  mov     eax, [rbp+70h+rectFrame.bottom]
0x18013d79c  mov     r8d, [rbp+70h+rectFrame.top]; y
0x18013d7a0  sub     eax, r8d
0x18013d7a3  test    eax, eax
0x18013d7a5  jle     loc_18013D888
0x18013d7ab  mov     r12d, 0F00021h
0x18013d7b1  mov     [rsp+170h+rop], r12d; rop
0x18013d7b6  mov     [rsp+170h+h], eax; h
0x18013d7ba  mov     r9d, r15d; w
0x18013d7bd  mov     this, [r14+8]; hdc
0x18013d7c1  call    cs:__imp_PatBlt
0x18013d7c7  mov     r9d, [rbp+70h+rectFrame.right]
0x18013d7cb  mov     edx, [rbp+70h+rectFrame.left]; x
0x18013d7ce  sub     r9d, edx; w
0x18013d7d1  mov     [rsp+170h+rop], r12d; rop
0x18013d7d6  mov     [rsp+170h+h], r15d; h
0x18013d7db  mov     r8d, [rbp+70h+rectFrame.top]; y
0x18013d7df  mov     this, [r14+8]; hdc
0x18013d7e3  call    cs:__imp_PatBlt
0x18013d7e9  mov     edx, [rbp+70h+rectFrame.right]
0x18013d7ec  sub     edx, r15d
0x18013d7ef  dec     edx; x
0x18013d7f1  mov     eax, [rbp+70h+rectFrame.bottom]
0x18013d7f4  mov     r8d, [rbp+70h+rectFrame.top]; y
0x18013d7f8  sub     eax, r8d
0x18013d7fb  lea     r9d, [r15+1]; w
0x18013d7ff  mov     [rsp+170h+rop], r12d; rop
0x18013d804  mov     [rsp+170h+h], eax; h
0x18013d808  mov     this, [r14+8]; hdc
0x18013d80c  call    cs:__imp_PatBlt
0x18013d812  mov     r8d, [rbp+70h+rectFrame.bottom]
0x18013d816  sub     r8d, r15d; y
0x18013d819  mov     r9d, [rbp+70h+rectFrame.right]
0x18013d81d  mov     edx, [rbp+70h+rectFrame.left]; x
0x18013d820  sub     r9d, edx; w
0x18013d823  mov     [rsp+170h+rop], r12d; rop
0x18013d828  mov     [rsp+170h+h], r15d; h
0x18013d82d  mov     this, [r14+8]; hdc
0x18013d831  call    cs:__imp_PatBlt
0x18013d837  mov     r9d, [rbp+70h+rectFrame.right]
0x18013d83b  mov     edx, [rbp+70h+rectFrame.left]; x
0x18013d83e  mov     [rsp+170h+rop], r12d; rop
0x18013d843  mov     this, [r14+8]; hdc
0x18013d847  sub     r9d, edx; w
0x18013d84a  cmp     [rdi+0F8h], esi
0x18013d850  jnz     short loc_18013D86D
0x18013d852  mov     r8d, [rdi+468h]
0x18013d859  mov     eax, [rbp+70h+rectFrame.bottom]
0x18013d85c  jmp     short loc_18013D877
0x18013d85e  mov     ebx, [r13+0]
0x18013d862  dec     ebx
0x18013d864  mov     dword ptr [rsp+170h+rgn.__vftable+4], ebx
0x18013d868  jmp     loc_18013D763
0x18013d86d  mov     eax, [rdi+460h]
0x18013d873  mov     r8d, [rbp+70h+rectFrame.top]; y
0x18013d877  sub     eax, r8d
0x18013d87a  mov     [rsp+170h+h], eax; h
0x18013d87e  call    cs:__imp_PatBlt
0x18013d884  mov     r12d, [rbp+70h+y]
0x18013d888  cmp     [rdi+3C0h], esi
0x18013d88e  jz      short loc_18013D8C4
0x18013d890  lea     pDC, [rbp+70h+penBlack]; pFont
0x18013d894  mov     this, r14; this
0x18013d897  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18013d89c  mov     r8d, [rbp+70h+rectFrame.left]
0x18013d8a0  add     r8d, r15d; x
0x18013d8a3  mov     r9d, r12d; y
0x18013d8a6  lea     pDC, [rsp+170h+result]; result
0x18013d8ab  mov     this, r14; this
0x18013d8ae  call    ?MoveTo@CDC@@QEAA?AVCPoint@@HH@Z; CDC::MoveTo(int,int)
0x18013d8b3  mov     edx, [rbp+70h+rectFrame.right]
0x18013d8b6  sub     edx, r15d; x
0x18013d8b9  mov     r8d, r12d; y
0x18013d8bc  mov     this, r14; this
0x18013d8bf  call    ?LineTo@CDC@@QEAAHHH@Z; CDC::LineTo(int,int)
0x18013d8c4  mov     r8d, [rbp+70h+clrFace]; clrTopLeft
0x18013d8c8  mov     r9d, r8d; clrBottomRight
0x18013d8cb  lea     pDC, [rsp+170h+rgn]; lpRect
0x18013d8d0  mov     this, r14; this
0x18013d8d3  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x18013d8d8  mov     rax, [rdi]
0x18013d8db  mov     this, rdi
0x18013d8de  mov     rax, [rax+308h]
0x18013d8e5  call    cs:__guard_dispatch_icall_fptr
0x18013d8eb  test    eax, eax
0x18013d8ed  jnz     short loc_18013D900
0x18013d8ef  mov     r8d, [rbp+70h+clrFace]
0x18013d8f3  mov     r9d, r8d
0x18013d8f6  lea     pDC, [rsp+170h+rgn]
0x18013d8fb  jmp     loc_18013DB69
0x18013d900  cmp     [rdi+3F0h], esi
0x18013d906  jz      short loc_18013D91D
0x18013d908  mov     r8d, [rsp+170h+clrDark]; clrTopLeft
0x18013d90d  mov     r9d, r8d; clrBottomRight
0x18013d910  lea     pDC, [rsp+170h+rgn]; lpRect
0x18013d915  mov     this, r14; this
0x18013d918  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x18013d91d  cmp     [rdi+3C4h], esi
0x18013d923  jnz     loc_18013DB85
0x18013d929  mov     eax, dword ptr [rsp+170h+rgn.m_hObject]
0x18013d92d  dec     eax
0x18013d92f  mov     r12d, eax
0x18013d932  sub     r12d, r15d
0x18013d935  cmp     [rdi+3F0h], esi
0x18013d93b  cmovnz  r12d, eax
  ... truncated ...
```
