# EpScanGdiDci::ProcessBatch_Gdi_Batch(HDC__ *,EpScanRecord *,EpScanRecord *)

- ea: `0x180017060`
- end: `0x180017af8`
- name: `?ProcessBatch_Gdi_Batch@EpScanGdiDci@@AEAAXPEAUHDC__@@PEAUEpScanRecord@@1@Z`
- size: `2712`
- prototype: `void(EpScanGdiDci *__hidden this, HDC, struct EpScanRecord *, struct EpScanRecord *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017f74`

## callees

- `0x180016660`
- `0x180017060`
- `0x180017d40`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017355`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017355`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172fa`
- `GDI32!StretchBlt` at `0x1800175b3`
- `GDI32!StretchBlt` at `0x1800177f0`
- `GDI32!StretchBlt` at `0x1800175b3`
- `GDI32!StretchBlt` at `0x1800177f0`
- `GDI32!CreateDIBSection` at `0x1800172b5`
- `GDI32!CreateDIBSection` at `0x1800172b5`
- `GDI32!SelectObject` at `0x1800172d9`
- `GDI32!SelectObject` at `0x1800172d9`
- `GDI32!DeleteObject` at `0x180017151`
- `GDI32!DeleteObject` at `0x180017151`
- `GDI32!GetDCOrgEx` at `0x1800170b1`
- `GDI32!GetDCOrgEx` at `0x1800170b1`
- `GDI32!GetDeviceCaps` at `0x1800171ab`
- `GDI32!GetDeviceCaps` at `0x1800171ab`

## pseudocode

```c
void __fastcall EpScanGdiDci::ProcessBatch_Gdi_Batch(
        EpScanGdiDci *this,
        HDC a2,
        struct EpScanRecord *a3,
        struct EpScanRecord *a4)
{
  __int64 v4; // rax
  int v7; // edi
  int v8; // ecx
  int v9; // r10d
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rsi
  int PixelFormatFromHDC; // edi
  LONG v14; // r14d
  int v15; // r12d
  void *v16; // rcx
  __int64 v17; // r13
  HDC v18; // r13
  int v19; // edx
  int v20; // ecx
  DWORD biCompression; // r8d
  WORD biBitCount; // r9
  HBITMAP v23; // rax
  HDC v24; // rcx
  void *v25; // r8
  char *v26; // r8
  HDC v27; // r13
  int v28; // r12d
  __int64 v29; // rcx
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rdx
  int v36; // r9d
  __int64 v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // r12d
  unsigned int v42; // esi
  unsigned int v43; // esi
  int v44; // r12d
  int v45; // r11d
  int v46; // r8d
  int v47; // r10d
  int v48; // r9d
  size_t v49; // r13
  char *v50; // rsi
  __int16 v51; // ax
  char *v52; // r14
  int v53; // r12d
  int v54; // edi
  int v55; // edi
  int v56; // r12d
  __int64 v57; // rcx
  char *v58; // rdi
  char *v59; // r12
  char *v60; // r9
  __int64 v61; // rcx
  char *v62; // rdx
  __int64 v63; // r8
  void (__fastcall *v64)(__int64, char *, __int64, char *); // rax
  int v65; // r9d
  __int64 v66; // r8
  char *v67; // rcx
  unsigned int v68; // edx
  __int64 v69; // rcx
  __int64 v70; // rcx
  char *v71; // r12
  char *v72; // rdi
  __int64 v73; // rcx
  int v74; // r9d
  __int64 v75; // rdx
  char *v76; // rcx
  int v77; // edx
  int v78; // eax
  int v79; // edx
  int v80; // eax
  unsigned int v81; // ecx
  BYTE *p_rgbGreen; // rdx
  __int64 v83; // r9
  int *v84; // r8
  int v85; // ecx
  unsigned int v86; // eax
  int offset; // [rsp+28h] [rbp-D8h]
  int offseta; // [rsp+28h] [rbp-D8h]
  int xSrc; // [rsp+30h] [rbp-D0h]
  int xSrca; // [rsp+30h] [rbp-D0h]
  int ySrc; // [rsp+38h] [rbp-C8h]
  int ySrca; // [rsp+38h] [rbp-C8h]
  int wSrc[2]; // [rsp+40h] [rbp-C0h]
  int v94; // [rsp+60h] [rbp-A0h]
  int v95; // [rsp+60h] [rbp-A0h]
  int v96; // [rsp+80h] [rbp-80h]
  int v97; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v98; // [rsp+88h] [rbp-78h]
  int v99; // [rsp+8Ch] [rbp-74h]
  int v100; // [rsp+90h] [rbp-70h]
  int v101; // [rsp+94h] [rbp-6Ch]
  __int64 v102; // [rsp+98h] [rbp-68h]
  char *v103; // [rsp+98h] [rbp-68h]
  int v104; // [rsp+A0h] [rbp-60h]
  int v105; // [rsp+A4h] [rbp-5Ch]
  int v106; // [rsp+A8h] [rbp-58h]
  unsigned int v107; // [rsp+ACh] [rbp-54h]
  char *v109; // [rsp+B8h] [rbp-48h] BYREF
  char *v110; // [rsp+C0h] [rbp-40h]
  int v111; // [rsp+C8h] [rbp-38h]
  __m128i si128; // [rsp+D0h] [rbp-30h]
  int v113; // [rsp+E0h] [rbp-20h]
  int v114; // [rsp+E4h] [rbp-1Ch]
  __int64 v115; // [rsp+E8h] [rbp-18h]
  struct EpScanRecord *v116; // [rsp+F0h] [rbp-10h]
  HDC v117; // [rsp+F8h] [rbp-8h]
  BITMAPINFO pbmi; // [rsp+100h] [rbp+0h] BYREF
  int v119; // [rsp+12Ch] [rbp+2Ch]
  int v120; // [rsp+130h] [rbp+30h]

