# DibDraw(void *,HDC__ *,_RECTL const *)

- ea: `0x1800a16c8`
- end: `0x1800a193a`
- name: `?DibDraw@@YAJPEAXPEAUHDC__@@PEBU_RECTL@@@Z`
- size: `626`
- prototype: `HRESULT __fastcall(void *hDib, HDC__ *hdc, const _RECTL *lprc)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a1a60`

## callees

- `0x1800a0248`
- `0x1800a16c8`
- `0x1800a1998`
- `0x1800adaac`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x1800a1910`
- `KERNELBASE!GlobalFree` at `0x1800a1910`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a17c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a18a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a17c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a18a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a1713`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a1713`
- `GDI32!StretchDIBits` at `0x1800a1878`
- `GDI32!StretchDIBits` at `0x1800a1878`
- `GDI32!RealizePalette` at `0x1800a17f8`
- `GDI32!RealizePalette` at `0x1800a17f8`
- `GDI32!CreatePalette` at `0x1800a17a7`
- `GDI32!CreatePalette` at `0x1800a17a7`
- `GDI32!DeleteObject` at `0x1800a18fc`
- `GDI32!DeleteObject` at `0x1800a18fc`
- `GDI32!GetStockObject` at `0x1800a18c8`
- `GDI32!GetStockObject` at `0x1800a18c8`
- `GDI32!SelectPalette` at `0x1800a17dd`
- `GDI32!SelectPalette` at `0x1800a18e8`
- `GDI32!SelectPalette` at `0x1800a17dd`
- `GDI32!SelectPalette` at `0x1800a18e8`

## pseudocode

```c
__int64 __fastcall DibDraw(void *hDib, HDC hdc, const _RECTL *lprc)
{
  int v3; // r13d
  unsigned int v5; // ebx
  HPALETTE Palette; // rsi
  void *LogPalette; // r14
  HPALETTE StockObject; // rbp
  int v9; // r15d
  tagBITMAPINFOHEADER *v11; // rax
  tagBITMAPINFOHEADER *lpbmi; // rdi
  unsigned __int64 v13; // rax
  unsigned __int16 biWidth; // [rsp+70h] [rbp-58h]
  tagLOGPALETTE *lpLogPalette; // [rsp+78h] [rbp-50h] BYREF
  unsigned __int64 v16; // [rsp+80h] [rbp-48h]
  unsigned __int16 biHeight; // [rsp+E8h] [rbp+20h]

  v3 = 0;
  lpLogPalette = 0;
  v5 = -2147221184;
  Palette = 0;
  LogPalette = 0;
  StockObject = 0;
  v9 = 0;
  if ( !hDib )
    return 2147745799LL;
  v11 = (tagBITMAPINFOHEADER *)GlobalLock(hDib);
  lpbmi = v11;
  if ( !v11 )
    return 2147942414LL;
  if ( v11->biSize != 40 )
  {
    v5 = -2147467259;
    if ( v11->biSize == 12 )
      v5 = -2147221399;
    goto $errRtn_137;
  }
  v13 = UtPaletteSize(v11);
  biWidth = lpbmi->biWidth;
  LOBYTE(v3) = lpbmi->biBitCount < 0x10u;
  biHeight = lpbmi->biHeight;
  v16 = v13;
  if ( !(_WORD)v13 || lpbmi->biBitCount >= 0x10u )
  {
LABEL_13:
    v9 = v3;
    v5 = StretchDIBits(
           hdc,
           lprc->left,
           lprc->top,
           lprc->right - lprc->left,
           lprc->bottom - lprc->top,
           0,
           0,
           biWidth,
           biHeight,
           (char *)&lpbmi[1] + (unsigned __int16)v13,
           (const BITMAPINFO *)lpbmi,
           0,
           0xCC0020u) == 0
       ? 0x80040140
       : 0;
    goto $errRtn_137;
  }
  LogPalette = DibMakeLogPalette((unsigned __int8 *)&lpbmi[1], v13, &lpLogPalette);
  if ( LogPalette )
  {
    Palette = CreatePalette(lpLogPalette);
    v9 = v3;
    if ( !Palette )
      goto $errRtn_137;
    GlobalUnlock(LogPalette);
    StockObject = SelectPalette(hdc, Palette, 1);
    if ( !StockObject )
      goto $errRtn_137;
    RealizePalette(hdc);
    LOWORD(v13) = v16;
    goto LABEL_13;
  }
  v5 = -2147024882;
  v9 = v3;
$errRtn_137:
  GlobalUnlock(hDib);
  if ( v9 )
  {
    if ( OleIsDcMeta(hdc) )
      StockObject = (HPALETTE)GetStockObject(15);
    if ( StockObject )
      SelectPalette(hdc, StockObject, 1);
    if ( Palette )
      DeleteObject(Palette);
    if ( LogPalette )
      GlobalFree(LogPalette);
  }
  return v5;
}

