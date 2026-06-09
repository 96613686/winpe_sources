# XHDC::AlphaBlend(int,int,int,int,XHDC const &,int,int,int,int,_BLENDFUNCTION)

- ea: `0x180b2ca78`
- end: `0x180b2d152`
- name: `?AlphaBlend@XHDC@@QEBAHHHHHAEBV1@HHHHU_BLENDFUNCTION@@@Z`
- size: `1754`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, const struct XHDC *, int, int, int, int cy, struct _BLENDFUNCTION)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180b2d2f8`
- `0x180b30374`

## callees

- `0x1801bf528`
- `0x1801c0b08`
- `0x18043c328`
- `0x180b2ca78`
- `0x180b2ef94`
- `0x180b2f394`
- `0x180b2f524`
- `0x180b2f5fc`
- `0x180b2f6ac`
- `0x180b32a60`
- `0x180b32bd0`
- `0x180b48564`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180b2cc04`
- `KERNEL32!GetLastError` at `0x180b2cd32`
- `KERNEL32!GetLastError` at `0x180b2d0ce`
- `KERNEL32!GetLastError` at `0x180b2cc04`
- `KERNEL32!GetLastError` at `0x180b2cd32`
- `KERNEL32!GetLastError` at `0x180b2d0ce`
- `GDI32!DeleteDC` at `0x180b2d0bf`
- `GDI32!DeleteDC` at `0x180b2d0bf`
- `GDI32!SetDIBits` at `0x180b2cfd1`
- `GDI32!SetDIBits` at `0x180b2cfd1`
- `GDI32!DeleteObject` at `0x180b2d0a3`
- `GDI32!DeleteObject` at `0x180b2d0b1`
- `GDI32!DeleteObject` at `0x180b2d0a3`
- `GDI32!DeleteObject` at `0x180b2d0b1`
- `GDI32!SelectObject` at `0x180b2cdf8`
- `GDI32!SelectObject` at `0x180b2ce3d`
- `GDI32!SelectObject` at `0x180b2d095`
- `GDI32!SelectObject` at `0x180b2cdf8`
- `GDI32!SelectObject` at `0x180b2ce3d`
- `GDI32!SelectObject` at `0x180b2d095`
- `GDI32!BitBlt` at `0x180b2ce2c`
- `GDI32!BitBlt` at `0x180b2ce2c`
- `GDI32!CreateCompatibleBitmap` at `0x180b2cd94`
- `GDI32!CreateCompatibleBitmap` at `0x180b2cdb9`
- `GDI32!CreateCompatibleBitmap` at `0x180b2cd94`
- `GDI32!CreateCompatibleBitmap` at `0x180b2cdb9`
- `GDI32!CreateCompatibleDC` at `0x180b2cdc7`
- `GDI32!CreateCompatibleDC` at `0x180b2cdc7`
- `GDI32!GetObjectW` at `0x180b2ce58`
- `GDI32!GetObjectW` at `0x180b2ce68`
- `GDI32!GetObjectW` at `0x180b2ce58`
- `GDI32!GetObjectW` at `0x180b2ce68`

## pseudocode

