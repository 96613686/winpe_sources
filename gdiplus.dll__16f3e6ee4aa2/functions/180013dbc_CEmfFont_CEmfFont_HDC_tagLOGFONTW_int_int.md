# CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)

- ea: `0x180013dbc`
- end: `0x180013ee4`
- name: `??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z`
- size: `296`
- prototype: `CEmfFont *(CEmfFont *__hidden this, HDC, struct tagLOGFONTW *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001226c`
- `0x180012db8`
- `0x1800133a4`

## callees

- `0x180013dbc`
- `0x180014048`
- `0x1800fe680`

## import_xrefs

- `USER32!GetDC` at `0x180013e3f`
- `USER32!GetDC` at `0x180013e3f`
- `USER32!ReleaseDC` at `0x180013eb3`
- `USER32!ReleaseDC` at `0x180013eb3`
- `GDI32!TranslateCharsetInfo` at `0x180013e8b`
- `GDI32!TranslateCharsetInfo` at `0x180013e8b`
- `GDI32!GetTextCharsetInfo` at `0x180013e6b`
- `GDI32!GetTextCharsetInfo` at `0x180013e6b`
- `GDI32!CreateFontIndirectW` at `0x180013e4b`
- `GDI32!CreateFontIndirectW` at `0x180013e4b`
- `GDI32!SelectObject` at `0x180013e5a`
- `GDI32!SelectObject` at `0x180013e9f`
- `GDI32!SelectObject` at `0x180013e5a`
- `GDI32!SelectObject` at `0x180013e9f`
- `GDI32!DeleteObject` at `0x180013ea8`
- `GDI32!DeleteObject` at `0x180013ea8`

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
0x180013dbc  mov     [rsp+arg_18], rbx
0x180013dc1  push    rsi
0x180013dc2  push    rdi
0x180013dc3  push    r14
0x180013dc5  sub     rsp, 50h
0x180013dc9  mov     rax, cs:__security_cookie
0x180013dd0  xor     rax, rsp
0x180013dd3  mov     [rsp+68h+var_28], rax
0x180013dd8  mov     ebx, r9d
0x180013ddb  mov     rdi, r8
0x180013dde  mov     r14, rcx
0x180013de1  call    ??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z; GpFont::GpFont(HDC__ *,tagLOGFONTW *)
0x180013de6  lea     rax, ??_7CEmfFont@@6B@; const CEmfFont::`vftable'
0x180013ded  mov     [r14+34h], ebx
0x180013df1  mov     [r14], rax
0x180013df4  mov     eax, [rsp+68h+arg_20]
0x180013dfb  mov     [r14+38h], eax
0x180013dff  mov     al, [rdi+17h]
0x180013e02  mov     [r14+40h], al
0x180013e06  mov     dword ptr [r14+44h], 0
0x180013e0e  cmp     dword ptr [rdi+0Ch], 0
0x180013e12  jz      loc_180013EDA
0x180013e18  movd    xmm0, dword ptr [rdi+0Ch]
0x180013e1d  cvtdq2ps xmm0, xmm0
0x180013e20  divss   xmm0, cs:__real@41200000
0x180013e28  movss   dword ptr [r14+30h], xmm0
0x180013e2e  cmp     word ptr [rdi+1Ch], 40h ; '@'
0x180013e33  jnz     short loc_180013E3D
0x180013e35  mov     dword ptr [r14+44h], 1
0x180013e3d  xor     ecx, ecx; hWnd
0x180013e3f  call    cs:__imp_GetDC
0x180013e45  mov     rcx, rdi; lplf
0x180013e48  mov     rsi, rax
0x180013e4b  call    cs:__imp_CreateFontIndirectW
0x180013e51  mov     rdx, rax; h
0x180013e54  mov     rcx, rsi; hdc
0x180013e57  mov     rdi, rax
0x180013e5a  call    cs:__imp_SelectObject
0x180013e60  xor     r8d, r8d; dwFlags
0x180013e63  xor     edx, edx; lpSig
0x180013e65  mov     rcx, rsi; hdc
0x180013e68  mov     rbx, rax
0x180013e6b  call    cs:__imp_GetTextCharsetInfo
0x180013e71  xorps   xmm0, xmm0
0x180013e74  mov     ecx, eax; lpSrc
0x180013e76  mov     r8d, 1; dwFlags
0x180013e7c  lea     rdx, [rsp+68h+var_48]; lpCs
0x180013e81  movups  xmmword ptr [rsp+68h+var_48.ciCharset], xmm0
0x180013e86  movups  xmmword ptr [rsp+68h+var_48.fs.fsUsb+8], xmm0
0x180013e8b  call    cs:__imp_TranslateCharsetInfo
0x180013e91  mov     ecx, [rsp+68h+var_48.ciACP]
0x180013e95  mov     rdx, rbx; h
0x180013e98  mov     [r14+3Ch], ecx
0x180013e9c  mov     rcx, rsi; hdc
0x180013e9f  call    cs:__imp_SelectObject
0x180013ea5  mov     rcx, rdi; ho
0x180013ea8  call    cs:__imp_DeleteObject
0x180013eae  mov     rdx, rsi; hDC
0x180013eb1  xor     ecx, ecx; hWnd
0x180013eb3  call    cs:__imp_ReleaseDC
0x180013eb9  mov     rax, r14
0x180013ebc  mov     rcx, [rsp+68h+var_28]
0x180013ec1  xor     rcx, rsp; StackCookie
0x180013ec4  call    __security_check_cookie
0x180013ec9  mov     rbx, [rsp+68h+arg_18]
0x180013ed1  add     rsp, 50h
0x180013ed5  pop     r14
0x180013ed7  pop     rdi
0x180013ed8  pop     rsi
0x180013ed9  retn
0x180013eda  movd    xmm0, dword ptr [rdi+8]
0x180013edf  jmp     loc_180013E1D
```
