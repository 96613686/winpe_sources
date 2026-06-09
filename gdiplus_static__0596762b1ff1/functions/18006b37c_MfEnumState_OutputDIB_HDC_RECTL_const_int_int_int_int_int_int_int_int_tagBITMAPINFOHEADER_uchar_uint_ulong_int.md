# MfEnumState::OutputDIB(HDC__ *,_RECTL const *,int,int,int,int,int,int,int,int,tagBITMAPINFOHEADER *,uchar *,uint,ulong,int)

- ea: `0x18006b37c`
- end: `0x18006be8f`
- name: `?OutputDIB@MfEnumState@@IEAAXPEAUHDC__@@PEBU_RECTL@@HHHHHHHHPEFAUtagBITMAPINFOHEADER@@PEAEIKH@Z`
- size: `2835`
- prototype: `void(MfEnumState *__hidden this, HDC, const struct _RECTL *, int, int, int, int, int, int, int, int, struct tagBITMAPINFOHEADER *, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `5`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800694d4`
- `0x180130b70`
- `0x180130f94`
- `0x1801313f8`
- `0x180132c40`

## callees

- `0x180010bd0`
- `0x180015c44`
- `0x180019610`
- `0x18002c2c8`
- `0x18002f060`
- `0x180033f1c`
- `0x180044c4c`
- `0x1800458f4`
- `0x1800599b0`
- `0x180063cd8`
- `0x1800647fc`
- `0x18006a480`
- `0x18006a510`
- `0x18006b37c`
- `0x18006be98`
- `0x180086a60`
- `0x180086ab0`
- `0x180105d40`
- `0x18011dbe0`
- `0x180131de0`
- `0x1801451cc`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `GDI32!SetStretchBltMode` at `0x18006b5fe`
- `GDI32!SetStretchBltMode` at `0x18006b5fe`
- `GDI32!StretchDIBits` at `0x18006b66e`
- `GDI32!StretchDIBits` at `0x18006b66e`
- `GDI32!SetBkColor` at `0x18006ba26`
- `GDI32!SetBkColor` at `0x18006be4e`
- `GDI32!SetBkColor` at `0x18006ba26`
- `GDI32!SetBkColor` at `0x18006be4e`
- `GDI32!SetTextColor` at `0x18006ba3f`
- `GDI32!SetTextColor` at `0x18006be60`
- `GDI32!SetTextColor` at `0x18006ba3f`
- `GDI32!SetTextColor` at `0x18006be60`
- `GDI32!DeleteObject` at `0x18006be75`
- `GDI32!DeleteObject` at `0x18006be75`
- `GDI32!LPtoDP` at `0x18006b497`
- `GDI32!LPtoDP` at `0x18006b497`

## pseudocode

