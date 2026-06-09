# DibDraw(void *,HDC__ *,_RECTL const *)

- ea: `0x18009e62c`
- end: `0x18009e87a`
- name: `?DibDraw@@YAJPEAXPEAUHDC__@@PEBU_RECTL@@@Z`
- size: `590`
- prototype: `HRESULT __fastcall(void *hDib, HDC__ *hdc, const _RECTL *lprc)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009e900`

## callees

- `0x18009d45c`
- `0x18009e62c`
- `0x18009e880`
- `0x1800a68f0`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18009e6e5`
- `KERNELBASE!GlobalAlloc` at `0x18009e6e5`
- `KERNELBASE!GlobalFree` at `0x18009e70d`
- `KERNELBASE!GlobalFree` at `0x18009e857`
- `KERNELBASE!GlobalFree` at `0x18009e70d`
- `KERNELBASE!GlobalFree` at `0x18009e857`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009e748`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009e806`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009e748`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009e806`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009e65f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009e6fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009e65f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009e6fc`
- `GDI32!StretchDIBits` at `0x18009e7e0`
- `GDI32!StretchDIBits` at `0x18009e7e0`
- `GDI32!RealizePalette` at `0x18009e76f`
- `GDI32!RealizePalette` at `0x18009e76f`
- `GDI32!CreatePalette` at `0x18009e733`
- `GDI32!CreatePalette` at `0x18009e733`
- `GDI32!DeleteObject` at `0x18009e849`
- `GDI32!DeleteObject` at `0x18009e849`
- `GDI32!GetStockObject` at `0x18009e821`
- `GDI32!GetStockObject` at `0x18009e821`
- `GDI32!SelectPalette` at `0x18009e75a`
- `GDI32!SelectPalette` at `0x18009e83b`
- `GDI32!SelectPalette` at `0x18009e75a`
- `GDI32!SelectPalette` at `0x18009e83b`

## pseudocode

```c
__int64 __fastcall DibDraw(void *hDib, HDC hdc, const _RECTL *lprc)
{
  tagBITMAPINFOHEADER *v6; // rax
  tagBITMAPINFOHEADER *lpbmi; // r14
  HPALETTE Palette; // r15
  HGLOBAL v9; // rbx
  HPALETTE StockObject; // rbp
  unsigned __int16 v11; // ax
  unsigned int v12; // edi
  BOOL v13; // esi
  int v14; // ecx
  tagLOGPALETTE *v15; // rax
  const LOGPALETTE *v16; // r9
  int v17; // [rsp+70h] [rbp-48h]
  unsigned __int16 v18; // [rsp+78h] [rbp-40h]
  unsigned __int16 biHeight; // [rsp+C0h] [rbp+8h]
  unsigned __int16 biWidth; // [rsp+D8h] [rbp+20h]

  if ( !hDib )
    return 2147745799LL;
  v6 = (tagBITMAPINFOHEADER *)GlobalLock(hDib);
  lpbmi = v6;
  if ( !v6 )
    return 2147942414LL;
  Palette = 0;
  v9 = 0;
  StockObject = 0;
  if ( v6->biSize != 40 )
  {
    v13 = 0;
    v12 = -2147467259;
    if ( v6->biSize == 12 )
      v12 = -2147221399;
    goto $errRtn_153;
  }
  v11 = UtPaletteSize(v6);
  v12 = -2147221184;
  biWidth = lpbmi->biWidth;
  v13 = lpbmi->biBitCount < 0x10u;
  biHeight = lpbmi->biHeight;
  v14 = v11;
  v17 = v11;
  v18 = v11;
  if ( !v11 || lpbmi->biBitCount >= 0x10u )
    goto LABEL_16;
  v9 = GlobalAlloc(2u, (unsigned int)v11 + 4);
  if ( v9 )
  {
    v15 = (tagLOGPALETTE *)GlobalLock(v9);
    if ( !v15 )
    {
      GlobalFree(v9);
      v9 = 0;
      goto LABEL_12;
    }
    DibFillPaletteEntries((unsigned __int8 *)&lpbmi[1], v18, v15);
    Palette = CreatePalette(v16);
    if ( !Palette )
      goto $errRtn_153;
    GlobalUnlock(v9);
    StockObject = SelectPalette(hdc, Palette, 1);
    if ( !StockObject )
      goto $errRtn_153;
    RealizePalette(hdc);
    v14 = v17;
LABEL_16:
    v12 = StretchDIBits(
            hdc,
            lprc->left,
            lprc->top,
            lprc->right - lprc->left,
            lprc->bottom - lprc->top,
            0,
            0,
            biWidth,
            biHeight,
            (char *)lpbmi + (unsigned int)(v14 + 40),
            (const BITMAPINFO *)lpbmi,
            0,
            0xCC0020u) == 0
        ? 0x80040140
        : 0;
    goto $errRtn_153;
  }
  v9 = 0;
LABEL_12:
  v12 = -2147024882;
$errRtn_153:
  GlobalUnlock(hDib);
  if ( v13 )
  {
    if ( OleIsDcMeta(hdc) )
      StockObject = (HPALETTE)GetStockObject(15);
    if ( StockObject )
      SelectPalette(hdc, StockObject, 1);
    if ( Palette )
      DeleteObject(Palette);
    if ( v9 )
      GlobalFree(v9);
  }
  return v12;
}

```

