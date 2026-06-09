# CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)

- ea: `0x1800603cc`
- end: `0x180060522`
- name: `??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z`
- size: `342`
- prototype: `CEmfFont *(CEmfFont *__hidden this, HDC, struct tagLOGFONTW *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18005e880`
- `0x18005f428`
- `0x18005fde8`

## callees

- `0x1800603cc`
- `0x180060830`
- `0x1800e9380`

## import_xrefs

- `USER32!GetDC` at `0x18006044c`
- `USER32!GetDC` at `0x18006044c`
- `USER32!ReleaseDC` at `0x1800604ea`
- `USER32!ReleaseDC` at `0x1800604ea`
- `GDI32!TranslateCharsetInfo` at `0x1800604b0`
- `GDI32!TranslateCharsetInfo` at `0x1800604b0`
- `GDI32!GetTextCharsetInfo` at `0x18006048a`
- `GDI32!GetTextCharsetInfo` at `0x18006048a`
- `GDI32!CreateFontIndirectW` at `0x18006045e`
- `GDI32!CreateFontIndirectW` at `0x18006045e`
- `GDI32!SelectObject` at `0x180060473`
- `GDI32!SelectObject` at `0x1800604ca`
- `GDI32!SelectObject` at `0x180060473`
- `GDI32!SelectObject` at `0x1800604ca`
- `GDI32!DeleteObject` at `0x1800604d9`
- `GDI32!DeleteObject` at `0x1800604d9`

## pseudocode

```c
CEmfFont *__fastcall CEmfFont::CEmfFont(CEmfFont *this, HDC a2, struct tagLOGFONTW *a3, int a4, int a5)
{
  BYTE lfCharSet; // al
  __m128i v9; // xmm0
  HDC DC; // rsi
  HFONT FontIndirectW; // rdi
  HGDIOBJ v12; // rbx
  unsigned int TextCharsetInfo; // eax
  tagCHARSETINFO v15; // [rsp+20h] [rbp-48h] BYREF

  GpFont::GpFont(this, a2, a3);
  *((_DWORD *)this + 13) = a4;
  *(_QWORD *)this = &CEmfFont::`vftable';
  *((_DWORD *)this + 14) = a5;
  lfCharSet = a3->lfCharSet;
  *((_DWORD *)this + 17) = 0;
  *((_BYTE *)this + 64) = lfCharSet;
  if ( a3->lfOrientation )
    v9 = _mm_cvtsi32_si128(a3->lfOrientation);
  else
    v9 = _mm_cvtsi32_si128(a3->lfEscapement);
  *((float *)this + 12) = _mm_cvtepi32_ps(v9).m128_f32[0] / 10.0;
  if ( a3->lfFaceName[0] == 64 )
    *((_DWORD *)this + 17) = 1;
  DC = GetDC(0);
  FontIndirectW = CreateFontIndirectW(a3);
  v12 = SelectObject(DC, FontIndirectW);
  TextCharsetInfo = GetTextCharsetInfo(DC, 0, 0);
  memset(&v15, 0, sizeof(v15));
  TranslateCharsetInfo((DWORD *)TextCharsetInfo, &v15, 1u);
  *((_DWORD *)this + 15) = v15.ciACP;
  SelectObject(DC, v12);
  DeleteObject(FontIndirectW);
  ReleaseDC(0, DC);
  return this;
}

