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
  __int64 v82; // rdx
  __int64 Description; // rax
  __int64 v84; // rbx
  __int64 v85; // rdx
  signed __int32 v86; // eax
  signed __int32 v87; // ett
  std::_Ref_count_base *v88; // rcx
  std::_Ref_count_base *v89; // rbx
  __int64 v90; // rax
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r15
  void **v94; // r14
  __int64 v95; // rsi
  __int64 v96; // rdi
  __int64 v97; // rbx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rdx
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rdi
  __int64 v106; // rbx
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdx
  __int64 v110; // rdx
  __int64 v111; // rdx
  __int64 v112; // rdi
  __int64 v113; // rbx
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdx
  __int64 v119; // rdi
  __int64 v120; // rbx
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // r15
  _QWORD *v127; // r14
  __int64 v128; // rsi
  __int64 v129; // rdi
  __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rdx
  __int64 v135; // rdx
  __int64 v136; // rax
  __int64 v137; // rdx
  __int64 v138; // rdi
  __int64 v139; // rbx
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rdx
  __int64 v144; // rdx
  _QWORD *v145; // rax
  _QWORD *v146; // r15
  __int64 v147; // rsi
  __int64 v148; // rdi
  __int64 v149; // rbx
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rdx
  __int64 v155; // rax
  __int64 v156; // rdx
  char *v157; // rax
  volatile signed __int32 *v158; // rbx
  void **v159; // rax
  _QWORD *v160; // rax
  __int64 *v161; // rax
  const char *v162; // r8
  const char *v163; // r9
  __int64 v164; // r15
  char **v165; // rbx
  volatile signed __int32 *v166; // rbx
  __int64 v167; // rcx
  __int64 v168; // rbx
  __int64 v169; // rbx
  __int64 v170; // rdx
  signed __int32 v171; // eax
  signed __int32 v172; // ett
  std::_Ref_count_base *v173; // rcx
  std::_Ref_count_base *v174; // rbx
  __int64 v175; // rax
  __int64 v176; // r8
  __int64 v177; // rdx
  __int64 v178; // rdi
  __int64 v179; // rbx
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rdx
  __int64 v183; // rdx
  __int64 v184; // rdx
  __int64 v185; // rdi
  __int64 v186; // rbx
  __int64 v187; // rax
  __int64 v188; // rax
  __int64 v189; // rdx
  __int64 v190; // rdx
  __int64 v191; // rdx
  __int64 v192; // rdi
  __int64 v193; // rbx
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // rdx
  __int64 v197; // rdx
  __int64 v198; // rdx
  __int64 v199; // r15
  _QWORD *v200; // r14
  __int64 v201; // rsi
  __int64 v202; // rdi
  __int64 v203; // rbx
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rdx
  __int64 v208; // rdx
  __int64 v209; // rax
  __int64 v210; // rdx
  __int64 v211; // rdi
  __int64 v212; // rbx
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rdx
  __int64 v216; // rdx
  __int64 v217; // rdx
  __int64 v218; // rdi
  __int64 v219; // rbx
  __int64 v220; // rax
  __int64 v221; // rax
  __int64 v222; // rdx
  __int64 v223; // rdx
  __int64 v224; // rdx
  __int64 v225; // rax
  __int64 v226; // rsi
  __int64 v227; // rdi
  __int64 v228; // rbx
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // rdx
  __int64 v232; // rdx
  __int64 v233; // rdx
  __int64 v234; // rax
  __int64 v235; // rdx
  __int64 v236; // rax
  __int64 v237; // rsi
  __int64 v238; // rdi
  __int64 v239; // rbx
  __int64 v240; // rax
  __int64 v241; // rax
  __int64 v242; // rdx
  __int64 v243; // rdx
  __int64 v244; // rdx
  __int64 v245; // rax
  __int64 v246; // rdx
  char *v247; // rax
  volatile signed __int32 *v248; // rbx
  __int64 *v249; // rax
  __int64 *v250; // rax
  __int64 *v251; // rax
  const char *v252; // r8
  const char *v253; // r9
  __int64 v254; // r15
  char **v255; // rbx
  __int64 v256; // rbx
  __int64 v257; // rbx
  __int64 v258; // rdx
  signed __int32 v259; // eax
  signed __int32 v260; // ett
  std::_Ref_count_base *v261; // rcx
  std::_Ref_count_base *v262; // rbx
  void (__fastcall **v263)(std::_Ref_count_base *, void **); // rax
  __int64 v264; // r8
  __int64 v265; // rdx
  __int64 v266; // r14
  __int64 v267; // rsi
  __int64 v268; // rdi
  __int64 v269; // rbx
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rdx
  __int64 v273; // rdx
  __int64 v274; // rdx
  __int64 v275; // rax
  __int64 v276; // rdx
  __int64 v277; // rdi
  __int64 v278; // rbx
  __int64 v279; // rax
  __int64 v280; // rax
  __int64 v281; // rdx
  __int64 v282; // rdx
  __int64 v283; // rdx
  __int64 v284; // rdi
  __int64 v285; // rbx
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rdx
  __int64 v289; // rdx
  __int64 v290; // rdx
  __int64 v291; // rdi
  __int64 v292; // rbx
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rdx
  __int64 v296; // rdx
  __int64 v297; // rdx
  __int64 v298; // r15
  _QWORD *v299; // r14
  __int64 v300; // rsi
  __int64 v301; // rdi
  __int64 v302; // rbx
  __int64 v303; // rax
  __int64 v304; // rax
  __int64 v305; // rdx
  __int64 v306; // rdx
  __int64 v307; // rdx
  __int64 v308; // rax
  __int64 v309; // rdx
  __int64 v310; // rdi
  __int64 v311; // rbx
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rdx
  __int64 v315; // rdx
  __int64 v316; // rdx
  _QWORD *v317; // rax
  _QWORD *v318; // r15
  __int64 v319; // rsi
  __int64 v320; // rdi
  __int64 v321; // rbx
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // rdx
  __int64 v325; // rdx
  __int64 v326; // rdx
  __int64 v327; // rax
  __int64 v328; // rdx
  char *v329; // rax
  volatile signed __int32 *v330; // rbx
  __int64 *v331; // rax
  __int64 *v332; // rax
  __int64 *v333; // rax
  const char *v334; // r8
  const char *v335; // r9
  __int64 v336; // r15
  char **v337; // rbx
  __int64 v338; // rbx
  std::_Ref_count_base *v339; // rcx
  __int64 v340; // rax
  __int64 v341; // r8
  __int64 v342; // rdx
  __int64 v343; // rdi
  __int64 v344; // rbx
  __int64 v345; // rax
  __int64 v346; // rax
  __int64 v347; // rdx
  __int64 v348; // rdx
  __int64 v349; // rdx
  __int64 v350; // rdi
  __int64 v351; // rbx
  __int64 v352; // rax
  __int64 v353; // rax
  __int64 v354; // rdx
  __int64 v355; // rdx
  __int64 v356; // rdx
  __int64 v357; // rdi
  __int64 v358; // rbx
  __int64 v359; // rax
  __int64 v360; // rax
  __int64 v361; // rdx
  __int64 v362; // rdx
  __int64 v363; // rdx
  __int64 v364; // r15
  _QWORD *v365; // r14
  __int64 v366; // rsi
  __int64 v367; // rdi
  __int64 v368; // rbx
  __int64 v369; // rax
  __int64 v370; // rax
  __int64 v371; // rdx
  __int64 v372; // rdx
  __int64 v373; // rdx
  __int64 v374; // rax
  __int64 v375; // rdx
  __int64 v376; // rdi
  __int64 v377; // rbx
  __int64 v378; // rax
  __int64 v379; // rax
  __int64 v380; // rdx
  __int64 v381; // rdx
  __int64 v382; // rdx
  _QWORD *v383; // rax
  _QWORD *v384; // r15
  __int64 v385; // rsi
  __int64 v386; // rdi
  __int64 v387; // rbx
  __int64 v388; // rax
  __int64 v389; // rax
  __int64 v390; // rdx
  __int64 v391; // rdx
  __int64 v392; // rdx
  __int64 v393; // rax
  __int64 v394; // rdx
  char *v395; // rax
  volatile signed __int32 *v396; // rbx
  __int64 *v397; // rax
  __int64 *v398; // rax
  const char *v399; // r8
  const char *v400; // r9
  __int64 v401; // r15
  char **v402; // rbx
  __int64 v403; // rbx
  __int64 v404; // rbx
  __int64 v405; // rdx
  signed __int32 v406; // eax
  signed __int32 v407; // ett
  std::_Ref_count_base *v408; // rcx
  std::_Ref_count_base *v409; // rbx
  void (__fastcall **v410)(std::_Ref_count_base *, void **); // rax
  __int64 v411; // r8
  __int64 v412; // rdx
  __int64 v413; // r14
  __int64 v414; // rsi
  __int64 v415; // rdi
  __int64 v416; // rbx
  __int64 v417; // rax
  __int64 v418; // rax
  __int64 v419; // rdx
  __int64 v420; // rdx
  __int64 v421; // rdx
  __int64 v422; // rax
  __int64 v423; // rdx
  __int64 v424; // rdi
  __int64 v425; // rbx
  __int64 v426; // rax
  __int64 v427; // rax
  __int64 v428; // rdx
  __int64 v429; // rdx
  __int64 v430; // rdx
  __int64 v431; // rdi
  __int64 v432; // rbx
  __int64 v433; // rax
  __int64 v434; // rax
  __int64 v435; // rdx
  __int64 v436; // rdx
  __int64 v437; // rdx
  __int64 v438; // rdi
  __int64 v439; // rbx
  __int64 v440; // rax
  __int64 v441; // rax
  __int64 v442; // rdx
  __int64 v443; // rdx
  __int64 v444; // rdx
  __int64 v445; // r15
  _QWORD *v446; // r14
  __int64 v447; // rsi
  __int64 v448; // rdi
  __int64 v449; // rbx
  __int64 v450; // rax
  __int64 v451; // rax
  __int64 v452; // rdx
  __int64 v453; // rdx
  __int64 v454; // rdx
  __int64 v455; // rax
  __int64 v456; // rdx
  __int64 v457; // rdi
  __int64 v458; // rbx
  __int64 v459; // rax
  __int64 v460; // rax
  __int64 v461; // rdx
  __int64 v462; // rdx
  __int64 v463; // rdx
  _QWORD *v464; // rax
  _QWORD *v465; // r15
  __int64 v466; // rsi
  __int64 v467; // rdi
  __int64 v468; // rbx
  __int64 v469; // rax
  __int64 v470; // rax
  __int64 v471; // rdx
  __int64 v472; // rdx
  __int64 v473; // rdx
  __int64 v474; // rax
  __int64 v475; // rdx
  char *v476; // rax
  volatile signed __int32 *v477; // rbx
  __int64 *v478; // rax
  __int64 *v479; // rax
  __int64 *v480; // rax
  const char *v481; // r8
  const char *v482; // r9
  __int64 v483; // r15
  char **v484; // rbx
  __int64 v485; // rbx
  std::_Ref_count_base *v486; // rcx
  __int64 v487; // rax
  __int64 v488; // r8
  __int64 v489; // rdx
  __int64 v490; // rdi
  __int64 v491; // rbx
  __int64 v492; // rax
  __int64 v493; // rax
  __int64 v494; // rdx
  __int64 v495; // rdx
  __int64 v496; // rdx
  __int64 v497; // rdi
  __int64 v498; // rbx
  __int64 v499; // rax
  __int64 v500; // rax
  __int64 v501; // rdx
  __int64 v502; // rdx
  __int64 v503; // rdx
  __int64 v504; // rdi
  __int64 v505; // rbx
  __int64 v506; // rax
  __int64 v507; // rax
  __int64 v508; // rdx
  __int64 v509; // rdx
  __int64 v510; // rdx
  __int64 v511; // r15
  _QWORD *v512; // r14
  __int64 v513; // rsi
  __int64 v514; // rdi
  __int64 v515; // rbx
  __int64 v516; // rax
  __int64 v517; // rax
  __int64 v518; // rdx
  __int64 v519; // rdx
  __int64 v520; // rdx
  __int64 v521; // rax
  __int64 v522; // rdx
  __int64 v523; // rdi
  __int64 v524; // rbx
  __int64 v525; // rax
  __int64 v526; // rax
  __int64 v527; // rdx
  __int64 v528; // rdx
  __int64 v529; // rdx
  _QWORD *v530; // rax
  _QWORD *v531; // r15
  __int64 v532; // rsi
  __int64 v533; // rdi
  __int64 v534; // rbx
  __int64 v535; // rax
  __int64 v536; // rax
  __int64 v537; // rdx
  __int64 v538; // rdx
  __int64 v539; // rdx
  __int64 v540; // rax
  __int64 v541; // rdx
  char *v542; // rax
  volatile signed __int32 *v543; // rbx
  __int64 *v544; // rax
  __int64 *v545; // rax
  const char *v546; // r8
  const char *v547; // r9
  __int64 v548; // r15
  char **v549; // rbx
  std::_Ref_count_base *v550; // rax
  std::_Ref_count_base *v551; // rax
  __int128 *v552; // rax
  __int64 v553; // r8
  const struct std::nothrow_t *v554; // rdx
  int v555; // r12d
  void *v556; // rcx
  Microsoft::Basix::Dct::LinkDataV3 *v557; // rcx
  int AveDelayOut; // eax
  __int64 v559; // rbx
  char **v560; // rcx
  int v561; // eax
  char *v562; // [rsp+20h] [rbp-E0h]
  char *v563; // [rsp+28h] [rbp-D8h]
  const char *v564; // [rsp+30h] [rbp-D0h]
  int v565; // [rsp+38h] [rbp-C8h]
  int v566; // [rsp+40h] [rbp-C0h]
  const char *v567; // [rsp+48h] [rbp-B8h]
  int v568; // [rsp+50h] [rbp-B0h]
  __int64 *v569; // [rsp+70h] [rbp-90h] BYREF
  char v570; // [rsp+78h] [rbp-88h]
  const struct Microsoft::Basix::Dct::OperationOnLinkId *v571; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v572; // [rsp+88h] [rbp-78h]
  __int64 p_Str; // [rsp+90h] [rbp-70h]
  __int64 *v574; // [rsp+98h] [rbp-68h]
  void *v575; // [rsp+A0h] [rbp-60h] BYREF
  void *v576; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v577; // [rsp+B0h] [rbp-50h]
  __int64 v578[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v579[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v580; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v581; // [rsp+108h] [rbp+8h]
  char v582; // [rsp+118h] [rbp+18h]
  __int128 *v583; // [rsp+120h] [rbp+20h]
  __int64 v584; // [rsp+128h] [rbp+28h] BYREF
  void *v585; // [rsp+130h] [rbp+30h]
  size_t v586; // [rsp+138h] [rbp+38h]
  char v587; // [rsp+140h] [rbp+40h]
  __int64 v588[4]; // [rsp+148h] [rbp+48h] BYREF
  char *Str; // [rsp+168h] [rbp+68h] BYREF
  void *v590; // [rsp+170h] [rbp+70h]
  __int64 v591; // [rsp+178h] [rbp+78h]
  unsigned __int64 v592; // [rsp+180h] [rbp+80h]
  _BYTE v593[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v594[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v595[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v596[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v597[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v598[32]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v599[32]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v600[4]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v601[4]; // [rsp+288h] [rbp+188h] BYREF
  __int64 v602[4]; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v603[4]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v604[4]; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v605[4]; // [rsp+308h] [rbp+208h] BYREF
  __int64 *v606; // [rsp+328h] [rbp+228h]
  __int64 v607[4]; // [rsp+330h] [rbp+230h] BYREF
  __int64 v608[4]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v609[4]; // [rsp+370h] [rbp+270h] BYREF
  __int64 v610[4]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v611[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 *v612; // [rsp+3D0h] [rbp+2D0h]
  __int64 v613[4]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v614[4]; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v615[4]; // [rsp+418h] [rbp+318h] BYREF
  __int64 v616[4]; // [rsp+438h] [rbp+338h] BYREF
  _BYTE v617[32]; // [rsp+458h] [rbp+358h] BYREF
  _BYTE v618[32]; // [rsp+478h] [rbp+378h] BYREF
  _BYTE v619[32]; // [rsp+498h] [rbp+398h] BYREF
  _BYTE v620[32]; // [rsp+4B8h] [rbp+3B8h] BYREF
  _BYTE v621[32]; // [rsp+4D8h] [rbp+3D8h] BYREF
  _BYTE v622[32]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v623[32]; // [rsp+518h] [rbp+418h] BYREF
  _BYTE v624[32]; // [rsp+538h] [rbp+438h] BYREF
  _BYTE v625[32]; // [rsp+558h] [rbp+458h] BYREF
  _BYTE v626[32]; // [rsp+578h] [rbp+478h] BYREF
  _BYTE v627[32]; // [rsp+598h] [rbp+498h] BYREF
  _BYTE v628[32]; // [rsp+5B8h] [rbp+4B8h] BYREF
  _BYTE v629[32]; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v630[32]; // [rsp+5F8h] [rbp+4F8h] BYREF
  _BYTE v631[32]; // [rsp+618h] [rbp+518h] BYREF
  _BYTE v632[32]; // [rsp+638h] [rbp+538h] BYREF
  _BYTE v633[32]; // [rsp+658h] [rbp+558h] BYREF
  _BYTE v634[32]; // [rsp+678h] [rbp+578h] BYREF
  _BYTE v635[32]; // [rsp+698h] [rbp+598h] BYREF
  _BYTE v636[32]; // [rsp+6B8h] [rbp+5B8h] BYREF
  _BYTE v637[32]; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v638[32]; // [rsp+6F8h] [rbp+5F8h] BYREF
  _BYTE v639[32]; // [rsp+718h] [rbp+618h] BYREF
  _BYTE v640[32]; // [rsp+738h] [rbp+638h] BYREF
  _BYTE v641[32]; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v642[32]; // [rsp+778h] [rbp+678h] BYREF
  _BYTE v643[32]; // [rsp+798h] [rbp+698h] BYREF
  _BYTE v644[32]; // [rsp+7B8h] [rbp+6B8h] BYREF
  _BYTE v645[32]; // [rsp+7D8h] [rbp+6D8h] BYREF
  _BYTE v646[32]; // [rsp+7F8h] [rbp+6F8h] BYREF
  _BYTE v647[32]; // [rsp+818h] [rbp+718h] BYREF
  _BYTE v648[32]; // [rsp+838h] [rbp+738h] BYREF
  _BYTE v649[32]; // [rsp+858h] [rbp+758h] BYREF
  _BYTE v650[32]; // [rsp+878h] [rbp+778h] BYREF
  _BYTE v651[32]; // [rsp+898h] [rbp+798h] BYREF
  _BYTE v652[32]; // [rsp+8B8h] [rbp+7B8h] BYREF
  _BYTE v653[32]; // [rsp+8D8h] [rbp+7D8h] BYREF
  _BYTE v654[32]; // [rsp+8F8h] [rbp+7F8h] BYREF
  _BYTE v655[32]; // [rsp+918h] [rbp+818h] BYREF
  _BYTE v656[32]; // [rsp+938h] [rbp+838h] BYREF
  _BYTE v657[32]; // [rsp+958h] [rbp+858h] BYREF
  _BYTE v658[32]; // [rsp+978h] [rbp+878h] BYREF
  _BYTE v659[32]; // [rsp+998h] [rbp+898h] BYREF
  _BYTE v660[32]; // [rsp+9B8h] [rbp+8B8h] BYREF
  _BYTE v661[32]; // [rsp+9D8h] [rbp+8D8h] BYREF
  _BYTE v662[8]; // [rsp+9F8h] [rbp+8F8h] BYREF
  std::_Ref_count_base *v663[2]; // [rsp+A00h] [rbp+900h] BYREF
  void *v664[2]; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v665; // [rsp+A20h] [rbp+920h]
  char v666; // [rsp+A28h] [rbp+928h]
  char *v667[2]; // [rsp+A30h] [rbp+930h] BYREF
  __m128i v668; // [rsp+A40h] [rbp+940h]
  std::_Ref_count_base *v669[2]; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v670; // [rsp+A60h] [rbp+960h]
  char v671; // [rsp+A68h] [rbp+968h]
  _QWORD v672[3]; // [rsp+A70h] [rbp+970h] BYREF
  unsigned __int64 v673; // [rsp+A88h] [rbp+988h]
  __int64 v674; // [rsp+A90h] [rbp+990h] BYREF
  void *v675; // [rsp+A98h] [rbp+998h] BYREF
  size_t v676; // [rsp+AA0h] [rbp+9A0h]
  __int64 v677; // [rsp+AA8h] [rbp+9A8h]
  void *v678[2]; // [rsp+AB0h] [rbp+9B0h] BYREF
  __m128i v679; // [rsp+AC0h] [rbp+9C0h]
  __int128 v680; // [rsp+AD0h] [rbp+9D0h] BYREF
  __m128i si128; // [rsp+AE0h] [rbp+9E0h]
  _QWORD v682[32]; // [rsp+AF0h] [rbp+9F0h] BYREF

  v2 = a2;
  v571 = a2;
  v4 = 0;
  LODWORD(p_Str) = 0;
  v680 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v680) = 0;
  *(_OWORD *)v667 = 0;
  v668 = si128;
  LOBYTE(v667[0]) = 0;
  v662[0] = *((_BYTE *)a2 + 24);
  v570 = *((_BYTE *)a2 + 25);
  v5 = v570;
  Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v672, *((_QWORD *)a2 + 1) + 80LL, 0, 6);
  if ( v570 )
    std::string::assign(v667, "(InfoOnly)");
  switch ( *(_BYTE *)v2 )
  {
    case 1:
      v485 = std::operator+<char>(&v580, v667, "LinkResumed");
      if ( v667 != (char **)v485 )
      {
        std::string::_Tidy_deallocate(v667);
        *(_OWORD *)v667 = *(_OWORD *)v485;
        v668 = *(__m128i *)(v485 + 16);
        *(_QWORD *)(v485 + 16) = 0;
        *(_QWORD *)(v485 + 24) = 15;
        *(_BYTE *)v485 = 0;
      }
      std::string::_Tidy_deallocate(&v580);
      if ( !v5 )
      {
        *(_OWORD *)v669 = 0;
        std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(*((_QWORD *)v2 + 1) + 120LL, v669);
        v486 = v669[0];
        if ( v669[0] )
        {
          v487 = *(_QWORD *)v669[0];
          v488 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v664 = 0;
          v489 = *(_QWORD *)(v488 + 112);
          if ( v489 )
            _InterlockedIncrement((volatile signed __int32 *)(v489 + 8));
          v664[0] = *(void **)(v488 + 104);
          v664[1] = *(void **)(v488 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, void **))(v487 + 8))(v486, v664);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v669);
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v663[0] = (std::_Ref_count_base *)v578;
        std::_Integral_to_string<char,unsigned int>(v593, *((unsigned int *)this + 373));
        v490 = std::string::string(v622, ":");
        v491 = std::string::string(v624, "\"");
        v492 = std::string::string(v625, "\"");
        v493 = std::operator+<char>(v626, v492, "NonIceDoR");
        LOBYTE(v494) = (_BYTE)v569;
        std::string::string(v594, v494, v493, v491);
        LOBYTE(v495) = (_BYTE)v569;
        std::string::string(v595, v495, v594, v490);
        LOBYTE(v496) = (_BYTE)v569;
        std::string::string(v578, v496, v595, v593);
        v669[0] = (std::_Ref_count_base *)v614;
        std::_Integral_to_string<char,unsigned int>(v596, *((unsigned int *)this + 372));
        v497 = std::string::string(v627, ":");
        v498 = std::string::string(v628, "\"");
        v499 = std::string::string(v629, "\"");
        v500 = std::operator+<char>(v623, v499, "IceDoR");
        LOBYTE(v501) = (_BYTE)v569;
        std::string::string(v597, v501, v500, v498);
        LOBYTE(v502) = (_BYTE)v569;
        std::string::string(v598, v502, v597, v497);
        LOBYTE(v503) = (_BYTE)v569;
        std::string::string(v614, v503, v598, v596);
        v612 = v613;
        std::_Integral_to_string<char,unsigned int>(v599, *((unsigned int *)this + 553));
        v504 = std::string::string(v611, ":");
        v505 = std::string::string(v640, "\"");
        v506 = std::string::string(v639, "\"");
        v507 = std::operator+<char>(v638, v506, "CurrentActiveNumLinks");
        LOBYTE(v508) = (_BYTE)v569;
        std::string::string(v600, v508, v507, v505);
        LOBYTE(v509) = (_BYTE)v569;
        std::string::string(v601, v509, v600, v504);
        LOBYTE(v510) = (_BYTE)v569;
        std::string::string(v613, v510, v601, v599);
        v606 = v616;
        v511 = std::string::string(v637, "\"");
        v512 = v672;
        if ( v673 > 0xF )
          v512 = (_QWORD *)v672[0];
        v513 = std::string::string(v636, "\"");
        v514 = std::string::string(v635, ":");
        v515 = std::string::string(v634, "\"");
        v516 = std::string::string(v633, "\"");
        v517 = std::operator+<char>(v632, v516, "ResumeLinkType");
        LOBYTE(v518) = (_BYTE)v569;
        std::string::string(v602, v518, v517, v515);
        LOBYTE(v519) = (_BYTE)v569;
        std::string::string(v603, v519, v602, v514);
        LOBYTE(v520) = (_BYTE)v569;
        std::string::string(v604, v520, v603, v513);
        v521 = std::operator+<char>(v631, v604, v512);
        LOBYTE(v522) = (_BYTE)v569;
        std::string::string(v616, v522, v521, v511);
        v574 = v615;
        std::_Integral_to_string<char,int>(v605, *((unsigned __int16 *)v571 + 1));
        v523 = std::string::string(v630, ":");
        v524 = std::string::string(v617, "\"");
        v525 = std::string::string(v649, "\"");
        v526 = std::operator+<char>(v650, v525, "ResumedLinkId");
        LOBYTE(v527) = (_BYTE)v569;
        std::string::string(v579, v527, v526, v524);
        LOBYTE(v528) = (_BYTE)v569;
        std::string::string(v607, v528, v579, v523);
        LOBYTE(v529) = (_BYTE)v569;
        std::string::string(v615, v529, v607, v605);
        v572 = (__int64 *)std::string::string(v651, "\"");
        v530 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v652, v662, 0, 6);
        v531 = v530;
        if ( v530[3] > 0xFu )
          v531 = (_QWORD *)*v530;
        v532 = std::string::string(v647, "\"");
        v533 = std::string::string(v653, ":");
        v534 = std::string::string(v654, "\"");
        v535 = std::string::string(v655, "\"");
        v536 = std::operator+<char>(v641, v535, "Direction");
        LOBYTE(v537) = (_BYTE)v569;
        std::string::string(v608, v537, v536, v534);
        LOBYTE(v538) = (_BYTE)v569;
        std::string::string(v609, v538, v608, v533);
        LOBYTE(v539) = (_BYTE)v569;
        std::string::string(v610, v539, v609, v532);
        v540 = std::operator+<char>(&v580, v610, v531);
        LOBYTE(v541) = (_BYTE)v569;
        std::string::string(v588, v541, v540, v572);
        v542 = (char *)v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          v542 = v667[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v664,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkResume",
          v542,
          (__int64)v588,
          (__int64)v615,
          (__int64)v616,
          (__int64)v613,
          (__int64)v614,
          (__int64)v578);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v579);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v605);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v611);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v593);
        v2 = v571;
        v5 = v570;
      }
      v543 = (volatile signed __int32 *)v664[1];
      if ( v664[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v664[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v543)(v543);
          if ( _InterlockedExchangeAdd(v543 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v543 + 8LL))(v543);
        }
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v571) = *((_DWORD *)this + 372);
        LODWORD(v575) = *((_DWORD *)this + 553);
        v544 = v672;
        if ( v673 > 0xF )
          v544 = (__int64 *)v672[0];
        v572 = v544;
        LOWORD(v569) = *((_WORD *)v2 + 1);
        v545 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v580, v662, 0, 6);
        v548 = (__int64)v545;
        if ( (unsigned __int64)v545[3] > 0xF )
          v548 = *v545;
        v549 = v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          LODWORD(v549) = v667[0];
        std::string::string(
          v578,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
          v546,
          v547,
          (_DWORD)v562,
          v563,
          (_DWORD)v564,
          v565,
          v566);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
          (unsigned int)v664,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v578,
          (_DWORD)v549,
          v548,
          (char)v569,
          (__int64)v572,
          (char)v575,
          (char)v571,
          p_Str);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(&v580);
      }
      goto LABEL_311;
    case 2:
      v403 = std::operator+<char>(&v580, v667, "LinkSuspended");
      if ( v667 != (char **)v403 )
      {
        std::string::_Tidy_deallocate(v667);
        *(_OWORD *)v667 = *(_OWORD *)v403;
        v668 = *(__m128i *)(v403 + 16);
        *(_QWORD *)(v403 + 16) = 0;
        *(_QWORD *)(v403 + 24) = 15;
        *(_BYTE *)v403 = 0;
      }
      std::string::_Tidy_deallocate(&v580);
      std::string::assign(&v680, "primaryLinkSuspended");
      if ( !v5 )
      {
        v404 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v669 = 0;
        v405 = *(_QWORD *)(v404 + 128);
        if ( v405 )
        {
          v406 = *(_DWORD *)(v405 + 8);
          while ( v406 )
          {
            v407 = v406;
            v406 = _InterlockedCompareExchange((volatile signed __int32 *)(v405 + 8), v406 + 1, v406);
            if ( v407 == v406 )
            {
              v408 = *(std::_Ref_count_base **)(v404 + 120);
              v669[0] = v408;
              v409 = *(std::_Ref_count_base **)(v404 + 128);
              v669[1] = v409;
              goto LABEL_249;
            }
          }
        }
        v408 = v669[0];
        v409 = v669[1];
LABEL_249:
        if ( v408 )
        {
          v410 = *(void (__fastcall ***)(std::_Ref_count_base *, void **))v408;
          v411 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v664 = 0;
          v412 = *(_QWORD *)(v411 + 112);
          if ( v412 )
            _InterlockedIncrement((volatile signed __int32 *)(v412 + 8));
          v664[0] = *(void **)(v411 + 104);
          v664[1] = *(void **)(v411 + 112);
          (*v410)(v408, v664);
        }
        if ( v409 )
          std::_Ref_count_base::_Decref(v409);
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v663[0] = (std::_Ref_count_base *)v578;
        v413 = std::string::string(v656, "\"");
        v414 = std::string::string(v648, "\"");
        v415 = std::string::string(v642, ":");
        v416 = std::string::string(v643, "\"");
        v417 = std::string::string(v644, "\"");
        v418 = std::operator+<char>(v645, v417, "reason");
        LOBYTE(v419) = (_BYTE)v569;
        std::string::string(v621, v419, v418, v416);
        LOBYTE(v420) = (_BYTE)v569;
        std::string::string(v618, v420, v621, v415);
        LOBYTE(v421) = (_BYTE)v569;
        std::string::string(v619, v421, v618, v414);
        v422 = std::operator+<char>(v646, v619, &v680);
        LOBYTE(v423) = (_BYTE)v569;
        std::string::string(v578, v423, v422, v413);
        v669[0] = (std::_Ref_count_base *)v614;
        std::_Integral_to_string<char,unsigned int>(v620, *((unsigned int *)this + 373));
        v424 = std::string::string(v622, ":");
        v425 = std::string::string(v624, "\"");
        v426 = std::string::string(v625, "\"");
        v427 = std::operator+<char>(v626, v426, "NonIceDoR");
        LOBYTE(v428) = (_BYTE)v569;
        std::string::string(v593, v428, v427, v425);
        LOBYTE(v429) = (_BYTE)v569;
        std::string::string(v594, v429, v593, v424);
        LOBYTE(v430) = (_BYTE)v569;
        std::string::string(v614, v430, v594, v620);
        v612 = v613;
        std::_Integral_to_string<char,unsigned int>(v595, *((unsigned int *)this + 372));
        v431 = std::string::string(v627, ":");
        v432 = std::string::string(v628, "\"");
        v433 = std::string::string(v629, "\"");
        v434 = std::operator+<char>(v623, v433, "IceDoR");
        LOBYTE(v435) = (_BYTE)v569;
        std::string::string(v596, v435, v434, v432);
        LOBYTE(v436) = (_BYTE)v569;
        std::string::string(v597, v436, v596, v431);
        LOBYTE(v437) = (_BYTE)v569;
        std::string::string(v613, v437, v597, v595);
        v606 = v616;
        std::_Integral_to_string<char,unsigned int>(v598, *((unsigned int *)this + 553));
        v438 = std::string::string(v611, ":");
        v439 = std::string::string(v640, "\"");
        v440 = std::string::string(v639, "\"");
        v441 = std::operator+<char>(v638, v440, "CurrentActiveNumLinks");
        LOBYTE(v442) = (_BYTE)v569;
        std::string::string(v599, v442, v441, v439);
        LOBYTE(v443) = (_BYTE)v569;
        std::string::string(v600, v443, v599, v438);
        LOBYTE(v444) = (_BYTE)v569;
        std::string::string(v616, v444, v600, v598);
        v574 = v615;
        v445 = std::string::string(v637, "\"");
        v446 = v672;
        if ( v673 > 0xF )
          v446 = (_QWORD *)v672[0];
        v447 = std::string::string(v636, "\"");
        v448 = std::string::string(v635, ":");
        v449 = std::string::string(v634, "\"");
        v450 = std::string::string(v633, "\"");
        v451 = std::operator+<char>(v632, v450, "SuspendLinkType");
        LOBYTE(v452) = (_BYTE)v569;
        std::string::string(v601, v452, v451, v449);
        LOBYTE(v453) = (_BYTE)v569;
        std::string::string(v602, v453, v601, v448);
        LOBYTE(v454) = (_BYTE)v569;
        std::string::string(v603, v454, v602, v447);
        v455 = std::operator+<char>(v631, v603, v446);
        LOBYTE(v456) = (_BYTE)v569;
        std::string::string(v615, v456, v455, v445);
        v577 = (__int64)v588;
        std::_Integral_to_string<char,int>(v604, *((unsigned __int16 *)v571 + 1));
        v457 = std::string::string(v630, ":");
        v458 = std::string::string(v617, "\"");
        v459 = std::string::string(v649, "\"");
        v460 = std::operator+<char>(v650, v459, "SuspendLinkId");
        LOBYTE(v461) = (_BYTE)v569;
        std::string::string(v605, v461, v460, v458);
        LOBYTE(v462) = (_BYTE)v569;
        std::string::string(v579, v462, v605, v457);
        LOBYTE(v463) = (_BYTE)v569;
        std::string::string(v588, v463, v579, v604);
        v572 = (__int64 *)std::string::string(v651, "\"");
        v464 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v652, v662, 0, 6);
        v465 = v464;
        if ( v464[3] > 0xFu )
          v465 = (_QWORD *)*v464;
        v466 = std::string::string(v647, "\"");
        v467 = std::string::string(v653, ":");
        v468 = std::string::string(v654, "\"");
        v469 = std::string::string(v655, "\"");
        v470 = std::operator+<char>(v641, v469, "Direction");
        LOBYTE(v471) = (_BYTE)v569;
        std::string::string(v607, v471, v470, v468);
        LOBYTE(v472) = (_BYTE)v569;
        std::string::string(v608, v472, v607, v467);
        LOBYTE(v473) = (_BYTE)v569;
        std::string::string(v609, v473, v608, v466);
        v474 = std::operator+<char>(&v580, v609, v465);
        LOBYTE(v475) = (_BYTE)v569;
        std::string::string(v610, v475, v474, v572);
        v476 = (char *)v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          v476 = v667[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v664,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSuspend",
          v476,
          (__int64)v610,
          (__int64)v588,
          (__int64)v615,
          (__int64)v616,
          (__int64)v613,
          (__int64)v614,
          (__int64)v578);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v579);
        std::string::_Tidy_deallocate(v605);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v611);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v656);
        v2 = v571;
        v5 = v570;
      }
      v477 = (volatile signed __int32 *)v664[1];
      if ( v664[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v664[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v477)(v477);
          if ( _InterlockedExchangeAdd(v477 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v477 + 8LL))(v477);
        }
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v478 = (__int64 *)&v680;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v478 = (__int64 *)v680;
        v572 = v478;
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v571) = *((_DWORD *)this + 372);
        LODWORD(v575) = *((_DWORD *)this + 553);
        v479 = v672;
        if ( v673 > 0xF )
          v479 = (__int64 *)v672[0];
        v574 = v479;
        LOWORD(v569) = *((_WORD *)v2 + 1);
        v480 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v580, v662, 0, 6);
        v483 = (__int64)v480;
        if ( (unsigned __int64)v480[3] > 0xF )
          v483 = *v480;
        v484 = v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          LODWORD(v484) = v667[0];
        std::string::string(
          v578,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s",
          v481,
          v482,
          (_DWORD)v562,
          v563,
          (_DWORD)v564,
          v565,
          v566,
          v567);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
          (unsigned int)v664,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v578,
          (_DWORD)v484,
          v483,
          (char)v569,
          (__int64)v574,
          (char)v575,
          (char)v571,
          p_Str,
          (__int64)v572);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(&v580);
      }
      goto LABEL_311;
    case 3:
      v338 = std::operator+<char>(&v580, v667, "LinkRemoved");
      if ( v667 != (char **)v338 )
      {
        std::string::_Tidy_deallocate(v667);
        *(_OWORD *)v667 = *(_OWORD *)v338;
        v668 = *(__m128i *)(v338 + 16);
        *(_QWORD *)(v338 + 16) = 0;
        *(_QWORD *)(v338 + 24) = 15;
        *(_BYTE *)v338 = 0;
      }
      std::string::_Tidy_deallocate(&v580);
      if ( !v5 )
      {
        *(_OWORD *)v669 = 0;
        std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(*((_QWORD *)v2 + 1) + 120LL, v669);
        v339 = v669[0];
        if ( v669[0] )
        {
          v340 = *(_QWORD *)v669[0];
          v341 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v664 = 0;
          v342 = *(_QWORD *)(v341 + 112);
          if ( v342 )
            _InterlockedIncrement((volatile signed __int32 *)(v342 + 8));
          v664[0] = *(void **)(v341 + 104);
          v664[1] = *(void **)(v341 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, void **))(v340 + 16))(v339, v664);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v669);
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v663[0] = (std::_Ref_count_base *)v578;
        std::_Integral_to_string<char,unsigned int>(v593, *((unsigned int *)this + 373));
        v343 = std::string::string(v622, ":");
        v344 = std::string::string(v624, "\"");
        v345 = std::string::string(v625, "\"");
        v346 = std::operator+<char>(v626, v345, "NonIceDoR");
        LOBYTE(v347) = (_BYTE)v569;
        std::string::string(v594, v347, v346, v344);
        LOBYTE(v348) = (_BYTE)v569;
        std::string::string(v595, v348, v594, v343);
        LOBYTE(v349) = (_BYTE)v569;
        std::string::string(v578, v349, v595, v593);
        v669[0] = (std::_Ref_count_base *)v614;
        std::_Integral_to_string<char,unsigned int>(v596, *((unsigned int *)this + 372));
        v350 = std::string::string(v627, ":");
        v351 = std::string::string(v628, "\"");
        v352 = std::string::string(v629, "\"");
        v353 = std::operator+<char>(v623, v352, "IceDoR");
        LOBYTE(v354) = (_BYTE)v569;
        std::string::string(v597, v354, v353, v351);
        LOBYTE(v355) = (_BYTE)v569;
        std::string::string(v598, v355, v597, v350);
        LOBYTE(v356) = (_BYTE)v569;
        std::string::string(v614, v356, v598, v596);
        v612 = v613;
        std::_Integral_to_string<char,unsigned int>(v599, *((unsigned int *)this + 553));
        v357 = std::string::string(v611, ":");
        v358 = std::string::string(v640, "\"");
        v359 = std::string::string(v639, "\"");
        v360 = std::operator+<char>(v638, v359, "CurrentActiveNumLinks");
        LOBYTE(v361) = (_BYTE)v569;
        std::string::string(v600, v361, v360, v358);
        LOBYTE(v362) = (_BYTE)v569;
        std::string::string(v601, v362, v600, v357);
        LOBYTE(v363) = (_BYTE)v569;
        std::string::string(v613, v363, v601, v599);
        v606 = v616;
        v364 = std::string::string(v637, "\"");
        v365 = v672;
        if ( v673 > 0xF )
          v365 = (_QWORD *)v672[0];
        v366 = std::string::string(v636, "\"");
        v367 = std::string::string(v635, ":");
        v368 = std::string::string(v634, "\"");
        v369 = std::string::string(v633, "\"");
        v370 = std::operator+<char>(v632, v369, "RemovedLinkType");
        LOBYTE(v371) = (_BYTE)v569;
        std::string::string(v602, v371, v370, v368);
        LOBYTE(v372) = (_BYTE)v569;
        std::string::string(v603, v372, v602, v367);
        LOBYTE(v373) = (_BYTE)v569;
        std::string::string(v604, v373, v603, v366);
        v374 = std::operator+<char>(v631, v604, v365);
        LOBYTE(v375) = (_BYTE)v569;
        std::string::string(v616, v375, v374, v364);
        v574 = v615;
        std::_Integral_to_string<char,int>(v605, *((unsigned __int16 *)v571 + 1));
        v376 = std::string::string(v630, ":");
        v377 = std::string::string(v617, "\"");
        v378 = std::string::string(v649, "\"");
        v379 = std::operator+<char>(v650, v378, "RemovedLinkId");
        LOBYTE(v380) = (_BYTE)v569;
        std::string::string(v579, v380, v379, v377);
        LOBYTE(v381) = (_BYTE)v569;
        std::string::string(v607, v381, v579, v376);
        LOBYTE(v382) = (_BYTE)v569;
        std::string::string(v615, v382, v607, v605);
        v572 = (__int64 *)std::string::string(v651, "\"");
        v383 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v652, v662, 0, 6);
        v384 = v383;
        if ( v383[3] > 0xFu )
          v384 = (_QWORD *)*v383;
        v385 = std::string::string(v647, "\"");
        v386 = std::string::string(v653, ":");
        v387 = std::string::string(v654, "\"");
        v388 = std::string::string(v655, "\"");
        v389 = std::operator+<char>(v641, v388, "Direction");
        LOBYTE(v390) = (_BYTE)v569;
        std::string::string(v608, v390, v389, v387);
        LOBYTE(v391) = (_BYTE)v569;
        std::string::string(v609, v391, v608, v386);
        LOBYTE(v392) = (_BYTE)v569;
        std::string::string(v610, v392, v609, v385);
        v393 = std::operator+<char>(&v580, v610, v384);
        LOBYTE(v394) = (_BYTE)v569;
        std::string::string(v588, v394, v393, v572);
        v395 = (char *)v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          v395 = v667[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v664,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkRemove",
          v395,
          (__int64)v588,
          (__int64)v615,
          (__int64)v616,
          (__int64)v613,
          (__int64)v614,
          (__int64)v578);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v610);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v579);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v605);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v611);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v593);
        v2 = v571;
        v5 = v570;
      }
      v396 = (volatile signed __int32 *)v664[1];
      if ( v664[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v664[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v396)(v396);
          if ( _InterlockedExchangeAdd(v396 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v396 + 8LL))(v396);
        }
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v571) = *((_DWORD *)this + 372);
        LODWORD(v575) = *((_DWORD *)this + 553);
        v397 = v672;
        if ( v673 > 0xF )
          v397 = (__int64 *)v672[0];
        v572 = v397;
        LOWORD(v569) = *((_WORD *)v2 + 1);
        v398 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v580, v662, 0, 6);
        v401 = (__int64)v398;
        if ( (unsigned __int64)v398[3] > 0xF )
          v401 = *v398;
        v402 = v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          LODWORD(v402) = v667[0];
        std::string::string(
          v578,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
          v399,
          v400,
          (_DWORD)v562,
          v563,
          (_DWORD)v564,
          v565,
          v566);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
          (unsigned int)v664,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v578,
          (_DWORD)v402,
          v401,
          (char)v569,
          (__int64)v572,
          (char)v575,
          (char)v571,
          p_Str);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(&v580);
      }
