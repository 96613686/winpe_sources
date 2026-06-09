# WarpRenderTarget::FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes(D2D_RECT_F const *,uint,RTDrawData const *,bool *)

- ea: `0x1800c50e0`
- end: `0x1800c6080`
- name: `?FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes@WarpRenderTarget@@AEAAJPEBUD2D_RECT_F@@IPEBVRTDrawData@@PEA_N@Z`
- size: `4000`
- prototype: `__int64 __usercall@<rax>(WarpRenderTarget *__hidden this@<rcx>, const struct D2D_RECT_F *@<rdx>, unsigned int@<r8d>, const struct RTDrawData *@<r9>, bool *)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800c28f0`
- `0x1800c3ed0`
- `0x1800c4b00`

## callees

- `0x180009510`
- `0x180012fb0`
- `0x18001fd58`
- `0x180084490`
- `0x180084870`
- `0x180084a10`
- `0x1800c4950`
- `0x1800c50e0`
- `0x1800c6090`
- `0x1800c60f0`
- `0x180121720`
- `0x1801fd630`
- `0x18025b100`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1800c53ac`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1800c5a54`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1800c53ac`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1800c5a54`

## string_xrefs

- `0x1800c6023`: `WarpRenderTarget::FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes`

## pseudocode

```c
__int64 __fastcall WarpRenderTarget::FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes(
        WarpRenderTarget *this,
        const struct D2D_RECT_F *a2,
        unsigned int a3,
        const struct RTDrawData *a4,
        bool *a5)
{
  bool *v5; // r15
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdx
  int *v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rdx
  float *v14; // rax
  float v15; // xmm3_4
  float v16; // xmm4_4
  float v17; // xmm11_4
  float v18; // xmm13_4
  float v19; // xmm2_4
  float v20; // xmm1_4
  unsigned int v21; // xmm7_4
  float v22; // xmm9_4
  float v23; // xmm10_4
  float v24; // xmm2_4
  float v25; // xmm1_4
  float v26; // xmm5_4
  float v27; // xmm3_4
  float v28; // xmm6_4
  float v29; // xmm14_4
  float v30; // xmm8_4
  float v31; // xmm12_4
  float v32; // xmm14_4
  float v33; // xmm15_4
  float v34; // xmm9_4
  float v35; // xmm7_4
  float v36; // xmm1_4
  float v37; // xmm13_4
  __m128 v38; // xmm8
  float v39; // xmm6_4
  int CurrentInputClampBehavior; // eax
  __m128 v41; // xmm13
  unsigned int v42; // r12d
  D3DVALUE r; // ebx
  unsigned int v44; // ecx
  int *v45; // r8
  __int64 v46; // rdx
  unsigned int v47; // eax
  __m128 v48; // xmm13
  int v49; // eax
  _DWORD *v50; // r15
  __int64 v51; // rbx
  struct CHwShaderState *v52; // r11
  enum DXGI_FORMAT v53; // edx
  int v54; // ecx
  const struct D2D_RECT_F *v55; // r8
  bool v56; // zf
  int v57; // ecx
  struct D2D_RECT_F v58; // xmm0
  __int64 v59; // rax
  __int64 v60; // rcx
  enum DXGI_FORMAT v61; // edx
  __int64 result; // rax
  __int64 v63; // rbx
  int v64; // eax
  float v65; // xmm1_4
  __m128 v66; // xmm0
  __int64 v67; // rax
  int v68; // ebx
  float v69; // xmm0_4
  float v70; // xmm4_4
  float *v71; // rax
  float v72; // xmm9_4
  float v73; // xmm8_4
  float v74; // xmm10_4
  float v75; // xmm1_4
  float v76; // xmm2_4
  float v77; // xmm0_4
  float v78; // xmm3_4
  unsigned int v79; // xmm10_4
  float v80; // xmm2_4
  float v81; // xmm1_4
  float v82; // xmm4_4
  float v83; // xmm5_4
  float v84; // xmm3_4
  float v85; // xmm6_4
  float v86; // xmm14_4
  float v87; // xmm0_4
  float v88; // xmm8_4
  float v89; // xmm11_4
  float v90; // xmm7_4
  float v91; // xmm9_4
  float v92; // xmm15_4
  float v93; // xmm1_4
  float v94; // xmm12_4
  __int64 v95; // rdx
  const struct MILMatrix3x2 *v96; // rdx
  int RealizationInfoAndTextureMapping; // eax
  unsigned int v98; // ebx
  unsigned int v99; // eax
  __int64 v100; // r12
  __int64 i; // rcx
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rbx
  int v105; // eax
  unsigned int v106; // eax
  __m128 v107; // xmm0
  __int64 v108; // rcx
  char v109; // al
  unsigned int v110; // ecx
  _QWORD *v111; // rcx
  unsigned int v112; // xmm6_4
  unsigned int v113; // xmm7_4
  unsigned int v114; // xmm8_4
  unsigned int v115; // xmm9_4
  unsigned int v116; // xmm10_4
  unsigned int v117; // xmm11_4
  int v118; // ebx
  __int64 v119; // rax
  _QWORD *v120; // rax
  unsigned int v121; // xmm5_4
  unsigned int v122; // xmm4_4
  unsigned int v123; // xmm3_4
  unsigned int v124; // xmm2_4
  unsigned int v125; // xmm1_4
  unsigned int v126; // xmm0_4
  __int64 v127; // rdx
  __int128 *v128; // rax
  __int128 v129; // xmm3
  __int64 v130; // rbx
  enum DXGI_FORMAT v131; // eax
  const struct BatchedBrush *v132; // rdx
  int v133; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int g_low; // [rsp+3Ch] [rbp-CCh] BYREF
  enum DXGI_FORMAT v135; // [rsp+40h] [rbp-C8h] BYREF
  int v136; // [rsp+44h] [rbp-C4h]
  bool v137; // [rsp+48h] [rbp-C0h]
  int v138; // [rsp+4Ch] [rbp-BCh]
  _QWORD *v139; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v140; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v141; // [rsp+68h] [rbp-A0h]
  struct _D3DCOLORVALUE v142; // [rsp+70h] [rbp-98h] BYREF
  __int64 v143; // [rsp+80h] [rbp-88h] BYREF
  __int128 v144; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v145; // [rsp+98h] [rbp-70h]
  unsigned int v146; // [rsp+A8h] [rbp-60h]
  _DWORD *v147; // [rsp+B0h] [rbp-58h]
  int v148; // [rsp+B8h] [rbp-50h]
  __int128 v149; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 v150; // [rsp+D0h] [rbp-38h]
  const struct D2D_RECT_F *v151; // [rsp+D8h] [rbp-30h]
  bool *v152; // [rsp+E0h] [rbp-28h]
  __int128 v153; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v154; // [rsp+F8h] [rbp-10h]
  char v155[24]; // [rsp+100h] [rbp-8h] BYREF

  v5 = a5;
  v151 = a2;
  v152 = a5;
  v146 = 0;
  *a5 = 0;
  v147 = 0;
  SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(&v153, a2);
  SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(v155, v9);
  v11 = (int *)*((_QWORD *)a4 + 2);
  *(_QWORD *)&v142.r = 0;
  switch ( *v11 )
  {
    case 7:
      v12 = *((_QWORD *)v11 + 6);
      v13 = *((unsigned int *)this + 35);
      *(float *)&g_low = 0.0;
      *(float *)&v133 = 0.0;
      (*(void (__fastcall **)(__int64, __int64, unsigned int *, int *))(*(_QWORD *)v12 + 288LL))(
        v12,
        v13,
        &g_low,
        &v133);
      v14 = (float *)*((_QWORD *)a4 + 3);
      *(_QWORD *)((char *)&v153 + 4) = 0;
      v154 = 0;
      *(float *)&v153 = 96.0 / *(float *)&g_low;
      *((float *)&v153 + 3) = 96.0 / *(float *)&v133;
      v15 = *((float *)v11 + 6);
      v16 = *((float *)v11 + 7);
      v17 = *((float *)v11 + 2) * 0.0;
      v18 = *((float *)v11 + 3) * 0.0;
      v19 = *((float *)v11 + 4) * 0.0;
      v20 = *((float *)v11 + 5) * 0.0;
      *(float *)&v21 = (float)(*((float *)v11 + 3) * (float)(96.0 / *(float *)&g_low)) + v20;
      v22 = *((float *)v11 + 5) * (float)(96.0 / *(float *)&v133);
      v23 = (float)(*((float *)v11 + 4) * (float)(96.0 / *(float *)&v133)) + v17;
      *(float *)&v153 = (float)(*((float *)v11 + 2) * (float)(96.0 / *(float *)&g_low)) + v19;
      *((float *)&v153 + 2) = v23;
      *((float *)&v153 + 3) = v22 + v18;
      *(float *)&v154 = (float)(v17 + v19) + v15;
      *((float *)&v154 + 1) = (float)(v18 + v20) + v16;
      v24 = *v14;
      v25 = v14[2];
      v26 = v14[1];
      v27 = v14[4];
      v28 = v14[5];
      v29 = v26 * *(float *)&v153;
      v30 = v14[3];
      v31 = (float)(*v14 * *(float *)&v153) + (float)(v25 * *(float *)&v21);
      *(_QWORD *)&v153 = __PAIR64__(v21, LODWORD(v31));
      v32 = v29 + (float)(v30 * *(float *)&v21);
      v33 = (float)(v25 * (float)(v22 + v18)) + (float)(v24 * v23);
      *(_QWORD *)((char *)&v153 + 4) = __PAIR64__(LODWORD(v33), LODWORD(v32));
      v34 = 0.0;
      v35 = (float)((float)(*((float *)&v154 + 1) * v25) + (float)(*(float *)&v154 * v24)) + v27;
      *((float *)&v153 + 3) = (float)(v30 * *((float *)&v153 + 3)) + (float)(v26 * v23);
      v135 = SHIDWORD(v153);
      v36 = (float)(v31 * *((float *)&v153 + 3)) - (float)(v33 * v32);
      v37 = (float)((float)(*((float *)&v154 + 1) * v30) + (float)(*(float *)&v154 * v26)) + v28;
      v154 = __PAIR64__(LODWORD(v37), LODWORD(v35));
      if ( v36 != 0.0 )
      {
        v38 = (__m128)LODWORD(FLOAT_1_0);
        v39 = 1.0 / v36;
        if ( _finite((float)(1.0 / v36)) )
        {
          *(float *)&v153 = *(float *)&v135 * v39;
          *((float *)&v153 + 1) = COERCE_FLOAT(LODWORD(v32) ^ _xmm) * v39;
          *((float *)&v153 + 2) = COERCE_FLOAT(LODWORD(v33) ^ _xmm) * v39;
          *((float *)&v153 + 3) = v31 * v39;
          *((float *)&v154 + 1) = (float)((float)(v35 * v32) - (float)(v31 * v37)) * v39;
          *(float *)&v154 = (float)((float)(v37 * v33) - (float)(v35 * *(float *)&v135)) * v39;
          (*(void (__fastcall **)(_QWORD, _QWORD **))(**((_QWORD **)v11 + 6) + 272LL))(*((_QWORD *)v11 + 6), &v139);
          if ( (_DWORD)v139 )
          {
            if ( HIDWORD(v139) )
            {
              v143 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 232LL))(v12) + 64);
              v138 = *(_DWORD *)(v143 + 164);
              *(_QWORD *)&v142.r = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, struct _D3DCOLORVALUE *))(*(_QWORD *)v12 + 280LL))(
                                                v12,
                                                &v142);
              CurrentInputClampBehavior = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
              v41 = (__m128)(unsigned int)v11[1];
              if ( CurrentInputClampBehavior != 2 )
              {
                if ( CurrentInputClampBehavior )
                {
                  if ( CurrentInputClampBehavior == 1 )
                  {
                    v34 = FLOAT_N65504_0;
                    v38 = (__m128)LODWORD(FLOAT_65504_0);
                  }
                  else
                  {
                    v34 = FLOAT_N3_4028235e38;
                    v38 = (__m128)LODWORD(FLOAT_3_4028235e38);
                  }
                }
                if ( v41.m128_f32[0] > v38.m128_f32[0] )
                  v41 = v38;
                else
                  v41.m128_f32[0] = fmaxf(v41.m128_f32[0], v34);
              }
              v42 = v11[10];
              v136 = v11[8];
              v133 = v11[9];
              goto LABEL_11;
            }
          }
        }
      }
      goto LABEL_44;
    case 3:
      v96 = (const struct MILMatrix3x2 *)*((_QWORD *)a4 + 3);
      *(_QWORD *)&v142.r = &LinearGradientBrushDataWrapper::`vftable';
      *(_QWORD *)&v142.b = v11;
      *(float *)&g_low = 0.0;
      RealizationInfoAndTextureMapping = GradientBrushDataWrapperCommon::GetRealizationInfoAndTextureMapping(
                                           (GradientBrushDataWrapperCommon *)&v142,
                                           v96,
                                           &g_low,
                                           (struct MILMatrix3x2 *)&v153);
      v146 = RealizationInfoAndTextureMapping;
      v98 = RealizationInfoAndTextureMapping;
      if ( RealizationInfoAndTextureMapping < 0 )
      {
        DoStackCapture(RealizationInfoAndTextureMapping);
        return v98;
      }
      v99 = g_low;
      v100 = *((_QWORD *)v11 + 6);
      for ( i = 10; v99 != 1; v99 >>= 1 )
        i = (unsigned int)(i - 1);
      v102 = v100 + 80;
      if ( !v100 )
        v102 = 88;
      v103 = *(_QWORD *)(*(_QWORD *)v102 + 8 * i);
      DWORD1(v153) = 0;
      HIDWORD(v153) = 0;
      *((float *)&v154 + 1) = (float)*(int *)(v103 + 32) + 0.5;
      v105 = *(_DWORD *)(v103 + 28);
      v143 = *(_QWORD *)(v103 + 16);
      v104 = v143;
      v138 = v105;
      v106 = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
      v107 = (__m128)(unsigned int)v11[1];
      *(double *)v107.m128_u64 = ClampInputAlpha(v108, v106);
      r = *(float *)(v104 + 152);
      v41 = v107;
      if ( !v100 )
        v100 = 8;
      v139 = (_QWORD *)v100;
      v109 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 176LL))(v100);
      v110 = 1;
      if ( v109 )
        v110 = 3;
      v42 = 1;
      g_low = v110;
      v136 = (*(__int64 (__fastcall **)(_QWORD *))(*v139 + 128LL))(v139);
      *(float *)&v133 = 0.0;
      goto LABEL_13;
    case 10:
      v111 = (_QWORD *)*((_QWORD *)v11 + 1);
      v41 = (__m128)(unsigned int)v11[4];
      v112 = v11[5];
      v113 = v11[6];
      v114 = v11[7];
      v115 = v11[8];
      v116 = v11[9];
      v117 = v11[10];
      v42 = v11[11];
      v118 = v11[12];
      v135 = *((enum DXGI_FORMAT *)v11 + 13);
      v119 = *v111;
      v139 = v111;
      v143 = *(_QWORD *)((*(__int64 (**)(void))(v119 + 232))() + 64);
      v138 = *(_DWORD *)(v143 + 164);
      v120 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, struct _D3DCOLORVALUE *))(*v139 + 280LL))(v139, &v142);
      v121 = *((_DWORD *)this + 62);
      v122 = *((_DWORD *)this + 63);
      v123 = *((_DWORD *)this + 64);
      v124 = *((_DWORD *)this + 65);
      v125 = *((_DWORD *)this + 66);
      v126 = *((_DWORD *)this + 67);
      *(_QWORD *)&v142.r = *v120;
      *(_QWORD *)&v149 = __PAIR64__(v122, v121);
      *((_QWORD *)&v149 + 1) = __PAIR64__(v124, v123);
      v150 = __PAIR64__(v126, v125);
      *(_QWORD *)&v144 = __PAIR64__(v122, v121);
      *((_QWORD *)&v144 + 1) = __PAIR64__(v124, v123);
      v145 = __PAIR64__(v126, v125);
      if ( MILMatrix3x2::Invert((const struct MILMatrix3x2 *)&v144, (struct MILMatrix3x2 *)&v149) )
      {
        v127 = *((unsigned int *)this + 35);
        *(float *)&g_low = 0.0;
        *(float *)&v133 = 0.0;
        (*(void (__fastcall **)(_QWORD *, __int64, unsigned int *, int *))(*v139 + 288LL))(v139, v127, &g_low, &v133);
        *(_QWORD *)&v144 = __PAIR64__(v113, v112);
        *(_QWORD *)((char *)&v153 + 4) = 0;
        v154 = 0;
        *(_QWORD *)((char *)&v140 + 4) = 0;
        v141 = 0;
        *(float *)&v153 = 96.0 / *(float *)&g_low;
        *(float *)&v140 = 96.0 / *(float *)&g_low;
        *((float *)&v153 + 3) = 96.0 / *(float *)&v133;
        *((_QWORD *)&v144 + 1) = __PAIR64__(v115, v114);
        v145 = __PAIR64__(v117, v116);
        *((float *)&v140 + 3) = 96.0 / *(float *)&v133;
        D2D1::Matrix3x2F::SetProduct(
          (D2D1::Matrix3x2F *)&v153,
          (const struct D2D1::Matrix3x2F *)&v140,
          (const struct D2D1::Matrix3x2F *)&v144);
        v140 = v153;
        v145 = v150;
        v141 = v154;
        v144 = v149;
        D2D1::Matrix3x2F::SetProduct(
          (D2D1::Matrix3x2F *)&v153,
          (const struct D2D1::Matrix3x2F *)&v140,
          (const struct D2D1::Matrix3x2F *)&v144);
        v128 = (__int128 *)*((_QWORD *)a4 + 3);
        v140 = v153;
        v129 = *v128;
        v145 = *((_QWORD *)v128 + 2);
        v141 = v154;
        v144 = v129;
        D2D1::Matrix3x2F::SetProduct(
          (D2D1::Matrix3x2F *)&v153,
          (const struct D2D1::Matrix3x2F *)&v140,
          (const struct D2D1::Matrix3x2F *)&v144);
        v140 = v153;
        v141 = v154;
        if ( MILMatrix3x2::Invert((const struct MILMatrix3x2 *)&v140, (struct MILMatrix3x2 *)&v153) )
        {
          v133 = 1;
          if ( v118 == 2 )
            v136 = 2;
          else
            v136 = v118 == 1;
          if ( v135 == DXGI_FORMAT_R32G32B32A32_FLOAT )
          {
            v133 = 2;
          }
          else if ( v135 != DXGI_FORMAT_R32G32B32A32_TYPELESS )
          {
            *(float *)&v133 = 0.0;
          }
LABEL_11:
          if ( v42 > 1 )
            return 0;
          goto LABEL_12;
        }
      }
