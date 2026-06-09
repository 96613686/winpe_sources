# CBulkFormat::GetXMLFormatStreamFromBCP(CComPtr<ISequentialStream>,BCP_COL_INFO *)

- ea: `0x1801482e0`
- end: `0x18014c85c`
- name: `?GetXMLFormatStreamFromBCP@CBulkFormat@@QEAA?AV?$CComPtr@UISequentialStream@@@@V2@PEAUBCP_COL_INFO@@@Z`
- size: `17788`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180146070`
- `0x18014feb0`

## callees

- `0x180001760`
- `0x180003488`
- `0x180003824`
- `0x180003d20`
- `0x180003d80`
- `0x180143b20`
- `0x180143b40`
- `0x180146780`
- `0x180146920`
- `0x180146ee0`
- `0x180146f90`
- `0x1801471d0`
- `0x180147ea0`
- `0x1801480c0`
- `0x1801482e0`
- `0x1801509e0`
- `0x180150ad0`
- `0x1801a65e1`
- `0x1801a6788`
- `0x1801a6800`
- `0x1801a6968`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!isspace` at `0x180148634`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x180148759`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x1801495d5`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x18014967f`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x18014971f`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x180148634`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x180148759`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x1801495d5`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x18014967f`
- `api-ms-win-crt-string-l1-1-0!isspace` at `0x18014971f`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180148608`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180148732`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1801495a6`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180149650`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1801496f0`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180148608`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180148732`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1801495a6`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x180149650`
- `api-ms-win-crt-convert-l1-1-0!_strtoui64` at `0x1801496f0`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x18014ba55`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x18014ba55`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
CFmtStream **__fastcall CBulkFormat::GetXMLFormatStreamFromBCP(__int64 a1, CFmtStream **a2, _QWORD *a3, __int64 a4)
{
  __int64 v6; // r14
  __int64 v7; // rax
  CFmtStream *v8; // rdi
  __int64 v9; // rcx
  const WCHAR *v10; // rcx
  char *v11; // r8
  int v12; // eax
  int v13; // edx
  const WCHAR *v14; // rcx
  char *v15; // r8
  int v16; // eax
  int v17; // edx
  const WCHAR *v18; // rcx
  char *v19; // r8
  int v20; // eax
  int v21; // edx
  const WCHAR *v22; // rcx
  char *v23; // r8
  int v24; // eax
  int v25; // edx
  const WCHAR *v26; // rcx
  char *v27; // r8
  int v28; // eax
  int v29; // edx
  const WCHAR *v30; // rcx
  char *v31; // r8
  int v32; // eax
  int v33; // edx
  const WCHAR *v34; // rcx
  char *v35; // r8
  int v36; // eax
  int v37; // edx
  size_t v38; // r12
  __int64 v39; // rdx
  bool v40; // cf
  __int64 v41; // rdx
  char *v42; // rax
  char *v43; // r15
  unsigned int v44; // ebx
  int v45; // eax
  unsigned __int64 v46; // rax
  int v47; // r14d
  __int64 v48; // rsi
  const WCHAR *v49; // rcx
  char *v50; // r8
  int v51; // eax
  int v52; // edx
  const WCHAR *v53; // rcx
  char *v54; // r8
  int v55; // eax
  int v56; // edx
  const WCHAR *v57; // rcx
  char *v58; // r8
  int v59; // eax
  int v60; // edx
  const WCHAR *v61; // rcx
  char *v62; // r8
  int v63; // eax
  int v64; // edx
  const WCHAR *v65; // rcx
  char *v66; // r8
  int v67; // eax
  int v68; // edx
  const WCHAR *v69; // rcx
  char *v70; // r8
  int v71; // eax
  int v72; // edx
  const WCHAR *v73; // rcx
  char *v74; // r8
  int v75; // eax
  int v76; // edx
  const WCHAR *v77; // rcx
  char *v78; // r8
  int v79; // eax
  int v80; // edx
  const WCHAR *v81; // rcx
  char *v82; // r8
  int v83; // eax
  int v84; // edx
  const WCHAR *v85; // rcx
  char *v86; // r8
  int v87; // eax
  int v88; // edx
  const WCHAR *v89; // rcx
  char *v90; // r8
  int v91; // eax
  int v92; // edx
  const WCHAR *v93; // rcx
  char *v94; // r8
  int v95; // eax
  int v96; // edx
  const WCHAR *v97; // rcx
  char *v98; // r8
  int v99; // eax
  int v100; // edx
  const WCHAR *v101; // rcx
  char *v102; // r8
  int v103; // eax
  int v104; // edx
  const WCHAR *v105; // rcx
  char *v106; // r8
  int v107; // eax
  int v108; // edx
  const WCHAR *v109; // rcx
  char *v110; // r8
  int v111; // eax
  int v112; // edx
  const WCHAR *v113; // rcx
  char *v114; // r8
  int v115; // eax
  int v116; // edx
  const WCHAR *v117; // rcx
  char *v118; // r8
  int v119; // eax
  int v120; // edx
  const WCHAR *v121; // rcx
  char *v122; // r8
  int v123; // eax
  int v124; // edx
  const WCHAR *v125; // rcx
  char *v126; // r8
  int v127; // eax
  int v128; // edx
  const WCHAR *v129; // rcx
  char *v130; // r8
  int v131; // eax
  int v132; // edx
  const WCHAR *v133; // rcx
  char *v134; // r8
  int v135; // eax
  int v136; // edx
  const WCHAR *v137; // rcx
  char *v138; // r8
  int v139; // eax
  int v140; // edx
  const WCHAR *v141; // rcx
  char *v142; // r8
  int v143; // eax
  int v144; // edx
  const WCHAR *v145; // rcx
  char *v146; // r8
  int v147; // eax
  int v148; // edx
  const WCHAR *v149; // rcx
  char *v150; // r8
  int v151; // eax
  int v152; // edx
  const WCHAR *v153; // rcx
  char *v154; // r8
  int v155; // eax
  int v156; // edx
  const WCHAR *v157; // rcx
  char *v158; // r8
  int v159; // eax
  int v160; // edx
  const WCHAR *v161; // rcx
  char *v162; // r8
  int v163; // eax
  int v164; // edx
  const WCHAR *v165; // rcx
  char *v166; // r8
  int v167; // eax
  int v168; // edx
  const WCHAR *v169; // rcx
  char *v170; // r8
  int v171; // eax
  int v172; // edx
  const WCHAR *v173; // rcx
  char *v174; // r8
  int v175; // eax
  int v176; // edx
  const WCHAR *v177; // rcx
  char *v178; // r8
  int v179; // eax
  int v180; // edx
  const WCHAR *v181; // rcx
  char *v182; // r8
  int v183; // eax
  int v184; // edx
  const WCHAR *v185; // rcx
  char *v186; // r8
  int v187; // eax
  int v188; // edx
  const WCHAR *v189; // rcx
  char *v190; // r8
  int v191; // eax
  int v192; // edx
  const WCHAR *v193; // rcx
  char *v194; // r8
  int v195; // eax
  int v196; // edx
  const WCHAR *v197; // rcx
  char *v198; // r8
  int v199; // eax
  int v200; // edx
  const WCHAR *v201; // rcx
  char *v202; // r8
  int v203; // eax
  int v204; // edx
  const WCHAR *v205; // rcx
  char *v206; // r8
  int v207; // eax
  int v208; // edx
  const WCHAR *v209; // rcx
  char *v210; // r8
  int v211; // eax
  int v212; // edx
  const WCHAR *v213; // rcx
  char *v214; // r8
  int v215; // eax
  int v216; // edx
  const WCHAR *v217; // rcx
  char *v218; // r8
  int v219; // eax
  int v220; // edx
  const WCHAR *v221; // rcx
  char *v222; // r8
  int v223; // eax
  int v224; // edx
  const WCHAR *v225; // rcx
  char *v226; // r8
  int v227; // eax
  int v228; // edx
  const WCHAR *v229; // rcx
  char *v230; // r8
  int v231; // eax
  int v232; // edx
  const WCHAR *v233; // rcx
  char *v234; // r8
  int v235; // eax
  int v236; // edx
  const WCHAR *v237; // rcx
  char *v238; // r8
  int v239; // eax
  int v240; // edx
  int v241; // eax
  unsigned __int64 v242; // rax
  int v243; // esi
  unsigned int v244; // eax
  int v245; // ecx
  int v246; // eax
  unsigned __int64 v247; // rax
  int v248; // esi
  int v249; // eax
  unsigned __int64 v250; // rsi
  const WCHAR *v251; // rcx
  char *v252; // r8
  int v253; // eax
  int v254; // edx
  const WCHAR *v255; // rcx
  char *v256; // r8
  int v257; // eax
  int v258; // edx
  const WCHAR *v259; // rcx
  char *v260; // r8
  int v261; // eax
  int v262; // edx
  const WCHAR *v263; // rcx
  char *v264; // r8
  int v265; // eax
  int v266; // edx
  const WCHAR *v267; // rcx
  char *v268; // r8
  int v269; // eax
  int v270; // edx
  const WCHAR *v271; // rcx
  char *v272; // r8
  int v273; // eax
  int v274; // edx
  const WCHAR *v275; // rcx
  char *v276; // r8
  int v277; // eax
  int v278; // edx
  const WCHAR *v279; // rcx
  char *v280; // r8
  int v281; // eax
  int v282; // edx
  const WCHAR *v283; // rcx
  char *v284; // r8
  int v285; // eax
  int v286; // edx
  const WCHAR *v287; // rcx
  char *v288; // r8
  int v289; // eax
  int v290; // edx
  const WCHAR *v291; // rcx
  char *v292; // r8
  int v293; // eax
  int v294; // edx
  const WCHAR *v295; // rcx
  char *v296; // r8
  int v297; // eax
  int v298; // edx
  const WCHAR *v299; // rcx
  char *v300; // r8
  int v301; // eax
  int v302; // edx
  const WCHAR *v303; // rcx
  char *v304; // r8
  int v305; // eax
  int v306; // edx
  const WCHAR *v307; // rcx
  char *v308; // r8
  int v309; // eax
  int v310; // edx
  __int64 v311; // rax
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  unsigned int v317; // r12d
  unsigned int v318; // esi
  unsigned int v319; // ebx
  __int64 v320; // rbx
  const WCHAR *v321; // rcx
  char *v322; // r8
  int v323; // eax
  int v324; // edx
  __int64 v325; // rax
  __int64 v326; // rax
  __int64 v327; // rax
  __int64 v328; // rax
  __int64 v329; // rax
  const WCHAR *v330; // rcx
  char *v331; // r8
  int v332; // eax
  int v333; // edx
  const WCHAR *v334; // rcx
  char *v335; // r8
  int v336; // eax
  int v337; // edx
  const WCHAR *v338; // rcx
  char *v339; // r8
  int v340; // eax
  int v341; // edx
  const WCHAR *v342; // rcx
  char *v343; // r8
  int v344; // eax
  int v345; // edx
  const WCHAR *v346; // rcx
  char *v347; // r8
  int v348; // eax
  int v349; // edx
  const WCHAR *v350; // rcx
  char *v351; // r8
  int v352; // eax
  int v353; // edx
  int v354; // r13d
  const WCHAR *v355; // rcx
  char *v356; // r8
  int v357; // eax
  int v358; // edx
  const WCHAR *v359; // rcx
  char *v360; // r8
  int v361; // eax
  int v362; // edx
  const WCHAR *v363; // rcx
  char *v364; // r8
  int v365; // eax
  int v366; // edx
  const WCHAR *v367; // rcx
  char *v368; // r9
  int v369; // eax
  int v370; // edx
  const WCHAR *v371; // rcx
  char *v372; // r10
  int v373; // eax
  int v374; // edx
  const WCHAR *v375; // rcx
  char *v376; // r8
  int v377; // eax
  int v378; // edx
  const WCHAR *v379; // rcx
  char *v380; // r8
  int v381; // eax
  int v382; // edx
  __int64 v383; // rax
  __int64 v384; // rax
  char *v385; // rsi
  char *v386; // rbx
  __int16 v387; // ax
  CFmtStream *v388; // rcx
  const wchar_t *v389; // rdx
  __int64 v390; // rax
  __int64 v391; // rax
  const WCHAR *v392; // rsi
  WCHAR v393; // ax
  CFmtStream *v394; // rcx
  const wchar_t *v395; // rdx
  __int64 v396; // rax
  __int64 v397; // rax
  const WCHAR *v398; // rsi
  WCHAR v399; // ax
  CFmtStream *v400; // rcx
  const wchar_t *v401; // rdx
  __int64 v402; // rax
  __int64 v403; // rax
  __int64 v404; // rax
  __int64 v405; // rax
  const WCHAR *v406; // rcx
  char *v407; // r8
  int v408; // eax
  int v409; // edx
  const WCHAR *v410; // rcx
  char *v411; // r8
  int v412; // eax
  int v413; // edx
  const WCHAR *v414; // rcx
  char *v415; // r8
  int v416; // eax
  int v417; // edx
  const WCHAR *v418; // rcx
  char *v419; // r8
  int v420; // eax
  int v421; // edx
  unsigned int v422; // ebx
  __int64 v423; // rax
  __int64 v424; // rax
  __int64 v425; // rax
  __int64 v426; // rax
  const WCHAR *v427; // rcx
  char *v428; // r8
  int v429; // eax
  int v430; // edx
  __int64 v431; // rax
  __int64 v432; // rax
  const WCHAR *v433; // rcx
  char *v434; // r8
  int v435; // eax
  int v436; // edx
  __int64 v437; // rax
  __int64 v438; // rax
  __int64 v439; // rax
  const WCHAR *v440; // rsi
  void *v441; // rbx
  WCHAR v442; // ax
  CFmtStream *v443; // rcx
  const wchar_t *v444; // rdx
  __int64 v445; // rax
  __int64 v446; // rax
  const WCHAR *v447; // rsi
  WCHAR v448; // ax
  CFmtStream *v449; // rcx
  const wchar_t *v450; // rdx
  __int64 v451; // rax
  __int64 v452; // rax
  const WCHAR *v453; // rsi
  WCHAR v454; // ax
  CFmtStream *v455; // rcx
  const wchar_t *v456; // rdx
  __int64 v457; // rax
  __int64 v458; // rax
  __int64 v459; // rbx
  __int64 v460; // rax
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rax
  const WCHAR *v464; // rcx
  char *v465; // r8
  int v466; // eax
  int v467; // edx
  __int64 v468; // rax
  __int64 v469; // rax
  const WCHAR *v470; // rcx
  char *v471; // r8
  int v472; // eax
  int v473; // edx
  __int64 v474; // rax
  __int64 v475; // rax
  const WCHAR *v476; // rsi
  void *v477; // rbx
  WCHAR v478; // ax
  CFmtStream *v479; // rcx
  const wchar_t *v480; // rdx
  __int64 v481; // rax
  __int64 v482; // rax
  const WCHAR *v483; // rsi
  WCHAR v484; // ax
  CFmtStream *v485; // rcx
  const wchar_t *v486; // rdx
  __int64 v487; // rax
  __int64 v488; // rax
  const WCHAR *v489; // rsi
  WCHAR v490; // ax
  CFmtStream *v491; // rcx
  const wchar_t *v492; // rdx
  __int64 v493; // rax
  __int64 v494; // rax
  __int64 v495; // rax
  __int64 v496; // rax
  const WCHAR *v497; // rcx
  char *v498; // r8
  int v499; // eax
  int v500; // edx
  __int64 v501; // rax
  __int64 v502; // rax
  const WCHAR *v503; // rbx
  WCHAR v504; // ax
  CFmtStream *v505; // rcx
  const wchar_t *v506; // rdx
  __int64 v507; // rax
  __int64 v508; // rax
  const WCHAR *v509; // rsi
  void *v510; // rbx
  WCHAR v511; // ax
  CFmtStream *v512; // rcx
  const wchar_t *v513; // rdx
  __int64 v514; // rax
  __int64 v515; // rax
  const WCHAR *v516; // rsi
  WCHAR v517; // ax
  CFmtStream *v518; // rcx
  const wchar_t *v519; // rdx
  __int64 v520; // rax
  __int64 v521; // rax
  const WCHAR *v522; // rsi
  WCHAR v523; // ax
  CFmtStream *v524; // rcx
  const wchar_t *v525; // rdx
  __int64 v526; // rax
  __int64 v527; // rax
  const WCHAR *v528; // rbx
  WCHAR v529; // ax
  CFmtStream *v530; // rcx
  const wchar_t *v531; // rdx
  const WCHAR *v532; // rcx
  char *v533; // r8
  int v534; // eax
  int v535; // edx
  const WCHAR *v536; // rcx
  char *v537; // r8
  int v538; // eax
  int v539; // edx
  const WCHAR *v540; // rcx
  char *v541; // r8
  int v542; // eax
  int v543; // edx
  const WCHAR *v544; // rcx
  char *v545; // r8
  int v546; // eax
  int v547; // edx
  unsigned int v548; // ebx
  __int64 v549; // rax
  __int64 v550; // rax
  __int64 v551; // rax
  __int64 v552; // rax
  const WCHAR *v553; // rcx
  char *v554; // r8
  int v555; // eax
  int v556; // edx
  __int64 v557; // rax
  __int64 v558; // rax
  const WCHAR *v559; // rbx
  WCHAR v560; // ax
  CFmtStream *v561; // rcx
  const wchar_t *v562; // rdx
  __int64 v563; // rax
  __int64 v564; // rax
  __int64 v565; // rax
  unsigned int v566; // r13d
  __int64 v567; // r12
  int v568; // r14d
  char *v569; // r9
  const WCHAR *v570; // rcx
  char *v571; // r8
  int v572; // eax
  int v573; // edx
  unsigned int v574; // ecx
  __int64 v575; // r15
  char *v576; // rsi
  unsigned int v577; // r13d
  __int64 v578; // rax
  __int64 v579; // rax
  __int64 v580; // rax
  __int64 v581; // rax
  __int64 v582; // rax
  __int64 v583; // rax
  __int64 v584; // rax
  __int64 v585; // rax
  const WCHAR *v586; // rcx
  char *v587; // r8
  int v588; // eax
  int v589; // edx
  const WCHAR *v590; // rcx
  char *v591; // r8
  int v592; // eax
  int v593; // edx
  const WCHAR *v594; // rcx
  char *v595; // r8
  int v596; // eax
  int v597; // edx
  const WCHAR *v598; // rcx
  char *v599; // r8
  int v600; // eax
  int v601; // edx
  const WCHAR *v602; // rcx
  char *v603; // r8
  int v604; // eax
  int v605; // edx
  const WCHAR *v606; // rcx
  char *v607; // r8
  int v608; // eax
  int v609; // edx
  __int64 v610; // rax
  __int64 v611; // rax
  const WCHAR *v612; // rsi
  void *v613; // rbx
  WCHAR v614; // ax
  CFmtStream *v615; // rcx
  const wchar_t *v616; // rdx
  CWStr *v617; // rax
  int v618; // r14d
  const WCHAR *v619; // rax
  const WCHAR *v620; // rcx
  char v621; // r9
  char *v622; // r8
  int v623; // eax
  int v624; // edx
  CWStr *v625; // rax
  const WCHAR *v626; // rax
  const WCHAR *v627; // rcx
  char *v628; // r8
  int v629; // eax
  int v630; // edx
  char v631; // bl
  unsigned int v632; // ebx
  __int64 v633; // rax
  __int64 v634; // rax
  __int64 v635; // rax
  __int64 v636; // rax
  unsigned int v637; // ebx
  __int64 v638; // rax
  __int64 v639; // rax
  __int64 v640; // rax
  __int64 v641; // rax
  CWStr *v642; // rax
  const WCHAR *v643; // rax
  const WCHAR *v644; // rcx
  char v645; // r9
  char *v646; // r8
  int v647; // eax
  int v648; // edx
  CWStr *v649; // rax
  const WCHAR *v650; // rax
  const WCHAR *v651; // rcx
  char *v652; // r8
  int v653; // eax
  int v654; // edx
  CWStr *v655; // rax
  const WCHAR *v656; // rax
  const WCHAR *v657; // rcx
  char *v658; // r8
  int v659; // eax
  int v660; // edx
  char v661; // bl
  __int64 v662; // rax
  __int64 v663; // rax
  const WCHAR *v664; // rcx
  char *v665; // r8
  int v666; // eax
  int v667; // edx
  const WCHAR *v668; // rcx
  char *v669; // r8
  int v670; // eax
  int v671; // edx
  unsigned int v672; // ebx
  __int64 v673; // rax
  __int64 v674; // rax
  __int64 v675; // rax
  __int64 v676; // rax
  unsigned int v677; // ebx
  __int64 v678; // rax
  __int64 v679; // rax
  __int64 v680; // rax
  __int64 v681; // rax
  const WCHAR *v682; // rcx
  char *v683; // r8
  int v684; // eax
  int v685; // edx
  const WCHAR *v686; // rcx
  char *v687; // r8
  int v688; // eax
  int v689; // edx
  const WCHAR *v690; // rcx
  char *v691; // r8
  int v692; // eax
  int v693; // edx
  unsigned int v694; // ebx
  __int64 v695; // rax
  __int64 v696; // rax
  __int64 v697; // rax
  __int64 v698; // rax
  __int64 v699; // rax
  __int64 v700; // rax
  __int64 v701; // rax
  __int64 v702; // rax
  CFmtStream **v703; // rsi
  size_t NumOfElements; // [rsp+30h] [rbp-D0h] BYREF
  int v706; // [rsp+38h] [rbp-C8h]
  int v707; // [rsp+3Ch] [rbp-C4h]
  void *v708; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  void *v710; // [rsp+50h] [rbp-B0h] BYREF
  void *v711; // [rsp+58h] [rbp-A8h] BYREF
  void *v712; // [rsp+60h] [rbp-A0h] BYREF
  void *v713; // [rsp+68h] [rbp-98h] BYREF
  void *v714; // [rsp+70h] [rbp-90h] BYREF
  char *v715; // [rsp+78h] [rbp-88h]
  char *v716; // [rsp+80h] [rbp-80h] BYREF
  char *v717; // [rsp+88h] [rbp-78h] BYREF
  void *v718; // [rsp+90h] [rbp-70h] BYREF
  void *v719; // [rsp+98h] [rbp-68h] BYREF
  void *v720; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v721; // [rsp+A8h] [rbp-58h]
  CFmtStream **v722; // [rsp+B0h] [rbp-50h]
  _QWORD *v723; // [rsp+B8h] [rbp-48h]
  __int64 v724; // [rsp+C0h] [rbp-40h]
  char *v725; // [rsp+C8h] [rbp-38h] BYREF
  char *EndPtr; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v727; // [rsp+E0h] [rbp-20h] BYREF
  char v728[4096]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v729; // [rsp+10E8h] [rbp+FE8h]
  char String[24]; // [rsp+10F0h] [rbp+FF0h] BYREF

  v721 = a4;
  pExceptionObject = a3;
  v722 = a2;
  v708 = a2;
  v723 = a3;
  v6 = 0;
  v706 = 0;
  v715 = 0;
  v7 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 32);
  v8 = (CFmtStream *)v7;
  if ( !v7 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)String);
    throw (std::bad_alloc *)String;
  }
  *(_DWORD *)(v7 + 12) = 0;
  *(_QWORD *)(v7 + 24) = 0;
  *(_QWORD *)v7 = &CFmtStream::`vftable';
  *(_DWORD *)(v7 + 8) = 0;
  *(_QWORD *)(v7 + 24) = v7 + 16;
  *(_QWORD *)(v7 + 16) = v7 + 16;
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *(_QWORD *)(v7 + 24) = v7 + 16;
  *(_QWORD *)(v7 + 16) = v7 + 16;
  v724 = v7;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v706 = 64;
  memset_0(&v727, 0, 0x1010u);
  v9 = *a3;
  v727 = v9;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  memset_0(v728, 0, sizeof(v728));
  v729 = 0;
  GetString((struct CWStr *)(a1 + 144), -1, (struct CBulkFmtStreamReader *)&v727);
  if ( !FORMAT_VERSION_110 )
    goto LABEL_17;
  v10 = &Class;
  if ( *(_QWORD *)(a1 + 144) )
    v10 = *(const WCHAR **)(a1 + 144);
  v11 = (char *)((char *)FORMAT_VERSION_110 - (char *)v10);
  do
  {
    v12 = *(unsigned __int16 *)&v11[(_QWORD)v10];
    v13 = *v10 - v12;
    if ( v13 )
      break;
    ++v10;
  }
  while ( v12 );
  if ( v13 )
  {
LABEL_17:
    if ( !FORMAT_VERSION_100 )
      goto LABEL_24;
    v14 = &Class;
    if ( *(_QWORD *)(a1 + 144) )
      v14 = *(const WCHAR **)(a1 + 144);
    v15 = (char *)((char *)FORMAT_VERSION_100 - (char *)v14);
    do
    {
      v16 = *(unsigned __int16 *)&v15[(_QWORD)v14];
      v17 = *v14 - v16;
      if ( v17 )
        break;
      ++v14;
    }
    while ( v16 );
    if ( v17 )
    {
LABEL_24:
      if ( !FORMAT_VERSION_90 )
        goto LABEL_31;
      v18 = &Class;
      if ( *(_QWORD *)(a1 + 144) )
        v18 = *(const WCHAR **)(a1 + 144);
      v19 = (char *)((char *)FORMAT_VERSION_90 - (char *)v18);
      do
      {
        v20 = *(unsigned __int16 *)&v19[(_QWORD)v18];
        v21 = *v18 - v20;
        if ( v21 )
          break;
        ++v18;
      }
      while ( v20 );
      if ( v21 )
      {
LABEL_31:
        if ( !FORMAT_VERSION_80 )
          goto LABEL_38;
        v22 = &Class;
        if ( *(_QWORD *)(a1 + 144) )
          v22 = *(const WCHAR **)(a1 + 144);
        v23 = (char *)((char *)FORMAT_VERSION_80 - (char *)v22);
        do
        {
          v24 = *(unsigned __int16 *)&v23[(_QWORD)v22];
          v25 = *v22 - v24;
          if ( v25 )
            break;
          ++v22;
        }
        while ( v24 );
        if ( v25 )
        {
LABEL_38:
          if ( !FORMAT_VERSION_70 )
            goto LABEL_45;
          v26 = &Class;
          if ( *(_QWORD *)(a1 + 144) )
            v26 = *(const WCHAR **)(a1 + 144);
          v27 = (char *)((char *)FORMAT_VERSION_70 - (char *)v26);
          do
          {
            v28 = *(unsigned __int16 *)&v27[(_QWORD)v26];
            v29 = *v26 - v28;
            if ( v29 )
              break;
            ++v26;
          }
          while ( v28 );
          if ( v29 )
          {
LABEL_45:
            if ( !FORMAT_VERSION_60 )
              goto LABEL_52;
            v30 = &Class;
            if ( *(_QWORD *)(a1 + 144) )
              v30 = *(const WCHAR **)(a1 + 144);
            v31 = (char *)((char *)FORMAT_VERSION_60 - (char *)v30);
            do
            {
              v32 = *(unsigned __int16 *)&v31[(_QWORD)v30];
              v33 = *v30 - v32;
              if ( v33 )
                break;
              ++v30;
            }
            while ( v32 );
            if ( v33 )
            {
LABEL_52:
              if ( !FORMAT_VERSION_42 )
                goto LABEL_1227;
              v34 = &Class;
              if ( *(_QWORD *)(a1 + 144) )
                v34 = *(const WCHAR **)(a1 + 144);
              v35 = (char *)((char *)FORMAT_VERSION_42 - (char *)v34);
              do
              {
                v36 = *(unsigned __int16 *)&v35[(_QWORD)v34];
                v37 = *v34 - v36;
                if ( v37 )
                  break;
                ++v34;
              }
              while ( v36 );
              if ( v37 )
              {
LABEL_1227:
                CBcpFmtException::CBcpFmtException(&pExceptionObject, 1);
                throw (CBcpFmtException *)&pExceptionObject;
              }
            }
          }
        }
      }
    }
  }
  EndPtr = 0;
  CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)&v727);
  if ( (unsigned int)CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)&v727, String, 0x14u)
    || (v38 = _strtoui64(String, &EndPtr, 10), NumOfElements = v38, v38 > 0x7FFFFFFF)
    || EndPtr && *EndPtr && !isspace((unsigned __int8)*EndPtr)
    || (unsigned int)(v38 - 1) > 0xFFF )
  {
    CBcpFmtException::CBcpFmtException(&pExceptionObject, 2);
    throw (CBcpFmtException *)&pExceptionObject;
  }
  _mm_lfence();
  v39 = 56LL * (unsigned int)v38;
  if ( !is_mul_ok((unsigned int)v38, 0x38u) )
    v39 = -1;
  v40 = __CFADD__(v39, 8);
  v41 = v39 + 8;
  if ( v40 )
    v41 = -1;
  v42 = (char *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v41);
  v708 = v42;
  if ( v42 )
  {
    _mm_lfence();
    *(_QWORD *)v42 = (unsigned int)v38;
    v43 = v42 + 8;
    EndPtr = v42 + 8;
    `eh vector constructor iterator'(
      v42 + 8,
      0x38u,
      (unsigned int)v38,
      (void (*)(void *))CBCPFormatField::CBCPFormatField,
      (void (*)(void *))CBCPFormatField::~CBCPFormatField);
  }
  else
  {
    v43 = 0;
    EndPtr = 0;
  }
  v715 = v43;
  if ( !v43 )
  {
    CXmlSyntaxException::CXmlSyntaxException((CXmlSyntaxException *)&v725, -2147024882);
    throw (CHRESULTException *)&v725;
  }
  v44 = 0;
  if ( (_DWORD)v38 )
  {
    _mm_lfence();
    do
    {
      v725 = 0;
      CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)&v727);
      v45 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)&v727, String, 0x14u);
      if ( v45 )
      {
        if ( v45 == -2147467259 )
        {
          CBcpFmtException::CBcpFmtException(&NumOfElements, 4, v44 + 1);
          throw (CBcpFmtException *)&NumOfElements;
        }
LABEL_1234:
        CBcpFmtException::CBcpFmtException(&NumOfElements, 3, v44 + 1);
        throw (CBcpFmtException *)&NumOfElements;
      }
      v46 = _strtoui64(String, &v725, 10);
      v47 = v46;
      if ( v46 > 0x7FFFFFFF || v725 && *v725 && !isspace((unsigned __int8)*v725) )
        goto LABEL_1234;
      *(_DWORD *)&v43[56 * v44] = v47;
      if ( *(_DWORD *)&v43[56 * v44] != v44 + 1 )
        goto LABEL_1234;
      v48 = 56LL * v44;
      GetString((struct CWStr *)&v43[v48 + 8], v44, (struct CBulkFmtStreamReader *)&v727);
      if ( !TYPE_SQLBIT )
        goto LABEL_88;
      v49 = &Class;
      if ( *(_QWORD *)&v43[v48 + 8] )
        v49 = *(const WCHAR **)&v43[v48 + 8];
      v50 = (char *)((char *)TYPE_SQLBIT - (char *)v49);
      do
      {
        v51 = *(unsigned __int16 *)&v50[(_QWORD)v49];
        v52 = *v49 - v51;
        if ( v52 )
          break;
        ++v49;
      }
      while ( v51 );
      if ( v52 )
      {
LABEL_88:
        if ( !TYPE_SQLTINYINT )
          goto LABEL_95;
        v53 = &Class;
        if ( *(_QWORD *)&v43[v48 + 8] )
          v53 = *(const WCHAR **)&v43[v48 + 8];
        v54 = (char *)((char *)TYPE_SQLTINYINT - (char *)v53);
        do
        {
          v55 = *(unsigned __int16 *)&v54[(_QWORD)v53];
          v56 = *v53 - v55;
          if ( v56 )
            break;
          ++v53;
        }
        while ( v55 );
        if ( v56 )
        {
LABEL_95:
          if ( !TYPE_SQLSMALLINT )
            goto LABEL_102;
          v57 = &Class;
          if ( *(_QWORD *)&v43[56 * v44 + 8] )
            v57 = *(const WCHAR **)&v43[56 * v44 + 8];
          v58 = (char *)((char *)TYPE_SQLSMALLINT - (char *)v57);
          do
          {
            v59 = *(unsigned __int16 *)&v58[(_QWORD)v57];
            v60 = *v57 - v59;
            if ( v60 )
              break;
            ++v57;
          }
          while ( v59 );
          if ( v60 )
          {
LABEL_102:
            if ( !TYPE_SQLINT )
              goto LABEL_109;
            v61 = &Class;
            if ( *(_QWORD *)&v43[56 * v44 + 8] )
              v61 = *(const WCHAR **)&v43[56 * v44 + 8];
            v62 = (char *)((char *)TYPE_SQLINT - (char *)v61);
            do
            {
              v63 = *(unsigned __int16 *)&v62[(_QWORD)v61];
              v64 = *v61 - v63;
              if ( v64 )
                break;
              ++v61;
            }
            while ( v63 );
            if ( v64 )
            {
LABEL_109:
              if ( !TYPE_SQLBIGINT )
                goto LABEL_116;
              v65 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v65 = *(const WCHAR **)&v43[56 * v44 + 8];
              v66 = (char *)((char *)TYPE_SQLBIGINT - (char *)v65);
              do
              {
                v67 = *(unsigned __int16 *)&v66[(_QWORD)v65];
                v68 = *v65 - v67;
                if ( v68 )
                  break;
                ++v65;
              }
              while ( v67 );
              if ( v68 )
              {
LABEL_116:
                if ( !TYPE_SQLFLT4 )
                  goto LABEL_123;
                v69 = &Class;
                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                  v69 = *(const WCHAR **)&v43[56 * v44 + 8];
                v70 = (char *)((char *)TYPE_SQLFLT4 - (char *)v69);
                do
                {
                  v71 = *(unsigned __int16 *)&v70[(_QWORD)v69];
                  v72 = *v69 - v71;
                  if ( v72 )
                    break;
                  ++v69;
                }
                while ( v71 );
                if ( v72 )
                {
LABEL_123:
                  if ( !TYPE_SQLFLT8 )
                    goto LABEL_130;
                  v73 = &Class;
                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                    v73 = *(const WCHAR **)&v43[56 * v44 + 8];
                  v74 = (char *)((char *)TYPE_SQLFLT8 - (char *)v73);
                  do
                  {
                    v75 = *(unsigned __int16 *)&v74[(_QWORD)v73];
                    v76 = *v73 - v75;
                    if ( v76 )
                      break;
                    ++v73;
                  }
                  while ( v75 );
                  if ( v76 )
                  {
LABEL_130:
                    if ( !TYPE_SQLDATETIME )
                      goto LABEL_137;
                    v77 = &Class;
                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                      v77 = *(const WCHAR **)&v43[56 * v44 + 8];
                    v78 = (char *)((char *)TYPE_SQLDATETIME - (char *)v77);
                    do
                    {
                      v79 = *(unsigned __int16 *)&v78[(_QWORD)v77];
                      v80 = *v77 - v79;
                      if ( v80 )
                        break;
                      ++v77;
                    }
                    while ( v79 );
                    if ( v80 )
                    {
LABEL_137:
                      if ( !TYPE_SQLDATETIM4 )
                        goto LABEL_144;
                      v81 = &Class;
                      if ( *(_QWORD *)&v43[56 * v44 + 8] )
                        v81 = *(const WCHAR **)&v43[56 * v44 + 8];
                      v82 = (char *)((char *)TYPE_SQLDATETIM4 - (char *)v81);
                      do
                      {
                        v83 = *(unsigned __int16 *)&v82[(_QWORD)v81];
                        v84 = *v81 - v83;
                        if ( v84 )
                          break;
                        ++v81;
                      }
                      while ( v83 );
                      if ( v84 )
                      {
LABEL_144:
                        if ( !TYPE_SQLDATETIM8 )
                          goto LABEL_151;
                        v85 = &Class;
                        if ( *(_QWORD *)&v43[56 * v44 + 8] )
                          v85 = *(const WCHAR **)&v43[56 * v44 + 8];
                        v86 = (char *)((char *)TYPE_SQLDATETIM8 - (char *)v85);
                        do
                        {
                          v87 = *(unsigned __int16 *)&v86[(_QWORD)v85];
                          v88 = *v85 - v87;
                          if ( v88 )
                            break;
                          ++v85;
                        }
                        while ( v87 );
                        if ( v88 )
                        {
LABEL_151:
                          if ( !TYPE_SQLDATE )
                            goto LABEL_158;
                          v89 = &Class;
                          if ( *(_QWORD *)&v43[56 * v44 + 8] )
                            v89 = *(const WCHAR **)&v43[56 * v44 + 8];
                          v90 = (char *)((char *)TYPE_SQLDATE - (char *)v89);
                          do
                          {
                            v91 = *(unsigned __int16 *)&v90[(_QWORD)v89];
                            v92 = *v89 - v91;
                            if ( v92 )
                              break;
                            ++v89;
                          }
                          while ( v91 );
                          if ( v92 )
                          {
LABEL_158:
                            if ( !TYPE_SQLTIME )
                              goto LABEL_165;
                            v93 = &Class;
                            if ( *(_QWORD *)&v43[56 * v44 + 8] )
                              v93 = *(const WCHAR **)&v43[56 * v44 + 8];
                            v94 = (char *)((char *)TYPE_SQLTIME - (char *)v93);
                            do
                            {
                              v95 = *(unsigned __int16 *)&v94[(_QWORD)v93];
                              v96 = *v93 - v95;
                              if ( v96 )
                                break;
                              ++v93;
                            }
                            while ( v95 );
                            if ( v96 )
                            {
LABEL_165:
                              if ( !TYPE_SQLDATETIME2 )
                                goto LABEL_172;
                              v97 = &Class;
                              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                v97 = *(const WCHAR **)&v43[56 * v44 + 8];
                              v98 = (char *)((char *)TYPE_SQLDATETIME2 - (char *)v97);
                              do
                              {
                                v99 = *(unsigned __int16 *)&v98[(_QWORD)v97];
                                v100 = *v97 - v99;
                                if ( v100 )
                                  break;
                                ++v97;
                              }
                              while ( v99 );
                              if ( v100 )
                              {
LABEL_172:
                                if ( !TYPE_SQLDATETIMEOFFSET )
                                  goto LABEL_179;
                                v101 = &Class;
                                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                  v101 = *(const WCHAR **)&v43[56 * v44 + 8];
                                v102 = (char *)((char *)TYPE_SQLDATETIMEOFFSET - (char *)v101);
                                do
                                {
                                  v103 = *(unsigned __int16 *)&v102[(_QWORD)v101];
                                  v104 = *v101 - v103;
                                  if ( v104 )
                                    break;
                                  ++v101;
                                }
                                while ( v103 );
                                if ( v104 )
                                {
LABEL_179:
                                  if ( !TYPE_SQLMONEY )
                                    goto LABEL_186;
                                  v105 = &Class;
                                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                    v105 = *(const WCHAR **)&v43[56 * v44 + 8];
                                  v106 = (char *)((char *)TYPE_SQLMONEY - (char *)v105);
                                  do
                                  {
                                    v107 = *(unsigned __int16 *)&v106[(_QWORD)v105];
                                    v108 = *v105 - v107;
                                    if ( v108 )
                                      break;
                                    ++v105;
                                  }
                                  while ( v107 );
                                  if ( v108 )
                                  {
LABEL_186:
                                    if ( !TYPE_SQLMONEY4 )
                                      goto LABEL_193;
                                    v109 = &Class;
                                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                      v109 = *(const WCHAR **)&v43[56 * v44 + 8];
                                    v110 = (char *)((char *)TYPE_SQLMONEY4 - (char *)v109);
                                    do
                                    {
                                      v111 = *(unsigned __int16 *)&v110[(_QWORD)v109];
                                      v112 = *v109 - v111;
                                      if ( v112 )
                                        break;
                                      ++v109;
                                    }
                                    while ( v111 );
                                    if ( v112 )
                                    {
LABEL_193:
                                      if ( !TYPE_SQLVARIANT )
                                        goto LABEL_200;
                                      v113 = &Class;
                                      if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                        v113 = *(const WCHAR **)&v43[56 * v44 + 8];
                                      v114 = (char *)((char *)TYPE_SQLVARIANT - (char *)v113);
                                      do
                                      {
                                        v115 = *(unsigned __int16 *)&v114[(_QWORD)v113];
                                        v116 = *v113 - v115;
                                        if ( v116 )
                                          break;
                                        ++v113;
                                      }
                                      while ( v115 );
                                      if ( v116 )
                                      {
LABEL_200:
                                        if ( !TYPE_SQLUNIQUEID )
                                          goto LABEL_207;
                                        v117 = &Class;
                                        if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                          v117 = *(const WCHAR **)&v43[56 * v44 + 8];
                                        v118 = (char *)((char *)TYPE_SQLUNIQUEID - (char *)v117);
                                        do
                                        {
                                          v119 = *(unsigned __int16 *)&v118[(_QWORD)v117];
                                          v120 = *v117 - v119;
                                          if ( v120 )
                                            break;
                                          ++v117;
                                        }
                                        while ( v119 );
                                        if ( v120 )
                                        {
LABEL_207:
                                          if ( !TYPE_SQLDECIMAL )
                                            goto LABEL_214;
                                          v121 = &Class;
                                          if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                            v121 = *(const WCHAR **)&v43[56 * v44 + 8];
                                          v122 = (char *)((char *)TYPE_SQLDECIMAL - (char *)v121);
                                          do
                                          {
                                            v123 = *(unsigned __int16 *)&v122[(_QWORD)v121];
                                            v124 = *v121 - v123;
                                            if ( v124 )
                                              break;
                                            ++v121;
                                          }
                                          while ( v123 );
                                          if ( v124 )
                                          {
LABEL_214:
                                            if ( !TYPE_SQLNUMERIC )
                                              goto LABEL_221;
                                            v125 = &Class;
                                            if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                              v125 = *(const WCHAR **)&v43[56 * v44 + 8];
                                            v126 = (char *)((char *)TYPE_SQLNUMERIC - (char *)v125);
                                            do
                                            {
                                              v127 = *(unsigned __int16 *)&v126[(_QWORD)v125];
                                              v128 = *v125 - v127;
                                              if ( v128 )
                                                break;
                                              ++v125;
                                            }
                                            while ( v127 );
                                            if ( v128 )
                                            {
LABEL_221:
                                              if ( !TYPE_SQLIMAGE )
                                                goto LABEL_228;
                                              v129 = &Class;
                                              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                v129 = *(const WCHAR **)&v43[56 * v44 + 8];
                                              v130 = (char *)((char *)TYPE_SQLIMAGE - (char *)v129);
                                              do
                                              {
                                                v131 = *(unsigned __int16 *)&v130[(_QWORD)v129];
                                                v132 = *v129 - v131;
                                                if ( v132 )
                                                  break;
                                                ++v129;
                                              }
                                              while ( v131 );
                                              if ( v132 )
                                              {
LABEL_228:
                                                if ( !TYPE_SQLTEXT )
                                                  goto LABEL_235;
                                                v133 = &Class;
                                                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                  v133 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                v134 = (char *)((char *)TYPE_SQLTEXT - (char *)v133);
                                                do
                                                {
                                                  v135 = *(unsigned __int16 *)&v134[(_QWORD)v133];
                                                  v136 = *v133 - v135;
                                                  if ( v136 )
                                                    break;
                                                  ++v133;
                                                }
                                                while ( v135 );
                                                if ( v136 )
                                                {
LABEL_235:
                                                  if ( !TYPE_SQLNTEXT )
                                                    goto LABEL_242;
                                                  v137 = &Class;
                                                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                    v137 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                  v138 = (char *)((char *)TYPE_SQLNTEXT - (char *)v137);
                                                  do
                                                  {
                                                    v139 = *(unsigned __int16 *)&v138[(_QWORD)v137];
                                                    v140 = *v137 - v139;
                                                    if ( v140 )
                                                      break;
                                                    ++v137;
                                                  }
                                                  while ( v139 );
                                                  if ( v140 )
                                                  {
LABEL_242:
                                                    if ( !TYPE_SQLBINARY )
                                                      goto LABEL_249;
                                                    v141 = &Class;
                                                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                      v141 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                    v142 = (char *)((char *)TYPE_SQLBINARY - (char *)v141);
                                                    do
                                                    {
                                                      v143 = *(unsigned __int16 *)&v142[(_QWORD)v141];
                                                      v144 = *v141 - v143;
                                                      if ( v144 )
                                                        break;
                                                      ++v141;
                                                    }
                                                    while ( v143 );
                                                    if ( v144 )
                                                    {
LABEL_249:
                                                      if ( !TYPE_SQLVARYBIN )
                                                        goto LABEL_256;
                                                      v145 = &Class;
                                                      if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                        v145 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                      v146 = (char *)((char *)TYPE_SQLVARYBIN - (char *)v145);
                                                      do
                                                      {
                                                        v147 = *(unsigned __int16 *)&v146[(_QWORD)v145];
                                                        v148 = *v145 - v147;
                                                        if ( v148 )
                                                          break;
                                                        ++v145;
                                                      }
                                                      while ( v147 );
                                                      if ( v148 )
                                                      {
LABEL_256:
                                                        if ( !TYPE_SQLCHAR )
                                                          goto LABEL_263;
                                                        v149 = &Class;
                                                        if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                          v149 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                        v150 = (char *)((char *)TYPE_SQLCHAR - (char *)v149);
                                                        do
                                                        {
                                                          v151 = *(unsigned __int16 *)&v150[(_QWORD)v149];
                                                          v152 = *v149 - v151;
                                                          if ( v152 )
                                                            break;
                                                          ++v149;
                                                        }
                                                        while ( v151 );
                                                        if ( v152 )
                                                        {
LABEL_263:
                                                          if ( !TYPE_SQLVARYCHAR )
                                                            goto LABEL_270;
                                                          v153 = &Class;
                                                          if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                            v153 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                          v154 = (char *)((char *)TYPE_SQLVARYCHAR - (char *)v153);
                                                          do
                                                          {
                                                            v155 = *(unsigned __int16 *)&v154[(_QWORD)v153];
                                                            v156 = *v153 - v155;
                                                            if ( v156 )
                                                              break;
                                                            ++v153;
                                                          }
                                                          while ( v155 );
                                                          if ( v156 )
                                                          {
LABEL_270:
                                                            if ( !TYPE_SQLNCHAR )
                                                              goto LABEL_277;
                                                            v157 = &Class;
                                                            if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                              v157 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                            v158 = (char *)((char *)TYPE_SQLNCHAR - (char *)v157);
                                                            do
                                                            {
                                                              v159 = *(unsigned __int16 *)&v158[(_QWORD)v157];
                                                              v160 = *v157 - v159;
                                                              if ( v160 )
                                                                break;
                                                              ++v157;
                                                            }
                                                            while ( v159 );
                                                            if ( v160 )
                                                            {
LABEL_277:
                                                              if ( !TYPE_SQLNVARCHAR )
                                                                goto LABEL_284;
                                                              v161 = &Class;
                                                              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                v161 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                              v162 = (char *)((char *)TYPE_SQLNVARCHAR - (char *)v161);
                                                              do
                                                              {
                                                                v163 = *(unsigned __int16 *)&v162[(_QWORD)v161];
                                                                v164 = *v161 - v163;
                                                                if ( v164 )
                                                                  break;
                                                                ++v161;
                                                              }
                                                              while ( v163 );
                                                              if ( v164 )
                                                              {
LABEL_284:
                                                                if ( !TYPE_SQLUDT )
                                                                  goto LABEL_291;
                                                                v165 = &Class;
                                                                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                  v165 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                v166 = (char *)((char *)TYPE_SQLUDT - (char *)v165);
                                                                do
                                                                {
                                                                  v167 = *(unsigned __int16 *)&v166[(_QWORD)v165];
                                                                  v168 = *v165 - v167;
                                                                  if ( v168 )
                                                                    break;
                                                                  ++v165;
                                                                }
                                                                while ( v167 );
                                                                if ( v168 )
                                                                {
LABEL_291:
                                                                  if ( !TYPE_SYBBIT )
                                                                    goto LABEL_298;
                                                                  v169 = &Class;
                                                                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                    v169 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                  v170 = (char *)((char *)TYPE_SYBBIT - (char *)v169);
                                                                  do
                                                                  {
                                                                    v171 = *(unsigned __int16 *)&v170[(_QWORD)v169];
                                                                    v172 = *v169 - v171;
                                                                    if ( v172 )
                                                                      break;
                                                                    ++v169;
                                                                  }
                                                                  while ( v171 );
                                                                  if ( v172 )
                                                                  {
LABEL_298:
                                                                    if ( !TYPE_SYBTINYINT )
                                                                      goto LABEL_305;
                                                                    v173 = &Class;
                                                                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                      v173 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                    v174 = (char *)((char *)TYPE_SYBTINYINT
                                                                                  - (char *)v173);
                                                                    do
                                                                    {
                                                                      v175 = *(unsigned __int16 *)&v174[(_QWORD)v173];
                                                                      v176 = *v173 - v175;
                                                                      if ( v176 )
                                                                        break;
                                                                      ++v173;
                                                                    }
                                                                    while ( v175 );
                                                                    if ( v176 )
                                                                    {
LABEL_305:
                                                                      if ( !TYPE_SYBSMALLINT )
                                                                        goto LABEL_312;
                                                                      v177 = &Class;
                                                                      if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                        v177 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                      v178 = (char *)((char *)TYPE_SYBSMALLINT
                                                                                    - (char *)v177);
                                                                      do
                                                                      {
                                                                        v179 = *(unsigned __int16 *)&v178[(_QWORD)v177];
                                                                        v180 = *v177 - v179;
                                                                        if ( v180 )
                                                                          break;
                                                                        ++v177;
                                                                      }
                                                                      while ( v179 );
                                                                      if ( v180 )
                                                                      {
LABEL_312:
                                                                        if ( !TYPE_SYBINT )
                                                                          goto LABEL_319;
                                                                        v181 = &Class;
                                                                        if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                          v181 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                        v182 = (char *)((char *)TYPE_SYBINT
                                                                                      - (char *)v181);
                                                                        do
                                                                        {
                                                                          v183 = *(unsigned __int16 *)&v182[(_QWORD)v181];
                                                                          v184 = *v181 - v183;
                                                                          if ( v184 )
                                                                            break;
                                                                          ++v181;
                                                                        }
                                                                        while ( v183 );
                                                                        if ( v184 )
                                                                        {
LABEL_319:
                                                                          if ( !TYPE_SYBBIGINT )
                                                                            goto LABEL_326;
                                                                          v185 = &Class;
                                                                          if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                            v185 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                          v186 = (char *)((char *)TYPE_SYBBIGINT
                                                                                        - (char *)v185);
                                                                          do
                                                                          {
                                                                            v187 = *(unsigned __int16 *)&v186[(_QWORD)v185];
                                                                            v188 = *v185 - v187;
                                                                            if ( v188 )
                                                                              break;
                                                                            ++v185;
                                                                          }
                                                                          while ( v187 );
                                                                          if ( v188 )
                                                                          {
LABEL_326:
                                                                            if ( !TYPE_SYBFLT4 )
                                                                              goto LABEL_333;
                                                                            v189 = &Class;
                                                                            if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                              v189 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                            v190 = (char *)((char *)TYPE_SYBFLT4
                                                                                          - (char *)v189);
                                                                            do
                                                                            {
                                                                              v191 = *(unsigned __int16 *)&v190[(_QWORD)v189];
                                                                              v192 = *v189 - v191;
                                                                              if ( v192 )
                                                                                break;
                                                                              ++v189;
                                                                            }
                                                                            while ( v191 );
                                                                            if ( v192 )
                                                                            {
LABEL_333:
                                                                              if ( !TYPE_SYBFLT8 )
                                                                                goto LABEL_340;
                                                                              v193 = &Class;
                                                                              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                v193 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                              v194 = (char *)((char *)TYPE_SYBFLT8
                                                                                            - (char *)v193);
                                                                              do
                                                                              {
                                                                                v195 = *(unsigned __int16 *)&v194[(_QWORD)v193];
                                                                                v196 = *v193 - v195;
                                                                                if ( v196 )
                                                                                  break;
                                                                                ++v193;
                                                                              }
                                                                              while ( v195 );
                                                                              if ( v196 )
                                                                              {
LABEL_340:
                                                                                if ( !TYPE_SYBDATETIME )
                                                                                  goto LABEL_347;
                                                                                v197 = &Class;
                                                                                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                  v197 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                v198 = (char *)((char *)TYPE_SYBDATETIME
                                                                                              - (char *)v197);
                                                                                do
                                                                                {
                                                                                  v199 = *(unsigned __int16 *)&v198[(_QWORD)v197];
                                                                                  v200 = *v197 - v199;
                                                                                  if ( v200 )
                                                                                    break;
                                                                                  ++v197;
                                                                                }
                                                                                while ( v199 );
                                                                                if ( v200 )
                                                                                {
LABEL_347:
                                                                                  if ( !TYPE_SYBDATETIM4 )
                                                                                    goto LABEL_354;
                                                                                  v201 = &Class;
                                                                                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                    v201 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                  v202 = (char *)((char *)TYPE_SYBDATETIM4
                                                                                                - (char *)v201);
                                                                                  do
                                                                                  {
                                                                                    v203 = *(unsigned __int16 *)&v202[(_QWORD)v201];
                                                                                    v204 = *v201 - v203;
                                                                                    if ( v204 )
                                                                                      break;
                                                                                    ++v201;
                                                                                  }
                                                                                  while ( v203 );
                                                                                  if ( v204 )
                                                                                  {
LABEL_354:
                                                                                    if ( !TYPE_SYBDATETIM8 )
                                                                                      goto LABEL_361;
                                                                                    v205 = &Class;
                                                                                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                      v205 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                    v206 = (char *)((char *)TYPE_SYBDATETIM8
                                                                                                  - (char *)v205);
                                                                                    do
                                                                                    {
                                                                                      v207 = *(unsigned __int16 *)&v206[(_QWORD)v205];
                                                                                      v208 = *v205 - v207;
                                                                                      if ( v208 )
                                                                                        break;
                                                                                      ++v205;
                                                                                    }
                                                                                    while ( v207 );
                                                                                    if ( v208 )
                                                                                    {
LABEL_361:
                                                                                      if ( !TYPE_SYBMONEY )
                                                                                        goto LABEL_368;
                                                                                      v209 = &Class;
                                                                                      if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                        v209 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                      v210 = (char *)((char *)TYPE_SYBMONEY - (char *)v209);
                                                                                      do
                                                                                      {
                                                                                        v211 = *(unsigned __int16 *)&v210[(_QWORD)v209];
                                                                                        v212 = *v209 - v211;
                                                                                        if ( v212 )
                                                                                          break;
                                                                                        ++v209;
                                                                                      }
                                                                                      while ( v211 );
                                                                                      if ( v212 )
                                                                                      {
LABEL_368:
                                                                                        if ( !TYPE_SYBMONEY4 )
                                                                                          goto LABEL_375;
                                                                                        v213 = &Class;
                                                                                        if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                          v213 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                        v214 = (char *)((char *)TYPE_SYBMONEY4 - (char *)v213);
                                                                                        do
                                                                                        {
                                                                                          v215 = *(unsigned __int16 *)&v214[(_QWORD)v213];
                                                                                          v216 = *v213 - v215;
                                                                                          if ( v216 )
                                                                                            break;
                                                                                          ++v213;
                                                                                        }
                                                                                        while ( v215 );
                                                                                        if ( v216 )
                                                                                        {
LABEL_375:
                                                                                          if ( !TYPE_SYBIMAGE )
                                                                                            goto LABEL_382;
                                                                                          v217 = &Class;
                                                                                          if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                            v217 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                          v218 = (char *)((char *)TYPE_SYBIMAGE - (char *)v217);
                                                                                          do
                                                                                          {
                                                                                            v219 = *(unsigned __int16 *)&v218[(_QWORD)v217];
                                                                                            v220 = *v217 - v219;
                                                                                            if ( v220 )
                                                                                              break;
                                                                                            ++v217;
                                                                                          }
                                                                                          while ( v219 );
                                                                                          if ( v220 )
                                                                                          {
LABEL_382:
                                                                                            if ( !TYPE_SYBTEXT )
                                                                                              goto LABEL_389;
                                                                                            v221 = &Class;
                                                                                            if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                              v221 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                            v222 = (char *)((char *)TYPE_SYBTEXT - (char *)v221);
                                                                                            do
                                                                                            {
                                                                                              v223 = *(unsigned __int16 *)&v222[(_QWORD)v221];
                                                                                              v224 = *v221 - v223;
                                                                                              if ( v224 )
                                                                                                break;
                                                                                              ++v221;
                                                                                            }
                                                                                            while ( v223 );
                                                                                            if ( v224 )
                                                                                            {
LABEL_389:
                                                                                              if ( !TYPE_SYBBINARY )
                                                                                                goto LABEL_396;
                                                                                              v225 = &Class;
                                                                                              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                                v225 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                              v226 = (char *)((char *)TYPE_SYBBINARY - (char *)v225);
                                                                                              do
                                                                                              {
                                                                                                v227 = *(unsigned __int16 *)&v226[(_QWORD)v225];
                                                                                                v228 = *v225 - v227;
                                                                                                if ( v228 )
                                                                                                  break;
                                                                                                ++v225;
                                                                                              }
                                                                                              while ( v227 );
                                                                                              if ( v228 )
                                                                                              {
LABEL_396:
                                                                                                if ( !TYPE_SYBVARYBIN )
                                                                                                  goto LABEL_403;
                                                                                                v229 = &Class;
                                                                                                if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                                  v229 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                                v230 = (char *)((char *)TYPE_SYBVARYBIN - (char *)v229);
                                                                                                do
                                                                                                {
                                                                                                  v231 = *(unsigned __int16 *)&v230[(_QWORD)v229];
                                                                                                  v232 = *v229 - v231;
                                                                                                  if ( v232 )
                                                                                                    break;
                                                                                                  ++v229;
                                                                                                }
                                                                                                while ( v231 );
                                                                                                if ( v232 )
                                                                                                {
LABEL_403:
                                                                                                  if ( !TYPE_SYBCHAR )
                                                                                                    goto LABEL_410;
                                                                                                  v233 = &Class;
                                                                                                  if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                                    v233 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                                  v234 = (char *)((char *)TYPE_SYBCHAR - (char *)v233);
                                                                                                  do
                                                                                                  {
                                                                                                    v235 = *(unsigned __int16 *)&v234[(_QWORD)v233];
                                                                                                    v236 = *v233 - v235;
                                                                                                    if ( v236 )
                                                                                                      break;
                                                                                                    ++v233;
                                                                                                  }
                                                                                                  while ( v235 );
                                                                                                  if ( v236 )
                                                                                                  {
LABEL_410:
                                                                                                    if ( !TYPE_SYBVARYCHAR )
                                                                                                      goto LABEL_1233;
                                                                                                    v237 = &Class;
                                                                                                    if ( *(_QWORD *)&v43[56 * v44 + 8] )
                                                                                                      v237 = *(const WCHAR **)&v43[56 * v44 + 8];
                                                                                                    v238 = (char *)((char *)TYPE_SYBVARYCHAR - (char *)v237);
                                                                                                    do
                                                                                                    {
                                                                                                      v239 = *(unsigned __int16 *)&v238[(_QWORD)v237];
                                                                                                      v240 = *v237 - v239;
                                                                                                      if ( v240 )
                                                                                                        break;
                                                                                                      ++v237;
                                                                                                    }
                                                                                                    while ( v239 );
                                                                                                    if ( v240 )
                                                                                                    {
LABEL_1233:
                                                                                                      CBcpFmtException::CBcpFmtException(&NumOfElements, 5, v44 + 1);
                                                                                                      throw (CBcpFmtException *)&NumOfElements;
                                                                                                    }
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v725 = 0;
      CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)&v727);
      v241 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)&v727, String, 0x14u);
      if ( v241 )
      {
        if ( v241 == -2147467259 )
        {
          CBcpFmtException::CBcpFmtException(&NumOfElements, 4, v44 + 1);
          throw (CBcpFmtException *)&NumOfElements;
        }
LABEL_1232:
        CBcpFmtException::CBcpFmtException(&NumOfElements, 6, v44 + 1);
        throw (CBcpFmtException *)&NumOfElements;
      }
      v242 = _strtoui64(String, &v725, 10);
      v243 = v242;
      if ( v242 > 0x7FFFFFFF || v725 && *v725 && !isspace((unsigned __int8)*v725) )
        goto LABEL_1232;
      *(_DWORD *)&v43[56 * v44 + 16] = v243;
      v244 = *(_DWORD *)&v43[56 * v44 + 16];
      if ( v244 > 8 )
        goto LABEL_1232;
      v245 = 279;
      if ( !_bittest(&v245, v244) )
        goto LABEL_1232;
      v725 = 0;
      CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)&v727);
      v246 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)&v727, String, 0x14u);
      if ( v246 )
      {
        if ( v246 == -2147467259 )
        {
          CBcpFmtException::CBcpFmtException(&NumOfElements, 4, v44 + 1);
          throw (CBcpFmtException *)&NumOfElements;
        }
LABEL_1231:
        CBcpFmtException::CBcpFmtException(&NumOfElements, 7, v44 + 1);
        throw (CBcpFmtException *)&NumOfElements;
      }
      v247 = _strtoui64(String, &v725, 10);
      v248 = v247;
      if ( v247 > 0x7FFFFFFF || v725 && *v725 && !isspace((unsigned __int8)*v725) )
        goto LABEL_1231;
      *(_DWORD *)&v43[56 * v44 + 20] = v248;
      GetString((struct CWStr *)&v43[56 * v44 + 24], v44, (struct CBulkFmtStreamReader *)&v727);
      v725 = 0;
      CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)&v727);
      v249 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)&v727, String, 0x14u);
      if ( v249 )
      {
        if ( v249 == -2147467259 )
        {
          CBcpFmtException::CBcpFmtException(&NumOfElements, 4, v44 + 1);
          throw (CBcpFmtException *)&NumOfElements;
        }
LABEL_1230:
        CBcpFmtException::CBcpFmtException(&NumOfElements, 9, v44 + 1);
        throw (CBcpFmtException *)&NumOfElements;
      }
      v250 = _strtoui64(String, &v725, 10);
      if ( v250 > 0x7FFFFFFF || v725 && *v725 && !isspace((unsigned __int8)*v725) )
        goto LABEL_1230;
      *(_DWORD *)&v43[56 * v44 + 32] = v250;
      GetString((struct CWStr *)&v43[56 * v44 + 40], v44, (struct CBulkFmtStreamReader *)&v727);
      if ( FORMAT_VERSION_110 )
      {
        v251 = &Class;
        if ( *(_QWORD *)(a1 + 144) )
          v251 = *(const WCHAR **)(a1 + 144);
        v252 = (char *)((char *)FORMAT_VERSION_110 - (char *)v251);
        do
        {
          v253 = *(unsigned __int16 *)&v252[(_QWORD)v251];
          v254 = *v251 - v253;
          if ( v254 )
            break;
          ++v251;
        }
        while ( v253 );
        if ( !v254 )
          goto LABEL_456;
      }
      if ( FORMAT_VERSION_100 )
      {
        v255 = &Class;
        if ( *(_QWORD *)(a1 + 144) )
          v255 = *(const WCHAR **)(a1 + 144);
        v256 = (char *)((char *)FORMAT_VERSION_100 - (char *)v255);
        do
        {
          v257 = *(unsigned __int16 *)&v256[(_QWORD)v255];
          v258 = *v255 - v257;
          if ( v258 )
            break;
          ++v255;
        }
        while ( v257 );
        if ( !v258 )
          goto LABEL_456;
      }
      if ( FORMAT_VERSION_90 )
      {
        v259 = &Class;
        if ( *(_QWORD *)(a1 + 144) )
          v259 = *(const WCHAR **)(a1 + 144);
        v260 = (char *)((char *)FORMAT_VERSION_90 - (char *)v259);
        do
        {
          v261 = *(unsigned __int16 *)&v260[(_QWORD)v259];
          v262 = *v259 - v261;
          if ( v262 )
            break;
          ++v259;
        }
        while ( v261 );
        if ( !v262 )
          goto LABEL_456;
      }
      if ( FORMAT_VERSION_80 )
      {
        v263 = &Class;
        if ( *(_QWORD *)(a1 + 144) )
          v263 = *(const WCHAR **)(a1 + 144);
        v264 = (char *)((char *)FORMAT_VERSION_80 - (char *)v263);
        do
        {
          v265 = *(unsigned __int16 *)&v264[(_QWORD)v263];
          v266 = *v263 - v265;
          if ( v266 )
            break;
          ++v263;
        }
        while ( v265 );
        if ( !v266 )
LABEL_456:
          GetString((struct CWStr *)&v43[56 * v44 + 48], v44, (struct CBulkFmtStreamReader *)&v727);
      }
      if ( !*(_DWORD *)&v43[56 * v44 + 32] && !*(_DWORD *)&v43[56 * v44 + 20] )
      {
        if ( !EMPTY_STRING )
          goto LABEL_468;
        v267 = &Class;
        if ( *(_QWORD *)&v43[56 * v44 + 24] )
          v267 = *(const WCHAR **)&v43[56 * v44 + 24];
        v268 = (char *)((char *)EMPTY_STRING - (char *)v267);
        do
        {
          v269 = *(unsigned __int16 *)&v268[(_QWORD)v267];
          v270 = *v267 - v269;
          if ( v270 )
            break;
          ++v267;
        }
        while ( v269 );
        if ( v270 )
        {
LABEL_468:
          if ( *(_DWORD *)&v43[56 * v44 + 16] != 1 )
          {
LABEL_469:
            if ( TYPE_SQLIMAGE )
            {
              v271 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v271 = *(const WCHAR **)&v43[56 * v44 + 8];
              v272 = (char *)((char *)TYPE_SQLIMAGE - (char *)v271);
              do
              {
                v273 = *(unsigned __int16 *)&v272[(_QWORD)v271];
                v274 = *v271 - v273;
                if ( v274 )
                  break;
                ++v271;
              }
              while ( v273 );
              if ( !v274 )
                goto LABEL_539;
            }
            if ( TYPE_SQLTEXT )
            {
              v275 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v275 = *(const WCHAR **)&v43[56 * v44 + 8];
              v276 = (char *)((char *)TYPE_SQLTEXT - (char *)v275);
              do
              {
                v277 = *(unsigned __int16 *)&v276[(_QWORD)v275];
                v278 = *v275 - v277;
                if ( v278 )
                  break;
                ++v275;
              }
              while ( v277 );
              if ( !v278 )
                goto LABEL_539;
            }
            if ( TYPE_SQLNTEXT )
            {
              v279 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v279 = *(const WCHAR **)&v43[56 * v44 + 8];
              v280 = (char *)((char *)TYPE_SQLNTEXT - (char *)v279);
              do
              {
                v281 = *(unsigned __int16 *)&v280[(_QWORD)v279];
                v282 = *v279 - v281;
                if ( v282 )
                  break;
                ++v279;
              }
              while ( v281 );
              if ( !v282 )
                goto LABEL_539;
            }
            if ( TYPE_SQLBINARY )
            {
              v283 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v283 = *(const WCHAR **)&v43[56 * v44 + 8];
              v284 = (char *)((char *)TYPE_SQLBINARY - (char *)v283);
              do
              {
                v285 = *(unsigned __int16 *)&v284[(_QWORD)v283];
                v286 = *v283 - v285;
                if ( v286 )
                  break;
                ++v283;
              }
              while ( v285 );
              if ( !v286 )
                goto LABEL_539;
            }
            if ( TYPE_SQLVARYBIN )
            {
              v287 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v287 = *(const WCHAR **)&v43[56 * v44 + 8];
              v288 = (char *)((char *)TYPE_SQLVARYBIN - (char *)v287);
              do
              {
                v289 = *(unsigned __int16 *)&v288[(_QWORD)v287];
                v290 = *v287 - v289;
                if ( v290 )
                  break;
                ++v287;
              }
              while ( v289 );
              if ( !v290 )
                goto LABEL_539;
            }
            if ( TYPE_SQLCHAR )
            {
              v291 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v291 = *(const WCHAR **)&v43[56 * v44 + 8];
              v292 = (char *)((char *)TYPE_SQLCHAR - (char *)v291);
              do
              {
                v293 = *(unsigned __int16 *)&v292[(_QWORD)v291];
                v294 = *v291 - v293;
                if ( v294 )
                  break;
                ++v291;
              }
              while ( v293 );
              if ( !v294 )
                goto LABEL_539;
            }
            if ( TYPE_SQLVARYCHAR )
            {
              v295 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v295 = *(const WCHAR **)&v43[56 * v44 + 8];
              v296 = (char *)((char *)TYPE_SQLVARYCHAR - (char *)v295);
              do
              {
                v297 = *(unsigned __int16 *)&v296[(_QWORD)v295];
                v298 = *v295 - v297;
                if ( v298 )
                  break;
                ++v295;
              }
              while ( v297 );
              if ( !v298 )
                goto LABEL_539;
            }
            if ( TYPE_SQLNCHAR )
            {
              v299 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v299 = *(const WCHAR **)&v43[56 * v44 + 8];
              v300 = (char *)((char *)TYPE_SQLNCHAR - (char *)v299);
              do
              {
                v301 = *(unsigned __int16 *)&v300[(_QWORD)v299];
                v302 = *v299 - v301;
                if ( v302 )
                  break;
                ++v299;
              }
              while ( v301 );
              if ( !v302 )
                goto LABEL_539;
            }
            if ( TYPE_SQLNVARCHAR )
            {
              v303 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v303 = *(const WCHAR **)&v43[56 * v44 + 8];
              v304 = (char *)((char *)TYPE_SQLNVARCHAR - (char *)v303);
              do
              {
                v305 = *(unsigned __int16 *)&v304[(_QWORD)v303];
                v306 = *v303 - v305;
                if ( v306 )
                  break;
                ++v303;
              }
              while ( v305 );
              if ( !v306 )
                goto LABEL_539;
            }
            if ( TYPE_SQLUDT )
            {
              v307 = &Class;
              if ( *(_QWORD *)&v43[56 * v44 + 8] )
                v307 = *(const WCHAR **)&v43[56 * v44 + 8];
              v308 = (char *)((char *)TYPE_SQLUDT - (char *)v307);
              do
              {
                v309 = *(unsigned __int16 *)&v308[(_QWORD)v307];
                v310 = *v307 - v309;
                if ( v310 )
                  break;
                ++v307;
              }
              while ( v309 );
              if ( !v310 )
LABEL_539:
                *(_DWORD *)&v43[56 * v44 + 20] = 0x7FFFFFFF;
            }
          }
        }
        else if ( *(_DWORD *)&v43[56 * v44 + 16] >= 2u )
        {
          goto LABEL_469;
        }
      }
      ++v44;
      v6 = 0;
    }
    while ( v44 < (unsigned int)v38 );
  }
  _mm_lfence();
  CFmtStream::operator<<(v8, 65279);
  CFmtStream::operator<<(v8, XML_SIGNATURE);
  v311 = CFmtStream::operator<<(v8, L"\r\n<");
  CFmtStream::operator<<(v311, ELEM_BCPFORMAT);
  v312 = CFmtStream::operator<<(v8, L" ");
  v313 = CFmtStream::operator<<(v312, XMLNS);
  CFmtStream::operator<<(v313, L"=\"");
  CWStr::CWStr((CWStr *)&v725, SCHEMA_URI_BULK);
  CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v725);
  operator delete(v725, 2u);
  CFmtStream::operator<<(v8, L"\"");
  v314 = CFmtStream::operator<<(v8, L" ");
  v315 = CFmtStream::operator<<(v314, XMLNS_XSI);
  CFmtStream::operator<<(v315, L"=\"");
  CWStr::CWStr((CWStr *)&v725, SCHEMA_URI_XSI);
  CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v725);
  operator delete(v725, 2u);
  CFmtStream::operator<<(v8, L"\"");
  CFmtStream::operator<<(v8, L">");
  v316 = CFmtStream::operator<<(v8, L"\r\n <");
  CFmtStream::operator<<(v316, ELEM_RECORD);
  CFmtStream::operator<<(v8, L">");
  v317 = 0;
  v318 = 1;
  v707 = 1;
  v319 = NumOfElements;
  if ( (_DWORD)NumOfElements )
  {
    _mm_lfence();
    while ( 1 )
    {
      v320 = 56 * v6;
      if ( !*(_DWORD *)&v43[56 * v6 + 16] && !*(_DWORD *)&v43[v320 + 20] && EMPTY_STRING )
      {
        v321 = &Class;
        if ( *(_QWORD *)&v43[v320 + 24] )
          v321 = *(const WCHAR **)&v43[v320 + 24];
        v322 = (char *)((char *)EMPTY_STRING - (char *)v321);
        do
        {
          v323 = *(unsigned __int16 *)&v322[(_QWORD)v321];
          v324 = *v321 - v323;
          if ( v324 )
            break;
          ++v321;
        }
        while ( v323 );
        if ( !v324 )
          goto LABEL_1042;
      }
      v325 = CFmtStream::operator<<(v8, L"\r\n  <");
      CFmtStream::operator<<(v325, ELEM_FIELD);
      v326 = CFmtStream::operator<<(v8, L" ");
      v327 = CFmtStream::operator<<(v326, ATTR_ID);
      v328 = CFmtStream::operator<<(v327, L"=\"");
      v329 = CFmtStream::operator<<(v328, *(unsigned int *)&v43[56 * v6]);
      CFmtStream::operator<<(v329, L"\"");
      if ( TYPE_SQLTEXT )
      {
        v330 = &Class;
        if ( *(_QWORD *)&v43[v320 + 8] )
          v330 = *(const WCHAR **)&v43[v320 + 8];
        v331 = (char *)((char *)TYPE_SQLTEXT - (char *)v330);
        do
        {
          v332 = *(unsigned __int16 *)&v331[(_QWORD)v330];
          v333 = *v330 - v332;
          if ( v333 )
            break;
          ++v330;
        }
        while ( v332 );
        if ( !v333 )
          goto LABEL_594;
      }
      if ( TYPE_SQLCHAR )
      {
        v334 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v334 = *(const WCHAR **)&v43[56 * v6 + 8];
        v335 = (char *)((char *)TYPE_SQLCHAR - (char *)v334);
        do
        {
          v336 = *(unsigned __int16 *)&v335[(_QWORD)v334];
          v337 = *v334 - v336;
          if ( v337 )
            break;
          ++v334;
        }
        while ( v336 );
        if ( !v337 )
          goto LABEL_594;
      }
      if ( TYPE_SQLVARYCHAR )
      {
        v338 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v338 = *(const WCHAR **)&v43[56 * v6 + 8];
        v339 = (char *)((char *)TYPE_SQLVARYCHAR - (char *)v338);
        do
        {
          v340 = *(unsigned __int16 *)&v339[(_QWORD)v338];
          v341 = *v338 - v340;
          if ( v341 )
            break;
          ++v338;
        }
        while ( v340 );
        if ( !v341 )
          goto LABEL_594;
      }
      if ( TYPE_SYBTEXT )
      {
        v342 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v342 = *(const WCHAR **)&v43[56 * v6 + 8];
        v343 = (char *)((char *)TYPE_SYBTEXT - (char *)v342);
        do
        {
          v344 = *(unsigned __int16 *)&v343[(_QWORD)v342];
          v345 = *v342 - v344;
          if ( v345 )
            break;
          ++v342;
        }
        while ( v344 );
        if ( !v345 )
          goto LABEL_594;
      }
      if ( TYPE_SYBCHAR )
      {
        v346 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v346 = *(const WCHAR **)&v43[56 * v6 + 8];
        v347 = (char *)((char *)TYPE_SYBCHAR - (char *)v346);
        do
        {
          v348 = *(unsigned __int16 *)&v347[(_QWORD)v346];
          v349 = *v346 - v348;
          if ( v349 )
            break;
          ++v346;
        }
        while ( v348 );
        if ( !v349 )
          goto LABEL_594;
      }
      if ( !TYPE_SYBVARYCHAR )
        goto LABEL_623;
      v350 = &Class;
      if ( *(_QWORD *)&v43[56 * v6 + 8] )
        v350 = *(const WCHAR **)&v43[56 * v6 + 8];
      v351 = (char *)((char *)TYPE_SYBVARYCHAR - (char *)v350);
      do
      {
        v352 = *(unsigned __int16 *)&v351[(_QWORD)v350];
        v353 = *v350 - v352;
        if ( v353 )
          break;
        ++v350;
      }
      while ( v352 );
      if ( v353 )
      {
LABEL_623:
        if ( TYPE_SQLNTEXT )
        {
          v355 = &Class;
          if ( *(_QWORD *)&v43[56 * v6 + 8] )
            v355 = *(const WCHAR **)&v43[56 * v6 + 8];
          v356 = (char *)((char *)TYPE_SQLNTEXT - (char *)v355);
          do
          {
            v357 = *(unsigned __int16 *)&v356[(_QWORD)v355];
            v358 = *v355 - v357;
            if ( v358 )
              break;
            ++v355;
          }
          while ( v357 );
          if ( !v358 )
            goto LABEL_624;
        }
        if ( TYPE_SQLNCHAR )
        {
          v359 = &Class;
          if ( *(_QWORD *)&v43[56 * v6 + 8] )
            v359 = *(const WCHAR **)&v43[56 * v6 + 8];
          v360 = (char *)((char *)TYPE_SQLNCHAR - (char *)v359);
          do
          {
            v361 = *(unsigned __int16 *)&v360[(_QWORD)v359];
            v362 = *v359 - v361;
            if ( v362 )
              break;
            ++v359;
          }
          while ( v361 );
          if ( !v362 )
            goto LABEL_624;
        }
        if ( !TYPE_SQLNVARCHAR )
          goto LABEL_625;
        v363 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v363 = *(const WCHAR **)&v43[56 * v6 + 8];
        v364 = (char *)((char *)TYPE_SQLNVARCHAR - (char *)v363);
        do
        {
          v365 = *(unsigned __int16 *)&v364[(_QWORD)v363];
          v366 = *v363 - v365;
          if ( v366 )
            break;
          ++v363;
        }
        while ( v365 );
        if ( v366 )
LABEL_625:
          v354 = 3;
        else
LABEL_624:
          v354 = 2;
      }
      else
      {
LABEL_594:
        v354 = 1;
      }
      if ( TYPE_SQLVARYCHAR )
      {
        v367 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v367 = *(const WCHAR **)&v43[56 * v6 + 8];
        v368 = (char *)((char *)TYPE_SQLVARYCHAR - (char *)v367);
        do
        {
          v369 = *(unsigned __int16 *)&v368[(_QWORD)v367];
          v370 = *v367 - v369;
          if ( v370 )
            break;
          ++v367;
        }
        while ( v369 );
        if ( !v370 )
          goto LABEL_1237;
      }
      if ( TYPE_SYBVARYCHAR )
      {
        v371 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v371 = *(const WCHAR **)&v43[56 * v6 + 8];
        v372 = (char *)((char *)TYPE_SYBVARYCHAR - (char *)v371);
        do
        {
          v373 = *(unsigned __int16 *)&v372[(_QWORD)v371];
          v374 = *v371 - v373;
          if ( v374 )
            break;
          ++v371;
        }
        while ( v373 );
        if ( !v374 )
          goto LABEL_1237;
      }
      if ( TYPE_SQLVARYBIN )
      {
        v375 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v375 = *(const WCHAR **)&v43[56 * v6 + 8];
        v376 = (char *)((char *)TYPE_SQLVARYBIN - (char *)v375);
        do
        {
          v377 = *(unsigned __int16 *)&v376[(_QWORD)v375];
          v378 = *v375 - v377;
          if ( v378 )
            break;
          ++v375;
        }
        while ( v377 );
        if ( !v378 )
          goto LABEL_1237;
      }
      if ( TYPE_SYBVARYBIN )
      {
        v379 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v379 = *(const WCHAR **)&v43[56 * v6 + 8];
        v380 = (char *)((char *)TYPE_SYBVARYBIN - (char *)v379);
        do
        {
          v381 = *(unsigned __int16 *)&v380[(_QWORD)v379];
          v382 = *v379 - v381;
          if ( v382 )
            break;
          ++v379;
        }
        while ( v381 );
        if ( !v382 )
        {
LABEL_1237:
          if ( !*(_DWORD *)&v43[56 * v6 + 16] )
            *(_DWORD *)&v43[56 * v6 + 16] = 2;
        }
      }
      if ( *(_DWORD *)&v43[56 * v6 + 16] )
      {
        if ( v354 != 1 )
        {
          if ( v354 != 2 )
          {
            v383 = CFmtStream::operator<<(v8, L" ");
            v384 = CFmtStream::operator<<(v383, XSI_TYPE);
            CFmtStream::operator<<(v384, L"=\"");
            CWStr::CWStr((CWStr *)&v725, TYPE_NativePrefix);
            v385 = (char *)&Class;
            v386 = v725;
            if ( v725 )
              v385 = v725;
            v387 = *(_WORD *)v385;
            if ( *(_WORD *)v385 )
            {
              while ( 1 )
              {
                if ( v387 == 34 )
                {
                  v389 = L"&quot;";
                  goto LABEL_673;
                }
                if ( v387 == 38 )
                {
                  v389 = L"&amp;";
                  goto LABEL_673;
                }
                if ( v387 == 39 )
                  break;
                if ( v387 == 60 )
                {
                  v389 = L"&lt;";
LABEL_673:
                  v388 = v8;
                  goto LABEL_674;
                }
                v388 = v8;
                if ( v387 == 62 )
                {
                  v389 = L"&gt;";
LABEL_674:
                  CFmtStream::operator<<(v388, v389);
                  goto LABEL_675;
                }
                CFmtStream::operator<<(v8, *(unsigned __int16 *)v385);
LABEL_675:
                v385 += 2;
                v387 = *(_WORD *)v385;
                if ( !*(_WORD *)v385 )
                  goto LABEL_712;
              }
              v389 = L"&apos;";
              goto LABEL_673;
            }
            goto LABEL_712;
          }
          v390 = CFmtStream::operator<<(v8, L" ");
          v391 = CFmtStream::operator<<(v390, XSI_TYPE);
          CFmtStream::operator<<(v391, L"=\"");
          CWStr::CWStr((CWStr *)&v716, TYPE_NCharPrefix);
          v392 = &Class;
          v386 = v716;
          if ( v716 )
            v392 = (const WCHAR *)v716;
          v393 = *v392;
          if ( *v392 )
          {
            while ( 1 )
            {
              if ( v393 == 34 )
              {
                v395 = L"&quot;";
                goto LABEL_691;
              }
              if ( v393 == 38 )
              {
                v395 = L"&amp;";
                goto LABEL_691;
              }
              if ( v393 == 39 )
                break;
              if ( v393 == 60 )
              {
                v395 = L"&lt;";
LABEL_691:
                v394 = v8;
                goto LABEL_692;
              }
              v394 = v8;
              if ( v393 == 62 )
              {
                v395 = L"&gt;";
LABEL_692:
                CFmtStream::operator<<(v394, v395);
                goto LABEL_693;
              }
              CFmtStream::operator<<(v8, *v392);
LABEL_693:
              v393 = *++v392;
              if ( !*v392 )
                goto LABEL_712;
            }
            v395 = L"&apos;";
            goto LABEL_691;
          }
LABEL_712:
          operator delete(v386, 2u);
          CFmtStream::operator<<(v8, L"\"");
          v402 = CFmtStream::operator<<(v8, L" ");
          v403 = CFmtStream::operator<<(v402, ATTR_PREFIX_LENGTH);
          v404 = CFmtStream::operator<<(v403, L"=\"");
          v405 = CFmtStream::operator<<(v404, *(unsigned int *)&v43[56 * v6 + 16]);
          CFmtStream::operator<<(v405, L"\"");
          if ( (unsigned int)(v354 - 1) <= 1 )
            goto LABEL_741;
          if ( TYPE_SQLBINARY )
          {
            v406 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 8] )
              v406 = *(const WCHAR **)&v43[56 * v6 + 8];
            v407 = (char *)((char *)TYPE_SQLBINARY - (char *)v406);
            do
            {
              v408 = *(unsigned __int16 *)&v407[(_QWORD)v406];
              v409 = *v406 - v408;
              if ( v409 )
                break;
              ++v406;
            }
            while ( v408 );
            if ( !v409 )
              goto LABEL_741;
          }
          if ( TYPE_SQLVARYBIN )
          {
            v410 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 8] )
              v410 = *(const WCHAR **)&v43[56 * v6 + 8];
            v411 = (char *)((char *)TYPE_SQLVARYBIN - (char *)v410);
            do
            {
              v412 = *(unsigned __int16 *)&v411[(_QWORD)v410];
              v413 = *v410 - v412;
              if ( v413 )
                break;
              ++v410;
            }
            while ( v412 );
            if ( !v413 )
              goto LABEL_741;
          }
          if ( TYPE_SYBBINARY )
          {
            v414 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 8] )
              v414 = *(const WCHAR **)&v43[56 * v6 + 8];
            v415 = (char *)((char *)TYPE_SYBBINARY - (char *)v414);
            do
            {
              v416 = *(unsigned __int16 *)&v415[(_QWORD)v414];
              v417 = *v414 - v416;
              if ( v417 )
                break;
              ++v414;
            }
            while ( v416 );
            if ( !v417 )
              goto LABEL_741;
          }
          if ( TYPE_SYBVARYBIN )
          {
            v418 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 8] )
              v418 = *(const WCHAR **)&v43[56 * v6 + 8];
            v419 = (char *)((char *)TYPE_SYBVARYBIN - (char *)v418);
            do
            {
              v420 = *(unsigned __int16 *)&v419[(_QWORD)v418];
              v421 = *v418 - v420;
              if ( v421 )
                break;
              ++v418;
            }
            while ( v420 );
            if ( !v421 )
            {
LABEL_741:
              v422 = *(_DWORD *)&v43[56 * v6 + 20];
              if ( v422 )
              {
                v423 = CFmtStream::operator<<(v8, L" ");
                v424 = CFmtStream::operator<<(v423, ATTR_MAX_LENGTH);
                v425 = CFmtStream::operator<<(v424, L"=\"");
                v426 = CFmtStream::operator<<(v425, v422);
                CFmtStream::operator<<(v426, L"\"");
              }
            }
          }
          if ( v354 != 3 )
          {
            if ( !EMPTY_STRING )
              goto LABEL_751;
            v427 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 48] )
              v427 = *(const WCHAR **)&v43[56 * v6 + 48];
            v428 = (char *)((char *)EMPTY_STRING - (char *)v427);
            do
            {
              v429 = *(unsigned __int16 *)&v428[(_QWORD)v427];
              v430 = *v427 - v429;
              if ( v430 )
                break;
              ++v427;
            }
            while ( v429 );
            if ( v430 )
            {
LABEL_751:
              v431 = CFmtStream::operator<<(v8, L" ");
              v432 = CFmtStream::operator<<(v431, ATTR_COLLATION);
              CFmtStream::operator<<(v432, L"=\"");
              CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v43[56 * v317 + 48]);
              CFmtStream::operator<<(v8, L"\"");
            }
          }
          if ( EMPTY_STRING )
          {
            v433 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 24] )
              v433 = *(const WCHAR **)&v43[56 * v6 + 24];
            v434 = (char *)((char *)EMPTY_STRING - (char *)v433);
            do
            {
              v435 = *(unsigned __int16 *)&v434[(_QWORD)v433];
              v436 = *v433 - v435;
              if ( v436 )
                break;
              ++v433;
            }
            while ( v435 );
            if ( !v436 )
              goto LABEL_1041;
          }
          CFmtStream::operator<<(v8, L"/>");
          v437 = CFmtStream::operator<<(v8, L"\r\n  <");
          CFmtStream::operator<<(v437, ELEM_FIELD);
          if ( v354 != 1 )
          {
            if ( v354 != 2 )
            {
              v438 = CFmtStream::operator<<(v8, L" ");
              v439 = CFmtStream::operator<<(v438, XSI_TYPE);
              CFmtStream::operator<<(v439, L"=\"");
              CWStr::CWStr((CWStr *)&v718, TYPE_NativeTerm);
              v440 = &Class;
              v441 = v718;
              if ( v718 )
                v440 = (const WCHAR *)v718;
              v442 = *v440;
              if ( *v440 )
              {
                while ( 1 )
                {
                  if ( v442 == 34 )
                  {
                    v444 = L"&quot;";
                    goto LABEL_775;
                  }
                  if ( v442 == 38 )
                  {
                    v444 = L"&amp;";
                    goto LABEL_775;
                  }
                  if ( v442 == 39 )
                    break;
                  if ( v442 == 60 )
                  {
                    v444 = L"&lt;";
LABEL_775:
                    v443 = v8;
                    goto LABEL_776;
                  }
                  v443 = v8;
                  if ( v442 == 62 )
                  {
                    v444 = L"&gt;";
LABEL_776:
                    CFmtStream::operator<<(v443, v444);
                    goto LABEL_777;
                  }
                  CFmtStream::operator<<(v8, *v440);
LABEL_777:
                  v442 = *++v440;
                  if ( !*v440 )
                    goto LABEL_814;
                }
                v444 = L"&apos;";
                goto LABEL_775;
              }
              goto LABEL_814;
            }
            v445 = CFmtStream::operator<<(v8, L" ");
            v446 = CFmtStream::operator<<(v445, XSI_TYPE);
            CFmtStream::operator<<(v446, L"=\"");
            CWStr::CWStr((CWStr *)&v719, TYPE_NCharTerm);
            v447 = &Class;
            v441 = v719;
            if ( v719 )
              v447 = (const WCHAR *)v719;
            v448 = *v447;
            if ( *v447 )
            {
              while ( 1 )
              {
                if ( v448 == 34 )
                {
                  v450 = L"&quot;";
                  goto LABEL_793;
                }
                if ( v448 == 38 )
                {
                  v450 = L"&amp;";
                  goto LABEL_793;
                }
                if ( v448 == 39 )
                  break;
                if ( v448 == 60 )
                {
                  v450 = L"&lt;";
LABEL_793:
                  v449 = v8;
                  goto LABEL_794;
                }
                v449 = v8;
                if ( v448 == 62 )
                {
                  v450 = L"&gt;";
LABEL_794:
                  CFmtStream::operator<<(v449, v450);
                  goto LABEL_795;
                }
                CFmtStream::operator<<(v8, *v447);
LABEL_795:
                v448 = *++v447;
                if ( !*v447 )
                  goto LABEL_814;
              }
              v450 = L"&apos;";
              goto LABEL_793;
            }
LABEL_814:
            operator delete(v441, 2u);
            CFmtStream::operator<<(v8, L"\"");
            v457 = CFmtStream::operator<<(v8, L" ");
            v458 = CFmtStream::operator<<(v457, ATTR_TERMINATOR);
            CFmtStream::operator<<(v458, L"=\"");
            v459 = 56LL * v317;
            CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v43[v459 + 24]);
            CFmtStream::operator<<(v8, L"\"");
            v460 = CFmtStream::operator<<(v8, L" ");
            v461 = CFmtStream::operator<<(v460, ATTR_MAX_LENGTH);
            v462 = CFmtStream::operator<<(v461, L"=\"");
            v463 = CFmtStream::operator<<(v462, 2);
            CFmtStream::operator<<(v463, L"\"");
            if ( v354 == 3 )
              goto LABEL_1041;
            if ( EMPTY_STRING )
            {
              v464 = &Class;
              if ( *(_QWORD *)&v43[56 * v6 + 48] )
                v464 = *(const WCHAR **)&v43[56 * v6 + 48];
              v465 = (char *)((char *)EMPTY_STRING - (char *)v464);
              do
              {
                v466 = *(unsigned __int16 *)&v465[(_QWORD)v464];
                v467 = *v464 - v466;
                if ( v467 )
                  break;
                ++v464;
              }
              while ( v466 );
              if ( !v467 )
                goto LABEL_1041;
            }
            v468 = CFmtStream::operator<<(v8, L" ");
            v469 = CFmtStream::operator<<(v468, ATTR_COLLATION);
            CFmtStream::operator<<(v469, L"=\"");
            CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v43[v459 + 48]);
            goto LABEL_1040;
          }
          v451 = CFmtStream::operator<<(v8, L" ");
          v452 = CFmtStream::operator<<(v451, XSI_TYPE);
          CFmtStream::operator<<(v452, L"=\"");
          CWStr::CWStr((CWStr *)&v720, TYPE_CharTerm);
          v453 = &Class;
          v441 = v720;
          if ( v720 )
            v453 = (const WCHAR *)v720;
          v454 = *v453;
          if ( !*v453 )
            goto LABEL_814;
          while ( 1 )
          {
            if ( v454 == 34 )
            {
              v456 = L"&quot;";
              goto LABEL_811;
            }
            if ( v454 == 38 )
            {
              v456 = L"&amp;";
              goto LABEL_811;
            }
            if ( v454 == 39 )
              break;
            if ( v454 == 60 )
            {
              v456 = L"&lt;";
LABEL_811:
              v455 = v8;
              goto LABEL_812;
            }
            v455 = v8;
            if ( v454 == 62 )
            {
              v456 = L"&gt;";
LABEL_812:
              CFmtStream::operator<<(v455, v456);
              goto LABEL_813;
            }
            CFmtStream::operator<<(v8, *v453);
LABEL_813:
            v454 = *++v453;
            if ( !*v453 )
              goto LABEL_814;
          }
          v456 = L"&apos;";
          goto LABEL_811;
        }
        v396 = CFmtStream::operator<<(v8, L" ");
        v397 = CFmtStream::operator<<(v396, XSI_TYPE);
        CFmtStream::operator<<(v397, L"=\"");
        CWStr::CWStr((CWStr *)&v717, TYPE_CharPrefix);
        v398 = &Class;
        v386 = v717;
        if ( v717 )
          v398 = (const WCHAR *)v717;
        v399 = *v398;
        if ( !*v398 )
          goto LABEL_712;
        while ( 1 )
        {
          if ( v399 == 34 )
          {
            v401 = L"&quot;";
            goto LABEL_709;
          }
          if ( v399 == 38 )
          {
            v401 = L"&amp;";
            goto LABEL_709;
          }
          if ( v399 == 39 )
            break;
          if ( v399 == 60 )
          {
            v401 = L"&lt;";
LABEL_709:
            v400 = v8;
            goto LABEL_710;
          }
          v400 = v8;
          if ( v399 == 62 )
          {
            v401 = L"&gt;";
LABEL_710:
            CFmtStream::operator<<(v400, v401);
            goto LABEL_711;
          }
          CFmtStream::operator<<(v8, *v398);
LABEL_711:
          v399 = *++v398;
          if ( !*v398 )
            goto LABEL_712;
        }
        v401 = L"&apos;";
        goto LABEL_709;
      }
      if ( !EMPTY_STRING )
        break;
      v470 = &Class;
      if ( *(_QWORD *)&v43[56 * v6 + 24] )
        v470 = *(const WCHAR **)&v43[56 * v6 + 24];
      v471 = (char *)((char *)EMPTY_STRING - (char *)v470);
      do
      {
        v472 = *(unsigned __int16 *)&v471[(_QWORD)v470];
        v473 = *v470 - v472;
        if ( v473 )
          break;
        ++v470;
      }
      while ( v472 );
      if ( v473 )
        break;
      if ( *(_DWORD *)&v43[56 * v6 + 20] )
      {
        if ( v354 != 1 )
        {
          if ( v354 != 2 )
          {
            v474 = CFmtStream::operator<<(v8, L" ");
            v475 = CFmtStream::operator<<(v474, XSI_TYPE);
            CFmtStream::operator<<(v475, L"=\"");
            CWStr::CWStr((CWStr *)&v710, TYPE_NativeFixed);
            v476 = &Class;
            v477 = v710;
            if ( v710 )
              v476 = (const WCHAR *)v710;
            v478 = *v476;
            if ( *v476 )
            {
              while ( 1 )
              {
                if ( v478 == 34 )
                {
                  v480 = L"&quot;";
                  goto LABEL_847;
                }
                if ( v478 == 38 )
                {
                  v480 = L"&amp;";
                  goto LABEL_847;
                }
                if ( v478 == 39 )
                  break;
                if ( v478 == 60 )
                {
                  v480 = L"&lt;";
LABEL_847:
                  v479 = v8;
                  goto LABEL_848;
                }
                v479 = v8;
                if ( v478 == 62 )
                {
                  v480 = L"&gt;";
LABEL_848:
                  CFmtStream::operator<<(v479, v480);
                  goto LABEL_849;
                }
                CFmtStream::operator<<(v8, *v476);
LABEL_849:
                v478 = *++v476;
                if ( !*v476 )
                  goto LABEL_886;
              }
              v480 = L"&apos;";
              goto LABEL_847;
            }
LABEL_886:
            operator delete(v477, 2u);
            CFmtStream::operator<<(v8, L"\"");
            v493 = CFmtStream::operator<<(v8, L" ");
            v494 = CFmtStream::operator<<(v493, ATTR_LENGTH);
            v495 = CFmtStream::operator<<(v494, L"=\"");
            v496 = CFmtStream::operator<<(v495, *(unsigned int *)&v43[56 * v6 + 20]);
            CFmtStream::operator<<(v496, L"\"");
            if ( v354 == 3 )
              goto LABEL_1041;
            if ( EMPTY_STRING )
            {
              v497 = &Class;
              if ( *(_QWORD *)&v43[56 * v6 + 48] )
                v497 = *(const WCHAR **)&v43[56 * v6 + 48];
              v498 = (char *)((char *)EMPTY_STRING - (char *)v497);
              do
              {
                v499 = *(unsigned __int16 *)&v498[(_QWORD)v497];
                v500 = *v497 - v499;
                if ( v500 )
                  break;
                ++v497;
              }
              while ( v499 );
              if ( !v500 )
                goto LABEL_1041;
            }
            v501 = CFmtStream::operator<<(v8, L" ");
            v502 = CFmtStream::operator<<(v501, ATTR_COLLATION);
            CFmtStream::operator<<(v502, L"=\"");
            v503 = &Class;
            if ( *(_QWORD *)&v43[56 * v6 + 48] )
              v503 = *(const WCHAR **)&v43[56 * v6 + 48];
            v504 = *v503;
            if ( *v503 )
            {
              while ( 2 )
              {
                switch ( v504 )
                {
                  case '"':
                    v506 = L"&quot;";
                    break;
                  case '&':
                    v506 = L"&amp;";
                    break;
                  case '\'':
                    v506 = L"&apos;";
                    break;
                  case '<':
                    v506 = L"&lt;";
                    break;
                  default:
                    v505 = v8;
                    if ( v504 != 62 )
                    {
                      CFmtStream::operator<<(v8, *v503);
                      goto LABEL_910;
                    }
                    v506 = L"&gt;";
LABEL_909:
                    CFmtStream::operator<<(v505, v506);
LABEL_910:
                    v504 = *++v503;
                    if ( !*v503 )
                      goto LABEL_1040;
                    continue;
                }
                break;
              }
              v505 = v8;
              goto LABEL_909;
            }
LABEL_1040:
            CFmtStream::operator<<(v8, L"\"");
            goto LABEL_1041;
          }
          v481 = CFmtStream::operator<<(v8, L" ");
          v482 = CFmtStream::operator<<(v481, XSI_TYPE);
          CFmtStream::operator<<(v482, L"=\"");
          CWStr::CWStr((CWStr *)&v711, TYPE_NCharFixed);
          v483 = &Class;
          v477 = v711;
          if ( v711 )
            v483 = (const WCHAR *)v711;
          v484 = *v483;
          if ( !*v483 )
            goto LABEL_886;
          while ( 2 )
          {
            switch ( v484 )
            {
              case '"':
                v486 = L"&quot;";
                break;
              case '&':
                v486 = L"&amp;";
                break;
              case '\'':
                v486 = L"&apos;";
                break;
              case '<':
                v486 = L"&lt;";
                break;
              default:
                v485 = v8;
                if ( v484 != 62 )
                {
                  CFmtStream::operator<<(v8, *v483);
                  goto LABEL_867;
                }
                v486 = L"&gt;";
LABEL_866:
                CFmtStream::operator<<(v485, v486);
LABEL_867:
                v484 = *++v483;
                if ( !*v483 )
                  goto LABEL_886;
                continue;
            }
            break;
          }
          v485 = v8;
          goto LABEL_866;
        }
        v487 = CFmtStream::operator<<(v8, L" ");
        v488 = CFmtStream::operator<<(v487, XSI_TYPE);
        CFmtStream::operator<<(v488, L"=\"");
        CWStr::CWStr((CWStr *)&v712, TYPE_CharFixed);
        v489 = &Class;
        v477 = v712;
        if ( v712 )
          v489 = (const WCHAR *)v712;
        v490 = *v489;
        if ( !*v489 )
          goto LABEL_886;
        while ( 2 )
        {
          switch ( v490 )
          {
            case '"':
              v492 = L"&quot;";
              break;
            case '&':
              v492 = L"&amp;";
              break;
            case '\'':
              v492 = L"&apos;";
              break;
            case '<':
              v492 = L"&lt;";
              break;
            default:
              v491 = v8;
              if ( v490 != 62 )
              {
                CFmtStream::operator<<(v8, *v489);
                goto LABEL_885;
              }
              v492 = L"&gt;";
LABEL_884:
              CFmtStream::operator<<(v491, v492);
LABEL_885:
              v490 = *++v489;
              if ( !*v489 )
                goto LABEL_886;
              continue;
          }
          break;
        }
        v491 = v8;
        goto LABEL_884;
      }
LABEL_1041:
      CFmtStream::operator<<(v8, L"/>");
      v318 = 1;
LABEL_1042:
      ++v317;
      ++v6;
      v319 = NumOfElements;
      if ( v317 >= (unsigned int)NumOfElements )
        goto LABEL_1043;
    }
    if ( v354 != 1 )
    {
      if ( v354 != 2 )
      {
        v507 = CFmtStream::operator<<(v8, L" ");
        v508 = CFmtStream::operator<<(v507, XSI_TYPE);
        CFmtStream::operator<<(v508, L"=\"");
        CWStr::CWStr((CWStr *)&v713, TYPE_NativeTerm);
        v509 = &Class;
        v510 = v713;
        if ( v713 )
          v509 = (const WCHAR *)v713;
        v511 = *v509;
        if ( *v509 )
        {
          while ( 1 )
          {
            if ( v511 == 34 )
            {
              v513 = L"&quot;";
              goto LABEL_928;
            }
            if ( v511 == 38 )
            {
              v513 = L"&amp;";
              goto LABEL_928;
            }
            if ( v511 == 39 )
              break;
            if ( v511 == 60 )
            {
              v513 = L"&lt;";
LABEL_928:
              v512 = v8;
              goto LABEL_929;
            }
            v512 = v8;
            if ( v511 == 62 )
            {
              v513 = L"&gt;";
LABEL_929:
              CFmtStream::operator<<(v512, v513);
              goto LABEL_930;
            }
            CFmtStream::operator<<(v8, *v509);
LABEL_930:
            v511 = *++v509;
            if ( !*v509 )
              goto LABEL_967;
          }
          v513 = L"&apos;";
          goto LABEL_928;
        }
        goto LABEL_967;
      }
      v514 = CFmtStream::operator<<(v8, L" ");
      v515 = CFmtStream::operator<<(v514, XSI_TYPE);
      CFmtStream::operator<<(v515, L"=\"");
      CWStr::CWStr((CWStr *)&v714, TYPE_NCharTerm);
      v516 = &Class;
      v510 = v714;
      if ( v714 )
        v516 = (const WCHAR *)v714;
      v517 = *v516;
      if ( *v516 )
      {
        while ( 1 )
        {
          if ( v517 == 34 )
          {
            v519 = L"&quot;";
            goto LABEL_946;
          }
          if ( v517 == 38 )
          {
            v519 = L"&amp;";
            goto LABEL_946;
          }
          if ( v517 == 39 )
            break;
          if ( v517 == 60 )
          {
            v519 = L"&lt;";
LABEL_946:
            v518 = v8;
            goto LABEL_947;
          }
          v518 = v8;
          if ( v517 == 62 )
          {
            v519 = L"&gt;";
LABEL_947:
            CFmtStream::operator<<(v518, v519);
            goto LABEL_948;
          }
          CFmtStream::operator<<(v8, *v516);
LABEL_948:
          v517 = *++v516;
          if ( !*v516 )
            goto LABEL_967;
        }
        v519 = L"&apos;";
        goto LABEL_946;
      }
LABEL_967:
      operator delete(v510, 2u);
      CFmtStream::operator<<(v8, L"\"");
      v526 = CFmtStream::operator<<(v8, L" ");
      v527 = CFmtStream::operator<<(v526, ATTR_TERMINATOR);
      CFmtStream::operator<<(v527, L"=\"");
      v528 = &Class;
      if ( *(_QWORD *)&v43[56 * v6 + 24] )
        v528 = *(const WCHAR **)&v43[56 * v6 + 24];
      v529 = *v528;
      if ( *v528 )
      {
        while ( 1 )
        {
          if ( v529 == 34 )
          {
            v531 = L"&quot;";
            goto LABEL_981;
          }
          if ( v529 == 38 )
          {
            v531 = L"&amp;";
            goto LABEL_981;
          }
          if ( v529 == 39 )
            break;
          if ( v529 == 60 )
          {
            v531 = L"&lt;";
LABEL_981:
            v530 = v8;
            goto LABEL_982;
          }
          v530 = v8;
          if ( v529 == 62 )
          {
            v531 = L"&gt;";
LABEL_982:
            CFmtStream::operator<<(v530, v531);
            goto LABEL_983;
          }
          CFmtStream::operator<<(v8, *v528);
LABEL_983:
          v529 = *++v528;
          if ( !*v528 )
            goto LABEL_984;
        }
        v531 = L"&apos;";
        goto LABEL_981;
      }
LABEL_984:
      CFmtStream::operator<<(v8, L"\"");
      if ( (unsigned int)(v354 - 1) <= 1 )
        goto LABEL_1013;
      if ( TYPE_SQLBINARY )
      {
        v532 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v532 = *(const WCHAR **)&v43[56 * v6 + 8];
        v533 = (char *)((char *)TYPE_SQLBINARY - (char *)v532);
        do
        {
          v534 = *(unsigned __int16 *)&v533[(_QWORD)v532];
          v535 = *v532 - v534;
          if ( v535 )
            break;
          ++v532;
        }
        while ( v534 );
        if ( !v535 )
          goto LABEL_1013;
      }
      if ( TYPE_SQLVARYBIN )
      {
        v536 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v536 = *(const WCHAR **)&v43[56 * v6 + 8];
        v537 = (char *)((char *)TYPE_SQLVARYBIN - (char *)v536);
        do
        {
          v538 = *(unsigned __int16 *)&v537[(_QWORD)v536];
          v539 = *v536 - v538;
          if ( v539 )
            break;
          ++v536;
        }
        while ( v538 );
        if ( !v539 )
          goto LABEL_1013;
      }
      if ( TYPE_SYBBINARY )
      {
        v540 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v540 = *(const WCHAR **)&v43[56 * v6 + 8];
        v541 = (char *)((char *)TYPE_SYBBINARY - (char *)v540);
        do
        {
          v542 = *(unsigned __int16 *)&v541[(_QWORD)v540];
          v543 = *v540 - v542;
          if ( v543 )
            break;
          ++v540;
        }
        while ( v542 );
        if ( !v543 )
          goto LABEL_1013;
      }
      if ( TYPE_SYBVARYBIN )
      {
        v544 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 8] )
          v544 = *(const WCHAR **)&v43[56 * v6 + 8];
        v545 = (char *)((char *)TYPE_SYBVARYBIN - (char *)v544);
        do
        {
          v546 = *(unsigned __int16 *)&v545[(_QWORD)v544];
          v547 = *v544 - v546;
          if ( v547 )
            break;
          ++v544;
        }
        while ( v546 );
        if ( !v547 )
        {
LABEL_1013:
          v548 = *(_DWORD *)&v43[56 * v6 + 20];
          if ( v548 )
          {
            v549 = CFmtStream::operator<<(v8, L" ");
            v550 = CFmtStream::operator<<(v549, ATTR_MAX_LENGTH);
            v551 = CFmtStream::operator<<(v550, L"=\"");
            v552 = CFmtStream::operator<<(v551, v548);
            CFmtStream::operator<<(v552, L"\"");
          }
        }
      }
      if ( v354 == 3 )
        goto LABEL_1041;
      if ( EMPTY_STRING )
      {
        v553 = &Class;
        if ( *(_QWORD *)&v43[56 * v6 + 48] )
          v553 = *(const WCHAR **)&v43[56 * v6 + 48];
        v554 = (char *)((char *)EMPTY_STRING - (char *)v553);
        do
        {
          v555 = *(unsigned __int16 *)&v554[(_QWORD)v553];
          v556 = *v553 - v555;
          if ( v556 )
            break;
          ++v553;
        }
        while ( v555 );
        if ( !v556 )
          goto LABEL_1041;
      }
      v557 = CFmtStream::operator<<(v8, L" ");
      v558 = CFmtStream::operator<<(v557, ATTR_COLLATION);
      CFmtStream::operator<<(v558, L"=\"");
      v559 = &Class;
      if ( *(_QWORD *)&v43[56 * v6 + 48] )
        v559 = *(const WCHAR **)&v43[56 * v6 + 48];
      v560 = *v559;
      if ( !*v559 )
        goto LABEL_1040;
      while ( 1 )
      {
        if ( v560 == 34 )
        {
          v562 = L"&quot;";
          goto LABEL_1037;
        }
        if ( v560 == 38 )
        {
          v562 = L"&amp;";
          goto LABEL_1037;
        }
        if ( v560 == 39 )
          break;
        if ( v560 == 60 )
        {
          v562 = L"&lt;";
LABEL_1037:
          v561 = v8;
          goto LABEL_1038;
        }
        v561 = v8;
        if ( v560 == 62 )
        {
          v562 = L"&gt;";
LABEL_1038:
          CFmtStream::operator<<(v561, v562);
          goto LABEL_1039;
        }
        CFmtStream::operator<<(v8, *v559);
LABEL_1039:
        v560 = *++v559;
        if ( !*v559 )
          goto LABEL_1040;
      }
      v562 = L"&apos;";
      goto LABEL_1037;
    }
    v520 = CFmtStream::operator<<(v8, L" ");
    v521 = CFmtStream::operator<<(v520, XSI_TYPE);
    CFmtStream::operator<<(v521, L"=\"");
    CWStr::CWStr((CWStr *)&v708, TYPE_CharTerm);
    v522 = &Class;
    v510 = v708;
    if ( v708 )
      v522 = (const WCHAR *)v708;
    v523 = *v522;
    if ( !*v522 )
      goto LABEL_967;
    while ( 1 )
    {
      if ( v523 == 34 )
      {
        v525 = L"&quot;";
        goto LABEL_964;
      }
      if ( v523 == 38 )
      {
        v525 = L"&amp;";
        goto LABEL_964;
      }
      if ( v523 == 39 )
        break;
      if ( v523 == 60 )
      {
        v525 = L"&lt;";
LABEL_964:
        v524 = v8;
        goto LABEL_965;
      }
      v524 = v8;
      if ( v523 == 62 )
      {
        v525 = L"&gt;";
LABEL_965:
        CFmtStream::operator<<(v524, v525);
        goto LABEL_966;
      }
      CFmtStream::operator<<(v8, *v522);
LABEL_966:
      v523 = *++v522;
      if ( !*v522 )
        goto LABEL_967;
    }
    v525 = L"&apos;";
    goto LABEL_964;
  }
LABEL_1043:
  v563 = CFmtStream::operator<<(v8, L"\r\n </");
  v564 = CFmtStream::operator<<(v563, ELEM_RECORD);
  CFmtStream::operator<<(v564, L">");
  v565 = CFmtStream::operator<<(v8, L"\r\n <");
  CFmtStream::operator<<(v565, ELEM_ROW);
  CFmtStream::operator<<(v8, L">");
  qsort(v43, v319, 0x38u, CBCPFormatField::CompareFunc);
  v566 = 0;
  LODWORD(v725) = 0;
  if ( v319 )
  {
    _mm_lfence();
    v567 = 0;
    v568 = v706;
    do
    {
      v569 = &v43[56 * v567];
      if ( !*((_DWORD *)v569 + 4) && !*((_DWORD *)v569 + 5) && EMPTY_STRING )
      {
        v570 = &Class;
        if ( *((_QWORD *)v569 + 3) )
          v570 = (const WCHAR *)*((_QWORD *)v569 + 3);
        v571 = (char *)((char *)EMPTY_STRING - (char *)v570);
        do
        {
          v572 = *(unsigned __int16 *)&v571[(_QWORD)v570];
          v573 = *v570 - v572;
          if ( v573 )
            break;
          ++v570;
        }
        while ( v572 );
        if ( !v573 )
          goto LABEL_1216;
      }
      v574 = *((_DWORD *)v569 + 8);
      if ( !v574 )
        goto LABEL_1216;
      if ( v721 )
        v575 = v721 + 76LL * v566;
      else
        v575 = 0;
      v40 = v318 < v574;
      v576 = EndPtr;
      if ( v40 )
      {
        v577 = v707;
        do
        {
          ++v577;
          v578 = CFmtStream::operator<<(v8, L"\r\n  <");
          CFmtStream::operator<<(v578, ELEM_COLUMN);
          CFmtStream::operator<<(v8, L"/>");
          v574 = *(_DWORD *)&v576[56 * v567 + 32];
        }
        while ( v577 < v574 );
        v566 = (unsigned int)v725;
      }
      v707 = v574 + 1;
      v579 = CFmtStream::operator<<(v8, L"\r\n  <");
      CFmtStream::operator<<(v579, ELEM_COLUMN);
      v580 = CFmtStream::operator<<(v8, L" ");
      v581 = CFmtStream::operator<<(v580, ATTR_SOURCE);
      v582 = CFmtStream::operator<<(v581, L"=\"");
      v583 = CFmtStream::operator<<(v582, *(unsigned int *)&v576[56 * v567]);
      CFmtStream::operator<<(v583, L"\"");
      v584 = CFmtStream::operator<<(v8, L" ");
      v585 = CFmtStream::operator<<(v584, ATTR_NAME);
      CFmtStream::operator<<(v585, L"=\"");
      CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v576[56 * v566 + 40]);
      CFmtStream::operator<<(v8, L"\"");
      if ( TYPE_SQLCHAR )
      {
        v586 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v586 = *(const WCHAR **)&v576[56 * v567 + 8];
        v587 = (char *)((char *)TYPE_SQLCHAR - (char *)v586);
        do
        {
          v588 = *(unsigned __int16 *)&v587[(_QWORD)v586];
          v589 = *v586 - v588;
          if ( v589 )
            break;
          ++v586;
        }
        while ( v588 );
        if ( !v589 )
          goto LABEL_1174;
      }
      if ( TYPE_SQLVARYCHAR )
      {
        v590 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v590 = *(const WCHAR **)&v576[56 * v567 + 8];
        v591 = (char *)((char *)TYPE_SQLVARYCHAR - (char *)v590);
        do
        {
          v592 = *(unsigned __int16 *)&v591[(_QWORD)v590];
          v593 = *v590 - v592;
          if ( v593 )
            break;
          ++v590;
        }
        while ( v592 );
        if ( !v593 )
          goto LABEL_1174;
      }
      if ( TYPE_SYBCHAR )
      {
        v594 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v594 = *(const WCHAR **)&v576[56 * v567 + 8];
        v595 = (char *)((char *)TYPE_SYBCHAR - (char *)v594);
        do
        {
          v596 = *(unsigned __int16 *)&v595[(_QWORD)v594];
          v597 = *v594 - v596;
          if ( v597 )
            break;
          ++v594;
        }
        while ( v596 );
        if ( !v597 )
          goto LABEL_1174;
      }
      if ( TYPE_SYBVARYCHAR )
      {
        v598 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v598 = *(const WCHAR **)&v576[56 * v567 + 8];
        v599 = (char *)((char *)TYPE_SYBVARYCHAR - (char *)v598);
        do
        {
          v600 = *(unsigned __int16 *)&v599[(_QWORD)v598];
          v601 = *v598 - v600;
          if ( v601 )
            break;
          ++v598;
        }
        while ( v600 );
        if ( !v601 )
          goto LABEL_1174;
      }
      if ( TYPE_SQLNCHAR )
      {
        v602 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v602 = *(const WCHAR **)&v576[56 * v567 + 8];
        v603 = (char *)((char *)TYPE_SQLNCHAR - (char *)v602);
        do
        {
          v604 = *(unsigned __int16 *)&v603[(_QWORD)v602];
          v605 = *v602 - v604;
          if ( v605 )
            break;
          ++v602;
        }
        while ( v604 );
        if ( !v605 )
          goto LABEL_1174;
      }
      if ( !TYPE_SQLNVARCHAR )
        goto LABEL_1176;
      v606 = &Class;
      if ( *(_QWORD *)&v576[56 * v567 + 8] )
        v606 = *(const WCHAR **)&v576[56 * v567 + 8];
      v607 = (char *)((char *)TYPE_SQLNVARCHAR - (char *)v606);
      do
      {
        v608 = *(unsigned __int16 *)&v607[(_QWORD)v606];
        v609 = *v606 - v608;
        if ( v609 )
          break;
        ++v606;
      }
      while ( v608 );
      if ( v609 )
      {
LABEL_1176:
        v662 = CFmtStream::operator<<(v8, L" ");
        v663 = CFmtStream::operator<<(v662, XSI_TYPE);
        CFmtStream::operator<<(v663, L"=\"");
        CFmtStream::WriteXMLString(v8, (const struct CWStr *)&v576[56 * v566 + 8]);
        CFmtStream::operator<<(v8, L"\"");
        if ( !v575 || *(_DWORD *)v575 )
          goto LABEL_1215;
        if ( TYPE_SQLDECIMAL )
        {
          v664 = &Class;
          if ( *(_QWORD *)&v576[56 * v567 + 8] )
            v664 = *(const WCHAR **)&v576[56 * v567 + 8];
          v665 = (char *)((char *)TYPE_SQLDECIMAL - (char *)v664);
          do
          {
            v666 = *(unsigned __int16 *)&v665[(_QWORD)v664];
            v667 = *v664 - v666;
            if ( v667 )
              break;
            ++v664;
          }
          while ( v666 );
          if ( !v667 )
            goto LABEL_1192;
        }
        if ( TYPE_SQLNUMERIC )
        {
          v668 = &Class;
          if ( *(_QWORD *)&v576[56 * v567 + 8] )
            v668 = *(const WCHAR **)&v576[56 * v567 + 8];
          v669 = (char *)((char *)TYPE_SQLNUMERIC - (char *)v668);
          do
          {
            v670 = *(unsigned __int16 *)&v669[(_QWORD)v668];
            v671 = *v668 - v670;
            if ( v671 )
              break;
            ++v668;
          }
          while ( v670 );
          if ( !v671 )
          {
LABEL_1192:
            v672 = *(unsigned __int8 *)(v575 + 68);
            v673 = CFmtStream::operator<<(v8, L" ");
            v674 = CFmtStream::operator<<(v673, ATTR_PRECISION);
            v675 = CFmtStream::operator<<(v674, L"=\"");
            v676 = CFmtStream::operator<<(v675, v672);
            CFmtStream::operator<<(v676, L"\"");
            v677 = *(unsigned __int8 *)(v575 + 69);
            v678 = CFmtStream::operator<<(v8, L" ");
            v679 = CFmtStream::operator<<(v678, ATTR_SCALE);
            v680 = CFmtStream::operator<<(v679, L"=\"");
            v681 = CFmtStream::operator<<(v680, v677);
            CFmtStream::operator<<(v681, L"\"");
          }
        }
        if ( !TYPE_SQLTIME )
          goto LABEL_1213;
        v682 = &Class;
        if ( *(_QWORD *)&v576[56 * v567 + 8] )
          v682 = *(const WCHAR **)&v576[56 * v567 + 8];
        v683 = (char *)((char *)TYPE_SQLTIME - (char *)v682);
        do
        {
          v684 = *(unsigned __int16 *)&v683[(_QWORD)v682];
          v685 = *v682 - v684;
          if ( v685 )
            break;
          ++v682;
        }
        while ( v684 );
        if ( v685 )
        {
LABEL_1213:
          if ( !TYPE_SQLDATETIME2 )
            goto LABEL_1238;
          v686 = &Class;
          if ( *(_QWORD *)&v576[56 * v567 + 8] )
            v686 = *(const WCHAR **)&v576[56 * v567 + 8];
          v687 = (char *)((char *)TYPE_SQLDATETIME2 - (char *)v686);
          do
          {
            v688 = *(unsigned __int16 *)&v687[(_QWORD)v686];
            v689 = *v686 - v688;
            if ( v689 )
              break;
            ++v686;
          }
          while ( v688 );
          if ( v689 )
          {
LABEL_1238:
            if ( !TYPE_SQLDATETIMEOFFSET )
              goto LABEL_1215;
            v690 = &Class;
            if ( *(_QWORD *)&v576[56 * v567 + 8] )
              v690 = *(const WCHAR **)&v576[56 * v567 + 8];
            v691 = (char *)((char *)TYPE_SQLDATETIMEOFFSET - (char *)v690);
            do
            {
              v692 = *(unsigned __int16 *)&v691[(_QWORD)v690];
              v693 = *v690 - v692;
              if ( v693 )
                break;
              ++v690;
            }
            while ( v692 );
            if ( v693 )
              goto LABEL_1215;
          }
        }
      }
      else
      {
LABEL_1174:
        if ( !v575 || *(_DWORD *)v575 )
          goto LABEL_1215;
        v610 = CFmtStream::operator<<(v8, L" ");
        v611 = CFmtStream::operator<<(v610, XSI_TYPE);
        CFmtStream::operator<<(v611, L"=\"");
        CWStr::CWStr((CWStr *)&v708, (const wchar_t *)(v575 + 4));
        v612 = &Class;
        v613 = v708;
        if ( v708 )
          v612 = (const WCHAR *)v708;
        v614 = *v612;
        if ( *v612 )
        {
          while ( 1 )
          {
            if ( v614 == 34 )
            {
              v616 = L"&quot;";
              goto LABEL_1120;
            }
            if ( v614 == 38 )
            {
              v616 = L"&amp;";
              goto LABEL_1120;
            }
            if ( v614 == 39 )
              break;
            if ( v614 == 60 )
            {
              v616 = L"&lt;";
LABEL_1120:
              v615 = v8;
              goto LABEL_1121;
            }
            v615 = v8;
            if ( v614 == 62 )
            {
              v616 = L"&gt;";
LABEL_1121:
              CFmtStream::operator<<(v615, v616);
              goto LABEL_1122;
            }
            CFmtStream::operator<<(v8, *v612);
LABEL_1122:
            v614 = *++v612;
            if ( !*v612 )
              goto LABEL_1123;
          }
          v616 = L"&apos;";
          goto LABEL_1120;
        }
LABEL_1123:
        operator delete(v613, 2u);
        CFmtStream::operator<<(v8, L"\"");
        v617 = CWStr::CWStr((CWStr *)&v713, (const wchar_t *)(v575 + 4));
        v618 = v568 | 1;
        v706 = v618;
        if ( TYPE_SQLDECIMAL )
        {
          v619 = *(const WCHAR **)v617;
          v620 = &Class;
          if ( v619 )
            v620 = v619;
          v621 = v618;
          v622 = (char *)((char *)TYPE_SQLDECIMAL - (char *)v620);
          do
          {
            v623 = *(unsigned __int16 *)&v622[(_QWORD)v620];
            v624 = *v620 - v623;
            if ( v624 )
              break;
            ++v620;
          }
          while ( v623 );
          if ( !v624 )
            goto LABEL_1137;
        }
        v625 = CWStr::CWStr((CWStr *)&v714, (const wchar_t *)(v575 + 4));
        v618 |= 2u;
        if ( !TYPE_SQLNUMERIC )
          goto LABEL_1138;
        v626 = *(const WCHAR **)v625;
        v627 = &Class;
        if ( v626 )
          v627 = v626;
        v621 = v618;
        v628 = (char *)((char *)TYPE_SQLNUMERIC - (char *)v627);
        do
        {
          v629 = *(unsigned __int16 *)&v628[(_QWORD)v627];
          v630 = *v627 - v629;
          if ( v630 )
            break;
          ++v627;
        }
        while ( v629 );
        if ( v630 )
        {
LABEL_1138:
          v631 = 0;
          v621 = v618;
        }
        else
        {
LABEL_1137:
          v631 = 1;
        }
        if ( (v621 & 2) != 0 )
        {
          v618 &= ~2u;
          operator delete(v714, 2u);
        }
        if ( (v618 & 1) != 0 )
        {
          v618 &= ~1u;
          operator delete(v713, 2u);
        }
        if ( v631 )
        {
          v632 = *(unsigned __int8 *)(v575 + 68);
          v633 = CFmtStream::operator<<(v8, L" ");
          v634 = CFmtStream::operator<<(v633, ATTR_PRECISION);
          v635 = CFmtStream::operator<<(v634, L"=\"");
          v636 = CFmtStream::operator<<(v635, v632);
          CFmtStream::operator<<(v636, L"\"");
          v637 = *(unsigned __int8 *)(v575 + 69);
          v638 = CFmtStream::operator<<(v8, L" ");
          v639 = CFmtStream::operator<<(v638, ATTR_SCALE);
          v640 = CFmtStream::operator<<(v639, L"=\"");
          v641 = CFmtStream::operator<<(v640, v637);
          CFmtStream::operator<<(v641, L"\"");
        }
        v642 = CWStr::CWStr((CWStr *)&v710, (const wchar_t *)(v575 + 4));
        v568 = v618 | 4;
        v706 = v568;
        if ( TYPE_SQLTIME )
        {
          v643 = *(const WCHAR **)v642;
          v644 = &Class;
          if ( v643 )
            v644 = v643;
          v645 = v568;
          v646 = (char *)((char *)TYPE_SQLTIME - (char *)v644);
          do
          {
            v647 = *(unsigned __int16 *)&v646[(_QWORD)v644];
            v648 = *v644 - v647;
            if ( v648 )
              break;
            ++v644;
          }
          while ( v647 );
          if ( !v648 )
            goto LABEL_1166;
        }
        v649 = CWStr::CWStr((CWStr *)&v711, (const wchar_t *)(v575 + 4));
        v568 |= 8u;
        v706 = v568;
        if ( TYPE_SQLDATETIME2 )
        {
          v650 = *(const WCHAR **)v649;
          v651 = &Class;
          if ( v650 )
            v651 = v650;
          v645 = v568;
          v652 = (char *)((char *)TYPE_SQLDATETIME2 - (char *)v651);
          do
          {
            v653 = *(unsigned __int16 *)&v652[(_QWORD)v651];
            v654 = *v651 - v653;
            if ( v654 )
              break;
            ++v651;
          }
          while ( v653 );
          if ( !v654 )
            goto LABEL_1166;
        }
        v655 = CWStr::CWStr((CWStr *)&v712, (const wchar_t *)(v575 + 4));
        v568 |= 0x10u;
        if ( !TYPE_SQLDATETIMEOFFSET )
          goto LABEL_1167;
        v656 = *(const WCHAR **)v655;
        v657 = &Class;
        if ( v656 )
          v657 = v656;
        v645 = v568;
        v658 = (char *)((char *)TYPE_SQLDATETIMEOFFSET - (char *)v657);
        do
        {
          v659 = *(unsigned __int16 *)&v658[(_QWORD)v657];
          v660 = *v657 - v659;
          if ( v660 )
            break;
          ++v657;
        }
        while ( v659 );
        if ( v660 )
        {
LABEL_1167:
          v661 = 0;
          v645 = v568;
        }
        else
        {
LABEL_1166:
          v661 = 1;
        }
        if ( (v645 & 0x10) != 0 )
        {
          v568 &= ~0x10u;
          operator delete(v712, 2u);
        }
        if ( (v568 & 8) != 0 )
        {
          v568 &= ~8u;
          operator delete(v711, 2u);
        }
        if ( (v568 & 4) != 0 )
        {
          v568 &= ~4u;
          operator delete(v710, 2u);
        }
        if ( !v661 )
          goto LABEL_1215;
      }
      v694 = *(unsigned __int8 *)(v575 + 69);
      v695 = CFmtStream::operator<<(v8, L" ");
      v696 = CFmtStream::operator<<(v695, ATTR_SCALE);
      v697 = CFmtStream::operator<<(v696, L"=\"");
      v698 = CFmtStream::operator<<(v697, v694);
      CFmtStream::operator<<(v698, L"\"");
LABEL_1215:
      CFmtStream::operator<<(v8, L"/>");
      v43 = EndPtr;
      v319 = NumOfElements;
LABEL_1216:
      LODWORD(v725) = ++v566;
      ++v567;
      v318 = v707;
    }
    while ( v566 < v319 );
  }
  v699 = CFmtStream::operator<<(v8, L"\r\n </");
  v700 = CFmtStream::operator<<(v699, ELEM_ROW);
  CFmtStream::operator<<(v700, L">");
  v701 = CFmtStream::operator<<(v8, L"\r\n</");
  v702 = CFmtStream::operator<<(v701, ELEM_BCPFORMAT);
  CFmtStream::operator<<(v702, L">");
  v703 = v722;
  *v722 = v8;
  (*(void (__fastcall **)(CFmtStream *))(*(_QWORD *)v8 + 8LL))(v8);
  if ( v727 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v727 + 16LL))(v727);
  (*(void (__fastcall **)(CFmtStream *))(*(_QWORD *)v8 + 16LL))(v8);
  _mm_lfence();
  `eh vector destructor iterator'(v43, 0x38u, *((_QWORD *)v43 - 1), (void (*)(void *))CBCPFormatField::~CBCPFormatField);
  _mm_lfence();
  operator delete[](v43 - 8, 56LL * *((_QWORD *)v43 - 1) + 8);
  if ( *pExceptionObject )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*pExceptionObject + 16LL))(*pExceptionObject);
  return v703;
}

