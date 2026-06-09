# GpGraphics::EnumEmf(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,RectF const &,MetafileType,int,int,GpMatrix const &,int)

- ea: `0x180005364`
- end: `0x180005bd5`
- name: `?EnumEmf@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@22W4MetafileType@@HHAEBVGpMatrix@@H@Z`
- size: `2161`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005bdc`

## callees

- `0x180005364`
- `0x180019204`
- `0x180019474`
- `0x18003b634`
- `0x18003b718`
- `0x180040ee0`
- `0x18005d7b0`
- `0x18005db38`
- `0x1800a20c0`
- `0x1800d34a4`
- `0x1800d7b6c`
- `0x1800e4fc0`
- `0x1800e9380`
- `0x1800ea080`
- `0x18010b418`
- `0x18010b6b4`
- `0x18010cc4c`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180005906`
- `GDI32!SetWorldTransform` at `0x180005906`
- `GDI32!SetGraphicsMode` at `0x1800058cb`
- `GDI32!SetGraphicsMode` at `0x1800058cb`
- `GDI32!SetViewportExtEx` at `0x180005719`
- `GDI32!SetViewportExtEx` at `0x180005aa3`
- `GDI32!SetViewportExtEx` at `0x180005719`
- `GDI32!SetViewportExtEx` at `0x180005aa3`
- `GDI32!SetViewportOrgEx` at `0x1800056f7`
- `GDI32!SetViewportOrgEx` at `0x180005a85`
- `GDI32!SetViewportOrgEx` at `0x1800056f7`
- `GDI32!SetViewportOrgEx` at `0x180005a85`
- `GDI32!SetWindowExtEx` at `0x1800056dc`
- `GDI32!SetWindowExtEx` at `0x180005a6e`
- `GDI32!SetWindowExtEx` at `0x1800056dc`
- `GDI32!SetWindowExtEx` at `0x180005a6e`
- `GDI32!SetWindowOrgEx` at `0x1800056c1`
- `GDI32!SetWindowOrgEx` at `0x180005a53`
- `GDI32!SetWindowOrgEx` at `0x1800056c1`
- `GDI32!SetWindowOrgEx` at `0x180005a53`
- `GDI32!SetMapMode` at `0x1800056a6`
- `GDI32!SetMapMode` at `0x180005a38`
- `GDI32!SetMapMode` at `0x1800056a6`
- `GDI32!SetMapMode` at `0x180005a38`
- `GDI32!SaveDC` at `0x1800053f1`
- `GDI32!SaveDC` at `0x1800053f1`
- `GDI32!RestoreDC` at `0x180005b7c`
- `GDI32!RestoreDC` at `0x180005b7c`
- `GDI32!DeleteDC` at `0x180005ad4`
- `GDI32!DeleteDC` at `0x180005ad4`
- `GDI32!SelectObject` at `0x1800059de`
- `GDI32!SelectObject` at `0x1800059de`
- `GDI32!CreateCompatibleDC` at `0x1800059be`
- `GDI32!CreateCompatibleDC` at `0x1800059be`
- `GDI32!DeleteObject` at `0x180005b59`
- `GDI32!DeleteObject` at `0x180005b59`

## pseudocode

