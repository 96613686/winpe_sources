# DriverMeta::BrushFillUsingBitmap(DpContext *,DpBitmap *,DpBrush const *,GpRuntime::GpRect &,ConvertPathToGdi *,int)

- ea: `0x180028690`
- end: `0x18002938f`
- name: `?BrushFillUsingBitmap@DriverMeta@@QEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBUDpBrush@@AEAVGpRect@GpRuntime@@PEAVConvertPathToGdi@@H@Z`
- size: `3327`
- prototype: `enum Status __high(struct DpContext *, struct DpBitmap *, const struct DpBrush *, struct GpRuntime::GpRect *, struct ConvertPathToGdi *, int)`
- caller_count: `3`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x1800e80f0`
- `0x1800f1c70`
- `0x180142d30`

## callees

- `0x180010bd0`
- `0x180015c44`
- `0x180015cc8`
- `0x180026ea8`
- `0x1800270a4`
- `0x18002720c`
- `0x180027270`
- `0x180027fd4`
- `0x1800280cc`
- `0x180028150`
- `0x180028690`
- `0x18002a930`
- `0x18002b1b0`
- `0x18002f12c`
- `0x180033f1c`
- `0x1800b2fd0`
- `0x1800d609c`
- `0x1800f9c64`
- `0x180105d40`
- `0x1801066d0`
- `0x180119fd8`
- `0x1801427dc`
- `0x180143170`
- `0x1801443d0`
- `0x180172010`

## import_xrefs

- `USER32!ReleaseDC` at `0x180028da2`
- `USER32!ReleaseDC` at `0x18002933b`
- `USER32!ReleaseDC` at `0x180028da2`
- `USER32!ReleaseDC` at `0x18002933b`
- `GDI32!CreateSolidBrush` at `0x180028a42`
- `GDI32!CreateSolidBrush` at `0x180028c7b`
- `GDI32!CreateSolidBrush` at `0x180028a42`
- `GDI32!CreateSolidBrush` at `0x180028c7b`
- `GDI32!SaveDC` at `0x180028832`
- `GDI32!SaveDC` at `0x180029138`
- `GDI32!SaveDC` at `0x180028832`
- `GDI32!SaveDC` at `0x180029138`
- `GDI32!GetStockObject` at `0x1800288c7`
- `GDI32!GetStockObject` at `0x1800288c7`
- `GDI32!SelectObject` at `0x1800288d9`
- `GDI32!SelectObject` at `0x180028d6b`
- `GDI32!SelectObject` at `0x1800288d9`
- `GDI32!SelectObject` at `0x180028d6b`
- `GDI32!DeleteObject` at `0x180028aca`
- `GDI32!DeleteObject` at `0x180028d03`
- `GDI32!DeleteObject` at `0x180028aca`
- `GDI32!DeleteObject` at `0x180028d03`

## pseudocode

```c
__int64 __fastcall DriverMeta::BrushFillUsingBitmap(
        DriverMeta *a1,
        __int64 a2,
        void *a3,
        _DWORD *a4,
        __m128i *a5,
        ConvertPathToGdi *a6,
        int a7)
{
  GpTexture *v7; // rdi
  __int64 v10; // r13
  __m128i v11; // xmm6
  __int64 v13; // rbx
  int v14; // eax
  __int64 result; // rax
  unsigned int v16; // edi
  HDC Hdc; // rbx
  __int64 v18; // rdi
  int v19; // r14d
  int v20; // r15d
  LONG v21; // r12d
  int v22; // esi
  HGDIOBJ StockObject; // rax
  __m128i *v24; // rax
  int v25; // r9d
  unsigned int v26; // edx
  unsigned __int8 *v27; // rdi
  __m128i v28; // xmm1
  float v29; // xmm0_4
  unsigned int v30; // r8d
  unsigned int v31; // r13d
  bool v32; // zf
  int v33; // r11d
  int v34; // r10d
  unsigned __int8 *v35; // rdi
  LONG v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned int v42; // ecx
  HBRUSH HalftoneBrush; // rax
  HBRUSH v44; // r14
  HBRUSH AlphaMaskBrush; // rax
  __m128i *v46; // rcx
  int v47; // r8d
  unsigned int v48; // edx
  unsigned __int8 *v49; // rdi
  __m128i v50; // xmm1
  float v51; // xmm0_4
  unsigned int v52; // r13d
  bool v53; // zf
  int v54; // r11d
  int v55; // r10d
  unsigned int v56; // r9d
  LONG v57; // ecx
  int v58; // ecx
  int v59; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  unsigned int v63; // ecx
  HBRUSH SolidBrush; // rax
  HBRUSH v65; // r14
  HBRUSH v66; // rax
  HWND v67; // rcx
  DriverMeta *v68; // rbx
  __int128 v69; // xmm0
  int v70; // r12d
  int v71; // r15d
  int v72; // xmm1_4
  int v73; // r14d
  float v74; // xmm0_4
  float v75; // xmm7_4
  float v76; // xmm7_4
  __m128 v77; // xmm1
  int v78; // ebx
  __m128 v79; // xmm1
  int v80; // eax
  __int8 *v81; // rcx
  __int8 *v82; // rdx
  unsigned int v83; // esi
  HDC v84; // rax
  __int64 v85; // rdi
  HDC v86; // rbx
  DriverMeta *v87; // r12
  ConvertPathToGdi *v88; // rsi
  int TransparencyHint; // eax
  int v90; // edx
  int v91; // eax
  HWND v92; // rcx
  unsigned int v93; // [rsp+28h] [rbp-E0h]
  int v94; // [rsp+48h] [rbp-C0h]
  int v95; // [rsp+48h] [rbp-C0h]
  int v96; // [rsp+48h] [rbp-C0h]
  int v97; // [rsp+4Ch] [rbp-BCh]
  LONG v98; // [rsp+4Ch] [rbp-BCh]
  __m128i v99; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v100; // [rsp+68h] [rbp-A0h] BYREF
  LONG v101; // [rsp+6Ch] [rbp-9Ch]
  __int64 v102; // [rsp+70h] [rbp-98h]
  __int64 v103; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v104; // [rsp+80h] [rbp-88h]
  int v105; // [rsp+84h] [rbp-84h]
  __m128i *v106; // [rsp+88h] [rbp-80h]
  unsigned int v107; // [rsp+98h] [rbp-70h]
  unsigned int v108; // [rsp+A8h] [rbp-60h] BYREF
  DriverMeta *v109; // [rsp+B0h] [rbp-58h]
  __int64 v110; // [rsp+B8h] [rbp-50h] BYREF
  struct tagPOINT v111; // [rsp+C0h] [rbp-48h] BYREF
  int v112; // [rsp+C8h] [rbp-40h]
  int v113; // [rsp+CCh] [rbp-3Ch]
  _BYTE v114[20]; // [rsp+D0h] [rbp-38h]
  __int64 v115; // [rsp+E4h] [rbp-24h]
  __int128 v116; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v117; // [rsp+100h] [rbp-8h]
  HGDIOBJ h; // [rsp+110h] [rbp+8h]
  __int64 v119; // [rsp+118h] [rbp+10h]
  ConvertPathToGdi *v120; // [rsp+120h] [rbp+18h]
  int v121; // [rsp+128h] [rbp+20h] BYREF
  __int64 v122; // [rsp+12Ch] [rbp+24h]
  int v123; // [rsp+134h] [rbp+2Ch]
  int v124; // [rsp+138h] [rbp+30h]
  float v125; // [rsp+13Ch] [rbp+34h]
  float v126; // [rsp+140h] [rbp+38h]
  int v127; // [rsp+148h] [rbp+40h] BYREF
  __int64 v128; // [rsp+150h] [rbp+48h]
  __int128 v129; // [rsp+168h] [rbp+60h]
  __int64 v130; // [rsp+178h] [rbp+70h]
  __int64 v131; // [rsp+188h] [rbp+80h]
  __int64 v132; // [rsp+190h] [rbp+88h]
  int v133; // [rsp+1A0h] [rbp+98h]
  __int64 v134; // [rsp+1A8h] [rbp+A0h]
  _BYTE v135[20]; // [rsp+1B8h] [rbp+B0h] BYREF
  char v136; // [rsp+1CCh] [rbp+C4h] BYREF
  char *v137; // [rsp+250h] [rbp+148h]
  _BYTE v138[20]; // [rsp+268h] [rbp+160h] BYREF
  char v139; // [rsp+27Ch] [rbp+174h] BYREF
  char *v140; // [rsp+300h] [rbp+1F8h]
  _DWORD v141[308]; // [rsp+318h] [rbp+210h] BYREF

  v32 = *a4 == 4;
  v7 = (GpTexture *)(a4 - 6);
  h = a3;
  v10 = a2;
  v119 = a2;
  v11 = *a5;
  v109 = a1;
  v106 = a5;
  v99 = v11;
  v120 = a6;
  v100 = 0;
  v108 = 1;
  v110 = 0;
  v116 = 0;
  v117 = 0;
  if ( v32 )
  {
    v13 = a2 + 144;
    v14 = (*(__int64 (__fastcall **)(GpTexture *, __int64))(*(_QWORD *)v7 + 112LL))(v7, a2 + 144) - 1;
    if ( !v14 )
    {
      v99 = v11;
      v99.m128i_i32[2] = 1;
      v94 = 0;
      goto LABEL_6;
    }
    if ( v14 == 1 )
    {
      v99 = v11;
      v94 = 1;
      v99.m128i_i32[3] = 1;
LABEL_6:
      result = GpBitmap::CreateBitmapAndFillWithBrush(
                 *(unsigned int *)(v10 + 48),
                 *(unsigned int *)(v10 + 52),
                 v13,
                 &v99,
                 v7,
                 &v110);
      if ( (_DWORD)result )
        return result;
      v16 = 1;
      Hdc = DpContext::GetHdc((DpContext *)v10, (struct DpBitmap *)a3);
      if ( !Hdc )
        goto LABEL_84;
      v105 = GpBitmap::LockBits(v110, 0, 1, 2498570, &v116);
      if ( v105 )
      {
LABEL_81:
        v67 = *(HWND *)(v10 + 632);
        if ( v67 )
          ReleaseDC(v67, Hdc);
        v16 = v105;
LABEL_84:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 56LL))(v110);
        return v16;
      }
      (*(void (__fastcall **)(DriverMeta *, HDC, __int64, __m128i *, unsigned int *, unsigned int *, _DWORD))(*(_QWORD *)a1 + 40LL))(
        a1,
        Hdc,
        v10,
        v106,
        &v100,
        &v108,
        0);
      if ( a6 )
      {
        if ( !v100 )
        {
          SaveDC(Hdc);
          v100 = 1;
        }
        ConvertPathToGdi::AndClip(a6, Hdc);
      }
      v18 = v117;
      v107 = 0;
      v101 = 0;
      v97 = 0;
      v19 = *(unsigned __int8 *)v117;
      v20 = *(unsigned __int8 *)(v117 + 1);
      v21 = *(unsigned __int8 *)(v117 + 2);
      v22 = *(unsigned __int8 *)(v117 + 3);
      LODWORD(v103) = 0;
      v104 = 0;
      v99 = 0u;
      v111 = (struct tagPOINT)&GpMatrix::`vftable';
      v113 = -1;
      *(_QWORD *)&v114[12] = 1065353216;
      *(_QWORD *)v114 = 1065353216;
      v115 = 0;
      *(_DWORD *)&v114[8] = 0;
      v112 = 1952533809;
      StockObject = GetStockObject(8);
      h = SelectObject(Hdc, StockObject);
      v105 = 0;
      if ( v94 )
      {
        v24 = v106;
        v25 = 2;
        v26 = v116;
        v27 = (unsigned __int8 *)(v18 + 4);
        v28 = _mm_cvtsi32_si128(v106->m128i_u32[3]);
        v29 = (float)v106->m128i_i32[1];
        if ( _mm_cvtsi128_si32(_mm_srli_si128(v11, 8)) <= 128 )
          v25 = 1;
        v95 = 1;
        LODWORD(v102) = v25;
        v30 = 1;
        *(float *)&v99.m128i_i32[1] = v29;
        v99.m128i_i32[3] = _mm_cvtepi32_ps(v28).m128_u32[0];
        if ( (_DWORD)v116 )
        {
          v31 = v104;
          v32 = (_DWORD)v116 == 1;
          while ( 1 )
          {
            if ( v32 )
            {
              v33 = v97;
              v22 = v31;
              v34 = v103;
              LOBYTE(v20) = v97;
              LOBYTE(v21) = v101;
              LOBYTE(v19) = v103;
            }
            else
            {
              v34 = *v27;
              v35 = v27 + 1;
              LODWORD(v103) = v34;
              v33 = *v35++;
              v97 = v33;
              v36 = *v35++;
              v101 = v36;
              v31 = *v35;
              v27 = v35 + 1;
              v37 = v36 - v21;
              v38 = v21 - v36;
              if ( v38 < 0 )
                v38 = v37;
              if ( v38 < v25 )
              {
                v39 = v20 - v33;
                if ( v20 - v33 < 0 )
                  v39 = v33 - v20;
                if ( v39 < v25 )
                {
                  v40 = v19 - v34;
                  if ( v19 - v34 < 0 )
                    v40 = v34 - v19;
                  if ( v40 < v25 )
                  {
                    v41 = v22 - v31;
                    if ( (int)(v22 - v31) < 0 )
                      v41 = v31 - v22;
                    if ( v41 < v25 )
                      goto LABEL_45;
                  }
                }
              }
              v24 = v106;
            }
            if ( v22 >= 2 )
            {
              *(float *)v99.m128i_i32 = (float)(int)(v107 + v24->m128i_i32[0]);
              v42 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
              *(float *)&v99.m128i_i32[2] = (float)(int)(v30 - v107);
              if ( a7 )
                HalftoneBrush = ConvertBrushToGdi::CreateHalftoneBrush(v42);
              else
                HalftoneBrush = CreateSolidBrush(v42);
              v44 = HalftoneBrush;
              ConvertRectFToGdi::ConvertRectFToGdi(
                (ConvertRectFToGdi *)v135,
                (const struct RectF *)&v99,
                1,
                (struct GpMatrix *)&v111,
                0);
              if ( v22 <= 253 && (AlphaMaskBrush = DriverMeta::GetAlphaMaskBrush(v109, v22, 0)) != 0 )
                ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v135, Hdc, v44, AlphaMaskBrush);
              else
                ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v135, Hdc, v44, 15728673, 1);
              DeleteObject(v44);
              if ( v137 != &v136 )
                GpFree(v137);
              v33 = v97;
              v34 = v103;
              v25 = v102;
              v30 = v95;
              v26 = v116;
            }
            v21 = v101;
            v20 = v33;
            v107 = v30;
            v19 = v34;
            v22 = v31;
LABEL_45:
            v24 = v106;
            v95 = ++v30;
            v32 = v30 == v26;
            if ( v30 > v26 )
              goto LABEL_79;
          }
        }
        goto LABEL_80;
      }
      v46 = v106;
      v47 = 2;
      v48 = DWORD1(v116);
      v49 = (unsigned __int8 *)(SDWORD2(v116) + v18);
      v50 = _mm_cvtsi32_si128(v106->m128i_u32[2]);
      v51 = (float)v106->m128i_i32[0];
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v11, 12)) <= 128 )
        v47 = 1;
      LODWORD(v102) = v47;
      *(float *)v99.m128i_i32 = v51;
      v99.m128i_i32[2] = _mm_cvtepi32_ps(v50).m128_u32[0];
      if ( !DWORD1(v116) )
      {
LABEL_80:
        SelectObject(Hdc, h);
        (*(void (__fastcall **)(DriverMeta *, HDC, _QWORD, _QWORD))(*(_QWORD *)v109 + 48LL))(v109, Hdc, v100, v108);
        goto LABEL_81;
      }
      v52 = 1;
      v53 = DWORD1(v116) == 1;
      while ( 1 )
      {
        if ( v53 )
        {
          v54 = v97;
          LOBYTE(v20) = v97;
          v55 = v103;
          LOBYTE(v19) = v103;
          v56 = v104;
          v22 = v104;
          LOBYTE(v21) = v101;
        }
        else
        {
          v57 = v49[2];
          v55 = *v49;
          v54 = v49[1];
          v56 = v49[3];
          v49 += SDWORD2(v116);
          v101 = v57;
          v58 = v57 - v21;
          LODWORD(v103) = v55;
          v59 = -v58;
          v97 = v54;
          v104 = v56;
          if ( v58 > 0 )
            v59 = v58;
          if ( v59 < v47 )
          {
            v60 = v20 - v54;
            if ( v20 - v54 < 0 )
              v60 = v54 - v20;
            if ( v60 < v47 )
            {
              v61 = v19 - v55;
              if ( v19 - v55 < 0 )
                v61 = v55 - v19;
              if ( v61 < v47 )
              {
                v62 = v22 - v56;
                if ( (int)(v22 - v56) < 0 )
                  v62 = v56 - v22;
                if ( v62 < v47 )
                  goto LABEL_78;
              }
            }
          }
          v46 = v106;
        }
        if ( v22 >= 2 )
        {
          *(float *)&v99.m128i_i32[1] = (float)(int)(v107 + v46->m128i_i32[1]);
          v63 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
          *(float *)&v99.m128i_i32[3] = (float)(int)(v52 - v107);
          if ( a7 )
            SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v63);
          else
            SolidBrush = CreateSolidBrush(v63);
          v65 = SolidBrush;
          ConvertRectFToGdi::ConvertRectFToGdi(
            (ConvertRectFToGdi *)v138,
            (const struct RectF *)&v99,
            1,
            (struct GpMatrix *)&v111,
            0);
          if ( v22 <= 253 && (v66 = DriverMeta::GetAlphaMaskBrush(v109, v22, 0)) != 0 )
            ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v138, Hdc, v65, v66);
          else
            ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v138, Hdc, v65, 15728673, 1);
          DeleteObject(v65);
          if ( v140 != &v139 )
            GpFree(v140);
          v54 = v97;
          v55 = v103;
          v56 = v104;
          v47 = v102;
          v48 = DWORD1(v116);
        }
        v21 = v101;
        v20 = v54;
        v107 = v52;
        v19 = v55;
        v22 = v56;
LABEL_78:
        v46 = v106;
        v53 = ++v52 == v48;
        if ( v52 > v48 )
        {
LABEL_79:
          v10 = v119;
          goto LABEL_80;
        }
      }
    }
  }
  v68 = v109;
  v32 = ((*(_DWORD *)(v10 + 52) - 2) & 0xFFFFFFFD) == 0;
  v104 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
  v98 = v104;
  v69 = *(_OWORD *)(v10 + 160);
  v70 = 0;
  v107 = v11.m128i_i32[0];
  v101 = v11.m128i_i32[0];
  v71 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
  v72 = *(_DWORD *)(v10 + 180);
  LODWORD(v102) = v32;
  v73 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 12));
  *(_OWORD *)v114 = v69;
  v111 = (struct tagPOINT)&GpMatrix::`vftable';
  LODWORD(v69) = *(_DWORD *)(v10 + 176);
  HIDWORD(v115) = *(_DWORD *)(v10 + 184);
  *(_DWORD *)&v114[16] = v69;
  LODWORD(v115) = v72;
  v96 = v71;
  v105 = v73;
  v113 = -1;
  v112 = 1952533809;
  if ( !*((_DWORD *)v109 + 28) )
  {
    v74 = fmaxf(*(float *)(v10 + 72), *(float *)(v10 + 76));
    v75 = *(float *)(v10 + 88);
    if ( v74 > v75 )
    {
      v76 = v75 / v74;
      v77 = (__m128)COERCE_UNSIGNED_INT((float)v71);
      v77.m128_f32[0] = (float)(v77.m128_f32[0] * v76) + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v78 = (int)_mm_round_ss(v77, v77, 9).m128_f32[0];
      else
        v78 = (int)floor(v77.m128_f32[0]);
      v79 = (__m128)COERCE_UNSIGNED_INT((float)v105);
      v79.m128_f32[0] = (float)(v79.m128_f32[0] * v76) + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v80 = (int)_mm_round_ss(v79, v79, 9).m128_f32[0];
      else
        v80 = (int)floor(v79.m128_f32[0]);
      if ( v78 > 0 && v80 > 0 )
      {
        v71 = v78;
        v99.m128i_i64[1] = __PAIR64__(v80, v78);
        v73 = v80;
        v70 = 1;
      }
      v68 = v109;
    }
  }
  if ( *a4 == 2 && GpTexture::IsPictureFill(v7, (const struct GpMatrix *)&v111, (const struct GpRuntime::GpRect *)&v99) )
  {
    v103 = 0;
    GpTexture::GetBitmapSize(v7, &v103);
    if ( v71 > (int)v103 )
    {
      v71 = v103;
      v70 = 1;
      v99.m128i_i32[2] = v103;
    }
    if ( v73 > SHIDWORD(v103) )
    {
      v73 = HIDWORD(v103);
      v70 = 1;
      v99.m128i_i32[3] = HIDWORD(v103);
    }
  }
  if ( *((_DWORD *)v68 + 28) || v71 <= 512 && v73 <= 512 )
  {
    if ( !v70 )
    {
      if ( (_DWORD)v102 )
        GpMatrix::Translate(&v111, a2, a3, 1);
      goto LABEL_114;
    }
  }
  else
  {
    if ( v71 < v73 )
    {
      v81 = &v99.m128i_i8[12];
      v82 = &v99.m128i_i8[8];
    }
    else
    {
      v81 = &v99.m128i_i8[8];
      v82 = &v99.m128i_i8[12];
    }
    AdjustForMaximumSize(v81, v82);
    v73 = v99.m128i_i32[3];
    v71 = v99.m128i_i32[2];
  }
  GpMatrix::Translate(&v111, a2, a3, 1);
  GpMatrix::Scale(&v111);
  v99.m128i_i64[0] = 0;
LABEL_114:
  result = GpBitmap::CreateBitmapAndFillWithBrush(*(unsigned int *)(v10 + 48), 4, &v111, &v99, v7, &v110);
  if ( !(_DWORD)result )
  {
    v83 = 1;
    v84 = DpContext::GetHdc((DpContext *)v10, (struct DpBitmap *)h);
    v85 = v110;
    v86 = v84;
    if ( v84 )
    {
      v87 = v109;
      (*(void (__fastcall **)(DriverMeta *, HDC, __int64, __m128i *, unsigned int *, unsigned int *, _DWORD))(*(_QWORD *)v109 + 40LL))(
        v109,
        v84,
        v10,
        v106,
        &v100,
        &v108,
        0);
      v88 = v120;
      if ( v120 )
      {
        if ( !v100 )
        {
          SaveDC(v86);
          v100 = 1;
        }
        ConvertPathToGdi::AndClip(v88, v86);
      }
      v99.m128i_i64[1] = __PAIR64__(v73, v71);
      v112 = v101 + v96;
      v111.x = v101;
      *(_DWORD *)&v114[4] = v98 + v105;
      v111.y = v98;
      v113 = v98;
      *(_DWORD *)v114 = v101;
      v99.m128i_i64[0] = 0;
      v83 = GpBitmap::LockBits(v85, 0, 1, 2498570, &v116);
      if ( !v83 )
      {
        v125 = Globals::DesktopDpiX;
        v129 = 0;
        v126 = Globals::DesktopDpiY;
        v121 = 1833067569;
        v130 = 1;
        v134 = 0;
        v128 = 0;
        v131 = 0;
        v127 = 0;
        GpBitmap::InitializeSurfaceForGdipBitmap(v85, &v121, (unsigned int)v116, DWORD1(v116));
        v132 = v117;
        v122 = v116;
        v133 = DWORD2(v116);
        v124 = 4 * v116 * DWORD1(v116);
        v123 = 2498570;
        TransparencyHint = GpBitmap::GetTransparencyHint(v85, &v127);
        v90 = v127;
        v32 = TransparencyHint == 0;
        v91 = *((_DWORD *)v87 + 28);
        if ( !v32 )
          v90 = 0;
        v127 = v90;
        ConvertBitmapToGdi::ConvertBitmapToGdi(
          (ConvertBitmapToGdi *)v141,
          v86,
          (struct DpBitmap *)&v121,
          (const struct GpRuntime::GpRect *)&v99,
          v91 != 0 ? 2312 : 264,
          -1,
          0);
        v83 = 1;
        if ( v141[0] == 1198932785
          && (v141[9] || ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v141, v86, &v111, a7, v93)) )
        {
          v83 = 0;
        }
        GpBitmap::UnlockBits(v85, &v116);
        ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v141);
        if ( v128 )
          GpFree(v128);
        if ( *((_QWORD *)&v129 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v129 + 1) + 16LL))(*((_QWORD *)&v129 + 1));
      }
      (*(void (__fastcall **)(DriverMeta *, HDC, _QWORD, _QWORD))(*(_QWORD *)v87 + 48LL))(v87, v86, v100, v108);
      v92 = *(HWND *)(v10 + 632);
      if ( v92 )
        ReleaseDC(v92, v86);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 56LL))(v85);
    return v83;
  }
  return result;
}

