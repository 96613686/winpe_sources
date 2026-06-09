# CDrawingContext::PushLocalSpaceClipAndAlphaInternal(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,CDrawingContext::NodeEffects *,bool *)

- ea: `0x180022f20`
- end: `0x18002468f`
- name: `?PushLocalSpaceClipAndAlphaInternal@CDrawingContext@@AEAAJPEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@PEAUNodeEffects@1@PEA_N@Z`
- size: `5999`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800bf5d8`
- `0x18012b980`
- `0x180238150`

## callees

- `0x180022580`
- `0x180022e40`
- `0x180022f20`
- `0x180024dd0`
- `0x180025388`
- `0x18002de54`
- `0x180042854`
- `0x180042de0`
- `0x1800441f0`
- `0x180044220`
- `0x180060100`
- `0x180060b80`
- `0x1800629b0`
- `0x180063e10`
- `0x180065370`
- `0x18006dad0`
- `0x18008f620`
- `0x180092080`
- `0x1801223ac`
- `0x1801225c0`
- `0x1801d7644`
- `0x180228490`
- `0x180229424`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180022fe3`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180022fe3`

## string_xrefs

- `0x180023121`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18002313b`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180023400`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18002341a`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180023ce2`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180023cf8`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180023dab`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180023dc1`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18002453b`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180024592`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18002460f`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180024634`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`

## pseudocode

```c
__int64 __fastcall CDrawingContext::PushLocalSpaceClipAndAlphaInternal(
        CDrawingContext *this,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  unsigned __int32 v4; // xmm12_4
  const struct CShape *v5; // r13
  float v6; // xmm13_4
  unsigned int v7; // esi
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  char v15; // dl
  __int64 v16; // rax
  __int64 v17; // rcx
  const struct CShape *v18; // rdi
  const struct CMILMatrix *v19; // r9
  enum D2D1_ANTIALIAS_MODE v20; // r12d
  char v21; // dl
  void *v22; // rcx
  int v23; // eax
  int v24; // edi
  __int64 v25; // rax
  __int64 v26; // rsi
  unsigned __int64 v27; // rax
  int v28; // r9d
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  float v32; // xmm7_4
  float v33; // xmm2_4
  float v34; // xmm1_4
  float v35; // xmm3_4
  float v36; // xmm0_4
  float v37; // xmm4_4
  float v38; // xmm5_4
  float v39; // xmm6_4
  float v40; // xmm6_4
  int v41; // eax
  int v42; // eax
  __int64 v43; // r9
  int v44; // eax
  bool v46; // zf
  void **v47; // rbx
  __int64 v48; // rax
  unsigned int v49; // edi
  unsigned __int64 v50; // rsi
  void *v51; // rax
  void *v52; // r12
  unsigned int v53; // eax
  __int64 v54; // rcx
  CShape *v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rcx
  int v58; // eax
  struct D2D_RECT_F v59; // xmm1
  __int64 v60; // rcx
  char v61; // r8
  __int64 *v62; // rcx
  __int64 v63; // rax
  struct _LIST_ENTRY *v64; // rsi
  CVisual *v65; // r12
  struct _LIST_ENTRY **p_Blink; // r9
  unsigned int v67; // esi
  unsigned __int64 v68; // rdi
  void *v69; // r13
  void *v70; // rax
  void *v71; // r12
  unsigned int v72; // eax
  unsigned int v73; // ecx
  unsigned int v74; // r9d
  unsigned int v75; // eax
  int v76; // xmm6_4
  char v77; // bl
  void *v78; // rcx
  __int64 v79; // rdx
  char v80; // cl
  __int64 (__fastcall *v81)(__int64, __int64, void **); // rax
  int v82; // eax
  unsigned int v83; // xmm1_4
  unsigned int v84; // xmm0_4
  struct D2D_RECT_F *v85; // rcx
  int v86; // eax
  void *v87; // rcx
  int v88; // eax
  unsigned int v89; // r8d
  unsigned int v90; // r9d
  unsigned int v91; // eax
  char v92; // r8
  struct D2D_RECT_F si128; // xmm5
  __int64 v94; // rcx
  __int64 v95; // rdx
  struct CCpuClipAntialiasSink *v96; // rdx
  struct _LIST_ENTRY *TreeDataListHead; // rax
  struct _LIST_ENTRY *i; // rcx
  int v99; // eax
  void *v100; // rdi
  __int64 v101; // rbx
  enum D2D1_ANTIALIAS_MODE v102; // edi
  void **v103; // rbx
  __int64 v104; // rax
  __int64 v105; // r13
  unsigned __int64 v106; // rax
  __int64 v107; // rdx
  int v108; // edi
  float v109; // xmm11_4
  enum D2D1_ANTIALIAS_MODE v110; // edi
  CVisual *v111; // rsi
  char v112; // r13
  __int64 v113; // rax
  __int64 v114; // r13
  unsigned __int64 v115; // rax
  __int64 v116; // rdx
  unsigned int v117; // esi
  unsigned __int64 v118; // r13
  void *v119; // rax
  unsigned int v120; // eax
  __int64 v121; // rcx
  float left; // xmm6_4
  float top; // xmm8_4
  float right; // xmm9_4
  float bottom; // xmm10_4
  unsigned int v126; // r9d
  __int64 v127; // rax
  __int64 v128; // rcx
  unsigned int v129; // eax
  float v130; // xmm6_4
  float v131; // xmm8_4
  float v132; // xmm9_4
  float v133; // xmm10_4
  unsigned int v134; // r9d
  __int64 v135; // rax
  __int64 v136; // rcx
  unsigned int v137; // eax
  int v138; // r12d
  unsigned __int64 v139; // rcx
  unsigned __int64 v140; // r13
  void *v141; // rax
  _DWORD *v142; // rax
  __int64 v143; // rcx
  int v144; // edx
  unsigned int v145; // eax
  __int64 v146; // rcx
  int v147; // eax
  int v148; // r9d
  unsigned int v149; // eax
  unsigned int v150; // eax
  int v151; // eax
  int v152; // eax
  int v153; // eax
  char v154; // r8
  char v155; // al
  int v156; // eax
  int v157; // eax
  int v158; // eax
  int v159; // eax
  int v160; // [rsp+20h] [rbp-E0h]
  int v161; // [rsp+20h] [rbp-E0h]
  unsigned int v162; // [rsp+20h] [rbp-E0h]
  int v163; // [rsp+20h] [rbp-E0h]
  int v164; // [rsp+20h] [rbp-E0h]
  int v165; // [rsp+20h] [rbp-E0h]
  int v166; // [rsp+20h] [rbp-E0h]
  int v167; // [rsp+20h] [rbp-E0h]
  unsigned int v168; // [rsp+40h] [rbp-C0h] BYREF
  bool v169; // [rsp+44h] [rbp-BCh] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  bool v171; // [rsp+50h] [rbp-B0h] BYREF
  void *v172; // [rsp+58h] [rbp-A8h] BYREF
  void *v173; // [rsp+60h] [rbp-A0h]
  __int64 v174; // [rsp+68h] [rbp-98h]
  _BYTE *v175; // [rsp+70h] [rbp-90h]
  __int128 v176; // [rsp+78h] [rbp-88h]
  __int64 v177; // [rsp+88h] [rbp-78h]
  struct D2D_RECT_F v178; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v179; // [rsp+A0h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v4 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  v5 = 0;
  v6 = FLOAT_1_0;
  v7 = 0;
  v177 = a2;
  v10 = 0;
  v175 = a4;
  v11 = 0xFFFFFFFFLL;
  v174 = 0;
  LODWORD(v173) = 101;
  if ( !*(_QWORD *)(a3 + 8) )
    goto LABEL_38;
  if ( EventEnabled(Microsoft_Windows_Dwm_Core_Provider_Context, &EVTDESC_ETWGUID_LAYEREVENT_BeginLayer_Start) )
  {
    v62 = *(__int64 **)(a3 + 8);
    if ( v62 )
    {
      v63 = *v62;
      v168 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(__int64 *, unsigned int *))(v63 + 64))(v62, &v168) )
      {
        if ( v168 == 1 )
          *(_DWORD *)(a3 + 180) |= 1u;
      }
    }
    if ( CMILMatrix::Is2DAxisAlignedPreserving((CMILMatrix *)(a3 + 108)) )
      *(_DWORD *)(a3 + 180) |= 4u;
  }
  v12 = *(__int64 **)(a3 + 8);
  if ( !v12
    || (v13 = *v12, v168 = 0, !(*(unsigned __int8 (__fastcall **)(__int64 *, unsigned int *))(v13 + 64))(v12, &v168))
    || v168 != 1 )
  {
    v14 = a3 + 108;
    v174 = *(_QWORD *)(a3 + 8);
    goto LABEL_8;
  }
  v14 = a3 + 108;
  v15 = *(_BYTE *)(a3 + 172);
  if ( v15 >> 6 == 1 )
    goto LABEL_90;
  if ( v15 >> 6 < 0 )
    goto LABEL_8;
  v61 = *(_BYTE *)(a3 + 173);
  if ( (char)(4 * v61) >> 6 != 1 )
  {
    if ( (char)(4 * v61) >> 6 < 0 )
    {
LABEL_88:
      if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)(a3 + 112) - 0.0) & v4) < 0.000081380211
        && COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)(a3 + 124) - 0.0) & v4) < 0.000081380211 )
      {
        *(_BYTE *)(a3 + 172) = v15 | 0xC0;
        goto LABEL_8;
      }
      goto LABEL_89;
    }
    v92 = v61 & 0xCF;
    if ( COERCE_FLOAT(
           COERCE_UNSIGNED_INT(
             (float)((float)((float)(COERCE_FLOAT(*(_DWORD *)(a3 + 136) & v4) * 61440.0)
                           + (float)(COERCE_FLOAT(*(_DWORD *)(a3 + 120) & v4) * 61440.0))
                   + COERCE_FLOAT(*(_DWORD *)(a3 + 168) & v4))
           - 1.0)
         & v4) < 0.000081380211 )
    {
      *(_BYTE *)(a3 + 173) = v92 ^ 0x30;
      goto LABEL_88;
    }
    *(_BYTE *)(a3 + 173) = v92 ^ 0x10;
  }