```c
void __fastcall MfEnumState::OutputDIB(
        COLORREF *this,
        HDC a2,
        const struct _RECTL *a3,
        int a4,
        LONG yDest,
        int DestWidth,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        BITMAPINFO *a12,
        unsigned __int8 *a13,
        UINT a14,
        DWORD a15,
        int a16)
{
  BITMAPINFO *v16; // rsi
  UINT iUsage; // r15d
  DWORD biSize; // edi
  int v21; // eax
  GpBitmap *v22; // rdi
  int v23; // ecx
  int SrcWidth; // r13d
  int v25; // r10d
  int SrcHeight; // r12d
  int v27; // eax
  int v28; // ecx
  LONG biWidth; // eax
  LONG biHeight; // r11d
  int v31; // r8d
  LONG v32; // r11d
  int v33; // edx
  int v34; // r9d
  int v35; // eax
  MfEnumState *v36; // rdx
  MfEnumState *v37; // r14
  int v38; // eax
  DWORD rop; // eax
  HDC v40; // rsi
  GpBitmap *v41; // rax
  GpBitmap *v42; // rax
  unsigned int v43; // r8d
  DWORD v44; // r9d
  DWORD v45; // edx
  struct tagBITMAPINFO *v46; // r15
  GpBitmap *v47; // rax
  int v48; // r9d
  GpBitmap *v49; // rax
  GpBitmap *v50; // r15
  __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  unsigned int v53; // edx
  DWORD v54; // eax
  unsigned __int64 v55; // r15
  unsigned int v56; // ecx
  DWORD v57; // eax
  __int64 v58; // rcx
  struct tagBITMAPINFO *v59; // rax
  unsigned int biBitCount; // r8d
  DWORD biCompression; // r9d
  COLORREF v62; // eax
  COLORREF v63; // edx
  COLORREF v64; // eax
  unsigned int v65; // r8d
  DWORD v66; // r9d
  DWORD v67; // edx
  struct tagBITMAPINFO *v68; // r15
  struct tagBITMAPINFO *v69; // rax
  unsigned __int64 v70; // r15
  __int64 v71; // rax
  __int64 v72; // r8
  unsigned int v73; // edx
  GpGraphics *v74; // r8
  DWORD DestHeight; // [rsp+20h] [rbp-E0h]
  DWORD DestHeighta; // [rsp+20h] [rbp-E0h]
  DWORD DestHeightb; // [rsp+20h] [rbp-E0h]
  BITMAPINFO *lpbmi; // [rsp+50h] [rbp-B0h]
  DWORD Size; // [rsp+70h] [rbp-90h] BYREF
  unsigned int Size_4; // [rsp+74h] [rbp-8Ch]
  int v81; // [rsp+78h] [rbp-88h]
  unsigned int v82; // [rsp+7Ch] [rbp-84h]
  int v83; // [rsp+80h] [rbp-80h]
  int ySrc; // [rsp+84h] [rbp-7Ch]
  int xSrc; // [rsp+88h] [rbp-78h]
  MfEnumState *v86; // [rsp+90h] [rbp-70h]
  int IntDistance; // [rsp+98h] [rbp-68h]
  void *lpBits; // [rsp+A0h] [rbp-60h]
  int xDest; // [rsp+A8h] [rbp-58h]
  int v90; // [rsp+ACh] [rbp-54h]
  COLORREF color; // [rsp+B0h] [rbp-50h]
  COLORREF v92; // [rsp+B4h] [rbp-4Ch]
  int v93; // [rsp+B8h] [rbp-48h]
  LONG v94; // [rsp+BCh] [rbp-44h]
  int v95; // [rsp+C0h] [rbp-40h]
  int v96; // [rsp+C4h] [rbp-3Ch]
  GpGraphics *v97; // [rsp+C8h] [rbp-38h]
  HDC hdc; // [rsp+D0h] [rbp-30h]
  BITMAPINFO *v99; // [rsp+D8h] [rbp-28h] BYREF
  void *v100; // [rsp+E0h] [rbp-20h] BYREF
  BITMAPINFO *v101; // [rsp+E8h] [rbp-18h]
  __int128 *v102; // [rsp+F0h] [rbp-10h]
  HGDIOBJ ho; // [rsp+F8h] [rbp-8h] BYREF
  float v104[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h] BYREF
  float v106; // [rsp+118h] [rbp+18h]
  float v107; // [rsp+11Ch] [rbp+1Ch]
  __int128 v108; // [rsp+120h] [rbp+20h] BYREF
  __int128 v109; // [rsp+130h] [rbp+30h]
  _BYTE v110[8]; // [rsp+140h] [rbp+40h] BYREF
  volatile signed __int32 *v111; // [rsp+148h] [rbp+48h]
  _BYTE v112[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v113; // [rsp+160h] [rbp+60h]
  __int64 v114; // [rsp+174h] [rbp+74h]
  int v115; // [rsp+17Ch] [rbp+7Ch]
  struct tagPOINT pt; // [rsp+188h] [rbp+88h] BYREF
  struct tagPOINT v117; // [rsp+190h] [rbp+90h] BYREF
  struct tagPOINT v118; // [rsp+198h] [rbp+98h] BYREF
  _DWORD v119[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v120; // [rsp+1B0h] [rbp+B0h]
  __int64 v121; // [rsp+1C0h] [rbp+C0h]
  int v122; // [rsp+1C8h] [rbp+C8h]

  v16 = a12;
  iUsage = a14;
  xDest = a4;
  biSize = a12->bmiHeader.biSize;
  hdc = a2;
  v86 = (MfEnumState *)this;
  lpBits = a13;
  Size_4 = a14;
  if ( biSize < 0x28 )
    return;
  if ( a14 >= 2 )
  {
    TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(1, a14, 0);
    return;
  }
  if ( !a13 )
  {
    biBitCount = a12->bmiHeader.biBitCount;
    biCompression = a12->bmiHeader.biCompression;
    DestHeighta = a12->bmiHeader.biClrUsed;
    Size = 0;
    if ( !(unsigned int)GetDibNumPalEntries(a16, biSize, biBitCount, biCompression, DestHeighta, &Size) )
      return;
    lpBits = (void *)GetDibBits(a12, Size, a14);
    Size = 0;
    if ( !(unsigned int)GetDibBitsSize(&a12->bmiHeader, &Size)
      || a12->bmiHeader.biSizeImage && Size > a12->bmiHeader.biSizeImage )
    {
      return;
    }
    if ( biSize + Size < biSize || biSize + Size > this[42] )
      return;
    a4 = xDest;
  }
  v21 = -DestWidth;
  v102 = 0;
  if ( DestWidth > 0 )
    v21 = DestWidth;
  v22 = 0;
  v23 = -a7;
  ho = 0;
  v108 = 0;
  if ( a7 > 0 )
    v23 = a7;
  v109 = 0;
  v100 = 0;
  v99 = 0;
  v93 = 0;
  if ( a12->bmiHeader.biBitCount == 1 && a15 != 13369376 )
  {
    v62 = SetBkColor(a2, this[47]);
    v63 = this[48];
    color = v62;
    v64 = SetTextColor(a2, v63);
    SrcHeight = a11;
    SrcWidth = a10;
    v92 = v64;
    ySrc = a9;
    xSrc = a8;
    v90 = 1;
    goto LABEL_41;
  }
  v117.x = a4 + v21;
  pt.y = yDest;
  v117.y = yDest;
  v90 = 0;
  v118.y = v23 + yDest;
  color = 0;
  v92 = 0;
  pt.x = a4;
  v118.x = a4;
  if ( !LPtoDP(a2, &pt, 3) )
  {
    SrcHeight = a11;
    SrcWidth = a10;
    ySrc = a9;
    xSrc = a8;
    goto LABEL_40;
  }
  IntDistance = GetIntDistance(&pt, &v117);
  SrcWidth = a10;
  v25 = GetIntDistance(&pt, &v118);
  SrcHeight = a11;
  v81 = v25;
  v27 = -a10;
  if ( a10 > 0 )
    v27 = a10;
  v28 = -a11;
  v82 = v27;
  biWidth = a12->bmiHeader.biWidth;
  if ( a11 > 0 )
    v28 = a11;
  v83 = v28;
  if ( biWidth > 0 )
  {
    biHeight = a12->bmiHeader.biHeight;
    v31 = 0;
    v95 = a10 >> 31;
    v32 = -biHeight;
    v96 = a11 >> 31;
    v33 = 0;
    if ( v32 < 0 )
      v32 = a12->bmiHeader.biHeight;
    v94 = v32;
    if ( a8 >= 0 )
      v31 = a8;
    if ( v31 > biWidth )
      v31 = biWidth;
    xSrc = v31;
    if ( a9 >= 0 )
      v33 = a9;
    v34 = v31 + a10;
    if ( v33 > v32 )
      v33 = v32;
    ySrc = v33;
    if ( v34 < 0 )
      SrcWidth = -v31;
    if ( v34 > biWidth )
      SrcWidth = biWidth - v31;
    if ( v33 + a11 < 0 )
      SrcHeight = -v33;
    if ( v33 + a11 > v32 )
      SrcHeight = v32 - v33;
    v35 = v82;
    if ( (int)v82 > 0 && v28 > 0 )
    {
      v36 = v86;
      if ( !*((_DWORD *)v86 + 45) || a15 == 13369376 )
        goto LABEL_36;
      v65 = a12->bmiHeader.biBitCount;
      v66 = a12->bmiHeader.biCompression;
      v67 = a12->bmiHeader.biSize;
      DestHeightb = a12->bmiHeader.biClrUsed;
      Size = 0;
      if ( !(unsigned int)GetDibNumPalEntries(a16, v67, v65, v66, DestHeightb, &Size) )
      {
LABEL_71:
        v25 = v81;
        v36 = v86;
        v28 = v83;
        v35 = v82;
LABEL_36:
        if ( v35 == IntDistance && v28 == v25 )
          goto LABEL_40;
        if ( (*((_BYTE *)v36 + 8) & 1) == 0 && (*((_BYTE *)v36 + 8) & 2) == 0 )
          goto LABEL_40;
        v82 = *((_DWORD *)v36 + 44);
        if ( v82 == 5 )
          goto LABEL_40;
        if ( v28 <= 1 )
          goto LABEL_40;
        if ( v35 <= 1 )
          goto LABEL_40;
        if ( IntDistance * v25 >= 0x800000 )
          goto LABEL_40;
        v41 = (GpBitmap *)GpMallocEx(1504, 0);
        if ( !v41
          || (v42 = GpBitmap::GpBitmap(v41, IntDistance, v81, 137224), (v22 = v42) == 0)
          || !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v42 + 8LL))(v42)
          || (v43 = a12->bmiHeader.biBitCount,
              v44 = a12->bmiHeader.biCompression,
              v45 = a12->bmiHeader.biSize,
              DestHeight = a12->bmiHeader.biClrUsed,
              Size = 0,
              !(unsigned int)GetDibNumPalEntries(a16, v45, v43, v44, DestHeight, &Size)) )
        {
LABEL_40:
          if ( a15 == 13369376 )
          {
            v37 = v86;
            if ( (!*((_DWORD *)v86 + 45) || Globals::OsVer.dwMajorVersion != 4) && (*((_BYTE *)v86 + 8) & 4) == 0 )
            {
              v38 = 4;
LABEL_43:
              SetStretchBltMode(hdc, v38);
              rop = a15;
              if ( a15 != 13369376 && Globals::OsVer.dwMajorVersion == 4 && (*((_DWORD *)v37 + 2) & 0x10000) != 0 )
                rop = 13369376;
              lpbmi = v16;
              v40 = hdc;
              StretchDIBits(
                hdc,
                xDest,
                yDest,
                DestWidth,
                a7,
                xSrc,
                ySrc,
                SrcWidth,
                SrcHeight,
                lpBits,
                lpbmi,
                iUsage,
                rop);
              if ( v22 )
              {
                if ( v102 )
                  GpBitmap::UnlockBits(v22, v102);
                (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v22 + 56LL))(v22);
              }
              if ( v90 )
              {
                SetBkColor(v40, color);
                SetTextColor(v40, v92);
              }
              if ( v93 )
              {
                DeleteObject(ho);
                GpFree(v99);
              }
              return;
            }
LABEL_42:
            v38 = 3;
            goto LABEL_43;
          }
LABEL_41:
          v37 = v86;
          goto LABEL_42;
        }
        if ( ((unsigned __int8)a12 & 3) != 0 || iUsage )
        {
          v70 = (-(__int64)(iUsage != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4;
          if ( Size_4 == 1 )
            TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 2, 0);
          v55 = Size * v70;
          if ( v55 > 0xFFFFFFFF )
            goto LABEL_67;
          v56 = 4 * Size;
          if ( 4 * (unsigned __int64)Size > 0xFFFFFFFF )
            goto LABEL_67;
          v57 = a12->bmiHeader.biSize;
          Size = a12->bmiHeader.biSize + v55;
          if ( v57 + (unsigned int)v55 < v57 )
            goto LABEL_67;
          v58 = v57 + v56;
          if ( (unsigned int)v58 < v57 )
            goto LABEL_67;
          v59 = (struct tagBITMAPINFO *)GpMallocEx(v58, 1);
          v101 = v59;
          v46 = v59;
          if ( !v59 )
            goto LABEL_67;
          memcpy_0(v59, a12, Size);
          Size = 1;
        }
        else
        {
          Size = 0;
          v46 = a12;
          v101 = a12;
        }
        v83 = 1;
        v47 = (GpBitmap *)GpMallocEx(1504, 0);
        if ( v47 )
        {
          v49 = GpBitmap::GpBitmap(v47, v46, lpBits, v48);
          v50 = v49;
          if ( v49 )
          {
            if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v49 + 8LL))(v49) )
            {
              v71 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)v22 + 128LL))(v22);
              v97 = (GpGraphics *)v71;
              v74 = (GpGraphics *)v71;
              if ( v71 )
              {
                if ( *(_DWORD *)(v71 + 8) == 1634879281 )
                {
                  GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v110, (struct GpRuntime::GpLockable *)(v71 + 16));
                  v105 = 0;
                  v107 = (float)v81;
                  v106 = (float)IntDistance;
                  v104[1] = (float)(v94 - ySrc - SrcHeight);
                  v104[0] = (float)xSrc;
                  v104[2] = (float)(int)(SrcWidth - (v95 & 0xFFFFFFFE) - 1);
                  v104[3] = (float)(int)(SrcHeight - (v96 & 0xFFFFFFFE) - 1);
                  GpGraphics::SetCompositingMode(v72, 1);
                  GpGraphics::SetInterpolationMode(v97, v82);
                  GpImageAttributes::GpImageAttributes((GpImageAttributes *)v112);
                  v114 = 3;
                  v115 = 0;
                  v113 = 0;
                  v83 = GpGraphics::DrawImage(v97, v50, &v105, v104, 2, v112);
                  GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v112);
                  v74 = v97;
                  _InterlockedDecrement(v111);
                }
                GpGraphics::`scalar deleting destructor'(v74, v73);
              }
            }
            (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v50 + 56LL))(v50);
          }
        }
        if ( Size )
          GpFree(v101);
        if ( !v83 && !(unsigned int)GpBitmap::LockBits(v22, 0, 1, 137224, &v108) )
        {
          v16 = (BITMAPINFO *)v119;
          lpBits = (void *)v109;
          SrcWidth = IntDistance;
          SrcHeight = v81;
          v121 = 0;
          v122 = 0;
          v119[2] = -v81;
          iUsage = 0;
          v120 = 0;
          v102 = &v108;
          xSrc = 0;
          ySrc = 0;
          v119[0] = 40;
          v119[1] = IntDistance;
          v119[3] = 1572865;
          goto LABEL_40;
        }
