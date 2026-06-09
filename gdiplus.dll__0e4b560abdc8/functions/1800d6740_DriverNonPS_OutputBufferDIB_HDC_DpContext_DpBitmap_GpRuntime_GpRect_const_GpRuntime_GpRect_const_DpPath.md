# DriverNonPS::OutputBufferDIB(HDC__ *,DpContext *,DpBitmap *,GpRuntime::GpRect const *,GpRuntime::GpRect const *,DpPath *)

- ea: `0x1800d6740`
- end: `0x1800d733d`
- name: `?OutputBufferDIB@DriverNonPS@@UEAA?AW4Status@@PEAUHDC__@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@3PEAVDpPath@@@Z`
- size: `3069`
- prototype: `__int64 __fastcall(_DWORD *, HDC, struct DpContext *, __int64, __int64, _DWORD *, const struct DpPath *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800aeca0`
- `0x1800c1c50`
- `0x1800d6740`
- `0x1800d7344`
- `0x1800e9380`
- `0x180130810`
- `0x180135220`
- `0x1801358f0`

## import_xrefs

- `GDI32!StretchBlt` at `0x1800d6f38`
- `GDI32!StretchBlt` at `0x1800d71a1`
- `GDI32!StretchBlt` at `0x1800d6f38`
- `GDI32!StretchBlt` at `0x1800d71a1`
- `GDI32!SetStretchBltMode` at `0x1800d6d82`
- `GDI32!SetStretchBltMode` at `0x1800d6d82`
- `GDI32!StretchDIBits` at `0x1800d6aaf`
- `GDI32!StretchDIBits` at `0x1800d6ba0`
- `GDI32!StretchDIBits` at `0x1800d6ca3`
- `GDI32!StretchDIBits` at `0x1800d6e82`
- `GDI32!StretchDIBits` at `0x1800d7075`
- `GDI32!StretchDIBits` at `0x1800d7117`
- `GDI32!StretchDIBits` at `0x1800d7271`
- `GDI32!StretchDIBits` at `0x1800d6aaf`
- `GDI32!StretchDIBits` at `0x1800d6ba0`
- `GDI32!StretchDIBits` at `0x1800d6ca3`
- `GDI32!StretchDIBits` at `0x1800d6e82`
- `GDI32!StretchDIBits` at `0x1800d7075`
- `GDI32!StretchDIBits` at `0x1800d7117`
- `GDI32!StretchDIBits` at `0x1800d7271`
- `GDI32!SetBrushOrgEx` at `0x1800d6da3`
- `GDI32!SetBrushOrgEx` at `0x1800d6da3`
- `GDI32!SetBkColor` at `0x1800d6ed8`
- `GDI32!SetBkColor` at `0x1800d6ed8`
- `GDI32!SetTextColor` at `0x1800d6eea`
- `GDI32!SetTextColor` at `0x1800d6eea`
- `GDI32!CreateBitmap` at `0x1800d6d3d`
- `GDI32!CreateBitmap` at `0x1800d6d3d`
- `GDI32!PatBlt` at `0x1800d6e06`
- `GDI32!PatBlt` at `0x1800d6fd1`
- `GDI32!PatBlt` at `0x1800d71ed`
- `GDI32!PatBlt` at `0x1800d6e06`
- `GDI32!PatBlt` at `0x1800d6fd1`
- `GDI32!PatBlt` at `0x1800d71ed`
- `GDI32!GdiFlush` at `0x1800d67a7`
- `GDI32!GdiFlush` at `0x1800d67a7`
- `GDI32!DeleteDC` at `0x1800d72a3`
- `GDI32!DeleteDC` at `0x1800d72a3`
- `GDI32!SelectObject` at `0x1800d6d6d`
- `GDI32!SelectObject` at `0x1800d6ddd`
- `GDI32!SelectObject` at `0x1800d6e1e`
- `GDI32!SelectObject` at `0x1800d6f9c`
- `GDI32!SelectObject` at `0x1800d7204`
- `GDI32!SelectObject` at `0x1800d6d6d`
- `GDI32!SelectObject` at `0x1800d6ddd`
- `GDI32!SelectObject` at `0x1800d6e1e`
- `GDI32!SelectObject` at `0x1800d6f9c`
- `GDI32!SelectObject` at `0x1800d7204`
- `GDI32!CreateCompatibleDC` at `0x1800d6cf2`
- `GDI32!CreateCompatibleDC` at `0x1800d6cf2`
- `GDI32!DeleteObject` at `0x1800d72bb`
- `GDI32!DeleteObject` at `0x1800d72bb`

## pseudocode

