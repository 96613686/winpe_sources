# DriverMeta::BrushFillUsingBitmap(DpContext *,DpBitmap *,DpBrush const *,GpRuntime::GpRect &,ConvertPathToGdi *,int)

- ea: `0x1800cd174`
- end: `0x1800cde1b`
- name: `?BrushFillUsingBitmap@DriverMeta@@QEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBUDpBrush@@AEAVGpRect@GpRuntime@@PEAVConvertPathToGdi@@H@Z`
- size: `3239`
- prototype: `__int64 __fastcall(DriverMeta *, DpContext *, struct DpBitmap *, _DWORD *, __m128i *, ConvertPathToGdi *, int)`
- caller_count: `3`
- callee_count: `28`
- tags: `installer_update`

## callers

- `0x18002ac30`
- `0x180137ad0`
- `0x180137dd0`

## callees

- `0x18000e90c`
- `0x180011960`
- `0x180012634`
- `0x1800126d0`
- `0x18001319c`
- `0x18001c214`
- `0x18001f950`
- `0x18003ae34`
- `0x18003b634`
- `0x18003b96c`
- `0x180065140`
- `0x180094b64`
- `0x180099258`
- `0x1800a20c0`
- `0x1800bffe0`
- `0x1800cd174`
- `0x1800d6520`
- `0x1800dcc0c`
- `0x1800dcdf4`
- `0x1800e740c`
- `0x1800e9380`
- `0x1800ea080`
- `0x1800ff6f8`
- `0x18013703c`
- `0x1801389d8`
- `0x18013a804`
- `0x18013b53c`
- `0x180175010`

## import_xrefs

- `USER32!ReleaseDC` at `0x1800cd898`
- `USER32!ReleaseDC` at `0x1800cd898`
- `GDI32!CreateSolidBrush` at `0x1800cd533`
- `GDI32!CreateSolidBrush` at `0x1800cd76e`
- `GDI32!CreateSolidBrush` at `0x1800cd533`
- `GDI32!CreateSolidBrush` at `0x1800cd76e`
- `GDI32!SaveDC` at `0x1800cd314`
- `GDI32!SaveDC` at `0x1800cdc25`
- `GDI32!SaveDC` at `0x1800cd314`
- `GDI32!SaveDC` at `0x1800cdc25`
- `GDI32!GetStockObject` at `0x1800cd3ab`
- `GDI32!GetStockObject` at `0x1800cd3ab`
- `GDI32!SelectObject` at `0x1800cd3bd`
- `GDI32!SelectObject` at `0x1800cd85c`
- `GDI32!SelectObject` at `0x1800cd3bd`
- `GDI32!SelectObject` at `0x1800cd85c`
- `GDI32!DeleteObject` at `0x1800cd5b8`
- `GDI32!DeleteObject` at `0x1800cd7f3`
- `GDI32!DeleteObject` at `0x1800cd5b8`
- `GDI32!DeleteObject` at `0x1800cd7f3`

## pseudocode

