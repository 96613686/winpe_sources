# DoPlgBlt

- ea: `0x1800fff20`
- end: `0x1801009d6`
- name: `DoPlgBlt`
- size: `2742`
- prototype: `__int64 __fastcall(int, int, int, int, int width, int, __int64, int, void *Src, int, __int64, int, int, int, int, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800ffcf0`

## callees

- `0x1800c790c`
- `0x1800c87fc`
- `0x1800c8944`
- `0x1800e8dbc`
- `0x1800ff3c0`
- `0x1800fff20`
- `0x180105d40`
- `0x18010673c`
- `0x180146ce0`
- `0x180146f10`
- `0x180148d90`
- `0x180148f08`
- `0x180148f5c`
- `0x18014a0e0`
- `0x18014a120`
- `0x180171428`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801002ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180100458`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801006ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180100879`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801002ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180100458`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801006ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180100879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010065d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010069d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010065d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010069d`
- `GDI32!PlgBlt` at `0x180100380`
- `GDI32!PlgBlt` at `0x180100825`
- `GDI32!PlgBlt` at `0x180100380`
- `GDI32!PlgBlt` at `0x180100825`
- `GDI32!CreateDIBitmap` at `0x180100241`
- `GDI32!CreateDIBitmap` at `0x18010030d`
- `GDI32!CreateDIBitmap` at `0x180100241`
- `GDI32!CreateDIBitmap` at `0x18010030d`
- `GDI32!DPtoLP` at `0x1801007bf`
- `GDI32!DPtoLP` at `0x1801007bf`
- `GDI32!CreateBitmap` at `0x180100533`
- `GDI32!CreateBitmap` at `0x180100736`
- `GDI32!CreateBitmap` at `0x180100533`
- `GDI32!CreateBitmap` at `0x180100736`
- `GDI32!PatBlt` at `0x180100577`
- `GDI32!PatBlt` at `0x180100788`
- `GDI32!PatBlt` at `0x180100577`
- `GDI32!PatBlt` at `0x180100788`
- `GDI32!DeleteDC` at `0x180100635`
- `GDI32!DeleteDC` at `0x180100649`
- `GDI32!DeleteDC` at `0x180100635`
- `GDI32!DeleteDC` at `0x180100649`
- `GDI32!GetDIBits` at `0x1801003c9`
- `GDI32!GetDIBits` at `0x18010048d`
- `GDI32!GetDIBits` at `0x1801008af`
- `GDI32!GetDIBits` at `0x1801003c9`
- `GDI32!GetDIBits` at `0x18010048d`
- `GDI32!GetDIBits` at `0x1801008af`
- `GDI32!SelectObject` at `0x18010026e`
- `GDI32!SelectObject` at `0x18010032f`
- `GDI32!SelectObject` at `0x1801004da`
- `GDI32!SelectObject` at `0x18010054e`
- `GDI32!SelectObject` at `0x1801005b3`
- `GDI32!SelectObject` at `0x1801005ce`
- `GDI32!SelectObject` at `0x180100758`
- `GDI32!SelectObject` at `0x18010026e`
- `GDI32!SelectObject` at `0x18010032f`
- `GDI32!SelectObject` at `0x1801004da`
- `GDI32!SelectObject` at `0x18010054e`
- `GDI32!SelectObject` at `0x1801005b3`
- `GDI32!SelectObject` at `0x1801005ce`
- `GDI32!SelectObject` at `0x180100758`
- `GDI32!CreateCompatibleDC` at `0x18010028d`
- `GDI32!CreateCompatibleDC` at `0x18010028d`
- `GDI32!DeleteObject` at `0x1801005de`
- `GDI32!DeleteObject` at `0x1801005f6`
- `GDI32!DeleteObject` at `0x18010060e`
- `GDI32!DeleteObject` at `0x180100626`
- `GDI32!DeleteObject` at `0x1801005de`
- `GDI32!DeleteObject` at `0x1801005f6`
- `GDI32!DeleteObject` at `0x18010060e`
- `GDI32!DeleteObject` at `0x180100626`

## pseudocode

