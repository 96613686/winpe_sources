# DriverNonPS::OutputBufferDIB(HDC__ *,DpContext *,DpBitmap *,GpRuntime::GpRect const *,GpRuntime::GpRect const *,DpPath *)

- ea: `0x1800da830`
- end: `0x1800db45a`
- name: `?OutputBufferDIB@DriverNonPS@@UEAA?AW4Status@@PEAUHDC__@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@3PEAVDpPath@@@Z`
- size: `3114`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18002ad28`
- `0x1800c5274`
- `0x1800da830`
- `0x1800db460`
- `0x180105d40`
- `0x18013e980`
- `0x180140ce0`
- `0x180141270`

## import_xrefs

- `GDI32!StretchBlt` at `0x1800db075`
- `GDI32!StretchBlt` at `0x1800db2d1`
- `GDI32!StretchBlt` at `0x1800db075`
- `GDI32!StretchBlt` at `0x1800db2d1`
- `GDI32!SetStretchBltMode` at `0x1800daece`
- `GDI32!SetStretchBltMode` at `0x1800daece`
- `GDI32!StretchDIBits` at `0x1800dab01`
- `GDI32!StretchDIBits` at `0x1800dabc8`
- `GDI32!StretchDIBits` at `0x1800dade6`
- `GDI32!StretchDIBits` at `0x1800dafcc`
- `GDI32!StretchDIBits` at `0x1800db1a9`
- `GDI32!StretchDIBits` at `0x1800db24a`
- `GDI32!StretchDIBits` at `0x1800db3a1`
- `GDI32!StretchDIBits` at `0x1800dab01`
- `GDI32!StretchDIBits` at `0x1800dabc8`
- `GDI32!StretchDIBits` at `0x1800dade6`
- `GDI32!StretchDIBits` at `0x1800dafcc`
- `GDI32!StretchDIBits` at `0x1800db1a9`
- `GDI32!StretchDIBits` at `0x1800db24a`
- `GDI32!StretchDIBits` at `0x1800db3a1`
- `GDI32!SetBrushOrgEx` at `0x1800daeed`
- `GDI32!SetBrushOrgEx` at `0x1800daeed`
- `GDI32!SetBkColor` at `0x1800db018`
- `GDI32!SetBkColor` at `0x1800db018`
- `GDI32!SetTextColor` at `0x1800db02a`
- `GDI32!SetTextColor` at `0x1800db02a`
- `GDI32!CreateBitmap` at `0x1800dae89`
- `GDI32!CreateBitmap` at `0x1800dae89`
- `GDI32!PatBlt` at `0x1800daf50`
- `GDI32!PatBlt` at `0x1800db10b`
- `GDI32!PatBlt` at `0x1800db31d`
- `GDI32!PatBlt` at `0x1800daf50`
- `GDI32!PatBlt` at `0x1800db10b`
- `GDI32!PatBlt` at `0x1800db31d`
- `GDI32!GdiFlush` at `0x1800da895`
- `GDI32!GdiFlush` at `0x1800da895`
- `GDI32!DeleteDC` at `0x1800db3d3`
- `GDI32!DeleteDC` at `0x1800db3d3`
- `GDI32!SelectObject` at `0x1800daeb9`
- `GDI32!SelectObject` at `0x1800daf27`
- `GDI32!SelectObject` at `0x1800daf68`
- `GDI32!SelectObject` at `0x1800db0d9`
- `GDI32!SelectObject` at `0x1800db334`
- `GDI32!SelectObject` at `0x1800daeb9`
- `GDI32!SelectObject` at `0x1800daf27`
- `GDI32!SelectObject` at `0x1800daf68`
- `GDI32!SelectObject` at `0x1800db0d9`
- `GDI32!SelectObject` at `0x1800db334`
- `GDI32!CreateCompatibleDC` at `0x1800dae3a`
- `GDI32!CreateCompatibleDC` at `0x1800dae3a`
- `GDI32!DeleteObject` at `0x1800db3ef`
- `GDI32!DeleteObject` at `0x1800db3ef`

## pseudocode

```c
__int64 __fastcall DriverNonPS::OutputBufferDIB(
        _DWORD *a1,
        HDC a2,
        struct DpContext *a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        struct DpPath *a7)
{
  unsigned int v7; // r14d
  EpScanDIB *v8; // rdi
  int ActualBounds; // eax
  int v12; // r12d
  int v13; // r8d
  int v14; // r13d
  EpScanDIB *v15; // rcx
  char *v16; // r9
  int SrcHeight; // edi
  int v18; // eax
  int v19; // r11d
  char *v20; // rdx
  int v21; // r8d
  int v22; // edx
  int v23; // r10d
  int v24; // ebx
  int v25; // eax
  HGDIOBJ v26; // r13
  int v27; // r12d
  char *v28; // rax
  _BYTE *v29; // rcx
  char *v30; // r9
  int v31; // edx
  _BYTE *v32; // rcx
  int DestHeight; // ecx
  int v34; // edx
  HDC v35; // r13
  int v36; // eax
  int v37; // edx
  int v39; // r8d
  int v40; // r9d
  int v41; // ebx
  int v42; // edx
  int v43; // ecx
  HBITMAP Bitmap; // rax
  HBRUSH GdiBrush; // rax
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  HBRUSH v49; // rax
  HGDIOBJ v50; // rax
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  char *v54; // r9
  int v55; // edx
  __int64 v56; // rax
  int v57; // r8d
  int v58; // edx
  int v59; // eax
  BOOL v60; // r12d
  void *lpBits; // [rsp+48h] [rbp-B8h]
  int v62; // [rsp+70h] [rbp-90h]
  unsigned int v63; // [rsp+70h] [rbp-90h]
  unsigned int v64; // [rsp+70h] [rbp-90h]
  unsigned int v65; // [rsp+70h] [rbp-90h]
  unsigned int v66; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+78h] [rbp-88h]
  unsigned int v69; // [rsp+78h] [rbp-88h]
  BOOL v70; // [rsp+78h] [rbp-88h]
  unsigned int v71; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+78h] [rbp-88h]
  int v73; // [rsp+80h] [rbp-80h]
  unsigned int v74; // [rsp+80h] [rbp-80h]
  unsigned int v75; // [rsp+80h] [rbp-80h]
  int v77; // [rsp+94h] [rbp-6Ch]
  int v78; // [rsp+94h] [rbp-6Ch]
  int v79; // [rsp+98h] [rbp-68h]
  int SrcWidth; // [rsp+9Ch] [rbp-64h]
  int v81; // [rsp+9Ch] [rbp-64h]
  HDC hdcSrc; // [rsp+A0h] [rbp-60h]
  HDC hdcSrca; // [rsp+A0h] [rbp-60h]
  int v84; // [rsp+A8h] [rbp-58h]
  int xSrc; // [rsp+ACh] [rbp-54h]
  int v86; // [rsp+B0h] [rbp-50h] BYREF
  int v87; // [rsp+B4h] [rbp-4Ch]
  int DestWidth; // [rsp+B8h] [rbp-48h]
  int nHeight; // [rsp+BCh] [rbp-44h]
  HGDIOBJ h; // [rsp+C0h] [rbp-40h]
  HGDIOBJ ho; // [rsp+C8h] [rbp-38h]
  void *v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  void *v94; // [rsp+E0h] [rbp-20h]
  EpScanDIB *v95; // [rsp+E8h] [rbp-18h]
  char *v96; // [rsp+F0h] [rbp-10h]
  struct DpPath *v97; // [rsp+F8h] [rbp-8h]
  _BYTE bmi[48]; // [rsp+100h] [rbp+0h] BYREF
  int v99; // [rsp+130h] [rbp+30h]
  _BYTE lpbmi[48]; // [rsp+138h] [rbp+38h] BYREF

  v7 = 0;
  v8 = *(EpScanDIB **)(a4 + 128);
  v93 = a5;
  v97 = a7;
  h = 0;
  v95 = v8;
  GdiFlush();
  ActualBounds = EpScanDIB::GetActualBounds(v8, (struct GpRuntime::GpRect *)&v86);
  v12 = nHeight;
  v13 = ActualBounds;
  v14 = DestWidth;
  v15 = v95;
  v77 = ActualBounds;
  hdcSrc = 0;
  v16 = (char *)*((_QWORD *)v95 + 185);
  SrcHeight = nHeight / a1[12];
  ho = 0;
  v96 = v16;
  v18 = DestWidth / a1[11];
  v94 = 0;
  SrcWidth = v18;
  v19 = v87 / a1[12];
  v84 = v19;
  v20 = (char *)*((_QWORD *)v95 + 172);
  xSrc = v86 / a1[11];
  v62 = *((_DWORD *)v95 + 372);
  v73 = *((_DWORD *)v95 + 332);
  v92 = v20;
  memset(bmi, 0, sizeof(bmi));
  v99 = 0;
  memset(lpbmi, 0, sizeof(lpbmi));
  if ( !a1[45] && v97 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::SetupPathClipping((DriverPrint *)a1, a2, a3, v97);
    v19 = v84;
    v15 = v95;
    v13 = v77;
    v20 = (char *)v92;
    v16 = v96;
  }
  if ( !v13 || !v14 || !v12 )
    goto LABEL_80;
  if ( v20 )
  {
    *(_OWORD *)bmi = *(_OWORD *)((char *)v15 + 1416);
    *(_OWORD *)&bmi[16] = *(_OWORD *)((char *)v15 + 1432);
    *(_OWORD *)&bmi[32] = *(_OWORD *)((char *)v15 + 1448);
    v99 = *((_DWORD *)v15 + 366);
  }
  if ( v16 )
  {
    *(_OWORD *)lpbmi = *(_OWORD *)((char *)v15 + 1492);
    *(_OWORD *)&lpbmi[16] = *(_OWORD *)((char *)v15 + 1508);
    *(_OWORD *)&lpbmi[32] = *(_OWORD *)((char *)v15 + 1524);
    if ( !AllWhite((const struct tagBITMAPINFO *)lpbmi, v16) )
    {
      v13 = v77;
      v20 = (char *)v92;
      goto LABEL_8;
    }
LABEL_80:
    v35 = a2;
    goto LABEL_25;
  }
