# DoType1InterpretCharString

- ea: `0x14006b7ac`
- end: `0x140070a9a`
- name: `DoType1InterpretCharString`
- size: `21230`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation`

## callers

- `0x140040cb4`

## callees

- `0x14003bebc`
- `0x140055858`
- `0x140057088`
- `0x140057188`
- `0x140057840`
- `0x140057a78`
- `0x140057d00`
- `0x140058368`
- `0x1400584c4`
- `0x1400590d8`
- `0x14005ce34`
- `0x14005d31c`
- `0x14005d630`
- `0x14006039c`
- `0x140060f1c`
- `0x140061894`
- `0x140066e4c`
- `0x1400675a0`
- `0x14006b3cc`
- `0x14006b7ac`
- `0x1400744a8`
- `0x140075de0`
- `0x140076370`
- `0x1400767dc`
- `0x14007680c`
- `0x140076ede`
- `0x140076ef6`
- `0x140085b34`
- `0x140085bb0`
- `0x14008c080`
- `0x14008c80c`
- `0x14008dea4`
- `0x14008df14`
- `0x14008e790`
- `0x14008e8f4`
- `0x14008e958`
- `0x14008ed30`
- `0x14008ee60`
- `0x14008f4a0`
- `0x140098010`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14006c4a2`
- `KERNEL32!TerminateProcess` at `0x14006c4a2`
- `KERNEL32!GetCurrentProcess` at `0x14006c494`
- `KERNEL32!GetCurrentProcess` at `0x14006c494`

## string_xrefs

- `0x14006e852`: `sidebearing or width override out of bounds`
- `0x14006e87c`: `sidebearing or width override out of bounds`
- `0x14006e8aa`: `sidebearing or width override out of bounds`
- `0x14006e8dc`: `sidebearing or width override out of bounds`

## pseudocode