```c
__int64 __fastcall DoPlgBlt(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int width,
        int a6,
        void *a7,
        UINT a8,
        BITMAPINFO *Src,
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
  POINT v18; // r8
  __int64 v19; // r9
  int v20; // eax
  int *v21; // rax
  LONG x; // esi
  int v23; // eax
  int v24; // eax
  int *v25; // rax
  LONG y; // r12d
  int v27; // eax
  int v28; // eax
  int *v29; // rax
  LONG v30; // r15d
  int v31; // eax
  int v32; // eax
  int *v33; // rax
  LONG v34; // r14d
  int v35; // eax
  HDC CompatibleDC; // rax
  HDC v37; // r12
  HDC v38; // rsi
  HLOCAL v39; // r13
  struct tagBITMAPINFO *v40; // rdi
  struct tagBITMAPINFO *v41; // rbx
  HBITMAP DIBitmap; // rax
  struct tagBITMAPINFO *v43; // rax
  int v44; // r15d
  int v45; // r14d
  HBITMAP v46; // rax
  HBITMAP v47; // r14
  BITMAPINFO *v48; // r15
  UINT v49; // r13d
  unsigned int v50; // edx
  unsigned __int64 biSizeImage; // rcx
  unsigned int CJScan; // eax
  unsigned __int64 v53; // r10
  __int64 v54; // r8
  unsigned int biHeight; // eax
  HLOCAL v56; // rax
  unsigned int v57; // r14d
  void *MonoDib; // rax
  BITMAPINFO *v59; // r13
  int biWidth; // r14d
  int v61; // r15d
  HBITMAP Bitmap; // rax
  unsigned int v64; // eax
  struct tagBITMAPINFO *v65; // rax
  int v66; // ecx
  int v67; // eax
  HBITMAP v68; // rax
  HBITMAP v69; // r15
  unsigned int v70; // eax
  __int64 v71; // r8
  unsigned int v72; // eax
  unsigned __int64 v73; // rcx
  __int64 v74; // r15
  int height; // [rsp+30h] [rbp-100h]
  SIZE_T v76; // [rsp+58h] [rbp-D8h]
  unsigned int Size; // [rsp+B8h] [rbp-78h]
  int Size_4; // [rsp+BCh] [rbp-74h] BYREF
  int ySrc; // [rsp+C0h] [rbp-70h]
  int xSrc; // [rsp+C4h] [rbp-6Ch]
  UINT ColorUse; // [rsp+C8h] [rbp-68h]
  UINT usage; // [rsp+CCh] [rbp-64h]
  LONG v83; // [rsp+D0h] [rbp-60h]
  int v84; // [rsp+D4h] [rbp-5Ch]
  unsigned int v85; // [rsp+D8h] [rbp-58h]
  struct tagPOINT pt; // [rsp+E0h] [rbp-50h] BYREF
  BITMAPINFO *pbmi; // [rsp+E8h] [rbp-48h]
  int nHeight; // [rsp+F0h] [rbp-40h]
  int nWidth; // [rsp+F4h] [rbp-3Ch]
  void *pjBits; // [rsp+F8h] [rbp-38h]
  HGDIOBJ v91; // [rsp+100h] [rbp-30h]
  HGDIOBJ v92; // [rsp+108h] [rbp-28h]
  HLOCAL hMem; // [rsp+110h] [rbp-20h]
  BITMAPINFO *lpbmi; // [rsp+118h] [rbp-18h]
  HGDIOBJ v95; // [rsp+120h] [rbp-10h]
  _BYTE v96[40]; // [rsp+128h] [rbp-8h] BYREF
  void *lpBits; // [rsp+150h] [rbp+20h]
  int v98[2]; // [rsp+158h] [rbp+28h]
  HGDIOBJ h; // [rsp+160h] [rbp+30h]
  HGDIOBJ ho; // [rsp+168h] [rbp+38h]
  _OWORD v101[3]; // [rsp+170h] [rbp+40h] BYREF
  POINT Point; // [rsp+1A0h] [rbp+70h] BYREF
  __int64 v103; // [rsp+1A8h] [rbp+78h] BYREF
  __int64 v104; // [rsp+1B0h] [rbp+80h] BYREF
  int v105; // [rsp+1B8h] [rbp+88h] BYREF
  int v106; // [rsp+1BCh] [rbp+8Ch] BYREF

  v91 = a7;
  usage = a8;
  Size = a10;
  pjBits = a11;
  *(_QWORD *)v98 = a1;
  xSrc = a3;
  v18 = *(POINT *)a2;
  ColorUse = a15;
  ySrc = a4;
  v19 = *(_QWORD *)(a2 + 8);
  v104 = *(_QWORD *)(a2 + 16);
  lpbmi = a16;
  Point = v18;
  lpBits = a18;
  v103 = v19;
  v105 = v19 + v104 - v18.x;
  v106 = HIDWORD(v19) + HIDWORD(v104) - v18.y;
  pbmi = Src;
  pt = 0;
  memset(v96, 0, sizeof(v96));
  LOWORD(Size_4) = 0;
  memset(v101, 0, 44);
  v85 = 0;
  if ( (unsigned int)bXformWorkhorse(&Point, 4, a1 + 84) )
  {
    v20 = v105;
    if ( (int)v104 < v105 )
      v20 = v104;
    if ( (int)v103 >= v20 )
    {
      v21 = (int *)&v104;
      if ( (int)v104 >= v105 )
        v21 = &v105;
    }
    else
    {
      v21 = (int *)&v103;
    }
    if ( Point.x >= *v21 )
    {
      v23 = v105;
      if ( (int)v104 < v105 )
        v23 = v104;
      if ( (int)v103 >= v23 )
      {
        x = v105;
        if ( (int)v104 < v105 )
          x = v104;
      }
      else
      {
        x = v103;
      }
    }
    else
    {
      x = Point.x;
    }
    v24 = v106;
    if ( SHIDWORD(v104) < v106 )
      v24 = HIDWORD(v104);
    v84 = x;
    if ( SHIDWORD(v103) >= v24 )
    {
      v25 = (int *)&v104 + 1;
      if ( SHIDWORD(v104) >= v106 )
        v25 = &v106;
    }
    else
    {
      v25 = (int *)&v103 + 1;
    }
    if ( Point.y >= *v25 )
    {
      v27 = v106;
      if ( SHIDWORD(v104) < v106 )
        v27 = HIDWORD(v104);
      if ( SHIDWORD(v103) >= v27 )
      {
        y = v106;
        if ( SHIDWORD(v104) < v106 )
          y = HIDWORD(v104);
      }
      else
      {
        y = HIDWORD(v103);
      }
    }
    else
    {
      y = Point.y;
    }
    v83 = y;
    v28 = v105;
    if ( (int)v104 > v105 )
      v28 = v104;
    if ( (int)v103 <= v28 )
    {
      v29 = (int *)&v104;
      if ( (int)v104 <= v105 )
        v29 = &v105;
    }
    else
    {
      v29 = (int *)&v103;
    }
    if ( Point.x <= *v29 )
    {
      v31 = v105;
      if ( (int)v104 > v105 )
        v31 = v104;
      if ( (int)v103 <= v31 )
      {
        v30 = v105;
        if ( (int)v104 > v105 )
          v30 = v104;
      }
      else
      {
        v30 = v103;
      }
    }
    else
    {
      v30 = Point.x;
    }
    v32 = v106;
    if ( SHIDWORD(v104) > v106 )
      v32 = HIDWORD(v104);
    if ( SHIDWORD(v103) <= v32 )
    {
      v33 = (int *)&v104 + 1;
      if ( SHIDWORD(v104) <= v106 )
        v33 = &v106;
    }
    else
    {
      v33 = (int *)&v103 + 1;
    }
    if ( Point.y <= *v33 )
    {
      v35 = v106;
      if ( SHIDWORD(v104) > v106 )
        v35 = HIDWORD(v104);
      if ( SHIDWORD(v103) <= v35 )
      {
        v34 = v106;
        if ( SHIDWORD(v104) > v106 )
          v34 = HIDWORD(v104);
      }
      else
      {
        v34 = HIDWORD(v103);
      }
    }
    else
    {
      v34 = Point.y;
    }
    Point.x -= x;
    Point.y -= y;
    LODWORD(v103) = v103 - x;
    HIDWORD(v103) -= y;
    LODWORD(v104) = v104 - x;
    HIDWORD(v104) -= y;
    v105 -= x;
    v106 -= y;
    if ( a10 < 0x2C )
    {
      memcpy_0(v101, Src, a10);
      Size = 44;
      pbmi = (BITMAPINFO *)v101;
    }
    CompatibleDC = (HDC)hdcMakeCompatibleDC((XFORM *)v91);
    v37 = CompatibleDC;
    if ( CompatibleDC )
    {
      v38 = 0;
      v39 = 0;
      hMem = 0;
      v40 = 0;
      v41 = 0;
      DIBitmap = CreateDIBitmap(CompatibleDC, &pbmi->bmiHeader, 6u, pjBits, pbmi, usage);
      ho = DIBitmap;
      if ( !DIBitmap )
      {
LABEL_98:
        DeleteDC(v37);
        if ( v38 )
          DeleteDC(v38);
        if ( v41 )
          LocalFree(v41);
        if ( v40 )
          LocalFree(v40);
        if ( hMem )
          LocalFree(hMem);
        if ( v39 )
          LocalFree(v39);
        return v85;
      }
      pjBits = 0;
      v91 = 0;
      v92 = 0;
      h = SelectObject(v37, DIBitmap);
      if ( !h )
      {
LABEL_92:
        DeleteObject(ho);
        if ( pjBits )
          DeleteObject(pjBits);
        if ( v92 )
          DeleteObject(v92);
        if ( v91 )
          DeleteObject(v91);
        goto LABEL_98;
      }
      v95 = 0;
      v38 = CreateCompatibleDC(0);
      if ( v38 )
      {
        v43 = (struct tagBITMAPINFO *)LocalAlloc(0, Size);
        v41 = v43;
        if ( !v43 )
          goto LABEL_89;
        memcpy_0(v43, pbmi, Size);
        v44 = v30 - v84;
        v45 = v34 - v83;
        v41->bmiHeader.biSizeImage = 0;
        nWidth = v44 + 1;
        v41->bmiHeader.biWidth = v44 + 1;
        nHeight = v45 + 1;
        v41->bmiHeader.biHeight = v45 + 1;
        v46 = CreateDIBitmap(v38, &v41->bmiHeader, 2u, 0, v41, usage);
        pjBits = v46;
        v47 = v46;
        if ( !v46 )
          goto LABEL_89;
        v95 = SelectObject(v38, v46);
        if ( !v95 )
          goto LABEL_134;
        if ( !PlgBlt(v38, &Point, v37, xSrc, ySrc, width, a6, 0, 0, 0) )
          goto LABEL_89;
        memset_0(v41, 0, Size);
        v48 = pbmi;
        v49 = usage;
        height = usage;
        v41->bmiHeader.biSize = pbmi->bmiHeader.biSize;
        if ( !GetDIBits(v38, v47, 0, 0, 0, v41, height) )
          goto LABEL_89;
        if ( (int)GetSizeOfColorTable(v41, &Size_4) < 0 )
          goto LABEL_89;
        v50 = v41->bmiHeader.biSize + (unsigned __int16)Size_4;
        if ( v50 < v41->bmiHeader.biSize || Size < v50 )
          goto LABEL_89;
        biSizeImage = v41->bmiHeader.biSizeImage;
        pbmi = (BITMAPINFO *)biSizeImage;
        if ( !(_DWORD)biSizeImage )
        {
          CJScan = GetCJScan((unsigned int)v41->bmiHeader.biWidth, v41->bmiHeader.biPlanes, v41->bmiHeader.biBitCount);
          v54 = CJScan;
          if ( !CJScan )
            goto LABEL_89;
          biHeight = -v41->bmiHeader.biHeight;
          if ( v41->bmiHeader.biHeight >= 0 )
            biHeight = v41->bmiHeader.biHeight;
          biSizeImage = v54 * biHeight;
          pbmi = (BITMAPINFO *)biSizeImage;
          if ( biSizeImage > v53 )
            goto LABEL_89;
        }
        v56 = LocalAlloc(0, (unsigned int)biSizeImage);
        hMem = v56;
        if ( !v56 )
          goto LABEL_89;
        if ( GetDIBits(v38, v47, 0, v41->bmiHeader.biHeight, v56, v41, v49) )
        {
          v57 = uBytes;
          Size_4 = uBytes;
          if ( (_DWORD)uBytes )
          {
            MonoDib = (void *)CreateMonoDib(lpbmi, lpBits, ColorUse);
            v92 = MonoDib;
            if ( !MonoDib || !SelectObject(v37, MonoDib) )
              goto LABEL_89;
            v59 = lpbmi;
          }
          else
          {
            biWidth = v48->bmiHeader.biWidth;
            v61 = v48->bmiHeader.biHeight;
            memset(&v96[20], 0, 20);
            *(_DWORD *)v96 = 40;
            *(_DWORD *)&v96[4] = biWidth;
            *(_DWORD *)&v96[8] = v61;
            *(_QWORD *)&v96[12] = 65537;
            Bitmap = CreateBitmap(biWidth, v61, 1u, 1u, 0);
            v92 = Bitmap;
            if ( !Bitmap || !SelectObject(v37, Bitmap) || !PatBlt(v37, 0, 0, biWidth, v61, 0xFF0062u) )
              goto LABEL_89;
            ColorUse = 2;
            v59 = (BITMAPINFO *)v96;
            v57 = 40;
          }
          if ( v57 < 0x28 )
          {
            v85 = 1;
LABEL_89:
            v39 = 0;
            goto LABEL_90;
          }
          v64 = 44;
          if ( v57 > 0x2C )
            v64 = v57;
          v65 = (struct tagBITMAPINFO *)LocalAlloc(0, v64);
          v40 = v65;
          if ( v65 )
          {
            memcpy_0(v65, v59, v57);
            v66 = nHeight;
            v39 = 0;
            v67 = nWidth;
            v40->bmiHeader.biHeight = nHeight;
            v40->bmiHeader.biWidth = v67;
            *(_QWORD *)&v40->bmiHeader.biCompression = 0;
            v68 = CreateBitmap(v67, v66, 1u, 1u, 0);
            v91 = v68;
            v69 = v68;
            if ( v68
              && SelectObject(v38, v68)
              && PatBlt(v38, 0, 0, v40->bmiHeader.biWidth, v40->bmiHeader.biHeight, 0x42u) )
            {
              if ( !Size_4 )
              {
                pt.x = xSrc;
                pt.y = ySrc;
                goto LABEL_119;
              }
              pt.x = a13;
              pt.y = a14;
              if ( DPtoLP(v37, &pt, 1) )
              {
                ySrc = pt.y;
                xSrc = pt.x;
LABEL_119:
                if ( PlgBlt(v38, &Point, v37, xSrc, ySrc, width, a6, 0, 0, 0) )
                {
                  v70 = GetCJScan(
                          (unsigned int)v40->bmiHeader.biWidth,
                          v40->bmiHeader.biPlanes,
                          v40->bmiHeader.biBitCount);
                  v71 = v70;
                  if ( v70 )
                  {
                    v72 = -v40->bmiHeader.biHeight;
                    if ( v40->bmiHeader.biHeight >= 0 )
                      v72 = v40->bmiHeader.biHeight;
                    v73 = v71 * v72;
                    if ( v73 <= 0xFFFFFFFF )
                    {
                      v39 = LocalAlloc(0, (unsigned int)v73);
                      if ( v39 )
                      {
                        if ( GetDIBits(v38, v69, 0, v40->bmiHeader.biHeight, v39, v40, ColorUse) )
                        {
                          v74 = *(_QWORD *)v98;
                          if ( (unsigned int)DoSaveDC(*(_QWORD *)v98) )
                          {
                            if ( (unsigned int)DoSetMapMode(v74, 1)
                              && (unsigned int)DoModifyWorldTransform(v74, 0, 1)
                              && (unsigned int)DoSetWindowOrg(v74, 0, 0)
                              && (unsigned int)DoSetViewportOrg(v74, 0, 0) )
                            {
                              LODWORD(v76) = Size;
                              v85 = DoMaskBlt(
                                      v74,
                                      v84,
                                      nHeight,
                                      -1429471232,
                                      0,
                                      0,
                                      (__int64)&xformIdentity,
                                      usage,
                                      v41,
                                      v76,
                                      hMem,
                                      (int)pbmi,
                                      0,
                                      0,
                                      ColorUse,
                                      v40,
                                      v57,
                                      v39);
                            }
                            DoRestoreDC(v74, 0xFFFFFFFFLL);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            v39 = 0;
          }
        }
        else
        {
LABEL_134:
          v39 = 0;
        }
      }
LABEL_90:
      SelectObject(v37, h);
      if ( v95 )
        SelectObject(v38, v95);
      goto LABEL_92;
    }
  }
  return v85;
}

```

