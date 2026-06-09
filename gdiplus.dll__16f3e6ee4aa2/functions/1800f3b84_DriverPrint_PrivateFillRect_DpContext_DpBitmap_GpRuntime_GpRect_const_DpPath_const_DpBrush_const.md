# DriverPrint::PrivateFillRect(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpPath const *,DpBrush const *)

- ea: `0x1800f3b84`
- end: `0x1800f5ad0`
- name: `?PrivateFillRect@DriverPrint@@AEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpPath@@PEBUDpBrush@@@Z`
- size: `8012`
- prototype: `__int64 __fastcall(__int64 *, __int64, struct DpBitmap *, unsigned int *, GpPath *, __int64)`
- caller_count: `2`
- callee_count: `53`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b7160`
- `0x180137460`

## callees

- `0x18000dfb8`
- `0x180010a68`
- `0x180013ad0`
- `0x18001a2e0`
- `0x18001d770`
- `0x18001fc64`
- `0x18001fea4`
- `0x1800202a0`
- `0x180023ca4`
- `0x180027b0c`
- `0x18002ba98`
- `0x18002f18c`
- `0x180041e78`
- `0x180042d20`
- `0x180044a70`
- `0x18004b4b0`
- `0x18004e87c`
- `0x18004eae0`
- `0x18004f028`
- `0x18004f0a8`
- `0x18004f1a0`
- `0x18005205c`
- `0x1800527b4`
- `0x180054870`
- `0x180061828`
- `0x180076f28`
- `0x18009cd98`
- `0x1800a2830`
- `0x1800ad22c`
- `0x1800b7760`
- `0x1800c6d6c`
- `0x1800dd4e0`
- `0x1800e6c40`
- `0x1800f287c`
- `0x1800f3b84`
- `0x1800fe680`
- `0x1800fefb0`
- `0x1800fefe0`
- `0x1800ff028`
- `0x1800ff034`
- `0x180110d0c`
- `0x180130418`
- `0x18013080c`
- `0x180130ec0`
- `0x180137254`
- `0x180137c38`
- `0x180137dcc`
- `0x180137e50`
- `0x18013808c`
- `0x1801384f0`

## import_xrefs

- `GDI32!SetROP2` at `0x1800f43f7`
- `GDI32!SetROP2` at `0x1800f4421`
- `GDI32!SetROP2` at `0x1800f4955`
- `GDI32!SetROP2` at `0x1800f497f`
- `GDI32!SetROP2` at `0x1800f43f7`
- `GDI32!SetROP2` at `0x1800f4421`
- `GDI32!SetROP2` at `0x1800f4955`
- `GDI32!SetROP2` at `0x1800f497f`
- `GDI32!GetStockObject` at `0x1800f43cf`
- `GDI32!GetStockObject` at `0x1800f48bf`
- `GDI32!GetStockObject` at `0x1800f43cf`
- `GDI32!GetStockObject` at `0x1800f48bf`

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
  int v103; // r15d
  int v104; // eax
  int v105; // xmm0_4
  int v106; // eax
  struct DpBitmap *v107; // rdx
  unsigned int v108; // r9d
  struct GpBitmap *Bitmap; // rax
  __int64 v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // r8
  bool v113; // di
  LONG v114; // eax
  unsigned int v115; // xmm1_4
  unsigned int v116; // eax
  float v117; // xmm0_4
  __m128 v118; // xmm1
  int v119; // eax
  float v120; // xmm1_4
  float v121; // xmm0_4
  float v122; // xmm0_4
  __m128 v123; // xmm1
  int v124; // r10d
  double v125; // xmm0_8
  __m128 v126; // xmm1
  int v127; // eax
  double v128; // xmm0_8
  __m128 v129; // xmm1
  __m128 v130; // xmm1
  int v131; // eax
  __m128 v132; // xmm1
  int v133; // eax
  __int64 v134; // rax
  __m128 v135; // xmm1
  int v136; // eax
  double v137; // xmm0_8
  int v138; // r11d
  __int64 v139; // r8
  int v140; // ecx
  int v141; // r9d
  __int64 v142; // rdx
  float v143; // xmm7_4
  __m128 v144; // xmm1
  int v145; // eax
  __m128i v146; // xmm6
  float v147; // xmm6_4
  __m128 v148; // xmm1
  int v149; // eax
  __m128 v150; // xmm1
  int v151; // eax
  __m128 v152; // xmm1
  int v153; // eax
  GpMatrix *v154; // rdi
  LONG v155; // xmm9_4
  LONG v156; // xmm10_4
  LONG v157; // xmm11_4
  LONG v158; // xmm12_4
  int v159; // xmm7_4
  int v160; // xmm8_4
  int v161; // xmm13_4
  int v162; // xmm14_4
  int v163; // xmm15_4
  float v164; // xmm5_4
  float v165; // xmm0_4
  float v166; // xmm1_4
  float v167; // xmm3_4
  float v168; // xmm4_4
  float v169; // xmm6_4
  float v170; // xmm0_4
  float v171; // xmm2_4
  void (__fastcall *v172)(__int64 *, __int64, int *, __m128i *); // rax
  int v173; // r8d
  int v174; // xmm6_4
  int v175; // eax
  int v176; // xmm0_4
  int v177; // eax
  __int64 v178; // rcx
  void (__fastcall ***v179)(_QWORD, _QWORD); // rax
  int v180; // eax
  __int128 v181; // xmm0
  float v182; // xmm0_4
  int v183; // xmm1_4
  int v184; // eax
  float v185; // xmm0_4
  int v186; // xmm1_4
  int v187; // xmm0_4
  int v188; // eax
  unsigned int v189; // [rsp+28h] [rbp-E0h]
  struct GpRuntime::GpRect *v190; // [rsp+28h] [rbp-E0h]
  __int32 v191; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v192; // [rsp+4Ch] [rbp-BCh] BYREF
  int v193; // [rsp+50h] [rbp-B8h]
  int v194; // [rsp+54h] [rbp-B4h]
  int v195[4]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v196[2]; // [rsp+68h] [rbp-A0h]
  __int64 v197; // [rsp+70h] [rbp-98h] BYREF
  __int128 v198; // [rsp+78h] [rbp-90h] BYREF
  int v199; // [rsp+88h] [rbp-80h] BYREF
  struct DpBitmap *v200; // [rsp+90h] [rbp-78h]
  int v201; // [rsp+98h] [rbp-70h]
  __m128i si128; // [rsp+A0h] [rbp-68h] BYREF
  void (__fastcall ***v203)(_QWORD, _QWORD); // [rsp+B0h] [rbp-58h]
  GpPath *v204; // [rsp+B8h] [rbp-50h]
  EpScanDIB *v205; // [rsp+C0h] [rbp-48h] BYREF
  EpScanDIB *v206; // [rsp+C8h] [rbp-40h]
  HDC v207; // [rsp+D0h] [rbp-38h] BYREF
  float v208; // [rsp+D8h] [rbp-30h]
  float v209; // [rsp+DCh] [rbp-2Ch]
  void **v210; // [rsp+E0h] [rbp-28h] BYREF
  int v211; // [rsp+E8h] [rbp-20h]
  int v212; // [rsp+ECh] [rbp-1Ch]
  unsigned __int64 v213; // [rsp+F0h] [rbp-18h]
  int v214; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v215; // [rsp+FCh] [rbp-Ch]
  unsigned __int64 v216; // [rsp+104h] [rbp-4h]
  float v217; // [rsp+110h] [rbp+8h]
  int v218; // [rsp+114h] [rbp+Ch]
  int v219; // [rsp+118h] [rbp+10h]
  float v220; // [rsp+11Ch] [rbp+14h]
  int v221; // [rsp+120h] [rbp+18h]
  int v222; // [rsp+124h] [rbp+1Ch]
  int v223; // [rsp+128h] [rbp+20h]
  struct tagPOINT v224[2]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v225[20]; // [rsp+140h] [rbp+38h]
  unsigned __int64 v226; // [rsp+154h] [rbp+4Ch]
  __m128i v227; // [rsp+168h] [rbp+60h] BYREF
  int v228; // [rsp+178h] [rbp+70h] BYREF
  int v229; // [rsp+17Ch] [rbp+74h]
  int v230; // [rsp+180h] [rbp+78h]
  int v231; // [rsp+184h] [rbp+7Ch]
  __m128i v232; // [rsp+188h] [rbp+80h] BYREF
  __int128 v233; // [rsp+198h] [rbp+90h] BYREF
  __int128 v234; // [rsp+1A8h] [rbp+A0h]
  int v235; // [rsp+1B8h] [rbp+B0h]
  int v236; // [rsp+1BCh] [rbp+B4h]
  int v237; // [rsp+1C0h] [rbp+B8h]
  void **v238; // [rsp+1C8h] [rbp+C0h] BYREF
  int v239; // [rsp+1D0h] [rbp+C8h]
  int v240; // [rsp+1D4h] [rbp+CCh]
  __int64 v241; // [rsp+1D8h] [rbp+D0h]
  int v242; // [rsp+1E0h] [rbp+D8h]
  __int64 v243; // [rsp+1E4h] [rbp+DCh]
  EpScanDIB *v244; // [rsp+1ECh] [rbp+E4h]
  float v245; // [rsp+1F8h] [rbp+F0h] BYREF
  float v246; // [rsp+1FCh] [rbp+F4h]
  float v247; // [rsp+200h] [rbp+F8h]
  float v248; // [rsp+204h] [rbp+FCh]
  void **v249; // [rsp+208h] [rbp+100h] BYREF
  int v250; // [rsp+210h] [rbp+108h]
  int v251; // [rsp+214h] [rbp+10Ch]
  __int128 v252; // [rsp+218h] [rbp+110h]
  int v253; // [rsp+228h] [rbp+120h]
  int v254; // [rsp+22Ch] [rbp+124h]
  int v255; // [rsp+230h] [rbp+128h]
  void **v256; // [rsp+238h] [rbp+130h] BYREF
  int v257; // [rsp+240h] [rbp+138h]
  int v258; // [rsp+244h] [rbp+13Ch]
  __int64 v259; // [rsp+248h] [rbp+140h]
  int v260; // [rsp+250h] [rbp+148h]
  __int64 v261; // [rsp+254h] [rbp+14Ch]
  EpScanDIB *v262; // [rsp+25Ch] [rbp+154h]
  __int128 v263; // [rsp+268h] [rbp+160h] BYREF
  void **v264; // [rsp+278h] [rbp+170h] BYREF
  int v265; // [rsp+280h] [rbp+178h]
  int v266; // [rsp+284h] [rbp+17Ch]
  __int128 v267; // [rsp+288h] [rbp+180h]
  int v268; // [rsp+298h] [rbp+190h]
  int v269; // [rsp+29Ch] [rbp+194h]
  int v270; // [rsp+2A0h] [rbp+198h]
  int v271; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v272; // [rsp+2ACh] [rbp+1A4h]
  int v273; // [rsp+2B4h] [rbp+1ACh]
  int v274; // [rsp+2B8h] [rbp+1B0h]
  int v275; // [rsp+2C8h] [rbp+1C0h]
  __int64 v276; // [rsp+310h] [rbp+208h]
  int v277; // [rsp+320h] [rbp+218h]
  _DWORD v278[308]; // [rsp+468h] [rbp+360h] BYREF
  float v279; // [rsp+938h] [rbp+830h] BYREF
  float v280; // [rsp+93Ch] [rbp+834h]
  float v281; // [rsp+940h] [rbp+838h]
  float v282; // [rsp+944h] [rbp+83Ch]
  float v283; // [rsp+948h] [rbp+840h]
  float v284; // [rsp+94Ch] [rbp+844h]
  float v285; // [rsp+950h] [rbp+848h]
  float v286; // [rsp+954h] [rbp+84Ch]

  v7 = a4[3];
  v9 = *a4;
  v204 = a5;
  v200 = a3;
  v11 = a4[1];
  v12 = (unsigned int)v9 + a4[2];
  v232 = 0;
  result = DpRegion::GetRectVisibility(a2 + 304, v9, v11, v12, (unsigned int)v11 + v7, &v232);
  if ( (_DWORD)result )
  {
    v14 = (GpTexture *)(a6 - 24);
    v15 = *(_QWORD *)(a6 - 24);
    v220 = FLOAT_1_0;
    BufferDIB = 0;
    v217 = FLOAT_1_0;
    v222 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64))(v15 + 112);
    v221 = 0;
    v219 = 0;
    v218 = 0;
    v223 = 0;
    v203 = 0;
    v18 = v17(a6 - 24, a2 + 144);
    v19 = _xmm;
    LODWORD(v20) = 0;
    v191 = v18;
    if ( !v18 )
      goto LABEL_116;
    v197 = 0;
    v21 = 0;
    v22 = *(_OWORD *)a4;
    v233 = 0;
    v198 = v22;
    v234 = 0;
    if ( v18 == 1 )
    {
      DWORD2(v198) = 1;
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
          v213 = __PAIR64__(v26, v25);
          v214 = v27;
          v215 = __PAIR64__(v29, v28);
          v196[0] = v23;
          v216 = __PAIR64__(v24, v23);
          v210 = &GpMatrix::`vftable';
          v212 = -1;
          v211 = 1952533809;
          v195[0] = v24;
          GpMatrix::MultiplyMatrix(
            (struct GpMatrix *)&v210,
            (const struct GpMatrix *)&v210,
            (const struct GpMatrix *)(a2 + 144));
          if ( *((_DWORD *)a1 + 10) == (_DWORD)v20
            && (*((_DWORD *)a1 + 41) != (_DWORD)v20 || *((_DWORD *)a1 + 19) != (_DWORD)v20)
            && (v216 & 0x800000000LL) == 0 )
          {
            v32 = _mm_loadu_si128((const __m128i *)(a6 + 60));
            v251 = v30;
            v266 = v30;
            v240 = v30;
            v212 = v30;
            v258 = v30;
            v249 = &GpMatrix::`vftable';
            v264 = &GpMatrix::`vftable';
            v238 = &GpMatrix::`vftable';
            v210 = &GpMatrix::`vftable';
            v256 = &GpMatrix::`vftable';
            v243 = 1065353216;
            v241 = 1065353216;
            v244 = v20;
            v242 = (int)v20;
            v239 = v31;
            v215 = 1065353216;
            v213 = 1065353216;
            v216 = (unsigned __int64)v20;
            v214 = (int)v20;
            v211 = v31;
            v261 = 1065353216;
            v259 = 1065353216;
            v262 = v20;
            v260 = (int)v20;
            v257 = v31;
            v206 = v20;
            v205 = v20;
            *(__m128i *)&v224[0].x = v32;
            `vector constructor iterator'(&v263, 8u, 2u, (void *(*)(void *))PointF::PointF);
            v263 = *(_OWORD *)(a6 + 248);
            `vector constructor iterator'(&si128, 8u, 2u, (void *(*)(void *))PointF::PointF);
            GpMatrix::Transform((GpMatrix *)(a2 + 144), (const struct PointF *)&v263, (struct PointF *)&si128, 2);
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
              HIDWORD(v207) = v35;
              v37 = v36;
              *(float *)&v207 = v37 + v34;
              o_atan2_0();
              GpMatrix::Translate(&v210, v38, v39, 1);
              GpMatrix::Rotate(&v210, v40, 1);
              GpMatrix::Translate(&v210, v41, v42, 1);
              GpMatrix::Translate(&v256, v43, v44, v45);
              GpMatrix::Rotate(&v256, v46, 1);
              GpMatrix::Translate(&v256, v47, v48, 1);
              v49 = *(_DWORD *)(a2 + 152);
              v50 = *(_DWORD *)(a2 + 180);
              v252 = *(_OWORD *)(a2 + 160);
              v250 = v49;
              v51 = *(_DWORD *)(a2 + 184);
              v253 = *(_DWORD *)(a2 + 176);
              v254 = v50;
              v255 = v51;
              GpMatrix::MultiplyMatrix(
                (struct GpMatrix *)&v249,
                (const struct GpMatrix *)&v249,
                (const struct GpMatrix *)&v210);
              v265 = v250;
              v267 = v252;
              v268 = v253;
              v269 = v254;
              v270 = v255;
              v52 = GpMatrix::Invert(&v264);
              LODWORD(v20) = 0;
              if ( !v52 )
              {
                v53 = v204;
                GpPath::Transform(v204, (const struct GpMatrix *)&v249);
                (*(void (__fastcall **)(GpPath *, EpScanDIB **, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v53 + 104LL))(
                  v53,
                  &v205,
                  0,
                  0,
                  0,
                  0);
                GpPath::Transform(v53, (const struct GpMatrix *)&v264);
                v19 = _xmm;
                *(_QWORD *)&v198 = 0;
                if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
                  v56 = (int)_mm_round_ss((__m128)(unsigned int)v206, (__m128)(unsigned int)v206, 10).m128_f32[0];
                else
                  v56 = -(int)floor(COERCE_FLOAT((unsigned int)v206 ^ _xmm));
                *((_QWORD *)&v198 + 1) = v56 | 0x100000000LL;
                GpMatrix::Translate(&v256, v54, v55, 0);
                GpMatrix::Translate(&v238, v57, v58, v59);
                v60 = (GpPathGradient *)(a6 - 24);
                v61 = GpLineGradient::ChangeLinePoints(a6 - 24, &si128, &v207, *(unsigned int *)(a6 + 104));
                LODWORD(v20) = 0;
                if ( !v61 )
                {
                  BufferDIB = GpBitmap::CreateBitmapAndFillWithBrush(
                                *(unsigned int *)(a2 + 48),
                                *(unsigned int *)(a2 + 52),
                                &v238,
                                &v198,
                                a6 - 24,
                                &v197);
                  v62 = v195[0];
                  *(_OWORD *)(a6 + 60) = *(_OWORD *)&v224[0].x;
                  *(_DWORD *)(a6 + 16) = 1952533809;
                  *(_DWORD *)(a6 + 44) = v196[0];
                  *(_DWORD *)(a6 + 24) = v25;
                  *(_DWORD *)(a6 + 28) = v26;
                  *(_DWORD *)(a6 + 32) = v27;
                  *(_DWORD *)(a6 + 36) = v28;
                  *(_DWORD *)(a6 + 40) = v29;
                  *(_DWORD *)(a6 + 48) = v62;
                  *(_OWORD *)(a6 + 248) = v263;
                  if ( !BufferDIB )
                  {
                    ContextHdc = DriverPrint::GetContextHdc((struct DpContext *)a2, v200);
                    v64 = v197;
                    v65 = ContextHdc;
                    if ( ContextHdc )
                    {
                      BufferDIB = GpBitmap::LockBits(v197, 0, 1, 2498570, &v233);
                      if ( !BufferDIB )
                      {
                        v66 = *a1;
                        v191 = 0;
                        v192 = 0;
                        (*(void (__fastcall **)(__int64 *, HDC, __int64, unsigned int *, __int32 *, unsigned int *, _DWORD))(v66 + 40))(
                          a1,
                          v65,
                          a2,
                          a4,
                          &v191,
                          &v192,
                          0);
                        if ( *((_DWORD *)a1 + 41)
                          && *((_DWORD *)v53 + 26) == 4
                          && (unsigned int)DpPath::IsRectangular(v53) )
                        {
                          (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v65, a2, v53);
                          BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                        a1,
                                        v65,
                                        &v233,
                                        15728673,
                                        0,
                                        &v256,
                                        HIDWORD(v206));
                          (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v65);
                        }
                        else
                        {
                          BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                        a1,
                                        v65,
                                        &v233,
                                        5898313,
                                        1,
                                        &v256,
                                        HIDWORD(v206));
                          if ( !BufferDIB )
                          {
                            ConvertPathToGdi::ConvertPathToGdi(
                              (ConvertPathToGdi *)&v271,
                              v53,
                              (struct GpMatrix *)(a2 + 144),
                              2u,
                              0);
                            if ( v271 == 1198932785 )
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
                              v70 = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v271, v65, v68);
                              BufferDIB = v70 == 0;
                              LODWORD(v68) = v70;
                              SetROP2(v65, v69);
                              if ( (_DWORD)v68 )
                                BufferDIB = DriverPrint::PrivateFillDiagonalGradient(
                                              a1,
                                              v65,
                                              &v233,
                                              5898313,
                                              1,
                                              &v256,
                                              HIDWORD(v206));
                              v64 = v197;
                            }
                            ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v271);
                          }
                        }
                        (*(void (__fastcall **)(__int64 *, HDC, _QWORD, _QWORD))(*a1 + 48))(
                          a1,
                          v65,
                          (unsigned int)v191,
                          v192);
                        GpBitmap::UnlockBits(v64, &v233);
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
          DWORD2(v198) = v74;
          if ( v75 )
            v73 = a4[3];
          HIDWORD(v198) = v73;
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
            DWORD2(v198) = 1024;
          }
          else
          {
            if ( v76 < v72 )
              v72 = ((int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 1)
                  + ((unsigned int)((unsigned __int64)(1717986919LL * (v72 - 256)) >> 32) >> 31)
                  + 256;
            DWORD2(v198) = v72;
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
            HIDWORD(v198) = 1024;
          }
          else
          {
            if ( v79 < v78 )
              v78 = ((int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 1)
                  + ((unsigned int)((unsigned __int64)(1717986919LL * (v78 - 256)) >> 32) >> 31)
                  + 256;
            HIDWORD(v198) = v78;
          }
        }
        goto LABEL_69;
      }
      HIDWORD(v198) = 1;
    }
    LOBYTE(v21) = *((_DWORD *)a1 + 10) == 0;
LABEL_69:
    if ( *((_DWORD *)a1 + 41) != (_DWORD)v20 || *((_DWORD *)a1 + 10) == 1 || v21 )
    {
      v81 = DriverPrint::GetContextHdc((struct DpContext *)a2, v200);
      LODWORD(v20) = 0;
      v82 = v81;
      if ( v81 )
      {
        *(_QWORD *)&v198 = 0;
        v207 = 0;
        v210 = &GpMatrix::`vftable';
        v212 = -1;
        v215 = 1065353216;
        v213 = 1065353216;
        v216 = 0;
        v214 = 0;
        v208 = (float)SDWORD2(v198);
        v83 = _mm_cvtsi32_si128(*a4);
        v209 = (float)SHIDWORD(v198);
        v84 = _mm_cvtsi32_si128(a4[1]);
        v211 = 1952533809;
        si128.m128i_i32[0] = _mm_cvtepi32_ps(v83).m128_u32[0];
        v85 = _mm_cvtsi32_si128(a4[2]);
        si128.m128i_i32[1] = _mm_cvtepi32_ps(v84).m128_u32[0];
        *(float *)v84.m128i_i32 = (float)(int)a4[3];
        si128.m128i_i32[2] = _mm_cvtepi32_ps(v85).m128_u32[0];
        si128.m128i_i32[3] = v84.m128i_i32[0];
        GpMatrix::InferAffineMatrix(&v210, &v207, &si128);
        GpMatrix::MultiplyMatrix(
          (struct GpMatrix *)&v210,
          (const struct GpMatrix *)(a2 + 144),
          (const struct GpMatrix *)&v210);
        v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a6 - 24) + 64LL))(a6 - 24);
        v203 = (void (__fastcall ***)(_QWORD, _QWORD))v86;
        v87 = (_DWORD *)v86;
        if ( v86 )
        {
          if ( !*((_DWORD *)a1 + 41) && *((_DWORD *)a1 + 10) == 1 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 168LL))(v86);
            v87 = v203;
            *((_DWORD *)a1 + 41) = 1;
          }
          if ( (unsigned int)(v191 - 4) <= 1 )
          {
            v87[110] = 1065772646;
            *((_QWORD *)v87 + 2) = 0;
          }
          BufferDIB = GpBitmap::CreateBitmapAndFillWithBrush(
                        *(unsigned int *)(a2 + 48),
                        *(unsigned int *)(a2 + 52),
                        &v210,
                        &v198,
                        v87,
                        &v197);
          (**v203)(v203, 1);
          if ( BufferDIB )
          {
            v203 = 0;
          }
          else
          {
            if ( v197 )
            {
              v88 = 6;
              v89 = 6;
              if ( *((_DWORD *)a1 + 10) != 1 )
                v89 = 2;
              v196[0] = v89;
              if ( (unsigned int)GpBitmap::LockBits(v197, 0, 1, 2498570, &v233) )
                goto LABEL_110;
              BufferDIB = 0;
              v90 = *(void (__fastcall **)(__int64 *, HDC, __int64, unsigned int *, __int32 *, unsigned int *, _DWORD))(*a1 + 40);
              v191 = 0;
              v192 = 0;
              v90(a1, v82, a2, a4, &v191, &v192, 0);
              if ( !v21 || HIDWORD(v198) != 1 && DWORD2(v198) != 1 )
              {
                (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v82, a2, v204);
                DpBitmap::DpBitmap((DpBitmap *)&v271, 0);
                GpBitmap::InitializeSurfaceForGdipBitmap(v197, &v271, (unsigned int)v233, DWORD1(v233));
                v276 = v234;
                v277 = DWORD2(v233);
                v272 = v233;
                v95 = *((_DWORD *)a1 + 10) == 1;
                v273 = 2498570;
                v275 = 3;
                v274 = 3 * DWORD1(v233) * v233;
                if ( !v95 )
                  v88 = 2;
                if ( v21 )
                  v96 = (*((unsigned __int8 *)a1 + 72) + (unsigned int)*((unsigned __int8 *)a1 + 73)) >> 1;
                else
                  v96 = -1;
                ConvertBitmapToGdi::ConvertBitmapToGdi(
                  (ConvertBitmapToGdi *)v278,
                  v82,
                  (struct DpBitmap *)&v271,
                  (const struct GpRuntime::GpRect *)&v198,
                  v88,
                  v96,
                  1);
                if ( v278[0] == 1198932785 )
                {
                  v97 = a4[1];
                  v98 = *a4 + a4[2];
                  v224[0].x = *a4;
                  v224[1].x = v98;
                  v99 = a4[3];
                  v224[0].y = v97;
                  *(_DWORD *)&v225[4] = v97 + v99;
                  v224[1].y = v97;
                  *(_DWORD *)v225 = v224[0].x;
                  LOBYTE(BufferDIB) = ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v278, v82, v224, 0, v189) == 0;
                }
                else
                {
                  BufferDIB = 1;
                }
                (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v82);
                ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v278);
                DpBitmap::~DpBitmap((DpBitmap *)&v271);
                goto LABEL_109;
              }
              v91 = v204;
              if ( *((_DWORD *)a1 + 41) )
              {
                if ( *((_DWORD *)v204 + 26) != 4 || !(unsigned int)DpPath::IsRectangular(v204) )
                {
LABEL_90:
                  BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v233, &v198, a4, 6684742, 1);
                  if ( !BufferDIB )
                  {
                    ConvertPathToGdi::ConvertPathToGdi(
                      (ConvertPathToGdi *)&v271,
                      v91,
                      (struct GpMatrix *)(a2 + 144),
                      v196[0],
                      0);
                    if ( v271 == 1198932785 )
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
                      LODWORD(v93) = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v271, v82, v93);
                      BufferDIB = (_DWORD)v93 == 0;
                      SetROP2(v82, v94);
                      if ( (_DWORD)v93 )
                        BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v233, &v198, a4, 6684742, 1);
                    }
                    ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v271);
                  }
                  goto LABEL_109;
                }
              }
              else if ( *((_DWORD *)a1 + 19) )
              {
                goto LABEL_90;
              }
              (*(void (__fastcall **)(__int64 *, HDC, __int64, GpPath *))(*a1 + 208))(a1, v82, a2, v91);
              BufferDIB = DriverPrint::PrivateFillGradient(a1, v82, &v233, &v198, a4, 13369376, 0);
              (*(void (__fastcall **)(__int64 *, HDC))(*a1 + 216))(a1, v82);
