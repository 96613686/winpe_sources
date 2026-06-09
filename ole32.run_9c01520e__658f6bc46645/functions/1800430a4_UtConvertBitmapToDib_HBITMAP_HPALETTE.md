# UtConvertBitmapToDib(HBITMAP__ *,HPALETTE__ *)

- ea: `0x1800430a4`
- end: `0x1800434ec`
- name: `?UtConvertBitmapToDib@@YAPEAXPEAUHBITMAP__@@PEAUHPALETTE__@@@Z`
- size: `1096`
- prototype: `void *__fastcall(HBITMAP__ *hBitmap, HPALETTE__ *hpal)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800371a0`
- `0x18008ce60`
- `0x1800a7804`

## callees

- `0x1800430a4`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180043150`
- `KERNELBASE!GlobalAlloc` at `0x18004326f`
- `KERNELBASE!GlobalAlloc` at `0x180043150`
- `KERNELBASE!GlobalAlloc` at `0x18004326f`
- `KERNELBASE!GlobalFree` at `0x1800431c1`
- `KERNELBASE!GlobalFree` at `0x18004330c`
- `KERNELBASE!GlobalFree` at `0x180043320`
- `KERNELBASE!GlobalFree` at `0x1800431c1`
- `KERNELBASE!GlobalFree` at `0x18004330c`
- `KERNELBASE!GlobalFree` at `0x180043320`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800433ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800433ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800431b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800432d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800433ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180043468`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800434a7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800431b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800432d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800433ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180043468`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800434a7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18004316b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180043286`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800433ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18004316b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180043286`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800433ee`
- `GDI32!GetDIBits` at `0x180043357`
- `GDI32!GetDIBits` at `0x180043457`
- `GDI32!GetDIBits` at `0x180043357`
- `GDI32!GetDIBits` at `0x180043457`
- `GDI32!RealizePalette` at `0x180043426`
- `GDI32!RealizePalette` at `0x180043426`
- `GDI32!CreatePalette` at `0x1800431a0`
- `GDI32!CreatePalette` at `0x1800431a0`
- `GDI32!DeleteObject` at `0x1800432f3`
- `GDI32!DeleteObject` at `0x1800432f3`
- `GDI32!GetObjectW` at `0x180043205`
- `GDI32!GetObjectW` at `0x180043205`
- `GDI32!GetDeviceCaps` at `0x18004311a`
- `GDI32!GetDeviceCaps` at `0x18004311a`
- `GDI32!GetStockObject` at `0x1800431e4`
- `GDI32!GetStockObject` at `0x1800431e4`
- `GDI32!SelectPalette` at `0x18004340f`
- `GDI32!SelectPalette` at `0x180043496`
- `GDI32!SelectPalette` at `0x18004340f`
- `GDI32!SelectPalette` at `0x180043496`
- `USER32!ReleaseDC` at `0x18004312d`
- `USER32!ReleaseDC` at `0x1800434c0`
- `USER32!ReleaseDC` at `0x18004312d`
- `USER32!ReleaseDC` at `0x1800434c0`
- `USER32!GetDC` at `0x1800430fc`
- `USER32!GetDC` at `0x1800432bb`
- `USER32!GetDC` at `0x1800430fc`
- `USER32!GetDC` at `0x1800432bb`

## pseudocode

