# CDetachedBrowserTabCoverUI::_AddPauseAtBreakpointOverlay(int,int,HDC__ * *)

- ea: `0x180331ab8`
- end: `0x180331df6`
- name: `?_AddPauseAtBreakpointOverlay@CDetachedBrowserTabCoverUI@@IEAAXHHPEAPEAUHDC__@@@Z`
- size: `830`
- prototype: `void(CDetachedBrowserTabCoverUI *__hidden this, int, int, HDC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180331dfc`

## callees

- `0x18009aaf0`
- `0x180331ab8`
- `0x1803326e4`
- `0x180591f80`

## import_xrefs

- `GDI32!PatBlt` at `0x180331c2a`
- `GDI32!PatBlt` at `0x180331c2a`
- `GDI32!CreateSolidBrush` at `0x180331b98`
- `GDI32!CreateSolidBrush` at `0x180331bb0`
- `GDI32!CreateSolidBrush` at `0x180331b98`
- `GDI32!CreateSolidBrush` at `0x180331bb0`
- `GDI32!DeleteObject` at `0x180331d57`
- `GDI32!DeleteObject` at `0x180331d88`
- `GDI32!DeleteObject` at `0x180331dae`
- `GDI32!DeleteObject` at `0x180331d57`
- `GDI32!DeleteObject` at `0x180331d88`
- `GDI32!DeleteObject` at `0x180331dae`
- `GDI32!SelectObject` at `0x180331b7f`
- `GDI32!SelectObject` at `0x180331bd9`
- `GDI32!SelectObject` at `0x180331ca1`
- `GDI32!SelectObject` at `0x180331d43`
- `GDI32!SelectObject` at `0x180331d73`
- `GDI32!SelectObject` at `0x180331d9f`
- `GDI32!SelectObject` at `0x180331b7f`
- `GDI32!SelectObject` at `0x180331bd9`
- `GDI32!SelectObject` at `0x180331ca1`
- `GDI32!SelectObject` at `0x180331d43`
- `GDI32!SelectObject` at `0x180331d73`
- `GDI32!SelectObject` at `0x180331d9f`
- `GDI32!CreateFontIndirectW` at `0x180331c8b`
- `GDI32!CreateFontIndirectW` at `0x180331c8b`
- `GDI32!SetTextColor` at `0x180331bc7`
- `GDI32!SetTextColor` at `0x180331bc7`
- `GDI32!SetBkMode` at `0x180331c3e`
- `GDI32!SetBkMode` at `0x180331c3e`
- `GDI32!TextOutW` at `0x180331cda`
- `GDI32!TextOutW` at `0x180331cda`
- `GDI32!DeleteDC` at `0x180331dc2`
- `GDI32!DeleteDC` at `0x180331dc2`
- `GDI32!CreateCompatibleDC` at `0x180331b4b`
- `GDI32!CreateCompatibleDC` at `0x180331b4b`
- `GDI32!CreateCompatibleBitmap` at `0x180331b30`
- `GDI32!CreateCompatibleBitmap` at `0x180331b30`
- `USER32!SetRect` at `0x180331bfb`
- `USER32!SetRect` at `0x180331bfb`
- `MSIMG32!AlphaBlend` at `0x180331d27`
- `MSIMG32!AlphaBlend` at `0x180331d27`

## pseudocode