LABEL_311:
      v76 = (volatile signed __int32 *)v664[1];
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
      v256 = std::operator+<char>(&v580, v667, "LinkSuspended");
      if ( v667 != (char **)v256 )
      {
        std::string::_Tidy_deallocate(v667);
        *(_OWORD *)v667 = *(_OWORD *)v256;
        v668 = *(__m128i *)(v256 + 16);
        *(_QWORD *)(v256 + 16) = 0;
        *(_QWORD *)(v256 + 24) = 15;
        *(_BYTE *)v256 = 0;
      }
      std::string::_Tidy_deallocate(&v580);
      std::string::assign(&v680, "linkSuspendedDueToTimeout");
      if ( !v5 )
      {
        v257 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v669 = 0;
        v258 = *(_QWORD *)(v257 + 128);
        if ( v258 )
        {
          v259 = *(_DWORD *)(v258 + 8);
          while ( v259 )
          {
            v260 = v259;
            v259 = _InterlockedCompareExchange((volatile signed __int32 *)(v258 + 8), v259 + 1, v259);
            if ( v260 == v259 )
            {
              v261 = *(std::_Ref_count_base **)(v257 + 120);
              v669[0] = v261;
              v262 = *(std::_Ref_count_base **)(v257 + 128);
              v669[1] = v262;
              goto LABEL_178;
            }
          }
        }
        v261 = v669[0];
        v262 = v669[1];
LABEL_178:
        if ( v261 )
        {
          v263 = *(void (__fastcall ***)(std::_Ref_count_base *, void **))v261;
          v264 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v664 = 0;
          v265 = *(_QWORD *)(v264 + 112);
          if ( v265 )
            _InterlockedIncrement((volatile signed __int32 *)(v265 + 8));
          v664[0] = *(void **)(v264 + 104);
          v664[1] = *(void **)(v264 + 112);
          (*v263)(v261, v664);
        }
        if ( v262 )
          std::_Ref_count_base::_Decref(v262);
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v663[0] = (std::_Ref_count_base *)v578;
        v266 = std::string::string(v656, "\"");
        v267 = std::string::string(v648, "\"");
        v268 = std::string::string(v642, ":");
        v269 = std::string::string(v643, "\"");
        v270 = std::string::string(v644, "\"");
        v271 = std::operator+<char>(v645, v270, "reason");
        LOBYTE(v272) = (_BYTE)v569;
        std::string::string(v621, v272, v271, v269);
        LOBYTE(v273) = (_BYTE)v569;
        std::string::string(v618, v273, v621, v268);
        LOBYTE(v274) = (_BYTE)v569;
        std::string::string(v619, v274, v618, v267);
        v275 = std::operator+<char>(v646, v619, &v680);
        LOBYTE(v276) = (_BYTE)v569;
        std::string::string(v578, v276, v275, v266);
        v669[0] = (std::_Ref_count_base *)v614;
        std::_Integral_to_string<char,unsigned int>(v620, *((unsigned int *)this + 373));
        v277 = std::string::string(v622, ":");
        v278 = std::string::string(v624, "\"");
        v279 = std::string::string(v625, "\"");
        v280 = std::operator+<char>(v626, v279, "NonIceDoR");
        LOBYTE(v281) = (_BYTE)v569;
        std::string::string(v593, v281, v280, v278);
        LOBYTE(v282) = (_BYTE)v569;
        std::string::string(v594, v282, v593, v277);
        LOBYTE(v283) = (_BYTE)v569;
        std::string::string(v614, v283, v594, v620);
        v612 = v613;
        std::_Integral_to_string<char,unsigned int>(v595, *((unsigned int *)this + 372));
        v284 = std::string::string(v627, ":");
        v285 = std::string::string(v628, "\"");
        v286 = std::string::string(v629, "\"");
        v287 = std::operator+<char>(v623, v286, "IceDoR");
        LOBYTE(v288) = (_BYTE)v569;
        std::string::string(v596, v288, v287, v285);
        LOBYTE(v289) = (_BYTE)v569;
        std::string::string(v597, v289, v596, v284);
        LOBYTE(v290) = (_BYTE)v569;
        std::string::string(v613, v290, v597, v595);
        v606 = v616;
        std::_Integral_to_string<char,unsigned int>(v598, *((unsigned int *)this + 553));
        v291 = std::string::string(v611, ":");
        v292 = std::string::string(v640, "\"");
        v293 = std::string::string(v639, "\"");
        v294 = std::operator+<char>(v638, v293, "CurrentActiveNumLinks");
        LOBYTE(v295) = (_BYTE)v569;
        std::string::string(v599, v295, v294, v292);
        LOBYTE(v296) = (_BYTE)v569;
        std::string::string(v600, v296, v599, v291);
        LOBYTE(v297) = (_BYTE)v569;
        std::string::string(v616, v297, v600, v598);
        v574 = v615;
        v298 = std::string::string(v637, "\"");
        v299 = v672;
        if ( v673 > 0xF )
          v299 = (_QWORD *)v672[0];
        v300 = std::string::string(v636, "\"");
        v301 = std::string::string(v635, ":");
        v302 = std::string::string(v634, "\"");
        v303 = std::string::string(v633, "\"");
        v304 = std::operator+<char>(v632, v303, "SuspendLinkType");
        LOBYTE(v305) = (_BYTE)v569;
        std::string::string(v601, v305, v304, v302);
        LOBYTE(v306) = (_BYTE)v569;
        std::string::string(v602, v306, v601, v301);
        LOBYTE(v307) = (_BYTE)v569;
        std::string::string(v603, v307, v602, v300);
        v308 = std::operator+<char>(v631, v603, v299);
        LOBYTE(v309) = (_BYTE)v569;
        std::string::string(v615, v309, v308, v298);
        v577 = (__int64)v588;
        std::_Integral_to_string<char,int>(v604, *((unsigned __int16 *)v571 + 1));
        v310 = std::string::string(v630, ":");
        v311 = std::string::string(v617, "\"");
        v312 = std::string::string(v649, "\"");
        v313 = std::operator+<char>(v650, v312, "SuspendLinkId");
        LOBYTE(v314) = (_BYTE)v569;
        std::string::string(v605, v314, v313, v311);
        v4 = -1024;
        LOBYTE(v315) = (_BYTE)v569;
        std::string::string(v579, v315, v605, v310);
        LOBYTE(v316) = (_BYTE)v569;
        std::string::string(v588, v316, v579, v604);
        v572 = (__int64 *)std::string::string(v651, "\"");
        v317 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v652, v662, 0, 6);
        v318 = v317;
        if ( v317[3] > 0xFu )
          v318 = (_QWORD *)*v317;
        v319 = std::string::string(v647, "\"");
        v320 = std::string::string(v653, ":");
        v321 = std::string::string(v654, "\"");
        v322 = std::string::string(v655, "\"");
        v323 = std::operator+<char>(v641, v322, "Direction");
        LOBYTE(v324) = (_BYTE)v569;
        std::string::string(v607, v324, v323, v321);
        LOBYTE(v325) = (_BYTE)v569;
        std::string::string(v608, v325, v607, v320);
        LOBYTE(v326) = (_BYTE)v569;
        std::string::string(v609, v326, v608, v319);
        v327 = std::operator+<char>(&v580, v609, v318);
        LOBYTE(v328) = (_BYTE)v569;
        std::string::string(v610, v328, v327, v572);
        v329 = (char *)v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          v329 = v667[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v664,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSuspend",
          v329,
          (__int64)v610,
          (__int64)v588,
          (__int64)v615,
          (__int64)v616,
          (__int64)v613,
          (__int64)v614,
          (__int64)v578);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v609);
        std::string::_Tidy_deallocate(v608);
        std::string::_Tidy_deallocate(v607);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v579);
        std::string::_Tidy_deallocate(v605);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v604);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v611);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v656);
        v2 = v571;
        v5 = v570;
      }
      v330 = (volatile signed __int32 *)v664[1];
      if ( v664[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v664[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v330)(v330);
          if ( _InterlockedExchangeAdd(v330 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v330 + 8LL))(v330);
        }
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v331 = (__int64 *)&v680;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v331 = (__int64 *)v680;
        v572 = v331;
        LODWORD(p_Str) = *((_DWORD *)this + 373);
        LODWORD(v571) = *((_DWORD *)this + 372);
        LODWORD(v575) = *((_DWORD *)this + 553);
        v332 = v672;
        if ( v673 > 0xF )
          v332 = (__int64 *)v672[0];
        v574 = v332;
        LOWORD(v569) = *((_WORD *)v2 + 1);
        v333 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(&v580, v662, 0, 6);
        v336 = (__int64)v333;
        if ( (unsigned __int64)v333[3] > 0xF )
          v336 = *v333;
        v337 = v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          LODWORD(v337) = v667[0];
        std::string::string(
          v578,
          "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, reason=%s",
          v334,
          v335,
          (_DWORD)v562,
          v563,
          (_DWORD)v564,
          v565,
          v566,
          v567);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
          (unsigned int)v664,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v578,
          (_DWORD)v337,
          v336,
          (char)v569,
          (__int64)v574,
          (char)v575,
          (char)v571,
          p_Str,
          (__int64)v572);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(&v580);
      }
      goto LABEL_311;
    case 5:
      LODWORD(v577) = 0;
      v167 = *((_QWORD *)v2 + 1);
      if ( v662[0] )
      {
        LODWORD(v576) = *(_DWORD *)(v167 + 288);
        if ( (_DWORD)v576 == 1 )
          LODWORD(v577) = (*(_QWORD *)(v167 + 264) - *((_QWORD *)this + 376)) / 1000LL;
      }
      else
      {
        LODWORD(v576) = *(_DWORD *)(v167 + 292);
        if ( (_DWORD)v576 == 1 )
          v577 = (*(_QWORD *)(v167 + 272) - *((_QWORD *)this + 376)) / 1000LL;
      }
      v168 = std::operator+<char>(v617, v667, "LinkRemovedAtClose");
      if ( v667 != (char **)v168 )
      {
        std::string::_Tidy_deallocate(v667);
        *(_OWORD *)v667 = *(_OWORD *)v168;
        v668 = *(__m128i *)(v168 + 16);
        *(_QWORD *)(v168 + 16) = 0;
        *(_QWORD *)(v168 + 24) = 15;
        *(_BYTE *)v168 = 0;
      }
      std::string::_Tidy_deallocate(v617);
      if ( !v5 )
      {
        v169 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v663 = 0;
        v170 = *(_QWORD *)(v169 + 128);
        if ( v170 )
        {
          v171 = *(_DWORD *)(v170 + 8);
          while ( v171 )
          {
            v172 = v171;
            v171 = _InterlockedCompareExchange((volatile signed __int32 *)(v170 + 8), v171 + 1, v171);
            if ( v172 == v171 )
            {
              v173 = *(std::_Ref_count_base **)(v169 + 120);
              v663[0] = v173;
              v174 = *(std::_Ref_count_base **)(v169 + 128);
              v663[1] = v174;
              goto LABEL_136;
            }
          }
        }
        v173 = v663[0];
        v174 = v663[1];
LABEL_136:
        if ( v173 )
        {
          v175 = *(_QWORD *)v173;
          v176 = *((_QWORD *)v2 + 1);
          *(_OWORD *)v669 = 0;
          v177 = *(_QWORD *)(v176 + 112);
          if ( v177 )
            _InterlockedIncrement((volatile signed __int32 *)(v177 + 8));
          v669[0] = *(std::_Ref_count_base **)(v176 + 104);
          v669[1] = *(std::_Ref_count_base **)(v176 + 112);
          (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v175 + 16))(v173, v669);
        }
        if ( v174 )
          std::_Ref_count_base::_Decref(v174);
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        v572 = v588;
        std::_Integral_to_string<char,unsigned int>(v578, *((unsigned int *)this + 373));
        v178 = std::string::string(&v580, ":");
        v179 = std::string::string(v641, "\"");
        v180 = std::string::string(v655, "\"");
        v181 = std::operator+<char>(v654, v180, "NonIceDoR");
        LOBYTE(v182) = (_BYTE)v569;
        std::string::string(v614, v182, v181, v179);
        LOBYTE(v183) = (_BYTE)v569;
        std::string::string(v613, v183, v614, v178);
        LOBYTE(v184) = (_BYTE)v569;
        std::string::string(v588, v184, v613, v578);
        v575 = v610;
        std::_Integral_to_string<char,unsigned int>(v616, *((unsigned int *)this + 372));
        v185 = std::string::string(v653, ":");
        v186 = std::string::string(v647, "\"");
        v187 = std::string::string(v652, "\"");
        v188 = std::operator+<char>(v651, v187, "IceDoR");
        LOBYTE(v189) = (_BYTE)v569;
        std::string::string(v615, v189, v188, v186);
        LOBYTE(v190) = (_BYTE)v569;
        std::string::string(v678, v190, v615, v185);
        LOBYTE(v191) = (_BYTE)v569;
        std::string::string(v610, v191, v678, v616);
        v569 = v609;
        std::_Integral_to_string<char,unsigned int>(&Str, *((unsigned int *)this + 553));
        v192 = std::string::string(v650, ":");
        v193 = std::string::string(v649, "\"");
        v194 = std::string::string(v659, "\"");
        v195 = std::operator+<char>(v661, v194, "CurrentActiveNumLinks");
        LOBYTE(v196) = (unsigned __int8)v609;
        std::string::string(&v584, v196, v195, v193);
        LOBYTE(v197) = (unsigned __int8)v609;
        std::string::string(&v674, v197, &v584, v192);
        LOBYTE(v198) = (unsigned __int8)v609;
        std::string::string(v609, v198, &v674, &Str);
        v606 = v608;
        v199 = std::string::string(v660, "\"");
        v200 = v672;
        if ( v673 > 0xF )
          v200 = (_QWORD *)v672[0];
        v201 = std::string::string(v658, "\"");
        v202 = std::string::string(v657, ":");
        v203 = std::string::string(v656, "\"");
        v204 = std::string::string(v648, "\"");
        v205 = std::operator+<char>(v642, v204, "RemovedLinkType");
        LOBYTE(v206) = (_BYTE)v569;
        std::string::string(v621, v206, v205, v203);
        LOBYTE(v207) = (_BYTE)v569;
        std::string::string(v618, v207, v621, v202);
        LOBYTE(v208) = (_BYTE)v569;
        std::string::string(v619, v208, v618, v201);
        v209 = std::operator+<char>(v643, v619, v200);
        LOBYTE(v210) = (_BYTE)v569;
        std::string::string(v608, v210, v209, v199);
        v612 = v607;
        std::_Integral_to_string<char,int>(v620, *((unsigned __int16 *)v571 + 1));
        v211 = std::string::string(v644, ":");
        v212 = std::string::string(v645, "\"");
        v213 = std::string::string(v646, "\"");
        v214 = std::operator+<char>(v622, v213, "RemovedLinkId");
        LOBYTE(v215) = (_BYTE)v569;
        std::string::string(v593, v215, v214, v212);
        LOBYTE(v216) = (_BYTE)v569;
        std::string::string(v594, v216, v593, v211);
        LOBYTE(v217) = (_BYTE)v569;
        std::string::string(v607, v217, v594, v620);
        v669[0] = (std::_Ref_count_base *)v579;
        std::_Integral_to_string<char,int>(v595, (unsigned int)v577);
        v218 = std::string::string(v624, ":");
        v219 = std::string::string(v625, "\"");
        v220 = std::string::string(v626, "\"");
        v221 = std::operator+<char>(v627, v220, "SuspendTimeInSec");
        LOBYTE(v222) = (_BYTE)v569;
        std::string::string(v596, v222, v221, v219);
        LOBYTE(v223) = (_BYTE)v569;
        std::string::string(v597, v223, v596, v218);
        LOBYTE(v224) = (_BYTE)v569;
        std::string::string(v579, v224, v597, v595);
        v663[0] = (std::_Ref_count_base *)v605;
        v574 = (__int64 *)std::string::string(v628, "\"");
        v225 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkDataV3::State>(v629, &v576, 0, 6);
        p_Str = v225;
        if ( *(_QWORD *)(v225 + 24) > 0xFu )
          p_Str = *(_QWORD *)v225;
        v226 = std::string::string(v623, "\"");
        v227 = std::string::string(v611, ":");
        v228 = std::string::string(v640, "\"");
        v229 = std::string::string(v639, "\"");
        v230 = std::operator+<char>(v638, v229, "StateBeforeRemove");
        LOBYTE(v231) = (_BYTE)v569;
        std::string::string(v598, v231, v230, v228);
        LOBYTE(v232) = (_BYTE)v569;
        std::string::string(v599, v232, v598, v227);
        LOBYTE(v233) = (_BYTE)v569;
        std::string::string(v600, v233, v599, v226);
        v234 = std::operator+<char>(v637, v600, p_Str);
        LOBYTE(v235) = (_BYTE)v569;
        std::string::string(v605, v235, v234, v574);
        v574 = (__int64 *)std::string::string(v636, "\"");
        v236 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v635, v662, 0, 6);
        p_Str = v236;
        if ( *(_QWORD *)(v236 + 24) > 0xFu )
          p_Str = *(_QWORD *)v236;
        v237 = std::string::string(v634, "\"");
        v238 = std::string::string(v633, ":");
        v239 = std::string::string(v632, "\"");
        v240 = std::string::string(v631, "\"");
        v241 = std::operator+<char>(v630, v240, "Direction");
        LOBYTE(v242) = (_BYTE)v569;
        std::string::string(v601, v242, v241, v239);
        LOBYTE(v243) = (_BYTE)v569;
        std::string::string(v602, v243, v601, v238);
        LOBYTE(v244) = (_BYTE)v569;
        std::string::string(v603, v244, v602, v237);
        v245 = std::operator+<char>(v617, v603, p_Str);
        LOBYTE(v246) = (_BYTE)v569;
        std::string::string(v604, v246, v245, v574);
        v247 = (char *)v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          v247 = v667[0];
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
          (int)v664,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkRemove",
          v247,
          (__int64)v604,
          (__int64)v605,
          (__int64)v579,
          (__int64)v607,
          (__int64)v608,
          (__int64)v609,
          (__int64)v610,
          (__int64)v588);
        std::string::_Tidy_deallocate(v617);
        std::string::_Tidy_deallocate(v603);
        std::string::_Tidy_deallocate(v602);
        std::string::_Tidy_deallocate(v601);
        std::string::_Tidy_deallocate(v630);
        std::string::_Tidy_deallocate(v631);
        std::string::_Tidy_deallocate(v632);
        std::string::_Tidy_deallocate(v633);
        std::string::_Tidy_deallocate(v634);
        std::string::_Tidy_deallocate(v635);
        std::string::_Tidy_deallocate(v636);
        std::string::_Tidy_deallocate(v637);
        std::string::_Tidy_deallocate(v600);
        std::string::_Tidy_deallocate(v599);
        std::string::_Tidy_deallocate(v598);
        std::string::_Tidy_deallocate(v638);
        std::string::_Tidy_deallocate(v639);
        std::string::_Tidy_deallocate(v640);
        std::string::_Tidy_deallocate(v611);
        std::string::_Tidy_deallocate(v623);
        std::string::_Tidy_deallocate(v629);
        std::string::_Tidy_deallocate(v628);
        std::string::_Tidy_deallocate(v597);
        std::string::_Tidy_deallocate(v596);
        std::string::_Tidy_deallocate(v627);
        std::string::_Tidy_deallocate(v626);
        std::string::_Tidy_deallocate(v625);
        std::string::_Tidy_deallocate(v624);
        std::string::_Tidy_deallocate(v595);
        std::string::_Tidy_deallocate(v594);
        std::string::_Tidy_deallocate(v593);
        std::string::_Tidy_deallocate(v622);
        std::string::_Tidy_deallocate(v646);
        std::string::_Tidy_deallocate(v645);
        std::string::_Tidy_deallocate(v644);
        std::string::_Tidy_deallocate(v620);
        std::string::_Tidy_deallocate(v643);
        std::string::_Tidy_deallocate(v619);
        std::string::_Tidy_deallocate(v618);
        std::string::_Tidy_deallocate(v621);
        std::string::_Tidy_deallocate(v642);
        std::string::_Tidy_deallocate(v648);
        std::string::_Tidy_deallocate(v656);
        std::string::_Tidy_deallocate(v657);
        std::string::_Tidy_deallocate(v658);
        std::string::_Tidy_deallocate(v660);
        std::string::_Tidy_deallocate(&v674);
        std::string::_Tidy_deallocate(&v584);
        std::string::_Tidy_deallocate(v661);
        std::string::_Tidy_deallocate(v659);
        std::string::_Tidy_deallocate(v649);
        std::string::_Tidy_deallocate(v650);
        std::string::_Tidy_deallocate(&Str);
        std::string::_Tidy_deallocate(v678);
        std::string::_Tidy_deallocate(v615);
        std::string::_Tidy_deallocate(v651);
        std::string::_Tidy_deallocate(v652);
        std::string::_Tidy_deallocate(v647);
        std::string::_Tidy_deallocate(v653);
        std::string::_Tidy_deallocate(v616);
        std::string::_Tidy_deallocate(v613);
        std::string::_Tidy_deallocate(v614);
        std::string::_Tidy_deallocate(v654);
        std::string::_Tidy_deallocate(v655);
        std::string::_Tidy_deallocate(v641);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v578);
        v2 = v571;
        v5 = v570;
      }
      v248 = (volatile signed __int32 *)v664[1];
      if ( v664[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v664[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v248)(v248);
          if ( _InterlockedExchangeAdd(v248 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v248 + 8LL))(v248);
        }
      }
      *(_OWORD *)v664 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v664);
      if ( v664[0] && *((_BYTE *)v664[0] + 128) )
      {
        LODWORD(v571) = *((_DWORD *)this + 373);
        LODWORD(v575) = *((_DWORD *)this + 372);
        LODWORD(p_Str) = *((_DWORD *)this + 553);
        v249 = v672;
        if ( v673 > 0xF )
          v249 = (__int64 *)v672[0];
        v572 = v249;
        LOWORD(v569) = *((_WORD *)v2 + 1);
        v250 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v641, v662, 0, 6);
        v574 = v250;
        if ( (unsigned __int64)v250[3] > 0xF )
          v574 = (__int64 *)*v250;
        v251 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkDataV3::State>(&v580, &v576, 0, 6);
        v254 = (__int64)v251;
        if ( (unsigned __int64)v251[3] > 0xF )
          v254 = *v251;
        v255 = v667;
        if ( v668.m128i_i64[1] > 0xFuLL )
          LODWORD(v255) = v667[0];
        std::string::string(
          v578,
          "Checkpoint.SMILES.%s(%s|%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, suspendTimeInSec=%d",
          v252,
          v253,
          v562,
          (_DWORD)v563,
          v564,
          v565,
          v566,
          (_DWORD)v567,
          v568);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,int>(
          (unsigned int)v664,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v578,
          (_DWORD)v255,
          v254,
          (__int64)v574,
          (char)v569,
          (__int64)v572,
          p_Str,
          (char)v575,
          (char)v571,
          v577);
        std::string::_Tidy_deallocate(v578);
        std::string::_Tidy_deallocate(&v580);
        std::string::_Tidy_deallocate(v641);
      }
      goto LABEL_311;
  }
  if ( *(_BYTE *)v2 != 6 )
  {
    if ( *(_BYTE *)v2 != 7 )
      goto LABEL_316;
    v6 = std::operator+<char>(v578, v667, "LinkRemovedTimeout");
    if ( v667 != (char **)v6 )
    {
      std::string::_Tidy_deallocate(v667);
      *(_OWORD *)v667 = *(_OWORD *)v6;
      v668 = *(__m128i *)(v6 + 16);
      *(_QWORD *)(v6 + 16) = 0;
      *(_QWORD *)(v6 + 24) = 15;
      *(_BYTE *)v6 = 0;
    }
    std::string::_Tidy_deallocate(v578);
    if ( !v5 )
    {
      v7 = *((_QWORD *)v2 + 1);
      *(_OWORD *)v663 = 0;
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
            v663[0] = v11;
            v663[1] = *(std::_Ref_count_base **)(v7 + 128);
            goto LABEL_18;
          }
        }
      }
      v11 = v663[0];
