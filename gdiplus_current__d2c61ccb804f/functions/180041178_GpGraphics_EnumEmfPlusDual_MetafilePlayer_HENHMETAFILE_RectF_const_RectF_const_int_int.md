# GpGraphics::EnumEmfPlusDual(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,int,int)

- ea: `0x180041178`
- end: `0x180041751`
- name: `?EnumEmfPlusDual@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@2HH@Z`
- size: `1497`
- prototype: `enum Status __high(struct MetafilePlayer *, HENHMETAFILE, const struct RectF *, const struct RectF *, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800421f4`

## callees

- `0x18002f12c`
- `0x18002f21c`
- `0x180035ac0`
- `0x18003f45c`
- `0x1800402d8`
- `0x180040e68`
- `0x180041178`
- `0x180041758`
- `0x180044ce8`
- `0x180044d34`
- `0x180051890`
- `0x180080604`
- `0x1800e0e64`
- `0x180105d40`
- `0x1801066d0`
- `0x18012200c`

## import_xrefs

- `USER32!ReleaseDC` at `0x1800412e3`
- `USER32!ReleaseDC` at `0x1800412f7`
- `USER32!ReleaseDC` at `0x1800412e3`
- `USER32!ReleaseDC` at `0x1800412f7`
- `GDI32!SetWorldTransform` at `0x180041592`
- `GDI32!SetWorldTransform` at `0x180041592`
- `GDI32!SetGraphicsMode` at `0x180041563`
- `GDI32!SetGraphicsMode` at `0x180041563`
- `GDI32!SaveDC` at `0x180041248`
- `GDI32!SaveDC` at `0x180041248`
- `GDI32!RestoreDC` at `0x1800412bb`
- `GDI32!RestoreDC` at `0x1800412bb`
- `GDI32!DeleteDC` at `0x18004170c`
- `GDI32!DeleteDC` at `0x18004170c`
- `GDI32!SelectObject` at `0x1800416c7`
- `GDI32!SelectObject` at `0x1800416c7`
- `GDI32!CreateCompatibleDC` at `0x18004167a`
- `GDI32!CreateCompatibleDC` at `0x18004167a`
- `GDI32!DeleteObject` at `0x180041726`
- `GDI32!DeleteObject` at `0x180041726`

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
0x180041178  mov     rax, rsp
0x18004117b  push    rbp
0x18004117c  push    rbx
0x18004117d  push    rsi
0x18004117e  push    rdi
0x18004117f  push    r12
0x180041181  push    r13
0x180041183  push    r14
0x180041185  push    r15
0x180041187  lea     rbp, [rax-47h]
0x18004118b  sub     rsp, 0E8h
0x180041192  movaps  xmmword ptr [rax-58h], xmm6
0x180041196  movaps  xmmword ptr [rax-68h], xmm7
0x18004119a  mov     rax, cs:__security_cookie
0x1800411a1  xor     rax, rsp
0x1800411a4  mov     [rbp+3Fh+var_68], rax
0x1800411a8  mov     rax, [rcx+88h]
0x1800411af  mov     r14, rcx
0x1800411b2  mov     rcx, [rcx+28h]
0x1800411b6  mov     r13, r9
0x1800411b9  mov     rbx, [rbp+3Fh+arg_20]
0x1800411bd  mov     r15, rdx
0x1800411c0  mov     [rsp+120h+var_C0], r8
0x1800411c5  mov     rsi, [rax+278h]
0x1800411cc  mov     [rbp+3Fh+hWnd], rsi
0x1800411d0  mov     dword ptr [rsp+120h+var_C8], 0
0x1800411d8  call    ?Flush@DpBitmap@@QEAAXW4FlushIntention@@@Z; DpBitmap::Flush(FlushIntention)
0x1800411dd  test    rsi, rsi
0x1800411e0  jnz     loc_18004132B
0x1800411e6  mov     rcx, [r14+88h]; this
0x1800411ed  mov     rsi, [rcx+270h]
0x1800411f4  test    rsi, rsi
0x1800411f7  jnz     short loc_180041240
0x1800411f9  mov     rdx, [r14+28h]; struct DpBitmap *
0x1800411fd  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x180041202  mov     rsi, rax
0x180041205  test    rax, rax
0x180041208  jnz     loc_180041624
0x18004120e  lea     eax, [rsi+2]
0x180041211  mov     rcx, [rbp+3Fh+var_68]
0x180041215  xor     rcx, rsp; StackCookie
0x180041218  call    __security_check_cookie
0x18004121d  lea     r11, [rsp+120h+var_38]
0x180041225  movaps  xmm6, xmmword ptr [r11-18h]
0x18004122a  movaps  xmm7, xmmword ptr [r11-28h]
0x18004122f  mov     rsp, r11
0x180041232  pop     r15
0x180041234  pop     r14
0x180041236  pop     r13
0x180041238  pop     r12
0x18004123a  pop     rdi
0x18004123b  pop     rsi
0x18004123c  pop     rbx
0x18004123d  pop     rbp
0x18004123e  retn
0x180041240  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x180041245  mov     rcx, rsi; hdc
0x180041248  call    cs:__imp_SaveDC
0x18004124f  nop     dword ptr [rax+rax+00h]
0x180041254  mov     rcx, [r14+88h]; this
0x18004125b  mov     rdx, rsi; HDC
0x18004125e  mov     [rsp+120h+nSavedDC], eax
0x180041262  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x180041267  mov     r9, [r14+88h]; struct DpContext *
0x18004126e  lea     rcx, [rbp+3Fh+var_A0]; this
0x180041272  mov     r8, [r14+80h]; struct DpDriver *
0x180041279  mov     rdx, rsi; HDC
0x18004127c  xor     r12d, r12d
0x18004127f  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x180041284  cmp     [rbp+3Fh+var_88], r12d
0x180041288  jz      loc_180041347
0x18004128e  lea     rcx, [rbp+3Fh+var_A0]; this
0x180041292  call    ??1SetupClippingForMetafilePlayback@@QEAA@XZ; SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback(void)
0x180041297  mov     rcx, r15; this
0x18004129a  call    ?DoneWithDownLevel@MetafilePlayer@@QEAAXXZ; MetafilePlayer::DoneWithDownLevel(void)
0x18004129f  mov     rcx, [r14+88h]; this
0x1800412a6  call    ?ResetHdc@DpContext@@QEAAXXZ; DpContext::ResetHdc(void)
0x1800412ab  mov     rbx, [rbp+3Fh+hWnd]
0x1800412af  test    rbx, rbx
0x1800412b2  jnz     short loc_1800412F1
0x1800412b4  mov     edx, [rsp+120h+nSavedDC]; nSavedDC
0x1800412b8  mov     rcx, rsi; hdc
0x1800412bb  call    cs:__imp_RestoreDC
0x1800412c2  nop     dword ptr [rax+rax+00h]
0x1800412c7  cmp     dword ptr [rsp+120h+var_C8], ebx
0x1800412cb  jz      short loc_180041323
0x1800412cd  mov     rax, [r14+88h]
0x1800412d4  mov     rcx, [rax+278h]; hWnd
0x1800412db  test    rcx, rcx
0x1800412de  jz      short loc_180041323
0x1800412e0  mov     rdx, rsi; hDC
0x1800412e3  call    cs:__imp_ReleaseDC
0x1800412ea  nop     dword ptr [rax+rax+00h]
0x1800412ef  jmp     short loc_180041323
0x1800412f1  mov     rdx, rsi; hDC
0x1800412f4  mov     rcx, rbx; hWnd
0x1800412f7  call    cs:__imp_ReleaseDC
0x1800412fe  nop     dword ptr [rax+rax+00h]
0x180041303  mov     rax, [r14+88h]
0x18004130a  mov     [rax+278h], rbx
0x180041311  mov     rax, [r14+88h]
0x180041318  mov     qword ptr [rax+270h], 0
0x180041323  mov     eax, r12d
0x180041326  jmp     loc_180041211
0x18004132b  mov     rcx, rsi; hWnd
0x18004132e  call    ?GetCleanHdc@@YAPEAUHDC__@@PEAUHWND__@@@Z; GetCleanHdc(HWND__ *)
0x180041333  mov     rsi, rax
0x180041336  test    rax, rax
0x180041339  jnz     loc_18004145F
0x18004133f  lea     eax, [rsi+7]
0x180041342  jmp     loc_180041211
0x180041347  movss   xmm6, dword ptr [rbx]
0x18004134b  movaps  xmm0, xmm6; float
0x18004134e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180041353  movss   xmm7, dword ptr [rbx+4]
0x180041358  movaps  xmm0, xmm7; float
0x18004135b  mov     [rbp+3Fh+xf.eM11], eax
0x18004135e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180041363  addss   xmm6, dword ptr [rbx+8]
0x180041368  mov     [rbp+3Fh+xf.eM12], eax
0x18004136b  movaps  xmm0, xmm6; float
0x18004136e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180041373  addss   xmm7, dword ptr [rbx+0Ch]
0x180041378  mov     [rbp+3Fh+xf.eM21], eax
0x18004137b  movaps  xmm0, xmm7; float
0x18004137e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180041383  mov     [rbp+3Fh+xf.eM22], eax
0x180041386  cmp     [rbp+3Fh+arg_28], r12d
0x18004138a  jz      loc_18004148C
0x180041390  lea     rbx, [rsp+120h+var_E0]
0x180041395  mov     edi, 2
0x18004139a  mov     rcx, rbx; this
0x18004139d  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x1800413a2  add     rbx, 8
0x1800413a6  sub     rdi, 1
0x1800413aa  jnz     short loc_18004139A
0x1800413ac  movss   xmm0, dword ptr [r13+0]
0x1800413b2  lea     rcx, [r15+1488h]; this
0x1800413b9  movss   xmm1, dword ptr [r13+4]
0x1800413bf  lea     r8d, [rdi+2]; int
0x1800413c3  movss   [rsp+120h+var_E0], xmm0
0x1800413c9  lea     rdx, [rsp+120h+var_E0]; struct PointF *
0x1800413ce  addss   xmm0, dword ptr [r13+8]
0x1800413d4  movss   [rsp+120h+var_DC], xmm1
0x1800413da  addss   xmm1, dword ptr [r13+0Ch]
0x1800413e0  movss   [rsp+120h+var_D8], xmm0
0x1800413e6  movss   [rsp+120h+var_D4], xmm1
0x1800413ec  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x1800413f1  movss   xmm0, [rsp+120h+var_E0]; float
0x1800413f7  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800413fc  movss   xmm0, [rsp+120h+var_DC]; float
0x180041402  mov     edi, eax
0x180041404  mov     dword ptr [rbp+3Fh+var_B8], eax
0x180041407  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004140c  movss   xmm0, [rsp+120h+var_D8]; float
0x180041412  mov     r13d, eax
0x180041415  mov     dword ptr [rbp+3Fh+var_B8+4], eax
0x180041418  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004141d  movss   xmm0, [rsp+120h+var_D4]; float
0x180041423  mov     ebx, eax
0x180041425  mov     dword ptr [rbp+3Fh+var_B8+8], eax
0x180041428  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18004142d  mov     dword ptr [rbp+3Fh+var_B8+0Ch], eax
0x180041430  cmp     edi, ebx
0x180041432  jge     loc_18004128E
0x180041438  cmp     r13d, eax
0x18004143b  jge     loc_18004128E
0x180041441  lea     rax, EnumEmfWithDownLevel
0x180041448  mov     [rsp+120h+var_F0], r12d
0x18004144d  mov     [rsp+120h+var_F8], rax
0x180041452  lea     r9, [rbp+3Fh+var_B8]
0x180041456  lea     rax, [rbp+3Fh+xf]
0x18004145a  jmp     loc_1800415BF
0x18004145f  mov     rax, [r14+88h]
0x180041466  mov     [rsp+120h+nSavedDC], 0FFFFFFFFh
0x18004146e  mov     qword ptr [rax+278h], 0
0x180041479  mov     rax, [r14+88h]
0x180041480  mov     [rax+270h], rsi
0x180041487  jmp     loc_180041267
0x18004148c  movss   xmm7, dword ptr [r13+0]
0x180041492  mov     bl, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180041498  movaps  xmm1, xmm7
0x18004149b  addss   xmm1, cs:__real@3f000000
0x1800414a3  test    bl, bl
0x1800414a5  jnz     loc_1800415DC
0x1800414ab  cvtps2pd xmm0, xmm1; X
0x1800414ae  call    floor
0x1800414b3  cvttsd2si eax, xmm0
0x1800414b7  movss   xmm6, dword ptr [r13+4]
0x1800414bd  mov     [rbp+3Fh+xf.eM11], eax
0x1800414c0  movaps  xmm1, xmm6
0x1800414c3  mov     [rsp+120h+var_E0], eax
0x1800414c7  addss   xmm1, cs:__real@3f000000
0x1800414cf  test    bl, bl
0x1800414d1  jnz     loc_1800415EE
0x1800414d7  cvtps2pd xmm0, xmm1; X
0x1800414da  call    floor
0x1800414df  cvttsd2si eax, xmm0
0x1800414e3  mov     [rsp+120h+var_D0], eax
0x1800414e7  mov     [rsp+120h+var_DC], eax
0x1800414eb  addss   xmm7, dword ptr [r13+8]
0x1800414f1  addss   xmm7, cs:__real@3f000000
0x1800414f9  test    bl, bl
0x1800414fb  jnz     loc_180041600
0x180041501  cvtps2pd xmm0, xmm7; X
0x180041504  call    floor
0x180041509  cvttsd2si edi, xmm0
0x18004150d  mov     [rsp+120h+var_D8], edi
0x180041511  addss   xmm6, dword ptr [r13+0Ch]
0x180041517  addss   xmm6, cs:__real@3f000000
0x18004151f  test    bl, bl
0x180041521  jnz     loc_180041612
0x180041527  cvtps2pd xmm0, xmm6; X
0x18004152a  call    floor
0x18004152f  cvttsd2si eax, xmm0
0x180041533  mov     [rsp+120h+var_D4], eax
0x180041537  cmp     eax, [rsp+120h+var_D0]
0x18004153b  jle     loc_18004128E
0x180041541  cmp     edi, [rbp+3Fh+xf.eM11]
0x180041544  jle     loc_18004128E
0x18004154a  lea     rbx, [r15+1488h]
0x180041551  cmp     [rbp+3Fh+arg_30], r12d
0x180041555  jnz     loc_180041631
0x18004155b  mov     edx, 2; iMode
0x180041560  mov     rcx, rsi; hdc
0x180041563  call    cs:__imp_SetGraphicsMode
0x18004156a  nop     dword ptr [rax+rax+00h]
0x18004156f  movups  xmm0, xmmword ptr [rbx+10h]
0x180041573  lea     rdx, [rbp+3Fh+xf]; lpxf
0x180041577  mov     rcx, rsi; hdc
0x18004157a  movss   xmm1, dword ptr [rbx+24h]
0x18004157f  movups  xmmword ptr [rbp+3Fh+xf.eM11], xmm0
0x180041583  movss   xmm0, dword ptr [rbx+20h]
0x180041588  movss   [rbp+3Fh+xf.eDx], xmm0
0x18004158d  movss   [rbp+3Fh+xf.eDy], xmm1
0x180041592  call    cs:__imp_SetWorldTransform
0x180041599  nop     dword ptr [rax+rax+00h]
0x18004159e  lea     rax, EnumEmfWithDownLevel
0x1800415a5  mov     [rsp+120h+var_F0], r12d
0x1800415aa  xorps   xmm0, xmm0
0x1800415ad  mov     [rsp+120h+var_F8], rax
0x1800415b2  lea     rax, [rbp+3Fh+var_B8]
0x1800415b6  movups  [rbp+3Fh+var_B8], xmm0
0x1800415ba  lea     r9, [rsp+120h+var_E0]
0x1800415bf  mov     r8, [rsp+120h+var_C0]
0x1800415c4  mov     rdx, rsi
0x1800415c7  mov     rcx, r15
0x1800415ca  mov     [rsp+120h+var_100], rax
0x1800415cf  call    ?EnumerateEmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHENHMETAFILE__@@PEBUtagRECT@@2P6AH0PEAUtagHANDLETABLE@@PEBUtagENHMETARECORD@@H_J@ZH@Z; MetafilePlayer::EnumerateEmfRecords(HDC__ *,HENHMETAFILE__ *,tagRECT const *,tagRECT const *,int (*)(HDC__ *,tagHANDLETABLE *,tagENHMETARECORD const *,int,__int64),int)
0x1800415d4  mov     r12d, eax
0x1800415d7  jmp     loc_18004128E
0x1800415dc  movaps  xmm0, xmm1
0x1800415df  roundss xmm0, xmm0, 9
0x1800415e5  cvttss2si eax, xmm0
0x1800415e9  jmp     loc_1800414B7
0x1800415ee  movaps  xmm0, xmm1
0x1800415f1  roundss xmm0, xmm0, 9
0x1800415f7  cvttss2si eax, xmm0
0x1800415fb  jmp     loc_1800414E3
0x180041600  movaps  xmm0, xmm7
0x180041603  roundss xmm0, xmm0, 9
0x180041609  cvttss2si edi, xmm0
0x18004160d  jmp     loc_18004150D
0x180041612  movaps  xmm0, xmm6
0x180041615  roundss xmm0, xmm0, 9
0x18004161b  cvttss2si eax, xmm0
0x18004161f  jmp     loc_180041533
0x180041624  mov     dword ptr [rsp+120h+var_C8], 1
0x18004162c  jmp     loc_180041245
0x180041631  mov     rax, [r14+88h]
0x180041638  lea     rdx, [r15+14D8h]
0x18004163f  mov     qword ptr [rbp+3Fh+xf.eM11], r12
0x180041643  lea     r9, [rbp+3Fh+xf]
0x180041647  mov     [rsp+120h+var_F8], rbx; GpMatrix *
0x18004164c  lea     r8, [rsp+120h+var_E0]
0x180041651  mov     [rsp+120h+var_100], rdx; __int64
0x180041656  mov     ecx, [rax+48h]
0x180041659  mov     [rdx], ecx
0x18004165b  mov     rdx, r13
0x18004165e  mov     rcx, rsi; hdc
0x180041661  call    CreateDibSection32Bpp
0x180041666  mov     rdi, rax
0x180041669  mov     r12d, 1
0x18004166f  test    rax, rax
0x180041672  jz      loc_180041737
0x180041678  xor     ecx, ecx; hdc
0x18004167a  call    cs:__imp_CreateCompatibleDC
0x180041681  nop     dword ptr [rax+rax+00h]
0x180041686  mov     rbx, rax
0x180041689  test    rax, rax
0x18004168c  jz      loc_180041723
0x180041692  mov     rcx, qword ptr [rbp+3Fh+xf.eM11]
0x180041696  mov     rdx, rdi; h
0x180041699  mov     [r15+14B8h], rcx
0x1800416a0  mov     ecx, [rsp+120h+var_D8]
0x1800416a4  mov     [r15+14C0h], ecx
0x1800416ab  mov     ecx, [rsp+120h+var_D4]
0x1800416af  mov     [r15+14C4h], ecx
0x1800416b6  mov     rcx, rax; hdc
0x1800416b9  movups  xmm0, xmmword ptr [r13+0]
  ... truncated ...
```