## disassembly

```asm
0x1800fff20  mov     [rsp-8+arg_8], rbx
0x1800fff25  push    rbp
0x1800fff26  push    rsi
0x1800fff27  push    rdi
0x1800fff28  push    r12
0x1800fff2a  push    r13
0x1800fff2c  push    r14
0x1800fff2e  push    r15
0x1800fff30  lea     rbp, [rsp-0A0h]
0x1800fff38  sub     rsp, 1D0h
0x1800fff3f  mov     rax, cs:__security_cookie
0x1800fff46  xor     rax, rsp
0x1800fff49  mov     [rbp+0D0h+var_40], rax
0x1800fff50  mov     rax, [rbp+0D0h+arg_30]
0x1800fff57  mov     r10, rcx
0x1800fff5a  mov     r13, [rbp+0D0h+Src]
0x1800fff61  xorps   xmm1, xmm1
0x1800fff64  mov     [rbp+0D0h+var_100], rax
0x1800fff68  xorps   xmm0, xmm0
0x1800fff6b  mov     eax, [rbp+0D0h+arg_38]
0x1800fff71  mov     [rbp+0D0h+usage], eax
0x1800fff74  mov     eax, [rbp+0D0h+arg_48]
0x1800fff7a  mov     dword ptr [rbp+0D0h+Size], eax
0x1800fff7d  mov     rax, [rbp+0D0h+arg_50]
0x1800fff84  mov     [rbp+0D0h+pjBits], rax
0x1800fff88  mov     eax, [rbp+0D0h+arg_70]
0x1800fff8e  mov     qword ptr [rbp+0D0h+var_A8], rcx
0x1800fff92  mov     [rbp+0D0h+xSrc], r8d
0x1800fff96  mov     r8, [rdx]
0x1800fff99  mov     [rbp+0D0h+ColorUse], eax
0x1800fff9c  mov     rax, [rbp+0D0h+arg_78]
0x1800fffa3  mov     [rbp+0D0h+ySrc], r9d
0x1800fffa7  mov     r9, [rdx+8]
0x1800fffab  mov     rdx, [rdx+10h]
0x1800fffaf  mov     ecx, edx
0x1800fffb1  mov     [rbp+0D0h+var_50], rdx
0x1800fffb8  sub     ecx, r8d
0x1800fffbb  shr     rdx, 20h
0x1800fffbf  add     ecx, r9d
0x1800fffc2  mov     [rbp+0D0h+lpbmi], rax
0x1800fffc6  mov     rax, [rbp+0D0h+arg_88]
0x1800fffcd  mov     qword ptr [rbp+0D0h+Point.x], r8
0x1800fffd1  shr     r8, 20h
0x1800fffd5  sub     edx, r8d
0x1800fffd8  mov     [rbp+0D0h+lpBits], rax
0x1800fffdc  xor     eax, eax
0x1800fffde  mov     [rbp+0D0h+var_58], r9
0x1800fffe2  shr     r9, 20h
0x1800fffe6  lea     r8, [r10+54h]
0x1800fffea  add     edx, r9d
0x1800fffed  mov     [rbp+0D0h+var_48], ecx
0x1800ffff3  mov     [rbp+0D0h+var_44], edx
0x1800ffff9  lea     rcx, [rbp+0D0h+Point]
0x1800ffffd  movups  xmmword ptr [rbp+0D0h+var_80], xmm1
0x180100001  lea     edx, [rax+4]
0x180100004  mov     [rbp+0D0h+var_118], r13
0x180100008  mov     qword ptr [rbp+0D0h+pt.x], 0
0x180100010  movups  [rbp+0D0h+var_D8], xmm0
0x180100014  mov     [rbp+0D0h+var_B8], rax
0x180100018  movups  [rbp+0D0h+var_C8], xmm0
0x18010001c  mov     word ptr [rbp+0D0h+Size+4], ax
0x180100020  movups  [rbp+0D0h+var_90], xmm1
0x180100024  mov     [rbp+0D0h+var_128], eax
0x180100027  movups  xmmword ptr [rbp+0D0h+var_80+0Ch], xmm1
0x18010002b  call    bXformWorkhorse
0x180100030  test    eax, eax
0x180100032  jz      loc_1801006A9
0x180100038  mov     ecx, [rbp+0D0h+var_48]
0x18010003e  mov     eax, ecx
0x180100040  mov     edx, dword ptr [rbp+0D0h+var_50]
0x180100046  cmp     edx, ecx
0x180100048  mov     r10d, dword ptr [rbp+0D0h+var_58]
0x18010004c  cmovl   eax, edx
0x18010004f  cmp     r10d, eax
0x180100052  jge     short loc_18010005A
0x180100054  lea     rax, [rbp+0D0h+var_58]
0x180100058  jmp     short loc_18010006E
0x18010005a  cmp     edx, ecx
0x18010005c  lea     rax, [rbp+0D0h+var_50]
0x180100063  lea     r8, [rbp+0D0h+var_48]
0x18010006a  cmovge  rax, r8
0x18010006e  mov     edi, [rbp+0D0h+Point.x]
0x180100071  cmp     edi, [rax]
0x180100073  jge     short loc_180100079
0x180100075  mov     esi, edi
0x180100077  jmp     short loc_180100091
0x180100079  cmp     edx, ecx
0x18010007b  mov     eax, ecx
0x18010007d  cmovl   eax, edx
0x180100080  cmp     r10d, eax
0x180100083  jge     short loc_18010008A
0x180100085  mov     esi, r10d
0x180100088  jmp     short loc_180100091
0x18010008a  cmp     edx, ecx
0x18010008c  mov     esi, ecx
0x18010008e  cmovl   esi, edx
0x180100091  mov     r8d, [rbp+0D0h+var_44]
0x180100098  mov     eax, r8d
0x18010009b  mov     r9d, dword ptr [rbp+0D0h+var_50+4]
0x1801000a2  cmp     r9d, r8d
0x1801000a5  mov     r11d, dword ptr [rbp+0D0h+var_58+4]
0x1801000a9  cmovl   eax, r9d
0x1801000ad  mov     [rbp+0D0h+var_12C], esi
0x1801000b0  cmp     r11d, eax
0x1801000b3  jge     short loc_1801000BB
0x1801000b5  lea     rax, [rbp+0D0h+var_58+4]
0x1801000b9  jmp     short loc_1801000D0
0x1801000bb  cmp     r9d, r8d
0x1801000be  lea     rax, [rbp+0D0h+var_50+4]
0x1801000c5  lea     rbx, [rbp+0D0h+var_44]
0x1801000cc  cmovge  rax, rbx
0x1801000d0  mov     ebx, [rbp+0D0h+Point.y]
0x1801000d3  cmp     ebx, [rax]
0x1801000d5  jge     short loc_1801000DC
0x1801000d7  mov     r12d, ebx
0x1801000da  jmp     short loc_1801000FA
0x1801000dc  cmp     r9d, r8d
0x1801000df  mov     eax, r8d
0x1801000e2  cmovl   eax, r9d
0x1801000e6  cmp     r11d, eax
0x1801000e9  jge     short loc_1801000F0
0x1801000eb  mov     r12d, r11d
0x1801000ee  jmp     short loc_1801000FA
0x1801000f0  cmp     r9d, r8d
0x1801000f3  mov     r12d, r8d
0x1801000f6  cmovl   r12d, r9d
0x1801000fa  cmp     edx, ecx
0x1801000fc  mov     [rbp+0D0h+var_130], r12d
0x180100100  mov     eax, ecx
0x180100102  cmovg   eax, edx
0x180100105  cmp     r10d, eax
0x180100108  jle     short loc_180100110
0x18010010a  lea     rax, [rbp+0D0h+var_58]
0x18010010e  jmp     short loc_180100124
0x180100110  cmp     edx, ecx
0x180100112  lea     rax, [rbp+0D0h+var_50]
0x180100119  lea     r14, [rbp+0D0h+var_48]
0x180100120  cmovle  rax, r14
0x180100124  cmp     edi, [rax]
0x180100126  jle     short loc_18010012D
0x180100128  mov     r15d, edi
0x18010012b  jmp     short loc_180100147
0x18010012d  cmp     edx, ecx
0x18010012f  mov     eax, ecx
0x180100131  cmovg   eax, edx
0x180100134  cmp     r10d, eax
0x180100137  jle     short loc_18010013E
0x180100139  mov     r15d, r10d
0x18010013c  jmp     short loc_180100147
0x18010013e  cmp     edx, ecx
0x180100140  mov     r15d, ecx
0x180100143  cmovg   r15d, edx
0x180100147  cmp     r9d, r8d
0x18010014a  mov     eax, r8d
0x18010014d  cmovg   eax, r9d
0x180100151  cmp     r11d, eax
0x180100154  jle     short loc_18010015C
0x180100156  lea     rax, [rbp+0D0h+var_58+4]
0x18010015a  jmp     short loc_180100171
0x18010015c  cmp     r9d, r8d
0x18010015f  lea     rax, [rbp+0D0h+var_50+4]
0x180100166  lea     r14, [rbp+0D0h+var_44]
0x18010016d  cmovle  rax, r14
0x180100171  cmp     ebx, [rax]
0x180100173  jle     short loc_18010017A
0x180100175  mov     r14d, ebx
0x180100178  jmp     short loc_180100198
0x18010017a  cmp     r9d, r8d
0x18010017d  mov     eax, r8d
0x180100180  cmovg   eax, r9d
0x180100184  cmp     r11d, eax
0x180100187  jle     short loc_18010018E
0x180100189  mov     r14d, r11d
0x18010018c  jmp     short loc_180100198
0x18010018e  cmp     r9d, r8d
0x180100191  mov     r14d, r8d
0x180100194  cmovg   r14d, r9d
0x180100198  sub     edi, esi
0x18010019a  sub     ebx, r12d
0x18010019d  sub     r10d, esi
0x1801001a0  mov     [rbp+0D0h+Point.x], edi
0x1801001a3  mov     edi, dword ptr [rbp+0D0h+Size]
0x1801001a6  sub     r11d, r12d
0x1801001a9  sub     edx, esi
0x1801001ab  mov     [rbp+0D0h+Point.y], ebx
0x1801001ae  sub     r9d, r12d
0x1801001b1  mov     dword ptr [rbp+0D0h+var_58], r10d
0x1801001b5  sub     ecx, esi
0x1801001b7  mov     dword ptr [rbp+0D0h+var_58+4], r11d
0x1801001bb  sub     r8d, r12d
0x1801001be  mov     dword ptr [rbp+0D0h+var_50], edx
0x1801001c4  mov     ebx, 2Ch ; ','
0x1801001c9  mov     dword ptr [rbp+0D0h+var_50+4], r9d
0x1801001d0  mov     [rbp+0D0h+var_48], ecx
0x1801001d6  mov     [rbp+0D0h+var_44], r8d
0x1801001dd  cmp     edi, ebx
0x1801001df  jnb     short loc_1801001FB
0x1801001e1  mov     r8d, edi; Size
0x1801001e4  lea     rcx, [rbp+0D0h+var_90]; void *
0x1801001e8  mov     rdx, r13; Src
0x1801001eb  call    memcpy_0
0x1801001f0  lea     rdx, [rbp+0D0h+var_90]
0x1801001f4  mov     dword ptr [rbp+0D0h+Size], ebx
0x1801001f7  mov     [rbp+0D0h+var_118], rdx
0x1801001fb  mov     rcx, [rbp+0D0h+var_100]; lpxf
0x1801001ff  call    hdcMakeCompatibleDC
0x180100204  mov     r12, rax
0x180100207  test    rax, rax
0x18010020a  jz      loc_1801006A9
0x180100210  mov     ecx, [rbp+0D0h+usage]
0x180100213  xor     eax, eax
0x180100215  mov     r9, [rbp+0D0h+pjBits]; pjBits
0x180100219  xor     esi, esi
0x18010021b  mov     [rsp+200h+iUsage], ecx; iUsage
0x18010021f  xor     r13d, r13d
0x180100222  mov     [rbp+0D0h+hMem], rax
0x180100226  mov     rcx, r12; hdc
0x180100229  mov     rax, [rbp+0D0h+var_118]
0x18010022d  xor     edi, edi
0x18010022f  lea     r8d, [rsi+6]; flInit
0x180100233  mov     [rbp+0D0h+var_150], r13
0x180100237  mov     rdx, rax; pbmih
0x18010023a  mov     [rsp+200h+pbmi], rax; pbmi
0x18010023f  xor     ebx, ebx
0x180100241  call    cs:__imp_CreateDIBitmap
0x180100248  nop     dword ptr [rax+rax+00h]
0x18010024d  xor     ecx, ecx
0x18010024f  mov     [rbp+0D0h+ho], rax
0x180100253  test    rax, rax
0x180100256  jz      loc_180100632
0x18010025c  mov     [rbp+0D0h+pjBits], rcx
0x180100260  mov     rdx, rax; h
0x180100263  mov     [rbp+0D0h+var_100], rcx
0x180100267  mov     [rbp+0D0h+var_F8], rcx
0x18010026b  mov     rcx, r12; hdc
0x18010026e  call    cs:__imp_SelectObject
0x180100275  nop     dword ptr [rax+rax+00h]
0x18010027a  mov     [rbp+0D0h+h], rax
0x18010027e  test    rax, rax
0x180100281  jz      loc_1801005DA
0x180100287  xor     ecx, ecx; hdc
0x180100289  mov     [rbp+0D0h+var_E0], rbx
0x18010028d  call    cs:__imp_CreateCompatibleDC
0x180100294  nop     dword ptr [rax+rax+00h]
0x180100299  mov     rsi, rax
0x18010029c  test    rax, rax
0x18010029f  jz      loc_1801005AC
0x1801002a5  mov     r13d, dword ptr [rbp+0D0h+Size]
0x1801002a9  xor     ecx, ecx; uFlags
0x1801002ab  mov     edx, r13d; uBytes
0x1801002ae  call    cs:__imp_LocalAlloc
0x1801002b5  nop     dword ptr [rax+rax+00h]
0x1801002ba  mov     rbx, rax
0x1801002bd  test    rax, rax
0x1801002c0  jz      loc_1801005A9
0x1801002c6  mov     rdx, [rbp+0D0h+var_118]; Src
0x1801002ca  mov     r8d, r13d; Size
0x1801002cd  mov     rcx, rax; void *
0x1801002d0  call    memcpy_0
0x1801002d5  sub     r15d, [rbp+0D0h+var_12C]
0x1801002d9  lea     r8d, [rdi+2]; flInit
0x1801002dd  sub     r14d, [rbp+0D0h+var_130]
0x1801002e1  xor     r9d, r9d; pjBits
0x1801002e4  mov     rdx, rbx; pbmih
0x1801002e7  mov     [rbx+14h], edi
0x1801002ea  mov     rcx, rsi; hdc
0x1801002ed  lea     eax, [r15+1]
0x1801002f1  mov     [rbp+0D0h+nWidth], eax
0x1801002f4  mov     [rbx+4], eax
0x1801002f7  lea     eax, [r14+1]
0x1801002fb  mov     [rbp+0D0h+nHeight], eax
0x1801002fe  mov     [rbx+8], eax
0x180100301  mov     eax, [rbp+0D0h+usage]
0x180100304  mov     [rsp+200h+iUsage], eax; iUsage
0x180100308  mov     [rsp+200h+pbmi], rbx; pbmi
0x18010030d  call    cs:__imp_CreateDIBitmap
0x180100314  nop     dword ptr [rax+rax+00h]
0x180100319  mov     [rbp+0D0h+pjBits], rax
0x18010031d  mov     r14, rax
0x180100320  test    rax, rax
0x180100323  jz      loc_1801005A9
0x180100329  mov     rdx, rax; h
0x18010032c  mov     rcx, rsi; hdc
0x18010032f  call    cs:__imp_SelectObject
0x180100336  nop     dword ptr [rax+rax+00h]
0x18010033b  xor     ecx, ecx
0x18010033d  mov     [rbp+0D0h+var_E0], rax
0x180100341  test    rax, rax
0x180100344  jz      loc_1801009CE
0x18010034a  mov     eax, [rbp+0D0h+arg_28]
0x180100350  lea     rdx, [rbp+0D0h+Point]; lpPoint
0x180100354  mov     r9d, [rbp+0D0h+xSrc]; xSrc
0x180100358  mov     r8, r12; hdcSrc
0x18010035b  mov     [rsp+200h+yMask], ecx; yMask
0x18010035f  mov     [rsp+200h+xMask], ecx; xMask
0x180100363  mov     [rsp+200h+hbmMask], rcx; hbmMask
0x180100368  mov     rcx, rsi; hdcDest
0x18010036b  mov     [rsp+200h+height], eax; height
0x18010036f  mov     eax, [rbp+0D0h+width]
0x180100375  mov     [rsp+200h+iUsage], eax; width
  ... truncated ...
```
