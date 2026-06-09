# MF_AnyBitBlt

- ea: `0x180020a00`
- end: `0x180021484`
- name: `MF_AnyBitBlt`
- size: `2692`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct tagPOINT *, HDC hdc, int, int, int, int, __int64, int, int, unsigned int, int)`
- caller_count: `7`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18001d880`
- `0x18001ff10`
- `0x1800218b0`
- `0x180068760`
- `0x18006f310`
- `0x180075e30`
- `0x180093580`

## callees

- `0x18000d6c0`
- `0x18000e5a0`
- `0x180010000`
- `0x1800102f0`
- `0x1800104e0`
- `0x18001da40`
- `0x18001fe20`
- `0x1800200f0`
- `0x1800201b0`
- `0x180020a00`
- `0x18002148c`
- `0x180021644`
- `0x1800218b0`
- `0x180023110`
- `0x180029790`
- `0x1800518e0`
- `0x18005ce70`
- `0x180069258`
- `0x18007ac50`
- `0x18008c3c4`
- `0x18008c4ec`
- `0x18008c710`
- `0x18008c8a4`

## import_xrefs

- `GDI32!DeleteDC` at `0x180020fc8`
- `GDI32!DeleteDC` at `0x180020fc8`
- `GDI32!GetDeviceCaps` at `0x180020d6d`
- `GDI32!GetDeviceCaps` at `0x180020d7f`
- `GDI32!GetDeviceCaps` at `0x180020d6d`
- `GDI32!GetDeviceCaps` at `0x180020d7f`
- `GDI32!RestoreDC` at `0x180020fac`
- `GDI32!RestoreDC` at `0x180020fac`
- `GDI32!SaveDC` at `0x180020e1e`
- `GDI32!SaveDC` at `0x180020e1e`
- `GDI32!SelectObject` at `0x180020e09`
- `GDI32!SelectObject` at `0x180020ed4`
- `GDI32!SelectObject` at `0x180021479`
- `GDI32!SelectObject` at `0x180020e09`
- `GDI32!SelectObject` at `0x180020ed4`
- `GDI32!SelectObject` at `0x180021479`
- `GDI32!pldcGet` at `0x180020a72`
- `GDI32!pldcGet` at `0x180020fe0`
- `GDI32!pldcGet` at `0x180020a72`
- `GDI32!pldcGet` at `0x180020fe0`
- `GDI32!GdiSetLastError` at `0x180020c2d`
- `GDI32!GdiSetLastError` at `0x180020c2d`
- `GDI32!DeleteObject` at `0x180020fbe`
- `GDI32!DeleteObject` at `0x180020fbe`
- `win32u!NtGdiGetNearestColor` at `0x180020c59`
- `win32u!NtGdiGetNearestColor` at `0x180020c59`
- `win32u!NtGdiGetTransform` at `0x180020b10`
- `win32u!NtGdiGetTransform` at `0x180020b10`

## pseudocode

