# GpGraphics::DrvDrawImage(GpRuntime::GpRect const *,GpBitmap *,int,PointF const *,RectF const *,GpImageAttributes const *,ulong)

- ea: `0x1800127a8`
- end: `0x180015711`
- name: `?DrvDrawImage@GpGraphics@@IEAA?AW4Status@@PEBVGpRect@GpRuntime@@PEAVGpBitmap@@HPEBVPointF@@PEBVRectF@@PEBVGpImageAttributes@@K@Z`
- size: `12137`
- prototype: ``
- caller_count: `2`
- callee_count: `60`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800127a8`
- `0x18002c47c`

## callees

- `0x180010bd0`
- `0x180012220`
- `0x1800126c0`
- `0x1800127a8`
- `0x180015718`
- `0x180015774`
- `0x180015b64`
- `0x180017a3c`
- `0x180019610`
- `0x180019dd8`
- `0x18001b2ec`
- `0x18001b6cc`
- `0x18001c4b0`
- `0x18001cb78`
- `0x18001da50`
- `0x18001e860`
- `0x18002b850`
- `0x18002c2c8`
- `0x18002c47c`
- `0x18002d150`
- `0x18002f060`
- `0x18002f12c`
- `0x180033c30`
- `0x18003dcb0`
- `0x180043038`
- `0x180043c9c`
- `0x180044c4c`
- `0x180045fa0`
- `0x180051890`
- `0x180053c04`
- `0x180053f94`
- `0x180054c7c`
- `0x180063cd8`
- `0x18006483c`
- `0x18006766c`
- `0x1800683ac`
- `0x18006f358`
- `0x18007b64c`
- `0x180080604`
- `0x180086a60`
- `0x180086ab0`
- `0x180086cc0`
- `0x18008ae2c`
- `0x1800948e8`
- `0x1800a2d9c`
- `0x1800a4618`
- `0x1800be5f0`
- `0x1800cbf9c`
- `0x1800d38d4`
- `0x1800f2e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800135f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013aa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001458a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800135f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013aa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001458a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015673`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ee1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ee1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001520e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001520e`

## pseudocode