LABEL_89:
  *(_BYTE *)(a3 + 172) = v15 & 0x3F | 0x40;
LABEL_90:
  if ( !(unsigned __int8)CMILMatrix::Is90Or270RotationWithTranslateAndScaleIgnoreZ<1>(v14) )
    v174 = *(_QWORD *)(a3 + 8);
LABEL_8:
  if ( *(_BYTE *)(a3 + 184) && *(_BYTE *)(*((_QWORD *)this + 93) - 8LL) )
  {
    v16 = *(_QWORD *)(a3 + 24);
    if ( v16 )
    {
      v17 = *(_QWORD *)(v16 + 56);
      v18 = *(const struct CShape **)(v17 + 8);
      if ( !v18 )
        v18 = *(const struct CShape **)(a3 + 8);
      v5 = *(const struct CShape **)(v17 + 24);
      v19 = (const struct CMILMatrix *)(v17 + 40);
      v20 = *(_DWORD *)(v17 + 108);
      v21 = *(_BYTE *)(v17 + 116);
      v22 = *(void **)v17;
    }
    else
    {
      v64 = (struct _LIST_ENTRY *)*((_QWORD *)this + 993);
      v18 = *(const struct CShape **)(a3 + 8);
      v65 = *(CVisual **)a3;
      if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *))v64->Flink[12].Flink)(v64) )
      {
        p_Blink = (struct _LIST_ENTRY **)((char *)v65 + 320);
      }
      else
      {
        TreeDataListHead = CVisual::GetTreeDataListHead(v65);
        if ( TreeDataListHead )
        {
          for ( i = TreeDataListHead->Flink; i != TreeDataListHead; i = i->Flink )
          {
            if ( i[2].Flink == v64 )
            {
              p_Blink = &i[-22].Blink;
              break;
            }
          }
        }
      }
      v19 = (const struct CMILMatrix *)p_Blink[14];
      v20 = *((_DWORD *)this + 59) != 0;
      v21 = 0;
      v22 = 0;
    }
    *(_QWORD *)&v178.right = *(_QWORD *)a3;
    v172 = v22;
    v169 = v21;
    *(_QWORD *)&v178.left = 2;
    v171 = 0;
    v23 = CScopedClipStack::PushCpuClipToScope(
            (CDrawingContext *)((char *)this + 736),
            v18,
            v5,
            v19,
            v20,
            v21,
            (struct CCpuClipAntialiasSink *)v22,
            &v171);
    v24 = v23;
    if ( v23 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, 0xC41u, 0);
      v7 = v24;
      goto LABEL_20;
    }
    v25 = *((unsigned int *)this + 67);
    if ( *((_DWORD *)this + 66) == (_DWORD)v25 )
    {
      v26 = (unsigned int)v25;
      v27 = 2 * v25;
      if ( v27 > 0xFFFFFFFF )
      {
        LODWORD(v173) = 95;
LABEL_18:
        v7 = -2147024362;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)(unsigned int)v173,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v7,
          v160);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v7,
          v161);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0xC44u, 0);
        v169 = 0;
        CScopedClipStack::PopCpuClipFromScope((CDrawingContext *)((char *)this + 736), this, &v169);
        v24 = v7;
LABEL_20:
        v162 = 4359;
LABEL_21:
        v28 = v24;