LABEL_18:
      if ( v11 )
      {
        v12 = *(_QWORD *)v11;
        v13 = *((_QWORD *)v2 + 1);
        *(_OWORD *)v669 = 0;
        v14 = *(_QWORD *)(v13 + 112);
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v669[0] = *(std::_Ref_count_base **)(v13 + 104);
        v669[1] = *(std::_Ref_count_base **)(v13 + 112);
        (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v12 + 16))(v11, v669);
      }
      if ( *((_BYTE *)this + 2688) )
      {
        LODWORD(v674) = 2;
        v675 = (void *)&Str1;
        v676 = 0;
        LOBYTE(v677) = 0;
        LOBYTE(v569) = 0;
        LODWORD(v584) = 2;
        v585 = "link removed due to timeout";
        v586 = 27;
        v587 = 0;
        LODWORD(Str) = 2;
        v590 = "smiles";
        v591 = 6;
        LOBYTE(v592) = 0;
        LODWORD(v669[0]) = 2;
        v669[1] = (std::_Ref_count_base *)"a link is removed after timeout";
        v670 = 31;
        v671 = 0;
        LODWORD(v664[0]) = 2;
        v664[1] = "LinkRemoveTimeout";
        v665 = 17;
        v666 = 0;
        LODWORD(v576) = 1460;
        v15 = "client";
        if ( *((_BYTE *)this + 1112) )
          v15 = "stack";
        LODWORD(v678[0]) = 2;
        v678[1] = (void *)v15;
        v679.m128i_i64[0] = strlen(v15);
        v679.m128i_i8[8] = 0;
        v4 = 63;
        LODWORD(v575) = *((unsigned __int16 *)v2 + 1);
        Microsoft::Basix::Instrumentation::MultiLinkError::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
          (_DWORD)this + 2816,
          (_DWORD)this + 2696,
          (unsigned int)&v575,
          (unsigned int)v678,
          (__int64)&v576,
          (__int64)v664,
          (__int64)v669,
          (__int64)&Str,
          (__int64)&v584,
          (__int64)&v569,
          (__int64)&v674);
      }
      if ( (v4 & 0x20) != 0 )
      {
        v4 &= ~0x20u;
        if ( v679.m128i_i8[8] )
          operator delete(v678[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 0x10) != 0 )
      {
        v4 &= ~0x10u;
        if ( v666 )
          operator delete(v664[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 8) != 0 )
      {
        v4 &= ~8u;
        if ( v671 )
          operator delete(v669[1], (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 4) != 0 )
      {
        v4 &= ~4u;
        if ( (_BYTE)v592 )
          operator delete(v590, (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        if ( v587 )
          operator delete(v585, (const struct std::nothrow_t *)v8);
      }
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        if ( (_BYTE)v677 )
          operator delete(v675, (const struct std::nothrow_t *)v8);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v663);
    }
    *(_OWORD *)v663 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
    if ( v663[0] && *((_BYTE *)v663[0] + 128) )
    {
      v572 = &v674;
      std::_Integral_to_string<char,unsigned int>(v579, *((unsigned int *)this + 373));
      v16 = std::string::string(v611, ":");
      v17 = std::string::string(v623, "\"");
      v18 = std::string::string(v629, "\"");
      v19 = std::operator+<char>(v628, v18, "NonIceDoR");
      LOBYTE(v20) = (_BYTE)v569;
      std::string::string(v605, v20, v19, v17);
      LOBYTE(v21) = (_BYTE)v569;
      std::string::string(v604, v21, v605, v16);
      LOBYTE(v22) = (_BYTE)v569;
      std::string::string(&v674, v22, v604, v579);
      v577 = (__int64)&v584;
      std::_Integral_to_string<char,unsigned int>(v603, *((unsigned int *)this + 372));
      v23 = std::string::string(v627, ":");
      v24 = std::string::string(v626, "\"");
      v25 = std::string::string(v625, "\"");
      v26 = std::operator+<char>(v624, v25, "IceDoR");
      LOBYTE(v27) = (_BYTE)v569;
      std::string::string(v602, v27, v26, v24);
      LOBYTE(v28) = (_BYTE)v569;
      std::string::string(v601, v28, v602, v23);
      LOBYTE(v29) = (_BYTE)v569;
      std::string::string(&v584, v29, v601, v603);
      p_Str = (__int64)&Str;
      std::_Integral_to_string<char,unsigned int>(v600, *((unsigned int *)this + 553));
      v30 = std::string::string(v622, ":");
      v31 = std::string::string(v646, "\"");
      v32 = std::string::string(v645, "\"");
      v33 = std::operator+<char>(v644, v32, "CurrentActiveNumLinks");
      LOBYTE(v34) = (_BYTE)v569;
      std::string::string(v599, v34, v33, v31);
      LOBYTE(v35) = (_BYTE)v569;
      std::string::string(v598, v35, v599, v30);
      LOBYTE(v36) = (_BYTE)v569;
      std::string::string(&Str, v36, v598, v600);
      v575 = v678;
      v37 = std::string::string(v643, "\"");
      v38 = v672;
      if ( v673 > 0xF )
        v38 = (_QWORD *)v672[0];
      v39 = std::string::string(v642, "\"");
      v40 = std::string::string(v648, ":");
      v41 = std::string::string(v656, "\"");
      v42 = std::string::string(v657, "\"");
      v43 = std::operator+<char>(v658, v42, "RemovedLinkType");
      LOBYTE(v44) = (_BYTE)v569;
      std::string::string(v597, v44, v43, v41);
      LOBYTE(v45) = (_BYTE)v569;
      std::string::string(v596, v45, v597, v40);
      LOBYTE(v46) = (_BYTE)v569;
      std::string::string(v595, v46, v596, v39);
      v47 = std::operator+<char>(v660, v595, v38);
      LOBYTE(v48) = (_BYTE)v569;
      std::string::string(v678, v48, v47, v37);
      v576 = v664;
      std::_Integral_to_string<char,int>(v594, *((unsigned __int16 *)v571 + 1));
      v49 = std::string::string(v661, ":");
      v50 = std::string::string(v659, "\"");
      v51 = std::string::string(v607, "\"");
      v52 = std::operator+<char>(v608, v51, "RemovedLinkId");
      LOBYTE(v53) = (_BYTE)v569;
      std::string::string(v593, v53, v52, v50);
      LOBYTE(v54) = (_BYTE)v569;
      std::string::string(v620, v54, v593, v49);
      LOBYTE(v55) = (_BYTE)v569;
      std::string::string(v664, v55, v620, v594);
      v574 = (__int64 *)std::string::string(v609, "\"");
      v56 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v610, v662, 0, 6);
      v57 = v56;
      if ( v56[3] > 0xFu )
        v57 = (_QWORD *)*v56;
      v58 = std::string::string(v588, "\"");
      v59 = std::string::string(v615, ":");
      v60 = std::string::string(v616, "\"");
      v61 = std::string::string(v613, "\"");
      v62 = std::operator+<char>(v614, v61, "Direction");
      LOBYTE(v63) = (_BYTE)v569;
      std::string::string(v619, v63, v62, v60);
      LOBYTE(v64) = (_BYTE)v569;
      std::string::string(v618, v64, v619, v59);
      LOBYTE(v65) = (_BYTE)v569;
      std::string::string(v621, v65, v618, v58);
      v66 = std::operator+<char>(v578, v621, v57);
      LOBYTE(v67) = (_BYTE)v569;
      std::string::string(v669, v67, v66, v574);
      v68 = (char *)v667;
      if ( v668.m128i_i64[1] > 0xFuLL )
        v68 = v667[0];
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
        (int)v663,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "LinkRemove",
        v68,
        (__int64)v669,
        (__int64)v664,
        (__int64)v678,
        (__int64)&Str,
        (__int64)&v584,
        (__int64)&v674);
      std::string::_Tidy_deallocate(v578);
      std::string::_Tidy_deallocate(v621);
      std::string::_Tidy_deallocate(v618);
      std::string::_Tidy_deallocate(v619);
      std::string::_Tidy_deallocate(v614);
      std::string::_Tidy_deallocate(v613);
      std::string::_Tidy_deallocate(v616);
      std::string::_Tidy_deallocate(v615);
      std::string::_Tidy_deallocate(v588);
      std::string::_Tidy_deallocate(v610);
      std::string::_Tidy_deallocate(v609);
      std::string::_Tidy_deallocate(v620);
      std::string::_Tidy_deallocate(v593);
      std::string::_Tidy_deallocate(v608);
      std::string::_Tidy_deallocate(v607);
      std::string::_Tidy_deallocate(v659);
      std::string::_Tidy_deallocate(v661);
      std::string::_Tidy_deallocate(v594);
      std::string::_Tidy_deallocate(v660);
      std::string::_Tidy_deallocate(v595);
      std::string::_Tidy_deallocate(v596);
      std::string::_Tidy_deallocate(v597);
      std::string::_Tidy_deallocate(v658);
      std::string::_Tidy_deallocate(v657);
      std::string::_Tidy_deallocate(v656);
      std::string::_Tidy_deallocate(v648);
      std::string::_Tidy_deallocate(v642);
      std::string::_Tidy_deallocate(v643);
      std::string::_Tidy_deallocate(v598);
      std::string::_Tidy_deallocate(v599);
      std::string::_Tidy_deallocate(v644);
      std::string::_Tidy_deallocate(v645);
      std::string::_Tidy_deallocate(v646);
      std::string::_Tidy_deallocate(v622);
      std::string::_Tidy_deallocate(v600);
      std::string::_Tidy_deallocate(v601);
      std::string::_Tidy_deallocate(v602);
      std::string::_Tidy_deallocate(v624);
      std::string::_Tidy_deallocate(v625);
      std::string::_Tidy_deallocate(v626);
      std::string::_Tidy_deallocate(v627);
      std::string::_Tidy_deallocate(v603);
      std::string::_Tidy_deallocate(v604);
      std::string::_Tidy_deallocate(v605);
      std::string::_Tidy_deallocate(v628);
      std::string::_Tidy_deallocate(v629);
      std::string::_Tidy_deallocate(v623);
      std::string::_Tidy_deallocate(v611);
      std::string::_Tidy_deallocate(v579);
      v2 = v571;
      v5 = v570;
    }
    v69 = (volatile signed __int32 *)v663[1];
    if ( v663[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
        if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
      }
    }
    *(_OWORD *)v663 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
    if ( v663[0] && *((_BYTE *)v663[0] + 128) )
    {
      LODWORD(v575) = *((_DWORD *)this + 373);
      LODWORD(v576) = *((_DWORD *)this + 372);
      LODWORD(v571) = *((_DWORD *)this + 553);
      v70 = v672;
      if ( v673 > 0xF )
        v70 = (__int64 *)v672[0];
      v574 = v70;
      LOWORD(v569) = *((_WORD *)v2 + 1);
      v71 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v611, v662, 0, 6);
      v74 = (__int64)v71;
      if ( (unsigned __int64)v71[3] > 0xF )
        v74 = *v71;
      v75 = v667;
      if ( v668.m128i_i64[1] > 0xFuLL )
        LODWORD(v75) = v667[0];
      std::string::string(
        v579,
        "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d",
        v72,
        v73,
        (_DWORD)v562,
        v563,
        (_DWORD)v564,
        v565,
        v566);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int>(
        (unsigned int)v663,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v579,
        (_DWORD)v75,
        v74,
        (char)v569,
        (__int64)v574,
        (char)v571,
        (char)v576,
        (char)v575);
      std::string::_Tidy_deallocate(v579);
      std::string::_Tidy_deallocate(v611);
    }
    v76 = (volatile signed __int32 *)v663[1];
    goto LABEL_312;
  }
  v77 = std::operator+<char>(v611, v667, "LinkRemovedDueToError");
  if ( v667 != (char **)v77 )
  {
    std::string::_Tidy_deallocate(v667);
    *(_OWORD *)v667 = *(_OWORD *)v77;
    v668 = *(__m128i *)(v77 + 16);
    *(_QWORD *)(v77 + 16) = 0;
    *(_QWORD *)(v77 + 24) = 15;
    *(_BYTE *)v77 = 0;
  }
  std::string::_Tidy_deallocate(v611);
  *(_OWORD *)v678 = 0;
  v679 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v678[0]) = 0;
  v78 = *((_QWORD *)v2 + 1);
  if ( v78 )
  {
    v79 = *(_QWORD *)(v78 + 104);
    if ( v79 )
    {
      v80 = *(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)(v79 + 40) + 8LL);
      std::string::string(v579, "Microsoft::Basix::Dct.LastException");
      v80(v79 + 40, &v674, v579);
      std::string::_Tidy_deallocate(v579);
      v81 = v674;
      if ( (_BYTE)v674 )
      {
        *(_OWORD *)v663 = 0;
        *(_OWORD *)v664 = 0;
        __ExceptionPtrCreate(v664);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
          v677,
          v663,
          v664);
        __ExceptionPtrDestroy(v664);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                v663,
                                v82) )
        {
          Description = Microsoft::Basix::Exception::CreateDescription(v611, v663);
          std::string::operator=(v678, Description);
          std::string::_Tidy_deallocate(v611);
        }
        __ExceptionPtrDestroy(v663);
        v81 = v674;
      }
      if ( v81 )
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v675);
    }
  }
  if ( !v5 )
  {
    v84 = *((_QWORD *)v2 + 1);
    *(_OWORD *)v663 = 0;
    v85 = *(_QWORD *)(v84 + 128);
    if ( v85 )
    {
      v86 = *(_DWORD *)(v85 + 8);
      while ( v86 )
      {
        v87 = v86;
        v86 = _InterlockedCompareExchange((volatile signed __int32 *)(v85 + 8), v86 + 1, v86);
        if ( v87 == v86 )
        {
          v88 = *(std::_Ref_count_base **)(v84 + 120);
          v663[0] = v88;
          v89 = *(std::_Ref_count_base **)(v84 + 128);
          v663[1] = v89;
          goto LABEL_85;
        }
      }
    }
    v88 = v663[0];
    v89 = v663[1];
LABEL_85:
    if ( v88 )
    {
      v90 = *(_QWORD *)v88;
      v91 = *((_QWORD *)v2 + 1);
      *(_OWORD *)v669 = 0;
      v92 = *(_QWORD *)(v91 + 112);
      if ( v92 )
        _InterlockedIncrement((volatile signed __int32 *)(v92 + 8));
      v669[0] = *(std::_Ref_count_base **)(v91 + 104);
      v669[1] = *(std::_Ref_count_base **)(v91 + 112);
      (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v90 + 16))(v88, v669);
    }
    if ( v89 )
      std::_Ref_count_base::_Decref(v89);
  }
  *(_OWORD *)v663 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v663);
  if ( v663[0] && *((_BYTE *)v663[0] + 128) )
  {
    v572 = v579;
    v93 = std::string::string(v617, "\"");
    v94 = v678;
    if ( v679.m128i_i64[1] > 0xFuLL )
      v94 = (void **)v678[0];
    v95 = std::string::string(v630, "\"");
    v96 = std::string::string(v631, ":");
    v97 = std::string::string(v632, "\"");
    v98 = std::string::string(v633, "\"");
    v99 = std::operator+<char>(v634, v98, "error");
    LOBYTE(v100) = (_BYTE)v569;
    std::string::string(v588, v100, v99, v97);
    LOBYTE(v101) = (_BYTE)v569;
    std::string::string(v610, v101, v588, v96);
    LOBYTE(v102) = (_BYTE)v569;
    std::string::string(v609, v102, v610, v95);
    v103 = std::operator+<char>(v635, v609, v94);
    LOBYTE(v104) = (_BYTE)v569;
    std::string::string(v579, v104, v103, v93);
    v577 = (__int64)v605;
    std::_Integral_to_string<char,unsigned int>(v608, *((unsigned int *)this + 373));
    v105 = std::string::string(v636, ":");
    v106 = std::string::string(v637, "\"");
    v107 = std::string::string(v638, "\"");
    v108 = std::operator+<char>(v639, v107, "NonIceDoR");
    LOBYTE(v109) = (_BYTE)v569;
    std::string::string(v607, v109, v108, v106);
    LOBYTE(v110) = (_BYTE)v569;
    std::string::string(v669, v110, v607, v105);
    LOBYTE(v111) = (_BYTE)v569;
    std::string::string(v605, v111, v669, v608);
    p_Str = (__int64)v604;
    std::_Integral_to_string<char,unsigned int>(v664, *((unsigned int *)this + 372));
    v112 = std::string::string(v640, ":");
    v113 = std::string::string(v615, "\"");
    v114 = std::string::string(v616, "\"");
    v115 = std::operator+<char>(v613, v114, "IceDoR");
    LOBYTE(v116) = (_BYTE)v569;
    std::string::string(&Str, v116, v115, v113);
    LOBYTE(v117) = (_BYTE)v569;
    std::string::string(&v584, v117, &Str, v112);
    LOBYTE(v118) = (_BYTE)v569;
    std::string::string(v604, v118, &v584, v664);
    v575 = v603;
    std::_Integral_to_string<char,unsigned int>(&v674, *((unsigned int *)this + 553));
    v119 = std::string::string(v614, ":");
    v120 = std::string::string(v578, "\"");
    v121 = std::string::string(v659, "\"");
    v122 = std::operator+<char>(v661, v121, "CurrentActiveNumLinks");
    LOBYTE(v123) = (_BYTE)v569;
    std::string::string(v621, v123, v122, v120);
    LOBYTE(v124) = (_BYTE)v569;
    std::string::string(v618, v124, v621, v119);
    LOBYTE(v125) = (_BYTE)v569;
    std::string::string(v603, v125, v618, &v674);
    v576 = v602;
    v126 = std::string::string(v660, "\"");
    v127 = v672;
    if ( v673 > 0xF )
      v127 = (_QWORD *)v672[0];
    v128 = std::string::string(v658, "\"");
    v129 = std::string::string(v657, ":");
    v130 = std::string::string(v656, "\"");
    v131 = std::string::string(v648, "\"");
    v132 = std::operator+<char>(v642, v131, "RemovedLinkType");
    LOBYTE(v133) = (_BYTE)v569;
    std::string::string(v619, v133, v132, v130);
    LOBYTE(v134) = (_BYTE)v569;
    std::string::string(v620, v134, v619, v129);
    LOBYTE(v135) = (_BYTE)v569;
    std::string::string(v593, v135, v620, v128);
    v136 = std::operator+<char>(v643, v593, v127);
    LOBYTE(v137) = (_BYTE)v569;
    std::string::string(v602, v137, v136, v126);
    v569 = v601;
    std::_Integral_to_string<char,int>(v594, *((unsigned __int16 *)v571 + 1));
    v138 = std::string::string(v644, ":");
    v139 = std::string::string(v645, "\"");
    v140 = std::string::string(v646, "\"");
    v141 = std::operator+<char>(v622, v140, "RemovedLinkId");
    LOBYTE(v142) = (unsigned __int8)v601;
    std::string::string(v595, v142, v141, v139);
    LOBYTE(v143) = (unsigned __int8)v601;
    std::string::string(v596, v143, v595, v138);
    LOBYTE(v144) = (unsigned __int8)v601;
    std::string::string(v601, v144, v596, v594);
    v574 = (__int64 *)std::string::string(v624, "\"");
    v145 = (_QWORD *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v625, v662, 0, 6);
    v146 = v145;
    if ( v145[3] > 0xFu )
      v146 = (_QWORD *)*v145;
    v147 = std::string::string(v626, "\"");
    v148 = std::string::string(v627, ":");
    v149 = std::string::string(v628, "\"");
    v150 = std::string::string(v629, "\"");
    v151 = std::operator+<char>(v623, v150, "Direction");
    LOBYTE(v152) = (_BYTE)v569;
    std::string::string(v597, v152, v151, v149);
    LOBYTE(v153) = (_BYTE)v569;
    std::string::string(v598, v153, v597, v148);
    LOBYTE(v154) = (_BYTE)v569;
    std::string::string(v599, v154, v598, v147);
    v155 = std::operator+<char>(v611, v599, v146);
    LOBYTE(v156) = (_BYTE)v569;
    std::string::string(v600, v156, v155, v574);
    v157 = (char *)v667;
    if ( v668.m128i_i64[1] > 0xFuLL )
      v157 = v667[0];
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
      (int)v663,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Smiles",
      "LinkRemove",
      v157,
      (__int64)v600,
      (__int64)v601,
      (__int64)v602,
      (__int64)v603,
      (__int64)v604,
      (__int64)v605,
      (__int64)v579);
    std::string::_Tidy_deallocate(v611);
    std::string::_Tidy_deallocate(v599);
    std::string::_Tidy_deallocate(v598);
    std::string::_Tidy_deallocate(v597);
    std::string::_Tidy_deallocate(v623);
    std::string::_Tidy_deallocate(v629);
    std::string::_Tidy_deallocate(v628);
    std::string::_Tidy_deallocate(v627);
    std::string::_Tidy_deallocate(v626);
    std::string::_Tidy_deallocate(v625);
    std::string::_Tidy_deallocate(v624);
    std::string::_Tidy_deallocate(v596);
    std::string::_Tidy_deallocate(v595);
    std::string::_Tidy_deallocate(v622);
    std::string::_Tidy_deallocate(v646);
    std::string::_Tidy_deallocate(v645);
    std::string::_Tidy_deallocate(v644);
    std::string::_Tidy_deallocate(v594);
    std::string::_Tidy_deallocate(v643);
    std::string::_Tidy_deallocate(v593);
    std::string::_Tidy_deallocate(v620);
    std::string::_Tidy_deallocate(v619);
    std::string::_Tidy_deallocate(v642);
    std::string::_Tidy_deallocate(v648);
    std::string::_Tidy_deallocate(v656);
    std::string::_Tidy_deallocate(v657);
    std::string::_Tidy_deallocate(v658);
    std::string::_Tidy_deallocate(v660);
    std::string::_Tidy_deallocate(v618);
    std::string::_Tidy_deallocate(v621);
    std::string::_Tidy_deallocate(v661);
    std::string::_Tidy_deallocate(v659);
    std::string::_Tidy_deallocate(v578);
    std::string::_Tidy_deallocate(v614);
    std::string::_Tidy_deallocate(&v674);
    std::string::_Tidy_deallocate(&v584);
    std::string::_Tidy_deallocate(&Str);
    std::string::_Tidy_deallocate(v613);
    std::string::_Tidy_deallocate(v616);
    std::string::_Tidy_deallocate(v615);
    std::string::_Tidy_deallocate(v640);
    std::string::_Tidy_deallocate(v664);
    std::string::_Tidy_deallocate(v669);
    std::string::_Tidy_deallocate(v607);
    std::string::_Tidy_deallocate(v639);
    std::string::_Tidy_deallocate(v638);
    std::string::_Tidy_deallocate(v637);
    std::string::_Tidy_deallocate(v636);
    std::string::_Tidy_deallocate(v608);
    std::string::_Tidy_deallocate(v635);
    std::string::_Tidy_deallocate(v609);
    std::string::_Tidy_deallocate(v610);
    std::string::_Tidy_deallocate(v588);
    std::string::_Tidy_deallocate(v634);
    std::string::_Tidy_deallocate(v633);
    std::string::_Tidy_deallocate(v632);
    std::string::_Tidy_deallocate(v631);
    std::string::_Tidy_deallocate(v630);
    std::string::_Tidy_deallocate(v617);
    v2 = v571;
    v5 = v570;
  }
  v158 = (volatile signed __int32 *)v663[1];
  if ( v663[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v158)(v158);
      if ( _InterlockedExchangeAdd(v158 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v158 + 8LL))(v158);
    }
  }
  *(_OWORD *)v663 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v663);
  if ( v663[0] && *((_BYTE *)v663[0] + 128) )
  {
    v159 = v678;
    if ( v679.m128i_i64[1] > 0xFuLL )
      v159 = (void **)v678[0];
    v574 = (__int64 *)v159;
    LODWORD(v571) = *((_DWORD *)this + 373);
    LODWORD(v575) = *((_DWORD *)this + 372);
    LODWORD(v576) = *((_DWORD *)this + 553);
    v160 = v672;
    if ( v673 > 0xF )
      v160 = (_QWORD *)v672[0];
    v577 = (__int64)v160;
    LOWORD(v569) = *((_WORD *)v2 + 1);
    v161 = (__int64 *)Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v617, v662, 0, 6);
    v164 = (__int64)v161;
    if ( (unsigned __int64)v161[3] > 0xF )
      v164 = *v161;
    v165 = v667;
    if ( v668.m128i_i64[1] > 0xFuLL )
      LODWORD(v165) = v667[0];
    std::string::string(
      v588,
      "Checkpoint.SMILES.%s(%s):Id=%d, type=%s, activeLinks=%d, iceDoR=%d, nonIceDoR=%d, error=%s",
      v162,
      v163,
      (_DWORD)v562,
      v563,
      (_DWORD)v564,
      v565,
      v566,
      v567);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *,unsigned short,char const *,unsigned int,unsigned int,unsigned int,char const *>(
      (unsigned int)v663,
      (unsigned int)"BASIX_DCT",
      (unsigned int)v588,
      (_DWORD)v165,
      v164,
      (char)v569,
      v577,
      (char)v576,
      (char)v575,
      (char)v571,
      (__int64)v574);
    std::string::_Tidy_deallocate(v588);
    std::string::_Tidy_deallocate(v617);
  }
  v166 = (volatile signed __int32 *)v663[1];
  if ( v663[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v663[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v166)(v166);
      if ( _InterlockedExchangeAdd(v166 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v166 + 8LL))(v166);
    }
  }
  std::string::_Tidy_deallocate(v678);
