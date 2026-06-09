# DDBToDIB

- ea: `0x18017603c`
- end: `0x18017632a`
- name: `DDBToDIB`
- size: `750`
- prototype: `void *__fastcall(HBITMAP__ *bitmap, unsigned int bitmap)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180175e00`

## callees

- `0x180175d10`
- `0x18017603c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18017613b`
- `KERNEL32!GlobalAlloc` at `0x18017613b`
- `KERNEL32!GlobalFree` at `0x1801762dc`
- `KERNEL32!GlobalFree` at `0x1801762dc`
- `KERNEL32!GlobalReAlloc` at `0x18017621e`
- `KERNEL32!GlobalReAlloc` at `0x18017621e`
- `GDI32!GetDIBits` at `0x1801761a2`
- `GDI32!GetDIBits` at `0x180176263`
- `GDI32!GetDIBits` at `0x1801761a2`
- `GDI32!GetDIBits` at `0x180176263`
- `GDI32!SelectPalette` at `0x180176124`
- `GDI32!SelectPalette` at `0x1801762ab`
- `GDI32!SelectPalette` at `0x1801762eb`
- `GDI32!SelectPalette` at `0x180176124`
- `GDI32!SelectPalette` at `0x1801762ab`
- `GDI32!SelectPalette` at `0x1801762eb`
- `GDI32!CreateBitmap` at `0x1801760f2`
- `GDI32!CreateBitmap` at `0x1801760f2`
- `GDI32!DeleteDC` at `0x1801762ce`
- `GDI32!DeleteDC` at `0x18017630e`
- `GDI32!DeleteDC` at `0x1801762ce`
- `GDI32!DeleteDC` at `0x18017630e`
- `GDI32!RealizePalette` at `0x180176130`
- `GDI32!RealizePalette` at `0x180176130`
- `GDI32!DeleteObject` at `0x1801762c5`
- `GDI32!DeleteObject` at `0x180176305`
- `GDI32!DeleteObject` at `0x1801762c5`
- `GDI32!DeleteObject` at `0x180176305`
- `GDI32!SelectObject` at `0x180176112`
- `GDI32!SelectObject` at `0x1801762bc`
- `GDI32!SelectObject` at `0x1801762fc`
- `GDI32!SelectObject` at `0x180176112`
- `GDI32!SelectObject` at `0x1801762bc`
- `GDI32!SelectObject` at `0x1801762fc`
- `GDI32!CreateCompatibleDC` at `0x1801760ce`
- `GDI32!CreateCompatibleDC` at `0x1801760ce`
- `GDI32!GetObjectW` at `0x18017607a`
- `GDI32!GetObjectW` at `0x18017607a`
- `GDI32!GetStockObject` at `0x180176060`
- `GDI32!GetStockObject` at `0x180176060`

## pseudocode

