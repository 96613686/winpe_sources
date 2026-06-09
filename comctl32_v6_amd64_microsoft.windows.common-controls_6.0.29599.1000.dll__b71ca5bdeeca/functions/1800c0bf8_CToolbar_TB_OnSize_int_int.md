# CToolbar::TB_OnSize(int,int)

- ea: `0x1800c0bf8`
- end: `0x1800c0ef8`
- name: `?TB_OnSize@CToolbar@@AEAAXHH@Z`
- size: `768`
- prototype: `void __fastcall(CToolbar *__hidden this, int xRight, int yBottom)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800134f0`

## callees

- `0x180017714`
- `0x1800c0bf8`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800c0d28`
- `USER32!IsRectEmpty` at `0x1800c0d3a`
- `USER32!IsRectEmpty` at `0x1800c0d28`
- `USER32!IsRectEmpty` at `0x1800c0d3a`
- `USER32!IntersectRect` at `0x1800c0eb1`
- `USER32!IntersectRect` at `0x1800c0ec7`
- `USER32!IntersectRect` at `0x1800c0eb1`
- `USER32!IntersectRect` at `0x1800c0ec7`
- `USER32!GetWindowRect` at `0x1800c0d10`
- `USER32!GetWindowRect` at `0x1800c0d10`
- `USER32!GetClientRect` at `0x1800c0d1e`
- `USER32!GetClientRect` at `0x1800c0d1e`
- `USER32!SetRect` at `0x1800c0ccd`
- `USER32!SetRect` at `0x1800c0d94`
- `USER32!SetRect` at `0x1800c0dd3`
- `USER32!SetRect` at `0x1800c0e37`
- `USER32!SetRect` at `0x1800c0e6e`
- `USER32!SetRect` at `0x1800c0ccd`
- `USER32!SetRect` at `0x1800c0d94`
- `USER32!SetRect` at `0x1800c0dd3`
- `USER32!SetRect` at `0x1800c0e37`
- `USER32!SetRect` at `0x1800c0e6e`
- `USER32!InvalidateRect` at `0x1800c0da8`
- `USER32!InvalidateRect` at `0x1800c0de7`
- `USER32!InvalidateRect` at `0x1800c0ef0`
- `USER32!InvalidateRect` at `0x1800c0da8`
- `USER32!InvalidateRect` at `0x1800c0de7`
- `USER32!InvalidateRect` at `0x1800c0ef0`
- `UxTheme!GetThemeMargins` at `0x1800c0ca6`
- `UxTheme!GetThemeMargins` at `0x1800c0ca6`

## pseudocode

```c
void __fastcall CToolbar::TB_OnSize(CToolbar *this, int xRight, int yBottom)
{
  int v6; // r13d
  int v7; // r15d
  void *v8; // rcx
  HWND v9; // rcx
  int v10; // edx
  int v11; // r8d
  int v12; // ecx
  int v13; // r9d
  int v14; // r8d
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // r9d
  int v19; // r8d
  signed int i; // r14d
  struct tagRECT Rect; // [rsp+40h] [rbp-29h] BYREF
  MARGINS pMargins; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT rcDst; // [rsp+70h] [rbp+7h] BYREF

  (*(void (__fastcall **)(CToolbar *))(*(_QWORD *)this + 16LL))(this);
  v6 = *((_DWORD *)this + 98) - *((_DWORD *)this + 96);
  v7 = *((_DWORD *)this + 99) - *((_DWORD *)this + 97);
  if ( *((char *)this + 120) < 0 )
  {
    v9 = (HWND)*((_QWORD *)this + 7);
    pMargins = 0;
    Rect = 0;
    GetWindowRect(v9, &Rect);
    GetClientRect(*((HWND *)this + 7), (LPRECT)&pMargins);
    if ( !IsRectEmpty(&Rect)
      && !IsRectEmpty((const RECT *)&pMargins)
      && (Rect.right - Rect.left != pMargins.cyTopHeight - pMargins.cxLeftWidth
       || Rect.bottom - Rect.top != pMargins.cyBottomHeight - pMargins.cxRightWidth) )
    {
      *((_DWORD *)this + 30) &= ~0x80u;
    }
  }
  if ( (*((_BYTE *)this + 120) & 0x10) != 0 )
  {
    v12 = yBottom;
    v13 = *((_DWORD *)this + 98);
    v14 = *((_DWORD *)this + 97);
    if ( *((_DWORD *)this + 99) < yBottom )
      v12 = *((_DWORD *)this + 99);
    pMargins = 0;
    rc = 0;
    if ( v13 <= xRight )
    {
      if ( v13 < xRight )
      {
        v15 = v13;
        v13 = xRight;
        goto LABEL_25;
      }
      v13 = xRight;
    }
    v15 = xRight;
LABEL_25:
    SetRect((LPRECT)&pMargins, v15, v14, v13, v12);
    v16 = *((_DWORD *)this + 99);
    v17 = yBottom;
    v18 = xRight;
    v19 = yBottom;
    if ( v16 > yBottom )
      v17 = *((_DWORD *)this + 99);
    if ( *((_DWORD *)this + 98) < xRight )
      v18 = *((_DWORD *)this + 98);
    if ( v16 < yBottom )
      v19 = *((_DWORD *)this + 99);
    SetRect(&rc, *((_DWORD *)this + 96), v19, v18, v17);
    for ( i = 0; i < *((_DWORD *)this + 66); ++i )
    {
      rcDst = 0;
      Rect = 0;
      if ( (unsigned int)CToolbar::TB_GetItemRect(this, i, &Rect)
        && (IntersectRect(&rcDst, &Rect, (const RECT *)&pMargins) || IntersectRect(&rcDst, &Rect, &rc)) )
      {
        InvalidateRect(*((HWND *)this + 7), &Rect, 1);
      }
    }
  }
  v8 = (void *)*((_QWORD *)this + 51);
  if ( v8 )
  {
    pMargins = 0;
    Rect = 0;
    GetThemeMargins(v8, 0, 0, 0, 3601, 0, &pMargins);
    if ( xRight != v6 )
    {
      v10 = xRight;
      if ( *((_DWORD *)this + 98) < xRight )
        v10 = *((_DWORD *)this + 98);
      SetRect(&Rect, v10 - pMargins.cxRightWidth, 0, xRight, yBottom);
      InvalidateRect(*((HWND *)this + 7), &Rect, 1);
    }
    if ( yBottom != v7 )
    {
      v11 = yBottom;
      if ( *((_DWORD *)this + 99) < yBottom )
        v11 = *((_DWORD *)this + 99);
      SetRect(&Rect, 0, v11 - pMargins.cyBottomHeight, xRight, yBottom);
      InvalidateRect(*((HWND *)this + 7), &Rect, 1);
    }
  }
  SetRect((LPRECT)this + 24, 0, 0, xRight, yBottom);
}

