# CScriptRuntime::Run(VAR *)

- ea: `0x180023440`
- end: `0x180029008`
- name: `?Run@CScriptRuntime@@QEAAJPEAVVAR@@@Z`
- size: `23496`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `2`
- callee_count: `92`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009e28`
- `0x1800642e8`

## callees

- `0x180002a64`
- `0x180002af0`
- `0x180003728`
- `0x1800037fc`
- `0x1800049d0`
- `0x180004d40`
- `0x180004f04`
- `0x180005070`
- `0x180005364`
- `0x180005400`
- `0x180005660`
- `0x180005bac`
- `0x180005ce8`
- `0x180006418`
- `0x1800065fc`
- `0x180006b60`
- `0x1800070c4`
- `0x1800076e0`
- `0x180007700`
- `0x180007e9c`
- `0x18000826c`
- `0x180008330`
- `0x180008794`
- `0x180008e88`
- `0x18000aa10`
- `0x18000b0e0`
- `0x18000bc50`
- `0x18000cb30`
- `0x18000d190`
- `0x18000da30`
- `0x18000eea4`
- `0x18000f108`
- `0x180011bc4`
- `0x1800132f8`
- `0x1800153d4`
- `0x180015660`
- `0x180015c38`
- `0x180016d48`
- `0x18001b4f4`
- `0x180023440`
- `0x18002fc08`
- `0x1800336c0`
- `0x180033c70`
- `0x18003477c`
- `0x180034980`
- `0x180039f20`
- `0x18003b0b0`
- `0x18003b0d0`
- `0x18003b2f0`
- `0x18003bad4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002815e`
- `OLEAUT32!__imp_VariantInit` at `0x18002815e`
- `OLEAUT32!__imp_VariantClear` at `0x180027354`
- `OLEAUT32!__imp_VariantClear` at `0x1800278dc`
- `OLEAUT32!__imp_VariantClear` at `0x180028120`
- `OLEAUT32!__imp_VariantClear` at `0x18002819b`
- `OLEAUT32!__imp_VariantClear` at `0x180028a0c`
- `OLEAUT32!__imp_VariantClear` at `0x180027354`
- `OLEAUT32!__imp_VariantClear` at `0x1800278dc`
- `OLEAUT32!__imp_VariantClear` at `0x180028120`
- `OLEAUT32!__imp_VariantClear` at `0x18002819b`
- `OLEAUT32!__imp_VariantClear` at `0x180028a0c`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800278ae`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002804d`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002813d`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800278ae`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002804d`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002813d`

## pseudocode

```c
__int64 __fastcall CScriptRuntime::Run(CScriptRuntime *this, struct VAR *a2)
{
  __int64 v3; // r13
  __int64 v4; // r14
  struct ExecBody *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int8 *v8; // rax
  int v9; // ecx
  unsigned __int8 *v10; // r9
  int v11; // ecx
  GcContext *v12; // rcx
  double *v13; // rdi
  __int16 v14; // ax
  int v15; // edx
  int Value; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  const unsigned __int16 *v19; // rsi
  VAR **v20; // rcx
  __int128 *v21; // rax
  __int64 v22; // rcx
  VAR *v23; // rax
  const unsigned __int16 *v24; // rdi
  struct VAR *v25; // rbx
  struct SYM *v26; // rax
  int VarVal; // eax
  const unsigned __int16 *v28; // r9
  struct VAR *v29; // r8
  int v30; // edx
  int v31; // eax
  __int64 v32; // rdx
  int v33; // ebx
  __int64 v34; // r8
  struct VAR *v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v39; // rdx
  __int64 v40; // r11
  VAR *v41; // rcx
  VARIANTARG *v42; // r8
  unsigned int v43; // r9d
  __int64 v44; // rdx
  struct VAR *v45; // rcx
  struct VAR *v46; // rcx
  double *v47; // rcx
  double v48; // xmm1_8
  VAR *v49; // rcx
  __int64 v50; // rax
  __int128 v51; // xmm0
  __int64 v52; // xmm1_8
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rax
  LONG v57; // ebx
  __int16 *v58; // r9
  VAR *v59; // rdx
  double *v60; // rbx
  struct VAR *v61; // rax
  struct VAR *v62; // rax
  __int64 v63; // rcx
  __int16 v64; // ax
  struct VAR *v65; // rdx
  const unsigned __int16 *v66; // rdx
  __int64 v67; // rsi
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  __int64 v71; // rax
  __int64 v72; // rsi
  __int64 v73; // rax
  VAR *v74; // rdx
  __int64 v75; // rdi
  __int64 v76; // rbx
  struct VAR *v77; // rax
  struct VAR *v78; // rax
  const unsigned __int16 *v79; // r12
  __int64 v80; // rsi
  __int64 v81; // rdx
  __int64 v82; // rax
  struct IDispatch **v83; // rbx
  VAR *v84; // rax
  struct SYM *v85; // rax
  int DispatchDispID; // eax
  __int64 v87; // rbx
  int v88; // eax
  struct VAR *v89; // r8
  VAR *v90; // r10
  __int64 v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rcx
  unsigned int v95; // edx
  int v96; // eax
  bool v97; // bl
  unsigned int *v98; // rcx
  unsigned int *v99; // rcx
  __int64 v100; // rdx
  __int64 v101; // rax
  GcAlloc *v102; // rax
  struct VAR *v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rcx
  LONG v106; // edx
  __int64 v107; // rcx
  int v108; // eax
  unsigned int v109; // edx
  __int64 v110; // rcx
  __int128 *v111; // rax
  __int128 v112; // xmm0
  __int64 v113; // xmm1_8
  __int64 v114; // rax
  const unsigned __int16 *v115; // rbx
  struct VAR *v116; // rax
  int v117; // edx
  struct IDispatch *v118; // rdx
  __int64 v119; // rax
  int v120; // eax
  __int64 v121; // rax
  double *v122; // rbx
  int v123; // ecx
  unsigned int *v124; // rax
  __int64 v125; // rdx
  __int64 v126; // rdx
  unsigned int v127; // ebx
  GcAlloc *GcAlloc; // rax
  _WORD *v129; // rax
  __int64 v130; // rdx
  int v131; // ecx
  int v132; // ebx
  _WORD *v133; // rcx
  const unsigned __int16 *v134; // rax
  struct VAR *v135; // rbx
  struct VAR *v136; // rdi
  struct SYM *v137; // rax
  int v138; // r8d
  int v139; // r9d
  _WORD *v140; // rcx
  NameTbl *v141; // rdi
  struct VAR *v142; // rbx
  struct SYM *v143; // rax
  bool v144; // zf
  __int64 v145; // rax
  VAR *v146; // rbx
  GcContext **v147; // rax
  VAR *v148; // rax
  VAR *v149; // r8
  int v150; // edx
  int v151; // edx
  int v152; // edx
  int v153; // edx
  __int64 v154; // rcx
  __int64 v155; // rax
  __int64 v156; // rax
  const unsigned __int16 *v157; // rbx
  __int64 v158; // rax
  int v159; // eax
  _WORD *v160; // rcx
  struct VAR *v161; // rbx
  struct SYM *v162; // rax
  int v163; // r8d
  __int64 v164; // r9
  int v165; // eax
  int v166; // r10d
  __int64 v167; // rcx
  __int16 v168; // ax
  int v169; // edx
  __int64 v170; // r8
  int v171; // r9d
  struct VAR *v172; // rdx
  int v173; // ecx
  __int64 v174; // rax
  struct VAR *v175; // rdx
  int v176; // ecx
  __int64 v177; // rax
  struct VAR *v178; // rdx
  int v179; // ecx
  __int64 v180; // rax
  __int64 v181; // rdi
  __int64 (__fastcall *v182)(__int64, struct SYM *, _QWORD, __int64, _QWORD); // rbx
  struct SYM *v183; // rax
  __int64 v184; // rdx
  __int64 v185; // rcx
  int v186; // eax
  double *v187; // rbx
  int IsAStringObj; // eax
  VAR *v189; // rcx
  struct VAR *v190; // rax
  struct VAR *v191; // rax
  int v192; // ebx
  __int64 v193; // rcx
  VAR *v194; // rax
  char *v195; // rax
  int v196; // ecx
  char *v197; // rax
  _WORD *v198; // rax
  __int64 v199; // r8
  VAR *v200; // rcx
  int v201; // eax
  __int64 v202; // rcx
  __int64 v203; // r8
  VAR *v204; // rcx
  unsigned int v205; // r14d
  __int64 v206; // rsi
  __int64 (__fastcall *v207)(__int64, struct SYM *, _QWORD, __int64, _QWORD); // rdi
  __int64 v208; // rbx
  struct SYM *v209; // rax
  __int64 v210; // rsi
  _WORD *v211; // rcx
  const unsigned __int16 *LocalName; // rax
  struct VAR *v213; // rbx
  struct VAR *v214; // rdi
  struct SYM *v215; // rax
  bool v216; // sf
  const unsigned __int16 *v217; // rsi
  VAR *v218; // rax
  __int64 (__fastcall *v219)(struct NameTbl *, struct SYM *, __int64); // rdi
  __int64 v220; // rbx
  struct SYM *v221; // rax
  _WORD *v222; // rcx
  struct VAR *v223; // rbx
  struct SYM *v224; // rax
  VARIANTARG *v225; // rax
  __int64 v226; // r8
  __int64 v227; // rdx
  __int64 v228; // r8
  VAR *v229; // rdx
  double *v230; // rcx
  int v231; // edx
  _WORD *v232; // rax
  _DWORD *v233; // rax
  __int64 v234; // rdx
  __int64 v235; // rcx
  __int64 v236; // rbx
  VARIANTARG *v237; // rdx
  __int64 v238; // rcx
  __int64 v239; // rdx
  char *v240; // rax
  _WORD *v241; // rax
  _WORD *v242; // rax
  __int64 v243; // r8
  __int64 v244; // rdx
  __int64 v245; // rbx
  GcAlloc *v246; // rax
  const unsigned __int16 *v247; // rax
  struct VAR *v248; // rbx
  struct VAR *v249; // rdi
  struct SYM *v250; // rax
  __int16 v251; // ax
  BOOL v252; // edx
  __int64 v253; // rcx
  __int64 v254; // rax
  _WORD *v255; // rcx
  const unsigned __int16 *v256; // rax
  struct VAR *v257; // rbx
  struct VAR *v258; // rdi
  struct SYM *v259; // rax
  int v260; // r8d
  double *v261; // rcx
  __int64 v262; // rax
  int v263; // edx
  int v264; // edx
  int v265; // edx
  __int64 v266; // rcx
  struct NameTbl *v267; // r9
  _WORD *v268; // rcx
  _WORD *v269; // rax
  __int64 *v270; // rax
  __int64 v271; // xmm0_8
  _WORD *v272; // rcx
  _WORD *v273; // rcx
  struct VAR *v274; // rbx
  struct SYM *v275; // rax
  double *v276; // rbx
  __int16 v277; // ax
  __int16 v278; // ax
  VARIANTARG *v279; // rbx
  GcContext **v280; // rax
  __int64 v281; // rax
  __int64 v282; // rax
  __int64 v283; // rax
  int v284; // r8d
  __int64 v285; // rdx
  int v286; // r9d
  struct VAR *v287; // rdx
  struct VAR *v288; // rdx
  double *v289; // rbx
  double v290; // xmm0_8
  struct VAR *v291; // rdx
  struct VAR *v292; // rdx
  double *v293; // rbx
  double v294; // xmm0_8
  struct SYM *v295; // rax
  __int64 v296; // rdi
  __int64 (__fastcall *v297)(__int64, struct SYM *, _QWORD, __int64, _QWORD); // rbx
  struct SYM *v298; // rax
  int v299; // eax
  struct VAR *v300; // rdx
  VAR *v301; // rbx
  int v302; // eax
  struct VAR *v303; // rdx
  __int64 v304; // rdx
  __int64 v305; // rax
  struct VAR *v306; // rcx
  __int64 v307; // rax
  __int64 v308; // rax
  __int64 v309; // rbx
  VAR *v310; // rcx
  __int64 v311; // rax
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rdx
  struct VAR *v315; // rcx
  __int64 v316; // rax
  __int64 v317; // rbx
  __int64 v318; // rbx
  __int64 v319; // rdx
  __int64 v320; // rdx
  VAR *v321; // rcx
  __int64 v322; // rax
  int v323; // edx
  int v324; // ebx
  __int16 *v325; // r9
  VAR *v326; // rdx
  int v327; // ebx
  __int16 *v328; // r9
  VAR *v329; // rdx
  int v330; // ebx
  __int16 *v331; // r9
  VAR *v332; // rdx
  int v333; // ebx
  __int16 *v334; // r9
  char v335; // bl
  VAR *v336; // rdx
  int v337; // ebx
  __int16 *v338; // r9
  char v339; // bl
  int *v340; // rdx
  enum tagBREAKREASON v341; // edx
  __int64 v342; // rax
  VAR *v343; // rcx
  __int64 v344; // rcx
  int v345; // edx
  __int64 v346; // rcx
  __int64 v347; // rax
  __int64 v348; // rcx
  _WORD *v349; // rax
  int *v350; // rax
  int v351; // ecx
  __int64 v352; // rcx
  __int64 v353; // rbx
  __int64 v354; // rdi
  GcAlloc *v355; // rax
  __int64 v356; // r8
  __int64 v357; // rdx
  __int64 v358; // rcx
  _WORD *v359; // rcx
  _WORD *v360; // rax
  _DWORD *v361; // rax
  struct VAR *v362; // rcx
  __int64 v363; // rax
  _WORD *v364; // rcx
  __int64 v365; // rcx
  __int64 v366; // r8
  VAR *v367; // rdx
  VAR *v368; // rcx
  int v369; // edx
  __int64 v370; // rdx
  __int64 v371; // rdi
  VAR *v372; // rcx
  __int64 v373; // rax
  __int64 v374; // rdx
  __int64 v375; // rcx
  __int64 v376; // rcx
  char *v377; // rdx
  size_t v378; // r8
  char *v379; // rcx
  __int64 v380; // rcx
  __int64 v381; // rdx
  _DWORD *v382; // rax
  __int64 v383; // rbx
  __int64 v384; // rdi
  GcAlloc *v385; // rax
  int v386; // ebx
  __int16 *v387; // r9
  VAR *v388; // rcx
  int v389; // edx
  int v390; // ebx
  __int16 *v391; // r9
  VAR *v392; // rcx
  int v393; // r8d
  int v394; // ebx
  __int16 *v395; // r9
  double *v396; // rdx
  double v397; // xmm0_8
  int v398; // ebx
  __int16 *v399; // r9
  double *v400; // rdx
  double v401; // xmm0_8
  int v402; // ebx
  __int16 *v403; // r9
  int v404; // ebx
  VAR *v405; // rdx
  int v406; // eax
  __int64 v407; // rcx
  __int64 v408; // rdx
  __int64 v409; // rdx
  VARIANTARG *v410; // rcx
  __int64 v411; // rcx
  __int64 *v412; // rax
  __int64 v413; // xmm0_8
  __int64 v414; // rcx
  __int64 v415; // rcx
  __int64 v416; // rcx
  __int64 v417; // rcx
  __int64 v418; // rdx
  char *v419; // rax
  __int64 v420; // rcx
  __int64 v421; // rdx
  _DWORD *v422; // rax
  __int64 v423; // rcx
  __int64 *v424; // rax
  __int64 v425; // xmm0_8
  int v426; // ecx
  int v427; // ecx
  int v428; // eax
  int v429; // eax
  __int64 v430; // rcx
  _WORD *v431; // rax
  _WORD *v432; // rcx
  VAR *v433; // rcx
  __int64 v434; // rcx
  __int64 v435; // rdx
  __int64 v436; // rax
  int pvarg; // [rsp+20h] [rbp-338h]
  VAR *v439; // [rsp+40h] [rbp-318h] BYREF
  struct NameTbl *v440; // [rsp+48h] [rbp-310h] BYREF
  VAR *v441; // [rsp+50h] [rbp-308h] BYREF
  VAR *v442; // [rsp+58h] [rbp-300h] BYREF
  VAR *v443; // [rsp+60h] [rbp-2F8h] BYREF
  VAR *v444; // [rsp+68h] [rbp-2F0h] BYREF
  VAR *v445; // [rsp+70h] [rbp-2E8h] BYREF
  VAR *v446; // [rsp+78h] [rbp-2E0h] BYREF
  __int128 v447; // [rsp+80h] [rbp-2D8h] BYREF
  __int64 v448; // [rsp+90h] [rbp-2C8h]
  VARIANTARG v449; // [rsp+98h] [rbp-2C0h] BYREF
  tagBREAKREASON v450; // [rsp+B0h] [rbp-2A8h] BYREF
  int v451; // [rsp+B4h] [rbp-2A4h] BYREF
  VAR *v452; // [rsp+B8h] [rbp-2A0h] BYREF
  VAR *v453; // [rsp+C0h] [rbp-298h] BYREF
  VAR *v454; // [rsp+C8h] [rbp-290h] BYREF
  VAR *v455; // [rsp+D0h] [rbp-288h] BYREF
  VAR *v456; // [rsp+D8h] [rbp-280h] BYREF
  VAR *v457; // [rsp+E0h] [rbp-278h] BYREF
  VAR *v458; // [rsp+E8h] [rbp-270h] BYREF
  VAR *v459; // [rsp+F0h] [rbp-268h] BYREF
  VAR *v460; // [rsp+F8h] [rbp-260h] BYREF
  VAR *v461; // [rsp+100h] [rbp-258h] BYREF
  VAR *v462; // [rsp+108h] [rbp-250h] BYREF
  VAR *v463; // [rsp+110h] [rbp-248h] BYREF
  VARIANTARG v464; // [rsp+118h] [rbp-240h] BYREF
  VARIANTARG v465; // [rsp+130h] [rbp-228h] BYREF
  VARIANTARG v466; // [rsp+148h] [rbp-210h] BYREF
  VARIANTARG v467; // [rsp+160h] [rbp-1F8h] BYREF
  VARIANTARG v468; // [rsp+178h] [rbp-1E0h] BYREF
  VARIANTARG v469; // [rsp+190h] [rbp-1C8h] BYREF
  __int64 v470; // [rsp+1A8h] [rbp-1B0h]
  struct ExecBody *v471; // [rsp+1B0h] [rbp-1A8h]
  VARIANTARG v472; // [rsp+1B8h] [rbp-1A0h] BYREF
  VARIANTARG *v473; // [rsp+1D0h] [rbp-188h] BYREF
  unsigned int *v474; // [rsp+1D8h] [rbp-180h]
  __int64 v475; // [rsp+1E0h] [rbp-178h]
  VARIANTARG *v476; // [rsp+1E8h] [rbp-170h] BYREF
  unsigned int *v477; // [rsp+1F0h] [rbp-168h]
  __int64 v478; // [rsp+1F8h] [rbp-160h]
  VARIANTARG *v479; // [rsp+200h] [rbp-158h] BYREF
  unsigned int *v480; // [rsp+208h] [rbp-150h]
  __int64 v481; // [rsp+210h] [rbp-148h]
  VARIANTARG *v482; // [rsp+218h] [rbp-140h] BYREF
  unsigned int *v483; // [rsp+220h] [rbp-138h]
  __int64 v484; // [rsp+228h] [rbp-130h]
  __int128 v485; // [rsp+230h] [rbp-128h] BYREF
  __int64 v486; // [rsp+240h] [rbp-118h]
  __m128i v487; // [rsp+248h] [rbp-110h] BYREF
  __int64 v488; // [rsp+258h] [rbp-100h]
  VARIANTARG *v489; // [rsp+260h] [rbp-F8h] BYREF
  unsigned int *v490; // [rsp+268h] [rbp-F0h]
  __int64 v491; // [rsp+270h] [rbp-E8h]
  VARIANTARG *v492; // [rsp+278h] [rbp-E0h] BYREF
  unsigned int *v493; // [rsp+280h] [rbp-D8h]
  __int64 v494; // [rsp+288h] [rbp-D0h]
  VARIANTARG *v495; // [rsp+290h] [rbp-C8h] BYREF
  unsigned int *v496; // [rsp+298h] [rbp-C0h]
  __int64 v497; // [rsp+2A0h] [rbp-B8h]
  VARIANTARG *v498; // [rsp+2A8h] [rbp-B0h] BYREF
  unsigned int *v499; // [rsp+2B0h] [rbp-A8h]
  __int64 v500; // [rsp+2B8h] [rbp-A0h]
  __int128 v501; // [rsp+2C0h] [rbp-98h] BYREF
  __int64 v502; // [rsp+2D0h] [rbp-88h]
  __int128 v503; // [rsp+2E0h] [rbp-78h] BYREF
  __int64 v504; // [rsp+2F0h] [rbp-68h]
  _BYTE v505[88]; // [rsp+300h] [rbp-58h] BYREF
  struct VAR *v506; // [rsp+368h] [rbp+10h] BYREF
  int TypeProto; // [rsp+370h] [rbp+18h] BYREF
  int v508; // [rsp+378h] [rbp+20h] BYREF

  v506 = a2;
  TypeProto = 0;
  v3 = *((_QWORD *)this + 32);
  v4 = *((_QWORD *)this + 33);
  v470 = v4;
  v447 = 0;
  v448 = 0;
  v439 = 0;
  v440 = 0;
  v508 = 0;
  v451 = 0;
  v5 = *(struct ExecBody **)(**((_QWORD **)this + 7) + 56LL);
  v471 = v5;
  v6 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 17) = v6;
  v450 = BREAKREASON_STEP;
  *((_QWORD *)this + 44) = &v506;
  *((_QWORD *)this + 43) = &v441;
  *((_QWORD *)this + 30) = *((_QWORD *)this + 31);
  v7 = *((_QWORD *)this + 20);
  *((_QWORD *)this + 19) = v7;
  *((_DWORD *)this + 42) = -1;
  *((_DWORD *)this + 84) = -2;
  *((_QWORD *)this + 25) = v6;
  *((_QWORD *)this + 26) = v7;
  if ( a2 )
    *(_WORD *)a2 = 0;
  else
    *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 76) |= 2u;
  TLS_NoDestructor::TLS_NoDestructor(
    (TLS_NoDestructor *)v505,
    *((struct COleScript **)this + 1),
    *(struct ThreadGlobals **)(*(_QWORD *)this + 984LL));
  v449.vt = 0;
  v499 = *(unsigned int **)this;
  v498 = &v449;
  v500 = *((_QWORD *)v499 + 122);
  *((_QWORD *)v499 + 122) = &v498;
  while ( 2 )
  {
    v8 = (unsigned __int8 *)*((_QWORD *)this + 19);
    v9 = *v8;
    v10 = v8 + 1;
    *((_QWORD *)this + 19) = v8 + 1;
    switch ( v9 )
    {
      case 0:
      case 2:
      case 99:
      case 100:
        goto LABEL_22;
      case 1:
      case 90:
        v315 = v506;
        if ( !v506 )
          goto LABEL_533;
        v316 = *((_QWORD *)this + 29);
        if ( v316 )
        {
          *(_OWORD *)v506 = *(_OWORD *)v316;
          *((_QWORD *)v315 + 2) = *(_QWORD *)(v316 + 16);
          TypeProto = 0;
        }
        else
        {
          *(_WORD *)v506 = 0;
LABEL_533:
          TypeProto = 0;
        }
        goto LABEL_850;
      case 3:
        v11 = *v10;
        *((_QWORD *)this + 19) = v8 + 2;
        *((_DWORD *)this + 42) = v11;
        goto LABEL_6;
      case 4:
        v427 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *((_DWORD *)this + 42) = v427;
        goto LABEL_6;
      case 5:
        v426 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        *((_DWORD *)this + 42) = v426;
LABEL_6:
        if ( !(unsigned int)CSession::FInterrupt(*(CSession **)this) )
          goto LABEL_7;
        TypeProto = CSession::HandleHalt(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        TypeProto = CSession::HandleAbort(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)this, *((_DWORD *)this + 8), &v450) )
        {
          v341 = v450;
        }
        else
        {
          if ( !(unsigned int)CScriptBody::FBreak(
                                **((CScriptBody ***)this + 7),
                                *((_DWORD *)this + 42) + *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 16LL) + 24LL)) )
            goto LABEL_7;
          v341 = BREAKREASON_BREAKPOINT;
        }
        TypeProto = CScriptRuntime::Break(this, v341);
        if ( TypeProto < 0 )
          goto LABEL_9;