  v4 = *((_QWORD *)this + 164);
  v116 = a4;
  v7 = *(_DWORD *)(v4 + 776);
  v104 = v7;
  GetDCOrgEx(a2, (LPPOINT)((char *)this + 1404));
  v8 = *((_DWORD *)this + 342);
  v9 = *((_DWORD *)this + 343);
  v10 = *((_DWORD *)this + 344);
  v11 = *((_DWORD *)this + 345);
  v96 = v8;
  v101 = v9;
  v97 = v10;
  v100 = v11;
  if ( v7 > 1 )
  {
    if ( v9 < v8 || v11 < v10 )
      return;
    v96 = v8 - v8 % v7;
    v77 = (v9 - v96) % v7;
    v78 = 0;
    if ( v77 > 0 )
      v78 = v7 - v77;
    v9 += v78;
    v101 = v9;
    v10 -= v10 % v7;
    v97 = v10;
    v79 = (v11 - v10 + 1) % v7;
    v80 = 0;
    if ( v79 > 0 )
      v80 = v7 - v79;
    v8 -= v8 % v7;
    v11 += v80;
    v100 = v11;
  }
  v12 = *((_QWORD *)this + 163);
  if ( Globals::g_fClientSession )
    PixelFormatFromHDC = *((_DWORD *)Globals::g_pRemoteSurface + 3);
  else
    PixelFormatFromHDC = 0;
  v14 = v9 - v8;
  v15 = v11 - v10 + 1;
  v16 = *(void **)(v12 + 16);
  v17 = *(_QWORD *)(*((_QWORD *)this + 164) + 664LL);
  v102 = v17;
  if ( v16 )
    DeleteObject(v16);
  if ( !v17 )
    v102 = *(_QWORD *)(v12 + 1576);
  v18 = *(HDC *)(v12 + 1504);
  memset_0(&pbmi, 0, 0x428u);
  if ( !PixelFormatFromHDC )
    PixelFormatFromHDC = ExtractPixelFormatFromHDC(v18);
  *(_DWORD *)(v12 + 80) = PixelFormatFromHDC;
  if ( (PixelFormatFromHDC & 0x10000) != 0 )
    *(_DWORD *)(v12 + 80) = 198659;
  if ( GetDeviceCaps(v18, 2) == 2 && (*(_DWORD *)(v12 + 80) & 0x10000) != 0 || (v19 = *(_DWORD *)(v12 + 80)) == 0 )
  {
    pbmi.bmiHeader.biSize = 40;
    LOBYTE(v19) = 9;
    pbmi.bmiHeader.biHeight = 0;
    *(_DWORD *)(v12 + 80) = 139273;
    biCompression = 0;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    LOBYTE(v20) = 32;
    biBitCount = 32;
    goto LABEL_15;
  }
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biHeight = 0;
  HIWORD(pbmi.bmiHeader.biCompression) = 0;
  v20 = v19 >> 8;
  pbmi.bmiHeader.biPlanes = 1;
  biCompression = 0;
  *(_DWORD *)&pbmi.bmiHeader.biBitCount = BYTE1(v19);
  biBitCount = BYTE1(v19);
  if ( (v19 & 0x10000) == 0 )
  {
LABEL_15:
    if ( (((unsigned __int8)v20 - 16) & 0xFFFFFFEF) == 0 )
    {
      biCompression = 3;
      pbmi.bmiHeader.biCompression = 3;
    }
    pbmi.bmiColors[0] = (RGBQUAD)dword_18018BAA0[(unsigned __int8)v19];
    v119 = dword_18018BA50[(unsigned __int8)v19];
    v120 = dword_18018BA00[(unsigned __int8)v19];
    goto LABEL_18;
  }
  if ( v102 )
  {
    v81 = *(_DWORD *)(v102 + 4);
    if ( v81 )
    {
      p_rgbGreen = &pbmi.bmiColors[0].rgbGreen;
      v83 = v81;
      v84 = (int *)(v102 + 8);
      do
      {
        v85 = *v84;
        v86 = HIWORD(*v84++);
        p_rgbGreen[1] = v86;
        *(_WORD *)(p_rgbGreen - 1) = v85;
        p_rgbGreen += 4;
        --v83;
      }
      while ( v83 );
      biCompression = pbmi.bmiHeader.biCompression;
      biBitCount = pbmi.bmiHeader.biBitCount;
    }
  }
LABEL_18:
  pbmi.bmiHeader.biWidth = v14;
  if ( v15 < 0 )
  {
    *(_QWORD *)(v12 + 16) = 0;
    goto LABEL_86;
  }
  pbmi.bmiHeader.biHeight = -v15;
  if ( !biCompression )
  {
LABEL_84:
    pbmi.bmiHeader.biSizeImage = 0;
    goto LABEL_23;
  }
  if ( biBitCount != 16 )
  {
    if ( biBitCount == 32 )
    {
      pbmi.bmiHeader.biSizeImage = 4 * v15 * v14;
      goto LABEL_23;
    }
    goto LABEL_84;
  }
  pbmi.bmiHeader.biSizeImage = 2 * v15 * v14;
LABEL_23:
  *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 0;
  v23 = CreateDIBSection(v18, &pbmi, 0, (void **)(v12 + 32), 0, 0);
  *(_QWORD *)(v12 + 16) = v23;
  if ( v23 )
  {
    v24 = *(HDC *)(v12 + 24);
    *(_DWORD *)(v12 + 12) = v14;
    SelectObject(v24, v23);
    goto LABEL_25;
  }
LABEL_86:
  *(_DWORD *)(v12 + 12) = 0;
LABEL_25:
  v25 = *(void **)(v12 + 40);
  if ( v25 )
  {
    HeapFree(GpRuntime::GpMemHeap, 0, v25);
    *(_QWORD *)(v12 + 40) = 0;
  }
  if ( v14 < 0 || (unsigned __int64)v14 > 0x3333333333333333LL )
  {
    *(_QWORD *)(v12 + 40) = 0;
    v26 = 0;
LABEL_33:
    *(_DWORD *)(v12 + 12) = 0;
    goto LABEL_34;
  }
  if ( (unsigned __int64)(5LL * v14) > 0x1FFFFFFFFFFFFFFFLL )
    v26 = 0;
  else
    v26 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, 40LL * v14);
  *(_QWORD *)(v12 + 40) = v26;
  if ( !v26 )
    goto LABEL_33;
  v75 = 8LL * v14;
  *(_QWORD *)(v12 + 48) = &v26[v75];
  v76 = &v26[v75 + v75];
  *(_QWORD *)(v12 + 56) = v76;
  *(_QWORD *)(v12 + 64) = &v76[v75];
  *(_QWORD *)(v12 + 72) = &v76[v75 + v75];
