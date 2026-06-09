# CPaneContainer::AddPane(CDockablePane *)

- ea: `0x1800a6a80`
- end: `0x1800a72d6`
- name: `?AddPane@CPaneContainer@@QEAAPEAVCDockablePane@@PEAV2@@Z`
- size: `2134`
- prototype: `CDockablePane *__fastcall(CPaneContainer *this, CDockablePane *pBar)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800a6a80`
- `0x1800ab580`

## callees

- `0x1800a6a80`
- `0x1800a7d00`
- `0x1800a9b60`
- `0x1800aaa00`
- `0x18023c7e0`
- `0x18023f820`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!UnionRect` at `0x1800a70ba`
- `USER32!UnionRect` at `0x1800a70ba`
- `USER32!BeginDeferWindowPos` at `0x1800a6d71`
- `USER32!BeginDeferWindowPos` at `0x1800a6d71`
- `USER32!EndDeferWindowPos` at `0x1800a72a6`
- `USER32!EndDeferWindowPos` at `0x1800a72a6`
- `USER32!SetRectEmpty` at `0x1800a6b04`
- `USER32!SetRectEmpty` at `0x1800a6b5f`
- `USER32!SetRectEmpty` at `0x1800a6b04`
- `USER32!SetRectEmpty` at `0x1800a6b5f`
- `USER32!GetWindowRect` at `0x1800a6eab`
- `USER32!GetWindowRect` at `0x1800a6fd1`
- `USER32!GetWindowRect` at `0x1800a71b8`
- `USER32!GetWindowRect` at `0x1800a6eab`
- `USER32!GetWindowRect` at `0x1800a6fd1`
- `USER32!GetWindowRect` at `0x1800a71b8`
- `USER32!IsRectEmpty` at `0x1800a6bc6`
- `USER32!IsRectEmpty` at `0x1800a6bdf`
- `USER32!IsRectEmpty` at `0x1800a6bc6`
- `USER32!IsRectEmpty` at `0x1800a6bdf`

## pseudocode

```c
CDockablePane *__fastcall CPaneContainer::AddPane(CPaneContainer *this, CDockablePane *pBar)
{
  int IsEmpty; // eax
  CPaneContainer *m_pParentContainer; // r13
  int cx; // edi
  int cy; // esi
  int top; // eax
  CDockablePane_vtbl *v9; // rax
  int m_nRecentPercent; // r15d
  int m_bIsRecentLeftBar; // eax
  int v12; // r8d
  CPaneDivider *m_pSlider; // rax
  int v14; // eax
  int left; // r8d
  CPaneDivider *v16; // rax
  HDWP v17; // rax
  CDockablePane_vtbl *v18; // rcx
  int v19; // eax
  CPaneContainer *m_pLeftContainer; // rcx
  CDockablePane *m_pBarLeftTop; // rdx
  CDockablePane *m_pBarRightBottom; // rcx
  CPaneContainer *m_pRightContainer; // rcx
  BOOL v25; // r12d
  int IsPaneDividerHorz; // eax
  CPaneDivider *v27; // rdx
  CDockablePane *v28; // rcx
  CPaneContainer *v29; // rcx
  CDockablePane *v30; // rcx
  CPaneContainer *v31; // rcx
  int v32; // eax
  CPaneDivider *v33; // rcx
  CPaneContainer_vtbl *v34; // rax
  CPaneDivider *v35; // rcx
  CPaneDivider *v36; // r12
  CPaneContainer *v37; // rax
  CPaneContainer *v38; // rcx
  CPaneContainer *v39; // rcx
  CPaneContainer *SubPaneContainer; // rdx
  CPaneContainer *v41; // rcx
  CPaneContainer *v42; // rax
  CPaneContainer *v43; // rcx
  int m_nWidth; // r15d
  int v45; // eax
  unsigned int v46; // r15d
  int v47; // ecx
  CPaneDivider *v48; // rcx
  int pTabbedControlBar; // [rsp+30h] [rbp-79h]
  CDockablePane *pTabbedControlBara; // [rsp+30h] [rbp-79h]
  int pTabbedControlBarb; // [rsp+30h] [rbp-79h]
  int IsKindOf; // [rsp+38h] [rbp-71h]
  unsigned int v53; // [rsp+38h] [rbp-71h]
  void *hdwp; // [rsp+40h] [rbp-69h] BYREF
  CSize sizeMin; // [rsp+48h] [rbp-61h] BYREF
  CWnd *v56; // [rsp+50h] [rbp-59h]
  CRect v57; // [rsp+60h] [rbp-49h] BYREF
  CRect rectContainer; // [rsp+70h] [rbp-39h] BYREF
  CRect rectNew; // [rsp+80h] [rbp-29h] BYREF
  CRect rectSlider; // [rsp+90h] [rbp-19h] BYREF
  CRect rectSecondBar; // [rsp+A0h] [rbp-9h] BYREF
  CRect rectParentContainer; // [rsp+B0h] [rbp+7h] BYREF

  v56 = this->m_pContainerManager->GetDockSiteFrameWnd(this->m_pContainerManager);
  IsKindOf = CObject::IsKindOf(v56, &CPaneFrameWnd::classCPaneFrameWnd);
  rectContainer = 0;
  rectNew = *(CRect *)((char *)&pBar->m_recentDockInfo.m_recentSliderInfo.m_rectDockedRect + (IsKindOf != 0 ? 0x68 : 0));
  SetRectEmpty(&rectContainer);
  this->GetWindowRect(this, &rectContainer, 0);
  CWnd::ScreenToClient(v56, &rectContainer);
  IsEmpty = CPaneContainer::IsEmpty(this);
  m_pParentContainer = this->m_pParentContainer;
  pTabbedControlBar = IsEmpty;
  while ( m_pParentContainer && CPaneContainer::IsEmpty(m_pParentContainer) )
    m_pParentContainer = m_pParentContainer->m_pParentContainer;
  rectParentContainer = 0;
  SetRectEmpty(&rectParentContainer);
  if ( m_pParentContainer )
  {
    m_pParentContainer->GetWindowRect(m_pParentContainer, &rectParentContainer, 0);
    CWnd::ScreenToClient(v56, &rectParentContainer);
  }
  cx = rectContainer.right - rectContainer.left;
  if ( rectContainer.right - rectContainer.left <= 0 )
    cx = rectParentContainer.right - rectParentContainer.left;
  cy = rectContainer.bottom - rectContainer.top;
  if ( rectContainer.bottom - rectContainer.top <= 0 )
    cy = rectParentContainer.bottom - rectParentContainer.top;
  if ( !cx )
    cx = rectNew.right - rectNew.left;
  if ( !cy )
    cy = rectNew.bottom - rectNew.top;
  if ( IsRectEmpty(&rectContainer) )
  {
    if ( IsRectEmpty(&rectParentContainer) )
      goto LABEL_20;
    rectNew.left = rectParentContainer.left;
    top = rectParentContainer.top;
  }
  else
  {
    rectNew.left = rectContainer.left;
    top = rectContainer.top;
  }
  rectNew.top = top;
LABEL_20:
  v9 = pBar->__vftable;
  sizeMin.cx = 0;
  sizeMin.cy = 0;
  v9->GetMinSize(&pBar->CPane, &sizeMin);
  if ( cx < sizeMin.cx )
    cx = sizeMin.cx;
  if ( cy < sizeMin.cy )
    cy = sizeMin.cy;
  if ( IsKindOf )
    m_nRecentPercent = pBar->m_recentDockInfo.m_recentMiniFrameInfo.m_nRecentPercent;
  else
    m_nRecentPercent = pBar->m_recentDockInfo.m_recentSliderInfo.m_nRecentPercent;
  if ( m_nRecentPercent == 100 || !m_nRecentPercent )
    m_nRecentPercent = 50;
  if ( !CPaneContainer::IsEmpty(this) && this->m_pSlider )
  {
    if ( CPaneContainer::IsPaneDividerHorz(this) )
    {
      if ( IsKindOf )
        m_bIsRecentLeftBar = pBar->m_recentDockInfo.m_recentMiniFrameInfo.m_bIsRecentLeftBar;
      else
        m_bIsRecentLeftBar = pBar->m_recentDockInfo.m_recentSliderInfo.m_bIsRecentLeftBar;
      if ( m_bIsRecentLeftBar )
      {
        v12 = rectContainer.top;
        cy = m_nRecentPercent * (rectContainer.bottom - rectContainer.top) / 100;
      }
      else
      {
        m_pSlider = this->m_pSlider;
        cy = rectContainer.bottom
           - (100 - m_nRecentPercent) * (rectContainer.bottom - rectContainer.top) / 100
           - m_pSlider->m_nWidth
           - rectContainer.top;
        v12 = rectContainer.top
            - ((100 - m_nRecentPercent) * (rectContainer.bottom - rectContainer.top) / -100
             - m_pSlider->m_nWidth);
      }
      rectNew.top = v12;
    }
    else
    {
      if ( IsKindOf )
        v14 = pBar->m_recentDockInfo.m_recentMiniFrameInfo.m_bIsRecentLeftBar;
      else
        v14 = pBar->m_recentDockInfo.m_recentSliderInfo.m_bIsRecentLeftBar;
      if ( v14 )
      {
        left = rectContainer.left;
        cx = m_nRecentPercent * (rectContainer.right - rectContainer.left) / 100;
      }
      else
      {
        v16 = this->m_pSlider;
        cx = rectContainer.right
           - (100 - m_nRecentPercent) * (rectContainer.right - rectContainer.left) / 100
           - v16->m_nWidth
           - rectContainer.left;
        left = rectContainer.left
             - ((100 - m_nRecentPercent) * (rectContainer.right - rectContainer.left) / -100
              - v16->m_nWidth);
      }
      rectNew.left = left;
    }
  }
  rectNew.bottom = cy + rectNew.top;
  rectNew.right = cx + rectNew.left;
  v17 = BeginDeferWindowPos(10);
  v18 = pBar->__vftable;
  hdwp = v17;
  hdwp = v18->MoveWindow(&pBar->CPane, &rectNew, 0, v17);
  rectSlider = rectNew;
  rectSecondBar = 0;
  if ( IsKindOf )
    v19 = pBar->m_recentDockInfo.m_recentMiniFrameInfo.m_bIsRecentLeftBar;
  else
    v19 = pBar->m_recentDockInfo.m_recentSliderInfo.m_bIsRecentLeftBar;
  if ( v19 )
  {
    m_pLeftContainer = this->m_pLeftContainer;
    if ( m_pLeftContainer )
      return CPaneContainer::AddPane(m_pLeftContainer, pBar);
    m_pBarLeftTop = this->m_pBarLeftTop;
    if ( m_pBarLeftTop )
      goto LABEL_54;
    m_pBarRightBottom = this->m_pBarRightBottom;
    this->m_pBarLeftTop = pBar;
    v53 = 1;
    if ( m_pBarRightBottom )
    {
      v25 = 1;
      GetWindowRect(m_pBarRightBottom->m_hWnd, &rectSecondBar);
    }
    else
    {
      m_pRightContainer = this->m_pRightContainer;
      v25 = m_pRightContainer != 0;
      if ( m_pRightContainer )
        ((void (__fastcall *)(CPaneContainer *, CRect *))m_pRightContainer->GetWindowRect)(
          m_pRightContainer,
          &rectSecondBar);
    }
    CWnd::ScreenToClient(v56, &rectSecondBar);
    if ( this->m_pSlider )
    {
      IsPaneDividerHorz = CPaneContainer::IsPaneDividerHorz(this);
      v27 = this->m_pSlider;
      if ( IsPaneDividerHorz )
      {
        rectSlider.top = rectNew.bottom;
        rectSlider.bottom = v27->m_nWidth + rectNew.bottom;
        rectSecondBar.top = rectSlider.bottom;
      }
      else
      {
        rectSlider.left = rectNew.right;
        rectSlider.right = v27->m_nWidth + rectNew.right;
        rectSecondBar.left = rectSlider.right;
      }
    }
    v28 = this->m_pBarRightBottom;
    if ( !v28 )
    {
      v29 = this->m_pRightContainer;
      goto LABEL_78;
    }
LABEL_76:
    hdwp = v28->MoveWindow(&v28->CPane, &rectSecondBar, 0, hdwp);
    goto LABEL_80;
  }
  m_pLeftContainer = this->m_pRightContainer;
  if ( m_pLeftContainer )
    return CPaneContainer::AddPane(m_pLeftContainer, pBar);
  m_pBarLeftTop = this->m_pBarRightBottom;
  if ( m_pBarLeftTop )
  {
LABEL_54:
    ((void (__fastcall *)(CDockablePane *, CDockablePane *, __int64))pBar->AttachToTabWnd)(pBar, m_pBarLeftTop, 2);
    return 0;
  }
  v30 = this->m_pBarLeftTop;
  this->m_pBarRightBottom = pBar;
  v53 = 1;
  if ( v30 )
  {
    v25 = 1;
    GetWindowRect(v30->m_hWnd, &rectSecondBar);
  }
  else
  {
    v31 = this->m_pLeftContainer;
    v25 = v31 != 0;
    if ( v31 )
      ((void (__fastcall *)(CPaneContainer *, CRect *))v31->GetWindowRect)(v31, &rectSecondBar);
  }
  CWnd::ScreenToClient(v56, &rectSecondBar);
  if ( this->m_pSlider )
  {
    v32 = CPaneContainer::IsPaneDividerHorz(this);
    v33 = this->m_pSlider;
    if ( v32 )
    {
      rectSlider.bottom = rectNew.top;
      rectSlider.top = rectNew.top - v33->m_nWidth;
      rectSecondBar.bottom = rectSlider.top;
    }
    else
    {
      rectSlider.right = rectNew.left;
      rectSlider.left = rectNew.left - v33->m_nWidth;
      rectSecondBar.right = rectSlider.left;
    }
  }
  v28 = this->m_pBarLeftTop;
  if ( v28 )
    goto LABEL_76;
  v29 = this->m_pLeftContainer;
LABEL_78:
  if ( v29 )
  {
    v34 = v29->__vftable;
    v57 = rectSecondBar;
    ((void (__fastcall *)(CPaneContainer *, CRect *, void **, _QWORD))v34->Resize)(v29, &v57, &hdwp, 0);
  }
LABEL_80:
  v35 = this->m_pSlider;
  if ( v35 )
  {
    if ( v25 )
      hdwp = v35->MoveWindow(v35, &rectSlider, 0, hdwp);
    else
      CWnd::ShowWindow(v35, 0);
  }
  UnionRect(&rectContainer, &rectNew, &rectSecondBar);
  CWnd::ClientToScreen(v56, &rectContainer);
  if ( !pTabbedControlBar )
    goto LABEL_116;
  if ( !m_pParentContainer )
    goto LABEL_116;
  v36 = m_pParentContainer->m_pSlider;
  if ( !v36 )
    goto LABEL_116;
  v37 = m_pParentContainer->m_pLeftContainer;
  v38 = m_pParentContainer->m_pRightContainer;
  *(_QWORD *)&v57.left = v37;
  pTabbedControlBara = (CDockablePane *)v38;
  if ( !v37 )
    goto LABEL_97;
  if ( v37 == this )
  {
LABEL_95:
    pTabbedControlBarb = 1;
    v53 = 0;
LABEL_106:
    GetWindowRect(v36->m_hWnd, &rectSlider);
    m_nWidth = v36->m_nWidth;
    v45 = v36->IsHorizontal(v36);
    if ( pTabbedControlBarb )
    {
      if ( v45 )
      {
        v46 = cy + m_nWidth;
        rectSlider.top = rectContainer.bottom;
        rectSlider.bottom = v36->m_nWidth + rectContainer.bottom;
      }
      else
      {
        v46 = cx + m_nWidth;
        rectSlider.left = rectContainer.right;
        rectSlider.right = v36->m_nWidth + rectContainer.right;
      }
    }
    else
    {
      v47 = v36->m_nWidth;
      if ( v45 )
      {
        v46 = -(v47 + cy);
        rectSlider.bottom = rectContainer.top;
        rectSlider.top = rectContainer.top - v36->m_nWidth;
      }
      else
      {
        v46 = -(v47 + cx);
        rectSlider.right = rectContainer.left;
        rectSlider.left = rectContainer.left - v36->m_nWidth;
      }
    }
    CWnd::ScreenToClient(v56, &rectSlider);
    v48 = this->m_pSlider;
    if ( v48 )
      hdwp = v48->MoveWindow(v48, &rectSlider, 0, hdwp);
    m_pParentContainer->ResizePartOfPaneContainer(m_pParentContainer, v46, v53, &hdwp);
LABEL_116:
    EndDeferWindowPos(hdwp);
    return pBar;
  }
  v39 = v37->m_pLeftContainer;
  SubPaneContainer = 0;
  if ( !v39 )
    goto LABEL_92;
  SubPaneContainer = CPaneContainer::FindSubPaneContainer(v39, this, BC_FIND_BY_CONTAINER);
  if ( !SubPaneContainer )
  {
    v37 = *(CPaneContainer **)&v57.left;
LABEL_92:
    v41 = v37->m_pRightContainer;
    if ( v41 )
      SubPaneContainer = CPaneContainer::FindSubPaneContainer(v41, this, BC_FIND_BY_CONTAINER);
  }
  if ( SubPaneContainer )
    goto LABEL_95;
  v38 = (CPaneContainer *)pTabbedControlBara;
LABEL_97:
  if ( v38 )
  {
    if ( v38 != this )
    {
      v42 = 0;
      if ( !v38->m_pLeftContainer )
        goto LABEL_102;
      v42 = CPaneContainer::FindSubPaneContainer(v38->m_pLeftContainer, this, BC_FIND_BY_CONTAINER);
      if ( !v42 )
      {
        v38 = (CPaneContainer *)pTabbedControlBara;
LABEL_102:
        v43 = v38->m_pRightContainer;
        if ( v43 )
          v42 = CPaneContainer::FindSubPaneContainer(v43, this, BC_FIND_BY_CONTAINER);
        if ( !v42 )
          return pBar;
      }
    }
    pTabbedControlBarb = 0;
    goto LABEL_106;
  }
  return pBar;
}