```c
void __fastcall CDetachedBrowserTabCoverUI::_AddPauseAtBreakpointOverlay(
        CDetachedBrowserTabCoverUI *this,
        int a2,
        int a3,
        HDC *a4)
{
  int v7; // ecx
  char v8; // di
  HBITMAP CompatibleBitmap; // rsi
  HDC CompatibleDC; // rax
  HDC v11; // rbx
  HGDIOBJ v12; // r15
  HBRUSH SolidBrush; // rax
  COLORREF v14; // edx
  HBRUSH v15; // rdi
  HDC v16; // rcx
  BLENDFUNCTION v17; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[2]; // [rsp+64h] [rbp-9Ch] BYREF
  int v19; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+70h] [rbp-90h]
  HGDIOBJ v21; // [rsp+78h] [rbp-88h]
  HGDIOBJ ho; // [rsp+80h] [rbp-80h]
  struct tagRECT rc; // [rsp+88h] [rbp-78h] BYREF
  LOGFONTW lf; // [rsp+A0h] [rbp-60h] BYREF

  v17 = 0;
  rc = 0;
  CDetachedBrowserTabCoverUI::_GetHighContrastMode(this, (enum CDetachedBrowserTabCoverUI::HighContrastMode *)&v17);
  if ( v17 == 2 || (v8 = 0, v17 == 3) && (unsigned int)SysColorIsDark(v7) )
    v8 = 1;
  CompatibleBitmap = CreateCompatibleBitmap(*a4, a2, a3);
  if ( CompatibleBitmap )
  {
    CompatibleDC = CreateCompatibleDC(*a4);
    v11 = CompatibleDC;
    if ( CompatibleDC )
    {
      v19 = a2 / 2;
      v17 = (BLENDFUNCTION)(a3 / 2);
      v12 = SelectObject(CompatibleDC, CompatibleBitmap);
      if ( v8 )
      {
        SolidBrush = CreateSolidBrush(0xFFFFFFu);
        v14 = 1973790;
      }
      else
      {
        SolidBrush = CreateSolidBrush(0x1E1E1Eu);
        v14 = 0xFFFFFF;
      }
      v15 = SolidBrush;
      SetTextColor(v11, v14);
      h = SelectObject(v11, v15);
      SetRect(&rc, 0, 0, a2, a3);
      PatBlt(v11, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0xF00021u);
      SetBkMode(v11, 1);
      *(_QWORD *)&lf.lfWeight = 600;
      *(__m128i *)&lf.lfHeight = _mm_load_si128((const __m128i *)&_xmm);
      *(_DWORD *)&lf.lfOutPrecision = 33816576;
      wcscpy(lf.lfFaceName, L"Segoe UI Symbol");
      memset(&lf.lfFaceName[16], 0, 32);
      ho = CreateFontIndirectW(&lf);
      v21 = SelectObject(v11, ho);
      *(_DWORD *)String = 660154201;
      TextOutW(v11, v19 - 30, *(_DWORD *)&v17 - 69, String, 2);
      v16 = *a4;
      v17 = (BLENDFUNCTION)9830400;
      AlphaBlend(v16, 0, 0, a2, a3, v11, rc.left, rc.top, rc.right, rc.bottom, (BLENDFUNCTION)9830400);
      if ( h )
        SelectObject(v11, h);
      if ( v15 )
        DeleteObject(v15);
      if ( v21 )
        SelectObject(v11, v21);
      if ( ho )
        DeleteObject(ho);
      if ( v12 )
        SelectObject(v11, v12);
    }
    DeleteObject(CompatibleBitmap);
    if ( v11 )
      DeleteDC(v11);
  }
}

```

## disassembly