LABEL_44:
      DoStackCapture(-2003197951);
      return 2291769345LL;
    case 11:
      v63 = *((_QWORD *)v11 + 8);
      v147 = (_DWORD *)*((_QWORD *)v11 + 9);
      *(_QWORD *)&v142.r = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 280LL))(
                                        v63,
                                        &v143);
      v64 = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
      v41 = (__m128)(unsigned int)v11[1];
      if ( v64 != 2 )
      {
        if ( v64 )
        {
          if ( v64 == 1 )
          {
            v65 = FLOAT_N65504_0;
            v66 = (__m128)LODWORD(FLOAT_65504_0);
          }
          else
          {
            v65 = FLOAT_N3_4028235e38;
            v66 = (__m128)LODWORD(FLOAT_3_4028235e38);
          }
        }
        else
        {
          v65 = 0.0;
          v66 = (__m128)LODWORD(FLOAT_1_0);
        }
        if ( v41.m128_f32[0] > v66.m128_f32[0] )
          v41 = v66;
        else
          v41.m128_f32[0] = fmaxf(v41.m128_f32[0], v65);
      }
      v42 = v11[14];
      v136 = v11[12];
      v133 = v11[13];
      v143 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 232LL))(v63) + 64);
      v138 = *(_DWORD *)(v143 + 164);
      v67 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v147 + 232LL))(v147);
      v56 = *((_DWORD *)this + 35) == 1;
      v147 = *(_DWORD **)(v67 + 64);
      v68 = v147[41];
      if ( v56 )
      {
        v69 = FLOAT_96_0;
        v70 = FLOAT_1_0;
      }
      else
      {
        v69 = *((float *)this + 46);
        v70 = 96.0 / *((float *)this + 47);
      }
      v71 = (float *)*((_QWORD *)a4 + 3);
      *(_QWORD *)((char *)&v153 + 4) = 0;
      v154 = 0;
      *(float *)&v153 = 96.0 / v69;
      v72 = *((float *)v11 + 5);
      v73 = *((float *)v11 + 2);
      v74 = *((float *)v11 + 4);
      v75 = *((float *)v11 + 6);
      v76 = *((float *)v11 + 7);
      v77 = v74 * 0.0;
      v78 = *((float *)v11 + 3) * 0.0;
      *((float *)&v153 + 1) = (float)(*((float *)v11 + 3) * *(float *)&v153) + (float)(v72 * 0.0);
      *(float *)&v79 = (float)(v74 * v70) + (float)(v73 * 0.0);
      *(float *)&v153 = (float)(v73 * *(float *)&v153) + v77;
      *((_QWORD *)&v153 + 1) = __PAIR64__(LODWORD(v70), v79);
      *((float *)&v154 + 1) = (float)((float)(v72 * 0.0) + v78) + v76;
      *((float *)&v153 + 3) = (float)(v72 * v70) + v78;
      *(float *)&v154 = (float)((float)(v73 * 0.0) + v77) + v75;
      v80 = *v71;
      v81 = v71[2];
      v82 = v71[3];
      v83 = v71[1];
      v84 = v71[4];
      v85 = v71[5];
      v86 = (float)(v81 * *((float *)&v153 + 1)) + (float)(*v71 * *(float *)&v153);
      v87 = v83 * *(float *)&v153;
      *(float *)&v153 = v86;
      v88 = (float)(v82 * *((float *)&v153 + 1)) + v87;
      *((float *)&v153 + 1) = v88;
      *(float *)&g_low = (float)(v81 * *((float *)&v153 + 3)) + (float)(v80 * *(float *)&v79);
      *((float *)&v153 + 2) = *(float *)&g_low;
      v89 = *(float *)&v154 * v83;
      *((float *)&v153 + 3) = (float)(v82 * *((float *)&v153 + 3)) + (float)(v83 * *(float *)&v79);
      v135 = SHIDWORD(v153);
      v90 = (float)((float)(*((float *)&v154 + 1) * v81) + (float)(*(float *)&v154 * v80)) + v84;
      *(float *)&v154 = v90;
      v91 = *((float *)&v153 + 3);
      v92 = (float)((float)(*((float *)&v154 + 1) * v82) + v89) + v85;
      *((float *)&v154 + 1) = v92;
      v93 = (float)(v86 * *((float *)&v153 + 3)) - (float)(*(float *)&g_low * v88);
      if ( v93 != 0.0 )
      {
        v94 = 1.0 / v93;
        if ( _finite((float)(1.0 / v93)) )
        {
          LODWORD(v139) = v68;
          *(float *)&v153 = v94 * v91;
          *((float *)&v153 + 1) = COERCE_FLOAT(LODWORD(v88) ^ _xmm) * v94;
          *((float *)&v153 + 2) = COERCE_FLOAT(g_low ^ _xmm) * v94;
          *((float *)&v153 + 3) = v94 * v86;
          *((float *)&v154 + 1) = (float)((float)(v90 * v88) - (float)(v86 * v92)) * v94;
          *(float *)&v154 = (float)((float)(v92 * *(float *)&g_low) - (float)(v90 * v91)) * v94;
          goto LABEL_11;
        }
      }
      goto LABEL_44;
  }
  v143 = 0;
  v136 = 0;
  *(float *)&v133 = 0.0;
  v42 = 0;
  v41 = 0;
  PrintAssertionMessageW(
    L"Unexpected brush type",
    v10,
    L"WarpRenderTarget::FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes",
    L"onecoreuap\\windows\\direct2d\\core\\hw\\warprt.cpp",
    0x1E2u);
  __int2c();