```c
__int64 __fastcall DriverMeta::BrushFillUsingBitmap(
        DriverMeta *a1,
        DpContext *a2,
        struct DpBitmap *a3,
        _DWORD *a4,
        __m128i *a5,
        ConvertPathToGdi *a6,
        int a7)
{
  GpTexture *v7; // r15
  __m128i v10; // xmm6
  DpContext *v11; // r12
  char *v12; // rbx
  int v13; // eax
  int v14; // r14d
  __int64 result; // rax
  unsigned int v16; // r15d
  CopyOnWriteBitmap *Hdc; // rbx
  __int64 v18; // rdi
  int v19; // r15d
  int v20; // r12d
  int v21; // r13d
  int v22; // esi
  HGDIOBJ StockObject; // rax
  HGDIOBJ v24; // rax
  int v25; // r8d
  __m128i *v26; // rax
  unsigned int v27; // edx
  unsigned __int8 *v28; // rdi
  __m128i v29; // xmm1
  unsigned int v30; // ecx
  float v31; // xmm0_4
  bool v32; // zf
  int v33; // r9d
  int v34; // r10d
  unsigned int v35; // r11d
  unsigned __int8 *v36; // rdi
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  float v43; // xmm0_4
  unsigned int v44; // ecx
  HBRUSH HalftoneBrush; // rax
  HBRUSH v46; // r14
  HBRUSH AlphaMaskBrush; // rax
  __m128i *v48; // r14
  unsigned __int8 *v49; // rdi
  unsigned int v50; // edx
  __m128i v51; // xmm1
  float v52; // xmm0_4
  unsigned int v53; // ecx
  bool v54; // zf
  int v55; // r9d
  int v56; // r10d
  unsigned int v57; // r11d
  int v58; // ecx
  int v59; // ecx
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // eax
  float v64; // xmm0_4
  unsigned int v65; // ecx
  HBRUSH SolidBrush; // rax
  HBRUSH v67; // r14
  HBRUSH v68; // rax
  HWND v69; // rcx
  __int64 v70; // rax
  int v71; // r14d
  __int128 v72; // xmm0
  int v73; // eax
  float v74; // xmm0_4
  float v75; // xmm8_4
  bool v76; // r12
  float v77; // xmm8_4
  int v78; // esi
  __m128 v79; // xmm1
  int v80; // ebx
  int v81; // edi
  __m128 v82; // xmm1
  int v83; // eax
  int v84; // r13d
  __int8 *v85; // rcx
  __int8 *v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  CopyOnWriteBitmap *v90; // rax
  GpBitmap *v91; // r14
  HDC v92; // rbx
  ConvertPathToGdi *v93; // r15
  LONG v94; // edx
  int TransparencyHint; // eax
  int v96; // ecx
  unsigned int v97; // [rsp+28h] [rbp-E0h]
  int v98; // [rsp+48h] [rbp-C0h]
  int v99; // [rsp+48h] [rbp-C0h]
  __m128i v100; // [rsp+58h] [rbp-B0h] BYREF
  int v101; // [rsp+68h] [rbp-A0h]
  int v102; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v103; // [rsp+70h] [rbp-98h]
  unsigned int v104; // [rsp+74h] [rbp-94h] BYREF
  BOOL v105; // [rsp+78h] [rbp-90h]
  int v106; // [rsp+7Ch] [rbp-8Ch]
  __int64 v107; // [rsp+80h] [rbp-88h]
  __m128i *v108; // [rsp+88h] [rbp-80h]
  int v109; // [rsp+90h] [rbp-78h] BYREF
  struct DpBitmap *v110; // [rsp+98h] [rbp-70h]
  DriverMeta *v111; // [rsp+A0h] [rbp-68h]
  GpBitmap *v112; // [rsp+A8h] [rbp-60h] BYREF
  struct tagPOINT v113; // [rsp+B0h] [rbp-58h] BYREF
  int v114; // [rsp+B8h] [rbp-50h]
  LONG y; // [rsp+BCh] [rbp-4Ch]
  __int128 v116; // [rsp+C0h] [rbp-48h]
  int v117; // [rsp+D0h] [rbp-38h]
  int v118; // [rsp+D4h] [rbp-34h]
  int v119; // [rsp+D8h] [rbp-30h]
  DpContext *v120; // [rsp+E0h] [rbp-28h]
  __int128 v121; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v122; // [rsp+F8h] [rbp-10h]
  HGDIOBJ h; // [rsp+108h] [rbp+0h]
  _BYTE v124[4]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v125; // [rsp+11Ch] [rbp+14h]
  int v126; // [rsp+124h] [rbp+1Ch]
  int v127; // [rsp+128h] [rbp+20h]
  int v128[18]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v129; // [rsp+180h] [rbp+78h]
  int v130; // [rsp+190h] [rbp+88h]
  _BYTE v131[20]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v132; // [rsp+1BCh] [rbp+B4h] BYREF
  char *v133; // [rsp+240h] [rbp+138h]
  _BYTE v134[20]; // [rsp+258h] [rbp+150h] BYREF
  char v135; // [rsp+26Ch] [rbp+164h] BYREF
  char *v136; // [rsp+2F0h] [rbp+1E8h]
  _DWORD v137[308]; // [rsp+308h] [rbp+200h] BYREF

  v7 = (GpTexture *)(a4 - 6);
  v110 = a3;
  v111 = a1;
  v32 = *a4 == 4;
  v10 = *a5;
  v11 = a2;
  v120 = a2;
  v108 = a5;
  v100 = v10;
  h = a6;
  v104 = 0;
  v109 = 1;
  v112 = 0;
  v121 = 0;
  v122 = 0;
  if ( v32 )
  {
    v12 = (char *)a2 + 144;
    v13 = (*(__int64 (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 112LL))(a4 - 6, (__int64)a2 + 144) - 1;
    if ( !v13 )
    {
      v14 = 0;
      v100 = v10;
      v100.m128i_i32[2] = 1;
      goto LABEL_6;
    }
    if ( v13 == 1 )
    {
      v100 = v10;
      v14 = 1;
      v100.m128i_i32[3] = 1;
LABEL_6:
      result = GpBitmap::CreateBitmapAndFillWithBrush(
                 *((unsigned int *)v11 + 12),
                 *((unsigned int *)v11 + 13),
                 v12,
                 &v100,
                 v7,
                 &v112);
      if ( (_DWORD)result )
        return result;
      v16 = 1;
      Hdc = DpContext::GetHdc(v11, v110);
      if ( !Hdc )
        goto LABEL_86;
      LODWORD(v107) = GpBitmap::LockBits(v112, 0, 1u, 0x26200Au, (__int64)&v121);
      if ( (_DWORD)v107 )
      {
LABEL_83:
        v69 = (HWND)*((_QWORD *)v11 + 79);
        if ( v69 )
          ReleaseDC(v69, (HDC)Hdc);
        v16 = v107;
LABEL_86:
        v70 = *(_QWORD *)v112;
        goto LABEL_132;
      }
      (*(void (__fastcall **)(DriverMeta *, CopyOnWriteBitmap *, DpContext *, __m128i *, unsigned int *, int *, _DWORD))(*(_QWORD *)a1 + 40LL))(
        a1,
        Hdc,
        v11,
        v108,
        &v104,
        &v109,
        0);
      if ( a6 )
      {
        if ( !v104 )
        {
          SaveDC((HDC)Hdc);
          v104 = 1;
        }
        ConvertPathToGdi::AndClip(a6, (HDC)Hdc);
      }
      v18 = v122;
      v19 = *(unsigned __int8 *)v122;
      v20 = *(unsigned __int8 *)(v122 + 1);
      v21 = *(unsigned __int8 *)(v122 + 2);
      v22 = *(unsigned __int8 *)(v122 + 3);
      v100 = 0u;
      y = -1;
      v118 = 0;
      v117 = 0;
      *(_QWORD *)((char *)&v116 + 4) = 0;
      LODWORD(v110) = 0;
      v106 = 0;
      v101 = 0;
      v102 = 0;
      v103 = 0;
      v119 = 0;
      v113 = (struct tagPOINT)&GpMatrix::`vftable';
      HIDWORD(v116) = 1065353216;
      LODWORD(v116) = 1065353216;
      v114 = 1952533809;
      StockObject = GetStockObject(8);
      v24 = SelectObject((HDC)Hdc, StockObject);
      LODWORD(v107) = 0;
      v25 = 2;
      h = v24;
      if ( v14 )
      {
        v26 = v108;
        v27 = v121;
        v28 = (unsigned __int8 *)(v18 + 4);
        v29 = _mm_cvtsi32_si128(v108->m128i_u32[3]);
        v30 = 1;
        v31 = (float)v108->m128i_i32[1];
        if ( _mm_cvtsi128_si32(_mm_srli_si128(v10, 8)) <= 128 )
          v25 = 1;
        v98 = 1;
        v105 = v25;
        *(float *)&v100.m128i_i32[1] = v31;
        v100.m128i_i32[3] = _mm_cvtepi32_ps(v29).m128_u32[0];
        if ( (_DWORD)v121 )
        {
          v32 = (_DWORD)v121 == 1;
          while ( 1 )
          {
            if ( v32 )
            {
              v33 = v101;
              LOBYTE(v20) = v101;
              v34 = v102;
              LOBYTE(v19) = v102;
              v35 = v103;
              v22 = v103;
              LOBYTE(v21) = v106;
            }
            else
            {
              v34 = *v28;
              v36 = v28 + 1;
              v102 = v34;
              v33 = *v36++;
              v101 = v33;
              v37 = *v36++;
              v106 = v37;
              v38 = v37 - v21;
              v35 = *v36;
              v28 = v36 + 1;
              v39 = v21 - v37;
              v103 = v35;
              if ( v39 < 0 )
                v39 = v38;
              if ( v39 >= v25 )
                goto LABEL_33;
              v40 = v20 - v33;
              if ( v20 - v33 < 0 )
                v40 = v33 - v20;
              if ( v40 >= v25 )
                goto LABEL_33;
              v41 = v19 - v34;
              if ( v19 - v34 < 0 )
                v41 = v34 - v19;
              if ( v41 >= v25 )
              {
LABEL_33:
                v30 = v98;
              }
              else
              {
                v42 = v22 - v35;
                if ( (int)(v22 - v35) < 0 )
                  v42 = v35 - v22;
                v30 = v98;
                if ( v42 < v25 )
                  goto LABEL_47;
              }
              v26 = v108;
            }
            if ( v22 >= 2 )
            {
              *(float *)v100.m128i_i32 = (float)((int)v110 + v26->m128i_i32[0]);
              v43 = (float)(int)(v30 - (_DWORD)v110);
              v44 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
              *(float *)&v100.m128i_i32[2] = v43;
              if ( a7 )
                HalftoneBrush = ConvertBrushToGdi::CreateHalftoneBrush(v44);
              else
                HalftoneBrush = CreateSolidBrush(v44);
              v46 = HalftoneBrush;
              ConvertRectFToGdi::ConvertRectFToGdi(
                (ConvertRectFToGdi *)v131,
                (const struct RectF *)&v100,
                1,
                (struct GpMatrix *)&v113,
                0);
              if ( v22 <= 253 && (AlphaMaskBrush = DriverMeta::GetAlphaMaskBrush(v111, v22, 0)) != 0 )
                ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v131, (HDC)Hdc, v46, AlphaMaskBrush);
              else
                ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v131, (HDC)Hdc, v46, 15728673, 1);
              DeleteObject(v46);
              if ( v133 != &v132 )
                GpFree(v133);
              v35 = v103;
              v34 = v102;
              v33 = v101;
              v25 = v105;
              v30 = v98;
              v27 = v121;
            }
            v21 = v106;
            v20 = v33;
            LODWORD(v110) = v30;
            v19 = v34;
            v22 = v35;
LABEL_47:
            v26 = v108;
            v98 = ++v30;
            v32 = v30 == v27;
            if ( v30 > v27 )
              goto LABEL_82;
          }
        }
        goto LABEL_82;
      }
      v48 = v108;
      v49 = (unsigned __int8 *)(SDWORD2(v121) + v18);
      v50 = DWORD1(v121);
      v51 = _mm_cvtsi32_si128(v108->m128i_u32[2]);
      v52 = (float)v108->m128i_i32[0];
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v10, 12)) <= 128 )
        v25 = 1;
      v99 = 1;
      v105 = v25;
      v53 = 1;
      *(float *)v100.m128i_i32 = v52;
      v100.m128i_i32[2] = _mm_cvtepi32_ps(v51).m128_u32[0];
      if ( !DWORD1(v121) )
      {
LABEL_82:
        SelectObject((HDC)Hdc, h);
        (*(void (__fastcall **)(DriverMeta *, CopyOnWriteBitmap *, _QWORD, _QWORD))(*(_QWORD *)v111 + 48LL))(
          v111,
          Hdc,
          v104,
          (unsigned int)v109);
        v11 = v120;
        goto LABEL_83;
      }
      v54 = DWORD1(v121) == 1;
      while ( 1 )
      {
        if ( v54 )
        {
          v55 = v101;
          LOBYTE(v20) = v101;
          v56 = v102;
          LOBYTE(v19) = v102;
          v57 = v103;
          v22 = v103;
          LOBYTE(v21) = v106;
        }
        else
        {
          v58 = v49[2];
          v56 = *v49;
          v55 = v49[1];
          v57 = v49[3];
          v49 += SDWORD2(v121);
          v106 = v58;
          v59 = v58 - v21;
          v102 = v56;
          v60 = -v59;
          v101 = v55;
          v103 = v57;
          if ( v59 > 0 )
            v60 = v59;
          if ( v60 >= v25 )
            goto LABEL_68;
          v61 = v20 - v55;
          if ( v20 - v55 < 0 )
            v61 = v55 - v20;
          if ( v61 >= v25 )
            goto LABEL_68;
          v62 = v19 - v56;
          if ( v19 - v56 < 0 )
            v62 = v56 - v19;
          if ( v62 >= v25 )
          {
LABEL_68:
            v53 = v99;
          }
          else
          {
            v63 = v22 - v57;
            if ( (int)(v22 - v57) < 0 )
              v63 = v57 - v22;
            v53 = v99;
            if ( v63 < v25 )
              goto LABEL_81;
          }
        }
        if ( v22 >= 2 )
        {
          *(float *)&v100.m128i_i32[1] = (float)((int)v110 + v48->m128i_i32[1]);
          v64 = (float)(int)(v53 - (_DWORD)v110);
          v65 = (unsigned __int8)v21 | ((unsigned __int8)v19 << 16) | ((unsigned __int8)v20 << 8);
          *(float *)&v100.m128i_i32[3] = v64;
          if ( a7 )
            SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v65);
          else
            SolidBrush = CreateSolidBrush(v65);
          v67 = SolidBrush;
          ConvertRectFToGdi::ConvertRectFToGdi(
            (ConvertRectFToGdi *)v134,
            (const struct RectF *)&v100,
            1,
            (struct GpMatrix *)&v113,
            0);
          if ( v22 <= 253 && (v68 = DriverMeta::GetAlphaMaskBrush(v111, v22, 0)) != 0 )
            ConvertRectFToGdi::AlphaFill((ConvertRectFToGdi *)v134, (HDC)Hdc, v67, v68);
          else
            ConvertRectFToGdi::Fill((ConvertRectFToGdi *)v134, (HDC)Hdc, v67, 15728673, 1);
          DeleteObject(v67);
          if ( v136 != &v135 )
            GpFree(v136);
          v48 = v108;
          v57 = v103;
          v56 = v102;
          v55 = v101;
          v25 = v105;
          v53 = v99;
          v50 = DWORD1(v121);
        }
        v21 = v106;
        v20 = v55;
        LODWORD(v110) = v53;
        v19 = v56;
        v22 = v57;
