# CMFCVisualManager::OnDrawTab(CDC *,CRect,int,int,CMFCBaseTabCtrl const *)

- ea: `0x18018cf70`
- end: `0x18018e444`
- name: `?OnDrawTab@CMFCVisualManager@@UEAAXPEAVCDC@@VCRect@@HHPEBVCMFCBaseTabCtrl@@@Z`
- size: `5332`
- prototype: `void __fastcall(CMFCVisualManager *this, CDC *pDC, CRect rectTab, int iTab, int bIsActive, const CMFCBaseTabCtrl *pTabWnd)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x1801b7c30`

## callees

- `0x1800027e0`
- `0x18001d090`
- `0x18006cab0`
- `0x1800cfb4c`
- `0x18018cf70`
- `0x180197e4c`
- `0x180197e90`
- `0x180197ef0`
- `0x180197f48`
- `0x180231d70`
- `0x1802af110`
- `0x1802af8a0`
- `0x1802af990`
- `0x1802afbb0`
- `0x1802afc20`
- `0x1802b09d0`
- `0x1802b0a90`
- `0x1802b0b50`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018d689`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018d689`
- `USER32!GetClientRect` at `0x18018da3f`
- `USER32!GetClientRect` at `0x18018da3f`
- `USER32!FillRect` at `0x18018e147`
- `USER32!FillRect` at `0x18018e189`
- `USER32!FillRect` at `0x18018e147`
- `USER32!FillRect` at `0x18018e189`
- `USER32!InflateRect` at `0x18018d9bc`
- `USER32!InflateRect` at `0x18018d9bc`
- `USER32!OffsetRect` at `0x18018e0eb`
- `USER32!OffsetRect` at `0x18018e263`
- `USER32!OffsetRect` at `0x18018e0eb`
- `USER32!OffsetRect` at `0x18018e263`
- `GDI32!Polyline` at `0x18018db0a`
- `GDI32!Polyline` at `0x18018db0a`
- `GDI32!CreateRectRgnIndirect` at `0x18018de0f`
- `GDI32!CreateRectRgnIndirect` at `0x18018e373`
- `GDI32!CreateRectRgnIndirect` at `0x18018de0f`
- `GDI32!CreateRectRgnIndirect` at `0x18018e373`
- `GDI32!CreatePolygonRgn` at `0x18018d4eb`
- `GDI32!CreatePolygonRgn` at `0x18018d991`
- `GDI32!CreatePolygonRgn` at `0x18018d4eb`
- `GDI32!CreatePolygonRgn` at `0x18018d991`
- `GDI32!Polygon` at `0x18018d0e3`
- `GDI32!Polygon` at `0x18018d0e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CMFCVisualManager::OnDrawTab(
        CMFCVisualManager *this,
        CDC *pDC,
        CRect *rectTab,
        unsigned int iTab,
        int bIsActive,
        CMFCBaseTabCtrl *pTabWnd)
{
  CDC *v8; // rdi
  CMFCVisualManager *v9; // r13
  CMFCBaseTabCtrl *v10; // r14
  unsigned int clrBtnFace; // ebx
  int v12; // eax
  CMFCBaseTabCtrl_vtbl *v13; // rdx
  int v14; // eax
  int left; // ecx
  int top; // r8d
  int v17; // r11d
  int right; // r10d
  int bottom; // r9d
  CFont *v20; // r15
  __POSITION *v21; // rax
  __POSITION *v22; // rax
  int v23; // r12d
  int v24; // ecx
  int v25; // r13d
  int v26; // edx
  int v27; // ebx
  int v28; // edi
  __POSITION *v29; // r14
  __POSITION *v30; // rax
  __POSITION *v31; // rax
  CMFCBaseTabCtrl::Location m_location; // eax
  int v33; // r13d
  int v34; // r12d
  int v35; // edi
  int v36; // r14d
  __POSITION *v37; // rax
  __POSITION *v38; // rax
  __POSITION *v39; // rax
  __POSITION *v40; // rax
  int v41; // ecx
  const POINT *v42; // rax
  POINT *v43; // r13
  _QWORD *v44; // r9
  int *p_y; // rdx
  __int64 v46; // rcx
  HRGN v47; // rax
  CMFCVisualManager_vtbl *v48; // rax
  int *v49; // rbx
  int v50; // r14d
  int v51; // r13d
  int v52; // ecx
  int v53; // r12d
  int v54; // r8d
  int v55; // eax
  int v56; // r8d
  int v57; // edx
  int v58; // ecx
  CMFCVisualManager *v59; // rdx
  int v60; // ebx
  __int64 m_nSize; // rax
  bool v62; // zf
  CRect v63; // xmm0
  tagPOINT v64; // r9
  __int64 v65; // rcx
  int v66; // edx
  HRGN PolygonRgn; // rax
  int v68; // eax
  CMFCVisualManager_vtbl *v69; // rax
  __int64 v70; // rax
  int v71; // ecx
  bool v72; // zf
  int v73; // ecx
  CMFCBaseTabCtrl::Location *p_m_location; // r13
  int v75; // ebx
  int y; // r8d
  int *p_top; // r12
  int *p_bottom; // rbx
  HRGN RectRgnIndirect; // rax
  int v80; // r8d
  CFont *p_penDark; // rdx
  int v82; // r9d
  int v83; // r9d
  int v84; // ecx
  unsigned int clrWindow; // r13d
  int m_bInitialized; // eax
  int v87; // ebx
  int v88; // eax
  unsigned int v89; // eax
  __int64 v90; // rdx
  unsigned int v91; // ebx
  int v92; // eax
  HRGN v93; // rax
  CMFCVisualManager_vtbl *v94; // rax
  CRgn *p_rgn; // rcx
  int v96; // [rsp+40h] [rbp-C0h]
  int v97; // [rsp+40h] [rbp-C0h]
  int v98; // [rsp+40h] [rbp-C0h]
  unsigned int v100; // [rsp+48h] [rbp-B8h]
  int v101; // [rsp+48h] [rbp-B8h]
  int v102; // [rsp+48h] [rbp-B8h]
  tagPOINT newElementa; // [rsp+50h] [rbp-B0h]
  __POSITION *newElement; // [rsp+50h] [rbp-B0h]
  int v106; // [rsp+60h] [rbp-A0h]
  int v107; // [rsp+60h] [rbp-A0h]
  int v108; // [rsp+60h] [rbp-A0h]
  __POSITION *position; // [rsp+68h] [rbp-98h]
  int v110; // [rsp+70h] [rbp-90h]
  int v111; // [rsp+70h] [rbp-90h]
  int v112; // [rsp+70h] [rbp-90h]
  CFont *pFont; // [rsp+78h] [rbp-88h]
  CRgn rgnClip; // [rsp+80h] [rbp-80h] BYREF
  CPen penShadow; // [rsp+90h] [rbp-70h] BYREF
  CGdiObject v116; // [rsp+A0h] [rbp-60h] BYREF
  tagPOINT v117; // [rsp+B0h] [rbp-50h]
  CPen penLight; // [rsp+B8h] [rbp-48h] BYREF
  CPen penDark; // [rsp+C8h] [rbp-38h] BYREF
  CPen pen; // [rsp+D8h] [rbp-28h] BYREF
  tagPOINT v121; // [rsp+E8h] [rbp-18h]
  tagPOINT v122; // [rsp+F0h] [rbp-10h]
  CRgn rgn; // [rsp+F8h] [rbp-8h] BYREF
  CRect rectLeftTab; // [rsp+110h] [rbp+10h] BYREF
  CRect rectFill; // [rsp+120h] [rbp+20h] BYREF
  CRect rectClipTab; // [rsp+130h] [rbp+30h] BYREF
  CRect rectClip; // [rsp+140h] [rbp+40h] BYREF
  CBrush br; // [rsp+150h] [rbp+50h] BYREF
  int v129; // [rsp+160h] [rbp+60h]
  int v130; // [rsp+164h] [rbp+64h]
  int v131; // [rsp+168h] [rbp+68h]
  int v132; // [rsp+16Ch] [rbp+6Ch]
  tagPOINT pts[8]; // [rsp+170h] [rbp+70h] BYREF

  v8 = pDC;
  *(_QWORD *)&rectLeftTab.left = pDC;
  v9 = this;
  v10 = pTabWnd;
  clrBtnFace = pTabWnd->GetTabBkColor(pTabWnd, iTab);
  v100 = clrBtnFace;
  rectClip = 0;
  v8->GetClipBox(v8, &rectClip);
  v12 = v10->IsFlatTab(v10);
  v13 = pTabWnd->__vftable;
  if ( v12 )
  {
    v14 = v13->GetTabsHeight(pTabWnd) / 2;
    left = rectTab->left;
    top = rectTab->top;
    v17 = rectTab->left + v14;
    right = rectTab->right;
    bottom = rectTab->bottom;
    if ( pTabWnd->m_location )
    {
      rectTab->top = top + 1;
      LODWORD(br.__vftable) = v17;
      HIDWORD(br.__vftable) = top + 1;
      br.m_hObject = (void *)__PAIR64__(bottom, left);
      v129 = right;
      v130 = bottom;
      v131 = right - v14;
      v132 = top + 1;
      rectTab->left = left + 2;
    }
    else
    {
      rectTab->bottom = bottom - 1;
      br.__vftable = (CBrush_vtbl *)__PAIR64__(top, left);
      LODWORD(br.m_hObject) = v17;
      HIDWORD(br.m_hObject) = bottom - 1;
      v129 = right - v14;
      v130 = bottom - 1;
      v131 = right;
      v132 = top;
    }
    v20 = 0;
    CBrush::CBrush((CBrush *)&rgnClip, clrBtnFace);
    if ( !bIsActive && clrBtnFace != -1 )
      v20 = CDC::SelectObject(v8, (CFont *)&rgnClip);
    Polygon(v8->m_hDC, (const POINT *)&br, 4);
    if ( v20 )
      CDC::SelectObject(v8, v20);
    rgnClip.__vftable = (CRgn_vtbl *)CBrush::`vftable';
    CGdiObject::~CGdiObject(&rgnClip);
    goto LABEL_183;
  }
  if ( !v13->IsLeftRightRounded(pTabWnd) )
  {
    v116.m_hObject = 0;
    v116.__vftable = (CGdiObject_vtbl *)CRgn::`vftable';
    rectClipTab = 0;
    pTabWnd->GetTabsRect(pTabWnd, &rectClipTab);
    v108 = 0;
    if ( pTabWnd->IsOneNoteStyle(pTabWnd) || pTabWnd->IsVS2005Style(pTabWnd) )
    {
      v98 = 1;
      m_nSize = pTabWnd->m_arTabIndices.m_nSize;
      if ( m_nSize == pTabWnd->m_arTabs.m_nSize )
      {
        if ( m_nSize <= 0 )
          AfxThrowInvalidArgException();
        v62 = *pTabWnd->m_arTabIndices.m_pData == iTab;
      }
      else
      {
        v62 = iTab == 0;
      }
      if ( !v62 && !bIsActive && !pTabWnd->IsVS2005Style(pTabWnd) )
      {
        v58 = rectTab->bottom - rectTab->top;
        goto LABEL_54;
      }
    }
    else
    {
      v98 = 0;
    }
    v58 = 0;
LABEL_54:
    if ( rectTab->left + 10 + v58 > rectClipTab.right || rectTab->right - 10 <= rectClipTab.left )
    {
      v116.__vftable = (CGdiObject_vtbl *)CRgn::`vftable';
      p_rgn = (CRgn *)&v116;
      goto LABEL_194;
    }
    v102 = pTabWnd->IsVS2005Style(pTabWnd);
    if ( !bIsActive || v98 )
    {
      v59 = this;
    }
    else
    {
      if ( clrBtnFace != -1 )
        goto LABEL_73;
      v59 = this;
      if ( !this->m_bAlwaysFillTab )
      {
        v60 = 0;
        goto LABEL_108;
      }
    }
    if ( clrBtnFace == -1 && !v98 && !v59->m_bAlwaysFillTab )
    {
      v60 = v98;
      goto LABEL_108;
    }