LABEL_12:
  r = v142.r;
  g_low = LODWORD(v142.g);
LABEL_13:
  v44 = 0;
  v45 = dword_18030EAE0;
  while ( 1 )
  {
    if ( v44 >= 0x1C )
      return 0;
    v46 = 5LL * (int)v44;
    if ( LODWORD(r) == dword_18030EAE0[10 * v44] )
      break;
    ++v44;
  }
  if ( (dword_18030EAE0[10 * v44 + 8] & 0x200) == 0 )
    return 0;
  v47 = *((_DWORD *)a4 + 10);
  if ( v47 )
  {
    if ( v47 <= 1 )
    {
      v130 = **((_QWORD **)a4 + 4);
      if ( (unsigned int)(**(_DWORD **)(v130 + 8) - 1) <= 1 )
      {
        *(float *)&v131 = COERCE_FLOAT(CBaseRenderTarget::GetDxgiFormatRoundTrip(this));
        v132 = *(const struct BatchedBrush **)(v130 + 8);
        v135 = v131;
        v41.m128_f32[0] = v41.m128_f32[0] * D2DSolidColorBrush::GetColor(&v142, v132, &v135)->a;
        goto LABEL_19;
      }
    }
    return 0;
  }
LABEL_19:
  v148 = *((_DWORD *)this + 32);
  v48 = _mm_shuffle_ps(v41, v41, 0);
  v142.r = *(D3DVALUE *)(*(_QWORD *)a4 + 8LL);
  v49 = (*(__int64 (__fastcall **)(WarpRenderTarget *, __int64, int *))(*(_QWORD *)this + 600LL))(this, v46, v45);
  *(float *)&v135 = 0.0;
  if ( !a3 )
    goto LABEL_28;
  v50 = v147;
  v137 = v49 == 3;
  do
  {
    v51 = *((_QWORD *)this + 106);
    if ( *(_DWORD *)(v51 + 4088) >= 0xC8u )
    {
      v95 = 10;
    }
    else
    {
      if ( (unsigned int)(*(_DWORD *)(v51 + 4032) + *(_DWORD *)(v51 + 4036)) <= 0xEB && *(_DWORD *)(v51 + 75600) != 128 )
        goto LABEL_24;
      if ( (unsigned int)(*(_DWORD *)(v51 + 4032) + *(_DWORD *)(v51 + 4036)) > 0xEB )
        v95 = 11;
      else
        v95 = (unsigned int)(*(_DWORD *)(v51 + 75600) != 128) + 12;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v51 + 24) + 560LL))(*(_QWORD *)(v51 + 24), v95);