```

## disassembly

```asm
0x1800a6a80  mov     [rsp-8+arg_10], rbx
0x1800a6a85  push    rbp
0x1800a6a86  push    rsi
0x1800a6a87  push    rdi
0x1800a6a88  push    r12
0x1800a6a8a  push    r13
0x1800a6a8c  push    r14
0x1800a6a8e  push    r15
0x1800a6a90  lea     rbp, [rsp-27h]
0x1800a6a95  sub     rsp, 0D0h
0x1800a6a9c  mov     rax, cs:__security_cookie
0x1800a6aa3  xor     rax, rsp
0x1800a6aa6  mov     [rbp+57h+var_40], rax
0x1800a6aaa  mov     rbx, this
0x1800a6aad  mov     r14, pBar
0x1800a6ab0  mov     this, [this+38h]
0x1800a6ab4  mov     rax, [this]
0x1800a6ab7  mov     rax, [rax+0F8h]
0x1800a6abe  call    cs:__guard_dispatch_icall_fptr
0x1800a6ac4  mov     this, rax; this
0x1800a6ac7  mov     [rbp+57h+var_B0], rax
0x1800a6acb  lea     pBar, ?classCPaneFrameWnd@CPaneFrameWnd@@2UCRuntimeClass@@A; pClass
0x1800a6ad2  mov     rdi, rax
0x1800a6ad5  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800a6ada  mov     ecx, eax
0x1800a6adc  mov     [rbp+57h+var_C8], eax
0x1800a6adf  neg     ecx
0x1800a6ae1  xorps   xmm1, xmm1
0x1800a6ae4  lea     this, [rbp+57h+rectContainer]; lprc
0x1800a6ae8  mov     r15d, eax
0x1800a6aeb  sbb     pBar, pBar
0x1800a6aee  and     edx, 68h
0x1800a6af1  movdqu  xmmword ptr [rbp+57h+rectContainer.left], xmm1
0x1800a6af6  movups  xmm0, xmmword ptr [pBar+r14+308h]
0x1800a6aff  movdqu  xmmword ptr [rbp+57h+rectNew.left], xmm0
0x1800a6b04  call    cs:__imp_SetRectEmpty
0x1800a6b0a  mov     this, [rbx]
0x1800a6b0d  lea     pBar, [rbp+57h+rectContainer]
0x1800a6b11  xor     r8d, r8d
0x1800a6b14  mov     rax, [this+28h]
0x1800a6b18  mov     this, rbx
0x1800a6b1b  call    cs:__guard_dispatch_icall_fptr
0x1800a6b21  lea     pBar, [rbp+57h+rectContainer]; lpRect
0x1800a6b25  mov     this, rdi; this
0x1800a6b28  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800a6b2d  mov     this, rbx; this
0x1800a6b30  call    ?IsEmpty@CPaneContainer@@QEBAHXZ; CPaneContainer::IsEmpty(void)
0x1800a6b35  mov     r13, [rbx+30h]
0x1800a6b39  mov     dword ptr [rbp+57h+pTabbedControlBar], eax
0x1800a6b3c  jmp     short loc_1800A6B4E
0x1800a6b3e  mov     this, r13; this
0x1800a6b41  call    ?IsEmpty@CPaneContainer@@QEBAHXZ; CPaneContainer::IsEmpty(void)
0x1800a6b46  test    eax, eax
0x1800a6b48  jz      short loc_1800A6B53
0x1800a6b4a  mov     r13, [r13+30h]
0x1800a6b4e  test    r13, r13
0x1800a6b51  jnz     short loc_1800A6B3E
0x1800a6b53  xorps   xmm0, xmm0
0x1800a6b56  lea     this, [rbp+57h+rectParentContainer]; lprc
0x1800a6b5a  movdqu  xmmword ptr [rbp+57h+rectParentContainer.left], xmm0
0x1800a6b5f  call    cs:__imp_SetRectEmpty
0x1800a6b65  test    r13, r13
0x1800a6b68  jz      short loc_1800A6B8E
0x1800a6b6a  mov     rax, [r13+0]
0x1800a6b6e  lea     pBar, [rbp+57h+rectParentContainer]
0x1800a6b72  xor     r8d, r8d
0x1800a6b75  mov     this, r13
0x1800a6b78  mov     rax, [rax+28h]
0x1800a6b7c  call    cs:__guard_dispatch_icall_fptr
0x1800a6b82  lea     pBar, [rbp+57h+rectParentContainer]; lpRect
0x1800a6b86  mov     this, rdi; this
0x1800a6b89  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800a6b8e  mov     edi, [rbp+57h+rectContainer.right]
0x1800a6b91  sub     edi, [rbp+57h+rectContainer.left]
0x1800a6b94  test    edi, edi
0x1800a6b96  jg      short loc_1800A6B9E
0x1800a6b98  mov     edi, [rbp+57h+rectParentContainer.right]
0x1800a6b9b  sub     edi, [rbp+57h+rectParentContainer.left]
0x1800a6b9e  mov     esi, [rbp+57h+rectContainer.bottom]
0x1800a6ba1  sub     esi, [rbp+57h+rectContainer.top]
0x1800a6ba4  test    esi, esi
0x1800a6ba6  jg      short loc_1800A6BAE
0x1800a6ba8  mov     esi, [rbp+57h+rectParentContainer.bottom]
0x1800a6bab  sub     esi, [rbp+57h+rectParentContainer.top]
0x1800a6bae  test    edi, edi
0x1800a6bb0  jnz     short loc_1800A6BB8
0x1800a6bb2  mov     edi, [rbp+57h+rectNew.right]
0x1800a6bb5  sub     edi, [rbp+57h+rectNew.left]
0x1800a6bb8  test    esi, esi
0x1800a6bba  jnz     short loc_1800A6BC2
0x1800a6bbc  mov     esi, [rbp+57h+rectNew.bottom]
0x1800a6bbf  sub     esi, [rbp+57h+rectNew.top]
0x1800a6bc2  lea     this, [rbp+57h+rectContainer]; lprc
0x1800a6bc6  call    cs:__imp_IsRectEmpty
0x1800a6bcc  test    eax, eax
0x1800a6bce  jnz     short loc_1800A6BDB
0x1800a6bd0  mov     eax, [rbp+57h+rectContainer.left]
0x1800a6bd3  mov     [rbp+57h+rectNew.left], eax
0x1800a6bd6  mov     eax, [rbp+57h+rectContainer.top]
0x1800a6bd9  jmp     short loc_1800A6BF2
0x1800a6bdb  lea     this, [rbp+57h+rectParentContainer]; lprc
0x1800a6bdf  call    cs:__imp_IsRectEmpty
0x1800a6be5  test    eax, eax
0x1800a6be7  jnz     short loc_1800A6BF5
0x1800a6be9  mov     eax, [rbp+57h+rectParentContainer.left]
0x1800a6bec  mov     [rbp+57h+rectNew.left], eax
0x1800a6bef  mov     eax, [rbp+57h+rectParentContainer.top]
0x1800a6bf2  mov     [rbp+57h+rectNew.top], eax
0x1800a6bf5  mov     rax, [r14]
0x1800a6bf8  lea     pBar, [rbp+57h+sizeMin]
0x1800a6bfc  and     [rbp+57h+sizeMin.cx], 0
0x1800a6c00  mov     this, r14
0x1800a6c03  and     [rbp+57h+sizeMin.cy], 0
0x1800a6c07  mov     rax, [rax+4F0h]
0x1800a6c0e  call    cs:__guard_dispatch_icall_fptr
0x1800a6c14  cmp     edi, [rbp+57h+sizeMin.cx]
0x1800a6c17  cmovl   edi, [rbp+57h+sizeMin.cx]
0x1800a6c1b  cmp     esi, [rbp+57h+sizeMin.cy]
0x1800a6c1e  cmovl   esi, [rbp+57h+sizeMin.cy]
0x1800a6c22  test    r15d, r15d
0x1800a6c25  jnz     short loc_1800A6C30
0x1800a6c27  mov     r15d, [r14+318h]
0x1800a6c2e  jmp     short loc_1800A6C37
0x1800a6c30  mov     r15d, [r14+380h]
0x1800a6c37  mov     r12d, 64h ; 'd'
0x1800a6c3d  cmp     r15d, r12d
0x1800a6c40  jz      short loc_1800A6C47
0x1800a6c42  test    r15d, r15d
0x1800a6c45  jnz     short loc_1800A6C4D
0x1800a6c47  mov     r15d, 32h ; '2'
0x1800a6c4d  mov     this, rbx; this
0x1800a6c50  call    ?IsEmpty@CPaneContainer@@QEBAHXZ; CPaneContainer::IsEmpty(void)
0x1800a6c55  test    eax, eax
0x1800a6c57  jnz     loc_1800A6D5C
0x1800a6c5d  cmp     qword ptr [rbx+18h], 0
0x1800a6c62  jz      loc_1800A6D5C
0x1800a6c68  mov     this, rbx; this
0x1800a6c6b  call    ?IsPaneDividerHorz@CPaneContainer@@IEBAHXZ; CPaneContainer::IsPaneDividerHorz(void)
0x1800a6c70  test    eax, eax
0x1800a6c72  jz      short loc_1800A6CE9
0x1800a6c74  cmp     [rbp+57h+var_C8], 0
0x1800a6c78  jnz     short loc_1800A6C83
0x1800a6c7a  mov     eax, [r14+31Ch]
0x1800a6c81  jmp     short loc_1800A6C8A
0x1800a6c83  mov     eax, [r14+384h]
0x1800a6c8a  test    eax, eax
0x1800a6c8c  mov     eax, 51EB851Fh
0x1800a6c91  jz      short loc_1800A6CB1
0x1800a6c93  mov     ecx, [rbp+57h+rectContainer.bottom]
0x1800a6c96  mov     r8d, [rbp+57h+rectContainer.top]
0x1800a6c9a  sub     ecx, r8d
0x1800a6c9d  imul    ecx, r15d
0x1800a6ca1  imul    ecx
0x1800a6ca3  mov     esi, edx
0x1800a6ca5  sar     esi, 5
0x1800a6ca8  mov     eax, esi
0x1800a6caa  shr     eax, 1Fh
0x1800a6cad  add     esi, eax
0x1800a6caf  jmp     short loc_1800A6CE3
0x1800a6cb1  mov     r8d, [rbp+57h+rectContainer.bottom]
0x1800a6cb5  sub     r12d, r15d
0x1800a6cb8  mov     ecx, r8d
0x1800a6cbb  mov     esi, r8d
0x1800a6cbe  sub     ecx, [rbp+57h+rectContainer.top]
0x1800a6cc1  imul    ecx, r12d
0x1800a6cc5  imul    ecx
0x1800a6cc7  sar     edx, 5
0x1800a6cca  mov     eax, edx
0x1800a6ccc  shr     eax, 1Fh
0x1800a6ccf  add     edx, eax
0x1800a6cd1  mov     rax, [rbx+18h]
0x1800a6cd5  sub     esi, edx
0x1800a6cd7  sub     esi, [rax+1B0h]
0x1800a6cdd  sub     esi, [rbp+57h+rectContainer.top]
0x1800a6ce0  sub     r8d, esi
0x1800a6ce3  mov     [rbp+57h+rectNew.top], r8d
0x1800a6ce7  jmp     short loc_1800A6D5C
0x1800a6ce9  cmp     [rbp+57h+var_C8], 0
0x1800a6ced  jnz     short loc_1800A6CF8
0x1800a6cef  mov     eax, [r14+31Ch]
0x1800a6cf6  jmp     short loc_1800A6CFF
0x1800a6cf8  mov     eax, [r14+384h]
0x1800a6cff  test    eax, eax
0x1800a6d01  mov     eax, 51EB851Fh
0x1800a6d06  jz      short loc_1800A6D26
0x1800a6d08  mov     ecx, [rbp+57h+rectContainer.right]
0x1800a6d0b  mov     r8d, [rbp+57h+rectContainer.left]
0x1800a6d0f  sub     ecx, r8d
0x1800a6d12  imul    ecx, r15d
0x1800a6d16  imul    ecx
0x1800a6d18  mov     edi, edx
0x1800a6d1a  sar     edi, 5
0x1800a6d1d  mov     eax, edi
0x1800a6d1f  shr     eax, 1Fh
0x1800a6d22  add     edi, eax
0x1800a6d24  jmp     short loc_1800A6D58
0x1800a6d26  mov     r8d, [rbp+57h+rectContainer.right]
0x1800a6d2a  sub     r12d, r15d
0x1800a6d2d  mov     ecx, r8d
0x1800a6d30  mov     edi, r8d
0x1800a6d33  sub     ecx, [rbp+57h+rectContainer.left]
0x1800a6d36  imul    ecx, r12d
0x1800a6d3a  imul    ecx
0x1800a6d3c  sar     edx, 5
0x1800a6d3f  mov     eax, edx
0x1800a6d41  shr     eax, 1Fh
0x1800a6d44  add     edx, eax
0x1800a6d46  mov     rax, [rbx+18h]
0x1800a6d4a  sub     edi, edx
0x1800a6d4c  sub     edi, [rax+1B0h]
0x1800a6d52  sub     edi, [rbp+57h+rectContainer.left]
0x1800a6d55  sub     r8d, edi
0x1800a6d58  mov     [rbp+57h+rectNew.left], r8d
0x1800a6d5c  mov     ecx, [rbp+57h+rectNew.top]
0x1800a6d5f  add     ecx, esi
0x1800a6d61  mov     [rbp+57h+rectNew.bottom], ecx
0x1800a6d64  mov     ecx, [rbp+57h+rectNew.left]
0x1800a6d67  add     ecx, edi
0x1800a6d69  mov     [rbp+57h+rectNew.right], ecx
0x1800a6d6c  mov     ecx, 0Ah; nNumWindows
0x1800a6d71  call    cs:__imp_BeginDeferWindowPos
0x1800a6d77  mov     this, [r14]
0x1800a6d7a  lea     pBar, [rbp+57h+rectNew]
0x1800a6d7e  mov     [rbp+57h+hdwp], rax
0x1800a6d82  mov     r9, rax
0x1800a6d85  xor     r8d, r8d
0x1800a6d88  mov     r10, [this+478h]
0x1800a6d8f  mov     this, r14
0x1800a6d92  mov     rax, r10
0x1800a6d95  call    cs:__guard_dispatch_icall_fptr
0x1800a6d9b  movaps  xmm0, xmmword ptr [rbp+57h+rectNew.left]
0x1800a6d9f  xor     r8d, r8d
0x1800a6da2  xorps   xmm1, xmm1
0x1800a6da5  mov     [rbp+57h+hdwp], rax
0x1800a6da9  movdqa  xmmword ptr [rbp+57h+rectSlider.left], xmm0
0x1800a6dae  movdqa  xmmword ptr [rbp+57h+rectSecondBar.left], xmm1
0x1800a6db3  cmp     [rbp+57h+var_C8], r8d
0x1800a6db7  jnz     short loc_1800A6DC2
0x1800a6db9  mov     eax, [r14+31Ch]
0x1800a6dc0  jmp     short loc_1800A6DC9
0x1800a6dc2  mov     eax, [r14+384h]
0x1800a6dc9  test    eax, eax
0x1800a6dcb  jz      loc_1800A6F11
0x1800a6dd1  mov     this, [rbx+20h]; this
0x1800a6dd5  test    this, this
0x1800a6dd8  jz      short loc_1800A6DE7
0x1800a6dda  mov     pBar, r14; pBar
0x1800a6ddd  call    ?AddPane@CPaneContainer@@QEAAPEAVCDockablePane@@PEAV2@@Z; CPaneContainer::AddPane(CDockablePane *)
0x1800a6de2  jmp     loc_1800A72AF
0x1800a6de7  mov     pBar, [rbx+8]
0x1800a6deb  test    pBar, pBar
0x1800a6dee  jz      short loc_1800A6E62
0x1800a6df0  mov     rax, [r14]
0x1800a6df3  lea     this, [rbp+57h+pTabbedControlBar]
0x1800a6df7  mov     r9d, 1
0x1800a6dfd  mov     [rbp+57h+pTabbedControlBar], r8
0x1800a6e01  mov     [rsp+100h+var_E0], this
0x1800a6e06  mov     this, r14
0x1800a6e09  mov     rax, [rax+6A8h]
0x1800a6e10  lea     r8d, [r9+1]
0x1800a6e14  call    cs:__guard_dispatch_icall_fptr
0x1800a6e1a  mov     r8, [rbp+57h+pTabbedControlBar]
0x1800a6e1e  test    r8, r8
0x1800a6e21  jz      short loc_1800A6E5A
0x1800a6e23  mov     pBar, [rbx+8]
0x1800a6e27  mov     this, [rbx+38h]
0x1800a6e2b  test    pBar, pBar
0x1800a6e2e  jz      short loc_1800A6E46
0x1800a6e30  mov     rax, [this]
0x1800a6e33  mov     rax, [rax+90h]
0x1800a6e3a  call    cs:__guard_dispatch_icall_fptr
0x1800a6e40  mov     r8, [rbp+57h+pTabbedControlBar]
0x1800a6e44  jmp     short loc_1800A6E5A
0x1800a6e46  add     this, 8; this
0x1800a6e4a  mov     pBar, r8; newElement
0x1800a6e4d  call    ?AddTail@CPtrList@@QEAAPEAU__POSITION@@PEAX@Z; CPtrList::AddTail(void *)
0x1800a6e52  mov     r8, [rbp+57h+pTabbedControlBar]
0x1800a6e56  mov     [rbx+8], r8
0x1800a6e5a  mov     rax, r8
0x1800a6e5d  jmp     loc_1800A72AF
0x1800a6e62  mov     this, [rbx+10h]
0x1800a6e66  mov     r15d, 1
0x1800a6e6c  mov     [rbx+8], r14
0x1800a6e70  mov     [rbp+57h+var_C8], r15d
0x1800a6e74  test    this, this
0x1800a6e77  jnz     short loc_1800A6EA0
0x1800a6e79  cmp     [rbx+28h], r8
0x1800a6e7d  mov     r12d, r8d
0x1800a6e80  mov     this, [rbx+28h]
0x1800a6e84  setnz   r12b
0x1800a6e88  test    this, this
0x1800a6e8b  jz      short loc_1800A6EB1
0x1800a6e8d  mov     rax, [this]
0x1800a6e90  lea     pBar, [rbp+57h+rectSecondBar]
0x1800a6e94  mov     rax, [rax+28h]
0x1800a6e98  call    cs:__guard_dispatch_icall_fptr
0x1800a6e9e  jmp     short loc_1800A6EB1
0x1800a6ea0  mov     this, [this+40h]; hWnd
0x1800a6ea4  lea     pBar, [rbp+57h+rectSecondBar]; lpRect
0x1800a6ea8  mov     r12d, r15d
  ... truncated ...
```