```c
__int64 __fastcall DoType1InterpretCharString(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 **a4,
        __int64 a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        unsigned int *a10)
{
  __int64 v10; // r13
  unsigned int *v13; // rdi
  BOOL v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 *v18; // r15
  __int64 *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  _QWORD *v22; // rdi
  __int64 v23; // rcx
  __int64 result; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // r12
  unsigned __int8 v28; // r14
  __int64 v29; // r10
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 (__fastcall *v33)(); // r11
  __int64 v34; // rdx
  __int64 **v35; // r13
  __int64 *v36; // r13
  _DWORD *v37; // r8
  int v38; // r10d
  __int64 *v39; // r9
  _DWORD *v40; // rax
  int v41; // ecx
  int v42; // edx
  __int16 v43; // ax
  __int16 v44; // ax
  __int16 v45; // ax
  __int16 v46; // ax
  __int16 v47; // ax
  __int64 *v48; // rax
  _DWORD *v49; // rcx
  __int64 v50; // r13
  __int64 v51; // r9
  char v52; // al
  __int64 v53; // rcx
  int v54; // edx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rcx
  unsigned int v58; // edx
  __int64 v59; // rax
  __int64 v60; // r10
  __int64 v61; // rcx
  __int64 v62; // rax
  signed int v63; // eax
  __int64 (__fastcall *v64)(); // rcx
  unsigned __int64 v65; // r13
  unsigned __int64 v66; // r9
  __int64 v67; // rdx
  int v68; // ecx
  unsigned int v69; // ecx
  size_t v70; // r8
  __int64 v71; // rcx
  unsigned int v72; // ecx
  bool v73; // zf
  bool v74; // cc
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  __int64 v82; // rax
  int v83; // ecx
  unsigned __int64 v84; // rdx
  __int64 v85; // r8
  int v86; // ecx
  int v87; // ecx
  __int64 v88; // rcx
  int v89; // ecx
  int v90; // ecx
  int v91; // ecx
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  __int64 v95; // rax
  int v96; // eax
  int v97; // edx
  __int64 (__fastcall ***v98)(_QWORD, size_t); // rcx
  __int64 (__fastcall *v99)(_QWORD, size_t); // r9
  void *v100; // rax
  int v101; // eax
  int v102; // ecx
  int v103; // ecx
  int v104; // ecx
  int v105; // ecx
  HANDLE CurrentProcess; // rax
  unsigned __int8 *v107; // rax
  __int64 v108; // r8
  __int64 v109; // rax
  __int64 v110; // rax
  _DWORD *v111; // rdx
  __int64 v112; // rcx
  _DWORD *v113; // rax
  __int64 v114; // rax
  int v115; // rax^4
  unsigned int v116; // ecx
  __int64 v117; // rax
  _DWORD *v118; // rdx
  __int64 v119; // rax
  int v120; // r9d
  int v121; // eax
  __int64 v122; // rdx
  __int64 v123; // rax
  __int64 v124; // rax
  int v125; // eax
  __m128i v126; // xmm0
  __int64 v127; // rax
  __m128i v128; // xmm0
  double v129; // xmm1_8
  double v130; // xmm1_8
  __int64 v131; // rax
  int v132; // eax
  int v133; // edx
  __int64 (__fastcall ***v134)(_QWORD, size_t); // rcx
  __int64 (__fastcall *v135)(_QWORD, size_t); // r9
  void *v136; // rax
  int v137; // edx
  unsigned int v138; // eax
  __int64 v139; // r9
  unsigned int v140; // r14d
  int v141; // eax
  __int64 v142; // rdx
  __int64 v143; // rax
  int v144; // eax
  int v145; // edx
  __int64 (__fastcall ***v146)(_QWORD, size_t); // rcx
  __int64 (__fastcall *v147)(_QWORD, size_t); // r9
  void *v148; // rax
  int v149; // eax
  int v150; // eax
  __int64 v151; // rax
  _DWORD *v152; // r8
  _DWORD *v153; // r13
  __int64 v154; // rax
  int v155; // eax
  int v156; // ecx
  __int64 v157; // rax
  int v158; // eax
  __int64 v159; // rax
  int v160; // ecx
  int v161; // r9d
  int v162; // edx
  int v163; // edx
  __int64 (__fastcall ***v164)(_QWORD, size_t); // rcx
  __int64 (__fastcall *v165)(_QWORD, size_t); // r9
  void *v166; // rax
  int v167; // edx
  int v168; // r9d
  int v169; // ecx
  size_t v170; // r8
  __int64 v171; // rax
  __int64 v172; // rcx
  const void *v173; // rdx
  int v174; // eax
  int v175; // ecx
  double v176; // xmm1_8
  double v177; // xmm0_8
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  unsigned int v181; // ecx
  unsigned int v182; // ecx
  unsigned int v183; // ecx
  unsigned int v184; // ecx
  unsigned int v185; // ecx
  unsigned int v186; // ecx
  __int64 v187; // rax
  __int64 v188; // rax
  int *v189; // rax
  int v190; // ecx
  __int64 v191; // rax
  __int64 v192; // rax
  int v193; // edx
  int v194; // r10d
  int v195; // r11d
  __int64 v196; // r8
  int v197; // ecx
  int v198; // edx
  __int64 (__fastcall ***v199)(_QWORD, size_t); // rcx
  __int64 (__fastcall *v200)(_QWORD, size_t); // r9
  void *v201; // rax
  int v202; // ecx
  int v203; // r10d
  int v204; // edx
  int v205; // r11d
  __int64 v206; // rax
  unsigned int v207; // ecx
  unsigned int v208; // ecx
  unsigned int v209; // ecx
  unsigned int v210; // ecx
  unsigned int v211; // ecx
  unsigned int v212; // ecx
  unsigned int v213; // ecx
  __int64 v214; // rax
  __int64 v215; // rax
  double v216; // xmm1_8
  __int64 v217; // rax
  __int64 v218; // rax
  int v219; // ecx
  unsigned int v220; // ecx
  unsigned int v221; // ecx
  unsigned int v222; // ecx
  unsigned int v223; // ecx
  unsigned int v224; // ecx
  unsigned int v225; // ecx
  unsigned int v226; // ecx
  __int64 *v227; // r10
  __int64 v228; // r9
  unsigned __int64 v229; // rcx
  unsigned __int64 v230; // rdx
  __int64 v231; // r8
  unsigned int v232; // r9d
  unsigned int v233; // r8d
  int v234; // edx
  unsigned int v235; // r10d
  int v236; // r13d
  unsigned int v237; // r11d
  unsigned int v238; // eax
  unsigned int v239; // ecx
  unsigned int v240; // edx
  unsigned int v241; // r10d
  int v242; // ecx
  unsigned int v243; // edx
  int v244; // r11d
  unsigned int v245; // ecx
  int v246; // eax
  int v247; // edx
  int v248; // eax
  int v249; // r10d
  unsigned int v250; // edx
  unsigned int v251; // r13d
  unsigned int v252; // r9d
  int v253; // edx
  unsigned int v254; // ecx
  unsigned int v255; // edx
  int v256; // edx
  unsigned int v257; // r9d
  unsigned int v258; // r11d
  unsigned int v259; // r10d
  int v260; // eax
  unsigned int v261; // ecx
  unsigned int v262; // edx
  int v263; // ecx
  unsigned int v264; // edx
  unsigned int v265; // ecx
  unsigned int v266; // edx
  unsigned int v267; // ecx
  unsigned int v268; // ecx
  unsigned int v269; // edx
  int v270; // r9d
  int v271; // ecx
  int v272; // r10d
  int v273; // eax
  __int64 (__fastcall *v274)(); // r13
  _DWORD *v275; // rcx
  __int64 v276; // rax
  __int64 v277; // rax
  int v278; // ecx
  __int64 v279; // r8
  int v280; // r10d
  int v281; // r11d
  int *v282; // r9
  int v283; // r14d
  int v284; // eax
  int v285; // edx
  int v286; // eax
  _DWORD *v287; // r9
  int v288; // r14d
  int v289; // eax
  int v290; // r8d
  __int64 v291; // rdx
  int v292; // eax
  __int64 v293; // rcx
  int v294; // edx
  __int64 v295; // rax
  unsigned int v296; // ecx
  unsigned int v297; // edx
  unsigned int *v298; // rax
  unsigned int *v299; // rcx
  unsigned int *v300; // rdx
  unsigned int v301; // ecx
  unsigned int v302; // edx
  int v303; // eax
  __int64 v304; // r10
  int v305; // eax
  __int64 v306; // r8
  __int64 v307; // r11
  __int64 v308; // r9
  char v309; // al
  __int64 v310; // rcx
  int v311; // edx
  int v312; // eax
  __int64 v313; // rcx
  __int64 v314; // rcx
  unsigned int v315; // edx
  __int64 v316; // r9
  __int64 v317; // r9
  char v318; // al
  __int64 v319; // rcx
  int v320; // edx
  int v321; // eax
  __int64 v322; // rcx
  __int64 v323; // rcx
  unsigned int v324; // edx
  __int64 v325; // r9
  char v326; // al
  __int64 v327; // rcx
  int v328; // edx
  int v329; // eax
  __int64 v330; // rcx
  __int64 v331; // rcx
  unsigned int v332; // edx
  __int64 v333; // rax
  __int64 v334; // rcx
  __int64 v335; // rax
  __int64 v336; // rax
  __int64 v337; // rcx
  __int64 v338; // r9
  __int64 v339; // r11
  char v340; // dl
  void (__fastcall *v341)(__int64 *, _QWORD, size_t, size_t); // rax
  __int64 v342; // r13
  int v343; // r14d
  int v344; // ebx
  __int64 (__fastcall *v345)(); // r15
  __int64 *v346; // r12
  __int64 v347; // rdx
  unsigned int v348; // ecx
  unsigned int v349; // eax
  void (__fastcall *v350)(unsigned __int64 *, __int64 *); // rax
  unsigned int *v351; // rax
  __int64 v352; // r10
  size_t v353; // r13
  __int64 v354; // r8
  __int64 v355; // r13
  unsigned int v356; // eax
  int v357; // eax
  int v358; // eax
  int v359; // edx
  __int64 v360; // rdx
  __int64 v361; // r13
  int v362; // r11d
  int v363; // r10d
  unsigned __int64 v364; // rax
  int v365; // r10d
  __int64 v366; // r13
  int v367; // r11d
  int v368; // r9d
  int v369; // r8d
  __int64 v370; // rax
  int v371; // r9d
  unsigned int v372; // r10d
  unsigned int v373; // r8d
  unsigned int v374; // r9d
  unsigned int v375; // eax
  __int64 **v376; // rdi
  __int64 *v377; // rdx
  __int64 v378; // rdi
  unsigned int v379; // eax
  void (__fastcall *v380)(unsigned __int64 *, __int64 *); // rax
  unsigned __int64 v381; // r13
  int v382; // eax
  __int64 v383; // rax
  int v384; // r13d
  int v385; // ecx
  unsigned int v386; // edx
  __int64 v387; // rax
  __int64 v388; // rdx
  __int64 v389; // rax
  unsigned int v390; // eax
  int v391; // r13d
  int v392; // eax
  unsigned int *v393; // rcx
  unsigned int v394; // edx
  __int64 v395; // rax
  __int64 v396; // rdx
  __int64 v397; // rax
  int v398; // eax
  int v399; // r13d
  __int64 *v400; // r13
  void (__fastcall *v401)(__int64 *); // rax
  void (__fastcall *v402)(unsigned __int64 *, __int64 *); // rax
  __int64 v403; // rcx
  _DWORD *v404; // rax
  int v405; // r8d
  char v406; // al
  int v407; // ecx
  int v408; // r13d
  unsigned int v409; // edx
  unsigned int v410; // r8d
  __int64 v411; // rax
  __int64 v412; // rdx
  __int64 v413; // rax
  int v414; // ecx
  int v415; // r13d
  int v416; // ecx
  bool j; // cc
  unsigned int v418; // edx
  unsigned int v419; // r8d
  __int64 v420; // rax
  __int64 v421; // rdx
  __int64 v422; // rax
  int v423; // edx
  int v424; // ecx
  __int64 v425; // r8
  __int64 v426; // rcx
  int v427; // r13d
  __int64 v428; // rax
  bool v429; // sf
  bool v430; // of
  __int64 v431; // rcx
  __int64 v432; // r13
  __int64 v433; // rax
  unsigned int v434; // ecx
  unsigned int v435; // eax
  int v436; // eax
  void (__fastcall *v437)(__int64, __int64 *); // rax
  int v438; // eax
  int v439; // r9d
  int v440; // eax
  int v441; // eax
  int v442; // r9d
  int v443; // eax
  unsigned int v444; // eax
  __int64 v445; // rax
  _QWORD *v446; // r13
  __int64 k; // r13
  __int64 v448; // rax
  __int64 v449; // rcx
  __int64 v450; // rdx
  __int64 v451; // rax
  unsigned int v452; // eax
  unsigned int v453; // edx
  unsigned int v454; // eax
  unsigned int v455; // ecx
  unsigned int v456; // edx
  unsigned int v457; // ecx
  char v458; // al
  unsigned __int8 *v459; // rdx
  int v460; // ecx
  int v461; // r11d
  int v462; // r8d
  __int64 v463; // r13
  int v464; // ecx
  __int64 v465; // rdx
  int v466; // r10d
  unsigned int v467; // r8d
  unsigned int v468; // ecx
  unsigned int v469; // r9d
  unsigned int v470; // r11d
  int v471; // eax
  unsigned int v472; // eax
  void (__fastcall *v473)(unsigned __int64 *, __int64 *, __int64 *, unsigned __int64 *, __int64 *); // rax
  __int64 v474; // r10
  int v475; // eax
  _DWORD *v476; // r8
  __int64 v477; // rcx
  int v478; // eax
  int v479; // r8d
  __int64 v480; // rcx
  __int64 v481; // rcx
  unsigned int v482; // r8d
  __int64 v483; // rcx
  int v484; // edx
  int v485; // eax
  __int64 v486; // rcx
  __int64 v487; // rcx
  int v488; // edx
  int v489; // edx
  __int64 v490; // r10
  __int64 v491; // rcx
  __int64 v492; // rax
  unsigned __int8 *v493; // rax
  __int64 v494; // r13
  int v495; // eax
  int v496; // edx
  unsigned int v497; // r9d
  unsigned int v498; // ecx
  void (__fastcall *v499)(unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, __int64 *); // rax
  __int64 v500; // r13
  int v501; // eax
  int v502; // ecx
  int v503; // edx
  unsigned int v504; // r9d
  unsigned int v505; // r10d
  int v506; // ecx
  void (__fastcall *v507)(unsigned __int64 *, unsigned __int64 *, __int64 *, unsigned __int64 *, __int64 *); // rax
  __int64 v508; // r13
  __int64 (__fastcall *v509)(); // r15
  int v510; // r14d
  __int64 *v511; // r13
  int v512; // ebx
  __int64 *v513; // r12
  void (__fastcall *v514)(unsigned __int64 *, __int64 *); // rax
  __int64 v515; // rdx
  int v516; // r13d
  int v517; // edx
  __int64 v518; // r13
  unsigned int v519; // edi
  unsigned int v520; // edi
  unsigned int v521; // edi
  int v522; // eax
  unsigned int v523; // edi
  unsigned int v524; // edi
  unsigned int v525; // edi
  void (__fastcall *v526)(unsigned __int64 *, __int64 *, __int64 *, unsigned __int64 *, __int64 *); // rax
  unsigned __int64 v527; // rax
  __int64 v528; // r11
  unsigned int v529; // r9d
  unsigned int v530; // r10d
  unsigned int v531; // edx
  unsigned int v532; // r8d
  unsigned int v533; // eax
  void (__fastcall *v534)(unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, __int64 *); // rax
  __int64 v535; // rdx
  __int64 v536; // r13
  int v537; // r14d
  __int64 (__fastcall *v538)(); // rbx
  __int64 *v539; // r12
  __int64 *v540; // r15
  void (__fastcall *v541)(unsigned __int64 *, __int64 *); // rax
  int v542; // ecx
  void (__fastcall *v543)(__int64 *); // rax
  void (__fastcall *v544)(__int64 *); // rax
  __int64 v545; // rdx
  __int64 v546; // rcx
  bool v547; // zf
  __int64 v548; // rcx
  _DWORD *v549; // rax
  __int64 i; // rcx
  __int64 v551; // rax
  __int64 v552; // r13
  int v553; // r8d
  __int64 v554; // rdx
  unsigned int v556; // [rsp+60h] [rbp-A8h]
  int v557; // [rsp+64h] [rbp-A4h]
  int v558; // [rsp+64h] [rbp-A4h]
  int v559; // [rsp+64h] [rbp-A4h]
  unsigned int v560; // [rsp+64h] [rbp-A4h]
  int v561; // [rsp+64h] [rbp-A4h]
  int v562; // [rsp+64h] [rbp-A4h]
  int v563; // [rsp+64h] [rbp-A4h]
  int v564; // [rsp+64h] [rbp-A4h]
  int v565; // [rsp+64h] [rbp-A4h]
  unsigned int v566; // [rsp+64h] [rbp-A4h]
  int v567; // [rsp+64h] [rbp-A4h]
  int v568; // [rsp+64h] [rbp-A4h]
  int v569; // [rsp+64h] [rbp-A4h]
  int v570; // [rsp+64h] [rbp-A4h]
  int v571; // [rsp+64h] [rbp-A4h]
  int v572; // [rsp+64h] [rbp-A4h]
  int v573; // [rsp+64h] [rbp-A4h]
  int v574; // [rsp+64h] [rbp-A4h]
  char v575; // [rsp+68h] [rbp-A0h]
  char v576; // [rsp+68h] [rbp-A0h]
  unsigned __int8 v577; // [rsp+68h] [rbp-A0h]
  char *v578; // [rsp+70h] [rbp-98h]
  unsigned __int8 *v579; // [rsp+70h] [rbp-98h]
  unsigned __int8 *v580; // [rsp+70h] [rbp-98h]
  _DWORD *v581; // [rsp+70h] [rbp-98h]
  unsigned __int8 *v582; // [rsp+70h] [rbp-98h]
  unsigned __int64 v583; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v584; // [rsp+88h] [rbp-80h]
  __int64 v585; // [rsp+90h] [rbp-78h]
  int v586; // [rsp+98h] [rbp-70h]
  unsigned int v587; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v588; // [rsp+A0h] [rbp-68h]
  int v589; // [rsp+A4h] [rbp-64h]
  size_t Size; // [rsp+A8h] [rbp-60h]
  unsigned __int8 v591; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v592; // [rsp+B8h] [rbp-50h] BYREF
  __int64 *v593; // [rsp+C0h] [rbp-48h]
  int v594; // [rsp+C8h] [rbp-40h]
  int v595; // [rsp+CCh] [rbp-3Ch]
  __int64 v596; // [rsp+D0h] [rbp-38h]
  __int64 *v597; // [rsp+D8h] [rbp-30h]
  unsigned __int8 *v598; // [rsp+E0h] [rbp-28h]
  __int64 (__fastcall *v599)(); // [rsp+E8h] [rbp-20h]
  int v600; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v601; // [rsp+F8h] [rbp-10h] BYREF
  int v602; // [rsp+100h] [rbp-8h]
  int v603; // [rsp+104h] [rbp-4h]
  unsigned __int8 v604; // [rsp+108h] [rbp+0h]
  int v605; // [rsp+10Ch] [rbp+4h]
  int v606; // [rsp+110h] [rbp+8h]
  unsigned __int64 v607; // [rsp+118h] [rbp+10h] BYREF
  int v608; // [rsp+120h] [rbp+18h]
  int v609; // [rsp+124h] [rbp+1Ch]
  __int64 v610; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int64 v611; // [rsp+130h] [rbp+28h] BYREF
  __int64 v612; // [rsp+138h] [rbp+30h] BYREF
  __int64 **v613; // [rsp+140h] [rbp+38h]
  __int64 v614; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v615; // [rsp+150h] [rbp+48h] BYREF
  int v616; // [rsp+158h] [rbp+50h]
  unsigned __int64 v617; // [rsp+160h] [rbp+58h] BYREF
  int v618; // [rsp+168h] [rbp+60h]
  unsigned __int64 v619; // [rsp+170h] [rbp+68h] BYREF
  __int64 v620; // [rsp+178h] [rbp+70h]
  int v621; // [rsp+180h] [rbp+78h]
  __int64 v622; // [rsp+188h] [rbp+80h] BYREF
  int v623; // [rsp+190h] [rbp+88h]
  __int64 v624; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int64 v625; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v626; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned int *v627; // [rsp+1B0h] [rbp+A8h]
  unsigned int v628; // [rsp+1B8h] [rbp+B0h]
  unsigned int v629; // [rsp+1BCh] [rbp+B4h]
  unsigned __int64 v630; // [rsp+1C0h] [rbp+B8h]
  __int64 v631; // [rsp+1C8h] [rbp+C0h]
  unsigned __int64 v632; // [rsp+1D0h] [rbp+C8h] BYREF
  int v633; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 v634; // [rsp+1E0h] [rbp+D8h] BYREF
  unsigned __int64 v635; // [rsp+1E8h] [rbp+E0h] BYREF
  _DWORD *v636; // [rsp+1F0h] [rbp+E8h]
  __int64 v637; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v638; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v639; // [rsp+208h] [rbp+100h] BYREF
  __int64 v640; // [rsp+210h] [rbp+108h] BYREF
  _QWORD *v641; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int64 v642; // [rsp+220h] [rbp+118h] BYREF
  unsigned __int64 v643; // [rsp+228h] [rbp+120h]
  int v644; // [rsp+230h] [rbp+128h]
  __int64 v645; // [rsp+238h] [rbp+130h] BYREF
  __int64 v646; // [rsp+240h] [rbp+138h] BYREF
  __int64 *v647; // [rsp+248h] [rbp+140h]
  __int64 *v648; // [rsp+250h] [rbp+148h]
  __int64 *v649; // [rsp+258h] [rbp+150h]
  __int64 v650; // [rsp+260h] [rbp+158h]
  unsigned __int64 v651; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 v652; // [rsp+270h] [rbp+168h] BYREF
  unsigned __int64 v653; // [rsp+278h] [rbp+170h] BYREF
  __int64 v654; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 v655; // [rsp+288h] [rbp+180h]
  unsigned __int64 v656; // [rsp+290h] [rbp+188h] BYREF
  unsigned __int64 v657; // [rsp+298h] [rbp+190h] BYREF
  __int64 v658; // [rsp+2A0h] [rbp+198h] BYREF
  unsigned __int64 v659; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned __int64 v660; // [rsp+2B0h] [rbp+1A8h]
  _DWORD v661[216]; // [rsp+2B8h] [rbp+1B0h]

  v10 = a7;
  v13 = a10;
  v650 = a5;
  v636 = a9;
  v593 = *(__int64 **)(a7 + 24);
  v608 = *(_DWORD *)(a1 + 716);
  v628 = *(_DWORD *)a7;
  v620 = a2;
  v613 = a4;
  v596 = a3;
  v600 = v628 & 0x404;
  v629 = *(_DWORD *)(a1 + 968);
  v15 = v600 != 0;
  v16 = *(_QWORD *)(a1 + 976);
  v627 = a10;
  v585 = a7;
  v583 = 0;
  v631 = 0;
  v625 = 0;
  v592 = 0;
  v622 = 0;
  v630 = 0;
  v624 = 0;
  v618 = 0;
  v641 = 0;
  if ( v16 )
    *(_DWORD *)(v16 + 4) = 0;
  v17 = a2;
  bprocs = a2;
  if ( v15 != (a6 == 0) )
  {
    os_raise(0xFFFFFFFFLL, 0);
    v17 = bprocs;
  }
  v18 = a4[3];
  v19 = gNullPathProcs;
  v647 = v18;
  v649 = v18;
  v20 = 1;
  if ( a6 )
    v19 = a6;
  v597 = v19;
  if ( !v600 )
  {
    v21 = (*a4)[4];
    if ( *(_DWORD *)(v21 + 8) < 0x2030u )
    {
      if ( *(_QWORD *)v21 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v17 + 24) + 16LL))(
          *(_QWORD *)(v17 + 24),
          v21,
          1);
        v17 = bprocs;
      }
      v22 = (_QWORD *)(*a4)[4];
      *v22 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64))(v17 + 24))(*(_QWORD *)(v17 + 24), 8240, v20);
      v23 = (*a4)[4];
      if ( !*(_QWORD *)v23 )
      {
        *(_DWORD *)(v23 + 8) = 0;
        return 4294967292LL;
      }
      v13 = v627;
      v20 = 1;
      *(_DWORD *)(v23 + 8) = 8240;
    }
    v25 = *(_QWORD *)(*a4)[4];
    qword_1400B6080 = v25;
    *(_DWORD *)v25 = 1;
    *(_DWORD *)(v25 + 64) = -399507455;
    *(_QWORD *)(v25 + 80) = v25 + 56;
    *(_DWORD *)(v25 + 68) = -399507455;
    *(_DWORD *)(v25 + 72) = 0;
    *(_QWORD *)(v25 + 4200) = v25 + 4176;
    qword_1400B6090 = v25 + 4120;
    *(_DWORD *)(v25 + 4120) = 1;
    *(_DWORD *)(v25 + 4184) = -399507455;
    *(_DWORD *)(v25 + 4188) = -399507455;
    *(_DWORD *)(v25 + 4192) = 0;
  }
  v26 = 0;
  v648 = 0;
  v27 = 0;
  v628 = ~(v628 | 0xFFFFFFFE);
  qword_1400B6060 = a1 + 28;
  qword_1400B6070 = a1 + 224;
  dword_1400B607C = *(_DWORD *)(a1 + 24);
  dword_1400B6068 = *(_DWORD *)(a1 + 220);
  v643 = 0;
  lockSlopesInited = 0;
  lockFixMapOk = 1;
  if ( (*(_BYTE *)a7 & 1) == 0 || (v595 = 1, (v608 & 0xC0000000) == 0) )
    v595 = 0;
  if ( (*(_DWORD *)a7 & 0x400) == 0 )
    SetGSMatrix(a1, 0, 1);
  v28 = v608;
  doFixupMap = v608 & 0x10;
  if ( (v608 & 0x10) != 0 && !v600 )
  {
    v622 = 0x1000000000000LL;
    ((void (__fastcall *)(__int64, __int64 *, __int64))IDTransform)(0x1000000000000LL, &v622, v20);
    *(_DWORD *)(qword_1400B6090 + 16) = HIDWORD(v622);
    v622 = 0x10000;
    ((void (__fastcall *)(__int64, __int64 *))IDTransform)(0x10000, &v622);
    *(_DWORD *)(qword_1400B6080 + 16) = v622;
  }
  v29 = a1;
  erosion = 0x10000;
  if ( *(_DWORD *)(a1 + 724) == 2 )
  {
    v30 = *(unsigned int *)(a1 + 712);
    dword_1400B606C = 1;
    v31 = ErodeSW(v30, 0x10000, 1);
    v29 = a1;
    dword_1400B6078 = ((v31 + 0x8000) & 0x10000) == 0;
  }
  else
  {
    dword_1400B606C = 0;
  }
  dword_1400B6088 = 0;
  v633 = -32768;
  v644 = 0x7FFF;
  if ( (v28 | 0xFFFFFFDF) == 0xFFFFFFFF && !v600 && v595 )
    goto LABEL_431;
  T1globalColoring = 2;
LABEL_32:
  CSIdealOffset = 0;
  CSIdealBase = 0;
  nGlbColors = 0;
  *((_DWORD *)v613 + 9) = 0;
  v73 = *(_DWORD *)(v29 + 964) == 0;
  gcList = 0;
  glbCounterList = 0;
  nGlbCounters = 0;
  v630 = 0;
  v631 = 0;
  v583 = 0;
  lockFixedMap = 0;
  *(_QWORD *)(v29 + 948) = 0;
  *(_DWORD *)(v29 + 956) = 0;
  if ( !v73 )
    *(_DWORD *)(v29 + 948) = 1;
  v32 = a8;
  v618 = 0;
  v33 = (__int64 (__fastcall *)())(a8 + 24);
  *(_DWORD *)(a8 + 24) = 0;
  v73 = (*(_BYTE *)v10 & 0x18) == 0;
  v599 = (__int64 (__fastcall *)())(a8 + 24);
  if ( !v73 )
  {
    v34 = v585;
    v35 = 0;
    if ( (*(_BYTE *)v585 & 0x20) != 0 )
    {
      if ( (*(_BYTE *)v585 & 0x40) != 0 )
        v36 = (__int64 *)*v593;
      else
        v36 = v593;
      v35 = (__int64 **)(v36 + 2);
    }
    if ( (*(_BYTE *)v585 & 0x10) != 0 )
    {
      v37 = (_DWORD *)(a8 + 12);
      v38 = *(_DWORD *)(*(_QWORD *)(v585 + 8) + 8LL);
      *(_DWORD *)(a8 + 12) = v38;
      *(_DWORD *)(a8 + 28) = 2;
      if ( (*(_BYTE *)v34 & 0x20) != 0 )
      {
        v39 = *v35;
        v648 = v39;
        if ( v39 )
        {
          v40 = *(_DWORD **)(v34 + 8);
          v41 = (*v40 + 0x8000) >> 16;
          v42 = (v40[1] + 0x8000) >> 16;
          if ( *(_WORD *)v39 == (_WORD)v633 )
            v43 = 0x8000;
          else
            v43 = *(_WORD *)v39 - v41;
          LOWORD(v624) = v43;
          v44 = *((_WORD *)v39 + 1);
          if ( v44 == (_WORD)v633 )
            v45 = 0x8000;
          else
            v45 = v44 - v42;
          WORD1(v624) = v45;
          v46 = *((_WORD *)v39 + 2);
          if ( v46 == (_WORD)v644 )
            WORD2(v624) = 0x7FFF;
          else
            WORD2(v624) = v46 - v41;
          v47 = *((_WORD *)v39 + 3);
          if ( v47 == 0x7FFF )
            HIWORD(v624) = 0x7FFF;
          else
            HIWORD(v624) = v47 - v42;
          v48 = &v624;
          goto LABEL_60;
        }
      }
    }
    else
    {
      if ( (*(_BYTE *)v585 & 8) == 0 )
      {
        os_raise(0xFFFFFFFFLL, 0);
        v33 = v599;
        v34 = v585;
        v32 = a8;
      }
      v37 = (_DWORD *)(v32 + 12);
      v38 = *(_DWORD *)(*(_QWORD *)(v34 + 8) + 12LL);
      *(_DWORD *)(v32 + 12) = v38;
      *(_DWORD *)(v32 + 28) = 2;
      v49 = *(_DWORD **)(v34 + 8);
      LOWORD(v618) = (unsigned int)(*v49 + 0x8000) >> 16;
      v73 = (*(_BYTE *)v34 & 0x20) == 0;
      HIWORD(v618) = (unsigned int)(v49[1] + 0x8000) >> 16;
      if ( !v73 )
      {
        v48 = v648;
LABEL_60:
        *v35 = v48;
      }
    }
    v50 = v596;
    v51 = *(_QWORD *)(v596 + 32);
    if ( !v51 )
      goto LABEL_75;
    v52 = *(_BYTE *)(v596 + 65);
    switch ( v52 )
    {
      case 4:
        v53 = 4 * v38;
        v54 = *(unsigned __int8 *)(v53 + v51 + 2)
            + ((*(unsigned __int8 *)(v53 + v51 + 1) + (*(unsigned __int8 *)(v53 + v51) << 8)) << 8);
        v55 = *(unsigned __int8 *)(v53 + v51 + 3);
        break;
      case 3:
        v56 = 3 * v38;
        v54 = *(unsigned __int8 *)(v56 + v51 + 1) + (*(unsigned __int8 *)(v56 + v51) << 8);
        v55 = *(unsigned __int8 *)(v56 + v51 + 2);
        break;
      case 2:
        v57 = 2 * v38;
        v54 = *(unsigned __int8 *)(v57 + v51);
        v55 = *(unsigned __int8 *)(v57 + v51 + 1);
        break;
      case 1:
        v58 = *(unsigned __int8 *)(v38 + v51);
        goto LABEL_71;
      default:
        goto LABEL_75;
    }
    v58 = v55 + (v54 << 8);
LABEL_71:
    if ( v58 )
    {
      v59 = *(_QWORD *)(v596 + 24) + v58;
      goto LABEL_74;
    }
LABEL_75:
    v60 = v620;
    *(_DWORD *)(v50 + 60) = *v37;
    if ( !*(_DWORD *)(v60 + 12) )
      goto LABEL_1108;
    v61 = 0;
    do
    {
      v62 = v61++;
      *(_QWORD *)(32 * v62 + a8 + 16) = 0;
    }
    while ( v61 != 11 );
    v59 = InvokeManageCString(*(_DWORD *)(v60 + 12), *(_DWORD *)(a8 + 28), v50, *(_QWORD *)(v585 + 16), (__int64)v33);
    v578 = (char *)v59;
    if ( !v59 )
      goto LABEL_1108;
    goto LABEL_79;
  }
  v50 = v596;
  v37 = (_DWORD *)(a8 + 12);
  *(_DWORD *)(a8 + 12) = 0;
  *(_DWORD *)(a8 + 28) = 1;
  *(_DWORD *)v33 = *(_DWORD *)(v50 + 56);
  v59 = *(_QWORD *)v50;
LABEL_74:
  v578 = (char *)v59;
  if ( !v59 )
    goto LABEL_75;
LABEL_79:
  v588 = 0;
  v602 = 0;
  v609 = 0;
  v623 = 0;
  v587 = 0;
  v605 = 0;
  v589 = 0;
  *(_QWORD *)a8 = v59;
  v63 = 0;
  v603 = 0;
  v606 = 0;
  v594 = 0;
  v586 = 1;
  v556 = 0;
  if ( v595 )
  {
    if ( (_DWORD)gsmat != 1
      || (int)xmmword_1400B6F08 > 0x10000
      || SHIDWORD(xmmword_1400B6F08) > 0x10000
      || (v64 = TfmLockPt_noTfm, !T1globalColoring) )
    {
      v64 = TfmLockPt1;
    }
  }
  else
  {
    v64 = TfmLockPt3;
  }
  v599 = v64;
  if ( !v600 )
  {
    if ( *v597 )
      ((void (__fastcall *)(__int64 *))*v597)(v593);
    v63 = 0;
  }
  v616 = 0;
  v65 = (unsigned __int64)v13;
LABEL_91:
  v66 = (unsigned __int64)v578;
LABEL_92:
  v29 = a1;
LABEL_98:
  v67 = a8;
LABEL_99:
  if ( *(_DWORD *)(v29 + 964) )
  {
    if ( v66 - *(_QWORD *)(32LL * v63 + a8) == *(_DWORD *)(32LL * v63 + a8 + 24) )
    {
      v68 = 11;
      if ( (int)v556 <= 0 )
        v68 = 14;
    }
    else
    {
      if ( v66 < *(_QWORD *)(v596 + 72) || v66 > *(_QWORD *)(v596 + 80) )
        goto LABEL_1112;
      v69 = *(unsigned __int8 *)v66;
      v584 = v69;
      v578 = (char *)(v66 + 1);
      if ( v69 != 11 && v69 != 14 )
        goto LABEL_112;
      v68 = 0;
    }
  }
  else
  {
    if ( !(unsigned int)GetDecryptInner(v596, v67, (unsigned int)v63, v66) )
      goto LABEL_1112;
    v68 = (unsigned __int8)*v578++;
  }
  v584 = v68;
LABEL_112:
  v70 = (size_t)(v13 + 513);
  Size = (size_t)(v13 + 513);
  while ( 1 )
  {
    if ( v65 < (unsigned __int64)v13 )
    {
      os_raise(0xFFFFFFFFLL, 0);
      v70 = Size;
    }
    v71 = v584;
    v66 = v70;
    if ( v584 > 0x10 )
    {
      if ( v584 <= 0x18 )
      {
        if ( v584 == 24 )
          goto LABEL_1039;
        if ( v584 != 17 )
        {
          if ( v584 == 18 )
          {
            lockFixMapOk = 0;
            goto LABEL_688;
          }
          v360 = v584 - 19;
          if ( v584 != 19 )
          {
            v360 = v584 - 20;
            switch ( v584 )
            {
              case 0x14u:
                if ( (unsigned int *)v65 == v13 )
                {
                  v29 = a1;
                  goto LABEL_826;
                }
                v606 = 1;
                goto LABEL_672;
              case 0x15u:
                v29 = a1;
                if ( v65 - (_QWORD)v13 == 8 )
                {
                  v296 = *v13;
                  goto LABEL_499;
                }
                v297 = v13[2];
                v296 = v13[1];
LABEL_649:
                v351 = v13;
                v66 = (unsigned __int64)(v13 + 6);
                break;
              case 0x16u:
                v351 = v13;
                if ( v65 - (_QWORD)v13 == 4 )
                {
                  v296 = *v13;
                  *v13 = -1;
                }
                else
                {
                  v296 = v13[1];
                }
                v29 = a1;
                v66 = (unsigned __int64)(v13 + 6);
                v297 = 0;
                break;
              default:
                lockFixMapOk = 0;
LABEL_672:
                v29 = a1;
                if ( *(_WORD *)(a1 + 960) != 2 )
                {
                  if ( !v595 )
                    goto LABEL_575;
                  v10 = v585;
                  RXLock(v13, v587, *(_QWORD *)(v585 + 16));
                  goto LABEL_368;
                }
                v361 = (__int64)(v65 - (_QWORD)v13) >> 2;
                v360 = v361 & 1;
                if ( (int)v360 < (int)v361 )
                {
                  v362 = v605;
                  v363 = 0;
                  LODWORD(v70) = v361 & 1;
                  do
                  {
                    if ( v362 + v589 >= 96 )
                      goto LABEL_148;
                    v364 = v362 + v589;
                    v71 = (int)v70;
                    v365 = v13[(int)v70] + v363;
                    v66 = v13[(int)v70 + 1];
                    v661[2 * v364] = v365;
                    v661[2 * v364 + 1] = v66;
                    if ( v364 >= 0x60 )
                      goto LABEL_1114;
                    ++v362;
                    *((_BYTE *)&v661[192] + v364) = 0;
                    v363 = v66 + v365;
                    v605 = v362;
                    v70 = (unsigned int)(v70 + 2);
                  }
                  while ( (int)v70 < (int)v361 );
                  v29 = a1;
                }
                if ( (v361 & 1) != 0 )
                  goto LABEL_680;
                if ( *(_DWORD *)(v29 + 948) )
                {
                  if ( v603 )
                    goto LABEL_769;
                  if ( !v606 )
                    goto LABEL_575;
                  goto LABEL_826;
                }
                goto LABEL_697;
            }
            v70 = 28;
            goto LABEL_651;
          }
          if ( (unsigned int *)v65 == v13 )
            goto LABEL_768;
          v603 = 1;
          goto LABEL_672;
        }
        v452 = v13[3];
        v13[5] -= v452;
        v453 = v13[1];
        v454 = v452 - v453;
        v455 = v13[2];
        v13[4] -= v455;
        v456 = v453 - HIDWORD(v583);
        v13[3] = v454;
        v457 = v455 - *v13;
        *v13 = v587 + *v13 - v583;
        v13[2] = v457;
        v13[1] = v456;
LABEL_1039:
        v29 = a1;
        if ( !*(_DWORD *)(a1 + 948) )
          goto LABEL_148;
        v517 = 0;
        v518 = (__int64)(v65 - (_QWORD)v13) >> 2;
        v586 = 0;
        LODWORD(Size) = v518 - 6;
        if ( (int)v518 - 6 < 0 )
          goto LABEL_1002;
        while ( 1 )
        {
          if ( (__int64 (__fastcall *)())lockSlopesInited == TfmLockPt_noTfm )
          {
            v646 = 0;
            v645 = 0;
            v642 = 0;
            if ( !T1globalColoring )
            {
              os_raise(0xFFFFFFFFLL, 0);
              v517 = v586;
            }
            v519 = v583 + v13[v517];
            LODWORD(v646) = Map(qword_1400B6080, v519);
            v520 = v627[v586 + 2] + v519;
            LODWORD(v645) = Map(qword_1400B6080, v520);
            v521 = v627[v586 + 4] + v520;
            v522 = Map(qword_1400B6080, v521);
            LODWORD(v583) = v521;
            LODWORD(v642) = v522;
            v523 = HIDWORD(v583) + v627[v586 + 1];
            HIDWORD(v646) = Map(qword_1400B6090, v523);
            v524 = v627[v586 + 3] + v523;
            HIDWORD(v645) = Map(qword_1400B6090, v524);
            v525 = v627[v586 + 5] + v524;
            HIDWORD(v642) = Map(qword_1400B6090, v525);
            HIDWORD(v583) = v525;
            v526 = (void (__fastcall *)(unsigned __int64 *, __int64 *, __int64 *, unsigned __int64 *, __int64 *))v597[3];
            if ( v526 )
              v526(&v592, &v646, &v645, &v642, v593);
            v527 = v642;
            v13 = v627;
          }
          else
          {
            v528 = v517;
            v13[v517] += v583;
            v13[v517 + 1] += HIDWORD(v583);
            v529 = v13[v517 + 1];
            v530 = v13[v517];
            v13[v517 + 3] += v529;
            v13[v517 + 2] += v530;
            v531 = v13[v517 + 3];
            v532 = v13[v528 + 2];
            v13[v528 + 5] += v531;
            v13[v528 + 4] += v532;
            v533 = v13[v528 + 5];
            LODWORD(v583) = v13[v528 + 4];
            HIDWORD(v583) = v533;
            v635 = __PAIR64__(v529, v530);
            v634 = __PAIR64__(v531, v532);
            v632 = __PAIR64__(v533, v583);
            if ( T1globalColoring )
            {
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v635, &v635);
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v634, &v634);
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v632, &v632);
              v534 = (void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, __int64 *))v597[3];
              if ( v534 )
                v534(&v592, &v635, &v634, &v632, v593);
            }
            else
            {
              GCLine(v26, v635);
              GCLine(v634, v632);
              v26 = v583;
            }
            v527 = v632;
          }
          v535 = v586;
          v592 = v527;
          if ( v518 == v586 + 8 )
            break;
          v517 = v586 + 6;
          v586 = v517;
          if ( v517 > (int)Size )
            goto LABEL_1001;
        }
        v65 = (unsigned __int64)(v13 + 2);
        *v13 = v13[v586 + 6];
        v13[1] = v13[v535 + 7];
        goto LABEL_1056;
      }
      switch ( v584 )
      {
        case 0x19u:
          if ( v65 < (unsigned __int64)v13 )
            goto LABEL_148;
          if ( v65 > v70 )
            goto LABEL_148;
          v508 = (__int64)(v65 - (_QWORD)v13) >> 2;
          v598 = (unsigned __int8 *)v508;
          if ( (int)v508 < 8 || (v508 & 1) != 0 || !*(_DWORD *)(a1 + 948) )
            goto LABEL_148;
          v509 = v599;
          v510 = v508 - 6;
          v511 = v593;
          v512 = 0;
          v513 = v597;
          do
          {
            LODWORD(v583) = v13[v512] + v583;
            HIDWORD(v583) += v13[v512 + 1];
            if ( T1globalColoring )
            {
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, size_t, unsigned __int64))v509)(
                &v583,
                &v592,
                v70,
                v66);
              v514 = (void (__fastcall *)(unsigned __int64 *, __int64 *))v513[2];
              if ( v514 )
                v514(&v592, v511);
            }
            else
            {
              GCLine(v26, v583);
              v26 = v583;
              v592 = v583;
            }
            v512 += 2;
          }
          while ( v512 < v510 );
          LODWORD(v18) = (_DWORD)v647;
          v27 = v643;
          v515 = 0;
          v516 = (int)v598;
          do
          {
            v13[v515] = v13[(int)v515 - 6 + v516];
            v515 = (unsigned int)(v515 + 1);
          }
          while ( (int)v515 < 6 );
          v65 = (unsigned __int64)(v13 + 6);
          goto LABEL_1039;
        case 0x1Au:
          v615 = 0;
          v612 = 0;
          v607 = 0;
          if ( v65 < (unsigned __int64)v13 )
            goto LABEL_148;
          if ( v65 > v70 )
            goto LABEL_148;
          v500 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( !(_DWORD)v500 )
            goto LABEL_148;
          v29 = a1;
          if ( !*(_DWORD *)(a1 + 948) )
            goto LABEL_148;
          v501 = 0;
          v574 = 0;
          if ( (int)v500 > 0 )
          {
            while ( 2 )
            {
              v502 = v500 - v501;
              LODWORD(Size) = ((_BYTE)v500 - (_BYTE)v501) & 1;
              if ( (((_BYTE)v500 - (_BYTE)v501) & 1) != 0 )
              {
                if ( v502 < 5 )
                  goto LABEL_148;
                v503 = HIDWORD(v583) + v13[v501 + 1];
                v504 = v583 + v13[v501];
                v505 = v504 + v13[v501 + 2];
                HIDWORD(v612) = v503 + v13[v501 + 3];
                v506 = v13[v501 + 4] + HIDWORD(v612);
              }
              else
              {
                if ( v502 < 4 )
                  goto LABEL_148;
                v504 = v583;
                v503 = HIDWORD(v583) + v13[v501];
                v505 = v583 + v13[v501 + 1];
                HIDWORD(v612) = v503 + v13[v501 + 2];
                v506 = v13[v501 + 3] + HIDWORD(v612);
              }
              v607 = __PAIR64__(v506, v505);
              LODWORD(v612) = v505;
              v615 = __PAIR64__(v503, v504);
              v583 = __PAIR64__(v506, v505);
              if ( (__int64 (__fastcall *)())lockSlopesInited == TfmLockPt_noTfm )
              {
                v583 = v607;
                LODWORD(v615) = Map(qword_1400B6080, v504);
                HIDWORD(v615) = Map(qword_1400B6090, HIDWORD(v615));
                LODWORD(v612) = Map(qword_1400B6080, (unsigned int)v612);
                HIDWORD(v612) = Map(qword_1400B6090, HIDWORD(v612));
                LODWORD(v607) = Map(qword_1400B6080, (unsigned int)v607);
                HIDWORD(v607) = Map(qword_1400B6090, HIDWORD(v607));
                v507 = (void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, __int64 *, unsigned __int64 *, __int64 *))v597[3];
              }
              else
              {
                if ( !T1globalColoring )
                {
                  GCLine(v26, v615);
                  GCLine(v612, v607);
                  v26 = v583;
                  goto LABEL_1020;
                }
                ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v615, &v615);
                ((void (__fastcall *)(__int64 *, __int64 *))v599)(&v612, &v612);
                ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v607, &v607);
                v507 = (void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, __int64 *, unsigned __int64 *, __int64 *))v597[3];
              }
              if ( v507 )
                v507(&v592, &v615, &v612, &v607, v593);
LABEL_1020:
              v592 = v607;
              if ( (_DWORD)Size )
                v501 = v574 + 5;
              else
                v501 = v574 + 4;
              v574 = v501;
              if ( v501 >= (int)v500 )
                goto LABEL_1001;
              continue;
            }
          }
LABEL_1002:
          v586 = 0;
          goto LABEL_575;
        case 0x1Bu:
          v619 = 0;
          v617 = 0;
          v611 = 0;
          if ( v65 < (unsigned __int64)v13 )
            goto LABEL_148;
          if ( v65 > v70 )
            goto LABEL_148;
          v494 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( !(_DWORD)v494 )
            goto LABEL_148;
          v29 = a1;
          if ( !*(_DWORD *)(a1 + 948) )
            goto LABEL_148;
          v495 = 0;
          v573 = 0;
          if ( (int)v494 <= 0 )
            goto LABEL_1002;
          while ( 2 )
          {
            if ( (((_BYTE)v494 - (_BYTE)v495) & 1) != 0 )
            {
              if ( v495 || (int)v494 < 5 )
                goto LABEL_148;
              v495 = 1;
              v496 = *v13 + HIDWORD(v583);
              v573 = 1;
            }
            else
            {
              if ( (int)v494 - v495 < 4 )
                goto LABEL_148;
              v496 = HIDWORD(v583);
            }
            v497 = v583 + v13[v495];
            v498 = v497 + v13[v495 + 1];
            HIDWORD(v611) = v13[v495 + 2] + v496;
            v617 = __PAIR64__(HIDWORD(v611), v498);
            LODWORD(v611) = v13[v495 + 3] + v498;
            v619 = __PAIR64__(v496, v497);
            v583 = v611;
            if ( (__int64 (__fastcall *)())lockSlopesInited == TfmLockPt_noTfm )
            {
              v583 = v611;
              LODWORD(v619) = Map(qword_1400B6080, v497);
              HIDWORD(v619) = Map(qword_1400B6090, HIDWORD(v619));
              LODWORD(v617) = Map(qword_1400B6080, (unsigned int)v617);
              HIDWORD(v617) = Map(qword_1400B6090, HIDWORD(v617));
              LODWORD(v611) = Map(qword_1400B6080, (unsigned int)v611);
              HIDWORD(v611) = Map(qword_1400B6090, HIDWORD(v611));
              v499 = (void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, __int64 *))v597[3];
            }
            else
            {
              if ( !T1globalColoring )
              {
                GCLine(v26, v619);
                GCLine(v617, v611);
                v26 = v583;
                goto LABEL_1000;
              }
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v619, &v619);
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v617, &v617);
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v611, &v611);
              v499 = (void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, __int64 *))v597[3];
            }
            if ( v499 )
              v499(&v592, &v619, &v617, &v611, v593);
LABEL_1000:
            v592 = v611;
            v495 = v573 + 4;
            v573 = v495;
            if ( v495 >= (int)v494 )
              goto LABEL_1001;
            continue;
          }
        case 0x1Cu:
          if ( v65 >= v70 )
            goto LABEL_148;
          if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
            goto LABEL_1112;
          v591 = *v578;
          v582 = (unsigned __int8 *)(v578 + 1);
          if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v582) )
            goto LABEL_1112;
          v493 = v582;
          v66 = (unsigned __int64)(v582 + 1);
          v578 = (char *)(v582 + 1);
          if ( v65 < (unsigned __int64)v13 )
            goto LABEL_148;
          *(_DWORD *)v65 = (*v493 | (v591 << 8)) << 16;
          v65 += 4LL;
          goto LABEL_979;
        case 0x1Du:
          if ( v65 < (unsigned __int64)(v13 + 1) )
            goto LABEL_148;
          if ( v65 > v70 )
            goto LABEL_148;
          v65 -= 4LL;
          v337 = (unsigned int)(*(_DWORD *)(a1 + 816) + *(__int16 *)(v65 + 2));
          v565 = v337;
          if ( (int)v337 >= *(_DWORD *)(a1 + 820) || (int)v337 < 0 || v556 == 10 )
            goto LABEL_148;
          v584 = 5;
          v338 = *(_QWORD *)(v596 + 48);
          v339 = *(_QWORD *)(v596 + 40);
          v340 = *(_BYTE *)(v596 + 66);
LABEL_943:
          v474 = 32LL * (int)v556;
          Size = v474;
          v475 = (_DWORD)v578 - *(_DWORD *)(v474 + a8);
          *(_QWORD *)(v474 + a8 + 16) = v578;
          v476 = (_DWORD *)(v474 + a8 + 56);
          *(_DWORD *)(v474 + a8 + 8) = v475;
          v581 = v476;
          *v476 = 0;
          if ( v338 )
          {
            switch ( v340 )
            {
              case 4:
                v477 = 4 * (int)v337;
                v478 = *(unsigned __int8 *)(v477 + v338 + 3);
                v479 = (*(unsigned __int8 *)(v477 + v338 + 2)
                      + (((*(unsigned __int8 *)(v477 + v338) << 8) + *(unsigned __int8 *)(v477 + v338 + 1)) << 8)) << 8;
                goto LABEL_950;
              case 3:
                v480 = 3 * (int)v337;
                v478 = *(unsigned __int8 *)(v480 + v338 + 2);
                v479 = ((*(unsigned __int8 *)(v480 + v338) << 8) + *(unsigned __int8 *)(v480 + v338 + 1)) << 8;
                goto LABEL_950;
              case 2:
                v481 = 2 * (int)v337;
                v479 = *(unsigned __int8 *)(v481 + v338 + 1);
                v478 = *(unsigned __int8 *)(v481 + v338) << 8;
LABEL_950:
                LODWORD(v337) = v565;
                v482 = v478 + v479;
LABEL_953:
                if ( v482 )
                {
                  v578 = (char *)(v339 + v482);
                  if ( *(_DWORD *)(a1 + 964) )
                  {
                    switch ( v340 )
                    {
                      case 4:
                        v483 = 4 * (int)v337;
                        v484 = *(unsigned __int8 *)(v483 + v338 + 6)
                             + ((*(unsigned __int8 *)(v483 + v338 + 5) + (*(unsigned __int8 *)(v483 + v338 + 4) << 8)) << 8);
                        v485 = *(unsigned __int8 *)(v483 + v338 + 7);
                        goto LABEL_961;
                      case 3:
                        v486 = 3 * (int)v337;
                        v484 = *(unsigned __int8 *)(v486 + v338 + 4) + (*(unsigned __int8 *)(v486 + v338 + 3) << 8);
                        v485 = *(unsigned __int8 *)(v486 + v338 + 5);
                        goto LABEL_961;
                      case 2:
                        v487 = 2 * (int)v337;
                        v484 = *(unsigned __int8 *)(v487 + v338 + 2);
                        v485 = *(unsigned __int8 *)(v487 + v338 + 3);
LABEL_961:
                        v488 = v485 + (v484 << 8);
                        break;
                      default:
                        v488 = *(unsigned __int8 *)((unsigned int)v337 + v338 + 1);
                        break;
                    }
                    *(_DWORD *)(v474 + a8 + 56) = v488 - v482;
                  }
                  v66 = v339 + v482;
LABEL_965:
                  v67 = a8;
                  ++v556;
                  *(_DWORD *)(v474 + a8 + 44) = v565;
                  *(_DWORD *)(v474 + a8 + 60) = v584;
                  *(_QWORD *)(v474 + a8 + 32) = v66;
                  goto LABEL_966;
                }
                v476 = v581;
                break;
              case 1:
                v482 = *(unsigned __int8 *)(v337 + v338);
                goto LABEL_953;
            }
          }
          v489 = v596;
          v490 = v620;
          *(_DWORD *)(v596 + 60) = v337;
          if ( !*(_DWORD *)(v490 + 12) )
            goto LABEL_1108;
          v491 = 0;
          do
          {
            v492 = v491++;
            *(_QWORD *)(32 * v492 + a8 + 16) = 0;
          }
          while ( v491 != 11 );
          v578 = (char *)InvokeManageCString(*(_DWORD *)(v490 + 12), v584, v489, *(_QWORD *)(v585 + 16), (__int64)v476);
          v66 = (unsigned __int64)v578;
          if ( !v578 )
          {
LABEL_1108:
            os_raise(0xFFFFFFFFLL, 0);
            return 4294967285LL;
          }
          v474 = Size;
          goto LABEL_965;
        case 0x1Eu:
          v462 = 0;
          goto LABEL_915;
        case 0x1Fu:
          v462 = 1;
LABEL_915:
          v614 = 0;
          v610 = 0;
          v601 = 0;
          if ( v65 < (unsigned __int64)v13 )
            goto LABEL_148;
          if ( v65 > v66 )
            goto LABEL_148;
          v463 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( (int)v463 < 4 || !*(_DWORD *)(a1 + 948) )
            goto LABEL_148;
          v464 = 0;
          v572 = 0;
          LODWORD(Size) = v463 - 4;
          while ( 2 )
          {
            if ( (int)v463 - v464 < 4 )
              goto LABEL_148;
            v465 = v464;
            v466 = v464 + 5;
            v73 = v462 == 0;
            v467 = v583;
            v468 = v13[v464];
            v469 = v13[v465 + 1];
            v470 = v13[v465 + 2];
            if ( v73 )
            {
              LODWORD(v610) = v469 + v583;
              v472 = v13[v465 + 3] + v469 + v583;
              LODWORD(v614) = v583;
              HIDWORD(v614) = HIDWORD(v583) + v468;
              HIDWORD(v610) = HIDWORD(v583) + v468 + v470;
              v601 = __PAIR64__(HIDWORD(v610), v472);
              if ( v466 == (_DWORD)v463 )
                HIDWORD(v601) = HIDWORD(v583) + v468 + v470 + v13[v465 + 4];
              v584 = 1;
            }
            else
            {
              v467 = v468 + v583;
              HIDWORD(v614) = HIDWORD(v583);
              HIDWORD(v610) = v470 + HIDWORD(v583);
              v471 = v13[v465 + 3] + v470 + HIDWORD(v583);
              LODWORD(v614) = v468 + v583;
              LODWORD(v610) = v468 + v583 + v469;
              v601 = __PAIR64__(v471, v610);
              if ( v466 == (_DWORD)v463 )
                LODWORD(v601) = v13[v465 + 4] + v467 + v469;
              v584 = 0;
            }
            v583 = v601;
            if ( (__int64 (__fastcall *)())lockSlopesInited == TfmLockPt_noTfm )
            {
              v583 = v601;
              LODWORD(v614) = Map(qword_1400B6080, v467);
              HIDWORD(v614) = Map(qword_1400B6090, HIDWORD(v614));
              LODWORD(v610) = Map(qword_1400B6080, (unsigned int)v610);
              HIDWORD(v610) = Map(qword_1400B6090, HIDWORD(v610));
              LODWORD(v601) = Map(qword_1400B6080, (unsigned int)v601);
              HIDWORD(v601) = Map(qword_1400B6090, HIDWORD(v601));
              v473 = (void (__fastcall *)(unsigned __int64 *, __int64 *, __int64 *, unsigned __int64 *, __int64 *))v597[3];
            }
            else
            {
              if ( !T1globalColoring )
              {
                GCLine(v26, v614);
                GCLine(v610, v601);
                v26 = v583;
                goto LABEL_935;
              }
              ((void (__fastcall *)(__int64 *, __int64 *))v599)(&v614, &v614);
              ((void (__fastcall *)(__int64 *, __int64 *))v599)(&v610, &v610);
              ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v601, &v601);
              v473 = (void (__fastcall *)(unsigned __int64 *, __int64 *, __int64 *, unsigned __int64 *, __int64 *))v597[3];
            }
            if ( v473 )
              v473(&v592, &v614, &v610, &v601, v593);
LABEL_935:
            v464 = v572 + 4;
            v462 = v584;
            v592 = v601;
            v572 = v464;
            if ( v464 > (int)Size )
            {
              v586 = 0;
              goto LABEL_574;
            }
            continue;
          }
      }
      if ( v65 < (unsigned __int64)v13 || v65 >= v70 )
        goto LABEL_148;
      v29 = a1;
      v66 = (unsigned __int64)v578;
      *(_DWORD *)v65 = (v584 - 139) << 16;
      v65 += 4LL;
      if ( (unsigned int)v71 > 0xF6 )
      {
        if ( (unsigned int)v71 > 0xFA )
        {
          if ( (unsigned int)v71 > 0xFE )
          {
            if ( (unsigned int)GetDecryptInner(v596, a8, v556, v578) )
            {
              v458 = *v578;
              v579 = (unsigned __int8 *)(v578 + 1);
              v577 = v458;
              if ( (unsigned int)GetDecryptInner(v596, a8, v556, v579) )
              {
                v604 = *v579;
                if ( (unsigned int)GetDecryptInner(v596, a8, v556, v579 + 1) )
                {
                  v591 = v579[1];
                  v580 = v579 + 2;
                  if ( (unsigned int)GetDecryptInner(v596, a8, v556, v580) )
                  {
                    v459 = v580;
                    v29 = a1;
                    v66 = (unsigned __int64)(v580 + 1);
                    v578 = (char *)(v580 + 1);
                    v460 = *v459 | ((v591 | ((v604 | (v577 << 8)) << 8)) << 8);
                    if ( *(_WORD *)(a1 + 960) == 1 && (unsigned int)(v460 + 32000) <= 0xFA00 )
                    {
                      *(_DWORD *)(v65 - 4) = v460 << 16;
                    }
                    else
                    {
                      v461 = v616;
                      *(_DWORD *)(v65 - 4) = v460;
                      if ( *(_WORD *)(a1 + 960) == 1 )
                        v461 = 1;
                      v616 = v461;
                    }
                    goto LABEL_577;
                  }
                }
              }
            }
            goto LABEL_1112;
          }
          if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
            goto LABEL_1112;
          v66 = (unsigned __int64)(v578 + 1);
          *(_DWORD *)(v65 - 4) = (-108 - ((unsigned __int8)*v578 | ((v584 << 8) - 64256))) << 16;
        }
        else
        {
          if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
            goto LABEL_1112;
          v66 = (unsigned __int64)(v578 + 1);
          *(_DWORD *)(v65 - 4) = (((unsigned __int8)*v578 << 16) | ((v584 + 9) << 24)) + 7077888;
        }
        v29 = a1;
        v578 = (char *)v66;
        goto LABEL_577;
      }
LABEL_97:
      v63 = v556;
      goto LABEL_98;
    }
    if ( v584 == 16 )
    {
      if ( v65 < (unsigned __int64)(v13 + 1) || v65 > v70 )
        goto LABEL_148;
      v352 = a1;
      v353 = v65 - 4;
      Size = v353;
      v354 = *(__int16 *)(v353 + 2);
      v566 = *(__int16 *)(v353 + 2);
      if ( !*(_DWORD *)(a1 + 964) )
      {
        v359 = *(_DWORD *)(a1 + 644);
        if ( !v359 && v353 + 4 * v354 >= v66 )
          goto LABEL_148;
        if ( (unsigned __int64)&v13[(unsigned int)(v354 * v359)] > v353 )
        {
          os_raise(0xFFFFFFFFLL, 0);
          v352 = a1;
        }
        v123 = DoBlend((_DWORD)v13, v353, (int)v352 + 648, *(_DWORD *)(v352 + 644), v566);
        goto LABEL_245;
      }
      if ( v354 > (__int64)(v353 - (_QWORD)v13) >> 2 )
        goto LABEL_148;
      if ( !*(_QWORD *)(a1 + 976) )
      {
        os_raise(0xFFFFFFFFLL, 0);
        v352 = a1;
      }
      v355 = *(_QWORD *)(v352 + 976);
      v356 = *(_DWORD *)(v352 + 984);
      LODWORD(v598) = v356;
      if ( *(_DWORD *)v355 && *(_DWORD *)(v355 + 16) == v629 && *(_DWORD *)(v355 + 20) == v356 )
      {
        if ( !v356
          || (v357 = memcmp_0(*(const void **)(v352 + 992), *(const void **)(v355 + 24), 4LL * v356), v352 = a1, !v357) )
        {
LABEL_627:
          v123 = AdobeCFFDoCharStringBlend(*(_QWORD *)(v352 + 976), v566, Size, v13);
LABEL_245:
          v65 = v123;
          if ( !v123 )
            goto LABEL_148;
          goto LABEL_227;
        }
        v356 = (unsigned int)v598;
      }
      v358 = AdobeCFFBuildBlendVector(v355, v629, v356, *(_QWORD *)(v352 + 992));
      if ( v358 )
      {
        if ( v358 != -67108864 )
          goto LABEL_148;
LABEL_1110:
        os_raise(0xFFFFFFFFLL, 0);
        return 4294967292LL;
      }
      v352 = a1;
      goto LABEL_627;
    }
    if ( v584 <= 8 )
    {
      if ( v584 == 8 )
        goto LABEL_1039;
      if ( !v584 )
        goto LABEL_148;
      if ( v584 != 1 )
      {
        if ( v584 == 2 )
          goto LABEL_148;
        if ( v584 != 3 )
        {
          if ( v584 != 4 )
          {
            if ( v584 != 5 )
            {
              v29 = a1;
              if ( *(_DWORD *)(a1 + 948) && v65 >= (unsigned __int64)v13 && v65 <= v70 )
              {
                LODWORD(v598) = 0;
                v342 = (__int64)(v65 - (_QWORD)v13) >> 2;
                if ( (int)v342 > 0 )
                {
                  v343 = v584 == 6;
                  v344 = (int)v598;
                  v345 = v599;
                  v346 = v597;
                  do
                  {
                    v347 = (unsigned int)v583;
                    v348 = v13[v344];
                    v349 = HIDWORD(v583);
                    if ( v343 )
                    {
                      v347 = v348 + (unsigned int)v583;
                      LODWORD(v583) = v348 + v583;
                    }
                    else
                    {
                      v349 = v348 + HIDWORD(v583);
                      HIDWORD(v583) += v348;
                    }
                    v343 ^= 1u;
                    if ( T1globalColoring )
                    {
                      if ( (__int64 (__fastcall *)())lockSlopesInited == TfmLockPt_noTfm )
                      {
                        if ( v343 )
                          HIDWORD(v592) = Map(qword_1400B6090, v349);
                        else
                          LODWORD(v592) = Map(qword_1400B6080, v347);
                      }
                      else
                      {
                        ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, size_t, unsigned __int64))v345)(
                          &v583,
                          &v592,
                          v70,
                          v66);
                      }
                      v350 = (void (__fastcall *)(unsigned __int64 *, __int64 *))v346[2];
                      if ( v350 )
                        v350(&v592, v593);
                    }
                    else
                    {
                      GCLine(v26, v583);
                      v26 = v583;
                      v592 = v583;
                    }
                    ++v344;
                  }
                  while ( v344 < (int)v342 );
                  LODWORD(v18) = (_DWORD)v647;
                  v27 = v643;
                  v29 = a1;
                }
                v586 = 0;
                goto LABEL_575;
              }
              goto LABEL_148;
            }
LABEL_1056:
            v29 = a1;
            if ( !*(_DWORD *)(a1 + 948) || v65 < (unsigned __int64)v13 || v65 > (unsigned __int64)(v13 + 513) )
              goto LABEL_148;
            LODWORD(Size) = 0;
            v536 = (__int64)(v65 - (_QWORD)v13) >> 2;
            if ( (int)v536 > 0 )
            {
              v537 = Size;
              v538 = v599;
              v539 = v597;
              v540 = v593;
              do
              {
                LODWORD(v583) = v13[v537] + v583;
                HIDWORD(v583) += v13[v537 + 1];
                if ( T1globalColoring )
                {
                  ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, size_t, unsigned __int64))v538)(
                    &v583,
                    &v592,
                    v70,
                    v66);
                  v541 = (void (__fastcall *)(unsigned __int64 *, __int64 *))v539[2];
                  if ( v541 )
                    v541(&v592, v540);
                }
                else
                {
                  GCLine(v26, v583);
                  v26 = v583;
                  v592 = v583;
                }
                v537 += 2;
              }
              while ( v537 < (int)v536 );
              LODWORD(v18) = (_DWORD)v647;
              v27 = v643;
LABEL_1001:
              v29 = a1;
            }
            goto LABEL_1002;
          }
          v29 = a1;
          v66 = (unsigned __int64)(v13 + 6);
          v296 = 0;
          v351 = v13;
          v70 = 28;
          if ( v65 - (_QWORD)v13 == 4 )
          {
            v297 = *v13;
            *v13 = -1;
          }
          else
          {
            v297 = v13[1];
          }
LABEL_651:
          *(_DWORD *)v66 = v296;
          v65 = (unsigned __int64)(v13 + 9);
          v351[7] = v297;
LABEL_652:
          v71 = v585;
          goto LABEL_653;
        }
        goto LABEL_672;
      }
LABEL_688:
      v29 = a1;
      if ( *(_WORD *)(a1 + 960) != 2 )
      {
        if ( !v595 || v608 >= 0 )
          goto LABEL_575;
        v10 = v585;
        RBLock(v13, v588, a1, *(_QWORD *)(v585 + 16));
        goto LABEL_368;
      }
      v366 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( (v366 & 1) < (int)v366 )
      {
        v367 = v589;
        v368 = 0;
        v369 = v366 & 1;
        do
        {
          if ( v367 + v605 >= 96 )
            goto LABEL_148;
          v370 = v367;
          v371 = v13[v369] + v368;
          v372 = v13[v369 + 1];
          v661[2 * v367] = v371;
          v661[2 * v367 + 1] = v372;
          if ( (unsigned __int64)v367 >= 0x60 )
LABEL_1114:
            ((void (__noreturn *)(void))_report_rangecheckfailure)();
          ++v367;
          *((_BYTE *)&v661[192] + v370) = 0;
          v368 = v372 + v371;
          v589 = v367;
          v369 += 2;
        }
        while ( v369 < (int)v366 );
        v29 = a1;
      }
      if ( (v366 & 1) != 0 )
      {
LABEL_680:
        v303 = *v13 + *(_DWORD *)(v29 + 944);
LABEL_698:
        v65 = (unsigned __int64)(v13 + 4);
        *(_QWORD *)v13 = 0;
        goto LABEL_699;
      }
      if ( *(_DWORD *)(v29 + 948) )
        goto LABEL_575;
LABEL_697:
      v303 = *(_DWORD *)(v29 + 780);
      goto LABEL_698;
    }
    switch ( v584 )
    {
      case 9u:
        if ( T1globalColoring )
        {
          if ( !v586 )
          {
            v341 = (void (__fastcall *)(__int64 *, _QWORD, size_t, size_t))v597[4];
            if ( v341 )
              v341(v593, v584 - 9, v70, v70);
          }
          goto LABEL_581;
        }
        GCLine(v583, v27);
LABEL_574:
        v29 = a1;
        goto LABEL_575;
      case 0xAu:
        if ( v556 == 10 )
          goto LABEL_148;
        if ( v65 < (unsigned __int64)(v13 + 1) )
          goto LABEL_148;
        if ( v65 > (unsigned __int64)(v13 + 513) )
          goto LABEL_148;
        v65 -= 4LL;
        v337 = (unsigned int)(*(_DWORD *)(a1 + 808) + *(__int16 *)(v65 + 2));
        v565 = v337;
        if ( (int)v337 >= *(_DWORD *)(a1 + 720) || (int)v337 < 0 )
          goto LABEL_148;
        v584 = 0;
        v338 = *(_QWORD *)(v596 + 16);
        v339 = *(_QWORD *)(v596 + 8);
        v340 = *(_BYTE *)(v596 + 64);
        goto LABEL_943;
      case 0xBu:
        if ( (int)v556 <= 0 )
          goto LABEL_148;
        v67 = a8;
        v63 = v556 - 1;
        v304 = 32LL * (int)--v556;
        Size = v304;
        v66 = *(_QWORD *)(v304 + a8 + 16);
        v578 = (char *)v66;
        if ( v66 )
        {
          v29 = a1;
          goto LABEL_99;
        }
        v305 = *(_DWORD *)(v304 + a8 + 28);
        v306 = *(int *)(v304 + a8 + 12);
        if ( !v305 )
        {
          v307 = v596;
          v308 = *(_QWORD *)(v596 + 16);
          if ( v308 )
          {
            v309 = *(_BYTE *)(v596 + 64);
            switch ( v309 )
            {
              case 4:
                v310 = 4 * (int)v306;
                v311 = *(unsigned __int8 *)(v310 + v308 + 2)
                     + ((*(unsigned __int8 *)(v310 + v308 + 1) + (*(unsigned __int8 *)(v310 + v308) << 8)) << 8);
                v312 = *(unsigned __int8 *)(v310 + v308 + 3);
                goto LABEL_526;
              case 3:
                v313 = 3 * (int)v306;
                v311 = *(unsigned __int8 *)(v313 + v308 + 1) + (*(unsigned __int8 *)(v313 + v308) << 8);
                v312 = *(unsigned __int8 *)(v313 + v308 + 2);
                goto LABEL_526;
              case 2:
                v314 = 2 * (int)v306;
                v311 = *(unsigned __int8 *)(v314 + v308);
                v312 = *(unsigned __int8 *)(v314 + v308 + 1);
LABEL_526:
                v315 = v312 + (v311 << 8);
LABEL_529:
                if ( v315 )
                {
                  v316 = *(_QWORD *)(v596 + 8) + v315;
                  goto LABEL_558;
                }
                break;
              case 1:
                v315 = *(unsigned __int8 *)(v306 + v308);
                goto LABEL_529;
            }
          }
LABEL_560:
          v333 = v620;
          *(_DWORD *)(v307 + 60) = v306;
          if ( !*(_DWORD *)(v333 + 12) )
            goto LABEL_1108;
          v334 = 0;
          do
          {
            v335 = v334++;
            *(_QWORD *)(32 * v335 + a8 + 16) = 0;
          }
          while ( v334 != 11 );
          v316 = InvokeManageCString(
                   *(_DWORD *)(v620 + 12),
                   *(_DWORD *)(v304 + a8 + 28),
                   v307,
                   *(_QWORD *)(v585 + 16),
                   v304 + a8 + 24);
          if ( !v316 )
            goto LABEL_1108;
          v304 = Size;
          v67 = a8;
LABEL_565:
          v336 = *(unsigned int *)(v304 + v67 + 8);
          *(_QWORD *)(v304 + v67) = v316;
          v66 = v336 + v316;
          v29 = a1;
          v578 = (char *)v66;
          goto LABEL_981;
        }
        if ( v305 == 5 )
        {
          v307 = v596;
          v317 = *(_QWORD *)(v596 + 48);
          if ( !v317 )
            goto LABEL_560;
          v318 = *(_BYTE *)(v596 + 66);
          switch ( v318 )
          {
            case 4:
              v319 = 4 * (int)v306;
              v320 = *(unsigned __int8 *)(v319 + v317 + 2)
                   + ((*(unsigned __int8 *)(v319 + v317 + 1) + (*(unsigned __int8 *)(v319 + v317) << 8)) << 8);
              v321 = *(unsigned __int8 *)(v319 + v317 + 3);
              goto LABEL_539;
            case 3:
              v322 = 3 * (int)v306;
              v320 = *(unsigned __int8 *)(v322 + v317 + 1) + (*(unsigned __int8 *)(v322 + v317) << 8);
              v321 = *(unsigned __int8 *)(v322 + v317 + 2);
              goto LABEL_539;
            case 2:
              v323 = 2 * (int)v306;
              v320 = *(unsigned __int8 *)(v323 + v317);
              v321 = *(unsigned __int8 *)(v323 + v317 + 1);
LABEL_539:
              v324 = v321 + (v320 << 8);
              break;
            case 1:
              v324 = *(unsigned __int8 *)(v306 + v317);
              break;
            default:
              goto LABEL_560;
          }
          if ( !v324 )
            goto LABEL_560;
          v316 = *(_QWORD *)(v596 + 40) + v324;
LABEL_558:
          v67 = a8;
LABEL_559:
          if ( !v316 )
            goto LABEL_560;
          goto LABEL_565;
        }
        v307 = v596;
        if ( v305 == 1 )
        {
          v316 = *(_QWORD *)v596;
          goto LABEL_559;
        }
        v325 = *(_QWORD *)(v596 + 32);
        if ( !v325 )
          goto LABEL_560;
        v326 = *(_BYTE *)(v596 + 65);
        switch ( v326 )
        {
          case 4:
            v327 = 4 * (int)v306;
            v328 = *(unsigned __int8 *)(v325 + v327 + 2)
                 + ((*(unsigned __int8 *)(v325 + v327 + 1) + (*(unsigned __int8 *)(v325 + v327) << 8)) << 8);
            v329 = *(unsigned __int8 *)(v325 + v327 + 3);
            goto LABEL_553;
          case 3:
            v330 = 3 * (int)v306;
            v328 = *(unsigned __int8 *)(v330 + v325 + 1) + (*(unsigned __int8 *)(v330 + v325) << 8);
            v329 = *(unsigned __int8 *)(v330 + v325 + 2);
            goto LABEL_553;
          case 2:
            v331 = 2 * (int)v306;
            v328 = *(unsigned __int8 *)(v331 + v325);
            v329 = *(unsigned __int8 *)(v331 + v325 + 1);
LABEL_553:
            v332 = v329 + (v328 << 8);
            break;
          case 1:
            v332 = *(unsigned __int8 *)(v306 + v325);
            break;
          default:
            goto LABEL_560;
        }
        if ( !v332 )
          goto LABEL_560;
        v316 = *(_QWORD *)(v596 + 24) + v332;
        goto LABEL_558;
    }
    if ( v584 != 12 )
    {
      if ( v584 != 13 )
      {
        if ( v584 != 14 )
        {
          v29 = a1;
          if ( *(_DWORD *)(a1 + 964) )
          {
            if ( (__int64)((v65 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFFCuLL) >= 4 )
            {
              v295 = *(_QWORD *)(a1 + 976);
              if ( !v295 || !*(_DWORD *)(v295 + 4) )
              {
                v629 = *(__int16 *)(v65 - 2);
                goto LABEL_575;
              }
            }
            goto LABEL_148;
          }
          v296 = *v13 + v587;
LABEL_499:
          v297 = v13[1];
          *v13 = -1;
          goto LABEL_649;
        }
        v71 = v585;
        if ( (*(_DWORD *)v585 & 0x400) != 0 )
        {
          if ( v65 < (unsigned __int64)v13 || v65 > v70 )
            goto LABEL_148;
          v551 = a1;
          v552 = (__int64)(v65 - (_QWORD)v13) >> 2;
          v553 = 0;
          for ( *(_DWORD *)(a1 + 912) = v552; v553 < v552; v551 = a1 )
          {
            v554 = v553++;
            *(_DWORD *)(*(_QWORD *)(v551 + 920) + 4 * v554) = v13[v554];
          }
          return 0;
        }
        v29 = a1;
        if ( *(_WORD *)(a1 + 960) != 2 || (__int64)((v65 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFFCuLL) <= 4 )
        {
          if ( !*(_DWORD *)(a1 + 948) )
          {
            if ( (unsigned int *)v65 == v13 )
              *v13 = -1;
            v65 = (unsigned __int64)(v13 + 5);
LABEL_653:
            if ( *(_DWORD *)(v29 + 956) && !T1globalColoring )
            {
              if ( !(unsigned int)GlobalColoringGC(
                                    gcList,
                                    (*v613)[2],
                                    (unsigned int)nGlbCounters,
                                    (unsigned int)nGlbColors,
                                    *(_QWORD *)(v71 + 16)) )
                goto LABEL_1074;
              T1globalColoring = 3;
              glbCounterList = 0;
              pPathData = 0;
              if ( dword_1400B6088 )
                T1globalColoring = 2;
              if ( !v600 && *v597 )
                ((void (__fastcall *)(__int64 *))*v597)(v593);
              v29 = a1;
            }
            if ( *(_DWORD *)(v29 + 948) )
              goto LABEL_721;
            if ( *v13 == -1 )
            {
              if ( ((_BYTE)v613[4] & 1) != 0 )
              {
                *v13 = 0;
                v13[2] = 0;
                v13[3] = *(_DWORD *)(v29 + 784);
                v13[1] = *(_DWORD *)(v29 + 776);
              }
              else
              {
                v13[1] = 0;
                v13[3] = 0;
                v13[2] = *(_DWORD *)(v29 + 780);
                *v13 = *(_DWORD *)(v29 + 772);
              }
              goto LABEL_701;
            }
            v13[2] = *(_DWORD *)(v29 + 944) + *v13;
            *(_QWORD *)v13 = 0;
LABEL_700:
            v13[3] = 0;
            goto LABEL_701;
          }
          v382 = v586;
LABEL_1076:
          if ( T1globalColoring )
          {
            v71 = (__int64)v597;
            if ( !v382 )
            {
              v543 = (void (__fastcall *)(__int64 *))v597[4];
              if ( v543 )
              {
                v543(v593);
                v71 = (__int64)v597;
              }
            }
            v10 = v585;
            if ( (*(_BYTE *)v585 & 0x20) != 0 )
            {
              result = CScanFill(a1, v650, (_DWORD)v613, v618, v620, *v593, *(_QWORD *)(v585 + 16));
              if ( (_DWORD)result )
                return result;
              v544 = (void (__fastcall *)(__int64 *))*v597;
LABEL_1085:
              if ( v544 )
                v544(v593);
            }
            else if ( !v600 )
            {
              v544 = *(void (__fastcall **)(__int64 *))(v71 + 40);
              goto LABEL_1085;
            }
            v545 = (unsigned int)T1globalColoring;
            if ( T1globalColoring )
            {
              if ( (*(_BYTE *)v10 & 0x30) != 0x30 )
                return 0;
              v546 = *(_DWORD *)v10 & 0xFFFFFFE7 | 8;
              *(_DWORD *)v10 = v546;
              v547 = (_DWORD)v545 == 0;
              goto LABEL_1090;
            }
          }
          else
          {
            v10 = v585;
          }
          T1globalColoring = 3;
          AdjustToStdWidths(v71);
          GCProcess(a1, (*v613)[2], *(unsigned int *)(a1 + 640), *(_QWORD *)(v10 + 16));
          v29 = a1;
          if ( dword_1400B6088 )
            T1globalColoring = 2;
          goto LABEL_32;
        }
LABEL_508:
        *(_DWORD *)v71 |= 0x80u;
        if ( (*(_BYTE *)v71 & 0x18) != 0 )
          return 0xFFFFFFFFLL;
        if ( *(_WORD *)(v29 + 960) == 2 )
        {
          v298 = v13 + 3;
          v299 = v13 + 2;
          v300 = v13 + 1;
          if ( v65 - (_QWORD)v13 == 20 )
          {
            v70 = *v300;
            v300 = v13 + 2;
            v299 = v13 + 3;
            v298 = v13 + 4;
          }
          else
          {
            v70 = *v13;
            *v13 = -1;
          }
          v301 = *v299;
          v302 = *v300;
          v13[7] = *v298;
          v13[6] = v301;
          v13[5] = v302;
          v13[4] = v70;
          if ( *(_DWORD *)(v29 + 948) )
            goto LABEL_1099;
          v65 = (unsigned __int64)(v13 + 8);
          goto LABEL_652;
        }
        v10 = v585;
        v542 = (int)v13;
LABEL_1101:
        CCBuild(v542, *(_QWORD *)(v10 + 8), v587, v588, v29);
        if ( (*(_DWORD *)v10 & 2) != 0 )
          return 1;
        v547 = T1globalColoring == 0;
        *(_DWORD *)v10 |= 0x10u;
LABEL_1090:
        if ( v547 )
          GCStartLock(v546, v545, v70, v66);
        v548 = qword_1400B6080;
        v549 = (_DWORD *)qword_1400B6090;
        lockSlopesInited = 0;
        lockFixMapOk = 1;
        *(_DWORD *)qword_1400B6080 = 1;
        *v549 = 1;
        *(_DWORD *)(v548 + 64) = -399507455;
        v549[16] = -399507455;
        goto LABEL_1069;
      }
      v303 = v13[1];
      v29 = a1;
      v13[1] = 0;
LABEL_699:
      v13[2] = v303;
      goto LABEL_700;
    }
    if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
      goto LABEL_1112;
    v72 = (unsigned __int8)*v578;
    v66 = (unsigned __int64)++v578;
    v73 = v72 == 17;
    v74 = v72 <= 0x11;
LABEL_124:
    if ( !v74 )
    {
      if ( v72 <= 0x1C )
      {
        if ( v72 == 28 )
        {
LABEL_415:
          v218 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v218 >= 0 && (unsigned int)v218 >= 2 )
          {
            v219 = *(_DWORD *)(v65 - 4);
            *(_DWORD *)(v65 - 4) = *(_DWORD *)(v65 - 8);
            *(_DWORD *)(v65 - 8) = v219;
            goto LABEL_220;
          }
          goto LABEL_1112;
        }
        v207 = v72 - 18;
        if ( !v207 )
        {
          v217 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v217 >= 0 && (_DWORD)v217 )
          {
            v65 -= 4LL;
            goto LABEL_220;
          }
          goto LABEL_1112;
        }
        v208 = v207 - 2;
        if ( !v208 )
          goto LABEL_165;
        v209 = v208 - 1;
        if ( v209 )
        {
          v210 = v209 - 1;
          if ( !v210 )
            goto LABEL_288;
          v211 = v210 - 2;
          if ( !v211 )
            goto LABEL_253;
          v212 = v211 - 1;
          if ( !v212 )
            goto LABEL_248;
          v213 = v212 - 1;
          if ( !v213 )
          {
            v215 = (__int64)(v65 - (_QWORD)v13) >> 2;
            if ( v215 < 0 || !(_DWORD)v215 )
              goto LABEL_1112;
            *(_DWORD *)(v65 - 4) = (((int)(sqrt((double)*(int *)(v65 - 4) * 9.313225746154785e-10) * 1073741824.0 + 0.5)
                                   + 64) >> 7)
                                 & 0x1FFFFFF;
            goto LABEL_227;
          }
          if ( v213 != 1 )
            goto LABEL_148;
LABEL_403:
          v214 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v214 >= 0 && (_DWORD)v214 )
          {
            if ( v65 >= (unsigned __int64)(v13 + 513) )
              goto LABEL_148;
            *(_DWORD *)v65 = *(_DWORD *)(v65 - 4);
            goto LABEL_392;
          }
          goto LABEL_1112;
        }
        goto LABEL_274;
      }
      v220 = v72 - 29;
      if ( !v220 )
      {
        v293 = (__int64)(v65 - (_QWORD)v13) >> 2;
        if ( v293 >= 0 && (unsigned int)v293 >= 2 )
        {
          v294 = 0;
          if ( *(__int16 *)(v65 - 2) >= 0 )
            v294 = *(__int16 *)(v65 - 2);
          if ( v294 + 2 >= 0 && (unsigned int)v293 >= v294 + 2 )
          {
            v158 = *(_DWORD *)(v65 - (4LL * v294 + 8));
            goto LABEL_301;
          }
        }
        goto LABEL_1112;
      }
      v221 = v220 - 1;
      if ( !v221 )
      {
        v277 = (__int64)(v65 - (_QWORD)v13) >> 2;
        if ( v277 < 0 || (unsigned int)v277 < 2 )
          goto LABEL_1112;
        v278 = *(_DWORD *)(v65 - 4);
        v65 -= 8LL;
        v279 = *(__int16 *)(v65 + 2);
        if ( (int)v279 < 0 || v65 - 4 * v279 < (unsigned __int64)v13 )
          goto LABEL_148;
        v29 = a1;
        v67 = a8;
        v63 = v556;
        if ( !*(_WORD *)(v65 + 2) )
        {
          v66 = (unsigned __int64)v578;
          goto LABEL_99;
        }
        v280 = 0;
        v281 = (v278 >> 16) % (int)v279;
        if ( v281 >= 0 )
        {
          v67 = a8;
          v63 = v556;
          if ( v281 <= 0 )
          {
            v29 = a1;
            v66 = (unsigned __int64)v578;
            goto LABEL_99;
          }
          v287 = (_DWORD *)(v65 - 4 * v279);
          v288 = v279 - 1;
          do
          {
            v289 = *(_DWORD *)(v65 - 4);
            v290 = 0;
            LODWORD(v598) = v289;
            if ( v288 > 0 )
            {
              do
              {
                v291 = -2 - v290;
                v292 = ~v290++;
                *(_DWORD *)(v65 + 4LL * v292) = *(_DWORD *)(v65 + 4 * v291);
              }
              while ( v290 < v288 );
              v289 = (int)v598;
            }
            ++v280;
            *v287 = v289;
          }
          while ( v280 < v281 );
        }
        else
        {
          v282 = (int *)(v65 - 4 * v279);
          v283 = v279 - 1;
          do
          {
            v284 = *v282;
            v285 = 0;
            LODWORD(v598) = *v282;
            if ( v283 > 0 )
            {
              do
              {
                v286 = v285++;
                *(_DWORD *)(v65 + 4LL * (v286 - (int)v279)) = *(_DWORD *)(v65 + 4LL * (v286 - (int)v279) + 4);
              }
              while ( v285 < v283 );
              v284 = (int)v598;
            }
            --v280;
            *(_DWORD *)(v65 - 4) = v284;
          }
          while ( v280 > v281 );
        }
        goto LABEL_227;
      }
      v222 = v221 - 3;
      if ( !v222 )
      {
        v276 = (__int64)(v65 - (_QWORD)v13) >> 2;
        if ( v276 >= 0 && (unsigned int)v276 >= 2 )
        {
          v583 = *(_QWORD *)(v65 - 8);
LABEL_464:
          v29 = a1;
          goto LABEL_576;
        }
        goto LABEL_1112;
      }
      v223 = v222 - 1;
      if ( v223 )
      {
        v224 = v223 - 1;
        if ( !v224 )
        {
          v256 = *v13 + v583 + v13[2];
          v257 = v13[10];
          v236 = v256 + v13[4];
          v233 = HIDWORD(v583);
          v258 = v13[5];
          v259 = v13[11];
          v260 = v13[12];
          LODWORD(v653) = *v13 + v583;
          v261 = v236 + v13[6];
          LODWORD(v654) = v256;
          v262 = v261 + v13[8];
          LODWORD(v657) = v261;
          v232 = v262 + v257;
          v263 = HIDWORD(v583) + v13[1];
          LODWORD(v658) = v262;
          v264 = v263 + v13[3];
          HIDWORD(v653) = v263;
          v244 = v264 + v258;
          v265 = v244 + v13[7];
          HIDWORD(v654) = v264;
          v266 = v265 + v13[9];
          v609 = v260;
          v249 = v266 + v259;
          v655 = __PAIR64__(v244, v236);
          HIDWORD(v659) = v249;
          HIDWORD(v657) = v265;
          HIDWORD(v658) = v266;
          goto LABEL_445;
        }
        v225 = v224 - 1;
        if ( v225 )
        {
          v226 = v225 - 1;
          if ( v226 )
          {
            if ( v226 != 1 )
              goto LABEL_148;
            v29 = a1;
            goto LABEL_427;
          }
          v232 = v583;
          v233 = HIDWORD(v583);
          v234 = v583 + *v13 + v13[2];
          v235 = v13[8];
          v236 = v234 + v13[4];
          v237 = v13[5];
          v238 = v13[9];
          LODWORD(v653) = v583 + *v13;
          v239 = v236 + v13[6];
          LODWORD(v654) = v234;
          v240 = v13[3];
          v241 = v239 + v235;
          LODWORD(v657) = v239;
          v242 = HIDWORD(v583) + v13[1];
          LODWORD(v655) = v236;
          v243 = v242 + v240;
          HIDWORD(v653) = v242;
          v244 = v243 + v237;
          v245 = v244 + v13[7];
          HIDWORD(v654) = v243;
          HIDWORD(v657) = v245;
          HIDWORD(v658) = v245 + v238;
          v246 = v245 + v238 - HIDWORD(v583);
          LODWORD(v658) = v241;
          HIDWORD(v655) = v244;
          v247 = HIDWORD(v583) - HIDWORD(v658);
          if ( HIDWORD(v583) - HIDWORD(v658) < 0 )
            v247 = v246;
          v248 = v583 - v241;
          if ( (int)(v241 - v583) > 0 )
            v248 = v241 - v583;
          if ( v248 > v247 )
          {
            v232 = v241 + v13[10];
            goto LABEL_443;
          }
          v249 = v13[10] + HIDWORD(v658);
          HIDWORD(v659) = v249;
LABEL_444:
          v609 = 3276800;
LABEL_445:
          LODWORD(v659) = v232;
          v270 = v232 - v583;
          v271 = -v270;
          if ( v270 > 0 )
            v271 = v270;
          v272 = v249 - v233;
          v273 = -v272;
          if ( v272 > 0 )
            v273 = v272;
          if ( v271 >= v273 )
            v651 = __PAIR64__(v233, v236);
          else
            v651 = __PAIR64__(v244, v583);
          v274 = v599;
          v652 = v651;
          v656 = v655;
          v660 = v659;
          v583 = v659;
          ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v599)(&v652, &v652);
          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v652, &v652);
          ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v274)(&v653, &v653);
          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v653, &v653);
          ((void (__fastcall *)(__int64 *, __int64 *))v274)(&v654, &v654);
          ((void (__fastcall *)(__int64, __int64 *))ITransform)(v654, &v654);
          ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v274)(&v656, &v656);
          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v656, &v656);
          ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v274)(&v657, &v657);
          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v657, &v657);
          ((void (__fastcall *)(__int64 *, __int64 *))v274)(&v658, &v658);
          ((void (__fastcall *)(__int64, __int64 *))ITransform)(v658, &v658);
          ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *))v274)(&v659, &v659);
          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v659, &v659);
          v115 = HIDWORD(v625);
          v65 = (unsigned __int64)v13;
          v116 = v609;
LABEL_453:
          v29 = a1;
          if ( !*(_DWORD *)(a1 + 948) )
            goto LABEL_148;
          v594 = 0;
          if ( T1globalColoring )
          {
            if ( v628 )
              FlexProc2(&v651, &v592, v597[3], v593);
            else
              FlexProc(
                (unsigned int)&v651,
                v116,
                (unsigned int)&v592,
                v597[2],
                v597[3],
                (__int64)v593,
                *(_DWORD *)(a1 + 632),
                erosion,
                dword_1400B606C);
            v115 = HIDWORD(v652);
            v29 = a1;
            v625 = v652;
          }
          v275 = v636;
          v602 = 2;
          v609 = 0;
          *v636 = v115;
          v275[1] = v625;
          v586 = 0;
          goto LABEL_460;
        }
        v233 = HIDWORD(v583);
        v250 = v13[2];
        v244 = HIDWORD(v583) + v13[1] + v13[3];
        v251 = v13[4];
        v252 = v13[8];
        HIDWORD(v653) = HIDWORD(v583) + v13[1];
        HIDWORD(v658) = v244 + v13[7];
        v253 = *v13 + v583 + v250;
        LODWORD(v653) = *v13 + v583;
        v254 = v13[5];
        v236 = v253 + v251;
        LODWORD(v654) = v253;
        v255 = v13[6];
      }
      else
      {
        v233 = HIDWORD(v583);
        v267 = *v13 + v583;
        v244 = HIDWORD(v583) + v13[2];
        v252 = v13[6];
        v236 = v267 + v13[1] + v13[3];
        LODWORD(v654) = v267 + v13[1];
        v255 = v13[5];
        v653 = __PAIR64__(HIDWORD(v583), v267);
        v254 = v13[4];
        HIDWORD(v658) = HIDWORD(v583);
      }
      v268 = v236 + v254;
      v655 = __PAIR64__(v244, v236);
      v269 = v268 + v255;
      v657 = __PAIR64__(v244, v268);
      v232 = v269 + v252;
      LODWORD(v658) = v269;
      HIDWORD(v654) = v244;
LABEL_443:
      v249 = v233;
      HIDWORD(v659) = v233;
      goto LABEL_444;
    }
    if ( v73 )
    {
      if ( v594 <= 0 )
      {
        if ( v602 <= 0 || v65 >= (unsigned __int64)(v13 + 513) )
          goto LABEL_148;
        v206 = v602--;
        *(_DWORD *)v65 = v636[v206 - 1];
LABEL_392:
        v65 += 4LL;
        goto LABEL_220;
      }
      --v594;
      goto LABEL_979;
    }
    if ( v72 <= 8 )
    {
      if ( v72 != 8 )
      {
        if ( !v72 )
          goto LABEL_464;
        v181 = v72 - 1;
        if ( v181 )
        {
          v182 = v181 - 1;
          if ( v182 )
          {
            v183 = v182 - 1;
            if ( v183 )
            {
              v184 = v183 - 1;
              if ( v184 )
              {
                v185 = v184 - 1;
                if ( v185 )
                {
                  v186 = v185 - 1;
                  if ( !v186 )
                  {
                    v29 = a1;
                    v71 = v585;
                    goto LABEL_508;
                  }
                  if ( v186 != 1 )
                    goto LABEL_148;
                  v29 = a1;
LABEL_701:
                  if ( *(_DWORD *)(v29 + 948) || !v586 )
                    goto LABEL_148;
                  *(_DWORD *)(v29 + 948) = 1;
                  v373 = *v13;
                  v374 = v13[1];
                  LODWORD(v631) = v13[2];
                  v375 = v13[3];
                  v376 = v613;
                  v583 = __PAIR64__(v374, v373);
                  v630 = __PAIR64__(v374, v373);
                  v377 = v613[1];
                  HIDWORD(v631) = v375;
                  switch ( *((_DWORD *)v377 + 4) )
                  {
                    case 1:
                      goto LABEL_712;
                    case 2:
                      goto LABEL_710;
                    case 4:
                      HIDWORD(v631) = *((_DWORD *)v377 + 3);
                      if ( (unsigned int)(HIDWORD(v631) + 399507455) > 0x2F9FFFFE )
                        os_raise(4294967286LL, "sidebearing or width override out of bounds");
                      v374 = *((_DWORD *)v376[1] + 1);
                      HIDWORD(v583) = v374;
                      if ( v374 + 131072000 > 0xFA00000 )
                      {
                        os_raise(4294967286LL, "sidebearing or width override out of bounds");
                        v374 = HIDWORD(v583);
                      }
LABEL_710:
                      v373 = *(_DWORD *)v376[1];
                      LODWORD(v583) = v373;
                      if ( v373 + 131072000 > 0xFA00000 )
                      {
                        os_raise(4294967286LL, "sidebearing or width override out of bounds");
                        v374 = HIDWORD(v583);
                        v373 = v583;
                      }
LABEL_712:
                      v377 = v376[1];
                      LODWORD(v631) = *((_DWORD *)v377 + 2);
                      if ( (unsigned int)(v631 + 399507455) > 0x2F9FFFFE )
                      {
                        os_raise(4294967286LL, "sidebearing or width override out of bounds");
                        v377 = v376[1];
                        v374 = HIDWORD(v583);
                        v373 = v583;
                      }
                      break;
                  }
                  v378 = v631;
                  v587 = (_DWORD)v18 + v373;
                  LODWORD(v583) = (_DWORD)v18 + v373;
                  v379 = *(_DWORD *)v585 | 0xFFFFFFEF;
                  v588 = HIDWORD(v649) + v374;
                  HIDWORD(v583) = HIDWORD(v649) + v374;
                  if ( v379 != -1 )
                  {
                    *v377 = v583;
                    v613[1][1] = v378;
                  }
                  BCTfmP(a1, v583, (char *)v613[1] + 20);
                  BCTfmP(a1, v378, (char *)v613[1] + 28);
                  if ( v600 )
                    return 0;
                  ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))Transform)(v583, &v592);
                  v71 = (__int64)v597;
                  v380 = (void (__fastcall *)(unsigned __int64 *, __int64 *))v597[1];
                  if ( v380 )
                    v380(&v592, v593);
                  v13 = v627;
                  v381 = v65 - (_QWORD)v627;
                  v382 = 1;
                  v586 = 1;
                  switch ( v381 )
                  {
                    case 0x24uLL:
                      v29 = a1;
                      *v627 = v627[6];
                      v13[1] = v13[7];
LABEL_721:
                      if ( !*(_DWORD *)(v29 + 952) )
                      {
                        v73 = v595 == 0;
                        *(_DWORD *)(v29 + 952) = 1;
                        if ( !v73 )
                        {
                          v66 = (unsigned int)v589;
                          if ( v608 >= 0 || (v383 = 0, v384 = 0, v584 = 0, v589 <= 0) )
                          {
LABEL_739:
                            v391 = 0;
                            v392 = v66;
                            v568 = v66;
                            if ( (int)v66 >= (int)v66 + v605 )
                              goto LABEL_754;
                            LODWORD(v598) = v66 + v605 - 1;
                            while ( 1 )
                            {
                              v393 = v13 + 4;
                              Size = (size_t)(v13 + 4);
                              v394 = v661[2 * v392];
                              v70 = (unsigned int)v661[2 * v392 + 1];
                              if ( *((_BYTE *)&v661[192] + v392) )
                              {
                                v397 = v391;
                                v391 += 2;
                                Size = (size_t)(v13 + 4);
                                v13[v397] = v394;
                                v13[v397 + 1] = v70;
                              }
                              else
                              {
                                v395 = v585;
                                *v393 = v394;
                                v396 = v587;
                                v13[5] = v70;
                                RXLock(v393, v396, *(_QWORD *)(v395 + 16));
                              }
                              if ( v391 == 6 )
                              {
                                RMLock(v13, v587, *(_QWORD *)(v585 + 16));
                                v391 = 0;
                              }
                              v398 = v568;
                              if ( v568 == (_DWORD)v598 && v391 )
                              {
                                RXLock(v13, v587, *(_QWORD *)(v585 + 16));
                                if ( v391 == 4 )
                                  RXLock(Size, v587, *(_QWORD *)(v585 + 16));
                                v398 = v568;
                              }
                              if ( dword_1400B6088 )
                              {
                                v70 = 2;
                                if ( T1globalColoring != 2 )
                                  break;
                              }
                              v392 = v398 + 1;
                              v568 = v392;
                              if ( v392 >= v589 + v605 )
                                goto LABEL_754;
                            }
                          }
                          else
                          {
                            v385 = v589 - 1;
                            v567 = v589 - 1;
                            while ( 1 )
                            {
                              v386 = v661[2 * v383];
                              v70 = (unsigned int)v661[2 * v383 + 1];
                              if ( *((_BYTE *)&v661[192] + v383) )
                              {
                                v389 = v384;
                                v384 += 2;
                                v13[v389] = v386;
                                v13[v389 + 1] = v70;
                              }
                              else
                              {
                                v387 = v585;
                                v13[4] = v386;
                                v388 = v588;
                                v13[5] = v70;
                                RBLock(v13 + 4, v388, v29, *(_QWORD *)(v387 + 16));
                                v385 = v567;
                              }
                              if ( v384 == 6 )
                              {
                                RVLock(v13, v588, *(_QWORD *)(v585 + 16));
                                v385 = v567;
                                v384 = 0;
                              }
                              v390 = v584;
                              if ( v584 == v385 && v384 )
                              {
                                RBLock(v13, v588, a1, *(_QWORD *)(v585 + 16));
                                if ( v384 == 4 )
                                  RBLock(v13 + 2, v588, a1, *(_QWORD *)(v585 + 16));
                                v385 = v567;
                                v390 = v584;
                              }
                              if ( dword_1400B6088 )
                              {
                                v70 = 2;
                                if ( T1globalColoring != 2 )
                                  break;
                              }
                              v66 = (unsigned int)v589;
                              v383 = v390 + 1;
                              v29 = a1;
                              v584 = v383;
                              if ( (int)v383 >= v589 )
                                goto LABEL_739;
                            }
                          }
LABEL_1071:
                          T1globalColoring = 2;
                          goto LABEL_1072;
                        }
                      }
LABEL_754:
                      LODWORD(v583) = v13[6] + v583;
                      HIDWORD(v583) += v13[7];
                      ((void (__fastcall *)(unsigned __int64 *, unsigned __int64 *, size_t, unsigned __int64))v599)(
                        &v583,
                        &v625,
                        v70,
                        v66);
                      if ( v609 )
                      {
                        v399 = v623;
                        if ( v623 < 10 )
                        {
                          if ( (v623 & 0xFFFFFFFB) == 0 )
                          {
                            *(&v651 + v623) = v583;
                            ++v399;
                          }
                          ((void (__fastcall *)(unsigned __int64, unsigned __int64 *))ITransform)(v625, &v651 + v399);
                          v623 = v399 + 1;
                          goto LABEL_582;
                        }
                      }
                      v26 = v583;
                      v27 = v583;
                      v592 = v625;
                      v643 = v583;
                      if ( T1globalColoring )
                      {
                        v400 = v593;
                        if ( !v586 )
                        {
                          v401 = (void (__fastcall *)(__int64 *))v597[4];
                          if ( v401 )
                            v401(v593);
                        }
                        v402 = (void (__fastcall *)(unsigned __int64 *, __int64 *))v597[1];
                        if ( v402 )
                          v402(&v592, v400);
LABEL_581:
                        v586 = 1;
LABEL_582:
                        v29 = a1;
                        goto LABEL_575;
                      }
                      goto LABEL_574;
                    case 0x20uLL:
                      for ( i = 0; i != 4; ++i )
                        v13[i] = v13[i + 4];
                      v29 = a1;
LABEL_1099:
                      v10 = v585;
                      if ( (*(_BYTE *)v585 & 0x18) != 0 )
                        return 0xFFFFFFFFLL;
                      v542 = (_DWORD)v13 + 12;
                      v13[3] = 0;
                      goto LABEL_1101;
                    case 0x14uLL:
                      goto LABEL_1076;
                  }
                  if ( v603 )
                  {
LABEL_768:
                    v29 = a1;
LABEL_769:
                    v10 = v585;
                    if ( *(_DWORD *)(v29 + 956) && !T1globalColoring )
                    {
                      if ( !(unsigned int)GlobalColoringGC(
                                            gcList,
                                            (*v613)[2],
                                            (unsigned int)nGlbCounters,
                                            (unsigned int)nGlbColors,
                                            *(_QWORD *)(v585 + 16)) )
                      {
                        dword_1400B6088 = 1;
                        goto LABEL_1069;
                      }
                      T1globalColoring = 3;
                      glbCounterList = 0;
                      pPathData = 0;
                      if ( dword_1400B6088 )
                        T1globalColoring = 2;
                      if ( !v600 && *v597 )
                        ((void (__fastcall *)(__int64 *))*v597)(v593);
                      v29 = a1;
                    }
                    if ( !*(_DWORD *)(v29 + 952) )
                      goto LABEL_782;
                    if ( !T1globalColoring )
                    {
                      GCStartLock(v71, v360, v70, v66);
                      v29 = a1;
                    }
                    v73 = lockFixedMap == 0;
                    v403 = qword_1400B6080;
                    v404 = (_DWORD *)qword_1400B6090;
                    lockSlopesInited = 0;
                    lockFixMapOk = 0;
                    *(_DWORD *)qword_1400B6080 = 1;
                    *v404 = 1;
                    *(_DWORD *)(v403 + 64) = -399507455;
                    v404[16] = -399507455;
                    if ( v73 )
                    {
LABEL_782:
                      v405 = v589;
                      v406 = 0;
                      v407 = 0;
                      v575 = 0;
                      v408 = 0;
                      v569 = 0;
                      if ( v589 <= 0 )
                      {
LABEL_802:
                        v415 = 0;
                        v416 = v405;
                        v603 = v405 + v605;
                        for ( j = v405 < v405 + v605; ; j = v416 < v423 )
                        {
                          v570 = v416;
                          if ( !j )
                            break;
                          if ( (v416 & 7) == 0 )
                          {
                            if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
                              goto LABEL_1112;
                            v406 = *v578++;
                            v416 = v570;
                            v575 = v406;
                          }
                          if ( v595 && v406 < 0 )
                          {
                            v418 = v661[2 * v416];
                            v419 = v661[2 * v416 + 1];
                            if ( *((_BYTE *)&v661[192] + v416) )
                            {
                              v422 = v415;
                              v415 += 2;
                              v13[v422] = v418;
                              v13[v422 + 1] = v419;
                            }
                            else
                            {
                              v420 = v585;
                              v13[4] = v418;
                              v421 = v587;
                              v13[5] = v419;
                              RXLock(v13 + 4, v421, *(_QWORD *)(v420 + 16));
                            }
                          }
                          if ( v415 == 6 )
                          {
                            RMLock(v13, v587, *(_QWORD *)(v585 + 16));
                            v415 = 0;
                          }
                          v423 = v603;
                          v424 = v570;
                          if ( v570 == v603 - 1 && v415 )
                          {
                            RXLock(v13, v587, *(_QWORD *)(v585 + 16));
                            if ( v415 == 4 )
                              RXLock(v13 + 4, v587, *(_QWORD *)(v585 + 16));
                            v423 = v603;
                            v424 = v570;
                          }
                          if ( dword_1400B6088 && T1globalColoring != 2 )
                            goto LABEL_1071;
                          v406 = 2 * v575;
                          v416 = v424 + 1;
                          v575 *= 2;
                        }
                        v29 = a1;
                        v603 = 0;
                        *(_DWORD *)(a1 + 952) = 1;
                        goto LABEL_575;
                      }
                      while ( 1 )
                      {
                        if ( (v407 & 7) == 0 )
                        {
                          if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
                            goto LABEL_1112;
                          v406 = *v578++;
                          v407 = v569;
                          v575 = v406;
                        }
                        if ( v595 && v406 < 0 && v608 < 0 )
                        {
                          v409 = v661[2 * v407];
                          v410 = v661[2 * v407 + 1];
                          if ( *((_BYTE *)&v661[192] + (unsigned int)v407) )
                          {
                            v413 = v408;
                            v408 += 2;
                            v13[v413] = v409;
                            v13[v413 + 1] = v410;
                          }
                          else
                          {
                            v411 = v585;
                            v13[4] = v409;
                            v412 = v588;
                            v13[5] = v410;
                            RBLock(v13 + 4, v412, a1, *(_QWORD *)(v411 + 16));
                          }
                        }
                        if ( v408 == 6 )
                        {
                          RVLock(v13, v588, *(_QWORD *)(v585 + 16));
                          v408 = 0;
                        }
                        v405 = v589;
                        v414 = v569;
                        if ( v569 == v589 - 1 && v408 )
                        {
                          RBLock(v13, v588, a1, *(_QWORD *)(v585 + 16));
                          if ( v408 == 4 )
                            RBLock(v13 + 2, v588, a1, *(_QWORD *)(v585 + 16));
                          v405 = v589;
                          v414 = v569;
                        }
                        if ( dword_1400B6088 && T1globalColoring != 2 )
                          break;
                        v406 = 2 * v575;
                        v407 = v414 + 1;
                        v575 *= 2;
                        v569 = v407;
                        if ( v407 >= v405 )
                          goto LABEL_802;
                      }
                      T1globalColoring = 2;
LABEL_1072:
                      v29 = a1;
                      v10 = v585;
                      goto LABEL_32;
                    }
                    goto LABEL_32;
                  }
                  v29 = a1;
                  if ( !v606 )
                    goto LABEL_575;
LABEL_826:
                  v73 = *(_DWORD *)(v29 + 956) == 0;
                  v626 = 0;
                  if ( v73 )
                    v641 = 0;
                  LOBYTE(v360) = 0;
                  v425 = (unsigned int)v589;
                  v426 = 0;
                  v427 = v589 + v605;
                  v576 = 0;
                  v571 = 0;
                  v584 = v589 + v605;
                  if ( v589 + v605 <= 0 )
                    goto LABEL_881;
                  while ( 1 )
                  {
                    if ( (v426 & 7) == 0 )
                    {
                      if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v578) )
                        goto LABEL_1112;
                      v426 = (unsigned int)v571;
                      v425 = (unsigned int)v589;
                      LOBYTE(v360) = *v578++;
                      v576 = v360;
                    }
                    if ( T1globalColoring )
                    {
                      if ( (v360 & 0x80u) == 0LL || T1globalColoring != 2 || dword_1400B6088 )
                      {
                        if ( (unsigned int)v426 >= 0x60uLL )
LABEL_1115:
                          _report_rangecheckfailure(v426, v360, v425, v66);
                        *((_BYTE *)&v661[192] + (unsigned int)v426) = 0;
                      }
                      else
                      {
                        *((_BYTE *)&v661[192] + (unsigned int)v426) = 1;
                      }
                    }
                    else
                    {
                      v428 = (unsigned int)v426;
                      if ( (unsigned int)v426 >= 0x60uLL )
                        goto LABEL_1115;
                      *((_BYTE *)&v661[192] + (unsigned int)v426) = 0;
                      if ( (v360 & 0x80u) != 0LL )
                      {
                        v430 = __OFSUB__((_DWORD)v426, (_DWORD)v425);
                        v429 = (int)v426 - (int)v425 < 0;
                        v431 = (unsigned int)v661[2 * (unsigned int)v426];
                        v606 = v661[2 * v428 + 1];
                        LODWORD(Size) = v429 ^ v430;
                        LODWORD(v598) = v431;
                        v621 = v431 + v606;
                        v432 = GCFind(v431, (unsigned int)(v431 + v606), v429 ^ (unsigned __int8)v430, v66);
                        if ( !v432 )
                        {
                          v433 = GCNew(&v641, &v626, *(_QWORD *)(v585 + 16));
                          v432 = v433;
                          if ( !v433 )
                            goto LABEL_1074;
                          if ( gcList )
                          {
                            if ( !v641 )
                              goto LABEL_148;
                            *v641 = v433;
                          }
                          else
                          {
                            gcList = v433;
                          }
                          v434 = (unsigned int)v598;
                          *(_DWORD *)(v433 + 16) = v621;
                          v435 = *(_DWORD *)(v433 + 72) & 0xFFFFFFFE;
                          *(_QWORD *)v432 = 0;
                          v436 = (Size | v435) & 0xFFFFFFF7;
                          *(_DWORD *)(v432 + 28) = 0;
                          *(_DWORD *)(v432 + 32) = 65536000;
                          *(_DWORD *)(v432 + 72) = v436 | 4;
                          v74 = v571 < v589;
                          v437 = (void (__fastcall *)(__int64, __int64 *))DTransform;
                          *(_DWORD *)(v432 + 12) = v434;
                          if ( v74 )
                          {
                            LODWORD(v637) = 0;
                            HIDWORD(v637) = v434;
                            v437(v637, &v637);
                            *(_DWORD *)(v432 + 20) = HIDWORD(v637);
                            HIDWORD(v638) = *(_DWORD *)(v432 + 16);
                            LODWORD(v638) = 0;
                            ((void (__fastcall *)(__int64, __int64 *))DTransform)(v638, &v638);
                            v438 = HIDWORD(v638);
                            v439 = dword_1400B6068;
                            *(_DWORD *)(v432 + 24) = HIDWORD(v638);
                            v440 = v438 - *(_DWORD *)(v432 + 20);
                            *(_DWORD *)(v432 + 44) = v440;
                            *(_DWORD *)(v432 + 8) = v440;
                            if ( v439 )
                              UseStdWidth(v606, v432 + 8, qword_1400B6070, v439, *(_DWORD *)(BCMAIN_inst + 764));
                          }
                          else
                          {
                            v639 = v434;
                            v437(v434, &v639);
                            *(_DWORD *)(v432 + 20) = v639;
                            v640 = *(unsigned int *)(v432 + 16);
                            ((void (__fastcall *)(__int64, __int64 *))DTransform)(v640, &v640);
                            v441 = v640;
                            v442 = dword_1400B607C;
                            *(_DWORD *)(v432 + 24) = v640;
                            v443 = v441 - *(_DWORD *)(v432 + 20);
                            *(_DWORD *)(v432 + 44) = v443;
                            *(_DWORD *)(v432 + 8) = v443;
                            if ( v442 )
                              UseStdWidth(v606, v432 + 8, qword_1400B6060, v442, *(_DWORD *)(BCMAIN_inst + 760));
                          }
                          v444 = *(_DWORD *)(v432 + 72) & 0xFFFF001D;
                          *(_QWORD *)(v432 + 64) = 0;
                          *(_QWORD *)(v432 + 56) = 0;
                          *(_DWORD *)(v432 + 72) = v444 | 0x10;
                          GCCalcLocs(v432);
                          v641 = (_QWORD *)v432;
                        }
                        if ( v626 )
                        {
                          if ( *(_DWORD *)(v432 + 20) < *(_DWORD *)(v626 + 24) )
                            goto LABEL_1073;
                          v445 = NewGlbCounter(*(_QWORD *)(v585 + 16));
                          v360 = v445;
                          if ( !v445 )
                            goto LABEL_1074;
                          *(_DWORD *)(v445 + 8) = *(_DWORD *)(v432 + 20) - *(_DWORD *)(v626 + 24);
                          *(_QWORD *)(v445 + 16) = v432;
                          *(_QWORD *)(v445 + 24) = v626;
                          *(_QWORD *)v445 = glbCounterList;
                          *(_QWORD *)(v432 + 64) = v445;
                          glbCounterList = v445;
                          *(_QWORD *)(v626 + 56) = v445;
                        }
                        LODWORD(v426) = v571;
                        LOBYTE(v360) = v576;
                        v425 = (unsigned int)v589;
                        v626 = v432;
                        v427 = v584;
                      }
                      if ( ((_DWORD)v426 == (_DWORD)v425 - 1 || (_DWORD)v426 == v427 - 1) && v626 )
                      {
                        v446 = (_QWORD *)gcList;
                        if ( gcList )
                        {
                          do
                          {
                            GCFix1Loc(v446, v360, v425, v66);
                            v446 = (_QWORD *)*v446;
                          }
                          while ( v446 );
                          for ( k = gcList; k; k = *(_QWORD *)k )
                            *(_DWORD *)(k + 8) = *(_DWORD *)(k + 40) - *(_DWORD *)(k + 36);
                        }
                        if ( pPathData )
                        {
                          v450 = pPathListBuffer;
                          v451 = a1;
                        }
                        else
                        {
                          if ( *(_DWORD *)(pGCPathBuf + 8) >= 0x1450u )
                          {
                            v448 = *(_QWORD *)pGCPathBuf;
                          }
                          else
                          {
                            if ( *(_QWORD *)pGCPathBuf )
                              (*(void (__fastcall **)(_QWORD, __int64, __int64, unsigned __int64))(**(_QWORD **)(bprocs + 24)
                                                                                                 + 16LL))(
                                *(_QWORD *)(bprocs + 24),
                                pGCPathBuf,
                                v425,
                                v66);
                            v448 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64, unsigned __int64))(bprocs + 24))(
                                     *(_QWORD *)(bprocs + 24),
                                     5200,
                                     v425,
                                     v66);
                            v449 = pGCPathBuf;
                            *(_QWORD *)pGCPathBuf = v448;
                            if ( !v448 )
                            {
                              *(_DWORD *)(v449 + 8) = 0;
                              T1globalColoring = 2;
LABEL_880:
                              v29 = a1;
LABEL_881:
                              v606 = 0;
LABEL_575:
                              v66 = (unsigned __int64)v578;
LABEL_576:
                              v65 = (unsigned __int64)v13;
LABEL_577:
                              v67 = a8;
LABEL_967:
                              v63 = v556;
                              goto LABEL_99;
                            }
                            *(_DWORD *)(v449 + 8) = 5200;
                          }
                          v450 = v448 + 1200;
                          pPathData = v448;
                          v451 = a1;
                          pPathListBuffer = v450;
                          *(_DWORD *)(a1 + 956) = 1;
                        }
                        if ( !(unsigned int)GCFixOnePath(v626, v450, *(unsigned int *)(v451 + 640)) )
                        {
LABEL_1073:
                          T1globalColoring = 2;
LABEL_1074:
                          v29 = a1;
                          dword_1400B6088 = 1;
                          goto LABEL_31;
                        }
                        LODWORD(v426) = v571;
                        LOBYTE(v360) = v576;
                        v427 = v584;
                        v425 = (unsigned int)v589;
                        v626 = 0;
                      }
                    }
                    LOBYTE(v360) = 2 * v360;
                    v426 = (unsigned int)(v426 + 1);
                    v576 = v360;
                    v571 = v426;
                    if ( (int)v426 >= v427 )
                      goto LABEL_880;
                  }
                }
                v187 = (__int64)(v65 - (_QWORD)v13) >> 2;
                if ( v187 >= 0 && (_DWORD)v187 )
                {
                  v156 = *(_DWORD *)(v65 - 4) == 0 ? 0x10000 : 0;
LABEL_297:
                  *(_DWORD *)(v65 - 4) = v156;
                  goto LABEL_220;
                }
LABEL_1112:
                os_raise(0xFFFFFFFFLL, 0);
                return 4294967288LL;
              }
              v188 = (__int64)(v65 - (_QWORD)v13) >> 2;
              if ( v188 < 0 || (unsigned int)v188 < 2 )
                goto LABEL_1112;
              v65 -= 4LL;
              v189 = (int *)(v65 - 4);
              if ( *(_DWORD *)v65 )
              {
LABEL_357:
                v190 = 0x10000;
LABEL_358:
                *v189 = v190;
                goto LABEL_220;
              }
LABEL_363:
              if ( *v189 )
                goto LABEL_357;
            }
            else
            {
              v191 = (__int64)(v65 - (_QWORD)v13) >> 2;
              if ( v191 < 0 || (unsigned int)v191 < 2 )
                goto LABEL_1112;
              v65 -= 4LL;
              v189 = (int *)(v65 - 4);
              if ( *(_DWORD *)v65 )
                goto LABEL_363;
            }
            v190 = 0;
            goto LABEL_358;
          }
          if ( !v595 || v608 >= 0 )
            goto LABEL_464;
          v10 = v585;
          RVLock(v13, v588, *(_QWORD *)(v585 + 16));
        }
        else
        {
          if ( !v595 )
            goto LABEL_464;
          v10 = v585;
          RMLock(v13, v587, *(_QWORD *)(v585 + 16));
        }
LABEL_368:
        v29 = a1;
        if ( !dword_1400B6088 || T1globalColoring == 2 )
          goto LABEL_575;
        T1globalColoring = 2;
        goto LABEL_32;
      }
      v192 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v192 < 0 || (unsigned int)v192 < 4 )
        goto LABEL_1112;
      v193 = *(_DWORD *)(v65 - 4);
      v194 = *(_DWORD *)(v65 - 8);
      v195 = *(_DWORD *)(v65 - 12);
      v65 -= 16LL;
      v196 = a1;
      v621 = v193;
      v564 = v194;
      v197 = *(_DWORD *)v65;
      v73 = *(_QWORD *)(a1 + 800) == 0;
      LODWORD(v598) = *(_DWORD *)v65;
      v584 = v195;
      if ( v73 )
      {
        v198 = *(_DWORD *)(a1 + 812);
        if ( (unsigned int)(v198 - 1) > 0xFFFE )
          goto LABEL_148;
        v199 = *(__int64 (__fastcall ****)(_QWORD, size_t))(v620 + 32);
        v200 = **v199;
        if ( !v200 )
          goto LABEL_1110;
        Size = (unsigned int)(4 * v198);
        v201 = (void *)v200(v199, Size);
        *(_QWORD *)(a1 + 800) = v201;
        if ( !v201 )
          goto LABEL_1110;
        memset_0(v201, 0, Size);
        v193 = v621;
        v194 = v564;
        v195 = v584;
        v197 = (int)v598;
        v196 = a1;
        v66 = (unsigned __int64)v578;
      }
      v63 = v556;
      v202 = v197 >> 16;
      if ( (unsigned int)v202 > 3 )
        goto LABEL_92;
      v203 = v194 >> 16;
      if ( v203 < 0 )
        goto LABEL_92;
      v204 = v193 >> 16;
      v63 = v556;
      if ( v204 + v203 > *(_DWORD *)(v196 + 812) )
        goto LABEL_92;
      v205 = v195 >> 16;
      if ( v205 < 0 || v204 <= 0 )
        goto LABEL_92;
      v63 = v556;
      if ( v205 + v204 > *(_DWORD *)(v196 + 16 * (v202 + 54LL)) )
        goto LABEL_91;
      v170 = (unsigned __int16)(4 * v204);
      v173 = (const void *)(*(_QWORD *)(a1 + 800) + 4LL * v203);
      v171 = *(_QWORD *)(a1 + 16LL * v202 + 872);
      v172 = v205;
LABEL_315:
      memmove_0((void *)(v171 + 4 * v172), v173, v170);
      goto LABEL_227;
    }
    v75 = v72 - 9;
    if ( !v75 )
    {
      v180 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v180 >= 0 && (_DWORD)v180 )
      {
        v158 = -*(_DWORD *)(v65 - 4);
        if ( *(int *)(v65 - 4) > 0 )
          v158 = *(_DWORD *)(v65 - 4);
        goto LABEL_301;
      }
      goto LABEL_1112;
    }
    v76 = v75 - 1;
    if ( !v76 )
      goto LABEL_333;
    v77 = v76 - 1;
    if ( !v77 )
      goto LABEL_330;
    v78 = v77 - 1;
    if ( !v78 )
      break;
    v79 = v78 - 1;
    if ( !v79 )
    {
      v159 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v159 < 0 || (unsigned int)v159 < 3 )
        goto LABEL_1112;
      v160 = *(_DWORD *)(v65 - 4);
      v161 = *(_DWORD *)(v65 - 8);
      v65 -= 12LL;
      v29 = a1;
      v563 = v160;
      v584 = v161;
      v162 = *(_DWORD *)v65;
      v73 = *(_QWORD *)(a1 + 800) == 0;
      v621 = *(_DWORD *)v65;
      if ( v73 )
      {
        v163 = *(_DWORD *)(a1 + 812);
        if ( (unsigned int)(v163 - 1) > 0xFFFE )
          goto LABEL_148;
        v164 = *(__int64 (__fastcall ****)(_QWORD, size_t))(v620 + 32);
        v165 = **v164;
        if ( !v165 )
          goto LABEL_1110;
        Size = (unsigned int)(4 * v163);
        v166 = (void *)v165(v164, Size);
        *(_QWORD *)(a1 + 800) = v166;
        if ( !v166 )
          goto LABEL_1110;
        memset_0(v166, 0, Size);
        v160 = v563;
        v161 = v584;
        v162 = v621;
        v29 = a1;
      }
      v63 = v556;
      v167 = v162 >> 16;
      if ( (unsigned int)v167 <= 3 )
      {
        v168 = v161 >> 16;
        if ( v168 >= 0 )
        {
          v169 = v160 >> 16;
          v63 = v556;
          if ( v169 + v168 <= *(_DWORD *)(v29 + 812) && v169 > 0 )
          {
            v63 = v556;
            if ( v169 <= *(_DWORD *)(v29 + 16 * (v167 + 54LL)) )
            {
              v170 = (unsigned __int16)(4 * v169);
              v171 = *(_QWORD *)(v29 + 800);
              v172 = v168;
              v173 = *(const void **)(v29 + 16LL * v167 + 872);
              goto LABEL_315;
            }
          }
        }
      }
      v66 = (unsigned __int64)v578;
      goto LABEL_98;
    }
    v80 = v79 - 1;
    if ( !v80 )
    {
      v157 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v157 >= 0 && (_DWORD)v157 )
      {
        v158 = -*(_DWORD *)(v65 - 4);
        goto LABEL_301;
      }
      goto LABEL_1112;
    }
    v81 = v80 - 1;
    if ( !v81 )
    {
      v154 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v154 >= 0 && (unsigned int)v154 >= 2 )
      {
        v155 = *(_DWORD *)(v65 - 8);
        v65 -= 4LL;
        v156 = 0;
        if ( *(_DWORD *)v65 == v155 )
          v156 = 0x10000;
        goto LABEL_297;
      }
      goto LABEL_1112;
    }
    if ( v81 != 1 )
      goto LABEL_148;
    v82 = (__int64)(v65 - (_QWORD)v13) >> 2;
    if ( v82 < 0 || (unsigned int)v82 < 2 )
      goto LABEL_1112;
    v83 = *(__int16 *)(v65 - 2);
    v84 = v65 - 4;
    v85 = *(__int16 *)(v65 - 6);
    v65 -= 8LL;
    v557 = v85;
    v584 = v83;
    if ( v83 > 18 )
    {
      if ( v83 > 25 )
      {
        v102 = v83 - 26;
        if ( !v102 )
        {
LABEL_164:
          v594 = 0;
LABEL_165:
          v95 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v95 < 0 || (unsigned int)v95 < 2 )
            goto LABEL_1112;
          v96 = *(_DWORD *)(v65 - 4);
          v65 -= 8LL;
          v29 = a1;
          v558 = v96;
          v73 = *(_QWORD *)(a1 + 800) == 0;
          LODWORD(v598) = *(_DWORD *)v65;
          if ( v73 )
          {
            v97 = *(_DWORD *)(a1 + 812);
            if ( (unsigned int)(v97 - 1) > 0xFFFE )
              goto LABEL_148;
            v98 = *(__int64 (__fastcall ****)(_QWORD, size_t))(v620 + 32);
            v99 = **v98;
            if ( !v99 )
              goto LABEL_1110;
            Size = (unsigned int)(4 * v97);
            v100 = (void *)v99(v98, Size);
            *(_QWORD *)(a1 + 800) = v100;
            if ( !v100 )
              goto LABEL_1110;
            memset_0(v100, 0, Size);
            v96 = v558;
            v29 = a1;
          }
          v101 = v96 >> 16;
          v559 = v101;
          if ( v101 < 0 || v101 >= *(_DWORD *)(v29 + 812) )
          {
            os_raise(0xFFFFFFFFLL, 0);
            v101 = v559;
            v29 = a1;
          }
          *(_DWORD *)(*(_QWORD *)(v29 + 800) + 4LL * v101) = (_DWORD)v598;
          goto LABEL_460;
        }
        v103 = v102 - 1;
        if ( v103 )
        {
          v104 = v103 - 1;
          if ( !v104 )
          {
            if ( v65 < (unsigned __int64)(v13 + 513) )
            {
              v29 = a1;
              v594 = 1;
              v150 = 1103515245 * *(_DWORD *)(a1 + 768) + 12345;
              *(_DWORD *)(a1 + 768) = v150;
              *(_DWORD *)v65 = HIWORD(v150) + 1;
              v65 = v84;
              *((_DWORD *)v613 + 9) |= 1u;
              goto LABEL_577;
            }
            goto LABEL_148;
          }
          v105 = v104 - 1;
          if ( !v105 )
            goto LABEL_403;
          if ( v105 == 1 )
            goto LABEL_415;
          goto LABEL_181;
        }
        v594 = 1;
LABEL_288:
        v151 = (__int64)(v65 - (_QWORD)v13) >> 2;
        if ( v151 >= 0 && (unsigned int)v151 >= 4 )
        {
          v152 = (_DWORD *)v65;
          v153 = (_DWORD *)(v65 - 4);
          if ( *(v153 - 1) <= *v153 )
            v152 = v153;
          *(v153 - 3) = *(v152 - 3);
          v65 = (unsigned __int64)(v153 - 2);
          goto LABEL_220;
        }
        goto LABEL_1112;
      }
      if ( v83 == 25 )
      {
        v594 = 1;
LABEL_274:
        v143 = (__int64)(v65 - (_QWORD)v13) >> 2;
        if ( v143 < 0 || !(_DWORD)v143 )
          goto LABEL_1112;
        v29 = a1;
        v598 = (unsigned __int8 *)(v65 - 4);
        v144 = *(_DWORD *)(v65 - 4);
        v561 = v144;
        if ( !*(_QWORD *)(a1 + 800) )
        {
          v145 = *(_DWORD *)(a1 + 812);
          if ( (unsigned int)(v145 - 1) > 0xFFFE )
            goto LABEL_148;
          v146 = *(__int64 (__fastcall ****)(_QWORD, size_t))(v620 + 32);
          v147 = **v146;
          if ( !v147 )
            goto LABEL_1110;
          Size = (unsigned int)(4 * v145);
          v148 = (void *)v147(v146, Size);
          *(_QWORD *)(a1 + 800) = v148;
          if ( !v148 )
            goto LABEL_1110;
          memset_0(v148, 0, Size);
          v144 = v561;
          v29 = a1;
        }
        v149 = v144 >> 16;
        v562 = v149;
        if ( v149 < 0 || v149 >= *(_DWORD *)(v29 + 812) )
        {
          os_raise(0xFFFFFFFFLL, 0);
          v149 = v562;
          v29 = a1;
        }
        *(_DWORD *)v598 = *(_DWORD *)(*(_QWORD *)(v29 + 800) + 4LL * v149);
        goto LABEL_460;
      }
      v90 = v83 - 19;
      if ( v90 )
      {
        v91 = v90 - 1;
        if ( !v91 )
        {
          v594 = 1;
LABEL_333:
          v179 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v179 >= 0 && (unsigned int)v179 >= 2 )
          {
            v65 -= 4LL;
            *(_DWORD *)(v65 - 4) += *(_DWORD *)v65;
            goto LABEL_220;
          }
          goto LABEL_1112;
        }
        v92 = v91 - 1;
        if ( !v92 )
        {
          v594 = 1;
LABEL_330:
          v178 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v178 >= 0 && (unsigned int)v178 >= 2 )
          {
            v65 -= 4LL;
            *(_DWORD *)(v65 - 4) -= *(_DWORD *)v65;
            goto LABEL_220;
          }
          goto LABEL_1112;
        }
        v93 = v92 - 1;
        if ( v93 )
        {
          v94 = v93 - 1;
          if ( v94 )
          {
            if ( v94 == 1 )
              goto LABEL_164;
            goto LABEL_181;
          }
          v594 = 1;
LABEL_248:
          v124 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v124 >= 0 && (unsigned int)v124 >= 2 )
          {
            v125 = *(_DWORD *)(v65 - 8);
            v65 -= 4LL;
            if ( !*(_DWORD *)v65 )
              goto LABEL_321;
            v126 = _mm_cvtsi32_si128(*(_DWORD *)v65);
            goto LABEL_323;
          }
        }
        else
        {
          v594 = 1;
LABEL_253:
          v127 = (__int64)(v65 - (_QWORD)v13) >> 2;
          if ( v127 >= 0 && (unsigned int)v127 >= 2 )
          {
            v128 = _mm_cvtsi32_si128(*(_DWORD *)(v65 - 8));
            v65 -= 4LL;
            v129 = (double)*(int *)v65 * _mm_cvtepi32_pd(v128).m128d_f64[0] * 0.0000152587890625;
            if ( v129 >= 0.0 )
            {
              v130 = v129 + 0.5;
              if ( v130 >= 2147483647.0 )
                goto LABEL_327;
              goto LABEL_329;
            }
            v216 = v129 - 0.5;
            v158 = (int)v216;
            if ( v216 <= -2147483648.0 )
              v158 = 0x80000000;
            goto LABEL_301;
          }
        }
        goto LABEL_1112;
      }
      v131 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v131 < 0 || !(_DWORD)v131 )
        goto LABEL_1112;
      v29 = a1;
      v65 -= 4LL;
      v132 = *(_DWORD *)v65;
      v560 = *(_DWORD *)v65;
      if ( !*(_QWORD *)(a1 + 800) )
      {
        v133 = *(_DWORD *)(a1 + 812);
        if ( (unsigned int)(v133 - 1) > 0xFFFE )
          goto LABEL_148;
        v134 = *(__int64 (__fastcall ****)(_QWORD, size_t))(v620 + 32);
        v135 = **v134;
        if ( !v135 )
          goto LABEL_1110;
        Size = (unsigned int)(4 * v133);
        v136 = (void *)v135(v134, Size);
        *(_QWORD *)(a1 + 800) = v136;
        if ( !v136 )
          goto LABEL_1110;
        memset_0(v136, 0, Size);
        v132 = v560;
        v29 = a1;
      }
      v137 = *(_DWORD *)(v29 + 644);
      v138 = v132 >> 16;
      if ( v137 + v138 < v138 || v137 + v138 > *(_DWORD *)(v29 + 812) )
        goto LABEL_148;
      v139 = 0;
      if ( v137 )
      {
        v140 = v138;
        do
        {
          v141 = *(_DWORD *)(v29 + 4 * v139 + 648);
          v142 = (unsigned int)v139 + v140;
          v139 = (unsigned int)(v139 + 1);
          *(_DWORD *)(*(_QWORD *)(v29 + 800) + 4 * v142) = v141;
        }
        while ( (unsigned int)v139 < *(_DWORD *)(v29 + 644) );
      }
      v594 = 0;
LABEL_460:
      v66 = (unsigned __int64)v578;
LABEL_980:
      v67 = a8;
LABEL_981:
      v63 = v556;
      goto LABEL_99;
    }
    if ( v83 == 18 )
    {
      v83 = 19;
LABEL_242:
      v122 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v122 < 0 )
        goto LABEL_1112;
      v594 = v83 - 13;
      if ( (unsigned int)v122 < (v83 - 13) * *(_DWORD *)(a1 + 644) )
        goto LABEL_1112;
      v123 = DoBlend((_DWORD)v13, v65, (int)a1 + 648, *(_DWORD *)(a1 + 644), v83 - 13);
      goto LABEL_245;
    }
    if ( v83 > 12 )
    {
      if ( v83 != 13 )
      {
        if ( v83 == 14 || v83 == 15 || (unsigned int)(v83 - 16) < 2 )
          goto LABEL_242;
        goto LABEL_181;
      }
LABEL_215:
      if ( (unsigned int)(v85 - 1) > 0x15 )
        goto LABEL_148;
      v117 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v117 < 0 || (unsigned int)v117 < (unsigned int)v85 )
        goto LABEL_1112;
      if ( T1globalColoring == 2 )
      {
        v65 -= 4 * v85;
        goto LABEL_220;
      }
      v118 = (_DWORD *)pPathData;
      if ( !pPathData )
      {
        if ( *(_DWORD *)(pGCPathBuf + 8) >= 0x1450u )
        {
          v118 = *(_DWORD **)pGCPathBuf;
        }
        else
        {
          if ( *(_QWORD *)pGCPathBuf )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(bprocs + 24) + 16LL))(*(_QWORD *)(bprocs + 24));
          v118 = (_DWORD *)(***(__int64 (__fastcall ****)(_QWORD, __int64))(bprocs + 24))(
                             *(_QWORD *)(bprocs + 24),
                             5200);
          v119 = pGCPathBuf;
          *(_QWORD *)pGCPathBuf = v118;
          if ( !v118 )
          {
            *(_DWORD *)(v119 + 8) = 0;
            T1globalColoring = 2;
            v65 -= 4LL * v557;
            goto LABEL_227;
          }
          v83 = v584;
          LODWORD(v85) = v557;
          *(_DWORD *)(v119 + 8) = 5200;
        }
        pPathData = (__int64)v118;
        pPathListBuffer = (__int64)(v118 + 300);
      }
      v120 = nPathData;
      if ( nPathData + (int)v85 > 300 )
        goto LABEL_148;
      do
      {
        v65 -= 4LL;
        ++v120;
        v121 = *(_DWORD *)v65;
        *v118++ = *(_DWORD *)v65;
        fPathTemp = v121;
        LODWORD(v85) = v85 - 1;
      }
      while ( (_DWORD)v85 );
      pPathData = (__int64)v118;
      nPathData = v120;
      if ( (unsigned int *)v65 != v13 )
        goto LABEL_148;
      if ( v83 == 12 )
      {
        v66 = (unsigned __int64)v578;
        goto LABEL_220;
      }
      BuildGlobalColorsGC(v630, (*v613)[2], *(unsigned int *)(a1 + 640), *(_QWORD *)(v585 + 16));
      glbCounterList = 0;
      pPathData = 0;
      T1globalColoring = 3;
      if ( dword_1400B6088 )
        T1globalColoring = 2;
      if ( !v600 && *v597 )
        ((void (__fastcall *)(__int64 *))*v597)(v593);
LABEL_227:
      v66 = (unsigned __int64)v578;
LABEL_979:
      v29 = a1;
      goto LABEL_980;
    }
    if ( v83 == 12 )
      goto LABEL_215;
    if ( !v83 )
    {
      v114 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v114 < 0 || (unsigned int)v114 < 3 )
        goto LABEL_1112;
      if ( v623 != 9 || (_DWORD)v85 != 3 )
        goto LABEL_148;
      HIDWORD(v625) = v588 + *(_DWORD *)(v65 - 4) - HIDWORD(v630);
      LODWORD(v625) = v587 + *(_DWORD *)(v65 - 8) - v630;
      v65 -= 12LL;
      v115 = HIDWORD(v625);
      v116 = *(_DWORD *)v65;
      v660 = v625;
      goto LABEL_453;
    }
    v29 = a1;
    v86 = v83 - 1;
    if ( !v86 )
    {
      v609 = 1;
      v623 = 0;
      goto LABEL_577;
    }
    v87 = v86 - 1;
    if ( !v87 )
      goto LABEL_97;
    v88 = (unsigned int)(v87 - 1);
    if ( !(_DWORD)v88 )
    {
      if ( (_DWORD)v85 != 1 )
        goto LABEL_148;
      v108 = v602;
      if ( v602 >= 3 )
        goto LABEL_148;
      v110 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v110 < 0 || !(_DWORD)v110 )
        goto LABEL_1112;
      v111 = v636;
      v65 -= 4LL;
      v73 = T1globalColoring == 0;
      v636[v602] = *(_DWORD *)v65;
      if ( v73 )
      {
        GCStartLock(v88, v111, v108, v66);
        v66 = (unsigned __int64)v578;
        LODWORD(v108) = v602;
      }
      v73 = lockFixedMap == 0;
      v112 = qword_1400B6080;
      v113 = (_DWORD *)qword_1400B6090;
      v29 = a1;
      lockSlopesInited = 0;
      *(_DWORD *)qword_1400B6080 = 1;
      *v113 = 1;
      *(_DWORD *)(v112 + 64) = -399507455;
      v113[16] = -399507455;
      lockFixMapOk = 0;
      if ( v73 )
        goto LABEL_200;
LABEL_31:
      v10 = v585;
      goto LABEL_32;
    }
    v89 = v88 - 1;
    if ( !v89 )
    {
      if ( (_DWORD)v85 != 1 )
        goto LABEL_148;
      LODWORD(v108) = v602;
      if ( v602 >= 3 )
        goto LABEL_148;
      v616 = 0;
      v109 = (__int64)(v65 - (_QWORD)v13) >> 2;
      if ( v109 < 0 || !(_DWORD)v109 )
        goto LABEL_1112;
      v65 -= 4LL;
      v636[v602] = 196608;
LABEL_200:
      v602 = v108 + 1;
      goto LABEL_577;
    }
    if ( v89 == 2 )
    {
      if ( (_DWORD)v85 )
        goto LABEL_148;
LABEL_427:
      v67 = a8;
      v63 = v556;
      if ( v595 && T1globalColoring == 2 && !dword_1400B6088 )
      {
        v10 = v585;
LABEL_431:
        T1globalColoring = 0;
        nPathData = 0;
        pPathData = 0;
        v227 = *v613;
        pPathListBuffer = 0;
        v228 = *v227;
        pGblColorBuf = v227[1];
        pGblCounterBuf = v228;
        v229 = *(unsigned int *)(v228 + 8);
        v230 = *(unsigned int *)(pGblColorBuf + 8) / 0x50uLL;
        freeGC = *(_QWORD *)pGblColorBuf;
        v231 = *(_QWORD *)v228;
        endGCList = freeGC + 80 * v230;
        freeGlbCounter = v231;
        endGlbCounterList = v231 + 48 * (v229 / 0x30);
        pGCPathBuf = v227[2];
LABEL_1069:
        v29 = a1;
        goto LABEL_32;
      }
      goto LABEL_99;
    }
LABEL_181:
    v65 -= 4 * v85;
    if ( v65 < (unsigned __int64)v13 || v65 >= (unsigned __int64)(v13 + 513) )
      goto LABEL_148;
    if ( *(_DWORD *)v620 )
    {
      if ( *(_DWORD *)v620 == 1 )
      {
        InvokeDoOtherSubr(
          **(unsigned int **)(*(_QWORD *)(v585 + 16) + 8LL),
          (unsigned int)(v85 + 1),
          v65,
          **(_QWORD **)(v585 + 16));
      }
      else
      {
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0xBu);
      }
      v66 = (unsigned __int64)v578;
      LODWORD(v85) = v557;
    }
    while ( 1 )
    {
      v29 = a1;
      if ( (int)v85 <= 0 )
        goto LABEL_97;
      if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v66) )
        goto LABEL_1112;
      v107 = (unsigned __int8 *)(v578 + 1);
      v584 = (unsigned __int8)*v578;
      v598 = (unsigned __int8 *)++v578;
      if ( v584 != 12 )
        break;
      if ( !(unsigned int)GetDecryptInner(v596, a8, v556, v107) )
        goto LABEL_1112;
      v72 = *v598;
      v66 = (unsigned __int64)(v598 + 1);
      v578 = (char *)(v598 + 1);
      v73 = v72 == 17;
      v74 = v72 <= 0x11;
      if ( v72 != 17 )
        goto LABEL_124;
      LODWORD(v85) = --v557;
      v65 += 4LL;
    }
    v70 = (size_t)(v13 + 513);
  }
  if ( v65 >= (unsigned __int64)(v13 + 2) && v65 <= (unsigned __int64)(v13 + 513) )
  {
    v174 = v616;
    v65 -= 4LL;
    v616 = 0;
    v175 = *(int *)v65 >> 16;
    v73 = v174 == 0;
    v125 = *(_DWORD *)(v65 - 4);
    if ( v73 )
      v175 = *(_DWORD *)v65;
    if ( !v175 )
    {
LABEL_321:
      v158 = ((v125 >> 31) & 1) + 0x7FFFFFFF;
      goto LABEL_301;
    }
    v126 = _mm_cvtsi32_si128(v175);
LABEL_323:
    v176 = (double)v125 / _mm_cvtepi32_pd(v126).m128d_f64[0] * 65536.0;
    if ( v176 >= 0.0 )
      v177 = DOUBLE_0_5;
    else
      v177 = DOUBLE_N0_5;
    v130 = v176 + v177;
    if ( v130 >= 2147483647.0 )
    {
LABEL_327:
      v158 = 0x7FFFFFFF;
      goto LABEL_301;
    }
    v158 = 0x80000000;
    if ( v130 > -2147483648.0 )
LABEL_329:
      v158 = (int)v130;
LABEL_301:
    *(_DWORD *)(v65 - 4) = v158;
LABEL_220:
    v67 = a8;
LABEL_966:
    v29 = a1;
    goto LABEL_967;
  }
LABEL_148:
  if ( gT1DebugLevel )
    os_raise(0xFFFFFFFFLL, 0);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14006b7ac  mov     rax, rsp
0x14006b7af  push    rbp
0x14006b7b0  push    rbx
0x14006b7b1  push    rsi
0x14006b7b2  push    rdi
0x14006b7b3  push    r12
0x14006b7b5  push    r13
0x14006b7b7  push    r14
0x14006b7b9  push    r15
0x14006b7bb  lea     rbp, [rax-5F8h]
0x14006b7c2  sub     rsp, 6B8h
0x14006b7c9  movaps  xmmword ptr [rax-58h], xmm6
0x14006b7cd  movaps  xmmword ptr [rax-68h], xmm7
0x14006b7d1  movaps  xmmword ptr [rax-78h], xmm8
0x14006b7d6  movaps  xmmword ptr [rax-88h], xmm9
0x14006b7de  movaps  xmmword ptr [rax-98h], xmm10
0x14006b7e6  movaps  xmmword ptr [rax-0A8h], xmm11
0x14006b7ee  movaps  xmmword ptr [rax-0B8h], xmm12
0x14006b7f6  movaps  xmmword ptr [rax-0C8h], xmm13
0x14006b7fe  movaps  xmmword ptr [rax-0D8h], xmm14
0x14006b806  mov     rax, cs:__security_cookie
0x14006b80d  xor     rax, rsp
0x14006b810  mov     [rbp+5F0h+var_E0], rax
0x14006b817  mov     r13, [rbp+5F0h+arg_30]
0x14006b81e  mov     r12, r9
0x14006b821  mov     rax, [rbp+5F0h+arg_20]
0x14006b828  mov     r14, rcx
0x14006b82b  mov     rdi, [rbp+5F0h+arg_48]
0x14006b832  mov     rsi, [rbp+5F0h+arg_28]
0x14006b839  mov     [rbp+5F0h+var_498], rax
0x14006b840  mov     rax, [rbp+5F0h+arg_38]
0x14006b847  mov     [rsp+6F0h+var_680], rax
0x14006b84c  mov     rax, [rbp+5F0h+arg_40]
0x14006b853  mov     [rbp+5F0h+var_508], rax
0x14006b85a  mov     rax, [r13+18h]
0x14006b85e  mov     [rbp+5F0h+var_638], rax
0x14006b862  mov     eax, [rcx+2CCh]
0x14006b868  mov     [rbp+5F0h+var_5D8], eax
0x14006b86b  mov     eax, [r13+0]
0x14006b86f  mov     [rbp+5F0h+var_540], eax
0x14006b875  mov     [rbp+5F0h+var_580], rdx
0x14006b879  mov     [rbp+5F0h+var_5B8], r9
0x14006b87d  xor     r9d, r9d
0x14006b880  and     eax, 404h
0x14006b885  mov     [rbp+5F0h+var_628], r8
0x14006b889  mov     [rbp+5F0h+var_608], eax
0x14006b88c  mov     r8, rdx
0x14006b88f  mov     eax, [rcx+3C8h]
0x14006b895  mov     edx, r9d
0x14006b898  mov     [rbp+5F0h+var_53C], eax
0x14006b89e  setnz   dl
0x14006b8a1  mov     rax, [rcx+3D0h]
0x14006b8a8  mov     qword ptr [rsp+6F0h+var_6A0], rcx
0x14006b8ad  mov     [rbp+5F0h+var_548], rdi
0x14006b8b4  mov     [rbp+5F0h+var_668], r13
0x14006b8b8  mov     [rsp+6F0h+var_678], r9
0x14006b8bd  mov     [rbp+5F0h+var_530], r9
0x14006b8c4  mov     [rbp+5F0h+var_558], r9
0x14006b8cb  mov     [rbp+5F0h+var_640], r9
0x14006b8cf  mov     [rbp+5F0h+var_570], r9
0x14006b8d6  mov     [rbp+5F0h+var_538], r9
0x14006b8dd  mov     [rbp+5F0h+var_560], r9
0x14006b8e4  mov     [rbp+5F0h+var_590], r9d
0x14006b8e8  mov     [rbp+5F0h+var_4E0], r9
0x14006b8ef  test    rax, rax
0x14006b8f2  jz      short loc_14006B8F8
0x14006b8f4  mov     [rax+4], r9d
0x14006b8f8  test    rsi, rsi
0x14006b8fb  mov     eax, r9d
0x14006b8fe  mov     rcx, r8
0x14006b901  setz    al
0x14006b904  mov     cs:bprocs, rcx
0x14006b90b  or      ebx, 0FFFFFFFFh
0x14006b90e  cmp     edx, eax
0x14006b910  jz      short loc_14006B925
0x14006b912  xor     edx, edx
0x14006b914  mov     ecx, ebx
0x14006b916  call    os_raise
0x14006b91b  mov     rcx, cs:bprocs
0x14006b922  xor     r9d, r9d
0x14006b925  mov     r15, [r12+18h]
0x14006b92a  lea     rax, gNullPathProcs
0x14006b931  test    rsi, rsi
0x14006b934  mov     [rbp+5F0h+var_4B0], r15
0x14006b93b  mov     [rbp+5F0h+var_4A0], r15
0x14006b942  mov     r8d, 1
0x14006b948  cmovnz  rax, rsi
0x14006b94c  mov     r10d, 0E8300001h
0x14006b952  mov     [rbp+5F0h+var_620], rax
0x14006b956  cmp     [rbp+5F0h+var_608], r9d
0x14006b95a  jnz     loc_14006BA2D
0x14006b960  mov     rax, [r12]
0x14006b964  mov     esi, 2030h
0x14006b969  mov     rdx, [rax+20h]
0x14006b96d  cmp     [rdx+8], esi
0x14006b970  jnb     short loc_14006B9DF
0x14006b972  cmp     [rdx], r9
0x14006b975  jz      short loc_14006B98E
0x14006b977  mov     rcx, [rcx+18h]
0x14006b97b  mov     rax, [rcx]
0x14006b97e  mov     rax, [rax+10h]
0x14006b982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b987  mov     rcx, cs:bprocs
0x14006b98e  mov     rax, [r12]
0x14006b992  mov     rdx, rsi
0x14006b995  mov     rcx, [rcx+18h]
0x14006b999  mov     rdi, [rax+20h]
0x14006b99d  mov     rax, [rcx]
0x14006b9a0  mov     rax, [rax]
0x14006b9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b9a8  mov     [rdi], rax
0x14006b9ab  xor     r9d, r9d
0x14006b9ae  mov     rax, [r12]
0x14006b9b2  mov     rcx, [rax+20h]
0x14006b9b6  cmp     [rcx], r9
0x14006b9b9  jnz     short loc_14006B9C9
0x14006b9bb  mov     [rcx+8], r9d
0x14006b9bf  mov     eax, 0FFFFFFFCh
0x14006b9c4  jmp     loc_140070A34
0x14006b9c9  mov     rdi, [rbp+5F0h+var_548]
0x14006b9d0  mov     r8d, 1
0x14006b9d6  mov     [rcx+8], esi
0x14006b9d9  mov     r10d, 0E8300001h
0x14006b9df  mov     rax, [r12]
0x14006b9e3  mov     rcx, [rax+20h]
0x14006b9e7  mov     rdx, [rcx]
0x14006b9ea  mov     cs:qword_1400B6080, rdx
0x14006b9f1  lea     rcx, [rdx+1018h]
0x14006b9f8  mov     [rdx], r8d
0x14006b9fb  mov     [rdx+40h], r10d
0x14006b9ff  lea     rax, [rdx+38h]
0x14006ba03  mov     [rdx+50h], rax
0x14006ba07  lea     rax, [rcx+38h]
0x14006ba0b  mov     [rdx+44h], r10d
0x14006ba0f  mov     [rdx+48h], r9d
0x14006ba13  mov     [rcx+50h], rax
0x14006ba17  mov     cs:qword_1400B6090, rcx
0x14006ba1e  mov     [rcx], r8d
0x14006ba21  mov     [rcx+40h], r10d
0x14006ba25  mov     [rcx+44h], r10d
0x14006ba29  mov     [rcx+48h], r9d
0x14006ba2d  mov     eax, [rbp+5F0h+var_540]
0x14006ba33  mov     rsi, r9
0x14006ba36  or      eax, 0FFFFFFFEh
0x14006ba39  mov     [rbp+5F0h+var_4A8], r9
0x14006ba40  not     eax
0x14006ba42  mov     r12, r9
0x14006ba45  mov     [rbp+5F0h+var_540], eax
0x14006ba4b  lea     rax, [r14+1Ch]
0x14006ba4f  mov     cs:qword_1400B6060, rax
0x14006ba56  lea     rax, [r14+0E0h]
0x14006ba5d  mov     cs:qword_1400B6070, rax
0x14006ba64  mov     eax, [r14+18h]
0x14006ba68  mov     cs:dword_1400B607C, eax
0x14006ba6e  mov     eax, [r14+0DCh]
0x14006ba75  mov     cs:dword_1400B6068, eax
0x14006ba7b  mov     [rbp+5F0h+var_4D0], r9
0x14006ba82  mov     cs:lockSlopesInited, r9
0x14006ba89  mov     cs:lockFixMapOk, r8d
0x14006ba90  test    [r13+0], r8b
0x14006ba94  jz      short loc_14006BAA3
0x14006ba96  test    [rbp+5F0h+var_5D8], 0C0000000h
0x14006ba9d  mov     [rbp+5F0h+var_62C], r8d
0x14006baa1  jnz     short loc_14006BAA7
0x14006baa3  mov     [rbp+5F0h+var_62C], r9d
0x14006baa7  test    dword ptr [r13+0], 400h
0x14006baaf  jnz     short loc_14006BABE
0x14006bab1  xor     edx, edx
0x14006bab3  mov     rcx, r14
0x14006bab6  call    SetGSMatrix
0x14006babb  xor     r9d, r9d
0x14006babe  mov     r14d, [rbp+5F0h+var_5D8]
0x14006bac2  mov     ecx, 10000h
0x14006bac7  mov     eax, r14d
0x14006baca  and     eax, 10h
0x14006bacd  mov     cs:doFixupMap, eax
0x14006bad3  jz      short loc_14006BB4C
0x14006bad5  cmp     [rbp+5F0h+var_608], r9d
0x14006bad9  jnz     short loc_14006BB4C
0x14006badb  mov     rax, cs:IDTransform
0x14006bae2  lea     rdx, [rbp+5F0h+var_570]
0x14006bae9  mov     dword ptr [rbp+5F0h+var_570], r9d
0x14006baf0  mov     dword ptr [rbp+5F0h+var_570+4], ecx
0x14006baf6  mov     rcx, [rbp+5F0h+var_570]
0x14006bafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bb02  mov     eax, dword ptr [rbp+5F0h+var_570+4]
0x14006bb08  lea     rdx, [rbp+5F0h+var_570]
0x14006bb0f  mov     rcx, cs:qword_1400B6090
0x14006bb16  mov     [rcx+10h], eax
0x14006bb19  mov     rax, cs:IDTransform
0x14006bb20  mov     [rbp+5F0h+var_570], 10000h
0x14006bb2b  mov     rcx, [rbp+5F0h+var_570]
0x14006bb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bb37  mov     rcx, cs:qword_1400B6080
0x14006bb3e  mov     eax, dword ptr [rbp+5F0h+var_570]
0x14006bb44  mov     [rcx+10h], eax
0x14006bb47  mov     ecx, 10000h
0x14006bb4c  mov     r10, qword ptr [rsp+6F0h+var_6A0]
0x14006bb51  mov     r8d, 2
0x14006bb57  mov     cs:erosion, ecx
0x14006bb5d  cmp     [r10+2D4h], r8d
0x14006bb64  jnz     short loc_14006BBA5
0x14006bb66  lea     eax, [r8-1]
0x14006bb6a  mov     edx, ecx
0x14006bb6c  mov     ecx, [r10+2C8h]
0x14006bb73  mov     r8d, eax
0x14006bb76  mov     cs:dword_1400B606C, eax
0x14006bb7c  call    ErodeSW
0x14006bb81  mov     r10, qword ptr [rsp+6F0h+var_6A0]
0x14006bb86  add     eax, 8000h
0x14006bb8b  shr     eax, 10h
0x14006bb8e  mov     r11d, 1
0x14006bb94  not     eax
0x14006bb96  and     eax, r11d
0x14006bb99  mov     cs:dword_1400B6078, eax
0x14006bb9f  lea     r8d, [r11+1]
0x14006bba3  jmp     short loc_14006BBB5
0x14006bba5  mov     cs:dword_1400B606C, 0
0x14006bbaf  mov     r11d, 1
0x14006bbb5  movsd   xmm11, cs:__real@40f0000000000000
0x14006bbbe  mov     eax, r14d
0x14006bbc1  movsd   xmm10, cs:__real@bfe0000000000000
0x14006bbca  or      eax, 0FFFFFFDFh
0x14006bbcd  movsd   xmm6, cs:__real@3fe0000000000000
0x14006bbd5  not     eax
0x14006bbd7  movsd   xmm8, cs:__real@41dfffffffc00000
0x14006bbe0  mov     r14d, 0FFFFFFF6h
0x14006bbe6  movsd   xmm7, cs:__real@c1e0000000000000
0x14006bbee  xorps   xmm9, xmm9
0x14006bbf2  movsd   xmm12, cs:__real@3e10000000000000
0x14006bbfb  movsd   xmm13, cs:__real@41d0000000000000
0x14006bc04  movsd   xmm14, cs:__real@3ef0000000000000
0x14006bc0d  mov     cs:dword_1400B6088, 0
0x14006bc17  mov     [rbp+5F0h+var_520], 0FFFF8000h
0x14006bc21  mov     [rbp+5F0h+var_4C8], 7FFFh
0x14006bc2b  test    eax, eax
0x14006bc2d  jnz     short loc_14006BC3D
0x14006bc2f  cmp     [rbp+5F0h+var_608], eax
0x14006bc32  jnz     short loc_14006BC3D
0x14006bc34  cmp     [rbp+5F0h+var_62C], eax
0x14006bc37  jnz     loc_14006D496
0x14006bc3d  mov     cs:T1globalColoring, r8d
0x14006bc44  jmp     short loc_14006BC4A
0x14006bc46  mov     r13, [rbp+5F0h+var_668]
0x14006bc4a  mov     rax, [rbp+5F0h+var_5B8]
0x14006bc4e  mov     cs:CSIdealOffset, 0
0x14006bc58  mov     cs:CSIdealBase, 0
0x14006bc62  mov     cs:nGlbColors, 0
0x14006bc6c  mov     dword ptr [rax+24h], 0
0x14006bc73  cmp     dword ptr [r10+3C4h], 0
0x14006bc7b  mov     cs:gcList, 0
0x14006bc86  mov     cs:glbCounterList, 0
0x14006bc91  mov     cs:nGlbCounters, 0
0x14006bc9b  mov     [rbp+5F0h+var_538], 0
0x14006bca6  mov     [rbp+5F0h+var_530], 0
0x14006bcb1  mov     [rsp+6F0h+var_678], 0
0x14006bcba  mov     cs:lockFixedMap, 0
0x14006bcc4  mov     qword ptr [r10+3B4h], 0
0x14006bccf  mov     dword ptr [r10+3BCh], 0
0x14006bcda  jz      short loc_14006BCE3
0x14006bcdc  mov     [r10+3B4h], r11d
0x14006bce3  mov     rcx, [rsp+6F0h+var_680]
0x14006bce8  xor     r10d, r10d
0x14006bceb  xor     eax, eax
0x14006bced  mov     [rbp+5F0h+var_590], eax
0x14006bcf0  lea     r11, [rcx+18h]
0x14006bcf4  mov     [r11], r10d
0x14006bcf7  test    byte ptr [r13+0], 18h
0x14006bcfc  mov     [rbp+5F0h+var_610], r11
0x14006bd00  jz      loc_14006BF13
0x14006bd06  mov     rdx, [rbp+5F0h+var_668]
0x14006bd0a  mov     r13d, r10d
0x14006bd0d  test    byte ptr [rdx], 20h
0x14006bd10  jz      short loc_14006BD28
0x14006bd12  test    byte ptr [rdx], 40h
0x14006bd15  jz      short loc_14006BD20
0x14006bd17  mov     rax, [rbp+5F0h+var_638]
0x14006bd1b  mov     r13, [rax]
0x14006bd1e  jmp     short loc_14006BD24
0x14006bd20  mov     r13, [rbp+5F0h+var_638]
0x14006bd24  add     r13, 10h
0x14006bd28  test    byte ptr [rdx], 10h
0x14006bd2b  jz      loc_14006BE0D
0x14006bd31  mov     rax, [rdx+8]
0x14006bd35  lea     r8, [rcx+0Ch]
0x14006bd39  mov     r10d, [rax+8]
0x14006bd3d  mov     [r8], r10d
0x14006bd40  mov     dword ptr [rcx+1Ch], 2
0x14006bd47  test    byte ptr [rdx], 20h
0x14006bd4a  jz      loc_14006BE71
0x14006bd50  mov     r9, [r13+0]
0x14006bd54  mov     [rbp+5F0h+var_4A8], r9
0x14006bd5b  test    r9, r9
0x14006bd5e  jz      loc_14006BE71
0x14006bd64  mov     rax, [rdx+8]
0x14006bd68  mov     ecx, [rax]
0x14006bd6a  mov     edx, [rax+4]
0x14006bd6d  add     ecx, 8000h
0x14006bd73  movzx   eax, word ptr [r9]
0x14006bd77  add     edx, 8000h
  ... truncated ...
```
