# EpScanGdiDci::ProcessBatch_Gdi_Batch(HDC__ *,EpScanRecord *,EpScanRecord *)

- ea: `0x1800319f0`
- end: `0x180032452`
- name: `?ProcessBatch_Gdi_Batch@EpScanGdiDci@@AEAAXPEAUHDC__@@PEAUEpScanRecord@@1@Z`
- size: `2658`
- prototype: `void(EpScanGdiDci *__hidden this, HDC, struct EpScanRecord *, struct EpScanRecord *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002fb10`

## callees

- `0x1800319f0`
- `0x180032540`
- `0x180033610`
- `0x180105d40`
- `0x18010673c`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031ce3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031ce3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031c84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031c84`
- `GDI32!StretchBlt` at `0x180031f36`
- `GDI32!StretchBlt` at `0x180032131`
- `GDI32!StretchBlt` at `0x180031f36`
- `GDI32!StretchBlt` at `0x180032131`
- `GDI32!CreateDIBSection` at `0x180031c3f`
- `GDI32!CreateDIBSection` at `0x180031c3f`
- `GDI32!SelectObject` at `0x180031c63`
- `GDI32!SelectObject` at `0x180031c63`
- `GDI32!DeleteObject` at `0x180031ad8`
- `GDI32!DeleteObject` at `0x180031ad8`
- `GDI32!GetDCOrgEx` at `0x180031a48`
- `GDI32!GetDCOrgEx` at `0x180031a48`
- `GDI32!GetDeviceCaps` at `0x180031b37`
- `GDI32!GetDeviceCaps` at `0x180031b37`

## pseudocode

```c
void __fastcall EpScanGdiDci::ProcessBatch_Gdi_Batch(
        EpScanGdiDci *this,
        HDC a2,
        struct EpScanRecord *a3,
        struct EpScanRecord *a4)
{
  struct EpScanRecord *v4; // rdi
  EpScanGdiDci *v5; // rbx
  int v6; // esi
  int v7; // r9d
  int v8; // r11d
  int v9; // r10d
  int v10; // r8d
  __int64 v11; // rsi
  int PixelFormatFromHDC; // r14d
  void *v13; // rcx
  __int64 v14; // r13
  HDC v15; // r15
  int v16; // ecx
  DWORD biCompression; // edx
  WORD biBitCount; // r8
  HBITMAP v19; // rax
  HDC v20; // rcx
  void *v21; // r8
  char *v22; // r8
  int v23; // esi
  __int64 v24; // rcx
  int v25; // r8d
  __int64 v26; // rdx
  __m128i si128; // xmm6
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r14d
  int v38; // r15d
  int v39; // esi
  unsigned int v40; // r9d
  int v41; // esi
  int v42; // edx
  int v43; // r13d
  __int64 v44; // r8
  size_t v45; // r12
  void *v46; // rsi
  __int16 v47; // ax
  char *v48; // r15
  int v49; // edx
  int v50; // r13d
  __int64 v51; // rcx
  char *v52; // r14
  char *v53; // rbx
  char *v54; // r9
  __int64 v55; // rcx
  void *v56; // rdx
  void (__fastcall *v57)(__int64, void *, _QWORD, char *); // rax
  __int64 v58; // rbx
  int v59; // ecx
  __int64 v60; // rdx
  __int64 v61; // r8
  char *v62; // r8
  __int64 v63; // rax
  unsigned int v64; // r9d
  int v65; // ecx
  char *v66; // r15
  __int64 v67; // rax
  char *v68; // rdi
  char *v69; // r14
  void *v70; // rdx
  char *v71; // r9
  __int64 v72; // rcx
  void (__fastcall *v73)(__int64, void *, _QWORD, char *); // rax
  char *v74; // rcx
  char *v75; // rdx
  char *v76; // rcx
  unsigned __int64 v77; // rax
  int v78; // edx
  int v79; // eax
  int v80; // edx
  int v81; // eax
  unsigned int v82; // r11d
  RGBQUAD *bmiColors; // r9
  __int64 v84; // r10
  int v85; // ecx
  int offset; // [rsp+28h] [rbp-D8h]
  int offseta; // [rsp+28h] [rbp-D8h]
  int xSrc; // [rsp+30h] [rbp-D0h]
  int xSrca; // [rsp+30h] [rbp-D0h]
  int ySrc; // [rsp+38h] [rbp-C8h]
  int ySrca; // [rsp+38h] [rbp-C8h]
  int wSrc[2]; // [rsp+40h] [rbp-C0h]
  int v93; // [rsp+80h] [rbp-80h]
  int v94; // [rsp+84h] [rbp-7Ch]
  int v95; // [rsp+88h] [rbp-78h]
  unsigned __int16 v96; // [rsp+88h] [rbp-78h]
  int hDest; // [rsp+8Ch] [rbp-74h]
  struct EpScanRecord *v98; // [rsp+90h] [rbp-70h]
  unsigned __int64 v99; // [rsp+90h] [rbp-70h]
  LONG v100; // [rsp+98h] [rbp-68h]
  int v101; // [rsp+9Ch] [rbp-64h]
  int v102; // [rsp+A0h] [rbp-60h]
  int v103; // [rsp+A4h] [rbp-5Ch]
  unsigned int v104; // [rsp+A8h] [rbp-58h]
  int v105; // [rsp+ACh] [rbp-54h]
  int v106; // [rsp+B0h] [rbp-50h]
  int wDest; // [rsp+B4h] [rbp-4Ch]
  int yDest; // [rsp+B8h] [rbp-48h]
  int xDest; // [rsp+BCh] [rbp-44h]
  HDC hdcDest; // [rsp+C8h] [rbp-38h]
  char *v113; // [rsp+D8h] [rbp-28h] BYREF
  char *v114; // [rsp+E0h] [rbp-20h]
  int v115; // [rsp+E8h] [rbp-18h]
  __m128i v116; // [rsp+F0h] [rbp-10h]
  int v117; // [rsp+100h] [rbp+0h]
  int v118; // [rsp+104h] [rbp+4h]
  __int64 v119; // [rsp+108h] [rbp+8h]
  struct EpScanRecord *v120; // [rsp+110h] [rbp+10h]
  BITMAPINFO pbmi; // [rsp+120h] [rbp+20h] BYREF
  int v122; // [rsp+14Ch] [rbp+4Ch]
  int v123; // [rsp+150h] [rbp+50h]

