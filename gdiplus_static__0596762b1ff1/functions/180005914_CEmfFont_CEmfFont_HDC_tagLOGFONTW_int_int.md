# CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)

- ea: `0x180005914`
- end: `0x180005a6d`
- name: `??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z`
- size: `345`
- prototype: `CEmfFont *(CEmfFont *__hidden this, HDC, struct tagLOGFONTW *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f8c`
- `0x180004ba8`
- `0x1800051a8`

## callees

- `0x180005914`
- `0x180005c20`
- `0x180105d40`

## import_xrefs

- `USER32!GetDC` at `0x180005997`
- `USER32!GetDC` at `0x180005997`
- `USER32!ReleaseDC` at `0x180005a35`
- `USER32!ReleaseDC` at `0x180005a35`
- `GDI32!TranslateCharsetInfo` at `0x1800059fb`
- `GDI32!TranslateCharsetInfo` at `0x1800059fb`
- `GDI32!GetTextCharsetInfo` at `0x1800059d5`
- `GDI32!GetTextCharsetInfo` at `0x1800059d5`
- `GDI32!CreateFontIndirectW` at `0x1800059a9`
- `GDI32!CreateFontIndirectW` at `0x1800059a9`
- `GDI32!SelectObject` at `0x1800059be`
- `GDI32!SelectObject` at `0x180005a15`
- `GDI32!SelectObject` at `0x1800059be`
- `GDI32!SelectObject` at `0x180005a15`
- `GDI32!DeleteObject` at `0x180005a24`
- `GDI32!DeleteObject` at `0x180005a24`

## pseudocode

```c
CEmfFont *__fastcall CEmfFont::CEmfFont(CEmfFont *this, HDC a2, struct tagLOGFONTW *a3, int a4, int a5)
{
  __m128i v8; // xmm0
  HDC DC; // rsi
  HFONT FontIndirectW; // rdi
  HGDIOBJ v11; // rbx
  unsigned int TextCharsetInfo; // eax
  tagCHARSETINFO v14; // [rsp+20h] [rbp-48h] BYREF

  GpFont::GpFont(this, a2, a3);
  *((_DWORD *)this + 13) = a4;
  *(_QWORD *)this = &CEmfFont::`vftable';
  *((_DWORD *)this + 14) = a5;
  *((_BYTE *)this + 64) = a3->lfCharSet;
  *((_DWORD *)this + 17) = 0;
  if ( a3->lfOrientation )
    v8 = _mm_cvtsi32_si128(a3->lfOrientation);
  else
    v8 = _mm_cvtsi32_si128(a3->lfEscapement);
  *((float *)this + 12) = _mm_cvtepi32_ps(v8).m128_f32[0] / 10.0;
  if ( a3->lfFaceName[0] == 64 )
    *((_DWORD *)this + 17) = 1;
  DC = GetDC(0);
  FontIndirectW = CreateFontIndirectW(a3);
  v11 = SelectObject(DC, FontIndirectW);
  TextCharsetInfo = GetTextCharsetInfo(DC, 0, 0);
  memset(&v14, 0, sizeof(v14));
  TranslateCharsetInfo((DWORD *)TextCharsetInfo, &v14, 1u);
  *((_DWORD *)this + 15) = v14.ciACP;
  SelectObject(DC, v11);
  DeleteObject(FontIndirectW);
  ReleaseDC(0, DC);
  return this;
}

