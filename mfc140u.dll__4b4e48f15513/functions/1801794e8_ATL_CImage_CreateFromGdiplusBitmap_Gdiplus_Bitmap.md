# ATL::CImage::CreateFromGdiplusBitmap(Gdiplus::Bitmap &)

- ea: `0x1801794e8`
- end: `0x18017992d`
- name: `?CreateFromGdiplusBitmap@CImage@ATL@@AEAAJAEAVBitmap@Gdiplus@@@Z`
- size: `1093`
- prototype: `HRESULT __fastcall(ATL::CImage *this, Gdiplus::Bitmap *bmSrc)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180178900`
- `0x180179930`

## callees

- `0x1800033dc`
- `0x180089bc8`
- `0x180089dd0`
- `0x180179464`
- `0x1801794e8`
- `0x180231d70`
- `0x1802c4640`
- `0x1802c49e4`
- `0x1802c6fb0`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180179904`
- `VCRUNTIME140!memset` at `0x180179904`
- `VCRUNTIME140!memcpy` at `0x180179853`
- `VCRUNTIME140!memcpy` at `0x180179853`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801797b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801797c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180179802`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801798f0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801797b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801797c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180179802`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801798f0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017964d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017964d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180179916`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180179916`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017990a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017990a`
- `GDI32!SetDIBColorTable` at `0x1801796e7`
- `GDI32!SetDIBColorTable` at `0x1801796e7`
- `GDI32!DeleteDC` at `0x180179751`
- `GDI32!DeleteDC` at `0x180179751`
- `GDI32!SelectObject` at `0x1801796fb`
- `GDI32!SelectObject` at `0x1801796fb`
- `gdiplus!GdipGetImagePixelFormat` at `0x180179526`
- `gdiplus!GdipGetImagePixelFormat` at `0x180179526`
- `gdiplus!GdipGetImageHeight` at `0x18017958d`
- `gdiplus!GdipGetImageHeight` at `0x18017958d`
- `gdiplus!GdipGetImageWidth` at `0x1801795a6`
- `gdiplus!GdipGetImageWidth` at `0x1801795a6`
- `gdiplus!GdipGetImagePaletteSize` at `0x1801795ea`
- `gdiplus!GdipGetImagePaletteSize` at `0x1801795ea`
- `gdiplus!GdipGetImagePalette` at `0x18017967a`
- `gdiplus!GdipGetImagePalette` at `0x18017967a`
- `gdiplus!GdipBitmapLockBits` at `0x18017979b`
- `gdiplus!GdipBitmapLockBits` at `0x18017979b`
- `gdiplus!GdipBitmapUnlockBits` at `0x180179878`
- `gdiplus!GdipBitmapUnlockBits` at `0x180179878`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1801798a5`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1801798a5`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1801798b8`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1801798b8`
- `gdiplus!GdipDrawImageI` at `0x1801798cf`
- `gdiplus!GdipDrawImageI` at `0x1801798cf`
- `gdiplus!GdipDeleteGraphics` at `0x1801798d8`
- `gdiplus!GdipDeleteGraphics` at `0x1801798d8`
- `gdiplus!GdipDisposeImage` at `0x1801798e2`
- `gdiplus!GdipDisposeImage` at `0x1801798e2`

## pseudocode

