# sqlite3VdbeExec

- ea: `0x140074448`
- end: `0x14007a710`
- name: `sqlite3VdbeExec`
- size: `25288`
- prototype: ``
- caller_count: `2`
- callee_count: `170`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001f748`
- `0x14008cfa0`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x14001bb44`
- `0x14001cfc0`
- `0x14001d034`
- `0x14001fd94`
- `0x140020674`
- `0x14002b924`
- `0x14002bc30`
- `0x14002f634`
- `0x14003bbcc`
- `0x14003c2e8`
- `0x140049bf8`
- `0x14004b2f4`
- `0x14004cfd8`
- `0x14004d050`
- `0x14004d0b4`
- `0x14004d0e0`
- `0x14004d194`
- `0x14004d1ac`
- `0x14004d6cc`
- `0x14004d7c4`
- `0x14004d82c`
- `0x14004d8ac`
- `0x14004d8bc`
- `0x14004d8c8`
- `0x14004d8d4`
- `0x14004dd28`
- `0x14004dd90`
- `0x14004ddb4`
- `0x14004ddc4`
- `0x14004de74`
- `0x14004df58`
- `0x14004e064`
- `0x14004e4c8`
- `0x14004e9ec`
- `0x14004ea0c`
- `0x14004edec`
- `0x14004ee0c`
- `0x14004ee1c`
- `0x14004ee3c`
- `0x14004eef4`
- `0x14004ef58`
- `0x14004efa0`
- `0x14004f650`
- `0x14004f68c`
- `0x14004f6ac`
- `0x14004f87c`
- `0x14004f8d0`
- `0x14004fd80`

## string_xrefs

