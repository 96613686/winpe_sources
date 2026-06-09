# truetype::gridfit::gridfit

- ea: `0x1800ea780`
- end: `0x1800ed04e`
- name: `truetype::gridfit::gridfit`
- size: `10446`
- prototype: `unsigned __int64 __fastcall(unsigned __int64, __int64, const __m128i *, _QWORD *, __int64, __int64, __int64, __int64 *, __int16, char, char, char, unsigned __int16, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800e94e0`

## callees

- `0x180089c70`
- `0x180089db0`
- `0x1800dd810`
- `0x1800decf0`
- `0x1800df210`
- `0x1800df3c0`
- `0x1800df5b0`
- `0x1800ea780`
- `0x1800ed670`
- `0x1800f1e80`
- `0x1800f2080`
- `0x180110f60`
- `0x180111190`
- `0x180212f4c`
- `0x180316190`
- `0x1803168c1`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316d00`
- `0x180318360`

## import_xrefs

- `kernel32!HeapFree` at `0x1800ea891`
- `kernel32!HeapFree` at `0x1800ead6e`
- `kernel32!HeapFree` at `0x1800ec044`
- `kernel32!HeapFree` at `0x1800ec1fb`
- `kernel32!HeapFree` at `0x1800ea85a`
- `kernel32!HeapFree` at `0x1800ead6e`
- `kernel32!HeapFree` at `0x1800ec044`
- `kernel32!HeapFree` at `0x1800ec1fb`
- `kernel32!GetProcessHeap` at `0x1800ea886`
- `kernel32!GetProcessHeap` at `0x1800ead5c`
- `kernel32!GetProcessHeap` at `0x1800ec036`
- `kernel32!GetProcessHeap` at `0x1800ec1ed`
- `kernel32!GetProcessHeap` at `0x1800ea853`
- `kernel32!GetProcessHeap` at `0x1800ead5c`
- `kernel32!GetProcessHeap` at `0x1800ec036`
- `kernel32!GetProcessHeap` at `0x1800ec1ed`

## string_xrefs

- `0x1800ece67`: `assertion failed: !self.resources.glyph_tree.is_empty()assertion failed: *remaining_components > 0assertion failed: glyph_data.parent < *current_nodeassertion failed: self.glyph_element.x.len() >= element::PHANTOMCOUNTassertion failed: points_start + element::PHANTOMCOUNT <= self.glyph_element.x.capacity()rust\truetype\src\interp\concertina.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
unsigned __int64 __fastcall truetype::gridfit::gridfit(
        unsigned __int64 a1,
        __int64 a2,
        const __m128i *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        __int16 a9,
        char a10,
        char a11,
        char a12,
        unsigned __int16 a13,
        unsigned __int16 a14,
        __int64 a15)
{
  _WORD *v15; // r13
  unsigned __int64 v16; // r12
  __int64 v17; // rdi
  __int64 v18; // rbx
  void **v19; // rdi
  void *v20; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int8 v22; // cl
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  const __m128i *v26; // r8
  __m128i v27; // xmm1
  _QWORD *v28; // rax
  __int64 v29; // rbx
  __int64 v30; // r15
  __int64 v31; // r8
  unsigned __int64 v32; // r11
  __int64 v33; // rbx
  __int64 v34; // rsi
  __int16 v35; // di
  __int64 v36; // r13
  int v37; // edi
  __int64 v38; // rbx
  __int16 v39; // r14
  unsigned __int64 v40; // r10
  __int64 v41; // rdx
  __int64 v42; // r15
  __int64 v43; // rdx
  unsigned int v44; // et0
  unsigned __int16 v45; // r8
  unsigned __int16 v46; // r9
  unsigned __int64 v47; // rdi
  __int64 v48; // r13
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rsi
  unsigned __int16 v53; // r14
  unsigned __int16 v54; // bx
  unsigned __int64 v55; // r15
  HANDLE v56; // rax
  int v57; // edi
  __int64 v58; // r14
  _WORD *v59; // rbx
  unsigned __int64 glyph_hor_metrics; // rax
  unsigned __int64 v61; // r13
  __int64 glyph_vert_metrics; // rax
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // r11
  char v65; // r10
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // r8
  __int64 v69; // r14
  __int64 v70; // r15
  __int64 v71; // rbx
  __int64 v72; // rax
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // r8
  unsigned __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdx
  unsigned int v78; // edi
  unsigned __int64 v79; // r9
  int v80; // esi
  unsigned __int64 v81; // rcx
  unsigned int v82; // r9d
  unsigned int v83; // r9d
  bool v84; // r9
  unsigned __int64 v85; // r9
  __int16 v86; // r10
  int v87; // r10d
  int v88; // r13d
  __int16 v89; // r10
  int v90; // r13d
  __int16 v91; // r11
  __int16 v92; // si
  __int64 v93; // r8
  __int16 v94; // dx
  char v95; // r9
  unsigned int v96; // ecx
  __int64 v97; // r9
  __int64 v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // r11
  __int64 v101; // rdx
  __int64 v102; // rbx
  __int64 v103; // rdx
  __int64 v104; // r10
  __int64 v105; // r8
  __int64 v106; // r8
  __int64 v107; // rcx
  char v108; // r14
  __int64 v109; // r9
  __int64 v110; // r15
  __int64 v111; // r11
  __int64 v112; // rsi
  __int64 v113; // rcx
  __int64 v114; // rbx
  int v115; // esi
  int v116; // r15d
  __int64 v117; // r8
  __int64 v118; // rdx
  __int64 v119; // rbx
  int v120; // ecx
  int v121; // r12d
  bool v122; // zf
  int v123; // eax
  int v124; // ecx
  int v125; // eax
  char v126; // r9
  char v127; // r14
  unsigned __int64 v128; // r13
  char v129; // di
  __int16 v130; // r14
  int v131; // ebx
  int v132; // esi
  char v133; // r15
  __int64 v134; // rax
  __int64 v135; // rcx
  __int16 v136; // dx
  unsigned __int64 v137; // rbx
  unsigned __int64 v138; // r8
  unsigned __int64 v139; // rsi
  unsigned __int64 v140; // rdx
  unsigned __int64 v141; // rax
  unsigned __int64 v142; // rcx
  unsigned __int64 v143; // rax
  unsigned __int16 v144; // cx
  __int64 v145; // r8
  int v146; // edi
  int v147; // r14d
  __int64 v148; // r15
  unsigned __int64 v149; // rbx
  __int64 v150; // r15
  __int64 v151; // r12
  _DWORD *v152; // rcx
  unsigned __int64 v153; // r13
  unsigned __int64 v154; // r13
  unsigned __int64 v155; // r8
  __int64 v156; // rbx
  __int64 v157; // r15
  _DWORD *v158; // rcx
  unsigned __int64 v159; // rdx
  unsigned __int64 v160; // rcx
  unsigned __int64 v161; // rax
  __int64 v162; // rbx
  unsigned __int64 v163; // r14
  unsigned __int64 v164; // r15
  __int64 v165; // rax
  __int64 v166; // rcx
  int v167; // edx
  int v168; // r8d
  int v169; // r9d
  int v170; // r10d
  int v171; // r11d
  int v172; // edi
  unsigned __int64 v173; // rdx
  bool v174; // cf
  _WORD *v175; // rax
  unsigned __int64 v176; // rcx
  unsigned __int64 v177; // rdx
  unsigned __int64 v178; // rdx
  __int64 v179; // rbx
  __int16 v180; // ax
  __int64 v181; // rdi
  __int64 v182; // r14
  void **v183; // r14
  void *v184; // rsi
  HANDLE v185; // rax
  __int16 v186; // ax
  unsigned __int16 v187; // r9
  BOOL v188; // ecx
  unsigned __int64 v189; // rdx
  unsigned __int64 v190; // rcx
  __int64 v191; // r14
  __int64 v192; // rdi
  unsigned __int64 v193; // r15
  int v194; // eax
  unsigned __int64 v195; // rax
  int v196; // eax
  int v197; // eax
  int v198; // ecx
  HANDLE v199; // rax
  _QWORD *v201; // rsi
  char v202; // r8
  int v203; // ecx
  __int64 v204; // rax
  unsigned __int64 v205; // rcx
  unsigned __int16 v206; // r11
  unsigned __int64 v207; // r12
  unsigned __int16 v208; // r8
  unsigned __int64 v209; // r9
  unsigned int v210; // edx
  unsigned int v211; // r8d
  __int64 v212; // rax
  __int64 v213; // rbx
  unsigned __int64 v214; // rax
  __int64 v215; // r11
  unsigned int v216; // esi
  unsigned __int64 v217; // r13
  __int64 v218; // rdx
  __int64 v219; // rcx
  __int64 v220; // r15
  unsigned int v221; // ebx
  unsigned int v222; // esi
  int v223; // r15d
  unsigned int v224; // edx
  __int64 v225; // r11
  __int64 v226; // rax
  unsigned __int64 v227; // r8
  int v228; // r9d
  int v229; // edx
  int v230; // ecx
  __int16 v231; // dx
  unsigned int v232; // ebx
  __int16 v233; // dx
  unsigned int v234; // eax
  unsigned int v235; // ecx
  signed int v236; // r8d
  unsigned __int64 v237; // rsi
  __int64 v238; // rdx
  __int64 v239; // r8
  unsigned __int64 v240; // r8
  bool v241; // cc
  signed int v242; // eax
  unsigned __int64 v243; // r11
  __int64 v244; // r9
  unsigned __int64 v245; // r9
  int v246; // eax
  unsigned int v247; // ebx
  unsigned int v248; // r9d
  int v249; // esi
  int v250; // r10d
  int v251; // r15d
  int v252; // r10d
  int v253; // ecx
  int v254; // r8d
  int v255; // eax
  int v256; // ecx
  __int64 v257; // rdx
  __int64 v258; // rdx
  __int64 v259; // rcx
  __int64 v260; // rax
  signed __int64 v261; // rax
  __int64 v262; // rax
  int v263; // ecx
  __int64 v264; // rdx
  __int64 v265; // rcx
  __int64 v266; // rax
  signed __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rbx
  signed __int64 v270; // rcx
  __int64 v271; // rax
  __int64 v272; // rax
  signed __int64 v273; // rcx
  int v274; // edx
  __int64 v275; // r8
  __int64 v276; // rsi
  __int64 v277; // r10
  __int64 v278; // rax
  unsigned __int64 v279; // rax
  unsigned __int64 v280; // r11
  __int64 v281; // r8
  __int64 v282; // r8
  int v283; // eax
  int v284; // ecx
  int v285; // edx
  int v286; // r8d
  int v287; // r11d
  int v288; // eax
  int v289; // ecx
  int v290; // edx
  int v291; // eax
  signed int v292; // eax
  signed int v293; // ecx
  int v294; // r11d
  int v295; // esi
  unsigned int v296; // r10d
  unsigned __int64 v297; // rcx
  unsigned __int64 v298; // rax
  unsigned int v299; // ecx
  char v300; // r15
  unsigned __int64 v301; // r9
  unsigned __int64 v302; // rdx
  __int64 v303; // rax
  __int64 v304; // rcx
  __int64 v305; // rax
  int v306; // r11d
  int v307; // ecx
  char v308; // r10
  int v309; // r11d
  int v310; // r14d
  unsigned __int64 v311; // rcx
  _DWORD *v312; // rdi
  _DWORD *v313; // r8
  __int32 v314; // esi
  __int32 v315; // eax
  int v316; // ebx
  unsigned __int64 v317; // rcx
  unsigned __int64 v318; // r15
  _DWORD *v319; // r14
  unsigned __int64 v320; // r15
  __m128i v321; // xmm0
  __int64 v322; // r13
  __m128i v323; // xmm2
  _DWORD *v324; // rcx
  int v325; // eax
  unsigned __int64 v326; // rcx
  unsigned __int8 v327; // si
  unsigned int v328; // eax
  unsigned __int64 v329; // r9
  _DWORD *v330; // rdx
  unsigned __int64 v331; // r9
  unsigned __int64 v332; // r10
  __m128i v333; // xmm0
  __int64 v334; // r11
  __m128i v335; // xmm2
  _DWORD *v336; // rcx
  char **v337; // r8
  __int16 v338; // [rsp+20h] [rbp-60h]
  _QWORD v339[9]; // [rsp+70h] [rbp-10h] BYREF
  char v340; // [rsp+B8h] [rbp+38h]
  __int64 v341; // [rsp+C0h] [rbp+40h]
  __int64 v342; // [rsp+C8h] [rbp+48h]
  unsigned __int64 v343; // [rsp+D0h] [rbp+50h]
  __int64 v344; // [rsp+D8h] [rbp+58h]
  _WORD *v345; // [rsp+E0h] [rbp+60h]
  int v346; // [rsp+ECh] [rbp+6Ch]
  unsigned __int64 v347; // [rsp+F0h] [rbp+70h]
  __int64 v348; // [rsp+F8h] [rbp+78h]
  __int64 v349; // [rsp+100h] [rbp+80h]
  __int64 v350; // [rsp+108h] [rbp+88h]
  __int64 v351; // [rsp+110h] [rbp+90h]
  __int64 v352; // [rsp+118h] [rbp+98h]
  unsigned __int64 v353; // [rsp+120h] [rbp+A0h]
  __int64 v354; // [rsp+128h] [rbp+A8h]
  __int64 v355; // [rsp+130h] [rbp+B0h]
  _QWORD *v356; // [rsp+138h] [rbp+B8h]
  __int64 v357; // [rsp+140h] [rbp+C0h]
  __int64 v358; // [rsp+148h] [rbp+C8h]
  unsigned __int64 v359; // [rsp+150h] [rbp+D0h]
  unsigned __int64 v360; // [rsp+158h] [rbp+D8h]
  unsigned int v361; // [rsp+160h] [rbp+E0h]
  int v362; // [rsp+164h] [rbp+E4h]
  int v363; // [rsp+168h] [rbp+E8h]
  signed int v364; // [rsp+16Ch] [rbp+ECh]
  __int64 v365; // [rsp+170h] [rbp+F0h]
  __int64 v366; // [rsp+178h] [rbp+F8h]
  const __m128i *v367; // [rsp+180h] [rbp+100h]
  unsigned __int64 v368; // [rsp+188h] [rbp+108h]
  __int64 v369; // [rsp+190h] [rbp+110h] BYREF
  _BYTE v370[6]; // [rsp+198h] [rbp+118h]
  unsigned __int16 v371; // [rsp+19Eh] [rbp+11Eh]
  __int64 v372; // [rsp+1A0h] [rbp+120h]
  unsigned __int64 v373; // [rsp+1A8h] [rbp+128h]
  __int64 v374; // [rsp+1B0h] [rbp+130h]
  __int64 v375; // [rsp+1B8h] [rbp+138h]
  __int64 v376; // [rsp+1C0h] [rbp+140h]
  __int64 v377; // [rsp+1C8h] [rbp+148h]
  __int64 v378; // [rsp+1D0h] [rbp+150h]
  _WORD *v379; // [rsp+1D8h] [rbp+158h]
  unsigned __int64 v380; // [rsp+1E0h] [rbp+160h]
  unsigned __int64 v381; // [rsp+1E8h] [rbp+168h]
  LPVOID lpMem; // [rsp+1F0h] [rbp+170h]
  unsigned int v383; // [rsp+1FCh] [rbp+17Ch]
  __int64 v384; // [rsp+200h] [rbp+180h]
  unsigned int v385; // [rsp+20Ch] [rbp+18Ch]
  __int64 v386; // [rsp+210h] [rbp+190h]
  unsigned __int64 v387; // [rsp+218h] [rbp+198h]
  __int64 v388; // [rsp+220h] [rbp+1A0h]
  __int64 v389; // [rsp+228h] [rbp+1A8h]
  unsigned int v390; // [rsp+234h] [rbp+1B4h]
  __int64 v391; // [rsp+238h] [rbp+1B8h]

  v391 = -2;
  v367 = a3;
  v15 = (_WORD *)a2;
  v16 = a1;
  v348 = *(_QWORD *)(a2 + 16);
  a4[2] = 0;
  a4[5] = 0;
  a4[8] = 0;
  a4[11] = 0;
  a4[14] = 0;
  a4[17] = 0;
  a4[23] = 0;
  a4[26] = 0;
  a4[32] = 0;
  a4[29] = 0;
  v356 = a4;
  a4[20] = 0;
  v17 = *(_QWORD *)(a1 + 8);
  v18 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  if ( v18 )
  {
    v19 = (void **)(v17 + 88);
    do
    {
      if ( *(v19 - 1) )
      {
        v20 = *v19;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v20);
      }
      v19 += 39;
      --v18;
    }
    while ( v18 );
  }
  v22 = 2;
  if ( !*(_QWORD *)v16 )
  {
    LOWORD(v61) = 5131;
    return ((unsigned __int64)v22 << 32) | (unsigned int)((_DWORD)v16 << 16) | (unsigned __int16)v61;
  }
  v23 = *(_QWORD *)(v16 + 16);
  if ( v23 == *(_QWORD *)v16 )
    alloc::raw_vec::RawVec_truetype::gridfit::GlyphData_alloc::alloc::Global_::grow_one_truetype::gridfit::GlyphData_alloc::alloc::Global_(
      v16,
      &off_180344A10);
  v24 = *(_QWORD *)(v16 + 8);
  v25 = 312 * v23;
  *(_QWORD *)(v24 + v25) = 0;
  *(_QWORD *)(v24 + v25 + 24) = 0;
  *(_QWORD *)(v24 + v25 + 40) = 0;
  *(_QWORD *)(v24 + v25 + 56) = 0;
  *(_QWORD *)(v24 + v25 + 80) = 0;
  *(_QWORD *)(v24 + v25 + 88) = 1;
  *(_OWORD *)(v24 + v25 + 96) = 0;
  *(_OWORD *)(v24 + v25 + 112) = 0;
  *(_QWORD *)(v24 + v25 + 128) = 0x800080007FFF7FFFuLL;
  *(_OWORD *)(v24 + v25 + 136) = 0;
  *(_OWORD *)(v24 + v25 + 152) = 0;
  *(_OWORD *)(v24 + v25 + 168) = 0;
  *(_OWORD *)(v24 + v25 + 184) = 0;
  *(_WORD *)(v24 + v25 + 200) = 0;
  *(_WORD *)(v24 + v25 + 250) = 2;
  v26 = v367;
  v27 = _mm_loadu_si128(v367 + 1);
  *(__m128i *)(v24 + v25 + 264) = _mm_loadu_si128(v367);
  *(__m128i *)(v24 + v25 + 280) = v27;
  *(_DWORD *)(v24 + v25 + 296) = v26[2].m128i_i32[0];
  *(_WORD *)(v24 + v25 + 300) = a9;
  *(_WORD *)(v24 + v25 + 302) = -1;
  *(_DWORD *)(v24 + v25 + 304) = 0x10000;
  v339[0] = v15;
  v340 = a10;
  v339[1] = v26;
  v28 = v356;
  v339[2] = v356;
  v339[3] = a5;
  v339[4] = a6;
  v339[5] = a7;
  v339[6] = a8;
  v339[7] = a15;
  v339[8] = v16;
  v29 = v23 + 1;
  *(_QWORD *)(v16 + 16) = v29;
  if ( !v29 )
    core::panicking::panic(
      "assertion failed: !self.resources.glyph_tree.is_empty()assertion failed: *remaining_components > 0assertion failed"
      ": glyph_data.parent < *current_nodeassertion failed: self.glyph_element.x.len() >= element::PHANTOMCOUNTassertion "
      "failed: points_start + element::PHANTOMCOUNT <= self.glyph_element.x.capacity()rust\\truetype\\src\\interp\\concertina.rs",
      55,
      &off_180344A28);
  v28[2] = 0;
  v28[5] = 0;
  v28[8] = 0;
  v28[11] = 0;
  v28[14] = 0;
  v28[17] = 0;
  v28[23] = 0;
  v28[26] = 0;
  v28[32] = 0;
  v28[29] = 0;
  v28[20] = 0;
  v345 = v15 + 12;
  v360 = (unsigned __int16)v15[166];
  LOWORD(v350) = v15[144];
  v346 = (unsigned __int16)v15[165];
  v341 = *(_QWORD *)(a6 + 32);
  v344 = *(_QWORD *)(a6 + 40);
  v30 = *a8;
  v31 = a8[1];
  v32 = 0;
  v33 = 0;
  v376 = *a8;
  v375 = v16;
  v379 = v15;
  v378 = v31;
  do
  {
    v34 = *(_QWORD *)(v16 + 8);
    v387 = v32;
    v380 = 312 * v32;
    v35 = *(_WORD *)(v34 + 312 * v32 + 300);
    truetype::sfnt::sfac::get_glyph_location((unsigned int)&v369, v30, v31, (_DWORD)v15, v35);
    if ( (_BYTE)v369 == 1 )
    {
      LOWORD(v61) = WORD1(v369);
      goto LABEL_221;
    }
    v16 = *(unsigned int *)v370;
    v352 = v33;
    if ( *(_DWORD *)v370 )
    {
      v36 = HIDWORD(v369);
      v338 = v35;
      v37 = v378;
      truetype::sfnt::sfac::read_glyph_header_core((unsigned int)&v369, v30, v378, (_DWORD)v379, v338);
      if ( (_BYTE)v369 == 1 )
      {
        LOWORD(v61) = WORD1(v369);
        goto LABEL_221;
      }
      v389 = WORD1(v369);
      v38 = *(unsigned __int16 *)v370;
      v388 = HIDWORD(v369);
      v39 = *(_WORD *)&v370[2];
      v16 += v36;
      sfnt_reader::SfntReader::get_file_fragment((unsigned int)&v369, v30, v37, v36, v16);
      v41 = v369;
      if ( __OFSUB__(-v369, 1) )
      {
        LOWORD(v61) = *(_WORD *)v370;
        goto LABEL_221;
      }
      v42 = v372;
      v16 = *(unsigned __int16 *)v370
          | ((unsigned __int64)*(unsigned int *)&v370[2] << 16)
          | ((unsigned __int64)v371 << 48);
      if ( v39 != -1 )
      {
        if ( v39 < 0 )
        {
          v186 = 5127;
          goto LABEL_219;
        }
        if ( v39 )
        {
          v384 = v369;
          LOWORD(v369) = 0;
          v343 = *(unsigned __int16 *)v370
               | ((unsigned __int64)*(unsigned int *)&v370[2] << 16)
               | ((unsigned __int64)v371 << 48);
          if ( (_guard_dispatch_icall_fptr() & 1) == 0 )
          {
            LOWORD(v44) = (_WORD)v369 << 8;
            HIWORD(v44) = BYTE1(v369);
            v45 = __ROL2__(v44 >> 8, 8) + 1;
            v46 = v39;
            v41 = v384;
LABEL_22:
            v50 = v388 << 16;
            v51 = (v388 << 16) | (v38 << 48);
            LOBYTE(v50) = v39 == -1;
            v388 = v50;
            LOBYTE(v40) = v39 != -1;
            v49 = v51 | v389;
            v48 = 10;
            v47 = v16;
            goto LABEL_23;
          }
          if ( v43 )
          {
            v343 = v16;
            core::ptr::drop_in_place_std::io::error::Error_(v43);
          }
          v186 = 5120;
          v41 = v384;
LABEL_219:
          LOWORD(v61) = v186;
          if ( v41 )
          {
            v199 = GetProcessHeap();
            HeapFree(v199, 0, (LPVOID)v16);
          }
          goto LABEL_221;
        }
      }
      v46 = 0;
      v45 = 0;
      goto LABEL_22;
    }
    v45 = 1;
    v47 = 1;
    v42 = 0;
    v48 = 0;
    v40 = 0;
    v388 = 0;
    v46 = 1;
    v49 = 0;
    v41 = 0;
LABEL_23:
    v52 = v380 + v34;
    v16 = v47 >> 16;
    if ( *(_QWORD *)(v52 + 80) )
    {
      lpMem = *(LPVOID *)(v52 + 88);
      v377 = v42;
      v389 = v49;
      v384 = v41;
      v53 = v45;
      v54 = v46;
      v55 = v40;
      v56 = GetProcessHeap();
      HeapFree(v56, 0, lpMem);
      v40 = v55;
      v46 = v54;
      v45 = v53;
      v41 = v384;
      v49 = v389;
      v42 = v377;
    }
    *(_QWORD *)(v52 + 80) = v41;
    v368 = v47;
    *(_WORD *)(v52 + 88) = v47;
    *(_DWORD *)(v52 + 90) = v16;
    *(_WORD *)(v52 + 94) = HIWORD(v47);
    *(_QWORD *)(v52 + 96) = v42;
    *(_QWORD *)(v52 + 104) = v48;
    *(_QWORD *)(v52 + 152) = v46;
    *(_QWORD *)(v52 + 160) = v45;
    *(_QWORD *)(v52 + 128) = v49;
    v353 = v40;
    *(_BYTE *)(v52 + 304) = v40;
    LODWORD(v16) = *(unsigned __int16 *)(v52 + 300);
    v57 = *(unsigned __int8 *)(a7 + 521);
    v30 = v376;
    v58 = v378;
    v59 = v379;
    glyph_hor_metrics = truetype::sfnt::sfac::read_glyph_hor_metrics(v376, v378, v379, *(unsigned __int16 *)(v52 + 300));
    v61 = glyph_hor_metrics >> 16;
    if ( (glyph_hor_metrics & 1) != 0 )
      goto LABEL_221;
    glyph_vert_metrics = truetype::sfnt::sfac::read_glyph_vert_metrics(v30, v58, v59, (unsigned int)v16);
    v63 = (glyph_vert_metrics & 0xFFFFFFFF0000uLL) >> 16;
    if ( (glyph_vert_metrics & 1) != 0 )
    {
      LOWORD(v61) = ((unsigned int)glyph_vert_metrics & 0xFFFF0000) >> 16;
      goto LABEL_221;
    }
    if ( v57 )
    {
      v16 = v375;
      v64 = v387;
      v65 = v388;
      if ( v57 == 1 )
        v66 = (unsigned int)-(v360 + ((__int16)(v346 - v360 - v61 + ((unsigned __int16)(v346 - v360 - v61) >> 15)) >> 1));
      else
        v66 = 0;
    }
    else
    {
      v66 = (unsigned __int16)v61 >> 1;
      v16 = v375;
      v64 = v387;
      v65 = v388;
    }
    v67 = glyph_vert_metrics & 0xFFFFFFFF00000000uLL;
    *(_WORD *)(v52 + 200) = 1;
    *(_WORD *)(v52 + 202) = v61;
    *(_WORD *)(v52 + 208) = WORD2(v67);
    *(_DWORD *)(v52 + 204) = (unsigned __int16)v63 | v67 | v61 & 0xFFFF0000;
    *(_WORD *)(v52 + 210) = v66;
    if ( !v65 )
    {
      *(_QWORD *)(v52 + 56) = 1;
      LODWORD(v15) = (_DWORD)v379;
      goto LABEL_135;
    }
    v68 = *(_QWORD *)(v16 + 16);
    if ( v64 >= v68 )
    {
      v66 = *(_QWORD *)(v16 + 16);
LABEL_407:
      core::panicking::panic_bounds_check(v64, v66, &off_180344A70);
    }
    v342 = 312 * v68;
    v69 = 2;
    v70 = -16;
    v71 = 312;
    v359 = v68;
    while ( 1 )
    {
      v72 = *(_QWORD *)(v16 + 8);
      v73 = v380;
      *(_QWORD *)(v72 + v380 + 112) = v68;
      v74 = *(_QWORD *)(v72 + v73 + 96);
      v75 = *(_QWORD *)(v72 + v73 + 104);
      LOWORD(v61) = 5133;
      if ( v74 < v75 )
        goto LABEL_221;
      if ( v74 - v75 < 2 )
        goto LABEL_221;
      v76 = v380 + v72;
      v77 = *(_QWORD *)(v76 + 88);
      v78 = *(unsigned __int16 *)(v77 + v75);
      *(_QWORD *)(v76 + 104) = v75 + 2;
      if ( v74 - (v75 + 2) < 2 )
        goto LABEL_221;
      LOWORD(v78) = __ROL2__(v78, 8);
      v79 = v75 + 4;
      LODWORD(v16) = *(unsigned __int16 *)(v77 + v75 + 2);
      *(_QWORD *)(v76 + 104) = v75 + 4;
      if ( (v78 & 2) != 0 )
      {
        if ( (v78 & 1) != 0 )
        {
          if ( v74 - v79 < 2 )
            goto LABEL_221;
          v80 = *(unsigned __int16 *)(v77 + v75 + 4);
          *(_QWORD *)(v76 + 104) = v75 + 6;
          if ( v74 - (v75 + 6) < 2 )
            goto LABEL_221;
          LOWORD(v80) = __ROL2__(v80, 8);
          v82 = *(unsigned __int16 *)(v77 + v75 + 6);
          v81 = v75 + 8;
          LOWORD(v82) = __ROL2__(v82, 8);
          v390 = v82;
        }
        else
        {
          if ( v74 <= v79 )
            goto LABEL_221;
          v80 = *(char *)(v77 + v75 + 4);
          *(_QWORD *)(v76 + 104) = v75 + 5;
          if ( v74 <= v75 + 5 )
            goto LABEL_221;
          v82 = *(char *)(v77 + v75 + 5);
          v390 = v82;
          v81 = v75 + 6;
        }
        *(_QWORD *)(v76 + 104) = v81;
        LOWORD(v82) = 1;
        LODWORD(v365) = v82;
      }
      else
      {
        if ( (v78 & 1) != 0 )
        {
          if ( v74 - v79 <= 1 )
            goto LABEL_221;
          v80 = *(unsigned __int16 *)(v77 + v75 + 4);
          *(_QWORD *)(v76 + 104) = v75 + 6;
          if ( v74 - (v75 + 6) < 2 )
            goto LABEL_221;
          LOWORD(v80) = __ROL2__(v80, 8);
          v83 = *(unsigned __int16 *)(v77 + v75 + 6);
          v81 = v75 + 8;
          LOWORD(v83) = __ROL2__(v83, 8);
          v390 = v83;
        }
        else
        {
          if ( v74 <= v79 )
            goto LABEL_221;
          v80 = *(unsigned __int8 *)(v77 + v75 + 4);
          *(_QWORD *)(v76 + 104) = v75 + 5;
          if ( v74 <= v75 + 5 )
            goto LABEL_221;
          v390 = *(unsigned __int8 *)(v77 + v75 + 5);
          v81 = v75 + 6;
        }
        *(_QWORD *)(v76 + 104) = v81;
        LODWORD(v365) = 0;
      }
      LODWORD(v389) = 0;
      if ( (v78 & 0xC8) == 0 )
      {
        v88 = 0x10000;
        LODWORD(lpMem) = 0;
        v87 = 0x10000;
        goto LABEL_69;
      }
      v84 = v74 < v81 || v74 - v81 < 2;
      if ( (v78 & 0x80u) == 0 )
      {
        if ( v84 )
          goto LABEL_221;
        v85 = v81 + 2;
        v86 = __ROL2__(*(_WORD *)(v77 + v81), 8);
        *(_QWORD *)(v76 + 104) = v81 + 2;
        v87 = 4 * v86;
        if ( (v78 & 0x40) == 0 )
        {
          LODWORD(lpMem) = 0;
          v88 = v87;
          goto LABEL_69;
        }
        if ( v74 - v85 < 2 )
          goto LABEL_221;
        LODWORD(v389) = 0;
        v93 = 4;
        LODWORD(lpMem) = 0;
        goto LABEL_68;
      }
      if ( v84 )
        goto LABEL_221;
      v89 = *(_WORD *)(v77 + v81);
      *(_QWORD *)(v76 + 104) = v81 + 2;
      if ( v74 - (v81 + 2) < 2 )
        goto LABEL_221;
      v90 = v80;
      v91 = *(_WORD *)(v77 + v81 + 2);
      *(_QWORD *)(v76 + 104) = v81 + 4;
      if ( v74 - (v81 + 4) < 2
        || (v85 = v81 + 6, v92 = *(_WORD *)(v77 + v81 + 4), *(_QWORD *)(v76 + 104) = v81 + 6, v74 - (v81 + 6) < 2) )
      {
        LOWORD(v61) = 5133;
LABEL_221:
        v22 = 2;
        return ((unsigned __int64)v22 << 32) | (unsigned int)((_DWORD)v16 << 16) | (unsigned __int16)v61;
      }
      v87 = 4 * (__int16)__ROL2__(v89, 8);
      LODWORD(lpMem) = 4 * (__int16)__ROL2__(v91, 8);
      LODWORD(v389) = 4 * (__int16)__ROL2__(v92, 8);
      v93 = 8;
      v64 = v387;
      v80 = v90;
LABEL_68:
      v94 = __ROL2__(*(_WORD *)(v77 + v85), 8);
      *(_QWORD *)(v76 + 104) = v93 + v81;
      v88 = 4 * v94;
LABEL_69:
      LOWORD(v16) = __ROL2__(v16, 8);
      LOBYTE(v385) = (v78 & 0xC8) != 0;
      LOBYTE(v347) = (v78 & 0x1800) == 2048;
      LOBYTE(v357) = (v78 & 0x20) == 0;
      if ( (unsigned __int16)v16 >= (unsigned __int16)v350 )
      {
        LOWORD(v61) = 5136;
        goto LABEL_221;
      }
      v95 = (unsigned __int8)v78 >> 2;
      v383 = v78 >> 9;
      v96 = v78 >> 8;
      LOBYTE(v96) = BYTE1(v78) & 1;
      v364 = HIWORD(v87);
      LODWORD(v381) = v96;
      *(_BYTE *)(v76 + 307) |= BYTE1(v78) & 1;
      v373 = v69;
      v349 = v71;
      v354 = v70;
      LOWORD(v361) = v16;
      v362 = v80;
      v363 = v88;
      if ( (v78 & 0xC8) != 0 )
      {
        LOBYTE(v351) = (unsigned __int8)v78 >> 2;
        v97 = *(int *)(v76 + 264);
        v98 = v87;
        v99 = (((v87 * v97) >> 63) + v87 * v97 + 0x8000) >> 16;
        if ( v99 < -2147483647 )
          v99 = 0xFFFFFFFF80000000uLL;
        if ( v99 >= 0x7FFFFFFF )
          v99 = 0x7FFFFFFF;
        v366 = v99;
        v100 = *(int *)(v76 + 276);
        v101 = ((((int)lpMem * v100) >> 63) + (int)lpMem * v100 + 0x8000) >> 16;
        if ( v101 < -2147483647 )
          v101 = 0xFFFFFFFF80000000uLL;
        if ( v101 >= 0x7FFFFFFF )
          v101 = 0x7FFFFFFF;
        v388 = v101;
        v102 = *(int *)(v76 + 268);
        v103 = (((v87 * v102) >> 63) + v87 * v102 + 0x8000) >> 16;
        if ( v103 < -2147483647 )
          v103 = 0xFFFFFFFF80000000uLL;
        LODWORD(v355) = v87;
        if ( v103 >= 0x7FFFFFFF )
          LODWORD(v103) = 0x7FFFFFFF;
        v104 = *(int *)(v76 + 280);
        v105 = ((((int)lpMem * v104) >> 63) + (int)lpMem * v104 + 0x8000) >> 16;
        if ( v105 < -2147483647 )
          v105 = 0xFFFFFFFF80000000uLL;
        if ( v105 >= 0x7FFFFFFF )
          v105 = 0x7FFFFFFF;
        v384 = v105;
        v386 = *(int *)(v76 + 272);
        v106 = (v386 * v98 + ((v386 * v98) >> 63) + 0x8000) >> 16;
        if ( v106 < -2147483647 )
          v106 = 0xFFFFFFFF80000000uLL;
        if ( v106 >= 0x7FFFFFFF )
          LODWORD(v106) = 0x7FFFFFFF;
        v374 = *(int *)(v76 + 284);
        v107 = (v374 * (int)lpMem + ((v374 * (int)lpMem) >> 63) + 0x8000) >> 16;
        if ( v107 < -2147483647 )
          v107 = 0xFFFFFFFF80000000uLL;
        v108 = v383;
        if ( v107 >= 0x7FFFFFFF )
          v107 = 0x7FFFFFFF;
        v377 = v107;
        v109 = ((((int)v389 * v97) >> 63) + (int)v389 * v97 + 0x8000) >> 16;
        if ( v109 < -2147483647 )
          v109 = 0xFFFFFFFF80000000uLL;
        if ( v109 >= 0x7FFFFFFF )
          LODWORD(v109) = 0x7FFFFFFF;
        v110 = (v88 * v100 + 4LL * (v88 * v100 >= 0) + 32764) >> 16;
        if ( v110 < -2147483647 )
          v110 = 0xFFFFFFFF80000000uLL;
        if ( v110 >= 0x7FFFFFFF )
          LODWORD(v110) = 0x7FFFFFFF;
        v111 = ((int)v389 * v102 + (((int)v389 * v102) >> 63) + 0x8000) >> 16;
        if ( v111 < -2147483647 )
          v111 = 0xFFFFFFFF80000000uLL;
        if ( v111 >= 0x7FFFFFFF )
          LODWORD(v111) = 0x7FFFFFFF;
        v112 = (v88 * v104 + 4LL * (v88 * v104 >= 0) + 32764) >> 16;
        if ( v112 < -2147483647 )
          v112 = 0xFFFFFFFF80000000uLL;
        if ( v112 >= 0x7FFFFFFF )
          LODWORD(v112) = 0x7FFFFFFF;
        v113 = (((v386 * (int)v389) >> 63) + v386 * (int)v389 + 0x8000) >> 16;
        if ( v113 < -2147483647 )
          v113 = 0xFFFFFFFF80000000uLL;
        if ( v113 >= 0x7FFFFFFF )
          LODWORD(v113) = 0x7FFFFFFF;
        v114 = (v374 * v88 + 4LL * (v374 * v88 >= 0) + 32764) >> 16;
        if ( v114 < -2147483647 )
          v114 = 0xFFFFFFFF80000000uLL;
        LOWORD(v87) = v355;
        if ( v114 >= 0x7FFFFFFF )
          LODWORD(v114) = 0x7FFFFFFF;
        v115 = v111 + v112;
        v116 = v109 + v110;
        v377 = (unsigned int)(v106 + v377);
        v117 = (unsigned int)(v103 + v384);
        v118 = (unsigned int)(v366 + v388);
        v119 = (unsigned int)(v113 + v114);
        v120 = *(_DWORD *)(v76 + 288);
        v121 = *(_DWORD *)(v76 + 292);
        LODWORD(v374) = *(_DWORD *)(v76 + 296);
        v122 = *(_BYTE *)(v76 + 306) == 0;
        LODWORD(v366) = v120;
        LODWORD(v386) = v121;
        if ( v122 )
        {
          LODWORD(v358) = 0;
          v64 = v387;
          v95 = v351;
        }
        else
        {
          v64 = v387;
          v95 = v351;
          if ( (unsigned int)v389 | (unsigned int)lpMem )
          {
            LODWORD(v358) = 0;
          }
          else
          {
            v123 = -(int)v355;
            if ( (int)v355 > 0 )
              v123 = v355;
            v124 = -v88;
            if ( v88 > 0 )
              v124 = v88;
            v125 = v123 ^ 0x10000;
            LOBYTE(v125) = (v125 | v124 ^ 0x10000) == 0;
            LODWORD(v358) = v125;
          }
        }
      }
      else
      {
        v118 = *(unsigned int *)(v76 + 264);
        v117 = *(unsigned int *)(v76 + 268);
        v377 = *(unsigned int *)(v76 + 272);
        v116 = *(_DWORD *)(v76 + 276);
        v115 = *(_DWORD *)(v76 + 280);
        v119 = *(unsigned int *)(v76 + 284);
        LODWORD(v366) = *(_DWORD *)(v76 + 288);
        LODWORD(v386) = *(_DWORD *)(v76 + 292);
        LODWORD(v374) = *(_DWORD *)(v76 + 296);
        LODWORD(v358) = *(unsigned __int8 *)(v76 + 306);
        v108 = v383;
      }
      v384 = v117;
      v388 = v118;
      v126 = v95 & 1;
      v127 = v108 & 1;
      v16 = v375;
      v128 = *(_QWORD *)(v375 + 16);
      if ( v128 == *(_QWORD *)v375 )
      {
        v383 = v78;
        v129 = v127;
        v130 = v87;
        v355 = v119;
        v131 = v115;
        v132 = v116;
        v133 = v126;
        alloc::raw_vec::RawVec_truetype::gridfit::GlyphData_alloc::alloc::Global_::grow_one_truetype::gridfit::GlyphData_alloc::alloc::Global_(
          v375,
          &off_180344A88);
        v126 = v133;
        v116 = v132;
        v115 = v131;
        LODWORD(v119) = v355;
        LOWORD(v87) = v130;
        v127 = v129;
        LOBYTE(v78) = v383;
        v64 = v387;
      }
      v134 = 312 * v128;
      v135 = *(_QWORD *)(v16 + 8);
      *(_QWORD *)(v135 + v134) = 0;
      *(_QWORD *)(v135 + v134 + 24) = 0;
      *(_QWORD *)(v135 + v134 + 40) = 0;
      *(_QWORD *)(v135 + v134 + 56) = 0;
      *(_QWORD *)(v135 + v134 + 80) = 0;
      *(_QWORD *)(v135 + v134 + 88) = 1;
      *(_OWORD *)(v135 + v134 + 96) = 0;
      *(_QWORD *)(v135 + v134 + 112) = 0;
      *(_QWORD *)(v135 + v134 + 120) = v64;
      *(_QWORD *)(v135 + v134 + 128) = 0x800080007FFF7FFFuLL;
      *(_OWORD *)(v135 + v134 + 136) = 0;
      *(_OWORD *)(v135 + v134 + 152) = 0;
      *(_OWORD *)(v135 + v134 + 168) = 0;
      *(_OWORD *)(v135 + v134 + 184) = 0;
      *(_WORD *)(v135 + v134 + 200) = 0;
      *(_WORD *)(v135 + v134 + 212) = v87;
      *(_WORD *)(v135 + v134 + 214) = v364;
      *(_DWORD *)(v135 + v134 + 216) = (_DWORD)lpMem;
      *(_DWORD *)(v135 + v134 + 220) = 0;
      *(_DWORD *)(v135 + v134 + 224) = v389;
      *(_DWORD *)(v135 + v134 + 228) = v363;
      *(_OWORD *)(v135 + v134 + 232) = _xmm;
      v136 = v361;
      *(_WORD *)(v135 + v134 + 248) = v361;
      *(_WORD *)(v135 + v134 + 250) = v365;
      *(_WORD *)(v135 + v134 + 252) = v362;
      *(_WORD *)(v135 + v134 + 254) = v390;
      *(_BYTE *)(v135 + v134 + 256) = v126;
      *(_BYTE *)(v135 + v134 + 257) = v127;
      *(_BYTE *)(v135 + v134 + 258) = v347;
      *(_BYTE *)(v135 + v134 + 259) = v381;
      *(_BYTE *)(v135 + v134 + 260) = v385;
      *(_BYTE *)(v135 + v134 + 261) = v357;
      *(_DWORD *)(v135 + v134 + 264) = v388;
      *(_DWORD *)(v135 + v134 + 268) = v384;
      *(_DWORD *)(v135 + v134 + 272) = v377;
      *(_DWORD *)(v135 + v134 + 276) = v116;
      *(_DWORD *)(v135 + v134 + 280) = v115;
      *(_DWORD *)(v135 + v134 + 284) = v119;
      *(_DWORD *)(v135 + v134 + 288) = v366;
      *(_DWORD *)(v135 + v134 + 292) = v386;
      *(_DWORD *)(v135 + v134 + 296) = v374;
      *(_WORD *)(v135 + v134 + 300) = v136;
      *(_DWORD *)(v135 + v134 + 302) = 0xFFFF;
      *(_BYTE *)(v135 + v134 + 306) = v358;
      *(_BYTE *)(v135 + v134 + 307) = 0;
      v66 = v128 + 1;
      *(_QWORD *)(v16 + 16) = v128 + 1;
      if ( (v78 & 0x20) == 0 )
        break;
      v69 = v373 + 1;
      v70 = v354 - 4;
      v71 = v349 + 312;
      v68 = v359;
      if ( v64 > v128 )
        goto LABEL_407;
    }
    LODWORD(v30) = v376;
    v137 = v373;
    v138 = v359;
    if ( v64 > v128 )
      core::panicking::panic_bounds_check(v64, v66, &off_180344AA0);
    v139 = *(_QWORD *)(v16 + 8) + v380;
    *(_QWORD *)(v139 + 56) = 2;
    *(_QWORD *)(v139 + 64) = v138;
    *(_QWORD *)(v139 + 72) = v137 - 1;
    LOWORD(v61) = 5133;
    if ( !*(_BYTE *)(v139 + 307) )
      goto LABEL_147;
    v140 = *(_QWORD *)(v139 + 96);
    v141 = *(_QWORD *)(v139 + 104);
    if ( v140 < v141 || v140 - v141 < 2 )
      goto LABEL_221;
    v142 = *(unsigned __int16 *)(*(_QWORD *)(v139 + 88) + v141);
    v143 = v141 + 2;
    *(_QWORD *)(v139 + 104) = v143;
    if ( (_WORD)v142 )
    {
      v144 = __ROL2__(v142, 8);
      if ( v140 - v143 < v144 )
        goto LABEL_221;
      v142 = v143 + v144;
      *(_QWORD *)(v139 + 104) = v142;
      v140 = v143 >> 16;
      v145 = 1;
    }
    else
    {
      v145 = 0;
    }
    *(_QWORD *)v139 = v145;
    *(_WORD *)(v139 + 8) = v143;
    *(_DWORD *)(v139 + 10) = v140;
    v66 = HIDWORD(v140);
    *(_WORD *)(v139 + 14) = v66;
    *(_QWORD *)(v139 + 16) = v142;
LABEL_147:
    LODWORD(v15) = (_DWORD)v379;
    v31 = v378;
    if ( !v348 || !v344 )
      goto LABEL_136;
    v380 = v137 - 1;
    variation::gvar::get_glyphs_byte_range(
      (unsigned int)&v369,
      v30,
      v378,
      (_DWORD)v345,
      *(unsigned __int16 *)(v139 + 300),
      *(unsigned __int16 *)(v139 + 300) + 1);
    if ( (v369 & 1) != 0 )
    {
      LOWORD(v61) = WORD1(v369);
      goto LABEL_221;
    }
    v146 = HIDWORD(v369);
    v147 = *(_DWORD *)v370;
    v31 = v378;
    v64 = v387;
    if ( HIDWORD(v369) >= *(_DWORD *)v370 )
      goto LABEL_136;
    *(_QWORD *)(v16 + 40) = 0;
    *(_QWORD *)(v16 + 64) = 0;
    if ( v137 == -3 )
    {
      v148 = 0;
      v149 = 0;
    }
    else
    {
      v149 = v137 + 3;
      if ( v149 > *(_QWORD *)(v16 + 24) )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2(v16 + 24, 0, v149, 4, 4);
        v150 = *(_QWORD *)(v16 + 40);
      }
      else
      {
        v150 = 0;
      }
      v151 = *(_QWORD *)(v16 + 32);
      v152 = (_DWORD *)(v151 + 4 * v150);
      v153 = v373;
      if ( v373 != -2 )
      {
        memset_0(v152, 0, -v354);
        v152 = (_DWORD *)(v151 + 4 * (v150 + v153) + 8);
        v150 += v153 + 2;
      }
      *v152 = 0;
      v148 = v150 + 1;
      v16 = v375;
      v154 = *(_QWORD *)(v375 + 64);
      *(_QWORD *)(v375 + 40) = v148;
      if ( v149 > v154 )
      {
        v155 = v373 - v154 + 3;
        v156 = v154;
        if ( v155 > *(_QWORD *)(v16 + 48) - v154 )
        {
          v179 = v373 - v154 + 3;
          alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2(v16 + 48, v154, v155, 4, 4);
          v155 = v179;
          v156 = *(_QWORD *)(v16 + 64);
        }
        v157 = *(_QWORD *)(v16 + 56);
        v158 = (_DWORD *)(v157 + 4 * v156);
        if ( v155 >= 2 )
        {
          memset_0(v158, 0, -(__int64)(v354 + 4 * v154));
          v158 = (_DWORD *)(v157 + 4 * (v156 - v154 + v373) + 8);
          v156 = v156 - v154 + v373 + 2;
        }
        *v158 = 0;
        v149 = v156 + 1;
        v148 = *(_QWORD *)(v16 + 40);
      }
    }
    *(_QWORD *)(v16 + 64) = v149;
    LOWORD(v61) = variation::gvar::GlyphOutlineVariationInterpolator::apply_variation(
                    a15,
                    v376,
                    v378,
                    (_DWORD)v345,
                    v146,
                    v147,
                    v341,
                    v344,
                    2,
                    0,
                    *(_QWORD *)(v16 + 32),
                    v148,
                    *(_QWORD *)(v16 + 56),
                    v149);
    if ( (unsigned __int16)v61 != 5119 )
      goto LABEL_221;
    v159 = *(_QWORD *)(v16 + 40);
    v160 = v380;
    if ( v380 >= v159 )
      goto LABEL_412;
    v161 = *(_QWORD *)(v16 + 64);
    LODWORD(v15) = (_DWORD)v379;
    v162 = v349;
    v163 = v373;
    v164 = v359;
    if ( v380 >= v161 )
      goto LABEL_413;
    if ( v373 >= v159 )
      core::panicking::panic_bounds_check(v373, v159, &off_180344B30);
    if ( v373 >= v161 )
      core::panicking::panic_bounds_check(v373, *(_QWORD *)(v16 + 64), &off_180344B48);
    v160 = v373 + 1;
    if ( v373 + 1 >= v159 )
      goto LABEL_412;
    if ( v160 >= v161 )
      goto LABEL_413;
    v160 = v373 + 2;
    if ( v373 + 2 >= v159 )
