# MF_AnyBitBlt

- ea: `0x180029730`
- end: `0x18002a209`
- name: `MF_AnyBitBlt`
- size: `2777`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct tagPOINT *, HDC hdc, int, int, int, int, __int64, int, int, unsigned int, int)`
- caller_count: `7`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180028bd0`
- `0x18002a660`
- `0x180036560`
- `0x18006cab0`
- `0x180073fe0`
- `0x18007a830`
- `0x180099250`

## callees

- `0x180004c00`
- `0x180006a28`
- `0x180018720`
- `0x180018a20`
- `0x180018c30`
- `0x1800200a0`
- `0x180028260`
- `0x18002841c`
- `0x180028974`
- `0x180028dd0`
- `0x180028e90`
- `0x180029730`
- `0x18002a210`
- `0x18002a3d8`
- `0x18002a660`
- `0x18002c048`
- `0x180032f20`
- `0x180057410`
- `0x18007f800`
- `0x180091bb4`
- `0x180091cdc`
- `0x180091f00`
- `0x180092094`

## import_xrefs

- `GDI32!DeleteDC` at `0x180029d3b`
- `GDI32!DeleteDC` at `0x180029d3b`
- `GDI32!GetDeviceCaps` at `0x180029ab6`
- `GDI32!GetDeviceCaps` at `0x180029ace`
- `GDI32!GetDeviceCaps` at `0x180029ab6`
- `GDI32!GetDeviceCaps` at `0x180029ace`
- `GDI32!RestoreDC` at `0x180029d13`
- `GDI32!RestoreDC` at `0x180029d13`
- `GDI32!SaveDC` at `0x180029b79`
- `GDI32!SaveDC` at `0x180029b79`
- `GDI32!SelectObject` at `0x180029b5e`
- `GDI32!SelectObject` at `0x180029c35`
- `GDI32!SelectObject` at `0x18002a1f8`
- `GDI32!SelectObject` at `0x180029b5e`
- `GDI32!SelectObject` at `0x180029c35`
- `GDI32!SelectObject` at `0x18002a1f8`
- `GDI32!pldcGet` at `0x1800297a2`
- `GDI32!pldcGet` at `0x180029d59`
- `GDI32!pldcGet` at `0x1800297a2`
- `GDI32!pldcGet` at `0x180029d59`
- `GDI32!GdiSetLastError` at `0x18002996a`
- `GDI32!GdiSetLastError` at `0x18002996a`
- `GDI32!DeleteObject` at `0x180029d2b`
- `GDI32!DeleteObject` at `0x180029d2b`
- `win32u!NtGdiGetNearestColor` at `0x18002999c`
- `win32u!NtGdiGetNearestColor` at `0x18002999c`
- `win32u!NtGdiGetTransform` at `0x180029846`
- `win32u!NtGdiGetTransform` at `0x180029846`

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
0x180029730  push    rbp
0x180029732  push    rbx
0x180029733  push    rsi
0x180029734  push    rdi
0x180029735  push    r12
0x180029737  push    r13
0x180029739  push    r14
0x18002973b  push    r15
0x18002973d  lea     rbp, [rsp-68h]
0x180029742  sub     rsp, 188h
0x180029749  mov     rax, cs:__security_cookie
0x180029750  xor     rax, rsp
0x180029753  mov     [rbp+0A0h+var_48], rax
0x180029757  mov     r14, [rbp+0A0h+arg_58]
0x18002975e  xorps   xmm0, xmm0
0x180029761  mov     rdi, [rbp+0A0h+hdc]
0x180029768  xor     eax, eax
0x18002976a  mov     [rbp+0A0h+var_E8], r14
0x18002976e  mov     rbx, rcx
0x180029771  movups  [rbp+0A0h+var_70], xmm0
0x180029775  mov     [rbp+0A0h+var_50], rax
0x180029779  movups  [rbp+0A0h+var_60], xmm0
0x18002977d  mov     qword ptr [rbp+0A0h+var_B0.eDx], rax
0x180029781  movups  xmmword ptr [rbp+0A0h+var_B0.eM11], xmm0
0x180029785  mov     [rbp+0A0h+var_114], r9d
0x180029789  mov     [rbp+0A0h+var_110], r8d
0x18002978d  mov     [rbp+0A0h+var_10C], edx
0x180029790  mov     [rbp+0A0h+var_100], rcx
0x180029794  mov     [rbp+0A0h+var_104], 0
0x18002979b  mov     [rbp+0A0h+var_108], 0
0x1800297a2  call    cs:__imp_pldcGet
0x1800297a9  nop     dword ptr [rax+rax+00h]
0x1800297ae  xor     edx, edx
0x1800297b0  mov     r13, rax
0x1800297b3  test    rax, rax
0x1800297b6  jz      loc_180029965
0x1800297bc  mov     ecx, ebx
0x1800297be  and     ecx, 7F0000h
0x1800297c4  cmp     ecx, 660000h
0x1800297ca  jz      loc_180029965
0x1800297d0  mov     r15, [rax+10h]
0x1800297d4  lea     esi, [rdx+1]
0x1800297d7  mov     [rbp+0A0h+var_F8], rdx
0x1800297db  test    r14, r14
0x1800297de  jnz     loc_180029D8A
0x1800297e4  mov     ebx, [rbp+0A0h+arg_78]
0x1800297ea  mov     r14d, [rbp+0A0h+arg_70]
0x1800297f1  lea     eax, [rbx-4Ch]
0x1800297f4  cmp     eax, esi
0x1800297f6  ja      short loc_180029805
0x1800297f8  test    r14d, 7F000000h
0x1800297ff  jnz     loc_180029976
0x180029805  mov     eax, r14d
0x180029808  mov     r12d, r14d
0x18002980b  and     eax, 0F3330000h
0x180029810  and     r12d, 0CCCC0000h
0x180029817  shl     eax, 2
0x18002981a  mov     [rbp+0A0h+var_120], eax
0x18002981d  cmp     r12d, eax
0x180029820  jnz     short loc_18002983A
0x180029822  lea     eax, [rbx-4Eh]
0x180029825  cmp     eax, 26h ; '&'
0x180029828  ja      short loc_180029897
0x18002982a  mov     rcx, 5000000001h
0x180029834  bt      rcx, rax
0x180029838  jnb     short loc_180029897
0x18002983a  lea     r8, [rbp+0A0h+var_B0]
0x18002983e  mov     edx, 204h
0x180029843  mov     rcx, rdi
0x180029846  call    cs:__imp_NtGdiGetTransform
0x18002984d  nop     dword ptr [rax+rax+00h]
0x180029852  xor     edx, edx
0x180029854  test    eax, eax
0x180029856  jz      loc_180029976
0x18002985c  movss   xmm0, [rbp+0A0h+var_B0.eM12]
0x180029861  xorps   xmm1, xmm1
0x180029864  ucomiss xmm0, xmm1
0x180029867  jp      loc_180029976
0x18002986d  jnz     loc_180029976
0x180029873  movss   xmm0, [rbp+0A0h+var_B0.eM21]
0x180029878  ucomiss xmm0, xmm1
0x18002987b  jp      loc_180029976
0x180029881  jnz     loc_180029976
0x180029887  bts     dword ptr [r13+8], 1Dh
0x18002988d  cmp     r12d, [rbp+0A0h+var_120]
0x180029891  jnz     loc_18002997A
0x180029897  lea     eax, [rbx-72h]
0x18002989a  test    eax, 0FFFFFFFDh
0x18002989f  jz      loc_18002997A
0x1800298a5  sub     ebx, 4Ch ; 'L'
0x1800298a8  jz      short loc_1800298B2
0x1800298aa  sub     ebx, esi
0x1800298ac  jnz     loc_180029DE1
0x1800298b2  mov     edx, 64h ; 'd'; unsigned int
0x1800298b7  mov     rcx, r15; this
0x1800298ba  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x1800298bf  xor     ebx, ebx
0x1800298c1  mov     rcx, rax; this
0x1800298c4  test    rax, rax
0x1800298c7  jz      loc_180029D4F
0x1800298cd  mov     r9d, [rbp+0A0h+var_114]
0x1800298d1  lea     rax, ?xformIdentity@@3UtagXFORM@@A; tagXFORM xformIdentity
0x1800298d8  mov     r8d, [rbp+0A0h+var_110]
0x1800298dc  lea     edx, [rbx+4Ch]; unsigned int
0x1800298df  mov     dword ptr [rsp+1C0h+var_138], ebx; unsigned int
0x1800298e6  mov     dword ptr [rsp+1C0h+var_140], ebx; unsigned int
0x1800298ed  mov     dword ptr [rsp+1C0h+var_148], ebx; unsigned int
0x1800298f1  mov     dword ptr [rsp+1C0h+var_150], ebx; unsigned int
0x1800298f5  mov     [rsp+1C0h+var_158], rbx; void *
0x1800298fa  mov     [rsp+1C0h+var_160], rbx; struct tagBITMAPINFOHEADER *
0x1800298ff  mov     dword ptr [rsp+1C0h+var_168], ebx; unsigned int
0x180029903  mov     [rsp+1C0h+var_170], rax; struct tagXFORM *
0x180029908  mov     eax, [rbp+0A0h+arg_20]
0x18002990e  mov     [rsp+1C0h+var_178], ebx; int
0x180029912  mov     [rsp+1C0h+rop], ebx; int
0x180029916  mov     [rsp+1C0h+y1], r14d; unsigned int
0x18002991b  mov     [rsp+1C0h+x1], eax; int
0x18002991f  mov     dword ptr [rsp+1C0h+hdcSrc], r9d; int
0x180029924  mov     r9d, [rbp+0A0h+var_10C]; int
0x180029928  mov     [rsp+1C0h+cy], r8d; int
0x18002992d  mov     r8, r15; struct MDC *
0x180029930  call    ?bInit@MRBB@@QEAAHKPEAVMDC@@JJJJKJJPEAUtagXFORM@@KPEAUtagBITMAPINFOHEADER@@PEAXKKKK@Z; MRBB::bInit(ulong,MDC *,long,long,long,long,ulong,long,long,tagXFORM *,ulong,tagBITMAPINFOHEADER *,void *,ulong,ulong,ulong,ulong)
0x180029935  test    eax, eax
0x180029937  jz      loc_180029D4F
0x18002993d  or      dword ptr [r15+20h], 4
0x180029942  mov     eax, esi
0x180029944  mov     rcx, [rbp+0A0h+var_48]
0x180029948  xor     rcx, rsp; StackCookie
0x18002994b  call    __security_check_cookie
0x180029950  add     rsp, 188h
0x180029957  pop     r15
0x180029959  pop     r14
0x18002995b  pop     r13
0x18002995d  pop     r12
0x18002995f  pop     rdi
0x180029960  pop     rsi
0x180029961  pop     rbx
0x180029962  pop     rbp
0x180029963  retn
0x180029965  mov     ecx, 6
0x18002996a  call    cs:__imp_GdiSetLastError
0x180029971  nop     dword ptr [rax+rax+00h]
0x180029976  xor     eax, eax
0x180029978  jmp     short loc_180029944
0x18002997a  mov     eax, edi
0x18002997c  and     eax, 7F0000h
0x180029981  mov     r14d, eax
0x180029984  cmp     eax, 10000h
0x180029989  jnz     loc_180029D56
0x18002998f  mov     rcx, rdi; hdc
0x180029992  call    GetBkColor
0x180029997  mov     edx, eax
0x180029999  mov     rcx, rdi
0x18002999c  call    cs:__imp_NtGdiGetNearestColor
0x1800299a3  nop     dword ptr [rax+rax+00h]
0x1800299a8  mov     [rbp+0A0h+var_120], eax
0x1800299ab  cmp     eax, 0FFFFFFFFh
0x1800299ae  jz      short loc_180029976
0x1800299b0  mov     ecx, [rbp+0A0h+arg_40]
0x1800299b6  lea     rdx, [rbp+0A0h+pt]; lppt
0x1800299ba  xor     eax, eax
0x1800299bc  mov     [rbp+0A0h+pt.y], ecx
0x1800299bf  mov     qword ptr [rbp+0A0h+var_98.biClrUsed], rax
0x1800299c3  xorps   xmm0, xmm0
0x1800299c6  mov     eax, [rbp+0A0h+arg_38]
0x1800299cc  mov     r8d, 2; c
0x1800299d2  mov     [rbp+0A0h+pt.x], eax
0x1800299d5  add     eax, [rbp+0A0h+arg_48]
0x1800299db  mov     [rbp+0A0h+var_B8], eax
0x1800299de  mov     eax, [rbp+0A0h+arg_50]
0x1800299e4  add     eax, ecx
0x1800299e6  mov     [rbp+0A0h+var_118], 0
0x1800299ed  mov     rcx, rdi; hdc
0x1800299f0  mov     [rbp+0A0h+var_B4], eax
0x1800299f3  mov     [rbp+0A0h+var_11C], 0
0x1800299fa  movups  xmmword ptr [rbp+0A0h+var_98.biSize], xmm0
0x1800299fe  movups  xmmword ptr [rbp+0A0h+var_98.biCompression], xmm0
0x180029a02  call    LPtoDP
0x180029a07  test    eax, eax
0x180029a09  jz      loc_180029976
0x180029a0f  mov     ecx, [rbp+0A0h+pt.x]
0x180029a12  mov     r12d, [rbp+0A0h+var_B8]
0x180029a16  cmp     ecx, r12d
0x180029a19  jg      loc_180029E83
0x180029a1f  mov     edx, [rbp+0A0h+pt.y]
0x180029a22  mov     r14d, [rbp+0A0h+var_B4]
0x180029a26  cmp     edx, r14d
0x180029a29  jg      loc_180029E90
0x180029a2f  movss   xmm1, [rbp+0A0h+var_B0.eDx]
0x180029a34  sub     ecx, esi
0x180029a36  movss   xmm2, [rbp+0A0h+var_B0.eDy]
0x180029a3b  sub     edx, esi
0x180029a3d  add     r12d, esi
0x180029a40  mov     [rbp+0A0h+pt.x], ecx
0x180029a43  add     r14d, esi
0x180029a46  mov     [rbp+0A0h+var_B8], r12d
0x180029a4a  movd    xmm0, ecx
0x180029a4e  sub     r12d, ecx
0x180029a51  cvtdq2ps xmm0, xmm0
0x180029a54  mov     [rbp+0A0h+var_B4], r14d
0x180029a58  mov     rcx, rdi
0x180029a5b  mov     [rbp+0A0h+pt.y], edx
0x180029a5e  sub     r14d, edx
0x180029a61  subss   xmm1, xmm0
0x180029a65  movd    xmm0, edx
0x180029a69  cvtdq2ps xmm0, xmm0
0x180029a6c  mov     edx, 50000h
0x180029a71  movss   [rbp+0A0h+var_B0.eDx], xmm1
0x180029a76  subss   xmm2, xmm0
0x180029a7a  movss   [rbp+0A0h+var_B0.eDy], xmm2
0x180029a7f  call    GetDCObject
0x180029a84  xorps   xmm0, xmm0
0x180029a87  movups  [rbp+0A0h+pv], xmm0
0x180029a8b  movups  [rbp+0A0h+var_D0], xmm0
0x180029a8f  test    rax, rax
0x180029a92  jz      short loc_180029AAD
0x180029a94  lea     r8, [rbp+0A0h+pv]; pv
0x180029a98  mov     edx, 20h ; ' '; c
0x180029a9d  mov     rcx, rax; h
0x180029aa0  call    GetObjectA
0x180029aa5  test    eax, eax
0x180029aa7  jnz     loc_180029E9D
0x180029aad  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180029ab1  mov     edx, 76h ; 'v'; index
0x180029ab6  call    cs:__imp_GetDeviceCaps
0x180029abd  nop     dword ptr [rax+rax+00h]
0x180029ac2  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180029ac6  mov     edx, 75h ; 'u'; index
0x180029acb  mov     r13d, eax
0x180029ace  call    cs:__imp_GetDeviceCaps
0x180029ad5  nop     dword ptr [rax+rax+00h]
0x180029ada  mov     ecx, eax
0x180029adc  mov     eax, [rbp+0A0h+pt.x]
0x180029adf  test    eax, eax
0x180029ae1  js      loc_180029EA9
0x180029ae7  cmp     [rbp+0A0h+var_B8], r13d
0x180029aeb  jge     loc_180029ECD
0x180029af1  mov     eax, [rbp+0A0h+pt.y]
0x180029af4  test    eax, eax
0x180029af6  js      loc_180029EE4
0x180029afc  cmp     [rbp+0A0h+var_B4], ecx
0x180029aff  jge     loc_180029F08
0x180029b05  test    r12d, r12d
0x180029b08  js      loc_180029942
0x180029b0e  test    r14d, r14d
0x180029b11  js      loc_180029942
0x180029b17  mov     rcx, rdi; hdc
0x180029b1a  xor     r13d, r13d
0x180029b1d  call    CreateCompatibleDC
0x180029b22  mov     [rbp+0A0h+var_100], rax
0x180029b26  test    rax, rax
0x180029b29  jz      loc_180029D47
0x180029b2f  lea     ecx, [r12+1]
0x180029b34  lea     eax, [r14+1]
0x180029b38  mov     [rbp+0A0h+var_EC], ecx
0x180029b3b  mov     edx, ecx; cx
0x180029b3d  mov     [rbp+0A0h+var_F0], eax
0x180029b40  mov     rcx, rdi; hdc
0x180029b43  mov     r8d, eax; cy
0x180029b46  call    CreateCompatibleBitmap
0x180029b4b  mov     r14, rax
0x180029b4e  test    rax, rax
0x180029b51  jz      loc_180029D37
0x180029b57  mov     rcx, [rbp+0A0h+var_100]; hdc
0x180029b5b  mov     rdx, rax; h
0x180029b5e  call    cs:__imp_SelectObject
0x180029b65  nop     dword ptr [rax+rax+00h]
0x180029b6a  mov     r12, rax
0x180029b6d  test    rax, rax
0x180029b70  jz      loc_180029D28
0x180029b76  mov     rcx, rdi; hdc
0x180029b79  call    cs:__imp_SaveDC
0x180029b80  nop     dword ptr [rax+rax+00h]
0x180029b85  test    eax, eax
0x180029b87  jz      loc_18002A1F1
0x180029b8d  lea     edx, [r13+2]; iMode
0x180029b91  mov     rcx, rdi; hdc
0x180029b94  call    SetGraphicsMode
0x180029b99  mov     edx, esi; iMode
0x180029b9b  mov     rcx, rdi; hdc
0x180029b9e  call    SetMapMode
0x180029ba3  test    eax, eax
0x180029ba5  jz      loc_180029D0D
0x180029bab  mov     r8d, esi; mode
0x180029bae  xor     edx, edx; lpxf
0x180029bb0  mov     rcx, rdi; hdc
0x180029bb3  call    ModifyWorldTransform
0x180029bb8  test    eax, eax
0x180029bba  jz      loc_180029D0D
0x180029bc0  xor     r9d, r9d; lppt
0x180029bc3  xor     r8d, r8d; y
0x180029bc6  xor     edx, edx; x
0x180029bc8  mov     rcx, rdi; hdc
0x180029bcb  call    SetWindowOrgEx
0x180029bd0  test    eax, eax
0x180029bd2  jz      loc_180029D0D
0x180029bd8  xor     r9d, r9d; lppt
0x180029bdb  xor     r8d, r8d; y
0x180029bde  xor     edx, edx; x
0x180029be0  mov     rcx, rdi; hdc
  ... truncated ...
```