- `0x14007a199`: `cannot open savepoint - SQL statements in progress`
- `0x14007a0cb`: `cannot commit transaction - SQL statements in progress`
- `0x14007a174`: `cannot rollback - no transaction is active`
- `0x14007a17b`: `cannot commit - no transaction is active`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1, __int64 a2, __int64 a3, unsigned __int64 a4)
{
  __int64 v4; // r12
  __int64 *v5; // r14
  __int64 v6; // r8
  unsigned __int8 *v7; // r13
  __int64 v8; // rsi
  unsigned __int64 v9; // r10
  unsigned __int64 v10; // rdi
  __int64 v11; // r11
  int v12; // eax
  _QWORD *v13; // rdi
  unsigned __int64 v14; // rdx
  unsigned int v15; // r15d
  __int64 v16; // rbx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  __int64 v20; // r14
  unsigned int v21; // ebx
  __int64 v22; // r15
  __int64 v23; // rsi
  unsigned int JournalMode; // eax
  unsigned int v25; // edi
  __int64 v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  unsigned int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rdi
  __int64 v36; // rbx
  int v37; // r8d
  unsigned int v38; // ebx
  _BYTE *v39; // rsi
  unsigned int v40; // ebx
  __int64 v41; // rbx
  _QWORD *v42; // rax
  _QWORD *v43; // rdi
  __int64 v44; // rax
  _QWORD *v45; // r14
  _QWORD *v46; // r15
  int v47; // esi
  int v48; // eax
  __int64 v49; // r8
  unsigned int v50; // eax
  int *v51; // r12
  int v52; // r15d
  __int64 v53; // rcx
  int v54; // ebx
  int v55; // esi
  int v56; // ebx
  unsigned int v57; // r15d
  __int64 n; // rax
  _QWORD *v59; // rcx
  __int64 v60; // r12
  unsigned int v61; // eax
  __int64 v62; // r9
  unsigned int v63; // eax
  bool v64; // zf
  int v65; // ebx
  int v66; // ebx
  int v67; // ebx
  int v68; // ebx
  __int64 v69; // rcx
  __int64 *v70; // rbx
  __int64 v71; // r10
  __int64 v72; // rdx
  char v73; // di
  __int64 v74; // r8
  __int64 v75; // rcx
  int ii; // r9d
  __int64 v77; // rax
  __int16 v78; // ax
  __int64 v79; // rdx
  int *v80; // r11
  __int64 v81; // r15
  int v82; // r9d
  __int64 **v83; // rbx
  __int64 v84; // rdx
  __int64 *v85; // r14
  __int64 v86; // rdi
  unsigned int v87; // r10d
  __int64 jj; // rsi
  __int64 v89; // rax
  unsigned int v90; // eax
  __int64 *v91; // rdx
  unsigned int v92; // edi
  int v93; // eax
  __int64 v94; // rcx
  int v95; // ebx
  int v96; // ebx
  int v97; // ebx
  int v98; // ebx
  unsigned int v99; // eax
  bool v100; // zf
  __int64 v101; // r8
  unsigned __int64 v102; // rcx
  unsigned int v103; // edx
  int v104; // eax
  int v105; // eax
  int v106; // eax
  __int64 v107; // rax
  __int64 v108; // rbx
  __int16 v109; // ax
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // r15
  BOOL v117; // r12d
  __int64 v118; // rdi
  __int16 v119; // si
  __int64 v120; // rax
  __int16 v121; // cx
  __int64 v122; // r14
  _BYTE *v123; // rcx
  BOOL v124; // ecx
  __int64 v125; // rdx
  __int64 v126; // rax
  __int64 v127; // rbx
  bool v128; // zf
  unsigned __int64 v129; // rdx
  __int64 v130; // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rcx
  __int16 v134; // ax
  int v135; // ecx
  bool v136; // zf
  __int64 v137; // rcx
  __int64 v138; // rax
  __int64 v139; // rbx
  __int64 v140; // rcx
  int *v141; // rsi
  __int64 v142; // rdx
  unsigned __int64 v143; // rsi
  __int64 v144; // rbx
  double v145; // xmm0_8
  __int64 v146; // rax
  _QWORD *v147; // rdi
  unsigned int v148; // eax
  char v149; // si
  __int64 v150; // rax
  unsigned int v151; // eax
  _BYTE *v152; // rax
  __int64 v153; // rcx
  __int64 v154; // rax
  __int64 v155; // rdi
  __int64 v156; // rsi
  __int64 v157; // rcx
  __int64 v158; // rcx
  __int128 v159; // xmm1
  __int128 v160; // xmm0
  __int64 v161; // rdi
  __int64 v162; // rbx
  __int64 v163; // rcx
  unsigned int v164; // eax
  __int64 v165; // rax
  __int64 v166; // rdi
  int v167; // ecx
  unsigned int v168; // edx
  __int64 v169; // rcx
  __int64 v170; // rax
  __int64 v171; // rbx
  __int64 v172; // rax
  int v173; // ebx
  int v174; // ebx
  int v175; // ebx
  int v176; // ebx
  __int64 v177; // rbx
  unsigned int v178; // eax
  __int64 v179; // rcx
  __int64 v180; // rax
  __int64 v181; // rbx
  unsigned int v182; // eax
  int v183; // ebx
  int v184; // eax
  int v185; // ebx
  __int64 *v186; // rax
  __int64 v187; // r8
  __int64 v188; // rdx
  __int16 v189; // cx
  __int16 v190; // cx
  bool v191; // zf
  bool v192; // zf
  __int64 v193; // r8
  __int64 kk; // rax
  int *v195; // r15
  int *v196; // r12
  __int64 v197; // rsi
  int v198; // edi
  int v199; // r14d
  __int64 v200; // rbx
  __int64 v201; // rcx
  __int64 *v202; // rsi
  __int64 v203; // rdx
  __int64 v204; // r14
  __int64 v205; // rcx
  void *v206; // rcx
  __int64 v207; // r8
  int v208; // eax
  int v209; // edi
  __int64 v210; // rbx
  __int64 v211; // rsi
  __int64 v212; // rsi
  bool v213; // sf
  __int64 v214; // rax
  __int64 v215; // rbx
  __int64 v216; // rcx
  __int64 v217; // rax
  __int64 v218; // rdx
  __int64 v219; // rcx
  __int64 v220; // rbx
  unsigned int v221; // edi
  unsigned int v222; // eax
  int v223; // ebx
  int v224; // ecx
  int v225; // ebx
  __int64 v226; // r15
  __int64 v227; // r14
  __int16 v228; // si
  __int16 v229; // di
  bool v230; // cc
  bool v231; // zf
  __int64 v232; // rcx
  __int64 v233; // rax
  __int64 v234; // rax
  __int64 v235; // rcx
  __int64 v236; // rax
  __int64 v237; // rdx
  __int64 v238; // rcx
  __int64 v239; // rax
  char v240; // cl
  __int64 v241; // rcx
  char v242; // cl
  unsigned __int8 v243; // al
  int v244; // eax
  unsigned int v245; // eax
  int v246; // ebx
  int v247; // ebx
  __int64 v248; // rbx
  __int64 v249; // rdi
  int v250; // edx
  int v251; // eax
  const char *v252; // rax
  __int64 v253; // rbx
  unsigned __int64 v254; // rax
  unsigned __int64 v255; // rdx
  int v256; // r8d
  unsigned __int8 v257; // cf
  __int64 v258; // rdi
  __int64 **v259; // rcx
  __int64 *v260; // rbx
  __int64 v261; // rsi
  __int64 v262; // rax
  int v263; // ebx
  int v264; // ebx
  int v265; // ebx
  int v266; // ebx
  __int64 v267; // rax
  __int64 *v268; // rax
  __int64 v269; // rcx
  __int64 v270; // rcx
  __int64 v271; // rax
  __int64 v272; // rax
  int v273; // eax
  __int64 v274; // rdx
  int v275; // eax
  int v276; // ebx
  int v277; // ebx
  int v278; // ebx
  __int64 v279; // rax
  __int64 v280; // rdx
  __int64 v281; // rbx
  __int64 v282; // rcx
  __int64 v283; // rbx
  int v284; // edi
  __int16 v285; // si
  __int16 v286; // si
  __int64 v287; // rdi
  __int64 v288; // rbx
  int v289; // ebx
  int v290; // ebx
  int v291; // ebx
  int v292; // ebx
  __int64 v293; // r8
  __int64 v294; // rdx
  __int64 v295; // rcx
  int v296; // esi
  __int64 v297; // rdi
  __int64 mm; // rbx
  __int16 v299; // ax
  int v300; // esi
  __int64 v301; // rdi
  __int64 v302; // rbx
  int v303; // ebx
  int v304; // ebx
  int v305; // ebx
  __int64 v306; // rbx
  _QWORD *v307; // rbx
  __int64 v308; // rax
  __int64 v309; // rax
  __int64 v310; // rsi
  int v311; // eax
  __int64 v312; // r8
  int v313; // ecx
  int v314; // edx
  __int64 v315; // r15
  int v316; // r12d
  __int64 v317; // r14
  int v318; // ebx
  int v319; // ebx
  int v320; // ebx
  int v321; // ebx
  char *v322; // rdi
  char v323; // al
  __int64 i; // rbx
  __int16 v325; // cx
  __int16 v326; // cx
  __int64 v327; // r15
  __int64 v328; // r14
  __int64 v329; // rdi
  int v330; // esi
  bool v331; // zf
  __int16 v332; // ax
  __int64 v333; // rax
  unsigned int v334; // r15d
  __int64 v335; // rbx
  unsigned int *v336; // r12
  int v337; // eax
  __int64 v338; // rdi
  __int64 v339; // rdx
  int v340; // eax
  unsigned int v341; // eax
  unsigned int *v342; // r14
  unsigned __int8 *Payload; // rcx
  __int64 v344; // rcx
  int v345; // eax
  int *v346; // rdi
  unsigned int v347; // eax
  int Varint32; // eax
  unsigned __int16 *v349; // rsi
  __int64 v350; // rcx
  __int64 v351; // rax
  __int64 v352; // r15
  unsigned int v353; // r13d
  unsigned __int8 *v354; // rdi
  unsigned __int64 v355; // rsi
  unsigned __int64 v356; // r12
  unsigned int *v357; // rcx
  __int64 v358; // rax
  __int64 v359; // rdx
  int v360; // eax
  __int64 v361; // rax
  __int64 v362; // rdi
  const void *v363; // rsi
  size_t v364; // rbx
  __int64 v365; // rdx
  char v366; // al
  unsigned int v367; // eax
  unsigned int v368; // eax
  __int64 v369; // rax
  unsigned int *v370; // rdx
  int v371; // eax
  __int64 v372; // r15
  int *v373; // r12
  int v374; // r14d
  _BYTE *v375; // rdi
  int *v376; // rsi
  __int64 *v377; // rbx
  __int16 v378; // ax
  int *j; // rbx
  __int16 v380; // cx
  unsigned __int64 v381; // rdx
  int v382; // edx
  __int64 v383; // rax
  __int64 v384; // rcx
  __int64 v385; // rax
  double v386; // xmm0_8
  unsigned int v387; // edi
  unsigned int v388; // esi
  __int64 v389; // rax
  int v390; // ecx
  unsigned __int64 v391; // rax
  __int64 v392; // rbx
  int v393; // edx
  unsigned __int64 v394; // rax
  int v395; // ecx
  unsigned __int64 v396; // rax
  __int64 v397; // rdi
  unsigned int *v398; // r15
  _BYTE *v399; // rbx
  _BYTE *v400; // rsi
  _BYTE *v401; // rdi
  __int64 v402; // rbx
  __int64 v403; // rax
  unsigned __int64 v404; // rdx
  __int64 v405; // r8
  __int64 v406; // rcx
  bool v407; // zf
  int v408; // ebx
  int v409; // ebx
  int v410; // ebx
  int v411; // ebx
  __int64 v412; // rdi
  __int64 v413; // rdx
  __int64 v414; // rsi
  __int64 v415; // rdi
  __int64 v416; // rbx
  __int64 v417; // rdi
  __int64 v418; // rbx
  unsigned int updated; // eax
  __int64 k; // rax
  __int64 v421; // rcx
  __int64 v422; // rdx
  __int64 v423; // rax
  __int64 v424; // rcx
  __int64 v425; // rax
  __int64 v426; // rcx
  __int64 *v427; // rax
  int v428; // ebx
  int v429; // ebx
  int v430; // ebx
  __int64 v431; // rax
  __int64 v432; // rdi
  __int64 v433; // rsi
  __int64 v434; // r14
  __int16 v435; // dx
  unsigned __int8 v436; // bl
  int v437; // ecx
  __int64 v438; // rdx
  __int64 v439; // r8
  int v440; // ecx
  int v441; // ecx
  int v442; // ecx
  __int128 v443; // rax
  __int64 v444; // rbx
  __int64 v445; // rdx
  __int64 v446; // rax
  char v447; // cl
  __int64 v448; // rdx
  int v449; // ebx
  int v450; // ebx
  int v451; // r15d
  __int64 v452; // rcx
  __int64 v453; // r14
  __int64 v454; // rax
  __int64 v455; // r12
  __int64 *v456; // rdi
  int v457; // esi
  unsigned __int8 v458; // cl
  unsigned __int8 v459; // al
  __int64 v460; // rbx
  __int64 v461; // r8
  __int64 Cursor; // rax
  __int64 v463; // rcx
  unsigned int v464; // eax
  __int64 v465; // rax
  __int64 v466; // rdx
  __int64 v467; // r13
  __int16 v468; // r15
  __int64 v469; // rdi
  __int64 v470; // rbx
  int v471; // eax
  __int16 v472; // si
  int v473; // eax
  unsigned __int64 v474; // r14
  __int64 v475; // rax
  int v476; // eax
  __int16 v477; // ax
  double v478; // xmm6_8
  __int64 v479; // rdx
  double v480; // xmm0_8
  __int64 v481; // rbx
  __int64 v482; // rdx
  __int64 v483; // rax
  double v484; // xmm0_8
  __int16 v485; // ax
  __int64 v486; // rdi
  __int64 v487; // rbx
  int v488; // ebx
  int v489; // ebx
  int v490; // ebx
  int v491; // ebx
  __int64 v492; // rax
  __int64 v493; // rax
  __int64 v494; // r9
  __int64 v495; // rdx
  __int64 v496; // rbx
  int v497; // ecx
  __int64 v498; // rcx
  __int64 v499; // rax
  __int64 v500; // rdx
  __int64 v501; // rsi
  __int64 v502; // rdx
  __int64 v503; // rcx
  __int64 v504; // rax
  _QWORD *v505; // r14
  __int64 v506; // r12
  _DWORD *v507; // r15
  __int64 v508; // rdi
  unsigned int v509; // ebx
  __int64 v510; // rax
  __int64 v511; // rcx
  __int64 v512; // rbx
  __int64 v513; // rax
  int v514; // ecx
  __int64 v515; // rdx
  __int64 v516; // rcx
  int v517; // ebx
  int v518; // ebx
  int v519; // ebx
  __int64 v520; // rdx
  int v521; // eax
  __int64 v522; // rcx
  __int64 v523; // rax
  __int64 v524; // rbx
  int v525; // edi
  __int64 v526; // rax
  bool v527; // sf
  __int64 v528; // rcx
  unsigned int v529; // eax
  __int64 v530; // rax
  _QWORD *v531; // rax
  __int64 v532; // rdx
  int v533; // ebx
  int v534; // ebx
  int v535; // ebx
  int v536; // ebx
  int v537; // r14d
  __int64 v538; // rbx
  __int64 v539; // rsi
  void (__fastcall *v540)(_QWORD, _QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v541; // r8
  __int64 v542; // rcx
  __int64 v543; // rdx
  __int64 v544; // rax
  __int64 v545; // rbx
  __int64 v546; // r8
  __int64 v547; // rsi
  __int16 v548; // r8
  __int64 v549; // r9
  __int64 *v550; // rsi
  __int64 v551; // rdi
  int v552; // ebx
  __int64 v553; // rax
  __int64 v554; // rcx
  __int64 *v555; // rbx
  __int64 v556; // rax
  __int64 v557; // rcx
  __int64 v558; // r8
  __int64 v559; // rdx
  __int64 v560; // rax
  int v561; // ebx
  int v562; // ebx
  int v563; // ebx
  __int64 v564; // rdx
  __int64 v565; // rbx
  __int64 v566; // rax
  __int64 v567; // rax
  __int64 v568; // rdx
  __int64 v569; // rdi
  __int64 v570; // rcx
  __int64 v571; // rbx
  __int64 v572; // rax
  __int64 *v573; // rcx
  __int64 v574; // rbx
  __int64 v575; // rbx
  __int64 v576; // rdi
  unsigned int v577; // eax
  unsigned int v578; // eax
  int v579; // ebx
  int v580; // ebx
  int v581; // ebx
  __int64 v582; // rcx
  __int64 v583; // rax
  __int64 v584; // rbx
  __int64 v585; // rdx
  __int64 v586; // rcx
  __int64 v587; // rax
  _QWORD *v588; // rbx
  __int64 v589; // rdi
  __int64 v590; // rax
  __int64 v591; // rdx
  unsigned int v592; // eax
  __int64 v593; // rdi
  __int64 v594; // rbx
  __int64 v595; // rax
  __int64 v596; // rcx
  __int64 v597; // rdi
  __int64 v598; // rbx
  __int16 v599; // r8
  __int64 v600; // rcx
  __int64 v601; // r9
  __int64 v602; // rcx
  int v603; // ebx
  int v604; // ebx
  int v605; // ebx
  int v606; // ebx
  __int64 v607; // rax
  __int64 v608; // rcx
  _QWORD *v609; // rbx
  __int64 v610; // r8
  __int64 v611; // r9
  __int64 v612; // rcx
  __int64 v613; // rcx
  __int64 v614; // rcx
  __int64 v615; // rdx
  __int64 v616; // rax
  __int64 v617; // rdx
  __int64 v618; // rbx
  unsigned int v619; // edi
  __int64 v620; // rcx
  __int64 v621; // rdx
  __int64 v622; // rdi
  __int64 v623; // rcx
  __int64 v624; // rbx
  unsigned int inited; // eax
  int v626; // eax
  __int64 v627; // r8
  __int64 v628; // rax
  int v629; // ebx
  int v630; // ebx
  int v631; // ebx
  int v632; // ebx
  __int64 v633; // rax
  __int64 v634; // rdx
  int v635; // r8d
  __int64 v636; // rdi
  __int64 v637; // rbx
  __int64 v638; // r9
  unsigned int (__fastcall *v639)(_QWORD); // rax
  __int64 v640; // rbx
  int v641; // ebx
  int v642; // ebx
  int v643; // ebx
  __int64 v644; // rcx
  _QWORD *v645; // rdi
  _QWORD *v646; // rbx
  __int64 v647; // rax
  __int64 v648; // rax
  __int64 v649; // rdi
  __int64 v650; // rbx
  __int64 v651; // rsi
  __int64 v652; // rbx
  __int64 v653; // rdx
  __int64 v654; // rdx
  int v655; // ebx
  int v656; // ebx
  int v657; // ebx
  __int64 v658; // rbx
  __int64 v659; // rdi
  __int64 v660; // rbx
  __int64 v661; // rcx
  _DWORD *v662; // rbx
  __int64 v663; // r8
  int v664; // edx
  _DWORD *v665; // r8
  __int64 v666; // rax
  __int64 v667; // rdx
  int v668; // eax
  const char *v669; // rax
  int v670; // ebx
  int v671; // ebx
  int v672; // ebx
  __int64 v673; // rbx
  unsigned int v674; // eax
  __int64 v675; // rax
  __int64 v676; // rax
  int v677; // ebx
  int v678; // ebx
  int v679; // ebx
  int v680; // ebx
  int v681; // esi
  __int64 v682; // rbx
  __int64 v683; // rdi
  __int64 v684; // rcx
  __int64 v685; // rax
  __int64 v686; // rdi
  __int64 v687; // rax
  __int64 v688; // rbx
  __int64 **v689; // rax
  __int64 *v690; // rsi
  __int64 v691; // r14
  __int16 v692; // ax
  unsigned int v693; // eax
  const char *v694; // rax
  __int64 v695; // rdi
  _QWORD *v696; // rax
  _QWORD *v697; // rbx
  __int64 v698; // rax
  __int64 v699; // rax
  __int64 *v700; // rbx
  __int64 v701; // rdi
  __int64 v702; // r9
  __int64 v703; // rax
  int v704; // ebx
  int v705; // ebx
  int v706; // ebx
  char v707; // al
  __int64 v708; // rbx
  __int64 v709; // rbx
  int v710; // eax
  int m; // ecx
  __int64 v712; // rax
  __int64 v713; // rbx
  unsigned __int64 v714; // rax
  unsigned __int64 v715; // r8
  __int64 v716; // rdx
  __int64 v717; // rbx
  unsigned int Page; // eax
  const char *v719; // r8
  int v720; // ebx
  int v721; // ecx
  char v722; // al
  const char *v723; // rdx
  unsigned int v724; // eax
  int v725; // ecx
  unsigned int v726; // eax
  const char *v727; // rax
  __int64 v728; // r8
  const char *v729; // rax
  __int64 (__fastcall *v730)(_QWORD); // rax
  int v731; // eax
  __int64 v733; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v734; // [rsp+48h] [rbp-C0h]
  unsigned int v735; // [rsp+4Ch] [rbp-BCh]
  unsigned int Table; // [rsp+50h] [rbp-B8h]
  unsigned int v737; // [rsp+50h] [rbp-B8h]
  __int64 v738; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v739; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v740; // [rsp+68h] [rbp-A0h]
  __int64 v741; // [rsp+70h] [rbp-98h]
  __int64 v743; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v744; // [rsp+88h] [rbp-80h] BYREF
  __int64 v745; // [rsp+90h] [rbp-78h]
  __int64 v746; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v747; // [rsp+A0h] [rbp-68h] BYREF
  char v748; // [rsp+A4h] [rbp-64h]
  unsigned int *v749; // [rsp+A8h] [rbp-60h]
  __int128 v750; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v751; // [rsp+C0h] [rbp-48h]
  __int128 v752; // [rsp+D0h] [rbp-38h]
  int v753; // [rsp+E0h] [rbp-28h]
  int v754; // [rsp+E4h] [rbp-24h] BYREF
  __int64 v755; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v756; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v757; // [rsp+100h] [rbp-8h]
  __int128 v758; // [rsp+110h] [rbp+8h]
  __int64 v759; // [rsp+120h] [rbp+18h]
  __int128 v760; // [rsp+128h] [rbp+20h] BYREF
  __int128 v761; // [rsp+138h] [rbp+30h]
  __int128 v762; // [rsp+148h] [rbp+40h]
  __int64 v763; // [rsp+158h] [rbp+50h]
  _OWORD v764[2]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v765; // [rsp+180h] [rbp+78h]
  __int64 v766; // [rsp+190h] [rbp+88h]
  int v767; // [rsp+198h] [rbp+90h]
  __int64 v768; // [rsp+19Ch] [rbp+94h] BYREF

  v4 = *a1;
  v5 = a1;
  v6 = a1[17];
  v7 = (unsigned __int8 *)v6;
  v8 = a1[13];
  v9 = 0;
  LOBYTE(a4) = *(_BYTE *)(*a1 + 100);
  v734 = a4;
  v738 = v6;
  v745 = *a1;
  v748 = 0;
  v740 = 0;
  v741 = v8;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter();
    LOBYTE(a4) = v734;
    v6 = (__int64)v7;
    v9 = 0;
  }
  if ( *(_QWORD *)(v4 + 528) )
    v10 = (unsigned int)(*(_DWORD *)(v4 + 544) - *((_DWORD *)v5 + 57) % *(_DWORD *)(v4 + 544));
  else
    v10 = -1;
  v11 = 1;
  v739 = v10;
  if ( *((_DWORD *)v5 + 13) == 7 )
    goto LABEL_1511;
  *((_DWORD *)v5 + 13) = 0;
  v5[9] = 0;
  v12 = *(_DWORD *)(v4 + 408);
  *(_DWORD *)(v4 + 664) = 0;
  if ( v12 )
    goto LABEL_1504;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  Table = 0;
  v735 = 0;
  v7 = (unsigned __int8 *)(v6 + 24LL * *((int *)v5 + 12));
  v753 = 0;
LABEL_9:
  v16 = *v7;
  v743 = (__int64)v7;
  v740 = v11 + v9;
  if ( (unsigned int)v16 > 0x5A )
  {
    if ( (unsigned int)v16 <= 0x89 )
    {
      if ( (_DWORD)v16 == 137 )
      {
LABEL_322:
        v153 = *((int *)v7 + 1);
        v154 = v5[15];
        LODWORD(v743) = 0;
        v155 = *(_QWORD *)(v154 + 8 * v153);
        v156 = *(_QWORD *)(v155 + 48);
        if ( (_BYTE)v16 != 0x89
          || (v157 = *(_QWORD *)(v155 + 48),
              *(_DWORD *)(v155 + 36) = -1,
              !(unsigned int)sqlite3BtreeCursorIsValidNN(v157)) )
        {
          v15 = sqlite3BtreeLast(v156, &v743);
          Table = v15;
          *(_BYTE *)(v155 + 2) = v743;
          *(_BYTE *)(v155 + 3) = 0;
          *(_DWORD *)(v155 + 32) = 0;
          v13 = 0;
          if ( v15 )
            goto LABEL_279;
          if ( *((int *)v7 + 2) > 0 )
          {
            if ( (_DWORD)v743 )
              goto LABEL_215;
LABEL_52:
            v8 = v741;
            goto LABEL_53;
          }
          v8 = v741;
          goto LABEL_1347;
        }
LABEL_1344:
        v8 = v741;
        goto LABEL_1345;
      }
      if ( (unsigned int)v16 <= 0x72 )
      {
        if ( (_DWORD)v16 == 114 )
        {
          v486 = v8 + 56LL * *((int *)v7 + 1);
          v487 = v8 + 56LL * *((int *)v7 + 2);
          if ( (*(_WORD *)(v487 + 20) & 0x9000) != 0 )
          {
            vdbeMemClearExternAndSetNull(v8 + 56LL * *((int *)v7 + 2));
            v14 = v735;
            v11 = 1;
          }
          else
          {
            *(_WORD *)(v487 + 20) = v11;
          }
          if ( ((unsigned __int8)v11 & *(_BYTE *)(v486 + 20)) == 0 )
          {
            *(_WORD *)(v487 + 20) = 4;
            *(_QWORD *)v487 = ~sqlite3VdbeIntValue(v486, v14);
            goto LABEL_80;
          }
          goto LABEL_1342;
        }
        if ( (unsigned int)v16 <= 0x67 )
        {
          if ( (_DWORD)v16 == 103 )
            goto LABEL_866;
          if ( (unsigned int)v16 <= 0x61 )
          {
            if ( (_DWORD)v16 != 97 )
            {
              v318 = v16 - 91;
              if ( !v318 )
              {
                v129 = (int)sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 1), *((unsigned int *)v7 + 3))
                     ^ (unsigned __int64)*((int *)v7 + 4);
                v309 = v8 + 56LL * *((int *)v7 + 2);
                if ( (*(_WORD *)(v309 + 20) & 0x9000) == 0 )
                {
                  *(_QWORD *)v309 = v129;
                  *(_WORD *)(v309 + 20) = 4;
                  goto LABEL_982;
                }
                goto LABEL_608;
              }
              v319 = v318 - 1;
              if ( !v319 )
              {
                if ( ((unsigned __int8)v11 & *(_BYTE *)(56LL * *((int *)v7 + 1) + v8 + 20)) != 0
                  || ((unsigned __int8)v11 & *(_BYTE *)(56LL * *((int *)v7 + 3) + v8 + 20)) != 0 )
                {
                  v369 = v8 + 56LL * *((int *)v7 + 2);
                  if ( (*(_WORD *)(v369 + 20) & 0x9000) == 0 )
                  {
                    *(_WORD *)(v369 + 20) = v11;
                    goto LABEL_1431;
                  }
                  v131 = v8 + 56LL * *((int *)v7 + 2);
                  goto LABEL_248;
                }
                v308 = *((int *)v7 + 2);
LABEL_606:
                v309 = v8 + 56 * v308;
                if ( (*(_WORD *)(v309 + 20) & 0x9000) == 0 )
                {
                  *(_QWORD *)v309 = 0;
                  *(_WORD *)(v309 + 20) = 4;
                  goto LABEL_1431;
                }
                v129 = 0;
LABEL_608:
                v130 = v309;
                goto LABEL_244;
              }
              v320 = v319 - 2;
              if ( v320 )
              {
                v321 = v320 - 1;
                if ( v321 )
                {
                  if ( v321 != 1 )
                    goto LABEL_1431;
                  v322 = (char *)*((_QWORD *)v7 + 2);
                  v323 = *v322;
                  for ( i = v8 + 56LL * *((int *)v7 + 1); ; i += 56 )
                  {
                    LOBYTE(v6) = a4;
                    LOBYTE(v14) = v323;
                    applyAffinity(i, v14, v6);
                    if ( *v322 == 69 )
                    {
                      v325 = *(_WORD *)(i + 20);
                      if ( (v325 & 4) != 0 )
                      {
                        v14 = *(_QWORD *)i;
                        v6 = 0xFFFFFFFFFFFFLL;
                        if ( (unsigned __int64)(*(_QWORD *)i + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                        {
                          v326 = v325 & 0xFFF1 | 8;
                          *(double *)i = (double)(int)v14;
                        }
                        else
                        {
                          v326 = v325 & 0xFFDB | 0x20;
                        }
                        *(_WORD *)(i + 20) = v326;
                      }
                    }
                    LOBYTE(a4) = v734;
                    v11 = 1;
                    v323 = *++v322;
                    if ( !*v322 )
                      break;
                  }
                  v13 = 0;
LABEL_1353:
                  v14 = v735;
                  goto LABEL_1042;
                }
                v327 = *((_QWORD *)v7 + 2);
                v328 = *(_QWORD *)(v327 + 8);
                v329 = v8 + 56LL * *((int *)v7 + 1);
                v330 = 0;
                if ( *(__int16 *)(v327 + 54) <= 0 )
                {
                  v15 = Table;
                  v5 = a1;
                  v8 = v741;
                  goto LABEL_1430;
                }
                while ( (*(_BYTE *)(v328 + 24LL * v330 + 18) & 0x60) != 0 )
                {
                  if ( (*(_BYTE *)(v328 + 24LL * v330 + 18) & 0x20) == 0 )
                  {
                    if ( !*((_DWORD *)v7 + 3) )
                      break;
                    v329 += 56;
                  }
LABEL_671:
                  v330 += v11;
                  LOBYTE(a4) = v734;
                  if ( v330 >= *(__int16 *)(v327 + 54) )
                  {
                    v15 = Table;
                    v5 = a1;
                    v6 = v738;
                    goto LABEL_673;
                  }
                }
                LOBYTE(v14) = *(_BYTE *)(v328 + 24LL * v330 + 12);
                LOBYTE(v6) = a4;
                applyAffinity(v329, v14, v6);
                a4 = v329 + 20;
                v11 = 1;
                v14 = *(unsigned __int16 *)(v329 + 20);
                if ( (v14 & 1) != 0 )
                  goto LABEL_670;
                v6 = (*(_DWORD *)(v328 + 24LL * v330 + 8) >> 4) & 0xF;
                switch ( (*(_DWORD *)(v328 + 24LL * v330 + 8) >> 4) & 0xF )
                {
                  case 2:
                    v331 = (v14 & 0x10) == 0;
                    break;
                  case 3:
                  case 4:
                    v331 = (v14 & 4) == 0;
                    break;
                  case 5:
                    if ( (v14 & 4) != 0 )
                    {
                      v6 = 0xFFFFFFFFFFFFLL;
                      if ( (unsigned __int64)(*(_QWORD *)v329 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                      {
                        v332 = v14 | 8;
                        v14 = (unsigned __int16)v14 | 8u;
                        *(double *)v329 = (double)(int)*(_QWORD *)v329;
                      }
                      else
                      {
                        LOWORD(v14) = v14 | 0x20;
                        v332 = v14;
                      }
                      *(_WORD *)a4 = v14;
                      *(_WORD *)a4 = v332 & 0xFFFB;
                      goto LABEL_670;
                    }
                    v331 = (v14 & 0x28) == 0;
                    break;
                  case 6:
                    v331 = (v14 & 2) == 0;
                    break;
                  default:
LABEL_670:
                    v329 += 56;
                    goto LABEL_671;
                }
                if ( v331 )
                {
                  v727 = *(const char **)(v328 + 24LL * v330);
                  v5 = a1;
                  sqlite3VdbeError(
                    a1,
                    "cannot store %s value in %s column %s.%s",
                    off_1400AAE18[*((unsigned __int8 *)qword_1400B5170 + (v14 & 0x3F))],
                    off_1400C8180[(unsigned int)(v6 - 1)],
                    *(const char **)v327,
                    v727);
                  v15 = 3091;
                  goto LABEL_279;
                }
                goto LABEL_670;
              }
              v747 = 0;
              v760 = 0;
              v763 = 0;
              v333 = v5[15];
              v761 = 0;
              v762 = 0;
              v334 = *((_DWORD *)v7 + 2);
              v335 = *(_QWORD *)(v333 + 8LL * *((int *)v7 + 1));
LABEL_676:
              LODWORD(v744) = v334;
              while ( 1 )
              {
                v336 = *(unsigned int **)(v335 + 88);
                v337 = *((_DWORD *)v5 + 11);
                v749 = v336;
                if ( *(_DWORD *)(v335 + 32) == v337 )
                {
                  if ( !**(_BYTE **)(v335 + 48) )
                  {
                    v11 = 1;
LABEL_706:
                    v349 = (unsigned __int16 *)(v335 + 74);
                    if ( *(unsigned __int16 *)(v335 + 74) > v334 )
                    {
                      v359 = *(unsigned int *)(v335 + 4LL * v334 + 120);
                      v747 = *(_DWORD *)(v335 + 4LL * v334 + 120);
                    }
                    else
                    {
                      v346 = (int *)(v335 + 64);
                      if ( *(_DWORD *)(v335 + 64) >= *v336 )
                      {
                        v13 = 0;
                        v359 = 0;
                        v747 = 0;
                      }
                      else
                      {
                        v350 = *(_QWORD *)(v335 + 96);
                        v746 = v350;
                        if ( !v350 )
                        {
                          v760 = 0;
                          v761 = 0;
                          v763 = 0;
                          v762 = 0;
                          Table = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v335 + 48), *v336, &v760);
                          v15 = Table;
                          if ( Table )
                            goto LABEL_279;
                          v350 = *((_QWORD *)&v760 + 1);
LABEL_711:
                          v746 = v350;
                        }
                        v352 = *v349;
                        v11 = 1;
                        v353 = (unsigned int)v744;
                        v354 = (unsigned __int8 *)(v350 + (unsigned int)*v346);
                        v355 = v336[v352];
                        v356 = v350 + *v336;
                        v357 = v749;
                        do
                        {
                          v747 = *v354;
                          *(_DWORD *)(v335 + 4LL * (int)v352 + 120) = v747;
                          if ( v747 >= 0x80 )
                          {
                            v354 += (unsigned __int8)sqlite3GetVarint32(v354, &v747);
                            *(_DWORD *)(v335 + 4LL * (int)v352 + 120) = v747;
                            if ( v747 < 0x80 )
                              v358 = *((unsigned __int8 *)qword_1400B27A0 + v747);
                            else
                              v358 = (v747 - 12) >> 1;
                            v357 = v749;
                            v11 = 1;
                          }
                          else
                          {
                            ++v354;
                            v358 = *((unsigned __int8 *)qword_1400B27A0 + (unsigned __int8)v747);
                          }
                          v355 += v358;
                          LODWORD(v352) = v352 + 1;
                          v357[(int)v352] = v355;
                        }
                        while ( (unsigned int)v352 <= v353 && (unsigned __int64)v354 < v356 );
                        v7 = (unsigned __int8 *)v743;
                        if ( (unsigned __int64)v354 >= v356 )
                        {
                          if ( (unsigned __int64)v354 <= v356 && v355 == *(_DWORD *)(v335 + 104) )
                            goto LABEL_724;
LABEL_729:
                          v13 = 0;
                          if ( !*v357 )
                          {
                            LOWORD(v352) = 0;
                            LODWORD(v354) = v356;
                            goto LABEL_724;
                          }
                          if ( !*(_QWORD *)(v335 + 96) && ((WORD2(v761) & 0x9000) != 0 || (_DWORD)v762) )
                          {
                            vdbeMemClear(&v760);
                            v11 = 1;
                          }
LABEL_735:
                          v6 = v738;
                          v360 = *(_DWORD *)(v738 + 12);
                          if ( v360 > 0 )
                          {
                            v15 = Table;
                            v7 = (unsigned __int8 *)(v738 + 24LL * (v360 - 1));
                            goto LABEL_737;
                          }
                          v15 = sqlite3CorruptError(94959);
LABEL_278:
                          v5 = a1;
                          goto LABEL_279;
                        }
                        if ( v355 > *(unsigned int *)(v335 + 104) )
                          goto LABEL_729;
LABEL_724:
                        *(_DWORD *)(v335 + 64) = (_DWORD)v354 - v746;
                        v13 = 0;
                        *(_WORD *)(v335 + 74) = v352;
                        if ( !*(_QWORD *)(v335 + 96) && ((WORD2(v761) & 0x9000) != 0 || (_DWORD)v762) )
                        {
                          vdbeMemClear(&v760);
                          v359 = v747;
                          v11 = 1;
                          v336 = v749;
                          v334 = (unsigned int)v744;
                        }
                        else
                        {
                          v359 = v747;
                          v336 = v749;
                          v334 = (unsigned int)v744;
                        }
                      }
                      if ( *(unsigned __int16 *)(v335 + 74) <= v334 )
                      {
                        v8 = v741;
                        v361 = v741 + 56LL * *((int *)v7 + 3);
                        if ( v7[1] == 0xF6 )
                        {
                          sqlite3VdbeMemShallowCopy(v741 + 56LL * *((int *)v7 + 3), *((_QWORD *)v7 + 2), 0x2000);
                        }
                        else
                        {
                          if ( (*(_WORD *)(v361 + 20) & 0x9000) == 0 )
                          {
                            v15 = Table;
                            v5 = a1;
                            *(_WORD *)(v361 + 20) = 1;
                            goto LABEL_99;
                          }
                          vdbeMemClearExternAndSetNull(v741 + 56LL * *((int *)v7 + 3));
                        }
                        v15 = Table;
                        v5 = a1;
                        goto LABEL_53;
                      }
                    }
                    v8 = v741;
                    v362 = v741 + 56LL * *((int *)v7 + 3);
                    if ( (*(_WORD *)(v362 + 20) & 0x9000) != 0 )
                    {
                      vdbeMemClearExternAndSetNull(v741 + 56LL * *((int *)v7 + 3));
                      v359 = v747;
                    }
                    if ( *(_DWORD *)(v335 + 108) >= v336[v334 + 1] )
                    {
                      v363 = (const void *)(*(_QWORD *)(v335 + 96) + v336[v334]);
                      if ( (unsigned int)v359 < 0xC )
                      {
                        sqlite3VdbeSerialGet(*(_QWORD *)(v335 + 96) + v336[v334], v359, v362);
                        v15 = Table;
                        v5 = a1;
                        goto LABEL_79;
                      }
                      v364 = (unsigned int)(v359 - 12) >> 1;
                      *(_DWORD *)(v362 + 16) = v364;
                      *(_BYTE *)(v362 + 22) = v734;
                      v365 = (unsigned int)(v364 + 2);
                      if ( *(_DWORD *)(v362 + 32) >= (int)v365 )
                      {
                        *(_QWORD *)(v362 + 8) = *(_QWORD *)(v362 + 40);
                        goto LABEL_758;
                      }
                      v4 = v745;
                      if ( (int)v364 <= *(_DWORD *)(v745 + 136) )
                      {
                        *(_WORD *)(v362 + 20) = 1;
                        if ( !(unsigned int)sqlite3VdbeMemGrow(v362, v365, 0) )
                        {
LABEL_758:
                          memcpy_0(*(void **)(v362 + 8), v363, v364);
                          v15 = Table;
                          v5 = a1;
                          *(_BYTE *)(v364 + *(_QWORD *)(v362 + 8)) = 0;
                          v11 = 1;
                          *(_BYTE *)(*(_QWORD *)(v362 + 8) + v364 + 1) = 0;
                          *(_WORD *)(v362 + 20) = word_1400B133C[v747 & 1];
                          goto LABEL_563;
                        }
LABEL_1506:
                        v5 = a1;
LABEL_1510:
                        v10 = v739;
LABEL_1511:
                        sqlite3OomFault(v4);
                        sqlite3VdbeError(v5, "out of memory");
                        v15 = 7;
LABEL_280:
                        v143 = v740;
LABEL_281:
                        v144 = v745;
                        if ( *(_BYTE *)(v745 + 103) )
                        {
                          v15 = 7;
                        }
                        else if ( v15 == 8458 )
                        {
                          v15 = sqlite3CorruptError(100679);
                        }
                        if ( !v5[21] && v15 != 3082 )
                        {
                          v729 = (const char *)sqlite3ErrStr(v15);
                          sqlite3VdbeError(v5, "%s", v729);
                        }
                        *((_DWORD *)v5 + 13) = v15;
                        sqlite3SystemError(v144, v15);
                        sqlite3_log(
                          v15,
                          "statement aborts at %d: [%s] %s",
                          -1431655765 * ((__int64)&v7[-v738] >> 3),
                          (const char *)v5[31],
                          (const char *)v5[21]);
                        if ( *((_BYTE *)v5 + 199) == 2 )
                          sqlite3VdbeHalt(v5);
                        if ( v15 == 3082 )
                        {
                          sqlite3OomFault(v144);
                          goto LABEL_1522;
                        }
                        if ( v15 == 11 )
                        {
                          v49 = v144;
                          if ( !*(_BYTE *)(v144 + 101) )
                            *(_QWORD *)(v144 + 48) |= 0x200000000uLL;
                        }
                        else
                        {
LABEL_1522:
                          v49 = v144;
                        }
                        v15 = 1;
                        if ( v748 )
                        {
                          sqlite3ResetOneSchema(v49);
                          v49 = v144;
                        }
                        goto LABEL_1531;
                      }
LABEL_1492:
                      v5 = a1;
                      goto LABEL_1493;
                    }
                    *(_BYTE *)(v362 + 22) = v734;
                    v366 = v7[2] & 0xC0;
                    if ( v366 && (v366 == (char)0x80 || v747 >= 0xC && ((v747 & 1) == 0 || v366 == -64))
                      || (v747 < 0x80
                        ? (v367 = *((unsigned __int8 *)qword_1400B27A0 + v747))
                        : (v367 = (v747 - 12) >> 1),
                          !v367) )
                    {
                      sqlite3VdbeSerialGet(byte_1400B2300, v747, v362);
                      v15 = Table;
                      v5 = a1;
                      goto LABEL_80;
                    }
                    v5 = a1;
                    v368 = vdbeColumnFromOverflow(v335, v334, v747, v336[v334], *((_DWORD *)a1 + 11), v753, v362);
                    v13 = 0;
                    Table = v368;
                    v15 = v368;
                    if ( !v368 )
                      goto LABEL_53;
                    if ( v368 != 7 )
                    {
                      if ( v368 == 18 )
                        goto LABEL_1493;
LABEL_279:
                      v10 = v739;
                      goto LABEL_280;
                    }
LABEL_1509:
                    v4 = v745;
                    goto LABEL_1510;
                  }
                  v341 = sqlite3VdbeHandleMovedCursor(v335);
                }
                else
                {
                  if ( *(_BYTE *)(v335 + 2) )
                  {
                    if ( *(_BYTE *)v335 != 3 || *(int *)(v335 + 36) <= 0 )
                    {
                      v351 = v8 + 56LL * *((int *)v7 + 3);
                      if ( (*(_WORD *)(v351 + 20) & 0x9000) == 0 )
                      {
                        v15 = Table;
                        v11 = 1;
                        *(_WORD *)(v351 + 20) = 1;
                        goto LABEL_99;
                      }
                      vdbeMemClearExternAndSetNull(v8 + 56LL * *((int *)v7 + 3));
                      v15 = Table;
                      goto LABEL_53;
                    }
                    v342 = (unsigned int *)(v335 + 108);
                    v344 = 56LL * *(int *)(v335 + 36);
                    v345 = *(_DWORD *)(v344 + v8 + 16);
                    *(_DWORD *)(v335 + 108) = v345;
                    *(_DWORD *)(v335 + 104) = v345;
                    Payload = *(unsigned __int8 **)(v344 + v8 + 8);
LABEL_694:
                    v346 = (int *)(v335 + 64);
                    *(_QWORD *)(v335 + 96) = Payload;
                    *(_DWORD *)(v335 + 32) = *((_DWORD *)a1 + 11);
                    v347 = *Payload;
                    *v336 = v347;
                    if ( v347 >= 0x80 )
                    {
                      Varint32 = (unsigned __int8)sqlite3GetVarint32(*(_QWORD *)(v335 + 96), v336);
                      v11 = 1;
                    }
                    else
                    {
                      v11 = 1;
                      Varint32 = 1;
                    }
                    v349 = (unsigned __int16 *)(v335 + 74);
                    *v346 = Varint32;
                    *(_WORD *)(v335 + 74) = 0;
                    if ( *v342 >= *v336 )
                    {
                      v350 = *(_QWORD *)(v335 + 96);
                      goto LABEL_711;
                    }
                    v13 = 0;
                    *(_QWORD *)(v335 + 96) = 0;
                    *v342 = 0;
                    if ( *v336 <= 0x18003 && *v336 <= *(_DWORD *)(v335 + 104) )
                    {
                      v5 = a1;
                      goto LABEL_706;
                    }
                    goto LABEL_735;
                  }
                  v338 = *(_QWORD *)(v335 + 48);
                  if ( *(_BYTE *)(v335 + 3) )
                  {
                    v339 = *(_QWORD *)(v335 + 16);
                    if ( !v339 || (v340 = *(_DWORD *)(v339 + 4LL * (v334 + 1))) == 0 )
                    {
                      Table = sqlite3VdbeFinishMoveto(v335);
                      if ( Table )
                      {
LABEL_688:
                        v15 = Table;
                        goto LABEL_279;
                      }
LABEL_690:
                      getCellInfo(v338);
                      v342 = (unsigned int *)(v335 + 108);
                      *(_DWORD *)(v335 + 104) = *(_DWORD *)(v338 + 64);
                      Payload = (unsigned __int8 *)fetchPayload(v338, v335 + 108);
                      goto LABEL_694;
                    }
                    v335 = *(_QWORD *)(v335 + 40);
                    v334 = v340 - 1;
                    v13 = 0;
                    goto LABEL_676;
                  }
                  if ( !*(_BYTE *)v338 )
                    goto LABEL_690;
                  v341 = sqlite3VdbeHandleMovedCursor(v335);
                  v13 = 0;
                }
                Table = v341;
                if ( v341 )
                  goto LABEL_688;
              }
            }
            v370 = 0;
            v371 = *((_DWORD *)v7 + 2);
            v372 = 0;
            v373 = (int *)(v8 + 56LL * *((int *)v7 + 1));
            v749 = 0;
            v744 = (__int64 *)v373;
            v374 = 0;
            v375 = (_BYTE *)*((_QWORD *)v7 + 2);
            v376 = &v373[14 * (v371 - (int)v11)];
            LODWORD(v743) = *((_DWORD *)v7 + 3);
            v746 = (__int64)v376;
            if ( v375 )
            {
              v377 = (__int64 *)v373;
              do
              {
                LOBYTE(v370) = *v375;
                LOBYTE(v6) = a4;
                applyAffinity(v377, v370, v6);
                if ( *v375 == 69 )
                {
                  v378 = *((_WORD *)v377 + 10);
                  if ( (v378 & 4) != 0 )
                    *((_WORD *)v377 + 10) = v378 & 0xFFDB | 0x20;
                }
                LOBYTE(a4) = v734;
                v11 = 1;
                ++v375;
                v377 += 7;
              }
              while ( *v375 );
              v373 = (int *)v744;
              v370 = v749;
            }
            for ( j = v376; ; j -= 14 )
            {
              v380 = *((_WORD *)j + 10);
              if ( ((unsigned __int8)v380 & (unsigned __int8)v11) != 0 )
              {
                j[9] = (v380 & 0x400) != 0 ? 0xA : 0;
                v374 += v11;
                goto LABEL_825;
              }
              if ( (v380 & 0x24) != 0 )
                break;
              if ( (v380 & 8) != 0 )
              {
                v374 += v11;
                j[9] = 7;
                v372 += 8;
              }
              else
              {
                v387 = j[4];
                v388 = ((v380 & 2 | 0x18u) >> 1) + 2 * v387;
                if ( (v380 & 0x400) != 0 )
                {
                  v389 = *j;
                  v388 += 2 * v389;
                  if ( v372 )
                  {
                    if ( (unsigned int)sqlite3VdbeMemExpandBlob(j) )
                      goto LABEL_1508;
                    v387 += *j;
                    v11 = 1;
                  }
                  else
                  {
                    v749 = (unsigned int *)((char *)v370 + v389);
                  }
                }
                v390 = v11;
                v372 += v387;
                v391 = v388;
                while ( 1 )
                {
                  v391 >>= 7;
                  if ( !v391 )
                    break;
                  v390 += v11;
                }
                v374 += v390;
                j[9] = v388;
              }
LABEL_825:
              if ( j == v373 )
              {
                v392 = v741 + 56LL * (int)v743;
                if ( v374 <= 126 )
                  goto LABEL_835;
                v393 = v11;
                v394 = v374;
                while ( 1 )
                {
                  v394 >>= 7;
                  if ( !v394 )
                    break;
                  v393 += v11;
                }
                v374 += v393;
                v395 = v11;
                v396 = v374;
                while ( 1 )
                {
                  v396 >>= 7;
                  if ( !v396 )
                    break;
                  v395 += v11;
                }
                if ( v393 < v395 )
LABEL_835:
                  v374 += v11;
                v397 = v372 + v374;
                v398 = v749;
                if ( (__int64)v749 + v397 <= *(int *)(v392 + 32) )
                {
                  *(_QWORD *)(v392 + 8) = *(_QWORD *)(v392 + 40);
                  goto LABEL_840;
                }
                if ( (__int64)v749 + v397 > *(int *)(v745 + 136) )
                  goto LABEL_1492;
                if ( (unsigned int)sqlite3VdbeMemClearAndResize(v741 + 56LL * (int)v743, (unsigned int)v397) )
                  goto LABEL_1508;
LABEL_840:
                *(_DWORD *)(v392 + 16) = v397;
                *(_WORD *)(v392 + 20) = 16;
                if ( v398 )
                {
                  *(_DWORD *)v392 = (_DWORD)v398;
                  *(_WORD *)(v392 + 20) = 1040;
                }
                v399 = *(_BYTE **)(v392 + 8);
                v400 = &v399[v374];
                if ( v374 >= 128 )
                {
                  v401 = &v399[(int)sqlite3PutVarint(v399, v374)];
                }
                else
                {
                  *v399 = v374;
                  v401 = v399 + 1;
                }
                v402 = v746;
                while ( 2 )
                {
                  v403 = (unsigned int)v373[9];
                  if ( (unsigned int)v403 <= 7 )
                  {
                    v11 = 1;
                    *v401++ = v403;
                    if ( (_DWORD)v403 )
                    {
                      v404 = *(_QWORD *)v373;
                      v405 = *((unsigned __int8 *)qword_1400B27A0 + v403);
                      v406 = (unsigned int)(v405 - 1);
                      v407 = (_DWORD)v405 == 1;
                      while ( 1 )
                      {
                        v400[v406] = v404;
                        if ( v407 )
                          break;
                        v404 >>= 8;
                        v407 = (_DWORD)v406 == 1;
                        v406 = (unsigned int)(v406 - 1);
                      }
                      v400 += v405;
                    }
                    goto LABEL_859;
                  }
                  if ( (unsigned int)v403 >= 0x80 )
                  {
                    v401 += (int)sqlite3PutVarint(v401, (unsigned int)v373[9]);
                    if ( v373[4] )
                      goto LABEL_857;
LABEL_858:
                    v11 = 1;
                  }
                  else
                  {
                    v11 = 1;
                    *v401++ = v403;
                    if ( (unsigned int)v403 >= 0xE && v373[4] > 0 )
                    {
LABEL_857:
                      memcpy_0(v400, *((const void **)v373 + 1), v373[4]);
                      v400 += v373[4];
                      goto LABEL_858;
                    }
                  }
LABEL_859:
                  if ( v373 == (int *)v402 )
                  {
                    v15 = Table;
                    v5 = a1;
                    goto LABEL_1341;
                  }
                  v373 += 14;
                  continue;
                }
              }
              v370 = v749;
            }
            v381 = *(_QWORD *)j;
            if ( *(__int64 *)j < 0 )
              v381 = ~v381;
            v374 += v11;
            if ( v381 <= 0x7F )
            {
              if ( (v11 & *(_QWORD *)j) == *(_QWORD *)j && *((_BYTE *)a1 + 197) >= 4u )
              {
                v382 = v381 + 8;
              }
              else
              {
                v372 += v11;
                v382 = v11;
              }
              v383 = 36;
              v384 = (__int64)j;
              goto LABEL_813;
            }
            if ( v381 > 0x7FFF )
            {
              if ( v381 <= 0x7FFFFF )
              {
                v372 += 3;
                v382 = 3;
                goto LABEL_812;
              }
              if ( v381 > 0x7FFFFFFF )
              {
                if ( v381 > 0x7FFFFFFFFFFFLL )
                {
                  v372 += 8;
                  if ( (v380 & 0x20) != 0 )
                  {
                    v386 = (double)(int)*(_QWORD *)j;
                    v382 = 7;
                    *((_WORD *)j + 10) = v380 & 0xFFD7 | 8;
                    *(double *)j = v386;
                  }
                  else
                  {
                    v382 = 6;
                  }
                }
                else
                {
                  v372 += 6;
                  v382 = 5;
                }
                goto LABEL_812;
              }
              v385 = 4;
            }
            else
            {
              v385 = 2;
            }
            v372 += v385;
            v382 = v385;
LABEL_812:
            v384 = 36;
            v383 = (__int64)j;
LABEL_813:
            *(_DWORD *)(v384 + v383) = v382;
            goto LABEL_825;
          }
          v408 = v16 - 98;
          if ( !v408 )
          {
            v424 = *((int *)v7 + 1);
            v425 = v5[15];
            v746 = 0;
            v426 = *(_QWORD *)(v425 + 8 * v424);
            if ( *((_DWORD *)v7 + 3) )
            {
              v746 = sqlite3BtreeRowCountEst(*(_QWORD *)(v426 + 48));
            }
            else
            {
              Table = sqlite3BtreeCount(v4, *(_QWORD *)(v426 + 48), &v746);
              v15 = Table;
              if ( Table )
                goto LABEL_279;
            }
            v427 = (__int64 *)out2Prerelease(v5, v7);
            *v427 = v746;
            goto LABEL_1276;
          }
          v409 = v408 - 1;
          if ( !v409 )
          {
            v421 = *(_QWORD *)(v4 + 32);
            v422 = *((unsigned int *)v7 + 3);
            v423 = 32LL * *((int *)v7 + 1);
            LODWORD(v743) = 0;
            sqlite3BtreeGetMeta(*(_QWORD *)(v423 + v421 + 8), v422, &v743);
            v268 = (__int64 *)out2Prerelease(v5, v7);
            v269 = (int)v743;
            goto LABEL_541;
          }
          v410 = v409 - 1;
          if ( v410 )
          {
            v411 = v410 - 1;
            if ( v411 )
            {
              if ( v411 != 1 )
                goto LABEL_1431;
LABEL_866:
              v412 = v8 + 56LL * *((int *)v7 + 1);
              v413 = v8 + 56LL * *((int *)v7 + 2);
              v414 = 56LL * *((int *)v7 + 3) + v8;
              if ( ((unsigned __int8)(*(_BYTE *)(v413 + 20) | *(_BYTE *)(v412 + 20)) & (unsigned __int8)v11) != 0 )
              {
                if ( (*(_WORD *)(v414 + 20) & 0x9000) != 0 )
                {
                  vdbeMemClearExternAndSetNull(v414);
                  goto LABEL_79;
                }
                *(_WORD *)(v414 + 20) = v11;
LABEL_673:
                v8 = v741;
LABEL_674:
                v14 = v735;
                goto LABEL_1430;
              }
              v444 = sqlite3VdbeIntValue(v413, v413);
              v446 = sqlite3VdbeIntValue(v412, v445);
              v447 = *v7;
              v448 = v446;
              if ( *v7 == 102 )
              {
                v444 &= v446;
LABEL_909:
                v13 = 0;
LABEL_924:
                *(_QWORD *)v414 = v444;
                *(_WORD *)(v414 + 20) &= 0xF244u;
                *(_WORD *)(v414 + 20) |= 4u;
LABEL_981:
                v8 = v741;
                goto LABEL_982;
              }
              if ( v447 == 103 )
              {
                v444 |= v446;
                goto LABEL_909;
              }
              v13 = 0;
              if ( !v446 )
                goto LABEL_924;
              if ( v446 < 0 )
              {
                v447 = -47 - v447;
                if ( v446 <= -64 )
                  goto LABEL_915;
                v448 = -v446;
              }
              if ( v448 < 64 )
              {
                if ( v447 == 104 )
                {
                  v444 <<= v448;
                }
                else if ( v444 >= 0 )
                {
                  v444 = (unsigned __int64)v444 >> v448;
                }
                else
                {
                  v444 = ((unsigned __int64)v444 >> v448) | (-1LL << (64 - (unsigned __int8)v448));
                }
                goto LABEL_924;
              }
LABEL_915:
              if ( v444 >= 0 || v447 == 104 )
                v444 = 0;
              else
                v444 = -1;
              goto LABEL_924;
            }
            v415 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
            if ( v415 && *(_DWORD *)(v415 + 68) == *((_DWORD *)v7 + 2) )
            {
              v416 = *(_QWORD *)(v415 + 48);
              sqlite3_free(*(_QWORD *)(v416 + 24));
              v11 = 1;
              *(_QWORD *)(v416 + 24) = 0;
              *(_BYTE *)v416 = 1;
LABEL_941:
              v465 = *(_QWORD *)(v415 + 48);
              v13 = 0;
              *(_BYTE *)(v465 + 3) = v7[2] & 3;
              goto LABEL_174;
            }
LABEL_928:
            if ( (v5[25] & 3) == (_BYTE)v11 )
            {
              v15 = 516;
              goto LABEL_279;
            }
            v451 = *((_DWORD *)v7 + 3);
            v452 = *(_QWORD *)(v4 + 32);
            v453 = *((unsigned int *)v7 + 2);
            v454 = 32LL * v451;
            v455 = *(_QWORD *)(v454 + v452 + 8);
            if ( *v7 == 113 )
            {
              v456 = a1;
              v457 = *((_WORD *)v7 + 1) & 8 | 4;
              v458 = *(_BYTE *)(*(_QWORD *)(v454 + v452 + 24) + 112LL);
              if ( v458 < *((_BYTE *)a1 + 197) )
                *((_BYTE *)a1 + 197) = v458;
            }
            else
            {
              v457 = 0;
              v456 = a1;
            }
            if ( (v7[2] & 0x10) != 0 )
            {
              sqlite3VdbeMemIntegerify(v741 + 56 * v453);
              LODWORD(v453) = *(_DWORD *)(v741 + 56 * v453);
            }
            v459 = v7[1];
            if ( v459 == 0xF8 )
            {
              v460 = *((_QWORD *)v7 + 2);
              v461 = *(unsigned __int16 *)(v460 + 8);
            }
            else
            {
              v461 = 0;
              v460 = 0;
              if ( v459 == 0xFD )
                v461 = *((unsigned int *)v7 + 4);
            }
            Cursor = allocateCursor(v456, *((unsigned int *)v7 + 1), v461, 0);
            v415 = Cursor;
            if ( !Cursor )
              goto LABEL_1508;
            v463 = *(_QWORD *)(Cursor + 48);
            *(_DWORD *)(Cursor + 8) |= 4u;
            *(_BYTE *)(Cursor + 1) = v451;
            *(_BYTE *)(Cursor + 2) = 1;
            *(_DWORD *)(Cursor + 68) = v453;
            v464 = sqlite3BtreeCursor(v455, v453, v457, v460, v463);
            v5 = a1;
            v15 = v464;
            v8 = v741;
            v11 = 1;
            *(_QWORD *)(v415 + 56) = v460;
            Table = v464;
            *(_BYTE *)(v415 + 4) = v7[1] != 0xF8;
            goto LABEL_941;
          }
          v417 = *(_QWORD *)(v4 + 32);
          v418 = 32LL * *((int *)v7 + 1);
          updated = sqlite3BtreeUpdateMeta(
                      *(_QWORD *)(v418 + v417 + 8),
                      *((unsigned int *)v7 + 2),
                      *((unsigned int *)v7 + 3));
          v11 = 1;
          Table = updated;
          v15 = updated;
          if ( *((_DWORD *)v7 + 2) == 1 )
          {
            **(_DWORD **)(v418 + v417 + 24) = *((_DWORD *)v7 + 3) - *((unsigned __int16 *)v7 + 1);
            *(_DWORD *)(v4 + 44) |= 1u;
            sqlite3FkClearTriggerCache(v4, *((unsigned int *)v7 + 1));
            v11 = 1;
          }
          else if ( *((_DWORD *)v7 + 2) == 2 )
          {
            *(_BYTE *)(*(_QWORD *)(v418 + v417 + 24) + 112LL) = v7[12];
          }
          v13 = 0;
          if ( *((_DWORD *)v7 + 1) == 1 )
          {
            for ( k = *(_QWORD *)(v4 + 8); k; k = *(_QWORD *)(k + 16) )
            {
              *(_DWORD *)(k + 200) &= ~2u;
              *(_DWORD *)(k + 200) |= 1u;
            }
            *((_DWORD *)v5 + 50) &= 0xFFFFFFFC;
          }
LABEL_174:
          if ( !v15 )
            goto LABEL_99;
          goto LABEL_279;
        }
        if ( (unsigned int)v16 <= 0x6D )
        {
          if ( (_DWORD)v16 != 109 )
          {
            v428 = v16 - 104;
            if ( !v428 )
              goto LABEL_866;
            v429 = v428 - 1;
            if ( !v429 )
              goto LABEL_866;
            v430 = v429 - 1;
            if ( v430 && (unsigned int)(v430 - 1) > 1 )
              goto LABEL_1431;
          }
LABEL_892:
          v431 = *((int *)v7 + 1);
          v755 = 0;
          v432 = v8 + 56 * v431;
          v433 = 56LL * *((int *)v7 + 2) + v8;
          v434 = v741 + 56LL * *((int *)v7 + 3);
          v435 = *(_WORD *)(v433 + 20);
          if ( (*(_BYTE *)(v432 + 20) & (unsigned __int8)v435 & 4) == 0 )
          {
            if ( ((unsigned __int8)(*(_BYTE *)(v432 + 20) | v435) & (unsigned __int8)v11) != 0 )
            {
LABEL_1002:
              v13 = 0;
              goto LABEL_1003;
            }
            v436 = numericType(v432);
            if ( (v436 & (unsigned __int8)numericType(v433) & 4) == 0 )
              goto LABEL_985;
            v11 = 1;
          }
          v437 = *v7;
          v438 = *(_QWORD *)v433;
          v439 = *(_QWORD *)v432;
          v755 = *(_QWORD *)v433;
          v440 = v437 - 106;
          if ( v440 )
          {
            v441 = v440 - 1;
            if ( v441 )
            {
              v442 = v441 - 1;
              if ( v442 )
              {
                if ( v442 != 1 )
                {
                  v13 = 0;
                  if ( v439 )
                  {
                    v443 = v438;
                    if ( v439 == -1 )
                      v439 = v11;
                    v755 = v443 % v439;
                    goto LABEL_979;
                  }
                  goto LABEL_1000;
                }
                if ( !v439 )
                {
LABEL_1001:
                  v6 = v738;
                  goto LABEL_1002;
                }
                if ( v439 != -1 || v438 != 0x8000000000000000uLL )
                {
                  v475 = v438 / v439;
LABEL_977:
                  v755 = v475;
LABEL_978:
                  v13 = 0;
LABEL_979:
                  *(_QWORD *)v434 = v755;
                  v477 = *(_WORD *)(v434 + 20) & 0xF240 | 4;
LABEL_980:
                  *(_WORD *)(v434 + 20) = v477;
                  v5 = a1;
                  goto LABEL_981;
                }
LABEL_985:
                v478 = sqlite3VdbeRealValue(v432);
                v480 = sqlite3VdbeRealValue(v433);
                switch ( *v7 )
                {
                  case 'j':
                    v484 = v480 + v478;
                    goto LABEL_998;
                  case 'k':
                    v484 = v480 - v478;
                    goto LABEL_998;
                  case 'l':
                    v484 = v480 * v478;
                    goto LABEL_998;
                }
                if ( *v7 != 109 )
                {
                  v481 = sqlite3VdbeIntValue(v432, v479);
                  v483 = sqlite3VdbeIntValue(v433, v482);
                  v13 = 0;
                  v755 = v483;
                  if ( !v481 )
                  {
LABEL_1000:
                    v6 = v738;
LABEL_1003:
                    if ( (*(_WORD *)(v434 + 20) & 0x9000) == 0 )
                    {
                      v8 = v741;
                      v11 = 1;
                      v14 = v735;
                      *(_WORD *)(v434 + 20) = 1;
                      v5 = a1;
                      goto LABEL_1006;
                    }
                    vdbeMemClearExternAndSetNull(v434);
                    v5 = a1;
                    goto LABEL_52;
                  }
                  if ( v481 == -1 )
                    v481 = 1;
                  v484 = (double)(int)(v483 % v481);
LABEL_999:
                  if ( (*(_QWORD *)&v484 & 0xFFFFFFFFFFFFFLL) == 0
                    || (*(_QWORD *)&v484 & 0x7FF0000000000000LL) != 0x7FF0000000000000LL )
                  {
                    v485 = *(_WORD *)(v434 + 20);
                    *(double *)v434 = v484;
                    v477 = v485 & 0xF240 | 8;
                    goto LABEL_980;
                  }
                  goto LABEL_1000;
                }
                if ( v478 != 0.0 )
                {
                  v484 = v480 / v478;
LABEL_998:
                  v13 = 0;
                  goto LABEL_999;
                }
                goto LABEL_1001;
              }
              v476 = sqlite3MulInt64(&v755, v439);
            }
            else
            {
              v476 = sqlite3SubInt64(&v755, v439);
            }
            if ( !v476 )
              goto LABEL_978;
            goto LABEL_985;
          }
          if ( v439 < 0 )
          {
            if ( v438 < 0 && (__int64)(0x8000000000000001uLL - v438) > v439 + 1 )
              goto LABEL_985;
          }
          else if ( v438 > 0 && 0x7FFFFFFFFFFFFFFFLL - v438 < v439 )
          {
            goto LABEL_985;
          }
          v475 = v438 + v439;
          goto LABEL_977;
        }
        v449 = v16 - 110;
        if ( !v449 )
          goto LABEL_892;
        v450 = v449 - 1;
        if ( v450 )
        {
          if ( (unsigned int)(v450 - 1) > 1 )
            goto LABEL_1431;
          goto LABEL_928;
        }
        v466 = v743;
        v467 = v8 + 56LL * *((int *)v7 + 1);
        v468 = *(_WORD *)(v467 + 20);
        v469 = v8 + 56LL * *(int *)(v743 + 8);
        v470 = v8 + 56LL * *(int *)(v743 + 12);
        if ( ((unsigned __int8)(*(_BYTE *)(v469 + 20) | v468) & (unsigned __int8)v11) != 0 )
        {
          if ( (*(_WORD *)(v470 + 20) & 0x9000) != 0 )
          {
            vdbeMemClearExternAndSetNull(v470);
            v7 = (unsigned __int8 *)v743;
            v15 = Table;
            goto LABEL_80;
          }
          v7 = (unsigned __int8 *)v743;
          v15 = Table;
          *(_WORD *)(v470 + 20) = v11;
          goto LABEL_674;
        }
        if ( (v468 & 0x12) != 0 )
        {
          if ( (v468 & 0x400) == 0 )
            goto LABEL_952;
          v471 = sqlite3VdbeMemExpandBlob(v467);
        }
        else
        {
          LOBYTE(v466) = a4;
          v471 = sqlite3VdbeMemStringify(v467, v466, 0);
        }
        if ( v471 )
          goto LABEL_1507;
        v468 = *(_WORD *)(v467 + 20) & 0xFFFD;
LABEL_952:
        v472 = *(_WORD *)(v469 + 20);
        if ( (v472 & 0x12) != 0 )
        {
          if ( (v472 & 0x400) == 0 )
          {
LABEL_958:
            LODWORD(v474) = *(_DWORD *)(v469 + 16) + *(_DWORD *)(v467 + 16);
            if ( (int)v474 > *(_DWORD *)(v4 + 136) )
            {
              v7 = (unsigned __int8 *)v743;
              goto LABEL_1492;
            }
            if ( (unsigned int)sqlite3VdbeMemGrow(v470, (unsigned int)(v474 + 2), v470 == v469) )
            {
              v7 = (unsigned __int8 *)v743;
              goto LABEL_1506;
            }
            v474 = (int)v474;
            *(_WORD *)(v470 + 20) &= 0xF242u;
            *(_WORD *)(v470 + 20) |= 2u;
            if ( v470 != v469 )
            {
              memcpy_0(*(void **)(v470 + 8), *(const void **)(v469 + 8), *(int *)(v469 + 16));
              *(_WORD *)(v469 + 20) = v472;
            }
            memcpy_0(
              (void *)(*(_QWORD *)(v470 + 8) + *(int *)(v469 + 16)),
              *(const void **)(v467 + 8),
              *(int *)(v467 + 16));
            LOBYTE(a4) = v734;
            v11 = 1;
            *(_WORD *)(v467 + 20) = v468;
            if ( v734 > 1u )
              v474 = (int)v474 & 0xFFFFFFFFFFFFFFFEuLL;
            v13 = 0;
            v7 = (unsigned __int8 *)v743;
            v15 = Table;
            v8 = v741;
            v6 = v738;
            *(_BYTE *)(v474 + *(_QWORD *)(v470 + 8)) = 0;
            *(_BYTE *)(*(_QWORD *)(v470 + 8) + v474 + 1) = 0;
            *(_WORD *)(v470 + 20) |= 0x200u;
            *(_DWORD *)(v470 + 16) = v474;
            v5 = a1;
            *(_BYTE *)(v470 + 22) = v734;
            goto LABEL_220;
          }
          v473 = sqlite3VdbeMemExpandBlob(v469);
        }
        else
        {
          LOBYTE(v466) = v734;
          v473 = sqlite3VdbeMemStringify(v469, v466, 0);
        }
        if ( !v473 )
        {
          v472 = *(_WORD *)(v469 + 20) & 0xFFFD;
          goto LABEL_958;
        }
LABEL_1507:
        v7 = (unsigned __int8 *)v743;
        goto LABEL_1510;
      }
      if ( (unsigned int)v16 <= 0x7E )
      {
        if ( (_DWORD)v16 == 126 )
        {
          v531 = (_QWORD *)out2Prerelease(v5, v7);
          v11 = 1;
          *v531 = *(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 24LL);
          v532 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
          ++*(_QWORD *)(v532 + 24);
          goto LABEL_99;
        }
        if ( (unsigned int)v16 > 0x78 )
        {
          v517 = v16 - 121;
          if ( !v517 )
          {
            LOBYTE(a4) = 3;
            v530 = allocateCursor(v5, *((unsigned int *)v7 + 1), *((unsigned int *)v7 + 3), a4);
            if ( v530 )
            {
              v11 = 1;
              *(_BYTE *)(v530 + 2) = 1;
              *(_DWORD *)(v530 + 36) = *((_DWORD *)v7 + 2);
              *(_QWORD *)(v530 + 48) = &dword_1400C9234;
              *(_BYTE *)(v530 + 4) = 1;
              goto LABEL_99;
            }
            goto LABEL_1510;
          }
          v518 = v517 - 1;
          if ( !v518 )
          {
            if ( *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) )
            {
              sqlite3VdbeFreeCursorNN(v5);
              v6 = v738;
              v11 = 1;
            }
            *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) = 0;
            goto LABEL_100;
          }
          v519 = v518 - 2;
          if ( !v519 )
          {
            v522 = *((int *)v7 + 7);
            *(_QWORD *)&v752 = 0;
            v523 = v5[15];
            LODWORD(v743) = 0;
            v750 = 0;
            v751 = 0;
            v524 = *(_QWORD *)(v523 + 8 * v522);
            if ( **(_BYTE **)(v524 + 48) )
              goto LABEL_1431;
            v525 = *((_DWORD *)v7 + 1);
            *(_QWORD *)&v750 = *(_QWORD *)(v524 + 56);
            WORD6(v751) = *((_WORD *)v7 + 20);
            v526 = *((int *)v7 + 9);
            BYTE14(v751) = 0;
            *((_QWORD *)&v750 + 1) = v8 + 56 * v526;
            while ( 1 )
            {
              Table = sqlite3VdbeIdxKeyCompare(v4, v524, &v750, &v743);
              v15 = Table;
              if ( Table )
                goto LABEL_279;
              v527 = (int)v743 < 0;
              if ( (int)v743 > 0 )
              {
                if ( !*((_WORD *)v7 + 1) )
                {
                  v13 = 0;
                  goto LABEL_1088;
                }
                v527 = (int)v743 < 0;
              }
              if ( !v527 )
                goto LABEL_1192;
              if ( v525 <= 0 )
                goto LABEL_1345;
              v528 = *(_QWORD *)(v524 + 48);
              *(_DWORD *)(v524 + 32) = 0;
              v529 = sqlite3BtreeNext(v528, 0);
              v15 = v529;
              if ( v529 )
                break;
              --v525;
            }
            if ( v529 != 101 )
              goto LABEL_279;
            v13 = 0;
            v15 = 0;
            Table = 0;
LABEL_1088:
            v7 += 24;
            goto LABEL_215;
          }
          if ( v519 != 1 )
            goto LABEL_1431;
          v520 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
          v521 = *(unsigned __int16 *)(v520 + 12);
          if ( v521 >= *((_DWORD *)v7 + 2) )
          {
            if ( v521 > *((_DWORD *)v7 + 3) )
              *(_WORD *)(v520 + 12) = *((_WORD *)v7 + 6);
            v14 = v735;
            goto LABEL_1431;
          }
          *(_WORD *)(v520 + 12) = *((_WORD *)v7 + 4);
          goto LABEL_220;
        }
        if ( (_DWORD)v16 == 120 )
        {
          v515 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
          v516 = *(_QWORD *)(v515 + 24);
          *(_QWORD *)(v515 + 24) = v516 + 1;
          if ( !v516 )
            goto LABEL_184;
          goto LABEL_220;
        }
        v488 = v16 - 115;
        if ( !v488 )
        {
          v512 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 2));
          v513 = allocateCursor(v5, *((unsigned int *)v7 + 1), (unsigned int)*(__int16 *)(v512 + 72), 0);
          if ( v513 )
          {
            *(_DWORD *)(v513 + 8) |= 1u;
            *(_BYTE *)(v513 + 2) = 1;
            *(_QWORD *)(v513 + 56) = *(_QWORD *)(v512 + 56);
            *(_BYTE *)(v513 + 4) = *(_BYTE *)(v512 + 4);
            *(_DWORD *)(v513 + 68) = *(_DWORD *)(v512 + 68);
            v514 = *(_DWORD *)(v513 + 8) ^ (*(_DWORD *)(v512 + 8) ^ *(_DWORD *)(v513 + 8)) & 4;
            *(_DWORD *)(v513 + 8) = v514;
            *(_QWORD *)(v513 + 16) = *(_QWORD *)(v512 + 16);
            *(_DWORD *)(v513 + 8) = v514 | 8;
            *(_DWORD *)(v512 + 8) |= 8u;
            v15 = sqlite3BtreeCursor(
                    *(_QWORD *)(v513 + 16),
                    *(_DWORD *)(v513 + 68),
                    4,
                    *(_QWORD *)(v513 + 56),
                    *(_QWORD *)(v513 + 48));
            Table = v15;
            goto LABEL_53;
          }
          goto LABEL_1510;
        }
        v489 = v488 - 1;
        if ( !v489 )
          goto LABEL_1043;
        v490 = v489 - 1;
        if ( !v490 )
        {
          v493 = out2Prerelease(v5, v7);
          v495 = *((_QWORD *)v7 + 2);
          v496 = v493;
          if ( v495 )
          {
            v498 = -1;
            do
              ++v498;
            while ( *(_BYTE *)(v495 + v498) );
            v497 = v498 & 0x3FFFFFFF;
          }
          else
          {
            v497 = 0;
          }
          *((_DWORD *)v7 + 1) = v497;
          if ( v734 == 1 )
          {
            v13 = 0;
          }
          else
          {
            LOBYTE(v494) = 1;
            Table = sqlite3VdbeMemSetStr(v493, v495, -1, v494, 0);
            v15 = Table;
            if ( Table )
              goto LABEL_1493;
            v13 = 0;
            if ( (unsigned int)sqlite3VdbeChangeEncoding(v496, v734) )
              goto LABEL_1510;
            *(_DWORD *)(v496 + 32) = 0;
            *(_WORD *)(v496 + 20) |= 0x2000u;
            if ( v7[1] == 0xFA && *((_QWORD *)v7 + 2) )
              sqlite3DbFreeNN(v4);
            v7[1] = -6;
            *((_QWORD *)v7 + 2) = *(_QWORD *)(v496 + 8);
            v497 = *(_DWORD *)(v496 + 16);
            *((_DWORD *)v7 + 1) = v497;
          }
          if ( v497 > *(_DWORD *)(v4 + 136) )
          {
LABEL_1493:
            sqlite3VdbeError(v5, "string or blob too big");
            v15 = 18;
            goto LABEL_279;
          }
          *v7 = 73;
LABEL_1039:
          v499 = out2Prerelease(v5, v7);
          LOBYTE(a4) = v734;
          v11 = 1;
          *(_WORD *)(v499 + 20) = 8706;
          *(_QWORD *)(v499 + 8) = *((_QWORD *)v7 + 2);
          *(_DWORD *)(v499 + 16) = *((_DWORD *)v7 + 1);
          *(_BYTE *)(v499 + 22) = v734;
          if ( *((int *)v7 + 3) > 0 )
          {
            v14 = v735;
            if ( *(_QWORD *)(56LL * *((int *)v7 + 3) + v8) == *((unsigned __int16 *)v7 + 1) )
              *(_WORD *)(v499 + 20) = 8720;
            goto LABEL_1042;
          }
          goto LABEL_1353;
        }
        v491 = v490 - 1;
        if ( !v491 )
        {
LABEL_1043:
          if ( *((int *)v7 + 3) > 0 )
          {
            *(_DWORD *)(56LL * *((int *)v7 + 3) + v8 + 16) = 0;
            *(_QWORD *)(56LL * *((int *)v7 + 3) + v8 + 8) = &dword_1400ACDEC;
          }
          v500 = *((int *)v7 + 1);
          v501 = *(_QWORD *)(v5[15] + 8 * v500);
          if ( !v501 || (*(_BYTE *)(v501 + 8) & 8) != 0 || *((_DWORD *)v7 + 2) > *(__int16 *)(v501 + 72) )
          {
            v504 = allocateCursor(v5, v500, *((unsigned int *)v7 + 2), 0);
            v501 = v504;
            if ( !v504 )
              goto LABEL_1510;
            v505 = (_QWORD *)(v504 + 16);
            *(_DWORD *)(v504 + 8) |= 1u;
            LODWORD(v733) = *((unsigned __int16 *)v7 + 1) | 5;
            v15 = sqlite3BtreeOpen(*(_QWORD *)v4, 0, v4, v504 + 16, v733, 1054);
            if ( v15 )
              goto LABEL_278;
            Table = sqlite3BtreeBeginTrans(*v505, 1, 0);
            v15 = Table;
            if ( !Table )
            {
              v506 = *((_QWORD *)v7 + 2);
              v507 = (_DWORD *)(v501 + 68);
              *(_QWORD *)(v501 + 56) = v506;
              if ( v506 )
              {
                v508 = *v505;
                v509 = *((unsigned __int16 *)v7 + 1) | 2;
                sqlite3BtreeEnter(*v505);
                Table = btreeCreateTable(v508, v501 + 68, v509);
                sqlite3BtreeLeave(v508);
                v13 = 0;
                if ( Table )
                {
                  v15 = Table;
                }
                else
                {
                  v15 = sqlite3BtreeCursor(*v505, *v507, 4, v506, *(_QWORD *)(v501 + 48));
                  Table = v15;
                }
                *(_BYTE *)(v501 + 4) = 0;
              }
              else
              {
                v510 = *(_QWORD *)(v501 + 48);
                v511 = *v505;
                *v507 = 1;
                v15 = sqlite3BtreeCursor(v511, 1, 4, 0, v510);
                Table = v15;
                *(_BYTE *)(v501 + 4) = 1;
              }
            }
            *(_DWORD *)(v501 + 8) = *(_DWORD *)(v501 + 8) & 0xFFFFFFFB | (*((_WORD *)v7 + 1) != 8 ? 4 : 0);
            if ( v15 )
            {
              sqlite3BtreeClose(*(_QWORD *)(v501 + 16));
              goto LABEL_278;
            }
            v5 = a1;
          }
          else
          {
            v502 = *(unsigned int *)(v501 + 68);
            v503 = *(_QWORD *)(v501 + 16);
            *(_QWORD *)(v501 + 24) = 0;
            *(_DWORD *)(v501 + 32) = 0;
            Table = sqlite3BtreeClearTable(v503, v502, 0);
            v15 = Table;
            if ( Table )
              goto LABEL_279;
          }
          v11 = 1;
          *(_BYTE *)(v501 + 2) = 1;
          goto LABEL_98;
        }
        if ( v491 != 1 )
          goto LABEL_1431;
        LOBYTE(a4) = v11;
        v492 = allocateCursor(v5, *((unsigned int *)v7 + 1), *((unsigned int *)v7 + 2), a4);
        if ( !v492 )
          goto LABEL_1510;
        *(_QWORD *)(v492 + 56) = *((_QWORD *)v7 + 2);
        v63 = sqlite3VdbeSorterInit(v4, *((unsigned int *)v7 + 3), v492);
        goto LABEL_155;
      }
      if ( (unsigned int)v16 <= 0x84 )
      {
        if ( (_DWORD)v16 == 132 )
        {
          v557 = v5[15];
          v558 = *((unsigned int *)v7 + 4);
          v559 = 56LL * *((int *)v7 + 3);
          v560 = *((int *)v7 + 1);
          LODWORD(v743) = 0;
          Table = sqlite3VdbeSorterCompare(*(_QWORD *)(v557 + 8 * v560), v8 + v559, v558, &v743);
          v15 = Table;
          if ( Table )
            goto LABEL_279;
          v100 = (_DWORD)v743 == 0;
          v11 = 1;
          goto LABEL_198;
        }
        v533 = v16 - 127;
        if ( !v533 )
        {
          v743 = 0;
          LODWORD(v744) = 0;
          v550 = (__int64 *)out2Prerelease(v5, v7);
          v551 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
          if ( (*(_BYTE *)(v551 + 8) & 2) != 0 )
          {
            v552 = 0;
          }
          else
          {
            v552 = 0;
            Table = sqlite3BtreeLast(*(_QWORD *)(v551 + 48), &v744);
            v15 = Table;
            if ( Table )
              goto LABEL_279;
            if ( (_DWORD)v744 )
            {
              v743 = 1;
            }
            else
            {
              v553 = sqlite3BtreeIntegerKey(*(_QWORD *)(v551 + 48));
              v743 = v553;
              if ( v553 == 0x7FFFFFFFFFFFFFFFLL )
                *(_DWORD *)(v551 + 8) |= 2u;
              else
                v743 = v553 + 1;
            }
          }
          if ( *((_DWORD *)v7 + 3) )
          {
            v554 = v5[33];
            if ( v554 )
            {
              while ( *(_QWORD *)(v554 + 8) )
                v554 = *(_QWORD *)(v554 + 8);
              v555 = (__int64 *)(*(_QWORD *)(v554 + 24) + 56LL * *((int *)v7 + 3));
            }
            else
            {
              v555 = (__int64 *)(v741 + 56LL * *((int *)v7 + 3));
            }
            sqlite3VdbeMemIntegerify(v555);
            if ( *v555 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v551 + 8) & 2) != 0 )
            {
              v15 = 13;
              goto LABEL_279;
            }
            v556 = v743;
            if ( v743 < *v555 + 1 )
            {
              v556 = *v555 + 1;
              v743 = v556;
            }
            *v555 = v556;
            v552 = 0;
          }
          if ( (*(_BYTE *)(v551 + 8) & 2) != 0 )
          {
            while ( 1 )
            {
              sqlite3_randomness(8, &v743);
              v743 = (v743 & 0x3FFFFFFFFFFFFFFFLL) + 1;
              Table = sqlite3BtreeTableMoveto(*(_QWORD *)(v551 + 48), v743, 0, &v744);
              v15 = Table;
              if ( Table )
                goto LABEL_279;
              if ( (_DWORD)v744 )
                break;
              if ( ++v552 >= 100 )
              {
                v15 = 13;
                goto LABEL_279;
              }
            }
          }
          *(_BYTE *)(v551 + 3) = 0;
          *(_DWORD *)(v551 + 32) = 0;
          *v550 = v743;
          goto LABEL_79;
        }
        v534 = v533 - 1;
        if ( v534 )
        {
          v535 = v534 - 1;
          if ( v535 )
          {
            v536 = v535 - 1;
            if ( !v536 )
            {
              v537 = *((_DWORD *)v7 + 2);
              v538 = *(_QWORD *)(a1[15] + 8LL * *((int *)v7 + 1));
              if ( v7[1] == 0xFB && *(_QWORD *)(v4 + 320) )
              {
                v13 = (_QWORD *)*((_QWORD *)v7 + 2);
                v539 = *(_QWORD *)(32LL * *(char *)(v538 + 1) + *(_QWORD *)(v4 + 32));
                if ( (v7[2] & 2) != 0 && *(_BYTE *)(v538 + 4) )
                  *(_QWORD *)(v538 + 80) = sqlite3BtreeIntegerKey(*(_QWORD *)(v538 + 48));
              }
              else
              {
                v539 = 0;
              }
              LOBYTE(v14) = v7[2];
              Table = sqlite3BtreeDelete(*(_QWORD *)(v538 + 48), v14);
              *(_QWORD *)(v538 + 32) = 0;
              v15 = Table;
              if ( Table )
              {
LABEL_139:
                v5 = a1;
                goto LABEL_279;
              }
              v11 = 1;
              ++v753;
              v64 = (v537 & 1) == 0;
              v5 = a1;
              if ( v64 )
                goto LABEL_1341;
              ++a1[7];
              v540 = *(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _QWORD))(v4 + 320);
              if ( !v540 || !v13 || *((char *)v13 + 48) < 0 )
                goto LABEL_1341;
              v540(*(_QWORD *)(v4 + 312), Table + 9, v539, *v13, *(_QWORD *)(v538 + 80));
              goto LABEL_79;
            }
            if ( v536 != 1 )
              goto LABEL_1431;
            sqlite3VdbeSetChanges(v4, v5[7]);
            v5[7] = 0;
            goto LABEL_53;
          }
          if ( *((_DWORD *)v7 + 3) )
            v541 = *(_QWORD *)(56LL * *((int *)v7 + 3) + v8);
          else
            v541 = 0;
          v63 = sqlite3BtreeTransferRow(
                  *(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 48LL),
                  *(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 2)) + 48LL),
                  v541);
          goto LABEL_155;
        }
        v542 = *((int *)v7 + 1);
        v543 = 56LL * *((int *)v7 + 2);
        v750 = 0;
        v751 = 0;
        v544 = v5[15];
        v752 = 0;
        v545 = *(_QWORD *)(v544 + 8 * v542);
        v64 = v7[1] == 0xFB;
        v546 = *(_QWORD *)(56LL * *((int *)v7 + 3) + v8);
        *((_QWORD *)&v750 + 1) = v546;
        if ( v64 && *(_QWORD *)(v4 + 320) )
        {
          v13 = (_QWORD *)*((_QWORD *)v7 + 2);
          v547 = *(_QWORD *)(32LL * *(char *)(v545 + 1) + *(_QWORD *)(v4 + 32));
        }
        else
        {
          v547 = 0;
        }
        if ( ((unsigned __int8)v11 & v7[2]) != 0 )
        {
          v5[7] += v11;
          if ( (v7[2] & 0x20) != 0 )
            *(_QWORD *)(v4 + 56) = v546;
        }
        v548 = *((_WORD *)v7 + 1);
        *(_QWORD *)&v751 = *(_QWORD *)(v543 + v741 + 8);
        DWORD1(v752) = *(_DWORD *)(v543 + v741 + 16);
        if ( (v548 & 0x10) != 0 )
          v549 = *(unsigned int *)(v545 + 36);
        else
          v549 = 0;
        if ( (*(_WORD *)(v543 + v741 + 20) & 0x400) != 0 )
          DWORD2(v752) = *(_DWORD *)(v543 + v741);
        else
          DWORD2(v752) = 0;
        *(_QWORD *)&v750 = 0;
        v15 = sqlite3BtreeInsert(*(_QWORD *)(v545 + 48), &v750, (unsigned __int8)v548 & 0x8A, v549);
        Table = v15;
        *(_BYTE *)(v545 + 3) = 0;
        *(_DWORD *)(v545 + 32) = 0;
        if ( v15 )
          goto LABEL_279;
        v11 = 1;
        ++v753;
        if ( !v13 )
        {
LABEL_1341:
          v8 = v741;
          v14 = v735;
LABEL_1342:
          v13 = 0;
LABEL_1343:
          LOBYTE(a4) = v734;
          goto LABEL_1042;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _QWORD))(v4 + 320))(
          *(_QWORD *)(v4 + 312),
          (v7[2] & 4) != 0 ? 23 : 18,
          v547,
          *v13,
          *((_QWORD *)&v750 + 1));
        goto LABEL_79;
      }
      v561 = v16 - 133;
      if ( !v561 )
      {
        Table = sqlite3VdbeSorterRowkey(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)), v8 + 56LL * *((int *)v7 + 2));
        v15 = Table;
        if ( Table )
          goto LABEL_279;
        *(_DWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 3)) + 32LL) = 0;
        goto LABEL_53;
      }
      v562 = v561 - 1;
      if ( !v562 )
      {
        v575 = out2Prerelease(v5, v7);
        v576 = *(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 48LL);
        v577 = sqlite3BtreePayloadSize(v576);
        if ( v577 > *(_DWORD *)(v4 + 136) )
          goto LABEL_1493;
        v578 = sqlite3VdbeMemFromBtreeZeroOffset(v576, v577, v575);
        v13 = 0;
        Table = v578;
        v15 = v578;
        if ( v578 )
          goto LABEL_279;
        if ( !*((_DWORD *)v7 + 3) && (*(_WORD *)(v575 + 20) & 0x4000) != 0 )
        {
          if ( !(unsigned int)sqlite3VdbeMemMakeWriteable(v575) )
            goto LABEL_53;
          goto LABEL_1510;
        }
        goto LABEL_1347;
      }
      v563 = v562 - 1;
      if ( v563 )
      {
        if ( v563 != 1 )
          goto LABEL_1431;
        v564 = *((int *)v7 + 1);
        v565 = *(_QWORD *)(v5[15] + 8 * v564);
        if ( !v565 )
        {
          LOBYTE(a4) = 3;
          v566 = allocateCursor(v5, v564, (unsigned int)v11, a4);
          v565 = v566;
          if ( !v566 )
            goto LABEL_1510;
          *(_DWORD *)(v566 + 8) |= 8u;
          *(_DWORD *)(v566 + 36) = 0;
          *(_BYTE *)(v566 + 4) = 1;
          *(_QWORD *)(v566 + 48) = sqlite3BtreeFakeValidCursor();
          v11 = 1;
        }
        *(_BYTE *)(v565 + 2) = v11;
        *(_DWORD *)(v565 + 32) = 0;
        if ( !*(_BYTE *)v565 )
        {
          sqlite3BtreeClearCursor(*(_QWORD *)(v565 + 48));
          goto LABEL_53;
        }
LABEL_1349:
        v14 = v735;
        goto LABEL_1343;
      }
      v746 = 0;
      v567 = out2Prerelease(v5, v7);
      v568 = *((int *)v7 + 1);
      v569 = v567;
      v570 = v5[15];
      v571 = *(_QWORD *)(v570 + 8 * v568);
      if ( *(_BYTE *)(v571 + 2) )
      {
LABEL_1172:
        v11 = 1;
        *(_WORD *)(v569 + 20) = 1;
        goto LABEL_60;
      }
      if ( *(_BYTE *)(v571 + 3) )
      {
        v572 = *(_QWORD *)(v571 + 80);
        goto LABEL_1181;
      }
      if ( *(_BYTE *)v571 == 2 )
      {
        v573 = *(__int64 **)(v571 + 48);
        v574 = *v573;
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*(_QWORD *)*v573 + 96LL))(v573, &v746);
        v15 = Table;
        sqlite3VtabImportErrmsg(v5, v574);
        if ( Table )
          goto LABEL_279;
        goto LABEL_1177;
      }
      Table = sqlite3VdbeCursorRestore(*(_QWORD *)(v570 + 8 * v568));
      v15 = Table;
      if ( Table )
        goto LABEL_279;
      if ( *(_BYTE *)(v571 + 2) )
        goto LABEL_1172;
      v572 = sqlite3BtreeIntegerKey(*(_QWORD *)(v571 + 48));