LABEL_412:
      core::panicking::panic_bounds_check(v160, v159, &off_180344B30);
    if ( v160 >= v161 )
LABEL_413:
      core::panicking::panic_bounds_check(v160, *(_QWORD *)(v16 + 64), &off_180344B48);
    v165 = *(_QWORD *)(v16 + 32);
    v166 = *(_QWORD *)(v16 + 56);
    v167 = *(_DWORD *)(v165 + 4 * v373 - 4);
    v168 = *(_DWORD *)(v166 + 4 * v373 - 4);
    v169 = *(_DWORD *)(v165 + 4 * v373);
    v170 = *(_DWORD *)(v166 + 4 * v373);
    v171 = *(_DWORD *)(v165 + 4 * v373 + 4);
    v172 = *(_DWORD *)(v166 + 4 * v373 + 4);
    LODWORD(v165) = *(_DWORD *)(v165 + 4 * v373 + 8);
    LODWORD(v166) = *(_DWORD *)(v166 + 4 * v373 + 8);
    *(_DWORD *)(v139 + 168) = v167;
    *(_DWORD *)(v139 + 172) = v168;
    *(_DWORD *)(v139 + 176) = v169;
    *(_DWORD *)(v139 + 180) = v170;
    *(_DWORD *)(v139 + 184) = v171;
    *(_DWORD *)(v139 + 188) = v172;
    *(_DWORD *)(v139 + 192) = v165;
    *(_DWORD *)(v139 + 196) = v166;
    v173 = *(_QWORD *)(v16 + 16);
    v174 = v173 < v164;
    v66 = v173 - v164;
    if ( v174 )
      core::slice::index::slice_start_index_len_fail(v164, *(_QWORD *)(v16 + 16), &off_180344B18);
    v64 = v387;
    if ( v380 > v66 )
      core::slice::index::slice_end_index_len_fail(v380, v66, &off_180344AB8);
    LODWORD(v30) = v376;
    if ( v163 != 1 )
    {
      v175 = (_WORD *)(v342 + *(_QWORD *)(v16 + 8) + 254);
      v176 = 0;
      do
      {
        v66 = (unsigned __int16)*(v175 - 2);
        if ( (_WORD)v66 == 2 )
          core::option::unwrap_failed(&off_180344AD0);
        if ( (v66 & 1) != 0 )
        {
          v177 = *(_QWORD *)(v16 + 40);
          if ( v176 >= v177 )
            core::panicking::panic_bounds_check(v176, v177, &off_180344AE8);
          *(v175 - 1) += *(_WORD *)(*(_QWORD *)(v16 + 32) + 4 * v176);
          v178 = *(_QWORD *)(v16 + 64);
          if ( v176 >= v178 )
            core::panicking::panic_bounds_check(v176, v178, &off_180344B00);
          v66 = *(unsigned __int16 *)(*(_QWORD *)(v16 + 56) + 4 * v176);
          *v175 += v66;
        }
        v175 += 156;
        ++v176;
        v162 -= 312;
      }
      while ( v162 );
    }
    *(_QWORD *)(v16 + 40) = 0;
    *(_QWORD *)(v16 + 64) = 0;
