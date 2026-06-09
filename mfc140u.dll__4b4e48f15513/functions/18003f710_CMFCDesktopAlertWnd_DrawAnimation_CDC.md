# CMFCDesktopAlertWnd::DrawAnimation(CDC *)

- ea: `0x18003f710`
- end: `0x18003fd34`
- name: `?DrawAnimation@CMFCDesktopAlertWnd@@IEAAXPEAVCDC@@@Z`
- size: `1572`
- prototype: `void __fastcall(CMFCDesktopAlertWnd *this, CDC *pPaintDC)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003ecf0`

## callees

- `0x18003f710`
- `0x18005d370`
- `0x18006cab0`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af4b0`
- `0x1802afdb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18003fa11`
- `VCRUNTIME140!memcpy` at `0x18003fa11`
- `USER32!SetLayeredWindowAttributes` at `0x18003fb91`
- `USER32!SetLayeredWindowAttributes` at `0x18003fb91`
- `USER32!GetClientRect` at `0x18003f754`
- `USER32!GetClientRect` at `0x18003f754`
- `USER32!GetWindowRect` at `0x18003fa9e`
- `USER32!GetWindowRect` at `0x18003fa9e`
- `USER32!SendMessageW` at `0x18003fa4f`
- `USER32!SendMessageW` at `0x18003fafc`
- `USER32!SendMessageW` at `0x18003fa4f`
- `USER32!SendMessageW` at `0x18003fafc`
- `GDI32!CreateDIBSection` at `0x18003f8dd`
- `GDI32!CreateDIBSection` at `0x18003f926`
- `GDI32!CreateDIBSection` at `0x18003f968`
- `GDI32!CreateDIBSection` at `0x18003f8dd`
- `GDI32!CreateDIBSection` at `0x18003f926`
- `GDI32!CreateDIBSection` at `0x18003f968`
- `GDI32!BitBlt` at `0x18003f9f4`
- `GDI32!BitBlt` at `0x18003fcdf`
- `GDI32!BitBlt` at `0x18003f9f4`
- `GDI32!BitBlt` at `0x18003fcdf`
- `GDI32!CreateCompatibleBitmap` at `0x18003f85f`
- `GDI32!CreateCompatibleBitmap` at `0x18003f85f`
- `GDI32!SelectObject` at `0x18003f880`
- `GDI32!SelectObject` at `0x18003f9a0`
- `GDI32!SelectObject` at `0x18003fa27`
- `GDI32!SelectObject` at `0x18003fb44`
- `GDI32!SelectObject` at `0x18003fbde`
- `GDI32!SelectObject` at `0x18003fc74`
- `GDI32!SelectObject` at `0x18003fcf5`
- `GDI32!SelectObject` at `0x18003f880`
- `GDI32!SelectObject` at `0x18003f9a0`
- `GDI32!SelectObject` at `0x18003fa27`
- `GDI32!SelectObject` at `0x18003fb44`
- `GDI32!SelectObject` at `0x18003fbde`
- `GDI32!SelectObject` at `0x18003fc74`
- `GDI32!SelectObject` at `0x18003fcf5`
- `GDI32!CreateCompatibleDC` at `0x18003f794`
- `GDI32!CreateCompatibleDC` at `0x18003f794`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMFCDesktopAlertWnd::DrawAnimation(CMFCDesktopAlertWnd *this, CDC *pPaintDC)
{
  int cx; // r15d
  int v5; // r13d
  void *v6; // rbx
  HDC__ *m_hDC; // rcx
  HDC CompatibleDC; // rax
  CMFCPopupMenu::ANIMATION_TYPE m_AnimationType; // esi
  int m_bInitialized; // ecx
  HBITMAP CompatibleBitmap; // rax
  void *v12; // rdx
  HGDIOBJ v13; // rax
  CGdiObject *v14; // r15
  unsigned int **p_m_cFadeSrcBits; // r13
  HBITMAP DIBSection; // rax
  HBITMAP v17; // rax
  HBITMAP v18; // rax
  void *v19; // rdx
  HGDIOBJ v20; // rax
  HDC v21; // rcx
  void *v22; // rdx
  HGDIOBJ v23; // rax
  CPoint *(__fastcall *SetViewportOrg)(CDC *, CPoint *, int, int); // rax
  CPoint *(__fastcall *v25)(CDC *, CPoint *, int, int); // rax
  void *v26; // rdx
  HGDIOBJ v27; // rax
  BYTE m_nTransparency; // r8
  unsigned int *m_cFadeSrcBits; // r15
  unsigned int *m_cFadeDstBits; // r12
  unsigned int *m_cFadeTmpBits; // r13
  __int32 v32; // esi
  __int32 v33; // esi
  void *m_hObject; // rdx
  HGDIOBJ v35; // rax
  CGdiObject *v36; // rsi
  signed __int64 v37; // r12
  __int64 v38; // r14
  unsigned int v39; // edx
  unsigned int v40; // ecx
  void *v41; // rdx
  HGDIOBJ v42; // rax
  int v43; // ecx
  int v44; // r9d
  int top; // r8d
  int left; // edx
  HGDIOBJ v47; // rax
  int cy; // [rsp+50h] [rbp-69h]
  int v49; // [rsp+54h] [rbp-65h]
  CDC dcMem; // [rsp+58h] [rbp-61h] BYREF
  CPoint result; // [rsp+78h] [rbp-41h] BYREF
  CDC *v52; // [rsp+80h] [rbp-39h]
  CRect rectClient; // [rsp+88h] [rbp-31h] BYREF
  tagBITMAPINFOHEADER bih; // [rsp+98h] [rbp-21h] BYREF
  CRect rect; // [rsp+C0h] [rbp+7h] BYREF

  v52 = pPaintDC;
  rectClient = 0;
  GetClientRect(this->m_hWnd, &rectClient);
  cx = this->m_FinalSize.cx;
  v49 = cx;
  v5 = this->m_FinalSize.cy;
  cy = v5;
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  v6 = 0;
  m_hDC = 0;
  if ( pPaintDC )
    m_hDC = pPaintDC->m_hDC;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&dcMem, CompatibleDC) )
  {
    m_AnimationType = this->m_AnimationType;
    m_bInitialized = afxGlobalData.m_bInitialized;
    if ( m_AnimationType == SYSTEM_DEFAULT_ANIMATION )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        m_bInitialized = 1;
        afxGlobalData.m_bInitialized = 1;
      }
      if ( afxGlobalData.m_bMenuAnimation )
        m_AnimationType = (afxGlobalData.m_bMenuFadeEffect != 0) + 2;
      else
        m_AnimationType = NO_ANIMATION;
    }
    if ( this != (CMFCDesktopAlertWnd *)-6104LL && this->m_bmpScreenDst.m_hObject )
    {
LABEL_51:
      m_cFadeSrcBits = this->m_cFadeSrcBits;
      m_cFadeDstBits = this->m_cFadeDstBits;
      m_cFadeTmpBits = this->m_cFadeTmpBits;
      v32 = m_AnimationType - 1;
      if ( v32 && (v33 = v32 - 1) != 0 )
      {
        if ( v33 != 1 )
        {
LABEL_72:
          v47 = SelectObject(dcMem.m_hDC, v6);
          CGdiObject::FromHandle(v47);
          goto LABEL_73;
        }
        m_hObject = 0;
        if ( this != (CMFCDesktopAlertWnd *)-6120LL )
          m_hObject = this->m_bmpScreenTmp.m_hObject;
        v35 = SelectObject(dcMem.m_hDC, m_hObject);
        v36 = CGdiObject::FromHandle(v35);
        result = (CPoint)v36;
        if ( v49 * cy > 0 )
        {
          v37 = (char *)m_cFadeDstBits - (char *)m_cFadeSrcBits;
          v38 = (unsigned int)(v49 * cy);
          do
          {
            v39 = *(unsigned int *)((char *)m_cFadeSrcBits + v37);
            v40 = *m_cFadeSrcBits++;
            *m_cFadeTmpBits++ = CDrawingManager::PixelAlpha(v40, v39, 100 - this->m_iFadePercent);
            --v38;
          }
          while ( v38 );
          v36 = (CGdiObject *)result;
        }
        BitBlt(v52->m_hDC, rectClient.left, rectClient.top, v49, cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
      }
      else
      {
        v41 = 0;
        if ( this != (CMFCDesktopAlertWnd *)-6104LL )
          v41 = this->m_bmpScreenDst.m_hObject;
        v42 = SelectObject(dcMem.m_hDC, v41);
        v36 = CGdiObject::FromHandle(v42);
        v43 = this->m_AnimSize.cy;
        v44 = this->m_AnimSize.cx;
        if ( this->m_bIsAnimDown )
          top = rectClient.top;
        else
          top = rectClient.bottom - v43;
        if ( this->m_bIsAnimRight )
          left = rectClient.left;
        else
          left = rectClient.right - v44;
        BitBlt(v52->m_hDC, left, top, v44, v43, dcMem.m_hDC, 0, 0, 0xCC0020u);
      }
      if ( v36 )
        v6 = v36->m_hObject;
      goto LABEL_72;
    }
    if ( m_AnimationType != FADE )
    {
      if ( !m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( afxGlobalData.m_nBitsPerPixel <= 8 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(pPaintDC->m_hDC, cx, v5);
        CGdiObject::Attach(&this->m_bmpScreenDst, CompatibleBitmap);
        v12 = 0;
        if ( this != (CMFCDesktopAlertWnd *)-6104LL )
          v12 = this->m_bmpScreenDst.m_hObject;
        v13 = SelectObject(dcMem.m_hDC, v12);
        v14 = CGdiObject::FromHandle(v13);
LABEL_32:
        SendMessageW(this->m_hWnd, 0x317u, (WPARAM)dcMem.m_hDC, 28);
        if ( this != (CMFCDesktopAlertWnd *)-312LL && this->m_btnClose.m_hWnd )
          CWnd::ShowWindow(&this->m_btnClose, 0);
        if ( this != (CMFCDesktopAlertWnd *)-3168LL && this->m_btnMenu.m_hWnd )
          CWnd::ShowWindow(&this->m_btnMenu, 0);
        rect = 0;
        GetWindowRect(this->m_pWndDlg->m_hWnd, &rect);
        CWnd::ScreenToClient(this, &rect);
        SetViewportOrg = dcMem.SetViewportOrg;
        if ( SetViewportOrg == CDC::SetViewportOrg )
          CDC::SetViewportOrg(&dcMem, &result, rect.left, rect.top);
        else
          SetViewportOrg(&dcMem, &result, *(_QWORD *)&rect.left, HIDWORD(*(_QWORD *)&rect.left));
        SendMessageW(this->m_pWndDlg->m_hWnd, 0x317u, (WPARAM)dcMem.m_hDC, 28);
        v25 = dcMem.SetViewportOrg;
        if ( v25 == CDC::SetViewportOrg )
          CDC::SetViewportOrg(&dcMem, &result, 0, 0);
        else
          v25(&dcMem, &result, 0, 0);
        v26 = 0;
        if ( v14 )
          v26 = v14->m_hObject;
        v27 = SelectObject(dcMem.m_hDC, v26);
        CGdiObject::FromHandle(v27);
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        if ( afxGlobalData.m_nBitsPerPixel > 8 )
        {
          m_nTransparency = this->m_nTransparency;
          if ( m_nTransparency != 0xFF )
            SetLayeredWindowAttributes(this->m_hWnd, 0, m_nTransparency, 2u);
        }
        goto LABEL_51;
      }
    }
    bih.biSize = 40;
    bih.biWidth = cx;
    bih.biHeight = v5;
    *(_QWORD *)&bih.biPlanes = 2097153;
    bih.biSizeImage = cx * v5;
    *(_QWORD *)&bih.biXPelsPerMeter = 0;
    *(_QWORD *)&bih.biClrUsed = 0;
    p_m_cFadeSrcBits = &this->m_cFadeSrcBits;
    DIBSection = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeSrcBits, 0, 0);
    if ( DIBSection )
    {
      if ( *p_m_cFadeSrcBits )
      {
        CGdiObject::Attach(&this->m_bmpScreenSrc, DIBSection);
        v17 = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeDstBits, 0, 0);
        if ( v17 )
        {
          if ( this->m_cFadeDstBits )
          {
            CGdiObject::Attach(&this->m_bmpScreenDst, v17);
            v18 = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeTmpBits, 0, 0);
            if ( v18 )
            {
              if ( this->m_cFadeTmpBits )
              {
                CGdiObject::Attach(&this->m_bmpScreenTmp, v18);
                v19 = 0;
                if ( this != (CMFCDesktopAlertWnd *)-6088LL )
                  v19 = this->m_bmpScreenSrc.m_hObject;
                v20 = SelectObject(dcMem.m_hDC, v19);
                v14 = CGdiObject::FromHandle(v20);
                v21 = 0;
                if ( v52 )
                  v21 = v52->m_hDC;
                BitBlt(dcMem.m_hDC, 0, 0, v49, cy, v21, rectClient.left, rectClient.top, 0xCC0020u);
                memcpy(this->m_cFadeDstBits, *p_m_cFadeSrcBits, 4 * v49 * (__int64)cy);
                v22 = 0;
                if ( this != (CMFCDesktopAlertWnd *)-6104LL )
                  v22 = this->m_bmpScreenDst.m_hObject;
                v23 = SelectObject(dcMem.m_hDC, v22);
                CGdiObject::FromHandle(v23);
                goto LABEL_32;
              }
            }
          }
        }
      }
    }
  }
LABEL_73:
  CDC::~CDC(&dcMem);
}

```

