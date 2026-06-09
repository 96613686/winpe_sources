# CToolTipsMgr::RenderTitledTip(HDC__ *,tagRECT *,uint)

- ea: `0x180074c1c`
- end: `0x1800751df`
- name: `?RenderTitledTip@CToolTipsMgr@@AEAAHPEAUHDC__@@PEAUtagRECT@@I@Z`
- size: `1475`
- prototype: `__int64 __fastcall(CToolTipsMgr *__hidden this, HDC, struct tagRECT *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180073438`
- `0x180074148`

## callees

- `0x1800725b4`
- `0x180073340`
- `0x180074c1c`
- `0x1800b16b0`
- `0x180114520`
- `0x180114ebc`
- `0x180132374`
- `0x1801323f0`
- `0x18013296c`
- `0x180132a00`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007506e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007506e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074cc0`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074fbc`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074cc0`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074fbc`
- `GDI32!DeleteObject` at `0x1800750c8`
- `GDI32!DeleteObject` at `0x1800750c8`
- `GDI32!GetObjectW` at `0x180074e09`
- `GDI32!GetObjectW` at `0x180074e09`
- `GDI32!SetBkMode` at `0x180074d69`
- `GDI32!SetBkMode` at `0x1800751b4`
- `GDI32!SetBkMode` at `0x180074d69`
- `GDI32!SetBkMode` at `0x1800751b4`
- `GDI32!SetTextColor` at `0x180074d57`
- `GDI32!SetTextColor` at `0x180075132`
- `GDI32!SetTextColor` at `0x1800751a7`
- `GDI32!SetTextColor` at `0x180074d57`
- `GDI32!SetTextColor` at `0x180075132`
- `GDI32!SetTextColor` at `0x1800751a7`
- `GDI32!GetTextMetricsW` at `0x180074e87`
- `GDI32!GetTextMetricsW` at `0x180074e87`
- `GDI32!SelectObject` at `0x180074e30`
- `GDI32!SelectObject` at `0x1800750bf`
- `GDI32!SelectObject` at `0x180074e30`
- `GDI32!SelectObject` at `0x1800750bf`
- `GDI32!CreateFontIndirectW` at `0x180074e1a`
- `GDI32!CreateFontIndirectW` at `0x180074e1a`
- `GDI32!GetCurrentObject` at `0x180074db0`
- `GDI32!GetCurrentObject` at `0x180074db0`
- `USER32!DrawTextW` at `0x18007508e`
- `USER32!DrawTextW` at `0x18007508e`
- `USER32!SetRect` at `0x180074f6b`
- `USER32!SetRect` at `0x18007503a`
- `USER32!SetRect` at `0x180074f6b`
- `USER32!SetRect` at `0x18007503a`
- `USER32!GetSystemMetricsForDpi` at `0x180074ea1`
- `USER32!GetSystemMetricsForDpi` at `0x180074eda`
- `USER32!GetSystemMetricsForDpi` at `0x180074ea1`
- `USER32!GetSystemMetricsForDpi` at `0x180074eda`
- `UxTheme!GetThemeTextMetrics` at `0x180074e76`
- `UxTheme!GetThemeTextMetrics` at `0x180074e76`
- `UxTheme!GetThemeFont` at `0x180074df3`
- `UxTheme!GetThemeFont` at `0x180074df3`
- `UxTheme!GetThemeColor` at `0x180074d3a`
- `UxTheme!GetThemeColor` at `0x180074d3a`

## pseudocode