LABEL_135:
    v31 = v378;
LABEL_136:
    v32 = v64 + 1;
    v33 = v352;
    LOBYTE(v33) = v353 | v352;
  }
  while ( v32 < *(_QWORD *)(v16 + 16) );
  v180 = truetype::gridfit::GridFitState::traverse_glyph_tree(v339, v66, v31);
  LOWORD(v61) = v180;
  if ( v180 != 4100 )
    goto LABEL_221;
  v181 = *(_QWORD *)(v16 + 16);
  if ( !v181 )
    core::panicking::panic_bounds_check(0, 0, &off_180344A40);
  v182 = *(_QWORD *)(v16 + 8);
  if ( (*(_BYTE *)(v182 + 200) & 1) == 0 )
    core::option::unwrap_failed(&off_180344A58);
  LOBYTE(v33) = v33 & 1;
  v368 = *(unsigned __int16 *)(v182 + 202);
  v61 = *(unsigned __int16 *)(v182 + 302);
  *(_QWORD *)(v16 + 16) = 0;
  v183 = (void **)(v182 + 88);
  do
  {
    if ( *(v183 - 1) )
    {
      v184 = *v183;
      v185 = GetProcessHeap();
      HeapFree(v185, 0, v184);
    }
    v183 += 39;
    --v181;
  }
  while ( v181 );
  v122 = v367[3].m128i_i8[1] == 0;
  v352 = v33;
  if ( v122 )
  {
    v201 = v356;
    v202 = a12;
    v16 = v368;
    goto LABEL_353;
  }
  v187 = *(_WORD *)(a7 + 506);
  v188 = v187 == 1;
  if ( a12 )
    v188 = (__int16)v187 <= 1;
  v363 = v188;
  v189 = v356[2];
  v190 = v189 - 8;
  if ( *((_BYTE *)v356 + 264) )
    v190 = v356[2];
  if ( v190 + 1 >= v189 )
    core::panicking::panic_bounds_check(v190 + 1, v189, &off_180344360);
  if ( v190 >= v189 )
    core::panicking::panic_bounds_check(v190, v189, &off_180344378);
  v191 = v356[1];
  v192 = v356[4];
  v193 = v356[5];
  v355 = v356[22];
  v350 = v356[23];
  v351 = v356[25];
  v359 = v356[26];
  v348 = v356[31];
  v353 = v356[32];
  v194 = *(_DWORD *)(v191 + 4 * v190 + 4);
  if ( v194 != *(_DWORD *)(v191 + 4 * v190) )
    *(_DWORD *)(v191 + 4 * v190 + 4) = v194 + 64;
  v195 = v190 + 3;
  if ( v190 + 3 >= v193 )
  {
    v337 = &off_180344390;
    goto LABEL_415;
  }
  v195 = v190 + 2;
  if ( v190 + 2 >= v193 )
  {
    v337 = &off_1803443A8;
LABEL_415:
    core::panicking::panic_bounds_check(v195, v193, v337);
  }
  v380 = v189;
  v360 = v61;
  v196 = *(_DWORD *)(v192 + 4 * v190 + 12);
  if ( v196 != *(_DWORD *)(v192 + 4 * v190 + 8) )
    *(_DWORD *)(v192 + 4 * v190 + 12) = v196 - 64;
  if ( !a11 )
  {
    if ( a10 )
    {
      if ( a12 )
      {
        v197 = (__int16)(v187 - ((unsigned int)(__int16)v187 >> 1));
        v198 = (__int16)v187 >> 1;
      }
      else
      {
        v198 = v187 >> 1;
        v197 = (unsigned __int16)(v187 - v198);
      }
      v357 = (unsigned int)(v197 << 6);
      v390 = v198 << 6;
      v203 = *(unsigned __int16 *)(a7 + 504) >> 1;
      v385 = (unsigned __int16)(*(_WORD *)(a7 + 504) - v203) << 6;
      LODWORD(v374) = v203 << 6;
    }
    else
    {
      v385 = 32 * *(unsigned __int16 *)(a7 + 504);
      LODWORD(v374) = v385;
      v390 = 32 * v187;
      v357 = v390;
    }
    if ( v350 )
    {
      v364 = *(_DWORD *)(a7 + 488);
      LOBYTE(v383) = *(_BYTE *)(a7 + 517);
      v366 = v385;
      v358 = (unsigned int)v374;
      LODWORD(v349) = -v390;
      LODWORD(v354) = -v385;
      v204 = 1;
      v205 = 0;
      v381 = v193;
      while ( 1 )
      {
        v378 = v204;
        if ( v205 >= v359 )
          core::panicking::panic_bounds_check(v205, v359, &off_1803443C0);
        v206 = *(_WORD *)(v355 + 2 * v205);
        v207 = v206;
        v208 = *(_WORD *)(v351 + 2 * v205);
        v209 = v208;
        if ( v208 - (unsigned __int64)v206 > 1 )
        {
          if ( v205 >= v353 )
            core::panicking::panic_bounds_check(v205, v353, &off_1803443D8);
          if ( v380 <= v206 )
            core::panicking::panic_bounds_check(v206, v380, &off_1803443F0);
          if ( v193 <= v206 )
            core::panicking::panic_bounds_check(v206, v193, &off_180344408);
          if ( v380 <= v208 )
            core::panicking::panic_bounds_check(v208, v380, &off_180344420);
          if ( v193 <= v208 )
            core::panicking::panic_bounds_check(v208, v193, &off_180344438);
          v195 = v206 + 1LL;
          if ( v195 >= v380 )
            core::panicking::panic_bounds_check(v206 + 1LL, v380, &off_180344450);
          if ( v195 >= v193 )
          {
            v337 = &off_180344468;
            goto LABEL_415;
          }
          if ( v206 <= v208 )
            break;
        }
LABEL_230:
        v205 = v378;
        v204 = v378 + 1;
        if ( v378 == v350 )
          goto LABEL_349;
      }
      LOBYTE(v373) = *(_BYTE *)(v348 + v205);
      v210 = *(_DWORD *)(v191 + 4LL * v206);
      v211 = *(_DWORD *)(v192 + 4LL * v206);
      LODWORD(v387) = *(_DWORD *)(v191 + 4 * v209);
      LODWORD(v388) = *(_DWORD *)(v192 + 4 * v209);
      v212 = 4 * (unsigned int)v206;
      v213 = *(unsigned int *)(v191 + v212 + 4);
      v214 = *(unsigned int *)(v192 + v212 + 4);
      v215 = v210;
      v216 = v211;
      v347 = v209;
      v362 = v210;
      v361 = v211;
      while ( 2 )
      {
        v217 = v207;
        while ( (_DWORD)v213 == (_DWORD)v215 )
        {
          if ( v217 >= v209 || (_DWORD)v214 != v216 )
          {
            v213 = (unsigned int)v215;
            break;
          }
          ++v217;
          v214 = v211;
          v213 = v210;
          if ( v217 < v209 )
          {
            v213 = *(unsigned int *)(v191 + 4 * v217 + 4);
            v214 = *(unsigned int *)(v192 + 4 * v217 + 4);
          }
        }
        v218 = (unsigned int)(v215 - v387);
        v219 = v216 - (unsigned int)v388;
        v220 = v213;
        v221 = v216;
        v377 = v220;
        v222 = v220 - v215;
        LODWORD(v384) = v221;
        v223 = v214 - v221;
        if ( (v373 & 1) != 0 )
        {
          v218 = (unsigned int)(v387 - v215);
          v222 = -v222;
        }
        else
        {
          v219 = (unsigned int)-(int)v219;
          v223 = v221 - v214;
        }
        lpMem = (LPVOID)v214;
        v365 = v215;
        if ( (_BYTE)v363 )
        {
          v224 = v215;
          v225 = (unsigned int)(v357 + v215);
          v226 = v224;
          if ( (int)v219 > 0 )
            v226 = (unsigned int)v225;
          v389 = v226;
          if ( v223 <= 0 )
            v225 = v224;
          v227 = (unsigned int)v384;
          v228 = v384;
          v229 = v377;
          v230 = (int)lpMem;
        }
        else
        {
          v232 = (unsigned int)(__int16)truetype::interp::normalize(v219, v218) >> 8;
          v389 = (unsigned int)v231 >> 8;
          v386 = (__int16)v389;
          v234 = (unsigned int)(__int16)truetype::interp::normalize((unsigned int)v223, v222) >> 8;
          v235 = (unsigned int)v233 >> 8;
          v236 = v390;
          if ( (__int16)v232 > 0 )
            v236 = v357;
          v237 = (unsigned __int64)((__int16)v232 * (__int64)v236 + 32) >> 6;
          v238 = v366 * v386;
          v239 = v358 * (unsigned int)v386;
          v386 = (__int16)v234;
          if ( (v389 & 0x8000u) != 0LL )
            v239 = v238;
          v240 = (unsigned __int64)(v239 + 32) >> 6;
          LODWORD(v387) = v237 + v387;
          LODWORD(v388) = v240 + v388;
          v389 = (unsigned int)(v365 + v237);
          v227 = (unsigned int)(v384 + v240);
          v241 = (__int16)v234 <= 0;
          v242 = v390;
          if ( !v241 )
            v242 = v357;
          v243 = (unsigned __int64)(v386 * v242 + 32) >> 6;
          v244 = v358 * (unsigned int)(__int16)v235;
          if ( (v235 & 0x8000u) != 0 )
            v244 = v366 * (__int16)v235;
          v245 = (unsigned __int64)(v244 + 32) >> 6;
          v229 = v377 + v243;
          v230 = (_DWORD)lpMem + v245;
          v225 = (unsigned int)(v365 + v243);
          v228 = v384 + v245;
        }
        v246 = v225 - v389;
        if ( (_DWORD)v225 == (_DWORD)v389 && v228 == (_DWORD)v227 )
        {
          *(_DWORD *)(v191 + 4 * v207) = v225;
          *(_DWORD *)(v192 + 4 * v207) = v228;
          v193 = v381;
          v247 = v390;
          v248 = v385;
          goto LABEL_337;
        }
        v249 = v229 - v225;
        v250 = v230 - v228;
        v251 = v227 - v388;
        if ( (_DWORD)v227 == (_DWORD)v388 )
        {
          if ( v229 == (_DWORD)v225 )
          {
            v252 = v227;
            v389 = v225;
            v193 = v381;
            v247 = v390;
LABEL_328:
            v283 = *(_DWORD *)(v191 + 4 * v207);
            v284 = v389 - v283;
            v285 = *(_DWORD *)(v192 + 4 * v207);
            v286 = v252 - v285;
            v287 = v283 + v357;
            if ( (int)v389 - v283 <= (int)v357 )
              v287 = v389;
            v288 = v283 - v247;
            if ( v284 >= (int)v349 )
              v288 = v287;
            v248 = v385;
            v289 = v285 - v385;
            if ( v286 >= (int)v354 )
              v289 = v252;
            v290 = v385 + v285;
            if ( v286 <= (int)v374 )
              v290 = v289;
            *(_DWORD *)(v191 + 4 * v207) = v288;
            *(_DWORD *)(v192 + 4 * v207) = v290;
LABEL_337:
            v390 = v247;
            *(_DWORD *)(v191 + 4 * v207) += v247;
            v291 = *(_DWORD *)(v192 + 4 * v207);
            v385 = v248;
            v292 = v248 + v291;
            v293 = v364;
            if ( v292 > v364 )
              v293 = v292;
            if ( (v383 & 1) == 0 )
              v293 = v292;
            *(_DWORD *)(v192 + 4 * v207) = v293;
            v209 = v347;
            v211 = v361;
            v294 = v365;
            v295 = v384;
            v296 = v377;
            if ( v207 < v217 )
            {
              v297 = v207 + 1;
              v298 = v207 + 1;
              do
              {
                v298 += v297 < v217;
                if ( v297 >= v380 )
                  core::panicking::panic_bounds_check(v297, v380, &off_180344480);
                *(_DWORD *)(v191 + 4 * v297) = *(_DWORD *)(v191 + 4 * v207);
                if ( v297 >= v193 )
                  core::panicking::panic_bounds_check(v297, v193, &off_180344498);
                *(_DWORD *)(v192 + 4 * v297) = *(_DWORD *)(v192 + 4 * v207);
                if ( v297 >= v217 )
                  break;
                v297 = v298;
              }
              while ( v298 <= v217 );
            }
            v207 = v217 + 1;
            v214 = v211;
            v210 = v362;
            v299 = v362;
            if ( v217 + 1 < v209 )
            {
              v299 = *(_DWORD *)(v191 + 4 * v217 + 8);
              v214 = *(unsigned int *)(v192 + 4 * v217 + 8);
            }
            LODWORD(v387) = v294;
            LODWORD(v388) = v295;
            v215 = v296;
            v216 = (unsigned int)lpMem;
            v213 = v299;
            if ( v217 >= v209 )
              goto LABEL_230;
            continue;
          }
          v246 = v228 - v227;
          v253 = v230 - v228;
LABEL_288:
          v263 = -v253;
          v193 = v381;
LABEL_307:
          v274 = -v263;
          if ( v263 > 0 )
            v274 = v263;
          if ( v274 <= 16 )
          {
            v389 = (unsigned int)(((int)v225 + (int)v389) >> 1);
            v252 = (v228 + (int)v227) >> 1;
            v247 = v390;
            goto LABEL_328;
          }
          LODWORD(v389) = v250;
          v275 = v246;
          v276 = v246 * (__int64)v249;
          v277 = v263 / 2;
          v278 = v263 / -2;
          if ( v263 < 0 == v276 < 0 )
            v278 = v263 / 2;
          v279 = v276 + v278;
          if ( v263 )
          {
            if ( (v263 | v279) >> 32 )
              v279 = (__int64)v279 / v263;
            else
              LODWORD(v279) = (unsigned int)v279 / v263;
            v280 = (unsigned int)(v279 + v225);
            v281 = (int)v389 * v275;
            if ( v263 < 0 != v281 < 0 )
            {
LABEL_320:
              v282 = v281 - v277;
LABEL_321:
              v389 = v280;
              if ( v263 )
              {
                if ( (v263 | (unsigned __int64)v282) >> 32 )
                  v282 /= v263;
                else
                  LODWORD(v282) = (unsigned int)v282 / v263;
              }
              else
              {
                v282 = (v282 >> 63) ^ 0x7FFFFFFF;
              }
              v228 += v282;
LABEL_327:
              v247 = v390;
              v252 = v228;
              goto LABEL_328;
            }
          }
          else
          {
            v280 = (v279 >> 63) + (unsigned int)v225 + 0x7FFFFFFF;
            v281 = (int)v389 * v275;
            if ( v281 < 0 )
              goto LABEL_320;
          }
          v282 = v277 + v281;
          goto LABEL_321;
        }
        break;
      }
      LODWORD(v386) = v229 - v225;
      if ( (_DWORD)v389 != (_DWORD)v387 )
      {
        v379 = (_WORD *)v227;
        v254 = v389 - v387;
        v255 = v387 - v389;
        if ( (int)v387 - (int)v389 < 0 )
          v255 = v389 - v387;
        v256 = -v251;
        if ( v251 > 0 )
          v256 = v251;
        v375 = v251;
        if ( v255 >= v256 )
        {
          v264 = v251 * (__int64)((int)v225 - (int)v387);
          v265 = v254 / 2;
          v266 = v265;
          if ( v254 < 0 != v264 < 0 )
            v266 = v254 / -2;
          v267 = v264 + v266;
          if ( (v254 | (unsigned __int64)v267) >> 32 )
            v268 = v267 / v254;
          else
            v268 = (unsigned int)v267 / v254;
          v387 = v268;
          v249 = v386;
          LOBYTE(v386) = v254 < 0;
          v272 = v249 * v375;
          if ( v254 < 0 != v272 < 0 )
            v265 = v254 / -2;
          v273 = v272 + v265;
          if ( (v254 | (unsigned __int64)v273) >> 32 )
            v273 /= v254;
          else
            LODWORD(v273) = (unsigned int)v273 / v254;
          v193 = v381;
          LODWORD(v227) = (_DWORD)v379;
          v246 = v228 - (v387 + v388);
          v263 = v273 - v250;
        }
        else
        {
          v257 = v228 - (int)v388;
          v388 = v254;
          v258 = v254 * v257;
          v259 = v251 / 2;
          v260 = v259;
          if ( v251 < 0 != v258 < 0 )
            v260 = v251 / -2;
          v261 = v258 + v260;
          if ( (v375 | (unsigned __int64)v261) >> 32 )
            v262 = v261 / v375;
          else
            v262 = (unsigned int)v261 / v251;
          v376 = v262;
          v269 = v250 * v388;
          if ( v251 < 0 != v269 < 0 )
            v259 = v251 / -2;
          v270 = v269 + v259;
          if ( (v375 | (unsigned __int64)v270) >> 32 )
            v271 = v270 / v375;
          else
            LODWORD(v271) = (unsigned int)v270 / v251;
          v193 = v381;
          LODWORD(v227) = (_DWORD)v379;
          v263 = v386 - v271;
          v246 = v376 + v387 - v225;
          v249 = v386;
        }
        goto LABEL_307;
      }
      if ( v230 != v228 )
      {
        v249 = v386;
        v253 = v386;
        goto LABEL_288;
      }
      v193 = v381;
      goto LABEL_327;
    }
  }
