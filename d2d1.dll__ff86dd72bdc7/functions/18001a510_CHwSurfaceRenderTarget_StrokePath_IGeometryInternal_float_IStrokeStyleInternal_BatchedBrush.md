# CHwSurfaceRenderTarget::StrokePath(IGeometryInternal *,float,IStrokeStyleInternal *,BatchedBrush *)

- ea: `0x18001a510`
- end: `0x18001d4b4`
- name: `?StrokePath@CHwSurfaceRenderTarget@@UEAAJPEAVIGeometryInternal@@MPEAVIStrokeStyleInternal@@PEAUBatchedBrush@@@Z`
- size: `12196`
- prototype: `__int64 __fastcall(CHwSurfaceRenderTarget *__hidden this, struct IGeometryInternal *, float, struct IStrokeStyleInternal *, struct BatchedBrush *)`
- caller_count: `0`
- callee_count: `44`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009860`
- `0x1800152a0`
- `0x180018ea0`
- `0x18001a390`
- `0x18001a510`
- `0x18001d4bc`
- `0x18001d570`
- `0x18001d5a0`
- `0x18001dc30`
- `0x18001ea50`
- `0x18001eab0`
- `0x18001fd58`
- `0x18006e0f0`
- `0x18007fcc0`
- `0x1800865f0`
- `0x18008e890`
- `0x1800905c0`
- `0x180091db0`
- `0x180091dd0`
- `0x180097b90`
- `0x1800b65e0`
- `0x1800c60f0`
- `0x1800d02f8`
- `0x1800d6140`
- `0x1800d7df0`
- `0x1800dc6f4`
- `0x1800dc760`
- `0x1800e7be0`
- `0x18013a54c`
- `0x18013a680`
- `0x180144144`
- `0x180144540`
- `0x180148b00`
- `0x180193050`
- `0x1801ceadc`
- `0x1801fd630`
- `0x18025b100`
- `0x18025b124`
- `0x18025b148`
- `0x18025bb68`
- `0x18025c96d`
- `0x18027a800`
- `0x18027a814`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c14c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c28f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cb18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c14c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c28f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cb18`

## pseudocode

