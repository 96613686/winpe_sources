# MfEnumState::OutputDIB(HDC__ *,_RECTL const *,int,int,int,int,int,int,int,int,tagBITMAPINFOHEADER *,uchar *,uint,ulong,int)

- ea: `0x1800526b8`
- end: `0x180053137`
- name: `?OutputDIB@MfEnumState@@IEAAXPEAUHDC__@@PEBU_RECTL@@HHHHHHHHPEFAUtagBITMAPINFOHEADER@@PEAEIKH@Z`
- size: `2687`
- prototype: `void __fastcall(MfEnumState *this, HDC, const struct _RECTL *, int, LONG yDest, int DestWidth, int, int, int ySrc, int SrcWidth, int, struct tagBITMAPINFO *Src, unsigned __int8 *, UINT, DWORD rop, int)`
- caller_count: `5`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180055278`
- `0x18011d0d0`
- `0x18011d500`
- `0x18011da48`
- `0x18011f3e8`

## callees

- `0x18000390c`
- `0x180003b38`
- `0x1800083a4`
- `0x1800083f8`
- `0x18000e6d0`
- `0x180011960`
- `0x1800126d0`
- `0x18001489c`
- `0x18001f950`
- `0x1800526b8`
- `0x180053140`
- `0x180054174`
- `0x180054210`
- `0x180064e70`
- `0x180070dd4`
- `0x1800a370c`
- `0x1800e5044`
- `0x1800e9380`
- `0x180104d40`
- `0x18011e400`
- `0x18013c118`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `GDI32!SetStretchBltMode` at `0x180052fd4`
- `GDI32!SetStretchBltMode` at `0x180052fd4`
- `GDI32!StretchDIBits` at `0x180053093`
- `GDI32!StretchDIBits` at `0x180053093`
- `GDI32!SetBkColor` at `0x180052863`
- `GDI32!SetBkColor` at `0x1800530cf`
- `GDI32!SetBkColor` at `0x180052863`
- `GDI32!SetBkColor` at `0x1800530cf`
- `GDI32!SetTextColor` at `0x18005287d`
- `GDI32!SetTextColor` at `0x1800530e1`
- `GDI32!SetTextColor` at `0x18005287d`
- `GDI32!SetTextColor` at `0x1800530e1`
- `GDI32!DeleteObject` at `0x1800530f7`
- `GDI32!DeleteObject` at `0x1800530f7`
- `GDI32!LPtoDP` at `0x1800528dd`
- `GDI32!LPtoDP` at `0x1800528dd`

## pseudocode

```c
void __fastcall MfEnumState::OutputDIB(
        MfEnumState *this,
        HDC a2,
        const struct _RECTL *a3,
        int a4,
        LONG yDest,
        int DestWidth,
        int a7,
        int a8,
        int ySrc,
        int SrcWidth,
        int a11,
        struct tagBITMAPINFO *Src,
        unsigned __int8 *a13,
        UINT a14,
        DWORD rop,
        int a16)
{
  const BITMAPINFO *lpbmi; // rdi
  LONG v17; // r10d
  UINT iUsage; // r12d
  MfEnumState *v19; // r13
  int xSrc; // ebx
  DWORD biSize; // esi
  HDC v22; // r9
  DWORD biCompression; // r9d
  DWORD biClrUsed; // eax
  void *DibBits; // rax
  int v26; // eax
  int v27; // ecx
  GpBitmap *v28; // r15
  COLORREF v29; // eax
  COLORREF v30; // edx
  int SrcHeight; // esi
  int v32; // r13d
  LONG biWidth; // ecx
  unsigned int v34; // eax
  int v35; // r9d
  int v36; // esi
  LONG biHeight; // r11d
  int v38; // eax
  int v39; // eax
  bool v40; // cc
  int v41; // r10d
  int v42; // eax
  LONG v43; // eax
  unsigned int v44; // ebx
  MfEnumState *v45; // rax
  unsigned int biBitCount; // r8d
  DWORD v47; // r9d
  int v48; // r13d
  struct tagBITMAPINFOHEADER *p_bmiHeader; // r12
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  DWORD v52; // eax
  DWORD v53; // ebx
  __int64 v54; // rcx
  struct tagBITMAPINFOHEADER *v55; // rax
  unsigned int v56; // ecx
  int v57; // eax
  GpBitmap *v58; // rax
  GpBitmap *v59; // rax
  unsigned int v60; // r8d
  DWORD v61; // r9d
  struct tagBITMAPINFO *v62; // r12
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // rdx
  DWORD v65; // eax
  DWORD v66; // ebx
  __int64 v67; // rcx
  struct tagBITMAPINFO *v68; // rax
  GpBitmap *v69; // rax
  int v70; // r9d
  GpBitmap *v71; // rax
  GpBitmap *v72; // rbx
  __int64 v73; // rax
  unsigned int v74; // edx
  GpGraphics *v75; // r13
  HDC v76; // r14
  bool v77; // zf
  __int128 *v78; // r13
  int DestHeight[2]; // [rsp+20h] [rbp-E0h]
  int DestHeighta[2]; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+78h] [rbp-88h]
  int v83; // [rsp+80h] [rbp-80h]
  int v84; // [rsp+80h] [rbp-80h]
  unsigned int v85; // [rsp+84h] [rbp-7Ch] BYREF
  int IntDistance; // [rsp+88h] [rbp-78h]
  int v87; // [rsp+8Ch] [rbp-74h]
  COLORREF color; // [rsp+90h] [rbp-70h]
  COLORREF v89; // [rsp+94h] [rbp-6Ch]
  int v90; // [rsp+98h] [rbp-68h]
  void *lpBits; // [rsp+A0h] [rbp-60h]
  unsigned int v92; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v93; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v94; // [rsp+B0h] [rbp-50h] BYREF
  int v95; // [rsp+B4h] [rbp-4Ch]
  int xDest; // [rsp+B8h] [rbp-48h]
  __int128 *v97; // [rsp+C0h] [rbp-40h]
  HDC hdc; // [rsp+C8h] [rbp-38h]
  int v99; // [rsp+D0h] [rbp-30h]
  LONG v100; // [rsp+D4h] [rbp-2Ch]
  unsigned int v101; // [rsp+D8h] [rbp-28h]
  unsigned int v102; // [rsp+DCh] [rbp-24h]
  unsigned int v103; // [rsp+E0h] [rbp-20h]
  const BITMAPINFO *v104; // [rsp+E8h] [rbp-18h] BYREF
  void *v105; // [rsp+F0h] [rbp-10h] BYREF
  HGDIOBJ ho; // [rsp+F8h] [rbp-8h] BYREF
  float v107[4]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v108[4]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v109; // [rsp+120h] [rbp+20h] BYREF
  __int128 v110; // [rsp+130h] [rbp+30h]
  _BYTE v111[8]; // [rsp+140h] [rbp+40h] BYREF
  volatile signed __int32 *v112; // [rsp+148h] [rbp+48h]
  _BYTE v113[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v114; // [rsp+160h] [rbp+60h]
  __int64 v115; // [rsp+174h] [rbp+74h]
  int v116; // [rsp+17Ch] [rbp+7Ch]
  struct tagPOINT pt; // [rsp+188h] [rbp+88h] BYREF
  struct tagPOINT v118; // [rsp+190h] [rbp+90h] BYREF
  struct tagPOINT v119; // [rsp+198h] [rbp+98h] BYREF
  _DWORD v120[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v121; // [rsp+1B0h] [rbp+B0h]
  __int64 v122; // [rsp+1C0h] [rbp+C0h]
  int v123; // [rsp+1C8h] [rbp+C8h]

  lpbmi = Src;
  v17 = a4;
  iUsage = a14;
  v19 = this;
  xSrc = a8;
  biSize = Src->bmiHeader.biSize;
  xDest = a4;
  v22 = a2;
  hdc = a2;
  lpBits = a13;
  v87 = 0;
  color = 0;
  v89 = 0;
  if ( biSize < 0x28 )
    return;
  if ( a14 >= 2 )
  {
    TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(1, a14, 0);
    return;
  }
  if ( !a13 )
  {
    biCompression = Src->bmiHeader.biCompression;
    biClrUsed = Src->bmiHeader.biClrUsed;
    v92 = 0;
    if ( !(unsigned int)GetDibNumPalEntries(a16, biSize, Src->bmiHeader.biBitCount, biCompression, biClrUsed, &v92) )
      return;
    DibBits = (void *)GetDibBits(Src, v92, a14);
    v93 = 0;
    lpBits = DibBits;
    if ( !(unsigned int)GetDibBitsSize(&Src->bmiHeader, &v93)
      || Src->bmiHeader.biSizeImage && v93 > Src->bmiHeader.biSizeImage )
    {
      return;
    }
    if ( biSize + v93 < biSize || biSize + v93 > *((_DWORD *)v19 + 42) )
      return;
    v22 = hdc;
    v17 = xDest;
  }
  v26 = -DestWidth;
  v99 = 4;
  v97 = 0;
  ho = 0;
  if ( DestWidth >= 0 )
    v26 = DestWidth;
  v105 = 0;
  v104 = 0;
  v27 = -a7;
  v90 = 0;
  v28 = 0;
  if ( a7 >= 0 )
    v27 = a7;
  v109 = 0;
  v110 = 0;
  if ( Src->bmiHeader.biBitCount == 1 && rop != 13369376 )
  {
    v29 = SetBkColor(v22, *((_DWORD *)v19 + 47));
    v30 = *((_DWORD *)v19 + 48);
    color = v29;
    SrcHeight = a11;
    v89 = SetTextColor(hdc, v30);
    v87 = 1;
    goto LABEL_79;
  }
  v118.x = v17 + v26;
  pt.y = yDest;
  v118.y = yDest;
  pt.x = v17;
  v119.y = v27 + yDest;
  v119.x = v17;
  if ( !LPtoDP(v22, &pt, 3) )
    goto LABEL_117;
  IntDistance = GetIntDistance(&pt, &v118);
  v32 = GetIntDistance(&pt, &v119);
  biWidth = Src->bmiHeader.biWidth;
  v82 = v32;
  v101 = ((SrcWidth >> 31) & 0xFFFFFFFE) + 1;
  v34 = -SrcWidth;
  if ( SrcWidth >= 0 )
    v34 = SrcWidth;
  v35 = -a11;
  v85 = v34;
  v102 = ((a11 >> 31) & 0xFFFFFFFE) + 1;
  if ( a11 >= 0 )
    v35 = a11;
  v83 = v35;
  if ( biWidth > 0 )
  {
    v36 = biWidth;
    biHeight = -Src->bmiHeader.biHeight;
    if ( Src->bmiHeader.biHeight > 0 )
      biHeight = Src->bmiHeader.biHeight;
    v38 = 0;
    v100 = biHeight;
    if ( a8 >= 0 )
      v38 = a8;
    if ( v38 <= biWidth )
      v36 = v38;
    v39 = 0;
    if ( ySrc >= 0 )
      v39 = ySrc;
    v40 = v39 <= biHeight;
    v41 = v39;
    v42 = v36 + SrcWidth;
    if ( !v40 )
      v41 = biHeight;
    ySrc = v41;
    if ( v42 < 0 )
      SrcWidth = -v36;
    if ( v42 > biWidth )
      SrcWidth = biWidth - v36;
    v43 = v41 + a11;
    if ( v41 + a11 < 0 )
      a11 = -v41;
    if ( v43 > biHeight )
      a11 = biHeight - v41;
    v44 = v85;
    if ( (int)v85 > 0 && v35 > 0 )
    {
      v45 = this;
      if ( !*((_DWORD *)this + 45) || rop == 13369376 )
        goto LABEL_68;
      biBitCount = Src->bmiHeader.biBitCount;
      v47 = Src->bmiHeader.biCompression;
      v48 = 0;
      v94 = 0;
      if ( !(unsigned int)GetDibNumPalEntries(
                            a16,
                            Src->bmiHeader.biSize,
                            biBitCount,
                            v47,
                            Src->bmiHeader.biClrUsed,
                            &v94) )
      {
LABEL_67:
        v45 = this;
        v35 = v83;
        v32 = v82;
LABEL_68:
        if ( v44 == IntDistance )
        {
          xSrc = v36;
          if ( v35 == v32 )
            goto LABEL_73;
        }
        v56 = *((_DWORD *)v45 + 44);
        v103 = v56;
        if ( (*((_BYTE *)v45 + 8) & 1) == 0 && (*((_BYTE *)v45 + 8) & 2) == 0 )
          goto LABEL_72;
        xSrc = v36;
        if ( v56 == 5 )
          goto LABEL_73;
        if ( (int)v85 > 1 )
        {
          if ( v35 <= 1 || IntDistance * v32 >= 0x800000 )
            goto LABEL_73;
          v95 = 1;
          v58 = (GpBitmap *)GpMallocEx(1504, 0);
          if ( !v58 )
          {
            v28 = 0;
            goto LABEL_73;
          }
          v59 = GpBitmap::GpBitmap(v58, IntDistance, v32, 137224);
          v28 = v59;
          if ( !v59 || !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v59 + 8LL))(v59) )
            goto LABEL_114;
          v60 = Src->bmiHeader.biBitCount;
          v61 = Src->bmiHeader.biCompression;
          v85 = 0;
          v84 = 0;
          iUsage = a14;
          if ( !(unsigned int)GetDibNumPalEntries(a16, Src->bmiHeader.biSize, v60, v61, Src->bmiHeader.biClrUsed, &v85) )
            goto LABEL_73;
          if ( ((unsigned __int8)Src & 3) != 0 || a14 )
          {
            if ( a14 == 1 )
            {
              DestHeighta[1] = 0;
              TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 2, 0);
            }
            v63 = v85 * ((-(__int64)(a14 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4);
            if ( v63 > 0xFFFFFFFF )
              goto LABEL_73;
            v64 = 4LL * v85;
            if ( v64 > 0xFFFFFFFF )
              goto LABEL_73;
            v65 = Src->bmiHeader.biSize;
            v66 = Src->bmiHeader.biSize + v63;
            if ( v66 < Src->bmiHeader.biSize || (v67 = v65 + (unsigned int)v64, (unsigned int)v67 < v65) )
            {
LABEL_72:
              xSrc = v36;
LABEL_73:
              SrcHeight = a11;
LABEL_74:
              v19 = this;
              goto LABEL_75;
            }
            v68 = (struct tagBITMAPINFO *)GpMallocEx(v67, 1);
            v62 = v68;
            if ( !v68 )
            {
              xSrc = v36;
LABEL_114:
              iUsage = a14;
              goto LABEL_73;
            }
            memcpy_0(v68, Src, v66);
            v84 = 1;
          }
          else
          {
            v62 = Src;
          }
          v69 = (GpBitmap *)GpMallocEx(1504, 0);
          if ( v69 )
          {
            v71 = GpBitmap::GpBitmap(v69, v62, lpBits, v70);
            v72 = v71;
            if ( v71 )
            {
              if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v71 + 8LL))(v71) )
              {
                v73 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)v28 + 128LL))(v28);
                v75 = (GpGraphics *)v73;
                if ( v73 )
                {
                  if ( *(_DWORD *)(v73 + 8) == 1634879281 )
                  {
                    GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v111, (struct GpRuntime::GpLockable *)(v73 + 16));
                    v108[0] = 0;
                    v108[1] = 0;
                    *(float *)&v108[3] = (float)v82;
                    *(float *)&v108[2] = (float)IntDistance;
                    v107[1] = (float)(v100 - ySrc - a11);
                    v107[2] = (float)(int)(SrcWidth - v101);
                    v107[3] = (float)(int)(a11 - v102);
                    v107[0] = (float)v36;
                    GpGraphics::SetCompositingMode(v75, 1);
                    GpGraphics::SetInterpolationMode(v75, v103);
                    GpImageAttributes::GpImageAttributes((GpImageAttributes *)v113);
                    v115 = 3;
                    v116 = 0;
                    v114 = 0;
                    DestHeighta[0] = 2;
                    v95 = GpGraphics::DrawImage(v75, v72, v108, v107, *(_QWORD *)DestHeighta, v113);
                    GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v113);
                    _InterlockedDecrement(v112);
                  }
                  GpGraphics::`scalar deleting destructor'(v75, v74);
                }
                v32 = v82;
              }
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v72 + 56LL))(v72);
            }
          }
          if ( v84 )
            GpFree(v62);
          xSrc = v36;
          if ( !v95 && !(unsigned int)GpBitmap::LockBits(v28, 0, 1, 137224, &v109) )
          {
            v123 = 0;
            lpbmi = (const BITMAPINFO *)v120;
            v122 = 0;
            xSrc = 0;
            ySrc = 0;
            iUsage = 0;
            SrcHeight = v32;
            lpBits = (void *)v110;
            v120[2] = -v32;
            v121 = 0;
            v97 = &v109;
            SrcWidth = IntDistance;
            v120[0] = 40;
            v120[1] = IntDistance;
            v120[3] = 1572865;
            goto LABEL_74;
          }
          goto LABEL_114;
        }
        v19 = this;
LABEL_117:
        SrcHeight = a11;
LABEL_75:
        if ( rop == 13369376
          && (!*((_DWORD *)v19 + 45) || Globals::OsVer.dwMajorVersion != 4)
          && (*((_BYTE *)v19 + 8) & 4) == 0 )
        {
          v57 = v99;
LABEL_119:
          v76 = hdc;
          SetStretchBltMode(hdc, v57);
          if ( rop == 13369376 || Globals::OsVer.dwMajorVersion != 4 )
          {
            v78 = v97;
          }
          else
          {
            v77 = (*((_DWORD *)v19 + 2) & 0x10000) == 0;
            v78 = v97;
            if ( !v77 )
              rop = 13369376;
          }
          StretchDIBits(v76, xDest, yDest, DestWidth, a7, xSrc, ySrc, SrcWidth, SrcHeight, lpBits, lpbmi, iUsage, rop);
          if ( v28 )
          {
            if ( v78 )
              GpBitmap::UnlockBits(v28, v78);
            (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v28 + 56LL))(v28);
          }
          if ( v87 )
          {
            SetBkColor(v76, color);
            SetTextColor(v76, v89);
          }
          if ( v90 )
          {
            DeleteObject(ho);
            GpFree(v104);
          }
          return;
        }
LABEL_79:
        v19 = this;
        v57 = 3;
        goto LABEL_119;
      }
      if ( ((unsigned __int8)Src & 3) != 0 || a14 )
      {
        if ( a14 == 1 )
        {
          DestHeight[1] = 0;
          TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 1, 0);
        }
        v50 = v94 * ((-(__int64)(a14 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4);
        if ( v50 > 0xFFFFFFFF )
          goto LABEL_67;
        v51 = 4LL * v94;
        if ( v51 > 0xFFFFFFFF )
          goto LABEL_67;
        v52 = Src->bmiHeader.biSize;
        v53 = Src->bmiHeader.biSize + v50;
        if ( v53 < Src->bmiHeader.biSize )
          goto LABEL_66;
        v54 = v52 + (unsigned int)v51;
        if ( (unsigned int)v54 < v52 )
          goto LABEL_66;
        v55 = (struct tagBITMAPINFOHEADER *)GpMallocEx(v54, 1);
        p_bmiHeader = v55;
        if ( !v55 )
        {
LABEL_65:
          iUsage = a14;
LABEL_66:
          v44 = v85;
          goto LABEL_67;
        }
        memcpy_0(v55, Src, v53);
        v48 = 1;
      }
      else
      {
        p_bmiHeader = &Src->bmiHeader;
      }
      DestHeight[0] = ySrc;
      if ( !(unsigned int)GpBitmap::DrawAndHalftoneForStretchBlt(
                            hdc,
                            p_bmiHeader,
                            lpBits,
                            (unsigned int)v36,
                            *(_QWORD *)DestHeight,
                            v85,
                            v83,
                            IntDistance,
                            v82,
                            &v104,
                            &v105,
                            &ho,
                            *((_DWORD *)this + 44)) )
      {
        xSrc = 0;
        ySrc = 0;
        SrcHeight = v82;
        lpbmi = v104;
        SrcWidth = IntDistance;
        v90 = 1;
        lpBits = v105;
        if ( v48 )
          GpFree(p_bmiHeader);
        iUsage = a14;
        goto LABEL_79;
      }
      if ( v48 )
        GpFree(p_bmiHeader);
      goto LABEL_65;
    }
  }
}

```

## disassembly

```asm
0x1800526b8  mov     [rsp-8+arg_10], rbx
0x1800526bd  push    rbp
0x1800526be  push    rsi
0x1800526bf  push    rdi
0x1800526c0  push    r12
0x1800526c2  push    r13
0x1800526c4  push    r14
0x1800526c6  push    r15
0x1800526c8  lea     rbp, [rsp-0E0h]
0x1800526d0  sub     rsp, 1E0h
0x1800526d7  mov     rax, cs:__security_cookie
0x1800526de  xor     rax, rsp
0x1800526e1  mov     [rbp+110h+var_40], rax
0x1800526e8  mov     rdi, [rbp+110h+Src]
0x1800526ef  xor     r8d, r8d
0x1800526f2  mov     rax, [rbp+110h+arg_60]
0x1800526f9  mov     r10d, r9d
0x1800526fc  mov     r12d, [rbp+110h+arg_68]
0x180052703  mov     r13, rcx
0x180052706  mov     ebx, [rbp+110h+arg_38]
0x18005270c  mov     esi, [rdi]
0x18005270e  mov     r14d, [rbp+110h+DestWidth]
0x180052715  mov     [rbp+110h+xDest], r9d
0x180052719  mov     r9, rdx
0x18005271c  mov     [rbp+110h+hdc], rdx
0x180052720  mov     [rsp+210h+var_1A0], rcx
0x180052725  mov     [rbp+110h+var_170], rax
0x180052729  mov     [rsp+210h+var_194], r12d
0x18005272e  mov     [rbp+110h+var_184], r8d
0x180052732  mov     [rbp+110h+color], r8d
0x180052736  mov     [rbp+110h+var_17C], r8d
0x18005273a  cmp     esi, 28h ; '('
0x18005273d  jb      loc_18005310C
0x180052743  cmp     r12d, 2
0x180052747  jb      short loc_180052762
0x180052749  mov     edx, r12d
0x18005274c  mov     qword ptr [rsp+210h+DestHeight], r8
0x180052751  xor     r9d, r9d
0x180052754  lea     ecx, [r8+1]
0x180052758  call    ?TraceLoggingUnsupportedGdiPlusUsage@TraceLogging@@YAXW4UnsupportedReason@1@_K111@Z; TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(TraceLogging::UnsupportedReason,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x18005275d  jmp     loc_18005310C
0x180052762  test    rax, rax
0x180052765  jnz     loc_1800527FC
0x18005276b  mov     r9d, [rdi+10h]; unsigned int
0x18005276f  lea     rax, [rbp+110h+var_168]
0x180052773  mov     ecx, [rbp+110h+arg_78]; int
0x180052779  mov     edx, esi; unsigned int
0x18005277b  mov     qword ptr [rsp+210h+xSrc], rax; unsigned int *
0x180052780  mov     eax, [rdi+20h]
0x180052783  mov     [rbp+110h+var_168], r8d
0x180052787  movzx   r8d, word ptr [rdi+0Eh]; unsigned int
0x18005278c  mov     [rsp+210h+DestHeight], eax; unsigned int
0x180052790  call    ?GetDibNumPalEntries@@YAHHIIIIPEAI@Z; GetDibNumPalEntries(int,uint,uint,uint,uint,uint *)
0x180052795  test    eax, eax
0x180052797  jz      loc_18005310C
0x18005279d  mov     edx, [rbp+110h+var_168]
0x1800527a0  mov     r8d, r12d
0x1800527a3  mov     rcx, rdi
0x1800527a6  call    GetDibBits
0x1800527ab  and     [rbp+110h+var_164], 0
0x1800527af  lea     rdx, [rbp+110h+var_164]; unsigned int *
0x1800527b3  mov     rcx, rdi; struct tagBITMAPINFOHEADER *
0x1800527b6  mov     [rbp+110h+var_170], rax
0x1800527ba  call    ?GetDibBitsSize@@YAHPEFAUtagBITMAPINFOHEADER@@PEAI@Z; GetDibBitsSize(tagBITMAPINFOHEADER *,uint *)
0x1800527bf  xor     r8d, r8d
0x1800527c2  test    eax, eax
0x1800527c4  jz      loc_18005310C
0x1800527ca  mov     ecx, [rbp+110h+var_164]
0x1800527cd  cmp     [rdi+14h], r8d
0x1800527d1  jz      short loc_1800527DC
0x1800527d3  cmp     ecx, [rdi+14h]
0x1800527d6  ja      loc_18005310C
0x1800527dc  lea     eax, [rsi+rcx]
0x1800527df  cmp     eax, esi
0x1800527e1  jb      loc_18005310C
0x1800527e7  cmp     eax, [r13+0A8h]
0x1800527ee  ja      loc_18005310C
0x1800527f4  mov     r9, [rbp+110h+hdc]
0x1800527f8  mov     r10d, [rbp+110h+xDest]
0x1800527fc  mov     edx, [rbp+110h+arg_30]
0x180052802  mov     eax, r14d
0x180052805  neg     eax
0x180052807  mov     [rbp+110h+var_140], 4
0x18005280e  test    r14d, r14d
0x180052811  mov     [rbp+110h+var_150], r8
0x180052815  xorps   xmm0, xmm0
0x180052818  mov     [rbp+110h+ho], r8
0x18005281c  cmovns  eax, r14d
0x180052820  mov     [rbp+110h+var_120], r8
0x180052824  mov     ecx, edx
0x180052826  mov     [rbp+110h+var_128], r8
0x18005282a  neg     ecx
0x18005282c  mov     [rbp+110h+var_178], r8d
0x180052830  test    edx, edx
0x180052832  mov     r14d, 1
0x180052838  mov     r15, r8
0x18005283b  cmovns  ecx, edx
0x18005283e  movups  [rbp+110h+var_F0], xmm0
0x180052842  movups  [rbp+110h+var_E0], xmm0
0x180052846  cmp     [rdi+0Eh], r14w
0x18005284b  jnz     short loc_18005289B
0x18005284d  cmp     [rbp+110h+arg_70], 0CC0020h
0x180052857  jz      short loc_18005289B
0x180052859  mov     edx, [r13+0BCh]; color
0x180052860  mov     rcx, r9; hdc
0x180052863  call    cs:__imp_SetBkColor
0x18005286a  nop     dword ptr [rax+rax+00h]
0x18005286f  mov     edx, [r13+0C0h]; color
0x180052876  mov     rcx, [rbp+110h+hdc]; hdc
0x18005287a  mov     [rbp+110h+color], eax
0x18005287d  call    cs:__imp_SetTextColor
0x180052884  nop     dword ptr [rax+rax+00h]
0x180052889  mov     esi, [rbp+110h+arg_50]
0x18005288f  mov     [rbp+110h+var_17C], eax
0x180052892  mov     [rbp+110h+var_184], r14d
0x180052896  jmp     loc_180052C23
0x18005289b  mov     edx, [rbp+110h+yDest]
0x1800528a1  add     eax, r10d
0x1800528a4  mov     [rbp+110h+var_80.x], eax
0x1800528aa  mov     r8d, 3; c
0x1800528b0  mov     [rbp+110h+pt.y], edx
0x1800528b6  mov     [rbp+110h+var_80.y], edx
0x1800528bc  lea     eax, [rcx+rdx]
0x1800528bf  mov     [rbp+110h+pt.x], r10d
0x1800528c6  lea     rdx, [rbp+110h+pt]; lppt
0x1800528cd  mov     [rbp+110h+var_78.y], eax
0x1800528d3  mov     rcx, r9; hdc
0x1800528d6  mov     [rbp+110h+var_78.x], r10d
0x1800528dd  call    cs:__imp_LPtoDP
0x1800528e4  nop     dword ptr [rax+rax+00h]
0x1800528e9  test    eax, eax
0x1800528eb  jz      loc_180052FBD
0x1800528f1  lea     rdx, [rbp+110h+var_80]; struct tagPOINT *
0x1800528f8  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x1800528ff  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x180052904  lea     rdx, [rbp+110h+var_78]; struct tagPOINT *
0x18005290b  mov     [rbp+110h+var_188], eax
0x18005290e  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x180052915  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x18005291a  mov     r8d, [rbp+110h+arg_48]
0x180052921  mov     r13d, eax
0x180052924  mov     edx, [rbp+110h+arg_50]
0x18005292a  mov     r9d, edx
0x18005292d  mov     ecx, [rdi+4]
0x180052930  mov     [rsp+210h+var_198], eax
0x180052934  mov     eax, r8d
0x180052937  sar     eax, 1Fh
0x18005293a  and     eax, 0FFFFFFFEh
0x18005293d  add     eax, r14d
0x180052940  mov     [rbp+110h+var_138], eax
0x180052943  mov     eax, r8d
0x180052946  neg     eax
0x180052948  test    r8d, r8d
0x18005294b  cmovns  eax, r8d
0x18005294f  neg     r9d
0x180052952  mov     [rbp+110h+var_18C], eax
0x180052955  mov     eax, edx
0x180052957  sar     eax, 1Fh
0x18005295a  and     eax, 0FFFFFFFEh
0x18005295d  add     eax, r14d
0x180052960  test    edx, edx
0x180052962  mov     [rbp+110h+var_134], eax
0x180052965  cmovns  r9d, edx
0x180052969  mov     [rbp+110h+var_190], r9d
0x18005296d  test    ecx, ecx
0x18005296f  jle     loc_18005310C
0x180052975  mov     r10d, [rbp+110h+arg_40]
0x18005297c  mov     esi, ecx
0x18005297e  mov     r11d, [rdi+8]
0x180052982  neg     r11d
0x180052985  cmovs   r11d, [rdi+8]
0x18005298a  xor     eax, eax
0x18005298c  test    ebx, ebx
0x18005298e  mov     [rbp+110h+var_13C], r11d
0x180052992  cmovns  eax, ebx
0x180052995  cmp     eax, ecx
0x180052997  cmovle  esi, eax
0x18005299a  xor     eax, eax
0x18005299c  test    r10d, r10d
0x18005299f  cmovns  eax, r10d
0x1800529a3  cmp     eax, r11d
0x1800529a6  mov     r10d, eax
0x1800529a9  lea     eax, [rsi+r8]
0x1800529ad  cmovg   r10d, r11d
0x1800529b1  mov     [rbp+110h+arg_40], r10d
0x1800529b8  test    eax, eax
0x1800529ba  jns     short loc_1800529C9
0x1800529bc  mov     r8d, esi
0x1800529bf  neg     r8d
0x1800529c2  mov     [rbp+110h+arg_48], r8d
0x1800529c9  cmp     eax, ecx
0x1800529cb  jle     short loc_1800529D7
0x1800529cd  mov     eax, ecx
0x1800529cf  sub     eax, esi
0x1800529d1  mov     [rbp+110h+arg_48], eax
0x1800529d7  lea     eax, [r10+rdx]
0x1800529db  test    eax, eax
0x1800529dd  jns     short loc_1800529EA
0x1800529df  mov     ecx, r10d
0x1800529e2  neg     ecx
0x1800529e4  mov     [rbp+110h+arg_50], ecx
0x1800529ea  cmp     eax, r11d
0x1800529ed  jle     short loc_1800529FB
0x1800529ef  mov     eax, r11d
0x1800529f2  sub     eax, r10d
0x1800529f5  mov     [rbp+110h+arg_50], eax
0x1800529fb  mov     ebx, [rbp+110h+var_18C]
0x1800529fe  test    ebx, ebx
0x180052a00  jle     loc_18005310C
0x180052a06  test    r9d, r9d
0x180052a09  jle     loc_18005310C
0x180052a0f  mov     rax, [rsp+210h+var_1A0]
0x180052a14  cmp     dword ptr [rax+0B4h], 0
0x180052a1b  jz      loc_180052BC9
0x180052a21  cmp     [rbp+110h+arg_70], 0CC0020h
0x180052a2b  jz      loc_180052BC9
0x180052a31  movzx   r8d, word ptr [rdi+0Eh]; unsigned int
0x180052a36  lea     rax, [rbp+110h+var_160]
0x180052a3a  mov     r9d, [rdi+10h]; unsigned int
0x180052a3e  xor     r13d, r13d
0x180052a41  mov     ecx, [rbp+110h+arg_78]; int
0x180052a47  and     [rbp+110h+var_160], r13d
0x180052a4b  mov     edx, [rdi]; unsigned int
0x180052a4d  mov     qword ptr [rsp+210h+xSrc], rax; unsigned int *
0x180052a52  mov     eax, [rdi+20h]
0x180052a55  mov     [rsp+210h+DestHeight], eax; unsigned int
0x180052a59  call    ?GetDibNumPalEntries@@YAHHIIIIPEAI@Z; GetDibNumPalEntries(int,uint,uint,uint,uint,uint *)
0x180052a5e  test    eax, eax
0x180052a60  jz      loc_180052BBB
0x180052a66  test    dil, 3
0x180052a6a  jnz     short loc_180052A79
0x180052a6c  test    r12d, r12d
0x180052a6f  jnz     short loc_180052A79
0x180052a71  mov     r12, rdi
0x180052a74  jmp     loc_180052B05
0x180052a79  cmp     r12d, r14d
0x180052a7c  jnz     short loc_180052A95
0x180052a7e  and     qword ptr [rsp+210h+DestHeight], r13
0x180052a83  xor     r9d, r9d
0x180052a86  xor     r8d, r8d
0x180052a89  mov     rdx, r14
0x180052a8c  lea     ecx, [r9+2]
0x180052a90  call    ?TraceLoggingUnsupportedGdiPlusUsage@TraceLogging@@YAXW4UnsupportedReason@1@_K111@Z; TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(TraceLogging::UnsupportedReason,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x180052a95  mov     edx, [rbp+110h+var_160]
0x180052a98  mov     eax, r12d
0x180052a9b  neg     eax
0x180052a9d  mov     r8d, 0FFFFFFFFh
0x180052aa3  sbb     rcx, rcx
0x180052aa6  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180052aaa  add     rcx, 4
0x180052aae  imul    rcx, rdx
0x180052ab2  cmp     rcx, r8
0x180052ab5  ja      loc_180052BBB
0x180052abb  shl     rdx, 2
0x180052abf  cmp     rdx, r8
0x180052ac2  ja      loc_180052BBB
0x180052ac8  mov     eax, [rdi]
0x180052aca  lea     ebx, [rax+rcx]
0x180052acd  cmp     ebx, eax
0x180052acf  jb      loc_180052BB8
0x180052ad5  lea     ecx, [rax+rdx]
0x180052ad8  cmp     ecx, eax
0x180052ada  jb      loc_180052BB8
0x180052ae0  mov     edx, r14d
0x180052ae3  call    GpMallocEx
0x180052ae8  mov     r12, rax
0x180052aeb  test    rax, rax
0x180052aee  jz      loc_180052BB3
0x180052af4  mov     r8d, ebx; Size
0x180052af7  mov     rdx, rdi; Src
0x180052afa  mov     rcx, rax; void *
0x180052afd  call    memcpy_0
0x180052b02  mov     r13d, r14d
0x180052b05  mov     rcx, [rsp+210h+var_1A0]
0x180052b0a  lea     rax, [rbp+110h+ho]
0x180052b0e  mov     edx, [rbp+110h+var_188]
0x180052b11  mov     r9d, esi
0x180052b14  mov     r8, [rbp+110h+var_170]
0x180052b18  mov     ecx, [rcx+0B0h]
0x180052b1e  mov     [rsp+210h+rop], ecx
0x180052b22  mov     rcx, [rbp+110h+hdc]
0x180052b26  mov     qword ptr [rsp+210h+iUsage], rax
0x180052b2b  lea     rax, [rbp+110h+var_120]
0x180052b2f  mov     [rsp+210h+lpbmi], rax
0x180052b34  lea     rax, [rbp+110h+var_128]
0x180052b38  mov     [rsp+210h+lpBits], rax
0x180052b3d  mov     eax, [rsp+210h+var_198]
0x180052b41  mov     [rsp+210h+SrcHeight], eax
0x180052b45  mov     eax, [rbp+110h+var_190]
0x180052b48  mov     [rsp+210h+SrcWidth], edx
0x180052b4c  mov     rdx, r12
0x180052b4f  mov     [rsp+210h+ySrc], eax
0x180052b53  mov     eax, [rbp+110h+var_18C]
0x180052b56  mov     [rsp+210h+xSrc], eax
0x180052b5a  mov     eax, [rbp+110h+arg_40]
0x180052b60  mov     [rsp+210h+DestHeight], eax
0x180052b64  call    ?DrawAndHalftoneForStretchBlt@GpBitmap@@SA?AW4Status@@PEAUHDC__@@PEAUtagBITMAPINFO@@PEAEHHHHHHPEAPEAU4@PEAPEAEPEAPEAUHBITMAP__@@W4InterpolationMode@@@Z; GpBitmap::DrawAndHalftoneForStretchBlt(HDC__ *,tagBITMAPINFO *,uchar *,int,int,int,int,int,int,tagBITMAPINFO * *,uchar * *,HBITMAP__ * *,InterpolationMode)
0x180052b69  test    eax, eax
0x180052b6b  jnz     short loc_180052BA6
0x180052b6d  mov     eax, [rbp+110h+var_188]
  ... truncated ...
```
