# DrawStatusTextEx(STATUSINFO *,HDC__ *,tagRECT const *,ushort const *,STRINGINFO *,uint,int)

- ea: `0x1800b2360`
- end: `0x1800b2a5f`
- name: `?DrawStatusTextEx@@YAXPEAUSTATUSINFO@@PEAUHDC__@@PEBUtagRECT@@PEBGPEAUSTRINGINFO@@IH@Z`
- size: `1791`
- prototype: `void(struct STATUSINFO *, HDC, const struct tagRECT *, const unsigned __int16 *, struct STRINGINFO *, unsigned int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b1e5c`
- `0x180117740`
- `0x1801177f0`

## callees

- `0x1800ad3b0`
- `0x1800b2360`
- `0x180114520`
- `0x18011ef90`

## import_xrefs

- `GDI32!SetTextAlign` at `0x1800b2794`
- `GDI32!SetTextAlign` at `0x1800b2a46`
- `GDI32!SetTextAlign` at `0x1800b2794`
- `GDI32!SetTextAlign` at `0x1800b2a46`
- `GDI32!CreateSolidBrush` at `0x1800b27ea`
- `GDI32!CreateSolidBrush` at `0x1800b27ea`
- `GDI32!DeleteObject` at `0x1800b2a54`
- `GDI32!DeleteObject` at `0x1800b2a54`
- `GDI32!SetBkColor` at `0x1800b2489`
- `GDI32!SetBkColor` at `0x1800b26ab`
- `GDI32!SetBkColor` at `0x1800b2864`
- `GDI32!SetBkColor` at `0x1800b2489`
- `GDI32!SetBkColor` at `0x1800b26ab`
- `GDI32!SetBkColor` at `0x1800b2864`
- `GDI32!SetBkMode` at `0x1800b2498`
- `GDI32!SetBkMode` at `0x1800b26b7`
- `GDI32!SetBkMode` at `0x1800b2820`
- `GDI32!SetBkMode` at `0x1800b2498`
- `GDI32!SetBkMode` at `0x1800b26b7`
- `GDI32!SetBkMode` at `0x1800b2820`
- `GDI32!SetTextColor` at `0x1800b2470`
- `GDI32!SetTextColor` at `0x1800b269f`
- `GDI32!SetTextColor` at `0x1800b2839`
- `GDI32!SetTextColor` at `0x1800b2470`
- `GDI32!SetTextColor` at `0x1800b269f`
- `GDI32!SetTextColor` at `0x1800b2839`
- `GDI32!GetTextAlign` at `0x1800b2782`
- `GDI32!GetTextAlign` at `0x1800b2782`
- `GDI32!PatBlt` at `0x1800b2917`
- `GDI32!PatBlt` at `0x1800b2917`
- `GDI32!SelectObject` at `0x1800b28df`
- `GDI32!SelectObject` at `0x1800b2923`
- `GDI32!SelectObject` at `0x1800b28df`
- `GDI32!SelectObject` at `0x1800b2923`
- `GDI32!GetNearestColor` at `0x1800b27c2`
- `GDI32!GetNearestColor` at `0x1800b27c2`
- `USER32!InflateRect` at `0x1800b245a`
- `USER32!InflateRect` at `0x1800b28c7`
- `USER32!InflateRect` at `0x1800b245a`
- `USER32!InflateRect` at `0x1800b28c7`
- `USER32!GetSystemMetrics` at `0x1800b243a`
- `USER32!GetSystemMetrics` at `0x1800b2449`
- `USER32!GetSystemMetrics` at `0x1800b25c2`
- `USER32!GetSystemMetrics` at `0x1800b2708`
- `USER32!GetSystemMetrics` at `0x1800b28a7`
- `USER32!GetSystemMetrics` at `0x1800b28b6`
- `USER32!GetSystemMetrics` at `0x1800b2946`
- `USER32!GetSystemMetrics` at `0x1800b243a`
- `USER32!GetSystemMetrics` at `0x1800b2449`
- `USER32!GetSystemMetrics` at `0x1800b25c2`
- `USER32!GetSystemMetrics` at `0x1800b2708`
- `USER32!GetSystemMetrics` at `0x1800b28a7`
- `USER32!GetSystemMetrics` at `0x1800b28b6`
- `USER32!GetSystemMetrics` at `0x1800b2946`
- `USER32!GetSysColor` at `0x1800b2465`
- `USER32!GetSysColor` at `0x1800b247e`
- `USER32!GetSysColor` at `0x1800b27aa`
- `USER32!GetSysColor` at `0x1800b27b5`
- `USER32!GetSysColor` at `0x1800b27e2`
- `USER32!GetSysColor` at `0x1800b282e`
- `USER32!GetSysColor` at `0x1800b2859`
- `USER32!GetSysColor` at `0x1800b2465`
- `USER32!GetSysColor` at `0x1800b247e`
- `USER32!GetSysColor` at `0x1800b27aa`
- `USER32!GetSysColor` at `0x1800b27b5`
- `USER32!GetSysColor` at `0x1800b27e2`
- `USER32!GetSysColor` at `0x1800b282e`
- `USER32!GetSysColor` at `0x1800b2859`
- `USER32!DrawIconEx` at `0x1800b29d1`
- `USER32!DrawIconEx` at `0x1800b29d1`
- `USER32!DrawEdge` at `0x1800b289d`
- `USER32!DrawEdge` at `0x1800b289d`
- `UxTheme!GetThemeTextExtent` at `0x1800b2574`
- `UxTheme!GetThemeTextExtent` at `0x1800b2574`
- `UxTheme!DrawThemeText` at `0x1800b2670`
- `UxTheme!DrawThemeText` at `0x1800b2670`
- `UxTheme!DrawThemeBackground` at `0x1800b242f`
- `UxTheme!DrawThemeBackground` at `0x1800b242f`

