# CMFCToolBarImages::TransparentBlt(HDC__ *,int,int,int,int,CDC *,int,int,ulong,int,int)

- ea: `0x180176b80`
- end: `0x180176fdc`
- name: `?TransparentBlt@CMFCToolBarImages@@KAXPEAUHDC__@@HHHHPEAVCDC@@HHKHH@Z`
- size: `1116`
- prototype: `void __fastcall(HDC__ *hdcDest, int nXDest, int nYDest, int nWidth, int nHeight, CDC *pDcSrc, int nXSrc, int nYSrc, unsigned int colorTransparent, int nWidthDest, int nHeightDest)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800725b0`
- `0x180173910`

## callees

- `0x18001d090`
- `0x180176b80`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af220`
- `0x1802af360`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `GDI32!StretchBlt` at `0x180176d5a`
- `GDI32!StretchBlt` at `0x180176d5a`
- `GDI32!CreateBitmap` at `0x180176dbf`
- `GDI32!CreateBitmap` at `0x180176dbf`
- `GDI32!DeleteDC` at `0x180176f7d`
- `GDI32!DeleteDC` at `0x180176f9d`
- `GDI32!DeleteDC` at `0x180176fba`
- `GDI32!DeleteDC` at `0x180176f7d`
- `GDI32!DeleteDC` at `0x180176f9d`
- `GDI32!DeleteDC` at `0x180176fba`
- `GDI32!BitBlt` at `0x180176da0`
- `GDI32!BitBlt` at `0x180176e26`
- `GDI32!BitBlt` at `0x180176e78`
- `GDI32!BitBlt` at `0x180176ebe`
- `GDI32!BitBlt` at `0x180176ef2`
- `GDI32!BitBlt` at `0x180176da0`
- `GDI32!BitBlt` at `0x180176e26`
- `GDI32!BitBlt` at `0x180176e78`
- `GDI32!BitBlt` at `0x180176ebe`
- `GDI32!BitBlt` at `0x180176ef2`
- `GDI32!CreateCompatibleBitmap` at `0x180176cdb`
- `GDI32!CreateCompatibleBitmap` at `0x180176cdb`
- `GDI32!SelectObject` at `0x180176cf6`
- `GDI32!SelectObject` at `0x180176dd9`
- `GDI32!SelectObject` at `0x180176f05`
- `GDI32!SelectObject` at `0x180176f25`
- `GDI32!SelectObject` at `0x180176cf6`
- `GDI32!SelectObject` at `0x180176dd9`
- `GDI32!SelectObject` at `0x180176f05`
- `GDI32!SelectObject` at `0x180176f25`
- `GDI32!CreateCompatibleDC` at `0x180176c84`
- `GDI32!CreateCompatibleDC` at `0x180176caa`
- `GDI32!CreateCompatibleDC` at `0x180176c84`
- `GDI32!CreateCompatibleDC` at `0x180176caa`
- `MSIMG32!TransparentBlt` at `0x180176c29`
- `MSIMG32!TransparentBlt` at `0x180176c29`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CMFCToolBarImages::TransparentBlt(
        HDC__ *hdcDest,
        int nXDest,
        int nYDest,
        int nWidth,
        int nHeight,
        CDC *pDcSrc,
        int nXSrc,
        int nYSrc,
        UINT colorTransparent,
        int nWidthDest,
        int nHeightDest)
{
  HDC__ *v12; // r10
  int v14; // r13d
  int hDest; // eax
  HDC__ *hdcSrc; // rcx
  HDC CompatibleDC; // rax
  HDC v18; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v20; // rax
  HDC__ *v21; // rcx
  HDC__ *m_hDC; // rax
  HBITMAP Bitmap; // rax
  HGDIOBJ v24; // rax
  CGdiObject *v25; // rdi
  HGDIOBJ v26; // rax
  HGDIOBJ v27; // rax
  HDC v28; // rax
  HDC v29; // rax
  HDC v30; // rax
  CDC memDC; // [rsp+60h] [rbp-91h] BYREF
  CDC dc; // [rsp+80h] [rbp-71h] BYREF
  CBitmap bmpImage; // [rsp+A0h] [rbp-51h] BYREF
  CBitmap maskBitmap; // [rsp+B0h] [rbp-41h] BYREF
  CDC maskDC; // [rsp+C0h] [rbp-31h] BYREF
  int v36; // [rsp+E0h] [rbp-11h]
  CGdiObject *v37; // [rsp+E8h] [rbp-9h]
  int cy; // [rsp+180h] [rbp+8Fh]

  v12 = hdcDest;
  v14 = nWidthDest;
  if ( nWidthDest == -1 )
    v14 = nWidth;
  hDest = nHeightDest;
  if ( nHeightDest == -1 )
    hDest = nHeight;
  cy = hDest;
  if ( !CMFCToolBarImages::m_bIsRTL )
  {
    if ( pDcSrc )
      hdcSrc = pDcSrc->m_hDC;
    else
      hdcSrc = 0;
    if ( TransparentBlt(v12, nXDest, nYDest, v14, hDest, hdcSrc, nXSrc, nYSrc, nWidth, nHeight, colorTransparent) )
      return;
    v12 = hdcDest;
  }
  dc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dc.m_hAttribDC = 0;
  LODWORD(bmpImage.__vftable) = 0;
  memDC.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDC.m_hAttribDC = 0;
  LODWORD(dc.__vftable) = 0;
  maskDC.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&maskDC.m_hAttribDC = 0;
  v36 = 0;
  CDC::Attach((CDC *)&dc.m_hDC, v12);
  CompatibleDC = CreateCompatibleDC(dc.m_hAttribDC);
  CDC::Attach((CDC *)&maskDC.m_hDC, CompatibleDC);
  maskDC.__vftable = 0;
  maskBitmap.m_hObject = (void *)CBitmap::`vftable';
  v18 = CreateCompatibleDC(dc.m_hAttribDC);
  CDC::Attach((CDC *)&memDC.m_hDC, v18);
  maskBitmap.__vftable = 0;
  bmpImage.m_hObject = (void *)CBitmap::`vftable';
  CompatibleBitmap = CreateCompatibleBitmap(dc.m_hAttribDC, v14, cy);
  CGdiObject::Attach((CGdiObject *)&bmpImage.m_hObject, CompatibleBitmap);
  v20 = SelectObject(memDC.m_hAttribDC, maskBitmap.__vftable);
  v37 = CGdiObject::FromHandle(v20);
  if ( nWidthDest == -1 || nWidthDest == nWidth && nHeightDest == nHeight )
  {
    m_hDC = 0;
    if ( pDcSrc )
      m_hDC = pDcSrc->m_hDC;
    BitBlt(memDC.m_hAttribDC, 0, 0, nWidth, nHeight, m_hDC, nXSrc, nYSrc, 0xCC0020u);
  }
  else
  {
    if ( pDcSrc )
      v21 = pDcSrc->m_hDC;
    else
      v21 = 0;
    StretchBlt(memDC.m_hAttribDC, 0, 0, nWidthDest, nHeightDest, v21, nXSrc, nYSrc, nWidth, nHeight, 0xCC0020u);
  }
  Bitmap = CreateBitmap(v14, cy, 1u, 1u, 0);
  CGdiObject::Attach((CGdiObject *)&maskBitmap.m_hObject, Bitmap);
  v24 = SelectObject(maskDC.m_hAttribDC, maskDC.__vftable);
  v25 = CGdiObject::FromHandle(v24);
  CDC::SetBkColor((CDC *)&memDC.m_hDC, colorTransparent);
  BitBlt(maskDC.m_hAttribDC, 0, 0, v14, cy, memDC.m_hAttribDC, 0, 0, 0xCC0020u);
  CDC::SetBkColor((CDC *)&memDC.m_hDC, 0);
  CDC::SetTextColor((CDC *)&memDC.m_hDC, 0xFFFFFFu);
  BitBlt(memDC.m_hAttribDC, 0, 0, v14, cy, maskDC.m_hAttribDC, 0, 0, 0x8800C6u);
  CDC::SetBkColor((CDC *)&dc.m_hDC, 0xFFFFFFu);
  CDC::SetTextColor((CDC *)&dc.m_hDC, 0);
  BitBlt(dc.m_hAttribDC, nXDest, nYDest, v14, cy, maskDC.m_hAttribDC, 0, 0, 0x8800C6u);
  BitBlt(dc.m_hAttribDC, nXDest, nYDest, v14, cy, memDC.m_hAttribDC, 0, 0, 0xEE0086u);
  if ( v25 )
  {
    v26 = SelectObject(maskDC.m_hAttribDC, v25->m_hObject);
    CGdiObject::FromHandle(v26);
  }
  if ( v37 )
  {
    v27 = SelectObject(memDC.m_hAttribDC, v37->m_hObject);
    CGdiObject::FromHandle(v27);
  }
  CDC::Detach((CDC *)&dc.m_hDC);
  bmpImage.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmpImage.m_hObject);
  maskBitmap.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&maskBitmap.m_hObject);
  maskDC.m_hDC = (HDC__ *)CDC::`vftable';
  if ( maskDC.m_hAttribDC )
  {
    v28 = CDC::Detach((CDC *)&maskDC.m_hDC);
    DeleteDC(v28);
  }
  memDC.m_hDC = (HDC__ *)CDC::`vftable';
  if ( memDC.m_hAttribDC )
  {
    v29 = CDC::Detach((CDC *)&memDC.m_hDC);
    DeleteDC(v29);
  }
  dc.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dc.m_hAttribDC )
  {
    v30 = CDC::Detach((CDC *)&dc.m_hDC);
    DeleteDC(v30);
  }
}

```