```c
__int64 __fastcall XHDC::AlphaBlend(
        XHDC *this,
        int a2,
        int a3,
        unsigned int a4,
        int a5,
        const struct XHDC *a6,
        int a7,
        int a8,
        int a9,
        int cy,
        struct _BLENDFUNCTION a11)
{
  HDC hdcSrc; // r14
  const struct tagSIZE *OffsetOnly; // r15
  const struct tagSIZE *v15; // rbx
  LONG v16; // eax
  LONG v17; // ebx
  unsigned int v18; // r10d
  unsigned int v19; // edx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  HDC v22; // rdx
  __int64 result; // rax
  int v24; // r15d
  int y1; // r12d
  int v26; // ebx
  HDC v27; // rdx
  signed int SurfaceFromDC; // ebx
  int v29; // r8d
  int v30; // edx
  HDC CompatibleDC; // rsi
  HBITMAP v32; // r15
  HBITMAP v33; // r12
  char v34; // r14
  unsigned int v35; // r13d
  int v36; // r14d
  unsigned int v37; // r12d
  void *v38; // r8
  HDC v39; // rdx
  int x1; // [rsp+38h] [rbp-D0h]
  char v41; // [rsp+68h] [rbp-A0h]
  unsigned int TrivialRotationAngle; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v44; // [rsp+6Ch] [rbp-9Ch]
  LONG ha; // [rsp+70h] [rbp-98h]
  int hb; // [rsp+70h] [rbp-98h]
  HBITMAP hc; // [rsp+70h] [rbp-98h]
  LONG v49; // [rsp+78h] [rbp-90h]
  int v50; // [rsp+78h] [rbp-90h]
  LONG cx; // [rsp+80h] [rbp-88h]
  int v52; // [rsp+80h] [rbp-88h]
  HBITMAP CompatibleBitmap; // [rsp+80h] [rbp-88h]
  int v54; // [rsp+88h] [rbp-80h] BYREF
  int v55; // [rsp+8Ch] [rbp-7Ch]
  unsigned int v56; // [rsp+90h] [rbp-78h]
  int v57; // [rsp+94h] [rbp-74h]
  HGDIOBJ v58; // [rsp+98h] [rbp-70h]
  struct IUnknown *v59; // [rsp+A0h] [rbp-68h] BYREF
  UINT cLines[4]; // [rsp+A8h] [rbp-60h] BYREF
  void *lpBits[2]; // [rsp+B8h] [rbp-50h]
  __int128 pv; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v63; // [rsp+D8h] [rbp-30h]
  int v64; // [rsp+E8h] [rbp-20h] BYREF
  char v65[36]; // [rsp+ECh] [rbp-1Ch] BYREF
  __int64 v66; // [rsp+110h] [rbp+8h]
  BITMAPINFO bmi; // [rsp+168h] [rbp+60h] BYREF

  hdcSrc = (HDC)*((_QWORD *)a6 + 4);
  LODWORD(v58) = a2;
  OffsetOnly = XHDC::GetOffsetOnly(this);
  v59 = 0;
  pv = 0;
  v15 = XHDC::GetOffsetOnly(a6);
  v63 = 0;
  *(_OWORD *)cLines = 0;
  *(_OWORD *)lpBits = 0;
  if ( !XHDC::s_pAlphaBlendProc && !(unsigned int)XHDC::LoadAlphaBlendProc() )
    return 0;
  if ( v15 )
  {
    if ( OffsetOnly )
    {
      cx = OffsetOnly->cx;
      v49 = OffsetOnly->cy;
      v16 = v15->cx;
      v17 = v15->cy;
      ha = v16;
      if ( XHDC::ValidateImageDestArea(this, a4, a5) )
      {
        v18 = (_DWORD)v58 + cx;
        v19 = v49 + a3;
        v20 = *((_QWORD *)this + 4);
        x1 = a7 + ha;
        v50 = a7 + ha;
        v52 = v19;
        hb = v17 + a8;
        LODWORD(v58) = v18;
        v21 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))XHDC::s_pAlphaBlendProc)(
                v20,
                v18,
                v19,
                a4,
                a5,
                hdcSrc,
                x1,
                v17 + a8,
                a9,
                cy,
                a11);
        if ( !v21 && GetLastError() == 87 )
          return (unsigned int)XHDC::GDIPlusAlphaBlend(this, v22, (int)v58, v52, a4, a5, hdcSrc, v50, hb, a9, cy);
        return v21;
      }
      return 0;
    }
    v24 = v15->cx + a7;
    y1 = v15->cy + a8;
  }
  else
  {
    y1 = a8;
    v24 = a7;
  }
  v54 = (int)v58;
  v55 = a3;
  v57 = a3 + a5;
  v56 = (_DWORD)v58 + a4;
  if ( !(unsigned int)XHDC::TransformRect(this, (struct CRect *)&v54) )
    return 0;
  TrivialRotationAngle = XHDC::GetTrivialRotationAngle(this);
  if ( TrivialRotationAngle )
  {
    v58 = 0;
    v41 = 0;
    SurfaceFromDC = 0;
    hc = CreateCompatibleBitmap(hdcSrc, a9, cy);
    if ( TrivialRotationAngle == 180 )
    {
      v29 = cy;
      v30 = a9;
    }
    else
    {
      v29 = a9;
      v30 = cy;
    }
    CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, v30, v29);
    CompatibleDC = CreateCompatibleDC(hdcSrc);
    if ( !hc || !CompatibleBitmap || !CompatibleDC )
    {
      v32 = CompatibleBitmap;
      v33 = hc;
      goto LABEL_45;
    }
    v58 = SelectObject(CompatibleDC, hc);
    BitBlt(CompatibleDC, 0, 0, a9, cy, hdcSrc, v24, y1, 0xCC0020u);
    v32 = CompatibleBitmap;
    SelectObject(CompatibleDC, CompatibleBitmap);
    v33 = hc;
    GetObjectW(hc, 32, &pv);
    GetObjectW(CompatibleBitmap, 32, cLines);
    if ( !*((_QWORD *)&v63 + 1) )
    {
      if ( WORD1(v63) != 32 )
      {
LABEL_27:
        SurfaceFromDC = -2147467259;
LABEL_45:
        ReleaseInterface(v59);
        ReleaseInterface(0);
        if ( v41 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, lpBits[1], v38);
        if ( v58 )
          SelectObject(CompatibleDC, v58);
        if ( v33 )
          DeleteObject(v33);
        if ( v32 )
          DeleteObject(v32);
        if ( CompatibleDC )
          DeleteDC(CompatibleDC);
        return SurfaceFromDC >= 0;
      }
      memset_0(v65, 0, 0x74u);
      v64 = 120;
      SurfaceFromDC = CDirectDraw::GetSurfaceFromDC(hdcSrc, (struct IDirectDrawSurface **)&v59);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, __int64, _QWORD))v59->lpVtbl[8].AddRef)(
                        v59,
                        0,
                        &v64,
                        2048,
                        0);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
      *((_QWORD *)&v63 + 1) = v66;
    }
    if ( lpBits[1] )
    {
      v34 = 0;
    }
    else
    {
      if ( WORD1(lpBits[0]) != 32 )
        goto LABEL_27;
      lpBits[1] = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 4 * cLines[1] * cLines[2]);
      if ( !lpBits[1] )
      {
        SurfaceFromDC = -2147024882;
        goto LABEL_45;
      }
      v34 = 1;
      v41 = 1;
    }
    RotateBitmap(&pv, cLines, TrivialRotationAngle);
    if ( v59 )
    {
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v59->lpVtbl[10].Release)(v59, 0);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
    }
    if ( !v34
      || (bmi.bmiHeader.biWidth = cLines[1],
          *(_DWORD *)&bmi.bmiHeader.biPlanes = lpBits[0],
          bmi.bmiHeader.biSize = 40,
          bmi.bmiHeader.biHeight = cLines[2],
          memset(&bmi.bmiHeader.biCompression, 0, 28),
          SetDIBits(CompatibleDC, CompatibleBitmap, 0, cLines[2], lpBits[1], &bmi, 0)) )
    {
      SurfaceFromDC = -2147467259;
      v35 = v55;
      v36 = v57 - v55;
      v37 = v56 - v54;
      if ( XHDC::ValidateImageDestArea(this, v56 - v54, v57 - v55) )
      {
        if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))XHDC::s_pAlphaBlendProc)(
                             *((_QWORD *)this + 4),
                             (unsigned int)v54,
                             v35,
                             v37,
                             v36,
                             CompatibleDC,
                             0,
                             0,
                             cLines[1],
                             cLines[2],
                             a11) )
        {
          SurfaceFromDC = 0;
        }
        else if ( GetLastError() == 87 )
        {
          SurfaceFromDC = (unsigned int)XHDC::GDIPlusAlphaBlend(
                                          this,
                                          v39,
                                          v54,
                                          v35,
                                          v37,
                                          v36,
                                          CompatibleDC,
                                          0,
                                          0,
                                          cLines[1],
                                          cLines[2]) != 0
                        ? 0x80004005
                        : 0;
        }
      }
      v33 = hc;
      goto LABEL_45;
    }
    goto LABEL_27;
  }
  v26 = v57 - v55;
  v44 = v56 - v54;
  if ( !XHDC::ValidateImageDestArea(this, v56 - v54, v57 - v55) )
    return 0;
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))XHDC::s_pAlphaBlendProc)(
             *((_QWORD *)this + 4),
             (unsigned int)v54,
             (unsigned int)v55,
             v44,
             v26,
             hdcSrc,
             v24,
             y1,
             a9,
             cy,
             a11);
  if ( !(_DWORD)result )
  {
    if ( GetLastError() == 87 )
      return XHDC::GDIPlusAlphaBlend(this, v27, v54, v55, v44, v26, hdcSrc, v24, y1, a9, cy);
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180b2ca78  mov     rax, rsp
0x180b2ca7b  mov     [rax+20h], r9d
0x180b2ca7f  mov     [rax+18h], r8d
0x180b2ca83  mov     [rax+10h], edx
0x180b2ca86  mov     [rax+8], rcx
0x180b2ca8a  push    rbp
0x180b2ca8b  push    rbx
0x180b2ca8c  push    rsi
0x180b2ca8d  push    rdi
0x180b2ca8e  push    r12
0x180b2ca90  push    r13
0x180b2ca92  push    r14
0x180b2ca94  push    r15
0x180b2ca96  lea     rbp, [rax-0E8h]
0x180b2ca9d  sub     rsp, 1A8h
0x180b2caa4  mov     rax, cs:__security_cookie
0x180b2caab  xor     rax, rsp
0x180b2caae  mov     [rbp+0E0h+var_50], rax
0x180b2cab5  mov     eax, [rbp+0E0h+arg_8]
0x180b2cabb  mov     rbx, [rbp+0E0h+arg_28]
0x180b2cac2  mov     rdi, [rbp+0E0h+arg_0]
0x180b2cac9  mov     r12d, [rbp+0E0h+arg_18]
0x180b2cad0  mov     rcx, rdi; this
0x180b2cad3  mov     esi, [rbp+0E0h+cy]
0x180b2cad9  mov     r14, [rbx+20h]
0x180b2cadd  mov     r13d, [rbp+0E0h+arg_40]
0x180b2cae4  mov     dword ptr [rbp+0E0h+var_150], eax
0x180b2cae7  mov     eax, [rbp+0E0h+arg_10]
0x180b2caed  mov     [rsp+1E0h+var_180+4], eax
0x180b2caf1  mov     dword ptr [rsp+1E0h+h], r12d
0x180b2caf6  mov     [rsp+1E0h+var_170], esi
0x180b2cafa  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b2caff  mov     rcx, rbx; this
0x180b2cb02  mov     r15, rax
0x180b2cb05  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b2cb0a  cmp     cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA, 0; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b2cb12  xorps   xmm0, xmm0
0x180b2cb15  xorps   xmm1, xmm1
0x180b2cb18  mov     [rbp+0E0h+var_148], 0
0x180b2cb20  movups  [rbp+0E0h+pv], xmm0
0x180b2cb24  mov     rbx, rax
0x180b2cb27  movups  [rbp+0E0h+var_110], xmm0
0x180b2cb2b  movups  xmmword ptr [rbp+0E0h+cLines], xmm1
0x180b2cb2f  movups  xmmword ptr [rbp+0E0h+var_130], xmm1
0x180b2cb33  jnz     short loc_180B2CB42
0x180b2cb35  call    ?LoadAlphaBlendProc@XHDC@@CAHXZ; XHDC::LoadAlphaBlendProc(void)
0x180b2cb3a  test    eax, eax
0x180b2cb3c  jz      loc_180B2D12D
0x180b2cb42  test    rbx, rbx
0x180b2cb45  jz      loc_180B2CC68
0x180b2cb4b  test    r15, r15
0x180b2cb4e  jz      loc_180B2CC51
0x180b2cb54  mov     eax, [r15]
0x180b2cb57  mov     edx, r12d; int
0x180b2cb5a  mov     [rsp+78h], eax
0x180b2cb5e  mov     rcx, rdi; this
0x180b2cb61  mov     eax, [r15+4]
0x180b2cb65  mov     r15d, [rbp+0E0h+arg_20]
0x180b2cb6c  mov     r8d, r15d; int
0x180b2cb6f  mov     [rsp+1E0h+var_170], eax
0x180b2cb73  mov     eax, [rbx]
0x180b2cb75  mov     ebx, [rbx+4]
0x180b2cb78  mov     dword ptr [rsp+1E0h+h], eax
0x180b2cb7c  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b2cb81  test    al, al
0x180b2cb83  jz      loc_180B2D12D
0x180b2cb89  mov     r8d, dword ptr [rsp+1E0h+h]
0x180b2cb8e  mov     r9d, r12d
0x180b2cb91  add     r8d, [rbp+0E0h+arg_30]
0x180b2cb98  mov     r10d, [rsp+78h]
0x180b2cb9d  add     r10d, dword ptr [rbp+0E0h+var_150]
0x180b2cba1  mov     eax, [rbp+0E0h+arg_38]
0x180b2cba7  mov     ecx, dword ptr [rbp+0E0h+arg_50.BlendOp]
0x180b2cbad  add     eax, ebx
0x180b2cbaf  mov     edx, [rsp+1E0h+var_180+4]
0x180b2cbb3  add     edx, [rsp+1E0h+var_170]
0x180b2cbb7  mov     [rsp+50h], ecx
0x180b2cbbb  mov     rcx, [rdi+20h]
0x180b2cbbf  mov     [rsp+1E0h+var_198], esi
0x180b2cbc3  mov     [rsp+1E0h+rop], r13d
0x180b2cbc8  mov     [rsp+1E0h+y1], eax
0x180b2cbcc  mov     [rsp+1E0h+x1], r8d
0x180b2cbd1  mov     [rsp+1E0h+var_170], r8d
0x180b2cbd6  mov     r8d, edx
0x180b2cbd9  mov     [rsp+78h], edx
0x180b2cbdd  mov     edx, r10d
0x180b2cbe0  mov     dword ptr [rsp+1E0h+h], eax
0x180b2cbe4  mov     rax, cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b2cbeb  mov     [rsp+1E0h+hdcSrc], r14
0x180b2cbf0  mov     dword ptr [rbp+0E0h+var_150], r10d
0x180b2cbf4  mov     dword ptr [rsp+1E0h+lpBits], r15d
0x180b2cbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b2cbfe  mov     ebx, eax
0x180b2cc00  test    eax, eax
0x180b2cc02  jnz     short loc_180B2CC4A
0x180b2cc04  call    cs:__imp_GetLastError
0x180b2cc0a  cmp     eax, 57h ; 'W'
0x180b2cc0d  jnz     short loc_180B2CC4A
0x180b2cc0f  mov     eax, dword ptr [rsp+1E0h+h]
0x180b2cc13  mov     rcx, rdi; this
0x180b2cc16  mov     r9d, [rsp+78h]; int
0x180b2cc1b  mov     r8d, dword ptr [rbp+0E0h+var_150]; int
0x180b2cc1f  mov     [rsp+50h], esi; int
0x180b2cc23  mov     [rsp+1E0h+var_198], r13d; int
0x180b2cc28  mov     [rsp+1E0h+rop], eax; int
0x180b2cc2c  mov     eax, [rsp+1E0h+var_170]
0x180b2cc30  mov     [rsp+1E0h+y1], eax; int
0x180b2cc34  mov     qword ptr [rsp+1E0h+x1], r14; hdc
0x180b2cc39  mov     dword ptr [rsp+1E0h+hdcSrc], r15d; int
0x180b2cc3e  mov     dword ptr [rsp+1E0h+lpBits], r12d; int
0x180b2cc43  call    ?GDIPlusAlphaBlend@XHDC@@IEBAHPEAUHDC__@@HHHH0HHHH@Z; XHDC::GDIPlusAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int)
0x180b2cc48  mov     ebx, eax
0x180b2cc4a  mov     eax, ebx
0x180b2cc4c  jmp     loc_180B2D12F
0x180b2cc51  mov     r15d, [rbp+0E0h+arg_30]
0x180b2cc58  add     r15d, [rbx]
0x180b2cc5b  mov     r12d, [rbp+0E0h+arg_38]
0x180b2cc62  add     r12d, [rbx+4]
0x180b2cc66  jmp     short loc_180B2CC76
0x180b2cc68  mov     r12d, [rbp+0E0h+arg_38]
0x180b2cc6f  mov     r15d, [rbp+0E0h+arg_30]
0x180b2cc76  mov     ecx, dword ptr [rbp+0E0h+var_150]
0x180b2cc79  mov     edx, [rsp+1E0h+var_180+4]
0x180b2cc7d  mov     eax, dword ptr [rsp+1E0h+h]
0x180b2cc81  add     eax, ecx
0x180b2cc83  mov     [rbp+0E0h+var_160], ecx
0x180b2cc86  mov     ecx, [rbp+0E0h+arg_20]
0x180b2cc8c  add     ecx, edx
0x180b2cc8e  mov     [rbp+0E0h+var_15C], edx
0x180b2cc91  mov     [rbp+0E0h+var_154], ecx
0x180b2cc94  lea     rdx, [rbp+0E0h+var_160]; struct CRect *
0x180b2cc98  mov     rcx, rdi; this
0x180b2cc9b  mov     [rbp+0E0h+var_158], eax
0x180b2cc9e  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b2cca3  test    eax, eax
0x180b2cca5  jz      loc_180B2D12D
0x180b2ccab  mov     rcx, rdi; this
0x180b2ccae  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b2ccb3  mov     [rsp+1E0h+var_180+4], eax
0x180b2ccb7  test    eax, eax
0x180b2ccb9  jnz     loc_180B2CD7F
0x180b2ccbf  mov     eax, [rbp+0E0h+var_158]
0x180b2ccc2  mov     rcx, rdi; this
0x180b2ccc5  sub     eax, [rbp+0E0h+var_160]
0x180b2ccc8  mov     ebx, [rbp+0E0h+var_154]
0x180b2cccb  mov     edx, eax; int
0x180b2cccd  sub     ebx, [rbp+0E0h+var_15C]
0x180b2ccd0  mov     r8d, ebx; int
0x180b2ccd3  mov     [rsp+1E0h+var_180+4], eax
0x180b2ccd7  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b2ccdc  test    al, al
0x180b2ccde  jz      loc_180B2D12D
0x180b2cce4  mov     ecx, dword ptr [rbp+0E0h+arg_50.BlendOp]
0x180b2ccea  mov     r9d, [rsp+1E0h+var_180+4]
0x180b2ccef  mov     r8d, [rbp+0E0h+var_15C]
0x180b2ccf3  mov     edx, [rbp+0E0h+var_160]
0x180b2ccf6  mov     rax, cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b2ccfd  mov     [rsp+50h], ecx
0x180b2cd01  mov     rcx, [rdi+20h]
0x180b2cd05  mov     [rsp+1E0h+var_198], esi
0x180b2cd09  mov     [rsp+1E0h+rop], r13d
0x180b2cd0e  mov     [rsp+1E0h+y1], r12d
0x180b2cd13  mov     [rsp+1E0h+x1], r15d
0x180b2cd18  mov     [rsp+1E0h+hdcSrc], r14
0x180b2cd1d  mov     dword ptr [rsp+1E0h+lpBits], ebx
0x180b2cd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b2cd26  mov     dword ptr [rsp+1E0h+h], eax
0x180b2cd2a  test    eax, eax
0x180b2cd2c  jnz     loc_180B2D12F
0x180b2cd32  call    cs:__imp_GetLastError
0x180b2cd38  cmp     eax, 57h ; 'W'
0x180b2cd3b  jnz     short loc_180B2CD76
0x180b2cd3d  mov     eax, [rsp+1E0h+var_180+4]
0x180b2cd41  mov     rcx, rdi; this
0x180b2cd44  mov     r9d, [rbp+0E0h+var_15C]; int
0x180b2cd48  mov     r8d, [rbp+0E0h+var_160]; int
0x180b2cd4c  mov     [rsp+50h], esi; int
0x180b2cd50  mov     [rsp+1E0h+var_198], r13d; int
0x180b2cd55  mov     [rsp+1E0h+rop], r12d; int
0x180b2cd5a  mov     [rsp+1E0h+y1], r15d; int
0x180b2cd5f  mov     qword ptr [rsp+1E0h+x1], r14; hdc
0x180b2cd64  mov     dword ptr [rsp+1E0h+hdcSrc], ebx; int
0x180b2cd68  mov     dword ptr [rsp+1E0h+lpBits], eax; int
0x180b2cd6c  call    ?GDIPlusAlphaBlend@XHDC@@IEBAHPEAUHDC__@@HHHH0HHHH@Z; XHDC::GDIPlusAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int)
0x180b2cd71  jmp     loc_180B2D12F
0x180b2cd76  mov     eax, dword ptr [rsp+1E0h+h]
0x180b2cd7a  jmp     loc_180B2D12F
0x180b2cd7f  xor     eax, eax
0x180b2cd81  mov     r8d, esi; cy
0x180b2cd84  mov     edx, r13d; cx
0x180b2cd87  mov     [rbp+0E0h+var_150], rax
0x180b2cd8b  mov     rcx, r14; hdc
0x180b2cd8e  mov     byte ptr [rsp+1E0h+var_180], al
0x180b2cd92  xor     ebx, ebx
0x180b2cd94  call    cs:__imp_CreateCompatibleBitmap
0x180b2cd9a  cmp     [rsp+1E0h+var_180+4], 0B4h
0x180b2cda2  mov     rcx, r14; hdc
0x180b2cda5  mov     [rsp+1E0h+h], rax
0x180b2cdaa  jnz     short loc_180B2CDB4
0x180b2cdac  mov     r8d, esi
0x180b2cdaf  mov     edx, r13d
0x180b2cdb2  jmp     short loc_180B2CDB9
0x180b2cdb4  mov     r8d, r13d; cy
0x180b2cdb7  mov     edx, esi; cx
0x180b2cdb9  call    cs:__imp_CreateCompatibleBitmap
0x180b2cdbf  mov     rcx, r14; hdc
0x180b2cdc2  mov     [rsp+78h], rax
0x180b2cdc7  call    cs:__imp_CreateCompatibleDC
0x180b2cdcd  mov     rsi, rax
0x180b2cdd0  mov     rax, [rsp+1E0h+h]
0x180b2cdd5  test    rax, rax
0x180b2cdd8  jz      loc_180B2D120
0x180b2cdde  cmp     [rsp+78h], rbx
0x180b2cde3  jz      loc_180B2D120
0x180b2cde9  test    rsi, rsi
0x180b2cdec  jz      loc_180B2D120
0x180b2cdf2  mov     rdx, rax; h
0x180b2cdf5  mov     rcx, rsi; hdc
0x180b2cdf8  call    cs:__imp_SelectObject
0x180b2cdfe  mov     ecx, [rsp+1E0h+var_170]
0x180b2ce02  mov     r9d, r13d; cx
0x180b2ce05  mov     [rsp+1E0h+rop], 0CC0020h; rop
0x180b2ce0d  xor     r8d, r8d; y
0x180b2ce10  mov     [rsp+1E0h+y1], r12d; y1
0x180b2ce15  xor     edx, edx; x
0x180b2ce17  mov     [rsp+1E0h+x1], r15d; x1
0x180b2ce1c  mov     [rsp+1E0h+hdcSrc], r14; hdcSrc
0x180b2ce21  mov     dword ptr [rsp+1E0h+lpBits], ecx; cy
0x180b2ce25  mov     rcx, rsi; hdc
0x180b2ce28  mov     [rbp+0E0h+var_150], rax
0x180b2ce2c  call    cs:__imp_BitBlt
0x180b2ce32  mov     r15, [rsp+78h]
0x180b2ce37  mov     rcx, rsi; hdc
0x180b2ce3a  mov     rdx, r15; h
0x180b2ce3d  call    cs:__imp_SelectObject
0x180b2ce43  mov     r12, [rsp+1E0h+h]
0x180b2ce48  lea     r8, [rbp+0E0h+pv]; pv
0x180b2ce4c  mov     r13d, 20h ; ' '
0x180b2ce52  mov     rcx, r12; h
0x180b2ce55  mov     edx, r13d; c
0x180b2ce58  call    cs:__imp_GetObjectW
0x180b2ce5e  lea     r8, [rbp+0E0h+cLines]; pv
0x180b2ce62  mov     edx, r13d; c
0x180b2ce65  mov     rcx, r15; h
0x180b2ce68  call    cs:__imp_GetObjectW
0x180b2ce6e  cmp     qword ptr [rbp+0E0h+var_110+8], rbx
0x180b2ce72  jnz     short loc_180B2CEEB
0x180b2ce74  cmp     word ptr [rbp+0E0h+var_110+2], r13w
0x180b2ce79  jz      short loc_180B2CE85
0x180b2ce7b  mov     ebx, 80004005h
0x180b2ce80  jmp     loc_180B2D05F
0x180b2ce85  xor     edx, edx; Val
0x180b2ce87  lea     rcx, [rbp+0E0h+var_FC]; void *
0x180b2ce8b  lea     r8d, [rdx+74h]; Size
0x180b2ce8f  call    memset_0
0x180b2ce94  lea     rdx, [rbp+0E0h+var_148]; struct IDirectDrawSurface **
0x180b2ce98  mov     [rbp+0E0h+var_100], 78h ; 'x'
0x180b2ce9f  mov     rcx, r14; HDC
0x180b2cea2  call    ?GetSurfaceFromDC@CDirectDraw@@SAJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@@Z; CDirectDraw::GetSurfaceFromDC(HDC__ *,IDirectDrawSurface * *)
0x180b2cea7  mov     ebx, eax
0x180b2cea9  test    eax, eax
0x180b2ceab  js      loc_180B2D05F
0x180b2ceb1  mov     rcx, [rbp+0E0h+var_148]
0x180b2ceb5  lea     r8, [rbp+0E0h+var_100]
0x180b2ceb9  mov     r9d, 800h
0x180b2cebf  mov     [rsp+1E0h+lpBits], 0
0x180b2cec8  xor     edx, edx
0x180b2ceca  mov     rax, [rcx]
0x180b2cecd  mov     rax, [rax+0C8h]
0x180b2ced4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b2ced9  mov     ebx, eax
0x180b2cedb  test    eax, eax
0x180b2cedd  js      loc_180B2D05F
0x180b2cee3  mov     rax, [rbp+0E0h+var_D8]
0x180b2cee7  mov     qword ptr [rbp+0E0h+var_110+8], rax
0x180b2ceeb  cmp     [rbp+0E0h+var_130+8], 0
0x180b2cef0  jnz     short loc_180B2CF2F
0x180b2cef2  cmp     word ptr [rbp+0E0h+var_130+2], r13w
0x180b2cef7  jnz     short loc_180B2CE7B
0x180b2cef9  mov     eax, [rbp+0E0h+cLines+8]
0x180b2cefc  imul    eax, [rbp+0E0h+cLines+4]
0x180b2cf00  mov     rcx, cs:g_hProcessHeap
0x180b2cf07  shl     eax, 2
0x180b2cf0a  movsxd  rdx, eax
0x180b2cf0d  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180b2cf12  mov     [rbp+0E0h+var_130+8], rax
0x180b2cf16  test    rax, rax
0x180b2cf19  jnz     short loc_180B2CF25
0x180b2cf1b  mov     ebx, 8007000Eh
0x180b2cf20  jmp     loc_180B2D05F
0x180b2cf25  mov     r14b, 1
0x180b2cf28  mov     byte ptr [rsp+1E0h+var_180], r14b
0x180b2cf2d  jmp     short loc_180B2CF34
0x180b2cf2f  mov     r14b, byte ptr [rsp+1E0h+var_180]
0x180b2cf34  mov     r8d, [rsp+1E0h+var_180+4]
0x180b2cf39  lea     rdx, [rbp+0E0h+cLines]
0x180b2cf3d  lea     rcx, [rbp+0E0h+pv]
0x180b2cf41  call    RotateBitmap
0x180b2cf46  mov     rcx, [rbp+0E0h+var_148]
0x180b2cf4a  test    rcx, rcx
  ... truncated ...
```