LABEL_50:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v28, v162, 0);
        return v7;
      }
      v49 = 64;
      if ( (unsigned int)v27 > 0x40 )
        v49 = v27;
      v50 = 16 * v26;
      if ( v50 > 0xFFFFFFFF )
      {
        LODWORD(v173) = 98;
        goto LABEL_18;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / v49 <= 0x10 )
      {
        v7 = -2147024809;
        goto LABEL_19;
      }
      Src = (void *)*((_QWORD *)this + 32);
      v51 = MIDL_user_allocate(16LL * v49);
      v52 = v51;
      if ( !v51 )
      {
        v7 = -2147024882;
        goto LABEL_19;
      }
      if ( Src && (_DWORD)v50 )
        memcpy_0(v51, Src, (unsigned int)v50);
      operator delete(*((void **)this + 32));
      *((_QWORD *)this + 32) = v52;
      *((_DWORD *)this + 67) = v49;
    }
    *(struct D2D_RECT_F *)(*((_QWORD *)this + 32) + 16LL * (unsigned int)(*((_DWORD *)this + 66))++) = v178;
    v53 = *((_DWORD *)this + 69);
    if ( v53 <= *((_DWORD *)this + 66) )
      v53 = *((_DWORD *)this + 66);
    v46 = !v171;
    *((_DWORD *)this + 69) = v53;
    if ( !v46 )
      *((_BYTE *)this + 8066) = 1;
    v7 = 0;
    if ( *(_QWORD *)(a3 + 24) )
    {
      if ( !v5 )
      {
        v54 = *((_QWORD *)this + 93);
        if ( v54 != *((_QWORD *)this + 92) )
        {
          if ( *(_QWORD *)(v54 - 176) )
          {
            v55 = *(CShape **)(*((_QWORD *)this + 336) - 40LL);
            if ( v55 )
            {
              v56 = *(_QWORD *)v55;
              v168 = 0;
              if ( !(*(unsigned __int8 (__fastcall **)(CShape *, unsigned int *))(v56 + 64))(v55, &v168) || v168 != 1 )
              {
                Src = 0;
                v99 = CShape::CopyShape(v55, 0, (struct CShape **)&Src);
                v7 = v99;
                if ( v99 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v99, 0x1115u, 0);
                  return v7;
                }
                v100 = Src;
                v101 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 56LL);
                CShapePtr::~CShapePtr((CShapePtr *)(v101 + 24));
                *(_QWORD *)(v101 + 24) = v100;
                *(_BYTE *)(v101 + 32) = 1;
              }
            }
          }
        }
      }
      if ( v169 && !v172 )
      {
        v94 = *(_QWORD *)(*((_QWORD *)this + 93) - 16LL);
        v95 = *(_QWORD *)(v94 + 24);
        if ( v95 == *(_QWORD *)(v94 + 16) )
          v96 = 0;
        else
          v96 = *(struct CCpuClipAntialiasSink **)(v95 - 432);
        CCpuClippingData::SetCachedCpuClipAntialiasSink(*(CCpuClippingData **)(a3 + 24), v96);
      }
    }
    goto LABEL_79;
  }
  v43 = *(_QWORD *)(a3 + 8);
  v7 = -2003304309;
  v178 = 0;
  if ( !v43 )
  {
LABEL_49:
    v28 = v7;
    v162 = 4399;
    goto LABEL_50;
  }
  v44 = (*(__int64 (__fastcall **)(__int64, struct D2D_RECT_F *, __int64))(*(_QWORD *)v43 + 48LL))(v43, &v178, v14);
  v7 = v44;
  if ( v44 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v44, 0x137u, 0);
    goto LABEL_49;
  }
  v102 = *((_DWORD *)this + 59) != 0;
  v103 = (void **)((char *)this + 256);
  *((_QWORD *)&v176 + 1) = *(_QWORD *)a3;
  v104 = *((unsigned int *)this + 67);
  *(_QWORD *)&v176 = 3;
  if ( *((_DWORD *)this + 66) == (_DWORD)v104 )
  {
    v105 = (unsigned int)v104;
    v106 = 2 * v104;
    if ( v106 > 0xFFFFFFFF )
    {
      v107 = 95;
LABEL_174:
      v108 = -2147024362;
LABEL_175:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v107,
        (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
        (const char *)(unsigned int)v108,
        v160);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
        (const char *)(unsigned int)v108,
        v164);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v108, 0xC86u, 0);
      v109 = FLOAT_0_5;
      goto LABEL_176;
    }
    v117 = 64;
    if ( (unsigned int)v106 > 0x40 )
      v117 = v106;
    v118 = 16 * v105;
    if ( v118 > 0xFFFFFFFF )
    {
      v107 = 98;
      goto LABEL_174;
    }
    if ( 0xFFFFFFFFFFFFFFFFuLL / v117 <= 0x10 )
    {
      v108 = -2147024809;
    }
    else
    {
      v172 = *v103;
      v119 = MIDL_user_allocate(16LL * v117);
      Src = v119;
      if ( v119 )
      {
        if ( v172 && (_DWORD)v118 )
          memcpy_0(v119, v172, (unsigned int)v118);
        operator delete(*v103);
        *v103 = Src;
        *((_DWORD *)this + 67) = v117;
        goto LABEL_191;
      }
      v108 = -2147024882;
    }
    v107 = 101;
    goto LABEL_175;
  }
LABEL_191:
  v109 = FLOAT_0_5;
  *(_OWORD *)(*((_QWORD *)this + 32) + 16LL * (unsigned int)(*((_DWORD *)this + 66))++) = v176;
  v120 = *((_DWORD *)this + 69);
  if ( v120 <= *((_DWORD *)this + 66) )
    v120 = *((_DWORD *)this + 66);
  *((_DWORD *)this + 69) = v120;
  v121 = *((_QWORD *)this + 93);
  if ( v121 == *((_QWORD *)this + 92) || !*(_QWORD *)(v121 - 168) )
  {
    if ( v102 == D2D1_ANTIALIAS_MODE_ALIASED )
    {
      left = (float)(int)CFloatFPU::CeilingSat(v178.left - 0.5);
      top = (float)(int)CFloatFPU::CeilingSat(v178.top - 0.5);
      right = (float)(int)CFloatFPU::CeilingSat(v178.right - 0.5);
      bottom = (float)(int)CFloatFPU::CeilingSat(v178.bottom - 0.5);
    }
    else
    {
      left = v178.left;
      top = v178.top;
      right = v178.right;
      bottom = v178.bottom;
    }
    v126 = *((_DWORD *)this + 785);
    if ( *((_DWORD *)this + 784) != v126 )
      goto LABEL_198;
    v168 = 0;
    v172 = 0;
    v152 = Grow(0x10u, 8u, a3, v126, *((void **)this + 391), &v168, &v172);
    v7 = v152;
    if ( v152 >= 0 )
    {
      operator delete(*((void **)this + 391));
      *((_QWORD *)this + 391) = v172;
      *((_DWORD *)this + 785) = v168;
LABEL_198:
      v7 = 0;
      v127 = *((_QWORD *)this + 391);
      v128 = 2LL * *((unsigned int *)this + 784);
      *(float *)(v127 + 8 * v128) = left;
      *(float *)(v127 + 8 * v128 + 4) = top;
      *(float *)(v127 + 8 * v128 + 8) = right;
      *(float *)(v127 + 8 * v128 + 12) = bottom;
      v129 = *((_DWORD *)this + 787);
      if ( v129 <= ++*((_DWORD *)this + 784) )
        v129 = *((_DWORD *)this + 784);
      *((_DWORD *)this + 787) = v129;
      goto LABEL_201;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)(unsigned int)v152,
      v160);
    v150 = 513;
