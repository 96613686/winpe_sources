# CMFCVisualManagerOffice2003::OnFillBarBackground(CDC *,CBasePane *,CRect,CRect,int)

- ea: `0x180198760`
- end: `0x18019912d`
- name: `?OnFillBarBackground@CMFCVisualManagerOffice2003@@UEAAXPEAVCDC@@PEAVCBasePane@@VCRect@@2H@Z`
- size: `2509`
- prototype: `void __fastcall(CMFCVisualManagerOffice2003 *this, CDC *pDC, CBasePane *pBar, CRect rectClient, CRect rectClip, int bNCArea)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x1801ac060`
- `0x1801bec90`

## callees

- `0x1800596d0`
- `0x18006cab0`
- `0x1800c3270`
- `0x180156640`
- `0x1801567a0`
- `0x180198760`
- `0x1801b7100`
- `0x180231d70`
- `0x18023f820`
- `0x18023f950`
- `0x180296d00`
- `0x1802af110`
- `0x1802af6a0`
- `0x1802af710`
- `0x1802afbb0`
- `0x1802afc20`
- `0x1802afe10`
- `0x1802b6310`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetClientRect` at `0x180198c4d`
- `USER32!GetClientRect` at `0x180198c4d`
- `USER32!SetRectEmpty` at `0x180198e30`
- `USER32!SetRectEmpty` at `0x180198e30`
- `USER32!GetWindowRect` at `0x180198f83`
- `USER32!GetWindowRect` at `0x180198f83`
- `USER32!FillRect` at `0x1801989c2`
- `USER32!FillRect` at `0x1801989c2`
- `USER32!MapWindowPoints` at `0x180198c16`
- `USER32!MapWindowPoints` at `0x180198c16`
- `USER32!IsRectEmpty` at `0x18019890f`
- `USER32!IsRectEmpty` at `0x180198f38`
- `USER32!IsRectEmpty` at `0x18019890f`
- `USER32!IsRectEmpty` at `0x180198f38`
- `USER32!GetParent` at `0x1801987cb`
- `USER32!GetParent` at `0x180198bc8`
- `USER32!GetParent` at `0x1801987cb`
- `USER32!GetParent` at `0x180198bc8`
- `USER32!InflateRect` at `0x180198a04`
- `USER32!InflateRect` at `0x180198cb4`
- `USER32!InflateRect` at `0x180198a04`
- `USER32!InflateRect` at `0x180198cb4`
- `UxTheme!DrawThemeBackground` at `0x1801988c2`
- `UxTheme!DrawThemeBackground` at `0x1801988c2`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
void __fastcall CMFCVisualManagerOffice2003::OnFillBarBackground(
        CMFCVisualManagerOffice2003 *this,
        CDC *pDC,
        CBasePane *pBar,
        CRect *rectClient,
        CRect *rectClip,
        int bNCArea)
{
  int v10; // esi
  HWND Parent; // rax
  CWnd *v12; // rax
  CRuntimeClass *v13; // r12
  int m_bInitialized; // ecx
  void *m_hThemeStatusBar; // rcx
  unsigned int m_clrBarGradientLight; // r9d
  unsigned int m_clrBarGradientDark; // r8d
  HBRUSH m_hObject; // r8
  CMFCPopupMenuBar *v19; // rcx
  int v20; // r12d
  int IsKindOf; // eax
  int v22; // edx
  unsigned int m_clrToolBarGradientLight; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  CMFCToolBar *v27; // r14
  HWND v28; // rax
  CWnd *v29; // rax
  CMFCVisualManagerOffice2003_vtbl *v30; // rax
  tagRECT v31; // xmm6
  CMFCToolBarButton *v32; // r12
  int m_nCount; // edx
  CMFCToolBarButton *Button; // rax
  int v35; // r8d
  int v36; // edx
  int v37; // eax
  void (__fastcall *DrawCustomizeButton)(CMFCVisualManagerOffice2003 *, CDC *, CRect, int, CMFCVisualManager::AFX_BUTTON_STATE, int, int); // rdi
  BOOL v39; // ebx
  unsigned int v40; // eax
  int pClipRect; // [rsp+30h] [rbp-D8h]
  int v42; // [rsp+48h] [rbp-C0h]
  int v43; // [rsp+48h] [rbp-C0h]
  int v44; // [rsp+48h] [rbp-C0h]
  unsigned int v45; // [rsp+4Ch] [rbp-BCh]
  unsigned int m_clrToolBarGradientDark; // [rsp+50h] [rbp-B8h]
  CWnd *v47; // [rsp+58h] [rbp-B0h]
  CFont *v48; // [rsp+58h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-B0h]
  CRect rectButton_8; // [rsp+68h] [rbp-A0h] OVERLAPPED BYREF
  unsigned int v51; // [rsp+78h] [rbp-90h]
  tagRECT v52; // [rsp+88h] [rbp-80h] BYREF
  CDrawingManager dm; // [rsp+98h] [rbp-70h] BYREF
  _BYTE rectCustomizeBtn[24]; // [rsp+A8h] [rbp-60h] OVERLAPPED BYREF
  __m256i rectWindow_8; // [rsp+C8h] [rbp-40h] OVERLAPPED BYREF

  v10 = 0;
  if ( !pBar || !pDC )
    AfxThrowInvalidArgException();
  if ( CObject::IsKindOf(pBar, (const CRuntimeClass *)&CMFCPropertySheetListBox::`vftable'[98])
    || (Parent = GetParent(pBar->m_hWnd), (v12 = CWnd::FromHandle(Parent)) != 0)
    && CObject::IsKindOf(v12, (const CRuntimeClass *)&CMFCPropertySheetListBox::`vftable'[98]) )
  {
    v52 = rectClient->tagRECT;
    ((void (__fastcall *)(CMFCVisualManagerOffice2003 *, CDC *, CBasePane *, tagRECT *))this->FillReBarPane)(
      this,
      pDC,
      pBar,
      &v52);
    return;
  }
  v13 = (CRuntimeClass *)pBar->GetRuntimeClass(pBar);
  m_bInitialized = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    m_bInitialized = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_nBitsPerPixel <= 8 )
    goto LABEL_90;
  if ( !m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_bIsWhiteHighContrast
    || afxGlobalData.m_bIsBlackHighContrast
    || pBar->m_bIsDlgControl
    || CRuntimeClass::IsDerivedFrom(v13, &CMFCColorBar::classCMFCColorBar) )
  {
LABEL_90:
    v52 = rectClip->tagRECT;
    *(CRect *)&rectWindow_8.m256i_u64[2] = *rectClient;
    CMFCVisualManagerOfficeXP::OnFillBarBackground(
      this,
      pDC,
      pBar,
      (CRect *)&rectWindow_8.m256i_u64[2],
      (CRect *)&v52,
      0);
    return;
  }
  if ( CObject::IsKindOf(pBar, &CMFCStatusBar::classCMFCStatusBar)
    && CMFCVisualManagerOffice2003::m_bStatusBarOfficeXPLook
    && (m_hThemeStatusBar = this->m_hThemeStatusBar) != 0
    || CObject::IsKindOf(pBar, (const CRuntimeClass *)&CMFCRibbonStatusBarCustomizeButton::`vftable'[162])
    && (m_hThemeStatusBar = this->m_hThemeStatusBar) != 0 )
  {
    DrawThemeBackground(m_hThemeStatusBar, pDC->m_hDC, 0, 0, rectClient, 0);
    return;
  }
  if ( IsRectEmpty(rectClip) )
    *rectClip = *rectClient;
  dm.m_dc = (CDC *)CDrawingManager::`vftable';
  *(_QWORD *)rectCustomizeBtn = pDC;
  if ( CObject::IsKindOf(pBar, &CMFCCaptionBar::classCMFCCaptionBar) )
  {
    *(CRect *)&rectWindow_8.m256i_u64[2] = *rectClient;
    pClipRect = 0;
    if ( !HIDWORD(pBar[2].m_pfnSuper) )
    {
      CDrawingManager::FillGradient(
        (CDrawingManager *)&dm.m_dc,
        (__m128i *)&rectWindow_8.m256i_u64[2],
        this->m_clrCaptionBarGradientDark,
        this->m_clrCaptionBarGradientLight,
        1,
        0,
        0);
      return;
    }
    m_clrBarGradientLight = this->m_clrBarGradientLight;
    m_clrBarGradientDark = this->m_clrBarGradientDark;
    goto LABEL_32;
  }
  if ( !CObject::IsKindOf(pBar, &CMFCPopupMenuBar::classCMFCPopupMenuBar) )
  {
    v20 = ((__int64 (__fastcall *)(CBasePane *))pBar->GetPaneStyle)(pBar) & 0xA000;
    v51 = v20;
    if ( !CObject::IsKindOf(pBar, &CMFCToolBar::classCMFCToolBar)
      || (IsKindOf = CObject::IsKindOf(pBar, &CMFCMenuBar::classCMFCMenuBar), v22 = 1, IsKindOf) )
    {
      v22 = 0;
    }
    v42 = v22;
    if ( v20 )
    {
      m_clrToolBarGradientDark = this->m_clrToolBarGradientDark;
      m_clrToolBarGradientLight = this->m_clrToolBarGradientLight;
    }
    else
    {
      m_clrToolBarGradientDark = this->m_clrToolBarGradientVertLight;
      m_clrToolBarGradientLight = this->m_clrToolBarGradientVertDark;
    }
    v45 = m_clrToolBarGradientLight;
    if ( !v22 )
    {
      v20 = 0;
      v51 = 0;
      m_clrToolBarGradientDark = this->m_clrBarGradientDark;
      v45 = this->m_clrBarGradientLight;
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
        v22 = v42;
      }
      rectClient->right = afxGlobalData.m_rectVirtual.right + 10 + rectClient->left - afxGlobalData.m_rectVirtual.left;
    }
    LODWORD(dm.__vftable) = v22 != 0 ? 0x19 : 0;
    v24 = CObject::IsKindOf(pBar, &CMFCDropDownToolBar::classCMFCDropDownToolBar);
    v25 = 0;
    if ( !v24 )
      v25 = bNCArea;
    *(_DWORD *)&rectCustomizeBtn[8] = v25;
    v26 = -CObject::IsKindOf(pBar, &CMFCToolBar::classCMFCToolBar);
    v27 = (CMFCToolBar *)((unsigned __int64)pBar & -(__int64)(v26 != 0));
    if ( *(_DWORD *)&rectCustomizeBtn[8]
      && v27
      && v27->IsDocked((CBasePane *)((unsigned __int64)pBar & -(__int64)(v26 != 0)))
      && v27->GetParentDockSite(v27)
      && !CObject::IsKindOf(v27, &CMFCMenuBar::classCMFCMenuBar) )
    {
      v43 = 1;
      v28 = GetParent(pBar->m_hWnd);
      v29 = CWnd::FromHandle(v28);
      v47 = v29;
      if ( v29 && CObject::IsKindOf(v29, (const CRuntimeClass *)&CBasePane::`vftable'[157]) )
      {
        *(_QWORD *)&rectCustomizeBtn[8] = 0;
        MapWindowPoints(pBar->m_hWnd, v47->m_hWnd, (LPPOINT)&rectCustomizeBtn[8], 1u);
        *(CPoint *)&rectCustomizeBtn[8] = *CDC::OffsetWindowOrg(
                                             pDC,
                                             (CPoint *)&rectButton_8,
                                             *(int *)&rectCustomizeBtn[8],
                                             *(int *)&rectCustomizeBtn[12]);
        *(_OWORD *)rectWindow_8.m256i_i8 = 0;
        GetClientRect(v47->m_hWnd, (LPRECT)&rectWindow_8);
        v30 = this->__vftable;
        rectButton_8 = (CRect)_mm_load_si128((const __m128i *)&rectWindow_8);
        v52 = rectButton_8.tagRECT;
        ((void (__fastcall *)(CMFCVisualManagerOffice2003 *, CDC *, CWnd *, tagRECT *, CRect *, _DWORD))v30->OnFillBarBackground)(
          this,
          pDC,
          v47,
          &v52,
          &rectButton_8,
          0);
        CDC::SetWindowOrg(pDC, (CPoint *)&rectButton_8, *(int *)&rectCustomizeBtn[8], *(int *)&rectCustomizeBtn[12]);
      }
      *(CRect *)&rectWindow_8.m256i_u64[2] = *rectClient;
      InflateRect((LPRECT)&rectWindow_8.m256i_u64[2], -1, 0);
      v52 = *(tagRECT *)&rectWindow_8.m256i_u64[2];
      CDrawingManager::FillGradient(
        (CDrawingManager *)&dm.m_dc,
        (__m128i *)&v52,
        m_clrToolBarGradientDark,
        v45,
        v20,
        (int)dm.__vftable,
        0);
      *(CRect *)rectWindow_8.m256i_i8 = *rectClient;
      ++rectWindow_8.m256i_i32[1];
      rectWindow_8.m256i_i32[2] = rectWindow_8.m256i_i32[0] + 1;
      v52 = *(tagRECT *)rectWindow_8.m256i_i8;
      CDrawingManager::FillGradient(
        (CDrawingManager *)&dm.m_dc,
        (__m128i *)&v52,
        m_clrToolBarGradientDark,
        v45,
        v20,
        0,
        0);
      *(CRect *)rectWindow_8.m256i_i8 = *rectClient;
      rectWindow_8.m256i_i32[0] = rectClient->right - 1;
      v52 = *(tagRECT *)rectWindow_8.m256i_i8;
      CDrawingManager::FillGradient(
        (CDrawingManager *)&dm.m_dc,
        (__m128i *)&v52,
        m_clrToolBarGradientDark,
        v45,
        v20,
        0,
        0);
    }
    else
    {
      v31 = rectClient->tagRECT;
      rectButton_8 = *rectClient;
      if ( v42 && v27 && pBar->IsDocked(pBar) && v27->GetParentDockSite(v27) )
      {
        rectButton_8.left -= v27->m_cxLeftBorder;
        rectButton_8.right += v27->m_cxRightBorder;
        rectButton_8.top -= v27->m_cyTopBorder;
        rectButton_8.bottom += v27->m_cyBottomBorder;
        v31 = rectButton_8.tagRECT;
      }
      v52 = v31;
      CDrawingManager::FillGradient(
        (CDrawingManager *)&dm.m_dc,
        (__m128i *)&v52,
        m_clrToolBarGradientDark,
        v45,
        v20,
        (int)dm.__vftable,
        0);
      v43 = 0;
      if ( !*(_DWORD *)&rectCustomizeBtn[8] )
        return;
    }
    v32 = 0;
    *(_OWORD *)&rectCustomizeBtn[8] = 0;
    SetRectEmpty((LPRECT)&rectCustomizeBtn[8]);
    if ( v27 )
    {
      m_nCount = v27->m_Buttons.m_nCount;
      if ( m_nCount > 0 )
      {
        Button = CMFCToolBar::GetButton(v27, m_nCount - 1);
        v32 = Button;
        if ( Button && CObject::IsKindOf(Button, &CMFCCustomizeButton::classCMFCCustomizeButton) )
          *(CRect *)&rectCustomizeBtn[8] = v32->m_rect;
        else
          v32 = 0;
      }
    }
    if ( v43 )
    {
      v48 = CDC::SelectObject(pDC, (CFont *)&this->m_penBottomLine);
      if ( !v48 )
        AfxThrowInvalidArgException();
      if ( v51 )
      {
        CDC::MoveTo(pDC, (CPoint *)&rectButton_8, rectClient->left + 2, rectClient->bottom - 1);
        v35 = rectClient->bottom - 1;
        v36 = rectClient->right + *(_DWORD *)&rectCustomizeBtn[8] - *(_DWORD *)&rectCustomizeBtn[16];
      }
      else
      {
        CDC::MoveTo(pDC, (CPoint *)&rectButton_8, rectClient->right - 1, rectClient->top + 2);
        v35 = *(_DWORD *)&rectCustomizeBtn[12] - *(_DWORD *)&rectCustomizeBtn[20] - 2 + rectClient->bottom;
        v36 = rectClient->right - 1;
      }
      CDC::LineTo(pDC, v36, v35);
      CDC::SelectObject(pDC, v48);
    }
    if ( v27
      && SLODWORD(v27->m_Buttons.m_nCount) > 0
      && v32
      && !IsRectEmpty((const RECT *)&rectCustomizeBtn[8])
      && LODWORD(v32[2].m_strTextCustom.m_pszData)
      && !HIDWORD(v32[2].m_strTextCustom.m_pszData) )
    {
      v51 = CWnd::GetExStyle(pBar) & 0x400000;
      *(_OWORD *)rectWindow_8.m256i_i8 = 0;
      GetWindowRect(pBar->m_hWnd, (LPRECT)&rectWindow_8);
      CWnd::ClientToScreen(pBar, (tagRECT *)&rectCustomizeBtn[8]);
      rectButton_8 = *rectClient;
      if ( v27->IsHorizontal(v27) )
      {
        if ( v51 )
          v37 = rectButton_8.right - (*(_DWORD *)&rectCustomizeBtn[16] - rectWindow_8.m256i_i32[0]);
        else
          v37 = *(_DWORD *)&rectCustomizeBtn[8] + rectButton_8.right - rectWindow_8.m256i_i32[2];
        rectButton_8.left = v37;
        LODWORD(v49) = 0;
        HIDWORD(v49) = rectWindow_8.m256i_i32[3] - *(_DWORD *)&rectCustomizeBtn[20];
      }
      else
      {
        rectButton_8.top = rectButton_8.bottom + *(_DWORD *)&rectCustomizeBtn[12] - rectWindow_8.m256i_i32[3];
        v49 = (unsigned int)(rectWindow_8.m256i_i32[2] - *(_DWORD *)&rectCustomizeBtn[16]);
      }
      *(_QWORD *)&v32[2].m_bTextBelow = v49;
      if ( CMFCToolBar::IsButtonHighlighted(v27, LODWORD(v27->m_Buttons.m_nCount) - 1) || v32->IsDroppedDown(v32) )
        v44 = 2;
      else
        v44 = (v32->m_nStyle & 0x30000) != 0;
      DrawCustomizeButton = this->DrawCustomizeButton;
      v39 = *(_QWORD *)&v32[2].m_rect.left != 0;
      LOBYTE(v10) = v32[2].m_bWholeText > 0;
      v40 = v27->IsHorizontal(v27);
      v52 = rectButton_8.tagRECT;
      ((void (__fastcall *)(CMFCVisualManagerOffice2003 *, CDC *, tagRECT *, _QWORD, int, int, BOOL))DrawCustomizeButton)(
        this,
        pDC,
        &v52,
        v40,
        v44,
        v10,
        v39);
    }
    return;
  }
  m_hObject = 0;
  if ( this != (CMFCVisualManagerOffice2003 *)-384LL )
    m_hObject = (HBRUSH)this->m_brMenuLight.m_hObject;
  FillRect(pDC->m_hDC, rectClip, m_hObject);
  v19 = (CMFCPopupMenuBar *)((unsigned __int64)pBar
                           & -(__int64)(CObject::IsKindOf(pBar, &CMFCPopupMenuBar::classCMFCPopupMenuBar) != 0));
  if ( !v19->m_bDisableSideBarInXPMode )
  {
    *(CRect *)rectWindow_8.m256i_i8 = *rectClient;
    rectWindow_8.m256i_i32[2] = rectWindow_8.m256i_i32[0] + CMFCPopupMenuBar::GetGutterWidth(v19);
    InflateRect((LPRECT)&rectWindow_8, 0, -1);
    *(_OWORD *)&rectWindow_8.m256i_u64[2] = *(_OWORD *)rectWindow_8.m256i_i8;
    pClipRect = 35;
    m_clrBarGradientLight = this->m_clrToolBarGradientDark;
    m_clrBarGradientDark = this->m_clrToolBarGradientLight;
LABEL_32:
    CDrawingManager::FillGradient(
      (CDrawingManager *)&dm.m_dc,
      (__m128i *)&rectWindow_8.m256i_u64[2],
      m_clrBarGradientDark,
      m_clrBarGradientLight,
      0,
      pClipRect,
      0);
  }
}