LABEL_67:
        iUsage = Size_4;
        goto LABEL_40;
      }
      if ( ((unsigned __int8)a12 & 3) != 0 || a14 )
      {
        if ( Size_4 == 1 )
          TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 1, 0);
        v52 = ((-(__int64)(a14 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4) * Size;
        if ( v52 > 0xFFFFFFFF
          || (v53 = 4 * Size, 4 * (unsigned __int64)Size > 0xFFFFFFFF)
          || (v54 = a12->bmiHeader.biSize, Size = a12->bmiHeader.biSize + v52, v54 + (unsigned int)v52 < v54)
          || (v51 = v53 + v54, (unsigned int)v51 < v54)
          || (v69 = (struct tagBITMAPINFO *)GpMallocEx(v51, 1), (v68 = v69) == 0) )
        {
LABEL_70:
          iUsage = Size_4;
          goto LABEL_71;
        }
        memcpy_0(v69, a12, Size);
        Size = 1;
      }
      else
      {
        Size = 0;
        v68 = a12;
      }
      if ( !(unsigned int)GpBitmap::DrawAndHalftoneForStretchBlt(
                            hdc,
                            v68,
                            lpBits,
                            xSrc,
                            ySrc,
                            v82,
                            v83,
                            IntDistance,
                            v81,
                            (HPALETTE)&v99,
                            &v100,
                            &ho,
                            *((_DWORD *)v86 + 44)) )
      {
        SrcWidth = IntDistance;
        SrcHeight = v81;
        v16 = v99;
        lpBits = v100;
        v93 = 1;
        xSrc = 0;
        ySrc = 0;
        if ( Size )
          GpFree(v68);
        iUsage = Size_4;
        goto LABEL_41;
      }
      if ( Size )
        GpFree(v68);
      goto LABEL_70;
    }
  }
}

