# Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(Microsoft::Basix::Dct::OperationOnLinkId const &)

- ea: `0x1802741d0`
- end: `0x180279eb5`
- name: `?ProcessLinkOperation@SmilesV3@Dct@Basix@Microsoft@@AEAAXAEBVOperationOnLinkId@234@@Z`
- size: `23781`
- prototype: `void __fastcall(Microsoft::Basix::Dct::SmilesV3 *__hidden this, const struct Microsoft::Basix::Dct::OperationOnLinkId *)`
- caller_count: `6`
- callee_count: `49`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18025e08c`
- `0x18025e404`
- `0x18025f410`
- `0x18025ff00`
- `0x18026da30`
- `0x180273934`

## callees

- `0x18000d9c0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017380`
- `0x180017404`
- `0x180018b94`
- `0x18001902c`
- `0x1800199ec`
- `0x18001dad8`
- `0x18001db78`
- `0x18001f8d4`
- `0x180021850`
- `0x180024700`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x18002a8ec`
- `0x18003e2e0`
- `0x18003f5c0`
- `0x1800448dc`
- `0x1800bee54`
- `0x1800c76d4`
- `0x1800c81d0`
- `0x1800f33a4`
- `0x1801b741c`
- `0x1801cd974`
- `0x1801cda84`
- `0x1801fe67c`
- `0x18024b19c`
- `0x18024b320`
- `0x18024b780`
- `0x180250ffc`
- `0x1802511ec`
- `0x180251400`
- `0x1802598d4`
- `0x1802618b4`
- `0x1802741d0`
- `0x1802ea40c`
- `0x1802f15e8`
- `0x180311dbc`
- `0x180311e54`
- `0x180312e30`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f140`
- `0x180375c40`
- `0x180376380`
- `0x1803768a0`

## string_xrefs

- `0x180276cb5`: `LinkSuspended`
- `0x18027841f`: `LinkSuspended`
- `0x18027847e`: `primaryLinkSuspended`
- `0x1802747ee`: `CurrentActiveNumLinks`
- `0x180275520`: `CurrentActiveNumLinks`
- `0x1802761a2`: `CurrentActiveNumLinks`
- `0x1802770d2`: `CurrentActiveNumLinks`
- `0x180277c54`: `CurrentActiveNumLinks`
- `0x180278840`: `CurrentActiveNumLinks`
- `0x1802793c9`: `CurrentActiveNumLinks`
- `0x1802771b8`: `SuspendLinkType`
- `0x180278932`: `SuspendLinkType`
- `0x18027729f`: `SuspendLinkId`
- `0x180278a20`: `SuspendLinkId`
- `0x180277489`: `LinkSuspend`
- `0x180278bfe`: `LinkSuspend`
- `0x1802778c9`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s`
- `0x18027903e`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s`
- `0x180276d14`: `linkSuspendedDueToTimeout`
- `0x1802790d9`: `LinkResumed`
- `0x1802794ba`: `ResumeLinkType`
- `0x1802795ab`: `ResumedLinkId`
- `0x18027977d`: `LinkResume`
- `0x180274f45`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d`
- `0x1802783ab`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d`
- `0x180279b20`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d`
- `0x1802742de`: `LinkRemovedTimeout`
- `0x180274401`: `link removed due to timeout`
- `0x18027443b`: `a link is removed after timeout`
- `0x180274461`: `LinkRemoveTimeout`
- `0x1802748d9`: `RemovedLinkType`
- `0x18027560e`: `RemovedLinkType`
- `0x18027628a`: `RemovedLinkType`
- `0x180277d45`: `RemovedLinkType`
- `0x1802749ca`: `RemovedLinkId`
- `0x180275700`: `RemovedLinkId`
- `0x180276381`: `RemovedLinkId`
- `0x180277e36`: `RemovedLinkId`
- `0x180274ba2`: `LinkRemove`
- `0x1802758ed`: `LinkRemove`
- `0x180276753`: `LinkRemove`
- `0x180278008`: `LinkRemove`
- `0x180277964`: `LinkRemoved`
- `0x180275ea1`: `LinkRemovedAtClose`
- `0x18027652f`: `StateBeforeRemove`
- `0x180276c05`: `Checkpoint.SMILES.%s(%s|%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, suspendTimeInSec=%d`
- `0x180274fe1`: `LinkRemovedDueToError`
- `0x180275d2a`: `Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, error=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=816
void __fastcall Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(
        Microsoft::Basix::Dct::SmilesV3 *this,
        const struct Microsoft::Basix::Dct::OperationOnLinkId *a2)
{
  const struct Microsoft::Basix::Dct::OperationOnLinkId *v2; // rsi
  int v4; // r12d
  char v5; // r14
  __int64 v6; // rbx
  __int64 v7; // r8
  volatile signed __int32 *v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  std::_Ref_count_base *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  const char *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r15
  _QWORD *v38; // r14
  __int64 v39; // rsi
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rdi
  __int64 v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  _QWORD *v56; // rax
  _QWORD *v57; // r15
  __int64 v58; // rsi
  __int64 v59; // rdi
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rdx
  char *v68; // rax
  volatile signed __int32 *v69; // rbx
  __int64 *v70; // rax
  __int64 *v71; // rax
  const char *v72; // r8
  const char *v73; // r9
  __int64 v74; // r15
  char **v75; // rbx
  volatile signed __int32 *v76; // rbx
  __int64 v77; // rbx
  __int64 v78; // rax
  __int64 v79; // rdi
  void (__fastcall *v80)(__int64, __int64 *, __int64 *); // rbx
  char v81; // al
  __int64 Description; // rax
  __int64 v83; // rbx
  __int64 v84; // rdx
  signed __int32 v85; // eax
  signed __int32 v86; // ett
  std::_Ref_count_base *v87; // rcx
  std::_Ref_count_base *v88; // rbx
  __int64 v89; // rax
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r15
  void **v93; // r14
  __int64 v94; // rsi
  __int64 v95; // rdi
  __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rdi
  __int64 v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // rdx
  __int64 v111; // rdi
  __int64 v112; // rbx
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rdx
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdi
  __int64 v119; // rbx
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rdx
  __int64 v123; // rdx
  __int64 v124; // rdx
  __int64 v125; // r15
  _QWORD *v126; // r14
  __int64 v127; // rsi
  __int64 v128; // rdi
  __int64 v129; // rbx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rdx
  __int64 v133; // rdx
  __int64 v134; // rdx
  __int64 v135; // rax
  __int64 v136; // rdx
  __int64 v137; // rdi
  __int64 v138; // rbx
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // rdx
  _QWORD *v144; // rax
  _QWORD *v145; // r15
  __int64 v146; // rsi
  __int64 v147; // rdi
  __int64 v148; // rbx
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rdx
  __int64 v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rax
  __int64 v155; // rdx
  char *v156; // rax
  volatile signed __int32 *v157; // rbx
  void **v158; // rax
  _QWORD *v159; // rax
  __int64 *v160; // rax
  const char *v161; // r8
  const char *v162; // r9
  __int64 v163; // r15
  char **v164; // rbx
  volatile signed __int32 *v165; // rbx
  __int64 v166; // rcx
  __int64 v167; // rbx
  __int64 v168; // rbx
  __int64 v169; // rdx
  signed __int32 v170; // eax
  signed __int32 v171; // ett
  std::_Ref_count_base *v172; // rcx
  std::_Ref_count_base *v173; // rbx
  __int64 v174; // rax
  __int64 v175; // r8
  __int64 v176; // rdx
  __int64 v177; // rdi
  __int64 v178; // rbx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rdx
  __int64 v182; // rdx
  __int64 v183; // rdx
  __int64 v184; // rdi
  __int64 v185; // rbx
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rdx
  __int64 v189; // rdx
  __int64 v190; // rdx
  __int64 v191; // rdi
  __int64 v192; // rbx
  __int64 v193; // rax
  __int64 v194; // rax
  __int64 v195; // rdx
  __int64 v196; // rdx
  __int64 v197; // rdx
  __int64 v198; // r15
  _QWORD *v199; // r14
  __int64 v200; // rsi
  __int64 v201; // rdi
  __int64 v202; // rbx
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rdx
  __int64 v206; // rdx
  __int64 v207; // rdx
  __int64 v208; // rax
  __int64 v209; // rdx
  __int64 v210; // rdi
  __int64 v211; // rbx
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // rdx
  __int64 v215; // rdx
  __int64 v216; // rdx
  __int64 v217; // rdi
  __int64 v218; // rbx
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rdx
  __int64 v222; // rdx
  __int64 v223; // rdx
  __int64 v224; // rax
  __int64 v225; // rsi
  __int64 v226; // rdi
  __int64 v227; // rbx
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // rdx
  __int64 v231; // rdx
  __int64 v232; // rdx
  __int64 v233; // rax
  __int64 v234; // rdx
  __int64 v235; // rax
  __int64 v236; // rsi
  __int64 v237; // rdi
  __int64 v238; // rbx
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rdx
  __int64 v242; // rdx
  __int64 v243; // rdx
  __int64 v244; // rax
  __int64 v245; // rdx
  char *v246; // rax
  volatile signed __int32 *v247; // rbx
  __int64 *v248; // rax
  __int64 *v249; // rax
  __int64 *v250; // rax
  const char *v251; // r8
  const char *v252; // r9
  __int64 v253; // r15
  char **v254; // rbx
  __int64 v255; // rbx
  __int64 v256; // rbx
  __int64 v257; // rdx
  signed __int32 v258; // eax
  signed __int32 v259; // ett
  std::_Ref_count_base *v260; // rcx
  std::_Ref_count_base *v261; // rbx
  void (__fastcall **v262)(std::_Ref_count_base *, void **); // rax
  __int64 v263; // r8
  __int64 v264; // rdx
  __int64 v265; // r14
  __int64 v266; // rsi
  __int64 v267; // rdi
  __int64 v268; // rbx
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rdx
  __int64 v272; // rdx
  __int64 v273; // rdx
  __int64 v274; // rax
  __int64 v275; // rdx
  __int64 v276; // rdi
  __int64 v277; // rbx
  __int64 v278; // rax
  __int64 v279; // rax
  __int64 v280; // rdx
  __int64 v281; // rdx
  __int64 v282; // rdx
  __int64 v283; // rdi
  __int64 v284; // rbx
  __int64 v285; // rax
  __int64 v286; // rax
  __int64 v287; // rdx
  __int64 v288; // rdx
  __int64 v289; // rdx
  __int64 v290; // rdi
  __int64 v291; // rbx
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rdx
  __int64 v295; // rdx
  __int64 v296; // rdx
  __int64 v297; // r15
  _QWORD *v298; // r14
  __int64 v299; // rsi
  __int64 v300; // rdi
  __int64 v301; // rbx
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rdx
  __int64 v305; // rdx
  __int64 v306; // rdx
  __int64 v307; // rax
  __int64 v308; // rdx
  __int64 v309; // rdi
  __int64 v310; // rbx
  __int64 v311; // rax
  __int64 v312; // rax
  __int64 v313; // rdx
  __int64 v314; // rdx
  __int64 v315; // rdx
  _QWORD *v316; // rax
  _QWORD *v317; // r15
  __int64 v318; // rsi
  __int64 v319; // rdi
  __int64 v320; // rbx
  __int64 v321; // rax
  __int64 v322; // rax
  __int64 v323; // rdx
  __int64 v324; // rdx
  __int64 v325; // rdx
  __int64 v326; // rax
  __int64 v327; // rdx
  char *v328; // rax
  volatile signed __int32 *v329; // rbx
  __int64 *v330; // rax
  __int64 *v331; // rax
  __int64 *v332; // rax
  const char *v333; // r8
  const char *v334; // r9
  __int64 v335; // r15
  char **v336; // rbx
  __int64 v337; // rbx
  std::_Ref_count_base *v338; // rcx
  __int64 v339; // rax
  __int64 v340; // r8
  __int64 v341; // rdx
  __int64 v342; // rdi
  __int64 v343; // rbx
  __int64 v344; // rax
  __int64 v345; // rax
  __int64 v346; // rdx
  __int64 v347; // rdx
  __int64 v348; // rdx
  __int64 v349; // rdi
  __int64 v350; // rbx
  __int64 v351; // rax
  __int64 v352; // rax
  __int64 v353; // rdx
  __int64 v354; // rdx
  __int64 v355; // rdx
  __int64 v356; // rdi
  __int64 v357; // rbx
  __int64 v358; // rax
  __int64 v359; // rax
  __int64 v360; // rdx
  __int64 v361; // rdx
  __int64 v362; // rdx
  __int64 v363; // r15
  _QWORD *v364; // r14
  __int64 v365; // rsi
  __int64 v366; // rdi
  __int64 v367; // rbx
  __int64 v368; // rax
  __int64 v369; // rax
  __int64 v370; // rdx
  __int64 v371; // rdx
  __int64 v372; // rdx
  __int64 v373; // rax
  __int64 v374; // rdx
  __int64 v375; // rdi
  __int64 v376; // rbx
  __int64 v377; // rax
  __int64 v378; // rax
  __int64 v379; // rdx
  __int64 v380; // rdx
  __int64 v381; // rdx
  _QWORD *v382; // rax
  _QWORD *v383; // r15
  __int64 v384; // rsi
  __int64 v385; // rdi
  __int64 v386; // rbx
  __int64 v387; // rax
  __int64 v388; // rax
  __int64 v389; // rdx
  __int64 v390; // rdx
  __int64 v391; // rdx
  __int64 v392; // rax
  __int64 v393; // rdx
  char *v394; // rax
  volatile signed __int32 *v395; // rbx
  __int64 *v396; // rax
  __int64 *v397; // rax
  const char *v398; // r8
  const char *v399; // r9
  __int64 v400; // r15
  char **v401; // rbx
  __int64 v402; // rbx
  __int64 v403; // rbx
  __int64 v404; // rdx
  signed __int32 v405; // eax
  signed __int32 v406; // ett
  std::_Ref_count_base *v407; // rcx
  std::_Ref_count_base *v408; // rbx
  void (__fastcall **v409)(std::_Ref_count_base *, void **); // rax
  __int64 v410; // r8
  __int64 v411; // rdx
  __int64 v412; // r14
  __int64 v413; // rsi
  __int64 v414; // rdi
  __int64 v415; // rbx
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rdx
  __int64 v419; // rdx
  __int64 v420; // rdx
  __int64 v421; // rax
  __int64 v422; // rdx
  __int64 v423; // rdi
  __int64 v424; // rbx
  __int64 v425; // rax
  __int64 v426; // rax
  __int64 v427; // rdx
  __int64 v428; // rdx
  __int64 v429; // rdx
  __int64 v430; // rdi
  __int64 v431; // rbx
  __int64 v432; // rax
  __int64 v433; // rax
  __int64 v434; // rdx
  __int64 v435; // rdx
  __int64 v436; // rdx
  __int64 v437; // rdi
  __int64 v438; // rbx
  __int64 v439; // rax
  __int64 v440; // rax
  __int64 v441; // rdx
  __int64 v442; // rdx
  __int64 v443; // rdx
  __int64 v444; // r15
  _QWORD *v445; // r14
  __int64 v446; // rsi
  __int64 v447; // rdi
  __int64 v448; // rbx
  __int64 v449; // rax
  __int64 v450; // rax
  __int64 v451; // rdx
  __int64 v452; // rdx
  __int64 v453; // rdx
  __int64 v454; // rax
  __int64 v455; // rdx
  __int64 v456; // rdi
  __int64 v457; // rbx
  __int64 v458; // rax
  __int64 v459; // rax
  __int64 v460; // rdx
  __int64 v461; // rdx
  __int64 v462; // rdx
  _QWORD *v463; // rax
  _QWORD *v464; // r15
  __int64 v465; // rsi
  __int64 v466; // rdi
  __int64 v467; // rbx
  __int64 v468; // rax
  __int64 v469; // rax
  __int64 v470; // rdx
  __int64 v471; // rdx
  __int64 v472; // rdx
  __int64 v473; // rax
  __int64 v474; // rdx
  char *v475; // rax
  volatile signed __int32 *v476; // rbx
  __int64 *v477; // rax
  __int64 *v478; // rax
  __int64 *v479; // rax
  const char *v480; // r8
  const char *v481; // r9
  __int64 v482; // r15
  char **v483; // rbx
  __int64 v484; // rbx
  std::_Ref_count_base *v485; // rcx
  __int64 v486; // rax
  __int64 v487; // r8
  __int64 v488; // rdx
  __int64 v489; // rdi
  __int64 v490; // rbx
  __int64 v491; // rax
  __int64 v492; // rax
  __int64 v493; // rdx
  __int64 v494; // rdx
  __int64 v495; // rdx
  __int64 v496; // rdi
  __int64 v497; // rbx
  __int64 v498; // rax
  __int64 v499; // rax
  __int64 v500; // rdx
  __int64 v501; // rdx
  __int64 v502; // rdx
  __int64 v503; // rdi
  __int64 v504; // rbx
  __int64 v505; // rax
  __int64 v506; // rax
  __int64 v507; // rdx
  __int64 v508; // rdx
  __int64 v509; // rdx
  __int64 v510; // r15
  _QWORD *v511; // r14
  __int64 v512; // rsi
  __int64 v513; // rdi
  __int64 v514; // rbx
  __int64 v515; // rax
  __int64 v516; // rax
  __int64 v517; // rdx
  __int64 v518; // rdx
  __int64 v519; // rdx
  __int64 v520; // rax
  __int64 v521; // rdx
  __int64 v522; // rdi
  __int64 v523; // rbx
  __int64 v524; // rax
  __int64 v525; // rax
  __int64 v526; // rdx
  __int64 v527; // rdx
  __int64 v528; // rdx
  _QWORD *v529; // rax
  _QWORD *v530; // r15
  __int64 v531; // rsi
  __int64 v532; // rdi
  __int64 v533; // rbx
  __int64 v534; // rax
  __int64 v535; // rax
  __int64 v536; // rdx
  __int64 v537; // rdx
  __int64 v538; // rdx
  __int64 v539; // rax
  __int64 v540; // rdx
  char *v541; // rax
  volatile signed __int32 *v542; // rbx
  __int64 *v543; // rax
  __int64 *v544; // rax
  const char *v545; // r8
  const char *v546; // r9
  __int64 v547; // r15
  char **v548; // rbx
  std::_Ref_count_base *v549; // rax
  std::_Ref_count_base *v550; // rax
  __int128 *v551; // rax
  __int64 v552; // r8
  const struct std::nothrow_t *v553; // rdx
  int v554; // r12d
  void *v555; // rcx
  Microsoft::Basix::Dct::LinkDataV3 *v556; // rcx
  int AveDelayOut; // eax
  __int64 v558; // rbx
  char **v559; // rcx
  int v560; // eax
  char *v561; // [rsp+20h] [rbp-E0h]
  char *v562; // [rsp+28h] [rbp-D8h]
  const char *v563; // [rsp+30h] [rbp-D0h]
  int v564; // [rsp+38h] [rbp-C8h]
  int v565; // [rsp+40h] [rbp-C0h]
  const char *v566; // [rsp+48h] [rbp-B8h]
  int v567; // [rsp+50h] [rbp-B0h]
  __int64 *v568; // [rsp+70h] [rbp-90h] BYREF
  char v569; // [rsp+78h] [rbp-88h]
  const struct Microsoft::Basix::Dct::OperationOnLinkId *v570; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v571; // [rsp+88h] [rbp-78h]
  __int64 p_Str; // [rsp+90h] [rbp-70h]
  __int64 *v573; // [rsp+98h] [rbp-68h]
  void *v574; // [rsp+A0h] [rbp-60h] BYREF
  void *v575; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v576; // [rsp+B0h] [rbp-50h]
  __int64 v577[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v578[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v579; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v580; // [rsp+108h] [rbp+8h]
  char v581; // [rsp+118h] [rbp+18h]
  __int128 *v582; // [rsp+120h] [rbp+20h]
  __int64 v583; // [rsp+128h] [rbp+28h] BYREF
  void *v584; // [rsp+130h] [rbp+30h]
  size_t v585; // [rsp+138h] [rbp+38h]
  char v586; // [rsp+140h] [rbp+40h]
  __int64 v587[4]; // [rsp+148h] [rbp+48h] BYREF
  char *Str; // [rsp+168h] [rbp+68h] BYREF
  void *v589; // [rsp+170h] [rbp+70h]
  __int64 v590; // [rsp+178h] [rbp+78h]
  unsigned __int64 v591; // [rsp+180h] [rbp+80h]
  _BYTE v592[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v593[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v594[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v595[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v596[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v597[32]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v598[32]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v599[4]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v600[4]; // [rsp+288h] [rbp+188h] BYREF
  __int64 v601[4]; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v602[4]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v603[4]; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v604[4]; // [rsp+308h] [rbp+208h] BYREF
  __int64 *v605; // [rsp+328h] [rbp+228h]
  __int64 v606[4]; // [rsp+330h] [rbp+230h] BYREF
  __int64 v607[4]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v608[4]; // [rsp+370h] [rbp+270h] BYREF
  __int64 v609[4]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v610[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 *v611; // [rsp+3D0h] [rbp+2D0h]
  __int64 v612[4]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v613[4]; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v614[4]; // [rsp+418h] [rbp+318h] BYREF
  __int64 v615[4]; // [rsp+438h] [rbp+338h] BYREF
  _BYTE v616[32]; // [rsp+458h] [rbp+358h] BYREF
  _BYTE v617[32]; // [rsp+478h] [rbp+378h] BYREF
  _BYTE v618[32]; // [rsp+498h] [rbp+398h] BYREF
  _BYTE v619[32]; // [rsp+4B8h] [rbp+3B8h] BYREF
  _BYTE v620[32]; // [rsp+4D8h] [rbp+3D8h] BYREF
  _BYTE v621[32]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v622[32]; // [rsp+518h] [rbp+418h] BYREF
  _BYTE v623[32]; // [rsp+538h] [rbp+438h] BYREF
  _BYTE v624[32]; // [rsp+558h] [rbp+458h] BYREF
  _BYTE v625[32]; // [rsp+578h] [rbp+478h] BYREF
  _BYTE v626[32]; // [rsp+598h] [rbp+498h] BYREF
  _BYTE v627[32]; // [rsp+5B8h] [rbp+4B8h] BYREF
  _BYTE v628[32]; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v629[32]; // [rsp+5F8h] [rbp+4F8h] BYREF
  _BYTE v630[32]; // [rsp+618h] [rbp+518h] BYREF
  _BYTE v631[32]; // [rsp+638h] [rbp+538h] BYREF
  _BYTE v632[32]; // [rsp+658h] [rbp+558h] BYREF
  _BYTE v633[32]; // [rsp+678h] [rbp+578h] BYREF
  _BYTE v634[32]; // [rsp+698h] [rbp+598h] BYREF
  _BYTE v635[32]; // [rsp+6B8h] [rbp+5B8h] BYREF
  _BYTE v636[32]; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v637[32]; // [rsp+6F8h] [rbp+5F8h] BYREF
  _BYTE v638[32]; // [rsp+718h] [rbp+618h] BYREF
  _BYTE v639[32]; // [rsp+738h] [rbp+638h] BYREF
  _BYTE v640[32]; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v641[32]; // [rsp+778h] [rbp+678h] BYREF
  _BYTE v642[32]; // [rsp+798h] [rbp+698h] BYREF
  _BYTE v643[32]; // [rsp+7B8h] [rbp+6B8h] BYREF
  _BYTE v644[32]; // [rsp+7D8h] [rbp+6D8h] BYREF
  _BYTE v645[32]; // [rsp+7F8h] [rbp+6F8h] BYREF
  _BYTE v646[32]; // [rsp+818h] [rbp+718h] BYREF
  _BYTE v647[32]; // [rsp+838h] [rbp+738h] BYREF
  _BYTE v648[32]; // [rsp+858h] [rbp+758h] BYREF
  _BYTE v649[32]; // [rsp+878h] [rbp+778h] BYREF
  _BYTE v650[32]; // [rsp+898h] [rbp+798h] BYREF
  _BYTE v651[32]; // [rsp+8B8h] [rbp+7B8h] BYREF
  _BYTE v652[32]; // [rsp+8D8h] [rbp+7D8h] BYREF
  _BYTE v653[32]; // [rsp+8F8h] [rbp+7F8h] BYREF
  _BYTE v654[32]; // [rsp+918h] [rbp+818h] BYREF
  _BYTE v655[32]; // [rsp+938h] [rbp+838h] BYREF
  _BYTE v656[32]; // [rsp+958h] [rbp+858h] BYREF
  _BYTE v657[32]; // [rsp+978h] [rbp+878h] BYREF
  _BYTE v658[32]; // [rsp+998h] [rbp+898h] BYREF
  _BYTE v659[32]; // [rsp+9B8h] [rbp+8B8h] BYREF
  _BYTE v660[32]; // [rsp+9D8h] [rbp+8D8h] BYREF
  _BYTE v661[8]; // [rsp+9F8h] [rbp+8F8h] BYREF
  std::_Ref_count_base *v662[2]; // [rsp+A00h] [rbp+900h] BYREF
  void *v663[2]; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v664; // [rsp+A20h] [rbp+920h]
  char v665; // [rsp+A28h] [rbp+928h]
  char *v666[2]; // [rsp+A30h] [rbp+930h] BYREF
  __m128i v667; // [rsp+A40h] [rbp+940h]
  std::_Ref_count_base *v668[2]; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v669; // [rsp+A60h] [rbp+960h]
  char v670; // [rsp+A68h] [rbp+968h]
  _QWORD v671[3]; // [rsp+A70h] [rbp+970h] BYREF
  unsigned __int64 v672; // [rsp+A88h] [rbp+988h]
  __int64 v673; // [rsp+A90h] [rbp+990h] BYREF
  void *v674; // [rsp+A98h] [rbp+998h] BYREF
  size_t v675; // [rsp+AA0h] [rbp+9A0h]
  __int64 v676; // [rsp+AA8h] [rbp+9A8h]
  void *v677[2]; // [rsp+AB0h] [rbp+9B0h] BYREF
  __m128i v678; // [rsp+AC0h] [rbp+9C0h]
  __int128 v679; // [rsp+AD0h] [rbp+9D0h] BYREF
  __m128i si128; // [rsp+AE0h] [rbp+9E0h]
  _QWORD v681[32]; // [rsp+AF0h] [rbp+9F0h] BYREF

  v2 = a2;
  v570 = a2;
  v4 = 0;
  LODWORD(p_Str) = 0;
  v679 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v679) = 0;
  *(_OWORD *)v666 = 0;
  v667 = si128;
  LOBYTE(v666[0]) = 0;
  v661[0] = *((_BYTE *)a2 + 24);
  v569 = *((_BYTE *)a2 + 25);
  v5 = v569;
  Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v671, *((_QWORD *)a2 + 1) + 80LL, 0, 6);
  if ( v569 )
    std::string::assign(v666, "(InfoOnly)");
  switch ( *(_BYTE *)v2 )
  {
    case 1:
      v484 = std::operator+<char>(&v579, v666, "LinkResumed");
      if ( v666 != (char **)v484 )
      {
        std::string::_Tidy_deallocate(v666);
        *(_OWORD *)v666 = *(_OWORD *)v484;
        v667 = *(__m128i *)(v484 + 16);
        *(_QWORD *)(v484 + 16) = 0;
        *(_QWORD *)(v484 + 24) = 15;
        *(_BYTE *)v484 = 0;
      }
      std::string::_Tidy_deallocate(&v579);
      if ( !v5 )
      {
        *(_OWORD *)v668 = 0;
        std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(*((_QWORD *)v2 + 1) + 120LL, v668);
        v485 = v668[0];
        if ( v668[0] )
        {
          v486 = *(_QWORD *)v668[0];
          v487 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v663 = 0;
          v488 = *(_QWORD *)(v487 + 112);
          if ( v488 )
            _InterlockedIncrement((volatile signed __int32 *)(v488 + 8));
          v663[0] = *(void **)(v487 + 104);
          v663[1] = *(void **)(v487 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, void **))(v486 + 8))(v485, v663);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v668);
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v662[0] = (std::_Ref_count_base *)v577;
        std::_Integral_to_string<char,unsigned int>(v592, *((unsigned int *)this + 373));
        v489 = std::string::string(v621, ":");
        v490 = std::string::string(v623, "\"");
        v491 = std::string::string(v624, "\"");
        v492 = std::operator+<char>(v625, v491, "NonIceDoR");
        LOBYTE(v493) = (_BYTE)v568;
        std::string::string(v593, v493, v492, v490);
        LOBYTE(v494) = (_BYTE)v568;
        std::string::string(v594, v494, v593, v489);
        LOBYTE(v495) = (_BYTE)v568;
        std::string::string(v577, v495, v594, v592);
        v668[0] = (std::_Ref_count_base *)v613;
        std::_Integral_to_string<char,unsigned int>(v595, *((unsigned int *)this + 372));
        v496 = std::string::string(v626, ":");
        v497 = std::string::string(v627, "\"");
        v498 = std::string::string(v628, "\"");
        v499 = std::operator+<char>(v622, v498, "IceDoR");
        LOBYTE(v500) = (_BYTE)v568;
        std::string::string(v596, v500, v499, v497);
        LOBYTE(v501) = (_BYTE)v568;
        std::string::string(v597, v501, v596, v496);
        LOBYTE(v502) = (_BYTE)v568;
        std::string::string(v613, v502, v597, v595);
        v611 = v612;
        std::_Integral_to_string<char,unsigned int>(v598, *((unsigned int *)this + 553));
        v503 = std::string::string(v610, ":");
        v504 = std::string::string(v639, "\"");
        v505 = std::string::string(v638, "\"");
        v506 = std::operator+<char>(v637, v505, "CurrentActiveNumLinks");
        LOBYTE(v507) = (_BYTE)v568;
        std::string::string(v599, v507, v506, v504);
        LOBYTE(v508) = (_BYTE)v568;
        std::string::string(v600, v508, v599, v503);
        LOBYTE(v509) = (_BYTE)v568;
        std::string::string(v612, v509, v600, v598);
        v605 = v615;
        v510 = std::string::string(v636, "\"");
        v511 = v671;
        if ( v672 > 0xF )
          v511 = (_QWORD *)v671[0];
        v512 = std::string::string(v635, "\"");
        v513 = std::string::string(v634, ":");
        v514 = std::string::string(v633, "\"");
        v515 = std::string::string(v632, "\"");
        v516 = std::operator+<char>(v631, v515, "ResumeLinkType");
        LOBYTE(v517) = (_BYTE)v568;
        std::string::string(v601, v517, v516, v514);
        LOBYTE(v518) = (_BYTE)v568;
        std::string::string(v602, v518, v601, v513);
        LOBYTE(v519) = (_BYTE)v568;
        std::string::string(v603, v519, v602, v512);
        v520 = std::operator+<char>(v630, v603, v511);
        LOBYTE(v521) = (_BYTE)v568;
        std::string::string(v615, v521, v520, v510);
        v573 = v614;
        std::_Integral_to_string<char,int>(v604, *((unsigned __int16 *)v570 + 1));
        v522 = std::string::string(v629, ":");
        v523 = std::string::string(v616, "\"");
        v524 = std::string::string(v648, "\"");
        v525 = std::operator+<char>(v649, v524, "ResumedLinkId");
        LOBYTE(v526) = (_BYTE)v568;
        std::string::string(v578, v526, v525, v523);
        LOBYTE(v527) = (_BYTE)v568;
        std::string::string(v606, v527, v578, v522);
        LOBYTE(v528) = (_BYTE)v568;
        std::string::string(v614, v528, v606, v604);
        v571 = (__int64 *)std::string::string(v650, "\"");
        v529 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v651, v661, 0, 6);
        v530 = v529;
        if ( v529[3] > 0xFu )
          v530 = (_QWORD *)*v529;
        v531 = std::string::string(v646, "\"");
        v532 = std::string::string(v652, ":");
        v533 = std::string::string(v653, "\"");
        v534 = std::string::string(v654, "\"");
        v535 = std::operator+<char>(v640, v534, "Direction");
        LOBYTE(v536) = (_BYTE)v568;
        std::string::string(v607, v536, v535, v533);
        LOBYTE(v537) = (_BYTE)v568;
        std::string::string(v608, v537, v607, v532);
        LOBYTE(v538) = (_BYTE)v568;
        std::string::string(v609, v538, v608, v531);
        v539 = std::operator+<char>(&v579, v609, v530);
        LOBYTE(v540) = (_BYTE)v568;
        std::string::string(v587, v540, v539, v571);
        v541 = (char *)v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          v541 = v666[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v663,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkResume",
          v541,
          (__int64)v587,
          (__int64)v614,
          (__int64)v615,
          (__int64)v612,
          (__int64)v613,
          (__int64)v577);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v606);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v592);
        v2 = v570;
        v5 = v569;
      }
      v542 = (volatile signed __int32 *)v663[1];
      if ( v663[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v542)(v542);
          if ( _InterlockedExchangeAdd(v542 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v542 + 8LL))(v542);
        }
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v570) = *((_DWORD *)this + 372);
        LODWORD(v574) = *((_DWORD *)this + 553);
        v543 = v671;
        if ( v672 > 0xF )
          v543 = (__int64 *)v671[0];
        v571 = v543;
        LOWORD(v568) = *((_WORD *)v2 + 1);
        v544 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v579, v661, 0, 6);
        v547 = (__int64)v544;
        if ( (unsigned __int64)v544[3] > 0xF )
          v547 = *v544;
        v548 = v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          LODWORD(v548) = v666[0];
        std::string::string(
          v577,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
          v545,
          v546,
          (_DWORD)v561,
          v562,
          (_DWORD)v563,
          v564,
          v565);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
          (unsigned int)v663,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v577,
          (_DWORD)v548,
          v547,
          (char)v568,
          (__int64)v571,
          (char)v574,
          (char)v570,
          p_Str);
        std::string::_Tidy_deallocate(v577);
        std::string::_Tidy_deallocate(&v579);
      }
      goto LABEL_311;
    case 2:
      v402 = std::operator+<char>(&v579, v666, "LinkSuspended");
      if ( v666 != (char **)v402 )
      {
        std::string::_Tidy_deallocate(v666);
        *(_OWORD *)v666 = *(_OWORD *)v402;
        v667 = *(__m128i *)(v402 + 16);
        *(_QWORD *)(v402 + 16) = 0;
        *(_QWORD *)(v402 + 24) = 15;
        *(_BYTE *)v402 = 0;
      }
      std::string::_Tidy_deallocate(&v579);
      std::string::assign(&v679, "primaryLinkSuspended");
      if ( !v5 )
      {
        v403 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v668 = 0;
        v404 = *(_QWORD *)(v403 + 128);
        if ( v404 )
        {
          v405 = *(_DWORD *)(v404 + 8);
          while ( v405 )
          {
            v406 = v405;
            v405 = _InterlockedCompareExchange((volatile signed __int32 *)(v404 + 8), v405 + 1, v405);
            if ( v406 == v405 )
            {
              v407 = *(std::_Ref_count_base **)(v403 + 120);
              v668[0] = v407;
              v408 = *(std::_Ref_count_base **)(v403 + 128);
              v668[1] = v408;
              goto LABEL_249;
            }
          }
        }
        v407 = v668[0];
        v408 = v668[1];
LABEL_249:
        if ( v407 )
        {
          v409 = *(void (__fastcall ***)(std::_Ref_count_base *, void **))v407;
          v410 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v663 = 0;
          v411 = *(_QWORD *)(v410 + 112);
          if ( v411 )
            _InterlockedIncrement((volatile signed __int32 *)(v411 + 8));
          v663[0] = *(void **)(v410 + 104);
          v663[1] = *(void **)(v410 + 112);
          (*v409)(v407, v663);
        }
        if ( v408 )
          std::_Ref_count_base::_Decref(v408);
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v662[0] = (std::_Ref_count_base *)v577;
        v412 = std::string::string(v655, "\"");
        v413 = std::string::string(v647, "\"");
        v414 = std::string::string(v641, ":");
        v415 = std::string::string(v642, "\"");
        v416 = std::string::string(v643, "\"");
        v417 = std::operator+<char>(v644, v416, "reason");
        LOBYTE(v418) = (_BYTE)v568;
        std::string::string(v620, v418, v417, v415);
        LOBYTE(v419) = (_BYTE)v568;
        std::string::string(v617, v419, v620, v414);
        LOBYTE(v420) = (_BYTE)v568;
        std::string::string(v618, v420, v617, v413);
        v421 = std::operator+<char>(v645, v618, &v679);
        LOBYTE(v422) = (_BYTE)v568;
        std::string::string(v577, v422, v421, v412);
        v668[0] = (std::_Ref_count_base *)v613;
        std::_Integral_to_string<char,unsigned int>(v619, *((unsigned int *)this + 373));
        v423 = std::string::string(v621, ":");
        v424 = std::string::string(v623, "\"");
        v425 = std::string::string(v624, "\"");
        v426 = std::operator+<char>(v625, v425, "NonIceDoR");
        LOBYTE(v427) = (_BYTE)v568;
        std::string::string(v592, v427, v426, v424);
        LOBYTE(v428) = (_BYTE)v568;
        std::string::string(v593, v428, v592, v423);
        LOBYTE(v429) = (_BYTE)v568;
        std::string::string(v613, v429, v593, v619);
        v611 = v612;
        std::_Integral_to_string<char,unsigned int>(v594, *((unsigned int *)this + 372));
        v430 = std::string::string(v626, ":");
        v431 = std::string::string(v627, "\"");
        v432 = std::string::string(v628, "\"");
        v433 = std::operator+<char>(v622, v432, "IceDoR");
        LOBYTE(v434) = (_BYTE)v568;
        std::string::string(v595, v434, v433, v431);
        LOBYTE(v435) = (_BYTE)v568;
        std::string::string(v596, v435, v595, v430);
        LOBYTE(v436) = (_BYTE)v568;
        std::string::string(v612, v436, v596, v594);
        v605 = v615;
        std::_Integral_to_string<char,unsigned int>(v597, *((unsigned int *)this + 553));
        v437 = std::string::string(v610, ":");
        v438 = std::string::string(v639, "\"");
        v439 = std::string::string(v638, "\"");
        v440 = std::operator+<char>(v637, v439, "CurrentActiveNumLinks");
        LOBYTE(v441) = (_BYTE)v568;
        std::string::string(v598, v441, v440, v438);
        LOBYTE(v442) = (_BYTE)v568;
        std::string::string(v599, v442, v598, v437);
        LOBYTE(v443) = (_BYTE)v568;
        std::string::string(v615, v443, v599, v597);
        v573 = v614;
        v444 = std::string::string(v636, "\"");
        v445 = v671;
        if ( v672 > 0xF )
          v445 = (_QWORD *)v671[0];
        v446 = std::string::string(v635, "\"");
        v447 = std::string::string(v634, ":");
        v448 = std::string::string(v633, "\"");
        v449 = std::string::string(v632, "\"");
        v450 = std::operator+<char>(v631, v449, "SuspendLinkType");
        LOBYTE(v451) = (_BYTE)v568;
        std::string::string(v600, v451, v450, v448);
        LOBYTE(v452) = (_BYTE)v568;
        std::string::string(v601, v452, v600, v447);
        LOBYTE(v453) = (_BYTE)v568;
        std::string::string(v602, v453, v601, v446);
        v454 = std::operator+<char>(v630, v602, v445);
        LOBYTE(v455) = (_BYTE)v568;
        std::string::string(v614, v455, v454, v444);
        v576 = (__int64)v587;
        std::_Integral_to_string<char,int>(v603, *((unsigned __int16 *)v570 + 1));
        v456 = std::string::string(v629, ":");
        v457 = std::string::string(v616, "\"");
        v458 = std::string::string(v648, "\"");
        v459 = std::operator+<char>(v649, v458, "SuspendLinkId");
        LOBYTE(v460) = (_BYTE)v568;
        std::string::string(v604, v460, v459, v457);
        LOBYTE(v461) = (_BYTE)v568;
        std::string::string(v578, v461, v604, v456);
        LOBYTE(v462) = (_BYTE)v568;
        std::string::string(v587, v462, v578, v603);
        v571 = (__int64 *)std::string::string(v650, "\"");
        v463 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v651, v661, 0, 6);
        v464 = v463;
        if ( v463[3] > 0xFu )
          v464 = (_QWORD *)*v463;
        v465 = std::string::string(v646, "\"");
        v466 = std::string::string(v652, ":");
        v467 = std::string::string(v653, "\"");
        v468 = std::string::string(v654, "\"");
        v469 = std::operator+<char>(v640, v468, "Direction");
        LOBYTE(v470) = (_BYTE)v568;
        std::string::string(v606, v470, v469, v467);
        LOBYTE(v471) = (_BYTE)v568;
        std::string::string(v607, v471, v606, v466);
        LOBYTE(v472) = (_BYTE)v568;
        std::string::string(v608, v472, v607, v465);
        v473 = std::operator+<char>(&v579, v608, v464);
        LOBYTE(v474) = (_BYTE)v568;
        std::string::string(v609, v474, v473, v571);
        v475 = (char *)v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          v475 = v666[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v663,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSuspend",
          v475,
          (__int64)v609,
          (__int64)v587,
          (__int64)v614,
          (__int64)v615,
          (__int64)v612,
          (__int64)v613,
          (__int64)v577);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v606);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v592);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v655);
        v2 = v570;
        v5 = v569;
      }
      v476 = (volatile signed __int32 *)v663[1];
      if ( v663[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v476)(v476);
          if ( _InterlockedExchangeAdd(v476 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v476 + 8LL))(v476);
        }
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v477 = (__int64 *)&v679;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v477 = (__int64 *)v679;
        v571 = v477;
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v570) = *((_DWORD *)this + 372);
        LODWORD(v574) = *((_DWORD *)this + 553);
        v478 = v671;
        if ( v672 > 0xF )
          v478 = (__int64 *)v671[0];
        v573 = v478;
        LOWORD(v568) = *((_WORD *)v2 + 1);
        v479 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v579, v661, 0, 6);
        v482 = (__int64)v479;
        if ( (unsigned __int64)v479[3] > 0xF )
          v482 = *v479;
        v483 = v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          LODWORD(v483) = v666[0];
        std::string::string(
          v577,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s",
          v480,
          v481,
          (_DWORD)v561,
          v562,
          (_DWORD)v563,
          v564,
          v565,
          v566);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
          (unsigned int)v663,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v577,
          (_DWORD)v483,
          v482,
          (char)v568,
          (__int64)v573,
          (char)v574,
          (char)v570,
          p_Str,
          (__int64)v571);
        std::string::_Tidy_deallocate(v577);
        std::string::_Tidy_deallocate(&v579);
      }
      goto LABEL_311;
    case 3:
      v337 = std::operator+<char>(&v579, v666, "LinkRemoved");
      if ( v666 != (char **)v337 )
      {
        std::string::_Tidy_deallocate(v666);
        *(_OWORD *)v666 = *(_OWORD *)v337;
        v667 = *(__m128i *)(v337 + 16);
        *(_QWORD *)(v337 + 16) = 0;
        *(_QWORD *)(v337 + 24) = 15;
        *(_BYTE *)v337 = 0;
      }
      std::string::_Tidy_deallocate(&v579);
      if ( !v5 )
      {
        *(_OWORD *)v668 = 0;
        std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(*((_QWORD *)v2 + 1) + 120LL, v668);
        v338 = v668[0];
        if ( v668[0] )
        {
          v339 = *(_QWORD *)v668[0];
          v340 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v663 = 0;
          v341 = *(_QWORD *)(v340 + 112);
          if ( v341 )
            _InterlockedIncrement((volatile signed __int32 *)(v341 + 8));
          v663[0] = *(void **)(v340 + 104);
          v663[1] = *(void **)(v340 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, void **))(v339 + 16))(v338, v663);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v668);
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v662[0] = (std::_Ref_count_base *)v577;
        std::_Integral_to_string<char,unsigned int>(v592, *((unsigned int *)this + 373));
        v342 = std::string::string(v621, ":");
        v343 = std::string::string(v623, "\"");
        v344 = std::string::string(v624, "\"");
        v345 = std::operator+<char>(v625, v344, "NonIceDoR");
        LOBYTE(v346) = (_BYTE)v568;
        std::string::string(v593, v346, v345, v343);
        LOBYTE(v347) = (_BYTE)v568;
        std::string::string(v594, v347, v593, v342);
        LOBYTE(v348) = (_BYTE)v568;
        std::string::string(v577, v348, v594, v592);
        v668[0] = (std::_Ref_count_base *)v613;
        std::_Integral_to_string<char,unsigned int>(v595, *((unsigned int *)this + 372));
        v349 = std::string::string(v626, ":");
        v350 = std::string::string(v627, "\"");
        v351 = std::string::string(v628, "\"");
        v352 = std::operator+<char>(v622, v351, "IceDoR");
        LOBYTE(v353) = (_BYTE)v568;
        std::string::string(v596, v353, v352, v350);
        LOBYTE(v354) = (_BYTE)v568;
        std::string::string(v597, v354, v596, v349);
        LOBYTE(v355) = (_BYTE)v568;
        std::string::string(v613, v355, v597, v595);
        v611 = v612;
        std::_Integral_to_string<char,unsigned int>(v598, *((unsigned int *)this + 553));
        v356 = std::string::string(v610, ":");
        v357 = std::string::string(v639, "\"");
        v358 = std::string::string(v638, "\"");
        v359 = std::operator+<char>(v637, v358, "CurrentActiveNumLinks");
        LOBYTE(v360) = (_BYTE)v568;
        std::string::string(v599, v360, v359, v357);
        LOBYTE(v361) = (_BYTE)v568;
        std::string::string(v600, v361, v599, v356);
        LOBYTE(v362) = (_BYTE)v568;
        std::string::string(v612, v362, v600, v598);
        v605 = v615;
        v363 = std::string::string(v636, "\"");
        v364 = v671;
        if ( v672 > 0xF )
          v364 = (_QWORD *)v671[0];
        v365 = std::string::string(v635, "\"");
        v366 = std::string::string(v634, ":");
        v367 = std::string::string(v633, "\"");
        v368 = std::string::string(v632, "\"");
        v369 = std::operator+<char>(v631, v368, "RemovedLinkType");
        LOBYTE(v370) = (_BYTE)v568;
        std::string::string(v601, v370, v369, v367);
        LOBYTE(v371) = (_BYTE)v568;
        std::string::string(v602, v371, v601, v366);
        LOBYTE(v372) = (_BYTE)v568;
        std::string::string(v603, v372, v602, v365);
        v373 = std::operator+<char>(v630, v603, v364);
        LOBYTE(v374) = (_BYTE)v568;
        std::string::string(v615, v374, v373, v363);
        v573 = v614;
        std::_Integral_to_string<char,int>(v604, *((unsigned __int16 *)v570 + 1));
        v375 = std::string::string(v629, ":");
        v376 = std::string::string(v616, "\"");
        v377 = std::string::string(v648, "\"");
        v378 = std::operator+<char>(v649, v377, "RemovedLinkId");
        LOBYTE(v379) = (_BYTE)v568;
        std::string::string(v578, v379, v378, v376);
        LOBYTE(v380) = (_BYTE)v568;
        std::string::string(v606, v380, v578, v375);
        LOBYTE(v381) = (_BYTE)v568;
        std::string::string(v614, v381, v606, v604);
        v571 = (__int64 *)std::string::string(v650, "\"");
        v382 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v651, v661, 0, 6);
        v383 = v382;
        if ( v382[3] > 0xFu )
          v383 = (_QWORD *)*v382;
        v384 = std::string::string(v646, "\"");
        v385 = std::string::string(v652, ":");
        v386 = std::string::string(v653, "\"");
        v387 = std::string::string(v654, "\"");
        v388 = std::operator+<char>(v640, v387, "Direction");
        LOBYTE(v389) = (_BYTE)v568;
        std::string::string(v607, v389, v388, v386);
        LOBYTE(v390) = (_BYTE)v568;
        std::string::string(v608, v390, v607, v385);
        LOBYTE(v391) = (_BYTE)v568;
        std::string::string(v609, v391, v608, v384);
        v392 = std::operator+<char>(&v579, v609, v383);
        LOBYTE(v393) = (_BYTE)v568;
        std::string::string(v587, v393, v392, v571);
        v394 = (char *)v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          v394 = v666[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v663,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkRemove",
          v394,
          (__int64)v587,
          (__int64)v614,
          (__int64)v615,
          (__int64)v612,
          (__int64)v613,
          (__int64)v577);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v606);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v592);
        v2 = v570;
        v5 = v569;
      }
      v395 = (volatile signed __int32 *)v663[1];
      if ( v663[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v395)(v395);
          if ( _InterlockedExchangeAdd(v395 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v395 + 8LL))(v395);
        }
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v570) = *((_DWORD *)this + 372);
        LODWORD(v574) = *((_DWORD *)this + 553);
        v396 = v671;
        if ( v672 > 0xF )
          v396 = (__int64 *)v671[0];
        v571 = v396;
        LOWORD(v568) = *((_WORD *)v2 + 1);
        v397 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v579, v661, 0, 6);
        v400 = (__int64)v397;
        if ( (unsigned __int64)v397[3] > 0xF )
          v400 = *v397;
        v401 = v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          LODWORD(v401) = v666[0];
        std::string::string(
          v577,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
          v398,
          v399,
          (_DWORD)v561,
          v562,
          (_DWORD)v563,
          v564,
          v565);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
          (unsigned int)v663,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v577,
          (_DWORD)v401,
          v400,
          (char)v568,
          (__int64)v571,
          (char)v574,
          (char)v570,
          p_Str);
        std::string::_Tidy_deallocate(v577);
        std::string::_Tidy_deallocate(&v579);
      }
LABEL_311:
      v76 = (volatile signed __int32 *)v663[1];
LABEL_312:
      if ( v76 )
      {
        if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
          if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
        }
      }
      goto LABEL_316;
    case 4:
      v255 = std::operator+<char>(&v579, v666, "LinkSuspended");
      if ( v666 != (char **)v255 )
      {
        std::string::_Tidy_deallocate(v666);
        *(_OWORD *)v666 = *(_OWORD *)v255;
        v667 = *(__m128i *)(v255 + 16);
        *(_QWORD *)(v255 + 16) = 0;
        *(_QWORD *)(v255 + 24) = 15;
        *(_BYTE *)v255 = 0;
      }
      std::string::_Tidy_deallocate(&v579);
      std::string::assign(&v679, "linkSuspendedDueToTimeout");
      if ( !v5 )
      {
        v256 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v668 = 0;
        v257 = *(_QWORD *)(v256 + 128);
        if ( v257 )
        {
          v258 = *(_DWORD *)(v257 + 8);
          while ( v258 )
          {
            v259 = v258;
            v258 = _InterlockedCompareExchange((volatile signed __int32 *)(v257 + 8), v258 + 1, v258);
            if ( v259 == v258 )
            {
              v260 = *(std::_Ref_count_base **)(v256 + 120);
              v668[0] = v260;
              v261 = *(std::_Ref_count_base **)(v256 + 128);
              v668[1] = v261;
              goto LABEL_178;
            }
          }
        }
        v260 = v668[0];
        v261 = v668[1];
LABEL_178:
        if ( v260 )
        {
          v262 = *(void (__fastcall ***)(std::_Ref_count_base *, void **))v260;
          v263 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v663 = 0;
          v264 = *(_QWORD *)(v263 + 112);
          if ( v264 )
            _InterlockedIncrement((volatile signed __int32 *)(v264 + 8));
          v663[0] = *(void **)(v263 + 104);
          v663[1] = *(void **)(v263 + 112);
          (*v262)(v260, v663);
        }
        if ( v261 )
          std::_Ref_count_base::_Decref(v261);
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v662[0] = (std::_Ref_count_base *)v577;
        v265 = std::string::string(v655, "\"");
        v266 = std::string::string(v647, "\"");
        v267 = std::string::string(v641, ":");
        v268 = std::string::string(v642, "\"");
        v269 = std::string::string(v643, "\"");
        v270 = std::operator+<char>(v644, v269, "reason");
        LOBYTE(v271) = (_BYTE)v568;
        std::string::string(v620, v271, v270, v268);
        LOBYTE(v272) = (_BYTE)v568;
        std::string::string(v617, v272, v620, v267);
        LOBYTE(v273) = (_BYTE)v568;
        std::string::string(v618, v273, v617, v266);
        v274 = std::operator+<char>(v645, v618, &v679);
        LOBYTE(v275) = (_BYTE)v568;
        std::string::string(v577, v275, v274, v265);
        v668[0] = (std::_Ref_count_base *)v613;
        std::_Integral_to_string<char,unsigned int>(v619, *((unsigned int *)this + 373));
        v276 = std::string::string(v621, ":");
        v277 = std::string::string(v623, "\"");
        v278 = std::string::string(v624, "\"");
        v279 = std::operator+<char>(v625, v278, "NonIceDoR");
        LOBYTE(v280) = (_BYTE)v568;
        std::string::string(v592, v280, v279, v277);
        LOBYTE(v281) = (_BYTE)v568;
        std::string::string(v593, v281, v592, v276);
        LOBYTE(v282) = (_BYTE)v568;
        std::string::string(v613, v282, v593, v619);
        v611 = v612;
        std::_Integral_to_string<char,unsigned int>(v594, *((unsigned int *)this + 372));
        v283 = std::string::string(v626, ":");
        v284 = std::string::string(v627, "\"");
        v285 = std::string::string(v628, "\"");
        v286 = std::operator+<char>(v622, v285, "IceDoR");
        LOBYTE(v287) = (_BYTE)v568;
        std::string::string(v595, v287, v286, v284);
        LOBYTE(v288) = (_BYTE)v568;
        std::string::string(v596, v288, v595, v283);
        LOBYTE(v289) = (_BYTE)v568;
        std::string::string(v612, v289, v596, v594);
        v605 = v615;
        std::_Integral_to_string<char,unsigned int>(v597, *((unsigned int *)this + 553));
        v290 = std::string::string(v610, ":");
        v291 = std::string::string(v639, "\"");
        v292 = std::string::string(v638, "\"");
        v293 = std::operator+<char>(v637, v292, "CurrentActiveNumLinks");
        LOBYTE(v294) = (_BYTE)v568;
        std::string::string(v598, v294, v293, v291);
        LOBYTE(v295) = (_BYTE)v568;
        std::string::string(v599, v295, v598, v290);
        LOBYTE(v296) = (_BYTE)v568;
        std::string::string(v615, v296, v599, v597);
        v573 = v614;
        v297 = std::string::string(v636, "\"");
        v298 = v671;
        if ( v672 > 0xF )
          v298 = (_QWORD *)v671[0];
        v299 = std::string::string(v635, "\"");
        v300 = std::string::string(v634, ":");
        v301 = std::string::string(v633, "\"");
        v302 = std::string::string(v632, "\"");
        v303 = std::operator+<char>(v631, v302, "SuspendLinkType");
        LOBYTE(v304) = (_BYTE)v568;
        std::string::string(v600, v304, v303, v301);
        LOBYTE(v305) = (_BYTE)v568;
        std::string::string(v601, v305, v600, v300);
        LOBYTE(v306) = (_BYTE)v568;
        std::string::string(v602, v306, v601, v299);
        v307 = std::operator+<char>(v630, v602, v298);
        LOBYTE(v308) = (_BYTE)v568;
        std::string::string(v614, v308, v307, v297);
        v576 = (__int64)v587;
        std::_Integral_to_string<char,int>(v603, *((unsigned __int16 *)v570 + 1));
        v309 = std::string::string(v629, ":");
        v310 = std::string::string(v616, "\"");
        v311 = std::string::string(v648, "\"");
        v312 = std::operator+<char>(v649, v311, "SuspendLinkId");
        LOBYTE(v313) = (_BYTE)v568;
        std::string::string(v604, v313, v312, v310);
        v4 = -1024;
        LOBYTE(v314) = (_BYTE)v568;
        std::string::string(v578, v314, v604, v309);
        LOBYTE(v315) = (_BYTE)v568;
        std::string::string(v587, v315, v578, v603);
        v571 = (__int64 *)std::string::string(v650, "\"");
        v316 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v651, v661, 0, 6);
        v317 = v316;
        if ( v316[3] > 0xFu )
          v317 = (_QWORD *)*v316;
        v318 = std::string::string(v646, "\"");
        v319 = std::string::string(v652, ":");
        v320 = std::string::string(v653, "\"");
        v321 = std::string::string(v654, "\"");
        v322 = std::operator+<char>(v640, v321, "Direction");
        LOBYTE(v323) = (_BYTE)v568;
        std::string::string(v606, v323, v322, v320);
        LOBYTE(v324) = (_BYTE)v568;
        std::string::string(v607, v324, v606, v319);
        LOBYTE(v325) = (_BYTE)v568;
        std::string::string(v608, v325, v607, v318);
        v326 = std::operator+<char>(&v579, v608, v317);
        LOBYTE(v327) = (_BYTE)v568;
        std::string::string(v609, v327, v326, v571);
        v328 = (char *)v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          v328 = v666[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v663,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSuspend",
          v328,
          (__int64)v609,
          (__int64)v587,
          (__int64)v614,
          (__int64)v615,
          (__int64)v612,
          (__int64)v613,
          (__int64)v577);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v606);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v592);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v655);
        v2 = v570;
        v5 = v569;
      }
      v329 = (volatile signed __int32 *)v663[1];
      if ( v663[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v329)(v329);
          if ( _InterlockedExchangeAdd(v329 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v329 + 8LL))(v329);
        }
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v330 = (__int64 *)&v679;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v330 = (__int64 *)v679;
        v571 = v330;
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v570) = *((_DWORD *)this + 372);
        LODWORD(v574) = *((_DWORD *)this + 553);
        v331 = v671;
        if ( v672 > 0xF )
          v331 = (__int64 *)v671[0];
        v573 = v331;
        LOWORD(v568) = *((_WORD *)v2 + 1);
        v332 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v579, v661, 0, 6);
        v335 = (__int64)v332;
        if ( (unsigned __int64)v332[3] > 0xF )
          v335 = *v332;
        v336 = v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          LODWORD(v336) = v666[0];
        std::string::string(
          v577,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s",
          v333,
          v334,
          (_DWORD)v561,
          v562,
          (_DWORD)v563,
          v564,
          v565,
          v566);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
          (unsigned int)v663,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v577,
          (_DWORD)v336,
          v335,
          (char)v568,
          (__int64)v573,
          (char)v574,
          (char)v570,
          p_Str,
          (__int64)v571);
        std::string::_Tidy_deallocate(v577);
        std::string::_Tidy_deallocate(&v579);
      }
      goto LABEL_311;
    case 5:
      LODWORD(v576) = 0;
      v166 = *((_QWORD *)v2 + 1);
      if ( v661[0] )
      {
        LODWORD(v575) = *(_DWORD *)(v166 + 288);
        if ( (_DWORD)v575 == 1 )
          LODWORD(v576) = (*(_QWORD *)(v166 + 264) - *((_QWORD *)this + 376)) / 1000LL;
      }
      else
      {
        LODWORD(v575) = *(_DWORD *)(v166 + 292);
        if ( (_DWORD)v575 == 1 )
          v576 = (*(_QWORD *)(v166 + 272) - *((_QWORD *)this + 376)) / 1000LL;
      }
      v167 = std::operator+<char>(v616, v666, "LinkRemovedAtClose");
      if ( v666 != (char **)v167 )
      {
        std::string::_Tidy_deallocate(v666);
        *(_OWORD *)v666 = *(_OWORD *)v167;
        v667 = *(__m128i *)(v167 + 16);
        *(_QWORD *)(v167 + 16) = 0;
        *(_QWORD *)(v167 + 24) = 15;
        *(_BYTE *)v167 = 0;
      }
      std::string::_Tidy_deallocate(v616);
      if ( !v5 )
      {
        v168 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v662 = 0;
        v169 = *(_QWORD *)(v168 + 128);
        if ( v169 )
        {
          v170 = *(_DWORD *)(v169 + 8);
          while ( v170 )
          {
            v171 = v170;
            v170 = _InterlockedCompareExchange((volatile signed __int32 *)(v169 + 8), v170 + 1, v170);
            if ( v171 == v170 )
            {
              v172 = *(std::_Ref_count_base **)(v168 + 120);
              v662[0] = v172;
              v173 = *(std::_Ref_count_base **)(v168 + 128);
              v662[1] = v173;
              goto LABEL_136;
            }
          }
        }
        v172 = v662[0];
        v173 = v662[1];
LABEL_136:
        if ( v172 )
        {
          v174 = *(_QWORD *)v172;
          v175 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v668 = 0;
          v176 = *(_QWORD *)(v175 + 112);
          if ( v176 )
            _InterlockedIncrement((volatile signed __int32 *)(v176 + 8));
          v668[0] = *(std::_Ref_count_base **)(v175 + 104);
          v668[1] = *(std::_Ref_count_base **)(v175 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v174 + 16))(v172, v668);
        }
        if ( v173 )
          std::_Ref_count_base::_Decref(v173);
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        v571 = v587;
        std::_Integral_to_string<char,unsigned int>(v577, *((unsigned int *)this + 373));
        v177 = std::string::string(&v579, ":");
        v178 = std::string::string(v640, "\"");
        v179 = std::string::string(v654, "\"");
        v180 = std::operator+<char>(v653, v179, "NonIceDoR");
        LOBYTE(v181) = (_BYTE)v568;
        std::string::string(v613, v181, v180, v178);
        LOBYTE(v182) = (_BYTE)v568;
        std::string::string(v612, v182, v613, v177);
        LOBYTE(v183) = (_BYTE)v568;
        std::string::string(v587, v183, v612, v577);
        v574 = v609;
        std::_Integral_to_string<char,unsigned int>(v615, *((unsigned int *)this + 372));
        v184 = std::string::string(v652, ":");
        v185 = std::string::string(v646, "\"");
        v186 = std::string::string(v651, "\"");
        v187 = std::operator+<char>(v650, v186, "IceDoR");
        LOBYTE(v188) = (_BYTE)v568;
        std::string::string(v614, v188, v187, v185);
        LOBYTE(v189) = (_BYTE)v568;
        std::string::string(v677, v189, v614, v184);
        LOBYTE(v190) = (_BYTE)v568;
        std::string::string(v609, v190, v677, v615);
        v568 = v608;
        std::_Integral_to_string<char,unsigned int>(&Str, *((unsigned int *)this + 553));
        v191 = std::string::string(v649, ":");
        v192 = std::string::string(v648, "\"");
        v193 = std::string::string(v658, "\"");
        v194 = std::operator+<char>(v660, v193, "CurrentActiveNumLinks");
        LOBYTE(v195) = (unsigned __int8)v608;
        std::string::string(&v583, v195, v194, v192);
        LOBYTE(v196) = (unsigned __int8)v608;
        std::string::string(&v673, v196, &v583, v191);
        LOBYTE(v197) = (unsigned __int8)v608;
        std::string::string(v608, v197, &v673, &Str);
        v605 = v607;
        v198 = std::string::string(v659, "\"");
        v199 = v671;
        if ( v672 > 0xF )
          v199 = (_QWORD *)v671[0];
        v200 = std::string::string(v657, "\"");
        v201 = std::string::string(v656, ":");
        v202 = std::string::string(v655, "\"");
        v203 = std::string::string(v647, "\"");
        v204 = std::operator+<char>(v641, v203, "RemovedLinkType");
        LOBYTE(v205) = (_BYTE)v568;
        std::string::string(v620, v205, v204, v202);
        LOBYTE(v206) = (_BYTE)v568;
        std::string::string(v617, v206, v620, v201);
        LOBYTE(v207) = (_BYTE)v568;
        std::string::string(v618, v207, v617, v200);
        v208 = std::operator+<char>(v642, v618, v199);
        LOBYTE(v209) = (_BYTE)v568;
        std::string::string(v607, v209, v208, v198);
        v611 = v606;
        std::_Integral_to_string<char,int>(v619, *((unsigned __int16 *)v570 + 1));
        v210 = std::string::string(v643, ":");
        v211 = std::string::string(v644, "\"");
        v212 = std::string::string(v645, "\"");
        v213 = std::operator+<char>(v621, v212, "RemovedLinkId");
        LOBYTE(v214) = (_BYTE)v568;
        std::string::string(v592, v214, v213, v211);
        LOBYTE(v215) = (_BYTE)v568;
        std::string::string(v593, v215, v592, v210);
        LOBYTE(v216) = (_BYTE)v568;
        std::string::string(v606, v216, v593, v619);
        v668[0] = (std::_Ref_count_base *)v578;
        std::_Integral_to_string<char,int>(v594, (unsigned int)v576);
        v217 = std::string::string(v623, ":");
        v218 = std::string::string(v624, "\"");
        v219 = std::string::string(v625, "\"");
        v220 = std::operator+<char>(v626, v219, "SuspendTimeInSec");
        LOBYTE(v221) = (_BYTE)v568;
        std::string::string(v595, v221, v220, v218);
        LOBYTE(v222) = (_BYTE)v568;
        std::string::string(v596, v222, v595, v217);
        LOBYTE(v223) = (_BYTE)v568;
        std::string::string(v578, v223, v596, v594);
        v662[0] = (std::_Ref_count_base *)v604;
        v573 = (__int64 *)std::string::string(v627, "\"");
        v224 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkDataV3::State>(v628, &v575, 0, 6);
        p_Str = v224;
        if ( *(_QWORD *)(v224 + 24) > 0xFu )
          p_Str = *(_QWORD *)v224;
        v225 = std::string::string(v622, "\"");
        v226 = std::string::string(v610, ":");
        v227 = std::string::string(v639, "\"");
        v228 = std::string::string(v638, "\"");
        v229 = std::operator+<char>(v637, v228, "StateBeforeRemove");
        LOBYTE(v230) = (_BYTE)v568;
        std::string::string(v597, v230, v229, v227);
        LOBYTE(v231) = (_BYTE)v568;
        std::string::string(v598, v231, v597, v226);
        LOBYTE(v232) = (_BYTE)v568;
        std::string::string(v599, v232, v598, v225);
        v233 = std::operator+<char>(v636, v599, p_Str);
        LOBYTE(v234) = (_BYTE)v568;
        std::string::string(v604, v234, v233, v573);
        v573 = (__int64 *)std::string::string(v635, "\"");
        v235 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v634, v661, 0, 6);
        p_Str = v235;
        if ( *(_QWORD *)(v235 + 24) > 0xFu )
          p_Str = *(_QWORD *)v235;
        v236 = std::string::string(v633, "\"");
        v237 = std::string::string(v632, ":");
        v238 = std::string::string(v631, "\"");
        v239 = std::string::string(v630, "\"");
        v240 = std::operator+<char>(v629, v239, "Direction");
        LOBYTE(v241) = (_BYTE)v568;
        std::string::string(v600, v241, v240, v238);
        LOBYTE(v242) = (_BYTE)v568;
        std::string::string(v601, v242, v600, v237);
        LOBYTE(v243) = (_BYTE)v568;
        std::string::string(v602, v243, v601, v236);
        v244 = std::operator+<char>(v616, v602, p_Str);
        LOBYTE(v245) = (_BYTE)v568;
        std::string::string(v603, v245, v244, v573);
        v246 = (char *)v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          v246 = v666[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v663,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkRemove",
          v246,
          (__int64)v603,
          (__int64)v604,
          (__int64)v578,
          (__int64)v606,
          (__int64)v607,
          (__int64)v608,
          (__int64)v609,
          (__int64)v587);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v592);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v656);
        std::string::_Tidy_deallocate(v657);
        std::string::_Tidy_deallocate(v659);
        std::string::_Tidy_deallocate(&v673);
        std::string::_Tidy_deallocate(&v583);
        std::string::_Tidy_deallocate(v660);
        std::string::_Tidy_deallocate(v658);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(&Str);
        std::string::_Tidy_deallocate(v677);
        std::string::_Tidy_deallocate(v614);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v615);
        std::string::_Tidy_deallocate(v612);
        std::string::_Tidy_deallocate(v613);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v577);
        v2 = v570;
        v5 = v569;
      }
      v247 = (volatile signed __int32 *)v663[1];
      if ( v663[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v247)(v247);
          if ( _InterlockedExchangeAdd(v247 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v247 + 8LL))(v247);
        }
      }
      *(_OWORD *)v663 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
      if ( v663[0] && *((_BYTE *)v663[0] + 128) )
      {
        LODWORD(v570) = *((_DWORD *)this + 373);
        LODWORD(v574) = *((_DWORD *)this + 372);
        LODWORD(p_Str) = *((_DWORD *)this + 553);
        v248 = v671;
        if ( v672 > 0xF )
          v248 = (__int64 *)v671[0];
        v571 = v248;
        LOWORD(v568) = *((_WORD *)v2 + 1);
        v249 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v640, v661, 0, 6);
        v573 = v249;
        if ( (unsigned __int64)v249[3] > 0xF )
          v573 = (__int64 *)*v249;
        v250 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkDataV3::State>(&v579, &v575, 0, 6);
        v253 = (__int64)v250;
        if ( (unsigned __int64)v250[3] > 0xF )
          v253 = *v250;
        v254 = v666;
        if ( v667.m128i_i64[1] > 0xFuLL )
          LODWORD(v254) = v666[0];
        std::string::string(
          v577,
          "Checkpoint.SMILES.%s(%s|%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, suspendTimeInSec=%d",
          v251,
          v252,
          v561,
          (_DWORD)v562,
          v563,
          v564,
          v565,
          (_DWORD)v566,
          v567);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,int>(
          (unsigned int)v663,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v577,
          (_DWORD)v254,
          v253,
          (__int64)v573,
          (char)v568,
          (__int64)v571,
          p_Str,
          (char)v574,
          (char)v570,
          v576);
        std::string::_Tidy_deallocate(v577);
        std::string::_Tidy_deallocate(&v579);
        std::string::_Tidy_deallocate(v640);
      }
      goto LABEL_311;
  }
  if ( *(_BYTE *)v2 != 6 )
  {
    if ( *(_BYTE *)v2 != 7 )
      goto LABEL_316;
    v6 = std::operator+<char>(v577, v666, "LinkRemovedTimeout");
    if ( v666 != (char **)v6 )
    {
      std::string::_Tidy_deallocate(v666);
      *(_OWORD *)v666 = *(_OWORD *)v6;
      v667 = *(__m128i *)(v6 + 16);
      *(_QWORD *)(v6 + 16) = 0;
      *(_QWORD *)(v6 + 24) = 15;
      *(_BYTE *)v6 = 0;
    }
    std::string::_Tidy_deallocate(v577);
    if ( !v5 )
    {
      v7 = *((_QWORD *)v2 + 1);
      *(_OWORD *)v662 = 0;
      v8 = *(volatile signed __int32 **)(v7 + 128);
      if ( v8 )
      {
        v9 = *((_DWORD *)v8 + 2);
        while ( v9 )
        {
          v10 = v9;
          v9 = _InterlockedCompareExchange(v8 + 2, v9 + 1, v9);
          if ( v10 == v9 )
          {
            v11 = *(std::_Ref_count_base **)(v7 + 120);
            v662[0] = v11;
            v662[1] = *(std::_Ref_count_base **)(v7 + 128);
            goto LABEL_18;
          }
        }
      }
      v11 = v662[0];
LABEL_18:
      if ( v11 )
      {
        v12 = *(_QWORD *)v11;
        v13 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v668 = 0;
        v14 = *(_QWORD *)(v13 + 112);
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v668[0] = *(std::_Ref_count_base **)(v13 + 104);
        v668[1] = *(std::_Ref_count_base **)(v13 + 112);
        (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v12 + 16))(v11, v668);
      }
      if ( *((_BYTE *)this + 2688) )
      {
        LODWORD(v673) = 2;
        v674 = (void *)&Str1;
        v675 = 0;
        LOBYTE(v676) = 0;
        LOBYTE(v568) = 0;
        LODWORD(v583) = 2;
        v584 = "link removed due to timeout";
        v585 = 27;
        v586 = 0;
        LODWORD(Str) = 2;
        v589 = "smiles";
        v590 = 6;
        LOBYTE(v591) = 0;
        LODWORD(v668[0]) = 2;
        v668[1] = (std::_Ref_count_base *)"a link is removed after timeout";
        v669 = 31;
        v670 = 0;
        LODWORD(v663[0]) = 2;
        v663[1] = "LinkRemoveTimeout";
        v664 = 17;
        v665 = 0;
        LODWORD(v575) = 1460;
        v15 = "client";
        if ( *((_BYTE *)this + 1112) )
          v15 = "stack";
        LODWORD(v677[0]) = 2;
        v677[1] = (void *)v15;
        v678.m128i_i64[0] = strlen(v15);
        v678.m128i_i8[8] = 0;
        v4 = 63;
        LODWORD(v574) = *((unsigned __int16 *)v2 + 1);
        Microsoft::Basix::Instrumentation::MultiLinkError::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
          (_DWORD)this + 2816,
          (_DWORD)this + 2696,
          (unsigned int)&v574,
          (unsigned int)v677,
          (__int64)&v575,
          (__int64)v663,
          (__int64)v668,
          (__int64)&Str,
          (__int64)&v583,
          (__int64)&v568,
          (__int64)&v673);
      }
      if ( (v4 & 0x20) != 0 )
      {
        v4 &= ~0x20u;
        if ( v678.m128i_i8[8] )
          operator delete(v677[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 0x10) != 0 )
      {
        v4 &= ~0x10u;
        if ( v665 )
          operator delete(v663[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 8) != 0 )
      {
        v4 &= ~8u;
        if ( v670 )
          operator delete(v668[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 4) != 0 )
      {
        v4 &= ~4u;
        if ( (_BYTE)v591 )
          operator delete(v589, (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        if ( v586 )
          operator delete(v584, (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        if ( (_BYTE)v676 )
          operator delete(v674, (const struct std::nothrow_t *)v8);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v662);
    }
    *(_OWORD *)v662 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v662);
    if ( v662[0] && *((_BYTE *)v662[0] + 128) )
    {
      v571 = &v673;
      std::_Integral_to_string<char,unsigned int>(v578, *((unsigned int *)this + 373));
      v16 = std::string::string(v610, ":");
      v17 = std::string::string(v622, "\"");
      v18 = std::string::string(v628, "\"");
      v19 = std::operator+<char>(v627, v18, "NonIceDoR");
      LOBYTE(v20) = (_BYTE)v568;
      std::string::string(v604, v20, v19, v17);
      LOBYTE(v21) = (_BYTE)v568;
      std::string::string(v603, v21, v604, v16);
      LOBYTE(v22) = (_BYTE)v568;
      std::string::string(&v673, v22, v603, v578);
      v576 = (__int64)&v583;
      std::_Integral_to_string<char,unsigned int>(v602, *((unsigned int *)this + 372));
      v23 = std::string::string(v626, ":");
      v24 = std::string::string(v625, "\"");
      v25 = std::string::string(v624, "\"");
      v26 = std::operator+<char>(v623, v25, "IceDoR");
      LOBYTE(v27) = (_BYTE)v568;
      std::string::string(v601, v27, v26, v24);
      LOBYTE(v28) = (_BYTE)v568;
      std::string::string(v600, v28, v601, v23);
      LOBYTE(v29) = (_BYTE)v568;
      std::string::string(&v583, v29, v600, v602);
      p_Str = (__int64)&Str;
      std::_Integral_to_string<char,unsigned int>(v599, *((unsigned int *)this + 553));
      v30 = std::string::string(v621, ":");
      v31 = std::string::string(v645, "\"");
      v32 = std::string::string(v644, "\"");
      v33 = std::operator+<char>(v643, v32, "CurrentActiveNumLinks");
      LOBYTE(v34) = (_BYTE)v568;
      std::string::string(v598, v34, v33, v31);
      LOBYTE(v35) = (_BYTE)v568;
      std::string::string(v597, v35, v598, v30);
      LOBYTE(v36) = (_BYTE)v568;
      std::string::string(&Str, v36, v597, v599);
      v574 = v677;
      v37 = std::string::string(v642, "\"");
      v38 = v671;
      if ( v672 > 0xF )
        v38 = (_QWORD *)v671[0];
      v39 = std::string::string(v641, "\"");
      v40 = std::string::string(v647, ":");
      v41 = std::string::string(v655, "\"");
      v42 = std::string::string(v656, "\"");
      v43 = std::operator+<char>(v657, v42, "RemovedLinkType");
      LOBYTE(v44) = (_BYTE)v568;
      std::string::string(v596, v44, v43, v41);
      LOBYTE(v45) = (_BYTE)v568;
      std::string::string(v595, v45, v596, v40);
      LOBYTE(v46) = (_BYTE)v568;
      std::string::string(v594, v46, v595, v39);
      v47 = std::operator+<char>(v659, v594, v38);
      LOBYTE(v48) = (_BYTE)v568;
      std::string::string(v677, v48, v47, v37);
      v575 = v663;
      std::_Integral_to_string<char,int>(v593, *((unsigned __int16 *)v570 + 1));
      v49 = std::string::string(v660, ":");
      v50 = std::string::string(v658, "\"");
      v51 = std::string::string(v606, "\"");
      v52 = std::operator+<char>(v607, v51, "RemovedLinkId");
      LOBYTE(v53) = (_BYTE)v568;
      std::string::string(v592, v53, v52, v50);
      LOBYTE(v54) = (_BYTE)v568;
      std::string::string(v619, v54, v592, v49);
      LOBYTE(v55) = (_BYTE)v568;
      std::string::string(v663, v55, v619, v593);
      v573 = (__int64 *)std::string::string(v608, "\"");
      v56 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v609, v661, 0, 6);
      v57 = v56;
      if ( v56[3] > 0xFu )
        v57 = (_QWORD *)*v56;
      v58 = std::string::string(v587, "\"");
      v59 = std::string::string(v614, ":");
      v60 = std::string::string(v615, "\"");
      v61 = std::string::string(v612, "\"");
      v62 = std::operator+<char>(v613, v61, "Direction");
      LOBYTE(v63) = (_BYTE)v568;
      std::string::string(v618, v63, v62, v60);
      LOBYTE(v64) = (_BYTE)v568;
      std::string::string(v617, v64, v618, v59);
      LOBYTE(v65) = (_BYTE)v568;
      std::string::string(v620, v65, v617, v58);
      v66 = std::operator+<char>(v577, v620, v57);
      LOBYTE(v67) = (_BYTE)v568;
      std::string::string(v668, v67, v66, v573);
      v68 = (char *)v666;
      if ( v667.m128i_i64[1] > 0xFuLL )
        v68 = v666[0];
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
        (int)v662,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "LinkRemove",
        v68,
        (__int64)v668,
        (__int64)v663,
        (__int64)v677,
        (__int64)&Str,
        (__int64)&v583,
        (__int64)&v673);
      std::string::_Tidy_deallocate(v577);
      std::string::_Tidy_deallocate(v620);
      std::string::_Tidy_deallocate(v617);
      std::string::_Tidy_deallocate(v618);
      std::string::_Tidy_deallocate(v613);
      std::string::_Tidy_deallocate(v612);
      std::string::_Tidy_deallocate(v615);
      std::string::_Tidy_deallocate(v614);
      std::string::_Tidy_deallocate(v587);
      std::string::_Tidy_deallocate(v609);
      std::string::_Tidy_deallocate(v608);
      std::string::_Tidy_deallocate(v619);
      std::string::_Tidy_deallocate(v592);
      std::string::_Tidy_deallocate(v607);
      std::string::_Tidy_deallocate(v606);
      std::string::_Tidy_deallocate(v658);
      std::string::_Tidy_deallocate(v660);
      std::string::_Tidy_deallocate(v593);
      std::string::_Tidy_deallocate(v659);
      std::string::_Tidy_deallocate(v594);
      std::string::_Tidy_deallocate(v595);
      std::string::_Tidy_deallocate(v596);
      std::string::_Tidy_deallocate(v657);
      std::string::_Tidy_deallocate(v656);
      std::string::_Tidy_deallocate(v655);
      std::string::_Tidy_deallocate(v647);
      std::string::_Tidy_deallocate(v641);
      std::string::_Tidy_deallocate(v642);
      std::string::_Tidy_deallocate(v597);
      std::string::_Tidy_deallocate(v598);
      std::string::_Tidy_deallocate(v643);
      std::string::_Tidy_deallocate(v644);
      std::string::_Tidy_deallocate(v645);
      std::string::_Tidy_deallocate(v621);
      std::string::_Tidy_deallocate(v599);
      std::string::_Tidy_deallocate(v600);
      std::string::_Tidy_deallocate(v601);
      std::string::_Tidy_deallocate(v623);
      std::string::_Tidy_deallocate(v624);
      std::string::_Tidy_deallocate(v625);
      std::string::_Tidy_deallocate(v626);
      std::string::_Tidy_deallocate(v602);
      std::string::_Tidy_deallocate(v603);
      std::string::_Tidy_deallocate(v604);
      std::string::_Tidy_deallocate(v627);
      std::string::_Tidy_deallocate(v628);
      std::string::_Tidy_deallocate(v622);
      std::string::_Tidy_deallocate(v610);
      std::string::_Tidy_deallocate(v578);
      v2 = v570;
      v5 = v569;
    }
    v69 = (volatile signed __int32 *)v662[1];
    if ( v662[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v662[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
        if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
      }
    }
    *(_OWORD *)v662 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v662);
    if ( v662[0] && *((_BYTE *)v662[0] + 128) )
    {
      LODWORD(v574) = *((_DWORD *)this + 373);
      LODWORD(v575) = *((_DWORD *)this + 372);
      LODWORD(v570) = *((_DWORD *)this + 553);
      v70 = v671;
      if ( v672 > 0xF )
        v70 = (__int64 *)v671[0];
      v573 = v70;
      LOWORD(v568) = *((_WORD *)v2 + 1);
      v71 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v610, v661, 0, 6);
      v74 = (__int64)v71;
      if ( (unsigned __int64)v71[3] > 0xF )
        v74 = *v71;
      v75 = v666;
      if ( v667.m128i_i64[1] > 0xFuLL )
        LODWORD(v75) = v666[0];
      std::string::string(
        v578,
        "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
        v72,
        v73,
        (_DWORD)v561,
        v562,
        (_DWORD)v563,
        v564,
        v565);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
        (unsigned int)v662,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v578,
        (_DWORD)v75,
        v74,
        (char)v568,
        (__int64)v573,
        (char)v570,
        (char)v575,
        (char)v574);
      std::string::_Tidy_deallocate(v578);
      std::string::_Tidy_deallocate(v610);
    }
    v76 = (volatile signed __int32 *)v662[1];
    goto LABEL_312;
  }
  v77 = std::operator+<char>(v610, v666, "LinkRemovedDueToError");
  if ( v666 != (char **)v77 )
  {
    std::string::_Tidy_deallocate(v666);
    *(_OWORD *)v666 = *(_OWORD *)v77;
    v667 = *(__m128i *)(v77 + 16);
    *(_QWORD *)(v77 + 16) = 0;
    *(_QWORD *)(v77 + 24) = 15;
    *(_BYTE *)v77 = 0;
  }
  std::string::_Tidy_deallocate(v610);
  *(_OWORD *)v677 = 0;
  v678 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v677[0]) = 0;
  v78 = *((_QWORD *)v2 + 1);
  if ( v78 )
  {
    v79 = *(_QWORD *)(v78 + 104);
    if ( v79 )
    {
      v80 = *(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)(v79 + 40) + 8LL);
      std::string::string(v578, "Microsoft::Basix::Dct.LastException");
      v80(v79 + 40, &v673, v578);
      std::string::_Tidy_deallocate(v578);
      v81 = v673;
      if ( (_BYTE)v673 )
      {
        *(_OWORD *)v662 = 0;
        *(_OWORD *)v663 = 0;
        __ExceptionPtrCreate(v663);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
          v676,
          v662,
          v663);
        __ExceptionPtrDestroy(v663);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v662) )
        {
          Description = Microsoft::Basix::Exception::CreateDescription(v610, v662);
          std::string::operator=(v677, Description);
          std::string::_Tidy_deallocate(v610);
        }
        __ExceptionPtrDestroy(v662);
        v81 = v673;
      }
      if ( v81 )
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v674);
    }
  }
  if ( !v5 )
  {
    v83 = *((_QWORD *)v2 + 1);
    *(_OWORD *)v662 = 0;
    v84 = *(_QWORD *)(v83 + 128);
    if ( v84 )
    {
      v85 = *(_DWORD *)(v84 + 8);
      while ( v85 )
      {
        v86 = v85;
        v85 = _InterlockedCompareExchange((volatile signed __int32 *)(v84 + 8), v85 + 1, v85);
        if ( v86 == v85 )
        {
          v87 = *(std::_Ref_count_base **)(v83 + 120);
          v662[0] = v87;
          v88 = *(std::_Ref_count_base **)(v83 + 128);
          v662[1] = v88;
          goto LABEL_85;
        }
      }
    }
    v87 = v662[0];
    v88 = v662[1];
LABEL_85:
    if ( v87 )
    {
      v89 = *(_QWORD *)v87;
      v90 = *((_QWORD *)v2 + 1);
      *(_OWORD *)v668 = 0;
      v91 = *(_QWORD *)(v90 + 112);
      if ( v91 )
        _InterlockedIncrement((volatile signed __int32 *)(v91 + 8));
      v668[0] = *(std::_Ref_count_base **)(v90 + 104);
      v668[1] = *(std::_Ref_count_base **)(v90 + 112);
      (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v89 + 16))(v87, v668);
    }
    if ( v88 )
      std::_Ref_count_base::_Decref(v88);
  }
  *(_OWORD *)v662 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v662);
  if ( v662[0] && *((_BYTE *)v662[0] + 128) )
  {
    v571 = v578;
    v92 = std::string::string(v616, "\"");
    v93 = v677;
    if ( v678.m128i_i64[1] > 0xFuLL )
      v93 = (void **)v677[0];
    v94 = std::string::string(v629, "\"");
    v95 = std::string::string(v630, ":");
    v96 = std::string::string(v631, "\"");
    v97 = std::string::string(v632, "\"");
    v98 = std::operator+<char>(v633, v97, "error");
    LOBYTE(v99) = (_BYTE)v568;
    std::string::string(v587, v99, v98, v96);
    LOBYTE(v100) = (_BYTE)v568;
    std::string::string(v609, v100, v587, v95);
    LOBYTE(v101) = (_BYTE)v568;
    std::string::string(v608, v101, v609, v94);
    v102 = std::operator+<char>(v634, v608, v93);
    LOBYTE(v103) = (_BYTE)v568;
    std::string::string(v578, v103, v102, v92);
    v576 = (__int64)v604;
    std::_Integral_to_string<char,unsigned int>(v607, *((unsigned int *)this + 373));
    v104 = std::string::string(v635, ":");
    v105 = std::string::string(v636, "\"");
    v106 = std::string::string(v637, "\"");
    v107 = std::operator+<char>(v638, v106, "NonIceDoR");
    LOBYTE(v108) = (_BYTE)v568;
    std::string::string(v606, v108, v107, v105);
    LOBYTE(v109) = (_BYTE)v568;
    std::string::string(v668, v109, v606, v104);
    LOBYTE(v110) = (_BYTE)v568;
    std::string::string(v604, v110, v668, v607);
    p_Str = (__int64)v603;
    std::_Integral_to_string<char,unsigned int>(v663, *((unsigned int *)this + 372));
    v111 = std::string::string(v639, ":");
    v112 = std::string::string(v614, "\"");
    v113 = std::string::string(v615, "\"");
    v114 = std::operator+<char>(v612, v113, "IceDoR");
    LOBYTE(v115) = (_BYTE)v568;
    std::string::string(&Str, v115, v114, v112);
    LOBYTE(v116) = (_BYTE)v568;
    std::string::string(&v583, v116, &Str, v111);
    LOBYTE(v117) = (_BYTE)v568;
    std::string::string(v603, v117, &v583, v663);
    v574 = v602;
    std::_Integral_to_string<char,unsigned int>(&v673, *((unsigned int *)this + 553));
    v118 = std::string::string(v613, ":");
    v119 = std::string::string(v577, "\"");
    v120 = std::string::string(v658, "\"");
    v121 = std::operator+<char>(v660, v120, "CurrentActiveNumLinks");
    LOBYTE(v122) = (_BYTE)v568;
    std::string::string(v620, v122, v121, v119);
    LOBYTE(v123) = (_BYTE)v568;
    std::string::string(v617, v123, v620, v118);
    LOBYTE(v124) = (_BYTE)v568;
    std::string::string(v602, v124, v617, &v673);
    v575 = v601;
    v125 = std::string::string(v659, "\"");
    v126 = v671;
    if ( v672 > 0xF )
      v126 = (_QWORD *)v671[0];
    v127 = std::string::string(v657, "\"");
    v128 = std::string::string(v656, ":");
    v129 = std::string::string(v655, "\"");
    v130 = std::string::string(v647, "\"");
    v131 = std::operator+<char>(v641, v130, "RemovedLinkType");
    LOBYTE(v132) = (_BYTE)v568;
    std::string::string(v618, v132, v131, v129);
    LOBYTE(v133) = (_BYTE)v568;
    std::string::string(v619, v133, v618, v128);
    LOBYTE(v134) = (_BYTE)v568;
    std::string::string(v592, v134, v619, v127);
    v135 = std::operator+<char>(v642, v592, v126);
    LOBYTE(v136) = (_BYTE)v568;
    std::string::string(v601, v136, v135, v125);
    v568 = v600;
    std::_Integral_to_string<char,int>(v593, *((unsigned __int16 *)v570 + 1));
    v137 = std::string::string(v643, ":");
    v138 = std::string::string(v644, "\"");
    v139 = std::string::string(v645, "\"");
    v140 = std::operator+<char>(v621, v139, "RemovedLinkId");
    LOBYTE(v141) = (unsigned __int8)v600;
    std::string::string(v594, v141, v140, v138);
    LOBYTE(v142) = (unsigned __int8)v600;
    std::string::string(v595, v142, v594, v137);
    LOBYTE(v143) = (unsigned __int8)v600;
    std::string::string(v600, v143, v595, v593);
    v573 = (__int64 *)std::string::string(v623, "\"");
    v144 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v624, v661, 0, 6);
    v145 = v144;
    if ( v144[3] > 0xFu )
      v145 = (_QWORD *)*v144;
    v146 = std::string::string(v625, "\"");
    v147 = std::string::string(v626, ":");
    v148 = std::string::string(v627, "\"");
    v149 = std::string::string(v628, "\"");
    v150 = std::operator+<char>(v622, v149, "Direction");
    LOBYTE(v151) = (_BYTE)v568;
    std::string::string(v596, v151, v150, v148);
    LOBYTE(v152) = (_BYTE)v568;
    std::string::string(v597, v152, v596, v147);
    LOBYTE(v153) = (_BYTE)v568;
    std::string::string(v598, v153, v597, v146);
    v154 = std::operator+<char>(v610, v598, v145);
    LOBYTE(v155) = (_BYTE)v568;
    std::string::string(v599, v155, v154, v573);
    v156 = (char *)v666;
    if ( v667.m128i_i64[1] > 0xFuLL )
      v156 = v666[0];
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
      (int)v662,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Smiles",
      "LinkRemove",
      v156,
      (__int64)v599,
      (__int64)v600,
      (__int64)v601,
      (__int64)v602,
      (__int64)v603,
      (__int64)v604,
      (__int64)v578);
    std::string::_Tidy_deallocate(v610);
    std::string::_Tidy_deallocate(v598);
    std::string::_Tidy_deallocate(v597);
    std::string::_Tidy_deallocate(v596);
    std::string::_Tidy_deallocate(v622);
    std::string::_Tidy_deallocate(v628);
    std::string::_Tidy_deallocate(v627);
    std::string::_Tidy_deallocate(v626);
    std::string::_Tidy_deallocate(v625);
    std::string::_Tidy_deallocate(v624);
    std::string::_Tidy_deallocate(v623);
    std::string::_Tidy_deallocate(v595);
    std::string::_Tidy_deallocate(v594);
    std::string::_Tidy_deallocate(v621);
    std::string::_Tidy_deallocate(v645);
    std::string::_Tidy_deallocate(v644);
    std::string::_Tidy_deallocate(v643);
    std::string::_Tidy_deallocate(v593);
    std::string::_Tidy_deallocate(v642);
    std::string::_Tidy_deallocate(v592);
    std::string::_Tidy_deallocate(v619);
    std::string::_Tidy_deallocate(v618);
    std::string::_Tidy_deallocate(v641);
    std::string::_Tidy_deallocate(v647);
    std::string::_Tidy_deallocate(v655);
    std::string::_Tidy_deallocate(v656);
    std::string::_Tidy_deallocate(v657);
    std::string::_Tidy_deallocate(v659);
    std::string::_Tidy_deallocate(v617);
    std::string::_Tidy_deallocate(v620);
    std::string::_Tidy_deallocate(v660);
    std::string::_Tidy_deallocate(v658);
    std::string::_Tidy_deallocate(v577);
    std::string::_Tidy_deallocate(v613);
    std::string::_Tidy_deallocate(&v673);
    std::string::_Tidy_deallocate(&v583);
    std::string::_Tidy_deallocate(&Str);
    std::string::_Tidy_deallocate(v612);
    std::string::_Tidy_deallocate(v615);
    std::string::_Tidy_deallocate(v614);
    std::string::_Tidy_deallocate(v639);
    std::string::_Tidy_deallocate(v663);
    std::string::_Tidy_deallocate(v668);
    std::string::_Tidy_deallocate(v606);
    std::string::_Tidy_deallocate(v638);
    std::string::_Tidy_deallocate(v637);
    std::string::_Tidy_deallocate(v636);
    std::string::_Tidy_deallocate(v635);
    std::string::_Tidy_deallocate(v607);
    std::string::_Tidy_deallocate(v634);
    std::string::_Tidy_deallocate(v608);
    std::string::_Tidy_deallocate(v609);
    std::string::_Tidy_deallocate(v587);
    std::string::_Tidy_deallocate(v633);
    std::string::_Tidy_deallocate(v632);
    std::string::_Tidy_deallocate(v631);
    std::string::_Tidy_deallocate(v630);
    std::string::_Tidy_deallocate(v629);
    std::string::_Tidy_deallocate(v616);
    v2 = v570;
    v5 = v569;
  }
  v157 = (volatile signed __int32 *)v662[1];
  if ( v662[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v662[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v157)(v157);
      if ( _InterlockedExchangeAdd(v157 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v157 + 8LL))(v157);
    }
  }
  *(_OWORD *)v662 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v662);
  if ( v662[0] && *((_BYTE *)v662[0] + 128) )
  {
    v158 = v677;
    if ( v678.m128i_i64[1] > 0xFuLL )
      v158 = (void **)v677[0];
    v573 = (__int64 *)v158;
    LODWORD(v570) = *((_DWORD *)this + 373);
    LODWORD(v574) = *((_DWORD *)this + 372);
    LODWORD(v575) = *((_DWORD *)this + 553);
    v159 = v671;
    if ( v672 > 0xF )
      v159 = (_QWORD *)v671[0];
    v576 = (__int64)v159;
    LOWORD(v568) = *((_WORD *)v2 + 1);
    v160 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v616, v661, 0, 6);
    v163 = (__int64)v160;
    if ( (unsigned __int64)v160[3] > 0xF )
      v163 = *v160;
    v164 = v666;
    if ( v667.m128i_i64[1] > 0xFuLL )
      LODWORD(v164) = v666[0];
    std::string::string(
      v587,
      "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, error=%s",
      v161,
      v162,
      (_DWORD)v561,
      v562,
      (_DWORD)v563,
      v564,
      v565,
      v566);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
      (unsigned int)v662,
      (unsigned int)"BASIX_DCT",
      (unsigned int)v587,
      (_DWORD)v164,
      v163,
      (char)v568,
      v576,
      (char)v575,
      (char)v574,
      (char)v570,
      (__int64)v573);
    std::string::_Tidy_deallocate(v587);
    std::string::_Tidy_deallocate(v616);
  }
  v165 = (volatile signed __int32 *)v662[1];
  if ( v662[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v662[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v165)(v165);
      if ( _InterlockedExchangeAdd(v165 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v165 + 8LL))(v165);
    }
  }
  std::string::_Tidy_deallocate(v677);
LABEL_316:
  if ( !v661[0] && !v5 )
  {
    v668[1] = 0;
    v668[0] = 0;
    v549 = (std::_Ref_count_base *)operator new(0x20u);
    v662[0] = v549;
    if ( v549 )
      v550 = (std::_Ref_count_base *)__0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v549);
    else
      v550 = 0;
    v668[1] = v550;
    v579 = 0;
    v580 = 0;
    std::string::_Construct<1,char const *>(&v579, "reason", 6);
    v581 = 46;
    v551 = &v579;
    if ( *((_QWORD *)&v580 + 1) > 0xFu )
      v551 = (__int128 *)v579;
    v582 = v551;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
      v668,
      &v579,
      &v679);
    std::string::_Tidy_deallocate(&v579);
    memset(v681, 0, 0xF8u);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v681,
      1);
    LOBYTE(v552) = 1;
    Microsoft::Basix::Containers::AnyPTreeToJson(v668, &v681[2], v552);
    if ( *((_BYTE *)this + 2368) )
    {
      std::stringbuf::str(&v681[3], &Str);
      v554 = v4 | 0x240;
      v555 = &Str;
      if ( v591 > 0xF )
        v555 = Str;
      LODWORD(v583) = 2;
      v584 = v555;
      v585 = strlen((const char *)v555);
      v586 = 0;
      v4 = v554 | 0x80;
      LODWORD(p_Str) = v4;
      LODWORD(v570) = -1;
      v556 = (Microsoft::Basix::Dct::LinkDataV3 *)*((_QWORD *)v2 + 1);
      if ( v556 )
      {
        AveDelayOut = (int)Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(v556);
        v558 = *((_QWORD *)v2 + 1);
      }
      else
      {
        AveDelayOut = 0;
        v558 = 0;
      }
      LODWORD(v574) = AveDelayOut;
      v559 = v666;
      if ( v667.m128i_i64[1] > 0xFuLL )
        v559 = (char **)v666[0];
      LODWORD(v673) = 2;
      v674 = v559;
      v675 = strlen((const char *)v559);
      LOBYTE(v676) = 0;
      LOWORD(v4) = v4 | 0x100;
      if ( v558 )
        v560 = *(_DWORD *)(v558 + 260);
      else
        v560 = 0;
      LODWORD(v575) = v560;
      LODWORD(v568) = *((unsigned __int16 *)v2 + 1);
      Microsoft::Basix::Instrumentation::MultiLinkActivity::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)this + 2496,
        (_DWORD)this + 2376,
        (unsigned int)&v568,
        (unsigned int)&v575,
        (__int64)&v673,
        (__int64)&v574,
        (__int64)&v570,
        (__int64)this + 2212,
        (__int64)&v583);
    }
    if ( (v4 & 0x100) != 0 && (_BYTE)v676 )
      operator delete(v674, v553);
    if ( (v4 & 0x80u) != 0 )
    {
      LOBYTE(v4) = v4 & 0x7F;
      if ( v586 )
        operator delete(v584, v553);
    }
    if ( (v4 & 0x40) != 0 )
      std::string::_Tidy_deallocate(&Str);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v681[19]);
    v681[19] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v681[19]);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v668);
  }
  std::string::_Tidy_deallocate(v671);
  std::string::_Tidy_deallocate(v666);
  std::string::_Tidy_deallocate(&v679);
}

```