```c
__int64 __fastcall ATL::CImage::CreateFromGdiplusBitmap(ATL::CImage *this, Gdiplus::Bitmap *bmSrc)
{
  Gdiplus::Status ImagePixelFormat; // eax
  int v5; // r12d
  unsigned int v6; // r13d
  unsigned int X; // r15d
  Gdiplus::Status ImageHeight; // eax
  Gdiplus::Status ImageWidth; // eax
  _QWORD *v10; // rbx
  Gdiplus::Status ImagePaletteSize; // eax
  unsigned __int64 v12; // r13
  __int64 v13; // r14
  __int64 v14; // rax
  void *v15; // rsp
  int *v16; // r14
  _QWORD *v17; // rax
  Gdiplus::Status ImagePalette; // eax
  UINT v19; // r13d
  __int64 i; // r8
  int v21; // ecx
  HDC__ *m_hDC; // rcx
  int v24; // edx
  __int64 m_nHeight; // rdx
  __int64 m_nWidth; // rcx
  Gdiplus::Status v27; // eax
  void *v28; // rcx
  void *v29; // rcx
  void *v31; // rcx
  size_t v32; // r15
  char *m_pBits; // r14
  char *Scan0; // r12
  int j; // r13d
  Gdiplus::Status v36; // eax
  __int64 v37; // rdi
  void *v38; // rcx
  unsigned int v39; // [rsp+20h] [rbp-20h]
  const unsigned int *v40; // [rsp+28h] [rbp-18h]
  int v41; // [rsp+40h] [rbp+0h] BYREF
  int nWidth[2]; // [rsp+48h] [rbp+8h] BYREF
  int nHeight; // [rsp+50h] [rbp+10h] BYREF
  Gdiplus::Rect rect; // [rsp+58h] [rbp+18h] BYREF
  Gdiplus::BitmapData data; // [rsp+68h] [rbp+28h] BYREF
  tagRGBQUAD argbPalette[256]; // [rsp+90h] [rbp+50h] BYREF

  ImagePixelFormat = (unsigned int)GdipGetImagePixelFormat(bmSrc->nativeImage, &rect);
  if ( ImagePixelFormat )
    bmSrc->lastResult = ImagePixelFormat;
  v5 = 32;
  v6 = 139273;
  v41 = 139273;
  X = rect.X;
  if ( (rect.X & 0x20000) != 0 )
  {
    v5 = BYTE1(rect.X);
    v6 = rect.X;
    v41 = rect.X;
  }
  if ( (rect.X & 0x40000) != 0 )
  {
    v5 = 32;
    v6 = 2498570;
    v41 = 2498570;
  }
  nHeight = 0;
  ImageHeight = (unsigned int)GdipGetImageHeight(bmSrc->nativeImage, &nHeight);
  if ( ImageHeight )
    bmSrc->lastResult = ImageHeight;
  nWidth[0] = 0;
  ImageWidth = (unsigned int)GdipGetImageWidth(bmSrc->nativeImage, nWidth);
  if ( ImageWidth )
    bmSrc->lastResult = ImageWidth;
  if ( !ATL::CImage::CreateEx(this, nWidth[0], nHeight, v5, v39, v40, (X & 0x40000) != 0) )
    return 2147500037LL;
  v10 = 0;
  if ( (X & 0x10000) == 0 )
    goto LABEL_39;
  nWidth[0] = 0;
  ImagePaletteSize = (unsigned int)GdipGetImagePaletteSize(bmSrc->nativeImage, nWidth);
  if ( ImagePaletteSize )
    bmSrc->lastResult = ImagePaletteSize;
  v12 = (unsigned int)nWidth[0];
  v13 = (unsigned int)nWidth[0];
  if ( nWidth[0] <= 0x400u && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((unsigned int)nWidth[0]) )
  {
    v14 = v12 + 15;
    if ( v12 + 15 < v12 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = alloca(v14 & 0xFFFFFFFFFFFFFFF0uLL);
    v16 = &v41;
  }
  else
  {
    if ( (unsigned __int64)~v13 < 0x10 )
      ATL::AtlThrowImpl(-2147024362);
    v17 = malloc(v13 + 16);
    if ( v17 )
    {
      *v17 = 0;
      v10 = v17;
      v16 = (int *)(v17 + 2);
    }
    else
    {
      v16 = 0;
    }
  }
  if ( !v16 )
  {
    while ( v10 )
    {
      v28 = v10;
      v10 = (_QWORD *)*v10;
      free(v28);
    }
    return 2147942414LL;
  }
  ImagePalette = (unsigned int)GdipGetImagePalette(bmSrc->nativeImage, v16, (unsigned int)v12);
  if ( ImagePalette )
    bmSrc->lastResult = ImagePalette;
  v19 = v16[1];
  if ( v19 - 1 > 0xFF )
  {
    while ( v10 )
    {
      v29 = v10;
      v10 = (_QWORD *)*v10;
      free(v29);
    }
    return 2147500037LL;
  }
  for ( i = 0; (unsigned int)i < v19; v19 = v16[1] )
  {
    v21 = v16[i + 2];
    argbPalette[i].rgbRed = BYTE2(v21);
    argbPalette[i].rgbGreen = BYTE1(v21);
    argbPalette[i].rgbBlue = v21;
    argbPalette[i].rgbReserved = 0;
    i = (unsigned int)(i + 1);
  }
  ATL::CImage::GetDC(this);
  SetDIBColorTable(this->m_hDC, 0, v19, argbPalette);
  if ( this->m_nDCRefCount-- == 1 )
  {
    SelectObject(this->m_hDC, this->m_hOldBitmap);
    if ( (`ATL::CImage::GetCDCCacheInstance'::`2'::`local static guard' & 1) == 0 )
    {
      `ATL::CImage::GetCDCCacheInstance'::`2'::`local static guard' |= 1u;
      `ATL::CImage::GetCDCCacheInstance'::`2'::cache = 0;
      xmmword_1803D33E0 = 0;
      atexit(`ATL::CImage::GetCDCCacheInstance'::`2'::`dynamic atexit destructor for 'cache'');
    }
    m_hDC = this->m_hDC;
    v24 = 0;
    while ( 1 )
    {
      m_hDC = (HDC__ *)_InterlockedExchange64(
                         (volatile __int64 *)&`ATL::CImage::GetCDCCacheInstance'::`2'::cache + v24,
                         (__int64)m_hDC);
      if ( !m_hDC )
        break;
      if ( ++v24 >= 4 )
      {
        DeleteDC(m_hDC);
        break;
      }
    }
    this->m_hDC = 0;
    X = rect.X;
  }
  v6 = v41;
