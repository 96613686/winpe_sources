# CMFCPopupMenu::DrawFade(CDC *)

- ea: `0x1800bc5f0`
- end: `0x1800bcb59`
- name: `?DrawFade@CMFCPopupMenu@@MEAAXPEAVCDC@@@Z`
- size: `1385`
- prototype: `void __fastcall(CMFCPopupMenu *this, CDC *pPaintDC)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18002f840`
- `0x18005d370`
- `0x18006cab0`
- `0x1800bc5f0`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af4b0`
- `0x1802afdb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x1800bc897`
- `VCRUNTIME140!memcpy` at `0x1800bc897`
- `USER32!GetClientRect` at `0x1800bc634`
- `USER32!GetClientRect` at `0x1800bc634`
- `USER32!GetWindowRect` at `0x1800bc8f9`
- `USER32!GetWindowRect` at `0x1800bc8f9`
- `GDI32!CreateDIBSection` at `0x1800bc76a`
- `GDI32!CreateDIBSection` at `0x1800bc7af`
- `GDI32!CreateDIBSection` at `0x1800bc7f1`
- `GDI32!CreateDIBSection` at `0x1800bc76a`
- `GDI32!CreateDIBSection` at `0x1800bc7af`
- `GDI32!CreateDIBSection` at `0x1800bc7f1`
- `GDI32!BitBlt` at `0x1800bc875`
- `GDI32!BitBlt` at `0x1800bcb04`
- `GDI32!BitBlt` at `0x1800bc875`
- `GDI32!BitBlt` at `0x1800bcb04`
- `GDI32!CreateCompatibleBitmap` at `0x1800bc6ec`
- `GDI32!CreateCompatibleBitmap` at `0x1800bc6ec`
- `GDI32!SelectObject` at `0x1800bc70d`
- `GDI32!SelectObject` at `0x1800bc82c`
- `GDI32!SelectObject` at `0x1800bc8ad`
- `GDI32!SelectObject` at `0x1800bc99c`
- `GDI32!SelectObject` at `0x1800bca00`
- `GDI32!SelectObject` at `0x1800bca9d`
- `GDI32!SelectObject` at `0x1800bcb1a`
- `GDI32!SelectObject` at `0x1800bc70d`
- `GDI32!SelectObject` at `0x1800bc82c`
- `GDI32!SelectObject` at `0x1800bc8ad`
- `GDI32!SelectObject` at `0x1800bc99c`
- `GDI32!SelectObject` at `0x1800bca00`
- `GDI32!SelectObject` at `0x1800bca9d`
- `GDI32!SelectObject` at `0x1800bcb1a`
- `GDI32!CreateCompatibleDC` at `0x1800bc67c`
- `GDI32!CreateCompatibleDC` at `0x1800bc67c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMFCPopupMenu::DrawFade(CMFCPopupMenu *this, CDC *pPaintDC)
{
  CDC *v2; // r14
  int m_iShadowSize; // r8d
  int v5; // r12d
  int v6; // r13d
  void *v7; // rbx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  void *m_hObject; // rdx
  HGDIOBJ v12; // rax
  CGdiObject *v13; // r15
  HBITMAP DIBSection; // rax
  HBITMAP v15; // rax
  HBITMAP v16; // rax
  void *v17; // rdx
  HGDIOBJ v18; // rax
  HDC v19; // rcx
  void *v20; // rdx
  HGDIOBJ v21; // rax
  CPoint *(__fastcall *SetViewportOrg)(CDC *, CPoint *, int, int); // rax
  CPoint *(__fastcall *v23)(CDC *, CPoint *, int, int); // rax
  void *v24; // rdx
  HGDIOBJ v25; // rax
  unsigned int *m_cFadeSrcBits; // r15
  __int32 v27; // eax
  __int32 v28; // eax
  void *v29; // rdx
  HGDIOBJ v30; // rax
  CGdiObject *v31; // rsi
  __int64 v32; // r14
  __int64 v33; // r12
  _DWORD *v34; // rsi
  unsigned int v35; // edx
  unsigned int v36; // ecx
  void *v37; // rdx
  HGDIOBJ v38; // rax
  int cy; // ecx
  int cx; // r9d
  int top; // r8d
  int left; // edx
  HGDIOBJ v43; // rax
  CDC dcMem; // [rsp+50h] [rbp-69h] BYREF
  CPoint m_cFadeDstBits; // [rsp+70h] [rbp-49h] BYREF
  int v46; // [rsp+78h] [rbp-41h]
  CPoint result; // [rsp+80h] [rbp-39h] BYREF
  CDC *v48; // [rsp+88h] [rbp-31h]
  CRect rectClient; // [rsp+90h] [rbp-29h] BYREF
  CRect rect; // [rsp+A0h] [rbp-19h] BYREF
  tagBITMAPINFOHEADER bih; // [rsp+B0h] [rbp-9h] BYREF

  v2 = pPaintDC;
  v48 = pPaintDC;
  rectClient = 0;
  GetClientRect(this->m_hWnd, &rectClient);
  m_iShadowSize = this->m_iShadowSize;
  v5 = m_iShadowSize + this->m_FinalSize.cx;
  v46 = v5;
  v6 = m_iShadowSize + this->m_FinalSize.cy;
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  v7 = 0;
  m_hDC = 0;
  if ( v2 )
    m_hDC = v2->m_hDC;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&dcMem, CompatibleDC) )
  {
    if ( this != (CMFCPopupMenu *)-6104LL && this->m_bmpScreenDst.m_hObject )
      goto LABEL_35;
    if ( CMFCPopupMenu::GetAnimationType(0) != FADE )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( afxGlobalData.m_nBitsPerPixel <= 8 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v2->m_hDC, v5, v6);
        CGdiObject::Attach(&this->m_bmpScreenDst, CompatibleBitmap);
        m_hObject = 0;
        if ( this != (CMFCPopupMenu *)-6104LL )
          m_hObject = this->m_bmpScreenDst.m_hObject;
        v12 = SelectObject(dcMem.m_hDC, m_hObject);
        v13 = CGdiObject::FromHandle(v12);
LABEL_26:
        rect = 0;
        this->DoPaint(this, &dcMem);
        m_cFadeDstBits = (CPoint)this->GetMenuBar(this);
        GetWindowRect(*(HWND *)(*(_QWORD *)&m_cFadeDstBits + 64LL), &rect);
        CWnd::ScreenToClient(this, &rect);
        SetViewportOrg = dcMem.SetViewportOrg;
        if ( SetViewportOrg == CDC::SetViewportOrg )
          CDC::SetViewportOrg(&dcMem, &result, rect.left, rect.top);
        else
          SetViewportOrg(&dcMem, &result, *(_QWORD *)&rect.left, HIDWORD(*(_QWORD *)&rect.left));
        (*(void (__fastcall **)(CPoint, CDC *))(**(_QWORD **)&m_cFadeDstBits + 1240LL))(m_cFadeDstBits, &dcMem);
        v23 = dcMem.SetViewportOrg;
        if ( v23 == CDC::SetViewportOrg )
          CDC::SetViewportOrg(&dcMem, &m_cFadeDstBits, 0, 0);
        else
          v23(&dcMem, &m_cFadeDstBits, 0, 0);
        v24 = 0;
        if ( v13 )
          v24 = v13->m_hObject;
        v25 = SelectObject(dcMem.m_hDC, v24);
        CGdiObject::FromHandle(v25);
LABEL_35:
        m_cFadeSrcBits = this->m_cFadeSrcBits;
        m_cFadeDstBits = (CPoint)this->m_cFadeDstBits;
        result = (CPoint)this->m_cFadeTmpBits;
        v27 = CMFCPopupMenu::GetAnimationType(0) - 1;
        if ( v27 && (v28 = v27 - 1) != 0 )
        {
          if ( v28 != 1 )
          {
LABEL_56:
            v43 = SelectObject(dcMem.m_hDC, v7);
            CGdiObject::FromHandle(v43);
            goto LABEL_57;
          }
          v29 = 0;
          if ( this != (CMFCPopupMenu *)-6120LL )
            v29 = this->m_bmpScreenTmp.m_hObject;
          v30 = SelectObject(dcMem.m_hDC, v29);
          v31 = CGdiObject::FromHandle(v30);
          *(_QWORD *)&rect.left = v31;
          if ( v5 * v6 > 0 )
          {
            v32 = *(_QWORD *)&m_cFadeDstBits - (_QWORD)m_cFadeSrcBits;
            v33 = (unsigned int)(v5 * v6);
            v34 = (_DWORD *)result;
            do
            {
              v35 = *(unsigned int *)((char *)m_cFadeSrcBits + v32);
              v36 = *m_cFadeSrcBits++;
              *v34++ = CDrawingManager::PixelAlpha(v36, v35, 100 - this->m_iFadePercent);
              --v33;
            }
            while ( v33 );
            v2 = v48;
            v31 = *(CGdiObject **)&rect.left;
            v5 = v46;
          }
          BitBlt(v2->m_hDC, rectClient.left, rectClient.top, v5, v6, dcMem.m_hDC, 0, 0, 0xCC0020u);
        }
        else
        {
          v37 = 0;
          if ( this != (CMFCPopupMenu *)-6104LL )
            v37 = this->m_bmpScreenDst.m_hObject;
          v38 = SelectObject(dcMem.m_hDC, v37);
          v31 = CGdiObject::FromHandle(v38);
          cy = this->m_AnimSize.cy;
          cx = this->m_AnimSize.cx;
          if ( this->m_bIsAnimDown )
            top = rectClient.top;
          else
            top = rectClient.bottom - cy;
          if ( this->m_bIsAnimRight )
            left = rectClient.left;
          else
            left = rectClient.right - cx;
          BitBlt(v2->m_hDC, left, top, cx, cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
        }
        if ( v31 )
          v7 = v31->m_hObject;
        goto LABEL_56;
      }
    }
    bih.biSize = 40;
    bih.biWidth = v5;
    bih.biHeight = v6;
    *(_QWORD *)&bih.biPlanes = 2097153;
    bih.biSizeImage = v5 * v6;
    *(_QWORD *)&bih.biXPelsPerMeter = 0;
    *(_QWORD *)&bih.biClrUsed = 0;
    DIBSection = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeSrcBits, 0, 0);
    if ( DIBSection )
    {
      if ( this->m_cFadeSrcBits )
      {
        CGdiObject::Attach(&this->m_bmpScreenSrc, DIBSection);
        v15 = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeDstBits, 0, 0);
        if ( v15 )
        {
          if ( this->m_cFadeDstBits )
          {
            CGdiObject::Attach(&this->m_bmpScreenDst, v15);
            v16 = CreateDIBSection(dcMem.m_hDC, (const BITMAPINFO *)&bih, 0, (void **)&this->m_cFadeTmpBits, 0, 0);
            if ( v16 )
            {
              if ( this->m_cFadeTmpBits )
              {
                CGdiObject::Attach(&this->m_bmpScreenTmp, v16);
                v17 = 0;
                if ( this != (CMFCPopupMenu *)-6088LL )
                  v17 = this->m_bmpScreenSrc.m_hObject;
                v18 = SelectObject(dcMem.m_hDC, v17);
                v13 = CGdiObject::FromHandle(v18);
                v19 = 0;
                if ( v2 )
                  v19 = v2->m_hDC;
                BitBlt(dcMem.m_hDC, 0, 0, v5, v6, v19, rectClient.left, rectClient.top, 0xCC0020u);
                memcpy(this->m_cFadeDstBits, this->m_cFadeSrcBits, 4 * v5 * (__int64)v6);
                v20 = 0;
                if ( this != (CMFCPopupMenu *)-6104LL )
                  v20 = this->m_bmpScreenDst.m_hObject;
                v21 = SelectObject(dcMem.m_hDC, v20);
                CGdiObject::FromHandle(v21);
                goto LABEL_26;
              }
            }
          }
        }
      }
    }
  }
