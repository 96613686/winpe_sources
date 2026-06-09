# CBrandingBar::Initialize(tagBRANDING_BAR_TEXT *,int)

- ea: `0x14004b29c`
- end: `0x14004b9dc`
- name: `?Initialize@CBrandingBar@@QEAAHPEAUtagBRANDING_BAR_TEXT@@H@Z`
- size: `1856`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this, struct tagBRANDING_BAR_TEXT *, int)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021968`
- `0x140047728`
- `0x140047e30`
- `0x1400527f8`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14001e290`
- `0x14004b29c`
- `0x14004bd88`
- `0x140095a20`
- `0x14009fe70`
- `0x140111220`

## import_xrefs

- `USER32!DrawIconEx` at `0x14004b7c9`
- `USER32!DrawIconEx` at `0x14004b7c9`
- `USER32!GetWindowDC` at `0x14004b570`
- `USER32!GetWindowDC` at `0x14004b570`
- `USER32!ReleaseDC` at `0x14004b82d`
- `USER32!ReleaseDC` at `0x14004b82d`
- `USER32!GetClientRect` at `0x14004b509`
- `USER32!GetClientRect` at `0x14004b509`
- `USER32!GetSystemMetrics` at `0x14004b773`
- `USER32!GetSystemMetrics` at `0x14004b788`
- `USER32!GetSystemMetrics` at `0x14004b773`
- `USER32!GetSystemMetrics` at `0x14004b788`
- `KERNEL32!GetLastError` at `0x14004b846`
- `KERNEL32!GetLastError` at `0x14004b846`
- `GDI32!DeleteDC` at `0x14004b817`
- `GDI32!DeleteDC` at `0x14004b820`
- `GDI32!DeleteDC` at `0x14004b817`
- `GDI32!DeleteDC` at `0x14004b820`
- `GDI32!StretchBlt` at `0x14004b6e9`
- `GDI32!StretchBlt` at `0x14004b6e9`
- `GDI32!BitBlt` at `0x14004b671`
- `GDI32!BitBlt` at `0x14004b750`
- `GDI32!BitBlt` at `0x14004b671`
- `GDI32!BitBlt` at `0x14004b750`
- `GDI32!CreateCompatibleBitmap` at `0x14004b58b`
- `GDI32!CreateCompatibleBitmap` at `0x14004b58b`
- `GDI32!CreateCompatibleDC` at `0x14004b598`
- `GDI32!CreateCompatibleDC` at `0x14004b5a4`
- `GDI32!CreateCompatibleDC` at `0x14004b598`
- `GDI32!CreateCompatibleDC` at `0x14004b5a4`
- `GDI32!GetObjectW` at `0x14004b3aa`
- `GDI32!GetObjectW` at `0x14004b411`
- `GDI32!GetObjectW` at `0x14004b478`
- `GDI32!GetObjectW` at `0x14004b3aa`
- `GDI32!GetObjectW` at `0x14004b411`
- `GDI32!GetObjectW` at `0x14004b478`
- `GDI32!SelectObject` at `0x14004b620`
- `GDI32!SelectObject` at `0x14004b639`
- `GDI32!SelectObject` at `0x14004b686`
- `GDI32!SelectObject` at `0x14004b69b`
- `GDI32!SelectObject` at `0x14004b6fe`
- `GDI32!SelectObject` at `0x14004b713`
- `GDI32!SelectObject` at `0x14004b761`
- `GDI32!SelectObject` at `0x14004b7de`
- `GDI32!SelectObject` at `0x14004b620`
- `GDI32!SelectObject` at `0x14004b639`
- `GDI32!SelectObject` at `0x14004b686`
- `GDI32!SelectObject` at `0x14004b69b`
- `GDI32!SelectObject` at `0x14004b6fe`
- `GDI32!SelectObject` at `0x14004b713`
- `GDI32!SelectObject` at `0x14004b761`
- `GDI32!SelectObject` at `0x14004b7de`
- `GDI32!RealizePalette` at `0x14004b609`
- `GDI32!RealizePalette` at `0x14004b609`
- `GDI32!SelectPalette` at `0x14004b5e8`
- `GDI32!SelectPalette` at `0x14004b5fc`
- `GDI32!SelectPalette` at `0x14004b7f6`
- `GDI32!SelectPalette` at `0x14004b80e`
- `GDI32!SelectPalette` at `0x14004b5e8`
- `GDI32!SelectPalette` at `0x14004b5fc`
- `GDI32!SelectPalette` at `0x14004b7f6`
- `GDI32!SelectPalette` at `0x14004b80e`
- `GDI32!DeleteObject` at `0x14004b92a`
- `GDI32!DeleteObject` at `0x14004b988`
- `GDI32!DeleteObject` at `0x14004b99a`
- `GDI32!DeleteObject` at `0x14004b9ac`
- `GDI32!DeleteObject` at `0x14004b92a`
- `GDI32!DeleteObject` at `0x14004b988`
- `GDI32!DeleteObject` at `0x14004b99a`
- `GDI32!DeleteObject` at `0x14004b9ac`

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
  HDC hdcSrc; // r12
  HDC CompatibleDC; // rax
  HDC v25; // r13
  HBITMAP v26; // rdx
  HPALETTE PaletteForBitmap; // rax
  HGDIOBJ v28; // rbx
  int v29; // ebx
  int v30; // eax
  int v31; // r8d
  HBITMAP v32; // rbx
  __int64 LastError; // r15
  unsigned int v34; // eax
  PVOID *v35; // rax
  unsigned int v36; // eax
  void *v37; // rcx
  int v39; // [rsp+60h] [rbp-A0h]
  int xDest; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+70h] [rbp-90h]
  int wSrc; // [rsp+78h] [rbp-88h]
  HPALETTE hPala; // [rsp+80h] [rbp-80h]
  HBITMAP ho; // [rsp+88h] [rbp-78h]
  HBITMAP v46; // [rsp+90h] [rbp-70h]
  HBITMAP ImageFromResID; // [rsp+98h] [rbp-68h]
  HGDIOBJ v48; // [rsp+A0h] [rbp-60h]
  HGDIOBJ v49; // [rsp+A0h] [rbp-60h]
  HPALETTE v50; // [rsp+A8h] [rbp-58h]
  HBITMAP h; // [rsp+B0h] [rbp-50h]
  HGDIOBJ v52; // [rsp+B8h] [rbp-48h]
  struct tagRECT Rect; // [rsp+C8h] [rbp-38h] BYREF
  int pv; // [rsp+E0h] [rbp-20h] BYREF
  int v56; // [rsp+E4h] [rbp-1Ch] BYREF
  int cy; // [rsp+E8h] [rbp-18h]

  v3 = *((_DWORD *)this + 10);
  v4 = *((_DWORD *)this + 11);
  v6 = *((_DWORD *)this + 12);
  Rect = 0;
  v46 = 0;
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
    && (pv = 0, memset_0(&v56, 0, 0x64u), GetObjectW(ho, 104, &pv)) )
  {
    v9 = cy;
    if ( cy < 0 )
      v9 = -cy;
    v10 = v56;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  xDest = v10;
  if ( v4
    && (ImageFromResID = LoadImageFromResID(*((HINSTANCE *)this + 2), (const unsigned __int16 *)(unsigned __int16)v4)) != 0
    && (pv = 0, memset_0(&v56, 0, 0x64u), GetObjectW(ImageFromResID, 104, &pv)) )
  {
    hDest = cy;
    if ( cy < 0 )
      hDest = -cy;
    v12 = v56;
  }
  else
  {
    hDest = 0;
    v12 = 0;
  }
  wSrc = v12;
  if ( v6
    && (v46 = LoadImageFromResID(*((HINSTANCE *)this + 2), (const unsigned __int16 *)(unsigned __int16)v6)) != 0
    && (pv = 0, memset_0(&v56, 0, 0x64u), GetObjectW(v46, 104, &pv)) )
  {
    v13 = cy;
    if ( cy < 0 )
      v13 = -cy;
    v14 = v56;
  }
  else
  {
    v13 = 0;
    v14 = 0;
  }
  v41 = v14;
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
  v39 = v18;
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
    hdcSrc = CreateCompatibleDC(v22);
    CompatibleDC = CreateCompatibleDC(v22);
    v25 = CompatibleDC;
    if ( hdcSrc && CompatibleDC )
    {
      v26 = ho;
      if ( !ho )
        v26 = v46;
      PaletteForBitmap = CClientUtilsWin32::UT_GetPaletteForBitmap(v22, v26);
      *((_QWORD *)this + 3) = PaletteForBitmap;
      if ( PaletteForBitmap )
      {
        hPala = SelectPalette(v22, PaletteForBitmap, 0);
        v50 = SelectPalette(v25, *((HPALETTE *)this + 3), 0);
        RealizePalette(v22);
      }
      else
      {
        hPala = 0;
        v50 = 0;
      }
      v52 = SelectObject(v25, h);
      if ( ho )
      {
        v48 = SelectObject(hdcSrc, ho);
        BitBlt(v25, 0, 0, v39, v9, hdcSrc, 0, 0, 0xCC0020u);
        if ( v48 )
          SelectObject(hdcSrc, v48);
      }
      if ( ImageFromResID )
      {
        v49 = SelectObject(hdcSrc, ImageFromResID);
        StretchBlt(v25, xDest, 0, v39 - v41 - xDest, hDest, hdcSrc, 0, 0, wSrc, hDest, 0xCC0020u);
        if ( v49 )
          SelectObject(hdcSrc, v49);
      }
      if ( v46 )
      {
        v28 = SelectObject(hdcSrc, v46);
        BitBlt(v25, v39 - v41, 0, v39, v9, hdcSrc, 0, 0, 0xCC0020u);
        if ( v28 )
          SelectObject(hdcSrc, v28);
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
      if ( v52 )
        SelectObject(v25, v52);
      if ( hPala )
        SelectPalette(v22, hPala, 1);
      if ( v50 )
        SelectPalette(v22, v50, 1);
      DeleteDC(hdcSrc);
      DeleteDC(v25);
    }
    ReleaseDC(*((HWND *)this + 1), v22);
    v18 = v39;
    v32 = h;
  }
  else
  {
    v32 = 0;
    LastError = (unsigned __int8)GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
        v34,
        (__int64)"GetWindowDC failed",
        LastError);
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
  if ( v46 )
    DeleteObject(v46);
  return v7;
}