LABEL_233:
    v108 = v7;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, v150, 0);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0xC8Bu, 0);
    v151 = *((_DWORD *)this + 66);
    if ( v151 )
    {
      *((_DWORD *)this + 66) = v151 - 1;
      goto LABEL_235;
    }
LABEL_176:
    v7 = v108;
    if ( v108 >= 0 )
      goto LABEL_177;
LABEL_235:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v108, 0x1133u, 0);
    return v7;
  }
  v7 = CD2DClipStack::Push((CDrawingContext *)((char *)this + 3128), &v178, v102);
  if ( (v7 & 0x80000000) != 0 )
  {
    v150 = 517;
    goto LABEL_233;
  }
LABEL_201:
  ++*(_QWORD *)(*((_QWORD *)this + 93) - 168LL);
LABEL_177:
  v10 = v174;
  if ( !v174 )
  {
    v110 = *((_DWORD *)this + 59) != 0;
    v111 = *(CVisual **)a3;
    v112 = 0;
    if ( !*(_QWORD *)a3 )
      goto LABEL_222;
    *(_QWORD *)&v176 = 0;
    v113 = *((unsigned int *)this + 67);
    if ( *((_DWORD *)this + 66) == (_DWORD)v113 )
    {
      v114 = (unsigned int)v113;
      v115 = 2 * v113;
      if ( v115 > 0xFFFFFFFF )
      {
        v116 = 95;
LABEL_182:
        v24 = -2147024362;
LABEL_183:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v116,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)(unsigned int)v24,
          v160);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)(unsigned int)v24,
          v165);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v24, 0xBB3u, 0);
        goto LABEL_210;
      }
      v139 = 64;
      if ( (unsigned int)v115 > 0x40 )
        v139 = (unsigned int)v115;
      v140 = 16 * v114;
      v168 = v139;
      if ( v140 > 0xFFFFFFFF )
      {
        v116 = 98;
        goto LABEL_182;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / v139 <= 0x10 )
      {
        v24 = -2147024809;
      }
      else
      {
        v172 = *v103;
        v141 = MIDL_user_allocate(16 * v139);
        Src = v141;
        if ( v141 )
        {
          if ( v172 && (_DWORD)v140 )
            memcpy_0(v141, v172, (unsigned int)v140);
          operator delete(*v103);
          *v103 = Src;
          *((_DWORD *)this + 67) = v168;
          goto LABEL_219;
        }
        v24 = -2147024882;
      }
      v116 = 101;
      goto LABEL_183;
    }
LABEL_219:
    v112 = 1;
    v142 = *v103;
    v143 = 2LL * *((unsigned int *)this + 66);
    v144 = v176;
    v142[2 * v143] = 1;
    v142[2 * v143 + 1] = v144;
    *(_QWORD *)&v142[2 * v143 + 2] = v111;
    v145 = *((_DWORD *)this + 69);
    if ( v145 <= ++*((_DWORD *)this + 66) )
      v145 = *((_DWORD *)this + 66);
    *((_DWORD *)this + 69) = v145;
LABEL_222:
    v146 = *((_QWORD *)this + 93);
    if ( v146 == *((_QWORD *)this + 92) || !*(_QWORD *)(v146 - 184) )
    {
      if ( v110 == D2D1_ANTIALIAS_MODE_ALIASED )
      {
        v130 = (float)(int)CFloatFPU::CeilingSat(v178.left - v109);
        v131 = (float)(int)CFloatFPU::CeilingSat(v178.top - v109);
        v132 = (float)(int)CFloatFPU::CeilingSat(v178.right - v109);
        v133 = (float)(int)CFloatFPU::CeilingSat(v178.bottom - v109);
      }
      else
      {
        v130 = v178.left;
        v131 = v178.top;
        v132 = v178.right;
        v133 = v178.bottom;
      }
      v134 = *((_DWORD *)this + 779);
      if ( *((_DWORD *)this + 778) == v134 )
      {
        v168 = 0;
        v172 = 0;
        v153 = Grow(0x10u, 8u, a3, v134, *((void **)this + 388), &v168, &v172);
        v7 = v153;
        if ( v153 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8B,
            (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
            (const char *)(unsigned int)v153,
            v160);
          v148 = v7;
          v149 = 252;
          v24 = v7;
          v138 = v7;
LABEL_271:
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v148, v149, 0);
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v138, 0xBB8u, 0);
          if ( v112 )
          {
            CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Pop(
              (char *)this + 256,
              0);
            goto LABEL_211;
          }
LABEL_210:
          v7 = v24;
          if ( v24 >= 0 )
          {
LABEL_79:
            v10 = v174;
            goto LABEL_80;
          }
LABEL_211:
          v162 = 4412;
          goto LABEL_21;
        }
        operator delete(*((void **)this + 388));
        *((_QWORD *)this + 388) = v172;
        *((_DWORD *)this + 779) = v168;
      }
      v135 = *((_QWORD *)this + 388);
      v136 = 2LL * *((unsigned int *)this + 778);
      *(float *)(v135 + 8 * v136) = v130;
      *(float *)(v135 + 8 * v136 + 4) = v131;
      *(float *)(v135 + 8 * v136 + 8) = v132;
      *(float *)(v135 + 8 * v136 + 12) = v133;
      ++*((_DWORD *)this + 778);
      v137 = *((_DWORD *)this + 781);
      if ( v137 <= *((_DWORD *)this + 778) )
        v137 = *((_DWORD *)this + 778);
      v138 = 0;
      *((_DWORD *)this + 781) = v137;
    }
    else
    {
      v147 = CD2DClipStack::Push((CDrawingContext *)((char *)this + 3104), &v178, v110);
      v138 = v147;
      if ( v147 < 0 )
      {
        v24 = v147;
        v7 = v147;
        v148 = v147;
        v149 = 256;
        goto LABEL_271;
      }
    }
    v24 = v138;
    ++*(_QWORD *)(*((_QWORD *)this + 93) - 184LL);
    *((_BYTE *)this + 8065) = 1;
    goto LABEL_210;
  }