LABEL_7:
        v12 = (GcContext *)*((_QWORD *)this + 15);
        if ( *((_DWORD *)v12 + 2) )
LABEL_198:
          GcContext::Collect(v12);
LABEL_8:
        TypeProto = CSession::PollHalt(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        goto LABEL_22;
      case 6:
        v131 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        *((_DWORD *)this + 42) = v131;
        TypeProto = CScriptRuntime::Break(this, BREAKREASON_BREAKPOINT);
        if ( TypeProto < 0 )
          goto LABEL_9;
        TypeProto = CSession::HandleHalt(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        v12 = (GcContext *)*((_QWORD *)this + 15);
        if ( *((_DWORD *)v12 + 2) )
          goto LABEL_198;
        goto LABEL_8;
      case 7:
        *((_QWORD *)this + 18) -= 24LL;
        **((_WORD **)this + 18) = 3;
        v195 = (char *)*((_QWORD *)this + 19);
        v196 = *v195;
        v197 = v195 + 1;
        goto LABEL_292;
      case 8:
        v232 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v232;
        *v232 = 3;
        v233 = (_DWORD *)*((_QWORD *)this + 19);
        v196 = *v233;
        v197 = (char *)(v233 + 1);
        goto LABEL_292;
      case 9:
        v269 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v269;
        *v269 = 5;
        v270 = (__int64 *)*((_QWORD *)this + 19);
        v271 = *v270;
        *((_QWORD *)this + 19) = v270 + 1;
        *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v271;
        goto LABEL_22;
      case 10:
        v127 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        GcAlloc = CScriptRuntime::GetGcAlloc(this);
        v439 = GcAlloc::PvarAlloc(GcAlloc);
        if ( v439 )
        {
          v129 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v129;
          *v129 = 128;
          *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v439;
          v130 = v127;
LABEL_194:
          VAR::SetConstBstr(v439, (unsigned __int16 *)(*((_QWORD *)this + 22) + v130), v5);
          goto LABEL_22;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 11:
        v245 = *(unsigned int *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        v246 = CScriptRuntime::GetGcAlloc(this);
        v439 = GcAlloc::PvarAlloc(v246);
        if ( v439 )
        {
          v431 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v431;
          *v431 = 128;
          *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v439;
          VAR::SetConstBstr(v439, (unsigned __int16 *)(*((_QWORD *)this + 22) + v245), v5);
          v432 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v432;
          *v432 = 0;
          TypeProto = CSession::GetTypeProto(*(CSession **)this, 7, *((struct VAR **)this + 18));
          if ( TypeProto >= 0 )
          {
            TypeProto = RegExpObj::CreateFromCode(
                          &v440,
                          *(struct CSession **)this,
                          (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
                          *((struct VAR **)this + 18),
                          0);
            if ( TypeProto >= 0 )
            {
              v433 = (VAR *)(*((_QWORD *)this + 18) + 24LL);
              *((_QWORD *)this + 18) = v433;
              TypeProto = VAR::SetHeapJsObj(v433, *(struct CSession **)this, v440);
              if ( TypeProto < 0 )
                (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v440 + 16LL))(v440);
              if ( TypeProto >= 0 )
                goto LABEL_22;
            }
          }
        }
        else
        {
          TypeProto = -2147024882;
        }
        goto LABEL_36;
      case 12:
        v241 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v241;
        *v241 = 11;
        *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = 0;
        goto LABEL_22;
      case 13:
        v242 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v242;
        *v242 = 11;
        *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = -1;
        goto LABEL_22;
      case 14:
        v198 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v198;
        *v198 = 1;
        goto LABEL_22;
      case 15:
        v268 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v268;
        *v268 = 0;
        goto LABEL_22;
      case 16:
        v210 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v211 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v211;
        *v211 = 0;
        if ( (unsigned int)CScriptRuntime::FNamedLocals(this) )
        {
          LocalName = CScriptRuntime::GetLocalName(this, v210);
          if ( LocalName )
          {
            v213 = (struct VAR *)*((_QWORD *)this + 31);
            v214 = (struct VAR *)*((_QWORD *)this + 18);
            v215 = SYM::InitFromSymbol((SYM *)&v447, LocalName);
            TypeProto = CScriptRuntime::GetVarVal(this, v215, v214, v213);
            if ( !(unsigned int)FNo(TypeProto) )
              goto LABEL_356;
          }
        }
        v216 = (int)v210 < 0;
        if ( (_DWORD)v210 )
          goto LABEL_838;
        if ( *((_QWORD *)this + 14) )
          goto LABEL_835;
        VarVal = CScriptRuntime::GetVarVal(this, (struct SYM *)&g_sym_arguments, *((struct VAR **)this + 18), 0);
        goto LABEL_201;
      case 17:
        v80 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *((_QWORD *)this + 18) -= 24LL;
        **((_WORD **)this + 18) = 0;
        if ( (unsigned int)CScriptRuntime::FNamedLocals(this) )
        {
          v247 = CScriptRuntime::GetLocalName(this, v80);
          if ( v247 )
          {
            v248 = (struct VAR *)*((_QWORD *)this + 31);
            v249 = (struct VAR *)*((_QWORD *)this + 18);
            v250 = SYM::InitFromSymbol((SYM *)&v447, v247);
            TypeProto = CScriptRuntime::GetVarAdr(this, v250, v249, v248);
            if ( !(unsigned int)FNo(TypeProto) )
              goto LABEL_356;
          }
        }
        if ( (_DWORD)v80 )
        {
          v81 = *((_QWORD *)this + 18);
          if ( (int)v80 < 0 )
            v82 = v4 + 24 * v80;
          else
            v82 = v3 + 24LL * -(int)v80;
          *(_WORD *)v81 = 16396;
          *(_QWORD *)(v81 + 8) = v82;
          goto LABEL_22;
        }
        if ( !*((_QWORD *)this + 14) )
        {
          VarVal = CScriptRuntime::GetVarAdr(this, (struct SYM *)&g_sym_arguments, *((struct VAR **)this + 18), 0);
          goto LABEL_201;
        }
        if ( *((_QWORD *)this + 13) || (TypeProto = CScriptRuntime::EnsureArguments(this), TypeProto >= 0) )
        {
          v253 = *((_QWORD *)this + 18);
          v254 = *((_QWORD *)this + 14);
          *(_WORD *)v253 = 16396;
          *(_QWORD *)(v253 + 8) = v254;
          goto LABEL_22;
        }
        goto LABEL_36;
      case 18:
        v210 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v255 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v255;
        *v255 = 0;
        if ( (unsigned int)CScriptRuntime::FNamedLocals(this)
          && (v256 = CScriptRuntime::GetLocalName(this, v210)) != 0
          && (v257 = (struct VAR *)*((_QWORD *)this + 31),
              v258 = (struct VAR *)*((_QWORD *)this + 18),
              v259 = SYM::InitFromSymbol((SYM *)&v447, v256),
              TypeProto = CScriptRuntime::GetFncAdr(this, v259, v258, v257),
              !(unsigned int)FNo(TypeProto)) )
        {
LABEL_356:
          if ( !(unsigned int)FErr(TypeProto) )
            goto LABEL_22;
        }
        else
        {
          v216 = (int)v210 < 0;
          if ( (_DWORD)v210 )
          {
LABEL_838:
            if ( v216 )
              v435 = v4 + 24 * v210;
            else
              v435 = v3 + 24LL * -(int)v210;
            v436 = *((_QWORD *)this + 18);
            *(_OWORD *)v436 = *(_OWORD *)v435;
            *(_QWORD *)(v436 + 16) = *(_QWORD *)(v435 + 16);
            goto LABEL_22;
          }
          if ( *((_QWORD *)this + 14) )
          {
LABEL_835:
            if ( *((_QWORD *)this + 13) || (TypeProto = CScriptRuntime::EnsureArguments(this), TypeProto >= 0) )
            {
              v194 = (VAR *)*((_QWORD *)this + 14);
LABEL_290:
              v37 = *((_QWORD *)this + 18);
              *(_OWORD *)v37 = *(_OWORD *)v194;
              pRecInfo = (IRecordInfo *)*((_QWORD *)v194 + 2);
LABEL_43:
              *(_QWORD *)(v37 + 16) = pRecInfo;
              goto LABEL_22;
            }
          }
          else
          {
            VarVal = CScriptRuntime::GetFncAdr(this, (struct SYM *)&g_sym_arguments, *((struct VAR **)this + 18), 0);
LABEL_201:
            TypeProto = VarVal;
            if ( VarVal >= 0 )
              goto LABEL_22;
            if ( VarVal != -2040119292 )
            {
              v28 = (const unsigned __int16 *)g_sym_arguments;
LABEL_32:
              v29 = 0;
LABEL_33:
              v30 = VarVal;
LABEL_34:
              v31 = CSession::RecordHr(*(CSession **)this, v30, v29, v28, -1);
LABEL_35:
              TypeProto = v31;
              goto LABEL_36;
            }
          }
        }
        goto LABEL_36;
      case 19:
        v132 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v133 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v133;
        *v133 = 0;
        if ( !(unsigned int)CScriptRuntime::FNamedLocals(this)
          || (v134 = CScriptRuntime::GetLocalName(this, v132)) == 0
          || (v135 = (struct VAR *)*((_QWORD *)this + 31),
              v136 = (struct VAR *)*((_QWORD *)this + 18),
              v137 = SYM::InitFromSymbol((SYM *)&v447, v134),
              TypeProto = CScriptRuntime::GetDelAdr(this, v137, v136, v135),
              (unsigned int)FNo(TypeProto)) )
        {
          ++*((_QWORD *)this + 19);
          **((_WORD **)this + 18) = 11;
          *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = 0;
          goto LABEL_22;
        }
        if ( !(unsigned int)FErr(TypeProto) )
          goto LABEL_22;
        goto LABEL_36;
      case 20:
        *((_QWORD *)this + 18) -= 24LL;
        v56 = *(__int16 *)v10;
        v51 = *(_OWORD *)(v3 + 24 * v56);
        v52 = *(_QWORD *)(v3 + 24 * v56 + 16);
        goto LABEL_65;
      case 21:
        v184 = *((_QWORD *)this + 18);
        v185 = 3LL * *(__int16 *)v10;
        *(_OWORD *)(v3 + 8 * v185) = *(_OWORD *)v184;
        *(_QWORD *)(v3 + 8 * v185 + 16) = *(_QWORD *)(v184 + 16);
        *((_QWORD *)this + 19) += 2LL;
        goto LABEL_22;
      case 22:
        v226 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v226;
        v227 = 24LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)v226 = 16396;
        *(_QWORD *)(v226 + 8) = v3 + v227;
        goto LABEL_22;
      case 23:
      case 27:
        *((_QWORD *)this + 19) = v8 + 3;
        v272 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v272;
        *((_QWORD *)this + 19) = v8 + 4;
        *v272 = 11;
        *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = 0;
        goto LABEL_22;
      case 24:
        *((_QWORD *)this + 18) -= 24LL;
        v50 = *(__int16 *)v10;
        v51 = *(_OWORD *)(v4 + 24 * v50);
        v52 = *(_QWORD *)(v4 + 24 * v50 + 16);
LABEL_65:
        v53 = *((_QWORD *)this + 18);
        *((_QWORD *)this + 19) = v10 + 2;
        *(_OWORD *)v53 = v51;
        *(_QWORD *)(v53 + 16) = v52;
        goto LABEL_22;
      case 25:
        v234 = *((_QWORD *)this + 18);
        v235 = 3LL * *(__int16 *)v10;
        *(_OWORD *)(v4 + 8 * v235) = *(_OWORD *)v234;
        *(_QWORD *)(v4 + 8 * v235 + 16) = *(_QWORD *)(v234 + 16);
        *((_QWORD *)this + 19) += 2LL;
        goto LABEL_22;
      case 26:
        v243 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v243;
        v244 = v4 + 24LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)v243 = 16396;
        *(_QWORD *)(v243 + 8) = v244;
        goto LABEL_22;
      case 28:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        *((_QWORD *)this + 18) -= 24LL;
        **((_WORD **)this + 18) = 0;
        v25 = (struct VAR *)*((_QWORD *)this + 18);
        v26 = SYM::InitFromSymbol((SYM *)&v447, v24);
        VarVal = CScriptRuntime::GetVarVal(this, v26, v25, 0);
        goto LABEL_29;
      case 29:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v222 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v222;
        *v222 = 0;
        v223 = (struct VAR *)*((_QWORD *)this + 18);
        v224 = SYM::InitFromSymbol((SYM *)&v447, v24);
        VarVal = CScriptRuntime::GetVarAdr(this, v224, v223, 0);
        goto LABEL_29;
      case 30:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v160 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v160;
        *v160 = 0;
        v161 = (struct VAR *)*((_QWORD *)this + 18);
        v162 = SYM::InitFromSymbol((SYM *)&v447, v24);
        VarVal = CScriptRuntime::GetFncAdr(this, v162, v161, 0);
        goto LABEL_29;
      case 31:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v273 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v273;
        *v273 = 0;
        v274 = (struct VAR *)*((_QWORD *)this + 18);
        v275 = SYM::InitFromSymbol((SYM *)&v447, v24);
        VarVal = CScriptRuntime::GetDelAdr(this, v275, v274, 0);
LABEL_29:
        TypeProto = VarVal;
        if ( VarVal >= 0 )
          goto LABEL_22;
        if ( VarVal == -2040119292 )
          goto LABEL_36;
        v28 = v24;
        goto LABEL_32;
      case 32:
        *((_QWORD *)this + 18) -= 24LL;
        TypeProto = CScriptRuntime::EnsureThis(this);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v194 = (VAR *)*((_QWORD *)this + 27);
        goto LABEL_290;
      case 33:
        v157 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        *((_QWORD *)this + 18) -= 24LL;
        **((_WORD **)this + 18) = 0;
        SYM::InitFromSymbol((SYM *)&v447, v157);
        v158 = *((_QWORD *)this + 18);
        v501 = *(_OWORD *)(v158 + 24);
        v502 = *(_QWORD *)(v158 + 40);
        if ( (unsigned __int8)CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(this, &v501)
          && (TypeProto = NameTbl::GetValSimpleInScope(
                            *((NameTbl **)this + 36),
                            (struct SYM *)&v447,
                            *((struct VAR **)this + 18)),
              (unsigned int)FYes(TypeProto))
          || (v159 = VAR::InvokeByName(
                       (VAR *)(*((_QWORD *)this + 18) + 24LL),
                       *(struct CSession **)this,
                       (struct SYM *)&v447,
                       2u,
                       *((VARIANTARG **)this + 18),
                       0,
                       0),
              TypeProto = v159,
              v159 >= 0) )
        {
          v308 = *((_QWORD *)this + 18);
          *(_OWORD *)(v308 + 24) = *(_OWORD *)v308;
          *(_QWORD *)(v308 + 40) = *(_QWORD *)(v308 + 16);
          *((_QWORD *)this + 18) += 24LL;
          goto LABEL_22;
        }
        if ( v159 != -2040119292 )
          TypeProto = CSession::RecordHr(
                        *(CSession **)this,
                        v159,
                        (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
                        v157,
                        -1);
        goto LABEL_36;
      case 34:
        v19 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v20 = (VAR **)*((_QWORD *)this + 18);
        if ( *(_WORD *)v20 == 128 )
        {
          v439 = v20[1];
          if ( !(unsigned int)VAR::FCanCastToObj(v439) )
          {
LABEL_412:
            v31 = CSession::RecordHr(*(CSession **)this, -2146823281, *((struct VAR **)this + 18), 0, 0);
            goto LABEL_35;
          }
          v21 = (__int128 *)*((_QWORD *)this + 18);
          v503 = *v21;
          v504 = *((_QWORD *)v21 + 2);
          if ( !(unsigned __int8)CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(this, &v503) )
            goto LABEL_27;
          v140 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v140;
          *v140 = 0;
          v141 = (NameTbl *)*((_QWORD *)this + 36);
          v142 = (struct VAR *)*((_QWORD *)this + 18);
          v143 = SYM::InitFromSymbol((SYM *)&v447, v19);
          TypeProto = NameTbl::GetAdrSimpleInScope(v141, v143, v142);
          v144 = (unsigned int)FYes(TypeProto) == 0;
          v121 = *((_QWORD *)this + 18);
          if ( v144 )
          {
            *((_QWORD *)this + 18) = v121 + 24;
LABEL_27:
            v22 = *((_QWORD *)this + 18);
            v23 = v439;
            *(_WORD *)v22 = 132;
            *(_QWORD *)(v22 + 8) = v23;
            *(_QWORD *)(v22 + 16) = v19;
            goto LABEL_22;
          }
          goto LABEL_186;
        }
        if ( !(unsigned int)VAR::FCanCastToObj((VAR *)v20) )
          goto LABEL_412;
        v102 = CScriptRuntime::GetGcAlloc(this);
        v103 = GcAlloc::PvarAlloc(v102);
        v439 = v103;
        if ( v103 )
        {
          v104 = *((_QWORD *)this + 18);
          *(_OWORD *)v103 = *(_OWORD *)v104;
          *((_QWORD *)v103 + 2) = *(_QWORD *)(v104 + 16);
          goto LABEL_27;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 35:
        v40 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v36 = 3 * v40;
        v41 = (VAR *)(*((_QWORD *)this + 18) + 24 * v40);
        v439 = v41;
        if ( *(_WORD *)v41 == 16396 )
        {
          v145 = *((_QWORD *)v41 + 1);
          *(_OWORD *)v41 = *(_OWORD *)v145;
          *((_QWORD *)v41 + 2) = *(_QWORD *)(v145 + 16);
          v41 = v439;
        }
        v449.vt = 0;
        v42 = &v449;
        if ( **((_BYTE **)this + 19) == 66 )
          v42 = 0;
        v43 = 3;
        if ( !(_WORD)v40 )
          v43 = 1;
        TypeProto = VAR::InvokeByDispID(
                      v41,
                      *(struct CSession **)this,
                      0,
                      v43,
                      v42,
                      v40,
                      *((struct VAR **)this + 18),
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        goto LABEL_42;
      case 36:
        v309 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v310 = (VAR *)(*((_QWORD *)this + 18) + 24 * v309);
        v439 = v310;
        if ( *(_WORD *)v310 == 16396 )
        {
          v311 = *((_QWORD *)v310 + 1);
          *(_OWORD *)v310 = *(_OWORD *)v311;
          *((_QWORD *)v310 + 2) = *(_QWORD *)(v311 + 16);
          v310 = v439;
        }
        TypeProto = VAR::InvokeByDispID(v310, *(struct CSession **)this, 0, 1u, 0, v309, *((struct VAR **)this + 18), 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v312 = (unsigned int)(v309 + 1);
        goto LABEL_525;
      case 37:
        v317 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        if ( !(_DWORD)v317 )
          goto LABEL_542;
        v370 = (unsigned int)(v317 + 1);
        v371 = 3 * v370;
        v372 = (VAR *)(*((_QWORD *)this + 18) + 24 * v370);
        v439 = v372;
        if ( *(_WORD *)v372 == 16396 )
        {
          v373 = *((_QWORD *)v372 + 1);
          *(_OWORD *)v372 = *(_OWORD *)v373;
          *((_QWORD *)v372 + 2) = *(_QWORD *)(v373 + 16);
          v372 = v439;
        }
        TypeProto = VAR::InvokeByDispID(
                      v372,
                      *(struct CSession **)this,
                      0,
                      0xCu,
                      0,
                      v370,
                      *((struct VAR **)this + 18),
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v374 = *((_QWORD *)this + 18);
        v375 = 3 * (v317 + 1);
        *(_OWORD *)(v374 + 8 * v375) = *(_OWORD *)v374;
        *(_QWORD *)(v374 + 8 * v375 + 16) = *(_QWORD *)(v374 + 16);
        *((_QWORD *)this + 18) += 8 * v371;
        goto LABEL_22;
      case 38:
        v318 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        if ( !(_DWORD)v318 )
        {
LABEL_542:
          v28 = 0;
          v29 = 0;
          v30 = -2146823285;
          goto LABEL_34;
        }
        v319 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v319;
        *(_OWORD *)v319 = *(_OWORD *)(v319 + 24 * (v318 + 2));
        *(_QWORD *)(v319 + 16) = *(_QWORD *)(v319 + 24 * (v318 + 2) + 16);
        v320 = (unsigned int)(v318 + 1);
        v321 = (VAR *)(*((_QWORD *)this + 18) + 24 * v320);
        v439 = v321;
        if ( *(_WORD *)v321 == 16396 )
        {
          v322 = *((_QWORD *)v321 + 1);
          *(_OWORD *)v321 = *(_OWORD *)v322;
          *((_QWORD *)v321 + 2) = *(_QWORD *)(v322 + 16);
          v321 = v439;
        }
        TypeProto = VAR::InvokeByDispID(
                      v321,
                      *(struct CSession **)this,
                      0,
                      0xCu,
                      0,
                      v320,
                      *((struct VAR **)this + 18),
                      0);
        if ( TypeProto >= 0 )
        {
          v312 = (unsigned int)(v318 + 3);
LABEL_525:
          *((_QWORD *)this + 18) += 24 * v312;
          goto LABEL_22;
        }
        goto LABEL_36;
      case 39:
        v34 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v35 = (struct VAR *)*((_QWORD *)this + 18);
        v36 = 3 * v34;
        v439 = (struct VAR *)((char *)v35 + 24 * v34);
        TypeProto = VAR::InvokeByDispID(v439, *(struct CSession **)this, 0, 0x4000u, &v449, v34, v35, 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
LABEL_42:
        v37 = *((_QWORD *)this + 18) + 8 * v36;
        *((_QWORD *)this + 18) = v37;
        *(_OWORD *)v37 = *(_OWORD *)&v449.vt;
        pRecInfo = v449.pRecInfo;
        goto LABEL_43;
      case 40:
        v83 = (struct IDispatch **)VAR::PvarCutHeap((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( !(unsigned int)VAR::FCanCastToObj((VAR *)v83) )
          goto LABEL_466;
        if ( *(_WORD *)v83 == 9 && (unsigned int)CSession::IsIE3(*(CSession **)this) )
        {
          v84 = (VAR *)*((_QWORD *)this + 18);
          v439 = v84;
          *((_QWORD *)this + 18) = (char *)v84 - 24;
          *((_WORD *)v84 - 12) = 0;
          TypeProto = ConvertToString(
                        *(struct CSession **)this,
                        (struct IDispatch ***)&v439,
                        *((VARIANTARG **)this + 18),
                        1);
          if ( TypeProto < 0 )
            goto LABEL_36;
          v85 = SYM::InitFromBstr((SYM *)&v447, *((const unsigned __int16 **)v439 + 1));
          DispatchDispID = GetDispatchDispID(*(struct CSession **)this, v83[1], v85, &v451);
          TypeProto = DispatchDispID;
          *((_QWORD *)this + 18) += 24LL;
          v87 = *((_QWORD *)this + 18);
          if ( DispatchDispID >= 0 )
          {
            v88 = VAR::InvokeByDispID(
                    (VAR *)(v87 + 24),
                    *(struct CSession **)this,
                    v451,
                    2u,
                    (VARIANTARG *)(v87 + 24),
                    0,
                    0,
                    0);
            goto LABEL_131;
          }
          if ( DispatchDispID == -2147352570 )
          {
            v295 = SYM::InitFromPsz((SYM *)&v447, L"item");
            v88 = VAR::InvokeByName(
                    (VAR *)(v87 + 24),
                    *(struct CSession **)this,
                    v295,
                    1u,
                    (VARIANTARG *)(v87 + 24),
                    1,
                    (struct VAR *)v87);
LABEL_131:
            TypeProto = v88;
            if ( v88 < 0 )
              goto LABEL_36;
            *((_QWORD *)this + 18) += 24LL;
LABEL_22:
            v4 = v470;
            goto LABEL_23;
          }
        }
        else
        {
          v186 = VAR::InvokeByVar(
                   (VAR **)(*((_QWORD *)this + 18) + 24LL),
                   *(struct CSession **)this,
                   *((const unsigned __int16 ***)this + 18),
                   2u,
                   (VARIANTARG *)(*((_QWORD *)this + 18) + 24LL),
                   0,
                   0);
LABEL_267:
          TypeProto = v186;
          if ( v186 >= 0 )
          {
            *((_QWORD *)this + 18) += 24LL;
            goto LABEL_22;
          }
        }
        goto LABEL_36;
      case 41:
        TypeProto = VAR::InvokeByVar(
                      (VAR **)(*((_QWORD *)this + 18) + 48LL),
                      *(struct CSession **)this,
                      (const unsigned __int16 **)(*((_QWORD *)this + 18) + 24LL),
                      0xCu,
                      0,
                      1,
                      *((struct VAR **)this + 18));
        if ( TypeProto < 0 )
          goto LABEL_36;
        v156 = *((_QWORD *)this + 18);
        *(_OWORD *)(v156 + 48) = *(_OWORD *)v156;
        *(_QWORD *)(v156 + 64) = *(_QWORD *)(v156 + 16);
        goto LABEL_233;
      case 42:
        v439 = VAR::PvarCutHeap((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( (unsigned int)VAR::FCanCastToObj(v439) )
        {
          v146 = (VAR *)(*((_QWORD *)this + 18) + 24LL);
          if ( v439 != v146
            || (v147 = (GcContext **)CScriptRuntime::GetGcAlloc(this),
                TypeProto = VAR::MoveToHeap((VARIANTARG *)v146, v147),
                TypeProto >= 0) )
          {
            v148 = VAR::PvarCutHeap(*((VAR **)this + 18));
            v149 = v148;
            v439 = v148;
            v150 = *(unsigned __int16 *)v148;
            if ( v150 == 3 || (v151 = v150 - 5) == 0 )
            {
              v279 = (VARIANTARG *)*((_QWORD *)this + 18);
              if ( v148 != (VAR *)v279
                || (v280 = (GcContext **)CScriptRuntime::GetGcAlloc(this),
                    TypeProto = VAR::MoveToHeap(v279, v280),
                    TypeProto >= 0) )
              {
                v149 = *(VAR **)(*((_QWORD *)this + 18) + 8LL);
                v439 = v149;
LABEL_230:
                v154 = *((_QWORD *)this + 18);
                v155 = *(_QWORD *)(v154 + 32);
                *(_WORD *)(v154 + 24) = 133;
                *(_QWORD *)(v154 + 32) = v155;
                *(_QWORD *)(v154 + 40) = v149;
                goto LABEL_19;
              }
            }
            else
            {
              v152 = v151 - 3;
              if ( !v152 )
                goto LABEL_230;
              v153 = v152 - 122;
              if ( !v153 || v153 == 13 )
                goto LABEL_230;
              TypeProto = ConvertToString(
                            *(struct CSession **)this,
                            (struct IDispatch ***)&v439,
                            *((VARIANTARG **)this + 18),
                            1);
              if ( TypeProto >= 0 )
              {
                v149 = v439;
                goto LABEL_230;
              }
            }
          }
        }
        else
        {
LABEL_466:
          TypeProto = CSession::RecordHr(
                        *(CSession **)this,
                        -2146823281,
                        (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
                        0,
                        1);
        }
        goto LABEL_36;
      case 43:
        v439 = VAR::PvarCutHeap(*((VAR **)this + 18));
        if ( *(_WORD *)v439 != 3
          && *(_WORD *)v439 != 5
          && *(_WORD *)v439 != 8
          && *(_WORD *)v439 != 130
          && *(_WORD *)v439 != 143 )
        {
          TypeProto = ConvertToString(
                        *(struct CSession **)this,
                        (struct IDispatch ***)&v439,
                        *((VARIANTARG **)this + 18),
                        1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        goto LABEL_22;
      case 44:
        v90 = (VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v90 == 131 )
        {
          TypeProto = VAR::InvokeDispMem(v90, *(struct CSession **)this, 2u, v90, 0, 0);
          if ( TypeProto >= 0 )
            goto LABEL_22;
        }
        else if ( *(_WORD *)v90 == 132 )
        {
          v299 = VAR::InvokeDispName(v90, *(struct CSession **)this, 2u, v90, 0, 0);
LABEL_471:
          TypeProto = v299;
          if ( v299 >= 0 )
            goto LABEL_22;
        }
        else
        {
          if ( *(_WORD *)v90 != 133 )
          {
            if ( *(_WORD *)v90 == 16396 )
            {
              v91 = *((_QWORD *)v90 + 1);
              *(_OWORD *)v90 = *(_OWORD *)v91;
              *((_QWORD *)v90 + 2) = *(_QWORD *)(v91 + 16);
            }
            goto LABEL_22;
          }
          TypeProto = VAR::InvokeDispVar(v90, *(struct CSession **)this, 2u, v90, 0, 0);
          if ( TypeProto >= 0 )
            goto LABEL_22;
        }
        goto LABEL_36;
      case 45:
        v67 = *((_QWORD *)this + 18);
        v68 = *(unsigned __int16 *)(v67 + 24);
        if ( v68 == 132 )
        {
          if ( *(_QWORD *)(v67 + 32) )
          {
            v120 = VAR::InvokeDispName(
                     (VAR *)(v67 + 24),
                     *(struct CSession **)this,
                     0xCu,
                     0,
                     1,
                     *((struct VAR **)this + 18));
          }
          else
          {
            v296 = *((_QWORD *)this + 36);
            v297 = *(__int64 (__fastcall **)(__int64, struct SYM *, _QWORD, __int64, _QWORD))(*(_QWORD *)v296 + 128LL);
            v298 = SYM::InitFromSymbol((SYM *)&v447, *(const unsigned __int16 **)(v67 + 40));
            v120 = v297(v296, v298, 0, v67, 0);
          }
LABEL_184:
          TypeProto = v120;
          if ( v120 >= 0 )
            goto LABEL_185;
          goto LABEL_36;
        }
        v69 = v68 - 131;
        if ( !v69 )
        {
          v120 = VAR::InvokeDispMem(
                   (VAR *)(v67 + 24),
                   *(struct CSession **)this,
                   0xCu,
                   0,
                   1,
                   *((struct VAR **)this + 18));
          goto LABEL_184;
        }
        v70 = v69 - 2;
        if ( v70 )
        {
          if ( v70 != 16263 )
          {
            v28 = 0;
            v29 = (struct VAR *)(v67 + 24);
            v30 = -2146823280;
            goto LABEL_34;
          }
          v71 = *(_QWORD *)(v67 + 32);
          *(_OWORD *)v71 = *(_OWORD *)v67;
          *(_QWORD *)(v71 + 16) = *(_QWORD *)(v67 + 16);
LABEL_185:
          v121 = *((_QWORD *)this + 18);
LABEL_186:
          *(_OWORD *)(v121 + 24) = *(_OWORD *)v121;
          *(_QWORD *)(v121 + 40) = *(_QWORD *)(v121 + 16);
          goto LABEL_19;
        }
        TypeProto = VAR::InvokeDispVar(
                      (VAR *)(v67 + 24),
                      *(struct CSession **)this,
                      0xCu,
                      0,
                      1,
                      *((struct VAR **)this + 18));
        if ( TypeProto >= 0 )
          goto LABEL_185;
LABEL_36:
        if ( TypeProto == -2147352318 )
          goto LABEL_37;
        if ( TypeProto != -2040119292 )
          TypeProto = CSession::RecordHr(*(CSession **)this, TypeProto, 0, 0, -1);
        if ( TypeProto != -2147352319 && (int)CScriptRuntime::ConstructErrorObject(this, (struct VAR *)&v449) >= 0 )
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)this + 1208LL));
          if ( *(_QWORD *)this != -1208 )
          {
            VAR::GetStdVar((VAR *)&v449, (struct tagVARIANT *)(*(_QWORD *)this + 1208LL));
            if ( (int)CSession::CanHandleException(*(CSession **)this) >= 0 )
              goto LABEL_37;
            if ( TypeProto == -2147352319
              || !(unsigned int)CSession::FReportError(*(CSession **)this)
              || !(unsigned int)CScriptRuntime::FResumeFromRuntimeError(this, &TypeProto, 1) )
            {
              goto LABEL_9;
            }
LABEL_23:
            v5 = v471;
            continue;
          }
        }
LABEL_9:
        if ( TypeProto < 0 )
          TypeProto = CSession::ReportError(*(CSession **)this, TypeProto);
LABEL_850:
        CSession::StepOutComplete(*(CSession **)this, *((_DWORD *)this + 8));
        *((_DWORD *)this + 76) &= ~2u;
        TLS_NoDestructor::Close((TLS_NoDestructor *)v505);
        GCRootStack::Pop((GCRootStack *)(v499 + 236));
        return (unsigned int)TypeProto;
      case 46:
        v72 = *((_QWORD *)this + 18);
        switch ( *(_WORD *)v72 )
        {
          case 0x83:
            TypeProto = VAR::InvokeDispMem((VAR *)v72, *(struct CSession **)this, 0xCu, 0, 1, (struct VAR *)(v72 + 24));
            if ( TypeProto < 0 )
              goto LABEL_36;
            v18 = *((_QWORD *)this + 18) + 48LL;
            break;
          case 0x84:
            if ( !*(_QWORD *)(v72 + 8) )
            {
              v181 = *((_QWORD *)this + 36);
              v182 = *(__int64 (__fastcall **)(__int64, struct SYM *, _QWORD, __int64, _QWORD))(*(_QWORD *)v181 + 128LL);
              v183 = SYM::InitFromSymbol((SYM *)&v447, *(const unsigned __int16 **)(v72 + 16));
              TypeProto = v182(v181, v183, 0, v72 + 24, 0);
              if ( TypeProto >= 0 )
                goto LABEL_233;
              goto LABEL_36;
            }
            TypeProto = VAR::InvokeDispName((VAR *)v72, *(struct CSession **)this, 0xCu, 0, 1, (struct VAR *)(v72 + 24));
            if ( TypeProto < 0 )
              goto LABEL_36;
LABEL_233:
            v18 = *((_QWORD *)this + 18) + 48LL;
            break;
          case 0x85:
            TypeProto = VAR::InvokeDispVar((VAR *)v72, *(struct CSession **)this, 0xCu, 0, 1, (struct VAR *)(v72 + 24));
            if ( TypeProto >= 0 )
              goto LABEL_233;
            goto LABEL_36;
          case 0x400C:
            v73 = *(_QWORD *)(v72 + 8);
            *(_OWORD *)v73 = *(_OWORD *)(v72 + 24);
            *(_QWORD *)(v73 + 16) = *(_QWORD *)(v72 + 40);
            v18 = *((_QWORD *)this + 18) + 48LL;
            break;
          default:
            v28 = 0;
            v29 = (struct VAR *)*((_QWORD *)this + 18);
            v30 = -2146823280;
            goto LABEL_34;
        }
LABEL_21:
        *((_QWORD *)this + 18) = v18;
        goto LABEL_22;
      case 47:
        v346 = *((_QWORD *)this + 18);
        v347 = v346 - 24;
        *((_QWORD *)this + 18) = v346 - 24;
        *(_OWORD *)v347 = *(_OWORD *)v346;
        *(_QWORD *)(v347 + 16) = *(_QWORD *)(v346 + 16);
        goto LABEL_22;
      case 48:
        v376 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v377 = (char *)*((_QWORD *)this + 18);
        v378 = 24 * v376;
        v379 = &v377[-24 * v376];
        *((_QWORD *)this + 18) = v379;
        memcpy_0(v379, v377, v378);
        goto LABEL_22;
      case 49:
        v407 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v408 = *((_QWORD *)this + 18);
        v407 *= 3;
        *(_OWORD *)(v408 + 8 * v407) = *(_OWORD *)v408;
        *(_QWORD *)(v408 + 8 * v407 + 16) = *(_QWORD *)(v408 + 16);
        goto LABEL_22;
      case 50:
        v236 = *(int *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        TypeProto = CSession::GetTypeProto(*(CSession **)this, 0, (struct VAR *)&v449);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = ArrayObj::Create(
                      &v440,
                      *(struct ThreadGlobals ***)this,
                      v236,
                      *((struct VAR **)this + 18),
                      (struct VAR *)&v449,
                      0,
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj((VAR *)&v449, *(struct CSession **)this, v440);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v440 + 16LL))(v440);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v237 = (VARIANTARG *)(*((_QWORD *)this + 18) + 24 * v236);
        *((_QWORD *)this + 18) = v237--;
        *((_QWORD *)this + 18) = v237;
        *v237 = v449;
        goto LABEL_22;
      case 51:
        TypeProto = CSession::GetTypeProto(*(CSession **)this, 5, (struct VAR *)&v449);
        if ( TypeProto < 0 )
          goto LABEL_36;
        pvarg = 0;
        TypeProto = NameTbl::Create(&v440, *(struct CSession **)this, (struct VAR *)&v449, 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj((VAR *)&v449, *(struct CSession **)this, v440);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v440 + 16LL))(v440);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v225 = (VARIANTARG *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v225;
        *v225 = v449;
        goto LABEL_22;
      case 52:
        v217 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v218 = VAR::PvarCutAll((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( !(unsigned int)VAR::IsJsObj(v218, &v440) )
          goto LABEL_181;
        v219 = *(__int64 (__fastcall **)(struct NameTbl *, struct SYM *, __int64))(*(_QWORD *)v440 + 272LL);
        v220 = *((_QWORD *)this + 18);
        v221 = SYM::InitFromSymbol((SYM *)&v447, v217);
        Value = v219(v440, v221, v220);
        goto LABEL_18;
      case 53:
        v175 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v175 == 3 )
        {
          v176 = *((_DWORD *)v175 + 2);
          *((_DWORD *)v175 + 2) = v176 + 1;
          v177 = *((_QWORD *)this + 18);
          if ( *(_DWORD *)(v177 + 8) < v176 )
          {
            *(double *)(v177 + 8) = (double)v176 + 1.0;
            **((_WORD **)this + 18) = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v175 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v175, v175, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v230 = (double *)*((_QWORD *)this + 18);
LABEL_381:
        VAR::SetNumber((VAR *)v230, v230[1] + 1.0);
        goto LABEL_22;
      case 54:
        v172 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v172 == 3 )
        {
          v173 = *((_DWORD *)v172 + 2);
          *((_DWORD *)v172 + 2) = v173 - 1;
          v174 = *((_QWORD *)this + 18);
          if ( *(_DWORD *)(v174 + 8) > v173 )
          {
            *(double *)(v174 + 8) = (double)v173 - 1.0;
            **((_WORD **)this + 18) = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v172 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v172, v172, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        VAR::SetNumber(*((VAR **)this + 18), *(double *)(*((_QWORD *)this + 18) + 8LL) - 1.0);
        goto LABEL_22;
      case 55:
        v54 = *(unsigned int *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        goto LABEL_67;
      case 56:
        if ( (unsigned int)VAR::FTrue(*((VAR **)this + 18)) )
        {
          v304 = *((_QWORD *)this + 20) + **((unsigned int **)this + 19);
          *((_QWORD *)this + 19) = v304;
          *((_QWORD *)this + 26) = v304;
          v305 = *((_QWORD *)this + 18) + 24LL;
          *((_QWORD *)this + 18) = v305;
          *((_QWORD *)this + 25) = v305;
          goto LABEL_22;
        }
        v342 = *((_QWORD *)this + 18) + 24LL;
        goto LABEL_596;
      case 57:
        if ( (unsigned int)VAR::FTrue(*((VAR **)this + 18)) )
        {
          *((_QWORD *)this + 18) += 24LL;
          *((_QWORD *)this + 19) += 4LL;
        }
        else
        {
          v39 = *((_QWORD *)this + 20) + **((unsigned int **)this + 19);
          *((_QWORD *)this + 19) = v39;
          *((_QWORD *)this + 26) = v39;
          *((_QWORD *)this + 18) += 24LL;
          *((_QWORD *)this + 25) = *((_QWORD *)this + 18);
        }
        goto LABEL_22;
      case 58:
        v178 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v178 == 3 )
        {
          v179 = *((_DWORD *)v178 + 2);
          *((_DWORD *)v178 + 2) = -v179;
          v180 = *((_QWORD *)this + 18);
          if ( *(_DWORD *)(v180 + 8) == v179 )
          {
            *(_QWORD *)(v180 + 8) = COERCE_UNSIGNED_INT64((double)v179) ^ _xmm;
            **((_WORD **)this + 18) = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v178 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v178, v178, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        VAR::SetNumber(*((VAR **)this + 18), COERCE_DOUBLE(*(_QWORD *)(*((_QWORD *)this + 18) + 8LL) ^ _xmm));
        goto LABEL_22;
      case 59:
        v186 = CScriptRuntime::BitOp(this, 2);
        goto LABEL_267;
      case 60:
        v186 = CScriptRuntime::BitOp(this, 1);
        goto LABEL_267;
      case 61:
        v186 = CScriptRuntime::BitOp(this, 0);
        goto LABEL_267;
      case 62:
        TypeProto = ConvertToScalar(
                      *(struct CSession **)this,
                      *((struct VAR **)this + 18),
                      *((struct VAR **)this + 18),
                      3,
                      1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = ~*(_DWORD *)(*((_QWORD *)this + 18) + 8LL);
        goto LABEL_22;
      case 63:
        v301 = (VAR *)*((_QWORD *)this + 18);
        v302 = VAR::FTrue(v301);
        VAR::SetBool(v301, v302 == 0);
        goto LABEL_22;
      case 64:
        v299 = CScriptRuntime::TypeOf(this);
        goto LABEL_471;
      case 65:
        v299 = CScriptRuntime::Delete(this);
        goto LABEL_471;
      case 66:
        **((_WORD **)this + 18) = 0;
        goto LABEL_22;
      case 67:
        v303 = (struct VAR *)*((_QWORD *)this + 18);
        if ( ((*(_WORD *)v303 - 3) & 0xFFFD) == 0 )
          goto LABEL_22;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v303, v303, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        VAR::SetNumber(*((VAR **)this + 18), *(double *)(*((_QWORD *)this + 18) + 8LL));
        goto LABEL_22;
      case 68:
        v203 = *((_QWORD *)this + 18);
        v204 = (VAR *)(v203 + 24);
        if ( *(_WORD *)(v203 + 24) == 3 && *(_WORD *)v203 == 3 )
          goto LABEL_797;
        Value = CScriptRuntime::CompareEqual(this);
        goto LABEL_18;
      case 69:
        v199 = *((_QWORD *)this + 18);
        v200 = (VAR *)(v199 + 24);
        if ( *(_WORD *)(v199 + 24) == 3 && *(_WORD *)v199 == 3 )
          goto LABEL_516;
        v201 = CScriptRuntime::CompareEqual(this);
        goto LABEL_296;
      case 70:
        v13 = (double *)*((_QWORD *)this + 18);
        v14 = *((_WORD *)v13 + 12);
        if ( v14 == 3 && *(_WORD *)v13 == 3 )
        {
          v252 = *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) < *((_DWORD *)v13 + 2);
          v204 = (VAR *)(v13 + 3);
LABEL_363:
          VAR::SetBool(v204, v252);
          goto LABEL_19;
        }
        v456 = 0;
        v457 = 0;
        if ( v14 == 5 && *(_WORD *)v13 == 5 )
          goto LABEL_14;
        Value = VAR::GetValue(
                  (VAR *)(v13 + 3),
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v456,
                  (VARIANTARG *)v13 + 1,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v456 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue(
                  (VAR *)v13,
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v457,
                  (VARIANTARG *)v13,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v457 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v456) && (unsigned int)VAR::FBstr(v457) )
        {
          v15 = (unsigned int)StrComp(
                                *(struct CSession **)this,
                                *((unsigned __int16 **)v456 + 1),
                                *((unsigned __int16 **)v457 + 1)) >> 31;
          goto LABEL_17;
        }
        if ( !(unsigned int)ConvertToScalarCore(v456, (struct VAR *)(v13 + 3), 5) )
          goto LABEL_844;
        if ( !(unsigned int)ConvertToScalarCore(v457, (struct VAR *)v13, 5) )
          goto LABEL_140;
LABEL_14:
        if ( (unsigned int)FNan(v13[4]) || (unsigned int)FNan(v13[1]) )
          goto LABEL_269;
        v15 = 0;
        LOBYTE(v15) = v13[1] > v13[4];
        goto LABEL_17;
      case 71:
        v276 = (double *)*((_QWORD *)this + 18);
        v278 = *((_WORD *)v276 + 12);
        if ( v278 == 3 && *(_WORD *)v276 == 3 )
        {
          VAR::SetBool((VAR *)(v276 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) <= *((_DWORD *)v276 + 2));
LABEL_19:
          v17 = *((_QWORD *)this + 18);
LABEL_20:
          v18 = v17 + 24;
          goto LABEL_21;
        }
        v460 = 0;
        v461 = 0;
        if ( v278 == 5 && *(_WORD *)v276 == 5 )
          goto LABEL_556;
        Value = VAR::GetValue(
                  (VAR *)(v276 + 3),
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v460,
                  (VARIANTARG *)v276 + 1,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v460 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue(
                  (VAR *)v276,
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v461,
                  (VARIANTARG *)v276,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v461 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v460) && (unsigned int)VAR::FBstr(v461) )
        {
          v429 = StrComp(*(struct CSession **)this, *((unsigned __int16 **)v460 + 1), *((unsigned __int16 **)v461 + 1));
          VAR::SetBool((VAR *)(v276 + 3), v429 <= 0);
          Value = 0;
          goto LABEL_18;
        }
        if ( !(unsigned int)ConvertToScalarCore(v460, (struct VAR *)(v276 + 3), 5) )
        {
          v89 = (struct VAR *)(v276 + 3);
          goto LABEL_786;
        }
        if ( !(unsigned int)ConvertToScalarCore(v461, (struct VAR *)v276, 5) )
        {
          v89 = (struct VAR *)v276;
          goto LABEL_786;
        }
LABEL_556:
        if ( !(unsigned int)FNan(v276[4]) && !(unsigned int)FNan(v276[1]) )
        {
          VAR::SetBool((VAR *)(v276 + 3), v276[1] >= v276[4]);
          Value = 0;
          goto LABEL_18;
        }
        goto LABEL_798;
      case 72:
        v13 = (double *)*((_QWORD *)this + 18);
        v251 = *((_WORD *)v13 + 12);
        if ( v251 == 3 && *(_WORD *)v13 == 3 )
        {
          VAR::SetBool((VAR *)(v13 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) > *((_DWORD *)v13 + 2));
          goto LABEL_19;
        }
        v458 = 0;
        v459 = 0;
        if ( v251 == 5 && *(_WORD *)v13 == 5 )
          goto LABEL_536;
        Value = VAR::GetValue(
                  (VAR *)(v13 + 3),
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v458,
                  (VARIANTARG *)v13 + 1,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v458 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue(
                  (VAR *)v13,
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v459,
                  (VARIANTARG *)v13,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v459 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v458) && (unsigned int)VAR::FBstr(v459) )
        {
          v15 = (int)StrComp(
                       *(struct CSession **)this,
                       *((unsigned __int16 **)v458 + 1),
                       *((unsigned __int16 **)v459 + 1)) > 0;
          goto LABEL_17;
        }
        if ( !(unsigned int)ConvertToScalarCore(v458, (struct VAR *)(v13 + 3), 5) )
        {
LABEL_844:
          Value = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)(v13 + 3), 0, -1);
LABEL_18:
          TypeProto = Value;
          if ( Value >= 0 )
            goto LABEL_19;
          goto LABEL_36;
        }
        if ( (unsigned int)ConvertToScalarCore(v459, (struct VAR *)v13, 5) )
        {
LABEL_536:
          if ( !(unsigned int)FNan(v13[4]) && !(unsigned int)FNan(v13[1]) )
          {
            v15 = 0;
            LOBYTE(v15) = v13[4] > v13[1];
            goto LABEL_17;
          }
LABEL_269:
          v15 = 0;
LABEL_17:
          VAR::SetBool((VAR *)(v13 + 3), v15);
          Value = 0;
          goto LABEL_18;
        }
LABEL_140:
        v89 = (struct VAR *)v13;
        goto LABEL_786;
      case 73:
        v276 = (double *)*((_QWORD *)this + 18);
        v277 = *((_WORD *)v276 + 12);
        if ( v277 == 3 && *(_WORD *)v276 == 3 )
        {
          VAR::SetBool((VAR *)(v276 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) >= *((_DWORD *)v276 + 2));
          goto LABEL_19;
        }
        v462 = 0;
        v463 = 0;
        if ( v277 == 5 && *(_WORD *)v276 == 5 )
          goto LABEL_550;
        Value = VAR::GetValue(
                  (VAR *)(v276 + 3),
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v462,
                  (VARIANTARG *)v276 + 1,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v462 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue(
                  (VAR *)v276,
                  *(struct CSession **)this,
                  (struct IDispatch ***)&v463,
                  (VARIANTARG *)v276,
                  0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v463 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v462) && (unsigned int)VAR::FBstr(v463) )
        {
          v428 = StrComp(*(struct CSession **)this, *((unsigned __int16 **)v462 + 1), *((unsigned __int16 **)v463 + 1));
          VAR::SetBool((VAR *)(v276 + 3), v428 >= 0);
          Value = 0;
          goto LABEL_18;
        }
        if ( !(unsigned int)ConvertToScalarCore(v462, (struct VAR *)(v276 + 3), 5) )
        {
          v89 = (struct VAR *)(v276 + 3);
          goto LABEL_786;
        }
        if ( !(unsigned int)ConvertToScalarCore(v463, (struct VAR *)v276, 5) )
        {
          v89 = (struct VAR *)v276;
LABEL_786:
          Value = CSession::RecordHr(*(CSession **)this, -2146823287, v89, 0, -1);
          goto LABEL_18;
        }
LABEL_550:
        if ( (unsigned int)FNan(v276[4]) || (unsigned int)FNan(v276[1]) )
        {
LABEL_798:
          v323 = 0;
        }
        else
        {
          v323 = 0;
          LOBYTE(v323) = v276[4] >= v276[1];
        }
        VAR::SetBool((VAR *)(v276 + 3), v323);
        Value = 0;
        goto LABEL_18;
      case 74:
        v203 = *((_QWORD *)this + 18);
        v204 = (VAR *)(v203 + 24);
        if ( *(_WORD *)(v203 + 24) == 3 && *(_WORD *)v203 == 3 )
        {
LABEL_797:
          v252 = *(_DWORD *)(v203 + 32) == *(_DWORD *)(v203 + 8);
          goto LABEL_363;
        }
        Value = CScriptRuntime::CompareEquiv(this);
        goto LABEL_18;
      case 75:
        v199 = *((_QWORD *)this + 18);
        v200 = (VAR *)(v199 + 24);
        if ( *(_WORD *)(v199 + 24) != 3 || *(_WORD *)v199 != 3 )
        {
          v201 = CScriptRuntime::CompareEquiv(this);
LABEL_296:
          TypeProto = v201;
          if ( v201 >= 0 )
          {
            v202 = *((_QWORD *)this + 18) + 24LL;
            *((_QWORD *)this + 18) = v202;
            *(_WORD *)(v202 + 8) = ~*(_WORD *)(v202 + 8);
            goto LABEL_22;
          }
          goto LABEL_36;
        }
LABEL_516:
        VAR::SetBool(v200, *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) != *(_DWORD *)(v199 + 8));
        goto LABEL_19;
      case 76:
        v186 = CScriptRuntime::BitOp(this, 3);
        goto LABEL_267;
      case 77:
        v186 = CScriptRuntime::BitOp(this, 4);
        goto LABEL_267;
      case 78:
        v186 = CScriptRuntime::BitOp(this, 5);
        goto LABEL_267;
      case 79:
        v44 = *((_QWORD *)this + 18);
        if ( *(_WORD *)(v44 + 24) == 3 && *(_WORD *)v44 == 3 )
        {
          v284 = *(_DWORD *)(v44 + 32);
          *(_DWORD *)(v44 + 32) = v284 + *(_DWORD *)(v44 + 8);
          v285 = *((_QWORD *)this + 18);
          v286 = *(_DWORD *)(v285 + 8);
          if ( *(_DWORD *)(v285 + 32) < v286 == (unsigned int)v284 >> 31 )
            goto LABEL_63;
          *(double *)(v285 + 32) = (double)v284 + (double)v286;
          *(_WORD *)(*((_QWORD *)this + 18) + 24LL) = 5;
          *((_QWORD *)this + 18) += 24LL;
          goto LABEL_22;
        }
        if ( (unsigned int)FVtIn(*(unsigned __int16 *)(v44 + 24), 0x2083Cu)
          && (unsigned int)FVtIn(**((unsigned __int16 **)this + 18), 0x2083Cu) )
        {
          v45 = (struct VAR *)(*((_QWORD *)this + 18) + 24LL);
          if ( *(_WORD *)v45 != 5 )
            ConvertToScalarCore(v45, (struct VAR *)(*((_QWORD *)this + 18) + 24LL), 5);
          v46 = (struct VAR *)*((_QWORD *)this + 18);
          if ( *(_WORD *)v46 != 5 )
            ConvertToScalarCore(v46, *((struct VAR **)this + 18), 5);
          v47 = (double *)*((_QWORD *)this + 18);
          v48 = v47[4] + v47[1];
          v49 = (VAR *)(v47 + 3);
          goto LABEL_62;
        }
        v187 = (double *)*((_QWORD *)this + 18);
        v444 = 0;
        v441 = 0;
        IsAStringObj = VAR::IsAStringObj((VAR *)(v187 + 3));
        v189 = (VAR *)(v187 + 3);
        if ( IsAStringObj )
        {
          v190 = VAR::PvarCutHeap(v189);
          v444 = v190;
        }
        else
        {
          if ( VAR::GetValue(v189, *(struct CSession **)this, (struct IDispatch ***)&v444, (VARIANTARG *)v187 + 1, 0) < 0 )
            goto LABEL_63;
          v190 = v444;
        }
        if ( !v190 )
          goto LABEL_63;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)v187) )
        {
          v191 = VAR::PvarCutHeap((VAR *)v187);
          v441 = v191;
        }
        else
        {
          if ( VAR::GetValue((VAR *)v187, *(struct CSession **)this, (struct IDispatch ***)&v441, (VARIANTARG *)v187, 0) < 0 )
            goto LABEL_63;
          v191 = v441;
        }
        if ( !v191 )
          goto LABEL_63;
        if ( (unsigned int)VAR::FStr(v444) )
        {
          if ( !(unsigned int)VAR::FStr(v441)
            && ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v441, (VARIANTARG *)v187, 0) < 0 )
          {
            goto LABEL_63;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v441) )
          {
            if ( !(unsigned int)ConvertToScalarCore(v444, (struct VAR *)(v187 + 3), 5) )
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)(v187 + 3), 0, -1);
              *((_QWORD *)this + 18) += 24LL;
              goto LABEL_22;
            }
            if ( !(unsigned int)ConvertToScalarCore(v441, (struct VAR *)v187, 5) )
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)v187, 0, -1);
              *((_QWORD *)this + 18) += 24LL;
              goto LABEL_22;
            }
            v48 = v187[4] + v187[1];
            v49 = (VAR *)(v187 + 3);
LABEL_62:
            VAR::SetNumber(v49, v48);
LABEL_63:
            *((_QWORD *)this + 18) += 24LL;
            goto LABEL_22;
          }
          if ( ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v444, (VARIANTARG *)v187 + 1, 0) < 0 )
            goto LABEL_63;
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)(v187 + 3), v444, v441);
        *((_QWORD *)this + 18) += 24LL;
        goto LABEL_22;
      case 80:
        v167 = *((_QWORD *)this + 18);
        v168 = *(_WORD *)(v167 + 24);
        if ( v168 == 3 && *(_WORD *)v167 == 3 )
        {
          v169 = *(_DWORD *)(v167 + 32);
          *(_DWORD *)(v167 + 32) = v169 - *(_DWORD *)(v167 + 8);
          v170 = *((_QWORD *)this + 18);
          v171 = *(_DWORD *)(v170 + 8);
          if ( *(_DWORD *)(v170 + 32) < v169 != v171 > 0 )
          {
            *(double *)(v170 + 32) = (double)v169 - (double)v171;
            *(_WORD *)(*((_QWORD *)this + 18) + 24LL) = 5;
          }
        }
        else
        {
          if ( v168 != 5 )
          {
            TypeProto = ConvertToScalar(
                          *(struct CSession **)this,
                          (struct VAR *)(v167 + 24),
                          (struct VAR *)(v167 + 24),
                          5,
                          1);
            if ( TypeProto < 0 )
              goto LABEL_36;
          }
          v300 = (struct VAR *)*((_QWORD *)this + 18);
          if ( *(_WORD *)v300 != 5 )
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v300, v300, 5, 1);
            if ( TypeProto < 0 )
              goto LABEL_36;
          }
          VAR::SetNumber(
            (VAR *)(*((_QWORD *)this + 18) + 24LL),
            *(double *)(*((_QWORD *)this + 18) + 32LL) - *(double *)(*((_QWORD *)this + 18) + 8LL));
        }
        goto LABEL_19;
      case 81:
        v63 = *((_QWORD *)this + 18);
        v64 = *(_WORD *)(v63 + 24);
        if ( v64 != 3 || *(_WORD *)v63 != 3 )
        {
          if ( v64 == 5
            || (TypeProto = ConvertToScalar(
                              *(struct CSession **)this,
                              (struct VAR *)(v63 + 24),
                              (struct VAR *)(v63 + 24),
                              5,
                              1),
                TypeProto >= 0) )
          {
            v65 = (struct VAR *)*((_QWORD *)this + 18);
            if ( *(_WORD *)v65 == 5
              || (TypeProto = ConvertToScalar(*(struct CSession **)this, v65, v65, 5, 1), TypeProto >= 0) )
            {
              VAR::SetNumber(
                (VAR *)(*((_QWORD *)this + 18) + 24LL),
                *(double *)(*((_QWORD *)this + 18) + 32LL) * *(double *)(*((_QWORD *)this + 18) + 8LL));
              goto LABEL_19;
            }
          }
          goto LABEL_36;
        }
        v163 = *(_DWORD *)(v63 + 32);
        *(_DWORD *)(v63 + 32) = *(_DWORD *)(v63 + 8) * v163;
        v164 = *((_QWORD *)this + 18);
        v165 = *(_DWORD *)(v164 + 32);
        v166 = *(_DWORD *)(v164 + 8);
        if ( (v165 ^ v163 ^ v166) < 0 || v163 && v166 != v165 / v163 )
        {
          *(double *)(v164 + 32) = (double)v166 * (double)v163;
          *(_WORD *)(*((_QWORD *)this + 18) + 24LL) = 5;
        }
        goto LABEL_19;
      case 82:
        v291 = (struct VAR *)(*((_QWORD *)this + 18) + 24LL);
        if ( *(_WORD *)v291 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v291, v291, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v292 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v292 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v292, v292, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v293 = (double *)*((_QWORD *)this + 18);
        v294 = CScriptRuntime::SafeDivide(this, v293[4], v293[1]);
        VAR::SetNumber((VAR *)(v293 + 3), v294);
        goto LABEL_19;
      case 83:
        v287 = (struct VAR *)(*((_QWORD *)this + 18) + 24LL);
        if ( *(_WORD *)v287 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v287, v287, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v288 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v288 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v288, v288, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v289 = (double *)*((_QWORD *)this + 18);
        v290 = DblMod(v289[4], v289[1]);
        VAR::SetNumber((VAR *)(v289 + 3), v290);
        goto LABEL_19;
      case 84:
        v192 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        v193 = *(int *)(v8 + 5);
        *((_QWORD *)this + 19) = v8 + 9;
        v439 = (VAR *)(*((_QWORD *)this + 34) + 24 * v193);
        if ( !*((_QWORD *)this + 37) )
        {
          TypeProto = CScriptRuntime::EnsureActivation(this);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        TypeProto = CScriptBody::CreateEntryPoint(
                      **((CScriptBody ***)this + 7),
                      *(struct CSession **)this,
                      v192,
                      *(_DWORD *)(*((_QWORD *)this + 7) + 24LL),
                      &v440,
                      *((struct VAR **)this + 30),
                      *((struct VAR **)this + 11),
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj(v439, *(struct CSession **)this, v440);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v440 + 16LL))(v440);
        if ( TypeProto < 0 )
          goto LABEL_36;
        *((_QWORD *)this + 18) -= 24LL;
        v194 = v439;
        goto LABEL_290;
      case 85:
        v110 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        if ( (_DWORD)v110 )
        {
          v111 = (__int128 *)*((_QWORD *)this + 18);
          v112 = *v111;
          v113 = *((_QWORD *)v111 + 2);
          if ( (int)v110 < 0 )
            v114 = v4 + 24 * v110;
          else
            v114 = v3 + 24LL * -(int)v110;
          *(_OWORD *)v114 = v112;
          *(_QWORD *)(v114 + 16) = v113;
          goto LABEL_22;
        }
        if ( !*((_QWORD *)this + 13) )
        {
          TypeProto = CScriptRuntime::EnsureArguments(this);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v262 = *((_QWORD *)this + 18);
        v37 = *((_QWORD *)this + 14);
        *(_OWORD *)v37 = *(_OWORD *)v262;
        pRecInfo = *(IRecordInfo **)(v262 + 16);
        goto LABEL_43;
      case 86:
        v79 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        if ( (*((_BYTE *)this + 80) & 1) == 0 )
          goto LABEL_301;
        SYM::InitFromSymbol((SYM *)&v447, v79);
        TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 37) + 160LL))(
                      *((_QWORD *)this + 37),
                      &v447,
                      &v508);
        if ( (unsigned int)FErr(TypeProto) )
          goto LABEL_36;
        if ( (unsigned int)FYes(TypeProto) )
        {
          (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, int))(**((_QWORD **)this + 37) + 264LL))(
            *((_QWORD *)this + 37),
            &v447,
            *((_QWORD *)this + 18),
            0,
            pvarg);
          goto LABEL_22;
        }
