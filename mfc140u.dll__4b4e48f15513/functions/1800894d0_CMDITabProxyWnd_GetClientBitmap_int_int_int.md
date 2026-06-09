# CMDITabProxyWnd::GetClientBitmap(int,int,int)

- ea: `0x1800894d0`
- end: `0x1800898bc`
- name: `?GetClientBitmap@CMDITabProxyWnd@@QEAAPEAUHBITMAP__@@HHH@Z`
- size: `1004`
- prototype: `HBITMAP__ *__fastcall(CMDITabProxyWnd *this, int nWidth, int nHeight, int bIsThumbnail)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800898c0`
- `0x180089950`

## callees

- `0x1800894d0`
- `0x180089c54`
- `0x180089dd0`
- `0x18008a148`
- `0x18008a2a0`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetWindowRect` at `0x180089553`
- `USER32!GetWindowRect` at `0x180089553`
- `USER32!OffsetRect` at `0x180089569`
- `USER32!OffsetRect` at `0x180089569`
- `GDI32!DeleteDC` at `0x18008983b`
- `GDI32!DeleteDC` at `0x18008983b`
- `GDI32!SelectObject` at `0x180089603`
- `GDI32!SelectObject` at `0x180089667`
- `GDI32!SelectObject` at `0x1800897ea`
- `GDI32!SelectObject` at `0x18008981b`
- `GDI32!SelectObject` at `0x180089603`
- `GDI32!SelectObject` at `0x180089667`
- `GDI32!SelectObject` at `0x1800897ea`
- `GDI32!SelectObject` at `0x18008981b`
- `GDI32!CreateCompatibleDC` at `0x1800895e2`
- `GDI32!CreateCompatibleDC` at `0x1800897c9`
- `GDI32!CreateCompatibleDC` at `0x1800895e2`
- `GDI32!CreateCompatibleDC` at `0x1800897c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HBITMAP__ *__fastcall CMDITabProxyWnd::GetClientBitmap(
        CMDITabProxyWnd *this,
        int nWidth,
        int nHeight,
        unsigned int bIsThumbnail)
{
  CMDIChildWndEx *m_pRelatedMDIChildFrame; // rcx
  CWnd *v9; // rdi
  HDC CompatibleDC; // rax
  HGDIOBJ v11; // rbx
  CWnd_vtbl *v12; // rax
  char *m_pBits; // rdx
  int v14; // ebx
  int right; // r8d
  int left; // r10d
  int bottom; // r9d
  int top; // r11d
  _BYTE *v19; // rdx
  double v20; // xmm1_8
  double v21; // xmm2_8
  double v22; // xmm3_8
  HDC v23; // rax
  HGDIOBJ v24; // rbx
  HDC v25; // rax
  HBITMAP__ *m_hBitmap; // rbx
  unsigned int dwFlags; // [rsp+20h] [rbp-E0h]
  CRect *dwFlagsa; // [rsp+20h] [rbp-E0h]
  unsigned int *v30; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v31; // [rsp+28h] [rbp-D8h]
  int bAlphaChannelSet; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v33; // [rsp+44h] [rbp-BCh]
  CDC dc; // [rsp+50h] [rbp-B0h] BYREF
  CDC dcThumbnail; // [rsp+70h] [rbp-90h] BYREF
  ATL::CImage bmpDst; // [rsp+90h] [rbp-70h] BYREF
  ATL::CImage bmpSrc; // [rsp+E0h] [rbp-20h] BYREF
  CClientDC dcPreview; // [rsp+130h] [rbp+30h] BYREF
  CRect rectWnd; // [rsp+160h] [rbp+60h] BYREF
  CRect rectDst; // [rsp+170h] [rbp+70h] BYREF

  m_pRelatedMDIChildFrame = this->m_pRelatedMDIChildFrame;
  if ( !m_pRelatedMDIChildFrame )
    return 0;
  if ( nWidth <= 0 )
    return 0;
  if ( nHeight <= 0 )
    return 0;
  rectWnd = 0;
  v9 = m_pRelatedMDIChildFrame->GetTaskbarPreviewWnd(m_pRelatedMDIChildFrame);
  GetWindowRect(v9->m_hWnd, &rectWnd);
  OffsetRect(&rectWnd, -rectWnd.left, -rectWnd.top);
  if ( rectWnd.right - rectWnd.left <= 0 || rectWnd.bottom - rectWnd.top <= 0 )
    return 0;
  ATL::CImage::CImage(&bmpSrc);
  ATL::CImage::CreateEx(&bmpSrc, rectWnd.right - rectWnd.left, rectWnd.bottom - rectWnd.top, 32, dwFlags, v30, 1u);
  CClientDC::CClientDC(&dcPreview, v9);
  dcThumbnail.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcThumbnail.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(dcPreview.m_hDC);
  CDC::Attach(&dcThumbnail, CompatibleDC);
  if ( bmpSrc.m_hBitmap )
    v11 = SelectObject(dcThumbnail.m_hDC, bmpSrc.m_hBitmap);
  else
    v11 = 0;
  bAlphaChannelSet = 0;
  v12 = v9->__vftable;
  v33 = __PAIR64__(nHeight, nWidth);
  *(CRect *)&dc.__vftable = rectWnd;
  ((void (__fastcall *)(CWnd *, CDC *, CDC *, unsigned __int64))v12->OnDrawIconicThumbnailOrLivePreview)(
    v9,
    &dcThumbnail,
    &dc,
    __PAIR64__(nHeight, nWidth));
  if ( v11 )
    SelectObject(dcThumbnail.m_hDC, v11);
  m_pBits = (char *)bmpSrc.m_pBits;
  if ( bmpSrc.m_nPitch < 0 )
    m_pBits = (char *)bmpSrc.m_pBits + bmpSrc.m_nPitch * (bmpSrc.m_nHeight - 1);
  v14 = 0;
  right = rectWnd.right;
  left = rectWnd.left;
  bottom = rectWnd.bottom;
  top = rectWnd.top;
  if ( (rectWnd.bottom - rectWnd.top) * (rectWnd.right - rectWnd.left) > 0 )
  {
    v19 = m_pBits + 3;
    do
    {
      *v19 = -1;
      v19 += 4;
      ++v14;
      right = rectWnd.right;
      left = rectWnd.left;
      bottom = rectWnd.bottom;
      top = rectWnd.top;
    }
    while ( v14 < (rectWnd.bottom - rectWnd.top) * (rectWnd.right - rectWnd.left) );
  }
  v20 = (double)(right - left);
  v21 = (double)(bottom - top);
  v22 = fmin((double)nWidth / v20, (double)nHeight / v21);
  *(_QWORD *)&rectDst.left = 0;
  rectDst.right = (int)(v22 * v20);
  rectDst.bottom = (int)(v22 * v21);
  ATL::CImage::CImage(&bmpDst);
  ATL::CImage::CreateEx(
    &bmpDst,
    (int)(v22 * v20),
    -(int)(v22 * v21),
    32,
    bIsThumbnail,
    (const unsigned int *)&bAlphaChannelSet,
    1u);
  if ( !bIsThumbnail
    || (dwFlagsa = &rectWnd,
        !((unsigned int (__fastcall *)(CMDIChildWndEx *, HBITMAP__ *, CRect *, HBITMAP__ *))this->m_pRelatedMDIChildFrame->OnTaskbarTabThumbnailStretch)(
           this->m_pRelatedMDIChildFrame,
           bmpDst.m_hBitmap,
           &rectDst,
           bmpSrc.m_hBitmap)) )
  {
    dc.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&dc.m_hDC, 0, 20);
    v23 = CreateCompatibleDC(dcPreview.m_hDC);
    CDC::Attach(&dc, v23);
    if ( bmpDst.m_hBitmap )
      v24 = SelectObject(dc.m_hDC, bmpDst.m_hBitmap);
    else
      v24 = 0;
    ATL::CImage::AlphaBlend(&bmpSrc, dc.m_hDC, &rectDst, &rectWnd, (unsigned __int8)dwFlagsa, v31);
    if ( v24 )
      SelectObject(dc.m_hDC, v24);
    dc.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( dc.m_hDC )
    {
      v25 = CDC::Detach(&dc);
      DeleteDC(v25);
    }
  }
  m_hBitmap = bmpDst.m_hBitmap;
  memset(&bmpDst.m_hBitmap, 0, 34);
  bmpDst.m_iTransparentColor = -1;
  bmpDst.m_clrTransparentColor = -1;
  ATL::CImage::~CImage(&bmpDst);
  CDC::~CDC(&dcThumbnail);
  CClientDC::~CClientDC(&dcPreview);
  ATL::CImage::~CImage(&bmpSrc);
  return m_hBitmap;
}