LABEL_1181:
      *(_QWORD *)v569 = v572;
      goto LABEL_80;
    }
    if ( (unsigned int)v16 > 0xA0 )
    {
      if ( (unsigned int)v16 <= 0xAB )
      {
        if ( (_DWORD)v16 == 171 )
        {
          v759 = 0;
          v675 = *((int *)v7 + 2);
          *(_QWORD *)&v757 = 0;
          v756 = 0;
          v758 = 0;
          *((_QWORD *)&v757 + 1) = v4;
          Table = sqlite3VdbeMemCopy(&v756, v8 + 56 * v675);
          v15 = Table;
          v676 = sqlite3_value_text(&v756);
          if ( v676 )
          {
            v15 = sqlite3VtabCallCreate(v4, *((unsigned int *)v7 + 1), v676, v5 + 21);
            Table = v15;
          }
          sqlite3VdbeMemRelease(&v756);
          goto LABEL_335;
        }
        if ( (unsigned int)v16 > 0xA6 )
        {
          v670 = v16 - 167;
          if ( !v670 )
          {
            sqlite3BtreeCursorPin(*(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 48LL));
            goto LABEL_53;
          }
          v671 = v670 - 1;
          if ( !v671 )
          {
            sqlite3BtreeCursorUnpin(*(_QWORD *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 48LL));
            goto LABEL_53;
          }
          v672 = v671 - 1;
          if ( v672 )
          {
            if ( v672 != 1 )
              goto LABEL_1431;
            v673 = *((_QWORD *)v7 + 2);
            Table = sqlite3VtabBegin(v4, v673);
            v15 = Table;
            if ( v673 )
              sqlite3VtabImportErrmsg(v5, *(_QWORD *)(v673 + 16));
            goto LABEL_335;
          }
          if ( v7[12] || (*(_QWORD *)(v4 + 48) & 0x400000000LL) == 0 )
          {
            v674 = sqlite3BtreeLockTable(
                     *(_QWORD *)(32LL * *((int *)v7 + 1) + *(_QWORD *)(v4 + 32) + 8),
                     *((unsigned int *)v7 + 2));
            Table = v674;
            v15 = v674;
            if ( !v674 )
              goto LABEL_53;
            if ( (_BYTE)v674 == 6 )
              sqlite3VdbeError(v5, "database table is locked: %s", *((_QWORD *)v7 + 2));
            goto LABEL_279;
          }
          goto LABEL_1042;
        }
        if ( (_DWORD)v16 == 166 )
        {
          if ( *((_DWORD *)v7 + 1) )
          {
            *((_DWORD *)v5 + 50) ^= ((unsigned __int8)*((_DWORD *)v5 + 50)
                                   ^ (unsigned __int8)(v11 + *((_DWORD *)v7 + 2)))
                                  & 3;
            goto LABEL_1431;
          }
          sqlite3ExpirePreparedStatements(v4, *((unsigned int *)v7 + 2));
          goto LABEL_53;
        }
        v655 = v16 - 161;
        if ( v655 && (v656 = v655 - 1) != 0 )
        {
          v657 = v656 - 1;
          if ( v657 )
          {
            if ( (unsigned int)(v657 - 1) > 1 )
              goto LABEL_1431;
            v658 = v8 + 56LL * *((int *)v7 + 1);
            if ( *((_DWORD *)v7 + 3) )
            {
              v15 = sqlite3VdbeMemAggValue(v658, v8 + 56LL * *((int *)v7 + 3), *((_QWORD *)v7 + 2));
              Table = v15;
              v658 = v8 + 56LL * *((int *)v7 + 3);
            }
            else
            {
              v15 = sqlite3VdbeMemFinalize(v658, *((_QWORD *)v7 + 2));
              Table = v15;
            }
            if ( !v15 )
            {
              sqlite3VdbeChangeEncoding(v658, v734);
              goto LABEL_53;
            }
            v728 = sqlite3_value_text(v658);
            sqlite3VdbeError(v5, "%s", v728);
            goto LABEL_279;
          }
        }
        else
        {
          v659 = *((unsigned __int16 *)v7 + 1);
          v660 = sqlite3DbMallocRawNN(v4, 8 * v659 + 104);
          if ( !v660 )
            goto LABEL_1510;
          *(_QWORD *)(v660 + 16) = 0;
          v661 = v660 + 8 * (v659 + 6);
          *(_QWORD *)v660 = v661;
          sqlite3VdbeMemInit(v661, v4, 1);
          v8 = v741;
          *(_QWORD *)(v660 + 8) = *((_QWORD *)v7 + 2);
          *(_BYTE *)(v660 + 42) = v659;
          *(_QWORD *)(v660 + 24) = v5;
          *(_BYTE *)(v660 + 41) = 0;
          v13 = 0;
          *(_DWORD *)(v660 + 36) = 0;
          *(_DWORD *)(v660 + 32) = -1431655765 * ((__int64)&v7[-v738] >> 3);
          *(_BYTE *)(v660 + 40) = v734;
          LODWORD(v11) = 1;
          *(_WORD *)v7 = -3677;
          *((_QWORD *)v7 + 2) = v660;
        }
        v662 = (_DWORD *)*((_QWORD *)v7 + 2);
        v663 = v8 + 56LL * *((int *)v7 + 3);
        if ( *((_QWORD *)v662 + 2) != v663 )
        {
          v664 = *((unsigned __int8 *)v662 + 42);
          *((_QWORD *)v662 + 2) = v663;
          while ( 1 )
          {
            v664 -= v11;
            if ( v664 < 0 )
              break;
            *(_QWORD *)&v662[2 * v664 + 12] = v8 + 56LL * (v664 + *((_DWORD *)v7 + 2));
          }
        }
        *(_DWORD *)(v663 + 16) += v11;
        v665 = v662 + 12;
        v666 = *((_QWORD *)v662 + 1);
        v667 = *((unsigned __int8 *)v662 + 42);
        if ( *((_DWORD *)v7 + 1) )
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v666 + 48))(v662, v667, v665);
        else
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v666 + 24))(v662, v667, v665);
        v668 = v662[9];
        if ( !v668 )
          goto LABEL_1347;
        if ( v668 > 0 )
        {
          v669 = (const char *)sqlite3_value_text(*(_QWORD *)v662);
          sqlite3VdbeError(v5, "%s", v669);
          v15 = v662[9];
          Table = v15;
        }
        if ( *((_BYTE *)v662 + 41) )
        {
          if ( *((_DWORD *)v7 - 5) )
            sqlite3VdbeMemSetInt64(v8 + 56LL * *((int *)v7 - 5), 1);
          *((_BYTE *)v662 + 41) = 0;
        }
        sqlite3VdbeMemRelease(*(_QWORD *)v662);
        v11 = 1;
        *(_WORD *)(*(_QWORD *)v662 + 20LL) = 1;
        v662[9] = 0;
        goto LABEL_174;
      }
      if ( (unsigned int)v16 > 0xB1 )
      {
        v704 = v16 - 178;
        if ( v704 )
        {
          v705 = v704 - 1;
          if ( !v705 )
          {
            *(_WORD *)(56LL * *((int *)v7 + 1) + v8 + 20) &= ~0x800u;
            goto LABEL_1431;
          }
          v706 = v705 - 1;
          if ( !v706 )
          {
            v713 = 56LL * *((int *)v7 + 1);
            v714 = filterHash(v8, v7);
            v715 = (v714 % (8 * *(_DWORD *)(v713 + v8 + 16))) >> 3;
            *(_BYTE *)(v715 + *(_QWORD *)(v713 + v8 + 8)) |= 1 << ((v714 % (8 * *(_DWORD *)(v713 + v8 + 16))) & 7);
            goto LABEL_53;
          }
          if ( v706 != 1 )
            goto LABEL_1431;
LABEL_1405:
          v707 = *(_BYTE *)(v4 + 110);
          if ( (v707 & 0x41) != 0 && *((_BYTE *)v5 + 197) != 0xFE )
          {
            a4 = *((_QWORD *)v7 + 2);
            if ( a4 || (a4 = v5[31]) != 0 )
            {
              if ( (v707 & 0x40) != 0 )
              {
                v708 = sqlite3VdbeExpandSql(v5, a4);
                (*(void (__fastcall **)(_QWORD, __int64))(v4 + 248))(*(_QWORD *)(v4 + 256), v708);
                sqlite3_free(v708);
              }
              else if ( *(_DWORD *)(v4 + 228) <= (int)v11 )
              {
                (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(v4 + 248))(
                  (unsigned int)v11,
                  *(_QWORD *)(v4 + 256),
                  v5);
              }
              else
              {
                v709 = sqlite3MPrintf(v4, "-- %s", (const char *)a4);
                (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v4 + 248))(
                  1,
                  *(_QWORD *)(v4 + 256),
                  v5,
                  v709);
                sqlite3DbFree(v4, v709);
              }
              v6 = v738;
              v14 = v735;
              v11 = 1;
            }
          }
          v710 = *((_DWORD *)v7 + 1);
          if ( v710 < dword_1400C8658 )
            goto LABEL_1422;
          if ( *v7 != 0xB5 )
          {
            for ( m = v11; m < *((_DWORD *)v5 + 36); m += v11 )
            {
              v712 = v5[17];
              if ( *(_BYTE *)(v712 + 24LL * m) == 15 )
                *(_DWORD *)(v712 + 24LL * m + 4) = 0;
            }
            v710 = 0;
LABEL_1422:
            *((_DWORD *)v7 + 1) = v710 + 1;
            *((_DWORD *)v5 + 59) += v11;
            goto LABEL_185;
          }
LABEL_1006:
          LOBYTE(a4) = v734;
          goto LABEL_1431;
        }
        v569 = out2Prerelease(v5, v7);
        v716 = 32LL * *((int *)v7 + 1);
        v717 = *(_QWORD *)(v716 + *(_QWORD *)(v4 + 32) + 8);
        Page = 0;
        if ( *((_DWORD *)v7 + 3) )
        {
          Page = sqlite3BtreeLastPage(*(_QWORD *)(v716 + *(_QWORD *)(v4 + 32) + 8));
          if ( Page < *((_DWORD *)v7 + 3) )
            Page = *((_DWORD *)v7 + 3);
        }
        v572 = (unsigned int)sqlite3BtreeMaxPageCount(v717, Page);
        goto LABEL_1181;
      }
      if ( (_DWORD)v16 == 177 )
      {
        v609 = (_QWORD *)out2Prerelease(v5, v7);
        v612 = (unsigned int)sqlite3BtreeLastPage(*(_QWORD *)(32LL * *((int *)v7 + 1) + *(_QWORD *)(v4 + 32) + 8));
        goto LABEL_1239;
      }
      v677 = v16 - 172;
      if ( v677 )
      {
        v678 = v677 - 1;
        if ( !v678 )
        {
          v699 = *((_QWORD *)v7 + 2);
          v743 = 0;
          v700 = *(__int64 **)(v699 + 16);
          if ( !v700 )
            goto LABEL_1468;
          v701 = *v700;
          if ( !*v700 )
            goto LABEL_1468;
          Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v701 + 48))(v700, &v743);
          v15 = Table;
          sqlite3VtabImportErrmsg(v5, v700);
          if ( Table )
            goto LABEL_279;
          LOBYTE(v702) = 2;
          *(_QWORD *)v743 = v700;
          v703 = allocateCursor(v5, *((unsigned int *)v7 + 1), 0, v702);
          if ( !v703 )
          {
            (*(void (__fastcall **)(__int64))(v701 + 56))(v743);
            goto LABEL_1510;
          }
          v11 = 1;
          *(_QWORD *)(v703 + 48) = v743;
          ++*((_DWORD *)v700 + 2);