```

## disassembly

```asm
0x14004b29c  mov     [rsp-8+arg_10], rbx
0x14004b2a1  push    rbp
0x14004b2a2  push    rsi
0x14004b2a3  push    rdi
0x14004b2a4  push    r12
0x14004b2a6  push    r13
0x14004b2a8  push    r14
0x14004b2aa  push    r15
0x14004b2ac  lea     rbp, [rsp-60h]
0x14004b2b1  sub     rsp, 160h
0x14004b2b8  mov     rax, cs:__security_cookie
0x14004b2bf  xor     rax, rsp
0x14004b2c2  mov     [rbp+90h+var_40], rax
0x14004b2c6  mov     ebx, [rcx+28h]
0x14004b2c9  xorps   xmm0, xmm0
0x14004b2cc  mov     r12d, [rcx+2Ch]
0x14004b2d0  mov     rdi, rcx
0x14004b2d3  mov     r13d, [rcx+30h]
0x14004b2d7  movups  xmmword ptr [rbp+90h+Rect.left], xmm0
0x14004b2db  mov     dword ptr [rbp+90h+hPal], r8d
0x14004b2df  mov     [rbp+90h+var_D0], rdx
0x14004b2e3  mov     qword ptr [rsp+190h+var_130], 0
0x14004b2ec  mov     qword ptr [rsp+190h+wSrc], 0
0x14004b2f5  mov     [rsp+190h+var_120], 0
0x14004b2fe  mov     [rbp+90h+var_100], 0
0x14004b306  mov     [rbp+90h+ho], 0
0x14004b30e  mov     [rbp+90h+var_F8], 0
0x14004b316  mov     rax, cs:WPP_GLOBAL_Control
0x14004b31d  lea     rcx, WPP_GLOBAL_Control
0x14004b324  mov     r14d, 1
0x14004b32a  cmp     rax, rcx
0x14004b32d  jz      short loc_14004B36C
0x14004b32f  test    [rax+1Ch], r14b
0x14004b333  jz      short loc_14004B36C
0x14004b335  cmp     byte ptr [rax+19h], 4
0x14004b339  jb      short loc_14004B36C
0x14004b33b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004b340  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b347  lea     edx, [r14+9]
0x14004b34b  mov     [rsp+190h+x1], r13d
0x14004b350  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004b357  mov     dword ptr [rsp+190h+hdcSrc], r12d
0x14004b35c  mov     r9d, eax
0x14004b35f  mov     [rsp+190h+hDest], ebx
0x14004b363  mov     rcx, [rcx+10h]
0x14004b367  call    WPP_SF_DDdd
0x14004b36c  test    ebx, ebx
0x14004b36e  jz      short loc_14004B3C3
0x14004b370  mov     rcx, [rdi+10h]; HINSTANCE
0x14004b374  movzx   edx, bx; unsigned __int16 *
0x14004b377  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004b37c  mov     [rbp+90h+ho], rax
0x14004b380  mov     r15, rax
0x14004b383  test    rax, rax
0x14004b386  jz      short loc_14004B3C3
0x14004b388  xor     edx, edx; Val
0x14004b38a  mov     [rbp+90h+pv], 0
0x14004b391  lea     rcx, [rbp+90h+var_AC]; void *
0x14004b395  lea     r8d, [rdx+64h]; Size
0x14004b399  call    memset_0
0x14004b39e  lea     r8, [rbp+90h+pv]; pv
0x14004b3a2  mov     edx, 68h ; 'h'; c
0x14004b3a7  mov     rcx, r15; h
0x14004b3aa  call    cs:__imp_GetObjectW
0x14004b3b0  test    eax, eax
0x14004b3b2  jz      short loc_14004B3C3
0x14004b3b4  mov     esi, [rbp+90h+cy]
0x14004b3b7  test    esi, esi
0x14004b3b9  jns     short loc_14004B3BD
0x14004b3bb  neg     esi
0x14004b3bd  mov     r15d, [rbp+90h+var_AC]
0x14004b3c1  jmp     short loc_14004B3CC
0x14004b3c3  mov     esi, [rsp+190h+wSrc+4]
0x14004b3c7  mov     r15d, [rsp+190h+wSrc]
0x14004b3cc  mov     [rsp+190h+xDest], r15d
0x14004b3d1  test    r12d, r12d
0x14004b3d4  jz      short loc_14004B42A
0x14004b3d6  mov     rcx, [rdi+10h]; HINSTANCE
0x14004b3da  movzx   edx, r12w; unsigned __int16 *
0x14004b3de  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004b3e3  mov     [rbp+90h+var_F8], rax
0x14004b3e7  mov     rbx, rax
0x14004b3ea  test    rax, rax
0x14004b3ed  jz      short loc_14004B42A
0x14004b3ef  xor     edx, edx; Val
0x14004b3f1  mov     [rbp+90h+pv], 0
0x14004b3f8  lea     rcx, [rbp+90h+var_AC]; void *
0x14004b3fc  lea     r8d, [rdx+64h]; Size
0x14004b400  call    memset_0
0x14004b405  lea     r8, [rbp+90h+pv]; pv
0x14004b409  mov     edx, 68h ; 'h'; c
0x14004b40e  mov     rcx, rbx; h
0x14004b411  call    cs:__imp_GetObjectW
0x14004b417  test    eax, eax
0x14004b419  jz      short loc_14004B42A
0x14004b41b  mov     ebx, [rbp+90h+cy]
0x14004b41e  test    ebx, ebx
0x14004b420  jns     short loc_14004B424
0x14004b422  neg     ebx
0x14004b424  mov     r12d, [rbp+90h+var_AC]
0x14004b428  jmp     short loc_14004B433
0x14004b42a  mov     ebx, dword ptr [rsp+190h+var_120+4]
0x14004b42e  mov     r12d, dword ptr [rsp+190h+var_120]
0x14004b433  mov     [rsp+190h+wSrc], r12d
0x14004b438  test    r13d, r13d
0x14004b43b  jz      short loc_14004B490
0x14004b43d  mov     rcx, [rdi+10h]; HINSTANCE
0x14004b441  movzx   edx, r13w; unsigned __int16 *
0x14004b445  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x14004b44a  mov     [rbp+90h+var_100], rax
0x14004b44e  mov     r13, rax
0x14004b451  test    rax, rax
0x14004b454  jz      short loc_14004B490
0x14004b456  xor     edx, edx; Val
0x14004b458  mov     [rbp+90h+pv], 0
0x14004b45f  lea     rcx, [rbp+90h+var_AC]; void *
0x14004b463  lea     r8d, [rdx+64h]; Size
0x14004b467  call    memset_0
0x14004b46c  lea     r8, [rbp+90h+pv]; pv
0x14004b470  mov     edx, 68h ; 'h'; c
0x14004b475  mov     rcx, r13; h
0x14004b478  call    cs:__imp_GetObjectW
0x14004b47e  test    eax, eax
0x14004b480  jz      short loc_14004B490
0x14004b482  mov     ecx, [rbp+90h+cy]
0x14004b485  test    ecx, ecx
0x14004b487  jns     short loc_14004B48B
0x14004b489  neg     ecx
0x14004b48b  mov     edx, [rbp+90h+var_AC]
0x14004b48e  jmp     short loc_14004B498
0x14004b490  mov     ecx, [rsp+190h+var_130+4]
0x14004b494  mov     edx, [rsp+190h+var_130]
0x14004b498  cmp     ebx, ecx
0x14004b49a  mov     dword ptr [rsp+190h+var_120], edx
0x14004b49e  mov     eax, ecx
0x14004b4a0  cmovg   eax, ebx
0x14004b4a3  cmp     esi, eax
0x14004b4a5  jg      short loc_14004B4AE
0x14004b4a7  cmp     ebx, ecx
0x14004b4a9  mov     esi, ecx
0x14004b4ab  cmovg   esi, ebx
0x14004b4ae  lea     eax, [rdx+r12]
0x14004b4b2  add     r15d, eax
0x14004b4b5  mov     [rdi+40h], r15d
0x14004b4b9  mov     rax, cs:WPP_GLOBAL_Control
0x14004b4c0  lea     r13, WPP_GLOBAL_Control
0x14004b4c7  cmp     rax, r13
0x14004b4ca  jz      short loc_14004B501
0x14004b4cc  test    [rax+1Ch], r14b
0x14004b4d0  jz      short loc_14004B501
0x14004b4d2  cmp     byte ptr [rax+19h], 4
0x14004b4d6  jb      short loc_14004B501
0x14004b4d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004b4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b4e4  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004b4eb  mov     edx, 0Bh
0x14004b4f0  mov     [rsp+190h+hDest], r15d
0x14004b4f5  mov     r9d, eax
0x14004b4f8  mov     rcx, [rcx+10h]
0x14004b4fc  call    WPP_SF_Dd
0x14004b501  mov     rcx, [rdi+8]; hWnd
0x14004b505  lea     rdx, [rbp+90h+Rect]; lpRect
0x14004b509  call    cs:__imp_GetClientRect
0x14004b50f  mov     r12d, [rbp+90h+Rect.right]
0x14004b513  sub     r12d, [rbp+90h+Rect.left]
0x14004b517  add     r12d, r14d
0x14004b51a  mov     [rsp+190h+var_130], r12d
0x14004b51f  jnz     short loc_14004B554
0x14004b521  mov     rax, cs:WPP_GLOBAL_Control
0x14004b528  cmp     rax, r13
0x14004b52b  jz      loc_14004B979
0x14004b531  test    [rax+1Ch], r14b
0x14004b535  jz      loc_14004B979
0x14004b53b  cmp     byte ptr [rax+19h], 2
0x14004b53f  jb      loc_14004B979
0x14004b545  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004b54a  mov     edx, 0Ch
0x14004b54f  jmp     loc_14004B95F
0x14004b554  cmp     dword ptr [rbp+90h+hPal], 0
0x14004b558  jnz     loc_14004B97C
0x14004b55e  mov     r13d, 2
0x14004b564  test    esi, esi
0x14004b566  jle     loc_14004B936
0x14004b56c  mov     rcx, [rdi+8]; hWnd
0x14004b570  call    cs:__imp_GetWindowDC
0x14004b576  mov     r15, rax
0x14004b579  test    rax, rax
0x14004b57c  jz      loc_14004B844
0x14004b582  mov     r8d, esi; cy
0x14004b585  mov     edx, r12d; cx
0x14004b588  mov     rcx, rax; hdc
0x14004b58b  call    cs:__imp_CreateCompatibleBitmap
0x14004b591  mov     rcx, r15; hdc
0x14004b594  mov     [rbp+90h+h], rax
0x14004b598  call    cs:__imp_CreateCompatibleDC
0x14004b59e  mov     rcx, r15; hdc
0x14004b5a1  mov     r12, rax
0x14004b5a4  call    cs:__imp_CreateCompatibleDC
0x14004b5aa  mov     r13, rax
0x14004b5ad  test    r12, r12
0x14004b5b0  jz      loc_14004B826
0x14004b5b6  test    rax, rax
0x14004b5b9  jz      loc_14004B826
0x14004b5bf  mov     rax, [rbp+90h+ho]
0x14004b5c3  mov     rcx, r15; HDC
0x14004b5c6  test    rax, rax
0x14004b5c9  mov     rdx, rax
0x14004b5cc  cmovz   rdx, [rbp+90h+var_100]; HBITMAP
0x14004b5d1  call    ?UT_GetPaletteForBitmap@CClientUtilsWin32@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAUHBITMAP__@@@Z; CClientUtilsWin32::UT_GetPaletteForBitmap(HDC__ *,HBITMAP__ *)
0x14004b5d6  mov     [rdi+18h], rax
0x14004b5da  test    rax, rax
0x14004b5dd  jz      short loc_14004B611
0x14004b5df  xor     r8d, r8d; bForceBkgd
0x14004b5e2  mov     rdx, rax; hPal
0x14004b5e5  mov     rcx, r15; hdc
0x14004b5e8  call    cs:__imp_SelectPalette
0x14004b5ee  mov     rdx, [rdi+18h]; hPal
0x14004b5f2  xor     r8d, r8d; bForceBkgd
0x14004b5f5  mov     rcx, r13; hdc
0x14004b5f8  mov     [rbp+90h+hPal], rax
0x14004b5fc  call    cs:__imp_SelectPalette
0x14004b602  mov     rcx, r15; hdc
0x14004b605  mov     [rbp+90h+var_E8], rax
0x14004b609  call    cs:__imp_RealizePalette
0x14004b60f  jmp     short loc_14004B619
0x14004b611  mov     [rbp+90h+hPal], rax
0x14004b615  mov     [rbp+90h+var_E8], rax
0x14004b619  mov     rdx, [rbp+90h+h]; h
0x14004b61d  mov     rcx, r13; hdc
0x14004b620  call    cs:__imp_SelectObject
0x14004b626  mov     [rbp+90h+var_D8], rax
0x14004b62a  mov     rax, [rbp+90h+ho]
0x14004b62e  test    rax, rax
0x14004b631  jz      short loc_14004B68C
0x14004b633  mov     rdx, rax; h
0x14004b636  mov     rcx, r12; hdc
0x14004b639  call    cs:__imp_SelectObject
0x14004b63f  mov     r9d, [rsp+190h+var_130]; cx
0x14004b644  xor     r8d, r8d; y
0x14004b647  mov     [rsp+190h+rop], 0CC0020h; rop
0x14004b64f  xor     edx, edx; x
0x14004b651  mov     [rsp+190h+y1], 0; y1
0x14004b659  mov     rcx, r13; hdc
0x14004b65c  mov     [rsp+190h+x1], 0; x1
0x14004b664  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004b669  mov     [rsp+190h+hDest], esi; cy
0x14004b66d  mov     [rbp+90h+var_F0], rax
0x14004b671  call    cs:__imp_BitBlt
0x14004b677  mov     rax, [rbp+90h+var_F0]
0x14004b67b  test    rax, rax
0x14004b67e  jz      short loc_14004B68C
0x14004b680  mov     rdx, rax; h
0x14004b683  mov     rcx, r12; hdc
0x14004b686  call    cs:__imp_SelectObject
0x14004b68c  mov     rax, [rbp+90h+var_F8]
0x14004b690  test    rax, rax
0x14004b693  jz      short loc_14004B704
0x14004b695  mov     rdx, rax; h
0x14004b698  mov     rcx, r12; hdc
0x14004b69b  call    cs:__imp_SelectObject
0x14004b6a1  mov     r9d, [rsp+190h+var_130]
0x14004b6a6  xor     r8d, r8d; yDest
0x14004b6a9  sub     r9d, dword ptr [rsp+190h+var_120]
0x14004b6ae  mov     rcx, r13; hdcDest
0x14004b6b1  mov     edx, [rsp+190h+xDest]; xDest
0x14004b6b5  sub     r9d, edx; wDest
0x14004b6b8  mov     [rsp+190h+var_140], 0CC0020h; rop
0x14004b6c0  mov     [rsp+190h+hSrc], ebx; hSrc
0x14004b6c4  mov     [rbp+90h+var_F0], rax
0x14004b6c8  mov     eax, [rsp+190h+wSrc]
0x14004b6cc  mov     [rsp+190h+rop], eax; wSrc
0x14004b6d0  mov     [rsp+190h+y1], 0; ySrc
0x14004b6d8  mov     [rsp+190h+x1], 0; xSrc
0x14004b6e0  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004b6e5  mov     [rsp+190h+hDest], ebx; hDest
0x14004b6e9  call    cs:__imp_StretchBlt
0x14004b6ef  mov     rax, [rbp+90h+var_F0]
0x14004b6f3  test    rax, rax
0x14004b6f6  jz      short loc_14004B704
0x14004b6f8  mov     rdx, rax; h
0x14004b6fb  mov     rcx, r12; hdc
0x14004b6fe  call    cs:__imp_SelectObject
0x14004b704  mov     rax, [rbp+90h+var_100]
0x14004b708  test    rax, rax
0x14004b70b  jz      short loc_14004B767
0x14004b70d  mov     rdx, rax; h
0x14004b710  mov     rcx, r12; hdc
0x14004b713  call    cs:__imp_SelectObject
0x14004b719  mov     edx, [rsp+190h+var_130]
0x14004b71d  xor     r8d, r8d; y
0x14004b720  sub     edx, dword ptr [rsp+190h+var_120]; x
0x14004b724  mov     rcx, r13; hdc
0x14004b727  mov     r9d, [rsp+190h+var_130]; cx
0x14004b72c  mov     rbx, rax
0x14004b72f  mov     [rsp+190h+rop], 0CC0020h; rop
0x14004b737  mov     [rsp+190h+y1], 0; y1
0x14004b73f  mov     [rsp+190h+x1], 0; x1
0x14004b747  mov     [rsp+190h+hdcSrc], r12; hdcSrc
0x14004b74c  mov     [rsp+190h+hDest], esi; cy
0x14004b750  call    cs:__imp_BitBlt
  ... truncated ...
```
