# PictureFromDib

- ea: `0x18001597c`
- end: `0x180015b47`
- name: `PictureFromDib`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010578`

## callees

- `0x18001597c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015995`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015ab7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015995`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015ab7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015aa6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015aa6`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180015af1`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180015b16`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180015af1`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180015b16`
- `GDI32!SetStretchBltMode` at `0x180015a1a`
- `GDI32!SetStretchBltMode` at `0x180015a1a`
- `GDI32!SelectPalette` at `0x180015a03`
- `GDI32!SelectPalette` at `0x180015a8a`
- `GDI32!SelectPalette` at `0x180015a03`
- `GDI32!SelectPalette` at `0x180015a8a`
- `GDI32!GetStockObject` at `0x180015a7b`
- `GDI32!GetStockObject` at `0x180015a7b`
- `GDI32!StretchDIBits` at `0x180015a6b`
- `GDI32!StretchDIBits` at `0x180015a6b`
- `GDI32!RealizePalette` at `0x180015a0c`
- `GDI32!RealizePalette` at `0x180015a0c`
- `GDI32!CreateMetaFileW` at `0x1800159be`
- `GDI32!CreateMetaFileW` at `0x1800159be`
- `GDI32!DeleteMetaFile` at `0x180015b2f`
- `GDI32!DeleteMetaFile` at `0x180015b2f`
- `GDI32!SetWindowExtEx` at `0x1800159ef`
- `GDI32!SetWindowExtEx` at `0x1800159ef`
- `GDI32!SetWindowOrgEx` at `0x1800159db`
- `GDI32!SetWindowOrgEx` at `0x1800159db`
- `GDI32!CloseMetaFile` at `0x180015a93`
- `GDI32!CloseMetaFile` at `0x180015a93`
- `GDI32!GetDeviceCaps` at `0x180015ae1`
- `GDI32!GetDeviceCaps` at `0x180015b06`
- `GDI32!GetDeviceCaps` at `0x180015ae1`
- `GDI32!GetDeviceCaps` at `0x180015b06`
- `USER32!GetDC` at `0x180015ac2`
- `USER32!GetDC` at `0x180015ac2`
- `USER32!ReleaseDC` at `0x180015b24`
- `USER32!ReleaseDC` at `0x180015b24`

## pseudocode

```c
HGLOBAL __fastcall PictureFromDib(void *a1, HPALETTE a2)
{
  const BITMAPINFO *v3; // rax
  const BITMAPINFO *lpbmi; // r14
  WORD biBitCount; // cx
  HDC MetaFileW; // rax
  HDC v7; // rbx
  HPALETTE StockObject; // rax
  HMETAFILE v9; // rbx
  HGLOBAL v10; // rax
  HGLOBAL v11; // rbp
  _QWORD *v12; // rsi
  HDC DC; // rax
  int biWidth; // ebx
  HDC v15; // rdi
  int DeviceCaps; // eax
  int biHeight; // ebx
  int v18; // eax

  if ( !a1 )
    return 0;
  v3 = (const BITMAPINFO *)GlobalLock(a1);
  lpbmi = v3;
  if ( !v3->bmiHeader.biClrUsed )
  {
    biBitCount = v3->bmiHeader.biBitCount;
    if ( (unsigned __int16)(biBitCount - 1) <= 7u )
      v3->bmiHeader.biClrUsed = 1 << biBitCount;
  }
  MetaFileW = CreateMetaFileW(0);
  v7 = MetaFileW;
  if ( !MetaFileW )
    return 0;
  SetWindowOrgEx(MetaFileW, 0, 0, 0);
  SetWindowExtEx(v7, lpbmi->bmiHeader.biWidth, lpbmi->bmiHeader.biHeight, 0);
  if ( a2 )
  {
    SelectPalette(v7, a2, 0);
    RealizePalette(v7);
  }
  SetStretchBltMode(v7, 3);
  StretchDIBits(
    v7,
    0,
    0,
    lpbmi->bmiHeader.biWidth,
    lpbmi->bmiHeader.biHeight,
    0,
    0,
    lpbmi->bmiHeader.biWidth,
    lpbmi->bmiHeader.biHeight,
    (char *)&lpbmi->bmiHeader.biSize + 4 * (int)lpbmi->bmiHeader.biClrUsed + (int)lpbmi->bmiHeader.biSize,
    lpbmi,
    0,
    0xCC0020u);
  if ( a2 )
  {
    StockObject = (HPALETTE)GetStockObject(15);
    SelectPalette(v7, StockObject, 0);
  }
  v9 = CloseMetaFile(v7);
  v10 = GlobalAlloc(0x2002u, 0x18u);
  v11 = v10;
  if ( v10 )
  {
    v12 = GlobalLock(v10);
    DC = GetDC(0);
    *(_DWORD *)v12 = 8;
    v12[2] = v9;
    biWidth = lpbmi->bmiHeader.biWidth;
    v15 = DC;
    DeviceCaps = GetDeviceCaps(DC, 88);
    *((_DWORD *)v12 + 1) = MulDiv(biWidth, 2540, DeviceCaps);
    biHeight = lpbmi->bmiHeader.biHeight;
    v18 = GetDeviceCaps(v15, 88);
    *((_DWORD *)v12 + 2) = MulDiv(biHeight, 2540, v18);
    ReleaseDC(0, v15);
  }
  else
  {
    DeleteMetaFile(v9);
  }
  return v11;
}

