# CMFCToolBarImages::MapBmpTo3dColors(HBITMAP__ * &,int,ulong,ulong)

- ea: `0x180176fe0`
- end: `0x18017724a`
- name: `?MapBmpTo3dColors@CMFCToolBarImages@@KAHAEAPEAUHBITMAP__@@HKK@Z`
- size: `618`
- prototype: `int __fastcall(HBITMAP__ **hBmp, int bUseRGBQUAD, unsigned int clrSrc, unsigned int clrDest)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180092220`
- `0x180092260`
- `0x1801728c0`
- `0x180174770`
- `0x180177250`

## callees

- `0x180175af0`
- `0x180175c10`
- `0x180176fe0`
- `0x1802aee60`
- `0x1802aef40`

## import_xrefs

- `GDI32!SetPixel` at `0x1801771cc`
- `GDI32!SetPixel` at `0x1801771cc`
- `GDI32!BitBlt` at `0x18017714b`
- `GDI32!BitBlt` at `0x18017714b`
- `GDI32!CreateCompatibleBitmap` at `0x1801770a8`
- `GDI32!CreateCompatibleBitmap` at `0x1801770a8`
- `GDI32!GetPixel` at `0x18017717d`
- `GDI32!GetPixel` at `0x18017717d`
- `GDI32!DeleteObject` at `0x180177117`
- `GDI32!DeleteObject` at `0x18017720f`
- `GDI32!DeleteObject` at `0x180177117`
- `GDI32!DeleteObject` at `0x18017720f`
- `GDI32!SelectObject` at `0x18017707e`
- `GDI32!SelectObject` at `0x1801770c1`
- `GDI32!SelectObject` at `0x1801770f8`
- `GDI32!SelectObject` at `0x18017710e`
- `GDI32!SelectObject` at `0x1801771f9`
- `GDI32!SelectObject` at `0x180177206`
- `GDI32!SelectObject` at `0x18017707e`
- `GDI32!SelectObject` at `0x1801770c1`
- `GDI32!SelectObject` at `0x1801770f8`
- `GDI32!SelectObject` at `0x18017710e`
- `GDI32!SelectObject` at `0x1801771f9`
- `GDI32!SelectObject` at `0x180177206`
- `GDI32!CreateCompatibleDC` at `0x180177042`
- `GDI32!CreateCompatibleDC` at `0x1801770df`
- `GDI32!CreateCompatibleDC` at `0x180177042`
- `GDI32!CreateCompatibleDC` at `0x1801770df`
- `GDI32!GetObjectW` at `0x180177060`
- `GDI32!GetObjectW` at `0x180177060`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMFCToolBarImages::MapBmpTo3dColors(
        HANDLE *hBmp,
        int bUseRGBQUAD,
        unsigned int clrSrc,
        COLORREF clrDest)
{
  HANDLE *v4; // r14
  unsigned int v5; // ebx
  HDC CompatibleDC; // rax
  HGDIOBJ v7; // rdi
  int bmWidthBytes; // r12d
  int cy; // esi
  HBITMAP CompatibleBitmap; // r13
  HDC v11; // rax
  int v12; // r15d
  int v13; // esi
  COLORREF Pixel; // eax
  COLORREF v15; // r12d
  COLORREF v16; // r9d
  unsigned int v17; // eax
  CDC memDCSrc; // [rsp+58h] [rbp-69h] BYREF
  CDC memDCDst; // [rsp+78h] [rbp-49h] BYREF
  int v21; // [rsp+98h] [rbp-29h]
  HGDIOBJ v22; // [rsp+A0h] [rbp-21h]
  HBITMAP v23; // [rsp+A8h] [rbp-19h]
  tagBITMAP bmp; // [rsp+B0h] [rbp-11h] BYREF

  v4 = hBmp;
  v5 = 0;
  if ( !*hBmp || clrSrc != -1 && clrDest == -1 )
    return 0;
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
  LODWORD(memDCDst.__vftable) = 0;
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
  if ( !GetObjectW(*v4, 32, &bmp.bmHeight) )
    goto LABEL_30;
  if ( !*v4 )
    goto LABEL_30;
  v7 = SelectObject(memDCSrc.m_hAttribDC, *v4);
  if ( !v7 )
    goto LABEL_30;
  bmWidthBytes = bmp.bmWidthBytes;
  cy = *(_DWORD *)&bmp.bmPlanes;
  memDCSrc.__vftable = (CDC_vtbl *)__PAIR64__(bmp.bmWidthBytes, *(unsigned int *)&bmp.bmPlanes);
  CompatibleBitmap = CreateCompatibleBitmap(memDCSrc.m_hAttribDC, bmp.bmWidthBytes, *(int *)&bmp.bmPlanes);
  v23 = CompatibleBitmap;
  if ( !CompatibleBitmap )
  {
    SelectObject(memDCSrc.m_hAttribDC, v7);
    goto LABEL_30;
  }
  memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCDst.m_hAttribDC = 0;
  v21 = 0;
  v11 = CreateCompatibleDC(memDCSrc.m_hAttribDC);
  CDC::Attach((CDC *)&memDCDst.m_hDC, v11);
  *(_QWORD *)&bmp.bmType = SelectObject(memDCDst.m_hAttribDC, CompatibleBitmap);
  if ( !*(_QWORD *)&bmp.bmType )
  {
    SelectObject(memDCSrc.m_hAttribDC, v7);
    DeleteObject(CompatibleBitmap);
    goto LABEL_29;
  }
  BitBlt(memDCDst.m_hAttribDC, 0, 0, bmWidthBytes, cy, memDCSrc.m_hAttribDC, 0, 0, 0xCC0020u);
  v12 = 0;
  if ( bmWidthBytes <= 0 )
    goto LABEL_28;
  v22 = v7;
  do
  {
    v13 = 0;
    if ( SLODWORD(memDCSrc.__vftable) <= 0 )
      goto LABEL_26;
    do
    {
      Pixel = GetPixel(memDCDst.m_hAttribDC, v12, v13);
      v15 = Pixel;
      if ( clrSrc != -1 )
      {
        if ( Pixel != clrSrc )
          goto LABEL_24;
        v16 = clrDest;
        goto LABEL_23;
      }
      if ( WORD1(bmp.bmBits) != 24 || CMFCToolBarImages::m_bDisableTrueColorAlpha )
        v17 = CMFCToolBarImages::MapToSysColor(Pixel, bUseRGBQUAD);
      else
        v17 = CMFCToolBarImages::MapToSysColorAlpha(Pixel);
      if ( v15 != v17 )
      {
        v16 = v17;
LABEL_23:
        SetPixel(memDCDst.m_hAttribDC, v12, v13, v16);
      }
LABEL_24:
      ++v13;
    }
    while ( v13 < SLODWORD(memDCSrc.__vftable) );
    bmWidthBytes = HIDWORD(memDCSrc.__vftable);
LABEL_26:
    ++v12;
  }
  while ( v12 < bmWidthBytes );
  v7 = v22;
  v4 = hBmp;
  CompatibleBitmap = v23;
LABEL_28:
  SelectObject(memDCDst.m_hAttribDC, *(HGDIOBJ *)&bmp.bmType);
  SelectObject(memDCSrc.m_hAttribDC, v7);
  DeleteObject(*v4);
  *v4 = CompatibleBitmap;
  v5 = 1;
LABEL_29:
  CDC::~CDC((CDC *)&memDCDst.m_hDC);
LABEL_30:
  CDC::~CDC((CDC *)&memDCSrc.m_hDC);
  return v5;
}