```

## disassembly

```asm
0x1800603cc  mov     [rsp+arg_18], rbx
0x1800603d1  push    rsi
0x1800603d2  push    rdi
0x1800603d3  push    r14
0x1800603d5  sub     rsp, 50h
0x1800603d9  mov     rax, cs:__security_cookie
0x1800603e0  xor     rax, rsp
0x1800603e3  mov     [rsp+68h+var_28], rax
0x1800603e8  mov     ebx, r9d
0x1800603eb  mov     rdi, r8
0x1800603ee  mov     r14, rcx
0x1800603f1  call    ??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z; GpFont::GpFont(HDC__ *,tagLOGFONTW *)
0x1800603f6  lea     rax, ??_7CEmfFont@@6B@; const CEmfFont::`vftable'
0x1800603fd  mov     [r14+34h], ebx
0x180060401  mov     [r14], rax
0x180060404  mov     eax, [rsp+68h+arg_20]
0x18006040b  mov     [r14+38h], eax
0x18006040f  mov     al, [rdi+17h]
0x180060412  and     dword ptr [r14+44h], 0
0x180060417  mov     [r14+40h], al
0x18006041b  cmp     dword ptr [rdi+0Ch], 0
0x18006041f  jz      loc_180060518
0x180060425  movd    xmm0, dword ptr [rdi+0Ch]
0x18006042a  cvtdq2ps xmm0, xmm0
0x18006042d  divss   xmm0, cs:__real@41200000
0x180060435  movss   dword ptr [r14+30h], xmm0
0x18006043b  cmp     word ptr [rdi+1Ch], 40h ; '@'
0x180060440  jnz     short loc_18006044A
0x180060442  mov     dword ptr [r14+44h], 1
0x18006044a  xor     ecx, ecx; hWnd
0x18006044c  call    cs:__imp_GetDC
0x180060453  nop     dword ptr [rax+rax+00h]
0x180060458  mov     rcx, rdi; lplf
0x18006045b  mov     rsi, rax
0x18006045e  call    cs:__imp_CreateFontIndirectW
0x180060465  nop     dword ptr [rax+rax+00h]
0x18006046a  mov     rdx, rax; h
0x18006046d  mov     rcx, rsi; hdc
0x180060470  mov     rdi, rax
0x180060473  call    cs:__imp_SelectObject
0x18006047a  nop     dword ptr [rax+rax+00h]
0x18006047f  xor     r8d, r8d; dwFlags
0x180060482  xor     edx, edx; lpSig
0x180060484  mov     rcx, rsi; hdc
0x180060487  mov     rbx, rax
0x18006048a  call    cs:__imp_GetTextCharsetInfo
0x180060491  nop     dword ptr [rax+rax+00h]
0x180060496  xorps   xmm0, xmm0
0x180060499  mov     ecx, eax; lpSrc
0x18006049b  mov     r8d, 1; dwFlags
0x1800604a1  lea     rdx, [rsp+68h+var_48]; lpCs
0x1800604a6  movups  xmmword ptr [rsp+68h+var_48.ciCharset], xmm0
0x1800604ab  movups  xmmword ptr [rsp+68h+var_48.fs.fsUsb+8], xmm0
0x1800604b0  call    cs:__imp_TranslateCharsetInfo
0x1800604b7  nop     dword ptr [rax+rax+00h]
0x1800604bc  mov     ecx, [rsp+68h+var_48.ciACP]
0x1800604c0  mov     rdx, rbx; h
0x1800604c3  mov     [r14+3Ch], ecx
0x1800604c7  mov     rcx, rsi; hdc
0x1800604ca  call    cs:__imp_SelectObject
0x1800604d1  nop     dword ptr [rax+rax+00h]
0x1800604d6  mov     rcx, rdi; ho
0x1800604d9  call    cs:__imp_DeleteObject
0x1800604e0  nop     dword ptr [rax+rax+00h]
0x1800604e5  mov     rdx, rsi; hDC
0x1800604e8  xor     ecx, ecx; hWnd
0x1800604ea  call    cs:__imp_ReleaseDC
0x1800604f1  nop     dword ptr [rax+rax+00h]
0x1800604f6  mov     rax, r14
0x1800604f9  mov     rcx, [rsp+68h+var_28]
0x1800604fe  xor     rcx, rsp; StackCookie
0x180060501  call    __security_check_cookie
0x180060506  mov     rbx, [rsp+68h+arg_18]
0x18006050e  add     rsp, 50h
0x180060512  pop     r14
0x180060514  pop     rdi
0x180060515  pop     rsi
0x180060516  retn
0x180060518  movd    xmm0, dword ptr [rdi+8]
0x18006051d  jmp     loc_18006042A
```