LABEL_60:
          v14 = v735;
LABEL_61:
          v6 = v738;
          LOBYTE(a4) = v734;
LABEL_1430:
          v13 = 0;
          goto LABEL_1431;
        }
        v679 = v678 - 1;
        if ( v679 )
        {
          v680 = v679 - 1;
          if ( !v680 )
          {
            v684 = *((int *)v7 + 1);
            v766 = 0;
            v685 = v5[15];
            memset(v764, 0, sizeof(v764));
            v765 = 0;
            v686 = *(_QWORD *)(v685 + 8 * v684);
            v687 = *((int *)v7 + 3);
            v688 = v8 + 56 * v687;
            if ( *(_BYTE *)(v686 + 2) )
            {
              sqlite3VdbeMemSetNull(v8 + 56 * v687);
              goto LABEL_80;
            }
            v689 = *(__int64 ***)(v686 + 48);
            v690 = *v689;
            v691 = **v689;
            *(_QWORD *)&v764[0] = v688;
            BYTE8(v765) = a4;
            if ( ((unsigned __int8)v11 & v7[2]) != 0 )
            {
              sqlite3VdbeMemSetNull(v688);
              v692 = 1025;
              *(_DWORD *)v688 = 0;
            }
            else
            {
              v692 = v11 | *(_WORD *)(v688 + 20) & 0xF241;
            }
            *(_WORD *)(v688 + 20) = v692;
            v693 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v691 + 88))(
                     *(_QWORD *)(v686 + 48),
                     v764,
                     *((unsigned int *)v7 + 2));
            v5 = a1;
            Table = v693;
            v15 = v693;
            sqlite3VtabImportErrmsg(a1, v690);
            v13 = 0;
            if ( SDWORD1(v765) > 0 )
            {
              v694 = (const char *)sqlite3_value_text(v688);
              sqlite3VdbeError(a1, "%s", v694);
              v15 = DWORD1(v765);
              Table = DWORD1(v765);
            }
            sqlite3VdbeChangeEncoding(v688, v734);
            goto LABEL_51;
          }
          if ( v680 != 1 )
            goto LABEL_1431;
          v681 = *(_DWORD *)(v4 + 48);
          *(_QWORD *)(v4 + 48) |= 0x4000000uLL;
          v682 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
          v683 = v741 + 56LL * *((int *)v7 + 1);
          v15 = sqlite3VdbeChangeEncoding(v683, (unsigned int)v11);
          if ( v15 )
            goto LABEL_279;
          Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v682 + 152LL))(v682, *(_QWORD *)(v683 + 8));
          v15 = Table;
          if ( (v681 & 0x4000000) == 0 )
            *(_QWORD *)(v4 + 48) &= ~0x4000000uLL;
          sqlite3VtabImportErrmsg(v5, v682);
          *((_DWORD *)v5 + 50) &= 0xFFFFFFFC;
