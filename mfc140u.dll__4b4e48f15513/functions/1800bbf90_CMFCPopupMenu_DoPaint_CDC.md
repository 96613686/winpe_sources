# CMFCPopupMenu::DoPaint(CDC *)

- ea: `0x1800bbf90`
- end: `0x1800bc5ec`
- name: `?DoPaint@CMFCPopupMenu@@MEAAXPEAVCDC@@@Z`
- size: `1628`
- prototype: `void __fastcall(CMFCPopupMenu *this, CDC *pPaintDC)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180126f40`

## callees

- `0x180009844`
- `0x180058b20`
- `0x1800ba970`
- `0x1800bbf90`
- `0x18023f820`
- `0x18029a620`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b6310`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetClientRect` at `0x1800bbfd2`
- `USER32!GetClientRect` at `0x1800bbfd2`
- `USER32!SetRectEmpty` at `0x1800bc02c`
- `USER32!SetRectEmpty` at `0x1800bc02c`
- `USER32!GetWindowRect` at `0x1800bc157`
- `USER32!GetWindowRect` at `0x1800bc157`
- `USER32!MapWindowPoints` at `0x1800bc08f`
- `USER32!MapWindowPoints` at `0x1800bc135`
- `USER32!MapWindowPoints` at `0x1800bc08f`
- `USER32!MapWindowPoints` at `0x1800bc135`
- `USER32!IsRectEmpty` at `0x1800bc3c9`
- `USER32!IsRectEmpty` at `0x1800bc565`
- `USER32!IsRectEmpty` at `0x1800bc3c9`
- `USER32!IsRectEmpty` at `0x1800bc565`
- `USER32!InflateRect` at `0x1800bc2ae`
- `USER32!InflateRect` at `0x1800bc2ae`
- `USER32!OffsetRect` at `0x1800bc250`
- `USER32!OffsetRect` at `0x1800bc250`
- `GDI32!BitBlt` at `0x1800bc195`
- `GDI32!BitBlt` at `0x1800bc195`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMFCPopupMenu::DoPaint(CMFCPopupMenu *this, CDC *pPaintDC)
{
  unsigned int v4; // esi
  int v5; // eax
  unsigned int v6; // ebx
  int m_iShadowSize; // ecx
  CMFCToolBarMenuButton *m_pParentBtn; // rax
  CWnd *m_pWndParent; // rcx
  CMFCVisualManager *Instance; // rax
  CMFCPopupMenu *ParentPopupMenu; // rax
  CMFCToolBarMenuButton *v12; // rcx
  CWnd *v13; // r10
  CMFCVisualManager *v14; // rax
  CMFCVisualManager *v15; // rax
  int v16; // edi
  int m_iLogoWidth; // edx
  CRect si128; // xmm0
  CMFCPopupMenu::LOGO_LOCATION m_nLogoLocation; // ecx
  __int32 v20; // ecx
  __int32 v21; // ecx
  CFrameWnd *TopLevelFrame; // rbx
  int IsKindOf; // eax
  CFrameWnd *v24; // rcx
  int v25; // eax
  CMFCVisualManager *v26; // rax
  CMFCVisualManager *v27; // rax
  CMFCVisualManager *v28; // rdi
  void (__fastcall *OnFillBarBackground)(CMFCVisualManager *, CDC *, CBasePane *, CRect, CRect, int); // rbx
  CMFCPopupMenuBar *v30; // rax
  CMFCVisualManager *v31; // rax
  CMFCVisualManager *v32; // rax
  CDrawingManager dm; // [rsp+60h] [rbp-59h] BYREF
  CRect rectFill; // [rsp+70h] [rbp-49h] BYREF
  CClientDC dcDesktop; // [rsp+80h] [rbp-39h] BYREF
  CRect rectLogo; // [rsp+B0h] [rbp-9h] BYREF
  CRect rectClient; // [rsp+C0h] [rbp+7h] BYREF
  CRect rectParentBtn; // [rsp+D0h] [rbp+17h] BYREF

  rectClient = 0;
  GetClientRect(this->m_hWnd, &rectClient);
  v4 = 0;
  if ( !this->m_iShadowSize || (v5 = 1, CMFCToolBar::m_bCustomizeMode) )
    v5 = 0;
  if ( v5 )
  {
    v6 = CWnd::GetExStyle(this) & 0x400000;
    m_iShadowSize = this->m_iShadowSize;
    if ( v6 )
      rectClient.left += m_iShadowSize;
    else
      rectClient.right -= m_iShadowSize;
    rectClient.bottom -= m_iShadowSize;
    rectParentBtn = 0;
    SetRectEmpty(&rectParentBtn);
    if ( this->m_pParentBtn )
    {
      if ( !CMFCPopupMenu::GetParentPopupMenu(this) )
      {
        m_pParentBtn = this->m_pParentBtn;
        m_pWndParent = m_pParentBtn->m_pWndParent;
        if ( m_pWndParent )
        {
          if ( m_pWndParent->m_hWnd )
          {
            rectParentBtn = m_pParentBtn->m_rect;
            rectParentBtn.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)rectParentBtn, 8)) - 1;
            --rectParentBtn.bottom;
            MapWindowPoints(m_pWndParent->m_hWnd, this->m_hWnd, (LPPOINT)&rectParentBtn, 2u);
          }
        }
      }
    }
    Instance = CMFCVisualManager::GetInstance();
    if ( Instance->IsOfficeXPStyleMenus(Instance) )
    {
      ParentPopupMenu = CMFCPopupMenu::GetParentPopupMenu(this);
      if ( ParentPopupMenu )
      {
        v12 = this->m_pParentBtn;
        if ( v12 )
        {
          if ( v12->m_bQuickCustomMode )
          {
            if ( ParentPopupMenu->m_bQuickCusomize )
            {
              if ( !this->m_bQuickCusomize && this->m_DropDirection == DROP_DIRECTION_LEFT )
              {
                v13 = v12->m_pWndParent;
                if ( v13 )
                {
                  if ( v13->m_hWnd )
                  {
                    rectParentBtn = v12->m_rect;
                    rectParentBtn.bottom = _mm_srli_si128(*(__m128i *)&rectParentBtn, 8).m128i_i32[1] + 2;
                    MapWindowPoints(v13->m_hWnd, this->m_hWnd, (LPPOINT)&rectParentBtn, 2u);
                  }
                }
              }
            }
          }
        }
      }
    }
    CClientDC::CClientDC(&dcDesktop, 0);
    rectLogo = 0;
    GetWindowRect(this->m_hWnd, &rectLogo);
    BitBlt(
      pPaintDC->m_hDC,
      0,
      0,
      rectLogo.right - rectLogo.left,
      rectLogo.bottom - rectLogo.top,
      dcDesktop.m_hDC,
      rectLogo.left,
      rectLogo.top,
      0xCC0020u);
    if ( v6 )
    {
      dm.__vftable = (CDrawingManager_vtbl *)CDrawingManager::`vftable';
      dm.m_dc = pPaintDC;
      *(_QWORD *)&rectFill.left = 0;
      rectFill.right = rectLogo.right - rectLogo.left;
      rectFill.bottom = rectLogo.bottom - rectLogo.top;
      CDrawingManager::MirrorRect(&dm, &rectFill, 1);
    }
    v14 = CMFCVisualManager::GetInstance();
    v14->OnDrawMenuShadow(
      v14,
      pPaintDC,
      &rectClient,
      &rectParentBtn,
      this->m_iShadowSize,
      100,
      65,
      &this->m_bmpShadowBottom,
      &this->m_bmpShadowRight,
      v6);
    if ( v6 )
      OffsetRect(&rectClient, -this->m_iShadowSize, 0);
    CClientDC::~CClientDC(&dcDesktop);
  }
  v15 = CMFCVisualManager::GetInstance();
  dm = (CDrawingManager)rectClient;
  ((void (__fastcall *)(CMFCVisualManager *, CDC *, CMFCPopupMenu *, CDrawingManager *))v15->OnDrawMenuBorder)(
    v15,
    pPaintDC,
    this,
    &dm);
  v16 = this->GetBorderSize(this);
  InflateRect(&rectClient, -v16, -v16);
  m_iLogoWidth = this->m_iLogoWidth;
  if ( m_iLogoWidth > 0 )
  {
    si128 = (CRect)_mm_load_si128((const __m128i *)&rectClient);
    rectLogo = si128;
    m_nLogoLocation = this->m_nLogoLocation;
    if ( m_nLogoLocation )
    {
      v20 = m_nLogoLocation - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 == 1 )
            rectLogo.top = _mm_srli_si128(*(__m128i *)&si128, 8).m128i_i32[1] - m_iLogoWidth - v16;
        }
        else
        {
          rectLogo.bottom = v16 + m_iLogoWidth + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)si128, 4));
        }
      }
      else
      {
        rectLogo.left = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)si128, 8)) - m_iLogoWidth - v16;
      }
    }
    else
    {
      rectLogo.right = _mm_cvtsi128_si32((__m128i)si128) + m_iLogoWidth + v16;
    }
    TopLevelFrame = g_pTopLevelFrame;
    if ( g_pTopLevelFrame || (TopLevelFrame = CWnd::GetTopLevelFrame(this)) != 0 )
    {
      IsKindOf = CObject::IsKindOf(TopLevelFrame, (const CRuntimeClass *)&CMDIChildWndEx::`vftable'[140]);
      v24 = TopLevelFrame;
      if ( !IsKindOf )
      {
        if ( CObject::IsKindOf(TopLevelFrame, (const CRuntimeClass *)&CFrameImpl::`vftable'[1]) )
        {
          ((void (__fastcall *)(CFrameWnd *, CDC *, CMFCPopupMenu *, CRect *))TopLevelFrame->__vftable[1].GetTypeLibCache)(
            TopLevelFrame,
            pPaintDC,
            this,
            &rectLogo);
          goto LABEL_46;
        }
        v25 = CObject::IsKindOf(TopLevelFrame, (const CRuntimeClass *)&COleDocIPFrameWndEx::`vftable'[135]);
        v24 = TopLevelFrame;
        if ( !v25 )
        {
          if ( !CObject::IsKindOf(TopLevelFrame, (const CRuntimeClass *)&COleCntrFrameWndEx::`vftable'[117]) )
            goto LABEL_46;
          v24 = TopLevelFrame;
        }
      }
      ((void (__fastcall *)(CFrameWnd *, CDC *, CMFCPopupMenu *, CRect *))TopLevelFrame->__vftable[1].GetEventSinkMap)(
        v24,
        pPaintDC,
        this,
        &rectLogo);
    }
  }
LABEL_46:
  if ( !IsRectEmpty(&this->m_rectTearOffCaption) )
  {
    v26 = CMFCVisualManager::GetInstance();
    dm = (CDrawingManager)this->m_rectTearOffCaption;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CDrawingManager *, _QWORD))v26->OnDrawTearOffCaption)(
      v26,
      pPaintDC,
      &dm,
      (unsigned int)this->m_bIsTearOffCaptionActive);
  }
  if ( this->m_bScrollable )
  {
    if ( this->IsScrollUpAvailable(this) )
    {
      v27 = CMFCVisualManager::GetInstance();
      dm = (CDrawingManager)this->m_rectScrollUp;
      ((void (__fastcall *)(CMFCVisualManager *, CDC *, CDrawingManager *, _QWORD, unsigned int, _DWORD, _DWORD))v27->OnDrawMenuScrollButton)(
        v27,
        pPaintDC,
        &dm,
        0,
        (unsigned int)this->m_iScrollMode >> 31,
        0,
        0);
    }
    if ( this->IsScrollDnAvailable(this) )
    {
      if ( this->GetMenuBar(this) )
      {
        rectFill = rectClient;
        rectFill.bottom = this->m_rectScrollDn.top;
        rectFill.top = rectFill.bottom - v16 - 1;
        v28 = CMFCVisualManager::GetInstance();
        OnFillBarBackground = v28->OnFillBarBackground;
        v30 = this->GetMenuBar(this);
        dm = (CDrawingManager)rectFill;
        ((void (__fastcall *)(CMFCVisualManager *, CDC *, CMFCPopupMenuBar *, CRect *, CDrawingManager *, _DWORD))OnFillBarBackground)(
          v28,
          pPaintDC,
          v30,
          &rectFill,
          &dm,
          0);
      }
      v31 = CMFCVisualManager::GetInstance();
      dm = (CDrawingManager)this->m_rectScrollDn;
      ((void (__fastcall *)(CMFCVisualManager *, CDC *, CDrawingManager *, __int64, bool, _DWORD, _DWORD))v31->OnDrawMenuScrollButton)(
        v31,
        pPaintDC,
        &dm,
        1,
        this->m_iScrollMode > 0,
        0,
        0);
    }
  }
  if ( !IsRectEmpty(&this->m_rectResize) )
  {
    LOBYTE(v4) = this->m_sizeMinResize.cx > 0;
    if ( this->m_bIsResizeBarOnTop )
      v4 += 2;
    v32 = CMFCVisualManager::GetInstance();
    dm = (CDrawingManager)this->m_rectResize;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CDrawingManager *, _QWORD))v32->OnDrawMenuResizeBar)(
      v32,
      pPaintDC,
      &dm,
      v4);
  }
  this->m_bShown = 1;
}

```

## disassembly

```asm
0x1800bbf90  mov     [rsp-8+arg_10], rbx
0x1800bbf95  mov     [rsp-8+arg_18], rsi
0x1800bbf9a  push    rbp
0x1800bbf9b  push    rdi
0x1800bbf9c  push    r12
0x1800bbf9e  push    r14
0x1800bbfa0  push    r15
0x1800bbfa2  lea     rbp, [rsp-37h]
0x1800bbfa7  sub     rsp, 0F0h
0x1800bbfae  mov     rax, cs:__security_cookie
0x1800bbfb5  xor     rax, rsp
0x1800bbfb8  mov     [rbp+57h+var_30], rax
0x1800bbfbc  mov     r15, pPaintDC
0x1800bbfbf  mov     r14, this
0x1800bbfc2  xorps   xmm0, xmm0
0x1800bbfc5  movdqa  xmmword ptr [rbp+57h+rectClient.left], xmm0
0x1800bbfca  lea     pPaintDC, [rbp+57h+rectClient]; lpRect
0x1800bbfce  mov     this, [this+40h]; hWnd
0x1800bbfd2  call    cs:__imp_GetClientRect
0x1800bbfd8  xor     esi, esi
0x1800bbfda  lea     r12d, [rsi+1]
0x1800bbfde  cmp     [r14+1810h], esi
0x1800bbfe5  jz      short loc_1800BBFF2
0x1800bbfe7  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, esi; int CMFCToolBar::m_bCustomizeMode
0x1800bbfed  mov     eax, r12d
0x1800bbff0  jz      short loc_1800BBFF4
0x1800bbff2  mov     eax, esi
0x1800bbff4  test    eax, eax
0x1800bbff6  jz      loc_1800BC260
0x1800bbffc  mov     this, r14; this
0x1800bbfff  call    ?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1800bc004  mov     ebx, eax
0x1800bc006  and     ebx, 400000h
0x1800bc00c  mov     ecx, [r14+1810h]
0x1800bc013  jz      short loc_1800BC01A
0x1800bc015  add     [rbp+57h+rectClient.left], ecx
0x1800bc018  jmp     short loc_1800BC01D
0x1800bc01a  sub     [rbp+57h+rectClient.right], ecx
0x1800bc01d  sub     [rbp+57h+rectClient.bottom], ecx
0x1800bc020  xorps   xmm0, xmm0
0x1800bc023  movdqu  xmmword ptr [rbp+57h+rectParentBtn.left], xmm0
0x1800bc028  lea     this, [rbp+57h+rectParentBtn]; lprc
0x1800bc02c  call    cs:__imp_SetRectEmpty
0x1800bc032  cmp     [r14+228h], rsi
0x1800bc039  jz      short loc_1800BC095
0x1800bc03b  mov     this, r14; this
0x1800bc03e  call    ?GetParentPopupMenu@CMFCPopupMenu@@QEBAPEAV1@XZ; CMFCPopupMenu::GetParentPopupMenu(void)
0x1800bc043  test    rax, rax
0x1800bc046  jnz     short loc_1800BC095
0x1800bc048  mov     rax, [r14+228h]
0x1800bc04f  mov     this, [rax+80h]
0x1800bc056  test    this, this
0x1800bc059  jz      short loc_1800BC095
0x1800bc05b  cmp     [this+40h], rsi
0x1800bc05f  jz      short loc_1800BC095
0x1800bc061  movups  xmm0, xmmword ptr [rax+68h]
0x1800bc065  movdqu  xmmword ptr [rbp+57h+rectParentBtn.left], xmm0
0x1800bc06a  psrldq  xmm0, 8
0x1800bc06f  movd    eax, xmm0
0x1800bc073  sub     eax, r12d
0x1800bc076  mov     [rbp+57h+rectParentBtn.right], eax
0x1800bc079  sub     [rbp+57h+rectParentBtn.bottom], r12d
0x1800bc07d  mov     r9d, 2; cPoints
0x1800bc083  lea     r8, [rbp+57h+rectParentBtn]; lpPoints
0x1800bc087  mov     pPaintDC, [r14+40h]; hWndTo
0x1800bc08b  mov     this, [this+40h]; hWndFrom
0x1800bc08f  call    cs:__imp_MapWindowPoints
0x1800bc095  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800bc09a  mov     pPaintDC, rax
0x1800bc09d  mov     this, [rax]
0x1800bc0a0  mov     rax, [this+5F0h]
0x1800bc0a7  mov     this, pPaintDC
0x1800bc0aa  call    cs:__guard_dispatch_icall_fptr
0x1800bc0b0  test    eax, eax
0x1800bc0b2  jz      loc_1800BC13B
0x1800bc0b8  mov     this, r14; this
0x1800bc0bb  call    ?GetParentPopupMenu@CMFCPopupMenu@@QEBAPEAV1@XZ; CMFCPopupMenu::GetParentPopupMenu(void)
0x1800bc0c0  test    rax, rax
0x1800bc0c3  jz      short loc_1800BC13B
0x1800bc0c5  mov     this, [r14+228h]
0x1800bc0cc  test    this, this
0x1800bc0cf  jz      short loc_1800BC13B
0x1800bc0d1  cmp     [this+0ECh], esi
0x1800bc0d7  jz      short loc_1800BC13B
0x1800bc0d9  cmp     [rax+19A8h], esi
0x1800bc0df  jz      short loc_1800BC13B
0x1800bc0e1  cmp     [r14+19A8h], esi
0x1800bc0e8  jnz     short loc_1800BC13B
0x1800bc0ea  cmp     dword ptr [r14+1650h], 4
0x1800bc0f2  jnz     short loc_1800BC13B
0x1800bc0f4  mov     r10, [this+80h]
0x1800bc0fb  test    r10, r10
0x1800bc0fe  jz      short loc_1800BC13B
0x1800bc100  cmp     [r10+40h], rsi
0x1800bc104  jz      short loc_1800BC13B
0x1800bc106  movups  xmm0, xmmword ptr [this+68h]
0x1800bc10a  movdqu  xmmword ptr [rbp+57h+rectParentBtn.left], xmm0
0x1800bc10f  psrldq  xmm0, 8
0x1800bc114  movq    rax, xmm0
0x1800bc119  shr     rax, 20h
0x1800bc11d  add     eax, 2
0x1800bc120  mov     [rbp+57h+rectParentBtn.bottom], eax
0x1800bc123  mov     r9d, 2; cPoints
0x1800bc129  lea     r8, [rbp+57h+rectParentBtn]; lpPoints
0x1800bc12d  mov     pPaintDC, [r14+40h]; hWndTo
0x1800bc131  mov     this, [r10+40h]; hWndFrom
0x1800bc135  call    cs:__imp_MapWindowPoints
0x1800bc13b  xor     edx, edx; pWnd
0x1800bc13d  lea     this, [rbp+57h+dcDesktop]; this
0x1800bc141  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x1800bc146  nop
0x1800bc147  xorps   xmm0, xmm0
0x1800bc14a  movdqu  xmmword ptr [rbp+57h+rectLogo.left], xmm0
0x1800bc14f  lea     pPaintDC, [rbp+57h+rectLogo]; lpRect
0x1800bc153  mov     this, [r14+40h]; hWnd
0x1800bc157  call    cs:__imp_GetWindowRect
0x1800bc15d  mov     ecx, [rbp+57h+rectLogo.bottom]
0x1800bc160  mov     edx, [rbp+57h+rectLogo.top]
0x1800bc163  sub     ecx, edx
0x1800bc165  mov     r9d, [rbp+57h+rectLogo.right]
0x1800bc169  mov     eax, [rbp+57h+rectLogo.left]
0x1800bc16c  sub     r9d, eax; cx
0x1800bc16f  mov     [rsp+110h+rop], 0CC0020h; rop
0x1800bc177  mov     [rsp+110h+y1], edx; y1
0x1800bc17b  mov     [rsp+110h+x1], eax; x1
0x1800bc17f  mov     rax, [rbp+57h+dcDesktop.m_hDC]
0x1800bc183  mov     [rsp+110h+hdcSrc], rax; hdcSrc
0x1800bc188  mov     [rsp+110h+cy], ecx; cy
0x1800bc18c  xor     r8d, r8d; y
0x1800bc18f  xor     edx, edx; x
0x1800bc191  mov     this, [r15+8]; hdc
0x1800bc195  call    cs:__imp_BitBlt
0x1800bc19b  test    ebx, ebx
0x1800bc19d  jz      short loc_1800BC1DE
0x1800bc19f  lea     rax, ??_7CDrawingManager@@6B@; const CDrawingManager::`vftable'
0x1800bc1a6  mov     [rbp+57h+dm.__vftable], rax
0x1800bc1aa  mov     [rbp+57h+dm.m_dc], r15
0x1800bc1ae  mov     ecx, [rbp+57h+rectLogo.bottom]
0x1800bc1b1  sub     ecx, [rbp+57h+rectLogo.top]
0x1800bc1b4  mov     eax, [rbp+57h+rectLogo.right]
0x1800bc1b7  sub     eax, [rbp+57h+rectLogo.left]
0x1800bc1ba  mov     qword ptr [rbp+57h+rectFill.left], rsi
0x1800bc1be  mov     [rbp+57h+rectFill.right], eax
0x1800bc1c1  mov     [rbp+57h+rectFill.bottom], ecx
0x1800bc1c4  movaps  xmm0, xmmword ptr [rbp+57h+rectFill.left]
0x1800bc1c8  movdqa  xmmword ptr [rbp+57h+rectFill.left], xmm0
0x1800bc1cd  mov     r8d, r12d
0x1800bc1d0  lea     pPaintDC, [rbp+57h+rectFill]
0x1800bc1d4  lea     this, [rbp+57h+dm]
0x1800bc1d8  call    ?MirrorRect@CDrawingManager@@QEAAXVCRect@@H@Z; CDrawingManager::MirrorRect(CRect,int)
0x1800bc1dd  nop
0x1800bc1de  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800bc1e3  mov     r10, rax
0x1800bc1e6  mov     this, [rax]
0x1800bc1e9  mov     rax, [this+90h]
0x1800bc1f0  mov     r8d, [r14+1810h]
0x1800bc1f7  lea     this, [r14+1818h]
0x1800bc1fe  lea     pPaintDC, [r14+1828h]
0x1800bc205  mov     [rsp+110h+var_C8], ebx
0x1800bc209  mov     qword ptr [rsp+110h+rop], this
0x1800bc20e  mov     qword ptr [rsp+110h+y1], pPaintDC
0x1800bc213  mov     [rsp+110h+x1], 41h ; 'A'
0x1800bc21b  mov     dword ptr [rsp+110h+hdcSrc], 64h ; 'd'
0x1800bc223  mov     [rsp+110h+cy], r8d
0x1800bc228  lea     r9, [rbp+57h+rectParentBtn]
0x1800bc22c  lea     r8, [rbp+57h+rectClient]
0x1800bc230  mov     pPaintDC, r15
0x1800bc233  mov     this, r10
0x1800bc236  call    cs:__guard_dispatch_icall_fptr
0x1800bc23c  test    ebx, ebx
0x1800bc23e  jz      short loc_1800BC257
0x1800bc240  mov     edx, [r14+1810h]
0x1800bc247  neg     edx; dx
0x1800bc249  xor     r8d, r8d; dy
0x1800bc24c  lea     this, [rbp+57h+rectClient]; lprc
0x1800bc250  call    cs:__imp_OffsetRect
0x1800bc256  nop
0x1800bc257  lea     this, [rbp+57h+dcDesktop]; this
0x1800bc25b  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1800bc260  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800bc265  mov     r10, rax
0x1800bc268  movaps  xmm0, xmmword ptr [rbp+57h+rectClient.left]
0x1800bc26c  movdqa  xmmword ptr [rbp+57h+dm.__vftable], xmm0
0x1800bc271  mov     this, [rax]
0x1800bc274  mov     rax, [this+88h]
0x1800bc27b  lea     r9, [rbp+57h+dm]
0x1800bc27f  mov     r8, r14
0x1800bc282  mov     pPaintDC, r15
0x1800bc285  mov     this, r10
0x1800bc288  call    cs:__guard_dispatch_icall_fptr
0x1800bc28e  mov     rax, [r14]
0x1800bc291  mov     this, r14
0x1800bc294  mov     rax, [rax+428h]
0x1800bc29b  call    cs:__guard_dispatch_icall_fptr
0x1800bc2a1  mov     edi, eax
0x1800bc2a3  mov     edx, eax
0x1800bc2a5  neg     edx; dx
0x1800bc2a7  mov     r8d, edx; dy
0x1800bc2aa  lea     this, [rbp+57h+rectClient]; lprc
0x1800bc2ae  call    cs:__imp_InflateRect
0x1800bc2b4  mov     edx, [r14+1680h]
0x1800bc2bb  test    edx, edx
0x1800bc2bd  jle     loc_1800BC3BF
0x1800bc2c3  movdqa  xmm0, xmmword ptr [rbp+57h+rectClient.left]
0x1800bc2c8  movdqa  xmmword ptr [rbp+57h+rectLogo.left], xmm0
0x1800bc2cd  mov     ecx, [r14+1688h]
0x1800bc2d4  test    ecx, ecx
0x1800bc2d6  jz      short loc_1800BC322
0x1800bc2d8  sub     ecx, 1
0x1800bc2db  jz      short loc_1800BC310
0x1800bc2dd  sub     ecx, 1
0x1800bc2e0  jz      short loc_1800BC2FE
0x1800bc2e2  cmp     ecx, 1
0x1800bc2e5  jnz     short loc_1800BC32E
0x1800bc2e7  psrldq  xmm0, 8
0x1800bc2ec  movq    rax, xmm0
0x1800bc2f1  shr     rax, 20h
0x1800bc2f5  sub     eax, edx
0x1800bc2f7  sub     eax, edi
0x1800bc2f9  mov     [rbp+57h+rectLogo.top], eax
0x1800bc2fc  jmp     short loc_1800BC32E
0x1800bc2fe  psrldq  xmm0, 4
0x1800bc303  movd    ecx, xmm0
0x1800bc307  add     ecx, edx
0x1800bc309  add     ecx, edi
0x1800bc30b  mov     [rbp+57h+rectLogo.bottom], ecx
0x1800bc30e  jmp     short loc_1800BC32E
0x1800bc310  psrldq  xmm0, 8
0x1800bc315  movd    eax, xmm0
0x1800bc319  sub     eax, edx
0x1800bc31b  sub     eax, edi
0x1800bc31d  mov     [rbp+57h+rectLogo.left], eax
0x1800bc320  jmp     short loc_1800BC32E
0x1800bc322  lea     ecx, [pPaintDC+rdi]
0x1800bc325  movd    eax, xmm0
0x1800bc329  add     ecx, eax
0x1800bc32b  mov     [rbp+57h+rectLogo.right], ecx
0x1800bc32e  mov     rbx, cs:?g_pTopLevelFrame@@3PEAVCFrameWnd@@EA; CFrameWnd * g_pTopLevelFrame
0x1800bc335  test    rbx, rbx
0x1800bc338  jnz     short loc_1800BC34A
0x1800bc33a  mov     this, r14; this
0x1800bc33d  call    ?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetTopLevelFrame(void)
0x1800bc342  mov     rbx, rax
0x1800bc345  test    rax, rax
0x1800bc348  jz      short loc_1800BC3BF
0x1800bc34a  lea     pPaintDC, ??_7CMDIChildWndEx@@6B@+460h; pClass
0x1800bc351  mov     this, rbx; this
0x1800bc354  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800bc359  mov     this, rbx; this
0x1800bc35c  test    eax, eax
0x1800bc35e  jnz     short loc_1800BC3A5
0x1800bc360  lea     pPaintDC, ??_7CFrameImpl@@6B@+8; pClass
0x1800bc367  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800bc36c  mov     this, rbx; this
0x1800bc36f  test    eax, eax
0x1800bc371  jz      short loc_1800BC37F
0x1800bc373  mov     rax, [rbx]
0x1800bc376  mov     rax, [rax+3E0h]
0x1800bc37d  jmp     short loc_1800BC3AF
0x1800bc37f  lea     pPaintDC, ??_7COleDocIPFrameWndEx@@6B@+438h; pClass
0x1800bc386  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800bc38b  mov     this, rbx; this
0x1800bc38e  test    eax, eax
0x1800bc390  jnz     short loc_1800BC3A5
0x1800bc392  lea     pPaintDC, ??_7COleCntrFrameWndEx@@6B@+3A8h; pClass
0x1800bc399  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800bc39e  test    eax, eax
0x1800bc3a0  jz      short loc_1800BC3BF
0x1800bc3a2  mov     this, rbx
0x1800bc3a5  mov     rax, [rbx]
0x1800bc3a8  mov     rax, [rax+418h]
0x1800bc3af  lea     r9, [rbp+57h+rectLogo]
0x1800bc3b3  mov     r8, r14
0x1800bc3b6  mov     pPaintDC, r15
0x1800bc3b9  call    cs:__guard_dispatch_icall_fptr
0x1800bc3bf  lea     rbx, [r14+1848h]
0x1800bc3c6  mov     this, rbx; lprc
0x1800bc3c9  call    cs:__imp_IsRectEmpty
0x1800bc3cf  test    eax, eax
0x1800bc3d1  jnz     short loc_1800BC404
0x1800bc3d3  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800bc3d8  mov     r10, rax
0x1800bc3db  movups  xmm0, xmmword ptr [rbx]
0x1800bc3de  movdqu  xmmword ptr [rbp+57h+dm.__vftable], xmm0
0x1800bc3e3  mov     this, [rax]
0x1800bc3e6  mov     rax, [this+100h]
0x1800bc3ed  mov     r9d, [r14+1844h]
0x1800bc3f4  lea     r8, [rbp+57h+dm]
0x1800bc3f8  mov     pPaintDC, r15
0x1800bc3fb  mov     this, r10
0x1800bc3fe  call    cs:__guard_dispatch_icall_fptr
0x1800bc404  cmp     [r14+16A4h], esi
0x1800bc40b  jz      loc_1800BC55B
0x1800bc411  mov     rax, [r14]
0x1800bc414  mov     this, r14
0x1800bc417  mov     rax, [rax+3D8h]
0x1800bc41e  call    cs:__guard_dispatch_icall_fptr
0x1800bc424  test    eax, eax
0x1800bc426  jz      short loc_1800BC470
0x1800bc428  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
  ... truncated ...
```
