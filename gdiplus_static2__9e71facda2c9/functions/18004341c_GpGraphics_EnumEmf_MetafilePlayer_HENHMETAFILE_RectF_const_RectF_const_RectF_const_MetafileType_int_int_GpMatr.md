# GpGraphics::EnumEmf(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,RectF const &,MetafileType,int,int,GpMatrix const &,int)

- ea: `0x18004341c`
- end: `0x180043c96`
- name: `?EnumEmf@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@22W4MetafileType@@HHAEBVGpMatrix@@H@Z`
- size: `2170`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800421f4`

## callees

- `0x180006718`
- `0x18002f12c`
- `0x18002f21c`
- `0x180035ac0`
- `0x18004321c`
- `0x18004341c`
- `0x180043c9c`
- `0x180044ce8`
- `0x180044d34`
- `0x180051890`
- `0x180080604`
- `0x1800e0e64`
- `0x180105d40`
- `0x1801066d0`
- `0x18012200c`
- `0x1801222a8`
- `0x180123600`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180043909`
- `GDI32!SetWorldTransform` at `0x180043909`
- `GDI32!SetGraphicsMode` at `0x1800438d1`
- `GDI32!SetGraphicsMode` at `0x1800438d1`
- `GDI32!SetViewportExtEx` at `0x18004372c`
- `GDI32!SetViewportExtEx` at `0x180043bba`
- `GDI32!SetViewportExtEx` at `0x18004372c`
- `GDI32!SetViewportExtEx` at `0x180043bba`
- `GDI32!SetViewportOrgEx` at `0x18004370d`
- `GDI32!SetViewportOrgEx` at `0x180043b9f`
- `GDI32!SetViewportOrgEx` at `0x18004370d`
- `GDI32!SetViewportOrgEx` at `0x180043b9f`
- `GDI32!SetWindowExtEx` at `0x1800436f5`
- `GDI32!SetWindowExtEx` at `0x180043b88`
- `GDI32!SetWindowExtEx` at `0x1800436f5`
- `GDI32!SetWindowExtEx` at `0x180043b88`
- `GDI32!SetWindowOrgEx` at `0x1800436da`
- `GDI32!SetWindowOrgEx` at `0x180043b6d`
- `GDI32!SetWindowOrgEx` at `0x1800436da`
- `GDI32!SetWindowOrgEx` at `0x180043b6d`
- `GDI32!SetMapMode` at `0x1800436bf`
- `GDI32!SetMapMode` at `0x180043b52`
- `GDI32!SetMapMode` at `0x1800436bf`
- `GDI32!SetMapMode` at `0x180043b52`
- `GDI32!SaveDC` at `0x180043496`
- `GDI32!SaveDC` at `0x180043496`
- `GDI32!RestoreDC` at `0x180043768`
- `GDI32!RestoreDC` at `0x180043768`
- `GDI32!DeleteDC` at `0x180043beb`
- `GDI32!DeleteDC` at `0x180043beb`
- `GDI32!SelectObject` at `0x180043af9`
- `GDI32!SelectObject` at `0x180043af9`
- `GDI32!CreateCompatibleDC` at `0x180043adb`
- `GDI32!CreateCompatibleDC` at `0x180043adb`
- `GDI32!DeleteObject` at `0x180043c6b`
- `GDI32!DeleteObject` at `0x180043c6b`

## pseudocode

