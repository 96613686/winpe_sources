# XHDC::StretchBlt(int,int,int,int,XHDC const &,int,int,int,int,ulong)

- ea: `0x180b2fde0`
- end: `0x180b3036e`
- name: `?StretchBlt@XHDC@@QEBAHHHHHAEBV1@HHHHK@Z`
- size: `1422`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, const struct XHDC *, int, int, int, int cy, DWORD rop)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180b2d1a8`
- `0x180b30374`

## callees

- `0x1801bf528`
- `0x1801c0b08`
- `0x18043c328`
- `0x180b2f394`
- `0x180b2f524`
- `0x180b2f6ac`
- `0x180b2fde0`
- `0x180b32a60`
- `0x180b32bd0`
- `0x180b48564`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180b30331`
- `GDI32!DeleteDC` at `0x180b30331`
- `GDI32!SetDIBits` at `0x180b3024e`
- `GDI32!SetDIBits` at `0x180b3024e`
- `GDI32!StretchBlt` at `0x180b2ff33`
- `GDI32!StretchBlt` at `0x180b302bc`
- `GDI32!StretchBlt` at `0x180b2ff33`
- `GDI32!StretchBlt` at `0x180b302bc`
- `GDI32!DeleteObject` at `0x180b30315`
- `GDI32!DeleteObject` at `0x180b30323`
- `GDI32!DeleteObject` at `0x180b30315`
- `GDI32!DeleteObject` at `0x180b30323`
- `GDI32!SelectObject` at `0x180b3007b`
- `GDI32!SelectObject` at `0x180b300bb`
- `GDI32!SelectObject` at `0x180b30307`
- `GDI32!SelectObject` at `0x180b3007b`
- `GDI32!SelectObject` at `0x180b300bb`
- `GDI32!SelectObject` at `0x180b30307`
- `GDI32!BitBlt` at `0x180b300af`
- `GDI32!BitBlt` at `0x180b300af`
- `GDI32!CreateCompatibleBitmap` at `0x180b3001b`
- `GDI32!CreateCompatibleBitmap` at `0x180b30040`
- `GDI32!CreateCompatibleBitmap` at `0x180b3001b`
- `GDI32!CreateCompatibleBitmap` at `0x180b30040`
- `GDI32!CreateCompatibleDC` at `0x180b3004c`
- `GDI32!CreateCompatibleDC` at `0x180b3004c`
- `GDI32!GetObjectW` at `0x180b300d6`
- `GDI32!GetObjectW` at `0x180b300e6`
- `GDI32!GetObjectW` at `0x180b300d6`
- `GDI32!GetObjectW` at `0x180b300e6`

## pseudocode