LABEL_73:
    rgnClip.m_hObject = 0;
    rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
    if ( clrBtnFace == -1 )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      clrBtnFace = afxGlobalData.clrBtnFace;
    }
    CBrush::CBrush((CBrush *)&pen, clrBtnFace);
    v63 = *rectTab;
    rectFill = *rectTab;
    v60 = v98;
    if ( v98 )
    {
      br = (CBrush)v63;
      v64 = *(tagPOINT *)&rectTab->right;
      pts[0].x = v63.left;
      pts[0].y = v64.y;
      pts[1].x = v63.left;
      pts[1].y = v64.y;
      pts[2].x = v63.left + 2;
      pts[2].y = v64.y;
      pts[3].x = v63.left + v64.y - v63.top;
      pts[3].y = v63.top + 2;
      pts[4].x = pts[3].x + 4;
      pts[4].y = v63.top;
      pts[5].x = v64.x - 2;
      pts[5].y = v63.top;
      pts[6].x = v64.x;
      pts[6].y = v63.top + 2;
      pts[7] = v64;
      v65 = 0;
      v66 = rectClipTab.right;
      do
      {
        if ( pts[v65].x > v66 )
        {
          pts[v65].x = v66;
          v108 = 1;
        }
        if ( pTabWnd->m_location == LOCATION_BOTTOM )
          pts[v65].y = v63.bottom + HIDWORD(br.__vftable) - pts[v65].y - 1;
        ++v65;
      }
      while ( v65 < 8 );
      PolygonRgn = CreatePolygonRgn(pts, 8, 2);
      CGdiObject::Attach(&rgnClip, PolygonRgn);
      CDC::SelectClipRgn(v8, &rgnClip);
    }
    else
    {
      InflateRect(&rectFill, -1, 0);
      if ( pTabWnd->m_location )
        ++rectFill.top;
      else
        --rectFill.bottom;
      v68 = rectClipTab.right;
      if ( rectFill.right < rectClipTab.right )
        v68 = rectFill.right;
      rectFill.right = v68;
    }
    v69 = this->__vftable;
    br = (CBrush)rectFill;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CBrush *, CPen *, unsigned int, int, CMFCBaseTabCtrl *))v69->OnFillTab)(
      this,
      v8,
      &br,
      &pen,
      iTab,
      bIsActive,
      pTabWnd);
    CDC::SelectClipRgn(v8, 0);
    if ( v98 )
    {
      br = 0;
      GetClientRect(pTabWnd->m_hWnd, (LPRECT)&br);
      LODWORD(br.m_hObject) = rectClipTab.left - 1;
      CDC::ExcludeClipRect(v8, (const tagRECT *)&br);
      v70 = pTabWnd->m_arTabIndices.m_nSize;
      if ( v70 == pTabWnd->m_arTabs.m_nSize )
      {
        if ( v70 <= 0 )
          AfxThrowInvalidArgException();
        v71 = 0;
        v72 = *pTabWnd->m_arTabIndices.m_pData == iTab;
      }
      else
      {
        v71 = 0;
        v72 = iTab == 0;
      }
      LOBYTE(v71) = v72;
      if ( !v71 && !bIsActive && iTab != pTabWnd->GetFirstVisibleTabNum(pTabWnd) )
      {
        rectLeftTab = rectClipTab;
        rectLeftTab.right = rectFill.bottom - 10 + rectFill.left - rectFill.top;
        v73 = (v102 != 0) + 1;
        if ( pTabWnd->m_location )
          rectLeftTab.bottom += v73;
        else
          rectLeftTab.top -= v73;
        CDC::ExcludeClipRect(v8, &rectLeftTab);
      }
      Polyline(v8->m_hDC, pts, 8);
      if ( v108 )
      {
        CDC::MoveTo(v8, (CPoint *)&rectLeftTab, rectClipTab.right, rectTab->top);
        CDC::LineTo(v8, rectClipTab.right, rectTab->bottom);
      }
      rectLeftTab = rectClipTab;
      rectLeftTab.left = rectFill.right;
      CDC::ExcludeClipRect(v8, &rectLeftTab);
    }
    pen.__vftable = (CPen_vtbl *)CBrush::`vftable';
    CGdiObject::~CGdiObject(&pen);
    rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
    CGdiObject::~CGdiObject(&rgnClip);
LABEL_108:
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    CPen::CPen(&penLight, 0, 1, afxGlobalData.clrBarHilite);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    CPen::CPen(&penShadow, 0, 1, afxGlobalData.clrBarShadow);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    CPen::CPen(&penDark, 0, 1, afxGlobalData.clrBarDkShadow);
    if ( v60 )
    {
      pFont = CDC::SelectObject(v8, (CFont *)&penLight);
      if ( pFont )
      {
        p_m_location = &pTabWnd->m_location;
        if ( pTabWnd->m_location )
        {
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[2].x + 1, pts[2].y);
          CDC::LineTo(v8, pts[3].x + 1, pts[3].y);
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[3].x + 1, pts[3].y);
          CDC::LineTo(v8, pts[3].x + 2, pts[3].y);
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[3].x + 2, pts[3].y);
          CDC::LineTo(v8, pts[3].x + 3, pts[3].y);
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[4].x - 1, pts[4].y + 1);
          CDC::LineTo(v8, pts[5].x + 1, pts[5].y + 1);
          if ( !bIsActive && !v108 && this->m_b3DTabWideBorder )
          {
            CDC::SelectObject(v8, (CFont *)&penShadow);
            CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[6].x - 2, pts[6].y - 1);
            CDC::LineTo(v8, pts[6].x - 1, pts[6].y - 1);
          }
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[6].x - 1, pts[6].y);
          y = pts[7].y;
        }
        else
        {
          if ( v108 )
          {
LABEL_127:
            p_top = &rectTab->top;
            p_bottom = &rectTab->bottom;
            goto LABEL_150;
          }
          v75 = pts[7].y;
          if ( bIsActive )
            v75 = pts[7].y - 1;
          CDC::MoveTo(v8, (CPoint *)&rectLeftTab, pts[6].x - 1, pts[6].y);
          y = v75;
        }
        CDC::LineTo(v8, pts[7].x - 1, y);
        goto LABEL_127;
      }
LABEL_196:
      AfxThrowInvalidArgException();
    }
    if ( rectTab->right > rectClipTab.right )
    {
      br = (CBrush)*rectTab;
      LODWORD(br.m_hObject) = rectClipTab.right;
      RectRgnIndirect = CreateRectRgnIndirect((const RECT *)&br);
      CGdiObject::Attach(&v116, RectRgnIndirect);
      CDC::SelectClipRgn(v8, (CRgn *)&v116);
    }
    p_m_location = &pTabWnd->m_location;
    if ( pTabWnd->m_location )
    {
      p_penDark = (CFont *)&penDark;
      if ( !this->m_b3DTabWideBorder )
        p_penDark = (CFont *)&penShadow;
      pFont = CDC::SelectObject(v8, p_penDark);
      if ( !pFont )
        goto LABEL_196;
      p_bottom = &rectTab->bottom;
      v82 = rectTab->bottom;
      if ( !bIsActive )
        --v82;
      CDC::MoveTo(v8, (CPoint *)&rectLeftTab, rectTab->right, v82);
      p_top = &rectTab->top;
      CDC::LineTo(v8, rectTab->right, rectTab->top + 2);
      CDC::LineTo(v8, rectTab->right - 2, rectTab->top);
      if ( this->m_b3DTabWideBorder )
        CDC::SelectObject(v8, (CFont *)&penLight);
      CDC::LineTo(v8, rectTab->left + 2, *p_top);
      CDC::LineTo(v8, rectTab->left, *p_top + 2);
      CDC::LineTo(v8, rectTab->left, *p_bottom);
      if ( this->m_b3DTabWideBorder )
      {
        CDC::SelectObject(v8, (CFont *)&penShadow);
        v83 = *p_bottom;
        if ( !bIsActive )
          v83 = *p_bottom - 1;
        CDC::MoveTo(v8, (CPoint *)&rectLeftTab, rectTab->right - 1, v83);
        v80 = *p_top + 1;
        goto LABEL_149;
      }
    }
    else
    {
      pFont = CDC::SelectObject(v8, (CFont *)&penLight);
      if ( !pFont )
        goto LABEL_196;
      if ( !this->m_b3DTabWideBorder )
        CDC::SelectObject(v8, (CFont *)&penShadow);
      p_top = &rectTab->top;
      CDC::MoveTo(v8, (CPoint *)&rectLeftTab, rectTab->left, rectTab->top);
      p_bottom = &rectTab->bottom;
      CDC::LineTo(v8, rectTab->left, rectTab->bottom - 2);
      if ( this->m_b3DTabWideBorder )
        CDC::SelectObject(v8, (CFont *)&penDark);
      CDC::LineTo(v8, rectTab->left + 2, *p_bottom);
      CDC::LineTo(v8, rectTab->right - 2, *p_bottom);
      CDC::LineTo(v8, rectTab->right, *p_bottom - 2);
      CDC::LineTo(v8, rectTab->right, *p_top - 1);
      CDC::SelectObject(v8, (CFont *)&penShadow);
      if ( this->m_b3DTabWideBorder )
      {
        CDC::MoveTo(v8, (CPoint *)&rectLeftTab, rectTab->left + 3, *p_bottom - 1);
        CDC::LineTo(v8, rectTab->right - 2, *p_bottom - 1);
        CDC::LineTo(v8, rectTab->right - 1, *p_bottom - 2);
        v80 = *p_top - 1;
LABEL_149:
        CDC::LineTo(v8, rectTab->right - 1, v80);
      }
    }
LABEL_150:
    if ( !bIsActive )
      goto LABEL_168;
    if ( *p_m_location )
      v84 = *p_bottom;
    else
      v84 = *p_top - 2;
    rectLeftTab.left = rectTab->left;
    rectLeftTab.right = rectTab->right;
    rectLeftTab.top = v84;
    rectLeftTab.bottom = v84 + 2;
    clrWindow = pTabWnd->GetTabBkColor(pTabWnd, iTab);
    if ( v98 )
    {
      if ( v102 )
      {
        rectLeftTab.left += 3;
      }
      else
      {
        OffsetRect(&rectLeftTab, 1, 0);
        ++rectLeftTab.left;
      }
      if ( clrWindow != -1 )
      {
LABEL_164:
        CBrush::CBrush(&br, clrWindow);
        FillRect(v8->m_hDC, &rectLeftTab, (HBRUSH)br.m_hObject);
        br.__vftable = (CBrush_vtbl *)CBrush::`vftable';
        CGdiObject::~CGdiObject(&br);
