# CMFCToolBarImages::DrawEx(CDC *,CRect,int,CMFCToolBarImages::ImageAlignHorz,CMFCToolBarImages::ImageAlignVert,CRect,uchar)

- ea: `0x1801742d0`
- end: `0x180174719`
- name: `?DrawEx@CMFCToolBarImages@@QEAAHPEAVCDC@@VCRect@@HW4ImageAlignHorz@1@W4ImageAlignVert@1@1E@Z`
- size: `1097`
- prototype: `int __fastcall(CMFCToolBarImages *this, CDC *pDC, CRect rect, int iImageIndex, CMFCToolBarImages::ImageAlignHorz horzAlign, CMFCToolBarImages::ImageAlignVert vertAlign, CRect rectSrc, unsigned __int8 alphaSrc)`
- caller_count: `25`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800338a0`
- `0x180033ec0`
- `0x180034510`
- `0x1800dc630`
- `0x18012dd80`
- `0x180135e00`
- `0x180136850`
- `0x1801a0ce0`
- `0x1801a0d60`
- `0x1801aa030`
- `0x1801abeb0`
- `0x1801ac900`
- `0x1801acc90`
- `0x1801ad230`
- `0x1801ad310`
- `0x1801ad8f0`
- `0x1801ad9e0`
- `0x1801adc30`
- `0x1801ae4f0`
- `0x1801b14f0`
- `0x1801b22f0`
- `0x1801b4860`
- `0x1801c8e20`
- `0x1801cae60`
- `0x1801cb280`

## callees

- `0x180173270`
- `0x1801734a0`
- `0x180173910`
- `0x1801742d0`
- `0x1802aee30`
- `0x1802c4640`

## import_xrefs

- `USER32!IntersectRect` at `0x1801743c4`
- `USER32!IntersectRect` at `0x18017447f`
- `USER32!IntersectRect` at `0x1801743c4`
- `USER32!IntersectRect` at `0x18017447f`
- `USER32!SetRectEmpty` at `0x1801746fc`
- `USER32!SetRectEmpty` at `0x1801746fc`
- `USER32!IsRectEmpty` at `0x180174311`
- `USER32!IsRectEmpty` at `0x18017433c`
- `USER32!IsRectEmpty` at `0x1801744c1`
- `USER32!IsRectEmpty` at `0x1801744d3`
- `USER32!IsRectEmpty` at `0x180174505`
- `USER32!IsRectEmpty` at `0x18017451f`
- `USER32!IsRectEmpty` at `0x180174311`
- `USER32!IsRectEmpty` at `0x18017433c`
- `USER32!IsRectEmpty` at `0x1801744c1`
- `USER32!IsRectEmpty` at `0x1801744d3`
- `USER32!IsRectEmpty` at `0x180174505`
- `USER32!IsRectEmpty` at `0x18017451f`
- `GDI32!StretchBlt` at `0x180174626`
- `GDI32!StretchBlt` at `0x180174626`
- `GDI32!SelectObject` at `0x1801744ef`
- `GDI32!SelectObject` at `0x18017463d`
- `GDI32!SelectObject` at `0x1801744ef`
- `GDI32!SelectObject` at `0x18017463d`
- `MSIMG32!AlphaBlend` at `0x1801745be`
- `MSIMG32!AlphaBlend` at `0x1801745be`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CMFCToolBarImages::DrawEx(
        CMFCToolBarImages *this,
        CDC *pDC,
        CRect *rect,
        int iImageIndex,
        CMFCToolBarImages::ImageAlignHorz horzAlign,
        CMFCToolBarImages::ImageAlignVert vertAlign,
        CRect *rectSrc,
        unsigned __int8 alphaSrc)
{
  HBITMAP__ *m_sizeImage; // rax
  int *p_right; // rdi
  __m128i v12; // xmm6
  int v13; // ecx
  int v14; // edx
  int v15; // r8d
  int *v16; // r15
  int *p_top; // r14
  int *p_bottom; // rdi
  __m128i v19; // xmm6
  int v20; // ecx
  int v21; // edx
  int v22; // r8d
  HBITMAP__ *v23; // rax
  int left; // r13d
  int wSrc; // r14d
  int hSrc; // edi
  BOOL v27; // r15d
  int xoriginSrc; // r15d
  CDC *v29; // rax
  HDC hdcSrc; // rcx
  CDC *v31; // r13
  BOOL v32; // eax
  int v33; // eax
  __int64 result; // rax
  int m_bCreateMonoDC; // r14d
  int top; // r9d
  int v37; // r8d
  unsigned int v38; // ebx
  BLENDFUNCTION ftn; // [rsp+68h] [rbp-61h]
  CSize sizeImageDesta; // [rsp+70h] [rbp-59h]
  tagAFXDrawState yoriginSrc; // [rsp+78h] [rbp-51h] BYREF
  CRect rectDst_8; // [rsp+98h] [rbp-31h] OVERLAPPED BYREF

  if ( IsRectEmpty(rectSrc) )
  {
    m_sizeImage = (HBITMAP__ *)this->m_sizeImage;
    yoriginSrc.hbmMonoOld = 0;
    yoriginSrc.hbmOldGlyphs = m_sizeImage;
    *rectSrc = *(CRect *)&yoriginSrc.hbmMonoOld;
  }
  if ( IsRectEmpty(rectSrc) )
    return 0;
  rectDst_8 = *rect;
  if ( horzAlign != ImageAlignHorzStretch )
  {
    if ( horzAlign )
    {
      if ( horzAlign == ImageAlignHorzRight )
      {
        p_right = &rectSrc->right;
        rectDst_8.left = rectDst_8.right + rectSrc->left - rectSrc->right;
      }
      else
      {
        if ( horzAlign != ImageAlignHorzCenter )
          goto LABEL_16;
        p_right = &rectSrc->right;
        rectDst_8.left += (rectDst_8.right + rectSrc->left - rectSrc->right - rectDst_8.left) / 2;
        rectDst_8.right = rectSrc->right + rectDst_8.left - rectSrc->left;
      }
    }
    else
    {
      p_right = &rectSrc->right;
      rectDst_8.right = rectDst_8.left + rectSrc->right - rectSrc->left;
    }
    v12 = (__m128i)rectDst_8;
    IntersectRect(&rectDst_8, &rectDst_8, rect);
    v13 = rectDst_8.right - rectDst_8.left;
    if ( rectDst_8.right - rectDst_8.left > 0 && v13 != *p_right - rectSrc->left )
    {
      v14 = rectDst_8.left + rectSrc->left - _mm_cvtsi128_si32(v12);
      v15 = *p_right - v14;
      rectSrc->left = v14;
      if ( v13 >= v15 )
        v13 = v15;
      *p_right = v14 + v13;
    }
  }
LABEL_16:
  if ( vertAlign != ImageAlignVertStretch )
  {
    if ( vertAlign )
    {
      if ( vertAlign == ImageAlignVertBottom )
      {
        p_bottom = &rectSrc->bottom;
        p_top = &rectSrc->top;
        rectDst_8.top = rectDst_8.bottom + rectSrc->top - rectSrc->bottom;
      }
      else
      {
        if ( vertAlign != ImageAlignVertCenter )
          goto LABEL_29;
        p_bottom = &rectSrc->bottom;
        p_top = &rectSrc->top;
        rectDst_8.top += (rectDst_8.bottom + rectSrc->top - rectSrc->bottom - rectDst_8.top) / 2;
        rectDst_8.bottom = rectSrc->bottom + rectDst_8.top - rectSrc->top;
      }
      v16 = p_bottom;
    }
    else
    {
      v16 = &rectSrc->bottom;
      p_top = &rectSrc->top;
      p_bottom = &rectSrc->bottom;
      rectDst_8.bottom = rectDst_8.top + rectSrc->bottom - rectSrc->top;
    }
    v19 = (__m128i)rectDst_8;
    IntersectRect(&rectDst_8, &rectDst_8, rect);
    v20 = rectDst_8.bottom - rectDst_8.top;
    if ( rectDst_8.bottom - rectDst_8.top > 0 && v20 != *p_bottom - *p_top )
    {
      v21 = rectDst_8.top + *p_top - _mm_cvtsi128_si32(_mm_srli_si128(v19, 4));
      v22 = *p_bottom - v21;
      *p_top = v21;
      if ( v20 >= v22 )
        v20 = v22;
      *v16 = v21 + v20;
    }
  }
LABEL_29:
  if ( IsRectEmpty(rectSrc) || IsRectEmpty(&rectDst_8) )
    return 0;
  v23 = (HBITMAP__ *)SelectObject(hDCGlyphs, this->m_hbmImageWell);
  left = rectSrc->left;
  yoriginSrc.hbmMonoOld = v23;
  LODWORD(yoriginSrc.hbmMono) = rectSrc->top;
  if ( IsRectEmpty(rectSrc) )
    wSrc = this->m_sizeImage.cx;
  else
    wSrc = rectSrc->right - rectSrc->left;
  if ( IsRectEmpty(rectSrc) )
    hSrc = this->m_sizeImage.cy;
  else
    hSrc = rectSrc->bottom - rectSrc->top;
  v27 = 0;
  if ( this->m_nBitsPerPixel == 32 )
  {
    *(_WORD *)&ftn.BlendOp = 0;
    ftn.SourceConstantAlpha = alphaSrc;
    ftn.AlphaFormat = 1;
    xoriginSrc = left + this->m_sizeImage.cx * iImageIndex;
    v29 = CDC::FromHandle(hDCGlyphs);
    if ( v29 )
      hdcSrc = v29->m_hDC;
    else
      hdcSrc = 0;
    v31 = pDC;
    v32 = AlphaBlend(
            pDC->m_hDC,
            rectDst_8.left,
            rectDst_8.top,
            rectDst_8.right - rectDst_8.left,
            rectDst_8.bottom - rectDst_8.top,
            hdcSrc,
            xoriginSrc,
            (int)yoriginSrc.hbmMono,
            wSrc,
            hSrc,
            ftn);
    goto LABEL_42;
  }
  if ( this->m_clrTransparent == -1 )
  {
    v33 = left + this->m_sizeImage.cx * iImageIndex;
    v31 = pDC;
    v32 = StretchBlt(
            pDC->m_hDC,
            rectDst_8.left,
            rectDst_8.top,
            rectDst_8.right - rectDst_8.left,
            rectDst_8.bottom - rectDst_8.top,
            hDCGlyphs,
            v33,
            (int)yoriginSrc.hbmMono,
            wSrc,
            hSrc,
            0xCC0020u);
LABEL_42:
    v27 = v32;
    goto LABEL_46;
  }
  v31 = pDC;
LABEL_46:
  SelectObject(hDCGlyphs, yoriginSrc.hbmMonoOld);
  if ( v27 )
    return 1;
  m_bCreateMonoDC = this->m_bCreateMonoDC;
  sizeImageDesta.cx = rectDst_8.right - rectDst_8.left;
  sizeImageDesta.cy = rectDst_8.bottom - rectDst_8.top;
  this->m_bCreateMonoDC = 0;
  if ( !CMFCToolBarImages::PrepareDrawImage(this, (tagAFXDrawState *)&yoriginSrc.hbmMonoOld, sizeImageDesta, 0) )
  {
    this->m_bCreateMonoDC = m_bCreateMonoDC;
    return 0;
  }
  top = rectDst_8.top;
  v37 = rectDst_8.left;
  this->m_rectSubImage = *rectSrc;
  v38 = CMFCToolBarImages::Draw(this, v31, v37, top, iImageIndex, 0, 0, 0, 0, 0, alphaSrc);
  SetRectEmpty(&this->m_rectSubImage);
  CMFCToolBarImages::EndDrawImage(this, (tagAFXDrawState *)&yoriginSrc.hbmMonoOld);
  result = v38;
  this->m_bCreateMonoDC = m_bCreateMonoDC;
  return result;
}

```

