# CBrandingBar::Initialize(tagBRANDING_BAR_TEXT *,int)

- ea: `0x14004d40c`
- end: `0x14004db4c`
- name: `?Initialize@CBrandingBar@@QEAAHPEAUtagBRANDING_BAR_TEXT@@H@Z`
- size: `1856`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this, struct tagBRANDING_BAR_TEXT *, int)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021968`
- `0x140049898`
- `0x140049fa0`
- `0x140054968`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14001e290`
- `0x14004d40c`
- `0x14004def8`
- `0x140097b90`
- `0x1400a1fe0`
- `0x140113390`

## import_xrefs

- `USER32!DrawIconEx` at `0x14004d939`
- `USER32!DrawIconEx` at `0x14004d939`
- `USER32!GetWindowDC` at `0x14004d6e0`
- `USER32!GetWindowDC` at `0x14004d6e0`
- `USER32!ReleaseDC` at `0x14004d99d`
- `USER32!ReleaseDC` at `0x14004d99d`
- `USER32!GetClientRect` at `0x14004d679`
- `USER32!GetClientRect` at `0x14004d679`
- `USER32!GetSystemMetrics` at `0x14004d8e3`
- `USER32!GetSystemMetrics` at `0x14004d8f8`
- `USER32!GetSystemMetrics` at `0x14004d8e3`
- `USER32!GetSystemMetrics` at `0x14004d8f8`
- `KERNEL32!GetLastError` at `0x14004d9b6`
- `KERNEL32!GetLastError` at `0x14004d9b6`
- `GDI32!DeleteDC` at `0x14004d987`
- `GDI32!DeleteDC` at `0x14004d990`
- `GDI32!DeleteDC` at `0x14004d987`
- `GDI32!DeleteDC` at `0x14004d990`
- `GDI32!StretchBlt` at `0x14004d859`
- `GDI32!StretchBlt` at `0x14004d859`
- `GDI32!BitBlt` at `0x14004d7e1`
- `GDI32!BitBlt` at `0x14004d8c0`
- `GDI32!BitBlt` at `0x14004d7e1`
- `GDI32!BitBlt` at `0x14004d8c0`
- `GDI32!CreateCompatibleBitmap` at `0x14004d6fb`
- `GDI32!CreateCompatibleBitmap` at `0x14004d6fb`
- `GDI32!CreateCompatibleDC` at `0x14004d708`
- `GDI32!CreateCompatibleDC` at `0x14004d714`
- `GDI32!CreateCompatibleDC` at `0x14004d708`
- `GDI32!CreateCompatibleDC` at `0x14004d714`
- `GDI32!GetObjectW` at `0x14004d51a`
- `GDI32!GetObjectW` at `0x14004d581`
- `GDI32!GetObjectW` at `0x14004d5e8`
- `GDI32!GetObjectW` at `0x14004d51a`
- `GDI32!GetObjectW` at `0x14004d581`
- `GDI32!GetObjectW` at `0x14004d5e8`
- `GDI32!SelectObject` at `0x14004d790`
- `GDI32!SelectObject` at `0x14004d7a9`
- `GDI32!SelectObject` at `0x14004d7f6`
- `GDI32!SelectObject` at `0x14004d80b`
- `GDI32!SelectObject` at `0x14004d86e`
- `GDI32!SelectObject` at `0x14004d883`
- `GDI32!SelectObject` at `0x14004d8d1`
- `GDI32!SelectObject` at `0x14004d94e`
- `GDI32!SelectObject` at `0x14004d790`
- `GDI32!SelectObject` at `0x14004d7a9`
- `GDI32!SelectObject` at `0x14004d7f6`
- `GDI32!SelectObject` at `0x14004d80b`
- `GDI32!SelectObject` at `0x14004d86e`
- `GDI32!SelectObject` at `0x14004d883`
- `GDI32!SelectObject` at `0x14004d8d1`
- `GDI32!SelectObject` at `0x14004d94e`
- `GDI32!RealizePalette` at `0x14004d779`
- `GDI32!RealizePalette` at `0x14004d779`
- `GDI32!SelectPalette` at `0x14004d758`
- `GDI32!SelectPalette` at `0x14004d76c`
- `GDI32!SelectPalette` at `0x14004d966`
- `GDI32!SelectPalette` at `0x14004d97e`
- `GDI32!SelectPalette` at `0x14004d758`
- `GDI32!SelectPalette` at `0x14004d76c`
- `GDI32!SelectPalette` at `0x14004d966`
- `GDI32!SelectPalette` at `0x14004d97e`
- `GDI32!DeleteObject` at `0x14004da9a`
- `GDI32!DeleteObject` at `0x14004daf8`
- `GDI32!DeleteObject` at `0x14004db0a`
- `GDI32!DeleteObject` at `0x14004db1c`
- `GDI32!DeleteObject` at `0x14004da9a`
- `GDI32!DeleteObject` at `0x14004daf8`
- `GDI32!DeleteObject` at `0x14004db0a`
- `GDI32!DeleteObject` at `0x14004db1c`