LABEL_168:
        CDC::SelectObject(v8, pFont);
        if ( v98 )
        {
          v87 = pTabWnd->IsVS2005Style(pTabWnd) && bIsActive ? 3 * (*p_bottom - *p_top) / 4 : *p_bottom - *p_top;
          v88 = pTabWnd->IsVS2005Style(pTabWnd) && bIsActive
              ? 3 * CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN / 4
              : CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN;
          rectTab->left += v87;
          rectTab->right -= v88;
          if ( pTabWnd->IsVS2005Style(pTabWnd) )
          {
            if ( bIsActive && pTabWnd->HasImage(pTabWnd, iTab) )
              OffsetRect(rectTab, CMFCBaseTabCtrl::AFX_TAB_IMAGE_MARGIN, 0);
          }
        }
        CDC::SelectClipRgn(v8, 0);
        penDark.__vftable = (CPen_vtbl *)CPen::`vftable';
        CGdiObject::~CGdiObject(&penDark);
        penShadow.__vftable = (CPen_vtbl *)CPen::`vftable';
        CGdiObject::~CGdiObject(&penShadow);
        penLight.__vftable = (CPen_vtbl *)CPen::`vftable';
        CGdiObject::~CGdiObject(&penLight);
        v116.__vftable = (CGdiObject_vtbl *)CRgn::`vftable';
        CGdiObject::~CGdiObject(&v116);
        goto LABEL_182;
      }
      m_bInitialized = afxGlobalData.m_bInitialized;
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        m_bInitialized = 1;
        afxGlobalData.m_bInitialized = 1;
      }
      clrWindow = afxGlobalData.clrWindow;
    }
    else
    {
      m_bInitialized = afxGlobalData.m_bInitialized;
    }
    if ( clrWindow == -1 )
    {
      if ( !m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      FillRect(v8->m_hDC, &rectLeftTab, (HBRUSH)afxGlobalData.brBarFace.m_hObject);
      goto LABEL_168;
    }
    goto LABEL_164;
  }
  pts[0] = (tagPOINT)CList<tagPOINT,tagPOINT>::`vftable';
  memset(&pts[1], 0, 32);
  *(__m128i *)&pts[5].x = _mm_load_si128((const __m128i *)&_xmm);
  v21 = CList<tagPOINT,tagPOINT>::AddHead((CList<tagPOINT,tagPOINT> *)pts, *(tagPOINT *)&rectTab->left);
  position = CList<tagPOINT,tagPOINT>::InsertAfter(
               (CList<tagPOINT,tagPOINT> *)pts,
               v21,
               (tagPOINT)(*(_QWORD *)&rectTab->left + 0x200000000LL));
  newElementa.x = rectTab->right;
  newElementa.y = rectTab->top;
  v22 = CList<tagPOINT,tagPOINT>::AddTail((CList<tagPOINT,tagPOINT> *)pts, newElementa);
  newElementa.x = rectTab->right;
  newElementa.y = rectTab->top + 2;
  newElement = CList<tagPOINT,tagPOINT>::InsertBefore((CList<tagPOINT,tagPOINT> *)pts, v22, newElementa);
  v23 = rectTab->left + 1;
  v96 = v23;
  v24 = rectTab->right - 1;
  v25 = rectTab->top + 2;
  v110 = v25;
  v26 = rectTab->bottom;
  if ( v25 < v26 - 4 )
  {
    v27 = rectTab->top + 4;
    v28 = rectTab->right - 1;
    v29 = position;
    do
    {
      v30 = CList<tagPOINT,tagPOINT>::InsertAfter((CList<tagPOINT,tagPOINT> *)pts, v29, (tagPOINT)__PAIR64__(v25, v23));
      v117 = (tagPOINT)__PAIR64__(v27, v23);
      v29 = CList<tagPOINT,tagPOINT>::InsertAfter((CList<tagPOINT,tagPOINT> *)pts, v30, (tagPOINT)__PAIR64__(v27, v23));
      v31 = CList<tagPOINT,tagPOINT>::InsertBefore(
              (CList<tagPOINT,tagPOINT> *)pts,
              newElement,
              (tagPOINT)__PAIR64__(v25, v28));
      newElement = CList<tagPOINT,tagPOINT>::InsertBefore(
                     (CList<tagPOINT,tagPOINT> *)pts,
                     v31,
                     (tagPOINT)__PAIR64__(v27, v28));
      ++v23;
      --v28;
      v25 += 2;
      v27 += 2;
      v26 = rectTab->bottom;
    }
    while ( v25 < v26 - 4 );
    position = v29;
    v106 = v28;
    v96 = v23;
    v110 = v25;
    v8 = *(CDC **)&rectLeftTab.left;
    v10 = pTabWnd;
    clrBtnFace = v100;
    v24 = v106;
  }
  m_location = v10->m_location;
  v33 = v24 + 1;
  if ( m_location != LOCATION_TOP )
    v33 = v24;
  v34 = v23 - 1;
  if ( m_location != LOCATION_TOP )
    v34 = v96;
  v107 = v34 - 1;
  v117.x = v33 + 1;
  if ( v110 < v26 - 1 )
  {
    v35 = v110 + 1;
    v97 = v33 - 2;
    v36 = v34 + 1;
    do
    {
      v111 = v35;
      v121.x = v34;
      v121.y = v35 - 1;
      v37 = CList<tagPOINT,tagPOINT>::InsertAfter((CList<tagPOINT,tagPOINT> *)pts, position, v121);
      v122 = (tagPOINT)__PAIR64__(v35, v36);
      position = CList<tagPOINT,tagPOINT>::InsertAfter(
                   (CList<tagPOINT,tagPOINT> *)pts,
                   v37,
                   (tagPOINT)__PAIR64__(v35, v36));
      penDark.__vftable = (CPen_vtbl *)__PAIR64__(v35 - 1, v33);
      v38 = CList<tagPOINT,tagPOINT>::InsertBefore(
              (CList<tagPOINT,tagPOINT> *)pts,
              newElement,
              (tagPOINT)__PAIR64__(v35 - 1, v33));
      LODWORD(penLight.__vftable) = v97 + 1;
      HIDWORD(penLight.__vftable) = v35;
      newElement = CList<tagPOINT,tagPOINT>::InsertBefore(
                     (CList<tagPOINT,tagPOINT> *)pts,
                     v38,
                     (tagPOINT)penLight.__vftable);
      if ( v35 - 1 == rectTab->bottom - 2 )
      {
        v116.__vftable = (CGdiObject_vtbl *)__PAIR64__(v35, v36);
        v39 = CList<tagPOINT,tagPOINT>::InsertAfter(
                (CList<tagPOINT,tagPOINT> *)pts,
                position,
                (tagPOINT)__PAIR64__(v35, v36));
        LODWORD(penShadow.__vftable) = v36 + 2;
        HIDWORD(penShadow.__vftable) = v35;
        position = CList<tagPOINT,tagPOINT>::InsertAfter(
                     (CList<tagPOINT,tagPOINT> *)pts,
                     v39,
                     (tagPOINT)penShadow.__vftable);
        *(_QWORD *)&rectClipTab.left = __PAIR64__(v35, v33);
        v40 = CList<tagPOINT,tagPOINT>::InsertBefore(
                (CList<tagPOINT,tagPOINT> *)pts,
                newElement,
                (tagPOINT)__PAIR64__(v35, v33));
        *(_QWORD *)&rectFill.left = __PAIR64__(v35, v97);
        newElement = CList<tagPOINT,tagPOINT>::InsertBefore(
                       (CList<tagPOINT,tagPOINT> *)pts,
                       v40,
                       (tagPOINT)__PAIR64__(v35, v97));
      }
      ++v34;
      ++v36;
      --v33;
      --v97;
      ++v35;
      v26 = rectTab->bottom;
    }
    while ( v111 < v26 - 1 );
    v8 = *(CDC **)&rectLeftTab.left;
    v10 = pTabWnd;
    clrBtnFace = v100;
  }
  rectLeftTab.left = v34 + 2;
  rectLeftTab.top = v26;
  CList<tagPOINT,tagPOINT>::InsertAfter((CList<tagPOINT,tagPOINT> *)pts, position, *(tagPOINT *)&rectLeftTab.left);
  v41 = rectTab->bottom;
  rectLeftTab.left = v33 - 2;
  rectLeftTab.top = v41;
  CList<tagPOINT,tagPOINT>::InsertBefore((CList<tagPOINT,tagPOINT> *)pts, newElement, *(tagPOINT *)&rectLeftTab.left);
  v42 = (const POINT *)operator new(saturated_mul(*(_QWORD *)&pts[3], 8u));
  v43 = (POINT *)v42;
  *(_QWORD *)&rectLeftTab.left = v42;
  v44 = (_QWORD *)pts[1];
  if ( pts[1] )
  {
    p_y = &v42->y;
    do
    {
      v46 = v44[2];
      v44 = (_QWORD *)*v44;
      *(_QWORD *)(p_y - 1) = v46;
      if ( v10->m_location == LOCATION_TOP )
        *p_y = rectTab->top + rectTab->bottom - *p_y;
      p_y += 2;
    }
    while ( v44 );
  }
  rgnClip.m_hObject = 0;
  rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  v47 = CreatePolygonRgn(v42, pts[3].x, 2);
  CGdiObject::Attach(&rgnClip, v47);
  CDC::SelectClipRgn(v8, &rgnClip);
  if ( clrBtnFace == -1 )
  {
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    clrBtnFace = afxGlobalData.clrBtnFace;
  }
  CBrush::CBrush(&br, clrBtnFace);
  v48 = this->__vftable;
  rectFill = *rectTab;
  ((void (__fastcall *)(CMFCVisualManager *, CDC *, CRect *, CBrush *, unsigned int, int, CMFCBaseTabCtrl *))v48->OnFillTab)(
    this,
    v8,
    &rectFill,
    &br,
    iTab,
    bIsActive,
    v10);
  CDC::SelectClipRgn(v8, 0);
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  CPen::CPen(&pen, 0, 1, afxGlobalData.clrBarShadow);
  *(_QWORD *)&rectFill.left = CDC::SelectObject(v8, (CFont *)&pen);
  if ( *(_QWORD *)&pts[3] > 0 )
  {
    v49 = (int *)&v43[-1];
    v50 = 0;
    do
    {
      if ( (v50 & 1) != 0 )
      {
        v51 = *v49;
        v52 = v49[1];
        v112 = v52;
        v53 = v49[2];
        v54 = v49[3];
        v101 = v54;
        v55 = (rectTab->right + rectTab->left) / 2;
        if ( *v49 > v55 && v53 > v55 )
        {
          --v51;
          --v53;
        }
        if ( v54 < v52 )
        {
          CDC::MoveTo(v8, (CPoint *)&penShadow, v53, v54);
          v56 = v112;
          v57 = v51;
        }
        else
        {
          CDC::MoveTo(v8, (CPoint *)&rectClipTab, v51, v52);
          v56 = v101;
          v57 = v53;
        }
        CDC::LineTo(v8, v57, v56);
      }
      ++v50;
      v49 += 2;
    }
    while ( v50 < *(_QWORD *)&pts[3] );
    v10 = pTabWnd;
    v43 = *(POINT **)&rectLeftTab.left;
  }
  free(v43);
  CDC::SelectObject(v8, *(CFont **)&rectFill.left);
  rectTab->left = v107;
  rectTab->right = v117.x;
  pen.__vftable = (CPen_vtbl *)CPen::`vftable';
  CGdiObject::~CGdiObject(&pen);
  br.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  CGdiObject::~CGdiObject(&br);
  rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnClip);
  CList<tagPOINT,tagPOINT>::~CList<tagPOINT,tagPOINT>((CList<tagPOINT,tagPOINT> *)pts);