```

## disassembly

```asm
0x180198760  mov     rax, rsp
0x180198763  push    rbp
0x180198764  push    rbx
0x180198765  push    rsi
0x180198766  push    rdi
0x180198767  push    r12
0x180198769  push    r13
0x18019876b  push    r14
0x18019876d  push    r15
0x18019876f  lea     rbp, [rax-48h]
0x180198773  sub     rsp, 108h
0x18019877a  movaps  xmmword ptr [rax-58h], xmm6
0x18019877e  mov     rax, cs:__security_cookie
0x180198785  xor     rax, rsp
0x180198788  mov     [rbp+40h+var_60], rax
0x18019878c  mov     rdi, rectClient
0x18019878f  mov     rbx, pBar
0x180198792  mov     r13, pDC
0x180198795  mov     r15, this
0x180198798  mov     r14, qword ptr [rbp+40h+rectClip.left]
0x18019879c  xor     esi, esi
0x18019879e  test    pBar, pBar
0x1801987a1  jz      loc_180199127
0x1801987a7  test    pDC, pDC
0x1801987aa  jz      loc_180199127
0x1801987b0  lea     pDC, ??_7CMFCPropertySheetListBox@@6B@+310h; pClass
0x1801987b7  mov     this, rbx; this
0x1801987ba  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1801987bf  test    eax, eax
0x1801987c1  jnz     loc_1801990FA
0x1801987c7  mov     this, [rbx+40h]; hWnd
0x1801987cb  call    cs:__imp_GetParent
0x1801987d1  mov     this, rax; hWnd
0x1801987d4  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1801987d9  test    rax, rax
0x1801987dc  jz      short loc_1801987F5
0x1801987de  lea     pDC, ??_7CMFCPropertySheetListBox@@6B@+310h; pClass
0x1801987e5  mov     this, rax; this
0x1801987e8  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1801987ed  test    eax, eax
0x1801987ef  jnz     loc_1801990FA
0x1801987f5  mov     rax, [rbx]
0x1801987f8  mov     this, rbx
0x1801987fb  mov     rax, [rax]
0x1801987fe  call    cs:__guard_dispatch_icall_fptr
0x180198804  mov     r12, rax
0x180198807  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18019880d  test    ecx, ecx
0x18019880f  jnz     short loc_180198828
0x180198811  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180198818  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18019881d  mov     ecx, 1
0x180198822  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x180198828  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x18019882f  jle     loc_1801990C5
0x180198835  test    ecx, ecx
0x180198837  jnz     short loc_18019884F
0x180198839  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180198840  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180198845  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18019884f  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsWhiteHighContrast, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x180198855  jnz     loc_1801990C5
0x18019885b  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsBlackHighContrast, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x180198861  jnz     loc_1801990C5
0x180198867  cmp     [rbx+0F4h], esi
0x18019886d  jnz     loc_1801990C5
0x180198873  lea     pDC, ?classCMFCColorBar@CMFCColorBar@@2UCRuntimeClass@@A; pBaseClass
0x18019887a  mov     this, r12; this
0x18019887d  call    ?IsDerivedFrom@CRuntimeClass@@QEBAHPEBU1@@Z; CRuntimeClass::IsDerivedFrom(CRuntimeClass const *)
0x180198882  test    eax, eax
0x180198884  jnz     loc_1801990C5
0x18019888a  lea     pDC, ?classCMFCStatusBar@CMFCStatusBar@@2UCRuntimeClass@@B; pClass
0x180198891  mov     this, rbx; this
0x180198894  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198899  test    eax, eax
0x18019889b  jz      short loc_1801988F0
0x18019889d  cmp     cs:?m_bStatusBarOfficeXPLook@CMFCVisualManagerOffice2003@@1HA, esi; int CMFCVisualManagerOffice2003::m_bStatusBarOfficeXPLook
0x1801988a3  jz      short loc_1801988F0
0x1801988a5  mov     this, [r15+28h]; hTheme
0x1801988a9  test    this, this
0x1801988ac  jz      short loc_1801988F0
0x1801988ae  mov     qword ptr [rsp+140h+pClipRect], rsi; pClipRect
0x1801988b3  mov     [rsp+140h+pRect], rdi; pRect
0x1801988b8  xor     r9d, r9d; iStateId
0x1801988bb  xor     r8d, r8d; iPartId
0x1801988be  mov     pDC, [r13+8]; hdc
0x1801988c2  call    cs:__imp_DrawThemeBackground
0x1801988c8  mov     this, [rbp+40h+var_60]
0x1801988cc  xor     this, rsp; StackCookie
0x1801988cf  call    __security_check_cookie
0x1801988d4  movaps  xmm6, [rsp+140h+var_58+8]
0x1801988dc  add     rsp, 108h
0x1801988e3  pop     r15
0x1801988e5  pop     r14
0x1801988e7  pop     r13
0x1801988e9  pop     r12
0x1801988eb  pop     rdi
0x1801988ec  pop     rsi
0x1801988ed  pop     rbx
0x1801988ee  pop     rbp
0x1801988ef  retn
0x1801988f0  lea     pDC, ??_7CMFCRibbonStatusBarCustomizeButton@@6B@+510h; pClass
0x1801988f7  mov     this, rbx; this
0x1801988fa  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1801988ff  test    eax, eax
0x180198901  jz      short loc_18019890C
0x180198903  mov     this, [r15+28h]
0x180198907  test    this, this
0x18019890a  jnz     short loc_1801988AE
0x18019890c  mov     this, r14; lprc
0x18019890f  call    cs:__imp_IsRectEmpty
0x180198915  test    eax, eax
0x180198917  jz      short loc_180198921
0x180198919  movups  xmm0, xmmword ptr [rdi]
0x18019891c  movdqu  xmmword ptr [r14], xmm0
0x180198921  lea     rax, ??_7CDrawingManager@@6B@; const CDrawingManager::`vftable'
0x180198928  mov     [rbp+40h+dm.m_dc], rax
0x18019892c  mov     qword ptr [rbp+40h+rectCustomizeBtn.left], r13
0x180198930  lea     pDC, ?classCMFCCaptionBar@CMFCCaptionBar@@2UCRuntimeClass@@B; pClass
0x180198937  mov     this, rbx; this
0x18019893a  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18019893f  test    eax, eax
0x180198941  jz      short loc_180198991
0x180198943  movups  xmm0, xmmword ptr [rdi]
0x180198946  mov     [rsp+140h+pClipRect+8], esi
0x18019894a  lea     pDC, [rbp+40h+rectFill.right]
0x18019894e  lea     this, [rbp+40h+dm.m_dc]
0x180198952  movdqu  xmmword ptr [rbp+40h+rectFill.right], xmm0
0x180198957  mov     [rsp+140h+pClipRect], esi
0x18019895b  cmp     [rbx+404h], esi
0x180198961  jz      short loc_180198976
0x180198963  mov     r9d, [r15+218h]
0x18019896a  mov     r8d, [r15+214h]
0x180198971  jmp     loc_180198A35
0x180198976  mov     dword ptr [rsp+140h+pRect], 1
0x18019897e  mov     r9d, [r15+264h]
0x180198985  mov     r8d, [r15+268h]
0x18019898c  jmp     loc_180198A39
0x180198991  lea     pDC, ?classCMFCPopupMenuBar@CMFCPopupMenuBar@@2UCRuntimeClass@@A; pClass
0x180198998  mov     this, rbx; this
0x18019899b  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1801989a0  test    eax, eax
0x1801989a2  jz      loc_180198A44
0x1801989a8  lea     rax, [r15+180h]
0x1801989af  test    rax, rax
0x1801989b2  mov     pBar, rsi
0x1801989b5  jz      short loc_1801989BB
0x1801989b7  mov     pBar, [rax+8]; hbr
0x1801989bb  mov     pDC, r14; lprc
0x1801989be  mov     this, [r13+8]; hDC
0x1801989c2  call    cs:__imp_FillRect
0x1801989c8  lea     pDC, ?classCMFCPopupMenuBar@CMFCPopupMenuBar@@2UCRuntimeClass@@A; pClass
0x1801989cf  mov     this, rbx; this
0x1801989d2  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1801989d7  neg     eax
0x1801989d9  sbb     this, this
0x1801989dc  and     this, rbx; this
0x1801989df  cmp     [this+1350h], esi
0x1801989e5  jnz     short loc_180198A3F
0x1801989e7  movups  xmm0, xmmword ptr [rdi]
0x1801989ea  movdqu  xmmword ptr [rbp+40h+rectWindow.right], xmm0
0x1801989ef  call    ?GetGutterWidth@CMFCPopupMenuBar@@QEAAHXZ; CMFCPopupMenuBar::GetGutterWidth(void)
0x1801989f4  add     eax, [rbp+40h+rectWindow.right]
0x1801989f7  mov     [rbp+40h+rectFill.left], eax
0x1801989fa  or      r8d, 0FFFFFFFFh; dy
0x1801989fe  xor     edx, edx; dx
0x180198a00  lea     this, [rbp+40h+rectWindow.right]; lprc
0x180198a04  call    cs:__imp_InflateRect
0x180198a0a  movaps  xmm0, xmmword ptr [rbp+40h+rectWindow.right]
0x180198a0e  movdqa  xmmword ptr [rbp+40h+rectFill.right], xmm0
0x180198a13  mov     [rsp+140h+pClipRect+8], esi
0x180198a17  mov     [rsp+140h+pClipRect], 23h ; '#'
0x180198a1f  mov     r9d, [r15+21Ch]
0x180198a26  mov     r8d, [r15+220h]
0x180198a2d  lea     pDC, [rbp+40h+rectFill.right]
0x180198a31  lea     this, [rbp+40h+dm.m_dc]
0x180198a35  mov     dword ptr [rsp+140h+pRect], esi
0x180198a39  call    ?FillGradient@CDrawingManager@@QEAAXVCRect@@KKHHH@Z; CDrawingManager::FillGradient(CRect,ulong,ulong,int,int,int)
0x180198a3e  nop
0x180198a3f  jmp     loc_1801988C8
0x180198a44  mov     rax, [rbx]
0x180198a47  mov     this, rbx
0x180198a4a  mov     rax, [rax+390h]
0x180198a51  call    cs:__guard_dispatch_icall_fptr
0x180198a57  mov     r12d, eax
0x180198a5a  and     r12d, 0A000h
0x180198a61  mov     [rsp+140h+var_D0], r12d
0x180198a66  lea     pDC, ?classCMFCToolBar@CMFCToolBar@@2UCRuntimeClass@@A; pClass
0x180198a6d  mov     this, rbx; this
0x180198a70  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198a75  test    eax, eax
0x180198a77  jz      short loc_180198A91
0x180198a79  lea     pDC, ?classCMFCMenuBar@CMFCMenuBar@@2UCRuntimeClass@@A; pClass
0x180198a80  mov     this, rbx; this
0x180198a83  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198a88  test    eax, eax
0x180198a8a  mov     edx, 1
0x180198a8f  jz      short loc_180198A93
0x180198a91  mov     edx, esi
0x180198a93  mov     [rsp+140h+var_100], edx
0x180198a97  test    r12d, r12d
0x180198a9a  jz      short loc_180198AB0
0x180198a9c  mov     ecx, [r15+21Ch]
0x180198aa3  mov     dword ptr [rsp+140h+var_F8], ecx
0x180198aa7  mov     eax, [r15+220h]
0x180198aae  jmp     short loc_180198AC2
0x180198ab0  mov     eax, [r15+228h]
0x180198ab7  mov     dword ptr [rsp+140h+var_F8], eax
0x180198abb  mov     eax, [r15+22Ch]
0x180198ac2  mov     [rsp+44h], eax
0x180198ac6  test    edx, edx
0x180198ac8  jnz     short loc_180198B1F
0x180198aca  mov     r12d, esi
0x180198acd  mov     [rsp+140h+var_D0], esi
0x180198ad1  mov     eax, [r15+214h]
0x180198ad8  mov     dword ptr [rsp+140h+var_F8], eax
0x180198adc  mov     eax, [r15+218h]
0x180198ae3  mov     [rsp+44h], eax
0x180198ae7  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x180198aed  jnz     short loc_180198B09
0x180198aef  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180198af6  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180198afb  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180198b05  mov     edx, [rsp+140h+var_100]
0x180198b09  mov     ecx, [rdi]
0x180198b0b  sub     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_rectVirtual.left; AFX_GLOBAL_DATA afxGlobalData ...
0x180198b11  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_rectVirtual.right; AFX_GLOBAL_DATA afxGlobalData ...
0x180198b17  add     eax, 0Ah
0x180198b1a  add     ecx, eax
0x180198b1c  mov     [rdi+8], ecx
0x180198b1f  mov     eax, edx
0x180198b21  neg     eax
0x180198b23  sbb     eax, eax
0x180198b25  and     eax, 19h
0x180198b28  mov     dword ptr [rbp+40h+dm.__vftable], eax
0x180198b2b  lea     pDC, ?classCMFCDropDownToolBar@CMFCDropDownToolBar@@2UCRuntimeClass@@A; pClass
0x180198b32  mov     this, rbx; this
0x180198b35  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198b3a  mov     ecx, esi
0x180198b3c  test    eax, eax
0x180198b3e  cmovz   ecx, [rbp+40h+rectClip.right]
0x180198b42  mov     [rbp+40h+rectCustomizeBtn.right], ecx
0x180198b45  lea     pDC, ?classCMFCToolBar@CMFCToolBar@@2UCRuntimeClass@@A; pClass
0x180198b4c  mov     this, rbx; this
0x180198b4f  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198b54  neg     eax
0x180198b56  sbb     r14, r14
0x180198b59  and     r14, rbx
0x180198b5c  cmp     [rbp+40h+rectCustomizeBtn.right], esi
0x180198b5f  jz      loc_180198D75
0x180198b65  test    r14, r14
0x180198b68  jz      loc_180198D75
0x180198b6e  mov     rax, [r14]
0x180198b71  mov     this, r14
0x180198b74  mov     rax, [rax+2E0h]
0x180198b7b  call    cs:__guard_dispatch_icall_fptr
0x180198b81  test    eax, eax
0x180198b83  jz      loc_180198D75
0x180198b89  mov     rax, [r14]
0x180198b8c  mov     this, r14
0x180198b8f  mov     rax, [rax+350h]
0x180198b96  call    cs:__guard_dispatch_icall_fptr
0x180198b9c  test    rax, rax
0x180198b9f  jz      loc_180198D75
0x180198ba5  lea     pDC, ?classCMFCMenuBar@CMFCMenuBar@@2UCRuntimeClass@@A; pClass
0x180198bac  mov     this, r14; this
0x180198baf  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198bb4  test    eax, eax
0x180198bb6  jnz     loc_180198D75
0x180198bbc  mov     [rsp+140h+var_100], 1
0x180198bc4  mov     this, [rbx+40h]; hWnd
0x180198bc8  call    cs:__imp_GetParent
0x180198bce  mov     this, rax; hWnd
0x180198bd1  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180198bd6  mov     [rsp+50h], rax
0x180198bdb  test    rax, rax
0x180198bde  jz      loc_180198CA2
0x180198be4  lea     pDC, ??_7CBasePane@@6B@+4E8h; pClass
0x180198beb  mov     this, rax; this
0x180198bee  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180198bf3  test    eax, eax
0x180198bf5  jz      loc_180198CA2
0x180198bfb  mov     qword ptr [rbp+40h+rectCustomizeBtn.right], rsi
0x180198bff  mov     r9d, 1; cPoints
0x180198c05  lea     pBar, [rbp+40h+rectCustomizeBtn.right]; lpPoints
0x180198c09  mov     this, [rsp+50h]
0x180198c0e  mov     pDC, [this+40h]; hWndTo
0x180198c12  mov     this, [rbx+40h]; hWndFrom
0x180198c16  call    cs:__imp_MapWindowPoints
0x180198c1c  mov     r9d, [rbp+40h+rectCustomizeBtn.bottom]; nHeight
0x180198c20  mov     r8d, [rbp+40h+rectCustomizeBtn.right]; nWidth
0x180198c24  lea     pDC, [rsp+140h+rectButton.right]; result
0x180198c29  mov     this, r13; this
0x180198c2c  call    ?OffsetWindowOrg@CDC@@QEAA?AVCPoint@@HH@Z; CDC::OffsetWindowOrg(int,int)
0x180198c31  mov     this, [rax]
0x180198c34  mov     qword ptr [rbp+40h+rectCustomizeBtn.right], this
0x180198c38  xorps   xmm0, xmm0
0x180198c3b  movdqa  xmmword ptr [rbp+40h+rectWindow.right], xmm0
0x180198c40  lea     pDC, [rbp+40h+rectWindow.right]; lpRect
0x180198c44  mov     rax, [rsp+50h]
  ... truncated ...
```