  v4 = a3;
  v98 = a3;
  v5 = this;
  v6 = *(_DWORD *)(*((_QWORD *)this + 164) + 776LL);
  v95 = v6;
  v120 = a4;
  GetDCOrgEx(a2, (LPPOINT)((char *)this + 1404));
  v7 = *((_DWORD *)v5 + 342);
  v8 = *((_DWORD *)v5 + 343);
  v9 = *((_DWORD *)v5 + 344);
  v10 = *((_DWORD *)v5 + 345);
  if ( v6 > 1 )
  {
    if ( v8 < v7 || v10 < v9 )
      return;
    v7 -= v7 % v6;
    v78 = (v8 - v7) % v6;
    v79 = 0;
    if ( v78 > 0 )
      v79 = v6 - v78;
    v8 += v79;
    v9 -= v9 % v6;
    v80 = (v10 - v9 + 1) % v6;
    v81 = 0;
    if ( v80 > 0 )
      v81 = v6 - v80;
    v10 += v81;
  }
  v11 = *((_QWORD *)v5 + 163);
  v93 = v7;
  v94 = v9;
  if ( Globals::g_fClientSession )
    PixelFormatFromHDC = *((_DWORD *)Globals::g_pRemoteSurface + 3);
  else
    PixelFormatFromHDC = 0;
  v13 = *(void **)(v11 + 16);
  v100 = v8 - v7;
  v14 = *(_QWORD *)(*((_QWORD *)v5 + 164) + 664LL);
  hDest = v10 - v9 + 1;
  if ( v13 )
    DeleteObject(v13);
  if ( !v14 )
    v14 = *(_QWORD *)(v11 + 1576);
  v15 = *(HDC *)(v11 + 1504);
  memset_0(&pbmi, 0, 0x428u);
  if ( !PixelFormatFromHDC )
    PixelFormatFromHDC = ExtractPixelFormatFromHDC(v15);
  *(_DWORD *)(v11 + 80) = PixelFormatFromHDC;
  if ( (PixelFormatFromHDC & 0x10000) != 0 )
    *(_DWORD *)(v11 + 80) = 198659;
  if ( GetDeviceCaps(v15, 2) == 2 && (*(_DWORD *)(v11 + 80) & 0x10000) != 0 || (v16 = *(_DWORD *)(v11 + 80)) == 0 )
  {
    LOBYTE(v16) = 9;
    pbmi.bmiHeader.biSize = 40;
    *(_DWORD *)(v11 + 80) = 139273;
    pbmi.bmiHeader.biHeight = 0;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    biBitCount = 32;
    goto LABEL_16;
  }
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biHeight = 0;
  pbmi.bmiHeader.biPlanes = 1;
  pbmi.bmiHeader.biBitCount = BYTE1(v16);
  biCompression = 0;
  pbmi.bmiHeader.biCompression = 0;
  biBitCount = BYTE1(v16);
  if ( (v16 & 0x10000) == 0 )
  {
    if ( (((v16 & 0xFF00) - 4096) & 0xFFFFEFFF) != 0 )
    {
LABEL_17:
      pbmi.bmiColors[0] = (RGBQUAD)dword_1801899E0[(unsigned __int8)v16];
      v122 = dword_180189990[(unsigned __int8)v16];
      v123 = dword_180189940[(unsigned __int8)v16];
      goto LABEL_18;
    }
LABEL_16:
    biCompression = 3;
    pbmi.bmiHeader.biCompression = 3;
    goto LABEL_17;
  }
  if ( v14 )
  {
    v82 = *(_DWORD *)(v14 + 4);
    bmiColors = pbmi.bmiColors;
    v84 = 0;
    if ( v82 )
    {
      do
      {
        v85 = *(_DWORD *)(v14 + 4 * v84 + 8);
        v84 = (unsigned int)(v84 + 1);
        bmiColors->rgbRed = BYTE2(v85);
        *(_WORD *)&bmiColors->rgbBlue = v85;
        ++bmiColors;
      }
      while ( (unsigned int)v84 < v82 );
      biCompression = pbmi.bmiHeader.biCompression;
      biBitCount = pbmi.bmiHeader.biBitCount;
    }
  }
LABEL_18:
  pbmi.bmiHeader.biWidth = v100;
  if ( hDest < 0 )
  {
    *(_QWORD *)(v11 + 16) = 0;
    goto LABEL_91;
  }
  pbmi.bmiHeader.biHeight = -hDest;
  if ( !biCompression )
  {
LABEL_89:
    pbmi.bmiHeader.biSizeImage = 0;
    goto LABEL_23;
  }
  if ( biBitCount != 16 )
  {
    if ( biBitCount == 32 )
    {
      pbmi.bmiHeader.biSizeImage = 4 * hDest * v100;
      goto LABEL_23;
    }
    goto LABEL_89;
  }
  pbmi.bmiHeader.biSizeImage = 2 * hDest * v100;
LABEL_23:
  *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 0;
  v19 = CreateDIBSection(v15, &pbmi, 0, (void **)(v11 + 32), 0, 0);
  *(_QWORD *)(v11 + 16) = v19;
  if ( v19 )
  {
    v20 = *(HDC *)(v11 + 24);
    *(_DWORD *)(v11 + 12) = v100;
    SelectObject(v20, v19);
    goto LABEL_25;
  }
LABEL_91:
  *(_DWORD *)(v11 + 12) = 0;
LABEL_25:
  v21 = *(void **)(v11 + 40);
  if ( v21 )
  {
    HeapFree(GpRuntime::GpMemHeap, 0, v21);
    *(_QWORD *)(v11 + 40) = 0;
  }
  if ( v100 < 0 )
  {
    v22 = 0;
    *(_QWORD *)(v11 + 40) = 0;
LABEL_32:
    *(_DWORD *)(v11 + 12) = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int64)(5LL * v100) > 0x1FFFFFFFFFFFFFFFLL )
    v22 = 0;
  else
    v22 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, 40LL * v100);
  *(_QWORD *)(v11 + 40) = v22;
  if ( !v22 )
    goto LABEL_32;
  v74 = &v22[8 * v100];
  *(_QWORD *)(v11 + 48) = v74;
  v75 = &v74[8 * v100];
  v76 = &v75[8 * v100];
  *(_QWORD *)(v11 + 56) = v75;
  *(_QWORD *)(v11 + 64) = v76;
  *(_QWORD *)(v11 + 72) = &v76[8 * v100];