LABEL_109:
              (*(void (__fastcall **)(__int64 *, HDC, _QWORD, _QWORD))(*a1 + 48))(a1, v82, (unsigned int)v191, v192);
              GpBitmap::UnlockBits(v197, &v233);
LABEL_110:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v197 + 56LL))(v197);
              DpContext::ReleaseHdc((DpContext *)a2, v82, 0);
              return BufferDIB;
            }
            v203 = 0;
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
    v192 = (unsigned int)v20;
    if ( v100 )
    {
      if ( v100 != 1 )
        return 6;
      v101 = *((_DWORD *)a1 + 40);
      v102 = (int)v20;
      LOBYTE(v102) = v101 == 0;
      v201 = v102;
      if ( v101 )
      {
        v103 = *((_DWORD *)a1 + 41) != 0 ? 2 : 66;
        if ( *((_DWORD *)a1 + 84) != 1 || (v95 = *((_DWORD *)a1 + 85) == 1, v193 = 1952533809, !v95) )
        {
          v104 = *(_DWORD *)(a2 + 152);
          v217 = *(float *)(a2 + 160);
          v218 = *(_DWORD *)(a2 + 164);
          v219 = *(_DWORD *)(a2 + 168);
          v220 = *(float *)(a2 + 172);
          v221 = *(_DWORD *)(a2 + 176);
          v105 = *(_DWORD *)(a2 + 180);
          v193 = v104;
          v106 = *(_DWORD *)(a2 + 184);
          v222 = v105;
          v192 = 1;
          v223 = v106;
        }
LABEL_141:
        v95 = *(_DWORD *)a6 == 2;
        v107 = v200;
        v108 = *((_DWORD *)a1 + 12);
        v196[0] = v108;
        v205 = (EpScanDIB *)*((_QWORD *)v200 + 16);
        LODWORD(v197) = *((_DWORD *)a1 + 11);
        if ( v95 )
        {
          Bitmap = GpTexture::GetBitmap(v14);
          if ( Bitmap )
          {
            v110 = *(_QWORD *)Bitmap;
            v207 = 0;
            (*(void (__fastcall **)(struct GpBitmap *, HDC *))(v110 + 368))(Bitmap, &v207);
            v95 = (*(_BYTE *)(a6 + 360) & 1) == 0;
            v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v224[0] = (struct tagPOINT)&GpMatrix::`vftable';
            v224[1].y = -1;
            *(_QWORD *)&v225[12] = 1065353216;
            *(_QWORD *)v225 = 1065353216;
            v226 = 0;
            *(_DWORD *)&v225[8] = 0;
            v224[1].x = 1952533809;
            if ( v95 )
            {
              v114 = *(_DWORD *)(a2 + 152);
              v115 = *(_DWORD *)(a2 + 180);
              *(_OWORD *)v225 = *(_OWORD *)(a2 + 160);
              v224[1].x = v114;
              v116 = *(_DWORD *)(a2 + 184);
              *(_DWORD *)&v225[16] = *(_DWORD *)(a2 + 176);
              v226 = __PAIR64__(v116, v115);
            }
            else
            {
              if ( !Feature_GdiPlusOptimizations_Misc_IsEnabled )
                floor((float)(*((float *)v200 + 6) / 100.0));
              if ( !v113 )
                floor((float)(*((float *)v200 + 5) / 100.0));
              GpMatrix::Scale(v224, v111, v112, 0);
            }
            GpMatrix::MultiplyMatrix(
              (struct GpMatrix *)v224,
              (const struct GpMatrix *)(a6 + 8),
              (const struct GpMatrix *)v224);
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            GpMatrix::VectorTransform((GpMatrix *)v224, (struct PointF *)&si128, 2);
            v117 = o_sqrtf_0(
                     (float)(*(float *)&si128.m128i_i32[1] * *(float *)&si128.m128i_i32[1])
                   + (float)(*(float *)si128.m128i_i32 * *(float *)si128.m128i_i32))
                 + 0.5;
            if ( v113 )
            {
              v118 = 0;
              v118.m128_f32[0] = v117;
              v119 = (int)_mm_round_ss(v118, v118, 9).m128_f32[0];
            }
            else
            {
              v119 = (int)floor(v117);
            }
            v120 = *(float *)&si128.m128i_i32[2];
            v121 = *(float *)&si128.m128i_i32[3];
            *((_DWORD *)a1 + 11) = v119;
            v122 = o_sqrtf_0((float)(v121 * v121) + (float)(v120 * v120)) + 0.5;
            if ( v113 )
            {
              v123 = 0;
              v123.m128_f32[0] = v122;
              v124 = (int)_mm_round_ss(v123, v123, 9).m128_f32[0];
LABEL_181:
              *((_DWORD *)a1 + 12) = v124;
LABEL_188:
              v138 = *((_DWORD *)a1 + 11);
              if ( v138 < 1 )
              {
                *((_DWORD *)a1 + 11) = 1;
                v138 = 1;
              }
              if ( v124 < 1 )
              {
                *((_DWORD *)a1 + 12) = 1;
                v124 = 1;
              }
              if ( v138 == 1 && v124 == 1 )
              {
                v227 = v232;
                v139 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v232, 12));
                v191 = _mm_cvtsi128_si32(_mm_srli_si128(v232, 4));
                v140 = _mm_cvtsi128_si32(_mm_srli_si128(v232, 8));
                v141 = _mm_cvtsi128_si32(v232);
              }
              else
              {
                v195[0] = v138 * (v232.m128i_i32[0] / v138);
                v227.m128i_i32[0] = v195[0];
                v191 = v124 * (v232.m128i_i32[1] / v124);
                v227.m128i_i32[1] = v191;
                v140 = v232.m128i_i32[0] % v138
                     + v232.m128i_i32[2]
                     + v138
                     - (v232.m128i_i32[0] % v138 + v232.m128i_i32[2]) % v138;
                v227.m128i_i32[2] = v140;
                v139 = (unsigned int)(v232.m128i_i32[1] % v124
                                    + v232.m128i_i32[3]
                                    + v124
                                    - (v232.m128i_i32[1] % v124 + v232.m128i_i32[3]) % v124);
                v141 = v195[0];
                v227.m128i_i32[3] = v232.m128i_i32[1] % v124
                                  + v232.m128i_i32[3]
                                  + v124
                                  - (v232.m128i_i32[1] % v124 + v232.m128i_i32[3]) % v124;
              }
              v194 = v139;
              v199 = v140;
              v228 = v141 / v138;
              v229 = v191 / v124;
              v230 = v140 / v138;
              v142 = (unsigned int)((int)v139 >> 31);
              LODWORD(v142) = (int)v139 % v124;
              v231 = (int)v139 / v124;
              if ( v192 )
              {
                v143 = (float)*((int *)a1 + 84);
                v144 = (__m128)COERCE_UNSIGNED_INT((float)v141);
                v144.m128_f32[0] = v144.m128_f32[0] / v143;
                if ( v113 )
                  v145 = (int)_mm_round_ss(v144, v144, 10).m128_f32[0];
                else
                  v145 = -(int)floor(COERCE_FLOAT(v144.m128_i32[0] ^ v19));
                v146 = _mm_cvtsi32_si128(*((_DWORD *)a1 + 85));
                v227.m128i_i32[0] = v145;
                v147 = _mm_cvtepi32_ps(v146).m128_f32[0];
                v148 = (__m128)COERCE_UNSIGNED_INT((float)v191);
                v148.m128_f32[0] = v148.m128_f32[0] / v147;
                if ( v113 )
                  v149 = (int)_mm_round_ss(v148, v148, 10).m128_f32[0];
                else
                  v149 = -(int)floor(COERCE_FLOAT(v148.m128_i32[0] ^ v19));
                v227.m128i_i32[1] = v149;
                v150 = (__m128)COERCE_UNSIGNED_INT((float)v199);
                v150.m128_f32[0] = v150.m128_f32[0] / v143;
                if ( v113 )
                  v151 = (int)_mm_round_ss(v150, v150, 10).m128_f32[0];
                else
                  v151 = -(int)floor(COERCE_FLOAT(v150.m128_i32[0] ^ v19));
                v227.m128i_i32[2] = v151;
                v152 = (__m128)COERCE_UNSIGNED_INT((float)v194);
                v152.m128_f32[0] = v152.m128_f32[0] / v147;
                if ( v113 )
                  v153 = (int)_mm_round_ss(v152, v152, 10).m128_f32[0];
                else
                  v153 = -(int)floor(COERCE_FLOAT(v152.m128_i32[0] ^ v19));
                v227.m128i_i32[3] = v153;
                v154 = (GpMatrix *)(a2 + 144);
                GpMatrix::Scale(a2 + 144, v142, v139, 1);
              }
              else
              {
                v154 = (GpMatrix *)(a2 + 144);
              }
              v155 = *(_DWORD *)(a2 + 160);
              v156 = *(_DWORD *)(a2 + 164);
              v157 = *(_DWORD *)(a2 + 168);
              v158 = *(_DWORD *)(a2 + 172);
              v159 = *(_DWORD *)(a2 + 176);
              v160 = *(_DWORD *)(a2 + 180);
              v224[0].x = v155;
              v224[0].y = v156;
              v224[1].x = v157;
              v224[1].y = v158;
              GpMatrix::Scale(v154, v142, v139, 1);
              v161 = *(_DWORD *)(a2 + 160);
              v162 = *(_DWORD *)(a2 + 164);
              v163 = *(_DWORD *)(a2 + 168);
              v194 = *(_DWORD *)(a2 + 172);
              v235 = *(_DWORD *)(a2 + 176);
              v237 = *(_DWORD *)(a2 + 180);
              *(_DWORD *)(a2 + 288) = 0;
              `vector constructor iterator'(&v279, 8u, 4u, (void *(*)(void *))PointF::PointF);
              v238 = &GpMatrix::`vftable';
              v240 = -1;
              v243 = 1065353216;
              v241 = 1065353216;
              v244 = 0;
              v242 = 0;
              v280 = (float)v229;
              v282 = (float)v229;
              v239 = 1952533809;
              v284 = (float)(v229 + v231);
              v286 = v284;
              v279 = (float)v228;
              v281 = (float)(v230 + v228);
              v283 = (float)v228;
              v285 = v281;
              DpContext::GetDeviceToWorld(a2, &v238);
              GpMatrix::Transform((GpMatrix *)&v238, (struct PointF *)&v279, 4);
              v164 = fminf(v279, v281);
              v165 = fminf(v283, v285);
              if ( v165 <= v164 )
              {
                v245 = v165;
                v164 = v165;
              }
              else
              {
                v245 = v164;
              }
              v166 = fminf(v280, v282);
              v167 = fminf(v284, v286);
              if ( v167 <= v166 )
              {
                v246 = v167;
                v166 = v167;
              }
              else
              {
                v246 = v166;
              }
              v168 = fmaxf(v279, v281);
              v169 = fmaxf(v283, v285);
              if ( v168 <= v169 )
                v168 = v169;
              v170 = fmaxf(v280, v282);
              v171 = fmaxf(v284, v286);
              v247 = v168 - v164;
              if ( v170 <= v171 )
                v170 = v171;
              v172 = *(void (__fastcall **)(__int64 *, __int64, int *, __m128i *))(*a1 + 160);
              v248 = v170 - v166;
              v172(a1, a2, &v228, &v227);
              v207 = DriverPrint::GetContextHdc((struct DpContext *)a2, v200);
              if ( v207 )
              {
                BufferDIB = EpScanDIB::CreateBufferDIB(
                              (__int64)v205,
                              (_OWORD *)a1 + 13,
                              (__int128 *)a1 + 14,
                              v103,
                              *((_DWORD *)a1 + 11),
                              *((_DWORD *)a1 + 12));
                if ( !BufferDIB )
                {
                  v195[0] = 0;
                  v199 = 0;
                  if ( v201 )
                    DriverPrint::SetupClipping(
                      (DriverPrint *)a1,
                      v207,
                      (struct DpContext *)a2,
                      (const struct GpRuntime::GpRect *)a4,
                      v195,
                      &v199,
                      0);
                  v75 = *((_DWORD *)a1 + 46) <= 0;
                  *((_DWORD *)a1 + 45) = 0;
                  if ( !v75 )
                  {
                    v174 = v194;
                    v175 = v103 & 0x1D;
                    v236 = v175;
                    do
                    {
                      if ( v175 )
                      {
                        DpClipRegion::DisableComplexClipping(
                          (DpClipRegion *)(a2 + 296),
                          (struct GpRuntime::GpRect *)(a1 + 26),
                          v173);
                        v176 = v235;
                        *(_DWORD *)(a2 + 288) = 0;
                        *(_DWORD *)(a2 + 176) = v176;
                        *(_DWORD *)(a2 + 180) = v237;
                        *(_DWORD *)(a2 + 160) = v161;
                        *(_DWORD *)(a2 + 164) = v162;
                        *(_DWORD *)(a2 + 168) = v163;
                        *(_DWORD *)(a2 + 172) = v174;
                        v177 = GpMatrix::ComputeComplexity((GpMatrix *)(a2 + 144));
                        *(_DWORD *)(v178 + 40) = v177;
                        EpScanDIB::SetRenderMode(v205, 0, (struct GpRuntime::GpRect *)(a1 + 26));
                        v95 = *(_DWORD *)a6 == 2;
                        v194 = 0;
                        if ( v95 && *((_DWORD *)a1 + 11) != 1 )
                        {
                          v194 = *(_DWORD *)(a6 + 364);
                          *(_DWORD *)(a6 + 364) = 1;
                        }
                        if ( v203 )
                          v179 = v203 + 3;
                        else
                          v179 = (void (__fastcall ***)(_QWORD, _QWORD))a6;
                        LODWORD(v190) = 1;
                        BufferDIB = DpDriver::FillRects(a1, a2, v200, &v228, v190, &v245, v179);
                        if ( *(_DWORD *)a6 == 2 && *((_DWORD *)a1 + 11) != 1 )
                          *(_DWORD *)(a6 + 364) = v194;
                        *(_DWORD *)(a2 + 392) = 0;
                        DpRegion::Set(a2 + 304, a2 + 352, 1);
                      }
                      *(_DWORD *)(a2 + 288) = 0;
                      *((_DWORD *)v154 + 4) = v155;
                      *((_DWORD *)v154 + 5) = v156;
                      *((_DWORD *)v154 + 6) = v157;
                      *((_DWORD *)v154 + 7) = v158;
                      *((_DWORD *)v154 + 8) = v159;
                      *((_DWORD *)v154 + 9) = v160;
                      *((_DWORD *)v154 + 10) = GpMatrix::ComputeComplexity(v154);
                      if ( BufferDIB )
                        break;
                      if ( (v103 & 0x62) != 0 )
                      {
                        if ( *(_DWORD *)a6 != 1 || (v180 = *((_DWORD *)a1 + 11), v180 == 1) )
                        {
                          v95 = *(_DWORD *)a6 == 2;
                          v191 = 0;
                          if ( v95 && *((_DWORD *)a1 + 11) != 1 )
                          {
                            v191 = *(_DWORD *)(a6 + 364);
                            *(_DWORD *)(a6 + 364) = 1;
                          }
                        }
                        else
                        {
                          *(_DWORD *)(a6 + 344) = v180;
                          v191 = 0;
                        }
                        DpClipRegion::SetBandBounds(
                          (DpClipRegion *)(a2 + 296),
                          (struct GpRuntime::GpRect *)(a1 + 28),
                          1);
                        EpScanDIB::SetRenderMode(v205, 1, (struct GpRuntime::GpRect *)(a1 + 28));
                        BufferDIB = DpDriver::FillPath(a1, a2, v200, a4, v204, a6);
                        if ( *(_DWORD *)a6 == 2 )
                        {
                          if ( *((_DWORD *)a1 + 11) != 1 )
                            *(_DWORD *)(a6 + 364) = v191;
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
                                    v207,
                                    a2,
                                    v200,
                                    a1 + 26,
                                    a1 + 28,
                                    v204);
                      if ( BufferDIB )
                        break;
                      *((_DWORD *)a1 + 53) += *((_DWORD *)a1 + 48);
                      *((_DWORD *)a1 + 57) += *((_DWORD *)a1 + 47);
                      ++*((_DWORD *)a1 + 45);
                      v175 = v236;
                    }
                    while ( *((_DWORD *)a1 + 45) < *((_DWORD *)a1 + 46) );
                  }
                  if ( v201 )
                    DriverPrint::RestoreClipping((DriverPrint *)a1, v207, v195[0], v199);
                  EpScanDIB::DestroyBufferDIB(v205);
                }
                DpContext::ReleaseHdc((DpContext *)a2, v207, 0);
              }
              else
              {
                v181 = *(_OWORD *)&v224[0].x;
                *(_DWORD *)(a2 + 288) = 0;
                *((_DWORD *)v154 + 8) = v159;
                *((_OWORD *)v154 + 1) = v181;
                *((_DWORD *)v154 + 9) = v160;
                *((_DWORD *)v154 + 10) = GpMatrix::ComputeComplexity(v154);
              }
              (*(void (__fastcall **)(__int64 *, __int64))(*a1 + 168))(a1, a2);
              if ( v192 )
              {
                v182 = v217;
                v183 = v218;
                v184 = v193;
                *(_DWORD *)(a2 + 288) = 0;
                *(float *)(a2 + 160) = v182;
                v185 = v220;
                *(_DWORD *)(a2 + 164) = v183;
                *(_DWORD *)(a2 + 168) = v219;
                v186 = v221;
                *(float *)(a2 + 172) = v185;
                v187 = v222;
                *(_DWORD *)(a2 + 152) = v184;
                v188 = v223;
                *(_DWORD *)(a2 + 176) = v186;
                *(_DWORD *)(a2 + 180) = v187;
                *(_DWORD *)(a2 + 184) = v188;
              }
              if ( v203 )
                (**v203)(v203, 1);
              *((_DWORD *)a1 + 11) = v197;
              *((_DWORD *)a1 + 12) = v196[0];
              return BufferDIB;
            }
            v125 = v122;
            goto LABEL_180;
          }
          goto LABEL_186;
        }
        if ( *(_DWORD *)a6 == 1 )
        {
          v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
          v126 = (__m128)*((unsigned int *)v200 + 5);
          v126.m128_f32[0] = v126.m128_f32[0] / 100.0;
          if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
          {
            v127 = (int)_mm_round_ss(v126, v126, 9).m128_f32[0];
          }
          else
          {
            v128 = floor(v126.m128_f32[0]);
            v107 = v200;
            v127 = (int)v128;
          }
          *((_DWORD *)a1 + 11) = v127;
          v129 = (__m128)*((unsigned int *)v107 + 6);
          v129.m128_f32[0] = v129.m128_f32[0] / 100.0;
          goto LABEL_177;
        }
        if ( v191 )
        {
          if ( v191 == 1 )
          {
            v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v135 = (__m128)*((unsigned int *)v200 + 5);
            if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
            {
              v136 = (int)_mm_round_ss(v135, v135, 9).m128_f32[0];
            }
            else
            {
              v137 = floor(v135.m128_f32[0]);
              v108 = v196[0];
              v136 = (int)v137;
            }
            *((_DWORD *)a1 + 11) = v136;
            goto LABEL_187;
          }
          if ( v191 == 2 )
          {
            v129 = (__m128)*((unsigned int *)v200 + 6);
            v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
LABEL_177:
            if ( v113 )
            {
              v124 = (int)_mm_round_ss(v129, v129, 9).m128_f32[0];
              goto LABEL_181;
            }
            v125 = v129.m128_f32[0];
LABEL_180:
            v124 = (int)floor(v125);
            goto LABEL_181;
          }
          if ( v191 == 3 || (unsigned int)(v191 - 4) <= 1 )
          {
            v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
            v130 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[2]);
            v130.m128_f32[0] = v130.m128_f32[0] * 0.00390625;
            if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
              v131 = (int)_mm_round_ss(v130, v130, 10).m128_f32[0];
            else
              v131 = -(int)floor(COERCE_FLOAT(v130.m128_i32[0] ^ v19));
            *((_DWORD *)a1 + 11) = v131;
            v132 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[3]);
            v132.m128_f32[0] = v132.m128_f32[0] * 0.00390625;
            if ( v113 )
              v133 = (int)_mm_round_ss(v132, v132, 10).m128_f32[0];
            else
              v133 = -(int)floor(COERCE_FLOAT(v132.m128_i32[0] ^ v19));
            v95 = v191 == 3;
            *((_DWORD *)a1 + 12) = v133;
            if ( !v95 )
            {
              v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a6 - 24) + 64LL))(a6 - 24);
              v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
              v203 = (void (__fastcall ***)(_QWORD, _QWORD))v134;
              if ( v134 )
              {
                *(_DWORD *)(v134 + 440) = 1065772646;
                *(_QWORD *)(v134 + 16) = 0;
              }
            }
            v124 = *((_DWORD *)a1 + 12);
            goto LABEL_188;
          }
        }
LABEL_186:
        v113 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
LABEL_187:
        v124 = v108;
        goto LABEL_188;
      }
      if ( *((_DWORD *)a1 + 42) == (_DWORD)v20 )
      {
        v193 = 1952533809;
        if ( *((_DWORD *)a1 + 41) == (_DWORD)v20 )
          v103 = 49;
        else
          v103 = 1;
        goto LABEL_141;
      }
      v103 = 5;
LABEL_140:
      v193 = 1952533809;
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
          v201 = (int)v20;
          goto LABEL_140;
        }
        v103 = 1;
LABEL_137:
        v201 = 1;
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
0x1800f3b84  mov     rax, rsp
0x1800f3b87  push    rbp
0x1800f3b88  push    rbx
0x1800f3b89  push    rsi
0x1800f3b8a  push    rdi
0x1800f3b8b  push    r12
0x1800f3b8d  push    r13
0x1800f3b8f  push    r14
0x1800f3b91  push    r15
0x1800f3b93  lea     rbp, [rax-948h]
0x1800f3b9a  sub     rsp, 0A08h
0x1800f3ba1  movaps  xmmword ptr [rax-58h], xmm6
0x1800f3ba5  movaps  xmmword ptr [rax-68h], xmm7
0x1800f3ba9  movaps  xmmword ptr [rax-78h], xmm8
0x1800f3bae  movaps  xmmword ptr [rax-88h], xmm9
0x1800f3bb6  movaps  xmmword ptr [rax-98h], xmm10
0x1800f3bbe  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800f3bc6  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800f3bce  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800f3bd6  movaps  xmmword ptr [rax-0D8h], xmm14
0x1800f3bde  movaps  xmmword ptr [rax-0E8h], xmm15
0x1800f3be6  mov     rax, cs:__security_cookie
0x1800f3bed  xor     rax, rsp
0x1800f3bf0  mov     [rbp+940h+var_F0], rax
0x1800f3bf7  mov     rax, [rbp+940h+arg_20]
0x1800f3bfe  mov     rsi, rcx
0x1800f3c01  mov     ecx, [r9+0Ch]
0x1800f3c05  mov     r14, rdx
0x1800f3c08  mov     edx, [r9]
0x1800f3c0b  mov     r13, r9
0x1800f3c0e  mov     rbx, [rbp+940h+arg_28]
0x1800f3c15  xorps   xmm0, xmm0
0x1800f3c18  mov     [rbp+940h+var_990], rax
0x1800f3c1c  lea     rax, [rbp+940h+var_8C0]
0x1800f3c23  mov     [rbp+940h+var_9B8], r8
0x1800f3c27  mov     r8d, [r9+4]
0x1800f3c2b  add     ecx, r8d
0x1800f3c2e  mov     r9d, [r9+8]
0x1800f3c32  mov     [rsp+0A40h+var_A18], rax
0x1800f3c37  add     r9d, edx
0x1800f3c3a  mov     dword ptr [rsp+0A40h+var_A20], ecx
0x1800f3c3e  lea     rcx, [r14+130h]
0x1800f3c45  movdqa  [rbp+940h+var_8C0], xmm0
0x1800f3c4d  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1800f3c52  test    eax, eax
0x1800f3c54  jz      loc_1800F5A6E
0x1800f3c5a  movss   xmm13, cs:__real@3f800000
0x1800f3c63  lea     rdi, [rbx-18h]
0x1800f3c67  mov     rax, [rdi]
0x1800f3c6a  lea     r15, [r14+90h]
0x1800f3c71  xorps   xmm9, xmm9
0x1800f3c75  movss   [rbp+940h+var_92C], xmm13
0x1800f3c7b  xor     r12d, r12d
0x1800f3c7e  movss   [rbp+940h+var_938], xmm13
0x1800f3c84  mov     rdx, r15
0x1800f3c87  movss   [rbp+940h+var_924], xmm9
0x1800f3c8d  mov     rax, [rax+70h]
0x1800f3c91  mov     rcx, rdi
0x1800f3c94  movss   [rbp+940h+var_928], xmm9
0x1800f3c9a  movss   [rbp+940h+var_930], xmm9
0x1800f3ca0  movss   [rbp+940h+var_934], xmm9
0x1800f3ca6  mov     [rbp+940h+var_920], r12d
0x1800f3caa  mov     [rbp+940h+var_998], r12
0x1800f3cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3cb3  movss   xmm8, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800f3cbc  or      r9d, 0FFFFFFFFh
0x1800f3cc0  xor     r11d, r11d
0x1800f3cc3  mov     [rsp+0A40h+var_A00], eax
0x1800f3cc7  mov     ecx, eax
0x1800f3cc9  mov     r10d, 74614D31h
0x1800f3ccf  test    eax, eax
0x1800f3cd1  jz      loc_1800F4BB4
0x1800f3cd7  mov     qword ptr [rsp+0A40h+var_9D8], r11
0x1800f3cdc  xorps   xmm1, xmm1
0x1800f3cdf  mov     edi, r11d
0x1800f3ce2  movups  xmm0, xmmword ptr [r13+0]
0x1800f3ce7  movups  [rbp+940h+var_8B0], xmm1
0x1800f3cee  movdqu  [rsp+0A40h+var_9D8+8], xmm0
0x1800f3cf4  movups  [rbp+940h+var_8A0], xmm1
0x1800f3cfb  sub     ecx, 1
0x1800f3cfe  jz      loc_1800F45D7
0x1800f3d04  sub     ecx, 1
0x1800f3d07  jz      loc_1800F45CD
0x1800f3d0d  sub     ecx, 1
0x1800f3d10  jz      short loc_1800F3D29
0x1800f3d12  sub     ecx, 1
0x1800f3d15  jz      loc_1800F44D5
0x1800f3d1b  cmp     ecx, 1
0x1800f3d1e  jz      loc_1800F44D5
0x1800f3d24  jmp     loc_1800F45E7
0x1800f3d29  movss   xmm0, dword ptr [rbx+2Ch]
0x1800f3d2e  lea     rdi, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1800f3d35  mov     eax, [rbx+30h]
0x1800f3d38  lea     rdx, [rbp+940h+var_968]; struct GpMatrix *
0x1800f3d3c  movss   xmm11, dword ptr [rbx+18h]
0x1800f3d42  lea     rcx, [rbp+940h+var_968]; struct GpMatrix *
0x1800f3d46  movss   xmm12, dword ptr [rbx+1Ch]
0x1800f3d4c  mov     r8, r15; struct GpMatrix *
0x1800f3d4f  movss   xmm13, dword ptr [rbx+20h]
0x1800f3d55  movss   xmm14, dword ptr [rbx+24h]
0x1800f3d5b  movss   xmm15, dword ptr [rbx+28h]
0x1800f3d61  movss   dword ptr [rbp+940h+var_958], xmm11
0x1800f3d67  movss   dword ptr [rbp+940h+var_958+4], xmm12
0x1800f3d6d  movss   [rbp+940h+var_950], xmm13
0x1800f3d73  movss   dword ptr [rbp+940h+var_94C], xmm14
0x1800f3d79  movss   dword ptr [rbp+940h+var_94C+4], xmm15
0x1800f3d7f  movss   [rsp+0A40h+var_9E0], xmm0
0x1800f3d85  movss   dword ptr [rbp+940h+var_944], xmm0
0x1800f3d8a  mov     [rbp+940h+var_968], rdi
0x1800f3d8e  mov     [rbp+940h+var_95C], r9d
0x1800f3d92  mov     [rbp+940h+var_960], r10d
0x1800f3d96  mov     [rsp+0A40h+var_9F0], eax
0x1800f3d9a  mov     dword ptr [rbp+940h+var_944+4], eax
0x1800f3d9d  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x1800f3da2  cmp     [rsi+28h], r11d
0x1800f3da6  jnz     loc_1800F44CC
0x1800f3dac  cmp     [rsi+0A4h], r11d
0x1800f3db3  jnz     short loc_1800F3DBF
0x1800f3db5  cmp     [rsi+4Ch], r11d
0x1800f3db9  jz      loc_1800F44CC
0x1800f3dbf  test    byte ptr [rbp+940h+var_944+4], 8
0x1800f3dc3  jnz     loc_1800F44CC
0x1800f3dc9  movdqu  xmm0, xmmword ptr [rbx+3Ch]
0x1800f3dce  mov     [rbp+940h+var_834], r9d
0x1800f3dd5  lea     rcx, [rbp+940h+var_7E0]; void *
0x1800f3ddc  mov     [rbp+940h+var_7C4], r9d
0x1800f3de3  mov     [rbp+940h+var_874], r9d
0x1800f3dea  mov     [rbp+940h+var_95C], r9d
0x1800f3dee  mov     [rbp+940h+var_804], r9d
0x1800f3df5  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1800f3dfc  mov     [rbp+940h+var_840], rdi
0x1800f3e03  mov     [rbp+940h+var_7D0], rdi
0x1800f3e0a  mov     [rbp+940h+var_880], rdi
0x1800f3e11  mov     [rbp+940h+var_968], rdi
0x1800f3e15  mov     [rbp+940h+var_810], rdi
0x1800f3e1c  mov     edi, 2
0x1800f3e21  mov     r8d, edi; unsigned __int64
0x1800f3e24  mov     [rbp+940h+var_864], 3F800000h
0x1800f3e2f  mov     [rbp+940h+var_870], 3F800000h
0x1800f3e3a  mov     [rbp+940h+var_85C], r11
0x1800f3e41  lea     edx, [rdi+6]; unsigned __int64
0x1800f3e44  mov     [rbp+940h+var_868], r11d
0x1800f3e4b  mov     [rbp+940h+var_878], r10d
0x1800f3e52  mov     [rbp+940h+var_94C], 3F800000h
0x1800f3e5a  mov     [rbp+940h+var_958], 3F800000h
0x1800f3e62  mov     [rbp+940h+var_944], r11
0x1800f3e66  mov     [rbp+940h+var_950], r11d
0x1800f3e6a  mov     [rbp+940h+var_960], r10d
0x1800f3e6e  mov     [rbp+940h+var_7F4], 3F800000h
0x1800f3e79  mov     [rbp+940h+var_800], 3F800000h
0x1800f3e84  mov     [rbp+940h+var_7EC], r11
0x1800f3e8b  mov     [rbp+940h+var_7F8], r11d
0x1800f3e92  mov     [rbp+940h+var_808], r10d
0x1800f3e99  mov     [rbp+940h+var_980], r11
0x1800f3e9d  mov     [rbp+940h+var_988], r11
0x1800f3ea1  movups  xmmword ptr [rbp+940h+var_918.x], xmm0
0x1800f3ea5  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800f3eaa  movups  xmm0, xmmword ptr [rbx+0F8h]
0x1800f3eb1  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1800f3eb8  mov     r8d, edi; unsigned __int64
0x1800f3ebb  lea     edx, [rdi+6]; unsigned __int64
0x1800f3ebe  lea     rcx, [rbp+940h+var_9A8]; void *
0x1800f3ec2  movups  [rbp+940h+var_7E0], xmm0
0x1800f3ec9  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800f3ece  mov     r9d, edi; int
0x1800f3ed1  lea     r8, [rbp+940h+var_9A8]; struct PointF *
0x1800f3ed5  lea     rdx, [rbp+940h+var_7E0]; struct PointF *
0x1800f3edc  mov     rcx, r15; this
0x1800f3edf  call    ?Transform@GpMatrix@@QEBAXPEBVPointF@@PEAV2@H@Z; GpMatrix::Transform(PointF const *,PointF *,int)
0x1800f3ee4  lea     rdx, [rbp+940h+var_9A8+8]; struct PointF *
0x1800f3ee8  lea     rcx, [rbp+940h+var_9A8]; struct PointF *
0x1800f3eec  call    ?IsClosePointF@@YAHAEBVPointF@@0@Z; IsClosePointF(PointF const &,PointF const &)
0x1800f3ef1  xor     r11d, r11d
0x1800f3ef4  test    eax, eax
0x1800f3ef6  jnz     loc_1800F44CC
0x1800f3efc  movss   xmm10, dword ptr [rbp+940h+var_9A8]
0x1800f3f02  movss   xmm7, dword ptr [rbp+940h+var_9A8+8]
0x1800f3f07  movss   xmm9, dword ptr [rbp+940h+var_9A8+4]
0x1800f3f0d  movss   xmm6, dword ptr [rbp+940h+var_9A8+0Ch]
0x1800f3f12  cvtps2pd xmm0, xmm10
0x1800f3f16  cvtps2pd xmm2, xmm7
0x1800f3f19  cvtps2pd xmm1, xmm9
0x1800f3f1d  subsd   xmm2, xmm0
0x1800f3f21  cvtps2pd xmm0, xmm6
0x1800f3f24  mulsd   xmm2, xmm2
0x1800f3f28  subsd   xmm0, xmm1
0x1800f3f2c  mulsd   xmm0, xmm0
0x1800f3f30  addsd   xmm0, xmm2; X
0x1800f3f34  call    sqrt
0x1800f3f39  xorps   xmm1, xmm1
0x1800f3f3c  movss   dword ptr [rbp+940h+var_978+4], xmm9
0x1800f3f42  cvtsd2ss xmm1, xmm0
0x1800f3f46  subss   xmm6, xmm9
0x1800f3f4b  addss   xmm1, xmm10
0x1800f3f50  subss   xmm7, xmm10
0x1800f3f55  cvtps2pd xmm0, xmm6
0x1800f3f58  movss   dword ptr [rbp+940h+var_978], xmm1
0x1800f3f5d  cvtps2pd xmm1, xmm7
0x1800f3f60  call    _o_atan2_0
0x1800f3f65  mulsd   xmm0, cs:__real@4066800000000000
0x1800f3f6d  lea     r15d, [rdi-1]
0x1800f3f71  lea     rcx, [rbp+940h+var_968]
0x1800f3f75  mov     r9d, r15d
0x1800f3f78  movaps  xmm7, xmm9
0x1800f3f7c  movaps  xmm6, xmm10
0x1800f3f80  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x1800f3f87  xorps   xmm8, xmm8
0x1800f3f8b  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1800f3f92  movaps  xmm2, xmm7
0x1800f3f95  divsd   xmm0, cs:__real@400921fb54442d18
0x1800f3f9d  movaps  xmm1, xmm6
0x1800f3fa0  cvtsd2ss xmm8, xmm0
0x1800f3fa5  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800f3faa  lea     rcx, [rbp+940h+var_968]
0x1800f3fae  mov     r8d, r15d
0x1800f3fb1  movaps  xmm1, xmm8
0x1800f3fb5  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800f3fbc  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x1800f3fc1  mov     r9d, r15d
0x1800f3fc4  lea     rcx, [rbp+940h+var_968]
0x1800f3fc8  movaps  xmm2, xmm9
0x1800f3fcc  movaps  xmm1, xmm10
0x1800f3fd0  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800f3fd5  movaps  xmm2, xmm7
0x1800f3fd8  lea     rcx, [rbp+940h+var_810]
0x1800f3fdf  movaps  xmm1, xmm6
0x1800f3fe2  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800f3fe7  movaps  xmm1, xmm8
0x1800f3feb  lea     rcx, [rbp+940h+var_810]
0x1800f3ff2  mov     r8d, r15d
0x1800f3ff5  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x1800f3ffa  mov     r9d, r15d
0x1800f3ffd  lea     rcx, [rbp+940h+var_810]
0x1800f4004  movaps  xmm2, xmm9
0x1800f4008  movaps  xmm1, xmm10
0x1800f400c  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1800f4011  movups  xmm0, xmmword ptr [r14+0A0h]
0x1800f4019  mov     eax, [r14+98h]
0x1800f4020  lea     r8, [rbp+940h+var_968]; struct GpMatrix *
0x1800f4024  movss   xmm1, dword ptr [r14+0B4h]
0x1800f402d  lea     rdx, [rbp+940h+var_840]; struct GpMatrix *
0x1800f4034  movups  [rbp+940h+var_830], xmm0
0x1800f403b  lea     rcx, [rbp+940h+var_840]; struct GpMatrix *
0x1800f4042  mov     [rbp+940h+var_838], eax
0x1800f4048  movss   xmm0, dword ptr [r14+0B0h]
0x1800f4051  mov     eax, [r14+0B8h]
0x1800f4058  movss   [rbp+940h+var_820], xmm0
0x1800f4060  movss   [rbp+940h+var_81C], xmm1
0x1800f4068  mov     [rbp+940h+var_818], eax
0x1800f406e  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x1800f4073  movups  xmm0, [rbp+940h+var_830]
0x1800f407a  mov     ecx, [rbp+940h+var_838]
0x1800f4080  mov     [rbp+940h+var_7C8], ecx
0x1800f4086  movups  [rbp+940h+var_7C0], xmm0
0x1800f408d  movss   xmm0, [rbp+940h+var_820]
0x1800f4095  movss   [rbp+940h+var_7B0], xmm0
0x1800f409d  movss   xmm1, [rbp+940h+var_81C]
0x1800f40a5  lea     rcx, [rbp+940h+var_7D0]
0x1800f40ac  mov     eax, [rbp+940h+var_818]
0x1800f40b2  movss   [rbp+940h+var_7AC], xmm1
0x1800f40ba  mov     [rbp+940h+var_7A8], eax
0x1800f40c0  call    ?Invert@GpMatrix@@QEAA?AW4Status@@XZ; GpMatrix::Invert(void)
0x1800f40c5  xor     r11d, r11d
0x1800f40c8  test    eax, eax
0x1800f40ca  jnz     loc_1800F44C3
0x1800f40d0  mov     rdi, [rbp+940h+var_990]
0x1800f40d4  lea     rdx, [rbp+940h+var_840]; struct GpMatrix *
0x1800f40db  mov     rcx, rdi; this
0x1800f40de  call    ?Transform@GpPath@@QEAAXPEBVGpMatrix@@@Z; GpPath::Transform(GpMatrix const *)
0x1800f40e3  mov     rcx, [rdi]
0x1800f40e6  lea     rdx, [rbp+940h+var_988]
0x1800f40ea  xorps   xmm0, xmm0
0x1800f40ed  xor     r9d, r9d
0x1800f40f0  movss   dword ptr [rsp+0A40h+var_A18], xmm0
0x1800f40f6  xor     r8d, r8d
0x1800f40f9  movss   dword ptr [rsp+0A40h+var_A20], xmm0
0x1800f40ff  mov     rax, [rcx+68h]
0x1800f4103  mov     rcx, rdi
0x1800f4106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f410b  lea     rdx, [rbp+940h+var_7D0]; struct GpMatrix *
0x1800f4112  mov     rcx, rdi; this
0x1800f4115  call    ?Transform@GpPath@@QEAAXPEBVGpMatrix@@@Z; GpPath::Transform(GpMatrix const *)
0x1800f411a  movss   xmm4, dword ptr [rbp+940h+var_980]
0x1800f411f  xor     eax, eax
0x1800f4121  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800f4127  movss   xmm8, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800f4130  mov     qword ptr [rsp+0A40h+var_9D8+8], rax
0x1800f4135  jz      short loc_1800F4146
0x1800f4137  movaps  xmm0, xmm4
0x1800f413a  roundss xmm0, xmm0, 0Ah
0x1800f4140  cvttss2si eax, xmm0
0x1800f4144  jmp     short loc_1800F415C
0x1800f4146  xorps   xmm4, xmm8
0x1800f414a  xorps   xmm0, xmm0
0x1800f414d  cvtss2sd xmm0, xmm4; X
0x1800f4151  call    floor
0x1800f4156  cvttsd2si eax, xmm0
0x1800f415a  neg     eax
0x1800f415c  movss   xmm7, dword ptr [rbp+940h+var_988+4]
0x1800f4161  lea     rcx, [rbp+940h+var_810]
  ... truncated ...
```
