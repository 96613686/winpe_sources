# GpGraphics::EnumEmfPlusDual(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,int,int)

- ea: `0x180007458`
- end: `0x1800079e1`
- name: `?EnumEmfPlusDual@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@2HH@Z`
- size: `1417`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005bdc`

## callees

- `0x180007458`
- `0x1800089fc`
- `0x18000930c`
- `0x180019204`
- `0x18003b634`
- `0x18003b718`
- `0x180040ee0`
- `0x180048ac0`
- `0x18005d7b0`
- `0x1800a20c0`
- `0x1800a82a4`
- `0x1800d34a4`
- `0x1800d7ab0`
- `0x1800d7b6c`
- `0x1800e9380`
- `0x1800ea080`
- `0x18010b418`

## import_xrefs

- `USER32!ReleaseDC` at `0x180007958`
- `USER32!ReleaseDC` at `0x180007958`
- `GDI32!SetWorldTransform` at `0x1800077d4`
- `GDI32!SetWorldTransform` at `0x1800077d4`
- `GDI32!SetGraphicsMode` at `0x1800077a5`
- `GDI32!SetGraphicsMode` at `0x1800077a5`
- `GDI32!SaveDC` at `0x18000753b`
- `GDI32!SaveDC` at `0x18000753b`
- `GDI32!RestoreDC` at `0x18000798a`
- `GDI32!RestoreDC` at `0x18000798a`
- `GDI32!DeleteDC` at `0x1800078f6`
- `GDI32!DeleteDC` at `0x1800078f6`
- `GDI32!SelectObject` at `0x1800078b4`
- `GDI32!SelectObject` at `0x1800078b4`
- `GDI32!CreateCompatibleDC` at `0x180007867`
- `GDI32!CreateCompatibleDC` at `0x180007867`
- `GDI32!DeleteObject` at `0x18000790d`
- `GDI32!DeleteObject` at `0x18000790d`

## pseudocode

```c
__int64 __fastcall GpGraphics::EnumEmfPlusDual(
        struct DpBitmap **a1,
        __int64 a2,
        __int64 a3,
        float *a4,
        float *a5,
        int a6,
        int a7)
{
  struct DpBitmap *v7; // rax
  __int64 v9; // rcx
  unsigned int v10; // r13d
  HWND v13; // rsi
  HDC CleanHdc; // rsi
  DpContext *v16; // rcx
  int v17; // eax
  DpContext *v18; // rcx
  float v19; // xmm6_4
  FLOAT v20; // eax
  float v21; // xmm7_4
  FLOAT v22; // eax
  float v23; // xmm6_4
  FLOAT v24; // eax
  float v25; // xmm7_4
  PointF *v26; // rbx
  __int64 v27; // rdi
  float v28; // xmm0_4
  float v29; // xmm1_4
  float v30; // xmm0_4
  int v31; // edi
  int v32; // r12d
  int v33; // ebx
  int v34; // eax
  unsigned int v35; // eax
  __m128 v36; // xmm6
  bool v37; // bl
  __m128 v38; // xmm0
  float v39; // eax
  __m128 v40; // xmm7
  __m128 v41; // xmm0
  int v42; // eax
  int v43; // edi
  int v44; // eax
  FLOAT v45; // xmm1_4
  struct DpBitmap *v46; // rax
  void *DibSection32Bpp; // rdi
  HDC CompatibleDC; // rax
  HDC v49; // rbx
  HWND v50; // rbx
  int v51; // [rsp+28h] [rbp-C1h]
  float v52; // [rsp+48h] [rbp-A1h] BYREF
  float v53; // [rsp+4Ch] [rbp-9Dh]
  float v54; // [rsp+50h] [rbp-99h]
  float v55; // [rsp+54h] [rbp-95h]
  int v56; // [rsp+58h] [rbp-91h]
  int nSavedDC; // [rsp+5Ch] [rbp-8Dh]
  __int64 v58; // [rsp+60h] [rbp-89h]
  __int64 v59; // [rsp+68h] [rbp-81h]
  __int128 v60; // [rsp+70h] [rbp-79h] BYREF
  HWND hWnd; // [rsp+80h] [rbp-69h]
  _BYTE v62[24]; // [rsp+88h] [rbp-61h] BYREF
  int v63; // [rsp+A0h] [rbp-49h]
  XFORM xf; // [rsp+A8h] [rbp-41h] BYREF

  v7 = a1[17];
  v9 = (__int64)a1[5];
  v10 = 0;
  nSavedDC = -1;
  v13 = (HWND)*((_QWORD *)v7 + 79);
  LODWORD(v58) = 0;
  hWnd = v13;
  v59 = a3;
  DpBitmap::Flush(v9);
  if ( v13 )
  {
    CleanHdc = GetCleanHdc(v13);
    if ( !CleanHdc )
      return 7;
    *((_QWORD *)a1[17] + 79) = 0;
    *((_QWORD *)a1[17] + 78) = CleanHdc;
  }
  else
  {
    v16 = a1[17];
    CleanHdc = (HDC)*((_QWORD *)v16 + 78);
    if ( CleanHdc )
    {
      DpContext::ResetHdc(v16);
    }
    else
    {
      CleanHdc = (HDC)DpContext::GetHdc(v16, a1[5]);
      if ( !CleanHdc )
        return 2;
      LODWORD(v58) = 1;
    }
    v17 = SaveDC(CleanHdc);
    v18 = a1[17];
    nSavedDC = v17;
    DpContext::CleanTheHdc(v18, CleanHdc);
  }
  SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
    (SetupClippingForMetafilePlayback *)v62,
    CleanHdc,
    a1[16],
    a1[17],
    v51);
  if ( !v63 )
  {
    v19 = *a5;
    LODWORD(v20) = RasterizerCeiling(*a5);
    v21 = a5[1];
    xf.eM11 = v20;
    LODWORD(v22) = RasterizerCeiling(v21);
    v23 = v19 + a5[2];
    xf.eM12 = v22;
    LODWORD(v24) = RasterizerCeiling(v23);
    v25 = v21 + a5[3];
    xf.eM21 = v24;
    LODWORD(xf.eM22) = RasterizerCeiling(v25);
    if ( !a6 )
    {
      v36 = (__m128)*(unsigned int *)a4;
      v37 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v38 = v36;
      v38.m128_f32[0] = v36.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        LODWORD(v39) = (int)_mm_round_ss(v38, v38, 9).m128_f32[0];
      else
        LODWORD(v39) = (int)floor(v38.m128_f32[0]);
      v40 = (__m128)*((unsigned int *)a4 + 1);
      xf.eM11 = v39;
      v41 = v40;
      v52 = v39;
      v41.m128_f32[0] = v40.m128_f32[0] + 0.5;
      if ( v37 )
        v42 = (int)_mm_round_ss(v41, v41, 9).m128_f32[0];
      else
        v42 = (int)floor(v41.m128_f32[0]);
      v56 = v42;
      LODWORD(v53) = v42;
      v36.m128_f32[0] = (float)(v36.m128_f32[0] + a4[2]) + 0.5;
      if ( v37 )
        v43 = (int)_mm_round_ss(v36, v36, 9).m128_f32[0];
      else
        v43 = (int)floor(v36.m128_f32[0]);
      LODWORD(v54) = v43;
      v40.m128_f32[0] = (float)(v40.m128_f32[0] + a4[3]) + 0.5;
      if ( v37 )
        v44 = (int)_mm_round_ss(v40, v40, 9).m128_f32[0];
      else
        v44 = (int)floor(v40.m128_f32[0]);
      LODWORD(v55) = v44;
      if ( v44 <= v56 || v43 <= SLODWORD(xf.eM11) )
        goto LABEL_42;
      if ( a7 )
      {
        v46 = a1[17];
        *(_QWORD *)&xf.eM11 = 0;
        *(_DWORD *)(a2 + 5336) = *((_DWORD *)v46 + 18);
        DibSection32Bpp = (void *)CreateDibSection32Bpp(CleanHdc, a2 + 5336, (GpMatrix *)(a2 + 5256));
        v10 = 1;
        if ( DibSection32Bpp )
        {
          CompatibleDC = CreateCompatibleDC(0);
          v49 = CompatibleDC;
          if ( CompatibleDC )
          {
            *(_QWORD *)(a2 + 5304) = *(_QWORD *)&xf.eM11;
            *(float *)(a2 + 5312) = v54;
            *(float *)(a2 + 5316) = v55;
            *(_OWORD *)(a2 + 5320) = *(_OWORD *)a4;
            SelectObject(CompatibleDC, DibSection32Bpp);
            v10 = MetafilePlayer::EnumerateEmfRecords(a2, v49, v59, &v52, &v52, &EnumEmfWithDownLevel, 0);
            DeleteDC(v49);
            *(_QWORD *)(a2 + 5304) = 0;
          }
          DeleteObject(DibSection32Bpp);
        }
        else if ( !LODWORD(v54) || !LODWORD(v55) )
        {
          v10 = 0;
        }
        goto LABEL_42;
      }
      SetGraphicsMode(CleanHdc, 2);
      v45 = *(float *)(a2 + 5292);
      *(_OWORD *)&xf.eM11 = *(_OWORD *)(a2 + 5272);
      xf.eDx = *(FLOAT *)(a2 + 5288);
      xf.eDy = v45;
      SetWorldTransform(CleanHdc, &xf);
      v60 = 0;
      v35 = MetafilePlayer::EnumerateEmfRecords(a2, CleanHdc, v59, &v52, &v60, &EnumEmfWithDownLevel, 0);
      goto LABEL_34;
    }
    v26 = (PointF *)&v52;
    v27 = 2;
    do
    {
      PointF::PointF(v26);
      v26 = (PointF *)((char *)v26 + 8);
      --v27;
    }
    while ( v27 );
    v28 = a4[1];
    v52 = *a4;
    v29 = v52 + a4[2];
    v53 = v28;
    v30 = v28 + a4[3];
    v54 = v29;
    v55 = v30;
    GpMatrix::Transform((GpMatrix *)(a2 + 5256), (struct PointF *)&v52, 2);
    v31 = RasterizerCeiling(v52);
    LODWORD(v60) = v31;
    v32 = RasterizerCeiling(v53);
    DWORD1(v60) = v32;
    v33 = RasterizerCeiling(v54);
    DWORD2(v60) = v33;
    v34 = RasterizerCeiling(v55);
    HIDWORD(v60) = v34;
    if ( v31 < v33 && v32 < v34 )
    {
      v35 = MetafilePlayer::EnumerateEmfRecords(a2, CleanHdc, v59, &v60, &xf, &EnumEmfWithDownLevel, 0);
LABEL_34:
      v10 = v35;
    }
  }