```c
__int64 __fastcall GpGraphics::EnumEmf(
        struct DpBitmap **a1,
        __int64 a2,
        __int64 a3,
        FLOAT *a4,
        unsigned int *a5,
        unsigned int *a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        int a11)
{
  struct DpBitmap *v12; // rdx
  DpContext *v14; // rcx
  CopyOnWriteBitmap *Hdc; // rax
  int v16; // ebx
  HDC v17; // rdi
  unsigned int v19; // r15d
  int v20; // r12d
  bool v21; // r13
  __m128 v22; // xmm0
  unsigned int *v23; // rax
  __m128 v24; // xmm0
  __m128 v25; // xmm0
  __m128 v26; // xmm0
  int v27; // eax
  float v28; // xmm6_4
  float v29; // xmm7_4
  float v30; // xmm0_4
  FLOAT v31; // xmm1_4
  FLOAT v32; // xmm0_4
  int v33; // r13d
  int v34; // eax
  FLOAT *v35; // r15
  __m128 v36; // xmm7
  __m128 v37; // xmm0
  int v38; // eax
  __m128 v39; // xmm6
  __m128 v40; // xmm0
  int v41; // eax
  int v42; // ecx
  int v43; // eax
  double v44; // xmm0_8
  FLOAT v45; // xmm1_4
  struct DpBitmap *v46; // rax
  HDC CompatibleDC; // rax
  HDC v48; // r13
  int v49; // eax
  unsigned int v50; // r15d
  struct DpBitmap *v51; // rax
  int v52; // r13d
  int v53; // [rsp+28h] [rbp-E0h]
  int v54; // [rsp+38h] [rbp-D0h]
  int v55[4]; // [rsp+48h] [rbp-C0h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-B0h]
  int y; // [rsp+60h] [rbp-A8h]
  int x; // [rsp+64h] [rbp-A4h]
  int v59[2]; // [rsp+68h] [rbp-A0h]
  unsigned int *v60; // [rsp+70h] [rbp-98h]
  FLOAT *v61; // [rsp+78h] [rbp-90h]
  __int64 v62; // [rsp+80h] [rbp-88h]
  __int128 v63; // [rsp+88h] [rbp-80h] BYREF
  int nSavedDC; // [rsp+98h] [rbp-70h]
  _BYTE v65[24]; // [rsp+A0h] [rbp-68h] BYREF
  int v66; // [rsp+B8h] [rbp-50h]
  XFORM xf; // [rsp+C0h] [rbp-48h] BYREF

  v12 = a1[5];
  v14 = a1[17];
  v60 = a6;
  *(_QWORD *)&xf.eM11 = a10;
  v61 = a4;
  v62 = a3;
  h = a5;
  Hdc = DpContext::GetHdc(v14, v12);
  v16 = 0;
  v17 = (HDC)Hdc;
  if ( !Hdc )
    return 1;
  nSavedDC = SaveDC((HDC)Hdc);
  if ( nSavedDC )
  {
    DpContext::CleanTheHdc(a1[17], v17);
    *(_DWORD *)(a2 + 5240) = 1;
    v20 = 0;
    v22 = (__m128)*a5;
    v21 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v22.m128_f32[0] = v22.m128_f32[0] + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      x = (int)_mm_round_ss(v22, v22, 9).m128_f32[0];
    else
      x = (int)floor(v22.m128_f32[0]);
    v23 = (unsigned int *)h;
    v24 = (__m128)*((unsigned int *)h + 1);
    v24.m128_f32[0] = v24.m128_f32[0] + 0.5;
    if ( v21 )
    {
      y = (int)_mm_round_ss(v24, v24, 9).m128_f32[0];
    }
    else
    {
      y = (int)floor(v24.m128_f32[0]);
      v23 = (unsigned int *)h;
    }
    v25 = (__m128)v23[2];
    v25.m128_f32[0] = v25.m128_f32[0] + 0.5;
    if ( v21 )
    {
      v59[1] = (int)_mm_round_ss(v25, v25, 9).m128_f32[0];
    }
    else
    {
      v59[1] = (int)floor(v25.m128_f32[0]);
      v23 = (unsigned int *)h;
    }
    v26 = (__m128)v23[3];
    v26.m128_f32[0] = v26.m128_f32[0] + 0.5;
    if ( v21 )
      v27 = (int)_mm_round_ss(v26, v26, 9).m128_f32[0];
    else
      v27 = (int)floor(v26.m128_f32[0]);
    v59[0] = v27;
    v28 = *(float *)v60;
    LODWORD(v63) = RasterizerCeiling(*(float *)v60);
    v29 = *((float *)v60 + 1);
    DWORD1(v63) = RasterizerCeiling(v29);
    DWORD2(v63) = RasterizerCeiling(v28 + *((float *)v60 + 2));
    HIDWORD(v63) = RasterizerCeiling(v29 + *((float *)v60 + 3));
    if ( a8 )
    {
      SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
        (SetupClippingForMetafilePlayback *)v65,
        v17,
        a1[16],
        a1[17],
        v53);
      if ( v66 )
        goto LABEL_47;
      *(_QWORD *)v55 = 0;
      `vector constructor iterator'(&xf, 8u, 2u, (void *(*)(void *))PointF::PointF);
      v30 = v61[1];
      xf.eM11 = *v61;
      v31 = xf.eM11 + v61[2];
      xf.eM12 = v30;
      v32 = v30 + v61[3];
      xf.eM21 = v31;
      xf.eM22 = v32;
      GpMatrix::Transform((GpMatrix *)(a2 + 5256), (struct PointF *)&xf, 2);
      v55[0] = RasterizerCeiling(xf.eM11);
      v55[1] = RasterizerCeiling(xf.eM12);
      LODWORD(h) = RasterizerCeiling(xf.eM21);
      v55[2] = (int)h;
      v33 = RasterizerCeiling(xf.eM22);
      v55[3] = v33;
      if ( v55[0] >= (int)h || v55[1] >= v33 )
        goto LABEL_47;
      if ( (unsigned int)(a7 - 1) > 1 )
      {
        if ( a11 )
        {
          *(_QWORD *)v55 = __PAIR64__(y, x);
          v54 = a11;
          v55[2] = v59[1] + 1 + x;
          v55[3] = v59[0] + 1 + y;
LABEL_45:
          v34 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v62, v55, &v63, &EnumEmfDownLevel, v54);
          goto LABEL_46;
        }