LABEL_301:
        v205 = 16 * ((*((_DWORD *)this + 20) & 1) == 0);
        v206 = *((_QWORD *)this + 37);
        v207 = *(__int64 (__fastcall **)(__int64, struct SYM *, _QWORD, __int64, _QWORD))(*(_QWORD *)v206 + 128LL);
        v208 = *((_QWORD *)this + 18);
        v209 = SYM::InitFromSymbol((SYM *)&v447, v79);
        TypeProto = v207(v206, v209, v205, v208, 0);
        if ( TypeProto >= 0 )
          goto LABEL_22;
        v4 = v470;
        goto LABEL_36;
      case 87:
        v115 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v116 = VAR::PvarCutHeap(*((VAR **)this + 18));
        v117 = *(unsigned __int16 *)v116;
        if ( v117 != 9 && (v263 = v117 - 129) != 0 && (v264 = v263 - 5) != 0 && (v265 = v264 - 1) != 0 && v265 != 9
          || (v118 = (struct IDispatch *)*((_QWORD *)v116 + 1)) == 0 )
        {
          TypeProto = CSession::RecordHr(*(CSession **)this, -2146823281, *((struct VAR **)this + 18), 0, 0);
          goto LABEL_36;
        }
        v119 = *((_QWORD *)this + 18);
        if ( *(_WORD *)(v119 + 24) != 128
          || (v266 = *(_QWORD *)(v119 + 32), *(_WORD *)v266 != 129)
          || (v267 = *(struct NameTbl **)(v266 + 8)) == 0 )
        {
LABEL_181:
          TypeProto = CSession::RecordHr(*(CSession **)this, -2146828237, 0, 0, -1);
          goto LABEL_36;
        }
        Value = COleScript::RegisterEvtHandler(*((COleScript **)this + 1), v118, v115, v267);
        goto LABEL_18;
      case 88:
        v66 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        SYM::InitFromSymbol((SYM *)&v447, v66);
        TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 37) + 160LL))(
                      *((_QWORD *)this + 37),
                      &v447,
                      &v508);
        if ( (unsigned int)FErr(TypeProto) )
          goto LABEL_36;
        if ( !(unsigned int)FYes(TypeProto) || (v508 & 3) != 0 )
        {
          TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 37)
                                                                                            + 128LL))(
                        *((_QWORD *)this + 37),
                        &v447,
                        16 * (unsigned int)((*((_DWORD *)this + 20) & 1) == 0),
                        0,
                        0);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        goto LABEL_22;
      case 89:
        v306 = v506;
        if ( v506 )
        {
          v307 = *((_QWORD *)this + 18);
          *(_OWORD *)v506 = *(_OWORD *)v307;
          *((_QWORD *)v306 + 2) = *(_QWORD *)(v307 + 16);
        }
        goto LABEL_514;
      case 91:
        goto LABEL_63;
      case 92:
        v362 = (struct VAR *)*((_QWORD *)this + 29);
        goto LABEL_637;
      case 93:
        if ( (unsigned int)VAR::IsIDispatch(*((VAR **)this + 18)) )
          goto LABEL_307;
        VarVal = ConvertToObject(*(struct CSession **)this, *((struct VAR **)this + 18), (struct VAR *)&v449, 0);
        TypeProto = VarVal;
        if ( VarVal == 1 )
        {
          v28 = 0;
          v29 = (struct VAR *)*((_QWORD *)this + 18);
          v30 = -2146827864;
          goto LABEL_34;
        }
        if ( VarVal >= 0 )
        {
          *(VARIANTARG *)*((_QWORD *)this + 18) = v449;
LABEL_307:
          *(_QWORD *)(*((_QWORD *)this + 18) + 16LL) = *((_QWORD *)this + 30);
          *((_QWORD *)this + 30) = *((_QWORD *)this + 18);
          goto LABEL_22;
        }
        v28 = 0;
        v29 = (struct VAR *)*((_QWORD *)this + 18);
        goto LABEL_33;
      case 94:
      case 95:
        v343 = (VAR *)*((_QWORD *)this + 18);
        if ( *((VAR **)this + 30) != v343
          || !(unsigned int)VAR::IsIDispatch(v343) && **((_WORD **)this + 18)
          || *((_QWORD *)this + 30) == *((_QWORD *)this + 31) )
        {
          goto LABEL_848;
        }
        v344 = *((_QWORD *)this + 18);
        *((_QWORD *)this + 30) = *(_QWORD *)(v344 + 16);
        v18 = v344 + 24;
        goto LABEL_21;
      case 96:
        v345 = 1;
        goto LABEL_614;
      case 97:
        v345 = 0;