```c
tagBITMAPINFO *__fastcall DDBToDIB(HBITMAP bitmap, unsigned int a2)
{
  HPALETTE StockObject; // r14
  unsigned __int16 v4; // si
  UINT v5; // edi
  int v6; // ebp
  unsigned int v7; // r13d
  HDC CompatibleDC; // rbx
  HBITMAP v9; // rax
  HBITMAP v10; // r12
  HDC v11; // rcx
  HGDIOBJ v12; // rdi
  HPALETTE v13; // r15
  tagBITMAPINFO *lpbmi; // rax
  __m128i *v15; // r14
  UINT v16; // r8d
  __m128i v17; // xmm2
  unsigned int biSizeImage; // eax
  tagBITMAPINFO *v19; // rax
  tagBITMAPINFO *v20; // rsi
  __int64 v21; // r13
  void *v22; // rcx
  char *v23; // r14
  __int64 v24; // rbp
  __m128i v26; // [rsp+40h] [rbp-A8h]
  tagBITMAP bm; // [rsp+50h] [rbp-98h] BYREF
  tagBITMAPINFOHEADER bi; // [rsp+70h] [rbp-78h]
  UINT bmWidth; // [rsp+F8h] [rbp+10h]
  UINT v31; // [rsp+F8h] [rbp+10h]
  int cLines; // [rsp+100h] [rbp+18h]
  HBITMAP v33; // [rsp+108h] [rbp+20h]

  StockObject = (HPALETTE)GetStockObject(15);
  GetObjectW(bitmap, 32, &bm);
  bmWidth = bm.bmWidth;
  cLines = bm.bmHeight;
  v4 = bm.bmPlanes * bm.bmBitsPixel;
  v5 = (unsigned __int16)(bm.bmPlanes * bm.bmBitsPixel);
  v6 = 1 << (LOBYTE(bm.bmPlanes) * LOBYTE(bm.bmBitsPixel));
  if ( v6 > 256 || v4 == 32 )
    v6 = 0;
  v7 = 4 * v6 + 40;
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
    return 0;
  v9 = CreateBitmap(1, 1, 1u, v5, 0);
  v33 = v9;
  v10 = v9;
  v11 = CompatibleDC;
  if ( !v9 )
  {
LABEL_25:
    DeleteDC(v11);
    return 0;
  }
  v12 = SelectObject(CompatibleDC, v9);
  v13 = SelectPalette(CompatibleDC, StockObject, 0);
  RealizePalette(CompatibleDC);
  lpbmi = (tagBITMAPINFO *)GlobalAlloc(0, v7);
  v15 = (__m128i *)lpbmi;
  if ( !lpbmi )
  {
LABEL_22:
    SelectPalette(CompatibleDC, v13, 0);
    if ( v12 )
      SelectObject(CompatibleDC, v12);
    DeleteObject(v10);
    v11 = CompatibleDC;
    goto LABEL_25;
  }
  lpbmi->bmiHeader.biSize = 40;
  lpbmi->bmiHeader.biWidth = bmWidth;
  lpbmi->bmiHeader.biHeight = cLines;
  lpbmi->bmiHeader.biPlanes = 1;
  lpbmi->bmiHeader.biBitCount = v4;
  *(_QWORD *)&lpbmi->bmiHeader.biCompression = 0;
  *(_QWORD *)&lpbmi->bmiHeader.biXPelsPerMeter = 0;
  *(_QWORD *)&lpbmi->bmiHeader.biClrUsed = 0;
  GetDIBits(CompatibleDC, bitmap, 0, cLines, 0, lpbmi, 0);
  v16 = v15->m128i_u32[2];
  v17 = *v15;
  v31 = v16;
  v26 = *v15;
  *(__m128i *)&bi.biCompression = v15[1];
  if ( bi.biSizeImage )
    biSizeImage = bi.biSizeImage;
  else
    biSizeImage = v16
                * ((int)((v17.m128i_i32[1] * *(int *)((char *)&_mm_srli_si128(v17, 8).m128i_i32[1] + 2) + 31)
                       & 0xFFFFFFE0)
                 / 8);
  v19 = (tagBITMAPINFO *)GlobalReAlloc(v15, biSizeImage + v7, 2u);
  v20 = v19;
  if ( !v19 )
  {
    v22 = v15;
    goto LABEL_21;
  }
  v21 = v6;
  if ( !GetDIBits(CompatibleDC, bitmap, 0, v31, (char *)&v19->bmiHeader.biSize + 4 * v6 + v26.m128i_u32[0], v19, 0) )
  {
    v22 = v20;
LABEL_21:
    GlobalFree(v22);
    goto LABEL_22;
  }
  v23 = (char *)v20 + v20->bmiHeader.biSize;
  if ( v6 > 0 )
  {
    v24 = 0;
    do
    {
      *(_DWORD *)&v23[4 * v24] = CMFCToolBarImages::MapFromSysColor(*(_DWORD *)&v23[4 * v24], 1);
      ++v24;
    }
    while ( v24 < v21 );
    v10 = v33;
  }
  SelectPalette(CompatibleDC, v13, 0);
  if ( v12 )
    SelectObject(CompatibleDC, v12);
  DeleteObject(v10);
  DeleteDC(CompatibleDC);
  return v20;
}

```

## disassembly