```

## disassembly

```asm
0x180005914  mov     [rsp+arg_18], rbx
0x180005919  push    rsi
0x18000591a  push    rdi
0x18000591b  push    r14
0x18000591d  sub     rsp, 50h
0x180005921  mov     rax, cs:__security_cookie
0x180005928  xor     rax, rsp
0x18000592b  mov     [rsp+68h+var_28], rax
0x180005930  mov     ebx, r9d
0x180005933  mov     rdi, r8
0x180005936  mov     r14, rcx
0x180005939  call    ??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z; GpFont::GpFont(HDC__ *,tagLOGFONTW *)
0x18000593e  lea     rax, ??_7CEmfFont@@6B@; const CEmfFont::`vftable'
0x180005945  mov     [r14+34h], ebx
0x180005949  mov     [r14], rax
0x18000594c  mov     eax, [rsp+68h+arg_20]
0x180005953  mov     [r14+38h], eax
0x180005957  mov     al, [rdi+17h]
0x18000595a  mov     [r14+40h], al
0x18000595e  mov     dword ptr [r14+44h], 0
0x180005966  cmp     dword ptr [rdi+0Ch], 0
0x18000596a  jz      loc_180005A63
0x180005970  movd    xmm0, dword ptr [rdi+0Ch]
0x180005975  cvtdq2ps xmm0, xmm0
0x180005978  divss   xmm0, cs:__real@41200000
0x180005980  movss   dword ptr [r14+30h], xmm0
0x180005986  cmp     word ptr [rdi+1Ch], 40h ; '@'
0x18000598b  jnz     short loc_180005995
0x18000598d  mov     dword ptr [r14+44h], 1
0x180005995  xor     ecx, ecx; hWnd
0x180005997  call    cs:__imp_GetDC
0x18000599e  nop     dword ptr [rax+rax+00h]
0x1800059a3  mov     rcx, rdi; lplf
0x1800059a6  mov     rsi, rax
0x1800059a9  call    cs:__imp_CreateFontIndirectW
0x1800059b0  nop     dword ptr [rax+rax+00h]
0x1800059b5  mov     rdx, rax; h
0x1800059b8  mov     rcx, rsi; hdc
0x1800059bb  mov     rdi, rax
0x1800059be  call    cs:__imp_SelectObject
0x1800059c5  nop     dword ptr [rax+rax+00h]
0x1800059ca  xor     r8d, r8d; dwFlags
0x1800059cd  xor     edx, edx; lpSig
0x1800059cf  mov     rcx, rsi; hdc
0x1800059d2  mov     rbx, rax
0x1800059d5  call    cs:__imp_GetTextCharsetInfo
0x1800059dc  nop     dword ptr [rax+rax+00h]
0x1800059e1  xorps   xmm0, xmm0
0x1800059e4  mov     ecx, eax; lpSrc
0x1800059e6  mov     r8d, 1; dwFlags
0x1800059ec  lea     rdx, [rsp+68h+var_48]; lpCs
0x1800059f1  movups  xmmword ptr [rsp+68h+var_48.ciCharset], xmm0
0x1800059f6  movups  xmmword ptr [rsp+68h+var_48.fs.fsUsb+8], xmm0
0x1800059fb  call    cs:__imp_TranslateCharsetInfo
0x180005a02  nop     dword ptr [rax+rax+00h]
0x180005a07  mov     ecx, [rsp+68h+var_48.ciACP]
0x180005a0b  mov     rdx, rbx; h
0x180005a0e  mov     [r14+3Ch], ecx
0x180005a12  mov     rcx, rsi; hdc
0x180005a15  call    cs:__imp_SelectObject
0x180005a1c  nop     dword ptr [rax+rax+00h]
0x180005a21  mov     rcx, rdi; ho
0x180005a24  call    cs:__imp_DeleteObject
0x180005a2b  nop     dword ptr [rax+rax+00h]
0x180005a30  mov     rdx, rsi; hDC
0x180005a33  xor     ecx, ecx; hWnd
0x180005a35  call    cs:__imp_ReleaseDC
0x180005a3c  nop     dword ptr [rax+rax+00h]
0x180005a41  mov     rax, r14
0x180005a44  mov     rcx, [rsp+68h+var_28]
0x180005a49  xor     rcx, rsp; StackCookie
0x180005a4c  call    __security_check_cookie
0x180005a51  mov     rbx, [rsp+68h+arg_18]
0x180005a59  add     rsp, 50h
0x180005a5d  pop     r14
0x180005a5f  pop     rdi
0x180005a60  pop     rsi
0x180005a61  retn
0x180005a63  movd    xmm0, dword ptr [rdi+8]
0x180005a68  jmp     loc_180005975
```