```

## disassembly

```asm
0x1801482e0  push    rbp
0x1801482e2  push    rbx
0x1801482e3  push    rsi
0x1801482e4  push    rdi
0x1801482e5  push    r12
0x1801482e7  push    r13
0x1801482e9  push    r14
0x1801482eb  push    r15
0x1801482ed  lea     rbp, [rsp-1018h]
0x1801482f5  mov     eax, 1118h
0x1801482fa  call    _alloca_probe
0x1801482ff  sub     rsp, rax
0x180148302  mov     rax, cs:__security_cookie
0x180148309  xor     rax, rsp
0x18014830c  mov     [rbp+1050h+var_48], rax
0x180148313  mov     [rbp+1050h+var_10A8], r9
0x180148317  mov     rbx, r8
0x18014831a  mov     [rsp+1150h+pExceptionObject], rbx
0x18014831f  mov     [rbp+1050h+var_10A0], rdx
0x180148323  mov     r13, rcx
0x180148326  mov     [rsp+1150h+var_1110], rdx
0x18014832b  mov     [rbp+1050h+var_1098], rbx
0x18014832f  xor     r14d, r14d
0x180148332  mov     [rsp+1150h+var_1118], r14d
0x180148337  mov     [rsp+1150h+var_10D8], r14
0x18014833c  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180148343  mov     rax, [rcx]
0x180148346  mov     edx, 20h ; ' '
0x18014834b  mov     rax, [rax+58h]
0x18014834f  call    cs:__guard_dispatch_icall_fptr
0x180148355  mov     rdi, rax
0x180148358  test    rax, rax
0x18014835b  jz      loc_18014C764
0x180148361  mov     [rax+0Ch], r14d
0x180148365  mov     [rax+18h], r14
0x180148369  lea     rax, ??_7CFmtStream@@6B@; const CFmtStream::`vftable'
0x180148370  mov     [rdi], rax
0x180148373  mov     [rdi+8], r14d
0x180148377  lea     rax, [rdi+10h]
0x18014837b  mov     [rax+8], rax
0x18014837f  mov     [rax], rax
0x180148382  lock inc dword ptr [rdi+8]
0x180148386  mov     [rax+8], rax
0x18014838a  mov     [rax], rax
0x18014838d  mov     [rbp+1050h+var_1090], rdi
0x180148391  mov     rax, [rdi]
0x180148394  mov     rcx, rdi
0x180148397  mov     rax, [rax+8]
0x18014839b  call    cs:__guard_dispatch_icall_fptr
0x1801483a1  mov     [rsp+1150h+var_1118], 40h ; '@'
0x1801483a9  xor     edx, edx; Val
0x1801483ab  mov     r8d, 1010h; Size
0x1801483b1  lea     rcx, [rbp+1050h+var_1070]; void *
0x1801483b5  call    memset_0
0x1801483ba  mov     rcx, [rbx]
0x1801483bd  mov     [rbp+1050h+var_1070], rcx
0x1801483c1  test    rcx, rcx
0x1801483c4  jz      short loc_1801483D3
0x1801483c6  mov     rax, [rcx]
0x1801483c9  mov     rax, [rax+8]
0x1801483cd  call    cs:__guard_dispatch_icall_fptr
0x1801483d3  xor     edx, edx; Val
0x1801483d5  mov     r8d, 1000h; Size
0x1801483db  lea     rcx, [rbp+1050h+var_1068]; void *
0x1801483df  call    memset_0
0x1801483e4  mov     [rbp+1050h+var_68], r14
0x1801483eb  lea     r8, [rbp+1050h+var_1070]; struct CBulkFmtStreamReader *
0x1801483ef  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1801483f6  mov     edx, esi; int
0x1801483f8  lea     rcx, [r13+90h]; struct CWStr *
0x1801483ff  call    ?GetString@@YAXAEAVCWStr@@JAEAVCBulkFmtStreamReader@@@Z; GetString(CWStr &,long,CBulkFmtStreamReader &)
0x180148404  mov     r8, cs:?FORMAT_VERSION_110@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_110
0x18014840b  test    r8, r8
0x18014840e  jz      short loc_18014844C
0x180148410  mov     rax, [r13+90h]
0x180148417  lea     rcx, Class
0x18014841e  test    rax, rax
0x180148421  cmovnz  rcx, rax
0x180148425  sub     r8, rcx
0x180148428  nop     dword ptr [rax+rax+00000000h]
0x180148430  movzx   edx, word ptr [rcx]
0x180148433  movzx   eax, word ptr [rcx+r8]
0x180148438  sub     edx, eax
0x18014843a  jnz     short loc_180148444
0x18014843c  add     rcx, 2
0x180148440  test    eax, eax
0x180148442  jnz     short loc_180148430
0x180148444  test    edx, edx
0x180148446  jz      loc_1801485CC
0x18014844c  mov     r8, cs:?FORMAT_VERSION_100@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_100
0x180148453  test    r8, r8
0x180148456  jz      short loc_18014848C
0x180148458  mov     rax, [r13+90h]
0x18014845f  lea     rcx, Class
0x180148466  test    rax, rax
0x180148469  cmovnz  rcx, rax
0x18014846d  sub     r8, rcx
0x180148470  movzx   edx, word ptr [rcx]
0x180148473  movzx   eax, word ptr [rcx+r8]
0x180148478  sub     edx, eax
0x18014847a  jnz     short loc_180148484
0x18014847c  add     rcx, 2
0x180148480  test    eax, eax
0x180148482  jnz     short loc_180148470
0x180148484  test    edx, edx
0x180148486  jz      loc_1801485CC
0x18014848c  mov     r8, cs:?FORMAT_VERSION_90@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_90
0x180148493  test    r8, r8
0x180148496  jz      short loc_1801484CC
0x180148498  mov     rax, [r13+90h]
0x18014849f  lea     rcx, Class
0x1801484a6  test    rax, rax
0x1801484a9  cmovnz  rcx, rax
0x1801484ad  sub     r8, rcx
0x1801484b0  movzx   edx, word ptr [rcx]
0x1801484b3  movzx   eax, word ptr [rcx+r8]
0x1801484b8  sub     edx, eax
0x1801484ba  jnz     short loc_1801484C4
0x1801484bc  add     rcx, 2
0x1801484c0  test    eax, eax
0x1801484c2  jnz     short loc_1801484B0
0x1801484c4  test    edx, edx
0x1801484c6  jz      loc_1801485CC
0x1801484cc  mov     r8, cs:?FORMAT_VERSION_80@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_80
0x1801484d3  test    r8, r8
0x1801484d6  jz      short loc_18014850C
0x1801484d8  mov     rax, [r13+90h]
0x1801484df  lea     rcx, Class
0x1801484e6  test    rax, rax
0x1801484e9  cmovnz  rcx, rax
0x1801484ed  sub     r8, rcx
0x1801484f0  movzx   edx, word ptr [rcx]
0x1801484f3  movzx   eax, word ptr [rcx+r8]
0x1801484f8  sub     edx, eax
0x1801484fa  jnz     short loc_180148504
0x1801484fc  add     rcx, 2
0x180148500  test    eax, eax
0x180148502  jnz     short loc_1801484F0
0x180148504  test    edx, edx
0x180148506  jz      loc_1801485CC
0x18014850c  mov     r8, cs:?FORMAT_VERSION_70@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_70
0x180148513  test    r8, r8
0x180148516  jz      short loc_18014854C
0x180148518  mov     rax, [r13+90h]
0x18014851f  lea     rcx, Class
0x180148526  test    rax, rax
0x180148529  cmovnz  rcx, rax
0x18014852d  sub     r8, rcx
0x180148530  movzx   edx, word ptr [rcx]
0x180148533  movzx   eax, word ptr [rcx+r8]
0x180148538  sub     edx, eax
0x18014853a  jnz     short loc_180148544
0x18014853c  add     rcx, 2
0x180148540  test    eax, eax
0x180148542  jnz     short loc_180148530
0x180148544  test    edx, edx
0x180148546  jz      loc_1801485CC
0x18014854c  mov     r8, cs:?FORMAT_VERSION_60@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_60
0x180148553  test    r8, r8
0x180148556  jz      short loc_180148588
0x180148558  mov     rax, [r13+90h]
0x18014855f  lea     rcx, Class
0x180148566  test    rax, rax
0x180148569  cmovnz  rcx, rax
0x18014856d  sub     r8, rcx
0x180148570  movzx   edx, word ptr [rcx]
0x180148573  movzx   eax, word ptr [rcx+r8]
0x180148578  sub     edx, eax
0x18014857a  jnz     short loc_180148584
0x18014857c  add     rcx, 2
0x180148580  test    eax, eax
0x180148582  jnz     short loc_180148570
0x180148584  test    edx, edx
0x180148586  jz      short loc_1801485CC
0x180148588  mov     r8, cs:?FORMAT_VERSION_42@@3PEB_WEB; wchar_t const * const FORMAT_VERSION_42
0x18014858f  test    r8, r8
0x180148592  jz      loc_18014C743
0x180148598  mov     rax, [r13+90h]
0x18014859f  lea     rcx, Class
0x1801485a6  test    rax, rax
0x1801485a9  cmovnz  rcx, rax
0x1801485ad  sub     r8, rcx
0x1801485b0  movzx   edx, word ptr [rcx]
0x1801485b3  movzx   eax, word ptr [rcx+r8]
0x1801485b8  sub     edx, eax
0x1801485ba  jnz     short loc_1801485C4
0x1801485bc  add     rcx, 2
0x1801485c0  test    eax, eax
0x1801485c2  jnz     short loc_1801485B0
0x1801485c4  test    edx, edx
0x1801485c6  jnz     loc_18014C743
0x1801485cc  mov     [rbp+1050h+EndPtr], r14
0x1801485d0  lea     rcx, [rbp+1050h+var_1070]; this
0x1801485d4  call    ?SkipWs@CBulkFmtStreamReader@@AEAAJXZ; CBulkFmtStreamReader::SkipWs(void)
0x1801485d9  mov     r8d, 14h; unsigned int
0x1801485df  lea     rdx, [rbp+1050h+String]; char *
0x1801485e6  lea     rcx, [rbp+1050h+var_1070]; this
0x1801485ea  call    ?GetString@CBulkFmtStreamReader@@QEAAJPEADK@Z; CBulkFmtStreamReader::GetString(char *,ulong)
0x1801485ef  test    eax, eax
0x1801485f1  jnz     loc_18014C68E
0x1801485f7  mov     r8d, 0Ah; Radix
0x1801485fd  lea     rdx, [rbp+1050h+EndPtr]; EndPtr
0x180148601  lea     rcx, [rbp+1050h+String]; String
0x180148608  call    cs:__imp__strtoui64
0x18014860e  mov     r12, rax
0x180148611  mov     [rsp+1150h+NumOfElements], rax
0x180148616  cmp     rax, 7FFFFFFFh
0x18014861c  ja      loc_18014C68E
0x180148622  mov     rcx, [rbp+1050h+EndPtr]
0x180148626  test    rcx, rcx
0x180148629  jz      short loc_180148642
0x18014862b  movzx   edx, byte ptr [rcx]
0x18014862e  test    dl, dl
0x180148630  jz      short loc_180148642
0x180148632  mov     ecx, edx; C
0x180148634  call    cs:__imp_isspace
0x18014863a  test    eax, eax
0x18014863c  jz      loc_18014C68E
0x180148642  lea     eax, [r12-1]
0x180148647  cmp     eax, 0FFFh
0x18014864c  ja      loc_18014C68E
0x180148652  lfence
0x180148655  mov     ebx, r12d
0x180148658  mov     eax, 38h ; '8'
0x18014865d  mul     rbx
0x180148660  mov     rdx, rax
0x180148663  cmovb   rdx, rsi
0x180148667  add     rdx, 8
0x18014866b  cmovb   rdx, rsi
0x18014866f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180148676  mov     rax, [rcx]
0x180148679  mov     rax, [rax+70h]
0x18014867d  call    cs:__guard_dispatch_icall_fptr
0x180148683  nop
0x180148684  mov     [rsp+1150h+var_1110], rax
0x180148689  lea     rcx, ??1CBCPFormatField@@QEAA@XZ; CBCPFormatField::~CBCPFormatField(void)
0x180148690  test    rax, rax
0x180148693  jz      short loc_1801486C1
0x180148695  lfence
0x180148698  mov     [rax], rbx
0x18014869b  lea     r15, [rax+8]
0x18014869f  mov     [rbp+1050h+EndPtr], r15
0x1801486a3  mov     [rsp+1150h+var_1130], rcx; void (*)(void *)
0x1801486a8  lea     r9, ??0CBCPFormatField@@QEAA@XZ; void (*)(void *)
0x1801486af  mov     r8d, ebx; unsigned __int64
0x1801486b2  mov     edx, 38h ; '8'; unsigned __int64
0x1801486b7  mov     rcx, r15; void *
0x1801486ba  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1801486bf  jmp     short loc_1801486C8
0x1801486c1  mov     r15, r14
0x1801486c4  mov     [rbp+1050h+EndPtr], r14
0x1801486c8  mov     [rsp+1150h+var_10D8], r15
0x1801486cd  test    r15, r15
0x1801486d0  jz      loc_18014C784
0x1801486d6  mov     ebx, r14d
0x1801486d9  test    r12d, r12d
0x1801486dc  jz      loc_180149C8D
0x1801486e2  lfence
0x1801486e5  nop     word ptr [rax+rax+00000000h]
0x1801486f0  mov     eax, ebx
0x1801486f2  imul    rsi, rax, 38h ; '8'
0x1801486f6  mov     [rbp+1050h+var_1088], r14
0x1801486fa  lea     rcx, [rbp+1050h+var_1070]; this
0x1801486fe  call    ?SkipWs@CBulkFmtStreamReader@@AEAAJXZ; CBulkFmtStreamReader::SkipWs(void)
0x180148703  mov     r8d, 14h; unsigned int
0x180148709  lea     rdx, [rbp+1050h+String]; char *
0x180148710  lea     rcx, [rbp+1050h+var_1070]; this
0x180148714  call    ?GetString@CBulkFmtStreamReader@@QEAAJPEADK@Z; CBulkFmtStreamReader::GetString(char *,ulong)
0x180148719  test    eax, eax
0x18014871b  jnz     loc_18014A0F8
0x180148721  mov     r8d, 0Ah; Radix
0x180148727  lea     rdx, [rbp+1050h+var_1088]; EndPtr
0x18014872b  lea     rcx, [rbp+1050h+String]; String
0x180148732  call    cs:__imp__strtoui64
0x180148738  mov     r14, rax
0x18014873b  cmp     rax, 7FFFFFFFh
0x180148741  ja      loc_18014C837
0x180148747  mov     rcx, [rbp+1050h+var_1088]
0x18014874b  test    rcx, rcx
0x18014874e  jz      short loc_180148767
0x180148750  movzx   edx, byte ptr [rcx]
0x180148753  test    dl, dl
0x180148755  jz      short loc_180148767
0x180148757  mov     ecx, edx; C
0x180148759  call    cs:__imp_isspace
0x18014875f  test    eax, eax
0x180148761  jz      loc_18014C837
0x180148767  mov     [rsi+r15], r14d
0x18014876b  mov     eax, ebx
0x18014876d  imul    rcx, rax, 38h ; '8'
0x180148771  lea     eax, [rbx+1]
0x180148774  cmp     [rcx+r15], eax
0x180148778  jnz     loc_18014C837
0x18014877e  mov     eax, ebx
0x180148780  imul    rsi, rax, 38h ; '8'
0x180148784  lea     r8, [rbp+1050h+var_1070]; struct CBulkFmtStreamReader *
0x180148788  mov     edx, ebx; int
0x18014878a  lea     rcx, [rsi+8]
0x18014878e  add     rcx, r15; struct CWStr *
0x180148791  call    ?GetString@@YAXAEAVCWStr@@JAEAVCBulkFmtStreamReader@@@Z; GetString(CWStr &,long,CBulkFmtStreamReader &)
  ... truncated ...
```