LABEL_8:
  if ( a1[42] )
  {
    v21 = 0;
    v22 = xSrc;
    v23 = 0;
    v24 = xSrc + SrcWidth;
    v78 = 0;
    v79 = 0;
    *(_DWORD *)&bmi[8] = 1;
    *(_WORD *)&bmi[14] = 24;
    v25 = v19 + SrcHeight;
    v68 = v19 + SrcHeight;
    *(_DWORD *)&bmi[16] = 0;
    v81 = xSrc + SrcWidth;
    while ( 1 )
    {
      if ( v19 >= v25 )
        goto LABEL_47;
      v26 = 0;
      v27 = v22;
      h = 0;
      v28 = (char *)v92 + 4 * v22 + (unsigned int)(*((_DWORD *)v95 + 332) * (*(_DWORD *)(v93 + 12) - v19 - 1));
      v29 = 0;
      hdcSrca = 0;
      v30 = v28;
      ho = v28;
      while ( 1 )
      {
        if ( v27 >= v24 )
        {
          v35 = a2;
          goto LABEL_22;
        }
        v31 = *(_DWORD *)v28;
        v94 = v28 + 4;
        if ( HIBYTE(v31) <= 4u )
          break;
        if ( !v21 )
        {
          v79 = v27;
          v78 = 1;
          h = &v30[4 * v27];
          v29 = h;
        }
        *v29 = v31;
        v32 = v29 + 1;
        *v32++ = BYTE1(v31);
        *v32 = BYTE2(v31);
        v29 = v32 + 1;
        hdcSrca = (HDC)v29;
LABEL_15:
        v23 = v79;
        ++v27;
        v21 = v78;
        v28 = (char *)v94;
        v26 = h;
      }
      if ( !v21 )
        goto LABEL_15;
      DestHeight = a1[12];
      v74 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v74);
      v78 = 0;
      v34 = *a6 + a1[11] * v23;
      *(_DWORD *)&bmi[4] = v27 - v23;
      lpBits = v26;
      v35 = a2;
      v36 = StretchDIBits(
              a2,
              v34,
              a6[1] + v19 * DestHeight,
              a1[11] * (v27 - v23),
              DestHeight,
              0,
              0,
              v27 - v23,
              1,
              lpBits,
              (const BITMAPINFO *)bmi,
              0,
              0xCC0020u);
      v19 = v84;
      if ( v36 )
        break;
      v21 = 0;
      v7 = 1;
      v23 = v79;
      _mm_setcsr(v74);
LABEL_22:
      if ( v21 )
      {
        v75 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v75);
        v37 = *a6 + a1[11] * v23;
        v78 = 0;
        *(_DWORD *)&bmi[4] = v27 - v23;
        if ( !StretchDIBits(
                v35,
                v37,
                a6[1] + v19 * a1[12],
                a1[11] * (v27 - v23),
                a1[12],
                0,
                0,
                v27 - v23,
                1,
                h,
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u) )
        {
          v7 = 1;
          _mm_setcsr(v75);
          goto LABEL_25;
        }
        v19 = v84;
        v21 = 0;
        _mm_setcsr(v75);
      }
      v23 = v79;
      ++v19;
      v22 = xSrc;
      v25 = v68;
      v24 = v81;
      v84 = v19;
    }
    v29 = hdcSrca;
    v30 = (char *)ho;
    _mm_setcsr(v74);
    v24 = v81;
    goto LABEL_15;
  }
  if ( a1[40] || !a1[41] )
  {
    if ( a1[16] == 2 )
    {
      v41 = _mm_getcsr();
      _mm_setcsr(v41 & 0xFFFFFFC0);
      hdcSrc = CreateCompatibleDC(a2);
      if ( !hdcSrc )
      {
        v7 = 1;
        _mm_setcsr(v41 & 0xFFFFFFC0);
LABEL_47:
        v35 = a2;
        goto LABEL_25;
      }
      v42 = -v12;
      if ( v12 > 0 )
        v42 = v12;
      v43 = -v14;
      if ( v14 > 0 )
        v43 = v14;
      Bitmap = CreateBitmap(v43, v42, 1u, 1u, 0);
      ho = Bitmap;
      if ( !Bitmap )
      {
        v7 = 1;
        _mm_setcsr(v41 & 0xFFFFFFC0);
LABEL_76:
        if ( hdcSrc )
          DeleteDC(hdcSrc);
        if ( ho )
          DeleteObject(ho);
        goto LABEL_47;
      }
      SelectObject(hdcSrc, Bitmap);
      SetStretchBltMode(hdcSrc, 4);
      SetBrushOrgEx(hdcSrc, -*a6, -a6[1], 0);
      if ( a1[40] )
      {
        ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
        GdiBrush = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
        h = SelectObject(hdcSrc, GdiBrush);
        v70 = PatBlt(hdcSrc, 0, 0, v14, v12, 0xF00021u);
        SelectObject(hdcSrc, h);
        v46 = v70;
      }
      else
      {
        v46 = StretchDIBits(
                hdcSrc,
                0,
                0,
                v14,
                v12,
                xSrc,
                *(_DWORD *)(v93 + 12) - v84 - SrcHeight,
                SrcWidth,
                SrcHeight,
                v92,
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u);
      }
      v47 = v41 & 0xFFFFFFC0;
      if ( !v46 )
      {
        v7 = 1;
        _mm_setcsr(v47);
        goto LABEL_76;
      }
      _mm_setcsr(v47);
      v71 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v71);
      SetBkColor(a2, 0xFFFFFFu);
      SetTextColor(a2, 0);
      v48 = StretchBlt(a2, *a6 + v86, a6[1] + v87, v14, v12, hdcSrc, 0, 0, v14, v12, 0x660046u);
      _mm_setcsr(v71);
    }
    else
    {
      if ( a1[40] )
      {
        v72 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v72);
        ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
        v49 = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
        v50 = SelectObject(a2, v49);
        v51 = a6[1] + v87;
        v52 = *a6 + v86;
        h = v50;
        v48 = PatBlt(a2, v52, v51, v14, v12, 0x5A0049u);
      }
      else
      {
        v53 = a6[1] + v87;
        v72 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v72);
        *(_DWORD *)&bmi[8] = SrcHeight;
        v54 = &v20[v73 * (*(_DWORD *)(v93 + 12) - v19 - SrcHeight)];
        v55 = *a6 + v86;
        v94 = v54;
        v48 = StretchDIBits(
                a2,
                v55,
                v53,
                v14,
                v12,
                xSrc,
                0,
                SrcWidth,
                SrcHeight,
                v54,
                (const BITMAPINFO *)bmi,
                0,
                0x660046u);
      }
      _mm_setcsr(v72);
    }
    if ( !v48 )
    {
      v7 = 1;
      goto LABEL_76;
    }
    v56 = (unsigned int)(v62 * (a6[3] - v87 - v12));
    *(_DWORD *)&lpbmi[8] = v12;
    v63 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v63);
    if ( !StretchDIBits(
            a2,
            v86 + *a6,
            v87 + a6[1],
            v14,
            v12,
            v86,
            0,
            v14,
            v12,
            &v96[v56],
            (const BITMAPINFO *)lpbmi,
            0,
            0x8800C6u) )
    {
      v7 = 1;
      _mm_setcsr(v63);
      goto LABEL_76;
    }
    v57 = a6[1] + v87;
    v58 = *a6 + v86;
    _mm_setcsr(v63);
    if ( hdcSrc )
    {
      v64 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v64);
      v59 = StretchBlt(a2, v58, v57, v14, v12, hdcSrc, 0, 0, v14, v12, 0x660046u);
      _mm_setcsr(v64);
    }
    else
    {
      if ( a1[40] )
      {
        v65 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v65);
        v60 = PatBlt(a2, v58, v57, v14, v12, 0x5A0049u);
        SelectObject(a2, h);
        _mm_setcsr(v65);
        goto LABEL_74;
      }
      v66 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v66);
      v59 = StretchDIBits(
              a2,
              v58,
              v57,
              v14,
              v12,
              xSrc,
              0,
              SrcWidth,
              SrcHeight,
              v94,
              (const BITMAPINFO *)bmi,
              0,
              0x660046u);
      _mm_setcsr(v66);
    }
    v60 = v59;
