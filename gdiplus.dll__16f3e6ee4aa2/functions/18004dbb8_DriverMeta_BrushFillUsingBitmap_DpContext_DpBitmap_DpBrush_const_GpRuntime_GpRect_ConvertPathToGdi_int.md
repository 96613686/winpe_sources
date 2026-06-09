# DriverMeta::BrushFillUsingBitmap(DpContext *,DpBitmap *,DpBrush const *,GpRuntime::GpRect &,ConvertPathToGdi *,int)

- ea: `0x18004dbb8`
- end: `0x18004e874`
- name: `?BrushFillUsingBitmap@DriverMeta@@QEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBUDpBrush@@AEAVGpRect@GpRuntime@@PEAVConvertPathToGdi@@H@Z`
- size: `3260`
- prototype: `enum Status __high(struct DpContext *, struct DpBitmap *, const struct DpBrush *, struct GpRuntime::GpRect *, struct ConvertPathToGdi *, int)`
- caller_count: `3`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x180050220`
- `0x1800eabe0`
- `0x18013a7c0`

## callees

- `0x18001ec80`
- `0x180023ca4`
- `0x180023d20`
- `0x18003d260`
- `0x180041e78`
- `0x18004d02c`
- `0x18004d3b8`
- `0x18004dbb8`
- `0x18004eae0`
- `0x18004f028`
- `0x18004f0a8`
- `0x18004f1a0`
- `0x18004ff14`
- `0x18004ff64`
- `0x18005205c`
- `0x1800520d0`
- `0x1800ad22c`
- `0x1800f287c`
- `0x1800fe680`
- `0x1800fefe0`
- `0x1801122a8`
- `0x18013a278`
- `0x18013abf4`
- `0x18013be08`
- `0x180169010`

## import_xrefs

- `USER32!ReleaseDC` at `0x18004e29a`
- `USER32!ReleaseDC` at `0x18004e827`
- `USER32!ReleaseDC` at `0x18004e29a`
- `USER32!ReleaseDC` at `0x18004e827`
- `GDI32!CreateSolidBrush` at `0x18004df58`
- `GDI32!CreateSolidBrush` at `0x18004e185`
- `GDI32!CreateSolidBrush` at `0x18004df58`
- `GDI32!CreateSolidBrush` at `0x18004e185`
- `GDI32!SaveDC` at `0x18004dd5a`
- `GDI32!SaveDC` at `0x18004e62a`
- `GDI32!SaveDC` at `0x18004dd5a`
- `GDI32!SaveDC` at `0x18004e62a`
- `GDI32!GetStockObject` at `0x18004dde9`
- `GDI32!GetStockObject` at `0x18004dde9`
- `GDI32!SelectObject` at `0x18004ddf5`
- `GDI32!SelectObject` at `0x18004e269`
- `GDI32!SelectObject` at `0x18004ddf5`
- `GDI32!SelectObject` at `0x18004e269`
- `GDI32!DeleteObject` at `0x18004dfda`
- `GDI32!DeleteObject` at `0x18004e207`
- `GDI32!DeleteObject` at `0x18004dfda`
- `GDI32!DeleteObject` at `0x18004e207`

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
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  unsigned int v86; // esi
  HDC v87; // rax
  __int64 v88; // rdi
  HDC v89; // rbx
  DriverMeta *v90; // r12
  ConvertPathToGdi *v91; // rsi
  int TransparencyHint; // eax
  int v93; // edx
  int v94; // eax
  HWND v95; // rcx
  unsigned int v96; // [rsp+28h] [rbp-E0h]
  int v97; // [rsp+48h] [rbp-C0h]
  int v98; // [rsp+48h] [rbp-C0h]
  int v99; // [rsp+48h] [rbp-C0h]
  int v100; // [rsp+4Ch] [rbp-BCh]
  LONG v101; // [rsp+4Ch] [rbp-BCh]
  __m128i v102; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v103; // [rsp+68h] [rbp-A0h] BYREF
  LONG v104; // [rsp+6Ch] [rbp-9Ch]
  __int64 v105; // [rsp+70h] [rbp-98h]
  __int64 v106; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v107; // [rsp+80h] [rbp-88h]
  int v108; // [rsp+84h] [rbp-84h]
  __m128i *v109; // [rsp+88h] [rbp-80h]
  unsigned int v110; // [rsp+98h] [rbp-70h]
  unsigned int v111; // [rsp+A8h] [rbp-60h] BYREF
  DriverMeta *v112; // [rsp+B0h] [rbp-58h]
  __int64 v113; // [rsp+B8h] [rbp-50h] BYREF
  struct tagPOINT v114; // [rsp+C0h] [rbp-48h] BYREF
  int v115; // [rsp+C8h] [rbp-40h]
  int v116; // [rsp+CCh] [rbp-3Ch]
  _BYTE v117[20]; // [rsp+D0h] [rbp-38h]
  __int64 v118; // [rsp+E4h] [rbp-24h]
  __int128 v119; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v120; // [rsp+100h] [rbp-8h]
  HGDIOBJ h; // [rsp+110h] [rbp+8h]
  __int64 v122; // [rsp+118h] [rbp+10h]
  ConvertPathToGdi *v123; // [rsp+120h] [rbp+18h]
  int v124; // [rsp+128h] [rbp+20h] BYREF
  __int64 v125; // [rsp+12Ch] [rbp+24h]
  int v126; // [rsp+134h] [rbp+2Ch]
  int v127; // [rsp+138h] [rbp+30h]
  float v128; // [rsp+13Ch] [rbp+34h]
  float v129; // [rsp+140h] [rbp+38h]
  int v130; // [rsp+148h] [rbp+40h] BYREF
  __int64 v131; // [rsp+150h] [rbp+48h]
  __int128 v132; // [rsp+168h] [rbp+60h]
  __int64 v133; // [rsp+178h] [rbp+70h]
  __int64 v134; // [rsp+188h] [rbp+80h]
  __int64 v135; // [rsp+190h] [rbp+88h]
  int v136; // [rsp+1A0h] [rbp+98h]
  __int64 v137; // [rsp+1A8h] [rbp+A0h]
  _BYTE v138[20]; // [rsp+1B8h] [rbp+B0h] BYREF
  char v139; // [rsp+1CCh] [rbp+C4h] BYREF
  char *v140; // [rsp+250h] [rbp+148h]
  _BYTE v141[20]; // [rsp+268h] [rbp+160h] BYREF
  char v142; // [rsp+27Ch] [rbp+174h] BYREF
  char *v143; // [rsp+300h] [rbp+1F8h]
  _DWORD v144[308]; // [rsp+318h] [rbp+210h] BYREF

  v32 = *a4 == 4;
  v7 = (GpTexture *)(a4 - 6);
  h = a3;
  v10 = a2;
  v122 = a2;
  v11 = *a5;
  v112 = a1;
  v109 = a5;
  v102 = v11;
  v123 = a6;
  v103 = 0;
  v111 = 1;
  v113 = 0;
  v119 = 0;
  v120 = 0;
  if ( v32 )
  {
    v13 = a2 + 144;
    v14 = (*(__int64 (__fastcall **)(GpTexture *, __int64))(*(_QWORD *)v7 + 112LL))(v7, a2 + 144) - 1;
    if ( !v14 )
    {
      v102 = v11;
      v102.m128i_i32[2] = 1;
      v97 = 0;
      goto LABEL_6;
    }
    if ( v14 == 1 )
    {
      v102 = v11;
      v97 = 1;
      v102.m128i_i32[3] = 1;
LABEL_6:
      result = GpBitmap::CreateBitmapAndFillWithBrush(
                 *(unsigned int *)(v10 + 48),
                 *(unsigned int *)(v10 + 52),
                 v13,
                 &v102,
                 v7,
                 &v113);
      if ( (_DWORD)result )
        return result;
      v16 = 1;
      Hdc = DpContext::GetHdc((DpContext *)v10, (struct DpBitmap *)a3);
      if ( !Hdc )
        goto LABEL_84;
      v108 = GpBitmap::LockBits(v113, 0, 1, 2498570, &v119);
      if ( v108 )
      {
LABEL_81:
        v67 = *(HWND *)(v10 + 632);
        if ( v67 )
          ReleaseDC(v67, Hdc);
        v16 = v108;
LABEL_84:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 56LL))(v113);
        return v16;
      }
      (*(void (__fastcall **)(DriverMeta *, HDC, __int64, __m128i *, unsigned int *, unsigned int *, _DWORD))(*(_QWORD *)a1 + 40LL))(
        a1,
        Hdc,
        v10,
        v109,
        &v103,
        &v111,
        0);
      if ( a6 )
      {
        if ( !v103 )
        {
          SaveDC(Hdc);
          v103 = 1;
        }
        ConvertPathToGdi::AndClip(a6, Hdc);
      }
      v18 = v120;
      v110 = 0;
      v104 = 0;
      v100 = 0;
      v19 = *(unsigned __int8 *)v120;
      v20 = *(unsigned __int8 *)(v120 + 1);
      v21 = *(unsigned __int8 *)(v120 + 2);
      v22 = *(unsigned __int8 *)(v120 + 3);
      LODWORD(v106) = 0;
      v107 = 0;
      v102 = 0u;
      v114 = (struct tagPOINT)&GpMatrix::`vftable';
      v116 = -1;
      *(_QWORD *)&v117[12] = 1065353216;
      *(_QWORD *)v117 = 1065353216;
      v118 = 0;
      *(_DWORD *)&v117[8] = 0;
      v115 = 1952533809;
      StockObject = GetStockObject(8);
      h = SelectObject(Hdc, StockObject);
      v108 = 0;
      if ( v97 )
      {
        v24 = v109;
        v25 = 2;
        v26 = v119;
        v27 = (unsigned __int8 *)(v18 + 4);
        v28 = _mm_cvtsi32_si128(v109->m128i_u32[3]);
        v29 = (float)v109->m128i_i32[1];
        if ( _mm_cvtsi128_si32(_mm_srli_si128(v11, 8)) <= 128 )
          v25 = 1;
        v98 = 1;
        LODWORD(v105) = v25;
        v30 = 1;
        *(float *)&v102.m128i_i32[1] = v29;
        v102.m128i_i32[3] = _mm_cvtepi32_ps(v28).m128_u32[0];
        if ( (_DWORD)v119 )
        {
          v31 = v107;
          v32 = (_DWORD)v119 == 1;
          while ( 1 )
          {
            if ( v32 )
            {
              v33 = v100;
              v22 = v31;
              v34 = v106;
              LOBYTE(v20) = v100;
              LOBYTE(v21) = v104;
              LOBYTE(v19) = v106;
            }
            else
            {
              v34 = *v27;
              v35 = v27 + 1;
              LODWORD(v106) = v34;
              v33 = *v35++;
              v100 = v33;
              v36 = *v35++;
              v104 = v36;
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
              v24 = v109;
            }
            if ( v22 >= 2 )
            {
              *(float *)v102.m128i_i32 = (float)(int)(v110 + v24->m128i_i32[0]);
              v42 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
              *(float *)&v102.m128i_i32[2] = (float)(int)(v30 - v110);
              if ( a7 )
                HalftoneBrush = ConvertBrushToGdi::CreateHalftoneBrush(v42);
              else
                HalftoneBrush = CreateSolidBrush(v42);
              v44 = HalftoneBrush;
              ConvertRectFToGdi::ConvertRectFToGdi(
                (ConvertRectFToGdi *)v138,
                (const struct RectF *)&v102,
                1,
                (struct GpMatrix *)&v114,
                0);
              if ( v22 <= 253 && (AlphaMaskBrush = DriverMeta::GetAlphaMaskBrush(v112, v22, 0)) != 0 )
                ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v138, Hdc, v44, AlphaMaskBrush);
              else
                ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v138, Hdc, v44, 15728673, 1);
              DeleteObject(v44);
              if ( v140 != &v139 )
                GpFree(v140);
              v33 = v100;
              v34 = v106;
              v25 = v105;
              v30 = v98;
              v26 = v119;
            }
            v21 = v104;
            v20 = v33;
            v110 = v30;
            v19 = v34;
            v22 = v31;
LABEL_45:
            v24 = v109;
            v98 = ++v30;
            v32 = v30 == v26;
            if ( v30 > v26 )
              goto LABEL_79;
          }
        }
        goto LABEL_80;
      }
      v46 = v109;
      v47 = 2;
      v48 = DWORD1(v119);
      v49 = (unsigned __int8 *)(SDWORD2(v119) + v18);
      v50 = _mm_cvtsi32_si128(v109->m128i_u32[2]);
      v51 = (float)v109->m128i_i32[0];
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v11, 12)) <= 128 )
        v47 = 1;
      LODWORD(v105) = v47;
      *(float *)v102.m128i_i32 = v51;
      v102.m128i_i32[2] = _mm_cvtepi32_ps(v50).m128_u32[0];
      if ( !DWORD1(v119) )
      {
LABEL_80:
        SelectObject(Hdc, h);
        (*(void (__fastcall **)(DriverMeta *, HDC, _QWORD, _QWORD))(*(_QWORD *)v112 + 48LL))(v112, Hdc, v103, v111);
        goto LABEL_81;
      }
      v52 = 1;
      v53 = DWORD1(v119) == 1;
      while ( 1 )
      {
        if ( v53 )
        {
          v54 = v100;
          LOBYTE(v20) = v100;
          v55 = v106;
          LOBYTE(v19) = v106;
          v56 = v107;
          v22 = v107;
          LOBYTE(v21) = v104;
        }
        else
        {
          v57 = v49[2];
          v55 = *v49;
          v54 = v49[1];
          v56 = v49[3];
          v49 += SDWORD2(v119);
          v104 = v57;
          v58 = v57 - v21;
          LODWORD(v106) = v55;
          v59 = -v58;
          v100 = v54;
          v107 = v56;
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
          v46 = v109;
        }
        if ( v22 >= 2 )
        {
          *(float *)&v102.m128i_i32[1] = (float)(int)(v110 + v46->m128i_i32[1]);
          v63 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
          *(float *)&v102.m128i_i32[3] = (float)(int)(v52 - v110);
          if ( a7 )
            SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v63);
          else
            SolidBrush = CreateSolidBrush(v63);
          v65 = SolidBrush;
          ConvertRectFToGdi::ConvertRectFToGdi(
            (ConvertRectFToGdi *)v141,
            (const struct RectF *)&v102,
            1,
            (struct GpMatrix *)&v114,
            0);
          if ( v22 <= 253 && (v66 = DriverMeta::GetAlphaMaskBrush(v112, v22, 0)) != 0 )
            ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v141, Hdc, v65, v66);
          else
            ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v141, Hdc, v65, 15728673, 1);
          DeleteObject(v65);
          if ( v143 != &v142 )
            GpFree(v143);
          v54 = v100;
          v55 = v106;
          v56 = v107;
          v47 = v105;
          v48 = DWORD1(v119);
        }
        v21 = v104;
        v20 = v54;
        v110 = v52;
        v19 = v55;
        v22 = v56;