```

## disassembly

```asm
0x18006b37c  mov     [rsp-8+arg_10], rbx
0x18006b381  push    rbp
0x18006b382  push    rsi
0x18006b383  push    rdi
0x18006b384  push    r12
0x18006b386  push    r13
0x18006b388  push    r14
0x18006b38a  push    r15
0x18006b38c  lea     rbp, [rsp-0E0h]
0x18006b394  sub     rsp, 1E0h
0x18006b39b  mov     rax, cs:__security_cookie
0x18006b3a2  xor     rax, rsp
0x18006b3a5  mov     [rbp+110h+var_40], rax
0x18006b3ac  mov     rsi, [rbp+110h+arg_58]
0x18006b3b3  mov     r12, rdx
0x18006b3b6  mov     rax, [rbp+110h+arg_60]
0x18006b3bd  mov     r13, rcx
0x18006b3c0  mov     r15d, [rbp+110h+arg_68]
0x18006b3c7  mov     [rbp+110h+xDest], r9d
0x18006b3cb  mov     edi, [rsi]
0x18006b3cd  mov     [rbp+110h+hdc], rdx
0x18006b3d1  mov     [rbp+110h+var_180], rcx
0x18006b3d5  mov     [rbp+110h+var_170], rax
0x18006b3d9  mov     dword ptr [rsp+210h+Size+4], r15d
0x18006b3de  cmp     edi, 28h ; '('
0x18006b3e1  jb      loc_18006B695
0x18006b3e7  xor     ebx, ebx
0x18006b3e9  cmp     r15d, 2
0x18006b3ed  jnb     loc_18006B976
0x18006b3f3  test    rax, rax
0x18006b3f6  jz      loc_18006B992
0x18006b3fc  mov     eax, [rbp+110h+DestWidth]
0x18006b402  xorps   xmm0, xmm0
0x18006b405  mov     ecx, [rbp+110h+arg_30]
0x18006b40b  neg     eax
0x18006b40d  mov     r14d, 1
0x18006b413  mov     [rbp+110h+var_120], rbx
0x18006b417  cmovs   eax, [rbp+110h+DestWidth]
0x18006b41e  mov     rdi, rbx
0x18006b421  neg     ecx
0x18006b423  mov     [rbp+110h+ho], rbx
0x18006b427  movups  [rbp+110h+var_F0], xmm0
0x18006b42b  cmovs   ecx, [rbp+110h+arg_30]
0x18006b432  movups  [rbp+110h+var_E0], xmm0
0x18006b436  mov     [rbp+110h+var_130], rbx
0x18006b43a  mov     [rbp+110h+var_138], rbx
0x18006b43e  mov     [rbp+110h+var_158], ebx
0x18006b441  cmp     [rsi+0Eh], r14w
0x18006b446  jz      loc_18006BA0C
0x18006b44c  mov     edx, [rbp+110h+yDest]
0x18006b452  add     eax, r9d
0x18006b455  mov     [rbp+110h+var_80.x], eax
0x18006b45b  mov     r8d, 3; c
0x18006b461  mov     [rbp+110h+pt.y], edx
0x18006b467  mov     [rbp+110h+var_80.y], edx
0x18006b46d  lea     eax, [rcx+rdx]
0x18006b470  mov     [rbp+110h+var_164], ebx
0x18006b473  lea     rdx, [rbp+110h+pt]; lppt
0x18006b47a  mov     [rbp+110h+var_78.y], eax
0x18006b480  mov     rcx, r12; hdc
0x18006b483  mov     [rbp+110h+color], ebx
0x18006b486  mov     [rbp+110h+var_15C], ebx
0x18006b489  mov     [rbp+110h+pt.x], r9d
0x18006b490  mov     [rbp+110h+var_78.x], r9d
0x18006b497  call    cs:__imp_LPtoDP
0x18006b49e  nop     dword ptr [rax+rax+00h]
0x18006b4a3  test    eax, eax
0x18006b4a5  jz      loc_18006B7F6
0x18006b4ab  lea     rdx, [rbp+110h+var_80]; struct tagPOINT *
0x18006b4b2  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x18006b4b9  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x18006b4be  lea     rdx, [rbp+110h+var_78]; struct tagPOINT *
0x18006b4c5  mov     [rbp+110h+var_178], eax
0x18006b4c8  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x18006b4cf  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x18006b4d4  mov     r13d, [rbp+110h+arg_48]
0x18006b4db  mov     r10d, eax
0x18006b4de  mov     r12d, [rbp+110h+arg_50]
0x18006b4e5  mov     ecx, r12d
0x18006b4e8  mov     [rsp+210h+var_198], eax
0x18006b4ec  mov     eax, r13d
0x18006b4ef  neg     eax
0x18006b4f1  cmovs   eax, r13d
0x18006b4f5  neg     ecx
0x18006b4f7  mov     [rsp+210h+var_194], eax
0x18006b4fb  mov     eax, [rsi+4]
0x18006b4fe  cmovs   ecx, r12d
0x18006b502  mov     [rbp+110h+var_190], ecx
0x18006b505  test    eax, eax
0x18006b507  jle     loc_18006B695
0x18006b50d  mov     r11d, [rsi+8]
0x18006b511  mov     edx, r13d
0x18006b514  sar     edx, 1Fh
0x18006b517  mov     r8d, ebx
0x18006b51a  mov     [rbp+110h+var_150], edx
0x18006b51d  mov     edx, r12d
0x18006b520  sar     edx, 1Fh
0x18006b523  neg     r11d
0x18006b526  mov     [rbp+110h+var_14C], edx
0x18006b529  mov     edx, ebx
0x18006b52b  cmovs   r11d, [rsi+8]
0x18006b530  cmp     [rbp+110h+arg_38], ebx
0x18006b536  mov     [rbp+110h+var_154], r11d
0x18006b53a  cmovge  r8d, [rbp+110h+arg_38]
0x18006b542  cmp     r8d, eax
0x18006b545  cmovg   r8d, eax
0x18006b549  cmp     [rbp+110h+arg_40], ebx
0x18006b54f  mov     [rbp+110h+var_188], r8d
0x18006b553  cmovge  edx, [rbp+110h+arg_40]
0x18006b55a  cmp     edx, r11d
0x18006b55d  lea     r9d, [r8+r13]
0x18006b561  cmovg   edx, r11d
0x18006b565  mov     [rbp+110h+var_18C], edx
0x18006b568  test    r9d, r9d
0x18006b56b  js      loc_18006BA77
0x18006b571  cmp     r9d, eax
0x18006b574  jg      loc_18006BA82
0x18006b57a  lea     eax, [rdx+r12]
0x18006b57e  test    eax, eax
0x18006b580  js      loc_18006BA8D
0x18006b586  cmp     eax, r11d
0x18006b589  jg      loc_18006BA98
0x18006b58f  mov     eax, [rsp+210h+var_194]
0x18006b593  test    eax, eax
0x18006b595  jle     loc_18006B695
0x18006b59b  test    ecx, ecx
0x18006b59d  jle     loc_18006B695
0x18006b5a3  mov     rdx, [rbp+110h+var_180]
0x18006b5a7  cmp     [rdx+0B4h], ebx
0x18006b5ad  jnz     loc_18006BAA3
0x18006b5b3  mov     r8d, [rbp+110h+var_178]
0x18006b5b7  cmp     eax, r8d
0x18006b5ba  jz      loc_18006BBDC
0x18006b5c0  test    [rdx+8], r14b
0x18006b5c4  jnz     short loc_18006B5CC
0x18006b5c6  test    byte ptr [rdx+8], 2
0x18006b5ca  jz      short loc_18006B5DF
0x18006b5cc  mov     edx, [rdx+0B0h]
0x18006b5d2  mov     [rsp+210h+var_194], edx
0x18006b5d6  cmp     edx, 5
0x18006b5d9  jnz     loc_18006B6E6
0x18006b5df  cmp     [rbp+110h+arg_70], 0CC0020h
0x18006b5e9  jz      loc_18006B6C0
0x18006b5ef  mov     r14, [rbp+110h+var_180]
0x18006b5f3  mov     eax, 3
0x18006b5f8  mov     rcx, [rbp+110h+hdc]; hdc
0x18006b5fc  mov     edx, eax; mode
0x18006b5fe  call    cs:__imp_SetStretchBltMode
0x18006b605  nop     dword ptr [rax+rax+00h]
0x18006b60a  mov     eax, [rbp+110h+arg_70]
0x18006b610  mov     ecx, 0CC0020h
0x18006b615  cmp     eax, ecx
0x18006b617  jnz     loc_18006BE03
0x18006b61d  mov     r9d, [rbp+110h+DestWidth]; DestWidth
0x18006b624  mov     r8d, [rbp+110h+yDest]; yDest
0x18006b62b  mov     edx, [rbp+110h+xDest]; xDest
0x18006b62e  mov     [rsp+210h+rop], eax; rop
0x18006b632  mov     rax, [rbp+110h+var_170]
0x18006b636  mov     [rsp+210h+iUsage], r15d; iUsage
0x18006b63b  mov     [rsp+210h+lpbmi], rsi; lpbmi
0x18006b640  mov     rsi, [rbp+110h+hdc]
0x18006b644  mov     [rsp+210h+lpBits], rax; lpBits
0x18006b649  mov     rcx, rsi; hdc
0x18006b64c  mov     eax, [rbp+110h+var_18C]
0x18006b64f  mov     [rsp+210h+SrcHeight], r12d; SrcHeight
0x18006b654  mov     [rsp+210h+SrcWidth], r13d; SrcWidth
0x18006b659  mov     [rsp+210h+ySrc], eax; ySrc
0x18006b65d  mov     eax, [rbp+110h+var_188]
0x18006b660  mov     [rsp+210h+xSrc], eax; xSrc
0x18006b664  mov     eax, [rbp+110h+arg_30]
0x18006b66a  mov     [rsp+210h+DestHeight], eax; DestHeight
0x18006b66e  call    cs:__imp_StretchDIBits
0x18006b675  nop     dword ptr [rax+rax+00h]
0x18006b67a  test    rdi, rdi
0x18006b67d  jnz     loc_18006BE20
0x18006b683  cmp     [rbp+110h+var_164], ebx
0x18006b686  jnz     loc_18006BE48
0x18006b68c  cmp     [rbp+110h+var_158], ebx
0x18006b68f  jnz     loc_18006BE71
0x18006b695  mov     rcx, [rbp+110h+var_40]
0x18006b69c  xor     rcx, rsp; StackCookie
0x18006b69f  call    __security_check_cookie
0x18006b6a4  mov     rbx, [rsp+210h+arg_10]
0x18006b6ac  add     rsp, 1E0h
0x18006b6b3  pop     r15
0x18006b6b5  pop     r14
0x18006b6b7  pop     r13
0x18006b6b9  pop     r12
0x18006b6bb  pop     rdi
0x18006b6bc  pop     rsi
0x18006b6bd  pop     rbp
0x18006b6be  retn
0x18006b6c0  mov     r14, [rbp+110h+var_180]
0x18006b6c4  cmp     [r14+0B4h], ebx
0x18006b6cb  jnz     loc_18006BDF1
0x18006b6d1  test    byte ptr [r14+8], 4
0x18006b6d6  jnz     loc_18006B5F3
0x18006b6dc  mov     eax, 4
0x18006b6e1  jmp     loc_18006B5F8
0x18006b6e6  cmp     ecx, r14d
0x18006b6e9  jle     loc_18006B5DF
0x18006b6ef  cmp     eax, r14d
0x18006b6f2  jle     loc_18006B5DF
0x18006b6f8  mov     eax, r10d
0x18006b6fb  imul    eax, r8d
0x18006b6ff  cmp     eax, 800000h
0x18006b704  jge     loc_18006B5DF
0x18006b70a  xor     edx, edx
0x18006b70c  mov     ecx, 5E0h
0x18006b711  call    GpMallocEx
0x18006b716  test    rax, rax
0x18006b719  jz      loc_18006B5DF
0x18006b71f  mov     r8d, [rsp+210h+var_198]; int
0x18006b724  mov     r9d, 21808h; int
0x18006b72a  mov     edx, [rbp+110h+var_178]; int
0x18006b72d  mov     rcx, rax; this
0x18006b730  call    ??0GpBitmap@@QEAA@HHH@Z; GpBitmap::GpBitmap(int,int,int)
0x18006b735  mov     rdi, rax
0x18006b738  test    rax, rax
0x18006b73b  jz      loc_18006B5DF
0x18006b741  mov     rax, [rax]
0x18006b744  mov     rcx, rdi
0x18006b747  mov     rax, [rax+8]
0x18006b74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b750  test    eax, eax
0x18006b752  jz      loc_18006B5DF
0x18006b758  movzx   r8d, word ptr [rsi+0Eh]; unsigned int
0x18006b75d  lea     rax, [rsp+210h+Size]
0x18006b762  mov     r9d, [rsi+10h]; unsigned int
0x18006b766  mov     edx, [rsi]; unsigned int
0x18006b768  mov     ecx, [rbp+110h+arg_78]; int
0x18006b76e  mov     qword ptr [rsp+210h+xSrc], rax; unsigned int *
0x18006b773  mov     eax, [rsi+20h]
0x18006b776  mov     [rsp+210h+DestHeight], eax; unsigned int
0x18006b77a  mov     dword ptr [rsp+210h+Size], ebx
0x18006b77e  call    ?GetDibNumPalEntries@@YAHHIIIIPEAI@Z; GetDibNumPalEntries(int,uint,uint,uint,uint,uint *)
0x18006b783  test    eax, eax
0x18006b785  jz      loc_18006B5DF
0x18006b78b  test    sil, 3
0x18006b78f  jnz     loc_18006BBEA
0x18006b795  test    r15d, r15d
0x18006b798  jnz     loc_18006BBEA
0x18006b79e  mov     dword ptr [rsp+210h+Size], ebx
0x18006b7a2  mov     r15, rsi
0x18006b7a5  mov     [rbp+110h+var_128], rsi
0x18006b7a9  xor     edx, edx
0x18006b7ab  mov     [rbp+110h+var_190], r14d
0x18006b7af  mov     ecx, 5E0h
0x18006b7b4  call    GpMallocEx
0x18006b7b9  test    rax, rax
0x18006b7bc  jz      short loc_18006B7D9
0x18006b7be  mov     r8, [rbp+110h+var_170]; void *
0x18006b7c2  mov     rdx, r15; struct tagBITMAPINFO *
0x18006b7c5  mov     rcx, rax; this
0x18006b7c8  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18006b7cd  mov     r15, rax
0x18006b7d0  test    rax, rax
0x18006b7d3  jnz     loc_18006BC22
0x18006b7d9  cmp     dword ptr [rsp+210h+Size], ebx
0x18006b7dd  jnz     loc_18006BD53
0x18006b7e3  cmp     [rbp+110h+var_190], ebx
0x18006b7e6  jz      loc_18006BD61
0x18006b7ec  mov     r15d, dword ptr [rsp+210h+Size+4]
0x18006b7f1  jmp     loc_18006B5DF
0x18006b7f6  mov     eax, [rbp+110h+arg_40]
0x18006b7fc  mov     r12d, [rbp+110h+arg_50]
0x18006b803  mov     r13d, [rbp+110h+arg_48]
0x18006b80a  mov     [rbp+110h+var_18C], eax
0x18006b80d  mov     eax, [rbp+110h+arg_38]
0x18006b813  mov     [rbp+110h+var_188], eax
0x18006b816  jmp     loc_18006B5DF
0x18006b81b  lea     ecx, [rdx+rax]
0x18006b81e  cmp     ecx, eax
0x18006b820  jnb     loc_18006BAFD
0x18006b826  mov     r15d, dword ptr [rsp+210h+Size+4]
0x18006b82b  mov     r10d, [rsp+210h+var_198]
0x18006b830  mov     rdx, [rbp+110h+var_180]
0x18006b834  mov     ecx, [rbp+110h+var_190]
0x18006b837  mov     eax, [rsp+210h+var_194]
0x18006b83b  jmp     loc_18006B5B3
0x18006b840  lea     eax, [rdi+rcx]
0x18006b843  cmp     eax, edi
0x18006b845  jb      loc_18006B695
0x18006b84b  cmp     eax, [r13+0A8h]
0x18006b852  ja      loc_18006B695
0x18006b858  mov     r9d, [rbp+110h+xDest]
0x18006b85c  jmp     loc_18006B3FC
0x18006b861  test    sil, 3
0x18006b865  jz      loc_18006BAEB
0x18006b86b  mov     eax, r15d
0x18006b86e  neg     eax
0x18006b870  sbb     r15, r15
0x18006b873  and     r15, 0FFFFFFFFFFFFFFFEh
0x18006b877  add     r15, 4
0x18006b87b  cmp     dword ptr [rsp+210h+Size+4], r14d
0x18006b880  jnz     short loc_18006B899
0x18006b882  xor     r9d, r9d
0x18006b885  mov     qword ptr [rsp+210h+DestHeight], rbx
0x18006b88a  xor     r8d, r8d
0x18006b88d  mov     rdx, r14
  ... truncated ...
```
