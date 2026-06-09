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
  const unsigned __int16 *v9; // rdx
  int *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdx
  float *v13; // rax
  float v14; // xmm3_4
  float v15; // xmm4_4
  float v16; // xmm11_4
  float v17; // xmm13_4
  float v18; // xmm2_4
  float v19; // xmm1_4
  unsigned int v20; // xmm7_4
  float v21; // xmm9_4
  float v22; // xmm10_4
  float v23; // xmm2_4
  float v24; // xmm1_4
  float v25; // xmm5_4
  float v26; // xmm3_4
  float v27; // xmm6_4
  float v28; // xmm14_4
  float v29; // xmm8_4
  float v30; // xmm12_4
  float v31; // xmm14_4
  float v32; // xmm15_4
  float v33; // xmm9_4
  float v34; // xmm7_4
  float v35; // xmm1_4
  float v36; // xmm13_4
  __m128 v37; // xmm8
  float v38; // xmm6_4
  int CurrentInputClampBehavior; // eax
  __m128 v40; // xmm13
  unsigned int v41; // r12d
  D3DVALUE r; // ebx
  unsigned int v43; // ecx
  int *v44; // r8
  __int64 v45; // rdx
  unsigned int v46; // eax
  __m128 v47; // xmm13
  int v48; // eax
  _DWORD *v49; // r15
  __int64 v50; // rbx
  struct CHwShaderState *v51; // r11
  enum DXGI_FORMAT v52; // edx
  int v53; // ecx
  const struct D2D_RECT_F *v54; // r8
  bool v55; // zf
  int v56; // ecx
  struct D2D_RECT_F v57; // xmm0
  __int64 v58; // rax
  __int64 v59; // rcx
  enum DXGI_FORMAT v60; // edx
  __int64 result; // rax
  __int64 v62; // rbx
  int v63; // eax
  float v64; // xmm1_4
  __m128 v65; // xmm0
  __int64 v66; // rax
  int v67; // ebx
  float v68; // xmm0_4
  float v69; // xmm4_4
  float *v70; // rax
  float v71; // xmm9_4
  float v72; // xmm8_4
  float v73; // xmm10_4
  float v74; // xmm1_4
  float v75; // xmm2_4
  float v76; // xmm0_4
  float v77; // xmm3_4
  unsigned int v78; // xmm10_4
  float v79; // xmm2_4
  float v80; // xmm1_4
  float v81; // xmm4_4
  float v82; // xmm5_4
  float v83; // xmm3_4
  float v84; // xmm6_4
  float v85; // xmm14_4
  float v86; // xmm0_4
  float v87; // xmm8_4
  float v88; // xmm11_4
  float v89; // xmm7_4
  float v90; // xmm9_4
  float v91; // xmm15_4
  float v92; // xmm1_4
  float v93; // xmm12_4
  __int64 v94; // rdx
  const struct MILMatrix3x2 *v95; // rdx
  int RealizationInfoAndTextureMapping; // eax
  unsigned int v97; // ebx
  unsigned int v98; // eax
  __int64 v99; // r12
  __int64 i; // rcx
  __int64 v101; // rax
  __int64 v102; // rdx
  __int64 v103; // rbx
  int v104; // eax
  unsigned int v105; // eax
  __m128 v106; // xmm0
  __int64 v107; // rcx
  __int64 v108; // r8
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
  SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(&v153);
  SvgPodInfo<SvgLineElement,SvgLengthAttribute<1>>::AsPodInfo(v155);
  v10 = (int *)*((_QWORD *)a4 + 2);
  *(_QWORD *)&v142.r = 0;
  switch ( *v10 )
  {
    case 7:
      v11 = *((_QWORD *)v10 + 6);
      v12 = *((unsigned int *)this + 35);
      *(float *)&g_low = 0.0;
      *(float *)&v133 = 0.0;
      (*(void (__fastcall **)(__int64, __int64, unsigned int *, int *))(*(_QWORD *)v11 + 288LL))(
        v11,
        v12,
        &g_low,
        &v133);
      v13 = (float *)*((_QWORD *)a4 + 3);
      *(_QWORD *)((char *)&v153 + 4) = 0;
      v154 = 0;
      *(float *)&v153 = 96.0 / *(float *)&g_low;
      *((float *)&v153 + 3) = 96.0 / *(float *)&v133;
      v14 = *((float *)v10 + 6);
      v15 = *((float *)v10 + 7);
      v16 = *((float *)v10 + 2) * 0.0;
      v17 = *((float *)v10 + 3) * 0.0;
      v18 = *((float *)v10 + 4) * 0.0;
      v19 = *((float *)v10 + 5) * 0.0;
      *(float *)&v20 = (float)(*((float *)v10 + 3) * (float)(96.0 / *(float *)&g_low)) + v19;
      v21 = *((float *)v10 + 5) * (float)(96.0 / *(float *)&v133);
      v22 = (float)(*((float *)v10 + 4) * (float)(96.0 / *(float *)&v133)) + v16;
      *(float *)&v153 = (float)(*((float *)v10 + 2) * (float)(96.0 / *(float *)&g_low)) + v18;
      *((float *)&v153 + 2) = v22;
      *((float *)&v153 + 3) = v21 + v17;
      *(float *)&v154 = (float)(v16 + v18) + v14;
      *((float *)&v154 + 1) = (float)(v17 + v19) + v15;
      v23 = *v13;
      v24 = v13[2];
      v25 = v13[1];
      v26 = v13[4];
      v27 = v13[5];
      v28 = v25 * *(float *)&v153;
      v29 = v13[3];
      v30 = (float)(*v13 * *(float *)&v153) + (float)(v24 * *(float *)&v20);
      *(_QWORD *)&v153 = __PAIR64__(v20, LODWORD(v30));
      v31 = v28 + (float)(v29 * *(float *)&v20);
      v32 = (float)(v24 * (float)(v21 + v17)) + (float)(v23 * v22);
      *(_QWORD *)((char *)&v153 + 4) = __PAIR64__(LODWORD(v32), LODWORD(v31));
      v33 = 0.0;
      v34 = (float)((float)(*((float *)&v154 + 1) * v24) + (float)(*(float *)&v154 * v23)) + v26;
      *((float *)&v153 + 3) = (float)(v29 * *((float *)&v153 + 3)) + (float)(v25 * v22);
      v135 = SHIDWORD(v153);
      v35 = (float)(v30 * *((float *)&v153 + 3)) - (float)(v32 * v31);
      v36 = (float)((float)(*((float *)&v154 + 1) * v29) + (float)(*(float *)&v154 * v25)) + v27;
      v154 = __PAIR64__(LODWORD(v36), LODWORD(v34));
      if ( v35 != 0.0 )
      {
        v37 = (__m128)LODWORD(FLOAT_1_0);
        v38 = 1.0 / v35;
        if ( _finite((float)(1.0 / v35)) )
        {
          *(float *)&v153 = *(float *)&v135 * v38;
          *((float *)&v153 + 1) = COERCE_FLOAT(LODWORD(v31) ^ _xmm) * v38;
          *((float *)&v153 + 2) = COERCE_FLOAT(LODWORD(v32) ^ _xmm) * v38;
          *((float *)&v153 + 3) = v30 * v38;
          *((float *)&v154 + 1) = (float)((float)(v34 * v31) - (float)(v30 * v36)) * v38;
          *(float *)&v154 = (float)((float)(v36 * v32) - (float)(v34 * *(float *)&v135)) * v38;
          (*(void (__fastcall **)(_QWORD, _QWORD **))(**((_QWORD **)v10 + 6) + 272LL))(*((_QWORD *)v10 + 6), &v139);
          if ( (_DWORD)v139 )
          {
            if ( HIDWORD(v139) )
            {
              v143 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 232LL))(v11) + 64);
              v138 = *(_DWORD *)(v143 + 164);
              *(_QWORD *)&v142.r = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, struct _D3DCOLORVALUE *))(*(_QWORD *)v11 + 280LL))(
                                                v11,
                                                &v142);
              CurrentInputClampBehavior = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
              v40 = (__m128)(unsigned int)v10[1];
              if ( CurrentInputClampBehavior != 2 )
              {
                if ( CurrentInputClampBehavior )
                {
                  if ( CurrentInputClampBehavior == 1 )
                  {
                    v33 = FLOAT_N65504_0;
                    v37 = (__m128)LODWORD(FLOAT_65504_0);
                  }
                  else
                  {
                    v33 = FLOAT_N3_4028235e38;
                    v37 = (__m128)LODWORD(FLOAT_3_4028235e38);
                  }
                }
                if ( v40.m128_f32[0] > v37.m128_f32[0] )
                  v40 = v37;
                else
                  v40.m128_f32[0] = fmaxf(v40.m128_f32[0], v33);
              }
              v41 = v10[10];
              v136 = v10[8];
              v133 = v10[9];
              goto LABEL_11;
            }
          }
        }
      }
      goto LABEL_44;
    case 3:
      v95 = (const struct MILMatrix3x2 *)*((_QWORD *)a4 + 3);
      *(_QWORD *)&v142.r = &LinearGradientBrushDataWrapper::`vftable';
      *(_QWORD *)&v142.b = v10;
      *(float *)&g_low = 0.0;
      RealizationInfoAndTextureMapping = GradientBrushDataWrapperCommon::GetRealizationInfoAndTextureMapping(
                                           (GradientBrushDataWrapperCommon *)&v142,
                                           v95,
                                           &g_low,
                                           (struct MILMatrix3x2 *)&v153);
      v146 = RealizationInfoAndTextureMapping;
      v97 = RealizationInfoAndTextureMapping;
      if ( RealizationInfoAndTextureMapping < 0 )
      {
        DoStackCapture(RealizationInfoAndTextureMapping);
        return v97;
      }
      v98 = g_low;
      v99 = *((_QWORD *)v10 + 6);
      for ( i = 10; v98 != 1; v98 >>= 1 )
        i = (unsigned int)(i - 1);
      v101 = v99 + 80;
      if ( !v99 )
        v101 = 88;
      v102 = *(_QWORD *)(*(_QWORD *)v101 + 8 * i);
      DWORD1(v153) = 0;
      HIDWORD(v153) = 0;
      *((float *)&v154 + 1) = (float)*(int *)(v102 + 32) + 0.5;
      v104 = *(_DWORD *)(v102 + 28);
      v143 = *(_QWORD *)(v102 + 16);
      v103 = v143;
      v138 = v104;
      v105 = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
      v106 = (__m128)(unsigned int)v10[1];
      v106.m128_f32[0] = ClampInputAlpha(v107, v105, v108);
      r = *(float *)(v103 + 152);
      v40 = v106;
      if ( !v99 )
        v99 = 8;
      v139 = (_QWORD *)v99;
      v109 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 176LL))(v99);
      v110 = 1;
      if ( v109 )
        v110 = 3;
      v41 = 1;
      g_low = v110;
      v136 = (*(__int64 (__fastcall **)(_QWORD *))(*v139 + 128LL))(v139);
      *(float *)&v133 = 0.0;
      goto LABEL_13;
    case 10:
      v111 = (_QWORD *)*((_QWORD *)v10 + 1);
      v40 = (__m128)(unsigned int)v10[4];
      v112 = v10[5];
      v113 = v10[6];
      v114 = v10[7];
      v115 = v10[8];
      v116 = v10[9];
      v117 = v10[10];
      v41 = v10[11];
      v118 = v10[12];
      v135 = *((enum DXGI_FORMAT *)v10 + 13);
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
          if ( v41 > 1 )
            return 0;
          goto LABEL_12;
        }
      }
LABEL_44:
      DoStackCapture(-2003197951);
      return 2291769345LL;
    case 11:
      v62 = *((_QWORD *)v10 + 8);
      v147 = (_DWORD *)*((_QWORD *)v10 + 9);
      *(_QWORD *)&v142.r = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 280LL))(
                                        v62,
                                        &v143);
      v63 = CBaseRenderTarget::GetCurrentInputClampBehavior(this);
      v40 = (__m128)(unsigned int)v10[1];
      if ( v63 != 2 )
      {
        if ( v63 )
        {
          if ( v63 == 1 )
          {
            v64 = FLOAT_N65504_0;
            v65 = (__m128)LODWORD(FLOAT_65504_0);
          }
          else
          {
            v64 = FLOAT_N3_4028235e38;
            v65 = (__m128)LODWORD(FLOAT_3_4028235e38);
          }
        }
        else
        {
          v64 = 0.0;
          v65 = (__m128)LODWORD(FLOAT_1_0);
        }
        if ( v40.m128_f32[0] > v65.m128_f32[0] )
          v40 = v65;
        else
          v40.m128_f32[0] = fmaxf(v40.m128_f32[0], v64);
      }
      v41 = v10[14];
      v136 = v10[12];
      v133 = v10[13];
      v143 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 232LL))(v62) + 64);
      v138 = *(_DWORD *)(v143 + 164);
      v66 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v147 + 232LL))(v147);
      v55 = *((_DWORD *)this + 35) == 1;
      v147 = *(_DWORD **)(v66 + 64);
      v67 = v147[41];
      if ( v55 )
      {
        v68 = FLOAT_96_0;
        v69 = FLOAT_1_0;
      }
      else
      {
        v68 = *((float *)this + 46);
        v69 = 96.0 / *((float *)this + 47);
      }
      v70 = (float *)*((_QWORD *)a4 + 3);
      *(_QWORD *)((char *)&v153 + 4) = 0;
      v154 = 0;
      *(float *)&v153 = 96.0 / v68;
      v71 = *((float *)v10 + 5);
      v72 = *((float *)v10 + 2);
      v73 = *((float *)v10 + 4);
      v74 = *((float *)v10 + 6);
      v75 = *((float *)v10 + 7);
      v76 = v73 * 0.0;
      v77 = *((float *)v10 + 3) * 0.0;
      *((float *)&v153 + 1) = (float)(*((float *)v10 + 3) * *(float *)&v153) + (float)(v71 * 0.0);
      *(float *)&v78 = (float)(v73 * v69) + (float)(v72 * 0.0);
      *(float *)&v153 = (float)(v72 * *(float *)&v153) + v76;
      *((_QWORD *)&v153 + 1) = __PAIR64__(LODWORD(v69), v78);
      *((float *)&v154 + 1) = (float)((float)(v71 * 0.0) + v77) + v75;
      *((float *)&v153 + 3) = (float)(v71 * v69) + v77;
      *(float *)&v154 = (float)((float)(v72 * 0.0) + v76) + v74;
      v79 = *v70;
      v80 = v70[2];
      v81 = v70[3];
      v82 = v70[1];
      v83 = v70[4];
      v84 = v70[5];
      v85 = (float)(v80 * *((float *)&v153 + 1)) + (float)(*v70 * *(float *)&v153);
      v86 = v82 * *(float *)&v153;
      *(float *)&v153 = v85;
      v87 = (float)(v81 * *((float *)&v153 + 1)) + v86;
      *((float *)&v153 + 1) = v87;
      *(float *)&g_low = (float)(v80 * *((float *)&v153 + 3)) + (float)(v79 * *(float *)&v78);
      *((float *)&v153 + 2) = *(float *)&g_low;
      v88 = *(float *)&v154 * v82;
      *((float *)&v153 + 3) = (float)(v81 * *((float *)&v153 + 3)) + (float)(v82 * *(float *)&v78);
      v135 = SHIDWORD(v153);
      v89 = (float)((float)(*((float *)&v154 + 1) * v80) + (float)(*(float *)&v154 * v79)) + v83;
      *(float *)&v154 = v89;
      v90 = *((float *)&v153 + 3);
      v91 = (float)((float)(*((float *)&v154 + 1) * v81) + v88) + v84;
      *((float *)&v154 + 1) = v91;
      v92 = (float)(v85 * *((float *)&v153 + 3)) - (float)(*(float *)&g_low * v87);
      if ( v92 != 0.0 )
      {
        v93 = 1.0 / v92;
        if ( _finite((float)(1.0 / v92)) )
        {
          LODWORD(v139) = v67;
          *(float *)&v153 = v93 * v90;
          *((float *)&v153 + 1) = COERCE_FLOAT(LODWORD(v87) ^ _xmm) * v93;
          *((float *)&v153 + 2) = COERCE_FLOAT(g_low ^ _xmm) * v93;
          *((float *)&v153 + 3) = v93 * v85;
          *((float *)&v154 + 1) = (float)((float)(v89 * v87) - (float)(v85 * v91)) * v93;
          *(float *)&v154 = (float)((float)(v91 * *(float *)&g_low) - (float)(v89 * v90)) * v93;
          goto LABEL_11;
        }
      }
      goto LABEL_44;
  }
  v143 = 0;
  v136 = 0;
  *(float *)&v133 = 0.0;
  v41 = 0;
  v40 = 0;
  PrintAssertionMessageW(
    L"Unexpected brush type",
    v9,
    L"WarpRenderTarget::FillNonOverlappingRectangles_FastPath_Warp_BitmapBrushes",
    L"onecoreuap\\windows\\direct2d\\core\\hw\\warprt.cpp",
    0x1E2u);
  __int2c();
LABEL_12:
  r = v142.r;
  g_low = LODWORD(v142.g);
LABEL_13:
  v43 = 0;
  v44 = dword_18030EAE0;
  while ( 1 )
  {
    if ( v43 >= 0x1C )
      return 0;
    v45 = 5LL * (int)v43;
    if ( LODWORD(r) == dword_18030EAE0[10 * v43] )
      break;
    ++v43;
  }
  if ( (dword_18030EAE0[10 * v43 + 8] & 0x200) == 0 )
    return 0;
  v46 = *((_DWORD *)a4 + 10);
  if ( v46 )
  {
    if ( v46 <= 1 )
    {
      v130 = **((_QWORD **)a4 + 4);
      if ( (unsigned int)(**(_DWORD **)(v130 + 8) - 1) <= 1 )
      {
        *(float *)&v131 = COERCE_FLOAT(CBaseRenderTarget::GetDxgiFormatRoundTrip(this));
        v132 = *(const struct BatchedBrush **)(v130 + 8);
        v135 = v131;
        v40.m128_f32[0] = v40.m128_f32[0] * D2DSolidColorBrush::GetColor(&v142, v132, &v135)->a;
        goto LABEL_19;
      }
    }
    return 0;
  }
LABEL_19:
  v148 = *((_DWORD *)this + 32);
  v47 = _mm_shuffle_ps(v40, v40, 0);
  v142.r = *(D3DVALUE *)(*(_QWORD *)a4 + 8LL);
  v48 = (*(__int64 (__fastcall **)(WarpRenderTarget *, __int64, int *))(*(_QWORD *)this + 600LL))(this, v45, v44);
  *(float *)&v135 = 0.0;
  if ( !a3 )
    goto LABEL_28;
  v49 = v147;
  v137 = v48 == 3;
  do
  {
    v50 = *((_QWORD *)this + 106);
    if ( *(_DWORD *)(v50 + 4088) >= 0xC8u )
    {
      v94 = 10;
    }
    else
    {
      if ( (unsigned int)(*(_DWORD *)(v50 + 4032) + *(_DWORD *)(v50 + 4036)) <= 0xEB && *(_DWORD *)(v50 + 75600) != 128 )
        goto LABEL_24;
      if ( (unsigned int)(*(_DWORD *)(v50 + 4032) + *(_DWORD *)(v50 + 4036)) > 0xEB )
        v94 = 11;
      else
        v94 = (unsigned int)(*(_DWORD *)(v50 + 75600) != 128) + 12;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v50 + 24) + 560LL))(*(_QWORD *)(v50 + 24), v94);
LABEL_24:
    v51 = CHwDeferredRenderingCallBuffer::LockForNewCall((CHwDeferredRenderingCallBuffer *)(v50 + 4088));
    v52 = v135;
    *(_DWORD *)(v50 + 4032) += *(_DWORD *)(v50 + 4036);
    v53 = *(_DWORD *)(v50 + 4032);
    v54 = v151;
    *(_DWORD *)(v50 + 4036) = 0;
    *(_DWORD *)(v50 + 4040) = 4;
    *(_WORD *)(*(_QWORD *)(v50 + 16) + 48LL) = v53;
    *((_BYTE *)v51 + 288) = 0;
    v55 = g_low == 3;
    *((_QWORD *)v51 + 35) = 0;
    v56 = *v10;
    *(_DWORD *)v51 = 9;
    v57 = v54[v52];
    *((_DWORD *)v51 + 51) = v148;
    *((_DWORD *)v51 + 52) = LODWORD(v142.r);
    *((_BYTE *)v51 + 212) = v137;
    *((_DWORD *)v51 + 48) = v136;
    *((float *)v51 + 49) = *(float *)&v133;
    *((_BYTE *)v51 + 213) = v55;
    v58 = v143;
    *(_DWORD *)((char *)v51 + 214) = 256;
    *((_DWORD *)v51 + 50) = v41;
    *(struct D2D_RECT_F *)((char *)v51 + 8) = v57;
    *(__m128 *)((char *)v51 + 24) = v47;
    *((_QWORD *)v51 + 21) = v58;
    *((_DWORD *)v51 + 46) = v138;
    *(_OWORD *)((char *)v51 + 104) = v153;
    *((_QWORD *)v51 + 15) = v154;
    if ( v56 == 11 )
    {
      *((_DWORD *)v51 + 47) = (_DWORD)v139;
      *((_BYTE *)v51 + 217) = 1;
      *((_QWORD *)v51 + 22) = v49;
    }
    v59 = *((_QWORD *)this + 106);
    v60 = v52 + 1;
    v135 = v60;
    *(_BYTE *)(v59 + 74544) = 0;
  }
  while ( v60 < a3 );
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