LABEL_316:
  if ( !v662[0] && !v5 )
  {
    v669[1] = 0;
    v669[0] = 0;
    v550 = (std::_Ref_count_base *)operator new(0x20u);
    v663[0] = v550;
    if ( v550 )
      v551 = (std::_Ref_count_base *)__0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v550);
    else
      v551 = 0;
    v669[1] = v551;
    v580 = 0;
    v581 = 0;
    std::string::_Construct<1,char const *>(&v580, "reason", 6);
    v582 = 46;
    v552 = &v580;
    if ( *((_QWORD *)&v581 + 1) > 0xFu )
      v552 = (__int128 *)v580;
    v583 = v552;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
      v669,
      &v580,
      &v680);
    std::string::_Tidy_deallocate(&v580);
    memset(v682, 0, 0xF8u);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v682,
      1);
    LOBYTE(v553) = 1;
    Microsoft::Basix::Containers::AnyPTreeToJson(v669, &v682[2], v553);
    if ( *((_BYTE *)this + 2368) )
    {
      std::stringbuf::str(&v682[3], &Str);
      v555 = v4 | 0x240;
      v556 = &Str;
      if ( v592 > 0xF )
        v556 = Str;
      LODWORD(v584) = 2;
      v585 = v556;
      v586 = strlen((const char *)v556);
      v587 = 0;
      v4 = v555 | 0x80;
      LODWORD(p_Str) = v4;
      LODWORD(v571) = -1;
      v557 = (Microsoft::Basix::Dct::LinkDataV3 *)*((_QWORD *)v2 + 1);
      if ( v557 )
      {
        AveDelayOut = (int)Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(v557);
        v559 = *((_QWORD *)v2 + 1);
      }
      else
      {
        AveDelayOut = 0;
        v559 = 0;
      }
      LODWORD(v575) = AveDelayOut;
      v560 = v667;
      if ( v668.m128i_i64[1] > 0xFuLL )
        v560 = (char **)v667[0];
      LODWORD(v674) = 2;
      v675 = v560;
      v676 = strlen((const char *)v560);
      LOBYTE(v677) = 0;
      LOWORD(v4) = v4 | 0x100;
      if ( v559 )
        v561 = *(_DWORD *)(v559 + 260);
      else
        v561 = 0;
      LODWORD(v576) = v561;
      LODWORD(v569) = *((unsigned __int16 *)v2 + 1);
      Microsoft::Basix::Instrumentation::MultiLinkActivity::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)this + 2496,
        (_DWORD)this + 2376,
        (unsigned int)&v569,
        (unsigned int)&v576,
        (__int64)&v674,
        (__int64)&v575,
        (__int64)&v571,
        (__int64)this + 2212,
        (__int64)&v584);
    }
    if ( (v4 & 0x100) != 0 && (_BYTE)v677 )
      operator delete(v675, v554);
    if ( (v4 & 0x80u) != 0 )
    {
      LOBYTE(v4) = v4 & 0x7F;
      if ( v587 )
        operator delete(v585, v554);
    }
    if ( (v4 & 0x40) != 0 )
      std::string::_Tidy_deallocate(&Str);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v682[19]);
    v682[19] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v682[19]);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v669);
  }
  std::string::_Tidy_deallocate(v672);
  std::string::_Tidy_deallocate(v667);
  std::string::_Tidy_deallocate(&v680);
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