LABEL_614:
        v299 = CScriptRuntime::ForIn(this, v345);
        goto LABEL_471;
      case 98:
        goto LABEL_233;
      case 101:
        v281 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v281;
        *(_OWORD *)v281 = *(_OWORD *)(v281 + 48);
        *(_QWORD *)(v281 + 16) = *(_QWORD *)(v281 + 64);
        TypeProto = CScriptRuntime::CompareEquiv(this);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v282 = *((_QWORD *)this + 18);
        if ( *(_WORD *)(v282 + 32) )
        {
          v283 = v282 + 72;
          *((_QWORD *)this + 18) = v283;
          *((_QWORD *)this + 25) = v283;
          v125 = **((unsigned int **)this + 19);
          goto LABEL_191;
        }
        v342 = v282 + 48;
LABEL_596:
        *((_QWORD *)this + 18) = v342;
        *((_QWORD *)this + 19) += 4LL;
        goto LABEL_22;
      case 102:
        v364 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v364;
        *v364 = 0;
        if ( *(_DWORD *)(*(_QWORD *)this + 1232LL)
          || VariantCopyInd(*((VARIANT **)this + 18), (const VARIANTARG *)(*(_QWORD *)this + 1208LL)) < 0 )
        {
          goto LABEL_643;
        }
        if ( (int)VAR::Import(*((VARIANTARG **)this + 18), *(struct CSession **)this) < 0 )
        {
          VariantClear(*((VARIANTARG **)this + 18));
LABEL_643:
          TypeProto = CScriptRuntime::ConstructErrorObject(this, *((struct VAR **)this + 18));
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        goto LABEL_40;
      case 103:
        TypeProto = CScriptRuntime::InstOf(this);
        if ( TypeProto < 0 )
          goto LABEL_36;
        goto LABEL_22;
      case 104:
        TypeProto = CScriptRuntime::In(this);
        if ( TypeProto < 0 )
          goto LABEL_36;
        goto LABEL_22;
      case 105:
        VariantClear((VARIANTARG *)(*(_QWORD *)this + 1208LL));
        VAR::GetStdVar(*((VAR **)this + 18), (struct tagVARIANT *)(*(_QWORD *)this + 1208LL));
        TypeProto = CSession::RecordHr(*(CSession **)this, -2146823266, 0, 0, -1);
        if ( (int)CSession::CanHandleException(*(CSession **)this) >= 0 )
        {
          *((_QWORD *)this + 18) += 24LL;
LABEL_37:
          v32 = *((_QWORD *)this + 23);
          if ( v32 == *((_QWORD *)this + 24) )
          {
            TypeProto = -2147352318;
            goto LABEL_850;
          }
          if ( *(_WORD *)v32 != 141 )
            goto LABEL_9;
          v33 = *((_DWORD *)this + 76);
          *((_DWORD *)this + 76) = v33 | 4;
          CScriptRuntime::SetNextStatement(this, *(_DWORD *)(v32 + 8));
          *((_DWORD *)this + 76) = ((int)((v33 & 0xFFFFFFFC) << 29) >> 29)
                                 ^ (*((_DWORD *)this + 76)
                                  ^ ((int)((v33 & 0xFFFFFFFC) << 29) >> 29))
                                 & 0xFFFFFFFB;
LABEL_40:
          TypeProto = 0;
          goto LABEL_22;
        }
        CScriptRuntime::RestoreExcepInfoFromThrownValue(this, *((struct VAR **)this + 18));
        *((_QWORD *)this + 18) += 24LL;
        TypeProto = -2040119292;
        goto LABEL_36;
      case 106:
        *((_QWORD *)this + 19) = v8 + 5;
        goto LABEL_627;
      case 107:
LABEL_627:
        v352 = *((_QWORD *)this + 18);
        *((_QWORD *)this + 23) = *(_QWORD *)(v352 + 16);
        v18 = v352 + 24;
        goto LABEL_21;
      case 108:
        v349 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v349;
        *v349 = 141;
        v350 = (int *)*((_QWORD *)this + 19);
        v351 = *v350;
        *((_QWORD *)this + 19) = v350 + 1;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = v351;
        *(_QWORD *)(*((_QWORD *)this + 18) + 16LL) = *((_QWORD *)this + 23);
        *((_QWORD *)this + 23) = *((_QWORD *)this + 18);
        goto LABEL_22;
      case 109:
        v356 = *((_QWORD *)this + 18);
        if ( *(_WORD *)v356 == 142 )
        {
          *((_QWORD *)this + 25) = v356;
          v357 = *((_QWORD *)this + 20) + *(int *)(v356 + 8);
          *((_QWORD *)this + 19) = v357;
          *((_QWORD *)this + 26) = v357;
        }
        v17 = v356 + 24;
        *((_QWORD *)this + 18) = v356 + 24;
        goto LABEL_20;
      case 110:
        v313 = *((_QWORD *)this + 18);
        if ( *(_WORD *)v313 == 142 )
        {
          v17 = v313 + 24;
          *((_QWORD *)this + 18) = v17;
          goto LABEL_20;
        }
        v314 = *(int *)(v313 + 8);
        *(_WORD *)v313 = 142;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = *((_DWORD *)this + 38) - *((_DWORD *)this + 40);
        v54 = v314;
LABEL_67:
        *((_QWORD *)this + 25) = *((_QWORD *)this + 18);
        v55 = v54 + *((_QWORD *)this + 20);
        *((_QWORD *)this + 19) = v55;
        *((_QWORD *)this + 26) = v55;
        goto LABEL_22;
      case 111:
        v359 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v359;
        *v359 = 0;
        v360 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v360;
        *v360 = 141;
        v361 = (_DWORD *)*((_QWORD *)this + 19);
        v196 = *v361;
        v197 = (char *)(v361 + 1);
LABEL_292:
        *((_QWORD *)this + 19) = v197;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = v196;
        goto LABEL_22;
      case 112:
        v362 = v506;
LABEL_637:
        if ( v362 )
        {
          v363 = *((_QWORD *)this + 18);
          *(_OWORD *)v362 = *(_OWORD *)v363;
          *((_QWORD *)v362 + 2) = *(_QWORD *)(v363 + 16);
        }
        goto LABEL_19;
      case 113:
LABEL_514:
        TypeProto = 0;
        goto LABEL_850;
      case 114:
        VariantCopyInd((VARIANT *)(*((_QWORD *)this + 18) + 24LL), (const VARIANTARG *)(*(_QWORD *)this + 1208LL));
        if ( (int)CSession::CanHandleException(*(CSession **)this) < 0 )
        {
          CSession::RecordHr(*(CSession **)this, -2146823266, 0, 0, -1);
          CScriptRuntime::RestoreExcepInfoFromThrownValue(this, (struct VAR *)(*((_QWORD *)this + 18) + 24LL));
          TypeProto = -2040119292;
          if ( (unsigned int)CSession::FReportError(*(CSession **)this) )
          {
            if ( !(unsigned int)CScriptRuntime::FResumeFromRuntimeError(this, &TypeProto, 0) && TypeProto < 0 )
              TypeProto = CSession::ReportError(*(CSession **)this, TypeProto);
          }
        }
        goto LABEL_22;
      case 115:
        v409 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v409;
        v410 = (VARIANTARG *)(*(_QWORD *)this + 1208LL);
        if ( *(_WORD *)v409 != v410->vt || *(_DWORD *)(v409 + 8) != *(_DWORD *)(*(_QWORD *)this + 1216LL) )
        {
          VariantClear(v410);
          TypeProto = VariantCopyInd((VARIANT *)(*(_QWORD *)this + 1208LL), *((const VARIANTARG **)this + 18));
          if ( TypeProto < 0 )
            VariantInit((VARIANTARG *)(*(_QWORD *)this + 1208LL));
          CSession::RecordHr(*(CSession **)this, -2146823266, 0, 0, -1);
          CScriptRuntime::RestoreExcepInfoFromThrownValue(this, *((struct VAR **)this + 18));
        }
        VariantClear(*((VARIANTARG **)this + 18));
        TypeProto = -2040119292;
        goto LABEL_37;
      case 116:
        v122 = (double *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        if ( *(_WORD *)v122 == 3 )
        {
          v123 = *((_DWORD *)v122 + 2);
          *((_DWORD *)v122 + 2) = v123 + 1;
          if ( v123 + 1 <= v123 )
          {
            v122[1] = (double)v123 + 1.0;
            *(_WORD *)v122 = 5;
          }
        }
        else
        {
          if ( *(_WORD *)v122 != 5 )
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v122, (struct VAR *)v122, 5, 1);
            if ( TypeProto < 0 )
              goto LABEL_36;
          }
          VAR::SetNumber((VAR *)v122, v122[1] + 1.0);
        }
        v124 = (unsigned int *)*((_QWORD *)this + 19);
        v125 = *v124;
        *((_QWORD *)this + 19) = v124 + 1;
        *((_QWORD *)this + 25) = *((_QWORD *)this + 18);