LABEL_39:
  m_nHeight = (unsigned int)this->m_nHeight;
  m_nWidth = (unsigned int)this->m_nWidth;
  if ( v6 == X )
  {
    rect.X = 0;
    rect.Y = 0;
    rect.Width = m_nWidth;
    rect.Height = m_nHeight;
    v27 = (unsigned int)GdipBitmapLockBits(bmSrc->nativeImage, &rect, 1, X, &data);
    if ( v27 )
    {
      bmSrc->lastResult = v27;
      while ( v10 )
      {
        v31 = v10;
        v10 = (_QWORD *)*v10;
        free(v31);
      }
      return 2147942414LL;
    }
    v32 = (unsigned __int64)(unsigned int)(this->m_nWidth * v5 + 7) >> 3;
    m_pBits = (char *)this->m_pBits;
    Scan0 = (char *)data.Scan0;
    for ( j = 0; j < this->m_nHeight; ++j )
    {
      if ( v32 )
      {
        if ( !m_pBits )
          goto LABEL_64;
        if ( !Scan0 )
        {
          memset(m_pBits, 0, v32);
LABEL_64:
          *_errno() = 22;
          _invalid_parameter_noinfo();
          AfxThrowInvalidArgException();
        }
        memcpy(m_pBits, Scan0, v32);
      }
      m_pBits += this->m_nPitch;
      Scan0 += data.Stride;
    }
    v36 = (unsigned int)GdipBitmapUnlockBits(bmSrc->nativeImage, &data);
    if ( v36 )
      bmSrc->lastResult = v36;
  }
  else
  {
    *(_QWORD *)&rect.X = 0;
    GdipCreateBitmapFromScan0(m_nWidth, m_nHeight, (unsigned int)this->m_nPitch, v6, this->m_pBits, &rect);
    *(_QWORD *)nWidth = 0;
    GdipGetImageGraphicsContext(*(_QWORD *)&rect.X, nWidth);
    v37 = *(_QWORD *)nWidth;
    GdipDrawImageI(*(_QWORD *)nWidth, bmSrc->nativeImage, 0, 0);
    GdipDeleteGraphics(v37);
    GdipDisposeImage(*(_QWORD *)&rect.X);
  }
  while ( v10 )
  {
    v38 = v10;
    v10 = (_QWORD *)*v10;
    free(v38);
  }
  return 0;
}