```

## disassembly

```asm
0x1800894d0  mov     [rsp-8+arg_10], rbx
0x1800894d5  push    rbp
0x1800894d6  push    rsi
0x1800894d7  push    rdi
0x1800894d8  push    r12
0x1800894da  push    r13
0x1800894dc  push    r14
0x1800894de  push    r15
0x1800894e0  lea     rbp, [rsp-90h]
0x1800894e8  sub     rsp, 190h
0x1800894ef  mov     rax, cs:__security_cookie
0x1800894f6  xor     rax, rsp
0x1800894f9  mov     [rbp+0C0h+var_40], rax
0x180089500  mov     r12d, bIsThumbnail
0x180089503  mov     esi, nHeight
0x180089506  mov     r14d, nWidth
0x180089509  mov     r15, this
0x18008950c  mov     this, [this+0E8h]
0x180089513  xor     r13d, r13d
0x180089516  test    this, this
0x180089519  jz      loc_180089890
0x18008951f  test    nWidth, nWidth
0x180089521  jle     loc_180089890
0x180089527  test    nHeight, nHeight
0x18008952a  jle     loc_180089890
0x180089530  xorps   xmm0, xmm0
0x180089533  movdqa  xmmword ptr [rbp+0C0h+rectWnd.left], xmm0
0x180089538  mov     rax, [this]
0x18008953b  mov     rax, [rax+418h]
0x180089542  call    cs:__guard_dispatch_icall_fptr
0x180089548  mov     rdi, rax
0x18008954b  lea     rdx, [rbp+0C0h+rectWnd]; lpRect
0x18008954f  mov     this, [rax+40h]; hWnd
0x180089553  call    cs:__imp_GetWindowRect
0x180089559  mov     nHeight, [rbp+0C0h+rectWnd.top]
0x18008955d  neg     nHeight; dy
0x180089560  mov     nWidth, [rbp+0C0h+rectWnd.left]
0x180089563  neg     nWidth; dx
0x180089565  lea     this, [rbp+0C0h+rectWnd]; lprc
0x180089569  call    cs:__imp_OffsetRect
0x18008956f  mov     ecx, [rbp+0C0h+rectWnd.right]
0x180089572  sub     ecx, [rbp+0C0h+rectWnd.left]
0x180089575  test    ecx, ecx
0x180089577  jle     loc_180089890
0x18008957d  mov     eax, [rbp+0C0h+rectWnd.bottom]
0x180089580  sub     eax, [rbp+0C0h+rectWnd.top]
0x180089583  test    eax, eax
0x180089585  jle     loc_180089890
0x18008958b  lea     this, [rbp+0C0h+bmpSrc]; this
0x18008958f  call    ??0CImage@ATL@@QEAA@XZ; ATL::CImage::CImage(void)
0x180089594  nop
0x180089595  mov     nHeight, [rbp+0C0h+rectWnd.bottom]
0x180089599  sub     nHeight, [rbp+0C0h+rectWnd.top]; nHeight
0x18008959d  mov     nWidth, [rbp+0C0h+rectWnd.right]
0x1800895a0  sub     nWidth, [rbp+0C0h+rectWnd.left]; nWidth
0x1800895a3  mov     [rsp+1C0h+var_190], 1; nHeight
0x1800895ab  lea     bIsThumbnail, [r13+20h]; nBPP
0x1800895af  lea     this, [rbp+0C0h+bmpSrc]; this
0x1800895b3  call    ?CreateEx@CImage@ATL@@QEAAHHHHKPEBKK@Z; ATL::CImage::CreateEx(int,int,int,ulong,ulong const *,ulong)
0x1800895b8  mov     rdx, rdi; pWnd
0x1800895bb  lea     this, [rbp+0C0h+dcPreview]; this
0x1800895bf  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x1800895c4  nop
0x1800895c5  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1800895cc  mov     [rsp+1C0h+dcThumbnail.__vftable], rax
0x1800895d1  xorps   xmm0, xmm0
0x1800895d4  movdqu  xmmword ptr [rsp+1C0h+dcThumbnail.m_hDC], xmm0
0x1800895da  mov     [rbp+0C0h+dcThumbnail.m_bPrinting], r13d
0x1800895de  mov     this, [rbp+0C0h+dcPreview.m_hDC]; hdc
0x1800895e2  call    cs:__imp_CreateCompatibleDC
0x1800895e8  mov     rdx, rax; hDC
0x1800895eb  lea     this, [rsp+1C0h+dcThumbnail]; this
0x1800895f0  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1800895f5  mov     rdx, [rbp+0C0h+bmpSrc.m_hBitmap]; h
0x1800895f9  test    rdx, rdx
0x1800895fc  jz      short loc_18008960E
0x1800895fe  mov     this, [rsp+1C0h+dcThumbnail.m_hDC]; hdc
0x180089603  call    cs:__imp_SelectObject
0x180089609  mov     rbx, rax
0x18008960c  jmp     short loc_180089611
0x18008960e  mov     rbx, r13
0x180089611  mov     [rsp+1C0h+bAlphaChannelSet], r13d
0x180089616  mov     rax, [rdi]
0x180089619  mov     dword ptr [rsp+1C0h+var_17C], r14d
0x18008961e  mov     dword ptr [rsp+1C0h+var_17C+4], esi
0x180089622  movaps  xmm0, xmmword ptr [rbp+0C0h+rectWnd.left]
0x180089626  movdqa  xmmword ptr [rsp+1C0h+dc.__vftable], xmm0
0x18008962c  lea     this, [rsp+1C0h+bAlphaChannelSet]
0x180089631  mov     [rsp+1C0h+var_198], this; rectDest
0x180089636  mov     [rsp+1C0h+dwFlags], r12d; dwFlags
0x18008963b  mov     r9, [rsp+1C0h+var_17C]
0x180089640  lea     r8, [rsp+1C0h+dc]
0x180089645  lea     rdx, [rsp+1C0h+dcThumbnail]
0x18008964a  mov     this, rdi
0x18008964d  mov     rax, [rax+130h]
0x180089654  call    cs:__guard_dispatch_icall_fptr
0x18008965a  test    rbx, rbx
0x18008965d  jz      short loc_18008966D
0x18008965f  mov     rdx, rbx; h
0x180089662  mov     this, [rsp+1C0h+dcThumbnail.m_hDC]; hdc
0x180089667  call    cs:__imp_SelectObject
0x18008966d  cmp     [rsp+1C0h+bAlphaChannelSet], r13d
0x180089672  jnz     short loc_1800896E8
0x180089674  mov     rdx, [rbp+0C0h+bmpSrc.m_pBits]
0x180089678  mov     r8, rdx
0x18008967b  mov     ecx, [rbp+0C0h+bmpSrc.m_nPitch]
0x18008967e  test    ecx, ecx
0x180089680  jns     short loc_180089690
0x180089682  mov     eax, [rbp+0C0h+bmpSrc.m_nHeight]
0x180089685  dec     eax
0x180089687  imul    eax, ecx
0x18008968a  movsxd  rdx, eax
0x18008968d  add     rdx, r8
0x180089690  mov     ebx, r13d
0x180089693  mov     nHeight, [rbp+0C0h+rectWnd.right]
0x180089697  mov     ecx, nHeight
0x18008969a  mov     r10d, [rbp+0C0h+rectWnd.left]
0x18008969e  sub     ecx, r10d
0x1800896a1  mov     bIsThumbnail, [rbp+0C0h+rectWnd.bottom]
0x1800896a5  mov     eax, bIsThumbnail
0x1800896a8  mov     r11d, [rbp+0C0h+rectWnd.top]
0x1800896ac  sub     eax, r11d
0x1800896af  imul    ecx, eax
0x1800896b2  test    ecx, ecx
0x1800896b4  jle     short loc_1800896F8
0x1800896b6  add     rdx, 3
0x1800896ba  mov     byte ptr [rdx], 0FFh
0x1800896bd  lea     rdx, [rdx+4]
0x1800896c1  inc     ebx
0x1800896c3  mov     nHeight, [rbp+0C0h+rectWnd.right]
0x1800896c7  mov     ecx, nHeight
0x1800896ca  mov     r10d, [rbp+0C0h+rectWnd.left]
0x1800896ce  sub     ecx, r10d
0x1800896d1  mov     bIsThumbnail, [rbp+0C0h+rectWnd.bottom]
0x1800896d5  mov     eax, bIsThumbnail
0x1800896d8  mov     r11d, [rbp+0C0h+rectWnd.top]
0x1800896dc  sub     eax, r11d
0x1800896df  imul    ecx, eax
0x1800896e2  cmp     ebx, ecx
0x1800896e4  jl      short loc_1800896BA
0x1800896e6  jmp     short loc_1800896F8
0x1800896e8  mov     bIsThumbnail, [rbp+0C0h+rectWnd.bottom]
0x1800896ec  mov     nHeight, [rbp+0C0h+rectWnd.right]
0x1800896f0  mov     r11d, [rbp+0C0h+rectWnd.top]
0x1800896f4  mov     r10d, [rbp+0C0h+rectWnd.left]
0x1800896f8  sub     bIsThumbnail, r11d
0x1800896fb  sub     nHeight, r10d
0x1800896fe  movd    xmm1, nHeight
0x180089703  cvtdq2pd xmm1, xmm1
0x180089707  movd    xmm2, bIsThumbnail
0x18008970c  cvtdq2pd xmm2, xmm2
0x180089710  movd    xmm3, r14d
0x180089715  cvtdq2pd xmm3, xmm3
0x180089719  divsd   xmm3, xmm1
0x18008971d  movd    xmm0, esi
0x180089721  cvtdq2pd xmm0, xmm0
0x180089725  divsd   xmm0, xmm2
0x180089729  minsd   xmm3, xmm0
0x18008972d  movaps  xmm0, xmm3
0x180089730  mulsd   xmm0, xmm1
0x180089734  cvttsd2si edi, xmm0
0x180089738  mulsd   xmm3, xmm2
0x18008973c  cvttsd2si ebx, xmm3
0x180089740  mov     qword ptr [rbp+0C0h+rectDst.left], r13
0x180089744  mov     [rbp+0C0h+rectDst.right], edi
0x180089747  mov     [rbp+0C0h+rectDst.bottom], ebx
0x18008974a  lea     this, [rbp+0C0h+bmpDst]; this
0x18008974e  call    ??0CImage@ATL@@QEAA@XZ; ATL::CImage::CImage(void)
0x180089753  nop
0x180089754  neg     ebx
0x180089756  mov     [rsp+1C0h+var_190], 1; nHeight
0x18008975e  mov     bIsThumbnail, 20h ; ' '; nBPP
0x180089764  mov     nHeight, ebx; nHeight
0x180089767  mov     nWidth, edi; nWidth
0x180089769  lea     this, [rbp+0C0h+bmpDst]; this
0x18008976d  call    ?CreateEx@CImage@ATL@@QEAAHHHHKPEBKK@Z; ATL::CImage::CreateEx(int,int,int,ulong,ulong const *,ulong)
0x180089772  test    r12d, r12d
0x180089775  jz      short loc_1800897AB
0x180089777  mov     this, [r15+0E8h]
0x18008977e  mov     rax, [this]
0x180089781  lea     rdx, [rbp+0C0h+rectWnd]
0x180089785  mov     qword ptr [rsp+1C0h+dwFlags], rdx; hDestDC
0x18008978a  mov     r9, [rbp+0C0h+bmpSrc.m_hBitmap]
0x18008978e  lea     r8, [rbp+0C0h+rectDst]
0x180089792  mov     rdx, [rbp+0C0h+bmpDst.m_hBitmap]
0x180089796  mov     rax, [rax+410h]
0x18008979d  call    cs:__guard_dispatch_icall_fptr
0x1800897a3  test    eax, eax
0x1800897a5  jnz     loc_180089842
0x1800897ab  lea     rdi, ??_7CDC@@6B@; const CDC::`vftable'
0x1800897b2  mov     [rsp+1C0h+dc.__vftable], rdi
0x1800897b7  xorps   xmm0, xmm0
0x1800897ba  movdqu  xmmword ptr [rsp+1C0h+dc.m_hDC], xmm0
0x1800897c0  mov     [rsp+1C0h+dc.m_bPrinting], r13d
0x1800897c5  mov     this, [rbp+0C0h+dcPreview.m_hDC]; hdc
0x1800897c9  call    cs:__imp_CreateCompatibleDC
0x1800897cf  mov     rdx, rax; hDC
0x1800897d2  lea     this, [rsp+1C0h+dc]; this
0x1800897d7  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1800897dc  mov     rdx, [rbp+0C0h+bmpDst.m_hBitmap]; h
0x1800897e0  test    rdx, rdx
0x1800897e3  jz      short loc_1800897F5
0x1800897e5  mov     this, [rsp+1C0h+dc.m_hDC]; hdc
0x1800897ea  call    cs:__imp_SelectObject
0x1800897f0  mov     rbx, rax
0x1800897f3  jmp     short loc_1800897F8
0x1800897f5  mov     rbx, r13
0x1800897f8  lea     r9, [rbp+0C0h+rectWnd]; rectSrc
0x1800897fc  lea     r8, [rbp+0C0h+rectDst]; rectDest
0x180089800  mov     rdx, [rsp+1C0h+dc.m_hDC]; hDestDC
0x180089805  lea     this, [rbp+0C0h+bmpSrc]; this
0x180089809  call    ?AlphaBlend@CImage@ATL@@QEBAHPEAUHDC__@@AEBUtagRECT@@1EE@Z; ATL::CImage::AlphaBlend(HDC__ *,tagRECT const &,tagRECT const &,uchar,uchar)
0x18008980e  test    rbx, rbx
0x180089811  jz      short loc_180089822
0x180089813  mov     rdx, rbx; h
0x180089816  mov     this, [rsp+1C0h+dc.m_hDC]; hdc
0x18008981b  call    cs:__imp_SelectObject
0x180089821  nop
0x180089822  mov     [rsp+1C0h+dc.__vftable], rdi
0x180089827  cmp     [rsp+1C0h+dc.m_hDC], r13
0x18008982c  jz      short loc_180089842
0x18008982e  lea     this, [rsp+1C0h+dc]; this
0x180089833  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180089838  mov     this, rax; hdc
0x18008983b  call    cs:__imp_DeleteDC
0x180089841  nop
0x180089842  mov     rbx, [rbp+0C0h+bmpDst.m_hBitmap]
0x180089846  mov     [rbp+0C0h+bmpDst.m_hBitmap], r13
0x18008984a  mov     [rbp+0C0h+bmpDst.m_pBits], r13
0x18008984e  mov     qword ptr [rbp+0C0h+bmpDst.m_nWidth], r13
0x180089852  mov     qword ptr [rbp+0C0h+bmpDst.m_nPitch], r13
0x180089856  or      [rbp+0C0h+bmpDst.m_iTransparentColor], 0FFFFFFFFh
0x18008985a  or      [rbp+0C0h+bmpDst.m_clrTransparentColor], 0FFFFFFFFh
0x18008985e  mov     word ptr [rbp+0C0h+bmpDst.m_bIsDIBSection], r13w
0x180089863  lea     this, [rbp+0C0h+bmpDst]; this
0x180089867  call    ??1CImage@ATL@@UEAA@XZ; ATL::CImage::~CImage(void)
0x18008986c  nop
0x18008986d  lea     this, [rsp+1C0h+dcThumbnail]; this
0x180089872  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x180089877  nop
0x180089878  lea     this, [rbp+0C0h+dcPreview]; this
0x18008987c  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180089881  nop
0x180089882  lea     this, [rbp+0C0h+bmpSrc]; this
0x180089886  call    ??1CImage@ATL@@UEAA@XZ; ATL::CImage::~CImage(void)
0x18008988b  mov     rax, rbx
0x18008988e  jmp     short loc_180089892
0x180089890  xor     eax, eax
0x180089892  mov     this, [rbp+0C0h+var_40]
0x180089899  xor     this, rsp; StackCookie
0x18008989c  call    __security_check_cookie
0x1800898a1  mov     rbx, [rsp+1C0h+arg_10]
0x1800898a9  add     rsp, 190h
0x1800898b0  pop     r15
0x1800898b2  pop     r14
0x1800898b4  pop     r13
0x1800898b6  pop     r12
0x1800898b8  pop     rdi
0x1800898b9  pop     rsi
0x1800898ba  pop     rbp
0x1800898bb  retn
```