LABEL_191:
        v126 = *((_QWORD *)this + 20) + v125;
        *((_QWORD *)this + 19) = v126;
        *((_QWORD *)this + 26) = v126;
        goto LABEL_22;
      case 117:
        v365 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v365 *= 3;
        *(_WORD *)(v3 + 8 * v365) = 11;
        *(_WORD *)(v3 + 8 * v365 + 8) = -1;
        goto LABEL_22;
      case 118:
        v358 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v358 *= 3;
        *(_WORD *)(v3 + 8 * v358) = 11;
        *(_WORD *)(v3 + 8 * v358 + 8) = 0;
        goto LABEL_22;
      case 119:
        v348 = 3LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)(v3 + 8 * v348) = 1;
        goto LABEL_22;
      case 120:
        v238 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v239 = 3 * v238;
        *(_WORD *)(v3 + 8 * v239) = 3;
        v240 = (char *)*((_QWORD *)this + 19);
        LODWORD(v238) = *v240;
        *((_QWORD *)this + 19) = v240 + 1;
        *(_DWORD *)(v3 + 8 * v239 + 8) = v238;
        goto LABEL_22;
      case 121:
        v380 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v381 = 3 * v380;
        *(_WORD *)(v3 + 8 * v381) = 3;
        v382 = (_DWORD *)*((_QWORD *)this + 19);
        LODWORD(v380) = *v382;
        *((_QWORD *)this + 19) = v382 + 1;
        *(_DWORD *)(v3 + 8 * v381 + 8) = v380;
        goto LABEL_22;
      case 122:
        v411 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v411 *= 3;
        *(_WORD *)(v3 + 8 * v411) = 5;
        v412 = (__int64 *)*((_QWORD *)this + 19);
        v413 = *v412;
        *((_QWORD *)this + 19) = v412 + 1;
        *(_QWORD *)(v3 + 8 * v411 + 8) = v413;
        goto LABEL_22;
      case 123:
        v353 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v354 = *(unsigned int *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 7;
        v355 = CScriptRuntime::GetGcAlloc(this);
        v439 = GcAlloc::PvarAlloc(v355);
        if ( v439 )
        {
          v430 = 3 * v353;
          *(_WORD *)(v3 + 8 * v430) = 128;
          *(_QWORD *)(v3 + 8 * v430 + 8) = v439;
          v130 = v354;
          goto LABEL_194;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 124:
        v414 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v414 *= 3;
        *(_WORD *)(v4 + 8 * v414) = 11;
        *(_WORD *)(v4 + 8 * v414 + 8) = -1;
        goto LABEL_22;
      case 125:
        v415 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v415 *= 3;
        *(_WORD *)(v4 + 8 * v415) = 11;
        *(_WORD *)(v4 + 8 * v415 + 8) = 0;
        goto LABEL_22;
      case 126:
        v416 = 3LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)(v4 + 8 * v416) = 1;
        goto LABEL_22;
      case 127:
        v417 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v418 = 3 * v417;
        *(_WORD *)(v4 + 8 * v418) = 3;
        v419 = (char *)*((_QWORD *)this + 19);
        LODWORD(v417) = *v419;
        *((_QWORD *)this + 19) = v419 + 1;
        *(_DWORD *)(v4 + 8 * v418 + 8) = v417;
        goto LABEL_22;
      case 128:
        v420 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v421 = 3 * v420;
        *(_WORD *)(v4 + 8 * v421) = 3;
        v422 = (_DWORD *)*((_QWORD *)this + 19);
        LODWORD(v420) = *v422;
        *((_QWORD *)this + 19) = v422 + 1;
        *(_DWORD *)(v4 + 8 * v421 + 8) = v420;
        goto LABEL_22;
      case 129:
        v423 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v423 *= 3;
        *(_WORD *)(v4 + 8 * v423) = 5;
        v424 = (__int64 *)*((_QWORD *)this + 19);
        v425 = *v424;
        *((_QWORD *)this + 19) = v424 + 1;
        *(_QWORD *)(v4 + 8 * v423 + 8) = v425;
        goto LABEL_22;
      case 130:
        v383 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v384 = *(unsigned int *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 7;
        v385 = CScriptRuntime::GetGcAlloc(this);
        v439 = GcAlloc::PvarAlloc(v385);
        if ( v439 )
        {
          v434 = 3 * v383;
          *(_WORD *)(v4 + 8 * v434) = 128;
          *(_QWORD *)(v4 + 8 * v434 + 8) = v439;
          v130 = v384;
          goto LABEL_194;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 131:
        v105 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v106 = *(_DWORD *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 7;
        v107 = 3 * v105;
        if ( *(_WORD *)(v3 + 8 * v107) != 3 )
        {
          v466 = *(VARIANTARG *)(v3 + 8 * v107);
          v477 = *(unsigned int **)this;
          v476 = &v466;
          v478 = *((_QWORD *)v477 + 122);
          *((_QWORD *)v477 + 122) = &v476;
          v474 = *(unsigned int **)this;
          v473 = &v472;
          v475 = *((_QWORD *)v474 + 122);
          *((_QWORD *)v474 + 122) = &v473;
          v472.vt = 3;
          v472.lVal = v106;
          v452 = 0;
          v453 = 0;
          v108 = VAR::GetValue((VAR *)&v466, *(struct CSession **)this, (struct IDispatch ***)&v452, &v466, 0x2000u);
          if ( v108 >= 0 )
          {
            if ( v452 )
            {
              v108 = VAR::GetValue((VAR *)&v472, *(struct CSession **)this, (struct IDispatch ***)&v453, &v472, 0x2000u);
              if ( v108 >= 0 )
              {
                if ( v453 )
                {
                  if ( (unsigned int)VAR::FBstr(v452) && (unsigned int)VAR::FBstr(v453) )
                  {
                    v109 = (unsigned int)StrComp(
                                           *(struct CSession **)this,
                                           *((unsigned __int16 **)v452 + 1),
                                           *((unsigned __int16 **)v453 + 1)) >> 31;
                  }
                  else
                  {
                    if ( !(unsigned int)ConvertToScalarCore(v452, (struct VAR *)&v466, 5) )
                    {
                      v108 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v466, 0, -1);
                      goto LABEL_173;
                    }
                    if ( !(unsigned int)ConvertToScalarCore(v453, (struct VAR *)&v472, 5) )
                    {
                      v108 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v472, 0, -1);
                      goto LABEL_173;
                    }
                    if ( (unsigned int)FNan(v466.dblVal) || (unsigned int)FNan(v472.dblVal) )
                    {
                      v109 = 0;
                    }
                    else
                    {
                      v109 = 0;
                      LOBYTE(v109) = v472.dblVal > v466.dblVal;
                    }
                  }
                  VAR::SetBool((VAR *)&v466, v109);
                  v108 = 0;
                }
                else
                {
                  v108 = -2146828281;
                }
              }
            }
            else
            {
              v108 = -2146828281;
            }
          }
LABEL_173:
          TypeProto = v108;
          if ( v108 < 0 )
          {
            GCRootStack::Pop((GCRootStack *)(v474 + 236));
            GCRootStack::Pop((GCRootStack *)(v477 + 236));
            goto LABEL_36;
          }
          v97 = v466.iVal == 0xFFFF;
          GCRootStack::Pop((GCRootStack *)(v474 + 236));
          v98 = v477;
LABEL_155:
          GCRootStack::Pop((GCRootStack *)(v98 + 236));
          goto LABEL_156;
        }
        v97 = *(_DWORD *)(v3 + 8 * v107 + 8) < v106;
        goto LABEL_156;
      case 132:
        v74 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v439 = v74;
        v75 = 3LL * *(__int16 *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 5;
        v76 = 3LL * *(__int16 *)(v8 + 5);
        *((_QWORD *)this + 19) = v8 + 7;
        if ( *(_WORD *)(v3 + 8 * v75) == 3 && *(_WORD *)(v3 + 8 * v76) == 3 )
        {
          v138 = *(_DWORD *)(v3 + 8 * v75 + 8);
          v139 = *(_DWORD *)(v3 + 8 * v76 + 8);
          *(_WORD *)v74 = 3;
          if ( v139 + v138 < v139 == (unsigned int)v138 >> 31 )
          {
            *((_DWORD *)v439 + 2) = v139 + v138;
          }
          else
          {
            *((double *)v439 + 1) = (double)v139 + (double)v138;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( (unsigned int)FVtIn(*(unsigned __int16 *)(v3 + 8 * v75), 0x2083Cu)
          && (unsigned int)FVtIn(*(unsigned __int16 *)(v3 + 8 * v76), 0x2083Cu) )
        {
          v487 = *(__m128i *)(v3 + 8 * v75);
          v488 = *(_QWORD *)(v3 + 8 * v75 + 16);
          v485 = *(_OWORD *)(v3 + 8 * v76);
          v486 = *(_QWORD *)(v3 + 8 * v76 + 16);
          if ( (unsigned __int16)_mm_cvtsi128_si32(v487) != 5 )
            ConvertToScalarCore((struct VAR *)&v487, (struct VAR *)&v487, 5);
          if ( (_WORD)v485 != 5 )
            ConvertToScalarCore((struct VAR *)&v485, (struct VAR *)&v485, 5);
          VAR::SetNumber(v439, *((double *)&v485 + 1) + *(double *)&v487.m128i_i64[1]);
          goto LABEL_22;
        }
        v467 = *(VARIANTARG *)(v3 + 8 * v76);
        v464 = *(VARIANTARG *)(v3 + 8 * v75);
        v493 = *(unsigned int **)this;
        v492 = &v467;
        v494 = *((_QWORD *)v493 + 122);
        *((_QWORD *)v493 + 122) = &v492;
        v490 = *(unsigned int **)this;
        v489 = &v464;
        v491 = *((_QWORD *)v490 + 122);
        *((_QWORD *)v490 + 122) = &v489;
        v445 = 0;
        v442 = 0;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v464) )
        {
          v77 = VAR::PvarCutHeap((VAR *)&v464);
          v445 = v77;
        }
        else
        {
          if ( VAR::GetValue((VAR *)&v464, *(struct CSession **)this, (struct IDispatch ***)&v445, &v464, 0) < 0 )
            goto LABEL_612;
          v77 = v445;
        }
        if ( !v77 )
          goto LABEL_612;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v467) )
        {
          v78 = VAR::PvarCutHeap((VAR *)&v467);
          v442 = v78;
        }
        else
        {
          if ( VAR::GetValue((VAR *)&v467, *(struct CSession **)this, (struct IDispatch ***)&v442, &v467, 0) < 0 )
            goto LABEL_612;
          v78 = v442;
        }
        if ( !v78 )
          goto LABEL_612;
        if ( (unsigned int)VAR::FStr(v445) )
        {
          if ( !(unsigned int)VAR::FStr(v442)
            && ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v442, &v467, 0) < 0 )
          {
            goto LABEL_612;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v442) )
          {
            if ( (unsigned int)ConvertToScalarCore(v445, (struct VAR *)&v464, 5) )
            {
              if ( (unsigned int)ConvertToScalarCore(v442, (struct VAR *)&v467, 5) )
                VAR::SetNumber((VAR *)&v464, v467.dblVal + v464.dblVal);
              else
                CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v467, 0, -1);
            }
            else
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v464, 0, -1);
            }
            goto LABEL_612;
          }
          if ( ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v445, &v464, 0) < 0 )
          {
LABEL_612:
            *(VARIANTARG *)v439 = v464;
            GCRootStack::Pop((GCRootStack *)(v490 + 236));
            GCRootStack::Pop((GCRootStack *)(v493 + 236));
            goto LABEL_22;
          }
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)&v464, v445, v442);
        goto LABEL_612;
      case 133:
        v92 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v93 = *(__int16 *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 5;
        v94 = 3 * v92;
        if ( *(_WORD *)(v3 + 8 * v94) == 3 && *(_WORD *)(v3 + 24 * v93) == 3 )
        {
          v97 = *(_DWORD *)(v3 + 8 * v94 + 8) < *(_DWORD *)(v3 + 24 * v93 + 8);
LABEL_156:
          v99 = (unsigned int *)*((_QWORD *)this + 19);
          if ( v97 )
          {
            *((_QWORD *)this + 18) = *((_QWORD *)this + 18);
            *((_QWORD *)this + 19) = v99 + 1;
          }
          else
          {
            v100 = *((_QWORD *)this + 20) + *v99;
            *((_QWORD *)this + 19) = v100;
            *((_QWORD *)this + 26) = v100;
            v101 = *((_QWORD *)this + 18);
            *((_QWORD *)this + 18) = v101;
            *((_QWORD *)this + 25) = v101;
          }
          goto LABEL_22;
        }
        v465 = *(VARIANTARG *)(v3 + 8 * v94);
        v469 = *(VARIANTARG *)(v3 + 24 * v93);
        v483 = *(unsigned int **)this;
        v482 = &v465;
        v484 = *((_QWORD *)v483 + 122);
        *((_QWORD *)v483 + 122) = &v482;
        v480 = *(unsigned int **)this;
        v479 = &v469;
        v481 = *((_QWORD *)v480 + 122);
        *((_QWORD *)v480 + 122) = &v479;
        v454 = 0;
        v455 = 0;
        if ( v465.vt == 5 && v469.vt == 5 )
          goto LABEL_149;
        v96 = VAR::GetValue((VAR *)&v465, *(struct CSession **)this, (struct IDispatch ***)&v454, &v465, 0x2000u);
        if ( v96 < 0 )
          goto LABEL_153;
        if ( !v454 )
        {
          v96 = -2146828281;
          goto LABEL_153;
        }
        v96 = VAR::GetValue((VAR *)&v469, *(struct CSession **)this, (struct IDispatch ***)&v455, &v469, 0x2000u);
        if ( v96 < 0 )
          goto LABEL_153;
        if ( !v455 )
        {
          v96 = -2146828281;
          goto LABEL_153;
        }
        if ( (unsigned int)VAR::FBstr(v454) && (unsigned int)VAR::FBstr(v455) )
        {
          v95 = (unsigned int)StrComp(
                                *(struct CSession **)this,
                                *((unsigned __int16 **)v454 + 1),
                                *((unsigned __int16 **)v455 + 1)) >> 31;
        }
        else
        {
          if ( !(unsigned int)ConvertToScalarCore(v454, (struct VAR *)&v465, 5) )
          {
            v96 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v465, 0, -1);
            goto LABEL_153;
          }
          if ( !(unsigned int)ConvertToScalarCore(v455, (struct VAR *)&v469, 5) )
          {
            v96 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v469, 0, -1);
            goto LABEL_153;
          }