LABEL_78:
        v46 = v109;
        v53 = ++v52 == v48;
        if ( v52 > v48 )
        {
LABEL_79:
          v10 = v122;
          goto LABEL_80;
        }
      }
    }
  }
  v68 = v112;
  v32 = ((*(_DWORD *)(v10 + 52) - 2) & 0xFFFFFFFD) == 0;
  v107 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
  v101 = v107;
  v69 = *(_OWORD *)(v10 + 160);
  v70 = 0;
  v110 = v11.m128i_i32[0];
  v104 = v11.m128i_i32[0];
  v71 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
  v72 = *(_DWORD *)(v10 + 180);
  LODWORD(v105) = v32;
  v73 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 12));
  *(_OWORD *)v117 = v69;
  v114 = (struct tagPOINT)&GpMatrix::`vftable';
  LODWORD(v69) = *(_DWORD *)(v10 + 176);
  HIDWORD(v118) = *(_DWORD *)(v10 + 184);
  *(_DWORD *)&v117[16] = v69;
  LODWORD(v118) = v72;
  v99 = v71;
  v108 = v73;
  v116 = -1;
  v115 = 1952533809;
  if ( !*((_DWORD *)v112 + 28) )
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
      v79 = (__m128)COERCE_UNSIGNED_INT((float)v108);
      v79.m128_f32[0] = (float)(v79.m128_f32[0] * v76) + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v80 = (int)_mm_round_ss(v79, v79, 9).m128_f32[0];
      else
        v80 = (int)floor(v79.m128_f32[0]);
      if ( v78 > 0 && v80 > 0 )
      {
        v71 = v78;
        v102.m128i_i64[1] = __PAIR64__(v80, v78);
        v73 = v80;
        v70 = 1;
      }
      v68 = v112;
    }
  }
  if ( *a4 == 2 && GpTexture::IsPictureFill(v7, (const struct GpMatrix *)&v114, (const struct GpRuntime::GpRect *)&v102) )
  {
    v106 = 0;
    GpTexture::GetBitmapSize(v7, &v106);
    if ( v71 > (int)v106 )
    {
      v71 = v106;
      v70 = 1;
      v102.m128i_i32[2] = v106;
    }
    if ( v73 > SHIDWORD(v106) )
    {
      v73 = HIDWORD(v106);
      v70 = 1;
      v102.m128i_i32[3] = HIDWORD(v106);
    }
  }
  if ( *((_DWORD *)v68 + 28) || v71 <= 512 && v73 <= 512 )
  {
    if ( !v70 )
    {
      if ( (_DWORD)v105 )
        GpMatrix::Translate(&v114, a2, a3, 1);
      goto LABEL_114;
    }
  }
  else
  {
    if ( v71 < v73 )
    {
      v81 = &v102.m128i_i8[12];
      v82 = &v102.m128i_i8[8];
    }
    else
    {
      v81 = &v102.m128i_i8[8];
      v82 = &v102.m128i_i8[12];
    }
    AdjustForMaximumSize(v81, v82);
    v73 = v102.m128i_i32[3];
    v71 = v102.m128i_i32[2];
  }
  GpMatrix::Translate(&v114, a2, a3, 1);
  GpMatrix::Scale(&v114, v83, v84, v85);
  v102.m128i_i64[0] = 0;
LABEL_114:
  result = GpBitmap::CreateBitmapAndFillWithBrush(*(unsigned int *)(v10 + 48), 4, &v114, &v102, v7, &v113);
  if ( !(_DWORD)result )
  {
    v86 = 1;
    v87 = DpContext::GetHdc((DpContext *)v10, (struct DpBitmap *)h);
    v88 = v113;
    v89 = v87;
    if ( v87 )
    {
      v90 = v112;
      (*(void (__fastcall **)(DriverMeta *, HDC, __int64, __m128i *, unsigned int *, unsigned int *, _DWORD))(*(_QWORD *)v112 + 40LL))(
        v112,
        v87,
        v10,
        v109,
        &v103,
        &v111,
        0);
      v91 = v123;
      if ( v123 )
      {
        if ( !v103 )
        {
          SaveDC(v89);
          v103 = 1;
        }
        ConvertPathToGdi::AndClip(v91, v89);
      }
      v102.m128i_i64[1] = __PAIR64__(v73, v71);
      v115 = v104 + v99;
      v114.x = v104;
      *(_DWORD *)&v117[4] = v101 + v108;
      v114.y = v101;
      v116 = v101;
      *(_DWORD *)v117 = v104;
      v102.m128i_i64[0] = 0;
      v86 = GpBitmap::LockBits(v88, 0, 1, 2498570, &v119);
      if ( !v86 )
      {
        v128 = Globals::DesktopDpiX;
        v132 = 0;
        v129 = Globals::DesktopDpiY;
        v124 = 1833067569;
        v133 = 1;
        v137 = 0;
        v131 = 0;
        v134 = 0;
        v130 = 0;
        GpBitmap::InitializeSurfaceForGdipBitmap(v88, &v124, (unsigned int)v119, DWORD1(v119));
        v135 = v120;
        v125 = v119;
        v136 = DWORD2(v119);
        v127 = 4 * v119 * DWORD1(v119);
        v126 = 2498570;
        TransparencyHint = GpBitmap::GetTransparencyHint(v88, &v130);
        v93 = v130;
        v32 = TransparencyHint == 0;
        v94 = *((_DWORD *)v90 + 28);
        if ( !v32 )
          v93 = 0;
        v130 = v93;
        ConvertBitmapToGdi::ConvertBitmapToGdi(
          (ConvertBitmapToGdi *)v144,
          v89,
          (struct DpBitmap *)&v124,
          (const struct GpRuntime::GpRect *)&v102,
          v94 != 0 ? 2312 : 264,
          -1,
          0);
        v86 = 1;
        if ( v144[0] == 1198932785
          && (v144[9] || ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v144, v89, &v114, a7, v96)) )
        {
          v86 = 0;
        }
        GpBitmap::UnlockBits(v88, &v119);
        ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v144);
        if ( v131 )
          GpFree(v131);
        if ( *((_QWORD *)&v132 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v132 + 1) + 16LL))(*((_QWORD *)&v132 + 1));
      }
      (*(void (__fastcall **)(DriverMeta *, HDC, _QWORD, _QWORD))(*(_QWORD *)v90 + 48LL))(v90, v89, v103, v111);
      v95 = *(HWND *)(v10 + 632);
      if ( v95 )
        ReleaseDC(v95, v89);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 56LL))(v88);
    return v86;
  }
  return result;
}

```