```c
__int64 __fastcall CToolTipsMgr::RenderTitledTip(CToolTipsMgr *this, HDC a2, struct tagRECT *a3, int a4)
{
  struct tagRECT *v5; // r13
  int v8; // ebx
  int v9; // r12d
  int v10; // r15d
  int v11; // r14d
  __int64 v12; // rax
  int v13; // ecx
  void *v14; // rcx
  COLORREF v15; // edx
  _WORD *v16; // rcx
  HGDIOBJ CurrentObject; // rax
  void *v18; // r10
  void *v19; // r13
  HFONT v20; // rax
  void *v21; // rcx
  HRESULT ThemeTextMetrics; // ebx
  LONG SystemMetricsForDpi; // eax
  LONG tmHeight; // ecx
  int v25; // eax
  COLORREF v26; // r13d
  bool v27; // zf
  _DWORD *v28; // rbx
  int v29; // r9d
  void *v30; // rdx
  int v31; // eax
  _DWORD *v32; // r13
  void *v33; // rdx
  int v34; // eax
  int v35; // eax
  int right; // ecx
  struct IControlMarkup *CurToolBestMarkup; // rax
  struct IControlMarkup *v38; // rax
  int bottom; // ecx
  int left; // edx
  int y; // [rsp+20h] [rbp-E0h]
  struct DPISCALEINFO *ya; // [rsp+20h] [rbp-E0h]
  int yTop; // [rsp+30h] [rbp-D0h]
  COLORREF color; // [rsp+38h] [rbp-C8h]
  int mode; // [rsp+3Ch] [rbp-C4h]
  HGDIOBJ h; // [rsp+48h] [rbp-B8h]
  HFONT ho; // [rsp+58h] [rbp-A8h]
  struct tagRECT v50; // [rsp+60h] [rbp-A0h] BYREF
  COLORREF pColor; // [rsp+70h] [rbp-90h] BYREF
  int x[4]; // [rsp+78h] [rbp-88h] BYREF
  TEXTMETRICW ptm; // [rsp+88h] [rbp-78h] BYREF
  LOGFONTW pFont; // [rsp+D0h] [rbp-30h] BYREF

  v5 = a3;
  if ( !*((_DWORD *)this + 42) )
    return 0;
  v8 = *((_DWORD *)this + 6) & 0x40;
  color = 0;
  v9 = a4 & 0x400;
  mode = 0;
  v10 = 0;
  v11 = 0;
  *(struct tagRECT *)x = *a3;
  if ( *((_DWORD *)this + 43) )
  {
    if ( (a4 & 0x400) == 0 )
    {
      v12 = *((_QWORD *)this + 24);
      if ( v12 )
      {
        if ( v12 == *((_QWORD *)this + 22) )
          v13 = MulDiv(3, *((_DWORD *)this + 16), 96);
        else
          v13 = 0;
        ImageList_Draw(*((HIMAGELIST *)this + 24), *((_DWORD *)this + 43) - 1, a2, x[0], x[1] + v13, 1u);
      }
    }
    v10 = *((_DWORD *)this + 71);
    x[0] += v10;
  }
  if ( !v9 )
  {
    v14 = (void *)*((_QWORD *)this + 36);
    pColor = 0;
    if ( v14 && GetThemeColor(v14, v8 != 0 ? 4 : 2, 0, 3803, &pColor) >= 0 )
    {
      v15 = pColor;
    }
    else
    {
      v15 = *((_DWORD *)this + 57);
      pColor = v15;
    }
    color = SetTextColor(a2, v15);
    mode = SetBkMode(a2, 1);
  }
  v16 = (_WORD *)*((_QWORD *)this + 20);
  if ( v16 && *v16 )
  {
    memset_0(&pFont, 0, sizeof(pFont));
    CurrentObject = GetCurrentObject(a2, 6u);
    v18 = (void *)*((_QWORD *)this + 36);
    v19 = CurrentObject;
    h = CurrentObject;
    if ( !v18 || GetThemeFont(v18, a2, v8 != 0 ? 4 : 2, 0, 210, &pFont) < 0 )
    {
      GetObjectW(v19, 92, &pFont);
      pFont.lfWeight = 700;
    }
    v20 = CreateFontIndirectW(&pFont);
    ho = v20;
    if ( v20 )
      h = SelectObject(a2, v20);
    v21 = (void *)*((_QWORD *)this + 36);
    memset(&ptm, 0, sizeof(ptm));
    if ( v21 )
      ThemeTextMetrics = GetThemeTextMetrics(v21, a2, v8 != 0 ? 4 : 2, 0, &ptm);
    else
      ThemeTextMetrics = !GetTextMetricsW(a2, &ptm) ? 0x80004005 : 0;
    SystemMetricsForDpi = GetSystemMetricsForDpi(50, *((unsigned int *)this + 16));
    if ( ThemeTextMetrics < 0 )
    {
      v25 = x[1] + SystemMetricsForDpi;
      yTop = x[1];
    }
    else
    {
      tmHeight = ptm.tmHeight;
      if ( SystemMetricsForDpi > ptm.tmHeight )
        tmHeight = SystemMetricsForDpi;
      yTop = x[1];
      v25 = tmHeight + x[1];
    }
    x[3] = v25;
    if ( v9 )
    {
      v26 = x[0] + 10 * GetSystemMetricsForDpi(11, *((unsigned int *)this + 15));
      x[2] = v26;
      yTop = x[1];
    }
    else
    {
      v26 = x[2];
    }
    v27 = *((_BYTE *)this + 24) >= 0;
    pColor = v26;
    if ( !v27 )
    {
      v28 = (_DWORD *)((char *)this + 384);
      CCloseButton::CalculateSize((SIZE *)this + 48, *((HTHEME *)this + 36), a2, (CToolTipsMgr *)((char *)this + 60));
      if ( v9 )
      {
        v11 = *((_DWORD *)this + 97);
        v10 += *v28;
        if ( v11 < 0 )
          v11 = 0;
      }
      else
      {
        v29 = v26;
        v26 -= *v28;
        y = yTop + *((_DWORD *)this + 97);
        pColor = v26;
        SetRect((LPRECT)((char *)this + 396), v26, yTop, v29, y);
        v30 = (void *)*((_QWORD *)this + 36);
        v50 = *(struct tagRECT *)((char *)this + 396);
        CCloseButton::Draw((CToolTipsMgr *)((char *)this + 384), v30, a2, &v50);
        x[2] -= *((_DWORD *)this + 96);
      }
      if ( *((char *)this + 24) < 0 )
      {
        if ( (*((_DWORD *)this + 6) & 0x400) == 0 )
        {
LABEL_52:
          v34 = lstrlenW(*((LPCWSTR *)this + 20));
          DrawTextW(a2, *((LPCWSTR *)this + 20), v34, (LPRECT)x, a4 | 0x20);
          v35 = ptm.tmHeight + 1;
          if ( v11 > ptm.tmHeight + 1 )
            v35 = v11;
          v11 = v35;
          v10 += x[2] - x[0];
          if ( ho )
          {
            SelectObject(a2, h);
            DeleteObject(ho);
          }
          v5 = a3;
          goto LABEL_57;
        }
        v31 = MulDiv(1, *((_DWORD *)this + 15), 96);
        if ( v9 )
          v10 += v31;
        else
          pColor = v26 - v31;
      }
    }
    if ( (*((_DWORD *)this + 6) & 0x400) != 0 )
    {
      v32 = (_DWORD *)((char *)this + 416);
      CWrenchButton::CalculateSize((SIZE *)this + 52, *((HTHEME *)this + 36), a2, (CToolTipsMgr *)((char *)this + 60));
      if ( v9 )
      {
        if ( v11 <= *((_DWORD *)this + 105) )
          v11 = *((_DWORD *)this + 105);
        v10 += *v32;
      }
      else
      {
        SetRect((LPRECT)((char *)this + 440), pColor - *v32, yTop, pColor, yTop + *((_DWORD *)this + 105));
        v33 = (void *)*((_QWORD *)this + 36);
        v50 = *(struct tagRECT *)((char *)this + 440);
        CWrenchButton::Draw((CToolTipsMgr *)((char *)this + 416), v33, a2, &v50, ya);
        x[2] -= *v32;
      }
    }
    goto LABEL_52;
  }
LABEL_57:
  x[1] += v11;
  right = v5->right;
  x[2] = right;
  if ( v9 )
    x[2] = *((_DWORD *)this + 71) + right;
  CToolTipsMgr::SetThemeRenderFlags(this, a4 & 0xFFFFFFDF);
  CurToolBestMarkup = CToolTipsMgr::GetCurToolBestMarkup(this);
  (*(void (__fastcall **)(struct IControlMarkup *, HDC, __int64, int *))(*(_QWORD *)CurToolBestMarkup + 160LL))(
    CurToolBestMarkup,
    a2,
    1,
    x);
  if ( !v9 )
  {
    SetTextColor(a2, *((_DWORD *)this + 57));
    v38 = CToolTipsMgr::GetCurToolBestMarkup(this);
    (*(void (__fastcall **)(struct IControlMarkup *, HDC, int *))(*(_QWORD *)v38 + 144LL))(v38, a2, x);
  }
  bottom = x[3];
  left = v5->left;
  if ( v5->bottom > x[3] )
    bottom = v5->bottom;
  x[3] = bottom;
  x[0] = left;
  if ( v10 <= x[2] - left )
    v10 = x[2] - left;
  if ( v9 )
  {
    v5->right = left + v10;
    v5->bottom = v11 + bottom + v5->top - x[1];
  }
  else
  {
    SetTextColor(a2, color);
    SetBkMode(a2, mode);
  }
  return 1;
}

```