LABEL_50:
          v13 = 0;
LABEL_51:
          if ( v15 )
            goto LABEL_279;
          goto LABEL_52;
        }
        v695 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        v696 = (_QWORD *)sqlite3_malloc64(16);
        v697 = v696;
        if ( !v696 )
          goto LABEL_1510;
        *v696 = *(_QWORD *)(v695 + 48);
        v696[1] = v8 + 56LL * *((int *)v7 + 3);
        v698 = out2Prerelease(v5, v7);
        *(_WORD *)(v698 + 20) = 1;
        sqlite3VdbeMemSetPointer(v698, v697, "ValueList", sqlite3VdbeValueListFree);
LABEL_80:
        v13 = 0;
        goto LABEL_53;
      }
      *(_DWORD *)(v4 + 232) += v11;
      v63 = sqlite3VtabCallDestroy(v4, *((unsigned int *)v7 + 1), *((_QWORD *)v7 + 2));
      --*(_DWORD *)(v4 + 232);
    }
    else
    {
      if ( (_DWORD)v16 == 160 )
      {
        v651 = *((int *)v7 + 3);
        v652 = 56LL * *((int *)v7 + 1);
        v746 = 0;
        v569 = out2Prerelease(v5, v7);
        v746 = *(_QWORD *)(v652 + v741);
        if ( v746 <= 0 )
        {
          v8 = v741;
        }
        else
        {
          v653 = 56 * v651;
          v8 = v741;
          v654 = *(_QWORD *)(v653 + v741);
          if ( v654 <= 0 )
            v654 = 0;
          if ( !(unsigned int)sqlite3AddInt64(&v746, v654) )
          {
LABEL_1177:
            v572 = v746;
            goto LABEL_1181;
          }
        }
        *(_QWORD *)v569 = -1;
        goto LABEL_80;
      }
      if ( (unsigned int)v16 <= 0x95 )
      {
        if ( (_DWORD)v16 != 149 )
        {
          if ( (unsigned int)v16 <= 0x8F )
          {
            if ( (_DWORD)v16 == 143 )
            {
              v602 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
              if ( !*(_BYTE *)(v602 + 3) )
                goto LABEL_1431;
              v63 = sqlite3VdbeFinishMoveto(v602);
            }
            else
            {
              v579 = v16 - 138;
              if ( v579 )
              {
                v580 = v579 - 1;
                if ( v580 )
                {
                  v581 = v580 - 1;
                  if ( !v581 )
                  {
                    v586 = *((int *)v7 + 1);
                    LODWORD(v743) = 0;
                    *(_QWORD *)&v752 = 0;
                    v587 = v5[15];
                    v750 = 0;
                    v751 = 0;
                    v588 = *(_QWORD **)(v587 + 8 * v586);
                    v589 = v588[6];
                    *(_QWORD *)&v750 = v588[7];
                    WORD6(v751) = *((_WORD *)v7 + 6);
                    v590 = *((int *)v7 + 2);
                    BYTE14(v751) = 0;
                    *((_QWORD *)&v750 + 1) = v8 + 56 * v590;
                    Table = sqlite3BtreeIndexMoveto(v589, &v750, &v743);
                    v15 = Table;
                    if ( Table )
                      goto LABEL_279;
                    if ( (_DWORD)v743 )
                    {
                      v13 = 0;
                      if ( *((_WORD *)v7 + 1) && !(unsigned int)sqlite3WritableSchema(v4) )
                      {
                        v724 = sqlite3ReportError(779, 98280, "index corruption");
                        goto LABEL_1472;
                      }
                    }
                    else
                    {
                      LOBYTE(v591) = 4;
                      v592 = sqlite3BtreeDelete(v589, v591);
                      v13 = 0;
                      Table = v592;
                      v15 = v592;
                      if ( v592 )
                        goto LABEL_279;
                    }
                    v588[4] = 0;
                    goto LABEL_53;
                  }
                  if ( (unsigned int)(v581 - 1) > 1 )
                    goto LABEL_1431;
                  v582 = *((int *)v7 + 1);
                  v583 = v5[15];
                  v743 = 0;
                  v584 = *(_QWORD *)(v583 + 8 * v582);
                  Table = sqlite3VdbeCursorRestore(v584);
                  v15 = Table;
                  if ( Table )
                    goto LABEL_279;
                  if ( *(_BYTE *)(v584 + 2) )
                  {
                    sqlite3VdbeMemSetNull(v8 + 56LL * *((int *)v7 + 2));
                    goto LABEL_53;
                  }
                  v743 = 0;
                  Table = sqlite3VdbeIdxRowid(v4, *(_QWORD *)(v584 + 48), &v743);
                  v15 = Table;
                  if ( Table )
                    goto LABEL_279;
                  if ( *v7 == 0x8D )
                  {
                    v11 = Table + 1;
                    v585 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 3));
                    *(_BYTE *)(v585 + 2) = 0;
                    *(_QWORD *)(v585 + 80) = v743;
                    *(_BYTE *)(v585 + 3) = Table + 1;
                    *(_DWORD *)(v585 + 32) = 0;
                    *(_QWORD *)(v585 + 16) = *((_QWORD *)v7 + 2);
                    *(_QWORD *)(v585 + 40) = v584;
                    goto LABEL_99;
                  }
                  v268 = (__int64 *)out2Prerelease(v5, v7);
                  v269 = v743;
                  goto LABEL_541;
                }
                v593 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
                v594 = v8 + 56LL * *((int *)v7 + 2);
                if ( (*(_WORD *)(v594 + 20) & 0x400) != 0 )
                {
                  v15 = sqlite3VdbeMemExpandBlob(v8 + 56LL * *((int *)v7 + 2));
                  if ( v15 )
                    goto LABEL_279;
                }
                v63 = sqlite3VdbeSorterWrite(v593, v594);
              }
              else
              {
                v595 = v5[15];
                v596 = *((int *)v7 + 1);
                v750 = 0;
                v751 = 0;
                v752 = 0;
                v597 = *(_QWORD *)(v595 + 8 * v596);
                v598 = v8 + 56LL * *((int *)v7 + 2);
                if ( ((unsigned __int8)v11 & v7[2]) != 0 )
                  v5[7] += v11;
                if ( (*(_WORD *)(v598 + 20) & 0x400) != 0 )
                {
                  v15 = sqlite3VdbeMemExpandBlob(v598);
                  if ( v15 )
                    goto LABEL_279;
                }
                v599 = *((_WORD *)v7 + 1);
                *((_QWORD *)&v750 + 1) = *(int *)(v598 + 16);
                *(_QWORD *)&v750 = *(_QWORD *)(v598 + 8);
                v600 = v8 + 56LL * *((int *)v7 + 3);
                LOWORD(v752) = *((_WORD *)v7 + 8);
                *((_QWORD *)&v751 + 1) = v600;
                if ( (v599 & 0x10) != 0 )
                  v601 = *(unsigned int *)(v597 + 36);
                else
                  v601 = 0;
                v63 = sqlite3BtreeInsert(*(_QWORD *)(v597 + 48), &v750, (unsigned __int8)v599 & 0x8A, v601);
                *(_DWORD *)(v597 + 32) = 0;
              }
              v13 = 0;
            }
            goto LABEL_155;
          }
          v603 = v16 - 144;
          if ( !v603 )
          {
            LODWORD(v744) = 0;
            v618 = out2Prerelease(v5, v7);
            *(_WORD *)(v618 + 20) = 1;
            if ( *(_DWORD *)(v4 + 220) > *(_DWORD *)(v4 + 232) + 1 )
            {
              v15 = 6;
              *((_BYTE *)v5 + 196) = 2;
              goto LABEL_279;
            }
            v619 = *((_DWORD *)v7 + 3);
            v620 = *(_QWORD *)(v4 + 32);
            v621 = *((unsigned int *)v7 + 1);
            LODWORD(v744) = 0;
            v15 = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v619 + v620 + 8), v621, &v744);
            Table = v15;
            *(_WORD *)(v618 + 20) = 4;
            *(_QWORD *)v618 = (int)v744;
            if ( v15 )
              goto LABEL_279;
            if ( (_DWORD)v744 )
            {
              sqlite3RootPageMoved(v4, v619, (unsigned int)v744, *((unsigned int *)v7 + 1));
              v748 = v619 + 1;
              goto LABEL_80;
            }
            v14 = v735;
            v13 = 0;
            v11 = 1;
            goto LABEL_1343;
          }
          v604 = v603 - 1;
          if ( !v604 )
          {
            v614 = *(_QWORD *)(v4 + 32);
            v615 = *((unsigned int *)v7 + 1);
            v616 = 32LL * *((int *)v7 + 2);
            v746 = 0;
            v15 = sqlite3BtreeClearTable(*(_QWORD *)(v616 + v614 + 8), v615, &v746);
            Table = v15;
            if ( *((_DWORD *)v7 + 3) )
            {
              v617 = v746;
              v5[7] += v746;
              if ( *((int *)v7 + 3) > 0 )
                *(_QWORD *)(56LL * *((int *)v7 + 3) + v8) += v617;
            }
            goto LABEL_335;
          }
          v605 = v604 - 1;
          if ( !v605 )
          {
            v613 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
            if ( *(_BYTE *)v613 == (_BYTE)v11 )
            {
              sqlite3VdbeSorterReset(v4, *(_QWORD *)(v613 + 48));
              goto LABEL_53;
            }
            v63 = sqlite3BtreeClearTableOfCursor(*(_QWORD *)(v613 + 48));
            goto LABEL_155;
          }
          v606 = v605 - 1;
          if ( v606 )
          {
            if ( v606 != 1 )
              goto LABEL_1431;
            *(_BYTE *)(v4 + 112) += v11;
            v63 = sqlite3_exec(v4, *((_QWORD *)v7 + 2), 0, 0, 0);
            --*(_BYTE *)(v4 + 112);
            goto LABEL_155;
          }
          LODWORD(v743) = 0;
          v607 = out2Prerelease(v5, v7);
          v608 = *(_QWORD *)(v4 + 32);
          v609 = (_QWORD *)v607;
          v610 = *((unsigned int *)v7 + 3);
          v611 = 32LL * *((int *)v7 + 1);
          LODWORD(v743) = 0;
          Table = sqlite3BtreeCreateTable(*(_QWORD *)(v611 + v608 + 8), &v743, v610);
          v15 = Table;
          if ( Table )
            goto LABEL_279;
          v612 = (unsigned int)v743;
LABEL_1239:
          *v609 = v612;
          goto LABEL_53;
        }
        v622 = *((int *)v7 + 1);
        v623 = *(_QWORD *)(v4 + 32);
        *(_QWORD *)&v752 = 0;
        v624 = 32 * v622;
        v750 = 0;
        v751 = 0;
        if ( *((_QWORD *)v7 + 2) )
        {
          LODWORD(v751) = v622;
          v13 = 0;
          DWORD2(v751) = 0;
          *(_QWORD *)&v750 = v4;
          *((_QWORD *)&v750 + 1) = v5 + 21;
          v626 = sqlite3BtreeLastPage(*(_QWORD *)(v624 + v623 + 8));
          v627 = *(_QWORD *)(v4 + 32);
          LODWORD(v752) = v626;
          v628 = sqlite3MPrintf(
                   v4,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(v624 + v627),
                   "sqlite_master",
                   *((_QWORD *)v7 + 2));
          if ( !v628 )
          {
            v15 = 7;
            goto LABEL_1497;
          }
          *(_BYTE *)(v4 + 197) = 1;
          DWORD1(v751) = 0;
          HIDWORD(v751) = 0;
          Table = sqlite3_exec(v4, v628, (unsigned int)sqlite3InitCallback, (unsigned int)&v750, 0);
          v15 = Table;
          if ( !Table )
          {
            v15 = DWORD1(v751);
            Table = DWORD1(v751);
            if ( !DWORD1(v751) && !HIDWORD(v751) )
            {
              v15 = sqlite3CorruptError(98737);
              Table = v15;
            }
          }
          sqlite3DbFreeNN(v4);
          v11 = 1;
          *(_BYTE *)(v4 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(v624 + v623 + 24));
          *(_DWORD *)(v4 + 44) &= ~0x10u;
          inited = sqlite3InitOne(v4, (unsigned int)v622, v5 + 21, *((unsigned __int16 *)v7 + 1));
          v11 = 1;
          Table = inited;
          *(_DWORD *)(v4 + 44) |= 1u;
          v15 = inited;
          *((_DWORD *)v5 + 50) &= 0xFFFFFFFC;
          v13 = 0;
        }
        if ( !v15 )
          goto LABEL_98;
LABEL_1497:
        sqlite3ResetAllSchemasOfConnection(v4);
        v10 = v739;
        if ( v15 == 7 )
          goto LABEL_1511;
        goto LABEL_280;
      }
      if ( (unsigned int)v16 > 0x9B )
      {
        v641 = v16 - 156;
        if ( !v641 )
        {
          v648 = *((int *)v7 + 1);
          v649 = *((int *)v7 + 2);
          v650 = v8 + 56 * v648;
          if ( (*(_BYTE *)(v650 + 20) & 0x10) == 0 && (unsigned int)sqlite3VdbeMemSetRowSet(v8 + 56 * v648) )
            goto LABEL_1510;
          sqlite3RowSetInsert(*(_QWORD *)(v650 + 8), *(_QWORD *)(56 * v649 + v8));
          goto LABEL_80;
        }
        v642 = v641 - 1;
        if ( v642 )
        {
          v643 = v642 - 1;
          if ( !v643 )
          {
            v647 = *((int *)v7 + 2);
            if ( (*(_DWORD *)(v4 + 48) & 0x80000) != 0 )
            {
              *(_QWORD *)(v4 + 768) += v647;
            }
            else if ( *((_DWORD *)v7 + 1) )
            {
              *(_QWORD *)(v4 + 760) += v647;
            }
            else
            {
              v5[10] += v647;
            }
            goto LABEL_1431;
          }
          if ( v643 != 1 )
            goto LABEL_1431;
          v644 = v5[33];
          if ( v644 )
          {
            while ( *(_QWORD *)(v644 + 8) )
              v644 = *(_QWORD *)(v644 + 8);
            v645 = (_QWORD *)(*(_QWORD *)(v644 + 24) + 56LL * *((int *)v7 + 1));
          }
          else
          {
            v645 = (_QWORD *)(v8 + 56LL * *((int *)v7 + 1));
          }
          sqlite3VdbeMemIntegerify(v645);
          v646 = (_QWORD *)(v8 + 56LL * *((int *)v7 + 2));
          sqlite3VdbeMemIntegerify(v646);
          v14 = v735;
          LOBYTE(a4) = v734;
          v11 = 1;
          if ( *v645 < *v646 )
          {
            v6 = v738;
            *v645 = *v646;
            v13 = 0;
            goto LABEL_1431;
          }
          v13 = 0;
          goto LABEL_1042;
        }
        v295 = out2Prerelease(v5, v7);
        v294 = *(_QWORD *)(v5[33] + 24)
             + 56LL * (*((_DWORD *)v7 + 1) + *(_DWORD *)(*(_QWORD *)(v5[33] + 16) + 24LL * *(int *)(v5[33] + 76) + 4));
        goto LABEL_580;
      }
      if ( (_DWORD)v16 == 155 )
      {
        v633 = *((int *)v7 + 3);
        v634 = *(_QWORD *)(v4 + 32);
        v635 = *((_QWORD *)v7 + 2) + 4;
        LODWORD(v743) = 0;
        v746 = 0;
        v636 = 56 * v633;
        v637 = v8 + 56LL * *((int *)v7 + 1);
        Table = sqlite3BtreeIntegrityCheck(
                  v4,
                  *(_QWORD *)(32LL * *((unsigned __int16 *)v7 + 1) + v634 + 8),
                  v635,
                  *((_DWORD *)v7 + 2),
                  (int)v11 + *(_DWORD *)(56 * v633 + v8),
                  (__int64)&v743,
                  (__int64)&v746);
        v15 = Table;
        sqlite3VdbeMemSetNull(v637);
        if ( (_DWORD)v743 )
        {
          if ( Table )
          {
            sqlite3_free(v746);
            goto LABEL_279;
          }
          LOBYTE(v638) = 1;
          *(_QWORD *)(v636 + v8) -= (int)v743 - 1;
          sqlite3VdbeMemSetStr(v637, v746, -1, v638, sqlite3_free);
        }
        sqlite3VdbeChangeEncoding(v637, v734);
        goto LABEL_1276;
      }
      v629 = v16 - 150;
      if ( v629 )
      {
        v630 = v629 - 1;
        if ( !v630 )
        {
          sqlite3UnlinkAndDeleteTable(v4, *((unsigned int *)v7 + 1), *((_QWORD *)v7 + 2));
          goto LABEL_53;
        }
        v631 = v630 - 1;
        if ( !v631 )
        {
          sqlite3UnlinkAndDeleteIndex(v4, *((unsigned int *)v7 + 1), *((_QWORD *)v7 + 2));
          goto LABEL_53;
        }
        v632 = v631 - 1;
        if ( !v632 )
        {
          v267 = out2Prerelease(v5, v7);
          *(_WORD *)(v267 + 20) = 8;
LABEL_539:
          *(_QWORD *)v267 = **((_QWORD **)v7 + 2);
          goto LABEL_53;
        }
        if ( v632 != 1 )
          goto LABEL_1431;
        sqlite3UnlinkAndDeleteTrigger(v4, *((unsigned int *)v7 + 1), *((_QWORD *)v7 + 2));
        goto LABEL_53;
      }
      v63 = sqlite3AnalysisLoad(v4, *((unsigned int *)v7 + 1));
    }