LABEL_80:
  v57 = *((_QWORD *)this + 93);
  v178 = 0;
  if ( v57 != *((_QWORD *)this + 92) )
  {
    if ( *(_QWORD *)(v57 - 184) )
    {
      v58 = *((_DWORD *)this + 778);
      if ( v58 )
      {
        v59 = *(struct D2D_RECT_F *)(*((_QWORD *)this + 388) + 16LL * (unsigned int)(v58 - 1));
        LODWORD(v39) = _mm_shuffle_ps((__m128)v59, (__m128)v59, 255).m128_u32[0];
        v178 = v59;
        LODWORD(v38) = _mm_shuffle_ps((__m128)v59, (__m128)v59, 170).m128_u32[0];
      }
      else
      {
        si128 = (struct D2D_RECT_F)_mm_load_si128((const __m128i *)&_xmm);
        LODWORD(v39) = _mm_shuffle_ps((__m128)si128, (__m128)si128, 255).m128_u32[0];
        v178 = si128;
        LODWORD(v38) = _mm_shuffle_ps((__m128)si128, (__m128)si128, 170).m128_u32[0];
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, void **))(**(_QWORD **)(v57 - 192) + 88LL))(*(_QWORD *)(v57 - 192), &v172);
      v38 = (float)(int)v172;
      v39 = (float)SHIDWORD(v172);
    }
    v60 = *((_QWORD *)this + 93);
    if ( v60 == *((_QWORD *)this + 92) || !*(_QWORD *)(v60 - 168) )
    {
      v37 = v178.top;
      v36 = v178.left;
    }
    else
    {
      v29 = *((_DWORD *)this + 784);
      if ( v29 )
      {
        v30 = (unsigned int)(v29 - 1);
        v31 = *((_QWORD *)this + 391);
        v30 *= 2;
        v32 = *(float *)(v31 + 8 * v30);
        v33 = *(float *)(v31 + 8 * v30 + 4);
        v34 = *(float *)(v31 + 8 * v30 + 8);
        v35 = *(float *)(v31 + 8 * v30 + 12);
      }
      else
      {
        v32 = FLOAT_N3_4028235e38;
        v34 = FLOAT_3_4028235e38;
        v33 = FLOAT_N3_4028235e38;
        v35 = FLOAT_3_4028235e38;
      }
      v36 = v178.left;
      if ( v32 > v178.left )
        v36 = v32;
      v37 = v178.top;
      if ( v33 <= v178.top )
        v33 = v178.top;
      else
        v37 = v33;
      if ( v38 <= v34 )
        v34 = v38;
      else
        v38 = v34;
      if ( v39 <= v35 )
        v35 = v39;
      else
        v39 = v35;
      if ( v34 <= v36 || v35 <= v33 )
        goto LABEL_59;
    }
    if ( v38 > v36 && v39 > v37 )
      goto LABEL_37;
LABEL_59:
    *v175 = 1;
    return v7;
  }
LABEL_37:
  v11 = 0xFFFFFFFFLL;
LABEL_38:
  v40 = *(float *)(a3 + 36);
  if ( !v10 )
  {
    if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)(a3 + 36) - 1.0) & v4) < 0.0000011920929 )
      return v7;
    if ( *(_BYTE *)(a3 + 189) )
    {
      v41 = *((_DWORD *)this + 790);
      if ( v41 )
        v6 = *(float *)(*((_QWORD *)this + 394) + 4LL * (unsigned int)(v41 - 1));
      if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(v40 - v6) & v4) > 0.0000011920929 )
      {
        v42 = CDrawingContext::PushEffectiveAlphaForNode(this, *(const struct CVisual **)a3, *(float *)(a3 + 36), 1);
        v7 = v42;
        if ( v42 < 0 )
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v42, 0x118Du, 0);
      }
      return v7;
    }
  }
  v46 = *(_BYTE *)(a3 + 189) == 0;
  v47 = (void **)((char *)this + 256);
  *(_QWORD *)&v178.right = *(_QWORD *)a3;
  Src = 0;
  *(_QWORD *)&v178.left = 8;
  if ( v46 )
  {
    v48 = *((unsigned int *)this + 67);
    if ( *((_DWORD *)this + 66) == (_DWORD)v48 )
    {
      if ( (unsigned __int64)(2 * v48) > 0xFFFFFFFF )
      {
        LODWORD(v173) = 95;
LABEL_56:
        v7 = -2147024362;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)(unsigned int)v173,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v7,
          v160);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v7,
          v163);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x11A2u, 0);
LABEL_58:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x115Cu, 0);
        goto LABEL_135;
      }
      v67 = 64;
      if ( (unsigned int)(2 * v48) > 0x40 )
        v67 = 2 * v48;
      v68 = 16LL * (unsigned int)v48;
      if ( v68 > 0xFFFFFFFF )
      {
        LODWORD(v173) = 98;
        goto LABEL_56;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / v67 <= 0x10 )
      {
        v7 = -2147024809;
        goto LABEL_57;
      }
      v69 = *v47;
      v70 = MIDL_user_allocate(16LL * v67);
      v71 = v70;
      if ( !v70 )
      {
        v7 = -2147024882;
        goto LABEL_57;
      }
      if ( v69 && (_DWORD)v68 )
        memcpy_0(v70, v69, (unsigned int)v68);
      operator delete(*v47);
      v10 = v174;
      *v47 = v71;
      *((_DWORD *)this + 67) = v67;
    }
    *(struct D2D_RECT_F *)(*((_QWORD *)this + 32) + 16LL * *((unsigned int *)this + 66)) = v178;
    v72 = *((_DWORD *)this + 69);
    v73 = *((_DWORD *)this + 66) + 1;
    *((_DWORD *)this + 66) = v73;
    if ( v72 <= v73 )
      v72 = v73;
    *((_DWORD *)this + 69) = v72;
    v74 = *((_DWORD *)this + 791);
    if ( *((_DWORD *)this + 790) == v74 )
    {
      v168 = 0;
      v172 = 0;
      v156 = Grow(4u, 0x40u, a3, v74, *((void **)this + 394), &v168, &v172);
      v7 = v156;
      if ( v156 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)(unsigned int)v156,
          v166);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x11A6u, 0);
        v158 = *((_DWORD *)this + 66);
        if ( v158 )
          *((_DWORD *)this + 66) = v158 - 1;
        goto LABEL_58;
      }
      operator delete(*((void **)this + 394));
      *((_QWORD *)this + 394) = v172;
      *((_DWORD *)this + 791) = v168;
    }
    *(_DWORD *)(*((_QWORD *)this + 394) + 4LL * (unsigned int)(*((_DWORD *)this + 790))++) = 1065353216;
    v75 = *((_DWORD *)this + 793);
    if ( v75 <= *((_DWORD *)this + 790) )
      v75 = *((_DWORD *)this + 790);
    *((_DWORD *)this + 793) = v75;
    v76 = *(_DWORD *)(a3 + 36);
