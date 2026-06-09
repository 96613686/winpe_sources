# CDrawingManager::DrawGradientRing(CRect,ulong,ulong,ulong,int,int,ulong)

- ea: `0x18005a0d0`
- end: `0x18005a9fa`
- name: `?DrawGradientRing@CDrawingManager@@QEAAHVCRect@@KKKHHK@Z`
- size: `2346`
- prototype: `int __fastcall(CDrawingManager *this, CRect rect, unsigned int colorStart, unsigned int colorFinish, unsigned int colorBorder, int nAngle, int nWidth, unsigned int clrFace)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18019b160`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005a0d0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af0b0`
- `0x1802af110`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0b50`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!cos` at `0x18005a68c`
- `api-ms-win-crt-math-l1-1-0!cos` at `0x18005a68c`
- `api-ms-win-crt-math-l1-1-0!sin` at `0x18005a6a6`
- `api-ms-win-crt-math-l1-1-0!sin` at `0x18005a6a6`
- `USER32!InflateRect` at `0x18005a89d`
- `USER32!InflateRect` at `0x18005a89d`
- `USER32!OffsetRect` at `0x18005a2a9`
- `USER32!OffsetRect` at `0x18005a2a9`
- `GDI32!DeleteDC` at `0x18005a96a`
- `GDI32!DeleteDC` at `0x18005a9ad`
- `GDI32!DeleteDC` at `0x18005a96a`
- `GDI32!DeleteDC` at `0x18005a9ad`
- `GDI32!Ellipse` at `0x18005a473`
- `GDI32!Ellipse` at `0x18005a495`
- `GDI32!Ellipse` at `0x18005a4b7`
- `GDI32!Ellipse` at `0x18005a4eb`
- `GDI32!Ellipse` at `0x18005a50c`
- `GDI32!Ellipse` at `0x18005a473`
- `GDI32!Ellipse` at `0x18005a495`
- `GDI32!Ellipse` at `0x18005a4b7`
- `GDI32!Ellipse` at `0x18005a4eb`
- `GDI32!Ellipse` at `0x18005a50c`
- `GDI32!BitBlt` at `0x18005a294`
- `GDI32!BitBlt` at `0x18005a908`
- `GDI32!BitBlt` at `0x18005a294`
- `GDI32!BitBlt` at `0x18005a908`
- `GDI32!CreateCompatibleBitmap` at `0x18005a1c9`
- `GDI32!CreateCompatibleBitmap` at `0x18005a1c9`
- `GDI32!Rectangle` at `0x18005a537`
- `GDI32!Rectangle` at `0x18005a537`
- `GDI32!DeleteObject` at `0x18005a92d`
- `GDI32!DeleteObject` at `0x18005a92d`
- `GDI32!SelectObject` at `0x18005a202`
- `GDI32!SelectObject` at `0x18005a251`
- `GDI32!SelectObject` at `0x18005a91b`
- `GDI32!SelectObject` at `0x18005a202`
- `GDI32!SelectObject` at `0x18005a251`
- `GDI32!SelectObject` at `0x18005a91b`
- `GDI32!CreateCompatibleDC` at `0x18005a190`
- `GDI32!CreateCompatibleDC` at `0x18005a190`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDrawingManager::DrawGradientRing(
        CDrawingManager *this,
        CRect *rect,
        unsigned int colorStart,
        unsigned int colorFinish,
        int colorBorder,
        int nAngle,
        int nWidth,
        unsigned int clrFace)
{
  CRect *v10; // rbx
  CDrawingManager *v11; // r13
  int v12; // r15d
  int cy; // r12d
  CDC *m_dc; // rcx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v18; // rax
  CBrush_vtbl *v19; // rax
  CDC *v20; // rcx
  HDC hdcSrc; // rax
  double v22; // xmm13_8
  double v23; // xmm1_8
  double v24; // xmm4_8
  double v25; // xmm5_8
  double v26; // xmm3_8
  int v27; // r8d
  double v28; // xmm10_8
  int v29; // r9d
  int top; // r13d
  int v31; // eax
  int v32; // eax
  int v33; // r13d
  CFont *v34; // rsi
  CFont *v35; // r14
  int v36; // r8d
  int left; // edx
  int bottom; // edi
  int v39; // r8d
  int v40; // eax
  int right; // r9d
  int v42; // edx
  int v43; // eax
  int v44; // edi
  double v45; // xmm8_8
  double v46; // xmm7_8
  double v47; // xmm11_8
  double v48; // xmm13_8
  int v49; // ebx
  int v50; // eax
  double v51; // xmm1_8
  double v52; // xmm2_8
  int v53; // edx
  double v54; // xmm2_8
  double v55; // xmm0_8
  int v56; // r14d
  double v57; // xmm0_8
  int v58; // esi
  double v59; // xmm0_8
  int v60; // r9d
  double v61; // xmm0_8
  double v62; // xmm0_8
  int v63; // eax
  int *v64; // rdi
  __int64 i; // rcx
  double v66; // xmm0_8
  double v67; // xmm0_8
  int v68; // r8d
  int *v69; // rcx
  __int64 v70; // rax
  HGDIOBJ v71; // rax
  HDC v72; // rax
  HDC v74; // rax
  int v75; // [rsp+58h] [rbp-B0h]
  int v76; // [rsp+5Ch] [rbp-ACh]
  CDC dcMem; // [rsp+60h] [rbp-A8h] BYREF
  int v78; // [rsp+80h] [rbp-88h]
  CSize size; // [rsp+88h] [rbp-80h] BYREF
  int v80; // [rsp+90h] [rbp-78h]
  int y; // [rsp+94h] [rbp-74h]
  unsigned int *pBits; // [rsp+98h] [rbp-70h]
  CBitmap bmpMem; // [rsp+A0h] [rbp-68h] BYREF
  HGDIOBJ h; // [rsp+B0h] [rbp-58h]
  unsigned int crColor; // [rsp+B8h] [rbp-50h]
  int v86; // [rsp+BCh] [rbp-4Ch]
  double v87; // [rsp+C0h] [rbp-48h]
  double v88; // [rsp+C8h] [rbp-40h]
  double v89; // [rsp+D0h] [rbp-38h]
  double v90; // [rsp+D8h] [rbp-30h]
  double v91; // [rsp+E0h] [rbp-28h]
  double v92; // [rsp+E8h] [rbp-20h]
  double v93; // [rsp+F0h] [rbp-18h]
  CRect *v94; // [rsp+F8h] [rbp-10h]
  CDrawingManager *v95; // [rsp+100h] [rbp-8h]
  CGdiObject *v96; // [rsp+108h] [rbp+0h]
  CBrush brFill; // [rsp+110h] [rbp+8h] BYREF

  v10 = rect;
  v94 = rect;
  v11 = this;
  v95 = this;
  crColor = clrFace;
  LODWORD(pBits) = rect->left;
  v12 = rect->right - (_DWORD)pBits;
  y = rect->top;
  cy = rect->bottom - y;
  if ( v12 <= 4 || cy <= 4 )
    return 0;
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMem.m_hAttribDC = 0;
  v78 = 0;
  m_dc = this->m_dc;
  if ( m_dc )
    m_hDC = m_dc->m_hDC;
  else
    m_hDC = 0;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( !CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
  {
LABEL_77:
    dcMem.m_hDC = (HDC__ *)CDC::`vftable';
    if ( dcMem.m_hAttribDC )
    {
      v74 = CDC::Detach((CDC *)&dcMem.m_hDC);
      DeleteDC(v74);
    }
    return 0;
  }
  h = 0;
  bmpMem.m_hObject = (void *)CBitmap::`vftable';
  CompatibleBitmap = CreateCompatibleBitmap(v11->m_dc->m_hDC, v12, cy);
  if ( !CGdiObject::Attach((CGdiObject *)&bmpMem.m_hObject, CompatibleBitmap) )
    goto LABEL_76;
  v18 = SelectObject(dcMem.m_hAttribDC, h);
  v96 = CGdiObject::FromHandle(v18);
  if ( !v96 )
    AfxThrowInvalidArgException();
  size.cx = v12;
  size.cy = cy;
  v19 = (CBrush_vtbl *)CDrawingManager::CreateBitmap_32(&size, (void **)&bmpMem.__vftable);
  brFill.__vftable = v19;
  if ( !v19 || !bmpMem.__vftable )
  {
LABEL_76:
    bmpMem.m_hObject = (void *)CBitmap::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
    goto LABEL_77;
  }
  SelectObject(dcMem.m_hAttribDC, v19);
  v20 = v11->m_dc;
  if ( v20 )
    hdcSrc = v20->m_hDC;
  else
    hdcSrc = 0;
  BitBlt(dcMem.m_hAttribDC, 0, 0, v12, cy, hdcSrc, v10->left, v10->top, 0xCC0020u);
  OffsetRect(v10, -(int)pBits, -y);
  v80 = (v10->right + v10->left) / 2;
  v86 = (v10->bottom + v10->top) / 2;
  v22 = (double)nAngle * 3.141592653589793 / 180.0;
  v93 = v22;
  v23 = v22 + 6.283185307179586;
  v89 = v22 + 6.283185307179586;
  v91 = (double)(unsigned __int8)colorStart;
  v24 = ((double)(unsigned __int8)colorFinish + 0.5 - v91) / 360.0
      + ((double)(unsigned __int8)colorFinish + 0.5 - v91) / 360.0;
  v88 = v24;
  v25 = (double)BYTE1(colorStart);
  *(double *)&size = v25;
  v90 = ((double)BYTE1(colorFinish) + 0.5 - v25) / 360.0 + ((double)BYTE1(colorFinish) + 0.5 - v25) / 360.0;
  v92 = (double)BYTE2(colorStart);
  v26 = ((double)BYTE2(colorFinish) + 0.5 - v92) / 360.0 + ((double)BYTE2(colorFinish) + 0.5 - v92) / 360.0;
  v87 = v26;
  v27 = 0;
  v75 = 0;
  if ( nWidth > 0 )
  {
    v28 = v23 + 0.0174532925199433;
    do
    {
      v29 = 0;
      v76 = 0;
      top = v10->top;
      v31 = v10->right - v10->left;
      if ( v31 >= v10->bottom - top )
        v31 = v10->bottom - top;
      v32 = v31 / 2;
      LODWORD(dcMem.__vftable) = v32;
      v33 = v10->right + top - v10->bottom - v10->left;
      if ( crColor != -1 && !v27 )
      {
        CBrush::CBrush((CBrush *)&brFill.m_hObject, crColor);
        v34 = CDC::SelectObject((CDC *)&dcMem.m_hDC, (CFont *)&brFill.m_hObject);
        v35 = (CFont *)CDC::SelectStockObject((CDC *)&dcMem.m_hDC, 8);
        v36 = v10->top;
        left = v10->left;
        if ( v33 )
        {
          if ( v33 <= 0 )
          {
            Ellipse(dcMem.m_hAttribDC, left, v36, v10->right, v10->right + v36 - v10->left);
            Ellipse(dcMem.m_hAttribDC, v10->left, v10->left + v10->bottom - v10->right, v10->right, v10->bottom);
            right = v10->right;
            v43 = (right - v10->left) / 2;
            bottom = v10->bottom - v43;
            v39 = v43 + v10->top;
            v42 = v10->left;
          }
          else
          {
            Ellipse(dcMem.m_hAttribDC, left, v36, v10->left + v10->bottom - v36, v10->bottom);
            Ellipse(dcMem.m_hAttribDC, v10->top + v10->right - v10->bottom, v10->top, v10->right, v10->bottom);
            bottom = v10->bottom;
            v39 = v10->top;
            v40 = (bottom - v39) / 2;
            right = v10->right - v40;
            v42 = v40 + v10->left;
          }
          Rectangle(dcMem.m_hAttribDC, v42, v39, right, bottom);
        }
        else
        {
          Ellipse(dcMem.m_hAttribDC, left, v36, v10->right, v10->bottom);
        }
        CDC::SelectObject((CDC *)&dcMem.m_hDC, v34);
        CDC::SelectObject((CDC *)&dcMem.m_hDC, v35);
        brFill.m_hObject = (void *)CBrush::`vftable';
        CGdiObject::~CGdiObject((CGdiObject *)&brFill.m_hObject);
        v23 = v89;
        v26 = v87;
        v24 = v88;
        v25 = *(double *)&size;
        v32 = (int)dcMem.__vftable;
        v27 = v75;
        v29 = 0;
      }
      v44 = -1;
      v45 = v22;
      if ( v28 > v22 )
      {
        v46 = (v23 + v22) * 0.5;
        v47 = (double)v32;
        v48 = v90;
        v49 = -1;
        do
        {
          v50 = 360 - v29;
          if ( v46 >= v45 )
            v50 = v29;
          v51 = (double)v50;
          v52 = fmin(255.0, (double)v50 * v24 + 0.5 + v91);
          if ( v52 < 0.0 )
            v52 = 0.0;
          v53 = (int)v52;
          v54 = fmin(255.0, v51 * v48 + 0.5 + v25);
          if ( v54 < 0.0 )
            v54 = 0.0;
          v55 = fmin(255.0, v51 * v26 + 0.5 + v92);
          if ( v55 < 0.0 )
            v55 = 0.0;
          if ( v27 || colorBorder == -1 )
            v56 = (unsigned __int8)v53 | ((unsigned __int8)(int)v55 << 16) | ((unsigned __int8)(int)v54 << 8);
          else
            v56 = colorBorder;
          v57 = cos(v45);
          v58 = v80 + (int)(v57 * v47 + 0.0);
          v59 = sin(v45);
          v60 = v86 + (int)(v59 * v47 + 0.0);
          if ( v33 <= 0 )
          {
            if ( v33 < 0 )
            {
              v66 = (double)v33;
              v67 = v60 <= v86 ? v66 * 0.5 : v66 * -0.5;
              v60 += (int)v67;
              if ( v44 != -1 && v44 > v86 != v60 > v86 )
              {
                v68 = v44;
                if ( v60 < v44 )
                  v68 = v60;
                if ( v60 > v44 )
                  v44 = v60;
                if ( v68 < v44 )
                {
                  v69 = (int *)((char *)bmpMem.__vftable + 4 * v58 + 4 * (__int64)(v12 * (cy - v68)));
                  v70 = (unsigned int)(v44 - v68);
                  do
                  {
                    *v69 = ((unsigned __int8)v56 << 16) | BYTE2(v56) | v56 & 0xFF00;
                    v69 -= v12;
                    --v70;
                  }
                  while ( v70 );
                }
              }
            }
          }
          else
          {
            v61 = (double)v33;
            if ( v58 <= v80 )
              v62 = v61 * -0.5;
            else
              v62 = v61 * 0.5;
            v58 += (int)v62;
            if ( v49 != -1 && v49 > v80 != v58 > v80 )
            {
              v63 = v49;
              if ( v58 > v49 )
                v63 = v58;
              if ( v58 < v49 )
                v49 = v58;
              if ( v49 < (__int64)v63 )
              {
                v64 = (int *)((char *)bmpMem.__vftable + 4 * v49 + 4 * (__int64)(v12 * (cy - v60)));
                for ( i = v63 - (__int64)v49; i; --i )
                  *v64++ = BYTE2(v56) | v56 & 0xFF00 | ((unsigned __int8)v56 << 16);
              }
            }
          }
          *((_DWORD *)&bmpMem.GetRuntimeClass + v58 + (__int64)(v12 * (cy - v60))) = ((unsigned __int8)v56 << 16)
                                                                                   | BYTE2(v56)
                                                                                   | v56 & 0xFF00;
          v49 = v58;
          v44 = v60;
          v45 = v45 + 0.0174532925199433;
          v29 = ++v76;
          v26 = v87;
          v24 = v88;
          v25 = *(double *)&size;
          v27 = v75;
        }
        while ( v28 > v45 );
        v22 = v93;
        v10 = v94;
      }
      InflateRect(v10, -1, -1);
      v27 = v75 + 1;
      v75 = v27;
      v23 = v89;
      v26 = v87;
      v24 = v88;
      v25 = *(double *)&size;
    }
    while ( v27 < nWidth );
    v11 = v95;
  }
  BitBlt(v11->m_dc->m_hDC, (int)pBits, y, v12, cy, dcMem.m_hAttribDC, 0, 0, 0xCC0020u);
  v71 = SelectObject(dcMem.m_hAttribDC, v96->m_hObject);
  CGdiObject::FromHandle(v71);
  DeleteObject(brFill.__vftable);
  bmpMem.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dcMem.m_hAttribDC )
  {
    v72 = CDC::Detach((CDC *)&dcMem.m_hDC);
    DeleteDC(v72);
  }
  return 1;
}