LABEL_155:
    Table = v63;
    v15 = v63;
    v64 = v63 == 0;
    goto LABEL_156;
  }
  if ( (_DWORD)v16 == 90 )
  {
    if ( ((unsigned __int8)v11 & v7[2]) != 0 )
      v310 = *((_QWORD *)v7 - 1) + 4LL;
    else
      v310 = 0;
    v311 = *((_DWORD *)v7 + 3);
    v312 = *((_QWORD *)v7 + 2);
    a4 = *((unsigned int *)v7 + 1);
    v313 = *((_DWORD *)v7 + 2);
    v746 = v312;
    LODWORD(v743) = v311;
    LODWORD(v749) = a4;
    LODWORD(v744) = v313;
    if ( v311 <= 0 )
    {
LABEL_620:
      v8 = v741;
      goto LABEL_61;
    }
    while ( 1 )
    {
      v314 = v310 ? *(_DWORD *)(v310 + 4LL * (unsigned int)v13) : (int)v13;
      v315 = v741 + 56LL * (unsigned int)(v314 + v313);
      v316 = (unsigned __int8)(v11 & *(_BYTE *)((unsigned int)v13 + *(_QWORD *)(v312 + 24)));
      v317 = v741 + 56LL * (unsigned int)(v314 + a4);
      v735 = sqlite3MemCompare(v317, v315, *(_QWORD *)(v312 + 8LL * (unsigned int)v13 + 32));
      v14 = v735;
      v11 = 1;
      if ( v735 )
        break;
      v312 = v746;
      LODWORD(v13) = (_DWORD)v13 + 1;
      a4 = (unsigned int)v749;
      v313 = (int)v744;
      if ( (int)v13 >= (int)v743 )
      {
        v15 = Table;
        v5 = a1;
        goto LABEL_620;
      }
    }
    if ( (*(_BYTE *)((unsigned int)v13 + *(_QWORD *)(v746 + 24)) & 2) != 0
      && ((*(_BYTE *)(v317 + 20) & 1) != 0 || (*(_BYTE *)(v315 + 20) & 1) != 0) )
    {
      v14 = -v735;
      v735 = -v735;
    }
    v15 = Table;
    v13 = 0;
    v5 = a1;
    v8 = v741;
    LOBYTE(a4) = v734;
    if ( v316 )
    {
      v14 = (unsigned int)-(int)v14;
      v735 = v14;
    }
    goto LABEL_1042;
  }
  if ( (unsigned int)v16 <= 0x2C )
  {
    if ( (_DWORD)v16 == 44 )
      goto LABEL_383;
    if ( (unsigned int)v16 <= 0x16 )
    {
      if ( (_DWORD)v16 == 22 )
        goto LABEL_226;
      if ( (unsigned int)v16 <= 0xB )
      {
        if ( (_DWORD)v16 == 11 )
        {
          v94 = 56LL * *((int *)v7 + 1);
          *(_QWORD *)(v94 + v8) = *((_DWORD *)v7 + 3) - (int)v11;
          *(_WORD *)(v94 + v8 + 20) = 4;
          if ( !*((_DWORD *)v7 + 2) )
            goto LABEL_1431;
          goto LABEL_184;
        }
        if ( (unsigned int)v16 <= 5 )
        {
          if ( (_DWORD)v16 != 5 )
          {
            if ( (_DWORD)v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  v19 = v18 - 1;
                  if ( v19 )
                  {
                    if ( v19 != 1 )
                      goto LABEL_1431;
                    v20 = out2Prerelease(v5, v7);
                    v21 = *((_DWORD *)v7 + 3);
                    v22 = *(_QWORD *)(32LL * *((int *)v7 + 1) + *(_QWORD *)(v4 + 32) + 8);
                    v23 = sqlite3BtreePager(v22);
                    JournalMode = sqlite3PagerGetJournalMode(v23);
                    v25 = JournalMode;
                    if ( v21 == -1 )
                      v21 = JournalMode;
                    if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(v23) )
                      v21 = v25;
                    v26 = sqlite3PagerFilename(v23, 1);
                    if ( v21 == 5
                      && (!(unsigned int)sqlite3Strlen30(v26) || !(unsigned int)sqlite3PagerWalSupported(v23)) )
                    {
                      v21 = v25;
LABEL_32:
                      v15 = Table;
                      goto LABEL_33;
                    }
                    if ( v21 == v25 || v25 != 5 && v21 != 5 )
                      goto LABEL_32;
                    if ( !*(_BYTE *)(v4 + 101) || *(int *)(v4 + 220) > 1 )
                    {
                      v5 = a1;
                      v719 = "into";
                      v15 = 1;
                      if ( v21 != 5 )
                        v719 = "out of";
                      sqlite3VdbeError(a1, "cannot change %s wal mode from within a transaction", v719);
                      goto LABEL_279;
                    }
                    if ( v25 == 5 )
                    {
                      Table = sqlite3PagerCloseWal(v23, v4);
                      if ( !Table )
                      {
                        sqlite3PagerSetJournalMode(v23, v21);
LABEL_46:
                        v15 = sqlite3BtreeSetVersion(v22, (unsigned int)(v21 == 5) + 1);
                        Table = v15;
LABEL_33:
                        if ( !v15 )
                        {
LABEL_49:
                          v27 = sqlite3PagerSetJournalMode(v23, v21);
                          *(_WORD *)(v20 + 20) = 8706;
                          v28 = sqlite3JournalModename(v27);
                          *(_QWORD *)(v20 + 8) = v28;
                          *(_DWORD *)(v20 + 16) = sqlite3Strlen30(v28);
                          *(_BYTE *)(v20 + 22) = 1;
                          sqlite3VdbeChangeEncoding(v20, v734);
                          v5 = a1;
                          goto LABEL_50;
                        }
LABEL_48:
                        v21 = v25;
                        goto LABEL_49;
                      }
                    }
                    else
                    {
                      if ( v25 == 4 )
                        sqlite3PagerSetJournalMode(v23, 2);
                      if ( !Table )
                        goto LABEL_46;
                    }
                    v15 = Table;
                    goto LABEL_48;
                  }
                  v29 = *((_DWORD *)v7 + 2);
                  v30 = *((_DWORD *)v7 + 1);
                  v767 = 0;
                  v768 = -1;
                  v31 = sqlite3Checkpoint(v4, v30, v29, (unsigned int)&v768, (__int64)&v768 + 4);
                  Table = v31;
                  v15 = v31;
                  if ( v31 )
                  {
                    if ( v31 != 5 )
                      goto LABEL_279;
                    v15 = 0;
                    Table = 0;
                    v767 = 1;
                  }
                  v32 = v8 + 56LL * *((int *)v7 + 3);
                  do
                  {
                    sqlite3VdbeMemSetInt64(v32, *(&v767 + (_QWORD)v13));
                    v11 = 1;
                    v32 += 56;
                    v13 = (_QWORD *)((char *)v13 + 1);
                  }
                  while ( v13 != (_QWORD *)3 );
                  goto LABEL_60;
                }
                v33 = *((unsigned int *)v7 + 2);
                LODWORD(v743) = 0;
                if ( (_DWORD)v33 && (*(_QWORD *)(v4 + 48) & 0x200100000LL) != 0 )
                {
                  v15 = (*(_QWORD *)(v4 + 48) & 0x100000LL) != 0 ? 8 : 11;
                  goto LABEL_279;
                }
                v34 = *(_QWORD *)(v4 + 32);
                v35 = 32LL * *((int *)v7 + 1);
                v36 = *(_QWORD *)(v35 + v34 + 8);
                if ( v36 )
                {
                  Table = sqlite3BtreeBeginTrans(*(_QWORD *)(v35 + v34 + 8), v33, &v743);
                  v15 = Table;
                  if ( Table )
                  {
                    v10 = v739;
                    v143 = v740;
                    if ( (_BYTE)Table == 5 )
                    {
                      *((_DWORD *)v5 + 13) = Table;
                      *((_DWORD *)v5 + 12) = -1431655765 * ((__int64)&v7[-v738] >> 3);
                      goto LABEL_1530;
                    }
                    goto LABEL_281;
                  }
                  if ( (v5[25] & 0x20) == 0 || !*((_DWORD *)v7 + 2) || *(_BYTE *)(v4 + 101) && *(int *)(v4 + 220) <= 1 )
                  {
LABEL_76:
                    if ( *((_WORD *)v7 + 1)
                      && ((_DWORD)v743 != *((_DWORD *)v7 + 3)
                       || *(_DWORD *)(*(_QWORD *)(v35 + v34 + 24) + 4LL) != *((_DWORD *)v7 + 4)) )
                    {
                      if ( v5[21] )
                        sqlite3DbFreeNN(v4);
                      v5[21] = sqlite3DbStrDup(v4, "database schema has changed");
                      if ( **(_DWORD **)(32LL * *((int *)v7 + 1) + *(_QWORD *)(v4 + 32) + 24) != (_DWORD)v743 )
                        sqlite3ResetOneSchema(v4);
                      v15 = 17;
                      *((_DWORD *)v5 + 50) = v5[25] & 0xFFFFFFEC | 1;
                      goto LABEL_279;
                    }
                    goto LABEL_79;
                  }
                  v37 = *((_DWORD *)v5 + 16);
                  if ( !v37 )
                  {
                    v37 = ++*(_DWORD *)(v4 + 756) + *(_DWORD *)(v4 + 752);
                    *((_DWORD *)v5 + 16) = v37;
                  }
                  Table = sqlite3VtabSavepoint(v4, 0, (unsigned int)(v37 - 1));
                  v15 = Table;
                  if ( !Table )
                  {
                    v15 = sqlite3BtreeBeginStmt(v36, *((unsigned int *)v5 + 16));
                    Table = v15;
                  }
                  v5[11] = *(_QWORD *)(v4 + 760);
                  v5[12] = *(_QWORD *)(v4 + 768);
                }
                if ( v15 )
                  goto LABEL_279;
                goto LABEL_76;
              }
              v720 = *((_DWORD *)v7 + 1);
              v721 = *((_DWORD *)v7 + 2);
              if ( v720 != *(unsigned __int8 *)(v4 + 101) )
              {
                if ( v721 )
                {
                  sqlite3RollbackAll(v4, 516);
                  v722 = 1;
                }
                else
                {
                  if ( v720 && *(int *)(v4 + 224) > 0 )
                  {
                    sqlite3VdbeError(v5, "cannot commit transaction - SQL statements in progress");
                    goto LABEL_1449;
                  }
                  v15 = sqlite3VdbeCheckFk(v5, (unsigned int)v11);
                  if ( v15 )
                    goto LABEL_1529;
                  v722 = v720;
                }
                *(_BYTE *)(v4 + 101) = v722;
                if ( (unsigned int)sqlite3VdbeHalt(v5) == 5 )
                {
                  v14 = 0xAAAAAAAAAAAAAAABuLL;
                  v15 = 5;
                  *((_DWORD *)v5 + 12) = -1431655765 * ((__int64)&v7[-v738] >> 3);
                  *(_BYTE *)(v4 + 101) = 1 - v720;
                  *((_DWORD *)v5 + 13) = 5;
                }
                else
                {
                  sqlite3CloseSavepoints(v4);
                  v15 = *((_DWORD *)v5 + 13) != 0 ? 1 : 101;
                }
                goto LABEL_1529;
              }
              if ( v720 )
              {
                v723 = "cannot rollback - no transaction is active";
                if ( !v721 )
                  v723 = "cannot commit - no transaction is active";
                sqlite3VdbeError(v5, v723);
              }
              else
              {
                sqlite3VdbeError(v5, "cannot start a transaction within a transaction");
              }
            }
            else
            {
              v38 = *((_DWORD *)v7 + 1);
              v39 = (_BYTE *)*((_QWORD *)v7 + 2);
              LODWORD(v749) = v38;
              if ( !v38 )
              {
                if ( *(int *)(v4 + 224) <= 0 )
                {
                  if ( v39 )
                  {
                    v41 = -1;
                    do
                      ++v41;
                    while ( v39[v41] );
                    v40 = v41 & 0x3FFFFFFF;
                  }
                  else
                  {
                    v40 = 0;
                  }
                  Table = sqlite3VtabSavepoint(v4, 0, (unsigned int)(*(_DWORD *)(v4 + 752) + *(_DWORD *)(v4 + 756)));
                  v15 = Table;
                  if ( !Table )
                  {
                    v42 = (_QWORD *)sqlite3DbMallocRawNN(v4, v40 + 33LL);
                    v43 = v42;
                    if ( v42 )
                    {
                      *v42 = v42 + 4;
                      memcpy_0(v42 + 4, v39, v40 + 1);
                      if ( *(_BYTE *)(v4 + 101) )
                      {
                        *(_BYTE *)(v4 + 101) = 0;
                        *(_BYTE *)(v4 + 109) = 1;
                      }
                      else
                      {
                        ++*(_DWORD *)(v4 + 752);
                      }
                      v43[3] = *(_QWORD *)(v4 + 736);
                      v44 = *(_QWORD *)(v4 + 760);
                      *(_QWORD *)(v4 + 736) = v43;
                      v43[1] = v44;
                      v43[2] = *(_QWORD *)(v4 + 768);
                    }
                    goto LABEL_95;
                  }
                  goto LABEL_279;
                }
                sqlite3VdbeError(v5, "cannot open savepoint - SQL statements in progress");
                goto LABEL_1449;
              }
              v45 = *(_QWORD **)(v4 + 736);
              while ( 1 )
              {
                LODWORD(v744) = (_DWORD)v13;
                if ( !v45 )
                  break;
                if ( !(unsigned int)sqlite3StrICmp(*v45, v39) )
                {
                  v11 = 1;
                  if ( *(int *)(v4 + 224) <= 0 || v38 != 1 )
                  {
                    v46 = v45 + 3;
                    v746 = (__int64)(v45 + 3);
                    if ( v45[3] || !*(_BYTE *)(v4 + 109) )
                    {
                      LODWORD(v743) = 0;
                    }
                    else
                    {
                      LODWORD(v743) = 1;
                      v47 = 1;
                      if ( v38 == 1 )
                      {
                        v737 = sqlite3VdbeCheckFk(a1, 1);
                        if ( !v737 )
                        {
                          *(_BYTE *)(v745 + 101) = 1;
                          v48 = sqlite3VdbeHalt(a1);
                          v49 = v745;
                          if ( v48 == 5 )
                          {
                            v10 = v739;
                            v14 = 0xAAAAAAAAAAAAAAABuLL;
                            v143 = v740;
                            v5 = a1;
                            v15 = 5;
                            *((_DWORD *)a1 + 12) = -1431655765 * ((__int64)&v7[-v738] >> 3);
                            *(_BYTE *)(v49 + 101) = 0;
                            *((_DWORD *)a1 + 13) = 5;
                            goto LABEL_1531;
                          }
                          v50 = *((_DWORD *)a1 + 13);
                          Table = v50;
                          if ( v50 )
                            *(_BYTE *)(v745 + 101) = 0;
                          else
                            *(_BYTE *)(v745 + 109) = 0;
                          v51 = (int *)(v49 + 752);
                          v11 = 1;
                          goto LABEL_137;
                        }
                        v15 = v737;
                        v5 = a1;
LABEL_1529:
                        v143 = v740;
                        v10 = v739;
LABEL_1530:
                        v49 = v745;
                        goto LABEL_1531;
                      }
                    }
                    v51 = (int *)(v4 + 752);
                    v52 = *v51;
                    if ( v38 == 2 )
                    {
                      v53 = v745;
                      v54 = 0;
                      v55 = *(_DWORD *)(v745 + 44) & 1;
                      if ( *(int *)(v745 + 40) > 0 )
                      {
                        do
                        {
                          Table = sqlite3BtreeTripAllCursors(
                                    *(_QWORD *)(32LL * v54 + *(_QWORD *)(v53 + 32) + 8),
                                    516,
                                    v55 ^ 1u);
                          if ( Table )
                            goto LABEL_138;
                          v53 = v745;
                          v11 = 1;
                          ++v54;
                        }
                        while ( v54 < *(_DWORD *)(v745 + 40) );
                        LODWORD(v13) = (_DWORD)v744;
                      }
                    }
                    else
                    {
                      v55 = 0;
                    }
                    v49 = v745;
                    LODWORD(v13) = v52 + ~(_DWORD)v13;
                    v56 = 0;
                    if ( *(int *)(v745 + 40) > 0 )
                    {
                      v57 = (unsigned int)v749;
                      while ( 1 )
                      {
                        v50 = sqlite3BtreeSavepoint(
                                *(_QWORD *)(32LL * v56 + *(_QWORD *)(v49 + 32) + 8),
                                v57,
                                (unsigned int)v13);
                        Table = v50;
                        if ( v50 )
                          goto LABEL_138;
                        v49 = v745;
                        v11 = 1;
                        if ( ++v56 >= *(_DWORD *)(v745 + 40) )
                          goto LABEL_131;
                      }
                    }
                    v50 = Table;
LABEL_131:
                    if ( v55 )
                    {
                      for ( n = *(_QWORD *)(v49 + 8); n; n = *(_QWORD *)(n + 16) )
                      {
                        *(_DWORD *)(n + 200) &= ~2u;
                        *(_DWORD *)(n + 200) |= 1u;
                      }
                      sqlite3ResetAllSchemasOfConnection(v49);
                      v49 = v745;
                      v11 = 1;
                      v50 = Table;
                      *(_DWORD *)(v745 + 44) |= 1u;
                    }
                    v46 = (_QWORD *)v746;
                    v47 = v743;
                    v38 = (unsigned int)v749;
LABEL_137:
                    if ( v50 )
                    {
LABEL_138:
                      v15 = Table;
                      goto LABEL_139;
                    }
                    while ( 1 )
                    {
                      v59 = *(_QWORD **)(v49 + 736);
                      if ( v59 == v45 )
                        break;
                      *(_QWORD *)(v49 + 736) = v59[3];
                      sqlite3DbFreeNN(v49);
                      v49 = v745;
                      v11 = 1;
                      --*v51;
                    }
                    if ( v38 != 1 )
                    {
                      v60 = v745;
                      *(_QWORD *)(v745 + 760) = v45[1];
                      *(_QWORD *)(v60 + 768) = v45[2];
                      if ( v47 && v38 != 2 )
                      {
                        v15 = Table;
                        v5 = a1;
                        goto LABEL_96;
                      }
LABEL_147:
                      v61 = sqlite3VtabSavepoint(v60, v38, (unsigned int)v13);
                      v13 = 0;
                      Table = v61;
                      v15 = v61;
                      if ( !v61 )
                      {
                        v5 = a1;
                        v11 = 1;
                        goto LABEL_97;
                      }
                      goto LABEL_278;
                    }
                    *(_QWORD *)(v49 + 736) = *v46;
                    sqlite3DbFreeNN(v49);
                    if ( !v47 )
                    {
                      --*v51;
                      v60 = v745;
                      goto LABEL_147;
                    }
                    v15 = Table;
                    v5 = a1;
LABEL_95:
                    v11 = 1;
LABEL_96:
                    v13 = 0;
LABEL_97:
                    if ( *((_BYTE *)v5 + 199) == 3 )
                    {
                      v15 = 101;
                      goto LABEL_1529;
                    }
LABEL_98:
                    v8 = v741;
LABEL_99:
                    v6 = v738;
LABEL_100:
                    v14 = v735;
LABEL_101:
                    LOBYTE(a4) = v734;
LABEL_1431:
                    v4 = v745;
                    v7 += 24;
                    v9 = v740;
                    goto LABEL_9;
                  }
                  v5 = a1;
                  sqlite3VdbeError(a1, "cannot release savepoint - SQL statements in progress");
LABEL_1449:
                  v15 = 5;
                  goto LABEL_279;
                }
                v45 = (_QWORD *)v45[3];
                LODWORD(v13) = (_DWORD)v13 + 1;
              }
              v5 = a1;
              sqlite3VdbeError(a1, "no such savepoint: %s", v39);
            }
            v15 = 1;
            goto LABEL_279;
          }
          if ( *((_DWORD *)v7 + 2) )
            v62 = v8 + 56LL * *((int *)v7 + 2);
          else
            v62 = 0;
          v63 = sqlite3RunVacuum(v5 + 21, v4, *((unsigned int *)v7 + 1), v62);
          goto LABEL_155;
        }
        v65 = v16 - 6;
        if ( v65 )
        {
          v66 = v65 - 1;
          if ( v66 )
          {
            v67 = v66 - 1;
            if ( v67 )
            {
              v68 = v67 - 1;
              if ( v68 )
              {
                if ( v68 != 1 )
                  goto LABEL_1431;
                v69 = 56LL * *((int *)v7 + 1);
                *(_WORD *)(v69 + v8 + 20) = 4;
                *(_QWORD *)(v69 + v8) = (int)(-1431655765 * ((__int64)&v7[-v6] >> 3));
              }
LABEL_526:
              v7 = (unsigned __int8 *)(v6 + 24LL * (*((_DWORD *)v7 + 2) - (int)v11));
LABEL_1277:
              v10 = v739;
              if ( !*(_DWORD *)(v4 + 408) )
              {
                v143 = v740;
                if ( v740 >= v739 )
                {
                  while ( 1 )
                  {
                    v639 = *(unsigned int (__fastcall **)(_QWORD))(v4 + 528);
                    if ( !v639 )
                      goto LABEL_1344;
                    v640 = *(unsigned int *)(v4 + 544);
                    if ( v639(*(_QWORD *)(v4 + 536)) )
                      break;
                    v10 += v640;
                    v739 = v10;
                    if ( v740 < v10 )
                      goto LABEL_79;
                  }
                  v10 = -1;
LABEL_1501:
                  v15 = 9;
                  goto LABEL_281;
                }
                goto LABEL_1341;
              }
LABEL_1504:
              v15 = 9;
              goto LABEL_280;
            }
            goto LABEL_1405;
          }
          v746 = 0;
          if ( *(_BYTE *)(v4 + 103) )
            goto LABEL_1510;
          v70 = *(__int64 **)(*((_QWORD *)v7 + 2) + 16LL);
          if ( v70 )
          {
            v71 = *v70;
            if ( *v70 )
            {
              if ( !*(_QWORD *)(v71 + 104) )
                goto LABEL_1431;
              v72 = *((unsigned int *)v7 + 2);
              v73 = *(_BYTE *)(v4 + 108);
              v74 = v5[14];
              v75 = v8 + 56LL * *((int *)v7 + 3);
              for ( ii = 0; ii < (int)v72; v75 += 56 )
              {
                v77 = (unsigned int)ii;
                ii += v11;
                *(_QWORD *)(v74 + 8 * v77) = v75;
              }
              *(_BYTE *)(v4 + 108) = v7[2];
              Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v71 + 104))(
                        v70,
                        v72,
                        v74,
                        &v746);
              *(_BYTE *)(v4 + 108) = v73;
              v15 = Table;
              sqlite3VtabImportErrmsg(v5, v70);
              v13 = 0;
              if ( !Table )
              {
                if ( *((_DWORD *)v7 + 1) )
                  *(_QWORD *)(v4 + 56) = v746;
                goto LABEL_173;
              }
              if ( (_BYTE)Table != 19 || !*(_BYTE *)(*((_QWORD *)v7 + 2) + 28LL) )
              {
LABEL_173:
                v11 = 1;
                ++v5[7];
                goto LABEL_174;
              }
              v78 = *((_WORD *)v7 + 1);
              if ( v78 != 4 )
              {
                if ( v78 == 5 )
                  LOBYTE(v78) = 2;
                *((_BYTE *)v5 + 196) = v78;
                goto LABEL_279;
              }
              v15 = 0;
              Table = 0;
LABEL_982:
              v6 = v738;
              v11 = 1;
              v14 = v735;
              LOBYTE(a4) = v734;
              goto LABEL_1431;
            }
          }
LABEL_1468:
          v15 = 6;
          goto LABEL_279;
        }
        v79 = 56LL * *((int *)v7 + 3);
        v80 = (int *)(v79 + v8 + 56);
        v81 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        v82 = *v80;
        v83 = *(__int64 ***)(v81 + 48);
        v84 = *(unsigned int *)(v79 + v741);
        v85 = *v83;
        v86 = a1[14];
        v87 = 0;
        for ( jj = **v83; (int)v87 < v82; *(_QWORD *)(v86 + 8 * v89) = &v80[14 * v87] )
          v89 = v87++;
        HIDWORD(v733) = HIDWORD(v86);
        v90 = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(jj + 64))(v83, v84, *((_QWORD *)v7 + 2));
        v91 = v85;
        Table = v90;
        v5 = a1;
        v92 = v90;
        sqlite3VtabImportErrmsg(a1, v91);
        if ( v92 )
        {
          v15 = Table;
          goto LABEL_279;
        }
        v93 = (*(__int64 (__fastcall **)(__int64 **))(jj + 80))(v83);
        v13 = 0;
        *(_BYTE *)(v81 + 2) = 0;
        v15 = Table;
        v11 = 1;
        if ( !v93 )
          goto LABEL_98;
        goto LABEL_184;
      }
      if ( (unsigned int)v16 <= 0x11 )
      {
        if ( (_DWORD)v16 != 17 )
        {
          v95 = v16 - 12;
          if ( v95 )
          {
            v96 = v95 - 1;
            if ( v96 )
            {
              v97 = v96 - 1;
              if ( v97 )
              {
                v98 = v97 - 1;
                if ( v98 )
                {
                  if ( v98 != 1 )
                    goto LABEL_1431;
                  v99 = sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 1), *((unsigned int *)v7 + 3));
LABEL_196:
                  v11 = 1;
                  goto LABEL_197;
                }
                v101 = v5[33];
                if ( v101 )
                {
                  a4 = *(_QWORD *)(v101 + 40);
                  v102 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v7[-v5[17]] >> 3)) >> 3;
                  v103 = (-85 * (unsigned __int8)((__int64)&v7[-v5[17]] >> 3)) & 7;
                  v104 = *(unsigned __int8 *)(v102 + a4);
                  if ( !_bittest(&v104, v103) )
                  {
                    v105 = v104 | (1 << v103);
                    v14 = v735;
                    *(_BYTE *)(v102 + a4) = v105;
LABEL_204:
                    v6 = v738;
                    *((_DWORD *)v7 + 1) = *(_DWORD *)(v5[17] + 4);
                    goto LABEL_101;
                  }
                }
                else if ( *(_DWORD *)(v5[17] + 4) != *((_DWORD *)v7 + 1) )
                {
                  goto LABEL_204;
                }
                goto LABEL_184;
              }
              if ( (v14 & 0x80000000) == 0LL )
              {
                if ( (_DWORD)v14 )
                  v106 = *((_DWORD *)v7 + 3);
                else
                  v106 = *((_DWORD *)v7 + 2);
              }
              else
              {
                v106 = *((_DWORD *)v7 + 1);
              }
              v107 = v106 - (int)v11;
LABEL_208:
              v7 = (unsigned __int8 *)(v6 + 24 * v107);
              goto LABEL_1431;
            }
            v108 = v8 + 56LL * *((int *)v7 + 1);
            v109 = *(_WORD *)(v108 + 20);
            if ( (v109 & 4) == 0 )
            {
              LOBYTE(v6) = a4;
              LOBYTE(v14) = 67;
              applyAffinity(v8 + 56LL * *((int *)v7 + 1), v14, v6);
              v109 = *(_WORD *)(v108 + 20);
              if ( (v109 & 4) == 0 )
              {
                if ( !*((_DWORD *)v7 + 2) )
                {
                  v15 = 20;
                  goto LABEL_279;
                }
                goto LABEL_215;
              }
              v6 = v738;
              v11 = 1;
              v14 = v735;
            }
            a4 = 62020;
            *(_WORD *)(v108 + 20) = v109 & 0xF240 | 4;
            goto LABEL_1006;
          }
          v110 = 56LL * *((int *)v7 + 1);
          *(_WORD *)(v110 + v8 + 20) = 4;
          v111 = *(int *)(v110 + v8);
          *(_QWORD *)(v110 + v8) = (int)(-1431655765 * ((__int64)&v7[-v6] >> 3));
          v112 = 3 * v111;
          goto LABEL_219;
        }
        v113 = sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 1), *((_DWORD *)v7 + 3) == 0);
        v11 = 1;
        if ( !v113 )
          goto LABEL_184;
        goto LABEL_1349;
      }
      if ( (_DWORD)v16 != 18 )
      {
        if ( (_DWORD)v16 != 19 )
        {
          if ( (_DWORD)v16 == 20 )
          {
            v125 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
            if ( !v125 || !*(_BYTE *)(v125 + 2) )
              goto LABEL_220;
            v126 = v8 + 56LL * *((int *)v7 + 3);
            if ( (*(_WORD *)(v126 + 20) & 0x9000) == 0 )
            {
              *(_WORD *)(v126 + 20) = v11;
              goto LABEL_185;
            }
            vdbeMemClearExternAndSetNull(v8 + 56LL * *((int *)v7 + 3));
            goto LABEL_215;
          }
LABEL_226:
          v114 = *((int *)v7 + 1);
          *(_QWORD *)&v752 = 0;
          v115 = v5[15];
          LODWORD(v744) = 0;
          v750 = 0;
          v751 = 0;
          v116 = *(_QWORD *)(v115 + 8 * v114);
          *(_WORD *)(v116 + 2) = 0;
          *(_DWORD *)(v116 + 32) = 0;
          if ( !*(_BYTE *)(v116 + 4) )
          {
            v147 = (_QWORD *)(v116 + 48);
            v149 = *(_BYTE *)(*(_QWORD *)(v116 + 48) + 3LL) & 2;
            *(_QWORD *)&v750 = *(_QWORD *)(v116 + 56);
            v117 = v149 != 0;
            WORD6(v751) = *((_WORD *)v7 + 8);
            BYTE2(v752) = 0;
            v150 = *((int *)v7 + 3);
            BYTE14(v751) = v11 + (((unsigned __int8)v11 & (unsigned __int8)(v16 - 1)) != 0 ? 0xFE : 0);
            *((_QWORD *)&v750 + 1) = v741 + 56 * v150;
            Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v116 + 48), &v750, &v744);
            v15 = Table;
            if ( Table )
              goto LABEL_279;
            if ( v149 )
            {
              if ( !BYTE2(v752) )
              {
                v13 = 0;
                goto LABEL_299;
              }
            }
            else
            {
              v117 = 0;
            }
LABEL_303:
            if ( (int)v16 < 23 )
            {
              if ( (int)v744 <= 0 && ((_DWORD)v744 || (_DWORD)v16 != 21) )
              {
                v152 = (_BYTE *)*v147;
                v13 = 0;
                v124 = *v152 != 0;
                goto LABEL_300;
              }
              LODWORD(v744) = 0;
              v151 = sqlite3BtreePrevious(*v147, 0);
            }
            else
            {
              if ( (int)v744 >= 0 && ((_DWORD)v744 || (_DWORD)v16 != 24) )
              {
                v13 = 0;
                goto LABEL_317;
              }
              LODWORD(v744) = 0;
              v151 = sqlite3BtreeNext(*v147, 0);
            }
            v13 = 0;
            Table = v151;
            v15 = v151;
            if ( v151 )
            {
              if ( v151 != 101 )
                goto LABEL_279;
              v15 = 0;
              Table = 0;
              v124 = 1;
LABEL_300:
              if ( !v124 )
              {
LABEL_317:
                v5 = a1;
                v8 = v741;
                v14 = v735;
                LOBYTE(a4) = v734;
                v11 = 1;
                if ( v117 )
                  v7 += 24;
                goto LABEL_1042;
              }
LABEL_215:
              v11 = 1;
              goto LABEL_184;
            }
LABEL_299:
            v124 = (int)v744;
            goto LABEL_300;
          }
          v117 = 0;
          v118 = v8 + 56LL * *((int *)v7 + 3);
          v119 = *(_WORD *)(v118 + 20);
          if ( (v119 & 0x2E) == 2 )
            applyNumericAffinity(v118, 0);
          v120 = sqlite3VdbeIntValue(v118, v14);
          v121 = *(_WORD *)(v118 + 20);
          v122 = v120;
          *(_WORD *)(v118 + 20) = v119;
          if ( (v121 & 0x24) != 0 )
          {
LABEL_291:
            v147 = (_QWORD *)(v116 + 48);
            v148 = sqlite3BtreeTableMoveto(*(_QWORD *)(v116 + 48), v122, 0, &v744);
            *(_QWORD *)(v116 + 80) = v122;
            v5 = a1;
            v15 = v148;
            Table = v148;
            if ( v148 )
              goto LABEL_279;
            goto LABEL_303;
          }
          if ( (v121 & 8) == 0 )
          {
            if ( (v121 & 1) == 0 )
            {
              v13 = 0;
              if ( (unsigned int)v16 >= 0x17 )
              {
                v15 = Table;
                goto LABEL_215;
              }
              v123 = *(_BYTE **)(v116 + 48);
              if ( !*v123 && (v123[1] & 8) != 0 )
              {
                v124 = 0;
                Table = 0;
                v15 = 0;
                goto LABEL_300;
              }
              Table = btreeLast(v123, &v744);
              v15 = Table;
              if ( Table )
                goto LABEL_278;
              goto LABEL_299;
            }
            v15 = Table;
LABEL_1192:
            v13 = 0;
            goto LABEL_215;
          }
          v145 = *(double *)v118;
          if ( *(double *)v118 >= -9.223372036854776e18 )
          {
            if ( v145 >= 9.223372036854776e18 || (v146 = (unsigned int)(int)v145, v122 < v146) )
            {
LABEL_293:
              if ( (v16 & 1) != 0 )
                LODWORD(v16) = v16 + 1;
              goto LABEL_291;
            }
            if ( v122 <= v146 )
            {
              if ( v145 <= (double)(int)v122 )
              {
                if ( (double)(int)v122 <= v145 )
                  goto LABEL_291;
                goto LABEL_289;
              }
              goto LABEL_293;
            }
          }
LABEL_289:
          if ( (v16 & 1) == 0 )
            LODWORD(v16) = v16 - 1;
          goto LABEL_291;
        }
        v127 = v8 + 56LL * *((int *)v7 + 2);
        if ( ((unsigned __int8)v11 & *(_BYTE *)(v8 + 56LL * *((int *)v7 + 1) + 20)) == 0 )
        {
          v128 = (unsigned int)sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 1), 0) == 0;
          if ( (*(_WORD *)(v127 + 20) & 0x9000) == 0 )
          {
            *(_QWORD *)v127 = v128;
            *(_WORD *)(v127 + 20) = 4;
            goto LABEL_982;
          }
          v129 = v128;
          v130 = v127;
LABEL_244:
          vdbeReleaseAndSetInt64(v130, v129);
          goto LABEL_53;
        }
        if ( (*(_WORD *)(v127 + 20) & 0x9000) == 0 )
        {
          *(_WORD *)(v127 + 20) = v11;
LABEL_250:
          v6 = v738;
          goto LABEL_1431;
        }
        v131 = v8 + 56LL * *((int *)v7 + 2);
LABEL_248:
        vdbeMemClearExternAndSetNull(v131);
        goto LABEL_53;
      }
      if ( *((int *)v7 + 1) < 0 )
      {
        LOBYTE(v135) = *((_BYTE *)qword_1400B5170 + (*(_WORD *)(56LL * *((int *)v7 + 3) + v8 + 20) & 0x3F));
      }
      else
      {
        v132 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        if ( *((_DWORD *)v7 + 3) < (int)*(unsigned __int16 *)(v132 + 74) )
        {
          v133 = *(unsigned int *)(v132 + 4LL * *((int *)v7 + 3) + 120);
          if ( (unsigned int)v133 < 0xC )
            v134 = *((unsigned __int8 *)&qword_1400B2770[3] + v133);
          else
            v134 = ((unsigned __int8)v11 & (unsigned __int8)v133) != 0 ? 4 : 8;
          goto LABEL_259;
        }
        v135 = *((_DWORD *)v7 + 4);
      }
      v134 = (_WORD)v11 << (v135 - v11);