LABEL_24:
    v52 = CHwDeferredRenderingCallBuffer::LockForNewCall((CHwDeferredRenderingCallBuffer *)(v51 + 4088));
    v53 = v135;
    *(_DWORD *)(v51 + 4032) += *(_DWORD *)(v51 + 4036);
    v54 = *(_DWORD *)(v51 + 4032);
    v55 = v151;
    *(_DWORD *)(v51 + 4036) = 0;
    *(_DWORD *)(v51 + 4040) = 4;
    *(_WORD *)(*(_QWORD *)(v51 + 16) + 48LL) = v54;
    *((_BYTE *)v52 + 288) = 0;
    v56 = g_low == 3;
    *((_QWORD *)v52 + 35) = 0;
    v57 = *v11;
    *(_DWORD *)v52 = 9;
    v58 = v55[v53];
    *((_DWORD *)v52 + 51) = v148;
    *((_DWORD *)v52 + 52) = LODWORD(v142.r);
    *((_BYTE *)v52 + 212) = v137;
    *((_DWORD *)v52 + 48) = v136;
    *((float *)v52 + 49) = *(float *)&v133;
    *((_BYTE *)v52 + 213) = v56;
    v59 = v143;
    *(_DWORD *)((char *)v52 + 214) = 256;
    *((_DWORD *)v52 + 50) = v42;
    *(struct D2D_RECT_F *)((char *)v52 + 8) = v58;
    *(__m128 *)((char *)v52 + 24) = v48;
    *((_QWORD *)v52 + 21) = v59;
    *((_DWORD *)v52 + 46) = v138;
    *(_OWORD *)((char *)v52 + 104) = v153;
    *((_QWORD *)v52 + 15) = v154;
    if ( v57 == 11 )
    {
      *((_DWORD *)v52 + 47) = (_DWORD)v139;
      *((_BYTE *)v52 + 217) = 1;
      *((_QWORD *)v52 + 22) = v50;
    }
    v60 = *((_QWORD *)this + 106);
    v61 = v53 + 1;
    v135 = v61;
    *(_BYTE *)(v60 + 74544) = 0;
  }
  while ( v61 < a3 );
  v5 = v152;