```

## disassembly

```asm
0x180028690  mov     rax, rsp
0x180028693  push    rbp
0x180028694  push    rbx
0x180028695  push    rsi
0x180028696  push    rdi
0x180028697  push    r12
0x180028699  push    r13
0x18002869b  push    r14
0x18002869d  push    r15
0x18002869f  lea     rbp, [rax-768h]
0x1800286a6  sub     rsp, 828h
0x1800286ad  movaps  xmmword ptr [rax-58h], xmm6
0x1800286b1  movaps  xmmword ptr [rax-68h], xmm7
0x1800286b5  movaps  xmmword ptr [rax-78h], xmm8
0x1800286ba  mov     rax, cs:__security_cookie
0x1800286c1  xor     rax, rsp
0x1800286c4  mov     [rbp+760h+var_80], rax
0x1800286cb  cmp     dword ptr [r9], 4
0x1800286cf  lea     rdi, [r9-18h]
0x1800286d3  mov     rax, [rbp+760h+arg_20]
0x1800286da  xorps   xmm0, xmm0
0x1800286dd  mov     r15, [rbp+760h+arg_28]
0x1800286e4  mov     rsi, r9
0x1800286e7  mov     r12, r8
0x1800286ea  mov     [rbp+760h+h], r8
0x1800286ee  mov     r13, rdx
0x1800286f1  mov     [rbp+760h+var_750], rdx
0x1800286f5  movups  xmm6, xmmword ptr [rax]
0x1800286f8  mov     r14, rcx
0x1800286fb  mov     [rbp+760h+var_7B8], rcx
0x1800286ff  mov     [rbp+760h+var_7E0], rax
0x180028703  movaps  [rsp+860h+var_818+8], xmm6
0x180028708  mov     [rbp+760h+var_748], r15
0x18002870c  mov     [rsp+860h+var_800], 0
0x180028714  mov     [rbp+760h+var_7C0], 1
0x18002871b  mov     [rbp+760h+var_7B0], 0
0x180028723  movups  [rbp+760h+var_778], xmm0
0x180028727  movups  [rbp+760h+var_768], xmm0
0x18002872b  jnz     loc_180028DC9
0x180028731  mov     rax, [rdi]
0x180028734  lea     rbx, [rdx+90h]
0x18002873b  mov     rdx, rbx
0x18002873e  mov     rcx, rdi
0x180028741  mov     rax, [rax+70h]
0x180028745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002874a  sub     eax, 1
0x18002874d  jz      short loc_18002876A
0x18002874f  cmp     eax, 1
0x180028752  jnz     loc_180028DC9
0x180028758  mov     esi, eax
0x18002875a  movdqa  [rsp+860h+var_818+8], xmm6
0x180028760  mov     [rsp+860h+var_820], esi
0x180028764  mov     [rsp+860h+var_804], esi
0x180028768  jmp     short loc_180028781
0x18002876a  mov     esi, 1
0x18002876f  movdqa  [rsp+860h+var_818+8], xmm6
0x180028775  mov     [rsp+860h+var_808], esi
0x180028779  mov     [rsp+860h+var_820], 0
0x180028781  mov     edx, [r13+34h]
0x180028785  lea     rax, [rbp+760h+var_7B0]
0x180028789  mov     ecx, [r13+30h]
0x18002878d  lea     r9, [rsp+860h+var_818+8]
0x180028792  mov     qword ptr [rsp+860h+var_838], rax
0x180028797  mov     r8, rbx
0x18002879a  mov     [rsp+860h+var_840], rdi
0x18002879f  call    ?CreateBitmapAndFillWithBrush@GpBitmap@@SA?AW4Status@@W4InterpolationMode@@W4PixelOffsetMode@@PEBVGpMatrix@@PEBVGpRect@GpRuntime@@PEAVGpBrush@@PEAPEAV1@H@Z; GpBitmap::CreateBitmapAndFillWithBrush(InterpolationMode,PixelOffsetMode,GpMatrix const *,GpRuntime::GpRect const *,GpBrush *,GpBitmap * *,int)
0x1800287a4  test    eax, eax
0x1800287a6  jnz     loc_180029358
0x1800287ac  mov     rdx, r12; struct DpBitmap *
0x1800287af  mov     rcx, r13; this
0x1800287b2  mov     edi, esi
0x1800287b4  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x1800287b9  mov     rbx, rax
0x1800287bc  test    rax, rax
0x1800287bf  jz      loc_180028DB2
0x1800287c5  mov     rcx, [rbp+760h+var_7B0]
0x1800287c9  lea     rax, [rbp+760h+var_778]
0x1800287cd  mov     r9d, 26200Ah
0x1800287d3  mov     [rsp+860h+var_840], rax
0x1800287d8  mov     r8d, esi
0x1800287db  xor     edx, edx
0x1800287dd  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x1800287e2  mov     [rsp+860h+var_7E4], eax
0x1800287e6  test    eax, eax
0x1800287e8  jnz     loc_180028D93
0x1800287ee  mov     rax, [r14]
0x1800287f1  lea     rcx, [rbp+760h+var_7C0]
0x1800287f5  mov     r9, [rbp+760h+var_7E0]
0x1800287f9  mov     r8, r13
0x1800287fc  mov     [rsp+860h+var_830], 0
0x180028804  mov     rdx, rbx
0x180028807  mov     qword ptr [rsp+860h+var_838], rcx
0x18002880c  lea     rcx, [rsp+860h+var_800]
0x180028811  mov     rax, [rax+28h]
0x180028815  mov     [rsp+860h+var_840], rcx
0x18002881a  mov     rcx, r14
0x18002881d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028822  xor     ecx, ecx
0x180028824  test    r15, r15
0x180028827  jz      short loc_18002884F
0x180028829  cmp     [rsp+860h+var_800], ecx
0x18002882d  jnz     short loc_180028842
0x18002882f  mov     rcx, rbx; hdc
0x180028832  call    cs:__imp_SaveDC
0x180028839  nop     dword ptr [rax+rax+00h]
0x18002883e  mov     [rsp+860h+var_800], esi
0x180028842  mov     rdx, rbx; HDC
0x180028845  mov     rcx, r15; this
0x180028848  call    ?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z; ConvertPathToGdi::AndClip(HDC__ *)
0x18002884d  xor     ecx, ecx
0x18002884f  mov     rdi, qword ptr [rbp+760h+var_768]
0x180028853  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x18002885a  mov     [rbp+760h+var_7D0], ecx
0x18002885d  mov     [rsp+860h+var_7FC], ecx
0x180028861  mov     [rsp+860h+var_81C], ecx
0x180028865  movzx   r14d, byte ptr [rdi]
0x180028869  movzx   r15d, byte ptr [rdi+1]
0x18002886e  movzx   r12d, byte ptr [rdi+2]
0x180028873  movzx   esi, byte ptr [rdi+3]
0x180028877  mov     [rsp+860h+var_7F0], ecx
0x18002887b  mov     [rsp+860h+var_7E8], ecx
0x18002887f  mov     ecx, 8; i
0x180028884  mov     qword ptr [rsp+860h+var_808], 0
0x18002888d  mov     qword ptr [rsp+860h+var_818+8], 0
0x180028896  mov     qword ptr [rbp+760h+var_7A8.x], rax
0x18002889a  mov     [rbp+760h+var_79C], 0FFFFFFFFh
0x1800288a1  mov     qword ptr [rbp+760h+var_798+0Ch], 3F800000h
0x1800288a9  mov     qword ptr [rbp+760h+var_798], 3F800000h
0x1800288b1  mov     [rbp+760h+var_784], 0
0x1800288b9  mov     dword ptr [rbp+760h+var_798+8], 0
0x1800288c0  mov     [rbp+760h+var_7A0], 74614D31h
0x1800288c7  call    cs:__imp_GetStockObject
0x1800288ce  nop     dword ptr [rax+rax+00h]
0x1800288d3  mov     rdx, rax; h
0x1800288d6  mov     rcx, rbx; hdc
0x1800288d9  call    cs:__imp_SelectObject
0x1800288e0  nop     dword ptr [rax+rax+00h]
0x1800288e5  cmp     [rsp+860h+var_820], 0
0x1800288ea  mov     [rbp+760h+h], rax
0x1800288ee  mov     [rsp+860h+var_7E4], 0
0x1800288f6  jz      loc_180028B36
0x1800288fc  mov     rax, [rbp+760h+var_7E0]
0x180028900  mov     r9d, 2
0x180028906  mov     edx, dword ptr [rbp+760h+var_778]
0x180028909  add     rdi, 4
0x18002890d  psrldq  xmm6, 8
0x180028912  movd    ecx, xmm6
0x180028916  movd    xmm0, dword ptr [rax+4]
0x18002891b  movd    xmm1, dword ptr [rax+0Ch]
0x180028920  cmp     ecx, 80h
0x180028926  lea     ecx, [r9-1]
0x18002892a  cvtdq2ps xmm0, xmm0
0x18002892d  cmovle  r9d, ecx
0x180028931  mov     [rsp+860h+var_820], ecx
0x180028935  mov     dword ptr [rsp+860h+var_7F8], r9d
0x18002893a  mov     r8d, ecx
0x18002893d  cvtdq2ps xmm1, xmm1
0x180028940  movss   dword ptr [rsp+860h+var_818+0Ch], xmm0
0x180028946  movss   [rsp+860h+var_804], xmm1
0x18002894c  cmp     edx, ecx
0x18002894e  jb      loc_180028D64
0x180028954  mov     r13d, [rsp+860h+var_7E8]
0x180028959  cmp     ecx, edx
0x18002895b  jnz     short loc_180028977
0x18002895d  mov     r11d, [rsp+860h+var_81C]
0x180028962  mov     esi, r13d
0x180028965  mov     r10d, [rsp+860h+var_7F0]
0x18002896a  mov     r15d, r11d
0x18002896d  mov     r12d, [rsp+860h+var_7FC]
0x180028972  mov     r14d, r10d
0x180028975  jmp     short loc_1800289EE
0x180028977  movzx   r10d, byte ptr [rdi]
0x18002897b  add     rdi, rcx
0x18002897e  mov     [rsp+860h+var_7F0], r10d
0x180028983  movzx   r11d, byte ptr [rdi]
0x180028987  add     rdi, rcx
0x18002898a  mov     [rsp+860h+var_81C], r11d
0x18002898f  movzx   eax, byte ptr [rdi]
0x180028992  add     rdi, rcx
0x180028995  mov     [rsp+860h+var_7FC], eax
0x180028999  movzx   r13d, byte ptr [rdi]
0x18002899d  add     rdi, rcx
0x1800289a0  mov     ecx, eax
0x1800289a2  sub     ecx, r12d
0x1800289a5  mov     eax, ecx
0x1800289a7  neg     eax
0x1800289a9  cmovs   eax, ecx
0x1800289ac  cmp     eax, r9d
0x1800289af  jge     short loc_1800289EA
0x1800289b1  mov     ecx, r11d
0x1800289b4  sub     ecx, r15d
0x1800289b7  mov     eax, ecx
0x1800289b9  neg     eax
0x1800289bb  cmovs   eax, ecx
0x1800289be  cmp     eax, r9d
0x1800289c1  jge     short loc_1800289EA
0x1800289c3  mov     ecx, r10d
0x1800289c6  sub     ecx, r14d
0x1800289c9  mov     eax, ecx
0x1800289cb  neg     eax
0x1800289cd  cmovs   eax, ecx
0x1800289d0  cmp     eax, r9d
0x1800289d3  jge     short loc_1800289EA
0x1800289d5  mov     ecx, r13d
0x1800289d8  sub     ecx, esi
0x1800289da  mov     eax, ecx
0x1800289dc  neg     eax
0x1800289de  cmovs   eax, ecx
0x1800289e1  cmp     eax, r9d
0x1800289e4  jl      loc_180028B17
0x1800289ea  mov     rax, [rbp+760h+var_7E0]
0x1800289ee  cmp     esi, 2
0x1800289f1  jl      loc_180028B05
0x1800289f7  mov     ecx, [rax]
0x1800289f9  mov     eax, r8d
0x1800289fc  add     ecx, [rbp+760h+var_7D0]
0x1800289ff  sub     eax, [rbp+760h+var_7D0]
0x180028a02  movd    xmm0, ecx
0x180028a06  cvtdq2ps xmm0, xmm0
0x180028a09  movzx   ecx, r15b
0x180028a0d  shl     ecx, 8
0x180028a10  movss   dword ptr [rsp+860h+var_818+8], xmm0
0x180028a16  movd    xmm0, eax
0x180028a1a  movzx   eax, r14b
0x180028a1e  shl     eax, 10h
0x180028a21  or      ecx, eax
0x180028a23  movzx   eax, r12b
0x180028a27  cvtdq2ps xmm0, xmm0
0x180028a2a  or      ecx, eax; unsigned int
0x180028a2c  cmp     [rbp+760h+arg_30], 0
0x180028a33  movss   [rsp+860h+var_808], xmm0
0x180028a39  jz      short loc_180028A42
0x180028a3b  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x180028a40  jmp     short loc_180028A4E
0x180028a42  call    cs:__imp_CreateSolidBrush
0x180028a49  nop     dword ptr [rax+rax+00h]
0x180028a4e  mov     r15d, 1
0x180028a54  mov     [rsp+860h+var_840], 0; struct GpRuntime::GpRect *
0x180028a5d  mov     r8d, r15d; int
0x180028a60  lea     r9, [rbp+760h+var_7A8]; struct GpMatrix *
0x180028a64  lea     rdx, [rsp+860h+var_818+8]; struct RectF *
0x180028a69  mov     r14, rax
0x180028a6c  lea     rcx, [rbp+760h+var_6B0]; this
0x180028a73  call    ??0ConvertRectFToGdi@@QEAA@PEBVRectF@@HPEAVGpMatrix@@PEBVGpRect@GpRuntime@@@Z; ConvertRectFToGdi::ConvertRectFToGdi(RectF const *,int,GpMatrix *,GpRuntime::GpRect const *)
0x180028a78  cmp     esi, 0FDh
0x180028a7e  jg      short loc_180028AAA
0x180028a80  mov     rcx, [rbp+760h+var_7B8]; this
0x180028a84  xor     r8d, r8d; int
0x180028a87  mov     edx, esi; unsigned int
0x180028a89  call    ?GetAlphaMaskBrush@DriverMeta@@AEBAPEAUHBRUSH__@@IH@Z; DriverMeta::GetAlphaMaskBrush(uint,int)
0x180028a8e  test    rax, rax
0x180028a91  jz      short loc_180028AAA
0x180028a93  mov     r9, rax; HBRUSH
0x180028a96  lea     rcx, [rbp+760h+var_6B0]; this
0x180028a9d  mov     r8, r14; h
0x180028aa0  mov     rdx, rbx; HDC
0x180028aa3  call    ?AlphaFill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertRectFToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x180028aa8  jmp     short loc_180028AC7
0x180028aaa  mov     r9d, 0F00021h; int
0x180028ab0  mov     dword ptr [rsp+860h+var_840], r15d; int
0x180028ab5  mov     r8, r14; HBRUSH
0x180028ab8  lea     rcx, [rbp+760h+var_6B0]; this
0x180028abf  mov     rdx, rbx; HDC
0x180028ac2  call    ?Fill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@HH@Z; ConvertRectFToGdi::Fill(HDC__ *,HBRUSH__ *,int,int)
0x180028ac7  mov     rcx, r14; ho
0x180028aca  call    cs:__imp_DeleteObject
0x180028ad1  nop     dword ptr [rax+rax+00h]
0x180028ad6  mov     rcx, [rbp+760h+var_618]
0x180028add  lea     rax, [rbp+760h+var_69C]
0x180028ae4  cmp     rcx, rax
0x180028ae7  jz      short loc_180028AEE
0x180028ae9  call    GpFree
0x180028aee  mov     r11d, [rsp+860h+var_81C]
0x180028af3  mov     r10d, [rsp+860h+var_7F0]
0x180028af8  mov     r9d, dword ptr [rsp+860h+var_7F8]
0x180028afd  mov     r8d, [rsp+860h+var_820]
0x180028b02  mov     edx, dword ptr [rbp+760h+var_778]
0x180028b05  mov     r12d, [rsp+860h+var_7FC]
0x180028b0a  mov     r15d, r11d
0x180028b0d  mov     [rbp+760h+var_7D0], r8d
0x180028b11  mov     r14d, r10d
0x180028b14  mov     esi, r13d
0x180028b17  mov     rax, [rbp+760h+var_7E0]
0x180028b1b  mov     ecx, 1
0x180028b20  add     r8d, ecx
0x180028b23  mov     [rsp+860h+var_820], r8d
0x180028b28  cmp     r8d, edx
0x180028b2b  jbe     loc_18002895B
0x180028b31  jmp     loc_180028D60
0x180028b36  mov     rcx, [rbp+760h+var_7E0]
0x180028b3a  mov     r8d, 2
0x180028b40  movsxd  rax, dword ptr [rbp+760h+var_778+8]
0x180028b44  mov     edx, dword ptr [rbp+760h+var_778+4]
0x180028b47  add     rdi, rax
0x180028b4a  psrldq  xmm6, 0Ch
0x180028b4f  movd    xmm0, dword ptr [rcx]
0x180028b53  movd    xmm1, dword ptr [rcx+8]
0x180028b58  movd    eax, xmm6
0x180028b5c  cvtdq2ps xmm0, xmm0
0x180028b5f  cmp     eax, 80h
  ... truncated ...
```