```c
__int64 __fastcall GpGraphics::DrvDrawImage(
        struct GpGraphics *a1,
        __int64 a2,
        GpBitmap *a3,
        int a4,
        __m128 *a5,
        __int128 *a6,
        GpImageAttributes *a7,
        int a8)
{
  unsigned int v8; // r13d
  __int64 v10; // rbx
  PointF *v11; // rdi
  struct GpGraphics *v12; // r15
  unsigned __int64 v13; // xmm3_8
  __m128 v14; // xmm5
  float v15; // xmm2_4
  GpImageAttributes *v16; // rdi
  BOOL v17; // r8d
  int v18; // eax
  int Uniqueness; // ecx
  __int64 v20; // rax
  unsigned int CompressedData; // r14d
  float v22; // xmm7_4
  float v23; // xmm8_4
  float v24; // xmm10_4
  float v25; // xmm6_4
  float v26; // xmm14_4
  float v27; // xmm2_4
  float v28; // xmm3_4
  float v29; // xmm6_4
  float v30; // xmm4_4
  float v31; // xmm2_4
  float *v32; // rax
  float v33; // xmm9_4
  float v34; // xmm13_4
  float v35; // xmm8_4
  float v36; // xmm14_4
  float v37; // xmm12_4
  float v38; // xmm0_4
  float v39; // xmm6_4
  float v40; // xmm11_4
  float v41; // xmm8_4
  float v42; // xmm14_4
  int v43; // eax
  __int32 v44; // xmm6_4
  int v45; // esi
  __int64 v46; // rax
  _DWORD *v47; // rax
  int v48; // xmm0_4
  __int64 v49; // rax
  float v50; // xmm9_4
  __int64 v51; // rax
  __int64 v52; // rbx
  PointF *v53; // rdi
  GpMatrix *v54; // rcx
  float v55; // xmm0_4
  bool v56; // bl
  int v57; // r14d
  float v58; // xmm0_4
  int v59; // ebx
  GpBitmap *v60; // rax
  unsigned int v61; // edx
  GpBitmap *v62; // rdi
  GpGraphics *v63; // rsi
  __int64 v64; // rax
  int v65; // eax
  unsigned int v66; // edi
  __int64 v67; // rbx
  float v68; // xmm7_4
  __int64 v69; // rbx
  PointF *v70; // rdi
  _DWORD *v71; // rax
  int v72; // xmm0_4
  __int64 v73; // rbx
  PointF *v74; // rdi
  float v75; // xmm3_4
  float v76; // xmm2_4
  float v77; // xmm0_4
  float v78; // xmm1_4
  float v79; // xmm0_4
  float v80; // xmm0_4
  float v81; // xmm1_4
  float v82; // xmm0_4
  bool v83; // bl
  __m128 x; // xmm1
  int v85; // edi
  __m128 y; // xmm1
  int v87; // ebx
  GpBitmap *v88; // rax
  GpBitmap *v89; // rcx
  __int64 v90; // rax
  unsigned int v91; // edx
  GpGraphics *v92; // rsi
  int v93; // ecx
  int v94; // eax
  __int64 v95; // rax
  GpBitmap *v96; // rcx
  int v97; // r13d
  int v98; // edi
  GpMemoryBitmap *v99; // rbx
  __int64 v100; // rax
  unsigned int (__fastcall *v101)(_QWORD); // rax
  __int64 v102; // rcx
  int v103; // ebx
  int v104; // ebx
  int v105; // edi
  float v106; // xmm7_4
  float v107; // xmm6_4
  float v108; // xmm8_4
  int v109; // xmm10_4
  float v110; // xmm9_4
  float v111; // xmm11_4
  __int64 v112; // rax
  struct _RTL_CRITICAL_SECTION *v113; // rcx
  __int32 v114; // edi
  __int32 v115; // ebx
  __int64 v116; // rax
  int v117; // r14d
  double v118; // xmm6_8
  double v119; // xmm7_8
  int v120; // esi
  int v121; // r8d
  __int128 *v122; // rax
  GpImageAttributes *v123; // rdi
  int v124; // r11d
  unsigned __int8 v125; // bl
  __int64 v126; // rdi
  int v127; // eax
  unsigned int v128; // edx
  int v129; // esi
  _DWORD *v130; // rax
  int v131; // xmm1_4
  int v132; // xmm2_4
  int v133; // ecx
  int v134; // xmm0_4
  int v135; // xmm1_4
  int v136; // xmm2_4
  struct GpRegion *v137; // rbx
  _DWORD *v138; // rax
  int v139; // xmm1_4
  int v140; // xmm2_4
  int v141; // ecx
  int v142; // xmm0_4
  int v143; // xmm1_4
  int v144; // xmm2_4
  struct GpBitmap *v145; // rcx
  bool v147; // zf
  __int64 v148; // rdx
  int v149; // ecx
  int *v150; // rax
  unsigned int v151; // ebx
  struct GpBitmap *v152; // rax
  float v153; // xmm7_4
  float v154; // xmm6_4
  int v155; // r8d
  unsigned int v156; // ebx
  unsigned int v157; // ebx
  unsigned int v158; // ebx
  unsigned int v159; // ebx
  unsigned int v160; // ebx
  unsigned int v161; // ebx
  float v162; // xmm7_4
  float v163; // xmm0_4
  float v164; // xmm6_4
  __int64 v165; // rax
  __int64 v166; // rax
  struct GpBitmap *v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  volatile signed __int32 *v170; // rax
  __m128i v171; // xmm1
  GpImageAttributes *v172; // rbx
  GpImageAttributes *v173; // rax
  __int64 v174; // rax
  int TransparencyFlags; // ebx
  unsigned int *v176; // r9
  unsigned int v177; // r8d
  unsigned int *v178; // r10
  unsigned int i; // edx
  unsigned int v180; // ecx
  unsigned int v181; // ecx
  unsigned __int8 v182; // al
  unsigned __int8 v183; // al
  float v184; // xmm6_4
  float v185; // xmm2_4
  float v186; // xmm0_4
  float v187; // xmm0_4
  float v188; // xmm7_4
  unsigned int v189; // ebx
  int v190; // ebx
  float v191; // xmm4_4
  float v192; // xmm2_4
  float v193; // xmm1_4
  float v194; // xmm1_4
  float v195; // xmm2_4
  float v196; // xmm1_4
  float v197; // xmm1_4
  __int64 v198; // rax
  float v199; // xmm8_4
  float v200; // xmm7_4
  float v201; // xmm6_4
  float v202; // xmm7_4
  float v203; // xmm9_4
  float v204; // xmm6_4
  struct GpImageAttributes *v205; // rax
  int v206; // et0
  struct DpBitmap *v207; // rdx
  DpContext *v208; // rcx
  HDC Hdc; // rax
  HDC v210; // rdi
  __int64 v211; // rax
  int v212; // eax
  unsigned int v213; // ebx
  __int64 v214; // rdx
  __int64 v215; // r8
  __int64 v216; // rdx
  float v217; // xmm7_4
  float v218; // xmm8_4
  __int64 v219; // rbx
  PointF *v220; // rdi
  __int64 v221; // rax
  float v222; // xmm6_4
  int v223; // eax
  __m128 v224; // xmm1
  __m128 v225; // xmm1
  int Rotation; // ebx
  int v227; // edi
  float v228; // xmm7_4
  float v229; // xmm0_4
  float v230; // xmm7_4
  float v231; // xmm0_4
  float v232; // xmm2_4
  float v233; // xmm1_4
  int v234; // ebx
  int v235; // ebx
  int v236; // eax
  LPSTREAM v237; // r10
  int v238; // r8d
  GpBitmap *v239; // rax
  GpBitmap *v240; // rbx
  struct CopyOnWriteBitmap *v241; // rax
  struct CopyOnWriteBitmap *v242; // rbx
  char v243; // [rsp+68h] [rbp-A0h] BYREF
  char v244; // [rsp+69h] [rbp-9Fh]
  char v245; // [rsp+6Ah] [rbp-9Eh]
  unsigned __int8 v246[4]; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v247; // [rsp+70h] [rbp-98h] BYREF
  struct GpGraphics *v248; // [rsp+78h] [rbp-90h]
  int v249; // [rsp+80h] [rbp-88h]
  __int128 v250; // [rsp+88h] [rbp-80h] BYREF
  int v251; // [rsp+98h] [rbp-70h]
  float v252; // [rsp+9Ch] [rbp-6Ch]
  int v253; // [rsp+A0h] [rbp-68h] BYREF
  float v254; // [rsp+A4h] [rbp-64h]
  BOOL v255; // [rsp+A8h] [rbp-60h] BYREF
  int v256; // [rsp+B0h] [rbp-58h]
  float v257; // [rsp+B8h] [rbp-50h]
  float v258; // [rsp+BCh] [rbp-4Ch]
  void **v259; // [rsp+C0h] [rbp-48h] BYREF
  int v260; // [rsp+C8h] [rbp-40h]
  int v261; // [rsp+CCh] [rbp-3Ch]
  _BYTE v262[20]; // [rsp+D0h] [rbp-38h]
  __int64 v263; // [rsp+E4h] [rbp-24h]
  float v264; // [rsp+F0h] [rbp-18h]
  float v265; // [rsp+F4h] [rbp-14h]
  int v266; // [rsp+F8h] [rbp-10h] BYREF
  LPSTREAM ppstm; // [rsp+100h] [rbp-8h] BYREF
  GpImageAttributes *v268; // [rsp+108h] [rbp+0h]
  GpBitmap *v269; // [rsp+110h] [rbp+8h]
  __int128 v270; // [rsp+118h] [rbp+10h] BYREF
  BOOL v271; // [rsp+128h] [rbp+20h]
  __int128 v272; // [rsp+130h] [rbp+28h] BYREF
  void **v273; // [rsp+140h] [rbp+38h] BYREF
  int v274; // [rsp+148h] [rbp+40h]
  int v275; // [rsp+14Ch] [rbp+44h]
  __int64 v276; // [rsp+150h] [rbp+48h]
  float v277; // [rsp+158h] [rbp+50h]
  __int64 v278; // [rsp+15Ch] [rbp+54h]
  unsigned __int64 v279; // [rsp+164h] [rbp+5Ch]
  struct GpBitmap *v280; // [rsp+170h] [rbp+68h]
  struct GpRegion *Clip; // [rsp+178h] [rbp+70h]
  __m256i v282; // [rsp+180h] [rbp+78h] BYREF
  __int128 v283; // [rsp+1A0h] [rbp+98h] BYREF
  GpMemoryBitmap *v284; // [rsp+1B0h] [rbp+A8h]
  int v285; // [rsp+1B8h] [rbp+B0h]
  int v286; // [rsp+1BCh] [rbp+B4h]
  int v287; // [rsp+1C0h] [rbp+B8h]
  int v288; // [rsp+1C4h] [rbp+BCh]
  int v289; // [rsp+1C8h] [rbp+C0h]
  int v290; // [rsp+1CCh] [rbp+C4h]
  int v291; // [rsp+1D0h] [rbp+C8h]
  int v292; // [rsp+1D4h] [rbp+CCh]
  int v293; // [rsp+1D8h] [rbp+D0h]
  int v294; // [rsp+1DCh] [rbp+D4h]
  int v295; // [rsp+1E0h] [rbp+D8h]
  int v296; // [rsp+1E4h] [rbp+DCh]
  __int64 v297; // [rsp+1E8h] [rbp+E0h]
  void **v298; // [rsp+1F0h] [rbp+E8h] BYREF
  int v299; // [rsp+1F8h] [rbp+F0h]
  __int64 v300; // [rsp+200h] [rbp+F8h]
  GpRecolor *v301; // [rsp+208h] [rbp+100h]
  __int64 v302; // [rsp+214h] [rbp+10Ch]
  int v303; // [rsp+21Ch] [rbp+114h]
  __m256i v304; // [rsp+228h] [rbp+120h] BYREF
  int *v305; // [rsp+248h] [rbp+140h]
  _BYTE Buf1[20]; // [rsp+258h] [rbp+150h] BYREF
  int v307; // [rsp+26Ch] [rbp+164h]
  int v308; // [rsp+270h] [rbp+168h]
  _BYTE v309[24]; // [rsp+298h] [rbp+190h] BYREF
  int v310[2]; // [rsp+2B0h] [rbp+1A8h] BYREF
  __int64 v311; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v312; // [rsp+2C0h] [rbp+1B8h]
  int v313; // [rsp+2C8h] [rbp+1C0h]
  unsigned __int64 v314; // [rsp+2CCh] [rbp+1C4h]
  _BYTE v315[20]; // [rsp+2D4h] [rbp+1CCh]
  __int64 v316; // [rsp+2E8h] [rbp+1E0h] BYREF
  int v317; // [rsp+2F0h] [rbp+1E8h]
  __int128 *v318; // [rsp+2F8h] [rbp+1F0h]
  __int64 v319; // [rsp+300h] [rbp+1F8h]
  __int32 v320; // [rsp+310h] [rbp+208h]
  _QWORD *v321; // [rsp+318h] [rbp+210h]
  __int128 v322; // [rsp+388h] [rbp+280h] BYREF
  int v323; // [rsp+398h] [rbp+290h]
  int v324; // [rsp+3A0h] [rbp+298h]
  int v325; // [rsp+3A4h] [rbp+29Ch]
  __int64 v326; // [rsp+3A8h] [rbp+2A0h]
  __int64 v327; // [rsp+3B0h] [rbp+2A8h]
  _BYTE *v328; // [rsp+3C0h] [rbp+2B8h]
  _BYTE *v329; // [rsp+3C8h] [rbp+2C0h]
  int v330; // [rsp+3D0h] [rbp+2C8h]
  __int64 v331; // [rsp+3D4h] [rbp+2CCh]
  _BYTE v332[40]; // [rsp+3E0h] [rbp+2D8h] BYREF
  _BYTE v333[16]; // [rsp+408h] [rbp+300h] BYREF
  int v334; // [rsp+418h] [rbp+310h]
  unsigned __int64 v335; // [rsp+41Ch] [rbp+314h]
  __m128 v336; // [rsp+448h] [rbp+340h] BYREF
  unsigned __int64 v337; // [rsp+458h] [rbp+350h]
  struct tagPOINT v338[2]; // [rsp+460h] [rbp+358h] BYREF
  __int64 v339; // [rsp+470h] [rbp+368h]
  float v340; // [rsp+478h] [rbp+370h]
  __int64 v341; // [rsp+47Ch] [rbp+374h]
  __int64 v342; // [rsp+484h] [rbp+37Ch]
  __m128 v343; // [rsp+490h] [rbp+388h] BYREF
  unsigned __int64 v344; // [rsp+4A0h] [rbp+398h]
  __m128 v345; // [rsp+4A8h] [rbp+3A0h] BYREF
  unsigned __int64 v346; // [rsp+4B8h] [rbp+3B0h]

  v8 = 3;
  v297 = a2;
  v248 = a1;
  v268 = a7;
  if ( a4 != 3 )
    return 2;
  v10 = 3;
  v11 = (PointF *)&v336;
  do
  {
    PointF::PointF(v11);
    v11 = (PointF *)((char *)v11 + 8);
    --v10;
  }
  while ( v10 );
  v12 = v248;
  v13 = a5[1].m128_u64[0];
  v14 = *a5;
  v250 = *a6;
  v337 = v13;
  v15 = _mm_shuffle_ps(v14, v14, 85).m128_f32[0];
  v336 = v14;
  if ( COERCE_FLOAT(
         COERCE_UNSIGNED_INT(
           (float)((float)(v14.m128_f32[0] - _mm_shuffle_ps(v14, v14, 170).m128_f32[0])
                 * (float)(*((float *)&v13 + 1) - v15))
         - (float)((float)(v15 - _mm_shuffle_ps(v14, v14, 255).m128_f32[0]) * (float)(*(float *)&v13 - v14.m128_f32[0])))
       & _xmm) < 0.00000011920929 )
    return 0;
  v16 = v268;
  v17 = *((_QWORD *)v248 + 16) == (_QWORD)Globals::MetaDriver;
  v271 = v17;
  if ( !v268 || !*((_QWORD *)v268 + 3) )
    goto LABEL_6;
  v148 = *((_QWORD *)v268 + 3);
  v149 = 0;
  v150 = *(int **)(v148 + 8);
  if ( v150 )
    goto LABEL_145;
  if ( !*(_BYTE *)(v148 + 41) )
    v150 = *(int **)v148;
  if ( v150 )
LABEL_145:
    v149 = *v150;
  v253 = 1;
  if ( !v149 )
LABEL_6:
    v253 = 0;
  v18 = 925707;
  if ( v17 )
    v18 = 2498570;
  v249 = v18;
  Uniqueness = GpObject::GenerateUniqueness();
  v20 = *((_QWORD *)v248 + 5);
  v257 = 0.0;
  v258 = 0.0;
  CompressedData = 0;
  v261 = -1;
  v22 = FLOAT_1_0;
  *(_DWORD *)(v20 + 28) = Uniqueness;
  v23 = FLOAT_1_0;
  v24 = 0.0;
  Clip = 0;
  v269 = 0;
  v255 = 0;
  v25 = 0.0;
  v259 = &GpMatrix::`vftable';
  HIDWORD(v263) = 0;
  v26 = 0.0;
  v260 = 1952533809;
  v27 = (float)((float)((float)(*((float *)&v250 + 3) + *((float *)&v250 + 1))
                      * (float)(*((float *)&v250 + 2) + *(float *)&v250))
              - (float)(*((float *)&v250 + 1) * *(float *)&v250))
      + (float)((float)(COERCE_FLOAT(HIDWORD(v250) ^ _xmm) * *(float *)&v250)
              - (float)(*((float *)&v250 + 1) * *((float *)&v250 + 2)));
  if ( COERCE_FLOAT(LODWORD(v27) & _xmm) >= 0.00000011920929 )
  {
    v28 = 1.0 / v27;
    v29 = COERCE_FLOAT(v250 ^ _xmm) * *((float *)&v250 + 3);
    v23 = (float)((float)(COERCE_FLOAT(HIDWORD(v250) ^ _xmm) * v336.m128_f32[0])
                + (float)(*((float *)&v250 + 3) * v336.m128_f32[2]))
        * (float)(1.0 / v27);
    *(float *)v262 = v23;
    v258 = (float)((float)(COERCE_FLOAT(HIDWORD(v250) ^ _xmm) * v336.m128_f32[1])
                 + (float)(*((float *)&v250 + 3) * v336.m128_f32[3]))
         * (float)(1.0 / v27);
    *(float *)&v262[4] = v258;
    v257 = (float)((float)(COERCE_FLOAT(DWORD2(v250) ^ _xmm) * v336.m128_f32[0])
                 + (float)(*((float *)&v250 + 2) * *(float *)&v337))
         * (float)(1.0 / v27);
    *(float *)&v262[8] = v257;
    v30 = COERCE_FLOAT(DWORD1(v250) ^ _xmm) * *((float *)&v250 + 2);
    v31 = (float)((float)(*((float *)&v250 + 3) + *((float *)&v250 + 1))
                * (float)(*((float *)&v250 + 2) + *(float *)&v250))
        - (float)(*((float *)&v250 + 1) * *(float *)&v250);
    v22 = (float)((float)(COERCE_FLOAT(DWORD2(v250) ^ _xmm) * v336.m128_f32[1])
                + (float)(*((float *)&v250 + 2) * *((float *)&v337 + 1)))
        * v28;
    *(float *)&v262[12] = v22;
    v26 = (float)((float)((float)(v29 * v336.m128_f32[2]) + (float)(v31 * v336.m128_f32[0]))
                + (float)(v30 * *(float *)&v337))
        * v28;
    v25 = (float)((float)((float)(v29 * v336.m128_f32[3]) + (float)(v31 * v336.m128_f32[1]))
                + (float)(v30 * *((float *)&v337 + 1)))
        * v28;
    *(float *)&v262[16] = v26;
    *(float *)&v263 = v25;
    HIDWORD(v263) = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
  }
  v32 = (float *)*((_QWORD *)v12 + 17);
  v33 = (float)(v258 * v32[42]) + (float)(v23 * v32[40]);
  v34 = (float)(v258 * v32[43]) + (float)(v23 * v32[41]);
  v35 = v26 * v32[40];
  v36 = v26 * v32[41];
  v37 = (float)(v257 * v32[40]) + (float)(v22 * v32[42]);
  v38 = v25 * v32[42];
  v39 = v25 * v32[43];
  v40 = (float)(v257 * v32[41]) + (float)(v22 * v32[43]);
  v264 = v33;
  v258 = v34;
  v265 = v37;
  v257 = v40;
  *(float *)v262 = v33;
  v41 = (float)(v35 + v38) + v32[44];
  *(float *)&v262[4] = v34;
  v42 = (float)(v36 + v39) + v32[45];
  *(float *)&v262[8] = v37;
  *(float *)&v262[12] = v40;
  v252 = v41;
  *(float *)&v262[16] = v41;
  v254 = v42;
  *(float *)&v263 = v42;
  v43 = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
  COERCE_FLOAT(v44 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
  v45 = v43;
  v251 = v43;
  HIDWORD(v263) = v43;
  if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v40 * v33) - (float)(v37 * v34)) & v44) < 0.00000011920929 )
    return 0;
  v46 = *((_QWORD *)v12 + 17);
  if ( *(_DWORD *)(v46 + 52) == 4 || (v147 = *(_DWORD *)(v46 + 52) == 2, v266 = 0, v147) )
    v266 = 1;
  if ( *((_DWORD *)v12 + 16) )
  {
    if ( *(_DWORD *)(*((_QWORD *)v12 + 16) + 56LL) )
    {
      if ( (*(_DWORD *)(*((_QWORD *)v12 + 17) + 184LL) & 0xFFFFFFFC) == 0 )
      {
        Rotation = GpMatrix::GetRotation(&v259);
        if ( (Rotation & 0xFFFFFFFB) != 0 && !(unsigned int)GpBitmap::IsDirty(a3) && !v253 )
        {
          memset_0(Buf1, 0, 0x40u);
          CompressedData = (*(__int64 (__fastcall **)(GpBitmap *, _BYTE *))(*(_QWORD *)a3 + 176LL))(a3, Buf1);
          if ( !CompressedData && !memcmp_0(Buf1, &IMGFMT_JPEG, 0x10u) )
          {
            ppstm = 0;
            v227 = 0;
            if ( !CreateStreamOnHGlobal(0, 0, &ppstm) && ppstm )
            {
              memset(&v304, 0, sizeof(v304));
              v305 = 0;
              v253 = 0;
              v304.m256i_i32[0] = 1;
              if ( *((float *)&v337 + 1) <= fminf(v336.m128_f32[1], v336.m128_f32[3]) )
                v228 = *((float *)&v337 + 1);
              else
                v228 = fminf(v336.m128_f32[1], v336.m128_f32[3]);
              if ( *(float *)&v337 <= fminf(v336.m128_f32[0], v336.m128_f32[2]) )
                LODWORD(v229) = v337;
              else
                v229 = fminf(v336.m128_f32[0], v336.m128_f32[2]);
              v345.m128_u64[0] = __PAIR64__(LODWORD(v228), LODWORD(v229));
              if ( *((float *)&v337 + 1) <= fminf(v336.m128_f32[1], v336.m128_f32[3]) )
                v230 = *((float *)&v337 + 1);
              else
                v230 = fminf(v336.m128_f32[1], v336.m128_f32[3]);
              if ( fmaxf(v336.m128_f32[0], v336.m128_f32[2]) <= *(float *)&v337 )
                LODWORD(v231) = v337;
              else
                v231 = fmaxf(v336.m128_f32[0], v336.m128_f32[2]);
              v345.m128_u64[1] = __PAIR64__(LODWORD(v230), LODWORD(v231));
              if ( fmaxf(v336.m128_f32[1], v336.m128_f32[3]) <= *((float *)&v337 + 1) )
                v232 = *((float *)&v337 + 1);
              else
                v232 = fmaxf(v336.m128_f32[1], v336.m128_f32[3]);
              if ( *(float *)&v337 <= fminf(v336.m128_f32[0], v336.m128_f32[2]) )
                LODWORD(v233) = v337;
              else
                v233 = fminf(v336.m128_f32[0], v336.m128_f32[2]);
              v346 = __PAIR64__(LODWORD(v232), LODWORD(v233));
              v259 = &GpMatrix::`vftable';
              v261 = -1;
              *(_QWORD *)&v262[12] = 1065353216;
              *(_QWORD *)v262 = 1065353216;
              v263 = 0;
              *(_DWORD *)&v262[8] = 0;
              v260 = 1952533809;
              v270 = v250;
              v234 = Rotation - 1;
              if ( v234 )
              {
                v235 = v234 - 1;
                if ( v235 )
                {
                  if ( v235 != 1 )
                  {
                    v304.m256i_i32[0] = 0;
LABEL_348:
                    GpMatrix::TransformRect((GpMatrix *)&v259, (struct RectF *)&v270);
                    v304.m256i_i64[3] = 0x400000001LL;
                    v305 = &v253;
                    *(_OWORD *)&v304.m256i_u64[1] = xmmword_180189460;
                    if ( v238 )
                    {
                      if ( !(*(unsigned int (__fastcall **)(GpBitmap *, LPSTREAM, __int64 *, __m256i *))(*(_QWORD *)a3 + 96LL))(
                              a3,
                              v237,
                              qword_180189450,
                              &v304) )
                      {
                        v239 = (GpBitmap *)GpMallocEx(1504, 0);
                        v240 = v239 ? GpBitmap::GpBitmap(v239, ppstm) : 0LL;
                        if ( v240 )
                        {
                          if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v240 + 8LL))(v240) )
                          {
                            CompressedData = GpGraphics::DrvDrawImage(v12, v297, v240, 3, &v345, &v270, v268, a8);
                            v227 = 1;
                          }
                          (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v240 + 56LL))(v240);
                        }
                      }
                      v237 = ppstm;
                    }
                    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v237 + 16LL))(v237);
                    if ( v227 )
                      return CompressedData;
                    return v8;
                  }
                  *(__m128i *)v262 = _mm_load_si128((const __m128i *)&_xmm);
                  *(_DWORD *)&v262[16] = 0;
                  *(float *)&v263 = (float)v307;
                  v236 = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
                  v253 = 15;
                }
                else
                {
                  *(__m128i *)v262 = _mm_load_si128((const __m128i *)&_xmm_bf8000000000000000000000bf800000);
                  *(float *)&v262[16] = (float)v307;
                  *(float *)&v263 = (float)v308;
                  v236 = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
                  v253 = 14;
                }
              }
              else
              {
                *(__m128i *)v262 = _mm_load_si128((const __m128i *)&_xmm);
                LODWORD(v263) = 0;
                *(float *)&v262[16] = (float)v308;
                v236 = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
                v253 = 13;
              }
              HIDWORD(v263) = v236;
              goto LABEL_348;
            }
            v16 = v268;
          }
        }
      }
    }
  }
  v47 = (_DWORD *)*((_QWORD *)v12 + 17);
  v280 = 0;
  v290 = v47[40];
  v291 = v47[41];
  v286 = v47[42];
  v287 = v47[43];
  v288 = v47[44];
  v48 = v47[45];
  LODWORD(ppstm) = v47[46];
  v49 = *((_QWORD *)v12 + 17);
  v289 = v48;
  *(_DWORD *)(v49 + 288) = 0;
  v50 = FLOAT_0_5;
  if ( (unsigned int)GpMatrix::IsIntegerTranslate((GpMatrix *)&v259) )
    goto LABEL_16;
  v151 = GpMatrix::AnalyzeRotateFlip(&v259);
  if ( !v151 )
    goto LABEL_16;
  memset_0(Buf1, 0, 0x40u);
  CompressedData = (*(__int64 (__fastcall **)(GpBitmap *, _BYTE *))(*(_QWORD *)a3 + 176LL))(a3, Buf1);
  if ( CompressedData )
    goto LABEL_134;
  v152 = GpBitmap::Clone(a3, 0, v249);
  v280 = v152;
  if ( !v152 )
  {
    CompressedData = 3;
    goto LABEL_134;
  }
  a3 = v152;
  (*(void (__fastcall **)(struct GpBitmap *, _QWORD))(*(_QWORD *)v152 + 248LL))(v152, v151);
  LODWORD(v153) = v250;
  v154 = *((float *)&v250 + 1);
  if ( v266 != CompressedData )
  {
    v153 = *(float *)&v250 + 0.5;
    v154 = *((float *)&v250 + 1) + 0.5;
    HIDWORD(v263) = (CompressedData + 1) | v45;
    *(float *)&v250 = *(float *)&v250 + 0.5;
    *((float *)&v250 + 1) = *((float *)&v250 + 1) + 0.5;
    v41 = (float)(v41 + 0.5) + (float)((float)(v264 * -0.5) - (float)(v265 * 0.5));
    v42 = (float)(v42 + 0.5) + (float)((float)(v40 * -0.5) - (float)(v34 * 0.5));
  }
  *(__m128i *)v262 = _mm_load_si128((const __m128i *)&_xmm);
  v254 = v42;
  v252 = v41;
  *(float *)&v262[16] = v41;
  *(float *)&v263 = v42;
  v251 = GpMatrix::ComputeComplexity((GpMatrix *)&v259);
  v45 = v251;
  HIDWORD(v263) = v251;
  v256 = 0;
  v156 = v151 - 1;
  if ( !v156 )
  {
    v188 = v153 + 0.0;
    *((_QWORD *)&v250 + 1) = __PAIR64__(DWORD2(v250), HIDWORD(v250));
    LODWORD(v197) = COERCE_UNSIGNED_INT((float)v308) ^ _xmm;
    v252 = (float)(v197 + 0.0) + v41;
    v41 = v252;
    *(float *)&v262[16] = v252;
    v42 = (float)((float)(v197 * 0.0) + 0.0) + v42;
    v254 = v42;
    *(float *)&v263 = v42;
    v184 = v154 + (float)((float)v308 - (float)((float)(v154 * 2.0) + *((float *)&v250 + 2)));
    goto LABEL_221;
  }
  v157 = v156 - 1;
  if ( !v157 )
  {
    LODWORD(v195) = COERCE_UNSIGNED_INT((float)v308) ^ _xmm;
    LODWORD(v196) = COERCE_UNSIGNED_INT((float)v307) ^ _xmm;
    v252 = (float)((float)(v195 * 0.0) + v196) + v41;
    v41 = v252;
    *(float *)&v262[16] = v252;
    v254 = (float)((float)(v196 * 0.0) + v195) + v42;
    v42 = v254;
    *(float *)&v263 = v254;
    v162 = v153 + (float)((float)v307 - (float)((float)(v153 * 2.0) + *((float *)&v250 + 2)));
    goto LABEL_161;
  }
  v158 = v157 - 1;
  if ( !v158 )
  {
    v184 = v154 + 0.0;
    v185 = *((float *)&v250 + 2);
    *((_QWORD *)&v250 + 1) = __PAIR64__(DWORD2(v250), HIDWORD(v250));
    LODWORD(v186) = COERCE_UNSIGNED_INT((float)v307) ^ _xmm;
    v254 = (float)(v186 + 0.0) + v42;
    v42 = v254;
    *(float *)&v263 = v254;
    v252 = (float)((float)(v186 * 0.0) + 0.0) + v41;
    v41 = v252;
    *(float *)&v262[16] = v252;
    v187 = (float)(v153 * 2.0) + v185;
LABEL_220:
    v188 = v153 + (float)((float)v307 - v187);
LABEL_221:
    *(_QWORD *)&v250 = __PAIR64__(LODWORD(v188), LODWORD(v184));
    goto LABEL_163;
  }
  v159 = v158 - 1;
  if ( !v159 )
  {
    v164 = v154 + 0.0;
    LODWORD(v194) = COERCE_UNSIGNED_INT((float)v307) ^ _xmm;
    v252 = (float)(v194 + 0.0) + v41;
    v41 = v252;
    *(float *)&v262[16] = v252;
    v42 = (float)((float)(v194 * 0.0) + 0.0) + v42;
    v254 = v42;
    *(float *)&v263 = v42;
    v162 = v153 + (float)((float)v307 - (float)((float)(v153 * 2.0) + *((float *)&v250 + 2)));
    goto LABEL_162;
  }
  v160 = v159 - 1;
  if ( !v160 )
  {
    *((_QWORD *)&v250 + 1) = __PAIR64__(DWORD2(v250), HIDWORD(v250));
    *(_QWORD *)&v250 = __PAIR64__(LODWORD(v153), LODWORD(v154));
    goto LABEL_164;
  }
  v161 = v160 - 1;
  if ( v161 )
  {
    if ( v161 != 1 )
      goto LABEL_164;
    v191 = *((float *)&v250 + 2);
    *((_QWORD *)&v250 + 1) = __PAIR64__(DWORD2(v250), HIDWORD(v250));
    LODWORD(v192) = COERCE_UNSIGNED_INT((float)v307) ^ _xmm;
    LODWORD(v193) = COERCE_UNSIGNED_INT((float)v308) ^ _xmm;
    v252 = (float)((float)(v192 * 0.0) + v193) + v41;
    v41 = v252;
    *(float *)&v262[16] = v252;
    v254 = (float)((float)(v193 * 0.0) + v192) + v42;
    v42 = v254;
    *(float *)&v263 = v254;
    v187 = (float)(v153 * 2.0) + v191;
    v184 = v154 + (float)((float)v308 - (float)((float)(v154 * 2.0) + *((float *)&v250 + 2)));
    goto LABEL_220;
  }
  v162 = v153 + 0.0;
  LODWORD(v163) = COERCE_UNSIGNED_INT((float)v308) ^ _xmm;
  v254 = (float)(v163 + 0.0) + v42;
  v42 = v254;
  *(float *)&v263 = v254;
  v252 = (float)((float)(v163 * 0.0) + 0.0) + v41;
  v41 = v252;
  *(float *)&v262[16] = v252;
LABEL_161:
  v164 = v154 + (float)((float)v308 - (float)((float)(v154 * 2.0) + *((float *)&v250 + 3)));
LABEL_162:
  *(_QWORD *)&v250 = __PAIR64__(LODWORD(v164), LODWORD(v162));
LABEL_163:
  v45 = v155 | v251;
  HIDWORD(v263) = v155 | v251;
  v251 |= v155;
LABEL_164:
  v165 = *((_QWORD *)v12 + 17);
  v40 = *(float *)&v262[12];
  v34 = *(float *)&v262[4];
  v257 = *(float *)&v262[12];
  *(float *)(v165 + 176) = v41;
  *(float *)(v165 + 180) = v42;
  *(_DWORD *)(v165 + 152) = 1952533809;
  *(_QWORD *)(v165 + 160) = 1065353216;
  *(_DWORD *)(v165 + 168) = 0;
  *(_DWORD *)(v165 + 172) = 1065353216;
  *(_DWORD *)(v165 + 184) = v45;
  v166 = *((_QWORD *)v12 + 17);
  v258 = v34;
  *(_DWORD *)(v166 + 288) = 0;
  v44 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  v336.m128_u64[0] = v250;
  v336.m128_i32[3] = DWORD1(v250);
  LODWORD(v337) = v250;
  v336.m128_f32[2] = *((float *)&v250 + 2) + *(float *)&v250;
  *((float *)&v337 + 1) = *((float *)&v250 + 3) + *((float *)&v250 + 1);
  v265 = *(float *)&v262[8];
  v264 = *(float *)v262;
LABEL_16:
  if ( (v45 & 0xFFFFFFFC) != 0 && !v271 )
  {
    v51 = *((_QWORD *)v12 + 17);
    if ( *(_DWORD *)(v51 + 48) == 7 || *(_DWORD *)(v51 + 48) == 6 )
    {
      if ( *((_DWORD *)v12 + 16) && (!v16 || *((_DWORD *)v16 + 9) == 4) )
      {
        v198 = *(_QWORD *)a3;
        v338[1] = 0;
        v338[0] = 0;
        (*(void (__fastcall **)(GpBitmap *, struct tagPOINT *))(v198 + 168))(a3, v338);
        v199 = *(float *)&v338[0].x;
        if ( (float)(*((float *)&v250 + 2) + *(float *)&v250) <= (float)(*(float *)&v338[0].x + *(float *)&v338[1].x) )
          v200 = *((float *)&v250 + 2) + *(float *)&v250;
        else
          v200 = *(float *)&v338[0].x + *(float *)&v338[1].x;
        if ( (float)(*((float *)&v250 + 3) + *((float *)&v250 + 1)) <= (float)(*(float *)&v338[0].y
                                                                             + *(float *)&v338[1].y) )
          v201 = *((float *)&v250 + 3) + *((float *)&v250 + 1);
        else
          v201 = *(float *)&v338[0].y + *(float *)&v338[1].y;
        if ( *(float *)&v338[0].x <= *(float *)&v250 )
          LODWORD(v199) = v250;
        v202 = v200 - v199;
        v203 = fmaxf(*(float *)&v338[0].y, *((float *)&v250 + 1));
        v204 = v201 - v203;
        *(float *)&v338[1].x = v202;
        *(float *)&v338[1].y = v204;
        if ( v202 <= 0.00000011920929 || v204 <= 0.00000011920929 )
          goto LABEL_134;
        if ( v199 != *(float *)&v250
          || v203 != *((float *)&v250 + 1)
          || v202 != *((float *)&v250 + 2)
          || v204 != *((float *)&v250 + 3) )
        {
          v275 = -1;
          v273 = &GpMatrix::`vftable';
          v278 = 1065353216;
          v276 = 1065353216;
          v279 = 0;
          v277 = 0.0;
          v274 = 1952533809;
          if ( !(unsigned int)GpMatrix::InferAffineMatrix(&v273, &v336, &v250) )
          {
            v336.m128_u64[0] = __PAIR64__(LODWORD(v203), LODWORD(v199));
            v336.m128_f32[3] = v203;
            *(float *)&v337 = v199;
            v336.m128_f32[2] = v199 + v202;
            *((float *)&v337 + 1) = v204 + v203;
            GpMatrix::Transform((GpMatrix *)&v273, (struct PointF *)&v336, 3);
            *(_QWORD *)&v250 = __PAIR64__(LODWORD(v203), LODWORD(v199));
            *((_QWORD *)&v250 + 1) = __PAIR64__(LODWORD(v204), LODWORD(v202));
          }
        }
        v41 = v252;
        v50 = FLOAT_0_5;
      }
      v52 = 3;
      v53 = (PointF *)&v343;
      do
      {
        PointF::PointF(v53);
        v53 = (PointF *)((char *)v53 + 8);
        --v52;
      }
      while ( v52 );
      v54 = (GpMatrix *)(*((_QWORD *)v12 + 17) + 144LL);
      v344 = v337;
      v343 = v336;
      GpMatrix::Transform(v54, (struct PointF *)&v343, 3);
      v55 = o_sqrtf_0(
              (float)((float)(v343.m128_f32[3] - v343.m128_f32[1]) * (float)(v343.m128_f32[3] - v343.m128_f32[1]))
            + (float)((float)(v343.m128_f32[2] - v343.m128_f32[0]) * (float)(v343.m128_f32[2] - v343.m128_f32[0])));
      v56 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      {
        v224 = 0;
        v224.m128_f32[0] = v55;
        v57 = (int)_mm_round_ss(v224, v224, 10).m128_f32[0];
      }
      else
      {
        v57 = -(int)floor(COERCE_FLOAT(LODWORD(v55) ^ _xmm));
      }
      v58 = o_sqrtf_0(
              (float)((float)(*((float *)&v344 + 1) - v343.m128_f32[1])
                    * (float)(*((float *)&v344 + 1) - v343.m128_f32[1]))
            + (float)((float)(*(float *)&v344 - v343.m128_f32[0]) * (float)(*(float *)&v344 - v343.m128_f32[0])));
      if ( v56 )
      {
        v225 = 0;
        v225.m128_f32[0] = v58;
        v59 = (int)_mm_round_ss(v225, v225, 10).m128_f32[0];
      }
      else
      {
        v59 = -(int)floor(COERCE_FLOAT(LODWORD(v58) ^ _xmm));
      }
      COERCE_FLOAT(v44 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
      v45 = v251;
      if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v57 - *((float *)&v250 + 2)) & v44) > 1.0000001
        && COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v59 - *((float *)&v250 + 3)) & v44) > 1.0000001 )
      {
        v60 = (GpBitmap *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5E0u);
        if ( v60 )
          v62 = GpBitmap::GpBitmap(v60, v57, v59, 925707);
        else
          v62 = 0;
        v63 = 0;
        if ( v62
          && (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v62 + 8LL))(v62)
          && (v168 = *(_QWORD *)a3,
              v266 = 0,
              v255 = 0,
              (*(void (__fastcall **)(GpBitmap *, int *, BOOL *))(v168 + 152))(a3, &v266, &v255),
              GpBitmap::SetResolution(v62),
              v169 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)v62 + 128LL))(v62),
              (v63 = (GpGraphics *)v169) != 0)
          && *(_DWORD *)(v169 + 8) == 1634879281 )
        {
          v170 = (volatile signed __int32 *)(v169 + 16);
          if ( v170 )
          {
            v338[1] = (struct tagPOINT)v170;
            v338[0].x = _InterlockedIncrement(v170);
          }
          else
          {
            v338[0].x = 0;
            v338[1] = (struct tagPOINT)v338;
          }
          GpGraphics::SetInterpolationMode(v63, *(unsigned int *)(*((_QWORD *)v12 + 17) + 48LL));
          GpGraphics::SetCompositingMode(v63, 1);
          v171 = _mm_cvtsi32_si128(v59);
          v172 = v268;
          *(_QWORD *)&v272 = 0;
          *((float *)&v272 + 2) = (float)v57;
          HIDWORD(v272) = _mm_cvtepi32_ps(v171).m128_u32[0];
          if ( *((_DWORD *)v12 + 16) )
          {
            if ( v268 )
            {
              if ( *((_DWORD *)v268 + 9) == 4 )
              {
                v205 = GpImageAttributes::Clone(v268);
                v172 = v205;
                if ( v205 )
                {
                  *(_QWORD *)((char *)v205 + 36) = 3;
                  *((_DWORD *)v205 + 11) = 0;
                  *((_QWORD *)v205 + 2) = 0;
                }
              }
            }
            else
            {
              v173 = (GpImageAttributes *)GpMallocEx(56, 0);
              if ( v173 )
                v172 = GpImageAttributes::GpImageAttributes(v173);
              else
                v172 = 0;
              if ( v172 )
              {
                *(_QWORD *)((char *)v172 + 36) = 3;
                *((_DWORD *)v172 + 11) = 0;
                *((_QWORD *)v172 + 2) = 0;
              }
            }
          }
          CompressedData = GpGraphics::DrawImage(v63, a3, &v272, &v250, 2, v172);
          if ( v172 != v268 && v172 )
            (**(void (__fastcall ***)(GpImageAttributes *, __int64))v172)(v172, 1);
          if ( !CompressedData )
          {
            v275 = -1;
            v273 = &GpMatrix::`vftable';
            v278 = 1065353216;
            v276 = 1065353216;
            v270 = v272;
            v279 = 0;
            v277 = 0.0;
            v274 = 1952533809;
            GpMatrix::InferAffineMatrix(&v273, &v336, &v270);
            UndoSourceFlip((struct RectF *)&v270);
            CompressedData = GpGraphics::DrawImage(v12, v62, &v270, &v273, 0, 0, 2);
          }
          _InterlockedDecrement(*(volatile signed __int32 **)&v338[1]);
        }
        else
        {
          CompressedData = 3;
        }
        if ( v63 )
          GpGraphics::`scalar deleting destructor'(v63, v61);
        if ( v62 )
          (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v62 + 56LL))(v62);
        goto LABEL_134;
      }
    }
  }
  v64 = *((_QWORD *)v12 + 5);
  if ( *(_DWORD *)(v64 + 12) == 0x10000000 )
    BYTE1(v65) = 32;
  else
    v65 = *(_DWORD *)(v64 + 12);
  v66 = BYTE1(v65);
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a3 + 4) + 16LL));
  v67 = *((_QWORD *)a3 + 4);
  CompressedData = 0;
  if ( !memcmp_0((const void *)(v67 + 144), &IMGFMT_ICO, 0x10u) )
  {
    CompressedData = CopyOnWriteBitmap::SetIconParameters(v67, &v250, &v259, v66);
    LODWORD(v42) = v263;
    v41 = *(float *)&v262[16];
    v40 = *(float *)&v262[12];
    v34 = *(float *)&v262[4];
    v68 = *(float *)v262;
    v45 = HIDWORD(v263);
    v265 = *(float *)&v262[8];
    v254 = *(float *)&v263;
    v252 = *(float *)&v262[16];
    v257 = *(float *)&v262[12];
    v258 = *(float *)&v262[4];
    v264 = *(float *)v262;
    v251 = HIDWORD(v263);
  }
  else
  {
    v68 = v264;
  }
  GpBitmap::Unlock(a3);
  if ( CompressedData )
    goto LABEL_134;
  memset_0(v333, 0, 0x40u);
  CompressedData = (*(__int64 (__fastcall **)(GpBitmap *, _BYTE *))(*(_QWORD *)a3 + 176LL))(a3, v333);
  if ( CompressedData )
    goto LABEL_134;
  v69 = 3;
  v70 = (PointF *)&v343;
  do
  {
    PointF::PointF(v70);
    v70 = (PointF *)((char *)v70 + 8);
    --v69;
  }
  while ( v69 );
  v71 = (_DWORD *)*((_QWORD *)v12 + 17);
  v285 = v71[40];
  v295 = v71[41];
  v296 = v71[42];
  v294 = v71[43];
  v293 = v71[44];
  v72 = v71[45];
  LODWORD(v71) = v71[46];
  v292 = v72;
  v256 = (int)v71;
  v344 = v337;
  v343 = v336;
  if ( (v45 & 0xFFFFFFFC) != 0 && v271 )
  {
    v73 = 3;
    v74 = (PointF *)&v345;
    do
    {
      PointF::PointF(v74);
      v74 = (PointF *)((char *)v74 + 8);
      --v73;
    }
    while ( v73 );
    v338[1] = 0;
    v338[0] = 0;
    TransformBounds(
      (const struct GpMatrix *)&v259,
      *(float *)&v250,
      *((float *)&v250 + 1),
      *((float *)&v250 + 2) + *(float *)&v250,
      *((float *)&v250 + 3) + *((float *)&v250 + 1),
      (struct RectF *)v338);
    v12 = v248;
    *((float *)&v278 + 1) = v41;
    v75 = FLOAT_1_0;
    v345.m128_i32[3] = v338[0].y;
    v345.m128_f32[2] = *(float *)&v338[1].x + *(float *)&v338[0].x;
    *(struct tagPOINT *)v345.m128_f32 = v338[0];
    LODWORD(v346) = v338[0].x;
    v76 = FLOAT_1_0;
    v279 = __PAIR64__(v45, LODWORD(v42));
    v273 = &GpMatrix::`vftable';
    v275 = -1;
    *((float *)&v346 + 1) = *(float *)&v338[1].y + *(float *)&v338[0].y;
    v77 = v68;
    v274 = 1952533809;
    if ( v68 < 0.0 )
      LODWORD(v77) = LODWORD(v68) ^ _xmm;
    v78 = v34;
    if ( v34 < 0.0 )
      LODWORD(v78) = LODWORD(v34) ^ _xmm;
    v79 = fmaxf(v77, v78);
    if ( v79 > 1.0 )
      v76 = 1.0 / v79;
    v80 = v265;
    if ( v265 < 0.0 )
      LODWORD(v80) = LODWORD(v265) ^ _xmm;
    v81 = v40;
    if ( v40 < 0.0 )
      LODWORD(v81) = LODWORD(v40) ^ _xmm;
    v82 = fmaxf(v80, v81);
    if ( v82 > 1.0 )
      v75 = 1.0 / v82;
    *(float *)&v276 = v76 * v68;
    v277 = v75 * v265;
    *((float *)&v276 + 1) = v76 * v34;
    *(float *)&v278 = v75 * v40;
    HIDWORD(v279) = GpMatrix::ComputeComplexity((GpMatrix *)&v273);
    TransformBounds(
      (const struct GpMatrix *)&v273,
      *(float *)&v250,
      *((float *)&v250 + 1),
      *((float *)&v250 + 2) + *(float *)&v250,
      *((float *)&v250 + 3) + *((float *)&v250 + 1),
      (struct RectF *)v338);
    x = (__m128)(unsigned int)v338[1].x;
    v83 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    x.m128_f32[0] = (float)((float)((float)(*(float *)&v338[1].x + *(float *)&v338[0].x) - *(float *)&v338[0].x) + 1.0)
                  + v50;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      v85 = (int)_mm_round_ss(x, x, 9).m128_f32[0];
    else
      v85 = (int)floor(x.m128_f32[0]);
    y = (__m128)(unsigned int)v338[1].y;
    y.m128_f32[0] = (float)((float)((float)(*(float *)&v338[1].y + *(float *)&v338[0].y) - *(float *)&v338[0].y) + 1.0)
                  + v50;
    if ( v83 )
      v87 = (int)_mm_round_ss(y, y, 9).m128_f32[0];
    else
      v87 = (int)floor(y.m128_f32[0]);
    v88 = (GpBitmap *)GpMallocEx(1504, 0);
    if ( v88 )
      v89 = GpBitmap::GpBitmap(v88, v85, v87, 2498570);
    else
      v89 = 0;
    v269 = v89;
    if ( !v89 || !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v89 + 8LL))(v89) )
      goto LABEL_87;
    v90 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)v269 + 128LL))(v269);
    v91 = 0;
    v92 = (GpGraphics *)v90;
    if ( !v90 )
    {
      v45 = v251;
      goto LABEL_87;
    }
    if ( *(_DWORD *)(v90 + 8) != 1634879281 )
    {
LABEL_86:
      GpGraphics::`scalar deleting destructor'(v92, v91);
      v45 = v251;
LABEL_87:
      v44 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
      v273 = &GpMatrix::`vftable';
      v274 = 1279869254;
      goto LABEL_88;
    }
    if ( v90 == -16 )
    {
      LODWORD(v270) = 0;
      *((_QWORD *)&v270 + 1) = &v270;
    }
    else
    {
      *((_QWORD *)&v270 + 1) = v90 + 16;
      LODWORD(v270) = _InterlockedIncrement((volatile signed __int32 *)(v90 + 16));
    }
    *(_DWORD *)v246 = 0;
    GpGraphics::Clear(v90, v246, 1);
    GpGraphics::TranslateWorldTransform(v92, v214, v215, 0);
    if ( (unsigned int)GpGraphics::MultiplyWorldTransform(v92, &v273, 0) )
    {
LABEL_85:
      _InterlockedDecrement(*((volatile signed __int32 **)&v270 + 1));
      goto LABEL_86;
    }
    GpImageAttributes::GpImageAttributes((GpImageAttributes *)&v298);
    v216 = *((_QWORD *)v12 + 17);
    v302 = 3;
    v303 = 0;
    v300 = 0;
    GpGraphics::SetPixelOffsetMode(v92, *(unsigned int *)(v216 + 52));
    if ( (unsigned int)GpGraphics::DrawImage(v92, a3, &v250, &v250, 2, &v298) )
    {
LABEL_82:
      v298 = &GpImageAttributes::`vftable';
      if ( v301 )
        GpRecolor::`scalar deleting destructor'(v301, v91);
      v299 = 1279869254;
      v298 = &GpObject::`vftable';
      goto LABEL_85;
    }
    v217 = (float)v85;
    v218 = (float)v87;
    Clip = GpGraphics::GetClip(v12);
    if ( !Clip )
    {
LABEL_81:
      v95 = *((_QWORD *)v12 + 17);
      v96 = v269;
      v343 = v345;
      a3 = v269;
      v344 = v346;
      *(_QWORD *)(v95 + 172) = 1065353216;
      *(_QWORD *)(v95 + 160) = 1065353216;
      *(_QWORD *)(v95 + 180) = 0;
      *(_DWORD *)(v95 + 168) = 0;
      *(_DWORD *)(v95 + 152) = 1952533809;
      (*(void (__fastcall **)(GpBitmap *, _BYTE *))(*(_QWORD *)a3 + 176LL))(v96, v333);
      *((_QWORD *)&v250 + 1) = __PAIR64__(LODWORD(v218), LODWORD(v217));
      *(_QWORD *)&v250 = 0;
      goto LABEL_82;
    }
    v219 = 4;
    v220 = (PointF *)&v304;
    do
    {
      PointF::PointF(v220);
      v220 = (PointF *)((char *)v220 + 8);
      --v219;
    }
    while ( v219 );
    v221 = *((_QWORD *)v12 + 17);
    v222 = 0.0;
    *(_DWORD *)v246 = -2130640640;
    if ( *(_DWORD *)(v221 + 52) == 4 || *(_DWORD *)(v221 + 52) == 2 )
    {
      v338[1].y = -1;
      v338[0] = (struct tagPOINT)&GpMatrix::`vftable';
      v341 = 1065353216;
      v339 = 1065353216;
      v342 = 0;
      v340 = 0.0;
      v338[1].x = 1952533809;
      if ( !(unsigned int)GpGraphics::GetDeviceToWorldTransform(v12, v338, 1) )
      {
        v24 = FLOAT_N0_5;
        v222 = FLOAT_N0_5;
        if ( HIDWORD(v342) )
        {
          LODWORD(v248) = -1090519040;
          v24 = (float)(*(float *)&v339 * -0.5) - (float)(v340 * v50);
          v222 = (float)(*(float *)&v341 * -0.5) - (float)(*((float *)&v339 + 1) * v50);
        }
      }
    }
    *(float *)v304.m256i_i32 = v24 + v336.m128_f32[0];
    *(float *)&v304.m256i_i32[1] = v222 + v336.m128_f32[1];
    *(float *)&v304.m256i_i32[2] = v24 + v336.m128_f32[2];
    *(float *)&v304.m256i_i32[3] = v222 + v336.m128_f32[3];
    *(float *)&v304.m256i_i32[4] = (float)((float)(v336.m128_f32[2] - v336.m128_f32[0]) + *(float *)&v337) + v24;
    *(float *)&v304.m256i_i32[6] = v24 + *(float *)&v337;
    *(float *)&v304.m256i_i32[5] = (float)((float)(*((float *)&v337 + 1) - v336.m128_f32[1]) + v336.m128_f32[3]) + v222;
    *(float *)&v304.m256i_i32[7] = v222 + *((float *)&v337 + 1);
    DpPath::DpPath((DpPath *)v309);
    v324 = -1;
    *(_QWORD *)v309 = &GpPath::`vftable';
    v327 = 0;
    v329 = v332;
    v326 = 0;
    v328 = v332;
    v330 = 3;
    v331 = 3;
    v310[0] = 0;
    v322 = 0;
    v323 = 1;
    HIDWORD(v314) = 0;
    LODWORD(v319) = 0;
    *(_DWORD *)&v309[8] = 1752453169;
    *(_QWORD *)&v309[16] = 0;
    v325 = 0;
    if ( (unsigned int)DpPath::ValidatePathTypes(v246, 4, (int *)&v322 + 3, v310) )
    {
      if ( (unsigned int)DynArrayImpl::AddMultiple(&v311, 1, 4, v246)
        || (v223 = DynArrayImpl::AddMultiple(&v316, 8, 4, &v304), v93 = 1752453169, v223) )
      {
        v93 = 1279869254;
      }
      *(_DWORD *)&v309[8] = v93;
      if ( v93 != 1752453169 )
        goto LABEL_76;
      *(_BYTE *)v311 = 0;
    }
    v93 = *(_DWORD *)&v309[8];
LABEL_76:
    if ( v93 == 1752453169 )
    {
      if ( *((_QWORD *)v12 + 7)
        && (v94 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD))(**((_QWORD **)v12 + 7) + 288LL))(
                    *((_QWORD *)v12 + 7),
                    v309,
                    1,
                    0)) != 0 )
      {
        *((_DWORD *)v12 + 2) = 1279869254;
      }
      else
      {
        v94 = GpGraphics::CombineClip(v12, v309, 1, 0);
      }
      v255 = v94 == 0;
    }
    GpPath::~GpPath((GpPath *)v309);
    goto LABEL_81;
  }
