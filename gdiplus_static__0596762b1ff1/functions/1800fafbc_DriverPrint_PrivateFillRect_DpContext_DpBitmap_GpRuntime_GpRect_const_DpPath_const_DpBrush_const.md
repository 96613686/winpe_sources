# DriverPrint::PrivateFillRect(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpPath const *,DpBrush const *)

- ea: `0x1800fafbc`
- end: `0x1800fcf31`
- name: `?PrivateFillRect@DriverPrint@@AEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpPath@@PEBUDpBrush@@@Z`
- size: `8053`
- prototype: ``
- caller_count: `2`
- callee_count: `53`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003eb90`
- `0x18013f940`

## callees

- `0x1800058d0`
- `0x18000c200`
- `0x18000f6b0`
- `0x180011bc0`
- `0x180011e24`
- `0x180012220`
- `0x180015c44`
- `0x180019dd8`
- `0x18001df60`
- `0x180021770`
- `0x180026ea8`
- `0x180027270`
- `0x180027fd4`
- `0x1800280cc`
- `0x180028150`
- `0x180033f1c`
- `0x180034e70`
- `0x180036328`
- `0x18003d7d0`
- `0x18003e8c4`
- `0x18003fa10`
- `0x180043c9c`
- `0x18004ad00`
- `0x180057928`
- `0x180080604`
- `0x180086fc0`
- `0x1800a83fc`
- `0x1800b2fd0`
- `0x1800cb44c`
- `0x1800d6764`
- `0x1800e37f0`
- `0x1800e83e8`
- `0x1800e869c`
- `0x1800f9c64`
- `0x1800fafbc`
- `0x180105d40`
- `0x1801066a0`
- `0x1801066d0`
- `0x180106718`
- `0x180106724`
- `0x180118a2c`
- `0x180138858`
- `0x180138c4c`
- `0x180139310`
- `0x18013f734`
- `0x180140118`
- `0x1801402ac`
- `0x180140330`
- `0x18014057c`
- `0x180140a0c`

## import_xrefs

- `GDI32!SetROP2` at `0x1800fb835`
- `GDI32!SetROP2` at `0x1800fb865`
- `GDI32!SetROP2` at `0x1800fbda9`
- `GDI32!SetROP2` at `0x1800fbdd9`
- `GDI32!SetROP2` at `0x1800fb835`
- `GDI32!SetROP2` at `0x1800fb865`
- `GDI32!SetROP2` at `0x1800fbda9`
- `GDI32!SetROP2` at `0x1800fbdd9`
- `GDI32!GetStockObject` at `0x1800fb807`
- `GDI32!GetStockObject` at `0x1800fbd0d`
- `GDI32!GetStockObject` at `0x1800fb807`
- `GDI32!GetStockObject` at `0x1800fbd0d`

## pseudocode

```c
__int64 __fastcall DriverPrint::PrivateFillRect(
        __int64 *a1,
        __int64 a2,
        struct DpBitmap *a3,
        unsigned int *a4,
        GpPath *a5,
        __int64 a6)
{
  unsigned int v7; // ecx
  __int64 v9; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 result; // rax
  GpTexture *v14; // rdi
  __int64 v15; // rax
  unsigned int BufferDIB; // r12d
  __int64 (__fastcall *v17)(__int64, __int64); // rax
  __int32 v18; // eax
  int v19; // xmm8_4
  EpScanDIB *v20; // r11
  int v21; // edi
  __int128 v22; // xmm0
  unsigned int v23; // xmm0_4
  int v24; // eax
  unsigned int v25; // xmm11_4
  unsigned int v26; // xmm12_4
  int v27; // xmm13_4
  unsigned int v28; // xmm14_4
  unsigned int v29; // xmm15_4
  int v30; // r9d
  int v31; // r10d
  __m128i v32; // xmm0
  int v33; // eax
  float v34; // xmm10_4
  __int32 v35; // xmm9_4
  double v36; // xmm0_8
  float v37; // xmm1_4
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // r8
  int v49; // eax
  int v50; // xmm1_4
  int v51; // eax
  int v52; // eax
  GpPath *v53; // rdi
  __int64 v54; // rdx
  __int64 v55; // r8
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  GpPathGradient *v60; // r15
  int v61; // eax
  int v62; // eax
  HDC ContextHdc; // rax
  __int64 v64; // rbx
  HDC v65; // r15
  __int64 v66; // rax
  HBRUSH StockObject; // rax
  HBRUSH v68; // rbx
  int v69; // edi
  int v70; // eax
  int IsRectangular; // eax
  signed int v72; // r8d
  int v73; // ecx
  int v74; // eax
  bool v75; // cc
  signed int v76; // ecx
  int v77; // eax
  signed int v78; // r8d
  signed int v79; // ecx
  int v80; // eax
  HDC v81; // rax
  HDC v82; // r15
  __m128i v83; // xmm0
  __m128i v84; // xmm1
  __m128i v85; // xmm0
  __int64 v86; // rax
  _DWORD *v87; // rdx
  unsigned int v88; // ebx
  unsigned int v89; // ecx
  void (__fastcall *v90)(__int64 *, HDC, __int64, unsigned int *, __int32 *, unsigned int *, _DWORD); // rax
  GpPath *v91; // rbx
  HBRUSH AlphaMaskBrush; // rax
  HBRUSH v93; // rbx
  int v94; // edi
  bool v95; // zf
  unsigned int v96; // ecx
  LONG v97; // r8d
  LONG v98; // ecx
  unsigned int v99; // ecx
  int v100; // ecx
  int v101; // eax
  int v102; // ecx
  unsigned int v103; // r15d
  int v104; // eax
  int v105; // xmm0_4
  int v106; // eax
  struct DpBitmap *v107; // rdx
  unsigned int v108; // r9d
  struct GpBitmap *Bitmap; // rax
  __int64 v110; // rcx
  bool v111; // di
  LONG v112; // eax
  unsigned int v113; // xmm1_4
  unsigned int v114; // eax
  float v115; // xmm0_4
  __m128 v116; // xmm1
  int v117; // eax
  float v118; // xmm1_4
  float v119; // xmm0_4
  float v120; // xmm0_4
  __m128 v121; // xmm1
  int v122; // r10d
  double v123; // xmm0_8
  __m128 v124; // xmm1
  int v125; // eax
  double v126; // xmm0_8
  __m128 v127; // xmm1
  __m128 v128; // xmm1
  int v129; // eax
  __m128 v130; // xmm1
  int v131; // eax
  __int64 v132; // rax
  __m128 v133; // xmm1
  int v134; // eax
  double v135; // xmm0_8
  int v136; // r11d
  __int32 v137; // r8d
  int v138; // ecx
  int v139; // r9d
  float v140; // xmm7_4
  __m128 v141; // xmm1
  int v142; // eax
  __m128i v143; // xmm6
  float v144; // xmm6_4
  __m128 v145; // xmm1
  int v146; // eax
  __m128 v147; // xmm1
  int v148; // eax
  __m128 v149; // xmm1
  int v150; // eax
  GpMatrix *v151; // rdi
  LONG v152; // xmm9_4
  LONG v153; // xmm10_4
  LONG v154; // xmm11_4
  LONG v155; // xmm12_4
  int v156; // xmm7_4
  int v157; // xmm8_4
  int v158; // xmm13_4
  int v159; // xmm14_4
  int v160; // xmm15_4
  float v161; // xmm5_4
  float v162; // xmm0_4
  float v163; // xmm1_4
  float v164; // xmm3_4
  float v165; // xmm4_4
  float v166; // xmm6_4
  float v167; // xmm0_4
  float v168; // xmm2_4
  void (__fastcall *v169)(__int64 *, __int64, int *, __m128i *); // rax
  int v170; // r8d
  int v171; // xmm6_4
  int v172; // eax
  int v173; // xmm0_4
  int v174; // eax
  __int64 v175; // rcx
  void (__fastcall ***v176)(_QWORD, _QWORD); // rax
  int v177; // eax
  __int128 v178; // xmm0
  float v179; // xmm0_4
  int v180; // xmm1_4
  int v181; // eax
  float v182; // xmm0_4
  int v183; // xmm1_4
  int v184; // xmm0_4
  int v185; // eax
  unsigned int v186; // [rsp+28h] [rbp-E0h]
  struct GpRuntime::GpRect *v187; // [rsp+28h] [rbp-E0h]
  __int32 v188; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v189; // [rsp+4Ch] [rbp-BCh] BYREF
  int v190; // [rsp+50h] [rbp-B8h]
  int v191; // [rsp+54h] [rbp-B4h]
  int v192[4]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v193[2]; // [rsp+68h] [rbp-A0h]
  __int64 v194; // [rsp+70h] [rbp-98h] BYREF
  __int128 v195; // [rsp+78h] [rbp-90h] BYREF
  int v196; // [rsp+88h] [rbp-80h] BYREF
  struct DpBitmap *v197; // [rsp+90h] [rbp-78h]
  int v198; // [rsp+98h] [rbp-70h]
  __m128i si128; // [rsp+A0h] [rbp-68h] BYREF
  void (__fastcall ***v200)(_QWORD, _QWORD); // [rsp+B0h] [rbp-58h]
  GpPath *v201; // [rsp+B8h] [rbp-50h]
  EpScanDIB *v202; // [rsp+C0h] [rbp-48h] BYREF
  EpScanDIB *v203; // [rsp+C8h] [rbp-40h]
  HDC v204; // [rsp+D0h] [rbp-38h] BYREF
  float v205; // [rsp+D8h] [rbp-30h]
  float v206; // [rsp+DCh] [rbp-2Ch]
  void **v207; // [rsp+E0h] [rbp-28h] BYREF
  int v208; // [rsp+E8h] [rbp-20h]
  int v209; // [rsp+ECh] [rbp-1Ch]
  unsigned __int64 v210; // [rsp+F0h] [rbp-18h]
  int v211; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v212; // [rsp+FCh] [rbp-Ch]
  unsigned __int64 v213; // [rsp+104h] [rbp-4h]
  float v214; // [rsp+110h] [rbp+8h]
  int v215; // [rsp+114h] [rbp+Ch]
  int v216; // [rsp+118h] [rbp+10h]
  float v217; // [rsp+11Ch] [rbp+14h]
  int v218; // [rsp+120h] [rbp+18h]
  int v219; // [rsp+124h] [rbp+1Ch]
  int v220; // [rsp+128h] [rbp+20h]
  struct tagPOINT v221[2]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v222[20]; // [rsp+140h] [rbp+38h]
  unsigned __int64 v223; // [rsp+154h] [rbp+4Ch]
  __m128i v224; // [rsp+168h] [rbp+60h] BYREF
  int v225; // [rsp+178h] [rbp+70h] BYREF
  int v226; // [rsp+17Ch] [rbp+74h]
  int v227; // [rsp+180h] [rbp+78h]
  int v228; // [rsp+184h] [rbp+7Ch]
  __m128i v229; // [rsp+188h] [rbp+80h] BYREF
  __int128 v230; // [rsp+198h] [rbp+90h] BYREF
  __int128 v231; // [rsp+1A8h] [rbp+A0h]
  int v232; // [rsp+1B8h] [rbp+B0h]
  int v233; // [rsp+1BCh] [rbp+B4h]
  int v234; // [rsp+1C0h] [rbp+B8h]
  void **v235; // [rsp+1C8h] [rbp+C0h] BYREF
  int v236; // [rsp+1D0h] [rbp+C8h]
  int v237; // [rsp+1D4h] [rbp+CCh]
  __int64 v238; // [rsp+1D8h] [rbp+D0h]
  int v239; // [rsp+1E0h] [rbp+D8h]
  __int64 v240; // [rsp+1E4h] [rbp+DCh]
  EpScanDIB *v241; // [rsp+1ECh] [rbp+E4h]
  float v242; // [rsp+1F8h] [rbp+F0h] BYREF
  float v243; // [rsp+1FCh] [rbp+F4h]
  float v244; // [rsp+200h] [rbp+F8h]
  float v245; // [rsp+204h] [rbp+FCh]
  void **v246; // [rsp+208h] [rbp+100h] BYREF
  int v247; // [rsp+210h] [rbp+108h]
  int v248; // [rsp+214h] [rbp+10Ch]
  __int128 v249; // [rsp+218h] [rbp+110h]
  int v250; // [rsp+228h] [rbp+120h]
  int v251; // [rsp+22Ch] [rbp+124h]
  int v252; // [rsp+230h] [rbp+128h]
  void **v253; // [rsp+238h] [rbp+130h] BYREF
  int v254; // [rsp+240h] [rbp+138h]
  int v255; // [rsp+244h] [rbp+13Ch]
  __int64 v256; // [rsp+248h] [rbp+140h]
  int v257; // [rsp+250h] [rbp+148h]
  __int64 v258; // [rsp+254h] [rbp+14Ch]
  EpScanDIB *v259; // [rsp+25Ch] [rbp+154h]
  __int128 v260; // [rsp+268h] [rbp+160h] BYREF
  void **v261; // [rsp+278h] [rbp+170h] BYREF
  int v262; // [rsp+280h] [rbp+178h]
  int v263; // [rsp+284h] [rbp+17Ch]
  __int128 v264; // [rsp+288h] [rbp+180h]
  int v265; // [rsp+298h] [rbp+190h]
  int v266; // [rsp+29Ch] [rbp+194h]
  int v267; // [rsp+2A0h] [rbp+198h]
  int v268; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v269; // [rsp+2ACh] [rbp+1A4h]
  int v270; // [rsp+2B4h] [rbp+1ACh]
  int v271; // [rsp+2B8h] [rbp+1B0h]
  int v272; // [rsp+2C8h] [rbp+1C0h]
  __int64 v273; // [rsp+310h] [rbp+208h]
  int v274; // [rsp+320h] [rbp+218h]
  _DWORD v275[308]; // [rsp+468h] [rbp+360h] BYREF
  float v276; // [rsp+938h] [rbp+830h] BYREF
  float v277; // [rsp+93Ch] [rbp+834h]
  float v278; // [rsp+940h] [rbp+838h]
  float v279; // [rsp+944h] [rbp+83Ch]
  float v280; // [rsp+948h] [rbp+840h]
  float v281; // [rsp+94Ch] [rbp+844h]
  float v282; // [rsp+950h] [rbp+848h]
  float v283; // [rsp+954h] [rbp+84Ch]

  v7 = a4[3];
  v9 = *a4;
  v201 = a5;
  v197 = a3;
  v11 = a4[1];
  v12 = (unsigned int)v9 + a4[2];
  v229 = 0;
  result = DpRegion::GetRectVisibility(a2 + 304, v9, v11, v12, (unsigned int)v11 + v7, &v229);
  if ( (_DWORD)result )
  {
    v14 = (GpTexture *)(a6 - 24);
    v15 = *(_QWORD *)(a6 - 24);
    v217 = FLOAT_1_0;
    BufferDIB = 0;
    v214 = FLOAT_1_0;
    v219 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64))(v15 + 112);
    v218 = 0;
    v216 = 0;
    v215 = 0;
    v220 = 0;
    v200 = 0;
    v18 = v17(a6 - 24, a2 + 144);
    v19 = _xmm;
    LODWORD(v20) = 0;
    v188 = v18;
    if ( !v18 )
      goto LABEL_116;
    v194 = 0;
    v21 = 0;
    v22 = *(_OWORD *)a4;
    v230 = 0;
    v195 = v22;
    v231 = 0;
    if ( v18 == 1 )
    {
      DWORD2(v195) = 1;
    }
    else
    {
      if ( v18 != 2 )
      {
        if ( v18 == 3 )
        {
          v23 = *(_DWORD *)(a6 + 44);
          v24 = *(_DWORD *)(a6 + 48);
          v25 = *(_DWORD *)(a6 + 24);
          v26 = *(_DWORD *)(a6 + 28);
          v27 = *(_DWORD *)(a6 + 32);
          v28 = *(_DWORD *)(a6 + 36);
          v29 = *(_DWORD *)(a6 + 40);
          v210 = __PAIR64__(v26, v25);
          v211 = v27;
          v212 = __PAIR64__(v29, v28);
          v193[0] = v23;
          v213 = __PAIR64__(v24, v23);
          v207 = &GpMatrix::`vftable';
          v209 = -1;
          v208 = 1952533809;
          v192[0] = v24;
          GpMatrix::MultiplyMatrix(
            (struct GpMatrix *)&v207,
            (const struct GpMatrix *)&v207,
            (const struct GpMatrix *)(a2 + 144));
          if ( *((_DWORD *)a1 + 10) == (_DWORD)v20
            && (*((_DWORD *)a1 + 41) != (_DWORD)v20 || *((_DWORD *)a1 + 19) != (_DWORD)v20)
            && (v213 & 0x800000000LL) == 0 )
          {
            v32 = _mm_loadu_si128((const __m128i *)(a6 + 60));
            v248 = v30;
            v263 = v30;
            v237 = v30;
            v209 = v30;
            v255 = v30;
            v246 = &GpMatrix::`vftable';
            v261 = &GpMatrix::`vftable';
            v235 = &GpMatrix::`vftable';
            v207 = &GpMatrix::`vftable';
            v253 = &GpMatrix::`vftable';
            v240 = 1065353216;
            v238 = 1065353216;
            v241 = v20;
            v239 = (int)v20;
            v236 = v31;
            v212 = 1065353216;
            v210 = 1065353216;
            v213 = (unsigned __int64)v20;
            v211 = (int)v20;
            v208 = v31;
            v258 = 1065353216;
            v256 = 1065353216;
            v259 = v20;
            v257 = (int)v20;
            v254 = v31;
            v203 = v20;
            v202 = v20;
            *(__m128i *)&v221[0].x = v32;
            `vector constructor iterator'(&v260, 8u, 2u, (void *(*)(void *))PointF::PointF);
            v260 = *(_OWORD *)(a6 + 248);
            `vector constructor iterator'(&si128, 8u, 2u, (void *(*)(void *))PointF::PointF);
            GpMatrix::Transform((GpMatrix *)(a2 + 144), (const struct PointF *)&v260, (struct PointF *)&si128, 2);
            v33 = IsClosePointF((const struct PointF *)&si128, (const struct PointF *)&si128.m128i_u64[1]);
            LODWORD(v20) = 0;
            if ( !v33 )
            {
              v34 = *(float *)si128.m128i_i32;
              v35 = si128.m128i_i32[1];
              v36 = sqrt(
                      (*(float *)&si128.m128i_i32[3] - *(float *)&si128.m128i_i32[1])
                    * (*(float *)&si128.m128i_i32[3] - *(float *)&si128.m128i_i32[1])
                    + (*(float *)&si128.m128i_i32[2] - *(float *)si128.m128i_i32)
                    * (*(float *)&si128.m128i_i32[2] - *(float *)si128.m128i_i32));
              HIDWORD(v204) = v35;
              v37 = v36;
              *(float *)&v204 = v37 + v34;
              o_atan2_0();
              GpMatrix::Translate(&v207, v38, v39, 1);
              GpMatrix::Rotate(&v207, v40, 1);
              GpMatrix::Translate(&v207, v41, v42, 1);
              GpMatrix::Translate(&v253, v43, v44, v45);
              GpMatrix::Rotate(&v253, v46, 1);
              GpMatrix::Translate(&v253, v47, v48, 1);
              v49 = *(_DWORD *)(a2 + 152);
              v50 = *(_DWORD *)(a2 + 180);
              v249 = *(_OWORD *)(a2 + 160);
              v247 = v49;
              v51 = *(_DWORD *)(a2 + 184);
              v250 = *(_DWORD *)(a2 + 176);
              v251 = v50;
              v252 = v51;
              GpMatrix::MultiplyMatrix(
                (struct GpMatrix *)&v246,
                (const struct GpMatrix *)&v246,
                (const struct GpMatrix *)&v207);
              v262 = v247;
              v264 = v249;
              v265 = v250;
              v266 = v251;
              v267 = v252;
              v52 = GpMatrix::Invert(&v261);
              LODWORD(v20) = 0;
              if ( !v52 )
              {
                v53 = v201;
                GpPath::Transform(v201, (const struct GpMatrix *)&v246);
                (*(void (__fastcall **)(GpPath *, EpScanDIB **, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v53 + 104LL))(
                  v53,
                  &v202,
                  0,
                  0,
                  0,
                  0);
                GpPath::Transform(v53, (const struct GpMatrix *)&v261);
                v19 = _xmm;
                *(_QWORD *)&v195 = 0;
                if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
                  v56 = (int)_mm_round_ss((__m128)(unsigned int)v203, (__m128)(unsigned int)v203, 10).m128_f32[0];
                else
                  v56 = -(int)floor(COERCE_FLOAT((unsigned int)v203 ^ _xmm));
                *((_QWORD *)&v195 + 1) = v56 | 0x100000000LL;
                GpMatrix::Translate(&v253, v54, v55, 0);
                GpMatrix::Translate(&v235, v57, v58, v59);
                v60 = (GpPathGradient *)(a6 - 24);
                v61 = GpLineGradient::ChangeLinePoints(a6 - 24, &si128, &v204, *(unsigned int *)(a6 + 104));
                LODWORD(v20) = 0;
                if ( !v61 )
                {
                  BufferDIB = GpBitmap::CreateBitmapAndFillWithBrush(
                                *(unsigned int *)(a2 + 48),
                                *(unsigned int *)(a2 + 52),
                                &v235,
                                &v195,
                                a6 - 24,
                                &v194);
                  v62 = v192[0];
                  *(_OWORD *)(a6 + 60) = *(_OWORD *)&v221[0].x;
                  *(_DWORD *)(a6 + 16) = 1952533809;
                  *(_DWORD *)(a6 + 44) = v193[0];
                  *(_DWORD *)(a6 + 24) = v25;
                  *(_DWORD *)(a6 + 28) = v26;
                  *(_DWORD *)(a6 + 32) = v27;
                  *(_DWORD *)(a6 + 36) = v28;
                  *(_DWORD *)(a6 + 40) = v29;
                  *(_DWORD *)(a6 + 48) = v62;
                  *(_OWORD *)(a6 + 248) = v260;
                  if ( !BufferDIB )
                  {
                    ContextHdc = DriverPrint::GetContextHdc((struct DpContext *)a2, v197);
                    v64 = v194;
                    v65 = ContextHdc;
                    if ( ContextHdc )
                    {
                      BufferDIB = GpBitmap::LockBits(v194, 0, 1, 2498570, &v230);
                      if ( !BufferDIB )
                      {
                        v66 = *a1;
                        v188 = 0;
                        v189 = 0;
                        (*(void (__fastcall **)(__int64 *, HDC, __int64, unsigned int *, __int32 *, unsigned int *, _DWORD))(v66 + 40))(
                          a1,
                          v65,
                          a2,
                          a4,
                          &v188,
                          &v189,
                          0);
                        if ( *((_DWORD *)a1 + 41)
                          && *((_DWORD *)v53 + 26) == 4
                          && (unsigned int)DpPath::IsRectangular(v53) )
                        {
                          (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v65, a2, v53);
                          BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                        (DriverPrint *)a1,
                                        v65,
                                        (__int64)&v230,
                                        15728673,
                                        0,
                                        (GpMatrix *)&v253,
                                        *((float *)&v203 + 1));
                          (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v65);
                        }
                        else
                        {
                          BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                        (DriverPrint *)a1,
                                        v65,
                                        (__int64)&v230,
                                        5898313,
                                        1,
                                        (GpMatrix *)&v253,
                                        *((float *)&v203 + 1));
                          if ( !BufferDIB )
                          {
                            ConvertPathToGdi::ConvertPathToGdi(
                              (ConvertPathToGdi *)&v268,
                              v53,
                              (struct GpMatrix *)(a2 + 144),
                              2u,
                              0);
                            if ( v268 == 1198932785 )
                            {
                              if ( *((_DWORD *)a1 + 41) )
                                StockObject = (HBRUSH)GetStockObject(BufferDIB + 4);
                              else
                                StockObject = DriverPrint::GetAlphaMaskBrush(
                                                (DriverPrint *)a1,
                                                *((unsigned __int8 *)a1 + 176),
                                                1);
                              v68 = StockObject;
                              v69 = SetROP2(v65, 9);
                              v70 = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v268, v65, v68);
                              BufferDIB = v70 == 0;
                              LODWORD(v68) = v70;
                              SetROP2(v65, v69);
                              if ( (_DWORD)v68 )
                                BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                              (DriverPrint *)a1,
                                              v65,
                                              (__int64)&v230,
                                              5898313,
                                              1,
                                              (GpMatrix *)&v253,
                                              *((float *)&v203 + 1));
                              v64 = v194;
                            }
                            ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v268);
                          }
                        }
                        (*(void (__fastcall **)(__int64 *, HDC, _QWORD, _QWORD))(*a1 + 48))(
                          a1,
                          v65,
                          (unsigned int)v188,
                          v189);
                        GpBitmap::UnlockBits(v64, &v230);
                      }
                      DpContext::ReleaseHdc((DpContext *)a2, v65, 0);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 56LL))(v64);
                  }
                  return BufferDIB;
                }
                goto LABEL_39;
              }
              v19 = _xmm;
            }
          }
        }
        else if ( (unsigned int)(v18 - 4) >= 2 )
        {
          goto LABEL_69;
        }
        v60 = (GpPathGradient *)(a6 - 24);
