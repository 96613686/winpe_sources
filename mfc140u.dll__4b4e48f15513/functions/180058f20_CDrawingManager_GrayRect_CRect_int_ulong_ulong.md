# CDrawingManager::GrayRect(CRect,int,ulong,ulong)

- ea: `0x180058f20`
- end: `0x180059386`
- name: `?GrayRect@CDrawingManager@@QEAAHVCRect@@HKK@Z`
- size: `1126`
- prototype: `int __fastcall(CDrawingManager *this, CRect rect, int nPercentage, unsigned int clrTransparent, unsigned int clrDisabled)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180173910`
- `0x1801774e0`

## callees

- `0x18001d090`
- `0x180058150`
- `0x180058f20`
- `0x18005d270`
- `0x18005d5b0`
- `0x18005d820`
- `0x18006cab0`
- `0x180174720`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180059334`
- `GDI32!DeleteDC` at `0x180059372`
- `GDI32!DeleteDC` at `0x180059334`
- `GDI32!DeleteDC` at `0x180059372`
- `GDI32!BitBlt` at `0x1800590f7`
- `GDI32!BitBlt` at `0x1800592d7`
- `GDI32!BitBlt` at `0x1800590f7`
- `GDI32!BitBlt` at `0x1800592d7`
- `GDI32!CreateCompatibleBitmap` at `0x18005902a`
- `GDI32!CreateCompatibleBitmap` at `0x18005902a`
- `GDI32!DeleteObject` at `0x1800592fb`
- `GDI32!DeleteObject` at `0x1800592fb`
- `GDI32!SelectObject` at `0x180059062`
- `GDI32!SelectObject` at `0x1800590b3`
- `GDI32!SelectObject` at `0x1800592e9`
- `GDI32!SelectObject` at `0x180059062`
- `GDI32!SelectObject` at `0x1800590b3`
- `GDI32!SelectObject` at `0x1800592e9`
- `GDI32!CreateCompatibleDC` at `0x180058ff2`
- `GDI32!CreateCompatibleDC` at `0x180058ff2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDrawingManager::GrayRect(
        CDrawingManager *this,
        CRect *rect,
        int nPercentage,
        unsigned int clrTransparent,
        unsigned int clrDisabled)
{
  CRect *v6; // rdi
  HDC__ *v8; // rsi
  CDC *m_dc; // rax
  int v11; // r15d
  int cy; // r12d
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v16; // rax
  HBITMAP__ *Bitmap_32; // rax
  CDC *v18; // rcx
  HDC hdcSrc; // rax
  unsigned int clrBtnHilite; // r13d
  unsigned int *v21; // rax
  unsigned int v22; // eax
  int v23; // r9d
  int v24; // edx
  int v25; // eax
  int v26; // edi
  unsigned int v27; // eax
  HGDIOBJ v28; // rax
  HDC v29; // rax
  HDC v30; // rax
  long double L; // [rsp+50h] [rbp-41h] BYREF
  unsigned int *pBits; // [rsp+58h] [rbp-39h] BYREF
  long double H; // [rsp+60h] [rbp-31h] BYREF
  CDC dcMem; // [rsp+68h] [rbp-29h] BYREF
  CBitmap bmpMem; // [rsp+88h] [rbp-9h] BYREF
  long double S; // [rsp+98h] [rbp+7h] BYREF
  CRect *v37; // [rsp+A0h] [rbp+Fh]
  CDrawingManager *v38; // [rsp+A8h] [rbp+17h]
  CGdiObject *v39; // [rsp+B0h] [rbp+1Fh]
  HGDIOBJ ho; // [rsp+B8h] [rbp+27h]

  LODWORD(L) = nPercentage;
  v6 = rect;
  v37 = rect;
  v38 = this;
  v8 = 0;
  if ( rect->bottom - rect->top <= 0 || rect->right - rect->left <= 0 )
    return 1;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  m_dc = this->m_dc;
  if ( afxGlobalData.m_nBitsPerPixel <= 8 )
  {
    CMFCToolBarImages::FillDitheredRect(this->m_dc, v6);
    return 1;
  }
  v11 = v6->right - v6->left;
  cy = v6->bottom - v6->top;
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  m_hDC = 0;
  if ( m_dc )
    m_hDC = m_dc->m_hDC;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&dcMem, CompatibleDC) )
  {
    bmpMem.m_hObject = 0;
    bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CompatibleBitmap = CreateCompatibleBitmap(this->m_dc->m_hDC, v11, cy);
    if ( CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
    {
      v16 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
      v39 = CGdiObject::FromHandle(v16);
      if ( !v39 )
        AfxThrowInvalidArgException();
      LODWORD(H) = v11;
      HIDWORD(H) = cy;
      Bitmap_32 = CDrawingManager::CreateBitmap_32((const CSize *)&H, (void **)&pBits);
      ho = Bitmap_32;
      if ( Bitmap_32 )
      {
        v8 = (HDC__ *)pBits;
        if ( pBits )
        {
          SelectObject(dcMem.m_hDC, Bitmap_32);
          v18 = this->m_dc;
          if ( v18 )
            hdcSrc = v18->m_hDC;
          else
            hdcSrc = 0;
          BitBlt(dcMem.m_hDC, 0, 0, v11, cy, hdcSrc, v6->left, v6->top, 0xCC0020u);
          if ( clrTransparent != -1 )
            clrTransparent = ((unsigned __int8)clrTransparent << 16) | BYTE2(clrTransparent) | clrTransparent & 0xFF00;
          clrBtnHilite = clrDisabled;
          if ( clrDisabled == -1 )
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            clrBtnHilite = afxGlobalData.clrBtnHilite;
          }
          v21 = (unsigned int *)(unsigned int)(v11 * cy);
          if ( (int)v21 > 0 )
          {
            pBits = (unsigned int *)(unsigned int)(v11 * cy);
            if ( LODWORD(L) == -1 )
            {
              do
              {
                if ( *(_DWORD *)v8 != clrTransparent )
                {
                  CDrawingManager::RGBtoHSL(*(_DWORD *)v8, &H, &S, &L);
                  v22 = CDrawingManager::HLStoRGB_ONE(H, L, 0.0);
                  v23 = (BYTE2(clrBtnHilite) - (unsigned __int8)v22) / 2 + (unsigned __int8)v22;
                  if ( v23 > 255 )
                    LOBYTE(v23) = -1;
                  v24 = (BYTE1(clrBtnHilite) - BYTE1(v22)) / 2 + BYTE1(v22);
                  if ( v24 > 255 )
                    LOBYTE(v24) = -1;
                  v25 = BYTE2(v22) + ((unsigned __int8)clrBtnHilite - BYTE2(v22)) / 2;
                  if ( v25 > 255 )
                    LOBYTE(v25) = -1;
                  *(_DWORD *)v8 = (unsigned __int8)v23 | ((unsigned __int8)v24 << 8) | ((v25 | 0xFFFFFF00) << 16);
                  v21 = pBits;
                }
                ++v8;
                v21 = (unsigned int *)((char *)v21 - 1);
                pBits = v21;
              }
              while ( v21 );
            }
            else
            {
              v26 = LODWORD(L);
              do
              {
                if ( *(_DWORD *)v8 != clrTransparent )
                {
                  CDrawingManager::RGBtoHSL(*(_DWORD *)v8, &H, &S, &L);
                  v27 = CDrawingManager::HLStoRGB_ONE(H, L, 0.0);
                  *(_DWORD *)v8 = CDrawingManager::PixelAlpha(
                                    v27,
                                    (double)v26 * 0.01,
                                    (double)v26 * 0.01,
                                    (double)v26 * 0.01)
                                | 0xFF000000;
                  v21 = pBits;
                }
                ++v8;
                v21 = (unsigned int *)((char *)v21 - 1);
                pBits = v21;
              }
              while ( v21 );
              v6 = v37;
            }
          }
          BitBlt(v38->m_dc->m_hDC, v6->left, v6->top, v11, cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
          v28 = SelectObject(dcMem.m_hDC, v39->m_hObject);
          CGdiObject::FromHandle(v28);
          DeleteObject(ho);
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
          dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( dcMem.m_hDC )
          {
            v29 = CDC::Detach(&dcMem);
            DeleteDC(v29);
          }
          return 1;
        }
      }
      bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
      CGdiObject::~CGdiObject(&bmpMem);
    }
    else
    {
      bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
      CGdiObject::~CGdiObject(&bmpMem);
    }
  }
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcMem.m_hDC != v8 )
  {
    v30 = CDC::Detach(&dcMem);
    DeleteDC(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x180058f20  mov     [rsp-8+arg_10], rsi
0x180058f25  mov     [rsp-8+arg_18], rdi
0x180058f2a  push    rbp
0x180058f2b  push    r12
0x180058f2d  push    r13
0x180058f2f  push    r14
0x180058f31  push    r15
0x180058f33  lea     rbp, [rsp-2Fh]
0x180058f38  sub     rsp, 0C0h
0x180058f3f  mov     r14d, clrTransparent
0x180058f42  mov     dword ptr [rbp+4Fh+L], nPercentage
0x180058f46  mov     rdi, rect
0x180058f49  mov     [rbp+4Fh+var_40], rect
0x180058f4d  mov     r13, this
0x180058f50  mov     [rbp+4Fh+var_38], this
0x180058f54  mov     eax, [rect+0Ch]
0x180058f57  sub     eax, [rect+4]
0x180058f5a  xor     esi, esi
0x180058f5c  test    eax, eax
0x180058f5e  jle     short loc_180058F9F
0x180058f60  mov     eax, [rect+8]
0x180058f63  sub     eax, [rect]
0x180058f65  test    eax, eax
0x180058f67  jle     short loc_180058F9F
0x180058f69  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x180058f6f  jnz     short loc_180058F87
0x180058f71  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058f78  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180058f7d  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180058f87  mov     rax, [r13+8]
0x180058f8b  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x180058f92  jg      short loc_180058FC1
0x180058f94  mov     rect, rdi; rect
0x180058f97  mov     this, rax; pDC
0x180058f9a  call    ?FillDitheredRect@CMFCToolBarImages@@SAXPEAVCDC@@AEBVCRect@@@Z; CMFCToolBarImages::FillDitheredRect(CDC *,CRect const &)
0x180058f9f  mov     eax, 1
0x180058fa4  lea     r11, [rsp+0E0h+var_20]
0x180058fac  mov     rsi, [r11+40h]
0x180058fb0  mov     rdi, [r11+48h]
0x180058fb4  mov     rsp, r11
0x180058fb7  pop     r15
0x180058fb9  pop     r14
0x180058fbb  pop     r13
0x180058fbd  pop     r12
0x180058fbf  pop     rbp
0x180058fc0  retn
0x180058fc1  mov     r15d, [rdi+8]
0x180058fc5  sub     r15d, [rdi]
0x180058fc8  mov     r12d, [rdi+0Ch]
0x180058fcc  sub     r12d, [rdi+4]
0x180058fd0  lea     this, ??_7CDC@@6B@; const CDC::`vftable'
0x180058fd7  mov     [rbp+4Fh+dcMem.__vftable], this
0x180058fdb  xorps   xmm0, xmm0
0x180058fde  movdqu  xmmword ptr [rbp+4Fh+dcMem.m_hDC], xmm0
0x180058fe3  mov     [rbp+4Fh+dcMem.m_bPrinting], esi
0x180058fe6  test    rax, rax
0x180058fe9  mov     this, rsi
0x180058fec  jz      short loc_180058FF2
0x180058fee  mov     this, [rax+8]; hdc
0x180058ff2  call    cs:__imp_CreateCompatibleDC
0x180058ff8  mov     rect, rax; hDC
0x180058ffb  lea     this, [rbp+4Fh+dcMem]; this
0x180058fff  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180059004  test    eax, eax
0x180059006  jnz     short loc_18005900D
0x180059008  jmp     loc_180059355
0x18005900d  mov     [rbp+4Fh+bmpMem.m_hObject], rsi
0x180059011  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059018  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x18005901c  mov     this, [r13+8]
0x180059020  mov     nPercentage, r12d; cy
0x180059023  mov     edx, r15d; cx
0x180059026  mov     this, [this+8]; hdc
0x18005902a  call    cs:__imp_CreateCompatibleBitmap
0x180059030  mov     rect, rax; hObject
0x180059033  lea     this, [rbp+4Fh+bmpMem]; this
0x180059037  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005903c  test    eax, eax
0x18005903e  jnz     short loc_18005905A
0x180059040  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059047  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x18005904b  lea     this, [rbp+4Fh+bmpMem]; this
0x18005904f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059054  nop
0x180059055  jmp     loc_180059355
0x18005905a  mov     rect, [rbp+4Fh+bmpMem.m_hObject]; h
0x18005905e  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x180059062  call    cs:__imp_SelectObject
0x180059068  mov     this, rax; h
0x18005906b  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180059070  mov     [rbp+4Fh+var_30], rax
0x180059074  test    rax, rax
0x180059077  jz      loc_180059380
0x18005907d  mov     dword ptr [rbp+4Fh+H], r15d
0x180059081  mov     dword ptr [rbp+4Fh+H+4], r12d
0x180059085  lea     rect, [rbp+4Fh+pBits]; pBits
0x180059089  lea     this, [rbp+4Fh+H]; size
0x18005908d  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x180059092  mov     [rbp+4Fh+ho], rax
0x180059096  test    rax, rax
0x180059099  jz      loc_180059340
0x18005909f  mov     rsi, [rbp+4Fh+pBits]
0x1800590a3  test    rsi, rsi
0x1800590a6  jz      loc_180059340
0x1800590ac  mov     rect, rax; h
0x1800590af  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x1800590b3  call    cs:__imp_SelectObject
0x1800590b9  mov     edx, [rdi+4]
0x1800590bc  mov     nPercentage, [rdi]
0x1800590bf  mov     this, [r13+8]
0x1800590c3  test    this, this
0x1800590c6  jnz     short loc_1800590CC
0x1800590c8  xor     eax, eax
0x1800590ca  jmp     short loc_1800590D0
0x1800590cc  mov     rax, [this+8]
0x1800590d0  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x1800590d8  mov     [rsp+0E0h+y1], edx; y1
0x1800590dc  mov     [rsp+0E0h+x1], nPercentage; x1
0x1800590e1  mov     [rsp+0E0h+hdcSrc], rax; hdcSrc
0x1800590e6  mov     [rsp+0E0h+cy], r12d; cy
0x1800590eb  mov     clrTransparent, r15d; cx
0x1800590ee  xor     nPercentage, nPercentage; y
0x1800590f1  xor     edx, edx; x
0x1800590f3  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x1800590f7  call    cs:__imp_BitBlt
0x1800590fd  or      nPercentage, 0FFFFFFFFh
0x180059101  cmp     r14d, nPercentage
0x180059104  jz      short loc_180059128
0x180059106  movzx   edx, r14w
0x18005910a  and     edx, 0FFFFFF00h
0x180059110  mov     eax, r14d
0x180059113  shr     eax, 10h
0x180059116  movzx   ecx, al
0x180059119  or      edx, ecx
0x18005911b  movzx   eax, r14b
0x18005911f  shl     eax, 10h
0x180059122  mov     r14d, edx
0x180059125  or      r14d, eax
0x180059128  mov     r13d, [rbp+4Fh+arg_20]
0x18005912c  cmp     r13d, nPercentage
0x18005912f  jnz     short loc_180059157
0x180059131  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180059138  jnz     short loc_180059150
0x18005913a  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180059141  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180059146  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180059150  mov     r13d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x180059157  mov     eax, r12d
0x18005915a  imul    eax, r15d
0x18005915e  test    eax, eax
0x180059160  jle     loc_1800592A2
0x180059166  mov     [rbp+4Fh+pBits], rax
0x18005916a  cmp     dword ptr [rbp+4Fh+L], 0FFFFFFFFh
0x18005916e  jnz     loc_18005923B
0x180059174  cmp     [rsi], r14d
0x180059177  jz      loc_180059227
0x18005917d  lea     r9, [rbp+4Fh+L]; L
0x180059181  lea     r8, [rbp+4Fh+S]; S
0x180059185  lea     rect, [rbp+4Fh+H]; H
0x180059189  mov     ecx, [rsi]; rgb
0x18005918b  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x180059190  xorps   xmm2, xmm2; S
0x180059193  movsd   xmm1, [rbp+4Fh+L]; L
0x180059198  movsd   xmm0, [rbp+4Fh+H]; H
0x18005919d  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x1800591a2  mov     nPercentage, eax
0x1800591a5  movzx   eax, al
0x1800591a8  mov     ecx, r13d
0x1800591ab  shr     ecx, 10h
0x1800591ae  movzx   edx, cl
0x1800591b1  sub     edx, eax
0x1800591b3  jns     short loc_1800591B7
0x1800591b5  inc     edx
0x1800591b7  sar     edx, 1
0x1800591b9  lea     clrTransparent, [rect+rax]
0x1800591bd  mov     r10d, 0FFh
0x1800591c3  cmp     clrTransparent, r10d
0x1800591c6  cmovg   clrTransparent, r10d
0x1800591ca  movzx   ecx, r8w
0x1800591ce  shr     ecx, 8
0x1800591d1  movzx   eax, r13w
0x1800591d5  shr     eax, 8
0x1800591d8  sub     eax, ecx
0x1800591da  jns     short loc_1800591DE
0x1800591dc  inc     eax
0x1800591de  sar     eax, 1
0x1800591e0  lea     edx, [rax+this]
0x1800591e3  cmp     edx, r10d
0x1800591e6  cmovg   edx, r10d
0x1800591ea  shr     nPercentage, 10h
0x1800591ee  movzx   ecx, r8b
0x1800591f2  movzx   eax, r13b
0x1800591f6  sub     eax, ecx
0x1800591f8  jns     short loc_1800591FC
0x1800591fa  inc     eax
0x1800591fc  sar     eax, 1
0x1800591fe  add     eax, ecx
0x180059200  cmp     eax, r10d
0x180059203  cmovg   eax, r10d
0x180059207  movzx   ecx, al
0x18005920a  or      ecx, 0FFFFFF00h
0x180059210  shl     ecx, 10h
0x180059213  movzx   eax, dl
0x180059216  shl     eax, 8
0x180059219  or      ecx, eax
0x18005921b  movzx   eax, r9b
0x18005921f  or      ecx, eax
0x180059221  mov     [rsi], ecx
0x180059223  mov     rax, [rbp+4Fh+pBits]
0x180059227  add     rsi, 4
0x18005922b  sub     rax, 1
0x18005922f  mov     [rbp+4Fh+pBits], rax
0x180059233  jnz     loc_180059174
0x180059239  jmp     short loc_1800592A2
0x18005923b  mov     edi, dword ptr [rbp+4Fh+L]
0x18005923e  cmp     [rsi], r14d
0x180059241  jz      short loc_180059290
0x180059243  lea     r9, [rbp+4Fh+L]; L
0x180059247  lea     r8, [rbp+4Fh+S]; S
0x18005924b  lea     rect, [rbp+4Fh+H]; H
0x18005924f  mov     ecx, [rsi]; rgb
0x180059251  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x180059256  xorps   xmm2, xmm2; S
0x180059259  movsd   xmm1, [rbp+4Fh+L]; L
0x18005925e  movsd   xmm0, [rbp+4Fh+H]; H
0x180059263  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x180059268  movd    xmm1, edi
0x18005926c  cvtdq2pd xmm1, xmm1
0x180059270  mulsd   xmm1, cs:__real@3f847ae147ae147b; percentR
0x180059278  movaps  xmm3, xmm1; percentB
0x18005927b  movaps  xmm2, xmm1; percentG
0x18005927e  mov     ecx, eax; srcPixel
0x180059280  call    ?PixelAlpha@CDrawingManager@@SAKKNNN@Z; CDrawingManager::PixelAlpha(ulong,double,double,double)
0x180059285  or      eax, 0FF000000h
0x18005928a  mov     [rsi], eax
0x18005928c  mov     rax, [rbp+4Fh+pBits]
0x180059290  add     rsi, 4
0x180059294  sub     rax, 1
0x180059298  mov     [rbp+4Fh+pBits], rax
0x18005929c  jnz     short loc_18005923E
0x18005929e  mov     rdi, [rbp+4Fh+var_40]
0x1800592a2  mov     rax, [rbp+4Fh+var_38]
0x1800592a6  mov     rax, [rax+8]
0x1800592aa  mov     this, [rax+8]; hdc
0x1800592ae  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x1800592b6  xor     esi, esi
0x1800592b8  mov     [rsp+0E0h+y1], esi; y1
0x1800592bc  mov     [rsp+0E0h+x1], esi; x1
0x1800592c0  mov     rax, [rbp+4Fh+dcMem.m_hDC]
0x1800592c4  mov     [rsp+0E0h+hdcSrc], rax; hdcSrc
0x1800592c9  mov     [rsp+0E0h+cy], r12d; cy
0x1800592ce  mov     clrTransparent, r15d; cx
0x1800592d1  mov     nPercentage, [rdi+4]; y
0x1800592d5  mov     edx, [rdi]; x
0x1800592d7  call    cs:__imp_BitBlt
0x1800592dd  mov     rect, [rbp+4Fh+var_30]
0x1800592e1  mov     rect, [rect+8]; h
0x1800592e5  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x1800592e9  call    cs:__imp_SelectObject
0x1800592ef  mov     this, rax; h
0x1800592f2  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800592f7  mov     this, [rbp+4Fh+ho]; ho
0x1800592fb  call    cs:__imp_DeleteObject
0x180059301  nop
0x180059302  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059309  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x18005930d  lea     this, [rbp+4Fh+bmpMem]; this
0x180059311  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059316  nop
0x180059317  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005931e  mov     [rbp+4Fh+dcMem.__vftable], rax
0x180059322  cmp     [rbp+4Fh+dcMem.m_hDC], rsi
0x180059326  jz      short loc_18005933B
0x180059328  lea     this, [rbp+4Fh+dcMem]; this
0x18005932c  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180059331  mov     this, rax; hdc
0x180059334  call    cs:__imp_DeleteDC
0x18005933a  nop
0x18005933b  jmp     loc_180058F9F
0x180059340  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059347  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x18005934b  lea     this, [rbp+4Fh+bmpMem]; this
0x18005934f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059354  nop
0x180059355  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005935c  mov     [rbp+4Fh+dcMem.__vftable], rax
0x180059360  cmp     [rbp+4Fh+dcMem.m_hDC], rsi
0x180059364  jz      short loc_180059379
0x180059366  lea     this, [rbp+4Fh+dcMem]; this
0x18005936a  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18005936f  mov     this, rax; hdc
0x180059372  call    cs:__imp_DeleteDC
0x180059378  nop
0x180059379  xor     eax, eax
0x18005937b  jmp     loc_180058FA4
0x180059380  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