LABEL_149:
          if ( (unsigned int)FNan(v465.dblVal) || (unsigned int)FNan(v469.dblVal) )
          {
            v95 = 0;
          }
          else
          {
            v95 = 0;
            LOBYTE(v95) = v469.dblVal > v465.dblVal;
          }
        }
        VAR::SetBool((VAR *)&v465, v95);
        v96 = 0;
LABEL_153:
        TypeProto = v96;
        if ( v96 < 0 )
        {
          GCRootStack::Pop((GCRootStack *)(v480 + 236));
          GCRootStack::Pop((GCRootStack *)(v483 + 236));
          goto LABEL_36;
        }
        v97 = v465.iVal == 0xFFFF;
        GCRootStack::Pop((GCRootStack *)(v480 + 236));
        v98 = v483;
        goto LABEL_155;
      case 134:
        v228 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v228;
        v229 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v439 = v229;
        *(_OWORD *)v228 = *(_OWORD *)v229;
        *(_QWORD *)(v228 + 16) = *((_QWORD *)v229 + 2);
        v230 = (double *)v439;
        goto LABEL_328;
      case 135:
        v366 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v366;
        v367 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v439 = v367;
        *(_OWORD *)v366 = *(_OWORD *)v367;
        *(_QWORD *)(v366 + 16) = *((_QWORD *)v367 + 2);
        v368 = v439;
        goto LABEL_658;
      case 136:
        v230 = (double *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v439 = (VAR *)v230;
LABEL_328:
        if ( *(_WORD *)v230 == 3 )
        {
          v231 = *((_DWORD *)v230 + 2);
          *((_DWORD *)v230 + 2) = v231 + 1;
          if ( *((_DWORD *)v439 + 2) < v231 )
          {
            *((double *)v439 + 1) = (double)v231 + 1.0;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v230 == 5 )
          goto LABEL_381;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v230, (struct VAR *)v230, 5, 1);
        if ( TypeProto >= 0 )
        {
          v230 = (double *)v439;
          goto LABEL_381;
        }
        goto LABEL_36;
      case 137:
        v368 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v439 = v368;
LABEL_658:
        if ( *(_WORD *)v368 == 3 )
        {
          v369 = *((_DWORD *)v368 + 2);
          *((_DWORD *)v368 + 2) = v369 - 1;
          if ( *((_DWORD *)v439 + 2) > v369 )
          {
            *((double *)v439 + 1) = (double)v369 - 1.0;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v368 == 5 )
          goto LABEL_728;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v368, v368, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v368 = v439;
LABEL_728:
        VAR::SetNumber(v368, *((double *)v368 + 1) - 1.0);
        goto LABEL_22;
      case 138:
        v57 = (char)*v10;
        v58 = (__int16 *)(v8 + 2);
        goto LABEL_70;
      case 139:
        v57 = *(_DWORD *)v10;
        v58 = (__int16 *)(v8 + 5);
LABEL_70:
        *((_QWORD *)this + 19) = v58;
        v59 = (VAR *)(v3 + 24LL * *v58);
        *((_QWORD *)this + 19) = v58 + 1;
        v439 = v59;
        if ( *(_WORD *)v59 == 3 )
        {
          v260 = *((_DWORD *)v59 + 2);
          *((_DWORD *)v59 + 2) = v260 + v57;
          if ( *((_DWORD *)v439 + 2) < v57 != (unsigned int)v260 >> 31 )
          {
            *((double *)v439 + 1) = (double)v260 + (double)v57;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( (unsigned int)FVtIn(*(unsigned __int16 *)v59, 0x2083Cu) )
        {
          v261 = (double *)v439;
          if ( *(_WORD *)v439 != 5 )
          {
            ConvertToScalarCore(v439, v439, 5);
            v261 = (double *)v439;
          }
          VAR::SetNumber((VAR *)v261, (double)v57 + v261[1]);
          goto LABEL_22;
        }
        v496 = *(unsigned int **)this;
        v495 = &v468;
        v497 = *((_QWORD *)v496 + 122);
        *((_QWORD *)v496 + 122) = &v495;
        v468.vt = 3;
        v468.lVal = v57;
        v60 = (double *)v439;
        v446 = 0;
        v443 = 0;
        if ( (unsigned int)VAR::IsAStringObj(v439) )
        {
          v61 = VAR::PvarCutHeap((VAR *)v60);
          v446 = v61;
        }
        else
        {
          if ( VAR::GetValue((VAR *)v60, *(struct CSession **)this, (struct IDispatch ***)&v446, (VARIANTARG *)v60, 0) < 0 )
            goto LABEL_219;
          v61 = v446;
        }
        if ( !v61 )
          goto LABEL_219;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v468) )
        {
          v62 = VAR::PvarCutHeap((VAR *)&v468);
          v443 = v62;
        }
        else
        {
          if ( VAR::GetValue((VAR *)&v468, *(struct CSession **)this, (struct IDispatch ***)&v443, &v468, 0) < 0 )
            goto LABEL_219;
          v62 = v443;
        }
        if ( !v62 )
          goto LABEL_219;
        if ( (unsigned int)VAR::FStr(v446) )
        {
          if ( !(unsigned int)VAR::FStr(v443)
            && ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v443, &v468, 0) < 0 )
          {
            goto LABEL_219;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v443) )
          {
            if ( (unsigned int)ConvertToScalarCore(v446, (struct VAR *)v60, 5) )
            {
              if ( (unsigned int)ConvertToScalarCore(v443, (struct VAR *)&v468, 5) )
                VAR::SetNumber((VAR *)v60, v468.dblVal + v60[1]);
              else
                CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v468, 0, -1);
            }
            else
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)v60, 0, -1);
            }
            goto LABEL_219;
          }
          if ( ConvertToString(*(struct CSession **)this, (struct IDispatch ***)&v446, (VARIANTARG *)v60, 0) < 0 )
          {
LABEL_219:
            GCRootStack::Pop((GCRootStack *)(v496 + 236));
            goto LABEL_22;
          }
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)v60, v446, v443);
        goto LABEL_219;
      case 140:
        v386 = (char)*v10;
        v387 = (__int16 *)(v8 + 2);
        goto LABEL_674;
      case 141:
        v386 = *(_DWORD *)v10;
        v387 = (__int16 *)(v8 + 5);
