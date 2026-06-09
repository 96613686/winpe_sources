# CreateCheckBoxImagelistEx

- ea: `0x180028af0`
- end: `0x180029007`
- name: `CreateCheckBoxImagelistEx`
- size: `1303`
- prototype: `__int64 __usercall@<rax>(HIMAGELIST himl@<rcx>, LPCWSTR pszClassList@<rdx>, int iPartId@<r8d>, __int64)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180028778`
- `0x18011e740`
- `0x180135c24`
- `0x180137758`

## callees

- `0x180007fc4`
- `0x180012230`
- `0x180019b30`
- `0x180027a2c`
- `0x180028af0`
- `0x18007b370`
- `0x1800b68d0`
- `0x1800b9e30`
- `0x1800bfd50`
- `0x1800bfe10`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x180028fc9`
- `GDI32!DeleteObject` at `0x180028fc9`
- `GDI32!SelectObject` at `0x180028c80`
- `GDI32!SelectObject` at `0x180028f4f`
- `GDI32!SelectObject` at `0x180028c80`
- `GDI32!SelectObject` at `0x180028f4f`
- `GDI32!DeleteDC` at `0x180028fc0`
- `GDI32!DeleteDC` at `0x180028fc0`
- `GDI32!CreateCompatibleDC` at `0x180028b55`
- `GDI32!CreateCompatibleDC` at `0x180028b55`
- `USER32!OffsetRect` at `0x180028d3d`
- `USER32!OffsetRect` at `0x180028da4`
- `USER32!OffsetRect` at `0x180028e11`
- `USER32!OffsetRect` at `0x180028e7e`
- `USER32!OffsetRect` at `0x180028eeb`
- `USER32!OffsetRect` at `0x180028d3d`
- `USER32!OffsetRect` at `0x180028da4`
- `USER32!OffsetRect` at `0x180028e11`
- `USER32!OffsetRect` at `0x180028e7e`
- `USER32!OffsetRect` at `0x180028eeb`
- `USER32!DestroyIcon` at `0x180028fac`
- `USER32!DestroyIcon` at `0x180028fac`
- `USER32!InflateRect` at `0x180028d12`
- `USER32!InflateRect` at `0x180028d12`
- `USER32!GetSystemMetrics` at `0x180028cf2`
- `USER32!GetSystemMetrics` at `0x180028d01`
- `USER32!GetSystemMetrics` at `0x180028cf2`
- `USER32!GetSystemMetrics` at `0x180028d01`
- `USER32!GetSysColor` at `0x180028cb7`
- `USER32!GetSysColor` at `0x180028cb7`
- `USER32!DrawFrameControl` at `0x180028d94`
- `USER32!DrawFrameControl` at `0x180028dfb`
- `USER32!DrawFrameControl` at `0x180028e68`
- `USER32!DrawFrameControl` at `0x180028ed5`
- `USER32!DrawFrameControl` at `0x180028f42`
- `USER32!DrawFrameControl` at `0x180028d94`
- `USER32!DrawFrameControl` at `0x180028dfb`
- `USER32!DrawFrameControl` at `0x180028e68`
- `USER32!DrawFrameControl` at `0x180028ed5`
- `USER32!DrawFrameControl` at `0x180028f42`
- `USER32!GetSystemMetricsForDpi` at `0x180028be6`
- `USER32!GetSystemMetricsForDpi` at `0x180028bf7`
- `USER32!GetSystemMetricsForDpi` at `0x180028be6`
- `USER32!GetSystemMetricsForDpi` at `0x180028bf7`
- `UxTheme!GetThemePartSize` at `0x180028ba6`
- `UxTheme!GetThemePartSize` at `0x180028ba6`
- `UxTheme!CloseThemeData` at `0x180028fd7`
- `UxTheme!CloseThemeData` at `0x180028fd7`
- `UxTheme!OpenThemeDataForDpi` at `0x180028b6f`
- `UxTheme!OpenThemeDataForDpi` at `0x180028b6f`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028d69`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028dd0`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028e3d`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028eaa`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028f17`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028d69`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028dd0`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028e3d`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028eaa`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x180028f17`

## pseudocode

```c
HDC __fastcall CreateCheckBoxImagelistEx(HIMAGELIST himl, LPCWSTR pszClassList, int iPartId, char a4, UINT *a5)
{
  HDC result; // rax
  HDC v10; // rsi
  HTHEME v11; // rdi
  int v12; // r10d
  int SystemMetricsForDpi; // eax
  __int64 v14; // rdx
  int v15; // eax
  LONG v16; // ecx
  LONG v17; // r14d
  struct _IMAGELIST *v18; // r13
  HBITMAP v19; // rbx
  HGDIOBJ v20; // rax
  int v21; // edx
  LONG v22; // ecx
  int v23; // r14d
  DWORD SysColor; // eax
  COLORREF v25; // r15d
  int v26; // ebx
  int SystemMetrics; // eax
  LONG v28; // r14d
  int v29; // ebx
  int v30; // [rsp+40h] [rbp-51h]
  int v31; // [rsp+44h] [rbp-4Dh]
  int v32; // [rsp+48h] [rbp-49h]
  int v33; // [rsp+4Ch] [rbp-45h]
  HBITMAP hbmImage; // [rsp+58h] [rbp-39h]
  HGDIOBJ h; // [rsp+60h] [rbp-31h]
  int cx; // [rsp+68h] [rbp-29h] BYREF
  int cy; // [rsp+6Ch] [rbp-25h] BYREF
  struct tagRECT rc; // [rsp+70h] [rbp-21h] BYREF
  SIZE psz; // [rsp+80h] [rbp-11h] BYREF
  DTBGOPTS pOptions; // [rsp+88h] [rbp-9h] BYREF

  pOptions.dwSize = 24;
  cx = 0;
  cy = 0;
  rc = 0;
  pOptions.rcClip = 0;
  pOptions.dwFlags = 2;
  result = CreateCompatibleDC(0);
  v10 = result;
  if ( result )
  {
    v11 = OpenThemeDataForDpi(0, pszClassList, *a5);
    if ( !v11 || (psz = 0, GetThemePartSize(v11, v10, iPartId, 1, 0, TS_DRAW, &psz)) )
    {
      if ( himl && ImageList_GetIconSize(himl, &cx, &cy) )
      {
        v12 = cy;
      }
      else
      {
        SystemMetricsForDpi = GetSystemMetricsForDpi(49, *a5);
        v14 = a5[1];
        cx = SystemMetricsForDpi;
        v12 = GetSystemMetricsForDpi(50, v14);
        cy = v12;
      }
    }
    else
    {
      v12 = psz.cy;
      cx = psz.cx;
      cy = psz.cy;
    }
    v31 = a4 & 4;
    v33 = a4 & 8;
    v15 = (v31 != 0) + 3;
    if ( (a4 & 8) == 0 )
      v15 = (v31 != 0) + 2;
    v32 = a4 & 0x10;
    v16 = v15 + 1;
    if ( (a4 & 0x10) == 0 )
      v16 = v15;
    v30 = a4 & 0x20;
    v17 = v16 + 1;
    if ( (a4 & 0x20) == 0 )
      v17 = v16;
    psz.cx = v17;
    v18 = ImageList_Create(cx, v12, 0x21u, 0, v17);
    hbmImage = (HBITMAP)CreateColorBitmap(cx * v17, cy);
    v19 = hbmImage;
    v20 = SelectObject(v10, hbmImage);
    v21 = cx;
    rc.bottom = cy;
    v22 = cx * v17;
    v23 = a4 & 2;
    h = v20;
    *(_QWORD *)&rc.left = 0;
    rc.right = v22;
    if ( v11 )
    {
      v25 = -16777216;
      rc.right = cx;
    }
    else
    {
      SysColor = GetSysColor(5);
      if ( (a4 & 2) != 0 )
      {
        v25 = 16711680;
        if ( SysColor != 16711935 )
          v25 = 16711935;
      }
      else
      {
        v25 = SysColor;
      }
      FillRectClr(v10, &rc, v25);
      rc.right = cx;
      v26 = -GetSystemMetrics(46);
      SystemMetrics = GetSystemMetrics(45);
      InflateRect(&rc, -SystemMetrics, v26);
      ++rc.right;
      ++rc.bottom;
      v21 = cx;
      v19 = hbmImage;
    }
    if ( v30 )
      OffsetRect(&rc, v21, 0);
    if ( v11 )
      DrawThemeBackgroundEx(v11, v10, iPartId, 1, &rc, &pOptions);
    else
      DrawFrameControl(v10, &rc, 4u, v23 != 0 ? 0x4000 : 18432);
    OffsetRect(&rc, cx, 0);
    if ( v11 )
      DrawThemeBackgroundEx(v11, v10, iPartId, 5, &rc, &pOptions);
    else
      DrawFrameControl(v10, &rc, 4u, v23 != 0 ? 17408 : 19456);
    if ( v31 )
    {
      OffsetRect(&rc, cx, 0);
      if ( v11 )
        DrawThemeBackgroundEx(v11, v10, iPartId, 9, &rc, &pOptions);
      else
        DrawFrameControl(v10, &rc, 4u, v23 != 0 ? 17416 : 19464);
    }
    if ( v32 )
    {
      OffsetRect(&rc, cx, 0);
      if ( v11 )
        DrawThemeBackgroundEx(v11, v10, iPartId, 13, &rc, &pOptions);
      else
        DrawFrameControl(v10, &rc, 4u, v23 != 0 ? 17664 : 19712);
    }
    if ( v33 )
    {
      OffsetRect(&rc, cx, 0);
      if ( v11 )
        DrawThemeBackgroundEx(v11, v10, iPartId, 17, &rc, &pOptions);
      else
        DrawFrameControl(v10, &rc, 4u, v23 != 0 ? 0x4000 : 18432);
    }
    SelectObject(v10, h);
    if ( v23 )
      ImageList_AddMasked(v18, v19, v25);
    else
      ImageList_Add(v18, v19, 0);
    if ( (a4 & 1) != 0 )
    {
      v28 = psz.cx;
      v29 = 0;
      do
      {
        psz = (SIZE)ImageList_GetIcon(v18, v29, 0);
        MirrorIcon((HICON *)&psz, 0);
        ImageList_ReplaceIcon(v18, v29, *(HICON *)&psz);
        DestroyIcon(*(HICON *)&psz);
        ++v29;
      }
      while ( v29 < v28 );
      v19 = hbmImage;
    }
    DeleteDC(v10);
    DeleteObject(v19);
    if ( v11 )
      CloseThemeData(v11);
    return (HDC)v18;
  }
  return result;
}