```c
__int64 __fastcall MF_AnyBitBlt(
        HDC a1,
        int a2,
        int a3,
        int a4,
        int a5,
        struct tagPOINT *a6,
        HDC hdc,
        LONG a8,
        LONG a9,
        int a10,
        int a11,
        HBITMAP a12,
        int a13,
        int a14,
        unsigned int a15,
        int a16)
{
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // r15
  unsigned int v20; // esi
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  MRBB *v23; // rcx
  COLORREF BkColor; // eax
  LONG x; // ecx
  LONG v27; // r12d
  LONG y; // edx
  LONG v29; // r14d
  int v30; // r12d
  int v31; // r14d
  void *DCObject; // rax
  int DeviceCaps; // r13d
  int v34; // ecx
  LONG v35; // eax
  LONG v36; // eax
  unsigned int v37; // r13d
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v39; // r14
  HGDIOBJ v40; // r12
  HDC v41; // rsi
  unsigned int v42; // eax
  __int64 v43; // rax
  unsigned int v44; // [rsp+A0h] [rbp-80h]
  unsigned int NearestColor; // [rsp+A0h] [rbp-80h]
  unsigned int v46; // [rsp+A4h] [rbp-7Ch] BYREF
  unsigned int v47; // [rsp+A8h] [rbp-78h] BYREF
  int v48; // [rsp+ACh] [rbp-74h]
  int v49; // [rsp+B0h] [rbp-70h]
  int v50; // [rsp+B4h] [rbp-6Ch]
  unsigned int v51; // [rsp+B8h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+BCh] [rbp-64h] BYREF
  HDC CompatibleDC; // [rsp+C0h] [rbp-60h]
  struct tagBITMAPINFOHEADER *v54; // [rsp+C8h] [rbp-58h]
  int cy; // [rsp+D0h] [rbp-50h]
  int v56; // [rsp+D4h] [rbp-4Ch]
  HBITMAP v57; // [rsp+D8h] [rbp-48h]
  _OWORD pv[2]; // [rsp+E0h] [rbp-40h] BYREF
  struct tagPOINT pt; // [rsp+100h] [rbp-20h] BYREF
  LONG v60; // [rsp+108h] [rbp-18h]
  LONG v61; // [rsp+10Ch] [rbp-14h]
  struct tagXFORM v62; // [rsp+110h] [rbp-10h] BYREF
  struct tagBITMAPINFOHEADER v63; // [rsp+128h] [rbp+8h] BYREF
  _OWORD v64[2]; // [rsp+150h] [rbp+30h] BYREF
  __int64 v65; // [rsp+170h] [rbp+50h]

  v57 = a12;
  memset(v64, 0, sizeof(v64));
  v65 = 0;
  memset(&v62, 0, sizeof(v62));
  v48 = a4;
  v49 = a3;
  v50 = a2;
  CompatibleDC = a1;
  v52 = 0;
  v51 = 0;
  v17 = pldcGet(a1);
  v18 = v17;
  if ( !v17 || ((unsigned int)a1 & 0x7F0000) == 0x660000 )
    goto LABEL_20;
  v19 = *(_QWORD *)(v17 + 16);
  v20 = 1;
  v54 = 0;
  if ( a12 )
  {
    if ( !(unsigned int)bMetaGetDIBInfo(a1, a12, v64, &v52, &v51, 2, 0, 0) )
      return 0;
    v54 = (struct tagBITMAPINFOHEADER *)v64;
    if ( WORD6(v64[0]) != 1 && HIWORD(v64[0]) != 1 )
      return 0;
  }
  if ( (unsigned int)(a16 - 76) <= 1 && (a15 & 0x7F000000) != 0 )
    return 0;
  v44 = 4 * (a15 & 0xF3330000);
  if ( (a15 & 0xCCCC0000) != v44
    || (v21 = (unsigned int)(a16 - 78), (unsigned int)v21 <= 0x26) && (v22 = 0x5000000001LL, _bittest64(&v22, v21)) )
  {
    if ( !(unsigned int)NtGdiGetTransform(hdc, 516, &v62) || v62.eM12 != 0.0 || v62.eM21 != 0.0 )
      return 0;
    *(_DWORD *)(v18 + 8) |= 0x20000000u;
    if ( (a15 & 0xCCCC0000) != v44 )
      goto LABEL_22;
  }
  if ( ((a16 - 114) & 0xFFFFFFFD) == 0 )
  {
LABEL_22:
    if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    {
LABEL_23:
      BkColor = GetBkColor(hdc);
      NearestColor = NtGdiGetNearestColor(hdc, BkColor);
      if ( NearestColor != -1 )
      {
        pt.y = a9;
        pt.x = a8;
        v60 = a10 + a8;
        v47 = 0;
        v61 = a9 + a11;
        v46 = 0;
        memset(&v63, 0, sizeof(v63));
        if ( LPtoDP(hdc, &pt, 2) )
        {
          x = pt.x;
          v27 = v60;
          if ( pt.x > v60 )
          {
            x = v60;
            v27 = pt.x;
          }
          y = pt.y;
          v29 = v61;
          if ( pt.y > v61 )
          {
            y = v61;
            v29 = pt.y;
          }
          pt.x = x - 1;
          v60 = v27 + 1;
          v30 = v27 + 1 - (x - 1);
          v61 = v29 + 1;
          pt.y = y - 1;
          v31 = v29 + 1 - (y - 1);
          v62.eDx = v62.eDx - (float)(x - 1);
          v62.eDy = v62.eDy - (float)(y - 1);
          DCObject = (void *)GetDCObject(hdc, 327680);
          memset(pv, 0, sizeof(pv));
          if ( DCObject && GetObjectA(DCObject, 32, pv) )
          {
            DeviceCaps = DWORD1(pv[0]);
            v34 = DWORD2(pv[0]);
          }
          else
          {
            DeviceCaps = GetDeviceCaps(CompatibleDC, 118);
            v34 = GetDeviceCaps(CompatibleDC, 117);
          }
          v35 = pt.x;
          if ( pt.x < 0 )
          {
            v30 += pt.x;
            pt.x = 0;
            v62.eDx = v62.eDx + (float)v35;
          }
          if ( v60 >= DeviceCaps )
          {
            v30 += DeviceCaps - v60 - 1;
            v60 = DeviceCaps - 1;
          }
          v36 = pt.y;
          if ( pt.y < 0 )
          {
            v31 += pt.y;
            pt.y = 0;
            v62.eDy = v62.eDy + (float)v36;
          }
          if ( v61 >= v34 )
          {
            v31 += v34 - v61 - 1;
            v61 = v34 - 1;
          }
          if ( v30 < 0 || v31 < 0 )
            return v20;
          v37 = 0;
          CompatibleDC = CreateCompatibleDC(hdc);
          if ( !CompatibleDC )
            return v37;
          v56 = v30 + 1;
          cy = v31 + 1;
          CompatibleBitmap = CreateCompatibleBitmap(hdc, v30 + 1, v31 + 1);
          v39 = CompatibleBitmap;
          if ( !CompatibleBitmap )
          {
LABEL_58:
            DeleteDC(CompatibleDC);
            return v37;
          }
          v40 = SelectObject(CompatibleDC, CompatibleBitmap);
          if ( !v40 )
          {
LABEL_57:
            DeleteObject(v39);
            goto LABEL_58;
          }
          if ( !SaveDC(hdc) )
          {
LABEL_81:
            SelectObject(CompatibleDC, v40);
            goto LABEL_57;
          }
          SetGraphicsMode(hdc, 2);
          if ( SetMapMode(hdc, 1) )
          {
            if ( ModifyWorldTransform(hdc, 0, 1u) )
            {
              if ( SetWindowOrgEx(hdc, 0, 0, 0) )
              {
                if ( SetViewportOrgEx(hdc, 0, 0, 0) )
                {
                  v41 = CompatibleDC;
                  if ( BitBlt(CompatibleDC, 0, 0, v56, cy, hdc, pt.x, pt.y, 0xCC0020u) )
                  {
                    SelectObject(v41, v40);
                    v40 = 0;
                    if ( (unsigned int)bMetaGetDIBInfo(v41, v39, &v63, &v47, &v46, 0, 0, 0) )
                    {
                      *(_QWORD *)(v19 + 768) = hdc;
                      switch ( a16 )
                      {
                        case 'L':
                          v42 = MF_DoBitBlt(
                                  (struct MDC *)v19,
                                  v50,
                                  v49,
                                  v48,
                                  a5,
                                  a15,
                                  a8,
                                  a9,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
                          goto LABEL_55;
                        case 'M':
                          v42 = MF_DoStretchBlt(
                                  (struct MDC *)v19,
                                  v50,
                                  v49,
                                  v48,
                                  a5,
                                  a15,
                                  a8,
                                  a9,
                                  a10,
                                  a11,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
LABEL_55:
                          v37 = v42;
                          break;
                        case 'N':
                          v42 = MF_DoMaskBlt(
                                  (MDC *)v19,
                                  a5,
                                  a15,
                                  v54,
                                  v57,
                                  v52,
                                  v51,
                                  a13,
                                  a14,
                                  a8,
                                  a9,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
                          goto LABEL_55;
                        case 'O':
                          v42 = MF_DoPlgBlt(
                                  (MDC *)v19,
                                  a6,
                                  v54,
                                  v57,
                                  v52,
                                  v51,
                                  a13,
                                  a14,
                                  a8,
                                  a9,
                                  a10,
                                  a11,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
                          goto LABEL_55;
                        case 'r':
                          v42 = MF_DoAlphaBlend(
                                  (struct MDC *)v19,
                                  v50,
                                  v49,
                                  v48,
                                  a5,
                                  a15,
                                  a8,
                                  a9,
                                  a10,
                                  a11,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
                          goto LABEL_55;
                        case 't':
                          v42 = MF_DoTransparentBlt(
                                  (struct MDC *)v19,
                                  v50,
                                  v49,
                                  v48,
                                  a5,
                                  a15,
                                  a8,
                                  a9,
                                  a10,
                                  a11,
                                  &v62,
                                  NearestColor,
                                  &v63,
                                  v39,
                                  v47,
                                  v46);
                          goto LABEL_55;
                      }
                    }
                  }
                }
              }
            }
          }
          RestoreDC(hdc, -1);
          if ( !v40 )
            goto LABEL_57;
          goto LABEL_81;
        }
      }
      return 0;
    }
    v43 = pldcGet(hdc);
    if ( v43 && ((unsigned int)hdc & 0x7F0000) != 0x660000 )
    {
      if ( *(_DWORD *)(v43 + 12) == 2 )
        return 0;
      goto LABEL_23;
    }
LABEL_20:
    GdiSetLastError(6);
    return 0;
  }
  if ( a16 == 76 || a16 == 77 )
  {
    v23 = (MRBB *)MDC::pvNewRecord((MDC *)v19, 0x64u);
    if ( v23
      && MRBB::bInit(v23, 0x4Cu, (struct MDC *)v19, v50, v49, v48, a5, a15, 0, 0, &xformIdentity, 0, 0, 0, 0, 0, 0, 0) )
    {
      *(_DWORD *)(v19 + 32) |= 4u;
    }
    else
    {
      return 0;
    }
    return v20;
  }
  if ( a16 != 78 )
    return 0;
  return MF_DoMaskBlt((MDC *)v19, a5, a15, v54, v57, v52, v51, a13, a14, a8, a9, &v62, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180020a00  push    rbp
0x180020a02  push    rbx
0x180020a03  push    rsi
0x180020a04  push    rdi
0x180020a05  push    r12
0x180020a07  push    r13
0x180020a09  push    r14
0x180020a0b  push    r15
0x180020a0d  lea     rbp, [rsp-68h]
0x180020a12  sub     rsp, 188h
0x180020a19  mov     rax, cs:__security_cookie
0x180020a20  xor     rax, rsp
0x180020a23  mov     [rbp+0A0h+var_48], rax
0x180020a27  mov     r14, [rbp+0A0h+arg_58]
0x180020a2e  xorps   xmm0, xmm0
0x180020a31  mov     rdi, [rbp+0A0h+hdc]
0x180020a38  xor     eax, eax
0x180020a3a  mov     [rbp+0A0h+var_E8], r14
0x180020a3e  mov     rbx, rcx
0x180020a41  movups  [rbp+0A0h+var_70], xmm0
0x180020a45  mov     [rbp+0A0h+var_50], rax
0x180020a49  movups  [rbp+0A0h+var_60], xmm0
0x180020a4d  mov     qword ptr [rbp+0A0h+var_B0.eDx], rax
0x180020a51  movups  xmmword ptr [rbp+0A0h+var_B0.eM11], xmm0
0x180020a55  mov     [rbp+0A0h+var_114], r9d
0x180020a59  mov     [rbp+0A0h+var_110], r8d
0x180020a5d  mov     [rbp+0A0h+var_10C], edx
0x180020a60  mov     [rbp+0A0h+var_100], rcx
0x180020a64  mov     [rbp+0A0h+var_104], 0
0x180020a6b  mov     [rbp+0A0h+var_108], 0
0x180020a72  call    cs:__imp_pldcGet
0x180020a78  xor     edx, edx
0x180020a7a  mov     r13, rax
0x180020a7d  test    rax, rax
0x180020a80  jz      loc_180020C28
0x180020a86  mov     ecx, ebx
0x180020a88  and     ecx, 7F0000h
0x180020a8e  cmp     ecx, 660000h
0x180020a94  jz      loc_180020C28
0x180020a9a  mov     r15, [rax+10h]
0x180020a9e  lea     esi, [rdx+1]
0x180020aa1  mov     [rbp+0A0h+var_F8], rdx
0x180020aa5  test    r14, r14
0x180020aa8  jnz     loc_18002100B
0x180020aae  mov     ebx, [rbp+0A0h+arg_78]
0x180020ab4  mov     r14d, [rbp+0A0h+arg_70]
0x180020abb  lea     eax, [rbx-4Ch]
0x180020abe  cmp     eax, esi
0x180020ac0  ja      short loc_180020ACF
0x180020ac2  test    r14d, 7F000000h
0x180020ac9  jnz     loc_180020C33
0x180020acf  mov     eax, r14d
0x180020ad2  mov     r12d, r14d
0x180020ad5  and     eax, 0F3330000h
0x180020ada  and     r12d, 0CCCC0000h
0x180020ae1  shl     eax, 2
0x180020ae4  mov     [rbp+0A0h+var_120], eax
0x180020ae7  cmp     r12d, eax
0x180020aea  jnz     short loc_180020B04
0x180020aec  lea     eax, [rbx-4Eh]
0x180020aef  cmp     eax, 26h ; '&'
0x180020af2  ja      short loc_180020B5B
0x180020af4  mov     rcx, 5000000001h
0x180020afe  bt      rcx, rax
0x180020b02  jnb     short loc_180020B5B
0x180020b04  lea     r8, [rbp+0A0h+var_B0]
0x180020b08  mov     edx, 204h
0x180020b0d  mov     rcx, rdi
0x180020b10  call    cs:__imp_NtGdiGetTransform
0x180020b16  xor     edx, edx
0x180020b18  test    eax, eax
0x180020b1a  jz      loc_180020C33
0x180020b20  movss   xmm0, [rbp+0A0h+var_B0.eM12]
0x180020b25  xorps   xmm1, xmm1
0x180020b28  ucomiss xmm0, xmm1
0x180020b2b  jp      loc_180020C33
0x180020b31  jnz     loc_180020C33
0x180020b37  movss   xmm0, [rbp+0A0h+var_B0.eM21]
0x180020b3c  ucomiss xmm0, xmm1
0x180020b3f  jp      loc_180020C33
0x180020b45  jnz     loc_180020C33
0x180020b4b  bts     dword ptr [r13+8], 1Dh
0x180020b51  cmp     r12d, [rbp+0A0h+var_120]
0x180020b55  jnz     loc_180020C37
0x180020b5b  lea     eax, [rbx-72h]
0x180020b5e  test    eax, 0FFFFFFFDh
0x180020b63  jz      loc_180020C37
0x180020b69  sub     ebx, 4Ch ; 'L'
0x180020b6c  jz      short loc_180020B76
0x180020b6e  sub     ebx, esi
0x180020b70  jnz     loc_180021062
0x180020b76  mov     edx, 64h ; 'd'; unsigned int
0x180020b7b  mov     rcx, r15; this
0x180020b7e  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x180020b83  xor     ebx, ebx
0x180020b85  mov     rcx, rax; this
0x180020b88  test    rax, rax
0x180020b8b  jz      loc_180020FD6
0x180020b91  mov     r9d, [rbp+0A0h+var_114]
0x180020b95  lea     rax, ?xformIdentity@@3UtagXFORM@@A; tagXFORM xformIdentity
0x180020b9c  mov     r8d, [rbp+0A0h+var_110]
0x180020ba0  lea     edx, [rbx+4Ch]; unsigned int
0x180020ba3  mov     dword ptr [rsp+1C0h+var_138], ebx; unsigned int
0x180020baa  mov     dword ptr [rsp+1C0h+var_140], ebx; unsigned int
0x180020bb1  mov     dword ptr [rsp+1C0h+var_148], ebx; unsigned int
0x180020bb5  mov     dword ptr [rsp+1C0h+var_150], ebx; unsigned int
0x180020bb9  mov     [rsp+1C0h+var_158], rbx; void *
0x180020bbe  mov     [rsp+1C0h+var_160], rbx; struct tagBITMAPINFOHEADER *
0x180020bc3  mov     dword ptr [rsp+1C0h+var_168], ebx; unsigned int
0x180020bc7  mov     [rsp+1C0h+var_170], rax; struct tagXFORM *
0x180020bcc  mov     eax, [rbp+0A0h+arg_20]
0x180020bd2  mov     [rsp+1C0h+var_178], ebx; int
0x180020bd6  mov     [rsp+1C0h+rop], ebx; int
0x180020bda  mov     [rsp+1C0h+y1], r14d; unsigned int
0x180020bdf  mov     [rsp+1C0h+x1], eax; int
0x180020be3  mov     dword ptr [rsp+1C0h+hdcSrc], r9d; int
0x180020be8  mov     r9d, [rbp+0A0h+var_10C]; int
0x180020bec  mov     [rsp+1C0h+cy], r8d; int
0x180020bf1  mov     r8, r15; struct MDC *
0x180020bf4  call    ?bInit@MRBB@@QEAAHKPEAVMDC@@JJJJKJJPEAUtagXFORM@@KPEAUtagBITMAPINFOHEADER@@PEAXKKKK@Z; MRBB::bInit(ulong,MDC *,long,long,long,long,ulong,long,long,tagXFORM *,ulong,tagBITMAPINFOHEADER *,void *,ulong,ulong,ulong,ulong)
0x180020bf9  test    eax, eax
0x180020bfb  jz      loc_180020FD6
0x180020c01  or      dword ptr [r15+20h], 4
0x180020c06  mov     eax, esi
0x180020c08  mov     rcx, [rbp+0A0h+var_48]
0x180020c0c  xor     rcx, rsp; StackCookie
0x180020c0f  call    __security_check_cookie
0x180020c14  add     rsp, 188h
0x180020c1b  pop     r15
0x180020c1d  pop     r14
0x180020c1f  pop     r13
0x180020c21  pop     r12
0x180020c23  pop     rdi
0x180020c24  pop     rsi
0x180020c25  pop     rbx
0x180020c26  pop     rbp
0x180020c27  retn
0x180020c28  mov     ecx, 6
0x180020c2d  call    cs:__imp_GdiSetLastError
0x180020c33  xor     eax, eax
0x180020c35  jmp     short loc_180020C08
0x180020c37  mov     eax, edi
0x180020c39  and     eax, 7F0000h
0x180020c3e  mov     r14d, eax
0x180020c41  cmp     eax, 10000h
0x180020c46  jnz     loc_180020FDD
0x180020c4c  mov     rcx, rdi; hdc
0x180020c4f  call    GetBkColor
0x180020c54  mov     edx, eax
0x180020c56  mov     rcx, rdi
0x180020c59  call    cs:__imp_NtGdiGetNearestColor
0x180020c5f  mov     [rbp+0A0h+var_120], eax
0x180020c62  cmp     eax, 0FFFFFFFFh
0x180020c65  jz      short loc_180020C33
0x180020c67  mov     ecx, [rbp+0A0h+arg_40]
0x180020c6d  lea     rdx, [rbp+0A0h+pt]; lppt
0x180020c71  xor     eax, eax
0x180020c73  mov     [rbp+0A0h+pt.y], ecx
0x180020c76  mov     qword ptr [rbp+0A0h+var_98.biClrUsed], rax
0x180020c7a  xorps   xmm0, xmm0
0x180020c7d  mov     eax, [rbp+0A0h+arg_38]
0x180020c83  mov     r8d, 2; c
0x180020c89  mov     [rbp+0A0h+pt.x], eax
0x180020c8c  add     eax, [rbp+0A0h+arg_48]
0x180020c92  mov     [rbp+0A0h+var_B8], eax
0x180020c95  mov     eax, [rbp+0A0h+arg_50]
0x180020c9b  add     eax, ecx
0x180020c9d  mov     [rbp+0A0h+var_118], 0
0x180020ca4  mov     rcx, rdi; hdc
0x180020ca7  mov     [rbp+0A0h+var_B4], eax
0x180020caa  mov     [rbp+0A0h+var_11C], 0
0x180020cb1  movups  xmmword ptr [rbp+0A0h+var_98.biSize], xmm0
0x180020cb5  movups  xmmword ptr [rbp+0A0h+var_98.biCompression], xmm0
0x180020cb9  call    LPtoDP
0x180020cbe  test    eax, eax
0x180020cc0  jz      loc_180020C33
0x180020cc6  mov     ecx, [rbp+0A0h+pt.x]
0x180020cc9  mov     r12d, [rbp+0A0h+var_B8]
0x180020ccd  cmp     ecx, r12d
0x180020cd0  jg      loc_180021104
0x180020cd6  mov     edx, [rbp+0A0h+pt.y]
0x180020cd9  mov     r14d, [rbp+0A0h+var_B4]
0x180020cdd  cmp     edx, r14d
0x180020ce0  jg      loc_180021111
0x180020ce6  movss   xmm1, [rbp+0A0h+var_B0.eDx]
0x180020ceb  sub     ecx, esi
0x180020ced  movss   xmm2, [rbp+0A0h+var_B0.eDy]
0x180020cf2  sub     edx, esi
0x180020cf4  add     r12d, esi
0x180020cf7  mov     [rbp+0A0h+pt.x], ecx
0x180020cfa  add     r14d, esi
0x180020cfd  mov     [rbp+0A0h+var_B8], r12d
0x180020d01  movd    xmm0, ecx
0x180020d05  sub     r12d, ecx
0x180020d08  cvtdq2ps xmm0, xmm0
0x180020d0b  mov     [rbp+0A0h+var_B4], r14d
0x180020d0f  mov     rcx, rdi
0x180020d12  mov     [rbp+0A0h+pt.y], edx
0x180020d15  sub     r14d, edx
0x180020d18  subss   xmm1, xmm0
0x180020d1c  movd    xmm0, edx
0x180020d20  cvtdq2ps xmm0, xmm0
0x180020d23  mov     edx, 50000h
0x180020d28  movss   [rbp+0A0h+var_B0.eDx], xmm1
0x180020d2d  subss   xmm2, xmm0
0x180020d31  movss   [rbp+0A0h+var_B0.eDy], xmm2
0x180020d36  call    GetDCObject
0x180020d3b  xorps   xmm0, xmm0
0x180020d3e  movups  [rbp+0A0h+pv], xmm0
0x180020d42  movups  [rbp+0A0h+var_D0], xmm0
0x180020d46  test    rax, rax
0x180020d49  jz      short loc_180020D64
0x180020d4b  lea     r8, [rbp+0A0h+pv]; pv
0x180020d4f  mov     edx, 20h ; ' '; c
0x180020d54  mov     rcx, rax; h
0x180020d57  call    GetObjectA
0x180020d5c  test    eax, eax
0x180020d5e  jnz     loc_18002111E
0x180020d64  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180020d68  mov     edx, 76h ; 'v'; index
0x180020d6d  call    cs:__imp_GetDeviceCaps
0x180020d73  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180020d77  mov     edx, 75h ; 'u'; index
0x180020d7c  mov     r13d, eax
0x180020d7f  call    cs:__imp_GetDeviceCaps
0x180020d85  mov     ecx, eax
0x180020d87  mov     eax, [rbp+0A0h+pt.x]
0x180020d8a  test    eax, eax
0x180020d8c  js      loc_18002112A
0x180020d92  cmp     [rbp+0A0h+var_B8], r13d
0x180020d96  jge     loc_18002114E
0x180020d9c  mov     eax, [rbp+0A0h+pt.y]
0x180020d9f  test    eax, eax
0x180020da1  js      loc_180021165
0x180020da7  cmp     [rbp+0A0h+var_B4], ecx
0x180020daa  jge     loc_180021189
0x180020db0  test    r12d, r12d
0x180020db3  js      loc_180020C06
0x180020db9  test    r14d, r14d
0x180020dbc  js      loc_180020C06
0x180020dc2  mov     rcx, rdi; hdc
0x180020dc5  xor     r13d, r13d
0x180020dc8  call    CreateCompatibleDC
0x180020dcd  mov     [rbp+0A0h+var_100], rax
0x180020dd1  test    rax, rax
0x180020dd4  jz      loc_180020FCE
0x180020dda  lea     ecx, [r12+1]
0x180020ddf  lea     eax, [r14+1]
0x180020de3  mov     [rbp+0A0h+var_EC], ecx
0x180020de6  mov     edx, ecx; cx
0x180020de8  mov     [rbp+0A0h+var_F0], eax
0x180020deb  mov     rcx, rdi; hdc
0x180020dee  mov     r8d, eax; cy
0x180020df1  call    CreateCompatibleBitmap
0x180020df6  mov     r14, rax
0x180020df9  test    rax, rax
0x180020dfc  jz      loc_180020FC4
0x180020e02  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180020e06  mov     rdx, rax; h
0x180020e09  call    cs:__imp_SelectObject
0x180020e0f  mov     r12, rax
0x180020e12  test    rax, rax
0x180020e15  jz      loc_180020FBB
0x180020e1b  mov     rcx, rdi; hdc
0x180020e1e  call    cs:__imp_SaveDC
0x180020e24  test    eax, eax
0x180020e26  jz      loc_180021472
0x180020e2c  lea     edx, [r13+2]; iMode
0x180020e30  mov     rcx, rdi; hdc
0x180020e33  call    SetGraphicsMode
0x180020e38  mov     edx, esi; iMode
0x180020e3a  mov     rcx, rdi; hdc
0x180020e3d  call    SetMapMode
0x180020e42  test    eax, eax
0x180020e44  jz      loc_180020FA6
0x180020e4a  mov     r8d, esi; mode
0x180020e4d  xor     edx, edx; lpxf
0x180020e4f  mov     rcx, rdi; hdc
0x180020e52  call    ModifyWorldTransform
0x180020e57  test    eax, eax
0x180020e59  jz      loc_180020FA6
0x180020e5f  xor     r9d, r9d; lppt
0x180020e62  xor     r8d, r8d; y
0x180020e65  xor     edx, edx; x
0x180020e67  mov     rcx, rdi; hdc
0x180020e6a  call    SetWindowOrgEx
0x180020e6f  test    eax, eax
0x180020e71  jz      loc_180020FA6
0x180020e77  xor     r9d, r9d; lppt
0x180020e7a  xor     r8d, r8d; y
0x180020e7d  xor     edx, edx; x
0x180020e7f  mov     rcx, rdi; hdc
0x180020e82  call    SetViewportOrgEx
0x180020e87  test    eax, eax
0x180020e89  jz      loc_180020FA6
0x180020e8f  mov     eax, [rbp+0A0h+pt.y]
0x180020e92  xor     r8d, r8d; y
0x180020e95  mov     rsi, [rbp+0A0h+var_100]
0x180020e99  xor     edx, edx; x
0x180020e9b  mov     r9d, [rbp+0A0h+var_EC]; cx
  ... truncated ...
```
