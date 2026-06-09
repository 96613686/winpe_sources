# OleMetafilePictFromIconAndLabel

- ea: `0x18009c290`
- end: `0x18009c8e8`
- name: `OleMetafilePictFromIconAndLabel`
- size: `1624`
- prototype: `HGLOBAL __stdcall(HICON hIcon, LPOLESTR lpszLabel, LPOLESTR lpszSourceFile, UINT iIconIndex)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009bdc0`
- `0x18009bf30`

## callees

- `0x1800077fc`
- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x18009afa8`
- `0x18009bb38`
- `0x18009c290`
- `0x18009c8f0`
- `0x18009c980`

## import_xrefs

- `KERNELBASE!AreFileApisANSI` at `0x18009c369`
- `KERNELBASE!AreFileApisANSI` at `0x18009c45d`
- `KERNELBASE!AreFileApisANSI` at `0x18009c369`
- `KERNELBASE!AreFileApisANSI` at `0x18009c45d`
- `KERNELBASE!GlobalAlloc` at `0x18009c3e1`
- `KERNELBASE!GlobalAlloc` at `0x18009c3e1`
- `KERNELBASE!GlobalFree` at `0x18009c817`
- `KERNELBASE!GlobalFree` at `0x18009c817`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c8a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c8a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c34d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c34d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c3a4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c49f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c3a4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c49f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009c871`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009c871`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009c82a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009c82a`
- `GDI32!DeleteMetaFile` at `0x18009c407`
- `GDI32!DeleteMetaFile` at `0x18009c407`
- `GDI32!DeleteObject` at `0x18009c88a`
- `GDI32!DeleteObject` at `0x18009c88a`
- `GDI32!SelectObject` at `0x18009c4f7`
- `GDI32!SelectObject` at `0x18009c52d`
- `GDI32!SelectObject` at `0x18009c4f7`
- `GDI32!SelectObject` at `0x18009c52d`
- `GDI32!CreateMetaFileA` at `0x18009c3bf`
- `GDI32!CreateMetaFileA` at `0x18009c3bf`
- `GDI32!CloseMetaFile` at `0x18009c3f8`
- `GDI32!CloseMetaFile` at `0x18009c800`
- `GDI32!CloseMetaFile` at `0x18009c3f8`
- `GDI32!CloseMetaFile` at `0x18009c800`
- `GDI32!CreateFontIndirectW` at `0x18009c4e0`
- `GDI32!CreateFontIndirectW` at `0x18009c4e0`
- `GDI32!GetTextMetricsA` at `0x18009c50f`
- `GDI32!GetTextMetricsA` at `0x18009c50f`
- `GDI32!SetMapMode` at `0x18009c586`
- `GDI32!SetMapMode` at `0x18009c586`
- `GDI32!SetWindowOrgEx` at `0x18009c59d`
- `GDI32!SetWindowOrgEx` at `0x18009c59d`
- `GDI32!SetWindowExtEx` at `0x18009c5c0`
- `GDI32!SetWindowExtEx` at `0x18009c5c0`
- `GDI32!Escape` at `0x18009c626`
- `GDI32!Escape` at `0x18009c6b4`
- `GDI32!Escape` at `0x18009c72e`
- `GDI32!Escape` at `0x18009c755`
- `GDI32!Escape` at `0x18009c781`
- `GDI32!Escape` at `0x18009c7a2`
- `GDI32!Escape` at `0x18009c7ce`
- `GDI32!Escape` at `0x18009c7f1`
- `GDI32!Escape` at `0x18009c626`
- `GDI32!Escape` at `0x18009c6b4`
- `GDI32!Escape` at `0x18009c72e`
- `GDI32!Escape` at `0x18009c755`
- `GDI32!Escape` at `0x18009c781`
- `GDI32!Escape` at `0x18009c7a2`
- `GDI32!Escape` at `0x18009c7ce`
- `GDI32!Escape` at `0x18009c7f1`
- `GDI32!SetTextColor` at `0x18009c648`
- `GDI32!SetTextColor` at `0x18009c648`
- `GDI32!SetBkMode` at `0x18009c65c`
- `GDI32!SetBkMode` at `0x18009c65c`
- `USER32!SetRectEmpty` at `0x18009c5d0`
- `USER32!SetRectEmpty` at `0x18009c5d0`
- `USER32!DrawIcon` at `0x18009c601`
- `USER32!DrawIcon` at `0x18009c601`
- `USER32!GetSysColor` at `0x18009c637`
- `USER32!GetSysColor` at `0x18009c637`
- `USER32!ReleaseDC` at `0x18009c8b5`
- `USER32!ReleaseDC` at `0x18009c8b5`
- `USER32!GetDC` at `0x18009c304`
- `USER32!GetDC` at `0x18009c304`
- `USER32!GetSystemMetrics` at `0x18009c53e`
- `USER32!GetSystemMetrics` at `0x18009c553`
- `USER32!GetSystemMetrics` at `0x18009c53e`
- `USER32!GetSystemMetrics` at `0x18009c553`
- `USER32!SystemParametersInfoW` at `0x18009c4d0`
- `USER32!SystemParametersInfoW` at `0x18009c4d0`