## pseudocode

```c
__int64 __fastcall CBrandingBar::Initialize(CBrandingBar *this, struct tagBRANDING_BAR_TEXT *a2, int a3)
{
  int v3; // ebx
  int v4; // r12d
  int v6; // r13d
  unsigned int v7; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // esi
  int v10; // r15d
  int hDest; // ebx
  int v12; // r12d
  int v13; // ecx
  int v14; // edx
  int v15; // eax
  int v16; // r15d
  unsigned int v17; // eax
  int v18; // r12d
  unsigned int v19; // eax
  __int64 v20; // rdx
  HDC WindowDC; // rax
  HDC v22; // r15
  HDC CompatibleDC; // r12
  HDC v24; // rax
  HDC v25; // r13
  HBITMAP v26; // rdx
  HPALETTE PaletteForBitmap; // rax
  HGDIOBJ v28; // rbx
  int v29; // ebx
  int v30; // eax
  int v31; // r8d
  HBITMAP v32; // rbx
  DWORD LastError; // r15d
  unsigned int v34; // eax
  PVOID *v35; // rax
  unsigned int v36; // eax
  void *v37; // rcx
  HDC hdcSrc; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+60h] [rbp-A0h]
  int xDest; // [rsp+68h] [rbp-98h]
  int v42; // [rsp+70h] [rbp-90h]
  int wSrc; // [rsp+78h] [rbp-88h]
  HPALETTE hPala; // [rsp+80h] [rbp-80h]
  HBITMAP ho; // [rsp+88h] [rbp-78h]
  HBITMAP v47; // [rsp+90h] [rbp-70h]
  HBITMAP ImageFromResID; // [rsp+98h] [rbp-68h]
  HGDIOBJ v49; // [rsp+A0h] [rbp-60h]
  HGDIOBJ v50; // [rsp+A0h] [rbp-60h]
  HPALETTE v51; // [rsp+A8h] [rbp-58h]
  HBITMAP h; // [rsp+B0h] [rbp-50h]
  HGDIOBJ v53; // [rsp+B8h] [rbp-48h]
  struct tagRECT Rect; // [rsp+C8h] [rbp-38h] BYREF
  int pv; // [rsp+E0h] [rbp-20h] BYREF
  int v57; // [rsp+E4h] [rbp-1Ch] BYREF
  int cy; // [rsp+E8h] [rbp-18h]

  v3 = *((_DWORD *)this + 10);
  v4 = *((_DWORD *)this + 11);
  v6 = *((_DWORD *)this + 12);
  Rect = 0;
  v47 = 0;
  ho = 0;
  ImageFromResID = 0;
  v7 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
      CurrentThreadActivityIdPrefix,
      v3,
      v4,
      v6);
  }
  if ( v3
    && (ho = LoadImageFromResID(*((HINSTANCE *)this + 2), (const unsigned __int16 *)(unsigned __int16)v3)) != 0
    && (pv = 0, memset_0(&v57, 0, 0x64u), GetObjectW(ho, 104, &pv)) )
  {
    v9 = cy;
    if ( cy < 0 )
      v9 = -cy;
    v10 = v57;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  xDest = v10;
  if ( v4
    && (ImageFromResID = LoadImageFromResID(*((HINSTANCE *)this + 2), (const unsigned __int16 *)(unsigned __int16)v4)) != 0
    && (pv = 0, memset_0(&v57, 0, 0x64u), GetObjectW(ImageFromResID, 104, &pv)) )
  {
    hDest = cy;
    if ( cy < 0 )
      hDest = -cy;
    v12 = v57;
  }
  else
  {
    hDest = 0;
    v12 = 0;
  }
  wSrc = v12;
  if ( v6
    && (v47 = LoadImageFromResID(*((HINSTANCE *)this + 2), (const unsigned __int16 *)(unsigned __int16)v6)) != 0
    && (pv = 0, memset_0(&v57, 0, 0x64u), GetObjectW(v47, 104, &pv)) )
  {
    v13 = cy;
    if ( cy < 0 )
      v13 = -cy;
    v14 = v57;
  }
  else
  {
    v13 = 0;
    v14 = 0;
  }
  v42 = v14;
  v15 = v13;
  if ( hDest > v13 )
    v15 = hDest;
  if ( v9 <= v15 )
  {
    v9 = v13;
    if ( hDest > v13 )
      v9 = hDest;
  }
  v16 = v14 + v12 + v10;
  *((_DWORD *)this + 16) = v16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v17, v16);
  }
  GetClientRect(*((HWND *)this + 1), &Rect);
  v18 = Rect.right - Rect.left + 1;
  v40 = v18;
  if ( Rect.right - Rect.left == -1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_93;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 12;
LABEL_92:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v19);
LABEL_93:
    v7 = 0;
    goto LABEL_94;
  }
  if ( a3 )
    goto LABEL_94;
  if ( v9 <= 0 )
  {
    v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_88:
    if ( v35 == &WPP_GLOBAL_Control || (*((_BYTE *)v35 + 28) & 1) == 0 || *((_BYTE *)v35 + 25) < 2u )
      goto LABEL_93;
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 15;
    goto LABEL_92;
  }
  WindowDC = GetWindowDC(*((HWND *)this + 1));
  v22 = WindowDC;
  if ( WindowDC )
  {
    h = CreateCompatibleBitmap(WindowDC, v18, v9);
    CompatibleDC = CreateCompatibleDC(v22);
    v24 = CreateCompatibleDC(v22);
    v25 = v24;
    if ( CompatibleDC && v24 )
    {
      v26 = ho;
      if ( !ho )
        v26 = v47;
      PaletteForBitmap = CClientUtilsWin32::UT_GetPaletteForBitmap(v22, v26);
      *((_QWORD *)this + 3) = PaletteForBitmap;
      if ( PaletteForBitmap )
      {
        hPala = SelectPalette(v22, PaletteForBitmap, 0);
        v51 = SelectPalette(v25, *((HPALETTE *)this + 3), 0);
        RealizePalette(v22);
      }
      else
      {
        hPala = 0;
        v51 = 0;
      }
      v53 = SelectObject(v25, h);
      if ( ho )
      {
        v49 = SelectObject(CompatibleDC, ho);
        BitBlt(v25, 0, 0, v40, v9, CompatibleDC, 0, 0, 0xCC0020u);
        if ( v49 )
          SelectObject(CompatibleDC, v49);
      }
      if ( ImageFromResID )
      {
        v50 = SelectObject(CompatibleDC, ImageFromResID);
        StretchBlt(v25, xDest, 0, v40 - v42 - xDest, hDest, CompatibleDC, 0, 0, wSrc, hDest, 0xCC0020u);
        if ( v50 )
          SelectObject(CompatibleDC, v50);
      }
      if ( v47 )
      {
        v28 = SelectObject(CompatibleDC, v47);
        BitBlt(v25, v40 - v42, 0, v40, v9, CompatibleDC, 0, 0, 0xCC0020u);
        if ( v28 )
          SelectObject(CompatibleDC, v28);
      }
      if ( *((_QWORD *)this + 9) )
      {
        v29 = GetSystemMetrics(12) / 2;
        v30 = (v9 - GetSystemMetrics(12)) / 2;
        v31 = 0;
        if ( v30 >= 0 )
          v31 = v30;
        DrawIconEx(v25, v29, v31, *((HICON *)this + 9), 0, 0, 0, 0, 0xBu);
      }
      if ( v53 )
        SelectObject(v25, v53);
      if ( hPala )
        SelectPalette(v22, hPala, 1);
      if ( v51 )
        SelectPalette(v22, v51, 1);
      DeleteDC(CompatibleDC);
      DeleteDC(v25);
    }
    ReleaseDC(*((HWND *)this + 1), v22);
    v18 = v40;
    v32 = h;
  }
  else
  {
    v32 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(hdcSrc) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
        v34,
        (__int64)"GetWindowDC failed",
        hdcSrc);
    }
  }
  *((_DWORD *)this + 8) = v18;
  *((_DWORD *)this + 9) = v9;
  v35 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v36, v18, v9);
    v35 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v32 )
    goto LABEL_88;
  if ( a2 )
  {
    if ( xDest )
      *(_DWORD *)a2 = xDest;
    CBrandingBar::PaintBrandingText(this, v32, a2);
  }
  v37 = (void *)*((_QWORD *)this + 7);
  if ( v37 )
    DeleteObject(v37);
  *((_QWORD *)this + 7) = v32;
LABEL_94:
  if ( ho )
    DeleteObject(ho);
  if ( ImageFromResID )
    DeleteObject(ImageFromResID);
  if ( v47 )
    DeleteObject(v47);
  return v7;
}

```

