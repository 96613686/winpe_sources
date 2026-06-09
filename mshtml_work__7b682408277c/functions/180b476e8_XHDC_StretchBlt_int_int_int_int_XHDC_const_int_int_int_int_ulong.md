# XHDC::StretchBlt(int,int,int,int,XHDC const &,int,int,int,int,ulong)

- ea: `0x180b476e8`
- end: `0x180b47cd4`
- name: `?StretchBlt@XHDC@@QEBAHHHHHAEBV1@HHHHK@Z`
- size: `1516`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, const struct XHDC *, int, int, int, int cy, DWORD rop)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180b44860`
- `0x180b47cdc`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x1800ea428`
- `0x180b46be8`
- `0x180b46d74`
- `0x180b46f14`
- `0x180b476e8`
- `0x180b4a458`
- `0x180b4a620`
- `0x180b610e8`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180b47c8d`
- `GDI32!DeleteDC` at `0x180b47c8d`
- `GDI32!SetDIBits` at `0x180b47b8c`
- `GDI32!SetDIBits` at `0x180b47b8c`
- `GDI32!StretchBlt` at `0x180b4783b`
- `GDI32!StretchBlt` at `0x180b47c00`
- `GDI32!StretchBlt` at `0x180b4783b`
- `GDI32!StretchBlt` at `0x180b47c00`
- `GDI32!DeleteObject` at `0x180b47c65`
- `GDI32!DeleteObject` at `0x180b47c79`
- `GDI32!DeleteObject` at `0x180b47c65`
- `GDI32!DeleteObject` at `0x180b47c79`
- `GDI32!SelectObject` at `0x180b4799b`
- `GDI32!SelectObject` at `0x180b479e7`
- `GDI32!SelectObject` at `0x180b47c51`
- `GDI32!SelectObject` at `0x180b4799b`
- `GDI32!SelectObject` at `0x180b479e7`
- `GDI32!SelectObject` at `0x180b47c51`
- `GDI32!BitBlt` at `0x180b479d5`
- `GDI32!BitBlt` at `0x180b479d5`
- `GDI32!CreateCompatibleBitmap` at `0x180b47929`
- `GDI32!CreateCompatibleBitmap` at `0x180b47954`
- `GDI32!CreateCompatibleBitmap` at `0x180b47929`
- `GDI32!CreateCompatibleBitmap` at `0x180b47954`
- `GDI32!CreateCompatibleDC` at `0x180b47966`
- `GDI32!CreateCompatibleDC` at `0x180b47966`
- `GDI32!GetObjectW` at `0x180b47a08`
- `GDI32!GetObjectW` at `0x180b47a1e`
- `GDI32!GetObjectW` at `0x180b47a08`
- `GDI32!GetObjectW` at `0x180b47a1e`

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
  __int64 v28; // r8
  char v29; // r14
  int v30; // r14d
  int v31; // r12d
  void *v32; // r8
  char v33; // [rsp+68h] [rbp-A0h]
  LONG ha; // [rsp+70h] [rbp-98h]
  int hb; // [rsp+70h] [rbp-98h]
  HBITMAP hc; // [rsp+70h] [rbp-98h]
  unsigned int wDesta; // [rsp+78h] [rbp-90h]
  int v40; // [rsp+80h] [rbp-88h] BYREF
  int v41; // [rsp+84h] [rbp-84h]
  int v42; // [rsp+88h] [rbp-80h]
  int v43; // [rsp+8Ch] [rbp-7Ch]
  int v44; // [rsp+90h] [rbp-78h]
  int v45; // [rsp+94h] [rbp-74h]
  int v46; // [rsp+98h] [rbp-70h]
  HGDIOBJ v47; // [rsp+A0h] [rbp-68h]
  struct IUnknown *v48; // [rsp+A8h] [rbp-60h] BYREF
  UINT cLines[4]; // [rsp+B0h] [rbp-58h] BYREF
  void *lpBits[2]; // [rsp+C0h] [rbp-48h]
  __int128 pv; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-28h]
  int v53; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v54[36]; // [rsp+FCh] [rbp-Ch] BYREF
  __int64 v55; // [rsp+120h] [rbp+18h]
  BITMAPINFO bmi; // [rsp+178h] [rbp+70h] BYREF

  hdcSrc = (HDC)*((_QWORD *)a6 + 4);
  v46 = a3;
  v44 = wSrc;
  v45 = cy;
  OffsetOnly = XHDC::GetOffsetOnly((XHDC *)this);
  v15 = XHDC::GetOffsetOnly(a6);
  v48 = 0;
  pv = 0;
  v52 = 0;
  *(_OWORD *)cLines = 0;
  *(_OWORD *)lpBits = 0;
  if ( v15 )
  {
    if ( OffsetOnly )
    {
      ha = OffsetOnly->cx;
      v45 = OffsetOnly->cy;
      cx = v15->cx;
      v17 = v15->cy;
      v44 = cx;
      LODWORD(v47) = v17;
      if ( XHDC::ValidateImageDestArea((XHDC *)this, a4, hDest) )
        return StretchBlt(this[4], a2 + ha, v46 + v45, a4, hDest, hdcSrc, a7 + v44, a8 + (_DWORD)v47, wSrc, cy, rop);
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
  v41 = v46;
  v40 = a2;
  v43 = hDest + v46;
  v42 = a4 + a2;
  if ( !(unsigned int)XHDC::TransformRect((XHDC *)this, (struct CRect *)&v40) )
    return 0;
  wDesta = XHDC::GetTrivialRotationAngle((XHDC *)this);
  if ( !wDesta )
  {
    v21 = v43 - v41;
    hb = v42 - v40;
    if ( XHDC::ValidateImageDestArea((XHDC *)this, v42 - v40, v43 - v41) )
      return StretchBlt(this[4], v40, v41, hb, v21, hdcSrc, xSrc, ySrc, wSrc, cy, rop);
    return 0;
  }
  v47 = 0;
  v33 = 0;
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
  v47 = SelectObject(CompatibleDC, hc);
  BitBlt(CompatibleDC, 0, 0, v44, v45, hdcSrc, xSrc, ySrc, 0xCC0020u);
  SelectObject(CompatibleDC, CompatibleBitmap);
  v27 = hc;
  GetObjectW(hc, 32, &pv);
  GetObjectW(CompatibleBitmap, 32, cLines);
  if ( *((_QWORD *)&v52 + 1) )
  {
LABEL_24:
    if ( lpBits[1] )
    {
      v29 = 0;
    }
    else
    {
      if ( WORD1(lpBits[0]) != 32 )
        goto LABEL_20;
      lpBits[1] = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 4 * cLines[1] * cLines[2], v28);
      if ( !lpBits[1] )
      {
        SurfaceFromDC = -2147024882;
        goto LABEL_38;
      }
      v29 = 1;
      v33 = 1;
    }
    RotateBitmap(&pv, cLines, wDesta);
    if ( v48 )
    {
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v48->lpVtbl[10].Release)(v48, 0);
      if ( SurfaceFromDC )
        goto LABEL_38;
    }
    if ( !v29
      || (bmi.bmiHeader.biWidth = cLines[1],
          *(_DWORD *)&bmi.bmiHeader.biPlanes = lpBits[0],
          bmi.bmiHeader.biSize = 40,
          bmi.bmiHeader.biHeight = cLines[2],
          memset(&bmi.bmiHeader.biCompression, 0, 28),
          SetDIBits(CompatibleDC, CompatibleBitmap, 0, cLines[2], lpBits[1], &bmi, 0)) )
    {
      v30 = v43 - v41;
      v31 = v42 - v40;
      if ( !XHDC::ValidateImageDestArea((XHDC *)this, v42 - v40, v43 - v41)
        || StretchBlt(this[4], v40, v41, v31, v30, CompatibleDC, 0, 0, cLines[1], cLines[2], rop) == -1 )
      {
        SurfaceFromDC = -2147467259;
      }
      v27 = hc;
      goto LABEL_38;
    }
    goto LABEL_20;
  }
  if ( WORD1(v52) == 32 )
  {
    memset_0(v54, 0, 0x74u);
    v53 = 120;
    SurfaceFromDC = CDirectDraw::GetSurfaceFromDC(hdcSrc, (struct IDirectDrawSurface **)&v48);
    if ( SurfaceFromDC )
      goto LABEL_38;
    SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, __int64, _QWORD))v48->lpVtbl[8].AddRef)(
                      v48,
                      0,
                      &v53,
                      2048,
                      0);
    if ( SurfaceFromDC )
      goto LABEL_38;
    *((_QWORD *)&v52 + 1) = v55;
    goto LABEL_24;
  }
LABEL_20:
  SurfaceFromDC = -2147467259;
LABEL_38:
  ReleaseInterface(v48);
  ReleaseInterface(0);
  if ( v33 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, lpBits[1], v32);
  if ( v47 )
    SelectObject(CompatibleDC, v47);
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
0x180b476e8  mov     rax, rsp
0x180b476eb  mov     [rax+20h], r9d
0x180b476ef  mov     [rax+18h], r8d
0x180b476f3  mov     [rax+10h], edx
0x180b476f6  mov     [rax+8], rcx
0x180b476fa  push    rbp
0x180b476fb  push    rbx
0x180b476fc  push    rsi
0x180b476fd  push    rdi
0x180b476fe  push    r12
0x180b47700  push    r13
0x180b47702  push    r14
0x180b47704  push    r15
0x180b47706  lea     rbp, [rax-0F8h]
0x180b4770d  sub     rsp, 1B8h
0x180b47714  mov     rax, cs:__security_cookie
0x180b4771b  xor     rax, rsp
0x180b4771e  mov     [rbp+0F0h+var_50], rax
0x180b47725  mov     eax, [rbp+0F0h+arg_10]
0x180b4772b  mov     rbx, [rbp+0F0h+arg_28]
0x180b47732  mov     rsi, [rbp+0F0h+arg_0]
0x180b47739  mov     r13d, [rbp+0F0h+arg_8]
0x180b47740  mov     rcx, rsi; this
0x180b47743  mov     edi, [rbp+0F0h+arg_40]
0x180b47749  mov     r15d, [rbp+0F0h+cy]
0x180b47750  mov     r14, [rbx+20h]
0x180b47754  mov     [rbp+0F0h+var_160], eax
0x180b47757  mov     eax, [rbp+0F0h+arg_18]
0x180b4775d  mov     dword ptr [rsp+1F0h+h], r13d
0x180b47762  mov     [rsp+1F0h+wDest], eax
0x180b47766  mov     [rbp+0F0h+var_168], edi
0x180b47769  mov     [rbp+0F0h+var_164], r15d
0x180b4776d  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b47772  mov     rcx, rbx; this
0x180b47775  mov     r12, rax
0x180b47778  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b4777d  mov     [rbp+0F0h+var_150], 0
0x180b47785  xorps   xmm0, xmm0
0x180b47788  xorps   xmm1, xmm1
0x180b4778b  movups  [rbp+0F0h+pv], xmm0
0x180b4778f  movups  [rbp+0F0h+var_118], xmm0
0x180b47793  movups  xmmword ptr [rbp+0F0h+cLines], xmm1
0x180b47797  movups  xmmword ptr [rbp+0F0h+lpBits], xmm1
0x180b4779b  test    rax, rax
0x180b4779e  jz      loc_180B47863
0x180b477a4  test    r12, r12
0x180b477a7  jz      loc_180B4784C
0x180b477ad  mov     ecx, [r12]
0x180b477b1  mov     ebx, [rsp+1F0h+wDest]
0x180b477b5  mov     edx, ebx; int
0x180b477b7  mov     dword ptr [rsp+1F0h+h], ecx
0x180b477bb  mov     ecx, [r12+4]
0x180b477c0  mov     r12d, [rbp+0F0h+arg_20]
0x180b477c7  mov     r8d, r12d; int
0x180b477ca  mov     [rbp+0F0h+var_164], ecx
0x180b477cd  mov     ecx, [rax]
0x180b477cf  mov     eax, [rax+4]
0x180b477d2  mov     [rbp+0F0h+var_168], ecx
0x180b477d5  mov     rcx, rsi; this
0x180b477d8  mov     dword ptr [rbp+0F0h+var_158], eax
0x180b477db  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b477e0  test    al, al
0x180b477e2  jz      loc_180B47CAE
0x180b477e8  mov     r11d, dword ptr [rbp+0F0h+var_158]
0x180b477ec  mov     r9d, ebx; wDest
0x180b477ef  add     r11d, [rbp+0F0h+arg_38]
0x180b477f6  mov     eax, [rbp+0F0h+rop]
0x180b477fc  mov     r10d, [rbp+0F0h+var_168]
0x180b47800  add     r10d, [rbp+0F0h+arg_30]
0x180b47807  mov     r8d, [rbp+0F0h+var_164]
0x180b4780b  add     r8d, [rbp+0F0h+var_160]; yDest
0x180b4780f  mov     edx, dword ptr [rsp+1F0h+h]
0x180b47813  mov     [rsp+50h], eax; rop
0x180b47817  add     edx, r13d; xDest
0x180b4781a  mov     [rsp+1F0h+hSrc], r15d; hSrc
0x180b4781f  mov     [rsp+1F0h+wSrc], edi; wSrc
0x180b47823  mov     [rsp+1F0h+ySrc], r11d; ySrc
0x180b47828  mov     [rsp+1F0h+xSrc], r10d; xSrc
0x180b4782d  mov     [rsp+1F0h+hdcSrc], r14; hdcSrc
0x180b47832  mov     [rsp+1F0h+hDest], r12d; hDest
0x180b47837  mov     rcx, [rsi+20h]; hdcDest
0x180b4783b  call    cs:__imp_StretchBlt
0x180b47842  nop     dword ptr [rax+rax+00h]
0x180b47847  jmp     loc_180B47CB0
0x180b4784c  mov     r12d, [rbp+0F0h+arg_30]
0x180b47853  add     r12d, [rax]
0x180b47856  mov     r13d, [rbp+0F0h+arg_38]
0x180b4785d  add     r13d, [rax+4]
0x180b47861  jmp     short loc_180B47871
0x180b47863  mov     r13d, [rbp+0F0h+arg_38]
0x180b4786a  mov     r12d, [rbp+0F0h+arg_30]
0x180b47871  mov     ecx, [rbp+0F0h+var_160]
0x180b47874  lea     rdx, [rsp+1F0h+var_178]; struct CRect *
0x180b47879  mov     eax, dword ptr [rsp+1F0h+h]
0x180b4787d  mov     [rsp+1F0h+var_174], ecx
0x180b47881  add     ecx, [rbp+0F0h+arg_20]
0x180b47887  mov     [rsp+1F0h+var_178], eax
0x180b4788b  add     eax, [rsp+1F0h+wDest]
0x180b4788f  mov     [rbp+0F0h+var_16C], ecx
0x180b47892  mov     rcx, rsi; this
0x180b47895  mov     [rbp+0F0h+var_170], eax
0x180b47898  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b4789d  test    eax, eax
0x180b4789f  jz      loc_180B47CAE
0x180b478a5  mov     rcx, rsi; this
0x180b478a8  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b478ad  mov     [rsp+1F0h+wDest], eax
0x180b478b1  test    eax, eax
0x180b478b3  jnz     short loc_180B47915
0x180b478b5  mov     eax, [rbp+0F0h+var_170]
0x180b478b8  mov     rcx, rsi; this
0x180b478bb  sub     eax, [rsp+1F0h+var_178]
0x180b478bf  mov     ebx, [rbp+0F0h+var_16C]
0x180b478c2  mov     edx, eax; int
0x180b478c4  sub     ebx, [rsp+1F0h+var_174]
0x180b478c8  mov     r8d, ebx; int
0x180b478cb  mov     dword ptr [rsp+1F0h+h], eax
0x180b478cf  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b478d4  test    al, al
0x180b478d6  jz      loc_180B47CAE
0x180b478dc  mov     eax, [rbp+0F0h+rop]
0x180b478e2  mov     r9d, dword ptr [rsp+1F0h+h]
0x180b478e7  mov     r8d, [rsp+1F0h+var_174]
0x180b478ec  mov     edx, [rsp+1F0h+var_178]
0x180b478f0  mov     [rsp+50h], eax
0x180b478f4  mov     [rsp+1F0h+hSrc], r15d
0x180b478f9  mov     [rsp+1F0h+wSrc], edi
0x180b478fd  mov     [rsp+1F0h+ySrc], r13d
0x180b47902  mov     [rsp+1F0h+xSrc], r12d
0x180b47907  mov     [rsp+1F0h+hdcSrc], r14
0x180b4790c  mov     [rsp+1F0h+hDest], ebx
0x180b47910  jmp     loc_180B47837
0x180b47915  xor     eax, eax
0x180b47917  mov     r8d, r15d; cy
0x180b4791a  mov     edx, edi; cx
0x180b4791c  mov     [rbp+0F0h+var_158], rax
0x180b47920  mov     rcx, r14; hdc
0x180b47923  mov     byte ptr [rsp+1F0h+var_190], al
0x180b47927  xor     ebx, ebx
0x180b47929  call    cs:__imp_CreateCompatibleBitmap
0x180b47930  nop     dword ptr [rax+rax+00h]
0x180b47935  cmp     [rsp+1F0h+wDest], 0B4h
0x180b4793d  mov     rcx, r14; hdc
0x180b47940  mov     [rsp+1F0h+h], rax
0x180b47945  jnz     short loc_180B4794E
0x180b47947  mov     r8d, r15d
0x180b4794a  mov     edx, edi
0x180b4794c  jmp     short loc_180B47954
0x180b4794e  mov     r8d, edi; cy
0x180b47951  mov     edx, r15d; cx
0x180b47954  call    cs:__imp_CreateCompatibleBitmap
0x180b4795b  nop     dword ptr [rax+rax+00h]
0x180b47960  mov     rcx, r14; hdc
0x180b47963  mov     r15, rax
0x180b47966  call    cs:__imp_CreateCompatibleDC
0x180b4796d  nop     dword ptr [rax+rax+00h]
0x180b47972  mov     rdi, rax
0x180b47975  mov     rax, [rsp+1F0h+h]
0x180b4797a  test    rax, rax
0x180b4797d  jz      loc_180B47CA3
0x180b47983  test    r15, r15
0x180b47986  jz      loc_180B47CA3
0x180b4798c  test    rdi, rdi
0x180b4798f  jz      loc_180B47CA3
0x180b47995  mov     rdx, rax; h
0x180b47998  mov     rcx, rdi; hdc
0x180b4799b  call    cs:__imp_SelectObject
0x180b479a2  nop     dword ptr [rax+rax+00h]
0x180b479a7  mov     ecx, [rbp+0F0h+var_164]
0x180b479aa  xor     r8d, r8d; y
0x180b479ad  mov     r9d, [rbp+0F0h+var_168]; cx
0x180b479b1  xor     edx, edx; x
0x180b479b3  mov     [rsp+1F0h+wSrc], 0CC0020h; rop
0x180b479bb  mov     [rsp+1F0h+ySrc], r13d; y1
0x180b479c0  mov     [rsp+1F0h+xSrc], r12d; x1
0x180b479c5  mov     [rsp+1F0h+hdcSrc], r14; hdcSrc
0x180b479ca  mov     [rsp+1F0h+hDest], ecx; cy
0x180b479ce  mov     rcx, rdi; hdc
0x180b479d1  mov     [rbp+0F0h+var_158], rax
0x180b479d5  call    cs:__imp_BitBlt
0x180b479dc  nop     dword ptr [rax+rax+00h]
0x180b479e1  mov     rdx, r15; h
0x180b479e4  mov     rcx, rdi; hdc
0x180b479e7  call    cs:__imp_SelectObject
0x180b479ee  nop     dword ptr [rax+rax+00h]
0x180b479f3  mov     r12, [rsp+1F0h+h]
0x180b479f8  lea     r8, [rbp+0F0h+pv]; pv
0x180b479fc  mov     r13d, 20h ; ' '
0x180b47a02  mov     rcx, r12; h
0x180b47a05  mov     edx, r13d; c
0x180b47a08  call    cs:__imp_GetObjectW
0x180b47a0f  nop     dword ptr [rax+rax+00h]
0x180b47a14  lea     r8, [rbp+0F0h+cLines]; pv
0x180b47a18  mov     edx, r13d; c
0x180b47a1b  mov     rcx, r15; h
0x180b47a1e  call    cs:__imp_GetObjectW
0x180b47a25  nop     dword ptr [rax+rax+00h]
0x180b47a2a  xor     r13d, r13d
0x180b47a2d  cmp     qword ptr [rbp+0F0h+var_118+8], r13
0x180b47a31  jnz     short loc_180B47AA9
0x180b47a33  lea     eax, [r13+20h]
0x180b47a37  cmp     word ptr [rbp+0F0h+var_118+2], ax
0x180b47a3b  jz      short loc_180B47A47
0x180b47a3d  mov     ebx, 80004005h
0x180b47a42  jmp     loc_180B47C1B
0x180b47a47  xor     edx, edx; Val
0x180b47a49  lea     rcx, [rbp+0F0h+var_FC]; void *
0x180b47a4d  lea     r8d, [rdx+74h]; Size
0x180b47a51  call    memset_0
0x180b47a56  lea     rdx, [rbp+0F0h+var_150]; struct IDirectDrawSurface **
0x180b47a5a  mov     [rbp+0F0h+var_100], 78h ; 'x'
0x180b47a61  mov     rcx, r14; HDC
0x180b47a64  call    ?GetSurfaceFromDC@CDirectDraw@@SAJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@@Z; CDirectDraw::GetSurfaceFromDC(HDC__ *,IDirectDrawSurface * *)
0x180b47a69  mov     ebx, eax
0x180b47a6b  test    eax, eax
0x180b47a6d  jnz     loc_180B47C1B
0x180b47a73  mov     rcx, [rbp+0F0h+var_150]
0x180b47a77  lea     r8, [rbp+0F0h+var_100]
0x180b47a7b  mov     r9d, 800h
0x180b47a81  mov     qword ptr [rsp+1F0h+hDest], r13
0x180b47a86  xor     edx, edx
0x180b47a88  mov     rax, [rcx]
0x180b47a8b  mov     rax, [rax+0C8h]
0x180b47a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b47a97  mov     ebx, eax
0x180b47a99  test    eax, eax
0x180b47a9b  jnz     loc_180B47C1B
0x180b47aa1  mov     rax, [rbp+0F0h+var_D8]
0x180b47aa5  mov     qword ptr [rbp+0F0h+var_118+8], rax
0x180b47aa9  cmp     [rbp+0F0h+lpBits+8], r13
0x180b47aad  jnz     short loc_180B47AF0
0x180b47aaf  mov     eax, 20h ; ' '
0x180b47ab4  cmp     word ptr [rbp+0F0h+lpBits+2], ax
0x180b47ab8  jnz     short loc_180B47A3D
0x180b47aba  mov     eax, [rbp+0F0h+cLines+8]
0x180b47abd  imul    eax, [rbp+0F0h+cLines+4]
0x180b47ac1  mov     rcx, cs:g_hProcessHeap
0x180b47ac8  shl     eax, 2
0x180b47acb  movsxd  rdx, eax
0x180b47ace  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180b47ad3  mov     [rbp+0F0h+lpBits+8], rax
0x180b47ad7  test    rax, rax
0x180b47ada  jnz     short loc_180B47AE6
0x180b47adc  mov     ebx, 8007000Eh
0x180b47ae1  jmp     loc_180B47C1B
0x180b47ae6  mov     r14b, 1
0x180b47ae9  mov     byte ptr [rsp+1F0h+var_190], r14b
0x180b47aee  jmp     short loc_180B47AF3
0x180b47af0  mov     r14b, r13b
0x180b47af3  mov     r8d, [rsp+1F0h+wDest]
0x180b47af8  lea     rdx, [rbp+0F0h+cLines]
0x180b47afc  lea     rcx, [rbp+0F0h+pv]
0x180b47b00  call    RotateBitmap
0x180b47b05  mov     rcx, [rbp+0F0h+var_150]
0x180b47b09  test    rcx, rcx
0x180b47b0c  jz      short loc_180B47B29
0x180b47b0e  mov     rax, [rcx]
0x180b47b11  xor     edx, edx
0x180b47b13  mov     rax, [rax+100h]
0x180b47b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b47b1f  mov     ebx, eax
0x180b47b21  test    eax, eax
0x180b47b23  jnz     loc_180B47C1B
0x180b47b29  test    r14b, r14b
0x180b47b2c  jz      short loc_180B47BA0
0x180b47b2e  mov     eax, [rbp+0F0h+cLines+4]
0x180b47b31  xorps   xmm0, xmm0
0x180b47b34  mov     r9d, [rbp+0F0h+cLines+8]; cLines
0x180b47b38  xor     r8d, r8d; start
0x180b47b3b  mov     [rbp+0F0h+bmi.bmiHeader.biWidth], eax
0x180b47b3e  mov     rdx, r15; hbm
0x180b47b41  movzx   eax, word ptr [rbp+0F0h+lpBits]
0x180b47b45  mov     rcx, rdi; hdc
0x180b47b48  mov     [rbp+0F0h+bmi.bmiHeader.biPlanes], ax
0x180b47b4c  movzx   eax, word ptr [rbp+0F0h+lpBits+2]
0x180b47b50  mov     [rbp+0F0h+bmi.bmiHeader.biBitCount], ax
0x180b47b54  lea     rax, [rbp+0F0h+bmi]
0x180b47b58  mov     [rsp+1F0h+xSrc], r13d; ColorUse
0x180b47b5d  mov     [rsp+1F0h+hdcSrc], rax; lpbmi
0x180b47b62  mov     rax, [rbp+0F0h+lpBits+8]
0x180b47b66  mov     qword ptr [rsp+1F0h+hDest], rax; lpBits
0x180b47b6b  movdqu  xmmword ptr [rbp+0F0h+bmi.bmiHeader.biSizeImage], xmm0
0x180b47b73  mov     qword ptr [rbp+0F0h+bmi.bmiHeader.biClrImportant], r13
0x180b47b7a  mov     [rbp+0F0h+bmi.bmiHeader.biSize], 28h ; '('
0x180b47b81  mov     [rbp+0F0h+bmi.bmiHeader.biHeight], r9d
0x180b47b85  mov     [rbp+0F0h+bmi.bmiHeader.biCompression], r13d
0x180b47b8c  call    cs:__imp_SetDIBits
0x180b47b93  nop     dword ptr [rax+rax+00h]
0x180b47b98  test    eax, eax
0x180b47b9a  jz      loc_180B47A3D
0x180b47ba0  mov     r14d, [rbp+0F0h+var_16C]
0x180b47ba4  mov     rcx, rsi; this
0x180b47ba7  mov     r12d, [rbp+0F0h+var_170]
0x180b47bab  sub     r14d, [rsp+1F0h+var_174]
0x180b47bb0  sub     r12d, [rsp+1F0h+var_178]
0x180b47bb5  mov     r8d, r14d; int
0x180b47bb8  mov     edx, r12d; int
0x180b47bbb  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b47bc0  test    al, al
0x180b47bc2  jz      short loc_180B47C11
  ... truncated ...
```
