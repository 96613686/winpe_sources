# shaping::engine::arabic::get_glyphs

- ea: `0x1800aef80`
- end: `0x1800b3881`
- name: `shaping::engine::arabic::get_glyphs`
- size: `18689`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800465a0`
- `0x180065910`
- `0x180065ec0`
- `0x180066440`
- `0x180066bd0`
- `0x18008d2d0`
- `0x18008d580`
- `0x18008ed10`
- `0x1800a01a0`
- `0x1800a5500`
- `0x1800a6840`
- `0x1800aef80`
- `0x1800c24b0`
- `0x1800c65f0`
- `0x1800c6d80`
- `0x1800c7030`
- `0x1800c7130`
- `0x1800c72f0`
- `0x1800c7350`
- `0x1800c9540`
- `0x1800c9650`
- `0x1800c96c0`
- `0x1800c9710`
- `0x1800d97e0`
- `0x1800dc910`
- `0x180212f4c`
- `0x18021e1b6`
- `0x180316190`
- `0x180316232`
- `0x180316255`
- `0x180316280`
- `0x1803168c1`
- `0x180316940`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316ce0`
- `0x180316ee0`
- `0x18031716c`
- `0x180318360`

## import_xrefs

- `kernel32!HeapFree` at `0x1800b014f`
- `kernel32!HeapFree` at `0x1800b0e40`
- `kernel32!HeapFree` at `0x1800b0e65`
- `kernel32!HeapFree` at `0x1800b0fed`
- `kernel32!HeapFree` at `0x1800b1aac`
- `kernel32!HeapFree` at `0x1800b1ad1`
- `kernel32!HeapFree` at `0x1800b2666`
- `kernel32!HeapFree` at `0x1800b268b`
- `kernel32!HeapFree` at `0x1800b2e3a`
- `kernel32!HeapFree` at `0x1800b32a5`
- `kernel32!HeapFree` at `0x1800b32ca`
- `kernel32!HeapFree` at `0x1800b331d`
- `kernel32!HeapFree` at `0x1800b3342`
- `kernel32!HeapFree` at `0x1800b3367`
- `kernel32!HeapFree` at `0x1800b014f`
- `kernel32!HeapFree` at `0x1800b0e40`
- `kernel32!HeapFree` at `0x1800b0e65`
- `kernel32!HeapFree` at `0x1800b0fed`
- `kernel32!HeapFree` at `0x1800b1aac`
- `kernel32!HeapFree` at `0x1800b1ad1`
- `kernel32!HeapFree` at `0x1800b2666`
- `kernel32!HeapFree` at `0x1800b268b`
- `kernel32!HeapFree` at `0x1800b2e3a`
- `kernel32!HeapFree` at `0x1800b32a5`
- `kernel32!HeapFree` at `0x1800b32ca`
- `kernel32!HeapFree` at `0x1800b331d`
- `kernel32!HeapFree` at `0x1800b3342`
- `kernel32!HeapFree` at `0x1800b3367`
- `kernel32!GetProcessHeap` at `0x1800b013d`
- `kernel32!GetProcessHeap` at `0x1800b0e32`
- `kernel32!GetProcessHeap` at `0x1800b0e57`
- `kernel32!GetProcessHeap` at `0x1800b0fdf`
- `kernel32!GetProcessHeap` at `0x1800b1a9e`
- `kernel32!GetProcessHeap` at `0x1800b1ac3`
- `kernel32!GetProcessHeap` at `0x1800b2654`
- `kernel32!GetProcessHeap` at `0x1800b267d`
- `kernel32!GetProcessHeap` at `0x1800b2e28`
- `kernel32!GetProcessHeap` at `0x1800b3293`
- `kernel32!GetProcessHeap` at `0x1800b32bc`
- `kernel32!GetProcessHeap` at `0x1800b330f`
- `kernel32!GetProcessHeap` at `0x1800b3334`
- `kernel32!GetProcessHeap` at `0x1800b3359`
- `kernel32!GetProcessHeap` at `0x1800b013d`
- `kernel32!GetProcessHeap` at `0x1800b0e32`
- `kernel32!GetProcessHeap` at `0x1800b0e57`
- `kernel32!GetProcessHeap` at `0x1800b0fdf`
- `kernel32!GetProcessHeap` at `0x1800b1a9e`
- `kernel32!GetProcessHeap` at `0x1800b1ac3`
- `kernel32!GetProcessHeap` at `0x1800b2654`
- `kernel32!GetProcessHeap` at `0x1800b267d`
- `kernel32!GetProcessHeap` at `0x1800b2e28`
- `kernel32!GetProcessHeap` at `0x1800b3293`
- `kernel32!GetProcessHeap` at `0x1800b32bc`
- `kernel32!GetProcessHeap` at `0x1800b330f`
- `kernel32!GetProcessHeap` at `0x1800b3334`
- `kernel32!GetProcessHeap` at `0x1800b3359`

## string_xrefs