```

## disassembly

```asm
0x18001597c  push    rbx
0x18001597e  push    rbp
0x18001597f  push    rsi
0x180015980  push    rdi
0x180015981  push    r14
0x180015983  sub     rsp, 70h
0x180015987  xor     esi, esi
0x180015989  mov     rdi, rdx
0x18001598c  test    rcx, rcx
0x18001598f  jz      loc_180015B3A
0x180015995  call    cs:__imp_GlobalLock
0x18001599b  mov     r14, rax
0x18001599e  cmp     [rax+20h], esi
0x1800159a1  jnz     short loc_1800159BC
0x1800159a3  movzx   ecx, word ptr [rax+0Eh]
0x1800159a7  lea     eax, [rsi+1]
0x1800159aa  movzx   edx, cx
0x1800159ad  sub     dx, ax
0x1800159b0  cmp     dx, 7
0x1800159b4  ja      short loc_1800159BC
0x1800159b6  shl     eax, cl
0x1800159b8  mov     [r14+20h], eax
0x1800159bc  xor     ecx, ecx; pszFile
0x1800159be  call    cs:__imp_CreateMetaFileW
0x1800159c4  mov     rbx, rax
0x1800159c7  test    rax, rax
0x1800159ca  jz      loc_180015B3A
0x1800159d0  xor     r9d, r9d; lppt
0x1800159d3  xor     r8d, r8d; y
0x1800159d6  xor     edx, edx; x
0x1800159d8  mov     rcx, rax; hdc
0x1800159db  call    cs:__imp_SetWindowOrgEx
0x1800159e1  mov     r8d, [r14+8]; y
0x1800159e5  xor     r9d, r9d; lpsz
0x1800159e8  mov     edx, [r14+4]; x
0x1800159ec  mov     rcx, rbx; hdc
0x1800159ef  call    cs:__imp_SetWindowExtEx
0x1800159f5  test    rdi, rdi
0x1800159f8  jz      short loc_180015A12
0x1800159fa  xor     r8d, r8d; bForceBkgd
0x1800159fd  mov     rdx, rdi; hPal
0x180015a00  mov     rcx, rbx; hdc
0x180015a03  call    cs:__imp_SelectPalette
0x180015a09  mov     rcx, rbx; hdc
0x180015a0c  call    cs:__imp_RealizePalette
0x180015a12  mov     edx, 3; mode
0x180015a17  mov     rcx, rbx; hdc
0x180015a1a  call    cs:__imp_SetStretchBltMode
0x180015a20  mov     r8d, [r14+8]
0x180015a24  movsxd  rdx, dword ptr [r14+20h]
0x180015a28  movsxd  rcx, dword ptr [r14]
0x180015a2b  mov     r9d, [r14+4]; DestWidth
0x180015a2f  add     rcx, r14
0x180015a32  mov     [rsp+98h+rop], 0CC0020h; rop
0x180015a3a  mov     [rsp+98h+iUsage], esi; iUsage
0x180015a3e  mov     [rsp+98h+lpbmi], r14; lpbmi
0x180015a43  lea     rax, [rcx+rdx*4]
0x180015a47  xor     edx, edx; xDest
0x180015a49  mov     [rsp+98h+lpBits], rax; lpBits
0x180015a4e  mov     rcx, rbx; hdc
0x180015a51  mov     [rsp+98h+SrcHeight], r8d; SrcHeight
0x180015a56  mov     [rsp+98h+SrcWidth], r9d; SrcWidth
0x180015a5b  mov     [rsp+98h+ySrc], esi; ySrc
0x180015a5f  mov     [rsp+98h+xSrc], esi; xSrc
0x180015a63  mov     [rsp+98h+DestHeight], r8d; DestHeight
0x180015a68  xor     r8d, r8d; yDest
0x180015a6b  call    cs:__imp_StretchDIBits
0x180015a71  test    rdi, rdi
0x180015a74  jz      short loc_180015A90
0x180015a76  mov     ecx, 0Fh; i
0x180015a7b  call    cs:__imp_GetStockObject
0x180015a81  xor     r8d, r8d; bForceBkgd
0x180015a84  mov     rcx, rbx; hdc
0x180015a87  mov     rdx, rax; hPal
0x180015a8a  call    cs:__imp_SelectPalette
0x180015a90  mov     rcx, rbx; hdc
0x180015a93  call    cs:__imp_CloseMetaFile
0x180015a99  mov     edx, 18h; dwBytes
0x180015a9e  mov     ecx, 2002h; uFlags
0x180015aa3  mov     rbx, rax
0x180015aa6  call    cs:__imp_GlobalAlloc
0x180015aac  mov     rbp, rax
0x180015aaf  test    rax, rax
0x180015ab2  jz      short loc_180015B2C
0x180015ab4  mov     rcx, rax; hMem
0x180015ab7  call    cs:__imp_GlobalLock
0x180015abd  xor     ecx, ecx; hWnd
0x180015abf  mov     rsi, rax
0x180015ac2  call    cs:__imp_GetDC
0x180015ac8  mov     dword ptr [rsi], 8
0x180015ace  mov     edx, 58h ; 'X'; index
0x180015ad3  mov     [rsi+10h], rbx
0x180015ad7  mov     rcx, rax; hdc
0x180015ada  mov     ebx, [r14+4]
0x180015ade  mov     rdi, rax
0x180015ae1  call    cs:__imp_GetDeviceCaps
0x180015ae7  mov     edx, 9ECh; nNumerator
0x180015aec  mov     ecx, ebx; nNumber
0x180015aee  mov     r8d, eax; nDenominator
0x180015af1  call    cs:__imp_MulDiv
0x180015af7  mov     [rsi+4], eax
0x180015afa  mov     edx, 58h ; 'X'; index
0x180015aff  mov     ebx, [r14+8]
0x180015b03  mov     rcx, rdi; hdc
0x180015b06  call    cs:__imp_GetDeviceCaps
0x180015b0c  mov     edx, 9ECh; nNumerator
0x180015b11  mov     ecx, ebx; nNumber
0x180015b13  mov     r8d, eax; nDenominator
0x180015b16  call    cs:__imp_MulDiv
0x180015b1c  mov     rdx, rdi; hDC
0x180015b1f  xor     ecx, ecx; hWnd
0x180015b21  mov     [rsi+8], eax
0x180015b24  call    cs:__imp_ReleaseDC
0x180015b2a  jmp     short loc_180015B35
0x180015b2c  mov     rcx, rbx; hmf
0x180015b2f  call    cs:__imp_DeleteMetaFile
0x180015b35  mov     rax, rbp
0x180015b38  jmp     short loc_180015B3C
0x180015b3a  xor     eax, eax
0x180015b3c  add     rsp, 70h
0x180015b40  pop     r14
0x180015b42  pop     rdi
0x180015b43  pop     rsi
0x180015b44  pop     rbp
0x180015b45  pop     rbx
0x180015b46  retn
```