```c
__int64 __fastcall CHwSurfaceRenderTarget::StrokePath(
        CHwSurfaceRenderTarget *this,
        struct IGeometryInternal *a2,
        float a3,
        struct IStrokeStyleInternal *a4,
        struct BatchedBrush *a5)
{
  struct BatchedBrush *v5; // rsi
  char v6; // r12
  struct IStrokeStyleInternal *v7; // rbx
  float v8; // xmm6_4
  struct IGeometryInternal *v9; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rax
  __m128 v13; // xmm2
  __int64 v14; // rax
  __int64 (__fastcall *v15)(CHwSurfaceRenderTarget *); // rax
  float v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // r13
  __int64 v22; // rdi
  char *v23; // rsi
  int v24; // eax
  __int128 v25; // xmm1
  struct D2D_RECT_F v26; // xmm0
  __m128 v27; // xmm5
  __m128i v28; // xmm1
  __m128 v29; // xmm6
  __m128 v30; // xmm2
  __m128i v31; // xmm0
  __m128i v32; // xmm3
  float v33; // xmm2_4
  __m128 v34; // xmm6
  float v35; // xmm7_4
  float v36; // xmm5_4
  float v37; // xmm4_4
  float v38; // xmm0_4
  float v39; // xmm1_4
  float v40; // xmm0_4
  float v41; // xmm1_4
  float v42; // xmm3_4
  float v43; // xmm2_4
  float v44; // xmm0_4
  int v45; // ebx
  float v46; // xmm0_4
  float v47; // xmm2_4
  float v48; // xmm4_4
  float v49; // xmm1_4
  float v50; // xmm3_4
  float v51; // xmm2_4
  int v52; // r9d
  int v53; // r8d
  int v54; // edx
  int v55; // ecx
  float v56; // xmm3_4
  float v57; // xmm1_4
  float v58; // xmm6_4
  float v59; // xmm2_4
  int v60; // r9d
  int v61; // r8d
  int v62; // edx
  int v63; // ecx
  float v64; // xmm2_4
  unsigned int v65; // eax
  unsigned int v66; // r8d
  unsigned int v67; // r10d
  unsigned int v68; // edx
  int v69; // eax
  __int64 v70; // rax
  __int64 *v71; // rax
  __int64 v72; // rdi
  float *v73; // rbx
  __int64 v74; // rcx
  _QWORD *v75; // r8
  __int64 v76; // rax
  _QWORD *v77; // rdx
  float v78; // xmm3_4
  float v79; // xmm2_4
  float v80; // xmm4_4
  float v81; // xmm5_4
  __m128 v82; // xmm0
  __m128 v83; // xmm0
  __m128 v84; // xmm0
  float v85; // xmm4_4
  float v86; // xmm5_4
  __m128i v87; // xmm1
  __m128 v88; // xmm4
  __m128 v89; // xmm2
  __m128 v90; // xmm3
  float v91; // xmm1_4
  int v92; // eax
  float v93; // xmm2_4
  int v94; // r8d
  float v95; // xmm4_4
  int v96; // r9d
  int v97; // eax
  int v98; // eax
  int v99; // eax
  __int64 *v100; // r15
  int v101; // ebx
  int v102; // eax
  int v103; // edx
  int v104; // r9d
  __int64 *v105; // rcx
  __int64 *v106; // rcx
  float *v107; // r13
  float v108; // xmm12_4
  float v109; // xmm11_4
  __int64 v110; // rax
  __m128i v111; // xmm9
  __m128i v112; // xmm7
  unsigned __int32 v113; // xmm14_4
  float v114; // xmm15_4
  __m128i v115; // xmm8
  __m128i v116; // xmm6
  struct IStrokeStyleInternal *v117; // rsi
  __int128 *v118; // rax
  unsigned int v119; // eax
  __int64 v120; // rdi
  int v121; // eax
  int v122; // ebx
  void *v123; // r15
  float v124; // xmm10_4
  enum D2D1_DASH_STYLE v125; // esi
  unsigned int v126; // esi
  int v127; // r8d
  int v128; // eax
  unsigned int v129; // ecx
  float v130; // xmm7_4
  unsigned int v131; // r8d
  int v132; // xmm6_4
  int v133; // eax
  __int64 v134; // rsi
  __int64 v135; // rax
  enum DXGI_FORMAT v136; // eax
  unsigned int v137; // edi
  unsigned int i; // r8d
  __int64 v139; // rbx
  __int64 v140; // r15
  __int64 v141; // rcx
  __int64 v142; // r9
  struct WeakReferenceable *v143; // rdi
  _QWORD *v144; // rbx
  _QWORD *v145; // rcx
  struct WeakReferenceable *v146; // rdx
  struct WeakReferenceable *v147; // rdx
  float v148; // xmm0_4
  float v149; // xmm2_4
  float v150; // xmm11_4
  float v151; // xmm10_4
  float v152; // xmm1_4
  float *v153; // rbx
  int v154; // xmm10_4
  int v155; // xmm1_4
  float v156; // xmm1_4
  float v157; // xmm12_4
  float v158; // xmm0_4
  float v159; // xmm12_4
  float v160; // xmm2_4
  float v161; // xmm11_4
  float v162; // xmm14_4
  float v163; // xmm15_4
  float v164; // xmm13_4
  float v165; // xmm8_4
  float v166; // xmm7_4
  float v167; // xmm10_4
  float v168; // xmm11_4
  float v169; // xmm2_4
  float v170; // xmm5_4
  float v171; // xmm1_4
  float v172; // xmm5_4
  float v173; // xmm9_4
  float v174; // xmm0_4
  float v175; // xmm4_4
  float v176; // xmm10_4
  float v177; // xmm11_4
  float v178; // xmm2_4
  float v179; // xmm0_4
  float v180; // xmm2_4
  bool v181; // si
  int v182; // ebx
  __int64 v183; // rax
  struct BatchedBrush *v184; // rbx
  __m128 v185; // xmm13
  __m128 v186; // xmm11
  __m128 v187; // xmm10
  unsigned int v188; // edi
  __int64 v189; // rax
  const unsigned __int16 *v190; // rdx
  __int64 v191; // r9
  __int64 v192; // rcx
  const struct D2D_RECT_F *v193; // r8
  int v194; // eax
  float v195; // xmm0_4
  float v196; // xmm2_4
  float v197; // xmm1_4
  char v198; // bl
  char v199; // al
  int v200; // edi
  char v201; // al
  double v202; // xmm12_8
  __m128 v203; // xmm10
  struct D2D_SIZE_U v204; // rbx
  void ***v205; // rdx
  unsigned int v206; // esi
  __int64 v207; // rax
  __int64 *v208; // rdi
  __int64 v209; // rdi
  _QWORD *v210; // rcx
  _QWORD *v211; // rax
  __int64 v212; // rdx
  _QWORD *v213; // rbx
  int v214; // eax
  int v215; // ebx
  float v217; // xmm2_4
  float v218; // xmm3_4
  float v219; // xmm1_4
  float v220; // xmm4_4
  LONG v221; // edx
  LONG v222; // ecx
  LONG v223; // r8d
  CConvexFigureStorage *v224; // r15
  int v225; // eax
  int v226; // eax
  float v227; // xmm0_4
  bool v228; // zf
  enum DXGI_FORMAT DxgiFormatInternal; // eax
  int v230; // eax
  unsigned int v231; // edi
  float v232; // xmm2_4
  float v233; // xmm0_4
  struct IStrokeStyleInternal *v234; // rbx
  int v235; // eax
  int v236; // ecx
  float v237; // xmm12_4
  float v238; // xmm2_4
  float v239; // xmm11_4
  float v240; // xmm1_4
  float v241; // xmm1_4
  float v242; // xmm1_4
  float v243; // xmm0_4
  __int64 v244; // rcx
  unsigned int v245; // esi
  _DWORD *v246; // rbx
  __int64 v247; // rdi
  int v248; // eax
  float v249; // xmm0_4
  float v250; // xmm2_4
  float v251; // xmm1_4
  void *v252; // rcx
  int Strip; // eax
  __int64 v254; // rax
  __int64 (__fastcall *v255)(CHwSurfaceRenderTarget *, _DWORD *, __int64 *, __int64, int, _QWORD); // rdi
  int v256; // ebx
  __int64 v257; // rax
  float *v258; // rcx
  float *v259; // r15
  __int64 v260; // rcx
  const struct D2D_RECT_F *v261; // rax
  int v262; // ecx
  float v263; // xmm2_4
  float v264; // xmm0_4
  struct IGeometryInternal *v265; // rbx
  __int64 v266; // rax
  const struct D2D1_ROUNDED_RECT *v267; // rax
  float v268; // xmm13_4
  struct D2D_SIZE_F v269; // xmm10_8
  __int64 v270; // rax
  DrawRectangleTessellator *v271; // rbx
  float v272; // xmm0_4
  int v273; // r8d
  CShapeBase *v274; // rax
  enum D2D1_ANTIALIAS_MODE v275; // edx
  float v276; // xmm0_4
  int v277; // eax
  struct WeakReferenceable *v278; // rdx
  unsigned int v279; // ebx
  int v280; // eax
  int v281; // eax
  __int64 *v282; // rax
  enum D2D1_STROKE_TRANSFORM_TYPE v283; // r9d
  __int64 v284; // rcx
  struct D2D_SIZE_F v285; // [rsp+28h] [rbp-E0h]
  enum D3D11_CULL_MODE v286; // [rsp+28h] [rbp-E0h]
  enum D3D11_CULL_MODE v287; // [rsp+28h] [rbp-E0h]
  char *v288; // [rsp+30h] [rbp-D8h]
  bool v290[8]; // [rsp+5Ch] [rbp-ACh] BYREF
  struct tagRECT v291; // [rsp+68h] [rbp-A0h] BYREF
  struct BatchedBrush *v292; // [rsp+78h] [rbp-90h]
  struct WeakReferenceable *v293; // [rsp+80h] [rbp-88h] BYREF
  float *v294; // [rsp+88h] [rbp-80h] BYREF
  struct IStrokeStyleInternal *v295; // [rsp+90h] [rbp-78h]
  float v296; // [rsp+98h] [rbp-70h]
  _QWORD *v297; // [rsp+A0h] [rbp-68h] BYREF
  float *v298; // [rsp+A8h] [rbp-60h] BYREF
  float *v299; // [rsp+B0h] [rbp-58h] BYREF
  float v300; // [rsp+B8h] [rbp-50h]
  struct IGeometryInternal *v301; // [rsp+C0h] [rbp-48h]
  DrawRectangleTessellator *v302; // [rsp+C8h] [rbp-40h] BYREF
  void *v303[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v304; // [rsp+E0h] [rbp-28h] BYREF
  int v305; // [rsp+E8h] [rbp-20h]
  __m128i v306; // [rsp+F8h] [rbp-10h]
  float v307; // [rsp+108h] [rbp+0h]
  __int64 v308; // [rsp+10Ch] [rbp+4h]
  __int64 v309; // [rsp+114h] [rbp+Ch]
  int v310; // [rsp+11Ch] [rbp+14h]
  unsigned __int64 v311; // [rsp+120h] [rbp+18h]
  __int64 v312; // [rsp+128h] [rbp+20h]
  int v313; // [rsp+130h] [rbp+28h]
  void *Block[2]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v315; // [rsp+148h] [rbp+40h]
  unsigned int v316; // [rsp+150h] [rbp+48h]
  int v317; // [rsp+158h] [rbp+50h] BYREF
  __int64 v318; // [rsp+160h] [rbp+58h] BYREF
  unsigned int v319[2]; // [rsp+168h] [rbp+60h] BYREF
  __int64 v320; // [rsp+170h] [rbp+68h] BYREF
  __int64 v321; // [rsp+178h] [rbp+70h] BYREF
  float *v322; // [rsp+180h] [rbp+78h] BYREF
  __int64 v323; // [rsp+188h] [rbp+80h] BYREF
  __int64 v324; // [rsp+190h] [rbp+88h] BYREF
  int v325[2]; // [rsp+198h] [rbp+90h]
  __int64 v326; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v327; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v328; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v329; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v330; // [rsp+1C0h] [rbp+B8h]
  unsigned __int32 v331; // [rsp+1D0h] [rbp+C8h]
  _BYTE v332[20]; // [rsp+1D8h] [rbp+D0h]
  __int64 v333; // [rsp+1F0h] [rbp+E8h] BYREF
  __m128 v334; // [rsp+1F8h] [rbp+F0h]
  _QWORD v335[5]; // [rsp+208h] [rbp+100h] BYREF
  int v336; // [rsp+230h] [rbp+128h]
  __int64 v337; // [rsp+238h] [rbp+130h]
  __int128 *v338; // [rsp+240h] [rbp+138h]
  void **v339; // [rsp+248h] [rbp+140h] BYREF
  float v340; // [rsp+250h] [rbp+148h]
  struct IStrokeStyleInternal *v341; // [rsp+258h] [rbp+150h]
  __int64 *v342; // [rsp+260h] [rbp+158h]
  float *v343; // [rsp+268h] [rbp+160h]
  int v344; // [rsp+270h] [rbp+168h]
  char *v345; // [rsp+278h] [rbp+170h]
  float v346; // [rsp+280h] [rbp+178h]
  __int32 v347; // [rsp+284h] [rbp+17Ch]
  enum D2D1_ANTIALIAS_MODE v348; // [rsp+290h] [rbp+188h]
  int v349; // [rsp+294h] [rbp+18Ch]
  __int128 v350; // [rsp+298h] [rbp+190h]
  __int128 v351; // [rsp+2A8h] [rbp+1A0h]
  char v352[8]; // [rsp+2B8h] [rbp+1B0h] BYREF
  unsigned int v353; // [rsp+2C0h] [rbp+1B8h] BYREF
  unsigned int v354; // [rsp+2C4h] [rbp+1BCh]
  unsigned int v355; // [rsp+2C8h] [rbp+1C0h]
  unsigned int v356; // [rsp+2CCh] [rbp+1C4h]
  __m128i si128; // [rsp+2D0h] [rbp+1C8h] BYREF
  _DWORD v358[4]; // [rsp+2E0h] [rbp+1D8h] BYREF
  struct D2D_RECT_F v359; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int64 v360; // [rsp+300h] [rbp+1F8h]
  void **v361; // [rsp+308h] [rbp+200h] BYREF
  void **v362; // [rsp+310h] [rbp+208h]
  CConvexFigureStorage *v363; // [rsp+318h] [rbp+210h]
  __int32 v364; // [rsp+338h] [rbp+230h]
  __int32 v365; // [rsp+33Ch] [rbp+234h]
  __int32 v366; // [rsp+340h] [rbp+238h]
  __int32 v367; // [rsp+344h] [rbp+23Ch]
  void **v368; // [rsp+348h] [rbp+240h] BYREF
  void **v369; // [rsp+350h] [rbp+248h]
  __int128 v370; // [rsp+3A0h] [rbp+298h]
  __int64 v371; // [rsp+3B0h] [rbp+2A8h]
  int v372; // [rsp+3D0h] [rbp+2C8h]
  __int128 v373; // [rsp+3D8h] [rbp+2D0h]
  __int32 v374; // [rsp+3E8h] [rbp+2E0h]
  __int32 v375; // [rsp+3ECh] [rbp+2E4h]
  char v376[16]; // [rsp+408h] [rbp+300h] BYREF
  _QWORD v377[10]; // [rsp+418h] [rbp+310h] BYREF
  char v378[24]; // [rsp+468h] [rbp+360h] BYREF
  char v379[32]; // [rsp+480h] [rbp+378h] BYREF
  char v380[32]; // [rsp+4A0h] [rbp+398h] BYREF
  char v381[32]; // [rsp+4C0h] [rbp+3B8h] BYREF
  char v382[32]; // [rsp+4E0h] [rbp+3D8h] BYREF

  v5 = a5;
  v6 = 0;
  v301 = a2;
  v7 = a4;
  v8 = a3;
  *(_DWORD *)&v290[4] = 0;
  v9 = a2;
  v295 = a4;
  v292 = a5;
  *(_QWORD *)&v291.left = this;
  LOWORD(v291.right) = 1;
  if ( *((_BYTE *)this + 156) )
  {
    v11 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 576LL))(this);
    if ( !v11 || (*((_DWORD *)this + 25) == 1 ? (v12 = (_QWORD *)(v11 + 392)) : (v12 = (_QWORD *)(v11 + 304)), !*v12) )
    {
      v134 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 576LL))(this);
      v135 = *(_QWORD *)(v134 + 64);
      if ( !v135 || dword_1805DBFF0 == -1 )
        v136 = TransformFormat(*(enum DXGI_FORMAT *)(v134 + 100), *(struct CD3DDeviceCommon **)(v134 + 72));
      else
        v136 = *(_DWORD *)(v135 + 120);
      v137 = -1;
      for ( i = 0; i < 0x1C; ++i )
      {
        if ( v136 == dword_18030EAE0[10 * i] )
        {
          v137 = i;
          break;
        }
      }
      v139 = *(_QWORD *)(v134 + 84);
      v293 = 0;
      if ( (unsigned int)v139 <= HIDWORD(v139) )
        LODWORD(v139) = HIDWORD(v139);
      v140 = (*(unsigned int (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 616LL))(this);
      v141 = *((_QWORD *)this + 2 * v137 + v140 + 41);
      if ( !v141 || dword_1805DC040 == -1 || *(_DWORD *)(v141 + 60) < (unsigned int)v139 )
      {
        DxgiFormatInternal = BitmapRealization::GetDxgiFormatInternal((BitmapRealization *)v134);
        v230 = CreateRefObject<ListElem<RTSubTargetState,null_type>,CBaseRenderTarget *,enum DXGI_FORMAT,enum ContentFlags::Flags,unsigned int>(
                 (_DWORD)this,
                 DxgiFormatInternal,
                 v140,
                 v139,
                 (__int64)&v293);
        v45 = v230;
        if ( v230 < 0 )
        {
          DoStackCapture(v230);
          if ( v293 )
          {
            (*(void (__fastcall **)(char *))(*((_QWORD *)v293 + 4) + 8LL))((char *)v293 + 32);
            v293 = 0;
          }
          DoStackCapture(v45);
          goto LABEL_312;
        }
      }
      else
      {
        v326 = 0;
        std::swap<win_dox::IXpsOMPackageTargetInternal *,0>(&v326, &v293);
        v293 = (struct WeakReferenceable *)*((_QWORD *)this + v142 + 41);
        *((_QWORD *)this + v142 + 41) = 0;
        if ( v326 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v326 + 32) + 8LL))(v326 + 32);
          v326 = 0;
        }
      }
      v143 = v293;
      if ( *((_DWORD *)this + 25) == 1 )
      {
        v278 = v293;
        *(_QWORD *)(v134 + 392) = v293;
        WeakReferenceBase::SetReference((WeakReferenceBase *)(v134 + 360), v278);
      }
      else
      {
        *(_QWORD *)(v134 + 304) = v293;
        v144 = (_QWORD *)(v134 + 280);
        **(_QWORD **)(v134 + 288) = *(_QWORD *)(v134 + 280);
        *(_QWORD *)(*(_QWORD *)(v134 + 280) + 8LL) = *(_QWORD *)(v134 + 288);
        *(_QWORD *)(v134 + 288) = v134 + 280;
        *(_QWORD *)(v134 + 280) = v134 + 280;
        v145 = *(_QWORD **)(v134 + 296);
        if ( v145 && (_QWORD *)v145[1] == v145 + 1 )
          (*(void (__fastcall **)(_QWORD *))(*v145 + 8LL))(v145);
        *(_QWORD *)(v134 + 296) = v143;
        if ( v143 )
        {
          v146 = (struct WeakReferenceable *)*((_QWORD *)v143 + 1);
          **(_QWORD **)(v134 + 288) = *(_QWORD *)(v134 + 280);
          *(_QWORD *)(*(_QWORD *)(v134 + 280) + 8LL) = *(_QWORD *)(v134 + 288);
          *(_QWORD *)(v134 + 288) = v134 + 280;
          *v144 = v144;
          *(_QWORD *)(*((_QWORD *)v143 + 1) + 8LL) = v144;
          *v144 = *((_QWORD *)v143 + 1);
          *(_QWORD *)(v134 + 288) = (char *)v143 + 8;
          *((_QWORD *)v143 + 1) = v144;
          if ( v146 == (struct WeakReferenceable *)((char *)v143 + 8) )
            (*(void (__fastcall **)(struct WeakReferenceable *))(*(_QWORD *)v143 + 16LL))(v143);
        }
      }
      v147 = v293;
      v293 = 0;
      v147 = (struct WeakReferenceable *)((char *)v147 + 200);
      **((_QWORD **)v147 + 1) = *(_QWORD *)v147;
      *(_QWORD *)(*(_QWORD *)v147 + 8LL) = *((_QWORD *)v147 + 1);
      *((_QWORD *)v147 + 1) = v147;
      *(_QWORD *)v147 = v147;
      *(_QWORD *)(*((_QWORD *)this + 38) + 8LL) = v147;
      *(_QWORD *)v147 = *((_QWORD *)this + 38);
      *((_QWORD *)v147 + 1) = (char *)this + 304;
      *((_QWORD *)this + 38) = v147;
      if ( v293 )
      {
        (*(void (__fastcall **)(char *))(*((_QWORD *)v293 + 4) + 8LL))((char *)v293 + 32);
        v293 = 0;
      }
    }
    (*(void (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 576LL))(this);
    v334 = 0;
    v334 = *((__m128 *)this + 10);
    v13 = v334;
    v299 = 0;
    v14 = *(_QWORD *)this;
    DWORD1(v330) = v334.m128_i32[0];
    DWORD2(v330) = _mm_shuffle_ps(v13, v13, 85).m128_u32[0];
    HIDWORD(v330) = _mm_shuffle_ps(v13, v13, 170).m128_u32[0];
    v15 = *(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(v14 + 600);
    v331 = _mm_shuffle_ps(v13, v13, 255).m128_u32[0];
    LOBYTE(v330) = 1;
    LODWORD(v16) = v15(this);
    v17 = *(_QWORD *)this;
    v296 = v16;
    v18 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(v17 + 576))(this);
    if ( v18 )
    {
      if ( *((_DWORD *)this + 25) == 1 )
        v19 = (__int64 *)(v18 + 392);
      else
        v19 = (__int64 *)(v18 + 304);
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    v21 = *((_QWORD *)this + 6);
    v22 = *((_QWORD *)this + 5);
    v294 = 0;
    v23 = (char *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 )
    {
      v24 = *((_DWORD *)this + 198);
      v25 = *(_OWORD *)((char *)this + 776);
      *((_DWORD *)v23 + 6) = 1;
      v26 = Clip::msc_nullClip;
      v23[28] = 0;
      *((struct D2D_RECT_F *)v23 + 2) = v26;
      *((_OWORD *)v23 + 3) = v25;
      *((_DWORD *)v23 + 16) = v24;
      *(_QWORD *)v23 = &ClipRectSubTarget::`vftable';
      *((_QWORD *)v23 + 11) = 0;
      *((_QWORD *)v23 + 12) = 0;
      *((_QWORD *)v23 + 13) = 0;
      *((_QWORD *)v23 + 14) = 0;
      *((_QWORD *)v23 + 15) = 0;
      *((_QWORD *)v23 + 16) = 0;
      *((_QWORD *)v23 + 17) = v20;
      win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(v23 + 144);
      win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(v23 + 152);
      win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(v23 + 160);
      win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(v23 + 168);
      *((float *)v23 + 48) = v296;
      v320 = 0;
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
        v320 = v22;
      }
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v320,
        v23 + 88);
      if ( v320 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v320 + 16LL))(v320);
        v320 = 0;
      }
      v321 = 0;
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
        v321 = v21;
      }
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v321,
        v23 + 96);
      if ( v321 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v321 + 16LL))(v321);
        v321 = 0;
      }
      *((_OWORD *)v23 + 11) = 0;
      *(_QWORD *)v23 = &RefCountedObject<ClipRectSubTarget,LockingRequired,DeleteOnZeroReference>::`vftable';
      *((_DWORD *)v23 + 50) = 1;
    }
    else
    {
      v23 = 0;
    }
    v327 = 0;
    win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
      &v327,
      &v294);
    if ( v327 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v327 + 8LL))(v327);
      v327 = 0;
    }
    v294 = (float *)v23;
    if ( !v23 )
    {
      DoStackCapture(-2147024882);
      if ( v294 )
      {
        (*(void (__fastcall **)(float *))(*(_QWORD *)v294 + 8LL))(v294);
        v294 = 0;
      }
      v45 = -2147024882;
LABEL_183:
      DoStackCapture(v45);
      if ( v299 )
      {
        (*(void (__fastcall **)(float *))(*(_QWORD *)v299 + 8LL))(v299);
        v299 = 0;
      }
      if ( v45 >= 0 )
      {
LABEL_125:
        v8 = a3;
        v6 = 1;
        v9 = v301;
        v5 = v292;
        v7 = v295;
        BYTE1(v291.right) = 1;
        goto LABEL_126;
      }
LABEL_312:
      DoStackCapture(v45);
      goto LABEL_313;
    }
    LODWORD(v304) = v331;
    *(_OWORD *)v303 = v330;
    std::swap<bool,0>(v23 + 28, v303);
    std::swap<float,0>(v23 + 36, &v303[1]);
    std::swap<float,0>(v23 + 32, (char *)v303 + 4);
    std::swap<float,0>(v23 + 44, &v304);
    std::swap<float,0>(v23 + 40, (char *)&v303[1] + 4);
    v27 = *(__m128 *)(v23 + 52);
    v28 = _mm_cvtps_epi32(v27);
    v29 = (__m128)_mm_cmpgt_epi32((__m128i)_mm_and_ps(v27, (__m128)xmmword_1803875D0), (__m128i)xmmword_1803875E0);
    v30 = _mm_cvtepi32_ps(v28);
    v31 = (__m128i)_mm_and_ps(_mm_cmplt_ps(v27, v30), (__m128)xmmword_1803875F0);
    v32 = (__m128i)_mm_andnot_ps((__m128)xmmword_1803875F0, _mm_cmplt_ps(v30, v27));
    v33 = *((float *)v23 + 8);
    v34 = _mm_or_ps(
            _mm_andnot_ps(v29, _mm_cvtepi32_ps(_mm_sub_epi32(_mm_add_epi32(v31, v28), v32))),
            _mm_and_ps(v29, v27));
    v35 = _mm_shuffle_ps(v34, v34, 170).m128_f32[0];
    LODWORD(v36) = _mm_shuffle_ps(v34, v34, 85).m128_u32[0];
    LODWORD(v37) = _mm_shuffle_ps(v34, v34, 255).m128_u32[0];
    if ( v35 < v33 )
      v33 = v35;
    v38 = *((float *)v23 + 9);
    if ( v37 < v38 )
      v38 = v37;
    *((float *)v23 + 9) = v38;
    v39 = *((float *)v23 + 10);
    if ( v39 < v34.m128_f32[0] )
      v39 = v34.m128_f32[0];
    *((float *)v23 + 10) = v39;
    v40 = *((float *)v23 + 11);
    if ( v40 < v36 )
      v40 = v36;
    *((float *)v23 + 11) = v40;
    if ( v33 < v34.m128_f32[0] )
      v33 = v34.m128_f32[0];
    *((float *)v23 + 8) = v33;
    v41 = *((float *)v23 + 9);
    if ( v41 < v36 )
      v41 = v36;
    *((float *)v23 + 9) = v41;
    v42 = *((float *)v23 + 10);
    if ( v35 < v42 )
      v42 = v35;
    *((float *)v23 + 10) = v42;
    v43 = *((float *)v23 + 11);
    if ( v37 < v43 )
      v43 = v37;
    *((float *)v23 + 11) = v43;
    v44 = *((float *)v23 + 8);
    if ( v42 <= v44 || v43 <= v41 )
    {
      v43 = v41;
      v42 = *((float *)v23 + 8);
    }
    *((float *)v23 + 8) = v44;
    *((float *)v23 + 9) = v41;
    *((float *)v23 + 10) = v42;
    *((float *)v23 + 11) = v43;
    v45 = 0;
    *(_OWORD *)(v23 + 72) = *((_OWORD *)v23 + 2);
    v46 = *((float *)v23 + 18);
    v47 = (float)*((int *)this + 8);
    v48 = (float)*((int *)this + 9);
    if ( v46 < 0.0 )
      v46 = 0.0;
    *((float *)v23 + 18) = v46;
    v49 = *((float *)v23 + 19);
    if ( v49 < 0.0 )
      v49 = 0.0;
    *((float *)v23 + 19) = v49;
    v50 = *((float *)v23 + 20);
    if ( v47 < v50 )
      v50 = v47;
    *((float *)v23 + 20) = v50;
    v51 = *((float *)v23 + 21);
    if ( v48 < v51 )
      v51 = v48;
    *((float *)v23 + 21) = v51;
    if ( v50 <= v46 || v51 <= v49 )
    {
      v51 = v49;
      v50 = v46;
    }
    *((float *)v23 + 18) = v46;
    *((float *)v23 + 19) = v49;
    *((float *)v23 + 20) = v50;
    *((float *)v23 + 21) = v51;
    if ( v23[28] && v50 > v46 && v51 > v49 )
    {
      if ( v51 < -2147483600.0 )
      {
        v52 = 0x80000000;
      }
      else if ( v51 >= 2147483600.0 )
      {
        v52 = 0x7FFFFFFF;
      }
      else
      {
        v52 = (int)v51 - 1;
        if ( (float)(int)v51 <= v51 )
          v52 = (int)v51;
      }
      if ( v50 < -2147483600.0 )
      {
        v53 = 0x80000000;
      }
      else if ( v50 >= 2147483600.0 )
      {
        v53 = 0x7FFFFFFF;
      }
      else
      {
        v53 = (int)v50 - 1;
        if ( (float)(int)v50 <= v50 )
          v53 = (int)v50;
      }
      if ( v49 < -2147483600.0 )
      {
        v54 = 0x80000000;
      }
      else if ( v49 >= 2147483600.0 )
      {
        v54 = 0x7FFFFFFF;
      }
      else
      {
        v54 = (int)v49 + 1;
        if ( v49 <= (float)(int)v49 )
          v54 = (int)v49;
      }
      if ( v46 < -2147483600.0 )
      {
        v55 = 0x80000000;
      }
      else if ( v46 >= 2147483600.0 )
      {
        v55 = 0x7FFFFFFF;
      }
      else
      {
        v55 = (int)v46 + 1;
        if ( v46 <= (float)(int)v46 )
          v55 = (int)v46;
      }
      *((_DWORD *)v23 + 26) = v55;
      v56 = v49;
      *((_DWORD *)v23 + 27) = v54;
      *((_DWORD *)v23 + 28) = v53;
      *((_DWORD *)v23 + 29) = v52;
      v57 = *((float *)v23 + 21);
      v58 = *((float *)v23 + 18);
      v59 = *((float *)v23 + 20);
      if ( v57 < -2147483600.0 )
      {
        v60 = 0x80000000;
      }
      else if ( v57 >= 2147483600.0 )
      {
        v60 = 0x7FFFFFFF;
      }
      else
      {
        v60 = (int)v57 + 1;
        if ( v57 <= (float)(int)v57 )
          v60 = (int)v57;
      }
      if ( v59 < -2147483600.0 )
      {
        v61 = 0x80000000;
      }
      else if ( v59 >= 2147483600.0 )
      {
        v61 = 0x7FFFFFFF;
      }
      else
      {
        v61 = (int)v59 + 1;
        if ( v59 <= (float)(int)v59 )
          v61 = (int)v59;
      }
      if ( v56 < -2147483600.0 )
      {
        v62 = 0x80000000;
      }
      else if ( v56 >= 2147483600.0 )
      {
        v62 = 0x7FFFFFFF;
      }
      else
      {
        v62 = (int)v56 - 1;
        if ( (float)(int)v56 <= v56 )
          v62 = (int)v56;
      }
      if ( v58 < -2147483600.0 )
      {
        v63 = 0x80000000;
      }
      else if ( v58 >= 2147483600.0 )
      {
        v63 = 0x7FFFFFFF;
      }
      else
      {
        v63 = (int)v58 - 1;
        if ( (float)(int)v58 <= v58 )
          v63 = (int)v58;
      }
      *((_DWORD *)v23 + 30) = v63;
      *((_DWORD *)v23 + 31) = v62;
      *((_DWORD *)v23 + 32) = v61;
      *((_DWORD *)v23 + 33) = v60;
      v64 = *((float *)v23 + 18);
      CFloatFPU::CeilingSat(v64);
      v65 = CFloatFPU::FloorSat(v64);
      v358[0] = v65;
      v358[1] = v67;
      v358[2] = v66;
      v358[3] = v68;
      if ( v68 > v67 && v66 > v65 && *((float *)v23 + 8) != *((float *)v23 + 13) )
      {
        Strip = AntialiasingStripCache::GetStrip(*((_QWORD *)v23 + 17) + 72LL, v23 + 144, v23 + 176);
        v45 = Strip;
        if ( Strip < 0
          || (v254 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 624LL))(this),
              v255 = *(__int64 (__fastcall **)(CHwSurfaceRenderTarget *, _DWORD *, __int64 *, __int64, int, _QWORD))(*(_QWORD *)this + 536LL),
              v256 = *(_BYTE *)(*(_QWORD *)(v254 + 5640) + 189LL) != 0 ? 4 : 0,
              v257 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 18) + 232LL))(*((_QWORD *)v23 + 18)),
              v333 = *((unsigned int *)v23 + 44),
              Strip = v255(this, v358, &v333, v257, v256, 0),
              v45 = Strip,
              Strip < 0) )
        {
          DoStackCapture(Strip);
          DoStackCapture(v45);
LABEL_358:
          DoStackCapture(v45);
          if ( v294 )
          {
            (*(void (__fastcall **)(float *))(*(_QWORD *)v294 + 8LL))(v294);
            v294 = 0;
          }
          goto LABEL_183;
        }
      }
      v69 = ClipRectSubTarget::CopyStripIfNecessary(v23, this, 2);
      v45 = v69;
      if ( v69 < 0
        || (v69 = ClipRectSubTarget::CopyStripIfNecessary(v23, this, 1), v45 = v69, v69 < 0)
        || (v69 = ClipRectSubTarget::CopyStripIfNecessary(v23, this, 3), v45 = v69, v69 < 0) )
      {
        DoStackCapture(v69);
        goto LABEL_358;
      }
    }
    if ( v45 >= 0 )
    {
      v328 = 0;
      std::swap<win_dox::IXpsOMPackageTargetInternal *,0>(&v328, &v299);
      v299 = v294;
      v294 = 0;
      if ( v328 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v328 + 8LL))(v328);
        v328 = 0;
        if ( v294 )
        {
          (*(void (__fastcall **)(float *))(*(_QWORD *)v294 + 8LL))(v294);
          v294 = 0;
        }
      }
      v70 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 576LL))(this);
      if ( v70 )
      {
        if ( *((_DWORD *)this + 25) == 1 )
          v71 = (__int64 *)(v70 + 392);
        else
          v71 = (__int64 *)(v70 + 304);
        v72 = *v71;
      }
      else
      {
        v72 = 0;
      }
      v73 = v299;
      if ( (*(unsigned __int8 (__fastcall **)(float *))(*(_QWORD *)v299 + 16LL))(v299) )
        ++*(_DWORD *)(v72 + 184);
      if ( (*(unsigned __int8 (__fastcall **)(float *))(*(_QWORD *)v73 + 32LL))(v73) )
        ++*(_DWORD *)(v72 + 188);
      v318 = 0;
      v322 = 0;
      (**(void (__fastcall ***)(float *))v73)(v73);
      v322 = v73;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v322,
        &v318);
      if ( v322 )
      {
        (*(void (__fastcall **)(float *))(*(_QWORD *)v322 + 8LL))(v322);
        v322 = 0;
      }
      v74 = v318;
      v75 = (_QWORD *)(v72 + 40);
      v318 = 0;
      v76 = *(_QWORD *)(v72 + 40);
      v77 = (_QWORD *)(v74 + 8);
      if ( !v74 )
        v77 = 0;
      if ( *(_QWORD **)(v76 + 8) != v75 )
        goto LABEL_355;
      *v77 = v76;
      v77[1] = v75;
      *(_QWORD *)(v76 + 8) = v77;
      *v75 = v77;
      if ( v318 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v318 + 8LL))(v318);
        v318 = 0;
      }
      v332[0] = 1;
      v78 = v299[11];
      v79 = v299[8];
      v80 = v299[9];
      v81 = v299[10];
      v82 = _mm_shuffle_ps(*(__m128 *)v332, *(__m128 *)v332, 225);
      v82.m128_f32[0] = v79;
      *(float *)&v332[16] = v78;
      v83 = _mm_shuffle_ps(v82, v82, 198);
      v83.m128_f32[0] = v80;
      *(float *)&v304 = v78;
      v84 = _mm_shuffle_ps(v83, v83, 39);
      v84.m128_f32[0] = v81;
      *(__m128 *)v332 = _mm_shuffle_ps(v84, v84, 57);
      *(_OWORD *)v303 = *(_OWORD *)v332;
      std::swap<bool,0>((char *)this + 776, v303);
      std::swap<float,0>((char *)this + 784, &v303[1]);
      std::swap<float,0>((char *)this + 780, (char *)v303 + 4);
      std::swap<float,0>((char *)this + 792, &v304);
      std::swap<float,0>((char *)this + 788, (char *)&v303[1] + 4);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( v79 != Clip::msc_nullClip.left
        || v85 != Clip::msc_nullClip.top
        || v86 != Clip::msc_nullClip.right
        || v78 != Clip::msc_nullClip.bottom )
      {
        v87 = _mm_cvtps_epi32(*(__m128 *)&v332[4]);
        v88 = (__m128)_mm_cmpgt_epi32(
                        (__m128i)_mm_and_ps(*(__m128 *)&v332[4], (__m128)xmmword_1803875D0),
                        (__m128i)xmmword_1803875E0);
        v89 = _mm_cvtepi32_ps(v87);
        v90 = _mm_or_ps(
                _mm_andnot_ps(
                  v88,
                  _mm_cvtepi32_ps(
                    _mm_sub_epi32(
                      _mm_add_epi32(
                        (__m128i)_mm_and_ps(_mm_cmplt_ps(*(__m128 *)&v332[4], v89), (__m128)xmmword_1803875F0),
                        v87),
                      (__m128i)_mm_andnot_ps((__m128)xmmword_1803875F0, _mm_cmplt_ps(v89, *(__m128 *)&v332[4]))))),
                _mm_and_ps(*(__m128 *)&v332[4], v88));
        v91 = _mm_shuffle_ps(v90, v90, 85).m128_f32[0];
        v92 = (int)v90.m128_f32[0] - 1;
        v93 = _mm_shuffle_ps(v90, v90, 170).m128_f32[0];
        v94 = (int)v93;
        v95 = _mm_shuffle_ps(v90, v90, 255).m128_f32[0];
        v96 = (int)v95;
        if ( (float)(int)v90.m128_f32[0] <= v90.m128_f32[0] )
          v92 = (int)v90.m128_f32[0];
        si128.m128i_i32[0] = v92;
        v97 = (int)v91 - 1;
        if ( (float)(int)v91 <= v91 )
          v97 = (int)v91;
        si128.m128i_i32[1] = v97;
        v98 = v94 + 1;
        if ( v93 <= (float)v94 )
          v98 = (int)v93;
        si128.m128i_i32[2] = v98;
        v99 = v96 + 1;
        if ( v95 <= (float)v96 )
          v99 = (int)v95;
        si128.m128i_i32[3] = v99;
      }
      (*(void (__fastcall **)(CHwSurfaceRenderTarget *, __m128i *))(*(_QWORD *)this + 688LL))(this, &si128);
      if ( v299 )
      {
        (*(void (__fastcall **)(float *))(*(_QWORD *)v299 + 8LL))(v299);
        v299 = 0;
      }
      goto LABEL_125;
    }
    goto LABEL_358;
  }
LABEL_126:
  v100 = (__int64 *)(*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v9 + 72LL))(v9);
  *(_QWORD *)v325 = v100;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(*v100 + 32))(v100) )
    goto LABEL_127;
  v260 = *v100;
  v290[0] = 0;
  v261 = (const struct D2D_RECT_F *)(*(__int64 (__fastcall **)(__int64 *, char *))(v260 + 168))(v100, v376);
  v45 = CHwSurfaceRenderTarget::TryFastDrawRectangle(this, v261, v5, v8, v7, v290);
  if ( v45 < 0 )
  {
LABEL_313:
    DoStackCapture(v45);
    PrimitiveClipPusher::~PrimitiveClipPusher((PrimitiveClipPusher *)&v291);
    return (unsigned int)v45;
  }
  if ( v290[0] )
  {
    PrimitiveClipPusher::~PrimitiveClipPusher((PrimitiveClipPusher *)&v291);
    return 0;
  }
LABEL_127:
  v101 = *((_DWORD *)this + 32);
  v102 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 144LL))(*((_QWORD *)this + 6));
  v103 = *((_DWORD *)this + 222);
  v104 = *(_DWORD *)(*((_QWORD *)this + 104) + 184LL);
  if ( v101 )
  {
    if ( v103 == 3 )
    {
      if ( v102 )
        v105 = qword_180371AB0;
      else
        v105 = qword_180371900;
    }
    else
    {
      v105 = qword_180375EB0;
    }
  }
  else if ( v103 == 3 )
  {
    if ( v102 )
      v105 = qword_180376060;
    else
      v105 = qword_180376210;
  }
  else if ( v104 < 40960 )
  {
    v105 = qword_1803EFA90;
  }
  else
  {
    v105 = qword_1803EF8E0;
  }
  v106 = (__int64 *)((char *)v105 + 36 * *((int *)this + 34));
  if ( v106 == qword_180375F88 && v104 <= 37120 )
  {
    v106 = qword_1803EFC68;
  }
  else if ( v106 == qword_180376018 )
  {
    v282 = qword_1803EFC40;
    if ( v104 > 37120 )
      v282 = v106;
    v106 = v282;
  }
  v335[1] = 0;
  v107 = (float *)((char *)this + 248);
  v335[0] = v106;
  v335[3] = (char *)this + 248;
  v335[2] = v5;
  v335[4] = 0;
  v337 = 0;
  v336 = 0;
  v338 = &IdentityMatrix3x2;
  if ( *((_DWORD *)this + 35) == 1 )
  {
    v300 = FLOAT_96_0;
    v108 = FLOAT_96_0;
    v109 = FLOAT_96_0;
  }
  else
  {
    v108 = *((float *)this + 47);
    v109 = *((float *)this + 46);
    v300 = v108;
  }
  v110 = *v100;
  v296 = v109;
  (*(void (__fastcall **)(__int64 *, _QWORD, __int64, unsigned int *))(v110 + 184))(v100, 0, 2, &v353);
  v111 = (__m128i)v353;
  v112 = (__m128i)v355;
  v113 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  v114 = FLOAT_1_0;
  v115 = (__m128i)v354;
  v116 = (__m128i)v356;
  if ( *(float *)&v353 > *(float *)&v355 || *(float *)&v354 > *(float *)&v356 )
  {
LABEL_215:
    v181 = *(float *)v112.m128i_i32 <= *(float *)v111.m128i_i32
        || *(float *)v116.m128i_i32 <= *(float *)v115.m128i_i32
        || (_mm_cvtsi128_si32(v111) & 0x7FFFFFFFu) <= 0x48FFFFE0
        && (_mm_cvtsi128_si32(v115) & 0x7FFFFFFFu) <= 0x48FFFFE0
        && (_mm_cvtsi128_si32(v112) & 0x7FFFFFFFu) <= 0x48FFFFE0
        && (_mm_cvtsi128_si32(v116) & 0x7FFFFFFFu) <= 0x48FFFFE0;
    v302 = 0;
    if ( !*(_QWORD *)(*((_QWORD *)this + 104) + 88LL) )
    {
      v182 = *((_DWORD *)this + 32);
      v183 = (*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v9 + 72LL))(v9);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v183 + 112LL))(v183) )
      {
        if ( !v182 )
        {
          v263 = *((float *)this + 62);
          if ( v263 == *((float *)this + 65) && *((float *)this + 63) == COERCE_FLOAT(*((_DWORD *)this + 64) ^ _xmm) )
          {
            v264 = o_sqrtf_0((float)(*((float *)this + 64) * *((float *)this + 64)) + (float)(v263 * v263));
            v184 = v292;
            if ( v292 && *(_DWORD *)v292 == 9 )
            {
LABEL_225:
              v185 = (__m128)LODWORD(FLOAT_96_0);
              if ( *((_DWORD *)this + 35) == 1 )
              {
                v186 = (__m128)LODWORD(FLOAT_96_0);
                v187 = (__m128)LODWORD(FLOAT_96_0);
              }
              else
              {
                v186 = (__m128)*((unsigned int *)this + 47);
                v187 = (__m128)*((unsigned int *)this + 46);
              }
              v188 = *((_DWORD *)this + 34);
              v189 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *))(*(_QWORD *)this + 576LL))(this);
              v191 = 0;
              v192 = 0;
              v193 = (const struct D2D_RECT_F *)*(unsigned int *)(v189 + 100);
              while ( (unsigned int)v192 < 0x1C )
              {
                v190 = (const unsigned __int16 *)(5 * v192);
                if ( (_DWORD)v193 == dword_18030EAE0[10 * v192] )
                {
                  v191 = (unsigned int)dword_18030EAFC[10 * v192];
                  break;
                }
                v192 = (unsigned int)(v192 + 1);
              }
              if ( v188 )
              {
                if ( v188 != 1 )
                {
LABEL_241:
                  v198 = 0;
                  v199 = 0;
                  goto LABEL_242;
                }
                v198 = 1;
                v199 = 1;
              }
              else
              {
                v194 = *(_DWORD *)v184;
                if ( *(_DWORD *)v184 == 2 )
                {
                  if ( *((float *)v184 + 4) != v114 )
                    goto LABEL_241;
                  v195 = *((float *)v184 + 5);
                  if ( (_DWORD)v191 != 2 )
                  {
                    if ( (_DWORD)v191 )
                    {
                      if ( (_DWORD)v191 == 1 )
                      {
                        v196 = FLOAT_N65504_0;
                        v197 = FLOAT_65504_0;
                      }
                      else
                      {
                        v196 = FLOAT_N3_4028235e38;
                        v197 = FLOAT_3_4028235e38;
                      }
                    }
                    else
                    {
                      v196 = *(float *)&v290[4];
                      v197 = v114;
                    }
                    if ( v195 > v197 )
                      v195 = v197;
                    else
                      v195 = fmaxf(v195, v196);
                  }
                  if ( v195 != v114 )
                    goto LABEL_241;
                }
                else
                {
                  if ( v194 != 1 )
                  {
                    switch ( v194 )
                    {
                      case 3:
                      case 5:
                        if ( ClampInputAlpha(v192, (unsigned int)v191, v193) != v114 )
                          goto LABEL_241;
                        v284 = *((_QWORD *)v184 + 6);
                        goto LABEL_504;
                      case 4:
                      case 6:
                        if ( ClampInputAlpha(v192, (unsigned int)v191, v193) != v114 )
                          goto LABEL_241;
                        v284 = *((_QWORD *)v184 + 7);
LABEL_504:
                        if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v284 + 176LL))(v284) )
                          goto LABEL_241;
                        goto LABEL_307;
                      case 7:
                      case 8:
                        v249 = *((float *)v184 + 1);
                        if ( (_DWORD)v191 != 2 )
                        {
                          if ( (_DWORD)v191 )
                          {
                            if ( (_DWORD)v191 == 1 )
                            {
                              v250 = FLOAT_N65504_0;
                              v251 = FLOAT_65504_0;
                            }
                            else
                            {
                              v250 = FLOAT_N3_4028235e38;
                              v251 = FLOAT_3_4028235e38;
                            }
                          }
                          else
                          {
                            v250 = *(float *)&v290[4];
                            v251 = v114;
                          }
                          if ( v249 > v251 )
                            v249 = v251;
                          else
                            v249 = fmaxf(v249, v250);
                        }
                        if ( v249 != v114 )
                          goto LABEL_241;
                        v228 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, char *, const struct D2D_RECT_F *))(**((_QWORD **)v184 + 6) + 280LL))(
                                             *((_QWORD *)v184 + 6),
                                             v352,
                                             v193)
                                         + 4) == 3;
                        goto LABEL_306;
                      case 9:
                      case 10:
                        goto LABEL_241;
                      case 11:
                        v227 = ClampInputAlpha(v192, (unsigned int)v191, v193);
                        goto LABEL_305;
                      default:
                        PrintAssertionMessageW(
                          L"Unexpected brush type.",
                          v190,
                          L"IsBrushOpaque",
                          L"onecoreuap\\windows\\direct2d\\core\\brush\\brushutils.cpp",
                          0xB0u);
                        __int2c();
                        goto LABEL_307;
                    }
                  }
                  v227 = *((float *)v184 + 4);
LABEL_305:
                  v228 = v227 == v114;
LABEL_306:
                  if ( !v228 )
                    goto LABEL_241;
                }
LABEL_307:
                v198 = 1;
                v199 = 1;
              }
LABEL_242:
              if ( *((_DWORD *)this + 32) == 1 )
              {
                if ( v188 <= 4 && v199 )
                {
                  v234 = v295;
                  goto LABEL_430;
                }
              }
              else if ( !v188 )
              {
                v200 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(struct IGeometryInternal *, const unsigned __int16 *, const struct D2D_RECT_F *, __int64))(*(_QWORD *)v301 + 32LL))(
                                              v301,
                                              v190,
                                              v193,
                                              v191)
                                          + 233);
                v201 = (*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v301 + 112LL))(v301);
                if ( v198 )
                {
                  if ( !v201 && (_BYTE)v200 && *v107 == v107[3] && v107[1] == COERCE_FLOAT(*((_DWORD *)v107 + 2) ^ _xmm) )
                  {
                    v232 = (float)(*v107 * *v107) + (float)(v107[2] * v107[2]);
                    v233 = v232 < 0.0 ? o_sqrtf_0(v232) : fsqrt(v232);
                    *(float *)&v290[4] = v233;
                    if ( v187.m128_f32[0] == v186.m128_f32[0] )
                    {
                      v234 = v295;
                      if ( !v295
                        || !*(_DWORD *)((*(__int64 (__fastcall **)(struct IStrokeStyleInternal *, char *))(*(_QWORD *)v295 + 48LL))(
                                          v295,
                                          v382)
                                      + 20) )
                      {
LABEL_430:
                        v291 = 0;
                        v274 = (CShapeBase *)(*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v301 + 72LL))(v301);
                        *(_QWORD *)&v202 = LODWORD(a3);
                        if ( (int)CShapeBase::GetLooseBounds(
                                    v274,
                                    v234,
                                    a3,
                                    (const struct MILMatrix3x2 *)v107,
                                    (struct D2D_SIZE_F)*(_OWORD *)&_mm_unpacklo_ps(v187, v186),
                                    (struct D2D_RECT_F *)&v291) >= 0
                          && (*(float *)&v291.left > *(float *)&v291.right
                           || (float)(*(float *)&v291.right - *(float *)&v291.left) < 524287.0)
                          && (*(float *)&v291.top > *(float *)&v291.bottom
                           || (float)(*(float *)&v291.bottom - *(float *)&v291.top) < 524287.0)
                          && !*(_QWORD *)(*((_QWORD *)this + 104) + 88LL) )
                        {
                          v339 = &CFastStrokeTessellator::`vftable';
                          v275 = *((_DWORD *)this + 32);
                          if ( *((_DWORD *)this + 35) == 1 )
                          {
                            v276 = FLOAT_96_0;
                          }
                          else
                          {
                            v185.m128_i32[0] = *((_DWORD *)this + 47);
                            v276 = *((float *)this + 46);
                          }
                          v346 = v276;
                          v349 = *(_DWORD *)&v290[4];
                          v340 = a3;
                          v347 = v185.m128_i32[0];
                          v341 = v234;
                          v342 = v100;
                          v343 = v107;
                          v345 = (char *)this + 208;
                          v344 = 1048576000;
                          v348 = v275;
                          v277 = CHwSurfaceRenderTarget::FillTessellation(
                                   this,
                                   v275,
                                   (struct IGeometryGenerator *)&v339,
                                   (const struct FillTessellationData *)v335,
                                   v287);
                          v206 = v277;
                          if ( v277 < 0 )
                            DoStackCapture(v277);
                          v339 = &IGeometryGenerator::`vftable';
                          goto LABEL_260;
                        }
LABEL_250:
                        if ( *((_DWORD *)this + 32) == 1 || !*(_BYTE *)(*((_QWORD *)this + 104) + 250LL) || !v181 )
                        {
                          v244 = *((_QWORD *)this + 103);
                          v245 = 0;
                          v246 = (_DWORD *)(v244 + 3880);
                          *(_DWORD *)(v244 + 3936) = 0;
                          *(_WORD *)(v244 + 4232) = 0;
                          *(_DWORD *)(v244 + 4016) = 0;
                          *(_DWORD *)(v244 + 4152) = 0;
                          *(_DWORD *)(v244 + 4192) = 0;
                          *(_DWORD *)(v244 + 4224) = 0;
                          if ( *(_DWORD *)(v244 + 3912) )
                          {
                            v247 = v244 + 3888;
                            v258 = (float *)(v244 + 3984);
                            v298 = v258;
                            do
                            {
                              v259 = *(float **)(*(_QWORD *)v247 + 8LL * v245);
                              if ( v259 != v258 )
                              {
                                if ( v259 )
                                {
                                  CFigureData::~CFigureData(*(CFigureData **)(*(_QWORD *)v247 + 8LL * v245));
                                  operator delete(v259);
                                  v258 = v298;
                                }
                                *(_QWORD *)(*(_QWORD *)v247 + 8LL * v245) = 0;
                              }
                              ++v245;
                            }
                            while ( v245 < v246[8] );
                            v100 = *(__int64 **)v325;
                          }
                          else
                          {
                            v247 = v244 + 3888;
                          }
                          *(_DWORD *)(v247 + 24) = 0;
                          v246[20] = 0;
                          v246[25] = 0;
                          v288 = (char *)this + 248;
                          v285.height = *((FLOAT *)&v246 + 1);
                          v248 = (*(__int64 (__fastcall **)(__int64 *, char *, struct IStrokeStyleInternal *))(*v100 + 192))(
                                   v100,
                                   (char *)this + 248,
                                   v295);
                          v206 = v248;
                          if ( v248 >= 0 )
                          {
                            LODWORD(v288) = 0;
                            v285.width = 0.0;
                            v248 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CHwSurfaceRenderTarget::FillShapeData)(
                                     this,
                                     *((unsigned int *)this + 32),
                                     v246,
                                     v335,
                                     v285,
                                     v288);
                            v206 = v248;
                            if ( v248 >= 0 )
                              goto LABEL_260;
                          }
LABEL_423:
                          DoStackCapture(v248);
                          goto LABEL_260;
                        }
                        if ( *((_DWORD *)this + 35) == 1 )
                        {
                          v203 = (__m128)LODWORD(FLOAT_96_0);
                        }
                        else
                        {
                          v185 = (__m128)*((unsigned int *)this + 47);
                          v203 = (__m128)*((unsigned int *)this + 46);
                        }
                        v363 = 0;
                        v368 = &TransformableStrokeTessellation::`vftable';
                        v373 = 0;
                        v369 = &CFastStrokeTessellator::`vftable';
                        v204 = 0;
                        v361 = &TransformableConvexFigureTessellation::`vftable'{for `ITransformableGeometryGenerator'};
                        v362 = &TransformableConvexFigureTessellation::`vftable'{for `IGeometryGenerator'};
                        v291 = 0;
                        if ( *(float *)v112.m128i_i32 <= *(float *)v111.m128i_i32
                          || *(float *)v116.m128i_i32 <= *(float *)v115.m128i_i32 )
                        {
                          goto LABEL_257;
                        }
                        v217 = (float)*((int *)this + 52);
                        v218 = (float)*((int *)this + 53);
                        v219 = (float)*((int *)this + 54);
                        v220 = (float)*((int *)this + 55);
                        if ( *(float *)v111.m128i_i32 > v217 )
                          v217 = *(float *)v111.m128i_i32;
                        if ( *(float *)v115.m128i_i32 > v218 )
                          v218 = *(float *)v115.m128i_i32;
                        if ( v219 > *(float *)v112.m128i_i32 )
                          v219 = *(float *)v112.m128i_i32;
                        if ( v220 > *(float *)v116.m128i_i32 )
                          v220 = *(float *)v116.m128i_i32;
                        if ( v217 >= v219 || v218 >= v220 || v217 >= v219 || v218 >= v220 )
                        {
LABEL_257:
                          v205 = 0;
                          goto LABEL_258;
                        }
                        v221 = (int)v217 - 1;
                        if ( (float)(int)v217 <= v217 )
                          v221 = (int)v217;
                        v291.left = v221;
                        v191 = (unsigned int)((int)v218 - 1);
                        if ( (float)(int)v218 <= v218 )
                          v191 = (unsigned int)(int)v218;
                        v291.top = v191;
                        v222 = (int)v219 + 1;
                        if ( v219 <= (float)(int)v219 )
                          v222 = (int)v219;
                        v291.right = v222;
                        v223 = (int)v220 + 1;
                        if ( v220 <= (float)(int)v220 )
                          v223 = (int)v220;
                        v291.bottom = v223;
                        if ( v222 - v221 <= 512 )
                        {
                          v193 = (const struct D2D_RECT_F *)(unsigned int)(v223 - v191);
                          if ( (int)v193 <= 512 )
                          {
                            v205 = &v368;
                            v204 = TIR_UNTILED_STROKE_TILE_SIZE;
                            v370 = *(_OWORD *)v107;
                            v371 = *((_QWORD *)v107 + 2);
                            v372 = LODWORD(v202);
                            v374 = v203.m128_i32[0];
                            v375 = v185.m128_i32[0];
                            *(_QWORD *)&v373 = v295;
                            *((_QWORD *)&v373 + 1) = v100;
LABEL_258:
                            v206 = 0;
                            if ( !v205 )
                              goto LABEL_259;
                            v235 = CHwSurfaceRenderTarget::FillTessellation_TIR(
                                     this,
                                     (struct ITransformableGeometryGenerator *)v205,
                                     v193,
                                     &v291,
                                     v204,
                                     (const struct FillTessellationData *)v335);
                            v206 = v235;
                            if ( v235 >= 0 )
                              goto LABEL_259;
                            v236 = v235;
LABEL_329:
                            DoStackCapture(v236);
LABEL_259:
                            v362 = &IGeometryGenerator::`vftable';
                            v369 = &IGeometryGenerator::`vftable';
LABEL_260:
                            if ( v302 )
                            {
                              win_scope::close_delete::close<OfferableBuffer>(&v302);
                              v302 = 0;
                            }
                            if ( !v6 )
                              return v206;
                            v207 = (*(__int64 (__fastcall **)(CHwSurfaceRenderTarget *, void ***, const struct D2D_RECT_F *, __int64))(*(_QWORD *)this + 576LL))(
                                     this,
                                     v205,
                                     v193,
                                     v191);
                            if ( v207 )
                            {
                              if ( *((_DWORD *)this + 25) == 1 )
                                v208 = (__int64 *)(v207 + 392);
                              else
                                v208 = (__int64 *)(v207 + 304);
                              v209 = *v208;
                            }
                            else
                            {
                              v209 = 0;
                            }
                            v210 = (_QWORD *)(v209 + 40);
                            v297 = 0;
                            v211 = *(_QWORD **)(v209 + 40);
                            if ( v211[1] == v209 + 40 )
                            {
                              v212 = *v211;
                              if ( *(_QWORD **)(*v211 + 8LL) == v211 )
                              {
                                *v210 = v212;
                                v213 = v211 - 1;
                                *(_QWORD *)(v212 + 8) = v210;
                                v329 = 0;
                                win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
                                  &v329,
                                  &v297);
                                if ( v329 )
                                {
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v329 + 8LL))(v329);
                                  v329 = 0;
                                }
                                v297 = v213;
                                if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*v213 + 16LL))(v213) )
                                  --*(_DWORD *)(v209 + 184);
                                if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*v297 + 32LL))(v297) )
                                  --*(_DWORD *)(v209 + 188);
                                v214 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*v297 + 40LL))(
                                         v297,
                                         *(_QWORD *)(v209 + 192),
                                         0,
                                         0);
                                v215 = v214;
                                if ( v214 < 0 )
                                {
                                  DoStackCapture(v214);
                                  if ( v297 )
                                  {
                                    win_scope::close_com::close<RefCountedObject<ClipRectSubTarget,LockingRequired,DeleteOnZeroReference> * *>(&v297);
                                    v297 = 0;
                                  }
                                  DoStackCapture(v215);
                                }
                                else if ( v297 )
                                {
                                  (*(void (__fastcall **)(_QWORD *))(*v297 + 8LL))(v297);
                                }
                                return v206;
                              }
                            }