```

## disassembly

```asm
0x1800c0bf8  mov     [rsp-8+arg_18], rbx
0x1800c0bfd  push    rbp
0x1800c0bfe  push    rsi
0x1800c0bff  push    rdi
0x1800c0c00  push    r12
0x1800c0c02  push    r13
0x1800c0c04  push    r14
0x1800c0c06  push    r15
0x1800c0c08  lea     rbp, [rsp-27h]
0x1800c0c0d  sub     rsp, 90h
0x1800c0c14  mov     rax, cs:__security_cookie
0x1800c0c1b  xor     rax, rsp
0x1800c0c1e  mov     [rbp+57h+var_40], rax
0x1800c0c22  mov     rax, [rcx]
0x1800c0c25  mov     esi, r8d
0x1800c0c28  mov     edi, edx
0x1800c0c2a  mov     rbx, rcx
0x1800c0c2d  mov     rax, [rax+10h]
0x1800c0c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0c36  mov     r13d, [rbx+188h]
0x1800c0c3d  lea     r12, [rbx+180h]
0x1800c0c44  mov     r15d, [rbx+18Ch]
0x1800c0c4b  sub     r13d, [r12]
0x1800c0c4f  sub     r15d, [rbx+184h]
0x1800c0c56  test    byte ptr [rbx+78h], 80h
0x1800c0c5a  jnz     loc_1800C0CFA
0x1800c0c60  test    byte ptr [rbx+78h], 10h
0x1800c0c64  jnz     loc_1800C0DF2
0x1800c0c6a  mov     rcx, [rbx+198h]; hTheme
0x1800c0c71  test    rcx, rcx
0x1800c0c74  jz      short loc_1800C0CBE
0x1800c0c76  lea     rax, [rbp+57h+var_70]
0x1800c0c7a  xorps   xmm0, xmm0
0x1800c0c7d  mov     [rsp+0C0h+pMargins], rax; pMargins
0x1800c0c82  xorps   xmm1, xmm1
0x1800c0c85  mov     [rsp+0C0h+prc], 0; prc
0x1800c0c8e  xor     r9d, r9d; iStateId
0x1800c0c91  xor     r8d, r8d; iPartId
0x1800c0c94  mov     [rsp+0C0h+iPropId], 0E11h; iPropId
0x1800c0c9c  xor     edx, edx; hdc
0x1800c0c9e  movups  xmmword ptr [rbp+57h+var_70.cxLeftWidth], xmm0
0x1800c0ca2  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x1800c0ca6  call    cs:__imp_GetThemeMargins
0x1800c0cac  cmp     edi, r13d
0x1800c0caf  jnz     loc_1800C0D76
0x1800c0cb5  cmp     esi, r15d
0x1800c0cb8  jnz     loc_1800C0DB3
0x1800c0cbe  mov     r9d, edi; xRight
0x1800c0cc1  mov     [rsp+0C0h+iPropId], esi; yBottom
0x1800c0cc5  xor     r8d, r8d; yTop
0x1800c0cc8  xor     edx, edx; xLeft
0x1800c0cca  mov     rcx, r12; lprc
0x1800c0ccd  call    cs:__imp_SetRect
0x1800c0cd3  mov     rcx, [rbp+57h+var_40]
0x1800c0cd7  xor     rcx, rsp; StackCookie
0x1800c0cda  call    __security_check_cookie
0x1800c0cdf  mov     rbx, [rsp+0C0h+arg_18]
0x1800c0ce7  add     rsp, 90h
0x1800c0cee  pop     r15
0x1800c0cf0  pop     r14
0x1800c0cf2  pop     r13
0x1800c0cf4  pop     r12
0x1800c0cf6  pop     rdi
0x1800c0cf7  pop     rsi
0x1800c0cf8  pop     rbp
0x1800c0cf9  retn
0x1800c0cfa  mov     rcx, [rbx+38h]; hWnd
0x1800c0cfe  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800c0d02  xorps   xmm0, xmm0
0x1800c0d05  xorps   xmm1, xmm1
0x1800c0d08  movups  xmmword ptr [rbp+57h+var_70.cxLeftWidth], xmm0
0x1800c0d0c  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x1800c0d10  call    cs:__imp_GetWindowRect
0x1800c0d16  mov     rcx, [rbx+38h]; hWnd
0x1800c0d1a  lea     rdx, [rbp+57h+var_70]; lpRect
0x1800c0d1e  call    cs:__imp_GetClientRect
0x1800c0d24  lea     rcx, [rbp+57h+Rect]; lprc
0x1800c0d28  call    cs:__imp_IsRectEmpty
0x1800c0d2e  test    eax, eax
0x1800c0d30  jnz     loc_1800C0C60
0x1800c0d36  lea     rcx, [rbp+57h+var_70]; lprc
0x1800c0d3a  call    cs:__imp_IsRectEmpty
0x1800c0d40  test    eax, eax
0x1800c0d42  jnz     loc_1800C0C60
0x1800c0d48  mov     ecx, [rbp+57h+var_70.cyTopHeight]
0x1800c0d4b  mov     eax, [rbp+57h+Rect.right]
0x1800c0d4e  sub     ecx, [rbp+57h+var_70.cxLeftWidth]
0x1800c0d51  sub     eax, [rbp+57h+Rect.left]
0x1800c0d54  cmp     eax, ecx
0x1800c0d56  jnz     short loc_1800C0D6C
0x1800c0d58  mov     ecx, [rbp+57h+var_70.cyBottomHeight]
0x1800c0d5b  mov     eax, [rbp+57h+Rect.bottom]
0x1800c0d5e  sub     ecx, [rbp+57h+var_70.cxRightWidth]
0x1800c0d61  sub     eax, [rbp+57h+Rect.top]
0x1800c0d64  cmp     eax, ecx
0x1800c0d66  jz      loc_1800C0C60
0x1800c0d6c  btr     dword ptr [rbx+78h], 7
0x1800c0d71  jmp     loc_1800C0C60
0x1800c0d76  mov     eax, [rbx+188h]
0x1800c0d7c  lea     rcx, [rbp+57h+Rect]; lprc
0x1800c0d80  cmp     eax, edi
0x1800c0d82  mov     [rsp+0C0h+iPropId], esi; yBottom
0x1800c0d86  mov     edx, edi
0x1800c0d88  mov     r9d, edi; xRight
0x1800c0d8b  cmovl   edx, eax
0x1800c0d8e  xor     r8d, r8d; yTop
0x1800c0d91  sub     edx, [rbp+57h+var_70.cxRightWidth]; xLeft
0x1800c0d94  call    cs:__imp_SetRect
0x1800c0d9a  mov     rcx, [rbx+38h]; hWnd
0x1800c0d9e  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800c0da2  mov     r8d, 1; bErase
0x1800c0da8  call    cs:__imp_InvalidateRect
0x1800c0dae  jmp     loc_1800C0CB5
0x1800c0db3  mov     eax, [rbx+18Ch]
0x1800c0db9  lea     rcx, [rbp+57h+Rect]; lprc
0x1800c0dbd  cmp     eax, esi
0x1800c0dbf  mov     [rsp+0C0h+iPropId], esi; yBottom
0x1800c0dc3  mov     r8d, esi
0x1800c0dc6  mov     r9d, edi; xRight
0x1800c0dc9  cmovl   r8d, eax
0x1800c0dcd  xor     edx, edx; xLeft
0x1800c0dcf  sub     r8d, [rbp+57h+var_70.cyBottomHeight]; yTop
0x1800c0dd3  call    cs:__imp_SetRect
0x1800c0dd9  mov     rcx, [rbx+38h]; hWnd
0x1800c0ddd  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800c0de1  mov     r8d, 1; bErase
0x1800c0de7  call    cs:__imp_InvalidateRect
0x1800c0ded  jmp     loc_1800C0CBE
0x1800c0df2  mov     eax, [rbx+18Ch]
0x1800c0df8  mov     ecx, esi
0x1800c0dfa  mov     r9d, [rbx+188h]
0x1800c0e01  cmp     eax, esi
0x1800c0e03  mov     r8d, [rbx+184h]; yTop
0x1800c0e0a  xorps   xmm0, xmm0
0x1800c0e0d  cmovl   ecx, eax
0x1800c0e10  xorps   xmm1, xmm1
0x1800c0e13  movups  xmmword ptr [rbp+57h+var_70.cxLeftWidth], xmm0
0x1800c0e17  movups  xmmword ptr [rbp+57h+rc.left], xmm1
0x1800c0e1b  cmp     r9d, edi
0x1800c0e1e  jg      short loc_1800C0E25
0x1800c0e20  jl      short loc_1800C0E29
0x1800c0e22  mov     r9d, edi
0x1800c0e25  mov     edx, edi
0x1800c0e27  jmp     short loc_1800C0E2F
0x1800c0e29  mov     edx, r9d; xLeft
0x1800c0e2c  mov     r9d, edi; xRight
0x1800c0e2f  mov     [rsp+0C0h+iPropId], ecx; yBottom
0x1800c0e33  lea     rcx, [rbp+57h+var_70]; lprc
0x1800c0e37  call    cs:__imp_SetRect
0x1800c0e3d  mov     ecx, [rbx+18Ch]
0x1800c0e43  mov     edx, esi
0x1800c0e45  mov     eax, [rbx+188h]
0x1800c0e4b  cmp     ecx, esi
0x1800c0e4d  mov     r9d, edi
0x1800c0e50  mov     r8d, esi
0x1800c0e53  cmovg   edx, ecx
0x1800c0e56  cmp     eax, edi
0x1800c0e58  mov     [rsp+0C0h+iPropId], edx; yBottom
0x1800c0e5c  mov     edx, [r12]; xLeft
0x1800c0e60  cmovl   r9d, eax; xRight
0x1800c0e64  cmp     ecx, esi
0x1800c0e66  cmovl   r8d, ecx; yTop
0x1800c0e6a  lea     rcx, [rbp+57h+rc]; lprc
0x1800c0e6e  call    cs:__imp_SetRect
0x1800c0e74  xor     r14d, r14d
0x1800c0e77  cmp     [rbx+108h], r14d
0x1800c0e7e  jle     loc_1800C0C6A
0x1800c0e84  xorps   xmm0, xmm0
0x1800c0e87  lea     r8, [rbp+57h+Rect]; struct tagRECT *
0x1800c0e8b  xorps   xmm1, xmm1
0x1800c0e8e  mov     edx, r14d; unsigned int
0x1800c0e91  mov     rcx, rbx; this
0x1800c0e94  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800c0e98  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x1800c0e9c  call    ?TB_GetItemRect@CToolbar@@AEAAHIPEAUtagRECT@@@Z; CToolbar::TB_GetItemRect(uint,tagRECT *)
0x1800c0ea1  test    eax, eax
0x1800c0ea3  jz      short loc_1800C0ED1
0x1800c0ea5  lea     r8, [rbp+57h+var_70]; lprcSrc2
0x1800c0ea9  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x1800c0ead  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800c0eb1  call    cs:__imp_IntersectRect
0x1800c0eb7  test    eax, eax
0x1800c0eb9  jnz     short loc_1800C0EE2
0x1800c0ebb  lea     r8, [rbp+57h+rc]; lprcSrc2
0x1800c0ebf  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x1800c0ec3  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800c0ec7  call    cs:__imp_IntersectRect
0x1800c0ecd  test    eax, eax
0x1800c0ecf  jnz     short loc_1800C0EE2
0x1800c0ed1  inc     r14d
0x1800c0ed4  cmp     r14d, [rbx+108h]
0x1800c0edb  jl      short loc_1800C0E84
0x1800c0edd  jmp     loc_1800C0C6A
0x1800c0ee2  mov     rcx, [rbx+38h]; hWnd
0x1800c0ee6  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800c0eea  mov     r8d, 1; bErase
0x1800c0ef0  call    cs:__imp_InvalidateRect
0x1800c0ef6  jmp     short loc_1800C0ED1
```