## disassembly

```asm
0x14004d40c  mov     [rsp-8+arg_10], rbx
0x14004d411  push    rbp
0x14004d412  push    rsi
0x14004d413  push    rdi
0x14004d414  push    r12
0x14004d416  push    r13
0x14004d418  push    r14
0x14004d41a  push    r15
0x14004d41c  lea     rbp, [rsp-60h]
0x14004d421  sub     rsp, 160h
0x14004d428  mov     rax, cs:__security_cookie
0x14004d42f  xor     rax, rsp
0x14004d432  mov     [rbp+90h+var_40], rax
0x14004d436  mov     ebx, [rcx+28h]
0x14004d439  xorps   xmm0, xmm0
0x14004d43c  mov     r12d, [rcx+2Ch]
0x14004d440  mov     rdi, rcx
0x14004d443  mov     r13d, [rcx+30h]
0x14004d447  movups  xmmword ptr [rbp+90h+Rect.left], xmm0
0x14004d44b  mov     dword ptr [rbp+90h+hPal], r8d
0x14004d44f  mov     [rbp+90h+var_D0], rdx
0x14004d453  mov     qword ptr [rsp+190h+var_130], 0
0x14004d45c  mov     qword ptr [rsp+190h+wSrc], 0
0x14004d465  mov     [rsp+190h+var_120], 0
0x14004d46e  mov     [rbp+90h+var_100], 0
0x14004d476  mov     [rbp+90h+ho], 0
0x14004d47e  mov     [rbp+90h+var_F8], 0
0x14004d486  mov     rax, cs:WPP_GLOBAL_Control
0x14004d48d  lea     rcx, WPP_GLOBAL_Control
0x14004d494  mov     r14d, 1
0x14004d49a  cmp     rax, rcx
0x14004d49d  jz      short loc_14004D4DC
0x14004d49f  test    [rax+1Ch], r14b
0x14004d4a3  jz      short loc_14004D4DC
0x14004d4a5  cmp     byte ptr [rax+19h], 4
0x14004d4a9  jb      short loc_14004D4DC
0x14004d4ab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d4b7  lea     edx, [r14+9]
0x14004d4bb  mov     [rsp+190h+x1], r13d
0x14004d4c0  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004d4c7  mov     dword ptr [rsp+190h+hdcSrc], r12d
0x14004d4cc  mov     r9d, eax
0x14004d4cf  mov     [rsp+190h+hDest], ebx
0x14004d4d3  mov     rcx, [rcx+10h]
0x14004d4d7  call    WPP_SF_DDdd
0x14004d4dc  test    ebx, ebx
0x14004d4de  jz      short loc_14004D533
0x14004d4e0  mov     rcx, [rdi+10h]; HINSTANCE
0x14004d4e4  movzx   edx, bx; unsigned __int16 *
0x14004d4e7  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004d4ec  mov     [rbp+90h+ho], rax
0x14004d4f0  mov     r15, rax
0x14004d4f3  test    rax, rax
0x14004d4f6  jz      short loc_14004D533
0x14004d4f8  xor     edx, edx; Val
0x14004d4fa  mov     [rbp+90h+pv], 0
0x14004d501  lea     rcx, [rbp+90h+var_AC]; void *
0x14004d505  lea     r8d, [rdx+64h]; Size
0x14004d509  call    memset_0
0x14004d50e  lea     r8, [rbp+90h+pv]; pv
0x14004d512  mov     edx, 68h ; 'h'; c
0x14004d517  mov     rcx, r15; h
0x14004d51a  call    cs:__imp_GetObjectW
0x14004d520  test    eax, eax
0x14004d522  jz      short loc_14004D533
0x14004d524  mov     esi, [rbp+90h+cy]
0x14004d527  test    esi, esi
0x14004d529  jns     short loc_14004D52D
0x14004d52b  neg     esi
0x14004d52d  mov     r15d, [rbp+90h+var_AC]
0x14004d531  jmp     short loc_14004D53C
0x14004d533  mov     esi, [rsp+190h+wSrc+4]
0x14004d537  mov     r15d, [rsp+190h+wSrc]
0x14004d53c  mov     [rsp+190h+xDest], r15d
0x14004d541  test    r12d, r12d
0x14004d544  jz      short loc_14004D59A
0x14004d546  mov     rcx, [rdi+10h]; HINSTANCE
0x14004d54a  movzx   edx, r12w; unsigned __int16 *
0x14004d54e  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004d553  mov     [rbp+90h+var_F8], rax
0x14004d557  mov     rbx, rax
0x14004d55a  test    rax, rax
0x14004d55d  jz      short loc_14004D59A
0x14004d55f  xor     edx, edx; Val
0x14004d561  mov     [rbp+90h+pv], 0
0x14004d568  lea     rcx, [rbp+90h+var_AC]; void *
0x14004d56c  lea     r8d, [rdx+64h]; Size
0x14004d570  call    memset_0
0x14004d575  lea     r8, [rbp+90h+pv]; pv
0x14004d579  mov     edx, 68h ; 'h'; c
0x14004d57e  mov     rcx, rbx; h
0x14004d581  call    cs:__imp_GetObjectW
0x14004d587  test    eax, eax
0x14004d589  jz      short loc_14004D59A
0x14004d58b  mov     ebx, [rbp+90h+cy]
0x14004d58e  test    ebx, ebx
0x14004d590  jns     short loc_14004D594
0x14004d592  neg     ebx
0x14004d594  mov     r12d, [rbp+90h+var_AC]
0x14004d598  jmp     short loc_14004D5A3
0x14004d59a  mov     ebx, dword ptr [rsp+190h+var_120+4]
0x14004d59e  mov     r12d, dword ptr [rsp+190h+var_120]
0x14004d5a3  mov     [rsp+190h+wSrc], r12d
0x14004d5a8  test    r13d, r13d
0x14004d5ab  jz      short loc_14004D600
0x14004d5ad  mov     rcx, [rdi+10h]; HINSTANCE
0x14004d5b1  movzx   edx, r13w; unsigned __int16 *
0x14004d5b5  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004d5ba  mov     [rbp+90h+var_100], rax
0x14004d5be  mov     r13, rax
0x14004d5c1  test    rax, rax
0x14004d5c4  jz      short loc_14004D600
0x14004d5c6  xor     edx, edx; Val
0x14004d5c8  mov     [rbp+90h+pv], 0
0x14004d5cf  lea     rcx, [rbp+90h+var_AC]; void *
0x14004d5d3  lea     r8d, [rdx+64h]; Size
0x14004d5d7  call    memset_0
0x14004d5dc  lea     r8, [rbp+90h+pv]; pv
0x14004d5e0  mov     edx, 68h ; 'h'; c
0x14004d5e5  mov     rcx, r13; h
0x14004d5e8  call    cs:__imp_GetObjectW
0x14004d5ee  test    eax, eax
0x14004d5f0  jz      short loc_14004D600
0x14004d5f2  mov     ecx, [rbp+90h+cy]
0x14004d5f5  test    ecx, ecx
0x14004d5f7  jns     short loc_14004D5FB
0x14004d5f9  neg     ecx
0x14004d5fb  mov     edx, [rbp+90h+var_AC]
0x14004d5fe  jmp     short loc_14004D608
0x14004d600  mov     ecx, [rsp+190h+var_130+4]
0x14004d604  mov     edx, [rsp+190h+var_130]
0x14004d608  cmp     ebx, ecx
0x14004d60a  mov     dword ptr [rsp+190h+var_120], edx
0x14004d60e  mov     eax, ecx
0x14004d610  cmovg   eax, ebx
0x14004d613  cmp     esi, eax
0x14004d615  jg      short loc_14004D61E
0x14004d617  cmp     ebx, ecx
0x14004d619  mov     esi, ecx
0x14004d61b  cmovg   esi, ebx
0x14004d61e  lea     eax, [rdx+r12]
0x14004d622  add     r15d, eax
0x14004d625  mov     [rdi+40h], r15d
0x14004d629  mov     rax, cs:WPP_GLOBAL_Control
0x14004d630  lea     r13, WPP_GLOBAL_Control
0x14004d637  cmp     rax, r13
0x14004d63a  jz      short loc_14004D671
0x14004d63c  test    [rax+1Ch], r14b
0x14004d640  jz      short loc_14004D671
0x14004d642  cmp     byte ptr [rax+19h], 4
0x14004d646  jb      short loc_14004D671
0x14004d648  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d64d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d654  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004d65b  mov     edx, 0Bh
0x14004d660  mov     [rsp+190h+hDest], r15d
0x14004d665  mov     r9d, eax
0x14004d668  mov     rcx, [rcx+10h]
0x14004d66c  call    WPP_SF_Dd
0x14004d671  mov     rcx, [rdi+8]; hWnd
0x14004d675  lea     rdx, [rbp+90h+Rect]; lpRect
0x14004d679  call    cs:__imp_GetClientRect
0x14004d67f  mov     r12d, [rbp+90h+Rect.right]
0x14004d683  sub     r12d, [rbp+90h+Rect.left]
0x14004d687  add     r12d, r14d
0x14004d68a  mov     [rsp+190h+var_130], r12d
0x14004d68f  jnz     short loc_14004D6C4
0x14004d691  mov     rax, cs:WPP_GLOBAL_Control
0x14004d698  cmp     rax, r13
0x14004d69b  jz      loc_14004DAE9
0x14004d6a1  test    [rax+1Ch], r14b
0x14004d6a5  jz      loc_14004DAE9
0x14004d6ab  cmp     byte ptr [rax+19h], 2
0x14004d6af  jb      loc_14004DAE9
0x14004d6b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d6ba  mov     edx, 0Ch
0x14004d6bf  jmp     loc_14004DACF
0x14004d6c4  cmp     dword ptr [rbp+90h+hPal], 0
0x14004d6c8  jnz     loc_14004DAEC
0x14004d6ce  mov     r13d, 2
0x14004d6d4  test    esi, esi
0x14004d6d6  jle     loc_14004DAA6
0x14004d6dc  mov     rcx, [rdi+8]; hWnd
0x14004d6e0  call    cs:__imp_GetWindowDC
0x14004d6e6  mov     r15, rax
0x14004d6e9  test    rax, rax
0x14004d6ec  jz      loc_14004D9B4
0x14004d6f2  mov     r8d, esi; cy
0x14004d6f5  mov     edx, r12d; cx
0x14004d6f8  mov     rcx, rax; hdc
0x14004d6fb  call    cs:__imp_CreateCompatibleBitmap
0x14004d701  mov     rcx, r15; hdc
0x14004d704  mov     [rbp+90h+h], rax
0x14004d708  call    cs:__imp_CreateCompatibleDC
0x14004d70e  mov     rcx, r15; hdc
0x14004d711  mov     r12, rax
0x14004d714  call    cs:__imp_CreateCompatibleDC
0x14004d71a  mov     r13, rax
0x14004d71d  test    r12, r12
0x14004d720  jz      loc_14004D996
0x14004d726  test    rax, rax
0x14004d729  jz      loc_14004D996
0x14004d72f  mov     rax, [rbp+90h+ho]
0x14004d733  mov     rcx, r15; HDC
0x14004d736  test    rax, rax
0x14004d739  mov     rdx, rax
0x14004d73c  cmovz   rdx, [rbp+90h+var_100]; HBITMAP
0x14004d741  call    ?UT_GetPaletteForBitmap@CClientUtilsWin32@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAUHBITMAP__@@@Z; CClientUtilsWin32::UT_GetPaletteForBitmap(HDC__ *,HBITMAP__ *)
0x14004d746  mov     [rdi+18h], rax
0x14004d74a  test    rax, rax
0x14004d74d  jz      short loc_14004D781
0x14004d74f  xor     r8d, r8d; bForceBkgd
0x14004d752  mov     rdx, rax; hPal
0x14004d755  mov     rcx, r15; hdc
0x14004d758  call    cs:__imp_SelectPalette
0x14004d75e  mov     rdx, [rdi+18h]; hPal
0x14004d762  xor     r8d, r8d; bForceBkgd
0x14004d765  mov     rcx, r13; hdc
0x14004d768  mov     [rbp+90h+hPal], rax
0x14004d76c  call    cs:__imp_SelectPalette
0x14004d772  mov     rcx, r15; hdc
0x14004d775  mov     [rbp+90h+var_E8], rax
0x14004d779  call    cs:__imp_RealizePalette
0x14004d77f  jmp     short loc_14004D789
0x14004d781  mov     [rbp+90h+hPal], rax
0x14004d785  mov     [rbp+90h+var_E8], rax
0x14004d789  mov     rdx, [rbp+90h+h]; h
0x14004d78d  mov     rcx, r13; hdc
0x14004d790  call    cs:__imp_SelectObject
0x14004d796  mov     [rbp+90h+var_D8], rax
0x14004d79a  mov     rax, [rbp+90h+ho]
0x14004d79e  test    rax, rax
0x14004d7a1  jz      short loc_14004D7FC
0x14004d7a3  mov     rdx, rax; h
0x14004d7a6  mov     rcx, r12; hdc
0x14004d7a9  call    cs:__imp_SelectObject
0x14004d7af  mov     r9d, [rsp+190h+var_130]; cx
0x14004d7b4  xor     r8d, r8d; y
0x14004d7b7  mov     [rsp+190h+rop], 0CC0020h; rop
0x14004d7bf  xor     edx, edx; x
0x14004d7c1  mov     [rsp+190h+y1], 0; y1
0x14004d7c9  mov     rcx, r13; hdc
0x14004d7cc  mov     [rsp+190h+x1], 0; x1
0x14004d7d4  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004d7d9  mov     [rsp+190h+hDest], esi; cy
0x14004d7dd  mov     [rbp+90h+var_F0], rax
0x14004d7e1  call    cs:__imp_BitBlt
0x14004d7e7  mov     rax, [rbp+90h+var_F0]
0x14004d7eb  test    rax, rax
0x14004d7ee  jz      short loc_14004D7FC
0x14004d7f0  mov     rdx, rax; h
0x14004d7f3  mov     rcx, r12; hdc
0x14004d7f6  call    cs:__imp_SelectObject
0x14004d7fc  mov     rax, [rbp+90h+var_F8]
0x14004d800  test    rax, rax
0x14004d803  jz      short loc_14004D874
0x14004d805  mov     rdx, rax; h
0x14004d808  mov     rcx, r12; hdc
0x14004d80b  call    cs:__imp_SelectObject
0x14004d811  mov     r9d, [rsp+190h+var_130]
0x14004d816  xor     r8d, r8d; yDest
0x14004d819  sub     r9d, dword ptr [rsp+190h+var_120]
0x14004d81e  mov     rcx, r13; hdcDest
0x14004d821  mov     edx, [rsp+190h+xDest]; xDest
0x14004d825  sub     r9d, edx; wDest
0x14004d828  mov     [rsp+190h+var_140], 0CC0020h; rop
0x14004d830  mov     [rsp+190h+hSrc], ebx; hSrc
0x14004d834  mov     [rbp+90h+var_F0], rax
0x14004d838  mov     eax, [rsp+190h+wSrc]
0x14004d83c  mov     [rsp+190h+rop], eax; wSrc
0x14004d840  mov     [rsp+190h+y1], 0; ySrc
0x14004d848  mov     [rsp+190h+x1], 0; xSrc
0x14004d850  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004d855  mov     [rsp+190h+hDest], ebx; hDest
0x14004d859  call    cs:__imp_StretchBlt
0x14004d85f  mov     rax, [rbp+90h+var_F0]
0x14004d863  test    rax, rax
0x14004d866  jz      short loc_14004D874
0x14004d868  mov     rdx, rax; h
0x14004d86b  mov     rcx, r12; hdc
0x14004d86e  call    cs:__imp_SelectObject
0x14004d874  mov     rax, [rbp+90h+var_100]
0x14004d878  test    rax, rax
0x14004d87b  jz      short loc_14004D8D7
0x14004d87d  mov     rdx, rax; h
0x14004d880  mov     rcx, r12; hdc
0x14004d883  call    cs:__imp_SelectObject
0x14004d889  mov     edx, [rsp+190h+var_130]
0x14004d88d  xor     r8d, r8d; y
0x14004d890  sub     edx, dword ptr [rsp+190h+var_120]; x
0x14004d894  mov     rcx, r13; hdc
0x14004d897  mov     r9d, [rsp+190h+var_130]; cx
0x14004d89c  mov     rbx, rax
0x14004d89f  mov     [rsp+190h+rop], 0CC0020h; rop
0x14004d8a7  mov     [rsp+190h+y1], 0; y1
0x14004d8af  mov     [rsp+190h+x1], 0; x1
0x14004d8b7  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004d8bc  mov     [rsp+190h+hDest], esi; cy
0x14004d8c0  call    cs:__imp_BitBlt
  ... truncated ...
```