LABEL_114:
    v179 = 0;
    v77 = 1;
    v178 = 0;
    if ( !v10 )
      goto LABEL_132;
    v78 = Src;
    if ( Src )
    {
      Src = 0;
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v78 + 16LL))(v78, v11);
    }
    v79 = a3 + 108;
    Src = 0;
    v80 = *(_BYTE *)(a3 + 173);
    if ( (v80 & 0x20) == 0 && 4 * (v80 & 0xF0) != 0 )
    {
      v82 = (*(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v10 + 24LL))(v10, v79, &Src);
      goto LABEL_122;
    }
    if ( (v80 & 0x20) != 0 )
    {
      v77 = 0;
      v81 = *(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v10 + 24LL);
    }
    else
    {
      if ( COERCE_FLOAT(
             COERCE_UNSIGNED_INT(
               (float)((float)((float)(COERCE_FLOAT(*(_DWORD *)(a3 + 136) & v4) * 61440.0)
                             + (float)(COERCE_FLOAT(*(_DWORD *)(a3 + 120) & v4) * 61440.0))
                     + COERCE_FLOAT(*(_DWORD *)(a3 + 168) & v4))
             - 1.0)
           & v4) >= 0.000081380211 )
      {
        v154 = 0;
        v155 = 16;
      }
      else
      {
        v154 = 1;
        v155 = -16;
      }
      v77 = v154 ^ 1;
      *(_BYTE *)(a3 + 173) = v155 ^ (v155 ^ v80) & 0xCF;
      v81 = *(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v10 + 24LL);
      if ( !v154 )
        goto LABEL_121;
    }
    v79 = 0;
LABEL_121:
    v82 = v81(v10, v79, &Src);
LABEL_122:
    v7 = v82;
    if ( v82 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v82, 0x975u, 0);
      if ( v7 != -2003238895 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x1171u, 0);
        goto LABEL_135;
      }
      v7 = 0;
      *v175 = 1;
LABEL_273:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Src);
      return v7;
    }
    if ( !v77 )
    {
      v83 = *(_DWORD *)(a3 + 112);
      v178.left = *(FLOAT *)(a3 + 108);
      *(_QWORD *)&v178.top = __PAIR64__(*(_DWORD *)(a3 + 124), v83);
      v84 = *(_DWORD *)(a3 + 156);
      v178.bottom = *(FLOAT *)(a3 + 128);
      v179 = __PAIR64__(*(_DWORD *)(a3 + 160), v84);
    }
LABEL_132:
    v85 = &v178;
    if ( v77 )
      v85 = 0;
    v86 = CDrawingContext::PushD2DLayer(this, (__int64)v85, v76, *(_BYTE *)(a3 + 184), *(_DWORD *)(a3 + 180));
    v7 = v86;
    if ( v86 >= 0 )
      goto LABEL_135;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v86, 0x1180u, 0);
    goto LABEL_273;
  }
  v88 = CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(
          (char *)this + 256,
          &v178);
  v7 = v88;
  if ( v88 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v88, 0x11A2u, 0);
LABEL_160:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x1155u, 0);
    goto LABEL_135;
  }
  v90 = *((_DWORD *)this + 791);
  if ( *((_DWORD *)this + 790) != v90 )
  {
LABEL_139:
    *(float *)(*((_QWORD *)this + 394) + 4LL * *((unsigned int *)this + 790)) = v40;
    v76 = LODWORD(FLOAT_1_0);
    v91 = *((_DWORD *)this + 793);
    if ( v91 <= ++*((_DWORD *)this + 790) )
      v91 = *((_DWORD *)this + 790);
    *((_DWORD *)this + 793) = v91;
    goto LABEL_114;
  }
  v168 = 0;
  v172 = 0;
  v157 = Grow(4u, 0x40u, v89, v90, *((void **)this + 394), &v168, &v172);
  v7 = v157;
  if ( v157 >= 0 )
  {
    operator delete(*((void **)this + 394));
    *((_QWORD *)this + 394) = v172;
    *((_DWORD *)this + 791) = v168;
    goto LABEL_139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
    (const char *)(unsigned int)v157,
    v167);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x11A6u, 0);
  v159 = *((_DWORD *)this + 66);
  if ( !v159 )
    goto LABEL_160;
  *((_DWORD *)this + 66) = v159 - 1;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x1155u, 0);
LABEL_135:
  v87 = Src;
  if ( Src )
  {
    Src = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v87 + 16LL))(v87);
  }
  return v7;
}