```

## disassembly

```asm
0x18005a0d0  mov     rax, rsp
0x18005a0d3  mov     [rax+18h], rbx
0x18005a0d7  push    rbp
0x18005a0d8  push    rsi
0x18005a0d9  push    rdi
0x18005a0da  push    r12
0x18005a0dc  push    r13
0x18005a0de  push    r14
0x18005a0e0  push    r15
0x18005a0e2  lea     rbp, [rax-0C8h]
0x18005a0e9  sub     rsp, 190h
0x18005a0f0  movaps  xmmword ptr [rax-48h], xmm6
0x18005a0f4  movaps  xmmword ptr [rax-58h], xmm7
0x18005a0f8  movaps  xmmword ptr [rax-68h], xmm8
0x18005a0fd  movaps  xmmword ptr [rax-78h], xmm9
0x18005a102  movaps  xmmword ptr [rax-88h], xmm10
0x18005a10a  movaps  xmmword ptr [rax-98h], xmm11
0x18005a112  movaps  xmmword ptr [rax-0A8h], xmm13
0x18005a11a  mov     esi, colorFinish
0x18005a11d  mov     r14d, colorStart
0x18005a120  mov     rbx, rect
0x18005a123  mov     [rbp+0C0h+var_D0], rect
0x18005a127  mov     r13, this
0x18005a12a  mov     [rbp+0C0h+var_C8], this
0x18005a12e  mov     eax, [rbp+0C0h+arg_38]
0x18005a134  mov     [rbp+0C0h+crColor], eax
0x18005a137  mov     eax, [rect]
0x18005a139  mov     dword ptr [rbp+0C0h+pBits], eax
0x18005a13c  mov     r15d, [rect+8]
0x18005a140  sub     r15d, eax
0x18005a143  mov     eax, [rect+4]
0x18005a146  mov     [rbp+0C0h+y], eax
0x18005a149  mov     r12d, [rect+0Ch]
0x18005a14d  sub     r12d, eax
0x18005a150  cmp     r15d, 4
0x18005a154  jle     loc_18005A9B4
0x18005a15a  cmp     r12d, 4
0x18005a15e  jle     loc_18005A9B4
0x18005a164  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005a16b  mov     [rsp+1C0h+dcMem.m_hDC], rax
0x18005a170  xorps   xmm0, xmm0
0x18005a173  movdqu  xmmword ptr [rsp+1C0h+dcMem.m_hAttribDC], xmm0
0x18005a179  xor     edi, edi
0x18005a17b  mov     [rsp+1C0h+var_148], edi
0x18005a17f  mov     this, [this+8]
0x18005a183  test    this, this
0x18005a186  jnz     short loc_18005A18C
0x18005a188  mov     ecx, edi
0x18005a18a  jmp     short loc_18005A190
0x18005a18c  mov     this, [this+8]; hdc
0x18005a190  call    cs:__imp_CreateCompatibleDC
0x18005a196  mov     rect, rax; hDC
0x18005a199  lea     this, [rsp+1C0h+dcMem.m_hDC]; this
0x18005a19e  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005a1a3  test    eax, eax
0x18005a1a5  jnz     short loc_18005A1AC
0x18005a1a7  jmp     loc_18005A98D
0x18005a1ac  mov     [rbp+0C0h+h], rdi
0x18005a1b0  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005a1b7  mov     [rbp+0C0h+bmpMem.m_hObject], rax
0x18005a1bb  mov     this, [r13+8]
0x18005a1bf  mov     colorStart, r12d; cy
0x18005a1c2  mov     edx, r15d; cx
0x18005a1c5  mov     this, [this+8]; hdc
0x18005a1c9  call    cs:__imp_CreateCompatibleBitmap
0x18005a1cf  mov     rect, rax; hObject
0x18005a1d2  lea     this, [rbp+0C0h+bmpMem.m_hObject]; this
0x18005a1d6  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005a1db  test    eax, eax
0x18005a1dd  jnz     short loc_18005A1F9
0x18005a1df  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005a1e6  mov     [rbp+0C0h+bmpMem.m_hObject], rax
0x18005a1ea  lea     this, [rbp+0C0h+bmpMem.m_hObject]; this
0x18005a1ee  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005a1f3  nop
0x18005a1f4  jmp     loc_18005A98D
0x18005a1f9  mov     rect, [rbp+0C0h+h]; h
0x18005a1fd  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a202  call    cs:__imp_SelectObject
0x18005a208  mov     this, rax; h
0x18005a20b  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005a210  mov     [rbp+0C0h+var_C0], rax
0x18005a214  test    rax, rax
0x18005a217  jz      loc_18005A9F4
0x18005a21d  mov     [rbp+0C0h+size.cx], r15d
0x18005a221  mov     [rbp+0C0h+size.cy], r12d
0x18005a225  lea     rect, [rbp+0C0h+bmpMem]; pBits
0x18005a229  lea     this, [rbp+0C0h+size]; size
0x18005a22d  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005a232  mov     [rbp+0C0h+brFill.__vftable], rax
0x18005a236  test    rax, rax
0x18005a239  jz      loc_18005A978
0x18005a23f  cmp     [rbp+0C0h+bmpMem.__vftable], rdi
0x18005a243  jz      loc_18005A978
0x18005a249  mov     rect, rax; h
0x18005a24c  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a251  call    cs:__imp_SelectObject
0x18005a257  mov     edx, [rbx+4]
0x18005a25a  mov     edi, [rbx]
0x18005a25c  mov     this, [r13+8]
0x18005a260  test    this, this
0x18005a263  jnz     short loc_18005A269
0x18005a265  xor     eax, eax
0x18005a267  jmp     short loc_18005A26D
0x18005a269  mov     rax, [this+8]
0x18005a26d  mov     [rsp+1C0h+rop], 0CC0020h; rop
0x18005a275  mov     [rsp+1C0h+y1], edx; y1
0x18005a279  mov     [rsp+1C0h+x1], edi; x1
0x18005a27d  mov     [rsp+1C0h+hdcSrc], rax; hdcSrc
0x18005a282  mov     [rsp+1C0h+cy], r12d; cy
0x18005a287  mov     colorFinish, r15d; cx
0x18005a28a  xor     colorStart, colorStart; y
0x18005a28d  xor     edx, edx; x
0x18005a28f  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a294  call    cs:__imp_BitBlt
0x18005a29a  mov     colorStart, [rbp+0C0h+y]
0x18005a29e  neg     colorStart; dy
0x18005a2a1  mov     edx, dword ptr [rbp+0C0h+pBits]
0x18005a2a4  neg     edx; dx
0x18005a2a6  mov     this, rbx; lprc
0x18005a2a9  call    cs:__imp_OffsetRect
0x18005a2af  mov     eax, [rbx]
0x18005a2b1  add     eax, [rbx+8]
0x18005a2b4  cdq
0x18005a2b5  sub     eax, edx
0x18005a2b7  sar     eax, 1
0x18005a2b9  mov     [rbp+0C0h+var_138], eax
0x18005a2bc  mov     eax, [rbx+4]
0x18005a2bf  add     eax, [rbx+0Ch]
0x18005a2c2  cdq
0x18005a2c3  sub     eax, edx
0x18005a2c5  sar     eax, 1
0x18005a2c7  mov     [rbp+0C0h+var_10C], eax
0x18005a2ca  movd    xmm13, [rbp+0C0h+arg_28]
0x18005a2d3  cvtdq2pd xmm13, xmm13
0x18005a2d8  mulsd   xmm13, cs:__real@400921fb54442d18
0x18005a2e1  divsd   xmm13, cs:__real@4066800000000000
0x18005a2ea  movsd   [rbp+0C0h+var_D8], xmm13
0x18005a2f0  movaps  xmm1, xmm13
0x18005a2f4  addsd   xmm1, cs:__real@401921fb54442d18
0x18005a2fc  movsd   [rbp+0C0h+var_F8], xmm1
0x18005a301  movzx   ecx, r14b
0x18005a305  movd    xmm0, ecx
0x18005a309  cvtdq2pd xmm0, xmm0
0x18005a30d  movsd   [rbp+0C0h+var_E8], xmm0
0x18005a312  movzx   ecx, sil
0x18005a316  movd    xmm4, ecx
0x18005a31a  cvtdq2pd xmm4, xmm4
0x18005a31e  movsd   xmm9, cs:__real@3fe0000000000000
0x18005a327  addsd   xmm4, xmm9
0x18005a32c  subsd   xmm4, xmm0
0x18005a330  movsd   xmm0, cs:__real@4076800000000000
0x18005a338  divsd   xmm4, xmm0
0x18005a33c  addsd   xmm4, xmm4
0x18005a340  movsd   [rbp+0C0h+var_100], xmm4
0x18005a345  movzx   eax, r14w
0x18005a349  shr     ax, 8
0x18005a34d  movzx   eax, ax
0x18005a350  movd    xmm5, eax
0x18005a354  cvtdq2pd xmm5, xmm5
0x18005a358  movsd   qword ptr [rbp+0C0h+size.cx], xmm5
0x18005a35d  movzx   eax, si
0x18005a360  shr     ax, 8
0x18005a364  movzx   eax, ax
0x18005a367  movd    xmm2, eax
0x18005a36b  cvtdq2pd xmm2, xmm2
0x18005a36f  addsd   xmm2, xmm9
0x18005a374  subsd   xmm2, xmm5
0x18005a378  divsd   xmm2, xmm0
0x18005a37c  addsd   xmm2, xmm2
0x18005a380  movsd   [rbp+0C0h+var_F0], xmm2
0x18005a385  shr     r14d, 10h
0x18005a389  movzx   eax, r14b
0x18005a38d  movd    xmm2, eax
0x18005a391  cvtdq2pd xmm2, xmm2
0x18005a395  movsd   [rbp+0C0h+var_E0], xmm2
0x18005a39a  shr     esi, 10h
0x18005a39d  movzx   eax, sil
0x18005a3a1  movd    xmm3, eax
0x18005a3a5  cvtdq2pd xmm3, xmm3
0x18005a3a9  addsd   xmm3, xmm9
0x18005a3ae  subsd   xmm3, xmm2
0x18005a3b2  divsd   xmm3, xmm0
0x18005a3b6  addsd   xmm3, xmm3
0x18005a3ba  movsd   [rbp+0C0h+var_108], xmm3
0x18005a3bf  xor     colorStart, colorStart
0x18005a3c2  mov     [rsp+1C0h+var_170], colorStart
0x18005a3c7  cmp     [rbp+0C0h+arg_30], colorStart
0x18005a3ce  jle     loc_18005A8D5
0x18005a3d4  movaps  xmm10, xmm1
0x18005a3d8  addsd   xmm10, cs:__real@3f91df46a2529d39
0x18005a3e1  xorps   xmm6, xmm6
0x18005a3e4  xor     colorFinish, colorFinish
0x18005a3e7  mov     [rsp+1C0h+var_16C], colorFinish
0x18005a3ec  mov     r13d, [rbx+4]
0x18005a3f0  mov     ecx, [rbx+0Ch]
0x18005a3f3  sub     ecx, r13d
0x18005a3f6  mov     eax, [rbx+8]
0x18005a3f9  sub     eax, [rbx]
0x18005a3fb  cmp     eax, ecx
0x18005a3fd  cmovge  eax, ecx
0x18005a400  cdq
0x18005a401  sub     eax, edx
0x18005a403  sar     eax, 1
0x18005a405  mov     dword ptr [rsp+1C0h+dcMem.__vftable], eax
0x18005a409  sub     r13d, [rbx+0Ch]
0x18005a40d  sub     r13d, [rbx]
0x18005a410  add     r13d, [rbx+8]
0x18005a414  mov     ecx, [rbp+0C0h+crColor]
0x18005a417  cmp     ecx, 0FFFFFFFFh
0x18005a41a  jz      loc_18005A58E
0x18005a420  test    colorStart, colorStart
0x18005a423  jnz     loc_18005A58E
0x18005a429  mov     edx, ecx; crColor
0x18005a42b  lea     this, [rbp+0C0h+brFill.m_hObject]; this
0x18005a42f  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x18005a434  nop
0x18005a435  lea     rect, [rbp+0C0h+brFill.m_hObject]; pFont
0x18005a439  lea     this, [rsp+1C0h+dcMem.m_hDC]; this
0x18005a43e  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005a443  mov     rsi, rax
0x18005a446  mov     edx, 8; nIndex
0x18005a44b  lea     this, [rsp+1C0h+dcMem.m_hDC]; this
0x18005a450  call    ?SelectStockObject@CDC@@UEAAPEAVCGdiObject@@H@Z; CDC::SelectStockObject(int)
0x18005a455  mov     r14, rax
0x18005a458  mov     colorStart, [rbx+4]; top
0x18005a45c  mov     edx, [rbx]; left
0x18005a45e  test    r13d, r13d
0x18005a461  jnz     short loc_18005A47E
0x18005a463  mov     ecx, [rbx+0Ch]
0x18005a466  mov     [rsp+1C0h+cy], ecx; bottom
0x18005a46a  mov     colorFinish, [rbx+8]; right
0x18005a46e  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a473  call    cs:__imp_Ellipse
0x18005a479  jmp     loc_18005A53D
0x18005a47e  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a483  jle     short loc_18005A4DB
0x18005a485  mov     eax, [rbx+0Ch]
0x18005a488  mov     colorFinish, eax
0x18005a48b  sub     colorFinish, colorStart
0x18005a48e  add     colorFinish, [rbx]; right
0x18005a491  mov     [rsp+1C0h+cy], eax; bottom
0x18005a495  call    cs:__imp_Ellipse
0x18005a49b  mov     eax, [rbx+0Ch]
0x18005a49e  mov     colorFinish, [rbx+8]; right
0x18005a4a2  mov     colorStart, [rbx+4]; top
0x18005a4a6  mov     edx, colorFinish
0x18005a4a9  sub     edx, eax
0x18005a4ab  add     edx, colorStart; left
0x18005a4ae  mov     [rsp+1C0h+cy], eax; bottom
0x18005a4b2  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a4b7  call    cs:__imp_Ellipse
0x18005a4bd  mov     edi, [rbx+0Ch]
0x18005a4c0  mov     colorStart, [rbx+4]
0x18005a4c4  mov     eax, edi
0x18005a4c6  sub     eax, colorStart
0x18005a4c9  cdq
0x18005a4ca  sub     eax, edx
0x18005a4cc  sar     eax, 1
0x18005a4ce  mov     colorFinish, [rbx+8]
0x18005a4d2  sub     colorFinish, eax
0x18005a4d5  mov     edx, [rbx]
0x18005a4d7  add     edx, eax
0x18005a4d9  jmp     short loc_18005A52E
0x18005a4db  mov     colorFinish, [rbx+8]; right
0x18005a4df  mov     eax, colorStart
0x18005a4e2  sub     eax, [rbx]
0x18005a4e4  add     eax, colorFinish
0x18005a4e7  mov     [rsp+1C0h+cy], eax; bottom
0x18005a4eb  call    cs:__imp_Ellipse
0x18005a4f1  mov     eax, [rbx+0Ch]
0x18005a4f4  mov     colorFinish, [rbx+8]; right
0x18005a4f8  mov     colorStart, eax
0x18005a4fb  sub     colorStart, colorFinish
0x18005a4fe  add     colorStart, [rbx]; top
0x18005a501  mov     [rsp+1C0h+cy], eax; bottom
0x18005a505  mov     edx, [rbx]; left
0x18005a507  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a50c  call    cs:__imp_Ellipse
0x18005a512  mov     colorFinish, [rbx+8]; right
0x18005a516  mov     eax, colorFinish
0x18005a519  sub     eax, [rbx]
0x18005a51b  cdq
0x18005a51c  sub     eax, edx
0x18005a51e  sar     eax, 1
0x18005a520  mov     edi, [rbx+0Ch]
0x18005a523  sub     edi, eax
0x18005a525  mov     colorStart, [rbx+4]
0x18005a529  add     colorStart, eax; top
0x18005a52c  mov     edx, [rbx]; left
0x18005a52e  mov     [rsp+1C0h+cy], edi; bottom
0x18005a532  mov     this, [rsp+1C0h+dcMem.m_hAttribDC]; hdc
0x18005a537  call    cs:__imp_Rectangle
0x18005a53d  mov     rect, rsi; pFont
0x18005a540  lea     this, [rsp+1C0h+dcMem.m_hDC]; this
0x18005a545  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005a54a  mov     rect, r14; pFont
0x18005a54d  lea     this, [rsp+1C0h+dcMem.m_hDC]; this
0x18005a552  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005a557  nop
  ... truncated ...
```
