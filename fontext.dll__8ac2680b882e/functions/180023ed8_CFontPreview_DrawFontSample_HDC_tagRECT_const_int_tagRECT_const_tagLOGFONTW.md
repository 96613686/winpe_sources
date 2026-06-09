# CFontPreview::DrawFontSample(HDC__ *,tagRECT const *,int,tagRECT const *,tagLOGFONTW *)

- ea: `0x180023ed8`
- end: `0x180024489`
- name: `?DrawFontSample@CFontPreview@@AEAAHPEAUHDC__@@PEBUtagRECT@@H1PEAUtagLOGFONTW@@@Z`
- size: `1457`
- prototype: `__int64 __fastcall(CFontPreview *this, HDC, const struct tagRECT *, int, struct tagRECT *, struct tagLOGFONTW *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800247a0`

## callees

- `0x180006668`
- `0x180023ed8`
- `0x180031070`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800240d3`
- `GDI32!DeleteObject` at `0x180024412`
- `GDI32!DeleteObject` at `0x180024461`
- `GDI32!DeleteObject` at `0x1800240d3`
- `GDI32!DeleteObject` at `0x180024412`
- `GDI32!DeleteObject` at `0x180024461`
- `GDI32!GetDeviceCaps` at `0x180023f2c`
- `GDI32!GetDeviceCaps` at `0x180023f2c`
- `GDI32!SetTextAlign` at `0x180023f40`
- `GDI32!SetTextAlign` at `0x18002430e`
- `GDI32!SetTextAlign` at `0x180024341`
- `GDI32!SetTextAlign` at `0x180024377`
- `GDI32!SetTextAlign` at `0x1800243aa`
- `GDI32!SetTextAlign` at `0x18002443c`
- `GDI32!SetTextAlign` at `0x180023f40`
- `GDI32!SetTextAlign` at `0x18002430e`
- `GDI32!SetTextAlign` at `0x180024341`
- `GDI32!SetTextAlign` at `0x180024377`
- `GDI32!SetTextAlign` at `0x1800243aa`
- `GDI32!SetTextAlign` at `0x18002443c`
- `GDI32!SetTextColor` at `0x180023f54`
- `GDI32!SetTextColor` at `0x180024449`
- `GDI32!SetTextColor` at `0x180023f54`
- `GDI32!SetTextColor` at `0x180024449`
- `GDI32!SetBkColor` at `0x180023f68`
- `GDI32!SetBkColor` at `0x180024456`
- `GDI32!SetBkColor` at `0x180023f68`
- `GDI32!SetBkColor` at `0x180024456`
- `GDI32!CreateFontIndirectW` at `0x180023fd1`
- `GDI32!CreateFontIndirectW` at `0x18002408f`
- `GDI32!CreateFontIndirectW` at `0x1800241af`
- `GDI32!CreateFontIndirectW` at `0x180023fd1`
- `GDI32!CreateFontIndirectW` at `0x18002408f`
- `GDI32!CreateFontIndirectW` at `0x1800241af`
- `GDI32!GetLayout` at `0x180024266`
- `GDI32!GetLayout` at `0x180024266`
- `GDI32!SelectObject` at `0x180023fe2`
- `GDI32!SelectObject` at `0x18002409e`
- `GDI32!SelectObject` at `0x1800240ca`
- `GDI32!SelectObject` at `0x1800241bf`
- `GDI32!SelectObject` at `0x180024220`
- `GDI32!SelectObject` at `0x1800242d5`
- `GDI32!SelectObject` at `0x180024408`
- `GDI32!SelectObject` at `0x18002442f`
- `GDI32!SelectObject` at `0x180023fe2`
- `GDI32!SelectObject` at `0x18002409e`
- `GDI32!SelectObject` at `0x1800240ca`
- `GDI32!SelectObject` at `0x1800241bf`
- `GDI32!SelectObject` at `0x180024220`
- `GDI32!SelectObject` at `0x1800242d5`
- `GDI32!SelectObject` at `0x180024408`
- `GDI32!SelectObject` at `0x18002442f`
- `GDI32!GetTextExtentPoint32W` at `0x1800240bc`
- `GDI32!GetTextExtentPoint32W` at `0x1800242c8`
- `GDI32!GetTextExtentPoint32W` at `0x1800240bc`
- `GDI32!GetTextExtentPoint32W` at `0x1800242c8`
- `GDI32!GetTextMetricsW` at `0x1800241df`
- `GDI32!GetTextMetricsW` at `0x1800241df`
- `GDI32!MoveToEx` at `0x1800243e3`
- `GDI32!MoveToEx` at `0x1800243e3`
- `GDI32!LineTo` at `0x1800243f4`
- `GDI32!LineTo` at `0x1800243f4`
- `GDI32!ExtTextOutW` at `0x1800242b2`
- `GDI32!ExtTextOutW` at `0x1800242b2`
- `KERNEL32!MulDiv` at `0x180023fb3`
- `KERNEL32!MulDiv` at `0x18002407e`
- `KERNEL32!MulDiv` at `0x1800240fd`
- `KERNEL32!MulDiv` at `0x1800241a2`
- `KERNEL32!MulDiv` at `0x180023fb3`
- `KERNEL32!MulDiv` at `0x18002407e`
- `KERNEL32!MulDiv` at `0x1800240fd`
- `KERNEL32!MulDiv` at `0x1800241a2`
- `KERNEL32!lstrlenW` at `0x180024247`
- `KERNEL32!lstrlenW` at `0x180024247`
- `USER32!DrawTextW` at `0x180024333`
- `USER32!DrawTextW` at `0x18002439c`
- `USER32!DrawTextW` at `0x180024333`
- `USER32!DrawTextW` at `0x18002439c`
- `USER32!SetRect` at `0x180024301`
- `USER32!SetRect` at `0x18002436a`
- `USER32!SetRect` at `0x180024301`
- `USER32!SetRect` at `0x18002436a`

## pseudocode

```c
__int64 __fastcall CFontPreview::DrawFontSample(
        CFontPreview *this,
        HDC a2,
        const struct tagRECT *a3,
        int a4,
        struct tagRECT *a5,
        struct tagLOGFONTW *a6)
{
  COLORREF v9; // eax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  LONG v14; // eax
  bool v15; // zf
  LOGFONTW *p_lf; // rcx
  int v17; // r13d
  LONG v18; // ecx
  unsigned int v19; // esi
  __int64 v20; // r12
  int v21; // eax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  HFONT v25; // rbx
  HGDIOBJ v26; // r12
  unsigned int v27; // esi
  unsigned int v28; // r13d
  __int64 v29; // rbx
  int v30; // eax
  char *v31; // r12
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  int v35; // ecx
  int v36; // esi
  int v37; // ecx
  UINT c; // eax
  int *p_left; // r12
  DWORD Layout; // eax
  int v43; // [rsp+40h] [rbp-C0h]
  LONG x; // [rsp+44h] [rbp-BCh]
  int xa; // [rsp+44h] [rbp-BCh]
  LONG v46; // [rsp+48h] [rbp-B8h]
  int nNumerator; // [rsp+4Ch] [rbp-B4h]
  UINT align; // [rsp+50h] [rbp-B0h]
  COLORREF color; // [rsp+54h] [rbp-ACh]
  COLORREF v50; // [rsp+58h] [rbp-A8h]
  tagSIZE psizl; // [rsp+60h] [rbp-A0h] BYREF
  const struct tagRECT *v52; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+70h] [rbp-90h]
  HGDIOBJ FontIndirectW; // [rsp+78h] [rbp-88h]
  struct tagSIZE v55; // [rsp+80h] [rbp-80h] BYREF
  HGDIOBJ ho; // [rsp+88h] [rbp-78h]
  RECT *lprect; // [rsp+90h] [rbp-70h]
  struct tagRECT rc; // [rsp+98h] [rbp-68h] BYREF
  LOGFONTW lf; // [rsp+B0h] [rbp-50h] BYREF
  tagTEXTMETRICW tm; // [rsp+110h] [rbp+10h] BYREF
  WCHAR String[8]; // [rsp+150h] [rbp+50h] BYREF
  int v62; // [rsp+160h] [rbp+60h]

  v52 = a3;
  lprect = a5;
  nNumerator = GetDeviceCaps(a2, 90);
  align = SetTextAlign(a2, 0x18u);
  color = SetTextColor(a2, *((_DWORD *)this + 32));
  v9 = SetBkColor(a2, *((_DWORD *)this + 33));
  v10 = *(_OWORD *)&a6->lfHeight;
  *(_OWORD *)&lf.lfWeight = *(_OWORD *)&a6->lfWeight;
  v11 = *(_OWORD *)&a6->lfFaceName[10];
  *(_OWORD *)&lf.lfHeight = v10;
  v12 = *(_OWORD *)&a6->lfFaceName[2];
  *(_OWORD *)&lf.lfFaceName[10] = v11;
  v13 = *(_OWORD *)&a6->lfFaceName[24];
  v50 = v9;
  *(_OWORD *)&lf.lfFaceName[2] = v12;
  *(_OWORD *)&lf.lfFaceName[18] = *(_OWORD *)&a6->lfFaceName[18];
  *(_OWORD *)&lf.lfFaceName[24] = v13;
  v14 = MulDiv(-10, nNumerator, 72);
  v15 = *((_DWORD *)this + 59) == 0;
  p_lf = (LOGFONTW *)((char *)this + 144);
  lf.lfHeight = v14;
  if ( v15 )
    p_lf = &lf;
  FontIndirectW = CreateFontIndirectW(p_lf);
  v17 = -1;
  psizl = 0;
  h = SelectObject(a2, FontIndirectW);
  v18 = -1;
  x = a3->right - a3->left;
  v19 = 0;
  v46 = -1;
  do
  {
    v20 = 32LL * (int)v19;
    v21 = *(_DWORD *)((char *)this + v20 + 1848);
    if ( !v21 )
      break;
    if ( v21 == 1 )
    {
      v22 = *(_OWORD *)&a6->lfHeight;
      *(_OWORD *)&lf.lfWeight = *(_OWORD *)&a6->lfWeight;
      v23 = *(_OWORD *)&a6->lfFaceName[10];
      *(_OWORD *)&lf.lfHeight = v22;
      v24 = *(_OWORD *)&a6->lfFaceName[2];
      *(_OWORD *)&lf.lfFaceName[10] = v23;
      *(_OWORD *)&lf.lfFaceName[2] = v24;
      *(_OWORD *)&lf.lfFaceName[18] = *(_OWORD *)&a6->lfFaceName[18];
      *(_OWORD *)&lf.lfFaceName[24] = *(_OWORD *)&a6->lfFaceName[24];
      if ( v17 == -1 )
        v17 = *(_DWORD *)((char *)this + v20 + 1852);
      v46 = MulDiv(-v17, nNumerator, 72);
      lf.lfHeight = v46;
      v25 = CreateFontIndirectW(&lf);
      SelectObject(a2, v25);
      GetTextExtentPoint32W(a2, *(LPCWSTR *)((char *)this + v20 + 1864), *(_DWORD *)((char *)this + v20 + 1872), &psizl);
      SelectObject(a2, h);
      DeleteObject(v25);
      if ( psizl.cx <= x )
      {
        v18 = v46;
      }
      else
      {
        v17 = v17 * x / psizl.cx;
        v18 = MulDiv(-v17, nNumerator, 72);
        v46 = v18;
      }
    }
    ++v19;
  }
  while ( v19 < 0x14 );
  v26 = h;
  v27 = -a4;
  v62 = 0;
  v28 = 0;
  *(_OWORD *)String = 0;
  do
  {
    v29 = 32LL * (int)v28;
    v30 = *(_DWORD *)((char *)this + v29 + 1848);
    if ( !v30 )
      break;
    v31 = (char *)this + v29;
    v32 = *(_OWORD *)&a6->lfHeight;
    *(_OWORD *)&lf.lfWeight = *(_OWORD *)&a6->lfWeight;
    v33 = *(_OWORD *)&a6->lfFaceName[10];
    *(_OWORD *)&lf.lfHeight = v32;
    v34 = *(_OWORD *)&a6->lfFaceName[2];
    *(_OWORD *)&lf.lfFaceName[10] = v33;
    *(_OWORD *)&lf.lfFaceName[2] = v34;
    *(_OWORD *)&lf.lfFaceName[18] = *(_OWORD *)&a6->lfFaceName[18];
    *(_OWORD *)&lf.lfFaceName[24] = *(_OWORD *)&a6->lfFaceName[24];
    if ( v30 == 1 )
      lf.lfHeight = v18;
    else
      lf.lfHeight = MulDiv(-*((_DWORD *)v31 + 463), nNumerator, 72);
    ho = CreateFontIndirectW(&lf);
    SelectObject(a2, ho);
    memset(&tm, 0, sizeof(tm));
    GetTextMetricsW(a2, &tm);
    v35 = *(_DWORD *)((char *)this + v29 + 1848);
    v36 = tm.tmAscent + tm.tmExternalLeading + v27;
    rc = 0;
    v37 = v35 - 1;
    if ( v37 )
    {
      if ( v37 == 1 )
      {
        v55 = 0;
        SelectObject(a2, FontIndirectW);
        StringCchPrintfW(String, 0xAu, L"%d", *((unsigned int *)v31 + 463));
        c = lstrlenW(String);
        p_left = &v52->left;
        v43 = c;
        xa = v52->left;
        if ( c )
        {
          Layout = GetLayout(a2);
          if ( Layout == -1 )
          {
            c = v43;
          }
          else
          {
            v15 = (Layout & 1) == 0;
            c = v43;
            if ( !v15 )
              --xa;
          }
        }
        ExtTextOutW(a2, xa, v36, 4u, lprect, String, c, 0);
        GetTextExtentPoint32W(a2, String, v43, &v55);
        SelectObject(a2, ho);
        SetRect(&rc, *p_left + 2 * v55.cx, v36 - tm.tmAscent, p_left[2], v36 + tm.tmDescent);
        SetTextAlign(a2, align);
        DrawTextW(a2, *(LPCWSTR *)((char *)this + v29 + 1864), *(_DWORD *)((char *)this + v29 + 1872), &rc, 0x800u);
        SetTextAlign(a2, 0x18u);
      }
      else
      {
        p_left = &v52->left;
      }
    }
    else
    {
      p_left = &v52->left;
      SetRect(&rc, v52->left, v36 - tm.tmAscent, v52->right, v36 + tm.tmDescent);
      SetTextAlign(a2, align);
      DrawTextW(a2, *(LPCWSTR *)((char *)this + v29 + 1864), *(_DWORD *)((char *)this + v29 + 1872), &rc, 0x810u);
      SetTextAlign(a2, 0x18u);
      if ( *(_DWORD *)((char *)this + v29 + 1856) )
      {
        v27 = v36 + 2 * tm.tmDescent;
LABEL_29:
        MoveToEx(a2, *p_left, v27, 0);
        LineTo(a2, p_left[2], v27);
        v27 += 5;
        goto LABEL_30;
      }
    }
    v27 = tm.tmDescent + v36;
    if ( *(_DWORD *)((char *)this + v29 + 1856) )
      goto LABEL_29;
LABEL_30:
    v26 = h;
    SelectObject(a2, h);
    DeleteObject(ho);
    v18 = v46;
    ++v28;
  }
  while ( v28 < 0x14 );
  SelectObject(a2, v26);
  SetTextAlign(a2, align);
  SetTextColor(a2, color);
  SetBkColor(a2, v50);
  DeleteObject(FontIndirectW);
  return v27;
}

