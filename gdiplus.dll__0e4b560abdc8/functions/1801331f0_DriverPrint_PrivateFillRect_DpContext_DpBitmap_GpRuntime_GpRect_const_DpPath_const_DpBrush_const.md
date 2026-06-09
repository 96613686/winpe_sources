# DriverPrint::PrivateFillRect(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpPath const *,DpBrush const *)

- ea: `0x1801331f0`
- end: `0x18013511e`
- name: `?PrivateFillRect@DriverPrint@@AEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpPath@@PEBUDpBrush@@@Z`
- size: `7982`
- prototype: `__int64 __fastcall(__int64, __int64, struct DpBitmap *, unsigned int *, GpPath *, __int64)`
- caller_count: `2`
- callee_count: `53`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180131730`
- `0x180131a70`

## callees

- `0x18000e90c`
- `0x180011960`
- `0x1800126d0`
- `0x18001319c`
- `0x18001af90`
- `0x18001b584`
- `0x18001b784`
- `0x18001b8b0`
- `0x18001c214`
- `0x18001c288`
- `0x18001f504`
- `0x180024d18`
- `0x180029450`
- `0x180039550`
- `0x180040ee0`
- `0x18004bf00`
- `0x180063ff8`
- `0x180065140`
- `0x180081974`
- `0x1800937a4`
- `0x180094b64`
- `0x180099258`
- `0x1800a20c0`
- `0x1800adcb0`
- `0x1800b34f4`
- `0x1800c02e8`
- `0x1800d4550`
- `0x1800d5f10`
- `0x1800dc7c8`
- `0x1800dcdf4`
- `0x1800e4fc0`
- `0x1800e740c`
- `0x1800e9380`
- `0x1800ea050`
- `0x1800ea080`
- `0x1800ea0c8`
- `0x1800ea0d4`
- `0x1800fdf74`
- `0x180126558`
- `0x180126920`
- `0x180127034`
- `0x180131524`
- `0x180132694`
- `0x1801326f8`
- `0x1801328a8`
- `0x180132930`
- `0x180132b78`
- `0x180132ff4`
- `0x1801331f0`
- `0x180135220`

## import_xrefs

- `GDI32!SetROP2` at `0x180133af2`
- `GDI32!SetROP2` at `0x180133b19`
- `GDI32!SetROP2` at `0x18013407d`
- `GDI32!SetROP2` at `0x1801340a4`
- `GDI32!SetROP2` at `0x180133af2`
- `GDI32!SetROP2` at `0x180133b19`
- `GDI32!SetROP2` at `0x18013407d`
- `GDI32!SetROP2` at `0x1801340a4`
- `GDI32!GetStockObject` at `0x180133ac4`
- `GDI32!GetStockObject` at `0x180133fe8`
- `GDI32!GetStockObject` at `0x180133ac4`
- `GDI32!GetStockObject` at `0x180133fe8`

## pseudocode

```c
__int64 __fastcall DriverPrint::PrivateFillRect(
        __int64 a1,
        __int64 a2,
        struct DpBitmap *a3,
        unsigned int *a4,
        GpPath *a5,
        __int64 a6)
{
  unsigned int v7; // edx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 result; // rax
  GpTexture *v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // xmm15_4
  __int64 (__fastcall *v17)(__int64, __int64); // rax
  int v18; // xmm13_4
  float v19; // xmm14_4
  __int64 v20; // r12
  __int32 v21; // eax
  __int64 v22; // r8
  int v23; // xmm8_4
  __int64 v24; // r9
  unsigned int v25; // r11d
  int v26; // edi
  __int128 v27; // xmm0
  int v28; // xmm0_4
  int v29; // eax
  int v30; // xmm11_4
  int v31; // xmm12_4
  int v32; // xmm13_4
  int v33; // xmm14_4
  int v34; // xmm15_4
  int v35; // r10d
  __m128i v36; // xmm0
  int v37; // eax
  float v38; // xmm10_4
  float v39; // xmm1_4
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // r8
  int v51; // eax
  int v52; // xmm1_4
  unsigned int v53; // eax
  int v54; // eax
  GpPath *v55; // rdi
  __int64 v56; // rdx
  __int64 v57; // r8
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  GpPathGradient *v62; // r15
  int v63; // eax
  unsigned int v64; // r12d
  int v65; // eax
  CopyOnWriteBitmap *ContextHdc; // rax
  GpBitmap *v67; // rbx
  HDC v68; // r15
  __int64 v69; // rax
  HBRUSH StockObject; // rax
  HBRUSH v71; // rdi
  int v72; // ebx
  unsigned int IsRectangular; // eax
  int v74; // ecx
  int v75; // eax
  bool v76; // cc
  signed int v77; // ecx
  int v78; // eax
  signed int v79; // ecx
  int v80; // eax
  CopyOnWriteBitmap *v81; // rax
  HDC v82; // r15
  __m128i v83; // xmm0
  float v84; // xmm1_4
  __m128i v85; // xmm0
  float v86; // xmm1_4
  __int64 v87; // rax
  unsigned int v88; // ebx
  unsigned int v89; // ecx
  void (__fastcall *v90)(__int64, HDC, __int64, unsigned int *, unsigned int *, __int32 *, _DWORD); // rax
  GpPath *v91; // rbx
  HBRUSH AlphaMaskBrush; // rax
  HBRUSH v93; // rdi
  int v94; // ebx
  bool v95; // zf
  unsigned int v96; // ecx
  LONG v97; // r8d
  LONG v98; // ecx
  unsigned int v99; // ecx
  int v100; // ecx
  int v101; // eax
  unsigned int v102; // ecx
  unsigned int v103; // r15d
  int v104; // eax
  int v105; // xmm0_4
  unsigned int v106; // eax
  struct DpBitmap *v107; // rdx
  struct GpBitmap *Bitmap; // rax
  __int64 v109; // rcx
  __int64 v110; // rdx
  __int64 v111; // r8
  bool v112; // di
  int v113; // eax
  int v114; // xmm1_4
  unsigned int v115; // eax
  float v116; // xmm0_4
  __m128 v117; // xmm1
  int v118; // eax
  float v119; // xmm0_4
  float v120; // xmm1_4
  float v121; // xmm0_4
  __m128 v122; // xmm1
  double v123; // xmm0_8
  __m128 v124; // xmm0
  int v125; // eax
  double v126; // xmm0_8
  __m128 v127; // xmm0
  __m128 v128; // xmm0
  int v129; // eax
  __m128 v130; // xmm0
  int v131; // eax
  __int64 v132; // rax
  int v133; // r11d
  int v134; // r10d
  __int64 v135; // r8
  int v136; // ecx
  int v137; // r9d
  int v138; // eax
  int v139; // eax
  __int64 v140; // rdx
  float v141; // xmm7_4
  __m128 v142; // xmm0
  int v143; // eax
  __m128i v144; // xmm6
  float v145; // xmm6_4
  __m128 v146; // xmm0
  int v147; // eax
  __m128 v148; // xmm0
  int v149; // eax
  __m128 v150; // xmm0
  int v151; // eax
  __int64 v152; // rdi
  __int128 v153; // xmm7
  int v154; // xmm8_4
  int v155; // xmm9_4
  __int128 v156; // xmm10
  int v157; // xmm11_4
  int v158; // xmm12_4
  float v159; // xmm5_4
  float v160; // xmm0_4
  float v161; // xmm1_4
  float v162; // xmm3_4
  float v163; // xmm4_4
  float v164; // xmm6_4
  float v165; // xmm0_4
  float v166; // xmm2_4
  void (__fastcall *v167)(__int64, __int64, int *, __m128i *); // rax
  unsigned int BufferDIB; // eax
  __int32 v169; // r8d
  int v170; // eax
  int v171; // eax
  EpScanDIB *v172; // rcx
  __int64 v173; // rax
  int v174; // eax
  unsigned int v175; // ecx
  unsigned int v176; // eax
  int v177; // eax
  __int64 v178; // rcx
  int v179; // xmm0_4
  int v180; // eax
  int v181; // xmm0_4
  unsigned int v182; // eax
  int v183; // [rsp+28h] [rbp-E0h]
  unsigned int v184; // [rsp+28h] [rbp-E0h]
  unsigned int v185; // [rsp+48h] [rbp-C0h] BYREF
  __int32 v186; // [rsp+4Ch] [rbp-BCh] BYREF
  int v187; // [rsp+50h] [rbp-B8h] BYREF
  int v188; // [rsp+58h] [rbp-B0h]
  unsigned int v189; // [rsp+5Ch] [rbp-ACh]
  int v190; // [rsp+60h] [rbp-A8h]
  HDC v191[2]; // [rsp+68h] [rbp-A0h] BYREF
  int v192[4]; // [rsp+78h] [rbp-90h] BYREF
  void (__fastcall ***v193)(_QWORD, __int64); // [rsp+88h] [rbp-80h] BYREF
  GpBitmap *v194; // [rsp+90h] [rbp-78h] BYREF
  __int128 v195; // [rsp+98h] [rbp-70h] BYREF
  struct DpBitmap *v196; // [rsp+A8h] [rbp-60h]
  unsigned int v197; // [rsp+B0h] [rbp-58h]
  EpScanDIB *v198; // [rsp+B8h] [rbp-50h] BYREF
  float v199; // [rsp+C0h] [rbp-48h] BYREF
  float v200; // [rsp+C4h] [rbp-44h]
  void **v201; // [rsp+C8h] [rbp-40h] BYREF
  int v202; // [rsp+D0h] [rbp-38h]
  int v203; // [rsp+D4h] [rbp-34h]
  __int128 v204; // [rsp+D8h] [rbp-30h]
  int v205; // [rsp+E8h] [rbp-20h]
  int v206; // [rsp+ECh] [rbp-1Ch]
  unsigned int v207; // [rsp+F0h] [rbp-18h]
  GpPath *v208; // [rsp+F8h] [rbp-10h]
  void **v209; // [rsp+100h] [rbp-8h] BYREF
  int v210; // [rsp+108h] [rbp+0h]
  int v211; // [rsp+10Ch] [rbp+4h]
  int v212; // [rsp+110h] [rbp+8h]
  int v213; // [rsp+114h] [rbp+Ch]
  int v214; // [rsp+118h] [rbp+10h]
  int v215; // [rsp+11Ch] [rbp+14h]
  int v216; // [rsp+120h] [rbp+18h]
  int v217; // [rsp+124h] [rbp+1Ch]
  unsigned int v218; // [rsp+128h] [rbp+20h]
  int v219; // [rsp+130h] [rbp+28h]
  int v220; // [rsp+134h] [rbp+2Ch]
  int v221; // [rsp+138h] [rbp+30h]
  int v222; // [rsp+13Ch] [rbp+34h]
  __m128i v223; // [rsp+148h] [rbp+40h] BYREF
  int v224; // [rsp+158h] [rbp+50h] BYREF
  int v225; // [rsp+15Ch] [rbp+54h]
  int v226; // [rsp+160h] [rbp+58h]
  int v227; // [rsp+164h] [rbp+5Ch]
  __m128i v228; // [rsp+168h] [rbp+60h] BYREF
  __int128 v229; // [rsp+178h] [rbp+70h] BYREF
  __int128 v230; // [rsp+188h] [rbp+80h]
  int v231; // [rsp+198h] [rbp+90h]
  float v232; // [rsp+1A0h] [rbp+98h] BYREF
  float v233; // [rsp+1A4h] [rbp+9Ch]
  float v234; // [rsp+1A8h] [rbp+A0h]
  float v235; // [rsp+1ACh] [rbp+A4h]
  void **v236; // [rsp+1B0h] [rbp+A8h] BYREF
  int v237; // [rsp+1B8h] [rbp+B0h]
  int v238; // [rsp+1BCh] [rbp+B4h]
  __int128 v239; // [rsp+1C0h] [rbp+B8h]
  int v240; // [rsp+1D0h] [rbp+C8h]
  int v241; // [rsp+1D4h] [rbp+CCh]
  unsigned int v242; // [rsp+1D8h] [rbp+D0h]
  struct tagPOINT v243[2]; // [rsp+1E0h] [rbp+D8h] BYREF
  LONG x; // [rsp+1F0h] [rbp+E8h]
  unsigned int v245; // [rsp+1F4h] [rbp+ECh]
  void **v246; // [rsp+1F8h] [rbp+F0h] BYREF
  int v247; // [rsp+200h] [rbp+F8h]
  int v248; // [rsp+204h] [rbp+FCh]
  int v249; // [rsp+208h] [rbp+100h]
  int v250; // [rsp+20Ch] [rbp+104h]
  int v251; // [rsp+210h] [rbp+108h]
  int v252; // [rsp+214h] [rbp+10Ch]
  int v253; // [rsp+218h] [rbp+110h]
  int v254; // [rsp+21Ch] [rbp+114h]
  unsigned int v255; // [rsp+220h] [rbp+118h]
  __int128 v256; // [rsp+228h] [rbp+120h] BYREF
  void **v257; // [rsp+238h] [rbp+130h] BYREF
  int v258; // [rsp+240h] [rbp+138h]
  int v259; // [rsp+244h] [rbp+13Ch]
  int v260; // [rsp+248h] [rbp+140h]
  int v261; // [rsp+24Ch] [rbp+144h]
  int v262; // [rsp+250h] [rbp+148h]
  int v263; // [rsp+254h] [rbp+14Ch]
  int v264; // [rsp+258h] [rbp+150h]
  int v265; // [rsp+25Ch] [rbp+154h]
  unsigned int v266; // [rsp+260h] [rbp+158h]
  void **v267; // [rsp+268h] [rbp+160h] BYREF
  int v268; // [rsp+270h] [rbp+168h]
  int v269; // [rsp+274h] [rbp+16Ch]
  int v270; // [rsp+278h] [rbp+170h]
  int v271; // [rsp+27Ch] [rbp+174h]
  int v272; // [rsp+280h] [rbp+178h]
  int v273; // [rsp+284h] [rbp+17Ch]
  int v274; // [rsp+288h] [rbp+180h]
  int v275; // [rsp+28Ch] [rbp+184h]
  int v276; // [rsp+290h] [rbp+188h]
  int v277; // [rsp+298h] [rbp+190h] BYREF
  __int64 v278; // [rsp+29Ch] [rbp+194h]
  int v279; // [rsp+2A4h] [rbp+19Ch]
  int v280; // [rsp+2A8h] [rbp+1A0h]
  int v281; // [rsp+2B8h] [rbp+1B0h]
  __int64 v282; // [rsp+300h] [rbp+1F8h]
  int v283; // [rsp+310h] [rbp+208h]
  _DWORD v284[308]; // [rsp+458h] [rbp+350h] BYREF
  float v285; // [rsp+928h] [rbp+820h] BYREF
  float v286; // [rsp+92Ch] [rbp+824h]
  float v287; // [rsp+930h] [rbp+828h]
  float v288; // [rsp+934h] [rbp+82Ch]
  float v289; // [rsp+938h] [rbp+830h]
  float v290; // [rsp+93Ch] [rbp+834h]
  float v291; // [rsp+940h] [rbp+838h]
  float v292; // [rsp+944h] [rbp+83Ch]

  v7 = a4[3];
  v189 = 0;
  v208 = a5;
  v196 = a3;
  v10 = a4[1];
  v11 = *a4 + a4[2];
  v183 = v10 + v7;
  v12 = *a4;
  v228 = 0;
  result = DpRegion::GetRectVisibility(a2 + 304, v12, v10, v11, v183, &v228);
  if ( !(_DWORD)result )
    return result;
  v14 = (GpTexture *)(a6 - 24);
  v15 = *(_QWORD *)(a6 - 24);
  v197 = 0;
  v16 = 0;
  v187 = LODWORD(FLOAT_1_0);
  *(float *)&v188 = FLOAT_1_0;
  v17 = *(__int64 (__fastcall **)(__int64, __int64))(v15 + 112);
  v222 = 0;
  v18 = LODWORD(FLOAT_1_0);
  v185 = 0;
  v19 = FLOAT_1_0;
  v221 = 0;
  v20 = 0;
  v220 = 0;
  v219 = 1952533809;
  v21 = v17(a6 - 24, a2 + 144);
  v23 = _xmm;
  v24 = 0xFFFFFFFFLL;
  v25 = 0;
  v186 = v21;
  if ( v21 )
  {
    v194 = 0;
    v26 = 0;
    v27 = *(_OWORD *)a4;
    v229 = 0;
    v195 = v27;
    v230 = 0;
    if ( v21 == 1 )
    {
      DWORD2(v195) = 1;
    }
    else
    {
      if ( v21 != 2 )
      {
        if ( v21 == 3 )
        {
          v28 = *(_DWORD *)(a6 + 44);
          v29 = *(_DWORD *)(a6 + 48);
          v30 = *(_DWORD *)(a6 + 24);
          v31 = *(_DWORD *)(a6 + 28);
          v32 = *(_DWORD *)(a6 + 32);
          v33 = *(_DWORD *)(a6 + 36);
          v34 = *(_DWORD *)(a6 + 40);
          v212 = v30;
          v213 = v31;
          v214 = v32;
          v215 = v33;
          v216 = v34;
          v192[0] = v28;
          v217 = v28;
          v209 = &GpMatrix::`vftable';
          v210 = 1952533809;
          v211 = -1;
          v190 = v29;
          v218 = v29;
          GpMatrix::MultiplyMatrix(
            (struct GpMatrix *)&v209,
            (const struct GpMatrix *)&v209,
            (const struct GpMatrix *)(a2 + 144));
          if ( *(_DWORD *)(a1 + 40) == v25
            && (*(_DWORD *)(a1 + 164) != v25 || *(_DWORD *)(a1 + 76) != v25)
            && (v218 & 8) == 0 )
          {
            v36 = _mm_loadu_si128((const __m128i *)(a6 + 60));
            v206 &= v25;
            v205 &= v25;
            DWORD2(v204) &= v25;
            DWORD1(v204) &= v25;
            v241 &= v25;
            v240 &= v25;
            DWORD2(v239) &= v25;
            DWORD1(v239) &= v25;
            v265 &= v25;
            v264 &= v25;
            v262 &= v25;
            v261 &= v25;
            v217 &= v25;
            v216 &= v25;
            v214 &= v25;
            v213 &= v25;
            v254 &= v25;
            v253 &= v25;
            v251 &= v25;
            v250 &= v25;
            HIDWORD(v191[1]) &= v25;
            LODWORD(v191[1]) &= v25;
            HIDWORD(v191[0]) &= v25;
            LODWORD(v191[0]) &= v25;
            HIDWORD(v193) &= v25;
            LODWORD(v193) = v25 & (unsigned int)v193;
            v203 = v24;
            v238 = v24;
            v259 = v24;
            v211 = v24;
            v248 = v24;
            v201 = &GpMatrix::`vftable';
            v236 = &GpMatrix::`vftable';
            v257 = &GpMatrix::`vftable';
            v209 = &GpMatrix::`vftable';
            v246 = &GpMatrix::`vftable';
            HIDWORD(v204) = 1065353216;
            LODWORD(v204) = 1065353216;
            v207 = v25;
            v202 = v35;
            HIDWORD(v239) = 1065353216;
            LODWORD(v239) = 1065353216;
            v242 = v25;
            v237 = v35;
            v263 = 1065353216;
            v260 = 1065353216;
            v266 = v25;
            v258 = v35;
            v215 = 1065353216;
            v212 = 1065353216;
            v218 = v25;
            v210 = v35;
            v252 = 1065353216;
            v249 = 1065353216;
            v255 = v25;
            v247 = v35;
            *(__m128i *)&v243[0].x = v36;
            `vector constructor iterator'(&v256, 8u, 2u, (void *(*)(void *))PointF::PointF);
            v256 = *(_OWORD *)(a6 + 248);
            `vector constructor iterator'(&v198, 8u, 2u, (void *(*)(void *))PointF::PointF);
            GpMatrix::Transform((GpMatrix *)(a2 + 144), (const struct PointF *)&v256, (struct PointF *)&v198, 2);
            v37 = IsClosePointF((const struct PointF *)&v198, (const struct PointF *)&v199);
            v25 = 0;
            if ( !v37 )
            {
              v38 = *(float *)&v198;
              HIDWORD(v193) = HIDWORD(v198);
              v39 = sqrt(
                      (v200 - *((float *)&v198 + 1)) * (v200 - *((float *)&v198 + 1))
                    + (v199 - *(float *)&v198) * (v199 - *(float *)&v198));
              *(float *)&v193 = v39 + v38;
              o_atan2_0();
              GpMatrix::Translate(&v209, v40, v41, 1);
              GpMatrix::Rotate(&v209, v42, 1);
              GpMatrix::Translate(&v209, v43, v44, 1);
              GpMatrix::Translate(&v246, v45, v46, v47);
              GpMatrix::Rotate(&v246, v48, 1);
              GpMatrix::Translate(&v246, v49, v50, 1);
              v51 = *(_DWORD *)(a2 + 152);
              v52 = *(_DWORD *)(a2 + 180);
              v204 = *(_OWORD *)(a2 + 160);
              v202 = v51;
              v53 = *(_DWORD *)(a2 + 184);
              v205 = *(_DWORD *)(a2 + 176);
              v206 = v52;
              v207 = v53;
              GpMatrix::MultiplyMatrix(
                (struct GpMatrix *)&v201,
                (const struct GpMatrix *)&v201,
                (const struct GpMatrix *)&v209);
              v237 = v202;
              v239 = v204;
              v240 = v205;
              v241 = v206;
              v242 = v207;
              v54 = GpMatrix::Invert(&v236);
              v25 = 0;
              if ( !v54 )
              {
                v55 = v208;
                GpPath::Transform(v208, (const struct GpMatrix *)&v201);
                (*(void (__fastcall **)(GpPath *, HDC *, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v55 + 104LL))(
                  v55,
                  v191,
                  0,
                  0,
                  0,
                  0);
                GpPath::Transform(v55, (const struct GpMatrix *)&v236);
                v23 = _xmm;
                *(_QWORD *)&v195 = 0;
                if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
                  v58 = (int)_mm_round_ss((__m128)LODWORD(v191[1]), (__m128)LODWORD(v191[1]), 10).m128_f32[0];
                else
                  v58 = -(int)floor(COERCE_FLOAT(LODWORD(v191[1]) ^ _xmm));
                *((_QWORD *)&v195 + 1) = v58 | 0x100000000LL;
                GpMatrix::Translate(&v246, v56, v57, 0);
                GpMatrix::Translate(&v257, v59, v60, v61);
                v62 = (GpPathGradient *)(a6 - 24);
                v63 = GpLineGradient::ChangeLinePoints(a6 - 24, &v198, &v193, *(unsigned int *)(a6 + 104));
                v25 = 0;
                if ( !v63 )
                {
                  v64 = GpBitmap::CreateBitmapAndFillWithBrush(
                          *(_DWORD *)(a2 + 48),
                          *(_DWORD *)(a2 + 52),
                          (const struct GpMatrix *)&v257,
                          &v195,
                          (GpTexture *)(a6 - 24),
                          &v194);
                  v65 = v190;
                  *(_OWORD *)(a6 + 60) = *(_OWORD *)&v243[0].x;
                  *(_DWORD *)(a6 + 16) = 1952533809;
                  *(_DWORD *)(a6 + 44) = v192[0];
                  *(_DWORD *)(a6 + 24) = v30;
                  *(_DWORD *)(a6 + 28) = v31;
                  *(_DWORD *)(a6 + 32) = v32;
                  *(_DWORD *)(a6 + 36) = v33;
                  *(_DWORD *)(a6 + 40) = v34;
                  *(_DWORD *)(a6 + 48) = v65;
                  *(_OWORD *)(a6 + 248) = v256;
                  if ( !v64 )
                  {
                    ContextHdc = DriverPrint::GetContextHdc((struct DpContext *)a2, v196);
                    v67 = v194;
                    v68 = (HDC)ContextHdc;
                    if ( ContextHdc )
                    {
                      v64 = GpBitmap::LockBits(v194, 0, 1u, 0x26200Au, (__int64)&v229);
                      if ( !v64 )
                      {
                        v69 = *(_QWORD *)a1;
                        v185 = 0;
                        v186 = 0;
                        (*(void (__fastcall **)(__int64, HDC, __int64, unsigned int *, unsigned int *, __int32 *, _DWORD))(v69 + 40))(
                          a1,
                          v68,
                          a2,
                          a4,
                          &v185,
                          &v186,
                          0);
                        if ( *(_DWORD *)(a1 + 164)
                          && *((_DWORD *)v55 + 26) == 4
                          && (unsigned int)DpPath::IsRectangular(v55) )
                        {
                          (*(void (__fastcall **)(__int64, HDC, __int64, GpPath *))(*(_QWORD *)a1 + 208LL))(
                            a1,
                            v68,
                            a2,
                            v55);
                          v64 = DriverPrint::PrivateFillDiagonalGradient(
                                  (DriverPrint *)a1,
                                  v68,
                                  (__int64)&v229,
                                  15728673,
                                  0,
                                  (GpMatrix *)&v246,
                                  *((float *)&v191[1] + 1));
                          (*(void (__fastcall **)(__int64, HDC))(*(_QWORD *)a1 + 216LL))(a1, v68);
                        }
                        else
                        {
                          v64 = DriverPrint::PrivateFillDiagonalGradient(
                                  (DriverPrint *)a1,
                                  v68,
                                  (__int64)&v229,
                                  5898313,
                                  1,
                                  (GpMatrix *)&v246,
                                  *((float *)&v191[1] + 1));
                          if ( !v64 )
                          {
                            ConvertPathToGdi::ConvertPathToGdi(
                              (ConvertPathToGdi *)&v277,
                              v55,
                              (struct GpMatrix *)(a2 + 144),
                              2u,
                              0);
                            if ( v277 == 1198932785 )
                            {
                              if ( *(_DWORD *)(a1 + 164) )
                                StockObject = (HBRUSH)GetStockObject(v64 + 4);
                              else
                                StockObject = DriverPrint::GetAlphaMaskBrush(
                                                (DriverPrint *)a1,
                                                *(unsigned __int8 *)(a1 + 176),
                                                1);
                              v71 = StockObject;
                              v72 = SetROP2(v68, 9);
                              LODWORD(v71) = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v277, v68, v71);
                              SetROP2(v68, v72);
                              v64 = (_DWORD)v71 == 0;
                              if ( (_DWORD)v71 )
                                v64 = DriverPrint::PrivateFillDiagonalGradient(
                                        (DriverPrint *)a1,
                                        v68,
                                        (__int64)&v229,
                                        5898313,
                                        1,
                                        (GpMatrix *)&v246,
                                        *((float *)&v191[1] + 1));
                              v67 = v194;
                            }
                            ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v277);
                          }
                        }
                        (*(void (__fastcall **)(__int64, HDC, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(
                          a1,
                          v68,
                          v185,
                          (unsigned int)v186);
                        GpBitmap::UnlockBits(v67, (__int64)&v229);
                      }
                      DpContext::ReleaseHdc((HWND *)a2, v68, 0);
                    }
                    (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v67 + 56LL))(v67);
                  }
                  return v64;
                }
                v18 = v187;
                v19 = *(float *)&v188;
                v16 = v185;
                goto LABEL_41;
              }
              v23 = _xmm;
            }
          }
          v16 = v185;
          v19 = *(float *)&v188;
          v18 = v187;
        }
        else if ( (unsigned int)(v21 - 4) >= 2 )
        {
          goto LABEL_71;
        }
        v62 = (GpPathGradient *)(a6 - 24);
LABEL_41:
        IsRectangular = v25;
        LOBYTE(IsRectangular) = *(_DWORD *)a6 == 4;
        if ( *(_DWORD *)(a1 + 164) != v25 || *(_DWORD *)(a1 + 76) == v25 || (v26 = 1, *(_DWORD *)(a1 + 40) != v25) )
          v26 = v25;
        if ( *(_DWORD *)a6 == 3 )
          IsRectangular = GpPathGradient::IsRectangular(v62);
        v22 = a4[2];
        if ( IsRectangular )
        {
          v74 = 256;
          v75 = 256;
          if ( (int)v22 < 256 )
            v75 = a4[2];
          v76 = (int)a4[3] < 256;
          DWORD2(v195) = v75;
          if ( v76 )
            v74 = a4[3];
          HIDWORD(v195) = v74;
        }
        else
        {
          v24 = 1024;
          v77 = ((int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 1)
              + ((unsigned int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 31)
              + 256;
          v78 = v77;
          if ( v77 >= (int)v22 )
            v78 = a4[2];
          if ( v78 >= 1024 )
          {
            DWORD2(v195) = 1024;
          }
          else
          {
            if ( v77 < (int)v22 )
              LODWORD(v22) = ((int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 1)
                           + ((unsigned int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 31)
                           + 256;
            DWORD2(v195) = v22;
          }
          v22 = a4[3];
          v79 = ((int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 1)
              + ((unsigned int)((unsigned __int64)(1717986919LL * ((int)v22 - 256)) >> 32) >> 31)
              + 256;
          v80 = v79;
          if ( v79 >= (int)v22 )
            v80 = a4[3];
          if ( v80 >= 1024 )
          {
            HIDWORD(v195) = 1024;
          }
          else
          {
            if ( v79 < (int)v22 )
              v22 = (unsigned int)v79;
            HIDWORD(v195) = v22;
          }
        }
        goto LABEL_71;
      }
      HIDWORD(v195) = 1;
    }
    LOBYTE(v26) = *(_DWORD *)(a1 + 40) == 0;
LABEL_71:
    if ( *(_DWORD *)(a1 + 164) != v25 || *(_DWORD *)(a1 + 40) == 1 || v26 )
    {
      v81 = DriverPrint::GetContextHdc((struct DpContext *)a2, v196);
      v25 = 0;
      v82 = (HDC)v81;
      if ( v81 )
      {
        v198 = 0;
        v211 = -1;
        v217 = 0;
        v216 = 0;
        v214 = 0;
        v213 = 0;
        *(_QWORD *)&v195 = 0;
        v209 = &GpMatrix::`vftable';
        v215 = 1065353216;
        v212 = 1065353216;
        v218 = 0;
        v210 = 1952533809;
        v199 = (float)SDWORD2(v195);
        v83 = _mm_cvtsi32_si128(*a4);
        v200 = (float)SHIDWORD(v195);
        v84 = (float)(int)a4[1];
        LODWORD(v191[0]) = _mm_cvtepi32_ps(v83).m128_u32[0];
        v85 = _mm_cvtsi32_si128(a4[2]);
        *((float *)v191 + 1) = v84;
        v86 = (float)(int)a4[3];
        LODWORD(v191[1]) = _mm_cvtepi32_ps(v85).m128_u32[0];
        *((float *)&v191[1] + 1) = v86;
        GpMatrix::InferAffineMatrix(&v209, &v198, v191);
        GpMatrix::MultiplyMatrix(
          (struct GpMatrix *)&v209,
          (const struct GpMatrix *)(a2 + 144),
          (const struct GpMatrix *)&v209);
        v87 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a6 - 24) + 64LL))(a6 - 24);
        v193 = (void (__fastcall ***)(_QWORD, __int64))v87;
        v20 = v87;
        if ( v87 )
        {
          if ( !*(_DWORD *)(a1 + 164) && *(_DWORD *)(a1 + 40) == 1 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 168LL))(v87);
            *(_DWORD *)(a1 + 164) = 1;
          }
          if ( (unsigned int)(v186 - 4) <= 1 )
          {
            *(_QWORD *)(v20 + 16) = 0;
            *(_DWORD *)(v20 + 440) = 1065772646;
          }
          v64 = GpBitmap::CreateBitmapAndFillWithBrush(
                  *(_DWORD *)(a2 + 48),
                  *(_DWORD *)(a2 + 52),
                  (const struct GpMatrix *)&v209,
                  &v195,
                  (GpTexture *)v20,
                  &v194);
          (**v193)(v193, 1);
          v189 = v64;
          if ( !v64 )
          {
            v189 = 0;
            if ( v194 )
            {
              v88 = 6;
              v89 = 6;
              if ( *(_DWORD *)(a1 + 40) != 1 )
                v89 = 2;
              v197 = v89;
              if ( (unsigned int)GpBitmap::LockBits(v194, 0, 1u, 0x26200Au, (__int64)&v229) )
                goto LABEL_111;
              v90 = *(void (__fastcall **)(__int64, HDC, __int64, unsigned int *, unsigned int *, __int32 *, _DWORD))(*(_QWORD *)a1 + 40LL);
              v185 = 0;
              v186 = 0;
              v90(a1, v82, a2, a4, &v185, &v186, 0);
              if ( !v26 || HIDWORD(v195) != 1 && DWORD2(v195) != 1 )
              {
                (*(void (__fastcall **)(__int64, HDC, __int64, GpPath *))(*(_QWORD *)a1 + 208LL))(a1, v82, a2, v208);
                DpBitmap::DpBitmap((DpBitmap *)&v277, 0);
                GpBitmap::InitializeSurfaceForGdipBitmap(v194, (__int64)&v277, v229, SDWORD1(v229));
                v282 = v230;
                v283 = DWORD2(v229);
                v278 = v229;
                v95 = *(_DWORD *)(a1 + 40) == 1;
                v279 = 2498570;
                v281 = 3;
                v280 = 3 * DWORD1(v229) * v229;
                if ( !v95 )
                  v88 = 2;
                if ( v26 )
                  v96 = (*(unsigned __int8 *)(a1 + 72) + (unsigned int)*(unsigned __int8 *)(a1 + 73)) >> 1;
                else
                  v96 = -1;
                ConvertBitmapToGdi::ConvertBitmapToGdi(
                  (ConvertBitmapToGdi *)v284,
                  v82,
                  (struct DpBitmap *)&v277,
                  (const struct GpRuntime::GpRect *)&v195,
                  v88,
                  v96,
                  1);
                v64 = 1;
                if ( v284[0] == 1198932785 )
                {
                  v97 = a4[1];
                  v98 = *a4 + a4[2];
                  v243[0].x = *a4;
                  v243[1].x = v98;
                  v99 = a4[3];
                  v243[0].y = v97;
                  v245 = v97 + v99;
                  v243[1].y = v97;
                  x = v243[0].x;
                  v64 = ConvertBitmapToGdi::StretchBlt((ConvertBitmapToGdi *)v284, v82, v243, 0, v184) == 0;
                }
                (*(void (__fastcall **)(__int64, HDC))(*(_QWORD *)a1 + 216LL))(a1, v82);
                ConvertBitmapToGdi::~ConvertBitmapToGdi((ConvertBitmapToGdi *)v284);
                DpBitmap::~DpBitmap((DpBitmap *)&v277);
                goto LABEL_110;
              }
              v91 = v208;
              if ( *(_DWORD *)(a1 + 164) )
              {
                if ( *((_DWORD *)v208 + 26) != 4 || !(unsigned int)DpPath::IsRectangular(v208) )
                {
LABEL_92:
                  v64 = DriverPrint::PrivateFillGradient(
                          a1,
                          v82,
                          (const struct BitmapData *)&v229,
                          (__int64)&v195,
                          (int *)a4,
                          0x660046u,
                          1);
                  if ( !v64 )
                  {
                    ConvertPathToGdi::ConvertPathToGdi(
                      (ConvertPathToGdi *)&v277,
                      v91,
                      (struct GpMatrix *)(a2 + 144),
                      v197,
                      0);
                    if ( v277 == 1198932785 )
                    {
                      if ( *(_DWORD *)(a1 + 164) == v64 )
                        AlphaMaskBrush = DriverPrint::GetAlphaMaskBrush(
                                           (DriverPrint *)a1,
                                           *(unsigned __int8 *)(a1 + 176),
                                           1);
                      else
                        AlphaMaskBrush = (HBRUSH)GetStockObject(v64 + 4);
                      v93 = AlphaMaskBrush;
                      v94 = SetROP2(v82, 9);
                      LODWORD(v93) = ConvertPathToGdi::Fill((ConvertPathToGdi *)&v277, v82, v93);
                      SetROP2(v82, v94);
                      v64 = (_DWORD)v93 == 0;
                      if ( (_DWORD)v93 )
                        v64 = DriverPrint::PrivateFillGradient(
                                a1,
                                v82,
                                (const struct BitmapData *)&v229,
                                (__int64)&v195,
                                (int *)a4,
                                0x660046u,
                                1);
                    }
                    ConvertPathToGdi::~ConvertPathToGdi((ConvertPathToGdi *)&v277);
                  }
                  goto LABEL_110;
                }
              }
              else if ( *(_DWORD *)(a1 + 76) )
              {
                goto LABEL_92;
              }
              (*(void (__fastcall **)(__int64, HDC, __int64, GpPath *))(*(_QWORD *)a1 + 208LL))(a1, v82, a2, v91);
              v64 = DriverPrint::PrivateFillGradient(
                      a1,
                      v82,
                      (const struct BitmapData *)&v229,
                      (__int64)&v195,
                      (int *)a4,
                      0xCC0020u,
                      0);
              (*(void (__fastcall **)(__int64, HDC))(*(_QWORD *)a1 + 216LL))(a1, v82);
LABEL_110:
              (*(void (__fastcall **)(__int64, HDC, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(
                a1,
                v82,
                v185,
                (unsigned int)v186);
              GpBitmap::UnlockBits(v194, (__int64)&v229);
LABEL_111:
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v194 + 56LL))(v194);
              DpContext::ReleaseHdc((HWND *)a2, v82, 0);
              return v64;
            }
          }
          v20 = 0;
        }
        else
        {
          v189 = 3;
        }
        DpContext::ReleaseHdc((HWND *)a2, v82, 0);
        v25 = 0;
      }
    }
    v14 = (GpTexture *)(a6 - 24);
  }
  v100 = *(_DWORD *)(a1 + 40);
  v188 = v25;
  if ( !v100 )
  {
    if ( *(_DWORD *)(a1 + 160) == v25 )
    {
      if ( *(_DWORD *)(a1 + 168) == v25 )
      {
        if ( *(_DWORD *)(a1 + 164) == v25 )
        {
          v103 = 67;
LABEL_137:
          v185 = v25;
          goto LABEL_138;
        }
        v103 = 1;
LABEL_135:
        v185 = 1;
        goto LABEL_138;
      }
      v103 = 5;
    }
    else
    {
      v103 = *(_DWORD *)(a1 + 164) != 0 ? 2 : 66;
    }
    if ( *(_DWORD *)(a1 + 164) == v25 && *(_DWORD *)(a1 + 168) == v25 )
      goto LABEL_137;
    goto LABEL_135;
  }
  if ( v100 != 1 )
    return 6;
  v101 = *(_DWORD *)(a1 + 160);
  v102 = v25;
  LOBYTE(v102) = v101 == 0;
  v185 = v102;
  if ( v101 )
  {
    v103 = *(_DWORD *)(a1 + 164) != 0 ? 2 : 66;
    if ( *(_DWORD *)(a1 + 336) != 1 || *(_DWORD *)(a1 + 340) != 1 )
    {
      v104 = *(_DWORD *)(a2 + 152);
      v19 = *(float *)(a2 + 160);
      v18 = *(_DWORD *)(a2 + 172);
      v16 = *(_DWORD *)(a2 + 176);
      v220 = *(_DWORD *)(a2 + 164);
      v221 = *(_DWORD *)(a2 + 168);
      v105 = *(_DWORD *)(a2 + 180);
      v219 = v104;
      v106 = *(_DWORD *)(a2 + 184);
      v222 = v105;
      v188 = 1;
      v197 = v106;
    }
  }
  else if ( *(_DWORD *)(a1 + 168) == v25 )
  {
    v103 = *(_DWORD *)(a1 + 164) != 0 ? 1 : 49;
  }
  else
  {
    v103 = 5;
  }
LABEL_138:
  v107 = v196;
  v198 = (EpScanDIB *)*((_QWORD *)v196 + 16);
  LODWORD(v193) = *(_DWORD *)(a1 + 44);
  LODWORD(v194) = *(_DWORD *)(a1 + 48);
  if ( *(_DWORD *)a6 != 2 )
  {
    if ( *(_DWORD *)a6 == 1 )
    {
      v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v124 = (__m128)*((unsigned int *)v196 + 5);
      v124.m128_f32[0] = v124.m128_f32[0] / 100.0;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      {
        v125 = (int)_mm_round_ss(v124, v124, 9).m128_f32[0];
      }
      else
      {
        v126 = floor(v124.m128_f32[0]);
        v107 = v196;
        v125 = (int)v126;
      }
      *(_DWORD *)(a1 + 44) = v125;
      v127 = (__m128)*((unsigned int *)v107 + 6);
      v127.m128_f32[0] = v127.m128_f32[0] / 100.0;
      if ( v112 )
      {
        v122 = v127;
        goto LABEL_183;
      }
    }
    else
    {
      if ( !v186 )
        goto LABEL_173;
      if ( v186 == 1 )
      {
        v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
        if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
          v139 = (int)_mm_round_ss((__m128)*((unsigned int *)v196 + 5), (__m128)*((unsigned int *)v196 + 5), 9).m128_f32[0];
        else
          v139 = (int)floor(*((float *)v196 + 5));
        *(_DWORD *)(a1 + 44) = v139;
        goto LABEL_174;
      }
      if ( v186 != 2 )
      {
        if ( v186 == 3 || (unsigned int)(v186 - 4) <= 1 )
        {
          v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
          v128 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[2]);
          v128.m128_f32[0] = v128.m128_f32[0] * 0.00390625;
          if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
            v129 = (int)_mm_round_ss(v128, v128, 10).m128_f32[0];
          else
            v129 = -(int)floor(COERCE_FLOAT(v128.m128_i32[0] ^ v23));
          *(_DWORD *)(a1 + 44) = v129;
          v130 = (__m128)COERCE_UNSIGNED_INT((float)(int)a4[3]);
          v130.m128_f32[0] = v130.m128_f32[0] * 0.00390625;
          if ( v112 )
            v131 = (int)_mm_round_ss(v130, v130, 10).m128_f32[0];
          else
            v131 = -(int)floor(COERCE_FLOAT(v130.m128_i32[0] ^ v23));
          v95 = v186 == 3;
          *(_DWORD *)(a1 + 48) = v131;
          if ( v95 )
            goto LABEL_174;
          v132 = (*(__int64 (__fastcall **)(__int64, struct DpBitmap *, __int64, __int64))(*(_QWORD *)(a6 - 24) + 64LL))(
                   a6 - 24,
                   v107,
                   v22,
                   v24);
          v20 = v132;
          if ( v132 )
          {
            *(_DWORD *)(v132 + 440) = 1065772646;
            *(_QWORD *)(v132 + 16) = 0;
          }
        }
        goto LABEL_173;
      }
      v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      {
        v122 = (__m128)*((unsigned int *)v196 + 6);
        goto LABEL_183;
      }
      v127.m128_i32[0] = *((_DWORD *)v196 + 6);
    }
    v123 = v127.m128_f32[0];
    goto LABEL_186;
  }
  Bitmap = GpTexture::GetBitmap(v14);
  if ( Bitmap )
  {
    v109 = *(_QWORD *)Bitmap;
    v191[0] = 0;
    (*(void (__fastcall **)(struct GpBitmap *, HDC *))(v109 + 368))(Bitmap, v191);
    v203 = -1;
    v206 = 0;
    v205 = 0;
    *(_QWORD *)((char *)&v204 + 4) = 0;
    v207 = 0;
    v95 = (*(_BYTE *)(a6 + 360) & 1) == 0;
    v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v201 = &GpMatrix::`vftable';
    HIDWORD(v204) = 1065353216;
    LODWORD(v204) = 1065353216;
    v202 = 1952533809;
    if ( v95 )
    {
      v113 = *(_DWORD *)(a2 + 152);
      v114 = *(_DWORD *)(a2 + 180);
      v204 = *(_OWORD *)(a2 + 160);
      v202 = v113;
      v115 = *(_DWORD *)(a2 + 184);
      v205 = *(_DWORD *)(a2 + 176);
      v206 = v114;
      v207 = v115;
    }
    else
    {
      if ( !Feature_GdiPlusOptimizations_Misc_IsEnabled )
        floor((float)(*((float *)v196 + 6) / 100.0));
      if ( !v112 )
        floor((float)(*((float *)v196 + 5) / 100.0));
      GpMatrix::Scale(&v201, v110, v111, 0);
    }
    GpMatrix::MultiplyMatrix(
      (struct GpMatrix *)&v201,
      (const struct GpMatrix *)(a6 + 8),
      (const struct GpMatrix *)&v201);
    *(_OWORD *)v191 = _xmm;
    GpMatrix::VectorTransform((GpMatrix *)&v201, (struct PointF *)v191, 2);
    v116 = o_sqrtf_0((float)(*((float *)v191 + 1) * *((float *)v191 + 1)) + (float)(*(float *)v191 * *(float *)v191))
         + 0.5;
    if ( v112 )
    {
      v117 = 0;
      v117.m128_f32[0] = v116;
      v118 = (int)_mm_round_ss(v117, v117, 9).m128_f32[0];
    }
    else
    {
      v118 = (int)floor(v116);
    }
    v119 = *((float *)&v191[1] + 1);
    v120 = *(float *)&v191[1];
    *(_DWORD *)(a1 + 44) = v118;
    v121 = o_sqrtf_0((float)(v119 * v119) + (float)(v120 * v120)) + 0.5;
    if ( v112 )
    {
      v122 = 0;
      v122.m128_f32[0] = v121;
LABEL_183:
      v138 = (int)_mm_round_ss(v122, v122, 9).m128_f32[0];
LABEL_187:
      *(_DWORD *)(a1 + 48) = v138;
      goto LABEL_174;
    }
    v123 = v121;
LABEL_186:
    v138 = (int)floor(v123);
    goto LABEL_187;
  }
LABEL_173:
  v112 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
LABEL_174:
  v133 = *(_DWORD *)(a1 + 44);
  if ( v133 < 1 )
  {
    *(_DWORD *)(a1 + 44) = 1;
    v133 = 1;
  }
  v134 = *(_DWORD *)(a1 + 48);
  if ( v134 < 1 )
  {
    *(_DWORD *)(a1 + 48) = 1;
    v134 = 1;
  }
  if ( v133 == 1 && v134 == 1 )
  {
    v223 = v228;
    v135 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v228, 12));
    v186 = _mm_cvtsi128_si32(_mm_srli_si128(v228, 4));
    v136 = _mm_cvtsi128_si32(_mm_srli_si128(v228, 8));
    v137 = _mm_cvtsi128_si32(v228);
  }
  else
  {
    v192[0] = v133 * (v228.m128i_i32[0] / v133);
    v223.m128i_i32[0] = v192[0];
    v186 = v134 * (v228.m128i_i32[1] / v134);
    v223.m128i_i32[1] = v186;
    v136 = v228.m128i_i32[0] % v133 + v228.m128i_i32[2] + v133 - (v228.m128i_i32[0] % v133 + v228.m128i_i32[2]) % v133;
    v223.m128i_i32[2] = v136;
    v135 = (unsigned int)(v228.m128i_i32[1] % v134
                        + v228.m128i_i32[3]
                        + v134
                        - (v228.m128i_i32[1] % v134 + v228.m128i_i32[3]) % v134);
    v137 = v192[0];
    v223.m128i_i32[3] = v228.m128i_i32[1] % v134
                      + v228.m128i_i32[3]
                      + v134
                      - (v228.m128i_i32[1] % v134 + v228.m128i_i32[3]) % v134;
  }
  v190 = v135;
  v187 = v136;
  v224 = v137 / v133;
  v225 = v186 / v134;
  v226 = v136 / v133;
  v140 = (unsigned int)((int)v135 >> 31);
  LODWORD(v140) = (int)v135 % v134;
  v227 = (int)v135 / v134;
  if ( *(float *)&v188 == 0.0 )
  {
    v152 = a2 + 144;
  }
  else
  {
    v141 = (float)*(int *)(a1 + 336);
    v142 = (__m128)COERCE_UNSIGNED_INT((float)v137);
    v142.m128_f32[0] = v142.m128_f32[0] / v141;
    if ( v112 )
      v143 = (int)_mm_round_ss(v142, v142, 10).m128_f32[0];
    else
      v143 = -(int)floor(COERCE_FLOAT(v142.m128_i32[0] ^ v23));
    v144 = _mm_cvtsi32_si128(*(_DWORD *)(a1 + 340));
    v223.m128i_i32[0] = v143;
    v145 = _mm_cvtepi32_ps(v144).m128_f32[0];
    v146 = (__m128)COERCE_UNSIGNED_INT((float)v186);
    v146.m128_f32[0] = v146.m128_f32[0] / v145;
    if ( v112 )
      v147 = (int)_mm_round_ss(v146, v146, 10).m128_f32[0];
    else
      v147 = -(int)floor(COERCE_FLOAT(v146.m128_i32[0] ^ v23));
    v223.m128i_i32[1] = v147;
    v148 = (__m128)COERCE_UNSIGNED_INT((float)v187);
    v148.m128_f32[0] = v148.m128_f32[0] / v141;
    if ( v112 )
      v149 = (int)_mm_round_ss(v148, v148, 10).m128_f32[0];
    else
      v149 = -(int)floor(COERCE_FLOAT(v148.m128_i32[0] ^ v23));
    v223.m128i_i32[2] = v149;
    v150 = (__m128)COERCE_UNSIGNED_INT((float)v190);
    v150.m128_f32[0] = v150.m128_f32[0] / v145;
    if ( v112 )
      v151 = (int)_mm_round_ss(v150, v150, 10).m128_f32[0];
    else
      v151 = -(int)floor(COERCE_FLOAT(v150.m128_i32[0] ^ v23));
    v223.m128i_i32[3] = v151;
    v152 = a2 + 144;
    GpMatrix::Scale(a2 + 144, v140, v135, 1);
  }
  v153 = *(_OWORD *)(a2 + 160);
  v154 = *(_DWORD *)(a2 + 176);
  v155 = *(_DWORD *)(a2 + 180);
  GpMatrix::Scale(v152, v140, v135, 1);
  v156 = *(_OWORD *)(a2 + 160);
  v157 = *(_DWORD *)(a2 + 176);
  v158 = *(_DWORD *)(a2 + 180);
  *(_DWORD *)(a2 + 288) = 0;
  `vector constructor iterator'(&v285, 8u, 4u, (void *(*)(void *))PointF::PointF);
  v269 = -1;
  v275 = 0;
  v274 = 0;
  v272 = 0;
  v271 = 0;
  v276 = 0;
  v267 = &GpMatrix::`vftable';
  v273 = 1065353216;
  v270 = 1065353216;
  v268 = 1952533809;
  v286 = (float)v225;
  v288 = (float)v225;
  v290 = (float)(v225 + v227);
  v292 = v290;
  v285 = (float)v224;
  v287 = (float)(v226 + v224);
  v289 = (float)v224;
  v291 = v287;
  DpContext::GetDeviceToWorld(a2, &v267);
  GpMatrix::Transform((GpMatrix *)&v267, (struct PointF *)&v285, 4);
  v159 = fminf(v285, v287);
  v160 = fminf(v289, v291);
  if ( v160 <= v159 )
  {
    v232 = v160;
    v159 = v160;
  }
  else
  {
    v232 = v159;
  }
  v161 = fminf(v286, v288);
  v162 = fminf(v290, v292);
  if ( v162 <= v161 )
  {
    v233 = v162;
    v161 = v162;
  }
  else
  {
    v233 = v161;
  }
  v163 = fmaxf(v285, v287);
  v164 = fmaxf(v289, v291);
  if ( v163 <= v164 )
    v163 = v164;
  v165 = fmaxf(v286, v288);
  v166 = fmaxf(v290, v292);
  v234 = v163 - v159;
  if ( v165 <= v166 )
    v165 = v166;
  v167 = *(void (__fastcall **)(__int64, __int64, int *, __m128i *))(*(_QWORD *)a1 + 160LL);
  v235 = v165 - v161;
  v167(a1, a2, &v224, &v223);
  v191[0] = (HDC)DriverPrint::GetContextHdc((struct DpContext *)a2, v196);
  if ( v191[0] )
  {
    BufferDIB = EpScanDIB::CreateBufferDIB(v198, a1 + 208, a1 + 224, v103, *(_DWORD *)(a1 + 44), *(_DWORD *)(a1 + 48));
    v169 = 0;
    v189 = BufferDIB;
    if ( !BufferDIB )
    {
      v192[0] = 0;
      v187 = 0;
      if ( v185 )
      {
        DriverPrint::SetupClipping(
          (DriverPrint *)a1,
          v191[0],
          (struct DpContext *)a2,
          (const struct GpRuntime::GpRect *)a4,
          v192,
          &v187,
          0);
        v169 = 0;
      }
      *(_DWORD *)(a1 + 180) = 0;
      if ( *(int *)(a1 + 184) > 0 )
      {
        v170 = v103 & 0x1D;
        v231 = v170;
        do
        {
          if ( v170 )
          {
            DpClipRegion::DisableComplexClipping((DpClipRegion *)(a2 + 296), (struct GpRuntime::GpRect *)(a1 + 208), 0);
            *(_DWORD *)(a2 + 288) = 0;
            v152 = a2 + 144;
            *(_DWORD *)(a2 + 176) = v157;
            *(_DWORD *)(a2 + 180) = v158;
            *(_OWORD *)(a2 + 160) = v156;
            v171 = GpMatrix::ComputeComplexity((GpMatrix *)(a2 + 144));
            v172 = v198;
            *(_DWORD *)(a2 + 184) = v171;
            EpScanDIB::SetRenderMode(v172, 0, (struct GpRuntime::GpRect *)(a1 + 208));
            v190 = 0;
            if ( *(_DWORD *)a6 == 2 && *(_DWORD *)(a1 + 44) != 1 )
            {
              v190 = *(_DWORD *)(a6 + 364);
              *(_DWORD *)(a6 + 364) = 1;
            }
            v173 = v20 + 24;
            if ( !v20 )
              v173 = a6;
            v189 = DpDriver::FillRects(a1, a2, (__int64)v196, (unsigned int *)&v224, 1, (__int64)&v232, v173);
            if ( *(_DWORD *)a6 == 2 && *(_DWORD *)(a1 + 44) != 1 )
              *(_DWORD *)(a6 + 364) = v190;
            *(_DWORD *)(a2 + 392) = 0;
            DpRegion::Set(a2 + 304, a2 + 352, 1);
          }
          *(_DWORD *)(a2 + 288) = 0;
          *(_DWORD *)(v152 + 32) = v154;
          *(_DWORD *)(v152 + 36) = v155;
          *(_OWORD *)(v152 + 16) = v153;
          *(_DWORD *)(v152 + 40) = GpMatrix::ComputeComplexity((GpMatrix *)v152);
          if ( v189 != v169 )
            break;
          if ( (v103 & 0x62) != 0 )
          {
            if ( *(_DWORD *)a6 != 1 || (v174 = *(_DWORD *)(a1 + 44), v174 == 1) )
            {
              v186 = v169;
              if ( *(_DWORD *)a6 == 2 && *(_DWORD *)(a1 + 44) != 1 )
              {
                v186 = *(_DWORD *)(a6 + 364);
                *(_DWORD *)(a6 + 364) = 1;
              }
            }
            else
            {
              *(_DWORD *)(a6 + 344) = v174;
              v186 = v169;
            }
            DpClipRegion::SetBandBounds((DpClipRegion *)(a2 + 296), (struct GpRuntime::GpRect *)(a1 + 224), 1);
            EpScanDIB::SetRenderMode(v198, 1, (struct GpRuntime::GpRect *)(a1 + 224));
            v175 = DpDriver::FillPath(a1, a2, (__int64)v196, (__int64)a4, (unsigned int *)v208, (_DWORD *)a6);
            v189 = v175;
            if ( *(_DWORD *)a6 == 2 )
            {
              if ( *(_DWORD *)(a1 + 44) != 1 )
                *(_DWORD *)(a6 + 364) = v186;
            }
            else if ( *(_DWORD *)a6 == 1 && *(_DWORD *)(a1 + 44) != 1 )
            {
              *(_DWORD *)(a6 + 344) = 1;
            }
            v169 = 0;
            if ( v175 )
              break;
          }
          v176 = (*(__int64 (__fastcall **)(__int64, HDC, __int64, struct DpBitmap *, __int64, __int64, GpPath *))(*(_QWORD *)a1 + 256LL))(
                   a1,
                   v191[0],
                   a2,
                   v196,
                   a1 + 208,
                   a1 + 224,
                   v208);
          v169 = 0;
          v189 = v176;
          if ( v176 )
            break;
          *(_DWORD *)(a1 + 212) += *(_DWORD *)(a1 + 192);
          *(_DWORD *)(a1 + 228) += *(_DWORD *)(a1 + 188);
          ++*(_DWORD *)(a1 + 180);
          v170 = v231;
        }
        while ( *(_DWORD *)(a1 + 180) < *(_DWORD *)(a1 + 184) );
      }
      if ( v185 != v169 )
        DriverPrint::RestoreClipping((DriverPrint *)a1, v191[0], v192[0], v187);
      EpScanDIB::DestroyBufferDIB(v198);
    }
    DpContext::ReleaseHdc((HWND *)a2, v191[0], 0);
  }
  else
  {
    *(_DWORD *)(a2 + 288) = 0;
    *(_DWORD *)(a2 + 176) = v154;
    *(_DWORD *)(a2 + 180) = v155;
    *(_OWORD *)(a2 + 160) = v153;
    v177 = GpMatrix::ComputeComplexity((GpMatrix *)(a2 + 144));
    *(_DWORD *)(v178 + 40) = v177;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 168LL))(a1, a2);
  if ( *(float *)&v188 != 0.0 )
  {
    v179 = v220;
    v180 = v219;
    *(_DWORD *)(a2 + 288) = 0;
    *(_DWORD *)(a2 + 164) = v179;
    *(_DWORD *)(a2 + 168) = v221;
    v181 = v222;
    *(_DWORD *)(a2 + 152) = v180;
    v182 = v197;
    *(_DWORD *)(a2 + 180) = v181;
    *(float *)(a2 + 160) = v19;
    *(_DWORD *)(a2 + 172) = v18;
    *(_DWORD *)(a2 + 176) = v16;
    *(_DWORD *)(a2 + 184) = v182;
  }
  if ( v20 )
    (**(void (__fastcall ***)(__int64, __int64))v20)(v20, 1);
  *(_DWORD *)(a1 + 44) = (_DWORD)v193;
  *(_DWORD *)(a1 + 48) = (_DWORD)v194;
  return v189;
}

```

## disassembly

```asm
0x1801331f0  mov     rax, rsp
0x1801331f3  push    rbp
0x1801331f4  push    rbx
0x1801331f5  push    rsi
0x1801331f6  push    rdi
0x1801331f7  push    r12
0x1801331f9  push    r13
0x1801331fb  push    r14
0x1801331fd  push    r15
0x1801331ff  lea     rbp, [rax-938h]
0x180133206  sub     rsp, 9F8h
0x18013320d  movaps  xmmword ptr [rax-58h], xmm6
0x180133211  movaps  xmmword ptr [rax-68h], xmm7
0x180133215  movaps  xmmword ptr [rax-78h], xmm8
0x18013321a  movaps  xmmword ptr [rax-88h], xmm9
0x180133222  movaps  xmmword ptr [rax-98h], xmm10
0x18013322a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180133232  movaps  xmmword ptr [rax-0B8h], xmm12
0x18013323a  movaps  xmmword ptr [rax-0C8h], xmm13
0x180133242  movaps  xmmword ptr [rax-0D8h], xmm14
0x18013324a  movaps  xmmword ptr [rax-0E8h], xmm15
0x180133252  mov     rax, cs:__security_cookie
0x180133259  xor     rax, rsp
0x18013325c  mov     [rbp+930h+var_F0], rax
0x180133263  mov     rax, [rbp+930h+arg_20]
0x18013326a  mov     r14, rdx
0x18013326d  mov     edx, [r9+0Ch]
0x180133271  mov     r13, r9
0x180133274  mov     rbx, [rbp+930h+arg_28]
0x18013327b  mov     rsi, rcx
0x18013327e  and     [rsp+0A30h+var_9DC], 0
0x180133283  xorps   xmm0, xmm0
0x180133286  mov     [rbp+930h+var_940], rax
0x18013328a  lea     rcx, [r14+130h]
0x180133291  mov     [rbp+930h+var_990], r8
0x180133295  lea     rax, [rbp+930h+var_8D0]
0x180133299  mov     r8d, [r9+4]
0x18013329d  add     edx, r8d
0x1801332a0  mov     r9d, [r9+8]
0x1801332a4  add     r9d, [r13+0]
0x1801332a8  mov     [rsp+0A30h+var_A08], rax
0x1801332ad  mov     dword ptr [rsp+0A30h+var_A10], edx
0x1801332b1  mov     edx, [r13+0]
0x1801332b5  movdqa  [rbp+930h+var_8D0], xmm0
0x1801332ba  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1801332bf  test    eax, eax
0x1801332c1  jz      loc_1801350BB
0x1801332c7  movss   xmm10, cs:__real@3f800000
0x1801332d0  lea     rdi, [rbx-18h]
0x1801332d4  mov     rax, [rdi]
0x1801332d7  lea     r15, [r14+90h]
0x1801332de  and     [rbp+930h+var_988], 0
0x1801332e2  xorps   xmm9, xmm9
0x1801332e6  xorps   xmm15, xmm15
0x1801332ea  movss   [rsp+0A30h+var_9E8], xmm10
0x1801332f1  mov     rdx, r15
0x1801332f4  movss   [rsp+0A30h+var_9E0], xmm10
0x1801332fb  mov     rax, [rax+70h]
0x1801332ff  mov     rcx, rdi
0x180133302  movss   [rbp+930h+var_8FC], xmm9
0x180133308  movaps  xmm13, xmm10
0x18013330c  movss   [rsp+0A30h+var_9F0], xmm15
0x180133313  movaps  xmm14, xmm10
0x180133317  movss   [rbp+930h+var_900], xmm9
0x18013331d  xor     r12d, r12d
0x180133320  movss   [rbp+930h+var_904], xmm9
0x180133326  mov     [rbp+930h+var_908], 74614D31h
0x18013332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133332  movss   xmm8, dword ptr cs:__xmm@80000000800000008000000080000000
0x18013333b  or      r9d, 0FFFFFFFFh
0x18013333f  xor     r11d, r11d
0x180133342  mov     [rsp+0A30h+var_9EC], eax
0x180133346  mov     ecx, eax
0x180133348  test    eax, eax
0x18013334a  jz      loc_1801342DE
0x180133350  mov     [rbp+930h+var_9A8], r11
0x180133354  xorps   xmm1, xmm1
0x180133357  mov     edi, r11d
0x18013335a  movups  xmm0, xmmword ptr [r13+0]
0x18013335f  movups  [rbp+930h+var_8C0], xmm1
0x180133363  movdqu  [rbp+930h+var_9A0], xmm0
0x180133368  movups  [rbp+930h+var_8B0], xmm1
0x18013336f  sub     ecx, 1
0x180133372  jz      loc_180133CFB
0x180133378  sub     ecx, 1
0x18013337b  jz      loc_180133CF2
0x180133381  sub     ecx, 1
0x180133384  jz      short loc_18013339D
0x180133386  sub     ecx, 1
0x180133389  jz      loc_180133BEB
0x18013338f  cmp     ecx, 1
0x180133392  jz      loc_180133BEB
0x180133398  jmp     loc_180133D0A
0x18013339d  movss   xmm0, dword ptr [rbx+2Ch]
0x1801333a2  lea     rdi, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1801333a9  mov     eax, [rbx+30h]
0x1801333ac  lea     rdx, [rbp+930h+var_938]; struct GpMatrix *
0x1801333b0  movss   xmm11, dword ptr [rbx+18h]
0x1801333b6  lea     rcx, [rbp+930h+var_938]; struct GpMatrix *
0x1801333ba  movss   xmm12, dword ptr [rbx+1Ch]
0x1801333c0  mov     r10d, 74614D31h
0x1801333c6  movss   xmm13, dword ptr [rbx+20h]
0x1801333cc  mov     r8, r15; struct GpMatrix *
0x1801333cf  movss   xmm14, dword ptr [rbx+24h]
0x1801333d5  movss   xmm15, dword ptr [rbx+28h]
0x1801333db  movss   [rbp+930h+var_928], xmm11
0x1801333e1  movss   [rbp+930h+var_924], xmm12
0x1801333e7  movss   [rbp+930h+var_920], xmm13
0x1801333ed  movss   [rbp+930h+var_91C], xmm14
0x1801333f3  movss   [rbp+930h+var_918], xmm15
0x1801333f9  movss   [rsp+0A30h+var_9C0], xmm0
0x1801333ff  movss   [rbp+930h+var_914], xmm0
0x180133404  mov     [rbp+930h+var_938], rdi
0x180133408  mov     [rbp+930h+var_930], r10d
0x18013340c  mov     [rbp+930h+var_92C], r9d
0x180133410  mov     dword ptr [rsp+0A30h+var_9D8], eax
0x180133414  mov     [rbp+930h+var_910], eax
0x180133417  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x18013341c  cmp     [rsi+28h], r11d
0x180133420  jnz     loc_180133BD6
0x180133426  cmp     [rsi+0A4h], r11d
0x18013342d  jnz     short loc_180133439
0x18013342f  cmp     [rsi+4Ch], r11d
0x180133433  jz      loc_180133BD6
0x180133439  test    byte ptr [rbp+930h+var_910], 8
0x18013343d  jnz     loc_180133BD6
0x180133443  movdqu  xmm0, xmmword ptr [rbx+3Ch]
0x180133448  and     [rbp+930h+var_94C], r11d
0x18013344c  lea     rcx, [rbp+930h+var_810]; void *
0x180133453  and     [rbp+930h+var_950], r11d
0x180133457  and     dword ptr [rbp+930h+var_960+8], r11d
0x18013345b  and     dword ptr [rbp+930h+var_960+4], r11d
0x18013345f  and     [rbp+930h+var_864], r11d
0x180133466  and     [rbp+930h+var_868], r11d
0x18013346d  and     dword ptr [rbp+930h+var_878+8], r11d
0x180133474  and     dword ptr [rbp+930h+var_878+4], r11d
0x18013347b  and     [rbp+930h+var_7DC], r11d
0x180133482  and     [rbp+930h+var_7E0], r11d
0x180133489  and     [rbp+930h+var_7E8], r11d
0x180133490  and     [rbp+930h+var_7EC], r11d
0x180133497  and     [rbp+930h+var_914], r11d
0x18013349b  and     [rbp+930h+var_918], r11d
0x18013349f  and     [rbp+930h+var_920], r11d
0x1801334a3  and     [rbp+930h+var_924], r11d
0x1801334a7  and     [rbp+930h+var_81C], r11d
0x1801334ae  and     [rbp+930h+var_820], r11d
0x1801334b5  and     [rbp+930h+var_828], r11d
0x1801334bc  and     [rbp+930h+var_82C], r11d
0x1801334c3  and     [rsp+0A30h+var_9C4], r11d
0x1801334c8  and     [rsp+0A30h+var_9C8], r11d
0x1801334cd  and     dword ptr [rsp+0A30h+var_9D8+0Ch], r11d
0x1801334d2  and     dword ptr [rsp+0A30h+var_9D8+8], r11d
0x1801334d7  and     dword ptr [rbp+930h+var_9B0+4], r11d
0x1801334db  and     dword ptr [rbp+930h+var_9B0], r11d
0x1801334df  mov     [rbp+930h+var_964], r9d
0x1801334e3  mov     [rbp+930h+var_87C], r9d
0x1801334ea  mov     [rbp+930h+var_7F4], r9d
0x1801334f1  mov     [rbp+930h+var_92C], r9d
0x1801334f5  mov     [rbp+930h+var_834], r9d
0x1801334fc  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x180133503  mov     [rbp+930h+var_970], rdi
0x180133507  mov     [rbp+930h+var_888], rdi
0x18013350e  mov     [rbp+930h+var_800], rdi
0x180133515  mov     [rbp+930h+var_938], rdi
0x180133519  mov     [rbp+930h+var_840], rdi
0x180133520  mov     edi, 2
0x180133525  mov     r8d, edi; unsigned __int64
0x180133528  mov     dword ptr [rbp+930h+var_960+0Ch], 3F800000h
0x18013352f  mov     dword ptr [rbp+930h+var_960], 3F800000h
0x180133536  mov     [rbp+930h+var_948], r11d
0x18013353a  lea     edx, [rdi+6]; unsigned __int64
0x18013353d  mov     [rbp+930h+var_968], r10d
0x180133541  mov     dword ptr [rbp+930h+var_878+0Ch], 3F800000h
0x18013354b  mov     dword ptr [rbp+930h+var_878], 3F800000h
0x180133555  mov     [rbp+930h+var_860], r11d
0x18013355c  mov     [rbp+930h+var_880], r10d
0x180133563  mov     [rbp+930h+var_7E4], 3F800000h
0x18013356d  mov     [rbp+930h+var_7F0], 3F800000h
0x180133577  mov     [rbp+930h+var_7D8], r11d
0x18013357e  mov     [rbp+930h+var_7F8], r10d
0x180133585  mov     [rbp+930h+var_91C], 3F800000h
0x18013358c  mov     [rbp+930h+var_928], 3F800000h
0x180133593  mov     [rbp+930h+var_910], r11d
0x180133597  mov     [rbp+930h+var_930], r10d
0x18013359b  mov     [rbp+930h+var_824], 3F800000h
0x1801335a5  mov     [rbp+930h+var_830], 3F800000h
0x1801335af  mov     [rbp+930h+var_818], r11d
0x1801335b6  mov     [rbp+930h+var_838], r10d
0x1801335bd  movups  xmmword ptr [rbp+930h+var_858.x], xmm0
0x1801335c4  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1801335c9  movups  xmm0, xmmword ptr [rbx+0F8h]
0x1801335d0  lea     r9, ??0PointF@@QEAA@XZ; void *(*)(void *)
0x1801335d7  mov     r8d, edi; unsigned __int64
0x1801335da  lea     edx, [rdi+6]; unsigned __int64
0x1801335dd  lea     rcx, [rbp+930h+var_980]; void *
0x1801335e1  movups  [rbp+930h+var_810], xmm0
0x1801335e8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1801335ed  mov     r9d, edi; int
0x1801335f0  lea     r8, [rbp+930h+var_980]; struct PointF *
0x1801335f4  lea     rdx, [rbp+930h+var_810]; struct PointF *
0x1801335fb  mov     rcx, r15; this
0x1801335fe  call    ?Transform@GpMatrix@@QEBAXPEBVPointF@@PEAV2@H@Z; GpMatrix::Transform(PointF const *,PointF *,int)
0x180133603  lea     rdx, [rbp+930h+var_978]; struct PointF *
0x180133607  lea     rcx, [rbp+930h+var_980]; struct PointF *
0x18013360b  call    ?IsClosePointF@@YAHAEBVPointF@@0@Z; IsClosePointF(PointF const &,PointF const &)
0x180133610  xor     r11d, r11d
0x180133613  test    eax, eax
0x180133615  jnz     loc_180133BD6
0x18013361b  movss   xmm7, [rbp+930h+var_978]
0x180133620  movss   xmm10, dword ptr [rbp+930h+var_980]
0x180133626  movss   xmm6, [rbp+930h+var_974]
0x18013362b  movss   xmm9, dword ptr [rbp+930h+var_980+4]
0x180133631  cvtps2pd xmm0, xmm10
0x180133635  cvtps2pd xmm2, xmm7
0x180133638  cvtps2pd xmm1, xmm9
0x18013363c  subsd   xmm2, xmm0
0x180133640  cvtps2pd xmm0, xmm6
0x180133643  mulsd   xmm2, xmm2
0x180133647  subsd   xmm0, xmm1
0x18013364b  mulsd   xmm0, xmm0
0x18013364f  addsd   xmm0, xmm2; X
0x180133653  call    sqrt
0x180133658  xorps   xmm1, xmm1
0x18013365b  movss   dword ptr [rbp+930h+var_9B0+4], xmm9
0x180133661  cvtsd2ss xmm1, xmm0
0x180133665  subss   xmm6, xmm9
0x18013366a  addss   xmm1, xmm10
0x18013366f  subss   xmm7, xmm10
0x180133674  cvtps2pd xmm0, xmm6
0x180133677  movss   dword ptr [rbp+930h+var_9B0], xmm1
0x18013367c  cvtps2pd xmm1, xmm7
0x18013367f  call    _o_atan2_0
0x180133684  mulsd   xmm0, cs:__real@4066800000000000
0x18013368c  lea     r15d, [rdi-1]
0x180133690  lea     rcx, [rbp+930h+var_938]
0x180133694  mov     r9d, r15d
0x180133697  movaps  xmm7, xmm9
0x18013369b  movaps  xmm6, xmm10
0x18013369f  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x1801336a6  xorps   xmm8, xmm8
0x1801336aa  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1801336b1  movaps  xmm2, xmm7
0x1801336b4  divsd   xmm0, cs:__real@400921fb54442d18
0x1801336bc  movaps  xmm1, xmm6
0x1801336bf  cvtsd2ss xmm8, xmm0
0x1801336c4  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1801336c9  lea     rcx, [rbp+930h+var_938]
0x1801336cd  mov     r8d, r15d
0x1801336d0  movaps  xmm1, xmm8
0x1801336d4  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1801336db  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x1801336e0  mov     r9d, r15d
0x1801336e3  lea     rcx, [rbp+930h+var_938]
0x1801336e7  movaps  xmm2, xmm9
0x1801336eb  movaps  xmm1, xmm10
0x1801336ef  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x1801336f4  movaps  xmm2, xmm7
0x1801336f7  lea     rcx, [rbp+930h+var_840]
0x1801336fe  movaps  xmm1, xmm6
0x180133701  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x180133706  movaps  xmm1, xmm8
0x18013370a  lea     rcx, [rbp+930h+var_840]
0x180133711  mov     r8d, r15d
0x180133714  call    ?Rotate@GpMatrix@@QEAAXMW4MatrixOrder@@@Z; GpMatrix::Rotate(float,MatrixOrder)
0x180133719  mov     r9d, r15d
0x18013371c  lea     rcx, [rbp+930h+var_840]
0x180133723  movaps  xmm2, xmm9
0x180133727  movaps  xmm1, xmm10
0x18013372b  call    ?Translate@GpMatrix@@QEAAXMMW4MatrixOrder@@@Z; GpMatrix::Translate(float,float,MatrixOrder)
0x180133730  movups  xmm0, xmmword ptr [r14+0A0h]
0x180133738  mov     eax, [r14+98h]
0x18013373f  lea     r8, [rbp+930h+var_938]; struct GpMatrix *
0x180133743  movss   xmm1, dword ptr [r14+0B4h]
0x18013374c  lea     rdx, [rbp+930h+var_970]; struct GpMatrix *
0x180133750  movups  [rbp+930h+var_960], xmm0
0x180133754  lea     rcx, [rbp+930h+var_970]; struct GpMatrix *
0x180133758  mov     [rbp+930h+var_968], eax
0x18013375b  movss   xmm0, dword ptr [r14+0B0h]
0x180133764  mov     eax, [r14+0B8h]
0x18013376b  movss   [rbp+930h+var_950], xmm0
0x180133770  movss   [rbp+930h+var_94C], xmm1
0x180133775  mov     [rbp+930h+var_948], eax
0x180133778  call    ?MultiplyMatrix@GpMatrix@@SAXAEAV1@AEBV1@1@Z; GpMatrix::MultiplyMatrix(GpMatrix &,GpMatrix const &,GpMatrix const &)
0x18013377d  movups  xmm0, [rbp+930h+var_960]
0x180133781  mov     ecx, [rbp+930h+var_968]
0x180133784  mov     [rbp+930h+var_880], ecx
0x18013378a  movups  [rbp+930h+var_878], xmm0
0x180133791  movss   xmm0, [rbp+930h+var_950]
0x180133796  movss   [rbp+930h+var_868], xmm0
0x18013379e  movss   xmm1, [rbp+930h+var_94C]
0x1801337a3  lea     rcx, [rbp+930h+var_888]
0x1801337aa  mov     eax, [rbp+930h+var_948]
0x1801337ad  movss   [rbp+930h+var_864], xmm1
0x1801337b5  mov     [rbp+930h+var_860], eax
0x1801337bb  call    ?Invert@GpMatrix@@QEAA?AW4Status@@XZ; GpMatrix::Invert(void)
0x1801337c0  xor     r11d, r11d
0x1801337c3  test    eax, eax
0x1801337c5  jnz     loc_180133BC4
0x1801337cb  mov     rdi, [rbp+930h+var_940]
0x1801337cf  lea     rdx, [rbp+930h+var_970]; struct GpMatrix *
  ... truncated ...
```