```

## disassembly

```asm
0x180028af0  mov     [rsp-8+arg_18], rbx
0x180028af5  push    rbp
0x180028af6  push    rsi
0x180028af7  push    rdi
0x180028af8  push    r12
0x180028afa  push    r13
0x180028afc  push    r14
0x180028afe  push    r15
0x180028b00  lea     rbp, [rsp-1Fh]
0x180028b05  sub     rsp, 0B0h
0x180028b0c  mov     rax, cs:__security_cookie
0x180028b13  xor     rax, rsp
0x180028b16  mov     [rbp+4Fh+var_40], rax
0x180028b1a  mov     rbx, [rbp+4Fh+arg_20]
0x180028b1e  xorps   xmm0, xmm0
0x180028b21  mov     r14, rcx
0x180028b24  mov     [rbp+4Fh+var_90], r9d
0x180028b28  xor     r13d, r13d
0x180028b2b  mov     [rbp+4Fh+pOptions.dwSize], 18h
0x180028b32  xor     ecx, ecx; hdc
0x180028b34  mov     [rbp+4Fh+var_78], r13d
0x180028b38  mov     [rbp+4Fh+cy], r13d
0x180028b3c  mov     r15d, r9d
0x180028b3f  movups  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x180028b43  mov     r12d, r8d
0x180028b46  mov     rdi, rdx
0x180028b49  movdqu  xmmword ptr [rbp+4Fh+pOptions.rcClip.left], xmm0
0x180028b4e  mov     [rbp+4Fh+pOptions.dwFlags], 2
0x180028b55  call    cs:__imp_CreateCompatibleDC
0x180028b5b  mov     rsi, rax
0x180028b5e  test    rax, rax
0x180028b61  jz      loc_180028FE0
0x180028b67  mov     r8d, [rbx]; dpi
0x180028b6a  mov     rdx, rdi; pszClassList
0x180028b6d  xor     ecx, ecx; hwnd
0x180028b6f  call    cs:__imp_OpenThemeDataForDpi
0x180028b75  mov     rdi, rax
0x180028b78  test    rax, rax
0x180028b7b  jz      short loc_180028BC0
0x180028b7d  lea     rax, [rbp+4Fh+var_60]
0x180028b81  mov     qword ptr [rbp+4Fh+var_60.cx], r13
0x180028b85  mov     [rsp+0E0h+psz], rax; psz
0x180028b8a  mov     r9d, 1; iStateId
0x180028b90  mov     [rsp+0E0h+eSize], 2; eSize
0x180028b98  mov     r8d, r12d; iPartId
0x180028b9b  mov     rdx, rsi; hdc
0x180028b9e  mov     [rsp+0E0h+prc], r13; prc
0x180028ba3  mov     rcx, rdi; hTheme
0x180028ba6  call    cs:__imp_GetThemePartSize
0x180028bac  test    eax, eax
0x180028bae  jnz     short loc_180028BC0
0x180028bb0  mov     eax, [rbp+4Fh+var_60.cx]
0x180028bb3  mov     r10d, [rbp+4Fh+var_60.cy]
0x180028bb7  mov     [rbp+4Fh+var_78], eax
0x180028bba  mov     [rbp+4Fh+cy], r10d
0x180028bbe  jmp     short loc_180028C03
0x180028bc0  test    r14, r14
0x180028bc3  jz      short loc_180028BDF
0x180028bc5  lea     r8, [rbp+4Fh+cy]; cy
0x180028bc9  mov     rcx, r14; himl
0x180028bcc  lea     rdx, [rbp+4Fh+var_78]; cx
0x180028bd0  call    ImageList_GetIconSize
0x180028bd5  test    eax, eax
0x180028bd7  jz      short loc_180028BDF
0x180028bd9  mov     r10d, [rbp+4Fh+cy]
0x180028bdd  jmp     short loc_180028C03
0x180028bdf  mov     edx, [rbx]
0x180028be1  mov     ecx, 31h ; '1'
0x180028be6  call    cs:__imp_GetSystemMetricsForDpi
0x180028bec  mov     edx, [rbx+4]
0x180028bef  mov     ecx, 32h ; '2'
0x180028bf4  mov     [rbp+4Fh+var_78], eax
0x180028bf7  call    cs:__imp_GetSystemMetricsForDpi
0x180028bfd  mov     r10d, eax
0x180028c00  mov     [rbp+4Fh+cy], eax
0x180028c03  mov     eax, r15d
0x180028c06  and     eax, 4
0x180028c09  mov     ecx, eax
0x180028c0b  mov     [rbp+4Fh+var_9C], eax
0x180028c0e  neg     ecx
0x180028c10  mov     ecx, r15d
0x180028c13  sbb     edx, edx
0x180028c15  neg     edx
0x180028c17  add     edx, 2
0x180028c1a  and     ecx, 8
0x180028c1d  mov     [rbp+4Fh+var_94], ecx
0x180028c20  lea     eax, [rdx+1]
0x180028c23  cmovz   eax, edx
0x180028c26  mov     edx, r15d
0x180028c29  and     edx, 10h
0x180028c2c  mov     [rbp+4Fh+var_98], edx
0x180028c2f  mov     edx, r10d; cy
0x180028c32  lea     ecx, [rax+1]
0x180028c35  cmovz   ecx, eax
0x180028c38  mov     eax, r15d
0x180028c3b  and     eax, 20h
0x180028c3e  mov     [rbp+4Fh+var_A0], eax
0x180028c41  lea     r14d, [rcx+1]
0x180028c45  cmovz   r14d, ecx
0x180028c49  mov     ecx, [rbp+4Fh+var_78]; cx
0x180028c4c  xor     r9d, r9d; cInitial
0x180028c4f  mov     [rbp+4Fh+var_60.cx], r14d
0x180028c53  mov     dword ptr [rsp+0E0h+prc], r14d; cGrow
0x180028c58  lea     r8d, [r9+21h]; flags
0x180028c5c  call    ImageList_Create
0x180028c61  mov     edx, [rbp+4Fh+cy]; cy
0x180028c64  mov     ecx, r14d
0x180028c67  imul    ecx, [rbp+4Fh+var_78]; cx
0x180028c6b  mov     r13, rax
0x180028c6e  call    CreateColorBitmap
0x180028c73  mov     rdx, rax; h
0x180028c76  mov     [rbp+4Fh+hbmImage], rax
0x180028c7a  mov     rcx, rsi; hdc
0x180028c7d  mov     rbx, rax
0x180028c80  call    cs:__imp_SelectObject
0x180028c86  mov     ecx, [rbp+4Fh+cy]
0x180028c89  mov     edx, [rbp+4Fh+var_78]; dx
0x180028c8c  mov     [rbp+4Fh+rc.bottom], ecx
0x180028c8f  mov     ecx, r14d
0x180028c92  imul    ecx, edx
0x180028c95  mov     r14d, r15d
0x180028c98  and     r14d, 2
0x180028c9c  mov     [rbp+4Fh+h], rax
0x180028ca0  mov     qword ptr [rbp+4Fh+rc.left], 0
0x180028ca8  mov     eax, 5
0x180028cad  mov     [rbp+4Fh+rc.right], ecx
0x180028cb0  test    rdi, rdi
0x180028cb3  jnz     short loc_180028D27
0x180028cb5  mov     ecx, eax; nIndex
0x180028cb7  call    cs:__imp_GetSysColor
0x180028cbd  test    r14d, r14d
0x180028cc0  jz      short loc_180028CD5
0x180028cc2  mov     ecx, 0FF00FFh
0x180028cc7  mov     r15d, 0FF0000h
0x180028ccd  cmp     eax, ecx
0x180028ccf  cmovnz  r15d, ecx
0x180028cd3  jmp     short loc_180028CD8
0x180028cd5  mov     r15d, eax
0x180028cd8  mov     r8d, r15d; color
0x180028cdb  lea     rdx, [rbp+4Fh+rc]; lprect
0x180028cdf  mov     rcx, rsi; hdc
0x180028ce2  call    FillRectClr
0x180028ce7  mov     eax, [rbp+4Fh+var_78]
0x180028cea  mov     ecx, 2Eh ; '.'; nIndex
0x180028cef  mov     [rbp+4Fh+rc.right], eax
0x180028cf2  call    cs:__imp_GetSystemMetrics
0x180028cf8  mov     ebx, eax
0x180028cfa  mov     ecx, 2Dh ; '-'; nIndex
0x180028cff  neg     ebx
0x180028d01  call    cs:__imp_GetSystemMetrics
0x180028d07  mov     r8d, ebx; dy
0x180028d0a  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028d0e  neg     eax
0x180028d10  mov     edx, eax; dx
0x180028d12  call    cs:__imp_InflateRect
0x180028d18  inc     [rbp+4Fh+rc.right]
0x180028d1b  inc     [rbp+4Fh+rc.bottom]
0x180028d1e  mov     edx, [rbp+4Fh+var_78]
0x180028d21  mov     rbx, [rbp+4Fh+hbmImage]
0x180028d25  jmp     short loc_180028D30
0x180028d27  mov     r15d, 0FF000000h
0x180028d2d  mov     [rbp+4Fh+rc.right], edx
0x180028d30  cmp     [rbp+4Fh+var_A0], 0
0x180028d34  jz      short loc_180028D43
0x180028d36  xor     r8d, r8d; dy
0x180028d39  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028d3d  call    cs:__imp_OffsetRect
0x180028d43  test    rdi, rdi
0x180028d46  jz      short loc_180028D71
0x180028d48  lea     rax, [rbp+4Fh+pOptions]
0x180028d4c  mov     r9d, 1; iStateId
0x180028d52  mov     qword ptr [rsp+0E0h+eSize], rax; pOptions
0x180028d57  mov     r8d, r12d; iPartId
0x180028d5a  lea     rax, [rbp+4Fh+rc]
0x180028d5e  mov     rdx, rsi; hdc
0x180028d61  mov     rcx, rdi; hTheme
0x180028d64  mov     [rsp+0E0h+prc], rax; pRect
0x180028d69  call    cs:__imp_DrawThemeBackgroundEx
0x180028d6f  jmp     short loc_180028D9A
0x180028d71  mov     eax, r14d
0x180028d74  lea     rdx, [rbp+4Fh+rc]; LPRECT
0x180028d78  neg     eax
0x180028d7a  mov     r8d, 4; UINT
0x180028d80  mov     rcx, rsi; HDC
0x180028d83  sbb     r9d, r9d
0x180028d86  and     r9d, 0FFFFF800h
0x180028d8d  add     r9d, 4800h; UINT
0x180028d94  call    cs:__imp_DrawFrameControl
0x180028d9a  mov     edx, [rbp+4Fh+var_78]; dx
0x180028d9d  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028da1  xor     r8d, r8d; dy
0x180028da4  call    cs:__imp_OffsetRect
0x180028daa  test    rdi, rdi
0x180028dad  jz      short loc_180028DD8
0x180028daf  lea     rax, [rbp+4Fh+pOptions]
0x180028db3  mov     r9d, 5; iStateId
0x180028db9  mov     qword ptr [rsp+0E0h+eSize], rax; pOptions
0x180028dbe  mov     r8d, r12d; iPartId
0x180028dc1  lea     rax, [rbp+4Fh+rc]
0x180028dc5  mov     rdx, rsi; hdc
0x180028dc8  mov     rcx, rdi; hTheme
0x180028dcb  mov     [rsp+0E0h+prc], rax; pRect
0x180028dd0  call    cs:__imp_DrawThemeBackgroundEx
0x180028dd6  jmp     short loc_180028E01
0x180028dd8  mov     eax, r14d
0x180028ddb  lea     rdx, [rbp+4Fh+rc]; LPRECT
0x180028ddf  neg     eax
0x180028de1  mov     r8d, 4; UINT
0x180028de7  mov     rcx, rsi; HDC
0x180028dea  sbb     r9d, r9d
0x180028ded  and     r9d, 0FFFFF800h
0x180028df4  add     r9d, 4C00h; UINT
0x180028dfb  call    cs:__imp_DrawFrameControl
0x180028e01  cmp     [rbp+4Fh+var_9C], 0
0x180028e05  jz      short loc_180028E6E
0x180028e07  mov     edx, [rbp+4Fh+var_78]; dx
0x180028e0a  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028e0e  xor     r8d, r8d; dy
0x180028e11  call    cs:__imp_OffsetRect
0x180028e17  test    rdi, rdi
0x180028e1a  jz      short loc_180028E45
0x180028e1c  lea     rax, [rbp+4Fh+pOptions]
0x180028e20  mov     r9d, 9; iStateId
0x180028e26  mov     qword ptr [rsp+0E0h+eSize], rax; pOptions
0x180028e2b  mov     r8d, r12d; iPartId
0x180028e2e  lea     rax, [rbp+4Fh+rc]
0x180028e32  mov     rdx, rsi; hdc
0x180028e35  mov     rcx, rdi; hTheme
0x180028e38  mov     [rsp+0E0h+prc], rax; pRect
0x180028e3d  call    cs:__imp_DrawThemeBackgroundEx
0x180028e43  jmp     short loc_180028E6E
0x180028e45  mov     eax, r14d
0x180028e48  lea     rdx, [rbp+4Fh+rc]; LPRECT
0x180028e4c  neg     eax
0x180028e4e  mov     r8d, 4; UINT
0x180028e54  mov     rcx, rsi; HDC
0x180028e57  sbb     r9d, r9d
0x180028e5a  and     r9d, 0FFFFF800h
0x180028e61  add     r9d, 4C08h; UINT
0x180028e68  call    cs:__imp_DrawFrameControl
0x180028e6e  cmp     [rbp+4Fh+var_98], 0
0x180028e72  jz      short loc_180028EDB
0x180028e74  mov     edx, [rbp+4Fh+var_78]; dx
0x180028e77  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028e7b  xor     r8d, r8d; dy
0x180028e7e  call    cs:__imp_OffsetRect
0x180028e84  test    rdi, rdi
0x180028e87  jz      short loc_180028EB2
0x180028e89  lea     rax, [rbp+4Fh+pOptions]
0x180028e8d  mov     r9d, 0Dh; iStateId
0x180028e93  mov     qword ptr [rsp+0E0h+eSize], rax; pOptions
0x180028e98  mov     r8d, r12d; iPartId
0x180028e9b  lea     rax, [rbp+4Fh+rc]
0x180028e9f  mov     rdx, rsi; hdc
0x180028ea2  mov     rcx, rdi; hTheme
0x180028ea5  mov     [rsp+0E0h+prc], rax; pRect
0x180028eaa  call    cs:__imp_DrawThemeBackgroundEx
0x180028eb0  jmp     short loc_180028EDB
0x180028eb2  mov     eax, r14d
0x180028eb5  lea     rdx, [rbp+4Fh+rc]; LPRECT
0x180028eb9  neg     eax
0x180028ebb  mov     r8d, 4; UINT
0x180028ec1  mov     rcx, rsi; HDC
0x180028ec4  sbb     r9d, r9d
0x180028ec7  and     r9d, 0FFFFF800h
0x180028ece  add     r9d, 4D00h; UINT
0x180028ed5  call    cs:__imp_DrawFrameControl
0x180028edb  cmp     [rbp+4Fh+var_94], 0
0x180028edf  jz      short loc_180028F48
0x180028ee1  mov     edx, [rbp+4Fh+var_78]; dx
0x180028ee4  lea     rcx, [rbp+4Fh+rc]; lprc
0x180028ee8  xor     r8d, r8d; dy
0x180028eeb  call    cs:__imp_OffsetRect
0x180028ef1  test    rdi, rdi
0x180028ef4  jz      short loc_180028F1F
0x180028ef6  lea     rax, [rbp+4Fh+pOptions]
0x180028efa  mov     r9d, 11h; iStateId
0x180028f00  mov     qword ptr [rsp+0E0h+eSize], rax; pOptions
0x180028f05  mov     r8d, r12d; iPartId
0x180028f08  lea     rax, [rbp+4Fh+rc]
0x180028f0c  mov     rdx, rsi; hdc
0x180028f0f  mov     rcx, rdi; hTheme
0x180028f12  mov     [rsp+0E0h+prc], rax; pRect
0x180028f17  call    cs:__imp_DrawThemeBackgroundEx
0x180028f1d  jmp     short loc_180028F48
0x180028f1f  mov     eax, r14d
0x180028f22  lea     rdx, [rbp+4Fh+rc]; LPRECT
0x180028f26  neg     eax
0x180028f28  mov     r8d, 4; UINT
0x180028f2e  mov     rcx, rsi; HDC
0x180028f31  sbb     r9d, r9d
0x180028f34  and     r9d, 0FFFFF800h
0x180028f3b  add     r9d, 4800h; UINT
0x180028f42  call    cs:__imp_DrawFrameControl
0x180028f48  mov     rdx, [rbp+4Fh+h]; h
0x180028f4c  mov     rcx, rsi; hdc
0x180028f4f  call    cs:__imp_SelectObject
0x180028f55  mov     rdx, rbx; hbmImage
0x180028f58  mov     rcx, r13; himl
0x180028f5b  test    r14d, r14d
  ... truncated ...
```