## pseudocode

```c
HGLOBAL __stdcall OleMetafilePictFromIconAndLabel(
        HICON hIcon,
        LPOLESTR lpszLabel,
        LPOLESTR lpszSourceFile,
        UINT iIconIndex)
{
  unsigned int v4; // r12d
  HGLOBAL v7; // rsi
  __int64 v8; // r14
  HDC v9; // rbx
  char *v10; // r15
  BOOL v11; // eax
  HDC MetaFileA; // rdi
  HMETAFILE v13; // rax
  BOOL v14; // eax
  HGDIOBJ v15; // rbx
  int v16; // ebx
  COLORREF SysColor; // eax
  int v18; // r8d
  char *v19; // r9
  int v20; // r8d
  HMETAFILE v21; // r12
  _DWORD *v22; // rdi
  int v23; // ebx
  int v24; // eax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+40h] [rbp-C0h]
  int bUsedDefaultChar; // [rsp+44h] [rbp-BCh] BYREF
  int SystemMetrics; // [rsp+48h] [rbp-B8h]
  int v30; // [rsp+4Ch] [rbp-B4h]
  int v31; // [rsp+50h] [rbp-B0h]
  unsigned __int64 cchRemain; // [rsp+58h] [rbp-A8h] BYREF
  HDC hdc; // [rsp+60h] [rbp-A0h]
  UINT v34; // [rsp+68h] [rbp-98h]
  LPCSTR pvIn; // [rsp+70h] [rbp-90h]
  HFONT__ *hFont; // [rsp+78h] [rbp-88h]
  HICON v37; // [rsp+80h] [rbp-80h]
  tagRECT TextRect; // [rsp+88h] [rbp-78h] BYREF
  tagTEXTMETRICA textMetric; // [rsp+98h] [rbp-68h] BYREF
  tagLOGFONTW lf; // [rsp+D0h] [rbp-30h] BYREF
  char szIndex[24]; // [rsp+130h] [rbp+30h] BYREF
  char szIconLabel[56]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t wszIconLabel[48]; // [rsp+180h] [rbp+80h] BYREF

  v4 = 0;
  v37 = hIcon;
  v34 = iIconIndex;
  pvIn = (LPCSTR)lpszSourceFile;
  bUsedDefaultChar = 0;
  v7 = 0;
  LODWORD(v8) = 0;
  memset(&textMetric, 0, sizeof(textMetric));
  TextRect = 0;
  if ( hIcon )
  {
    hdc = GetDC(0);
    v9 = hdc;
    if ( hdc )
    {
      v31 = 0;
      v10 = 0;
      if ( lpszSourceFile )
      {
        v8 = (unsigned int)(safe_lstrlenW(lpszSourceFile) + 1);
        v10 = (char *)HeapAlloc(g_hHeap, 0, 2 * v8);
        if ( !v10 )
          goto $ErrRtn_6;
        v11 = AreFileApisANSI();
        WideCharToMultiByte(!v11, 0, lpszSourceFile, v8, v10, 2 * v8, szDefaultChar, &bUsedDefaultChar);
        v9 = hdc;
        v31 = bUsedDefaultChar;
      }
      MetaFileA = CreateMetaFileA(0);
      if ( !MetaFileA )
      {
LABEL_30:
        HeapFree(g_hHeap, 0, v10);
        goto $ErrRtn_6;
      }
      v7 = GlobalAlloc(0x2002u, 0x18u);
      if ( !v7 )
      {
        v13 = CloseMetaFile(MetaFileA);
        DeleteMetaFile(v13);
        goto LABEL_30;
      }
      v30 = 0;
      szIconLabel[0] = 0;
      if ( lpszLabel )
      {
        v4 = safe_lstrlenW(lpszLabel) + 1;
        if ( v4 > 0x2A )
        {
          StringCchCopyW(wszIconLabel, 0x2Bu, lpszLabel);
          lpszLabel = wszIconLabel;
          v4 = 42;
        }
        v14 = AreFileApisANSI();
        WideCharToMultiByte(!v14, 0, lpszLabel, v4, szIconLabel, 43, szDefaultChar, &bUsedDefaultChar);
        v30 = bUsedDefaultChar;
      }
      memset_0(&lf, 0, sizeof(lf));
      SystemParametersInfoW(0x1Fu, 0x5Cu, &lf, 0);
      hFont = CreateFontIndirectW(&lf);
      v15 = SelectObject(v9, hFont);
      GetTextMetricsA(hdc, &textMetric);
      v27 = 3 * textMetric.tmHeight;
      SelectObject(hdc, v15);
      LODWORD(cchRemain) = GetSystemMetrics(11);
      SystemMetrics = GetSystemMetrics(12);
      v16 = cchRemain;
      if ( szIconLabel[0] )
      {
        if ( 3 * (int)cchRemain > (unsigned int)cchRemain )
          v16 = 3 * cchRemain;
      }
      else
      {
        v16 = cchRemain + ((unsigned int)cchRemain >> 2);
      }
      SetMapMode(MetaFileA, 8);
      SetWindowOrgEx(MetaFileA, 0, 0, 0);
      SetWindowExtEx(MetaFileA, v16, v27 + 4 + SystemMetrics, 0);
      SetRectEmpty(&TextRect);
      TextRect.right = v16;
      TextRect.bottom = v27 + 4 + SystemMetrics;
      DrawIcon(MetaFileA, (unsigned int)(v16 - cchRemain) >> 1, 0, v37);
      Escape(MetaFileA, 15, 9, szIconOnly, 0);
      SysColor = GetSysColor(8);
      SetTextColor(MetaFileA, SysColor);
      SetBkMode(MetaFileA, 1);
      IconLabelTextOut(MetaFileA, hFont, v18, SystemMetrics + 4, lpMultiByteStr, &TextRect, szIconLabel);
      if ( pvIn )
      {
        Escape(MetaFileA, 15, v8, v10, 0);
        cchRemain = 0;
        StringCchPrintfExA(szIndex, 0x14u, 0, &cchRemain, 0, "%u", v34);
        v19 = szIndex;
        v20 = 21 - cchRemain;
      }
      else
      {
        if ( !v30 && !v31 )
        {
LABEL_26:
          v21 = CloseMetaFile(MetaFileA);
          if ( v21 )
          {
            v22 = GlobalLock(v7);
            v23 = XformWidthInPixelsToHimetric(hdc, v16);
            v24 = XformHeightInPixelsToHimetric(hdc, SystemMetrics + 4 + v27);
            *v22 = 8;
            v22[1] = v23;
            v22[2] = v24;
            *((_QWORD *)v22 + 2) = v21;
            GlobalUnlock(v7);
            if ( hFont )
              DeleteObject(hFont);
            goto LABEL_30;
          }
          GlobalFree(v7);
          v7 = 0;
$ErrRtn_6:
          ReleaseDC(0, hdc);
          return v7;
        }
        Escape(MetaFileA, 15, 1, Src, 0);
        v19 = "0";
        v20 = 2;
      }
      Escape(MetaFileA, 15, v20, v19, 0);
      if ( v30 )
      {
        Escape(MetaFileA, 15, 31, szIconLabelNext, 0);
        Escape(MetaFileA, 15, 2 * v4, (LPCSTR)lpszLabel, 0);
      }
      if ( v31 )
      {
        Escape(MetaFileA, 15, 32, szIconSourceNext, 0);
        Escape(MetaFileA, 15, 2 * v8, pvIn, 0);
      }
      goto LABEL_26;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18009c290  push    rbp
0x18009c292  push    rbx
0x18009c293  push    rsi
0x18009c294  push    rdi
0x18009c295  push    r12
0x18009c297  push    r13
0x18009c299  push    r14
0x18009c29b  push    r15
0x18009c29d  lea     rbp, [rsp-0F8h]
0x18009c2a5  sub     rsp, 1F8h
0x18009c2ac  mov     rax, cs:__security_cookie
0x18009c2b3  xor     rax, rsp
0x18009c2b6  mov     [rbp+130h+var_50], rax
0x18009c2bd  xor     r12d, r12d
0x18009c2c0  mov     [rbp+130h+var_1B0], hIcon
0x18009c2c4  xorps   xmm0, xmm0
0x18009c2c7  mov     [rsp+230h+var_1C8], iIcon
0x18009c2cc  mov     rax, hIcon
0x18009c2cf  mov     [rsp+230h+pvIn], pwcsSourceFile
0x18009c2d4  xor     ecx, ecx; hWnd
0x18009c2d6  mov     [rsp+230h+bUsedDefaultChar], r12d
0x18009c2db  mov     qword ptr [rbp+130h+textMetric.tmItalic], hIcon
0x18009c2df  mov     rdi, pwcsSourceFile
0x18009c2e2  mov     r13, pwcsLabel
0x18009c2e5  mov     esi, r12d
0x18009c2e8  mov     r14d, r12d
0x18009c2eb  movups  xmmword ptr [rbp+130h+textMetric.tmHeight], xmm0
0x18009c2ef  movups  xmmword ptr [rbp+130h+textMetric.tmExternalLeading], xmm0
0x18009c2f3  movups  xmmword ptr [rbp+130h+textMetric.tmOverhang], xmm0
0x18009c2f7  movups  xmmword ptr [rbp+130h+TextRect.left], xmm0
0x18009c2fb  test    rax, rax
0x18009c2fe  jz      loc_18009C8C1
0x18009c304  call    cs:__imp_GetDC
0x18009c30b  nop     dword ptr [rax+rax+00h]
0x18009c310  mov     [rsp+230h+hdc], rax
0x18009c315  mov     rbx, rax
0x18009c318  test    rax, rax
0x18009c31b  jz      loc_18009C8C1
0x18009c321  mov     [rsp+230h+var_1E0], r12d
0x18009c326  mov     r15d, r12d
0x18009c329  test    rdi, rdi
0x18009c32c  jz      loc_18009C3BD
0x18009c332  mov     hIcon, rdi; string
0x18009c335  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009c33a  mov     hIcon, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009c341  xor     edx, edx; dwFlags
0x18009c343  lea     r14d, [rax+1]
0x18009c347  mov     r8d, r14d
0x18009c34a  add     pwcsSourceFile, pwcsSourceFile; dwBytes
0x18009c34d  call    cs:__imp_HeapAlloc
0x18009c354  nop     dword ptr [rax+rax+00h]
0x18009c359  mov     r15, rax
0x18009c35c  test    rax, rax
0x18009c35f  jz      $ErrRtn_6
0x18009c365  lea     ebx, [r14+r14]
0x18009c369  call    cs:__imp_AreFileApisANSI
0x18009c370  nop     dword ptr [rax+rax+00h]
0x18009c375  mov     ecx, r12d
0x18009c378  mov     iIcon, r14d; cchWideChar
0x18009c37b  test    eax, eax
0x18009c37d  mov     pwcsSourceFile, rdi; lpWideCharStr
0x18009c380  lea     rax, [rsp+230h+bUsedDefaultChar]
0x18009c385  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18009c38a  setz    cl; CodePage
0x18009c38d  lea     rax, szDefaultChar; "?"
0x18009c394  xor     edx, edx; dwFlags
0x18009c396  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x18009c39b  mov     [rsp+230h+cbMultiByte], ebx; cbMultiByte
0x18009c39f  mov     [rsp+230h+lpMultiByteStr], r15; lpMultiByteStr
0x18009c3a4  call    cs:__imp_WideCharToMultiByte
0x18009c3ab  nop     dword ptr [rax+rax+00h]
0x18009c3b0  mov     eax, [rsp+230h+bUsedDefaultChar]
0x18009c3b4  mov     rbx, [rsp+230h+hdc]
0x18009c3b9  mov     [rsp+230h+var_1E0], eax
0x18009c3bd  xor     ecx, ecx; pszFile
0x18009c3bf  call    cs:__imp_CreateMetaFileA
0x18009c3c6  nop     dword ptr [rax+rax+00h]
0x18009c3cb  mov     rdi, rax
0x18009c3ce  test    rax, rax
0x18009c3d1  jz      loc_18009C896
0x18009c3d7  mov     edx, 18h; dwBytes
0x18009c3dc  mov     ecx, 2002h; uFlags
0x18009c3e1  call    cs:__imp_GlobalAlloc
0x18009c3e8  nop     dword ptr [rax+rax+00h]
0x18009c3ed  mov     rsi, rax
0x18009c3f0  test    rax, rax
0x18009c3f3  jnz     short loc_18009C418
0x18009c3f5  mov     hIcon, rdi; hdc
0x18009c3f8  call    cs:__imp_CloseMetaFile
0x18009c3ff  nop     dword ptr [rax+rax+00h]
0x18009c404  mov     hIcon, rax; hmf
0x18009c407  call    cs:__imp_DeleteMetaFile
0x18009c40e  nop     dword ptr [rax+rax+00h]
0x18009c413  jmp     loc_18009C896
0x18009c418  and     [rsp+230h+var_1E4], r12d
0x18009c41d  mov     [rbp+130h+szIconLabel], r12b
0x18009c421  test    r13, r13
0x18009c424  jz      loc_18009C4B3
0x18009c42a  mov     hIcon, r13; string
0x18009c42d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009c432  lea     r12d, [rax+1]
0x18009c436  cmp     r12d, 2Ah ; '*'
0x18009c43a  jbe     short loc_18009C45D
0x18009c43c  mov     pwcsSourceFile, r13; pszSrc
0x18009c43f  lea     hIcon, [rbp+130h+wszIconLabel]; pszDest
0x18009c446  mov     edx, 2Bh ; '+'; cchDest
0x18009c44b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009c450  lea     r13, [rbp+130h+wszIconLabel]
0x18009c457  mov     r12d, 2Ah ; '*'
0x18009c45d  call    cs:__imp_AreFileApisANSI
0x18009c464  nop     dword ptr [rax+rax+00h]
0x18009c469  xor     ecx, ecx
0x18009c46b  mov     iIcon, r12d; cchWideChar
0x18009c46e  test    eax, eax
0x18009c470  mov     pwcsSourceFile, r13; lpWideCharStr
0x18009c473  lea     rax, [rsp+230h+bUsedDefaultChar]
0x18009c478  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18009c47d  setz    cl; CodePage
0x18009c480  lea     rax, szDefaultChar; "?"
0x18009c487  xor     edx, edx; dwFlags
0x18009c489  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x18009c48e  lea     rax, [rbp+130h+szIconLabel]
0x18009c492  mov     [rsp+230h+cbMultiByte], 2Bh ; '+'; cbMultiByte
0x18009c49a  mov     [rsp+230h+lpMultiByteStr], rax; lpszString
0x18009c49f  call    cs:__imp_WideCharToMultiByte
0x18009c4a6  nop     dword ptr [rax+rax+00h]
0x18009c4ab  mov     eax, [rsp+230h+bUsedDefaultChar]
0x18009c4af  mov     [rsp+230h+var_1E4], eax
0x18009c4b3  xor     edx, edx; Val
0x18009c4b5  lea     hIcon, [rbp+130h+lf]; void *
0x18009c4b9  lea     r8d, [pwcsLabel+5Ch]; Size
0x18009c4bd  call    memset_0
0x18009c4c2  xor     iIcon, iIcon; fWinIni
0x18009c4c5  lea     pwcsSourceFile, [rbp+130h+lf]; pvParam
0x18009c4c9  lea     edx, [r9+5Ch]; uiParam
0x18009c4cd  lea     ecx, [pwcsLabel-3Dh]; uiAction
0x18009c4d0  call    cs:__imp_SystemParametersInfoW
0x18009c4d7  nop     dword ptr [rax+rax+00h]
0x18009c4dc  lea     hIcon, [rbp+130h+lf]; lplf
0x18009c4e0  call    cs:__imp_CreateFontIndirectW
0x18009c4e7  nop     dword ptr [rax+rax+00h]
0x18009c4ec  mov     pwcsLabel, rax; h
0x18009c4ef  mov     [rsp+230h+hFont], rax
0x18009c4f4  mov     hIcon, rbx; hdc
0x18009c4f7  call    cs:__imp_SelectObject
0x18009c4fe  nop     dword ptr [rax+rax+00h]
0x18009c503  mov     hIcon, [rsp+230h+hdc]; hdc
0x18009c508  lea     pwcsLabel, [rbp+130h+textMetric]; lptm
0x18009c50c  mov     rbx, rax
0x18009c50f  call    cs:__imp_GetTextMetricsA
0x18009c516  nop     dword ptr [rax+rax+00h]
0x18009c51b  mov     ecx, [rbp+130h+textMetric.tmHeight]
0x18009c51e  mov     pwcsLabel, rbx; h
0x18009c521  lea     eax, [hIcon+hIcon*2]
0x18009c524  mov     hIcon, [rsp+230h+hdc]; hdc
0x18009c529  mov     [rsp+230h+var_1F0], eax
0x18009c52d  call    cs:__imp_SelectObject
0x18009c534  nop     dword ptr [rax+rax+00h]
0x18009c539  mov     ecx, 0Bh; nIndex
0x18009c53e  call    cs:__imp_GetSystemMetrics
0x18009c545  nop     dword ptr [rax+rax+00h]
0x18009c54a  mov     ecx, 0Ch; nIndex
0x18009c54f  mov     dword ptr [rsp+230h+cchRemain], eax
0x18009c553  call    cs:__imp_GetSystemMetrics
0x18009c55a  nop     dword ptr [rax+rax+00h]
0x18009c55f  cmp     [rbp+130h+szIconLabel], 0
0x18009c563  mov     [rsp+230h+var_1E8], eax
0x18009c567  mov     eax, dword ptr [rsp+230h+cchRemain]
0x18009c56b  mov     ebx, eax
0x18009c56d  lea     ecx, [rax+rax*2]
0x18009c570  jnz     short loc_18009C579
0x18009c572  shr     ebx, 2
0x18009c575  add     ebx, eax
0x18009c577  jmp     short loc_18009C57E
0x18009c579  cmp     ecx, eax
0x18009c57b  cmova   ebx, ecx
0x18009c57e  mov     edx, 8; iMode
0x18009c583  mov     hIcon, rdi; hdc
0x18009c586  call    cs:__imp_SetMapMode
0x18009c58d  nop     dword ptr [rax+rax+00h]
0x18009c592  xor     iIcon, iIcon; lppt
0x18009c595  xor     r8d, r8d; y
0x18009c598  xor     edx, edx; x
0x18009c59a  mov     hIcon, rdi; hdc
0x18009c59d  call    cs:__imp_SetWindowOrgEx
0x18009c5a4  nop     dword ptr [rax+rax+00h]
0x18009c5a9  mov     eax, [rsp+230h+var_1F0]
0x18009c5ad  xor     iIcon, iIcon; lpsz
0x18009c5b0  mov     r8d, [rsp+230h+var_1E8]
0x18009c5b5  add     eax, 4
0x18009c5b8  add     r8d, eax; y
0x18009c5bb  mov     edx, ebx; x
0x18009c5bd  mov     hIcon, rdi; hdc
0x18009c5c0  call    cs:__imp_SetWindowExtEx
0x18009c5c7  nop     dword ptr [rax+rax+00h]
0x18009c5cc  lea     hIcon, [rbp+130h+TextRect]; lprc
0x18009c5d0  call    cs:__imp_SetRectEmpty
0x18009c5d7  nop     dword ptr [rax+rax+00h]
0x18009c5dc  mov     edx, [rsp+230h+var_1F0]
0x18009c5e0  xor     r8d, r8d; Y
0x18009c5e3  mov     eax, [rsp+230h+var_1E8]
0x18009c5e7  add     edx, 4
0x18009c5ea  mov     r9, [rbp+130h+var_1B0]; hIcon
0x18009c5ee  add     eax, edx
0x18009c5f0  mov     edx, ebx
0x18009c5f2  mov     [rbp+130h+TextRect.right], ebx
0x18009c5f5  sub     edx, dword ptr [rsp+230h+cchRemain]
0x18009c5f9  mov     hIcon, rdi; hDC
0x18009c5fc  shr     edx, 1; X
0x18009c5fe  mov     [rbp+130h+TextRect.bottom], eax
0x18009c601  call    cs:__imp_DrawIcon
0x18009c608  nop     dword ptr [rax+rax+00h]
0x18009c60d  and     [rsp+230h+lpMultiByteStr], 0
0x18009c613  lea     r9, szIconOnly; "IconOnly"
0x18009c61a  mov     edx, 0Fh; iEscape
0x18009c61f  mov     hIcon, rdi; hdc
0x18009c622  lea     r8d, [pwcsLabel-6]; cjIn
0x18009c626  call    cs:__imp_Escape
0x18009c62d  nop     dword ptr [rax+rax+00h]
0x18009c632  mov     ecx, 8; nIndex
0x18009c637  call    cs:__imp_GetSysColor
0x18009c63e  nop     dword ptr [rax+rax+00h]
0x18009c643  mov     edx, eax; color
0x18009c645  mov     hIcon, rdi; hdc
0x18009c648  call    cs:__imp_SetTextColor
0x18009c64f  nop     dword ptr [rax+rax+00h]
0x18009c654  mov     edx, 1; mode
0x18009c659  mov     hIcon, rdi; hdc
0x18009c65c  call    cs:__imp_SetBkMode
0x18009c663  nop     dword ptr [rax+rax+00h]
0x18009c668  mov     iIcon, [rsp+230h+var_1E8]
0x18009c66d  lea     rax, [rbp+130h+szIconLabel]
0x18009c671  mov     pwcsLabel, [rsp+230h+hFont]; hFont
0x18009c676  add     iIcon, 4
0x18009c67a  add     iIcon, [rsp+230h+var_1F0]
0x18009c67f  mov     hIcon, rdi; hDC
0x18009c682  sub     iIcon, [rsp+230h+var_1F0]; lpRect
0x18009c687  mov     [rsp+230h+lpDefaultChar], rax; hFont
0x18009c68c  lea     rax, [rbp+130h+TextRect]
0x18009c690  mov     qword ptr [rsp+230h+cbMultiByte], rax; hDC
0x18009c695  call    ?IconLabelTextOut@@YAXPEAUHDC__@@PEAUHFONT__@@HHIPEAUtagRECT@@PEBD@Z; IconLabelTextOut(HDC__ *,HFONT__ *,int,int,uint,tagRECT *,char const *)
0x18009c69a  xor     eax, eax
0x18009c69c  cmp     [rsp+230h+pvIn], rax
0x18009c6a1  jz      short loc_18009C706
0x18009c6a3  mov     r9, r15; pvIn
0x18009c6a6  mov     [rsp+230h+lpMultiByteStr], rax; dwFlags
0x18009c6ab  mov     r8d, r14d; cjIn
0x18009c6ae  lea     edx, [rax+0Fh]; iEscape
0x18009c6b1  mov     hIcon, rdi; hdc
0x18009c6b4  call    cs:__imp_Escape
0x18009c6bb  nop     dword ptr [rax+rax+00h]
0x18009c6c0  mov     eax, [rsp+230h+var_1C8]
0x18009c6c4  lea     r9, [rsp+230h+cchRemain]; pcchRemaining
0x18009c6c9  and     [rsp+230h+cchRemain], 0
0x18009c6cf  lea     hIcon, [rbp+130h+szIndex]; pszDest
0x18009c6d3  mov     dword ptr [rsp+230h+lpDefaultChar], eax
0x18009c6d7  xor     r8d, r8d; ppszDestEnd
0x18009c6da  lea     rax, aU; "%u"
0x18009c6e1  mov     qword ptr [rsp+230h+cbMultiByte], rax; pszFormat
0x18009c6e6  and     [rsp+230h+lpMultiByteStr], 0
0x18009c6ec  lea     edx, [pwcsSourceFile+14h]; cchDest
0x18009c6f0  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18009c6f5  mov     r8d, 15h
0x18009c6fb  lea     r9, [rbp+130h+szIndex]
0x18009c6ff  sub     r8d, dword ptr [rsp+230h+cchRemain]
0x18009c704  jmp     short loc_18009C747
0x18009c706  cmp     [rsp+230h+var_1E4], eax
0x18009c70a  jnz     short loc_18009C716
0x18009c70c  cmp     [rsp+230h+var_1E0], eax
0x18009c710  jz      loc_18009C7FD
0x18009c716  mov     edx, 0Fh; iEscape
0x18009c71b  mov     [rsp+230h+lpMultiByteStr], rax; pvOut
0x18009c720  lea     r9, Src; pvIn
0x18009c727  mov     hIcon, rdi; hdc
0x18009c72a  lea     r8d, [pwcsLabel-0Eh]; cjIn
0x18009c72e  call    cs:__imp_Escape
0x18009c735  nop     dword ptr [rax+rax+00h]
0x18009c73a  lea     r9, a0; "0"
0x18009c741  mov     r8d, 2; cjIn
0x18009c747  and     [rsp+230h+lpMultiByteStr], 0
0x18009c74d  mov     edx, 0Fh; iEscape
0x18009c752  mov     hIcon, rdi; hdc
0x18009c755  call    cs:__imp_Escape
0x18009c75c  nop     dword ptr [rax+rax+00h]
0x18009c761  cmp     [rsp+230h+var_1E4], 0
0x18009c766  jz      short loc_18009C7AE
0x18009c768  and     [rsp+230h+lpMultiByteStr], 0
0x18009c76e  lea     r9, szIconLabelNext; "OLE: Icon label next (Unicode)"
0x18009c775  mov     edx, 0Fh; iEscape
0x18009c77a  mov     hIcon, rdi; hdc
0x18009c77d  lea     r8d, [pwcsLabel+10h]; cjIn
0x18009c781  call    cs:__imp_Escape
0x18009c788  nop     dword ptr [rax+rax+00h]
0x18009c78d  and     [rsp+230h+lpMultiByteStr], 0
0x18009c793  lea     r8d, [r12+r12]; cjIn
0x18009c797  mov     r9, r13; pvIn
0x18009c79a  mov     edx, 0Fh; iEscape
0x18009c79f  mov     hIcon, rdi; hdc
0x18009c7a2  call    cs:__imp_Escape
0x18009c7a9  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