LABEL_57:
  CDC::~CDC(&dcMem);
}

```

## disassembly

```asm
0x1800bc5f0  mov     [rsp-8+arg_10], rbx
0x1800bc5f5  push    rbp
0x1800bc5f6  push    rsi
0x1800bc5f7  push    rdi
0x1800bc5f8  push    r12
0x1800bc5fa  push    r13
0x1800bc5fc  push    r14
0x1800bc5fe  push    r15
0x1800bc600  lea     rbp, [rsp-27h]
0x1800bc605  sub     rsp, 0E0h
0x1800bc60c  mov     rax, cs:__security_cookie
0x1800bc613  xor     rax, rsp
0x1800bc616  mov     [rbp+57h+var_38], rax
0x1800bc61a  mov     r14, pPaintDC
0x1800bc61d  mov     [rbp+57h+var_88], pPaintDC
0x1800bc621  mov     rdi, this
0x1800bc624  xorps   xmm0, xmm0
0x1800bc627  movdqu  xmmword ptr [rbp+57h+rectClient.left], xmm0
0x1800bc62c  lea     pPaintDC, [rbp+57h+rectClient]; lpRect
0x1800bc630  mov     this, [this+40h]; hWnd
0x1800bc634  call    cs:__imp_GetClientRect
0x1800bc63a  mov     r8d, [rdi+1810h]
0x1800bc641  mov     r12d, [rdi+210h]
0x1800bc648  add     r12d, r8d
0x1800bc64b  mov     [rbp+57h+var_98], r12d
0x1800bc64f  mov     r13d, [rdi+214h]
0x1800bc656  add     r13d, r8d
0x1800bc659  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1800bc660  mov     [rbp+57h+dcMem.__vftable], rax
0x1800bc664  xorps   xmm0, xmm0
0x1800bc667  movdqu  xmmword ptr [rbp+57h+dcMem.m_hDC], xmm0
0x1800bc66c  xor     ebx, ebx
0x1800bc66e  mov     [rbp+57h+dcMem.m_bPrinting], ebx
0x1800bc671  test    r14, r14
0x1800bc674  mov     ecx, ebx
0x1800bc676  jz      short loc_1800BC67C
0x1800bc678  mov     this, [r14+8]; hdc
0x1800bc67c  call    cs:__imp_CreateCompatibleDC
0x1800bc682  mov     pPaintDC, rax; hDC
0x1800bc685  lea     this, [rbp+57h+dcMem]; this
0x1800bc689  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1800bc68e  test    eax, eax
0x1800bc690  jz      loc_1800BCB29
0x1800bc696  lea     rsi, [rdi+17D8h]
0x1800bc69d  mov     r15d, 1
0x1800bc6a3  test    rsi, rsi
0x1800bc6a6  jz      short loc_1800BC6B2
0x1800bc6a8  cmp     [rsi+8], rbx
0x1800bc6ac  jnz     loc_1800BC9AA
0x1800bc6b2  xor     ecx, ecx; bNoSystem
0x1800bc6b4  call    ?GetAnimationType@CMFCPopupMenu@@SA?AW4ANIMATION_TYPE@1@H@Z; CMFCPopupMenu::GetAnimationType(int)
0x1800bc6b9  cmp     eax, 3
0x1800bc6bc  jz      short loc_1800BC723
0x1800bc6be  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800bc6c4  jnz     short loc_1800BC6D9
0x1800bc6c6  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800bc6cd  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800bc6d2  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800bc6d9  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x1800bc6e0  jg      short loc_1800BC723
0x1800bc6e2  mov     r8d, r13d; cy
0x1800bc6e5  mov     edx, r12d; cx
0x1800bc6e8  mov     this, [r14+8]; hdc
0x1800bc6ec  call    cs:__imp_CreateCompatibleBitmap
0x1800bc6f2  mov     pPaintDC, rax; hObject
0x1800bc6f5  mov     this, rsi; this
0x1800bc6f8  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800bc6fd  test    rsi, rsi
0x1800bc700  mov     pPaintDC, rbx
0x1800bc703  jz      short loc_1800BC709
0x1800bc705  mov     pPaintDC, [rsi+8]; h
0x1800bc709  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc70d  call    cs:__imp_SelectObject
0x1800bc713  mov     this, rax; h
0x1800bc716  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bc71b  mov     r15, rax
0x1800bc71e  jmp     loc_1800BC8BB
0x1800bc723  mov     [rbp+57h+bih.biSize], 28h ; '('
0x1800bc72a  mov     [rbp+57h+bih.biWidth], r12d
0x1800bc72e  mov     [rbp+57h+bih.biHeight], r13d
0x1800bc732  mov     qword ptr [rbp+57h+bih.biPlanes], 200001h
0x1800bc73a  mov     eax, r13d
0x1800bc73d  imul    eax, r12d
0x1800bc741  mov     [rbp+57h+bih.biSizeImage], eax
0x1800bc744  mov     qword ptr [rbp+57h+bih.biXPelsPerMeter], rbx
0x1800bc748  mov     qword ptr [rbp+57h+bih.biClrUsed], rbx
0x1800bc74c  lea     r15, [rdi+17F8h]
0x1800bc753  mov     [rsp+110h+offset], ebx; offset
0x1800bc757  mov     [rsp+110h+hSection], rbx; hSection
0x1800bc75c  mov     r9, r15; ppvBits
0x1800bc75f  xor     r8d, r8d; usage
0x1800bc762  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x1800bc766  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc76a  call    cs:__imp_CreateDIBSection
0x1800bc770  test    rax, rax
0x1800bc773  jz      loc_1800BCB29
0x1800bc779  cmp     [r15], rbx
0x1800bc77c  jz      loc_1800BCB29
0x1800bc782  lea     r15, [rdi+17C8h]
0x1800bc789  mov     pPaintDC, rax; hObject
0x1800bc78c  mov     this, r15; this
0x1800bc78f  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800bc794  lea     r9, [rdi+1800h]; ppvBits
0x1800bc79b  mov     [rsp+110h+offset], ebx; offset
0x1800bc79f  mov     [rsp+110h+hSection], rbx; hSection
0x1800bc7a4  xor     r8d, r8d; usage
0x1800bc7a7  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x1800bc7ab  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc7af  call    cs:__imp_CreateDIBSection
0x1800bc7b5  test    rax, rax
0x1800bc7b8  jz      loc_1800BCB29
0x1800bc7be  cmp     [rdi+1800h], rbx
0x1800bc7c5  jz      loc_1800BCB29
0x1800bc7cb  mov     pPaintDC, rax; hObject
0x1800bc7ce  mov     this, rsi; this
0x1800bc7d1  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800bc7d6  lea     r9, [rdi+1808h]; ppvBits
0x1800bc7dd  mov     [rsp+110h+offset], ebx; offset
0x1800bc7e1  mov     [rsp+110h+hSection], rbx; hSection
0x1800bc7e6  xor     r8d, r8d; usage
0x1800bc7e9  lea     pPaintDC, [rbp+57h+bih]; pbmi
0x1800bc7ed  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc7f1  call    cs:__imp_CreateDIBSection
0x1800bc7f7  test    rax, rax
0x1800bc7fa  jz      loc_1800BCB29
0x1800bc800  cmp     [rdi+1808h], rbx
0x1800bc807  jz      loc_1800BCB29
0x1800bc80d  lea     this, [rdi+17E8h]; this
0x1800bc814  mov     pPaintDC, rax; hObject
0x1800bc817  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800bc81c  test    r15, r15
0x1800bc81f  mov     pPaintDC, rbx
0x1800bc822  jz      short loc_1800BC828
0x1800bc824  mov     pPaintDC, [r15+8]; h
0x1800bc828  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc82c  call    cs:__imp_SelectObject
0x1800bc832  mov     this, rax; h
0x1800bc835  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bc83a  mov     r15, rax
0x1800bc83d  test    r14, r14
0x1800bc840  mov     this, rbx
0x1800bc843  jz      short loc_1800BC849
0x1800bc845  mov     this, [r14+8]
0x1800bc849  mov     [rsp+110h+rop], 0CC0020h; rop
0x1800bc851  mov     eax, [rbp+57h+rectClient.top]
0x1800bc854  mov     [rsp+110h+y1], eax; y1
0x1800bc858  mov     eax, [rbp+57h+rectClient.left]
0x1800bc85b  mov     [rsp+110h+x1], eax; x1
0x1800bc85f  mov     qword ptr [rsp+110h+offset], this; hdcSrc
0x1800bc864  mov     dword ptr [rsp+110h+hSection], r13d; cy
0x1800bc869  mov     r9d, r12d; cx
0x1800bc86c  xor     r8d, r8d; y
0x1800bc86f  xor     edx, edx; x
0x1800bc871  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc875  call    cs:__imp_BitBlt
0x1800bc87b  movsxd  r8, r13d
0x1800bc87e  movsxd  rax, r12d
0x1800bc881  imul    r8, rax
0x1800bc885  shl     r8, 2; Size
0x1800bc889  mov     pPaintDC, [rdi+17F8h]; Src
0x1800bc890  mov     this, [rdi+1800h]; void *
0x1800bc897  call    cs:__imp_memcpy
0x1800bc89d  test    rsi, rsi
0x1800bc8a0  mov     pPaintDC, rbx
0x1800bc8a3  jz      short loc_1800BC8A9
0x1800bc8a5  mov     pPaintDC, [rsi+8]; h
0x1800bc8a9  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc8ad  call    cs:__imp_SelectObject
0x1800bc8b3  mov     this, rax; h
0x1800bc8b6  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bc8bb  xorps   xmm0, xmm0
0x1800bc8be  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800bc8c3  mov     rax, [rdi]
0x1800bc8c6  lea     pPaintDC, [rbp+57h+dcMem]
0x1800bc8ca  mov     this, rdi
0x1800bc8cd  mov     rax, [rax+3E8h]
0x1800bc8d4  call    cs:__guard_dispatch_icall_fptr
0x1800bc8da  mov     rax, [rdi]
0x1800bc8dd  mov     this, rdi
0x1800bc8e0  mov     rax, [rax+3A0h]
0x1800bc8e7  call    cs:__guard_dispatch_icall_fptr
0x1800bc8ed  mov     qword ptr [rbp+57h+var_A0.x], rax
0x1800bc8f1  lea     pPaintDC, [rbp+57h+rect]; lpRect
0x1800bc8f5  mov     this, [rax+40h]; hWnd
0x1800bc8f9  call    cs:__imp_GetWindowRect
0x1800bc8ff  lea     pPaintDC, [rbp+57h+rect]; lpRect
0x1800bc903  mov     this, rdi; this
0x1800bc906  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800bc90b  mov     this, [rbp+57h+dcMem.__vftable]
0x1800bc90f  mov     rax, [this+80h]
0x1800bc916  mov     r8, qword ptr [rbp+57h+rect.left]; x
0x1800bc91a  mov     r9, r8
0x1800bc91d  shr     r9, 20h; y
0x1800bc921  lea     this, ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x1800bc928  lea     pPaintDC, [rbp+57h+result]; result
0x1800bc92c  cmp     rax, this
0x1800bc92f  lea     this, [rbp+57h+dcMem]; this
0x1800bc933  jnz     short loc_1800BC93C
0x1800bc935  call    ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x1800bc93a  jmp     short loc_1800BC942
0x1800bc93c  call    cs:__guard_dispatch_icall_fptr
0x1800bc942  mov     this, qword ptr [rbp+57h+var_A0.x]
0x1800bc946  mov     rax, [this]
0x1800bc949  lea     pPaintDC, [rbp+57h+dcMem]
0x1800bc94d  mov     rax, [rax+4D8h]
0x1800bc954  call    cs:__guard_dispatch_icall_fptr
0x1800bc95a  mov     rax, [rbp+57h+dcMem.__vftable]
0x1800bc95e  mov     rax, [rax+80h]
0x1800bc965  lea     this, ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x1800bc96c  xor     r9d, r9d; y
0x1800bc96f  xor     r8d, r8d; x
0x1800bc972  lea     pPaintDC, [rbp+57h+var_A0]; result
0x1800bc976  cmp     rax, this
0x1800bc979  lea     this, [rbp+57h+dcMem]; this
0x1800bc97d  jnz     short loc_1800BC986
0x1800bc97f  call    ?SetViewportOrg@CDC@@UEAA?AVCPoint@@HH@Z; CDC::SetViewportOrg(int,int)
0x1800bc984  jmp     short loc_1800BC98C
0x1800bc986  call    cs:__guard_dispatch_icall_fptr
0x1800bc98c  test    r15, r15
0x1800bc98f  mov     pPaintDC, rbx
0x1800bc992  jz      short loc_1800BC998
0x1800bc994  mov     pPaintDC, [r15+8]; h
0x1800bc998  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bc99c  call    cs:__imp_SelectObject
0x1800bc9a2  mov     this, rax; h
0x1800bc9a5  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bc9aa  mov     r15, [rdi+17F8h]
0x1800bc9b1  mov     rax, [rdi+1800h]
0x1800bc9b8  mov     qword ptr [rbp+57h+var_A0.x], rax
0x1800bc9bc  mov     this, [rdi+1808h]
0x1800bc9c3  mov     qword ptr [rbp+57h+result.x], this
0x1800bc9c7  xor     ecx, ecx; bNoSystem
0x1800bc9c9  call    ?GetAnimationType@CMFCPopupMenu@@SA?AW4ANIMATION_TYPE@1@H@Z; CMFCPopupMenu::GetAnimationType(int)
0x1800bc9ce  sub     eax, 1
0x1800bc9d1  jz      loc_1800BCA8D
0x1800bc9d7  sub     eax, 1
0x1800bc9da  jz      loc_1800BCA8D
0x1800bc9e0  cmp     eax, 1
0x1800bc9e3  jnz     loc_1800BCB13
0x1800bc9e9  lea     rax, [rdi+17E8h]
0x1800bc9f0  test    rax, rax
0x1800bc9f3  mov     pPaintDC, rbx
0x1800bc9f6  jz      short loc_1800BC9FC
0x1800bc9f8  mov     pPaintDC, [rax+8]; h
0x1800bc9fc  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bca00  call    cs:__imp_SelectObject
0x1800bca06  mov     this, rax; h
0x1800bca09  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bca0e  mov     rsi, rax
0x1800bca11  mov     qword ptr [rbp+57h+rect.left], rax
0x1800bca15  mov     ecx, r13d
0x1800bca18  imul    ecx, r12d
0x1800bca1c  test    ecx, ecx
0x1800bca1e  jle     short loc_1800BCA63
0x1800bca20  mov     r14, qword ptr [rbp+57h+var_A0.x]
0x1800bca24  sub     r14, r15
0x1800bca27  mov     r12d, ecx
0x1800bca2a  mov     rsi, qword ptr [rbp+57h+result.x]
0x1800bca2e  mov     edx, [r14+r15]; dstPixel
0x1800bca32  mov     ecx, [r15]; srcPixel
0x1800bca35  lea     r15, [r15+4]
0x1800bca39  mov     r8d, 64h ; 'd'
0x1800bca3f  sub     r8d, [rdi+16D8h]; percent
0x1800bca46  call    ?PixelAlpha@CDrawingManager@@SAKKKH@Z; CDrawingManager::PixelAlpha(ulong,ulong,int)
0x1800bca4b  mov     [rsi], eax
0x1800bca4d  lea     rsi, [rsi+4]
0x1800bca51  sub     r12, 1
0x1800bca55  jnz     short loc_1800BCA2E
0x1800bca57  mov     r14, [rbp+57h+var_88]
0x1800bca5b  mov     rsi, qword ptr [rbp+57h+rect.left]
0x1800bca5f  mov     r12d, [rbp+57h+var_98]
0x1800bca63  mov     [rsp+110h+rop], 0CC0020h
0x1800bca6b  mov     [rsp+110h+y1], ebx
0x1800bca6f  mov     [rsp+110h+x1], ebx
0x1800bca73  mov     rax, [rbp+57h+dcMem.m_hDC]
0x1800bca77  mov     qword ptr [rsp+110h+offset], rax
0x1800bca7c  mov     dword ptr [rsp+110h+hSection], r13d
0x1800bca81  mov     r9d, r12d
0x1800bca84  mov     r8d, [rbp+57h+rectClient.top]
0x1800bca88  mov     edx, [rbp+57h+rectClient.left]
0x1800bca8b  jmp     short loc_1800BCB00
0x1800bca8d  test    rsi, rsi
0x1800bca90  mov     pPaintDC, rbx
0x1800bca93  jz      short loc_1800BCA99
0x1800bca95  mov     pPaintDC, [rsi+8]; h
0x1800bca99  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x1800bca9d  call    cs:__imp_SelectObject
0x1800bcaa3  mov     this, rax; h
0x1800bcaa6  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800bcaab  mov     rsi, rax
0x1800bcaae  mov     ecx, [rdi+1690h]
0x1800bcab4  mov     r9d, [rdi+168Ch]; cx
0x1800bcabb  cmp     [rdi+1698h], ebx
0x1800bcac1  jz      short loc_1800BCAC9
0x1800bcac3  mov     r8d, [rbp+57h+rectClient.top]
0x1800bcac7  jmp     short loc_1800BCAD0
0x1800bcac9  mov     r8d, [rbp+57h+rectClient.bottom]
0x1800bcacd  sub     r8d, ecx; y
0x1800bcad0  cmp     [rdi+1694h], ebx
0x1800bcad6  jz      short loc_1800BCADD
  ... truncated ...
```