## disassembly

```asm
0x180074c1c  push    rbp
0x180074c1e  push    rbx
0x180074c1f  push    rsi
0x180074c20  push    rdi
0x180074c21  push    r12
0x180074c23  push    r13
0x180074c25  push    r14
0x180074c27  push    r15
0x180074c29  lea     rbp, [rsp-48h]
0x180074c2e  sub     rsp, 148h
0x180074c35  mov     rax, cs:__security_cookie
0x180074c3c  xor     rax, rsp
0x180074c3f  mov     [rbp+80h+var_50], rax
0x180074c43  mov     rsi, rdx
0x180074c46  mov     [rsp+180h+var_130], r8
0x180074c4b  xor     edx, edx
0x180074c4d  mov     eax, r9d
0x180074c50  mov     r13, r8
0x180074c53  mov     [rsp+180h+var_14C], eax
0x180074c57  mov     rdi, rcx
0x180074c5a  cmp     [rcx+0A8h], edx
0x180074c60  jnz     short loc_180074C69
0x180074c62  xor     eax, eax
0x180074c64  jmp     loc_1800751BF
0x180074c69  mov     ebx, [rcx+18h]
0x180074c6c  mov     r12d, eax
0x180074c6f  movups  xmm0, xmmword ptr [r8]
0x180074c73  and     ebx, 40h
0x180074c76  mov     [rsp+180h+color], edx
0x180074c7a  and     r12d, 400h
0x180074c81  mov     [rsp+180h+mode], edx
0x180074c85  mov     r15d, edx
0x180074c88  mov     r14d, edx
0x180074c8b  movdqu  xmmword ptr [rsp+180h+x], xmm0
0x180074c91  cmp     [rcx+0ACh], edx
0x180074c97  jz      short loc_180074D06
0x180074c99  test    r12d, r12d
0x180074c9c  jnz     short loc_180074CFA
0x180074c9e  mov     rax, [rcx+0C0h]
0x180074ca5  test    rax, rax
0x180074ca8  jz      short loc_180074CFA
0x180074caa  cmp     rax, [rcx+0B0h]
0x180074cb1  jnz     short loc_180074CCA
0x180074cb3  mov     edx, [rcx+40h]; nNumerator
0x180074cb6  lea     r8d, [r12+60h]; nDenominator
0x180074cbb  lea     ecx, [r12+3]; nNumber
0x180074cc0  call    cs:__imp_MulDiv
0x180074cc6  mov     ecx, eax
0x180074cc8  jmp     short loc_180074CCC
0x180074cca  mov     ecx, edx
0x180074ccc  add     ecx, [rsp+180h+x+4]
0x180074cd0  mov     r8, rsi; hdcDst
0x180074cd3  mov     edx, [rdi+0ACh]
0x180074cd9  mov     r9d, [rsp+180h+x]; x
0x180074cde  dec     edx; i
0x180074ce0  mov     [rsp+180h+fStyle], 1; fStyle
0x180074ce8  mov     [rsp+180h+y], ecx; y
0x180074cec  mov     rcx, [rdi+0C0h]; himl
0x180074cf3  call    ImageList_Draw
0x180074cf8  xor     edx, edx
0x180074cfa  mov     r15d, [rdi+11Ch]
0x180074d01  add     [rsp+180h+x], r15d
0x180074d06  test    r12d, r12d
0x180074d09  jnz     short loc_180074D75
0x180074d0b  mov     rcx, [rdi+120h]; hTheme
0x180074d12  mov     [rsp+180h+pColor], edx
0x180074d16  test    rcx, rcx
0x180074d19  jz      short loc_180074D4A
0x180074d1b  mov     eax, ebx
0x180074d1d  mov     r9d, 0EDBh; iPropId
0x180074d23  neg     eax
0x180074d25  lea     rax, [rsp+180h+pColor]
0x180074d2a  sbb     edx, edx
0x180074d2c  mov     qword ptr [rsp+180h+y], rax; pColor
0x180074d31  and     edx, 2
0x180074d34  xor     r8d, r8d; iStateId
0x180074d37  add     edx, 2; iPartId
0x180074d3a  call    cs:__imp_GetThemeColor
0x180074d40  test    eax, eax
0x180074d42  js      short loc_180074D4A
0x180074d44  mov     edx, [rsp+180h+pColor]
0x180074d48  jmp     short loc_180074D54
0x180074d4a  mov     edx, [rdi+0E4h]; color
0x180074d50  mov     [rsp+180h+pColor], edx
0x180074d54  mov     rcx, rsi; hdc
0x180074d57  call    cs:__imp_SetTextColor
0x180074d5d  mov     edx, 1; mode
0x180074d62  mov     rcx, rsi; hdc
0x180074d65  mov     [rsp+180h+color], eax
0x180074d69  call    cs:__imp_SetBkMode
0x180074d6f  mov     [rsp+180h+mode], eax
0x180074d73  xor     edx, edx
0x180074d75  mov     rcx, [rdi+0A0h]
0x180074d7c  test    rcx, rcx
0x180074d7f  jz      loc_1800750D3
0x180074d85  cmp     [rcx], dx
0x180074d88  jz      loc_1800750D3
0x180074d8e  xor     edx, edx; Val
0x180074d90  lea     rcx, [rbp+80h+pFont]; void *
0x180074d94  lea     r8d, [rdx+5Ch]; Size
0x180074d98  call    memset_0
0x180074d9d  mov     eax, [rsp+180h+var_14C]
0x180074da1  mov     edx, 6; type
0x180074da6  or      eax, 20h
0x180074da9  mov     rcx, rsi; hdc
0x180074dac  mov     [rsp+180h+format], eax
0x180074db0  call    cs:__imp_GetCurrentObject
0x180074db6  mov     r10, [rdi+120h]
0x180074dbd  mov     r13, rax
0x180074dc0  mov     [rsp+180h+h], rax
0x180074dc5  test    r10, r10
0x180074dc8  jz      short loc_180074DFD
0x180074dca  mov     ecx, ebx
0x180074dcc  lea     rax, [rbp+80h+pFont]
0x180074dd0  neg     ecx
0x180074dd2  mov     qword ptr [rsp+180h+fStyle], rax; pFont
0x180074dd7  mov     rdx, rsi; hdc
0x180074dda  mov     [rsp+180h+y], 0D2h; iPropId
0x180074de2  sbb     r8d, r8d
0x180074de5  mov     rcx, r10; hTheme
0x180074de8  and     r8d, 2
0x180074dec  xor     r9d, r9d; iStateId
0x180074def  add     r8d, 2; iPartId
0x180074df3  call    cs:__imp_GetThemeFont
0x180074df9  test    eax, eax
0x180074dfb  jns     short loc_180074E16
0x180074dfd  lea     r8, [rbp+80h+pFont]; pv
0x180074e01  mov     edx, 5Ch ; '\'; c
0x180074e06  mov     rcx, r13; h
0x180074e09  call    cs:__imp_GetObjectW
0x180074e0f  mov     [rbp+80h+pFont.lfWeight], 2BCh
0x180074e16  lea     rcx, [rbp+80h+pFont]; lplf
0x180074e1a  call    cs:__imp_CreateFontIndirectW
0x180074e20  mov     [rsp+180h+ho], rax
0x180074e25  test    rax, rax
0x180074e28  jz      short loc_180074E3B
0x180074e2a  mov     rdx, rax; h
0x180074e2d  mov     rcx, rsi; hdc
0x180074e30  call    cs:__imp_SelectObject
0x180074e36  mov     [rsp+180h+h], rax
0x180074e3b  mov     rcx, [rdi+120h]; hTheme
0x180074e42  xorps   xmm0, xmm0
0x180074e45  movups  xmmword ptr [rbp+80h+ptm.tmOverhang], xmm0
0x180074e49  movups  xmmword ptr [rbp+80h+ptm.tmFirstChar], xmm0
0x180074e4d  movups  xmmword ptr [rbp+80h+ptm.tmHeight], xmm0
0x180074e51  movups  xmmword ptr [rbp+80h+ptm.tmExternalLeading], xmm0
0x180074e55  test    rcx, rcx
0x180074e58  jz      short loc_180074E80
0x180074e5a  neg     ebx
0x180074e5c  lea     rax, [rbp+80h+ptm]
0x180074e60  mov     rdx, rsi; hdc
0x180074e63  mov     qword ptr [rsp+180h+y], rax; ptm
0x180074e68  sbb     r8d, r8d
0x180074e6b  xor     r9d, r9d; iStateId
0x180074e6e  and     r8d, 2
0x180074e72  add     r8d, 2; iPartId
0x180074e76  call    cs:__imp_GetThemeTextMetrics
0x180074e7c  mov     ebx, eax
0x180074e7e  jmp     short loc_180074E99
0x180074e80  lea     rdx, [rbp+80h+ptm]; lptm
0x180074e84  mov     rcx, rsi; hdc
0x180074e87  call    cs:__imp_GetTextMetricsW
0x180074e8d  neg     eax
0x180074e8f  sbb     ebx, ebx
0x180074e91  not     ebx
0x180074e93  and     ebx, 80004005h
0x180074e99  mov     edx, [rdi+40h]
0x180074e9c  mov     ecx, 32h ; '2'
0x180074ea1  call    cs:__imp_GetSystemMetricsForDpi
0x180074ea7  test    ebx, ebx
0x180074ea9  js      short loc_180074EC0
0x180074eab  mov     ecx, [rbp+80h+ptm.tmHeight]
0x180074eae  cmp     eax, ecx
0x180074eb0  mov     edx, [rsp+180h+x+4]
0x180074eb4  cmovg   ecx, eax
0x180074eb7  mov     [rsp+180h+yTop], edx
0x180074ebb  lea     eax, [rcx+rdx]
0x180074ebe  jmp     short loc_180074ECA
0x180074ec0  mov     ecx, [rsp+180h+x+4]
0x180074ec4  add     eax, ecx
0x180074ec6  mov     [rsp+180h+yTop], ecx
0x180074eca  mov     [rbp+80h+x+0Ch], eax
0x180074ecd  test    r12d, r12d
0x180074ed0  jz      short loc_180074EF9
0x180074ed2  mov     edx, [rdi+3Ch]
0x180074ed5  mov     ecx, 0Bh
0x180074eda  call    cs:__imp_GetSystemMetricsForDpi
0x180074ee0  lea     ecx, [rax+rax*4]
0x180074ee3  mov     eax, [rsp+180h+x]
0x180074ee7  lea     r13d, [rax+rcx*2]
0x180074eeb  mov     eax, [rsp+180h+x+4]
0x180074eef  mov     [rbp+80h+x+8], r13d
0x180074ef3  mov     [rsp+180h+yTop], eax
0x180074ef7  jmp     short loc_180074EFD
0x180074ef9  mov     r13d, [rbp+80h+x+8]
0x180074efd  test    byte ptr [rdi+18h], 80h
0x180074f01  mov     [rsp+180h+pColor], r13d
0x180074f06  jz      loc_180074FD4
0x180074f0c  mov     rdx, [rdi+120h]; hTheme
0x180074f13  lea     rbx, [rdi+180h]
0x180074f1a  mov     rcx, rbx; psz
0x180074f1d  lea     r9, [rdi+3Ch]; struct DPISCALEINFO *
0x180074f21  mov     r8, rsi; hdc
0x180074f24  call    ?CalculateSize@CCloseButton@@QEAAXPEAXPEAUHDC__@@PEAUDPISCALEINFO@@@Z; CCloseButton::CalculateSize(void *,HDC__ *,DPISCALEINFO *)
0x180074f29  xor     ecx, ecx
0x180074f2b  test    r12d, r12d
0x180074f2e  jz      short loc_180074F40
0x180074f30  mov     r14d, [rbx+4]
0x180074f34  add     r15d, [rbx]
0x180074f37  test    r14d, r14d
0x180074f3a  cmovs   r14d, ecx
0x180074f3e  jmp     short loc_180074F9D
0x180074f40  mov     ecx, [rdi+184h]
0x180074f46  mov     r9d, r13d; xRight
0x180074f49  sub     r13d, [rbx]
0x180074f4c  lea     rbx, [rdi+18Ch]
0x180074f53  add     ecx, [rsp+180h+yTop]
0x180074f57  mov     edx, r13d; xLeft
0x180074f5a  mov     r8d, [rsp+180h+yTop]; yTop
0x180074f5f  mov     [rsp+180h+y], ecx; yBottom
0x180074f63  mov     rcx, rbx; lprc
0x180074f66  mov     [rsp+180h+pColor], r13d
0x180074f6b  call    cs:__imp_SetRect
0x180074f71  movups  xmm0, xmmword ptr [rbx]
0x180074f74  mov     rdx, [rdi+120h]; void *
0x180074f7b  lea     rbx, [rdi+180h]
0x180074f82  mov     rcx, rbx; this
0x180074f85  lea     r9, [rsp+180h+var_120]; struct tagRECT
0x180074f8a  mov     r8, rsi; HDC
0x180074f8d  movdqu  xmmword ptr [rsp+180h+var_120.left], xmm0
0x180074f93  call    ?Draw@CCloseButton@@QEAAXPEAXPEAUHDC__@@UtagRECT@@@Z; CCloseButton::Draw(void *,HDC__ *,tagRECT)
0x180074f98  mov     eax, [rbx]
0x180074f9a  sub     [rbp+80h+x+8], eax
0x180074f9d  test    byte ptr [rdi+18h], 80h
0x180074fa1  jz      short loc_180074FD4
0x180074fa3  test    dword ptr [rdi+18h], 400h
0x180074faa  jz      loc_180075067
0x180074fb0  mov     edx, [rdi+3Ch]; nNumerator
0x180074fb3  mov     ecx, 1; nNumber
0x180074fb8  lea     r8d, [rcx+5Fh]; nDenominator
0x180074fbc  call    cs:__imp_MulDiv
0x180074fc2  test    r12d, r12d
0x180074fc5  jz      short loc_180074FCC
0x180074fc7  add     r15d, eax
0x180074fca  jmp     short loc_180074FD4
0x180074fcc  sub     r13d, eax
0x180074fcf  mov     [rsp+180h+pColor], r13d
0x180074fd4  test    dword ptr [rdi+18h], 400h
0x180074fdb  jz      loc_180075067
0x180074fe1  mov     rdx, [rdi+120h]; hTheme
0x180074fe8  lea     r13, [rdi+1A0h]
0x180074fef  mov     rcx, r13; psz
0x180074ff2  lea     r9, [rdi+3Ch]; struct DPISCALEINFO *
0x180074ff6  mov     r8, rsi; hdc
0x180074ff9  call    ?CalculateSize@CWrenchButton@@QEAAXPEAXPEAUHDC__@@PEAUDPISCALEINFO@@@Z; CWrenchButton::CalculateSize(void *,HDC__ *,DPISCALEINFO *)
0x180074ffe  test    r12d, r12d
0x180075001  jz      short loc_180075012
0x180075003  cmp     r14d, [r13+4]
0x180075007  cmovle  r14d, [r13+4]
0x18007500c  add     r15d, [r13+0]
0x180075010  jmp     short loc_180075067
0x180075012  mov     ecx, [rdi+1A4h]
0x180075018  lea     rbx, [rdi+1B8h]
0x18007501f  mov     r8d, [rsp+180h+yTop]; yTop
0x180075024  add     ecx, r8d
0x180075027  mov     r9d, [rsp+180h+pColor]; xRight
0x18007502c  mov     edx, r9d
0x18007502f  sub     edx, [r13+0]; xLeft
0x180075033  mov     [rsp+180h+y], ecx; struct DPISCALEINFO *
0x180075037  mov     rcx, rbx; lprc
0x18007503a  call    cs:__imp_SetRect
0x180075040  movups  xmm0, xmmword ptr [rbx]
0x180075043  mov     rdx, [rdi+120h]; void *
0x18007504a  lea     r9, [rsp+180h+var_120]; struct tagRECT
0x18007504f  mov     r8, rsi; HDC
0x180075052  mov     rcx, r13; this
0x180075055  movdqu  xmmword ptr [rsp+180h+var_120.left], xmm0
0x18007505b  call    ?Draw@CWrenchButton@@QEAAXPEAXPEAUHDC__@@UtagRECT@@PEAUDPISCALEINFO@@@Z; CWrenchButton::Draw(void *,HDC__ *,tagRECT,DPISCALEINFO *)
0x180075060  mov     eax, [r13+0]
0x180075064  sub     [rbp+80h+x+8], eax
0x180075067  mov     rcx, [rdi+0A0h]; lpString
0x18007506e  call    cs:__imp_lstrlenW
0x180075074  mov     ecx, [rsp+180h+format]
0x180075078  lea     r9, [rsp+180h+x]; lprc
0x18007507d  mov     rdx, [rdi+0A0h]; lpchText
0x180075084  mov     r8d, eax; cchText
0x180075087  mov     [rsp+180h+y], ecx; format
0x18007508b  mov     rcx, rsi; hdc
0x18007508e  call    cs:__imp_DrawTextW
0x180075094  mov     eax, [rbp+80h+ptm.tmHeight]
0x180075097  mov     rbx, [rsp+180h+ho]
0x18007509c  inc     eax
0x18007509e  cmp     r14d, eax
0x1800750a1  cmovg   eax, r14d
0x1800750a5  mov     r14d, eax
0x1800750a8  mov     eax, [rbp+80h+x+8]
0x1800750ab  sub     eax, [rsp+180h+x]
0x1800750af  add     r15d, eax
0x1800750b2  test    rbx, rbx
0x1800750b5  jz      short loc_1800750CE
  ... truncated ...
```