## disassembly

```asm
0x18004dbb8  mov     rax, rsp
0x18004dbbb  push    rbp
0x18004dbbc  push    rbx
0x18004dbbd  push    rsi
0x18004dbbe  push    rdi
0x18004dbbf  push    r12
0x18004dbc1  push    r13
0x18004dbc3  push    r14
0x18004dbc5  push    r15
0x18004dbc7  lea     rbp, [rax-768h]
0x18004dbce  sub     rsp, 828h
0x18004dbd5  movaps  xmmword ptr [rax-58h], xmm6
0x18004dbd9  movaps  xmmword ptr [rax-68h], xmm7
0x18004dbdd  movaps  xmmword ptr [rax-78h], xmm8
0x18004dbe2  mov     rax, cs:__security_cookie
0x18004dbe9  xor     rax, rsp
0x18004dbec  mov     [rbp+760h+var_80], rax
0x18004dbf3  cmp     dword ptr [r9], 4
0x18004dbf7  lea     rdi, [r9-18h]
0x18004dbfb  mov     rax, [rbp+760h+arg_20]
0x18004dc02  xorps   xmm0, xmm0
0x18004dc05  mov     r15, [rbp+760h+arg_28]
0x18004dc0c  mov     rsi, r9
0x18004dc0f  mov     r12, r8
0x18004dc12  mov     [rbp+760h+h], r8
0x18004dc16  mov     r13, rdx
0x18004dc19  mov     [rbp+760h+var_750], rdx
0x18004dc1d  movups  xmm6, xmmword ptr [rax]
0x18004dc20  mov     r14, rcx
0x18004dc23  mov     [rbp+760h+var_7B8], rcx
0x18004dc27  mov     [rbp+760h+var_7E0], rax
0x18004dc2b  movaps  [rsp+860h+var_818+8], xmm6
0x18004dc30  mov     [rbp+760h+var_748], r15
0x18004dc34  mov     [rsp+860h+var_800], 0
0x18004dc3c  mov     [rbp+760h+var_7C0], 1
0x18004dc43  mov     [rbp+760h+var_7B0], 0
0x18004dc4b  movups  [rbp+760h+var_778], xmm0
0x18004dc4f  movups  [rbp+760h+var_768], xmm0
0x18004dc53  jnz     loc_18004E2BB
0x18004dc59  mov     rax, [rdi]
0x18004dc5c  lea     rbx, [rdx+90h]
0x18004dc63  mov     rdx, rbx
0x18004dc66  mov     rcx, rdi
0x18004dc69  mov     rax, [rax+70h]
0x18004dc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc72  sub     eax, 1
0x18004dc75  jz      short loc_18004DC92
0x18004dc77  cmp     eax, 1
0x18004dc7a  jnz     loc_18004E2BB
0x18004dc80  mov     esi, eax
0x18004dc82  movdqa  [rsp+860h+var_818+8], xmm6
0x18004dc88  mov     [rsp+860h+var_820], esi
0x18004dc8c  mov     [rsp+860h+var_804], esi
0x18004dc90  jmp     short loc_18004DCA9
0x18004dc92  mov     esi, 1
0x18004dc97  movdqa  [rsp+860h+var_818+8], xmm6
0x18004dc9d  mov     [rsp+860h+var_808], esi
0x18004dca1  mov     [rsp+860h+var_820], 0
0x18004dca9  mov     edx, [r13+34h]
0x18004dcad  lea     rax, [rbp+760h+var_7B0]
0x18004dcb1  mov     ecx, [r13+30h]
0x18004dcb5  lea     r9, [rsp+860h+var_818+8]
0x18004dcba  mov     qword ptr [rsp+860h+var_838], rax
0x18004dcbf  mov     r8, rbx
0x18004dcc2  mov     [rsp+860h+var_840], rdi
0x18004dcc7  call    ?CreateBitmapAndFillWithBrush@GpBitmap@@SA?AW4Status@@W4InterpolationMode@@W4PixelOffsetMode@@PEBVGpMatrix@@PEBVGpRect@GpRuntime@@PEAVGpBrush@@PEAPEAV1@H@Z; GpBitmap::CreateBitmapAndFillWithBrush(InterpolationMode,PixelOffsetMode,GpMatrix const *,GpRuntime::GpRect const *,GpBrush *,GpBitmap * *,int)
0x18004dccc  test    eax, eax
0x18004dcce  jnz     loc_18004E83E
0x18004dcd4  mov     rdx, r12; struct DpBitmap *
0x18004dcd7  mov     rcx, r13; this
0x18004dcda  mov     edi, esi
0x18004dcdc  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x18004dce1  mov     rbx, rax
0x18004dce4  test    rax, rax
0x18004dce7  jz      loc_18004E2A4
0x18004dced  mov     rcx, [rbp+760h+var_7B0]
0x18004dcf1  lea     rax, [rbp+760h+var_778]
0x18004dcf5  mov     r9d, 26200Ah
0x18004dcfb  mov     [rsp+860h+var_840], rax
0x18004dd00  mov     r8d, esi
0x18004dd03  xor     edx, edx
0x18004dd05  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18004dd0a  mov     [rsp+860h+var_7E4], eax
0x18004dd0e  test    eax, eax
0x18004dd10  jnz     loc_18004E28B
0x18004dd16  mov     rax, [r14]
0x18004dd19  lea     rcx, [rbp+760h+var_7C0]
0x18004dd1d  mov     r9, [rbp+760h+var_7E0]
0x18004dd21  mov     r8, r13
0x18004dd24  mov     [rsp+860h+var_830], 0
0x18004dd2c  mov     rdx, rbx
0x18004dd2f  mov     qword ptr [rsp+860h+var_838], rcx
0x18004dd34  lea     rcx, [rsp+860h+var_800]
0x18004dd39  mov     rax, [rax+28h]
0x18004dd3d  mov     [rsp+860h+var_840], rcx
0x18004dd42  mov     rcx, r14
0x18004dd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd4a  xor     ecx, ecx
0x18004dd4c  test    r15, r15
0x18004dd4f  jz      short loc_18004DD71
0x18004dd51  cmp     [rsp+860h+var_800], ecx
0x18004dd55  jnz     short loc_18004DD64
0x18004dd57  mov     rcx, rbx; hdc
0x18004dd5a  call    cs:__imp_SaveDC
0x18004dd60  mov     [rsp+860h+var_800], esi
0x18004dd64  mov     rdx, rbx; HDC
0x18004dd67  mov     rcx, r15; this
0x18004dd6a  call    ?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z; ConvertPathToGdi::AndClip(HDC__ *)
0x18004dd6f  xor     ecx, ecx
0x18004dd71  mov     rdi, qword ptr [rbp+760h+var_768]
0x18004dd75  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x18004dd7c  mov     [rbp+760h+var_7D0], ecx
0x18004dd7f  mov     [rsp+860h+var_7FC], ecx
0x18004dd83  mov     [rsp+860h+var_81C], ecx
0x18004dd87  movzx   r14d, byte ptr [rdi]
0x18004dd8b  movzx   r15d, byte ptr [rdi+1]
0x18004dd90  movzx   r12d, byte ptr [rdi+2]
0x18004dd95  movzx   esi, byte ptr [rdi+3]
0x18004dd99  mov     [rsp+860h+var_7F0], ecx
0x18004dd9d  mov     [rsp+860h+var_7E8], ecx
0x18004dda1  mov     ecx, 8; i
0x18004dda6  mov     qword ptr [rsp+860h+var_808], 0
0x18004ddaf  mov     qword ptr [rsp+860h+var_818+8], 0
0x18004ddb8  mov     qword ptr [rbp+760h+var_7A8.x], rax
0x18004ddbc  mov     [rbp+760h+var_79C], 0FFFFFFFFh
0x18004ddc3  mov     qword ptr [rbp+760h+var_798+0Ch], 3F800000h
0x18004ddcb  mov     qword ptr [rbp+760h+var_798], 3F800000h
0x18004ddd3  mov     [rbp+760h+var_784], 0
0x18004dddb  mov     dword ptr [rbp+760h+var_798+8], 0
0x18004dde2  mov     [rbp+760h+var_7A0], 74614D31h
0x18004dde9  call    cs:__imp_GetStockObject
0x18004ddef  mov     rdx, rax; h
0x18004ddf2  mov     rcx, rbx; hdc
0x18004ddf5  call    cs:__imp_SelectObject
0x18004ddfb  cmp     [rsp+860h+var_820], 0
0x18004de00  mov     [rbp+760h+h], rax
0x18004de04  mov     [rsp+860h+var_7E4], 0
0x18004de0c  jz      loc_18004E040
0x18004de12  mov     rax, [rbp+760h+var_7E0]
0x18004de16  mov     r9d, 2
0x18004de1c  mov     edx, dword ptr [rbp+760h+var_778]
0x18004de1f  add     rdi, 4
0x18004de23  psrldq  xmm6, 8
0x18004de28  movd    ecx, xmm6
0x18004de2c  movd    xmm0, dword ptr [rax+4]
0x18004de31  movd    xmm1, dword ptr [rax+0Ch]
0x18004de36  cmp     ecx, 80h
0x18004de3c  lea     ecx, [r9-1]
0x18004de40  cvtdq2ps xmm0, xmm0
0x18004de43  cmovle  r9d, ecx
0x18004de47  mov     [rsp+860h+var_820], ecx
0x18004de4b  mov     dword ptr [rsp+860h+var_7F8], r9d
0x18004de50  mov     r8d, ecx
0x18004de53  cvtdq2ps xmm1, xmm1
0x18004de56  movss   dword ptr [rsp+860h+var_818+0Ch], xmm0
0x18004de5c  movss   [rsp+860h+var_804], xmm1
0x18004de62  cmp     edx, ecx
0x18004de64  jb      loc_18004E262
0x18004de6a  mov     r13d, [rsp+860h+var_7E8]
0x18004de6f  cmp     ecx, edx
0x18004de71  jnz     short loc_18004DE8D
0x18004de73  mov     r11d, [rsp+860h+var_81C]
0x18004de78  mov     esi, r13d
0x18004de7b  mov     r10d, [rsp+860h+var_7F0]
0x18004de80  mov     r15d, r11d
0x18004de83  mov     r12d, [rsp+860h+var_7FC]
0x18004de88  mov     r14d, r10d
0x18004de8b  jmp     short loc_18004DF04
0x18004de8d  movzx   r10d, byte ptr [rdi]
0x18004de91  add     rdi, rcx
0x18004de94  mov     [rsp+860h+var_7F0], r10d
0x18004de99  movzx   r11d, byte ptr [rdi]
0x18004de9d  add     rdi, rcx
0x18004dea0  mov     [rsp+860h+var_81C], r11d
0x18004dea5  movzx   eax, byte ptr [rdi]
0x18004dea8  add     rdi, rcx
0x18004deab  mov     [rsp+860h+var_7FC], eax
0x18004deaf  movzx   r13d, byte ptr [rdi]
0x18004deb3  add     rdi, rcx
0x18004deb6  mov     ecx, eax
0x18004deb8  sub     ecx, r12d
0x18004debb  mov     eax, ecx
0x18004debd  neg     eax
0x18004debf  cmovs   eax, ecx
0x18004dec2  cmp     eax, r9d
0x18004dec5  jge     short loc_18004DF00
0x18004dec7  mov     ecx, r11d
0x18004deca  sub     ecx, r15d
0x18004decd  mov     eax, ecx
0x18004decf  neg     eax
0x18004ded1  cmovs   eax, ecx
0x18004ded4  cmp     eax, r9d
0x18004ded7  jge     short loc_18004DF00
0x18004ded9  mov     ecx, r10d
0x18004dedc  sub     ecx, r14d
0x18004dedf  mov     eax, ecx
0x18004dee1  neg     eax
0x18004dee3  cmovs   eax, ecx
0x18004dee6  cmp     eax, r9d
0x18004dee9  jge     short loc_18004DF00
0x18004deeb  mov     ecx, r13d
0x18004deee  sub     ecx, esi
0x18004def0  mov     eax, ecx
0x18004def2  neg     eax
0x18004def4  cmovs   eax, ecx
0x18004def7  cmp     eax, r9d
0x18004defa  jl      loc_18004E021
0x18004df00  mov     rax, [rbp+760h+var_7E0]
0x18004df04  cmp     esi, 2
0x18004df07  jl      loc_18004E00F
0x18004df0d  mov     ecx, [rax]
0x18004df0f  mov     eax, r8d
0x18004df12  add     ecx, [rbp+760h+var_7D0]
0x18004df15  sub     eax, [rbp+760h+var_7D0]
0x18004df18  movd    xmm0, ecx
0x18004df1c  cvtdq2ps xmm0, xmm0
0x18004df1f  movzx   ecx, r15b
0x18004df23  shl     ecx, 8
0x18004df26  movss   dword ptr [rsp+860h+var_818+8], xmm0
0x18004df2c  movd    xmm0, eax
0x18004df30  movzx   eax, r14b
0x18004df34  shl     eax, 10h
0x18004df37  or      ecx, eax
0x18004df39  movzx   eax, r12b
0x18004df3d  cvtdq2ps xmm0, xmm0
0x18004df40  or      ecx, eax; unsigned int
0x18004df42  cmp     [rbp+760h+arg_30], 0
0x18004df49  movss   [rsp+860h+var_808], xmm0
0x18004df4f  jz      short loc_18004DF58
0x18004df51  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x18004df56  jmp     short loc_18004DF5E
0x18004df58  call    cs:__imp_CreateSolidBrush
0x18004df5e  mov     r15d, 1
0x18004df64  mov     [rsp+860h+var_840], 0; struct GpRuntime::GpRect *
0x18004df6d  mov     r8d, r15d; int
0x18004df70  lea     r9, [rbp+760h+var_7A8]; struct GpMatrix *
0x18004df74  lea     rdx, [rsp+860h+var_818+8]; struct RectF *
0x18004df79  mov     r14, rax
0x18004df7c  lea     rcx, [rbp+760h+var_6B0]; this
0x18004df83  call    ??0ConvertRectFToGdi@@QEAA@PEBVRectF@@HPEAVGpMatrix@@PEBVGpRect@GpRuntime@@@Z; ConvertRectFToGdi::ConvertRectFToGdi(RectF const *,int,GpMatrix *,GpRuntime::GpRect const *)
0x18004df88  cmp     esi, 0FDh
0x18004df8e  jg      short loc_18004DFBA
0x18004df90  mov     rcx, [rbp+760h+var_7B8]; this
0x18004df94  xor     r8d, r8d; int
0x18004df97  mov     edx, esi; unsigned int
0x18004df99  call    ?GetAlphaMaskBrush@DriverMeta@@AEBAPEAUHBRUSH__@@IH@Z; DriverMeta::GetAlphaMaskBrush(uint,int)
0x18004df9e  test    rax, rax
0x18004dfa1  jz      short loc_18004DFBA
0x18004dfa3  mov     r9, rax; HBRUSH
0x18004dfa6  lea     rcx, [rbp+760h+var_6B0]; this
0x18004dfad  mov     r8, r14; h
0x18004dfb0  mov     rdx, rbx; HDC
0x18004dfb3  call    ?AlphaFill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertRectFToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x18004dfb8  jmp     short loc_18004DFD7
0x18004dfba  mov     r9d, 0F00021h; int
0x18004dfc0  mov     dword ptr [rsp+860h+var_840], r15d; int
0x18004dfc5  mov     r8, r14; HBRUSH
0x18004dfc8  lea     rcx, [rbp+760h+var_6B0]; this
0x18004dfcf  mov     rdx, rbx; HDC
0x18004dfd2  call    ?Fill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@HH@Z; ConvertRectFToGdi::Fill(HDC__ *,HBRUSH__ *,int,int)
0x18004dfd7  mov     rcx, r14; ho
0x18004dfda  call    cs:__imp_DeleteObject
0x18004dfe0  mov     rcx, [rbp+760h+var_618]
0x18004dfe7  lea     rax, [rbp+760h+var_69C]
0x18004dfee  cmp     rcx, rax
0x18004dff1  jz      short loc_18004DFF8
0x18004dff3  call    GpFree
0x18004dff8  mov     r11d, [rsp+860h+var_81C]
0x18004dffd  mov     r10d, [rsp+860h+var_7F0]
0x18004e002  mov     r9d, dword ptr [rsp+860h+var_7F8]
0x18004e007  mov     r8d, [rsp+860h+var_820]
0x18004e00c  mov     edx, dword ptr [rbp+760h+var_778]
0x18004e00f  mov     r12d, [rsp+860h+var_7FC]
0x18004e014  mov     r15d, r11d
0x18004e017  mov     [rbp+760h+var_7D0], r8d
0x18004e01b  mov     r14d, r10d
0x18004e01e  mov     esi, r13d
0x18004e021  mov     rax, [rbp+760h+var_7E0]
0x18004e025  mov     ecx, 1
0x18004e02a  add     r8d, ecx
0x18004e02d  mov     [rsp+860h+var_820], r8d
0x18004e032  cmp     r8d, edx
0x18004e035  jbe     loc_18004DE71
0x18004e03b  jmp     loc_18004E25E
0x18004e040  mov     rcx, [rbp+760h+var_7E0]
0x18004e044  mov     r8d, 2
0x18004e04a  movsxd  rax, dword ptr [rbp+760h+var_778+8]
0x18004e04e  mov     edx, dword ptr [rbp+760h+var_778+4]
0x18004e051  add     rdi, rax
0x18004e054  psrldq  xmm6, 0Ch
0x18004e059  movd    xmm0, dword ptr [rcx]
0x18004e05d  movd    xmm1, dword ptr [rcx+8]
0x18004e062  movd    eax, xmm6
0x18004e066  cvtdq2ps xmm0, xmm0
0x18004e069  cmp     eax, 80h
0x18004e06e  lea     eax, [r8-1]
0x18004e072  cmovle  r8d, eax
0x18004e076  mov     dword ptr [rsp+860h+var_7F8], r8d
0x18004e07b  movss   dword ptr [rsp+860h+var_818+8], xmm0
0x18004e081  cvtdq2ps xmm1, xmm1
  ... truncated ...
```
