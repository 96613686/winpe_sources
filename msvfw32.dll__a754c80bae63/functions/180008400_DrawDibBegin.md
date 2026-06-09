# DrawDibBegin

- ea: `0x180008400`
- end: `0x1800097d0`
- name: `DrawDibBegin`
- size: `5072`
- prototype: `BOOL __stdcall(HDRAWDIB hdd, HDC hdc, int dxDst, int dyDst, LPBITMAPINFOHEADER lpbi, int dxSrc, int dySrc, UINT wFlags)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009bb0`

## callees

- `0x180002640`
- `0x180002a90`
- `0x1800033e0`
- `0x180003a60`
- `0x1800080f8`
- `0x18000824c`
- `0x18000837c`
- `0x180008400`
- `0x18000a860`
- `0x18000ab84`
- `0x18000aeb0`
- `0x18000b0a0`
- `0x18000b928`
- `0x18000bbc0`
- `0x18000bc24`
- `0x18000bd90`
- `0x18000d9fc`
- `0x18000dae0`
- `0x18000e098`
- `0x1800162fd`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008463`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008451`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008451`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008603`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008a9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008e33`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008f5c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008603`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008a9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008e33`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008f5c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180008fb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000939c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800093d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000940d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180008fb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000939c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800093d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000940d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180008fad`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180008fc3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009393`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093a9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009404`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009417`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180008fad`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180008fc3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009393`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093a9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800093e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009404`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180009417`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008fcc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800093b2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800093ec`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009420`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008fcc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800093b2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800093ec`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009420`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800085fa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008a94`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008e2a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008f53`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800085fa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008a94`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008e2a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008f53`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000895b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000896d`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800089fd`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180008a21`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000895b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000896d`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800089fd`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180008a21`
- `GDI32!DeleteObject` at `0x180008d70`
- `GDI32!DeleteObject` at `0x180008d82`
- `GDI32!DeleteObject` at `0x18000919d`
- `GDI32!DeleteObject` at `0x18000922b`
- `GDI32!DeleteObject` at `0x1800092a1`
- `GDI32!DeleteObject` at `0x180009444`
- `GDI32!DeleteObject` at `0x1800094c9`
- `GDI32!DeleteObject` at `0x18000965f`
- `GDI32!DeleteObject` at `0x180008d70`
- `GDI32!DeleteObject` at `0x180008d82`
- `GDI32!DeleteObject` at `0x18000919d`
- `GDI32!DeleteObject` at `0x18000922b`
- `GDI32!DeleteObject` at `0x1800092a1`
- `GDI32!DeleteObject` at `0x180009444`
- `GDI32!DeleteObject` at `0x1800094c9`
- `GDI32!DeleteObject` at `0x18000965f`
- `GDI32!GetObjectW` at `0x180009087`
- `GDI32!GetObjectW` at `0x180009087`
- `GDI32!SelectPalette` at `0x18000856f`
- `GDI32!SelectPalette` at `0x180008d66`
- `GDI32!SelectPalette` at `0x180009306`
- `GDI32!SelectPalette` at `0x18000946e`
- `GDI32!SelectPalette` at `0x18000856f`
- `GDI32!SelectPalette` at `0x180008d66`
- `GDI32!SelectPalette` at `0x180009306`
- `GDI32!SelectPalette` at `0x18000946e`
- `GDI32!DeleteDC` at `0x180009212`
- `GDI32!DeleteDC` at `0x1800092ae`
- `GDI32!DeleteDC` at `0x180009432`
- `GDI32!DeleteDC` at `0x1800094b0`
- `GDI32!DeleteDC` at `0x180009646`
- `GDI32!DeleteDC` at `0x180009212`
- `GDI32!DeleteDC` at `0x1800092ae`
- `GDI32!DeleteDC` at `0x180009432`
- `GDI32!DeleteDC` at `0x1800094b0`
- `GDI32!DeleteDC` at `0x180009646`
- `GDI32!GetStockObject` at `0x18000855f`
- `GDI32!GetStockObject` at `0x180008d54`
- `GDI32!GetStockObject` at `0x18000855f`
- `GDI32!GetStockObject` at `0x180008d54`
- `GDI32!CreateCompatibleDC` at `0x180009184`
- `GDI32!CreateCompatibleDC` at `0x180009348`
- `GDI32!CreateCompatibleDC` at `0x1800095b7`
- `GDI32!CreateCompatibleDC` at `0x180009184`
- `GDI32!CreateCompatibleDC` at `0x180009348`
- `GDI32!CreateCompatibleDC` at `0x1800095b7`
- `GDI32!CreateDIBSection` at `0x180009338`
- `GDI32!CreateDIBSection` at `0x180009338`
- `GDI32!SelectObject` at `0x180009179`
- `GDI32!SelectObject` at `0x1800091d3`
- `GDI32!SelectObject` at `0x180009294`
- `GDI32!SelectObject` at `0x18000937a`
- `GDI32!SelectObject` at `0x1800094a3`
- `GDI32!SelectObject` at `0x1800095f5`
- `GDI32!SelectObject` at `0x180009179`
- `GDI32!SelectObject` at `0x1800091d3`
- `GDI32!SelectObject` at `0x180009294`
- `GDI32!SelectObject` at `0x18000937a`
- `GDI32!SelectObject` at `0x1800094a3`
- `GDI32!SelectObject` at `0x1800095f5`
- `GDI32!CreateCompatibleBitmap` at `0x1800091af`
- `GDI32!CreateCompatibleBitmap` at `0x1800095d4`
- `GDI32!CreateCompatibleBitmap` at `0x1800091af`
- `GDI32!CreateCompatibleBitmap` at `0x1800095d4`
- `USER32!GetDC` at `0x180009154`
- `USER32!GetDC` at `0x1800092d7`
- `USER32!GetDC` at `0x1800095a3`
- `USER32!GetDC` at `0x180009154`
- `USER32!GetDC` at `0x1800092d7`
- `USER32!GetDC` at `0x1800095a3`
- `USER32!ReleaseDC` at `0x180009247`
- `USER32!ReleaseDC` at `0x18000947a`
- `USER32!ReleaseDC` at `0x18000960c`
- `USER32!ReleaseDC` at `0x18000962b`
- `USER32!ReleaseDC` at `0x180009247`
- `USER32!ReleaseDC` at `0x18000947a`
- `USER32!ReleaseDC` at `0x18000960c`
- `USER32!ReleaseDC` at `0x18000962b`
- `USER32!WindowFromDC` at `0x180008787`
- `USER32!WindowFromDC` at `0x180008787`
- `USER32!GetActiveWindow` at `0x180009148`
- `USER32!GetActiveWindow` at `0x1800092cb`
- `USER32!GetActiveWindow` at `0x180009597`
- `USER32!GetActiveWindow` at `0x180009148`
- `USER32!GetActiveWindow` at `0x1800092cb`
- `USER32!GetActiveWindow` at `0x180009597`

## pseudocode

```c
BOOL __stdcall DrawDibBegin(
        HDRAWDIB hdd,
        HDC hdc,
        int dxDst,
        int dyDst,
        LPBITMAPINFOHEADER lpbi,
        int dxSrc,
        int dySrc,
        UINT wFlags)
{
  LPBITMAPINFOHEADER v8; // r14
  int biWidth; // r12d
  int biHeight; // ebx
  UINT v15; // edi
  HDC v16; // r15
  unsigned int v17; // edi
  bool v18; // zf
  unsigned int v19; // ebx
  HPALETTE StockObject; // rax
  WORD *p_biBitCount; // rbx
  unsigned int biClrUsed; // eax
  WORD v24; // cx
  unsigned __int64 v25; // rcx
  signed int v26; // edx
  size_t v27; // rdi
  HGLOBAL v28; // rax
  void *v29; // rax
  UINT i; // ebx
  int v31; // edi
  char v32; // cl
  HIC v33; // rcx
  int v34; // edi
  unsigned __int16 v35; // r15
  __int128 v36; // xmm1
  __int64 v37; // xmm0_8
  int v38; // ecx
  int v39; // eax
  char v40; // al
  DWORD v41; // ebx
  HIC v42; // rax
  LONG_PTR v43; // rax
  int v44; // ecx
  unsigned int v45; // ecx
  int v46; // edx
  int v47; // r15d
  int v48; // r12d
  HIC v49; // rdi
  int dy; // ebx
  int v51; // eax
  int v52; // edx
  int v53; // edx
  __int128 v54; // xmm1
  unsigned int *v55; // rdx
  HIC v56; // rcx
  HGLOBAL v57; // rax
  LPVOID v58; // rax
  __int64 v59; // rdx
  _OWORD *v60; // rax
  _OWORD *v61; // rcx
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  int v69; // ebx
  int v70; // r9d
  int v71; // r8d
  int v72; // eax
  const void *v73; // rcx
  HPALETTE v74; // rax
  void *v75; // rcx
  int v76; // eax
  __int128 v77; // xmm1
  __int64 v78; // xmm0_8
  __int128 v79; // xmm1
  unsigned int *v80; // rdx
  HGLOBAL v81; // rax
  LPVOID v82; // rax
  int v83; // eax
  __int16 biBitCount; // ax
  char v85; // al
  int v86; // ecx
  unsigned int v87; // edx
  int v88; // ecx
  int v89; // edi
  int v90; // r14d
  int v91; // r12d
  __int128 v92; // xmm1
  __int64 v93; // r10
  __int64 v94; // rax
  HGLOBAL v95; // rax
  LPVOID v96; // rax
  const void *v97; // rcx
  const void *v98; // rcx
  HGLOBAL v99; // rax
  HGLOBAL v100; // rax
  __int16 v101; // ax
  void *v102; // rcx
  HWND ActiveWindow; // rbx
  int *v104; // rbx
  int v105; // eax
  unsigned int v106; // r9d
  UINT v107; // edx
  int v108; // r8d
  __int16 v109; // cx
  int v110; // eax
  int v111; // edi
  HDC v112; // rcx
  void *v113; // rcx
  HBITMAP CompatibleBitmap; // rax
  HDC v115; // rcx
  HGDIOBJ v116; // rax
  __int64 v117; // r8
  HDC v118; // rcx
  void *v119; // rcx
  int v120; // r15d
  HWND v121; // r14
  HPALETTE v122; // rdx
  HPALETTE v123; // rdi
  _QWORD *v124; // rbx
  HDC CompatibleDC; // rax
  void *v126; // rdx
  HGDIOBJ v127; // rax
  const void *v128; // rcx
  HGLOBAL v129; // rax
  HGLOBAL v130; // rax
  const void *v131; // rcx
  HGLOBAL v132; // rax
  HGLOBAL v133; // rax
  const void *v134; // rcx
  HGLOBAL v135; // rax
  HGLOBAL v136; // rax
  void *v137; // rcx
  HDC v138; // rcx
  void *v139; // rcx
  __int64 v140; // rax
  __int64 v141; // rax
  int v142; // edi
  HWND v143; // rbx
  HDC v144; // rax
  int v145; // r8d
  int v146; // edx
  HBITMAP v147; // rax
  HDC v148; // rcx
  HDC v149; // rcx
  void *v150; // rcx
  _DWORD *v151; // rcx
  HIC v152; // rcx
  __int64 v153; // rdx
  int v154; // eax
  int v155; // eax
  char v156; // [rsp+30h] [rbp-59h]
  DWORD_PTR dw1[2]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v158; // [rsp+50h] [rbp-39h]
  __int64 v159; // [rsp+60h] [rbp-29h]
  __int64 v160; // [rsp+68h] [rbp-21h]
  int v161; // [rsp+70h] [rbp-19h]
  int v162; // [rsp+74h] [rbp-15h]
  __int64 v163; // [rsp+78h] [rbp-11h]
  int v164; // [rsp+80h] [rbp-9h]
  int v165; // [rsp+84h] [rbp-5h]
  int v166; // [rsp+E0h] [rbp+57h]
  int nNumber; // [rsp+E8h] [rbp+5Fh]
  int lpbia; // [rsp+F0h] [rbp+67h]

  v8 = lpbi;
  if ( !lpbi || !hdd || *(_DWORD *)hdd != 2792 )
    return 0;
  EnterCriticalSection(&DCISerialize);
  DrawDibInit();
  LeaveCriticalSection(&DCISerialize);
  biWidth = dxSrc;
  if ( dxSrc < 0 )
  {
    biWidth = lpbi->biWidth;
    dxSrc = biWidth;
  }
  biHeight = dySrc;
  if ( dySrc < 0 )
  {
    biHeight = lpbi->biHeight;
    dySrc = biHeight;
  }
  if ( dxDst < 0 )
    dxDst = biWidth;
  v166 = dxDst;
  if ( dyDst < 0 )
    dyDst = biHeight;
  nNumber = dyDst;
  if ( !biWidth || !biHeight )
    return 0;
  v15 = wFlags ^ *((_DWORD *)hdd + 1);
  v16 = (HDC)*((_QWORD *)hdd + 37);
  v156 = v15;
  lpbia = *((_DWORD *)hdd + 1);
  if ( !(unsigned int)DibEq(*((_QWORD *)hdd + 42), v8)
    || (v15 & 0x1000) != 0
    || (v17 = 1, *((_QWORD *)hdd + 6) != *((_QWORD *)hdd + 7)) )
  {
    v17 = 0;
  }
  if ( *((_DWORD *)hdd + 6) != v166
    || *((_DWORD *)hdd + 7) != nNumber
    || *((_DWORD *)hdd + 4) != biWidth
    || (v18 = *((_DWORD *)hdd + 5) == biHeight, v19 = 1, !v18) )
  {
    v19 = 0;
  }
  *((_QWORD *)hdd + 37) = hdc;
  if ( v17
    && v19
    && (((unsigned __int16)wFlags ^ (unsigned __int16)lpbia) & 0x11E0) == 0
    && (v8->biCompression - 1 > 1 || hdc == v16) )
  {
    return 1;
  }
  *((_QWORD *)hdd + 7) = *((_QWORD *)hdd + 6);
  if ( *((_QWORD *)hdd + 4) && !v17 && hdc )
  {
    StockObject = (HPALETTE)GetStockObject(15);
    SelectPalette(hdc, StockObject, 1);
  }
  DrawDibFree(hdd, v17, v19);
  p_biBitCount = &v8->biBitCount;
  *((_DWORD *)hdd + 6) = v166;
  *((_DWORD *)hdd + 7) = nNumber;
  *((_DWORD *)hdd + 4) = biWidth;
  *((_DWORD *)hdd + 5) = dySrc;
  biClrUsed = v8->biClrUsed;
  if ( !biClrUsed )
  {
    v24 = *p_biBitCount;
    if ( *p_biBitCount <= 8u && v24 )
    {
      biClrUsed = 1 << v24;
      v8->biClrUsed = 1 << v24;
    }
    else
    {
      biClrUsed = 0;
    }
  }
  if ( !v17 )
  {
    v25 = 4LL * biClrUsed;
    if ( v25 > 0xFFFFFFFF )
      return 0;
    v26 = v25 + v8->biSize;
    if ( v26 < v8->biSize )
      return 0;
    v27 = v26;
    v28 = GlobalAlloc(0x40u, v26);
    v29 = GlobalLock(v28);
    *((_QWORD *)hdd + 42) = v29;
    if ( !v29 )
      return 0;
    memcpy_0(v29, v8, v27);
    *((_QWORD *)hdd + 43) = (char *)v8 + v8->biSize;
  }
  *((_OWORD *)hdd + 22) = *(_OWORD *)&v8->biSize;
  *((_OWORD *)hdd + 23) = *(_OWORD *)&v8->biCompression;
  *((_QWORD *)hdd + 48) = *(_QWORD *)&v8->biClrUsed;
  *(_DWORD *)(*((_QWORD *)hdd + 42) + 20LL) = 0;
  *((_DWORD *)hdd + 93) = 0;
  if ( (unsigned __int16)(*p_biBitCount - 1) <= 7u )
  {
    memcpy_0((char *)hdd + 392, (char *)v8 + (int)v8->biSize, 4LL * (int)v8->biClrUsed);
    memcpy_0((char *)hdd + 1508, (char *)v8 + (int)v8->biSize, 4LL * (int)v8->biClrUsed);
  }
  *((_DWORD *)hdd + 21) = 0;
  if ( (wFlags & 0x20) == 0 || (gwRasterCaps & 0x100) != 0 && *p_biBitCount <= 8u && !*((_QWORD *)hdd + 6) )
  {
    i = wFlags;
    goto LABEL_52;
  }
  for ( i = wFlags & 0xFFFFFFDF; ; i &= ~0x40u )
  {
    wFlags = i;
LABEL_52:
    *((_DWORD *)hdd + 1) = i & 0x3FFD ^ *((_DWORD *)hdd + 1) & 0xFFFFC000;
    if ( !v8->biCompression )
      goto LABEL_70;
    v31 = i & 0x40;
    if ( (i & 0x40) != 0 )
      goto LABEL_77;
    v32 = DrawDibProfileDisplay(v8);
    if ( (v32 & 1) == 0 )
      goto LABEL_77;
    if ( biWidth == v166 && dySrc == nNumber )
    {
      if ( (v32 & 4) != 0 )
        goto LABEL_63;
      if ( dySrc == nNumber )
        goto LABEL_60;
    }
    if ( (v32 & 0x10) == 0 )
    {
LABEL_60:
      if ( v166 % biWidth || nNumber % dySrc || (v32 & 8) == 0 )
        goto LABEL_77;
    }
LABEL_63:
    if ( v8->biCompression - 1 > 1 || hdc && WindowFromDC(hdc) && (unsigned __int16)gwScreenBitDepth >= 8u )
    {
      v33 = (HIC)*((_QWORD *)hdd + 41);
      LOWORD(i) = i | 0x80;
      LOWORD(wFlags) = i;
      if ( v33 )
        ICClose(v33);
      *((_QWORD *)hdd + 41) = 0;
LABEL_70:
      v34 = dySrc;
LABEL_71:
      v35 = 0;
      v36 = *((_OWORD *)hdd + 23);
      *(_OWORD *)((char *)hdd + 1468) = *((_OWORD *)hdd + 22);
      v37 = *((_QWORD *)hdd + 48);
      *(_OWORD *)((char *)hdd + 1484) = v36;
      *(_QWORD *)((char *)hdd + 1500) = v37;
      v38 = *((_DWORD *)hdd + 369);
      v39 = -v38;
      *((_DWORD *)hdd + 372) = 0;
      if ( v38 > 0 )
        v39 = v38;
      *((_DWORD *)hdd + 369) = v39;
      if ( (i & 0x80u) != 0 || v8->biCompression )
      {
LABEL_175:
        if ( *((_QWORD *)hdd + 4)
          && *(_WORD *)(*((_QWORD *)hdd + 42) + 14LL) > 8u
          && ((*((_DWORD *)hdd + 1) ^ lpbia) & 0x20000) != 0 )
        {
          v73 = (const void *)*((_QWORD *)hdd + 40);
          if ( v73 )
          {
            DitherTerm(v73);
            *((_QWORD *)hdd + 40) = 0;
          }
          if ( hdc )
          {
            v74 = (HPALETTE)GetStockObject(15);
            SelectPalette(hdc, v74, 1);
          }
          DeleteObject(*((HGDIOBJ *)hdd + 4));
          v75 = (void *)*((_QWORD *)hdd + 5);
          if ( v75 )
            DeleteObject(v75);
          *((_QWORD *)hdd + 4) = 0;
          *((_QWORD *)hdd + 5) = 0;
        }
        v76 = *((_DWORD *)hdd + 1);
        if ( (v76 & 0x10000) != 0 )
        {
          if ( *((_WORD *)hdd + 183) >= 8u )
          {
            v77 = *((_OWORD *)hdd + 23);
            *(_OWORD *)((char *)hdd + 1416) = *((_OWORD *)hdd + 22);
            v78 = *((_QWORD *)hdd + 48);
            *(_OWORD *)((char *)hdd + 1432) = v77;
            *((_QWORD *)hdd + 181) = v78;
            *((_DWORD *)hdd + 355) = v166;
            *((_DWORD *)hdd + 356) = nNumber;
            v79 = *(_OWORD *)((char *)hdd + 1432);
            *(_OWORD *)dw1 = *(_OWORD *)((char *)hdd + 1416);
            v159 = *((_QWORD *)hdd + 181);
            v158 = v79;
            if ( (int)SAFE_DIBSIZEIMAGE(dw1, (char *)hdd + 1436) < 0 )
              return 0;
            v81 = GlobalAlloc(0x42u, *v80);
            v82 = GlobalLock(v81);
            *((_QWORD *)hdd + 13) = v82;
            if ( v82 )
            {
              v8 = (LPBITMAPINFOHEADER)((char *)hdd + 1416);
              *((_DWORD *)hdd + 368) = v166;
              biWidth = v166;
              *((_DWORD *)hdd + 369) = nNumber;
              dySrc = nNumber;
            }
            else
            {
              *((_DWORD *)hdd + 1) &= ~0x10000u;
            }
          }
          else
          {
            *((_DWORD *)hdd + 1) = v76 & 0xFFFEFFFF;
          }
        }
        v83 = *((_DWORD *)hdd + 1);
        if ( (v83 & 0x20000) != 0 )
        {
          *((_DWORD *)hdd + 1) = v83 & 0xFFFFFFDF;
          if ( v35 > 8u )
          {
            biBitCount = v35;
            if ( v8->biBitCount <= 8u )
              biBitCount = v8->biBitCount;
          }
          else
          {
            biBitCount = 8;
          }
          *((_WORD *)hdd + 741) = biBitCount;
          v85 = DrawDibProfileDisplay((LPBITMAPINFOHEADER)((char *)hdd + 1468));
          v86 = *((_DWORD *)hdd + 1);
          v87 = v86 & 0xFFFBFFFF;
          v88 = v86 | 0x40000;
          if ( (v85 & 4) == 0 )
            v87 = v88;
          *((_DWORD *)hdd + 1) = v87;
          v89 = *((_DWORD *)hdd + 368);
          v90 = *((_DWORD *)hdd + 369);
          *((_DWORD *)hdd + 368) = biWidth;
          v91 = dySrc;
          *((_DWORD *)hdd + 369) = dySrc;
          v92 = *(_OWORD *)((char *)hdd + 1484);
          *(_OWORD *)dw1 = *(_OWORD *)((char *)hdd + 1468);
          v159 = *(_QWORD *)((char *)hdd + 1500);
          v158 = v92;
          if ( (int)SAFE_DIBSIZEIMAGE(dw1, (char *)hdd + 1488) < 0 )
            return 0;
          v94 = DitherInit((char *)hdd + 352, v93, (char *)hdd + 88, *((_QWORD *)hdd + 40));
          *((_QWORD *)hdd + 40) = v94;
          if ( v94 == -1
            || !*((_QWORD *)hdd + 11)
            || (v95 = GlobalAlloc(0x42u, *((unsigned int *)hdd + 372)),
                v96 = GlobalLock(v95),
                (*((_QWORD *)hdd + 39) = v96) == 0) )
          {
            v97 = (const void *)*((_QWORD *)hdd + 40);
            if ( v97 == (const void *)-1LL )
            {
              *((_QWORD *)hdd + 40) = 0;
            }
            else if ( v97 )
            {
              DitherTerm(v97);
            }
            v98 = (const void *)*((_QWORD *)hdd + 39);
            if ( v98 && v98 != *((const void **)hdd + 38) )
            {
              v99 = GlobalHandle(v98);
              GlobalUnlock(v99);
              v100 = GlobalHandle(*((LPCVOID *)hdd + 39));
              GlobalFree(v100);
            }
            v101 = *((_WORD *)hdd + 183);
            *((_DWORD *)hdd + 1) &= ~0x20000u;
            *((_WORD *)hdd + 741) = v101;
            *((_QWORD *)hdd + 40) = 0;
            *((_QWORD *)hdd + 39) = 0;
            *((_DWORD *)hdd + 368) = v89;
            *((_DWORD *)hdd + 369) = v90;
            *((_DWORD *)hdd + 372) = 0;
          }
        }
        else
        {
          v91 = dySrc;
        }
        if ( (gwRasterCaps & 0x100) != 0 && *((_WORD *)hdd + 741) <= 8u && !*((_QWORD *)hdd + 4) )
        {
          *((_QWORD *)hdd + 4) = CreateBIPalette(0);
          *((_DWORD *)hdd + 1) |= 0x10000000u;
        }
        if ( (v156 & 0x20) != 0 )
          *((_DWORD *)hdd + 1) |= 0x10000000u;
        v102 = (void *)*((_QWORD *)hdd + 4);
        ActiveWindow = 0;
        if ( v102 )
        {
          if ( (*((_DWORD *)hdd + 1) & 0x10000000) != 0 )
          {
            v104 = (int *)((char *)hdd + 64);
            GetObjectW(v102, 4, (char *)hdd + 64);
            if ( (v156 & 0x20) != 0 )
              SetPalFlags(*((HPALETTE *)hdd + 4), 0);
            v105 = IsIdentityPalette(*((HGDIOBJ *)hdd + 4));
            v106 = *((_DWORD *)hdd + 1) | 0x100000;
            if ( !v105 )
              v106 = *((_DWORD *)hdd + 1) & 0xFFEFFFFF;
            *((_DWORD *)hdd + 1) = v106;
            v107 = v105 != 0 ? 0xA : 0;
            *((_DWORD *)hdd + 17) = v107;
            v108 = *v104;
            if ( *v104 > 236 )
              v108 = 236;
            *((_DWORD *)hdd + 18) = v108;
            *((_DWORD *)hdd + 19) = v108 + v107;
            if ( (v106 & 0x20) != 0 )
              SetPalFlags(*((HPALETTE *)hdd + 4), v107);
            ActiveWindow = 0;
          }
        }
        else
        {
          *((_DWORD *)hdd + 16) = 0;
        }
        v109 = *((_WORD *)hdd + 741);
        if ( (unsigned __int16)(v109 - 1) > 7u )
          v110 = 0;
        else
          v110 = 1 << v109;
        *((_DWORD *)hdd + 375) = v110;
        DrawDibSetPalette(hdd, *((HPALETTE *)hdd + 6));
        if ( (*((_DWORD *)hdd + 1) & 0x40000) != 0 )
        {
          if ( hdc )
          {
            v111 = 0;
          }
          else
          {
            v111 = 1;
            ActiveWindow = GetActiveWindow();
            hdc = GetDC(ActiveWindow);
          }
          v112 = (HDC)*((_QWORD *)hdd + 36);
          if ( v112 )
          {
            if ( h )
              SelectObject(v112, h);
          }
          else
          {
            *((_QWORD *)hdd + 36) = CreateCompatibleDC(hdc);
          }
          v113 = (void *)*((_QWORD *)hdd + 35);
          if ( v113 )
            DeleteObject(v113);
          CompatibleBitmap = CreateCompatibleBitmap(hdc, *((_DWORD *)hdd + 368), v91);
          *((_QWORD *)hdd + 35) = CompatibleBitmap;
          if ( !CompatibleBitmap
            || (v115 = (HDC)*((_QWORD *)hdd + 36)) == 0
            || (v116 = SelectObject(v115, CompatibleBitmap),
                v117 = *((_QWORD *)hdd + 35),
                *((_DWORD *)hdd + 1) |= 0x10000000u,
                h = v116,
                !(unsigned int)SetBitmapBegin((char *)hdd + 112, hdc, v117, (char *)hdd + 1468, *((_DWORD *)hdd + 21))) )
          {
            v118 = (HDC)*((_QWORD *)hdd + 36);
            if ( v118 )
            {
              DeleteDC(v118);
              *((_QWORD *)hdd + 36) = 0;
            }
            v119 = (void *)*((_QWORD *)hdd + 35);
            if ( v119 )
            {
              DeleteObject(v119);
              *((_QWORD *)hdd + 35) = 0;
            }
            *((_DWORD *)hdd + 1) &= ~0x40000u;
          }
          if ( v111 )
          {
            ReleaseDC(ActiveWindow, hdc);
            hdc = 0;
          }
        }
        if ( v35 <= 4u || !*((_QWORD *)hdd + 41) && (*((_DWORD *)hdd + 1) & 0x30000) == 0 )
        {
          v138 = (HDC)*((_QWORD *)hdd + 36);
          if ( v138 )
          {
            if ( h )
              SelectObject(v138, h);
            DeleteDC(*((HDC *)hdd + 36));
            *((_QWORD *)hdd + 36) = 0;
          }
          v139 = (void *)*((_QWORD *)hdd + 35);
          if ( v139 )
          {
            DeleteObject(v139);
            *((_QWORD *)hdd + 35) = 0;
          }
          v124 = (char *)hdd + 304;
          v140 = *((_QWORD *)hdd + 38);
          if ( *((_QWORD *)hdd + 39) == v140 )
            *((_QWORD *)hdd + 39) = 0;
          if ( *((_QWORD *)hdd + 13) == v140 )
            *((_QWORD *)hdd + 13) = 0;
          if ( *((_QWORD *)hdd + 12) == v140 )
            *((_QWORD *)hdd + 12) = 0;
          *v124 = 0;
          goto LABEL_295;
        }
        if ( *((_QWORD *)hdd + 35) )
        {
          SelectObject(*((HDC *)hdd + 36), h);
          DeleteObject(*((HGDIOBJ *)hdd + 35));
          DeleteDC(*((HDC *)hdd + 36));
          *((_QWORD *)hdd + 36) = 0;
          *((_QWORD *)hdd + 35) = 0;
        }
        if ( hdc )
        {
          v121 = 0;
          v120 = 0;
        }
        else
        {
          v120 = 1;
          v121 = GetActiveWindow();
          hdc = GetDC(v121);
        }
        v122 = (HPALETTE)*((_QWORD *)hdd + 6);
        if ( v122 || (v122 = (HPALETTE)*((_QWORD *)hdd + 4), v123 = 0, v122) )
          v123 = SelectPalette(hdc, v122, 1);
        v124 = (char *)hdd + 304;
        *((_QWORD *)hdd + 35) = CreateDIBSection(
                                  hdc,
                                  (const BITMAPINFO *)((char *)hdd + 1468),
                                  *((_DWORD *)hdd + 21) != 0,
                                  (void **)hdd + 38,
                                  0,
                                  0);
        CompatibleDC = CreateCompatibleDC(hdc);
        *((_QWORD *)hdd + 36) = CompatibleDC;
        if ( CompatibleDC )
        {
          v126 = (void *)*((_QWORD *)hdd + 35);
          if ( v126 && *v124 )
          {
            v127 = SelectObject(CompatibleDC, v126);
            v128 = (const void *)*((_QWORD *)hdd + 39);
            h = v127;
            if ( v128 )
            {
              v129 = GlobalHandle(v128);
              GlobalUnlock(v129);
              v130 = GlobalHandle(*((LPCVOID *)hdd + 39));
              GlobalFree(v130);
              *((_QWORD *)hdd + 39) = *v124;
            }
            else
            {
              v131 = (const void *)*((_QWORD *)hdd + 13);
              if ( v131 )
              {
                v132 = GlobalHandle(v131);
                GlobalUnlock(v132);
                v133 = GlobalHandle(*((LPCVOID *)hdd + 13));
                GlobalFree(v133);
                *((_QWORD *)hdd + 13) = *v124;
              }
              else
              {
                v134 = (const void *)*((_QWORD *)hdd + 12);
                if ( v134 )
                {
                  v135 = GlobalHandle(v134);
                  GlobalUnlock(v135);
                  v136 = GlobalHandle(*((LPCVOID *)hdd + 12));
                  GlobalFree(v136);
                  *((_QWORD *)hdd + 12) = *v124;
                }
              }
            }
LABEL_277:
            if ( v120 )
            {
              if ( v123 )
                SelectPalette(hdc, v123, 0);
              ReleaseDC(v121, hdc);
              hdc = 0;
            }
LABEL_295:
            if ( *((_QWORD *)hdd + 41) )
            {
              if ( (*((_DWORD *)hdd + 1) & 0x30000) == 0 )
              {
                if ( dword_180023D58 )
                {
                  if ( !*v124 )
                  {
                    v141 = *((_QWORD *)hdd + 42);
                    if ( v166 == *(_DWORD *)(v141 + 4) && nNumber == *(_DWORD *)(v141 + 8) )
                    {
                      if ( (*((_DWORD *)hdd + 1) & 0x40000) != 0 )
                      {
                        if ( *((_QWORD *)hdd + 35) )
                          DrawDibQueryBitmapX(hdd);
                      }
                      else if ( (DrawDibProfileDisplay((LPBITMAPINFOHEADER)((char *)hdd + 352)) & 0x20) != 0 )
                      {
                        if ( hdc )
                        {
                          v143 = 0;
                          v142 = 0;
                        }
                        else
                        {
                          v142 = 1;
                          v143 = GetActiveWindow();
                          hdc = GetDC(v143);
                        }
                        v144 = CreateCompatibleDC(hdc);
                        v145 = *((_DWORD *)hdd + 369);
                        v146 = *((_DWORD *)hdd + 368);
                        *((_QWORD *)hdd + 36) = v144;
                        v147 = CreateCompatibleBitmap(hdc, v146, v145);
                        *((_QWORD *)hdd + 35) = v147;
                        if ( v147 && (v148 = (HDC)*((_QWORD *)hdd + 36)) != 0 )
                        {
                          h = SelectObject(v148, v147);
                          if ( v142 )
                            ReleaseDC(v143, hdc);
                          DrawDibQueryBitmapX(hdd);
                        }
                        else if ( v142 && hdc )
                        {
                          ReleaseDC(v143, hdc);
                        }
                        if ( (*((_DWORD *)hdd + 1) & 0x200000) == 0 )
                        {
                          v149 = (HDC)*((_QWORD *)hdd + 36);
                          if ( v149 )
                          {
                            DeleteDC(v149);
                            *((_QWORD *)hdd + 36) = 0;
                          }
                          v150 = (void *)*((_QWORD *)hdd + 35);
                          if ( v150 )
                          {
                            DeleteObject(v150);
                            *((_QWORD *)hdd + 35) = 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( *((_QWORD *)hdd + 41) )
            {
              if ( pdci )
              {
                if ( gfScreenX )
                {
                  if ( (wFlags & 0x40) == 0 )
                  {
                    if ( word_180023FCE != 32
                      || (v151 = (_DWORD *)*((_QWORD *)hdd + 42), v151[4] != 808801865)
                      || *((_DWORD *)hdd + 6) != 2 * v151[1]
                      || *((_DWORD *)hdd + 7) != 2 * v151[2] )
                    {
                      if ( ((gwRasterCaps & 0x100) == 0 || (*((_DWORD *)hdd + 1) & 0x100000) != 0)
                        && (gwScreenBitDepth != 8 || (gwRasterCaps & 0x100) != 0)
                        && (*((_DWORD *)hdd + 1) & 0x30000) == 0 )
                      {
                        v152 = (HIC)*((_QWORD *)hdd + 41);
                        *(_QWORD *)&v158 = 0;
                        dw1[0] = 0;
                        dw1[1] = *((_QWORD *)hdd + 42);
                        v164 = *((_DWORD *)hdd + 4);
                        v165 = *((_DWORD *)hdd + 5);
                        *((_QWORD *)&v158 + 1) = &biScreen;
                        v159 = lpScreen;
                        v161 = *((_DWORD *)hdd + 6);
                        v162 = *((_DWORD *)hdd + 7);
                        v163 = 0;
                        v160 = 0;
                        if ( !ICSendMessage(v152, 0x403Du, (DWORD_PTR)dw1, 0x48u) )
                          *((_DWORD *)hdd + 1) |= 0x38400000u;
                      }
                    }
                  }
                }
              }
            }
            v153 = *((_QWORD *)hdd + 42);
            v154 = -*((_DWORD *)hdd + 89);
            if ( *((int *)hdd + 89) > 0 )
              v154 = *((_DWORD *)hdd + 89);
            if ( v154 != *(_DWORD *)(v153 + 4) )
              goto LABEL_342;
            v155 = -*((_DWORD *)hdd + 90);
            if ( *((int *)hdd + 90) > 0 )
              v155 = *((_DWORD *)hdd + 90);
            if ( v155 != *(_DWORD *)(v153 + 8) )
LABEL_342:
              *((_DWORD *)hdd + 1) |= 0x4000000u;
            return 1;
          }
          DeleteDC(CompatibleDC);
        }
        v137 = (void *)*((_QWORD *)hdd + 35);
        if ( v137 )
          DeleteObject(v137);
        *v124 = 0;
        *((_QWORD *)hdd + 36) = 0;
        *((_QWORD *)hdd + 35) = 0;
        goto LABEL_277;
      }
      v40 = DrawDibProfileDisplay(v8);
      if ( (unsigned __int16)gwScreenBitDepth <= 0x18u )
      {
        v35 = gwScreenBitDepth;
        if ( (unsigned __int16)gwScreenBitDepth < 0x18u )
        {
          if ( (unsigned __int16)gwScreenBitDepth < 0x10u )
            goto LABEL_124;
          goto LABEL_121;
        }
      }
      else
      {
        v35 = 32;
      }
      if ( v8->biBitCount == 32 )
      {
LABEL_122:
        if ( (v40 & 1) == 0 )
          v35 = 24;
LABEL_124:
        if ( (v40 & 4) == 0 )
          *((_DWORD *)hdd + 1) |= 0x40000u;
        v69 = *((_DWORD *)hdd + 1);
        if ( dword_180023D70 )
        {
          if ( dword_180023D70 != 1 )
          {
LABEL_131:
            v70 = v166;
            if ( (biWidth != v166 || v34 != nNumber) && (v40 & 0x10) == 0 )
            {
              v69 |= 0x10000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( 2 * biWidth == v166 && 2 * v34 == nNumber && (v40 & 8) != 0 )
            {
              v69 &= ~0x10000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( !(v166 % biWidth) && !(nNumber % v34) && (v40 & 8) != 0 )
            {
              v69 &= ~0x10000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( v8->biBitCount > v35 )
            {
              v69 |= 0x20000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( (dword_180023D60 || (wFlags & 0x1000) != 0) && v35 <= 8u )
            {
              v69 |= 0x20000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( v8->biBitCount > 8u && v8->biBitCount < v35 )
            {
              v69 |= 0x20000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( (v69 & 0x20000) != 0 )
            {
              if ( v8->biBitCount == 16 )
              {
                v71 = v40 & 1;
                if ( (v40 & 1) != 0 )
                {
                  v69 &= ~0x20000u;
                  *((_DWORD *)hdd + 1) = v69;
                }
              }
              else
              {
                v71 = v40 & 1;
              }
              if ( v8->biBitCount == 32 && v71 )
              {
                v69 &= ~0x20000u;
                *((_DWORD *)hdd + 1) = v69;
              }
              if ( v8->biBitCount == 8 && v8->biClrUsed <= 0x10 )
              {
                v72 = AreColorsAllGDIColors(v8, 8);
                v70 = v166;
                if ( v72 )
                {
                  v69 &= ~0x20000u;
                  *((_DWORD *)hdd + 1) = v69;
                }
              }
              if ( (v69 & 0x20000) != 0 && (biWidth != v70 || v34 != nNumber) )
              {
                v69 |= 0x10000u;
                *((_DWORD *)hdd + 1) = v69;
              }
            }
            if ( (v69 & 0x40) != 0 && !*((_QWORD *)hdd + 41) && (v69 & 0x70000) == 0 )
            {
              v69 |= 0x10000u;
              *((_DWORD *)hdd + 1) = v69;
            }
            if ( ((v8->biBitCount - 8) & 0xFFE7) != 0 || v8->biBitCount == 32 )
              *((_DWORD *)hdd + 1) = v69 & 0xFFFEFFFF;
            goto LABEL_175;
          }
          v69 |= 0x40000u;
        }
        else
        {
          v69 &= ~0x40000u;
        }
        *((_DWORD *)hdd + 1) = v69;
        goto LABEL_131;
      }
LABEL_121:
      if ( v8->biBitCount != 16 )
        goto LABEL_124;
      goto LABEL_122;
    }
LABEL_77:
    if ( !*((_QWORD *)hdd + 41) )
    {
      v41 = 541412434;
      if ( v8->biCompression != 1 )
        v41 = 0;
      v42 = ICLocate(0x63646976u, v41, v8, 0, 3u);
      *((_QWORD *)hdd + 41) = v42;
      if ( v42 || (v42 = ICLocate(0x63646976u, v41, v8, 0, 2u), (*((_QWORD *)hdd + 41) = v42) != 0) )
      {
        v43 = ICSendMessage(v42, 0x401Du, 0, 0);
        v44 = *((_DWORD *)hdd + 1);
        i = wFlags;
        if ( v43 )
          v45 = v44 & 0x7FFFFFFF;
        else
          v45 = v44 | 0x80000000;
        *((_DWORD *)hdd + 1) = v45;
      }
      else
      {
        i = wFlags;
      }
    }
    if ( ((*((_QWORD *)hdd + 41) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      break;
    *((_QWORD *)hdd + 41) = -1;
    if ( !v31 )
      return 0;
  }
  v46 = -v8->biHeight;
  if ( v8->biHeight > 0 )
    v46 = v8->biHeight;
  v47 = -v8->biWidth;
  if ( v8->biWidth > 0 )
    v47 = v8->biWidth;
  if ( dword_180023D60 || (v48 = 0, (i & 0x1000) != 0) )
    v48 = 16;
  v49 = (HIC)*((_QWORD *)hdd + 41);
  dy = MulDiv(nNumber, v46, dySrc);
  v51 = MulDiv(v166, v47, dxSrc);
  if ( ICGetDisplayFormat(v49, v8, (LPBITMAPINFOHEADER)((char *)hdd + 352), v48, v51, dy) )
  {
    if ( *((_WORD *)hdd + 183) == 32
      && !*((_DWORD *)hdd + 92)
      && v8->biCompression == 808801865
      && *((_DWORD *)hdd + 89) == 2 * v8->biWidth
      && *((_DWORD *)hdd + 90) == 2 * v8->biHeight )
    {
      *((_WORD *)hdd + 183) = 24;
    }
    v52 = -*((_DWORD *)hdd + 89);
    if ( *((int *)hdd + 89) > 0 )
      v52 = *((_DWORD *)hdd + 89);
    biWidth = MulDiv(dxSrc, v52, *(_DWORD *)(*((_QWORD *)hdd + 42) + 4LL));
    v53 = -*((_DWORD *)hdd + 90);
    if ( *((int *)hdd + 90) > 0 )
      v53 = *((_DWORD *)hdd + 90);
    v34 = MulDiv(dySrc, v53, *(_DWORD *)(*((_QWORD *)hdd + 42) + 8LL));
    v54 = *((_OWORD *)hdd + 23);
    dySrc = v34;
    *(_OWORD *)dw1 = *((_OWORD *)hdd + 22);
    v159 = *((_QWORD *)hdd + 48);
    v158 = v54;
    if ( (int)SAFE_DIBSIZEIMAGE(dw1, (char *)hdd + 372) < 0 )
    {
      v56 = (HIC)*((_QWORD *)hdd + 41);
LABEL_110:
      ICClose(v56);
      *((_QWORD *)hdd + 41) = -1;
      return 0;
    }
    v57 = GlobalAlloc(2u, *v55);
    v58 = GlobalLock(v57);
    v56 = (HIC)*((_QWORD *)hdd + 41);
    *((_QWORD *)hdd + 12) = v58;
    if ( !v58 )
      goto LABEL_110;
    *((_DWORD *)hdd + 1) |= 0x1000000u;
    if ( !ICSendMessage(v56, 0x400Cu, (DWORD_PTR)v8, (DWORD_PTR)hdd + 352) )
    {
      v59 = 8;
      *((_DWORD *)hdd + 3) = 3;
      v60 = (char *)hdd + 1508;
      v61 = (char *)hdd + 392;
      do
      {
        v62 = v61[1];
        *v60 = *v61;
        v63 = v61[2];
        v60[1] = v62;
        v64 = v61[3];
        v60[2] = v63;
        v65 = v61[4];
        v60[3] = v64;
        v66 = v61[5];
        v60[4] = v65;
        v67 = v61[6];
        v60[5] = v66;
        v68 = v61[7];
        v61 += 8;
        v60[6] = v67;
        v60[7] = v68;
        v60 += 8;
        --v59;
      }
      while ( v59 );
      v8 = (LPBITMAPINFOHEADER)((char *)hdd + 352);
      LOBYTE(i) = wFlags;
      goto LABEL_71;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008400  mov     [rsp-8+arg_0], rbx
0x180008405  push    rbp
0x180008406  push    rsi
0x180008407  push    rdi
0x180008408  push    r12
0x18000840a  push    r13
0x18000840c  push    r14
0x18000840e  push    r15
0x180008410  lea     rbp, [rsp-7]
0x180008415  sub     rsp, 90h
0x18000841c  mov     r14, [rbp+37h+lpbi]
0x180008420  mov     edi, r9d
0x180008423  mov     r15d, r8d
0x180008426  mov     r13, rdx
0x180008429  mov     rsi, rcx
0x18000842c  test    r14, r14
0x18000842f  jz      loc_180008A70
0x180008435  test    rcx, rcx
0x180008438  jz      loc_180008A70
0x18000843e  cmp     dword ptr [rcx], 0AE8h
0x180008444  jnz     loc_180008A70
0x18000844a  lea     rcx, DCISerialize; lpCriticalSection
0x180008451  call    cs:__imp_EnterCriticalSection
0x180008457  call    DrawDibInit
0x18000845c  lea     rcx, DCISerialize; lpCriticalSection
0x180008463  call    cs:__imp_LeaveCriticalSection
0x180008469  mov     r12d, [rbp+37h+dxSrc]
0x18000846d  test    r12d, r12d
0x180008470  jns     short loc_18000847A
0x180008472  mov     r12d, [r14+4]
0x180008476  mov     [rbp+37h+dxSrc], r12d
0x18000847a  mov     ebx, [rbp+37h+dySrc]
0x18000847d  test    ebx, ebx
0x18000847f  jns     short loc_180008488
0x180008481  mov     ebx, [r14+8]
0x180008485  mov     [rbp+37h+dySrc], ebx
0x180008488  test    r15d, r15d
0x18000848b  cmovs   r15d, r12d
0x18000848f  test    edi, edi
0x180008491  mov     [rbp+37h+arg_10], r15d
0x180008495  cmovs   edi, ebx
0x180008498  mov     [rbp+37h+nNumber], edi
0x18000849b  test    r12d, r12d
0x18000849e  jz      loc_180008A70
0x1800084a4  test    ebx, ebx
0x1800084a6  jz      loc_180008A70
0x1800084ac  mov     eax, [rsi+4]
0x1800084af  mov     rdx, r14
0x1800084b2  mov     rcx, [rsi+150h]
0x1800084b9  mov     edi, eax
0x1800084bb  xor     edi, [rbp+37h+wFlags]
0x1800084be  mov     r15, [rsi+128h]
0x1800084c5  mov     dword ptr [rbp+37h+var_90], edi
0x1800084c8  mov     dword ptr [rbp+37h+lpbi], eax
0x1800084cb  call    DibEq
0x1800084d0  xor     edx, edx
0x1800084d2  lea     r8d, [rdx+1]
0x1800084d6  test    eax, eax
0x1800084d8  jz      short loc_1800084ED
0x1800084da  bt      edi, 0Ch
0x1800084de  jb      short loc_1800084ED
0x1800084e0  mov     rax, [rsi+38h]
0x1800084e4  mov     edi, r8d
0x1800084e7  cmp     [rsi+30h], rax
0x1800084eb  jz      short loc_1800084EF
0x1800084ed  mov     edi, edx
0x1800084ef  mov     ecx, [rbp+37h+arg_10]
0x1800084f2  cmp     [rsi+18h], ecx
0x1800084f5  jnz     short loc_18000850D
0x1800084f7  mov     ecx, [rbp+37h+nNumber]
0x1800084fa  cmp     [rsi+1Ch], ecx
0x1800084fd  jnz     short loc_18000850D
0x1800084ff  cmp     [rsi+10h], r12d
0x180008503  jnz     short loc_18000850D
0x180008505  cmp     [rsi+14h], ebx
0x180008508  mov     ebx, r8d
0x18000850b  jz      short loc_18000850F
0x18000850d  mov     ebx, edx
0x18000850f  mov     [rsi+128h], r13
0x180008516  test    edi, edi
0x180008518  jz      short loc_180008545
0x18000851a  test    ebx, ebx
0x18000851c  jz      short loc_180008545
0x18000851e  mov     ecx, dword ptr [rbp+37h+lpbi]
0x180008521  xor     ecx, [rbp+37h+wFlags]
0x180008524  test    ecx, 11E0h
0x18000852a  jnz     short loc_180008545
0x18000852c  mov     ecx, [r14+10h]
0x180008530  sub     ecx, r8d
0x180008533  cmp     ecx, r8d
0x180008536  ja      short loc_18000853D
0x180008538  cmp     r13, r15
0x18000853b  jnz     short loc_180008545
0x18000853d  mov     eax, r8d
0x180008540  jmp     loc_180008A72
0x180008545  mov     rax, [rsi+30h]
0x180008549  mov     [rsi+38h], rax
0x18000854d  cmp     [rsi+20h], rdx
0x180008551  jz      short loc_180008575
0x180008553  test    edi, edi
0x180008555  jnz     short loc_180008575
0x180008557  test    r13, r13
0x18000855a  jz      short loc_180008575
0x18000855c  lea     ecx, [rdi+0Fh]; i
0x18000855f  call    cs:__imp_GetStockObject
0x180008565  lea     r8d, [rdi+1]; bForceBkgd
0x180008569  mov     rcx, r13; hdc
0x18000856c  mov     rdx, rax; hPal
0x18000856f  call    cs:__imp_SelectPalette
0x180008575  mov     r8d, ebx
0x180008578  mov     edx, edi
0x18000857a  mov     rcx, rsi
0x18000857d  call    DrawDibFree
0x180008582  mov     eax, [rbp+37h+arg_10]
0x180008585  lea     rbx, [r14+0Eh]
0x180008589  mov     r15d, [rbp+37h+dySrc]
0x18000858d  xor     r10d, r10d
0x180008590  mov     [rsi+18h], eax
0x180008593  mov     edx, 8
0x180008598  mov     eax, [rbp+37h+nNumber]
0x18000859b  mov     [rsi+1Ch], eax
0x18000859e  mov     [rsi+10h], r12d
0x1800085a2  mov     [rsi+14h], r15d
0x1800085a6  mov     eax, [r14+20h]
0x1800085aa  test    eax, eax
0x1800085ac  jnz     short loc_1800085C9
0x1800085ae  movzx   ecx, word ptr [rbx]
0x1800085b1  cmp     cx, dx
0x1800085b4  ja      short loc_1800085C6
0x1800085b6  test    cx, cx
0x1800085b9  jz      short loc_1800085C6
0x1800085bb  lea     eax, [rdx-7]
0x1800085be  shl     eax, cl
0x1800085c0  mov     [r14+20h], eax
0x1800085c4  jmp     short loc_1800085C9
0x1800085c6  mov     eax, r10d
0x1800085c9  test    edi, edi
0x1800085cb  jnz     short loc_180008637
0x1800085cd  mov     ecx, eax
0x1800085cf  mov     eax, 0FFFFFFFFh
0x1800085d4  shl     rcx, 2
0x1800085d8  cmp     rcx, rax
0x1800085db  ja      loc_180008A70
0x1800085e1  mov     eax, [r14]
0x1800085e4  lea     edx, [rcx+rax]
0x1800085e7  cmp     edx, eax
0x1800085e9  jb      loc_180008A70
0x1800085ef  movsxd  rdi, edx
0x1800085f2  mov     ecx, 40h ; '@'; uFlags
0x1800085f7  mov     rdx, rdi; dwBytes
0x1800085fa  call    cs:__imp_GlobalAlloc
0x180008600  mov     rcx, rax; hMem
0x180008603  call    cs:__imp_GlobalLock
0x180008609  mov     [rsi+150h], rax
0x180008610  test    rax, rax
0x180008613  jz      loc_180008A70
0x180008619  mov     r8, rdi; Size
0x18000861c  mov     rdx, r14; Src
0x18000861f  mov     rcx, rax; void *
0x180008622  call    memcpy_0
0x180008627  mov     eax, [r14]
0x18000862a  add     rax, r14
0x18000862d  mov     [rsi+158h], rax
0x180008634  xor     r10d, r10d
0x180008637  movups  xmm0, xmmword ptr [r14]
0x18000863b  lea     rax, [rsi+160h]
0x180008642  movups  xmmword ptr [rax], xmm0
0x180008645  movups  xmm1, xmmword ptr [r14+10h]
0x18000864a  movups  xmmword ptr [rax+10h], xmm1
0x18000864e  movsd   xmm0, qword ptr [r14+20h]
0x180008654  movsd   qword ptr [rax+20h], xmm0
0x180008659  mov     rax, [rsi+150h]
0x180008660  mov     [rax+14h], r10d
0x180008664  mov     [rsi+174h], r10d
0x18000866b  movzx   eax, word ptr [rbx]
0x18000866e  dec     ax
0x180008671  cmp     ax, 7
0x180008675  ja      short loc_1800086AE
0x180008677  movsxd  r8, dword ptr [r14+20h]
0x18000867b  lea     rcx, [rsi+188h]; void *
0x180008682  movsxd  rdx, dword ptr [r14]
0x180008685  shl     r8, 2; Size
0x180008689  add     rdx, r14; Src
0x18000868c  call    memcpy_0
0x180008691  movsxd  r8, dword ptr [r14+20h]
0x180008695  lea     rcx, [rsi+5E4h]; void *
0x18000869c  movsxd  rdx, dword ptr [r14]
0x18000869f  shl     r8, 2; Size
0x1800086a3  add     rdx, r14; Src
0x1800086a6  call    memcpy_0
0x1800086ab  xor     r10d, r10d
0x1800086ae  test    byte ptr [rbp+37h+wFlags], 20h
0x1800086b2  mov     [rsi+54h], r10d
0x1800086b6  jz      short loc_1800086DF
0x1800086b8  test    cs:gwRasterCaps, 100h
0x1800086c2  jz      short loc_1800086D4
0x1800086c4  mov     edx, 8
0x1800086c9  cmp     [rbx], dx
0x1800086cc  ja      short loc_1800086D4
0x1800086ce  cmp     [rsi+30h], r10
0x1800086d2  jz      short loc_1800086DF
0x1800086d4  mov     ebx, [rbp+37h+wFlags]
0x1800086d7  and     ebx, 0FFFFFFDFh
0x1800086da  mov     [rbp+37h+wFlags], ebx
0x1800086dd  jmp     short loc_1800086E2
0x1800086df  mov     ebx, [rbp+37h+wFlags]
0x1800086e2  mov     edx, 3
0x1800086e7  mov     ecx, [rsi+4]
0x1800086ea  mov     eax, ebx
0x1800086ec  and     ecx, 0FFFFC000h
0x1800086f2  and     eax, 3FFDh
0x1800086f7  xor     ecx, eax
0x1800086f9  mov     [rsi+4], ecx
0x1800086fc  cmp     [r14+10h], r10d
0x180008700  jz      loc_1800087CC
0x180008706  mov     edi, ebx
0x180008708  and     edi, 40h
0x18000870b  jnz     loc_180008858
0x180008711  mov     rcx, r14; lpbi
0x180008714  call    DrawDibProfileDisplay
0x180008719  mov     rcx, rax
0x18000871c  test    al, 1
0x18000871e  jz      loc_180008850
0x180008724  mov     eax, [rbp+37h+arg_10]
0x180008727  mov     r8d, [rbp+37h+nNumber]
0x18000872b  cmp     r12d, eax
0x18000872e  jnz     short loc_18000873F
0x180008730  cmp     r15d, r8d
0x180008733  jnz     short loc_18000873F
0x180008735  test    cl, 4
0x180008738  jnz     short loc_18000876D
0x18000873a  cmp     r15d, r8d
0x18000873d  jz      short loc_180008744
0x18000873f  test    cl, 10h
0x180008742  jnz     short loc_18000876D
0x180008744  cdq
0x180008745  xor     r10d, r10d
0x180008748  idiv    r12d
0x18000874b  test    edx, edx
0x18000874d  jnz     loc_180008853
0x180008753  mov     eax, r8d
0x180008756  cdq
0x180008757  idiv    r15d
0x18000875a  test    edx, edx
0x18000875c  jnz     loc_180008853
0x180008762  test    cl, 8
0x180008765  jz      loc_180008853
0x18000876b  jmp     short loc_180008770
0x18000876d  xor     r10d, r10d
0x180008770  mov     eax, [r14+10h]
0x180008774  dec     eax
0x180008776  cmp     eax, 1
0x180008779  ja      short loc_1800087AA
0x18000877b  test    r13, r13
0x18000877e  jz      loc_180008853
0x180008784  mov     rcx, r13; hDC
0x180008787  call    cs:__imp_WindowFromDC
0x18000878d  xor     r10d, r10d
0x180008790  test    rax, rax
0x180008793  jz      loc_180008853
0x180008799  lea     eax, [r10+8]
0x18000879d  cmp     cs:gwScreenBitDepth, ax
0x1800087a4  jb      loc_180008853
0x1800087aa  mov     rcx, [rsi+148h]; hic
0x1800087b1  bts     ebx, 7
0x1800087b5  mov     [rbp+37h+wFlags], ebx
0x1800087b8  test    rcx, rcx
0x1800087bb  jz      short loc_1800087C5
0x1800087bd  call    ICClose
0x1800087c2  xor     r10d, r10d
0x1800087c5  mov     [rsi+148h], r10
0x1800087cc  mov     edi, r15d
0x1800087cf  lea     rcx, [rsi+160h]
0x1800087d6  mov     r15d, r10d
0x1800087d9  movups  xmm0, xmmword ptr [rcx]
0x1800087dc  lea     rax, [rsi+5BCh]
0x1800087e3  movups  xmm1, xmmword ptr [rcx+10h]
0x1800087e7  movups  xmmword ptr [rax], xmm0
0x1800087ea  movsd   xmm0, qword ptr [rcx+20h]
0x1800087ef  movups  xmmword ptr [rax+10h], xmm1
0x1800087f3  movsd   qword ptr [rax+20h], xmm0
0x1800087f8  mov     ecx, [rsi+5C4h]
0x1800087fe  mov     eax, ecx
0x180008800  neg     eax
0x180008802  mov     [rsi+5D0h], r10d
0x180008809  cmovs   eax, ecx
0x18000880c  mov     [rsi+5C4h], eax
0x180008812  test    bl, bl
0x180008814  js      loc_180008D0B
0x18000881a  cmp     [r14+10h], r10d
0x18000881e  jnz     loc_180008D0B
0x180008824  mov     rcx, r14; lpbi
0x180008827  call    DrawDibProfileDisplay
0x18000882c  movzx   ecx, cs:gwScreenBitDepth
0x180008833  mov     r8, rax
0x180008836  mov     eax, 18h
0x18000883b  cmp     cx, ax
0x18000883e  jbe     loc_180008B42
0x180008844  lea     ecx, [rax+8]
0x180008847  movzx   r15d, cx
  ... truncated ...
```
