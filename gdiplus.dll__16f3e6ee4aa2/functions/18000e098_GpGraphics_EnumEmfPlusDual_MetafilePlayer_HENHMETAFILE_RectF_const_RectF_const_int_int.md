# GpGraphics::EnumEmfPlusDual(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,int,int)

- ea: `0x18000e098`
- end: `0x18000e634`
- name: `?EnumEmfPlusDual@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@2HH@Z`
- size: `1436`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f07c`

## callees

- `0x18000ca18`
- `0x18000cb6c`
- `0x18000e098`
- `0x18000e63c`
- `0x18003d260`
- `0x18003d33c`
- `0x18004396c`
- `0x18005b2a0`
- `0x18006fa3c`
- `0x180071884`
- `0x180076f28`
- `0x1800daab8`
- `0x1800e3fc8`
- `0x1800fe680`
- `0x1800fefe0`
- `0x180119efc`

## import_xrefs

- `USER32!ReleaseDC` at `0x18000e1f6`
- `USER32!ReleaseDC` at `0x18000e204`
- `USER32!ReleaseDC` at `0x18000e1f6`
- `USER32!ReleaseDC` at `0x18000e204`
- `GDI32!SetWorldTransform` at `0x18000e493`
- `GDI32!SetWorldTransform` at `0x18000e493`
- `GDI32!SetGraphicsMode` at `0x18000e46a`
- `GDI32!SetGraphicsMode` at `0x18000e46a`
- `GDI32!SaveDC` at `0x18000e167`
- `GDI32!SaveDC` at `0x18000e167`
- `GDI32!RestoreDC` at `0x18000e1d4`
- `GDI32!RestoreDC` at `0x18000e1d4`
- `GDI32!DeleteDC` at `0x18000e5fb`
- `GDI32!DeleteDC` at `0x18000e5fb`
- `GDI32!SelectObject` at `0x18000e5bc`
- `GDI32!SelectObject` at `0x18000e5bc`
- `GDI32!CreateCompatibleDC` at `0x18000e575`
- `GDI32!CreateCompatibleDC` at `0x18000e575`
- `GDI32!DeleteObject` at `0x18000e60f`
- `GDI32!DeleteObject` at `0x18000e60f`

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
  struct DpBitmap *v9; // rcx
  DpContext *v12; // rcx
  HDC CleanHdc; // rsi
  int v15; // eax
  DpContext *v16; // rcx
  unsigned int v17; // r12d
  HWND v18; // rbx
  HWND v19; // rcx
  float v20; // xmm6_4
  FLOAT v21; // eax
  float v22; // xmm7_4
  FLOAT v23; // eax
  float v24; // xmm6_4
  FLOAT v25; // eax
  float v26; // xmm7_4
  PointF *v27; // rbx
  __int64 v28; // rdi
  float v29; // xmm1_4
  float v30; // xmm0_4
  float v31; // xmm1_4
  int v32; // edi
  int v33; // r13d
  int v34; // ebx
  int v35; // eax
  unsigned int v36; // eax
  struct DpBitmap *v37; // rax
  __m128 v38; // xmm7
  bool v39; // bl
  __m128 v40; // xmm1
  float v41; // eax
  __m128 v42; // xmm6
  __m128 v43; // xmm1
  int v44; // eax
  int v45; // edi
  int v46; // eax
  FLOAT v47; // xmm1_4
  struct DpBitmap *v48; // rax
  void *DibSection32Bpp; // rdi
  HDC CompatibleDC; // rax
  HDC v51; // rbx
  int v52; // [rsp+28h] [rbp-C1h]
  float v53; // [rsp+48h] [rbp-A1h] BYREF
  float v54; // [rsp+4Ch] [rbp-9Dh]
  float v55; // [rsp+50h] [rbp-99h]
  float v56; // [rsp+54h] [rbp-95h]
  int v57; // [rsp+58h] [rbp-91h]
  int nSavedDC; // [rsp+5Ch] [rbp-8Dh]
  __int64 v59; // [rsp+60h] [rbp-89h]
  __int64 v60; // [rsp+68h] [rbp-81h]
  __int128 v61; // [rsp+70h] [rbp-79h] BYREF
  HWND hWnd; // [rsp+80h] [rbp-69h]
  _BYTE v63[24]; // [rsp+88h] [rbp-61h] BYREF
  int v64; // [rsp+A0h] [rbp-49h]
  XFORM xf; // [rsp+A8h] [rbp-41h] BYREF

  v7 = a1[17];
  v9 = a1[5];
  v60 = a3;
  hWnd = (HWND)*((_QWORD *)v7 + 79);
  LODWORD(v59) = 0;
  DpBitmap::Flush(v9);
  if ( hWnd )
  {
    CleanHdc = GetCleanHdc(hWnd);
    if ( !CleanHdc )
      return 7;
    v37 = a1[17];
    nSavedDC = -1;
    *((_QWORD *)v37 + 79) = 0;
    *((_QWORD *)a1[17] + 78) = CleanHdc;
  }
  else
  {
    v12 = a1[17];
    CleanHdc = (HDC)*((_QWORD *)v12 + 78);
    if ( CleanHdc )
    {
      DpContext::ResetHdc(v12);
    }
    else
    {
      CleanHdc = DpContext::GetHdc(v12, a1[5]);
      if ( !CleanHdc )
        return 2;
      LODWORD(v59) = 1;
    }
    v15 = SaveDC(CleanHdc);
    v16 = a1[17];
    nSavedDC = v15;
    DpContext::CleanTheHdc(v16, CleanHdc);
  }
  v17 = 0;
  SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
    (SetupClippingForMetafilePlayback *)v63,
    CleanHdc,
    a1[16],
    a1[17],
    v52);
  if ( !v64 )
  {
    v20 = *a5;
    LODWORD(v21) = RasterizerCeiling(*a5);
    v22 = a5[1];
    xf.eM11 = v21;
    LODWORD(v23) = RasterizerCeiling(v22);
    v24 = v20 + a5[2];
    xf.eM12 = v23;
    LODWORD(v25) = RasterizerCeiling(v24);
    v26 = v22 + a5[3];
    xf.eM21 = v25;
    LODWORD(xf.eM22) = RasterizerCeiling(v26);
    if ( a6 )
    {
      v27 = (PointF *)&v53;
      v28 = 2;
      do
      {
        PointF::PointF(v27);
        v27 = (PointF *)((char *)v27 + 8);
        --v28;
      }
      while ( v28 );
      v29 = a4[1];
      v53 = *a4;
      v30 = v53 + a4[2];
      v54 = v29;
      v31 = v29 + a4[3];
      v55 = v30;
      v56 = v31;
      GpMatrix::Transform((GpMatrix *)(a2 + 5256), (struct PointF *)&v53, 2);
      v32 = RasterizerCeiling(v53);
      LODWORD(v61) = v32;
      v33 = RasterizerCeiling(v54);
      DWORD1(v61) = v33;
      v34 = RasterizerCeiling(v55);
      DWORD2(v61) = v34;
      v35 = RasterizerCeiling(v56);
      HIDWORD(v61) = v35;
      if ( v32 >= v34 || v33 >= v35 )
        goto LABEL_8;
      v36 = MetafilePlayer::EnumerateEmfRecords(a2, CleanHdc, v60, &v61, &xf, &EnumEmfWithDownLevel, 0);
    }
    else
    {
      v38 = (__m128)*(unsigned int *)a4;
      v39 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v40 = v38;
      v40.m128_f32[0] = v38.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        LODWORD(v41) = (int)_mm_round_ss(v40, v40, 9).m128_f32[0];
      else
        LODWORD(v41) = (int)floor(v40.m128_f32[0]);
      v42 = (__m128)*((unsigned int *)a4 + 1);
      xf.eM11 = v41;
      v43 = v42;
      v53 = v41;
      v43.m128_f32[0] = v42.m128_f32[0] + 0.5;
      if ( v39 )
        v44 = (int)_mm_round_ss(v43, v43, 9).m128_f32[0];
      else
        v44 = (int)floor(v43.m128_f32[0]);
      v57 = v44;
      LODWORD(v54) = v44;
      v38.m128_f32[0] = (float)(v38.m128_f32[0] + a4[2]) + 0.5;
      if ( v39 )
        v45 = (int)_mm_round_ss(v38, v38, 9).m128_f32[0];
      else
        v45 = (int)floor(v38.m128_f32[0]);
      LODWORD(v55) = v45;
      v42.m128_f32[0] = (float)(v42.m128_f32[0] + a4[3]) + 0.5;
      if ( v39 )
        v46 = (int)_mm_round_ss(v42, v42, 9).m128_f32[0];
      else
        v46 = (int)floor(v42.m128_f32[0]);
      LODWORD(v56) = v46;
      if ( v46 <= v57 || v45 <= SLODWORD(xf.eM11) )
        goto LABEL_8;
      if ( a7 )
      {
        v48 = a1[17];
        *(_QWORD *)&xf.eM11 = 0;
        *(_DWORD *)(a2 + 5336) = *((_DWORD *)v48 + 18);
        DibSection32Bpp = (void *)CreateDibSection32Bpp(CleanHdc, a2 + 5336, (GpMatrix *)(a2 + 5256));
        v17 = 1;
        if ( DibSection32Bpp )
        {
          CompatibleDC = CreateCompatibleDC(0);
          v51 = CompatibleDC;
          if ( CompatibleDC )
          {
            *(_QWORD *)(a2 + 5304) = *(_QWORD *)&xf.eM11;
            *(float *)(a2 + 5312) = v55;
            *(float *)(a2 + 5316) = v56;
            *(_OWORD *)(a2 + 5320) = *(_OWORD *)a4;
            SelectObject(CompatibleDC, DibSection32Bpp);
            v17 = MetafilePlayer::EnumerateEmfRecords(a2, v51, v60, &v53, &v53, &EnumEmfWithDownLevel, 0);
            DeleteDC(v51);
            *(_QWORD *)(a2 + 5304) = 0;
          }
          DeleteObject(DibSection32Bpp);
        }
        else if ( !LODWORD(v55) || !LODWORD(v56) )
        {
          v17 = 0;
        }
        goto LABEL_8;
      }
      SetGraphicsMode(CleanHdc, 2);
      v47 = *(float *)(a2 + 5292);
      *(_OWORD *)&xf.eM11 = *(_OWORD *)(a2 + 5272);
      xf.eDx = *(FLOAT *)(a2 + 5288);
      xf.eDy = v47;
      SetWorldTransform(CleanHdc, &xf);
      v61 = 0;
      v36 = MetafilePlayer::EnumerateEmfRecords(a2, CleanHdc, v60, &v53, &v61, &EnumEmfWithDownLevel, 0);
    }
    v17 = v36;
  }
LABEL_8:
  SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback((SetupClippingForMetafilePlayback *)v63);
  MetafilePlayer::DoneWithDownLevel((MetafilePlayer *)a2);
  DpContext::ResetHdc(a1[17]);
  v18 = hWnd;
  if ( hWnd )
  {
    ReleaseDC(hWnd, CleanHdc);
    *((_QWORD *)a1[17] + 79) = v18;
    *((_QWORD *)a1[17] + 78) = 0;
  }
  else
  {
    RestoreDC(CleanHdc, nSavedDC);
    if ( (_DWORD)v59 )
    {
      v19 = (HWND)*((_QWORD *)a1[17] + 79);
      if ( v19 )
        ReleaseDC(v19, CleanHdc);
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18000e098  mov     rax, rsp
0x18000e09b  push    rbp
0x18000e09c  push    rbx
0x18000e09d  push    rsi
0x18000e09e  push    rdi
0x18000e09f  push    r12
0x18000e0a1  push    r13
0x18000e0a3  push    r14
0x18000e0a5  push    r15
0x18000e0a7  lea     rbp, [rax-47h]
0x18000e0ab  sub     rsp, 0E8h
0x18000e0b2  movaps  xmmword ptr [rax-58h], xmm6
0x18000e0b6  movaps  xmmword ptr [rax-68h], xmm7
0x18000e0ba  mov     rax, cs:__security_cookie
0x18000e0c1  xor     rax, rsp
0x18000e0c4  mov     [rbp+3Fh+var_68], rax
0x18000e0c8  mov     rax, [rcx+88h]
0x18000e0cf  mov     r14, rcx
0x18000e0d2  mov     rcx, [rcx+28h]
0x18000e0d6  mov     r13, r9
0x18000e0d9  mov     rbx, [rbp+3Fh+arg_20]
0x18000e0dd  mov     r15, rdx
0x18000e0e0  mov     [rsp+120h+var_C0], r8
0x18000e0e5  mov     rsi, [rax+278h]
0x18000e0ec  mov     [rbp+3Fh+hWnd], rsi
0x18000e0f0  mov     dword ptr [rsp+120h+var_C8], 0
0x18000e0f8  call    ?Flush@DpBitmap@@QEAAXW4FlushIntention@@@Z; DpBitmap::Flush(FlushIntention)
0x18000e0fd  test    rsi, rsi
0x18000e100  jnz     loc_18000E232
0x18000e106  mov     rcx, [r14+88h]; this
0x18000e10d  mov     rsi, [rcx+270h]
0x18000e114  test    rsi, rsi
0x18000e117  jnz     short loc_18000E15F
0x18000e119  mov     rdx, [r14+28h]; struct DpBitmap *
0x18000e11d  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x18000e122  mov     rsi, rax
0x18000e125  test    rax, rax
0x18000e128  jnz     loc_18000E51F
0x18000e12e  lea     eax, [rsi+2]
0x18000e131  mov     rcx, [rbp+3Fh+var_68]
0x18000e135  xor     rcx, rsp; StackCookie
0x18000e138  call    __security_check_cookie
0x18000e13d  lea     r11, [rsp+120h+var_38]
0x18000e145  movaps  xmm6, xmmword ptr [r11-18h]
0x18000e14a  movaps  xmm7, xmmword ptr [r11-28h]
0x18000e14f  mov     rsp, r11
0x18000e152  pop     r15
0x18000e154  pop     r14
0x18000e156  pop     r13
0x18000e158  pop     r12
0x18000e15a  pop     rdi
0x18000e15b  pop     rsi
0x18000e15c  pop     rbx
0x18000e15d  pop     rbp
0x18000e15e  retn
0x18000e15f  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x18000e164  mov     rcx, rsi; hdc
0x18000e167  call    cs:__imp_SaveDC
0x18000e16d  mov     rcx, [r14+88h]; this
0x18000e174  mov     rdx, rsi; HDC
0x18000e177  mov     [rsp+120h+nSavedDC], eax
0x18000e17b  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x18000e180  mov     r9, [r14+88h]; struct DpContext *
0x18000e187  lea     rcx, [rbp+3Fh+var_A0]; this
0x18000e18b  mov     r8, [r14+80h]; struct DpDriver *
0x18000e192  mov     rdx, rsi; HDC
0x18000e195  xor     r12d, r12d
0x18000e198  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x18000e19d  cmp     [rbp+3Fh+var_88], r12d
0x18000e1a1  jz      loc_18000E24E
0x18000e1a7  lea     rcx, [rbp+3Fh+var_A0]; this
0x18000e1ab  call    ??1SetupClippingForMetafilePlayback@@QEAA@XZ; SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback(void)
0x18000e1b0  mov     rcx, r15; this
0x18000e1b3  call    ?DoneWithDownLevel@MetafilePlayer@@QEAAXXZ; MetafilePlayer::DoneWithDownLevel(void)
0x18000e1b8  mov     rcx, [r14+88h]; this
0x18000e1bf  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x18000e1c4  mov     rbx, [rbp+3Fh+hWnd]
0x18000e1c8  test    rbx, rbx
0x18000e1cb  jnz     short loc_18000E1FE
0x18000e1cd  mov     edx, [rsp+120h+nSavedDC]; nSavedDC
0x18000e1d1  mov     rcx, rsi; hdc
0x18000e1d4  call    cs:__imp_RestoreDC
0x18000e1da  cmp     dword ptr [rsp+120h+var_C8], ebx
0x18000e1de  jz      short loc_18000E22A
0x18000e1e0  mov     rax, [r14+88h]
0x18000e1e7  mov     rcx, [rax+278h]; hWnd
0x18000e1ee  test    rcx, rcx
0x18000e1f1  jz      short loc_18000E22A
0x18000e1f3  mov     rdx, rsi; hDC
0x18000e1f6  call    cs:__imp_ReleaseDC
0x18000e1fc  jmp     short loc_18000E22A
0x18000e1fe  mov     rdx, rsi; hDC
0x18000e201  mov     rcx, rbx; hWnd
0x18000e204  call    cs:__imp_ReleaseDC
0x18000e20a  mov     rax, [r14+88h]
0x18000e211  mov     [rax+278h], rbx
0x18000e218  mov     rax, [r14+88h]
0x18000e21f  mov     qword ptr [rax+270h], 0
0x18000e22a  mov     eax, r12d
0x18000e22d  jmp     loc_18000E131
0x18000e232  mov     rcx, rsi; hWnd
0x18000e235  call    ?GetCleanHdc@@YAPEAUHDC__@@PEAUHWND__@@@Z; GetCleanHdc(HWND__ *)
0x18000e23a  mov     rsi, rax
0x18000e23d  test    rax, rax
0x18000e240  jnz     loc_18000E366
0x18000e246  lea     eax, [rsi+7]
0x18000e249  jmp     loc_18000E131
0x18000e24e  movss   xmm6, dword ptr [rbx]
0x18000e252  movaps  xmm0, xmm6; float
0x18000e255  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e25a  movss   xmm7, dword ptr [rbx+4]
0x18000e25f  movaps  xmm0, xmm7; float
0x18000e262  mov     [rbp+3Fh+xf.eM11], eax
0x18000e265  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e26a  addss   xmm6, dword ptr [rbx+8]
0x18000e26f  mov     [rbp+3Fh+xf.eM12], eax
0x18000e272  movaps  xmm0, xmm6; float
0x18000e275  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e27a  addss   xmm7, dword ptr [rbx+0Ch]
0x18000e27f  mov     [rbp+3Fh+xf.eM21], eax
0x18000e282  movaps  xmm0, xmm7; float
0x18000e285  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e28a  mov     [rbp+3Fh+xf.eM22], eax
0x18000e28d  cmp     [rbp+3Fh+arg_28], r12d
0x18000e291  jz      loc_18000E393
0x18000e297  lea     rbx, [rsp+120h+var_E0]
0x18000e29c  mov     edi, 2
0x18000e2a1  mov     rcx, rbx; this
0x18000e2a4  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x18000e2a9  add     rbx, 8
0x18000e2ad  sub     rdi, 1
0x18000e2b1  jnz     short loc_18000E2A1
0x18000e2b3  movss   xmm0, dword ptr [r13+0]
0x18000e2b9  lea     rcx, [r15+1488h]; this
0x18000e2c0  movss   xmm1, dword ptr [r13+4]
0x18000e2c6  lea     r8d, [rdi+2]; int
0x18000e2ca  movss   [rsp+120h+var_E0], xmm0
0x18000e2d0  lea     rdx, [rsp+120h+var_E0]; struct PointF *
0x18000e2d5  addss   xmm0, dword ptr [r13+8]
0x18000e2db  movss   [rsp+120h+var_DC], xmm1
0x18000e2e1  addss   xmm1, dword ptr [r13+0Ch]
0x18000e2e7  movss   [rsp+120h+var_D8], xmm0
0x18000e2ed  movss   [rsp+120h+var_D4], xmm1
0x18000e2f3  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x18000e2f8  movss   xmm0, [rsp+120h+var_E0]; float
0x18000e2fe  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e303  movss   xmm0, [rsp+120h+var_DC]; float
0x18000e309  mov     edi, eax
0x18000e30b  mov     dword ptr [rbp+3Fh+var_B8], eax
0x18000e30e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e313  movss   xmm0, [rsp+120h+var_D8]; float
0x18000e319  mov     r13d, eax
0x18000e31c  mov     dword ptr [rbp+3Fh+var_B8+4], eax
0x18000e31f  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e324  movss   xmm0, [rsp+120h+var_D4]; float
0x18000e32a  mov     ebx, eax
0x18000e32c  mov     dword ptr [rbp+3Fh+var_B8+8], eax
0x18000e32f  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18000e334  mov     dword ptr [rbp+3Fh+var_B8+0Ch], eax
0x18000e337  cmp     edi, ebx
0x18000e339  jge     loc_18000E1A7
0x18000e33f  cmp     r13d, eax
0x18000e342  jge     loc_18000E1A7
0x18000e348  lea     rax, EnumEmfWithDownLevel
0x18000e34f  mov     [rsp+120h+var_F0], r12d
0x18000e354  mov     [rsp+120h+var_F8], rax
0x18000e359  lea     r9, [rbp+3Fh+var_B8]
0x18000e35d  lea     rax, [rbp+3Fh+xf]
0x18000e361  jmp     loc_18000E4BA
0x18000e366  mov     rax, [r14+88h]
0x18000e36d  mov     [rsp+120h+nSavedDC], 0FFFFFFFFh
0x18000e375  mov     qword ptr [rax+278h], 0
0x18000e380  mov     rax, [r14+88h]
0x18000e387  mov     [rax+270h], rsi
0x18000e38e  jmp     loc_18000E180
0x18000e393  movss   xmm7, dword ptr [r13+0]
0x18000e399  mov     bl, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18000e39f  movaps  xmm1, xmm7
0x18000e3a2  addss   xmm1, cs:__real@3f000000
0x18000e3aa  test    bl, bl
0x18000e3ac  jnz     loc_18000E4D7
0x18000e3b2  cvtps2pd xmm0, xmm1; X
0x18000e3b5  call    floor
0x18000e3ba  cvttsd2si eax, xmm0
0x18000e3be  movss   xmm6, dword ptr [r13+4]
0x18000e3c4  mov     [rbp+3Fh+xf.eM11], eax
0x18000e3c7  movaps  xmm1, xmm6
0x18000e3ca  mov     [rsp+120h+var_E0], eax
0x18000e3ce  addss   xmm1, cs:__real@3f000000
0x18000e3d6  test    bl, bl
0x18000e3d8  jnz     loc_18000E4E9
0x18000e3de  cvtps2pd xmm0, xmm1; X
0x18000e3e1  call    floor
0x18000e3e6  cvttsd2si eax, xmm0
0x18000e3ea  mov     [rsp+120h+var_D0], eax
0x18000e3ee  mov     [rsp+120h+var_DC], eax
0x18000e3f2  addss   xmm7, dword ptr [r13+8]
0x18000e3f8  addss   xmm7, cs:__real@3f000000
0x18000e400  test    bl, bl
0x18000e402  jnz     loc_18000E4FB
0x18000e408  cvtps2pd xmm0, xmm7; X
0x18000e40b  call    floor
0x18000e410  cvttsd2si edi, xmm0
0x18000e414  mov     [rsp+120h+var_D8], edi
0x18000e418  addss   xmm6, dword ptr [r13+0Ch]
0x18000e41e  addss   xmm6, cs:__real@3f000000
0x18000e426  test    bl, bl
0x18000e428  jnz     loc_18000E50D
0x18000e42e  cvtps2pd xmm0, xmm6; X
0x18000e431  call    floor
0x18000e436  cvttsd2si eax, xmm0
0x18000e43a  mov     [rsp+120h+var_D4], eax
0x18000e43e  cmp     eax, [rsp+120h+var_D0]
0x18000e442  jle     loc_18000E1A7
0x18000e448  cmp     edi, [rbp+3Fh+xf.eM11]
0x18000e44b  jle     loc_18000E1A7
0x18000e451  lea     rbx, [r15+1488h]
0x18000e458  cmp     [rbp+3Fh+arg_30], r12d
0x18000e45c  jnz     loc_18000E52C
0x18000e462  mov     edx, 2; iMode
0x18000e467  mov     rcx, rsi; hdc
0x18000e46a  call    cs:__imp_SetGraphicsMode
0x18000e470  movups  xmm0, xmmword ptr [rbx+10h]
0x18000e474  lea     rdx, [rbp+3Fh+xf]; lpxf
0x18000e478  mov     rcx, rsi; hdc
0x18000e47b  movss   xmm1, dword ptr [rbx+24h]
0x18000e480  movups  xmmword ptr [rbp+3Fh+xf.eM11], xmm0
0x18000e484  movss   xmm0, dword ptr [rbx+20h]
0x18000e489  movss   [rbp+3Fh+xf.eDx], xmm0
0x18000e48e  movss   [rbp+3Fh+xf.eDy], xmm1
0x18000e493  call    cs:__imp_SetWorldTransform
0x18000e499  lea     rax, EnumEmfWithDownLevel
0x18000e4a0  mov     [rsp+120h+var_F0], r12d
0x18000e4a5  xorps   xmm0, xmm0
0x18000e4a8  mov     [rsp+120h+var_F8], rax
0x18000e4ad  lea     rax, [rbp+3Fh+var_B8]
0x18000e4b1  movups  [rbp+3Fh+var_B8], xmm0
0x18000e4b5  lea     r9, [rsp+120h+var_E0]
0x18000e4ba  mov     r8, [rsp+120h+var_C0]
0x18000e4bf  mov     rdx, rsi
0x18000e4c2  mov     rcx, r15
0x18000e4c5  mov     [rsp+120h+var_100], rax
0x18000e4ca  call    ?EnumerateEmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHENHMETAFILE__@@PEBUtagRECT@@2P6AH0PEAUtagHANDLETABLE@@PEBUtagENHMETARECORD@@H_J@ZH@Z; MetafilePlayer::EnumerateEmfRecords(HDC__ *,HENHMETAFILE__ *,tagRECT const *,tagRECT const *,int (*)(HDC__ *,tagHANDLETABLE *,tagENHMETARECORD const *,int,__int64),int)
0x18000e4cf  mov     r12d, eax
0x18000e4d2  jmp     loc_18000E1A7
0x18000e4d7  movaps  xmm0, xmm1
0x18000e4da  roundss xmm0, xmm0, 9
0x18000e4e0  cvttss2si eax, xmm0
0x18000e4e4  jmp     loc_18000E3BE
0x18000e4e9  movaps  xmm0, xmm1
0x18000e4ec  roundss xmm0, xmm0, 9
0x18000e4f2  cvttss2si eax, xmm0
0x18000e4f6  jmp     loc_18000E3EA
0x18000e4fb  movaps  xmm0, xmm7
0x18000e4fe  roundss xmm0, xmm0, 9
0x18000e504  cvttss2si edi, xmm0
0x18000e508  jmp     loc_18000E414
0x18000e50d  movaps  xmm0, xmm6
0x18000e510  roundss xmm0, xmm0, 9
0x18000e516  cvttss2si eax, xmm0
0x18000e51a  jmp     loc_18000E43A
0x18000e51f  mov     dword ptr [rsp+120h+var_C8], 1
0x18000e527  jmp     loc_18000E164
0x18000e52c  mov     rax, [r14+88h]
0x18000e533  lea     rdx, [r15+14D8h]
0x18000e53a  mov     qword ptr [rbp+3Fh+xf.eM11], r12
0x18000e53e  lea     r9, [rbp+3Fh+xf]
0x18000e542  mov     [rsp+120h+var_F8], rbx; GpMatrix *
0x18000e547  lea     r8, [rsp+120h+var_E0]
0x18000e54c  mov     [rsp+120h+var_100], rdx; __int64
0x18000e551  mov     ecx, [rax+48h]
0x18000e554  mov     [rdx], ecx
0x18000e556  mov     rdx, r13
0x18000e559  mov     rcx, rsi; hdc
0x18000e55c  call    CreateDibSection32Bpp
0x18000e561  mov     rdi, rax
0x18000e564  mov     r12d, 1
0x18000e56a  test    rax, rax
0x18000e56d  jz      loc_18000E61A
0x18000e573  xor     ecx, ecx; hdc
0x18000e575  call    cs:__imp_CreateCompatibleDC
0x18000e57b  mov     rbx, rax
0x18000e57e  test    rax, rax
0x18000e581  jz      loc_18000E60C
0x18000e587  mov     rcx, qword ptr [rbp+3Fh+xf.eM11]
0x18000e58b  mov     rdx, rdi; h
0x18000e58e  mov     [r15+14B8h], rcx
0x18000e595  mov     ecx, [rsp+120h+var_D8]
0x18000e599  mov     [r15+14C0h], ecx
0x18000e5a0  mov     ecx, [rsp+120h+var_D4]
0x18000e5a4  mov     [r15+14C4h], ecx
0x18000e5ab  mov     rcx, rax; hdc
0x18000e5ae  movups  xmm0, xmmword ptr [r13+0]
0x18000e5b3  movdqu  xmmword ptr [r15+14C8h], xmm0
0x18000e5bc  call    cs:__imp_SelectObject
0x18000e5c2  mov     r8, [rsp+120h+var_C0]
0x18000e5c7  lea     rax, EnumEmfWithDownLevel
0x18000e5ce  mov     [rsp+120h+var_F0], 0
0x18000e5d6  lea     r9, [rsp+120h+var_E0]
0x18000e5db  mov     [rsp+120h+var_F8], rax
  ... truncated ...
```
