# DoPlgBlt

- ea: `0x1801427e0`
- end: `0x1801432a9`
- name: `DoPlgBlt`
- size: `2761`
- prototype: `__int64 __fastcall(int, int, int, int, int width, int, __int64, int, __int64, int, __int64, int, int, int, int, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180140240`

## callees

- `0x1800afb24`
- `0x1800b1ee8`
- `0x1800d48b0`
- `0x1800d4f9c`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x18013e4d8`
- `0x18013ead4`
- `0x180141680`
- `0x1801417f8`
- `0x18014184c`
- `0x180141ed8`
- `0x1801427e0`
- `0x180143e38`
- `0x1801440d0`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142b77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142d1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142e92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180143025`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142b77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142d1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142e92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180143025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014322b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014323f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143257`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014326f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014322b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014323f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143257`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014326f`
- `GDI32!PlgBlt` at `0x180142c4e`
- `GDI32!PlgBlt` at `0x180142fd6`
- `GDI32!PlgBlt` at `0x180142c4e`
- `GDI32!PlgBlt` at `0x180142fd6`
- `GDI32!CreateDIBitmap` at `0x180142b19`
- `GDI32!CreateDIBitmap` at `0x180142bd8`
- `GDI32!CreateDIBitmap` at `0x180142b19`
- `GDI32!CreateDIBitmap` at `0x180142bd8`
- `GDI32!DPtoLP` at `0x180142f6c`
- `GDI32!DPtoLP` at `0x180142f6c`
- `GDI32!CreateBitmap` at `0x180142e06`
- `GDI32!CreateBitmap` at `0x180142ee1`
- `GDI32!CreateBitmap` at `0x180142e06`
- `GDI32!CreateBitmap` at `0x180142ee1`
- `GDI32!PatBlt` at `0x180142e52`
- `GDI32!PatBlt` at `0x180142f33`
- `GDI32!PatBlt` at `0x180142e52`
- `GDI32!PatBlt` at `0x180142f33`
- `GDI32!DeleteDC` at `0x180143203`
- `GDI32!DeleteDC` at `0x180143217`
- `GDI32!DeleteDC` at `0x180143203`
- `GDI32!DeleteDC` at `0x180143217`
- `GDI32!GetDIBits` at `0x180142c93`
- `GDI32!GetDIBits` at `0x180142d52`
- `GDI32!GetDIBits` at `0x18014305c`
- `GDI32!GetDIBits` at `0x180142c93`
- `GDI32!GetDIBits` at `0x180142d52`
- `GDI32!GetDIBits` at `0x18014305c`
- `GDI32!SelectObject` at `0x180142b3b`
- `GDI32!SelectObject` at `0x180142bfa`
- `GDI32!SelectObject` at `0x180142d9e`
- `GDI32!SelectObject` at `0x180142e25`
- `GDI32!SelectObject` at `0x180142f03`
- `GDI32!SelectObject` at `0x180143182`
- `GDI32!SelectObject` at `0x18014319d`
- `GDI32!SelectObject` at `0x180142b3b`
- `GDI32!SelectObject` at `0x180142bfa`
- `GDI32!SelectObject` at `0x180142d9e`
- `GDI32!SelectObject` at `0x180142e25`
- `GDI32!SelectObject` at `0x180142f03`
- `GDI32!SelectObject` at `0x180143182`
- `GDI32!SelectObject` at `0x18014319d`
- `GDI32!CreateCompatibleDC` at `0x180142b56`
- `GDI32!CreateCompatibleDC` at `0x180142b56`
- `GDI32!DeleteObject` at `0x1801431ac`
- `GDI32!DeleteObject` at `0x1801431c4`
- `GDI32!DeleteObject` at `0x1801431dc`
- `GDI32!DeleteObject` at `0x1801431f4`
- `GDI32!DeleteObject` at `0x1801431ac`
- `GDI32!DeleteObject` at `0x1801431c4`
- `GDI32!DeleteObject` at `0x1801431dc`
- `GDI32!DeleteObject` at `0x1801431f4`

## pseudocode

```c
__int64 __fastcall DoPlgBlt(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int width,
        int height,
        XFORM *a7,
        UINT a8,
        void *a9,
        unsigned int a10,
        void *a11,
        int a12,
        LONG a13,
        LONG a14,
        UINT a15,
        BITMAPINFO *a16,
        SIZE_T uBytes,
        void *a18)
{
  POINT v19; // rdx
  __int64 v20; // r8
  HDC v21; // r12
  struct tagBITMAPINFO *v22; // rdi
  struct tagBITMAPINFO *v23; // rbx
  int v24; // eax
  LONG v25; // eax
  int v26; // eax
  LONG v27; // esi
  int v28; // eax
  LONG v29; // eax
  int v30; // eax
  LONG v31; // r14d
  int v32; // eax
  LONG v33; // eax
  LONG v34; // r13d
  int v35; // eax
  int v36; // eax
  LONG v37; // eax
  LONG y; // r14d
  int v39; // eax
  const BITMAPINFO *pbmi; // r15
  HDC CompatibleDC; // rax
  HDC v42; // rsi
  HBITMAP DIBitmap; // rax
  void *v44; // r15
  unsigned int v45; // r15d
  struct tagBITMAPINFO *v46; // rax
  int v47; // r14d
  int v48; // eax
  UINT iUsage; // r13d
  HBITMAP v50; // rax
  HBITMAP v51; // r14
  _DWORD *v52; // r15
  unsigned int v53; // edx
  unsigned __int64 v54; // r13
  unsigned int CJScan; // eax
  unsigned __int64 v56; // r10
  __int64 biHeight; // r13
  HLOCAL v58; // rax
  BITMAPINFO *v59; // r15
  void *MonoDib; // rax
  int v61; // r14d
  int v62; // r15d
  HBITMAP Bitmap; // rax
  SIZE_T v64; // rdx
  struct tagBITMAPINFO *v65; // rax
  int v66; // eax
  int v67; // r15d
  int v68; // edx
  HBITMAP v69; // rax
  HBITMAP v70; // r14
  unsigned int v71; // eax
  __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  HLOCAL v74; // rax
  __int64 v75; // r14
  __int64 v76; // r8
  int v77; // eax
  SIZE_T v79; // [rsp+58h] [rbp-D8h]
  XFORM *lpxf; // [rsp+B0h] [rbp-80h]
  LONG x; // [rsp+B8h] [rbp-78h]
  unsigned __int16 v82; // [rsp+BCh] [rbp-74h] BYREF
  unsigned int Size; // [rsp+C0h] [rbp-70h]
  LONG Size_4; // [rsp+C4h] [rbp-6Ch]
  int ySrc; // [rsp+C8h] [rbp-68h]
  int xSrc; // [rsp+CCh] [rbp-64h]
  UINT ColorUse; // [rsp+D0h] [rbp-60h]
  UINT usage; // [rsp+D4h] [rbp-5Ch]
  unsigned int v89; // [rsp+D8h] [rbp-58h]
  struct tagPOINT pt; // [rsp+E0h] [rbp-50h] BYREF
  int nHeight; // [rsp+E8h] [rbp-48h]
  void *Src; // [rsp+F0h] [rbp-40h]
  void *pjBits; // [rsp+F8h] [rbp-38h]
  int v94; // [rsp+100h] [rbp-30h]
  BITMAPINFO *lpbmi; // [rsp+108h] [rbp-28h]
  HGDIOBJ v96; // [rsp+110h] [rbp-20h]
  HLOCAL hMem; // [rsp+118h] [rbp-18h]
  HLOCAL v98; // [rsp+120h] [rbp-10h]
  HGDIOBJ v99; // [rsp+128h] [rbp-8h]
  HGDIOBJ ho; // [rsp+130h] [rbp+0h]
  HGDIOBJ v101; // [rsp+138h] [rbp+8h]
  void *lpBits; // [rsp+140h] [rbp+10h]
  int v103[2]; // [rsp+148h] [rbp+18h]
  HGDIOBJ h; // [rsp+150h] [rbp+20h]
  _BYTE v105[40]; // [rsp+158h] [rbp+28h] BYREF
  BITMAPINFO v106; // [rsp+180h] [rbp+50h] BYREF
  POINT Point; // [rsp+1B0h] [rbp+80h] BYREF
  __int64 v108; // [rsp+1B8h] [rbp+88h]
  __int64 v109; // [rsp+1C0h] [rbp+90h]
  int v110; // [rsp+1C8h] [rbp+98h]
  int v111; // [rsp+1CCh] [rbp+9Ch]

  *(_QWORD *)v103 = a1;
  xSrc = a3;
  v19 = *(POINT *)a2;
  ySrc = a4;
  Point = v19;
  v20 = *(_QWORD *)(a2 + 8);
  v21 = 0;
  v22 = 0;
  v94 = uBytes;
  v23 = 0;
  usage = a8;
  Src = a9;
  Size = a10;
  pjBits = a11;
  ColorUse = a15;
  lpbmi = a16;
  lpBits = a18;
  v109 = *(_QWORD *)(a2 + 16);
  v108 = v20;
  pt = 0;
  v111 = HIDWORD(v20) + HIDWORD(v109) - v19.y;
  v82 = 0;
  memset(v105, 0, sizeof(v105));
  v89 = 0;
  v99 = 0;
  memset(&v106, 0, sizeof(v106));
  ho = 0;
  v101 = 0;
  v96 = 0;
  v98 = 0;
  hMem = 0;
  v110 = v109 + v20 - v19.x;
  if ( (unsigned int)bXformWorkhorse(&Point, 4, a1 + 84) )
  {
    v24 = v110;
    if ( (int)v109 < v110 )
      v24 = v109;
    if ( (int)v108 >= v24 )
    {
      v25 = v110;
      if ( (int)v109 < v110 )
        v25 = v109;
    }
    else
    {
      v25 = v108;
    }
    if ( Point.x >= v25 )
    {
      v26 = v110;
      if ( (int)v109 < v110 )
        v26 = v109;
      if ( (int)v108 >= v26 )
      {
        v27 = v110;
        if ( (int)v109 < v110 )
          v27 = v109;
        x = v27;
      }
      else
      {
        x = v108;
      }
    }
    else
    {
      x = Point.x;
    }
    v28 = v111;
    if ( SHIDWORD(v109) < v111 )
      v28 = HIDWORD(v109);
    if ( SHIDWORD(v108) >= v28 )
    {
      v29 = v111;
      if ( SHIDWORD(v109) < v111 )
        v29 = HIDWORD(v109);
    }
    else
    {
      v29 = HIDWORD(v108);
    }
    if ( Point.y >= v29 )
    {
      v30 = v111;
      if ( SHIDWORD(v109) < v111 )
        v30 = HIDWORD(v109);
      if ( SHIDWORD(v108) >= v30 )
      {
        v31 = v111;
        if ( SHIDWORD(v109) < v111 )
          v31 = HIDWORD(v109);
        Size_4 = v31;
      }
      else
      {
        Size_4 = HIDWORD(v108);
      }
    }
    else
    {
      Size_4 = Point.y;
    }
    v32 = v110;
    if ( (int)v109 > v110 )
      v32 = v109;
    if ( (int)v108 <= v32 )
    {
      v33 = v110;
      if ( (int)v109 > v110 )
        v33 = v109;
    }
    else
    {
      v33 = v108;
    }
    if ( Point.x <= v33 )
    {
      v35 = v110;
      if ( (int)v109 > v110 )
        v35 = v109;
      if ( (int)v108 <= v35 )
      {
        v34 = v110;
        if ( (int)v109 > v110 )
          v34 = v109;
      }
      else
      {
        v34 = v108;
      }
    }
    else
    {
      v34 = Point.x;
    }
    v36 = v111;
    if ( SHIDWORD(v109) > v111 )
      v36 = HIDWORD(v109);
    if ( SHIDWORD(v108) <= v36 )
    {
      v37 = v111;
      if ( SHIDWORD(v109) > v111 )
        v37 = HIDWORD(v109);
    }
    else
    {
      v37 = HIDWORD(v108);
    }
    if ( Point.y <= v37 )
    {
      v39 = v111;
      if ( SHIDWORD(v109) > v111 )
        v39 = HIDWORD(v109);
      if ( SHIDWORD(v108) <= v39 )
      {
        y = v111;
        if ( SHIDWORD(v109) > v111 )
          y = HIDWORD(v109);
      }
      else
      {
        y = HIDWORD(v108);
      }
    }
    else
    {
      y = Point.y;
    }
    Point.y -= Size_4;
    Point.x -= x;
    LODWORD(v108) = v108 - x;
    HIDWORD(v108) -= Size_4;
    LODWORD(v109) = v109 - x;
    HIDWORD(v109) -= Size_4;
    v110 -= x;
    v111 -= Size_4;
    if ( Size >= 0x2C )
    {
      pbmi = (const BITMAPINFO *)Src;
    }
    else
    {
      memcpy_0(&v106, Src, Size);
      pbmi = &v106;
      Size = 44;
      Src = &v106;
    }
    CompatibleDC = (HDC)hdcMakeCompatibleDC(a7);
    v42 = CompatibleDC;
    if ( CompatibleDC )
    {
      DIBitmap = CreateDIBitmap(CompatibleDC, &pbmi->bmiHeader, 6u, pjBits, pbmi, usage);
      lpxf = (XFORM *)DIBitmap;
      v44 = DIBitmap;
      if ( !DIBitmap )
      {
LABEL_125:
        DeleteDC(v42);
        if ( v21 )
          DeleteDC(v21);
        if ( v23 )
          LocalFree(v23);
        if ( v22 )
          LocalFree(v22);
        if ( hMem )
          LocalFree(hMem);
        if ( v98 )
          LocalFree(v98);
        return v89;
      }
      h = SelectObject(v42, DIBitmap);
      if ( !h )
      {
LABEL_119:
        DeleteObject(v44);
        if ( ho )
          DeleteObject(ho);
        if ( v96 )
          DeleteObject(v96);
        if ( v101 )
          DeleteObject(v101);
        goto LABEL_125;
      }
      v21 = CreateCompatibleDC(0);
      if ( !v21 )
      {
LABEL_117:
        SelectObject(v42, h);
        if ( v99 )
          SelectObject(v21, v99);
        goto LABEL_119;
      }
      v45 = Size;
      v46 = (struct tagBITMAPINFO *)LocalAlloc(0, Size);
      v23 = v46;
      if ( v46 )
      {
        memcpy_0(v46, Src, Size);
        v47 = y - Size_4;
        v23->bmiHeader.biSizeImage = 0;
        v48 = v34 - x + 1;
        iUsage = usage;
        LODWORD(pjBits) = v48;
        v23->bmiHeader.biWidth = v48;
        nHeight = v47 + 1;
        v23->bmiHeader.biHeight = v47 + 1;
        v50 = CreateDIBitmap(v21, &v23->bmiHeader, 2u, 0, v23, iUsage);
        ho = v50;
        v51 = v50;
        if ( v50 )
        {
          v99 = SelectObject(v21, v50);
          if ( v99 )
          {
            if ( PlgBlt(v21, &Point, v42, xSrc, ySrc, width, height, 0, 0, 0) )
            {
              memset_0(v23, 0, v45);
              v52 = Src;
              v23->bmiHeader.biSize = *(_DWORD *)Src;
              if ( GetDIBits(v21, v51, 0, 0, 0, v23, iUsage) )
              {
                if ( (int)GetSizeOfColorTable(v23, &v82) >= 0 )
                {
                  v53 = v23->bmiHeader.biSize + v82;
                  if ( v53 >= v23->bmiHeader.biSize && Size >= v53 )
                  {
                    LODWORD(v54) = v23->bmiHeader.biSizeImage;
                    if ( (_DWORD)v54 )
                      goto LABEL_138;
                    CJScan = GetCJScan(
                               (unsigned int)v23->bmiHeader.biWidth,
                               v23->bmiHeader.biPlanes,
                               v23->bmiHeader.biBitCount);
                    if ( CJScan )
                    {
                      biHeight = (unsigned int)-v23->bmiHeader.biHeight;
                      if ( v23->bmiHeader.biHeight > 0 )
                        biHeight = (unsigned int)v23->bmiHeader.biHeight;
                      v54 = CJScan * biHeight;
                      if ( v54 <= v56 )
                      {
LABEL_138:
                        v58 = LocalAlloc(0, (unsigned int)v54);
                        hMem = v58;
                        if ( v58 )
                        {
                          if ( GetDIBits(v21, v51, 0, v23->bmiHeader.biHeight, v58, v23, usage) )
                          {
                            if ( (_DWORD)uBytes )
                            {
                              v59 = lpbmi;
                              MonoDib = (void *)CreateMonoDib(lpbmi, lpBits, ColorUse);
                              v96 = MonoDib;
                              if ( !MonoDib || !SelectObject(v42, MonoDib) )
                                goto LABEL_116;
                            }
                            else
                            {
                              v61 = v52[1];
                              v62 = v52[2];
                              LODWORD(uBytes) = 40;
                              *(_DWORD *)v105 = 40;
                              memset(&v105[20], 0, 20);
                              ColorUse = 2;
                              lpbmi = (BITMAPINFO *)v105;
                              *(_DWORD *)&v105[4] = v61;
                              *(_DWORD *)&v105[8] = v62;
                              *(_QWORD *)&v105[12] = 65537;
                              Bitmap = CreateBitmap(v61, v62, 1u, 1u, 0);
                              v96 = Bitmap;
                              if ( !Bitmap || !SelectObject(v42, Bitmap) || !PatBlt(v42, 0, 0, v61, v62, 0xFF0062u) )
                                goto LABEL_116;
                              v59 = lpbmi;
                            }
                            if ( (unsigned int)uBytes >= 0x28 )
                            {
                              v64 = 44;
                              if ( (unsigned int)uBytes > 0x2C )
                                v64 = (unsigned int)uBytes;
                              v65 = (struct tagBITMAPINFO *)LocalAlloc(0, v64);
                              v22 = v65;
                              if ( !v65 )
                                goto LABEL_116;
                              memcpy_0(v65, v59, (unsigned int)uBytes);
                              v66 = nHeight;
                              v67 = (int)pjBits;
                              v68 = nHeight;
                              *(_QWORD *)&v22->bmiHeader.biCompression = 0;
                              v22->bmiHeader.biWidth = v67;
                              v22->bmiHeader.biHeight = v66;
                              v69 = CreateBitmap(v67, v68, 1u, 1u, 0);
                              v101 = v69;
                              v70 = v69;
                              if ( !v69
                                || !SelectObject(v21, v69)
                                || !PatBlt(v21, 0, 0, v22->bmiHeader.biWidth, v22->bmiHeader.biHeight, 0x42u) )
                              {
                                goto LABEL_116;
                              }
                              if ( v94 )
                              {
                                pt.x = a13;
                                pt.y = a14;
                                if ( !DPtoLP(v42, &pt, 1) )
                                  goto LABEL_116;
                                ySrc = pt.y;
                                xSrc = pt.x;
                              }
                              else
                              {
                                pt.x = xSrc;
                                pt.y = ySrc;
                              }
                              if ( PlgBlt(v21, &Point, v42, xSrc, ySrc, width, height, 0, 0, 0) )
                              {
                                v71 = GetCJScan(
                                        (unsigned int)v22->bmiHeader.biWidth,
                                        v22->bmiHeader.biPlanes,
                                        v22->bmiHeader.biBitCount);
                                if ( v71 )
                                {
                                  v72 = (unsigned int)-v22->bmiHeader.biHeight;
                                  if ( v22->bmiHeader.biHeight > 0 )
                                    v72 = (unsigned int)v22->bmiHeader.biHeight;
                                  v73 = v71 * v72;
                                  if ( v73 <= 0xFFFFFFFF )
                                  {
                                    v74 = LocalAlloc(0, (unsigned int)v73);
                                    v98 = v74;
                                    if ( v74 )
                                    {
                                      if ( GetDIBits(v21, v70, 0, v22->bmiHeader.biHeight, v74, v22, ColorUse) )
                                      {
                                        v75 = *(_QWORD *)v103;
                                        if ( (unsigned int)DoSaveDC(*(_QWORD *)v103) )
                                        {
                                          if ( (unsigned int)DoSetMapMode(v75, 1) )
                                          {
                                            if ( (unsigned int)DoModifyWorldTransform(v75, 0, 1) )
                                            {
                                              if ( (unsigned int)DoSetWindowOrg(v75, 0, 0) )
                                              {
                                                v77 = DoSetViewportOrg(v75, 0, 0);
                                                v76 = 0;
                                                if ( v77 )
                                                {
                                                  LODWORD(v79) = Size;
                                                  v89 = DoMaskBlt(
                                                          v75,
                                                          x,
                                                          Size_4,
                                                          v67,
                                                          nHeight,
                                                          -1429471232,
                                                          0,
                                                          0,
                                                          (__int64)&xformIdentity,
                                                          usage,
                                                          v23,
                                                          v79,
                                                          (__int64)hMem,
                                                          v54,
                                                          0,
                                                          0,
                                                          ColorUse,
                                                          v22,
                                                          uBytes,
                                                          v98);
                                                }
                                              }
                                            }
                                          }
                                          DoRestoreDC(v75, 0xFFFFFFFFLL, v76);
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              goto LABEL_116;
                            }
                            v89 = 1;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_116:
      v44 = lpxf;
      goto LABEL_117;
    }
  }
  return v89;
}

```

## disassembly

```asm
0x1801427e0  mov     [rsp-8+arg_8], rbx
0x1801427e5  push    rbp
0x1801427e6  push    rsi
0x1801427e7  push    rdi
0x1801427e8  push    r12
0x1801427ea  push    r13
0x1801427ec  push    r14
0x1801427ee  push    r15
0x1801427f0  lea     rbp, [rsp-0B0h]
0x1801427f8  sub     rsp, 1E0h
0x1801427ff  mov     rax, cs:__security_cookie
0x180142806  xor     rax, rsp
0x180142809  mov     [rbp+0E0h+var_40], rax
0x180142810  mov     qword ptr [rbp+0E0h+var_C8], rcx
0x180142814  xor     esi, esi
0x180142816  mov     rax, rdx
0x180142819  mov     [rbp+0E0h+xSrc], r8d
0x18014281d  mov     rdx, [rdx]
0x180142820  xorps   xmm0, xmm0
0x180142823  mov     [rbp+0E0h+ySrc], r9d
0x180142827  xorps   xmm1, xmm1
0x18014282a  mov     r9, rcx
0x18014282d  mov     qword ptr [rbp+0E0h+Point.x], rdx
0x180142834  mov     r8, [rax+8]
0x180142838  mov     r12d, esi
0x18014283b  mov     ecx, dword ptr [rbp+0E0h+uBytes]
0x180142841  mov     edi, esi
0x180142843  mov     [rbp+0E0h+var_110], ecx
0x180142846  mov     ebx, esi
0x180142848  mov     rcx, [rbp+0E0h+arg_30]
0x18014284f  mov     [rbp+0E0h+lpxf], rcx
0x180142853  mov     ecx, [rbp+0E0h+arg_38]
0x180142859  mov     [rbp+0E0h+usage], ecx
0x18014285c  mov     rcx, [rbp+0E0h+arg_40]
0x180142863  mov     [rbp+0E0h+Src], rcx
0x180142867  mov     ecx, [rbp+0E0h+arg_48]
0x18014286d  mov     dword ptr [rbp+0E0h+Size], ecx
0x180142870  mov     rcx, [rbp+0E0h+arg_50]
0x180142877  mov     [rbp+0E0h+pjBits], rcx
0x18014287b  mov     ecx, [rbp+0E0h+arg_70]
0x180142881  mov     [rbp+0E0h+ColorUse], ecx
0x180142884  mov     rcx, [rbp+0E0h+arg_78]
0x18014288b  mov     [rbp+0E0h+lpbmi], rcx
0x18014288f  mov     rcx, [rbp+0E0h+arg_88]
0x180142896  mov     [rbp+0E0h+lpBits], rcx
0x18014289a  xor     ecx, ecx
0x18014289c  mov     [rbp+0E0h+var_98], rcx
0x1801428a0  mov     qword ptr [rbp+0E0h+var_90.bmiHeader.biClrUsed], rcx
0x1801428a4  mov     dword ptr [rbp+0E0h+var_90.bmiColors.rgbBlue], ecx
0x1801428a7  mov     rcx, [rax+10h]
0x1801428ab  mov     eax, r8d
0x1801428ae  mov     [rbp+0E0h+var_50], rcx
0x1801428b5  sub     eax, edx
0x1801428b7  add     eax, ecx
0x1801428b9  shr     rdx, 20h
0x1801428bd  shr     rcx, 20h
0x1801428c1  sub     ecx, edx
0x1801428c3  mov     [rbp+0E0h+var_58], r8
0x1801428ca  shr     r8, 20h
0x1801428ce  lea     edx, [rsi+4]
0x1801428d1  add     ecx, r8d
0x1801428d4  mov     qword ptr [rbp+0E0h+pt.x], rsi
0x1801428d8  mov     [rbp+0E0h+var_44], ecx
0x1801428de  lea     r8, [r9+54h]
0x1801428e2  lea     rcx, [rbp+0E0h+Point]
0x1801428e9  mov     [rbp+0E0h+var_154], si
0x1801428ed  movups  [rbp+0E0h+var_B8], xmm0
0x1801428f1  mov     [rbp+0E0h+var_138], esi
0x1801428f4  movups  [rbp+0E0h+var_A8], xmm0
0x1801428f8  mov     [rbp+0E0h+var_E8], rsi
0x1801428fc  movups  xmmword ptr [rbp+0E0h+var_90.bmiHeader.biSize], xmm1
0x180142900  mov     [rbp+0E0h+ho], rsi
0x180142904  movups  xmmword ptr [rbp+0E0h+var_90.bmiHeader.biCompression], xmm1
0x180142908  mov     [rbp+0E0h+var_D8], rsi
0x18014290c  mov     [rbp+0E0h+var_100], rsi
0x180142910  mov     [rbp+0E0h+var_F0], rsi
0x180142914  mov     [rbp+0E0h+hMem], rsi
0x180142918  mov     [rbp+0E0h+var_48], eax
0x18014291e  call    bXformWorkhorse
0x180142923  test    eax, eax
0x180142925  jz      loc_18014327B
0x18014292b  mov     ecx, [rbp+0E0h+var_48]
0x180142931  mov     eax, ecx
0x180142933  mov     edx, dword ptr [rbp+0E0h+var_50]
0x180142939  cmp     edx, ecx
0x18014293b  mov     r11d, dword ptr [rbp+0E0h+var_58]
0x180142942  cmovl   eax, edx
0x180142945  cmp     r11d, eax
0x180142948  jge     short loc_18014294F
0x18014294a  mov     eax, r11d
0x18014294d  jmp     short loc_180142956
0x18014294f  cmp     edx, ecx
0x180142951  mov     eax, ecx
0x180142953  cmovl   eax, edx
0x180142956  mov     r15d, [rbp+0E0h+Point.x]
0x18014295d  cmp     r15d, eax
0x180142960  jge     short loc_180142968
0x180142962  mov     [rbp+0E0h+var_158], r15d
0x180142966  jmp     short loc_180142984
0x180142968  cmp     edx, ecx
0x18014296a  mov     eax, ecx
0x18014296c  cmovl   eax, edx
0x18014296f  cmp     r11d, eax
0x180142972  jge     short loc_18014297A
0x180142974  mov     [rbp+0E0h+var_158], r11d
0x180142978  jmp     short loc_180142984
0x18014297a  cmp     edx, ecx
0x18014297c  mov     esi, ecx
0x18014297e  cmovl   esi, edx
0x180142981  mov     [rbp+0E0h+var_158], esi
0x180142984  mov     r8d, [rbp+0E0h+var_44]
0x18014298b  mov     eax, r8d
0x18014298e  mov     r9d, dword ptr [rbp+0E0h+var_50+4]
0x180142995  cmp     r9d, r8d
0x180142998  mov     r10d, dword ptr [rbp+0E0h+var_58+4]
0x18014299f  cmovl   eax, r9d
0x1801429a3  cmp     r10d, eax
0x1801429a6  jge     short loc_1801429AD
0x1801429a8  mov     eax, r10d
0x1801429ab  jmp     short loc_1801429B7
0x1801429ad  cmp     r9d, r8d
0x1801429b0  mov     eax, r8d
0x1801429b3  cmovl   eax, r9d
0x1801429b7  mov     esi, [rbp+0E0h+Point.y]
0x1801429bd  cmp     esi, eax
0x1801429bf  jge     short loc_1801429C6
0x1801429c1  mov     dword ptr [rbp+0E0h+Size+4], esi
0x1801429c4  jmp     short loc_1801429E9
0x1801429c6  cmp     r9d, r8d
0x1801429c9  mov     eax, r8d
0x1801429cc  cmovl   eax, r9d
0x1801429d0  cmp     r10d, eax
0x1801429d3  jge     short loc_1801429DB
0x1801429d5  mov     dword ptr [rbp+0E0h+Size+4], r10d
0x1801429d9  jmp     short loc_1801429E9
0x1801429db  cmp     r9d, r8d
0x1801429de  mov     r14d, r8d
0x1801429e1  cmovl   r14d, r9d
0x1801429e5  mov     dword ptr [rbp+0E0h+Size+4], r14d
0x1801429e9  cmp     edx, ecx
0x1801429eb  mov     eax, ecx
0x1801429ed  cmovg   eax, edx
0x1801429f0  cmp     r11d, eax
0x1801429f3  jle     short loc_1801429FA
0x1801429f5  mov     eax, r11d
0x1801429f8  jmp     short loc_180142A01
0x1801429fa  cmp     edx, ecx
0x1801429fc  mov     eax, ecx
0x1801429fe  cmovg   eax, edx
0x180142a01  cmp     r15d, eax
0x180142a04  jle     short loc_180142A0B
0x180142a06  mov     r13d, r15d
0x180142a09  jmp     short loc_180142A25
0x180142a0b  cmp     edx, ecx
0x180142a0d  mov     eax, ecx
0x180142a0f  cmovg   eax, edx
0x180142a12  cmp     r11d, eax
0x180142a15  jle     short loc_180142A1C
0x180142a17  mov     r13d, r11d
0x180142a1a  jmp     short loc_180142A25
0x180142a1c  cmp     edx, ecx
0x180142a1e  mov     r13d, ecx
0x180142a21  cmovg   r13d, edx
0x180142a25  cmp     r9d, r8d
0x180142a28  mov     eax, r8d
0x180142a2b  cmovg   eax, r9d
0x180142a2f  cmp     r10d, eax
0x180142a32  jle     short loc_180142A39
0x180142a34  mov     eax, r10d
0x180142a37  jmp     short loc_180142A43
0x180142a39  cmp     r9d, r8d
0x180142a3c  mov     eax, r8d
0x180142a3f  cmovg   eax, r9d
0x180142a43  cmp     esi, eax
0x180142a45  jle     short loc_180142A4C
0x180142a47  mov     r14d, esi
0x180142a4a  jmp     short loc_180142A6A
0x180142a4c  cmp     r9d, r8d
0x180142a4f  mov     eax, r8d
0x180142a52  cmovg   eax, r9d
0x180142a56  cmp     r10d, eax
0x180142a59  jle     short loc_180142A60
0x180142a5b  mov     r14d, r10d
0x180142a5e  jmp     short loc_180142A6A
0x180142a60  cmp     r9d, r8d
0x180142a63  mov     r14d, r8d
0x180142a66  cmovg   r14d, r9d
0x180142a6a  mov     eax, dword ptr [rbp+0E0h+Size+4]
0x180142a6d  sub     esi, eax
0x180142a6f  sub     r15d, [rbp+0E0h+var_158]
0x180142a73  sub     r10d, eax
0x180142a76  sub     r9d, eax
0x180142a79  mov     [rbp+0E0h+Point.y], esi
0x180142a7f  mov     esi, [rbp+0E0h+var_158]
0x180142a82  sub     r8d, eax
0x180142a85  mov     eax, dword ptr [rbp+0E0h+Size]
0x180142a88  sub     r11d, esi
0x180142a8b  sub     edx, esi
0x180142a8d  mov     [rbp+0E0h+Point.x], r15d
0x180142a94  sub     ecx, esi
0x180142a96  mov     dword ptr [rbp+0E0h+var_58], r11d
0x180142a9d  mov     esi, 2Ch ; ','
0x180142aa2  mov     dword ptr [rbp+0E0h+var_58+4], r10d
0x180142aa9  mov     dword ptr [rbp+0E0h+var_50], edx
0x180142aaf  mov     dword ptr [rbp+0E0h+var_50+4], r9d
0x180142ab6  mov     [rbp+0E0h+var_48], ecx
0x180142abc  mov     [rbp+0E0h+var_44], r8d
0x180142ac3  cmp     eax, esi
0x180142ac5  jnb     short loc_180142AE4
0x180142ac7  mov     rdx, [rbp+0E0h+Src]; Src
0x180142acb  lea     rcx, [rbp+0E0h+var_90]; void *
0x180142acf  mov     r8d, eax; Size
0x180142ad2  call    memcpy_0
0x180142ad7  lea     r15, [rbp+0E0h+var_90]
0x180142adb  mov     dword ptr [rbp+0E0h+Size], esi
0x180142ade  mov     [rbp+0E0h+Src], r15
0x180142ae2  jmp     short loc_180142AE8
0x180142ae4  mov     r15, [rbp+0E0h+Src]
0x180142ae8  mov     rcx, [rbp+0E0h+lpxf]; lpxf
0x180142aec  call    hdcMakeCompatibleDC
0x180142af1  mov     rsi, rax
0x180142af4  test    rax, rax
0x180142af7  jz      loc_18014327B
0x180142afd  mov     ecx, [rbp+0E0h+usage]
0x180142b00  mov     r8d, 6; flInit
0x180142b06  mov     r9, [rbp+0E0h+pjBits]; pjBits
0x180142b0a  mov     rdx, r15; pbmih
0x180142b0d  mov     [rsp+210h+iUsage], ecx; iUsage
0x180142b11  mov     rcx, rax; hdc
0x180142b14  mov     [rsp+210h+pbmi], r15; pbmi
0x180142b19  call    cs:__imp_CreateDIBitmap
0x180142b20  nop     dword ptr [rax+rax+00h]
0x180142b25  mov     [rbp+0E0h+lpxf], rax
0x180142b29  mov     r15, rax
0x180142b2c  test    rax, rax
0x180142b2f  jz      loc_180143200
0x180142b35  mov     rdx, rax; h
0x180142b38  mov     rcx, rsi; hdc
0x180142b3b  call    cs:__imp_SelectObject
0x180142b42  nop     dword ptr [rax+rax+00h]
0x180142b47  mov     [rbp+0E0h+h], rax
0x180142b4b  test    rax, rax
0x180142b4e  jz      loc_1801431A9
0x180142b54  xor     ecx, ecx; hdc
0x180142b56  call    cs:__imp_CreateCompatibleDC
0x180142b5d  nop     dword ptr [rax+rax+00h]
0x180142b62  mov     r12, rax
0x180142b65  test    rax, rax
0x180142b68  jz      loc_18014317B
0x180142b6e  mov     r15d, dword ptr [rbp+0E0h+Size]
0x180142b72  xor     ecx, ecx; uFlags
0x180142b74  mov     edx, r15d; uBytes
0x180142b77  call    cs:__imp_LocalAlloc
0x180142b7e  nop     dword ptr [rax+rax+00h]
0x180142b83  mov     rbx, rax
0x180142b86  test    rax, rax
0x180142b89  jz      loc_180143177
0x180142b8f  mov     rdx, [rbp+0E0h+Src]; Src
0x180142b93  mov     r8d, r15d; Size
0x180142b96  mov     rcx, rax; void *
0x180142b99  call    memcpy_0
0x180142b9e  sub     r13d, [rbp+0E0h+var_158]
0x180142ba2  xor     r9d, r9d; pjBits
0x180142ba5  sub     r14d, dword ptr [rbp+0E0h+Size+4]
0x180142ba9  mov     rdx, rbx; pbmih
0x180142bac  and     [rbx+14h], edi
0x180142baf  mov     rcx, r12; hdc
0x180142bb2  lea     eax, [r13+1]
0x180142bb6  mov     r13d, [rbp+0E0h+usage]
0x180142bba  mov     dword ptr [rbp+0E0h+pjBits], eax
0x180142bbd  lea     r8d, [r9+2]; flInit
0x180142bc1  mov     [rbx+4], eax
0x180142bc4  lea     eax, [r14+1]
0x180142bc8  mov     [rsp+210h+iUsage], r13d; iUsage
0x180142bcd  mov     [rbp+0E0h+nHeight], eax
0x180142bd0  mov     [rbx+8], eax
0x180142bd3  mov     [rsp+210h+pbmi], rbx; pbmi
0x180142bd8  call    cs:__imp_CreateDIBitmap
0x180142bdf  nop     dword ptr [rax+rax+00h]
0x180142be4  mov     [rbp+0E0h+ho], rax
0x180142be8  mov     r14, rax
0x180142beb  test    rax, rax
0x180142bee  jz      loc_180143177
0x180142bf4  mov     rdx, rax; h
0x180142bf7  mov     rcx, r12; hdc
0x180142bfa  call    cs:__imp_SelectObject
0x180142c01  nop     dword ptr [rax+rax+00h]
0x180142c06  xor     ecx, ecx
0x180142c08  mov     [rbp+0E0h+var_E8], rax
0x180142c0c  test    rax, rax
0x180142c0f  jz      loc_180143177
0x180142c15  mov     r9d, [rbp+0E0h+xSrc]; xSrc
0x180142c19  lea     rdx, [rbp+0E0h+Point]; lpPoint
0x180142c20  mov     [rsp+210h+yMask], ecx; yMask
0x180142c24  mov     r8, rsi; hdcSrc
0x180142c27  mov     [rsp+210h+xMask], ecx; xMask
0x180142c2b  mov     [rsp+210h+hbmMask], rcx; hbmMask
0x180142c30  mov     ecx, [rbp+0E0h+arg_28]
0x180142c36  mov     [rsp+210h+height], ecx; height
0x180142c3a  mov     ecx, [rbp+0E0h+width]
  ... truncated ...
```