LABEL_349:
  if ( (_WORD)v368 )
    v16 = ((unsigned int)(5243 * ((unsigned __int16)(2 * v367[2].m128i_i32[2] - 1) >> 2)) >> 17) + (unsigned int)v368;
  else
    v16 = 0;
  v201 = v356;
  v202 = a12;
  v61 = v360;
LABEL_353:
  v300 = *(_BYTE *)(a7 + 520);
  v301 = v201[2];
  v302 = v201[5];
  if ( (v367[2].m128i_i8[11] & 0x20) != 0 )
  {
    v305 = 8 * (unsigned int)((v300 & 1) == 0);
    v304 = v305 + 476;
    v303 = v305 + 472;
LABEL_357:
    v306 = *(_DWORD *)(a7 + v303);
    v307 = *(_DWORD *)(a7 + v304);
    LODWORD(v303) = v301 + 8;
    if ( !*((_BYTE *)v201 + 264) )
      v303 = v201[2];
    truetype::trans_matrix::TransMatrix::intel_mul((_DWORD)v367, v303, v201[1], v301, v201[4], v302, v306, v307);
    v300 = *(_BYTE *)(a7 + 520);
    v301 = v201[2];
    v302 = v201[5];
    v202 = a12;
  }
  else if ( (v300 & 1) != 0 )
  {
    v303 = 472;
    v304 = 476;
    goto LABEL_357;
  }
  v308 = *((_BYTE *)v201 + 264);
  v309 = a14;
  v310 = 1;
  if ( !v202 )
    v309 = 1;
  v311 = v301 - 8;
  if ( v308 )
    v311 = v301;
  if ( v311 >= v301 )
    core::panicking::panic_bounds_check(v311, v301, &off_1803478B0);
  if ( v202 )
    v310 = a13;
  if ( v311 >= v302 )
    core::panicking::panic_bounds_check(v311, v302, &off_1803478C8);
  v312 = (_DWORD *)v201[1];
  v313 = (_DWORD *)v201[4];
  v314 = v310 * ((v367->m128i_i32[2] + 512) >> 10) - v312[v311];
  if ( a10 && (v300 & 1) == 0 )
  {
    if ( a12 )
      v314 = (v314 + 2) & 0xFFFFFFFC;
    else
      v314 = (v314 + 32) & 0xFFFFFFC0;
  }
  v315 = v367[1].m128i_i32[1] + 512;
  v316 = v313[v311];
  if ( v314 )
  {
    v317 = v301 + 8;
    if ( !v308 )
      v317 = v301;
    if ( v317 > v301 )
      core::slice::index::slice_end_index_len_fail(v317, v301, &off_1803478E0);
    if ( v317 )
    {
      v318 = (v317 - 1) & 0x3FFFFFFFFFFFFFFFLL;
      v319 = v312;
      if ( v318 < 7 )
        goto LABEL_382;
      v368 = v16;
      v360 = v61;
      v320 = v318 + 1;
      v16 = v320 & 0xFFFFFFFFFFFFFFF8uLL;
      v319 = &v312[v320 & 0xFFFFFFFFFFFFFFF8uLL];
      v321 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v314), 0);
      v322 = 0;
      do
      {
        v323 = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v312[v322 + 4]), v321);
        *(__m128i *)&v312[v322] = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v312[v322]), v321);
        *(__m128i *)&v312[v322 + 4] = v323;
        v322 += 8;
      }
      while ( v16 != v322 );
      v122 = v320 == v16;
      LOWORD(v61) = v360;
      LODWORD(v16) = v368;
      if ( !v122 )
      {
LABEL_382:
        v324 = &v312[v317];
        do
          *v319++ += v314;
        while ( v319 != v324 );
      }
    }
  }
  v325 = v309 * (v315 >> 10);
  if ( v325 == v316 )
  {
    v22 = v352;
  }
  else
  {
    v326 = v301 + 8;
    if ( !v308 )
      v326 = v301;
    v327 = v352;
    if ( v326 > v302 )
      core::slice::index::slice_end_index_len_fail(v326, v302, &off_1803478F8);
    if ( v326 )
    {
      v328 = v325 - v316;
      v329 = (v326 - 1) & 0x3FFFFFFFFFFFFFFFLL;
      v330 = v313;
      if ( v329 < 7 )
        goto LABEL_394;
      v331 = v329 + 1;
      v332 = v331 & 0xFFFFFFFFFFFFFFF8uLL;
      v330 = &v313[v331 & 0xFFFFFFFFFFFFFFF8uLL];
      v333 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v328), 0);
      v334 = 0;
      do
      {
        v335 = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v313[v334 + 4]), v333);
        *(__m128i *)&v313[v334] = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v313[v334]), v333);
        *(__m128i *)&v313[v334 + 4] = v335;
        v334 += 8;
      }
      while ( v332 != v334 );
      if ( v331 != v332 )
      {
LABEL_394:
        v336 = &v313[v326];
        do
          *v330++ += v328;
        while ( v330 != v336 );
      }
    }
    v22 = v327;
  }
  return ((unsigned __int64)v22 << 32) | (unsigned int)((_DWORD)v16 << 16) | (unsigned __int16)v61;
}

