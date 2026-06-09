# CMFCRibbonBar::OnPaint(void)

- ea: `0x1800dedc0`
- end: `0x1800df2fa`
- name: `?OnPaint@CMFCRibbonBar@@IEAAXXZ`
- size: `1338`
- prototype: `void __fastcall(CMFCRibbonBar *this)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180009844`
- `0x18001d090`
- `0x18006c260`
- `0x18006c690`
- `0x1800dedc0`
- `0x180231d70`
- `0x1802af260`
- `0x1802af8a0`
- `0x1802b0810`
- `0x1802b08c0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b2580`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetClientRect` at `0x1800dee9a`
- `USER32!GetClientRect` at `0x1800dee9a`
- `USER32!SendMessageW` at `0x1800deedb`
- `USER32!SendMessageW` at `0x1800deedb`
- `USER32!IsRectEmpty` at `0x1800dee4d`
- `USER32!IsRectEmpty` at `0x1800def0e`
- `USER32!IsRectEmpty` at `0x1800defb7`
- `USER32!IsRectEmpty` at `0x1800df108`
- `USER32!IsRectEmpty` at `0x1800df230`
- `USER32!IsRectEmpty` at `0x1800dee4d`
- `USER32!IsRectEmpty` at `0x1800def0e`
- `USER32!IsRectEmpty` at `0x1800defb7`
- `USER32!IsRectEmpty` at `0x1800df108`
- `USER32!IsRectEmpty` at `0x1800df230`
- `GDI32!CreateRectRgnIndirect` at `0x1800dee5b`
- `GDI32!CreateRectRgnIndirect` at `0x1800dee5b`
- `GDI32!GetClipBox` at `0x1800dee32`
- `GDI32!GetClipBox` at `0x1800dee32`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CMFCRibbonBar::OnPaint(CMFCRibbonBar *this)
{
  CDC *p_m_dcMem; // rsi
  HRGN v3; // rax
  CMFCRibbonBar_vtbl *v4; // rax
  CFont *(__fastcall *SelectObject)(CDC *, CFont *); // rbx
  void *v6; // rax
  CGdiObject *v7; // rax
  __int64 v8; // r13
  CRect *p_m_rectCaption; // r14
  CMFCVisualManager *Instance; // r10
  void (__fastcall *OnDrawRibbonCaption)(CMFCVisualManager *, CDC *, CMFCRibbonBar *, CRect, CRect); // rax
  CMFCRibbonCaptionButton *m_CaptionButtons; // rbx
  CMFCRibbonCaptionButton *v13; // r15
  __int64 v14; // r12
  int v15; // r15d
  __int64 v16; // rbx
  CMFCRibbonContextCaption *v17; // rcx
  unsigned int v18; // ebx
  CMFCVisualManager *v19; // rax
  unsigned int v20; // eax
  CMFCRibbonCategory *m_pActiveCategory; // rcx
  BOOL v22; // eax
  int top; // ecx
  CMFCVisualManager *v24; // r10
  unsigned int (__fastcall *OnDrawRibbonTabsFrame)(CMFCVisualManager *, CDC *, CMFCRibbonBar *, CRect); // rax
  unsigned int v26; // r15d
  int v27; // r14d
  __int64 v28; // rbx
  CMFCRibbonCategory *v29; // rcx
  unsigned int v30; // ebx
  CMFCRibbonApplicationButton *m_pMainButton; // rax
  CMFCVisualManager *v32; // rax
  CRgn rgnClip; // [rsp+30h] [rbp-D0h] BYREF
  CRect m_rectCaptionText; // [rsp+40h] [rbp-C0h] BYREF
  CRect rectFill; // [rsp+50h] [rbp-B0h] BYREF
  RECT rc; // [rsp+60h] [rbp-A0h] BYREF
  CRect rectClient; // [rsp+70h] [rbp-90h] BYREF
  CRect rectClip; // [rsp+80h] [rbp-80h] BYREF
  CMemDC memDC; // [rsp+90h] [rbp-70h] BYREF
  CPaintDC dc; // [rsp+100h] [rbp+0h] BYREF

  CPaintDC::CPaintDC(&dc, this);
  CMemDC::CMemDC(&memDC, &dc, this);
  p_m_dcMem = &memDC.m_dcMem;
  if ( !memDC.m_bMemDC )
    p_m_dcMem = memDC.m_dc;
  rectClip = 0;
  GetClipBox(dc.m_hDC, &rectClip);
  rgnClip.m_hObject = 0;
  rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  if ( !IsRectEmpty(&rectClip) )
  {
    v3 = CreateRectRgnIndirect(&rectClip);
    CGdiObject::Attach(&rgnClip, v3);
    CDC::SelectClipRgn(p_m_dcMem, &rgnClip);
  }
  CDC::SetBkMode(p_m_dcMem, 1);
  rectClient = 0;
  GetClientRect(this->m_hWnd, &rectClient);
  v4 = this->__vftable;
  rectFill = rectClient;
  ((void (__fastcall *)(CMFCRibbonBar *, CDC *, CRect *))v4->OnFillBackground)(this, p_m_dcMem, &rectFill);
  SelectObject = p_m_dcMem->SelectObject;
  v6 = (void *)SendMessageW(this->m_hWnd, 0x31u, 0, 0);
  v7 = CGdiObject::FromHandle(v6);
  v8 = (__int64)SelectObject(p_m_dcMem, (CFont *)v7);
  if ( !v8 )
    goto LABEL_47;
  p_m_rectCaption = &this->m_rectCaption;
  if ( !IsRectEmpty(&this->m_rectCaption) )
  {
    rectFill = *p_m_rectCaption;
    rectFill.top = 0;
    if ( this->m_bIsTransparentCaption )
    {
      CDC::FillSolidRect(p_m_dcMem, &rectFill, 0);
      CMFCToolBarImages::m_bIsDrawOnGlass = 1;
    }
    Instance = CMFCVisualManager::GetInstance();
    OnDrawRibbonCaption = Instance->OnDrawRibbonCaption;
    m_rectCaptionText = this->m_rectCaptionText;
    rc = p_m_rectCaption->tagRECT;
    ((void (__fastcall *)(CMFCVisualManager *, CDC *, CMFCRibbonBar *, RECT *, CRect *))OnDrawRibbonCaption)(
      Instance,
      p_m_dcMem,
      this,
      &rc,
      &m_rectCaptionText);
    m_CaptionButtons = this->m_CaptionButtons;
    v13 = this->m_CaptionButtons;
    v14 = 3;
    do
    {
      rc = (RECT)m_CaptionButtons->m_rect;
      if ( !IsRectEmpty(&rc) )
        m_CaptionButtons->OnDraw(v13, p_m_dcMem);
      ++v13;
      ++m_CaptionButtons;
      --v14;
    }
    while ( v14 );
    v15 = 0;
    if ( SLODWORD(this->m_arContextCaptions.m_nSize) > 0 )
    {
      v16 = 0;
      do
      {
        if ( v16 < 0 || v16 >= this->m_arContextCaptions.m_nSize )
          AfxThrowInvalidArgException();
        v17 = this->m_arContextCaptions.m_pData[v16];
        v17->OnDraw(v17, p_m_dcMem);
        ++v15;
        ++v16;
      }
      while ( v15 < SLODWORD(this->m_arContextCaptions.m_nSize) );
    }
    CMFCToolBarImages::m_bIsDrawOnGlass = 0;
  }
  if ( this->m_bIsTransparentCaption && this->m_bQuickAccessToolbarOnTop )
    CMFCToolBarImages::m_bIsDrawOnGlass = 1;
  v18 = -1;
  v19 = CMFCVisualManager::GetInstance();
  v20 = v19->GetRibbonQuickAccessToolBarTextColor(v19, 0);
  if ( v20 != -1 )
    v18 = p_m_dcMem->SetTextColor(p_m_dcMem, v20);
  this->m_QAToolbar.OnDraw(&this->m_QAToolbar, p_m_dcMem);
  if ( v18 != -1 )
    p_m_dcMem->SetTextColor(p_m_dcMem, v18);
  CMFCToolBarImages::m_bIsDrawOnGlass = 0;
  m_pActiveCategory = this->m_pActiveCategory;
  if ( m_pActiveCategory && !this->m_dwHideFlags )
    m_pActiveCategory->OnDraw(m_pActiveCategory, p_m_dcMem);
  rectFill = rectClient;
  v22 = IsRectEmpty(&this->m_rectCaption);
  top = rectClient.top;
  if ( !v22 )
    top = this->m_rectCaption.bottom;
  rectFill.top = top;
  rectFill.bottom = this->m_nTabsHeight + top;
  v24 = CMFCVisualManager::GetInstance();
  OnDrawRibbonTabsFrame = v24->OnDrawRibbonTabsFrame;
  rc = rectFill.tagRECT;
  v26 = ((__int64 (__fastcall *)(CMFCVisualManager *, CDC *, CMFCRibbonBar *, RECT *))OnDrawRibbonTabsFrame)(
          v24,
          p_m_dcMem,
          this,
          &rc);
  v27 = 0;
  if ( SLODWORD(this->m_arCategories.m_nSize) > 0 )
  {
    v28 = 0;
    while ( v28 >= 0 && v28 < this->m_arCategories.m_nSize )
    {
      v29 = this->m_arCategories.m_pData[v28];
      if ( v29->m_bIsVisible )
        v29->m_Tab.OnDraw(&v29->m_Tab, p_m_dcMem);
      ++v27;
      ++v28;
      if ( v27 >= SLODWORD(this->m_arCategories.m_nSize) )
        goto LABEL_38;
    }
LABEL_47:
    AfxThrowInvalidArgException();
  }
LABEL_38:
  v30 = -1;
  if ( v26 != -1 )
    v30 = p_m_dcMem->SetTextColor(p_m_dcMem, v26);
  this->m_TabElements.OnDraw(&this->m_TabElements, p_m_dcMem);
  if ( v30 != -1 )
    p_m_dcMem->SetTextColor(p_m_dcMem, v30);
  m_pMainButton = this->m_pMainButton;
  if ( m_pMainButton )
  {
    rc = (RECT)m_pMainButton->m_rect;
    if ( !IsRectEmpty(&rc) )
    {
      v32 = CMFCVisualManager::GetInstance();
      v32->OnDrawRibbonApplicationButton(v32, p_m_dcMem, this->m_pMainButton);
      this->m_pMainButton->OnDraw(this->m_pMainButton, p_m_dcMem);
    }
  }
  p_m_dcMem->SelectObject(p_m_dcMem, (CFont *)v8);
  CDC::SelectClipRgn(p_m_dcMem, 0);
  rgnClip.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnClip);
  CMemDC::~CMemDC(&memDC);
  CPaintDC::~CPaintDC(&dc);
}

```