LABEL_355:
                            __fastfail(3u);
                          }
                        }
                        v204 = TIR_TILED_STROKE_TILE_SIZE;
                        v224 = (CConvexFigureStorage *)(*((_QWORD *)this + 103) + 5408LL);
                        v225 = CConvexFigureStorage::PrepareForFigures(v224, &v291, TIR_TILED_STROKE_TILE_SIZE, 0.25);
                        v206 = v225;
                        if ( v225 < 0 )
                        {
                          DoStackCapture(v225);
                        }
                        else
                        {
                          CConvexWideningSink::CConvexWideningSink((CConvexWideningSink *)v377, v224);
                          v290[0] = 0;
                          v226 = CShapeBase::WidenToSink(
                                   *(__int64 **)v325,
                                   v202,
                                   (__int64 *)v295,
                                   (struct MILMatrix3x2 *)v107,
                                   _mm_unpacklo_ps(v203, v185).m128_i64[0],
                                   SLODWORD(FLOAT_0_25),
                                   0,
                                   (struct CWideningSink *)v377,
                                   (int *)this + 52,
                                   v290);
                          v206 = v226;
                          if ( v226 >= 0 )
                          {
                            v364 = v111.m128i_i32[0];
                            v377[0] = &CWideningSink::`vftable';
                            v205 = &v361;
                            v365 = v115.m128i_i32[0];
                            v366 = v112.m128i_i32[0];
                            v367 = v116.m128i_i32[0];
                            v363 = v224;
                            goto LABEL_258;
                          }
                          DoStackCapture(v226);
                          DoStackCapture(v206);
                          v377[0] = &CWideningSink::`vftable';
                        }
                        v236 = v206;
                        goto LABEL_329;
                      }
                    }
                  }
                }
              }
              *(_QWORD *)&v202 = LODWORD(a3);
              goto LABEL_250;
            }
            v265 = v301;
            v266 = (*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v301 + 72LL))(v301);
            v267 = (const struct D2D1_ROUNDED_RECT *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v266 + 136LL))(
                                                       v266,
                                                       v378);
            v268 = v296;
            v269 = (struct D2D_SIZE_F)_mm_unpacklo_ps((__m128)LODWORD(v296), (__m128)LODWORD(v300)).m128_u64[0];
            if ( DrawRoundedRectangleTessellator::CanUse(
                   v267,
                   (CHwSurfaceRenderTarget *)((char *)this + 248),
                   a3,
                   v295,
                   v264,
                   v269) )
            {
              v270 = (*(__int64 (__fastcall **)(struct IGeometryInternal *))(*(_QWORD *)v265 + 72LL))(v265);
              (*(void (__fastcall **)(__int64, struct D2D_RECT_F *))(*(_QWORD *)v270 + 136LL))(v270, &v359);
              if ( *(float *)&v360 == *(float *)&v290[4] )
              {
                v271 = (DrawRectangleTessellator *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v271 )
                {
                  if ( v295 )
                    v283 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IStrokeStyleInternal *, char *))(*(_QWORD *)v295 + 48LL))(
                                         v295,
                                         v380)
                                     + 28);
                  else
                    v283 = D2D1_STROKE_TRANSFORM_TYPE_NORMAL;
                  v271 = DrawRectangleTessellator::DrawRectangleTessellator(
                           v271,
                           &v359,
                           a3,
                           v283,
                           (CHwSurfaceRenderTarget *)((char *)this + 248),
                           v264,
                           v269);
                }
                v323 = 0;
                win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
                  &v323,
                  &v302);
                if ( v323 )
                {
                  win_scope::close_delete::close<OfferableBuffer>(&v323);
                  v323 = 0;
                }
                v302 = v271;
                if ( v271 )
                {
LABEL_422:
                  v248 = CHwSurfaceRenderTarget::FillTessellation(
                           this,
                           D2D1_ANTIALIAS_MODE_PER_PRIMITIVE,
                           v271,
                           (const struct FillTessellationData *)v335,
                           v286);
                  v206 = v248;
                  if ( v248 >= 0 )
                    goto LABEL_260;
                  goto LABEL_423;
                }
              }
              else
              {
                v271 = (DrawRectangleTessellator *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v271 )
                {
                  if ( v295 )
                    (*(void (__fastcall **)(struct IStrokeStyleInternal *, char *))(*(_QWORD *)v295 + 48LL))(v295, v381);
                  SpecialCaseGeometryTessellator::SpecialCaseGeometryTessellator(
                    v271,
                    (CHwSurfaceRenderTarget *)((char *)this + 248),
                    v264);
                  v272 = v300;
                  *(_QWORD *)v271 = &DrawRoundedRectangleTessellator::`vftable';
                  *((_DWORD *)v271 + 19) = v273;
                  *((float *)v271 + 20) = v268;
                  *((float *)v271 + 21) = v272;
                  *((_DWORD *)v271 + 18) = LODWORD(a3) & v113;
                  *((struct D2D_RECT_F *)v271 + 3) = v359;
                  *((_QWORD *)v271 + 8) = v360;
                }
                else
                {
                  v271 = 0;
                }
                v324 = 0;
                win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
                  &v324,
                  &v302);
                if ( v324 )
                {
                  win_scope::close_delete::close<OfferableBuffer>(&v324);
                  v324 = 0;
                }
                v302 = v271;
                if ( v271 )
                  goto LABEL_422;
              }
              DoStackCapture(-2147024882);
            }
          }
        }
      }
    }
    v184 = v292;
    goto LABEL_225;
  }
  v117 = v295;
  v306 = _mm_load_si128((const __m128i *)&_xmm);
  *(_OWORD *)Block = 0;
  v307 = 96.0;
  v308 = 1119879168;
  v309 = 0;
  v310 = 0;
  v311 = 1092616192;
  v312 = 0;
  v313 = 0;
  v315 = 0;
  v316 = 0;
  v304 = 0;
  v305 = 0;
  *(_OWORD *)v303 = 0;
  v350 = 0;
  v351 = 0;
  if ( !v295 )
  {
    HIDWORD(v308) = 0;
    v309 = 0;
    v310 = 0;
    v298 = 0;
    v316 = 0;
    v124 = a3;
    v123 = v303[0];
    HIDWORD(v312) = 0;
    LODWORD(v311) = fmaxf(10.0, 1.0);
    v313 = 0;
    goto LABEL_190;
  }
  v118 = (__int128 *)(*(__int64 (__fastcall **)(struct IStrokeStyleInternal *, char *))(*(_QWORD *)v295 + 48LL))(
                       v295,
                       v379);
  v350 = *v118;
  v351 = v118[1];
  v119 = (*(__int64 (__fastcall **)(struct IStrokeStyleInternal *))(*(_QWORD *)v117 + 56LL))(v117);
  v120 = v119;
  v121 = DynArrayImpl<0>::Grow((unsigned int)v303, 4, v119, 0, 0);
  v122 = v121;
  if ( v121 < 0 )
  {
    DoStackCapture(v121);
    DoStackCapture(v122);
    v252 = v303[0];
    if ( v303[0] == v303[1] )
      goto LABEL_392;
    goto LABEL_394;
  }
  v123 = v303[0];
  v298 = (float *)((char *)v303[0] + (unsigned int)(4 * v305));
  (*(void (__fastcall **)(struct IStrokeStyleInternal *, float *, _QWORD))(*(_QWORD *)v117 + 64LL))(
    v117,
    v298,
    (unsigned int)v120);
  HIDWORD(v308) = v350;
  v309 = *(_QWORD *)((char *)&v350 + 4);
  v310 = HIDWORD(v350);
  v311 = __PAIR64__(HIDWORD(v351), COERCE_UNSIGNED_INT(fmaxf(*(float *)&v351, 1.0)));
  v313 = DWORD2(v351);
  if ( HIDWORD(v351) == 2 )
    v124 = FLOAT_1_0;
  else
    v124 = a3;
  v307 = v109;
  *(float *)&v308 = v108;
  v125 = DWORD1(v351);
  if ( DWORD1(v351) != 5 )
  {
    v231 = dword_180387600[SDWORD1(v351)];
    v298 = 0;
    v316 = 0;
    if ( v231 )
    {
      v281 = DynArrayImpl<0>::AddMultiple(Block, 4, v231, &v298);
      v122 = v281;
      if ( v281 < 0 )
      {
        DoStackCapture(v281);
        goto LABEL_391;
      }
      GetDashArrayFromDashStyle(v125, v231, v298, v319);
    }
    v116 = (__m128i)v356;
    v112 = (__m128i)v355;
    v115 = (__m128i)v354;
    v111 = (__m128i)v353;
    HIDWORD(v312) = v125;
    goto LABEL_190;
  }
  v126 = 0;
  v316 = 0;
  DynArrayImpl<0>::ShrinkToSize(Block, 4);
  v127 = 2 * v120;
  if ( (v120 & 1) == 0 )
    v127 = v120;
  v128 = DynArrayImpl<0>::Grow((unsigned int)Block, 4, v127, 1, 0);
  v122 = v128;
  if ( v128 < 0 )
  {
    v262 = v128;
  }
  else
  {
    v129 = v316;
    v130 = 0.0;
    while ( v126 < (unsigned int)v120 )
    {
      v131 = v129 + 1;
      v132 = LODWORD(v298[v126]) & v113;
      v317 = v132;
      if ( v129 + 1 < v129 )
        goto LABEL_388;
      if ( v131 <= HIDWORD(v315) )
      {
        v130 = v130 + *(float *)&v132;
        ++v126;
        *((_DWORD *)Block[0] + v129++) = v317;
        v316 = v131;
      }
      else
      {
        *(_QWORD *)v319 = &v317;
        v133 = DynArrayImpl<0>::Grow((unsigned int)Block, 4, 1, 0, (__int64)v319);
        v122 = v133;
        if ( v133 < 0 )
        {
          DoStackCapture(v133);
          v129 = v316;
        }
        else
        {
          *((_DWORD *)Block[0] + v316) = **(_DWORD **)v319;
          v129 = ++v316;
        }
        if ( v122 < 0 )
          goto LABEL_389;
        v130 = v130 + *(float *)&v132;
        ++v126;
      }
    }
    if ( v130 <= 0.0 )
    {
      v316 = 0;
      DynArrayImpl<0>::ShrinkToSize(Block, 4);
      HIDWORD(v312) = 0;
      goto LABEL_188;
    }
    if ( (v120 & 1) == 0 )
    {
LABEL_187:
      HIDWORD(v312) = 5;
LABEL_188:
      v116 = (__m128i)v356;
      v107 = (float *)((char *)this + 248);
      v112 = (__m128i)v355;
      v115 = (__m128i)v354;
      v111 = (__m128i)v353;
LABEL_190:
      v148 = *(float *)&v290[4];
      v149 = *(float *)&v290[4];
      v150 = *(float *)&v290[4];
      v306.m128i_i32[2] = *(_DWORD *)&v290[4];
      LODWORD(v151) = COERCE_UNSIGNED_INT(v124 * 0.5) & v113;
      v152 = v151;
      v306.m128i_i64[0] = __PAIR64__(*(unsigned int *)&v290[4], LODWORD(v151));
      *(float *)&v306.m128i_i32[3] = v151;
      if ( v123 != v303[1] )
      {
        free(v123);
        v152 = *(float *)&v306.m128i_i32[3];
        v149 = *(float *)&v306.m128i_i32[1];
        v148 = *(float *)&v290[4];
        v116 = (__m128i)v356;
        v112 = (__m128i)v355;
        v115 = (__m128i)v354;
        v111 = (__m128i)v353;
        v150 = *(float *)&v306.m128i_i32[2];
        v151 = *(float *)v306.m128i_i32;
      }
      v153 = (float *)((char *)this + 248);
      if ( HIDWORD(v311) == 2 )
      {
        v156 = FLOAT_1_0;
      }
      else
      {
        if ( v149 == v148 && v150 == v148 )
        {
          v154 = LODWORD(v151) & v113;
          v155 = LODWORD(v152) & v113;
          if ( *(float *)&v155 < *(float *)&v154 )
            v155 = v154;
        }
        else
        {
          v237 = (float)(v149 * v149) + (float)(v151 * v151);
          v238 = (float)(v149 * v152) + (float)(v151 * v150);
          v239 = (float)(v150 * v150) + (float)(v152 * v152);
          v240 = (float)((float)(v238 * 4.0) * v238) + (float)((float)(v237 - v239) * (float)(v237 - v239));
          if ( v240 < 0.0 )
            v241 = o_sqrtf_0(v240);
          else
            v241 = fsqrt(v240);
          v242 = (float)(v241 + (float)(v239 + v237)) * 0.5;
          if ( v242 < 0.0 )
            v243 = o_sqrtf_0(v242);
          else
            v243 = fsqrt(v242);
          *(float *)&v155 = v243;
        }
        v156 = *(float *)&v155 + *(float *)&v155;
      }
      v157 = fmaxf((float)(v156 * v307) / 96.0, (float)(v156 * *(float *)&v308) / 96.0);
      if ( v310 == 3 || !v310 )
      {
        v158 = *(float *)&v311 * 1.414213562373095;
      }
      else if ( HIDWORD(v309) == 1 || HIDWORD(v308) == 1 || (_DWORD)v309 == 1 )
      {
        v158 = FLOAT_1_4142135;
      }
      else
      {
        v158 = FLOAT_1_0;
      }
      v159 = (float)(v157 * 0.5) * v158;
      if ( !HIDWORD(v311) )
      {
        *(float *)v111.m128i_i32 = *(float *)v111.m128i_i32 - v159;
        *(float *)v115.m128i_i32 = *(float *)v115.m128i_i32 - v159;
        *(float *)v112.m128i_i32 = *(float *)v112.m128i_i32 + v159;
        *(float *)v116.m128i_i32 = *(float *)v116.m128i_i32 + v159;
        v353 = v111.m128i_u32[0];
        v354 = v115.m128i_u32[0];
        v355 = v112.m128i_u32[0];
        v356 = v116.m128i_u32[0];
      }
      if ( this != (CHwSurfaceRenderTarget *)-248LL
        && *(float *)v111.m128i_i32 <= *(float *)v112.m128i_i32
        && *(float *)v115.m128i_i32 <= *(float *)v116.m128i_i32 )
      {
        v160 = *(float *)v112.m128i_i32;
        v161 = *((float *)this + 63);
        v162 = *((float *)this + 66);
        v163 = *((float *)this + 67);
        v164 = *(float *)v115.m128i_i32 * *((float *)this + 64);
        v165 = *(float *)v115.m128i_i32 * *((float *)this + 65);
        v166 = *(float *)v112.m128i_i32 * v161;
        v167 = *v153 * *(float *)v111.m128i_i32;
        v168 = v161 * *(float *)v111.m128i_i32;
        v169 = v160 * *v153;
        v170 = v166 + v165;
        v171 = v166;
        v112 = v116;
        *(float *)v112.m128i_i32 = *(float *)v116.m128i_i32 * *((float *)this + 64);
        *(float *)v116.m128i_i32 = *(float *)v116.m128i_i32 * *((float *)this + 65);
        v172 = v170 + v163;
        v173 = (float)(v169 + v164) + v162;
        v174 = (float)(*(float *)v112.m128i_i32 + v167) + v162;
        v175 = (float)(*(float *)v116.m128i_i32 + v168) + v163;
        *(float *)v112.m128i_i32 = (float)(*(float *)v112.m128i_i32 + v169) + v162;
        *(float *)v116.m128i_i32 = (float)(*(float *)v116.m128i_i32 + v171) + v163;
        v176 = (float)(v167 + v164) + v162;
        v177 = (float)(v168 + v165) + v163;
        v178 = v174;
        v179 = fmaxf(v174, fmaxf(v173, v176));
        v180 = fminf(v178, fminf(v173, v176));
        v111 = v112;
        *(float *)v112.m128i_i32 = fmaxf(*(float *)v112.m128i_i32, v179);
        *(float *)v111.m128i_i32 = fminf(*(float *)v111.m128i_i32, v180);
        v115 = v116;
        *(float *)v116.m128i_i32 = fmaxf(*(float *)v116.m128i_i32, fmaxf(v175, fmaxf(v172, v177)));
        *(float *)v115.m128i_i32 = fminf(*(float *)v115.m128i_i32, fminf(v175, fminf(v172, v177)));
        v113 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
        v114 = FLOAT_1_0;
        v353 = v111.m128i_u32[0];
        v354 = v115.m128i_u32[0];
        v355 = v112.m128i_u32[0];
        v356 = v116.m128i_u32[0];
      }
      if ( HIDWORD(v311) )
      {
        *(float *)v111.m128i_i32 = *(float *)v111.m128i_i32 - v159;
        *(float *)v115.m128i_i32 = *(float *)v115.m128i_i32 - v159;
        *(float *)v112.m128i_i32 = *(float *)v112.m128i_i32 + v159;
        *(float *)v116.m128i_i32 = *(float *)v116.m128i_i32 + v159;
        v353 = v111.m128i_u32[0];
        v354 = v115.m128i_u32[0];
        v355 = v112.m128i_u32[0];
        v356 = v116.m128i_u32[0];
      }
      if ( Block[0] != Block[1] )
      {
        free(Block[0]);
        v116 = (__m128i)v356;
        v112 = (__m128i)v355;
        v115 = (__m128i)v354;
        v111 = (__m128i)v353;
        Block[0] = 0;
      }
      v9 = v301;
      v100 = *(__int64 **)v325;
      goto LABEL_215;
    }
    v279 = v129 + v120;
    if ( v129 + (unsigned int)v120 < v129 )
    {
LABEL_388:
      v122 = -2147024362;
      DoStackCapture(-2147024362);
    }
    else
    {
      if ( v279 <= HIDWORD(v315) )
      {
        memcpy_0((char *)Block[0] + 4 * v129, Block[0], 4 * v120);
        v316 = v279;
        goto LABEL_187;
      }
      v280 = DynArrayImpl<0>::AddMultipleAndSet(Block, 4, (unsigned int)v120, Block[0]);
      v122 = v280;
      if ( v280 < 0 )
        DoStackCapture(v280);
      if ( v122 >= 0 )
        goto LABEL_187;
    }
LABEL_389:
    v262 = v122;
  }
  DoStackCapture(v262);
LABEL_391:
  DoStackCapture(v122);
  DoStackCapture(v122);
  if ( v123 != v303[1] )
  {
    v252 = v123;
LABEL_394:
    free(v252);
  }
LABEL_392:
  DoStackCapture(v122);
  DynArrayImpl<0>::~DynArrayImpl<0>(Block);
  DoStackCapture(v122);
  PrimitiveClipPusher::~PrimitiveClipPusher((PrimitiveClipPusher *)&v291);
  return (unsigned int)v122;
}

```

## disassembly

```asm
0x18001a510  mov     rax, rsp
0x18001a513  push    rbp
0x18001a514  push    rbx
0x18001a515  push    rsi
0x18001a516  push    rdi
0x18001a517  push    r12
0x18001a519  push    r13
0x18001a51b  push    r14
0x18001a51d  push    r15
0x18001a51f  lea     rbp, [rax-4E8h]
0x18001a526  sub     rsp, 5A8h
0x18001a52d  movaps  xmmword ptr [rax-58h], xmm6
0x18001a531  movaps  xmmword ptr [rax-68h], xmm7
0x18001a535  movaps  xmmword ptr [rax-78h], xmm8
0x18001a53a  movaps  xmmword ptr [rax-88h], xmm9
0x18001a542  movaps  xmmword ptr [rax-98h], xmm10
0x18001a54a  movaps  xmmword ptr [rax-0A8h], xmm11
0x18001a552  movaps  xmmword ptr [rax-0B8h], xmm12
0x18001a55a  movaps  xmmword ptr [rax-0C8h], xmm13
0x18001a562  movaps  xmmword ptr [rax-0D8h], xmm14
0x18001a56a  movaps  xmmword ptr [rax-0E8h], xmm15
0x18001a572  mov     rax, cs:__security_cookie
0x18001a579  xor     rax, rsp
0x18001a57c  mov     [rbp+4E0h+var_E8], rax
0x18001a583  mov     rsi, [rbp+4E0h+arg_20]
0x18001a58a  lea     r15, __ImageBase
0x18001a591  xor     r12b, r12b
0x18001a594  movss   [rsp+5E0h+var_590], xmm2
0x18001a59a  xor     r13d, r13d
0x18001a59d  mov     [rbp+4E0h+var_528], rdx
0x18001a5a1  mov     rbx, r9
0x18001a5a4  xorps   xmm13, xmm13
0x18001a5a8  movaps  xmm6, xmm2
0x18001a5ab  movss   dword ptr [rsp+5E0h+var_58C+4], xmm13
0x18001a5b2  mov     rdi, rdx
0x18001a5b5  mov     [rbp+4E0h+var_558], rbx
0x18001a5b9  mov     r14, rcx
0x18001a5bc  mov     [rsp+5E0h+var_570], rsi
0x18001a5c1  mov     qword ptr [rsp+5E0h+var_580.left], rcx
0x18001a5c6  mov     word ptr [rsp+5E0h+var_580.right], 1
0x18001a5cd  cmp     [rcx+9Ch], r12b
0x18001a5d4  jz      loc_18001B0DB
0x18001a5da  mov     rax, [rcx]
0x18001a5dd  mov     rax, [rax+240h]
0x18001a5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e9  test    rax, rax
0x18001a5ec  jz      loc_18001B4F2
0x18001a5f2  cmp     dword ptr [r14+64h], 1
0x18001a5f7  jz      loc_18001C9E8
0x18001a5fd  add     rax, 130h
0x18001a603  cmp     [rax], r13
0x18001a606  jz      loc_18001B4F2
0x18001a60c  mov     rax, [r14]
0x18001a60f  mov     rcx, r14
0x18001a612  mov     rax, [rax+240h]
0x18001a619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a61e  xorps   xmm0, xmm0
0x18001a621  movups  [rbp+4E0h+var_3F0], xmm0
0x18001a628  movups  xmm2, xmmword ptr [r14+0A0h]
0x18001a630  ucomiss xmm2, xmm2
0x18001a633  movups  [rbp+4E0h+var_3F0], xmm2
0x18001a63a  jp      loc_18001C487
0x18001a640  movaps  xmm1, xmm2
0x18001a643  shufps  xmm1, xmm2, 0AAh
0x18001a647  ucomiss xmm1, xmm1
0x18001a64a  jp      loc_18001C487
0x18001a650  movaps  xmm0, xmm2
0x18001a653  shufps  xmm0, xmm2, 55h ; 'U'
0x18001a657  ucomiss xmm0, xmm0
0x18001a65a  jp      loc_18001C487
0x18001a660  movaps  xmm3, xmm2
0x18001a663  shufps  xmm3, xmm2, 0FFh
0x18001a667  ucomiss xmm3, xmm3
0x18001a66a  jp      loc_18001C487
0x18001a670  mov     [rbp+4E0h+var_538], r13
0x18001a674  mov     rcx, r14
0x18001a677  mov     rax, [r14]
0x18001a67a  movss   dword ptr [rbp+4E0h+var_428+4], xmm2
0x18001a682  movss   dword ptr [rbp+4E0h+var_428+8], xmm0
0x18001a68a  movss   dword ptr [rbp+4E0h+var_428+0Ch], xmm1
0x18001a692  mov     rax, [rax+258h]
0x18001a699  movss   [rbp+4E0h+var_418], xmm3
0x18001a6a1  mov     byte ptr [rbp+4E0h+var_428], 1
0x18001a6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ad  mov     rcx, [r14]
0x18001a6b0  mov     [rbp+4E0h+var_550], eax
0x18001a6b3  mov     rax, [rcx+240h]
0x18001a6ba  mov     rcx, r14
0x18001a6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c2  test    rax, rax
0x18001a6c5  jz      loc_18001D152
0x18001a6cb  cmp     dword ptr [r14+64h], 1
0x18001a6d0  jz      loc_18001CA0E
0x18001a6d6  lea     rbx, [rax+130h]
0x18001a6dd  mov     rbx, [rbx]
0x18001a6e0  mov     r13, [r14+30h]
0x18001a6e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a6eb  mov     rdi, [r14+28h]
0x18001a6ef  mov     ecx, 0D0h; unsigned __int64
0x18001a6f4  mov     [rbp+4E0h+var_560], 0
0x18001a6fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a701  mov     rsi, rax
0x18001a704  test    rax, rax
0x18001a707  jz      loc_18001D300
0x18001a70d  mov     eax, [r14+318h]
0x18001a714  lea     rcx, [rsi+90h]; void *
0x18001a71b  movups  xmm1, xmmword ptr [r14+308h]
0x18001a723  mov     dword ptr [rsi+18h], 1
0x18001a72a  movups  xmm0, cs:?msc_nullClip@Clip@@0UD2D_RECT_F@@B; D2D_RECT_F const Clip::msc_nullClip
0x18001a731  mov     [rsi+1Ch], r12b
0x18001a735  movups  xmmword ptr [rsi+20h], xmm0
0x18001a739  movups  xmmword ptr [rsi+30h], xmm1
0x18001a73d  mov     [rsi+40h], eax
0x18001a740  lea     rax, ??_7ClipRectSubTarget@@6B@; const ClipRectSubTarget::`vftable'
0x18001a747  mov     [rsi], rax
0x18001a74a  xor     eax, eax
0x18001a74c  mov     [rsi+58h], rax
0x18001a750  mov     [rsi+60h], rax
0x18001a754  mov     [rsi+68h], rax
0x18001a758  mov     [rsi+70h], rax
0x18001a75c  mov     [rsi+78h], rax
0x18001a760  mov     [rsi+80h], rax
0x18001a767  mov     [rsi+88h], rbx
0x18001a76e  call    ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(void)
0x18001a773  lea     rcx, [rsi+98h]; void *
0x18001a77a  call    ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(void)
0x18001a77f  lea     rcx, [rsi+0A0h]; void *
0x18001a786  call    ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(void)
0x18001a78b  lea     rcx, [rsi+0A8h]; void *
0x18001a792  call    ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(void)
0x18001a797  mov     eax, [rbp+4E0h+var_550]
0x18001a79a  xor     ebx, ebx
0x18001a79c  mov     [rsi+0C0h], eax
0x18001a7a2  mov     [rbp+4E0h+var_478], rbx
0x18001a7a6  test    rdi, rdi
0x18001a7a9  jz      short loc_18001A7BE
0x18001a7ab  mov     rax, [rdi]
0x18001a7ae  mov     rcx, rdi
0x18001a7b1  mov     rax, [rax+8]
0x18001a7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ba  mov     [rbp+4E0h+var_478], rdi
0x18001a7be  lea     rdx, [rsi+58h]
0x18001a7c2  lea     rcx, [rbp+4E0h+var_478]
0x18001a7c6  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x18001a7cb  mov     rcx, [rbp+4E0h+var_478]
0x18001a7cf  test    rcx, rcx
0x18001a7d2  jz      short loc_18001A7E4
0x18001a7d4  mov     rax, [rcx]
0x18001a7d7  mov     rax, [rax+10h]
0x18001a7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7e0  mov     [rbp+4E0h+var_478], rbx
0x18001a7e4  mov     [rbp+4E0h+var_470], rbx
0x18001a7e8  test    r13, r13
0x18001a7eb  jnz     loc_18001B4B0
0x18001a7f1  lea     rdx, [rsi+60h]
0x18001a7f5  lea     rcx, [rbp+4E0h+var_470]
0x18001a7f9  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x18001a7fe  mov     rcx, [rbp+4E0h+var_470]
0x18001a802  test    rcx, rcx
0x18001a805  jz      loc_18001B4A8
0x18001a80b  mov     rax, [rcx]
0x18001a80e  mov     rax, [rax+10h]
0x18001a812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a817  xor     r13d, r13d
0x18001a81a  mov     [rbp+4E0h+var_470], r13
0x18001a81e  xorps   xmm0, xmm0
0x18001a821  lea     rax, ??_7?$RefCountedObject@VClipRectSubTarget@@ULockingRequired@@UDeleteOnZeroReference@@@@6B@; const RefCountedObject<ClipRectSubTarget,LockingRequired,DeleteOnZeroReference>::`vftable'
0x18001a828  movups  xmmword ptr [rsi+0B0h], xmm0
0x18001a82f  mov     [rsi], rax
0x18001a832  mov     dword ptr [rsi+0C8h], 1
0x18001a83c  lea     rdx, [rbp+4E0h+var_560]
0x18001a840  mov     [rbp+4E0h+var_440], r13
0x18001a847  lea     rcx, [rbp+4E0h+var_440]
0x18001a84e  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x18001a853  mov     rcx, [rbp+4E0h+var_440]
0x18001a85a  test    rcx, rcx
0x18001a85d  jz      short loc_18001A872
0x18001a85f  mov     rax, [rcx]
0x18001a862  mov     rax, [rax+8]
0x18001a866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a86b  mov     [rbp+4E0h+var_440], r13
0x18001a872  mov     [rbp+4E0h+var_560], rsi
0x18001a876  test    rsi, rsi
0x18001a879  jz      loc_18001B702
0x18001a87f  mov     eax, [rbp+4E0h+var_418]
0x18001a885  lea     rdx, [rbp+4E0h+var_518]
0x18001a889  movups  xmm0, [rbp+4E0h+var_428]
0x18001a890  lea     rcx, [rsi+1Ch]
0x18001a894  mov     dword ptr [rbp+4E0h+var_508], eax
0x18001a897  movups  xmmword ptr [rbp+4E0h+var_518], xmm0
0x18001a89b  call    ??$swap@_N$0A@@std@@YAXAEA_N0@Z; std::swap<bool,0>(bool &,bool &)
0x18001a8a0  lea     rcx, [rsi+24h]
0x18001a8a4  lea     rdx, [rbp+4E0h+var_518+8]
0x18001a8a8  call    ??$swap@M$0A@@std@@YAXAEAM0@Z; std::swap<float,0>(float &,float &)
0x18001a8ad  lea     rdx, [rbp+4E0h+var_518+4]
0x18001a8b1  lea     rcx, [rsi+20h]
0x18001a8b5  call    ??$swap@M$0A@@std@@YAXAEAM0@Z; std::swap<float,0>(float &,float &)
0x18001a8ba  lea     rcx, [rsi+2Ch]
0x18001a8be  lea     rdx, [rbp+4E0h+var_508]
0x18001a8c2  call    ??$swap@M$0A@@std@@YAXAEAM0@Z; std::swap<float,0>(float &,float &)
0x18001a8c7  lea     rcx, [rsi+28h]
0x18001a8cb  lea     rdx, [rbp+4E0h+var_518+0Ch]
0x18001a8cf  call    ??$swap@M$0A@@std@@YAXAEAM0@Z; std::swap<float,0>(float &,float &)
0x18001a8d4  movups  xmm5, xmmword ptr [rsi+34h]
0x18001a8d8  movaps  xmm3, cs:xmmword_1803875F0
0x18001a8df  cvtps2dq xmm1, xmm5
0x18001a8e3  movaps  xmm0, xmm5
0x18001a8e6  movaps  xmm4, xmm5
0x18001a8e9  andps   xmm4, cs:xmmword_1803875D0
0x18001a8f0  pcmpgtd xmm4, cs:xmmword_1803875E0
0x18001a8f8  movaps  xmm6, xmm4
0x18001a8fb  andps   xmm4, xmm5
0x18001a8fe  cvtdq2ps xmm2, xmm1
0x18001a901  cmpltps xmm0, xmm2
0x18001a905  andps   xmm0, xmm3
0x18001a908  cmpltps xmm2, xmm5
0x18001a90c  paddd   xmm0, xmm1
0x18001a910  andnps  xmm3, xmm2
0x18001a913  movss   xmm2, dword ptr [rsi+20h]
0x18001a918  psubd   xmm0, xmm3
0x18001a91c  cvtdq2ps xmm0, xmm0
0x18001a91f  andnps  xmm6, xmm0
0x18001a922  orps    xmm6, xmm4
0x18001a925  movaps  xmm7, xmm6
0x18001a928  movaps  xmm5, xmm6
0x18001a92b  shufps  xmm7, xmm6, 0AAh
0x18001a92f  movaps  xmm4, xmm6
0x18001a932  comiss  xmm7, xmm2
0x18001a935  shufps  xmm5, xmm6, 55h ; 'U'
0x18001a939  shufps  xmm4, xmm6, 0FFh
0x18001a93d  jb      loc_18001C379
0x18001a943  movss   xmm0, dword ptr [rsi+24h]
0x18001a948  comiss  xmm4, xmm0
0x18001a94b  jb      loc_18001C38A
0x18001a951  movss   dword ptr [rsi+24h], xmm0
0x18001a956  movss   xmm1, dword ptr [rsi+28h]
0x18001a95b  comiss  xmm1, xmm6
0x18001a95e  jb      loc_18001C553
0x18001a964  movss   dword ptr [rsi+28h], xmm1
0x18001a969  movss   xmm0, dword ptr [rsi+2Ch]
0x18001a96e  comiss  xmm0, xmm5
0x18001a971  jb      loc_18001C564
0x18001a977  comiss  xmm2, xmm6
0x18001a97a  movss   dword ptr [rsi+2Ch], xmm0
0x18001a97f  jb      loc_18001C575
0x18001a985  movss   dword ptr [rsi+20h], xmm2
0x18001a98a  movss   xmm1, dword ptr [rsi+24h]
0x18001a98f  comiss  xmm1, xmm5
0x18001a992  jb      loc_18001C586
0x18001a998  movss   dword ptr [rsi+24h], xmm1
0x18001a99d  movss   xmm3, dword ptr [rsi+28h]
0x18001a9a2  comiss  xmm7, xmm3
0x18001a9a5  jb      loc_18001C39B
0x18001a9ab  movss   dword ptr [rsi+28h], xmm3
0x18001a9b0  movss   xmm2, dword ptr [rsi+2Ch]
0x18001a9b5  comiss  xmm4, xmm2
0x18001a9b8  jb      loc_18001C3AC
0x18001a9be  movss   dword ptr [rsi+2Ch], xmm2
0x18001a9c3  movss   xmm0, dword ptr [rsi+20h]
0x18001a9c8  ucomiss xmm0, xmm0
0x18001a9cb  jp      loc_18001C4B0
0x18001a9d1  ucomiss xmm3, xmm3
0x18001a9d4  jp      loc_18001C4B0
0x18001a9da  ucomiss xmm1, xmm1
0x18001a9dd  jp      loc_18001C4B0
0x18001a9e3  ucomiss xmm2, xmm2
0x18001a9e6  jp      loc_18001C4B0
0x18001a9ec  comiss  xmm3, xmm0
0x18001a9ef  jbe     loc_18001C259
0x18001a9f5  comiss  xmm2, xmm1
0x18001a9f8  jbe     loc_18001C259
0x18001a9fe  movss   dword ptr [rsi+20h], xmm0
0x18001aa03  movss   dword ptr [rsi+24h], xmm1
0x18001aa08  movss   dword ptr [rsi+28h], xmm3
0x18001aa0d  movss   dword ptr [rsi+2Ch], xmm2
0x18001aa12  movss   xmm0, dword ptr [rsi+20h]
0x18001aa17  ucomiss xmm0, xmm0
0x18001aa1a  jp      loc_18001C4C3
0x18001aa20  ucomiss xmm3, xmm3
0x18001aa23  jp      loc_18001C4C3
0x18001aa29  ucomiss xmm1, xmm1
0x18001aa2c  jp      loc_18001C4C3
0x18001aa32  ucomiss xmm2, xmm2
0x18001aa35  jp      loc_18001C4C3
0x18001aa3b  movups  xmm0, xmmword ptr [rsi+20h]
0x18001aa3f  mov     ebx, r13d
0x18001aa42  xorps   xmm2, xmm2
0x18001aa45  xorps   xmm4, xmm4
0x18001aa48  movups  xmmword ptr [rsi+48h], xmm0
0x18001aa4c  mov     eax, [r14+20h]
0x18001aa50  movss   xmm0, dword ptr [rsi+48h]
0x18001aa55  comiss  xmm0, xmm13
0x18001aa59  cvtsi2ss xmm2, rax
0x18001aa5e  mov     eax, [r14+24h]
0x18001aa62  cvtsi2ss xmm4, rax
0x18001aa67  jb      loc_18001C597
0x18001aa6d  movss   dword ptr [rsi+48h], xmm0
0x18001aa72  movss   xmm1, dword ptr [rsi+4Ch]
0x18001aa77  comiss  xmm1, xmm13
0x18001aa7b  jb      loc_18001C5AA
  ... truncated ...
```