LABEL_88:
  *(_QWORD *)v310 = &GpMatrix::`vftable';
  v97 = 0;
  *(_DWORD *)v246 = 0;
  v98 = 0;
  v251 = 0;
  v244 = 0;
  LOBYTE(v247) = 0;
  v272 = 0u;
  v245 = -1;
  v243 = -1;
  v99 = 0;
  v283 = 0u;
  v100 = *(_QWORD *)a3;
  memset(&v304, 0, sizeof(v304));
  v101 = *(unsigned int (__fastcall **)(_QWORD))(v100 + 8);
  *(_OWORD *)&v309[8] = 0u;
  v314 = 1065353216;
  v312 = 1065353216;
  *(_QWORD *)v315 = 0;
  v313 = 0;
  v311 = -2342433487LL;
  if ( !v101(a3) )
  {
    CompressedData = 2;
    goto LABEL_111;
  }
  if ( !*((_DWORD *)v12 + 16) )
    goto LABEL_90;
  v174 = *((_QWORD *)v12 + 17);
  if ( (*(_DWORD *)(v174 + 184) & 0xFFFFFFFC) != 0
    || COERCE_FLOAT(COERCE_UNSIGNED_INT(v343.m128_f32[0] - *(float *)&v344) & v44) >= 0.00000011920929
    || COERCE_FLOAT(COERCE_UNSIGNED_INT(v343.m128_f32[1] - v343.m128_f32[3]) & v44) >= 0.00000011920929
    || v343.m128_f32[2] <= v343.m128_f32[0]
    || *((float *)&v344 + 1) <= v343.m128_f32[1]
    || (GpMatrix::Transform((GpMatrix *)(v174 + 144), (const struct PointF *)&v343, v338, 3), v338[1].x <= v338[0].x)
    || SHIDWORD(v339) <= v338[0].y )
  {
    if ( !*((_DWORD *)v12 + 16) )
    {
LABEL_90:
      EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a3 + 4) + 16LL));
      v102 = *((_QWORD *)a3 + 4);
      v103 = 1;
      if ( *(_QWORD *)(v102 + 88) )
      {
        switch ( *(_DWORD *)(*(_QWORD *)(v102 + 88) + 136LL) )
        {
          case 1:
            v97 = 1;
            break;
          case 2:
            v97 = 2;
            break;
          case 3:
            v97 = 3;
            break;
          case 5:
            v97 = 5;
            break;
          default:
            v97 = 0;
            break;
        }
        v103 = 0;
      }
      else
      {
        v97 = 0;
      }
      GpBitmap::Unlock(a3);
      if ( v103 )
        v97 = 0;
      goto LABEL_99;
    }
    if ( *(_DWORD *)(*((_QWORD *)v12 + 17) + 28LL) != 1 )
    {
      if ( v253
        || (EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a3 + 4) + 16LL)),
            TransparencyFlags = CopyOnWriteBitmap::GetTransparencyFlags(
                                  *((_QWORD *)a3 + 4),
                                  v246,
                                  (unsigned int)v249,
                                  &v247,
                                  &v243),
            GpBitmap::Unlock(a3),
            v244 = v247,
            v245 = v243,
            TransparencyFlags) )
      {
        v97 = 0;
      }
      else
      {
        v97 = *(_DWORD *)v246;
      }
      goto LABEL_99;
    }
    goto LABEL_232;
  }
  if ( !v253 && *((float *)&v250 + 3) >= 32.0 && *((float *)&v250 + 2) >= 32.0 )
  {
    v206 = _mm_getcsr();
    LODWORD(v248) = v206;
    v207 = (struct DpBitmap *)*((_QWORD *)v12 + 5);
    v208 = (DpContext *)*((_QWORD *)v12 + 17);
    LODWORD(v248) = v206 & 0xFFFFFFC0;
    _mm_setcsr(v206 & 0xFFFFFFC0);
    Hdc = DpContext::GetHdc(v208, v207);
    v210 = Hdc;
    LODWORD(v248) = v206 & 0xFFFFFFC0;
    _mm_setcsr(v206 & 0xFFFFFFC0);
    if ( Hdc )
    {
      CompressedData = GpBitmap::GetCompressedData(
                         a3,
                         &v272,
                         *(unsigned int *)(*((_QWORD *)v12 + 16) + 56LL),
                         *(unsigned int *)(*((_QWORD *)v12 + 16) + 60LL),
                         Hdc);
      if ( *((_QWORD *)&v272 + 1) )
      {
        v97 = 3;
        *(_OWORD *)v304.m256i_i8 = v335;
        *(_OWORD *)&v304.m256i_u64[2] = 0u;
        v251 = 1;
        *(_DWORD *)v246 = 3;
        v249 = 0;
      }
      DpContext::ReleaseHdc(*((DpContext **)v12 + 17), v210, *((struct DpBitmap **)v12 + 5));
      v98 = v251;
      if ( v251 )
        goto LABEL_99;
    }
    else
    {
      v98 = 0;
    }
  }
  if ( (v334 & 0x20000) == 0 || (v334 & 0x40000) != 0 || (v334 & 0x100000) != 0 || BYTE1(v334) > 8u )
    goto LABEL_225;
  if ( v268 && *((_DWORD *)v268 + 9) != 4 )
  {
    v211 = *(_QWORD *)a3;
    v338[1] = 0;
    v338[0] = 0;
    (*(void (__fastcall **)(GpBitmap *, struct tagPOINT *))(v211 + 168))(a3, v338);
    if ( *(float *)&v250 >= *(float *)&v338[0].x
      && (float)(*(float *)&v338[0].x + *(float *)&v338[1].x) >= (float)(*((float *)&v250 + 2) + *(float *)&v250)
      && *((float *)&v250 + 1) >= *(float *)&v338[0].y
      && (float)(*(float *)&v338[0].y + *(float *)&v338[1].y) >= (float)(*((float *)&v250 + 3) + *((float *)&v250 + 1)) )
    {
      v189 = v334;
      v249 = v334;
      goto LABEL_226;
    }
LABEL_225:
    v189 = v249;
    goto LABEL_226;
  }
  v189 = v334;
  v249 = v334;
LABEL_226:
  if ( *(_DWORD *)(*((_QWORD *)v12 + 17) + 28LL) == 1 )
  {
LABEL_232:
    v97 = 5;
    goto LABEL_99;
  }
  if ( !v253 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a3 + 4) + 16LL));
    v190 = CopyOnWriteBitmap::GetTransparencyFlags(*((_QWORD *)a3 + 4), v246, v189, &v247, &v243);
    GpBitmap::Unlock(a3);
    if ( !v190 )
    {
      v97 = *(_DWORD *)v246;
      v244 = v247;
      v245 = v243;
      goto LABEL_230;
    }
    v244 = v247;
    v245 = v243;
  }
  v97 = 0;
LABEL_230:
  if ( ((v97 - 3) & 0xFFFFFFFD) == 0 )
  {
LABEL_99:
    v104 = v249;
    goto LABEL_100;
  }
  v104 = 925707;
  v249 = 925707;
LABEL_100:
  if ( !v271 )
    ApplyVisibleClipToSourceRect(v12, (const struct GpMatrix *)&v259, (struct RectF *)&v250, (struct PointF *)&v343);
  if ( v98 )
  {
    v99 = 0;
    v282 = v304;
    v283 = v250;
    v284 = 0;
  }
  else
  {
    v105 = v266;
    CompressedData = 1;
    v106 = v252;
    v107 = v254;
    v108 = v264;
    v109 = LODWORD(v265);
    v110 = v257;
    v111 = v258;
    if ( v266 )
    {
      v45 |= 1u;
      *(float *)&v250 = *(float *)&v250 + 0.5;
      *((float *)&v250 + 1) = *((float *)&v250 + 1) + 0.5;
      v106 = (float)(v252 + 0.5) + (float)((float)(v264 * -0.5) - (float)(v265 * 0.5));
      v107 = (float)(v254 + 0.5) + (float)((float)(v257 * -0.5) - (float)(v258 * 0.5));
    }
    if ( *((GpBitmap **)v12 + 6) == a3 )
    {
      v167 = GpBitmap::Clone(a3, 0, v104);
      v280 = v167;
      if ( !v167 )
      {
        CompressedData = 3;
        goto LABEL_134;
      }
      a3 = v167;
    }
    *(_QWORD *)v309 = *((_QWORD *)v12 + 17);
    LODWORD(v311) = v260;
    v316 = (__int64)v268;
    v112 = *((_QWORD *)a3 + 4);
    v312 = __PAIR64__(LODWORD(v111), LODWORD(v108));
    v313 = v109;
    v314 = __PAIR64__(LODWORD(v106), LODWORD(v110));
    *(float *)v315 = v107;
    *(_OWORD *)&v309[8] = v250;
    *(_DWORD *)&v315[4] = v45;
    *(_DWORD *)&v315[12] = v104;
    if ( *(int *)(v112 + 60) > 1 )
    {
      v241 = GpBitmap::LockForWrite(a3);
      v242 = v241;
      if ( v241 )
      {
        CompressedData = CopyOnWriteBitmap::PipeLockBits(v241, v309, &v282);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v242 + 16));
      }
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v112 + 16));
      CompressedData = CopyOnWriteBitmap::PipeLockBits(*((_QWORD *)a3 + 4), v309, &v282);
      GpBitmap::Unlock(a3);
    }
    v99 = 0;
    if ( CompressedData )
    {
LABEL_131:
      if ( *((GpMemoryBitmap **)&v272 + 1) != v99 )
        GpBitmap::DeleteCompressedData(a3, &v272);
      v130 = (_DWORD *)*((_QWORD *)v12 + 17);
      v131 = v295;
      v132 = v296;
      v133 = v256;
      v130[40] = v285;
      v134 = v294;
      v130[41] = v131;
      v135 = v293;
      v130[42] = v132;
      v136 = v292;
      v130[43] = v134;
      v130[44] = v135;
      v130[45] = v136;
      v130[38] = 1952533809;
      v130[46] = v133;
      *(_DWORD *)(*((_QWORD *)v12 + 17) + 288LL) = (_DWORD)v99;
      v137 = Clip;
      if ( Clip )
      {
        if ( v255 )
          GpGraphics::SetClip(v12, Clip, 0);
        (**(void (__fastcall ***)(struct GpRegion *, __int64))v137)(v137, 1);
      }
      goto LABEL_134;
    }
    if ( v105 )
    {
      *(float *)&v283 = *(float *)&v283 + -0.5;
      *((float *)&v283 + 1) = *((float *)&v283 + 1) + -0.5;
    }
  }
LABEL_111:
  if ( CompressedData )
    goto LABEL_131;
  v113 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)a3 + 4) + 16LL);
  v114 = v282.m256i_i32[1];
  *(float *)&v309[20] = Globals::DesktopDpiX;
  v321 = 0;
  v312 = 0;
  v318 = 0;
  LODWORD(v311) = 0;
  v115 = v282.m256i_i32[0];
  *(_OWORD *)&v315[4] = 0;
  *(float *)v310 = Globals::DesktopDpiY;
  *(_DWORD *)v309 = 1833067569;
  v316 = 1;
  EnterCriticalSection(v113);
  v116 = *((_QWORD *)a3 + 4);
  v117 = *(_DWORD *)(v116 + 160);
  v118 = *(double *)(v116 + 184);
  v119 = *(double *)(v116 + 192);
  v120 = *(_DWORD *)(v116 + 128);
  *(_DWORD *)&v309[4] = v115;
  *(_DWORD *)&v309[8] = v114;
  *(_DWORD *)&v309[16] = 0;
  v310[1] = GpObject::GenerateUniqueness();
  *(_DWORD *)v315 = -16777216;
  v313 = 16711680;
  v314 = 0xFF0000FF00LL;
  *(_DWORD *)v309 = 1833067569;
  v319 = 0;
  v320 = 0;
  v317 = 2;
  v321 = (_QWORD *)((char *)a3 + 48);
  *(float *)&v309[20] = v118;
  *(float *)v310 = v119;
  v312 = 0;
  *(_DWORD *)&v309[12] = v117;
  LODWORD(v316) = v120;
  GpBitmap::Unlock(a3);
  v121 = v249;
  v319 = v282.m256i_i64[2];
  *(_QWORD *)&v309[4] = v282.m256i_i64[0];
  v320 = v282.m256i_i32[2];
  v122 = &v272;
  *(_DWORD *)&v309[12] = v249;
  *(_DWORD *)&v309[16] = 4 * v282.m256i_i32[1] * v282.m256i_i32[0];
  if ( !*((_QWORD *)&v272 + 1) )
    v122 = v318;
  v318 = v122;
  if ( (v249 & 0x10000) == 0 )
  {
    v123 = v268;
LABEL_116:
    if ( *((_DWORD *)v12 + 16) && !v97 && (v121 == 2498570 || v121 == 925707) )
    {
      v176 = (unsigned int *)v319;
      v125 = 0;
      v177 = 0;
      v97 = 3;
      LOBYTE(v124) = -1;
      while ( v177 < *(_DWORD *)&v309[8] )
      {
        v178 = v176;
        for ( i = 0; i < *(_DWORD *)&v309[4]; ++i )
        {
          v180 = *v178++;
          v181 = HIBYTE(v180);
          v182 = v124;
          if ( (unsigned __int8)v181 < (unsigned __int8)v124 )
            v182 = v181;
          v124 = v182;
          v183 = v125;
          if ( (unsigned __int8)v181 > v125 )
            v183 = v181;
          v125 = v183;
          if ( (_BYTE)v181 != 0xFF )
          {
            if ( (_BYTE)v181 )
            {
              if ( v183 - v124 > 16 )
              {
                v97 = 1;
                goto LABEL_118;
              }
              v97 = 4;
            }
            else if ( v97 != 4 )
            {
              v97 = 2;
            }
          }
        }
        v176 = (unsigned int *)((char *)v176 + v320);
        ++v177;
      }
    }
    else
    {
      LOBYTE(v124) = v244;
      v125 = v245;
    }
LABEL_118:
    BYTE5(v311) = v125;
    v99 = 0;
    LODWORD(v311) = v97;
    BYTE4(v311) = v124;
    v338[0] = (struct tagPOINT)4LL;
    v338[1] = 0;
    if ( v123 )
      *(_OWORD *)&v338[0].x = *(_OWORD *)((char *)v123 + 36);
    CompressedData = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, _QWORD, __int64, struct tagPOINT *, int, __m128 *, __int128 *, int))(**((_QWORD **)v12 + 16) + 120LL))(
                       *((_QWORD *)v12 + 16),
                       *((_QWORD *)v12 + 17),
                       v309,
                       *((_QWORD *)v12 + 5),
                       v297,
                       v338,
                       3,
                       &v343,
                       &v283,
                       a8);
    if ( !v251 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)a3 + 4) + 16LL));
      v99 = v284;
      v126 = *((_QWORD *)a3 + 4);
      if ( v284 )
      {
        v127 = (*(__int64 (__fastcall **)(GpMemoryBitmap *, __m256i *))(*(_QWORD *)v284 + 48LL))(v284, &v282);
        --*(_DWORD *)(v126 + 60);
        v129 = v127;
        if ( v99 != *(GpMemoryBitmap **)(v126 + 88) )
          GpMemoryBitmap::`scalar deleting destructor'(v99, v128);
        v99 = 0;
        if ( v129 < 0 )
          MapHRESULTToGpStatus((unsigned int)v129);
      }
      GpBitmap::Unlock(a3);
    }
    if ( v312 )
      GpFree(v312);
    if ( *(_QWORD *)&v315[12] )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v315[12] + 16LL))(*(_QWORD *)&v315[12]);
    goto LABEL_131;
  }
  v212 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)a3 + 240LL))(a3);
  v213 = v212;
  if ( v212 > 0 && (v312 = GpMallocEx(v212, 0)) != 0 )
  {
    CompressedData = (*(__int64 (__fastcall **)(GpBitmap *, __int64, _QWORD))(*(_QWORD *)a3 + 224LL))(a3, v312, v213);
    if ( !CompressedData )
    {
      v123 = v268;
      if ( v253 )
        GpRecolor::ColorAdjust(*((_QWORD *)v268 + 3), v312 + 8, *(unsigned int *)(v312 + 4), 1);
      v121 = v249;
      goto LABEL_116;
    }
  }
  else
  {
    CompressedData = 3;
  }
  DpBitmap::~DpBitmap((DpBitmap *)v309);