LABEL_259:
      v136 = ((unsigned __int16)v134 & *((_WORD *)v7 + 1)) == 0;
      goto LABEL_260;
    }
    if ( (unsigned int)v16 <= 0x21 )
    {
      if ( (_DWORD)v16 != 33 )
      {
        if ( (unsigned int)v16 <= 0x1C )
        {
          if ( (_DWORD)v16 == 28 )
            goto LABEL_270;
          if ( (_DWORD)v16 == 23 || (_DWORD)v16 == 24 )
            goto LABEL_226;
          if ( (_DWORD)v16 != 25 )
          {
            if ( (_DWORD)v16 == 26
              && *(unsigned __int16 *)(*(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1)) + 12LL) >= *((int *)v7 + 4) )
            {
              goto LABEL_1431;
            }
LABEL_270:
            v137 = *((int *)v7 + 1);
            *(_QWORD *)&v752 = 0;
            v138 = v5[15];
            v750 = 0;
            v751 = 0;
            v139 = *(_QWORD *)(v138 + 8 * v137);
            v140 = v8 + 56LL * *((int *)v7 + 3);
            WORD6(v751) = *((_WORD *)v7 + 8);
            *((_QWORD *)&v750 + 1) = v140;
            if ( WORD6(v751) )
            {
              v141 = (int *)(v139 + 36);
              *(_QWORD *)&v750 = *(_QWORD *)(v139 + 56);
              BYTE14(v751) = 0;
              v15 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v139 + 48), &v750, v139 + 36);
              Table = v15;
            }
            else
            {
              if ( (*(_WORD *)(v140 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v140) )
                goto LABEL_1510;
              v165 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v139 + 56));
              v166 = v165;
              if ( !v165 )
                goto LABEL_1510;
              sqlite3VdbeRecordUnpack(
                *(_QWORD *)(v139 + 56),
                *(unsigned int *)(*((_QWORD *)&v750 + 1) + 16LL),
                *(_QWORD *)(*((_QWORD *)&v750 + 1) + 8LL),
                v165);
              *(_BYTE *)(v166 + 30) = 0;
              v141 = (int *)(v139 + 36);
              Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v139 + 48), v166, v139 + 36);
              v15 = Table;
              sqlite3DbFreeNN(v4);
              v13 = 0;
            }
            if ( v15 )
              goto LABEL_279;
            v167 = *v141;
            *(_BYTE *)(v139 + 3) = 0;
            *(_DWORD *)(v139 + 32) = 0;
            *(_BYTE *)(v139 + 2) = v167 != 0;
            if ( *v7 == 29 )
            {
              v11 = 1;
              if ( v167 )
                goto LABEL_98;
              goto LABEL_184;
            }
            if ( !v167 )
            {
              v11 = 1;
              if ( *v7 != 27 )
              {
                v8 = v741;
                v14 = v735;
                LOBYTE(a4) = v734;
                if ( *v7 == 26 )
                  *(_WORD *)(v139 + 12) = *((_WORD *)v7 + 8);
                goto LABEL_1042;
              }
              v168 = 0;
              if ( WORD6(v751) )
              {
                a4 = *((_QWORD *)&v750 + 1);
                while ( (*(_BYTE *)(56LL * v168 + *((_QWORD *)&v750 + 1) + 20) & 1) == 0 )
                {
                  if ( (int)++v168 >= WORD6(v751) )
                    goto LABEL_98;
                }
                goto LABEL_184;
              }
              v8 = v741;
              goto LABEL_1349;
            }
            goto LABEL_215;
          }
          v142 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
          if ( !v142 || *(_BYTE *)(v142 + 2) )
            goto LABEL_526;
LABEL_220:
          v14 = v735;
          goto LABEL_1431;
        }
        switch ( (_DWORD)v16 )
        {
          case 0x1D:
            goto LABEL_270;
          case 0x1E:
            v158 = 56LL * *((int *)v7 + 3);
            v754 = 0;
            if ( (*(_BYTE *)(v158 + v8 + 20) & 0x24) == 0 )
            {
              LOBYTE(v6) = a4;
              LOBYTE(v14) = 67;
              v159 = *(_OWORD *)(v158 + v8 + 16);
              v756 = *(_OWORD *)(v158 + v8);
              v160 = *(_OWORD *)(v158 + v8 + 32);
              v757 = v159;
              *(_QWORD *)&v159 = *(_QWORD *)(v158 + v8 + 48);
              v758 = v160;
              v759 = v159;
              applyAffinity(&v756, v14, v6);
              if ( (BYTE4(v757) & 4) == 0 )
                goto LABEL_215;
              v161 = v756;
              goto LABEL_332;
            }
            break;
          case 0x1F:
            break;
          default:
            goto LABEL_322;
        }
        v161 = *(_QWORD *)(56LL * *((int *)v7 + 3) + v8);
LABEL_332:
        v162 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        v163 = *(_QWORD *)(v162 + 48);
        v754 = 0;
        v164 = sqlite3BtreeTableMoveto(v163, v161, 0, &v754);
        *(_QWORD *)(v162 + 80) = v161;
        v15 = v164;
        v13 = 0;
        Table = v164;
        *(_WORD *)(v162 + 2) = 0;
        *(_DWORD *)(v162 + 32) = 0;
        *(_DWORD *)(v162 + 36) = v754;
        if ( v754 )
        {
          if ( *((_DWORD *)v7 + 2) )
            goto LABEL_215;
          v15 = sqlite3CorruptError(97203);
          Table = v15;
        }
        goto LABEL_335;
      }
      v169 = *((int *)v7 + 1);
      v170 = v5[15];
      LODWORD(v743) = 0;
      v171 = *(_QWORD *)(*(_QWORD *)(v170 + 8 * v169) + 48LL);
      Table = sqlite3BtreeFirst(v171, &v743);
      v15 = Table;
      if ( Table )
        goto LABEL_279;
      if ( (_DWORD)v743 )
        goto LABEL_215;
      v172 = sqlite3BtreeRowCountEst(v171);
      if ( v172 < 0 || (__int16)sqlite3LogEst(v172) >= *((_DWORD *)v7 + 3) )
      {
        v99 = v743;
        goto LABEL_196;
      }
      v11 = Table + 1;
      v99 = Table + 1;
LABEL_197:
      v100 = v99 == 0;
LABEL_198:
      if ( v100 )
        goto LABEL_99;
      goto LABEL_184;
    }
    if ( (unsigned int)v16 <= 0x27 )
    {
      if ( (_DWORD)v16 == 39 )
      {
        v177 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        v178 = sqlite3BtreeNext(*(_QWORD *)(v177 + 48), *((unsigned int *)v7 + 3));
LABEL_376:
        v15 = v178;
        Table = v178;
        *(_DWORD *)(v177 + 32) = 0;
        if ( v178 )
        {
          if ( v178 != 101 )
            goto LABEL_279;
          v11 = 1;
          Table = 0;
          *(_BYTE *)(v177 + 2) = 1;
          v15 = 0;
          goto LABEL_1277;
        }
        *(_BYTE *)(v177 + 2) = 0;
        v11 = 1;
        ++*((_DWORD *)v5 + *((unsigned __int16 *)v7 + 1) + 53);
LABEL_525:
        v6 = v738;
        goto LABEL_526;
      }
      v173 = v16 - 34;
      if ( v173 && (v174 = v173 - 1) != 0 )
      {
        v175 = v174 - 1;
        if ( v175 )
        {
          v176 = v175 - 1;
          if ( v176 )
          {
            if ( v176 != 1 )
              goto LABEL_1431;
            v177 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
            v178 = sqlite3BtreePrevious(*(_QWORD *)(v177 + 48), *((unsigned int *)v7 + 3));
          }
          else
          {
            v177 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
            v178 = sqlite3VdbeSorterNext(v4, v177);
          }
          goto LABEL_376;
        }
      }
      else
      {
        *((_DWORD *)v5 + 55) += v11;
      }
      v179 = *((int *)v7 + 1);
      v180 = v5[15];
      LODWORD(v744) = 0;
      v181 = *(_QWORD *)(v180 + 8 * v179);
      LODWORD(v744) = v11;
      if ( *(_BYTE *)v181 == (_BYTE)v11 )
      {
        v182 = sqlite3VdbeSorterRewind(v181, &v744);
      }
      else
      {
        v182 = sqlite3BtreeFirst(*(_QWORD *)(v181 + 48), &v744);
        *(_BYTE *)(v181 + 3) = 0;
        *(_DWORD *)(v181 + 32) = 0;
      }
      Table = v182;
      v15 = v182;
      if ( v182 )
        goto LABEL_279;
      *(_BYTE *)(v181 + 2) = (_BYTE)v744;
      if ( *((int *)v7 + 2) > 0 )
      {
        v100 = (_DWORD)v744 == 0;
        v11 = v182 + 1;
        goto LABEL_198;
      }
LABEL_1347:
      v14 = v735;
      v11 = 1;
      goto LABEL_1343;
    }
    if ( (_DWORD)v16 != 40 && (_DWORD)v16 != 41 && (_DWORD)v16 != 42 )
    {
LABEL_383:
      v183 = sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 1), 2);
      v184 = sqlite3VdbeBooleanValue(v8 + 56LL * *((int *)v7 + 2), 2);
      v11 = 1;
      v185 = v184 + 2 * v183 + v183;
      v186 = qword_1400B50B0;
      if ( *v7 != 44 )
        v186 = qword_1400B5BC8;
      v187 = *((unsigned __int8 *)v186 + v185);
      v188 = 56LL * *((int *)v7 + 3);
      v189 = *(_WORD *)(v188 + v8 + 20);
      if ( (_BYTE)v187 == 2 )
      {
        v190 = v189 & 0xF240 | 1;
      }
      else
      {
        *(_QWORD *)(v188 + v8) = v187;
        v190 = v189 & 0xF240 | 4;
      }
      *(_WORD *)(v188 + v8 + 20) = v190;
      goto LABEL_99;
    }
    goto LABEL_434;
  }
  if ( (unsigned int)v16 <= 0x43 )
  {
    if ( (_DWORD)v16 == 67 )
    {
      v262 = 56LL * *((int *)v7 + 1);
      if ( (*(_BYTE *)(v262 + v8 + 20) & 4) == 0 )
        goto LABEL_1431;
      v107 = *(_QWORD *)(v262 + v8);
      goto LABEL_208;
    }
    if ( (unsigned int)v16 > 0x38 )
    {
      if ( (unsigned int)v16 > 0x3E )
      {
        v246 = v16 - 63;
        if ( v246 )
        {
          v247 = v246 - 1;
          if ( !v247 )
          {
            v253 = 56LL * *((int *)v7 + 1);
            v254 = filterHash(v8, v7);
            v11 = 1;
            v255 = v254 % (8 * *(_DWORD *)(v253 + v8 + 16));
            v256 = *(char *)((v255 >> 3) + *(_QWORD *)(v253 + v8 + 8));
            v257 = _bittest(&v256, v255 & 7);
            v6 = v738;
            if ( v257 )
            {
              ++*((_DWORD *)v5 + 60);
              goto LABEL_100;
            }
            ++*((_DWORD *)v5 + 61);
            goto LABEL_185;
          }
          if ( (unsigned int)(v247 - 1) > 1 )
            goto LABEL_1431;
          v248 = *((_QWORD *)v7 + 2);
          v249 = v8 + 56LL * *((int *)v7 + 3);
          if ( *(_QWORD *)v248 != v249 )
          {
            v250 = *(unsigned __int8 *)(v248 + 42);
            *(_QWORD *)(v248 + 24) = v5;
            *(_QWORD *)v248 = v249;
            *(_BYTE *)(v248 + 40) = a4;
            while ( 1 )
            {
              v250 -= v11;
              if ( v250 < 0 )
                break;
              *(_QWORD *)(v248 + 8LL * (unsigned int)v250 + 48) = v8 + 56LL * (v250 + *((_DWORD *)v7 + 2));
            }
          }
          *(_WORD *)(v249 + 20) &= 0xF241u;
          *(_WORD *)(v249 + 20) |= v11;
          (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v248 + 8) + 24LL))(
            v248,
            *(unsigned __int8 *)(v248 + 42),
            v248 + 48);
          v251 = *(_DWORD *)(v248 + 36);
          if ( !v251 )
          {
LABEL_1345:
            v14 = v735;
            v11 = 1;
            goto LABEL_1342;
          }
          if ( v251 > 0 )
          {
            v252 = (const char *)sqlite3_value_text(v249);
            sqlite3VdbeError(v5, "%s", v252);
            v15 = *(_DWORD *)(v248 + 36);
            Table = v15;
          }
          sqlite3VdbeDeleteAuxData(v4, v5 + 37, *(unsigned int *)(v248 + 32), *((unsigned int *)v7 + 1));
          v13 = 0;
          *(_DWORD *)(v248 + 36) = 0;
LABEL_335:
          v64 = v15 == 0;
LABEL_156:
          if ( !v64 )
            goto LABEL_279;
          goto LABEL_53;
        }
        v258 = *(_QWORD *)(v5[15] + 8LL * *((int *)v7 + 1));
        if ( *(_BYTE *)(v258 + 2) )
          goto LABEL_1430;
        v259 = *(__int64 ***)(v258 + 48);
        v260 = *v259;
        v261 = **v259;
        Table = (*(__int64 (**)(void))(v261 + 72))();
        v15 = Table;
        sqlite3VtabImportErrmsg(v5, v260);
        if ( Table )
          goto LABEL_279;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(v261 + 80))(*(_QWORD *)(v258 + 48)) )
        {
LABEL_1276:
          v11 = 1;
          goto LABEL_1277;
        }
        goto LABEL_524;
      }
      if ( (_DWORD)v16 == 62 )
      {
        v245 = sqlite3BtreeIncrVacuum(*(_QWORD *)(32LL * *((int *)v7 + 1) + *(_QWORD *)(v4 + 32) + 8));
        Table = v245;
        v15 = v245;
        if ( v245 )
        {
          if ( v245 != 101 )
            goto LABEL_279;
          v15 = 0;
          Table = 0;
          goto LABEL_215;
        }
        goto LABEL_1347;
      }
      if ( (_DWORD)v16 == 57 )
      {
LABEL_445:
        v226 = v8 + 56LL * *((int *)v7 + 1);
        v227 = v8 + 56LL * *((int *)v7 + 3);
        v228 = *(_WORD *)(v226 + 20);
        v229 = *(_WORD *)(v227 + 20);
        if ( ((unsigned __int8)v228 & (unsigned __int8)v229 & 4) != 0 )
        {
          v230 = *(_QWORD *)v227 < *(_QWORD *)v226;
          if ( *(_QWORD *)v227 <= *(_QWORD *)v226 )
          {
            v239 = *v7;
            v15 = Table;
            if ( v230 )
            {
              v13 = 0;
              if ( *((_BYTE *)&qword_1400B2890[25] + v239 + 4) )
                goto LABEL_185;
              v14 = 0xFFFFFFFFLL;
            }
            else
            {
              v13 = 0;
              if ( *((_BYTE *)&qword_1400B2890[26] + v239 + 2) )
                goto LABEL_185;
              v14 = 0;
            }
            goto LABEL_450;
          }
          v13 = 0;
          v231 = *((_BYTE *)&qword_1400B2890[27] + v16) == 0;
LABEL_448:
          v15 = Table;
          if ( !v231 )
            goto LABEL_185;
          v14 = (unsigned int)v11;
LABEL_450:
          v5 = a1;
          v8 = v741;
          v735 = v14;
          goto LABEL_1431;
        }
        v240 = v228 | v229;
        if ( ((unsigned __int8)(v228 | v229) & (unsigned __int8)v11) != 0 )
        {
          if ( (v7[2] & 0x80u) == 0 )
          {
            v13 = 0;
            v231 = (v7[2] & 0x10) == 0;
            goto LABEL_448;
          }
          if ( ((unsigned __int8)(v228 & v229) & (unsigned __int8)v11) != 0 && (v229 & 0x100) == 0 )
          {
            v14 = 0;
LABEL_477:
            v735 = v14;
LABEL_478:
            v241 = *v7;
            if ( (_DWORD)v14 )
              v242 = *((_BYTE *)&qword_1400B2890[27] + v241);
            else
              v242 = *((_BYTE *)&qword_1400B2890[26] + v241 + 2);
LABEL_502:
            *(_WORD *)(v227 + 20) = v229;
            v13 = 0;
            *(_WORD *)(v226 + 20) = v228;
            v15 = Table;
            if ( !v242 )
            {
              v5 = a1;
              v8 = v741;
              goto LABEL_101;
            }
            goto LABEL_184;
          }
          if ( ((unsigned __int8)v229 & (unsigned __int8)v11) == 0 )
          {
            v14 = (unsigned int)v11;
            goto LABEL_477;
          }
          v14 = 0xFFFFFFFFLL;
          v735 = -1;
        }
        else
        {
          v243 = v7[2] & 0x47;
          if ( v243 < 0x43u )
          {
            if ( v243 == 66 && (v240 & 2) != 0 )
            {
              if ( (v228 & 2) == 0 && (v228 & 0x2C) != 0 )
              {
                LOBYTE(v6) = v11;
                LOBYTE(v14) = a4;
                sqlite3VdbeMemStringify(v226, v14, v6);
                LOBYTE(v11) = 1;
                v228 = *(_WORD *)(v226 + 20) ^ (*(_WORD *)(v226 + 20) ^ v228) & 0xDBF;
                if ( v226 == v227 )
                  v229 = v228 | 2;
              }
              if ( (v229 & 2) == 0 && (v229 & 0x2C) != 0 )
              {
                LOBYTE(v14) = v734;
                LOBYTE(v6) = v11;
                sqlite3VdbeMemStringify(v227, v14, v6);
                v229 = *(_WORD *)(v227 + 20) ^ (*(_WORD *)(v227 + 20) ^ v229) & 0xDBF;
              }
            }
          }
          else if ( (v240 & 2) != 0 )
          {
            if ( (v228 & 0x2E) == 2 )
            {
              applyNumericAffinity(v226, 0);
              v229 = *(_WORD *)(v227 + 20);
            }
            if ( (v229 & 0x2E) == 2 )
              applyNumericAffinity(v227, 0);
          }
          v244 = sqlite3MemCompare(v227, v226, *((_QWORD *)v7 + 2));
          v6 = v738;
          v14 = (unsigned int)v244;
          v735 = v244;
          v11 = 1;
          if ( v244 >= 0 )
            goto LABEL_478;
        }
        v242 = *((_BYTE *)&qword_1400B2890[25] + *v7 + 4);
        goto LABEL_502;
      }
      if ( (_DWORD)v16 != 58 )
      {
        if ( (_DWORD)v16 != 59 )
        {
          if ( (_DWORD)v16 == 60 )
          {
            v235 = 56LL * *((int *)v7 + 1);
            v236 = *(_QWORD *)(v235 + v8);
            if ( !v236 )
              goto LABEL_1431;
            if ( v236 > 0 )
              *(_QWORD *)(v235 + v8) = v236 - 1;
            goto LABEL_185;
          }
          v232 = 56LL * *((int *)v7 + 1);
          v233 = *(_QWORD *)(v232 + v8);
          if ( v233 == 0x8000000000000000uLL )
            goto LABEL_1431;
          v234 = v233 - 1;
          *(_QWORD *)(v232 + v8) = v234;
          if ( v234 )
            goto LABEL_1431;
          goto LABEL_184;
        }
        v237 = 56LL * *((int *)v7 + 1);
        v238 = *(_QWORD *)(v237 + v8);
        if ( v238 > 0 )
        {
          *(_QWORD *)(v237 + v8) = v238 - *((int *)v7 + 3);
          goto LABEL_185;
        }
        goto LABEL_220;
      }
      v192 = (_DWORD)v14 == 0;
    }
    else
    {
      if ( (_DWORD)v16 == 56 )
        goto LABEL_445;
      if ( (unsigned int)v16 <= 0x32 )
      {
        if ( (_DWORD)v16 == 50 )
        {
          v136 = ((unsigned __int8)v11 & *(_BYTE *)(56LL * *((int *)v7 + 1) + v8 + 20)) == 0;
LABEL_260:
          if ( v136 )
            goto LABEL_1431;
          goto LABEL_185;
        }
        if ( (_DWORD)v16 == 45 )
        {
LABEL_434:
          v216 = *((int *)v7 + 1);
          *(_QWORD *)&v752 = 0;
          v217 = v5[15];
          v750 = 0;
          v751 = 0;
          v218 = *(_QWORD *)(v217 + 8 * v216);
          v756 = 0;
          v757 = 0;
          *(_QWORD *)&v750 = *(_QWORD *)(v218 + 56);
          WORD6(v751) = *((_WORD *)v7 + 8);
          BYTE14(v751) = -((unsigned __int8)v16 < 0x2Au);
          v219 = 56LL * *((int *)v7 + 3);
          v758 = 0;
          v759 = 0;
          *((_QWORD *)&v750 + 1) = v8 + v219;
          v220 = *(_QWORD *)(v218 + 48);
          v221 = sqlite3BtreePayloadSize(v220);
          if ( v221 - 1 <= 0x7FFFFFFE )
          {
            sqlite3VdbeMemInit(&v756, v4, 0);
            v222 = sqlite3VdbeMemFromBtreeZeroOffset(v220, v221, &v756);
            v13 = 0;
            Table = v222;
            v15 = v222;
            if ( v222 )
              goto LABEL_279;
            v223 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v757, *((_QWORD *)&v756 + 1), &v750, 0);
            sqlite3VdbeMemReleaseMalloc(&v756);
            v224 = v223 + 1;
            v225 = -v223;
            v11 = 1;
            if ( (*v7 & 1) != 0 )
              v225 = v224;
            if ( v225 <= 0 )
              goto LABEL_99;
LABEL_184:
            v6 = v738;
LABEL_185:
            v7 = (unsigned __int8 *)(v6 + 24LL * (*((_DWORD *)v7 + 2) - (int)v11));
LABEL_737:
            v5 = a1;
            v8 = v741;
            goto LABEL_100;
          }
          v724 = sqlite3CorruptError(98485);
LABEL_1472:
          v15 = v724;
          goto LABEL_279;
        }
        if ( (_DWORD)v16 != 46 )
        {
          if ( (_DWORD)v16 != 47 )
          {
            if ( (_DWORD)v16 != 48 )
            {
              if ( *((_DWORD *)v7 + 1) )
                v191 = *(_QWORD *)(v4 + 760) == 0;
              else
                v191 = v5[10] == 0;
              if ( !v191 )
                goto LABEL_1431;
              v192 = *(_QWORD *)(v4 + 768) == 0;
              goto LABEL_403;
            }
            v193 = *((_QWORD *)v7 + 2);
            v746 = v193;
            if ( *((_WORD *)v7 + 1) )
            {
              for ( kk = v5[33]; kk; kk = *(_QWORD *)(kk + 8) )
              {
                if ( *(_QWORD *)(kk + 48) == *(_QWORD *)(v193 + 32) )
                  goto LABEL_250;
              }
            }
            if ( *((_DWORD *)v5 + 70) >= *(_DWORD *)(v4 + 176) )
            {
              v15 = v11;
              sqlite3VdbeError(v5, "too many levels of trigger recursion");
              goto LABEL_279;
            }
            v195 = (int *)(v193 + 16);
            v196 = (int *)(v193 + 8);
            v197 = 56LL * *((int *)v7 + 3) + v8;
            if ( (*(_BYTE *)(v197 + 20) & 0x10) != 0 )
            {
              v200 = *(_QWORD *)(v197 + 8);
              v202 = (__int64 *)v193;
LABEL_422:
              *((_DWORD *)v5 + 70) += v11;
              *(_QWORD *)(v200 + 8) = v5[33];
              v741 = v200 + 112;
              *(_QWORD *)(v200 + 56) = *(_QWORD *)(v745 + 56);
              *(_QWORD *)(v200 + 96) = v5[7];
              *(_QWORD *)(v200 + 104) = *(_QWORD *)(*v5 + 120);
              *(_QWORD *)(v200 + 64) = v5[37];
              v5[13] = v200 + 112;
              v5[37] = 0;
              v5[7] = 0;
              v5[33] = v200;
              v205 = *(int *)(v200 + 88);
              *((_DWORD *)v5 + 9) = v205;
              *((_DWORD *)v5 + 10) = *(unsigned __int16 *)(v200 + 92);
              v5[15] = v200 + 112 + 56 * v205;
              v206 = (void *)(v200 + 112 + 8 * (*v195 + 7 * v205));
              *(_QWORD *)(v200 + 40) = v206;
              memset_0(v206, 0, (*v196 + 7) / 8);
              v207 = *v202;
              v15 = Table;
              v5[17] = *v202;
              v208 = *v196;
              v4 = v745;
              v7 = (unsigned __int8 *)(v207 - 24);
              v738 = v207;
              *((_DWORD *)v5 + 36) = v208;
              goto LABEL_1276;
            }
            v198 = *v195 + *(_DWORD *)(v193 + 12) + 1;
            if ( *v195 )
              v198 = *v195 + *(_DWORD *)(v193 + 12);
            v199 = (*v196 + 7) / 8 + 8 * (*v195 + 7 * (v198 + 2));
            v200 = sqlite3DbMallocZero(v745, v199);
            if ( v200 )
            {
              sqlite3VdbeMemRelease(v197);
              *(_QWORD *)(v197 + 48) = sqlite3VdbeFrameMemDel;
              v201 = v200 + 112;
              *(_DWORD *)(v197 + 16) = v199;
              v5 = a1;
              *(_WORD *)(v197 + 20) = 4112;
              *(_QWORD *)(v197 + 8) = v200;
              v202 = (__int64 *)v746;
              *(_DWORD *)(v200 + 88) = v198;
              *(_QWORD *)v200 = a1;
              *(_DWORD *)(v200 + 92) = *v195;
              *(_DWORD *)(v200 + 76) = -1431655765 * ((__int64)&v7[-v738] >> 3);
              *(_QWORD *)(v200 + 24) = a1[13];
              *(_DWORD *)(v200 + 84) = *((_DWORD *)a1 + 9);
              *(_QWORD *)(v200 + 32) = a1[15];
              *(_DWORD *)(v200 + 72) = *((_DWORD *)a1 + 10);
              *(_QWORD *)(v200 + 16) = a1[17];
              *(_DWORD *)(v200 + 80) = *((_DWORD *)a1 + 36);
              *(_QWORD *)(v200 + 48) = v202[4];
              v203 = v200 + 56 * (v198 + 2LL);
              if ( v200 + 112 != v203 )
              {
                v204 = v745;
                do
                {
                  *(_WORD *)(v201 + 20) = 0;
                  *(_QWORD *)(v201 + 24) = v204;
                  v201 += 56;
                }
                while ( v201 != v203 );
                v5 = a1;
              }
              LODWORD(v11) = 1;
              goto LABEL_422;
            }
LABEL_1508:
            v5 = a1;
            goto LABEL_1509;
          }
          v209 = *((_DWORD *)v7 + 4);
          v210 = v8 + 56LL * *((int *)v7 + 1);
          v211 = *((int *)v7 + 3);
          if ( (*(_BYTE *)(v210 + 20) & 0x10) == 0 && (unsigned int)sqlite3VdbeMemSetRowSet(v210) )
            goto LABEL_1510;
          v212 = 56 * v211;
          v213 = v209 < 0;
          if ( v209 )
          {
            if ( (unsigned int)sqlite3RowSetTest(*(_QWORD *)(v210 + 8), (unsigned int)v209, *(_QWORD *)(v212 + v741)) )
              goto LABEL_1192;
            v213 = v209 < 0;
          }
          if ( !v213 )
            sqlite3RowSetInsert(*(_QWORD *)(v210 + 8), *(_QWORD *)(v212 + v741));
LABEL_79:
          v8 = v741;
          goto LABEL_80;
        }
        v214 = *((int *)v7 + 1);
        v746 = 0;
        v215 = v8 + 56 * v214;
        if ( (*(_BYTE *)(v215 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v215 + 8), &v746) )
        {
          sqlite3VdbeMemSetInt64(v8 + 56LL * *((int *)v7 + 3), v746);
          goto LABEL_1276;
        }
        sqlite3VdbeMemSetNull(v215);
LABEL_524:
        v11 = 1;
        goto LABEL_525;
      }
      if ( (_DWORD)v16 != 51 )
      {
        if ( (_DWORD)v16 != 52 && (_DWORD)v16 != 53 && (unsigned int)(v16 - 54) > 1 )
          goto LABEL_1431;
        goto LABEL_445;
      }
      v192 = ((unsigned __int8)v11 & *(_BYTE *)(56LL * *((int *)v7 + 1) + v8 + 20)) == 0;
    }