## pseudocode

```c
void __fastcall DrawStatusTextEx(
        struct STATUSINFO *a1,
        HDC a2,
        const struct tagRECT *a3,
        const unsigned __int16 *a4,
        struct STRINGINFO *a5,
        __int16 a6,
        int a7)
{
  RECT v8; // xmm0
  const WCHAR *v11; // r15
  void *v12; // rcx
  int v13; // ebx
  int SystemMetrics; // eax
  COLORREF SysColor; // eax
  COLORREF v16; // eax
  __int16 v17; // r14
  int v18; // eax
  int v19; // r14d
  int v20; // edi
  const WCHAR *i; // rax
  __int64 v22; // rbx
  int v23; // r14d
  void *v24; // rcx
  HRESULT ThemeTextExtent; // eax
  int v26; // r10d
  LONG v27; // eax
  int v28; // r10d
  struct STRINGINFO *v29; // r8
  LONG v30; // r11d
  void *v31; // r10
  HRESULT v32; // eax
  int v33; // eax
  LONG v34; // ecx
  COLORREF v35; // ebx
  DWORD v36; // edi
  HGDIOBJ v37; // rdi
  int v38; // r12d
  COLORREF v39; // eax
  COLORREF v40; // eax
  COLORREF v41; // edx
  int v42; // ebx
  int v43; // eax
  HGDIOBJ v44; // rbx
  HICON v45; // r9
  LONG left; // [rsp+50h] [rbp-91h]
  int v47; // [rsp+54h] [rbp-8Dh]
  int v48; // [rsp+58h] [rbp-89h]
  int v49; // [rsp+5Ch] [rbp-85h]
  int v50; // [rsp+60h] [rbp-81h] BYREF
  int v51; // [rsp+64h] [rbp-7Dh]
  int v52; // [rsp+68h] [rbp-79h]
  COLORREF v53; // [rsp+6Ch] [rbp-75h]
  int v54; // [rsp+70h] [rbp-71h]
  LONG right; // [rsp+74h] [rbp-6Dh]
  int v56; // [rsp+78h] [rbp-69h]
  int v57; // [rsp+7Ch] [rbp-65h]
  UINT align; // [rsp+80h] [rbp-61h]
  COLORREF color; // [rsp+84h] [rbp-5Dh]
  int mode; // [rsp+88h] [rbp-59h]
  struct STRINGINFO *v61; // [rsp+90h] [rbp-51h]
  int v62; // [rsp+98h] [rbp-49h]
  HGDIOBJ h; // [rsp+A0h] [rbp-41h]
  const WCHAR *v64; // [rsp+A8h] [rbp-39h]
  RECT rc; // [rsp+B0h] [rbp-31h] BYREF
  RECT pBoundingRect; // [rsp+C0h] [rbp-21h] BYREF
  unsigned int v67; // [rsp+158h] [rbp+77h]

  v8 = *a3;
  left = a3->left;
  right = a3->right;
  v61 = a5;
  v62 = a6 & 0x400;
  v49 = 0;
  v50 = 0;
  h = 0;
  align = 0;
  v54 = 0;
  rc = v8;
  if ( (a6 & 0x400) != 0 )
  {
    align = GetTextAlign(a2);
    SetTextAlign(a2, align | 0x100);
  }
  v11 = &c_szNULL;
  if ( a4 )
    v11 = a4;
  if ( a1 && (v12 = (void *)*((_QWORD *)a1 + 22)) != 0 )
  {
    v48 = 0;
    if ( (a6 & 0x100) == 0 )
      DrawThemeBackground(v12, a2, (a7 != 0) + 1, 0, &rc, 0);
    v13 = -GetSystemMetrics(6);
    SystemMetrics = GetSystemMetrics(5);
    InflateRect(&rc, -SystemMetrics, v13);
    SysColor = GetSysColor(18);
    color = SetTextColor(a2, SysColor);
    v16 = GetSysColor(15);
    v53 = SetBkColor(a2, v16);
    mode = SetBkMode(a2, 1);
    v17 = a6;
  }
  else
  {
    v35 = GetSysColor(15);
    v36 = GetSysColor(15);
    if ( GetNearestColor(a2, v35) == v36 )
    {
      v37 = h;
      v38 = 6;
    }
    else
    {
      v38 = 4;
      v39 = GetSysColor(15);
      h = CreateSolidBrush(v39);
      v37 = h;
      if ( !h )
        v38 = 6;
    }
    v48 = v38;
    mode = SetBkMode(a2, ((v38 & 2) != 0) + 1);
    v40 = GetSysColor(18);
    color = SetTextColor(a2, v40);
    if ( !a1 || (v41 = *((_DWORD *)a1 + 43), v41 == -16777216) )
      v41 = GetSysColor(15);
    v17 = a6;
    v53 = SetBkColor(a2, v41);
    if ( (a6 & 0x100) != 0 )
    {
      v42 = -GetSystemMetrics(6);
      v43 = GetSystemMetrics(5);
      InflateRect(&rc, -v43, v42);
    }
    else
    {
      DrawEdge(a2, &rc, (a6 & 0x200) != 0 ? 4 : 2, 0x200Fu);
    }
    if ( v37 )
    {
      v44 = SelectObject(a2, v37);
      if ( v44 )
      {
        PatBlt(a2, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0xF00021u);
        SelectObject(a2, v44);
      }
    }
  }
  v18 = 0;
  v57 = 0;
  v19 = v17 & 0x800;
  v52 = 0;
  v67 = v19;
  do
  {
    if ( !v19 && *v11 == 9 && (unsigned int)v18 <= 1 )
      goto LABEL_49;
    v51 = -2147467259;
    v20 = 0;
    for ( i = v11; ; ++i )
    {
      v64 = i;
      if ( !*i )
        break;
      if ( !v19 && *i == 9 )
        goto LABEL_19;
    }
    v57 = 1;
LABEL_19:
    v22 = i - v11;
    if ( !a1 )
      goto LABEL_20;
    v24 = (void *)*((_QWORD *)a1 + 22);
    if ( !v24
      || (pBoundingRect = 0,
          ThemeTextExtent = GetThemeTextExtent(v24, a2, 0, 0, v11, v22, 0x420u, &pBoundingRect, &pBoundingRect),
          v23 = pBoundingRect.right - pBoundingRect.left,
          v51 = ThemeTextExtent,
          v49 = pBoundingRect.right - pBoundingRect.left,
          v47 = pBoundingRect.bottom - pBoundingRect.top,
          v50 = pBoundingRect.bottom - pBoundingRect.top,
          ThemeTextExtent < 0) )
    {
LABEL_20:
      MGetTextExtent(a2, v11, v22, (__int64)&v50);
      v23 = v49;
      v47 = v50;
    }
    if ( v61 && *((_QWORD *)v61 + 2) && !v54 )
    {
      v33 = GetSystemMetrics(45);
      v54 = 1;
      v20 = *((_DWORD *)v61 + 6) + 2 * v33;
    }
    if ( v52 )
    {
      if ( v52 == 1 )
        v28 = (left + right - v20 - v23) / 2;
      else
        v28 = right - v20 - v23 - GetSystemMetrics(45);
      v27 = left;
    }
    else
    {
      v26 = GetSystemMetrics(45);
      v27 = left;
      v28 = left + v26;
    }
    v29 = v61;
    v30 = v28 + v20;
    v56 = v28 + v20;
    if ( v61 )
    {
      if ( v20 )
      {
        if ( v28 > v27 )
        {
          v45 = (HICON)*((_QWORD *)v61 + 2);
          if ( v45 )
          {
            DrawIconEx(
              a2,
              v28,
              rc.top + (rc.bottom - *((_DWORD *)v61 + 7) - rc.top) / 2,
              v45,
              *((_DWORD *)v61 + 6),
              *((_DWORD *)v61 + 7),
              0,
              0,
              3u);
            v30 = v56;
            v29 = v61;
          }
        }
        v34 = v30;
        rc.left = v30;
      }
      else
      {
        v34 = rc.left;
      }
      *((_DWORD *)v29 + 10) = !*v11 && v20 || v23 >= rc.right - v34;
    }
    if ( a1 && (v31 = (void *)*((_QWORD *)a1 + 22)) != 0 )
    {
      *(_QWORD *)&pBoundingRect.right = *(_QWORD *)&rc.right;
      pBoundingRect.left = v30;
      pBoundingRect.top = (_mm_cvtsi128_si32(_mm_srli_si128((__m128i)rc, 12))
                         + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)rc, 4))
                         - v47)
                        / 2;
      if ( a7 )
        pBoundingRect.right -= *((_DWORD *)a1 + 27);
      v32 = DrawThemeText(v31, a2, 0, 0, v11, v22, 0x820u, 0, &pBoundingRect);
      v30 = v56;
    }
    else
    {
      v32 = v51;
    }
    if ( v32 < 0 )
      SHExtTextOutW(a2, v30, (rc.bottom + rc.top - v47) / 2, v48);
    if ( v57 )
      break;
    v11 = v64;
    v19 = v67;
    v18 = v52;
    v48 = 4;
LABEL_49:
    ++v18;
    ++v11;
    v52 = v18;
  }
  while ( v18 < 3 );
  if ( v62 )
    SetTextAlign(a2, align);
  SetTextColor(a2, color);
  SetBkColor(a2, v53);
  SetBkMode(a2, mode);
  if ( h )
    DeleteObject(h);
}

```