LABEL_34:
  v27 = *(HDC *)(v12 + 24);
  v115 = *(_QWORD *)(v12 + 32);
  v117 = v27;
  if ( this != (EpScanGdiDci *)-1328LL )
  {
    *((_QWORD *)this + 166) = v26;
    *((_QWORD *)this + 167) = *(_QWORD *)(v12 + 48);
    *((_QWORD *)this + 168) = *(_QWORD *)(v12 + 56);
    *((_QWORD *)this + 169) = *(_QWORD *)(v12 + 64);
    *((_QWORD *)this + 170) = *(_QWORD *)(v12 + 72);
  }
  v28 = *(_DWORD *)(v12 + 80);
  if ( *(_DWORD *)(v12 + 12) && v28 )
  {
    v29 = *((_QWORD *)this + 164);
    v30 = *((_DWORD *)this + 355);
    v31 = *(_QWORD *)(v29 + 664);
    if ( !v31 )
      v31 = *(_QWORD *)(*((_QWORD *)this + 163) + 1576LL);
    v109 = (char *)this + 168;
    v94 = v30;
    v32 = *((unsigned int *)this + 162);
    *(_QWORD *)wSrc = v31;
    v33 = *((unsigned int *)this + 163);
    ySrc = *(_DWORD *)(v29 + 44);
    xSrc = *(_DWORD *)(v29 + 32);
    offset = *(_DWORD *)(v29 + 28);
    v34 = *(_QWORD *)(v29 + 672);
    v110 = (char *)this + 1328;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v111 = 0;
    v113 = 1;
    v114 = 2;
    EpAlphaBlender::BuildPipeline(
      (char *)this + 24,
      v33,
      (unsigned int)v28,
      v32,
      v34,
      offset,
      xSrc,
      ySrc,
      *(_QWORD *)wSrc,
      (char *)this + 1328,
      1,
      1,
      v94,
      &v109,
      1);
    *((_QWORD *)v109 - 1) = 0;
    v35 = *((_QWORD *)this + 164);
    v36 = *((_DWORD *)this + 355);
    v37 = *(_QWORD *)(v35 + 664);
    if ( !v37 )
      v37 = *(_QWORD *)(*((_QWORD *)this + 163) + 1576LL);
    v109 = (char *)this + 800;
    v95 = v36;
    v38 = *((unsigned int *)this + 320);
    ySrca = *(_DWORD *)(v35 + 44);
    xSrca = *(_DWORD *)(v35 + 32);
    offseta = *(_DWORD *)(v35 + 28);
    v39 = *(_QWORD *)(v35 + 672);
    v40 = *((unsigned int *)this + 321);
    v110 = (char *)this + 1328;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v111 = 0;
    v113 = 1;
    v114 = 2;
    EpAlphaBlender::BuildPipeline(
      (char *)this + 656,
      v40,
      (unsigned int)v28,
      v38,
      v39,
      offseta,
      xSrca,
      ySrca,
      v37,
      (char *)this + 1328,
      1,
      1,
      v95,
      &v109,
      1);
    *((_QWORD *)v109 - 1) = 0;
    v105 = *((_DWORD *)this + 4);
    v106 = *((_DWORD *)this + 5);
    StretchBlt(
      v27,
      0,
      0,
      v101 - v96,
      v100 - v97 + 1,
      a2,
      v96 / v104,
      v97 / v104,
      (v101 - v96) / v104,
      (v100 - v97 + 1) / v104,
      0xCC0020u);
    v41 = v28 >> 8;
    v42 = v101 - v96;
    if ( (_BYTE)v41 )
    {
      if ( v42 <= 0x7FFFFFF8u / (unsigned __int8)v41 )
      {
        v43 = ((((unsigned __int8)v41 * v42 + 7) >> 3) + 3) & 0xFFFFFFFC;
        v107 = v43;
        if ( v43 )
        {
          v44 = (unsigned __int8)v41 >> 3;
          v99 = v44;
          while ( 1 )
          {
            v45 = *((_DWORD *)this + 353);
            v46 = *((_DWORD *)a3 + 1);
            v47 = *((_DWORD *)this + 354);
            v48 = *((_DWORD *)a3 + 2);
            v49 = *((int *)a3 + 3);
            v98 = *(_WORD *)a3;
            v50 = (char *)((unsigned int)(v44 * (v46 + v45 - v96)) + v115 + (v48 + v47 - v97) * v43);
            v51 = *((_WORD *)a3 + 1);
            if ( v51 != 1 )
              break;
            v70 = 632LL * *(unsigned __int16 *)a3;
            if ( (_DWORD)v49 )
            {
              if ( !*(_DWORD *)((char *)this + v70 + 128) )
                *(_QWORD *)((char *)this + v70 + 96) = (char *)a3 + 24;
              v71 = (char *)this + v70;
              *(_DWORD *)((char *)this + v70 + 60) = v48 + v47 - v106;
              v72 = (char *)this + v70 + 168;
              *(_QWORD *)((char *)this + v70 + 72) = 0;
              *(_DWORD *)((char *)this + v70 + 56) = v46 + v45 - v105;
              while ( 1 )
              {
                v62 = (char *)*((_QWORD *)v72 + 1);
                v60 = v71 + 32;
                v73 = *((_QWORD *)v72 + 2);
                v64 = *(void (__fastcall **)(__int64, char *, __int64, char *))v72;
                v63 = (unsigned int)v49;
                if ( v62 == (char *)1 )
                  v62 = (char *)a3 + 24;
                if ( !v62 )
                  v62 = v50;
                if ( !v73 )
                  break;
                v64(v73, v62, (unsigned int)v49, v60);
                v72 += 24;
              }
LABEL_61:
              v64((__int64)v50, v62, v63, v60);
LABEL_62:
              v44 = v99;
            }
            v65 = *((unsigned __int16 *)a3 + 1);
            v66 = *((int *)a3 + 3);
            v67 = 0;
            v68 = ((*((int *)this + 158 * v98 + 162) >> 8) & 0xF8u) >> 3;
            if ( v65 == 3 )
            {
              v69 = v66 + 20;
            }
            else
            {
              if ( *((_WORD *)a3 + 1) )
              {
                v74 = v65 - 1;
                if ( v74 )
                {
                  if ( v74 == 1 )
                    v67 = (char *)(v66
                                 + (((unsigned __int64)a3 + (int)(*((_DWORD *)a3 + 4) * v68) + 27)
                                  & 0xFFFFFFFFFFFFFFFCuLL));
                  goto LABEL_66;
                }
              }
              v69 = (int)(v68 * v66) + 24LL;
            }
            v67 = (char *)a3 + v69;
LABEL_66:
            v43 = v107;
            a3 = (struct EpScanRecord *)((unsigned __int64)(v67 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
            if ( a3 >= v116 )
            {
              StretchBlt(
                a2,
                v96 / v104,
                v97 / v104,
                (v101 - v96) / v104,
                (v100 - v97 + 1) / v104,
                v117,
                0,
                0,
                v101 - v96,
                v100 - v97 + 1,
                0xCC0020u);
              return;
            }
          }
          v103 = 0;
          if ( v51 == 3 )
          {
            v52 = 0;
            v103 = (char *)a3 + 20;
          }
          else
          {
            v52 = (char *)a3 + 24;
            if ( v51 == 2 )
              v103 = (char *)(((unsigned __int64)a3
                             + (int)(*((_DWORD *)a3 + 4) * (((*((int *)this + 162) >> 8) & 0xF8u) >> 3))
                             + 27)
                            & 0xFFFFFFFFFFFFFFFCuLL);
          }
          v53 = v46 + v45;
          v54 = v48 + v47;
          if ( (*(_DWORD *)(*((_QWORD *)this + 165) + 12LL) & 0xFF00u) < 0x800 )
            memset_0(v50, 0, v49);
          v55 = v54 - *((_DWORD *)this + 5);
          v56 = v53 - *((_DWORD *)this + 4);
          v57 = 632LL * *(unsigned __int16 *)a3;
          if ( (_DWORD)v49 )
          {
            if ( !*(_DWORD *)((char *)this + v57 + 128) )
              *(_QWORD *)((char *)this + v57 + 96) = v52;
            *(_DWORD *)((char *)this + v57 + 60) = v55;
            *(_DWORD *)((char *)this + v57 + 56) = v56;
            v58 = (char *)this + v57 + 168;
            *(_QWORD *)((char *)this + v57 + 72) = v103;
            v59 = (char *)this + v57;
            while ( 1 )
            {
              v60 = v59 + 32;
              v61 = *((_QWORD *)v58 + 2);
              v62 = v52;
              if ( *((_QWORD *)v58 + 1) != 1 )
                v62 = (char *)*((_QWORD *)v58 + 1);
              v63 = (unsigned int)v49;
              v64 = *(void (__fastcall **)(__int64, char *, __int64, char *))v58;
              if ( !v62 )
                v62 = v50;
              if ( !v61 )
                break;
              v64(v61, v62, (unsigned int)v49, v60);
              v58 += 24;
            }
            goto LABEL_61;
          }
          goto LABEL_62;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180017060  push    rbp
0x180017062  push    rbx
0x180017063  push    rdi
0x180017064  push    r15
0x180017066  lea     rbp, [rsp-458h]
0x18001706e  sub     rsp, 558h
0x180017075  mov     rax, cs:__security_cookie
0x18001707c  xor     rax, rsp
0x18001707f  mov     [rbp+470h+var_40], rax
0x180017086  mov     rax, [rcx+520h]
0x18001708d  mov     rbx, r8
0x180017090  mov     r8, rdx
0x180017093  mov     [rbp+470h+hdcSrc], rdx
0x180017097  mov     r15, rcx
0x18001709a  mov     [rbp+470h+var_480], r9
0x18001709e  lea     rdx, [rcx+57Ch]; lppt
0x1800170a5  mov     rcx, r8; hdc
0x1800170a8  mov     edi, [rax+308h]
0x1800170ae  mov     [rbp+470h+var_4D0], edi
0x1800170b1  call    cs:__imp_GetDCOrgEx
0x1800170b8  nop     dword ptr [rax+rax+00h]
0x1800170bd  mov     ecx, [r15+558h]
0x1800170c4  mov     r10d, [r15+55Ch]
0x1800170cb  mov     r8d, [r15+560h]
0x1800170d2  mov     r9d, [r15+564h]
0x1800170d9  mov     [rbp+470h+var_4F0], ecx
0x1800170dc  mov     [rbp+470h+var_4DC], r10d
0x1800170e0  mov     [rbp+470h+var_4EC], r8d
0x1800170e4  mov     [rbp+470h+var_4E0], r9d
0x1800170e8  cmp     edi, 1
0x1800170eb  jg      loc_1800179A9
0x1800170f1  cmp     cs:?g_fClientSession@Globals@@3HA, 0; int Globals::g_fClientSession
0x1800170f8  mov     [rsp+570h+arg_18], rsi
0x180017100  mov     rsi, [r15+518h]
0x180017107  mov     [rsp+570h+var_20], r12
0x18001710f  mov     [rsp+570h+var_28], r13
0x180017117  mov     [rsp+570h+var_30], r14
0x18001711f  jnz     loc_180017A11
0x180017125  xor     edi, edi
0x180017127  mov     rax, [r15+520h]
0x18001712e  mov     r12d, r9d
0x180017131  sub     r12d, r8d
0x180017134  mov     r14d, r10d
0x180017137  sub     r14d, ecx
0x18001713a  inc     r12d
0x18001713d  mov     rcx, [rsi+10h]; ho
0x180017141  mov     r13, [rax+298h]
0x180017148  mov     [rbp+470h+var_4D8], r13
0x18001714c  test    rcx, rcx
0x18001714f  jz      short loc_18001715D
0x180017151  call    cs:__imp_DeleteObject
0x180017158  nop     dword ptr [rax+rax+00h]
0x18001715d  test    r13, r13
0x180017160  jnz     short loc_18001716D
0x180017162  mov     rax, [rsi+628h]
0x180017169  mov     [rbp+470h+var_4D8], rax
0x18001716d  mov     r13, [rsi+5E0h]
0x180017174  lea     rcx, [rbp+470h+pbmi]; void *
0x180017178  xor     edx, edx; Val
0x18001717a  mov     r8d, 428h; Size
0x180017180  call    memset_0
0x180017185  test    edi, edi
0x180017187  jnz     short loc_180017193
0x180017189  mov     rcx, r13; hdc
0x18001718c  call    ?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z; ExtractPixelFormatFromHDC(HDC__ *)
0x180017191  mov     edi, eax
0x180017193  mov     [rsi+50h], edi
0x180017196  bt      edi, 10h
0x18001719a  jnb     short loc_1800171A3
0x18001719c  mov     dword ptr [rsi+50h], 30803h
0x1800171a3  mov     edx, 2; index
0x1800171a8  mov     rcx, r13; hdc
0x1800171ab  call    cs:__imp_GetDeviceCaps
0x1800171b2  nop     dword ptr [rax+rax+00h]
0x1800171b7  cmp     eax, 2
0x1800171ba  jz      loc_180017A20
0x1800171c0  mov     edx, [rsi+50h]
0x1800171c3  test    edx, edx
0x1800171c5  jz      loc_180017A2D
0x1800171cb  xor     r11d, r11d
0x1800171ce  mov     [rbp+470h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800171d5  mov     r8d, 0FFh
0x1800171db  mov     [rbp+470h+pbmi.bmiHeader.biHeight], r11d
0x1800171df  mov     ecx, edx
0x1800171e1  mov     [rbp+470h+pbmi.bmiHeader.biCompression], r11d
0x1800171e5  sar     ecx, 8
0x1800171e8  mov     edi, 1
0x1800171ed  movzx   eax, cx
0x1800171f0  mov     [rbp+470h+pbmi.bmiHeader.biPlanes], di
0x1800171f4  and     ax, r8w
0x1800171f8  mov     r8d, r11d
0x1800171fb  mov     [rbp+470h+pbmi.bmiHeader.biBitCount], ax
0x1800171ff  movzx   r9d, ax
0x180017203  bt      edx, 10h
0x180017207  jb      loc_180017A60
0x18001720d  movzx   eax, cl
0x180017210  sub     eax, 10h
0x180017213  test    eax, 0FFFFFFEFh
0x180017218  jnz     short loc_180017224
0x18001721a  mov     r8d, 3
0x180017220  mov     [rbp+470h+pbmi.bmiHeader.biCompression], r8d
0x180017224  movzx   eax, dl
0x180017227  lea     rdx, __ImageBase
0x18001722e  lea     rcx, ds:0[rax*4]
0x180017236  mov     eax, [rcx+rdx+18BAA0h]
0x18001723d  mov     dword ptr [rbp+470h+pbmi.bmiColors.rgbBlue], eax
0x180017240  mov     eax, [rcx+rdx+18BA50h]
0x180017247  mov     [rbp+470h+var_444], eax
0x18001724a  mov     eax, [rcx+rdx+18BA00h]
0x180017251  mov     [rbp+470h+var_440], eax
0x180017254  mov     [rbp+470h+pbmi.bmiHeader.biWidth], r14d
0x180017258  test    r12d, r12d
0x18001725b  js      loc_18001795E
0x180017261  mov     eax, r12d
0x180017264  neg     eax
0x180017266  mov     [rbp+470h+pbmi.bmiHeader.biHeight], eax
0x180017269  test    r8d, r8d
0x18001726c  jz      loc_180017928
0x180017272  cmp     r9w, 10h
0x180017277  jz      loc_180017AB3
0x18001727d  cmp     r9w, 20h ; ' '
0x180017282  jnz     loc_180017928
0x180017288  mov     eax, r14d
0x18001728b  imul    eax, r12d
0x18001728f  shl     eax, 2
0x180017292  mov     [rbp+470h+pbmi.bmiHeader.biSizeImage], eax
0x180017295  mov     [rsp+570h+offset], r11d; offset
0x18001729a  lea     r9, [rsi+20h]; ppvBits
0x18001729e  xor     r8d, r8d; usage
0x1800172a1  mov     [rsp+570h+hSection], r11; hSection
0x1800172a6  lea     rdx, [rbp+470h+pbmi]; pbmi
0x1800172aa  mov     qword ptr [rbp+470h+pbmi.bmiHeader.biClrUsed], 0
0x1800172b2  mov     rcx, r13; hdc
0x1800172b5  call    cs:__imp_CreateDIBSection
0x1800172bc  nop     dword ptr [rax+rax+00h]
0x1800172c1  mov     [rsi+10h], rax
0x1800172c5  test    rax, rax
0x1800172c8  jz      loc_180017AC4
0x1800172ce  mov     rcx, [rsi+18h]; hdc
0x1800172d2  mov     rdx, rax; h
0x1800172d5  mov     [rsi+0Ch], r14d
0x1800172d9  call    cs:__imp_SelectObject
0x1800172e0  nop     dword ptr [rax+rax+00h]
0x1800172e5  xor     r11d, r11d
0x1800172e8  mov     r8, [rsi+28h]; lpMem
0x1800172ec  test    r8, r8
0x1800172ef  jz      short loc_18001730D
0x1800172f1  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800172f8  xor     edx, edx; dwFlags
0x1800172fa  call    cs:__imp_HeapFree
0x180017301  nop     dword ptr [rax+rax+00h]
0x180017306  xor     r11d, r11d
0x180017309  mov     [rsi+28h], r11
0x18001730d  test    r14d, r14d
0x180017310  js      short loc_180017324
0x180017312  movsxd  rax, r14d
0x180017315  mov     rcx, 3333333333333333h
0x18001731f  cmp     rax, rcx
0x180017322  jbe     short loc_18001732D
0x180017324  mov     [rsi+28h], r11
0x180017328  mov     r8, r11
0x18001732b  jmp     short loc_180017374
0x18001732d  lea     r8, [rax+rax*4]
0x180017331  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001733b  cmp     r8, rax
0x18001733e  ja      loc_180017ACC
0x180017344  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18001734b  lea     r8, ds:0[r8*8]; dwBytes
0x180017353  xor     edx, edx; dwFlags
0x180017355  call    cs:__imp_HeapAlloc
0x18001735c  nop     dword ptr [rax+rax+00h]
0x180017361  mov     r8, rax
0x180017364  xor     r11d, r11d
0x180017367  mov     [rsi+28h], r8
0x18001736b  test    r8, r8
0x18001736e  jnz     loc_1800178E7
0x180017374  mov     [rsi+0Ch], r11d
0x180017378  mov     rax, [rsi+20h]
0x18001737c  lea     rcx, [r15+530h]
0x180017383  mov     r13, [rsi+18h]
0x180017387  mov     [rbp+470h+var_488], rax
0x18001738b  mov     [rbp+470h+var_478], r13
0x18001738f  test    rcx, rcx
0x180017392  jnz     loc_18001796B
0x180017398  cmp     dword ptr [rsi+0Ch], 0
0x18001739c  mov     r12d, [rsi+50h]
0x1800173a0  jz      loc_1800177FC
0x1800173a6  test    r12d, r12d
0x1800173a9  jz      loc_1800177FC
0x1800173af  mov     rcx, [r15+520h]
0x1800173b6  lea     r8, [r15+530h]
0x1800173bd  mov     r9d, [r15+58Ch]
0x1800173c4  mov     rdx, [rcx+298h]
0x1800173cb  test    rdx, rdx
0x1800173ce  jnz     short loc_1800173DE
0x1800173d0  mov     rax, [r15+518h]
0x1800173d7  mov     rdx, [rax+628h]
0x1800173de  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x1800173e6  lea     rax, [r15+0A8h]
0x1800173ed  mov     [rsp+570h+var_500], edi
0x1800173f1  mov     [rbp+470h+var_4B8], rax
0x1800173f5  lea     rax, [rbp+470h+var_4B8]
0x1800173f9  mov     [rsp+570h+var_508], rax
0x1800173fe  mov     eax, [rcx+2Ch]
0x180017401  mov     [rsp+570h+var_510], r9d
0x180017406  mov     r9d, [r15+288h]
0x18001740d  mov     [rsp+570h+var_518], edi
0x180017411  mov     [rsp+570h+rop], edi
0x180017415  mov     qword ptr [rsp+570h+hSrc], r8
0x18001741a  mov     qword ptr [rsp+570h+wSrc], rdx
0x18001741f  mov     edx, [r15+28Ch]
0x180017426  mov     [rsp+570h+ySrc], eax
0x18001742a  mov     eax, [rcx+20h]
0x18001742d  mov     [rsp+570h+xSrc], eax
0x180017431  mov     eax, [rcx+1Ch]
0x180017434  mov     [rsp+570h+offset], eax
0x180017438  mov     rax, [rcx+2A0h]
0x18001743f  lea     rcx, [r15+18h]
0x180017443  mov     [rbp+470h+var_4B0], r8
0x180017447  mov     r8d, r12d
0x18001744a  mov     [rsp+570h+hSection], rax
0x18001744f  movdqu  [rbp+470h+var_4A0], xmm0
0x180017454  mov     [rbp+470h+var_4A8], r11d
0x180017458  mov     [rbp+470h+var_490], edi
0x18001745b  mov     [rbp+470h+var_48C], 2
0x180017462  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x180017467  mov     rax, [rbp+470h+var_4B8]
0x18001746b  lea     r8, [r15+530h]
0x180017472  xor     esi, esi
0x180017474  mov     [rax-8], rsi
0x180017478  mov     rdx, [r15+520h]
0x18001747f  mov     r9d, [r15+58Ch]
0x180017486  mov     rcx, [rdx+298h]
0x18001748d  test    rcx, rcx
0x180017490  jnz     short loc_1800174A0
0x180017492  mov     rax, [r15+518h]
0x180017499  mov     rcx, [rax+628h]
0x1800174a0  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x1800174a8  lea     rax, [r15+320h]
0x1800174af  mov     [rsp+570h+var_500], edi
0x1800174b3  mov     [rbp+470h+var_4B8], rax
0x1800174b7  lea     rax, [rbp+470h+var_4B8]
0x1800174bb  mov     [rsp+570h+var_508], rax
0x1800174c0  mov     eax, [rdx+2Ch]
0x1800174c3  mov     [rsp+570h+var_510], r9d
0x1800174c8  mov     r9d, [r15+500h]
0x1800174cf  mov     [rsp+570h+var_518], edi
0x1800174d3  mov     [rsp+570h+rop], edi
0x1800174d7  mov     qword ptr [rsp+570h+hSrc], r8
0x1800174dc  mov     qword ptr [rsp+570h+wSrc], rcx
0x1800174e1  lea     rcx, [r15+290h]
0x1800174e8  mov     [rsp+570h+ySrc], eax
0x1800174ec  mov     eax, [rdx+20h]
0x1800174ef  mov     [rsp+570h+xSrc], eax
0x1800174f3  mov     eax, [rdx+1Ch]
0x1800174f6  mov     [rsp+570h+offset], eax
0x1800174fa  mov     rax, [rdx+2A0h]
0x180017501  mov     edx, [r15+504h]
0x180017508  mov     [rbp+470h+var_4B0], r8
0x18001750c  mov     r8d, r12d
0x18001750f  mov     [rsp+570h+hSection], rax
0x180017514  movdqu  [rbp+470h+var_4A0], xmm0
0x180017519  mov     [rbp+470h+var_4A8], esi
0x18001751c  mov     [rbp+470h+var_490], edi
0x18001751f  mov     [rbp+470h+var_48C], 2
0x180017526  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x18001752b  mov     r9d, [rbp+470h+var_4EC]
0x18001752f  mov     rax, [rbp+470h+var_4B8]
0x180017533  mov     ecx, [rbp+470h+var_4E0]
0x180017536  mov     edi, [rbp+470h+var_4F0]
0x180017539  mov     r14d, [rbp+470h+var_4DC]
0x18001753d  mov     [rax-8], rsi
0x180017541  mov     eax, [r15+10h]
0x180017545  mov     esi, [rbp+470h+var_4D0]
0x180017548  mov     [rbp+470h+var_4CC], eax
0x18001754b  mov     eax, [r15+14h]
0x18001754f  mov     [rbp+470h+var_4C8], eax
0x180017552  mov     eax, ecx
0x180017554  sub     eax, r9d
0x180017557  mov     [rsp+570h+rop], 0CC0020h; rop
0x18001755f  inc     eax
0x180017561  sub     ecx, r9d
0x180017564  cdq
0x180017565  inc     ecx
0x180017567  idiv    esi
0x180017569  mov     r11d, eax
0x18001756c  mov     eax, r14d
0x18001756f  sub     eax, edi
0x180017571  mov     [rsp+570h+hSrc], r11d; hSrc
0x180017576  cdq
0x180017577  idiv    esi
0x180017579  mov     r10d, eax
0x18001757c  mov     eax, r9d
0x18001757f  cdq
0x180017580  mov     [rsp+570h+wSrc], r10d; wSrc
0x180017585  idiv    esi
0x180017587  mov     r9d, r14d
0x18001758a  mov     r8d, eax
0x18001758d  sub     r9d, edi; wDest
0x180017590  mov     [rsp+570h+ySrc], r8d; ySrc
  ... truncated ...
```
