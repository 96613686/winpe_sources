# LZ4HC_compress_generic_dictCtx

- ea: `0x1800efdb4`
- end: `0x1800f76fd`
- name: `LZ4HC_compress_generic_dictCtx`
- size: `31049`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ed460`

## callees

- `0x1800e5f28`
- `0x1800e5f84`
- `0x1800efdb4`
- `0x18010a3a0`
- `0x18011f26c`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall LZ4HC_compress_generic_dictCtx(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        unsigned int *a4,
        int a5,
        __int64 a6,
        int a7)
{
  unsigned int v7; // esi
  __int64 v10; // r10
  unsigned __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rbx
  unsigned int *v15; // r8
  __int64 v16; // rdx
  char *v17; // r15
  unsigned __int64 v18; // rcx
  char *v19; // r9
  unsigned __int64 v20; // r13
  size_t v21; // r9
  size_t v22; // rdi
  unsigned __int64 v23; // rax
  int v24; // eax
  unsigned int *v26; // r9
  char *v27; // r15
  __int64 v28; // rdx
  char *v29; // r8
  __int64 v30; // rdi
  unsigned __int64 v31; // r14
  size_t v32; // r8
  size_t v33; // rbx
  int v34; // esi
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned int v37; // r13d
  unsigned int v38; // edx
  __int64 v39; // r10
  __int64 v40; // r11
  _QWORD *v41; // r14
  unsigned int v42; // r12d
  _QWORD *v43; // r9
  unsigned int v44; // edi
  __int64 v45; // rcx
  int v46; // edx
  unsigned int v47; // r8d
  _DWORD *v48; // r8
  unsigned int v49; // r11d
  __int64 v50; // r8
  __int64 v51; // rdx
  _QWORD *v52; // r8
  _QWORD *v53; // rdx
  _QWORD *v54; // rcx
  unsigned int v57; // ecx
  __int64 v58; // rdx
  _QWORD *v59; // r9
  _QWORD *v60; // r8
  _QWORD *v61; // rdx
  _QWORD *v62; // rcx
  signed int v64; // r10d
  int v65; // ecx
  _QWORD *v66; // r9
  _QWORD *v67; // rcx
  _QWORD *v68; // rdx
  unsigned int v69; // ecx
  signed int v70; // ecx
  __int64 v71; // r10
  unsigned int v72; // eax
  unsigned int v73; // r15d
  int v74; // r12d
  _DWORD *v75; // rdi
  _DWORD *v76; // r14
  unsigned __int64 v77; // rsi
  __int64 v78; // r9
  _QWORD *v79; // rdx
  unsigned int v80; // eax
  __int64 v81; // r8
  unsigned int v82; // r11d
  unsigned int v83; // eax
  unsigned int v84; // r11d
  unsigned __int64 v85; // rcx
  int v86; // r9d
  __int16 v87; // r11
  _DWORD *v88; // rdx
  unsigned __int64 v89; // rcx
  unsigned __int64 v90; // r15
  __int64 v91; // r14
  _DWORD *v92; // r10
  __int16 v93; // di
  int v94; // r12d
  unsigned __int64 v95; // rsi
  __int64 v96; // r10
  _DWORD *v97; // r13
  __int16 v98; // r15
  int v99; // r14d
  __int64 v100; // r11
  unsigned __int64 v101; // r10
  int v102; // r10d
  int v103; // ecx
  __int64 v104; // rdi
  _BYTE *v105; // rcx
  unsigned int v106; // esi
  char *v107; // r9
  char *v108; // rbx
  unsigned __int64 v109; // r8
  unsigned __int64 v110; // rax
  __int64 *v111; // rdx
  _WORD *v112; // rbx
  __int64 v113; // rax
  unsigned __int64 v114; // rcx
  char v115; // al
  unsigned __int64 j; // rax
  unsigned __int64 v117; // rdx
  unsigned int v118; // ecx
  int v119; // eax
  int v120; // r11d
  int v121; // r11d
  _BYTE *v122; // rcx
  unsigned __int64 v123; // r8
  unsigned __int64 v124; // rax
  __int64 *v125; // rdx
  _WORD *v126; // r9
  __int64 v127; // rax
  __int64 v128; // rcx
  __int16 v129; // r14
  __int64 v130; // r9
  unsigned __int64 v131; // r8
  char v132; // al
  unsigned __int64 n; // rax
  _BYTE *v134; // r8
  char *v135; // r11
  unsigned __int64 v136; // r9
  unsigned __int64 v137; // rax
  __int64 *v138; // rdx
  _WORD *v139; // rbx
  __int64 v140; // rax
  __int16 v141; // r9
  unsigned __int64 v142; // r8
  char v143; // al
  unsigned __int64 ii; // rax
  int v145; // ecx
  __int16 v146; // r13
  _BYTE *v147; // rcx
  char *v148; // r9
  unsigned __int64 v149; // r8
  unsigned __int64 v150; // rax
  __int64 *v151; // rdx
  _WORD *v152; // rbx
  __int64 v153; // rax
  unsigned __int64 v154; // rcx
  char v155; // al
  unsigned __int64 m; // rax
  _BYTE *v157; // rcx
  unsigned __int64 v158; // r8
  char *v159; // r9
  unsigned __int64 v160; // rax
  __int64 *v161; // rdx
  _WORD *v162; // rbx
  __int64 v163; // rax
  unsigned __int64 v164; // rcx
  char v165; // al
  unsigned __int64 i; // rcx
  int v175; // edx
  int v176; // ecx
  _BYTE *v177; // rcx
  _BYTE *v178; // rbx
  _DWORD *v179; // r15
  unsigned int v180; // r10d
  unsigned int v181; // r14d
  char *v182; // rdi
  _QWORD *v183; // r12
  char *v184; // rdx
  unsigned int v185; // r8d
  unsigned int v186; // esi
  unsigned int v187; // r9d
  unsigned int v188; // r13d
  int v189; // eax
  int v190; // r8d
  int v191; // r14d
  _DWORD *v192; // r14
  unsigned int v193; // edi
  _QWORD *v194; // r15
  __int64 v195; // r10
  unsigned int v196; // r8d
  unsigned int v197; // r11d
  unsigned int v198; // esi
  char *v199; // rdx
  unsigned int v200; // r9d
  unsigned int v201; // r13d
  int v202; // eax
  int v203; // r12d
  int v204; // r8d
  int v205; // esi
  _BYTE *v206; // rbx
  int v208; // r10d
  unsigned __int64 v209; // r8
  unsigned __int64 v210; // r9
  _BYTE *v211; // rcx
  unsigned __int64 v212; // rax
  _WORD *v213; // rbx
  __int64 v214; // rax
  char v215; // cl
  unsigned __int64 k; // rax
  _DWORD *v217; // r9
  bool v218; // zf
  int v219; // r8d
  int v220; // edx
  __int64 v221; // rax
  unsigned int v222; // eax
  unsigned __int64 v223; // r12
  _QWORD *v224; // r10
  _QWORD *v225; // rdx
  _QWORD *v226; // rcx
  unsigned int v229; // ecx
  _DWORD *v230; // r9
  int v231; // edx
  __int64 v232; // rax
  unsigned int v233; // eax
  unsigned __int64 v234; // r15
  _QWORD *v235; // r10
  _QWORD *v236; // rdx
  _QWORD *v237; // rcx
  unsigned int v240; // ecx
  char *v241; // r14
  _QWORD *v242; // r9
  _QWORD *v243; // rdi
  _QWORD *v244; // rdx
  _QWORD *v245; // rcx
  signed int v248; // esi
  _BYTE *v249; // rbx
  char *v250; // rsi
  _QWORD *v251; // r9
  _QWORD *v252; // r11
  _QWORD *v253; // rdx
  _QWORD *v254; // rcx
  signed int v257; // edi
  _BYTE *v258; // rbx
  unsigned int *v259; // r11
  __int64 v260; // rdx
  unsigned __int64 v261; // rcx
  char *v262; // r8
  unsigned __int64 v263; // r14
  unsigned __int64 v264; // r9
  size_t v265; // r8
  bool v266; // cf
  _BYTE *v267; // rbx
  _QWORD *v268; // rcx
  _QWORD *v269; // rdx
  unsigned int v270; // ecx
  int v271; // r10d
  int v272; // edx
  int v273; // r8d
  unsigned int v274; // eax
  int v275; // r10d
  unsigned int v276; // r10d
  unsigned int v277; // r12d
  int v278; // r15d
  char *v279; // rsi
  __int64 v280; // r9
  unsigned __int64 v281; // r14
  char *v282; // rdx
  unsigned int v283; // eax
  char *v284; // r8
  unsigned int v285; // esi
  unsigned __int64 v286; // rcx
  unsigned __int64 v287; // rdx
  unsigned int v288; // ecx
  __int64 v289; // r8
  unsigned __int64 v290; // rcx
  __int64 v291; // r13
  int v292; // r12d
  _QWORD *v293; // rsi
  unsigned int v294; // r10d
  unsigned int v295; // ebx
  __int64 v296; // rdx
  unsigned int v297; // r14d
  int v298; // r15d
  unsigned int v299; // r9d
  unsigned int v300; // r8d
  _DWORD *v301; // r9
  unsigned int v302; // r11d
  __int64 v303; // r8
  __int64 v304; // rdx
  _QWORD *v305; // r8
  _QWORD *v306; // rdx
  char *v307; // rcx
  unsigned int v311; // ecx
  int v312; // ecx
  _QWORD *v313; // r9
  int v315; // ecx
  _QWORD *v316; // rcx
  _QWORD *v317; // rdx
  unsigned int v318; // ecx
  int v319; // r10d
  int v320; // edx
  int v321; // r8d
  unsigned int v322; // eax
  int v323; // r10d
  __int64 v324; // r9
  unsigned int v325; // r10d
  unsigned int v326; // r12d
  int v327; // r15d
  char *v328; // rdi
  char *v329; // rsi
  __int64 v330; // r9
  unsigned __int64 v331; // r14
  char *v332; // rdx
  unsigned int v333; // esi
  char *v334; // r13
  unsigned int v335; // eax
  char *v336; // r8
  unsigned int v337; // r11d
  unsigned __int64 v338; // rcx
  unsigned __int64 v339; // rdx
  unsigned int v340; // ecx
  __int64 v341; // r8
  int v342; // eax
  int v343; // r11d
  unsigned int v344; // ecx
  _QWORD *v345; // r9
  unsigned __int64 v356; // r9
  _QWORD *v357; // r8
  _QWORD *v358; // rdx
  _QWORD *v359; // rcx
  signed int v361; // r10d
  int v362; // ecx
  char *v363; // r8
  char *v364; // rcx
  _QWORD *v365; // rdx
  unsigned int v366; // ecx
  int v372; // ebx
  __int16 v373; // r11
  _DWORD *v374; // rdx
  unsigned __int64 v375; // rcx
  unsigned __int64 v376; // r15
  __int64 v377; // r14
  _DWORD *v378; // r10
  __int16 v379; // r8
  int v380; // r12d
  unsigned __int64 v381; // rsi
  __int64 v382; // r10
  _DWORD *v383; // r13
  __int16 v384; // r15
  int v385; // r14d
  __int64 v386; // r11
  unsigned __int64 v387; // r10
  int v388; // r11d
  int v389; // r11d
  _BYTE *v390; // rcx
  __int64 v391; // rbx
  unsigned __int64 v392; // r8
  unsigned int v393; // esi
  unsigned __int64 v394; // rax
  __int64 *v395; // rdx
  _WORD *v396; // r9
  __int64 v397; // rax
  __int64 v398; // rcx
  unsigned __int64 v399; // r8
  char v400; // al
  int v401; // ecx
  __int16 v402; // r13
  _BYTE *v403; // rcx
  char *v404; // r9
  unsigned __int64 v405; // r8
  unsigned __int64 v406; // rax
  __int64 *v407; // rdx
  _WORD *v408; // rdi
  __int64 v409; // rax
  unsigned __int64 v410; // rcx
  char v411; // al
  unsigned __int64 i9; // rax
  signed int v413; // ecx
  unsigned int v414; // r12d
  int v415; // r14d
  _DWORD *v416; // rbx
  char *v417; // rsi
  unsigned __int64 v418; // r15
  unsigned __int64 v419; // r9
  unsigned __int64 jj; // rcx
  _BYTE *kk; // r8
  int v422; // edx
  __int64 v423; // r9
  unsigned int v424; // r11d
  unsigned __int64 v425; // rcx
  unsigned __int64 v426; // rdx
  unsigned int v427; // ecx
  int v428; // eax
  int v429; // r9d
  unsigned __int64 v430; // rcx
  _BYTE *mm; // r8
  int v432; // edx
  _BYTE *v433; // rcx
  unsigned __int64 v434; // r8
  char *v435; // r9
  unsigned __int64 v436; // rax
  __int64 *v437; // rdx
  _WORD *v438; // rdi
  __int64 v439; // rax
  __int16 v440; // r11
  unsigned __int64 v441; // rcx
  char v442; // al
  int v449; // r8d
  int v450; // ecx
  unsigned __int64 i10; // rax
  _BYTE *v452; // r8
  unsigned __int64 v453; // r9
  unsigned __int64 v454; // rax
  __int64 *v455; // rdx
  _WORD *v456; // rdi
  __int64 v457; // rax
  unsigned __int64 v458; // r8
  char v459; // al
  unsigned __int64 i11; // rax
  int v461; // ecx
  _BYTE *v462; // rcx
  char *v463; // r9
  unsigned __int64 v464; // r8
  unsigned __int64 v465; // rax
  __int64 *v466; // rdx
  _WORD *v467; // rdi
  __int64 v468; // rax
  unsigned __int64 v469; // rcx
  char v470; // al
  unsigned __int64 i8; // rax
  _DWORD *v472; // r15
  unsigned int v473; // edx
  unsigned int v474; // r14d
  char *v475; // rsi
  char *v476; // rbx
  char *v477; // r9
  unsigned int v478; // r12d
  unsigned int v479; // r8d
  unsigned int v480; // r10d
  unsigned int v481; // r13d
  _DWORD *v482; // r15
  unsigned int v483; // r11d
  unsigned int v484; // edx
  char *v485; // rsi
  unsigned int v486; // ebx
  char *v487; // r9
  unsigned int v488; // r8d
  unsigned int v489; // r14d
  unsigned int v490; // r10d
  unsigned int v491; // r13d
  _BYTE *v492; // rcx
  _BYTE *v493; // rdi
  int v494; // edx
  int v495; // eax
  int v496; // r8d
  int v497; // r12d
  int v498; // eax
  int v499; // r10d
  _BYTE *v502; // rdi
  unsigned __int64 v503; // r8
  unsigned __int64 v504; // r9
  _BYTE *v505; // rcx
  unsigned __int64 v506; // rax
  _WORD *v507; // rdi
  __int64 v508; // rax
  char v509; // cl
  unsigned __int64 i3; // rax
  _BYTE *v511; // rdi
  char *v512; // r9
  int v513; // r8d
  int v514; // edx
  __int64 v515; // rax
  unsigned int v516; // eax
  _QWORD *v517; // r10
  _QWORD *v518; // rdx
  char *v519; // rcx
  int v522; // edx
  char *v523; // r8
  int v524; // r9d
  int v525; // edx
  __int64 v526; // rax
  unsigned int v527; // eax
  _QWORD *v528; // r10
  _QWORD *v529; // rdx
  char *v530; // rcx
  unsigned int v533; // ecx
  unsigned int v534; // r12d
  int v535; // r14d
  char *v536; // rsi
  unsigned __int64 v537; // r15
  unsigned __int64 v538; // r13
  char *v539; // r9
  unsigned __int64 nn; // rdx
  _BYTE *i1; // r8
  int v542; // ecx
  __int64 v543; // r9
  unsigned __int64 v544; // rcx
  unsigned __int64 v545; // rdx
  unsigned int v546; // ecx
  char *v547; // r14
  _QWORD *v548; // r9
  unsigned __int64 v549; // rbx
  _QWORD *v550; // rdx
  _QWORD *v551; // rcx
  signed int v554; // esi
  int v556; // r10d
  char *v557; // r9
  _QWORD *v558; // rdx
  char *v559; // rcx
  unsigned int v562; // ecx
  int v564; // edx
  int v565; // r8d
  unsigned int v566; // eax
  int v567; // r10d
  int v568; // eax
  int v569; // r9d
  unsigned __int64 v570; // rdx
  _BYTE *i2; // r8
  int v572; // ecx
  unsigned int v573; // ecx
  char *v574; // rsi
  _QWORD *v575; // r9
  unsigned __int64 v576; // r11
  _QWORD *v577; // rdx
  _QWORD *v578; // rcx
  unsigned int v581; // eax
  int v582; // edx
  int v583; // r10d
  unsigned int v584; // r12d
  int v585; // r14d
  char *v586; // rbx
  char *v587; // rsi
  unsigned __int64 v588; // r15
  unsigned __int64 v589; // r13
  char *v590; // r9
  unsigned __int64 i5; // rdx
  _BYTE *i6; // r8
  int v593; // ecx
  __int64 v594; // r9
  unsigned __int64 v595; // rcx
  unsigned __int64 v596; // rdx
  unsigned int v597; // ecx
  signed int v598; // ebx
  int v600; // r10d
  char *v601; // r9
  _QWORD *v602; // rdx
  char *v603; // rcx
  unsigned int v606; // ecx
  int v608; // r8d
  int v609; // eax
  int v610; // r9d
  unsigned __int64 v611; // rdx
  _BYTE *i7; // r8
  int v613; // ecx
  unsigned __int64 v614; // rcx
  __int64 v615; // r12
  int v616; // r14d
  _QWORD *v617; // r15
  __int64 v618; // r13
  unsigned int v619; // r10d
  unsigned int v620; // ebx
  __int64 v621; // rdx
  unsigned int v622; // r12d
  unsigned int v623; // r8d
  unsigned __int64 v624; // rcx
  unsigned int v625; // r11d
  bool v626; // cc
  __int64 v627; // r8
  __int64 v628; // rdx
  _QWORD *v629; // r8
  _QWORD *v630; // rdx
  _QWORD *v631; // rcx
  __int64 v634; // r14
  __int64 v635; // r15
  unsigned int v636; // ebx
  __int64 v637; // rsi
  int v638; // r9d
  int v639; // edi
  unsigned __int64 v640; // r8
  _QWORD *v641; // r10
  _QWORD *v642; // rdx
  _QWORD *v643; // rcx
  unsigned int v646; // ecx
  signed int v647; // ecx
  int v648; // ecx
  int v649; // ebx
  __int16 v650; // r11
  unsigned __int64 v651; // r9
  unsigned __int64 v652; // rcx
  unsigned __int64 v653; // rdx
  unsigned __int64 v654; // r15
  __int64 v655; // r14
  _DWORD *v656; // r10
  int v657; // r9d
  _DWORD *v658; // r12
  __int64 v659; // rbx
  __int64 v660; // rdx
  unsigned int v661; // r10d
  _QWORD *v662; // r15
  __int64 v663; // rsi
  char *v664; // r14
  unsigned int v665; // r8d
  unsigned int v666; // r9d
  unsigned __int64 v667; // rcx
  unsigned int v668; // r13d
  unsigned int v669; // r11d
  char *v670; // rdi
  int v671; // esi
  int v672; // edx
  bool v673; // cc
  _DWORD *v674; // r9
  int v675; // r8d
  int v676; // edx
  __int64 v677; // rax
  unsigned int v678; // eax
  unsigned __int64 v679; // r15
  _QWORD *v680; // r10
  _QWORD *v681; // rdx
  _QWORD *v682; // rcx
  unsigned int v686; // ecx
  _QWORD *v687; // r8
  _QWORD *v688; // rdx
  _QWORD *v689; // rcx
  signed int v693; // r10d
  signed int v695; // ecx
  unsigned int v696; // r14d
  int v697; // r12d
  _DWORD *v698; // rbx
  _DWORD *v699; // r15
  unsigned __int64 v700; // rsi
  unsigned int v701; // eax
  __int64 v702; // r9
  _QWORD *v703; // rdx
  unsigned int v704; // eax
  unsigned int v705; // r8d
  unsigned int v706; // r11d
  unsigned int v707; // eax
  int v708; // eax
  int v709; // r11d
  unsigned int v710; // eax
  unsigned int v711; // r11d
  unsigned __int64 v712; // rcx
  unsigned __int64 v713; // rdx
  unsigned int v714; // ecx
  int v716; // ecx
  _QWORD *v717; // r8
  _QWORD *v718; // rcx
  _QWORD *v720; // rdx
  unsigned int v722; // ecx
  unsigned int v723; // ecx
  __int64 v724; // r9
  char *v725; // r14
  _QWORD *v726; // r9
  _QWORD *v727; // rbx
  _QWORD *v728; // rdx
  _QWORD *v729; // rcx
  signed int v732; // esi
  int v734; // r10d
  _QWORD *v735; // r9
  _QWORD *v736; // rcx
  _QWORD *v738; // rdx
  unsigned int v740; // ecx
  int v742; // edx
  int v743; // r8d
  unsigned int v744; // eax
  int v745; // r10d
  int v747; // ecx
  unsigned int v748; // eax
  unsigned int v749; // r15d
  int v750; // r12d
  char *v751; // rbx
  char *v752; // rsi
  unsigned __int64 v753; // r14
  unsigned int v754; // eax
  __int64 v755; // r9
  char *v756; // r13
  char *v757; // rdx
  unsigned int v758; // eax
  char *v759; // r8
  unsigned int v760; // esi
  unsigned int v761; // eax
  unsigned __int64 v762; // rcx
  int v763; // r12d
  __int16 v764; // r8
  _BYTE *v765; // rcx
  __int64 v766; // rbx
  unsigned __int64 v767; // r8
  unsigned int v768; // esi
  char *v769; // r9
  unsigned __int64 v770; // rax
  __int64 *v771; // rdx
  _WORD *v772; // rdi
  __int64 v773; // rax
  __int16 v774; // r11
  unsigned __int64 v775; // rcx
  char v776; // al
  unsigned __int64 i16; // rcx
  unsigned __int64 v778; // rdx
  unsigned int v779; // ecx
  __int64 v780; // r15
  __int64 v781; // r12
  __int64 v782; // r14
  unsigned int v783; // esi
  __int64 v784; // r14
  int v785; // r10d
  unsigned int v786; // r11d
  _DWORD *v787; // rbx
  _QWORD *v788; // r9
  unsigned __int64 v789; // r8
  _QWORD *v790; // rdx
  _QWORD *v791; // rcx
  unsigned int v794; // ecx
  int v796; // edx
  int v797; // r8d
  unsigned int v798; // eax
  int v799; // ecx
  unsigned __int64 v800; // rsi
  int v801; // r8d
  int v802; // ecx
  __int64 v803; // r10
  _DWORD *v804; // r13
  _DWORD *v805; // r12
  __int64 v806; // rdx
  unsigned int v807; // ebx
  _QWORD *v808; // r14
  unsigned int v809; // esi
  __int64 v810; // r11
  char *v811; // r15
  unsigned int v812; // r9d
  unsigned int v813; // r8d
  unsigned int v814; // r10d
  unsigned __int64 v815; // rcx
  unsigned int v816; // r13d
  unsigned int v817; // edi
  int v818; // r11d
  bool v819; // cc
  _DWORD *v820; // r9
  int v821; // r8d
  int v822; // edx
  __int64 v823; // rax
  unsigned int v824; // eax
  _QWORD *v825; // r10
  _QWORD *v826; // rdx
  _QWORD *v827; // rcx
  unsigned int v830; // ecx
  char *v831; // rsi
  _QWORD *v832; // r9
  _QWORD *v833; // r11
  _QWORD *v834; // rdx
  _QWORD *v835; // rcx
  signed int v838; // ebx
  int v840; // r10d
  _QWORD *v841; // r9
  _QWORD *v842; // rcx
  _QWORD *v844; // rdx
  unsigned int v846; // ecx
  int v848; // edx
  int v849; // r8d
  unsigned int v850; // eax
  int v851; // r10d
  __int64 v852; // r9
  unsigned int v853; // eax
  unsigned int v854; // r15d
  int v855; // r12d
  _DWORD *v856; // rbx
  _DWORD *v857; // rsi
  unsigned __int64 v858; // r14
  unsigned int v859; // eax
  _DWORD *v860; // rsi
  __int64 v861; // r9
  _QWORD *v862; // rdx
  unsigned int v863; // eax
  unsigned int v864; // r8d
  unsigned int v865; // r11d
  unsigned int v866; // eax
  int v867; // eax
  int v868; // r11d
  unsigned __int64 v869; // rcx
  int v870; // r14d
  __int16 v871; // r15
  __int64 v872; // r11
  int v873; // r11d
  _BYTE *v874; // rcx
  unsigned __int64 v875; // r8
  unsigned __int64 v876; // rax
  __int64 *v877; // rdx
  _WORD *v878; // r9
  __int64 v879; // rax
  __int64 v880; // rcx
  unsigned __int64 v881; // r8
  char v882; // al
  unsigned __int64 i12; // rax
  _BYTE *v884; // r8
  unsigned __int64 v885; // r9
  unsigned __int64 v886; // rax
  __int64 *v887; // rdx
  _WORD *v888; // rdi
  __int64 v889; // rax
  unsigned __int64 v890; // r8
  char v891; // al
  unsigned __int64 i13; // rax
  unsigned __int64 v893; // rdx
  unsigned int v894; // ecx
  __int64 v895; // r12
  __int64 v896; // r15
  unsigned int v897; // esi
  __int64 v898; // r14
  int v899; // ebx
  int v900; // edi
  _DWORD *v901; // r11
  _QWORD *v902; // r9
  unsigned __int64 v903; // r8
  _QWORD *v904; // rdx
  _QWORD *v905; // rcx
  unsigned int v908; // ecx
  int v910; // edx
  int v911; // r8d
  unsigned int v912; // eax
  int v913; // ecx
  unsigned __int64 v914; // r10
  int v915; // ecx
  __int16 v916; // r13
  _BYTE *v917; // rcx
  char *v918; // r9
  unsigned __int64 v919; // r8
  unsigned __int64 v920; // rax
  __int64 *v921; // rdx
  _WORD *v922; // rdi
  __int64 v923; // rax
  unsigned __int64 v924; // rcx
  char v925; // al
  unsigned __int64 i15; // rax
  int v927; // r11d
  int v928; // ecx
  _BYTE *v929; // rcx
  char *v930; // r9
  unsigned __int64 v931; // r8
  unsigned __int64 v932; // rax
  __int64 *v933; // rdx
  _WORD *v934; // rdi
  __int64 v935; // rax
  unsigned __int64 v936; // rcx
  char v937; // al
  unsigned __int64 i14; // rax
  _BYTE *v939; // rdi
  int v940; // r10d
  unsigned __int64 v941; // r8
  unsigned __int64 v942; // r9
  _BYTE *v943; // rcx
  unsigned __int64 v944; // rax
  _WORD *v945; // rdi
  __int64 v946; // rax
  char v947; // cl
  unsigned __int64 i17; // rax
  _BYTE *v949; // rdi
  int v951; // ecx
  unsigned int v955; // eax
  int v957; // ecx
  unsigned int v961; // eax
  unsigned int v962; // ecx
  _BYTE *v963; // rdi
  unsigned __int64 i4; // rcx
  _BYTE *v965; // rdi
  int v975; // ecx
  _BYTE *v980; // rdi
  _BYTE *v981; // rdi
  _BYTE *v982; // rcx
  _BYTE *v983; // rdi
  __int64 v984; // r8
  unsigned __int64 v985; // rax
  __int64 v986; // r8
  unsigned __int64 v987; // rax
  __int64 v988; // r8
  unsigned __int64 v989; // rax
  unsigned int v990; // eax
  __int64 v991; // r9
  unsigned int v992; // eax
  __int64 v993; // r9
  unsigned int v994; // eax
  __int64 v995; // r9
  unsigned __int64 v996; // rdx
  unsigned __int64 v997; // rcx
  unsigned __int64 v998; // rdx
  unsigned __int64 v999; // rcx
  unsigned __int64 v1000; // rdx
  unsigned __int64 v1001; // rcx
  unsigned __int64 v1002; // rdx
  unsigned __int64 v1003; // rcx
  unsigned __int64 v1004; // rdx
  unsigned __int64 v1005; // rcx
  unsigned __int64 v1006; // rdx
  unsigned __int64 v1007; // rcx
  unsigned __int64 v1008; // rdx
  unsigned __int64 v1009; // rcx
  __int64 v1010; // r11
  unsigned __int64 v1011; // rdx
  unsigned __int64 v1012; // rcx
  __int64 v1013; // rbx
  unsigned __int64 v1014; // rdx
  unsigned __int64 v1015; // rcx
  int v1016; // [rsp+20h] [rbp-E0h]
  int v1017; // [rsp+20h] [rbp-E0h]
  int v1018; // [rsp+20h] [rbp-E0h]
  unsigned int v1019; // [rsp+20h] [rbp-E0h]
  unsigned int v1020; // [rsp+20h] [rbp-E0h]
  unsigned int v1021; // [rsp+24h] [rbp-DCh]
  unsigned int v1022; // [rsp+24h] [rbp-DCh]
  unsigned int v1023; // [rsp+24h] [rbp-DCh]
  int v1024; // [rsp+24h] [rbp-DCh]
  unsigned int v1025; // [rsp+24h] [rbp-DCh]
  int v1026; // [rsp+24h] [rbp-DCh]
  int v1027; // [rsp+24h] [rbp-DCh]
  unsigned int v1028; // [rsp+24h] [rbp-DCh]
  unsigned int v1029; // [rsp+24h] [rbp-DCh]
  unsigned int v1030; // [rsp+28h] [rbp-D8h]
  unsigned int v1031; // [rsp+28h] [rbp-D8h]
  unsigned int v1032; // [rsp+28h] [rbp-D8h]
  int v1033; // [rsp+2Ch] [rbp-D4h]
  int v1034; // [rsp+2Ch] [rbp-D4h]
  int v1035; // [rsp+2Ch] [rbp-D4h]
  int v1036; // [rsp+2Ch] [rbp-D4h]
  unsigned int v1037; // [rsp+30h] [rbp-D0h]
  int v1038; // [rsp+30h] [rbp-D0h]
  unsigned int v1039; // [rsp+30h] [rbp-D0h]
  unsigned int v1040; // [rsp+30h] [rbp-D0h]
  int v1041; // [rsp+30h] [rbp-D0h]
  int v1042; // [rsp+30h] [rbp-D0h]
  int v1043; // [rsp+30h] [rbp-D0h]
  int v1044; // [rsp+30h] [rbp-D0h]
  _DWORD *v1045; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v1046; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v1047; // [rsp+38h] [rbp-C8h]
  __int16 v1048; // [rsp+40h] [rbp-C0h]
  __int16 v1049; // [rsp+40h] [rbp-C0h]
  unsigned int v1050; // [rsp+40h] [rbp-C0h]
  __int16 v1051; // [rsp+40h] [rbp-C0h]
  int v1052; // [rsp+44h] [rbp-BCh]
  unsigned int v1053; // [rsp+44h] [rbp-BCh]
  __int16 v1054; // [rsp+44h] [rbp-BCh]
  int v1055; // [rsp+44h] [rbp-BCh]
  unsigned int v1056; // [rsp+44h] [rbp-BCh]
  unsigned int v1057; // [rsp+44h] [rbp-BCh]
  int v1058; // [rsp+44h] [rbp-BCh]
  __int16 v1059; // [rsp+44h] [rbp-BCh]
  _DWORD *v1060; // [rsp+48h] [rbp-B8h]
  char *v1061; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v1062; // [rsp+48h] [rbp-B8h]
  unsigned int v1063; // [rsp+50h] [rbp-B0h]
  unsigned int v1064; // [rsp+50h] [rbp-B0h]
  unsigned int v1065; // [rsp+50h] [rbp-B0h]
  int v1066; // [rsp+50h] [rbp-B0h]
  int v1067; // [rsp+50h] [rbp-B0h]
  int v1068; // [rsp+54h] [rbp-ACh]
  int v1069; // [rsp+54h] [rbp-ACh]
  unsigned int v1070; // [rsp+54h] [rbp-ACh]
  __int16 v1071; // [rsp+54h] [rbp-ACh]
  unsigned int v1072; // [rsp+54h] [rbp-ACh]
  unsigned int v1073; // [rsp+54h] [rbp-ACh]
  unsigned int v1074; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v1075; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v1076; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v1077; // [rsp+58h] [rbp-A8h]
  int v1078; // [rsp+64h] [rbp-9Ch]
  int v1079; // [rsp+64h] [rbp-9Ch]
  int v1080; // [rsp+64h] [rbp-9Ch]
  _DWORD *v1081; // [rsp+68h] [rbp-98h]
  int v1082; // [rsp+68h] [rbp-98h]
  unsigned int v1083; // [rsp+68h] [rbp-98h]
  unsigned int v1084; // [rsp+68h] [rbp-98h]
  unsigned int v1085; // [rsp+68h] [rbp-98h]
  int v1086; // [rsp+68h] [rbp-98h]
  int v1087; // [rsp+68h] [rbp-98h]
  unsigned __int64 v1088; // [rsp+70h] [rbp-90h]
  unsigned __int64 v1089; // [rsp+70h] [rbp-90h]
  unsigned __int64 v1090; // [rsp+70h] [rbp-90h]
  __int64 v1091; // [rsp+78h] [rbp-88h]
  __int64 v1092; // [rsp+78h] [rbp-88h]
  __int16 v1093; // [rsp+78h] [rbp-88h]
  _DWORD *v1094; // [rsp+78h] [rbp-88h]
  _DWORD *v1095; // [rsp+78h] [rbp-88h]
  _DWORD *v1096; // [rsp+78h] [rbp-88h]
  _QWORD *v1097; // [rsp+78h] [rbp-88h]
  __int16 v1098; // [rsp+78h] [rbp-88h]
  _QWORD *v1099; // [rsp+78h] [rbp-88h]
  _QWORD *v1100; // [rsp+80h] [rbp-80h]
  char *v1101; // [rsp+80h] [rbp-80h]
  char *v1102; // [rsp+80h] [rbp-80h]
  _QWORD *v1103; // [rsp+80h] [rbp-80h]
  char *v1104; // [rsp+80h] [rbp-80h]
  char *v1105; // [rsp+80h] [rbp-80h]
  unsigned __int64 v1106; // [rsp+80h] [rbp-80h]
  unsigned int v1107; // [rsp+88h] [rbp-78h]
  int v1108; // [rsp+88h] [rbp-78h]
  unsigned int v1109; // [rsp+88h] [rbp-78h]
  int v1110; // [rsp+88h] [rbp-78h]
  int v1111; // [rsp+88h] [rbp-78h]
  unsigned int v1112; // [rsp+88h] [rbp-78h]
  unsigned int v1113; // [rsp+88h] [rbp-78h]
  unsigned __int64 v1114; // [rsp+90h] [rbp-70h]
  char *v1115; // [rsp+90h] [rbp-70h]
  char *v1116; // [rsp+90h] [rbp-70h]
  char *v1117; // [rsp+90h] [rbp-70h]
  _QWORD *v1118; // [rsp+90h] [rbp-70h]
  char *v1119; // [rsp+98h] [rbp-68h]
  char *v1120; // [rsp+98h] [rbp-68h]
  __int64 v1121; // [rsp+98h] [rbp-68h]
  unsigned int v1122; // [rsp+A0h] [rbp-60h]
  int v1123; // [rsp+A0h] [rbp-60h]
  unsigned int v1124; // [rsp+A0h] [rbp-60h]
  unsigned int v1125; // [rsp+A0h] [rbp-60h]
  unsigned int v1126; // [rsp+A0h] [rbp-60h]
  int v1127; // [rsp+A0h] [rbp-60h]
  unsigned int v1128; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v1129; // [rsp+A0h] [rbp-60h]
  unsigned int v1130; // [rsp+A0h] [rbp-60h]
  unsigned int v1131; // [rsp+A8h] [rbp-58h]
  __int16 v1132; // [rsp+A8h] [rbp-58h]
  unsigned int v1133; // [rsp+A8h] [rbp-58h]
  unsigned int v1134; // [rsp+A8h] [rbp-58h]
  __int16 v1135; // [rsp+A8h] [rbp-58h]
  __int16 v1136; // [rsp+A8h] [rbp-58h]
  unsigned int v1137; // [rsp+A8h] [rbp-58h]
  char *v1138; // [rsp+A8h] [rbp-58h]
  int v1139; // [rsp+A8h] [rbp-58h]
  _QWORD *v1140; // [rsp+B0h] [rbp-50h]
  char *v1141; // [rsp+B0h] [rbp-50h]
  char *v1142; // [rsp+B0h] [rbp-50h]
  char *v1143; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v1144; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v1145; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v1146; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v1147; // [rsp+B8h] [rbp-48h]
  char *v1148; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1149; // [rsp+C0h] [rbp-40h]
  char *v1150; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1151; // [rsp+C0h] [rbp-40h]
  _DWORD *v1152; // [rsp+C0h] [rbp-40h]
  __int64 v1153; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1154; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1155; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1156; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v1157; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v1158; // [rsp+C8h] [rbp-38h]
  int v1159; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v1160; // [rsp+C8h] [rbp-38h]
  __int64 v1161; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v1162; // [rsp+C8h] [rbp-38h]
  __int64 v1163; // [rsp+D0h] [rbp-30h]
  char *v1164; // [rsp+D0h] [rbp-30h]
  __int64 v1165; // [rsp+D0h] [rbp-30h]
  _DWORD *v1166; // [rsp+D8h] [rbp-28h]
  _DWORD *v1167; // [rsp+E0h] [rbp-20h]
  char *v1168; // [rsp+E0h] [rbp-20h]
  char *v1169; // [rsp+E0h] [rbp-20h]
  _DWORD *v1170; // [rsp+E0h] [rbp-20h]
  _QWORD *v1171; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v1172; // [rsp+E0h] [rbp-20h]
  __int64 v1173; // [rsp+E0h] [rbp-20h]
  int v1174; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v1175; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v1176; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v1177; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v1178; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v1179; // [rsp+E8h] [rbp-18h]
  _DWORD *v1180; // [rsp+E8h] [rbp-18h]
  __int64 v1181; // [rsp+F0h] [rbp-10h]
  int v1182; // [rsp+F0h] [rbp-10h]
  __int64 v1183; // [rsp+F0h] [rbp-10h]
  _DWORD *v1184; // [rsp+F8h] [rbp-8h]
  _DWORD *v1185; // [rsp+F8h] [rbp-8h]
  char *v1186; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v1187; // [rsp+F8h] [rbp-8h]
  _DWORD *v1188; // [rsp+F8h] [rbp-8h]
  _DWORD *v1189; // [rsp+F8h] [rbp-8h]
  __int64 v1190; // [rsp+100h] [rbp+0h]
  __int64 v1191; // [rsp+100h] [rbp+0h]
  __int64 v1192; // [rsp+100h] [rbp+0h]
  __int64 v1193; // [rsp+100h] [rbp+0h]
  _DWORD *v1194; // [rsp+108h] [rbp+8h]
  unsigned __int64 v1195; // [rsp+108h] [rbp+8h]
  int v1196; // [rsp+110h] [rbp+10h] BYREF
  int v1197; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v1198; // [rsp+120h] [rbp+20h] BYREF
  int v1199; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v1200; // [rsp+130h] [rbp+30h] BYREF
  int v1201; // [rsp+138h] [rbp+38h] BYREF
  int v1203; // [rsp+198h] [rbp+98h]
  int v1204; // [rsp+1A0h] [rbp+A0h]
  int v1206; // [rsp+1B8h] [rbp+B8h]
  int v1207; // [rsp+1B8h] [rbp+B8h]
  int v1208; // [rsp+1B8h] [rbp+B8h]

  v1204 = a3;
  v1203 = (int)a2;
  v7 = 0;
  v10 = *(_QWORD *)(a1 + 0x40000);
  v12 = v10 + (unsigned int)(*(_DWORD *)(a1 + 262168) - *(_DWORD *)(a1 + 262172)) - *(_QWORD *)(a1 + 262152);
  v13 = a1;
  if ( v12 >= 0x10000 )
  {
    *(_QWORD *)(a1 + 262184) = 0;
    if ( a7 == 2 && a5 < 1 || *a4 > 0x7E000000 )
      return v7;
    v14 = a3;
    v1060 = a2;
    *(_QWORD *)(a1 + 0x40000) = v10 + (int)*a4;
    v15 = a2;
    v16 = (int)*a4;
    v17 = (char *)a2;
    v18 = a3 + a5;
    v1119 = (char *)a2;
    v19 = (char *)a2 + v16;
    v1091 = a3;
    v1148 = (char *)a2 + v16;
    v20 = v18 - 5;
    v1078 = HIDWORD(v1091);
    if ( a7 != 2 )
      v20 = v18;
    *a4 = 0;
    v1088 = v20;
    if ( (int)v16 < 13 )
    {
LABEL_7:
      v21 = v19 - v17;
      v22 = v21;
      if ( a7 != 2 )
      {
        if ( !a7 )
        {
LABEL_9:
          if ( v22 < 0xF )
          {
            LOBYTE(v23) = 16 * v22;
          }
          else
          {
            *(_BYTE *)v14 = -16;
            v23 = v22 - 15;
            ++v14;
            while ( v23 >= 0xFF )
            {
              *(_BYTE *)v14++ = -1;
              v23 -= 255LL;
            }
          }
          *(_BYTE *)v14 = v23;
          memmove((void *)(v14 + 1), v17, v22);
          *a4 = v22 + (_DWORD)v17 - v1203;
          v24 = v22 - v1204 + v14 + 1;
LABEL_13:
          if ( v24 <= 0 )
            goto LABEL_14;
          return (unsigned int)v24;
        }
LABEL_216:
        if ( v14 + (v21 + 240) / 0xFF + v21 + 1 > v20 )
        {
          if ( a7 == 1 )
            goto LABEL_218;
          v22 = v20 - v14 - 1 - ((v20 - v14 - 1 + 241) >> 8);
        }
        goto LABEL_9;
      }
LABEL_215:
      v20 += 5LL;
      goto LABEL_216;
    }
    v36 = (unsigned __int64)(v19 - 12);
    v1075 = 0;
    v1114 = (unsigned __int64)(v19 - 12);
    v1046 = (unsigned __int64)(v19 - 5);
    v1145 = 0;
    while ( 1 )
    {
      if ( (unsigned __int64)v15 > v36 )
      {
        v19 = v1148;
        goto LABEL_7;
      }
      v37 = *v15;
      v1206 = 3;
      v38 = *(_DWORD *)(a1 + 262168);
      v39 = *(unsigned int *)(a1 + 262172);
      v40 = v38;
      v41 = *(_QWORD **)(a1 + 262152);
      v42 = v39;
      v43 = *(_QWORD **)(a1 + 262160);
      v44 = v38 + (_DWORD)v15 - (_DWORD)v41;
      v1107 = v38;
      v1140 = v41;
      v1021 = v44;
      v45 = v38;
      v1122 = *(_DWORD *)(a1 + 262172);
      v1100 = v43;
      if ( (int)v39 + 0x10000 <= v44 )
        v42 = v44 - 0xFFFF;
      v46 = 256;
      v1131 = v42;
      v1156 = 0;
      v1030 = 0;
      v1167 = (_DWORD *)((char *)v43 + v45 - v39);
      v1068 = 256;
      v47 = *(_DWORD *)(a1 + 262176);
      if ( v47 < v44 )
      {
        do
        {
          v996 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v41 + v47 - v40)) >> 17;
          v997 = v47 - *(_DWORD *)(a1 + 4 * v996);
          if ( v997 > 0xFFFF )
            LOWORD(v997) = -1;
          *(_WORD *)(a1 + 2LL * (unsigned __int16)v47 + 0x20000) = v997;
          *(_DWORD *)(a1 + 4 * v996) = v47++;
        }
        while ( v47 < v44 );
        LODWORD(v39) = v1122;
        v46 = 256;
      }
      v48 = v1060;
      *(_DWORD *)(a1 + 262176) = v44;
      v49 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v1060) >> 17));
      if ( v49 >= v42 )
      {
        while ( 1 )
        {
          if ( v46 <= 0 )
          {
LABEL_116:
            v14 = v1091;
            v17 = v1119;
            break;
          }
          if ( v49 < v1107 )
          {
            if ( v49 <= v1107 - 4 && *(_DWORD *)((char *)v43 + v49 - (unsigned int)v39) == v37 )
            {
              v58 = (__int64)v43 + 4;
              v59 = v1060 + 1;
              v60 = (_QWORD *)((char *)v48 + v1107 - v49);
              if ( (unsigned __int64)v60 > v1046 )
                v60 = (_QWORD *)v1046;
              v61 = (_QWORD *)(v49 - (unsigned int)v39 + v58);
              v62 = v1060 + 1;
              if ( v59 >= (_QWORD *)((char *)v60 - 7) )
              {
                while ( v62 < (_QWORD *)((char *)v60 - 7) )
                {
                  if ( *v62 != *v61 )
                  {
                    __asm { tzcnt   r10, rax }
                    v64 = (_DWORD)v62 + ((unsigned int)_R10 >> 3) - (_DWORD)v59;
                    goto LABEL_64;
                  }
                  ++v62;
LABEL_52:
                  ++v61;
                }
                if ( v62 < (_QWORD *)((char *)v60 - 3) && *(_DWORD *)v61 == *(_DWORD *)v62 )
                {
                  v62 = (_QWORD *)((char *)v62 + 4);
                  v61 = (_QWORD *)((char *)v61 + 4);
                }
                if ( v62 < (_QWORD *)((char *)v60 - 1) && *(_WORD *)v61 == *(_WORD *)v62 )
                {
                  v62 = (_QWORD *)((char *)v62 + 2);
                  v61 = (_QWORD *)((char *)v61 + 2);
                }
                if ( v62 < v60 && *(_BYTE *)v61 == *(_BYTE *)v62 )
                  LODWORD(v62) = (_DWORD)v62 + 1;
                v64 = (_DWORD)v62 - (_DWORD)v59;
              }
              else
              {
                if ( *v59 == *v61 )
                {
                  v62 = v1060 + 3;
                  goto LABEL_52;
                }
                __asm { tzcnt   r10, rax }
                v64 = (unsigned int)_R10 >> 3;
              }
LABEL_64:
              v65 = v64 + 4;
              v66 = (_QWORD *)((char *)v1060 + v64 + 4);
              if ( v66 == v60 && (unsigned __int64)v60 < v1046 )
              {
                v67 = (_QWORD *)((char *)v1060 + v64 + 4);
                if ( (unsigned __int64)v66 >= v1046 - 7 )
                {
                  v68 = v41;
                  goto LABEL_68;
                }
                if ( *v66 != *v41 )
                {
                  __asm { tzcnt   rcx, rax }
                  v69 = (unsigned int)_RCX >> 3;
                }
                else
                {
                  v67 = v66 + 1;
                  v68 = v41 + 1;
LABEL_68:
                  while ( (unsigned __int64)v67 < v1046 - 7 )
                  {
                    if ( *v67 != *v68 )
                    {
                      __asm { tzcnt   rax, rax }
                      v69 = ((unsigned int)_RAX >> 3) - (_DWORD)v66 + (_DWORD)v67;
                      goto LABEL_79;
                    }
                    ++v67;
                    ++v68;
                  }
                  if ( (unsigned __int64)v67 < v1046 - 3 && *(_DWORD *)v68 == *(_DWORD *)v67 )
                  {
                    v67 = (_QWORD *)((char *)v67 + 4);
                    v68 = (_QWORD *)((char *)v68 + 4);
                  }
                  if ( (unsigned __int64)v67 < v1046 - 1 && *(_WORD *)v68 == *(_WORD *)v67 )
                  {
                    v67 = (_QWORD *)((char *)v67 + 2);
                    v68 = (_QWORD *)((char *)v68 + 2);
                  }
                  if ( (unsigned __int64)v67 < v1046 && *(_BYTE *)v68 == *(_BYTE *)v67 )
                    LODWORD(v67) = (_DWORD)v67 + 1;
                  v69 = (_DWORD)v67 - (_DWORD)v66;
                }
LABEL_79:
                v65 = v64 + v69 + 4;
              }
              if ( v65 > v1206 )
              {
                v1206 = v65;
                v1030 = v44 - v49;
              }
            }
          }
          else
          {
            v50 = v49 - v1107;
            if ( *(_WORD *)((char *)v1060 + v1206 - 1) == *(_WORD *)((char *)v41 + v1206 + v50 - 1)
              && *(_DWORD *)((char *)v41 + v50) == v37 )
            {
              v51 = v50 + 4;
              v52 = v1060 + 1;
              v53 = (_QWORD *)((char *)v41 + v51);
              v54 = v1060 + 1;
              if ( (unsigned __int64)(v1060 + 1) >= v1046 - 7 )
              {
                while ( (unsigned __int64)v54 < v1046 - 7 )
                {
                  if ( *v53 != *v54 )
                  {
                    __asm { tzcnt   rax, rax }
                    v57 = ((unsigned int)_RAX >> 3) - (_DWORD)v52 + (_DWORD)v54;
                    goto LABEL_92;
                  }
                  ++v54;
LABEL_238:
                  ++v53;
                }
                if ( (unsigned __int64)v54 < v1046 - 3 && *(_DWORD *)v53 == *(_DWORD *)v54 )
                {
                  v54 = (_QWORD *)((char *)v54 + 4);
                  v53 = (_QWORD *)((char *)v53 + 4);
                }
                if ( (unsigned __int64)v54 < v1046 - 1 && *(_WORD *)v53 == *(_WORD *)v54 )
                {
                  v54 = (_QWORD *)((char *)v54 + 2);
                  v53 = (_QWORD *)((char *)v53 + 2);
                }
                if ( (unsigned __int64)v54 < v1046 && *(_BYTE *)v53 == *(_BYTE *)v54 )
                  LODWORD(v54) = (_DWORD)v54 + 1;
                v57 = (_DWORD)v54 - (_DWORD)v52;
              }
              else
              {
                if ( *v53 == *v52 )
                {
                  v54 = v1060 + 3;
                  goto LABEL_238;
                }
                __asm { tzcnt   rcx, rax }
                v57 = (unsigned int)_RCX >> 3;
              }
LABEL_92:
              v70 = v57 + 4;
              if ( v70 > v1206 )
              {
                v1206 = v70;
                v1030 = v44 - v49;
              }
            }
          }
          v71 = a1;
          if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v49 + 0x20000) != 1 )
            goto LABEL_149;
          if ( v7 )
          {
            v1052 = v7;
            if ( v7 != 2 )
              goto LABEL_149;
          }
          else
          {
            if ( (_BYTE)v37 != HIBYTE(v37) || (unsigned __int16)v37 != HIWORD(v37) )
            {
              v7 = 1;
LABEL_149:
              v49 -= *(unsigned __int16 *)(v71 + 2LL * (unsigned __int16)v49 + 0x20000);
              goto LABEL_115;
            }
            v7 = 2;
            v1052 = 2;
            v72 = LZ4HC_countPattern(v1060 + 1, v1046, v37, 1);
            v71 = a1;
            v1156 = v72 + 4LL;
          }
          v73 = v49 - 1;
          if ( v49 - 1 < v42 || v1107 - v49 < 3 )
            goto LABEL_149;
          if ( v73 < v1107 )
          {
            v74 = 1;
            v75 = (_DWORD *)((char *)v1100 + v73 - v1122);
          }
          else
          {
            v74 = 0;
            v75 = (_DWORD *)((char *)v41 + v73 - v1107);
          }
          if ( *v75 != v37 )
          {
            v42 = v1131;
            goto LABEL_149;
          }
          v76 = (_DWORD *)v1046;
          if ( v74 )
            v76 = v1167;
          v77 = (unsigned int)LZ4HC_countPattern(v75 + 1, v76, v37, 1) + 4LL;
          if ( v74 )
          {
            if ( (_DWORD *)((char *)v75 + v77) == v76 )
            {
              v984 = v37;
              v985 = v77 & 3;
              if ( 8 * v985 )
                v984 = (unsigned int)__ROL4__(v37, 8 * v985);
              v41 = v1140;
              v77 += (unsigned int)LZ4HC_countPattern(v1140, v1046, v984, v78);
            }
            else
            {
              v41 = v1140;
            }
            v79 = v1100;
          }
          else
          {
            v41 = v1140;
            v79 = v1140;
          }
          v80 = LZ4HC_reverseCountPattern(v75, v79, v37);
          v82 = v80;
          if ( !v74 && (_QWORD *)((char *)v75 - v80) == v41 && v1122 < v1107 )
          {
            if ( 8LL * (-v80 & 3) )
              v81 = (unsigned int)__ROL4__(v81, 8 * (-(char)v80 & 3));
            v119 = LZ4HC_reverseCountPattern(v1167, v1100, v81);
            v82 = v119 + v120;
          }
          v42 = v1131;
          v83 = v73 - v82;
          v84 = v1131;
          if ( v83 > v1131 )
            v84 = v83;
          v85 = v77 + v73 - v84;
          if ( v85 < v1156 || v77 > v1156 )
          {
            if ( v1107 - v84 - 1 >= 3 )
            {
              v48 = v1060;
              v117 = v1156;
              if ( v85 < v1156 )
                v117 = v77 + v73 - v84;
              if ( v1206 < v117 )
              {
                if ( (unsigned __int64)v1060 + v1107 - (unsigned __int64)v84 - (_QWORD)v41 > 0xFFFF )
                  goto LABEL_116;
                v1206 = v117;
                v1030 = v1021 - v84;
              }
              v118 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v84 + 0x20000);
              if ( v118 > v84 )
                goto LABEL_116;
              v49 = v84 - v118;
            }
            else
            {
              v49 = v1107;
            }
          }
          else
          {
            v49 = v1107;
            if ( v1107 - ((_DWORD)v77 - (_DWORD)v1156 + v73) - 1 >= 3 )
              v49 = v77 - v1156 + v73;
          }
          v7 = v1052;
LABEL_115:
          v44 = v1021;
          v46 = v1068 - 1;
          v43 = v1100;
          LODWORD(v39) = v1122;
          v48 = v1060;
          --v1068;
          if ( v49 < v42 )
            goto LABEL_116;
        }
      }
      v86 = v1206;
      if ( v1206 < 4 )
      {
        v20 = v1088;
        v15 = (_DWORD *)((char *)v48 + 1);
        v1060 = v15;
LABEL_236:
        v36 = v1114;
        v7 = 0;
        continue;
      }
      v87 = v1030;
      v88 = v48;
      v89 = __PAIR64__(v1206, v1030) >> 32;
LABEL_119:
      v90 = v1114;
      v1174 = v89;
      v1081 = v88;
      v1093 = v87;
      while ( 1 )
      {
        v91 = v86;
        v1190 = v86;
        v92 = (_DWORD *)((char *)v48 + v86);
        v1184 = v92;
        if ( (unsigned __int64)v92 > v90 )
        {
          v93 = 0;
          v1048 = 0;
          v94 = 0;
          v1033 = 0;
          goto LABEL_122;
        }
        v1033 = v86;
        v179 = (_DWORD *)((char *)v92 - 2);
        v1075 = (unsigned __int64)v179;
        v1166 = (_DWORD *)((char *)v92 - 2);
        v180 = *(_DWORD *)(a1 + 262172);
        v181 = v180;
        v182 = (char *)*(unsigned int *)(a1 + 262168);
        v183 = *(_QWORD **)(a1 + 262152);
        v184 = *(char **)(a1 + 262160);
        v185 = *(_DWORD *)(a1 + 262176);
        v186 = *v179;
        v187 = (_DWORD)v179 + *(_DWORD *)(a1 + 262168) - (_DWORD)v183;
        v1101 = (char *)v183;
        v1022 = *(_DWORD *)(a1 + 262168);
        v1132 = v187;
        v1053 = v180;
        if ( v180 + 0x10000 <= v187 )
          v181 = v187 - 0xFFFF;
        v1141 = *(char **)(a1 + 262160);
        v1037 = v181;
        v1063 = *v179;
        v1048 = 0;
        if ( v185 < v187 )
        {
          do
          {
            v998 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v183 + v185 - (_QWORD)v182)) >> 17;
            v999 = v185 - *(_DWORD *)(a1 + 4 * v998);
            if ( v999 > 0xFFFF )
              LOWORD(v999) = -1;
            *(_WORD *)(a1 + 2LL * (unsigned __int16)v185 + 0x20000) = v999;
            *(_DWORD *)(a1 + 4 * v998) = v185++;
          }
          while ( v185 < v187 );
          v87 = v1093;
          v184 = v1141;
        }
        *(_DWORD *)(a1 + 262176) = v187;
        v188 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v179) >> 17));
        if ( v188 >= v181 )
        {
          v189 = 256;
          v1168 = &v182[(_QWORD)v184 - v180];
          v190 = (_DWORD)v179 - (_DWORD)v1060;
          v1069 = 256;
          v1123 = (_DWORD)v179 - (_DWORD)v1060;
          v191 = 0;
          v1016 = 0;
          v1157 = 0;
          do
          {
            if ( v189 <= 0 )
              break;
            if ( v188 < (unsigned int)v182 )
            {
              if ( v188 > (int)v182 - 4 )
                goto LABEL_2025;
              v241 = &v184[v188 - v180];
              if ( *(_DWORD *)v241 != v186 )
              {
                v191 = v1016;
LABEL_2025:
                v223 = v1046;
                goto LABEL_424;
              }
              v242 = v179 + 1;
              v243 = (_QWORD *)((char *)v179 + (unsigned int)v182 - v188);
              v244 = v241 + 4;
              v245 = v179 + 1;
              if ( (unsigned __int64)v243 > v1046 )
                v243 = (_QWORD *)v1046;
              if ( v242 >= (_QWORD *)((char *)v243 - 7) )
              {
                while ( v245 < (_QWORD *)((char *)v243 - 7) )
                {
                  if ( *v244 != *v245 )
                  {
                    __asm { tzcnt   rsi, rax }
                    v248 = (_DWORD)v245 + ((unsigned int)_RSI >> 3) - (_DWORD)v242;
                    goto LABEL_511;
                  }
                  ++v245;
LABEL_499:
                  ++v244;
                }
                if ( v245 < (_QWORD *)((char *)v243 - 3) && *(_DWORD *)v244 == *(_DWORD *)v245 )
                {
                  v245 = (_QWORD *)((char *)v245 + 4);
                  v244 = (_QWORD *)((char *)v244 + 4);
                }
                if ( v245 < (_QWORD *)((char *)v243 - 1) && *(_WORD *)v244 == *(_WORD *)v245 )
                {
                  v245 = (_QWORD *)((char *)v245 + 2);
                  v244 = (_QWORD *)((char *)v244 + 2);
                }
                if ( v245 < v243 && *(_BYTE *)v244 == *(_BYTE *)v245 )
                  LODWORD(v245) = (_DWORD)v245 + 1;
                v248 = (_DWORD)v245 - (_DWORD)v242;
              }
              else
              {
                if ( *v244 == *v242 )
                {
                  v245 = v179 + 3;
                  goto LABEL_499;
                }
                __asm { tzcnt   rsi, rax }
                v248 = (unsigned int)_RSI >> 3;
              }
LABEL_511:
              v271 = v248 + 4;
              v313 = (_QWORD *)((char *)v179 + v248 + 4);
              if ( v313 == v243 && (unsigned __int64)v243 < v1046 )
              {
                v268 = (_QWORD *)((char *)v179 + v248 + 4);
                if ( (unsigned __int64)v313 >= v1046 - 7 )
                {
                  v269 = v183;
                  goto LABEL_515;
                }
                if ( *v183 != *v313 )
                {
                  __asm { tzcnt   rcx, rax }
                  v270 = (unsigned int)_RCX >> 3;
                }
                else
                {
                  v268 = v313 + 1;
                  v269 = v183 + 1;
LABEL_515:
                  while ( (unsigned __int64)v268 < v1046 - 7 )
                  {
                    if ( *v269 != *v268 )
                    {
                      __asm { tzcnt   rax, rax }
                      v270 = ((unsigned int)_RAX >> 3) - (_DWORD)v313 + (_DWORD)v268;
                      goto LABEL_415;
                    }
                    ++v268;
                    ++v269;
                  }
                  if ( (unsigned __int64)v268 < v1046 - 3 && *(_DWORD *)v269 == *(_DWORD *)v268 )
                  {
                    v268 = (_QWORD *)((char *)v268 + 4);
                    v269 = (_QWORD *)((char *)v269 + 4);
                  }
                  if ( (unsigned __int64)v268 < v1046 - 1 && *(_WORD *)v269 == *(_WORD *)v268 )
                  {
                    v268 = (_QWORD *)((char *)v268 + 2);
                    v269 = (_QWORD *)((char *)v269 + 2);
                  }
                  if ( (unsigned __int64)v268 < v1046 && *(_BYTE *)v269 == *(_BYTE *)v268 )
                    LODWORD(v268) = (_DWORD)v268 + 1;
                  v270 = (_DWORD)v268 - (_DWORD)v313;
                }
LABEL_415:
                v271 = v248 + v270 + 4;
              }
              v272 = 0;
              if ( v1123 )
              {
                v273 = (_DWORD)v1060 - (_DWORD)v179;
                if ( (char *)v1060 - (char *)v179 <= v1141 - v241 )
                  v273 = (_DWORD)v1141 - (_DWORD)v241;
                while ( v272 - v273 > 3 )
                {
                  if ( *(_DWORD *)&v241[v272 - 4] != *(_DWORD *)((char *)v179 + v272 - 4) )
                  {
                    _BitScanReverse(&v274, *(_DWORD *)&v241[v272 - 4] ^ *(_DWORD *)((char *)v179 + v272 - 4));
                    v272 -= (31 - v274) >> 3;
                    goto LABEL_422;
                  }
                  v272 -= 4;
                }
                if ( v272 > v273 )
                {
                  do
                  {
                    if ( *((_BYTE *)v179 + v272 - 1) != v241[v272 - 1] )
                      break;
                    --v272;
                  }
                  while ( v272 > v273 );
                  v87 = v1093;
                }
              }
LABEL_422:
              LODWORD(v182) = v1022;
              v275 = v271 - v272;
              v186 = v1063;
              v191 = v1016;
              v223 = v1046;
              if ( v275 > v1033 )
              {
                v1033 = v275;
                v1048 = v1132 - v188;
                v1075 = (unsigned __int64)v179 + v272;
              }
            }
            else
            {
              v217 = (_DWORD *)((char *)v183 + v188 - (unsigned int)v182);
              if ( *(_WORD *)((char *)v1060 + v1033 - 1) == *(_WORD *)((char *)v217 + v1033 - (__int64)v190 - 1)
                && *v217 == v186 )
              {
                v218 = v190 == 0;
                v219 = 0;
                if ( !v218 )
                {
                  v220 = (_DWORD)v1060 - (_DWORD)v179;
                  v221 = -(__int64)(v188 - (unsigned int)v182);
                  if ( (char *)v1060 - (char *)v179 <= v221 )
                    v220 = v221;
                  while ( v219 - v220 > 3 )
                  {
                    if ( *(_DWORD *)((char *)v179 + v219 - 4) != *(_DWORD *)((char *)v217 + v219 - 4) )
                    {
                      _BitScanReverse(
                        &v222,
                        *(_DWORD *)((char *)v179 + v219 - 4) ^ *(_DWORD *)((char *)v217 + v219 - 4));
                      v219 -= (31 - v222) >> 3;
                      goto LABEL_329;
                    }
                    v219 -= 4;
                  }
                  if ( v219 > v220 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v179 + v219 - 1) != *((_BYTE *)v217 + v219 - 1) )
                        break;
                      --v219;
                    }
                    while ( v219 > v220 );
                    v87 = v1093;
                  }
                }
LABEL_329:
                v223 = v1046;
                v224 = v179 + 1;
                v225 = v217 + 1;
                v226 = v179 + 1;
                if ( (unsigned __int64)(v179 + 1) >= v1046 - 7 )
                {
                  while ( (unsigned __int64)v226 < v1046 - 7 )
                  {
                    if ( *v225 != *v226 )
                    {
                      __asm { tzcnt   rax, rax }
                      v229 = ((unsigned int)_RAX >> 3) - (_DWORD)v224 + (_DWORD)v226;
                      goto LABEL_495;
                    }
                    ++v226;
LABEL_483:
                    ++v225;
                  }
                  if ( (unsigned __int64)v226 < v1046 - 3 && *(_DWORD *)v225 == *(_DWORD *)v226 )
                  {
                    v226 = (_QWORD *)((char *)v226 + 4);
                    v225 = (_QWORD *)((char *)v225 + 4);
                  }
                  if ( (unsigned __int64)v226 < v1046 - 1 && *(_WORD *)v225 == *(_WORD *)v226 )
                  {
                    v226 = (_QWORD *)((char *)v226 + 2);
                    v225 = (_QWORD *)((char *)v225 + 2);
                  }
                  if ( (unsigned __int64)v226 < v1046 && *(_BYTE *)v225 == *(_BYTE *)v226 )
                    LODWORD(v226) = (_DWORD)v226 + 1;
                  v229 = (_DWORD)v226 - (_DWORD)v224;
                }
                else
                {
                  if ( *v225 == *v224 )
                  {
                    v226 = v179 + 3;
                    goto LABEL_483;
                  }
                  __asm { tzcnt   rcx, rax }
                  v229 = (unsigned int)_RCX >> 3;
                }
LABEL_495:
                v312 = v229 - v219 + 4;
                if ( v312 > v1033 )
                {
                  v1033 = v312;
                  v1048 = v1132 - v188;
                  v1075 = (unsigned __int64)v179 + v219;
                }
              }
              else
              {
                v223 = v1046;
              }
            }
LABEL_424:
            if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v188 + 0x20000) != 1 )
              goto LABEL_453;
            if ( v191 )
            {
              v1016 = v191;
              if ( v191 != 2 )
                goto LABEL_453;
            }
            else
            {
              if ( (_BYTE)v186 != HIBYTE(v186) || (unsigned __int16)v186 != HIWORD(v186) )
              {
                v191 = 1;
                v1016 = 1;
LABEL_453:
                v276 = v1037;
LABEL_454:
                LODWORD(v182) = v1022;
                v188 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v188 + 0x20000);
                goto LABEL_383;
              }
              v191 = 2;
              v1016 = 2;
              v1157 = (unsigned int)LZ4HC_countPattern(v179 + 1, v223, v186, 0) + 4LL;
            }
            v276 = v1037;
            v277 = v188 - 1;
            if ( v188 - 1 < v1037 || (unsigned int)v182 - v188 < 3 )
              goto LABEL_454;
            if ( v277 < (unsigned int)v182 )
            {
              v278 = 1;
              v182 = &v1141[v277 - v1053];
            }
            else
            {
              v278 = 0;
              v182 = &v1101[v277 - (unsigned int)v182];
            }
            if ( *(_DWORD *)v182 != v186 )
              goto LABEL_454;
            v279 = (char *)v1046;
            if ( v278 )
              v279 = v1168;
            v281 = (unsigned int)LZ4HC_countPattern(v182 + 4, v279, v1063, 0) + 4LL;
            if ( v278 )
            {
              if ( &v182[v281] == v279 )
              {
                v986 = v1063;
                v987 = v281 & 3;
                if ( 8 * v987 )
                  v986 = (unsigned int)__ROL4__(v1063, 8 * v987);
                v281 += (unsigned int)LZ4HC_countPattern(v1101, v1046, v986, v280);
              }
              v282 = v1141;
            }
            else
            {
              v282 = v1101;
            }
            v283 = LZ4HC_reverseCountPattern(v182, v282, v1063);
            v284 = v1101;
            v285 = v283;
            if ( v278 )
            {
              LODWORD(v182) = v1022;
            }
            else
            {
              v218 = &v182[-v283] == v1101;
              LODWORD(v182) = v1022;
              if ( v218 && v1053 < v1022 )
              {
                v289 = v1063;
                if ( 8LL * (-v283 & 3) )
                  v289 = (unsigned int)__ROL4__(v1063, 8 * (-(char)v283 & 3));
                v285 = LZ4HC_reverseCountPattern(v1168, v1141, v289) + v283;
                v284 = v1101;
              }
            }
            v276 = v1037;
            v188 = v1037;
            if ( v277 - v285 > v1037 )
              v188 = v277 - v285;
            v286 = v281 + v277 - v188;
            if ( v286 < v1157 || v281 > v1157 )
            {
              if ( (unsigned int)v182 - v188 - 1 < 3 )
              {
                v188 = (unsigned int)v182;
              }
              else if ( !v1123 )
              {
                v287 = v1157;
                if ( v286 < v1157 )
                  v287 = v281 + v277 - v188;
                if ( v1033 < v287 )
                {
                  if ( (unsigned __int64)v1166 + (unsigned int)v182 - (unsigned __int64)v188 - (_QWORD)v284 > 0xFFFF )
                    break;
                  v1033 = v287;
                  v1048 = v1132 - v188;
                  v1075 = (unsigned __int64)v1166;
                }
                v288 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v188 + 0x20000);
                if ( v288 > v188 )
                  break;
                v188 -= v288;
              }
            }
            else
            {
              v188 = (unsigned int)v182;
              if ( (unsigned int)v182 - ((_DWORD)v281 - (_DWORD)v1157 + v277) - 1 >= 3 )
                v188 = v281 - v1157 + v277;
            }
            v191 = v1016;
LABEL_383:
            v179 = v1166;
            v189 = v1069 - 1;
            v186 = v1063;
            v266 = v188 < v276;
            v180 = v1053;
            v183 = v1101;
            v190 = v1123;
            v184 = v1141;
            --v1069;
          }
          while ( !v266 );
        }
        LODWORD(v89) = v1174;
        v88 = v1081;
        v92 = v1184;
        v91 = v1190;
        v94 = v1033;
        v48 = v1060;
        v86 = v1206;
        v93 = v1048;
        v90 = v1114;
LABEL_122:
        if ( v94 <= v86 )
        {
          v17 = v1119;
          v157 = (_BYTE *)(v14 + 1);
          v104 = v14 >> 32;
          v158 = (char *)v48 - v1119;
          v106 = v14;
          v20 = v1088;
          v159 = (char *)v14;
          if ( a7 && (unsigned __int64)&v157[v158 / 0xFF + 8 + v158] > v1088 )
            goto LABEL_304;
          if ( v158 < 0xF )
          {
            *(_BYTE *)v14 = 16 * v158;
          }
          else
          {
            v160 = v158 - 15;
            *(_BYTE *)v14 = -16;
            while ( v160 >= 0xFF )
            {
              *v157++ = -1;
              v160 -= 255LL;
            }
            *v157++ = v160;
          }
          v161 = (__int64 *)v1119;
          v162 = &v157[v158];
          do
          {
            v163 = *v161++;
            *(_QWORD *)v157 = v163;
            v157 += 8;
          }
          while ( v157 < (_BYTE *)v162 );
          v164 = v91 - 4;
          *v162 = v1030;
          v14 = (__int64)(v162 + 1);
          v1091 = v14;
          v1078 = HIDWORD(v14);
          if ( a7 )
          {
            if ( v14 + v164 / 0xFF + 6 > v1088 )
              goto LABEL_304;
          }
          v165 = *v159;
          if ( v164 < 0xF )
          {
            *v159 = v165 + v164;
          }
          else
          {
            *v159 = v165 + 15;
            for ( i = v91 - 19; i >= 0x1FE; i -= 510LL )
            {
              *(_BYTE *)v14 = -1;
              v249 = (_BYTE *)(v14 + 1);
              *v249 = -1;
              v14 = (__int64)(v249 + 1);
            }
            if ( i >= 0xFF )
            {
              LOBYTE(i) = i + 1;
              *(_BYTE *)v14++ = -1;
            }
            *(_BYTE *)v14++ = i;
            v1091 = v14;
            v1078 = HIDWORD(v14);
          }
          v15 = v92;
          v1060 = v92;
          v17 = (char *)v92;
          v1119 = (char *)v92;
          goto LABEL_236;
        }
        v95 = v1075;
        if ( v88 < v48 && v1075 < (unsigned __int64)v48 + (int)v89 )
        {
          v48 = v88;
          v1060 = v88;
          LOWORD(v1030) = v87;
          v86 = v89;
          v1206 = v89;
        }
        if ( (__int64)(v1075 - (_QWORD)v48) >= 3 )
          break;
        v48 = (_DWORD *)v1075;
        v1060 = (_DWORD *)v1075;
        LOWORD(v1030) = v93;
        v86 = v94;
        v1206 = v94;
      }
      while ( 2 )
      {
        if ( (__int64)(v95 - (_QWORD)v48) < 18 )
        {
          v175 = v86;
          if ( v86 > 18 )
            v175 = 18;
          if ( (unsigned __int64)v48 + v175 > v95 + v94 - 4LL )
            v175 = v94 + v95 - (_DWORD)v48 - 4;
          v176 = v175 + (_DWORD)v48 - v95;
          if ( v176 > 0 )
          {
            v95 += v176;
            v94 -= v176;
            v1075 = v95;
            v1033 = v94;
          }
        }
        v96 = v94;
        v1191 = v94;
        v97 = (_DWORD *)(v94 + v95);
        v1185 = v97;
        if ( (unsigned __int64)v97 > v90 )
        {
          v98 = 0;
          v99 = 0;
          goto LABEL_128;
        }
        v1082 = v94;
        v192 = (_DWORD *)((char *)v97 - 3);
        v1145 = (unsigned __int64)v97 - 3;
        v1094 = (_DWORD *)((char *)v97 - 3);
        v193 = *(_DWORD *)(a1 + 262168);
        v194 = *(_QWORD **)(a1 + 262152);
        v195 = *(unsigned int *)(a1 + 262172);
        v196 = *(_DWORD *)(a1 + 262176);
        v197 = *(_DWORD *)((char *)v97 - 3);
        v198 = v195;
        v1133 = v193 + (_DWORD)v97 - 3 - (_DWORD)v194;
        v1102 = (char *)v194;
        v1023 = v193;
        v1124 = *(_DWORD *)(a1 + 262172);
        v199 = *(char **)(a1 + 262160);
        if ( (int)v195 + 0x10000 <= v1133 )
          v198 = v1133 - 0xFFFF;
        v1070 = v198;
        v1142 = *(char **)(a1 + 262160);
        v200 = v193 + (_DWORD)v97 - 3 - (_DWORD)v194;
        v1064 = *(_DWORD *)((char *)v97 - 3);
        v1054 = 0;
        if ( v196 < v200 )
        {
          do
          {
            v1000 = (unsigned __int64)(unsigned int)(-1640531535
                                                   * *(_DWORD *)((char *)v194 + v196 - (unsigned __int64)v193)) >> 17;
            v1001 = v196 - *(_DWORD *)(a1 + 4 * v1000);
            if ( v1001 > 0xFFFF )
              LOWORD(v1001) = -1;
            *(_WORD *)(a1 + 2LL * (unsigned __int16)v196 + 0x20000) = v1001;
            *(_DWORD *)(a1 + 4 * v1000) = v196++;
          }
          while ( v196 < v200 );
          v199 = v1142;
        }
        *(_DWORD *)(a1 + 262176) = v200;
        v201 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v192) >> 17));
        if ( v201 >= v198 )
        {
          v202 = 256;
          v1108 = 256;
          v1169 = &v199[v193 - v195];
          v203 = (_DWORD)v192 - v1075;
          v204 = 0;
          v1038 = (_DWORD)v192 - v1075;
          v205 = 0;
          v1017 = 0;
          v1158 = 0;
          while ( 1 )
          {
            if ( v202 <= 0 )
              goto LABEL_404;
            if ( v201 < v193 )
            {
              if ( v201 > v193 - 4 )
                goto LABEL_2032;
              v250 = &v199[v201 - (unsigned int)v195];
              if ( *(_DWORD *)v250 != v197 )
              {
                v205 = v1017;
LABEL_2032:
                v234 = v1046;
                goto LABEL_553;
              }
              v251 = v192 + 1;
              v252 = (_QWORD *)((char *)v192 + v193 - v201);
              v253 = v250 + 4;
              v254 = v192 + 1;
              if ( (unsigned __int64)v252 > v1046 )
                v252 = (_QWORD *)v1046;
              if ( v251 >= (_QWORD *)((char *)v252 - 7) )
              {
                while ( v254 < (_QWORD *)((char *)v252 - 7) )
                {
                  if ( *v253 != *v254 )
                  {
                    __asm { tzcnt   rdi, rax }
                    v257 = (_DWORD)v254 + ((unsigned int)_RDI >> 3) - (_DWORD)v251;
                    goto LABEL_609;
                  }
                  ++v254;
LABEL_597:
                  ++v253;
                }
                if ( v254 < (_QWORD *)((char *)v252 - 3) && *(_DWORD *)v253 == *(_DWORD *)v254 )
                {
                  v254 = (_QWORD *)((char *)v254 + 4);
                  v253 = (_QWORD *)((char *)v253 + 4);
                }
                if ( v254 < (_QWORD *)((char *)v252 - 1) && *(_WORD *)v253 == *(_WORD *)v254 )
                {
                  v254 = (_QWORD *)((char *)v254 + 2);
                  v253 = (_QWORD *)((char *)v253 + 2);
                }
                if ( v254 < v252 && *(_BYTE *)v253 == *(_BYTE *)v254 )
                  LODWORD(v254) = (_DWORD)v254 + 1;
                v257 = (_DWORD)v254 - (_DWORD)v251;
              }
              else
              {
                if ( *v251 == *v253 )
                {
                  v254 = v192 + 3;
                  goto LABEL_597;
                }
                __asm { tzcnt   rdi, rax }
                v257 = (unsigned int)_RDI >> 3;
              }
LABEL_609:
              v319 = v257 + 4;
              v345 = (_QWORD *)((char *)v192 + v257 + 4);
              if ( v345 == v252 && (unsigned __int64)v252 < v1046 )
              {
                v316 = (_QWORD *)((char *)v192 + v257 + 4);
                if ( (unsigned __int64)v345 >= v1046 - 7 )
                {
                  v317 = v194;
                  goto LABEL_613;
                }
                if ( *v194 != *v345 )
                {
                  __asm { tzcnt   rcx, rax }
                  v318 = (unsigned int)_RCX >> 3;
                }
                else
                {
                  v316 = v345 + 1;
                  v317 = v194 + 1;
LABEL_613:
                  while ( (unsigned __int64)v316 < v1046 - 7 )
                  {
                    if ( *v317 != *v316 )
                    {
                      __asm { tzcnt   rax, rax }
                      v318 = ((unsigned int)_RAX >> 3) - (_DWORD)v345 + (_DWORD)v316;
                      goto LABEL_544;
                    }
                    ++v316;
                    ++v317;
                  }
                  if ( (unsigned __int64)v316 < v1046 - 3 && *(_DWORD *)v317 == *(_DWORD *)v316 )
                  {
                    v316 = (_QWORD *)((char *)v316 + 4);
                    v317 = (_QWORD *)((char *)v317 + 4);
                  }
                  if ( (unsigned __int64)v316 < v1046 - 1 && *(_WORD *)v317 == *(_WORD *)v316 )
                  {
                    v316 = (_QWORD *)((char *)v316 + 2);
                    v317 = (_QWORD *)((char *)v317 + 2);
                  }
                  if ( (unsigned __int64)v316 < v1046 && *(_BYTE *)v317 == *(_BYTE *)v316 )
                    LODWORD(v316) = (_DWORD)v316 + 1;
                  v318 = (_DWORD)v316 - (_DWORD)v345;
                }
LABEL_544:
                v319 = v257 + v318 + 4;
              }
              v320 = 0;
              if ( v203 )
              {
                v321 = v1075 - (_DWORD)v192;
                if ( (__int64)(v1075 - (_QWORD)v192) <= v1142 - v250 )
                  v321 = (_DWORD)v1142 - (_DWORD)v250;
                while ( v320 - v321 > 3 )
                {
                  if ( *(_DWORD *)&v250[v320 - 4] != *(_DWORD *)((char *)v192 + v320 - 4) )
                  {
                    _BitScanReverse(&v322, *(_DWORD *)&v250[v320 - 4] ^ *(_DWORD *)((char *)v192 + v320 - 4));
                    v320 -= (31 - v322) >> 3;
                    goto LABEL_551;
                  }
                  v320 -= 4;
                }
                if ( v320 > v321 )
                {
                  do
                  {
                    if ( *((_BYTE *)v192 + v320 - 1) != v250[v320 - 1] )
                      break;
                    --v320;
                  }
                  while ( v320 > v321 );
                  v203 = v1038;
                }
              }
LABEL_551:
              v193 = v1023;
              v323 = v319 - v320;
              v197 = v1064;
              v205 = v1017;
              v234 = v1046;
              if ( v323 > v1082 )
              {
                v1082 = v323;
                v1054 = v1133 - v201;
                v1145 = (unsigned __int64)v192 + v320;
              }
            }
            else
            {
              v230 = (_DWORD *)((char *)v194 + v201 - v193);
              if ( *(_WORD *)(v1082 + v1075 - 1) == *(_WORD *)((char *)v230 + v1082 - (__int64)v203 - 1)
                && *v230 == v197 )
              {
                if ( v203 )
                {
                  v231 = v1075 - (_DWORD)v192;
                  v232 = -(__int64)(v201 - v193);
                  if ( (__int64)(v1075 - (_QWORD)v192) <= v232 )
                    v231 = v232;
                  while ( v204 - v231 > 3 )
                  {
                    if ( *(_DWORD *)((char *)v230 + v204 - 4) != *(_DWORD *)((char *)v192 + v204 - 4) )
                    {
                      _BitScanReverse(
                        &v233,
                        *(_DWORD *)((char *)v230 + v204 - 4) ^ *(_DWORD *)((char *)v192 + v204 - 4));
                      v204 -= (31 - v233) >> 3;
                      goto LABEL_343;
                    }
                    v204 -= 4;
                  }
                  if ( v204 > v231 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v192 + v204 - 1) != *((_BYTE *)v230 + v204 - 1) )
                        break;
                      --v204;
                    }
                    while ( v204 > v231 );
                    v203 = v1038;
                  }
                }
LABEL_343:
                v234 = v1046;
                v235 = v192 + 1;
                v236 = v230 + 1;
                v237 = v192 + 1;
                if ( (unsigned __int64)(v192 + 1) >= v1046 - 7 )
                {
                  while ( (unsigned __int64)v237 < v1046 - 7 )
                  {
                    if ( *v236 != *v237 )
                    {
                      __asm { tzcnt   rax, rax }
                      v240 = ((unsigned int)_RAX >> 3) - (_DWORD)v235 + (_DWORD)v237;
                      goto LABEL_531;
                    }
                    ++v237;
LABEL_519:
                    ++v236;
                  }
                  if ( (unsigned __int64)v237 < v1046 - 3 && *(_DWORD *)v236 == *(_DWORD *)v237 )
                  {
                    v237 = (_QWORD *)((char *)v237 + 4);
                    v236 = (_QWORD *)((char *)v236 + 4);
                  }
                  if ( (unsigned __int64)v237 < v1046 - 1 && *(_WORD *)v236 == *(_WORD *)v237 )
                  {
                    v237 = (_QWORD *)((char *)v237 + 2);
                    v236 = (_QWORD *)((char *)v236 + 2);
                  }
                  if ( (unsigned __int64)v237 < v1046 && *(_BYTE *)v236 == *(_BYTE *)v237 )
                    LODWORD(v237) = (_DWORD)v237 + 1;
                  v240 = (_DWORD)v237 - (_DWORD)v235;
                }
                else
                {
                  if ( *v235 == *v236 )
                  {
                    v237 = v192 + 3;
                    goto LABEL_519;
                  }
                  __asm { tzcnt   rcx, rax }
                  v240 = (unsigned int)_RCX >> 3;
                }
LABEL_531:
                v315 = v240 - v204 + 4;
                if ( v315 > v1082 )
                {
                  v1082 = v315;
                  v1054 = v1133 - v201;
                  v1145 = (unsigned __int64)v192 + v204;
                }
              }
              else
              {
                v234 = v1046;
              }
            }
LABEL_553:
            v324 = a1;
            if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v201 + 0x20000) != 1 )
              goto LABEL_595;
            if ( v205 )
            {
              v1017 = v205;
              if ( v205 != 2 )
                goto LABEL_595;
            }
            else
            {
              if ( (_BYTE)v197 != HIBYTE(v197) || (unsigned __int16)v197 != HIWORD(v197) )
              {
                v205 = 1;
                v1017 = 1;
LABEL_595:
                v325 = v1070;
LABEL_402:
                v193 = v1023;
                v201 -= *(unsigned __int16 *)(v324 + 2LL * (unsigned __int16)v201 + 0x20000);
                goto LABEL_403;
              }
              v205 = 2;
              v1017 = 2;
              v1158 = (unsigned int)LZ4HC_countPattern(v192 + 1, v234, v197, a1) + 4LL;
              v324 = a1;
            }
            v325 = v1070;
            v326 = v201 - 1;
            if ( v201 - 1 < v1070
              || v193 - v201 < 3
              || (v326 < v193 ? (v327 = 1, v328 = &v1142[v326 - v1124]) : (v327 = 0, v328 = &v1102[v326 - v193]),
                  *(_DWORD *)v328 != v197) )
            {
              v203 = v1038;
              goto LABEL_402;
            }
            v329 = (char *)v1046;
            if ( v327 )
              v329 = v1169;
            v331 = (unsigned int)LZ4HC_countPattern(v328 + 4, v329, v197, v324) + 4LL;
            if ( v327 )
            {
              v218 = &v328[v331] == v329;
              v333 = v1064;
              if ( v218 )
              {
                v988 = v1064;
                v989 = v331 & 3;
                if ( 8 * v989 )
                  v988 = (unsigned int)__ROL4__(v1064, 8 * v989);
                v331 += (unsigned int)LZ4HC_countPattern(v1102, v1046, v988, v330);
              }
              v334 = v1142;
              v332 = v1142;
            }
            else
            {
              v332 = v1102;
              v333 = v1064;
              v334 = v1142;
            }
            v335 = LZ4HC_reverseCountPattern(v328, v332, v333);
            v336 = v1102;
            v337 = v335;
            if ( v327 )
            {
              v193 = v1023;
            }
            else
            {
              v218 = &v328[-v335] == v1102;
              v193 = v1023;
              if ( v218 && v1124 < v1023 )
              {
                v341 = v333;
                if ( 8LL * (-v335 & 3) )
                  v341 = (unsigned int)__ROL4__(v333, 8 * (-(char)v335 & 3));
                v342 = LZ4HC_reverseCountPattern(v1169, v334, v341);
                v337 = v342 + v343;
                v336 = v1102;
              }
            }
            v325 = v1070;
            v201 = v1070;
            if ( v326 - v337 > v1070 )
              v201 = v326 - v337;
            v338 = v331 + v326 - v201;
            if ( v338 < v1158 || v331 > v1158 )
            {
              v203 = v1038;
              if ( v193 - v201 - 1 < 3 )
              {
                v201 = v193;
                goto LABEL_574;
              }
              if ( v1038 )
              {
LABEL_574:
                v192 = v1094;
              }
              else
              {
                v192 = v1094;
                v339 = v1158;
                if ( v338 < v1158 )
                  v339 = v338;
                if ( v1082 < v339 )
                {
                  if ( (unsigned __int64)v1094 + v193 - (unsigned __int64)v201 - (_QWORD)v336 > 0xFFFF )
                    goto LABEL_404;
                  v1082 = v339;
                  v1054 = v1133 - v201;
                  v1145 = (unsigned __int64)v1094;
                }
                v340 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v201 + 0x20000);
                if ( v340 > v201 )
                  goto LABEL_404;
                v201 -= v340;
              }
              v205 = v1017;
              goto LABEL_403;
            }
            v205 = v1017;
            v201 = v193;
            v344 = v331 - v1158 + v326;
            v192 = v1094;
            v203 = v1038;
            if ( v193 - v344 - 1 >= 3 )
              v201 = v344;
LABEL_403:
            v197 = v1064;
            v202 = v1108 - 1;
            v194 = v1102;
            v266 = v201 < v325;
            LODWORD(v195) = v1124;
            v199 = v1142;
            --v1108;
            if ( v266 )
              goto LABEL_404;
            v204 = 0;
          }
        }
        v1145 = (unsigned __int64)v192;
LABEL_404:
        v99 = v1082;
        v98 = v1054;
        v97 = v1185;
        v96 = v1191;
        v94 = v1033;
        v48 = v1060;
        v86 = v1206;
        v95 = v1075;
LABEL_128:
        v100 = v86;
        if ( v99 > v94 )
        {
          v101 = (unsigned __int64)v48 + v86;
          if ( v1145 >= v101 + 3 )
          {
            if ( v95 >= v101 )
            {
              v102 = v1206;
            }
            else if ( (__int64)(v95 - (_QWORD)v48) >= 18 )
            {
              v102 = v95 - (_DWORD)v48;
              v1206 = v95 - (_DWORD)v48;
            }
            else
            {
              if ( v86 > 18 )
                v86 = 18;
              v1206 = v86;
              if ( (_DWORD *)((char *)v48 + v86) > v97 - 1 )
              {
                v86 = v94 + v95 - (_DWORD)v48 - 4;
                v1206 = v86;
              }
              v102 = v1206;
              v103 = v86 + (_DWORD)v48 - v95;
              if ( v103 > 0 )
              {
                v1075 = v103 + v95;
                v94 -= v103;
              }
            }
            LODWORD(v104) = v1078;
            v105 = (_BYTE *)(v14 + 1);
            v20 = v1088;
            v106 = v14;
            v107 = (char *)v14;
            v108 = v1119;
            v109 = (char *)v48 - v1119;
            if ( a7 && (unsigned __int64)&v105[v109 + 8 + v109 / 0xFF] > v1088 )
              goto LABEL_399;
            if ( v109 < 0xF )
            {
              *v107 = 16 * v109;
            }
            else
            {
              v110 = v109 - 15;
              *v107 = -16;
              while ( v110 >= 0xFF )
              {
                *v105++ = -1;
                v110 -= 255LL;
              }
              *v105++ = v110;
            }
            v111 = (__int64 *)v1119;
            v112 = &v105[v109];
            do
            {
              v113 = *v111++;
              *(_QWORD *)v105 = v113;
              v105 += 8;
            }
            while ( v105 < (_BYTE *)v112 );
            *v112 = v1030;
            v14 = (__int64)(v112 + 1);
            v1078 = HIDWORD(v14);
            v114 = v102 - 4LL;
            if ( a7 && v14 + v114 / 0xFF + 6 > v1088 )
            {
              v17 = v1119;
              goto LABEL_304;
            }
            v115 = *v107;
            if ( v114 < 0xF )
            {
              *v107 = v115 + v114;
            }
            else
            {
              *v107 = v115 + 15;
              for ( j = v102 - 19LL; j >= 0x1FE; j -= 510LL )
              {
                *(_BYTE *)v14 = -1;
                v206 = (_BYTE *)(v14 + 1);
                *v206 = -1;
                v14 = (__int64)(v206 + 1);
              }
              if ( j >= 0xFF )
              {
                LOBYTE(j) = j + 1;
                *(_BYTE *)v14++ = -1;
              }
              *(_BYTE *)v14++ = j;
              v1078 = HIDWORD(v14);
            }
            LOWORD(v1030) = v1048;
            v48 = (_DWORD *)v1075;
            v86 = v94;
            v1119 = (char *)v1060 + v102;
            v1206 = v94;
            v95 = v1145;
            v1048 = v98;
            v94 = v99;
            v90 = v1114;
            v1075 = v1145;
            v1060 = v48;
            v1033 = v99;
            continue;
          }
          if ( v1145 < v101 )
          {
            v1048 = v98;
            v95 = v1145;
            v90 = v1114;
            v94 = v99;
            v1075 = v1145;
            v1033 = v99;
            continue;
          }
          if ( v95 >= v101 )
            goto LABEL_2037;
          v145 = v86 + (_DWORD)v48 - v95;
          v94 -= v145;
          if ( v94 >= 4 )
          {
            v1075 = v145 + v95;
LABEL_2037:
            v146 = v1048;
            goto LABEL_201;
          }
          v1075 = v1145;
          v146 = v98;
          v94 = v99;
LABEL_201:
          v147 = (_BYTE *)(v14 + 1);
          v106 = v14;
          v104 = v14 >> 32;
          v148 = (char *)v14;
          v108 = v1119;
          v149 = (char *)v48 - v1119;
          if ( a7 && (unsigned __int64)&v147[v149 / 0xFF + 8 + v149] > v1088 )
          {
            v20 = v1088;
LABEL_399:
            v17 = v108;
LABEL_304:
            v129 = v1030;
LABEL_305:
            v135 = (char *)v1060;
            v208 = v1206;
LABEL_306:
            if ( a7 == 2 )
            {
              v14 = __PAIR64__(v104, v106);
              v209 = v135 - v17;
              v210 = (v135 - v17 + 240) / 0xFFuLL + v135 - v17 + 1;
              if ( __PAIR64__(v104, v106) + v210 <= v20 - 3 )
              {
                if ( v208 > 255 * (v20 - 3 - __PAIR64__(v104, v106) - v210) + 18 )
                  v208 = 255 * (v20 - 3 - v106 - v210) + 18;
                if ( (__int64)(v208 + v20 - __PAIR64__(v104, v106) - v210 + 2) >= 12 )
                {
                  v211 = (_BYTE *)(__PAIR64__(v104, v106) + 1);
                  if ( v209 < 0xF )
                  {
                    *(_BYTE *)__PAIR64__(v104, v106) = 16 * v209;
                  }
                  else
                  {
                    v212 = v209 - 15;
                    *(_BYTE *)__PAIR64__(v104, v106) = -16;
                    while ( v212 >= 0xFF )
                    {
                      *v211++ = -1;
                      v212 -= 255LL;
                    }
                    *v211++ = v212;
                  }
                  v213 = &v211[v209];
                  do
                  {
                    v214 = *(_QWORD *)v17;
                    v17 += 8;
                    *(_QWORD *)v211 = v214;
                    v211 += 8;
                  }
                  while ( v211 < (_BYTE *)v213 );
                  *v213 = v129;
                  v215 = *(_BYTE *)__PAIR64__(v104, v106);
                  v14 = (__int64)(v213 + 1);
                  if ( (unsigned __int64)(v208 - 4LL) < 0xF )
                  {
                    *(_BYTE *)__PAIR64__(v104, v106) = v215 + v208 - 4;
                  }
                  else
                  {
                    *(_BYTE *)__PAIR64__(v104, v106) = v215 + 15;
                    for ( k = v208 - 19LL; k >= 0x1FE; k -= 510LL )
                    {
                      *(_BYTE *)v14 = -1;
                      v267 = (_BYTE *)(v14 + 1);
                      *v267 = -1;
                      v14 = (__int64)(v267 + 1);
                    }
                    if ( k >= 0xFF )
                    {
                      LOBYTE(k) = k + 1;
                      *(_BYTE *)v14++ = -1;
                    }
                    *(_BYTE *)v14++ = k;
                  }
                  v17 = &v135[v208];
                }
              }
              v21 = v1148 - v17;
              v22 = v1148 - v17;
              goto LABEL_215;
            }
LABEL_387:
            v24 = 0;
            goto LABEL_14;
          }
          if ( v149 < 0xF )
          {
            *v148 = 16 * v149;
          }
          else
          {
            v150 = v149 - 15;
            for ( *v148 = -16; v150 >= 0xFF; ++v147 )
            {
              *v147 = -1;
              v150 -= 255LL;
            }
            *v147++ = v150;
          }
          v151 = (__int64 *)v1119;
          v152 = &v147[v149];
          do
          {
            v153 = *v151++;
            *(_QWORD *)v147 = v153;
            v147 += 8;
          }
          while ( v147 < (_BYTE *)v152 );
          v154 = v100 - 4;
          *v152 = v1030;
          v14 = (__int64)(v152 + 1);
          v1078 = HIDWORD(v14);
          if ( a7 && v14 + v154 / 0xFF + 6 > v1088 )
          {
            v17 = v1119;
            v20 = v1088;
            goto LABEL_304;
          }
          v155 = *v148;
          if ( v154 < 0xF )
          {
            *v148 = v155 + v154;
          }
          else
          {
            *v148 = v155 + 15;
            for ( m = v100 - 19; m >= 0x1FE; m -= 510LL )
            {
              *(_BYTE *)v14 = -1;
              v258 = (_BYTE *)(v14 + 1);
              *v258 = -1;
              v14 = (__int64)(v258 + 1);
            }
            if ( m >= 0xFF )
            {
              LOBYTE(m) = m + 1;
              *(_BYTE *)v14++ = -1;
            }
            *(_BYTE *)v14++ = m;
            v1078 = HIDWORD(v14);
          }
          v86 = v99;
          v88 = (_DWORD *)v1075;
          v48 = (_DWORD *)v1145;
          v1060 = (_DWORD *)v1145;
          v87 = v146;
          v1119 = (char *)v101;
          LODWORD(v89) = v94;
          LOWORD(v1030) = v98;
          v1206 = v99;
          goto LABEL_119;
        }
        break;
      }
      if ( v95 >= (unsigned __int64)v48 + v86 )
      {
        v121 = v1206;
      }
      else
      {
        v121 = v95 - (_DWORD)v48;
        v1206 = v95 - (_DWORD)v48;
      }
      v17 = v1119;
      v122 = (_BYTE *)(v14 + 1);
      v104 = v14 >> 32;
      v123 = (char *)v48 - v1119;
      v106 = v14;
      if ( a7 && (unsigned __int64)&v122[v123 + 8 + v123 / 0xFF] > v1088 )
      {
        v135 = (char *)v1060;
        v208 = v1206;
        v129 = v1030;
        v20 = v1088;
        goto LABEL_306;
      }
      if ( v123 < 0xF )
      {
        *(_BYTE *)v14 = 16 * v123;
      }
      else
      {
        v124 = v123 - 15;
        for ( *(_BYTE *)v14 = -16; v124 >= 0xFF; ++v122 )
        {
          *v122 = -1;
          v124 -= 255LL;
        }
        *v122++ = v124;
      }
      v125 = (__int64 *)v1119;
      v126 = &v122[v123];
      do
      {
        v127 = *v125++;
        *(_QWORD *)v122 = v127;
        v122 += 8;
      }
      while ( v122 < (_BYTE *)v126 );
      v128 = (__int64)(v126 + 1);
      v129 = v1030;
      *v126 = v1030;
      v130 = v121;
      v131 = v121 - 4LL;
      if ( a7 && v128 + v131 / 0xFF + 6 > v1088 )
      {
        v20 = v1088;
        goto LABEL_305;
      }
      v132 = *(_BYTE *)v14;
      if ( v131 < 0xF )
      {
        *(_BYTE *)v14 = v132 + v131;
      }
      else
      {
        *(_BYTE *)v14 = v132 + 15;
        for ( n = v121 - 19LL; n >= 0x1FE; n -= 510LL )
        {
          *(_BYTE *)v128 = -1;
          v177 = (_BYTE *)(v128 + 1);
          *v177 = -1;
          v128 = (__int64)(v177 + 1);
        }
        if ( n >= 0xFF )
        {
          LOBYTE(n) = n + 1;
          *(_BYTE *)v128++ = -1;
        }
        *(_BYTE *)v128++ = n;
      }
      v134 = (_BYTE *)(v128 + 1);
      v135 = (char *)v1075;
      v17 = (char *)v1060 + v130;
      v136 = v1075 - ((_QWORD)v1060 + v130);
      v104 = v128 >> 32;
      v106 = v128;
      if ( a7 && (unsigned __int64)&v134[v136 / 0xFF + 8 + v136] > v1088 )
      {
        v141 = v1048;
LABEL_297:
        v20 = v1088;
        v129 = v141;
        v208 = v94;
        goto LABEL_306;
      }
      if ( v136 < 0xF )
      {
        *(_BYTE *)v128 = 16 * v136;
      }
      else
      {
        v137 = v136 - 15;
        *(_BYTE *)v128 = -16;
        while ( v137 >= 0xFF )
        {
          *v134++ = -1;
          v137 -= 255LL;
        }
        *v134++ = v137;
      }
      v138 = (__int64 *)v17;
      v139 = &v134[v136];
      do
      {
        v140 = *v138++;
        *(_QWORD *)v134 = v140;
        v134 += 8;
      }
      while ( v134 < (_BYTE *)v139 );
      v141 = v1048;
      v142 = v96 - 4;
      *v139 = v1048;
      v14 = (__int64)(v139 + 1);
      v1091 = v14;
      v1078 = HIDWORD(v14);
      if ( a7 && v14 + v142 / 0xFF + 6 > v1088 )
        goto LABEL_297;
      v143 = *(_BYTE *)v128;
      if ( v142 < 0xF )
      {
        *(_BYTE *)v128 = v143 + v142;
      }
      else
      {
        *(_BYTE *)v128 = v143 + 15;
        for ( ii = v96 - 19; ii >= 0x1FE; ii -= 510LL )
        {
          *(_BYTE *)v14 = -1;
          v178 = (_BYTE *)(v14 + 1);
          *v178 = -1;
          v14 = (__int64)(v178 + 1);
        }
        if ( ii >= 0xFF )
        {
          LOBYTE(ii) = ii + 1;
          *(_BYTE *)v14++ = -1;
        }
        *(_BYTE *)v14++ = ii;
        v1091 = v14;
        v1078 = HIDWORD(v14);
      }
      v36 = v1114;
      v15 = v97;
      v1060 = v97;
      v17 = (char *)v97;
      v1119 = (char *)v97;
      v7 = 0;
      v20 = v1088;
    }
  }
  if ( !v12 && (int)*a4 > 4096 )
  {
    memmove((void *)a1, *(const void **)(a1 + 262184), 0x40030u);
    LZ4HC_setExternalDict(v13, a2);
    *(_WORD *)(v13 + 262180) = 9;
    if ( a7 == 2 && a5 < 1 || *a4 > 0x7E000000 )
      return v7;
    v26 = a2;
    *(_QWORD *)(v13 + 0x40000) += (int)*a4;
    v27 = (char *)a2;
    v28 = (int)*a4;
    *a4 = 0;
    v29 = (char *)a2 + v28;
    v1045 = a2;
    v1120 = (char *)a2;
    v30 = a3;
    v31 = a3 + a5 - 5;
    v1092 = a3;
    if ( a7 != 2 )
      v31 = a3 + a5;
    v1079 = HIDWORD(a3);
    v1089 = v31;
    v1061 = v29;
    if ( (int)v28 < 13 )
    {
LABEL_26:
      v32 = v29 - v27;
      v33 = v32;
      if ( a7 != 2 )
      {
        if ( !a7 )
          goto LABEL_28;
        goto LABEL_668;
      }
LABEL_667:
      v31 += 5LL;
LABEL_668:
      if ( v30 + (v32 + 240) / 0xFF + v32 + 1 > v31 )
      {
        if ( a7 == 1 )
          goto LABEL_218;
        v33 = v31 - v30 - 1 - ((v31 - v30 - 1 + 241) >> 8);
      }
LABEL_28:
      v34 = v33 + (_DWORD)v27;
      if ( v33 >= 0xF )
      {
        *(_BYTE *)v30 = -16;
        v35 = v33 - 15;
        ++v30;
        while ( v35 >= 0xFF )
        {
          *(_BYTE *)v30++ = -1;
          v35 -= 255LL;
        }
        goto LABEL_31;
      }
LABEL_812:
      LOBYTE(v35) = 16 * v33;
LABEL_31:
      *(_BYTE *)v30 = v35;
      memmove((void *)(v30 + 1), v27, v33);
      *a4 = v34 - v1203;
      v24 = v33 - v1204 + v30 + 1;
      goto LABEL_13;
    }
    v290 = (unsigned __int64)(v29 - 12);
    v1076 = 0;
    v1144 = (unsigned __int64)(v29 - 12);
    v1146 = 0;
    while ( 1 )
    {
      if ( (unsigned __int64)v26 > v290 )
      {
        v29 = v1061;
        goto LABEL_26;
      }
      v291 = *(unsigned int *)(v13 + 262168);
      v292 = 256;
      v293 = *(_QWORD **)(v13 + 262152);
      v294 = *v26;
      v295 = (_DWORD)v26 + *(_DWORD *)(v13 + 262168) - (_DWORD)v293;
      v1207 = 3;
      v1103 = v293;
      v296 = *(unsigned int *)(a1 + 262172);
      v1134 = v295;
      v297 = v296;
      v1125 = *(_DWORD *)(a1 + 262172);
      v1024 = 256;
      v1039 = *v26;
      v1187 = *(_QWORD *)(a1 + 262160);
      if ( (int)v296 + 0x10000 <= v295 )
        v297 = v295 - 0xFFFF;
      v1175 = 0;
      v1031 = 0;
      v1149 = *(_QWORD *)(a1 + 262160) + (unsigned int)v291 - v296;
      v298 = 0;
      v1109 = v297;
      v299 = v291 + (_DWORD)v26 - (_DWORD)v293;
      v300 = *(_DWORD *)(a1 + 262176);
      if ( v300 < v299 )
      {
        do
        {
          v1002 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v293 + v300 - v291)) >> 17;
          v1003 = v300 - *(_DWORD *)(a1 + 4 * v1002);
          if ( v1003 > 0xFFFF )
            LOWORD(v1003) = -1;
          *(_WORD *)(a1 + 2LL * (unsigned __int16)v300 + 0x20000) = v1003;
          *(_DWORD *)(a1 + 4 * v1002) = v300++;
        }
        while ( v300 < v299 );
        v294 = v1039;
        LODWORD(v296) = v1125;
      }
      *(_DWORD *)(a1 + 262176) = v299;
      v301 = v1045;
      v302 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v1045) >> 17));
      if ( v302 >= v297 )
      {
        while ( 1 )
        {
          if ( v292 <= 0 )
          {
LABEL_683:
            v30 = v1092;
            break;
          }
          if ( v302 < (unsigned int)v291 )
          {
            if ( v302 <= (int)v291 - 4 && *(_DWORD *)(v302 - (unsigned int)v296 + v1187) == v294 )
            {
              v356 = (unsigned __int64)v301 + (unsigned int)v291 - v302;
              if ( v356 > (unsigned __int64)(v1061 - 5) )
                v356 = (unsigned __int64)(v1061 - 5);
              v357 = v1045 + 1;
              v358 = (_QWORD *)(v302 - (unsigned int)v296 + v1187 + 4);
              v359 = v1045 + 1;
              if ( (unsigned __int64)(v1045 + 1) >= v356 - 7 )
              {
                while ( (unsigned __int64)v359 < v356 - 7 )
                {
                  if ( *v359 != *v358 )
                  {
                    __asm { tzcnt   r10, rax }
                    v361 = (_DWORD)v359 + ((unsigned int)_R10 >> 3) - (_DWORD)v357;
                    goto LABEL_647;
                  }
                  ++v359;
LABEL_635:
                  ++v358;
                }
                if ( (unsigned __int64)v359 < v356 - 3 && *(_DWORD *)v358 == *(_DWORD *)v359 )
                {
                  v359 = (_QWORD *)((char *)v359 + 4);
                  v358 = (_QWORD *)((char *)v358 + 4);
                }
                if ( (unsigned __int64)v359 < v356 - 1 && *(_WORD *)v358 == *(_WORD *)v359 )
                {
                  v359 = (_QWORD *)((char *)v359 + 2);
                  v358 = (_QWORD *)((char *)v358 + 2);
                }
                if ( (unsigned __int64)v359 < v356 && *(_BYTE *)v358 == *(_BYTE *)v359 )
                  LODWORD(v359) = (_DWORD)v359 + 1;
                v361 = (_DWORD)v359 - (_DWORD)v357;
              }
              else
              {
                if ( *v358 == *v357 )
                {
                  v359 = v1045 + 3;
                  goto LABEL_635;
                }
                __asm { tzcnt   r10, rax }
                v361 = (unsigned int)_R10 >> 3;
              }
LABEL_647:
              v362 = v361 + 4;
              v363 = (char *)v1045 + v361 + 4;
              if ( v363 == (char *)v356 && v356 < (unsigned __int64)(v1061 - 5) )
              {
                v364 = (char *)v1045 + v361 + 4;
                if ( v363 >= v1061 - 12 )
                {
                  v365 = v293;
                  goto LABEL_651;
                }
                if ( *v293 != *(_QWORD *)v363 )
                {
                  __asm { tzcnt   rcx, rax }
                  v366 = (unsigned int)_RCX >> 3;
                }
                else
                {
                  v364 = v363 + 8;
                  v365 = v293 + 1;
LABEL_651:
                  while ( v364 < v1061 - 12 )
                  {
                    if ( *(_QWORD *)v364 != *v365 )
                    {
                      __asm { tzcnt   rax, rax }
                      v366 = ((unsigned int)_RAX >> 3) - (_DWORD)v363 + (_DWORD)v364;
                      goto LABEL_662;
                    }
                    v364 += 8;
                    ++v365;
                  }
                  if ( v364 < v1061 - 8 && *(_DWORD *)v365 == *(_DWORD *)v364 )
                  {
                    v364 += 4;
                    v365 = (_QWORD *)((char *)v365 + 4);
                  }
                  if ( v364 < v1061 - 6 && *(_WORD *)v365 == *(_WORD *)v364 )
                  {
                    v364 += 2;
                    v365 = (_QWORD *)((char *)v365 + 2);
                  }
                  if ( v364 < v1061 - 5 && *(_BYTE *)v365 == *v364 )
                    LODWORD(v364) = (_DWORD)v364 + 1;
                  v366 = (_DWORD)v364 - (_DWORD)v363;
                }
LABEL_662:
                v362 = v361 + v366 + 4;
              }
              v294 = v1039;
              v301 = v1045;
              if ( v362 > v1207 )
              {
                v1207 = v362;
                v1031 = v295 - v302;
              }
            }
          }
          else
          {
            v303 = v302 - (unsigned int)v291;
            if ( *(_WORD *)((char *)v301 + v1207 - 1) == *(_WORD *)((char *)v293 + v1207 + v303 - 1)
              && *(_DWORD *)((char *)v293 + v303) == v294 )
            {
              v304 = v303 + 4;
              v305 = v301 + 1;
              v306 = (_QWORD *)((char *)v293 + v304);
              v307 = (char *)(v301 + 1);
              if ( v301 + 1 >= (_DWORD *)v1061 - 3 )
              {
                while ( v307 < v1061 - 12 )
                {
                  if ( *v306 != *(_QWORD *)v307 )
                  {
                    __asm { tzcnt   rax, rax }
                    v311 = ((unsigned int)_RAX >> 3) - (_DWORD)v305 + (_DWORD)v307;
                    goto LABEL_746;
                  }
                  v307 += 8;
LABEL_478:
                  ++v306;
                }
                if ( v307 < v1061 - 8 && *(_DWORD *)v306 == *(_DWORD *)v307 )
                {
                  v307 += 4;
                  v306 = (_QWORD *)((char *)v306 + 4);
                }
                if ( v307 < v1061 - 6 && *(_WORD *)v306 == *(_WORD *)v307 )
                {
                  v307 += 2;
                  v306 = (_QWORD *)((char *)v306 + 2);
                }
                if ( v307 < v1061 - 5 && *(_BYTE *)v306 == *v307 )
                  LODWORD(v307) = (_DWORD)v307 + 1;
                v311 = (_DWORD)v307 - (_DWORD)v305;
              }
              else
              {
                if ( *v306 == *v305 )
                {
                  v307 = (char *)(v301 + 3);
                  goto LABEL_478;
                }
                __asm { tzcnt   rcx, rax }
                v311 = (unsigned int)_RCX >> 3;
              }
LABEL_746:
              v301 = v1045;
              v413 = v311 + 4;
              if ( v413 > v1207 )
              {
                v1207 = v413;
                v1031 = v295 - v302;
              }
            }
          }
          if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v302 + 0x20000) != 1 )
            goto LABEL_785;
          if ( v298 )
          {
            v1055 = v298;
            if ( v298 != 2 )
              goto LABEL_785;
          }
          else
          {
            if ( (_BYTE)v294 != HIBYTE(v294) || (unsigned __int16)v294 != HIWORD(v294) )
            {
              v298 = 1;
              goto LABEL_785;
            }
            v298 = 2;
            v1055 = 2;
            v1175 = (unsigned int)LZ4HC_countPattern(v301 + 1, v1061 - 5, v294, v301) + 4LL;
          }
          v414 = v302 - 1;
          if ( v302 - 1 < v297 || (unsigned int)v291 - v302 < 3 )
          {
            v294 = v1039;
            goto LABEL_784;
          }
          if ( v414 < (unsigned int)v291 )
          {
            v415 = 1;
            v416 = (_DWORD *)(v1187 + v414 - v1125);
          }
          else
          {
            v415 = 0;
            v416 = (_DWORD *)((char *)v293 + v414 - (unsigned int)v291);
          }
          v294 = v1039;
          if ( *v416 != v1039 )
          {
            v297 = v1109;
LABEL_784:
            v292 = v1024;
LABEL_785:
            v302 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v302 + 0x20000);
            goto LABEL_682;
          }
          v417 = v1061 - 5;
          if ( v415 )
            v417 = (char *)v1149;
          v418 = (unsigned int)LZ4HC_countPattern(v416 + 1, v417, v1039, v301) + 4LL;
          if ( v415 )
          {
            if ( (char *)v416 + v418 == v417 )
            {
              v990 = LZ4HC_rotatePattern(v418, v1039);
              v293 = v1103;
              v418 += (unsigned int)LZ4HC_countPattern(v1103, v1061 - 5, v990, v991);
            }
            else
            {
              v293 = v1103;
            }
            v419 = v1187;
          }
          else
          {
            v293 = v1103;
            v419 = (unsigned __int64)v1103;
          }
          v294 = v1039;
          HIBYTE(v1196) = HIBYTE(v1039);
          for ( jj = (unsigned __int64)v416; jj >= v419 + 4 && *(_DWORD *)(jj - 4) == v1039; jj -= 4LL )
            ;
          for ( kk = (char *)&v1196 + 3; ; --kk )
          {
            v422 = jj;
            if ( jj <= v419 )
              break;
            if ( *(_BYTE *)--jj != *kk )
              break;
          }
          v423 = (unsigned int)((_DWORD)v416 - v422);
          if ( !v415 && (_QWORD *)((char *)v416 - v423) == v293 && v1125 < (unsigned int)v291 )
          {
            v428 = LZ4HC_rotatePattern((unsigned int)(v422 - (_DWORD)v416), v1039);
            v430 = v1149;
            v1197 = v428;
            while ( v430 >= v1187 + 4 && *(_DWORD *)(v430 - 4) == v428 )
              v430 -= 4LL;
            for ( mm = (char *)&v1197 + 3; ; --mm )
            {
              v432 = v430;
              if ( v430 <= v1187 )
                break;
              if ( *(_BYTE *)--v430 != *mm )
                break;
            }
            LODWORD(v423) = v1149 - v432 + v429;
          }
          v297 = v1109;
          v424 = v1109;
          if ( v414 - (unsigned int)v423 > v1109 )
            v424 = v414 - v423;
          v425 = v418 + v414 - v424;
          if ( v425 < v1175 || v418 > v1175 )
          {
            if ( (unsigned int)v291 - v424 - 1 < 3 )
            {
              v302 = v291;
            }
            else
            {
              v301 = v1045;
              v426 = v1175;
              if ( v425 < v1175 )
                v426 = v418 + v414 - v424;
              if ( v1207 < v426 )
              {
                if ( (unsigned __int64)v1045 + v291 - v424 - (_QWORD)v293 > 0xFFFF )
                  goto LABEL_683;
                v1207 = v426;
                v1031 = v1134 - v424;
              }
              v427 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v424 + 0x20000);
              if ( v427 > v424 )
                goto LABEL_683;
              v302 = v424 - v427;
            }
          }
          else
          {
            v302 = v291;
            if ( (unsigned int)v291 - ((_DWORD)v418 - (_DWORD)v1175 + v414) - 1 >= 3 )
              v302 = v418 - v1175 + v414;
          }
          v298 = v1055;
          v292 = v1024;
LABEL_682:
          v295 = v1134;
          --v292;
          LODWORD(v296) = v1125;
          v301 = v1045;
          v1024 = v292;
          if ( v302 < v297 )
            goto LABEL_683;
        }
      }
      v372 = v1207;
      if ( v1207 < 4 )
      {
        v27 = v1120;
        v31 = v1089;
        v26 = (_DWORD *)((char *)v301 + 1);
        v1045 = v26;
LABEL_876:
        v290 = v1144;
        v13 = a1;
        continue;
      }
      v373 = v1031;
      v374 = v301;
      v375 = __PAIR64__(v1207, v1031) >> 32;
LABEL_686:
      v376 = v1144;
      v1159 = v375;
      v1170 = v374;
      while ( 1 )
      {
        v377 = v372;
        v1192 = v372;
        v378 = (_DWORD *)((char *)v301 + v372);
        v1188 = v378;
        if ( (unsigned __int64)v378 > v376 )
        {
          v379 = 0;
          v380 = 0;
          v1049 = 0;
          v1018 = 0;
          goto LABEL_689;
        }
        v1018 = v372;
        v472 = (_DWORD *)((char *)v378 - 2);
        v1076 = (unsigned __int64)v378 - 2;
        v1095 = (_DWORD *)((char *)v378 - 2);
        v473 = *(_DWORD *)(a1 + 262172);
        v474 = v473;
        v475 = *(char **)(a1 + 262152);
        v476 = (char *)*(unsigned int *)(a1 + 262168);
        v477 = *(char **)(a1 + 262160);
        v478 = (_DWORD)v476 + (_DWORD)v378 - 2 - (_DWORD)v475;
        v479 = *(_DWORD *)(a1 + 262176);
        v480 = *(_DWORD *)((char *)v378 - 2);
        v1104 = v475;
        v1040 = *(_DWORD *)(a1 + 262168);
        if ( v473 + 0x10000 <= v478 )
          v474 = v478 - 0xFFFF;
        v1135 = v478;
        v1025 = v474;
        v1056 = *(_DWORD *)(a1 + 262172);
        v1115 = *(char **)(a1 + 262160);
        v1083 = v480;
        v1049 = 0;
        if ( v479 < v478 )
        {
          do
          {
            v1004 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)&v475[v479 - (_QWORD)v476]) >> 17;
            v1005 = v479 - *(_DWORD *)(a1 + 4 * v1004);
            if ( v1005 > 0xFFFF )
              LOWORD(v1005) = -1;
            *(_WORD *)(a1 + 2LL * (unsigned __int16)v479 + 0x20000) = v1005;
            *(_DWORD *)(a1 + 4 * v1004) = v479++;
          }
          while ( v479 < v478 );
          v473 = v1056;
        }
        *(_DWORD *)(a1 + 262176) = v478;
        v481 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v472) >> 17));
        if ( v481 >= v474 )
        {
          v495 = 256;
          v1150 = &v477[(_QWORD)v476 - v473];
          v496 = (_DWORD)v472 - (_DWORD)v1045;
          v1110 = 256;
          v1127 = (_DWORD)v472 - (_DWORD)v1045;
          v494 = 0;
          v1034 = 0;
          v1176 = 0;
          do
          {
            if ( v495 <= 0 )
              break;
            if ( v481 < (unsigned int)v476 )
            {
              if ( v481 <= (int)v476 - 4 )
              {
                v547 = &v477[v481 - v1056];
                if ( *(_DWORD *)v547 == v480 )
                {
                  v548 = v472 + 1;
                  v549 = (unsigned __int64)v472 + (unsigned int)v476 - v481;
                  v550 = v547 + 4;
                  v551 = v472 + 1;
                  if ( v549 > (unsigned __int64)(v1061 - 5) )
                    v549 = (unsigned __int64)(v1061 - 5);
                  if ( (unsigned __int64)v548 >= v549 - 7 )
                  {
                    while ( (unsigned __int64)v551 < v549 - 7 )
                    {
                      if ( *v550 != *v551 )
                      {
                        __asm { tzcnt   rsi, rax }
                        v554 = (_DWORD)v551 + ((unsigned int)_RSI >> 3) - (_DWORD)v548;
                        goto LABEL_1071;
                      }
                      ++v551;
LABEL_1056:
                      ++v550;
                    }
                    if ( (unsigned __int64)v551 < v549 - 3 && *(_DWORD *)v550 == *(_DWORD *)v551 )
                    {
                      v551 = (_QWORD *)((char *)v551 + 4);
                      v550 = (_QWORD *)((char *)v550 + 4);
                    }
                    if ( (unsigned __int64)v551 < v549 - 1 && *(_WORD *)v550 == *(_WORD *)v551 )
                    {
                      v551 = (_QWORD *)((char *)v551 + 2);
                      v550 = (_QWORD *)((char *)v550 + 2);
                    }
                    if ( (unsigned __int64)v551 < v549 && *(_BYTE *)v550 == *(_BYTE *)v551 )
                      LODWORD(v551) = (_DWORD)v551 + 1;
                    v554 = (_DWORD)v551 - (_DWORD)v548;
                  }
                  else
                  {
                    if ( *v548 == *v550 )
                    {
                      v551 = v472 + 3;
                      goto LABEL_1056;
                    }
                    __asm { tzcnt   rsi, rax }
                    v554 = (unsigned int)_RSI >> 3;
                  }
LABEL_1071:
                  v556 = v554 + 4;
                  v557 = (char *)v472 + v554 + 4;
                  if ( v557 == (char *)v549 && v549 < (unsigned __int64)(v1061 - 5) )
                  {
                    v558 = v1104;
                    v559 = (char *)v472 + v554 + 4;
                    if ( v557 >= v1061 - 12 )
                    {
                      while ( v559 < v1061 - 12 )
                      {
                        if ( *v558 != *(_QWORD *)v559 )
                        {
                          __asm { tzcnt   rax, rax }
                          v562 = ((unsigned int)_RAX >> 3) - (_DWORD)v557 + (_DWORD)v559;
                          goto LABEL_1091;
                        }
                        v559 += 8;
LABEL_1076:
                        ++v558;
                      }
                      if ( v559 < v1061 - 8 && *(_DWORD *)v558 == *(_DWORD *)v559 )
                      {
                        v559 += 4;
                        v558 = (_QWORD *)((char *)v558 + 4);
                      }
                      if ( v559 < v1061 - 6 && *(_WORD *)v558 == *(_WORD *)v559 )
                      {
                        v559 += 2;
                        v558 = (_QWORD *)((char *)v558 + 2);
                      }
                      if ( v559 < v1061 - 5 && *(_BYTE *)v558 == *v559 )
                        LODWORD(v559) = (_DWORD)v559 + 1;
                      v562 = (_DWORD)v559 - (_DWORD)v557;
                    }
                    else
                    {
                      if ( *(_QWORD *)v557 == *(_QWORD *)v1104 )
                      {
                        v559 = v557 + 8;
                        goto LABEL_1076;
                      }
                      __asm { tzcnt   rcx, rax }
                      v562 = (unsigned int)_RCX >> 3;
                    }
LABEL_1091:
                    v556 = v554 + v562 + 4;
                  }
                  v564 = 0;
                  if ( v1127 )
                  {
                    v565 = (_DWORD)v1045 - (_DWORD)v472;
                    if ( (char *)v1045 - (char *)v472 <= v1115 - v547 )
                      v565 = (_DWORD)v1115 - (_DWORD)v547;
                    while ( v564 - v565 > 3 )
                    {
                      if ( *(_DWORD *)((char *)v472 + v564 - 4) != *(_DWORD *)&v547[v564 - 4] )
                      {
                        _BitScanReverse(&v566, *(_DWORD *)((char *)v472 + v564 - 4) ^ *(_DWORD *)&v547[v564 - 4]);
                        v564 -= (31 - v566) >> 3;
                        goto LABEL_1098;
                      }
                      v564 -= 4;
                    }
                    if ( v564 > v565 )
                    {
                      do
                      {
                        if ( *((_BYTE *)v472 + v564 - 1) != v547[v564 - 1] )
                          break;
                        --v564;
                      }
                      while ( v564 > v565 );
                      LOWORD(v478) = v1135;
                    }
                  }
LABEL_1098:
                  LODWORD(v476) = v1040;
                  v567 = v556 - v564;
                  v475 = v1104;
                  v474 = v1025;
                  if ( v567 > v1018 )
                  {
                    v1018 = v567;
                    v1049 = v478 - v481;
                    v1076 = (unsigned __int64)v472 + v564;
                  }
                  v480 = v1083;
                  v494 = v1034;
                }
                else
                {
                  v474 = v1025;
                }
              }
            }
            else
            {
              v512 = &v475[v481 - (unsigned int)v476];
              if ( *(_WORD *)((char *)v1045 + v1018 - 1) == *(_WORD *)&v512[v1018 - (__int64)v496 - 1]
                && *(_DWORD *)v512 == v480 )
              {
                v218 = v496 == 0;
                v513 = 0;
                if ( !v218 )
                {
                  v514 = (_DWORD)v1045 - (_DWORD)v472;
                  v515 = -(__int64)(v481 - (unsigned int)v476);
                  if ( (char *)v1045 - (char *)v472 <= v515 )
                    v514 = v515;
                  while ( v513 - v514 > 3 )
                  {
                    if ( *(_DWORD *)&v512[v513 - 4] != *(_DWORD *)((char *)v472 + v513 - 4) )
                    {
                      _BitScanReverse(&v516, *(_DWORD *)&v512[v513 - 4] ^ *(_DWORD *)((char *)v472 + v513 - 4));
                      v513 -= (31 - v516) >> 3;
                      goto LABEL_971;
                    }
                    v513 -= 4;
                  }
                  if ( v513 > v514 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v472 + v513 - 1) != v512[v513 - 1] )
                        break;
                      --v513;
                    }
                    while ( v513 > v514 );
                    v474 = v1025;
                  }
                }
LABEL_971:
                v517 = v472 + 1;
                v518 = v512 + 4;
                v519 = (char *)(v472 + 1);
                if ( v472 + 1 >= (_DWORD *)v1061 - 3 )
                {
                  while ( v519 < v1061 - 12 )
                  {
                    if ( *v518 != *(_QWORD *)v519 )
                    {
                      __asm { tzcnt   rax, rax }
                      v533 = ((unsigned int)_RAX >> 3) - (_DWORD)v517 + (_DWORD)v519;
                      goto LABEL_1869;
                    }
                    v519 += 8;
LABEL_974:
                    ++v518;
                  }
                  if ( v519 < v1061 - 8 && *(_DWORD *)v518 == *(_DWORD *)v519 )
                  {
                    v519 += 4;
                    v518 = (_QWORD *)((char *)v518 + 4);
                  }
                  if ( v519 < v1061 - 6 && *(_WORD *)v518 == *(_WORD *)v519 )
                  {
                    v519 += 2;
                    v518 = (_QWORD *)((char *)v518 + 2);
                  }
                  if ( v519 < v1061 - 5 && *(_BYTE *)v518 == *v519 )
                    LODWORD(v519) = (_DWORD)v519 + 1;
                  v533 = (_DWORD)v519 - (_DWORD)v517;
                }
                else
                {
                  if ( *v517 == *v518 )
                  {
                    v519 = (char *)(v472 + 3);
                    goto LABEL_974;
                  }
                  __asm { tzcnt   rcx, rax }
                  v533 = (unsigned int)_RCX >> 3;
                }
LABEL_1869:
                v480 = v1083;
                v494 = v1034;
                v951 = v533 - v513 + 4;
                if ( v951 > v1018 )
                {
                  v1018 = v951;
                  v1049 = v478 - v481;
                  v1076 = (unsigned __int64)v472 + v513;
                }
              }
              else
              {
                v494 = v1034;
              }
            }
            if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v481 + 0x20000) != 1 )
              goto LABEL_1048;
            if ( v494 )
            {
              v1034 = v494;
              if ( v494 != 2 )
                goto LABEL_1048;
            }
            else
            {
              if ( (_BYTE)v480 != HIBYTE(v480) || (unsigned __int16)v480 != HIWORD(v480) )
              {
                v494 = 1;
                v1034 = 1;
LABEL_1048:
                LODWORD(v476) = v1040;
                v474 = v1025;
                v481 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v481 + 0x20000);
                goto LABEL_899;
              }
              v1034 = 2;
              v955 = LZ4HC_countPattern(v472 + 1, v1061 - 5, v480, 1);
              v494 = 2;
              v1176 = v955 + 4LL;
            }
            v534 = v481 - 1;
            if ( v481 - 1 < v474 || (unsigned int)v476 - v481 < 3 )
            {
              v480 = v1083;
              goto LABEL_1048;
            }
            if ( v534 < (unsigned int)v476 )
            {
              v535 = 1;
              v476 = &v1115[v534 - v1056];
            }
            else
            {
              v535 = 0;
              v476 = &v475[v534 - (unsigned int)v476];
            }
            v480 = v1083;
            if ( *(_DWORD *)v476 != v1083 )
              goto LABEL_1048;
            v536 = v1061 - 5;
            if ( v535 )
              v536 = v1150;
            v537 = (unsigned int)LZ4HC_countPattern(v476 + 4, v536, v1083, 1) + 4LL;
            if ( v535 )
            {
              if ( &v476[v537] == v536 )
              {
                v992 = LZ4HC_rotatePattern(v537, v1083);
                v475 = v1104;
                v537 += (unsigned int)LZ4HC_countPattern(v1104, v1061 - 5, v992, v993);
              }
              else
              {
                v475 = v1104;
              }
              v538 = (unsigned __int64)v1115;
              v539 = v1115;
            }
            else
            {
              v475 = v1104;
              v538 = (unsigned __int64)v1115;
              v539 = v1104;
            }
            v480 = v1083;
            v1198 = v1083;
            for ( nn = (unsigned __int64)v476; nn >= (unsigned __int64)(v539 + 4) && *(_DWORD *)(nn - 4) == v1083; nn -= 4LL )
              ;
            for ( i1 = (char *)&v1198 + 3; ; --i1 )
            {
              v542 = nn;
              if ( nn <= (unsigned __int64)v539 )
                break;
              if ( *(_BYTE *)--nn != *i1 )
                break;
            }
            v543 = (unsigned int)((_DWORD)v476 - v542);
            if ( v535 )
            {
              LODWORD(v476) = v1040;
            }
            else
            {
              v218 = &v476[-v543] == v475;
              LODWORD(v476) = v1040;
              if ( v218 && v1056 < v1040 )
              {
                v568 = LZ4HC_rotatePattern((unsigned int)-(int)v543, v1083);
                v570 = (unsigned __int64)v1150;
                v1199 = v568;
                while ( v570 >= v538 + 4 && *(_DWORD *)(v570 - 4) == v568 )
                  v570 -= 4LL;
                for ( i2 = (char *)&v1199 + 3; ; --i2 )
                {
                  v572 = v570;
                  if ( v570 <= v538 )
                    break;
                  if ( *(_BYTE *)--v570 != *i2 )
                    break;
                }
                LODWORD(v543) = (_DWORD)v1150 - v572 + v569;
              }
            }
            v474 = v1025;
            v481 = v1025;
            if ( v534 - (unsigned int)v543 > v1025 )
              v481 = v534 - v543;
            v544 = v537 + v534 - v481;
            if ( v544 < v1176 || v537 > v1176 )
            {
              if ( (unsigned int)v476 - v481 - 1 < 3 )
              {
                v481 = (unsigned int)v476;
              }
              else if ( !v1127 )
              {
                v472 = v1095;
                v545 = v1176;
                if ( v544 < v1176 )
                  v545 = v544;
                if ( v1018 < v545 )
                {
                  if ( (unsigned __int64)(unsigned int)v476 + (char *)v1095 - v481 - v475 > 0xFFFF )
                    break;
                  v1018 = v545;
                  v1049 = v1135 - v481;
                  v1076 = (unsigned __int64)v1095;
                }
                v546 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v481 + 0x20000);
                if ( v546 > v481 )
                  break;
                v481 -= v546;
                goto LABEL_898;
              }
            }
            else
            {
              v481 = (unsigned int)v476;
              if ( (unsigned int)v476 - ((_DWORD)v537 - (_DWORD)v1176 + v534) - 1 >= 3 )
                v481 = v537 - v1176 + v534;
            }
            v472 = v1095;
LABEL_898:
            v494 = v1034;
LABEL_899:
            LOWORD(v478) = v1135;
            v495 = v1110 - 1;
            v496 = v1127;
            v477 = v1115;
            --v1110;
          }
          while ( v481 >= v474 );
        }
        LODWORD(v375) = v1159;
        v374 = v1170;
        v378 = v1188;
        v377 = v1192;
        v380 = v1018;
        v301 = v1045;
        v372 = v1207;
        v379 = v1049;
        v376 = v1144;
LABEL_689:
        if ( v380 <= v372 )
        {
          v433 = (_BYTE *)(v30 + 1);
          v27 = v1120;
          v391 = v30 >> 32;
          v434 = (char *)v1045 - v1120;
          v393 = v30;
          v435 = (char *)v30;
          if ( a7 && (unsigned __int64)&v433[v434 / 0xFF + 8 + v434] > v1089 )
          {
            v301 = v1045;
            v499 = v1207;
            v440 = v1031;
            v31 = v1089;
            goto LABEL_940;
          }
          if ( v434 < 0xF )
          {
            *(_BYTE *)v30 = 16 * v434;
          }
          else
          {
            v436 = v434 - 15;
            *(_BYTE *)v30 = -16;
            while ( v436 >= 0xFF )
            {
              *v433++ = -1;
              v436 -= 255LL;
            }
            *v433++ = v436;
          }
          v437 = (__int64 *)v1120;
          v438 = &v433[v434];
          do
          {
            v439 = *v437++;
            *(_QWORD *)v433 = v439;
            v433 += 8;
          }
          while ( v433 < (_BYTE *)v438 );
          v440 = v1031;
          v441 = v377 - 4;
          v31 = v1089;
          *v438 = v1031;
          v30 = (__int64)(v438 + 1);
          v1092 = v30;
          v1079 = HIDWORD(v30);
          if ( a7 && v30 + v441 / 0xFF + 6 > v1089 )
          {
            v301 = v1045;
LABEL_939:
            v499 = v1207;
LABEL_940:
            if ( a7 != 2 )
              goto LABEL_387;
            v503 = (char *)v301 - v27;
            v30 = __PAIR64__(v391, v393);
            v504 = ((char *)v301 - v27 + 240) / 0xFFuLL + (char *)v301 - v27 + 1;
            if ( __PAIR64__(v391, v393) + v504 <= v31 - 3 )
            {
              if ( v499 > 255 * (v31 - 3 - __PAIR64__(v391, v393) - v504) + 18 )
                v499 = 255 * (v31 - 3 - v393 - v504) + 18;
              if ( (__int64)(v31 + v499 - __PAIR64__(v391, v393) - v504 + 2) >= 12 )
              {
                v505 = (_BYTE *)(__PAIR64__(v391, v393) + 1);
                if ( v503 < 0xF )
                {
                  *(_BYTE *)__PAIR64__(v391, v393) = 16 * v503;
                }
                else
                {
                  v506 = v503 - 15;
                  *(_BYTE *)__PAIR64__(v391, v393) = -16;
                  while ( v506 >= 0xFF )
                  {
                    *v505++ = -1;
                    v506 -= 255LL;
                  }
                  *v505++ = v506;
                }
                v507 = &v505[v503];
                do
                {
                  v508 = *(_QWORD *)v27;
                  v27 += 8;
                  *(_QWORD *)v505 = v508;
                  v505 += 8;
                }
                while ( v505 < (_BYTE *)v507 );
                *v507 = v440;
                v509 = *(_BYTE *)__PAIR64__(v391, v393);
                v30 = (__int64)(v507 + 1);
                if ( (unsigned __int64)(v499 - 4LL) < 0xF )
                {
                  *(_BYTE *)__PAIR64__(v391, v393) = v509 + v499 - 4;
                }
                else
                {
                  *(_BYTE *)__PAIR64__(v391, v393) = v509 + 15;
                  for ( i3 = v499 - 19LL; i3 >= 0x1FE; i3 -= 510LL )
                  {
                    *(_BYTE *)v30 = -1;
                    v511 = (_BYTE *)(v30 + 1);
                    *v511 = -1;
                    v30 = (__int64)(v511 + 1);
                  }
                  if ( i3 >= 0xFF )
                  {
                    LOBYTE(i3) = i3 + 1;
                    *(_BYTE *)v30++ = -1;
                  }
                  *(_BYTE *)v30++ = i3;
                }
                v27 = (char *)v1045 + v499;
              }
            }
            v32 = v1061 - v27;
            v33 = v1061 - v27;
            goto LABEL_667;
          }
          v442 = *v435;
          if ( v441 >= 0xF )
          {
            *v435 = v442 + 15;
            for ( i4 = v441 - 15; i4 >= 0x1FE; i4 -= 510LL )
            {
              *(_BYTE *)v30 = -1;
              v965 = (_BYTE *)(v30 + 1);
              *v965 = -1;
              v30 = (__int64)(v965 + 1);
            }
            if ( i4 >= 0xFF )
            {
              LOBYTE(i4) = i4 + 1;
              *(_BYTE *)v30++ = -1;
            }
            *(_BYTE *)v30++ = i4;
            v1092 = v30;
            v1079 = HIDWORD(v30);
          }
          else
          {
            *v435 = v442 + v441;
          }
          v26 = v378;
          v1045 = v378;
          v27 = (char *)v378;
          v1120 = (char *)v378;
          goto LABEL_876;
        }
        v381 = v1076;
        if ( v374 < v301 && v1076 < (unsigned __int64)v301 + (int)v375 )
        {
          v301 = v374;
          v1045 = v374;
          LOWORD(v1031) = v373;
          v372 = v375;
          v1207 = v375;
        }
        if ( (__int64)(v1076 - (_QWORD)v301) >= 3 )
          break;
        v372 = v380;
        v1045 = (_DWORD *)v1076;
        v1207 = v380;
        v301 = (_DWORD *)v1076;
        LOWORD(v1031) = v379;
      }
      while ( 2 )
      {
        if ( (__int64)(v381 - (_QWORD)v301) < 18 )
        {
          v449 = v372;
          if ( v372 > 18 )
            v449 = 18;
          if ( (unsigned __int64)v301 + v449 > v381 + v380 - 4LL )
            v449 = v380 + v381 - (_DWORD)v301 - 4;
          v450 = v449 + (_DWORD)v301 - v381;
          if ( v450 > 0 )
          {
            v381 += v450;
            v380 -= v450;
            v1076 = v381;
            v1018 = v380;
          }
        }
        v382 = v380;
        v1193 = v380;
        v383 = (_DWORD *)(v381 + v380);
        v1189 = v383;
        if ( (unsigned __int64)v383 > v376 )
        {
          v384 = 0;
          v385 = 0;
          goto LABEL_695;
        }
        v1041 = v380;
        v482 = (_DWORD *)((char *)v383 - 3);
        v1146 = (unsigned __int64)v383 - 3;
        v1096 = (_DWORD *)((char *)v383 - 3);
        v483 = *(_DWORD *)(a1 + 262168);
        v484 = *(_DWORD *)(a1 + 262172);
        v485 = *(char **)(a1 + 262152);
        v486 = v484;
        v487 = *(char **)(a1 + 262160);
        v488 = *(_DWORD *)(a1 + 262176);
        v489 = (_DWORD)v383 - 3 + v483 - (_DWORD)v485;
        v490 = *(_DWORD *)((char *)v383 - 3);
        v1116 = v485;
        v1065 = v483;
        v1136 = (_WORD)v383 - 3 + v483 - (_WORD)v485;
        if ( v484 + 0x10000 <= v489 )
          v486 = v489 - 0xFFFF;
        v1057 = *(_DWORD *)(a1 + 262172);
        v1126 = v486;
        v1105 = *(char **)(a1 + 262160);
        v1084 = *(_DWORD *)((char *)v383 - 3);
        v1071 = 0;
        if ( v488 < v489 )
        {
          do
          {
            v1006 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)&v485[v488 - (unsigned __int64)v483]) >> 17;
            v1007 = v488 - *(_DWORD *)(a1 + 4 * v1006);
            if ( v1007 > 0xFFFF )
              LOWORD(v1007) = -1;
            *(_WORD *)(a1 + 2LL * (unsigned __int16)v488 + 0x20000) = v1007;
            *(_DWORD *)(a1 + 4 * v1006) = v488++;
          }
          while ( v488 < v489 );
          v484 = v1057;
        }
        *(_DWORD *)(a1 + 262176) = v489;
        v491 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v482) >> 17));
        if ( v491 >= v486 )
        {
          v498 = 256;
          v1111 = 256;
          v1151 = (unsigned __int64)&v487[v483 - v484];
          v497 = (_DWORD)v482 - v1076;
          v522 = 0;
          v1026 = (_DWORD)v482 - v1076;
          v1035 = 0;
          v1177 = 0;
          while ( 1 )
          {
            if ( v498 <= 0 )
              goto LABEL_905;
            if ( v491 < v483 )
            {
              if ( v491 > v483 - 4 )
                goto LABEL_1143;
              v574 = &v487[v491 - v1057];
              if ( *(_DWORD *)v574 == v490 )
              {
                v575 = v482 + 1;
                v576 = (unsigned __int64)v482 + v483 - v491;
                v577 = v574 + 4;
                v578 = v482 + 1;
                if ( v576 > (unsigned __int64)(v1061 - 5) )
                  v576 = (unsigned __int64)(v1061 - 5);
                if ( (unsigned __int64)v575 >= v576 - 7 )
                {
                  while ( (unsigned __int64)v578 < v576 - 7 )
                  {
                    if ( *v577 != *v578 )
                    {
                      __asm { tzcnt   rbx, rax }
                      v598 = (_DWORD)v578 + ((unsigned int)_RBX >> 3) - (_DWORD)v575;
                      goto LABEL_1193;
                    }
                    ++v578;
LABEL_1134:
                    ++v577;
                  }
                  if ( (unsigned __int64)v578 < v576 - 3 && *(_DWORD *)v577 == *(_DWORD *)v578 )
                  {
                    v578 = (_QWORD *)((char *)v578 + 4);
                    v577 = (_QWORD *)((char *)v577 + 4);
                  }
                  if ( (unsigned __int64)v578 < v576 - 1 && *(_WORD *)v577 == *(_WORD *)v578 )
                  {
                    v578 = (_QWORD *)((char *)v578 + 2);
                    v577 = (_QWORD *)((char *)v577 + 2);
                  }
                  if ( (unsigned __int64)v578 < v576 && *(_BYTE *)v577 == *(_BYTE *)v578 )
                    LODWORD(v578) = (_DWORD)v578 + 1;
                  v598 = (_DWORD)v578 - (_DWORD)v575;
                }
                else
                {
                  if ( *v575 == *v577 )
                  {
                    v578 = v482 + 3;
                    goto LABEL_1134;
                  }
                  __asm { tzcnt   rbx, rax }
                  v598 = (unsigned int)_RBX >> 3;
                }
LABEL_1193:
                v600 = v598 + 4;
                v601 = (char *)v482 + v598 + 4;
                if ( v601 == (char *)v576 && v576 < (unsigned __int64)(v1061 - 5) )
                {
                  v602 = v1116;
                  v603 = (char *)v482 + v598 + 4;
                  if ( v601 >= v1061 - 12 )
                  {
                    while ( v603 < v1061 - 12 )
                    {
                      if ( *v602 != *(_QWORD *)v603 )
                      {
                        __asm { tzcnt   rax, rax }
                        v606 = ((unsigned int)_RAX >> 3) - (_DWORD)v601 + (_DWORD)v603;
                        goto LABEL_1213;
                      }
                      v603 += 8;
LABEL_1198:
                      ++v602;
                    }
                    if ( v603 < v1061 - 8 && *(_DWORD *)v602 == *(_DWORD *)v603 )
                    {
                      v603 += 4;
                      v602 = (_QWORD *)((char *)v602 + 4);
                    }
                    if ( v603 < v1061 - 6 && *(_WORD *)v602 == *(_WORD *)v603 )
                    {
                      v603 += 2;
                      v602 = (_QWORD *)((char *)v602 + 2);
                    }
                    if ( v603 < v1061 - 5 && *(_BYTE *)v602 == *v603 )
                      LODWORD(v603) = (_DWORD)v603 + 1;
                    v606 = (_DWORD)v603 - (_DWORD)v601;
                  }
                  else
                  {
                    if ( *(_QWORD *)v1116 == *(_QWORD *)v601 )
                    {
                      v603 = v601 + 8;
                      goto LABEL_1198;
                    }
                    __asm { tzcnt   rcx, rax }
                    v606 = (unsigned int)_RCX >> 3;
                  }
LABEL_1213:
                  v600 = v598 + v606 + 4;
                }
                v582 = 0;
                if ( v497 )
                {
                  v608 = v1076 - (_DWORD)v482;
                  if ( (__int64)(v1076 - (_QWORD)v482) <= v1105 - v574 )
                    v608 = (_DWORD)v1105 - (_DWORD)v574;
                  while ( v582 - v608 > 3 )
                  {
                    if ( *(_DWORD *)&v574[v582 - 4] != *(_DWORD *)((char *)v482 + v582 - 4) )
                    {
                      _BitScanReverse(&v581, *(_DWORD *)&v574[v582 - 4] ^ *(_DWORD *)((char *)v482 + v582 - 4));
                      v582 -= (31 - v581) >> 3;
                      goto LABEL_1139;
                    }
                    v582 -= 4;
                  }
                  if ( v582 > v608 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v482 + v582 - 1) != v574[v582 - 1] )
                        break;
                      --v582;
                    }
                    while ( v582 > v608 );
                    LOWORD(v489) = v1136;
                  }
                }
LABEL_1139:
                v483 = v1065;
                v583 = v600 - v582;
                v485 = v1116;
                v486 = v1126;
                if ( v583 > v1041 )
                {
                  v1041 = v583;
                  v1071 = v489 - v491;
                  v1146 = (unsigned __int64)v482 + v582;
                }
                v490 = v1084;
LABEL_1142:
                v522 = v1035;
                goto LABEL_1143;
              }
              v485 = v1116;
            }
            else
            {
              v523 = &v485[v491 - v483];
              if ( *(_WORD *)(v1076 + v1041 - 1) != *(_WORD *)&v523[v1041 - (__int64)v497 - 1]
                || *(_DWORD *)v523 != v490 )
              {
                goto LABEL_1142;
              }
              v524 = 0;
              if ( v497 )
              {
                v525 = v1076 - (_DWORD)v482;
                v526 = -(__int64)(v491 - v483);
                if ( (__int64)(v1076 - (_QWORD)v482) <= v526 )
                  v525 = v526;
                while ( v524 - v525 > 3 )
                {
                  if ( *(_DWORD *)&v523[v524 - 4] != *(_DWORD *)((char *)v482 + v524 - 4) )
                  {
                    _BitScanReverse(&v527, *(_DWORD *)&v523[v524 - 4] ^ *(_DWORD *)((char *)v482 + v524 - 4));
                    v524 -= (31 - v527) >> 3;
                    goto LABEL_989;
                  }
                  v524 -= 4;
                }
                if ( v524 > v525 )
                {
                  do
                  {
                    if ( *((_BYTE *)v482 + v524 - 1) != v523[v524 - 1] )
                      break;
                    --v524;
                  }
                  while ( v524 > v525 );
                  v497 = v1026;
                }
              }
LABEL_989:
              v528 = v482 + 1;
              v529 = v523 + 4;
              v530 = (char *)(v482 + 1);
              if ( v482 + 1 >= (_DWORD *)v1061 - 3 )
              {
                while ( v530 < v1061 - 12 )
                {
                  if ( *v529 != *(_QWORD *)v530 )
                  {
                    __asm { tzcnt   rax, rax }
                    v573 = ((unsigned int)_RAX >> 3) - (_DWORD)v528 + (_DWORD)v530;
                    goto LABEL_1886;
                  }
                  v530 += 8;
LABEL_992:
                  ++v529;
                }
                if ( v530 < v1061 - 8 && *(_DWORD *)v529 == *(_DWORD *)v530 )
                {
                  v530 += 4;
                  v529 = (_QWORD *)((char *)v529 + 4);
                }
                if ( v530 < v1061 - 6 && *(_WORD *)v529 == *(_WORD *)v530 )
                {
                  v530 += 2;
                  v529 = (_QWORD *)((char *)v529 + 2);
                }
                if ( v530 < v1061 - 5 && *(_BYTE *)v529 == *v530 )
                  LODWORD(v530) = (_DWORD)v530 + 1;
                v573 = (_DWORD)v530 - (_DWORD)v528;
              }
              else
              {
                if ( *v528 == *v529 )
                {
                  v530 = (char *)(v482 + 3);
                  goto LABEL_992;
                }
                __asm { tzcnt   rcx, rax }
                v573 = (unsigned int)_RCX >> 3;
              }
LABEL_1886:
              v490 = v1084;
              v522 = v1035;
              v957 = v573 - v524 + 4;
              if ( v957 > v1041 )
              {
                v1041 = v957;
                v1071 = v489 - v491;
                v1146 = (unsigned __int64)v482 + v524;
              }
            }
LABEL_1143:
            if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v491 + 0x20000) == 1 )
            {
              if ( v522 )
              {
                v1035 = v522;
                if ( v522 != 2 )
                  goto LABEL_903;
              }
              else
              {
                if ( (_BYTE)v490 != HIBYTE(v490) || (unsigned __int16)v490 != HIWORD(v490) )
                {
                  v522 = 1;
                  v1035 = 1;
                  goto LABEL_903;
                }
                v1035 = 2;
                v961 = LZ4HC_countPattern(v482 + 1, v1061 - 5, v490, 1);
                v522 = 2;
                v1177 = v961 + 4LL;
              }
              v584 = v491 - 1;
              if ( v491 - 1 < v486 || v483 - v491 < 3 )
              {
                v490 = v1084;
              }
              else
              {
                if ( v584 < v483 )
                {
                  v585 = 1;
                  v586 = &v1105[v584 - v1057];
                }
                else
                {
                  v585 = 0;
                  v586 = &v485[v584 - v483];
                }
                v490 = v1084;
                if ( *(_DWORD *)v586 == v1084 )
                {
                  v587 = v1061 - 5;
                  if ( v585 )
                    v587 = (char *)v1151;
                  v588 = (unsigned int)LZ4HC_countPattern(v586 + 4, v587, v1084, 1) + 4LL;
                  if ( v585 )
                  {
                    if ( &v586[v588] == v587 )
                    {
                      v994 = LZ4HC_rotatePattern(v588, v1084);
                      v485 = v1116;
                      v588 += (unsigned int)LZ4HC_countPattern(v1116, v1061 - 5, v994, v995);
                    }
                    else
                    {
                      v485 = v1116;
                    }
                    v589 = (unsigned __int64)v1105;
                    v590 = v1105;
                  }
                  else
                  {
                    v485 = v1116;
                    v589 = (unsigned __int64)v1105;
                    v590 = v1116;
                  }
                  v490 = v1084;
                  v1200 = v1084;
                  for ( i5 = (unsigned __int64)v586;
                        i5 >= (unsigned __int64)(v590 + 4) && *(_DWORD *)(i5 - 4) == v1084;
                        i5 -= 4LL )
                  {
                    ;
                  }
                  for ( i6 = (char *)&v1200 + 3; ; --i6 )
                  {
                    v593 = i5;
                    if ( i5 <= (unsigned __int64)v590 )
                      break;
                    if ( *(_BYTE *)--i5 != *i6 )
                      break;
                  }
                  v483 = v1065;
                  v594 = (unsigned int)((_DWORD)v586 - v593);
                  if ( !v585 && &v586[-v594] == v485 && v1057 < v1065 )
                  {
                    v609 = LZ4HC_rotatePattern((unsigned int)(v593 - (_DWORD)v586), v1084);
                    v611 = v1151;
                    v1201 = v609;
                    while ( v611 >= v589 + 4 && *(_DWORD *)(v611 - 4) == v609 )
                      v611 -= 4LL;
                    for ( i7 = (char *)&v1201 + 3; ; --i7 )
                    {
                      v613 = v611;
                      if ( v611 <= v589 )
                        break;
                      if ( *(_BYTE *)--v611 != *i7 )
                        break;
                    }
                    LODWORD(v594) = v1151 - v613 + v610;
                  }
                  v486 = v1126;
                  v491 = v1126;
                  if ( v584 - (unsigned int)v594 > v1126 )
                    v491 = v584 - v594;
                  v595 = v588 + v584 - v491;
                  if ( v595 >= v1177 && v588 <= v1177 )
                  {
                    v522 = v1035;
                    v491 = v483;
                    v962 = v588 - v1177 + v584;
                    v482 = v1096;
                    v497 = v1026;
                    if ( v483 - v962 - 1 >= 3 )
                      v491 = v962;
                    goto LABEL_904;
                  }
                  v497 = v1026;
                  if ( v483 - v491 - 1 < 3 )
                  {
                    v491 = v483;
                    goto LABEL_1171;
                  }
                  if ( v1026 )
                  {
LABEL_1171:
                    v482 = v1096;
                  }
                  else
                  {
                    v482 = v1096;
                    v596 = v1177;
                    if ( v595 < v1177 )
                      v596 = v595;
                    if ( v1041 < v596 )
                    {
                      if ( (unsigned __int64)v483 + (char *)v1096 - v491 - v485 > 0xFFFF )
                        goto LABEL_905;
                      v1041 = v596;
                      v1071 = v1136 - v491;
                      v1146 = (unsigned __int64)v1096;
                    }
                    v597 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v491 + 0x20000);
                    if ( v597 > v491 )
                      goto LABEL_905;
                    v491 -= v597;
                  }
                  v522 = v1035;
                  goto LABEL_904;
                }
              }
              v497 = v1026;
            }
LABEL_903:
            v486 = v1126;
            v491 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v491 + 0x20000);
LABEL_904:
            LOWORD(v489) = v1136;
            v498 = v1111 - 1;
            v487 = v1105;
            --v1111;
            if ( v491 < v486 )
              goto LABEL_905;
          }
        }
        v1146 = (unsigned __int64)v482;
LABEL_905:
        v385 = v1041;
        v384 = v1071;
        v383 = v1189;
        v382 = v1193;
        v380 = v1018;
        v301 = v1045;
        v372 = v1207;
        v381 = v1076;
LABEL_695:
        v386 = v372;
        if ( v385 > v380 )
        {
          v387 = (unsigned __int64)v301 + v372;
          if ( v1146 >= v387 + 3 )
          {
            if ( v381 >= v387 )
            {
              v388 = v1207;
            }
            else if ( (__int64)(v381 - (_QWORD)v301) < 18 )
            {
              if ( v372 > 18 )
                v372 = 18;
              v1207 = v372;
              if ( (_DWORD *)((char *)v301 + v372) > v383 - 1 )
              {
                v372 = v380 + v381 - (_DWORD)v301 - 4;
                v1207 = v372;
              }
              v388 = v1207;
              v461 = v372 + (_DWORD)v301 - v381;
              if ( v461 > 0 )
              {
                v1076 = v461 + v381;
                v380 -= v461;
              }
            }
            else
            {
              v388 = v381 - (_DWORD)v301;
              v1207 = v381 - (_DWORD)v301;
            }
            v462 = (_BYTE *)(v30 + 1);
            LODWORD(v391) = v1079;
            v393 = v30;
            v463 = (char *)v30;
            v464 = (char *)v1045 - v1120;
            if ( a7 && (unsigned __int64)&v462[v464 / 0xFF + 8 + v464] > v1089 )
            {
              v301 = v1045;
              v27 = v1120;
              v31 = v1089;
              goto LABEL_917;
            }
            if ( v464 < 0xF )
            {
              *(_BYTE *)v30 = 16 * v464;
            }
            else
            {
              v465 = v464 - 15;
              *(_BYTE *)v30 = -16;
              while ( v465 >= 0xFF )
              {
                *v462++ = -1;
                v465 -= 255LL;
              }
              *v462++ = v465;
            }
            v466 = (__int64 *)v1120;
            v467 = &v462[v464];
            do
            {
              v468 = *v466++;
              *(_QWORD *)v462 = v468;
              v462 += 8;
            }
            while ( v462 < (_BYTE *)v467 );
            *v467 = v1031;
            v30 = (__int64)(v467 + 1);
            v1079 = HIDWORD(v30);
            v469 = v388 - 4LL;
            if ( a7 && v30 + v469 / 0xFF + 6 > v1089 )
              goto LABEL_931;
            v470 = *v463;
            if ( v469 < 0xF )
            {
              *v463 = v470 + v469;
            }
            else
            {
              *v463 = v470 + 15;
              for ( i8 = v388 - 19LL; i8 >= 0x1FE; i8 -= 510LL )
              {
                *(_BYTE *)v30 = -1;
                v502 = (_BYTE *)(v30 + 1);
                *v502 = -1;
                v30 = (__int64)(v502 + 1);
              }
              if ( i8 >= 0xFF )
              {
                LOBYTE(i8) = i8 + 1;
                *(_BYTE *)v30++ = -1;
              }
              *(_BYTE *)v30++ = i8;
              v1079 = HIDWORD(v30);
            }
            v301 = (_DWORD *)v1076;
            v372 = v380;
            v1120 = (char *)v1045 + v388;
            v381 = v1146;
            v1076 = v1146;
            v1045 = v301;
            LOWORD(v1031) = v1049;
            v1207 = v380;
LABEL_866:
            v1049 = v384;
            v380 = v385;
            v376 = v1144;
            v1018 = v385;
            continue;
          }
          if ( v1146 < v387 )
          {
            v381 = v1146;
            v1076 = v1146;
            goto LABEL_866;
          }
          if ( v381 >= v387 )
            goto LABEL_2071;
          v401 = v372 + (_DWORD)v301 - v381;
          v380 -= v401;
          if ( v380 >= 4 )
          {
            v1076 = v401 + v381;
LABEL_2071:
            v402 = v1049;
            goto LABEL_716;
          }
          v1076 = v1146;
          v402 = v384;
          v380 = v385;
LABEL_716:
          v403 = (_BYTE *)(v30 + 1);
          v393 = v30;
          v391 = v30 >> 32;
          v404 = (char *)v30;
          v405 = (char *)v1045 - v1120;
          if ( a7 && (unsigned __int64)&v403[v405 / 0xFF + 8 + v405] > v1089 )
          {
            v27 = v1120;
LABEL_2078:
            v301 = v1045;
            v31 = v1089;
LABEL_917:
            v440 = v1031;
            goto LABEL_939;
          }
          if ( v405 < 0xF )
          {
            *(_BYTE *)v30 = 16 * v405;
          }
          else
          {
            v406 = v405 - 15;
            *(_BYTE *)v30 = -16;
            while ( v406 >= 0xFF )
            {
              *v403++ = -1;
              v406 -= 255LL;
            }
            *v403++ = v406;
          }
          v407 = (__int64 *)v1120;
          v408 = &v403[v405];
          do
          {
            v409 = *v407++;
            *(_QWORD *)v403 = v409;
            v403 += 8;
          }
          while ( v403 < (_BYTE *)v408 );
          v410 = v386 - 4;
          *v408 = v1031;
          v30 = (__int64)(v408 + 1);
          v1079 = HIDWORD(v30);
          if ( a7 && v30 + v410 / 0xFF + 6 > v1089 )
          {
LABEL_931:
            v27 = v1120;
            goto LABEL_2078;
          }
          v411 = *v404;
          if ( v410 < 0xF )
          {
            *v404 = v411 + v410;
          }
          else
          {
            *v404 = v411 + 15;
            for ( i9 = v386 - 19; i9 >= 0x1FE; i9 -= 510LL )
            {
              *(_BYTE *)v30 = -1;
              v963 = (_BYTE *)(v30 + 1);
              *v963 = -1;
              v30 = (__int64)(v963 + 1);
            }
            if ( i9 >= 0xFF )
            {
              LOBYTE(i9) = i9 + 1;
              *(_BYTE *)v30++ = -1;
            }
            *(_BYTE *)v30++ = i9;
            v1079 = HIDWORD(v30);
          }
          v372 = v385;
          v374 = (_DWORD *)v1076;
          v301 = (_DWORD *)v1146;
          v1045 = (_DWORD *)v1146;
          v373 = v402;
          v1207 = v385;
          LODWORD(v375) = v380;
          v1120 = (char *)v387;
          LOWORD(v1031) = v384;
          goto LABEL_686;
        }
        break;
      }
      if ( v381 >= (unsigned __int64)v301 + v372 )
      {
        v389 = v1207;
      }
      else
      {
        v389 = v381 - (_DWORD)v301;
        v1207 = v381 - (_DWORD)v301;
      }
      v27 = v1120;
      v390 = (_BYTE *)(v30 + 1);
      v31 = v1089;
      v391 = v30 >> 32;
      v392 = (char *)v301 - v1120;
      v393 = v30;
      if ( a7 && (unsigned __int64)&v390[v392 + 8 + v392 / 0xFF] > v1089 )
        goto LABEL_917;
      if ( v392 < 0xF )
      {
        *(_BYTE *)v30 = 16 * v392;
      }
      else
      {
        v394 = v392 - 15;
        *(_BYTE *)v30 = -16;
        while ( v394 >= 0xFF )
        {
          *v390++ = -1;
          v394 -= 255LL;
        }
        *v390++ = v394;
      }
      v395 = (__int64 *)v1120;
      v396 = &v390[v392];
      do
      {
        v397 = *v395++;
        *(_QWORD *)v390 = v397;
        v390 += 8;
      }
      while ( v390 < (_BYTE *)v396 );
      v398 = (__int64)(v396 + 1);
      *v396 = v1031;
      v399 = v389 - 4LL;
      if ( a7 && v398 + v399 / 0xFF + 6 > v1089 )
      {
        v301 = v1045;
        goto LABEL_917;
      }
      v400 = *(_BYTE *)v30;
      if ( v399 >= 0xF )
      {
        *(_BYTE *)v30 = v400 + 15;
        for ( i10 = v389 - 19LL; i10 >= 0x1FE; i10 -= 510LL )
        {
          *(_BYTE *)v398 = -1;
          v492 = (_BYTE *)(v398 + 1);
          *v492 = -1;
          v398 = (__int64)(v492 + 1);
        }
        if ( i10 >= 0xFF )
        {
          LOBYTE(i10) = i10 + 1;
          *(_BYTE *)v398++ = -1;
        }
        *(_BYTE *)v398++ = i10;
      }
      else
      {
        *(_BYTE *)v30 = v400 + v399;
      }
      v452 = (_BYTE *)(v398 + 1);
      v27 = (char *)v1045 + v389;
      v1045 = (_DWORD *)v1076;
      v453 = v1076 - (_QWORD)v27;
      v391 = v398 >> 32;
      v393 = v398;
      if ( a7 && (unsigned __int64)&v452[v453 / 0xFF + 8 + v453] > v1089 )
      {
        v440 = v1049;
LABEL_922:
        v301 = (_DWORD *)v1076;
        v499 = v380;
        goto LABEL_940;
      }
      if ( v453 < 0xF )
      {
        *(_BYTE *)v398 = 16 * v453;
      }
      else
      {
        v454 = v453 - 15;
        *(_BYTE *)v398 = -16;
        while ( v454 >= 0xFF )
        {
          *v452++ = -1;
          v454 -= 255LL;
        }
        *v452++ = v454;
      }
      v455 = (__int64 *)v27;
      v456 = &v452[v453];
      do
      {
        v457 = *v455++;
        *(_QWORD *)v452 = v457;
        v452 += 8;
      }
      while ( v452 < (_BYTE *)v456 );
      v440 = v1049;
      v458 = v382 - 4;
      *v456 = v1049;
      v30 = (__int64)(v456 + 1);
      v1092 = v30;
      v1079 = HIDWORD(v30);
      if ( a7 && v30 + v458 / 0xFF + 6 > v1089 )
        goto LABEL_922;
      v459 = *(_BYTE *)v398;
      if ( v458 < 0xF )
      {
        *(_BYTE *)v398 = v459 + v458;
      }
      else
      {
        *(_BYTE *)v398 = v459 + 15;
        for ( i11 = v382 - 19; i11 >= 0x1FE; i11 -= 510LL )
        {
          *(_BYTE *)v30 = -1;
          v493 = (_BYTE *)(v30 + 1);
          *v493 = -1;
          v30 = (__int64)(v493 + 1);
        }
        if ( i11 >= 0xFF )
        {
          LOBYTE(i11) = i11 + 1;
          *(_BYTE *)v30++ = -1;
        }
        *(_BYTE *)v30++ = i11;
        v1092 = v30;
        v1079 = HIDWORD(v30);
      }
      v290 = v1144;
      v26 = v383;
      v13 = a1;
      v27 = (char *)v383;
      v1045 = v383;
      v1120 = (char *)v383;
    }
  }
  if ( a7 == 2 && a5 < 1 || *a4 > 0x7E000000 )
    return v7;
  v259 = a2;
  v1047 = (unsigned __int64)a2;
  *(_QWORD *)(a1 + 0x40000) = v10 + (int)*a4;
  v27 = (char *)a2;
  v260 = (int)*a4;
  v261 = a3 + a5;
  v1143 = (char *)a2;
  v262 = (char *)a2 + v260;
  v1121 = a3;
  v30 = a3;
  v1080 = HIDWORD(a3);
  v263 = v261 - 5;
  *a4 = 0;
  if ( a7 != 2 )
    v263 = v261;
  v1186 = v262;
  v1090 = v263;
  v264 = 0x8080808080808081uLL;
  if ( (int)v260 < 13 )
    goto LABEL_375;
  v614 = (unsigned __int64)(v262 - 12);
  v1077 = 0;
  v1106 = (unsigned __int64)(v262 - 12);
  v1062 = (unsigned __int64)(v262 - 5);
  v1147 = 0;
LABEL_1237:
  while ( 2 )
  {
    if ( (unsigned __int64)v259 > v614 )
    {
      v262 = v1186;
LABEL_375:
      v265 = v262 - v27;
      v33 = v265;
      if ( a7 == 2 )
        goto LABEL_376;
      if ( a7 )
        goto LABEL_377;
      goto LABEL_1863;
    }
    v615 = *(_QWORD *)(v13 + 262184);
    v616 = 256;
    v617 = *(_QWORD **)(v13 + 262152);
    v618 = *(unsigned int *)(v13 + 262168);
    v619 = *v259;
    v620 = v618 + (_DWORD)v259 - (_DWORD)v617;
    v1181 = v615;
    v1208 = 3;
    v621 = *(unsigned int *)(a1 + 262172);
    v1097 = v617;
    v622 = v621;
    v1072 = v620;
    v1128 = *(_DWORD *)(a1 + 262172);
    v1027 = 256;
    v1050 = *v259;
    v623 = *(_DWORD *)(a1 + 262176);
    if ( (int)v621 + 0x10000 <= v620 )
      v622 = v620 - 0xFFFF;
    v1171 = *(_QWORD **)(a1 + 262160);
    v1137 = v622;
    v1178 = 0;
    v1152 = (_DWORD *)((char *)v1171 + v618 - v621);
    v1032 = 0;
    if ( v623 < v620 )
    {
      do
      {
        v1008 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v617 + v623 - v618)) >> 17;
        v1009 = v623 - *(_DWORD *)(a1 + 4 * v1008);
        if ( v1009 > 0xFFFF )
          LOWORD(v1009) = -1;
        *(_WORD *)(a1 + 2LL * (unsigned __int16)v623 + 0x20000) = v1009;
        *(_DWORD *)(a1 + 4 * v1008) = v623++;
      }
      while ( v623 < v620 );
      v619 = v1050;
      LODWORD(v621) = v1128;
    }
    *(_DWORD *)(a1 + 262176) = v620;
    v624 = (unsigned __int64)(-1640531535 * *v259) >> 17;
    v1160 = v624;
    v625 = *(_DWORD *)(a1 + 4 * v624);
    if ( v625 < v622 )
      goto LABEL_1259;
    while ( 1 )
    {
      v626 = v616 <= 0;
      if ( v616 <= 0 )
        break;
      v1027 = v616 - 1;
      if ( v625 < (unsigned int)v618 )
      {
        if ( v625 <= (int)v618 - 4 && *(_DWORD *)((char *)v1171 + v625 - (unsigned int)v621) == v619 )
        {
          v687 = (_QWORD *)(v1047 + 4);
          v264 = v1047 + (unsigned int)v618 - v625;
          if ( v264 > v1062 )
            v264 = v1062;
          v688 = (_QWORD *)((char *)v1171 + v625 - (unsigned int)v621 + 4);
          v689 = (_QWORD *)(v1047 + 4);
          if ( (unsigned __int64)v687 >= v264 - 7 )
          {
            while ( (unsigned __int64)v689 < v264 - 7 )
            {
              if ( *v688 != *v689 )
              {
                __asm { tzcnt   r10, rax }
                v693 = (_DWORD)v689 + ((unsigned int)_R10 >> 3) - (_DWORD)v687;
                goto LABEL_1371;
              }
              ++v689;
LABEL_1321:
              ++v688;
            }
            if ( (unsigned __int64)v689 < v264 - 3 && *(_DWORD *)v688 == *(_DWORD *)v689 )
            {
              v689 = (_QWORD *)((char *)v689 + 4);
              v688 = (_QWORD *)((char *)v688 + 4);
            }
            if ( (unsigned __int64)v689 < v264 - 1 && *(_WORD *)v688 == *(_WORD *)v689 )
            {
              v689 = (_QWORD *)((char *)v689 + 2);
              v688 = (_QWORD *)((char *)v688 + 2);
            }
            if ( (unsigned __int64)v689 < v264 && *(_BYTE *)v688 == *(_BYTE *)v689 )
              LODWORD(v689) = (_DWORD)v689 + 1;
            v693 = (_DWORD)v689 - (_DWORD)v687;
          }
          else
          {
            if ( *v687 == *v688 )
            {
              v689 = (_QWORD *)(v1047 + 12);
              goto LABEL_1321;
            }
            __asm { tzcnt   r10, rax }
            v693 = (unsigned int)_R10 >> 3;
          }
LABEL_1371:
          v716 = v693 + 4;
          v717 = (_QWORD *)(v1047 + v693 + 4LL);
          if ( v717 == (_QWORD *)v264 && v264 < v1062 )
          {
            v264 = v1062 - 7;
            v718 = (_QWORD *)(v1047 + v693 + 4LL);
            if ( (unsigned __int64)v717 >= v1062 - 7 )
            {
              v720 = v617;
LABEL_1376:
              while ( (unsigned __int64)v718 < v264 )
              {
                if ( *v720 != *v718 )
                {
                  __asm { tzcnt   rax, rax }
                  v722 = ((unsigned int)_RAX >> 3) - (_DWORD)v717 + (_DWORD)v718;
                  goto LABEL_1915;
                }
                ++v718;
                ++v720;
              }
              v264 = v1062;
              if ( (unsigned __int64)v718 < v1062 - 3 && *(_DWORD *)v720 == *(_DWORD *)v718 )
              {
                v718 = (_QWORD *)((char *)v718 + 4);
                v720 = (_QWORD *)((char *)v720 + 4);
              }
              if ( (unsigned __int64)v718 < v1062 - 1 && *(_WORD *)v720 == *(_WORD *)v718 )
              {
                v718 = (_QWORD *)((char *)v718 + 2);
                v720 = (_QWORD *)((char *)v720 + 2);
              }
              if ( (unsigned __int64)v718 < v1062 && *(_BYTE *)v720 == *(_BYTE *)v718 )
                LODWORD(v718) = (_DWORD)v718 + 1;
              v722 = (_DWORD)v718 - (_DWORD)v717;
            }
            else
            {
              if ( *v717 == *v617 )
              {
                v718 = v717 + 1;
                v720 = v617 + 1;
                goto LABEL_1376;
              }
              __asm { tzcnt   rcx, rax }
              v722 = (unsigned int)_RCX >> 3;
            }
LABEL_1915:
            v716 = v693 + v722 + 4;
          }
          v619 = v1050;
          if ( v716 > v1208 )
          {
            v1208 = v716;
            v1032 = v620 - v625;
          }
        }
      }
      else
      {
        v627 = v625 - (unsigned int)v618;
        if ( *(_WORD *)(v1047 + v1208 - 1) == *(_WORD *)((char *)v617 + v1208 + v627 - 1)
          && *(_DWORD *)((char *)v617 + v627) == v619 )
        {
          v628 = v627 + 4;
          v629 = (_QWORD *)(v1047 + 4);
          v630 = (_QWORD *)((char *)v617 + v628);
          v264 = v1062 - 7;
          v631 = (_QWORD *)(v1047 + 4);
          if ( v1047 + 4 >= v1062 - 7 )
          {
            while ( (unsigned __int64)v631 < v264 )
            {
              if ( *v630 != *v631 )
              {
                __asm { tzcnt   rax, rax }
                v686 = ((unsigned int)_RAX >> 3) - (_DWORD)v629 + (_DWORD)v631;
                goto LABEL_1326;
              }
              ++v631;
LABEL_1249:
              ++v630;
            }
            v264 = v1062;
            if ( (unsigned __int64)v631 < v1062 - 3 && *(_DWORD *)v630 == *(_DWORD *)v631 )
            {
              v631 = (_QWORD *)((char *)v631 + 4);
              v630 = (_QWORD *)((char *)v630 + 4);
            }
            if ( (unsigned __int64)v631 < v1062 - 1 && *(_WORD *)v630 == *(_WORD *)v631 )
            {
              v631 = (_QWORD *)((char *)v631 + 2);
              v630 = (_QWORD *)((char *)v630 + 2);
            }
            if ( (unsigned __int64)v631 < v1062 && *(_BYTE *)v630 == *(_BYTE *)v631 )
              LODWORD(v631) = (_DWORD)v631 + 1;
            v686 = (_DWORD)v631 - (_DWORD)v629;
          }
          else
          {
            if ( *v629 == *v630 )
            {
              v631 = (_QWORD *)(v1047 + 12);
              goto LABEL_1249;
            }
            __asm { tzcnt   rcx, rax }
            v686 = (unsigned int)_RCX >> 3;
          }
LABEL_1326:
          v695 = v686 + 4;
          if ( v695 > v1208 )
          {
            v1208 = v695;
            v1032 = v620 - v625;
          }
        }
      }
      if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v625 + 0x20000) != 1 )
        goto LABEL_1359;
      if ( v7 )
      {
        if ( v7 != 2 )
          goto LABEL_1359;
      }
      else
      {
        if ( (_BYTE)v619 != HIBYTE(v619) || (unsigned __int16)v619 != HIWORD(v619) )
        {
          v7 = 1;
LABEL_1359:
          v625 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v625 + 0x20000);
          goto LABEL_1255;
        }
        v7 = 2;
        v264 = (unsigned int)LZ4HC_countPattern(v1047 + 4, v1062, v619, v264) + 4LL;
        v1178 = v264;
      }
      v696 = v625 - 1;
      if ( v625 - 1 < v622 || (unsigned int)v618 - v625 < 3 )
        goto LABEL_1359;
      if ( v696 >= (unsigned int)v618 )
      {
        v697 = 0;
        v698 = (_DWORD *)((char *)v617 + v696 - (unsigned int)v618);
      }
      else
      {
        v697 = 1;
        v698 = (_DWORD *)((char *)v1171 + v696 - v1128);
      }
      if ( *v698 != v1050 )
      {
        v622 = v1137;
        goto LABEL_1359;
      }
      v699 = (_DWORD *)v1062;
      if ( v697 )
        v699 = v1152;
      v700 = (unsigned int)LZ4HC_countPattern(v698 + 1, v699, v1050, v264) + 4LL;
      if ( v697 )
      {
        if ( (_DWORD *)((char *)v698 + v700) == v699 )
        {
          v701 = LZ4HC_rotatePattern(v700, v1050);
          v617 = v1097;
          v700 += (unsigned int)LZ4HC_countPattern(v1097, v1062, v701, v702);
        }
        else
        {
          v617 = v1097;
        }
        v703 = v1171;
      }
      else
      {
        v617 = v1097;
        v703 = v1097;
      }
      v704 = LZ4HC_reverseCountPattern(v698, v703, v1050);
      v706 = v704;
      if ( !v697 && (_QWORD *)((char *)v698 - v704) == v617 && v1128 < (unsigned int)v618 )
      {
        v707 = LZ4HC_rotatePattern(-v704, v705);
        v708 = LZ4HC_reverseCountPattern(v1152, v1171, v707);
        v706 = v708 + v709;
      }
      v622 = v1137;
      v264 = v1178;
      v710 = v696 - v706;
      v711 = v1137;
      if ( v710 > v1137 )
        v711 = v710;
      v712 = v700 + v696 - v711;
      if ( v712 < v1178 || v700 > v1178 )
      {
        if ( (unsigned int)v618 - v711 - 1 < 3 )
        {
          v625 = v618;
        }
        else
        {
          v620 = v1072;
          v713 = v1178;
          if ( v712 < v1178 )
            v713 = v700 + v696 - v711;
          if ( v1208 < v713 )
          {
            if ( v618 + v1047 - v711 - (unsigned __int64)v617 > 0xFFFF )
              goto LABEL_1357;
            v1208 = v713;
            v1032 = v1072 - v711;
          }
          v714 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v711 + 0x20000);
          if ( v714 > v711 )
          {
LABEL_1357:
            v616 = v1027;
            v619 = v1050;
LABEL_1256:
            v626 = v616 <= 0;
            break;
          }
          v625 = v711 - v714;
        }
      }
      else
      {
        v625 = v618;
        if ( (unsigned int)v618 - ((_DWORD)v700 - (_DWORD)v1178 + v696) - 1 >= 3 )
          v625 = v700 - v1178 + v696;
      }
      v7 = 2;
LABEL_1255:
      v619 = v1050;
      v620 = v1072;
      LODWORD(v621) = v1128;
      v616 = v1027;
      if ( v625 < v622 )
        goto LABEL_1256;
    }
    v30 = v1121;
    if ( !v626 )
    {
      v624 = v1160;
LABEL_1259:
      if ( v620 - v622 < 0xFFFF )
      {
        v634 = *(_QWORD *)(v1181 + 262152);
        v635 = *(unsigned int *)(v1181 + 262168);
        v636 = *(_DWORD *)(v1181 + 4 * v624);
        v637 = v635 + *(_QWORD *)(v1181 + 0x40000) - v634;
        v638 = v622 + v636 - v637;
        if ( v1072 - v638 <= 0xFFFF )
        {
          v639 = v1027;
          do
          {
            if ( !v639 )
              break;
            --v639;
            if ( *(_DWORD *)(v634 - v635 + v636) == v619 )
            {
              v640 = v1047 + v637 - v636;
              if ( v640 > v1062 )
                v640 = v1062;
              v641 = (_QWORD *)(v1047 + 4);
              v642 = (_QWORD *)(v634 - v635 + 4 + v636);
              v643 = (_QWORD *)(v1047 + 4);
              if ( v1047 + 4 >= v640 - 7 )
              {
                while ( (unsigned __int64)v643 < v640 - 7 )
                {
                  if ( *v643 != *v642 )
                  {
                    __asm { tzcnt   rax, rax }
                    v646 = ((unsigned int)_RAX >> 3) - (_DWORD)v641 + (_DWORD)v643;
                    goto LABEL_1269;
                  }
                  ++v643;
LABEL_1300:
                  ++v642;
                }
                if ( (unsigned __int64)v643 < v640 - 3 && *(_DWORD *)v642 == *(_DWORD *)v643 )
                {
                  v643 = (_QWORD *)((char *)v643 + 4);
                  v642 = (_QWORD *)((char *)v642 + 4);
                }
                if ( (unsigned __int64)v643 < v640 - 1 && *(_WORD *)v642 == *(_WORD *)v643 )
                {
                  v643 = (_QWORD *)((char *)v643 + 2);
                  v642 = (_QWORD *)((char *)v642 + 2);
                }
                if ( (unsigned __int64)v643 < v640 && *(_BYTE *)v642 == *(_BYTE *)v643 )
                  LODWORD(v643) = (_DWORD)v643 + 1;
                v646 = (_DWORD)v643 - (_DWORD)v641;
              }
              else
              {
                if ( *v641 == *v642 )
                {
                  v643 = (_QWORD *)(v1047 + 12);
                  goto LABEL_1300;
                }
                __asm { tzcnt   rcx, rax }
                v646 = (unsigned int)_RCX >> 3;
              }
LABEL_1269:
              v619 = v1050;
              v647 = v646 + 4;
              if ( v647 > v1208 )
              {
                v1208 = v647;
                v1032 = v1072 - v638;
              }
            }
            v648 = *(unsigned __int16 *)(v1181 + 2LL * (unsigned __int16)v636 + 0x20000);
            v638 -= v648;
            v636 -= v648;
          }
          while ( v1072 - v638 <= 0xFFFF );
          v30 = v1121;
        }
      }
    }
    v649 = v1208;
    if ( v1208 < 4 )
    {
      v27 = v1143;
      v259 = (unsigned int *)(v1047 + 1);
      v263 = v1090;
      ++v1047;
LABEL_1840:
      v614 = v1106;
      v7 = 0;
      v13 = a1;
      v264 = 0x8080808080808081uLL;
      continue;
    }
    break;
  }
  v650 = v1032;
  v651 = v1047;
  v652 = __PAIR64__(v1208, v1032) >> 32;
  v653 = v1047;
LABEL_1275:
  v654 = v1106;
  v1182 = v652;
  v1179 = v653;
  v1098 = v650;
  while ( 1 )
  {
    v655 = v649;
    v1163 = v649;
    v656 = (_DWORD *)(v649 + v651);
    v1194 = v656;
    if ( (unsigned __int64)v656 > v654 )
    {
      v764 = 0;
      v763 = 0;
      v1051 = 0;
      v1036 = 0;
    }
    else
    {
      v657 = (_DWORD)v656 - 2;
      v1077 = (unsigned __int64)v656 - 2;
      v658 = (_DWORD *)((char *)v656 - 2);
      v1129 = (unsigned __int64)v656 - 2;
      v1036 = v649;
      v659 = *(unsigned int *)(a1 + 262172);
      v660 = *(unsigned int *)(a1 + 262168);
      v661 = v659;
      v662 = *(_QWORD **)(a1 + 262152);
      v663 = *(_QWORD *)(a1 + 262184);
      v664 = *(char **)(a1 + 262160);
      v665 = *(_DWORD *)(a1 + 262176);
      v666 = v660 + v657 - (_DWORD)v662;
      v1161 = v663;
      v1138 = (char *)v662;
      v1112 = *(_DWORD *)(a1 + 262168);
      v1028 = v666;
      if ( (int)v659 + 0x10000 <= v666 )
        v661 = v666 - 0xFFFF;
      v1073 = *(_DWORD *)(a1 + 262172);
      v1085 = v661;
      v1058 = (_DWORD)v658 - v1047;
      v1019 = *v658;
      v1117 = *(char **)(a1 + 262160);
      v1153 = *(unsigned int *)(a1 + 262168);
      v1042 = 256;
      v1051 = 0;
      if ( v665 < v666 )
      {
        v1010 = *(unsigned int *)(a1 + 262168);
        do
        {
          v1011 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v662 + v665 - v1010)) >> 17;
          v1012 = v665 - *(_DWORD *)(a1 + 4 * v1011);
          if ( v1012 > 0xFFFF )
            LOWORD(v1012) = -1;
          *(_WORD *)(a1 + 2LL * (unsigned __int16)v665 + 0x20000) = v1012;
          *(_DWORD *)(a1 + 4 * v1011) = v665++;
        }
        while ( v665 < v666 );
        v650 = v1098;
        v660 = v1153;
      }
      *(_DWORD *)(a1 + 262176) = v666;
      v667 = (unsigned __int64)(unsigned int)(-1640531535 * *v658) >> 17;
      v1172 = v667;
      v668 = *(_DWORD *)(a1 + 4 * v667);
      if ( v668 >= v661 )
      {
        v669 = v1112;
        v670 = &v664[v660 - v659];
        v671 = 0;
        v1066 = 0;
        v1154 = 0;
        while ( 1 )
        {
          v672 = v1042;
          v673 = v1042 <= 0;
          if ( v1042 <= 0 )
          {
LABEL_1494:
            v650 = v1098;
            v30 = v1121;
            if ( !v673 )
            {
              v667 = v1172;
              v663 = v1161;
              goto LABEL_1496;
            }
            goto LABEL_1497;
          }
          --v1042;
          if ( v668 < v669 )
          {
            v724 = v1019;
            if ( v668 > v669 - 4 )
              goto LABEL_2096;
            v725 = &v664[v668 - (unsigned int)v659];
            if ( *(_DWORD *)v725 != v1019 )
            {
              v664 = v1117;
LABEL_2096:
              v679 = v1062;
              goto LABEL_1467;
            }
            v726 = v658 + 1;
            v727 = (_QWORD *)((char *)v658 + v669 - v668);
            v728 = v725 + 4;
            v729 = v658 + 1;
            if ( (unsigned __int64)v727 > v1062 )
              v727 = (_QWORD *)v1062;
            if ( v726 >= (_QWORD *)((char *)v727 - 7) )
            {
              while ( v729 < (_QWORD *)((char *)v727 - 7) )
              {
                if ( *v728 != *v729 )
                {
                  __asm { tzcnt   rsi, rax }
                  v732 = (_DWORD)v729 + ((unsigned int)_RSI >> 3) - (_DWORD)v726;
                  goto LABEL_1435;
                }
                ++v729;
LABEL_1420:
                ++v728;
              }
              if ( v729 < (_QWORD *)((char *)v727 - 3) && *(_DWORD *)v728 == *(_DWORD *)v729 )
              {
                v729 = (_QWORD *)((char *)v729 + 4);
                v728 = (_QWORD *)((char *)v728 + 4);
              }
              if ( v729 < (_QWORD *)((char *)v727 - 1) && *(_WORD *)v728 == *(_WORD *)v729 )
              {
                v729 = (_QWORD *)((char *)v729 + 2);
                v728 = (_QWORD *)((char *)v728 + 2);
              }
              if ( v729 < v727 && *(_BYTE *)v728 == *(_BYTE *)v729 )
                LODWORD(v729) = (_DWORD)v729 + 1;
              v732 = (_DWORD)v729 - (_DWORD)v726;
            }
            else
            {
              if ( *v728 == *v726 )
              {
                v729 = v658 + 3;
                goto LABEL_1420;
              }
              __asm { tzcnt   rsi, rax }
              v732 = (unsigned int)_RSI >> 3;
            }
LABEL_1435:
            v734 = v732 + 4;
            v735 = (_QWORD *)((char *)v658 + v732 + 4);
            if ( v735 == v727 && (unsigned __int64)v727 < v1062 )
            {
              v736 = (_QWORD *)((char *)v658 + v732 + 4);
              if ( (unsigned __int64)v735 >= v1062 - 7 )
              {
                v738 = v662;
LABEL_1440:
                while ( (unsigned __int64)v736 < v1062 - 7 )
                {
                  if ( *v738 != *v736 )
                  {
                    __asm { tzcnt   rax, rax }
                    v740 = ((unsigned int)_RAX >> 3) - (_DWORD)v735 + (_DWORD)v736;
                    goto LABEL_1454;
                  }
                  ++v736;
                  ++v738;
                }
                if ( (unsigned __int64)v736 < v1062 - 3 && *(_DWORD *)v738 == *(_DWORD *)v736 )
                {
                  v736 = (_QWORD *)((char *)v736 + 4);
                  v738 = (_QWORD *)((char *)v738 + 4);
                }
                if ( (unsigned __int64)v736 < v1062 - 1 && *(_WORD *)v738 == *(_WORD *)v736 )
                {
                  v736 = (_QWORD *)((char *)v736 + 2);
                  v738 = (_QWORD *)((char *)v738 + 2);
                }
                if ( (unsigned __int64)v736 < v1062 && *(_BYTE *)v738 == *(_BYTE *)v736 )
                  LODWORD(v736) = (_DWORD)v736 + 1;
                v740 = (_DWORD)v736 - (_DWORD)v735;
              }
              else
              {
                if ( *v662 == *v735 )
                {
                  v736 = v735 + 1;
                  v738 = v662 + 1;
                  goto LABEL_1440;
                }
                __asm { tzcnt   rcx, rax }
                v740 = (unsigned int)_RCX >> 3;
              }
LABEL_1454:
              v734 = v732 + v740 + 4;
            }
            v742 = 0;
            if ( v1058 )
            {
              v743 = v1047 - (_DWORD)v658;
              if ( (__int64)(v1047 - (_QWORD)v658) <= v1117 - v725 )
                v743 = (_DWORD)v1117 - (_DWORD)v725;
              while ( v742 - v743 > 3 )
              {
                if ( *(_DWORD *)&v725[v742 - 4] != *(_DWORD *)((char *)v658 + v742 - 4) )
                {
                  _BitScanReverse(&v744, *(_DWORD *)&v725[v742 - 4] ^ *(_DWORD *)((char *)v658 + v742 - 4));
                  v742 -= (31 - v744) >> 3;
                  goto LABEL_1461;
                }
                v742 -= 4;
              }
              if ( v742 > v743 )
              {
                do
                {
                  if ( *((_BYTE *)v658 + v742 - 1) != v725[v742 - 1] )
                    break;
                  --v742;
                }
                while ( v742 > v743 );
                v669 = v1112;
              }
            }
LABEL_1461:
            v671 = v1066;
            v745 = v734 - v742;
            v664 = v1117;
            LODWORD(v659) = v1073;
            v724 = v1019;
            v679 = v1062;
            if ( v745 > v1036 )
            {
              v1036 = v745;
              v1051 = v1028 - v668;
              v1077 = (unsigned __int64)v658 + v742;
            }
            v661 = v1085;
          }
          else
          {
            v674 = (_DWORD *)((char *)v662 + v668 - v669);
            if ( *(_WORD *)(v1036 + v1047 - 1) != *(_WORD *)((char *)v674 + v1036 - (__int64)v1058 - 1)
              || *v674 != v1019 )
            {
              v724 = v1019;
              goto LABEL_2096;
            }
            v675 = 0;
            if ( v1058 )
            {
              v676 = v1047 - (_DWORD)v658;
              v677 = -(__int64)(v668 - v669);
              if ( (__int64)(v1047 - (_QWORD)v658) <= v677 )
                v676 = v677;
              while ( v675 - v676 > 3 )
              {
                if ( *(_DWORD *)((char *)v658 + v675 - 4) != *(_DWORD *)((char *)v674 + v675 - 4) )
                {
                  _BitScanReverse(&v678, *(_DWORD *)((char *)v658 + v675 - 4) ^ *(_DWORD *)((char *)v674 + v675 - 4));
                  v675 -= (31 - v678) >> 3;
                  goto LABEL_1292;
                }
                v675 -= 4;
              }
              if ( v675 > v676 )
              {
                do
                {
                  if ( *((_BYTE *)v658 + v675 - 1) != *((_BYTE *)v674 + v675 - 1) )
                    break;
                  --v675;
                }
                while ( v675 > v676 );
                LODWORD(v659) = v1073;
              }
            }
LABEL_1292:
            v679 = v1062;
            v680 = v658 + 1;
            v681 = v674 + 1;
            v682 = v658 + 1;
            if ( (unsigned __int64)(v658 + 1) >= v1062 - 7 )
            {
              while ( (unsigned __int64)v682 < v1062 - 7 )
              {
                if ( *v681 != *v682 )
                {
                  __asm { tzcnt   rax, rax }
                  v723 = ((unsigned int)_RAX >> 3) - (_DWORD)v680 + (_DWORD)v682;
                  goto LABEL_1465;
                }
                ++v682;
LABEL_1295:
                ++v681;
              }
              if ( (unsigned __int64)v682 < v1062 - 3 && *(_DWORD *)v681 == *(_DWORD *)v682 )
              {
                v682 = (_QWORD *)((char *)v682 + 4);
                v681 = (_QWORD *)((char *)v681 + 4);
              }
              if ( (unsigned __int64)v682 < v1062 - 1 && *(_WORD *)v681 == *(_WORD *)v682 )
              {
                v682 = (_QWORD *)((char *)v682 + 2);
                v681 = (_QWORD *)((char *)v681 + 2);
              }
              if ( (unsigned __int64)v682 < v1062 && *(_BYTE *)v681 == *(_BYTE *)v682 )
                LODWORD(v682) = (_DWORD)v682 + 1;
              v723 = (_DWORD)v682 - (_DWORD)v680;
            }
            else
            {
              if ( *v681 == *v680 )
              {
                v682 = v658 + 3;
                goto LABEL_1295;
              }
              __asm { tzcnt   rcx, rax }
              v723 = (unsigned int)_RCX >> 3;
            }
LABEL_1465:
            v661 = v1085;
            v724 = v1019;
            v747 = v723 - v675 + 4;
            if ( v747 > v1036 )
            {
              v1036 = v747;
              v1051 = v1028 - v668;
              v1077 = (unsigned __int64)v658 + v675;
            }
          }
LABEL_1467:
          if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v668 + 0x20000) != 1 )
            goto LABEL_1512;
          if ( v671 )
          {
            v1066 = v671;
            if ( v671 != 2 )
              goto LABEL_1512;
          }
          else
          {
            if ( (_BYTE)v724 != BYTE3(v724) || (unsigned __int16)v724 != WORD1(v724) )
            {
              v671 = 1;
              v1066 = 1;
LABEL_1512:
              v668 -= *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v668 + 0x20000);
              goto LABEL_1492;
            }
            v671 = 2;
            v1066 = 2;
            v748 = LZ4HC_countPattern(v658 + 1, v679, (unsigned int)v724, v724);
            v661 = v1085;
            v724 = v748 + 4LL;
            v1154 = v724;
          }
          v749 = v668 - 1;
          if ( v668 - 1 < v661 || v669 - v668 < 3 )
            goto LABEL_1512;
          if ( v749 >= v669 )
          {
            v750 = 0;
            v751 = &v1138[v749 - v669];
          }
          else
          {
            v750 = 1;
            v751 = &v664[v749 - (unsigned int)v659];
          }
          if ( *(_DWORD *)v751 != v1019 )
            goto LABEL_1512;
          v752 = (char *)v1062;
          if ( v750 )
            v752 = v670;
          v753 = (unsigned int)LZ4HC_countPattern(v751 + 4, v752, v1019, v724) + 4LL;
          if ( v750 )
          {
            if ( &v751[v753] == v752 )
            {
              v754 = LZ4HC_rotatePattern(v753, v1019);
              v753 += (unsigned int)LZ4HC_countPattern(v1138, v1062, v754, v755);
            }
            v756 = v1117;
            v757 = v1117;
          }
          else
          {
            v757 = v1138;
            v756 = v1117;
          }
          v758 = LZ4HC_reverseCountPattern(v751, v757, v1019);
          v759 = v1138;
          v760 = v758;
          if ( !v750 && &v751[-v758] == v1138 && v1073 < v669 )
          {
            v761 = LZ4HC_rotatePattern(-v758, v1019);
            v760 += LZ4HC_reverseCountPattern(v670, v756, v761);
            v759 = v1138;
          }
          v661 = v1085;
          v668 = v1085;
          if ( v749 - v760 > v1085 )
            v668 = v749 - v760;
          v762 = v753 + v749 - v668;
          if ( v762 < v1154 || v753 > v1154 )
          {
            if ( v669 - v668 - 1 >= 3 )
            {
              if ( !v1058 )
              {
                v778 = v1154;
                v666 = v1028;
                if ( v762 < v1154 )
                  v778 = v753 + v749 - v668;
                if ( v1036 < v778 )
                {
                  if ( v669 + v1129 - v668 - (unsigned __int64)v759 > 0xFFFF )
                    goto LABEL_1493;
                  v1036 = v778;
                  v1077 = v1129;
                  v1051 = v1028 - v668;
                }
                v779 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v668 + 0x20000);
                if ( v779 > v668 )
                {
LABEL_1493:
                  v672 = v1042;
                  v673 = v1042 <= 0;
                  goto LABEL_1494;
                }
                v668 -= v779;
              }
            }
            else
            {
              v668 = v669;
            }
          }
          else
          {
            v668 = v669;
            if ( v669 - ((_DWORD)v753 - (_DWORD)v1154 + v749) - 1 >= 3 )
              v668 = v753 - v1154 + v749;
          }
          v671 = 2;
LABEL_1492:
          v662 = v1138;
          v664 = v1117;
          LODWORD(v659) = v1073;
          v658 = (_DWORD *)v1129;
          v666 = v1028;
          if ( v668 < v661 )
            goto LABEL_1493;
        }
      }
      v672 = 256;
LABEL_1496:
      if ( v666 - v661 < 0xFFFF )
      {
        v780 = *(_QWORD *)(v663 + 262152);
        v781 = *(unsigned int *)(v663 + 262168);
        v782 = *(_QWORD *)(v663 + 0x40000) - v780;
        v783 = *(_DWORD *)(v663 + 4 * v667);
        v784 = v781 + v782;
        v785 = v783 + v661 - v784;
        v1086 = v785;
        if ( v666 - v785 <= 0xFFFF )
        {
          v786 = v1019;
          do
          {
            if ( !v672 )
              break;
            v1043 = --v672;
            v787 = (_DWORD *)(v783 + v780 - v781);
            if ( *v787 == v786 )
            {
              v788 = (_QWORD *)(v1129 + 4);
              v789 = v784 + v1129 - v783;
              v790 = v787 + 1;
              v791 = (_QWORD *)(v1129 + 4);
              if ( v789 > v1062 )
                v789 = v1062;
              if ( (unsigned __int64)v788 >= v789 - 7 )
              {
                while ( (unsigned __int64)v791 < v789 - 7 )
                {
                  if ( *v790 != *v791 )
                  {
                    __asm { tzcnt   rax, rax }
                    v794 = ((unsigned int)_RAX >> 3) - (_DWORD)v788 + (_DWORD)v791;
                    goto LABEL_1550;
                  }
                  ++v791;
LABEL_1535:
                  ++v790;
                }
                if ( (unsigned __int64)v791 < v789 - 3 && *(_DWORD *)v790 == *(_DWORD *)v791 )
                {
                  v791 = (_QWORD *)((char *)v791 + 4);
                  v790 = (_QWORD *)((char *)v790 + 4);
                }
                if ( (unsigned __int64)v791 < v789 - 1 && *(_WORD *)v790 == *(_WORD *)v791 )
                {
                  v791 = (_QWORD *)((char *)v791 + 2);
                  v790 = (_QWORD *)((char *)v790 + 2);
                }
                if ( (unsigned __int64)v791 < v789 && *(_BYTE *)v790 == *(_BYTE *)v791 )
                  LODWORD(v791) = (_DWORD)v791 + 1;
                v794 = (_DWORD)v791 - (_DWORD)v788;
              }
              else
              {
                if ( *v790 == *v788 )
                {
                  v791 = (_QWORD *)(v1129 + 12);
                  goto LABEL_1535;
                }
                __asm { tzcnt   rcx, rax }
                v794 = (unsigned int)_RCX >> 3;
              }
LABEL_1550:
              v796 = 0;
              if ( v1058 )
              {
                v797 = v1047 - v1129;
                if ( (__int64)(v1047 - v1129) <= v781 - v783 )
                  v797 = v781 - v783;
                while ( v796 - v797 > 3 )
                {
                  if ( *(_DWORD *)(v796 + v1129 - 4) != *(_DWORD *)((char *)v787 + v796 - 4) )
                  {
                    _BitScanReverse(&v798, *(_DWORD *)(v796 + v1129 - 4) ^ *(_DWORD *)((char *)v787 + v796 - 4));
                    v796 -= (31 - v798) >> 3;
                    goto LABEL_1556;
                  }
                  v796 -= 4;
                }
                if ( v796 > v797 )
                {
                  do
                  {
                    if ( *(_BYTE *)(v796 + v1129 - 1) != *((_BYTE *)v787 + v796 - 1) )
                      break;
                    --v796;
                  }
                  while ( v796 > v797 );
                  v786 = v1019;
                }
              }
LABEL_1556:
              v785 = v1086;
              if ( (int)(v794 + 4 - v796) <= v1036 )
              {
                v666 = v1028;
              }
              else
              {
                v1036 = v794 + 4 - v796;
                v666 = v1028;
                v1051 = v1028 - v1086;
                v1077 = v1129 + v796;
              }
              v672 = v1043;
            }
            v799 = *(unsigned __int16 *)(v1161 + 2LL * (unsigned __int16)v783 + 0x20000);
            v785 -= v799;
            v783 -= v799;
            v1086 = v785;
          }
          while ( v666 - v785 <= 0xFFFF );
          v650 = v1098;
          v30 = v1121;
        }
      }
LABEL_1497:
      LODWORD(v652) = v1182;
      v653 = v1179;
      v656 = v1194;
      v655 = v1163;
      v763 = v1036;
      v651 = v1047;
      v649 = v1208;
      v764 = v1051;
      v654 = v1106;
    }
    if ( v763 <= v649 )
      break;
    v800 = v1077;
    if ( v653 < v651 && v1077 < v651 + (int)v652 )
    {
      v651 = v653;
      v1047 = v653;
      LOWORD(v1032) = v650;
      v649 = v652;
      v1208 = v652;
    }
    if ( (__int64)(v1077 - v651) >= 3 )
    {
      while ( 1 )
      {
        if ( (__int64)(v800 - v651) < 18 )
        {
          v801 = v649;
          if ( v649 > 18 )
            v801 = 18;
          if ( v651 + v801 > v800 + v763 - 4LL )
            v801 = v763 + v800 - v651 - 4;
          v802 = v801 + v651 - v800;
          if ( v802 > 0 )
          {
            v800 += v802;
            v763 -= v802;
            v1077 = v800;
            v1036 = v763;
          }
        }
        v803 = v763;
        v1183 = v763;
        v804 = (_DWORD *)(v800 + v763);
        v1180 = v804;
        if ( (unsigned __int64)v804 > v654 )
        {
          v871 = 0;
          v870 = 0;
        }
        else
        {
          v1067 = v763;
          v805 = (_DWORD *)((char *)v804 - 3);
          v1147 = (unsigned __int64)v804 - 3;
          v1162 = (unsigned __int64)v804 - 3;
          v1059 = 0;
          v806 = *(unsigned int *)(a1 + 262168);
          v807 = *(_DWORD *)(a1 + 262172);
          v808 = *(_QWORD **)(a1 + 262152);
          v809 = v807;
          v810 = *(_QWORD *)(a1 + 262184);
          v811 = *(char **)(a1 + 262160);
          v812 = (_DWORD)v804 - 3 + *(_DWORD *)(a1 + 262168) - (_DWORD)v808;
          v813 = *(_DWORD *)(a1 + 262176);
          v814 = *(_DWORD *)((char *)v804 - 3);
          v1173 = v810;
          v1118 = v808;
          if ( v807 + 0x10000 <= v812 )
            v809 = v812 - 0xFFFF;
          v1113 = *(_DWORD *)(a1 + 262168);
          v1029 = (_DWORD)v804 - 3 + v1113 - (_DWORD)v808;
          v1074 = *(_DWORD *)(a1 + 262172);
          v1130 = v809;
          v1099 = *(_QWORD **)(a1 + 262160);
          v1139 = (_DWORD)v805 - v1077;
          v1087 = 256;
          v1020 = *(_DWORD *)((char *)v804 - 3);
          if ( v813 < v812 )
          {
            v1013 = *(unsigned int *)(a1 + 262168);
            do
            {
              v1014 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v808 + v813 - v1013)) >> 17;
              v1015 = v813 - *(_DWORD *)(a1 + 4 * v1014);
              if ( v1015 > 0xFFFF )
                LOWORD(v1015) = -1;
              *(_WORD *)(a1 + 2LL * (unsigned __int16)v813 + 0x20000) = v1015;
              *(_DWORD *)(a1 + 4 * v1014) = v813++;
            }
            while ( v813 < v812 );
            v807 = v1074;
            v806 = v1113;
          }
          *(_DWORD *)(a1 + 262176) = v812;
          v815 = (unsigned __int64)(unsigned int)(-1640531535 * *v805) >> 17;
          v1195 = v815;
          v816 = *(_DWORD *)(a1 + 4 * v815);
          if ( v816 >= v809 )
          {
            v817 = v1113;
            v1164 = &v811[v806 - v807];
            v818 = 0;
            v1044 = 0;
            v1155 = 0;
            while ( 1 )
            {
              v819 = v1087 <= 0;
              if ( v1087 <= 0 )
              {
LABEL_1693:
                v30 = v1121;
                if ( !v819 )
                {
                  v815 = v1195;
                  v810 = v1173;
                  goto LABEL_1695;
                }
                goto LABEL_1696;
              }
              --v1087;
              if ( v816 < v817 )
              {
                if ( v816 <= v817 - 4 )
                {
                  v831 = &v811[v816 - v807];
                  if ( *(_DWORD *)v831 == v814 )
                  {
                    v832 = v805 + 1;
                    v833 = (_QWORD *)((char *)v805 + v817 - v816);
                    v834 = v831 + 4;
                    v835 = v805 + 1;
                    if ( (unsigned __int64)v833 > v1062 )
                      v833 = (_QWORD *)v1062;
                    if ( v832 >= (_QWORD *)((char *)v833 - 7) )
                    {
                      while ( v835 < (_QWORD *)((char *)v833 - 7) )
                      {
                        if ( *v834 != *v835 )
                        {
                          __asm { tzcnt   rbx, rax }
                          v838 = (_DWORD)v835 + ((unsigned int)_RBX >> 3) - (_DWORD)v832;
                          goto LABEL_1636;
                        }
                        ++v835;
LABEL_1621:
                        ++v834;
                      }
                      if ( v835 < (_QWORD *)((char *)v833 - 3) && *(_DWORD *)v834 == *(_DWORD *)v835 )
                      {
                        v835 = (_QWORD *)((char *)v835 + 4);
                        v834 = (_QWORD *)((char *)v834 + 4);
                      }
                      if ( v835 < (_QWORD *)((char *)v833 - 1) && *(_WORD *)v834 == *(_WORD *)v835 )
                      {
                        v835 = (_QWORD *)((char *)v835 + 2);
                        v834 = (_QWORD *)((char *)v834 + 2);
                      }
                      if ( v835 < v833 && *(_BYTE *)v834 == *(_BYTE *)v835 )
                        LODWORD(v835) = (_DWORD)v835 + 1;
                      v838 = (_DWORD)v835 - (_DWORD)v832;
                    }
                    else
                    {
                      if ( *v832 == *v834 )
                      {
                        v835 = v805 + 3;
                        goto LABEL_1621;
                      }
                      __asm { tzcnt   rbx, rax }
                      v838 = (unsigned int)_RBX >> 3;
                    }
LABEL_1636:
                    v840 = v838 + 4;
                    v841 = (_QWORD *)((char *)v805 + v838 + 4);
                    if ( v841 == v833 && (unsigned __int64)v833 < v1062 )
                    {
                      v842 = (_QWORD *)((char *)v805 + v838 + 4);
                      if ( (unsigned __int64)v841 >= v1062 - 7 )
                      {
                        v844 = v808;
LABEL_1641:
                        while ( (unsigned __int64)v842 < v1062 - 7 )
                        {
                          if ( *v844 != *v842 )
                          {
                            __asm { tzcnt   rax, rax }
                            v846 = ((unsigned int)_RAX >> 3) - (_DWORD)v841 + (_DWORD)v842;
                            goto LABEL_1655;
                          }
                          ++v842;
                          ++v844;
                        }
                        if ( (unsigned __int64)v842 < v1062 - 3 && *(_DWORD *)v844 == *(_DWORD *)v842 )
                        {
                          v842 = (_QWORD *)((char *)v842 + 4);
                          v844 = (_QWORD *)((char *)v844 + 4);
                        }
                        if ( (unsigned __int64)v842 < v1062 - 1 && *(_WORD *)v844 == *(_WORD *)v842 )
                        {
                          v842 = (_QWORD *)((char *)v842 + 2);
                          v844 = (_QWORD *)((char *)v844 + 2);
                        }
                        if ( (unsigned __int64)v842 < v1062 && *(_BYTE *)v844 == *(_BYTE *)v842 )
                          LODWORD(v842) = (_DWORD)v842 + 1;
                        v846 = (_DWORD)v842 - (_DWORD)v841;
                      }
                      else
                      {
                        if ( *v841 == *v808 )
                        {
                          v842 = v841 + 1;
                          v844 = v808 + 1;
                          goto LABEL_1641;
                        }
                        __asm { tzcnt   rcx, rax }
                        v846 = (unsigned int)_RCX >> 3;
                      }
LABEL_1655:
                      v840 = v838 + v846 + 4;
                    }
                    v848 = 0;
                    if ( v1139 )
                    {
                      v849 = v1077 - (_DWORD)v805;
                      if ( (__int64)(v1077 - (_QWORD)v805) <= v811 - v831 )
                        v849 = (_DWORD)v811 - (_DWORD)v831;
                      while ( v848 - v849 > 3 )
                      {
                        if ( *(_DWORD *)&v831[v848 - 4] != *(_DWORD *)((char *)v805 + v848 - 4) )
                        {
                          _BitScanReverse(&v850, *(_DWORD *)&v831[v848 - 4] ^ *(_DWORD *)((char *)v805 + v848 - 4));
                          v848 -= (31 - v850) >> 3;
                          goto LABEL_1662;
                        }
                        v848 -= 4;
                      }
                      if ( v848 > v849 )
                      {
                        do
                        {
                          if ( *((_BYTE *)v805 + v848 - 1) != v831[v848 - 1] )
                            break;
                          --v848;
                        }
                        while ( v848 > v849 );
                        v817 = v1113;
                      }
                    }
LABEL_1662:
                    v818 = v1044;
                    v851 = v840 - v848;
                    v809 = v1130;
                    v807 = v1074;
                    if ( v851 > v1067 )
                    {
                      v1067 = v851;
                      v1059 = v1029 - v816;
                      v1147 = (unsigned __int64)v805 + v848;
                    }
                    v814 = v1020;
                  }
                  else
                  {
                    v809 = v1130;
                  }
                }
              }
              else
              {
                v820 = (_DWORD *)((char *)v808 + v816 - v817);
                if ( *(_WORD *)(v1077 + v1067 - 1) == *(_WORD *)((char *)v820 + v1067 - (__int64)v1139 - 1)
                  && *v820 == v814 )
                {
                  v821 = 0;
                  if ( v1139 )
                  {
                    v822 = v1077 - (_DWORD)v805;
                    v823 = -(__int64)(v816 - v817);
                    if ( (__int64)(v1077 - (_QWORD)v805) <= v823 )
                      v822 = v823;
                    while ( v821 - v822 > 3 )
                    {
                      if ( *(_DWORD *)((char *)v805 + v821 - 4) != *(_DWORD *)((char *)v820 + v821 - 4) )
                      {
                        _BitScanReverse(
                          &v824,
                          *(_DWORD *)((char *)v805 + v821 - 4) ^ *(_DWORD *)((char *)v820 + v821 - 4));
                        v821 -= (31 - v824) >> 3;
                        goto LABEL_1593;
                      }
                      v821 -= 4;
                    }
                    if ( v821 > v822 )
                    {
                      do
                      {
                        if ( *((_BYTE *)v805 + v821 - 1) != *((_BYTE *)v820 + v821 - 1) )
                          break;
                        --v821;
                      }
                      while ( v821 > v822 );
                      v808 = v1118;
                    }
                  }
LABEL_1593:
                  v825 = v805 + 1;
                  v826 = v820 + 1;
                  v827 = v805 + 1;
                  if ( (unsigned __int64)(v805 + 1) >= v1062 - 7 )
                  {
                    while ( (unsigned __int64)v827 < v1062 - 7 )
                    {
                      if ( *v826 != *v827 )
                      {
                        __asm { tzcnt   rax, rax }
                        v830 = ((unsigned int)_RAX >> 3) - (_DWORD)v825 + (_DWORD)v827;
                        goto LABEL_1950;
                      }
                      ++v827;
LABEL_1596:
                      ++v826;
                    }
                    if ( (unsigned __int64)v827 < v1062 - 3 && *(_DWORD *)v826 == *(_DWORD *)v827 )
                    {
                      v827 = (_QWORD *)((char *)v827 + 4);
                      v826 = (_QWORD *)((char *)v826 + 4);
                    }
                    if ( (unsigned __int64)v827 < v1062 - 1 && *(_WORD *)v826 == *(_WORD *)v827 )
                    {
                      v827 = (_QWORD *)((char *)v827 + 2);
                      v826 = (_QWORD *)((char *)v826 + 2);
                    }
                    if ( (unsigned __int64)v827 < v1062 && *(_BYTE *)v826 == *(_BYTE *)v827 )
                      LODWORD(v827) = (_DWORD)v827 + 1;
                    v830 = (_DWORD)v827 - (_DWORD)v825;
                  }
                  else
                  {
                    if ( *v826 == *v825 )
                    {
                      v827 = v805 + 3;
                      goto LABEL_1596;
                    }
                    __asm { tzcnt   rcx, rax }
                    v830 = (unsigned int)_RCX >> 3;
                  }
LABEL_1950:
                  v814 = v1020;
                  v975 = v830 - v821 + 4;
                  if ( v975 > v1067 )
                  {
                    v1067 = v975;
                    v1059 = v1029 - v816;
                    v1147 = (unsigned __int64)v805 + v821;
                  }
                }
              }
              v852 = a1;
              if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v816 + 0x20000) != 1 )
                goto LABEL_1734;
              if ( v818 )
              {
                v1044 = v818;
                if ( v818 != 2 )
                  goto LABEL_1734;
              }
              else
              {
                if ( (_BYTE)v814 != HIBYTE(v814) || (unsigned __int16)v814 != HIWORD(v814) )
                {
                  v818 = 1;
                  v1044 = 1;
LABEL_1734:
                  v816 -= *(unsigned __int16 *)(v852 + 2LL * (unsigned __int16)v816 + 0x20000);
                  goto LABEL_1691;
                }
                v1044 = 2;
                v853 = LZ4HC_countPattern(v805 + 1, v1062, v814, a1);
                v852 = a1;
                v1155 = v853 + 4LL;
              }
              v854 = v816 - 1;
              if ( v816 - 1 < v809 || v817 - v816 < 3 )
                goto LABEL_1734;
              if ( v854 >= v817 )
              {
                v855 = 0;
                v856 = (_DWORD *)((char *)v808 + v854 - v817);
              }
              else
              {
                v855 = 1;
                v856 = (_DWORD *)((char *)v1099 + v854 - v807);
              }
              if ( *v856 != v1020 )
                goto LABEL_1734;
              v857 = (_DWORD *)v1062;
              if ( v855 )
                v857 = v1164;
              v858 = (unsigned int)LZ4HC_countPattern(v856 + 1, v857, v1020, v852) + 4LL;
              if ( v855 )
              {
                if ( (_DWORD *)((char *)v856 + v858) == v857 )
                {
                  v859 = LZ4HC_rotatePattern(v858, v1020);
                  v860 = v1118;
                  v858 += (unsigned int)LZ4HC_countPattern(v1118, v1062, v859, v861);
                }
                else
                {
                  v860 = v1118;
                }
                v862 = v1099;
              }
              else
              {
                v860 = v1118;
                v862 = v1118;
              }
              v863 = LZ4HC_reverseCountPattern(v856, v862, v1020);
              v865 = v863;
              if ( !v855 && (_DWORD *)((char *)v856 - v863) == v860 && v1074 < v817 )
              {
                v866 = LZ4HC_rotatePattern(-v863, v864);
                v867 = LZ4HC_reverseCountPattern(v1164, v1099, v866);
                v865 = v867 + v868;
              }
              v809 = v1130;
              v816 = v1130;
              if ( v854 - v865 > v1130 )
                v816 = v854 - v865;
              v869 = v858 + v854 - v816;
              if ( v869 < v1155 || v858 > v1155 )
              {
                if ( v817 - v816 - 1 >= 3 )
                {
                  if ( !v1139 )
                  {
                    v808 = v1118;
                    v893 = v1155;
                    v812 = v1029;
                    if ( v869 < v1155 )
                      v893 = v869;
                    if ( v1067 < v893 )
                    {
                      if ( v1162 + v817 - (unsigned __int64)v816 - (_QWORD)v1118 > 0xFFFF )
                        goto LABEL_1964;
                      v1067 = v893;
                      v1147 = v1162;
                      v1059 = v1029 - v816;
                    }
                    v894 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v816 + 0x20000);
                    if ( v894 > v816 )
                    {
LABEL_1964:
                      v814 = v1020;
LABEL_1692:
                      v819 = v1087 <= 0;
                      goto LABEL_1693;
                    }
                    v816 -= v894;
                    goto LABEL_1690;
                  }
                }
                else
                {
                  v816 = v817;
                }
              }
              else
              {
                v816 = v817;
                if ( v817 - ((_DWORD)v858 - (_DWORD)v1155 + v854) - 1 >= 3 )
                  v816 = v858 - v1155 + v854;
              }
              v808 = v1118;
LABEL_1690:
              v818 = 2;
LABEL_1691:
              v811 = (char *)v1099;
              v807 = v1074;
              v805 = (_DWORD *)v1162;
              v812 = v1029;
              v814 = v1020;
              if ( v816 < v809 )
                goto LABEL_1692;
            }
          }
          v1147 = (unsigned __int64)v805;
LABEL_1695:
          if ( v812 - v809 < 0xFFFF )
          {
            v895 = *(unsigned int *)(v810 + 262168);
            v896 = *(_QWORD *)(v810 + 262152);
            v897 = *(_DWORD *)(v810 + 4 * v815);
            v898 = v895 + *(_QWORD *)(v810 + 0x40000) - v896;
            v1165 = v895;
            v899 = v1130 + v897 - v898;
            if ( v812 - v899 <= 0xFFFF )
            {
              v900 = v1087;
              do
              {
                if ( !v900 )
                  break;
                --v900;
                v901 = (_DWORD *)(v897 + v896 - v895);
                if ( *v901 == v814 )
                {
                  v902 = (_QWORD *)(v1162 + 4);
                  v903 = v1162 + v898 - v897;
                  v904 = v901 + 1;
                  v905 = (_QWORD *)(v1162 + 4);
                  if ( v903 > v1062 )
                    v903 = v1062;
                  if ( (unsigned __int64)v902 >= v903 - 7 )
                  {
                    while ( (unsigned __int64)v905 < v903 - 7 )
                    {
                      if ( *v904 != *v905 )
                      {
                        __asm { tzcnt   rax, rax }
                        v908 = ((unsigned int)_RAX >> 3) - (_DWORD)v902 + (_DWORD)v905;
                        goto LABEL_1772;
                      }
                      ++v905;
LABEL_1757:
                      ++v904;
                    }
                    if ( (unsigned __int64)v905 < v903 - 3 && *(_DWORD *)v904 == *(_DWORD *)v905 )
                    {
                      v905 = (_QWORD *)((char *)v905 + 4);
                      v904 = (_QWORD *)((char *)v904 + 4);
                    }
                    if ( (unsigned __int64)v905 < v903 - 1 && *(_WORD *)v904 == *(_WORD *)v905 )
                    {
                      v905 = (_QWORD *)((char *)v905 + 2);
                      v904 = (_QWORD *)((char *)v904 + 2);
                    }
                    if ( (unsigned __int64)v905 < v903 && *(_BYTE *)v904 == *(_BYTE *)v905 )
                      LODWORD(v905) = (_DWORD)v905 + 1;
                    v908 = (_DWORD)v905 - (_DWORD)v902;
                  }
                  else
                  {
                    if ( *v904 == *v902 )
                    {
                      v905 = (_QWORD *)(v1162 + 12);
                      goto LABEL_1757;
                    }
                    __asm { tzcnt   rcx, rax }
                    v908 = (unsigned int)_RCX >> 3;
                  }
LABEL_1772:
                  v910 = 0;
                  if ( v1139 )
                  {
                    v911 = v1077 - v1162;
                    if ( (__int64)(v1077 - v1162) <= v895 - v897 )
                      v911 = v895 - v897;
                    while ( v910 - v911 > 3 )
                    {
                      if ( *(_DWORD *)((char *)v901 + v910 - 4) != *(_DWORD *)(v910 + v1162 - 4) )
                      {
                        _BitScanReverse(&v912, *(_DWORD *)((char *)v901 + v910 - 4) ^ *(_DWORD *)(v910 + v1162 - 4));
                        v910 -= (31 - v912) >> 3;
                        goto LABEL_1778;
                      }
                      v910 -= 4;
                    }
                    if ( v910 > v911 )
                    {
                      do
                      {
                        if ( *(_BYTE *)(v910 + v1162 - 1) != *((_BYTE *)v901 + v910 - 1) )
                          break;
                        --v910;
                      }
                      while ( v910 > v911 );
                      v895 = v1165;
                    }
                  }
LABEL_1778:
                  v814 = v1020;
                  if ( (int)(v908 + 4 - v910) <= v1067 )
                  {
                    v812 = v1029;
                  }
                  else
                  {
                    v1067 = v908 + 4 - v910;
                    v812 = v1029;
                    v1059 = v1029 - v899;
                    v1147 = v1162 + v910;
                  }
                }
                v913 = *(unsigned __int16 *)(v1173 + 2LL * (unsigned __int16)v897 + 0x20000);
                v899 -= v913;
                v897 -= v913;
              }
              while ( v812 - v899 <= 0xFFFF );
              v30 = v1121;
            }
          }
LABEL_1696:
          v870 = v1067;
          v871 = v1059;
          v804 = v1180;
          v803 = v1183;
          v763 = v1036;
          v651 = v1047;
          v649 = v1208;
          v800 = v1077;
        }
        v872 = v649;
        if ( v870 <= v763 )
        {
          if ( v800 >= v649 + v651 )
          {
            v873 = v1208;
          }
          else
          {
            v873 = v800 - v651;
            v1208 = v800 - v651;
          }
          v27 = v1143;
          v874 = (_BYTE *)(v30 + 1);
          v263 = v1090;
          v766 = v30 >> 32;
          v875 = v651 - (_QWORD)v1143;
          v768 = v30;
          if ( a7 && (unsigned __int64)&v874[v875 + 8 + v875 / 0xFF] > v1090 )
            goto LABEL_2121;
          if ( v875 < 0xF )
          {
            *(_BYTE *)v30 = 16 * v875;
          }
          else
          {
            v876 = v875 - 15;
            *(_BYTE *)v30 = -16;
            while ( v876 >= 0xFF )
            {
              *v874++ = -1;
              v876 -= 255LL;
            }
            *v874++ = v876;
          }
          v877 = (__int64 *)v1143;
          v878 = &v874[v875];
          do
          {
            v879 = *v877++;
            *(_QWORD *)v874 = v879;
            v874 += 8;
          }
          while ( v874 < (_BYTE *)v878 );
          v880 = (__int64)(v878 + 1);
          *v878 = v1032;
          v881 = v873 - 4LL;
          if ( a7 && v880 + v881 / 0xFF + 6 > v1090 )
          {
            v651 = v1047;
            goto LABEL_2121;
          }
          v882 = *(_BYTE *)v30;
          if ( v881 < 0xF )
          {
            *(_BYTE *)v30 = v882 + v881;
          }
          else
          {
            *(_BYTE *)v30 = v882 + 15;
            for ( i12 = v873 - 19LL; i12 >= 0x1FE; i12 -= 510LL )
            {
              *(_BYTE *)v880 = -1;
              v982 = (_BYTE *)(v880 + 1);
              *v982 = -1;
              v880 = (__int64)(v982 + 1);
            }
            if ( i12 >= 0xFF )
            {
              LOBYTE(i12) = i12 + 1;
              *(_BYTE *)v880++ = -1;
            }
            *(_BYTE *)v880++ = i12;
          }
          v884 = (_BYTE *)(v880 + 1);
          v27 = (char *)(v873 + v1047);
          v1047 = v1077;
          v885 = v1077 - (_QWORD)v27;
          v766 = v880 >> 32;
          v768 = v880;
          if ( a7 && (unsigned __int64)&v884[v885 / 0xFF + 8 + v885] > v1090 )
          {
            v774 = v1051;
LABEL_1987:
            v651 = v1077;
            v940 = v763;
            goto LABEL_1842;
          }
          if ( v885 < 0xF )
          {
            *(_BYTE *)v880 = 16 * v885;
          }
          else
          {
            v886 = v885 - 15;
            *(_BYTE *)v880 = -16;
            while ( v886 >= 0xFF )
            {
              *v884++ = -1;
              v886 -= 255LL;
            }
            *v884++ = v886;
          }
          v887 = (__int64 *)v27;
          v888 = &v884[v885];
          do
          {
            v889 = *v887++;
            *(_QWORD *)v884 = v889;
            v884 += 8;
          }
          while ( v884 < (_BYTE *)v888 );
          v774 = v1051;
          v890 = v803 - 4;
          *v888 = v1051;
          v264 = 0x8080808080808081uLL;
          v30 = (__int64)(v888 + 1);
          v1121 = v30;
          v1080 = HIDWORD(v30);
          if ( a7 && v30 + v890 / 0xFF + 6 > v1090 )
            goto LABEL_1987;
          v891 = *(_BYTE *)v880;
          if ( v890 < 0xF )
          {
            *(_BYTE *)v880 = v891 + v890;
          }
          else
          {
            *(_BYTE *)v880 = v891 + 15;
            for ( i13 = v803 - 19; i13 >= 0x1FE; i13 -= 510LL )
            {
              *(_BYTE *)v30 = -1;
              v983 = (_BYTE *)(v30 + 1);
              *v983 = -1;
              v30 = (__int64)(v983 + 1);
            }
            if ( i13 >= 0xFF )
            {
              LOBYTE(i13) = i13 + 1;
              *(_BYTE *)v30++ = -1;
            }
            *(_BYTE *)v30++ = i13;
            v1121 = v30;
            v1080 = HIDWORD(v30);
          }
          v614 = v1106;
          v259 = v804;
          v13 = a1;
          v27 = (char *)v804;
          v1047 = (unsigned __int64)v804;
          v7 = 0;
          v1143 = (char *)v804;
          goto LABEL_1237;
        }
        v914 = v649 + v651;
        if ( v1147 >= v914 + 3 )
        {
          if ( v800 >= v914 )
          {
            v927 = v1208;
          }
          else if ( (__int64)(v800 - v651) >= 18 )
          {
            v927 = v800 - v651;
            v1208 = v800 - v651;
          }
          else
          {
            if ( v649 > 18 )
              v649 = 18;
            v1208 = v649;
            if ( v651 + v649 > (unsigned __int64)(v804 - 1) )
            {
              v649 = v763 + v800 - v651 - 4;
              v1208 = v649;
            }
            v927 = v1208;
            v928 = v649 + v651 - v800;
            if ( v928 > 0 )
            {
              v1077 = v928 + v800;
              v763 -= v928;
            }
          }
          v929 = (_BYTE *)(v30 + 1);
          LODWORD(v766) = v1080;
          v768 = v30;
          v930 = (char *)v30;
          v931 = v1047 - (_QWORD)v1143;
          if ( a7 && (unsigned __int64)&v929[v931 / 0xFF + 8 + v931] > v1090 )
          {
            v651 = v1047;
            v27 = v1143;
            v263 = v1090;
            goto LABEL_2121;
          }
          if ( v931 < 0xF )
          {
            *(_BYTE *)v30 = 16 * v931;
          }
          else
          {
            v932 = v931 - 15;
            *(_BYTE *)v30 = -16;
            while ( v932 >= 0xFF )
            {
              *v929++ = -1;
              v932 -= 255LL;
            }
            *v929++ = v932;
          }
          v933 = (__int64 *)v1143;
          v934 = &v929[v931];
          do
          {
            v935 = *v933++;
            *(_QWORD *)v929 = v935;
            v929 += 8;
          }
          while ( v929 < (_BYTE *)v934 );
          *v934 = v1032;
          v30 = (__int64)(v934 + 1);
          v1121 = v30;
          v936 = v927 - 4LL;
          v1080 = HIDWORD(v30);
          if ( a7 && v30 + v936 / 0xFF + 6 > v1090 )
            goto LABEL_2123;
          v937 = *v930;
          if ( v936 < 0xF )
          {
            *v930 = v937 + v936;
          }
          else
          {
            *v930 = v937 + 15;
            for ( i14 = v927 - 19LL; i14 >= 0x1FE; i14 -= 510LL )
            {
              *(_BYTE *)v30 = -1;
              v980 = (_BYTE *)(v30 + 1);
              *v980 = -1;
              v30 = (__int64)(v980 + 1);
            }
            if ( i14 >= 0xFF )
            {
              LOBYTE(i14) = i14 + 1;
              *(_BYTE *)v30++ = -1;
            }
            *(_BYTE *)v30++ = i14;
            v1121 = v30;
            v1080 = HIDWORD(v30);
          }
          v651 = v1077;
          v649 = v763;
          v1143 = (char *)(v927 + v1047);
          v800 = v1147;
          v1077 = v1147;
          v1047 = v651;
          LOWORD(v1032) = v1051;
          v1208 = v763;
        }
        else
        {
          if ( v1147 >= v914 )
          {
            if ( v800 < v914 )
            {
              v915 = v649 + v651 - v800;
              v763 -= v915;
              if ( v763 < 4 )
              {
                v1077 = v1147;
                v916 = v871;
                v763 = v870;
LABEL_1792:
                v917 = (_BYTE *)(v30 + 1);
                v768 = v30;
                v766 = v30 >> 32;
                v918 = (char *)v30;
                v919 = v1047 - (_QWORD)v1143;
                if ( a7 && (unsigned __int64)&v917[v919 / 0xFF + 8 + v919] > v1090 )
                {
                  v27 = v1143;
                }
                else
                {
                  if ( v919 < 0xF )
                  {
                    *(_BYTE *)v30 = 16 * v919;
                  }
                  else
                  {
                    v920 = v919 - 15;
                    *(_BYTE *)v30 = -16;
                    while ( v920 >= 0xFF )
                    {
                      *v917++ = -1;
                      v920 -= 255LL;
                    }
                    *v917++ = v920;
                  }
                  v921 = (__int64 *)v1143;
                  v922 = &v917[v919];
                  do
                  {
                    v923 = *v921++;
                    *(_QWORD *)v917 = v923;
                    v917 += 8;
                  }
                  while ( v917 < (_BYTE *)v922 );
                  v924 = v872 - 4;
                  *v922 = v1032;
                  v30 = (__int64)(v922 + 1);
                  v1121 = v30;
                  v1080 = HIDWORD(v30);
                  if ( !a7 || v30 + v924 / 0xFF + 6 <= v1090 )
                  {
                    v925 = *v918;
                    if ( v924 < 0xF )
                    {
                      *v918 = v925 + v924;
                    }
                    else
                    {
                      *v918 = v925 + 15;
                      for ( i15 = v872 - 19; i15 >= 0x1FE; i15 -= 510LL )
                      {
                        *(_BYTE *)v30 = -1;
                        v981 = (_BYTE *)(v30 + 1);
                        *v981 = -1;
                        v30 = (__int64)(v981 + 1);
                      }
                      if ( i15 >= 0xFF )
                      {
                        LOBYTE(i15) = i15 + 1;
                        *(_BYTE *)v30++ = -1;
                      }
                      *(_BYTE *)v30++ = i15;
                      v1121 = v30;
                      v1080 = HIDWORD(v30);
                    }
                    v649 = v870;
                    v653 = v1077;
                    v651 = v1147;
                    v1047 = v1147;
                    v650 = v916;
                    v1208 = v870;
                    LODWORD(v652) = v763;
                    v1143 = (char *)v914;
                    LOWORD(v1032) = v871;
                    goto LABEL_1275;
                  }
LABEL_2123:
                  v27 = v1143;
                }
                v651 = v1047;
                v263 = v1090;
LABEL_2121:
                v774 = v1032;
                goto LABEL_2122;
              }
              v1077 = v915 + v800;
            }
            v916 = v1051;
            goto LABEL_1792;
          }
          v800 = v1147;
          v1077 = v1147;
        }
        v1051 = v871;
        v763 = v870;
        v654 = v1106;
        v1036 = v870;
      }
    }
    v649 = v763;
    v1047 = v1077;
    v1208 = v763;
    v651 = v1077;
    LOWORD(v1032) = v764;
  }
  v765 = (_BYTE *)(v30 + 1);
  v27 = v1143;
  v766 = v30 >> 32;
  v767 = v1047 - (_QWORD)v1143;
  v768 = v30;
  v769 = (char *)v30;
  if ( a7 && (unsigned __int64)&v765[v767 / 0xFF + 8 + v767] > v1090 )
  {
    v651 = v1047;
    v940 = v1208;
    v774 = v1032;
    v263 = v1090;
    goto LABEL_1842;
  }
  if ( v767 < 0xF )
  {
    *(_BYTE *)v30 = 16 * v767;
  }
  else
  {
    v770 = v767 - 15;
    *(_BYTE *)v30 = -16;
    while ( v770 >= 0xFF )
    {
      *v765++ = -1;
      v770 -= 255LL;
    }
    *v765++ = v770;
  }
  v771 = (__int64 *)v1143;
  v772 = &v765[v767];
  do
  {
    v773 = *v771++;
    *(_QWORD *)v765 = v773;
    v765 += 8;
  }
  while ( v765 < (_BYTE *)v772 );
  v774 = v1032;
  v775 = v655 - 4;
  v263 = v1090;
  *v772 = v1032;
  v30 = (__int64)(v772 + 1);
  v1121 = v30;
  v1080 = HIDWORD(v30);
  if ( !a7 || v30 + v775 / 0xFF + 6 <= v1090 )
  {
    v776 = *v769;
    if ( v775 < 0xF )
    {
      *v769 = v776 + v775;
    }
    else
    {
      *v769 = v776 + 15;
      for ( i16 = v775 - 15; i16 >= 0x1FE; i16 -= 510LL )
      {
        *(_BYTE *)v30 = -1;
        v939 = (_BYTE *)(v30 + 1);
        *v939 = -1;
        v30 = (__int64)(v939 + 1);
      }
      if ( i16 >= 0xFF )
      {
        LOBYTE(i16) = i16 + 1;
        *(_BYTE *)v30++ = -1;
      }
      *(_BYTE *)v30++ = i16;
      v1121 = v30;
      v1080 = HIDWORD(v30);
    }
    v259 = v656;
    v1047 = (unsigned __int64)v656;
    v27 = (char *)v656;
    v1143 = (char *)v656;
    goto LABEL_1840;
  }
  v651 = v1047;
LABEL_2122:
  v940 = v1208;
LABEL_1842:
  if ( a7 != 2 )
    goto LABEL_387;
  v941 = v651 - (_QWORD)v27;
  v30 = __PAIR64__(v766, v768);
  v942 = (v651 - (unsigned __int64)v27 + 240) / 0xFF + v651 - (_QWORD)v27 + 1;
  if ( __PAIR64__(v766, v768) + v942 <= v263 - 3 )
  {
    if ( v940 > 255 * (v263 - 3 - __PAIR64__(v766, v768) - v942) + 18 )
      v940 = 255 * (v263 - 3 - v768 - v942) + 18;
    if ( (__int64)(v263 + v940 - __PAIR64__(v766, v768) - v942 + 2) >= 12 )
    {
      v943 = (_BYTE *)(__PAIR64__(v766, v768) + 1);
      if ( v941 < 0xF )
      {
        *(_BYTE *)__PAIR64__(v766, v768) = 16 * v941;
      }
      else
      {
        v944 = v941 - 15;
        *(_BYTE *)__PAIR64__(v766, v768) = -16;
        while ( v944 >= 0xFF )
        {
          *v943++ = -1;
          v944 -= 255LL;
        }
        *v943++ = v944;
      }
      v945 = &v943[v941];
      do
      {
        v946 = *(_QWORD *)v27;
        v27 += 8;
        *(_QWORD *)v943 = v946;
        v943 += 8;
      }
      while ( v943 < (_BYTE *)v945 );
      *v945 = v774;
      v947 = *(_BYTE *)__PAIR64__(v766, v768);
      v30 = (__int64)(v945 + 1);
      if ( (unsigned __int64)(v940 - 4LL) < 0xF )
      {
        *(_BYTE *)__PAIR64__(v766, v768) = v947 + v940 - 4;
      }
      else
      {
        *(_BYTE *)__PAIR64__(v766, v768) = v947 + 15;
        for ( i17 = v940 - 19LL; i17 >= 0x1FE; i17 -= 510LL )
        {
          *(_BYTE *)v30 = -1;
          v949 = (_BYTE *)(v30 + 1);
          *v949 = -1;
          v30 = (__int64)(v949 + 1);
        }
        if ( i17 >= 0xFF )
        {
          LOBYTE(i17) = i17 + 1;
          *(_BYTE *)v30++ = -1;
        }
        *(_BYTE *)v30++ = i17;
      }
      v27 = (char *)(v940 + v1047);
    }
  }
  v265 = v1186 - v27;
  v33 = v1186 - v27;
LABEL_376:
  v263 += 5LL;
LABEL_377:
  if ( v30 + (v265 + 240) / 0xFF + v265 + 1 <= v263 )
  {
LABEL_1863:
    v34 = v33 + (_DWORD)v27;
    if ( v33 >= 0xF )
    {
      *(_BYTE *)v30 = -16;
      v35 = v33 - 15;
      ++v30;
      while ( v35 >= 0xFF )
      {
        *(_BYTE *)v30++ = -1;
        v35 -= 255LL;
      }
      goto LABEL_31;
    }
    goto LABEL_812;
  }
  if ( a7 != 1 )
  {
    v33 = v263 - v30 - 1 - ((v263 - v30 - 1 + 241) >> 8);
    goto LABEL_1863;
  }
LABEL_218:
  v24 = 0;
LABEL_14:
  *(_BYTE *)(a1 + 262183) = 1;
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800efdb4  mov     rax, rsp
0x1800efdb7  mov     [rax+20h], r9
0x1800efdbb  mov     [rax+18h], r8
0x1800efdbf  mov     [rax+10h], rdx
0x1800efdc3  mov     [rax+8], rcx
0x1800efdc7  push    rbp
0x1800efdc8  push    rbx
0x1800efdc9  push    rsi
0x1800efdca  push    rdi
0x1800efdcb  push    r12
0x1800efdcd  push    r13
0x1800efdcf  push    r14
0x1800efdd1  push    r15
0x1800efdd3  lea     rbp, [rsp-48h]
0x1800efdd8  sub     rsp, 148h
0x1800efddf  mov     eax, [rcx+40018h]
0x1800efde5  xor     esi, esi
0x1800efde7  sub     eax, [rcx+4001Ch]
0x1800efded  mov     r14, r9
0x1800efdf0  sub     rax, [rcx+40008h]
0x1800efdf7  mov     r13, r8
0x1800efdfa  mov     r10, [rcx+40000h]
0x1800efe01  mov     rdi, rdx
0x1800efe04  add     rax, r10
0x1800efe07  mov     rbx, rcx
0x1800efe0a  cmp     rax, 10000h
0x1800efe10  jb      loc_1800EFF51
0x1800efe16  cmp     [rbp+80h+arg_30], 2
0x1800efe1d  lea     r12d, [rsi+1]
0x1800efe21  mov     [rcx+40028h], rsi
0x1800efe28  jz      loc_1800EFF42
0x1800efe2e  cmp     dword ptr [r9], 7E000000h
0x1800efe35  ja      loc_1800EFF2B
0x1800efe3b  movsxd  rax, dword ptr [r9]
0x1800efe3e  mov     rbx, r13
0x1800efe41  add     rax, r10
0x1800efe44  mov     [rsp+180h+var_138], rdi
0x1800efe49  mov     [rcx+40000h], rax
0x1800efe50  mov     r8, rdi
0x1800efe53  movsxd  rdx, dword ptr [r9]
0x1800efe56  mov     r15, rdi
0x1800efe59  movsxd  rcx, [rbp+80h+arg_20]
0x1800efe60  mov     r10, 8080808080808081h
0x1800efe6a  add     rcx, r13
0x1800efe6d  mov     [rbp+80h+var_E8], rdi
0x1800efe71  cmp     [rbp+80h+arg_30], 2
0x1800efe78  mov     r11d, 0FFh
0x1800efe7e  lea     r9, [rdi+rdx]
0x1800efe82  mov     [rsp+180h+var_108], rbx
0x1800efe87  mov     [rbp+80h+var_C0], r9
0x1800efe8b  lea     r13, [rcx-5]
0x1800efe8f  mov     [rsp+180h+var_120], rbx
0x1800efe94  cmovnz  r13, rcx
0x1800efe98  mov     [r14], esi
0x1800efe9b  mov     [rsp+180h+var_110], r13
0x1800efea0  cmp     edx, 0Dh
0x1800efea3  jge     loc_1800F0088
0x1800efea9  sub     r9, r15
0x1800efeac  cmp     [rbp+80h+arg_30], 2
0x1800efeb3  mov     rdi, r9
0x1800efeb6  jz      loc_1800F0B37
0x1800efebc  cmp     [rbp+80h+arg_30], esi
0x1800efec2  jnz     loc_1800F0B3B
0x1800efec8  lea     rsi, [rdi+r15]
0x1800efecc  cmp     rdi, 0Fh
0x1800efed0  jb      loc_1800F0D5B
0x1800efed6  mov     byte ptr [rbx], 0F0h
0x1800efed9  lea     rax, [rdi-0Fh]
0x1800efedd  add     rbx, r12
0x1800efee0  cmp     rax, r11
0x1800efee3  jnb     loc_1800F72B4
0x1800efee9  lea     rcx, [rbx+1]; void *
0x1800efeed  mov     [rbx], al
0x1800efeef  mov     r8, rdi; Size
0x1800efef2  lea     r14, [rbx+1]
0x1800efef6  mov     rdx, r15; Src
0x1800efef9  call    memmove
0x1800efefe  sub     esi, [rbp+80h+arg_8]
0x1800eff04  mov     rax, [rbp+80h+arg_18]
0x1800eff0b  sub     edi, [rbp+80h+arg_10]
0x1800eff11  mov     [rax], esi
0x1800eff13  lea     eax, [rdi+r14]
0x1800eff17  test    eax, eax
0x1800eff19  jg      short loc_1800EFF29
0x1800eff1b  mov     rcx, [rbp+80h+arg_0]; void *
0x1800eff22  mov     byte ptr [rcx+40027h], 1
0x1800eff29  mov     esi, eax
0x1800eff2b  mov     eax, esi
0x1800eff2d  add     rsp, 148h
0x1800eff34  pop     r15
0x1800eff36  pop     r14
0x1800eff38  pop     r13
0x1800eff3a  pop     r12
0x1800eff3c  pop     rdi
0x1800eff3d  pop     rsi
0x1800eff3e  pop     rbx
0x1800eff3f  pop     rbp
0x1800eff40  retn
0x1800eff42  cmp     [rbp+80h+arg_20], r12d
0x1800eff49  jge     loc_1800EFE2E
0x1800eff4f  jmp     short loc_1800EFF2B
0x1800eff51  test    rax, rax
0x1800eff54  jnz     loc_1800F1655
0x1800eff5a  cmp     dword ptr [r9], 1000h
0x1800eff61  jle     loc_1800F1655
0x1800eff67  mov     rdx, [rcx+40028h]; Src
0x1800eff6e  mov     r8d, 40030h; Size
0x1800eff74  call    memmove
0x1800eff79  mov     rdx, rdi
0x1800eff7c  mov     rcx, rbx
0x1800eff7f  call    LZ4HC_setExternalDict
0x1800eff84  cmp     [rbp+80h+arg_30], 2
0x1800eff8b  mov     r12d, 1
0x1800eff91  mov     word ptr [rbx+40024h], 9
0x1800eff9a  jz      loc_1800F0B73
0x1800effa0  cmp     dword ptr [r14], 7E000000h
0x1800effa7  ja      short loc_1800EFF2B
0x1800effa9  movsxd  rax, dword ptr [r14]
0x1800effac  mov     r9, rdi
0x1800effaf  add     [rbx+40000h], rax
0x1800effb6  mov     r15, rdi
0x1800effb9  movsxd  rdx, dword ptr [r14]
0x1800effbc  mov     r10, 8080808080808081h
0x1800effc6  movsxd  rcx, [rbp+80h+arg_20]
0x1800effcd  add     rcx, r13
0x1800effd0  mov     [r14], esi
0x1800effd3  cmp     [rbp+80h+arg_30], 2
0x1800effda  lea     r8, [rdi+rdx]
0x1800effde  mov     [rsp+180h+var_148], rdi
0x1800effe3  mov     [rbp+80h+var_E8], rdi
0x1800effe7  mov     rdi, r13
0x1800effea  lea     r14, [rcx-5]
0x1800effee  mov     [rsp+180h+var_108], r13
0x1800efff3  cmovnz  r14, rcx
0x1800efff7  mov     [rsp+180h+var_120], r13
0x1800efffc  mov     [rsp+180h+var_110], r14
0x1800f0001  mov     r13d, 0FFh
0x1800f0007  mov     [rsp+180h+var_138], r8
0x1800f000c  cmp     edx, 0Dh
0x1800f000f  jge     loc_1800F1C59
0x1800f0015  sub     r8, r15
0x1800f0018  cmp     [rbp+80h+arg_30], 2
0x1800f001f  mov     rbx, r8
0x1800f0022  jz      loc_1800F25C7
0x1800f0028  cmp     [rbp+80h+arg_30], esi
0x1800f002e  jnz     loc_1800F25CB
0x1800f0034  lea     rsi, [rbx+r15]
0x1800f0038  cmp     rbx, 0Fh
0x1800f003c  jb      loc_1800F2E01
0x1800f0042  mov     byte ptr [rdi], 0F0h
0x1800f0045  lea     rax, [rbx-0Fh]
0x1800f0049  add     rdi, r12
0x1800f004c  cmp     rax, r13
0x1800f004f  jnb     loc_1800F749B
0x1800f0055  mov     r8, rbx; Size
0x1800f0058  mov     [rdi], al
0x1800f005a  mov     rdx, r15; Src
0x1800f005d  lea     rcx, [rdi+1]; void *
0x1800f0061  lea     r14, [rdi+1]
0x1800f0065  call    memmove
0x1800f006a  sub     esi, [rbp+80h+arg_8]
0x1800f0070  mov     rax, [rbp+80h+arg_18]
0x1800f0077  sub     ebx, [rbp+80h+arg_10]
0x1800f007d  mov     [rax], esi
0x1800f007f  lea     eax, [rbx+r14]
0x1800f0083  jmp     loc_1800EFF17
0x1800f0088  lea     rcx, [r9-0Ch]
0x1800f008c  mov     [rsp+180h+var_128], rsi
0x1800f0091  lea     rax, [r9-5]
0x1800f0095  mov     [rbp+80h+var_F0], rcx
0x1800f0099  mov     [rsp+180h+var_148], rax
0x1800f009e  mov     [rbp+80h+var_C8], rsi
0x1800f00a2  cmp     r8, rcx
0x1800f00a5  ja      loc_1800F72AB
0x1800f00ab  mov     r9, [rbp+80h+arg_0]
0x1800f00b2  mov     edi, r8d
0x1800f00b5  mov     r13d, [r8]
0x1800f00b8  mov     [rbp+80h+arg_28], 3
0x1800f00c2  mov     edx, [r9+40018h]
0x1800f00c9  mov     r10d, [r9+4001Ch]
0x1800f00d0  mov     r11d, edx
0x1800f00d3  mov     r14, [r9+40008h]
0x1800f00da  mov     r12d, r10d
0x1800f00dd  mov     r9, [r9+40010h]
0x1800f00e4  sub     edi, r14d
0x1800f00e7  add     edi, edx
0x1800f00e9  mov     [rbp+80h+var_F8], edx
0x1800f00ec  lea     ecx, [r10+10000h]
0x1800f00f3  mov     [rbp+80h+var_D0], r14
0x1800f00f7  cmp     ecx, edi
0x1800f00f9  mov     [rsp+180h+var_15C], edi
0x1800f00fd  mov     ecx, edx
0x1800f00ff  mov     dword ptr [rbp+80h+var_E0], r10d
0x1800f0103  lea     eax, [rdi-0FFFFh]
0x1800f0109  mov     [rbp+80h+var_100], r9
0x1800f010d  cmovbe  r12d, eax
0x1800f0111  mov     edx, 100h
0x1800f0116  xor     eax, eax
0x1800f0118  mov     dword ptr [rbp+80h+var_D8], r12d
0x1800f011c  sub     rcx, r10
0x1800f011f  mov     [rbp+80h+var_B8], rax
0x1800f0123  add     rcx, r9
0x1800f0126  mov     [rsp+180h+var_158], eax
0x1800f012a  mov     rax, [rbp+80h+arg_0]
0x1800f0131  mov     [rbp+80h+var_A0], rcx
0x1800f0135  mov     [rsp+180h+var_12C], edx
0x1800f0139  mov     r8d, [rax+40020h]
0x1800f0140  cmp     r8d, edi
0x1800f0143  jb      loc_1800F70CA
0x1800f0149  mov     r11, [rbp+80h+arg_0]
0x1800f0150  mov     r8, [rsp+180h+var_138]
0x1800f0155  mov     [r11+40020h], edi
0x1800f015c  imul    ecx, [r8], 9E3779B1h
0x1800f0163  shr     rcx, 11h
0x1800f0167  mov     r11d, [r11+rcx*4]
0x1800f016b  cmp     r11d, r12d
0x1800f016e  jb      loc_1800F0511
0x1800f0174  mov     ebx, [rbp+80h+var_F8]
0x1800f0177  test    edx, edx
0x1800f0179  jle     loc_1800F0508
0x1800f017f  mov     r15, [rsp+180h+var_138]
0x1800f0184  cmp     r11d, ebx
0x1800f0187  jb      short loc_1800F01EF
0x1800f0189  movsxd  r10, [rbp+80h+arg_28]
0x1800f0190  mov     r8d, r11d
0x1800f0193  sub     r8d, ebx
0x1800f0196  lea     rax, [r14+r10]
0x1800f019a  movzx   ecx, word ptr [rax+r8-1]
0x1800f01a0  cmp     [r10+r15-1], cx
0x1800f01a6  jnz     loc_1800F0393
0x1800f01ac  cmp     [r14+r8], r13d
0x1800f01b0  jnz     loc_1800F0393
0x1800f01b6  mov     r9, [rsp+180h+var_148]
0x1800f01bb  lea     rdx, [r8+4]
0x1800f01bf  lea     r8, [r15+4]
0x1800f01c3  add     rdx, r14
0x1800f01c6  add     r9, 0FFFFFFFFFFFFFFF9h
0x1800f01ca  mov     rcx, r8
0x1800f01cd  cmp     r8, r9
0x1800f01d0  jnb     loc_1800F0C8B
0x1800f01d6  mov     rax, [r8]
0x1800f01d9  xor     rax, [rdx]
0x1800f01dc  jz      loc_1800F0C83
0x1800f01e2  tzcnt   rcx, rax
0x1800f01e7  shr     ecx, 3
0x1800f01ea  jmp     loc_1800F037C
0x1800f01ef  lea     eax, [rbx-4]
0x1800f01f2  cmp     r11d, eax
0x1800f01f5  ja      loc_1800F0393
0x1800f01fb  mov     eax, r11d
0x1800f01fe  sub     eax, r10d
0x1800f0201  mov     ecx, eax
0x1800f0203  cmp     [rax+r9], r13d
0x1800f0207  jnz     loc_1800F0393
0x1800f020d  mov     eax, ebx
0x1800f020f  lea     rdx, [r9+4]
0x1800f0213  sub     eax, r11d
0x1800f0216  lea     r9, [r15+4]
0x1800f021a  add     r8, rax
0x1800f021d  cmp     r8, [rsp+180h+var_148]
0x1800f0222  cmova   r8, [rsp+180h+var_148]
0x1800f0228  add     rdx, rcx
0x1800f022b  mov     rcx, r9
0x1800f022e  lea     r10, [r8-7]
0x1800f0232  cmp     r9, r10
0x1800f0235  jnb     short loc_1800F024B
0x1800f0237  mov     rax, [rdx]
0x1800f023a  xor     rax, [r9]
0x1800f023d  jnz     loc_1800F10B4
0x1800f0243  lea     rcx, [r9+8]
0x1800f0247  add     rdx, 8
0x1800f024b  cmp     rcx, r10
0x1800f024e  jb      loc_1800F0CB2
0x1800f0254  lea     rax, [r8-3]
0x1800f0258  cmp     rcx, rax
0x1800f025b  jnb     short loc_1800F026B
0x1800f025d  mov     eax, [rcx]
0x1800f025f  cmp     [rdx], eax
0x1800f0261  jnz     short loc_1800F026B
0x1800f0263  add     rcx, 4
0x1800f0267  add     rdx, 4
0x1800f026b  lea     rax, [r8-1]
0x1800f026f  cmp     rcx, rax
0x1800f0272  jnb     short loc_1800F0284
0x1800f0274  movzx   eax, word ptr [rcx]
0x1800f0277  cmp     [rdx], ax
0x1800f027a  jnz     short loc_1800F0284
0x1800f027c  add     rcx, 2
0x1800f0280  add     rdx, 2
0x1800f0284  cmp     rcx, r8
0x1800f0287  jnb     short loc_1800F0292
0x1800f0289  mov     al, [rcx]
0x1800f028b  cmp     [rdx], al
0x1800f028d  jnz     short loc_1800F0292
0x1800f028f  inc     rcx
0x1800f0292  sub     ecx, r9d
0x1800f0295  mov     r10d, ecx
0x1800f0298  movsxd  r9, r10d
0x1800f029b  lea     ecx, [r10+4]
0x1800f029f  add     r9, 4
  ... truncated ...
```