```c
void *__fastcall UtConvertBitmapToDib(HBITMAP hBitmap, HPALETTE hpal)
{
  void *v2; // rsi
  BOOL v3; // r14d
  void *v4; // rdi
  HPALETTE Palette; // r15
  HDC DC; // rax
  HDC v8; // rbp
  __int16 DeviceCaps; // bx
  HGLOBAL v10; // rax
  void *v11; // rbx
  _DWORD *v12; // rax
  int v13; // ecx
  const LOGPALETTE *v14; // rdx
  _WORD *v15; // rax
  unsigned int v16; // r13d
  unsigned __int64 v17; // r14
  int v18; // ebp
  HGLOBAL v19; // rax
  tagBITMAPINFO *v20; // rax
  tagBITMAPINFO *lpbmi; // rbx
  HDC v22; // rax
  HDC v23; // r12
  unsigned __int64 v25; // rbp
  unsigned __int64 v26; // rcx
  SIZE_T v27; // rdx
  HGLOBAL v28; // rax
  void *v29; // r13
  tagBITMAPINFO *v30; // rbx
  int DIBits; // ebx
  tagBITMAP bm; // [rsp+48h] [rbp-60h] BYREF
  HPALETTE v34; // [rsp+C0h] [rbp+18h]
  int v35; // [rsp+C8h] [rbp+20h]

  v2 = 0;
  v3 = 0;
  v35 = 0;
  v4 = 0;
  Palette = hpal;
  memset(&bm, 0, sizeof(bm));
  if ( !hBitmap )
    return 0;
  if ( hpal )
    goto LABEL_11;
  DC = GetDC(0);
  v8 = DC;
  if ( !DC )
    return 0;
  DeviceCaps = GetDeviceCaps(DC, 38);
  ReleaseDC(0, v8);
  if ( (DeviceCaps & 0x100) != 0 )
  {
    v10 = GlobalAlloc(0x42u, 0x408u);
    v11 = v10;
    if ( v10 )
    {
      v12 = GlobalLock(v10);
      v13 = 0;
      v14 = (const LOGPALETTE *)v12;
      *v12 = 16777984;
      v15 = (_WORD *)v12 + 3;
      do
      {
        *(v15 - 1) = v13++;
        *v15 = 512;
        v15 += 2;
      }
      while ( v13 < 256 );
      Palette = CreatePalette(v14);
      GlobalUnlock(v11);
      GlobalFree(v11);
      if ( Palette )
      {
        v35 = 1;
        goto LABEL_11;
      }
    }
    return 0;
  }
  Palette = (HPALETTE)GetStockObject(15);
LABEL_11:
  if ( GetObjectW(hBitmap, 32, &bm) )
  {
    v16 = bm.bmPlanes * bm.bmBitsPixel;
    if ( ((bm.bmBitsPixel - 16) & 0xFFEF) != 0 )
    {
      if ( bm.bmBitsPixel == 24 )
        v17 = 40;
      else
        v17 = 4 * (1LL << v16) + 40;
      v18 = 0;
    }
    else
    {
      v18 = 3;
      v17 = 52;
    }
    v19 = GlobalAlloc(0x42u, (unsigned int)v17);
    v4 = v19;
    if ( !v19 )
      goto LABEL_22;
    v20 = (tagBITMAPINFO *)GlobalLock(v19);
    lpbmi = v20;
    if ( !v20 )
      goto LABEL_22;
    v20->bmiHeader.biSize = 40;
    v20->bmiHeader.biWidth = bm.bmWidth;
    v20->bmiHeader.biHeight = bm.bmHeight;
    v20->bmiHeader.biPlanes = 1;
    v20->bmiHeader.biBitCount = v16;
    v20->bmiHeader.biCompression = v18;
    v22 = GetDC(0);
    v23 = v22;
    if ( !v22 )
    {
      GlobalUnlock(v4);
LABEL_22:
      v3 = 0;
      goto LABEL_23;
    }
    GetDIBits(v22, hBitmap, 0, bm.bmHeight, 0, lpbmi, 0);
    LODWORD(v25) = lpbmi->bmiHeader.biSizeImage;
    if ( !(_DWORD)v25 )
    {
      v26 = v16 * (unsigned __int64)(unsigned int)bm.bmWidth;
      if ( v26 > 0xFFFFFFFF
        || (int)v26 + 31 < (unsigned int)v26
        || (v25 = (unsigned int)bm.bmHeight * ((unsigned __int64)(unsigned int)(v26 + 31) >> 3), v25 > 0xFFFFFFFF) )
      {
        GlobalUnlock(v4);
        goto LABEL_42;
      }
      lpbmi->bmiHeader.biSizeImage = v25;
    }
    GlobalUnlock(v4);
    v27 = v17 + (unsigned int)v25;
    if ( v27 >= v17 )
    {
      v28 = GlobalReAlloc(v4, v27, 2u);
      v2 = v28;
      v29 = v28;
      if ( v28 )
      {
        v4 = 0;
        v30 = (tagBITMAPINFO *)GlobalLock(v28);
        if ( v30 )
        {
          v34 = SelectPalette(v23, Palette, 0);
          RealizePalette(v23);
          DIBits = GetDIBits(v23, hBitmap, 0, LOWORD(v30->bmiHeader.biHeight), (char *)v30 + v17, v30, 0);
          GlobalUnlock(v29);
          v3 = DIBits != 0;
          if ( v34 )
            SelectPalette(v23, v34, 0);
          goto LABEL_43;
        }
      }
    }
LABEL_42:
    v3 = 0;
LABEL_43:
    ReleaseDC(0, v23);
  }
LABEL_23:
  if ( v35 )
    DeleteObject(Palette);
  if ( !v3 )
  {
    if ( v4 )
      GlobalFree(v4);
    if ( v2 )
    {
      GlobalFree(v2);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800430a4  mov     rax, rsp
0x1800430a7  mov     [rax+10h], rbx
0x1800430ab  mov     [rax+8], hBitmap
0x1800430af  push    rbp
0x1800430b0  push    rsi
0x1800430b1  push    rdi
0x1800430b2  push    r12
0x1800430b4  push    r13
0x1800430b6  push    r14
0x1800430b8  push    r15
0x1800430ba  sub     rsp, 70h
0x1800430be  xor     esi, esi
0x1800430c0  xor     r14d, r14d
0x1800430c3  and     [rsp+0A8h+arg_18], esi
0x1800430ca  xorps   xmm0, xmm0
0x1800430cd  xor     edi, edi
0x1800430cf  mov     dword ptr [rsp+0A8h+arg_10], r14d
0x1800430d7  mov     r15, hpal
0x1800430da  mov     r12, hBitmap
0x1800430dd  movups  xmmword ptr [rax-60h], xmm0
0x1800430e1  movups  xmmword ptr [rax-50h], xmm0
0x1800430e5  test    hBitmap, hBitmap
0x1800430e8  jz      loc_1800434D1
0x1800430ee  lea     ebp, [rdi+1]
0x1800430f1  test    hpal, hpal
0x1800430f4  jnz     loc_1800431F8
0x1800430fa  xor     ecx, ecx; hWnd
0x1800430fc  call    cs:__imp_GetDC
0x180043103  nop     dword ptr [rax+rax+00h]
0x180043108  mov     rbp, rax
0x18004310b  test    rax, rax
0x18004310e  jz      loc_1800434D1
0x180043114  lea     edx, [rdi+26h]; index
0x180043117  mov     hBitmap, rax; hdc
0x18004311a  call    cs:__imp_GetDeviceCaps
0x180043121  nop     dword ptr [rax+rax+00h]
0x180043126  mov     hpal, rbp; hDC
0x180043129  xor     ecx, ecx; hWnd
0x18004312b  mov     ebx, eax
0x18004312d  call    cs:__imp_ReleaseDC
0x180043134  nop     dword ptr [rax+rax+00h]
0x180043139  mov     r15d, 100h
0x18004313f  test    r15d, ebx
0x180043142  jz      loc_1800431DF
0x180043148  mov     edx, 408h; dwBytes
0x18004314d  lea     ecx, [rdi+42h]; uFlags
0x180043150  call    cs:__imp_GlobalAlloc
0x180043157  nop     dword ptr [rax+rax+00h]
0x18004315c  mov     rbx, rax
0x18004315f  test    rax, rax
0x180043162  jz      loc_1800434D1
0x180043168  mov     hBitmap, rax; hMem
0x18004316b  call    cs:__imp_GlobalLock
0x180043172  nop     dword ptr [rax+rax+00h]
0x180043177  xor     ecx, ecx
0x180043179  lea     ebp, [rdi+1]
0x18004317c  mov     hpal, rax
0x18004317f  mov     dword ptr [rax], 1000300h
0x180043185  add     rax, 6
0x180043189  mov     [rax-2], cx
0x18004318d  add     ecx, ebp
0x18004318f  mov     word ptr [rax], 200h
0x180043194  lea     rax, [rax+4]
0x180043198  cmp     ecx, r15d
0x18004319b  jl      short loc_180043189
0x18004319d  mov     hBitmap, hpal; plpal
0x1800431a0  call    cs:__imp_CreatePalette
0x1800431a7  nop     dword ptr [rax+rax+00h]
0x1800431ac  mov     hBitmap, rbx; hMem
0x1800431af  mov     r15, rax
0x1800431b2  call    cs:__imp_GlobalUnlock
0x1800431b9  nop     dword ptr [rax+rax+00h]
0x1800431be  mov     hBitmap, rbx; hMem
0x1800431c1  call    cs:__imp_GlobalFree
0x1800431c8  nop     dword ptr [rax+rax+00h]
0x1800431cd  test    r15, r15
0x1800431d0  jz      loc_1800434D1
0x1800431d6  mov     [rsp+0A8h+arg_18], ebp
0x1800431dd  jmp     short loc_1800431F8
0x1800431df  mov     ecx, 0Fh; i
0x1800431e4  call    cs:__imp_GetStockObject
0x1800431eb  nop     dword ptr [rax+rax+00h]
0x1800431f0  mov     r15, rax
0x1800431f3  mov     ebp, 1
0x1800431f8  lea     r8, [rsp+0A8h+bm]; pv
0x1800431fd  mov     edx, 20h ; ' '; c
0x180043202  mov     hBitmap, r12; h
0x180043205  call    cs:__imp_GetObjectW
0x18004320c  nop     dword ptr [rax+rax+00h]
0x180043211  test    eax, eax
0x180043213  jz      loc_1800432E6
0x180043219  movzx   ecx, [rsp+0A8h+bm.bmBitsPixel]
0x18004321e  mov     edx, 0FFEFh
0x180043223  movzx   eax, [rsp+0A8h+bm.bmPlanes]
0x180043228  mov     r13d, ecx
0x18004322b  imul    r13d, eax
0x18004322f  mov     r12d, 28h ; '('
0x180043235  lea     eax, [hBitmap-10h]
0x180043238  test    dx, ax
0x18004323b  jz      short loc_18004325E
0x18004323d  lea     eax, [r12-10h]
0x180043242  cmp     ax, cx
0x180043245  jnz     short loc_18004324E
0x180043247  mov     r14d, r12d
0x18004324a  xor     ebp, ebp
0x18004324c  jmp     short loc_180043267
0x18004324e  mov     ecx, r13d
0x180043251  shl     rbp, cl
0x180043254  lea     r14, ds:28h[rbp*4]
0x18004325c  jmp     short loc_18004324A
0x18004325e  mov     ebp, 3
0x180043263  lea     r14d, [rbp+31h]
0x180043267  mov     edx, r14d; dwBytes
0x18004326a  mov     ecx, 42h ; 'B'; uFlags
0x18004326f  call    cs:__imp_GlobalAlloc
0x180043276  nop     dword ptr [rax+rax+00h]
0x18004327b  mov     rdi, rax
0x18004327e  test    rax, rax
0x180043281  jz      short loc_1800432DE
0x180043283  mov     hBitmap, rax; hMem
0x180043286  call    cs:__imp_GlobalLock
0x18004328d  nop     dword ptr [rax+rax+00h]
0x180043292  mov     rbx, rax
0x180043295  test    rax, rax
0x180043298  jz      short loc_1800432DE
0x18004329a  mov     [rax], r12d
0x18004329d  mov     ecx, [rsp+0A8h+bm.bmWidth]
0x1800432a1  mov     [rax+4], ecx
0x1800432a4  mov     ecx, [rsp+0A8h+bm.bmHeight]
0x1800432a8  mov     [rax+8], ecx
0x1800432ab  xor     ecx, ecx; hWnd
0x1800432ad  mov     word ptr [rax+0Ch], 1
0x1800432b3  mov     [rax+0Eh], r13w
0x1800432b8  mov     [rax+10h], ebp
0x1800432bb  call    cs:__imp_GetDC
0x1800432c2  nop     dword ptr [rax+rax+00h]
0x1800432c7  mov     r12, rax
0x1800432ca  test    rax, rax
0x1800432cd  jnz     short loc_180043336
0x1800432cf  mov     hBitmap, rdi; hMem
0x1800432d2  call    cs:__imp_GlobalUnlock
0x1800432d9  nop     dword ptr [rax+rax+00h]
0x1800432de  mov     r14d, dword ptr [rsp+0A8h+arg_10]
0x1800432e6  cmp     [rsp+0A8h+arg_18], 0
0x1800432ee  jz      short loc_1800432FF
0x1800432f0  mov     hBitmap, r15; ho
0x1800432f3  call    cs:__imp_DeleteObject
0x1800432fa  nop     dword ptr [rax+rax+00h]
0x1800432ff  test    r14d, r14d
0x180043302  jnz     short loc_18004332E
0x180043304  test    rdi, rdi
0x180043307  jz      short loc_180043318
0x180043309  mov     hBitmap, rdi; hMem
0x18004330c  call    cs:__imp_GlobalFree
0x180043313  nop     dword ptr [rax+rax+00h]
0x180043318  test    rsi, rsi
0x18004331b  jz      short loc_18004332E
0x18004331d  mov     hBitmap, rsi; hMem
0x180043320  call    cs:__imp_GlobalFree
0x180043327  nop     dword ptr [rax+rax+00h]
0x18004332c  xor     esi, esi
0x18004332e  mov     rax, rsi
0x180043331  jmp     loc_1800434D3
0x180043336  and     [rsp+0A8h+var_78], esi
0x18004333a  xor     r8d, r8d; start
0x18004333d  mov     r9d, [rsp+0A8h+bm.bmHeight]; cLines
0x180043342  mov     hBitmap, r12; hdc
0x180043345  mov     hpal, [rsp+0A8h+hbm]; hbm
0x18004334d  mov     [rsp+0A8h+lpbmi], rbx; lpbmi
0x180043352  and     [rsp+0A8h+lpvBits], rsi
0x180043357  call    cs:__imp_GetDIBits
0x18004335e  nop     dword ptr [rax+rax+00h]
0x180043363  mov     ebp, [rbx+14h]
0x180043366  test    ebp, ebp
0x180043368  jnz     short loc_1800433A8
0x18004336a  mov     ecx, [rsp+0A8h+bm.bmWidth]
0x18004336e  mov     edx, 0FFFFFFFFh
0x180043373  mov     eax, r13d
0x180043376  imul    hBitmap, rax
0x18004337a  cmp     hBitmap, hpal
0x18004337d  ja      loc_1800434A4
0x180043383  lea     eax, [hBitmap+1Fh]
0x180043386  cmp     eax, ecx
0x180043388  jb      loc_1800434A4
0x18004338e  mov     ebp, eax
0x180043390  mov     eax, [rsp+0A8h+bm.bmHeight]
0x180043394  shr     rbp, 3
0x180043398  imul    rbp, rax
0x18004339c  cmp     rbp, hpal
0x18004339f  ja      loc_1800434A4
0x1800433a5  mov     [rbx+14h], ebp
0x1800433a8  mov     hBitmap, rdi; hMem
0x1800433ab  call    cs:__imp_GlobalUnlock
0x1800433b2  nop     dword ptr [rax+rax+00h]
0x1800433b7  mov     edx, ebp
0x1800433b9  add     hpal, r14; dwBytes
0x1800433bc  cmp     hpal, r14
0x1800433bf  jb      loc_1800434B3
0x1800433c5  mov     r8d, 2; uFlags
0x1800433cb  mov     hBitmap, rdi; hMem
0x1800433ce  call    cs:__imp_GlobalReAlloc
0x1800433d5  nop     dword ptr [rax+rax+00h]
0x1800433da  mov     rsi, rax
0x1800433dd  mov     r13, rax
0x1800433e0  test    rax, rax
0x1800433e3  jz      loc_1800434B3
0x1800433e9  mov     hBitmap, rax; hMem
0x1800433ec  xor     edi, edi
0x1800433ee  call    cs:__imp_GlobalLock
0x1800433f5  nop     dword ptr [rax+rax+00h]
0x1800433fa  mov     rbx, rax
0x1800433fd  test    rax, rax
0x180043400  jz      loc_1800434B3
0x180043406  xor     r8d, r8d; bForceBkgd
0x180043409  mov     hpal, r15; hPal
0x18004340c  mov     hBitmap, r12; hdc
0x18004340f  call    cs:__imp_SelectPalette
0x180043416  nop     dword ptr [rax+rax+00h]
0x18004341b  mov     hBitmap, r12; hdc
0x18004341e  mov     [rsp+0A8h+arg_10], rax
0x180043426  call    cs:__imp_RealizePalette
0x18004342d  nop     dword ptr [rax+rax+00h]
0x180043432  and     [rsp+0A8h+var_78], edi
0x180043436  lea     hBitmap, [rbx+r14]
0x18004343a  movzx   r9d, word ptr [rbx+8]; cLines
0x18004343f  xor     r8d, r8d; start
0x180043442  mov     hpal, [rsp+0A8h+hbm]; hbm
0x18004344a  mov     [rsp+0A8h+lpbmi], rbx; lpbmi
0x18004344f  mov     [rsp+0A8h+lpvBits], hBitmap; lpvBits
0x180043454  mov     hBitmap, r12; hdc
0x180043457  call    cs:__imp_GetDIBits
0x18004345e  nop     dword ptr [rax+rax+00h]
0x180043463  mov     hBitmap, r13; hMem
0x180043466  mov     ebx, eax
0x180043468  call    cs:__imp_GlobalUnlock
0x18004346f  nop     dword ptr [rax+rax+00h]
0x180043474  mov     rax, [rsp+0A8h+arg_10]
0x18004347c  xor     r14d, r14d
0x18004347f  test    ebx, ebx
0x180043481  mov     rbx, r12
0x180043484  setnz   r14b
0x180043488  test    rax, rax
0x18004348b  jz      short loc_1800434BB
0x18004348d  xor     r8d, r8d; bForceBkgd
0x180043490  mov     hpal, rax; hPal
0x180043493  mov     hBitmap, rbx; hdc
0x180043496  call    cs:__imp_SelectPalette
0x18004349d  nop     dword ptr [rax+rax+00h]
0x1800434a2  jmp     short loc_1800434BB
0x1800434a4  mov     hBitmap, rdi; hMem
0x1800434a7  call    cs:__imp_GlobalUnlock
0x1800434ae  nop     dword ptr [rax+rax+00h]
0x1800434b3  mov     r14d, dword ptr [rsp+0A8h+arg_10]
0x1800434bb  mov     hpal, r12; hDC
0x1800434be  xor     ecx, ecx; hWnd
0x1800434c0  call    cs:__imp_ReleaseDC
0x1800434c7  nop     dword ptr [rax+rax+00h]
0x1800434cc  jmp     loc_1800432E6
0x1800434d1  xor     eax, eax
0x1800434d3  mov     rbx, [rsp+0A8h+arg_8]
0x1800434db  add     rsp, 70h
0x1800434df  pop     r15
0x1800434e1  pop     r14
0x1800434e3  pop     r13
0x1800434e5  pop     r12
0x1800434e7  pop     rdi
0x1800434e8  pop     rsi
0x1800434e9  pop     rbp
0x1800434ea  retn
```
