# XHDC::AlphaBlend(int,int,int,int,XHDC const &,int,int,int,int,_BLENDFUNCTION)

- ea: `0x180b440c4`
- end: `0x180b44807`
- name: `?AlphaBlend@XHDC@@QEBAHHHHHAEBV1@HHHHU_BLENDFUNCTION@@@Z`
- size: `1859`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, const struct XHDC *, int, int, int, int cy, struct _BLENDFUNCTION)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180b449b4`
- `0x180b47cdc`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x1800ea428`
- `0x180b440c4`
- `0x180b467a0`
- `0x180b46be8`
- `0x180b46d74`
- `0x180b46e50`
- `0x180b46f14`
- `0x180b4a458`
- `0x180b4a620`
- `0x180b610e8`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180b44250`
- `KERNEL32!GetLastError` at `0x180b44384`
- `KERNEL32!GetLastError` at `0x180b44778`
- `KERNEL32!GetLastError` at `0x180b44250`
- `KERNEL32!GetLastError` at `0x180b44384`
- `KERNEL32!GetLastError` at `0x180b44778`
- `GDI32!DeleteDC` at `0x180b44763`
- `GDI32!DeleteDC` at `0x180b44763`
- `GDI32!SetDIBits` at `0x180b44659`
- `GDI32!SetDIBits` at `0x180b44659`
- `GDI32!DeleteObject` at `0x180b4473b`
- `GDI32!DeleteObject` at `0x180b4474f`
- `GDI32!DeleteObject` at `0x180b4473b`
- `GDI32!DeleteObject` at `0x180b4474f`
- `GDI32!SelectObject` at `0x180b44462`
- `GDI32!SelectObject` at `0x180b444b3`
- `GDI32!SelectObject` at `0x180b44727`
- `GDI32!SelectObject` at `0x180b44462`
- `GDI32!SelectObject` at `0x180b444b3`
- `GDI32!SelectObject` at `0x180b44727`
- `GDI32!BitBlt` at `0x180b4449c`
- `GDI32!BitBlt` at `0x180b4449c`
- `GDI32!CreateCompatibleBitmap` at `0x180b443ec`
- `GDI32!CreateCompatibleBitmap` at `0x180b44417`
- `GDI32!CreateCompatibleBitmap` at `0x180b443ec`
- `GDI32!CreateCompatibleBitmap` at `0x180b44417`
- `GDI32!CreateCompatibleDC` at `0x180b4442b`
- `GDI32!CreateCompatibleDC` at `0x180b4442b`
- `GDI32!GetObjectW` at `0x180b444d4`
- `GDI32!GetObjectW` at `0x180b444ea`
- `GDI32!GetObjectW` at `0x180b444d4`
- `GDI32!GetObjectW` at `0x180b444ea`

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
  __int64 v34; // r8
  char v35; // r14
  unsigned int v36; // r13d
  int v37; // r14d
  unsigned int v38; // r12d
  void *v39; // r8
  HDC v40; // rdx
  int x1; // [rsp+38h] [rbp-D0h]
  char v42; // [rsp+68h] [rbp-A0h]
  unsigned int TrivialRotationAngle; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v45; // [rsp+6Ch] [rbp-9Ch]
  LONG ha; // [rsp+70h] [rbp-98h]
  int hb; // [rsp+70h] [rbp-98h]
  HBITMAP hc; // [rsp+70h] [rbp-98h]
  LONG v50; // [rsp+78h] [rbp-90h]
  int v51; // [rsp+78h] [rbp-90h]
  LONG cx; // [rsp+80h] [rbp-88h]
  int v53; // [rsp+80h] [rbp-88h]
  HBITMAP CompatibleBitmap; // [rsp+80h] [rbp-88h]
  int v55; // [rsp+88h] [rbp-80h] BYREF
  int v56; // [rsp+8Ch] [rbp-7Ch]
  unsigned int v57; // [rsp+90h] [rbp-78h]
  int v58; // [rsp+94h] [rbp-74h]
  HGDIOBJ v59; // [rsp+98h] [rbp-70h]
  struct IUnknown *v60; // [rsp+A0h] [rbp-68h] BYREF
  UINT cLines[4]; // [rsp+A8h] [rbp-60h] BYREF
  void *lpBits[2]; // [rsp+B8h] [rbp-50h]
  __int128 pv; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v64; // [rsp+D8h] [rbp-30h]
  int v65; // [rsp+E8h] [rbp-20h] BYREF
  char v66[36]; // [rsp+ECh] [rbp-1Ch] BYREF
  __int64 v67; // [rsp+110h] [rbp+8h]
  BITMAPINFO bmi; // [rsp+168h] [rbp+60h] BYREF

  hdcSrc = (HDC)*((_QWORD *)a6 + 4);
  LODWORD(v59) = a2;
  OffsetOnly = XHDC::GetOffsetOnly(this);
  v60 = 0;
  pv = 0;
  v15 = XHDC::GetOffsetOnly(a6);
  v64 = 0;
  *(_OWORD *)cLines = 0;
  *(_OWORD *)lpBits = 0;
  if ( !XHDC::s_pAlphaBlendProc && !(unsigned int)XHDC::LoadAlphaBlendProc() )
    return 0;
  if ( v15 )
  {
    if ( OffsetOnly )
    {
      cx = OffsetOnly->cx;
      v50 = OffsetOnly->cy;
      v16 = v15->cx;
      v17 = v15->cy;
      ha = v16;
      if ( XHDC::ValidateImageDestArea(this, a4, a5) )
      {
        v18 = (_DWORD)v59 + cx;
        v19 = v50 + a3;
        v20 = *((_QWORD *)this + 4);
        x1 = a7 + ha;
        v51 = a7 + ha;
        v53 = v19;
        hb = v17 + a8;
        LODWORD(v59) = v18;
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
          return (unsigned int)XHDC::GDIPlusAlphaBlend(this, v22, (int)v59, v53, a4, a5, hdcSrc, v51, hb, a9, cy);
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
  v55 = (int)v59;
  v56 = a3;
  v58 = a3 + a5;
  v57 = (_DWORD)v59 + a4;
  if ( !(unsigned int)XHDC::TransformRect(this, (struct CRect *)&v55) )
    return 0;
  TrivialRotationAngle = XHDC::GetTrivialRotationAngle(this);
  if ( TrivialRotationAngle )
  {
    v59 = 0;
    v42 = 0;
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
    v59 = SelectObject(CompatibleDC, hc);
    BitBlt(CompatibleDC, 0, 0, a9, cy, hdcSrc, v24, y1, 0xCC0020u);
    v32 = CompatibleBitmap;
    SelectObject(CompatibleDC, CompatibleBitmap);
    v33 = hc;
    GetObjectW(hc, 32, &pv);
    GetObjectW(CompatibleBitmap, 32, cLines);
    if ( !*((_QWORD *)&v64 + 1) )
    {
      if ( WORD1(v64) != 32 )
      {
LABEL_27:
        SurfaceFromDC = -2147467259;
LABEL_45:
        ReleaseInterface(v60);
        ReleaseInterface(0);
        if ( v42 )
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, lpBits[1], v39);
        if ( v59 )
          SelectObject(CompatibleDC, v59);
        if ( v33 )
          DeleteObject(v33);
        if ( v32 )
          DeleteObject(v32);
        if ( CompatibleDC )
          DeleteDC(CompatibleDC);
        return SurfaceFromDC >= 0;
      }
      memset_0(v66, 0, 0x74u);
      v65 = 120;
      SurfaceFromDC = CDirectDraw::GetSurfaceFromDC(hdcSrc, (struct IDirectDrawSurface **)&v60);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, __int64, _QWORD))v60->lpVtbl[8].AddRef)(
                        v60,
                        0,
                        &v65,
                        2048,
                        0);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
      *((_QWORD *)&v64 + 1) = v67;
    }
    if ( lpBits[1] )
    {
      v35 = 0;
    }
    else
    {
      if ( WORD1(lpBits[0]) != 32 )
        goto LABEL_27;
      lpBits[1] = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 4 * cLines[1] * cLines[2], v34);
      if ( !lpBits[1] )
      {
        SurfaceFromDC = -2147024882;
        goto LABEL_45;
      }
      v35 = 1;
      v42 = 1;
    }
    RotateBitmap(&pv, cLines, TrivialRotationAngle);
    if ( v60 )
    {
      SurfaceFromDC = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v60->lpVtbl[10].Release)(v60, 0);
      if ( SurfaceFromDC < 0 )
        goto LABEL_45;
    }
    if ( !v35
      || (bmi.bmiHeader.biWidth = cLines[1],
          *(_DWORD *)&bmi.bmiHeader.biPlanes = lpBits[0],
          bmi.bmiHeader.biSize = 40,
          bmi.bmiHeader.biHeight = cLines[2],
          memset(&bmi.bmiHeader.biCompression, 0, 28),
          SetDIBits(CompatibleDC, CompatibleBitmap, 0, cLines[2], lpBits[1], &bmi, 0)) )
    {
      SurfaceFromDC = -2147467259;
      v36 = v56;
      v37 = v58 - v56;
      v38 = v57 - v55;
      if ( XHDC::ValidateImageDestArea(this, v57 - v55, v58 - v56) )
      {
        if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))XHDC::s_pAlphaBlendProc)(
                             *((_QWORD *)this + 4),
                             (unsigned int)v55,
                             v36,
                             v38,
                             v37,
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
                                          v40,
                                          v55,
                                          v36,
                                          v38,
                                          v37,
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
  v26 = v58 - v56;
  v45 = v57 - v55;
  if ( !XHDC::ValidateImageDestArea(this, v57 - v55, v58 - v56) )
    return 0;
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))XHDC::s_pAlphaBlendProc)(
             *((_QWORD *)this + 4),
             (unsigned int)v55,
             (unsigned int)v56,
             v45,
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
      return XHDC::GDIPlusAlphaBlend(this, v27, v55, v56, v45, v26, hdcSrc, v24, y1, a9, cy);
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180b440c4  mov     rax, rsp
0x180b440c7  mov     [rax+20h], r9d
0x180b440cb  mov     [rax+18h], r8d
0x180b440cf  mov     [rax+10h], edx
0x180b440d2  mov     [rax+8], rcx
0x180b440d6  push    rbp
0x180b440d7  push    rbx
0x180b440d8  push    rsi
0x180b440d9  push    rdi
0x180b440da  push    r12
0x180b440dc  push    r13
0x180b440de  push    r14
0x180b440e0  push    r15
0x180b440e2  lea     rbp, [rax-0E8h]
0x180b440e9  sub     rsp, 1A8h
0x180b440f0  mov     rax, cs:__security_cookie
0x180b440f7  xor     rax, rsp
0x180b440fa  mov     [rbp+0E0h+var_50], rax
0x180b44101  mov     eax, [rbp+0E0h+arg_8]
0x180b44107  mov     rbx, [rbp+0E0h+arg_28]
0x180b4410e  mov     rdi, [rbp+0E0h+arg_0]
0x180b44115  mov     r12d, [rbp+0E0h+arg_18]
0x180b4411c  mov     rcx, rdi; this
0x180b4411f  mov     esi, [rbp+0E0h+cy]
0x180b44125  mov     r14, [rbx+20h]
0x180b44129  mov     r13d, [rbp+0E0h+arg_40]
0x180b44130  mov     dword ptr [rbp+0E0h+var_150], eax
0x180b44133  mov     eax, [rbp+0E0h+arg_10]
0x180b44139  mov     [rsp+1E0h+var_180+4], eax
0x180b4413d  mov     dword ptr [rsp+1E0h+h], r12d
0x180b44142  mov     [rsp+1E0h+var_170], esi
0x180b44146  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b4414b  mov     rcx, rbx; this
0x180b4414e  mov     r15, rax
0x180b44151  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b44156  cmp     cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA, 0; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b4415e  xorps   xmm0, xmm0
0x180b44161  xorps   xmm1, xmm1
0x180b44164  mov     [rbp+0E0h+var_148], 0
0x180b4416c  movups  [rbp+0E0h+pv], xmm0
0x180b44170  mov     rbx, rax
0x180b44173  movups  [rbp+0E0h+var_110], xmm0
0x180b44177  movups  xmmword ptr [rbp+0E0h+cLines], xmm1
0x180b4417b  movups  xmmword ptr [rbp+0E0h+var_130], xmm1
0x180b4417f  jnz     short loc_180B4418E
0x180b44181  call    ?LoadAlphaBlendProc@XHDC@@CAHXZ; XHDC::LoadAlphaBlendProc(void)
0x180b44186  test    eax, eax
0x180b44188  jz      loc_180B447E1
0x180b4418e  test    rbx, rbx
0x180b44191  jz      loc_180B442BA
0x180b44197  test    r15, r15
0x180b4419a  jz      loc_180B442A3
0x180b441a0  mov     eax, [r15]
0x180b441a3  mov     edx, r12d; int
0x180b441a6  mov     [rsp+78h], eax
0x180b441aa  mov     rcx, rdi; this
0x180b441ad  mov     eax, [r15+4]
0x180b441b1  mov     r15d, [rbp+0E0h+arg_20]
0x180b441b8  mov     r8d, r15d; int
0x180b441bb  mov     [rsp+1E0h+var_170], eax
0x180b441bf  mov     eax, [rbx]
0x180b441c1  mov     ebx, [rbx+4]
0x180b441c4  mov     dword ptr [rsp+1E0h+h], eax
0x180b441c8  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b441cd  test    al, al
0x180b441cf  jz      loc_180B447E1
0x180b441d5  mov     r8d, dword ptr [rsp+1E0h+h]
0x180b441da  mov     r9d, r12d
0x180b441dd  add     r8d, [rbp+0E0h+arg_30]
0x180b441e4  mov     r10d, [rsp+78h]
0x180b441e9  add     r10d, dword ptr [rbp+0E0h+var_150]
0x180b441ed  mov     eax, [rbp+0E0h+arg_38]
0x180b441f3  mov     ecx, dword ptr [rbp+0E0h+arg_50.BlendOp]
0x180b441f9  add     eax, ebx
0x180b441fb  mov     edx, [rsp+1E0h+var_180+4]
0x180b441ff  add     edx, [rsp+1E0h+var_170]
0x180b44203  mov     [rsp+50h], ecx
0x180b44207  mov     rcx, [rdi+20h]
0x180b4420b  mov     [rsp+1E0h+var_198], esi
0x180b4420f  mov     [rsp+1E0h+rop], r13d
0x180b44214  mov     [rsp+1E0h+y1], eax
0x180b44218  mov     [rsp+1E0h+x1], r8d
0x180b4421d  mov     [rsp+1E0h+var_170], r8d
0x180b44222  mov     r8d, edx
0x180b44225  mov     [rsp+78h], edx
0x180b44229  mov     edx, r10d
0x180b4422c  mov     dword ptr [rsp+1E0h+h], eax
0x180b44230  mov     rax, cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b44237  mov     [rsp+1E0h+hdcSrc], r14
0x180b4423c  mov     dword ptr [rbp+0E0h+var_150], r10d
0x180b44240  mov     dword ptr [rsp+1E0h+lpBits], r15d
0x180b44245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b4424a  mov     ebx, eax
0x180b4424c  test    eax, eax
0x180b4424e  jnz     short loc_180B4429C
0x180b44250  call    cs:__imp_GetLastError
0x180b44257  nop     dword ptr [rax+rax+00h]
0x180b4425c  cmp     eax, 57h ; 'W'
0x180b4425f  jnz     short loc_180B4429C
0x180b44261  mov     eax, dword ptr [rsp+1E0h+h]
0x180b44265  mov     rcx, rdi; this
0x180b44268  mov     r9d, [rsp+78h]; int
0x180b4426d  mov     r8d, dword ptr [rbp+0E0h+var_150]; int
0x180b44271  mov     [rsp+50h], esi; int
0x180b44275  mov     [rsp+1E0h+var_198], r13d; int
0x180b4427a  mov     [rsp+1E0h+rop], eax; int
0x180b4427e  mov     eax, [rsp+1E0h+var_170]
0x180b44282  mov     [rsp+1E0h+y1], eax; int
0x180b44286  mov     qword ptr [rsp+1E0h+x1], r14; hdc
0x180b4428b  mov     dword ptr [rsp+1E0h+hdcSrc], r15d; int
0x180b44290  mov     dword ptr [rsp+1E0h+lpBits], r12d; int
0x180b44295  call    ?GDIPlusAlphaBlend@XHDC@@IEBAHPEAUHDC__@@HHHH0HHHH@Z; XHDC::GDIPlusAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int)
0x180b4429a  mov     ebx, eax
0x180b4429c  mov     eax, ebx
0x180b4429e  jmp     loc_180B447E3
0x180b442a3  mov     r15d, [rbp+0E0h+arg_30]
0x180b442aa  add     r15d, [rbx]
0x180b442ad  mov     r12d, [rbp+0E0h+arg_38]
0x180b442b4  add     r12d, [rbx+4]
0x180b442b8  jmp     short loc_180B442C8
0x180b442ba  mov     r12d, [rbp+0E0h+arg_38]
0x180b442c1  mov     r15d, [rbp+0E0h+arg_30]
0x180b442c8  mov     ecx, dword ptr [rbp+0E0h+var_150]
0x180b442cb  mov     edx, [rsp+1E0h+var_180+4]
0x180b442cf  mov     eax, dword ptr [rsp+1E0h+h]
0x180b442d3  add     eax, ecx
0x180b442d5  mov     [rbp+0E0h+var_160], ecx
0x180b442d8  mov     ecx, [rbp+0E0h+arg_20]
0x180b442de  add     ecx, edx
0x180b442e0  mov     [rbp+0E0h+var_15C], edx
0x180b442e3  mov     [rbp+0E0h+var_154], ecx
0x180b442e6  lea     rdx, [rbp+0E0h+var_160]; struct CRect *
0x180b442ea  mov     rcx, rdi; this
0x180b442ed  mov     [rbp+0E0h+var_158], eax
0x180b442f0  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b442f5  test    eax, eax
0x180b442f7  jz      loc_180B447E1
0x180b442fd  mov     rcx, rdi; this
0x180b44300  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b44305  mov     [rsp+1E0h+var_180+4], eax
0x180b44309  test    eax, eax
0x180b4430b  jnz     loc_180B443D7
0x180b44311  mov     eax, [rbp+0E0h+var_158]
0x180b44314  mov     rcx, rdi; this
0x180b44317  sub     eax, [rbp+0E0h+var_160]
0x180b4431a  mov     ebx, [rbp+0E0h+var_154]
0x180b4431d  mov     edx, eax; int
0x180b4431f  sub     ebx, [rbp+0E0h+var_15C]
0x180b44322  mov     r8d, ebx; int
0x180b44325  mov     [rsp+1E0h+var_180+4], eax
0x180b44329  call    ?ValidateImageDestArea@XHDC@@AEBA_NHH@Z; XHDC::ValidateImageDestArea(int,int)
0x180b4432e  test    al, al
0x180b44330  jz      loc_180B447E1
0x180b44336  mov     ecx, dword ptr [rbp+0E0h+arg_50.BlendOp]
0x180b4433c  mov     r9d, [rsp+1E0h+var_180+4]
0x180b44341  mov     r8d, [rbp+0E0h+var_15C]
0x180b44345  mov     edx, [rbp+0E0h+var_160]
0x180b44348  mov     rax, cs:?s_pAlphaBlendProc@XHDC@@0P6AHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@ZEA; int (*XHDC::s_pAlphaBlendProc)(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x180b4434f  mov     [rsp+50h], ecx
0x180b44353  mov     rcx, [rdi+20h]
0x180b44357  mov     [rsp+1E0h+var_198], esi
0x180b4435b  mov     [rsp+1E0h+rop], r13d
0x180b44360  mov     [rsp+1E0h+y1], r12d
0x180b44365  mov     [rsp+1E0h+x1], r15d
0x180b4436a  mov     [rsp+1E0h+hdcSrc], r14
0x180b4436f  mov     dword ptr [rsp+1E0h+lpBits], ebx
0x180b44373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b44378  mov     dword ptr [rsp+1E0h+h], eax
0x180b4437c  test    eax, eax
0x180b4437e  jnz     loc_180B447E3
0x180b44384  call    cs:__imp_GetLastError
0x180b4438b  nop     dword ptr [rax+rax+00h]
0x180b44390  cmp     eax, 57h ; 'W'
0x180b44393  jnz     short loc_180B443CE
0x180b44395  mov     eax, [rsp+1E0h+var_180+4]
0x180b44399  mov     rcx, rdi; this
0x180b4439c  mov     r9d, [rbp+0E0h+var_15C]; int
0x180b443a0  mov     r8d, [rbp+0E0h+var_160]; int
0x180b443a4  mov     [rsp+50h], esi; int
0x180b443a8  mov     [rsp+1E0h+var_198], r13d; int
0x180b443ad  mov     [rsp+1E0h+rop], r12d; int
0x180b443b2  mov     [rsp+1E0h+y1], r15d; int
0x180b443b7  mov     qword ptr [rsp+1E0h+x1], r14; hdc
0x180b443bc  mov     dword ptr [rsp+1E0h+hdcSrc], ebx; int
0x180b443c0  mov     dword ptr [rsp+1E0h+lpBits], eax; int
0x180b443c4  call    ?GDIPlusAlphaBlend@XHDC@@IEBAHPEAUHDC__@@HHHH0HHHH@Z; XHDC::GDIPlusAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int)
0x180b443c9  jmp     loc_180B447E3
0x180b443ce  mov     eax, dword ptr [rsp+1E0h+h]
0x180b443d2  jmp     loc_180B447E3
0x180b443d7  xor     eax, eax
0x180b443d9  mov     r8d, esi; cy
0x180b443dc  mov     edx, r13d; cx
0x180b443df  mov     [rbp+0E0h+var_150], rax
0x180b443e3  mov     rcx, r14; hdc
0x180b443e6  mov     byte ptr [rsp+1E0h+var_180], al
0x180b443ea  xor     ebx, ebx
0x180b443ec  call    cs:__imp_CreateCompatibleBitmap
0x180b443f3  nop     dword ptr [rax+rax+00h]
0x180b443f8  cmp     [rsp+1E0h+var_180+4], 0B4h
0x180b44400  mov     rcx, r14; hdc
0x180b44403  mov     [rsp+1E0h+h], rax
0x180b44408  jnz     short loc_180B44412
0x180b4440a  mov     r8d, esi
0x180b4440d  mov     edx, r13d
0x180b44410  jmp     short loc_180B44417
0x180b44412  mov     r8d, r13d; cy
0x180b44415  mov     edx, esi; cx
0x180b44417  call    cs:__imp_CreateCompatibleBitmap
0x180b4441e  nop     dword ptr [rax+rax+00h]
0x180b44423  mov     rcx, r14; hdc
0x180b44426  mov     [rsp+78h], rax
0x180b4442b  call    cs:__imp_CreateCompatibleDC
0x180b44432  nop     dword ptr [rax+rax+00h]
0x180b44437  mov     rsi, rax
0x180b4443a  mov     rax, [rsp+1E0h+h]
0x180b4443f  test    rax, rax
0x180b44442  jz      loc_180B447D4
0x180b44448  cmp     [rsp+78h], rbx
0x180b4444d  jz      loc_180B447D4
0x180b44453  test    rsi, rsi
0x180b44456  jz      loc_180B447D4
0x180b4445c  mov     rdx, rax; h
0x180b4445f  mov     rcx, rsi; hdc
0x180b44462  call    cs:__imp_SelectObject
0x180b44469  nop     dword ptr [rax+rax+00h]
0x180b4446e  mov     ecx, [rsp+1E0h+var_170]
0x180b44472  mov     r9d, r13d; cx
0x180b44475  mov     [rsp+1E0h+rop], 0CC0020h; rop
0x180b4447d  xor     r8d, r8d; y
0x180b44480  mov     [rsp+1E0h+y1], r12d; y1
0x180b44485  xor     edx, edx; x
0x180b44487  mov     [rsp+1E0h+x1], r15d; x1
0x180b4448c  mov     [rsp+1E0h+hdcSrc], r14; hdcSrc
0x180b44491  mov     dword ptr [rsp+1E0h+lpBits], ecx; cy
0x180b44495  mov     rcx, rsi; hdc
0x180b44498  mov     [rbp+0E0h+var_150], rax
0x180b4449c  call    cs:__imp_BitBlt
0x180b444a3  nop     dword ptr [rax+rax+00h]
0x180b444a8  mov     r15, [rsp+78h]
0x180b444ad  mov     rcx, rsi; hdc
0x180b444b0  mov     rdx, r15; h
0x180b444b3  call    cs:__imp_SelectObject
0x180b444ba  nop     dword ptr [rax+rax+00h]
0x180b444bf  mov     r12, [rsp+1E0h+h]
0x180b444c4  lea     r8, [rbp+0E0h+pv]; pv
0x180b444c8  mov     r13d, 20h ; ' '
0x180b444ce  mov     rcx, r12; h
0x180b444d1  mov     edx, r13d; c
0x180b444d4  call    cs:__imp_GetObjectW
0x180b444db  nop     dword ptr [rax+rax+00h]
0x180b444e0  lea     r8, [rbp+0E0h+cLines]; pv
0x180b444e4  mov     edx, r13d; c
0x180b444e7  mov     rcx, r15; h
0x180b444ea  call    cs:__imp_GetObjectW
0x180b444f1  nop     dword ptr [rax+rax+00h]
0x180b444f6  cmp     qword ptr [rbp+0E0h+var_110+8], rbx
0x180b444fa  jnz     short loc_180B44573
0x180b444fc  cmp     word ptr [rbp+0E0h+var_110+2], r13w
0x180b44501  jz      short loc_180B4450D
0x180b44503  mov     ebx, 80004005h
0x180b44508  jmp     loc_180B446F1
0x180b4450d  xor     edx, edx; Val
0x180b4450f  lea     rcx, [rbp+0E0h+var_FC]; void *
0x180b44513  lea     r8d, [rdx+74h]; Size
0x180b44517  call    memset_0
0x180b4451c  lea     rdx, [rbp+0E0h+var_148]; struct IDirectDrawSurface **
0x180b44520  mov     [rbp+0E0h+var_100], 78h ; 'x'
0x180b44527  mov     rcx, r14; HDC
0x180b4452a  call    ?GetSurfaceFromDC@CDirectDraw@@SAJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@@Z; CDirectDraw::GetSurfaceFromDC(HDC__ *,IDirectDrawSurface * *)
0x180b4452f  mov     ebx, eax
0x180b44531  test    eax, eax
0x180b44533  js      loc_180B446F1
0x180b44539  mov     rcx, [rbp+0E0h+var_148]
0x180b4453d  lea     r8, [rbp+0E0h+var_100]
0x180b44541  mov     r9d, 800h
0x180b44547  mov     [rsp+1E0h+lpBits], 0
0x180b44550  xor     edx, edx
0x180b44552  mov     rax, [rcx]
0x180b44555  mov     rax, [rax+0C8h]
0x180b4455c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b44561  mov     ebx, eax
0x180b44563  test    eax, eax
0x180b44565  js      loc_180B446F1
0x180b4456b  mov     rax, [rbp+0E0h+var_D8]
0x180b4456f  mov     qword ptr [rbp+0E0h+var_110+8], rax
0x180b44573  cmp     [rbp+0E0h+var_130+8], 0
0x180b44578  jnz     short loc_180B445B7
0x180b4457a  cmp     word ptr [rbp+0E0h+var_130+2], r13w
0x180b4457f  jnz     short loc_180B44503
0x180b44581  mov     eax, [rbp+0E0h+cLines+8]
0x180b44584  imul    eax, [rbp+0E0h+cLines+4]
0x180b44588  mov     rcx, cs:g_hProcessHeap
0x180b4458f  shl     eax, 2
0x180b44592  movsxd  rdx, eax
0x180b44595  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180b4459a  mov     [rbp+0E0h+var_130+8], rax
0x180b4459e  test    rax, rax
0x180b445a1  jnz     short loc_180B445AD
0x180b445a3  mov     ebx, 8007000Eh
0x180b445a8  jmp     loc_180B446F1
  ... truncated ...
```
