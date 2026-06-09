# CDrawingManager::FillGradient2(CRect,ulong,ulong,int)

- ea: `0x1800599c0`
- end: `0x180059e30`
- name: `?FillGradient2@CDrawingManager@@QEAAXVCRect@@KKH@Z`
- size: `1136`
- prototype: `void __fastcall(CDrawingManager *this, CRect rect, unsigned int colorStart, unsigned int colorFinish, int nAngle)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800cff50`
- `0x180188e40`
- `0x18019c550`

## callees

- `0x18001d090`
- `0x1800596d0`
- `0x1800599c0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af0b0`
- `0x1802af110`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0b50`
- `0x1802c4640`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!abs` at `0x180059b98`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x180059b98`
- `api-ms-win-crt-math-l1-1-0!cos` at `0x180059b79`
- `api-ms-win-crt-math-l1-1-0!cos` at `0x180059b79`
- `USER32!FillRect` at `0x180059a19`
- `USER32!FillRect` at `0x180059a19`
- `GDI32!DeleteDC` at `0x180059b14`
- `GDI32!DeleteDC` at `0x180059da8`
- `GDI32!DeleteDC` at `0x180059b14`
- `GDI32!DeleteDC` at `0x180059da8`
- `GDI32!BitBlt` at `0x180059d54`
- `GDI32!BitBlt` at `0x180059d54`
- `GDI32!CreateCompatibleBitmap` at `0x180059ad3`
- `GDI32!CreateCompatibleBitmap` at `0x180059ad3`
- `GDI32!Polygon` at `0x180059cc3`
- `GDI32!Polygon` at `0x180059cc3`
- `GDI32!SelectObject` at `0x180059b28`
- `GDI32!SelectObject` at `0x180059d66`
- `GDI32!SelectObject` at `0x180059b28`
- `GDI32!SelectObject` at `0x180059d66`
- `GDI32!CreateCompatibleDC` at `0x180059a97`
- `GDI32!CreateCompatibleDC` at `0x180059a97`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CDrawingManager::FillGradient2(
        CDrawingManager *this,
        CRect *rect,
        unsigned int colorStart,
        unsigned int colorFinish,
        int nAngle)
{
  unsigned int v5; // r15d
  unsigned int v6; // esi
  int v9; // r12d
  CDC *m_dc; // rcx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HDC v14; // rax
  HGDIOBJ v15; // rax
  int v16; // ebx
  int v17; // r13d
  int v18; // ebx
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // r10d
  int v23; // r11d
  int v24; // ebx
  int v25; // r15d
  int v26; // r8d
  int v27; // edx
  CFont *v28; // rbx
  HGDIOBJ v29; // rax
  HDC v30; // rax
  int cy; // [rsp+20h] [rbp-C1h]
  CBrush br; // [rsp+50h] [rbp-91h] BYREF
  int v33; // [rsp+60h] [rbp-81h]
  CDC dcMem; // [rsp+68h] [rbp-79h] BYREF
  int v35; // [rsp+88h] [rbp-59h]
  int v36; // [rsp+8Ch] [rbp-55h]
  int v37; // [rsp+90h] [rbp-51h]
  int v38; // [rsp+94h] [rbp-4Dh]
  int v39; // [rsp+98h] [rbp-49h]
  CBitmap bmpMem; // [rsp+A0h] [rbp-41h] BYREF
  CFont *pFont; // [rsp+B0h] [rbp-31h]
  CDrawingManager *v42; // [rsp+B8h] [rbp-29h]
  CGdiObject *v43; // [rsp+C0h] [rbp-21h]
  tagPOINT points[4]; // [rsp+C8h] [rbp-19h] BYREF

  v5 = colorFinish;
  v6 = colorStart;
  v42 = this;
  if ( colorStart == colorFinish )
  {
    CBrush::CBrush(&br, colorStart);
    FillRect(this->m_dc->m_hDC, rect, (HBRUSH)br.m_hObject);
    br.__vftable = (CBrush_vtbl *)CBrush::`vftable';
    CGdiObject::~CGdiObject(&br);
    return;
  }
  v9 = 0;
  switch ( nAngle )
  {
    case 0:
      goto LABEL_31;
    case 90:
      cy = 1;
      goto LABEL_32;
    case 180:
      colorFinish = colorStart;
      colorStart = v5;
      goto LABEL_31;
    case 270:
      cy = 1;
      colorFinish = colorStart;
      colorStart = v5;
LABEL_32:
      br = (CBrush)*rect;
      CDrawingManager::FillGradient(this, (__m128i *)&br, colorStart, colorFinish, cy, 0, 0);
      return;
    case 360:
LABEL_31:
      cy = 0;
      goto LABEL_32;
  }
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  m_dc = this->m_dc;
  if ( m_dc )
    m_hDC = m_dc->m_hDC;
  else
    m_hDC = 0;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( !CDC::Attach(&dcMem, CompatibleDC) )
    goto LABEL_14;
  bmpMem.m_hObject = 0;
  bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CompatibleBitmap = CreateCompatibleBitmap(this->m_dc->m_hDC, rect->right - rect->left, rect->bottom - rect->top);
  if ( !CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
  {
    bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bmpMem);
LABEL_14:
    dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( dcMem.m_hDC )
    {
      v14 = CDC::Detach(&dcMem);
      DeleteDC(v14);
    }
    return;
  }
  v15 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
  v43 = CGdiObject::FromHandle(v15);
  if ( !v43 )
    AfxThrowInvalidArgException();
  pFont = (CFont *)CDC::SelectStockObject(&dcMem, 8);
  v16 = rect->bottom - rect->top;
  v17 = (int)(cos((double)(nAngle + 180) * 3.141592653589793 / 180.0) * (double)v16);
  v18 = rect->right - rect->left;
  v33 = v18 + abs(v17);
  v19 = (unsigned __int8)v6;
  v36 = (unsigned __int8)v6;
  v20 = (unsigned __int8)v5;
  v37 = (unsigned __int8)v5;
  v21 = BYTE1(v5);
  v35 = v21;
  v22 = BYTE2(v6);
  v38 = BYTE2(v6);
  v23 = BYTE2(v5);
  v39 = BYTE2(v5);
  v24 = 0;
  v25 = v33;
  do
  {
    CBrush::CBrush(
      &br,
      (unsigned __int8)(((64 - v9) * v19 + v9 * v20) >> 6)
    | ((unsigned __int8)((v23 * v9 + (64 - v9) * v22) >> 6) << 16)
    | ((unsigned __int8)(((64 - v9) * BYTE1(v6) + v9 * v21) >> 6) << 8));
    v26 = v24 >> 6;
    if ( v17 > 0 )
      v26 = (v24 >> 6) - v17;
    v24 += v25;
    v33 = v24;
    v27 = v24 >> 6;
    if ( v17 > 0 )
      v27 = (v24 >> 6) - v17;
    if ( v26 != v27 )
    {
      points[0].x = v26;
      points[0].y = 0;
      points[1].x = v27;
      points[1].y = 0;
      points[2].x = v27 + v17;
      points[2].y = rect->bottom - rect->top;
      points[3].x = v26 + v17;
      points[3].y = points[2].y;
      v28 = CDC::SelectObject(&dcMem, (CFont *)&br);
      Polygon(dcMem.m_hDC, points, 4);
      CDC::SelectObject(&dcMem, v28);
      v24 = v33;
    }
    br.__vftable = (CBrush_vtbl *)CBrush::`vftable';
    CGdiObject::~CGdiObject(&br);
    ++v9;
    v21 = v35;
    v19 = v36;
    v20 = v37;
    v22 = v38;
    v23 = v39;
  }
  while ( v9 < 64 );
  CDC::SelectObject(&dcMem, pFont);
  BitBlt(
    v42->m_dc->m_hDC,
    rect->left,
    rect->top,
    rect->right - rect->left,
    rect->bottom - rect->top,
    dcMem.m_hDC,
    0,
    0,
    0xCC0020u);
  v29 = SelectObject(dcMem.m_hDC, v43->m_hObject);
  CGdiObject::FromHandle(v29);
  bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmpMem);
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcMem.m_hDC )
  {
    v30 = CDC::Detach(&dcMem);
    DeleteDC(v30);
  }
}

```

## disassembly

```asm
0x1800599c0  push    rbp
0x1800599c2  push    rbx
0x1800599c3  push    rsi
0x1800599c4  push    rdi
0x1800599c5  push    r12
0x1800599c7  push    r13
0x1800599c9  push    r14
0x1800599cb  push    r15
0x1800599cd  lea     rbp, [rsp-17h]
0x1800599d2  sub     rsp, 0F8h
0x1800599d9  mov     rax, cs:__security_cookie
0x1800599e0  xor     rax, rsp
0x1800599e3  mov     [rbp+4Fh+var_48], rax
0x1800599e7  mov     r15d, colorFinish
0x1800599ea  mov     esi, colorStart
0x1800599ed  mov     rdi, rect
0x1800599f0  mov     r14, this
0x1800599f3  mov     [rbp+4Fh+var_78], this
0x1800599f7  cmp     colorStart, colorFinish
0x1800599fa  jnz     short loc_180059A3A
0x1800599fc  mov     edx, colorStart; crColor
0x1800599ff  lea     this, [rsp+130h+br]; this
0x180059a04  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x180059a09  mov     this, [r14+8]
0x180059a0d  mov     r8, [rsp+130h+br.m_hObject]; hbr
0x180059a12  mov     rect, rdi; lprc
0x180059a15  mov     this, [this+8]; hDC
0x180059a19  call    cs:__imp_FillRect
0x180059a1f  lea     rsi, ??_7CBrush@@6B@; const CBrush::`vftable'
0x180059a26  mov     [rsp+130h+br.__vftable], rsi
0x180059a2b  lea     this, [rsp+130h+br]; this
0x180059a30  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059a35  jmp     loc_180059DF6
0x180059a3a  mov     ebx, [rbp+4Fh+arg_20]
0x180059a3d  mov     ecx, ebx
0x180059a3f  xor     r12d, r12d
0x180059a42  test    ebx, ebx
0x180059a44  jz      loc_180059DD1
0x180059a4a  sub     ecx, 5Ah ; 'Z'
0x180059a4d  jz      loc_180059E16
0x180059a53  sub     ecx, 5Ah ; 'Z'
0x180059a56  jz      loc_180059DCB
0x180059a5c  sub     ecx, 5Ah ; 'Z'
0x180059a5f  jz      loc_180059DB1
0x180059a65  cmp     ecx, 5Ah ; 'Z'
0x180059a68  jz      loc_180059DD1
0x180059a6e  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x180059a75  mov     [rbp+4Fh+dcMem.__vftable], r13
0x180059a79  xorps   xmm0, xmm0
0x180059a7c  movdqu  xmmword ptr [rbp+4Fh+dcMem.m_hDC], xmm0
0x180059a81  mov     [rbp+4Fh+dcMem.m_bPrinting], r12d
0x180059a85  mov     this, [r14+8]
0x180059a89  test    this, this
0x180059a8c  jnz     short loc_180059A93
0x180059a8e  mov     ecx, r12d
0x180059a91  jmp     short loc_180059A97
0x180059a93  mov     this, [this+8]; hdc
0x180059a97  call    cs:__imp_CreateCompatibleDC
0x180059a9d  mov     rect, rax; hDC
0x180059aa0  lea     this, [rbp+4Fh+dcMem]; this
0x180059aa4  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180059aa9  test    eax, eax
0x180059aab  jnz     short loc_180059AAF
0x180059aad  jmp     short loc_180059AFE
0x180059aaf  mov     [rbp+4Fh+bmpMem.m_hObject], r12
0x180059ab3  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059aba  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x180059abe  mov     colorStart, [rdi+0Ch]
0x180059ac2  sub     colorStart, [rdi+4]; cy
0x180059ac6  mov     edx, [rdi+8]
0x180059ac9  sub     edx, [rdi]; cx
0x180059acb  mov     this, [r14+8]
0x180059acf  mov     this, [this+8]; hdc
0x180059ad3  call    cs:__imp_CreateCompatibleBitmap
0x180059ad9  mov     rect, rax; hObject
0x180059adc  lea     this, [rbp+4Fh+bmpMem]; this
0x180059ae0  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180059ae5  test    eax, eax
0x180059ae7  jnz     short loc_180059B20
0x180059ae9  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059af0  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x180059af4  lea     this, [rbp+4Fh+bmpMem]; this
0x180059af8  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059afd  nop
0x180059afe  cmp     [rbp+4Fh+dcMem.m_hDC], r12
0x180059b02  mov     [rbp+4Fh+dcMem.__vftable], r13
0x180059b06  jz      short loc_180059B1B
0x180059b08  lea     this, [rbp+4Fh+dcMem]; this
0x180059b0c  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180059b11  mov     this, rax; hdc
0x180059b14  call    cs:__imp_DeleteDC
0x180059b1a  nop
0x180059b1b  jmp     loc_180059DF6
0x180059b20  mov     rect, [rbp+4Fh+bmpMem.m_hObject]; h
0x180059b24  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x180059b28  call    cs:__imp_SelectObject
0x180059b2e  mov     this, rax; h
0x180059b31  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180059b36  mov     [rbp+4Fh+var_70], rax
0x180059b3a  test    rax, rax
0x180059b3d  jz      loc_180059E2A
0x180059b43  mov     edx, 8; nIndex
0x180059b48  lea     this, [rbp+4Fh+dcMem]; this
0x180059b4c  call    ?SelectStockObject@CDC@@UEAAPEAVCGdiObject@@H@Z; CDC::SelectStockObject(int)
0x180059b51  mov     [rbp+4Fh+pFont], rax
0x180059b55  lea     ecx, [rbx+0B4h]
0x180059b5b  movd    xmm0, ecx
0x180059b5f  cvtdq2pd xmm0, xmm0
0x180059b63  mulsd   xmm0, cs:__real@400921fb54442d18
0x180059b6b  divsd   xmm0, cs:__real@4066800000000000; X
0x180059b73  mov     ebx, [rdi+0Ch]
0x180059b76  sub     ebx, [rdi+4]
0x180059b79  call    cs:__imp_cos
0x180059b7f  movd    xmm1, ebx
0x180059b83  cvtdq2pd xmm1, xmm1
0x180059b87  mulsd   xmm0, xmm1
0x180059b8b  cvttsd2si r13d, xmm0
0x180059b90  mov     ebx, [rdi+8]
0x180059b93  sub     ebx, [rdi]
0x180059b95  mov     ecx, r13d; Number
0x180059b98  call    cs:__imp_abs
0x180059b9e  add     eax, ebx
0x180059ba0  mov     [rsp+130h+var_D0], eax
0x180059ba4  movzx   eax, sil
0x180059ba8  mov     [rbp+4Fh+var_A4], eax
0x180059bab  movzx   edx, r15b
0x180059baf  mov     [rbp+4Fh+var_A0], edx
0x180059bb2  movzx   r14d, si
0x180059bb6  shr     r14d, 8
0x180059bba  movzx   ecx, r15w
0x180059bbe  shr     ecx, 8
0x180059bc1  mov     [rbp+4Fh+var_A8], ecx
0x180059bc4  shr     esi, 10h
0x180059bc7  movzx   r10d, sil
0x180059bcb  mov     [rbp+4Fh+var_9C], r10d
0x180059bcf  shr     r15d, 10h
0x180059bd3  movzx   r11d, r15b
0x180059bd7  mov     [rbp+4Fh+var_98], r11d
0x180059bdb  xor     ebx, ebx
0x180059bdd  lea     rsi, ??_7CBrush@@6B@; const CBrush::`vftable'
0x180059be4  mov     r15d, [rsp+130h+var_D0]
0x180059be9  mov     colorStart, 40h ; '@'
0x180059bef  sub     colorStart, r12d
0x180059bf2  mov     colorFinish, edx
0x180059bf5  imul    colorFinish, r12d
0x180059bf9  imul    eax, colorStart
0x180059bfd  add     colorFinish, eax
0x180059c00  sar     colorFinish, 6
0x180059c04  mov     edx, ecx
0x180059c06  imul    edx, r12d
0x180059c0a  mov     eax, r14d
0x180059c0d  imul    eax, colorStart
0x180059c11  add     edx, eax
0x180059c13  sar     edx, 6
0x180059c16  mov     ecx, r10d
0x180059c19  imul    ecx, colorStart
0x180059c1d  mov     eax, r12d
0x180059c20  imul    eax, r11d
0x180059c24  add     ecx, eax
0x180059c26  sar     ecx, 6
0x180059c29  movzx   edx, dl
0x180059c2c  shl     edx, 8
0x180059c2f  movzx   eax, cl
0x180059c32  shl     eax, 10h
0x180059c35  or      edx, eax
0x180059c37  movzx   eax, r9b
0x180059c3b  or      edx, eax; crColor
0x180059c3d  lea     this, [rsp+130h+br]; this
0x180059c42  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x180059c47  nop
0x180059c48  mov     colorStart, ebx
0x180059c4b  sar     colorStart, 6
0x180059c4f  mov     eax, colorStart
0x180059c52  sub     eax, r13d
0x180059c55  test    r13d, r13d
0x180059c58  cmovg   colorStart, eax
0x180059c5c  lea     edx, [rbx+r15]
0x180059c60  mov     ebx, edx
0x180059c62  mov     [rsp+130h+var_D0], edx
0x180059c66  sar     edx, 6
0x180059c69  mov     eax, edx
0x180059c6b  sub     eax, r13d
0x180059c6e  test    r13d, r13d
0x180059c71  cmovg   edx, eax
0x180059c74  cmp     colorStart, edx
0x180059c77  jnz     short loc_180059C7B
0x180059c79  jmp     short loc_180059CDA
0x180059c7b  lea     ecx, [r8+r13]
0x180059c7f  lea     eax, [rect+r13]
0x180059c83  mov     [rbp+4Fh+points.x], colorStart
0x180059c87  and     [rbp+4Fh+points.y], 0
0x180059c8b  mov     [rbp+4Fh+points.x+8], edx
0x180059c8e  and     [rbp+4Fh+points.y+8], 0
0x180059c92  mov     [rbp+4Fh+points.x+10h], eax
0x180059c95  mov     eax, [rdi+0Ch]
0x180059c98  sub     eax, [rdi+4]
0x180059c9b  mov     [rbp+4Fh+points.y+10h], eax
0x180059c9e  mov     [rbp+4Fh+points.x+18h], ecx
0x180059ca1  mov     [rbp+4Fh+points.y+18h], eax
0x180059ca4  lea     rect, [rsp+130h+br]; pFont
0x180059ca9  lea     this, [rbp+4Fh+dcMem]; this
0x180059cad  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x180059cb2  mov     rbx, rax
0x180059cb5  mov     colorStart, 4; cpt
0x180059cbb  lea     rect, [rbp+4Fh+points]; apt
0x180059cbf  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x180059cc3  call    cs:__imp_Polygon
0x180059cc9  mov     rect, rbx; pFont
0x180059ccc  lea     this, [rbp+4Fh+dcMem]; this
0x180059cd0  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x180059cd5  nop
0x180059cd6  mov     ebx, [rsp+130h+var_D0]
0x180059cda  mov     [rsp+130h+br.__vftable], rsi
0x180059cdf  lea     this, [rsp+130h+br]; this
0x180059ce4  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059ce9  inc     r12d
0x180059cec  cmp     r12d, 40h ; '@'
0x180059cf0  mov     ecx, [rbp+4Fh+var_A8]
0x180059cf3  mov     eax, [rbp+4Fh+var_A4]
0x180059cf6  mov     edx, [rbp+4Fh+var_A0]
0x180059cf9  mov     r10d, [rbp+4Fh+var_9C]
0x180059cfd  mov     r11d, [rbp+4Fh+var_98]
0x180059d01  jl      loc_180059BE9
0x180059d07  mov     rect, [rbp+4Fh+pFont]; pFont
0x180059d0b  lea     this, [rbp+4Fh+dcMem]; this
0x180059d0f  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x180059d14  mov     r14, [rbp+4Fh+var_78]
0x180059d18  mov     this, [r14+8]
0x180059d1c  mov     colorStart, [rdi+4]; y
0x180059d20  mov     r10d, [rdi+0Ch]
0x180059d24  sub     r10d, colorStart
0x180059d27  mov     colorFinish, [rdi+8]
0x180059d2b  sub     colorFinish, [rdi]; cx
0x180059d2e  mov     [rsp+130h+rop], 0CC0020h; rop
0x180059d36  and     [rsp+130h+var_F8], 0
0x180059d3b  and     [rsp+130h+var_100], 0
0x180059d40  mov     rax, [rbp+4Fh+dcMem.m_hDC]
0x180059d44  mov     [rsp+130h+hdcSrc], rax; hdcSrc
0x180059d49  mov     [rsp+130h+cy], r10d; cy
0x180059d4e  mov     edx, [rdi]; x
0x180059d50  mov     this, [this+8]; hdc
0x180059d54  call    cs:__imp_BitBlt
0x180059d5a  mov     r13, [rbp+4Fh+var_70]
0x180059d5e  mov     rect, [r13+8]; h
0x180059d62  mov     this, [rbp+4Fh+dcMem.m_hDC]; hdc
0x180059d66  call    cs:__imp_SelectObject
0x180059d6c  mov     this, rax; h
0x180059d6f  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180059d74  nop
0x180059d75  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180059d7c  mov     [rbp+4Fh+bmpMem.__vftable], rax
0x180059d80  lea     this, [rbp+4Fh+bmpMem]; this
0x180059d84  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180059d89  nop
0x180059d8a  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180059d91  mov     [rbp+4Fh+dcMem.__vftable], rax
0x180059d95  cmp     [rbp+4Fh+dcMem.m_hDC], 0
0x180059d9a  jz      short loc_180059DAF
0x180059d9c  lea     this, [rbp+4Fh+dcMem]; this
0x180059da0  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180059da5  mov     this, rax; hdc
0x180059da8  call    cs:__imp_DeleteDC
0x180059dae  nop
0x180059daf  jmp     short loc_180059DF6
0x180059db1  mov     [rsp+130h+var_100], r12d
0x180059db6  mov     dword ptr [rsp+130h+hdcSrc], r12d
0x180059dbb  mov     [rsp+130h+cy], 1
0x180059dc3  mov     colorFinish, esi
0x180059dc6  mov     colorStart, r15d
0x180059dc9  jmp     short loc_180059DE0
0x180059dcb  mov     colorFinish, esi
0x180059dce  mov     colorStart, r15d
0x180059dd1  mov     [rsp+130h+var_100], r12d
0x180059dd6  mov     dword ptr [rsp+130h+hdcSrc], r12d
0x180059ddb  mov     [rsp+130h+cy], r12d
0x180059de0  movups  xmm0, xmmword ptr [rect]
0x180059de3  movdqu  xmmword ptr [rsp+130h+br.__vftable], xmm0
0x180059de9  lea     rect, [rsp+130h+br]
0x180059dee  mov     this, r14
0x180059df1  call    ?FillGradient@CDrawingManager@@QEAAXVCRect@@KKHHH@Z; CDrawingManager::FillGradient(CRect,ulong,ulong,int,int,int)
0x180059df6  mov     this, [rbp+4Fh+var_48]
0x180059dfa  xor     this, rsp; StackCookie
0x180059dfd  call    __security_check_cookie
0x180059e02  add     rsp, 0F8h
0x180059e09  pop     r15
0x180059e0b  pop     r14
0x180059e0d  pop     r13
0x180059e0f  pop     r12
0x180059e11  pop     rdi
0x180059e12  pop     rsi
0x180059e13  pop     rbx
0x180059e14  pop     rbp
0x180059e15  retn
0x180059e16  mov     [rsp+130h+var_100], r12d
0x180059e1b  mov     dword ptr [rsp+130h+hdcSrc], r12d
0x180059e20  mov     [rsp+130h+cy], 1
0x180059e28  jmp     short loc_180059DE0
0x180059e2a  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