```

## disassembly

```asm
0x1800ea780  push    rbp
0x1800ea781  push    r15
0x1800ea783  push    r14
0x1800ea785  push    r13
0x1800ea787  push    r12
0x1800ea789  push    rsi
0x1800ea78a  push    rdi
0x1800ea78b  push    rbx
0x1800ea78c  sub     rsp, 268h
0x1800ea793  lea     rbp, [rsp+80h]
0x1800ea79b  movaps  [rbp+220h+var_50], xmm7
0x1800ea7a2  movaps  [rbp+220h+var_60], xmm6
0x1800ea7a9  mov     [rbp+220h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800ea7b4  mov     [rbp+220h+var_120], r8
0x1800ea7bb  mov     r13, rdx
0x1800ea7be  mov     r12, rcx
0x1800ea7c1  mov     rax, [rdx+10h]
0x1800ea7c5  mov     [rbp+220h+var_1A8], rax
0x1800ea7c9  mov     qword ptr [r9+10h], 0
0x1800ea7d1  mov     qword ptr [r9+28h], 0
0x1800ea7d9  mov     qword ptr [r9+40h], 0
0x1800ea7e1  mov     qword ptr [r9+58h], 0
0x1800ea7e9  mov     qword ptr [r9+70h], 0
0x1800ea7f1  mov     qword ptr [r9+88h], 0
0x1800ea7fc  mov     qword ptr [r9+0B8h], 0
0x1800ea807  mov     qword ptr [r9+0D0h], 0
0x1800ea812  mov     qword ptr [r9+100h], 0
0x1800ea81d  mov     qword ptr [r9+0E8h], 0
0x1800ea828  mov     [rbp+220h+var_168], r9
0x1800ea82f  mov     qword ptr [r9+0A0h], 0
0x1800ea83a  mov     rdi, [rcx+8]
0x1800ea83e  mov     rbx, [rcx+10h]
0x1800ea842  mov     qword ptr [rcx+10h], 0
0x1800ea84a  test    rbx, rbx
0x1800ea84d  jz      short loc_1800EA896
0x1800ea84f  add     rdi, 58h ; 'X'
0x1800ea853  mov     r14, cs:__imp_GetProcessHeap
0x1800ea85a  mov     r15, cs:__imp_HeapFree
0x1800ea861  jmp     short loc_1800EA87C
0x1800ea870  add     rdi, 138h
0x1800ea877  dec     rbx
0x1800ea87a  jz      short loc_1800EA896
0x1800ea87c  cmp     qword ptr [rdi-8], 0
0x1800ea881  jz      short loc_1800EA870
0x1800ea883  mov     rsi, [rdi]
0x1800ea886  call    r14 ; __imp_GetProcessHeap
0x1800ea889  mov     rcx, rax; hHeap
0x1800ea88c  xor     edx, edx; dwFlags
0x1800ea88e  mov     r8, rsi; lpMem
0x1800ea891  call    r15 ; __imp_HeapFree
0x1800ea894  jmp     short loc_1800EA870
0x1800ea896  mov     rax, [r12]
0x1800ea89a  mov     cl, 2
0x1800ea89c  test    rax, rax
0x1800ea89f  jz      loc_1800EBF6E
0x1800ea8a5  movzx   r15d, [rbp+220h+arg_40]
0x1800ea8ad  mov     rsi, [rbp+220h+arg_38]
0x1800ea8b4  mov     rdi, [rbp+220h+arg_28]
0x1800ea8bb  mov     r14, [rbp+220h+arg_20]
0x1800ea8c2  mov     rbx, [r12+10h]
0x1800ea8c7  cmp     rbx, rax
0x1800ea8ca  jnz     short loc_1800EA8DB
0x1800ea8cc  lea     rdx, off_180344A10; "rust\\truetype\\src\\gridfit.rs"
0x1800ea8d3  mov     rcx, r12
0x1800ea8d6  call    alloc__raw_vec__RawVec_truetype__gridfit__GlyphData_alloc__alloc__Global___grow_one_truetype__gridfit__GlyphData_alloc__alloc__Global_
0x1800ea8db  mov     rax, [r12+8]
0x1800ea8e0  imul    rcx, rbx, 138h
0x1800ea8e7  mov     qword ptr [rax+rcx], 0
0x1800ea8ef  mov     qword ptr [rax+rcx+18h], 0
0x1800ea8f8  mov     qword ptr [rax+rcx+28h], 0
0x1800ea901  mov     qword ptr [rax+rcx+38h], 0
0x1800ea90a  mov     qword ptr [rax+rcx+50h], 0
0x1800ea913  mov     qword ptr [rax+rcx+58h], 1
0x1800ea91c  xorps   xmm6, xmm6
0x1800ea91f  movups  xmmword ptr [rax+rcx+60h], xmm6
0x1800ea924  movups  xmmword ptr [rax+rcx+70h], xmm6
0x1800ea929  mov     rdx, 800080007FFF7FFFh
0x1800ea933  mov     [rax+rcx+80h], rdx
0x1800ea93b  movups  xmmword ptr [rax+rcx+88h], xmm6
0x1800ea943  movups  xmmword ptr [rax+rcx+98h], xmm6
0x1800ea94b  movups  xmmword ptr [rax+rcx+0A8h], xmm6
0x1800ea953  movups  xmmword ptr [rax+rcx+0B8h], xmm6
0x1800ea95b  mov     word ptr [rax+rcx+0C8h], 0
0x1800ea965  mov     word ptr [rax+rcx+0FAh], 2
0x1800ea96f  mov     r8, [rbp+220h+var_120]
0x1800ea976  movdqu  xmm0, xmmword ptr [r8]
0x1800ea97b  movdqu  xmm1, xmmword ptr [r8+10h]
0x1800ea981  movdqu  xmmword ptr [rax+rcx+108h], xmm0
0x1800ea98a  movdqu  xmmword ptr [rax+rcx+118h], xmm1
0x1800ea993  mov     edx, [r8+20h]
0x1800ea997  mov     [rax+rcx+128h], edx
0x1800ea99e  mov     [rax+rcx+12Ch], r15w
0x1800ea9a7  mov     word ptr [rax+rcx+12Eh], 0FFFFh
0x1800ea9b1  mov     dword ptr [rax+rcx+130h], 10000h
0x1800ea9bc  mov     [rbp+220h+var_230], r13
0x1800ea9c0  movzx   eax, [rbp+220h+arg_48]
0x1800ea9c7  mov     [rbp+220h+var_1E8], al
0x1800ea9ca  mov     [rbp+220h+var_228], r8
0x1800ea9ce  mov     rax, [rbp+220h+var_168]
0x1800ea9d5  mov     [rbp+220h+var_220], rax
0x1800ea9d9  mov     [rbp+220h+var_218], r14
0x1800ea9dd  mov     [rbp+220h+var_210], rdi
0x1800ea9e1  mov     rcx, [rbp+220h+arg_30]
0x1800ea9e8  mov     [rbp+220h+var_208], rcx
0x1800ea9ec  mov     [rbp+220h+var_200], rsi
0x1800ea9f0  mov     rcx, [rbp+220h+arg_70]
0x1800ea9f7  mov     [rbp+220h+var_1F8], rcx
0x1800ea9fb  mov     [rbp+220h+var_1F0], r12
0x1800ea9ff  inc     rbx
0x1800eaa02  mov     [r12+10h], rbx
0x1800eaa07  jz      loc_1800ECE67
0x1800eaa0d  mov     qword ptr [rax+10h], 0
0x1800eaa15  mov     qword ptr [rax+28h], 0
0x1800eaa1d  mov     qword ptr [rax+40h], 0
0x1800eaa25  mov     qword ptr [rax+58h], 0
0x1800eaa2d  mov     qword ptr [rax+70h], 0
0x1800eaa35  mov     qword ptr [rax+88h], 0
0x1800eaa40  mov     qword ptr [rax+0B8h], 0
0x1800eaa4b  mov     qword ptr [rax+0D0h], 0
0x1800eaa56  mov     qword ptr [rax+100h], 0
0x1800eaa61  mov     qword ptr [rax+0E8h], 0
0x1800eaa6c  mov     qword ptr [rax+0A0h], 0
0x1800eaa77  lea     rax, [r13+18h]
0x1800eaa7b  mov     [rbp+220h+var_1C0], rax
0x1800eaa7f  movzx   eax, word ptr [r13+14Ch]
0x1800eaa87  mov     [rbp+220h+var_148], rax
0x1800eaa8e  movzx   eax, word ptr [r13+120h]
0x1800eaa96  mov     word ptr [rbp+220h+var_198], ax
0x1800eaa9d  movzx   eax, word ptr [r13+14Ah]
0x1800eaaa5  mov     [rbp+220h+var_1B4], eax
0x1800eaaa8  mov     rax, [rdi+20h]
0x1800eaaac  mov     [rbp+220h+var_1E0], rax
0x1800eaab0  mov     rax, [rdi+28h]
0x1800eaab4  mov     [rbp+220h+var_1C8], rax
0x1800eaab8  mov     r15, [rsi]
0x1800eaabb  mov     r8, [rsi+8]
0x1800eaabf  lea     rcx, [rbp+220h+var_110]
0x1800eaac6  movaps  xmm7, cs:__xmm@00010000000000000000000000000000
0x1800eaacd  xor     r11d, r11d
0x1800eaad0  xor     ebx, ebx
0x1800eaad2  mov     [rbp+220h+var_E0], r15
0x1800eaad9  mov     [rbp+220h+var_E8], r12
0x1800eaae0  mov     [rbp+220h+var_C8], r13
0x1800eaae7  mov     [rbp+220h+var_D0], r8
0x1800eaaee  mov     rsi, [r12+8]
0x1800eaaf3  mov     [rbp+220h+var_88], r11
0x1800eaafa  imul    rax, r11, 138h
0x1800eab01  mov     [rbp+220h+var_C0], rax
0x1800eab08  movzx   edi, word ptr [rsi+rax+12Ch]
0x1800eab10  mov     word ptr [rsp+2A0h+var_280], di
0x1800eab15  mov     rdx, r15
0x1800eab18  mov     r9, r13
0x1800eab1b  call    truetype__sfnt__sfac__get_glyph_location
0x1800eab20  cmp     byte ptr [rbp+220h+var_110], 1
0x1800eab27  jz      loc_1800EBF8C
0x1800eab2d  mov     r12d, dword ptr [rbp+220h+var_108]
0x1800eab34  test    r12d, r12d
0x1800eab37  mov     [rbp+220h+var_188], rbx
0x1800eab3e  jz      loc_1800EACB0
0x1800eab44  mov     r13d, dword ptr [rbp+220h+var_110+4]
0x1800eab4b  mov     word ptr [rsp+2A0h+var_280], di
0x1800eab50  mov     r14, r15
0x1800eab53  lea     r15, [rbp+220h+var_110]
0x1800eab5a  mov     rcx, r15
0x1800eab5d  mov     rdx, r14
0x1800eab60  mov     rdi, [rbp+220h+var_D0]
0x1800eab67  mov     r8, rdi
0x1800eab6a  mov     r9, [rbp+220h+var_C8]
0x1800eab71  call    truetype__sfnt__sfac__read_glyph_header_core
0x1800eab76  movzx   eax, word ptr [rbp+220h+var_110+2]
0x1800eab7d  cmp     byte ptr [rbp+220h+var_110], 1
0x1800eab84  jz      loc_1800EBFA1
0x1800eab8a  mov     [rbp+220h+var_78], rax
0x1800eab91  movzx   ebx, word ptr [rbp+220h+var_108]
0x1800eab98  mov     eax, dword ptr [rbp+220h+var_110+4]
0x1800eab9e  mov     [rbp+220h+var_80], rax
0x1800eaba5  mov     rdx, r14
0x1800eaba8  movzx   r14d, word ptr [rbp+220h+var_108+2]
0x1800eabb0  add     r12, r13
0x1800eabb3  mov     [rsp+2A0h+var_280], r12
0x1800eabb8  mov     rcx, r15
0x1800eabbb  mov     r8, rdi
0x1800eabbe  mov     r9, r13
0x1800eabc1  call    sfnt_reader__SfntReader__get_file_fragment
0x1800eabc6  mov     rdx, [rbp+220h+var_110]
0x1800eabcd  mov     rax, rdx
0x1800eabd0  neg     rax
0x1800eabd3  movzx   ecx, word ptr [rbp+220h+var_108]
0x1800eabda  jo      loc_1800EBFA9
0x1800eabe0  movzx   r12d, [rbp+220h+var_102]
0x1800eabe8  mov     eax, dword ptr [rbp+220h+var_108+2]
0x1800eabee  mov     r15, [rbp+220h+var_100]
0x1800eabf5  shl     rax, 10h
0x1800eabf9  shl     r12, 30h
0x1800eabfd  or      r12, rax
0x1800eac00  or      r12, rcx
0x1800eac03  cmp     r14w, 0FFFFh
0x1800eac08  jz      loc_1800EACE0
0x1800eac0e  test    r14w, r14w
0x1800eac12  js      loc_1800EC04C
0x1800eac18  mov     rdi, [rbp+220h+var_118]
0x1800eac1f  jz      loc_1800EACE0
0x1800eac25  mov     [rbp+220h+var_A0], rdx
0x1800eac2c  lea     eax, [r14-1]
0x1800eac30  movzx   eax, ax
0x1800eac33  lea     rdx, ds:0Ah[rax*2]
0x1800eac3b  add     rdx, r13
0x1800eac3e  mov     word ptr [rbp+220h+var_110], 0
0x1800eac47  mov     rax, [rbp+220h+var_D0]
0x1800eac4e  mov     rax, [rax+18h]
0x1800eac52  mov     r10, cs:__guard_dispatch_icall_fptr
0x1800eac59  mov     [rbp+220h+var_1D0], r12
0x1800eac5d  mov     r9d, 2
0x1800eac63  mov     rcx, [rbp+220h+var_E0]
0x1800eac6a  lea     r8, [rbp+220h+var_110]
0x1800eac71  call    r10 ; _guard_dispatch_icall_nop
0x1800eac74  test    al, 1
0x1800eac76  jnz     loc_1800EC1BE
0x1800eac7c  movzx   r8d, word ptr [rbp+220h+var_110]
0x1800eac84  mov     eax, r8d
0x1800eac87  shr     eax, 8
0x1800eac8a  shl     r8d, 8
0x1800eac8e  shrd    r8w, ax, 8
0x1800eac94  rol     r8w, 8
0x1800eac99  inc     r8d
0x1800eac9c  mov     r9d, r14d
0x1800eac9f  mov     rdx, [rbp+220h+var_A0]
0x1800eaca6  jmp     short loc_1800EACE6
0x1800eacb0  mov     r8w, 1
0x1800eacb5  mov     edi, 1
0x1800eacba  xor     r15d, r15d
0x1800eacbd  xor     r13d, r13d
0x1800eacc0  xor     r10d, r10d
0x1800eacc3  mov     [rbp+220h+var_80], 0
0x1800eacce  mov     r9w, 1
0x1800eacd3  xor     ecx, ecx
0x1800eacd5  xor     edx, edx
0x1800eacd7  jmp     short loc_1800EAD1E
0x1800eace0  xor     r9d, r9d
0x1800eace3  xor     r8d, r8d
0x1800eace6  mov     rax, [rbp+220h+var_80]
0x1800eaced  shl     rax, 10h
0x1800eacf1  shl     rbx, 30h
0x1800eacf5  or      rbx, rax
0x1800eacf8  cmp     r14w, 0FFFFh
0x1800eacfd  setz    al
0x1800ead00  mov     [rbp+220h+var_80], rax
0x1800ead07  setnz   r10b
0x1800ead0b  mov     rcx, [rbp+220h+var_78]
0x1800ead12  or      rcx, rbx
0x1800ead15  mov     r13d, 0Ah
0x1800ead1b  mov     rdi, r12
0x1800ead1e  add     rsi, [rbp+220h+var_C0]
0x1800ead25  mov     r12, rdi
0x1800ead28  shr     r12, 10h
0x1800ead2c  cmp     qword ptr [rsi+50h], 0
0x1800ead31  jz      short loc_1800EAD92
0x1800ead33  mov     r11, [rsi+58h]
0x1800ead37  mov     [rbp+220h+lpMem], r11
0x1800ead3e  mov     [rbp+220h+var_D8], r15
0x1800ead45  mov     [rbp+220h+var_78], rcx
0x1800ead4c  mov     [rbp+220h+var_A0], rdx
0x1800ead53  mov     r14d, r8d
0x1800ead56  mov     ebx, r9d
0x1800ead59  mov     r15, r10
0x1800ead5c  call    cs:__imp_GetProcessHeap
0x1800ead62  mov     rcx, rax; hHeap
0x1800ead65  xor     edx, edx; dwFlags
0x1800ead67  mov     r8, [rbp+220h+lpMem]; lpMem
0x1800ead6e  call    cs:__imp_HeapFree
0x1800ead74  mov     r10, r15
0x1800ead77  mov     r9d, ebx
0x1800ead7a  mov     r8d, r14d
0x1800ead7d  mov     rdx, [rbp+220h+var_A0]
0x1800ead84  mov     rcx, [rbp+220h+var_78]
0x1800ead8b  mov     r15, [rbp+220h+var_D8]
0x1800ead92  mov     [rsi+50h], rdx
0x1800ead96  mov     [rbp+220h+var_118], rdi
0x1800ead9d  mov     [rsi+58h], di
0x1800eada1  mov     [rsi+5Ah], r12d
0x1800eada5  shr     r12, 20h
0x1800eada9  mov     [rsi+5Eh], r12w
0x1800eadae  mov     [rsi+60h], r15
0x1800eadb2  mov     [rsi+68h], r13
0x1800eadb6  movzx   eax, r9w
0x1800eadba  mov     [rsi+98h], rax
0x1800eadc1  movzx   eax, r8w
0x1800eadc5  mov     [rsi+0A0h], rax
0x1800eadcc  mov     [rsi+80h], rcx
0x1800eadd3  mov     [rbp+220h+var_180], r10
0x1800eadda  mov     [rsi+130h], r10b
0x1800eade1  movzx   r12d, word ptr [rsi+12Ch]
0x1800eade9  mov     rax, [rbp+220h+arg_30]
0x1800eadf0  movzx   edi, byte ptr [rax+209h]
0x1800eadf7  mov     r15, [rbp+220h+var_E0]
0x1800eadfe  mov     rcx, r15
0x1800eae01  mov     r14, [rbp+220h+var_D0]
0x1800eae08  mov     rdx, r14
0x1800eae0b  mov     rbx, [rbp+220h+var_C8]
0x1800eae12  mov     r8, rbx
  ... truncated ...
```