LABEL_28:
  result = v146;
  *v5 = 1;
  return result;
}

```

## disassembly

```asm
0x1800c50e0  mov     rax, rsp
0x1800c50e3  mov     [rax+10h], rbx
0x1800c50e7  push    rbp
0x1800c50e8  push    rsi
0x1800c50e9  push    rdi
0x1800c50ea  push    r12
0x1800c50ec  push    r13
0x1800c50ee  push    r14
0x1800c50f0  push    r15
0x1800c50f2  lea     rbp, [rax-0F8h]
0x1800c50f9  sub     rsp, 1C0h
0x1800c5100  movaps  xmmword ptr [rax-48h], xmm6
0x1800c5104  movaps  xmmword ptr [rax-58h], xmm7
0x1800c5108  movaps  xmmword ptr [rax-68h], xmm8
0x1800c510d  movaps  xmmword ptr [rax-78h], xmm9
0x1800c5112  movaps  xmmword ptr [rax-88h], xmm10
0x1800c511a  movaps  xmmword ptr [rax-98h], xmm11
0x1800c5122  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800c512a  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800c5132  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800c513a  movaps  xmmword ptr [rax-0D8h], xmm15
0x1800c5142  mov     rax, cs:__security_cookie
0x1800c5149  xor     rax, rsp
0x1800c514c  mov     [rbp+0F0h+var_E0], rax
0x1800c5150  mov     r15, [rbp+0F0h+arg_20]
0x1800c5157  xor     ebx, ebx
0x1800c5159  mov     rsi, rcx
0x1800c515c  mov     [rbp+0F0h+var_120], rdx
0x1800c5160  lea     rcx, [rbp+0F0h+var_110]
0x1800c5164  mov     [rbp+0F0h+var_118], r15
0x1800c5168  mov     r14, r9
0x1800c516b  mov     [rbp+0F0h+var_150], ebx
0x1800c516e  mov     [r15], bl
0x1800c5171  mov     r13d, r8d
0x1800c5174  mov     [rbp+0F0h+var_148], rbx
0x1800c5178  call    ?AsPodInfo@?$SvgPodInfo@VSvgLineElement@@U?$SvgLengthAttribute@$00@@@@UEBAPEBUISvgPodInfo@@XZ; SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(void)
0x1800c517d  lea     rcx, [rbp+0F0h+var_F8]
0x1800c5181  call    ?AsPodInfo@?$SvgPodInfo@VSvgLineElement@@U?$SvgLengthAttribute@$00@@@@UEBAPEBUISvgPodInfo@@XZ; SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(void)
0x1800c5186  mov     rdi, [r14+10h]
0x1800c518a  mov     qword ptr [rsp+1F0h+var_188], rbx
0x1800c518f  mov     ecx, [rdi]
0x1800c5191  cmp     ecx, 7
0x1800c5194  jnz     loc_1800C5780
0x1800c519a  mov     rbx, [rdi+30h]
0x1800c519e  lea     r9, [rsp+1F0h+var_1C0]
0x1800c51a3  mov     edx, [rsi+8Ch]
0x1800c51a9  lea     r8, [rsp+1F0h+var_1BC]
0x1800c51ae  mov     [rsp+1F0h+var_1BC], 0
0x1800c51b6  mov     rcx, rbx
0x1800c51b9  mov     [rsp+1F0h+var_1C0], 0
0x1800c51c1  xorps   xmm6, xmm6
0x1800c51c4  mov     rax, [rbx]
0x1800c51c7  mov     rax, [rax+120h]
0x1800c51ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c51d3  mov     rax, [r14+18h]
0x1800c51d7  movss   xmm5, cs:__real@42c00000
0x1800c51df  mov     qword ptr [rbp+0F0h+var_110+4], 0
0x1800c51e7  movaps  xmm0, xmm5
0x1800c51ea  divss   xmm0, [rsp+1F0h+var_1BC]
0x1800c51f0  mov     [rbp+0F0h+var_100], 0
0x1800c51f8  divss   xmm5, [rsp+1F0h+var_1C0]
0x1800c51fe  movss   dword ptr [rbp+0F0h+var_110], xmm0
0x1800c5203  movss   dword ptr [rbp+0F0h+var_110+0Ch], xmm5
0x1800c5208  movss   xmm11, dword ptr [rdi+8]
0x1800c520e  movss   xmm13, dword ptr [rdi+0Ch]
0x1800c5214  movaps  xmm8, xmm11
0x1800c5218  movss   xmm10, dword ptr [rdi+10h]
0x1800c521e  movaps  xmm7, xmm13
0x1800c5222  movss   xmm9, dword ptr [rdi+14h]
0x1800c5228  movaps  xmm2, xmm10
0x1800c522c  movss   xmm3, dword ptr [rdi+18h]
0x1800c5231  movaps  xmm1, xmm9
0x1800c5235  movss   xmm4, dword ptr [rdi+1Ch]
0x1800c523a  mulss   xmm8, xmm0
0x1800c523f  mulss   xmm7, xmm0
0x1800c5243  mulss   xmm11, xmm6
0x1800c5248  mulss   xmm13, xmm6
0x1800c524d  mulss   xmm2, xmm6
0x1800c5251  mulss   xmm1, xmm6
0x1800c5255  addss   xmm8, xmm2
0x1800c525a  mulss   xmm10, xmm5
0x1800c525f  addss   xmm7, xmm1
0x1800c5263  mulss   xmm9, xmm5
0x1800c5268  addss   xmm10, xmm11
0x1800c526d  movss   dword ptr [rbp+0F0h+var_110], xmm8
0x1800c5273  addss   xmm11, xmm2
0x1800c5278  addss   xmm9, xmm13
0x1800c527d  movss   dword ptr [rbp+0F0h+var_110+4], xmm7
0x1800c5282  addss   xmm13, xmm1
0x1800c5287  movss   dword ptr [rbp+0F0h+var_110+8], xmm10
0x1800c528d  addss   xmm11, xmm3
0x1800c5292  movss   dword ptr [rbp+0F0h+var_110+0Ch], xmm9
0x1800c5298  addss   xmm13, xmm4
0x1800c529d  movss   dword ptr [rbp+0F0h+var_100], xmm11
0x1800c52a3  movss   dword ptr [rbp+0F0h+var_100+4], xmm13
0x1800c52a9  movss   xmm2, dword ptr [rax]
0x1800c52ad  movss   xmm1, dword ptr [rax+8]
0x1800c52b2  movaps  xmm12, xmm2
0x1800c52b6  movss   xmm5, dword ptr [rax+4]
0x1800c52bb  movaps  xmm0, xmm1
0x1800c52be  movss   xmm4, dword ptr [rax+0Ch]
0x1800c52c3  movaps  xmm14, xmm5
0x1800c52c7  movss   xmm3, dword ptr [rax+10h]
0x1800c52cc  movaps  xmm15, xmm1
0x1800c52d0  movss   xmm6, dword ptr [rax+14h]
0x1800c52d5  mulss   xmm0, xmm7
0x1800c52d9  mulss   xmm12, xmm8
0x1800c52de  mulss   xmm14, xmm8
0x1800c52e3  movaps  xmm8, xmm4
0x1800c52e7  addss   xmm12, xmm0
0x1800c52ec  mulss   xmm15, xmm9
0x1800c52f1  movaps  xmm0, xmm4
0x1800c52f4  mulss   xmm8, xmm9
0x1800c52f9  mulss   xmm0, xmm7
0x1800c52fd  movss   dword ptr [rbp+0F0h+var_110], xmm12
0x1800c5303  addss   xmm14, xmm0
0x1800c5308  movaps  xmm0, xmm2
0x1800c530b  mulss   xmm0, xmm10
0x1800c5310  addss   xmm15, xmm0
0x1800c5315  movss   dword ptr [rbp+0F0h+var_110+4], xmm14
0x1800c531b  movaps  xmm0, xmm5
0x1800c531e  mulss   xmm0, xmm10
0x1800c5323  movss   dword ptr [rbp+0F0h+var_110+8], xmm15
0x1800c5329  addss   xmm8, xmm0
0x1800c532e  movaps  xmm7, xmm13
0x1800c5332  movss   [rsp+1F0h+var_1B8], xmm8
0x1800c5339  mulss   xmm7, xmm1
0x1800c533d  movaps  xmm0, xmm11
0x1800c5341  mulss   xmm0, xmm2
0x1800c5345  movaps  xmm1, xmm12
0x1800c5349  mulss   xmm13, xmm4
0x1800c534e  xorps   xmm9, xmm9
0x1800c5352  addss   xmm7, xmm0
0x1800c5356  mulss   xmm11, xmm5
0x1800c535b  movaps  xmm0, xmm15
0x1800c535f  mulss   xmm1, xmm8
0x1800c5364  mulss   xmm0, xmm14
0x1800c5369  addss   xmm13, xmm11
0x1800c536e  addss   xmm7, xmm3
0x1800c5372  movss   dword ptr [rbp+0F0h+var_110+0Ch], xmm8
0x1800c5378  subss   xmm1, xmm0
0x1800c537c  addss   xmm13, xmm6
0x1800c5381  movss   dword ptr [rbp+0F0h+var_100], xmm7
0x1800c5386  ucomiss xmm1, xmm9
0x1800c538a  movss   dword ptr [rbp+0F0h+var_100+4], xmm13
0x1800c5390  jp      short loc_1800C5398
0x1800c5392  jz      loc_1800C5AE7
0x1800c5398  movss   xmm8, cs:__real@3f800000
0x1800c53a1  movaps  xmm6, xmm8
0x1800c53a5  divss   xmm6, xmm1
0x1800c53a9  cvtps2pd xmm0, xmm6; X
0x1800c53ac  call    cs:__imp__finite
0x1800c53b2  test    eax, eax
0x1800c53b4  jz      loc_1800C5AE7
0x1800c53ba  movss   xmm3, [rsp+1F0h+var_1B8]
0x1800c53c0  lea     rdx, [rsp+1F0h+var_1A8]
0x1800c53c5  movaps  xmm0, xmm3
0x1800c53c8  movaps  xmm1, xmm14
0x1800c53cc  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800c53d3  mulss   xmm0, xmm6
0x1800c53d7  mulss   xmm1, xmm6
0x1800c53db  movss   dword ptr [rbp+0F0h+var_110], xmm0
0x1800c53e0  movaps  xmm0, xmm15
0x1800c53e4  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800c53eb  movss   dword ptr [rbp+0F0h+var_110+4], xmm1
0x1800c53f0  movaps  xmm1, xmm13
0x1800c53f4  mulss   xmm0, xmm6
0x1800c53f8  mulss   xmm1, xmm15
0x1800c53fd  movss   dword ptr [rbp+0F0h+var_110+8], xmm0
0x1800c5402  movaps  xmm0, xmm12
0x1800c5406  mulss   xmm0, xmm6
0x1800c540a  mulss   xmm12, xmm13
0x1800c540f  movss   dword ptr [rbp+0F0h+var_110+0Ch], xmm0
0x1800c5414  movaps  xmm0, xmm7
0x1800c5417  mulss   xmm7, xmm14
0x1800c541c  mulss   xmm0, xmm3
0x1800c5420  subss   xmm7, xmm12
0x1800c5425  subss   xmm1, xmm0
0x1800c5429  mulss   xmm7, xmm6
0x1800c542d  mulss   xmm1, xmm6
0x1800c5431  movss   dword ptr [rbp+0F0h+var_100+4], xmm7
0x1800c5436  movss   dword ptr [rbp+0F0h+var_100], xmm1
0x1800c543b  mov     rcx, [rdi+30h]
0x1800c543f  mov     rax, [rcx]
0x1800c5442  mov     rax, [rax+110h]
0x1800c5449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c544e  cmp     dword ptr [rsp+1F0h+var_1A8], 0
0x1800c5453  jz      loc_1800C5AE7
0x1800c5459  cmp     dword ptr [rsp+1F0h+var_1A8+4], 0
0x1800c545e  jz      loc_1800C5AE7
0x1800c5464  mov     rax, [rbx]
0x1800c5467  mov     rcx, rbx
0x1800c546a  mov     rax, [rax+0E8h]
0x1800c5471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5476  lea     rdx, [rsp+1F0h+var_188]
0x1800c547b  mov     rcx, rbx
0x1800c547e  mov     rax, [rax+40h]
0x1800c5482  mov     [rsp+1F0h+var_178], rax
0x1800c5487  mov     eax, [rax+0A4h]
0x1800c548d  mov     dword ptr [rsp+1F0h+var_1B0+4], eax
0x1800c5491  mov     rax, [rbx]
0x1800c5494  mov     rax, [rax+118h]
0x1800c549b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c54a0  mov     rcx, [rax]
0x1800c54a3  mov     qword ptr [rsp+1F0h+var_188], rcx
0x1800c54a8  mov     rcx, rsi
0x1800c54ab  call    ?GetCurrentInputClampBehavior@CBaseRenderTarget@@QEBA?AW4Enum@InputClampBehavior@@XZ; CBaseRenderTarget::GetCurrentInputClampBehavior(void)
0x1800c54b0  movss   xmm13, dword ptr [rdi+4]
0x1800c54b6  cmp     eax, 2
0x1800c54b9  jz      short loc_1800C54D2
0x1800c54bb  test    eax, eax
0x1800c54bd  jnz     loc_1800C5C54
0x1800c54c3  comiss  xmm13, xmm8
0x1800c54c7  ja      loc_1800C5F8F
0x1800c54cd  maxss   xmm13, xmm9
0x1800c54d2  mov     eax, [rdi+20h]
0x1800c54d5  mov     r12d, [rdi+28h]
0x1800c54d9  mov     [rsp+1F0h+var_1B4], eax
0x1800c54dd  mov     eax, [rdi+24h]
0x1800c54e0  mov     [rsp+1F0h+var_1C0], eax
0x1800c54e4  cmp     r12d, 1
0x1800c54e8  ja      loc_1800C577C
0x1800c54ee  mov     eax, dword ptr [rsp+1F0h+var_188.4]
0x1800c54f2  mov     ebx, dword ptr [rsp+1F0h+var_188]
0x1800c54f6  mov     [rsp+1F0h+var_1BC], eax
0x1800c54fa  xor     ecx, ecx
0x1800c54fc  lea     r8, dword_18030EAE0
0x1800c5503  cmp     ecx, 1Ch
0x1800c5506  jnb     loc_1800C577C
0x1800c550c  movsxd  rax, ecx
0x1800c550f  lea     rdx, [rax+rax*4]
0x1800c5513  cmp     ebx, [r8+rdx*8]
0x1800c5517  jz      short loc_1800C551D
0x1800c5519  inc     ecx
0x1800c551b  jmp     short loc_1800C5503
0x1800c551d  test    dword ptr [r8+rdx*8+20h], 200h
0x1800c5526  jz      loc_1800C577C
0x1800c552c  mov     eax, [r14+28h]
0x1800c5530  test    eax, eax
0x1800c5532  jnz     loc_1800C5773
0x1800c5538  mov     eax, [rsi+80h]
0x1800c553e  mov     rcx, rsi
0x1800c5541  mov     [rbp+0F0h+var_140], eax
0x1800c5544  mov     rax, [r14]
0x1800c5547  shufps  xmm13, xmm13, 0
0x1800c554c  mov     eax, [rax+8]
0x1800c554f  mov     dword ptr [rsp+1F0h+var_188], eax
0x1800c5553  mov     rax, [rsi]
0x1800c5556  mov     rax, [rax+258h]
0x1800c555d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5562  mov     [rsp+1F0h+var_1B8], 0
0x1800c556a  test    r13d, r13d
0x1800c556d  jz      loc_1800C570D
0x1800c5573  mov     r15, [rbp+0F0h+var_148]
0x1800c5577  cmp     eax, 3
0x1800c557a  setz    byte ptr [rsp+1F0h+var_1B0]
0x1800c557f  mov     rbx, [rsi+350h]
0x1800c5586  cmp     dword ptr [rbx+0FF8h], 0C8h
0x1800c5590  jnb     loc_1800C5AFB
0x1800c5596  mov     eax, [rbx+0FC4h]
0x1800c559c  add     eax, [rbx+0FC0h]
0x1800c55a2  cmp     eax, 0EBh
0x1800c55a7  ja      loc_1800C5FA1
0x1800c55ad  cmp     dword ptr [rbx+12750h], 80h
0x1800c55b7  jz      loc_1800C5FA1
0x1800c55bd  lea     rcx, [rbx+0FF8h]; this
0x1800c55c4  call    ?LockForNewCall@CHwDeferredRenderingCallBuffer@@QEAAPEAVCHwShaderState@@XZ; CHwDeferredRenderingCallBuffer::LockForNewCall(void)
0x1800c55c9  mov     r11, rax
0x1800c55cc  mov     edx, [rsp+1F0h+var_1B8]
0x1800c55d0  mov     eax, [rbx+0FC4h]
0x1800c55d6  add     [rbx+0FC0h], eax
0x1800c55dc  mov     ecx, [rbx+0FC0h]
0x1800c55e2  mov     r8, [rbp+0F0h+var_120]
0x1800c55e6  mov     dword ptr [rbx+0FC4h], 0
0x1800c55f0  mov     dword ptr [rbx+0FC8h], 4
0x1800c55fa  mov     rax, [rbx+10h]
0x1800c55fe  mov     [rax+30h], cx
0x1800c5602  mov     eax, edx
0x1800c5604  mov     byte ptr [r11+120h], 0
0x1800c560c  add     rax, rax
0x1800c560f  cmp     [rsp+1F0h+var_1BC], 3
0x1800c5614  mov     qword ptr [r11+118h], 0
0x1800c561f  mov     ecx, [rdi]
0x1800c5621  mov     dword ptr [r11], 9
0x1800c5628  movups  xmm0, xmmword ptr [r8+rax*8]
0x1800c562d  mov     eax, [rbp+0F0h+var_140]
0x1800c5630  mov     [r11+0CCh], eax
0x1800c5637  mov     eax, dword ptr [rsp+1F0h+var_188]
0x1800c563b  mov     [r11+0D0h], eax
0x1800c5642  movzx   eax, byte ptr [rsp+1F0h+var_1B0]
0x1800c5647  mov     [r11+0D4h], al
0x1800c564e  mov     eax, [rsp+1F0h+var_1B4]
0x1800c5652  mov     [r11+0C0h], eax
0x1800c5659  mov     eax, [rsp+1F0h+var_1C0]
0x1800c565d  mov     [r11+0C4h], eax
0x1800c5664  setz    al
0x1800c5667  mov     [r11+0D5h], al
0x1800c566e  mov     rax, [rsp+1F0h+var_178]
0x1800c5673  mov     dword ptr [r11+0D6h], 100h
0x1800c567e  mov     [r11+0C8h], r12d
  ... truncated ...
```