LABEL_81:
        v99 = ++v53;
        v54 = v53 == v50;
        if ( v53 > v50 )
          goto LABEL_82;
      }
    }
  }
  v71 = 0;
  v72 = *((_OWORD *)v11 + 10);
  v73 = *((_DWORD *)v11 + 13) - 2;
  v114 = 1952533809;
  v118 = *((_DWORD *)v11 + 45);
  y = -1;
  v116 = v72;
  v105 = (v73 & 0xFFFFFFFD) == 0;
  v117 = *((_DWORD *)v11 + 44);
  v74 = fmaxf(*((float *)v11 + 18), *((float *)v11 + 19));
  v113 = (struct tagPOINT)&GpMatrix::`vftable';
  v119 = *((_DWORD *)v11 + 46);
  if ( *((_DWORD *)a1 + 28) || (v75 = *((float *)v11 + 22), v74 <= v75) )
  {
    v81 = v100.m128i_i32[3];
    v78 = v100.m128i_i32[2];
  }
  else
  {
    v76 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v77 = v75 / v74;
    v78 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 8));
    v79 = (__m128)COERCE_UNSIGNED_INT((float)v78);
    v79.m128_f32[0] = (float)(v79.m128_f32[0] * v77) + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      v80 = (int)_mm_round_ss(v79, v79, 9).m128_f32[0];
    else
      v80 = (int)floor(v79.m128_f32[0]);
    v81 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 12));
    v82 = (__m128)COERCE_UNSIGNED_INT((float)v81);
    v82.m128_f32[0] = (float)(v82.m128_f32[0] * v77) + 0.5;
    if ( v76 )
      v83 = (int)_mm_round_ss(v82, v82, 9).m128_f32[0];
    else
      v83 = (int)floor(v82.m128_f32[0]);
    v11 = v120;
    if ( v80 > 0 && v83 > 0 )
    {
      v78 = v80;
      v100.m128i_i64[1] = __PAIR64__(v83, v80);
      v71 = 1;
      v81 = v83;
    }
  }
  if ( *a4 == 2 && GpTexture::IsPictureFill(v7, (const struct GpMatrix *)&v113, (const struct GpRuntime::GpRect *)&v100) )
  {
    v107 = 0;
    GpTexture::GetBitmapSize(v7);
    if ( v78 > (int)v107 )
    {
      v78 = v107;
      v71 = 1;
      v100.m128i_i32[2] = v107;
    }
    if ( v81 > SHIDWORD(v107) )
    {
      v81 = HIDWORD(v107);
      v71 = 1;
      v100.m128i_i32[3] = HIDWORD(v107);
    }
  }
  v84 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 12));
  LODWORD(v107) = _mm_cvtsi128_si32(_mm_srli_si128(v10, 8));
  if ( *((_DWORD *)v111 + 28) || v78 <= 512 && v81 <= 512 )
  {
    if ( !v71 )
    {
      if ( v105 )
        GpMatrix::Translate(&v113, a2, 0, 1);
      goto LABEL_116;
    }
  }
  else
  {
    if ( v78 < v81 )
    {
      v85 = &v100.m128i_i8[12];
      v86 = &v100.m128i_i8[8];
    }
    else
    {
      v85 = &v100.m128i_i8[8];
      v86 = &v100.m128i_i8[12];
    }
    AdjustForMaximumSize(v85, v86);
    v81 = v100.m128i_i32[3];
    v78 = v100.m128i_i32[2];
  }
  GpMatrix::Translate(&v113, a2, 0, 1);
  GpMatrix::Scale(&v113, v87, v88, v89);
  v100.m128i_i64[0] = 0;
LABEL_116:
  result = GpBitmap::CreateBitmapAndFillWithBrush(*((unsigned int *)v11 + 12), 4, &v113, &v100, v7, &v112);
  if ( (_DWORD)result )
    return result;
  v16 = 1;
  v90 = DpContext::GetHdc(v11, v110);
  v91 = v112;
  v92 = (HDC)v90;
  if ( v90 )
  {
    (*(void (__fastcall **)(DriverMeta *, CopyOnWriteBitmap *, DpContext *, __m128i *, unsigned int *, int *, _DWORD))(*(_QWORD *)v111 + 40LL))(
      v111,
      v90,
      v11,
      v108,
      &v104,
      &v109,
      0);
    v93 = (ConvertPathToGdi *)h;
    if ( h )
    {
      if ( !v104 )
      {
        SaveDC(v92);
        v104 = 1;
      }
      ConvertPathToGdi::AndClip(v93, v92);
    }
    v94 = _mm_cvtsi128_si32(v10);
    v114 = v94 + v107;
    v113.x = v94;
    v113.y = _mm_cvtsi128_si32(_mm_srli_si128(v10, 4));
    y = v113.y;
    LODWORD(v116) = v94;
    DWORD1(v116) = v113.y + v84;
    v100.m128i_i64[0] = 0;
    v100.m128i_i64[1] = __PAIR64__(v81, v78);
    v16 = GpBitmap::LockBits(v91, 0, 1u, 0x26200Au, (__int64)&v121);
    if ( !v16 )
    {
      DpBitmap::DpBitmap((DpBitmap *)v124, 0);
      GpBitmap::InitializeSurfaceForGdipBitmap(v91, (__int64)v124, v121, SDWORD1(v121));
      v129 = v122;
      v125 = v121;
      v130 = DWORD2(v121);
      v127 = 4 * v121 * DWORD1(v121);
      v126 = 2498570;
      TransparencyHint = GpBitmap::GetTransparencyHint(v91, v128);
      v96 = v128[0];
      if ( TransparencyHint )
        v96 = 0;
      v128[0] = v96;
      ConvertBitmapToGdi::ConvertBitmapToGdi(
        (ConvertBitmapToGdi *)v137,
        v92,
        (struct DpBitmap *)v124,
        (const struct GpRuntime::GpRect *)&v100,
        *((_DWORD *)v111 + 28) != 0 ? 2312 : 264,
        -1,
        0);
      v16 = 1;
      if ( v137[0] == 1198932785
        && (v137[9] || (unsigned int)ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v137, v92, &v113, a7, v97)) )
      {
        v16 = 0;
      }
      GpBitmap::UnlockBits(v91, (__int64)&v121);
      ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v137);
      DpBitmap::~DpBitmap((DpBitmap *)v124);
    }
    (*(void (__fastcall **)(DriverMeta *, HDC, _QWORD, _QWORD))(*(_QWORD *)v111 + 48LL))(
      v111,
      v92,
      v104,
      (unsigned int)v109);
    DpContext::ReleaseHdc((HWND *)v11, v92, 0);
  }
  v70 = *(_QWORD *)v91;
LABEL_132:
  (*(void (**)(void))(v70 + 56))();
  return v16;
}

```