## disassembly

```asm
0x1802741d0  mov     [rsp-8+arg_10], rbx
0x1802741d5  push    rbp
0x1802741d6  push    rsi
0x1802741d7  push    rdi
0x1802741d8  push    r12
0x1802741da  push    r13
0x1802741dc  push    r14
0x1802741de  push    r15
0x1802741e0  lea     rbp, [rsp-0B00h]
0x1802741e8  mov     eax, 0C00h
0x1802741ed  call    _alloca_probe
0x1802741f2  sub     rsp, rax
0x1802741f5  mov     rax, cs:__security_cookie
0x1802741fc  xor     rax, rsp
0x1802741ff  mov     [rbp+0B30h+var_40], rax
0x180274206  mov     rsi, rdx
0x180274209  mov     [rbp+0B30h+var_BB0], rdx
0x18027420d  mov     r13, rcx
0x180274210  xor     r15d, r15d
0x180274213  mov     r12d, r15d
0x180274216  mov     dword ptr [rbp+0B30h+var_BA0], r15d
0x18027421a  xorps   xmm0, xmm0
0x18027421d  movups  [rbp+0B30h+var_160], xmm0
0x180274224  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18027422c  movdqu  [rbp+0B30h+var_150], xmm1
0x180274234  mov     byte ptr [rbp+0B30h+var_160], r15b
0x18027423b  movups  xmmword ptr [rbp+0B30h+var_200], xmm0
0x180274242  movdqu  [rbp+0B30h+var_1F0], xmm1
0x18027424a  mov     byte ptr [rbp+0B30h+var_200], r15b
0x180274251  mov     al, [rdx+18h]
0x180274254  mov     [rbp+0B30h+var_238], al
0x18027425a  mov     r14b, [rdx+19h]
0x18027425e  mov     [rsp+0C30h+var_BB8], r14b
0x180274263  mov     rdx, [rdx+8]
0x180274267  add     rdx, 50h ; 'P'
0x18027426b  lea     r9d, [r15+6]
0x18027426f  xor     r8d, r8d
0x180274272  lea     rcx, [rbp+0B30h+var_1C0]
0x180274279  call    ??$ToString@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4LinkType@ISmiles@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &,int,int)
0x18027427e  nop
0x18027427f  test    r14b, r14b
0x180274282  jz      short loc_180274297
0x180274284  lea     rdx, aInfoonly; "(InfoOnly)"
0x18027428b  lea     rcx, [rbp+0B30h+var_200]
0x180274292  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180274297  movzx   ecx, byte ptr [rsi]
0x18027429a  mov     edi, 2
0x18027429f  sub     ecx, 1
0x1802742a2  jz      loc_1802790D9
0x1802742a8  sub     ecx, 1
0x1802742ab  jz      loc_18027841F
0x1802742b1  sub     ecx, 1
0x1802742b4  jz      loc_180277964
0x1802742ba  sub     ecx, 1
0x1802742bd  jz      loc_180276CB5
0x1802742c3  sub     ecx, 1
0x1802742c6  jz      loc_180275E16
0x1802742cc  sub     ecx, 1
0x1802742cf  jz      loc_180274FE1
0x1802742d5  cmp     ecx, 1
0x1802742d8  jnz     loc_180279BD0
0x1802742de  lea     r8, aLinkremovedtim; "LinkRemovedTimeout"
0x1802742e5  lea     rdx, [rbp+0B30h+var_200]
0x1802742ec  lea     rcx, [rbp+0B30h+var_B78]
0x1802742f0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x1802742f5  mov     rbx, rax
0x1802742f8  lea     rax, [rbp+0B30h+var_200]
0x1802742ff  cmp     rax, rbx
0x180274302  jz      short loc_180274334
0x180274304  lea     rcx, [rbp+0B30h+var_200]
0x18027430b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180274310  movups  xmm0, xmmword ptr [rbx]
0x180274313  movups  xmmword ptr [rbp+0B30h+var_200], xmm0
0x18027431a  movups  xmm1, xmmword ptr [rbx+10h]
0x18027431e  movups  [rbp+0B30h+var_1F0], xmm1
0x180274325  mov     [rbx+10h], r15
0x180274329  mov     qword ptr [rbx+18h], 0Fh
0x180274331  mov     [rbx], r15b
0x180274334  lea     rcx, [rbp+0B30h+var_B78]
0x180274338  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027433d  test    r14b, r14b
0x180274340  jnz     loc_1802745F2
0x180274346  mov     r8, [rsi+8]
0x18027434a  xorps   xmm1, xmm1
0x18027434d  movdqu  xmmword ptr [rbp+0B30h+var_230], xmm1
0x180274355  mov     rdx, [r8+80h]
0x18027435c  test    rdx, rdx
0x18027435f  jz      short loc_180274378
0x180274361  mov     eax, [rdx+8]
0x180274364  jmp     short loc_180274374
0x180274366  lea     ecx, [rax+1]
0x180274369  lock cmpxchg [rdx+8], ecx
0x18027436e  jz      loc_180274FC3
0x180274374  test    eax, eax
0x180274376  jnz     short loc_180274366
0x180274378  mov     rcx, [rbp+0B30h+var_230]
0x18027437f  test    rcx, rcx
0x180274382  jz      short loc_1802743CA
0x180274384  mov     rax, [rcx]
0x180274387  mov     r8, [rsi+8]
0x18027438b  xorps   xmm0, xmm0
0x18027438e  movdqu  xmmword ptr [rbp+0B30h+var_1E0], xmm0
0x180274396  mov     rdx, [r8+70h]
0x18027439a  test    rdx, rdx
0x18027439d  jz      short loc_1802743A3
0x18027439f  lock inc dword ptr [rdx+8]
0x1802743a3  mov     rdx, [r8+68h]
0x1802743a7  mov     [rbp+0B30h+var_1E0], rdx
0x1802743ae  mov     rdx, [r8+70h]
0x1802743b2  mov     [rbp+0B30h+var_1E0+8], rdx
0x1802743b9  lea     rdx, [rbp+0B30h+var_1E0]
0x1802743c0  mov     rax, [rax+10h]
0x1802743c4  call    cs:__guard_dispatch_icall_fptr
0x1802743ca  cmp     [r13+0A80h], r15b
0x1802743d1  jz      loc_180274535
0x1802743d7  mov     dword ptr [rbp+0B30h+var_1A0], edi
0x1802743dd  lea     rax, Str1
0x1802743e4  mov     [rbp+0B30h+var_198], rax
0x1802743eb  mov     [rbp+0B30h+var_190], r15
0x1802743f2  mov     byte ptr [rbp+0B30h+var_188], r15b
0x1802743f9  mov     byte ptr [rsp+0C30h+var_BC0], r15b
0x1802743fe  mov     dword ptr [rbp+0B30h+var_B08], edi
0x180274401  lea     rax, aLinkRemovedDue; "link removed due to timeout"
0x180274408  mov     [rbp+0B30h+var_B00], rax
0x18027440c  mov     [rbp+0B30h+var_AF8], 1Bh
0x180274414  mov     [rbp+0B30h+var_AF0], r15b
0x180274418  mov     dword ptr [rbp+0B30h+Str], edi
0x18027441b  lea     rax, aSmiles_0; "smiles"
0x180274422  mov     [rbp+0B30h+var_AC0], rax
0x180274426  mov     [rbp+0B30h+var_AB8], 6
0x18027442e  mov     byte ptr [rbp+0B30h+var_AB0], r15b
0x180274435  mov     dword ptr [rbp+0B30h+var_1E0], edi
0x18027443b  lea     rax, aALinkIsRemoved; "a link is removed after timeout"
0x180274442  mov     [rbp+0B30h+var_1E0+8], rax
0x180274449  mov     [rbp+0B30h+var_1D0], 1Fh
0x180274454  mov     [rbp+0B30h+var_1C8], r15b
0x18027445b  mov     dword ptr [rbp+0B30h+var_220], edi
0x180274461  lea     rax, aLinkremovetime; "LinkRemoveTimeout"
0x180274468  mov     [rbp+0B30h+var_220+8], rax
0x18027446f  mov     [rbp+0B30h+var_210], 11h
0x18027447a  mov     [rbp+0B30h+var_208], r15b
0x180274481  mov     dword ptr [rbp+0B30h+var_B88], 5B4h
0x180274488  lea     rax, aStack; "stack"
0x18027448f  lea     rcx, aClient_0; "client"
0x180274496  cmp     [r13+458h], r15b
0x18027449d  cmovnz  rcx, rax; Str
0x1802744a1  mov     dword ptr [rbp+0B30h+var_180], edi
0x1802744a7  mov     [rbp+0B30h+var_180+8], rcx
0x1802744ae  call    strlen
0x1802744b3  mov     qword ptr [rbp+0B30h+var_170], rax
0x1802744ba  mov     byte ptr [rbp+0B30h+var_170+8], r15b
0x1802744c1  mov     r12d, 3Fh ; '?'
0x1802744c7  movzx   eax, word ptr [rsi+2]
0x1802744cb  mov     dword ptr [rbp+0B30h+var_B90], eax
0x1802744ce  lea     rdx, [r13+0A88h]
0x1802744d5  lea     rax, [rbp+0B30h+var_1A0]
0x1802744dc  mov     [rsp+0C30h+var_BE0], rax
0x1802744e1  lea     rax, [rsp+0C30h+var_BC0]
0x1802744e6  mov     [rsp+0C30h+var_BE8], rax
0x1802744eb  lea     rax, [rbp+0B30h+var_B08]
0x1802744ef  mov     [rsp+0C30h+var_BF0], rax
0x1802744f4  lea     rax, [rbp+0B30h+Str]
0x1802744f8  mov     [rsp+0C30h+var_BF8], rax
0x1802744fd  lea     rax, [rbp+0B30h+var_1E0]
0x180274504  mov     [rsp+0C30h+var_C00], rax
0x180274509  lea     rax, [rbp+0B30h+var_220]
0x180274510  mov     [rsp+0C30h+var_C08], rax
0x180274515  lea     rax, [rbp+0B30h+var_B88]
0x180274519  mov     [rsp+0C30h+var_C10], rax
0x18027451e  lea     r9, [rbp+0B30h+var_180]
0x180274525  lea     r8, [rbp+0B30h+var_B90]
0x180274529  lea     rcx, [r13+0B00h]
0x180274530  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@MultiLinkError@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEBIAEBVEncodedString@234@12222AEB_N2@Z; Microsoft::Basix::Instrumentation::MultiLinkError::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,uint const &,Microsoft::Basix::Instrumentation::EncodedString const &,uint const &,Microsoft::Basix::Instrumentation::EncodedString const &,Microsoft::Basix::Instrumentation::EncodedString const &,Microsoft::Basix::Instrumentation::EncodedString const &,Microsoft::Basix::Instrumentation::EncodedString const &,bool const &,Microsoft::Basix::Instrumentation::EncodedString const &)
0x180274535  test    r12b, 20h
0x180274539  jz      short loc_180274554
0x18027453b  and     r12d, 0FFFFFFDFh
0x18027453f  cmp     byte ptr [rbp+0B30h+var_170+8], r15b
0x180274546  jz      short loc_180274554
0x180274548  mov     rcx, [rbp+0B30h+var_180+8]; void *
0x18027454f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180274554  test    r12b, 10h
0x180274558  jz      short loc_180274573
0x18027455a  and     r12d, 0FFFFFFEFh
0x18027455e  cmp     [rbp+0B30h+var_208], r15b
0x180274565  jz      short loc_180274573
0x180274567  mov     rcx, [rbp+0B30h+var_220+8]; void *
0x18027456e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180274573  test    r12b, 8
0x180274577  jz      short loc_180274592
0x180274579  and     r12d, 0FFFFFFF7h
0x18027457d  cmp     [rbp+0B30h+var_1C8], r15b
0x180274584  jz      short loc_180274592
0x180274586  mov     rcx, [rbp+0B30h+var_1E0+8]; void *
0x18027458d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180274592  test    r12b, 4
0x180274596  jz      short loc_1802745AE
0x180274598  and     r12d, 0FFFFFFFBh
0x18027459c  cmp     byte ptr [rbp+0B30h+var_AB0], r15b
0x1802745a3  jz      short loc_1802745AE
0x1802745a5  mov     rcx, [rbp+0B30h+var_AC0]; void *
0x1802745a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802745ae  test    dil, r12b
0x1802745b1  jz      short loc_1802745C6
0x1802745b3  and     r12d, 0FFFFFFFDh
0x1802745b7  cmp     [rbp+0B30h+var_AF0], r15b
0x1802745bb  jz      short loc_1802745C6
0x1802745bd  mov     rcx, [rbp+0B30h+var_B00]; void *
0x1802745c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802745c6  test    r12b, 1
0x1802745ca  jz      short loc_1802745E6
0x1802745cc  and     r12d, 0FFFFFFFEh
0x1802745d0  cmp     byte ptr [rbp+0B30h+var_188], r15b
0x1802745d7  jz      short loc_1802745E6
0x1802745d9  mov     rcx, [rbp+0B30h+var_198]; void *
0x1802745e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802745e5  nop
0x1802745e6  lea     rcx, [rbp+0B30h+var_230]; void *
0x1802745ed  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x1802745f2  xorps   xmm0, xmm0
0x1802745f5  movups  xmmword ptr [rbp+0B30h+var_230], xmm0
0x1802745fc  lea     rcx, [rbp+0B30h+var_230]
0x180274603  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x180274608  nop
0x180274609  mov     rax, [rbp+0B30h+var_230]
0x180274610  test    rax, rax
0x180274613  jz      loc_180274E4B
0x180274619  cmp     [rax+80h], r15b
0x180274620  jz      loc_180274E4B
0x180274626  lea     rax, [rbp+0B30h+var_1A0]
0x18027462d  mov     [rbp+0B30h+var_BA8], rax
0x180274631  mov     edx, [r13+5D4h]
0x180274638  lea     rcx, [rbp+0B30h+var_B58]
0x18027463c  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x180274641  nop
0x180274642  lea     r14, asc_1803D71C4; ":"
0x180274649  mov     rdx, r14
0x18027464c  lea     rcx, [rbp+0B30h+var_880]
0x180274653  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274658  mov     rdi, rax
0x18027465b  lea     rsi, asc_1803D71C8; "\""
0x180274662  mov     rdx, rsi
0x180274665  lea     rcx, [rbp+0B30h+var_718]
0x18027466c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274671  mov     rbx, rax
0x180274674  mov     rdx, rsi
0x180274677  lea     rcx, [rbp+0B30h+var_658]
0x18027467e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274683  nop
0x180274684  lea     r8, aNonicedor; "NonIceDoR"
0x18027468b  mov     rdx, rax
0x18027468e  lea     rcx, [rbp+0B30h+var_678]
0x180274695  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027469a  nop
0x18027469b  mov     r9, rbx
0x18027469e  mov     r8, rax
0x1802746a1  mov     dl, byte ptr [rsp+0C30h+var_BC0]
0x1802746a5  lea     rcx, [rbp+0B30h+var_928]
0x1802746ac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1802746b1  nop
0x1802746b2  mov     r9, rdi
0x1802746b5  lea     r8, [rbp+0B30h+var_928]
0x1802746bc  mov     dl, byte ptr [rsp+0C30h+var_BC0]
0x1802746c0  lea     rcx, [rbp+0B30h+var_948]
0x1802746c7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1802746cc  nop
0x1802746cd  lea     r9, [rbp+0B30h+var_B58]
0x1802746d1  lea     r8, [rbp+0B30h+var_948]
0x1802746d8  mov     dl, byte ptr [rsp+0C30h+var_BC0]
0x1802746dc  lea     rcx, [rbp+0B30h+var_1A0]
0x1802746e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1802746e8  nop
0x1802746e9  lea     rax, [rbp+0B30h+var_B08]
0x1802746ed  mov     [rbp+0B30h+var_B80], rax
0x1802746f1  mov     edx, [r13+5D0h]
0x1802746f8  lea     rcx, [rbp+0B30h+var_968]
0x1802746ff  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x180274704  nop
0x180274705  mov     rdx, r14
0x180274708  lea     rcx, [rbp+0B30h+var_698]
0x18027470f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274714  mov     rdi, rax
0x180274717  mov     rdx, rsi
0x18027471a  lea     rcx, [rbp+0B30h+var_6B8]
0x180274721  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274726  mov     rbx, rax
0x180274729  mov     rdx, rsi
0x18027472c  lea     rcx, [rbp+0B30h+var_6D8]
0x180274733  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180274738  nop
0x180274739  lea     r8, aIcedor; "IceDoR"
0x180274740  mov     rdx, rax
0x180274743  lea     rcx, [rbp+0B30h+var_6F8]
0x18027474a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027474f  nop
0x180274750  mov     r9, rbx
0x180274753  mov     r8, rax
0x180274756  mov     dl, byte ptr [rsp+0C30h+var_BC0]
0x18027475a  lea     rcx, [rbp+0B30h+var_988]
0x180274761  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180274766  nop
  ... truncated ...
```