LABEL_182:
  v9 = this;
LABEL_183:
  v89 = v10->GetTabTextColor(v10, iTab);
  v90 = v89;
  v91 = -1;
  if ( !bIsActive && v89 != -1 )
    v91 = v8->SetTextColor(v8, v89);
  if ( ((unsigned int (__fastcall *)(CMFCBaseTabCtrl *, __int64))v10->IsOneNoteStyle)(v10, v90)
    || v10->IsVS2005Style(v10) )
  {
    br = 0;
    v10->GetTabsRect(v10, (CRect *)&br);
    v92 = rectTab->right;
    if ( v92 >= LODWORD(br.m_hObject) - 2 )
      v92 = LODWORD(br.m_hObject) - 2;
    rectTab->right = v92;
  }
  rgn.m_hObject = 0;
  rgn.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  v93 = CreateRectRgnIndirect(&rectClip);
  CGdiObject::Attach(&rgn, v93);
  CDC::SelectClipRgn(v8, &rgn);
  v94 = v9->__vftable;
  br = (CBrush)*rectTab;
  ((void (__fastcall *)(CMFCVisualManager *, CDC *, CBrush *, _QWORD, int, CMFCBaseTabCtrl *, int))v94->OnDrawTabContent)(
    v9,
    v8,
    &br,
    iTab,
    bIsActive,
    v10,
    -1);
  if ( v91 != -1 )
    v8->SetTextColor(v8, v91);
  CDC::SelectClipRgn(v8, 0);
  rgn.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  p_rgn = &rgn;