LABEL_44:
        v54 = 0;
        goto LABEL_45;
      }
      SetMapMode(v17, 8);
      SetWindowOrgEx(v17, x, y, 0);
      SetWindowExtEx(v17, v59[1], v59[0], 0);
      SetViewportOrgEx(v17, v55[0], v55[1], 0);
      SetViewportExtEx(v17, (_DWORD)h - v55[0], v33 - v55[1], 0);
      v34 = MetafilePlayer::EnumerateWmfRecords(a2, v17, v62, v55, &v63);
    }
    else
    {
      *(_OWORD *)v55 = 0;
      if ( a9 )
      {
        v46 = a1[17];
        v60 = 0;
        v20 = 1;
        *(_DWORD *)(a2 + 5336) = *((_DWORD *)v46 + 18);
        h = (HGDIOBJ)CreateDibSection32Bpp(v17, a2 + 5336, (GpMatrix *)(a2 + 5256));
        if ( h )
        {
          Init32BppDibToTransparent(v60, v55[2] * v55[3]);
          CompatibleDC = CreateCompatibleDC(0);
          v48 = CompatibleDC;
          if ( CompatibleDC )
          {
            SelectObject(CompatibleDC, h);
            if ( (unsigned int)(a7 - 1) <= 1 )
            {
              SetMapMode(v48, 8);
              SetWindowOrgEx(v48, x, y, 0);
              SetWindowExtEx(v48, v59[1], v59[0], 0);
              SetViewportOrgEx(v48, 0, 0, 0);
              v50 = v55[3];
              SetViewportExtEx(v48, v55[2], v55[3], 0);
              v49 = MetafilePlayer::EnumerateWmfRecords(a2, v48, v62, v55, v55);
            }
            else
            {
              v49 = MetafilePlayer::EnumerateEmfRecords(a2, v48, v62, v55, v55, &EnumEmfDownLevel, 0);
              v50 = v55[3];
            }
            v20 = v49;
            DeleteDC(v48);
            if ( v20 != 9 )
            {
              v51 = a1[17];
              v52 = *((_DWORD *)v51 + 12);
              if ( v52 == 5 )
                *((_DWORD *)v51 + 12) = 3;
              GpGraphics::SetWorldTransform(a1, *(_QWORD *)&xf.eM11);
              LOBYTE(v16) = *(_DWORD *)(a2 + 5412) == 0;
              v20 = Draw32BppDib(a1, v60, (unsigned int)v55[2], v50, v61, *(_DWORD *)(a2 + 5336), v16);
              *((_DWORD *)a1[17] + 12) = v52;
            }
          }
          DeleteObject(h);
        }
        else if ( !v55[2] || !v55[3] )
        {
          v20 = 0;
        }
        goto LABEL_61;
      }
      v35 = v61;
      v36 = (__m128)*(unsigned int *)v61;
      v37 = v36;
      v37.m128_f32[0] = v36.m128_f32[0] + 0.5;
      if ( v21 )
        v38 = (int)_mm_round_ss(v37, v37, 9).m128_f32[0];
      else
        v38 = (int)floor(v37.m128_f32[0]);
      v39 = (__m128)*((unsigned int *)v61 + 1);
      LODWORD(v60) = v38;
      v40 = v39;
      v55[0] = v38;
      v40.m128_f32[0] = v39.m128_f32[0] + 0.5;
      if ( v21 )
        v41 = (int)_mm_round_ss(v40, v40, 9).m128_f32[0];
      else
        v41 = (int)floor(v40.m128_f32[0]);
      LODWORD(v61) = v41;
      v55[1] = v41;
      v36.m128_f32[0] = (float)(v36.m128_f32[0] + v35[2]) + 0.5;
      if ( v21 )
        v42 = (int)_mm_round_ss(v36, v36, 9).m128_f32[0];
      else
        v42 = (int)floor(v36.m128_f32[0]);
      LODWORD(h) = v42;
      v55[2] = v42;
      v39.m128_f32[0] = (float)(v39.m128_f32[0] + v35[3]) + 0.5;
      if ( v21 )
      {
        v43 = (int)_mm_round_ss(v39, v39, 9).m128_f32[0];
      }
      else
      {
        v44 = floor(v39.m128_f32[0]);
        v42 = (int)h;
        v43 = (int)v44;
      }
      v55[3] = v43;
      if ( v43 <= (int)v61 || v42 <= (int)v60 )
      {
LABEL_61:
        RestoreDC(v17, nSavedDC);
        v19 = v20;
        goto LABEL_62;
      }
      SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
        (SetupClippingForMetafilePlayback *)v65,
        v17,
        a1[16],
        a1[17],
        v53);
      if ( v66 )
      {
LABEL_47:
        SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback((SetupClippingForMetafilePlayback *)v65);
        goto LABEL_61;
      }
      if ( !a11 )
      {
        SetGraphicsMode(v17, 2);
        v45 = *(float *)(a2 + 5292);
        *(_OWORD *)&xf.eM11 = *(_OWORD *)(a2 + 5272);
        xf.eDx = *(FLOAT *)(a2 + 5288);
        xf.eDy = v45;
        SetWorldTransform(v17, &xf);
        v63 = 0;
        goto LABEL_44;
      }
      *(_QWORD *)&v63 = __PAIR64__(y, x);
      DWORD2(v63) = v59[1] + 1 + x;
      HIDWORD(v63) = v59[0] + 1 + y;
      *(_OWORD *)v55 = 0;
      v34 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v62, &v63, v55, &EnumEmfDownLevel, a11);
    }