## disassembly

```asm
0x1800dedc0  mov     [rsp-8+arg_8], rbx
0x1800dedc5  mov     [rsp-8+arg_10], rsi
0x1800dedca  mov     [rsp-8+arg_18], rdi
0x1800dedcf  push    rbp
0x1800dedd0  push    r12
0x1800dedd2  push    r13
0x1800dedd4  push    r14
0x1800dedd6  push    r15
0x1800dedd8  lea     rbp, [rsp-80h]
0x1800deddd  sub     rsp, 180h
0x1800dede4  mov     rax, cs:__security_cookie
0x1800dedeb  xor     rax, rsp
0x1800dedee  mov     [rbp+0A0h+var_30], rax
0x1800dedf2  mov     rdi, this
0x1800dedf5  mov     rdx, this; pWnd
0x1800dedf8  lea     this, [rbp+0A0h+dc]; this
0x1800dedfc  call    ??0CPaintDC@@QEAA@PEAVCWnd@@@Z; CPaintDC::CPaintDC(CWnd *)
0x1800dee01  nop
0x1800dee02  mov     r8, rdi; pWnd
0x1800dee05  lea     rdx, [rbp+0A0h+dc]; dc
0x1800dee09  lea     this, [rbp+0A0h+memDC]; this
0x1800dee0d  call    ??0CMemDC@@QEAA@AEAVCDC@@PEAVCWnd@@@Z; CMemDC::CMemDC(CDC &,CWnd *)
0x1800dee12  nop
0x1800dee13  lea     rsi, [rbp+0A0h+memDC.m_dcMem]
0x1800dee17  xor     r12d, r12d
0x1800dee1a  cmp     [rbp+0A0h+memDC.m_bMemDC], r12d
0x1800dee1e  cmovz   rsi, [rbp+0A0h+memDC.m_dc]
0x1800dee23  xorps   xmm0, xmm0
0x1800dee26  movups  xmmword ptr [rbp+0A0h+rectClip.left], xmm0
0x1800dee2a  lea     rdx, [rbp+0A0h+rectClip]; lprect
0x1800dee2e  mov     this, [rbp+0A0h+dc.m_hDC]; hdc
0x1800dee32  call    cs:__imp_GetClipBox
0x1800dee38  mov     [rsp+1A0h+rgnClip.m_hObject], r12
0x1800dee3d  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800dee44  mov     [rsp+1A0h+rgnClip.__vftable], rax
0x1800dee49  lea     this, [rbp+0A0h+rectClip]; lprc
0x1800dee4d  call    cs:__imp_IsRectEmpty
0x1800dee53  test    eax, eax
0x1800dee55  jnz     short loc_1800DEE7B
0x1800dee57  lea     this, [rbp+0A0h+rectClip]; lprect
0x1800dee5b  call    cs:__imp_CreateRectRgnIndirect
0x1800dee61  mov     rdx, rax; hObject
0x1800dee64  lea     this, [rsp+1A0h+rgnClip]; this
0x1800dee69  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800dee6e  lea     rdx, [rsp+1A0h+rgnClip]; pRgn
0x1800dee73  mov     this, rsi; this
0x1800dee76  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800dee7b  mov     edx, 1; nBkMode
0x1800dee80  mov     this, rsi; this
0x1800dee83  call    ?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x1800dee88  xorps   xmm0, xmm0
0x1800dee8b  movdqa  xmmword ptr [rsp+1A0h+rectClient.left], xmm0
0x1800dee91  lea     rdx, [rsp+1A0h+rectClient]; lpRect
0x1800dee96  mov     this, [rdi+40h]; hWnd
0x1800dee9a  call    cs:__imp_GetClientRect
0x1800deea0  mov     rax, [rdi]
0x1800deea3  movaps  xmm0, xmmword ptr [rsp+1A0h+rectClient.left]
0x1800deea8  movdqa  xmmword ptr [rsp+1A0h+rectFill.left], xmm0
0x1800deeae  lea     r8, [rsp+1A0h+rectFill]
0x1800deeb3  mov     rdx, rsi
0x1800deeb6  mov     this, rdi
0x1800deeb9  mov     rax, [rax+6C0h]
0x1800deec0  call    cs:__guard_dispatch_icall_fptr
0x1800deec6  mov     rax, [rsi]
0x1800deec9  mov     rbx, [rax+60h]
0x1800deecd  xor     r9d, r9d; lParam
0x1800deed0  xor     r8d, r8d; wParam
0x1800deed3  lea     edx, [r9+31h]; Msg
0x1800deed7  mov     this, [rdi+40h]; hWnd
0x1800deedb  call    cs:__imp_SendMessageW
0x1800deee1  mov     this, rax; h
0x1800deee4  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800deee9  mov     rdx, rax
0x1800deeec  mov     this, rsi
0x1800deeef  mov     rax, rbx
0x1800deef2  call    cs:__guard_dispatch_icall_fptr
0x1800deef8  mov     r13, rax
0x1800deefb  test    rax, rax
0x1800deefe  jz      loc_1800DF2F4
0x1800def04  lea     r14, [rdi+0BC8h]
0x1800def0b  mov     this, r14; lprc
0x1800def0e  call    cs:__imp_IsRectEmpty
0x1800def14  test    eax, eax
0x1800def16  jnz     loc_1800DF041
0x1800def1c  movups  xmm0, xmmword ptr [r14]
0x1800def20  movdqu  xmmword ptr [rsp+1A0h+rectFill.left], xmm0
0x1800def26  mov     [rsp+1A0h+rectFill.top], r12d
0x1800def2b  cmp     [rdi+448h], r12d
0x1800def32  jz      short loc_1800DEF4E
0x1800def34  xor     r8d, r8d; clr
0x1800def37  lea     rdx, [rsp+1A0h+rectFill]; lpRect
0x1800def3c  mov     this, rsi; this
0x1800def3f  call    ?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1800def44  mov     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, 1; int CMFCToolBarImages::m_bIsDrawOnGlass
0x1800def4e  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800def53  mov     r10, rax
0x1800def56  mov     this, [rax]
0x1800def59  mov     rax, [this+4B0h]
0x1800def60  movups  xmm0, xmmword ptr [rdi+0BD8h]
0x1800def67  movdqu  [rsp+1A0h+var_160], xmm0
0x1800def6d  movups  xmm1, xmmword ptr [r14]
0x1800def71  movdqu  xmmword ptr [rsp+1A0h+rc.left], xmm1
0x1800def77  lea     this, [rsp+1A0h+var_160]
0x1800def7c  mov     [rsp+1A0h+var_180], this
0x1800def81  lea     r9, [rsp+1A0h+rc]
0x1800def86  mov     r8, rdi
0x1800def89  mov     rdx, rsi
0x1800def8c  mov     this, r10
0x1800def8f  call    cs:__guard_dispatch_icall_fptr
0x1800def95  lea     rbx, [rdi+0C18h]
0x1800def9c  mov     r15, rbx
0x1800def9f  mov     r12d, 3
0x1800defa5  movups  xmm0, xmmword ptr [rbx+0C8h]
0x1800defac  movdqu  xmmword ptr [rsp+1A0h+rc.left], xmm0
0x1800defb2  lea     this, [rsp+1A0h+rc]; lprc
0x1800defb7  call    cs:__imp_IsRectEmpty
0x1800defbd  test    eax, eax
0x1800defbf  jnz     short loc_1800DEFD7
0x1800defc1  mov     rax, [rbx]
0x1800defc4  mov     rdx, rsi
0x1800defc7  mov     this, r15
0x1800defca  mov     rax, [rax+308h]
0x1800defd1  call    cs:__guard_dispatch_icall_fptr
0x1800defd7  mov     eax, 278h
0x1800defdc  add     r15, rax
0x1800defdf  add     rbx, rax
0x1800defe2  sub     r12, 1
0x1800defe6  jnz     short loc_1800DEFA5
0x1800defe8  mov     r15d, r12d
0x1800defeb  cmp     [rdi+0B38h], r12d
0x1800deff2  jle     short loc_1800DF03A
0x1800deff4  mov     rbx, r12
0x1800deff7  test    rbx, rbx
0x1800deffa  js      loc_1800DF2EE
0x1800df000  cmp     rbx, [rdi+0B38h]
0x1800df007  jge     loc_1800DF2EE
0x1800df00d  mov     rax, [rdi+0B30h]
0x1800df014  mov     this, [rax+rbx*8]
0x1800df018  mov     rax, [this]
0x1800df01b  mov     rdx, rsi
0x1800df01e  mov     rax, [rax+308h]
0x1800df025  call    cs:__guard_dispatch_icall_fptr
0x1800df02b  inc     r15d
0x1800df02e  inc     rbx
0x1800df031  cmp     r15d, [rdi+0B38h]
0x1800df038  jl      short loc_1800DEFF7
0x1800df03a  mov     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, r12d; int CMFCToolBarImages::m_bIsDrawOnGlass
0x1800df041  cmp     [rdi+448h], r12d
0x1800df048  jz      short loc_1800DF05D
0x1800df04a  cmp     [rdi+434h], r12d
0x1800df051  jz      short loc_1800DF05D
0x1800df053  mov     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, 1; int CMFCToolBarImages::m_bIsDrawOnGlass
0x1800df05d  or      r15d, 0FFFFFFFFh
0x1800df061  mov     ebx, r15d
0x1800df064  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800df069  mov     r8, rax
0x1800df06c  mov     this, [rax]
0x1800df06f  mov     rax, [this+4C8h]
0x1800df076  xor     edx, edx
0x1800df078  mov     this, r8
0x1800df07b  call    cs:__guard_dispatch_icall_fptr
0x1800df081  mov     edx, eax
0x1800df083  cmp     eax, r15d
0x1800df086  jz      short loc_1800DF09A
0x1800df088  mov     this, [rsi]
0x1800df08b  mov     rax, [this+70h]
0x1800df08f  mov     this, rsi
0x1800df092  call    cs:__guard_dispatch_icall_fptr
0x1800df098  mov     ebx, eax
0x1800df09a  lea     this, [rdi+1380h]
0x1800df0a1  mov     rdx, [this]
0x1800df0a4  mov     rax, [rdx+308h]
0x1800df0ab  mov     rdx, rsi
0x1800df0ae  call    cs:__guard_dispatch_icall_fptr
0x1800df0b4  cmp     ebx, r15d
0x1800df0b7  jz      short loc_1800DF0CB
0x1800df0b9  mov     rax, [rsi]
0x1800df0bc  mov     edx, ebx
0x1800df0be  mov     this, rsi
0x1800df0c1  mov     rax, [rax+70h]
0x1800df0c5  call    cs:__guard_dispatch_icall_fptr
0x1800df0cb  mov     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, r12d; int CMFCToolBarImages::m_bIsDrawOnGlass
0x1800df0d2  mov     this, [rdi+0B08h]
0x1800df0d9  test    this, this
0x1800df0dc  jz      short loc_1800DF0FA
0x1800df0de  cmp     [rdi+478h], r12d
0x1800df0e5  jnz     short loc_1800DF0FA
0x1800df0e7  mov     rax, [this]
0x1800df0ea  mov     rdx, rsi
0x1800df0ed  mov     rax, [rax+178h]
0x1800df0f4  call    cs:__guard_dispatch_icall_fptr
0x1800df0fa  movaps  xmm0, xmmword ptr [rsp+1A0h+rectClient.left]
0x1800df0ff  movdqa  xmmword ptr [rsp+1A0h+rectFill.left], xmm0
0x1800df105  mov     this, r14; lprc
0x1800df108  call    cs:__imp_IsRectEmpty
0x1800df10e  test    eax, eax
0x1800df110  mov     ecx, [rsp+1A0h+rectClient.top]
0x1800df114  jnz     short loc_1800DF11C
0x1800df116  mov     ecx, [rdi+0BD4h]
0x1800df11c  mov     [rsp+1A0h+rectFill.top], ecx
0x1800df120  add     ecx, [rdi+3F8h]
0x1800df126  mov     [rsp+1A0h+rectFill.bottom], ecx
0x1800df12a  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800df12f  mov     r10, rax
0x1800df132  mov     this, [rax]
0x1800df135  mov     rax, [this+428h]
0x1800df13c  movaps  xmm0, xmmword ptr [rsp+1A0h+rectFill.left]
0x1800df141  movdqa  xmmword ptr [rsp+1A0h+rc.left], xmm0
0x1800df147  lea     r9, [rsp+1A0h+rc]
0x1800df14c  mov     r8, rdi
0x1800df14f  mov     rdx, rsi
0x1800df152  mov     this, r10
0x1800df155  call    cs:__guard_dispatch_icall_fptr
0x1800df15b  mov     r15d, eax
0x1800df15e  mov     r14d, r12d
0x1800df161  cmp     [rdi+0B60h], r12d
0x1800df168  jle     short loc_1800DF1C0
0x1800df16a  mov     rbx, r12
0x1800df16d  test    rbx, rbx
0x1800df170  js      loc_1800DF2F4
0x1800df176  cmp     rbx, [rdi+0B60h]
0x1800df17d  jge     loc_1800DF2F4
0x1800df183  mov     rax, [rdi+0B58h]
0x1800df18a  mov     this, [rax+rbx*8]
0x1800df18e  cmp     [this+0A8h], r12d
0x1800df195  jz      short loc_1800DF1B1
0x1800df197  add     this, 0D8h
0x1800df19e  mov     rax, [this]
0x1800df1a1  mov     rdx, rsi
0x1800df1a4  mov     rax, [rax+308h]
0x1800df1ab  call    cs:__guard_dispatch_icall_fptr
0x1800df1b1  inc     r14d
0x1800df1b4  inc     rbx
0x1800df1b7  cmp     r14d, [rdi+0B60h]
0x1800df1be  jl      short loc_1800DF16D
0x1800df1c0  or      r14d, 0FFFFFFFFh
0x1800df1c4  mov     ebx, r14d
0x1800df1c7  cmp     r15d, r14d
0x1800df1ca  jz      short loc_1800DF1E1
0x1800df1cc  mov     rax, [rsi]
0x1800df1cf  mov     edx, r15d
0x1800df1d2  mov     this, rsi
0x1800df1d5  mov     rax, [rax+70h]
0x1800df1d9  call    cs:__guard_dispatch_icall_fptr
0x1800df1df  mov     ebx, eax
0x1800df1e1  lea     this, [rdi+498h]
0x1800df1e8  mov     rdx, [this]
0x1800df1eb  mov     rax, [rdx+308h]
0x1800df1f2  mov     rdx, rsi
0x1800df1f5  call    cs:__guard_dispatch_icall_fptr
0x1800df1fb  cmp     ebx, r14d
0x1800df1fe  jz      short loc_1800DF212
0x1800df200  mov     rax, [rsi]
0x1800df203  mov     edx, ebx
0x1800df205  mov     this, rsi
0x1800df208  mov     rax, [rax+70h]
0x1800df20c  call    cs:__guard_dispatch_icall_fptr
0x1800df212  mov     rax, [rdi+480h]
0x1800df219  test    rax, rax
0x1800df21c  jz      short loc_1800DF279
0x1800df21e  movups  xmm0, xmmword ptr [rax+0C8h]
0x1800df225  movdqu  xmmword ptr [rsp+1A0h+rc.left], xmm0
0x1800df22b  lea     this, [rsp+1A0h+rc]; lprc
0x1800df230  call    cs:__imp_IsRectEmpty
0x1800df236  test    eax, eax
0x1800df238  jnz     short loc_1800DF279
0x1800df23a  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800df23f  mov     r9, rax
0x1800df242  mov     this, [rax]
0x1800df245  mov     rax, [this+430h]
0x1800df24c  mov     r8, [rdi+480h]
0x1800df253  mov     rdx, rsi
0x1800df256  mov     this, r9
0x1800df259  call    cs:__guard_dispatch_icall_fptr
0x1800df25f  mov     this, [rdi+480h]
0x1800df266  mov     rax, [this]
0x1800df269  mov     rdx, rsi
0x1800df26c  mov     rax, [rax+308h]
0x1800df273  call    cs:__guard_dispatch_icall_fptr
0x1800df279  mov     rax, [rsi]
0x1800df27c  mov     rdx, r13
0x1800df27f  mov     this, rsi
0x1800df282  mov     rax, [rax+60h]
0x1800df286  call    cs:__guard_dispatch_icall_fptr
0x1800df28c  xor     edx, edx; pRgn
0x1800df28e  mov     this, rsi; this
0x1800df291  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800df296  nop
0x1800df297  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800df29e  mov     [rsp+1A0h+rgnClip.__vftable], rax
0x1800df2a3  lea     this, [rsp+1A0h+rgnClip]; this
0x1800df2a8  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800df2ad  nop
0x1800df2ae  lea     this, [rbp+0A0h+memDC]; this
0x1800df2b2  call    ??1CMemDC@@UEAA@XZ; CMemDC::~CMemDC(void)
0x1800df2b7  nop
0x1800df2b8  lea     this, [rbp+0A0h+dc]; this
0x1800df2bc  call    ??1CPaintDC@@UEAA@XZ; CPaintDC::~CPaintDC(void)
0x1800df2c1  mov     this, [rbp+0A0h+var_30]
0x1800df2c5  xor     this, rsp; StackCookie
  ... truncated ...
```