```asm
0x18017603c  mov     [rsp+arg_8], edx
0x180176040  mov     [rsp+hbm], bitmap
0x180176045  push    rbx
0x180176046  push    rbp
0x180176047  push    rsi
0x180176048  push    rdi
0x180176049  push    r12
0x18017604b  push    r13
0x18017604d  push    r14
0x18017604f  push    r15
0x180176051  sub     rsp, 0A8h
0x180176058  mov     rbx, bitmap
0x18017605b  mov     ecx, 0Fh; i
0x180176060  call    cs:__imp_GetStockObject
0x180176066  mov     r12d, 20h ; ' '
0x18017606c  lea     r8, [rsp+0E8h+bm]; pv
0x180176071  mov     edx, r12d; c
0x180176074  mov     bitmap, rbx; h
0x180176077  mov     r14, rax
0x18017607a  call    cs:__imp_GetObjectW
0x180176080  mov     eax, [rsp+0E8h+bm.bmWidth]
0x180176084  lea     r15d, [r12-1Fh]
0x180176089  movzx   edx, [rsp+0E8h+bm.bmPlanes]
0x18017608e  mov     ebp, r15d
0x180176091  movzx   ecx, [rsp+0E8h+bm.bmBitsPixel]
0x180176096  imul    ecx, edx
0x180176099  mov     [rsp+0E8h+arg_8], eax
0x1801760a0  mov     eax, [rsp+0E8h+bm.bmHeight]
0x1801760a4  mov     [rsp+0E8h+cLines], eax
0x1801760ab  movzx   esi, cx
0x1801760ae  mov     ecx, esi
0x1801760b0  mov     edi, esi
0x1801760b2  shl     ebp, cl
0x1801760b4  cmp     ebp, 100h
0x1801760ba  jg      short loc_1801760C2
0x1801760bc  cmp     si, r12w
0x1801760c0  jnz     short loc_1801760C4
0x1801760c2  xor     ebp, ebp
0x1801760c4  xor     ecx, ecx; hdc
0x1801760c6  lea     r13d, ds:28h[rbp*4]
0x1801760ce  call    cs:__imp_CreateCompatibleDC
0x1801760d4  mov     rbx, rax
0x1801760d7  test    rax, rax
0x1801760da  jz      loc_180176314
0x1801760e0  and     [rsp+0E8h+lpvBits], 0
0x1801760e6  mov     r9d, edi; nBitCount
0x1801760e9  mov     r8d, r15d; nPlanes
0x1801760ec  mov     edx, r15d; nHeight
0x1801760ef  mov     ecx, r15d; nWidth
0x1801760f2  call    cs:__imp_CreateBitmap
0x1801760f8  mov     [rsp+0E8h+arg_18], rax
0x180176100  mov     r12, rax
0x180176103  mov     bitmap, rbx; hdc
0x180176106  test    rax, rax
0x180176109  jz      loc_18017630E
0x18017610f  mov     rdx, rax; h
0x180176112  call    cs:__imp_SelectObject
0x180176118  xor     r8d, r8d; bForceBkgd
0x18017611b  mov     rdx, r14; hPal
0x18017611e  mov     bitmap, rbx; hdc
0x180176121  mov     rdi, rax
0x180176124  call    cs:__imp_SelectPalette
0x18017612a  mov     bitmap, rbx; hdc
0x18017612d  mov     r15, rax
0x180176130  call    cs:__imp_RealizePalette
0x180176136  mov     edx, r13d; dwBytes
0x180176139  xor     ecx, ecx; uFlags
0x18017613b  call    cs:__imp_GlobalAlloc
0x180176141  xor     ecx, ecx
0x180176143  xor     r8d, r8d; start
0x180176146  mov     r14, rax
0x180176149  test    rax, rax
0x18017614c  jz      loc_1801762E5
0x180176152  mov     dword ptr [rax], 28h ; '('
0x180176158  mov     eax, [rsp+0E8h+arg_8]
0x18017615f  mov     [r14+4], eax
0x180176163  mov     eax, [rsp+0E8h+cLines]
0x18017616a  mov     r9d, eax; cLines
0x18017616d  mov     [r14+8], eax
0x180176171  mov     word ptr [r14+0Ch], 1
0x180176178  mov     [r14+0Eh], si
0x18017617d  mov     [r14+10h], bitmap
0x180176181  mov     [rsp+0E8h+usage], ecx; usage
0x180176185  mov     [r14+18h], bitmap
0x180176189  mov     [r14+20h], bitmap
0x18017618d  mov     rdx, [rsp+0E8h+hbm]; hbm
0x180176195  mov     [rsp+0E8h+lpbmi], r14; lpbmi
0x18017619a  mov     [rsp+0E8h+lpvBits], bitmap; lpvBits
0x18017619f  mov     bitmap, rbx; hdc
0x1801761a2  call    cs:__imp_GetDIBits
0x1801761a8  movups  xmm1, xmmword ptr [r14+10h]
0x1801761ad  mov     r8d, [r14+8]
0x1801761b1  movups  xmm2, xmmword ptr [r14]
0x1801761b5  mov     [rsp+0E8h+arg_8], r8d
0x1801761bd  movq    rax, xmm1
0x1801761c2  shr     rax, 20h
0x1801761c6  movups  [rsp+0E8h+var_A8], xmm2
0x1801761cb  movups  xmmword ptr [rsp+0E8h+bi.biCompression], xmm1
0x1801761d3  test    eax, eax
0x1801761d5  jnz     short loc_18017620A
0x1801761d7  movdqa  xmm0, xmm2
0x1801761db  movq    bitmap, xmm2
0x1801761e0  shr     bitmap, 20h
0x1801761e4  psrldq  xmm0, 8
0x1801761e9  movq    rax, xmm0
0x1801761ee  shr     rax, 30h
0x1801761f2  imul    eax, ecx
0x1801761f5  add     eax, 1Fh
0x1801761f8  and     eax, 0FFFFFFE0h
0x1801761fb  cdq
0x1801761fc  and     edx, 7
0x1801761ff  add     eax, edx
0x180176201  sar     eax, 3
0x180176204  imul    eax, r8d
0x180176208  jmp     short loc_180176211
0x18017620a  mov     eax, [rsp+0E8h+bi.biSizeImage]
0x180176211  lea     edx, [rax+r13]; dwBytes
0x180176215  mov     r8d, 2; uFlags
0x18017621b  mov     bitmap, r14; hMem
0x18017621e  call    cs:__imp_GlobalReAlloc
0x180176224  mov     rsi, rax
0x180176227  test    rax, rax
0x18017622a  jz      loc_1801762D9
0x180176230  and     [rsp+0E8h+usage], 0
0x180176235  xor     r8d, r8d; start
0x180176238  mov     ecx, dword ptr [rsp+0E8h+var_A8]
0x18017623c  mov     r9d, [rsp+0E8h+arg_8]; cLines
0x180176244  add     bitmap, rax
0x180176247  mov     [rsp+0E8h+lpbmi], rax; lpbmi
0x18017624c  movsxd  r13, ebp
0x18017624f  lea     rdx, [bitmap+r13*4]
0x180176253  mov     bitmap, rbx; hdc
0x180176256  mov     [rsp+0E8h+lpvBits], rdx; lpvBits
0x18017625b  mov     rdx, [rsp+0E8h+hbm]; hbm
0x180176263  call    cs:__imp_GetDIBits
0x180176269  test    eax, eax
0x18017626b  jnz     short loc_180176272
0x18017626d  mov     bitmap, rsi
0x180176270  jmp     short loc_1801762DC
0x180176272  mov     r14d, [rsi]
0x180176275  add     r14, rsi
0x180176278  test    ebp, ebp
0x18017627a  jle     short loc_1801762A2
0x18017627c  xor     ebp, ebp
0x18017627e  lea     r12d, [rbp+1]
0x180176282  mov     ecx, [r14+rbp*4]; color
0x180176286  mov     edx, r12d; bUseRGBQUAD
0x180176289  call    ?MapFromSysColor@CMFCToolBarImages@@SAKKH@Z; CMFCToolBarImages::MapFromSysColor(ulong,int)
0x18017628e  mov     [r14+rbp*4], eax
0x180176292  add     rbp, r12
0x180176295  cmp     rbp, r13
0x180176298  jl      short loc_180176282
0x18017629a  mov     r12, [rsp+0E8h+arg_18]
0x1801762a2  xor     r8d, r8d; bForceBkgd
0x1801762a5  mov     rdx, r15; hPal
0x1801762a8  mov     bitmap, rbx; hdc
0x1801762ab  call    cs:__imp_SelectPalette
0x1801762b1  test    rdi, rdi
0x1801762b4  jz      short loc_1801762C2
0x1801762b6  mov     rdx, rdi; h
0x1801762b9  mov     bitmap, rbx; hdc
0x1801762bc  call    cs:__imp_SelectObject
0x1801762c2  mov     bitmap, r12; ho
0x1801762c5  call    cs:__imp_DeleteObject
0x1801762cb  mov     bitmap, rbx; hdc
0x1801762ce  call    cs:__imp_DeleteDC
0x1801762d4  mov     rax, rsi
0x1801762d7  jmp     short loc_180176316
0x1801762d9  mov     bitmap, r14; hMem
0x1801762dc  call    cs:__imp_GlobalFree
0x1801762e2  xor     r8d, r8d; bForceBkgd
0x1801762e5  mov     rdx, r15; hPal
0x1801762e8  mov     bitmap, rbx; hdc
0x1801762eb  call    cs:__imp_SelectPalette
0x1801762f1  test    rdi, rdi
0x1801762f4  jz      short loc_180176302
0x1801762f6  mov     rdx, rdi; h
0x1801762f9  mov     bitmap, rbx; hdc
0x1801762fc  call    cs:__imp_SelectObject
0x180176302  mov     bitmap, r12; ho
0x180176305  call    cs:__imp_DeleteObject
0x18017630b  mov     bitmap, rbx; hdc
0x18017630e  call    cs:__imp_DeleteDC
0x180176314  xor     eax, eax
0x180176316  add     rsp, 0A8h
0x18017631d  pop     r15
0x18017631f  pop     r14
0x180176321  pop     r13
0x180176323  pop     r12
0x180176325  pop     rdi
0x180176326  pop     rsi
0x180176327  pop     rbp
0x180176328  pop     rbx
0x180176329  retn
```