## disassembly

```asm
0x1800cd174  mov     rax, rsp
0x1800cd177  push    rbp
0x1800cd178  push    rbx
0x1800cd179  push    rsi
0x1800cd17a  push    rdi
0x1800cd17b  push    r12
0x1800cd17d  push    r13
0x1800cd17f  push    r14
0x1800cd181  push    r15
0x1800cd183  lea     rbp, [rax-768h]
0x1800cd18a  sub     rsp, 828h
0x1800cd191  movaps  xmmword ptr [rax-58h], xmm6
0x1800cd195  movaps  xmmword ptr [rax-68h], xmm7
0x1800cd199  movaps  xmmword ptr [rax-78h], xmm8
0x1800cd19e  movaps  xmmword ptr [rax-88h], xmm9
0x1800cd1a6  mov     rax, cs:__security_cookie
0x1800cd1ad  xor     rax, rsp
0x1800cd1b0  mov     [rbp+760h+var_90], rax
0x1800cd1b7  mov     rax, [rbp+760h+arg_20]
0x1800cd1be  lea     r15, [r9-18h]
0x1800cd1c2  mov     rdi, [rbp+760h+arg_28]
0x1800cd1c9  xorps   xmm0, xmm0
0x1800cd1cc  mov     [rbp+760h+var_7D0], r8
0x1800cd1d0  mov     rsi, rcx
0x1800cd1d3  xor     r8d, r8d
0x1800cd1d6  mov     [rbp+760h+var_7C8], rcx
0x1800cd1da  cmp     dword ptr [r9], 4
0x1800cd1de  mov     r13, r9
0x1800cd1e1  movups  xmm6, xmmword ptr [rax]
0x1800cd1e4  mov     r12, rdx
0x1800cd1e7  mov     [rbp+760h+var_788], rdx
0x1800cd1eb  lea     ecx, [r8+1]
0x1800cd1ef  mov     [rbp+760h+var_7E0], rax
0x1800cd1f3  movaps  [rsp+860h+var_818+8], xmm6
0x1800cd1f8  mov     [rbp+760h+h], rdi
0x1800cd1fc  mov     [rsp+860h+var_7F4], r8d
0x1800cd201  mov     [rbp+760h+var_7D8], ecx
0x1800cd204  mov     [rbp+760h+var_7C0], r8
0x1800cd208  movups  [rbp+760h+var_780], xmm0
0x1800cd20c  movups  [rbp+760h+var_770], xmm0
0x1800cd210  jnz     loc_1800CD8B8
0x1800cd216  mov     rax, [r15]
0x1800cd219  lea     rbx, [rdx+90h]
0x1800cd220  mov     rdx, rbx
0x1800cd223  mov     rcx, r15
0x1800cd226  mov     rax, [rax+70h]
0x1800cd22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd22f  sub     eax, 1
0x1800cd232  jz      short loc_1800CD250
0x1800cd234  cmp     eax, 1
0x1800cd237  jnz     loc_1800CD8B5
0x1800cd23d  mov     r13d, eax
0x1800cd240  movdqu  [rsp+860h+var_818+8], xmm6
0x1800cd246  mov     r14d, r13d
0x1800cd249  mov     [rsp+860h+var_804], r13d
0x1800cd24e  jmp     short loc_1800CD262
0x1800cd250  xor     r14d, r14d
0x1800cd253  movdqu  [rsp+860h+var_818+8], xmm6
0x1800cd259  lea     r13d, [r14+1]
0x1800cd25d  mov     [rsp+860h+var_808], r13d
0x1800cd262  mov     edx, [r12+34h]
0x1800cd267  lea     rax, [rbp+760h+var_7C0]
0x1800cd26b  mov     ecx, [r12+30h]
0x1800cd270  lea     r9, [rsp+860h+var_818+8]
0x1800cd275  mov     qword ptr [rsp+860h+var_838], rax
0x1800cd27a  mov     r8, rbx
0x1800cd27d  mov     [rsp+860h+var_840], r15
0x1800cd282  call    ?CreateBitmapAndFillWithBrush@GpBitmap@@SA?AW4Status@@W4InterpolationMode@@W4PixelOffsetMode@@PEBVGpMatrix@@PEBVGpRect@GpRuntime@@PEAVGpBrush@@PEAPEAV1@H@Z; GpBitmap::CreateBitmapAndFillWithBrush(InterpolationMode,PixelOffsetMode,GpMatrix const *,GpRuntime::GpRect const *,GpBrush *,GpBitmap * *,int)
0x1800cd287  test    eax, eax
0x1800cd289  jnz     loc_1800CDDDF
0x1800cd28f  mov     rdx, [rbp+760h+var_7D0]; struct DpBitmap *
0x1800cd293  mov     rcx, r12; this
0x1800cd296  mov     r15d, r13d
0x1800cd299  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x1800cd29e  mov     rbx, rax
0x1800cd2a1  test    rax, rax
0x1800cd2a4  jz      loc_1800CD8A9
0x1800cd2aa  mov     rcx, [rbp+760h+var_7C0]
0x1800cd2ae  lea     rax, [rbp+760h+var_780]
0x1800cd2b2  mov     r9d, 26200Ah
0x1800cd2b8  mov     [rsp+860h+var_840], rax
0x1800cd2bd  mov     r8d, r13d
0x1800cd2c0  xor     edx, edx
0x1800cd2c2  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x1800cd2c7  mov     dword ptr [rsp+860h+var_7E8], eax
0x1800cd2cb  test    eax, eax
0x1800cd2cd  jnz     loc_1800CD888
0x1800cd2d3  mov     rax, [rsi]
0x1800cd2d6  lea     rcx, [rbp+760h+var_7D8]
0x1800cd2da  and     [rsp+860h+var_830], 0
0x1800cd2df  mov     r8, r12
0x1800cd2e2  mov     r9, [rbp+760h+var_7E0]
0x1800cd2e6  mov     rdx, rbx
0x1800cd2e9  mov     qword ptr [rsp+860h+var_838], rcx
0x1800cd2ee  lea     rcx, [rsp+860h+var_7F4]
0x1800cd2f3  mov     rax, [rax+28h]
0x1800cd2f7  mov     [rsp+860h+var_840], rcx; struct GpRuntime::GpRect *
0x1800cd2fc  mov     rcx, rsi
0x1800cd2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd304  xor     ecx, ecx
0x1800cd306  test    rdi, rdi
0x1800cd309  jz      short loc_1800CD332
0x1800cd30b  cmp     [rsp+860h+var_7F4], ecx
0x1800cd30f  jnz     short loc_1800CD325
0x1800cd311  mov     rcx, rbx; hdc
0x1800cd314  call    cs:__imp_SaveDC
0x1800cd31b  nop     dword ptr [rax+rax+00h]
0x1800cd320  mov     [rsp+860h+var_7F4], r13d
0x1800cd325  mov     rdx, rbx; HDC
0x1800cd328  mov     rcx, rdi; this
0x1800cd32b  call    ?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z; ConvertPathToGdi::AndClip(HDC__ *)
0x1800cd330  xor     ecx, ecx
0x1800cd332  mov     rdi, qword ptr [rbp+760h+var_770]
0x1800cd336  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1800cd33d  and     [rsp+860h+var_804], 0
0x1800cd342  and     [rsp+860h+var_808], 0
0x1800cd347  and     dword ptr [rsp+860h+var_818+0Ch], 0
0x1800cd34c  movzx   r15d, byte ptr [rdi]
0x1800cd350  movzx   r12d, byte ptr [rdi+1]
0x1800cd355  movzx   r13d, byte ptr [rdi+2]
0x1800cd35a  movzx   esi, byte ptr [rdi+3]
0x1800cd35e  and     dword ptr [rsp+860h+var_818+8], 0
0x1800cd363  or      [rbp+760h+var_7AC], 0FFFFFFFFh
0x1800cd367  and     [rbp+760h+var_794], 0
0x1800cd36b  and     [rbp+760h+var_798], 0
0x1800cd36f  and     dword ptr [rbp+760h+var_7A8+8], 0
0x1800cd373  and     dword ptr [rbp+760h+var_7A8+4], 0
0x1800cd377  mov     dword ptr [rbp+760h+var_7D0], ecx
0x1800cd37a  mov     dword ptr [rsp+860h+var_7F0+4], ecx
0x1800cd37e  mov     [rsp+860h+var_800], ecx
0x1800cd382  mov     [rsp+860h+var_7FC], ecx
0x1800cd386  mov     [rsp+860h+var_7F8], ecx
0x1800cd38a  mov     [rbp+760h+var_790], ecx
0x1800cd38d  mov     ecx, 8; i
0x1800cd392  mov     qword ptr [rbp+760h+var_7B8.x], rax
0x1800cd396  mov     dword ptr [rbp+760h+var_7A8+0Ch], 3F800000h
0x1800cd39d  mov     dword ptr [rbp+760h+var_7A8], 3F800000h
0x1800cd3a4  mov     [rbp+760h+var_7B0], 74614D31h
0x1800cd3ab  call    cs:__imp_GetStockObject
0x1800cd3b2  nop     dword ptr [rax+rax+00h]
0x1800cd3b7  mov     rdx, rax; h
0x1800cd3ba  mov     rcx, rbx; hdc
0x1800cd3bd  call    cs:__imp_SelectObject
0x1800cd3c4  nop     dword ptr [rax+rax+00h]
0x1800cd3c9  and     dword ptr [rsp+860h+var_7E8], 0
0x1800cd3ce  mov     r8d, 2
0x1800cd3d4  mov     [rbp+760h+h], rax
0x1800cd3d8  test    r14d, r14d
0x1800cd3db  jz      loc_1800CD623
0x1800cd3e1  mov     rax, [rbp+760h+var_7E0]
0x1800cd3e5  lea     r14d, [r8-1]
0x1800cd3e9  mov     edx, dword ptr [rbp+760h+var_780]
0x1800cd3ec  add     rdi, 4
0x1800cd3f0  psrldq  xmm6, 8
0x1800cd3f5  movd    ecx, xmm6
0x1800cd3f9  movd    xmm0, dword ptr [rax+4]
0x1800cd3fe  movd    xmm1, dword ptr [rax+0Ch]
0x1800cd403  cmp     ecx, 80h
0x1800cd409  mov     ecx, r14d
0x1800cd40c  cvtdq2ps xmm0, xmm0
0x1800cd40f  cmovle  r8d, r14d
0x1800cd413  mov     [rsp+860h+var_820], ecx
0x1800cd417  mov     dword ptr [rsp+860h+var_7F0], r8d
0x1800cd41c  cvtdq2ps xmm1, xmm1
0x1800cd41f  movss   dword ptr [rsp+860h+var_818+0Ch], xmm0
0x1800cd425  movss   [rsp+860h+var_804], xmm1
0x1800cd42b  cmp     edx, r14d
0x1800cd42e  jb      loc_1800CD855
0x1800cd434  cmp     ecx, edx
0x1800cd436  jnz     short loc_1800CD45A
0x1800cd438  mov     r9d, [rsp+860h+var_800]
0x1800cd43d  mov     r12d, r9d
0x1800cd440  mov     r10d, [rsp+860h+var_7FC]
0x1800cd445  mov     r15d, r10d
0x1800cd448  mov     r11d, [rsp+860h+var_7F8]
0x1800cd44d  mov     esi, r11d
0x1800cd450  mov     r13d, dword ptr [rsp+860h+var_7F0+4]
0x1800cd455  jmp     loc_1800CD4E0
0x1800cd45a  movzx   r10d, byte ptr [rdi]
0x1800cd45e  add     rdi, r14
0x1800cd461  mov     [rsp+860h+var_7FC], r10d
0x1800cd466  movzx   r9d, byte ptr [rdi]
0x1800cd46a  add     rdi, r14
0x1800cd46d  mov     [rsp+860h+var_800], r9d
0x1800cd472  movzx   eax, byte ptr [rdi]
0x1800cd475  add     rdi, r14
0x1800cd478  mov     ecx, eax
0x1800cd47a  mov     dword ptr [rsp+860h+var_7F0+4], eax
0x1800cd47e  sub     ecx, r13d
0x1800cd481  mov     eax, ecx
0x1800cd483  movzx   r11d, byte ptr [rdi]
0x1800cd487  add     rdi, r14
0x1800cd48a  neg     eax
0x1800cd48c  mov     [rsp+860h+var_7F8], r11d
0x1800cd491  cmovs   eax, ecx
0x1800cd494  cmp     eax, r8d
0x1800cd497  jge     short loc_1800CD4D8
0x1800cd499  mov     ecx, r9d
0x1800cd49c  sub     ecx, r12d
0x1800cd49f  mov     eax, ecx
0x1800cd4a1  neg     eax
0x1800cd4a3  cmovs   eax, ecx
0x1800cd4a6  cmp     eax, r8d
0x1800cd4a9  jge     short loc_1800CD4D8
0x1800cd4ab  mov     ecx, r10d
0x1800cd4ae  sub     ecx, r15d
0x1800cd4b1  mov     eax, ecx
0x1800cd4b3  neg     eax
0x1800cd4b5  cmovs   eax, ecx
0x1800cd4b8  cmp     eax, r8d
0x1800cd4bb  jge     short loc_1800CD4D8
0x1800cd4bd  mov     ecx, r11d
0x1800cd4c0  sub     ecx, esi
0x1800cd4c2  mov     eax, ecx
0x1800cd4c4  neg     eax
0x1800cd4c6  cmovs   eax, ecx
0x1800cd4c9  mov     ecx, [rsp+860h+var_820]
0x1800cd4cd  cmp     eax, r8d
0x1800cd4d0  jl      loc_1800CD60B
0x1800cd4d6  jmp     short loc_1800CD4DC
0x1800cd4d8  mov     ecx, [rsp+860h+var_820]
0x1800cd4dc  mov     rax, [rbp+760h+var_7E0]
0x1800cd4e0  cmp     esi, 2
0x1800cd4e3  jl      loc_1800CD5FA
0x1800cd4e9  mov     eax, [rax]
0x1800cd4eb  add     eax, dword ptr [rbp+760h+var_7D0]
0x1800cd4ee  movd    xmm0, eax
0x1800cd4f2  mov     eax, ecx
0x1800cd4f4  sub     eax, dword ptr [rbp+760h+var_7D0]
0x1800cd4f7  cvtdq2ps xmm0, xmm0
0x1800cd4fa  movzx   ecx, r12b
0x1800cd4fe  shl     ecx, 8
0x1800cd501  movss   dword ptr [rsp+860h+var_818+8], xmm0
0x1800cd507  movd    xmm0, eax
0x1800cd50b  movzx   eax, r15b
0x1800cd50f  shl     eax, 10h
0x1800cd512  or      ecx, eax
0x1800cd514  movzx   eax, r13b
0x1800cd518  cvtdq2ps xmm0, xmm0
0x1800cd51b  or      ecx, eax; unsigned int
0x1800cd51d  cmp     [rbp+760h+arg_30], 0
0x1800cd524  movss   [rsp+860h+var_808], xmm0
0x1800cd52a  jz      short loc_1800CD533
0x1800cd52c  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x1800cd531  jmp     short loc_1800CD53F
0x1800cd533  call    cs:__imp_CreateSolidBrush
0x1800cd53a  nop     dword ptr [rax+rax+00h]
0x1800cd53f  and     [rsp+860h+var_840], 0
0x1800cd545  lea     r9, [rbp+760h+var_7B8]; struct GpMatrix *
0x1800cd549  mov     r15d, 1
0x1800cd54f  lea     rdx, [rsp+860h+var_818+8]; struct RectF *
0x1800cd554  mov     r8d, r15d; int
0x1800cd557  lea     rcx, [rbp+760h+var_6C0]; this
0x1800cd55e  mov     r14, rax
0x1800cd561  call    ??0ConvertRectFToGdi@@QEAA@PEBVRectF@@HPEAVGpMatrix@@PEBVGpRect@GpRuntime@@@Z; ConvertRectFToGdi::ConvertRectFToGdi(RectF const *,int,GpMatrix *,GpRuntime::GpRect const *)
0x1800cd566  cmp     esi, 0FDh
0x1800cd56c  jg      short loc_1800CD598
0x1800cd56e  mov     rcx, [rbp+760h+var_7C8]; this
0x1800cd572  xor     r8d, r8d; int
0x1800cd575  mov     edx, esi; unsigned int
0x1800cd577  call    ?GetAlphaMaskBrush@DriverMeta@@AEBAPEAUHBRUSH__@@IH@Z; DriverMeta::GetAlphaMaskBrush(uint,int)
0x1800cd57c  test    rax, rax
0x1800cd57f  jz      short loc_1800CD598
0x1800cd581  mov     r9, rax; HBRUSH
0x1800cd584  lea     rcx, [rbp+760h+var_6C0]; this
0x1800cd58b  mov     r8, r14; h
0x1800cd58e  mov     rdx, rbx; HDC
0x1800cd591  call    ?AlphaFill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z; ConvertRectFToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)
0x1800cd596  jmp     short loc_1800CD5B5
0x1800cd598  mov     r9d, 0F00021h; int
0x1800cd59e  mov     dword ptr [rsp+860h+var_840], r15d; int
0x1800cd5a3  mov     r8, r14; HBRUSH
0x1800cd5a6  lea     rcx, [rbp+760h+var_6C0]; this
0x1800cd5ad  mov     rdx, rbx; HDC
0x1800cd5b0  call    ?Fill@ConvertRectFToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@HH@Z; ConvertRectFToGdi::Fill(HDC__ *,HBRUSH__ *,int,int)
0x1800cd5b5  mov     rcx, r14; ho
0x1800cd5b8  call    cs:__imp_DeleteObject
0x1800cd5bf  nop     dword ptr [rax+rax+00h]
0x1800cd5c4  mov     rcx, [rbp+760h+var_628]
0x1800cd5cb  lea     rax, [rbp+760h+var_6AC]
0x1800cd5d2  cmp     rcx, rax
0x1800cd5d5  jz      short loc_1800CD5DC
0x1800cd5d7  call    GpFree
0x1800cd5dc  mov     r11d, [rsp+860h+var_7F8]
0x1800cd5e1  mov     r14, r15
0x1800cd5e4  mov     r10d, [rsp+860h+var_7FC]
0x1800cd5e9  mov     r9d, [rsp+860h+var_800]
0x1800cd5ee  mov     r8d, dword ptr [rsp+860h+var_7F0]
0x1800cd5f3  mov     ecx, [rsp+860h+var_820]
0x1800cd5f7  mov     edx, dword ptr [rbp+760h+var_780]
0x1800cd5fa  mov     r13d, dword ptr [rsp+860h+var_7F0+4]
0x1800cd5ff  mov     r12d, r9d
0x1800cd602  mov     dword ptr [rbp+760h+var_7D0], ecx
0x1800cd605  mov     r15d, r10d
0x1800cd608  mov     esi, r11d
0x1800cd60b  mov     rax, [rbp+760h+var_7E0]
0x1800cd60f  add     ecx, r14d
0x1800cd612  mov     [rsp+860h+var_820], ecx
0x1800cd616  cmp     ecx, edx
0x1800cd618  jbe     loc_1800CD436
  ... truncated ...
```