LABEL_674:
        *((_QWORD *)this + 19) = v387;
        v388 = (VAR *)(v3 + 24LL * *v387);
        *((_QWORD *)this + 19) = v387 + 1;
        v439 = v388;
        if ( *(_WORD *)v388 == 3 )
        {
          v389 = *((_DWORD *)v388 + 2);
          *((_DWORD *)v388 + 2) = v389 - v386;
          if ( *((_DWORD *)v439 + 2) < v389 != v386 > 0 )
          {
            *((double *)v439 + 1) = (double)v389 - (double)v386;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v388 == 5 )
          goto LABEL_733;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v388, v388, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v388 = v439;
LABEL_733:
        VAR::SetNumber(v388, *((double *)v388 + 1) - (double)v386);
        goto LABEL_22;
      case 142:
        v390 = (char)*v10;
        v391 = (__int16 *)(v8 + 2);
        goto LABEL_678;
      case 143:
        v390 = *(_DWORD *)v10;
        v391 = (__int16 *)(v8 + 5);
LABEL_678:
        *((_QWORD *)this + 19) = v391;
        v392 = (VAR *)(v3 + 24LL * *v391);
        *((_QWORD *)this + 19) = v391 + 1;
        v439 = v392;
        if ( *(_WORD *)v392 == 3 )
        {
          v393 = *((_DWORD *)v392 + 2);
          *((_DWORD *)v392 + 2) = v390 * v393;
          if ( (v390 ^ v393 ^ *((_DWORD *)v439 + 2)) < 0 || v393 && v390 != *((_DWORD *)v439 + 2) / v393 )
          {
            *((double *)v439 + 1) = (double)v393 * (double)v390;
            *(_WORD *)v439 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v392 == 5 )
          goto LABEL_738;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v392, v392, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v392 = v439;
LABEL_738:
        VAR::SetNumber(v392, (double)v390 * *((double *)v392 + 1));
        goto LABEL_22;
      case 144:
        v394 = (char)*v10;
        v395 = (__int16 *)(v8 + 2);
        goto LABEL_684;
      case 145:
        v394 = *(_DWORD *)v10;
        v395 = (__int16 *)(v8 + 5);
LABEL_684:
        *((_QWORD *)this + 19) = v395;
        v396 = (double *)(v3 + 24LL * *v395);
        *((_QWORD *)this + 19) = v395 + 1;
        v439 = (VAR *)v396;
        if ( *(_WORD *)v396 == 5 )
          goto LABEL_687;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v396, (struct VAR *)v396, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v396 = (double *)v439;
LABEL_687:
        v397 = CScriptRuntime::SafeDivide(this, v396[1], (double)v394);
        VAR::SetNumber(v439, v397);
        goto LABEL_22;
      case 146:
        v398 = (char)*v10;
        v399 = (__int16 *)(v8 + 2);
        goto LABEL_689;
      case 147:
        v398 = *(_DWORD *)v10;
        v399 = (__int16 *)(v8 + 5);
LABEL_689:
        *((_QWORD *)this + 19) = v399;
        v400 = (double *)(v3 + 24LL * *v399);
        *((_QWORD *)this + 19) = v399 + 1;
        v439 = (VAR *)v400;
        if ( *(_WORD *)v400 == 5 )
          goto LABEL_692;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v400, (struct VAR *)v400, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v400 = (double *)v439;
LABEL_692:
        v401 = DblMod(v400[1], (double)v398);
        VAR::SetNumber(v439, v401);
        goto LABEL_22;
      case 148:
        v324 = (char)*v10;
        v325 = (__int16 *)(v8 + 2);
        goto LABEL_560;
      case 149:
        v324 = *(_DWORD *)v10;
        v325 = (__int16 *)(v8 + 5);
LABEL_560:
        *((_QWORD *)this + 19) = v325;
        v326 = (VAR *)(v3 + 24LL * *v325);
        *((_QWORD *)this + 19) = v325 + 1;
        v439 = v326;
        if ( *(_WORD *)v326 == 3 )
        {
          *((_DWORD *)v326 + 2) &= v324;
        }
        else
        {
          if ( *(_WORD *)v326 == 5 )
          {
            *(_WORD *)v326 = 3;
            *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v326, v326, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v439 + 2) &= v324;
        }
        goto LABEL_22;
      case 150:
        v327 = (char)*v10;
        v328 = (__int16 *)(v8 + 2);
        goto LABEL_565;
      case 151:
        v327 = *(_DWORD *)v10;
        v328 = (__int16 *)(v8 + 5);
LABEL_565:
        *((_QWORD *)this + 19) = v328;
        v329 = (VAR *)(v3 + 24LL * *v328);
        *((_QWORD *)this + 19) = v328 + 1;
        v439 = v329;
        if ( *(_WORD *)v329 == 3 )
        {
          *((_DWORD *)v329 + 2) ^= v327;
        }
        else
        {
          if ( *(_WORD *)v329 == 5 )
          {
            *(_WORD *)v329 = 3;
            *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v329, v329, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v439 + 2) ^= v327;
        }
        goto LABEL_22;
      case 152:
        v330 = (char)*v10;
        v331 = (__int16 *)(v8 + 2);
        goto LABEL_570;
      case 153:
        v330 = *(_DWORD *)v10;
        v331 = (__int16 *)(v8 + 5);
LABEL_570:
        *((_QWORD *)this + 19) = v331;
        v332 = (VAR *)(v3 + 24LL * *v331);
        *((_QWORD *)this + 19) = v331 + 1;
        v439 = v332;
        if ( *(_WORD *)v332 == 3 )
        {
          *((_DWORD *)v332 + 2) |= v330;
        }
        else
        {
          if ( *(_WORD *)v332 == 5 )
          {
            *(_WORD *)v332 = 3;
            *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v332, v332, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v439 + 2) |= v330;
        }
        goto LABEL_22;
      case 154:
        LOBYTE(v333) = *v10;
        v334 = (__int16 *)(v8 + 2);
        goto LABEL_575;
      case 155:
        v333 = *(_DWORD *)v10;
        v334 = (__int16 *)(v8 + 5);
LABEL_575:
        *((_QWORD *)this + 19) = v334;
        v335 = v333 & 0x1F;
        v336 = (VAR *)(v3 + 24LL * *v334);
        *((_QWORD *)this + 19) = v334 + 1;
        v439 = v336;
        if ( *(_WORD *)v336 == 3 )
        {
          *((_DWORD *)v336 + 2) <<= v335;
        }
        else
        {
          if ( *(_WORD *)v336 == 5 )
          {
            *(_WORD *)v336 = 3;
            *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v336, v336, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v439 + 2) <<= v335;
        }
        goto LABEL_22;
      case 156:
        LOBYTE(v337) = *v10;
        v338 = (__int16 *)(v8 + 2);
        goto LABEL_580;
      case 157:
        v337 = *(_DWORD *)v10;
        v338 = (__int16 *)(v8 + 5);
LABEL_580:
        *((_QWORD *)this + 19) = v338;
        v339 = v337 & 0x1F;
        v340 = (int *)(v3 + 24LL * *v338);
        *((_QWORD *)this + 19) = v338 + 1;
        v439 = (VAR *)v340;
        if ( *(_WORD *)v340 == 3 )
        {
          v340[2] >>= v339;
        }
        else
        {
          if ( *(_WORD *)v340 == 5 )
          {
            *(_WORD *)v340 = 3;
            *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v340, (struct VAR *)v340, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((int *)v439 + 2) >>= v339;
        }
        goto LABEL_22;
      case 158:
        LOBYTE(v402) = *v10;
        v403 = (__int16 *)(v8 + 2);
        goto LABEL_704;
      case 159:
        v402 = *(_DWORD *)v10;
        v403 = (__int16 *)(v8 + 5);
LABEL_704:
        *((_QWORD *)this + 19) = v403;
        v404 = v402 & 0x1F;
        v405 = (VAR *)(v3 + 24LL * *v403);
        *((_QWORD *)this + 19) = v403 + 1;
        v439 = v405;
        if ( *(_WORD *)v405 == 3 )
          goto LABEL_708;
        if ( *(_WORD *)v405 == 5 )
        {
          *(_WORD *)v405 = 3;
          *((_DWORD *)v439 + 2) = (int)*((double *)v439 + 1);
        }
        else
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v405, v405, 3, 1);
          if ( TypeProto < 0 )
            goto LABEL_22;
        }
        v405 = v439;
LABEL_708:
        v406 = *((_DWORD *)v405 + 2);
        if ( v404 || v406 >= 0 )
        {
          *((_DWORD *)v405 + 2) = (unsigned int)v406 >> v404;
        }
        else
        {
          *((double *)v405 + 1) = (double)v406;
          *(_WORD *)v439 = 5;
        }
        goto LABEL_22;
      default:
LABEL_848:
        v28 = 0;
        v29 = 0;
        v30 = -2146828237;
        goto LABEL_34;
    }
  }
}

