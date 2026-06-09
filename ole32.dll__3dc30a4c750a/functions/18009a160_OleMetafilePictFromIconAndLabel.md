# OleMetafilePictFromIconAndLabel

- ea: `0x18009a160`
- end: `0x18009a6fd`
- name: `OleMetafilePictFromIconAndLabel`
- size: `1437`
- prototype: `HGLOBAL __stdcall(HICON hIcon, LPOLESTR lpszLabel, LPOLESTR lpszSourceFile, UINT iIconIndex)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180099cf0`
- `0x180099e50`

## callees

- `0x180009374`
- `0x18001b810`
- `0x180052390`
- `0x180053014`
- `0x180099604`
- `0x180099b00`
- `0x18009a160`

## import_xrefs

- `KERNELBASE!AreFileApisANSI` at `0x18009a220`
- `KERNELBASE!AreFileApisANSI` at `0x18009a2f7`
- `KERNELBASE!AreFileApisANSI` at `0x18009a220`
- `KERNELBASE!AreFileApisANSI` at `0x18009a2f7`
- `KERNELBASE!GlobalAlloc` at `0x18009a28e`
- `KERNELBASE!GlobalAlloc` at `0x18009a28e`
- `KERNELBASE!GlobalFree` at `0x18009a62b`
- `KERNELBASE!GlobalFree` at `0x18009a62b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009a6c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009a6c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a206`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a254`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a333`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a254`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a333`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009a668`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009a688`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009a668`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009a688`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009a6a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009a6a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009a63e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009a63e`
- `GDI32!DeleteMetaFile` at `0x18009a2a8`
- `GDI32!DeleteMetaFile` at `0x18009a2a8`
- `GDI32!DeleteObject` at `0x18009a6b4`
- `GDI32!DeleteObject` at `0x18009a6b4`
- `GDI32!SelectObject` at `0x18009a385`
- `GDI32!SelectObject` at `0x18009a3ab`
- `GDI32!SelectObject` at `0x18009a385`
- `GDI32!SelectObject` at `0x18009a3ab`
- `GDI32!CreateMetaFileA` at `0x18009a272`
- `GDI32!CreateMetaFileA` at `0x18009a272`
- `GDI32!CloseMetaFile` at `0x18009a29f`
- `GDI32!CloseMetaFile` at `0x18009a61a`
- `GDI32!CloseMetaFile` at `0x18009a29f`
- `GDI32!CloseMetaFile` at `0x18009a61a`
- `GDI32!CreateFontIndirectW` at `0x18009a374`
- `GDI32!CreateFontIndirectW` at `0x18009a374`
- `GDI32!GetTextMetricsA` at `0x18009a395`
- `GDI32!GetTextMetricsA` at `0x18009a395`
- `GDI32!SetMapMode` at `0x18009a3fc`
- `GDI32!SetMapMode` at `0x18009a3fc`
- `GDI32!SetWindowOrgEx` at `0x18009a40d`
- `GDI32!SetWindowOrgEx` at `0x18009a40d`
- `GDI32!SetWindowExtEx` at `0x18009a420`
- `GDI32!SetWindowExtEx` at `0x18009a420`
- `GDI32!Escape` at `0x18009a46e`
- `GDI32!Escape` at `0x18009a4dd`
- `GDI32!Escape` at `0x18009a557`
- `GDI32!Escape` at `0x18009a57b`
- `GDI32!Escape` at `0x18009a5a4`
- `GDI32!Escape` at `0x18009a5c6`
- `GDI32!Escape` at `0x18009a5ef`
- `GDI32!Escape` at `0x18009a611`
- `GDI32!Escape` at `0x18009a46e`
- `GDI32!Escape` at `0x18009a4dd`
- `GDI32!Escape` at `0x18009a557`
- `GDI32!Escape` at `0x18009a57b`
- `GDI32!Escape` at `0x18009a5a4`
- `GDI32!Escape` at `0x18009a5c6`
- `GDI32!Escape` at `0x18009a5ef`
- `GDI32!Escape` at `0x18009a611`
- `GDI32!SetTextColor` at `0x18009a484`
- `GDI32!SetTextColor` at `0x18009a484`
- `GDI32!SetBkMode` at `0x18009a492`
- `GDI32!SetBkMode` at `0x18009a492`
- `GDI32!GetDeviceCaps` at `0x18009a654`
- `GDI32!GetDeviceCaps` at `0x18009a678`
- `GDI32!GetDeviceCaps` at `0x18009a654`
- `GDI32!GetDeviceCaps` at `0x18009a678`
- `USER32!ReleaseDC` at `0x18009a6d1`
- `USER32!ReleaseDC` at `0x18009a6d1`
- `USER32!GetDC` at `0x18009a1cf`
- `USER32!GetDC` at `0x18009a1cf`
- `USER32!SystemParametersInfoW` at `0x18009a36a`
- `USER32!SystemParametersInfoW` at `0x18009a36a`
- `USER32!GetSystemMetrics` at `0x18009a3b6`
- `USER32!GetSystemMetrics` at `0x18009a3c4`
- `USER32!GetSystemMetrics` at `0x18009a3b6`
- `USER32!GetSystemMetrics` at `0x18009a3c4`
- `USER32!SetRectEmpty` at `0x18009a42a`
- `USER32!SetRectEmpty` at `0x18009a42a`
- `USER32!DrawIcon` at `0x18009a44c`
- `USER32!DrawIcon` at `0x18009a44c`
- `USER32!GetSysColor` at `0x18009a479`
- `USER32!GetSysColor` at `0x18009a479`

## pseudocode

```c
HGLOBAL __stdcall OleMetafilePictFromIconAndLabel(
        HICON hIcon,
        LPOLESTR lpszLabel,
        LPOLESTR lpszSourceFile,
        UINT iIconIndex)
{
  HGLOBAL v6; // r14
  HDC v7; // r15
  __int64 v8; // r13
  char *v9; // rsi
  BOOL v10; // eax
  HDC MetaFileA; // rdi
  HMETAFILE v12; // rax
  int v13; // ebx
  unsigned int v14; // eax
  BOOL v15; // eax
  HGDIOBJ v16; // rbx
  unsigned int SystemMetrics; // r15d
  int v18; // ebx
  int v19; // ecx
  COLORREF SysColor; // eax
  int v21; // r8d
  const char *v22; // r15
  char *v23; // r9
  int v24; // r8d
  HMETAFILE v25; // r12
  _DWORD *v26; // rax
  _DWORD *v27; // rdi
  int DeviceCaps; // eax
  int v29; // ebx
  int v30; // eax
  int v31; // eax
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int bUsedDefaultChar; // [rsp+40h] [rbp-C0h] BYREF
  int y; // [rsp+44h] [rbp-BCh]
  int v36; // [rsp+48h] [rbp-B8h]
  int v37; // [rsp+4Ch] [rbp-B4h]
  int v38; // [rsp+50h] [rbp-B0h]
  unsigned __int64 cchRemain; // [rsp+58h] [rbp-A8h] BYREF
  UINT v40; // [rsp+60h] [rbp-A0h]
  HDC hdc; // [rsp+68h] [rbp-98h]
  HFONT__ *hFont; // [rsp+70h] [rbp-90h]
  HICON v43; // [rsp+78h] [rbp-88h]
  LPCSTR pvIn; // [rsp+80h] [rbp-80h]
  tagRECT TextRect; // [rsp+88h] [rbp-78h] BYREF
  tagTEXTMETRICA textMetric; // [rsp+98h] [rbp-68h] BYREF
  tagLOGFONTW lf; // [rsp+D0h] [rbp-30h] BYREF
  char szIndex[24]; // [rsp+130h] [rbp+30h] BYREF
  char szIconLabel[56]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t wszIconLabel[48]; // [rsp+180h] [rbp+80h] BYREF

  v43 = hIcon;
  v40 = iIconIndex;
  pvIn = (LPCSTR)lpszSourceFile;
  bUsedDefaultChar = 0;
  v6 = 0;
  memset(&textMetric, 0, sizeof(textMetric));
  TextRect = 0;
  if ( hIcon )
  {
    hdc = GetDC(0);
    v7 = hdc;
    if ( hdc )
    {
      if ( lpszSourceFile )
      {
        v8 = (unsigned int)(safe_lstrlenW(lpszSourceFile) + 1);
        v9 = (char *)HeapAlloc(g_hHeap, 0, 2 * v8);
        if ( !v9 )
          goto LABEL_34;
        v10 = AreFileApisANSI();
        WideCharToMultiByte(!v10, 0, lpszSourceFile, v8, v9, 2 * v8, szDefaultChar, &bUsedDefaultChar);
        v38 = bUsedDefaultChar;
      }
      else
      {
        LODWORD(v8) = 0;
        v38 = 0;
        v9 = 0;
      }
      MetaFileA = CreateMetaFileA(0);
      if ( !MetaFileA )
      {
LABEL_33:
        HeapFree(g_hHeap, 0, v9);
        goto LABEL_34;
      }
      v6 = GlobalAlloc(0x2002u, 0x18u);
      if ( !v6 )
      {
        v12 = CloseMetaFile(MetaFileA);
        DeleteMetaFile(v12);
        goto LABEL_33;
      }
      szIconLabel[0] = 0;
      if ( lpszLabel )
      {
        v13 = 42;
        v14 = safe_lstrlenW(lpszLabel) + 1;
        v37 = 42;
        if ( v14 <= 0x2A )
        {
          v13 = v14;
          v37 = v14;
        }
        else
        {
          StringCchCopyW(wszIconLabel, 0x2Bu, lpszLabel);
          lpszLabel = wszIconLabel;
        }
        v15 = AreFileApisANSI();
        WideCharToMultiByte(!v15, 0, lpszLabel, v13, szIconLabel, 43, szDefaultChar, &bUsedDefaultChar);
        v36 = bUsedDefaultChar;
      }
      else
      {
        v37 = 0;
        v36 = 0;
      }
      memset_0(&lf, 0, sizeof(lf));
      SystemParametersInfoW(0x1Fu, 0x5Cu, &lf, 0);
      hFont = CreateFontIndirectW(&lf);
      v16 = SelectObject(v7, hFont);
      GetTextMetricsA(v7, &textMetric);
      LODWORD(cchRemain) = 3 * textMetric.tmHeight;
      SelectObject(v7, v16);
      SystemMetrics = GetSystemMetrics(11);
      v18 = SystemMetrics;
      v19 = GetSystemMetrics(12);
      if ( szIconLabel[0] )
      {
        if ( 3 * SystemMetrics > SystemMetrics )
          v18 = 3 * SystemMetrics;
      }
      else
      {
        v18 = SystemMetrics + (SystemMetrics >> 2);
      }
      y = v19 + cchRemain + 4;
      SetMapMode(MetaFileA, 8);
      SetWindowOrgEx(MetaFileA, 0, 0, 0);
      SetWindowExtEx(MetaFileA, v18, y, 0);
      SetRectEmpty(&TextRect);
      TextRect.right = v18;
      TextRect.bottom = y;
      DrawIcon(MetaFileA, (v18 - SystemMetrics) >> 1, 0, v43);
      Escape(MetaFileA, 15, 9, szIconOnly, 0);
      SysColor = GetSysColor(8);
      SetTextColor(MetaFileA, SysColor);
      SetBkMode(MetaFileA, 1);
      IconLabelTextOut(MetaFileA, hFont, v21, y - cchRemain, lpMultiByteStr, &TextRect, szIconLabel);
      v22 = pvIn;
      if ( pvIn )
      {
        Escape(MetaFileA, 15, v8, v9, 0);
        cchRemain = 0;
        StringCchPrintfExA(szIndex, 0x14u, 0, &cchRemain, 0, "%u", v40);
        v23 = szIndex;
        v24 = 21 - cchRemain;
      }
      else
      {
        if ( !v36 && !v38 )
        {
LABEL_29:
          v25 = CloseMetaFile(MetaFileA);
          if ( v25 )
          {
            v26 = GlobalLock(v6);
            v7 = hdc;
            v27 = v26;
            DeviceCaps = GetDeviceCaps(hdc, 88);
            v29 = MulDiv(2540, v18, DeviceCaps);
            v30 = GetDeviceCaps(v7, 90);
            v31 = MulDiv(2540, y, v30);
            *v27 = 8;
            v27[2] = v31;
            v27[1] = v29;
            *((_QWORD *)v27 + 2) = v25;
            GlobalUnlock(v6);
            if ( hFont )
              DeleteObject(hFont);
            goto LABEL_33;
          }
          GlobalFree(v6);
          v7 = hdc;
          v6 = 0;
LABEL_34:
          ReleaseDC(0, v7);
          return v6;
        }
        Escape(MetaFileA, 15, 1, Src, 0);
        v23 = "0";
        v24 = 2;
      }
      Escape(MetaFileA, 15, v24, v23, 0);
      if ( v36 )
      {
        Escape(MetaFileA, 15, 31, szIconLabelNext, 0);
        Escape(MetaFileA, 15, 2 * v37, (LPCSTR)lpszLabel, 0);
      }
      if ( v38 )
      {
        Escape(MetaFileA, 15, 32, szIconSourceNext, 0);
        Escape(MetaFileA, 15, 2 * v8, v22, 0);
      }
      goto LABEL_29;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18009a160  push    rbp
0x18009a162  push    rbx
0x18009a163  push    rsi
0x18009a164  push    rdi
0x18009a165  push    r12
0x18009a167  push    r13
0x18009a169  push    r14
0x18009a16b  push    r15
0x18009a16d  lea     rbp, [rsp-0F8h]
0x18009a175  sub     rsp, 1F8h
0x18009a17c  mov     rax, cs:__security_cookie
0x18009a183  xor     rax, rsp
0x18009a186  mov     [rbp+130h+var_50], rax
0x18009a18d  xorps   xmm0, xmm0
0x18009a190  mov     [rsp+230h+var_1B8], hIcon
0x18009a195  xor     ebx, ebx
0x18009a197  mov     [rsp+230h+var_1D0], iIcon
0x18009a19c  mov     rax, hIcon
0x18009a19f  mov     [rbp+130h+pvIn], pwcsSourceFile
0x18009a1a3  xor     ecx, ecx; hWnd
0x18009a1a5  mov     [rsp+230h+bUsedDefaultChar], ebx
0x18009a1a9  mov     qword ptr [rbp+130h+textMetric.tmItalic], hIcon
0x18009a1ad  mov     rdi, pwcsSourceFile
0x18009a1b0  mov     r12, pwcsLabel
0x18009a1b3  mov     r14d, ebx
0x18009a1b6  movups  xmmword ptr [rbp+130h+textMetric.tmHeight], xmm0
0x18009a1ba  movups  xmmword ptr [rbp+130h+textMetric.tmExternalLeading], xmm0
0x18009a1be  movups  xmmword ptr [rbp+130h+textMetric.tmOverhang], xmm0
0x18009a1c2  movups  xmmword ptr [rbp+130h+TextRect.left], xmm0
0x18009a1c6  test    rax, rax
0x18009a1c9  jz      loc_18009A6D7
0x18009a1cf  call    cs:__imp_GetDC
0x18009a1d5  mov     [rsp+230h+hdc], rax
0x18009a1da  mov     r15, rax
0x18009a1dd  test    rax, rax
0x18009a1e0  jz      loc_18009A6D7
0x18009a1e6  test    rdi, rdi
0x18009a1e9  jz      short loc_18009A266
0x18009a1eb  mov     hIcon, rdi; string
0x18009a1ee  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009a1f3  mov     hIcon, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009a1fa  xor     edx, edx; dwFlags
0x18009a1fc  lea     r13d, [rax+1]
0x18009a200  mov     r8d, r13d
0x18009a203  add     pwcsSourceFile, pwcsSourceFile; dwBytes
0x18009a206  call    cs:__imp_HeapAlloc
0x18009a20c  mov     rsi, rax
0x18009a20f  test    rax, rax
0x18009a212  jz      loc_18009A6CC
0x18009a218  lea     ebx, ds:0[r13*2]
0x18009a220  call    cs:__imp_AreFileApisANSI
0x18009a226  xor     ecx, ecx
0x18009a228  mov     iIcon, r13d; cchWideChar
0x18009a22b  test    eax, eax
0x18009a22d  mov     pwcsSourceFile, rdi; lpWideCharStr
0x18009a230  lea     rax, [rsp+230h+bUsedDefaultChar]
0x18009a235  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18009a23a  setz    cl; CodePage
0x18009a23d  lea     rax, szDefaultChar; "?"
0x18009a244  xor     edx, edx; dwFlags
0x18009a246  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x18009a24b  mov     [rsp+230h+cbMultiByte], ebx; cbMultiByte
0x18009a24f  mov     [rsp+230h+lpMultiByteStr], rsi; lpMultiByteStr
0x18009a254  call    cs:__imp_WideCharToMultiByte
0x18009a25a  mov     ebx, [rsp+230h+bUsedDefaultChar]
0x18009a25e  mov     [rsp+230h+var_1E0], ebx
0x18009a262  xor     ebx, ebx
0x18009a264  jmp     short loc_18009A270
0x18009a266  mov     r13d, ebx
0x18009a269  mov     [rsp+230h+var_1E0], ebx
0x18009a26d  mov     rsi, rbx
0x18009a270  xor     ecx, ecx; pszFile
0x18009a272  call    cs:__imp_CreateMetaFileA
0x18009a278  mov     rdi, rax
0x18009a27b  test    rax, rax
0x18009a27e  jz      loc_18009A6BA
0x18009a284  mov     edx, 18h; dwBytes
0x18009a289  mov     ecx, 2002h; uFlags
0x18009a28e  call    cs:__imp_GlobalAlloc
0x18009a294  mov     r14, rax
0x18009a297  test    rax, rax
0x18009a29a  jnz     short loc_18009A2B3
0x18009a29c  mov     hIcon, rdi; hdc
0x18009a29f  call    cs:__imp_CloseMetaFile
0x18009a2a5  mov     hIcon, rax; hmf
0x18009a2a8  call    cs:__imp_DeleteMetaFile
0x18009a2ae  jmp     loc_18009A6BA
0x18009a2b3  mov     [rbp+130h+szIconLabel], bl
0x18009a2b6  test    r12, r12
0x18009a2b9  jz      loc_18009A343
0x18009a2bf  mov     hIcon, r12; string
0x18009a2c2  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009a2c7  mov     ebx, 2Ah ; '*'
0x18009a2cc  inc     eax
0x18009a2ce  mov     [rsp+230h+var_1E4], ebx
0x18009a2d2  cmp     eax, ebx
0x18009a2d4  jbe     short loc_18009A2F1
0x18009a2d6  mov     pwcsSourceFile, r12; pszSrc
0x18009a2d9  lea     edx, [rbx+1]; cchDest
0x18009a2dc  lea     hIcon, [rbp+130h+wszIconLabel]; pszDest
0x18009a2e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009a2e8  lea     r12, [rbp+130h+wszIconLabel]
0x18009a2ef  jmp     short loc_18009A2F7
0x18009a2f1  mov     ebx, eax
0x18009a2f3  mov     [rsp+230h+var_1E4], eax
0x18009a2f7  call    cs:__imp_AreFileApisANSI
0x18009a2fd  xor     ecx, ecx
0x18009a2ff  mov     iIcon, ebx; cchWideChar
0x18009a302  test    eax, eax
0x18009a304  mov     pwcsSourceFile, r12; lpWideCharStr
0x18009a307  lea     rax, [rsp+230h+bUsedDefaultChar]
0x18009a30c  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18009a311  setz    cl; CodePage
0x18009a314  lea     rax, szDefaultChar; "?"
0x18009a31b  xor     edx, edx; dwFlags
0x18009a31d  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x18009a322  lea     rax, [rbp+130h+szIconLabel]
0x18009a326  mov     [rsp+230h+cbMultiByte], 2Bh ; '+'; cbMultiByte
0x18009a32e  mov     [rsp+230h+lpMultiByteStr], rax; lpMultiByteStr
0x18009a333  call    cs:__imp_WideCharToMultiByte
0x18009a339  mov     eax, [rsp+230h+bUsedDefaultChar]
0x18009a33d  mov     [rsp+230h+var_1E8], eax
0x18009a341  jmp     short loc_18009A34B
0x18009a343  mov     [rsp+230h+var_1E4], ebx
0x18009a347  mov     [rsp+230h+var_1E8], ebx
0x18009a34b  mov     ebx, 5Ch ; '\'
0x18009a350  lea     hIcon, [rbp+130h+lf]; void *
0x18009a354  mov     r8d, ebx; Size
0x18009a357  xor     edx, edx; Val
0x18009a359  call    memset_0
0x18009a35e  xor     iIcon, iIcon; fWinIni
0x18009a361  lea     pwcsSourceFile, [rbp+130h+lf]; pvParam
0x18009a365  mov     edx, ebx; uiParam
0x18009a367  lea     ecx, [rbx-3Dh]; uiAction
0x18009a36a  call    cs:__imp_SystemParametersInfoW
0x18009a370  lea     hIcon, [rbp+130h+lf]; lplf
0x18009a374  call    cs:__imp_CreateFontIndirectW
0x18009a37a  mov     pwcsLabel, rax; h
0x18009a37d  mov     [rsp+230h+hFont], rax
0x18009a382  mov     hIcon, r15; hdc
0x18009a385  call    cs:__imp_SelectObject
0x18009a38b  lea     pwcsLabel, [rbp+130h+textMetric]; lptm
0x18009a38f  mov     hIcon, r15; hdc
0x18009a392  mov     rbx, rax
0x18009a395  call    cs:__imp_GetTextMetricsA
0x18009a39b  mov     ecx, [rbp+130h+textMetric.tmHeight]
0x18009a39e  mov     pwcsLabel, rbx; h
0x18009a3a1  lea     eax, [hIcon+hIcon*2]
0x18009a3a4  mov     hIcon, r15; hdc
0x18009a3a7  mov     dword ptr [rsp+230h+cchRemain], eax
0x18009a3ab  call    cs:__imp_SelectObject
0x18009a3b1  mov     ecx, 0Bh; nIndex
0x18009a3b6  call    cs:__imp_GetSystemMetrics
0x18009a3bc  mov     ecx, 0Ch; nIndex
0x18009a3c1  mov     r15d, eax
0x18009a3c4  call    cs:__imp_GetSystemMetrics
0x18009a3ca  cmp     [rbp+130h+szIconLabel], 0
0x18009a3ce  mov     ebx, r15d
0x18009a3d1  mov     ecx, eax
0x18009a3d3  jnz     short loc_18009A3DD
0x18009a3d5  shr     ebx, 2
0x18009a3d8  add     ebx, r15d
0x18009a3db  jmp     short loc_18009A3E7
0x18009a3dd  lea     eax, [r15+r15*2]
0x18009a3e1  cmp     eax, r15d
0x18009a3e4  cmova   ebx, eax
0x18009a3e7  mov     eax, dword ptr [rsp+230h+cchRemain]
0x18009a3eb  mov     edx, 8; iMode
0x18009a3f0  add     eax, 4
0x18009a3f3  add     eax, ecx
0x18009a3f5  mov     hIcon, rdi; hdc
0x18009a3f8  mov     [rsp+230h+y], eax
0x18009a3fc  call    cs:__imp_SetMapMode
0x18009a402  xor     iIcon, iIcon; lppt
0x18009a405  xor     r8d, r8d; y
0x18009a408  xor     edx, edx; x
0x18009a40a  mov     hIcon, rdi; hdc
0x18009a40d  call    cs:__imp_SetWindowOrgEx
0x18009a413  mov     r8d, [rsp+230h+y]; y
0x18009a418  xor     iIcon, iIcon; lpsz
0x18009a41b  mov     edx, ebx; x
0x18009a41d  mov     hIcon, rdi; hdc
0x18009a420  call    cs:__imp_SetWindowExtEx
0x18009a426  lea     hIcon, [rbp+130h+TextRect]; lprc
0x18009a42a  call    cs:__imp_SetRectEmpty
0x18009a430  mov     eax, [rsp+230h+y]
0x18009a434  mov     edx, ebx
0x18009a436  mov     r9, [rsp+230h+var_1B8]; hIcon
0x18009a43b  sub     edx, r15d
0x18009a43e  shr     edx, 1; X
0x18009a440  xor     r8d, r8d; Y
0x18009a443  mov     hIcon, rdi; hDC
0x18009a446  mov     [rbp+130h+TextRect.right], ebx
0x18009a449  mov     [rbp+130h+TextRect.bottom], eax
0x18009a44c  call    cs:__imp_DrawIcon
0x18009a452  mov     edx, 0Fh; iEscape
0x18009a457  mov     [rsp+230h+lpMultiByteStr], 0; lpszString
0x18009a460  lea     r9, szIconOnly; "IconOnly"
0x18009a467  mov     hIcon, rdi; hdc
0x18009a46a  lea     r8d, [pwcsLabel-6]; cjIn
0x18009a46e  call    cs:__imp_Escape
0x18009a474  mov     ecx, 8; nIndex
0x18009a479  call    cs:__imp_GetSysColor
0x18009a47f  mov     edx, eax; color
0x18009a481  mov     hIcon, rdi; hdc
0x18009a484  call    cs:__imp_SetTextColor
0x18009a48a  mov     edx, 1; mode
0x18009a48f  mov     hIcon, rdi; hdc
0x18009a492  call    cs:__imp_SetBkMode
0x18009a498  mov     iIcon, [rsp+230h+y]
0x18009a49d  lea     rax, [rbp+130h+szIconLabel]
0x18009a4a1  sub     iIcon, dword ptr [rsp+230h+cchRemain]; lpRect
0x18009a4a6  mov     hIcon, rdi; hDC
0x18009a4a9  mov     pwcsLabel, [rsp+230h+hFont]; hFont
0x18009a4ae  mov     [rsp+230h+lpDefaultChar], rax; hFont
0x18009a4b3  lea     rax, [rbp+130h+TextRect]
0x18009a4b7  mov     qword ptr [rsp+230h+cbMultiByte], rax; hDC
0x18009a4bc  call    ?IconLabelTextOut@@YAXPEAUHDC__@@PEAUHFONT__@@HHIPEAUtagRECT@@PEBD@Z; IconLabelTextOut(HDC__ *,HFONT__ *,int,int,uint,tagRECT *,char const *)
0x18009a4c1  mov     r15, [rbp+130h+pvIn]
0x18009a4c5  xor     eax, eax
0x18009a4c7  test    r15, r15
0x18009a4ca  jz      short loc_18009A52F
0x18009a4cc  mov     r9, rsi; pvIn
0x18009a4cf  mov     [rsp+230h+lpMultiByteStr], rax; pvOut
0x18009a4d4  mov     r8d, r13d; cjIn
0x18009a4d7  lea     edx, [rax+0Fh]; iEscape
0x18009a4da  mov     hIcon, rdi; hdc
0x18009a4dd  call    cs:__imp_Escape
0x18009a4e3  mov     eax, [rsp+230h+var_1D0]
0x18009a4e7  lea     r9, [rsp+230h+cchRemain]; pcchRemaining
0x18009a4ec  mov     dword ptr [rsp+230h+lpDefaultChar], eax
0x18009a4f0  lea     hIcon, [rbp+130h+szIndex]; pszDest
0x18009a4f4  xor     r8d, r8d; ppszDestEnd
0x18009a4f7  mov     [rsp+230h+cchRemain], 0
0x18009a500  lea     rax, aU; "%u"
0x18009a507  mov     qword ptr [rsp+230h+cbMultiByte], rax; pszFormat
0x18009a50c  mov     [rsp+230h+lpMultiByteStr], 0; dwFlags
0x18009a515  lea     edx, [pwcsSourceFile+14h]; cchDest
0x18009a519  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18009a51e  mov     r8d, 15h
0x18009a524  lea     r9, [rbp+130h+szIndex]
0x18009a528  sub     r8d, dword ptr [rsp+230h+cchRemain]
0x18009a52d  jmp     short loc_18009A56A
0x18009a52f  cmp     [rsp+230h+var_1E8], eax
0x18009a533  jnz     short loc_18009A53F
0x18009a535  cmp     [rsp+230h+var_1E0], eax
0x18009a539  jz      loc_18009A617
0x18009a53f  mov     edx, 0Fh; iEscape
0x18009a544  mov     [rsp+230h+lpMultiByteStr], rax; pvOut
0x18009a549  lea     r9, Src; pvIn
0x18009a550  mov     hIcon, rdi; hdc
0x18009a553  lea     r8d, [pwcsLabel-0Eh]; cjIn
0x18009a557  call    cs:__imp_Escape
0x18009a55d  lea     r9, a0; "0"
0x18009a564  mov     r8d, 2; cjIn
0x18009a56a  mov     edx, 0Fh; iEscape
0x18009a56f  mov     [rsp+230h+lpMultiByteStr], 0; pvOut
0x18009a578  mov     hIcon, rdi; hdc
0x18009a57b  call    cs:__imp_Escape
0x18009a581  cmp     [rsp+230h+var_1E8], 0
0x18009a586  jz      short loc_18009A5CC
0x18009a588  mov     edx, 0Fh; iEscape
0x18009a58d  mov     [rsp+230h+lpMultiByteStr], 0; pvOut
0x18009a596  lea     r9, szIconLabelNext; "OLE: Icon label next (Unicode)"
0x18009a59d  mov     hIcon, rdi; hdc
0x18009a5a0  lea     r8d, [pwcsLabel+10h]; cjIn
0x18009a5a4  call    cs:__imp_Escape
0x18009a5aa  mov     r8d, [rsp+230h+var_1E4]
0x18009a5af  mov     r9, r12; pvIn
0x18009a5b2  add     r8d, r8d; cjIn
0x18009a5b5  mov     [rsp+230h+lpMultiByteStr], 0; pvOut
0x18009a5be  mov     edx, 0Fh; iEscape
0x18009a5c3  mov     hIcon, rdi; hdc
0x18009a5c6  call    cs:__imp_Escape
0x18009a5cc  cmp     [rsp+230h+var_1E0], 0
0x18009a5d1  jz      short loc_18009A617
0x18009a5d3  mov     edx, 0Fh; iEscape
0x18009a5d8  mov     [rsp+230h+lpMultiByteStr], 0; pvOut
0x18009a5e1  lea     r9, szIconSourceNext; "OLE: Icon source next (Unicode)"
0x18009a5e8  mov     hIcon, rdi; hdc
0x18009a5eb  lea     r8d, [pwcsLabel+11h]; cjIn
0x18009a5ef  call    cs:__imp_Escape
0x18009a5f5  lea     r8d, ds:0[r13*2]; cjIn
0x18009a5fd  mov     [rsp+230h+lpMultiByteStr], 0; pvOut
0x18009a606  mov     r9, r15; pvIn
0x18009a609  mov     edx, 0Fh; iEscape
0x18009a60e  mov     hIcon, rdi; hdc
0x18009a611  call    cs:__imp_Escape
0x18009a617  mov     hIcon, rdi; hdc
0x18009a61a  call    cs:__imp_CloseMetaFile
0x18009a620  mov     r12, rax
0x18009a623  mov     hIcon, r14; hMem
0x18009a626  test    rax, rax
0x18009a629  jnz     short loc_18009A63E
0x18009a62b  call    cs:__imp_GlobalFree
0x18009a631  mov     r15, [rsp+230h+hdc]
0x18009a636  xor     r14d, r14d
0x18009a639  jmp     loc_18009A6CC
0x18009a63e  call    cs:__imp_GlobalLock
0x18009a644  mov     r15, [rsp+230h+hdc]
  ... truncated ...
```
