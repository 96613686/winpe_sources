# CDetachedBrowserTabCoverUI::_AddPauseAtBreakpointOverlay(int,int,HDC__ * *)

- ea: `0x180307fc4`
- end: `0x180308283`
- name: `?_AddPauseAtBreakpointOverlay@CDetachedBrowserTabCoverUI@@IEAAXHHPEAPEAUHDC__@@@Z`
- size: `703`
- prototype: `void(CDetachedBrowserTabCoverUI *__hidden this, int, int, HDC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18030828c`

## callees

- `0x180093920`
- `0x180307fc4`
- `0x180308a48`
- `0x18054e310`

## import_xrefs

- `GDI32!PatBlt` at `0x180308106`
- `GDI32!PatBlt` at `0x180308106`
- `GDI32!CreateSolidBrush` at `0x180308092`
- `GDI32!CreateSolidBrush` at `0x1803080a4`
- `GDI32!CreateSolidBrush` at `0x180308092`
- `GDI32!CreateSolidBrush` at `0x1803080a4`
- `GDI32!DeleteObject` at `0x180308209`
- `GDI32!DeleteObject` at `0x18030822e`
- `GDI32!DeleteObject` at `0x180308248`
- `GDI32!DeleteObject` at `0x180308209`
- `GDI32!DeleteObject` at `0x18030822e`
- `GDI32!DeleteObject` at `0x180308248`
- `GDI32!SelectObject` at `0x18030807f`
- `GDI32!SelectObject` at `0x1803080c1`
- `GDI32!SelectObject` at `0x18030816b`
- `GDI32!SelectObject` at `0x1803081fb`
- `GDI32!SelectObject` at `0x18030821f`
- `GDI32!SelectObject` at `0x18030823f`
- `GDI32!SelectObject` at `0x18030807f`
- `GDI32!SelectObject` at `0x1803080c1`
- `GDI32!SelectObject` at `0x18030816b`
- `GDI32!SelectObject` at `0x1803081fb`
- `GDI32!SelectObject` at `0x18030821f`
- `GDI32!SelectObject` at `0x18030823f`
- `GDI32!CreateFontIndirectW` at `0x18030815b`
- `GDI32!CreateFontIndirectW` at `0x18030815b`
- `GDI32!SetTextColor` at `0x1803080b5`
- `GDI32!SetTextColor` at `0x1803080b5`
- `GDI32!SetBkMode` at `0x180308114`
- `GDI32!SetBkMode` at `0x180308114`
- `GDI32!TextOutW` at `0x18030819e`
- `GDI32!TextOutW` at `0x18030819e`
- `GDI32!DeleteDC` at `0x180308256`
- `GDI32!DeleteDC` at `0x180308256`
- `GDI32!CreateCompatibleDC` at `0x180308051`
- `GDI32!CreateCompatibleDC` at `0x180308051`
- `GDI32!CreateCompatibleBitmap` at `0x18030803c`
- `GDI32!CreateCompatibleBitmap` at `0x18030803c`
- `USER32!SetRect` at `0x1803080dd`
- `USER32!SetRect` at `0x1803080dd`
- `MSIMG32!AlphaBlend` at `0x1803081e5`
- `MSIMG32!AlphaBlend` at `0x1803081e5`

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
0x180307fc4  mov     [rsp-8+arg_0], rbx
0x180307fc9  push    rbp
0x180307fca  push    rsi
0x180307fcb  push    rdi
0x180307fcc  push    r12
0x180307fce  push    r13
0x180307fd0  push    r14
0x180307fd2  push    r15
0x180307fd4  lea     rbp, [rsp-10h]
0x180307fd9  sub     rsp, 110h
0x180307fe0  mov     rax, cs:__security_cookie
0x180307fe7  xor     rax, rsp
0x180307fea  mov     [rbp+40h+var_40], rax
0x180307fee  mov     r12d, edx
0x180307ff1  mov     dword ptr [rsp+140h+var_E0.BlendOp], 0
0x180307ff9  xorps   xmm0, xmm0
0x180307ffc  lea     rdx, [rsp+140h+var_E0]; enum CDetachedBrowserTabCoverUI::HighContrastMode *
0x180308001  movups  xmmword ptr [rbp+40h+rc.left], xmm0
0x180308005  mov     r14, r9
0x180308008  mov     r13d, r8d
0x18030800b  call    ?_GetHighContrastMode@CDetachedBrowserTabCoverUI@@IEAAXPEAW4HighContrastMode@1@@Z; CDetachedBrowserTabCoverUI::_GetHighContrastMode(CDetachedBrowserTabCoverUI::HighContrastMode *)
0x180308010  mov     r15d, 2
0x180308016  cmp     dword ptr [rsp+140h+var_E0.BlendOp], r15d
0x18030801b  jz      short loc_180308030
0x18030801d  xor     dil, dil
0x180308020  cmp     dword ptr [rsp+140h+var_E0.BlendOp], 3
0x180308025  jnz     short loc_180308033
0x180308027  call    ?SysColorIsDark@@YAHH@Z; SysColorIsDark(int)
0x18030802c  test    eax, eax
0x18030802e  jz      short loc_180308033
0x180308030  mov     dil, 1
0x180308033  mov     rcx, [r14]; hdc
0x180308036  mov     r8d, r13d; cy
0x180308039  mov     edx, r12d; cx
0x18030803c  call    cs:__imp_CreateCompatibleBitmap
0x180308042  mov     rsi, rax
0x180308045  test    rax, rax
0x180308048  jz      loc_18030825C
0x18030804e  mov     rcx, [r14]; hdc
0x180308051  call    cs:__imp_CreateCompatibleDC
0x180308057  mov     rbx, rax
0x18030805a  test    rax, rax
0x18030805d  jz      loc_180308245
0x180308063  mov     eax, r12d
0x180308066  mov     rcx, rbx; hdc
0x180308069  cdq
0x18030806a  idiv    r15d
0x18030806d  mov     [rsp+140h+var_D8], eax
0x180308071  mov     eax, r13d
0x180308074  cdq
0x180308075  idiv    r15d
0x180308078  mov     rdx, rsi; h
0x18030807b  mov     dword ptr [rsp+140h+var_E0.BlendOp], eax
0x18030807f  call    cs:__imp_SelectObject
0x180308085  mov     r15, rax
0x180308088  test    dil, dil
0x18030808b  jz      short loc_18030809F
0x18030808d  mov     ecx, 0FFFFFFh; color
0x180308092  call    cs:__imp_CreateSolidBrush
0x180308098  mov     edx, 1E1E1Eh
0x18030809d  jmp     short loc_1803080AF
0x18030809f  mov     ecx, 1E1E1Eh; color
0x1803080a4  call    cs:__imp_CreateSolidBrush
0x1803080aa  mov     edx, 0FFFFFFh; color
0x1803080af  mov     rcx, rbx; hdc
0x1803080b2  mov     rdi, rax
0x1803080b5  call    cs:__imp_SetTextColor
0x1803080bb  mov     rdx, rdi; h
0x1803080be  mov     rcx, rbx; hdc
0x1803080c1  call    cs:__imp_SelectObject
0x1803080c7  mov     r9d, r12d; xRight
0x1803080ca  mov     [rsp+140h+yBottom], r13d; yBottom
0x1803080cf  xor     r8d, r8d; yTop
0x1803080d2  mov     [rsp+140h+h], rax
0x1803080d7  xor     edx, edx; xLeft
0x1803080d9  lea     rcx, [rbp+40h+rc]; lprc
0x1803080dd  call    cs:__imp_SetRect
0x1803080e3  mov     ecx, [rbp+40h+rc.bottom]
0x1803080e6  mov     r8d, [rbp+40h+rc.top]; y
0x1803080ea  sub     ecx, r8d
0x1803080ed  mov     r9d, [rbp+40h+rc.right]
0x1803080f1  mov     edx, [rbp+40h+rc.left]; x
0x1803080f4  sub     r9d, edx; w
0x1803080f7  mov     [rsp+140h+rop], 0F00021h; rop
0x1803080ff  mov     [rsp+140h+yBottom], ecx; h
0x180308103  mov     rcx, rbx; hdc
0x180308106  call    cs:__imp_PatBlt
0x18030810c  mov     edx, 1; mode
0x180308111  mov     rcx, rbx; hdc
0x180308114  call    cs:__imp_SetBkMode
0x18030811a  movdqa  xmm0, cs:__xmm@00000000000000000000000000000078
0x180308122  lea     rcx, [rbp+40h+lf]; lplf
0x180308126  movups  xmm1, xmmword ptr cs:aSegoeUiSymbol+10h; " Symbol"
0x18030812d  mov     qword ptr [rbp+40h+lf.lfWeight], 258h
0x180308135  movdqa  xmmword ptr [rbp+40h+lf.lfHeight], xmm0
0x18030813a  movups  xmm0, xmmword ptr cs:aSegoeUiSymbol; "Segoe UI Symbol"
0x180308141  mov     dword ptr [rbp+40h+lf.lfOutPrecision], 2040000h
0x180308148  movups  xmmword ptr [rbp+40h+lf.lfFaceName+10h], xmm1
0x18030814c  movups  xmmword ptr [rbp+40h+lf.lfFaceName], xmm0
0x180308150  xorps   xmm0, xmm0
0x180308153  movups  xmmword ptr [rbp+40h+lf.lfFaceName+20h], xmm0
0x180308157  movups  xmmword ptr [rbp+40h+lf.lfFaceName+30h], xmm0
0x18030815b  call    cs:__imp_CreateFontIndirectW
0x180308161  mov     rdx, rax; h
0x180308164  mov     [rbp+40h+ho], rax
0x180308168  mov     rcx, rbx; hdc
0x18030816b  call    cs:__imp_SelectObject
0x180308171  mov     r8d, dword ptr [rsp+140h+var_E0.BlendOp]
0x180308176  lea     r9, [rsp+140h+String]; lpString
0x18030817b  mov     edx, [rsp+140h+var_D8]
0x18030817f  add     r8d, 0FFFFFFBBh; y
0x180308183  add     edx, 0FFFFFFE2h; x
0x180308186  mov     [rsp+140h+var_C8], rax
0x18030818b  mov     rcx, rbx; hdc
0x18030818e  mov     dword ptr [rsp+140h+String], 27592759h
0x180308196  mov     [rsp+140h+yBottom], 2; c
0x18030819e  call    cs:__imp_TextOutW
0x1803081a4  mov     rcx, [r14]; hdcDest
0x1803081a7  mov     r9d, r12d; wDest
0x1803081aa  mov     dword ptr [rsp+140h+var_E0.BlendOp], 960000h
0x1803081b2  xor     r8d, r8d; yoriginDest
0x1803081b5  mov     eax, dword ptr [rsp+140h+var_E0.BlendOp]
0x1803081b9  xor     edx, edx; xoriginDest
0x1803081bb  mov     dword ptr [rsp+140h+ftn.BlendOp], eax; ftn
0x1803081bf  mov     eax, [rbp+40h+rc.bottom]
0x1803081c2  mov     [rsp+140h+hSrc], eax; hSrc
0x1803081c6  mov     eax, [rbp+40h+rc.right]
0x1803081c9  mov     [rsp+140h+wSrc], eax; wSrc
0x1803081cd  mov     eax, [rbp+40h+rc.top]
0x1803081d0  mov     [rsp+140h+yoriginSrc], eax; yoriginSrc
0x1803081d4  mov     eax, [rbp+40h+rc.left]
0x1803081d7  mov     [rsp+140h+xoriginSrc], eax; xoriginSrc
0x1803081db  mov     qword ptr [rsp+140h+rop], rbx; hdcSrc
0x1803081e0  mov     [rsp+140h+yBottom], r13d; hDest
0x1803081e5  call    cs:__imp_AlphaBlend
0x1803081eb  mov     rax, [rsp+140h+h]
0x1803081f0  test    rax, rax
0x1803081f3  jz      short loc_180308201
0x1803081f5  mov     rdx, rax; h
0x1803081f8  mov     rcx, rbx; hdc
0x1803081fb  call    cs:__imp_SelectObject
0x180308201  test    rdi, rdi
0x180308204  jz      short loc_18030820F
0x180308206  mov     rcx, rdi; ho
0x180308209  call    cs:__imp_DeleteObject
0x18030820f  mov     rax, [rsp+140h+var_C8]
0x180308214  test    rax, rax
0x180308217  jz      short loc_180308225
0x180308219  mov     rdx, rax; h
0x18030821c  mov     rcx, rbx; hdc
0x18030821f  call    cs:__imp_SelectObject
0x180308225  mov     rcx, [rbp+40h+ho]; ho
0x180308229  test    rcx, rcx
0x18030822c  jz      short loc_180308234
0x18030822e  call    cs:__imp_DeleteObject
0x180308234  test    r15, r15
0x180308237  jz      short loc_180308245
0x180308239  mov     rdx, r15; h
0x18030823c  mov     rcx, rbx; hdc
0x18030823f  call    cs:__imp_SelectObject
0x180308245  mov     rcx, rsi; ho
0x180308248  call    cs:__imp_DeleteObject
0x18030824e  test    rbx, rbx
0x180308251  jz      short loc_18030825C
0x180308253  mov     rcx, rbx; hdc
0x180308256  call    cs:__imp_DeleteDC
0x18030825c  mov     rcx, [rbp+40h+var_40]
0x180308260  xor     rcx, rsp; StackCookie
0x180308263  call    __security_check_cookie
0x180308268  mov     rbx, [rsp+140h+arg_0]
0x180308270  add     rsp, 110h
0x180308277  pop     r15
0x180308279  pop     r14
0x18030827b  pop     r13
0x18030827d  pop     r12
0x18030827f  pop     rdi
0x180308280  pop     rsi
0x180308281  pop     rbp
0x180308282  retn
```