```c
BOOL __fastcall XHDC::StretchBlt(
        HDC *this,
        int a2,
        int a3,
        int a4,
        int hDest,
        const struct XHDC *a6,
        int a7,
        int a8,
        int wSrc,
        int cy,
        DWORD rop)
{
  HDC hdcSrc; // r14
  const struct tagSIZE *OffsetOnly; // r12
  const struct tagSIZE *v15; // rax
  int cx; // ecx
  LONG v17; // eax
  int xSrc; // r12d
  int ySrc; // r13d
  int v21; // ebx
  int SurfaceFromDC; // ebx
  int v23; // r8d
  int v24; // edx
  HBITMAP CompatibleBitmap; // r15
  HDC CompatibleDC; // rdi
  HBITMAP v27; // r12
  char v28; // r14
  int v29; // r14d
  int v30; // r12d
  void *v31; // r8
  char v32; // [rsp+68h] [rbp-A0h]
  LONG ha; // [rsp+70h] [rbp-98h]
  int hb; // [rsp+70h] [rbp-98h]
  HBITMAP hc; // [rsp+70h] [rbp-98h]
  unsigned int wDesta; // [rsp+78h] [rbp-90h]
  int v39; // [rsp+80h] [rbp-88h] BYREF
  int v40; // [rsp+84h] [rbp-84h]
  int v41; // [rsp+88h] [rbp-80h]
  int v42; // [rsp+8Ch] [rbp-7Ch]
  int v43; // [rsp+90h] [rbp-78h]
  int v44; // [rsp+94h] [rbp-74h]
  int v45; // [rsp+98h] [rbp-70h]
  HGDIOBJ v46; // [rsp+A0h] [rbp-68h]
  struct IUnknown *v47; // [rsp+A8h] [rbp-60h] BYREF
  UINT cLines[4]; // [rsp+B0h] [rbp-58h] BYREF
  void *lpBits[2]; // [rsp+C0h] [rbp-48h]
  __int128 pv; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v51; // [rsp+E0h] [rbp-28h]
  int v52; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v53[36]; // [rsp+FCh] [rbp-Ch] BYREF
  __int64 v54; // [rsp+120h] [rbp+18h]
  BITMAPINFO bmi; // [rsp+178h] [rbp+70h] BYREF

  hdcSrc = (HDC)*((_QWORD *)a6 + 4);
  v45 = a3;
  v43 = wSrc;
  v44 = cy;
  OffsetOnly = XHDC::GetOffsetOnly((XHDC *)this);
  v15 = XHDC::GetOffsetOnly(a6);
  v47 = 0;
  pv = 0;
  v51 = 0;
  *(_OWORD *)cLines = 0;
  *(_OWORD *)lpBits = 0;
  if ( v15 )
  {
    if ( OffsetOnly )
    {
      ha = OffsetOnly->cx;
      v44 = OffsetOnly->cy;
      cx = v15->cx;
      v17 = v15->cy;
      v43 = cx;
      LODWORD(v46) = v17;
      if ( XHDC::ValidateImageDestArea((XHDC *)this, a4, hDest) )
        return StretchBlt(this[4], a2 + ha, v45 + v44, a4, hDest, hdcSrc, a7 + v43, a8 + (_DWORD)v46, wSrc, cy, rop);
      return 0;
    }
    xSrc = v15->cx + a7;
    ySrc = v15->cy + a8;
  }
  else
  {
    ySrc = a8;
    xSrc = a7;
  }
  v40 = v45;
  v39 = a2;
  v42 = hDest + v45;
  v41 = a4 + a2;
  if ( !(unsigned int)XHDC::TransformRect((XHDC *)this, (struct CRect *)&v39) )
    return 0;
  wDesta = XHDC::GetTrivialRotationAngle((XHDC *)this);
  if ( !wDesta )
  {
    v21 = v42 - v40;
    hb = v41 - v39;
    if ( XHDC::ValidateImageDestArea((XHDC *)this, v41 - v39, v42 - v40) )
      return StretchBlt(this[4], v39, v40, hb, v21, hdcSrc, xSrc, ySrc, wSrc, cy, rop);
    return 0;
  }
  v46 = 0;
  v32 = 0;
  SurfaceFromDC = 0;
  hc = CreateCompatibleBitmap(hdcSrc, wSrc, cy);
  if ( wDesta == 180 )
  {
    v23 = cy;
    v24 = wSrc;
  }
  else
  {
    v23 = wSrc;
    v24 = cy;
  }
  CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, v24, v23);
  CompatibleDC = CreateCompatibleDC(hdcSrc);
  if ( !hc || !CompatibleBitmap || !CompatibleDC )
  {
    v27 = hc;
    goto LABEL_38;
  }
  v46 = SelectObject(CompatibleDC, hc);
  BitBlt(CompatibleDC, 0, 0, v43, v44, hdcSrc, xSrc, ySrc, 0xCC0020u);
  SelectObject(CompatibleDC, CompatibleBitmap);
  v27 = hc;
  GetObjectW(hc, 32, &pv);
  GetObjectW(CompatibleBitmap, 32, cLines);
  if ( *((_QWORD *)&v51 + 1) )
  {
LABEL_24:
    if ( lpBits[1] )
    {
      v28 = 0;
    }
    else
    {
      if ( WORD1(lpBits[0]) != 32 )
        goto LABEL_20;
      lpBits[1] = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 4 * cLines[1] * cLines[2]);
      if ( !lpBits[1] )
      {
        SurfaceFromDC = -2147024882;
        goto LABEL_38;
      }
      v28 = 1;
      v32 = 1;
    }
    RotateBitmap(&pv, cLines, wDesta);
    if ( v47 )
    {
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v47->lpVtbl[10].Release)(v47, 0);
      if ( SurfaceFromDC )
        goto LABEL_38;
    }
    if ( !v28
      || (bmi.bmiHeader.biWidth = cLines[1],
          *(_DWORD *)&bmi.bmiHeader.biPlanes = lpBits[0],
          bmi.bmiHeader.biSize = 40,
          bmi.bmiHeader.biHeight = cLines[2],
          memset(&bmi.bmiHeader.biCompression, 0, 28),
          SetDIBits(CompatibleDC, CompatibleBitmap, 0, cLines[2], lpBits[1], &bmi, 0)) )
    {
      v29 = v42 - v40;
      v30 = v41 - v39;
      if ( !XHDC::ValidateImageDestArea((XHDC *)this, v41 - v39, v42 - v40)
        || StretchBlt(this[4], v39, v40, v30, v29, CompatibleDC, 0, 0, cLines[1], cLines[2], rop) == -1 )
      {
        SurfaceFromDC = -2147467259;
      }
      v27 = hc;
      goto LABEL_38;
    }
    goto LABEL_20;
  }
  if ( WORD1(v51) == 32 )
  {
    memset_0(v53, 0, 0x74u);
    v52 = 120;
    SurfaceFromDC = CDirectDraw::GetSurfaceFromDC(hdcSrc, (struct IDirectDrawSurface **)&v47);
    if ( SurfaceFromDC )
      goto LABEL_38;
    SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, __int64, _QWORD))v47->lpVtbl[8].AddRef)(
                      v47,
                      0,
                      &v52,
                      2048,
                      0);
    if ( SurfaceFromDC )
      goto LABEL_38;
    *((_QWORD *)&v51 + 1) = v54;
    goto LABEL_24;
  }
LABEL_20:
  SurfaceFromDC = -2147467259;
LABEL_38:
  ReleaseInterface(v47);
  ReleaseInterface(0);
  if ( v32 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, lpBits[1], v31);
  if ( v46 )
    SelectObject(CompatibleDC, v46);
  if ( v27 )
    DeleteObject(v27);
  if ( CompatibleBitmap )
    DeleteObject(CompatibleBitmap);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  return SurfaceFromDC == 0;
}

```