```

## disassembly

```asm
0x180176fe0  mov     rax, rsp
0x180176fe3  mov     [rax+20h], clrDest
0x180176fe7  mov     [rax+18h], clrSrc
0x180176feb  mov     [rax+10h], bUseRGBQUAD
0x180176fee  mov     [rax+8], hBmp
0x180176ff2  push    rbp
0x180176ff3  push    rbx
0x180176ff4  push    rsi
0x180176ff5  push    rdi
0x180176ff6  push    r12
0x180176ff8  push    r13
0x180176ffa  push    r14
0x180176ffc  push    r15
0x180176ffe  lea     rbp, [rax-5Fh]
0x180177002  sub     rsp, 0D8h
0x180177009  mov     eax, clrSrc
0x18017700c  mov     r14, hBmp
0x18017700f  xor     ebx, ebx
0x180177011  cmp     [hBmp], rbx
0x180177014  jz      loc_180177234
0x18017701a  or      ecx, 0FFFFFFFFh
0x18017701d  cmp     eax, ecx
0x18017701f  jz      short loc_18017702A
0x180177021  cmp     clrDest, ecx
0x180177024  jz      loc_180177234
0x18017702a  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180177031  mov     [rbp+57h+memDCSrc.m_hDC], r15
0x180177035  xorps   xmm0, xmm0
0x180177038  movdqu  xmmword ptr [rbp+57h+memDCSrc.m_hAttribDC], xmm0
0x18017703d  mov     dword ptr [rbp+57h+memDCDst.__vftable], ebx
0x180177040  xor     ecx, ecx; hdc
0x180177042  call    cs:__imp_CreateCompatibleDC
0x180177048  mov     rdx, rax; hDC
0x18017704b  lea     hBmp, [rbp+57h+memDCSrc.m_hDC]; this
0x18017704f  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180177054  lea     r8, [rbp+57h+bmp.bmHeight]; pv
0x180177058  mov     bUseRGBQUAD, 20h ; ' '; c
0x18017705d  mov     hBmp, [r14]; h
0x180177060  call    cs:__imp_GetObjectW
0x180177066  test    eax, eax
0x180177068  jz      loc_180177227
0x18017706e  cmp     [r14], rbx
0x180177071  jz      loc_180177227
0x180177077  mov     rdx, [r14]; h
0x18017707a  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x18017707e  call    cs:__imp_SelectObject
0x180177084  mov     rdi, rax
0x180177087  test    rax, rax
0x18017708a  jz      loc_180177227
0x180177090  mov     r12d, [rbp+57h+bmp.bmWidthBytes]
0x180177094  mov     dword ptr [rbp+57h+memDCSrc.__vftable+4], r12d
0x180177098  mov     esi, dword ptr [rbp+57h+bmp.bmPlanes]
0x18017709b  mov     dword ptr [rbp+57h+memDCSrc.__vftable], esi
0x18017709e  mov     clrSrc, esi; cy
0x1801770a1  mov     bUseRGBQUAD, r12d; cx
0x1801770a4  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801770a8  call    cs:__imp_CreateCompatibleBitmap
0x1801770ae  mov     r13, rax
0x1801770b1  mov     [rbp+57h+var_70], rax
0x1801770b5  test    rax, rax
0x1801770b8  jnz     short loc_1801770CC
0x1801770ba  mov     rdx, rdi; h
0x1801770bd  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801770c1  call    cs:__imp_SelectObject
0x1801770c7  jmp     loc_180177227
0x1801770cc  mov     [rbp+57h+memDCDst.m_hDC], r15
0x1801770d0  xorps   xmm0, xmm0
0x1801770d3  movdqu  xmmword ptr [rbp+57h+memDCDst.m_hAttribDC], xmm0
0x1801770d8  mov     [rbp+57h+var_80], ebx
0x1801770db  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801770df  call    cs:__imp_CreateCompatibleDC
0x1801770e5  mov     rdx, rax; hDC
0x1801770e8  lea     hBmp, [rbp+57h+memDCDst.m_hDC]; this
0x1801770ec  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1801770f1  mov     rdx, r13; h
0x1801770f4  mov     hBmp, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801770f8  call    cs:__imp_SelectObject
0x1801770fe  mov     qword ptr [rbp+57h+bmp.bmType], rax
0x180177102  test    rax, rax
0x180177105  jnz     short loc_180177122
0x180177107  mov     rdx, rdi; h
0x18017710a  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x18017710e  call    cs:__imp_SelectObject
0x180177114  mov     hBmp, r13; ho
0x180177117  call    cs:__imp_DeleteObject
0x18017711d  jmp     loc_18017721D
0x180177122  mov     dword ptr [rsp+40h], 0CC0020h; rop
0x18017712a  mov     [rsp+110h+y1], ebx; y1
0x18017712e  mov     [rsp+110h+x1], ebx; x1
0x180177132  mov     rax, [rbp+57h+memDCSrc.m_hAttribDC]
0x180177136  mov     [rsp+110h+hdcSrc], rax; hdcSrc
0x18017713b  mov     [rsp+110h+cy], esi; cy
0x18017713f  mov     clrDest, r12d; cx
0x180177142  xor     clrSrc, clrSrc; y
0x180177145  xor     bUseRGBQUAD, bUseRGBQUAD; x
0x180177147  mov     hBmp, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x18017714b  call    cs:__imp_BitBlt
0x180177151  mov     r15d, ebx
0x180177154  test    r12d, r12d
0x180177157  jle     loc_1801771F1
0x18017715d  mov     [rbp+57h+var_78], rdi
0x180177161  mov     r13d, dword ptr [rbp+57h+memDCSrc.__vftable]
0x180177165  mov     r14d, [rbp+57h+arg_10]
0x180177169  mov     edi, [rbp+57h+arg_18]
0x18017716c  mov     esi, ebx
0x18017716e  test    r13d, r13d
0x180177171  jle     short loc_1801771DD
0x180177173  mov     clrSrc, esi; y
0x180177176  mov     bUseRGBQUAD, r15d; x
0x180177179  mov     hBmp, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x18017717d  call    cs:__imp_GetPixel
0x180177183  mov     r12d, eax
0x180177186  cmp     r14d, 0FFFFFFFFh
0x18017718a  jz      short loc_180177196
0x18017718c  cmp     eax, r14d
0x18017718f  jnz     short loc_1801771D2
0x180177191  mov     clrDest, edi
0x180177194  jmp     short loc_1801771C2
0x180177196  cmp     word ptr [rbp+57h+bmp.bmBits+2], 18h
0x18017719b  jnz     short loc_1801771AF
0x18017719d  cmp     cs:?m_bDisableTrueColorAlpha@CMFCToolBarImages@@2HA, ebx; int CMFCToolBarImages::m_bDisableTrueColorAlpha
0x1801771a3  jnz     short loc_1801771AF
0x1801771a5  mov     ecx, r12d; color
0x1801771a8  call    ?MapToSysColorAlpha@CMFCToolBarImages@@SAKK@Z; CMFCToolBarImages::MapToSysColorAlpha(ulong)
0x1801771ad  jmp     short loc_1801771BA
0x1801771af  mov     bUseRGBQUAD, [rbp+57h+arg_8]; bUseRGBQUAD
0x1801771b2  mov     ecx, r12d; color
0x1801771b5  call    ?MapToSysColor@CMFCToolBarImages@@SAKKH@Z; CMFCToolBarImages::MapToSysColor(ulong,int)
0x1801771ba  cmp     r12d, eax
0x1801771bd  jz      short loc_1801771D2
0x1801771bf  mov     clrDest, eax; color
0x1801771c2  mov     clrSrc, esi; y
0x1801771c5  mov     bUseRGBQUAD, r15d; x
0x1801771c8  mov     hBmp, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801771cc  call    cs:__imp_SetPixel
0x1801771d2  inc     esi
0x1801771d4  cmp     esi, r13d
0x1801771d7  jl      short loc_180177173
0x1801771d9  mov     r12d, dword ptr [rbp+57h+memDCSrc.__vftable+4]
0x1801771dd  inc     r15d
0x1801771e0  cmp     r15d, r12d
0x1801771e3  jl      short loc_18017716C
0x1801771e5  mov     rdi, [rbp+57h+var_78]
0x1801771e9  mov     r14, [rbp+57h+arg_0]
0x1801771ed  mov     r13, [rbp+57h+var_70]
0x1801771f1  mov     rdx, qword ptr [rbp+57h+bmp.bmType]; h
0x1801771f5  mov     hBmp, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801771f9  call    cs:__imp_SelectObject
0x1801771ff  mov     rdx, rdi; h
0x180177202  mov     hBmp, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180177206  call    cs:__imp_SelectObject
0x18017720c  mov     hBmp, [r14]; ho
0x18017720f  call    cs:__imp_DeleteObject
0x180177215  mov     [r14], r13
0x180177218  mov     ebx, 1
0x18017721d  lea     hBmp, [rbp+57h+memDCDst.m_hDC]; this
0x180177221  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x180177226  nop
0x180177227  lea     hBmp, [rbp+57h+memDCSrc.m_hDC]; this
0x18017722b  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x180177230  mov     eax, ebx
0x180177232  jmp     short loc_180177236
0x180177234  xor     eax, eax
0x180177236  add     rsp, 0D8h
0x18017723d  pop     r15
0x18017723f  pop     r14
0x180177241  pop     r13
0x180177243  pop     r12
0x180177245  pop     rdi
0x180177246  pop     rsi
0x180177247  pop     rbx
0x180177248  pop     rbp
0x180177249  retn
```