```c
__int64 __fastcall DriverNonPS::OutputBufferDIB(
        _DWORD *a1,
        HDC a2,
        struct DpContext *a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        const struct DpPath *a7)
{
  unsigned int v7; // r14d
  EpScanDIB *v8; // rsi
  HDC v9; // rbx
  int ActualBounds; // eax
  int DestHeight; // r15d
  int v13; // r8d
  int v14; // r13d
  EpScanDIB *v15; // rcx
  char *v16; // r10
  int SrcHeight; // esi
  int v18; // r11d
  char *v19; // rdx
  int v20; // r9d
  int v21; // edx
  int v22; // r8d
  int v23; // eax
  int v24; // r15d
  char *v25; // rax
  const void *lpBits; // r10
  _BYTE *v27; // r13
  char *v28; // rax
  struct DpContext *v29; // rbx
  int v30; // ecx
  _BYTE *v31; // r13
  int v32; // r9d
  int v33; // r8d
  int v34; // eax
  int v35; // r8d
  int v36; // r8d
  int v37; // edx
  int v38; // ebx
  int v39; // edx
  int v40; // ecx
  HBITMAP Bitmap; // rax
  HBRUSH GdiBrush; // rax
  int v43; // eax
  unsigned int v44; // ebx
  int v45; // eax
  HBRUSH v46; // rax
  int v47; // r8d
  int v48; // edx
  int v49; // ecx
  char *v50; // rcx
  int v51; // r8d
  int v52; // edx
  int v53; // eax
  BOOL v54; // r12d
  int v56; // [rsp+70h] [rbp-90h]
  unsigned int v57; // [rsp+70h] [rbp-90h]
  unsigned int v58; // [rsp+70h] [rbp-90h]
  unsigned int v59; // [rsp+70h] [rbp-90h]
  BOOL v60; // [rsp+70h] [rbp-90h]
  unsigned int v61; // [rsp+70h] [rbp-90h]
  int v62; // [rsp+74h] [rbp-8Ch]
  unsigned int v63; // [rsp+74h] [rbp-8Ch]
  unsigned int v64; // [rsp+74h] [rbp-8Ch]
  int v65; // [rsp+78h] [rbp-88h]
  unsigned int v66; // [rsp+78h] [rbp-88h]
  unsigned int v67; // [rsp+78h] [rbp-88h]
  unsigned int v68; // [rsp+78h] [rbp-88h]
  unsigned int v69; // [rsp+78h] [rbp-88h]
  int v70; // [rsp+7Ch] [rbp-84h]
  int v71; // [rsp+7Ch] [rbp-84h]
  int v72; // [rsp+80h] [rbp-80h]
  int v73; // [rsp+80h] [rbp-80h]
  int v75; // [rsp+90h] [rbp-70h]
  int xSrc; // [rsp+94h] [rbp-6Ch]
  int v77; // [rsp+98h] [rbp-68h]
  HDC hdcSrc; // [rsp+A0h] [rbp-60h]
  int SrcWidth; // [rsp+A8h] [rbp-58h]
  HGDIOBJ h; // [rsp+B0h] [rbp-50h]
  char *ha; // [rsp+B0h] [rbp-50h]
  char *v82; // [rsp+B8h] [rbp-48h]
  char *v83; // [rsp+C8h] [rbp-38h]
  char *v84; // [rsp+C8h] [rbp-38h]
  EpScanDIB *v85; // [rsp+D0h] [rbp-30h]
  HBITMAP ho; // [rsp+D8h] [rbp-28h]
  struct DpContext *v88; // [rsp+E0h] [rbp-20h]
  char *v89; // [rsp+E8h] [rbp-18h]
  int v90; // [rsp+F8h] [rbp-8h] BYREF
  int v91; // [rsp+FCh] [rbp-4h]
  int DestWidth; // [rsp+100h] [rbp+0h]
  int nHeight; // [rsp+104h] [rbp+4h]
  _BYTE bmi[48]; // [rsp+108h] [rbp+8h] BYREF
  int v95; // [rsp+138h] [rbp+38h]
  _BYTE lpbmi[48]; // [rsp+140h] [rbp+40h] BYREF

  v7 = 0;
  v8 = *(EpScanDIB **)(a4 + 128);
  v9 = a2;
  h = 0;
  v85 = v8;
  GdiFlush();
  ActualBounds = EpScanDIB::GetActualBounds(v8, (struct GpRuntime::GpRect *)&v90);
  DestHeight = nHeight;
  v13 = ActualBounds;
  v14 = DestWidth;
  v15 = v8;
  hdcSrc = 0;
  ho = 0;
  v83 = 0;
  v16 = (char *)*((_QWORD *)v8 + 172);
  v56 = ActualBounds;
  v82 = v16;
  SrcHeight = nHeight / a1[12];
  SrcWidth = DestWidth / a1[11];
  v72 = v91;
  v18 = v91 / a1[12];
  v75 = v18;
  v70 = v90;
  v19 = (char *)*((_QWORD *)v15 + 185);
  xSrc = v90 / a1[11];
  v65 = *((_DWORD *)v15 + 372);
  v62 = *((_DWORD *)v15 + 332);
  v89 = v19;
  memset(bmi, 0, sizeof(bmi));
  v95 = 0;
  memset(lpbmi, 0, sizeof(lpbmi));
  if ( !a1[45] && a7 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::SetupPathClipping((DriverPrint *)a1, v9, a3, a7);
    v18 = v75;
    v15 = v85;
    v13 = v56;
    v16 = v82;
    v19 = v89;
  }
  if ( v13 && v14 && DestHeight )
  {
    if ( v16 )
    {
      *(_OWORD *)bmi = *(_OWORD *)((char *)v15 + 1416);
      *(_OWORD *)&bmi[16] = *(_OWORD *)((char *)v15 + 1432);
      *(_OWORD *)&bmi[32] = *(_OWORD *)((char *)v15 + 1448);
      v95 = *((_DWORD *)v15 + 366);
    }
    if ( v19 )
    {
      *(_OWORD *)lpbmi = *(_OWORD *)((char *)v15 + 1492);
      *(_OWORD *)&lpbmi[16] = *(_OWORD *)((char *)v15 + 1508);
      *(_OWORD *)&lpbmi[32] = *(_OWORD *)((char *)v15 + 1524);
      if ( AllWhite((const struct tagBITMAPINFO *)lpbmi, v19) )
        goto LABEL_74;
      v13 = v56;
      v16 = v82;
    }
    if ( a1[42] )
    {
      v20 = xSrc;
      v21 = 0;
      *(_DWORD *)&bmi[16] = 0;
      v22 = 0;
      v71 = 0;
      v73 = 0;
      *(_WORD *)&bmi[14] = 24;
      *(_DWORD *)&bmi[8] = 1;
      v23 = v18 + SrcHeight;
      v77 = v18 + SrcHeight;
      while ( v18 < v23 )
      {
        v24 = v20;
        v25 = &v16[*((_DWORD *)v85 + 332) * (*(_DWORD *)(a5 + 12) - v18 - 1)];
        lpBits = 0;
        ha = 0;
        v27 = 0;
        v28 = &v25[4 * v20];
        v29 = (struct DpContext *)v28;
        v88 = (struct DpContext *)v28;
        while ( v24 < xSrc + SrcWidth )
        {
          v30 = *(_DWORD *)v28;
          v84 = v28 + 4;
          if ( HIBYTE(*(_DWORD *)v28) <= 4u )
          {
            if ( v22 )
            {
              v57 = _mm_getcsr() & 0xFFFFFFC0;
              v32 = a1[11] * (v24 - v21);
              _mm_setcsr(v57);
              v33 = a6[1] + a1[12] * v18;
              v71 = 0;
              *(_DWORD *)&bmi[4] = v24 - v21;
              v34 = StretchDIBits(
                      a2,
                      *a6 + a1[11] * v21,
                      v33,
                      v32,
                      a1[12],
                      0,
                      0,
                      v24 - v21,
                      1,
                      lpBits,
                      (const BITMAPINFO *)bmi,
                      0,
                      0xCC0020u);
              v18 = v75;
              if ( !v34 )
              {
                v21 = v73;
                v22 = 0;
                v7 = 1;
                lpBits = ha;
                _mm_setcsr(v57);
                break;
              }
              _mm_setcsr(v57);
              v29 = v88;
            }
          }
          else
          {
            if ( !v22 )
            {
              v73 = v24;
              v71 = 1;
              ha = (char *)v29 + 4 * v24;
              v27 = ha;
            }
            *v27 = v30;
            v31 = v27 + 1;
            *v31++ = BYTE1(v30);
            *v31 = BYTE2(v30);
            v27 = v31 + 1;
          }
          v22 = v71;
          ++v24;
          v21 = v73;
          v28 = v84;
          lpBits = ha;
        }
        if ( v22 )
        {
          v58 = _mm_getcsr() & 0xFFFFFFC0;
          _mm_setcsr(v58);
          v71 = 0;
          v35 = a6[1] + a1[12] * v18;
          *(_DWORD *)&bmi[4] = v24 - v21;
          if ( !StretchDIBits(
                  a2,
                  *a6 + a1[11] * v21,
                  v35,
                  a1[11] * (v24 - v21),
                  a1[12],
                  0,
                  0,
                  v24 - v21,
                  1,
                  lpBits,
                  (const BITMAPINFO *)bmi,
                  0,
                  0xCC0020u) )
          {
            v7 = 1;
            _mm_setcsr(v58);
            goto LABEL_69;
          }
          v22 = 0;
          v18 = v75;
          _mm_setcsr(v58);
        }
        v21 = v73;
        ++v18;
        v20 = xSrc;
        v23 = v77;
        v16 = v82;
        v75 = v18;
      }
      goto LABEL_69;
    }
    if ( !a1[40] && a1[41] )
    {
      if ( v14 > 0 && DestHeight > 0 )
      {
        v36 = a6[1] + v72;
        v37 = *a6 + v70;
        v59 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v59);
        *(_DWORD *)&bmi[8] = SrcHeight;
        v13 = StretchDIBits(
                a2,
                v37,
                v36,
                v14,
                DestHeight,
                xSrc,
                0,
                SrcWidth,
                SrcHeight,
                &v16[v62 * (*(_DWORD *)(a5 + 12) - SrcHeight - v18)],
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u);
        _mm_setcsr(v59);
      }
      LOBYTE(v7) = v13 == 0;
      goto LABEL_69;
    }
    if ( a1[16] == 2 )
    {
      v38 = _mm_getcsr();
      _mm_setcsr(v38 & 0xFFFFFFC0);
      hdcSrc = CreateCompatibleDC(a2);
      if ( !hdcSrc )
        goto LABEL_42;
      v39 = -DestHeight;
      if ( DestHeight > 0 )
        v39 = DestHeight;
      v40 = -v14;
      if ( v14 > 0 )
        v40 = v14;
      Bitmap = CreateBitmap(v40, v39, 1u, 1u, 0);
      ho = Bitmap;
      if ( !Bitmap )
      {
LABEL_42:
        v7 = 1;
        _mm_setcsr(v38 & 0xFFFFFFC0);
LABEL_69:
        if ( hdcSrc )
          DeleteDC(hdcSrc);
        if ( ho )
          DeleteObject(ho);
        v9 = a2;
        goto LABEL_74;
      }
      SelectObject(hdcSrc, Bitmap);
      SetStretchBltMode(hdcSrc, 4);
      SetBrushOrgEx(hdcSrc, -*a6, -a6[1], 0);
      if ( a1[40] )
      {
        ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
        GdiBrush = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
        h = SelectObject(hdcSrc, GdiBrush);
        v60 = PatBlt(hdcSrc, 0, 0, v14, DestHeight, 0xF00021u);
        SelectObject(hdcSrc, h);
        v43 = v60;
      }
      else
      {
        v43 = StretchDIBits(
                hdcSrc,
                0,
                0,
                v14,
                DestHeight,
                xSrc,
                *(_DWORD *)(a5 + 12) - SrcHeight - v75,
                SrcWidth,
                SrcHeight,
                v82,
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u);
      }
      v44 = v38 & 0xFFFFFFC0;
      if ( !v43 )
      {
        v7 = 1;
        _mm_setcsr(v44);
        goto LABEL_69;
      }
      _mm_setcsr(v44);
      v63 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v63);
      SetBkColor(a2, 0xFFFFFFu);
      SetTextColor(a2, 0);
      v45 = StretchBlt(a2, *a6 + v70, a6[1] + v72, v14, DestHeight, hdcSrc, 0, 0, v14, DestHeight, 0x660046u);
      _mm_setcsr(v63);
    }
    else if ( a1[40] )
    {
      v64 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v64);
      ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
      v46 = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
      h = SelectObject(a2, v46);
      v45 = PatBlt(a2, *a6 + v70, a6[1] + v72, v14, DestHeight, 0x5A0049u);
      _mm_setcsr(v64);
    }
    else
    {
      v47 = a6[1] + v72;
      v48 = *a6 + v70;
      v61 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v61);
      *(_DWORD *)&bmi[8] = SrcHeight;
      v83 = &v82[v62 * (*(_DWORD *)(a5 + 12) - SrcHeight - v75)];
      v45 = StretchDIBits(
              a2,
              v48,
              v47,
              v14,
              DestHeight,
              xSrc,
              0,
              SrcWidth,
              SrcHeight,
              v83,
              (const BITMAPINFO *)bmi,
              0,
              0x660046u);
      _mm_setcsr(v61);
    }
    if ( !v45 )
    {
      v7 = 1;
      goto LABEL_69;
    }
    v49 = a6[3] - v72 - DestHeight;
    *(_DWORD *)&lpbmi[8] = DestHeight;
    v50 = &v89[v65 * v49];
    v66 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v66);
    if ( !StretchDIBits(
            a2,
            v70 + *a6,
            v72 + a6[1],
            v14,
            DestHeight,
            v70,
            0,
            v14,
            DestHeight,
            v50,
            (const BITMAPINFO *)lpbmi,
            0,
            0x8800C6u) )
    {
      v7 = 1;
      _mm_setcsr(v66);
      goto LABEL_69;
    }
    v51 = a6[1] + v72;
    v52 = *a6 + v70;
    _mm_setcsr(v66);
    if ( hdcSrc )
    {
      v67 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v67);
      v53 = StretchBlt(a2, v52, v51, v14, DestHeight, hdcSrc, 0, 0, v14, DestHeight, 0x660046u);
      _mm_setcsr(v67);
    }
    else
    {
      if ( a1[40] )
      {
        v68 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v68);
        v54 = PatBlt(a2, v52, v51, v14, DestHeight, 0x5A0049u);
        SelectObject(a2, h);
        _mm_setcsr(v68);
        goto LABEL_67;
      }
      v69 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v69);
      v53 = StretchDIBits(
              a2,
              v52,
              v51,
              v14,
              DestHeight,
              xSrc,
              0,
              SrcWidth,
              SrcHeight,
              v83,
              (const BITMAPINFO *)bmi,
              0,
              0x660046u);
      _mm_setcsr(v69);
    }
    v54 = v53;
LABEL_67:
    if ( !v54 )
      v7 = 1;
    goto LABEL_69;
  }
LABEL_74:
  if ( a1[45] == a1[46] - 1 && a7 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::RestoreClipping((DriverPrint *)a1, v9, a1[83], 0);
    a1[83] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800d6740  push    rbp
0x1800d6742  push    rbx
0x1800d6743  push    rsi
0x1800d6744  push    rdi
0x1800d6745  push    r12
0x1800d6747  push    r13
0x1800d6749  push    r14
0x1800d674b  push    r15
0x1800d674d  lea     rbp, [rsp-88h]
0x1800d6755  sub     rsp, 188h
0x1800d675c  mov     rax, cs:__security_cookie
0x1800d6763  xor     rax, rsp
0x1800d6766  mov     [rbp+0C0h+var_50], rax
0x1800d676a  mov     rax, [rbp+0C0h+arg_20]
0x1800d6771  xor     r14d, r14d
0x1800d6774  mov     rsi, [r9+80h]
0x1800d677b  mov     rbx, rdx
0x1800d677e  mov     r12, [rbp+0C0h+arg_28]
0x1800d6785  mov     rdi, rcx
0x1800d6788  and     [rbp+0C0h+h], r14
0x1800d678c  mov     [rbp+0C0h+var_100], rax
0x1800d6790  mov     rax, [rbp+0C0h+arg_30]
0x1800d6797  mov     [rbp+0C0h+var_D0], rax
0x1800d679b  mov     [rbp+0C0h+var_E0], r8
0x1800d679f  mov     [rbp+0C0h+hdc], rdx
0x1800d67a3  mov     [rbp+0C0h+var_F0], rsi
0x1800d67a7  call    cs:__imp_GdiFlush
0x1800d67ae  nop     dword ptr [rax+rax+00h]
0x1800d67b3  lea     rdx, [rbp+0C0h+var_C8]; struct GpRuntime::GpRect *
0x1800d67b7  mov     rcx, rsi; this
0x1800d67ba  call    ?GetActualBounds@EpScanDIB@@QEAAHPEAVGpRect@GpRuntime@@@Z
0x1800d67bf  mov     r15d, [rbp+0C0h+nHeight]
0x1800d67c3  mov     r8d, eax
0x1800d67c6  mov     r13d, [rbp+0C0h+DestWidth]
0x1800d67ca  xorps   xmm0, xmm0
0x1800d67cd  mov     rcx, [rbp+0C0h+var_F0]
0x1800d67d1  and     [rbp+0C0h+hdcSrc], r14
0x1800d67d5  and     [rbp+0C0h+ho], r14
0x1800d67d9  and     [rbp+0C0h+var_F8], r14
0x1800d67dd  mov     r10, [rcx+560h]
0x1800d67e4  mov     [rsp+1C0h+var_150], eax
0x1800d67e8  mov     eax, r15d
0x1800d67eb  cdq
0x1800d67ec  mov     [rbp+0C0h+var_108], r10
0x1800d67f0  idiv    dword ptr [rdi+30h]
0x1800d67f3  mov     esi, eax
0x1800d67f5  mov     [rbp+0C0h+var_128], eax
0x1800d67f8  mov     eax, r13d
0x1800d67fb  cdq
0x1800d67fc  idiv    dword ptr [rdi+2Ch]
0x1800d67ff  mov     [rbp+0C0h+var_118], eax
0x1800d6802  mov     eax, [rbp+0C0h+var_C4]
0x1800d6805  mov     [rbp+0C0h+var_140], eax
0x1800d6808  cdq
0x1800d6809  idiv    dword ptr [rdi+30h]
0x1800d680c  mov     r11d, eax
0x1800d680f  mov     [rbp+0C0h+var_130], eax
0x1800d6812  mov     eax, [rbp+0C0h+var_C8]
0x1800d6815  mov     [rsp+1C0h+var_144], eax
0x1800d6819  cdq
0x1800d681a  idiv    dword ptr [rdi+2Ch]
0x1800d681d  mov     rdx, [rcx+5C8h]
0x1800d6824  mov     [rbp+0C0h+var_12C], eax
0x1800d6827  mov     eax, [rcx+5D0h]
0x1800d682d  mov     [rsp+1C0h+var_148], eax
0x1800d6831  mov     eax, [rcx+530h]
0x1800d6837  mov     [rsp+1C0h+var_14C], eax
0x1800d683b  xor     eax, eax
0x1800d683d  mov     [rbp+0C0h+var_D8], rdx
0x1800d6841  movups  xmmword ptr [rbp+0C0h+bmi], xmm0
0x1800d6845  mov     [rbp+0C0h+var_88], eax
0x1800d6848  movups  xmmword ptr [rbp+0C0h+bmi+10h], xmm0
0x1800d684c  movups  xmmword ptr [rbp+0C0h+bmi+20h], xmm0
0x1800d6850  movups  xmmword ptr [rbp+0C0h+var_80], xmm0
0x1800d6854  movups  xmmword ptr [rbp+0C0h+var_80+10h], xmm0
0x1800d6858  movups  xmmword ptr [rbp+0C0h+var_80+20h], xmm0
0x1800d685c  cmp     [rdi+0B4h], eax
0x1800d6862  jnz     short loc_1800D68AF
0x1800d6864  mov     rax, [rbp+0C0h+var_D0]
0x1800d6868  test    rax, rax
0x1800d686b  jz      short loc_1800D68AF
0x1800d686d  cmp     [rdi+0A0h], r14d
0x1800d6874  jnz     short loc_1800D68AF
0x1800d6876  cmp     [rdi+0A4h], r14d
0x1800d687d  jnz     short loc_1800D6888
0x1800d687f  cmp     [rdi+0A8h], r14d
0x1800d6886  jz      short loc_1800D68AF
0x1800d6888  mov     r8, [rbp+0C0h+var_E0]; struct DpContext *
0x1800d688c  mov     r9, rax; struct DpPath *
0x1800d688f  mov     rdx, rbx; HDC
0x1800d6892  mov     rcx, rdi; this
0x1800d6895  call    ?SetupPathClipping@DriverPrint@@MEAAXPEAUHDC__@@PEAVDpContext@@PEBVDpPath@@@Z
0x1800d689a  mov     r11d, [rbp+0C0h+var_130]
0x1800d689e  mov     rcx, [rbp+0C0h+var_F0]
0x1800d68a2  mov     r8d, [rsp+1C0h+var_150]
0x1800d68a7  mov     r10, [rbp+0C0h+var_108]
0x1800d68ab  mov     rdx, [rbp+0C0h+var_D8]; void *
0x1800d68af  test    r8d, r8d
0x1800d68b2  jz      loc_1800D72CB
0x1800d68b8  test    r13d, r13d
0x1800d68bb  jz      loc_1800D72CB
0x1800d68c1  test    r15d, r15d
0x1800d68c4  jz      loc_1800D72CB
0x1800d68ca  test    r10, r10
0x1800d68cd  jz      short loc_1800D68F9
0x1800d68cf  movups  xmm0, xmmword ptr [rcx+588h]
0x1800d68d6  movups  xmmword ptr [rbp+0C0h+bmi], xmm0
0x1800d68da  movups  xmm1, xmmword ptr [rcx+598h]
0x1800d68e1  movups  xmmword ptr [rbp+0C0h+bmi+10h], xmm1
0x1800d68e5  movups  xmm0, xmmword ptr [rcx+5A8h]
0x1800d68ec  movups  xmmword ptr [rbp+0C0h+bmi+20h], xmm0
0x1800d68f0  mov     eax, [rcx+5B8h]
0x1800d68f6  mov     [rbp+0C0h+var_88], eax
0x1800d68f9  test    rdx, rdx
0x1800d68fc  jz      short loc_1800D6939
0x1800d68fe  movups  xmm0, xmmword ptr [rcx+5D4h]
0x1800d6905  movups  xmmword ptr [rbp+0C0h+var_80], xmm0
0x1800d6909  movups  xmm1, xmmword ptr [rcx+5E4h]
0x1800d6910  movups  xmmword ptr [rbp+0C0h+var_80+10h], xmm1
0x1800d6914  movups  xmm0, xmmword ptr [rcx+5F4h]
0x1800d691b  lea     rcx, [rbp+0C0h+var_80]; struct tagBITMAPINFO *
0x1800d691f  movups  xmmword ptr [rbp+0C0h+var_80+20h], xmm0
0x1800d6923  call    ?AllWhite@@YA_NAEBUtagBITMAPINFO@@PEBX@Z
0x1800d6928  test    al, al
0x1800d692a  jnz     loc_1800D72CB
0x1800d6930  mov     r8d, [rsp+1C0h+var_150]
0x1800d6935  mov     r10, [rbp+0C0h+var_108]
0x1800d6939  cmp     [rdi+0A8h], r14d
0x1800d6940  jz      loc_1800D6BEF
0x1800d6946  mov     r9d, [rbp+0C0h+var_12C]
0x1800d694a  xor     edx, edx
0x1800d694c  and     dword ptr [rbp+0C0h+bmi+10h], edx
0x1800d694f  xor     r8d, r8d
0x1800d6952  mov     [rsp+1C0h+var_144], r8d
0x1800d6957  mov     [rbp+0C0h+var_140], edx
0x1800d695a  lea     eax, [rdx+18h]
0x1800d695d  mov     word ptr [rbp+0C0h+bmi+0Eh], ax
0x1800d6961  lea     r13d, [r8+1]
0x1800d6965  mov     eax, [rbp+0C0h+var_118]
0x1800d6968  add     eax, r9d
0x1800d696b  mov     dword ptr [rbp+0C0h+bmi+8], r13d
0x1800d696f  mov     [rsp+1C0h+var_14C], eax
0x1800d6973  lea     eax, [r11+rsi]
0x1800d6977  mov     [rbp+0C0h+var_128], eax
0x1800d697a  mov     esi, 0FFFFFFC0h
0x1800d697f  cmp     r11d, eax
0x1800d6982  jge     loc_1800D7297
0x1800d6988  mov     rax, [rbp+0C0h+var_100]
0x1800d698c  mov     r15d, r9d
0x1800d698f  mov     rcx, [rbp+0C0h+var_F0]
0x1800d6993  mov     eax, [rax+0Ch]
0x1800d6996  sub     eax, r11d
0x1800d6999  sub     eax, r13d
0x1800d699c  imul    eax, [rcx+530h]
0x1800d69a3  movsxd  rcx, r9d
0x1800d69a6  add     rax, r10
0x1800d69a9  xor     r10d, r10d
0x1800d69ac  mov     [rbp+0C0h+h], r10
0x1800d69b0  xor     r13d, r13d
0x1800d69b3  lea     rax, [rax+rcx*4]
0x1800d69b7  mov     rbx, rax
0x1800d69ba  mov     [rbp+0C0h+var_E0], rax
0x1800d69be  cmp     r15d, [rsp+1C0h+var_14C]
0x1800d69c3  jge     loc_1800D6B0F
0x1800d69c9  mov     ecx, [rax]
0x1800d69cb  add     rax, 4
0x1800d69cf  mov     [rbp+0C0h+var_F8], rax
0x1800d69d3  mov     eax, ecx
0x1800d69d5  shr     eax, 18h
0x1800d69d8  cmp     al, 4
0x1800d69da  jbe     short loc_1800D6A1E
0x1800d69dc  mov     edx, 1
0x1800d69e1  test    r8d, r8d
0x1800d69e4  jnz     short loc_1800D69FC
0x1800d69e6  movsxd  rax, r15d
0x1800d69e9  mov     [rbp+0C0h+var_140], r15d
0x1800d69ed  mov     [rsp+1C0h+var_144], edx
0x1800d69f1  lea     r10, [rbx+rax*4]
0x1800d69f5  mov     [rbp+0C0h+h], r10
0x1800d69f9  mov     r13, r10
0x1800d69fc  mov     [r13+0], cl
0x1800d6a00  mov     eax, ecx
0x1800d6a02  add     r13, rdx
0x1800d6a05  shr     eax, 8
0x1800d6a08  shr     ecx, 10h
0x1800d6a0b  mov     [r13+0], al
0x1800d6a0f  add     r13, rdx
0x1800d6a12  mov     [r13+0], cl
0x1800d6a16  add     r13, rdx
0x1800d6a19  jmp     loc_1800D6AD7
0x1800d6a1e  test    r8d, r8d
0x1800d6a21  jz      loc_1800D6AD2
0x1800d6a27  stmxcsr [rsp+1C0h+var_150]
0x1800d6a2c  mov     ebx, [rsp+1C0h+var_150]
0x1800d6a30  lea     rcx, [rbp+0C0h+bmi]
0x1800d6a34  mov     [rsp+1C0h+rop], 0CC0020h; rop
0x1800d6a3c  mov     r8d, r11d
0x1800d6a3f  imul    r8d, [rdi+30h]
0x1800d6a44  xor     r11d, r11d
0x1800d6a47  mov     [rsp+1C0h+iUsage], r11d; iUsage
0x1800d6a4c  mov     eax, ebx
0x1800d6a4e  and     eax, esi
0x1800d6a50  mov     [rsp+1C0h+lpbmi], rcx; lpbmi
0x1800d6a55  mov     rcx, [rbp+0C0h+hdc]; hdc
0x1800d6a59  mov     r9d, r15d
0x1800d6a5c  mov     [rsp+1C0h+var_150], eax
0x1800d6a60  sub     r9d, edx
0x1800d6a63  imul    r9d, [rdi+2Ch]; DestWidth
0x1800d6a68  xor     eax, eax
0x1800d6a6a  ldmxcsr [rsp+1C0h+var_150]
0x1800d6a6f  add     r8d, [r12+4]; yDest
0x1800d6a74  mov     [rsp+1C0h+var_144], eax
0x1800d6a78  mov     eax, r15d
0x1800d6a7b  sub     eax, edx
0x1800d6a7d  mov     [rsp+1C0h+lpBits], r10; lpBits
0x1800d6a82  mov     dword ptr [rbp+0C0h+bmi+4], eax
0x1800d6a85  mov     eax, r15d
0x1800d6a88  sub     eax, edx
0x1800d6a8a  mov     [rsp+1C0h+SrcHeight], 1; SrcHeight
0x1800d6a92  imul    edx, [rdi+2Ch]
0x1800d6a96  mov     [rsp+1C0h+SrcWidth], eax; SrcWidth
0x1800d6a9a  mov     eax, [rdi+30h]
0x1800d6a9d  mov     [rsp+1C0h+ySrc], r11d; ySrc
0x1800d6aa2  mov     [rsp+1C0h+xSrc], r11d; xSrc
0x1800d6aa7  add     edx, [r12]; xDest
0x1800d6aab  mov     [rsp+1C0h+DestHeight], eax; DestHeight
0x1800d6aaf  call    cs:__imp_StretchDIBits
0x1800d6ab6  nop     dword ptr [rax+rax+00h]
0x1800d6abb  mov     r11d, [rbp+0C0h+var_130]
0x1800d6abf  and     ebx, esi
0x1800d6ac1  test    eax, eax
0x1800d6ac3  jz      short loc_1800D6AEF
0x1800d6ac5  mov     [rsp+1C0h+var_150], ebx
0x1800d6ac9  ldmxcsr [rsp+1C0h+var_150]
0x1800d6ace  mov     rbx, [rbp+0C0h+var_E0]
0x1800d6ad2  mov     edx, 1
0x1800d6ad7  mov     r8d, [rsp+1C0h+var_144]
0x1800d6adc  add     r15d, edx
0x1800d6adf  mov     edx, [rbp+0C0h+var_140]
0x1800d6ae2  mov     rax, [rbp+0C0h+var_F8]
0x1800d6ae6  mov     r10, [rbp+0C0h+h]
0x1800d6aea  jmp     loc_1800D69BE
0x1800d6aef  mov     edx, [rbp+0C0h+var_140]
0x1800d6af2  mov     r13d, 1
0x1800d6af8  mov     r8d, [rsp+1C0h+var_144]
0x1800d6afd  mov     r14d, r13d
0x1800d6b00  mov     r10, [rbp+0C0h+h]
0x1800d6b04  mov     [rsp+1C0h+var_150], ebx
0x1800d6b08  ldmxcsr [rsp+1C0h+var_150]
0x1800d6b0d  jmp     short loc_1800D6B15
0x1800d6b0f  mov     r13d, 1
0x1800d6b15  test    r8d, r8d
0x1800d6b18  jz      loc_1800D6BC4
0x1800d6b1e  stmxcsr [rsp+1C0h+var_150]
0x1800d6b23  mov     ebx, [rsp+1C0h+var_150]
0x1800d6b27  lea     rcx, [rbp+0C0h+bmi]
0x1800d6b2b  mov     [rsp+1C0h+rop], 0CC0020h; rop
0x1800d6b33  mov     eax, ebx
0x1800d6b35  and     [rsp+1C0h+iUsage], 0
0x1800d6b3a  and     eax, esi
0x1800d6b3c  mov     [rsp+1C0h+var_150], eax
0x1800d6b40  mov     r8d, r11d
0x1800d6b43  imul    r8d, [rdi+30h]
0x1800d6b48  xor     eax, eax
0x1800d6b4a  ldmxcsr [rsp+1C0h+var_150]
0x1800d6b4f  mov     [rsp+1C0h+lpbmi], rcx; lpbmi
0x1800d6b54  mov     rcx, [rbp+0C0h+hdc]; hdc
0x1800d6b58  mov     [rsp+1C0h+var_144], eax
0x1800d6b5c  mov     eax, r15d
0x1800d6b5f  add     r8d, [r12+4]; yDest
0x1800d6b64  sub     eax, edx
0x1800d6b66  mov     [rsp+1C0h+lpBits], r10; lpBits
0x1800d6b6b  mov     dword ptr [rbp+0C0h+bmi+4], eax
0x1800d6b6e  mov     eax, r15d
0x1800d6b71  sub     eax, edx
0x1800d6b73  mov     [rsp+1C0h+SrcHeight], r13d; SrcHeight
0x1800d6b78  mov     [rsp+1C0h+SrcWidth], eax; SrcWidth
0x1800d6b7c  sub     r15d, edx
0x1800d6b7f  imul    r15d, [rdi+2Ch]
0x1800d6b84  imul    edx, [rdi+2Ch]
0x1800d6b88  and     [rsp+1C0h+ySrc], 0
0x1800d6b8d  mov     eax, [rdi+30h]
0x1800d6b90  and     [rsp+1C0h+xSrc], 0
0x1800d6b95  mov     r9d, r15d; DestWidth
0x1800d6b98  mov     [rsp+1C0h+DestHeight], eax; DestHeight
0x1800d6b9c  add     edx, [r12]; xDest
0x1800d6ba0  call    cs:__imp_StretchDIBits
0x1800d6ba7  nop     dword ptr [rax+rax+00h]
0x1800d6bac  and     ebx, esi
0x1800d6bae  test    eax, eax
0x1800d6bb0  jz      short loc_1800D6BDE
0x1800d6bb2  mov     r8d, [rsp+1C0h+var_144]
0x1800d6bb7  mov     r11d, [rbp+0C0h+var_130]
0x1800d6bbb  mov     [rsp+1C0h+var_150], ebx
0x1800d6bbf  ldmxcsr [rsp+1C0h+var_150]
0x1800d6bc4  mov     edx, [rbp+0C0h+var_140]
0x1800d6bc7  add     r11d, r13d
0x1800d6bca  mov     r9d, [rbp+0C0h+var_12C]
0x1800d6bce  mov     eax, [rbp+0C0h+var_128]
0x1800d6bd1  mov     r10, [rbp+0C0h+var_108]
  ... truncated ...
```