## disassembly

```asm
0x1801742d0  mov     rax, rsp
0x1801742d3  push    rbp
0x1801742d4  push    rbx
0x1801742d5  push    rsi
0x1801742d6  push    rdi
0x1801742d7  push    r12
0x1801742d9  push    r13
0x1801742db  push    r14
0x1801742dd  push    r15
0x1801742df  lea     rbp, [rax-47h]
0x1801742e3  sub     rsp, 0C8h
0x1801742ea  movaps  xmmword ptr [rax-58h], xmm6
0x1801742ee  mov     rax, cs:__security_cookie
0x1801742f5  xor     rax, rsp
0x1801742f8  mov     [rbp+3Fh+var_60], rax
0x1801742fc  mov     rbx, qword ptr [rbp+3Fh+rectSrc.left]
0x180174300  mov     rsi, this
0x180174303  mov     this, rbx; lprc
0x180174306  mov     [rbp+3Fh+iImage], iImageIndex
0x18017430a  mov     r12, rect
0x18017430d  mov     qword ptr [rbp+3Fh+sizeImageDest.cx], pDC
0x180174311  call    cs:__imp_IsRectEmpty
0x180174317  test    eax, eax
0x180174319  jz      short loc_180174339
0x18017431b  mov     rax, [rsi+68h]
0x18017431f  and     dword ptr [rbp+3Fh+var_90.hbmMonoOld], 0
0x180174323  and     dword ptr [rbp+3Fh+var_90.hbmMonoOld+4], 0
0x180174327  mov     dword ptr [rbp+3Fh+var_90.hbmOldGlyphs], eax
0x18017432a  shr     rax, 20h
0x18017432e  mov     dword ptr [rbp+3Fh+var_90.hbmOldGlyphs+4], eax
0x180174331  movups  xmm0, xmmword ptr [rbp+3Fh+var_90.hbmMonoOld]
0x180174335  movdqu  xmmword ptr [rbx], xmm0
0x180174339  mov     this, rbx; lprc
0x18017433c  call    cs:__imp_IsRectEmpty
0x180174342  test    eax, eax
0x180174344  jnz     loc_180174687
0x18017434a  movups  xmm0, xmmword ptr [r12]
0x18017434f  mov     eax, [rbp+3Fh+arg_20]
0x180174352  movdqu  xmmword ptr [rbp+3Fh+rectDst.right], xmm0
0x180174357  cmp     eax, 3
0x18017435a  jz      loc_1801743FB
0x180174360  test    eax, eax
0x180174362  jnz     short loc_180174374
0x180174364  lea     rdi, [rbx+8]
0x180174368  mov     eax, [rdi]
0x18017436a  sub     eax, [rbx]
0x18017436c  add     eax, [rbp+3Fh+rectDst.right]
0x18017436f  mov     [rbp+3Fh+var_68], eax
0x180174372  jmp     short loc_1801743B5
0x180174374  cmp     eax, 2
0x180174377  jnz     short loc_18017438A
0x180174379  mov     eax, [rbx]
0x18017437b  lea     rdi, [rbx+8]
0x18017437f  sub     eax, [rbx+8]
0x180174382  add     eax, [rbp+3Fh+var_68]
0x180174385  mov     [rbp+3Fh+rectDst.right], eax
0x180174388  jmp     short loc_1801743B5
0x18017438a  cmp     eax, 1
0x18017438d  jnz     short loc_1801743FB
0x18017438f  mov     ecx, [rbp+3Fh+rectDst.right]
0x180174392  lea     rect, [rbx+8]
0x180174396  mov     eax, [rbx]
0x180174398  mov     rdi, rect
0x18017439b  sub     eax, [rect]
0x18017439e  sub     eax, ecx
0x1801743a0  add     eax, [rbp+3Fh+var_68]
0x1801743a3  cdq
0x1801743a4  sub     eax, edx
0x1801743a6  sar     eax, 1
0x1801743a8  add     ecx, eax
0x1801743aa  mov     [rbp+3Fh+rectDst.right], ecx
0x1801743ad  sub     ecx, [rbx]
0x1801743af  add     ecx, [rect]
0x1801743b2  mov     [rbp+3Fh+var_68], ecx
0x1801743b5  movaps  xmm6, xmmword ptr [rbp+3Fh+rectDst.right]
0x1801743b9  lea     pDC, [rbp+3Fh+rectDst.right]; lprcSrc1
0x1801743bd  mov     rect, r12; lprcSrc2
0x1801743c0  lea     this, [rbp+3Fh+rectDst.right]; lprcDst
0x1801743c4  call    cs:__imp_IntersectRect
0x1801743ca  mov     ecx, [rbp+3Fh+var_68]
0x1801743cd  sub     ecx, [rbp+3Fh+rectDst.right]
0x1801743d0  test    ecx, ecx
0x1801743d2  jle     short loc_1801743FB
0x1801743d4  mov     r8d, [rdi]
0x1801743d7  mov     eax, r8d
0x1801743da  mov     edx, [rbx]
0x1801743dc  sub     eax, edx
0x1801743de  cmp     ecx, eax
0x1801743e0  jz      short loc_1801743FB
0x1801743e2  movd    eax, xmm6
0x1801743e6  sub     edx, eax
0x1801743e8  add     edx, [rbp+3Fh+rectDst.right]
0x1801743eb  sub     r8d, edx
0x1801743ee  mov     [rbx], edx
0x1801743f0  cmp     ecx, r8d
0x1801743f3  cmovge  ecx, r8d
0x1801743f7  add     ecx, edx
0x1801743f9  mov     [rdi], ecx
0x1801743fb  mov     eax, [rbp+3Fh+arg_28]
0x1801743fe  cmp     eax, 3
0x180174401  jz      loc_1801744BE
0x180174407  test    eax, eax
0x180174409  jnz     short loc_180174424
0x18017440b  lea     r15, [rbx+0Ch]
0x18017440f  mov     eax, [r15]
0x180174412  lea     r14, [rbx+4]
0x180174416  sub     eax, [r14]
0x180174419  mov     rdi, r15
0x18017441c  add     eax, [rbp+3Fh+rectDst.bottom]
0x18017441f  mov     [rbp+3Fh+var_64], eax
0x180174422  jmp     short loc_180174470
0x180174424  cmp     eax, 2
0x180174427  jnz     short loc_18017443E
0x180174429  mov     eax, [rbx+4]
0x18017442c  lea     rdi, [rbx+0Ch]
0x180174430  sub     eax, [rdi]
0x180174432  lea     r14, [rbx+4]
0x180174436  add     eax, [rbp+3Fh+var_64]
0x180174439  mov     [rbp+3Fh+rectDst.bottom], eax
0x18017443c  jmp     short loc_18017446D
0x18017443e  cmp     eax, 1
0x180174441  jnz     short loc_1801744BE
0x180174443  mov     ecx, [rbp+3Fh+rectDst.bottom]
0x180174446  lea     r9, [rbx+4]
0x18017444a  mov     eax, [r9]
0x18017444d  lea     rdi, [rbx+0Ch]
0x180174451  sub     eax, [rdi]
0x180174453  mov     r14, r9
0x180174456  sub     eax, ecx
0x180174458  add     eax, [rbp+3Fh+var_64]
0x18017445b  cdq
0x18017445c  sub     eax, edx
0x18017445e  sar     eax, 1
0x180174460  add     ecx, eax
0x180174462  mov     [rbp+3Fh+rectDst.bottom], ecx
0x180174465  sub     ecx, [r9]
0x180174468  add     ecx, [rdi]
0x18017446a  mov     [rbp+3Fh+var_64], ecx
0x18017446d  mov     r15, rdi
0x180174470  movaps  xmm6, xmmword ptr [rbp+3Fh+rectDst.right]
0x180174474  lea     pDC, [rbp+3Fh+rectDst.right]; lprcSrc1
0x180174478  mov     rect, r12; lprcSrc2
0x18017447b  lea     this, [rbp+3Fh+rectDst.right]; lprcDst
0x18017447f  call    cs:__imp_IntersectRect
0x180174485  mov     ecx, [rbp+3Fh+var_64]
0x180174488  sub     ecx, [rbp+3Fh+rectDst.bottom]
0x18017448b  test    ecx, ecx
0x18017448d  jle     short loc_1801744BE
0x18017448f  mov     r8d, [rdi]
0x180174492  mov     eax, r8d
0x180174495  mov     edx, [r14]
0x180174498  sub     eax, edx
0x18017449a  cmp     ecx, eax
0x18017449c  jz      short loc_1801744BE
0x18017449e  psrldq  xmm6, 4
0x1801744a3  movd    eax, xmm6
0x1801744a7  sub     edx, eax
0x1801744a9  add     edx, [rbp+3Fh+rectDst.bottom]
0x1801744ac  sub     r8d, edx
0x1801744af  mov     [r14], edx
0x1801744b2  cmp     ecx, r8d
0x1801744b5  cmovge  ecx, r8d
0x1801744b9  add     ecx, edx
0x1801744bb  mov     [r15], ecx
0x1801744be  mov     this, rbx; lprc
0x1801744c1  call    cs:__imp_IsRectEmpty
0x1801744c7  test    eax, eax
0x1801744c9  jnz     loc_180174687
0x1801744cf  lea     this, [rbp+3Fh+rectDst.right]; lprc
0x1801744d3  call    cs:__imp_IsRectEmpty
0x1801744d9  test    eax, eax
0x1801744db  jnz     loc_180174687
0x1801744e1  mov     pDC, [rsi+0A0h]; h
0x1801744e8  mov     this, cs:hDCGlyphs; hdc
0x1801744ef  call    cs:__imp_SelectObject
0x1801744f5  mov     r13d, [rbx]
0x1801744f8  mov     this, rbx; lprc
0x1801744fb  mov     [rbp+3Fh+var_90.hbmMonoOld], rax
0x1801744ff  mov     eax, [rbx+4]
0x180174502  mov     dword ptr [rbp+3Fh+var_90.hbmMono], eax
0x180174505  call    cs:__imp_IsRectEmpty
0x18017450b  test    eax, eax
0x18017450d  jz      short loc_180174515
0x18017450f  mov     r14d, [rsi+68h]
0x180174513  jmp     short loc_18017451C
0x180174515  mov     r14d, [rbx+8]
0x180174519  sub     r14d, [rbx]
0x18017451c  mov     this, rbx; lprc
0x18017451f  call    cs:__imp_IsRectEmpty
0x180174525  test    eax, eax
0x180174527  jz      short loc_18017452E
0x180174529  mov     edi, [rsi+6Ch]
0x18017452c  jmp     short loc_180174534
0x18017452e  mov     edi, [rbx+0Ch]
0x180174531  sub     edi, [rbx+4]
0x180174534  mov     r12b, byte ptr [rbp+3Fh+rectSrc.right]
0x18017453b  xor     r15d, r15d
0x18017453e  cmp     dword ptr [rsi+0Ch], 20h ; ' '
0x180174542  jnz     loc_1801745C9
0x180174548  mov     this, cs:hDCGlyphs; hDC
0x18017454f  mov     word ptr [rbp+3Fh+ftn.BlendOp], r15w
0x180174554  mov     r15d, [rbp+3Fh+iImage]
0x180174558  imul    r15d, [rsi+68h]
0x18017455d  mov     [rbp+3Fh+ftn.SourceConstantAlpha], r12b
0x180174561  mov     [rbp+3Fh+ftn.AlphaFormat], 1
0x180174565  add     r15d, r13d
0x180174568  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x18017456d  mov     edx, [rbp+3Fh+var_64]
0x180174570  mov     iImageIndex, [rbp+3Fh+var_68]
0x180174574  mov     r8d, [rbp+3Fh+rectDst.bottom]; yoriginDest
0x180174578  sub     edx, r8d
0x18017457b  sub     iImageIndex, [rbp+3Fh+rectDst.right]; wDest
0x18017457f  test    rax, rax
0x180174582  jnz     short loc_180174588
0x180174584  xor     ecx, ecx
0x180174586  jmp     short loc_18017458C
0x180174588  mov     this, [rax+8]
0x18017458c  mov     eax, dword ptr [rbp+3Fh+ftn.BlendOp]
0x18017458f  mov     r10d, dword ptr [rbp+3Fh+var_90.hbmMono]
0x180174593  mov     r13, qword ptr [rbp+3Fh+sizeImageDest.cx]
0x180174597  mov     [rsp+50h], eax; ftn
0x18017459b  mov     [rsp+100h+hSrc], edi; hSrc
0x18017459f  mov     [rsp+100h+wSrc], r14d; wSrc
0x1801745a4  mov     [rsp+100h+yoriginSrc], r10d; yoriginSrc
0x1801745a9  mov     [rsp+100h+xoriginSrc], r15d; xoriginSrc
0x1801745ae  mov     [rsp+100h+hdcSrc], this; hdcSrc
0x1801745b3  mov     this, [r13+8]; hdcDest
0x1801745b7  mov     [rsp+100h+hDest], edx; hDest
0x1801745bb  mov     edx, [rbp+3Fh+rectDst.right]; xoriginDest
0x1801745be  call    cs:__imp_AlphaBlend
0x1801745c4  mov     r15d, eax
0x1801745c7  jmp     short loc_180174632
0x1801745c9  cmp     dword ptr [rsi+0D8h], 0FFFFFFFFh
0x1801745d0  jnz     short loc_18017462E
0x1801745d2  mov     ecx, [rbp+3Fh+var_64]
0x1801745d5  mov     eax, [rbp+3Fh+iImage]
0x1801745d8  imul    eax, [rsi+68h]
0x1801745dc  mov     r10d, dword ptr [rbp+3Fh+var_90.hbmMono]
0x1801745e0  mov     r8d, [rbp+3Fh+rectDst.bottom]; yDest
0x1801745e4  sub     ecx, r8d
0x1801745e7  mov     iImageIndex, [rbp+3Fh+var_68]
0x1801745eb  mov     edx, [rbp+3Fh+rectDst.right]; xDest
0x1801745ee  sub     iImageIndex, edx; wDest
0x1801745f1  mov     dword ptr [rsp+50h], 0CC0020h; rop
0x1801745f9  add     eax, r13d
0x1801745fc  mov     r13, qword ptr [rbp+3Fh+sizeImageDest.cx]
0x180174600  mov     [rsp+100h+hSrc], edi; hSrc
0x180174604  mov     [rsp+100h+wSrc], r14d; wSrc
0x180174609  mov     [rsp+100h+yoriginSrc], r10d; ySrc
0x18017460e  mov     [rsp+100h+xoriginSrc], eax; xSrc
0x180174612  mov     rax, cs:hDCGlyphs
0x180174619  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x18017461e  mov     [rsp+100h+hDest], ecx; hDest
0x180174622  mov     this, [r13+8]; hdcDest
0x180174626  call    cs:__imp_StretchBlt
0x18017462c  jmp     short loc_1801745C4
0x18017462e  mov     r13, qword ptr [rbp+3Fh+sizeImageDest.cx]
0x180174632  mov     pDC, [rbp+3Fh+var_90.hbmMonoOld]; h
0x180174636  mov     this, cs:hDCGlyphs; hdc
0x18017463d  call    cs:__imp_SelectObject
0x180174643  test    r15d, r15d
0x180174646  jz      short loc_18017464F
0x180174648  mov     eax, 1
0x18017464d  jmp     short loc_180174689
0x18017464f  mov     eax, [rbp+3Fh+var_68]
0x180174652  lea     pDC, [rbp+3Fh+var_90.hbmMonoOld]; ds
0x180174656  sub     eax, [rbp+3Fh+rectDst.right]
0x180174659  xor     r15d, r15d
0x18017465c  mov     r14d, [rsi+44h]
0x180174660  xor     iImageIndex, iImageIndex; bFadeInactive
0x180174663  mov     [rbp+3Fh+sizeImageDest.cx], eax
0x180174666  mov     this, rsi; this
0x180174669  mov     eax, [rbp+3Fh+var_64]
0x18017466c  sub     eax, [rbp+3Fh+rectDst.bottom]
0x18017466f  mov     [rbp+3Fh+sizeImageDest.cy], eax
0x180174672  mov     rect, qword ptr [rbp+3Fh+sizeImageDest.cx]; sizeImageDest
0x180174676  mov     [rsi+44h], r15d
0x18017467a  call    ?PrepareDrawImage@CMFCToolBarImages@@QEAAHAEAUtagAFXDrawState@@VCSize@@H@Z; CMFCToolBarImages::PrepareDrawImage(tagAFXDrawState &,CSize,int)
0x18017467f  test    eax, eax
0x180174681  jnz     short loc_1801746B1
0x180174683  mov     [rsi+44h], r14d
0x180174687  xor     eax, eax
0x180174689  mov     this, [rbp+3Fh+var_60]
0x18017468d  xor     this, rsp; StackCookie
0x180174690  call    __security_check_cookie
0x180174695  movaps  xmm6, [rsp+100h+var_58+8]
0x18017469d  add     rsp, 0C8h
0x1801746a4  pop     r15
0x1801746a6  pop     r14
0x1801746a8  pop     r13
0x1801746aa  pop     r12
0x1801746ac  pop     rdi
0x1801746ad  pop     rsi
0x1801746ae  pop     rbx
0x1801746af  pop     rbp
0x1801746b0  retn
0x1801746b1  movups  xmm0, xmmword ptr [rbx]
0x1801746b4  mov     eax, [rbp+3Fh+iImage]
0x1801746b7  lea     rdi, [rsi+90h]
0x1801746be  mov     iImageIndex, [rbp+3Fh+rectDst.bottom]; yDest
  ... truncated ...
```