```

## disassembly

```asm
0x1800a16c8  mov     rax, rsp
0x1800a16cb  mov     [rax+10h], rbx
0x1800a16cf  mov     [rax+18h], lprc
0x1800a16d3  mov     [rax+8], hDib
0x1800a16d7  push    rbp
0x1800a16d8  push    rsi
0x1800a16d9  push    rdi
0x1800a16da  push    r12
0x1800a16dc  push    r13
0x1800a16de  push    r14
0x1800a16e0  push    r15
0x1800a16e2  sub     rsp, 90h
0x1800a16e9  xor     r13d, r13d
0x1800a16ec  mov     r12, hdc
0x1800a16ef  mov     [rax-50h], r13
0x1800a16f3  mov     ebx, 80040140h
0x1800a16f8  mov     esi, r13d
0x1800a16fb  mov     r14d, r13d
0x1800a16fe  mov     ebp, r13d
0x1800a1701  mov     r15d, r13d
0x1800a1704  test    hDib, hDib
0x1800a1707  jnz     short loc_1800A1713
0x1800a1709  mov     eax, 80040007h
0x1800a170e  jmp     loc_1800A191E
0x1800a1713  call    cs:__imp_GlobalLock
0x1800a171a  nop     dword ptr [rax+rax+00h]
0x1800a171f  mov     rdi, rax
0x1800a1722  test    rax, rax
0x1800a1725  jnz     short loc_1800A1731
0x1800a1727  mov     eax, 8007000Eh
0x1800a172c  jmp     loc_1800A191E
0x1800a1731  cmp     dword ptr [rax], 28h ; '('
0x1800a1734  jnz     loc_1800A188E
0x1800a173a  mov     hDib, rdi; pbmi
0x1800a173d  call    ?UtPaletteSize@@YA_KPEAUtagBITMAPINFOHEADER@@@Z; UtPaletteSize(tagBITMAPINFOHEADER *)
0x1800a1742  movzx   ecx, word ptr [rdi+4]
0x1800a1746  cmp     word ptr [rdi+0Eh], 10h
0x1800a174b  mov     [rsp+0C8h+var_58], cx
0x1800a1750  movzx   ecx, word ptr [rdi+8]
0x1800a1754  setb    r13b
0x1800a1758  mov     [rsp+0C8h+arg_18], cx
0x1800a1760  mov     [rsp+0C8h+var_48], rax
0x1800a1768  test    ax, ax
0x1800a176b  jz      loc_1800A180C
0x1800a1771  cmp     word ptr [rdi+0Eh], 10h
0x1800a1776  jnb     loc_1800A180C
0x1800a177c  lea     hDib, [rdi+28h]; lpColorData
0x1800a1780  movzx   edx, ax; wDataSize
0x1800a1783  lea     lprc, [rsp+0C8h+lpLogPalette]; lplpLogPalette
0x1800a1788  call    ?DibMakeLogPalette@@YAPEAXPEAEGPEAPEAUtagLOGPALETTE@@@Z; DibMakeLogPalette(uchar *,ushort,tagLOGPALETTE * *)
0x1800a178d  mov     r14, rax
0x1800a1790  test    rax, rax
0x1800a1793  jnz     short loc_1800A17A2
0x1800a1795  mov     ebx, 8007000Eh
0x1800a179a  mov     r15d, r13d
0x1800a179d  jmp     $errRtn_137
0x1800a17a2  mov     hDib, [rsp+0C8h+lpLogPalette]; plpal
0x1800a17a7  call    cs:__imp_CreatePalette
0x1800a17ae  nop     dword ptr [rax+rax+00h]
0x1800a17b3  mov     rsi, rax
0x1800a17b6  mov     r15d, r13d
0x1800a17b9  test    rax, rax
0x1800a17bc  jz      $errRtn_137
0x1800a17c2  mov     hDib, r14; hMem
0x1800a17c5  call    cs:__imp_GlobalUnlock
0x1800a17cc  nop     dword ptr [rax+rax+00h]
0x1800a17d1  mov     r8d, 1; bForceBkgd
0x1800a17d7  mov     hdc, rsi; hPal
0x1800a17da  mov     hDib, r12; hdc
0x1800a17dd  call    cs:__imp_SelectPalette
0x1800a17e4  nop     dword ptr [rax+rax+00h]
0x1800a17e9  mov     rbp, rax
0x1800a17ec  test    rax, rax
0x1800a17ef  jz      $errRtn_137
0x1800a17f5  mov     hDib, r12; hdc
0x1800a17f8  call    cs:__imp_RealizePalette
0x1800a17ff  nop     dword ptr [rax+rax+00h]
0x1800a1804  mov     rax, [rsp+0C8h+var_48]
0x1800a180c  mov     hdc, [rsp+0C8h+arg_10]
0x1800a1814  mov     r15d, r13d
0x1800a1817  movzx   r10d, [rsp+0C8h+var_58]
0x1800a181d  xor     r13d, r13d
0x1800a1820  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1800a1828  mov     [rsp+0C8h+iUsage], r13d; iUsage
0x1800a182d  mov     r11d, [hdc+0Ch]
0x1800a1831  mov     r9d, [hdc+8]
0x1800a1835  mov     r8d, [hdc+4]; yDest
0x1800a1839  sub     r11d, r8d
0x1800a183c  sub     r9d, [hdc]; DestWidth
0x1800a183f  mov     edx, [hdc]; xDest
0x1800a1841  mov     [rsp+0C8h+lpbmi], rdi; lpbmi
0x1800a1846  movzx   ecx, ax
0x1800a1849  movzx   eax, [rsp+0C8h+arg_18]
0x1800a1851  add     hDib, 28h ; '('
0x1800a1855  add     hDib, rdi
0x1800a1858  mov     [rsp+0C8h+lpBits], hDib; lpBits
0x1800a185d  mov     hDib, r12; hdc
0x1800a1860  mov     [rsp+0C8h+SrcHeight], eax; SrcHeight
0x1800a1864  mov     [rsp+0C8h+SrcWidth], r10d; SrcWidth
0x1800a1869  mov     [rsp+0C8h+ySrc], r13d; ySrc
0x1800a186e  mov     [rsp+0C8h+xSrc], r13d; xSrc
0x1800a1873  mov     [rsp+0C8h+DestHeight], r11d; DestHeight
0x1800a1878  call    cs:__imp_StretchDIBits
0x1800a187f  nop     dword ptr [rax+rax+00h]
0x1800a1884  neg     eax
0x1800a1886  sbb     ecx, ecx
0x1800a1888  not     ecx
0x1800a188a  and     ebx, ecx
0x1800a188c  jmp     short $errRtn_137
0x1800a188e  cmp     dword ptr [rdi], 0Ch
0x1800a1891  mov     ebx, 80004005h
0x1800a1896  mov     eax, 80040069h
0x1800a189b  cmovz   ebx, eax
0x1800a189e  mov     hDib, [rsp+0C8h+hMem]; hMem
0x1800a18a6  call    cs:__imp_GlobalUnlock
0x1800a18ad  nop     dword ptr [rax+rax+00h]
0x1800a18b2  test    r15d, r15d
0x1800a18b5  jz      short loc_1800A191C
0x1800a18b7  mov     hDib, r12; hdc
0x1800a18ba  call    OleIsDcMeta
0x1800a18bf  test    eax, eax
0x1800a18c1  jz      short loc_1800A18D7
0x1800a18c3  mov     ecx, 0Fh; i
0x1800a18c8  call    cs:__imp_GetStockObject
0x1800a18cf  nop     dword ptr [rax+rax+00h]
0x1800a18d4  mov     rbp, rax
0x1800a18d7  test    rbp, rbp
0x1800a18da  jz      short loc_1800A18F4
0x1800a18dc  mov     r8d, 1; bForceBkgd
0x1800a18e2  mov     hdc, rbp; hPal
0x1800a18e5  mov     hDib, r12; hdc
0x1800a18e8  call    cs:__imp_SelectPalette
0x1800a18ef  nop     dword ptr [rax+rax+00h]
0x1800a18f4  test    rsi, rsi
0x1800a18f7  jz      short loc_1800A1908
0x1800a18f9  mov     hDib, rsi; ho
0x1800a18fc  call    cs:__imp_DeleteObject
0x1800a1903  nop     dword ptr [rax+rax+00h]
0x1800a1908  test    r14, r14
0x1800a190b  jz      short loc_1800A191C
0x1800a190d  mov     hDib, r14; hMem
0x1800a1910  call    cs:__imp_GlobalFree
0x1800a1917  nop     dword ptr [rax+rax+00h]
0x1800a191c  mov     eax, ebx
0x1800a191e  mov     rbx, [rsp+0C8h+arg_8]
0x1800a1926  add     rsp, 90h
0x1800a192d  pop     r15
0x1800a192f  pop     r14
0x1800a1931  pop     r13
0x1800a1933  pop     r12
0x1800a1935  pop     rdi
0x1800a1936  pop     rsi
0x1800a1937  pop     rbp
0x1800a1938  retn
```