```

## disassembly

```asm
0x180022f20  mov     rax, rsp
0x180022f23  push    rbp
0x180022f24  push    rbx
0x180022f25  push    rsi
0x180022f26  push    rdi
0x180022f27  push    r12
0x180022f29  push    r13
0x180022f2b  push    r14
0x180022f2d  push    r15
0x180022f2f  lea     rbp, [rsp-48h]
0x180022f34  sub     rsp, 148h
0x180022f3b  movaps  xmmword ptr [rax-58h], xmm6
0x180022f3f  movaps  xmmword ptr [rax-68h], xmm7
0x180022f43  movaps  xmmword ptr [rax-78h], xmm8
0x180022f48  movaps  xmmword ptr [rax-88h], xmm9
0x180022f50  movaps  xmmword ptr [rax-98h], xmm10
0x180022f58  movaps  xmmword ptr [rax-0A8h], xmm11
0x180022f60  movaps  xmmword ptr [rax-0B8h], xmm12
0x180022f68  movaps  xmmword ptr [rax-0C8h], xmm13
0x180022f70  movaps  xmmword ptr [rax-0D8h], xmm14
0x180022f78  mov     rax, cs:__security_cookie
0x180022f7f  xor     rax, rsp
0x180022f82  mov     [rbp+80h+var_D8], rax
0x180022f86  movdqa  xmm12, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180022f8f  xor     r13d, r13d
0x180022f92  movss   xmm13, cs:__real@3f800000
0x180022f9b  mov     esi, r13d
0x180022f9e  mov     r15, r8
0x180022fa1  movss   xmm14, cs:__real@38aaaaab
0x180022faa  mov     r14, rcx
0x180022fad  mov     [rbp+80h+var_F8], rdx
0x180022fb1  mov     edi, r13d
0x180022fb4  mov     [rsp+180h+var_110], r9
0x180022fb9  mov     edx, 0FFFFFFFFh
0x180022fbe  mov     [rsp+180h+var_118], r13
0x180022fc3  mov     dword ptr [rsp+180h+var_120], 65h ; 'e'
0x180022fcb  cmp     [r8+8], rsi
0x180022fcf  jz      loc_18002324D
0x180022fd5  mov     rcx, cs:Microsoft_Windows_Dwm_Core_Provider_Context; RegHandle
0x180022fdc  lea     rdx, EVTDESC_ETWGUID_LAYEREVENT_BeginLayer_Start; EventDescriptor
0x180022fe3  call    cs:__imp_EventEnabled
0x180022fe9  test    al, al
0x180022feb  jnz     loc_180023671
0x180022ff1  mov     rcx, [r15+8]
0x180022ff5  test    rcx, rcx
0x180022ff8  jz      loc_1800238BD
0x180022ffe  mov     rax, [rcx]
0x180023001  lea     rdx, [rsp+180h+var_140]
0x180023006  mov     [rsp+180h+var_140], r13d
0x18002300b  mov     rax, [rax+40h]
0x18002300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023014  test    al, al
0x180023016  jz      loc_1800238BD
0x18002301c  cmp     [rsp+180h+var_140], 1
0x180023021  jnz     loc_1800238BD
0x180023027  lea     rcx, [r15+6Ch]
0x18002302b  xorps   xmm7, xmm7
0x18002302e  movzx   edx, byte ptr [rcx+40h]
0x180023032  movzx   eax, dl
0x180023035  sar     al, 6
0x180023038  test    al, al
0x18002303a  jg      loc_180023656
0x180023040  jns     loc_18002361D
0x180023046  cmp     [r15+0B8h], sil
0x18002304d  jz      loc_1800232DC
0x180023053  lea     rbx, [r14+2E0h]
0x18002305a  mov     rax, [rbx+8]
0x18002305e  cmp     [rax-8], sil
0x180023062  jz      loc_1800232DC
0x180023068  mov     rax, [r15+18h]
0x18002306c  test    rax, rax
0x18002306f  jz      loc_1800236C1
0x180023075  mov     rcx, [rax+38h]
0x180023079  mov     rdi, [rcx+8]
0x18002307d  test    rdi, rdi
0x180023080  jnz     short loc_180023086
0x180023082  mov     rdi, [r15+8]
0x180023086  mov     r13, [rcx+18h]
0x18002308a  lea     r9, [rcx+28h]; struct CMILMatrix *
0x18002308e  mov     r12d, [rcx+6Ch]
0x180023092  movzx   edx, byte ptr [rcx+74h]
0x180023096  mov     rcx, [rcx]
0x180023099  mov     rax, [r15]
0x18002309c  mov     r8, r13; struct CShape *
0x18002309f  mov     qword ptr [rbp+80h+var_F0.right], rax
0x1800230a3  lea     rax, [rsp+180h+var_130]
0x1800230a8  mov     [rsp+180h+var_148], rax; bool *
0x1800230ad  mov     [rsp+180h+var_150], rcx; struct CCpuClipAntialiasSink *
0x1800230b2  mov     byte ptr [rsp+180h+var_158], dl; bool
0x1800230b6  mov     [rsp+180h+var_128], rcx
0x1800230bb  mov     rcx, rbx; this
0x1800230be  mov     [rsp+180h+var_13C], dl
0x1800230c2  mov     rdx, rdi; struct CShape *
0x1800230c5  mov     qword ptr [rbp+80h+var_F0.left], 2
0x1800230cd  mov     [rsp+180h+var_130], 0
0x1800230d2  mov     [rsp+180h+var_160], r12d; int
0x1800230d7  call    ?PushCpuClipToScope@CScopedClipStack@@QEAAJPEBVCShape@@0PEBVCMILMatrix@@W4D2D1_ANTIALIAS_MODE@@_NPEAVCCpuClipAntialiasSink@@PEA_N@Z; CScopedClipStack::PushCpuClipToScope(CShape const *,CShape const *,CMILMatrix const *,D2D1_ANTIALIAS_MODE,bool,CCpuClipAntialiasSink *,bool *)
0x1800230dc  mov     edi, eax
0x1800230de  test    eax, eax
0x1800230e0  js      loc_180023A32
0x1800230e6  mov     eax, [r14+10Ch]
0x1800230ed  cmp     [r14+108h], eax
0x1800230f4  jnz     loc_1800234EC
0x1800230fa  mov     esi, eax
0x1800230fc  mov     edx, 0FFFFFFFFh
0x180023101  add     rax, rax
0x180023104  cmp     rax, rdx
0x180023107  jbe     loc_18002346C
0x18002310d  mov     dword ptr [rsp+180h+var_120], 5Fh ; '_'
0x180023115  mov     esi, 80070216h
0x18002311a  mov     rcx, [rbp+88h]; this
0x180023121  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180023128  mov     edx, dword ptr [rsp+180h+var_120]; void *
0x18002312c  mov     r9d, esi; char *
0x18002312f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023134  mov     rcx, [rbp+88h]; this
0x18002313b  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180023142  mov     r9d, esi; char *
0x180023145  mov     edx, 8Bh; void *
0x18002314a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002314f  xor     r12d, r12d
0x180023152  mov     r9d, esi; int
0x180023155  mov     [rsp+180h+var_158], r12; void *
0x18002315a  xor     r8d, r8d; unsigned int
0x18002315d  xor     edx, edx; int *
0x18002315f  mov     [rsp+180h+var_160], 0C44h; unsigned int
0x180023167  mov     ecx, 14h; unsigned int
0x18002316c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180023171  lea     r8, [rsp+180h+var_13C]; bool *
0x180023176  mov     [rsp+180h+var_13C], r12b
0x18002317b  mov     rdx, r14; struct CDrawingContext *
0x18002317e  mov     rcx, rbx; this
0x180023181  call    ?PopCpuClipFromScope@CScopedClipStack@@QEAAXPEAVCDrawingContext@@PEA_N@Z; CScopedClipStack::PopCpuClipFromScope(CDrawingContext *,bool *)
0x180023186  mov     edi, esi
0x180023188  mov     [rsp+180h+var_158], r12
0x18002318d  mov     [rsp+180h+var_160], 1107h
0x180023195  mov     r9d, edi
0x180023198  jmp     loc_180023340
0x18002319d  cmp     qword ptr [rcx-0A8h], 0
0x1800231a5  jbe     loc_18002360E
0x1800231ab  mov     eax, [r14+0C40h]
0x1800231b2  test    eax, eax
0x1800231b4  jz      loc_180023ACE
0x1800231ba  movaps  xmm2, xmm7
0x1800231bd  movaps  xmm1, xmm7
0x1800231c0  movaps  xmm3, xmm7
0x1800231c3  test    eax, eax
0x1800231c5  jz      short loc_1800231EB
0x1800231c7  lea     ecx, [rax-1]
0x1800231ca  mov     rax, [r14+0C38h]
0x1800231d1  add     rcx, rcx
0x1800231d4  movss   xmm7, dword ptr [rax+rcx*8]
0x1800231d9  movss   xmm2, dword ptr [rax+rcx*8+4]
0x1800231df  movss   xmm1, dword ptr [rax+rcx*8+8]
0x1800231e5  movss   xmm3, dword ptr [rax+rcx*8+0Ch]
0x1800231eb  movss   xmm0, [rbp+80h+var_F0.left]
0x1800231f0  comiss  xmm7, xmm0
0x1800231f3  jbe     short loc_1800231F8
0x1800231f5  movaps  xmm0, xmm7
0x1800231f8  movss   xmm4, [rbp+80h+var_F0.top]
0x1800231fd  comiss  xmm2, xmm4
0x180023200  jbe     loc_180024430
0x180023206  movaps  xmm4, xmm2
0x180023209  comiss  xmm5, xmm1
0x18002320c  jbe     loc_1800244A3
0x180023212  movaps  xmm5, xmm1
0x180023215  comiss  xmm6, xmm3
0x180023218  jbe     loc_1800244AB
0x18002321e  movaps  xmm6, xmm3
0x180023221  comiss  xmm1, xmm0
0x180023224  jbe     loc_18002345F
0x18002322a  comiss  xmm3, xmm2
0x18002322d  jbe     loc_18002345F
0x180023233  comiss  xmm5, xmm0
0x180023236  jbe     loc_18002345F
0x18002323c  comiss  xmm6, xmm4
0x18002323f  jbe     loc_18002345F
0x180023245  mov     edx, 0FFFFFFFFh
0x18002324a  xor     r13d, r13d
0x18002324d  movss   xmm6, dword ptr [r15+24h]
0x180023253  movss   xmm1, cs:__real@35a00000
0x18002325b  movaps  xmm0, xmm6
0x18002325e  subss   xmm0, xmm13
0x180023263  andps   xmm0, xmm12
0x180023267  comiss  xmm1, xmm0
0x18002326a  setnbe  al
0x18002326d  test    rdi, rdi
0x180023270  jnz     loc_1800233A8
0x180023276  test    al, al
0x180023278  jnz     loc_18002334F
0x18002327e  cmp     [r15+0BDh], al
0x180023285  jz      loc_1800233A8
0x18002328b  mov     eax, [r14+0C58h]
0x180023292  test    eax, eax
0x180023294  jnz     loc_180023B28
0x18002329a  movaps  xmm0, xmm6
0x18002329d  subss   xmm0, xmm13
0x1800232a2  andps   xmm0, xmm12
0x1800232a6  comiss  xmm1, xmm0
0x1800232a9  jnb     loc_18002334F
0x1800232af  mov     rdx, [r15]; struct CVisual *
0x1800232b2  mov     r9b, 1; bool
0x1800232b5  movaps  xmm2, xmm6; float
0x1800232b8  mov     rcx, r14; this
0x1800232bb  call    ?PushEffectiveAlphaForNode@CDrawingContext@@AEAAJPEBVCVisual@@M_N@Z; CDrawingContext::PushEffectiveAlphaForNode(CVisual const *,float,bool)
0x1800232c0  mov     esi, eax
0x1800232c2  test    eax, eax
0x1800232c4  jns     loc_18002334F
0x1800232ca  mov     [rsp+180h+var_158], r13
0x1800232cf  mov     r9d, eax
0x1800232d2  mov     [rsp+180h+var_160], 118Dh
0x1800232da  jmp     short loc_180023340
0x1800232dc  mov     r9, [r15+8]
0x1800232e0  xorps   xmm0, xmm0
0x1800232e3  mov     esi, 8898008Bh
0x1800232e8  movups  xmmword ptr [rbp+80h+var_F0.left], xmm0
0x1800232ec  test    r9, r9
0x1800232ef  jz      short loc_180023330
0x1800232f1  mov     rax, [r9]
0x1800232f4  lea     rdx, [rbp+80h+var_F0]
0x1800232f8  mov     r8, rcx
0x1800232fb  mov     rcx, r9
0x1800232fe  mov     rax, [rax+30h]
0x180023302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023307  mov     esi, eax
0x180023309  test    eax, eax
0x18002330b  jns     loc_180023C80
0x180023311  mov     [rsp+180h+var_158], r13; void *
0x180023316  mov     r9d, eax; int
0x180023319  xor     r8d, r8d; unsigned int
0x18002331c  mov     [rsp+180h+var_160], 137h; unsigned int
0x180023324  xor     edx, edx; int *
0x180023326  mov     ecx, 14h; unsigned int
0x18002332b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180023330  mov     [rsp+180h+var_158], r13; void *
0x180023335  mov     r9d, esi; int
0x180023338  mov     [rsp+180h+var_160], 112Fh; unsigned int
0x180023340  xor     r8d, r8d; unsigned int
0x180023343  xor     edx, edx; int *
0x180023345  mov     ecx, 14h; unsigned int
0x18002334a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002334f  mov     eax, esi
0x180023351  mov     rcx, [rbp+80h+var_D8]
0x180023355  xor     rcx, rsp; StackCookie
0x180023358  call    __security_check_cookie
0x18002335d  lea     r11, [rsp+180h+var_38]
0x180023365  movaps  xmm6, xmmword ptr [r11-18h]
0x18002336a  movaps  xmm7, xmmword ptr [r11-28h]
0x18002336f  movaps  xmm8, xmmword ptr [r11-38h]
0x180023374  movaps  xmm9, xmmword ptr [r11-48h]
0x180023379  movaps  xmm10, xmmword ptr [r11-58h]
0x18002337e  movaps  xmm11, xmmword ptr [r11-68h]
0x180023383  movaps  xmm12, xmmword ptr [r11-78h]
0x180023388  movaps  xmm13, xmmword ptr [r11-88h]
0x180023390  movaps  xmm14, xmmword ptr [r11-98h]
0x180023398  mov     rsp, r11
0x18002339b  pop     r15
0x18002339d  pop     r14
0x18002339f  pop     r13
0x1800233a1  pop     r12
0x1800233a3  pop     rdi
0x1800233a4  pop     rsi
0x1800233a5  pop     rbx
0x1800233a6  pop     rbp
0x1800233a7  retn
0x1800233a8  cmp     byte ptr [r15+0BDh], 0
0x1800233b0  lea     rbx, [r14+100h]
0x1800233b7  mov     rax, [r15]
0x1800233ba  mov     qword ptr [rbp+80h+var_F0.right], rax
0x1800233be  mov     [rsp+180h+Src], r13
0x1800233c3  mov     qword ptr [rbp+80h+var_F0.left], 8
0x1800233cb  jnz     loc_1800239CB
0x1800233d1  mov     eax, [rbx+0Ch]
0x1800233d4  cmp     [rbx+8], eax
0x1800233d7  jnz     loc_18002377E
0x1800233dd  lea     rcx, [rax+rax]
0x1800233e1  mov     edi, eax
0x1800233e3  cmp     rcx, rdx
0x1800233e6  jbe     loc_180023710
0x1800233ec  mov     dword ptr [rsp+180h+var_120], 5Fh ; '_'
0x1800233f4  mov     esi, 80070216h
0x1800233f9  mov     rcx, [rbp+88h]; this
0x180023400  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180023407  mov     edx, dword ptr [rsp+180h+var_120]; void *
0x18002340b  mov     r9d, esi; char *
0x18002340e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023413  mov     rcx, [rbp+88h]; this
0x18002341a  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x180023421  mov     r9d, esi; char *
0x180023424  mov     edx, 8Bh; void *
0x180023429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002342e  mov     [rsp+180h+var_158], r13; void *
0x180023433  mov     r9d, esi; int
0x180023436  xor     r8d, r8d; unsigned int
0x180023439  mov     [rsp+180h+var_160], 11A2h; unsigned int
0x180023441  xor     edx, edx; int *
0x180023443  mov     ecx, 14h; unsigned int
0x180023448  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002344d  mov     [rsp+180h+var_158], r13
0x180023452  mov     [rsp+180h+var_160], 115Ch
  ... truncated ...
```