```

## disassembly

```asm
0x1801794e8  push    rbp
0x1801794ea  push    rsi
0x1801794eb  push    rdi
0x1801794ec  push    r12
0x1801794ee  push    r13
0x1801794f0  push    r14
0x1801794f2  push    r15
0x1801794f4  sub     rsp, 4A0h
0x1801794fb  lea     rbp, [rsp+40h]
0x180179500  mov     [rbp+490h+arg_10], rbx
0x180179507  mov     rax, cs:__security_cookie
0x18017950e  xor     rax, rbp
0x180179511  mov     [rbp+490h+var_40], rax
0x180179518  mov     rsi, bmSrc
0x18017951b  mov     rdi, this
0x18017951e  lea     bmSrc, [rbp+490h+rect]
0x180179522  mov     this, [rsi+8]
0x180179526  call    cs:__imp_GdipGetImagePixelFormat
0x18017952c  test    eax, eax
0x18017952e  jz      short loc_180179533
0x180179530  mov     [rsi+10h], eax
0x180179533  mov     ecx, 20h ; ' '
0x180179538  mov     r12d, ecx
0x18017953b  mov     r13d, 22009h
0x180179541  mov     [rbp+490h+var_490], r13d
0x180179545  mov     r15d, [rbp+490h+rect.X]
0x180179549  bt      r15d, 11h
0x18017954e  jnb     short loc_180179561
0x180179550  mov     eax, r15d
0x180179553  sar     eax, 8
0x180179556  movzx   r12d, al
0x18017955a  mov     r13d, r15d
0x18017955d  mov     [rbp+490h+var_490], r15d
0x180179561  mov     eax, r15d
0x180179564  and     eax, 40000h
0x180179569  jz      short loc_180179578
0x18017956b  mov     r12d, ecx
0x18017956e  mov     r13d, 26200Ah
0x180179574  mov     [rbp+490h+var_490], r13d
0x180179578  xor     r14d, r14d
0x18017957b  test    eax, eax
0x18017957d  setnz   r14b
0x180179581  and     [rbp+490h+nHeight], 0
0x180179585  lea     bmSrc, [rbp+490h+nHeight]
0x180179589  mov     this, [rsi+8]
0x18017958d  call    cs:__imp_GdipGetImageHeight
0x180179593  test    eax, eax
0x180179595  jz      short loc_18017959A
0x180179597  mov     [rsi+10h], eax
0x18017959a  and     [rbp+490h+nWidth], 0
0x18017959e  lea     bmSrc, [rbp+490h+nWidth]
0x1801795a2  mov     this, [rsi+8]
0x1801795a6  call    cs:__imp_GdipGetImageWidth
0x1801795ac  test    eax, eax
0x1801795ae  jz      short loc_1801795B3
0x1801795b0  mov     [rsi+10h], eax
0x1801795b3  mov     [rsp+4D0h+var_4A0], r14d; nHeight
0x1801795b8  mov     r9d, r12d; nBPP
0x1801795bb  mov     r8d, [rbp+490h+nHeight]; nHeight
0x1801795bf  mov     edx, [rbp+490h+nWidth]; nWidth
0x1801795c2  mov     this, rdi; this
0x1801795c5  call    ?CreateEx@CImage@ATL@@QEAAHHHHKPEBKK@Z; ATL::CImage::CreateEx(int,int,int,ulong,ulong const *,ulong)
0x1801795ca  test    eax, eax
0x1801795cc  jz      loc_1801797CE
0x1801795d2  xor     ebx, ebx
0x1801795d4  bt      r15d, 10h
0x1801795d9  jnb     loc_180179764
0x1801795df  and     [rbp+490h+nWidth], ebx
0x1801795e2  lea     bmSrc, [rbp+490h+nWidth]
0x1801795e6  mov     this, [rsi+8]
0x1801795ea  call    cs:__imp_GdipGetImagePaletteSize
0x1801795f0  test    eax, eax
0x1801795f2  jz      short loc_1801795F7
0x1801795f4  mov     [rsi+10h], eax
0x1801795f7  mov     r13d, [rbp+490h+nWidth]
0x1801795fb  mov     r14d, r13d
0x1801795fe  cmp     r13d, 400h
0x180179605  ja      short loc_180179639
0x180179607  mov     ecx, r13d; Size
0x18017960a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18017960f  test    al, al
0x180179611  jz      short loc_180179639
0x180179613  lea     rax, [r13+0Fh]
0x180179617  cmp     rax, r13
0x18017961a  ja      short loc_180179626
0x18017961c  mov     rax, 0FFFFFFFFFFFFFF0h
0x180179626  and     rax, 0FFFFFFFFFFFFFFF0h
0x18017962a  call    _alloca_probe
0x18017962f  sub     rsp, rax
0x180179632  lea     r14, [rsp+4D0h+var_490]
0x180179637  jmp     short loc_180179667
0x180179639  mov     rax, r14
0x18017963c  not     rax
0x18017963f  cmp     rax, 10h
0x180179643  jb      loc_180179922
0x180179649  lea     this, [r14+10h]; Size
0x18017964d  call    cs:__imp_malloc
0x180179653  test    rax, rax
0x180179656  jnz     short loc_18017965D
0x180179658  xor     r14d, r14d
0x18017965b  jmp     short loc_180179667
0x18017965d  and     [rax], rbx
0x180179660  mov     rbx, rax
0x180179663  lea     r14, [rax+10h]
0x180179667  test    r14, r14
0x18017966a  jz      loc_1801797B6
0x180179670  mov     r8d, r13d
0x180179673  mov     bmSrc, r14
0x180179676  mov     this, [rsi+8]
0x18017967a  call    cs:__imp_GdipGetImagePalette
0x180179680  test    eax, eax
0x180179682  jz      short loc_180179687
0x180179684  mov     [rsi+10h], eax
0x180179687  mov     r13d, [r14+4]
0x18017968b  lea     eax, [r13-1]
0x18017968f  cmp     eax, 0FFh
0x180179694  ja      loc_1801797C9
0x18017969a  xor     r8d, r8d
0x18017969d  test    r13d, r13d
0x1801796a0  jz      short loc_1801796D2
0x1801796a2  mov     ecx, [r14+r8*4+8]
0x1801796a7  mov     eax, ecx
0x1801796a9  shr     eax, 10h
0x1801796ac  mov     [rbp+r8*4+490h+argbPalette.rgbRed], al
0x1801796b1  mov     eax, ecx
0x1801796b3  shr     eax, 8
0x1801796b6  mov     [rbp+r8*4+490h+argbPalette.rgbGreen], al
0x1801796bb  mov     [rbp+r8*4+490h+argbPalette.rgbBlue], cl
0x1801796c0  mov     [rbp+r8*4+490h+argbPalette.rgbReserved], 0
0x1801796c6  inc     r8d
0x1801796c9  mov     r13d, [r14+4]
0x1801796cd  cmp     r8d, r13d
0x1801796d0  jb      short loc_1801796A2
0x1801796d2  mov     this, rdi; this
0x1801796d5  call    ?GetDC@CImage@ATL@@QEBAPEAUHDC__@@XZ; ATL::CImage::GetDC(void)
0x1801796da  lea     r9, [rbp+490h+argbPalette]; prgbq
0x1801796de  mov     r8d, r13d; cEntries
0x1801796e1  xor     edx, edx; iStart
0x1801796e3  mov     this, [rdi+38h]; hdc
0x1801796e7  call    cs:__imp_SetDIBColorTable
0x1801796ed  sub     dword ptr [rdi+40h], 1
0x1801796f1  jnz     short loc_180179760
0x1801796f3  mov     bmSrc, [rdi+48h]; h
0x1801796f7  mov     this, [rdi+38h]; hdc
0x1801796fb  call    cs:__imp_SelectObject
0x180179701  mov     eax, cs:??_B?1??GetCDCCacheInstance@CImage@ATL@@CAPEAVCDCCache@12@XZ@51; `ATL::CImage::GetCDCCacheInstance(void)'::`2'::`local static guard'{2}'
0x180179707  test    al, 1
0x180179709  jnz     short loc_180179731
0x18017970b  or      eax, 1
0x18017970e  mov     cs:??_B?1??GetCDCCacheInstance@CImage@ATL@@CAPEAVCDCCache@12@XZ@51, eax; `ATL::CImage::GetCDCCacheInstance(void)'::`2'::`local static guard'{2}'
0x180179714  xorps   xmm0, xmm0
0x180179717  movups  cs:?cache@?1??GetCDCCacheInstance@CImage@ATL@@CAPEAVCDCCache@23@XZ@4V423@A, xmm0; ATL::CImage::CDCCache `ATL::CImage::GetCDCCacheInstance(void)'::`2'::cache
0x18017971e  movups  cs:xmmword_1803D33E0, xmm0
0x180179725  lea     this, ??__Fcache@?1??GetCDCCacheInstance@CImage@ATL@@CAPEAVCDCCache@12@XZ@YAXXZ; function
0x18017972c  call    atexit
0x180179731  mov     this, [rdi+38h]
0x180179735  xor     edx, edx
0x180179737  movsxd  rax, edx
0x18017973a  lea     r8, ?cache@?1??GetCDCCacheInstance@CImage@ATL@@CAPEAVCDCCache@23@XZ@4V423@A; ATL::CImage::CDCCache `ATL::CImage::GetCDCCacheInstance(void)'::`2'::cache
0x180179741  xchg    this, [r8+rax*8]; hdc
0x180179745  test    this, this
0x180179748  jz      short loc_180179757
0x18017974a  inc     edx
0x18017974c  cmp     edx, 4
0x18017974f  jl      short loc_180179737
0x180179751  call    cs:__imp_DeleteDC
0x180179757  and     qword ptr [rdi+38h], 0
0x18017975c  mov     r15d, [rbp+490h+rect.X]
0x180179760  mov     r13d, [rbp+490h+var_490]
0x180179764  mov     edx, [rdi+1Ch]
0x180179767  mov     ecx, [rdi+18h]
0x18017976a  cmp     r13d, r15d
0x18017976d  jnz     loc_180179887
0x180179773  and     [rbp+490h+rect.X], 0
0x180179777  and     [rbp+490h+rect.Y], 0
0x18017977b  mov     [rbp+490h+rect.Width], ecx
0x18017977e  mov     [rbp+490h+rect.Height], edx
0x180179781  lea     rax, [rbp+490h+data]
0x180179785  mov     [rsp+4D0h+var_4B0], rax
0x18017978a  mov     r9d, r15d
0x18017978d  mov     r8d, 1
0x180179793  lea     bmSrc, [rbp+490h+rect]
0x180179797  mov     this, [rsi+8]
0x18017979b  call    cs:__imp_GdipBitmapLockBits
0x1801797a1  test    eax, eax
0x1801797a3  jz      short loc_180179814
0x1801797a5  mov     [rsi+10h], eax
0x1801797a8  jmp     short loc_180179808
0x1801797aa  mov     this, rbx; Block
0x1801797ad  mov     rbx, [rbx]
0x1801797b0  call    cs:__imp_free
0x1801797b6  test    rbx, rbx
0x1801797b9  jnz     short loc_1801797AA
0x1801797bb  jmp     short loc_18017980D
0x1801797bd  mov     this, rbx; Block
0x1801797c0  mov     rbx, [rbx]
0x1801797c3  call    cs:__imp_free
0x1801797c9  test    rbx, rbx
0x1801797cc  jnz     short loc_1801797BD
0x1801797ce  mov     eax, 80004005h
0x1801797d3  mov     this, [rbp+490h+var_40]
0x1801797da  xor     this, rbp; StackCookie
0x1801797dd  call    __security_check_cookie
0x1801797e2  mov     rbx, [rbp+490h+arg_10]
0x1801797e9  lea     rsp, [rbp+460h]
0x1801797f0  pop     r15
0x1801797f2  pop     r14
0x1801797f4  pop     r13
0x1801797f6  pop     r12
0x1801797f8  pop     rdi
0x1801797f9  pop     rsi
0x1801797fa  pop     rbp
0x1801797fb  retn
0x1801797fc  mov     this, rbx; Block
0x1801797ff  mov     rbx, [rbx]
0x180179802  call    cs:__imp_free
0x180179808  test    rbx, rbx
0x18017980b  jnz     short loc_1801797FC
0x18017980d  mov     eax, 8007000Eh
0x180179812  jmp     short loc_1801797D3
0x180179814  imul    r12d, [rdi+18h]
0x180179819  lea     r15d, [r12+7]
0x18017981e  shr     r15, 3
0x180179822  mov     r14, [rdi+10h]
0x180179826  mov     r12, [rbp+490h+data.Scan0]
0x18017982a  xor     r13d, r13d
0x18017982d  cmp     [rdi+1Ch], r13d
0x180179831  jle     short loc_180179870
0x180179833  test    r15, r15
0x180179836  jz      short loc_180179859
0x180179838  test    r14, r14
0x18017983b  jz      loc_18017990A
0x180179841  mov     r8, r15; Size
0x180179844  mov     this, r14; void *
0x180179847  test    r12, r12
0x18017984a  jz      loc_180179902
0x180179850  mov     bmSrc, r12; Src
0x180179853  call    cs:__imp_memcpy
0x180179859  movsxd  rax, dword ptr [rdi+20h]
0x18017985d  add     r14, rax
0x180179860  movsxd  rax, [rbp+490h+data.Stride]
0x180179864  add     r12, rax
0x180179867  inc     r13d
0x18017986a  cmp     r13d, [rdi+1Ch]
0x18017986e  jl      short loc_180179833
0x180179870  lea     bmSrc, [rbp+490h+data]
0x180179874  mov     this, [rsi+8]
0x180179878  call    cs:__imp_GdipBitmapUnlockBits
0x18017987e  test    eax, eax
0x180179880  jz      short loc_1801798F6
0x180179882  mov     [rsi+10h], eax
0x180179885  jmp     short loc_1801798F6
0x180179887  and     qword ptr [rbp+490h+rect.X], 0
0x18017988c  lea     rax, [rbp+490h+rect]
0x180179890  mov     [rsp+4D0h+var_4A8], rax
0x180179895  mov     rax, [rdi+10h]
0x180179899  mov     [rsp+4D0h+var_4B0], rax
0x18017989e  mov     r9d, r13d
0x1801798a1  mov     r8d, [rdi+20h]
0x1801798a5  call    cs:__imp_GdipCreateBitmapFromScan0
0x1801798ab  and     qword ptr [rbp+490h+nWidth], 0
0x1801798b0  lea     bmSrc, [rbp+490h+nWidth]
0x1801798b4  mov     this, qword ptr [rbp+490h+rect.X]
0x1801798b8  call    cs:__imp_GdipGetImageGraphicsContext
0x1801798be  mov     rdi, qword ptr [rbp+490h+nWidth]
0x1801798c2  xor     r9d, r9d
0x1801798c5  xor     r8d, r8d
0x1801798c8  mov     bmSrc, [rsi+8]
0x1801798cc  mov     this, rdi
0x1801798cf  call    cs:__imp_GdipDrawImageI
0x1801798d5  mov     this, rdi
0x1801798d8  call    cs:__imp_GdipDeleteGraphics
0x1801798de  mov     this, qword ptr [rbp+490h+rect.X]
0x1801798e2  call    cs:__imp_GdipDisposeImage
0x1801798e8  jmp     short loc_1801798F6
0x1801798ea  mov     this, rbx; Block
0x1801798ed  mov     rbx, [rbx]
0x1801798f0  call    cs:__imp_free
0x1801798f6  test    rbx, rbx
0x1801798f9  jnz     short loc_1801798EA
0x1801798fb  xor     eax, eax
0x1801798fd  jmp     loc_1801797D3
0x180179902  xor     edx, edx; Val
0x180179904  call    cs:__imp_memset
0x18017990a  call    cs:__imp__errno
0x180179910  mov     dword ptr [rax], 16h
0x180179916  call    cs:__imp__invalid_parameter_noinfo
0x18017991c  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180179922  mov     ecx, 80070216h; hr
0x180179927  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