## disassembly

```asm
0x18003f710  mov     [rsp-8+arg_10], rbx
0x18003f715  push    rbp
0x18003f716  push    rsi
0x18003f717  push    rdi
0x18003f718  push    r12
0x18003f71a  push    r13
0x18003f71c  push    r14
0x18003f71e  push    r15
0x18003f720  lea     rbp, [rsp-27h]
0x18003f725  sub     rsp, 0E0h
0x18003f72c  mov     rax, cs:__security_cookie
0x18003f733  xor     rax, rsp
0x18003f736  mov     [rbp+57h+var_40], rax
0x18003f73a  mov     r12, pPaintDC
0x18003f73d  mov     [rbp+57h+var_90], pPaintDC
0x18003f741  mov     rdi, this
0x18003f744  xorps   xmm0, xmm0
0x18003f747  movdqu  xmmword ptr [rbp+57h+rectClient.left], xmm0
0x18003f74c  lea     pPaintDC, [rbp+57h+rectClient]; lpRect
0x18003f750  mov     this, [this+40h]; hWnd
0x18003f754  call    cs:__imp_GetClientRect
0x18003f75a  mov     r15d, [rdi+17BCh]
0x18003f761  mov     [rbp+57h+var_BC], r15d
0x18003f765  mov     r13d, [rdi+17C0h]
0x18003f76c  mov     [rbp+57h+cy], r13d
0x18003f770  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18003f777  mov     [rbp+57h+dcMem.__vftable], rax
0x18003f77b  xorps   xmm0, xmm0
0x18003f77e  movdqu  xmmword ptr [rbp+57h+dcMem.m_hDC], xmm0
0x18003f783  xor     ebx, ebx
0x18003f785  mov     [rbp+57h+dcMem.m_bPrinting], ebx
0x18003f788  test    r12, r12
0x18003f78b  mov     ecx, ebx
0x18003f78d  jz      short loc_18003F794
0x18003f78f  mov     this, [r12+8]; hdc
0x18003f794  call    cs:__imp_CreateCompatibleDC
0x18003f79a  mov     pPaintDC, rax; hDC
0x18003f79d  lea     this, [rbp+57h+dcMem]; this
0x18003f7a1  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18003f7a6  test    eax, eax
0x18003f7a8  jz      loc_18003FD04
0x18003f7ae  mov     esi, [rdi+1788h]
0x18003f7b4  mov     r14d, 1
0x18003f7ba  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f7c0  cmp     esi, 3E7h
0x18003f7c6  jnz     short loc_18003F815
0x18003f7c8  test    ecx, ecx
0x18003f7ca  jnz     short loc_18003F7E1
0x18003f7cc  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18003f7d3  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18003f7d8  mov     ecx, r14d
0x18003f7db  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f7e1  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bMenuAnimation, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f7e7  jz      short loc_18003F813
0x18003f7e9  test    ecx, ecx
0x18003f7eb  jnz     short loc_18003F802
0x18003f7ed  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18003f7f4  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18003f7f9  mov     ecx, r14d
0x18003f7fc  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ecx; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f802  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bMenuFadeEffect; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f808  neg     eax
0x18003f80a  sbb     esi, esi
0x18003f80c  neg     esi
0x18003f80e  add     esi, 2
0x18003f811  jmp     short loc_18003F815
0x18003f813  mov     esi, ebx
0x18003f815  lea     r14, [rdi+17D8h]
0x18003f81c  test    r14, r14
0x18003f81f  jz      short loc_18003F82B
0x18003f821  cmp     [r14+8], rbx
0x18003f825  jnz     loc_18003FB97
0x18003f82b  cmp     esi, 3
0x18003f82e  jz      short loc_18003F896
0x18003f830  test    ecx, ecx
0x18003f832  jnz     short loc_18003F84B
0x18003f834  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18003f83b  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18003f840  mov     eax, 1
0x18003f845  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f84b  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x18003f852  jg      short loc_18003F896
0x18003f854  mov     r8d, r13d; cy
0x18003f857  mov     edx, r15d; cx
0x18003f85a  mov     this, [r12+8]; hdc
0x18003f85f  call    cs:__imp_CreateCompatibleBitmap
0x18003f865  mov     pPaintDC, rax; hObject
0x18003f868  mov     this, r14; this
0x18003f86b  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18003f870  test    r14, r14
0x18003f873  mov     pPaintDC, rbx
0x18003f876  jz      short loc_18003F87C
0x18003f878  mov     pPaintDC, [r14+8]; h
0x18003f87c  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f880  call    cs:__imp_SelectObject
0x18003f886  mov     this, rax; h
0x18003f889  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18003f88e  mov     r15, rax
0x18003f891  jmp     loc_18003FA35
0x18003f896  mov     [rbp+57h+bih.biSize], 28h ; '('
0x18003f89d  mov     [rbp+57h+bih.biWidth], r15d
0x18003f8a1  mov     [rbp+57h+bih.biHeight], r13d
0x18003f8a5  mov     qword ptr [rbp+57h+bih.biPlanes], 200001h
0x18003f8ad  mov     eax, r13d
0x18003f8b0  imul    eax, r15d
0x18003f8b4  mov     [rbp+57h+bih.biSizeImage], eax
0x18003f8b7  mov     qword ptr [rbp+57h+bih.biXPelsPerMeter], rbx
0x18003f8bb  mov     qword ptr [rbp+57h+bih.biClrUsed], rbx
0x18003f8bf  lea     r13, [rdi+17F8h]
0x18003f8c6  mov     [rsp+110h+offset], ebx; offset
0x18003f8ca  mov     [rsp+110h+hSection], rbx; hSection
0x18003f8cf  mov     r9, r13; ppvBits
0x18003f8d2  xor     r8d, r8d; usage
0x18003f8d5  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x18003f8d9  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f8dd  call    cs:__imp_CreateDIBSection
0x18003f8e3  test    rax, rax
0x18003f8e6  jz      loc_18003FD04
0x18003f8ec  cmp     [r13+0], rbx
0x18003f8f0  jz      loc_18003FD04
0x18003f8f6  lea     r15, [rdi+17C8h]
0x18003f8fd  mov     pPaintDC, rax; hObject
0x18003f900  mov     this, r15; this
0x18003f903  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18003f908  lea     r12, [rdi+1800h]
0x18003f90f  mov     [rsp+110h+offset], ebx; offset
0x18003f913  mov     [rsp+110h+hSection], rbx; hSection
0x18003f918  mov     r9, r12; ppvBits
0x18003f91b  xor     r8d, r8d; usage
0x18003f91e  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x18003f922  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f926  call    cs:__imp_CreateDIBSection
0x18003f92c  test    rax, rax
0x18003f92f  jz      loc_18003FD04
0x18003f935  cmp     [r12], rbx
0x18003f939  jz      loc_18003FD04
0x18003f93f  mov     pPaintDC, rax; hObject
0x18003f942  mov     this, r14; this
0x18003f945  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18003f94a  lea     r12, [rdi+1808h]
0x18003f951  mov     [rsp+110h+offset], ebx; offset
0x18003f955  mov     [rsp+110h+hSection], rbx; hSection
0x18003f95a  mov     r9, r12; ppvBits
0x18003f95d  xor     r8d, r8d; usage
0x18003f960  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x18003f964  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f968  call    cs:__imp_CreateDIBSection
0x18003f96e  test    rax, rax
0x18003f971  jz      loc_18003FD04
0x18003f977  cmp     [r12], rbx
0x18003f97b  jz      loc_18003FD04
0x18003f981  lea     this, [rdi+17E8h]; this
0x18003f988  mov     pPaintDC, rax; hObject
0x18003f98b  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18003f990  test    r15, r15
0x18003f993  mov     pPaintDC, rbx
0x18003f996  jz      short loc_18003F99C
0x18003f998  mov     pPaintDC, [r15+8]; h
0x18003f99c  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f9a0  call    cs:__imp_SelectObject
0x18003f9a6  mov     this, rax; h
0x18003f9a9  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18003f9ae  mov     r15, rax
0x18003f9b1  mov     r12, [rbp+57h+var_90]
0x18003f9b5  test    r12, r12
0x18003f9b8  mov     this, rbx
0x18003f9bb  jz      short loc_18003F9C2
0x18003f9bd  mov     this, [r12+8]
0x18003f9c2  mov     [rsp+110h+rop], 0CC0020h; rop
0x18003f9ca  mov     eax, [rbp+57h+rectClient.top]
0x18003f9cd  mov     [rsp+110h+y1], eax; y1
0x18003f9d1  mov     eax, [rbp+57h+rectClient.left]
0x18003f9d4  mov     [rsp+110h+x1], eax; x1
0x18003f9d8  mov     qword ptr [rsp+110h+offset], this; hdcSrc
0x18003f9dd  mov     eax, [rbp+57h+cy]
0x18003f9e0  mov     dword ptr [rsp+110h+hSection], eax; cy
0x18003f9e4  movsxd  r12, [rbp+57h+var_BC]
0x18003f9e8  mov     r9d, r12d; cx
0x18003f9eb  xor     r8d, r8d; y
0x18003f9ee  xor     edx, edx; x
0x18003f9f0  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003f9f4  call    cs:__imp_BitBlt
0x18003f9fa  movsxd  r8, [rbp+57h+cy]
0x18003f9fe  imul    r8, r12
0x18003fa02  shl     r8, 2; Size
0x18003fa06  mov     pPaintDC, [r13+0]; Src
0x18003fa0a  mov     this, [rdi+1800h]; void *
0x18003fa11  call    cs:__imp_memcpy
0x18003fa17  test    r14, r14
0x18003fa1a  mov     pPaintDC, rbx
0x18003fa1d  jz      short loc_18003FA23
0x18003fa1f  mov     pPaintDC, [r14+8]; h
0x18003fa23  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003fa27  call    cs:__imp_SelectObject
0x18003fa2d  mov     this, rax; h
0x18003fa30  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18003fa35  mov     r12d, 1Ch
0x18003fa3b  mov     r9d, r12d; lParam
0x18003fa3e  mov     r8, [rbp+57h+dcMem.m_hDC]; wParam
0x18003fa42  mov     r13d, 317h
0x18003fa48  mov     edx, r13d; Msg
0x18003fa4b  mov     this, [rdi+40h]; hWnd
0x18003fa4f  call    cs:__imp_SendMessageW
0x18003fa55  lea     this, [rdi+138h]; this
0x18003fa5c  test    this, this
0x18003fa5f  jz      short loc_18003FA6E
0x18003fa61  cmp     [this+40h], rbx
0x18003fa65  jz      short loc_18003FA6E
0x18003fa67  xor     edx, edx; nCmdShow
0x18003fa69  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18003fa6e  lea     this, [rdi+0C60h]; this
0x18003fa75  test    this, this
0x18003fa78  jz      short loc_18003FA87
0x18003fa7a  cmp     [this+40h], rbx
0x18003fa7e  jz      short loc_18003FA87
0x18003fa80  xor     edx, edx; nCmdShow
0x18003fa82  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18003fa87  xorps   xmm0, xmm0
0x18003fa8a  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x18003fa8f  mov     this, [rdi+130h]
0x18003fa96  lea     pPaintDC, [rbp+57h+rect]; lpRect
0x18003fa9a  mov     this, [this+40h]; hWnd
0x18003fa9e  call    cs:__imp_GetWindowRect
0x18003faa4  lea     pPaintDC, [rbp+57h+rect]; lpRect
0x18003faa8  mov     this, rdi; this
0x18003faab  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x18003fab0  mov     rax, [rbp+57h+dcMem.__vftable]
0x18003fab4  mov     rax, [rax+80h]
0x18003fabb  mov     r8, qword ptr [rbp+57h+rect.left]; x
0x18003fabf  mov     r9, r8
0x18003fac2  shr     r9, 20h; y
0x18003fac6  lea     this, ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x18003facd  lea     pPaintDC, [rbp+57h+result]; result
0x18003fad1  cmp     rax, this
0x18003fad4  lea     this, [rbp+57h+dcMem]; this
0x18003fad8  jnz     short loc_18003FAE1
0x18003fada  call    ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x18003fadf  jmp     short loc_18003FAE7
0x18003fae1  call    cs:__guard_dispatch_icall_fptr
0x18003fae7  mov     this, [rdi+130h]
0x18003faee  mov     r9, r12; lParam
0x18003faf1  mov     r8, [rbp+57h+dcMem.m_hDC]; wParam
0x18003faf5  mov     edx, r13d; Msg
0x18003faf8  mov     this, [this+40h]; hWnd
0x18003fafc  call    cs:__imp_SendMessageW
0x18003fb02  mov     rax, [rbp+57h+dcMem.__vftable]
0x18003fb06  mov     rax, [rax+80h]
0x18003fb0d  lea     this, ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x18003fb14  xor     r9d, r9d; y
0x18003fb17  xor     r8d, r8d; x
0x18003fb1a  lea     pPaintDC, [rbp+57h+result]; result
0x18003fb1e  cmp     rax, this
0x18003fb21  lea     this, [rbp+57h+dcMem]; this
0x18003fb25  jnz     short loc_18003FB2E
0x18003fb27  call    ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x18003fb2c  jmp     short loc_18003FB34
0x18003fb2e  call    cs:__guard_dispatch_icall_fptr
0x18003fb34  test    r15, r15
0x18003fb37  mov     pPaintDC, rbx
0x18003fb3a  jz      short loc_18003FB40
0x18003fb3c  mov     pPaintDC, [r15+8]; h
0x18003fb40  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003fb44  call    cs:__imp_SelectObject
0x18003fb4a  mov     this, rax; h
0x18003fb4d  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18003fb52  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x18003fb58  jnz     short loc_18003FB71
0x18003fb5a  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18003fb61  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18003fb66  mov     eax, 1
0x18003fb6b  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x18003fb71  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x18003fb78  jle     short loc_18003FB97
0x18003fb7a  mov     r8b, [rdi+120h]; bAlpha
0x18003fb81  cmp     r8b, 0FFh
0x18003fb85  jnb     short loc_18003FB97
0x18003fb87  xor     edx, edx; crKey
0x18003fb89  lea     r9d, [pPaintDC+2]; dwFlags
0x18003fb8d  mov     this, [rdi+40h]; hwnd
0x18003fb91  call    cs:__imp_SetLayeredWindowAttributes
0x18003fb97  mov     r15, [rdi+17F8h]
0x18003fb9e  mov     r12, [rdi+1800h]
0x18003fba5  mov     r13, [rdi+1808h]
0x18003fbac  sub     esi, 1
0x18003fbaf  jz      loc_18003FC64
0x18003fbb5  sub     esi, 1
0x18003fbb8  jz      loc_18003FC64
0x18003fbbe  cmp     esi, 1
0x18003fbc1  jnz     loc_18003FCEE
0x18003fbc7  lea     rax, [rdi+17E8h]
0x18003fbce  test    rax, rax
0x18003fbd1  mov     pPaintDC, rbx
0x18003fbd4  jz      short loc_18003FBDA
0x18003fbd6  mov     pPaintDC, [rax+8]; h
0x18003fbda  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18003fbde  call    cs:__imp_SelectObject
0x18003fbe4  mov     this, rax; h
0x18003fbe7  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18003fbec  mov     rsi, rax
0x18003fbef  mov     qword ptr [rbp+57h+result.x], rax
  ... truncated ...
```