LABEL_39:
        IsRectangular = (int)v20;
        LOBYTE(IsRectangular) = *(_DWORD *)a6 == 4;
        if ( *((_DWORD *)a1 + 41) != (_DWORD)v20
          || *((_DWORD *)a1 + 19) == (_DWORD)v20
          || (v21 = 1, *((_DWORD *)a1 + 10) != (_DWORD)v20) )
        {
          v21 = (int)v20;
        }
        if ( *(_DWORD *)a6 == 3 )
          IsRectangular = GpPathGradient::IsRectangular(v60);
        v72 = a4[2];
        if ( IsRectangular )
        {
          v73 = 256;
          v74 = 256;
          if ( v72 < 256 )
            v74 = a4[2];
          v75 = (int)a4[3] < 256;
          DWORD2(v195) = v74;
          if ( v75 )
            v73 = a4[3];
          HIDWORD(v195) = v73;
        }
        else
        {
          v76 = ((int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 1)
              + ((unsigned int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 31)
              + 256;
          v77 = v76;
          if ( v76 >= v72 )
            v77 = a4[2];
          if ( v77 >= 1024 )
          {
            DWORD2(v195) = 1024;
          }
          else
          {
            if ( v76 < v72 )
              v72 = ((int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 1)
                  + ((unsigned int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 31)
                  + 256;
            DWORD2(v195) = v72;
          }
          v78 = a4[3];
          v79 = ((int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 1)
              + ((unsigned int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 31)
              + 256;
          v80 = v79;
          if ( v79 >= v78 )
            v80 = a4[3];
          if ( v80 >= 1024 )
          {
            HIDWORD(v195) = 1024;
          }
          else
          {
            if ( v79 < v78 )
              v78 = ((int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 1)
                  + ((unsigned int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 31)
                  + 256;
            HIDWORD(v195) = v78;
          }
        }
        goto LABEL_69;
      }
      HIDWORD(v195) = 1;
    }
    LOBYTE(v21) = *((_DWORD *)a1 + 10) == 0;
LABEL_69:
    if ( *((_DWORD *)a1 + 41) != (_DWORD)v20 || *((_DWORD *)a1 + 10) == 1 || v21 )
    {
      v81 = DriverPrint::GetContextHdc((struct DpContext *)a2, v197);
      LODWORD(v20) = 0;
      v82 = v81;
      if ( v81 )
      {
        *(_QWORD *)&v195 = 0;
        v204 = 0;
        v207 = &GpMatrix::`vftable';
        v209 = -1;
        v212 = 1065353216;
        v210 = 1065353216;
        v213 = 0;
        v211 = 0;
        v205 = (float)SDWORD2(v195);
        v83 = _mm_cvtsi32_si128(*a4);
        v206 = (float)SHIDWORD(v195);
        v84 = _mm_cvtsi32_si128(a4[1]);
        v208 = 1952533809;
        si128.m128i_i32[0] = _mm_cvtepi32_ps(v83).m128_u32[0];
        v85 = _mm_cvtsi32_si128(a4[2]);
        si128.m128i_i32[1] = _mm_cvtepi32_ps(v84).m128_u32[0];
        *(float *)v84.m128i_i32 = (float)(int)a4[3];
        si128.m128i_i32[2] = _mm_cvtepi32_ps(v85).m128_u32[0];
        si128.m128i_i32[3] = v84.m128i_i32[0];
        GpMatrix::InferAffineMatrix(&v207, &v204, &si128);
        GpMatrix::MultiplyMatrix(
          (struct GpMatrix *)&v207,
          (const struct GpMatrix *)(a2 + 144),
          (const struct GpMatrix *)&v207);
        v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a6 - 24) + 64LL))(a6 - 24);
        v200 = (void (__fastcall ***)(_QWORD, _QWORD))v86;
        v87 = (_DWORD *)v86;
        if ( v86 )
        {
          if ( !*((_DWORD *)a1 + 41) && *((_DWORD *)a1 + 10) == 1 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 168LL))(v86);
            v87 = v200;
            *((_DWORD *)a1 + 41) = 1;
          }
          if ( (unsigned int)(v188 - 4) <= 1 )
          {
            v87[110] = 1065772646;
            *((_QWORD *)v87 + 2) = 0;
          }
          BufferDIB = GpBitmap::CreateBitmapAndFillWithBrush(
                        *(unsigned int *)(a2 + 48),
                        *(unsigned int *)(a2 + 52),
                        &v207,
                        &v195,
                        v87,
                        &v194);
          (**v200)(v200, 1);
          if ( BufferDIB )
          {
            v200 = 0;
          }
          else
          {
            if ( v194 )
            {
              v88 = 6;
              v89 = 6;
              if ( *((_DWORD *)a1 + 10) != 1 )
                v89 = 2;
              v193[0] = v89;
              if ( (unsigned int)GpBitmap::LockBits(v194, 0, 1, 2498570, &v230) )
                goto LABEL_110;
              BufferDIB = 0;
              v90 = *(void (__fastcall **)(__int64 *, HDC, __int64, unsigned int *, __int32 *, unsigned int *, _DWORD))(*a1 + 40);
              v188 = 0;
              v189 = 0;
              v90(a1, v82, a2, a4, &v188, &v189, 0);
              if ( !v21 || HIDWORD(v195) != 1 && DWORD2(v195) != 1 )
              {
                (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v82, a2, v201);
                DpBitmap::DpBitmap((DpBitmap *)&v268, 0);
                GpBitmap::InitializeSurfaceForGdipBitmap(v194, &v268, (unsigned int)v230, DWORD1(v230));
                v273 = v231;
                v274 = DWORD2(v230);
                v269 = v230;
                v95 = *((_DWORD *)a1 + 10) == 1;
                v270 = 2498570;
                v272 = 3;
                v271 = 3 * DWORD1(v230) * v230;
                if ( !v95 )
                  v88 = 2;
                if ( v21 )
                  v96 = (*((unsigned __int8 *)a1 + 72) + (unsigned int)*((unsigned __int8 *)a1 + 73)) >> 1;
                else
                  v96 = -1;
                ConvertBitmapToGdi::ConvertBitmapToGdi(
                  (ConvertBitmapToGdi *)v275,
                  v82,
                  (struct DpBitmap *)&v268,
                  (const struct GpRuntime::GpRect *)&v195,
                  v88,
                  v96,
                  1);
                if ( v275[0] == 1198932785 )
                {
                  v97 = a4[1];
                  v98 = *a4 + a4[2];
                  v221[0].x = *a4;
                  v221[1].x = v98;
                  v99 = a4[3];
                  v221[0].y = v97;
                  *(_DWORD *)&v222[4] = v97 + v99;
                  v221[1].y = v97;
                  *(_DWORD *)v222 = v221[0].x;
                  LOBYTE(BufferDIB) = ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v275, v82, v221, 0, v186) == 0;
                }
                else
                {
                  BufferDIB = 1;
                }
                (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v82);
                ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v275);
                DpBitmap::~DpBitmap((DpBitmap *)&v268);
                goto LABEL_109;
              }
              v91 = v201;
              if ( *((_DWORD *)a1 + 41) )
              {
                if ( *((_DWORD *)v201 + 26) != 4 || !(unsigned int)DpPath::IsRectangular(v201) )
                {
LABEL_90:
                  BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v230, &v195, a4, 6684742, 1);
                  if ( !BufferDIB )
                  {
                    ConvertPathToGdi::ConvertPathToGdi(
                      (ConvertPathToGdi *)&v268,
                      v91,
                      (struct GpMatrix *)(a2 + 144),
                      v193[0],
                      0);
                    if ( v268 == 1198932785 )
                    {
                      if ( *((_DWORD *)a1 + 41) == BufferDIB )
                        AlphaMaskBrush = DriverPrint::GetAlphaMaskBrush(
                                           (DriverPrint *)a1,
                                           *((unsigned __int8 *)a1 + 176),
                                           1);
                      else
                        AlphaMaskBrush = (HBRUSH)GetStockObject(BufferDIB + 4);
                      v93 = AlphaMaskBrush;
                      v94 = SetROP2(v82, 9);
                      LODWORD(v93) = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v268, v82, v93);
                      BufferDIB = (_DWORD)v93 == 0;
                      SetROP2(v82, v94);
                      if ( (_DWORD)v93 )
                        BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v230, &v195, a4, 6684742, 1);
                    }
                    ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v268);
                  }
                  goto LABEL_109;
                }
              }
              else if ( *((_DWORD *)a1 + 19) )
              {
                goto LABEL_90;
              }
              (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v82, a2, v91);
              BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v230, &v195, a4, 13369376, 0);
              (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v82);
LABEL_109:
              (*(void (__fastcall **)(__int64 *, HDC, _QWORD, _QWORD))(*a1 + 48))(a1, v82, (unsigned int)v188, v189);
              GpBitmap::UnlockBits(v194, &v230);
LABEL_110:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v194 + 56LL))(v194);
              DpContext::ReleaseHdc((DpContext *)a2, v82, 0);
              return BufferDIB;
            }
            v200 = 0;
          }
        }
        else
        {
          BufferDIB = 3;
        }
        DpContext::ReleaseHdc((DpContext *)a2, v82, 0);
        LODWORD(v20) = 0;
      }
    }
    v14 = (GpTexture *)(a6 - 24);
LABEL_116:
    v100 = *((_DWORD *)a1 + 10);
    v189 = (unsigned int)v20;
    if ( v100 )
    {
      if ( v100 != 1 )
        return 6;
      v101 = *((_DWORD *)a1 + 40);
      v102 = (int)v20;
      LOBYTE(v102) = v101 == 0;
      v198 = v102;
      if ( v101 )
      {
        v103 = *((_DWORD *)a1 + 41) != 0 ? 2 : 66;
        if ( *((_DWORD *)a1 + 84) != 1 || (v95 = *((_DWORD *)a1 + 85) == 1, v190 = 1952533809, !v95) )
        {
          v104 = *(_DWORD *)(a2 + 152);
          v214 = *(float *)(a2 + 160);
          v215 = *(_DWORD *)(a2 + 164);
          v216 = *(_DWORD *)(a2 + 168);
          v217 = *(float *)(a2 + 172);
          v218 = *(_DWORD *)(a2 + 176);
          v105 = *(_DWORD *)(a2 + 180);
          v190 = v104;
          v106 = *(_DWORD *)(a2 + 184);
          v219 = v105;
          v189 = 1;
          v220 = v106;
        }
LABEL_141:
        v95 = *(_DWORD *)a6 == 2;
        v107 = v197;
        v108 = *((_DWORD *)a1 + 12);
        v193[0] = v108;
        v202 = (EpScanDIB *)*((_QWORD *)v197 + 16);
        LODWORD(v194) = *((_DWORD *)a1 + 11);
        if ( v95 )
        {
          Bitmap = GpTexture::GetBitmap(v14);
          if ( Bitmap )
          {
            v110 = *(_QWORD *)Bitmap;
            v204 = 0;
            (*(void (__fastcall **)(struct GpBitmap *, HDC *))(v110 + 368))(Bitmap, &v204);
            v95 = (*(_BYTE *)(a6 + 360) & 1) == 0;
            v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v221[0] = (struct tagPOINT)&GpMatrix::`vftable';
            v221[1].y = -1;
            *(_QWORD *)&v222[12] = 1065353216;
            *(_QWORD *)v222 = 1065353216;
            v223 = 0;
            *(_DWORD *)&v222[8] = 0;
            v221[1].x = 1952533809;
            if ( v95 )
            {
              v112 = *(_DWORD *)(a2 + 152);
              v113 = *(_DWORD *)(a2 + 180);
              *(_OWORD *)v222 = *(_OWORD *)(a2 + 160);
              v221[1].x = v112;
              v114 = *(_DWORD *)(a2 + 184);
              *(_DWORD *)&v222[16] = *(_DWORD *)(a2 + 176);
              v223 = __PAIR64__(v114, v113);
            }
            else
            {
              if ( !Feature_GdiPlusOptimizations_Misc_IsEnabled )
                floor((float)(*((float *)v197 + 6) / 100.0));
              if ( !v111 )
                floor((float)(*((float *)v197 + 5) / 100.0));
              GpMatrix::Scale(v221);
            }
            GpMatrix::MultiplyMatrix(
              (struct GpMatrix *)v221,
              (const struct GpMatrix *)(a6 + 8),
              (const struct GpMatrix *)v221);
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            GpMatrix::VectorTransform((GpMatrix *)v221, (struct PointF *)&si128, 2);
            v115 = o_sqrtf_0(
                     (float)(*(float *)&si128.m128i_i32[1] * *(float *)&si128.m128i_i32[1])
                   + (float)(*(float *)si128.m128i_i32 * *(float *)si128.m128i_i32))
                 + 0.5;
            if ( v111 )
            {
              v116 = 0;
              v116.m128_f32[0] = v115;
              v117 = (int)_mm_round_ss(v116, v116, 9).m128_f32[0];
            }
            else
            {
              v117 = (int)floor(v115);
            }
            v118 = *(float *)&si128.m128i_i32[2];
            v119 = *(float *)&si128.m128i_i32[3];
            *((_DWORD *)a1 + 11) = v117;
            v120 = o_sqrtf_0((float)(v119 * v119) + (float)(v118 * v118)) + 0.5;
            if ( v111 )
            {
              v121 = 0;
              v121.m128_f32[0] = v120;
              v122 = (int)_mm_round_ss(v121, v121, 9).m128_f32[0];
LABEL_181:
              *((_DWORD *)a1 + 12) = v122;
LABEL_188:
              v136 = *((_DWORD *)a1 + 11);
              if ( v136 < 1 )
              {
                *((_DWORD *)a1 + 11) = 1;
                v136 = 1;
              }
              if ( v122 < 1 )
              {
                *((_DWORD *)a1 + 12) = 1;
                v122 = 1;
              }
              if ( v136 == 1 && v122 == 1 )
              {
                v224 = v229;
                v137 = _mm_cvtsi128_si32(_mm_srli_si128(v229, 12));
                v188 = _mm_cvtsi128_si32(_mm_srli_si128(v229, 4));
                v138 = _mm_cvtsi128_si32(_mm_srli_si128(v229, 8));
                v139 = _mm_cvtsi128_si32(v229);
              }
              else
              {
                v192[0] = v136 * (v229.m128i_i32[0] / v136);
                v224.m128i_i32[0] = v192[0];
                v188 = v122 * (v229.m128i_i32[1] / v122);
                v224.m128i_i32[1] = v188;
                v138 = v229.m128i_i32[0] % v136
                     + v229.m128i_i32[2]
                     + v136
                     - (v229.m128i_i32[0] % v136 + v229.m128i_i32[2]) % v136;
                v224.m128i_i32[2] = v138;
                v137 = v229.m128i_i32[1] % v122
                     + v229.m128i_i32[3]
                     + v122
                     - (v229.m128i_i32[1] % v122 + v229.m128i_i32[3]) % v122;
                v139 = v192[0];
                v224.m128i_i32[3] = v137;
              }
              v191 = v137;
              v196 = v138;
              v225 = v139 / v136;
              v226 = v188 / v122;
              v227 = v138 / v136;
              v228 = v137 / v122;
              if ( v189 )
              {
                v140 = (float)*((int *)a1 + 84);
                v141 = (__m128)COERCE_UNSIGNED_INT((float)v139);
                v141.m128_f32[0] = v141.m128_f32[0] / v140;
                if ( v111 )
                  v142 = (int)_mm_round_ss(v141, v141, 10).m128_f32[0];
                else
                  v142 = -(int)floor(COERCE_FLOAT(v141.m128_i32[0] ^ v19));
                v143 = _mm_cvtsi32_si128(*((_DWORD *)a1 + 85));
                v224.m128i_i32[0] = v142;
                v144 = _mm_cvtepi32_ps(v143).m128_f32[0];
                v145 = (__m128)COERCE_UNSIGNED_INT((float)v188);
                v145.m128_f32[0] = v145.m128_f32[0] / v144;
                if ( v111 )
                  v146 = (int)_mm_round_ss(v145, v145, 10).m128_f32[0];
                else
                  v146 = -(int)floor(COERCE_FLOAT(v145.m128_i32[0] ^ v19));
                v224.m128i_i32[1] = v146;
                v147 = (__m128)COERCE_UNSIGNED_INT((float)v196);
                v147.m128_f32[0] = v147.m128_f32[0] / v140;
                if ( v111 )
                  v148 = (int)_mm_round_ss(v147, v147, 10).m128_f32[0];
                else
                  v148 = -(int)floor(COERCE_FLOAT(v147.m128_i32[0] ^ v19));
                v224.m128i_i32[2] = v148;
                v149 = (__m128)COERCE_UNSIGNED_INT((float)v191);
                v149.m128_f32[0] = v149.m128_f32[0] / v144;
                if ( v111 )
                  v150 = (int)_mm_round_ss(v149, v149, 10).m128_f32[0];
                else
                  v150 = -(int)floor(COERCE_FLOAT(v149.m128_i32[0] ^ v19));
                v224.m128i_i32[3] = v150;
                v151 = (GpMatrix *)(a2 + 144);
                GpMatrix::Scale(a2 + 144);
              }
              else
              {
                v151 = (GpMatrix *)(a2 + 144);
              }
              v152 = *(_DWORD *)(a2 + 160);
              v153 = *(_DWORD *)(a2 + 164);
              v154 = *(_DWORD *)(a2 + 168);
              v155 = *(_DWORD *)(a2 + 172);
              v156 = *(_DWORD *)(a2 + 176);
              v157 = *(_DWORD *)(a2 + 180);
              v221[0].x = v152;
              v221[0].y = v153;
              v221[1].x = v154;
              v221[1].y = v155;
              GpMatrix::Scale(v151);
              v158 = *(_DWORD *)(a2 + 160);
              v159 = *(_DWORD *)(a2 + 164);
              v160 = *(_DWORD *)(a2 + 168);
              v191 = *(_DWORD *)(a2 + 172);
              v232 = *(_DWORD *)(a2 + 176);
              v234 = *(_DWORD *)(a2 + 180);
              *(_DWORD *)(a2 + 288) = 0;
              `vector constructor iterator'(&v276, 8u, 4u, (void *(*)(void *))PointF::PointF);
              v235 = &GpMatrix::`vftable';
              v237 = -1;
              v240 = 1065353216;
              v238 = 1065353216;
              v241 = 0;
              v239 = 0;
              v277 = (float)v226;
              v279 = (float)v226;
              v236 = 1952533809;
              v281 = (float)(v226 + v228);
              v283 = v281;
              v276 = (float)v225;
              v278 = (float)(v227 + v225);
              v280 = (float)v225;
              v282 = v278;
              DpContext::GetDeviceToWorld(a2, &v235);
              GpMatrix::Transform((GpMatrix *)&v235, (struct PointF *)&v276, 4);
              v161 = fminf(v276, v278);
              v162 = fminf(v280, v282);
              if ( v162 <= v161 )
              {
                v242 = v162;
                v161 = v162;
              }
              else
              {
                v242 = v161;
              }
              v163 = fminf(v277, v279);
              v164 = fminf(v281, v283);
              if ( v164 <= v163 )
              {
                v243 = v164;
                v163 = v164;
              }
              else
              {
                v243 = v163;
              }
              v165 = fmaxf(v276, v278);
              v166 = fmaxf(v280, v282);
              if ( v165 <= v166 )
                v165 = v166;
              v167 = fmaxf(v277, v279);
              v168 = fmaxf(v281, v283);
              v244 = v165 - v161;
              if ( v167 <= v168 )
                v167 = v168;
              v169 = *(void (__fastcall **)(__int64 *, __int64, int *, __m128i *))(*a1 + 160);
              v245 = v167 - v163;
              v169(a1, a2, &v225, &v224);
              v204 = DriverPrint::GetContextHdc((struct DpContext *)a2, v197);
              if ( v204 )
              {
                BufferDIB = EpScanDIB::CreateBufferDIB(
                              v202,
                              a1 + 26,
                              a1 + 28,
                              v103,
                              *((_DWORD *)a1 + 11),
                              *((_DWORD *)a1 + 12));
                if ( !BufferDIB )
                {
                  v192[0] = 0;
                  v196 = 0;
                  if ( v198 )
                    DriverPrint::SetupClipping(
                      (DriverPrint *)a1,
                      v204,
                      (struct DpContext *)a2,
                      (const struct GpRuntime::GpRect *)a4,
                      v192,
                      &v196,
                      0);
                  v75 = *((_DWORD *)a1 + 46) <= 0;
                  *((_DWORD *)a1 + 45) = 0;
                  if ( !v75 )
                  {
                    v171 = v191;
                    v172 = v103 & 0x1D;
                    v233 = v172;
                    do
                    {
                      if ( v172 )
                      {
                        DpClipRegion::DisableComplexClipping(
                          (DpClipRegion *)(a2 + 296),
                          (struct GpRuntime::GpRect *)(a1 + 26),
                          v170);
                        v173 = v232;
                        *(_DWORD *)(a2 + 288) = 0;
                        *(_DWORD *)(a2 + 176) = v173;
                        *(_DWORD *)(a2 + 180) = v234;
                        *(_DWORD *)(a2 + 160) = v158;
                        *(_DWORD *)(a2 + 164) = v159;
                        *(_DWORD *)(a2 + 168) = v160;
                        *(_DWORD *)(a2 + 172) = v171;
                        v174 = GpMatrix::ComputeComplexity((GpMatrix *)(a2 + 144));
                        *(_DWORD *)(v175 + 40) = v174;
                        EpScanDIB::SetRenderMode(v202, 0, (struct GpRuntime::GpRect *)(a1 + 26));
                        v95 = *(_DWORD *)a6 == 2;
                        v191 = 0;
                        if ( v95 && *((_DWORD *)a1 + 11) != 1 )
                        {
                          v191 = *(_DWORD *)(a6 + 364);
                          *(_DWORD *)(a6 + 364) = 1;
                        }
                        if ( v200 )
                          v176 = v200 + 3;
                        else
                          v176 = (void (__fastcall ***)(_QWORD, _QWORD))a6;
                        LODWORD(v187) = 1;
                        BufferDIB = DpDriver::FillRects(a1, a2, v197, &v225, v187, &v242, v176);
                        if ( *(_DWORD *)a6 == 2 && *((_DWORD *)a1 + 11) != 1 )
                          *(_DWORD *)(a6 + 364) = v191;
                        *(_DWORD *)(a2 + 392) = 0;
                        DpRegion::Set(a2 + 304, a2 + 352, 1);
                      }
                      *(_DWORD *)(a2 + 288) = 0;
                      *((_DWORD *)v151 + 4) = v152;
                      *((_DWORD *)v151 + 5) = v153;
                      *((_DWORD *)v151 + 6) = v154;
                      *((_DWORD *)v151 + 7) = v155;
                      *((_DWORD *)v151 + 8) = v156;
                      *((_DWORD *)v151 + 9) = v157;
                      *((_DWORD *)v151 + 10) = GpMatrix::ComputeComplexity(v151);
                      if ( BufferDIB )
                        break;
                      if ( (v103 & 0x62) != 0 )
                      {
                        if ( *(_DWORD *)a6 != 1 || (v177 = *((_DWORD *)a1 + 11), v177 == 1) )
                        {
                          v95 = *(_DWORD *)a6 == 2;
                          v188 = 0;
                          if ( v95 && *((_DWORD *)a1 + 11) != 1 )
                          {
                            v188 = *(_DWORD *)(a6 + 364);
                            *(_DWORD *)(a6 + 364) = 1;
                          }
                        }
                        else
                        {
                          *(_DWORD *)(a6 + 344) = v177;
                          v188 = 0;
                        }
                        DpClipRegion::SetBandBounds(
                          (DpClipRegion *)(a2 + 296),
                          (struct GpRuntime::GpRect *)(a1 + 28),
                          1);
                        EpScanDIB::SetRenderMode(v202, 1, (struct GpRuntime::GpRect *)(a1 + 28));
                        BufferDIB = DpDriver::FillPath(a1, a2, v197, a4, v201, a6);
                        if ( *(_DWORD *)a6 == 2 )
                        {
                          if ( *((_DWORD *)a1 + 11) != 1 )
                            *(_DWORD *)(a6 + 364) = v188;
                        }
                        else if ( *(_DWORD *)a6 == 1 && *((_DWORD *)a1 + 11) != 1 )
                        {
                          *(_DWORD *)(a6 + 344) = 1;
                        }
                        if ( BufferDIB )
                          break;
                      }
                      BufferDIB = (*(__int64 (__fastcall **)(__int64 *, HDC, __int64, struct DpBitmap *, __int64 *, __int64 *, GpPath *))(*a1 + 256))(
                                    a1,
                                    v204,
                                    a2,
                                    v197,
                                    a1 + 26,
                                    a1 + 28,
                                    v201);
                      if ( BufferDIB )
                        break;
                      *((_DWORD *)a1 + 53) += *((_DWORD *)a1 + 48);
                      *((_DWORD *)a1 + 57) += *((_DWORD *)a1 + 47);
                      ++*((_DWORD *)a1 + 45);
                      v172 = v233;
                    }
                    while ( *((_DWORD *)a1 + 45) < *((_DWORD *)a1 + 46) );
                  }
                  if ( v198 )
                    DriverPrint::RestoreClipping((DriverPrint *)a1, v204, v192[0], v196);
                  EpScanDIB::DestroyBufferDIB(v202);
                }
                DpContext::ReleaseHdc((DpContext *)a2, v204, 0);
              }
              else
              {
                v178 = *(_OWORD *)&v221[0].x;
                *(_DWORD *)(a2 + 288) = 0;
                *((_DWORD *)v151 + 8) = v156;
                *((_OWORD *)v151 + 1) = v178;
                *((_DWORD *)v151 + 9) = v157;
                *((_DWORD *)v151 + 10) = GpMatrix::ComputeComplexity(v151);
              }
              (*(void (__fastcall **)(__int64 *, __int64))(*a1 + 168))(a1, a2);
              if ( v189 )
              {
                v179 = v214;
                v180 = v215;
                v181 = v190;
                *(_DWORD *)(a2 + 288) = 0;
                *(float *)(a2 + 160) = v179;
                v182 = v217;
                *(_DWORD *)(a2 + 164) = v180;
                *(_DWORD *)(a2 + 168) = v216;
                v183 = v218;
                *(float *)(a2 + 172) = v182;
                v184 = v219;
                *(_DWORD *)(a2 + 152) = v181;
                v185 = v220;
                *(_DWORD *)(a2 + 176) = v183;
                *(_DWORD *)(a2 + 180) = v184;
                *(_DWORD *)(a2 + 184) = v185;
              }
              if ( v200 )
                (**v200)(v200, 1);
              *((_DWORD *)a1 + 11) = v194;
              *((_DWORD *)a1 + 12) = v193[0];
              return BufferDIB;
            }
            v123 = v120;
            goto LABEL_180;
          }
          goto LABEL_186;
        }
        if ( *(_DWORD *)a6 == 1 )
        {
          v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
          v124 = (__m128)*((unsigned int *)v197 + 5);
          v124.m128_f32[0] = v124.m128_f32[0] / 100.0;
          if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
          {
            v125 = (int)_mm_round_ss(v124, v124, 9).m128_f32[0];
          }
          else
          {
            v126 = floor(v124.m128_f32[0]);
            v107 = v197;
            v125 = (int)v126;
          }
          *((_DWORD *)a1 + 11) = v125;
          v127 = (__m128)*((unsigned int *)v107 + 6);
          v127.m128_f32[0] = v127.m128_f32[0] / 100.0;
          goto LABEL_177;
        }
        if ( v188 )
        {
          if ( v188 == 1 )
          {
            v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v133 = (__m128)*((unsigned int *)v197 + 5);
            if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
            {
              v134 = (int)_mm_round_ss(v133, v133, 9).m128_f32[0];
            }
            else
            {
              v135 = floor(v133.m128_f32[0]);
              v108 = v193[0];
              v134 = (int)v135;
            }
            *((_DWORD *)a1 + 11) = v134;
            goto LABEL_187;
          }
          if ( v188 == 2 )
          {
            v127 = (__m128)*((unsigned int *)v197 + 6);
            v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
LABEL_177:
            if ( v111 )
            {
              v122 = (int)_mm_round_ss(v127, v127, 9).m128_f32[0];
              goto LABEL_181;
            }
            v123 = v127.m128_f32[0];
LABEL_180:
            v122 = (int)floor(v123);
            goto LABEL_181;
          }
          if ( v188 == 3 || (unsigned int)(v188 - 4) <= 1 )
          {
            v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v128 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[2]);
            v128.m128_f32[0] = v128.m128_f32[0] * 0.00390625;
            if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
              v129 = (int)_mm_round_ss(v128, v128, 10).m128_f32[0];
            else
              v129 = -(int)floor(COERCE_FLOAT(v128.m128_i32[0] ^ v19));
            *((_DWORD *)a1 + 11) = v129;
            v130 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[3]);
            v130.m128_f32[0] = v130.m128_f32[0] * 0.00390625;
            if ( v111 )
              v131 = (int)_mm_round_ss(v130, v130, 10).m128_f32[0];
            else
              v131 = -(int)floor(COERCE_FLOAT(v130.m128_i32[0] ^ v19));
            v95 = v188 == 3;
            *((_DWORD *)a1 + 12) = v131;
            if ( !v95 )
            {
              v132 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a6 - 24) + 64LL))(a6 - 24);
              v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
              v200 = (void (__fastcall ***)(_QWORD, _QWORD))v132;
              if ( v132 )
              {
                *(_DWORD *)(v132 + 440) = 1065772646;
                *(_QWORD *)(v132 + 16) = 0;
              }
            }
            v122 = *((_DWORD *)a1 + 12);
            goto LABEL_188;
          }
        }
LABEL_186:
        v111 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
LABEL_187:
        v122 = v108;
        goto LABEL_188;
      }
      if ( *((_DWORD *)a1 + 42) == (_DWORD)v20 )
      {
        v190 = 1952533809;
        if ( *((_DWORD *)a1 + 41) == (_DWORD)v20 )
          v103 = 49;
        else
          v103 = 1;
        goto LABEL_141;
      }
      v103 = 5;