```c
__int64 __fastcall GpGraphics::EnumEmf(
        struct DpBitmap **a1,
        __int64 a2,
        __int64 a3,
        float *a4,
        unsigned int *a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        int a11)
{
  struct DpBitmap *v12; // rdx
  DpContext *v14; // rcx
  HDC Hdc; // rax
  HDC v17; // rdi
  int v18; // eax
  DpContext *v19; // rcx
  bool v20; // r15
  unsigned int v21; // r14d
  __m128 v22; // xmm1
  int v23; // eax
  __m128 v24; // xmm1
  int v25; // eax
  __m128 v26; // xmm1
  int v27; // eax
  __m128 v28; // xmm1
  int v29; // eax
  float v30; // xmm6_4
  int v31; // eax
  float v32; // xmm7_4
  int v33; // eax
  float v34; // xmm6_4
  int v35; // eax
  float v36; // xmm7_4
  PointF *v37; // r15
  __int64 v38; // r13
  float v39; // xmm1_4
  FLOAT v40; // r12d
  FLOAT v41; // r13d
  FLOAT eM22; // r15d
  unsigned int v43; // eax
  __m128 v45; // xmm7
  __m128 v46; // xmm1
  int v47; // eax
  __m128 v48; // xmm6
  __m128 v49; // xmm1
  int v50; // eax
  int v51; // r13d
  int v52; // eax
  FLOAT v53; // xmm1_4
  XFORM *p_xf; // r9
  struct DpBitmap *v55; // rax
  void *DibSection32Bpp; // r13
  HDC CompatibleDC; // rax
  HDC v58; // r15
  unsigned int v59; // eax
  struct DpBitmap *v60; // rax
  int v61; // r15d
  int v62; // [rsp+28h] [rbp-E0h]
  int v63; // [rsp+38h] [rbp-D0h]
  __int128 v64; // [rsp+48h] [rbp-C0h] BYREF
  int y; // [rsp+58h] [rbp-B0h]
  int x; // [rsp+5Ch] [rbp-ACh]
  int v67[2]; // [rsp+60h] [rbp-A8h]
  __int64 v68; // [rsp+68h] [rbp-A0h]
  __int128 v69; // [rsp+70h] [rbp-98h] BYREF
  __int64 v70; // [rsp+80h] [rbp-88h]
  int nSavedDC; // [rsp+88h] [rbp-80h]
  _BYTE v72[24]; // [rsp+90h] [rbp-78h] BYREF
  int v73; // [rsp+A8h] [rbp-60h]
  XFORM xf; // [rsp+B0h] [rbp-58h] BYREF

  v12 = a1[5];
  v14 = a1[17];
  *(_QWORD *)&xf.eM11 = a6;
  v70 = a10;
  v68 = a3;
  Hdc = DpContext::GetHdc(v14, v12);
  v17 = Hdc;
  if ( Hdc )
  {
    v18 = SaveDC(Hdc);
    v19 = a1[17];
    nSavedDC = v18;
    if ( v18 )
    {
      DpContext::CleanTheHdc(v19, v17);
      v20 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v21 = 0;
      *(_DWORD *)(a2 + 5240) = 1;
      v22 = (__m128)*a5;
      v22.m128_f32[0] = v22.m128_f32[0] + 0.5;
      if ( v20 )
        v23 = (int)_mm_round_ss(v22, v22, 9).m128_f32[0];
      else
        v23 = (int)floor(v22.m128_f32[0]);
      v24 = (__m128)a5[1];
      x = v23;
      v24.m128_f32[0] = v24.m128_f32[0] + 0.5;
      if ( v20 )
        v25 = (int)_mm_round_ss(v24, v24, 9).m128_f32[0];
      else
        v25 = (int)floor(v24.m128_f32[0]);
      v26 = (__m128)a5[2];
      y = v25;
      v26.m128_f32[0] = v26.m128_f32[0] + 0.5;
      if ( v20 )
        v27 = (int)_mm_round_ss(v26, v26, 9).m128_f32[0];
      else
        v27 = (int)floor(v26.m128_f32[0]);
      v28 = (__m128)a5[3];
      v67[1] = v27;
      v28.m128_f32[0] = v28.m128_f32[0] + 0.5;
      if ( v20 )
        v29 = (int)_mm_round_ss(v28, v28, 9).m128_f32[0];
      else
        v29 = (int)floor(v28.m128_f32[0]);
      v67[0] = v29;
      v30 = **(float **)&xf.eM11;
      v31 = RasterizerCeiling(**(float **)&xf.eM11);
      v32 = *(float *)(*(_QWORD *)&xf.eM11 + 4LL);
      LODWORD(v69) = v31;
      v33 = RasterizerCeiling(v32);
      v34 = v30 + *(float *)(*(_QWORD *)&xf.eM11 + 8LL);
      DWORD1(v69) = v33;
      v35 = RasterizerCeiling(v34);
      v36 = v32 + *(float *)(*(_QWORD *)&xf.eM11 + 12LL);
      DWORD2(v69) = v35;
      HIDWORD(v69) = RasterizerCeiling(v36);
      if ( a8 )
      {
        SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
          (SetupClippingForMetafilePlayback *)v72,
          v17,
          a1[16],
          a1[17],
          v62);
        if ( v73 )
          goto LABEL_20;
        *(_QWORD *)&xf.eM11 = 0;
        v37 = (PointF *)&v64;
        v38 = 2;
        do
        {
          PointF::PointF(v37);
          v37 = (PointF *)((char *)v37 + 8);
          --v38;
        }
        while ( v38 );
        v39 = a4[1];
        *(float *)&v64 = *a4;
        *(_QWORD *)((char *)&v64 + 4) = __PAIR64__(*(float *)&v64 + a4[2], LODWORD(v39));
        *((float *)&v64 + 3) = v39 + a4[3];
        GpMatrix::Transform((GpMatrix *)(a2 + 5256), (struct PointF *)&v64, 2);
        LODWORD(xf.eM11) = RasterizerCeiling(*(float *)&v64);
        LODWORD(v40) = RasterizerCeiling(*((float *)&v64 + 1));
        xf.eM12 = v40;
        LODWORD(v41) = RasterizerCeiling(*((float *)&v64 + 2));
        xf.eM21 = v41;
        LODWORD(xf.eM22) = RasterizerCeiling(*((float *)&v64 + 3));
        eM22 = xf.eM22;
        if ( SLODWORD(v40) >= SLODWORD(xf.eM22) || SLODWORD(xf.eM11) >= SLODWORD(v41) )
          goto LABEL_20;
        if ( (unsigned int)(a7 - 1) <= 1 )
        {
          SetMapMode(v17, 8);
          SetWindowOrgEx(v17, x, y, 0);
          SetWindowExtEx(v17, v67[1], v67[0], 0);
          SetViewportOrgEx(v17, SLODWORD(xf.eM11), SLODWORD(v40), 0);
          SetViewportExtEx(v17, LODWORD(v41) - LODWORD(xf.eM11), LODWORD(eM22) - LODWORD(v40), 0);
          v43 = MetafilePlayer::EnumerateWmfRecords(a2, v17, v68, &xf, &v69);
LABEL_19:
          v21 = v43;
          goto LABEL_20;
        }
        p_xf = &xf;
        if ( a11 )
        {
          LODWORD(xf.eM11) = x;
          v63 = a11;
          LODWORD(xf.eM21) = v67[1] + 1 + x;
          LODWORD(xf.eM12) = y;
          LODWORD(xf.eM22) = v67[0] + 1 + y;
          goto LABEL_40;
        }
      }
      else
      {
        v64 = 0;
        if ( a9 )
        {
          v55 = a1[17];
          *(_QWORD *)&xf.eM11 = 0;
          v21 = 1;
          *(_DWORD *)(a2 + 5336) = *((_DWORD *)v55 + 18);
          DibSection32Bpp = (void *)CreateDibSection32Bpp(v17, a2 + 5336, (GpMatrix *)(a2 + 5256));
          if ( DibSection32Bpp )
          {
            Init32BppDibToTransparent(*(unsigned int **)&xf.eM11, DWORD2(v64) * HIDWORD(v64));
            CompatibleDC = CreateCompatibleDC(0);
            v58 = CompatibleDC;
            if ( CompatibleDC )
            {
              SelectObject(CompatibleDC, DibSection32Bpp);
              if ( (unsigned int)(a7 - 1) <= 1 )
              {
                SetMapMode(v58, 8);
                SetWindowOrgEx(v58, x, y, 0);
                SetWindowExtEx(v58, v67[1], v67[0], 0);
                SetViewportOrgEx(v58, 0, 0, 0);
                SetViewportExtEx(v58, SDWORD2(v64), SHIDWORD(v64), 0);
                v59 = MetafilePlayer::EnumerateWmfRecords(a2, v58, v68, &v64, &v64);
              }
              else
              {
                v59 = MetafilePlayer::EnumerateEmfRecords(a2, v58, v68, &v64, &v64, &EnumEmfDownLevel, 0);
              }
              v21 = v59;
              DeleteDC(v58);
              if ( v21 != 9 )
              {
                v60 = a1[17];
                v61 = *((_DWORD *)v60 + 12);
                if ( v61 == 5 )
                  *((_DWORD *)v60 + 12) = 3;
                GpGraphics::SetWorldTransform(a1, v70);
                v21 = Draw32BppDib(
                        a1,
                        *(_QWORD *)&xf.eM11,
                        DWORD2(v64),
                        HIDWORD(v64),
                        a4,
                        *(_DWORD *)(a2 + 5336),
                        *(_DWORD *)(a2 + 5412) == 0);
                *((_DWORD *)a1[17] + 12) = v61;
              }
            }
            DeleteObject(DibSection32Bpp);
          }
          else if ( !DWORD2(v64) || !HIDWORD(v64) )
          {
            v21 = 0;
          }
          goto LABEL_21;
        }
        v45 = (__m128)*(unsigned int *)a4;
        v46 = v45;
        v46.m128_f32[0] = v45.m128_f32[0] + 0.5;
        if ( v20 )
          v47 = (int)_mm_round_ss(v46, v46, 9).m128_f32[0];
        else
          v47 = (int)floor(v46.m128_f32[0]);
        v48 = (__m128)*((unsigned int *)a4 + 1);
        LODWORD(xf.eM11) = v47;
        v49 = v48;
        LODWORD(v64) = v47;
        v49.m128_f32[0] = v48.m128_f32[0] + 0.5;
        if ( v20 )
          v50 = (int)_mm_round_ss(v49, v49, 9).m128_f32[0];
        else
          v50 = (int)floor(v49.m128_f32[0]);
        LODWORD(v70) = v50;
        DWORD1(v64) = v50;
        v45.m128_f32[0] = (float)(v45.m128_f32[0] + a4[2]) + 0.5;
        if ( v20 )
          v51 = (int)_mm_round_ss(v45, v45, 9).m128_f32[0];
        else
          v51 = (int)floor(v45.m128_f32[0]);
        DWORD2(v64) = v51;
        v48.m128_f32[0] = (float)(v48.m128_f32[0] + a4[3]) + 0.5;
        if ( v20 )
          v52 = (int)_mm_round_ss(v48, v48, 9).m128_f32[0];
        else
          v52 = (int)floor(v48.m128_f32[0]);
        HIDWORD(v64) = v52;
        if ( v52 <= (int)v70 || v51 <= SLODWORD(xf.eM11) )
        {
LABEL_21:
          RestoreDC(v17, nSavedDC);
          DpContext::ReleaseHdc(a1[17], v17, a1[5]);
          return v21;
        }
        SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
          (SetupClippingForMetafilePlayback *)v72,
          v17,
          a1[16],
          a1[17],
          v62);
        if ( v73 )
        {
LABEL_20:
          SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback((SetupClippingForMetafilePlayback *)v72);
          goto LABEL_21;
        }
        if ( a11 )
        {
          *(_QWORD *)&v69 = __PAIR64__(y, x);
          DWORD2(v69) = v67[1] + 1 + x;
          HIDWORD(v69) = v67[0] + 1 + y;
          v64 = 0;
          v43 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v68, &v69, &v64, &EnumEmfDownLevel, a11);
          goto LABEL_19;
        }
        SetGraphicsMode(v17, 2);
        v53 = *(float *)(a2 + 5292);
        *(_OWORD *)&xf.eM11 = *(_OWORD *)(a2 + 5272);
        xf.eDx = *(FLOAT *)(a2 + 5288);
        xf.eDy = v53;
        SetWorldTransform(v17, &xf);
        p_xf = (XFORM *)&v64;
        v69 = 0;
      }
      v63 = 0;
LABEL_40:
      v43 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v68, p_xf, &v69, &EnumEmfDownLevel, v63);
      goto LABEL_19;
    }
    DpContext::ReleaseHdc(v19, v17, a1[5]);
  }
  return 1;
}

```