- `0x1800b13d9`: `assertion failed: cluster_start < chars.len()assertion failed: cluster_len > 0assertion failed: num_shapes > 0assertion failed: chars.len() <= glyphs.len()rust\shaping\src\engine\common_legacy.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall shaping::engine::arabic::get_glyphs(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 *a9,
        unsigned __int64 **a10,
        __int64 a11,
        unsigned __int64 a12,
        __int64 a13,
        unsigned __int64 a14,
        __int64 a15,
        unsigned __int64 a16)
{
  __int64 v18; // r14
  __int64 (__fastcall *v19)(char *); // rsi
  char *v20; // rbx
  __m128i v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 (__fastcall *v25)(unsigned __int64); // rax
  unsigned __int64 v26; // rdx
  __int64 v27; // r12
  unsigned __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // r13
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rcx
  unsigned int v34; // eax
  char v35; // r9
  int v36; // r9d
  __int64 v37; // rax
  unsigned int *v38; // rdi
  unsigned __int64 v39; // r12
  unsigned __int64 v40; // rcx
  char v41; // r8
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r9
  unsigned __int64 v44; // rax
  char v45; // r10
  int v46; // r10d
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // r14
  unsigned int *v50; // r15
  __int64 v51; // rdi
  char v52; // al
  __int64 v53; // rdx
  unsigned __int64 v54; // rcx
  char v55; // r8
  int v56; // r8d
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // r13
  size_t v59; // rsi
  unsigned __int64 v60; // r12
  _DWORD *v61; // rcx
  unsigned __int8 v62; // bl
  char v63; // r14
  __int64 v64; // r15
  unsigned __int64 v65; // rcx
  __m128i v66; // rax
  unsigned __int64 v67; // r9
  unsigned __int64 *v68; // rcx
  __int64 v69; // r8
  unsigned __int64 v70; // r8
  unsigned __int64 v71; // rdi
  unsigned __int64 v72; // rdi
  unsigned __int64 v73; // r10
  bool v74; // cf
  unsigned __int64 v75; // rdi
  unsigned __int64 v76; // rbx
  unsigned __int64 v77; // rdi
  unsigned __int64 v78; // r11
  unsigned __int64 v79; // rdi
  unsigned __int64 v80; // rsi
  volatile signed __int64 *v81; // r15
  char *v82; // rdi
  void *v83; // rbx
  volatile signed __int64 *v84; // r11
  char v85; // al
  unsigned __int8 v86; // cl
  unsigned __int64 v87; // rdx
  char v88; // r8
  __int64 v89; // r14
  unsigned __int64 v90; // r8
  int v91; // esi
  int v92; // eax
  char v93; // bl
  unsigned __int64 v94; // r15
  unsigned __int64 v95; // rax
  unsigned int v96; // edx
  __int64 v97; // rcx
  unsigned __int16 v98; // dx
  unsigned int v99; // esi
  __int64 v100; // r13
  unsigned __int64 v101; // rcx
  __int64 v102; // r9
  unsigned __int16 v103; // si
  int v104; // r10d
  __int64 v105; // rdx
  __int64 v106; // rax
  unsigned int v107; // eax
  __int64 v108; // rax
  int v109; // eax
  unsigned __int64 v110; // rcx
  char *v111; // rax
  signed __int64 v112; // r15
  unsigned __int64 v113; // rcx
  __int64 v114; // rax
  int v115; // eax
  __int64 v116; // rdx
  unsigned __int64 v117; // r13
  unsigned __int64 v118; // rdx
  __int64 v119; // rbx
  unsigned __int64 v120; // r13
  __int64 v121; // r9
  __int64 v122; // r15
  __int64 v123; // rax
  unsigned __int64 v124; // r11
  unsigned int v125; // edx
  int v126; // ecx
  unsigned int v127; // edx
  __int64 v128; // r9
  __int64 v129; // rcx
  unsigned __int64 v130; // rax
  unsigned __int16 v131; // r12
  int v132; // ecx
  __int64 v133; // r12
  bool v134; // zf
  __int64 v135; // r12
  int v136; // eax
  int v137; // eax
  unsigned __int64 v138; // rax
  unsigned __int64 v139; // rdi
  unsigned __int16 v140; // bx
  char *v141; // rcx
  __int64 v142; // rdi
  unsigned __int16 v143; // r13
  char *v144; // r15
  unsigned __int64 v145; // r14
  unsigned __int64 v146; // r9
  unsigned __int64 v147; // r12
  int v148; // ebx
  __int64 v149; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v151; // r10
  unsigned __int16 v152; // r11
  unsigned __int64 v153; // r10
  unsigned __int64 v154; // r10
  unsigned __int64 v155; // rsi
  __int64 v156; // r11
  unsigned __int16 v157; // r8
  unsigned __int16 v158; // r8
  char v159; // bl
  unsigned int v160; // esi
  __int64 v161; // rbx
  unsigned __int64 v162; // rsi
  unsigned __int64 v163; // rdi
  unsigned __int16 v164; // r8
  __int64 v165; // rsi
  unsigned __int8 v166; // di
  unsigned __int64 v167; // rcx
  int v168; // eax
  char v169; // dl
  unsigned __int64 v170; // rax
  unsigned __int64 v171; // rsi
  int v172; // edx
  unsigned __int64 v173; // rcx
  __int64 v174; // rax
  __int64 v175; // r10
  __int64 v176; // rdx
  __int64 v177; // rcx
  unsigned __int64 v178; // r15
  __int64 v179; // r11
  unsigned int v180; // r9d
  char v181; // al
  int v182; // eax
  __int64 v183; // r9
  int v184; // eax
  char *v185; // r12
  __int64 v186; // rax
  unsigned __int64 v187; // rcx
  unsigned __int64 v188; // rbx
  unsigned __int64 v189; // r9
  char v190; // r10
  unsigned __int8 v191; // r15
  char *v192; // r9
  unsigned __int64 v193; // r11
  __int64 v194; // r10
  unsigned __int8 v195; // r11
  char v196; // dl
  char v197; // dl
  int v198; // r10d
  unsigned __int64 v199; // r9
  _WORD *v200; // r10
  unsigned __int64 v201; // rax
  char v202; // cl
  int v203; // ecx
  unsigned __int64 v204; // rax
  unsigned __int64 v205; // rax
  char v206; // al
  __int64 m; // rax
  char v208; // bl
  char v209; // bl
  __int64 v210; // rcx
  char v211; // bl
  int v212; // ebx
  __int64 v213; // rcx
  char v214; // bl
  int v215; // ebx
  __int64 v216; // rcx
  __int64 v217; // rbx
  __int64 v218; // rcx
  int v219; // ebx
  __int64 v220; // rcx
  unsigned __int64 v221; // rcx
  __int64 v222; // rbx
  __int64 v223; // r14
  unsigned __int64 v224; // rdx
  unsigned __int64 v225; // rax
  __int64 v226; // r12
  unsigned __int64 v227; // r10
  unsigned __int64 v228; // rdi
  unsigned int v229; // r9d
  char v230; // r15
  int v231; // r15d
  __int64 v232; // r9
  __int16 v233; // r9
  __int64 v234; // rax
  unsigned __int64 v235; // rcx
  unsigned __int64 v236; // r10
  __int16 v237; // dx
  unsigned __int64 v238; // r9
  __int64 v239; // rbx
  char v240; // dl
  int v241; // edx
  unsigned __int64 v242; // r9
  int v243; // r9d
  int v244; // ebx
  unsigned __int64 v245; // r14
  __int64 v246; // rdx
  unsigned __int64 v247; // rax
  char *v248; // rbx
  __int64 v249; // r14
  unsigned __int64 v250; // rsi
  _DWORD *v251; // rcx
  unsigned __int64 v252; // r13
  unsigned __int64 v253; // r14
  unsigned __int64 v254; // rbx
  _WORD *v255; // rdi
  unsigned __int64 v256; // rsi
  unsigned __int64 v257; // rcx
  unsigned __int64 v258; // rdx
  __int64 v259; // r10
  __int64 v260; // rbx
  unsigned __int64 v261; // rax
  __int64 v262; // r8
  __int64 v263; // r11
  unsigned __int64 v264; // r9
  __int16 v265; // r15
  __int64 v266; // r8
  unsigned __int64 v267; // rax
  unsigned __int64 v268; // rcx
  unsigned __int64 v269; // r10
  unsigned __int64 v270; // r9
  __int64 v271; // rbx
  __int16 v272; // dx
  __int64 **v273; // rsi
  __int64 v274; // rcx
  unsigned __int64 v275; // rbx
  unsigned __int64 v276; // rbx
  __int64 v277; // rax
  __int64 v278; // rcx
  __int64 v279; // rax
  void *v280; // rsi
  HANDLE v281; // rax
  void *v282; // rsi
  HANDLE v283; // rax
  volatile signed __int64 *v284; // rcx
  int v286; // r14d
  __int64 v287; // rbx
  __int32 v288; // edi
  int v289; // ecx
  int v290; // eax
  _DWORD *v291; // rcx
  void *v292; // rsi
  HANDLE v293; // rax
  char *v294; // r13
  int v295; // eax
  int v296; // eax
  __int64 v297; // rdx
  __int64 v298; // rcx
  __int64 v299; // r8
  unsigned __int64 v300; // rdi
  __int64 v301; // rax
  unsigned __int64 v302; // rdi
  unsigned __int8 v303; // al
  unsigned __int64 v304; // rsi
  __int64 v305; // rcx
  char *v306; // r9
  __int64 v307; // rdx
  unsigned __int64 v308; // r8
  __int64 v309; // rbx
  __int64 (__fastcall **v310)(int, int, int, int, int); // rdx
  __int64 v311; // rcx
  __int64 v312; // r15
  __int64 v313; // rax
  __int64 v314; // r9
  __int64 v315; // rcx
  __int64 v316; // rdx
  __int64 v317; // rdi
  unsigned __int64 v318; // rcx
  char *v319; // r13
  unsigned __int64 v320; // r12
  __int64 j; // r10
  unsigned int v322; // r9d
  char v323; // al
  int v324; // eax
  __int64 v325; // r9
  __int64 v326; // r9
  __int64 v327; // rdi
  __int64 k; // rax
  unsigned __int64 v329; // rdx
  int v330; // r8d
  __int64 v331; // rdi
  __int64 v332; // r15
  unsigned __int64 v333; // r12
  __int64 v334; // r13
  int v335; // ebx
  __int64 v336; // r12
  __int64 v337; // rax
  __int16 *v338; // rax
  __int16 v339; // bx
  __int64 v340; // r14
  unsigned __int64 v341; // rax
  __int64 v342; // rbx
  __int64 v343; // r13
  __int64 v344; // r14
  LPVOID v345; // rdi
  _WORD *v346; // rax
  __int64 v347; // rcx
  _WORD *v348; // rax
  __int64 v349; // rcx
  __int16 v350; // dx
  unsigned int v351; // eax
  unsigned int v352; // ecx
  int v353; // eax
  char *v354; // rdi
  char *v355; // rbx
  char *v356; // r15
  const char *v357; // r11
  int v358; // r14d
  int v359; // r9d
  __int64 v360; // r10
  __int16 v361; // r13
  __int64 v362; // rax
  const char *v363; // r12
  _DWORD *v364; // rax
  __int64 v365; // rcx
  __m128i *v366; // r10
  __int64 v367; // r11
  __m128i v368; // xmm0
  __int64 v369; // rdx
  char *v370; // r10
  __int64 v371; // r8
  __int64 v372; // rcx
  __int16 v373; // r9
  unsigned __int64 *v374; // r8
  unsigned __int64 *v375; // rcx
  unsigned __int64 v376; // r9
  unsigned __int64 *v377; // rdx
  void *v378; // rsi
  HANDLE v379; // rax
  void *v380; // rsi
  HANDLE v381; // rax
  _DWORD *v382; // rax
  unsigned int v383; // eax
  unsigned int v384; // ecx
  __int64 v385; // rax
  unsigned __int64 v386; // r9
  unsigned __int64 v387; // r10
  __m128i v388; // xmm0
  unsigned __int64 v389; // r11
  __m128i v390; // xmm3
  __int64 v391; // rcx
  __int64 v392; // r9
  __int64 v393; // rdx
  unsigned __int64 v394; // r8
  __m128i *v395; // r10
  __int64 v396; // r11
  __m128i v397; // xmm0
  __int64 v398; // rdx
  __int16 *v399; // r10
  __int64 v400; // r8
  __int64 v401; // rcx
  __int16 v402; // r9
  unsigned __int64 v403; // rcx
  unsigned __int64 *v404; // rdx
  int v405; // r9d
  unsigned __int64 v406; // r8
  __int64 v407; // rsi
  unsigned __int64 v408; // rax
  __int16 v409; // ax
  unsigned __int64 v410; // rcx
  __int16 v411; // r8
  __int16 v412; // r8
  __int64 (__fastcall *v413)(__int64, _QWORD); // rsi
  unsigned __int64 i; // r14
  unsigned int v415; // ecx
  __int64 **v416; // rax
  char v417; // di
  __int64 *v418; // rcx
  __int64 v419; // rax
  __int64 v420; // rcx
  __int64 v421; // rdx
  __int64 v422; // rsi
  unsigned int v423; // eax
  unsigned int v424; // ecx
  __m128i v425; // xmm0
  unsigned __int64 v426; // rdi
  __int64 v427; // r15
  __int16 v428; // r13
  unsigned __int64 v429; // rdx
  __int16 v430; // ax
  _WORD *v431; // rax
  _DWORD *v432; // rcx
  HANDLE v433; // rax
  void *v434; // rsi
  HANDLE v435; // rax
  unsigned __int64 v436; // rdi
  unsigned __int64 v437; // r12
  unsigned __int64 v438; // rbx
  __int64 v439; // r15
  unsigned __int16 v440; // r14
  __int64 v441; // rsi
  unsigned __int64 v442; // rax
  unsigned __int16 *v443; // rax
  __int64 v444; // rax
  unsigned __int64 n; // rsi
  __int16 v446; // r14
  _WORD *v447; // rax
  HANDLE v448; // rax
  char is_gsub_feature_in_font; // al
  __int64 v450; // rdx
  __int64 v451; // r8
  char v452; // r11
  _DWORD *v453; // rsi
  unsigned __int64 v454; // r9
  __int64 v455; // rdi
  __int16 v456; // bx
  __int16 v457; // r14
  __int16 v458; // r13
  unsigned __int64 v459; // rcx
  __int16 v460; // bx
  __int16 v461; // r15
  __int16 v462; // r14
  unsigned __int64 v463; // r10
  int v464; // r10d
  __m128i *v465; // rdx
  unsigned __int64 v466; // rax
  __int64 v467; // rcx
  __m128i *v468; // rdx
  unsigned __int64 v469; // r8
  __int64 v470; // r9
  __m128i v471; // xmm0
  __int16 *v472; // r8
  __int64 v473; // rcx
  __int64 v474; // r9
  __int16 v475; // r10
  __int64 v476; // rcx
  unsigned __int64 v477; // r8
  __int64 v478; // r9
  __m128i v479; // xmm0
  __int64 v480; // rax
  __int64 v481; // rcx
  __int64 v482; // r8
  __int16 v483; // r9
  _DWORD *v484; // rax
  HANDLE v485; // rax
  void *v486; // rsi
  HANDLE v487; // rax
  void *v488; // rsi
  HANDLE v489; // rax
  void *v490; // rsi
  HANDLE v491; // rax
  void *v492; // rsi
  HANDLE v493; // rax
  __m128i v494; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v495; // [rsp+68h] [rbp-18h]
  __int64 v496; // [rsp+70h] [rbp-10h]
  __int64 v497; // [rsp+78h] [rbp-8h]
  unsigned __int64 v498; // [rsp+80h] [rbp+0h]
  __int64 v499; // [rsp+88h] [rbp+8h]
  unsigned __int64 v500; // [rsp+90h] [rbp+10h]
  char *v501; // [rsp+98h] [rbp+18h]
  __int64 v502; // [rsp+A0h] [rbp+20h]
  __int64 v503; // [rsp+A8h] [rbp+28h]
  __int64 v504; // [rsp+B0h] [rbp+30h]
  __int128 v505; // [rsp+B8h] [rbp+38h]
  char *v506; // [rsp+C8h] [rbp+48h]
  unsigned __int64 v507; // [rsp+D0h] [rbp+50h]
  void *v508; // [rsp+D8h] [rbp+58h]
  __int64 v509; // [rsp+5D0h] [rbp+550h] BYREF
  __m128i Src; // [rsp+5D8h] [rbp+558h] BYREF
  __int128 v511; // [rsp+5E8h] [rbp+568h]
  unsigned __int64 v512; // [rsp+5F8h] [rbp+578h]
  char *v513; // [rsp+600h] [rbp+580h]
  unsigned __int64 v514; // [rsp+608h] [rbp+588h]
  __int64 v515; // [rsp+610h] [rbp+590h]
  unsigned __int64 v516; // [rsp+618h] [rbp+598h]
  unsigned __int64 *v517; // [rsp+620h] [rbp+5A0h]
  unsigned __int64 v518; // [rsp+628h] [rbp+5A8h]
  __m128i *v519; // [rsp+630h] [rbp+5B0h]
  unsigned __int64 v520; // [rsp+638h] [rbp+5B8h]
  __int64 v521; // [rsp+640h] [rbp+5C0h]
  __int64 v522; // [rsp+648h] [rbp+5C8h]
  _QWORD v523[3]; // [rsp+650h] [rbp+5D0h] BYREF
  unsigned __int64 v524; // [rsp+668h] [rbp+5E8h] BYREF
  __int16 v525; // [rsp+670h] [rbp+5F0h]
  char v526; // [rsp+672h] [rbp+5F2h]
  __int16 v527; // [rsp+673h] [rbp+5F3h]
  _QWORD v528[2]; // [rsp+B48h] [rbp+AC8h] BYREF
  __int16 v529; // [rsp+B58h] [rbp+AD8h]
  bool v530; // [rsp+B5Ah] [rbp+ADAh]
  __int64 v531; // [rsp+B60h] [rbp+AE0h]
  __int64 v532; // [rsp+B68h] [rbp+AE8h]
  _QWORD v533[2]; // [rsp+B70h] [rbp+AF0h] BYREF
  __int16 v534; // [rsp+B80h] [rbp+B00h]
  __int16 v535; // [rsp+B82h] [rbp+B02h]
  unsigned __int64 v536; // [rsp+B88h] [rbp+B08h]
  _QWORD v537[2]; // [rsp+B90h] [rbp+B10h] BYREF
  __int16 v538; // [rsp+BA0h] [rbp+B20h]
  __int16 v539; // [rsp+BA2h] [rbp+B22h]
  _DWORD v540[3]; // [rsp+BACh] [rbp+B2Ch] BYREF
  char v541; // [rsp+BB8h] [rbp+B38h]
  int v542; // [rsp+BBAh] [rbp+B3Ah]
  __int16 v543; // [rsp+BBEh] [rbp+B3Eh]
  volatile signed __int64 *v544; // [rsp+BC0h] [rbp+B40h] BYREF
  __int64 v545; // [rsp+BC8h] [rbp+B48h]
  __m128i v546; // [rsp+BD8h] [rbp+B58h] BYREF
  __int16 v547; // [rsp+BE8h] [rbp+B68h]
  __int16 v548; // [rsp+BEAh] [rbp+B6Ah]
  volatile signed __int64 *v549; // [rsp+BF0h] [rbp+B70h] BYREF
  __int64 v550; // [rsp+BF8h] [rbp+B78h]
  __int64 v551; // [rsp+C00h] [rbp+B80h]
  BOOL v552; // [rsp+C0Ch] [rbp+B8Ch] BYREF
  unsigned __int64 v553; // [rsp+C10h] [rbp+B90h]
  unsigned __int64 v554; // [rsp+C18h] [rbp+B98h] BYREF
  __int128 v555; // [rsp+C20h] [rbp+BA0h]
  unsigned __int64 v556; // [rsp+C30h] [rbp+BB0h] BYREF
  LPVOID v557; // [rsp+C38h] [rbp+BB8h]
  unsigned __int64 v558; // [rsp+C40h] [rbp+BC0h]
  _QWORD *v559; // [rsp+C48h] [rbp+BC8h]
  LPVOID v560[2]; // [rsp+C50h] [rbp+BD0h] BYREF
  unsigned __int64 v561; // [rsp+C60h] [rbp+BE0h]
  __int64 v562; // [rsp+C68h] [rbp+BE8h]
  char *v563; // [rsp+C70h] [rbp+BF0h] BYREF
  LPVOID v564[2]; // [rsp+C78h] [rbp+BF8h] BYREF
  unsigned __int64 v565; // [rsp+C88h] [rbp+C08h]
  __int64 v566; // [rsp+C90h] [rbp+C10h]
  LPVOID lpMem; // [rsp+C98h] [rbp+C18h]
  __int64 v568; // [rsp+CA0h] [rbp+C20h]
  __int64 v569; // [rsp+CA8h] [rbp+C28h]
  __int64 v570; // [rsp+CB0h] [rbp+C30h] BYREF
  __int128 v571; // [rsp+CB8h] [rbp+C38h]
  __int64 v572; // [rsp+CC8h] [rbp+C48h]
  __int64 v573; // [rsp+CD0h] [rbp+C50h]
  unsigned __int64 v574; // [rsp+CD8h] [rbp+C58h]
  LPVOID v575; // [rsp+CE0h] [rbp+C60h]
  volatile signed __int64 *v576; // [rsp+CE8h] [rbp+C68h]
  _WORD *v577; // [rsp+CF0h] [rbp+C70h]
  unsigned __int64 v578; // [rsp+CF8h] [rbp+C78h]
  bool v579; // [rsp+D07h] [rbp+C87h]
  __int64 v580; // [rsp+D08h] [rbp+C88h]
  unsigned __int64 v581; // [rsp+D10h] [rbp+C90h]
  LPVOID v582; // [rsp+D18h] [rbp+C98h]
  unsigned __int64 v583; // [rsp+D20h] [rbp+CA0h]
  unsigned __int64 v584; // [rsp+D28h] [rbp+CA8h]
  __int64 v585; // [rsp+D30h] [rbp+CB0h]

  v585 = -2;
  v573 = a1;
  v568 = a4;
  v578 = *(unsigned int *)(a4 + 4);
  v583 = a9[11];
  shaping::engine::helpers::set_default_character_properties(a9, a11, 0);
  v559 = a3;
  v18 = a3[12];
  v572 = a2;
  shaping::caching::CacheSlot_shaping::engine::arabic::FontCacheData_::init_shaping::engine::arabic::FontCacheData_(
    &v549,
    a2,
    v18);
  if ( v549 )
  {
    v19 = *(__int64 (__fastcall **)(char *))(v550 + 24);
    v20 = (char *)v549 + ((*(_QWORD *)(v550 + 16) - 1LL) & 0xFFFFFFFFFFFFFFF0uLL) + 16;
    v21.m128i_i64[0] = v19(v20);
    if ( v21.m128i_i64[1] <= 3uLL )
    {
      v509 = 1;
      Src = v21;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)&v509,
        (unsigned int)&qword_18033B6C8,
        (__int64)&off_18033B840);
    }
    if ( *(_BYTE *)(v21.m128i_i64[0] + 2) )
    {
      v22 = 2 * a14;
      if ( (a14 & 0x8000000000000000uLL) != 0LL || 2 * a14 > 0x7FFFFFFFFFFFFFFELL )
      {
        v23 = 0;
        goto LABEL_6;
      }
      if ( v22 )
      {
        lpMem = (LPVOID)std::sys::alloc::windows::process_heap_alloc(8, v22);
        if ( !lpMem )
        {
          v23 = 2;
          v22 = 2 * a14;
LABEL_6:
          alloc::raw_vec::handle_error(v23, v22, &off_18033CE08);
        }
        v579 = a14 == 0;
      }
      else
      {
        lpMem = (LPVOID)2;
        v579 = 1;
      }
      v66.m128i_i64[0] = v19(v20);
      v566 = a9[9];
      v67 = a9[10];
      v68 = *a10;
      v69 = (__int64)a10[1];
      v537[0] = v67;
      v546.m128i_i64[0] = v69;
      if ( v67 != v69 )
      {
        v509 = 0;
        core::panicking::assert_failed_usize_usize_(v537, &v546, &v509, &off_18033BCC8);
      }
      if ( v66.m128i_i64[1] <= 3uLL )
      {
        v509 = 1;
        Src = v66;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v509,
          (unsigned int)&qword_18033B6C8,
          (__int64)&off_18033C1C0);
      }
      v565 = v67;
      if ( (unsigned __int64)(v66.m128i_i64[1] - 4) <= 0x81F )
      {
        v509 = 1;
        Src.m128i_i64[0] = v66.m128i_i64[0] + 4;
        Src.m128i_i64[1] = v66.m128i_i64[1] - 4;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v509,
          (unsigned int)&qword_18033B728,
          (__int64)&off_18033C1D8);
      }
      v70 = *(unsigned int *)(v66.m128i_i64[0] + 2064);
      v71 = v66.m128i_i64[1] - 2084 - v70;
      if ( v66.m128i_i64[1] - 2084 < v70 )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      LOBYTE(v562) = *(_BYTE *)(v568 + 20);
      LOBYTE(v581) = *(_BYTE *)(v568 + 23);
      v570 = *(unsigned int *)(v66.m128i_i64[0] + 2068);
      if ( v570 != 4096 )
      {
        v509 = 0;
        core::panicking::assert_failed_usize_usize_(&v570, &qword_1803B5150, &v509, &off_18033C208);
      }
      if ( v71 <= 0xFFF )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      v72 = v71 - 4096;
      v73 = *(unsigned int *)(v66.m128i_i64[0] + 2072);
      v74 = v72 < v73;
      v75 = v72 - v73;
      if ( v74 )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      v76 = *(unsigned int *)(v66.m128i_i64[0] + 2052);
      v74 = v75 < v76;
      v77 = v75 - v76;
      if ( v74 )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      v78 = *(unsigned int *)(v66.m128i_i64[0] + 2056);
      v74 = v77 < v78;
      v79 = v77 - v78;
      if ( v74 )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      v80 = *(unsigned int *)(v66.m128i_i64[0] + 2060);
      if ( v79 < v80 )
      {
        v509 = (__int64)&off_180343D18;
        Src.m128i_i64[0] = 1;
        Src.m128i_i64[1] = 8;
        v511 = 0;
        core::panicking::panic_fmt(&v509, &off_18033C220);
      }
      v81 = (volatile signed __int64 *)(v66.m128i_i64[0] + 2084);
      if ( (v70 & 3) != 0 )
      {
        v509 = 1;
        Src.m128i_i64[0] = v66.m128i_i64[0] + 2084;
        Src.m128i_i64[1] = (unsigned int)v70 & 0xFFFFFFFC;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v509,
          (unsigned int)&qword_18033B568,
          (__int64)&off_18033C1F0);
      }
      v82 = (char *)v81 + v70 + v73 + v76 + 4096;
      v83 = (void *)*(unsigned int *)(v66.m128i_i64[0] + 2080);
      v494 = v66;
      v495 = v66.m128i_i64[0] + 4;
      v496 = v66.m128i_i64[0] + 4;
      v497 = v66.m128i_i64[0] + 2084;
      v578 = (unsigned int)v70 >> 2;
      v498 = v578;
      v499 = (__int64)v81 + v70 + 4096;
      v500 = v73;
      v583 = (unsigned __int64)v81 + v70;
      v501 = (char *)v81 + v70;
      v502 = 1024;
      v503 = (__int64)v81 + v70 + 2048;
      v504 = 1024;
      *(_QWORD *)&v505 = v82;
      *((_QWORD *)&v505 + 1) = v78;
      v506 = &v82[v78];
      v507 = v80;
      v582 = v83;
      v508 = v83;
      *((_QWORD *)&v511 + 1) = v566;
      v512 = v565;
      v84 = (volatile signed __int64 *)(v66.m128i_i64[0] + 2084);
      if ( (_BYTE)v562 )
      {
        v521 = -1;
        v513 = (char *)lpMem;
        v514 = a14;
        v515 = a15;
        v516 = a16;
        v522 = 0;
        v509 = 0;
        v517 = v68;
        v518 = v565;
        *(_OWORD *)&v523[1] = 0;
        v85 = *(_BYTE *)(v568 + 21);
        v86 = *(_BYTE *)(v568 + 22);
        v87 = v565 - 1;
        v523[0] = v565 - 1;
        v88 = 1;
      }
      else
      {
        v521 = 1;
        v513 = (char *)lpMem;
        v514 = a14;
        v515 = a15;
        v516 = a16;
        v522 = 0;
        v509 = 0;
        v517 = v68;
        v518 = v565;
        memset(v523, 0, sizeof(v523));
        v86 = *(_BYTE *)(v568 + 21);
        v85 = *(_BYTE *)(v568 + 22);
        v88 = 0;
        v87 = 0;
      }
      v89 = v565;
      v526 = v88;
      v519 = &v494;
      v527 = 0;
      Src.m128i_i64[1] = 0;
      v90 = a12;
      v524 = a12;
      v525 = 0;
      v520 = v87;
      v91 = 4 * v86;
      LODWORD(v574) = 3 * (v85 == 0) + 5;
      v531 = 2LL * (_QWORD)v582;
      v577 = (_WORD *)v559[3];
      v569 = v559[6];
      v92 = v569;
      LOBYTE(v92) = 1;
      LODWORD(v580) = v92;
      v93 = 0;
      v575 = 0;
      v553 = 0;
      LODWORD(v584) = 0;
      v576 = v81;
LABEL_83:
      if ( v89 )
      {
        v551 = (v580 & 1) == 0;
        v532 = -(v580 & 1);
        v94 = v520;
        while ( 1 )
        {
          v95 = (unsigned int)v584;
          if ( (v580 & 1) != 0 )
          {
            if ( v94 >= v565 )
              core::panicking::panic_bounds_check(v94, v565, &off_18033BCE0);
            v96 = *(unsigned __int16 *)(v583 + 2LL * HIBYTE(*(unsigned __int16 *)(v566 + 2 * v94)));
            LODWORD(v584) = *(unsigned __int16 *)(v566 + 2 * v94);
            v97 = (v96 << 8) | (unsigned __int8)v584;
            if ( v96 >= 4 )
              core::panicking::panic_bounds_check(v97, 1024, &off_18033D360);
            v98 = *(_WORD *)(v583 + 2 * v97) & 0x3FF;
            v90 = *(unsigned __int16 *)(v583 + 2 * v97) >> 10;
          }
          else
          {
            v94 += v521;
            v520 = v94;
            LOBYTE(v90) = 4;
            v98 = v574;
          }
          v99 = (_DWORD)v582 * v91;
          v100 = v98;
          v101 = v98 + (unsigned __int64)(unsigned __int16)v99;
          if ( v101 >= v578 )
            core::panicking::panic_bounds_check(v101, v578, &off_18033BCF8);
          v102 = v99;
          v103 = *((_WORD *)v84 + 2 * v101);
          v104 = v103 >> 11;
          v105 = *((unsigned __int16 *)v84 + 2 * v101 + 1);
          switch ( v104 )
          {
            case 0:
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_putout(&v509, v105, v90, v102);
              goto LABEL_131;
            case 1:
            case 2:
            case 3:
            case 4:
              v106 = (unsigned int)(v95 - 1536);
              if ( (unsigned int)v106 >= 0x180 )
                core::panicking::panic_bounds_check(v106, 384, &off_18033BC68);
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                       &v509,
                       (unsigned int)v106,
                       (unsigned __int16)(v104 - 1),
                       (unsigned __int8)byte_1803C12F7[384 * (unsigned int)(unsigned __int16)(v104 - 1) + v106]);
LABEL_131:
              v84 = v576;
              if ( !v107 )
                goto LABEL_132;
              goto LABEL_175;
            case 5:
            case 6:
              HIBYTE(v527) = 1;
              v109 = 32;
              if ( (_BYTE)v581 )
                v109 = v584;
              goto LABEL_125;
            case 7:
            case 8:
            case 9:
            case 10:
              v108 = (unsigned int)(v95 - 1536);
              if ( (unsigned int)v108 >= 0x180 )
                core::panicking::panic_bounds_check(v108, 384, &off_18033BC68);
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                       &v509,
                       (unsigned int)v108,
                       (unsigned __int16)(v104 - 7),
                       (unsigned __int8)byte_1803C12F7[384 * (unsigned int)(unsigned __int16)(v104 - 7) + v108]);
              if ( v107 )
                goto LABEL_175;
              HIBYTE(v527) = 1;
              v109 = 32;
              if ( (_BYTE)v581 )
                v109 = v584;
              goto LABEL_125;
            case 11:
              v114 = (unsigned int)(v95 - 1536);
              if ( (unsigned int)v114 >= 0x180 )
                core::panicking::panic_bounds_check(v114, 384, &off_18033BC68);
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                       &v509,
                       (unsigned int)v114,
                       0,
                       (unsigned __int8)byte_1803C12F7[v114]);
              if ( v107 )
                goto LABEL_175;
              HIBYTE(v527) = 1;
              v109 = 32;
              if ( (_BYTE)v581 )
                v109 = v584;
              goto LABEL_125;
            case 12:
              LOWORD(v95) = 4;
              v553 = v95;
              if ( (_WORD)v102 == 4 )
              {
                v575 = (LPVOID)v94;
              }
              else
              {
                v93 = 1;
                v575 = (LPVOID)(v94 - v521);
                v553 = (unsigned int)v102;
              }
              goto LABEL_132;
            case 13:
              goto LABEL_103;
            case 14:
            case 15:
              HIBYTE(v527) = 1;
LABEL_103:
              v110 = (unsigned __int64)v575;
              v111 = (char *)v575 - v94;
              v112 = v94 - (_QWORD)v575;
              if ( (_BYTE)v562 )
                v112 = (signed __int64)v111;
              v520 = (unsigned __int64)v575;
              v82 = (char *)v551;
              if ( (v93 & 1) == 0 )
                goto LABEL_139;
              if ( (unsigned __int8)v90 > 0xAu )
                core::panicking::panic_bounds_check((unsigned __int8)v90, 11, &off_18033BD10);
              v113 = (unsigned __int16)v553
                   + (unsigned __int64)*(unsigned __int16 *)&aAssertionFaile_28[2 * (unsigned __int8)v90 + 258];
              if ( v113 >= v578 )
                core::panicking::panic_bounds_check(v113, v578, &off_18033BD28);
              if ( (unsigned __int64)v575 >= v565 )
                core::panicking::panic_bounds_check(v575, v565, &off_18033BD40);
              if ( *((_WORD *)v84 + 2 * v113 + 1) )
              {
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_putout(
                         &v509,
                         *((unsigned __int16 *)v84 + 2 * v113 + 1),
                         v90,
                         v102);
              }
              else
              {
                if ( (unsigned __int16)((*((_WORD *)v84 + 2 * v113) >> 11) - 1) > 3u )
                  goto LABEL_138;
                v116 = (unsigned int)*(unsigned __int16 *)(v566 + 2LL * (_QWORD)v575) - 1536;
                if ( (unsigned int)v116 >= 0x180 )
                  core::panicking::panic_bounds_check((unsigned int)v116, 384, &off_18033BC68);
                v115 = (*((unsigned __int16 *)v84 + 2 * v113) >> 11) - 1;
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                         &v509,
                         v116,
                         (unsigned __int16)v115,
                         (unsigned __int8)byte_1803C12F7[384 * (unsigned __int16)v115 + (unsigned int)v116]);
              }
              v84 = v576;
              if ( v107 )
                goto LABEL_175;
LABEL_138:
              v110 = v520 + v521;
              v520 += v521;
              v82 = (char *)v532;
LABEL_139:
              v117 = v531 + v100;
              if ( v117 >= v578 )
                core::panicking::panic_bounds_check(v117, v578, &off_18033BD58);
              v118 = v512;
              if ( v110 >= v512 )
                core::panicking::panic_bounds_check(v110, v512, &off_18033BBF0);
              v103 = *((_WORD *)v84 + 2 * v117);
              v119 = v519[2].m128i_i64[0];
              v120 = v519[2].m128i_u64[1];
              v121 = *((_QWORD *)&v511 + 1);
              v90 = *(unsigned __int16 *)(*((_QWORD *)&v511 + 1) + 2 * v110);
              v82 += v112;
              if ( v82 )
              {
                v122 = 1;
                v123 = 0;
                v124 = v583;
                while ( 1 )
                {
                  if ( v110 >= v118 )
                    core::panicking::panic_bounds_check(v110, v118, &off_18033BC20);
                  v125 = *(unsigned __int16 *)(v121 + 2 * v110);
                  v126 = (unsigned __int8)v125;
                  v127 = *(unsigned __int16 *)(v124 + 2LL * (v125 >> 8));
                  v128 = v127 << 8;
                  v129 = (unsigned int)v128 | v126;
                  if ( v127 >= 4 )
                    core::panicking::panic_bounds_check(v129, 1024, &off_18033D360);
                  v130 = (*(_WORD *)(v124 + 2 * v129) & 0x3FF) + (_QWORD)v582 * v123;
                  if ( v130 >= v120 )
                    core::panicking::panic_bounds_check(v130, v120, &off_18033BC38);
                  v131 = *(_WORD *)(v119 + 4 * v130);
                  v132 = v131 >> 11;
                  if ( !v132 )
                    break;
                  if ( v132 == 1 )
                  {
                    v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                             &v509,
                             (unsigned int)(unsigned __int16)v90 - 1536,
                             0,
                             0);
                    goto LABEL_150;
                  }
LABEL_151:
                  v118 = v512;
                  if ( v520 >= v512 )
                    core::panicking::panic_bounds_check(v520, v512, &off_18033BC50);
                  v133 = v131 & 0x7FF;
                  v121 = *((_QWORD *)&v511 + 1);
                  v90 = *(unsigned __int16 *)(*((_QWORD *)&v511 + 1) + 2 * v520);
                  v110 = v521 + v520;
                  v520 += v521;
                  v123 = v133;
                  v134 = v122++ == (_QWORD)v82;
                  if ( v134 )
                    goto LABEL_155;
                }
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_putout(
                         &v509,
                         *(unsigned __int16 *)(v119 + 4 * v130 + 2),
                         v90,
                         v128);
LABEL_150:
                v124 = v583;
                if ( v107 )
                  goto LABEL_175;
                goto LABEL_151;
              }
              v133 = 0;
LABEL_155:
              v135 = (_QWORD)v582 * v133;
              if ( v135 + 8 >= v120 )
                core::panicking::panic_bounds_check(v135 + 8, v120, &off_18033BC08);
              v136 = *(unsigned __int16 *)(v119 + 4 * v135 + 32) >> 11;
              if ( v136 )
              {
                if ( v136 != 1 )
                  goto LABEL_161;
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_one_glyph(
                         &v509,
                         (unsigned int)(unsigned __int16)v90 - 1536,
                         0,
                         0);
              }
              else
              {
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_putout(
                         &v509,
                         *(unsigned __int16 *)(v119 + 4 * v135 + 34),
                         v90,
                         v121);
              }
              if ( v107 )
                goto LABEL_175;
LABEL_161:
              if ( HIBYTE(v527) == 1 )
              {
                v137 = 32;
                if ( (_BYTE)v581 )
                  v137 = v584;
                v107 = shaping::engine::arabic::legacy::ShapingContext::do_po_cmap(
                         (unsigned int)&v509,
                         v572,
                         (_DWORD)v577,
                         v569,
                         v137,
                         1);
                if ( v107 )
                {
LABEL_175:
                  v148 = 1;
LABEL_176:
                  v149 = v573;
                  *(_DWORD *)v573 = v148;
                  *(_DWORD *)(v149 + 4) = v107;
                  *(_QWORD *)(v149 + 8) = v82;
                  if ( !v579 )
                  {
                    ProcessHeap = GetProcessHeap();
                    HeapFree(ProcessHeap, 0, lpMem);
                  }
                  goto LABEL_379;
                }
                HIBYTE(v527) = 0;
              }
              v93 = 0;
LABEL_127:
              v84 = v576;
LABEL_132:
              v91 = v103 & 0x7FF;
              if ( !--v89 )
              {
                v89 = 1;
                v134 = (v580 & 1) == 0;
                LODWORD(v580) = 0;
                if ( v134 )
                  goto LABEL_169;
                goto LABEL_83;
              }
              v94 = v520 + v521;
              v520 += v521;
              break;
            case 16:
              goto LABEL_116;
            case 17:
            case 18:
              HIBYTE(v527) = 1;
LABEL_116:
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_po_cmap(
                       (unsigned int)&v509,
                       v572,
                       (_DWORD)v577,
                       v569,
                       v95,
                       0);
              if ( v107 )
                goto LABEL_175;
              if ( HIBYTE(v527) != 1 )
                goto LABEL_127;
              v109 = 32;
              if ( (_BYTE)v581 )
                v109 = v584;
LABEL_125:
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_po_cmap(
                       (unsigned int)&v509,
                       v572,
                       (_DWORD)v577,
                       v569,
                       v109,
                       1);
              if ( v107 )
                goto LABEL_175;
              HIBYTE(v527) = 0;
              goto LABEL_127;
            case 19:
            case 20:
              v107 = shaping::engine::arabic::legacy::ShapingContext::do_putout(&v509, v105, v90, v102);
              if ( v107 )
                goto LABEL_175;
              HIBYTE(v527) = 1;
              v109 = 32;
              if ( (_BYTE)v581 )
                v109 = v584;
              goto LABEL_125;
            default:
              goto LABEL_132;
          }
        }
      }
LABEL_169:
      v582 = (LPVOID)v523[2];
      if ( v523[2] > v514 )
        core::slice::index::slice_end_index_len_fail(v582, v514, &off_18033BE00);
      v138 = v505;
      if ( *((_QWORD *)&v505 + 1) <= 0xDu )
      {
        v570 = 1;
        v571 = v505;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v570,
          (unsigned int)&qword_18033B748,
          (__int64)&off_18033BEA8);
      }
      v139 = *(unsigned __int16 *)(v505 + 8);
      if ( *((_QWORD *)&v505 + 1) < v139 )
        core::slice::index::slice_start_index_len_fail(
          *(unsigned __int16 *)(v505 + 8),
          *((_QWORD *)&v505 + 1),
          &off_18033BED8);
      v578 = *((_QWORD *)&v505 + 1);
      v140 = *(_WORD *)(v505 + 6);
      if ( *((_QWORD *)&v505 + 1) - v139 < v140 )
        core::slice::index::slice_end_index_len_fail(v140, *((_QWORD *)&v505 + 1) - v139, &off_18033BEC0);
      if ( (unsigned __int64)v582 >= 2 )
      {
        v141 = v513;
        v142 = v505 + v139;
        v143 = *(_WORD *)(v505 + 10);
        v144 = v506;
        v584 = v507;
        v145 = v507 >> 1;
        v576 = (volatile signed __int64 *)(v578 - 14);
        v577 = (_WORD *)(v505 + 14);
        v146 = 0;
        v147 = (unsigned __int64)v582;
        v569 = v142;
        LOWORD(v580) = v140;
        v583 = v505;
        do
        {
          if ( v146 >= (unsigned __int64)v582 )
            core::panicking::panic_bounds_check(v146, v582, &off_18033CB38);
          if ( (v584 & 1) != 0 )
          {
            v570 = 1;
            *(_QWORD *)&v571 = v144;
            *((_QWORD *)&v571 + 1) = v584 & 0xFFFFFFFFFFFFFFFEuLL;
            core::result::unwrap_failed(
              (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
              43,
              (unsigned int)&v570,
              (unsigned int)&qword_18033B528,
              (__int64)&off_18033CA78);
          }
          v152 = *(_WORD *)&v141[2 * v146];
          v153 = HIBYTE(v152);
          if ( v145 <= v153 )
            core::panicking::panic_bounds_check(HIBYTE(v152), v145, &off_18033CA90);
          v154 = ((*(unsigned __int16 *)&v144[2 * v153] << 8) | (unsigned int)(unsigned __int8)v152) + 256LL;
          if ( v154 >= v145 )
            core::panicking::panic_bounds_check(v154, v145, &off_18033CAA8);
          v155 = v147 - 1;
          v156 = *(unsigned __int16 *)&v144[2 * v154];
          if ( v156 == 0xFFFF )
            goto LABEL_178;
          v151 = v146 + 1;
          if ( v146 + 1 >= (unsigned __int64)v582 )
            core::panicking::panic_bounds_check(v146 + 1, v582, &off_18033CB50);
          v157 = *(_WORD *)&v141[2 * v146 + 2];
          if ( v157 < v143 || (v158 = v157 - v143, v140 <= v158) )
          {
LABEL_178:
            v151 = v146;
          }
          else
          {
            v159 = *(_BYTE *)(v142 + v158);
            if ( v159 )
            {
              v160 = *(unsigned __int16 *)(v138 + 4);
              if ( 2 * v160 > (unsigned __int64)v576 )
              {
                v570 = 1;
                *(_QWORD *)&v571 = v577;
                *((_QWORD *)&v571 + 1) = v576;
                core::result::unwrap_failed(
                  (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                  43,
                  (unsigned int)&v570,
                  (unsigned int)&qword_18033B528,
                  (__int64)&off_18033BEF0);
              }
              v161 = (unsigned __int8)(v159 - 1);
              if ( (unsigned int)v161 >= v160 )
                core::panicking::panic_bounds_check(v161, *(unsigned __int16 *)(v138 + 4), &off_18033BF08);
              v162 = (unsigned __int16)v577[v161];
              v163 = v578 - v162;
              if ( v578 < v162 )
                core::slice::index::slice_start_index_len_fail((unsigned __int16)v577[v161], v578, &off_18033BF38);
              v164 = *(_WORD *)(v583 + 2);
              v165 = v583 + v162;
              if ( 2 * (unsigned int)v164 > v163 )
              {
                v570 = 1;
                *(_QWORD *)&v571 = v165;
                *((_QWORD *)&v571 + 1) = v163;
                core::result::unwrap_failed(
                  (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                  43,
                  (unsigned int)&v570,
                  (unsigned int)&qword_18033B528,
                  (__int64)&off_18033BF20);
              }
              if ( v164 <= (unsigned __int16)v156 )
                core::panicking::panic_bounds_check(v156, v164, &off_18033CB68);
              *(_WORD *)&v141[2 * v146] = *(_WORD *)(v165 + 2 * v156);
              v155 = v147 - 2;
              v138 = v583;
              v142 = v569;
            }
            else
            {
              v151 = v146;
            }
            v140 = v580;
          }
          v147 = v155;
          v146 = v151 + 1;
        }
        while ( v155 > 1 );
      }
      v303 = *(_BYTE *)(v568 + 26);
      v304 = v565;
      if ( v303 & 1 | ((v562 & 1) == 0) )
        goto LABEL_521;
      v305 = v523[2];
      if ( v523[2] > v514 )
        core::slice::index::slice_end_index_len_fail(v523[2], v514, &off_18033BD70);
      if ( v523[2] >= 2u )
      {
        v306 = v513;
        v307 = v523[2] >> 1;
        if ( v523[2] < 0x10u )
        {
          v308 = 0;
LABEL_487:
          v369 = -v307;
          v370 = &v306[2 * v308];
          v371 = -(__int64)v308;
          v372 = (__int64)&v306[2 * v305 - 2];
          do
          {
            v373 = *(_WORD *)v370;
            *(_WORD *)v370 = *(_WORD *)(v372 + 2 * v371);
            *(_WORD *)(v372 + 2 * v371--) = v373;
            v370 += 2;
          }
          while ( v369 != v371 );
          goto LABEL_489;
        }
        v308 = v307 & 0xFFFFFFFFFFFFFFF8uLL;
        v366 = (__m128i *)&v513[2 * v523[2] - 16];
        v367 = 0;
        do
        {
          v368 = _mm_loadu_si128((const __m128i *)&v306[2 * v367]);
          *(__m128i *)&v306[2 * v367] = _mm_shufflehi_epi16(
                                          _mm_shufflelo_epi16(_mm_shuffle_epi32(_mm_loadu_si128(v366), 78), 27),
                                          27);
          *v366 = _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_shuffle_epi32(v368, 78), 27), 27);
          v367 += 8;
          --v366;
        }
        while ( v308 != v367 );
        if ( v307 != v308 )
          goto LABEL_487;
      }
LABEL_489:
      if ( v304 > v518 )
        core::slice::index::slice_end_index_len_fail(v304, v518, &off_18033BD88);
      if ( !v304 )
        goto LABEL_512;
      v374 = v517;
      v375 = (unsigned __int64 *)((char *)v517 + 2 * v304);
      v376 = (v304 - 1) & 0x7FFFFFFFFFFFFFFFLL;
      if ( v376 >= 0xD )
      {
        if ( &v523[2] < v375 && v517 < &v524 )
        {
          v377 = v517;
        }
        else
        {
          v386 = v376 + 1;
          v387 = v386 & 0xFFFFFFFFFFFFFFFCuLL;
          v377 = (unsigned __int64 *)((char *)v517 + 2 * (v386 & 0xFFFFFFFFFFFFFFFCuLL));
          v388 = _mm_shufflelo_epi16(_mm_cvtsi32_si128(v523[2]), 0);
          v389 = 0;
          do
          {
            v390 = _mm_add_epi16(_mm_xor_si128(_mm_cvtsi32_si128(HIDWORD(v374[v389 / 4])), (__m128i)-1LL), v388);
            LODWORD(v374[v389 / 4]) = _mm_cvtsi128_si32(
                                        _mm_add_epi16(
                                          _mm_xor_si128(_mm_cvtsi32_si128(v374[v389 / 4]), (__m128i)-1LL),
                                          v388));
            HIDWORD(v374[v389 / 4]) = _mm_cvtsi128_si32(v390);
            v389 += 4LL;
          }
          while ( v387 != v389 );
          if ( v386 == v387 )
            goto LABEL_512;
        }
      }
      else
      {
        v377 = v517;
      }
      do
      {
        *(_WORD *)v377 = LOWORD(v523[2]) + ~*(_WORD *)v377;
        v377 = (unsigned __int64 *)((char *)v377 + 2);
      }
      while ( v377 != v375 );
LABEL_512:
      v391 = v523[2];
      if ( v523[2] > v516 )
        core::slice::index::slice_end_index_len_fail(v523[2], v516, &off_18033BDA0);
      if ( v523[2] < 2u )
        goto LABEL_521;
      v392 = v515;
      v393 = v523[2] >> 1;
      if ( v523[2] >= 0x10u )
      {
        v394 = v393 & 0xFFFFFFFFFFFFFFF8uLL;
        v395 = (__m128i *)(v515 + 2LL * v523[2] - 16);
        v396 = 0;
        do
        {
          v397 = _mm_loadu_si128((const __m128i *)(v392 + 2 * v396));
          *(__m128i *)(v392 + 2 * v396) = _mm_shufflehi_epi16(
                                            _mm_shufflelo_epi16(_mm_shuffle_epi32(_mm_loadu_si128(v395), 78), 27),
                                            27);
          *v395 = _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_shuffle_epi32(v397, 78), 27), 27);
          v396 += 8;
          --v395;
        }
        while ( v394 != v396 );
        if ( v393 == v394 )
          goto LABEL_521;
      }
      else
      {
        v394 = 0;
      }
      v398 = -v393;
      v399 = (__int16 *)(v392 + 2 * v394);
      v400 = -(__int64)v394;
      v401 = v392 + 2 * v391 - 2;
      do
      {
        v402 = *v399;
        *v399 = *(_WORD *)(v401 + 2 * v400);
        *(_WORD *)(v401 + 2 * v400--) = v402;
        ++v399;
      }
      while ( v398 != v400 );
LABEL_521:
      v523[0] = 0;
      if ( v303 | (unsigned __int8)v562 )
      {
        v403 = v523[2];
        if ( v523[2] )
        {
          if ( v304 > v518 )
            core::slice::index::slice_end_index_len_fail(v304, v518, &off_18033B858);
          if ( v304 )
          {
            v404 = v517;
            v405 = LODWORD(v523[2]) - 1;
            v406 = 0;
            if ( !v303 )
              v405 = 0;
            if ( !(_BYTE)v562 )
              v405 = 0;
            v407 = 2 * v304;
            do
            {
              v408 = *(unsigned __int16 *)((char *)v404 + v406);
              if ( v403 <= v408 )
              {
                *(_WORD *)((char *)v404 + v406) = v405;
                LODWORD(v408) = v405;
              }
              v406 += 2LL;
              v405 = v408;
            }
            while ( v407 != v406 );
          }
        }
      }
      else if ( v304 )
      {
        v409 = 0;
        v410 = 0;
        do
        {
          if ( v410 >= v518 )
            core::panicking::panic_bounds_check(v410, v518, &off_18033BDB8);
          v412 = *((_WORD *)v517 + v410);
          if ( v412 == v409 )
          {
            if ( v410 >= v304 )
            {
LABEL_544:
              v411 = v523[2];
            }
            else
            {
              while ( 1 )
              {
                if ( v410 >= v518 )
                  core::panicking::panic_bounds_check(v518, v518, &off_18033BDD0);
                v411 = *((_WORD *)v517 + v410);
                if ( v411 != v409 )
                  break;
                if ( v304 == ++v410 )
                {
                  v410 = v304;
                  goto LABEL_544;
                }
              }
            }
          }
          else
          {
            if ( v410 < v304 )
            {
              while ( 1 )
              {
                if ( v410 >= v518 )
                  core::panicking::panic_bounds_check(v410, v518, &off_18033BDE8);
                if ( *((_WORD *)v517 + v410) != v412 )
                  break;
                *((_WORD *)v517 + v410++) = v409;
                if ( v304 == v410 )
                {
                  v410 = v304;
                  break;
                }
              }
            }
            v411 = v412 + 1;
          }
          v409 = v411;
        }
        while ( v410 < v304 );
      }
      v82 = (char *)v523[2];
      v107 = (unsigned int)v559;
      v413 = (__int64 (__fastcall *)(__int64, _QWORD))v559[13];
      v148 = 0;
      for ( i = 0; i < a14; ++i )
      {
        v107 = v413(v572, *((unsigned __int16 *)lpMem + i));
        v415 = HIWORD(v107);
        if ( (v107 & 1) != 0 )
          LOWORD(v415) = 0;
        *(_WORD *)(a13 + 2 * i) = v415;
      }
      goto LABEL_176;
    }
  }
  shaping::caching::CacheSlot_shaping::caching::CommonFontCacheData_::init_shaping::caching::CommonFontCacheData_(
    &v509,
    v572,
    v18);
  if ( !v509 )
  {
    v61 = (_DWORD *)v573;
    *(_DWORD *)(v573 + 4) = Src.m128i_i32[0];
    *v61 = 1;
    goto LABEL_379;
  }
  v24 = *(_QWORD *)(Src.m128i_i64[0] + 16);
  v565 = Src.m128i_i64[0];
  v25 = *(__int64 (__fastcall **)(unsigned __int64))(Src.m128i_i64[0] + 24);
  v576 = (volatile signed __int64 *)v509;
  v27 = v25(v509 + ((v24 - 1) & 0xFFFFFFFFFFFFFFF0uLL) + 16);
  v28 = v583;
  if ( (v27 & 3) != 0 )
  {
    v444 = 0;
    goto LABEL_671;
  }
  if ( v26 <= 0xBB )
  {
    v444 = 1;
LABEL_671:
    v509 = v444;
    Src.m128i_i64[0] = v27;
    Src.m128i_i64[1] = v26;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&v509,
      (unsigned int)&qword_18033B688,
      (__int64)&off_18033B840);
  }
  LOBYTE(v577) = *(_BYTE *)(v568 + 20);
  v569 = v27;
  if ( (_BYTE)v577 || !v583 )
  {
LABEL_24:
    shaping::string::ShapingString::copy_string_to_vec(&v494, a9);
    v38 = (unsigned int *)v494.m128i_i64[1];
    v39 = v495;
    v40 = 0;
    v582 = (LPVOID)v494.m128i_i64[1];
LABEL_25:
    v41 = 0;
    v42 = v40;
    if ( v40 >= v39 )
    {
LABEL_35:
      v43 = v39;
      goto LABEL_37;
    }
    v43 = v40;
    while ( 1 )
    {
      v44 = v38[v43];
      if ( v44 > 0x10EFF )
        goto LABEL_32;
      v45 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v44 >> 8));
      if ( v45 >= 0 )
        goto LABEL_32;
      v46 = v45 & 0x7F;
      v47 = (unsigned __int8)v44 | (unsigned __int64)(unsigned int)(v46 << 8);
      if ( (unsigned __int8)v46 >= 6u )
        core::panicking::panic_bounds_check(v47, 1536, &off_1803431E8);
      if ( (unsigned __int8)(byte_1803C65A5[v47] - 6) >= 0xDu )
      {
LABEL_32:
        if ( (v41 & 1) != 0 )
        {
          if ( v43 <= v42 )
            core::panicking::panic(
              "assertion failed: i_next_base > i_base_char || i_next_base == chars.len()assertion failed: i_next_base - i_base_char <= chars.len()",
              73,
              &off_18033BAD0);
LABEL_37:
          v48 = v43 - v42;
          if ( v43 - v42 > v39 )
            core::panicking::panic("assertion failed: i_next_base - i_base_char <= chars.len()", 58, &off_18033BAE8);
          if ( (v41 & 1) == 0 )
            goto LABEL_57;
          if ( v40 >= v39 )
            core::panicking::panic(
              "assertion failed: cluster_start < chars.len()assertion failed: cluster_len > 0assertion failed: num_shapes"
              " > 0assertion failed: chars.len() <= glyphs.len()rust\\shaping\\src\\engine\\common_legacy.rs",
              45,
              &off_18033CE20);
          if ( v43 == v42 )
            core::panicking::panic(
              "assertion failed: cluster_len > 0assertion failed: num_shapes > 0assertion failed: chars.len() <= glyphs.len()rust\\shaping\\src\\engine\\common_legacy.rs",
              33,
              &off_18033CE38);
          v49 = v48 + v40;
          if ( v48 + v40 > v39 )
          {
LABEL_57:
            v58 = v495;
            v561 = v495;
            *(__m128i *)v560 = _mm_loadu_si128(&v494);
            v584 = (unsigned __int64)v560[1];
            v59 = 4 * v495;
            LOBYTE(v38) = 1;
            v60 = v583;
            goto LABEL_58;
          }
          if ( v49 < v40 )
            core::slice::index::slice_index_order_fail(v40, v48 + v40, &off_18033D150);
          v50 = &v38[v40];
          v509 = 0;
          v51 = 0;
          v52 = 0;
          while ( 2 )
          {
            v53 = v51++;
            v54 = v50[v53];
            if ( v54 <= 0x10EFF && (v55 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v54 >> 8)), v55 < 0) )
            {
              v56 = v55 & 0x7F;
              v57 = (unsigned __int8)v54 | (unsigned __int64)(unsigned int)(v56 << 8);
              if ( (unsigned __int8)v56 >= 6u )
                core::panicking::panic_bounds_check(v57, 1536, &off_1803431E8);
              if ( (unsigned int)(unsigned __int8)byte_1803C65A5[v57] - 7 >= 0xC )
              {
                if ( (v52 & 1) != 0 )
                {
LABEL_49:
                  enum2__shaping::engine::arabic::fsm::reorder_arabic_cluster::State_::apply_mcm_shifts(&v509, v50, v48);
                  v509 = 0;
                  v52 = 0;
                }
              }
              else
              {
                v509 = 1;
                if ( (v52 & 1) == 0 )
                  Src.m128i_i64[0] = v53;
                Src.m128i_i64[1] = v51;
                v52 = 1;
              }
            }
            else if ( (v52 & 1) != 0 )
            {
              goto LABEL_49;
            }
            if ( v51 == v48 )
            {
              enum2__shaping::engine::arabic::fsm::reorder_arabic_cluster::State_::apply_mcm_shifts(&v509, v50, v48);
              v40 = v49;
              v38 = (unsigned int *)v582;
              goto LABEL_25;
            }
            continue;
          }
        }
        v42 = v43;
      }
      else
      {
        v40 = v42;
        v41 = 1;
      }
      if ( v39 == ++v43 )
        goto LABEL_35;
    }
  }
  v29 = *a9;
  v30 = a9[1];
  v31 = a9[2];
  v32 = a9[10];
  v33 = 0;
  while ( 1 )
  {
    if ( __OFSUB__(-v29, 1) )
    {
      if ( v33 >= v32 )
        core::panicking::panic_bounds_check(v33, a9[10], &off_180341210);
      v34 = *(unsigned __int16 *)(a9[9] + 2 * v33);
    }
    else
    {
      if ( v33 >= v31 )
        core::panicking::panic_bounds_check(v33, a9[2], &off_1803411F8);
      v34 = *(_DWORD *)(v30 + 4 * v33);
      if ( v34 > 0x10EFF )
        goto LABEL_13;
    }
    v35 = byte_1803C6BA5[v34 >> 8];
    if ( v35 < 0 )
    {
      v36 = v35 & 0x7F;
      v37 = (unsigned __int8)v34 | (unsigned int)(v36 << 8);
      if ( (unsigned __int8)v36 >= 5u )
        core::panicking::panic_bounds_check(v37, 1280, &off_180343200);
      if ( *((_BYTE *)&dword_1803C6CB4 + v37) == 1 )
        break;
    }
LABEL_13:
    if ( v583 == ++v33 )
      goto LABEL_24;
  }
  if ( 4 * v583 >= 0x7FFFFFFFFFFFFFFDLL || v583 >> 62 != 0 )
    alloc::raw_vec::capacity_overflow(&off_18033CCE8);
  v582 = (LPVOID)a9[9];
  v581 = 4 * v583;
  v174 = std::sys::alloc::windows::process_heap_alloc(8, 4 * v583);
  if ( !v174 )
    alloc::alloc::handle_alloc_error(4, v581);
  v566 = v174;
  v175 = v174;
  v176 = -(__int64)v28;
  v177 = v28 - 1;
  v178 = 0;
  v179 = v28;
  v584 = v174;
  v580 = v30;
  while ( 1 )
  {
    if ( !(v178 + v176) )
    {
      v179 = -1;
      v178 = v28;
      goto LABEL_419;
    }
    --v179;
    if ( __OFSUB__(-v29, 1) )
    {
      if ( v178 >= v32 )
        core::panicking::panic_bounds_check(v178, v32, &off_180341210);
      v180 = *((unsigned __int16 *)v582 + v178);
    }
    else
    {
      if ( v178 >= v31 )
        core::panicking::panic_bounds_check(v178, v31, &off_1803411F8);
      v180 = *(_DWORD *)(v30 + 4 * v178);
      if ( v180 > 0x10EFF )
        goto LABEL_419;
    }
    v181 = *((_BYTE *)&word_1803C6496 + (v180 >> 8));
    if ( v181 >= 0 )
      goto LABEL_419;
    v182 = v181 & 0x7F;
    v183 = (unsigned __int8)v180 | (unsigned int)(v182 << 8);
    if ( (unsigned __int8)v182 >= 6u )
      core::panicking::panic_bounds_check(v183, 1536, &off_1803431E8);
    if ( (unsigned __int8)(byte_1803C65A5[v183] - 6) > 0xCu )
      break;
    if ( __OFSUB__(-v29, 1) )
    {
      v28 = v583;
      if ( v178 >= v32 )
        core::panicking::panic_bounds_check(v178, v32, &off_180341210);
      v184 = *((unsigned __int16 *)v582 + v178);
    }
    else
    {
      v28 = v583;
      if ( v178 >= v31 )
        core::panicking::panic_bounds_check(v178, v31, &off_1803411F8);
      v184 = *(_DWORD *)(v30 + 4 * v178);
    }
    *(_DWORD *)(v175 + 4 * v177) = v184;
    ++v178;
    --v177;
  }
  v179 = v177;
LABEL_419:
  v566 += 4;
  while ( 1 )
  {
    v60 = v583;
    v316 = v583 - v178;
    if ( v583 <= v178 )
      break;
    v317 = v179;
    v318 = v178;
    v319 = (char *)v582 + 2 * v178;
    v320 = v580 + 4 * v178;
    for ( j = 1; v316 != j; ++j )
    {
      v178 = j + v318;
      if ( __OFSUB__(-v29, 1) )
      {
        if ( v178 >= v32 )
          core::panicking::panic_bounds_check(j + v318, v32, &off_180341210);
        v322 = *(unsigned __int16 *)&v319[2 * j];
      }
      else
      {
        if ( v178 >= v31 )
          core::panicking::panic_bounds_check(j + v318, v31, &off_1803411F8);
        v322 = *(_DWORD *)(v320 + 4 * j);
        if ( v322 > 0x10EFF )
          goto LABEL_432;
      }
      v323 = *((_BYTE *)&word_1803C6496 + (v322 >> 8));
      if ( v323 >= 0 )
        goto LABEL_432;
      v324 = v323 & 0x7F;
      v325 = (unsigned __int8)v322 | (unsigned int)(v324 << 8);
      if ( (unsigned __int8)v324 >= 6u )
        core::panicking::panic_bounds_check(v325, 1536, &off_1803431E8);
      if ( (unsigned __int8)(byte_1803C65A5[v325] - 6) > 0xCu )
        goto LABEL_432;
    }
    j = v316;
    v178 = v583;
LABEL_432:
    v179 -= j;
    if ( j )
    {
      v326 = v179 + 1;
      v327 = v566 + 4 * v317 - 4 * j;
      for ( k = 0; k != j; ++k )
      {
        v329 = v318 + k;
        if ( __OFSUB__(-v29, 1) )
        {
          if ( v329 >= v32 )
            core::panicking::panic_bounds_check(v318 + k, v32, &off_180341210);
          v330 = *(unsigned __int16 *)&v319[2 * k];
        }
        else
        {
          if ( v329 >= v31 )
            core::panicking::panic_bounds_check(v318 + k, v31, &off_1803411F8);
          v330 = *(_DWORD *)(v320 + 4 * k);
        }
        if ( v326 + k >= v583 )
          core::panicking::panic_bounds_check(v326 + k, v583, &off_18033CD00);
        *(_DWORD *)(v327 + 4 * k) = v330;
      }
    }
  }
  v560[0] = (LPVOID)v583;
  v560[1] = (LPVOID)v584;
  v561 = v583;
  LODWORD(v38) = 0;
  v58 = v583;
  v59 = v581;
LABEL_58:
  if ( v59 >= 0x7FFFFFFFFFFFFFFFLL || v58 >> 62 != 0 )
    alloc::raw_vec::capacity_overflow(&off_180348ED8);
  v62 = *(_BYTE *)(v568 + 21);
  v63 = *(_BYTE *)(v568 + 22);
  if ( v59 )
  {
    v64 = std::sys::alloc::windows::process_heap_alloc(0, v59);
    v65 = v58;
    if ( !v64 )
      alloc::alloc::handle_alloc_error(2, v59);
  }
  else
  {
    v64 = 2;
    v65 = 0;
  }
  LODWORD(v566) = (_DWORD)v38;
  v582 = (LPVOID)v64;
  if ( !v58 )
  {
    v170 = 0;
    v171 = 0;
    goto LABEL_276;
  }
  v574 = v65;
  v166 = 0;
  memset_0((void *)v64, 0, v59);
  v167 = *(unsigned int *)v584;
  v168 = 1;
  LOBYTE(v581) = v63;
  if ( v167 > 0x10EFF )
  {
LABEL_225:
    v580 = 0;
    goto LABEL_226;
  }
  v169 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v167 >> 8));
  if ( v169 < 0 )
  {
    v172 = v169 & 0x7F;
    v173 = (unsigned __int8)v167 | (unsigned __int64)(unsigned int)(v172 << 8);
    if ( (unsigned __int8)v172 >= 6u )
      core::panicking::panic_bounds_check(v173, 1536, &off_1803431E8);
    v166 = byte_1803C65A5[v173];
    if ( (unsigned __int8)(v166 - 1) >= 4u )
    {
      if ( (unsigned __int8)(v166 - 6) < 0xDu )
      {
        v166 = 22;
        v580 = 1;
        v168 = 524315;
        goto LABEL_226;
      }
    }
    else
    {
      v168 = (v62 << 18) | 0x10001;
    }
    goto LABEL_225;
  }
  v580 = 0;
  v166 = 0;
LABEL_226:
  *(_DWORD *)v64 = v168;
  v185 = (char *)(v64 + 6);
  v186 = 1;
  v187 = 0;
  v188 = 0;
  while ( (v58 == 0) + v58 != v186 )
  {
    v189 = *(unsigned int *)(v584 + 4 * v186);
    if ( v189 <= 0x10EFF && (v190 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v189 >> 8)), v190 < 0) )
    {
      v198 = v190 & 0x7F;
      v199 = (unsigned __int8)v189 | (unsigned __int64)(unsigned int)(v198 << 8);
      if ( (unsigned __int8)v198 >= 6u )
        core::panicking::panic_bounds_check(v199, 1536, &off_1803431E8);
      v191 = byte_1803C65A5[v199];
      v200 = v582;
      *((_DWORD *)v582 + v186) = 0;
      v192 = (char *)&v200[2 * v186 + 1];
      if ( (unsigned __int8)(v191 - 6) <= 0xCu )
      {
        v200[2 * v186] = 2;
        LOBYTE(v200[2 * v186 + 1]) = 0;
        if ( v166 == 22 )
        {
          ++v580;
          v200[2 * v186] = 26;
          v187 = v186;
          v188 = v186;
        }
      }
    }
    else
    {
      *(_DWORD *)(v64 + 4 * v186) = 0;
      v191 = 0;
      v192 = v185;
    }
    if ( v187 >= v58 )
      core::panicking::panic_bounds_check(v187, v58, &off_18033BA70);
    v193 = *((unsigned __int8 *)v582 + 4 * v187 + 2);
    if ( v193 >= 9 )
      core::panicking::panic(
        "assertion failed: (shape_current as u8) < ARSYFSM_SHAPE_MAX as u8assertion failed: i_next_base > i_base_char || i_next_base == chars.len()assertion failed: i_next_base - i_base_char <= chars.len()",
        65,
        &off_18033BA88);
    v194 = v166;
    v166 = v191;
    v195 = *((_BYTE *)&word_1803C005E + 529 * v193 + 23 * v194 + v191);
    v196 = byte_1803B4AC3[v195];
    if ( v196 != -1 )
      *((_BYTE *)v582 + 4 * v187 + 2) = v196;
    v197 = 8;
    if ( v191 != 22 )
      v197 = byte_1803B4AD5[v195];
    *v192 = v197;
    if ( v195 )
    {
      v187 = v186;
      v188 = v186;
    }
    else
    {
      v166 = v194;
    }
    v185 += 4;
    ++v186;
    v64 = (__int64)v582;
  }
  v60 = v583;
  if ( (v581 & 1) != 0 )
  {
    if ( v188 >= v58 )
      core::panicking::panic_bounds_check(v188, v58, &off_18033BA40);
    v201 = *(unsigned int *)(v584 + 4 * v188);
    if ( v201 <= 0x10EFF )
    {
      v202 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v201 >> 8));
      if ( v202 < 0 )
      {
        v203 = v202 & 0x7F;
        v204 = (unsigned __int8)v201 | (unsigned __int64)(unsigned int)(v203 << 8);
        if ( (unsigned __int8)v203 >= 6u )
          core::panicking::panic_bounds_check(v204, 1536, &off_1803431E8);
        if ( byte_1803C65A5[v204] == 1 )
        {
          v205 = *(unsigned __int8 *)(v64 + 4 * v188 + 2);
          if ( v205 >= 9 )
            core::panicking::panic(
              "assertion failed: (shape_current as usize) < ARSYFSM_SHAPE_MAXassertion failed: (shape_current as u8) < AR"
              "SYFSM_SHAPE_MAX as u8assertion failed: i_next_base > i_base_char || i_next_base == chars.len()assertion fa"
              "iled: i_next_base - i_base_char <= chars.len()",
              62,
              &off_18033BA58);
          v206 = byte_1803B4AC3[*((unsigned __int8 *)&word_1803C005E + 529 * v205 + 43)];
          if ( v206 != -1 )
            *(_BYTE *)(v64 + 4 * v188 + 2) = v206;
        }
      }
    }
  }
  v580 += v58;
  for ( m = 0; v58 != m; ++m )
  {
    v210 = *(unsigned int *)(v584 + 4 * m);
    v209 = 1;
    if ( v210 != 32 )
    {
      if ( (unsigned int)(v210 - 1536) > 0x17F )
      {
LABEL_256:
        v209 = 0;
      }
      else
      {
        switch ( *(_BYTE *)(v64 + 4 * m + 2) )
        {
          case 2:
            v211 = byte_1803C9655[(unsigned int)v210 >> 8];
            if ( v211 >= 0 )
              goto LABEL_256;
            v212 = v211 & 0x7F;
            v213 = (unsigned __int8)v210 | (unsigned int)(v212 << 8);
            if ( (unsigned __int8)v212 > 1u )
              core::panicking::panic_bounds_check(v213, 512, &off_180343308);
            v209 = byte_1803C9255[v213];
            break;
          case 3:
            v214 = byte_1803C9655[(unsigned int)v210 >> 8];
            if ( v214 >= 0 )
              goto LABEL_256;
            v215 = v214 & 0x7F;
            v216 = (unsigned __int8)v210 | (unsigned int)(v215 << 8);
            if ( (unsigned __int8)v215 > 1u )
              core::panicking::panic_bounds_check(v216, 512, &off_180343320);
            v209 = byte_1803C9455[v216];
            break;
          case 4:
            v209 = 7;
            break;
          case 5:
            v208 = byte_1803C9655[(unsigned int)v210 >> 8];
            if ( v208 >= 0 )
              goto LABEL_256;
            v219 = v208 & 0x7F;
            v220 = (unsigned __int8)v210 | (unsigned int)(v219 << 8);
            if ( (unsigned __int8)v219 > 1u )
              core::panicking::panic_bounds_check(v220, 512, &off_180343338);
            v209 = byte_1803C965D[v220];
            break;
          default:
            if ( (unsigned int)v210 > 0x6FF || *((char *)&word_1803C914E + ((unsigned int)v210 >> 8)) >= 0 )
              goto LABEL_256;
            v217 = *((_BYTE *)&word_1803C914E + ((unsigned int)v210 >> 8)) & 0x7F;
            v218 = (unsigned int)(unsigned __int8)v210 | ((_DWORD)v217 << 8);
            if ( v217 )
              core::panicking::panic_bounds_check(v218, 256, &off_1803432F0);
            v209 = byte_1803C9155[v218];
            break;
        }
      }
    }
    *(_BYTE *)(v64 + 4 * m + 3) = v209;
  }
  v171 = v58;
  LOBYTE(v38) = v566;
  v170 = v580;
  v65 = v574;
LABEL_276:
  v556 = v65;
  v557 = (LPVOID)v64;
  v558 = v171;
  if ( !(_BYTE)v38 && v60 )
  {
    v580 = v170;
    v221 = v60 - 1;
    v222 = *a9;
    v223 = a9[1];
    v224 = a9[2];
    v225 = a9[10];
    v226 = a9[9];
    v227 = 0;
    v228 = v221;
    while ( 1 )
    {
      if ( __OFSUB__(-v222, 1) )
      {
        if ( v227 >= v225 )
          core::panicking::panic_bounds_check(v227, v225, &off_180341210);
        v229 = *(unsigned __int16 *)(v226 + 2 * v227);
      }
      else
      {
        if ( v227 >= v224 )
          core::panicking::panic_bounds_check(v227, v224, &off_1803411F8);
        v229 = *(_DWORD *)(v223 + 4 * v227);
        if ( v229 > 0x10EFF )
          goto LABEL_294;
      }
      v230 = *((_BYTE *)&word_1803C6496 + (v229 >> 8));
      if ( v230 >= 0 )
      {
        v64 = (__int64)v582;
        goto LABEL_294;
      }
      v231 = v230 & 0x7F;
      v232 = (unsigned __int8)v229 | (unsigned int)(v231 << 8);
      if ( (unsigned __int8)v231 >= 6u )
        core::panicking::panic_bounds_check(v232, 1536, &off_1803431E8);
      v64 = (__int64)v582;
      if ( (unsigned __int8)(byte_1803C65A5[v232] - 6) > 0xCu )
        goto LABEL_294;
      if ( v221 >= v171 )
        core::panicking::panic_bounds_check(v221, v171, &off_18033CD18);
      v233 = *((_WORD *)v582 + 2 * v228);
      if ( (v233 & 0x18) == 0 )
      {
        *((_WORD *)v582 + 2 * v228) = v233 | 0x18;
        ++v580;
      }
      v74 = v228-- == 0;
      if ( v74 )
        break;
      ++v227;
    }
    v228 = 0;
LABEL_294:
    v234 = -1;
    v235 = 0;
    v236 = 0;
    v60 = v583;
    while ( 2 )
    {
      v236 += v235 < v228;
      if ( v235 >= v171 )
        core::panicking::panic_bounds_check(v235, v171, &off_18033CD30);
      v237 = *(_WORD *)(v64 + 4 * v235);
      if ( (v237 & 0x10) != 0 && (v237 & 8) != 0 && v234 != -1 )
      {
        v243 = *(_DWORD *)(v584 + 4 * v235);
        v244 = *(_DWORD *)(v64 + 4 * v235);
        v245 = v235;
        if ( (__int64)v235 > v234 )
        {
          do
          {
            v246 = v245 - 1;
            if ( v245 - 1 >= v58 )
              core::panicking::panic_bounds_check(v245 - 1, v58, &off_18033CD78);
            *(_DWORD *)(v584 + 4 * v245) = *(_DWORD *)(v584 + 4 * v245 - 4);
            v64 = (__int64)v582;
            *((_DWORD *)v582 + v245) = *((_DWORD *)v582 + v245 - 1);
            --v245;
          }
          while ( v246 > v234 );
        }
        if ( v234 >= v58 )
          core::panicking::panic_bounds_check(v234, v58, &off_18033CD60);
        *(_DWORD *)(v584 + 4 * v234) = v243;
        *(_DWORD *)(v64 + 4 * v234++) = v244;
        goto LABEL_311;
      }
      if ( v235 >= v58 )
        core::panicking::panic_bounds_check(v235, v58, &off_18033CD48);
      v238 = *(unsigned int *)(v584 + 4 * v235);
      v239 = v235;
      if ( v238 <= 0x10EFF )
      {
        v240 = *((_BYTE *)&word_1803C6496 + ((unsigned int)v238 >> 8));
        v239 = v235;
        if ( v240 < 0 )
        {
          v241 = v240 & 0x7F;
          v242 = (unsigned __int8)v238 | (unsigned __int64)(unsigned int)(v241 << 8);
          if ( (unsigned __int8)v241 > 5u )
            core::panicking::panic_bounds_check(v242, 1536, &off_1803431E8);
          if ( (unsigned __int8)(byte_1803C65A5[v242] - 6) >= 0xDu )
            v234 = v235;
LABEL_311:
          v239 = v234;
        }
      }
      if ( v235 >= v228 || (v234 = v239, v235 = v236, v236 > v228) )
      {
        v170 = v580;
        break;
      }
      continue;
    }
  }
  if ( !v170 )
    core::panicking::panic(
      "assertion failed: num_shapes > 0assertion failed: chars.len() <= glyphs.len()rust\\shaping\\src\\engine\\common_legacy.rs",
      32,
      &off_18033CE50);
  if ( v170 > v60 )
  {
    if ( v170 > a12 )
    {
      v247 = 0xFFFFFFFE00000001uLL;
      goto LABEL_372;
    }
    v248 = (char *)(v170 - v58);
    v580 = v170;
    if ( v170 <= v58 )
    {
      v253 = v170;
      v252 = v584;
    }
    else
    {
      v249 = v58;
      if ( v248 > (char *)v560[0] - v58 )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2(
          (unsigned int)v560,
          v58,
          (_DWORD)v248,
          4,
          4);
        v584 = (unsigned __int64)v560[1];
        v249 = v561;
        v60 = v583;
      }
      v250 = v584;
      v251 = (_DWORD *)(v584 + 4 * v249);
      v170 = v580;
      if ( (unsigned __int64)v248 >= 2 )
      {
        memset_0(v251, 0, 4 * (v580 + ~v58));
        v251 = (_DWORD *)(v250 + 4 * (v249 + v580 - v58) - 4);
        v170 = v580;
        v249 = (__int64)&v248[v249 - 1];
      }
      v252 = v250;
      *v251 = 0;
      v253 = v249 + 1;
      v171 = v558;
    }
    v561 = v253;
    v254 = v170 - v171;
    if ( v170 <= v171 )
    {
      v255 = v557;
      v256 = v170;
    }
    else
    {
      if ( v254 > v556 - v171 )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2(
          (unsigned int)&v556,
          v171,
          v254,
          2,
          4);
        v171 = v558;
        v60 = v583;
      }
      v255 = v557;
      memset_0((char *)v557 + 4 * v171, 0, 4 * v254);
      v256 = v254 + v171;
      v170 = v580;
    }
    v558 = v256;
    v257 = v170;
    do
    {
      v258 = v60 - 1;
      if ( v60 - 1 < v257 )
      {
        v259 = -1;
        v260 = -1;
        v261 = v60 - 1;
        do
        {
          if ( v258 >= v256 )
            core::panicking::panic_bounds_check(v261, v256, &off_18033E7F8);
          v262 = v260;
          v263 = v259;
          v264 = v261 - 1;
          if ( !v261 )
            break;
          v265 = v255[2 * v261] & 8;
          ++v260;
          --v259;
          --v261;
        }
        while ( !v265 );
        v266 = v262 + 2;
        v267 = v257 - v266;
        if ( v264 + 1 < v60 && v267 < v257 )
        {
          if ( !v266 )
            goto LABEL_656;
          v268 = v257 - 1;
          v269 = v60 - 1;
          v270 = v268;
          v271 = v263;
          do
          {
            if ( v269 >= v253 )
              core::panicking::panic_bounds_check(v269, v253, &off_18033E840);
            if ( v270 >= v253 )
              core::panicking::panic_bounds_check(v270, v253, &off_18033E858);
            *(_DWORD *)(v252 + 4 * v270--) = *(_DWORD *)(v252 + 4 * v269--);
            ++v271;
          }
          while ( v271 );
          do
          {
            if ( v258 >= v256 )
              core::panicking::panic_bounds_check(v258, v256, &off_18033E810);
            if ( v268 >= v256 )
              core::panicking::panic_bounds_check(v268, v256, &off_18033E828);
            *(_DWORD *)&v255[2 * v268--] = *(_DWORD *)&v255[2 * v258--];
            ++v263;
          }
          while ( v263 );
        }
        if ( v266 )
          goto LABEL_350;
      }
LABEL_656:
      core::panicking::panic("assertion failed: copy_size > 0rust\\shaping\\src\\engine\\arabic.rs", 31, &off_18033CCA0);
LABEL_350:
      if ( !v267 )
        break;
      if ( v267 >= v256 )
        core::panicking::panic_bounds_check(v267, v256, &off_18033CCB8);
      v272 = v255[2 * v267];
      if ( (v272 & 0x10) != 0 )
      {
        v257 = v267 - 1;
        if ( v267 - 1 > v253 )
          core::slice::index::slice_start_index_len_fail(v257, v253, &off_18033CCD0);
        if ( v267 - 1 == v253 )
          core::panicking::panic_bounds_check(0, 0, &off_18033E7E0);
        *(_DWORD *)(v252 + 4 * v267 - 4) = 9676;
        LOBYTE(v255[2 * v267 - 1]) = v255[2 * v267 + 1];
        v255[2 * v267 - 2] = v272 & 0xFFE5 | 0x18;
        HIBYTE(v255[2 * v267 - 1]) = 0;
        v255[2 * v267] = v272 & 0xFFE6;
        LOBYTE(v255[2 * v267 + 1]) = 0;
      }
      else
      {
        v257 = v267;
      }
      v60 -= v266;
    }
    while ( v257 );
    v60 = v580;
  }
  v273 = a7;
  if ( a8 )
  {
    v274 = 0;
    v275 = 0;
    while ( 1 )
    {
      v275 += a7[v274][1];
      if ( v275 > 0xFFF9 )
        break;
      if ( a8 == ++v274 )
      {
        v276 = v275 + 6;
        goto LABEL_363;
      }
    }
    v247 = 0xFFFFFFFF00000001uLL;
LABEL_372:
    *(_QWORD *)v573 = v247;
    goto LABEL_373;
  }
  v276 = 6;
LABEL_363:
  if ( v276 <= v60 )
    v276 = v60;
  v277 = 12 * v276;
  if ( (0xC * (unsigned __int128)v276) >> 64 != 0 || 12 * v276 > 0x7FFFFFFFFFFFFFFCLL )
  {
    v278 = 0;
    goto LABEL_367;
  }
  if ( v277 )
  {
    v279 = std::sys::alloc::windows::process_heap_alloc(0, 12 * v276);
    if ( !v279 )
    {
      v278 = 4;
      v277 = 12 * v276;
LABEL_367:
      alloc::raw_vec::handle_error(v278, v277, &off_18033CE68);
    }
  }
  else
  {
    v279 = 4;
    v276 = 0;
  }
  v563 = (char *)v276;
  v564[0] = (LPVOID)v279;
  v564[1] = 0;
  v286 = *(_DWORD *)v568;
  v552 = *(_DWORD *)v568 != 0;
  v528[0] = v572;
  v528[1] = v559;
  v529 = 1;
  v530 = v286 != 0;
  v544 = 0;
  otls::resource::ResourceMgr::init(
    (char *)&v509,
    v528,
    (__int64)&v544,
    (int *)"GDEFGSUBrust\\otls\\src\\resource.rs",
    2);
  v287 = v509;
  v288 = Src.m128i_i32[0];
  if ( v509 == 4 )
  {
    v289 = -1000;
    if ( Src.m128i_i32[0] == 258 )
      v289 = -200;
    v290 = -4;
    if ( Src.m128i_i32[0] != 257 )
      v290 = v289;
    v291 = (_DWORD *)v573;
    *(_DWORD *)(v573 + 4) = v290;
    *v291 = 1;
    goto LABEL_390;
  }
  memcpy_0((char *)&v494.m128i_u64[1] + 4, (char *)Src.m128i_i64 + 4, 0x56Cu);
  v494.m128i_i64[0] = v287;
  v494.m128i_i32[2] = v288;
  v542 = 0;
  v543 = 0;
  v294 = (char *)&off_180341570 + (unsigned int)(32 * v578);
  v540[2] = 0;
  v541 = 0;
  v295 = *(_DWORD *)(v568 + 8);
  if ( ((unsigned __int8)v294[25] | (v295 == 0)) == 1 )
    v295 = *((_DWORD *)v294 + 4);
  v540[0] = v295;
  v296 = *(_DWORD *)(v568 + 12);
  if ( ((unsigned __int8)v294[26] | (v296 == 1953261156)) == 1 )
    v296 = *((_DWORD *)v294 + 5);
  v540[1] = v296;
  v297 = 8 * a12;
  if ( a12 >> 61 != 0 || 8 * a12 > 0x7FFFFFFFFFFFFFFELL )
  {
    v298 = 0;
    goto LABEL_401;
  }
  v582 = v560[1];
  v299 = v561;
  if ( v297 )
  {
    v300 = v561;
    v301 = std::sys::alloc::windows::process_heap_alloc(0, v297);
    v299 = v300;
    v302 = a12;
    if ( !v301 )
    {
      v298 = 2;
      v297 = 8 * a12;
LABEL_401:
      alloc::raw_vec::handle_error(v298, v297, &off_18033CD90);
    }
  }
  else
  {
    v301 = 2;
    v302 = 0;
  }
  v570 = v302;
  v309 = v301;
  v571 = (unsigned __int64)v301;
  v310 = (__int64 (__fastcall **)(int, int, int, int, int))(2 * v299);
  if ( v299 < 0 || (unsigned __int64)(2 * v299) > 0x7FFFFFFFFFFFFFFELL )
  {
    v311 = 0;
    goto LABEL_413;
  }
  if ( v310 )
  {
    v584 = 2 * v299;
    v312 = v299;
    v313 = std::sys::alloc::windows::process_heap_alloc(0, v310);
    v299 = v312;
    v314 = v313;
    v315 = v312;
    if ( !v313 )
    {
      v311 = 2;
      v310 = (__int64 (__fastcall **)(int, int, int, int, int))v584;
LABEL_413:
      v536 = v302;
      alloc::raw_vec::handle_error(v311, v310, &off_18033CDA8);
    }
  }
  else
  {
    v314 = 2;
    v315 = 0;
  }
  v575 = v294;
  LODWORD(v581) = v286;
  v583 = v60;
  v509 = v315;
  Src = (__m128i)(unsigned __int64)v314;
  if ( v299 )
  {
    LOBYTE(v577) = (*(_BYTE *)(v568 + 24) ^ 1) & (unsigned __int8)v577;
    v574 = v559[6];
    v580 = 4 * v299;
    v331 = 0;
    v332 = 0;
    v333 = 0;
    v334 = 0;
    v299 = v309;
    do
    {
      v335 = *(_DWORD *)((char *)v582 + v332);
      if ( v335 == 847 && v334 )
      {
        ++*(_WORD *)(v299 + 8 * v334 - 2);
        v336 = Src.m128i_i64[1];
        v314 = Src.m128i_i64[0];
        v337 = Src.m128i_i64[0] + 2 * Src.m128i_i64[1];
        v134 = v337 == 2;
        v338 = (__int16 *)(v337 - 2);
        LOBYTE(v310) = Src.m128i_i64[1] == 0 || v134;
        if ( (_BYTE)v310 )
          v339 = 0;
        else
          v339 = *v338;
        if ( Src.m128i_i64[1] == v509 )
        {
          v344 = v299;
          alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(&v509, &off_18033CDF0);
          v314 = Src.m128i_i64[0];
          v299 = v344;
        }
        *(_WORD *)(v314 + 2 * v336) = v339;
        v333 = v336 + 1;
        Src.m128i_i64[1] = v333;
      }
      else
      {
        v584 = v333;
        if ( v333 == v509 )
        {
          alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(&v509, &off_18033CDC0);
          v314 = Src.m128i_i64[0];
        }
        v340 = v314;
        v341 = v584;
        *(_WORD *)(v314 + 2 * v584) = v334;
        v333 = v341 + 1;
        Src.m128i_i64[1] = v341 + 1;
        LODWORD(v533[0]) = v335;
        LODWORD(v537[0]) = 0;
        LOWORD(v554) = 0;
        LODWORD(v309) = _guard_dispatch_icall_fptr();
        if ( (_DWORD)v309 )
        {
          if ( v509 )
          {
            v378 = (void *)Src.m128i_i64[0];
            v379 = GetProcessHeap();
            HeapFree(v379, 0, v378);
          }
          if ( v570 )
          {
            v380 = (void *)v571;
            v381 = GetProcessHeap();
            HeapFree(v381, 0, v380);
          }
LABEL_499:
          v382 = (_DWORD *)v573;
          *(_DWORD *)(v573 + 4) = v309;
          *v382 = 1;
LABEL_606:
          core::ptr::drop_in_place_otls::resource::ResourceMgr_(&v494, v310);
LABEL_390:
          if ( v544 && !_InterlockedDecrement64(v544) )
            alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
              v544,
              v545);
          if ( v563 )
          {
            v292 = v564[0];
            v293 = GetProcessHeap();
            HeapFree(v293, 0, v292);
          }
LABEL_373:
          if ( v556 )
          {
            v280 = v557;
            v281 = GetProcessHeap();
            HeapFree(v281, 0, v280);
          }
          if ( v560[0] )
          {
            v282 = v560[1];
            v283 = GetProcessHeap();
            HeapFree(v283, 0, v282);
          }
          v284 = v576;
          if ( !_InterlockedDecrement64(v576) )
            goto LABEL_378;
          goto LABEL_379;
        }
        v342 = (unsigned __int16)v554;
        v343 = *((_QWORD *)&v571 + 1);
        if ( *((_QWORD *)&v571 + 1) == v570 )
          alloc::raw_vec::RawVec_otls::GlyphInfo_alloc::alloc::Global_::grow_one_otls::GlyphInfo_alloc::alloc::Global_(
            &v570,
            &off_18033CDD8);
        v299 = v571;
        *(_QWORD *)(v571 + 8 * v343) = v342 | v331 & 0xFFFF00000000LL | 0x10000000F0000LL;
        v334 = v343 + 1;
        *((_QWORD *)&v571 + 1) = v334;
        v314 = v340;
      }
      v332 += 4;
      v331 += 0x100000000LL;
    }
    while ( v580 != v332 );
    v315 = v509;
    v314 = Src.m128i_i64[0];
    v302 = v570;
    LODWORD(v309) = v571;
    v546.m128i_i64[0] = *(_QWORD *)((char *)&v571 + 4);
    v546.m128i_i32[2] = HIDWORD(v571);
    if ( __OFSUB__(-v570, 1) )
      goto LABEL_499;
  }
  else
  {
    v546.m128i_i32[2] = HIDWORD(v571);
    v546.m128i_i64[0] = *(_QWORD *)((char *)&v571 + 4);
    v333 = 0;
  }
  v584 = v333;
  v580 = v315;
  v582 = (LPVOID)v314;
  HIDWORD(v555) = v546.m128i_i32[2];
  *(_QWORD *)((char *)&v555 + 4) = v546.m128i_i64[0];
  v554 = v302;
  LODWORD(v555) = v309;
  v345 = v564[1];
  if ( v564[1] == v563 )
    alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_(
      &v563,
      &off_18033CE80,
      v299);
  v346 = v564[0];
  v347 = 3LL * (_QWORD)v345;
  *(_QWORD *)((char *)v564[0] + 4 * v347) = 0x1706D6363LL;
  v346[2 * v347 + 4] = 0;
  v346[2 * v347 + 5] = v583;
  v564[1] = (char *)v345 + 1;
  if ( (char *)v345 + 1 == v563 )
    alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_(
      &v563,
      &off_18033CE98,
      v299);
  v348 = v564[0];
  v349 = 3LL * ((_QWORD)v345 + 1);
  *(_QWORD *)((char *)v564[0] + 4 * v349) = 0x16C636F6CLL;
  v348[2 * v349 + 4] = 0;
  v350 = v583;
  v348[2 * v349 + 5] = v583;
  v564[1] = (char *)v345 + 2;
  v533[0] = v564[0];
  v533[1] = (char *)v345 + 2;
  v534 = 0;
  v535 = v350;
  LODWORD(v577) = *((_DWORD *)v575 + 5);
  v351 = shaping::engine::helpers::substitute_otl_glyphs_with_fallback(
           (unsigned int)v540,
           (unsigned int)&v494,
           (unsigned int)v533,
           (_DWORD)v582,
           v584,
           (__int64)&v554,
           1414284868,
           (_DWORD)v577);
  v352 = 0;
  if ( v351 >= 0x200 )
    v352 = v351;
  v353 = -1000;
  if ( v352 )
    goto LABEL_601;
  v564[1] = 0;
  if ( v583 > v558 )
    core::slice::index::slice_end_index_len_fail(v583, v558, &off_18033CEB0);
  v575 = &a7[a8];
  v354 = (char *)v557;
  v355 = (char *)v557 + 4 * v583;
  v356 = 0;
  v357 = "isolisolinitmedimed2finafin2fin3isolrust\\shaping\\src\\engine\\arabic\\fsm.rs";
  v358 = 0;
  v359 = v578;
  v360 = v584;
  while ( v354 != v355 )
  {
    v361 = v358++;
    v362 = (unsigned __int8)v354[2];
    v354 += 4;
    if ( (unsigned __int8)(v362 - 8) >= 0xF9u && (v362 != 1 || v359 != 23) )
    {
      v363 = v357;
      LODWORD(v574) = *(_DWORD *)&v357[4 * v362];
      if ( v356 == v563 )
        alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ScriptRun__alloc::alloc::Global_(
          &v563,
          &off_18033D138,
          (unsigned int)(v362 - 8));
      v364 = v564[0];
      v365 = 3LL * (_QWORD)v356;
      *((_DWORD *)v564[0] + v365) = v574;
      v364[v365 + 1] = 1;
      LOWORD(v364[v365 + 2]) = v361;
      HIWORD(v364[v365 + 2]) = 1;
      v564[1] = ++v356;
      v359 = v578;
      v360 = v584;
      v357 = v363;
    }
  }
  v537[0] = v564[0];
  v537[1] = v356;
  v538 = 0;
  v539 = v583;
  v383 = shaping::engine::helpers::substitute_otl_glyphs_with_fallback(
           (unsigned int)v540,
           (unsigned int)&v494,
           (unsigned int)v537,
           (_DWORD)v582,
           v360,
           (__int64)&v554,
           1414284868,
           (_DWORD)v577);
  v384 = 0;
  if ( v383 >= 0x200 )
    v384 = v383;
  v310 = &off_180341570;
  v353 = -1000;
  if ( v384 )
    goto LABEL_601;
  v564[1] = 0;
  v385 = *(__int64 *)((char *)&off_180341570 + (unsigned int)(32 * v578) + 8);
  v509 = v568;
  Src.m128i_i64[0] = v385;
  Src.m128i_i64[1] = (__int64)&v563;
  v511 = 0;
  shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(&v563, 1734962290, v583);
  if ( (_DWORD)v581 != 2 )
    shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(&v563, 1953260402, v583);
  if ( (unsigned int)shaping::engine::universal::feature_collector::Collector::add_user_features(
                       (unsigned int)&v509,
                       a5,
                       a6,
                       (_DWORD)a7,
                       a8,
                       v583,
                       (__int64)&v552) )
  {
    *(_QWORD *)v573 = 0xFFFFFFFF00000001uLL;
LABEL_602:
    if ( v580 )
    {
      v433 = GetProcessHeap();
      HeapFree(v433, 0, v582);
    }
    if ( v554 )
    {
      v434 = (void *)v555;
      v435 = GetProcessHeap();
      HeapFree(v435, 0, v434);
    }
    goto LABEL_606;
  }
  v353 = shaping::engine::universal::feature_collector::Collector::add_reading_direction_features(&v509, v552, v583);
  if ( v353 )
    goto LABEL_601;
  if ( a8 )
  {
    v416 = a7 + 1;
    v417 = 0;
    do
    {
      v418 = *v273;
      v273 = v416;
      v419 = *v418;
      v420 = 8 * v418[1];
      v421 = 0;
      while ( v420 != v421 )
      {
        v134 = *(_DWORD *)(v419 + v421) == 1634167148;
        v421 += 8;
        if ( v134 )
        {
          v417 = 1;
          break;
        }
      }
      v416 = &v273[v273 != v575];
    }
    while ( v273 != v575 );
  }
  else
  {
    v417 = 0;
  }
  v422 = Src.m128i_i64[1];
  shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(Src.m128i_i64[1], 1953259875, v583);
  if ( (v417 & 1) == 0 )
    shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(v422, 1634167148, v583);
  shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(v422, 1952805741, v583);
  shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(v422, 1751348339, v583);
  shaping::engine::universal::feature_collector::Collector::add_single_feature_tag(v422, 1852995186, v583);
  v546 = _mm_loadu_si128((const __m128i *)v564);
  v547 = 0;
  v548 = v583;
  v423 = shaping::engine::helpers::substitute_otl_glyphs_with_fallback(
           (unsigned int)v540,
           (unsigned int)&v494,
           (unsigned int)&v546,
           (_DWORD)v582,
           v584,
           (__int64)&v554,
           1414284868,
           (_DWORD)v577);
  v424 = 0;
  if ( v423 >= 0x200 )
    v424 = v423;
  v353 = -1000;
  if ( v424
    || (v353 = -100, v583 - 0x10000 < 0xFFFFFFFFFFFF0001uLL)
    || (v425 = _mm_loadu_si128((const __m128i *)&v560[1]),
        (v353 = shaping::stretch::shape_stretch_glyphs(
                  v572,
                  v559[8],
                  v581,
                  v569,
                  v425.m128i_i64[0],
                  v425.m128i_i64[1],
                  v583,
                  (__int64)&v554,
                  (__int64)v582,
                  v584,
                  a12)) != 0) )
  {
LABEL_601:
    v432 = (_DWORD *)v573;
    *(_DWORD *)(v573 + 4) = v353;
    *v432 = 1;
    goto LABEL_602;
  }
  v577 = v557;
  v578 = v558;
  v426 = 0;
  v427 = 0;
  v428 = 0;
  while ( 1 )
  {
    v429 = v426;
    if ( v426 >= v583 )
      break;
    if ( v426 >= v578 )
      core::panicking::panic_bounds_check(v426, v578, &off_18033D0C0);
    ++v426;
    v430 = v577[2 * v429];
    if ( (v430 & 8) != 0 )
    {
      ++v427;
      if ( (v430 & 0x10) != 0 )
      {
        if ( v429 >= v584 )
          core::panicking::panic_bounds_check(v429, v584, &off_18033D120);
        v428 = *((_WORD *)v582 + v429);
      }
    }
    else
    {
      if ( (v430 & 2) != 0 )
      {
        v431 = (_WORD *)shaping::string::impl_7::index_u16_(a10, v429 - v427, &off_18033D108);
      }
      else
      {
        if ( v429 >= v584 )
          core::panicking::panic_bounds_check(v429, v584, &off_18033D0D8);
        v428 = *((_WORD *)v582 + v429);
        v431 = (_WORD *)shaping::string::impl_7::index_u16_(a10, v429 - v427, &off_18033D0F0);
      }
      *v431 = v428;
    }
  }
  v581 = *((_QWORD *)&v555 + 1);
  if ( !*((_QWORD *)&v555 + 1) )
    core::panicking::panic("assertion failed: num_glyphs > 0", 32, &off_18033CEC8);
  if ( v581 > a12 )
    core::panicking::panic(
      "assertion failed: num_glyphs <= max_glyphsassertion failed: num_glyphs > 0",
      42,
      &off_18033CEE0);
  if ( !(_BYTE)v566 )
  {
    alloc::vec::spec_from_elem::impl_1::from_elem_u16_alloc::alloc::Global_(&v570, v583);
    v436 = v583 - v427;
    v437 = v583 - v427 - 1;
    lpMem = (LPVOID)*((_QWORD *)&v571 + 1);
    v575 = (LPVOID)v571;
    v438 = 0;
    v439 = v581;
LABEL_637:
    v553 = v437 + 1;
    v574 = v438;
    while ( 1 )
    {
      v551 = v439 - 1;
      if ( v574 >= v436 )
        break;
      v440 = *(_WORD *)shaping::string::impl_7::index_u16_(a10, v574, &off_18033CF10);
      v562 = v440;
      v441 = 1;
      v438 = v574;
      while ( 1 )
      {
        if ( ++v438 >= v436 )
        {
          v442 = v581;
          goto LABEL_647;
        }
        if ( v440 != *(_WORD *)shaping::string::impl_7::index_u16_(a10, v438, &off_18033CF28) )
          break;
        ++v441;
      }
      if ( *(_WORD *)shaping::string::impl_7::index_u16_(a10, v438, &off_18033CF40) < v440 )
        break;
      v443 = (unsigned __int16 *)shaping::string::impl_7::index_u16_(a10, v438, &off_18033CF58);
      if ( v581 <= *v443 )
        break;
      v442 = *(unsigned __int16 *)shaping::string::impl_7::index_u16_(a10, v438, &off_18033CF70);
LABEL_647:
      v439 = v562 + v439 - v442;
      if ( v439 < 0 )
      {
        v551 = v439;
        break;
      }
      if ( (__int64)(v553 - v441) < 0 )
        goto LABEL_687;
      v574 = v438;
      if ( v441 > 0 )
      {
        do
        {
          if ( v437 >= (unsigned __int64)lpMem )
            core::panicking::panic_bounds_check(v437, lpMem, &off_18033CF88);
          *((_WORD *)v575 + v437--) = v439;
          --v441;
        }
        while ( v441 );
        goto LABEL_637;
      }
    }
    if ( v574 >= v436 && (v551 & v437) == 0xFFFFFFFFFFFFFFFFuLL )
    {
      for ( n = 0; n < v436; *v447 = v446 )
      {
        if ( n >= (unsigned __int64)lpMem )
          core::panicking::panic_bounds_check(n, lpMem, &off_18033CFA0);
        v446 = *((_WORD *)v575 + n);
        v447 = (_WORD *)shaping::string::impl_7::index_u16_(a10, n++, &off_18033CFB8);
      }
    }
LABEL_687:
    if ( v570 )
    {
      v448 = GetProcessHeap();
      HeapFree(v448, 0, v575);
    }
  }
  is_gsub_feature_in_font = shaping::engine::helpers::is_gsub_feature_in_font(v572, v559);
  v451 = *((_QWORD *)&v555 + 1);
  v450 = v555;
  v452 = *(_BYTE *)(v568 + 23);
  v453 = v560[1];
  v454 = v561;
  v455 = 0;
  while ( 2 )
  {
    if ( v451 == v455 )
      core::panicking::panic_bounds_check(v451, v451, &off_18033D000);
    v456 = *(_WORD *)(v450 + 8 * v455 + 2);
    v457 = 96;
    if ( (v456 & 0xF) != 3 )
      v457 = 0;
    v458 = *(_WORD *)(v450 + 8 * v455 + 6);
    v459 = *(unsigned __int16 *)(v450 + 8 * v455 + 4);
    v460 = v457 + 2 * (v456 & 0x40);
    if ( v458 )
    {
      if ( v578 <= v459 )
        core::panicking::panic_bounds_check(v459, v578, &off_18033D018);
      v461 = v577[2 * v459];
      if ( (v461 & 2) == 0 )
        goto LABEL_698;
    }
    if ( v578 <= v459 )
      core::panicking::panic_bounds_check(v459, v578, &off_18033D030);
    v461 = v577[2 * v459];
    if ( (v461 & 0x10) != 0 )
    {
LABEL_698:
      if ( v578 <= v459 )
        core::panicking::panic_bounds_check(v459, v578, &off_18033D048);
      v460 |= 0x10u;
      v462 = HIBYTE(v577[2 * v459 + 1]);
      if ( v462 != 14 || v458 == 1 )
        v460 |= v462;
    }
    if ( a14 == v455 )
      core::panicking::panic_bounds_check(a14, a14, &off_18033D060);
    *(_WORD *)(a13 + 2 * v455) = *(_WORD *)(v450 + 8 * v455);
    if ( (v452 & 1) == 0 )
    {
      v463 = v583 + ~v459;
      if ( (_BYTE)v566 )
        v463 = v459;
      if ( v463 >= v454 )
        core::panicking::panic_bounds_check(v463, v454, &off_18033D078);
      v464 = v453[v463];
      if ( v464 > 8202 )
      {
        if ( (unsigned int)(v464 - 8203) < 5 || v464 == 65279 )
          goto LABEL_712;
      }
      else
      {
        if ( v464 > 6154 )
        {
          if ( (unsigned int)(v464 - 6155) >= 4 )
            goto LABEL_714;
LABEL_712:
          *(_WORD *)(a13 + 2 * v455) = *(_WORD *)(v569 + 146);
LABEL_713:
          v460 |= 0x40u;
          goto LABEL_714;
        }
        if ( v464 == 847 || v464 == 1564 )
          goto LABEL_712;
        if ( v464 == 1807 )
          goto LABEL_713;
      }
    }
LABEL_714:
    if ( is_gsub_feature_in_font )
    {
      if ( v578 <= v459 )
        core::panicking::panic_bounds_check(v459, v578, &off_18033D090);
      v460 |= (32 * (_BYTE)v461) & 0x40;
    }
    if ( a16 == v455 )
      core::panicking::panic_bounds_check(a16, a16, &off_18033D0A8);
    *(_WORD *)(a15 + 2 * v455++) = v460;
    if ( v581 != v455 )
      continue;
    break;
  }
  shaping::engine::helpers::encode_char_map(v581, v450, v451, v583, (__int64)v582, v584, a15, a16, a11);
  if ( (_BYTE)v566 )
    goto LABEL_746;
  if ( v581 > a14 )
    core::slice::index::slice_end_index_len_fail(v581, a14, &off_18033CFD0);
  if ( v581 != 1 )
  {
    v466 = v581 >> 1;
    if ( v581 >= 0x10 )
    {
      v467 = v466 & 0x7FFFFFFFFFFFFF8LL;
      v468 = (__m128i *)(a13 + 2 * v581 - 16);
      v469 = v581 & 0xFFFFFFFFFFFFFFF0uLL;
      v470 = 0;
      do
      {
        v471 = _mm_loadu_si128((const __m128i *)(a13 + v470));
        *(__m128i *)(a13 + v470) = _mm_shufflehi_epi16(
                                     _mm_shufflelo_epi16(_mm_shuffle_epi32(_mm_loadu_si128(v468), 78), 27),
                                     27);
        *v468-- = _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_shuffle_epi32(v471, 78), 27), 27);
        v470 += 16;
      }
      while ( v469 != v470 );
      if ( v466 == v467 )
      {
LABEL_738:
        if ( v581 > a16 )
          goto LABEL_793;
        if ( v581 >= 0x10 )
        {
          v476 = v466 & 0x7FFFFFFFFFFFFF8LL;
          v465 = (__m128i *)(a15 + 2 * v581 - 16);
          v477 = v581 & 0xFFFFFFFFFFFFFFF0uLL;
          v478 = 0;
          do
          {
            v479 = _mm_loadu_si128((const __m128i *)(a15 + v478));
            *(__m128i *)(a15 + v478) = _mm_shufflehi_epi16(
                                         _mm_shufflelo_epi16(_mm_shuffle_epi32(_mm_loadu_si128(v465), 78), 27),
                                         27);
            *v465-- = _mm_shufflehi_epi16(_mm_shufflelo_epi16(_mm_shuffle_epi32(v479, 78), 27), 27);
            v478 += 16;
          }
          while ( v477 != v478 );
          if ( v466 == v476 )
            goto LABEL_746;
        }
        else
        {
          v476 = 0;
        }
        v480 = -(__int64)v466;
        v465 = (__m128i *)(a15 + 2 * v476);
        v481 = -v476;
        v482 = a15 + 2 * v581 - 2;
        do
        {
          v483 = v465->m128i_i16[0];
          v465->m128i_i16[0] = *(_WORD *)(v482 + 2 * v481);
          *(_WORD *)(v482 + 2 * v481--) = v483;
          v465 = (__m128i *)((char *)v465 + 2);
        }
        while ( v480 != v481 );
        goto LABEL_746;
      }
    }
    else
    {
      v467 = 0;
    }
    v472 = (__int16 *)(a13 + 2 * v467);
    v473 = -v467;
    v474 = a13 + 2 * v581 - 2;
    do
    {
      v475 = *v472;
      *v472 = *(_WORD *)(v474 + 2 * v473);
      *(_WORD *)(v474 + 2 * v473--) = v475;
      ++v472;
    }
    while ( -(__int64)v466 != v473 );
    goto LABEL_738;
  }
  if ( !a16 )
LABEL_793:
    core::slice::index::slice_end_index_len_fail(v581, a16, &off_18033CFE8);
LABEL_746:
  v484 = (_DWORD *)v573;
  *(_QWORD *)(v573 + 8) = v581;
  *v484 = 0;
  if ( v580 )
  {
    v485 = GetProcessHeap();
    HeapFree(v485, 0, v582);
  }
  if ( v554 )
  {
    v486 = (void *)v555;
    v487 = GetProcessHeap();
    HeapFree(v487, 0, v486);
  }
  core::ptr::drop_in_place_otls::resource::ResourceMgr_(&v494, v465);
  if ( v544 && !_InterlockedDecrement64(v544) )
    alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
      v544,
      v545);
  if ( v563 )
  {
    v488 = v564[0];
    v489 = GetProcessHeap();
    HeapFree(v489, 0, v488);
  }
  if ( v556 )
  {
    v490 = v557;
    v491 = GetProcessHeap();
    HeapFree(v491, 0, v490);
  }
  if ( v560[0] )
  {
    v492 = v560[1];
    v493 = GetProcessHeap();
    HeapFree(v493, 0, v492);
  }
  v284 = v576;
  if ( !_InterlockedDecrement64(v576) )
LABEL_378:
    alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
      v284,
      v565);
LABEL_379:
  if ( v549 && !_InterlockedDecrement64(v549) )
    alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
      v549,
      v550);
  return v573;
}

```