```asm
0x180331ab8  mov     [rsp-8+arg_0], rbx
0x180331abd  push    rbp
0x180331abe  push    rsi
0x180331abf  push    rdi
0x180331ac0  push    r12
0x180331ac2  push    r13
0x180331ac4  push    r14
0x180331ac6  push    r15
0x180331ac8  lea     rbp, [rsp-10h]
0x180331acd  sub     rsp, 110h
0x180331ad4  mov     rax, cs:__security_cookie
0x180331adb  xor     rax, rsp
0x180331ade  mov     [rbp+40h+var_40], rax
0x180331ae2  mov     r12d, edx
0x180331ae5  mov     dword ptr [rsp+140h+var_E0.BlendOp], 0
0x180331aed  xorps   xmm0, xmm0
0x180331af0  lea     rdx, [rsp+140h+var_E0]; enum CDetachedBrowserTabCoverUI::HighContrastMode *
0x180331af5  movups  xmmword ptr [rbp+40h+rc.left], xmm0
0x180331af9  mov     r14, r9
0x180331afc  mov     r13d, r8d
0x180331aff  call    ?_GetHighContrastMode@CDetachedBrowserTabCoverUI@@IEAAXPEAW4HighContrastMode@1@@Z; CDetachedBrowserTabCoverUI::_GetHighContrastMode(CDetachedBrowserTabCoverUI::HighContrastMode *)
0x180331b04  mov     r15d, 2
0x180331b0a  cmp     dword ptr [rsp+140h+var_E0.BlendOp], r15d
0x180331b0f  jz      short loc_180331B24
0x180331b11  xor     dil, dil
0x180331b14  cmp     dword ptr [rsp+140h+var_E0.BlendOp], 3
0x180331b19  jnz     short loc_180331B27
0x180331b1b  call    ?SysColorIsDark@@YAHH@Z; SysColorIsDark(int)
0x180331b20  test    eax, eax
0x180331b22  jz      short loc_180331B27
0x180331b24  mov     dil, 1
0x180331b27  mov     rcx, [r14]; hdc
0x180331b2a  mov     r8d, r13d; cy
0x180331b2d  mov     edx, r12d; cx
0x180331b30  call    cs:__imp_CreateCompatibleBitmap
0x180331b37  nop     dword ptr [rax+rax+00h]
0x180331b3c  mov     rsi, rax
0x180331b3f  test    rax, rax
0x180331b42  jz      loc_180331DCE
0x180331b48  mov     rcx, [r14]; hdc
0x180331b4b  call    cs:__imp_CreateCompatibleDC
0x180331b52  nop     dword ptr [rax+rax+00h]
0x180331b57  mov     rbx, rax
0x180331b5a  test    rax, rax
0x180331b5d  jz      loc_180331DAB
0x180331b63  mov     eax, r12d
0x180331b66  mov     rcx, rbx; hdc
0x180331b69  cdq
0x180331b6a  idiv    r15d
0x180331b6d  mov     [rsp+140h+var_D8], eax
0x180331b71  mov     eax, r13d
0x180331b74  cdq
0x180331b75  idiv    r15d
0x180331b78  mov     rdx, rsi; h
0x180331b7b  mov     dword ptr [rsp+140h+var_E0.BlendOp], eax
0x180331b7f  call    cs:__imp_SelectObject
0x180331b86  nop     dword ptr [rax+rax+00h]
0x180331b8b  mov     r15, rax
0x180331b8e  test    dil, dil
0x180331b91  jz      short loc_180331BAB
0x180331b93  mov     ecx, 0FFFFFFh; color
0x180331b98  call    cs:__imp_CreateSolidBrush
0x180331b9f  nop     dword ptr [rax+rax+00h]
0x180331ba4  mov     edx, 1E1E1Eh
0x180331ba9  jmp     short loc_180331BC1
0x180331bab  mov     ecx, 1E1E1Eh; color
0x180331bb0  call    cs:__imp_CreateSolidBrush
0x180331bb7  nop     dword ptr [rax+rax+00h]
0x180331bbc  mov     edx, 0FFFFFFh; color
0x180331bc1  mov     rcx, rbx; hdc
0x180331bc4  mov     rdi, rax
0x180331bc7  call    cs:__imp_SetTextColor
0x180331bce  nop     dword ptr [rax+rax+00h]
0x180331bd3  mov     rdx, rdi; h
0x180331bd6  mov     rcx, rbx; hdc
0x180331bd9  call    cs:__imp_SelectObject
0x180331be0  nop     dword ptr [rax+rax+00h]
0x180331be5  mov     r9d, r12d; xRight
0x180331be8  mov     [rsp+140h+yBottom], r13d; yBottom
0x180331bed  xor     r8d, r8d; yTop
0x180331bf0  mov     [rsp+140h+h], rax
0x180331bf5  xor     edx, edx; xLeft
0x180331bf7  lea     rcx, [rbp+40h+rc]; lprc
0x180331bfb  call    cs:__imp_SetRect
0x180331c02  nop     dword ptr [rax+rax+00h]
0x180331c07  mov     ecx, [rbp+40h+rc.bottom]
0x180331c0a  mov     r8d, [rbp+40h+rc.top]; y
0x180331c0e  sub     ecx, r8d
0x180331c11  mov     r9d, [rbp+40h+rc.right]
0x180331c15  mov     edx, [rbp+40h+rc.left]; x
0x180331c18  sub     r9d, edx; w
0x180331c1b  mov     [rsp+140h+rop], 0F00021h; rop
0x180331c23  mov     [rsp+140h+yBottom], ecx; h
0x180331c27  mov     rcx, rbx; hdc
0x180331c2a  call    cs:__imp_PatBlt
0x180331c31  nop     dword ptr [rax+rax+00h]
0x180331c36  mov     edx, 1; mode
0x180331c3b  mov     rcx, rbx; hdc
0x180331c3e  call    cs:__imp_SetBkMode
0x180331c45  nop     dword ptr [rax+rax+00h]
0x180331c4a  movdqa  xmm0, cs:__xmm@00000000000000000000000000000078
0x180331c52  lea     rcx, [rbp+40h+lf]; lplf
0x180331c56  movups  xmm1, xmmword ptr cs:aSegoeUiSymbol+10h; " Symbol"
0x180331c5d  mov     qword ptr [rbp+40h+lf.lfWeight], 258h
0x180331c65  movdqa  xmmword ptr [rbp+40h+lf.lfHeight], xmm0
0x180331c6a  movups  xmm0, xmmword ptr cs:aSegoeUiSymbol; "Segoe UI Symbol"
0x180331c71  mov     dword ptr [rbp+40h+lf.lfOutPrecision], 2040000h
0x180331c78  movups  xmmword ptr [rbp+40h+lf.lfFaceName+10h], xmm1
0x180331c7c  movups  xmmword ptr [rbp+40h+lf.lfFaceName], xmm0
0x180331c80  xorps   xmm0, xmm0
0x180331c83  movups  xmmword ptr [rbp+40h+lf.lfFaceName+20h], xmm0
0x180331c87  movups  xmmword ptr [rbp+40h+lf.lfFaceName+30h], xmm0
0x180331c8b  call    cs:__imp_CreateFontIndirectW
0x180331c92  nop     dword ptr [rax+rax+00h]
0x180331c97  mov     rdx, rax; h
0x180331c9a  mov     [rbp+40h+ho], rax
0x180331c9e  mov     rcx, rbx; hdc
0x180331ca1  call    cs:__imp_SelectObject
0x180331ca8  nop     dword ptr [rax+rax+00h]
0x180331cad  mov     r8d, dword ptr [rsp+140h+var_E0.BlendOp]
0x180331cb2  lea     r9, [rsp+140h+String]; lpString
0x180331cb7  mov     edx, [rsp+140h+var_D8]
0x180331cbb  add     r8d, 0FFFFFFBBh; y
0x180331cbf  add     edx, 0FFFFFFE2h; x
0x180331cc2  mov     [rsp+140h+var_C8], rax
0x180331cc7  mov     rcx, rbx; hdc
0x180331cca  mov     dword ptr [rsp+140h+String], 27592759h
0x180331cd2  mov     [rsp+140h+yBottom], 2; c
0x180331cda  call    cs:__imp_TextOutW
0x180331ce1  nop     dword ptr [rax+rax+00h]
0x180331ce6  mov     rcx, [r14]; hdcDest
0x180331ce9  mov     r9d, r12d; wDest
0x180331cec  mov     dword ptr [rsp+140h+var_E0.BlendOp], 960000h
0x180331cf4  xor     r8d, r8d; yoriginDest
0x180331cf7  mov     eax, dword ptr [rsp+140h+var_E0.BlendOp]
0x180331cfb  xor     edx, edx; xoriginDest
0x180331cfd  mov     dword ptr [rsp+140h+ftn.BlendOp], eax; ftn
0x180331d01  mov     eax, [rbp+40h+rc.bottom]
0x180331d04  mov     [rsp+140h+hSrc], eax; hSrc
0x180331d08  mov     eax, [rbp+40h+rc.right]
0x180331d0b  mov     [rsp+140h+wSrc], eax; wSrc
0x180331d0f  mov     eax, [rbp+40h+rc.top]
0x180331d12  mov     [rsp+140h+yoriginSrc], eax; yoriginSrc
0x180331d16  mov     eax, [rbp+40h+rc.left]
0x180331d19  mov     [rsp+140h+xoriginSrc], eax; xoriginSrc
0x180331d1d  mov     qword ptr [rsp+140h+rop], rbx; hdcSrc
0x180331d22  mov     [rsp+140h+yBottom], r13d; hDest
0x180331d27  call    cs:__imp_AlphaBlend
0x180331d2e  nop     dword ptr [rax+rax+00h]
0x180331d33  mov     rax, [rsp+140h+h]
0x180331d38  test    rax, rax
0x180331d3b  jz      short loc_180331D4F
0x180331d3d  mov     rdx, rax; h
0x180331d40  mov     rcx, rbx; hdc
0x180331d43  call    cs:__imp_SelectObject
0x180331d4a  nop     dword ptr [rax+rax+00h]
0x180331d4f  test    rdi, rdi
0x180331d52  jz      short loc_180331D63
0x180331d54  mov     rcx, rdi; ho
0x180331d57  call    cs:__imp_DeleteObject
0x180331d5e  nop     dword ptr [rax+rax+00h]
0x180331d63  mov     rax, [rsp+140h+var_C8]
0x180331d68  test    rax, rax
0x180331d6b  jz      short loc_180331D7F
0x180331d6d  mov     rdx, rax; h
0x180331d70  mov     rcx, rbx; hdc
0x180331d73  call    cs:__imp_SelectObject
0x180331d7a  nop     dword ptr [rax+rax+00h]
0x180331d7f  mov     rcx, [rbp+40h+ho]; ho
0x180331d83  test    rcx, rcx
0x180331d86  jz      short loc_180331D94
0x180331d88  call    cs:__imp_DeleteObject
0x180331d8f  nop     dword ptr [rax+rax+00h]
0x180331d94  test    r15, r15
0x180331d97  jz      short loc_180331DAB
0x180331d99  mov     rdx, r15; h
0x180331d9c  mov     rcx, rbx; hdc
0x180331d9f  call    cs:__imp_SelectObject
0x180331da6  nop     dword ptr [rax+rax+00h]
0x180331dab  mov     rcx, rsi; ho
0x180331dae  call    cs:__imp_DeleteObject
0x180331db5  nop     dword ptr [rax+rax+00h]
0x180331dba  test    rbx, rbx
0x180331dbd  jz      short loc_180331DCE
0x180331dbf  mov     rcx, rbx; hdc
0x180331dc2  call    cs:__imp_DeleteDC
0x180331dc9  nop     dword ptr [rax+rax+00h]
0x180331dce  mov     rcx, [rbp+40h+var_40]
0x180331dd2  xor     rcx, rsp; StackCookie
0x180331dd5  call    __security_check_cookie
0x180331dda  mov     rbx, [rsp+140h+arg_0]
0x180331de2  add     rsp, 110h
0x180331de9  pop     r15
0x180331deb  pop     r14
0x180331ded  pop     r13
0x180331def  pop     r12
0x180331df1  pop     rdi
0x180331df2  pop     rsi
0x180331df3  pop     rbp
0x180331df4  retn
```