## disassembly

```asm
0x18009e62c  mov     [rsp+arg_8], rbx
0x18009e631  mov     [rsp+arg_10], lprc
0x18009e636  push    rbp
0x18009e637  push    rsi
0x18009e638  push    rdi
0x18009e639  push    r12
0x18009e63b  push    r13
0x18009e63d  push    r14
0x18009e63f  push    r15
0x18009e641  sub     rsp, 80h
0x18009e648  xor     edi, edi
0x18009e64a  mov     r12, hdc
0x18009e64d  mov     r13, hDib
0x18009e650  test    hDib, hDib
0x18009e653  jnz     short loc_18009E65F
0x18009e655  mov     eax, 80040007h
0x18009e65a  jmp     loc_18009E85F
0x18009e65f  call    cs:__imp_GlobalLock
0x18009e665  mov     r14, rax
0x18009e668  test    rax, rax
0x18009e66b  jnz     short loc_18009E677
0x18009e66d  mov     eax, 8007000Eh
0x18009e672  jmp     loc_18009E85F
0x18009e677  cmp     dword ptr [rax], 28h ; '('
0x18009e67a  mov     r15, rdi
0x18009e67d  mov     rbx, rdi
0x18009e680  mov     rbp, rdi
0x18009e683  jnz     loc_18009E7F0
0x18009e689  mov     hDib, r14; pbmi
0x18009e68c  call    ?UtPaletteSize@@YA_KPEAUtagBITMAPINFOHEADER@@@Z; UtPaletteSize(tagBITMAPINFOHEADER *)
0x18009e691  movzx   ecx, word ptr [r14+4]
0x18009e696  mov     esi, edi
0x18009e698  cmp     word ptr [r14+0Eh], 10h
0x18009e69e  mov     edi, 80040140h
0x18009e6a3  mov     [rsp+0B8h+arg_18], cx
0x18009e6ab  movzx   ecx, word ptr [r14+8]
0x18009e6b0  setb    sil
0x18009e6b4  mov     [rsp+0B8h+arg_0], cx
0x18009e6bc  movzx   ecx, ax
0x18009e6bf  mov     [rsp+0B8h+var_48], ecx
0x18009e6c3  mov     qword ptr [rsp+0B8h+var_40], rax
0x18009e6c8  test    ax, ax
0x18009e6cb  jz      loc_18009E779
0x18009e6d1  cmp     word ptr [r14+0Eh], 10h
0x18009e6d7  jnb     loc_18009E779
0x18009e6dd  lea     edx, [hDib+4]; dwBytes
0x18009e6e0  mov     ecx, 2; uFlags
0x18009e6e5  call    cs:__imp_GlobalAlloc
0x18009e6eb  mov     rbx, rax
0x18009e6ee  xor     eax, eax
0x18009e6f0  test    rbx, rbx
0x18009e6f3  jnz     short loc_18009E6F9
0x18009e6f5  mov     ebx, eax
0x18009e6f7  jmp     short loc_18009E715
0x18009e6f9  mov     hDib, rbx; hMem
0x18009e6fc  call    cs:__imp_GlobalLock
0x18009e702  mov     r9, rax
0x18009e705  test    rax, rax
0x18009e708  jnz     short loc_18009E71F
0x18009e70a  mov     hDib, rbx; hMem
0x18009e70d  call    cs:__imp_GlobalFree
0x18009e713  xor     ebx, ebx
0x18009e715  mov     edi, 8007000Eh
0x18009e71a  jmp     $errRtn_153
0x18009e71f  movzx   edx, [rsp+0B8h+var_40]; wDataSize
0x18009e724  lea     hDib, [r14+28h]; lpColorData
0x18009e728  mov     lprc, r9; lpLogPalette
0x18009e72b  call    ?DibFillPaletteEntries@@YAXPEAEGPEAUtagLOGPALETTE@@@Z; DibFillPaletteEntries(uchar *,ushort,tagLOGPALETTE *)
0x18009e730  mov     hDib, r9; plpal
0x18009e733  call    cs:__imp_CreatePalette
0x18009e739  mov     r15, rax
0x18009e73c  test    rax, rax
0x18009e73f  jz      $errRtn_153
0x18009e745  mov     hDib, rbx; hMem
0x18009e748  call    cs:__imp_GlobalUnlock
0x18009e74e  mov     r8d, 1; bForceBkgd
0x18009e754  mov     hdc, r15; hPal
0x18009e757  mov     hDib, r12; hdc
0x18009e75a  call    cs:__imp_SelectPalette
0x18009e760  mov     rbp, rax
0x18009e763  test    rax, rax
0x18009e766  jz      $errRtn_153
0x18009e76c  mov     hDib, r12; hdc
0x18009e76f  call    cs:__imp_RealizePalette
0x18009e775  mov     ecx, [rsp+0B8h+var_48]
0x18009e779  mov     hdc, [rsp+0B8h+arg_10]
0x18009e781  lea     r10d, [hDib+28h]
0x18009e785  movzx   eax, [rsp+0B8h+arg_0]
0x18009e78d  add     r10, r14
0x18009e790  movzx   ecx, [rsp+0B8h+arg_18]
0x18009e798  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x18009e7a0  mov     r11d, [hdc+0Ch]
0x18009e7a4  mov     r9d, [hdc+8]
0x18009e7a8  mov     r8d, [hdc+4]; yDest
0x18009e7ac  sub     r11d, r8d
0x18009e7af  sub     r9d, [hdc]; DestWidth
0x18009e7b2  mov     edx, [hdc]; xDest
0x18009e7b4  mov     [rsp+0B8h+iUsage], 0; iUsage
0x18009e7bc  mov     [rsp+0B8h+lpbmi], r14; lpbmi
0x18009e7c1  mov     [rsp+0B8h+lpBits], r10; lpBits
0x18009e7c6  mov     [rsp+0B8h+SrcHeight], eax; SrcHeight
0x18009e7ca  xor     eax, eax
0x18009e7cc  mov     [rsp+0B8h+SrcWidth], ecx; SrcWidth
0x18009e7d0  mov     hDib, r12; hdc
0x18009e7d3  mov     [rsp+0B8h+ySrc], eax; ySrc
0x18009e7d7  mov     [rsp+0B8h+xSrc], eax; xSrc
0x18009e7db  mov     [rsp+0B8h+DestHeight], r11d; DestHeight
0x18009e7e0  call    cs:__imp_StretchDIBits
0x18009e7e6  neg     eax
0x18009e7e8  sbb     ecx, ecx
0x18009e7ea  not     ecx
0x18009e7ec  and     edi, ecx
0x18009e7ee  jmp     short $errRtn_153
0x18009e7f0  cmp     dword ptr [r14], 0Ch
0x18009e7f4  mov     esi, edi
0x18009e7f6  mov     edi, 80004005h
0x18009e7fb  mov     eax, 80040069h
0x18009e800  cmovz   edi, eax
0x18009e803  mov     hDib, r13; hMem
0x18009e806  call    cs:__imp_GlobalUnlock
0x18009e80c  test    esi, esi
0x18009e80e  jz      short loc_18009E85D
0x18009e810  mov     hDib, r12; hdc
0x18009e813  call    OleIsDcMeta
0x18009e818  test    eax, eax
0x18009e81a  jz      short loc_18009E82A
0x18009e81c  mov     ecx, 0Fh; i
0x18009e821  call    cs:__imp_GetStockObject
0x18009e827  mov     rbp, rax
0x18009e82a  test    rbp, rbp
0x18009e82d  jz      short loc_18009E841
0x18009e82f  mov     r8d, 1; bForceBkgd
0x18009e835  mov     hdc, rbp; hPal
0x18009e838  mov     hDib, r12; hdc
0x18009e83b  call    cs:__imp_SelectPalette
0x18009e841  test    r15, r15
0x18009e844  jz      short loc_18009E84F
0x18009e846  mov     hDib, r15; ho
0x18009e849  call    cs:__imp_DeleteObject
0x18009e84f  test    rbx, rbx
0x18009e852  jz      short loc_18009E85D
0x18009e854  mov     hDib, rbx; hMem
0x18009e857  call    cs:__imp_GlobalFree
0x18009e85d  mov     eax, edi
0x18009e85f  mov     rbx, [rsp+0B8h+arg_8]
0x18009e867  add     rsp, 80h
0x18009e86e  pop     r15
0x18009e870  pop     r14
0x18009e872  pop     r13
0x18009e874  pop     r12
0x18009e876  pop     rdi
0x18009e877  pop     rsi
0x18009e878  pop     rbp
0x18009e879  retn
```