LABEL_74:
    if ( !v60 )
      v7 = 1;
    goto LABEL_76;
  }
  if ( v14 <= 0 || v12 <= 0 )
  {
    v35 = a2;
  }
  else
  {
    v39 = a6[1] + v87;
    v69 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v69);
    *(_DWORD *)&bmi[8] = SrcHeight;
    v40 = v14;
    v35 = a2;
    v13 = StretchDIBits(
            a2,
            *a6 + v86,
            v39,
            v40,
            v12,
            xSrc,
            0,
            SrcWidth,
            SrcHeight,
            &v20[v73 * (*(_DWORD *)(v93 + 12) - v19 - SrcHeight)],
            (const BITMAPINFO *)bmi,
            0,
            0xCC0020u);
    _mm_setcsr(v69);
  }
  LOBYTE(v7) = v13 == 0;
LABEL_25:
  if ( a1[45] == a1[46] - 1 && v97 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::RestoreClipping((DriverPrint *)a1, v35, a1[83], 0);
    a1[83] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800da830  push    rbp
0x1800da832  push    rbx
0x1800da833  push    rsi
0x1800da834  push    rdi
0x1800da835  push    r12
0x1800da837  push    r13
0x1800da839  push    r14
0x1800da83b  push    r15
0x1800da83d  lea     rbp, [rsp-78h]
0x1800da842  sub     rsp, 178h
0x1800da849  mov     rax, cs:__security_cookie
0x1800da850  xor     rax, rsp
0x1800da853  mov     [rbp+0B0h+var_48], rax
0x1800da857  mov     rax, [rbp+0B0h+arg_20]
0x1800da85e  xor     r14d, r14d
0x1800da861  mov     rdi, [r9+80h]
0x1800da868  mov     rbx, rdx
0x1800da86b  mov     r15, [rbp+0B0h+arg_28]
0x1800da872  mov     rsi, rcx
0x1800da875  mov     [rbp+0B0h+var_D8], rax
0x1800da879  mov     rax, [rbp+0B0h+arg_30]
0x1800da880  mov     [rbp+0B0h+var_B8], rax
0x1800da884  mov     [rsp+1B0h+var_138], r8
0x1800da889  mov     [rbp+0B0h+hdc], rdx
0x1800da88d  mov     [rbp+0B0h+h], r14
0x1800da891  mov     [rbp+0B0h+var_C8], rdi
0x1800da895  call    cs:__imp_GdiFlush
0x1800da89c  nop     dword ptr [rax+rax+00h]
0x1800da8a1  lea     rdx, [rbp+0B0h+var_100]; struct GpRuntime::GpRect *
0x1800da8a5  mov     rcx, rdi; this
0x1800da8a8  call    ?GetActualBounds@EpScanDIB@@QEAAHPEAVGpRect@GpRuntime@@@Z; EpScanDIB::GetActualBounds(GpRuntime::GpRect *)
0x1800da8ad  mov     r12d, [rbp+0B0h+nHeight]
0x1800da8b1  mov     r8d, eax
0x1800da8b4  mov     r13d, [rbp+0B0h+DestWidth]
0x1800da8b8  xorps   xmm0, xmm0
0x1800da8bb  mov     rcx, [rbp+0B0h+var_C8]
0x1800da8bf  mov     [rbp+0B0h+var_11C], eax
0x1800da8c2  mov     eax, r12d
0x1800da8c5  cdq
0x1800da8c6  mov     [rbp+0B0h+hdcSrc], r14
0x1800da8ca  idiv    dword ptr [rsi+30h]
0x1800da8cd  mov     r9, [rcx+5C8h]
0x1800da8d4  mov     edi, eax
0x1800da8d6  mov     [rbp+0B0h+var_118], eax
0x1800da8d9  mov     eax, r13d
0x1800da8dc  mov     [rbp+0B0h+ho], r14
0x1800da8e0  cdq
0x1800da8e1  mov     [rbp+0B0h+var_C0], r9
0x1800da8e5  idiv    dword ptr [rsi+2Ch]
0x1800da8e8  mov     [rbp+0B0h+var_D0], r14
0x1800da8ec  mov     [rbp+0B0h+var_114], eax
0x1800da8ef  mov     eax, [rbp+0B0h+var_FC]
0x1800da8f2  cdq
0x1800da8f3  idiv    dword ptr [rsi+30h]
0x1800da8f6  mov     r11d, eax
0x1800da8f9  mov     [rbp+0B0h+var_108], eax
0x1800da8fc  mov     eax, [rbp+0B0h+var_100]
0x1800da8ff  cdq
0x1800da900  idiv    dword ptr [rsi+2Ch]
0x1800da903  mov     rdx, [rcx+560h]
0x1800da90a  mov     [rbp+0B0h+var_104], eax
0x1800da90d  mov     eax, [rcx+5D0h]
0x1800da913  mov     [rsp+1B0h+var_140], eax
0x1800da917  mov     eax, [rcx+530h]
0x1800da91d  mov     [rbp+0B0h+var_130], eax
0x1800da920  xor     eax, eax
0x1800da922  mov     [rbp+0B0h+var_E0], rdx
0x1800da926  movups  xmmword ptr [rbp+0B0h+bmi], xmm0
0x1800da92a  mov     [rbp+0B0h+var_80], eax
0x1800da92d  movups  xmmword ptr [rbp+0B0h+bmi+10h], xmm0
0x1800da931  movups  xmmword ptr [rbp+0B0h+bmi+20h], xmm0
0x1800da935  movups  xmmword ptr [rbp+0B0h+var_78], xmm0
0x1800da939  movups  xmmword ptr [rbp+0B0h+var_78+10h], xmm0
0x1800da93d  movups  xmmword ptr [rbp+0B0h+var_78+20h], xmm0
0x1800da941  cmp     [rsi+0B4h], eax
0x1800da947  jz      loc_1800DAC23
0x1800da94d  test    r8d, r8d
0x1800da950  jz      loc_1800DB400
0x1800da956  test    r13d, r13d
0x1800da959  jz      loc_1800DB400
0x1800da95f  test    r12d, r12d
0x1800da962  jz      loc_1800DB400
0x1800da968  test    rdx, rdx
0x1800da96b  jnz     loc_1800DAC7F
0x1800da971  test    r9, r9
0x1800da974  jnz     loc_1800DACAE
0x1800da97a  cmp     [rsi+0A8h], r14d
0x1800da981  jz      loc_1800DAD33
0x1800da987  mov     ebx, [rbp+0B0h+var_114]
0x1800da98a  xor     r8d, r8d
0x1800da98d  mov     edx, [rbp+0B0h+var_104]
0x1800da990  xor     r10d, r10d
0x1800da993  add     ebx, edx
0x1800da995  mov     [rbp+0B0h+var_11C], r8d
0x1800da999  mov     [rbp+0B0h+var_118], r10d
0x1800da99d  lea     eax, [r8+18h]
0x1800da9a1  mov     dword ptr [rbp+0B0h+bmi+8], 1
0x1800da9a8  mov     word ptr [rbp+0B0h+bmi+0Eh], ax
0x1800da9ac  lea     eax, [r11+rdi]
0x1800da9b0  mov     dword ptr [rsp+1B0h+var_138], eax
0x1800da9b4  mov     edi, 0FFFFFFC0h
0x1800da9b9  mov     dword ptr [rbp+0B0h+bmi+10h], r8d
0x1800da9bd  mov     [rbp+0B0h+var_114], ebx
0x1800da9c0  cmp     r11d, eax
0x1800da9c3  jge     loc_1800DAE5E
0x1800da9c9  mov     rax, [rbp+0B0h+var_D8]
0x1800da9cd  xor     r13d, r13d
0x1800da9d0  mov     rcx, [rbp+0B0h+var_C8]
0x1800da9d4  mov     r12d, edx
0x1800da9d7  mov     [rbp+0B0h+h], r13
0x1800da9db  mov     eax, [rax+0Ch]
0x1800da9de  sub     eax, r11d
0x1800da9e1  dec     eax
0x1800da9e3  imul    eax, [rcx+530h]
0x1800da9ea  movsxd  rcx, edx
0x1800da9ed  add     rax, [rbp+0B0h+var_E0]
0x1800da9f1  lea     rax, [rax+rcx*4]
0x1800da9f5  xor     ecx, ecx
0x1800da9f7  mov     [rbp+0B0h+hdcSrc], rcx
0x1800da9fb  mov     r9, rax
0x1800da9fe  mov     [rbp+0B0h+ho], rax
0x1800daa02  cmp     r12d, ebx
0x1800daa05  jge     loc_1800DAB32
0x1800daa0b  mov     edx, [rax]
0x1800daa0d  add     rax, 4
0x1800daa11  mov     [rbp+0B0h+var_D0], rax
0x1800daa15  mov     eax, edx
0x1800daa17  shr     eax, 18h
0x1800daa1a  cmp     al, 4
0x1800daa1c  ja      short loc_1800DAA3E
0x1800daa1e  test    r8d, r8d
0x1800daa21  jnz     short loc_1800DAA7C
0x1800daa23  mov     r8d, 1
0x1800daa29  mov     r10d, [rbp+0B0h+var_118]
0x1800daa2d  add     r12d, r8d
0x1800daa30  mov     r8d, [rbp+0B0h+var_11C]
0x1800daa34  mov     rax, [rbp+0B0h+var_D0]
0x1800daa38  mov     r13, [rbp+0B0h+h]
0x1800daa3c  jmp     short loc_1800DAA02
0x1800daa3e  test    r8d, r8d
0x1800daa41  mov     r8d, 1
0x1800daa47  jnz     short loc_1800DAA5F
0x1800daa49  movsxd  rax, r12d
0x1800daa4c  mov     [rbp+0B0h+var_118], r12d
0x1800daa50  mov     [rbp+0B0h+var_11C], r8d
0x1800daa54  lea     r13, [r9+rax*4]
0x1800daa58  mov     [rbp+0B0h+h], r13
0x1800daa5c  mov     rcx, r13
0x1800daa5f  mov     [rcx], dl
0x1800daa61  mov     eax, edx
0x1800daa63  add     rcx, r8
0x1800daa66  shr     eax, 8
0x1800daa69  shr     edx, 10h
0x1800daa6c  mov     [rcx], al
0x1800daa6e  add     rcx, r8
0x1800daa71  mov     [rcx], dl
0x1800daa73  add     rcx, r8
0x1800daa76  mov     [rbp+0B0h+hdcSrc], rcx
0x1800daa7a  jmp     short loc_1800DAA29
0x1800daa7c  stmxcsr [rbp+0B0h+var_130]
0x1800daa80  mov     ebx, [rbp+0B0h+var_130]
0x1800daa83  mov     edx, r10d
0x1800daa86  mov     ecx, [rsi+30h]
0x1800daa89  mov     eax, ebx
0x1800daa8b  imul    edx, [rsi+2Ch]
0x1800daa8f  and     eax, edi
0x1800daa91  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x1800daa99  mov     r8d, ecx
0x1800daa9c  mov     [rbp+0B0h+var_130], eax
0x1800daa9f  xor     eax, eax
0x1800daaa1  ldmxcsr [rbp+0B0h+var_130]
0x1800daaa5  mov     [rbp+0B0h+var_11C], eax
0x1800daaa8  mov     eax, r12d
0x1800daaab  add     edx, [r15]; xDest
0x1800daaae  sub     eax, r10d
0x1800daab1  mov     dword ptr [rbp+0B0h+bmi+4], eax
0x1800daab4  mov     eax, r12d
0x1800daab7  sub     eax, r10d
0x1800daaba  imul    r8d, r11d
0x1800daabe  xor     r11d, r11d
0x1800daac1  lea     r10, [rbp+0B0h+bmi]
0x1800daac5  mov     [rsp+1B0h+iUsage], r11d; iUsage
0x1800daaca  mov     r9d, eax
0x1800daacd  imul    r9d, [rsi+2Ch]; DestWidth
0x1800daad2  mov     [rsp+1B0h+lpbmi], r10; lpbmi
0x1800daad7  add     r8d, [r15+4]; yDest
0x1800daadb  mov     [rsp+1B0h+lpBits], r13; lpBits
0x1800daae0  mov     r13, [rbp+0B0h+hdc]
0x1800daae4  mov     [rsp+1B0h+SrcHeight], 1; SrcHeight
0x1800daaec  mov     [rsp+1B0h+SrcWidth], eax; SrcWidth
0x1800daaf0  mov     [rsp+1B0h+ySrc], r11d; ySrc
0x1800daaf5  mov     [rsp+1B0h+xSrc], r11d; xSrc
0x1800daafa  mov     [rsp+1B0h+DestHeight], ecx; DestHeight
0x1800daafe  mov     rcx, r13; hdc
0x1800dab01  call    cs:__imp_StretchDIBits
0x1800dab08  nop     dword ptr [rax+rax+00h]
0x1800dab0d  mov     r11d, [rbp+0B0h+var_108]
0x1800dab11  and     ebx, edi
0x1800dab13  test    eax, eax
0x1800dab15  jz      loc_1800DACF0
0x1800dab1b  mov     rcx, [rbp+0B0h+hdcSrc]
0x1800dab1f  mov     r9, [rbp+0B0h+ho]
0x1800dab23  mov     [rbp+0B0h+var_130], ebx
0x1800dab26  ldmxcsr [rbp+0B0h+var_130]
0x1800dab2a  mov     ebx, [rbp+0B0h+var_114]
0x1800dab2d  jmp     loc_1800DAA23
0x1800dab32  mov     r13, [rbp+0B0h+hdc]
0x1800dab36  test    r8d, r8d
0x1800dab39  jz      loc_1800DAD19
0x1800dab3f  stmxcsr [rbp+0B0h+var_130]
0x1800dab43  mov     ebx, [rbp+0B0h+var_130]
0x1800dab46  lea     rcx, [rbp+0B0h+bmi]
0x1800dab4a  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x1800dab52  mov     eax, ebx
0x1800dab54  mov     [rsp+1B0h+iUsage], 0; iUsage
0x1800dab5c  and     eax, edi
0x1800dab5e  mov     [rsp+1B0h+lpbmi], rcx; lpbmi
0x1800dab63  mov     edx, r10d
0x1800dab66  imul    edx, [rsi+2Ch]
0x1800dab6a  mov     rcx, [rbp+0B0h+h]
0x1800dab6e  mov     [rsp+1B0h+lpBits], rcx; lpBits
0x1800dab73  mov     rcx, r13; hdc
0x1800dab76  mov     [rbp+0B0h+var_130], eax
0x1800dab79  xor     eax, eax
0x1800dab7b  ldmxcsr [rbp+0B0h+var_130]
0x1800dab7f  add     edx, [r15]; xDest
0x1800dab82  mov     [rbp+0B0h+var_11C], eax
0x1800dab85  mov     eax, r12d
0x1800dab88  mov     [rsp+1B0h+SrcHeight], 1; SrcHeight
0x1800dab90  sub     eax, r10d
0x1800dab93  sub     r12d, r10d
0x1800dab96  mov     dword ptr [rbp+0B0h+bmi+4], eax
0x1800dab99  mov     eax, [rsi+30h]
0x1800dab9c  mov     r9d, r12d
0x1800dab9f  imul    r9d, [rsi+2Ch]; DestWidth
0x1800daba4  mov     r8d, eax
0x1800daba7  mov     [rsp+1B0h+SrcWidth], r12d; SrcWidth
0x1800dabac  imul    r8d, r11d
0x1800dabb0  mov     [rsp+1B0h+ySrc], 0; ySrc
0x1800dabb8  mov     [rsp+1B0h+xSrc], 0; xSrc
0x1800dabc0  mov     [rsp+1B0h+DestHeight], eax; DestHeight
0x1800dabc4  add     r8d, [r15+4]; yDest
0x1800dabc8  call    cs:__imp_StretchDIBits
0x1800dabcf  nop     dword ptr [rax+rax+00h]
0x1800dabd4  and     ebx, edi
0x1800dabd6  test    eax, eax
0x1800dabd8  jnz     loc_1800DAD0A
0x1800dabde  mov     dword ptr [rsp+1B0h+var_138], ebx
0x1800dabe2  lea     r14d, [rax+1]
0x1800dabe6  ldmxcsr dword ptr [rsp+1B0h+var_138]
0x1800dabeb  mov     eax, [rsi+0B8h]
0x1800dabf1  dec     eax
0x1800dabf3  cmp     [rsi+0B4h], eax
0x1800dabf9  jz      loc_1800DB408
0x1800dabff  mov     eax, r14d
0x1800dac02  mov     rcx, [rbp+0B0h+var_48]
0x1800dac06  xor     rcx, rsp; StackCookie
0x1800dac09  call    __security_check_cookie
0x1800dac0e  add     rsp, 178h
0x1800dac15  pop     r15
0x1800dac17  pop     r14
0x1800dac19  pop     r13
0x1800dac1b  pop     r12
0x1800dac1d  pop     rdi
0x1800dac1e  pop     rsi
0x1800dac1f  pop     rbx
0x1800dac20  pop     rbp
0x1800dac21  retn
0x1800dac23  mov     rax, [rbp+0B0h+var_B8]
0x1800dac27  test    rax, rax
0x1800dac2a  jz      loc_1800DA94D
0x1800dac30  cmp     [rsi+0A0h], r14d
0x1800dac37  jnz     loc_1800DA94D
0x1800dac3d  cmp     [rsi+0A4h], r14d
0x1800dac44  jnz     short loc_1800DAC53
0x1800dac46  cmp     [rsi+0A8h], r14d
0x1800dac4d  jz      loc_1800DA94D
0x1800dac53  mov     r8, [rsp+1B0h+var_138]; struct DpContext *
0x1800dac58  mov     r9, rax; struct DpPath *
0x1800dac5b  mov     rdx, rbx; HDC
0x1800dac5e  mov     rcx, rsi; this
0x1800dac61  call    ?SetupPathClipping@DriverPrint@@MEAAXPEAUHDC__@@PEAVDpContext@@PEBVDpPath@@@Z; DriverPrint::SetupPathClipping(HDC__ *,DpContext *,DpPath const *)
0x1800dac66  mov     r11d, [rbp+0B0h+var_108]
0x1800dac6a  mov     rcx, [rbp+0B0h+var_C8]
0x1800dac6e  mov     r8d, [rbp+0B0h+var_11C]
0x1800dac72  mov     rdx, [rbp+0B0h+var_E0]
0x1800dac76  mov     r9, [rbp+0B0h+var_C0]
0x1800dac7a  jmp     loc_1800DA94D
0x1800dac7f  movups  xmm0, xmmword ptr [rcx+588h]
0x1800dac86  movups  xmmword ptr [rbp+0B0h+bmi], xmm0
0x1800dac8a  movups  xmm1, xmmword ptr [rcx+598h]
0x1800dac91  movups  xmmword ptr [rbp+0B0h+bmi+10h], xmm1
0x1800dac95  movups  xmm0, xmmword ptr [rcx+5A8h]
0x1800dac9c  movups  xmmword ptr [rbp+0B0h+bmi+20h], xmm0
0x1800daca0  mov     eax, [rcx+5B8h]
0x1800daca6  mov     [rbp+0B0h+var_80], eax
0x1800daca9  jmp     loc_1800DA971
0x1800dacae  movups  xmm0, xmmword ptr [rcx+5D4h]
0x1800dacb5  mov     rdx, r9; void *
0x1800dacb8  movups  xmmword ptr [rbp+0B0h+var_78], xmm0
  ... truncated ...
```