LABEL_33:
  v119 = *(_QWORD *)(v11 + 32);
  hdcDest = *(HDC *)(v11 + 24);
  if ( v5 != (EpScanGdiDci *)-1328LL )
  {
    *((_QWORD *)v5 + 166) = v22;
    *((_QWORD *)v5 + 167) = *(_QWORD *)(v11 + 48);
    *((_QWORD *)v5 + 168) = *(_QWORD *)(v11 + 56);
    *((_QWORD *)v5 + 169) = *(_QWORD *)(v11 + 64);
    *((_QWORD *)v5 + 170) = *(_QWORD *)(v11 + 72);
  }
  if ( *(_DWORD *)(v11 + 12) )
  {
    v23 = *(_DWORD *)(v11 + 80);
    if ( v23 )
    {
      v24 = *((_QWORD *)v5 + 164);
      v25 = *((_DWORD *)v5 + 355);
      v26 = *(_QWORD *)(v24 + 664);
      if ( !v26 )
        v26 = *(_QWORD *)(*((_QWORD *)v5 + 163) + 1576LL);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v28 = *((unsigned int *)v5 + 162);
      v113 = (char *)v5 + 168;
      *(_QWORD *)wSrc = v26;
      v29 = *((unsigned int *)v5 + 163);
      ySrc = *(_DWORD *)(v24 + 44);
      xSrc = *(_DWORD *)(v24 + 32);
      offset = *(_DWORD *)(v24 + 28);
      v30 = *(_QWORD *)(v24 + 672);
      v114 = (char *)v5 + 1328;
      v116 = si128;
      v115 = 0;
      v117 = 1;
      v118 = 2;
      EpAlphaBlender::BuildPipeline(
        (char *)v5 + 24,
        v29,
        (unsigned int)v23,
        v28,
        v30,
        offset,
        xSrc,
        ySrc,
        *(_QWORD *)wSrc,
        (char *)v5 + 1328,
        1,
        1,
        v25,
        &v113,
        1);
      *((_QWORD *)v113 - 1) = 0;
      v31 = *((_QWORD *)v5 + 164);
      v32 = *((_DWORD *)v5 + 355);
      v33 = *(_QWORD *)(v31 + 664);
      if ( !v33 )
        v33 = *(_QWORD *)(*((_QWORD *)v5 + 163) + 1576LL);
      v34 = *((unsigned int *)v5 + 320);
      v113 = (char *)v5 + 800;
      ySrca = *(_DWORD *)(v31 + 44);
      xSrca = *(_DWORD *)(v31 + 32);
      offseta = *(_DWORD *)(v31 + 28);
      v35 = *(_QWORD *)(v31 + 672);
      v36 = *((unsigned int *)v5 + 321);
      v114 = (char *)v5 + 1328;
      v116 = si128;
      v115 = 0;
      v117 = 1;
      v118 = 2;
      EpAlphaBlender::BuildPipeline(
        (char *)v5 + 656,
        v36,
        (unsigned int)v23,
        v34,
        v35,
        offseta,
        xSrca,
        ySrca,
        v33,
        (char *)v5 + 1328,
        1,
        1,
        v32,
        &v113,
        1);
      v37 = v93;
      *((_QWORD *)v113 - 1) = 0;
      v38 = v94;
      v102 = *((_DWORD *)v5 + 4);
      v103 = *((_DWORD *)v5 + 5);
      v106 = hDest / v95;
      wDest = v100 / v95;
      yDest = v94 / v95;
      xDest = v93 / v95;
      StretchBlt(hdcDest, 0, 0, v100, hDest, a2, v93 / v95, v94 / v95, v100 / v95, hDest / v95, 0xCC0020u);
      v39 = v23 >> 8;
      if ( (_BYTE)v39 )
      {
        if ( v100 <= 0x7FFFFFF8u / (unsigned __int8)v39 )
        {
          v40 = (((v100 * (unsigned int)(unsigned __int8)v39 + 7) >> 3) + 3) & 0xFFFFFFFC;
          v104 = v40;
          if ( v40 )
          {
            v41 = (unsigned __int8)(v39 & 0xF8) >> 3;
            v105 = v41;
            while ( 1 )
            {
              v42 = *((_DWORD *)v5 + 354) + *((_DWORD *)v4 + 2);
              v43 = *((_DWORD *)v5 + 353) + *((_DWORD *)v4 + 1);
              v44 = *(unsigned __int16 *)v4;
              v45 = *((int *)v4 + 3);
              v96 = *(_WORD *)v4;
              v101 = v42;
              v46 = (void *)(v40 * (v42 - v38) + v119 + (unsigned int)((v43 - v37) * v41));
              v47 = *((_WORD *)v4 + 1);
              if ( v47 != 1 )
                break;
              v58 = *(unsigned __int16 *)v4;
              if ( (_DWORD)v45 )
              {
                v66 = (char *)v4 + 24;
                v67 = 632 * v44;
                if ( !*((_DWORD *)this + 158 * v44 + 32) )
                  *(_QWORD *)((char *)this + v67 + 96) = v66;
                v68 = (char *)this + v67;
                *(_QWORD *)((char *)this + v67 + 72) = 0;
                v69 = (char *)this + v67 + 168;
                *(_DWORD *)((char *)this + v67 + 56) = v43 - v102;
                *(_DWORD *)((char *)this + v67 + 60) = v42 - v103;
                while ( 1 )
                {
                  v70 = (void *)*((_QWORD *)v69 + 1);
                  v71 = v68 + 32;
                  v72 = *((_QWORD *)v69 + 2);
                  v73 = *(void (__fastcall **)(__int64, void *, _QWORD, char *))v69;
                  if ( v70 == (void *)1 )
                    v70 = v66;
                  if ( !v70 )
                    v70 = v46;
                  if ( !v72 )
                    break;
                  v73(v72, v70, (unsigned int)v45, v71);
                  v69 += 24;
                }
                v73((__int64)v46, v70, (unsigned int)v45, v71);
                v4 = v98;
                goto LABEL_62;
              }
LABEL_63:
              v59 = *((unsigned __int16 *)v4 + 1);
              v60 = *((int *)v4 + 3);
              if ( v59 == 3 )
              {
                v5 = this;
                v61 = v60 + 20;
              }
              else
              {
                v63 = 632 * v58;
                v5 = this;
                v62 = 0;
                v64 = ((*(int *)((char *)this + v63 + 648) >> 8) & 0xF8u) >> 3;
                if ( *((_WORD *)v4 + 1) )
                {
                  v65 = v59 - 1;
                  if ( v65 )
                  {
                    if ( v65 == 1 )
                      v62 = (char *)(v60
                                   + (((unsigned __int64)v4 + (int)(*((_DWORD *)v4 + 4) * v64) + 27)
                                    & 0xFFFFFFFFFFFFFFFCuLL));
                    goto LABEL_66;
                  }
                }
                v61 = (int)(v64 * v60) + 24LL;
              }
              v62 = (char *)v4 + v61;
LABEL_66:
              v40 = v104;
              v41 = v105;
              v4 = (struct EpScanRecord *)((unsigned __int64)(v62 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
              v98 = v4;
              if ( v4 >= v120 )
              {
                StretchBlt(a2, xDest, yDest, wDest, v106, hdcDest, 0, 0, v100, hDest, 0xCC0020u);
                return;
              }
            }
            if ( v47 == 3 )
            {
              v48 = 0;
            }
            else
            {
              v48 = (char *)v4 + 24;
              if ( v47 == 2 )
              {
                v77 = ((unsigned __int64)v4
                     + (int)(*((_DWORD *)v4 + 4) * (((*((int *)v5 + 162) >> 8) & 0xF8u) >> 3))
                     + 27)
                    & 0xFFFFFFFFFFFFFFFCuLL;
                goto LABEL_87;
              }
            }
            v99 = 0;
            if ( v47 != 3 )
            {
LABEL_49:
              if ( (*(_DWORD *)(*((_QWORD *)v5 + 165) + 12LL) & 0xFF00u) < 0x800 )
              {
                memset_0(v46, 0, v45);
                v42 = v101;
              }
              if ( (_DWORD)v45 )
              {
                v49 = v42 - *((_DWORD *)v5 + 5);
                v50 = v43 - *((_DWORD *)v5 + 4);
                v51 = 632LL * *(unsigned __int16 *)v4;
                if ( !*(_DWORD *)((char *)v5 + v51 + 128) )
                  *(_QWORD *)((char *)v5 + v51 + 96) = v48;
                v52 = (char *)v5 + v51;
                *(_DWORD *)((char *)v5 + v51 + 56) = v50;
                *(_DWORD *)((char *)v5 + v51 + 60) = v49;
                v53 = (char *)v5 + v51 + 168;
                *((_QWORD *)v52 + 9) = v99;
                while ( 1 )
                {
                  v54 = v52 + 32;
                  v55 = *((_QWORD *)v53 + 2);
                  v56 = v48;
                  if ( *((_QWORD *)v53 + 1) != 1 )
                    v56 = (void *)*((_QWORD *)v53 + 1);
                  v57 = *(void (__fastcall **)(__int64, void *, _QWORD, char *))v53;
                  if ( !v56 )
                    v56 = v46;
                  if ( !v55 )
                    break;
                  v57(v55, v56, (unsigned int)v45, v54);
                  v53 += 24;
                }
                v57((__int64)v46, v56, (unsigned int)v45, v54);
              }
              v58 = v96;
LABEL_62:
              v38 = v94;
              v37 = v93;
              goto LABEL_63;
            }
            v77 = (unsigned __int64)v4 + 20;
LABEL_87:
            v99 = v77;
            goto LABEL_49;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800319f0  push    rbp
0x1800319f2  push    rbx
0x1800319f3  push    rsi
0x1800319f4  push    rdi
0x1800319f5  lea     rbp, [rsp-488h]
0x1800319fd  sub     rsp, 588h
0x180031a04  mov     rax, cs:__security_cookie
0x180031a0b  xor     rax, rsp
0x180031a0e  mov     [rbp+4A0h+var_50], rax
0x180031a15  mov     rax, [rcx+520h]
0x180031a1c  mov     rdi, r8
0x180031a1f  mov     [rbp+4A0h+var_510], r8
0x180031a23  mov     rbx, rcx
0x180031a26  mov     r8, rdx
0x180031a29  mov     [rbp+4A0h+hdcSrc], rdx
0x180031a2d  mov     [rbp+4A0h+var_4E0], rcx
0x180031a31  lea     rdx, [rcx+57Ch]; lppt
0x180031a38  mov     esi, [rax+308h]
0x180031a3e  mov     rcx, r8; hdc
0x180031a41  mov     [rbp+4A0h+var_518], esi
0x180031a44  mov     [rbp+4A0h+var_490], r9
0x180031a48  call    cs:__imp_GetDCOrgEx
0x180031a4f  nop     dword ptr [rax+rax+00h]
0x180031a54  mov     r9d, [rbx+558h]
0x180031a5b  mov     r11d, [rbx+55Ch]
0x180031a62  mov     r10d, [rbx+560h]
0x180031a69  mov     r8d, [rbx+564h]
0x180031a70  cmp     esi, 1
0x180031a73  jg      loc_180032321
0x180031a79  cmp     cs:?g_fClientSession@Globals@@3HA, 0; int Globals::g_fClientSession
0x180031a80  mov     rsi, [rbx+518h]
0x180031a87  mov     [rsp+5A0h+var_20], r13
0x180031a8f  mov     [rsp+5A0h+var_28], r14
0x180031a97  mov     [rsp+5A0h+var_30], r15
0x180031a9f  mov     [rbp+4A0h+var_520], r9d
0x180031aa3  mov     [rbp+4A0h+var_51C], r10d
0x180031aa7  jnz     loc_1800323B6
0x180031aad  xor     r14d, r14d
0x180031ab0  mov     rax, [rbx+520h]
0x180031ab7  sub     r8d, r10d
0x180031aba  mov     rcx, [rsi+10h]; ho
0x180031abe  sub     r11d, r9d
0x180031ac1  mov     [rbp+4A0h+var_508], r11d
0x180031ac5  mov     r13, [rax+298h]
0x180031acc  lea     eax, [r8+1]
0x180031ad0  mov     [rbp+4A0h+hDest], eax
0x180031ad3  test    rcx, rcx
0x180031ad6  jz      short loc_180031AE4
0x180031ad8  call    cs:__imp_DeleteObject
0x180031adf  nop     dword ptr [rax+rax+00h]
0x180031ae4  test    r13, r13
0x180031ae7  jnz     short loc_180031AF0
0x180031ae9  mov     r13, [rsi+628h]
0x180031af0  mov     r15, [rsi+5E0h]
0x180031af7  lea     rcx, [rbp+4A0h+pbmi]; void *
0x180031afb  xor     edx, edx; Val
0x180031afd  mov     r8d, 428h; Size
0x180031b03  call    memset_0
0x180031b08  test    r14d, r14d
0x180031b0b  jnz     short loc_180031B18
0x180031b0d  mov     rcx, r15; hdc
0x180031b10  call    ?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z; ExtractPixelFormatFromHDC(HDC__ *)
0x180031b15  mov     r14d, eax
0x180031b18  mov     [rsi+50h], r14d
0x180031b1c  bt      r14d, 10h
0x180031b21  jb      loc_1800323C6
0x180031b27  mov     edx, 2; index
0x180031b2c  mov     [rsp+5A0h+arg_18], r12
0x180031b34  mov     rcx, r15; hdc
0x180031b37  call    cs:__imp_GetDeviceCaps
0x180031b3e  nop     dword ptr [rax+rax+00h]
0x180031b43  cmp     eax, 2
0x180031b46  jz      loc_18003237A
0x180031b4c  mov     ecx, [rsi+50h]
0x180031b4f  test    ecx, ecx
0x180031b51  jz      loc_180032387
0x180031b57  xor     r11d, r11d
0x180031b5a  mov     [rbp+4A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180031b61  mov     edx, 0FFh
0x180031b66  mov     [rbp+4A0h+pbmi.bmiHeader.biHeight], r11d
0x180031b6a  mov     eax, ecx
0x180031b6c  mov     r12d, 1
0x180031b72  sar     eax, 8
0x180031b75  and     ax, dx
0x180031b78  mov     [rbp+4A0h+pbmi.bmiHeader.biPlanes], r12w
0x180031b7d  mov     [rbp+4A0h+pbmi.bmiHeader.biBitCount], ax
0x180031b81  mov     edx, r11d
0x180031b84  mov     [rbp+4A0h+pbmi.bmiHeader.biCompression], edx
0x180031b87  movzx   r8d, ax
0x180031b8b  bt      ecx, 10h
0x180031b8f  jb      loc_1800323D2
0x180031b95  mov     eax, ecx
0x180031b97  and     eax, 0FF00h
0x180031b9c  sub     eax, 1000h
0x180031ba1  test    eax, 0FFFFEFFFh
0x180031ba6  jnz     short loc_180031BB0
0x180031ba8  mov     edx, 3
0x180031bad  mov     [rbp+4A0h+pbmi.bmiHeader.biCompression], edx
0x180031bb0  movzx   ecx, cl
0x180031bb3  lea     r9, __ImageBase
0x180031bba  mov     eax, ds:rva dword_1801899E0[r9+rcx*4]
0x180031bc2  mov     dword ptr [rbp+4A0h+pbmi.bmiColors.rgbBlue], eax
0x180031bc5  mov     eax, ds:rva dword_180189990[r9+rcx*4]
0x180031bcd  mov     [rbp+4A0h+var_454], eax
0x180031bd0  mov     eax, ds:rva dword_180189940[r9+rcx*4]
0x180031bd8  mov     [rbp+4A0h+var_450], eax
0x180031bdb  movsxd  r13, [rbp+4A0h+var_508]
0x180031bdf  mov     ecx, [rbp+4A0h+hDest]
0x180031be2  mov     [rbp+4A0h+pbmi.bmiHeader.biWidth], r13d
0x180031be6  test    ecx, ecx
0x180031be8  js      loc_1800322EC
0x180031bee  mov     eax, ecx
0x180031bf0  lea     r9, [rsi+20h]; ppvBits
0x180031bf4  neg     eax
0x180031bf6  mov     [rbp+4A0h+pbmi.bmiHeader.biHeight], eax
0x180031bf9  test    edx, edx
0x180031bfb  jz      loc_1800322E3
0x180031c01  cmp     r8w, 10h
0x180031c06  jz      loc_180032421
0x180031c0c  cmp     r8w, 20h ; ' '
0x180031c11  jnz     loc_1800322E3
0x180031c17  mov     eax, r13d
0x180031c1a  imul    eax, ecx
0x180031c1d  shl     eax, 2
0x180031c20  mov     [rbp+4A0h+pbmi.bmiHeader.biSizeImage], eax
0x180031c23  mov     [rsp+5A0h+offset], r11d; offset
0x180031c28  lea     rdx, [rbp+4A0h+pbmi]; pbmi
0x180031c2c  xor     r8d, r8d; usage
0x180031c2f  mov     [rsp+5A0h+hSection], r11; hSection
0x180031c34  mov     rcx, r15; hdc
0x180031c37  mov     qword ptr [rbp+4A0h+pbmi.bmiHeader.biClrUsed], 0
0x180031c3f  call    cs:__imp_CreateDIBSection
0x180031c46  nop     dword ptr [rax+rax+00h]
0x180031c4b  mov     [rsi+10h], rax
0x180031c4f  test    rax, rax
0x180031c52  jz      loc_180032431
0x180031c58  mov     rcx, [rsi+18h]; hdc
0x180031c5c  mov     rdx, rax; h
0x180031c5f  mov     [rsi+0Ch], r13d
0x180031c63  call    cs:__imp_SelectObject
0x180031c6a  nop     dword ptr [rax+rax+00h]
0x180031c6f  xor     r11d, r11d
0x180031c72  mov     r8, [rsi+28h]; lpMem
0x180031c76  test    r8, r8
0x180031c79  jz      short loc_180031C97
0x180031c7b  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180031c82  xor     edx, edx; dwFlags
0x180031c84  call    cs:__imp_HeapFree
0x180031c8b  nop     dword ptr [rax+rax+00h]
0x180031c90  xor     r11d, r11d
0x180031c93  mov     [rsi+28h], r11
0x180031c97  test    r13d, r13d
0x180031c9a  js      short loc_180031CAB
0x180031c9c  mov     rax, 3333333333333333h
0x180031ca6  cmp     r13, rax
0x180031ca9  jbe     short loc_180031CB4
0x180031cab  mov     r8, r11
0x180031cae  mov     [rsi+28h], r11
0x180031cb2  jmp     short loc_180031D02
0x180031cb4  lea     r8, ds:0[r13*4]
0x180031cbc  mov     rax, 1FFFFFFFFFFFFFFFh
0x180031cc6  add     r8, r13
0x180031cc9  cmp     r8, rax
0x180031ccc  ja      loc_180032439
0x180031cd2  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180031cd9  lea     r8, ds:0[r8*8]; dwBytes
0x180031ce1  xor     edx, edx; dwFlags
0x180031ce3  call    cs:__imp_HeapAlloc
0x180031cea  nop     dword ptr [rax+rax+00h]
0x180031cef  mov     r8, rax
0x180031cf2  xor     r11d, r11d
0x180031cf5  mov     [rsi+28h], r8
0x180031cf9  test    r8, r8
0x180031cfc  jnz     loc_180032285
0x180031d02  mov     [rsi+0Ch], r11d
0x180031d06  mov     rax, [rsi+20h]
0x180031d0a  lea     r14, [rbx+530h]
0x180031d11  mov     [rbp+4A0h+var_498], rax
0x180031d15  mov     rax, [rsi+18h]
0x180031d19  mov     [rbp+4A0h+hdcDest], rax
0x180031d1d  test    r14, r14
0x180031d20  jnz     loc_1800322F9
0x180031d26  cmp     dword ptr [rsi+0Ch], 0
0x180031d2a  jz      loc_18003213D
0x180031d30  mov     esi, [rsi+50h]
0x180031d33  test    esi, esi
0x180031d35  jz      loc_18003213D
0x180031d3b  mov     rcx, [rbx+520h]
0x180031d42  mov     r8d, [rbx+58Ch]
0x180031d49  movaps  [rsp+5A0h+var_40], xmm6
0x180031d51  mov     rdx, [rcx+298h]
0x180031d58  test    rdx, rdx
0x180031d5b  jnz     short loc_180031D6B
0x180031d5d  mov     rax, [rbx+518h]
0x180031d64  mov     rdx, [rax+628h]
0x180031d6b  movdqa  xmm6, cs:__xmm@00000000000000010000000000000000
0x180031d73  lea     rax, [rbx+0A8h]
0x180031d7a  mov     r9d, [rbx+288h]
0x180031d81  mov     [rsp+5A0h+var_530], r12d
0x180031d86  mov     [rbp+4A0h+var_4C8], rax
0x180031d8a  lea     rax, [rbp+4A0h+var_4C8]
0x180031d8e  mov     [rsp+5A0h+var_538], rax
0x180031d93  mov     eax, [rcx+2Ch]
0x180031d96  mov     [rsp+5A0h+var_540], r8d
0x180031d9b  mov     r8d, esi
0x180031d9e  mov     [rsp+5A0h+var_548], r12d
0x180031da3  mov     [rsp+5A0h+rop], r12d
0x180031da8  mov     qword ptr [rsp+5A0h+hSrc], r14
0x180031dad  mov     qword ptr [rsp+5A0h+wSrc], rdx
0x180031db2  mov     edx, [rbx+28Ch]
0x180031db8  mov     [rsp+5A0h+ySrc], eax
0x180031dbc  mov     eax, [rcx+20h]
0x180031dbf  mov     [rsp+5A0h+xSrc], eax
0x180031dc3  mov     eax, [rcx+1Ch]
0x180031dc6  mov     [rsp+5A0h+offset], eax
0x180031dca  mov     rax, [rcx+2A0h]
0x180031dd1  lea     rcx, [rbx+18h]
0x180031dd5  mov     [rsp+5A0h+hSection], rax
0x180031dda  mov     [rbp+4A0h+var_4C0], r14
0x180031dde  movdqu  [rbp+4A0h+var_4B0], xmm6
0x180031de3  mov     [rbp+4A0h+var_4B8], r11d
0x180031de7  mov     [rbp+4A0h+var_4A0], r12d
0x180031deb  mov     [rbp+4A0h+var_49C], 2
0x180031df2  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x180031df7  mov     rax, [rbp+4A0h+var_4C8]
0x180031dfb  xor     r15d, r15d
0x180031dfe  mov     [rax-8], r15
0x180031e02  mov     rdx, [rbx+520h]
0x180031e09  mov     r8d, [rbx+58Ch]
0x180031e10  mov     rcx, [rdx+298h]
0x180031e17  test    rcx, rcx
0x180031e1a  jnz     short loc_180031E2A
0x180031e1c  mov     rax, [rbx+518h]
0x180031e23  mov     rcx, [rax+628h]
0x180031e2a  mov     r9d, [rbx+500h]
0x180031e31  lea     rax, [rbx+320h]
0x180031e38  mov     [rsp+5A0h+var_530], r12d
0x180031e3d  mov     [rbp+4A0h+var_4C8], rax
0x180031e41  lea     rax, [rbp+4A0h+var_4C8]
0x180031e45  mov     [rsp+5A0h+var_538], rax
0x180031e4a  mov     eax, [rdx+2Ch]
0x180031e4d  mov     [rsp+5A0h+var_540], r8d
0x180031e52  mov     r8d, esi
0x180031e55  mov     [rsp+5A0h+var_548], r12d
0x180031e5a  mov     [rsp+5A0h+rop], r12d
0x180031e5f  mov     qword ptr [rsp+5A0h+hSrc], r14
0x180031e64  mov     qword ptr [rsp+5A0h+wSrc], rcx
0x180031e69  lea     rcx, [rbx+290h]
0x180031e70  mov     [rsp+5A0h+ySrc], eax
0x180031e74  mov     eax, [rdx+20h]
0x180031e77  mov     [rsp+5A0h+xSrc], eax
0x180031e7b  mov     eax, [rdx+1Ch]
0x180031e7e  mov     [rsp+5A0h+offset], eax
0x180031e82  mov     rax, [rdx+2A0h]
0x180031e89  mov     edx, [rbx+504h]
0x180031e8f  mov     [rsp+5A0h+hSection], rax
0x180031e94  mov     [rbp+4A0h+var_4C0], r14
0x180031e98  movdqu  [rbp+4A0h+var_4B0], xmm6
0x180031e9d  mov     [rbp+4A0h+var_4B8], r15d
0x180031ea1  mov     [rbp+4A0h+var_4A0], r12d
0x180031ea5  mov     [rbp+4A0h+var_49C], 2
0x180031eac  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x180031eb1  mov     ecx, [rbp+4A0h+var_518]
0x180031eb4  mov     r8d, [rbp+4A0h+hDest]
0x180031eb8  mov     rax, [rbp+4A0h+var_4C8]
0x180031ebc  mov     r14d, [rbp+4A0h+var_520]
0x180031ec0  mov     [rsp+5A0h+rop], 0CC0020h; rop
0x180031ec8  mov     [rax-8], r15
0x180031ecc  mov     eax, [rbx+10h]
0x180031ecf  mov     r15d, [rbp+4A0h+var_51C]
0x180031ed3  mov     [rbp+4A0h+var_500], eax
0x180031ed6  mov     eax, [rbx+14h]
0x180031ed9  mov     [rbp+4A0h+var_4FC], eax
0x180031edc  mov     eax, r8d
0x180031edf  cdq
0x180031ee0  idiv    ecx
0x180031ee2  mov     r9d, eax
0x180031ee5  mov     [rbp+4A0h+var_4F0], eax
0x180031ee8  mov     eax, r13d
0x180031eeb  mov     [rsp+5A0h+hSrc], r9d; hSrc
0x180031ef0  cdq
0x180031ef1  mov     r9d, r13d; wDest
0x180031ef4  idiv    ecx
0x180031ef6  mov     r10d, eax
0x180031ef9  mov     [rbp+4A0h+wDest], eax
0x180031efc  mov     eax, r15d
0x180031eff  mov     [rsp+5A0h+wSrc], r10d; wSrc
0x180031f04  cdq
0x180031f05  idiv    ecx
0x180031f07  mov     r11d, eax
0x180031f0a  mov     [rbp+4A0h+yDest], eax
0x180031f0d  mov     [rsp+5A0h+ySrc], r11d; ySrc
0x180031f12  mov     eax, r14d
0x180031f15  cdq
0x180031f16  idiv    ecx
0x180031f18  mov     rcx, [rbp+4A0h+hdcDest]; hdcDest
0x180031f1c  xor     edx, edx; xDest
0x180031f1e  mov     [rsp+5A0h+xSrc], eax; xSrc
0x180031f22  mov     [rbp+4A0h+xDest], eax
0x180031f25  mov     rax, [rbp+4A0h+hdcSrc]
  ... truncated ...
```