## disassembly

```asm
0x180176b80  mov     rax, rsp
0x180176b83  mov     [rax+20h], rbx
0x180176b87  mov     [rax+18h], nYDest
0x180176b8b  mov     [rax+10h], nXDest
0x180176b8e  mov     [rax+8], hdcDest
0x180176b92  push    rbp
0x180176b93  push    rsi
0x180176b94  push    rdi
0x180176b95  push    r12
0x180176b97  push    r13
0x180176b99  push    r14
0x180176b9b  push    r15
0x180176b9d  lea     rbp, [rax-3Fh]
0x180176ba1  sub     rsp, 0F0h
0x180176ba8  mov     edi, nWidth
0x180176bab  mov     r11d, nXDest
0x180176bae  mov     r10, hdcDest
0x180176bb1  mov     rbx, [rbp+37h+arg_28]
0x180176bb5  mov     r15d, [rbp+37h+cy]
0x180176bbc  mov     r13d, r15d
0x180176bbf  cmp     r15d, 0FFFFFFFFh
0x180176bc3  cmovz   r13d, nWidth
0x180176bc7  mov     r12d, [rbp+37h+arg_50]
0x180176bce  mov     eax, r12d
0x180176bd1  mov     esi, [rbp+37h+arg_20]
0x180176bd4  cmp     r12d, 0FFFFFFFFh
0x180176bd8  cmovz   eax, esi
0x180176bdb  mov     [rbp+37h+cy], eax
0x180176be1  cmp     cs:?m_bIsRTL@CMFCToolBarImages@@1HA, 0; int CMFCToolBarImages::m_bIsRTL
0x180176be8  jnz     short loc_180176C3B
0x180176bea  test    rbx, rbx
0x180176bed  jnz     short loc_180176BF3
0x180176bef  xor     ecx, ecx
0x180176bf1  jmp     short loc_180176BF7
0x180176bf3  mov     hdcDest, [rbx+8]
0x180176bf7  mov     nXDest, [rbp+37h+crTransparent]
0x180176bfd  mov     [rsp+50h], nXDest; crTransparent
0x180176c01  mov     [rsp+120h+hSrc], esi; hSrc
0x180176c05  mov     [rsp+120h+wSrc], edi; wSrc
0x180176c09  mov     nXDest, [rbp+37h+ySrc]
0x180176c0c  mov     [rsp+120h+yoriginSrc], nXDest; yoriginSrc
0x180176c10  mov     nXDest, [rbp+37h+xSrc]
0x180176c13  mov     [rsp+120h+xoriginSrc], nXDest; xoriginSrc
0x180176c17  mov     [rsp+120h+hdcSrc], hdcDest; hdcSrc
0x180176c1c  mov     [rsp+120h+hDest], eax; hDest
0x180176c20  mov     nWidth, r13d; wDest
0x180176c23  mov     nXDest, r11d; xoriginDest
0x180176c26  mov     hdcDest, r10; hdcDest
0x180176c29  call    cs:__imp_TransparentBlt
0x180176c2f  test    eax, eax
0x180176c31  jnz     loc_180176FC1
0x180176c37  mov     r10, [rbp+37h+arg_0]
0x180176c3b  mov     r14d, 8
0x180176c41  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180176c48  mov     [rbp+37h+dc.m_hDC], rax
0x180176c4c  xorps   xmm0, xmm0
0x180176c4f  movdqu  xmmword ptr [rbp+37h+dc.m_hAttribDC], xmm0
0x180176c54  and     dword ptr [rbp+37h+bmpImage.__vftable], 0
0x180176c58  mov     [rsp+120h+memDC.m_hDC], rax
0x180176c5d  movdqu  xmmword ptr [rsp+120h+memDC.m_hAttribDC], xmm0
0x180176c63  and     dword ptr [rbp+37h+dc.__vftable], 0
0x180176c67  mov     [rbp+37h+maskDC.m_hDC], rax
0x180176c6b  movdqu  xmmword ptr [rbp+37h+maskDC.m_hAttribDC], xmm0
0x180176c70  and     [rbp+37h+var_48], 0
0x180176c74  mov     rdx, r10; hDC
0x180176c77  lea     hdcDest, [rbp+37h+dc.m_hDC]; this
0x180176c7b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180176c80  mov     hdcDest, [rbp+37h+dc.m_hAttribDC]; hdc
0x180176c84  call    cs:__imp_CreateCompatibleDC
0x180176c8a  mov     rdx, rax; hDC
0x180176c8d  lea     hdcDest, [rbp+37h+maskDC.m_hDC]; this
0x180176c91  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180176c96  and     [rbp+37h+maskDC.__vftable], 0
0x180176c9b  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180176ca2  mov     [rbp+37h+maskBitmap.m_hObject], rax
0x180176ca6  mov     hdcDest, [rbp+37h+dc.m_hAttribDC]; hdc
0x180176caa  call    cs:__imp_CreateCompatibleDC
0x180176cb0  mov     rdx, rax; hDC
0x180176cb3  lea     hdcDest, [rsp+120h+memDC.m_hDC]; this
0x180176cb8  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180176cbd  and     [rbp+37h+maskBitmap.__vftable], 0
0x180176cc2  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180176cc9  mov     [rbp+37h+bmpImage.m_hObject], rax
0x180176ccd  mov     nYDest, [rbp+37h+cy]; cy
0x180176cd4  mov     nXDest, r13d; cx
0x180176cd7  mov     hdcDest, [rbp+37h+dc.m_hAttribDC]; hdc
0x180176cdb  call    cs:__imp_CreateCompatibleBitmap
0x180176ce1  mov     rdx, rax; hObject
0x180176ce4  lea     hdcDest, [rbp+37h+bmpImage.m_hObject]; this
0x180176ce8  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180176ced  mov     rdx, [rbp+37h+maskBitmap.__vftable]; h
0x180176cf1  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]; hdc
0x180176cf6  call    cs:__imp_SelectObject
0x180176cfc  mov     hdcDest, rax; h
0x180176cff  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180176d04  mov     [rbp+37h+var_40], rax
0x180176d08  cmp     r15d, 0FFFFFFFFh
0x180176d0c  jz      short loc_180176D65
0x180176d0e  cmp     r15d, edi
0x180176d11  jnz     short loc_180176D18
0x180176d13  cmp     r12d, esi
0x180176d16  jz      short loc_180176D65
0x180176d18  test    rbx, rbx
0x180176d1b  jnz     short loc_180176D21
0x180176d1d  xor     ecx, ecx
0x180176d1f  jmp     short loc_180176D25
0x180176d21  mov     hdcDest, [rbx+8]
0x180176d25  mov     dword ptr [rsp+50h], 0CC0020h; rop
0x180176d2d  mov     [rsp+120h+hSrc], esi; hSrc
0x180176d31  mov     [rsp+120h+wSrc], edi; wSrc
0x180176d35  mov     eax, [rbp+37h+ySrc]
0x180176d38  mov     [rsp+120h+yoriginSrc], eax; ySrc
0x180176d3c  mov     eax, [rbp+37h+xSrc]
0x180176d3f  mov     [rsp+120h+xoriginSrc], eax; xSrc
0x180176d43  mov     [rsp+120h+hdcSrc], hdcDest; hdcSrc
0x180176d48  mov     [rsp+120h+hDest], r12d; hDest
0x180176d4d  mov     nWidth, r15d; wDest
0x180176d50  xor     nYDest, nYDest; yDest
0x180176d53  xor     nXDest, nXDest; xDest
0x180176d55  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]; hdcDest
0x180176d5a  call    cs:__imp_StretchBlt
0x180176d60  xor     r15d, r15d
0x180176d63  jmp     short loc_180176DA6
0x180176d65  xor     r15d, r15d
0x180176d68  test    rbx, rbx
0x180176d6b  mov     eax, r15d
0x180176d6e  jz      short loc_180176D74
0x180176d70  mov     rax, [rbx+r14]
0x180176d74  mov     [rsp+120h+wSrc], 0CC0020h; rop
0x180176d7c  mov     ecx, [rbp+37h+ySrc]
0x180176d7f  mov     [rsp+120h+yoriginSrc], ecx; y1
0x180176d83  mov     ecx, [rbp+37h+xSrc]
0x180176d86  mov     [rsp+120h+xoriginSrc], ecx; x1
0x180176d8a  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180176d8f  mov     [rsp+120h+hDest], esi; cy
0x180176d93  mov     nWidth, edi; cx
0x180176d96  xor     nYDest, nYDest; y
0x180176d99  xor     nXDest, nXDest; x
0x180176d9b  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]; hdc
0x180176da0  call    cs:__imp_BitBlt
0x180176da6  mov     qword ptr [rsp+120h+hDest], r15; lpBits
0x180176dab  mov     nYDest, 1; nPlanes
0x180176db1  mov     nWidth, nYDest; nBitCount
0x180176db4  mov     ebx, [rbp+37h+cy]
0x180176dba  mov     nXDest, ebx; nHeight
0x180176dbc  mov     ecx, r13d; nWidth
0x180176dbf  call    cs:__imp_CreateBitmap
0x180176dc5  mov     rdx, rax; hObject
0x180176dc8  lea     hdcDest, [rbp+37h+maskBitmap.m_hObject]; this
0x180176dcc  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180176dd1  mov     rdx, [rbp+37h+maskDC.__vftable]; h
0x180176dd5  mov     hdcDest, [rbp+37h+maskDC.m_hAttribDC]; hdc
0x180176dd9  call    cs:__imp_SelectObject
0x180176ddf  mov     hdcDest, rax; h
0x180176de2  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180176de7  mov     rdi, rax
0x180176dea  mov     nXDest, [rbp+37h+crTransparent]; crColor
0x180176df0  lea     hdcDest, [rsp+120h+memDC.m_hDC]; this
0x180176df5  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x180176dfa  mov     [rsp+120h+wSrc], 0CC0020h; rop
0x180176e02  mov     [rsp+120h+yoriginSrc], r15d; y1
0x180176e07  mov     [rsp+120h+xoriginSrc], r15d; x1
0x180176e0c  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]
0x180176e11  mov     [rsp+120h+hdcSrc], hdcDest; hdcSrc
0x180176e16  mov     [rsp+120h+hDest], ebx; cy
0x180176e1a  mov     nWidth, r13d; cx
0x180176e1d  xor     nYDest, nYDest; y
0x180176e20  xor     nXDest, nXDest; x
0x180176e22  mov     hdcDest, [rbp+37h+maskDC.m_hAttribDC]; hdc
0x180176e26  call    cs:__imp_BitBlt
0x180176e2c  xor     nXDest, nXDest; crColor
0x180176e2e  lea     hdcDest, [rsp+120h+memDC.m_hDC]; this
0x180176e33  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x180176e38  mov     esi, 0FFFFFFh
0x180176e3d  mov     nXDest, esi; crColor
0x180176e3f  lea     hdcDest, [rsp+120h+memDC.m_hDC]; this
0x180176e44  call    ?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x180176e49  mov     r14d, 8800C6h
0x180176e4f  mov     [rsp+120h+wSrc], r14d; rop
0x180176e54  mov     [rsp+120h+yoriginSrc], r15d; y1
0x180176e59  mov     [rsp+120h+xoriginSrc], r15d; x1
0x180176e5e  mov     rax, [rbp+37h+maskDC.m_hAttribDC]
0x180176e62  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180176e67  mov     [rsp+120h+hDest], ebx; cy
0x180176e6b  mov     nWidth, r13d; cx
0x180176e6e  xor     nYDest, nYDest; y
0x180176e71  xor     nXDest, nXDest; x
0x180176e73  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]; hdc
0x180176e78  call    cs:__imp_BitBlt
0x180176e7e  mov     nXDest, esi; crColor
0x180176e80  lea     hdcDest, [rbp+37h+dc.m_hDC]; this
0x180176e84  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x180176e89  xor     nXDest, nXDest; crColor
0x180176e8b  lea     hdcDest, [rbp+37h+dc.m_hDC]; this
0x180176e8f  call    ?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x180176e94  mov     [rsp+120h+wSrc], r14d; rop
0x180176e99  mov     [rsp+120h+yoriginSrc], r15d; y1
0x180176e9e  mov     [rsp+120h+xoriginSrc], r15d; x1
0x180176ea3  mov     rax, [rbp+37h+maskDC.m_hAttribDC]
0x180176ea7  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180176eac  mov     [rsp+120h+hDest], ebx; cy
0x180176eb0  mov     nWidth, r13d; cx
0x180176eb3  mov     nYDest, [rbp+37h+y]; y
0x180176eb7  mov     nXDest, [rbp+37h+x]; x
0x180176eba  mov     hdcDest, [rbp+37h+dc.m_hAttribDC]; hdc
0x180176ebe  call    cs:__imp_BitBlt
0x180176ec4  mov     [rsp+120h+wSrc], 0EE0086h; rop
0x180176ecc  mov     [rsp+120h+yoriginSrc], r15d; y1
0x180176ed1  mov     [rsp+120h+xoriginSrc], r15d; x1
0x180176ed6  mov     rax, [rsp+120h+memDC.m_hAttribDC]
0x180176edb  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180176ee0  mov     [rsp+120h+hDest], ebx; cy
0x180176ee4  mov     nWidth, r13d; cx
0x180176ee7  mov     nYDest, [rbp+37h+y]; y
0x180176eeb  mov     nXDest, [rbp+37h+x]; x
0x180176eee  mov     hdcDest, [rbp+37h+dc.m_hAttribDC]; hdc
0x180176ef2  call    cs:__imp_BitBlt
0x180176ef8  test    rdi, rdi
0x180176efb  jz      short loc_180176F13
0x180176efd  mov     rdx, [rdi+8]; h
0x180176f01  mov     hdcDest, [rbp+37h+maskDC.m_hAttribDC]; hdc
0x180176f05  call    cs:__imp_SelectObject
0x180176f0b  mov     hdcDest, rax; h
0x180176f0e  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180176f13  mov     rax, [rbp+37h+var_40]
0x180176f17  test    rax, rax
0x180176f1a  jz      short loc_180176F33
0x180176f1c  mov     rdx, [rax+8]; h
0x180176f20  mov     hdcDest, [rsp+120h+memDC.m_hAttribDC]; hdc
0x180176f25  call    cs:__imp_SelectObject
0x180176f2b  mov     hdcDest, rax; h
0x180176f2e  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180176f33  lea     hdcDest, [rbp+37h+dc.m_hDC]; this
0x180176f37  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176f3c  nop
0x180176f3d  lea     rbx, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180176f44  mov     [rbp+37h+bmpImage.m_hObject], rbx
0x180176f48  lea     hdcDest, [rbp+37h+bmpImage.m_hObject]; this
0x180176f4c  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180176f51  nop
0x180176f52  mov     [rbp+37h+maskBitmap.m_hObject], rbx
0x180176f56  lea     hdcDest, [rbp+37h+maskBitmap.m_hObject]; this
0x180176f5a  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180176f5f  nop
0x180176f60  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x180176f67  mov     [rbp+37h+maskDC.m_hDC], rbx
0x180176f6b  cmp     [rbp+37h+maskDC.m_hAttribDC], r15
0x180176f6f  jz      short loc_180176F84
0x180176f71  lea     hdcDest, [rbp+37h+maskDC.m_hDC]; this
0x180176f75  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176f7a  mov     hdcDest, rax; hdc
0x180176f7d  call    cs:__imp_DeleteDC
0x180176f83  nop
0x180176f84  mov     [rsp+120h+memDC.m_hDC], rbx
0x180176f89  cmp     [rsp+120h+memDC.m_hAttribDC], r15
0x180176f8e  jz      short loc_180176FA4
0x180176f90  lea     hdcDest, [rsp+120h+memDC.m_hDC]; this
0x180176f95  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176f9a  mov     hdcDest, rax; hdc
0x180176f9d  call    cs:__imp_DeleteDC
0x180176fa3  nop
0x180176fa4  mov     [rbp+37h+dc.m_hDC], rbx
0x180176fa8  cmp     [rbp+37h+dc.m_hAttribDC], r15
0x180176fac  jz      short loc_180176FC1
0x180176fae  lea     hdcDest, [rbp+37h+dc.m_hDC]; this
0x180176fb2  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176fb7  mov     hdcDest, rax; hdc
0x180176fba  call    cs:__imp_DeleteDC
0x180176fc0  nop
0x180176fc1  mov     rbx, [rsp+120h+arg_18]
0x180176fc9  add     rsp, 0F0h
0x180176fd0  pop     r15
0x180176fd2  pop     r14
0x180176fd4  pop     r13
0x180176fd6  pop     r12
0x180176fd8  pop     rdi
0x180176fd9  pop     rsi
0x180176fda  pop     rbp
0x180176fdb  retn
```