LABEL_42:
  SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback((SetupClippingForMetafilePlayback *)v62);
  MetafilePlayer::DoneWithDownLevel((MetafilePlayer *)a2);
  DpContext::ResetHdc(a1[17]);
  v50 = hWnd;
  if ( hWnd )
  {
    ReleaseDC(hWnd, CleanHdc);
    *((_QWORD *)a1[17] + 79) = v50;
    *((_QWORD *)a1[17] + 78) = 0;
  }
  else
  {
    RestoreDC(CleanHdc, nSavedDC);
    if ( (_DWORD)v58 )
      DpContext::ReleaseHdc((HWND *)a1[17], CleanHdc, 0);
  }
  return v10;
}

```

## disassembly

```asm
0x180007458  mov     rax, rsp
0x18000745b  push    rbp
0x18000745c  push    rbx
0x18000745d  push    rsi
0x18000745e  push    rdi
0x18000745f  push    r12
0x180007461  push    r13
0x180007463  push    r14
0x180007465  push    r15
0x180007467  lea     rbp, [rax-47h]
0x18000746b  sub     rsp, 0E8h
0x180007472  movaps  xmmword ptr [rax-58h], xmm6
0x180007476  movaps  xmmword ptr [rax-68h], xmm7
0x18000747a  mov     rax, cs:__security_cookie
0x180007481  xor     rax, rsp
0x180007484  mov     [rbp+3Fh+var_68], rax
0x180007488  mov     rax, [rcx+88h]
0x18000748f  mov     r14, rcx
0x180007492  mov     rcx, [rcx+28h]
0x180007496  xor     r13d, r13d
0x180007499  mov     rbx, [rbp+3Fh+arg_20]
0x18000749d  mov     r12, r9
0x1800074a0  or      [rsp+120h+nSavedDC], 0FFFFFFFFh
0x1800074a5  mov     r15, rdx
0x1800074a8  mov     rsi, [rax+278h]
0x1800074af  and     dword ptr [rsp+120h+var_C8], r13d
0x1800074b4  mov     [rbp+3Fh+hWnd], rsi
0x1800074b8  mov     [rsp+120h+var_C0], r8
0x1800074bd  call    ?Flush@DpBitmap@@QEAAXW4FlushIntention@@@Z; DpBitmap::Flush(FlushIntention)
0x1800074c2  test    rsi, rsi
0x1800074c5  jz      short loc_1800074FD
0x1800074c7  mov     rcx, rsi; hWnd
0x1800074ca  call    ?GetCleanHdc@@YAPEAUHDC__@@PEAUHWND__@@@Z; GetCleanHdc(HWND__ *)
0x1800074cf  mov     rsi, rax
0x1800074d2  test    rax, rax
0x1800074d5  jnz     short loc_1800074DF
0x1800074d7  lea     eax, [rsi+7]
0x1800074da  jmp     loc_1800079B2
0x1800074df  mov     rax, [r14+88h]
0x1800074e6  and     [rax+278h], r13
0x1800074ed  mov     rax, [r14+88h]
0x1800074f4  mov     [rax+270h], rsi
0x1800074fb  jmp     short loc_18000755A
0x1800074fd  mov     rcx, [r14+88h]; this
0x180007504  mov     rsi, [rcx+270h]
0x18000750b  test    rsi, rsi
0x18000750e  jz      short loc_180007517
0x180007510  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x180007515  jmp     short loc_180007538
0x180007517  mov     rdx, [r14+28h]; struct DpBitmap *
0x18000751b  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x180007520  mov     rsi, rax
0x180007523  test    rax, rax
0x180007526  jnz     short loc_180007530
0x180007528  lea     eax, [rsi+2]
0x18000752b  jmp     loc_1800079B2
0x180007530  mov     dword ptr [rsp+120h+var_C8], 1
0x180007538  mov     rcx, rsi; hdc
0x18000753b  call    cs:__imp_SaveDC
0x180007542  nop     dword ptr [rax+rax+00h]
0x180007547  mov     rcx, [r14+88h]; this
0x18000754e  mov     rdx, rsi; HDC
0x180007551  mov     [rsp+120h+nSavedDC], eax
0x180007555  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x18000755a  mov     r9, [r14+88h]; struct DpContext *
0x180007561  lea     rcx, [rbp+3Fh+var_A0]; this
0x180007565  mov     r8, [r14+80h]; struct DpDriver *
0x18000756c  mov     rdx, rsi; HDC
0x18000756f  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x180007574  cmp     [rbp+3Fh+var_88], r13d
0x180007578  jnz     loc_18000792C
0x18000757e  movss   xmm6, dword ptr [rbx]
0x180007582  movaps  xmm0, xmm6; float
0x180007585  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000758a  movss   xmm7, dword ptr [rbx+4]
0x18000758f  movaps  xmm0, xmm7; float
0x180007592  mov     [rbp+3Fh+xf.eM11], eax
0x180007595  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000759a  addss   xmm6, dword ptr [rbx+8]
0x18000759f  mov     [rbp+3Fh+xf.eM12], eax
0x1800075a2  movaps  xmm0, xmm6; float
0x1800075a5  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800075aa  addss   xmm7, dword ptr [rbx+0Ch]
0x1800075af  mov     [rbp+3Fh+xf.eM21], eax
0x1800075b2  movaps  xmm0, xmm7; float
0x1800075b5  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800075ba  mov     [rbp+3Fh+xf.eM22], eax
0x1800075bd  cmp     [rbp+3Fh+arg_28], r13d
0x1800075c1  jz      loc_180007699
0x1800075c7  lea     rbx, [rsp+120h+var_E0]
0x1800075cc  mov     edi, 2
0x1800075d1  mov     rcx, rbx; this
0x1800075d4  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x1800075d9  add     rbx, 8
0x1800075dd  sub     rdi, 1
0x1800075e1  jnz     short loc_1800075D1
0x1800075e3  movss   xmm1, dword ptr [r12]
0x1800075e9  lea     rcx, [r15+1488h]; this
0x1800075f0  movss   xmm0, dword ptr [r12+4]
0x1800075f7  lea     r8d, [rdi+2]; int
0x1800075fb  movss   [rsp+120h+var_E0], xmm1
0x180007601  lea     rdx, [rsp+120h+var_E0]; struct PointF *
0x180007606  addss   xmm1, dword ptr [r12+8]
0x18000760d  movss   [rsp+120h+var_DC], xmm0
0x180007613  addss   xmm0, dword ptr [r12+0Ch]
0x18000761a  movss   [rsp+120h+var_D8], xmm1
0x180007620  movss   [rsp+120h+var_D4], xmm0
0x180007626  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x18000762b  movss   xmm0, [rsp+120h+var_E0]; float
0x180007631  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180007636  movss   xmm0, [rsp+120h+var_DC]; float
0x18000763c  mov     edi, eax
0x18000763e  mov     dword ptr [rbp+3Fh+var_B8], eax
0x180007641  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180007646  movss   xmm0, [rsp+120h+var_D8]; float
0x18000764c  mov     r12d, eax
0x18000764f  mov     dword ptr [rbp+3Fh+var_B8+4], eax
0x180007652  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180007657  movss   xmm0, [rsp+120h+var_D4]; float
0x18000765d  mov     ebx, eax
0x18000765f  mov     dword ptr [rbp+3Fh+var_B8+8], eax
0x180007662  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180007667  mov     dword ptr [rbp+3Fh+var_B8+0Ch], eax
0x18000766a  cmp     edi, ebx
0x18000766c  jge     loc_18000792C
0x180007672  cmp     r12d, eax
0x180007675  jge     loc_18000792C
0x18000767b  and     [rsp+120h+var_F0], r13d
0x180007680  lea     rax, EnumEmfWithDownLevel
0x180007687  mov     [rsp+120h+var_F8], rax
0x18000768c  lea     r9, [rbp+3Fh+var_B8]
0x180007690  lea     rax, [rbp+3Fh+xf]
0x180007694  jmp     loc_180007801
0x180007699  movss   xmm6, dword ptr [r12]
0x18000769f  mov     bl, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800076a5  movaps  xmm0, xmm6
0x1800076a8  addss   xmm0, cs:__real@3f000000
0x1800076b0  test    bl, bl
0x1800076b2  jz      short loc_1800076C3
0x1800076b4  movaps  xmm1, xmm0
0x1800076b7  roundss xmm1, xmm1, 9
0x1800076bd  cvttss2si eax, xmm1
0x1800076c1  jmp     short loc_1800076CF
0x1800076c3  cvtps2pd xmm0, xmm0; X
0x1800076c6  call    floor
0x1800076cb  cvttsd2si eax, xmm0
0x1800076cf  movss   xmm7, dword ptr [r12+4]
0x1800076d6  mov     [rbp+3Fh+xf.eM11], eax
0x1800076d9  movaps  xmm0, xmm7
0x1800076dc  mov     [rsp+120h+var_E0], eax
0x1800076e0  addss   xmm0, cs:__real@3f000000
0x1800076e8  test    bl, bl
0x1800076ea  jz      short loc_1800076FB
0x1800076ec  movaps  xmm1, xmm0
0x1800076ef  roundss xmm1, xmm1, 9
0x1800076f5  cvttss2si eax, xmm1
0x1800076f9  jmp     short loc_180007707
0x1800076fb  cvtps2pd xmm0, xmm0; X
0x1800076fe  call    floor
0x180007703  cvttsd2si eax, xmm0
0x180007707  mov     [rsp+120h+var_D0], eax
0x18000770b  mov     [rsp+120h+var_DC], eax
0x18000770f  addss   xmm6, dword ptr [r12+8]
0x180007716  addss   xmm6, cs:__real@3f000000
0x18000771e  test    bl, bl
0x180007720  jz      short loc_180007734
0x180007722  movaps  xmm0, xmm6
0x180007725  movaps  xmm1, xmm0
0x180007728  roundss xmm1, xmm1, 9
0x18000772e  cvttss2si edi, xmm1
0x180007732  jmp     short loc_180007740
0x180007734  cvtps2pd xmm0, xmm6; X
0x180007737  call    floor
0x18000773c  cvttsd2si edi, xmm0
0x180007740  mov     [rsp+120h+var_D8], edi
0x180007744  addss   xmm7, dword ptr [r12+0Ch]
0x18000774b  addss   xmm7, cs:__real@3f000000
0x180007753  test    bl, bl
0x180007755  jz      short loc_180007769
0x180007757  movaps  xmm0, xmm7
0x18000775a  movaps  xmm1, xmm0
0x18000775d  roundss xmm1, xmm1, 9
0x180007763  cvttss2si eax, xmm1
0x180007767  jmp     short loc_180007775
0x180007769  cvtps2pd xmm0, xmm7; X
0x18000776c  call    floor
0x180007771  cvttsd2si eax, xmm0
0x180007775  mov     [rsp+120h+var_D4], eax
0x180007779  cmp     eax, [rsp+120h+var_D0]
0x18000777d  jle     loc_18000792C
0x180007783  cmp     edi, [rbp+3Fh+xf.eM11]
0x180007786  jle     loc_18000792C
0x18000778c  lea     rbx, [r15+1488h]
0x180007793  cmp     [rbp+3Fh+arg_30], r13d
0x180007797  jnz     loc_18000781E
0x18000779d  mov     edx, 2; iMode
0x1800077a2  mov     rcx, rsi; hdc
0x1800077a5  call    cs:__imp_SetGraphicsMode
0x1800077ac  nop     dword ptr [rax+rax+00h]
0x1800077b1  movups  xmm0, xmmword ptr [rbx+10h]
0x1800077b5  lea     rdx, [rbp+3Fh+xf]; lpxf
0x1800077b9  mov     rcx, rsi; hdc
0x1800077bc  movss   xmm1, dword ptr [rbx+24h]
0x1800077c1  movups  xmmword ptr [rbp+3Fh+xf.eM11], xmm0
0x1800077c5  movss   xmm0, dword ptr [rbx+20h]
0x1800077ca  movss   [rbp+3Fh+xf.eDx], xmm0
0x1800077cf  movss   [rbp+3Fh+xf.eDy], xmm1
0x1800077d4  call    cs:__imp_SetWorldTransform
0x1800077db  nop     dword ptr [rax+rax+00h]
0x1800077e0  and     [rsp+120h+var_F0], r13d
0x1800077e5  lea     rax, EnumEmfWithDownLevel
0x1800077ec  xorps   xmm0, xmm0
0x1800077ef  mov     [rsp+120h+var_F8], rax
0x1800077f4  lea     rax, [rbp+3Fh+var_B8]
0x1800077f8  movups  [rbp+3Fh+var_B8], xmm0
0x1800077fc  lea     r9, [rsp+120h+var_E0]
0x180007801  mov     r8, [rsp+120h+var_C0]
0x180007806  mov     rdx, rsi
0x180007809  mov     rcx, r15
0x18000780c  mov     [rsp+120h+var_100], rax
0x180007811  call    ?EnumerateEmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHENHMETAFILE__@@PEBUtagRECT@@2P6AH0PEAUtagHANDLETABLE@@PEBUtagENHMETARECORD@@H_J@ZH@Z; MetafilePlayer::EnumerateEmfRecords(HDC__ *,HENHMETAFILE__ *,tagRECT const *,tagRECT const *,int (*)(HDC__ *,tagHANDLETABLE *,tagENHMETARECORD const *,int,__int64),int)
0x180007816  mov     r13d, eax
0x180007819  jmp     loc_18000792C
0x18000781e  mov     rax, [r14+88h]
0x180007825  lea     rdx, [r15+14D8h]
0x18000782c  and     qword ptr [rbp+3Fh+xf.eM11], r13
0x180007830  lea     r9, [rbp+3Fh+xf]
0x180007834  mov     [rsp+120h+var_F8], rbx; GpMatrix *
0x180007839  lea     r8, [rsp+120h+var_E0]
0x18000783e  mov     [rsp+120h+var_100], rdx; __int64
0x180007843  mov     ecx, [rax+48h]
0x180007846  mov     [rdx], ecx
0x180007848  mov     rdx, r12
0x18000784b  mov     rcx, rsi; hdc
0x18000784e  call    CreateDibSection32Bpp
0x180007853  mov     rdi, rax
0x180007856  mov     r13d, 1
0x18000785c  test    rax, rax
0x18000785f  jz      loc_18000791B
0x180007865  xor     ecx, ecx; hdc
0x180007867  call    cs:__imp_CreateCompatibleDC
0x18000786e  nop     dword ptr [rax+rax+00h]
0x180007873  mov     rbx, rax
0x180007876  test    rax, rax
0x180007879  jz      loc_18000790A
0x18000787f  mov     rcx, qword ptr [rbp+3Fh+xf.eM11]
0x180007883  mov     rdx, rdi; h
0x180007886  mov     [r15+14B8h], rcx
0x18000788d  mov     ecx, [rsp+120h+var_D8]
0x180007891  mov     [r15+14C0h], ecx
0x180007898  mov     ecx, [rsp+120h+var_D4]
0x18000789c  mov     [r15+14C4h], ecx
0x1800078a3  mov     rcx, rax; hdc
0x1800078a6  movups  xmm0, xmmword ptr [r12]
0x1800078ab  movdqu  xmmword ptr [r15+14C8h], xmm0
0x1800078b4  call    cs:__imp_SelectObject
0x1800078bb  nop     dword ptr [rax+rax+00h]
0x1800078c0  and     [rsp+120h+var_F0], 0
0x1800078c5  lea     rax, EnumEmfWithDownLevel
0x1800078cc  mov     r8, [rsp+120h+var_C0]
0x1800078d1  lea     r9, [rsp+120h+var_E0]
0x1800078d6  mov     [rsp+120h+var_F8], rax
0x1800078db  mov     rdx, rbx
0x1800078de  lea     rax, [rsp+120h+var_E0]
0x1800078e3  mov     rcx, r15
0x1800078e6  mov     [rsp+120h+var_100], rax
0x1800078eb  call    ?EnumerateEmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHENHMETAFILE__@@PEBUtagRECT@@2P6AH0PEAUtagHANDLETABLE@@PEBUtagENHMETARECORD@@H_J@ZH@Z; MetafilePlayer::EnumerateEmfRecords(HDC__ *,HENHMETAFILE__ *,tagRECT const *,tagRECT const *,int (*)(HDC__ *,tagHANDLETABLE *,tagENHMETARECORD const *,int,__int64),int)
0x1800078f0  mov     rcx, rbx; hdc
0x1800078f3  mov     r13d, eax
0x1800078f6  call    cs:__imp_DeleteDC
0x1800078fd  nop     dword ptr [rax+rax+00h]
0x180007902  and     qword ptr [r15+14B8h], 0
0x18000790a  mov     rcx, rdi; ho
0x18000790d  call    cs:__imp_DeleteObject
0x180007914  nop     dword ptr [rax+rax+00h]
0x180007919  jmp     short loc_18000792C
0x18000791b  cmp     [rsp+120h+var_D8], 0
0x180007920  jz      short loc_180007929
0x180007922  cmp     [rsp+120h+var_D4], 0
0x180007927  jnz     short loc_18000792C
0x180007929  xor     r13d, r13d
0x18000792c  lea     rcx, [rbp+3Fh+var_A0]; this
0x180007930  call    ??1SetupClippingForMetafilePlayback@@QEAA@XZ; SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback(void)
0x180007935  mov     rcx, r15; this
0x180007938  call    ?DoneWithDownLevel@MetafilePlayer@@QEAAXXZ; MetafilePlayer::DoneWithDownLevel(void)
0x18000793d  mov     rcx, [r14+88h]; this
0x180007944  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x180007949  mov     rbx, [rbp+3Fh+hWnd]
0x18000794d  test    rbx, rbx
0x180007950  jz      short loc_180007983
0x180007952  mov     rdx, rsi; hDC
0x180007955  mov     rcx, rbx; hWnd
0x180007958  call    cs:__imp_ReleaseDC
0x18000795f  nop     dword ptr [rax+rax+00h]
0x180007964  mov     rax, [r14+88h]
0x18000796b  mov     [rax+278h], rbx
0x180007972  mov     rax, [r14+88h]
0x180007979  and     qword ptr [rax+270h], 0
0x180007981  jmp     short loc_1800079AF
0x180007983  mov     edx, [rsp+120h+nSavedDC]; nSavedDC
  ... truncated ...
```