```

## disassembly

```asm
0x180023440  mov     r11, rsp
0x180023443  mov     [r11+10h], rdx
0x180023447  mov     [r11+8], rcx
0x18002344b  push    rbx
0x18002344c  push    rsi
0x18002344d  push    rdi
0x18002344e  push    r12
0x180023450  push    r13
0x180023452  push    r14
0x180023454  push    r15
0x180023456  sub     rsp, 320h
0x18002345d  mov     r15, rcx
0x180023460  xor     r12d, r12d
0x180023463  mov     [r11+18h], r12d
0x180023467  mov     r13, [rcx+100h]
0x18002346e  mov     r14, [rcx+108h]
0x180023475  mov     [rsp+358h+var_1B0], r14
0x18002347d  xorps   xmm0, xmm0
0x180023480  xor     eax, eax
0x180023482  movups  [rsp+358h+var_2D8], xmm0
0x18002348a  mov     [r11-2C8h], rax
0x180023491  mov     [rsp+358h+var_318], r12
0x180023496  mov     [rsp+358h+var_310], r12
0x18002349b  mov     [r11+20h], r12d
0x18002349f  mov     [r11-2A4h], r12d
0x1800234a6  mov     rax, [rcx+38h]
0x1800234aa  mov     rcx, [rax]
0x1800234ad  mov     rsi, [rcx+38h]
0x1800234b1  mov     [rsp+358h+var_1A8], rsi
0x1800234b9  mov     rcx, [r15+90h]
0x1800234c0  mov     [r15+88h], rcx
0x1800234c7  mov     [r11-2A8h], r12d
0x1800234ce  lea     rax, [r11+10h]
0x1800234d2  mov     [r15+160h], rax
0x1800234d9  lea     rax, [rsp+358h+var_308]
0x1800234de  mov     [r15+158h], rax
0x1800234e5  mov     rax, [r15+0F8h]
0x1800234ec  mov     [r15+0F0h], rax
0x1800234f3  mov     rax, [r15+0A0h]
0x1800234fa  mov     [r15+98h], rax
0x180023501  mov     dword ptr [r15+0A8h], 0FFFFFFFFh
0x18002350c  mov     dword ptr [r15+150h], 0FFFFFFFEh
0x180023517  mov     [r15+0C8h], rcx
0x18002351e  mov     [r15+0D0h], rax
0x180023525  test    rdx, rdx
0x180023528  jz      loc_180028D7C
0x18002352e  mov     [rdx], r12w
0x180023532  or      dword ptr [r15+130h], 2
0x18002353a  mov     r8, [r15]
0x18002353d  mov     r8, [r8+3D8h]; struct ThreadGlobals *
0x180023544  mov     rdx, [r15+8]; struct COleScript *
0x180023548  lea     rcx, [rsp+358h+var_58]; this
0x180023550  call    ??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@PEAVThreadGlobals@@@Z; TLS_NoDestructor::TLS_NoDestructor(COleScript *,ThreadGlobals *)
0x180023555  mov     word ptr [rsp+358h+var_2C0], r12w
0x18002355e  mov     rcx, [r15]
0x180023561  mov     [rsp+358h+var_A8], rcx
0x180023569  lea     rax, [rsp+358h+var_2C0]
0x180023571  mov     [rsp+358h+var_B0], rax
0x180023579  mov     rax, [rcx+3D0h]
0x180023580  mov     [rsp+358h+var_A0], rax
0x180023588  lea     rax, [rsp+358h+var_B0]
0x180023590  mov     [rcx+3D0h], rax
0x180023597  mov     r8d, 80h
0x18002359d  mov     r11d, 1
0x1800235a3  mov     r10d, 3
0x1800235a9  mov     ebx, 8Dh
0x1800235ae  mov     edi, 5
0x1800235b3  lea     rdx, __ImageBase
0x1800235ba  nop     word ptr [rax+rax+00h]
0x1800235c0  mov     rax, [r15+98h]
0x1800235c7  movzx   ecx, byte ptr [rax]
0x1800235ca  lea     r9, [rax+1]
0x1800235ce  mov     [r15+98h], r9
0x1800235d5  cmp     ecx, 9Fh; switch 160 cases
0x1800235db  ja      def_1800235EB; jumptable 00000001800235EB default case
0x1800235e1  mov     ecx, ds:(jpt_1800235EB - 180000000h)[rdx+rcx*4]
0x1800235e8  add     rcx, rdx
0x1800235eb  jmp     rcx; switch jump
0x1800235f1  movzx   ecx, byte ptr [r9]; jumptable 00000001800235EB case 3
0x1800235f5  lea     rax, [r9+1]
0x1800235f9  mov     [r15+98h], rax
0x180023600  mov     [r15+0A8h], ecx
0x180023607  mov     rcx, [r15]; this
0x18002360a  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x18002360f  test    eax, eax
0x180023611  jnz     loc_1800273BF
0x180023617  mov     rcx, [r15+78h]
0x18002361b  cmp     dword ptr [rcx+8], 0
0x18002361f  jnz     loc_180024AD9
0x180023625  mov     rcx, [r15]; this
0x180023628  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x18002362d  mov     [rsp+358h+arg_10], eax
0x180023634  test    eax, eax
0x180023636  jns     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x18002363c  mov     edx, [rsp+358h+arg_10]; int
0x180023643  test    edx, edx
0x180023645  jns     loc_180028D2B
0x18002364b  mov     rcx, [r15]; this
0x18002364e  call    ?ReportError@CSession@@QEAAJJ@Z; CSession::ReportError(long)
0x180023653  mov     [rsp+358h+arg_10], eax
0x18002365a  jmp     loc_180028D2B
0x18002365f  mov     rdi, [r15+90h]; jumptable 00000001800235EB case 70
0x180023666  movzx   eax, word ptr [rdi+18h]
0x18002366a  cmp     r10w, ax
0x18002366e  jz      loc_180025DD6
0x180023674  mov     [rsp+358h+var_280], r12
0x18002367c  mov     [rsp+358h+var_278], r12
0x180023684  mov     esi, 5
0x180023689  cmp     si, ax
0x18002368c  jnz     loc_1800242EF
0x180023692  cmp     si, [rdi]
0x180023695  jnz     loc_1800242EF
0x18002369b  movsd   xmm0, qword ptr [rdi+20h]; double
0x1800236a0  call    ?FNan@@YAHN@Z; FNan(double)
0x1800236a5  test    eax, eax
0x1800236a7  jnz     loc_180025306
0x1800236ad  movsd   xmm0, qword ptr [rdi+8]; double
0x1800236b2  call    ?FNan@@YAHN@Z; FNan(double)
0x1800236b7  test    eax, eax
0x1800236b9  jnz     loc_180025306
0x1800236bf  mov     edx, r12d
0x1800236c2  movsd   xmm0, qword ptr [rdi+8]
0x1800236c7  comisd  xmm0, qword ptr [rdi+20h]
0x1800236cc  setnbe  dl; int
0x1800236cf  lea     rcx, [rdi+18h]; this
0x1800236d3  call    ?SetBool@VAR@@QEAAXH@Z; VAR::SetBool(int)
0x1800236d8  mov     eax, r12d
0x1800236db  mov     [rsp+358h+arg_10], eax
0x1800236e2  test    eax, eax
0x1800236e4  js      loc_180023831
0x1800236ea  mov     rax, [r15+90h]
0x1800236f1  add     rax, 18h
0x1800236f5  mov     [r15+90h], rax
0x1800236fc  mov     r14, [rsp+358h+var_1B0]; jumptable 00000001800235EB cases 0,2,99,100
0x180023704  mov     rsi, [rsp+358h+var_1A8]
0x18002370c  jmp     loc_180023597
0x180023711  mov     ecx, [r9]; jumptable 00000001800235EB case 34
0x180023714  mov     rsi, [r15+0B0h]
0x18002371b  add     rsi, rcx
0x18002371e  lea     rax, [r9+4]
0x180023722  mov     [r15+98h], rax
0x180023729  mov     rcx, [r15+90h]; this
0x180023730  cmp     r8w, [rcx]
0x180023734  jnz     loc_1800245E6
0x18002373a  mov     rcx, [rcx+8]; this
0x18002373e  mov     [rsp+358h+var_318], rcx
0x180023743  call    ?FCanCastToObj@VAR@@QEAAHXZ; VAR::FCanCastToObj(void)
0x180023748  test    eax, eax
0x18002374a  jz      loc_1800262EC
0x180023750  mov     rax, [r15+90h]
0x180023757  movups  xmm0, xmmword ptr [rax]
0x18002375a  movaps  [rsp+358h+var_78], xmm0
0x180023762  movsd   xmm1, qword ptr [rax+10h]
0x180023767  movsd   [rsp+358h+var_68], xmm1
0x180023770  lea     rdx, [rsp+358h+var_78]
0x180023778  mov     rcx, r15
0x18002377b  call    ?IsGlobalBasedAndCanOptimizeGlobalLookup@CScriptRuntime@@QEAA_NVVAR@@@Z; CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(VAR)
0x180023780  test    al, al
0x180023782  jnz     loc_180024C3A
0x180023788  mov     rcx, [r15+90h]
0x18002378f  mov     rax, [rsp+358h+var_318]
0x180023794  mov     edx, 84h
0x180023799  mov     [rcx], dx
0x18002379c  mov     [rcx+8], rax
0x1800237a0  mov     [rcx+10h], rsi
0x1800237a4  jmp     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x1800237a9  mov     ecx, [r9]; jumptable 00000001800235EB case 28
0x1800237ac  mov     rdi, [r15+0B0h]
0x1800237b3  add     rdi, rcx
0x1800237b6  lea     rax, [r9+4]
0x1800237ba  mov     [r15+98h], rax
0x1800237c1  add     qword ptr [r15+90h], 0FFFFFFFFFFFFFFE8h
0x1800237c9  mov     rcx, [r15+90h]
0x1800237d0  mov     [rcx], r12w
0x1800237d4  mov     rbx, [r15+90h]
0x1800237db  mov     rdx, rdi; unsigned __int16 *
0x1800237de  lea     rcx, [rsp+358h+var_2D8]; this
0x1800237e6  call    ?InitFromSymbol@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromSymbol(ushort const *)
0x1800237eb  xor     r9d, r9d; struct VAR *
0x1800237ee  mov     r8, rbx; struct VAR *
0x1800237f1  mov     rdx, rax; struct SYM *
0x1800237f4  mov     rcx, r15; this
0x1800237f7  call    ?GetVarVal@CScriptRuntime@@AEAAJPEAUSYM@@PEAVVAR@@1@Z; CScriptRuntime::GetVarVal(SYM *,VAR *,VAR *)
0x1800237fc  mov     [rsp+358h+arg_10], eax
0x180023803  test    eax, eax
0x180023805  jns     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x18002380b  cmp     eax, 86664004h
0x180023810  jz      short loc_180023831
0x180023812  mov     r9, rdi; Src
0x180023815  xor     r8d, r8d; struct VAR *
0x180023818  mov     edx, eax; int
0x18002381a  mov     dword ptr [rsp+358h+pvarg], 0FFFFFFFFh; int
0x180023822  mov     rcx, [r15]; this
0x180023825  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18002382a  mov     [rsp+358h+arg_10], eax
0x180023831  mov     edi, 1
0x180023836  cmp     [rsp+358h+arg_10], 80020102h
0x180023841  jnz     loc_1800289AD
0x180023847  mov     ebx, 8Dh
0x18002384c  mov     rdx, [r15+0B8h]
0x180023853  cmp     rdx, [r15+0C0h]
0x18002385a  jz      loc_180028D20
0x180023860  cmp     bx, [rdx]
0x180023863  jnz     loc_18002363C
0x180023869  mov     ebx, [r15+130h]
0x180023870  mov     eax, ebx
0x180023872  or      eax, 4
0x180023875  mov     [r15+130h], eax
0x18002387c  mov     edx, [rdx+8]; int
0x18002387f  mov     rcx, r15; this
0x180023882  call    ?SetNextStatement@CScriptRuntime@@QEAAJJ@Z; CScriptRuntime::SetNextStatement(long)
0x180023887  and     ebx, 0FFFFFFFCh
0x18002388a  shl     ebx, 1Dh
0x18002388d  sar     ebx, 1Dh
0x180023890  mov     eax, ebx
0x180023892  xor     eax, [r15+130h]
0x180023899  and     eax, 0FFFFFFFBh
0x18002389c  xor     eax, ebx
0x18002389e  mov     [r15+130h], eax
0x1800238a5  mov     [rsp+358h+arg_10], r12d
0x1800238ad  jmp     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x1800238b2  movzx   r8d, word ptr [r9]; jumptable 00000001800235EB case 39
0x1800238b6  lea     rax, [r9+2]
0x1800238ba  mov     [r15+98h], rax
0x1800238c1  mov     rdx, [r15+90h]
0x1800238c8  lea     rbx, [r8+r8*2]
0x1800238cc  lea     rcx, [rdx+rbx*8]; this
0x1800238d0  mov     [rsp+358h+var_318], rcx
0x1800238d5  mov     [rsp+358h+var_320], r12; struct VAR *
0x1800238da  mov     [rsp+358h+var_328], rdx; struct VAR *
0x1800238df  mov     dword ptr [rsp+358h+var_330], r8d; int
0x1800238e4  lea     rax, [rsp+358h+var_2C0]
0x1800238ec  mov     [rsp+358h+pvarg], rax; pvarg
0x1800238f1  mov     r9d, 4000h; unsigned int
0x1800238f7  xor     r8d, r8d; int
0x1800238fa  mov     rdx, [r15]; struct CSession *
0x1800238fd  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x180023902  mov     [rsp+358h+arg_10], eax
0x180023909  test    eax, eax
0x18002390b  js      loc_180023831
0x180023911  mov     rax, [r15+90h]
0x180023918  lea     rcx, [rax+rbx*8]
0x18002391c  mov     [r15+90h], rcx
0x180023923  movups  xmm0, xmmword ptr [rsp+358h+var_2C0]
0x18002392b  movups  xmmword ptr [rcx], xmm0
0x18002392e  movsd   xmm1, qword ptr [rsp+358h+var_2C0+10h]
0x180023937  movsd   qword ptr [rcx+10h], xmm1
0x18002393c  jmp     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x180023941  mov     rcx, [r15+90h]; jumptable 00000001800235EB case 57
0x180023948  call    ?FTrue@VAR@@QEAAHXZ; VAR::FTrue(void)
0x18002394d  test    eax, eax
0x18002394f  jnz     loc_180023DE7
0x180023955  mov     rax, [r15+98h]
0x18002395c  mov     edx, [rax]
0x18002395e  add     rdx, [r15+0A0h]
0x180023965  mov     [r15+98h], rdx
0x18002396c  mov     [r15+0D0h], rdx
0x180023973  add     qword ptr [r15+90h], 18h
0x18002397b  mov     rax, [r15+90h]
0x180023982  mov     [r15+0C8h], rax
0x180023989  jmp     loc_1800236FC; jumptable 00000001800235EB cases 0,2,99,100
0x18002398e  movzx   r11d, word ptr [r9]; jumptable 00000001800235EB case 35
0x180023992  lea     rax, [r9+2]
0x180023996  mov     [r15+98h], rax
0x18002399d  lea     rbx, [r11+r11*2]
0x1800239a1  mov     rax, [r15+90h]
0x1800239a8  lea     rcx, [rax+rbx*8]; this
0x1800239ac  mov     [rsp+358h+var_318], rcx
0x1800239b1  mov     eax, 400Ch
0x1800239b6  cmp     [rcx], ax
0x1800239b9  jz      loc_180024D2A
0x1800239bf  mov     word ptr [rsp+358h+var_2C0], r12w
0x1800239c8  mov     rdx, [r15+98h]
0x1800239cf  lea     r8, [rsp+358h+var_2C0]
0x1800239d7  cmp     byte ptr [rdx], 42h ; 'B'
0x1800239da  cmovz   r8, r12
0x1800239de  mov     r9d, 3
0x1800239e4  test    r11w, r11w
0x1800239e8  mov     edi, 1
0x1800239ed  cmovz   r9d, edi; unsigned int
0x1800239f1  mov     [rsp+358h+var_320], r12; struct VAR *
0x1800239f6  mov     rax, [r15+90h]
0x1800239fd  mov     [rsp+358h+var_328], rax; struct VAR *
0x180023a02  mov     dword ptr [rsp+358h+var_330], r11d; int
0x180023a07  mov     [rsp+358h+pvarg], r8; pvarg
0x180023a0c  xor     r8d, r8d; int
0x180023a0f  mov     rdx, [r15]; struct CSession *
0x180023a12  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x180023a17  mov     [rsp+358h+arg_10], eax
0x180023a1e  test    eax, eax
0x180023a20  jns     loc_180023911
0x180023a26  jmp     loc_180023836
0x180023a2b  mov     rdx, [r15+90h]; jumptable 00000001800235EB case 79
0x180023a32  movzx   eax, word ptr [rdx+18h]
0x180023a36  cmp     r10w, ax
0x180023a3a  jz      loc_18002669C
0x180023a40  mov     ecx, eax; int
0x180023a42  mov     edx, 2083Ch; unsigned int
0x180023a47  call    ?FVtIn@@YAHJK@Z; FVtIn(long,ulong)
0x180023a4c  test    eax, eax
  ... truncated ...
```