LABEL_46:
    v20 = v34;
    goto LABEL_47;
  }
  v19 = 1;
LABEL_62:
  DpContext::ReleaseHdc((HWND *)a1[17], v17, a1[5]);
  return v19;
}

```

## disassembly

```asm
0x180005364  mov     rax, rsp
0x180005367  push    rbp
0x180005368  push    rbx
0x180005369  push    rsi
0x18000536a  push    rdi
0x18000536b  push    r12
0x18000536d  push    r13
0x18000536f  push    r14
0x180005371  push    r15
0x180005373  lea     rbp, [rax-58h]
0x180005377  sub     rsp, 118h
0x18000537e  movaps  xmmword ptr [rax-58h], xmm6
0x180005382  movaps  xmmword ptr [rax-68h], xmm7
0x180005386  movaps  xmmword ptr [rax-78h], xmm8
0x18000538b  mov     rax, cs:__security_cookie
0x180005392  xor     rax, rsp
0x180005395  mov     [rbp+50h+var_80], rax
0x180005399  mov     rax, [rbp+50h+arg_28]
0x1800053a0  mov     r14, rdx
0x1800053a3  mov     rdx, [rcx+28h]; struct DpBitmap *
0x1800053a7  mov     rsi, rcx
0x1800053aa  mov     r13, [rbp+50h+arg_20]
0x1800053b1  mov     rcx, [rcx+88h]; this
0x1800053b8  mov     [rsp+150h+var_E8], rax
0x1800053bd  mov     rax, [rbp+50h+arg_48]
0x1800053c4  mov     qword ptr [rbp+50h+xf.eM11], rax
0x1800053c8  mov     [rsp+150h+var_E0], r9
0x1800053cd  mov     [rsp+150h+var_D8], r8
0x1800053d2  mov     [rsp+150h+h], r13
0x1800053d7  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x1800053dc  xor     ebx, ebx
0x1800053de  mov     rdi, rax
0x1800053e1  test    rax, rax
0x1800053e4  jnz     short loc_1800053EE
0x1800053e6  lea     eax, [rdi+1]
0x1800053e9  jmp     loc_180005BA1
0x1800053ee  mov     rcx, rdi; hdc
0x1800053f1  call    cs:__imp_SaveDC
0x1800053f8  nop     dword ptr [rax+rax+00h]
0x1800053fd  mov     [rbp+50h+nSavedDC], eax
0x180005400  test    eax, eax
0x180005402  jnz     short loc_18000540D
0x180005404  lea     r15d, [rax+1]
0x180005408  jmp     loc_180005B8B
0x18000540d  mov     rcx, [rsi+88h]; this
0x180005414  mov     rdx, rdi; HDC
0x180005417  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x18000541c  movss   xmm8, cs:__real@3f000000
0x180005425  mov     r15d, 1
0x18000542b  mov     [r14+1478h], r15d
0x180005432  mov     r12d, ebx
0x180005435  movss   xmm0, dword ptr [r13+0]
0x18000543b  mov     r13b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180005442  addss   xmm0, xmm8
0x180005447  test    r13b, r13b
0x18000544a  jz      short loc_18000545F
0x18000544c  movaps  xmm1, xmm0
0x18000544f  roundss xmm1, xmm1, 9
0x180005455  cvttss2si ecx, xmm1
0x180005459  mov     [rsp+150h+x], ecx
0x18000545d  jmp     short loc_18000546F
0x18000545f  cvtps2pd xmm0, xmm0; X
0x180005462  call    floor
0x180005467  cvttsd2si eax, xmm0
0x18000546b  mov     [rsp+150h+x], eax
0x18000546f  mov     rax, [rsp+150h+h]
0x180005474  movss   xmm0, dword ptr [rax+4]
0x180005479  addss   xmm0, xmm8
0x18000547e  test    r13b, r13b
0x180005481  jz      short loc_180005496
0x180005483  movaps  xmm1, xmm0
0x180005486  roundss xmm1, xmm1, 9
0x18000548c  cvttss2si ecx, xmm1
0x180005490  mov     [rsp+150h+y], ecx
0x180005494  jmp     short loc_1800054AB
0x180005496  cvtps2pd xmm0, xmm0; X
0x180005499  call    floor
0x18000549e  cvttsd2si eax, xmm0
0x1800054a2  mov     [rsp+150h+y], eax
0x1800054a6  mov     rax, [rsp+150h+h]
0x1800054ab  movss   xmm0, dword ptr [rax+8]
0x1800054b0  addss   xmm0, xmm8
0x1800054b5  test    r13b, r13b
0x1800054b8  jz      short loc_1800054CD
0x1800054ba  movaps  xmm1, xmm0
0x1800054bd  roundss xmm1, xmm1, 9
0x1800054c3  cvttss2si ecx, xmm1
0x1800054c7  mov     [rsp+150h+var_F0+4], ecx
0x1800054cb  jmp     short loc_1800054E2
0x1800054cd  cvtps2pd xmm0, xmm0; X
0x1800054d0  call    floor
0x1800054d5  cvttsd2si eax, xmm0
0x1800054d9  mov     [rsp+150h+var_F0+4], eax
0x1800054dd  mov     rax, [rsp+150h+h]
0x1800054e2  movss   xmm0, dword ptr [rax+0Ch]
0x1800054e7  addss   xmm0, xmm8
0x1800054ec  test    r13b, r13b
0x1800054ef  jz      short loc_180005500
0x1800054f1  movaps  xmm1, xmm0
0x1800054f4  roundss xmm1, xmm1, 9
0x1800054fa  cvttss2si eax, xmm1
0x1800054fe  jmp     short loc_18000550C
0x180005500  cvtps2pd xmm0, xmm0; X
0x180005503  call    floor
0x180005508  cvttsd2si eax, xmm0
0x18000550c  mov     [rsp+150h+var_F0], eax
0x180005510  mov     rax, [rsp+150h+var_E8]
0x180005515  movss   xmm6, dword ptr [rax]
0x180005519  movaps  xmm0, xmm6; float
0x18000551c  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180005521  mov     dword ptr [rbp+50h+var_D0], eax
0x180005524  mov     rax, [rsp+150h+var_E8]
0x180005529  movss   xmm7, dword ptr [rax+4]
0x18000552e  movaps  xmm0, xmm7; float
0x180005531  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180005536  mov     dword ptr [rbp+50h+var_D0+4], eax
0x180005539  mov     rax, [rsp+150h+var_E8]
0x18000553e  addss   xmm6, dword ptr [rax+8]
0x180005543  movaps  xmm0, xmm6; float
0x180005546  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000554b  mov     dword ptr [rbp+50h+var_D0+8], eax
0x18000554e  mov     rax, [rsp+150h+var_E8]
0x180005553  addss   xmm7, dword ptr [rax+0Ch]
0x180005558  movaps  xmm0, xmm7; float
0x18000555b  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180005560  mov     dword ptr [rbp+50h+var_D0+0Ch], eax
0x180005563  cmp     [rbp+50h+arg_38], ebx
0x180005569  jz      loc_180005748
0x18000556f  mov     r9, [rsi+88h]; struct DpContext *
0x180005576  lea     rcx, [rbp+50h+var_B8]; this
0x18000557a  mov     r8, [rsi+80h]; struct DpDriver *
0x180005581  mov     rdx, rdi; HDC
0x180005584  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x180005589  cmp     [rbp+50h+var_A0], ebx
0x18000558c  jnz     loc_18000594A
0x180005592  mov     edx, 8; unsigned __int64
0x180005597  mov     qword ptr [rsp+150h+var_118+8], rbx
0x18000559c  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1800055a3  lea     rcx, [rbp+50h+xf]; void *
0x1800055a7  lea     r8d, [rdx-6]; unsigned __int64
0x1800055ab  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800055b0  mov     rax, [rsp+150h+var_E0]
0x1800055b5  lea     rcx, [r14+1488h]; this
0x1800055bc  mov     r8d, 2; int
0x1800055c2  lea     rdx, [rbp+50h+xf]; struct PointF *
0x1800055c6  movss   xmm1, dword ptr [rax]
0x1800055ca  movss   xmm0, dword ptr [rax+4]
0x1800055cf  movss   [rbp+50h+xf.eM11], xmm1
0x1800055d4  addss   xmm1, dword ptr [rax+8]
0x1800055d9  movss   [rbp+50h+xf.eM12], xmm0
0x1800055de  addss   xmm0, dword ptr [rax+0Ch]
0x1800055e3  movss   [rbp+50h+xf.eM21], xmm1
0x1800055e8  movss   [rbp+50h+xf.eM22], xmm0
0x1800055ed  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x1800055f2  movss   xmm0, [rbp+50h+xf.eM11]; float
0x1800055f7  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800055fc  movss   xmm0, [rbp+50h+xf.eM12]; float
0x180005601  mov     [rsp+150h+var_118+8], eax
0x180005605  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000560a  movss   xmm0, [rbp+50h+xf.eM21]; float
0x18000560f  mov     [rsp+150h+var_118+0Ch], eax
0x180005613  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180005618  movss   xmm0, [rbp+50h+xf.eM22]; float
0x18000561d  mov     dword ptr [rsp+150h+h], eax
0x180005621  mov     [rsp+150h+var_108], eax
0x180005625  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000562a  mov     r13d, eax
0x18000562d  mov     [rsp+150h+var_108+4], eax
0x180005631  mov     eax, [rsp+150h+var_118+8]
0x180005635  cmp     eax, dword ptr [rsp+150h+h]
0x180005639  jge     loc_18000594A
0x18000563f  cmp     [rsp+150h+var_118+0Ch], r13d
0x180005644  jge     loc_18000594A
0x18000564a  mov     eax, [rbp+50h+arg_30]
0x180005650  dec     eax
0x180005652  cmp     eax, r15d
0x180005655  jbe     short loc_18000569E
0x180005657  mov     ecx, [rbp+50h+arg_50]
0x18000565d  lea     r9, [rsp+150h+var_118+8]
0x180005662  test    ecx, ecx
0x180005664  jz      loc_18000591E
0x18000566a  mov     eax, [rsp+150h+x]
0x18000566e  mov     edx, [rsp+150h+var_F0+4]
0x180005672  mov     r8d, [rsp+150h+var_F0]
0x180005677  inc     edx
0x180005679  mov     [rsp+150h+var_118+8], eax
0x18000567d  inc     r8d
0x180005680  add     eax, edx
0x180005682  mov     [rsp+150h+var_120], ecx
0x180005686  mov     [rsp+150h+var_108], eax
0x18000568a  mov     eax, [rsp+150h+y]
0x18000568e  mov     [rsp+150h+var_118+0Ch], eax
0x180005692  add     eax, r8d
0x180005695  mov     [rsp+150h+var_108+4], eax
0x180005699  jmp     loc_180005922
0x18000569e  mov     edx, 8; iMode
0x1800056a3  mov     rcx, rdi; hdc
0x1800056a6  call    cs:__imp_SetMapMode
0x1800056ad  nop     dword ptr [rax+rax+00h]
0x1800056b2  mov     r8d, [rsp+150h+y]; y
0x1800056b7  xor     r9d, r9d; lppt
0x1800056ba  mov     edx, [rsp+150h+x]; x
0x1800056be  mov     rcx, rdi; hdc
0x1800056c1  call    cs:__imp_SetWindowOrgEx
0x1800056c8  nop     dword ptr [rax+rax+00h]
0x1800056cd  mov     r8d, [rsp+150h+var_F0]; y
0x1800056d2  xor     r9d, r9d; lpsz
0x1800056d5  mov     edx, [rsp+150h+var_F0+4]; x
0x1800056d9  mov     rcx, rdi; hdc
0x1800056dc  call    cs:__imp_SetWindowExtEx
0x1800056e3  nop     dword ptr [rax+rax+00h]
0x1800056e8  mov     r8d, [rsp+150h+var_118+0Ch]; y
0x1800056ed  xor     r9d, r9d; lppt
0x1800056f0  mov     edx, [rsp+150h+var_118+8]; x
0x1800056f4  mov     rcx, rdi; hdc
0x1800056f7  call    cs:__imp_SetViewportOrgEx
0x1800056fe  nop     dword ptr [rax+rax+00h]
0x180005703  mov     edx, dword ptr [rsp+150h+h]
0x180005707  xor     r9d, r9d; lpsz
0x18000570a  sub     r13d, [rsp+150h+var_118+0Ch]
0x18000570f  mov     rcx, rdi; hdc
0x180005712  sub     edx, [rsp+150h+var_118+8]; x
0x180005716  mov     r8d, r13d; y
0x180005719  call    cs:__imp_SetViewportExtEx
0x180005720  nop     dword ptr [rax+rax+00h]
0x180005725  mov     r8, [rsp+150h+var_D8]
0x18000572a  lea     rax, [rbp+50h+var_D0]
0x18000572e  lea     r9, [rsp+150h+var_118+8]
0x180005733  mov     [rsp+150h+var_130], rax
0x180005738  mov     rdx, rdi
0x18000573b  mov     rcx, r14
0x18000573e  call    ?EnumerateWmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHMETAFILE__@@PEBUtagRECT@@2@Z; MetafilePlayer::EnumerateWmfRecords(HDC__ *,HMETAFILE__ *,tagRECT const *,tagRECT const *)
0x180005743  jmp     loc_180005947
0x180005748  xorps   xmm0, xmm0
0x18000574b  movups  xmmword ptr [rsp+150h+var_118+8], xmm0
0x180005750  cmp     [rbp+50h+arg_40], ebx
0x180005756  jnz     loc_180005958
0x18000575c  mov     r15, [rsp+150h+var_E0]
0x180005761  movss   xmm7, dword ptr [r15]
0x180005766  movaps  xmm0, xmm7
0x180005769  addss   xmm0, xmm8
0x18000576e  test    r13b, r13b
0x180005771  jz      short loc_180005782
0x180005773  movaps  xmm1, xmm0
0x180005776  roundss xmm1, xmm1, 9
0x18000577c  cvttss2si eax, xmm1
0x180005780  jmp     short loc_18000578E
0x180005782  cvtps2pd xmm0, xmm0; X
0x180005785  call    floor
0x18000578a  cvttsd2si eax, xmm0
0x18000578e  movss   xmm6, dword ptr [r15+4]
0x180005794  mov     dword ptr [rsp+150h+var_E8], eax
0x180005798  movaps  xmm0, xmm6
0x18000579b  mov     [rsp+150h+var_118+8], eax
0x18000579f  addss   xmm0, xmm8
0x1800057a4  test    r13b, r13b
0x1800057a7  jz      short loc_1800057B8
0x1800057a9  movaps  xmm1, xmm0
0x1800057ac  roundss xmm1, xmm1, 9
0x1800057b2  cvttss2si eax, xmm1
0x1800057b6  jmp     short loc_1800057C4
0x1800057b8  cvtps2pd xmm0, xmm0; X
0x1800057bb  call    floor
0x1800057c0  cvttsd2si eax, xmm0
0x1800057c4  mov     dword ptr [rsp+150h+var_E0], eax
0x1800057c8  mov     [rsp+150h+var_118+0Ch], eax
0x1800057cc  addss   xmm7, dword ptr [r15+8]
0x1800057d2  addss   xmm7, xmm8
0x1800057d7  test    r13b, r13b
0x1800057da  jz      short loc_1800057EE
0x1800057dc  movaps  xmm0, xmm7
0x1800057df  movaps  xmm1, xmm0
0x1800057e2  roundss xmm1, xmm1, 9
0x1800057e8  cvttss2si ecx, xmm1
0x1800057ec  jmp     short loc_1800057FA
0x1800057ee  cvtps2pd xmm0, xmm7; X
0x1800057f1  call    floor
0x1800057f6  cvttsd2si ecx, xmm0
0x1800057fa  mov     dword ptr [rsp+150h+h], ecx
0x1800057fe  mov     [rsp+150h+var_108], ecx
0x180005802  addss   xmm6, dword ptr [r15+0Ch]
0x180005808  addss   xmm6, xmm8
0x18000580d  test    r13b, r13b
0x180005810  jz      short loc_180005824
0x180005812  movaps  xmm0, xmm6
0x180005815  movaps  xmm1, xmm0
0x180005818  roundss xmm1, xmm1, 9
0x18000581e  cvttss2si eax, xmm1
0x180005822  jmp     short loc_180005834
0x180005824  cvtps2pd xmm0, xmm6; X
0x180005827  call    floor
0x18000582c  mov     ecx, dword ptr [rsp+150h+h]
0x180005830  cvttsd2si eax, xmm0
0x180005834  mov     [rsp+150h+var_108+4], eax
0x180005838  cmp     eax, dword ptr [rsp+150h+var_E0]
0x18000583c  jle     loc_180005B76
0x180005842  cmp     ecx, dword ptr [rsp+150h+var_E8]
0x180005846  jle     loc_180005B76
0x18000584c  mov     r9, [rsi+88h]; struct DpContext *
0x180005853  lea     rcx, [rbp+50h+var_B8]; this
  ... truncated ...
```