```

## disassembly

```asm
0x180023ed8  push    rbp
0x180023eda  push    rbx
0x180023edb  push    rsi
0x180023edc  push    rdi
0x180023edd  push    r12
0x180023edf  push    r13
0x180023ee1  push    r14
0x180023ee3  push    r15
0x180023ee5  lea     rbp, [rsp-78h]
0x180023eea  sub     rsp, 178h
0x180023ef1  mov     rax, cs:__security_cookie
0x180023ef8  xor     rax, rsp
0x180023efb  mov     [rbp+0B0h+var_48], rax
0x180023eff  mov     rax, [rbp+0B0h+arg_20]
0x180023f06  mov     rdi, rdx
0x180023f09  mov     r15, [rbp+0B0h+arg_28]
0x180023f10  mov     rbx, r8
0x180023f13  mov     r14, rcx
0x180023f16  mov     [rsp+1B0h+var_170], r9d
0x180023f1b  mov     rcx, rdi; hdc
0x180023f1e  mov     [rsp+1B0h+var_148], rbx
0x180023f23  mov     edx, 5Ah ; 'Z'; index
0x180023f28  mov     [rbp+0B0h+var_120], rax
0x180023f2c  call    cs:__imp_GetDeviceCaps
0x180023f32  mov     edx, 18h; align
0x180023f37  mov     rcx, rdi; hdc
0x180023f3a  mov     esi, eax
0x180023f3c  mov     [rsp+1B0h+nNumerator], eax
0x180023f40  call    cs:__imp_SetTextAlign
0x180023f46  mov     edx, [r14+80h]; color
0x180023f4d  mov     rcx, rdi; hdc
0x180023f50  mov     [rsp+1B0h+align], eax
0x180023f54  call    cs:__imp_SetTextColor
0x180023f5a  mov     edx, [r14+84h]; color
0x180023f61  mov     rcx, rdi; hdc
0x180023f64  mov     [rsp+1B0h+color], eax
0x180023f68  call    cs:__imp_SetBkColor
0x180023f6e  movaps  xmm1, xmmword ptr [r15+10h]
0x180023f73  mov     r8d, 48h ; 'H'; nDenominator
0x180023f79  movaps  xmm0, xmmword ptr [r15]
0x180023f7d  mov     edx, esi; nNumerator
0x180023f7f  movaps  xmmword ptr [rbp+0B0h+lf.lfWeight], xmm1
0x180023f83  movaps  xmm1, xmmword ptr [r15+30h]
0x180023f88  movaps  xmmword ptr [rbp+0B0h+lf.lfHeight], xmm0
0x180023f8c  lea     ecx, [r8-52h]; nNumber
0x180023f90  movaps  xmm0, xmmword ptr [r15+20h]
0x180023f95  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+14h], xmm1
0x180023f99  movups  xmm1, xmmword ptr [r15+4Ch]
0x180023f9e  mov     [rsp+1B0h+var_158], eax
0x180023fa2  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+4], xmm0
0x180023fa6  movaps  xmm0, xmmword ptr [r15+40h]
0x180023fab  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+24h], xmm0
0x180023faf  movups  xmmword ptr [rbp+0B0h+lf.lfFaceName+30h], xmm1
0x180023fb3  call    cs:__imp_MulDiv
0x180023fb9  cmp     dword ptr [r14+0ECh], 0
0x180023fc1  lea     rcx, [r14+90h]
0x180023fc8  mov     [rbp+0B0h+lf.lfHeight], eax
0x180023fcb  jnz     short loc_180023FD1
0x180023fcd  lea     rcx, [rbp+0B0h+lf]; lplf
0x180023fd1  call    cs:__imp_CreateFontIndirectW
0x180023fd7  mov     rdx, rax; h
0x180023fda  mov     [rsp+1B0h+var_138], rax
0x180023fdf  mov     rcx, rdi; hdc
0x180023fe2  call    cs:__imp_SelectObject
0x180023fe8  or      r13d, 0FFFFFFFFh
0x180023fec  mov     qword ptr [rsp+1B0h+psizl.cx], 0
0x180023ff5  mov     [rsp+1B0h+h], rax
0x180023ffa  or      ecx, r13d
0x180023ffd  mov     eax, [rbx+8]
0x180024000  sub     eax, [rbx]
0x180024002  mov     [rsp+1B0h+x], eax
0x180024006  xor     esi, esi
0x180024008  mov     [rsp+1B0h+var_168], ecx
0x18002400c  movsxd  r12, esi
0x18002400f  shl     r12, 5
0x180024013  mov     eax, [r12+r14+738h]
0x18002401b  test    eax, eax
0x18002401d  jz      loc_18002411A
0x180024023  cmp     eax, 1
0x180024026  jnz     loc_18002410F
0x18002402c  movaps  xmm1, xmmword ptr [r15+10h]
0x180024031  movaps  xmm0, xmmword ptr [r15]
0x180024035  movaps  xmmword ptr [rbp+0B0h+lf.lfWeight], xmm1
0x180024039  movaps  xmm1, xmmword ptr [r15+30h]
0x18002403e  movaps  xmmword ptr [rbp+0B0h+lf.lfHeight], xmm0
0x180024042  movaps  xmm0, xmmword ptr [r15+20h]
0x180024047  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+14h], xmm1
0x18002404b  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+4], xmm0
0x18002404f  movaps  xmm0, xmmword ptr [r15+40h]
0x180024054  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+24h], xmm0
0x180024058  movups  xmm1, xmmword ptr [r15+4Ch]
0x18002405d  movups  xmmword ptr [rbp+0B0h+lf.lfFaceName+30h], xmm1
0x180024061  cmp     r13d, 0FFFFFFFFh
0x180024065  jnz     short loc_18002406F
0x180024067  mov     r13d, [r12+r14+73Ch]
0x18002406f  mov     edx, [rsp+1B0h+nNumerator]; nNumerator
0x180024073  mov     ecx, r13d
0x180024076  neg     ecx; nNumber
0x180024078  mov     r8d, 48h ; 'H'; nDenominator
0x18002407e  call    cs:__imp_MulDiv
0x180024084  lea     rcx, [rbp+0B0h+lf]; lplf
0x180024088  mov     [rsp+1B0h+var_168], eax
0x18002408c  mov     [rbp+0B0h+lf.lfHeight], eax
0x18002408f  call    cs:__imp_CreateFontIndirectW
0x180024095  mov     rdx, rax; h
0x180024098  mov     rcx, rdi; hdc
0x18002409b  mov     rbx, rax
0x18002409e  call    cs:__imp_SelectObject
0x1800240a4  mov     r8d, [r12+r14+750h]; c
0x1800240ac  lea     r9, [rsp+1B0h+psizl]; psizl
0x1800240b1  mov     rdx, [r12+r14+748h]; lpString
0x1800240b9  mov     rcx, rdi; hdc
0x1800240bc  call    cs:__imp_GetTextExtentPoint32W
0x1800240c2  mov     rdx, [rsp+1B0h+h]; h
0x1800240c7  mov     rcx, rdi; hdc
0x1800240ca  call    cs:__imp_SelectObject
0x1800240d0  mov     rcx, rbx; ho
0x1800240d3  call    cs:__imp_DeleteObject
0x1800240d9  mov     eax, [rsp+1B0h+x]
0x1800240dd  cmp     [rsp+1B0h+psizl.cx], eax
0x1800240e1  jle     short loc_18002410B
0x1800240e3  imul    eax, r13d
0x1800240e7  mov     r8d, 48h ; 'H'; nDenominator
0x1800240ed  cdq
0x1800240ee  idiv    [rsp+1B0h+psizl.cx]
0x1800240f2  mov     edx, [rsp+1B0h+nNumerator]; nNumerator
0x1800240f6  mov     ecx, eax
0x1800240f8  mov     r13d, eax
0x1800240fb  neg     ecx; nNumber
0x1800240fd  call    cs:__imp_MulDiv
0x180024103  mov     ecx, eax
0x180024105  mov     [rsp+1B0h+var_168], eax
0x180024109  jmp     short loc_18002410F
0x18002410b  mov     ecx, [rsp+1B0h+var_168]
0x18002410f  inc     esi
0x180024111  cmp     esi, 14h
0x180024114  jb      loc_18002400C
0x18002411a  mov     esi, [rsp+1B0h+var_170]
0x18002411e  xor     eax, eax
0x180024120  mov     r12, [rsp+1B0h+h]
0x180024125  neg     esi
0x180024127  xorps   xmm0, xmm0
0x18002412a  mov     [rbp+0B0h+var_50], eax
0x18002412d  xor     r13d, r13d
0x180024130  movups  xmmword ptr [rbp+0B0h+String], xmm0
0x180024134  movsxd  rbx, r13d
0x180024137  shl     rbx, 5
0x18002413b  mov     eax, [rbx+r14+738h]
0x180024143  test    eax, eax
0x180024145  jz      loc_180024429
0x18002414b  movaps  xmm1, xmmword ptr [r15+10h]
0x180024150  lea     r12, [rbx+r14]
0x180024154  movaps  xmm0, xmmword ptr [r15]
0x180024158  movaps  xmmword ptr [rbp+0B0h+lf.lfWeight], xmm1
0x18002415c  movaps  xmm1, xmmword ptr [r15+30h]
0x180024161  movaps  xmmword ptr [rbp+0B0h+lf.lfHeight], xmm0
0x180024165  movaps  xmm0, xmmword ptr [r15+20h]
0x18002416a  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+14h], xmm1
0x18002416e  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+4], xmm0
0x180024172  movaps  xmm0, xmmword ptr [r15+40h]
0x180024177  movaps  xmmword ptr [rbp+0B0h+lf.lfFaceName+24h], xmm0
0x18002417b  movups  xmm1, xmmword ptr [r15+4Ch]
0x180024180  movups  xmmword ptr [rbp+0B0h+lf.lfFaceName+30h], xmm1
0x180024184  cmp     eax, 1
0x180024187  jnz     short loc_18002418E
0x180024189  mov     [rbp+0B0h+lf.lfHeight], ecx
0x18002418c  jmp     short loc_1800241AB
0x18002418e  mov     ecx, [r12+73Ch]
0x180024196  mov     r8d, 48h ; 'H'; nDenominator
0x18002419c  mov     edx, [rsp+1B0h+nNumerator]; nNumerator
0x1800241a0  neg     ecx; nNumber
0x1800241a2  call    cs:__imp_MulDiv
0x1800241a8  mov     [rbp+0B0h+lf.lfHeight], eax
0x1800241ab  lea     rcx, [rbp+0B0h+lf]; lplf
0x1800241af  call    cs:__imp_CreateFontIndirectW
0x1800241b5  mov     rdx, rax; h
0x1800241b8  mov     [rbp+0B0h+ho], rax
0x1800241bc  mov     rcx, rdi; hdc
0x1800241bf  call    cs:__imp_SelectObject
0x1800241c5  xorps   xmm0, xmm0
0x1800241c8  lea     rdx, [rbp+0B0h+tm]; lptm
0x1800241cc  movups  xmmword ptr [rbp+0B0h+tm.tmOverhang], xmm0
0x1800241d0  mov     rcx, rdi; hdc
0x1800241d3  movups  xmmword ptr [rbp+0B0h+tm.tmFirstChar], xmm0
0x1800241d7  movups  xmmword ptr [rbp+0B0h+tm.tmHeight], xmm0
0x1800241db  movups  xmmword ptr [rbp+0B0h+tm.tmExternalLeading], xmm0
0x1800241df  call    cs:__imp_GetTextMetricsW
0x1800241e5  mov     eax, [rbp+0B0h+tm.tmExternalLeading]
0x1800241e8  xorps   xmm0, xmm0
0x1800241eb  mov     edx, [rbp+0B0h+tm.tmAscent]
0x1800241ee  add     eax, edx
0x1800241f0  mov     ecx, [rbx+r14+738h]
0x1800241f8  add     esi, eax
0x1800241fa  movups  xmmword ptr [rbp+0B0h+rc.left], xmm0
0x1800241fe  sub     ecx, 1
0x180024201  jz      loc_180024349
0x180024207  cmp     ecx, 1
0x18002420a  jnz     loc_1800243C3
0x180024210  mov     rdx, [rsp+1B0h+var_138]; h
0x180024215  mov     rcx, rdi; hdc
0x180024218  mov     qword ptr [rbp+0B0h+var_130.cx], 0
0x180024220  call    cs:__imp_SelectObject
0x180024226  mov     r9d, [r12+73Ch]
0x18002422e  lea     r8, aD; "%d"
0x180024235  mov     edx, 0Ah; unsigned __int64
0x18002423a  lea     rcx, [rbp+0B0h+String]; unsigned __int16 *
0x18002423e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024243  lea     rcx, [rbp+0B0h+String]; lpString
0x180024247  call    cs:__imp_lstrlenW
0x18002424d  mov     r12, [rsp+1B0h+var_148]
0x180024252  mov     [rsp+1B0h+var_170], eax
0x180024256  mov     r8d, [r12]
0x18002425a  mov     [rsp+1B0h+x], r8d
0x18002425f  test    eax, eax
0x180024261  jz      short loc_180024283
0x180024263  mov     rcx, rdi; hdc
0x180024266  call    cs:__imp_GetLayout
0x18002426c  cmp     eax, 0FFFFFFFFh
0x18002426f  jz      short loc_18002427F
0x180024271  test    al, 1
0x180024273  mov     eax, [rsp+1B0h+var_170]
0x180024277  jz      short loc_180024283
0x180024279  dec     [rsp+1B0h+x]
0x18002427d  jmp     short loc_180024283
0x18002427f  mov     eax, [rsp+1B0h+var_170]
0x180024283  mov     edx, [rsp+1B0h+x]; x
0x180024287  mov     r9d, 4; options
0x18002428d  mov     [rsp+1B0h+lpDx], 0; lpDx
0x180024296  mov     r8d, esi; y
0x180024299  mov     [rsp+1B0h+c], eax; c
0x18002429d  mov     rcx, rdi; hdc
0x1800242a0  lea     rax, [rbp+0B0h+String]
0x1800242a4  mov     [rsp+1B0h+lpString], rax; lpString
0x1800242a9  mov     rax, [rbp+0B0h+var_120]
0x1800242ad  mov     [rsp+1B0h+lprect], rax; lprect
0x1800242b2  call    cs:__imp_ExtTextOutW
0x1800242b8  mov     r8d, [rsp+1B0h+var_170]; c
0x1800242bd  lea     r9, [rbp+0B0h+var_130]; psizl
0x1800242c1  lea     rdx, [rbp+0B0h+String]; lpString
0x1800242c5  mov     rcx, rdi; hdc
0x1800242c8  call    cs:__imp_GetTextExtentPoint32W
0x1800242ce  mov     rdx, [rbp+0B0h+ho]; h
0x1800242d2  mov     rcx, rdi; hdc
0x1800242d5  call    cs:__imp_SelectObject
0x1800242db  mov     ecx, [r12]
0x1800242df  mov     r8d, esi
0x1800242e2  mov     eax, [rbp+0B0h+var_130.cx]
0x1800242e5  mov     r9d, [rbp+0B0h+tm.tmDescent]
0x1800242e9  sub     r8d, [rbp+0B0h+tm.tmAscent]; yTop
0x1800242ed  add     r9d, esi
0x1800242f0  mov     dword ptr [rsp+1B0h+lprect], r9d; yBottom
0x1800242f5  mov     r9d, [r12+8]; xRight
0x1800242fa  lea     edx, [rcx+rax*2]; xLeft
0x1800242fd  lea     rcx, [rbp+0B0h+rc]; lprc
0x180024301  call    cs:__imp_SetRect
0x180024307  mov     edx, [rsp+1B0h+align]; align
0x18002430b  mov     rcx, rdi; hdc
0x18002430e  call    cs:__imp_SetTextAlign
0x180024314  mov     r8d, [rbx+r14+750h]; cchText
0x18002431c  lea     r9, [rbp+0B0h+rc]; lprc
0x180024320  mov     rdx, [rbx+r14+748h]; lpchText
0x180024328  mov     rcx, rdi; hdc
0x18002432b  mov     dword ptr [rsp+1B0h+lprect], 800h; format
0x180024333  call    cs:__imp_DrawTextW
0x180024339  mov     edx, 18h; align
0x18002433e  mov     rcx, rdi; hdc
0x180024341  call    cs:__imp_SetTextAlign
0x180024347  jmp     short loc_1800243C8
0x180024349  mov     ecx, [rbp+0B0h+tm.tmDescent]
0x18002434c  mov     r8d, esi
0x18002434f  mov     r12, [rsp+1B0h+var_148]
0x180024354  add     ecx, esi
0x180024356  mov     dword ptr [rsp+1B0h+lprect], ecx; yBottom
0x18002435a  sub     r8d, edx; yTop
0x18002435d  lea     rcx, [rbp+0B0h+rc]; lprc
0x180024361  mov     r9d, [r12+8]; xRight
0x180024366  mov     edx, [r12]; xLeft
0x18002436a  call    cs:__imp_SetRect
0x180024370  mov     edx, [rsp+1B0h+align]; align
0x180024374  mov     rcx, rdi; hdc
0x180024377  call    cs:__imp_SetTextAlign
0x18002437d  mov     r8d, [rbx+r14+750h]; cchText
0x180024385  lea     r9, [rbp+0B0h+rc]; lprc
0x180024389  mov     rdx, [rbx+r14+748h]; lpchText
0x180024391  mov     rcx, rdi; hdc
0x180024394  mov     dword ptr [rsp+1B0h+lprect], 810h; format
0x18002439c  call    cs:__imp_DrawTextW
0x1800243a2  mov     edx, 18h; align
0x1800243a7  mov     rcx, rdi; hdc
0x1800243aa  call    cs:__imp_SetTextAlign
0x1800243b0  cmp     dword ptr [rbx+r14+740h], 0
0x1800243b9  jz      short loc_1800243C8
0x1800243bb  mov     eax, [rbp+0B0h+tm.tmDescent]
0x1800243be  lea     esi, [rsi+rax*2]
0x1800243c1  jmp     short loc_1800243D6
0x1800243c3  mov     r12, [rsp+1B0h+var_148]
0x1800243c8  add     esi, [rbp+0B0h+tm.tmDescent]
0x1800243cb  cmp     dword ptr [rbx+r14+740h], 0
0x1800243d4  jz      short loc_1800243FD
0x1800243d6  mov     edx, [r12]; x
  ... truncated ...
```