## disassembly

```asm
0x1800b2360  push    rbp
0x1800b2362  push    rbx
0x1800b2363  push    rsi
0x1800b2364  push    rdi
0x1800b2365  push    r12
0x1800b2367  push    r13
0x1800b2369  push    r14
0x1800b236b  push    r15
0x1800b236d  lea     rbp, [rsp-7]
0x1800b2372  sub     rsp, 0E8h
0x1800b2379  mov     rax, cs:__security_cookie
0x1800b2380  xor     rax, rsp
0x1800b2383  mov     [rbp+3Fh+var_50], rax
0x1800b2387  mov     eax, [r8]
0x1800b238a  mov     rsi, rdx
0x1800b238d  mov     edi, [rbp+3Fh+arg_28]
0x1800b2390  xor     edx, edx
0x1800b2392  movups  xmm0, xmmword ptr [r8]
0x1800b2396  mov     [rsp+120h+var_D0], eax
0x1800b239a  mov     r13, rcx
0x1800b239d  mov     eax, [r8+8]
0x1800b23a1  mov     rbx, r9
0x1800b23a4  mov     rcx, [rbp+3Fh+arg_20]
0x1800b23a8  mov     [rbp+3Fh+var_AC], eax
0x1800b23ab  mov     eax, edi
0x1800b23ad  and     eax, 400h
0x1800b23b2  mov     [rbp+3Fh+var_90], rcx
0x1800b23b6  mov     [rbp+3Fh+var_88], eax
0x1800b23b9  mov     [rsp+120h+var_C4], edx
0x1800b23bd  mov     dword ptr [rsp+120h+var_C0], edx
0x1800b23c1  mov     [rbp+3Fh+h], rdx
0x1800b23c5  mov     [rbp+3Fh+align], edx
0x1800b23c8  mov     [rbp+3Fh+var_B0], edx
0x1800b23cb  movdqu  xmmword ptr [rbp+3Fh+rc.left], xmm0
0x1800b23d0  jnz     loc_1800B277F
0x1800b23d6  test    rbx, rbx
0x1800b23d9  lea     r15, c_szNULL
0x1800b23e0  cmovnz  r15, rbx
0x1800b23e4  test    r13, r13
0x1800b23e7  jz      loc_1800B27A1
0x1800b23ed  mov     rcx, [r13+0B0h]; hTheme
0x1800b23f4  test    rcx, rcx
0x1800b23f7  jz      loc_1800B27A1
0x1800b23fd  mov     [rsp+120h+var_C8], edx
0x1800b2401  mov     r12d, 1
0x1800b2407  bt      edi, 8
0x1800b240b  jb      short loc_1800B2435
0x1800b240d  mov     eax, [rbp+3Fh+arg_30]
0x1800b2410  neg     eax
0x1800b2412  mov     [rsp+120h+pClipRect], rdx; pClipRect
0x1800b2417  lea     rax, [rbp+3Fh+rc]
0x1800b241b  mov     rdx, rsi; hdc
0x1800b241e  sbb     r8d, r8d
0x1800b2421  mov     [rsp+120h+pRect], rax; pRect
0x1800b2426  neg     r8d
0x1800b2429  xor     r9d, r9d; iStateId
0x1800b242c  add     r8d, r12d; iPartId
0x1800b242f  call    cs:__imp_DrawThemeBackground
0x1800b2435  mov     ecx, 6; nIndex
0x1800b243a  call    cs:__imp_GetSystemMetrics
0x1800b2440  mov     ebx, eax
0x1800b2442  mov     ecx, 5; nIndex
0x1800b2447  neg     ebx
0x1800b2449  call    cs:__imp_GetSystemMetrics
0x1800b244f  mov     r8d, ebx; dy
0x1800b2452  lea     rcx, [rbp+3Fh+rc]; lprc
0x1800b2456  neg     eax
0x1800b2458  mov     edx, eax; dx
0x1800b245a  call    cs:__imp_InflateRect
0x1800b2460  mov     ecx, 12h; nIndex
0x1800b2465  call    cs:__imp_GetSysColor
0x1800b246b  mov     edx, eax; color
0x1800b246d  mov     rcx, rsi; hdc
0x1800b2470  call    cs:__imp_SetTextColor
0x1800b2476  mov     ecx, 0Fh; nIndex
0x1800b247b  mov     [rbp+3Fh+color], eax
0x1800b247e  call    cs:__imp_GetSysColor
0x1800b2484  mov     edx, eax; color
0x1800b2486  mov     rcx, rsi; hdc
0x1800b2489  call    cs:__imp_SetBkColor
0x1800b248f  mov     edx, r12d; mode
0x1800b2492  mov     rcx, rsi; hdc
0x1800b2495  mov     [rbp+3Fh+var_B4], eax
0x1800b2498  call    cs:__imp_SetBkMode
0x1800b249e  mov     [rbp+3Fh+mode], eax
0x1800b24a1  mov     r14d, edi
0x1800b24a4  xor     r9d, r9d
0x1800b24a7  mov     eax, r9d
0x1800b24aa  mov     [rbp+3Fh+var_A4], r9d
0x1800b24ae  and     r14d, 800h
0x1800b24b5  mov     [rbp+3Fh+var_B8], eax
0x1800b24b8  mov     [rbp+3Fh+arg_28], r14d
0x1800b24bc  test    r14d, r14d
0x1800b24bf  jnz     short loc_1800B24CC
0x1800b24c1  cmp     word ptr [r15], 9
0x1800b24c6  jz      loc_1800B292E
0x1800b24cc  mov     dword ptr [rbp+3Fh+var_C0+4], 80004005h
0x1800b24d3  mov     edi, r9d
0x1800b24d6  mov     rax, r15
0x1800b24d9  mov     [rbp+3Fh+var_78], rax
0x1800b24dd  cmp     [rax], r9w
0x1800b24e1  jz      short loc_1800B24F4
0x1800b24e3  test    r14d, r14d
0x1800b24e6  jnz     short loc_1800B24EE
0x1800b24e8  cmp     word ptr [rax], 9
0x1800b24ec  jz      short loc_1800B24F8
0x1800b24ee  add     rax, 2
0x1800b24f2  jmp     short loc_1800B24D9
0x1800b24f4  mov     [rbp+3Fh+var_A4], r12d
0x1800b24f8  mov     rbx, rax
0x1800b24fb  sub     rbx, r15
0x1800b24fe  sar     rbx, 1
0x1800b2501  test    r13, r13
0x1800b2504  jnz     short loc_1800B2535
0x1800b2506  lea     rax, [rsp+120h+var_C0]
0x1800b250b  mov     r8d, ebx; c
0x1800b250e  lea     r9, [rsp+120h+var_C4]
0x1800b2513  mov     [rsp+120h+pRect], rax; __int64
0x1800b2518  mov     rdx, r15; lpString
0x1800b251b  mov     rcx, rsi; hdc
0x1800b251e  call    MGetTextExtent
0x1800b2523  mov     eax, dword ptr [rsp+120h+var_C0]
0x1800b2527  xor     r9d, r9d
0x1800b252a  mov     r14d, [rsp+120h+var_C4]
0x1800b252f  mov     [rsp+120h+var_CC], eax
0x1800b2533  jmp     short loc_1800B25A5
0x1800b2535  mov     rcx, [r13+0B0h]; hTheme
0x1800b253c  test    rcx, rcx
0x1800b253f  jz      short loc_1800B2506
0x1800b2541  lea     rax, [rbp+3Fh+var_60]
0x1800b2545  xorps   xmm0, xmm0
0x1800b2548  mov     [rsp+120h+pExtentRect], rax; pExtentRect
0x1800b254d  xor     r9d, r9d; iStateId
0x1800b2550  lea     rax, [rbp+3Fh+var_60]
0x1800b2554  xor     r8d, r8d; iPartId
0x1800b2557  mov     [rsp+120h+pBoundingRect], rax; pBoundingRect
0x1800b255c  mov     rdx, rsi; hdc
0x1800b255f  mov     [rsp+120h+dwTextFlags], 420h; dwTextFlags
0x1800b2567  mov     dword ptr [rsp+120h+pClipRect], ebx; cchCharCount
0x1800b256b  mov     [rsp+120h+pRect], r15; pszText
0x1800b2570  movups  xmmword ptr [rbp+3Fh+var_60.left], xmm0
0x1800b2574  call    cs:__imp_GetThemeTextExtent
0x1800b257a  mov     r14d, [rbp+3Fh+var_60.right]
0x1800b257e  xor     r9d, r9d
0x1800b2581  sub     r14d, [rbp+3Fh+var_60.left]
0x1800b2585  mov     ecx, eax
0x1800b2587  mov     dword ptr [rbp+3Fh+var_C0+4], eax
0x1800b258a  mov     eax, [rbp+3Fh+var_60.bottom]
0x1800b258d  sub     eax, [rbp+3Fh+var_60.top]
0x1800b2590  mov     [rsp+120h+var_C4], r14d
0x1800b2595  mov     [rsp+120h+var_CC], eax
0x1800b2599  mov     dword ptr [rsp+120h+var_C0], eax
0x1800b259d  test    ecx, ecx
0x1800b259f  js      loc_1800B2506
0x1800b25a5  mov     rax, [rbp+3Fh+var_90]
0x1800b25a9  test    rax, rax
0x1800b25ac  jnz     loc_1800B26EF
0x1800b25b2  mov     ecx, [rbp+3Fh+var_B8]
0x1800b25b5  test    ecx, ecx
0x1800b25b7  jnz     loc_1800B293C
0x1800b25bd  mov     ecx, 2Dh ; '-'; nIndex
0x1800b25c2  call    cs:__imp_GetSystemMetrics
0x1800b25c8  mov     r10d, eax
0x1800b25cb  mov     eax, [rsp+120h+var_D0]
0x1800b25cf  add     r10d, eax
0x1800b25d2  xor     r9d, r9d
0x1800b25d5  mov     r8, [rbp+3Fh+var_90]
0x1800b25d9  lea     r11d, [r10+rdi]
0x1800b25dd  mov     [rbp+3Fh+var_A8], r11d
0x1800b25e1  test    r8, r8
0x1800b25e4  jnz     loc_1800B2724
0x1800b25ea  mov     edi, [rsp+120h+var_CC]
0x1800b25ee  mov     r14d, 2
0x1800b25f4  test    r13, r13
0x1800b25f7  jz      loc_1800B26EA
0x1800b25fd  mov     r10, [r13+0B0h]
0x1800b2604  test    r10, r10
0x1800b2607  jz      loc_1800B26EA
0x1800b260d  movaps  xmm1, xmmword ptr [rbp+3Fh+rc.left]
0x1800b2611  movdqa  xmmword ptr [rbp+3Fh+var_60.left], xmm1
0x1800b2616  movdqa  xmm0, xmm1
0x1800b261a  psrldq  xmm0, 4
0x1800b261f  movd    eax, xmm0
0x1800b2623  psrldq  xmm1, 0Ch
0x1800b2628  movd    ecx, xmm1
0x1800b262c  sub     eax, edi
0x1800b262e  mov     [rbp+3Fh+var_60.left], r11d
0x1800b2632  add     eax, ecx
0x1800b2634  cdq
0x1800b2635  idiv    r14d
0x1800b2638  mov     [rbp+3Fh+var_60.top], eax
0x1800b263b  cmp     [rbp+3Fh+arg_30], r9d
0x1800b263f  jnz     loc_1800B29F6
0x1800b2645  lea     rax, [rbp+3Fh+var_60]
0x1800b2649  xor     r8d, r8d; iPartId
0x1800b264c  mov     [rsp+120h+pExtentRect], rax; pRect
0x1800b2651  mov     rdx, rsi; hdc
0x1800b2654  mov     dword ptr [rsp+120h+pBoundingRect], r9d; dwTextFlags2
0x1800b2659  mov     rcx, r10; hTheme
0x1800b265c  mov     [rsp+120h+dwTextFlags], 820h; dwTextFlags
0x1800b2664  xor     r9d, r9d; iStateId
0x1800b2667  mov     dword ptr [rsp+120h+pClipRect], ebx; cchText
0x1800b266b  mov     [rsp+120h+pRect], r15; pszText
0x1800b2670  call    cs:__imp_DrawThemeText
0x1800b2676  mov     r11d, [rbp+3Fh+var_A8]
0x1800b267a  xor     r9d, r9d
0x1800b267d  test    eax, eax
0x1800b267f  js      loc_1800B2A02
0x1800b2685  cmp     [rbp+3Fh+var_A4], r9d
0x1800b2689  jz      loc_1800B2754
0x1800b268f  cmp     [rbp+3Fh+var_88], r9d
0x1800b2693  jnz     loc_1800B2A40
0x1800b2699  mov     edx, [rbp+3Fh+color]; color
0x1800b269c  mov     rcx, rsi; hdc
0x1800b269f  call    cs:__imp_SetTextColor
0x1800b26a5  mov     edx, [rbp+3Fh+var_B4]; color
0x1800b26a8  mov     rcx, rsi; hdc
0x1800b26ab  call    cs:__imp_SetBkColor
0x1800b26b1  mov     edx, [rbp+3Fh+mode]; mode
0x1800b26b4  mov     rcx, rsi; hdc
0x1800b26b7  call    cs:__imp_SetBkMode
0x1800b26bd  mov     rax, [rbp+3Fh+h]
0x1800b26c1  test    rax, rax
0x1800b26c4  jnz     loc_1800B2A51
0x1800b26ca  mov     rcx, [rbp+3Fh+var_50]
0x1800b26ce  xor     rcx, rsp; StackCookie
0x1800b26d1  call    __security_check_cookie
0x1800b26d6  add     rsp, 0E8h
0x1800b26dd  pop     r15
0x1800b26df  pop     r14
0x1800b26e1  pop     r13
0x1800b26e3  pop     r12
0x1800b26e5  pop     rdi
0x1800b26e6  pop     rsi
0x1800b26e7  pop     rbx
0x1800b26e8  pop     rbp
0x1800b26e9  retn
0x1800b26ea  mov     eax, dword ptr [rbp+3Fh+var_C0+4]
0x1800b26ed  jmp     short loc_1800B267D
0x1800b26ef  cmp     [rax+10h], r9
0x1800b26f3  jz      loc_1800B25B2
0x1800b26f9  cmp     [rbp+3Fh+var_B0], r9d
0x1800b26fd  jnz     loc_1800B25B2
0x1800b2703  mov     ecx, 2Dh ; '-'; nIndex
0x1800b2708  call    cs:__imp_GetSystemMetrics
0x1800b270e  mov     rcx, [rbp+3Fh+var_90]
0x1800b2712  xor     r9d, r9d
0x1800b2715  mov     [rbp+3Fh+var_B0], r12d
0x1800b2719  mov     ecx, [rcx+18h]
0x1800b271c  lea     edi, [rcx+rax*2]
0x1800b271f  jmp     loc_1800B25B2
0x1800b2724  test    edi, edi
0x1800b2726  jnz     loc_1800B2982
0x1800b272c  mov     ecx, [rbp+3Fh+rc.left]
0x1800b272f  cmp     [r15], r9w
0x1800b2733  jnz     short loc_1800B273D
0x1800b2735  test    edi, edi
0x1800b2737  jnz     loc_1800B29ED
0x1800b273d  mov     eax, [rbp+3Fh+rc.right]
0x1800b2740  sub     eax, ecx
0x1800b2742  mov     ecx, r9d
0x1800b2745  cmp     r14d, eax
0x1800b2748  setnl   cl
0x1800b274b  mov     [r8+28h], ecx
0x1800b274f  jmp     loc_1800B25EA
0x1800b2754  mov     r15, [rbp+3Fh+var_78]
0x1800b2758  mov     r14d, [rbp+3Fh+arg_28]
0x1800b275c  mov     eax, [rbp+3Fh+var_B8]
0x1800b275f  mov     [rsp+120h+var_C8], 4
0x1800b2767  add     eax, r12d
0x1800b276a  add     r15, 2
0x1800b276e  mov     [rbp+3Fh+var_B8], eax
0x1800b2771  cmp     eax, 3
0x1800b2774  jge     loc_1800B268F
0x1800b277a  jmp     loc_1800B24BC
0x1800b277f  mov     rcx, rsi; hdc
0x1800b2782  call    cs:__imp_GetTextAlign
0x1800b2788  mov     edx, eax
0x1800b278a  mov     [rbp+3Fh+align], eax
0x1800b278d  bts     edx, 8; align
0x1800b2791  mov     rcx, rsi; hdc
0x1800b2794  call    cs:__imp_SetTextAlign
0x1800b279a  xor     edx, edx
0x1800b279c  jmp     loc_1800B23D6
0x1800b27a1  mov     r14d, 0Fh
0x1800b27a7  mov     ecx, r14d; nIndex
0x1800b27aa  call    cs:__imp_GetSysColor
0x1800b27b0  mov     ecx, r14d; nIndex
0x1800b27b3  mov     ebx, eax
0x1800b27b5  call    cs:__imp_GetSysColor
0x1800b27bb  mov     edx, ebx; color
0x1800b27bd  mov     rcx, rsi; hdc
0x1800b27c0  mov     edi, eax
0x1800b27c2  call    cs:__imp_GetNearestColor
0x1800b27c8  cmp     eax, edi
0x1800b27ca  jnz     short loc_1800B27D9
0x1800b27cc  mov     rdi, [rbp+3Fh+h]
0x1800b27d0  lea     ebx, [r14-9]
0x1800b27d4  mov     r12d, ebx
0x1800b27d7  jmp     short loc_1800B2803
  ... truncated ...
```