LABEL_403:
    if ( !v192 )
      goto LABEL_1431;
    goto LABEL_185;
  }
  if ( (unsigned int)v16 > 0x4E )
  {
    if ( (unsigned int)v16 <= 0x54 )
    {
      if ( (_DWORD)v16 == 84 )
      {
        *((_DWORD *)v5 + 11) = v11 | (*((_DWORD *)v5 + 11) + 2);
        v5[20] = v8 + 56LL * *((int *)v7 + 1);
        if ( !*(_BYTE *)(v4 + 103) )
        {
          if ( (*(_BYTE *)(v4 + 110) & 4) != 0 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v4 + 248))(4, *(_QWORD *)(v4 + 256), v5, 0);
            v6 = v738;
            LODWORD(v11) = 1;
          }
          v15 = 100;
          *((_DWORD *)v5 + 12) = v11 - 1431655765 * ((__int64)&v7[-v6] >> 3);
          goto LABEL_1529;
        }
        goto LABEL_1510;
      }
      v289 = v16 - 79;
      if ( !v289 )
      {
        v300 = *((_DWORD *)v7 + 3);
        v301 = v741 + 56LL * *((int *)v7 + 1);
        v302 = v741 + 56LL * *((int *)v7 + 2);
        while ( 1 )
        {
          sqlite3VdbeMemMove(v302, v301);
          if ( (*(_WORD *)(v302 + 20) & 0x4000) != 0 )
          {
            if ( (unsigned int)sqlite3VdbeMemMakeWriteable(v302) )
              goto LABEL_1510;
          }
          v301 += 56;
          v302 += 56;
          v11 = 1;
          if ( !--v300 )
            goto LABEL_563;
        }
      }
      v290 = v289 - 1;
      if ( !v290 )
      {
        v296 = *((_DWORD *)v7 + 3);
        v297 = v741 + 56LL * *((int *)v7 + 1);
        for ( mm = v741 + 56LL * *((int *)v7 + 2); ; mm += 56 )
        {
          sqlite3VdbeMemShallowCopy(mm, v297, 0x4000);
          if ( (*(_WORD *)(mm + 20) & 0x4000) != 0 )
          {
            if ( (unsigned int)sqlite3VdbeMemMakeWriteable(mm) )
              break;
          }
          v299 = *(_WORD *)(mm + 20);
          if ( (v299 & 0x800) != 0 && (v7[2] & 2) != 0 )
            *(_WORD *)(mm + 20) = v299 & 0xF7FF;
          if ( !v296 )
            goto LABEL_1344;
          --v296;
          v297 += 56;
        }
        goto LABEL_1510;
      }
      v291 = v290 - 1;
      if ( v291 )
      {
        v292 = v291 - 1;
        if ( v292 )
        {
          if ( v292 != 1 )
            goto LABEL_1431;
          v63 = sqlite3VdbeCheckFk(v5, 0);
          goto LABEL_155;
        }
        v293 = v8 + 56LL * *((int *)v7 + 2);
        if ( (*(_WORD *)(v293 + 20) & 0x9000) != 0 )
        {
          v129 = *(_QWORD *)(56LL * *((int *)v7 + 1) + v8);
          v130 = v8 + 56LL * *((int *)v7 + 2);
          goto LABEL_244;
        }
        *(_QWORD *)v293 = *(_QWORD *)(56LL * *((int *)v7 + 1) + v8);
        *(_WORD *)(v293 + 20) = 4;
LABEL_1042:
        v6 = v738;
        goto LABEL_1431;
      }
      v294 = v8 + 56LL * *((int *)v7 + 1);
      v295 = v8 + 56LL * *((int *)v7 + 2);
LABEL_580:
      sqlite3VdbeMemShallowCopy(v295, v294, 0x4000);
      goto LABEL_53;
    }
    v303 = v16 - 85;
    if ( v303 )
    {
      v304 = v303 - 1;
      if ( !v304 )
      {
        v307 = (_QWORD *)(v8 + 56LL * *((int *)v7 + 1));
        sqlite3VdbeMemIntegerify(v307);
        *v307 += *((int *)v7 + 2);
        goto LABEL_53;
      }
      v305 = v304 - 1;
      if ( v305 )
      {
        if ( v305 != 1 )
          goto LABEL_1431;
        v306 = v8 + 56LL * *((int *)v7 + 1);
        if ( (*(_WORD *)(v306 + 20) & 0x400) != 0 )
        {
          v15 = sqlite3VdbeMemExpandBlob(v8 + 56LL * *((int *)v7 + 1));
          if ( v15 )
            goto LABEL_279;
        }
        LOBYTE(v6) = v734;
        LOBYTE(v14) = v7[8];
        v63 = sqlite3VdbeMemCast(v306, v14, v6);
        goto LABEL_155;
      }
      if ( (*(_BYTE *)(v8 + 56LL * *((int *)v7 + 1) + 20) & 0x24) == 0 )
        goto LABEL_1431;
      sqlite3VdbeMemRealify();
LABEL_53:
      LOBYTE(a4) = v734;
      goto LABEL_54;
    }
    if ( !*((_DWORD *)v7 + 1) )
      goto LABEL_1431;
    v308 = *((int *)v7 + 1);
    goto LABEL_606;
  }
  if ( (_DWORD)v16 == 78 )
  {
    v287 = v5[16] + 56LL * *((int *)v7 + 1);
    if ( (unsigned int)sqlite3VdbeMemTooBig(v287 - 56) )
      goto LABEL_1493;
    v288 = v8 + 56LL * *((int *)v7 + 2);
    if ( (*(_WORD *)(v288 + 20) & 0x9000) != 0 )
      vdbeMemClearExternAndSetNull(v8 + 56LL * *((int *)v7 + 2));
    *(_OWORD *)v288 = *(_OWORD *)(v287 - 56);
    *(_QWORD *)(v288 + 16) = *(_QWORD *)(v287 - 40);
    *(_WORD *)(v288 + 20) = *(_WORD *)(v288 + 20) & 0x8FBF | 0x2040;
    goto LABEL_80;
  }
  if ( (unsigned int)v16 > 0x49 )
  {
    v276 = v16 - 74;
    if ( v276 )
    {
      v277 = v276 - 1;
      if ( v277 )
      {
        v278 = v277 - 1;
        if ( !v278 )
        {
          v282 = 56LL * *((int *)v7 + 1);
          *(_WORD *)(v282 + v8 + 20) &= 0xFFC1u;
          *(_WORD *)(v282 + v8 + 20) |= v11;
          goto LABEL_1431;
        }
        if ( v278 != 1 )
          goto LABEL_1431;
        v279 = out2Prerelease(v5, v7);
        v280 = *((_QWORD *)v7 + 2);
        v281 = v279;
        if ( v280 )
        {
          sqlite3VdbeMemSetStr(v279, v280, *((int *)v7 + 1), 0, 0);
        }
        else
        {
          sqlite3VdbeMemSetZeroBlob(v279, *((unsigned int *)v7 + 1));
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v281) )
            goto LABEL_1510;
        }
        LOBYTE(a4) = v734;
        *(_BYTE *)(v281 + 22) = v734;
LABEL_54:
        v6 = v738;
        v11 = 1;
        v14 = v735;
        goto LABEL_1431;
      }
    }
    v283 = out2Prerelease(v5, v7);
    v284 = *((_DWORD *)v7 + 3) - *((_DWORD *)v7 + 2);
    v11 = 1;
    v285 = *((_DWORD *)v7 + 1) != 0 ? 0x100 : 0;
    *(_DWORD *)(v283 + 16) = 0;
    v286 = v285 + 1;
    *(_WORD *)(v283 + 20) = v286;
    if ( v284 <= 0 )
      goto LABEL_1341;
    do
    {
      v283 += 56;
      if ( (*(_WORD *)(v283 + 20) & 0x9000) != 0 )
      {
        vdbeMemClearExternAndSetNull(v283);
        v11 = 1;
      }
      --v284;
      *(_WORD *)(v283 + 20) = v286;
      *(_DWORD *)(v283 + 16) = 0;
    }
    while ( v284 > 0 );
LABEL_563:
    v8 = v741;
    goto LABEL_60;
  }
  if ( (_DWORD)v16 == 73 )
    goto LABEL_1039;
  v263 = v16 - 68;
  if ( !v263 )
  {
    v274 = 56LL * *((int *)v7 + 1);
    v275 = *(_DWORD *)(v6 + 24LL * *(_QWORD *)(v274 + v8) + 8) - v11;
    *(_WORD *)(v274 + v8 + 20) = 0;
    v112 = 3LL * v275;
LABEL_219:
    v7 = (unsigned __int8 *)(v6 + 8 * v112);
    goto LABEL_220;
  }
  v264 = v263 - 1;
  if ( v264 )
  {
    v265 = v264 - 1;
    if ( v265 )
    {
      v266 = v265 - 1;
      if ( v266 )
      {
        if ( v266 != 1 )
          goto LABEL_1431;
        v267 = out2Prerelease(v5, v7);
        goto LABEL_539;
      }
      v268 = (__int64 *)out2Prerelease(v5, v7);
      v269 = *((int *)v7 + 1);
LABEL_541:
      *v268 = v269;
      goto LABEL_53;
    }
  }
  else if ( ((unsigned __int8)v11 & *(_BYTE *)(56LL * *((int *)v7 + 3) + v8 + 20)) == 0 )
  {
    goto LABEL_1431;
  }
  v270 = v5[33];
  if ( v270 && !*((_DWORD *)v7 + 1) )
  {
    v271 = *(_QWORD *)(v270 + 8);
    --*((_DWORD *)v5 + 70);
    v5[33] = v271;
    v272 = v5[7];
    *(_QWORD *)(v4 + 128) += v272;
    *(_QWORD *)(v4 + 120) = v272;
    v273 = sqlite3VdbeFrameRestore();
    v11 = 1;
    if ( *((_DWORD *)v7 + 2) == 4 )
      v273 = *(_DWORD *)(v5[17] + 24LL * v273 + 8) - 1;
    v6 = v5[17];
    v8 = v5[13];
    v738 = v6;
    v741 = v8;
    v7 = (unsigned __int8 *)(v6 + 24LL * v273);
    goto LABEL_100;
  }
  v725 = *((_DWORD *)v7 + 1);
  *((_DWORD *)v5 + 13) = v725;
  *((_BYTE *)v5 + 196) = v7[8];
  if ( v725 )
  {
    if ( *((_WORD *)v7 + 1) )
    {
      sqlite3VdbeError(v5, "%s constraint failed", off_1400AA2B0[*((unsigned __int16 *)v7 + 1)]);
      if ( *((_QWORD *)v7 + 2) )
        v5[21] = sqlite3MPrintf(v4, "%z: %s", v5[21]);
    }
    else
    {
      sqlite3VdbeError(v5, "%s", *((const char **)v7 + 2));
    }
    sqlite3_log(
      *((unsigned int *)v7 + 1),
      "abort at %d in [%s]: %s",
      -1431655765 * ((__int64)&v7[-v738] >> 3),
      (const char *)v5[31],
      (const char *)v5[21]);
  }
  v726 = sqlite3VdbeHalt(v5);
  v49 = v745;
  v15 = v726;
  v10 = v739;
  v143 = v740;
  if ( v726 == 5 )
    *((_DWORD *)v5 + 13) = 5;
  else
    v15 = *((_DWORD *)v5 + 13) != 0 ? 1 : 101;
LABEL_1531:
  while ( v143 >= v10 )
  {
    v730 = *(__int64 (__fastcall **)(_QWORD))(v49 + 528);
    if ( !v730 )
      break;
    v10 += *(unsigned int *)(v49 + 544);
    v731 = v730(*(_QWORD *)(v49 + 536));
    v49 = v745;
    if ( v731 )
    {
      v10 = -1;
      goto LABEL_1501;
    }
  }
  *((_DWORD *)v5 + 57) += v143;
  if ( *((_DWORD *)v5 + 52) )
    sqlite3VdbeLeave(v5, v14, v49);
  return v15;
}

```

## disassembly

```asm
0x140074448  mov     rax, rsp
0x14007444b  push    rbp
0x14007444c  push    rbx
0x14007444d  push    rsi
0x14007444e  push    rdi
0x14007444f  push    r12
0x140074451  push    r13
0x140074453  push    r14
0x140074455  push    r15
0x140074457  lea     rbp, [rax-138h]
0x14007445e  sub     rsp, 1F8h
0x140074465  movaps  xmmword ptr [rax-58h], xmm6
0x140074469  movaps  xmmword ptr [rax-68h], xmm7
0x14007446d  movaps  xmmword ptr [rax-78h], xmm8
0x140074472  movaps  xmmword ptr [rax-88h], xmm9
0x14007447a  mov     rax, cs:__security_cookie
0x140074481  xor     rax, rsp
0x140074484  mov     [rbp+130h+var_90], rax
0x14007448b  mov     r12, [rcx]
0x14007448e  xor     ebx, ebx
0x140074490  mov     r14, rcx
0x140074493  mov     r8, [rcx+88h]
0x14007449a  mov     r13, r8
0x14007449d  mov     rsi, [rcx+68h]
0x1400744a1  mov     r10d, ebx
0x1400744a4  mov     [rsp+230h+var_1C0], rcx
0x1400744a9  mov     r9b, [r12+64h]
0x1400744ae  mov     byte ptr [rsp+230h+var_1F0], r9b
0x1400744b3  mov     [rsp+230h+var_1E0], r8
0x1400744b8  mov     [rbp+130h+var_1A8], r12
0x1400744bc  mov     [rbp+130h+var_194], bl
0x1400744bf  mov     [rsp+230h+var_1D0], rbx
0x1400744c4  mov     [rsp+230h+var_1C8], rsi
0x1400744c9  cmp     [rcx+0D0h], ebx
0x1400744cf  jz      short loc_1400744E1
0x1400744d1  call    sqlite3VdbeEnter
0x1400744d6  mov     r9b, byte ptr [rsp+230h+var_1F0]
0x1400744db  mov     r8, r13
0x1400744de  mov     r10d, ebx
0x1400744e1  cmp     [r12+210h], rbx
0x1400744e9  jz      short loc_140074504
0x1400744eb  mov     ecx, [r12+220h]
0x1400744f3  xor     edx, edx
0x1400744f5  mov     eax, [r14+0E4h]
0x1400744fc  div     ecx
0x1400744fe  sub     ecx, edx
0x140074500  mov     edi, ecx
0x140074502  jmp     short loc_140074508
0x140074504  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140074508  cmp     dword ptr [r14+34h], 7
0x14007450d  mov     r11d, 1
0x140074513  mov     [rsp+230h+var_1D8], rdi
0x140074518  jz      loc_14007A546
0x14007451e  mov     [r14+34h], ebx
0x140074522  mov     [r14+48h], rbx
0x140074526  mov     eax, [r12+198h]
0x14007452e  mov     [r12+298h], ebx
0x140074536  test    eax, eax
0x140074538  jnz     loc_14007A51D
0x14007453e  movsxd  rax, dword ptr [r14+30h]
0x140074542  xor     edi, edi
0x140074544  movsd   xmm9, cs:__real@c3e0000000000000
0x14007454d  mov     edx, edi
0x14007454f  movsd   xmm7, cs:__real@43e0000000000000
0x140074557  mov     r15d, edi
0x14007455a  mov     dword ptr [rsp+230h+var_1E8], edi
0x14007455e  xorps   xmm8, xmm8
0x140074562  lea     rcx, [rax+rax*2]
0x140074566  mov     [rsp+230h+var_1EC], edx
0x14007456a  lea     r13, [r8+rcx*8]
0x14007456e  mov     [rbp+130h+var_158], edi
0x140074571  lea     ecx, [rdi+4]
0x140074574  movzx   ebx, byte ptr [r13+0]
0x140074579  add     r10, r11
0x14007457c  mov     [rsp+230h+var_1B8], r13
0x140074581  mov     eax, 5
0x140074586  mov     [rsp+230h+var_1D0], r10
0x14007458b  cmp     ebx, 5Ah ; 'Z'
0x14007458e  ja      loc_140076B08
0x140074594  jz      loc_140076A0C
0x14007459a  cmp     ebx, 2Ch ; ','
0x14007459d  ja      loc_140075B77
0x1400745a3  jz      loc_140075AE6
0x1400745a9  cmp     ebx, 16h
0x1400745ac  ja      loc_1400753CD
0x1400745b2  jz      loc_1400751B8
0x1400745b8  cmp     ebx, 0Bh
0x1400745bb  ja      loc_140074FB8
0x1400745c1  jz      loc_140074F91
0x1400745c7  cmp     ebx, eax
0x1400745c9  ja      loc_140074D6C
0x1400745cf  jz      loc_140074D2F
0x1400745d5  test    ebx, ebx
0x1400745d7  jz      loc_140074958
0x1400745dd  sub     ebx, 1
0x1400745e0  jz      loc_14007A090
0x1400745e6  sub     ebx, 1
0x1400745e9  jz      loc_140074823
0x1400745ef  sub     ebx, 1
0x1400745f2  jz      loc_140074785
0x1400745f8  cmp     ebx, 1
0x1400745fb  jnz     loc_140079F8A
0x140074601  mov     rdx, r13
0x140074604  mov     rcx, r14
0x140074607  call    out2Prerelease
0x14007460c  movsxd  rcx, dword ptr [r13+4]
0x140074610  mov     r14, rax
0x140074613  mov     rax, [r12+20h]
0x140074618  mov     ebx, [r13+0Ch]
0x14007461c  shl     rcx, 5
0x140074620  mov     r15, [rcx+rax+8]
0x140074625  mov     rcx, r15
0x140074628  call    sqlite3BtreePager
0x14007462d  mov     rcx, rax
0x140074630  mov     rsi, rax
0x140074633  call    sqlite3PagerGetJournalMode
0x140074638  cmp     ebx, 0FFFFFFFFh
0x14007463b  mov     rcx, rsi
0x14007463e  mov     edi, eax
0x140074640  cmovz   ebx, eax
0x140074643  call    sqlite3PagerOkToChangeJournalMode
0x140074648  test    eax, eax
0x14007464a  mov     edx, 1
0x14007464f  mov     rcx, rsi
0x140074652  cmovz   ebx, edi
0x140074655  call    sqlite3PagerFilename
0x14007465a  mov     ecx, 5
0x14007465f  cmp     ebx, ecx
0x140074661  jnz     short loc_140074695
0x140074663  mov     rcx, rax
0x140074666  call    sqlite3Strlen30
0x14007466b  test    eax, eax
0x14007466d  jz      short loc_14007467B
0x14007466f  mov     rcx, rsi
0x140074672  call    sqlite3PagerWalSupported
0x140074677  test    eax, eax
0x140074679  jnz     short loc_140074690
0x14007467b  mov     ebx, edi
0x14007467d  mov     r15d, dword ptr [rsp+230h+var_1E8]
0x140074682  test    r15d, r15d
0x140074685  jz      loc_14007471D
0x14007468b  jmp     loc_14007471B
0x140074690  mov     ecx, 5
0x140074695  cmp     ebx, edi
0x140074697  jz      short loc_14007467D
0x140074699  cmp     edi, ecx
0x14007469b  jz      short loc_1400746A1
0x14007469d  cmp     ebx, ecx
0x14007469f  jnz     short loc_14007467D
0x1400746a1  cmp     byte ptr [r12+65h], 0
0x1400746a7  jz      loc_140079F9C
0x1400746ad  cmp     dword ptr [r12+0DCh], 1
0x1400746b6  jg      loc_140079F9C
0x1400746bc  cmp     edi, ecx
0x1400746be  jnz     short loc_1400746DF
0x1400746c0  mov     rdx, r12
0x1400746c3  mov     rcx, rsi
0x1400746c6  call    sqlite3PagerCloseWal
0x1400746cb  mov     dword ptr [rsp+230h+var_1E8], eax
0x1400746cf  test    eax, eax
0x1400746d1  jnz     short loc_140074716
0x1400746d3  mov     edx, ebx
0x1400746d5  mov     rcx, rsi
0x1400746d8  call    sqlite3PagerSetJournalMode
0x1400746dd  jmp     short loc_1400746F6
0x1400746df  cmp     edi, 4
0x1400746e2  jnz     short loc_1400746EF
0x1400746e4  lea     edx, [rdi-2]
0x1400746e7  mov     rcx, rsi
0x1400746ea  call    sqlite3PagerSetJournalMode
0x1400746ef  cmp     dword ptr [rsp+230h+var_1E8], 0
0x1400746f4  jnz     short loc_140074716
0x1400746f6  xor     edx, edx
0x1400746f8  lea     ecx, [rdx+5]
0x1400746fb  cmp     ebx, ecx
0x1400746fd  mov     rcx, r15
0x140074700  setz    dl
0x140074703  inc     edx
0x140074705  call    sqlite3BtreeSetVersion
0x14007470a  mov     r15d, eax
0x14007470d  mov     dword ptr [rsp+230h+var_1E8], eax
0x140074711  jmp     loc_140074682
0x140074716  mov     r15d, dword ptr [rsp+230h+var_1E8]
0x14007471b  mov     ebx, edi
0x14007471d  mov     edx, ebx
0x14007471f  mov     rcx, rsi
0x140074722  call    sqlite3PagerSetJournalMode
0x140074727  mov     ecx, eax
0x140074729  mov     word ptr [r14+14h], 2202h
0x140074730  call    sqlite3JournalModename
0x140074735  mov     rcx, rax
0x140074738  mov     [r14+8], rax
0x14007473c  call    sqlite3Strlen30
0x140074741  movzx   edx, byte ptr [rsp+230h+var_1F0]
0x140074746  mov     rcx, r14
0x140074749  mov     [r14+10h], eax
0x14007474d  mov     byte ptr [r14+16h], 1
0x140074752  call    sqlite3VdbeChangeEncoding
0x140074757  mov     r14, [rsp+230h+var_1C0]
0x14007475c  xor     edi, edi
0x14007475e  test    r15d, r15d
0x140074761  jnz     loc_1400754D8
0x140074767  mov     rsi, [rsp+230h+var_1C8]
0x14007476c  mov     r9b, byte ptr [rsp+230h+var_1F0]
0x140074771  mov     r8, [rsp+230h+var_1E0]
0x140074776  mov     r11d, 1
0x14007477c  mov     edx, [rsp+230h+var_1EC]
0x140074780  jmp     loc_140079F85
0x140074785  mov     r8d, [r13+8]
0x140074789  lea     rax, [rbp+130h+var_9C+4]
0x140074790  mov     edx, [r13+4]
0x140074794  lea     r9, [rbp+130h+var_9C]
0x14007479b  mov     rcx, r12
0x14007479e  mov     [rsp+230h+var_210], rax
0x1400747a3  mov     [rbp+130h+var_A0], edi
0x1400747a9  mov     [rbp+130h+var_9C], 0FFFFFFFFFFFFFFFFh
0x1400747b4  call    sqlite3Checkpoint
0x1400747b9  mov     dword ptr [rsp+230h+var_1E8], eax
0x1400747bd  mov     r15d, eax
0x1400747c0  test    eax, eax
0x1400747c2  jz      short loc_1400747E2
0x1400747c4  mov     ecx, 5
0x1400747c9  cmp     eax, ecx
0x1400747cb  jnz     loc_1400754D8
0x1400747d1  mov     r15d, edi
0x1400747d4  mov     dword ptr [rsp+230h+var_1E8], edi
0x1400747d8  mov     [rbp+130h+var_A0], 1
0x1400747e2  movsxd  rax, dword ptr [r13+0Ch]
0x1400747e6  imul    rbx, rax, 38h ; '8'
0x1400747ea  add     rbx, rsi
0x1400747ed  movsxd  rdx, [rbp+rdi*4+130h+var_A0]
0x1400747f5  mov     rcx, rbx
0x1400747f8  call    sqlite3VdbeMemSetInt64
0x1400747fd  mov     r11d, 1
0x140074803  add     rbx, 38h ; '8'
0x140074807  add     rdi, r11
0x14007480a  cmp     rdi, 3
0x14007480e  jnz     short loc_1400747ED
0x140074810  mov     edx, [rsp+230h+var_1EC]
0x140074814  mov     r8, [rsp+230h+var_1E0]
0x140074819  mov     r9b, byte ptr [rsp+230h+var_1F0]
0x14007481e  jmp     loc_140079F83
0x140074823  mov     edx, [r13+8]
0x140074827  mov     dword ptr [rsp+230h+var_1B8], edi
0x14007482b  test    edx, edx
0x14007482d  jz      short loc_140074847
0x14007482f  mov     rax, [r12+30h]
0x140074834  mov     rcx, 200100000h
0x14007483e  test    rcx, rax
0x140074841  jnz     loc_140079FCF
0x140074847  movsxd  rdi, dword ptr [r13+4]
0x14007484b  mov     rsi, [r12+20h]
0x140074850  shl     rdi, 5
0x140074854  mov     rbx, [rdi+rsi+8]
0x140074859  test    rbx, rbx
0x14007485c  jz      loc_140074916
0x140074862  lea     r8, [rsp+230h+var_1B8]
0x140074867  mov     rcx, rbx
0x14007486a  call    sqlite3BtreeBeginTrans
0x14007486f  xor     ecx, ecx
0x140074871  mov     dword ptr [rsp+230h+var_1E8], eax
0x140074875  mov     r15d, eax
0x140074878  test    eax, eax
0x14007487a  jnz     loc_140079FE7
0x140074880  test    byte ptr [r14+0C8h], 20h
0x140074888  jz      loc_140074954
0x14007488e  cmp     [r13+8], ecx
0x140074892  jz      loc_140074954
0x140074898  cmp     [r12+65h], cl
0x14007489d  jz      short loc_1400748AE
0x14007489f  cmp     dword ptr [r12+0DCh], 1
0x1400748a8  jle     loc_140074954
0x1400748ae  mov     r8d, [r14+40h]
0x1400748b2  test    r8d, r8d
0x1400748b5  jnz     short loc_1400748D3
0x1400748b7  inc     dword ptr [r12+2F4h]
0x1400748bf  mov     r8d, [r12+2F0h]
0x1400748c7  add     r8d, [r12+2F4h]
0x1400748cf  mov     [r14+40h], r8d
0x1400748d3  dec     r8d
0x1400748d6  xor     edx, edx
0x1400748d8  mov     rcx, r12
0x1400748db  call    sqlite3VtabSavepoint
0x1400748e0  mov     dword ptr [rsp+230h+var_1E8], eax
0x1400748e4  mov     r15d, eax
0x1400748e7  test    eax, eax
0x1400748e9  jnz     short loc_1400748FE
0x1400748eb  mov     edx, [r14+40h]
0x1400748ef  mov     rcx, rbx
0x1400748f2  call    sqlite3BtreeBeginStmt
0x1400748f7  mov     r15d, eax
0x1400748fa  mov     dword ptr [rsp+230h+var_1E8], eax
0x1400748fe  mov     rax, [r12+2F8h]
0x140074906  mov     [r14+58h], rax
0x14007490a  mov     rax, [r12+300h]
0x140074912  mov     [r14+60h], rax
0x140074916  xor     ebx, ebx
0x140074918  test    r15d, r15d
0x14007491b  jnz     loc_1400754D8
0x140074921  cmp     [r13+2], bx
  ... truncated ...
```