## disassembly

```asm
0x1800aef80  push    rbp
0x1800aef81  push    r15
0x1800aef83  push    r14
0x1800aef85  push    r13
0x1800aef87  push    r12
0x1800aef89  push    rsi
0x1800aef8a  push    rdi
0x1800aef8b  push    rbx
0x1800aef8c  sub     rsp, 0D38h
0x1800aef93  lea     rbp, [rsp+80h]
0x1800aef9b  mov     [rbp+0CF0h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800aefa6  mov     rdi, r8
0x1800aefa9  mov     rsi, rdx
0x1800aefac  mov     [rbp+0CF0h+var_A0], rcx
0x1800aefb3  mov     r12, [rbp+0CF0h+arg_78]
0x1800aefba  mov     r15, [rbp+0CF0h+arg_68]
0x1800aefc1  mov     rdx, [rbp+0CF0h+arg_50]
0x1800aefc8  mov     rcx, [rbp+0CF0h+arg_40]
0x1800aefcf  mov     [rbp+0CF0h+var_D0], r9
0x1800aefd6  mov     eax, [r9+4]
0x1800aefda  mov     [rbp+0CF0h+var_78], rax
0x1800aefe1  mov     rax, [rcx+58h]
0x1800aefe5  mov     [rbp+0CF0h+var_50], rax
0x1800aefec  xor     r8d, r8d
0x1800aefef  call    shaping__engine__helpers__set_default_character_properties
0x1800aeff4  mov     [rbp+0CF0h+var_128], rdi
0x1800aeffb  mov     r14, [rdi+60h]
0x1800aefff  lea     rcx, [rbp+0CF0h+var_180]
0x1800af006  mov     [rbp+0CF0h+var_A8], rsi
0x1800af00d  mov     rdx, rsi
0x1800af010  mov     r8, r14
0x1800af013  call    shaping__caching__CacheSlot_shaping__engine__arabic__FontCacheData___init_shaping__engine__arabic__FontCacheData_
0x1800af018  mov     rax, [rbp+0CF0h+var_180]
0x1800af01f  test    rax, rax
0x1800af022  jz      short loc_1800AF093
0x1800af024  mov     rcx, [rbp+0CF0h+var_178]
0x1800af02b  mov     rdx, [rcx+10h]
0x1800af02f  mov     rsi, [rcx+18h]
0x1800af033  dec     rdx
0x1800af036  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800af03a  lea     rbx, [rax+rdx]
0x1800af03e  add     rbx, 10h
0x1800af042  mov     rcx, rbx
0x1800af045  mov     rax, rsi
0x1800af048  call    cs:__guard_dispatch_icall_fptr
0x1800af04e  cmp     rdx, 3
0x1800af052  jbe     loc_1800B2B4E
0x1800af058  cmp     byte ptr [rax+2], 0
0x1800af05c  jz      short loc_1800AF093
0x1800af05e  lea     rdx, [r15+r15]
0x1800af062  test    r15, r15
0x1800af065  sets    al
0x1800af068  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800af072  cmp     rdx, rcx
0x1800af075  setnbe  cl
0x1800af078  or      cl, al
0x1800af07a  jz      loc_1800AF49F
0x1800af080  xor     ecx, ecx
0x1800af082  lea     r8, off_18033CE08; "rust\\shaping\\src\\engine\\arabic.rs"
0x1800af089  call    alloc__raw_vec__handle_error
0x1800af08e  jmp     loc_1800B387F
0x1800af093  lea     rcx, [rbp+0CF0h+var_7A0]
0x1800af09a  mov     rdx, [rbp+0CF0h+var_A8]
0x1800af0a1  mov     r8, r14
0x1800af0a4  call    shaping__caching__CacheSlot_shaping__caching__CommonFontCacheData___init_shaping__caching__CommonFontCacheData_
0x1800af0a9  mov     rdx, [rbp+0CF0h+var_7A0]
0x1800af0b0  test    rdx, rdx
0x1800af0b3  jz      loc_1800AF484
0x1800af0b9  mov     rax, [rbp+0CF0h+Src]
0x1800af0c0  mov     rcx, [rax+10h]
0x1800af0c4  mov     [rbp+0CF0h+var_E8], rax
0x1800af0cb  mov     rax, [rax+18h]
0x1800af0cf  dec     rcx
0x1800af0d2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800af0d6  mov     [rbp+0CF0h+var_88], rdx
0x1800af0dd  add     rcx, rdx
0x1800af0e0  add     rcx, 10h
0x1800af0e4  call    cs:__guard_dispatch_icall_fptr
0x1800af0ea  mov     r12, rax
0x1800af0ed  test    r12b, 3
0x1800af0f1  mov     rdi, [rbp+0CF0h+var_50]
0x1800af0f8  jnz     loc_1800B2C43
0x1800af0fe  cmp     rdx, 0BBh
0x1800af105  jbe     loc_1800B2C47
0x1800af10b  mov     rax, [rbp+0CF0h+var_D0]
0x1800af112  movzx   eax, byte ptr [rax+14h]
0x1800af116  mov     byte ptr [rbp+0CF0h+var_80], al
0x1800af11c  test    al, al
0x1800af11e  mov     [rbp+0CF0h+var_C8], r12
0x1800af125  jnz     loc_1800AF213
0x1800af12b  test    rdi, rdi
0x1800af12e  jz      loc_1800AF213
0x1800af134  mov     rax, [rbp+0CF0h+arg_40]
0x1800af13b  mov     rbx, [rax]
0x1800af13e  mov     r13, [rax+8]
0x1800af142  mov     rsi, [rax+10h]
0x1800af146  mov     r14, [rax+50h]
0x1800af14a  mov     r11, [rax+48h]
0x1800af14e  xor     ecx, ecx
0x1800af150  lea     rdx, byte_1803C6BA5
0x1800af157  lea     r8, dword_1803C6CB4
0x1800af15e  jmp     short loc_1800AF16C
0x1800af160  inc     rcx
0x1800af163  cmp     rdi, rcx
0x1800af166  jz      loc_1800AF213
0x1800af16c  mov     rax, rbx
0x1800af16f  neg     rax
0x1800af172  jno     short loc_1800AF190
0x1800af174  cmp     rcx, r14
0x1800af177  jnb     loc_1800B28CA
0x1800af17d  movzx   eax, word ptr [r11+rcx*2]
0x1800af182  jmp     short loc_1800AF1A5
0x1800af190  cmp     rcx, rsi
0x1800af193  jnb     loc_1800B28B6
0x1800af199  mov     eax, [r13+rcx*4+0]
0x1800af19e  cmp     eax, 10EFFh
0x1800af1a3  ja      short loc_1800AF160
0x1800af1a5  mov     r9d, eax
0x1800af1a8  shr     r9d, 8
0x1800af1ac  movzx   r9d, byte ptr [r9+rdx]
0x1800af1b1  test    r9b, r9b
0x1800af1b4  jns     short loc_1800AF160
0x1800af1b6  movzx   r10d, al
0x1800af1ba  and     r9d, 7Fh
0x1800af1be  mov     eax, r9d
0x1800af1c1  shl     eax, 8
0x1800af1c4  or      eax, r10d
0x1800af1c7  cmp     r9b, 5
0x1800af1cb  jnb     loc_1800B2B05
0x1800af1d1  cmp     byte ptr [rax+r8], 1
0x1800af1d6  jnz     short loc_1800AF160
0x1800af1d8  lea     rdx, ds:0[rdi*4]
0x1800af1e0  mov     rax, rdi
0x1800af1e3  shr     rax, 3Eh
0x1800af1e7  setz    al
0x1800af1ea  mov     rcx, 7FFFFFFFFFFFFFFDh
0x1800af1f4  cmp     rdx, rcx
0x1800af1f7  setb    cl
0x1800af1fa  test    al, cl
0x1800af1fc  jnz     loc_1800B0372
0x1800af202  lea     rcx, off_18033CCE8; "rust\\shaping\\src\\engine\\arabic.rs"
0x1800af209  call    alloc__raw_vec__capacity_overflow
0x1800af20e  jmp     loc_1800B387F
0x1800af213  lea     rcx, [rbp+0CF0h+var_D18]
0x1800af217  mov     rdx, [rbp+0CF0h+arg_40]
0x1800af21e  call    shaping__string__ShapingString__copy_string_to_vec
0x1800af223  mov     rdi, qword ptr [rbp+0CF0h+var_D18+8]
0x1800af227  mov     r12, [rbp+0CF0h+var_D08]
0x1800af22b  xor     ecx, ecx
0x1800af22d  lea     r13, word_1803C6496
0x1800af234  lea     rsi, [rbp+0CF0h+var_7A0]
0x1800af23b  mov     [rbp+0CF0h+var_58], rdi
0x1800af242  nop     word ptr [rax+rax+00000000h]
0x1800af250  xor     r8d, r8d
0x1800af253  mov     rdx, rcx
0x1800af256  cmp     rcx, r12
0x1800af259  jnb     short loc_1800AF2D1
0x1800af25b  mov     r9, rcx
0x1800af25e  xchg    ax, ax
0x1800af260  mov     eax, [rdi+r9*4]
0x1800af264  cmp     rax, 10EFFh
0x1800af26a  ja      short loc_1800AF2C0
0x1800af26c  mov     r10d, eax
0x1800af26f  shr     r10d, 8
0x1800af273  movzx   r10d, byte ptr [r10+r13]
0x1800af278  test    r10b, r10b
0x1800af27b  jns     short loc_1800AF2C0
0x1800af27d  movzx   r11d, al
0x1800af281  and     r10d, 7Fh
0x1800af285  mov     eax, r10d
0x1800af288  shl     eax, 8
0x1800af28b  or      rax, r11
0x1800af28e  cmp     r10b, 6
0x1800af292  jnb     loc_1800B269F
0x1800af298  lea     r10, byte_1803C65A5
0x1800af29f  movzx   eax, byte ptr [rax+r10]
0x1800af2a4  add     al, 0FAh
0x1800af2a6  cmp     al, 0Dh
0x1800af2a8  jnb     short loc_1800AF2C0
0x1800af2aa  mov     rcx, rdx
0x1800af2ad  mov     r8b, 1
0x1800af2b0  jmp     short loc_1800AF2C9
0x1800af2c0  test    r8b, 1
0x1800af2c4  jnz     short loc_1800AF2E0
0x1800af2c6  mov     rdx, r9
0x1800af2c9  inc     r9
0x1800af2cc  cmp     r12, r9
0x1800af2cf  jnz     short loc_1800AF260
0x1800af2d1  mov     r9, r12
0x1800af2d4  jmp     short loc_1800AF2E9
0x1800af2e0  cmp     r9, rdx
0x1800af2e3  jbe     loc_1800B1AEC
0x1800af2e9  mov     rbx, r9
0x1800af2ec  sub     rbx, rdx
0x1800af2ef  cmp     rbx, r12
0x1800af2f2  ja      loc_1800B13BC
0x1800af2f8  test    r8b, 1
0x1800af2fc  jz      loc_1800AF41D
0x1800af302  cmp     rcx, r12
0x1800af305  jnb     loc_1800B13D9
0x1800af30b  cmp     r9, rdx
0x1800af30e  jz      loc_1800B13F6
0x1800af314  lea     r14, [rbx+rcx]
0x1800af318  cmp     r14, r12
0x1800af31b  ja      loc_1800AF41D
0x1800af321  cmp     r14, rcx
0x1800af324  jb      loc_1800B1413
0x1800af32a  lea     r15, [rdi+rcx*4]
0x1800af32e  mov     [rbp+0CF0h+var_7A0], 0
0x1800af339  xor     edi, edi
0x1800af33b  xor     eax, eax
0x1800af33d  jmp     short loc_1800AF359
0x1800af33f  mov     [rbp+0CF0h+var_790], rdi
0x1800af346  mov     eax, 1
0x1800af34b  nop     dword ptr [rax+rax+00h]
0x1800af350  cmp     rdi, rbx
0x1800af353  jz      loc_1800AF400
0x1800af359  mov     rdx, rdi
0x1800af35c  inc     rdi
0x1800af35f  mov     ecx, [r15+rdx*4]
0x1800af363  cmp     rcx, 10EFFh
0x1800af36a  ja      short loc_1800AF37D
0x1800af36c  mov     r8d, ecx
0x1800af36f  shr     r8d, 8
0x1800af373  movzx   r8d, byte ptr [r8+r13]
0x1800af378  test    r8b, r8b
0x1800af37b  js      short loc_1800AF39E
0x1800af37d  test    al, 1
0x1800af37f  jz      short loc_1800AF350
0x1800af381  mov     rcx, rsi
0x1800af384  mov     rdx, r15
0x1800af387  mov     r8, rbx
0x1800af38a  call    enum2$_shaping__engine__arabic__fsm__reorder_arabic_cluster__State___apply_mcm_shifts
0x1800af38f  mov     [rbp+0CF0h+var_7A0], 0
0x1800af39a  xor     eax, eax
0x1800af39c  jmp     short loc_1800AF350
0x1800af39e  movzx   r9d, cl
0x1800af3a2  and     r8d, 7Fh
0x1800af3a6  mov     ecx, r8d
0x1800af3a9  shl     ecx, 8
0x1800af3ac  or      rcx, r9
0x1800af3af  cmp     r8b, 6
0x1800af3b3  jnb     loc_1800B22BD
0x1800af3b9  lea     r8, byte_1803C65A5
0x1800af3c0  movzx   ecx, byte ptr [rcx+r8]
0x1800af3c5  lea     r8d, [rcx-7]
0x1800af3c9  cmp     r8d, 0Ch
0x1800af3cd  jnb     short loc_1800AF3EE
0x1800af3cf  mov     [rbp+0CF0h+var_7A0], 1
0x1800af3da  test    al, 1
0x1800af3dc  jnz     loc_1800AF33F
0x1800af3e2  mov     [rbp+0CF0h+Src], rdx
0x1800af3e9  jmp     loc_1800AF33F
0x1800af3ee  cmp     ecx, 6
0x1800af3f1  test    al, 1
0x1800af3f3  jz      loc_1800AF350
0x1800af3f9  jmp     short loc_1800AF381
0x1800af400  mov     rcx, rsi
0x1800af403  mov     rdx, r15
0x1800af406  mov     r8, rbx
0x1800af409  call    enum2$_shaping__engine__arabic__fsm__reorder_arabic_cluster__State___apply_mcm_shifts
0x1800af40e  mov     rcx, r14
0x1800af411  mov     rdi, [rbp+0CF0h+var_58]
0x1800af418  jmp     loc_1800AF250
0x1800af41d  mov     r13, [rbp+0CF0h+var_D08]
0x1800af421  mov     [rbp+0CF0h+var_110], r13
0x1800af428  movdqu  xmm0, [rbp+0CF0h+var_D18]
0x1800af42d  movdqa  xmmword ptr [rbp+0CF0h+var_120], xmm0
0x1800af435  mov     rax, [rbp+0CF0h+var_120+8]
0x1800af43c  mov     [rbp+0CF0h+var_48], rax
0x1800af443  lea     rsi, ds:0[r13*4]
0x1800af44b  mov     dil, 1
0x1800af44e  mov     r12, [rbp+0CF0h+var_50]
0x1800af455  mov     rax, r13
0x1800af458  shr     rax, 3Eh
0x1800af45c  setz    al
0x1800af45f  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1800af469  cmp     rsi, rcx
0x1800af46c  setb    cl
0x1800af46f  test    al, cl
0x1800af471  jnz     short loc_1800AF4CD
0x1800af473  lea     rcx, off_180348ED8; "D:\\os\\tools\\Rust\\vpack\\rust.tools"...
0x1800af47a  call    alloc__raw_vec__capacity_overflow
0x1800af47f  jmp     loc_1800B387F
0x1800af484  mov     eax, dword ptr [rbp+0CF0h+Src]
0x1800af48a  mov     rcx, [rbp+0CF0h+var_A0]
0x1800af491  mov     [rcx+4], eax
0x1800af494  mov     dword ptr [rcx], 1
0x1800af49a  jmp     loc_1800B0E84
0x1800af49f  test    rdx, rdx
0x1800af4a2  jz      short loc_1800AF511
0x1800af4a4  mov     ecx, 8
0x1800af4a9  mov     rdi, rdx
0x1800af4ac  call    std__sys__alloc__windows__process_heap_alloc
0x1800af4b1  mov     [rbp+0CF0h+lpMem], rax
0x1800af4b8  test    rax, rax
0x1800af4bb  jz      loc_1800B3425
0x1800af4c1  test    r15, r15
0x1800af4c4  setz    [rbp+0CF0h+var_69]
0x1800af4cb  jmp     short loc_1800AF524
  ... truncated ...
```