LABEL_194:
  CGdiObject::~CGdiObject(p_rgn);
}

```

## disassembly

```asm
0x18018cf70  push    rbp
0x18018cf72  push    rbx
0x18018cf73  push    rsi
0x18018cf74  push    rdi
0x18018cf75  push    r12
0x18018cf77  push    r13
0x18018cf79  push    r14
0x18018cf7b  push    r15
0x18018cf7d  lea     rbp, [rsp-0C8h]
0x18018cf85  sub     rsp, 1C8h
0x18018cf8c  mov     rax, cs:__security_cookie
0x18018cf93  xor     rax, rsp
0x18018cf96  mov     [rbp+100h+var_50], rax
0x18018cf9d  mov     r12d, iTab
0x18018cfa0  mov     [rsp+200h+var_1BC], iTab
0x18018cfa5  mov     rsi, rectTab
0x18018cfa8  mov     rdi, pDC
0x18018cfab  mov     qword ptr [rbp+100h+rectLeftTab.left], pDC
0x18018cfaf  mov     r13, this
0x18018cfb2  mov     [rsp+200h+var_1A8], this
0x18018cfb7  mov     r14, [rbp+100h+arg_28]
0x18018cfbe  mov     [rsp+200h+pFont], r14
0x18018cfc3  mov     rax, [r14]
0x18018cfc6  mov     edx, iTab
0x18018cfc9  mov     this, r14
0x18018cfcc  mov     rax, [rax+3C8h]
0x18018cfd3  call    cs:__guard_dispatch_icall_fptr
0x18018cfd9  mov     ebx, eax
0x18018cfdb  mov     [rsp+200h+var_1B8], eax
0x18018cfdf  xorps   xmm0, xmm0
0x18018cfe2  movups  xmmword ptr [rbp+100h+rectClip.left], xmm0
0x18018cfe6  mov     this, [rdi]
0x18018cfe9  mov     rax, [this+0B0h]
0x18018cff0  lea     pDC, [rbp+100h+rectClip]
0x18018cff4  mov     this, rdi
0x18018cff7  call    cs:__guard_dispatch_icall_fptr
0x18018cffd  mov     this, [r14]
0x18018d000  mov     rax, [this+510h]
0x18018d007  mov     this, r14
0x18018d00a  call    cs:__guard_dispatch_icall_fptr
0x18018d010  mov     pDC, [r14]
0x18018d013  lea     r15, ??_7CRgn@@6B@; const CRgn::`vftable'
0x18018d01a  mov     this, r14
0x18018d01d  test    eax, eax
0x18018d01f  jz      loc_18018D113
0x18018d025  mov     rax, [pDC+308h]
0x18018d02c  call    cs:__guard_dispatch_icall_fptr
0x18018d032  cdq
0x18018d033  sub     eax, edx
0x18018d035  sar     eax, 1
0x18018d037  mov     ecx, [rsi]
0x18018d039  mov     r8d, [rsi+4]
0x18018d03d  lea     r11d, [this+rax]
0x18018d041  mov     r10d, [rsi+8]
0x18018d045  mov     iTab, [rsi+0Ch]
0x18018d049  mov     edx, r10d
0x18018d04c  sub     edx, eax
0x18018d04e  cmp     dword ptr [r14+0F8h], 0
0x18018d056  jnz     short loc_18018D07D
0x18018d058  lea     eax, [r9-1]
0x18018d05c  mov     [rsi+0Ch], eax
0x18018d05f  mov     dword ptr [rbp+100h+br.__vftable], ecx
0x18018d062  mov     dword ptr [rbp+100h+br.__vftable+4], r8d
0x18018d066  mov     dword ptr [rbp+100h+br.m_hObject], r11d
0x18018d06a  mov     dword ptr [rbp+100h+br.m_hObject+4], eax
0x18018d06d  mov     [rbp+100h+var_A0], edx
0x18018d070  mov     [rbp+100h+var_9C], eax
0x18018d073  mov     [rbp+100h+var_98], r10d
0x18018d077  mov     [rbp+100h+var_94], r8d
0x18018d07b  jmp     short loc_18018D0A5
0x18018d07d  lea     eax, [rectTab+1]
0x18018d081  mov     [rsi+4], eax
0x18018d084  mov     dword ptr [rbp+100h+br.__vftable], r11d
0x18018d088  mov     dword ptr [rbp+100h+br.__vftable+4], eax
0x18018d08b  mov     dword ptr [rbp+100h+br.m_hObject], ecx
0x18018d08e  mov     dword ptr [rbp+100h+br.m_hObject+4], iTab
0x18018d092  mov     [rbp+100h+var_A0], r10d
0x18018d096  mov     [rbp+100h+var_9C], iTab
0x18018d09a  mov     [rbp+100h+var_98], edx
0x18018d09d  mov     [rbp+100h+var_94], eax
0x18018d0a0  lea     eax, [this+2]
0x18018d0a3  mov     [rsi], eax
0x18018d0a5  xor     r15d, r15d
0x18018d0a8  mov     edx, ebx; crColor
0x18018d0aa  lea     this, [rbp+100h+rgnClip]; this
0x18018d0ae  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x18018d0b3  nop
0x18018d0b4  or      r12d, 0FFFFFFFFh
0x18018d0b8  cmp     [rbp+100h+arg_20], r15d
0x18018d0bf  jnz     short loc_18018D0D5
0x18018d0c1  cmp     ebx, r12d
0x18018d0c4  jz      short loc_18018D0D5
0x18018d0c6  lea     pDC, [rbp+100h+rgnClip]; pFont
0x18018d0ca  mov     this, rdi; this
0x18018d0cd  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18018d0d2  mov     r15, rax
0x18018d0d5  mov     r8d, 4; cpt
0x18018d0db  lea     pDC, [rbp+100h+br]; apt
0x18018d0df  mov     this, [rdi+8]; hdc
0x18018d0e3  call    cs:__imp_Polygon
0x18018d0e9  test    r15, r15
0x18018d0ec  jz      short loc_18018D0FA
0x18018d0ee  mov     pDC, r15; pFont
0x18018d0f1  mov     this, rdi; this
0x18018d0f4  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18018d0f9  nop
0x18018d0fa  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x18018d101  mov     [rbp+100h+rgnClip.__vftable], rax
0x18018d105  lea     this, [rbp+100h+rgnClip]; this
0x18018d109  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18018d10e  jmp     loc_18018E2C2
0x18018d113  mov     rax, [pDC+530h]
0x18018d11a  call    cs:__guard_dispatch_icall_fptr
0x18018d120  xor     r13d, r13d
0x18018d123  test    eax, eax
0x18018d125  jz      loc_18018D6F4
0x18018d12b  lea     rax, ??_7?$CList@UtagPOINT@@U1@@@6B@; const CList<tagPOINT,tagPOINT>::`vftable'
0x18018d132  mov     qword ptr [rbp+100h+pts.x], rax
0x18018d136  xorps   xmm0, xmm0
0x18018d139  movdqu  xmmword ptr [rbp+100h+pts.x+18h], xmm0
0x18018d141  mov     qword ptr [rbp+100h+pts.x+10h], r13
0x18018d148  mov     qword ptr [rbp+100h+pts.x+8], r13
0x18018d14c  movdqa  xmm0, cs:__xmm@000000000000000a0000000000000000
0x18018d154  movdqu  xmmword ptr [rbp+100h+pts.x+28h], xmm0
0x18018d15c  mov     ecx, [rsi+4]
0x18018d15f  mov     eax, [rsi]
0x18018d161  mov     [rsp+200h+newElement.x], eax
0x18018d165  mov     [rsp+200h+newElement.y], ecx
0x18018d169  mov     pDC, qword ptr [rsp+200h+newElement.x]; newElement
0x18018d16e  lea     this, [rbp+100h+pts]; this
0x18018d172  call    ?AddHead@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::AddHead(tagPOINT)
0x18018d177  mov     edx, [rsi+4]
0x18018d17a  add     edx, 2
0x18018d17d  mov     ecx, [rsi]
0x18018d17f  mov     [rsp+200h+newElement.x], ecx
0x18018d183  mov     [rsp+200h+newElement.y], edx
0x18018d187  mov     rectTab, qword ptr [rsp+200h+newElement.x]; newElement
0x18018d18c  mov     pDC, rax; position
0x18018d18f  lea     this, [rbp+100h+pts]; this
0x18018d193  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d198  mov     [rsp+200h+position], rax
0x18018d19d  mov     edx, [rsi+4]
0x18018d1a0  mov     ecx, [rsi+8]
0x18018d1a3  mov     [rsp+200h+newElement.x], ecx
0x18018d1a7  mov     [rsp+200h+newElement.y], edx
0x18018d1ab  mov     pDC, qword ptr [rsp+200h+newElement.x]; newElement
0x18018d1b0  lea     this, [rbp+100h+pts]; this
0x18018d1b4  call    ?AddTail@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::AddTail(tagPOINT)
0x18018d1b9  mov     edx, [rsi+4]
0x18018d1bc  add     edx, 2
0x18018d1bf  mov     ecx, [rsi+8]
0x18018d1c2  mov     [rsp+200h+newElement.x], ecx
0x18018d1c6  mov     [rsp+200h+newElement.y], edx
0x18018d1ca  mov     rectTab, qword ptr [rsp+200h+newElement.x]; newElement
0x18018d1cf  mov     pDC, rax; position
0x18018d1d2  lea     this, [rbp+100h+pts]; this
0x18018d1d6  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d1db  mov     qword ptr [rsp+200h+newElement.x], rax
0x18018d1e0  mov     r12d, [rsi]
0x18018d1e3  lea     r15d, [r13+1]
0x18018d1e7  add     r12d, r15d
0x18018d1ea  mov     [rsp+200h+var_1C0], r12d
0x18018d1ef  mov     ecx, [rsi+8]
0x18018d1f2  sub     ecx, r15d
0x18018d1f5  mov     r13d, [rsi+4]
0x18018d1f9  add     r13d, 2
0x18018d1fd  mov     [rsp+200h+var_190.x], r13d
0x18018d202  mov     edx, [rsi+0Ch]
0x18018d205  lea     eax, [pDC-4]
0x18018d208  cmp     r13d, eax
0x18018d20b  jge     loc_18018D2CB
0x18018d211  lea     ebx, [r13+2]
0x18018d215  mov     edi, ecx
0x18018d217  mov     r14, [rsp+200h+position]
0x18018d21c  mov     dword ptr [rsp+200h+position], r12d
0x18018d221  mov     dword ptr [rsp+200h+position+4], r13d
0x18018d226  mov     rectTab, [rsp+200h+position]; newElement
0x18018d22b  mov     pDC, r14; position
0x18018d22e  lea     this, [rbp+100h+pts]; this
0x18018d232  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d237  mov     [rbp+100h+var_150.x], r12d
0x18018d23b  mov     [rbp+100h+var_150.y], ebx
0x18018d23e  mov     rectTab, qword ptr [rbp+100h+var_150.x]; newElement
0x18018d242  mov     pDC, rax; position
0x18018d245  lea     this, [rbp+100h+pts]; this
0x18018d249  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d24e  mov     r14, rax
0x18018d251  mov     [rsp+200h+var_190.x], edi
0x18018d255  mov     [rsp+200h+var_190.y], r13d
0x18018d25a  mov     rectTab, qword ptr [rsp+200h+var_190.x]; newElement
0x18018d25f  mov     pDC, qword ptr [rsp+200h+newElement.x]; position
0x18018d264  lea     this, [rbp+100h+pts]; this
0x18018d268  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d26d  mov     [rsp+200h+var_1A0.x], edi
0x18018d271  mov     [rsp+200h+var_1A0.y], ebx
0x18018d275  mov     rectTab, qword ptr [rsp+200h+var_1A0.x]; newElement
0x18018d27a  mov     pDC, rax; position
0x18018d27d  lea     this, [rbp+100h+pts]; this
0x18018d281  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d286  mov     qword ptr [rsp+200h+newElement.x], rax
0x18018d28b  add     r12d, r15d
0x18018d28e  sub     edi, r15d
0x18018d291  add     r13d, 2
0x18018d295  add     ebx, 2
0x18018d298  mov     edx, [rsi+0Ch]
0x18018d29b  lea     eax, [pDC-4]
0x18018d29e  cmp     r13d, eax
0x18018d2a1  jl      loc_18018D21C
0x18018d2a7  mov     [rsp+200h+position], r14
0x18018d2ac  mov     [rsp+200h+var_1A0.x], edi
0x18018d2b0  mov     [rsp+200h+var_1C0], r12d
0x18018d2b5  mov     [rsp+200h+var_190.x], r13d
0x18018d2ba  mov     rdi, qword ptr [rbp+100h+rectLeftTab.left]
0x18018d2be  mov     r14, [rsp+200h+pFont]
0x18018d2c3  mov     ebx, [rsp+200h+var_1B8]
0x18018d2c7  mov     ecx, [rsp+200h+var_1A0.x]
0x18018d2cb  mov     eax, [r14+0F8h]
0x18018d2d2  lea     r13d, [this+1]
0x18018d2d6  cmp     eax, r15d
0x18018d2d9  cmovnz  r13d, ecx
0x18018d2dd  dec     r12d
0x18018d2e0  cmp     eax, r15d
0x18018d2e3  cmovnz  r12d, [rsp+200h+var_1C0]
0x18018d2e9  lea     eax, [r12-1]
0x18018d2ee  mov     [rsp+200h+var_1A0.x], eax
0x18018d2f2  lea     eax, [r13+1]
0x18018d2f6  mov     [rbp+100h+var_150.x], eax
0x18018d2f9  lea     eax, [pDC-1]
0x18018d2fc  mov     ecx, [rsp+200h+var_190.x]
0x18018d300  cmp     ecx, eax
0x18018d302  jge     loc_18018D436
0x18018d308  lea     edi, [this+1]
0x18018d30b  lea     eax, [r13-2]
0x18018d30f  mov     [rsp+200h+var_1C0], eax
0x18018d313  lea     r14d, [r12+1]
0x18018d318  mov     [rsp+200h+var_190.x], edi
0x18018d31c  mov     [rbp+100h+var_118.x], r12d
0x18018d320  lea     ebx, [rdi-1]
0x18018d323  mov     [rbp+100h+var_118.y], ebx
0x18018d326  mov     rectTab, qword ptr [rbp+100h+var_118.x]; newElement
0x18018d32a  mov     pDC, [rsp+200h+position]; position
0x18018d32f  lea     this, [rbp+100h+pts]; this
0x18018d333  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d338  mov     [rbp+100h+var_110.x], r14d
0x18018d33c  mov     [rbp+100h+var_110.y], edi
0x18018d33f  mov     rectTab, qword ptr [rbp+100h+var_110.x]; newElement
0x18018d343  mov     pDC, rax; position
0x18018d346  lea     this, [rbp+100h+pts]; this
0x18018d34a  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d34f  mov     [rsp+200h+position], rax
0x18018d354  mov     dword ptr [rbp+100h+penDark.__vftable], r13d
0x18018d358  mov     dword ptr [rbp+100h+penDark.__vftable+4], ebx
0x18018d35b  mov     rectTab, [rbp+100h+penDark.__vftable]; newElement
0x18018d35f  mov     pDC, qword ptr [rsp+200h+newElement.x]; position
0x18018d364  lea     this, [rbp+100h+pts]; this
0x18018d368  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d36d  mov     ecx, [rsp+200h+var_1C0]
0x18018d371  inc     ecx
0x18018d373  mov     dword ptr [rbp+100h+penLight.__vftable], ecx
0x18018d376  mov     dword ptr [rbp+100h+penLight.__vftable+4], edi
0x18018d379  mov     rectTab, [rbp+100h+penLight.__vftable]; newElement
0x18018d37d  mov     pDC, rax; position
0x18018d380  lea     this, [rbp+100h+pts]; this
0x18018d384  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d389  mov     qword ptr [rsp+200h+newElement.x], rax
0x18018d38e  mov     eax, [rsi+0Ch]
0x18018d391  sub     eax, 2
0x18018d394  cmp     ebx, eax
0x18018d396  jnz     short loc_18018D408
0x18018d398  mov     [rbp+100h+var_160.x], r14d
0x18018d39c  mov     [rbp+100h+var_160.y], edi
0x18018d39f  mov     rectTab, qword ptr [rbp+100h+var_160.x]; newElement
0x18018d3a3  mov     pDC, [rsp+200h+position]; position
0x18018d3a8  lea     this, [rbp+100h+pts]; this
0x18018d3ac  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d3b1  lea     ecx, [r14+2]
0x18018d3b5  mov     dword ptr [rbp+100h+penShadow.__vftable], ecx
0x18018d3b8  mov     dword ptr [rbp+100h+penShadow.__vftable+4], edi
0x18018d3bb  mov     rectTab, [rbp+100h+penShadow.__vftable]; newElement
0x18018d3bf  mov     pDC, rax; position
0x18018d3c2  lea     this, [rbp+100h+pts]; this
0x18018d3c6  call    ?InsertAfter@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertAfter(__POSITION *,tagPOINT)
0x18018d3cb  mov     [rsp+200h+position], rax
0x18018d3d0  mov     [rbp+100h+rectClipTab.left], r13d
0x18018d3d4  mov     [rbp+100h+rectClipTab.top], edi
0x18018d3d7  mov     rectTab, qword ptr [rbp+100h+rectClipTab.left]; newElement
0x18018d3db  mov     pDC, qword ptr [rsp+200h+newElement.x]; position
0x18018d3e0  lea     this, [rbp+100h+pts]; this
0x18018d3e4  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d3e9  mov     ecx, [rsp+200h+var_1C0]
0x18018d3ed  mov     [rbp+100h+rectFill.left], ecx
0x18018d3f0  mov     [rbp+100h+rectFill.top], edi
0x18018d3f3  mov     rectTab, qword ptr [rbp+100h+rectFill.left]; newElement
0x18018d3f7  mov     pDC, rax; position
0x18018d3fa  lea     this, [rbp+100h+pts]; this
0x18018d3fe  call    ?InsertBefore@?$CList@UtagPOINT@@U1@@@QEAAPEAU__POSITION@@PEAU2@UtagPOINT@@@Z; CList<tagPOINT,tagPOINT>::InsertBefore(__POSITION *,tagPOINT)
0x18018d403  mov     qword ptr [rsp+200h+newElement.x], rax
0x18018d408  add     r12d, r15d
0x18018d40b  add     r14d, r15d
0x18018d40e  sub     r13d, r15d
  ... truncated ...
```