LABEL_134:
  v138 = (_DWORD *)*((_QWORD *)v12 + 17);
  v139 = v291;
  v140 = v286;
  v141 = (int)ppstm;
  v138[40] = v290;
  v142 = v287;
  v138[41] = v139;
  v143 = v288;
  v138[42] = v140;
  v144 = v289;
  v138[46] = v141;
  v145 = v280;
  v138[43] = v142;
  v138[44] = v143;
  v138[45] = v144;
  v138[38] = 1952533809;
  *(_DWORD *)(*((_QWORD *)v12 + 17) + 288LL) = 0;
  if ( v145 )
    (*(void (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v145 + 56LL))(v145);
  if ( v269 )
    (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v269 + 56LL))(v269);
  return CompressedData;
}

```

## disassembly

```asm
0x1800127a8  mov     rax, rsp
0x1800127ab  push    rbp
0x1800127ac  push    rbx
0x1800127ad  push    rsi
0x1800127ae  push    rdi
0x1800127af  push    r12
0x1800127b1  push    r13
0x1800127b3  push    r14
0x1800127b5  push    r15
0x1800127b7  lea     rbp, [rax-4A8h]
0x1800127be  sub     rsp, 568h
0x1800127c5  movaps  xmmword ptr [rax-58h], xmm6
0x1800127c9  movaps  xmmword ptr [rax-68h], xmm7
0x1800127cd  movaps  xmmword ptr [rax-78h], xmm8
0x1800127d2  movaps  xmmword ptr [rax-88h], xmm9
0x1800127da  movaps  xmmword ptr [rax-98h], xmm10
0x1800127e2  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800127ea  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800127f2  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800127fa  movaps  xmmword ptr [rax-0D8h], xmm14
0x180012802  movaps  xmmword ptr [rax-0E8h], xmm15
0x18001280a  mov     rax, cs:__security_cookie
0x180012811  xor     rax, rsp
0x180012814  mov     [rbp+4A0h+var_E8], rax
0x18001281b  mov     rax, [rbp+4A0h+arg_30]
0x180012822  mov     r13d, 3
0x180012828  mov     rsi, [rbp+4A0h+arg_20]
0x18001282f  mov     r12, r8
0x180012832  mov     r14, [rbp+4A0h+arg_28]
0x180012839  mov     [rbp+4A0h+var_3C0], rdx
0x180012840  mov     [rsp+5A0h+var_530], rcx
0x180012845  mov     [rbp+4A0h+var_4A0], rax
0x180012849  cmp     r9d, r13d
0x18001284c  jnz     loc_180015285
0x180012852  mov     ebx, r13d
0x180012855  lea     rdi, [rbp+4A0h+var_160]
0x18001285c  lea     r15d, [r13-2]
0x180012860  mov     rcx, rdi; this
0x180012863  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180012868  add     rdi, 8
0x18001286c  sub     rbx, r15
0x18001286f  jnz     short loc_180012860
0x180012871  movups  xmm4, xmmword ptr [rsi]
0x180012874  mov     r15, [rsp+5A0h+var_530]
0x180012879  movups  xmm0, xmmword ptr [r14]
0x18001287d  movsd   xmm3, qword ptr [rsi+10h]
0x180012882  movaps  xmm5, xmm4
0x180012885  movdqu  xmmword ptr [rbp+4A0h+var_520], xmm0
0x18001288a  movsd   [rbp+4A0h+var_150], xmm3
0x180012892  movaps  xmm0, xmm4
0x180012895  movss   xmm1, dword ptr [rbp+4A0h+var_150+4]
0x18001289d  subss   xmm3, xmm4
0x1800128a1  shufps  xmm0, xmm4, 0AAh
0x1800128a5  movaps  xmm2, xmm4
0x1800128a8  subss   xmm5, xmm0
0x1800128ac  shufps  xmm2, xmm4, 55h ; 'U'
0x1800128b0  subss   xmm1, xmm2
0x1800128b4  movaps  xmm0, xmm4
0x1800128b7  shufps  xmm0, xmm4, 0FFh
0x1800128bb  subss   xmm2, xmm0
0x1800128bf  movss   xmm0, cs:__real@34000000
0x1800128c7  movups  [rbp+4A0h+var_160], xmm4
0x1800128ce  mulss   xmm5, xmm1
0x1800128d2  mulss   xmm2, xmm3
0x1800128d6  subss   xmm5, xmm2
0x1800128da  andps   xmm5, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800128e1  comiss  xmm0, xmm5
0x1800128e4  ja      loc_180014080
0x1800128ea  mov     rax, cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::MetaDriver
0x1800128f1  xor     r8d, r8d
0x1800128f4  cmp     [r15+80h], rax
0x1800128fb  mov     ebx, 1
0x180012900  mov     rdi, [rbp+4A0h+var_4A0]
0x180012904  setz    r8b
0x180012908  mov     [rbp+4A0h+var_480], r8d
0x18001290c  test    rdi, rdi
0x18001290f  jnz     loc_180013CE5
0x180012915  mov     [rbp+4A0h+var_508], 0
0x18001291c  test    r8d, r8d
0x18001291f  mov     eax, 0E200Bh
0x180012924  mov     ecx, 26200Ah
0x180012929  cmovnz  eax, ecx
0x18001292c  mov     [rsp+5A0h+var_528], eax
0x180012930  call    ?GenerateUniqueness@GpObject@@SA_JXZ; GpObject::GenerateUniqueness(void)
0x180012935  movss   xmm3, cs:__real@3f800000
0x18001293d  mov     rcx, rax
0x180012940  mov     rax, [r15+28h]
0x180012944  xorps   xmm9, xmm9
0x180012948  xorps   xmm11, xmm11
0x18001294c  movss   [rbp+4A0h+var_4F0], xmm9
0x180012952  movss   [rbp+4A0h+var_4EC], xmm11
0x180012958  xor     r14d, r14d
0x18001295b  mov     [rbp+4A0h+var_4DC], 0FFFFFFFFh
0x180012962  movaps  xmm7, xmm3
0x180012965  mov     [rax+1Ch], ecx
0x180012968  movaps  xmm8, xmm3
0x18001296c  movss   xmm4, [rbp+4A0h+var_520+4]
0x180012971  xor     ecx, ecx
0x180012973  movss   xmm5, [rbp+4A0h+var_520]
0x180012978  xor     eax, eax
0x18001297a  movss   xmm9, [rbp+4A0h+var_520+0Ch]
0x180012980  xorps   xmm10, xmm10
0x180012984  movss   xmm11, [rbp+4A0h+var_520+8]
0x18001298a  movaps  xmm2, xmm9
0x18001298e  movss   xmm15, dword ptr cs:__xmm@80000000800000008000000080000000
0x180012997  addss   xmm2, xmm4
0x18001299b  movss   xmm12, dword ptr [rbp+4A0h+var_160]
0x1800129a4  movaps  xmm0, xmm11
0x1800129a8  movss   xmm13, dword ptr [rbp+4A0h+var_160+4]
0x1800129b1  addss   xmm0, xmm5
0x1800129b5  movaps  xmm1, xmm9
0x1800129b9  mov     [rbp+4A0h+var_430], rax
0x1800129bd  xorps   xmm1, xmm15
0x1800129c1  mov     [rbp+4A0h+var_498], rcx
0x1800129c5  mulss   xmm1, xmm5
0x1800129c9  lea     rax, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1800129d0  mov     [rbp+4A0h+var_500], ecx
0x1800129d3  mulss   xmm2, xmm0
0x1800129d7  xorps   xmm6, xmm6
0x1800129da  mov     [rbp+4A0h+var_4E8], rax
0x1800129de  movaps  xmm0, xmm4
0x1800129e1  mov     dword ptr [rbp+4A0h+var_4C4+4], ecx
0x1800129e4  mulss   xmm0, xmm5
0x1800129e8  xorps   xmm14, xmm14
0x1800129ec  mov     [rbp+4A0h+var_4E0], 74614D31h
0x1800129f3  subss   xmm2, xmm0
0x1800129f7  movaps  xmm0, xmm4
0x1800129fa  mulss   xmm0, xmm11
0x1800129ff  subss   xmm1, xmm0
0x180012a03  addss   xmm2, xmm1
0x180012a07  movss   xmm1, cs:__real@34000000
0x180012a0f  movaps  xmm0, xmm2
0x180012a12  andps   xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180012a19  comiss  xmm1, xmm0
0x180012a1c  ja      loc_180012B5D
0x180012a22  divss   xmm3, xmm2
0x180012a26  lea     rcx, [rbp+4A0h+var_4E8]; this
0x180012a2a  movaps  xmm1, xmm9
0x180012a2e  movaps  xmm0, xmm9
0x180012a32  mulss   xmm0, dword ptr [rbp+4A0h+var_160+8]
0x180012a3a  xorps   xmm1, xmm15
0x180012a3e  movaps  xmm8, xmm1
0x180012a42  movaps  xmm2, xmm9
0x180012a46  mulss   xmm1, xmm13
0x180012a4b  addss   xmm2, xmm4
0x180012a4f  mulss   xmm8, xmm12
0x180012a54  movaps  xmm6, xmm5
0x180012a57  xorps   xmm6, xmm15
0x180012a5b  movaps  xmm7, xmm11
0x180012a5f  xorps   xmm7, xmm15
0x180012a63  mulss   xmm6, xmm9
0x180012a68  addss   xmm8, xmm0
0x180012a6d  movaps  xmm0, xmm9
0x180012a71  mulss   xmm0, dword ptr [rbp+4A0h+var_160+0Ch]
0x180012a79  movaps  xmm14, xmm6
0x180012a7d  mulss   xmm6, dword ptr [rbp+4A0h+var_160+0Ch]
0x180012a85  mulss   xmm14, dword ptr [rbp+4A0h+var_160+8]
0x180012a8e  addss   xmm1, xmm0
0x180012a92  movaps  xmm0, xmm11
0x180012a96  mulss   xmm8, xmm3
0x180012a9b  mulss   xmm0, dword ptr [rbp+4A0h+var_150]
0x180012aa3  mulss   xmm1, xmm3
0x180012aa7  movss   dword ptr [rbp+4A0h+var_4D8], xmm8
0x180012aad  movss   [rbp+4A0h+var_4EC], xmm1
0x180012ab2  movss   dword ptr [rbp+4A0h+var_4D8+4], xmm1
0x180012ab7  movaps  xmm1, xmm7
0x180012aba  mulss   xmm1, xmm12
0x180012abf  mulss   xmm7, xmm13
0x180012ac4  addss   xmm1, xmm0
0x180012ac8  movaps  xmm0, xmm11
0x180012acc  mulss   xmm0, dword ptr [rbp+4A0h+var_150+4]
0x180012ad4  mulss   xmm1, xmm3
0x180012ad8  addss   xmm7, xmm0
0x180012adc  movaps  xmm0, xmm11
0x180012ae0  addss   xmm0, xmm5
0x180012ae4  movss   [rbp+4A0h+var_4F0], xmm1
0x180012ae9  movss   dword ptr [rbp+4A0h+var_4D8+8], xmm1
0x180012aee  movaps  xmm1, xmm4
0x180012af1  mulss   xmm1, xmm5
0x180012af5  xorps   xmm4, xmm15
0x180012af9  mulss   xmm2, xmm0
0x180012afd  mulss   xmm4, xmm11
0x180012b02  subss   xmm2, xmm1
0x180012b06  mulss   xmm7, xmm3
0x180012b0a  movaps  xmm1, xmm4
0x180012b0d  mulss   xmm4, dword ptr [rbp+4A0h+var_150+4]
0x180012b15  mulss   xmm1, dword ptr [rbp+4A0h+var_150]
0x180012b1d  movaps  xmm0, xmm2
0x180012b20  movss   dword ptr [rbp+4A0h+var_4D8+0Ch], xmm7
0x180012b25  mulss   xmm0, xmm12
0x180012b2a  mulss   xmm2, xmm13
0x180012b2f  addss   xmm14, xmm0
0x180012b34  addss   xmm6, xmm2
0x180012b38  addss   xmm14, xmm1
0x180012b3d  addss   xmm6, xmm4
0x180012b41  mulss   xmm14, xmm3
0x180012b46  mulss   xmm6, xmm3
0x180012b4a  movss   [rbp+4A0h+var_4C8], xmm14
0x180012b50  movss   dword ptr [rbp+4A0h+var_4C4], xmm6
0x180012b55  call    ?ComputeComplexity@GpMatrix@@IEBAHXZ; GpMatrix::ComputeComplexity(void)
0x180012b5a  mov     dword ptr [rbp+4A0h+var_4C4+4], eax
0x180012b5d  mov     rax, [r15+88h]
0x180012b64  lea     rcx, [rbp+4A0h+var_4E8]; this
0x180012b68  movss   xmm13, [rbp+4A0h+var_4EC]
0x180012b6e  movaps  xmm0, xmm8
0x180012b72  movss   xmm11, [rbp+4A0h+var_4F0]
0x180012b78  movaps  xmm9, xmm13
0x180012b7c  movaps  xmm12, xmm11
0x180012b80  mulss   xmm0, dword ptr [rax+0A0h]
0x180012b88  mulss   xmm8, dword ptr [rax+0A4h]
0x180012b91  mulss   xmm9, dword ptr [rax+0A8h]
0x180012b9a  mulss   xmm13, dword ptr [rax+0ACh]
0x180012ba3  mulss   xmm12, dword ptr [rax+0A0h]
0x180012bac  addss   xmm9, xmm0
0x180012bb1  mulss   xmm11, dword ptr [rax+0A4h]
0x180012bba  addss   xmm13, xmm8
0x180012bbf  movaps  xmm0, xmm7
0x180012bc2  movaps  xmm8, xmm14
0x180012bc6  mulss   xmm0, dword ptr [rax+0A8h]
0x180012bce  mulss   xmm8, dword ptr [rax+0A0h]
0x180012bd7  mulss   xmm14, dword ptr [rax+0A4h]
0x180012be0  addss   xmm12, xmm0
0x180012be5  mulss   xmm7, dword ptr [rax+0ACh]
0x180012bed  movaps  xmm0, xmm6
0x180012bf0  mulss   xmm0, dword ptr [rax+0A8h]
0x180012bf8  mulss   xmm6, dword ptr [rax+0ACh]
0x180012c00  addss   xmm11, xmm7
0x180012c05  addss   xmm8, xmm0
0x180012c0a  movss   [rbp+4A0h+var_4B8], xmm9
0x180012c10  movss   [rbp+4A0h+var_4EC], xmm13
0x180012c16  addss   xmm14, xmm6
0x180012c1b  movss   [rbp+4A0h+var_4B4], xmm12
0x180012c21  movss   [rbp+4A0h+var_4F0], xmm11
0x180012c27  movss   dword ptr [rbp+4A0h+var_4D8], xmm9
0x180012c2d  addss   xmm8, dword ptr [rax+0B0h]
0x180012c36  movss   dword ptr [rbp+4A0h+var_4D8+4], xmm13
0x180012c3c  addss   xmm14, dword ptr [rax+0B4h]
0x180012c45  movss   dword ptr [rbp+4A0h+var_4D8+8], xmm12
0x180012c4b  movss   dword ptr [rbp+4A0h+var_4D8+0Ch], xmm11
0x180012c51  movss   [rbp+4A0h+var_50C], xmm8
0x180012c57  movss   [rbp+4A0h+var_4C8], xmm8
0x180012c5d  movss   [rbp+4A0h+var_504], xmm14
0x180012c63  movss   dword ptr [rbp+4A0h+var_4C4], xmm14
0x180012c69  call    ?ComputeComplexity@GpMatrix@@IEBAHXZ; GpMatrix::ComputeComplexity(void)
0x180012c6e  movdqa  xmm6, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180012c76  movaps  xmm1, xmm11
0x180012c7a  movaps  xmm0, xmm12
0x180012c7e  mulss   xmm1, xmm9
0x180012c83  mov     esi, eax
0x180012c85  mov     [rbp+4A0h+var_510], eax
0x180012c88  movss   xmm12, cs:__real@34000000
0x180012c91  mulss   xmm0, xmm13
0x180012c96  mov     dword ptr [rbp+4A0h+var_4C4+4], eax
0x180012c99  subss   xmm1, xmm0
0x180012c9d  andps   xmm1, xmm6
0x180012ca0  comiss  xmm12, xmm1
0x180012ca4  ja      loc_180014080
0x180012caa  mov     rax, [r15+88h]
0x180012cb1  cmp     dword ptr [rax+34h], 4
0x180012cb5  jnz     loc_180013CD2
0x180012cbb  mov     [rbp+4A0h+var_4B0], ebx
0x180012cbe  cmp     [r15+40h], r14d
0x180012cc2  jnz     loc_18001528F
0x180012cc8  mov     rax, [r15+88h]
0x180012ccf  xor     ecx, ecx
0x180012cd1  mov     [rbp+4A0h+var_438], rcx
0x180012cd5  movss   xmm0, dword ptr [rax+0A0h]
0x180012cdd  movss   [rbp+4A0h+var_3DC], xmm0
0x180012ce5  movss   xmm0, dword ptr [rax+0A4h]
0x180012ced  movss   [rbp+4A0h+var_3D8], xmm0
0x180012cf5  movss   xmm0, dword ptr [rax+0A8h]
0x180012cfd  movss   [rbp+4A0h+var_3EC], xmm0
0x180012d05  movss   xmm0, dword ptr [rax+0ACh]
0x180012d0d  movss   [rbp+4A0h+var_3E8], xmm0
0x180012d15  movss   xmm0, dword ptr [rax+0B0h]
0x180012d1d  movss   [rbp+4A0h+var_3E4], xmm0
0x180012d25  movss   xmm0, dword ptr [rax+0B4h]
0x180012d2d  mov     eax, [rax+0B8h]
0x180012d33  mov     dword ptr [rbp+4A0h+ppstm], eax
0x180012d36  mov     rax, [r15+88h]
0x180012d3d  movss   [rbp+4A0h+var_3E0], xmm0
0x180012d45  mov     [rax+120h], ecx
0x180012d4b  lea     rcx, [rbp+4A0h+var_4E8]; this
0x180012d4f  call    ?IsIntegerTranslate@GpMatrix@@QEBAHXZ; GpMatrix::IsIntegerTranslate(void)
0x180012d54  movss   xmm9, cs:__real@3f000000
0x180012d5d  test    eax, eax
0x180012d5f  jz      loc_180013D1D
0x180012d65  test    esi, 0FFFFFFFCh
0x180012d6b  jz      loc_180012F4F
0x180012d71  cmp     [rbp+4A0h+var_480], 0
0x180012d75  jnz     loc_180012F4F
0x180012d7b  mov     rax, [r15+88h]
0x180012d82  cmp     dword ptr [rax+30h], 7
0x180012d86  jnz     loc_180012F45
0x180012d8c  cmp     dword ptr [r15+40h], 0
0x180012d91  jnz     loc_180014894
0x180012d97  mov     rbx, r13
0x180012d9a  lea     rdi, [rbp+4A0h+var_118]
0x180012da1  mov     esi, 1
0x180012da6  mov     rcx, rdi; this
  ... truncated ...
```
