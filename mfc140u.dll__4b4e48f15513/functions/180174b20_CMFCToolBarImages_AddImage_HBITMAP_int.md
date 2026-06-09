# CMFCToolBarImages::AddImage(HBITMAP__ *,int)

- ea: `0x180174b20`
- end: `0x180174f73`
- name: `?AddImage@CMFCToolBarImages@@QEAAHPEAUHBITMAP__@@H@Z`
- size: `1107`
- prototype: `int __fastcall(CMFCToolBarImages *this, HBITMAP__ *hbmp, int bSetBitPerPixel)`
- caller_count: `18`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e3d0`
- `0x180021dc0`
- `0x1800342b0`
- `0x18009aff0`
- `0x18009b630`
- `0x18009bb20`
- `0x1800dc3c0`
- `0x1800dc500`
- `0x1800f574c`
- `0x180117af0`
- `0x18012db90`
- `0x180165ce0`
- `0x1801728c0`
- `0x180174770`
- `0x180174f80`
- `0x180175270`
- `0x1801a0a80`
- `0x1801a0a90`

## callees

- `0x1801722d0`
- `0x180172740`
- `0x180174ad0`
- `0x180174b20`
- `0x180177900`
- `0x180178c70`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802c4640`

## import_xrefs

- `USER32!CopyImage` at `0x180174b90`
- `USER32!CopyImage` at `0x180174b90`
- `GDI32!DeleteDC` at `0x180174d5c`
- `GDI32!DeleteDC` at `0x180174f34`
- `GDI32!DeleteDC` at `0x180174d5c`
- `GDI32!DeleteDC` at `0x180174f34`
- `GDI32!BitBlt` at `0x180174de8`
- `GDI32!BitBlt` at `0x180174e3e`
- `GDI32!BitBlt` at `0x180174de8`
- `GDI32!BitBlt` at `0x180174e3e`
- `GDI32!CreateCompatibleBitmap` at `0x180174d18`
- `GDI32!CreateCompatibleBitmap` at `0x180174d18`
- `GDI32!DeleteObject` at `0x180174c33`
- `GDI32!DeleteObject` at `0x180174e73`
- `GDI32!DeleteObject` at `0x180174ea7`
- `GDI32!DeleteObject` at `0x180174ec8`
- `GDI32!DeleteObject` at `0x180174edb`
- `GDI32!DeleteObject` at `0x180174f0e`
- `GDI32!DeleteObject` at `0x180174c33`
- `GDI32!DeleteObject` at `0x180174e73`
- `GDI32!DeleteObject` at `0x180174ea7`
- `GDI32!DeleteObject` at `0x180174ec8`
- `GDI32!DeleteObject` at `0x180174edb`
- `GDI32!DeleteObject` at `0x180174f0e`
- `GDI32!SelectObject` at `0x180174cd6`
- `GDI32!SelectObject` at `0x180174cfe`
- `GDI32!SelectObject` at `0x180174d33`
- `GDI32!SelectObject` at `0x180174d9f`
- `GDI32!SelectObject` at `0x180174dff`
- `GDI32!SelectObject` at `0x180174e4b`
- `GDI32!SelectObject` at `0x180174e61`
- `GDI32!SelectObject` at `0x180174eef`
- `GDI32!SelectObject` at `0x180174f05`
- `GDI32!SelectObject` at `0x180174cd6`
- `GDI32!SelectObject` at `0x180174cfe`
- `GDI32!SelectObject` at `0x180174d33`
- `GDI32!SelectObject` at `0x180174d9f`
- `GDI32!SelectObject` at `0x180174dff`
- `GDI32!SelectObject` at `0x180174e4b`
- `GDI32!SelectObject` at `0x180174e61`
- `GDI32!SelectObject` at `0x180174eef`
- `GDI32!SelectObject` at `0x180174f05`
- `GDI32!CreateCompatibleDC` at `0x180174c65`
- `GDI32!CreateCompatibleDC` at `0x180174d86`
- `GDI32!CreateCompatibleDC` at `0x180174c65`
- `GDI32!CreateCompatibleDC` at `0x180174d86`
- `GDI32!GetObjectW` at `0x180174bdb`
- `GDI32!GetObjectW` at `0x180174c82`
- `GDI32!GetObjectW` at `0x180174cbb`
- `GDI32!GetObjectW` at `0x180174bdb`
- `GDI32!GetObjectW` at `0x180174c82`
- `GDI32!GetObjectW` at `0x180174cbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CMFCToolBarImages::AddImage(CMFCToolBarImages *this, HBITMAP__ *hbmp, int bSetBitPerPixel)
{
  HBITMAP__ *m_hbmImageWell; // rsi
  HDC CompatibleDC; // rax
  int bmWidth; // r15d
  int bmHeight; // r12d
  HBITMAP__ *v9; // rcx
  HBITMAP__ *v10; // rdx
  HGDIOBJ v11; // rdi
  int v12; // r14d
  HBITMAP__ *CompatibleBitmap; // r15
  unsigned int v14; // ebx
  HDC v15; // rax
  HDC v17; // rax
  HGDIOBJ v18; // r13
  HBITMAP__ *v19; // rcx
  HBITMAP__ **p_m_hbmImageLight; // rdi
  HBITMAP__ **p_m_hbmImageShadow; // rdi
  HDC v22; // rax
  int v23; // [rsp+50h] [rbp-B0h]
  HBITMAP__ *v24; // [rsp+58h] [rbp-A8h] BYREF
  CDC memDCSrc; // [rsp+60h] [rbp-A0h] BYREF
  CDC memDCDst; // [rsp+80h] [rbp-80h] BYREF
  tagBITMAP bmp; // [rsp+A0h] [rbp-60h] BYREF
  tagBITMAP bmpScale; // [rsp+C0h] [rbp-40h] BYREF
  CMFCToolBarImages imageForScale; // [rsp+E0h] [rbp-20h] BYREF

  m_hbmImageWell = hbmp;
  if ( this->m_bIsTemporary )
    return 0xFFFFFFFFLL;
  v23 = 0;
  if ( CMFCToolBarImages::m_bIsRTL )
  {
    v23 = 1;
    v24 = (HBITMAP__ *)CopyImage(hbmp, 0, 0, 0, 0x2000u);
    CMFCToolBarImages::MirrorBitmap(&v24, this->m_sizeImage.cx);
    m_hbmImageWell = v24;
  }
  if ( this->m_dblScale != 1.0 )
  {
    if ( GetObjectW(m_hbmImageWell, 32, &bmpScale) )
    {
      if ( bmpScale.bmHeight != this->m_sizeImage.cy )
      {
        CMFCToolBarImages::CMFCToolBarImages(&imageForScale);
        imageForScale.m_hbmImageWell = m_hbmImageWell;
        imageForScale.m_nBitsPerPixel = bmpScale.bmBitsPixel;
        imageForScale.m_sizeImage = this->m_sizeImageOriginal;
        imageForScale.m_iCount = bmpScale.bmWidth / this->m_sizeImageOriginal.cx;
        CMFCToolBarImages::SmoothResize(&imageForScale, this->m_dblScale);
        imageForScale.m_bIsTemporary = 1;
        DeleteObject(m_hbmImageWell);
        m_hbmImageWell = imageForScale.m_hbmImageWell;
        CMFCToolBarImages::~CMFCToolBarImages(&imageForScale);
      }
      goto LABEL_8;
    }
    return 0xFFFFFFFFLL;
  }
LABEL_8:
  memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDCSrc.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&memDCSrc, CompatibleDC);
  if ( GetObjectW(m_hbmImageWell, 32, &bmp) )
  {
    if ( bSetBitPerPixel )
      this->m_nBitsPerPixel = bmp.bmBitsPixel;
    bmWidth = bmp.bmWidth;
    LODWORD(v24) = bmp.bmWidth;
    bmHeight = bmp.bmHeight;
    v9 = this->m_hbmImageWell;
    if ( v9 )
    {
      if ( !GetObjectW(v9, 32, &bmp) )
        goto LABEL_20;
      v10 = this->m_hbmImageWell;
      if ( !v10 )
        goto LABEL_20;
      v11 = SelectObject(memDCSrc.m_hDC, v10);
      if ( !v11 )
        goto LABEL_20;
      v12 = bmp.bmWidth;
      bmHeight = bmp.bmHeight;
    }
    else
    {
      v12 = 0;
      if ( !m_hbmImageWell )
        goto LABEL_20;
      v11 = SelectObject(memDCSrc.m_hDC, m_hbmImageWell);
      if ( !v11 )
        goto LABEL_20;
    }
    CompatibleBitmap = CreateCompatibleBitmap(memDCSrc.m_hDC, v12 + bmWidth, bmHeight);
    if ( !CompatibleBitmap )
    {
      SelectObject(memDCSrc.m_hDC, v11);
      goto LABEL_20;
    }
    memDCDst.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&memDCDst.m_hDC, 0, 20);
    v17 = CreateCompatibleDC(memDCSrc.m_hDC);
    CDC::Attach(&memDCDst, v17);
    v18 = SelectObject(memDCDst.m_hDC, CompatibleBitmap);
    if ( v18 )
    {
      if ( this->m_hbmImageWell )
        BitBlt(memDCDst.m_hDC, 0, 0, v12, bmHeight, memDCSrc.m_hDC, 0, 0, 0xCC0020u);
      if ( m_hbmImageWell && SelectObject(memDCSrc.m_hDC, m_hbmImageWell) )
      {
        BitBlt(memDCDst.m_hDC, v12, 0, (int)v24, bmHeight, memDCSrc.m_hDC, 0, 0, 0xCC0020u);
        SelectObject(memDCDst.m_hDC, v18);
        SelectObject(memDCSrc.m_hDC, v11);
        v19 = this->m_hbmImageWell;
        if ( v19 )
          DeleteObject(v19);
        this->m_hbmImageWell = CompatibleBitmap;
        this->m_bModified = 1;
        CMFCToolBarImages::UpdateCount(this);
        p_m_hbmImageLight = &this->m_hbmImageLight;
        if ( this == (CMFCToolBarImages *)-168LL )
          goto LABEL_46;
        if ( *p_m_hbmImageLight )
          DeleteObject(*p_m_hbmImageLight);
        *p_m_hbmImageLight = 0;
        p_m_hbmImageShadow = &this->m_hbmImageShadow;
        if ( this == (CMFCToolBarImages *)-176LL )
LABEL_46:
          AfxThrowInvalidArgException();
        if ( *p_m_hbmImageShadow )
          DeleteObject(*p_m_hbmImageShadow);
        *p_m_hbmImageShadow = 0;
        if ( v23 )
          DeleteObject(m_hbmImageWell);
        v14 = this->m_iCount - 1;
        goto LABEL_42;
      }
      SelectObject(memDCDst.m_hDC, v18);
    }
    SelectObject(memDCSrc.m_hDC, v11);
    DeleteObject(CompatibleBitmap);
    v14 = -1;
LABEL_42:
    memDCDst.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDst.m_hDC )
    {
      v22 = CDC::Detach(&memDCDst);
      DeleteDC(v22);
    }
    goto LABEL_21;
  }
LABEL_20:
  v14 = -1;
LABEL_21:
  memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( memDCSrc.m_hDC )
  {
    v15 = CDC::Detach(&memDCSrc);
    DeleteDC(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x180174b20  mov     [rsp-8+arg_10], rbx
0x180174b25  push    rbp
0x180174b26  push    rsi
0x180174b27  push    rdi
0x180174b28  push    r12
0x180174b2a  push    r13
0x180174b2c  push    r14
0x180174b2e  push    r15
0x180174b30  lea     rbp, [rsp-190h]
0x180174b38  sub     rsp, 290h
0x180174b3f  mov     rax, cs:__security_cookie
0x180174b46  xor     rax, rsp
0x180174b49  mov     [rbp+1C0h+var_40], rax
0x180174b50  mov     edi, bSetBitPerPixel
0x180174b53  mov     rsi, hbmp
0x180174b56  mov     rbx, this
0x180174b59  xor     r13d, r13d
0x180174b5c  cmp     [this+2Ch], r13d
0x180174b60  jnz     loc_180174F40
0x180174b66  mov     [rsp+2C0h+var_270], r13d
0x180174b6b  lea     r15d, [r13+1]
0x180174b6f  cmp     cs:?m_bIsRTL@CMFCToolBarImages@@1HA, r13d; int CMFCToolBarImages::m_bIsRTL
0x180174b76  jz      short loc_180174BAD
0x180174b78  mov     [rsp+2C0h+var_270], r15d
0x180174b7d  mov     [rsp+2C0h+flags], 2000h; flags
0x180174b85  xor     r9d, r9d; cy
0x180174b88  xor     bSetBitPerPixel, bSetBitPerPixel; cx
0x180174b8b  xor     edx, edx; type
0x180174b8d  mov     this, rsi; h
0x180174b90  call    cs:__imp_CopyImage
0x180174b96  mov     [rsp+2C0h+var_268], rax
0x180174b9b  mov     edx, [rbx+68h]; cxImage
0x180174b9e  lea     this, [rsp+2C0h+var_268]; hbmp
0x180174ba3  call    ?MirrorBitmap@CMFCToolBarImages@@SAHAEAPEAUHBITMAP__@@H@Z; CMFCToolBarImages::MirrorBitmap(HBITMAP__ * &,int)
0x180174ba8  mov     rsi, [rsp+2C0h+var_268]
0x180174bad  movsd   xmm0, qword ptr [rbx+0E8h]
0x180174bb5  ucomisd xmm0, cs:__real@3ff0000000000000
0x180174bbd  jp      short loc_180174BC4
0x180174bbf  mov     eax, r13d
0x180174bc2  jz      short loc_180174BC7
0x180174bc4  mov     eax, r15d
0x180174bc7  mov     r14d, 20h ; ' '
0x180174bcd  test    eax, eax
0x180174bcf  jz      short loc_180174C49
0x180174bd1  lea     r8, [rbp+1C0h+bmpScale]; pv
0x180174bd5  mov     edx, r14d; c
0x180174bd8  mov     this, rsi; h
0x180174bdb  call    cs:__imp_GetObjectW
0x180174be1  test    eax, eax
0x180174be3  jz      loc_180174F40
0x180174be9  mov     eax, [rbx+6Ch]
0x180174bec  cmp     [rbp+1C0h+bmpScale.bmHeight], eax
0x180174bef  jz      short loc_180174C49
0x180174bf1  lea     this, [rbp+1C0h+imageForScale]; this
0x180174bf5  call    ??0CMFCToolBarImages@@QEAA@XZ; CMFCToolBarImages::CMFCToolBarImages(void)
0x180174bfa  nop
0x180174bfb  mov     [rbp+1C0h+imageForScale.m_hbmImageWell], rsi
0x180174c02  movzx   eax, [rbp+1C0h+bmpScale.bmBitsPixel]
0x180174c06  mov     [rbp+1C0h+imageForScale.m_nBitsPerPixel], eax
0x180174c09  mov     rax, [rbx+70h]
0x180174c0d  mov     qword ptr [rbp+1C0h+imageForScale.m_sizeImage.cx], rax
0x180174c11  mov     eax, [rbp+1C0h+bmpScale.bmWidth]
0x180174c14  cdq
0x180174c15  idiv    dword ptr [rbx+70h]
0x180174c18  mov     [rbp+1C0h+imageForScale.m_iCount], eax
0x180174c1b  movsd   xmm1, qword ptr [rbx+0E8h]; dblImageScale
0x180174c23  lea     this, [rbp+1C0h+imageForScale]; this
0x180174c27  call    ?SmoothResize@CMFCToolBarImages@@QEAAHN@Z; CMFCToolBarImages::SmoothResize(double)
0x180174c2c  mov     [rbp+1C0h+imageForScale.m_bIsTemporary], r15d
0x180174c30  mov     this, rsi; ho
0x180174c33  call    cs:__imp_DeleteObject
0x180174c39  mov     rsi, [rbp+1C0h+imageForScale.m_hbmImageWell]
0x180174c40  lea     this, [rbp+1C0h+imageForScale]; this
0x180174c44  call    ??1CMFCToolBarImages@@UEAA@XZ; CMFCToolBarImages::~CMFCToolBarImages(void)
0x180174c49  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180174c50  mov     [rsp+2C0h+memDCSrc.__vftable], r15
0x180174c55  xorps   xmm0, xmm0
0x180174c58  movdqu  xmmword ptr [rsp+2C0h+memDCSrc.m_hDC], xmm0
0x180174c5e  mov     [rsp+2C0h+memDCSrc.m_bPrinting], r13d
0x180174c63  xor     ecx, ecx; hdc
0x180174c65  call    cs:__imp_CreateCompatibleDC
0x180174c6b  mov     hbmp, rax; hDC
0x180174c6e  lea     this, [rsp+2C0h+memDCSrc]; this
0x180174c73  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180174c78  lea     r8, [rbp+1C0h+bmp]; pv
0x180174c7c  mov     edx, r14d; c
0x180174c7f  mov     this, rsi; h
0x180174c82  call    cs:__imp_GetObjectW
0x180174c88  test    eax, eax
0x180174c8a  jz      loc_180174D40
0x180174c90  test    edi, edi
0x180174c92  jz      short loc_180174C9B
0x180174c94  movzx   eax, [rbp+1C0h+bmp.bmBitsPixel]
0x180174c98  mov     [rbx+0Ch], eax
0x180174c9b  mov     r15d, [rbp+1C0h+bmp.bmWidth]
0x180174c9f  mov     dword ptr [rsp+2C0h+var_268], r15d
0x180174ca4  mov     r12d, [rbp+1C0h+bmp.bmHeight]
0x180174ca8  mov     this, [rbx+0A0h]; h
0x180174caf  test    this, this
0x180174cb2  jz      short loc_180174CEE
0x180174cb4  lea     r8, [rbp+1C0h+bmp]; pv
0x180174cb8  mov     edx, r14d; c
0x180174cbb  call    cs:__imp_GetObjectW
0x180174cc1  test    eax, eax
0x180174cc3  jz      short loc_180174D39
0x180174cc5  mov     hbmp, [rbx+0A0h]; h
0x180174ccc  test    hbmp, hbmp
0x180174ccf  jz      short loc_180174D39
0x180174cd1  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174cd6  call    cs:__imp_SelectObject
0x180174cdc  mov     rdi, rax
0x180174cdf  test    rax, rax
0x180174ce2  jz      short loc_180174D39
0x180174ce4  mov     r14d, [rbp+1C0h+bmp.bmWidth]
0x180174ce8  mov     r12d, [rbp+1C0h+bmp.bmHeight]
0x180174cec  jmp     short loc_180174D0C
0x180174cee  mov     r14d, r13d
0x180174cf1  test    rsi, rsi
0x180174cf4  jz      short loc_180174D39
0x180174cf6  mov     hbmp, rsi; h
0x180174cf9  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174cfe  call    cs:__imp_SelectObject
0x180174d04  mov     rdi, rax
0x180174d07  test    rax, rax
0x180174d0a  jz      short loc_180174D39
0x180174d0c  lea     edx, [r14+r15]; cx
0x180174d10  mov     bSetBitPerPixel, r12d; cy
0x180174d13  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174d18  call    cs:__imp_CreateCompatibleBitmap
0x180174d1e  mov     r15, rax
0x180174d21  test    rax, rax
0x180174d24  jnz     short loc_180174D6A
0x180174d26  test    rdi, rdi
0x180174d29  jz      short loc_180174D39
0x180174d2b  mov     hbmp, rdi; h
0x180174d2e  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174d33  call    cs:__imp_SelectObject
0x180174d39  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180174d40  or      ebx, 0FFFFFFFFh
0x180174d43  mov     [rsp+2C0h+memDCSrc.__vftable], r15
0x180174d48  cmp     [rsp+2C0h+memDCSrc.m_hDC], r13
0x180174d4d  jz      short loc_180174D63
0x180174d4f  lea     this, [rsp+2C0h+memDCSrc]; this
0x180174d54  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180174d59  mov     this, rax; hdc
0x180174d5c  call    cs:__imp_DeleteDC
0x180174d62  nop
0x180174d63  mov     eax, ebx
0x180174d65  jmp     loc_180174F43
0x180174d6a  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180174d71  mov     [rbp+1C0h+memDCDst.__vftable], rax
0x180174d75  xorps   xmm0, xmm0
0x180174d78  movdqu  xmmword ptr [rbp+1C0h+memDCDst.m_hDC], xmm0
0x180174d7d  mov     [rbp+1C0h+memDCDst.m_bPrinting], r13d
0x180174d81  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174d86  call    cs:__imp_CreateCompatibleDC
0x180174d8c  mov     hbmp, rax; hDC
0x180174d8f  lea     this, [rbp+1C0h+memDCDst]; this
0x180174d93  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180174d98  mov     hbmp, r15; h
0x180174d9b  mov     this, [rbp+1C0h+memDCDst.m_hDC]; hdc
0x180174d9f  call    cs:__imp_SelectObject
0x180174da5  mov     r13, rax
0x180174da8  test    rax, rax
0x180174dab  jz      loc_180174EF5
0x180174db1  cmp     qword ptr [rbx+0A0h], 0
0x180174db9  jz      short loc_180174DEE
0x180174dbb  mov     [rsp+2C0h+rop], 0CC0020h; rop
0x180174dc3  and     [rsp+2C0h+var_288], 0
0x180174dc8  and     [rsp+2C0h+var_290], 0
0x180174dcd  mov     rax, [rsp+2C0h+memDCSrc.m_hDC]
0x180174dd2  mov     [rsp+2C0h+hdcSrc], rax; hdcSrc
0x180174dd7  mov     [rsp+2C0h+flags], r12d; cy
0x180174ddc  mov     r9d, r14d; cx
0x180174ddf  xor     bSetBitPerPixel, bSetBitPerPixel; y
0x180174de2  xor     edx, edx; x
0x180174de4  mov     this, [rbp+1C0h+memDCDst.m_hDC]; hdc
0x180174de8  call    cs:__imp_BitBlt
0x180174dee  test    rsi, rsi
0x180174df1  jz      loc_180174EE8
0x180174df7  mov     hbmp, rsi; h
0x180174dfa  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174dff  call    cs:__imp_SelectObject
0x180174e05  test    rax, rax
0x180174e08  jz      loc_180174EE8
0x180174e0e  mov     [rsp+2C0h+rop], 0CC0020h; rop
0x180174e16  and     [rsp+2C0h+var_288], 0
0x180174e1b  and     [rsp+2C0h+var_290], 0
0x180174e20  mov     rax, [rsp+2C0h+memDCSrc.m_hDC]
0x180174e25  mov     [rsp+2C0h+hdcSrc], rax; hdcSrc
0x180174e2a  mov     [rsp+2C0h+flags], r12d; cy
0x180174e2f  mov     r9d, dword ptr [rsp+2C0h+var_268]; cx
0x180174e34  xor     bSetBitPerPixel, bSetBitPerPixel; y
0x180174e37  mov     edx, r14d; x
0x180174e3a  mov     this, [rbp+1C0h+memDCDst.m_hDC]; hdc
0x180174e3e  call    cs:__imp_BitBlt
0x180174e44  mov     hbmp, r13; h
0x180174e47  mov     this, [rbp+1C0h+memDCDst.m_hDC]; hdc
0x180174e4b  call    cs:__imp_SelectObject
0x180174e51  xor     r13d, r13d
0x180174e54  test    rdi, rdi
0x180174e57  jz      short loc_180174E67
0x180174e59  mov     hbmp, rdi; h
0x180174e5c  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174e61  call    cs:__imp_SelectObject
0x180174e67  mov     this, [rbx+0A0h]; ho
0x180174e6e  test    this, this
0x180174e71  jz      short loc_180174E79
0x180174e73  call    cs:__imp_DeleteObject
0x180174e79  mov     [rbx+0A0h], r15
0x180174e80  mov     dword ptr [rbx+20h], 1
0x180174e87  mov     this, rbx; this
0x180174e8a  call    ?UpdateCount@CMFCToolBarImages@@IEAAXXZ; CMFCToolBarImages::UpdateCount(void)
0x180174e8f  lea     rdi, [rbx+0A8h]
0x180174e96  test    rdi, rdi
0x180174e99  jz      loc_180174F6D
0x180174e9f  mov     this, [rdi]; ho
0x180174ea2  test    this, this
0x180174ea5  jz      short loc_180174EAD
0x180174ea7  call    cs:__imp_DeleteObject
0x180174ead  mov     [rdi], r13
0x180174eb0  lea     rdi, [rbx+0B0h]
0x180174eb7  test    rdi, rdi
0x180174eba  jz      loc_180174F6D
0x180174ec0  mov     this, [rdi]; ho
0x180174ec3  test    this, this
0x180174ec6  jz      short loc_180174ECE
0x180174ec8  call    cs:__imp_DeleteObject
0x180174ece  mov     [rdi], r13
0x180174ed1  cmp     [rsp+2C0h+var_270], r13d
0x180174ed6  jz      short loc_180174EE1
0x180174ed8  mov     this, rsi; ho
0x180174edb  call    cs:__imp_DeleteObject
0x180174ee1  mov     ebx, [rbx+8]
0x180174ee4  dec     ebx
0x180174ee6  jmp     short loc_180174F17
0x180174ee8  mov     hbmp, r13; h
0x180174eeb  mov     this, [rbp+1C0h+memDCDst.m_hDC]; hdc
0x180174eef  call    cs:__imp_SelectObject
0x180174ef5  xor     r13d, r13d
0x180174ef8  test    rdi, rdi
0x180174efb  jz      short loc_180174F0B
0x180174efd  mov     hbmp, rdi; h
0x180174f00  mov     this, [rsp+2C0h+memDCSrc.m_hDC]; hdc
0x180174f05  call    cs:__imp_SelectObject
0x180174f0b  mov     this, r15; ho
0x180174f0e  call    cs:__imp_DeleteObject
0x180174f14  or      ebx, 0FFFFFFFFh
0x180174f17  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180174f1e  mov     [rbp+1C0h+memDCDst.__vftable], r15
0x180174f22  cmp     [rbp+1C0h+memDCDst.m_hDC], r13
0x180174f26  jz      short loc_180174F3B
0x180174f28  lea     this, [rbp+1C0h+memDCDst]; this
0x180174f2c  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180174f31  mov     this, rax; hdc
0x180174f34  call    cs:__imp_DeleteDC
0x180174f3a  nop
0x180174f3b  jmp     loc_180174D43
0x180174f40  or      eax, 0FFFFFFFFh
0x180174f43  mov     this, [rbp+1C0h+var_40]
0x180174f4a  xor     this, rsp; StackCookie
0x180174f4d  call    __security_check_cookie
0x180174f52  mov     rbx, [rsp+2C0h+arg_10]
0x180174f5a  add     rsp, 290h
0x180174f61  pop     r15
0x180174f63  pop     r14
0x180174f65  pop     r13
0x180174f67  pop     r12
0x180174f69  pop     rdi
0x180174f6a  pop     rsi
0x180174f6b  pop     rbp
0x180174f6c  retn
0x180174f6d  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