## disassembly

```asm
0x18004341c  mov     rax, rsp
0x18004341f  push    rbp
0x180043420  push    rbx
0x180043421  push    rsi
0x180043422  push    rdi
0x180043423  push    r12
0x180043425  push    r13
0x180043427  push    r14
0x180043429  push    r15
0x18004342b  lea     rbp, [rax-48h]
0x18004342f  sub     rsp, 108h
0x180043436  movaps  xmmword ptr [rax-58h], xmm6
0x18004343a  movaps  xmmword ptr [rax-68h], xmm7
0x18004343e  movaps  xmmword ptr [rax-78h], xmm8
0x180043443  mov     rax, cs:__security_cookie
0x18004344a  xor     rax, rsp
0x18004344d  mov     [rbp+40h+var_80], rax
0x180043451  mov     rax, [rbp+40h+arg_28]
0x180043455  mov     rsi, rdx
0x180043458  mov     rdx, [rcx+28h]; struct DpBitmap *
0x18004345c  mov     rbx, rcx
0x18004345f  mov     rcx, [rcx+88h]; this
0x180043466  mov     r12, r9
0x180043469  mov     r13, [rbp+40h+arg_20]
0x18004346d  mov     qword ptr [rbp+40h+xf.eM11], rax
0x180043471  mov     rax, [rbp+40h+arg_48]
0x180043478  mov     [rsp+140h+var_C8], rax
0x18004347d  mov     qword ptr [rsp+140h+var_E0], r8
0x180043482  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x180043487  mov     rdi, rax
0x18004348a  test    rax, rax
0x18004348d  jz      loc_180043795
0x180043493  mov     rcx, rax; hdc
0x180043496  call    cs:__imp_SaveDC
0x18004349d  nop     dword ptr [rax+rax+00h]
0x1800434a2  mov     rcx, [rbx+88h]; this
0x1800434a9  mov     rdx, rdi; HDC
0x1800434ac  mov     [rbp+40h+nSavedDC], eax
0x1800434af  test    eax, eax
0x1800434b1  jz      loc_18004378C
0x1800434b7  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x1800434bc  mov     r15b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800434c3  xor     r14d, r14d
0x1800434c6  movss   xmm8, cs:__real@3f000000
0x1800434cf  mov     dword ptr [rsi+1478h], 1
0x1800434d9  movss   xmm1, dword ptr [r13+0]
0x1800434df  addss   xmm1, xmm8
0x1800434e4  test    r15b, r15b
0x1800434e7  jnz     loc_180043966
0x1800434ed  cvtps2pd xmm0, xmm1; X
0x1800434f0  call    floor
0x1800434f5  cvttsd2si eax, xmm0
0x1800434f9  movss   xmm1, dword ptr [r13+4]
0x1800434ff  mov     [rsp+140h+x], eax
0x180043503  addss   xmm1, xmm8
0x180043508  test    r15b, r15b
0x18004350b  jnz     loc_180043978
0x180043511  cvtps2pd xmm0, xmm1; X
0x180043514  call    floor
0x180043519  cvttsd2si eax, xmm0
0x18004351d  movss   xmm1, dword ptr [r13+8]
0x180043523  mov     [rsp+140h+y], eax
0x180043527  addss   xmm1, xmm8
0x18004352c  test    r15b, r15b
0x18004352f  jnz     loc_18004398A
0x180043535  cvtps2pd xmm0, xmm1; X
0x180043538  call    floor
0x18004353d  cvttsd2si eax, xmm0
0x180043541  movss   xmm1, dword ptr [r13+0Ch]
0x180043547  mov     [rsp+140h+var_E8+4], eax
0x18004354b  addss   xmm1, xmm8
0x180043550  test    r15b, r15b
0x180043553  jnz     loc_18004399C
0x180043559  cvtps2pd xmm0, xmm1; X
0x18004355c  call    floor
0x180043561  cvttsd2si eax, xmm0
0x180043565  mov     r13, qword ptr [rbp+40h+xf.eM11]
0x180043569  mov     [rsp+140h+var_E8], eax
0x18004356d  movss   xmm6, dword ptr [r13+0]
0x180043573  movaps  xmm0, xmm6; float
0x180043576  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004357b  movss   xmm7, dword ptr [r13+4]
0x180043581  movaps  xmm0, xmm7; float
0x180043584  mov     dword ptr [rsp+140h+var_E0+8], eax
0x180043588  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004358d  addss   xmm6, dword ptr [r13+8]
0x180043593  mov     dword ptr [rsp+140h+var_E0+0Ch], eax
0x180043597  movaps  xmm0, xmm6; float
0x18004359a  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004359f  addss   xmm7, dword ptr [r13+0Ch]
0x1800435a5  mov     dword ptr [rsp+140h+var_D0], eax
0x1800435a9  movaps  xmm0, xmm7; float
0x1800435ac  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800435b1  xor     r13d, r13d
0x1800435b4  mov     dword ptr [rsp+140h+var_D0+4], eax
0x1800435b8  cmp     [rbp+40h+arg_38], r13d
0x1800435bf  jz      loc_1800437CE
0x1800435c5  mov     r9, [rbx+88h]; struct DpContext *
0x1800435cc  lea     rcx, [rbp+40h+var_B8]; this
0x1800435d0  mov     r8, [rbx+80h]; struct DpDriver *
0x1800435d7  mov     rdx, rdi; HDC
0x1800435da  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x1800435df  cmp     [rbp+40h+var_A0], r13d
0x1800435e3  jnz     loc_180043759
0x1800435e9  mov     qword ptr [rbp+40h+xf.eM11], r13
0x1800435ed  lea     r15, [rsp+140h+var_108+8]
0x1800435f2  mov     r13d, 2
0x1800435f8  mov     rcx, r15; this
0x1800435fb  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180043600  add     r15, 8
0x180043604  sub     r13, 1
0x180043608  jnz     short loc_1800435F8
0x18004360a  movss   xmm0, dword ptr [r12]
0x180043610  lea     rcx, [rsi+1488h]; this
0x180043617  movss   xmm1, dword ptr [r12+4]
0x18004361e  lea     r8d, [r13+2]; int
0x180043622  movss   [rsp+140h+var_108+8], xmm0
0x180043628  lea     rdx, [rsp+140h+var_108+8]; struct PointF *
0x18004362d  addss   xmm0, dword ptr [r12+8]
0x180043634  movss   [rsp+140h+var_108+0Ch], xmm1
0x18004363a  addss   xmm1, dword ptr [r12+0Ch]
0x180043641  movss   [rsp+140h+var_F8], xmm0
0x180043647  movss   [rsp+140h+var_F4], xmm1
0x18004364d  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180043652  movss   xmm0, [rsp+140h+var_108+8]; float
0x180043658  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004365d  movss   xmm0, [rsp+140h+var_108+0Ch]; float
0x180043663  mov     [rbp+40h+xf.eM11], eax
0x180043666  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004366b  movss   xmm0, [rsp+140h+var_F8]; float
0x180043671  mov     r12d, eax
0x180043674  mov     [rbp+40h+xf.eM12], eax
0x180043677  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004367c  movss   xmm0, [rsp+140h+var_F4]; float
0x180043682  mov     r13d, eax
0x180043685  mov     [rbp+40h+xf.eM21], eax
0x180043688  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004368d  mov     [rbp+40h+xf.eM22], eax
0x180043690  mov     r15d, eax
0x180043693  cmp     r12d, eax
0x180043696  jge     loc_180043759
0x18004369c  cmp     [rbp+40h+xf.eM11], r13d
0x1800436a0  jge     loc_180043759
0x1800436a6  mov     eax, [rbp+40h+arg_30]
0x1800436ac  dec     eax
0x1800436ae  cmp     eax, 1
0x1800436b1  ja      loc_180043924
0x1800436b7  mov     edx, 8; iMode
0x1800436bc  mov     rcx, rdi; hdc
0x1800436bf  call    cs:__imp_SetMapMode
0x1800436c6  nop     dword ptr [rax+rax+00h]
0x1800436cb  mov     r8d, [rsp+140h+y]; y
0x1800436d0  xor     r9d, r9d; lppt
0x1800436d3  mov     edx, [rsp+140h+x]; x
0x1800436d7  mov     rcx, rdi; hdc
0x1800436da  call    cs:__imp_SetWindowOrgEx
0x1800436e1  nop     dword ptr [rax+rax+00h]
0x1800436e6  mov     r8d, [rsp+140h+var_E8]; y
0x1800436eb  xor     r9d, r9d; lpsz
0x1800436ee  mov     edx, [rsp+140h+var_E8+4]; x
0x1800436f2  mov     rcx, rdi; hdc
0x1800436f5  call    cs:__imp_SetWindowExtEx
0x1800436fc  nop     dword ptr [rax+rax+00h]
0x180043701  mov     edx, [rbp+40h+xf.eM11]; x
0x180043704  xor     r9d, r9d; lppt
0x180043707  mov     r8d, r12d; y
0x18004370a  mov     rcx, rdi; hdc
0x18004370d  call    cs:__imp_SetViewportOrgEx
0x180043714  nop     dword ptr [rax+rax+00h]
0x180043719  sub     r13d, [rbp+40h+xf.eM11]
0x18004371d  sub     r15d, r12d
0x180043720  mov     r8d, r15d; y
0x180043723  mov     edx, r13d; x
0x180043726  xor     r9d, r9d; lpsz
0x180043729  mov     rcx, rdi; hdc
0x18004372c  call    cs:__imp_SetViewportExtEx
0x180043733  nop     dword ptr [rax+rax+00h]
0x180043738  mov     r8, qword ptr [rsp+140h+var_E0]
0x18004373d  lea     rax, [rsp+140h+var_E0+8]
0x180043742  lea     r9, [rbp+40h+xf]
0x180043746  mov     [rsp+140h+var_120], rax
0x18004374b  mov     rdx, rdi
0x18004374e  mov     rcx, rsi
0x180043751  call    ?EnumerateWmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHMETAFILE__@@PEBUtagRECT@@2@Z; MetafilePlayer::EnumerateWmfRecords(HDC__ *,HMETAFILE__ *,tagRECT const *,tagRECT const *)
0x180043756  mov     r14d, eax
0x180043759  lea     rcx, [rbp+40h+var_B8]; this
0x18004375d  call    ??1SetupClippingForMetafilePlayback@@QEAA@XZ; SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback(void)
0x180043762  mov     edx, [rbp+40h+nSavedDC]; nSavedDC
0x180043765  mov     rcx, rdi; hdc
0x180043768  call    cs:__imp_RestoreDC
0x18004376f  nop     dword ptr [rax+rax+00h]
0x180043774  mov     r8, [rbx+28h]; struct DpBitmap *
0x180043778  mov     rdx, rdi; HDC
0x18004377b  mov     rcx, [rbx+88h]; this
0x180043782  call    ?ReleaseHdc@DpContext@@QEAAXPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::ReleaseHdc(HDC__ *,DpBitmap *)
0x180043787  mov     eax, r14d
0x18004378a  jmp     short loc_18004379A
0x18004378c  mov     r8, [rbx+28h]; struct DpBitmap *
0x180043790  call    ?ReleaseHdc@DpContext@@QEAAXPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::ReleaseHdc(HDC__ *,DpBitmap *)
0x180043795  mov     eax, 1
0x18004379a  mov     rcx, [rbp+40h+var_80]
0x18004379e  xor     rcx, rsp; StackCookie
0x1800437a1  call    __security_check_cookie
0x1800437a6  lea     r11, [rsp+140h+var_38]
0x1800437ae  movaps  xmm6, xmmword ptr [r11-18h]
0x1800437b3  movaps  xmm7, xmmword ptr [r11-28h]
0x1800437b8  movaps  xmm8, xmmword ptr [r11-38h]
0x1800437bd  mov     rsp, r11
0x1800437c0  pop     r15
0x1800437c2  pop     r14
0x1800437c4  pop     r13
0x1800437c6  pop     r12
0x1800437c8  pop     rdi
0x1800437c9  pop     rsi
0x1800437ca  pop     rbx
0x1800437cb  pop     rbp
0x1800437cc  retn
0x1800437ce  xorps   xmm0, xmm0
0x1800437d1  movups  xmmword ptr [rsp+140h+var_108+8], xmm0
0x1800437d6  cmp     [rbp+40h+arg_40], r13d
0x1800437dd  jnz     loc_180043A79
0x1800437e3  movss   xmm7, dword ptr [r12]
0x1800437e9  movaps  xmm1, xmm7
0x1800437ec  addss   xmm1, xmm8
0x1800437f1  test    r15b, r15b
0x1800437f4  jnz     loc_1800439AE
0x1800437fa  cvtps2pd xmm0, xmm1; X
0x1800437fd  call    floor
0x180043802  cvttsd2si eax, xmm0
0x180043806  movss   xmm6, dword ptr [r12+4]
0x18004380d  mov     [rbp+40h+xf.eM11], eax
0x180043810  movaps  xmm1, xmm6
0x180043813  mov     [rsp+140h+var_108+8], eax
0x180043817  addss   xmm1, xmm8
0x18004381c  test    r15b, r15b
0x18004381f  jnz     loc_1800439C0
0x180043825  cvtps2pd xmm0, xmm1; X
0x180043828  call    floor
0x18004382d  cvttsd2si eax, xmm0
0x180043831  mov     dword ptr [rsp+140h+var_C8], eax
0x180043835  mov     [rsp+140h+var_108+0Ch], eax
0x180043839  addss   xmm7, dword ptr [r12+8]
0x180043840  addss   xmm7, xmm8
0x180043845  test    r15b, r15b
0x180043848  jnz     loc_1800439D2
0x18004384e  cvtps2pd xmm0, xmm7; X
0x180043851  call    floor
0x180043856  cvttsd2si r13d, xmm0
0x18004385b  mov     [rsp+140h+var_F8], r13d
0x180043860  addss   xmm6, dword ptr [r12+0Ch]
0x180043867  addss   xmm6, xmm8
0x18004386c  test    r15b, r15b
0x18004386f  jnz     loc_1800439E5
0x180043875  cvtps2pd xmm0, xmm6; X
0x180043878  call    floor
0x18004387d  cvttsd2si eax, xmm0
0x180043881  mov     [rsp+140h+var_F4], eax
0x180043885  cmp     eax, dword ptr [rsp+140h+var_C8]
0x180043889  jle     loc_180043762
0x18004388f  cmp     r13d, [rbp+40h+xf.eM11]
0x180043893  jle     loc_180043762
0x180043899  mov     r9, [rbx+88h]; struct DpContext *
0x1800438a0  lea     rcx, [rbp+40h+var_B8]; this
0x1800438a4  mov     r8, [rbx+80h]; struct DpDriver *
0x1800438ab  mov     rdx, rdi; HDC
0x1800438ae  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x1800438b3  cmp     [rbp+40h+var_A0], r14d
0x1800438b7  jnz     loc_180043759
0x1800438bd  mov     ecx, [rbp+40h+arg_50]
0x1800438c3  test    ecx, ecx
0x1800438c5  jnz     loc_180043A27
0x1800438cb  lea     edx, [rcx+2]; iMode
0x1800438ce  mov     rcx, rdi; hdc
0x1800438d1  call    cs:__imp_SetGraphicsMode
0x1800438d8  nop     dword ptr [rax+rax+00h]
0x1800438dd  movups  xmm0, xmmword ptr [rsi+1498h]
0x1800438e4  lea     rdx, [rbp+40h+xf]; lpxf
0x1800438e8  mov     rcx, rdi; hdc
0x1800438eb  movss   xmm1, dword ptr [rsi+14ACh]
0x1800438f3  movups  xmmword ptr [rbp+40h+xf.eM11], xmm0
0x1800438f7  movss   xmm0, dword ptr [rsi+14A8h]
0x1800438ff  movss   [rbp+40h+xf.eDx], xmm0
0x180043904  movss   [rbp+40h+xf.eDy], xmm1
0x180043909  call    cs:__imp_SetWorldTransform
0x180043910  nop     dword ptr [rax+rax+00h]
0x180043915  xorps   xmm0, xmm0
0x180043918  lea     r9, [rsp+140h+var_108+8]
0x18004391d  movups  [rsp+140h+var_E0+8], xmm0
0x180043922  jmp     short loc_180043936
0x180043924  mov     ecx, [rbp+40h+arg_50]
0x18004392a  lea     r9, [rbp+40h+xf]
0x18004392e  test    ecx, ecx
0x180043930  jnz     loc_1800439F7
0x180043936  mov     [rsp+140h+var_110], r14d
0x18004393b  lea     rax, EnumEmfDownLevel
0x180043942  mov     [rsp+140h+var_118], rax
0x180043947  lea     rax, [rsp+140h+var_E0+8]
0x18004394c  mov     r8, qword ptr [rsp+140h+var_E0]
0x180043951  mov     rdx, rdi
0x180043954  mov     rcx, rsi
  ... truncated ...
```