## disassembly

```asm
0x180b2fde0  mov     rax, rsp
0x180b2fde3  mov     [rax+20h], r9d
0x180b2fde7  mov     [rax+18h], r8d
0x180b2fdeb  mov     [rax+10h], edx
0x180b2fdee  mov     [rax+8], rcx
0x180b2fdf2  push    rbp
0x180b2fdf3  push    rbx
0x180b2fdf4  push    rsi
0x180b2fdf5  push    rdi
0x180b2fdf6  push    r12
0x180b2fdf8  push    r13
0x180b2fdfa  push    r14
0x180b2fdfc  push    r15
0x180b2fdfe  lea     rbp, [rax-0F8h]
0x180b2fe05  sub     rsp, 1B8h
0x180b2fe0c  mov     rax, cs:__security_cookie
0x180b2fe13  xor     rax, rsp
0x180b2fe16  mov     [rbp+0F0h+var_50], rax
0x180b2fe1d  mov     eax, [rbp+0F0h+arg_10]
0x180b2fe23  mov     rbx, [rbp+0F0h+arg_28]
0x180b2fe2a  mov     rsi, [rbp+0F0h+arg_0]
0x180b2fe31  mov     r13d, [rbp+0F0h+arg_8]
0x180b2fe38  mov     rcx, rsi; this
0x180b2fe3b  mov     edi, [rbp+0F0h+arg_40]
0x180b2fe41  mov     r15d, [rbp+0F0h+cy]
0x180b2fe48  mov     r14, [rbx+20h]
0x180b2fe4c  mov     [rbp+0F0h+var_160], eax
0x180b2fe4f  mov     eax, [rbp+0F0h+arg_18]
0x180b2fe55  mov     dword ptr [rsp+1F0h+h], r13d
0x180b2fe5a  mov     [rsp+1F0h+wDest], eax
0x180b2fe5e  mov     [rbp+0F0h+var_168], edi
0x180b2fe61  mov     [rbp+0F0h+var_164], r15d
0x180b2fe65  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b2fe6a  mov     rcx, rbx; this
0x180b2fe6d  mov     r12, rax
0x180b2fe70  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b2fe75  mov     [rbp+0F0h+var_150], 0
0x180b2fe7d  xorps   xmm0, xmm0
0x180b2fe80  xorps   xmm1, xmm1
0x180b2fe83  movups  [rbp+0F0h+pv], xmm0
0x180b2fe87  movups  [rbp+0F0h+var_118], xmm0
0x180b2fe8b  movups  xmmword ptr [rbp+0F0h+cLines], xmm1
0x180b2fe8f  movups  xmmword ptr [rbp+0F0h+lpBits], xmm1
0x180b2fe93  test    rax, rax
0x180b2fe96  jz      loc_180B2FF55
0x180b2fe9c  test    r12, r12
0x180b2fe9f  jz      loc_180B2FF3E
0x180b2fea5  mov     ecx, [r12]
0x180b2fea9  mov     ebx, [rsp+1F0h+wDest]
0x180b2fead  mov     edx, ebx; int
0x180b2feaf  mov     dword ptr [rsp+1F0h+h], ecx
0x180b2feb3  mov     ecx, [r12+4]
0x180b2feb8  mov     r12d, [rbp+0F0h+arg_20]
0x180b2febf  mov     r8d, r12d; int
0x180b2fec2  mov     [rbp+0F0h+var_164], ecx
0x180b2fec5  mov     ecx, [rax]
0x180b2fec7  mov     eax, [rax+4]
0x180b2feca  mov     [rbp+0F0h+var_168], ecx
0x180b2fecd  mov     rcx, rsi; this
0x180b2fed0  mov     dword ptr [rbp+0F0h+var_158], eax
0x180b2fed3  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b2fed8  test    al, al
0x180b2feda  jz      loc_180B30349
0x180b2fee0  mov     r11d, dword ptr [rbp+0F0h+var_158]
0x180b2fee4  mov     r9d, ebx; wDest
0x180b2fee7  add     r11d, [rbp+0F0h+arg_38]
0x180b2feee  mov     eax, [rbp+0F0h+rop]
0x180b2fef4  mov     r10d, [rbp+0F0h+var_168]
0x180b2fef8  add     r10d, [rbp+0F0h+arg_30]
0x180b2feff  mov     r8d, [rbp+0F0h+var_164]
0x180b2ff03  add     r8d, [rbp+0F0h+var_160]; yDest
0x180b2ff07  mov     edx, dword ptr [rsp+1F0h+h]
0x180b2ff0b  mov     [rsp+50h], eax; rop
0x180b2ff0f  add     edx, r13d; xDest
0x180b2ff12  mov     [rsp+1F0h+hSrc], r15d; hSrc
0x180b2ff17  mov     [rsp+1F0h+wSrc], edi; wSrc
0x180b2ff1b  mov     [rsp+1F0h+ySrc], r11d; ySrc
0x180b2ff20  mov     [rsp+1F0h+xSrc], r10d; xSrc
0x180b2ff25  mov     [rsp+1F0h+hdcSrc], r14; hdcSrc
0x180b2ff2a  mov     [rsp+1F0h+hDest], r12d; hDest
0x180b2ff2f  mov     rcx, [rsi+20h]; hdcDest
0x180b2ff33  call    cs:__imp_StretchBlt
0x180b2ff39  jmp     loc_180B3034B
0x180b2ff3e  mov     r12d, [rbp+0F0h+arg_30]
0x180b2ff45  add     r12d, [rax]
0x180b2ff48  mov     r13d, [rbp+0F0h+arg_38]
0x180b2ff4f  add     r13d, [rax+4]
0x180b2ff53  jmp     short loc_180B2FF63
0x180b2ff55  mov     r13d, [rbp+0F0h+arg_38]
0x180b2ff5c  mov     r12d, [rbp+0F0h+arg_30]
0x180b2ff63  mov     ecx, [rbp+0F0h+var_160]
0x180b2ff66  lea     rdx, [rsp+1F0h+var_178]; struct CRect *
0x180b2ff6b  mov     eax, dword ptr [rsp+1F0h+h]
0x180b2ff6f  mov     [rsp+1F0h+var_174], ecx
0x180b2ff73  add     ecx, [rbp+0F0h+arg_20]
0x180b2ff79  mov     [rsp+1F0h+var_178], eax
0x180b2ff7d  add     eax, [rsp+1F0h+wDest]
0x180b2ff81  mov     [rbp+0F0h+var_16C], ecx
0x180b2ff84  mov     rcx, rsi; this
0x180b2ff87  mov     [rbp+0F0h+var_170], eax
0x180b2ff8a  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b2ff8f  test    eax, eax
0x180b2ff91  jz      loc_180B30349
0x180b2ff97  mov     rcx, rsi; this
0x180b2ff9a  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b2ff9f  mov     [rsp+1F0h+wDest], eax
0x180b2ffa3  test    eax, eax
0x180b2ffa5  jnz     short loc_180B30007
0x180b2ffa7  mov     eax, [rbp+0F0h+var_170]
0x180b2ffaa  mov     rcx, rsi; this
0x180b2ffad  sub     eax, [rsp+1F0h+var_178]
0x180b2ffb1  mov     ebx, [rbp+0F0h+var_16C]
0x180b2ffb4  mov     edx, eax; int
0x180b2ffb6  sub     ebx, [rsp+1F0h+var_174]
0x180b2ffba  mov     r8d, ebx; int
0x180b2ffbd  mov     dword ptr [rsp+1F0h+h], eax
0x180b2ffc1  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b2ffc6  test    al, al
0x180b2ffc8  jz      loc_180B30349
0x180b2ffce  mov     eax, [rbp+0F0h+rop]
0x180b2ffd4  mov     r9d, dword ptr [rsp+1F0h+h]
0x180b2ffd9  mov     r8d, [rsp+1F0h+var_174]
0x180b2ffde  mov     edx, [rsp+1F0h+var_178]
0x180b2ffe2  mov     [rsp+50h], eax
0x180b2ffe6  mov     [rsp+1F0h+hSrc], r15d
0x180b2ffeb  mov     [rsp+1F0h+wSrc], edi
0x180b2ffef  mov     [rsp+1F0h+ySrc], r13d
0x180b2fff4  mov     [rsp+1F0h+xSrc], r12d
0x180b2fff9  mov     [rsp+1F0h+hdcSrc], r14
0x180b2fffe  mov     [rsp+1F0h+hDest], ebx
0x180b30002  jmp     loc_180B2FF2F
0x180b30007  xor     eax, eax
0x180b30009  mov     r8d, r15d; cy
0x180b3000c  mov     edx, edi; cx
0x180b3000e  mov     [rbp+0F0h+var_158], rax
0x180b30012  mov     rcx, r14; hdc
0x180b30015  mov     byte ptr [rsp+1F0h+var_190], al
0x180b30019  xor     ebx, ebx
0x180b3001b  call    cs:__imp_CreateCompatibleBitmap
0x180b30021  cmp     [rsp+1F0h+wDest], 0B4h
0x180b30029  mov     rcx, r14; hdc
0x180b3002c  mov     [rsp+1F0h+h], rax
0x180b30031  jnz     short loc_180B3003A
0x180b30033  mov     r8d, r15d
0x180b30036  mov     edx, edi
0x180b30038  jmp     short loc_180B30040
0x180b3003a  mov     r8d, edi; cy
0x180b3003d  mov     edx, r15d; cx
0x180b30040  call    cs:__imp_CreateCompatibleBitmap
0x180b30046  mov     rcx, r14; hdc
0x180b30049  mov     r15, rax
0x180b3004c  call    cs:__imp_CreateCompatibleDC
0x180b30052  mov     rdi, rax
0x180b30055  mov     rax, [rsp+1F0h+h]
0x180b3005a  test    rax, rax
0x180b3005d  jz      loc_180B30341
0x180b30063  test    r15, r15
0x180b30066  jz      loc_180B30341
0x180b3006c  test    rdi, rdi
0x180b3006f  jz      loc_180B30341
0x180b30075  mov     rdx, rax; h
0x180b30078  mov     rcx, rdi; hdc
0x180b3007b  call    cs:__imp_SelectObject
0x180b30081  mov     ecx, [rbp+0F0h+var_164]
0x180b30084  xor     r8d, r8d; y
0x180b30087  mov     r9d, [rbp+0F0h+var_168]; cx
0x180b3008b  xor     edx, edx; x
0x180b3008d  mov     [rsp+1F0h+wSrc], 0CC0020h; rop
0x180b30095  mov     [rsp+1F0h+ySrc], r13d; y1
0x180b3009a  mov     [rsp+1F0h+xSrc], r12d; x1
0x180b3009f  mov     [rsp+1F0h+hdcSrc], r14; hdcSrc
0x180b300a4  mov     [rsp+1F0h+hDest], ecx; cy
0x180b300a8  mov     rcx, rdi; hdc
0x180b300ab  mov     [rbp+0F0h+var_158], rax
0x180b300af  call    cs:__imp_BitBlt
0x180b300b5  mov     rdx, r15; h
0x180b300b8  mov     rcx, rdi; hdc
0x180b300bb  call    cs:__imp_SelectObject
0x180b300c1  mov     r12, [rsp+1F0h+h]
0x180b300c6  lea     r8, [rbp+0F0h+pv]; pv
0x180b300ca  mov     r13d, 20h ; ' '
0x180b300d0  mov     rcx, r12; h
0x180b300d3  mov     edx, r13d; c
0x180b300d6  call    cs:__imp_GetObjectW
0x180b300dc  lea     r8, [rbp+0F0h+cLines]; pv
0x180b300e0  mov     edx, r13d; c
0x180b300e3  mov     rcx, r15; h
0x180b300e6  call    cs:__imp_GetObjectW
0x180b300ec  xor     r13d, r13d
0x180b300ef  cmp     qword ptr [rbp+0F0h+var_118+8], r13
0x180b300f3  jnz     short loc_180B3016B
0x180b300f5  lea     eax, [r13+20h]
0x180b300f9  cmp     word ptr [rbp+0F0h+var_118+2], ax
0x180b300fd  jz      short loc_180B30109
0x180b300ff  mov     ebx, 80004005h
0x180b30104  jmp     loc_180B302D1
0x180b30109  xor     edx, edx; Val
0x180b3010b  lea     rcx, [rbp+0F0h+var_FC]; void *
0x180b3010f  lea     r8d, [rdx+74h]; Size
0x180b30113  call    memset_0
0x180b30118  lea     rdx, [rbp+0F0h+var_150]; struct IDirectDrawSurface **
0x180b3011c  mov     [rbp+0F0h+var_100], 78h ; 'x'
0x180b30123  mov     rcx, r14; HDC
0x180b30126  call    ?GetSurfaceFromDC@CDirectDraw@@SAJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@@Z; CDirectDraw::GetSurfaceFromDC(HDC__ *,IDirectDrawSurface * *)
0x180b3012b  mov     ebx, eax
0x180b3012d  test    eax, eax
0x180b3012f  jnz     loc_180B302D1
0x180b30135  mov     rcx, [rbp+0F0h+var_150]
0x180b30139  lea     r8, [rbp+0F0h+var_100]
0x180b3013d  mov     r9d, 800h
0x180b30143  mov     qword ptr [rsp+1F0h+hDest], r13
0x180b30148  xor     edx, edx
0x180b3014a  mov     rax, [rcx]
0x180b3014d  mov     rax, [rax+0C8h]
0x180b30154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b30159  mov     ebx, eax
0x180b3015b  test    eax, eax
0x180b3015d  jnz     loc_180B302D1
0x180b30163  mov     rax, [rbp+0F0h+var_D8]
0x180b30167  mov     qword ptr [rbp+0F0h+var_118+8], rax
0x180b3016b  cmp     [rbp+0F0h+lpBits+8], r13
0x180b3016f  jnz     short loc_180B301B2
0x180b30171  mov     eax, 20h ; ' '
0x180b30176  cmp     word ptr [rbp+0F0h+lpBits+2], ax
0x180b3017a  jnz     short loc_180B300FF
0x180b3017c  mov     eax, [rbp+0F0h+cLines+8]
0x180b3017f  imul    eax, [rbp+0F0h+cLines+4]
0x180b30183  mov     rcx, cs:g_hProcessHeap
0x180b3018a  shl     eax, 2
0x180b3018d  movsxd  rdx, eax
0x180b30190  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180b30195  mov     [rbp+0F0h+lpBits+8], rax
0x180b30199  test    rax, rax
0x180b3019c  jnz     short loc_180B301A8
0x180b3019e  mov     ebx, 8007000Eh
0x180b301a3  jmp     loc_180B302D1
0x180b301a8  mov     r14b, 1
0x180b301ab  mov     byte ptr [rsp+1F0h+var_190], r14b
0x180b301b0  jmp     short loc_180B301B5
0x180b301b2  mov     r14b, r13b
0x180b301b5  mov     r8d, [rsp+1F0h+wDest]
0x180b301ba  lea     rdx, [rbp+0F0h+cLines]
0x180b301be  lea     rcx, [rbp+0F0h+pv]
0x180b301c2  call    RotateBitmap
0x180b301c7  mov     rcx, [rbp+0F0h+var_150]
0x180b301cb  test    rcx, rcx
0x180b301ce  jz      short loc_180B301EB
0x180b301d0  mov     rax, [rcx]
0x180b301d3  xor     edx, edx
0x180b301d5  mov     rax, [rax+100h]
0x180b301dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b301e1  mov     ebx, eax
0x180b301e3  test    eax, eax
0x180b301e5  jnz     loc_180B302D1
0x180b301eb  test    r14b, r14b
0x180b301ee  jz      short loc_180B3025C
0x180b301f0  mov     eax, [rbp+0F0h+cLines+4]
0x180b301f3  xorps   xmm0, xmm0
0x180b301f6  mov     r9d, [rbp+0F0h+cLines+8]; cLines
0x180b301fa  xor     r8d, r8d; start
0x180b301fd  mov     [rbp+0F0h+bmi.bmiHeader.biWidth], eax
0x180b30200  mov     rdx, r15; hbm
0x180b30203  movzx   eax, word ptr [rbp+0F0h+lpBits]
0x180b30207  mov     rcx, rdi; hdc
0x180b3020a  mov     [rbp+0F0h+bmi.bmiHeader.biPlanes], ax
0x180b3020e  movzx   eax, word ptr [rbp+0F0h+lpBits+2]
0x180b30212  mov     [rbp+0F0h+bmi.bmiHeader.biBitCount], ax
0x180b30216  lea     rax, [rbp+0F0h+bmi]
0x180b3021a  mov     [rsp+1F0h+xSrc], r13d; ColorUse
0x180b3021f  mov     [rsp+1F0h+hdcSrc], rax; lpbmi
0x180b30224  mov     rax, [rbp+0F0h+lpBits+8]
0x180b30228  mov     qword ptr [rsp+1F0h+hDest], rax; lpBits
0x180b3022d  movdqu  xmmword ptr [rbp+0F0h+bmi.bmiHeader.biSizeImage], xmm0
0x180b30235  mov     qword ptr [rbp+0F0h+bmi.bmiHeader.biClrImportant], r13
0x180b3023c  mov     [rbp+0F0h+bmi.bmiHeader.biSize], 28h ; '('
0x180b30243  mov     [rbp+0F0h+bmi.bmiHeader.biHeight], r9d
0x180b30247  mov     [rbp+0F0h+bmi.bmiHeader.biCompression], r13d
0x180b3024e  call    cs:__imp_SetDIBits
0x180b30254  test    eax, eax
0x180b30256  jz      loc_180B300FF
0x180b3025c  mov     r14d, [rbp+0F0h+var_16C]
0x180b30260  mov     rcx, rsi; this
0x180b30263  mov     r12d, [rbp+0F0h+var_170]
0x180b30267  sub     r14d, [rsp+1F0h+var_174]
0x180b3026c  sub     r12d, [rsp+1F0h+var_178]
0x180b30271  mov     r8d, r14d; int
0x180b30274  mov     edx, r12d; int
0x180b30277  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b3027c  test    al, al
0x180b3027e  jz      short loc_180B302C7
0x180b30280  mov     eax, [rbp+0F0h+rop]
0x180b30286  mov     r9d, r12d; wDest
0x180b30289  mov     r8d, [rsp+1F0h+var_174]; yDest
0x180b3028e  mov     edx, [rsp+1F0h+var_178]; xDest
0x180b30292  mov     rcx, [rsi+20h]; hdcDest
0x180b30296  mov     [rsp+50h], eax; rop
0x180b3029a  mov     eax, [rbp+0F0h+cLines+8]
0x180b3029d  mov     [rsp+1F0h+hSrc], eax; hSrc
0x180b302a1  mov     eax, [rbp+0F0h+cLines+4]
0x180b302a4  mov     [rsp+1F0h+wSrc], eax; wSrc
  ... truncated ...
```