LABEL_140:
      v190 = 1952533809;
      goto LABEL_141;
    }
    if ( *((_DWORD *)a1 + 40) == (_DWORD)v20 )
    {
      if ( *((_DWORD *)a1 + 42) == (_DWORD)v20 )
      {
        if ( *((_DWORD *)a1 + 41) == (_DWORD)v20 )
        {
          v103 = 67;
LABEL_139:
          v198 = (int)v20;
          goto LABEL_140;
        }
        v103 = 1;
LABEL_137:
        v198 = 1;
        goto LABEL_140;
      }
      v103 = 5;
    }
    else
    {
      v103 = *((_DWORD *)a1 + 41) != 0 ? 2 : 66;
    }
    if ( *((_DWORD *)a1 + 41) == (_DWORD)v20 && *((_DWORD *)a1 + 42) == (_DWORD)v20 )
      goto LABEL_139;
    goto LABEL_137;
  }
  return result;
}

```

## disassembly

```asm
0x1800fafbc  mov     rax, rsp
0x1800fafbf  push    rbp
0x1800fafc0  push    rbx
0x1800fafc1  push    rsi
0x1800fafc2  push    rdi
0x1800fafc3  push    r12
0x1800fafc5  push    r13
0x1800fafc7  push    r14
0x1800fafc9  push    r15
0x1800fafcb  lea     rbp, [rax-948h]
0x1800fafd2  sub     rsp, 0A08h
0x1800fafd9  movaps  xmmword ptr [rax-58h], xmm6
0x1800fafdd  movaps  xmmword ptr [rax-68h], xmm7
0x1800fafe1  movaps  xmmword ptr [rax-78h], xmm8
0x1800fafe6  movaps  xmmword ptr [rax-88h], xmm9
0x1800fafee  movaps  xmmword ptr [rax-98h], xmm10
0x1800faff6  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800faffe  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800fb006  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800fb00e  movaps  xmmword ptr [rax-0D8h], xmm14
0x1800fb016  movaps  xmmword ptr [rax-0E8h], xmm15
0x1800fb01e  mov     rax, cs:__security_cookie
0x1800fb025  xor     rax, rsp
0x1800fb028  mov     [rbp+940h+var_F0], rax
0x1800fb02f  mov     rax, [rbp+940h+arg_20]
0x1800fb036  mov     rsi, rcx
0x1800fb039  mov     ecx, [r9+0Ch]
0x1800fb03d  mov     r14, rdx
0x1800fb040  mov     edx, [r9]
0x1800fb043  mov     r13, r9
0x1800fb046  mov     rbx, [rbp+940h+arg_28]
0x1800fb04d  xorps   xmm0, xmm0
0x1800fb050  mov     [rbp+940h+var_990], rax
0x1800fb054  lea     rax, [rbp+940h+var_8C0]
0x1800fb05b  mov     [rbp+940h+var_9B8], r8
0x1800fb05f  mov     r8d, [r9+4]
0x1800fb063  add     ecx, r8d
0x1800fb066  mov     r9d, [r9+8]
0x1800fb06a  mov     [rsp+0A40h+var_A18], rax
0x1800fb06f  add     r9d, edx
0x1800fb072  mov     dword ptr [rsp+0A40h+var_A20], ecx
0x1800fb076  lea     rcx, [r14+130h]
0x1800fb07d  movdqa  [rbp+940h+var_8C0], xmm0
0x1800fb085  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1800fb08a  test    eax, eax
0x1800fb08c  jz      loc_1800FCECE
0x1800fb092  movss   xmm13, cs:__real@3f800000
0x1800fb09b  lea     rdi, [rbx-18h]
0x1800fb09f  mov     rax, [rdi]
0x1800fb0a2  lea     r15, [r14+90h]
0x1800fb0a9  xorps   xmm9, xmm9
0x1800fb0ad  movss   [rbp+940h+var_92C], xmm13
0x1800fb0b3  xor     r12d, r12d
0x1800fb0b6  movss   [rbp+940h+var_938], xmm13
0x1800fb0bc  mov     rdx, r15
0x1800fb0bf  movss   [rbp+940h+var_924], xmm9
0x1800fb0c5  mov     rax, [rax+70h]
0x1800fb0c9  mov     rcx, rdi
0x1800fb0cc  movss   [rbp+940h+var_928], xmm9
0x1800fb0d2  movss   [rbp+940h+var_930], xmm9
0x1800fb0d8  movss   [rbp+940h+var_934], xmm9
0x1800fb0de  mov     [rbp+940h+var_920], r12d
0x1800fb0e2  mov     [rbp+940h+var_998], r12
0x1800fb0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0eb  movss   xmm8, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800fb0f4  or      r9d, 0FFFFFFFFh
0x1800fb0f8  xor     r11d, r11d
0x1800fb0fb  mov     [rsp+0A40h+var_A00], eax
0x1800fb0ff  mov     ecx, eax
0x1800fb101  mov     r10d, 74614D31h
0x1800fb107  test    eax, eax
0x1800fb109  jz      loc_1800FC014
0x1800fb10f  mov     qword ptr [rsp+0A40h+var_9D8], r11
0x1800fb114  xorps   xmm1, xmm1
0x1800fb117  mov     edi, r11d
0x1800fb11a  movups  xmm0, xmmword ptr [r13+0]
0x1800fb11f  movups  [rbp+940h+var_8B0], xmm1
0x1800fb126  movdqu  [rsp+0A40h+var_9D8+8], xmm0
0x1800fb12c  movups  [rbp+940h+var_8A0], xmm1
0x1800fb133  sub     ecx, 1
0x1800fb136  jz      loc_1800FBA21
0x1800fb13c  sub     ecx, 1
0x1800fb13f  jz      loc_1800FBA17
0x1800fb145  sub     ecx, 1
0x1800fb148  jz      short loc_1800FB161
0x1800fb14a  sub     ecx, 1
0x1800fb14d  jz      loc_1800FB91F
0x1800fb153  cmp     ecx, 1
0x1800fb156  jz      loc_1800FB91F
0x1800fb15c  jmp     loc_1800FBA31
0x1800fb161  movss   xmm0, dword ptr [rbx+2Ch]
0x1800fb166  lea     rdi, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1800fb16d  mov     eax, [rbx+30h]
0x1800fb170  lea     rdx, [rbp+940h+var_968]; struct GpMatrix *
0x1800fb174  movss   xmm11, dword ptr [rbx+18h]
0x1800fb17a  lea     rcx, [rbp+940h+var_968]; struct GpMatrix *
0x1800fb17e  movss   xmm12, dword ptr [rbx+1Ch]
0x1800fb184  mov     r8, r15; struct GpMatrix *
0x1800fb187  movss   xmm13, dword ptr [rbx+20h]
0x1800fb18d  movss   xmm14, dword ptr [rbx+24h]
0x1800fb193  movss   xmm15, dword ptr [rbx+28h]
0x1800fb199  movss   dword ptr [rbp+940h+var_958], xmm11
0x1800fb19f  movss   dword ptr [rbp+940h+var_958+4], xmm12
0x1800fb1a5  movss   [rbp+940h+var_950], xmm13
0x1800fb1ab  movss   dword ptr [rbp+940h+var_94C], xmm14
0x1800fb1b1  movss   dword ptr [rbp+940h+var_94C+4], xmm15
0x1800fb1b7  movss   [rsp+0A40h+var_9E0], xmm0
0x1800fb1bd  movss   dword ptr [rbp+940h+var_944], xmm0
0x1800fb1c2  mov     [rbp+940h+var_968], rdi
0x1800fb1c6  mov     [rbp+940h+var_95C], r9d
0x1800fb1ca  mov     [rbp+940h+var_960], r10d
0x1800fb1ce  mov     [rsp+0A40h+var_9F0], eax
0x1800fb1d2  mov     dword ptr [rbp+940h+var_944+4], eax
0x1800fb1d5  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x1800fb1da  cmp     [rsi+28h], r11d
0x1800fb1de  jnz     loc_1800FB916
0x1800fb1e4  cmp     [rsi+0A4h], r11d
0x1800fb1eb  jnz     short loc_1800FB1F7
0x1800fb1ed  cmp     [rsi+4Ch], r11d
0x1800fb1f1  jz      loc_1800FB916
0x1800fb1f7  test    byte ptr [rbp+940h+var_944+4], 8
0x1800fb1fb  jnz     loc_1800FB916
0x1800fb201  movdqu  xmm0, xmmword ptr [rbx+3Ch]
0x1800fb206  mov     [rbp+940h+var_834], r9d
0x1800fb20d  lea     rcx, [rbp+940h+var_7E0]; void *
0x1800fb214  mov     [rbp+940h+var_7C4], r9d
0x1800fb21b  mov     [rbp+940h+var_874], r9d
0x1800fb222  mov     [rbp+940h+var_95C], r9d
0x1800fb226  mov     [rbp+940h+var_804], r9d
0x1800fb22d  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1800fb234  mov     [rbp+940h+var_840], rdi
0x1800fb23b  mov     [rbp+940h+var_7D0], rdi
0x1800fb242  mov     [rbp+940h+var_880], rdi
0x1800fb249  mov     [rbp+940h+var_968], rdi
0x1800fb24d  mov     [rbp+940h+var_810], rdi
0x1800fb254  mov     edi, 2
0x1800fb259  mov     r8d, edi; unsigned __int64
0x1800fb25c  mov     [rbp+940h+var_864], 3F800000h
0x1800fb267  mov     [rbp+940h+var_870], 3F800000h
0x1800fb272  mov     [rbp+940h+var_85C], r11
0x1800fb279  lea     edx, [rdi+6]; unsigned __int64
0x1800fb27c  mov     [rbp+940h+var_868], r11d
0x1800fb283  mov     [rbp+940h+var_878], r10d
0x1800fb28a  mov     [rbp+940h+var_94C], 3F800000h
0x1800fb292  mov     [rbp+940h+var_958], 3F800000h
0x1800fb29a  mov     [rbp+940h+var_944], r11
0x1800fb29e  mov     [rbp+940h+var_950], r11d
0x1800fb2a2  mov     [rbp+940h+var_960], r10d
0x1800fb2a6  mov     [rbp+940h+var_7F4], 3F800000h
0x1800fb2b1  mov     [rbp+940h+var_800], 3F800000h
0x1800fb2bc  mov     [rbp+940h+var_7EC], r11
0x1800fb2c3  mov     [rbp+940h+var_7F8], r11d
0x1800fb2ca  mov     [rbp+940h+var_808], r10d
0x1800fb2d1  mov     [rbp+940h+var_980], r11
0x1800fb2d5  mov     [rbp+940h+var_988], r11
0x1800fb2d9  movups  xmmword ptr [rbp+940h+var_918.x], xmm0
0x1800fb2dd  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800fb2e2  movups  xmm0, xmmword ptr [rbx+0F8h]
0x1800fb2e9  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1800fb2f0  mov     r8d, edi; unsigned __int64
0x1800fb2f3  lea     edx, [rdi+6]; unsigned __int64
0x1800fb2f6  lea     rcx, [rbp+940h+var_9A8]; void *
0x1800fb2fa  movups  [rbp+940h+var_7E0], xmm0
0x1800fb301  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800fb306  mov     r9d, edi; int
0x1800fb309  lea     r8, [rbp+940h+var_9A8]; struct PointF *
0x1800fb30d  lea     rdx, [rbp+940h+var_7E0]; struct PointF *
0x1800fb314  mov     rcx, r15; this
0x1800fb317  call    ?Transform@GpMatrix@@QEBAXPEBVPointF@@PEAV2@H@Z; GpMatrix::Transform(PointF const *,PointF *,int)
0x1800fb31c  lea     rdx, [rbp+940h+var_9A8+8]; struct PointF *
0x1800fb320  lea     rcx, [rbp+940h+var_9A8]; struct PointF *
0x1800fb324  call    ?IsClosePointF@@YAHAEBVPointF@@0@Z; IsClosePointF(PointF const &,PointF const &)
0x1800fb329  xor     r11d, r11d
0x1800fb32c  test    eax, eax
0x1800fb32e  jnz     loc_1800FB916
0x1800fb334  movss   xmm10, dword ptr [rbp+940h+var_9A8]
0x1800fb33a  movss   xmm7, dword ptr [rbp+940h+var_9A8+8]
0x1800fb33f  movss   xmm9, dword ptr [rbp+940h+var_9A8+4]
0x1800fb345  movss   xmm6, dword ptr [rbp+940h+var_9A8+0Ch]
0x1800fb34a  cvtps2pd xmm0, xmm10
0x1800fb34e  cvtps2pd xmm2, xmm7
0x1800fb351  cvtps2pd xmm1, xmm9
0x1800fb355  subsd   xmm2, xmm0
0x1800fb359  cvtps2pd xmm0, xmm6
0x1800fb35c  mulsd   xmm2, xmm2
0x1800fb360  subsd   xmm0, xmm1
0x1800fb364  mulsd   xmm0, xmm0
0x1800fb368  addsd   xmm0, xmm2; X
0x1800fb36c  call    sqrt
0x1800fb371  xorps   xmm1, xmm1
0x1800fb374  movss   dword ptr [rbp+940h+var_978+4], xmm9
0x1800fb37a  cvtsd2ss xmm1, xmm0
0x1800fb37e  subss   xmm6, xmm9
0x1800fb383  addss   xmm1, xmm10
0x1800fb388  subss   xmm7, xmm10
0x1800fb38d  cvtps2pd xmm0, xmm6
0x1800fb390  movss   dword ptr [rbp+940h+var_978], xmm1
0x1800fb395  cvtps2pd xmm1, xmm7
0x1800fb398  call    _o_atan2_0
0x1800fb39d  mulsd   xmm0, cs:__real@4066800000000000
0x1800fb3a5  lea     r15d, [rdi-1]
0x1800fb3a9  lea     rcx, [rbp+940h+var_968]
0x1800fb3ad  mov     r9d, r15d
0x1800fb3b0  movaps  xmm7, xmm9
0x1800fb3b4  movaps  xmm6, xmm10
0x1800fb3b8  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x1800fb3bf  xorps   xmm8, xmm8
0x1800fb3c3  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1800fb3ca  movaps  xmm2, xmm7
0x1800fb3cd  divsd   xmm0, cs:__real@400921fb54442d18
0x1800fb3d5  movaps  xmm1, xmm6
0x1800fb3d8  cvtsd2ss xmm8, xmm0
0x1800fb3dd  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800fb3e2  lea     rcx, [rbp+940h+var_968]
0x1800fb3e6  mov     r8d, r15d
0x1800fb3e9  movaps  xmm1, xmm8
0x1800fb3ed  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800fb3f4  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x1800fb3f9  mov     r9d, r15d
0x1800fb3fc  lea     rcx, [rbp+940h+var_968]
0x1800fb400  movaps  xmm2, xmm9
0x1800fb404  movaps  xmm1, xmm10
0x1800fb408  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800fb40d  movaps  xmm2, xmm7
0x1800fb410  lea     rcx, [rbp+940h+var_810]
0x1800fb417  movaps  xmm1, xmm6
0x1800fb41a  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800fb41f  movaps  xmm1, xmm8
0x1800fb423  lea     rcx, [rbp+940h+var_810]
0x1800fb42a  mov     r8d, r15d
0x1800fb42d  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x1800fb432  mov     r9d, r15d
0x1800fb435  lea     rcx, [rbp+940h+var_810]
0x1800fb43c  movaps  xmm2, xmm9
0x1800fb440  movaps  xmm1, xmm10
0x1800fb444  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800fb449  movups  xmm0, xmmword ptr [r14+0A0h]
0x1800fb451  mov     eax, [r14+98h]
0x1800fb458  lea     r8, [rbp+940h+var_968]; struct GpMatrix *
0x1800fb45c  movss   xmm1, dword ptr [r14+0B4h]
0x1800fb465  lea     rdx, [rbp+940h+var_840]; struct GpMatrix *
0x1800fb46c  movups  [rbp+940h+var_830], xmm0
0x1800fb473  lea     rcx, [rbp+940h+var_840]; struct GpMatrix *
0x1800fb47a  mov     [rbp+940h+var_838], eax
0x1800fb480  movss   xmm0, dword ptr [r14+0B0h]
0x1800fb489  mov     eax, [r14+0B8h]
0x1800fb490  movss   [rbp+940h+var_820], xmm0
0x1800fb498  movss   [rbp+940h+var_81C], xmm1
0x1800fb4a0  mov     [rbp+940h+var_818], eax
0x1800fb4a6  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x1800fb4ab  movups  xmm0, [rbp+940h+var_830]
0x1800fb4b2  mov     ecx, [rbp+940h+var_838]
0x1800fb4b8  mov     [rbp+940h+var_7C8], ecx
0x1800fb4be  movups  [rbp+940h+var_7C0], xmm0
0x1800fb4c5  movss   xmm0, [rbp+940h+var_820]
0x1800fb4cd  movss   [rbp+940h+var_7B0], xmm0
0x1800fb4d5  movss   xmm1, [rbp+940h+var_81C]
0x1800fb4dd  lea     rcx, [rbp+940h+var_7D0]
0x1800fb4e4  mov     eax, [rbp+940h+var_818]
0x1800fb4ea  movss   [rbp+940h+var_7AC], xmm1
0x1800fb4f2  mov     [rbp+940h+var_7A8], eax
0x1800fb4f8  call    ?Invert@GpMatrix@@QEAA?AW4Status@@XZ; GpMatrix::Invert(void)
0x1800fb4fd  xor     r11d, r11d
0x1800fb500  test    eax, eax
0x1800fb502  jnz     loc_1800FB90D
0x1800fb508  mov     rdi, [rbp+940h+var_990]
0x1800fb50c  lea     rdx, [rbp+940h+var_840]; struct GpMatrix *
0x1800fb513  mov     rcx, rdi; this
0x1800fb516  call    ?Transform@GpPath@@QEAAXPEBVGpMatrix@@@Z; GpPath::Transform(GpMatrix const *)
0x1800fb51b  mov     rcx, [rdi]
0x1800fb51e  lea     rdx, [rbp+940h+var_988]
0x1800fb522  xorps   xmm0, xmm0
0x1800fb525  xor     r9d, r9d
0x1800fb528  movss   dword ptr [rsp+0A40h+var_A18], xmm0
0x1800fb52e  xor     r8d, r8d
0x1800fb531  movss   dword ptr [rsp+0A40h+var_A20], xmm0
0x1800fb537  mov     rax, [rcx+68h]
0x1800fb53b  mov     rcx, rdi
0x1800fb53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb543  lea     rdx, [rbp+940h+var_7D0]; struct GpMatrix *
0x1800fb54a  mov     rcx, rdi; this
0x1800fb54d  call    ?Transform@GpPath@@QEAAXPEBVGpMatrix@@@Z; GpPath::Transform(GpMatrix const *)
0x1800fb552  movss   xmm4, dword ptr [rbp+940h+var_980]
0x1800fb557  xor     eax, eax
0x1800fb559  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800fb55f  movss   xmm8, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800fb568  mov     qword ptr [rsp+0A40h+var_9D8+8], rax
0x1800fb56d  jz      short loc_1800FB57E
0x1800fb56f  movaps  xmm0, xmm4
0x1800fb572  roundss xmm0, xmm0, 0Ah
0x1800fb578  cvttss2si eax, xmm0
0x1800fb57c  jmp     short loc_1800FB594
0x1800fb57e  xorps   xmm4, xmm8
0x1800fb582  xorps   xmm0, xmm0
0x1800fb585  cvtss2sd xmm0, xmm4; X
0x1800fb589  call    floor
0x1800fb58e  cvttsd2si eax, xmm0
0x1800fb592  neg     eax
0x1800fb594  movss   xmm7, dword ptr [rbp+940h+var_988+4]
0x1800fb599  lea     rcx, [rbp+940h+var_810]
  ... truncated ...
```
