# CScriptRuntime::Run(VAR *)

- ea: `0x180026230`
- end: `0x18002bdc0`
- name: `?Run@CScriptRuntime@@QEAAJPEAVVAR@@@Z`
- size: `23440`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `2`
- callee_count: `92`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cc8c`
- `0x180062fe8`

## callees

- `0x180001d90`
- `0x1800057f0`
- `0x180005b48`
- `0x1800060f0`
- `0x180006bf0`
- `0x180006df0`
- `0x18000a610`
- `0x18000ad6c`
- `0x18000b130`
- `0x18000b200`
- `0x18000bd24`
- `0x18000d820`
- `0x18000ded0`
- `0x18000ea20`
- `0x18000f880`
- `0x18000ff30`
- `0x1800107c0`
- `0x180011c70`
- `0x180011ecc`
- `0x180014b50`
- `0x180014dc0`
- `0x180016498`
- `0x180016714`
- `0x1800167a0`
- `0x180018514`
- `0x18001879c`
- `0x180018d68`
- `0x180019d24`
- `0x18001e518`
- `0x180026230`
- `0x1800302ac`
- `0x180031594`
- `0x18003229c`
- `0x1800327e0`
- `0x180032a78`
- `0x180032b08`
- `0x18003390c`
- `0x180033ac4`
- `0x180033c30`
- `0x180033f7c`
- `0x180038180`
- `0x1800384b0`
- `0x1800384f0`
- `0x1800394f8`
- `0x180039580`
- `0x180039ee0`
- `0x18003a070`
- `0x18003a2a0`
- `0x18003a640`
- `0x18003a750`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002af26`
- `OLEAUT32!__imp_VariantInit` at `0x18002af26`
- `OLEAUT32!__imp_VariantClear` at `0x18002a140`
- `OLEAUT32!__imp_VariantClear` at `0x18002a6bc`
- `OLEAUT32!__imp_VariantClear` at `0x18002aef4`
- `OLEAUT32!__imp_VariantClear` at `0x18002af5d`
- `OLEAUT32!__imp_VariantClear` at `0x18002b7c8`
- `OLEAUT32!__imp_VariantClear` at `0x18002a140`
- `OLEAUT32!__imp_VariantClear` at `0x18002a6bc`
- `OLEAUT32!__imp_VariantClear` at `0x18002aef4`
- `OLEAUT32!__imp_VariantClear` at `0x18002af5d`
- `OLEAUT32!__imp_VariantClear` at `0x18002b7c8`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002a694`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002ae27`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002af0b`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002a694`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002ae27`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002af0b`

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
  __int64 v38; // xmm1_8
  __int64 v39; // rdx
  __int64 v40; // r11
  VAR *v41; // rcx
  struct VAR *v42; // r8
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
  int v57; // ebx
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
  int v106; // edx
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
  struct GcAlloc *v147; // rax
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
  __int64 v210; // rax
  __int64 v211; // rsi
  _WORD *v212; // rcx
  const unsigned __int16 *LocalName; // rax
  struct VAR *v214; // rbx
  struct VAR *v215; // rdi
  struct SYM *v216; // rax
  bool v217; // sf
  const unsigned __int16 *v218; // rsi
  VAR *v219; // rax
  __int64 (__fastcall *v220)(struct NameTbl *, struct SYM *, __int64); // rdi
  __int64 v221; // rbx
  struct SYM *v222; // rax
  _WORD *v223; // rcx
  struct VAR *v224; // rbx
  struct SYM *v225; // rax
  __int64 v226; // rax
  __int64 v227; // r8
  __int64 v228; // rdx
  __int64 v229; // r8
  VAR *v230; // rdx
  double *v231; // rcx
  int v232; // edx
  _WORD *v233; // rax
  _DWORD *v234; // rax
  __int64 v235; // rdx
  __int64 v236; // rcx
  __int64 v237; // rbx
  __int64 v238; // rdx
  __int64 v239; // rcx
  __int64 v240; // rdx
  char *v241; // rax
  _WORD *v242; // rax
  _WORD *v243; // rax
  __int64 v244; // r8
  __int64 v245; // rdx
  __int64 v246; // rbx
  GcAlloc *v247; // rax
  const unsigned __int16 *v248; // rax
  struct VAR *v249; // rbx
  struct VAR *v250; // rdi
  struct SYM *v251; // rax
  __int16 v252; // ax
  BOOL v253; // edx
  __int64 v254; // rcx
  __int64 v255; // rax
  _WORD *v256; // rcx
  const unsigned __int16 *v257; // rax
  struct VAR *v258; // rbx
  struct VAR *v259; // rdi
  struct SYM *v260; // rax
  int v261; // r8d
  double *v262; // rcx
  __int64 v263; // rax
  int v264; // edx
  int v265; // edx
  int v266; // edx
  __int64 v267; // rcx
  struct NameTbl *v268; // r9
  _WORD *v269; // rcx
  _WORD *v270; // rax
  __int64 *v271; // rax
  __int64 v272; // xmm0_8
  _WORD *v273; // rcx
  _WORD *v274; // rcx
  struct VAR *v275; // rbx
  struct SYM *v276; // rax
  double *v277; // rbx
  __int16 v278; // ax
  __int16 v279; // ax
  VARIANTARG *v280; // rbx
  struct GcAlloc *v281; // rax
  __int64 v282; // rax
  __int64 v283; // rax
  __int64 v284; // rax
  int v285; // r8d
  __int64 v286; // rdx
  int v287; // r9d
  struct VAR *v288; // rdx
  struct VAR *v289; // rdx
  double *v290; // rbx
  double v291; // xmm0_8
  struct VAR *v292; // rdx
  struct VAR *v293; // rdx
  double *v294; // rbx
  double v295; // xmm0_8
  struct SYM *v296; // rax
  __int64 v297; // rdi
  __int64 (__fastcall *v298)(__int64, struct SYM *, _QWORD, __int64, _QWORD); // rbx
  struct SYM *v299; // rax
  int v300; // eax
  struct VAR *v301; // rdx
  VAR *v302; // rbx
  int v303; // eax
  struct VAR *v304; // rdx
  __int64 v305; // rdx
  __int64 v306; // rax
  struct VAR *v307; // rcx
  __int64 v308; // rax
  __int64 v309; // rax
  __int64 v310; // rbx
  VAR *v311; // rcx
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rdx
  struct VAR *v316; // rcx
  __int64 v317; // rax
  __int64 v318; // rbx
  __int64 v319; // rbx
  __int64 v320; // rdx
  __int64 v321; // rdx
  VAR *v322; // rcx
  __int64 v323; // rax
  int v324; // edx
  int v325; // ebx
  __int16 *v326; // r9
  VAR *v327; // rdx
  int v328; // ebx
  __int16 *v329; // r9
  VAR *v330; // rdx
  int v331; // ebx
  __int16 *v332; // r9
  VAR *v333; // rdx
  int v334; // ebx
  __int16 *v335; // r9
  char v336; // bl
  VAR *v337; // rdx
  int v338; // ebx
  __int16 *v339; // r9
  char v340; // bl
  int *v341; // rdx
  enum tagBREAKREASON v342; // edx
  __int64 v343; // rax
  VAR *v344; // rcx
  __int64 v345; // rcx
  VAR *v346; // rax
  int v347; // edx
  __int64 v348; // rcx
  __int64 v349; // rax
  __int64 v350; // rcx
  _WORD *v351; // rax
  int *v352; // rax
  int v353; // ecx
  __int64 v354; // rcx
  __int64 v355; // rbx
  __int64 v356; // rdi
  GcAlloc *v357; // rax
  __int64 v358; // r8
  __int64 v359; // rdx
  __int64 v360; // rcx
  _WORD *v361; // rcx
  _WORD *v362; // rax
  _DWORD *v363; // rax
  struct VAR *v364; // rcx
  __int64 v365; // rax
  _WORD *v366; // rcx
  __int64 v367; // rcx
  __int64 v368; // r8
  VAR *v369; // rdx
  VAR *v370; // rcx
  int v371; // edx
  __int64 v372; // rdx
  __int64 v373; // rdi
  VAR *v374; // rcx
  __int64 v375; // rax
  __int64 v376; // rdx
  __int64 v377; // rcx
  __int64 v378; // rcx
  char *v379; // rdx
  size_t v380; // r8
  char *v381; // rcx
  __int64 v382; // rcx
  __int64 v383; // rdx
  _DWORD *v384; // rax
  __int64 v385; // rbx
  __int64 v386; // rdi
  GcAlloc *v387; // rax
  int v388; // ebx
  __int16 *v389; // r9
  VAR *v390; // rcx
  int v391; // edx
  int v392; // ebx
  __int16 *v393; // r9
  VAR *v394; // rcx
  int v395; // r8d
  int v396; // ebx
  __int16 *v397; // r9
  double *v398; // rdx
  double v399; // xmm0_8
  int v400; // ebx
  __int16 *v401; // r9
  double *v402; // rdx
  double v403; // xmm0_8
  int v404; // ebx
  __int16 *v405; // r9
  int v406; // ebx
  VAR *v407; // rdx
  int v408; // eax
  __int64 v409; // rcx
  __int64 v410; // rdx
  __int64 v411; // rdx
  VARIANTARG *v412; // rcx
  __int64 v413; // rcx
  __int64 *v414; // rax
  __int64 v415; // xmm0_8
  __int64 v416; // rcx
  __int64 v417; // rcx
  __int64 v418; // rcx
  __int64 v419; // rcx
  __int64 v420; // rdx
  char *v421; // rax
  __int64 v422; // rcx
  __int64 v423; // rdx
  _DWORD *v424; // rax
  __int64 v425; // rcx
  __int64 *v426; // rax
  __int64 v427; // xmm0_8
  int v428; // ecx
  int v429; // ecx
  int v430; // eax
  int v431; // eax
  __int64 v432; // rcx
  _WORD *v433; // rax
  _WORD *v434; // rcx
  VAR *v435; // rcx
  __int64 v436; // rcx
  __int64 v437; // rdx
  __int64 v438; // rax
  VAR *v440; // [rsp+40h] [rbp-318h] BYREF
  struct NameTbl *v441; // [rsp+48h] [rbp-310h] BYREF
  VAR *v442; // [rsp+50h] [rbp-308h] BYREF
  VAR *v443; // [rsp+58h] [rbp-300h] BYREF
  VAR *v444; // [rsp+60h] [rbp-2F8h] BYREF
  VAR *v445; // [rsp+68h] [rbp-2F0h] BYREF
  VAR *v446; // [rsp+70h] [rbp-2E8h] BYREF
  VAR *v447; // [rsp+78h] [rbp-2E0h] BYREF
  __int128 v448; // [rsp+80h] [rbp-2D8h] BYREF
  __int64 v449; // [rsp+90h] [rbp-2C8h]
  __int128 v450; // [rsp+98h] [rbp-2C0h] BYREF
  __int64 v451; // [rsp+A8h] [rbp-2B0h]
  tagBREAKREASON v452; // [rsp+B0h] [rbp-2A8h] BYREF
  int v453; // [rsp+B4h] [rbp-2A4h] BYREF
  VAR *v454; // [rsp+B8h] [rbp-2A0h] BYREF
  VAR *v455; // [rsp+C0h] [rbp-298h] BYREF
  VAR *v456; // [rsp+C8h] [rbp-290h] BYREF
  VAR *v457; // [rsp+D0h] [rbp-288h] BYREF
  VAR *v458; // [rsp+D8h] [rbp-280h] BYREF
  VAR *v459; // [rsp+E0h] [rbp-278h] BYREF
  VAR *v460; // [rsp+E8h] [rbp-270h] BYREF
  VAR *v461; // [rsp+F0h] [rbp-268h] BYREF
  VAR *v462; // [rsp+F8h] [rbp-260h] BYREF
  VAR *v463; // [rsp+100h] [rbp-258h] BYREF
  VAR *v464; // [rsp+108h] [rbp-250h] BYREF
  VAR *v465; // [rsp+110h] [rbp-248h] BYREF
  __int128 v466; // [rsp+118h] [rbp-240h] BYREF
  __int64 v467; // [rsp+128h] [rbp-230h]
  __int128 v468; // [rsp+130h] [rbp-228h] BYREF
  __int64 v469; // [rsp+140h] [rbp-218h]
  __int128 v470; // [rsp+148h] [rbp-210h] BYREF
  __int64 v471; // [rsp+158h] [rbp-200h]
  __int128 v472; // [rsp+160h] [rbp-1F8h] BYREF
  __int64 v473; // [rsp+170h] [rbp-1E8h]
  __int16 v474; // [rsp+178h] [rbp-1E0h] BYREF
  double v475; // [rsp+180h] [rbp-1D8h]
  __int128 v476; // [rsp+190h] [rbp-1C8h] BYREF
  __int64 v477; // [rsp+1A0h] [rbp-1B8h]
  __int64 v478; // [rsp+1A8h] [rbp-1B0h]
  struct ExecBody *v479; // [rsp+1B0h] [rbp-1A8h]
  __int16 v480; // [rsp+1B8h] [rbp-1A0h] BYREF
  double v481; // [rsp+1C0h] [rbp-198h]
  __int16 *v482; // [rsp+1D0h] [rbp-188h] BYREF
  unsigned int *v483; // [rsp+1D8h] [rbp-180h]
  __int64 v484; // [rsp+1E0h] [rbp-178h]
  __int128 *v485; // [rsp+1E8h] [rbp-170h] BYREF
  unsigned int *v486; // [rsp+1F0h] [rbp-168h]
  __int64 v487; // [rsp+1F8h] [rbp-160h]
  __int128 *v488; // [rsp+200h] [rbp-158h] BYREF
  unsigned int *v489; // [rsp+208h] [rbp-150h]
  __int64 v490; // [rsp+210h] [rbp-148h]
  __int128 *v491; // [rsp+218h] [rbp-140h] BYREF
  unsigned int *v492; // [rsp+220h] [rbp-138h]
  __int64 v493; // [rsp+228h] [rbp-130h]
  __int128 v494; // [rsp+230h] [rbp-128h] BYREF
  __int64 v495; // [rsp+240h] [rbp-118h]
  __m128i v496; // [rsp+248h] [rbp-110h] BYREF
  __int64 v497; // [rsp+258h] [rbp-100h]
  __int128 *v498; // [rsp+260h] [rbp-F8h] BYREF
  unsigned int *v499; // [rsp+268h] [rbp-F0h]
  __int64 v500; // [rsp+270h] [rbp-E8h]
  __int128 *v501; // [rsp+278h] [rbp-E0h] BYREF
  unsigned int *v502; // [rsp+280h] [rbp-D8h]
  __int64 v503; // [rsp+288h] [rbp-D0h]
  __int16 *v504; // [rsp+290h] [rbp-C8h] BYREF
  unsigned int *v505; // [rsp+298h] [rbp-C0h]
  __int64 v506; // [rsp+2A0h] [rbp-B8h]
  __int128 *v507; // [rsp+2A8h] [rbp-B0h] BYREF
  unsigned int *v508; // [rsp+2B0h] [rbp-A8h]
  __int64 v509; // [rsp+2B8h] [rbp-A0h]
  __int128 v510; // [rsp+2C0h] [rbp-98h] BYREF
  __int64 v511; // [rsp+2D0h] [rbp-88h]
  __int128 v512; // [rsp+2E0h] [rbp-78h] BYREF
  __int64 v513; // [rsp+2F0h] [rbp-68h]
  _BYTE v514[88]; // [rsp+300h] [rbp-58h] BYREF
  struct VAR *v515; // [rsp+368h] [rbp+10h] BYREF
  int TypeProto; // [rsp+370h] [rbp+18h] BYREF
  int v517; // [rsp+378h] [rbp+20h] BYREF

  v515 = a2;
  TypeProto = 0;
  v3 = *((_QWORD *)this + 32);
  v4 = *((_QWORD *)this + 33);
  v478 = v4;
  v448 = 0;
  v449 = 0;
  v440 = 0;
  v441 = 0;
  v517 = 0;
  v453 = 0;
  v5 = *(struct ExecBody **)(**((_QWORD **)this + 7) + 56LL);
  v479 = v5;
  v6 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 17) = v6;
  v452 = BREAKREASON_STEP;
  *((_QWORD *)this + 44) = &v515;
  *((_QWORD *)this + 43) = &v442;
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
    (TLS_NoDestructor *)v514,
    *((struct COleScript **)this + 1),
    *(struct ThreadGlobals **)(*(_QWORD *)this + 984LL));
  LOWORD(v450) = 0;
  v508 = *(unsigned int **)this;
  v507 = &v450;
  v509 = *((_QWORD *)v508 + 122);
  *((_QWORD *)v508 + 122) = &v507;
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
        v316 = v515;
        if ( !v515 )
          goto LABEL_533;
        v317 = *((_QWORD *)this + 29);
        if ( v317 )
        {
          *(_OWORD *)v515 = *(_OWORD *)v317;
          *((_QWORD *)v316 + 2) = *(_QWORD *)(v317 + 16);
          TypeProto = 0;
        }
        else
        {
          *(_WORD *)v515 = 0;
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
        v429 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *((_DWORD *)this + 42) = v429;
        goto LABEL_6;
      case 5:
        v428 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        *((_DWORD *)this + 42) = v428;
LABEL_6:
        if ( !(unsigned int)CSession::FInterrupt(*(CSession **)this) )
          goto LABEL_7;
        TypeProto = CSession::HandleHalt(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        TypeProto = CSession::HandleAbort(*(CSession **)this);
        if ( TypeProto < 0 )
          goto LABEL_9;
        if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)this, *((_DWORD *)this + 8), &v452) )
        {
          v342 = v452;
        }
        else
        {
          if ( !(unsigned int)CScriptBody::FBreak(
                                **((CScriptBody ***)this + 7),
                                *((_DWORD *)this + 42) + *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 16LL) + 24LL)) )
            goto LABEL_7;
          v342 = BREAKREASON_BREAKPOINT;
        }
        TypeProto = CScriptRuntime::Break(this, v342);
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
        v233 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v233;
        *v233 = 3;
        v234 = (_DWORD *)*((_QWORD *)this + 19);
        v196 = *v234;
        v197 = (char *)(v234 + 1);
        goto LABEL_292;
      case 9:
        v270 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v270;
        *v270 = 5;
        v271 = (__int64 *)*((_QWORD *)this + 19);
        v272 = *v271;
        *((_QWORD *)this + 19) = v271 + 1;
        *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v272;
        goto LABEL_22;
      case 10:
        v127 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        GcAlloc = CScriptRuntime::GetGcAlloc(this);
        v440 = GcAlloc::PvarAlloc(GcAlloc);
        if ( v440 )
        {
          v129 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v129;
          *v129 = 128;
          *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v440;
          v130 = v127;
LABEL_194:
          VAR::SetConstBstr(v440, (unsigned __int16 *)(*((_QWORD *)this + 22) + v130), v5);
          goto LABEL_22;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 11:
        v246 = *(unsigned int *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        v247 = CScriptRuntime::GetGcAlloc(this);
        v440 = GcAlloc::PvarAlloc(v247);
        if ( v440 )
        {
          v433 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v433;
          *v433 = 128;
          *(_QWORD *)(*((_QWORD *)this + 18) + 8LL) = v440;
          VAR::SetConstBstr(v440, (unsigned __int16 *)(*((_QWORD *)this + 22) + v246), v5);
          v434 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v434;
          *v434 = 0;
          TypeProto = CSession::GetTypeProto(*(CSession **)this, 7, *((struct VAR **)this + 18));
          if ( TypeProto >= 0 )
          {
            TypeProto = RegExpObj::CreateFromCode(
                          &v441,
                          *(struct CSession **)this,
                          (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
                          *((struct VAR **)this + 18),
                          0);
            if ( TypeProto >= 0 )
            {
              v435 = (VAR *)(*((_QWORD *)this + 18) + 24LL);
              *((_QWORD *)this + 18) = v435;
              TypeProto = VAR::SetHeapJsObj(v435, *(struct CSession **)this, v441);
              if ( TypeProto < 0 )
                (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v441 + 16LL))(v441);
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
        v242 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v242;
        *v242 = 11;
        *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = 0;
        goto LABEL_22;
      case 13:
        v243 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v243;
        *v243 = 11;
        *(_WORD *)(*((_QWORD *)this + 18) + 8LL) = -1;
        goto LABEL_22;
      case 14:
        v198 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v198;
        *v198 = 1;
        goto LABEL_22;
      case 15:
        v269 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v269;
        *v269 = 0;
        goto LABEL_22;
      case 16:
        v211 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v212 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v212;
        *v212 = 0;
        if ( (unsigned int)CScriptRuntime::FNamedLocals(this) )
        {
          LocalName = CScriptRuntime::GetLocalName(this, v211);
          if ( LocalName )
          {
            v214 = (struct VAR *)*((_QWORD *)this + 31);
            v215 = (struct VAR *)*((_QWORD *)this + 18);
            v216 = SYM::InitFromSymbol((SYM *)&v448, LocalName);
            TypeProto = CScriptRuntime::GetVarVal(this, v216, v215, v214);
            if ( !(unsigned int)FNo(TypeProto) )
              goto LABEL_356;
          }
        }
        v217 = (int)v211 < 0;
        if ( (_DWORD)v211 )
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
          v248 = CScriptRuntime::GetLocalName(this, v80);
          if ( v248 )
          {
            v249 = (struct VAR *)*((_QWORD *)this + 31);
            v250 = (struct VAR *)*((_QWORD *)this + 18);
            v251 = SYM::InitFromSymbol((SYM *)&v448, v248);
            TypeProto = CScriptRuntime::GetVarAdr(this, v251, v250, v249);
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
          v254 = *((_QWORD *)this + 18);
          v255 = *((_QWORD *)this + 14);
          *(_WORD *)v254 = 16396;
          *(_QWORD *)(v254 + 8) = v255;
          goto LABEL_22;
        }
        goto LABEL_36;
      case 18:
        v211 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v256 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v256;
        *v256 = 0;
        if ( (unsigned int)CScriptRuntime::FNamedLocals(this)
          && (v257 = CScriptRuntime::GetLocalName(this, v211)) != 0
          && (v258 = (struct VAR *)*((_QWORD *)this + 31),
              v259 = (struct VAR *)*((_QWORD *)this + 18),
              v260 = SYM::InitFromSymbol((SYM *)&v448, v257),
              TypeProto = CScriptRuntime::GetFncAdr(this, v260, v259, v258),
              !(unsigned int)FNo(TypeProto)) )
        {
LABEL_356:
          if ( !(unsigned int)FErr(TypeProto) )
            goto LABEL_22;
        }
        else
        {
          v217 = (int)v211 < 0;
          if ( (_DWORD)v211 )
          {
LABEL_838:
            if ( v217 )
              v437 = v4 + 24 * v211;
            else
              v437 = v3 + 24LL * -(int)v211;
            v438 = *((_QWORD *)this + 18);
            *(_OWORD *)v438 = *(_OWORD *)v437;
            *(_QWORD *)(v438 + 16) = *(_QWORD *)(v437 + 16);
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
              v38 = *((_QWORD *)v194 + 2);
LABEL_43:
              *(_QWORD *)(v37 + 16) = v38;
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
              v137 = SYM::InitFromSymbol((SYM *)&v448, v134),
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
        v227 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v227;
        v228 = 24LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)v227 = 16396;
        *(_QWORD *)(v227 + 8) = v3 + v228;
        goto LABEL_22;
      case 23:
      case 27:
        *((_QWORD *)this + 19) = v8 + 3;
        v273 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v273;
        *((_QWORD *)this + 19) = v8 + 4;
        *v273 = 11;
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
        v235 = *((_QWORD *)this + 18);
        v236 = 3LL * *(__int16 *)v10;
        *(_OWORD *)(v4 + 8 * v236) = *(_OWORD *)v235;
        *(_QWORD *)(v4 + 8 * v236 + 16) = *(_QWORD *)(v235 + 16);
        *((_QWORD *)this + 19) += 2LL;
        goto LABEL_22;
      case 26:
        v244 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v244;
        v245 = v4 + 24LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)v244 = 16396;
        *(_QWORD *)(v244 + 8) = v245;
        goto LABEL_22;
      case 28:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        *((_QWORD *)this + 18) -= 24LL;
        **((_WORD **)this + 18) = 0;
        v25 = (struct VAR *)*((_QWORD *)this + 18);
        v26 = SYM::InitFromSymbol((SYM *)&v448, v24);
        VarVal = CScriptRuntime::GetVarVal(this, v26, v25, 0);
        goto LABEL_29;
      case 29:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v223 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v223;
        *v223 = 0;
        v224 = (struct VAR *)*((_QWORD *)this + 18);
        v225 = SYM::InitFromSymbol((SYM *)&v448, v24);
        VarVal = CScriptRuntime::GetVarAdr(this, v225, v224, 0);
        goto LABEL_29;
      case 30:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v160 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v160;
        *v160 = 0;
        v161 = (struct VAR *)*((_QWORD *)this + 18);
        v162 = SYM::InitFromSymbol((SYM *)&v448, v24);
        VarVal = CScriptRuntime::GetFncAdr(this, v162, v161, 0);
        goto LABEL_29;
      case 31:
        v24 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v274 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v274;
        *v274 = 0;
        v275 = (struct VAR *)*((_QWORD *)this + 18);
        v276 = SYM::InitFromSymbol((SYM *)&v448, v24);
        VarVal = CScriptRuntime::GetDelAdr(this, v276, v275, 0);
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
        SYM::InitFromSymbol((SYM *)&v448, v157);
        v158 = *((_QWORD *)this + 18);
        v510 = *(_OWORD *)(v158 + 24);
        v511 = *(_QWORD *)(v158 + 40);
        if ( (unsigned __int8)CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(this, &v510)
          && (TypeProto = NameTbl::GetValSimpleInScope(
                            *((NameTbl **)this + 36),
                            (struct SYM *)&v448,
                            *((struct VAR **)this + 18)),
              (unsigned int)FYes(TypeProto))
          || (v159 = VAR::InvokeByName(
                       (VAR *)(*((_QWORD *)this + 18) + 24LL),
                       *(struct CSession **)this,
                       (struct SYM *)&v448,
                       2u,
                       *((VARIANTARG **)this + 18),
                       0,
                       0),
              TypeProto = v159,
              v159 >= 0) )
        {
          v309 = *((_QWORD *)this + 18);
          *(_OWORD *)(v309 + 24) = *(_OWORD *)v309;
          *(_QWORD *)(v309 + 40) = *(_QWORD *)(v309 + 16);
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
          v440 = v20[1];
          if ( !(unsigned int)VAR::FCanCastToObj(v440) )
          {
LABEL_412:
            v31 = CSession::RecordHr(*(CSession **)this, -2146823281, *((struct VAR **)this + 18), 0, 0);
            goto LABEL_35;
          }
          v21 = (__int128 *)*((_QWORD *)this + 18);
          v512 = *v21;
          v513 = *((_QWORD *)v21 + 2);
          if ( !(unsigned __int8)CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(this, &v512) )
            goto LABEL_27;
          v140 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
          *((_QWORD *)this + 18) = v140;
          *v140 = 0;
          v141 = (NameTbl *)*((_QWORD *)this + 36);
          v142 = (struct VAR *)*((_QWORD *)this + 18);
          v143 = SYM::InitFromSymbol((SYM *)&v448, v19);
          TypeProto = NameTbl::GetAdrSimpleInScope(v141, v143, v142);
          v144 = (unsigned int)FYes(TypeProto) == 0;
          v121 = *((_QWORD *)this + 18);
          if ( v144 )
          {
            *((_QWORD *)this + 18) = v121 + 24;
LABEL_27:
            v22 = *((_QWORD *)this + 18);
            v23 = v440;
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
        v440 = v103;
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
        v440 = v41;
        if ( *(_WORD *)v41 == 16396 )
        {
          v145 = *((_QWORD *)v41 + 1);
          *(_OWORD *)v41 = *(_OWORD *)v145;
          *((_QWORD *)v41 + 2) = *(_QWORD *)(v145 + 16);
          v41 = v440;
        }
        LOWORD(v450) = 0;
        v42 = (struct VAR *)&v450;
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
        v310 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v311 = (VAR *)(*((_QWORD *)this + 18) + 24 * v310);
        v440 = v311;
        if ( *(_WORD *)v311 == 16396 )
        {
          v312 = *((_QWORD *)v311 + 1);
          *(_OWORD *)v311 = *(_OWORD *)v312;
          *((_QWORD *)v311 + 2) = *(_QWORD *)(v312 + 16);
          v311 = v440;
        }
        TypeProto = VAR::InvokeByDispID(v311, *(struct CSession **)this, 0, 1u, 0, v310, *((struct VAR **)this + 18), 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v313 = (unsigned int)(v310 + 1);
        goto LABEL_525;
      case 37:
        v318 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        if ( !(_DWORD)v318 )
          goto LABEL_542;
        v372 = (unsigned int)(v318 + 1);
        v373 = 3 * v372;
        v374 = (VAR *)(*((_QWORD *)this + 18) + 24 * v372);
        v440 = v374;
        if ( *(_WORD *)v374 == 16396 )
        {
          v375 = *((_QWORD *)v374 + 1);
          *(_OWORD *)v374 = *(_OWORD *)v375;
          *((_QWORD *)v374 + 2) = *(_QWORD *)(v375 + 16);
          v374 = v440;
        }
        TypeProto = VAR::InvokeByDispID(
                      v374,
                      *(struct CSession **)this,
                      0,
                      0xCu,
                      0,
                      v372,
                      *((struct VAR **)this + 18),
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v376 = *((_QWORD *)this + 18);
        v377 = 3 * (v318 + 1);
        *(_OWORD *)(v376 + 8 * v377) = *(_OWORD *)v376;
        *(_QWORD *)(v376 + 8 * v377 + 16) = *(_QWORD *)(v376 + 16);
        *((_QWORD *)this + 18) += 8 * v373;
        goto LABEL_22;
      case 38:
        v319 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        if ( !(_DWORD)v319 )
        {
LABEL_542:
          v28 = 0;
          v29 = 0;
          v30 = -2146823285;
          goto LABEL_34;
        }
        v320 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v320;
        *(_OWORD *)v320 = *(_OWORD *)(v320 + 24 * (v319 + 2));
        *(_QWORD *)(v320 + 16) = *(_QWORD *)(v320 + 24 * (v319 + 2) + 16);
        v321 = (unsigned int)(v319 + 1);
        v322 = (VAR *)(*((_QWORD *)this + 18) + 24 * v321);
        v440 = v322;
        if ( *(_WORD *)v322 == 16396 )
        {
          v323 = *((_QWORD *)v322 + 1);
          *(_OWORD *)v322 = *(_OWORD *)v323;
          *((_QWORD *)v322 + 2) = *(_QWORD *)(v323 + 16);
          v322 = v440;
        }
        TypeProto = VAR::InvokeByDispID(
                      v322,
                      *(struct CSession **)this,
                      0,
                      0xCu,
                      0,
                      v321,
                      *((struct VAR **)this + 18),
                      0);
        if ( TypeProto >= 0 )
        {
          v313 = (unsigned int)(v319 + 3);
LABEL_525:
          *((_QWORD *)this + 18) += 24 * v313;
          goto LABEL_22;
        }
        goto LABEL_36;
      case 39:
        v34 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v35 = (struct VAR *)*((_QWORD *)this + 18);
        v36 = 3 * v34;
        v440 = (struct VAR *)((char *)v35 + 24 * v34);
        TypeProto = VAR::InvokeByDispID(v440, *(struct CSession **)this, 0, 0x4000u, (struct VAR *)&v450, v34, v35, 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
LABEL_42:
        v37 = *((_QWORD *)this + 18) + 8 * v36;
        *((_QWORD *)this + 18) = v37;
        *(_OWORD *)v37 = v450;
        v38 = v451;
        goto LABEL_43;
      case 40:
        v83 = (struct IDispatch **)VAR::PvarCutHeap((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( !(unsigned int)VAR::FCanCastToObj((VAR *)v83) )
          goto LABEL_466;
        if ( *(_WORD *)v83 == 9 && (unsigned int)CSession::IsIE3(*(CSession **)this) )
        {
          v84 = (VAR *)*((_QWORD *)this + 18);
          v440 = v84;
          *((_QWORD *)this + 18) = (char *)v84 - 24;
          *((_WORD *)v84 - 12) = 0;
          TypeProto = ConvertToString(*(struct CSession **)this, &v440, *((struct VAR **)this + 18), 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
          v85 = SYM::InitFromBstr((SYM *)&v448, *((const unsigned __int16 **)v440 + 1));
          DispatchDispID = GetDispatchDispID(*(struct CSession **)this, v83[1], v85, &v453);
          TypeProto = DispatchDispID;
          *((_QWORD *)this + 18) += 24LL;
          v87 = *((_QWORD *)this + 18);
          if ( DispatchDispID >= 0 )
          {
            v88 = VAR::InvokeByDispID(
                    (VAR *)(v87 + 24),
                    *(struct CSession **)this,
                    v453,
                    2u,
                    (struct VAR *)(v87 + 24),
                    0,
                    0,
                    0);
            goto LABEL_131;
          }
          if ( DispatchDispID == -2147352570 )
          {
            v296 = SYM::InitFromPsz((SYM *)&v448, L"item");
            v88 = VAR::InvokeByName(
                    (VAR *)(v87 + 24),
                    *(struct CSession **)this,
                    v296,
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
            v4 = v478;
            goto LABEL_23;
          }
        }
        else
        {
          v186 = VAR::InvokeByVar(
                   (VAR *)(*((_QWORD *)this + 18) + 24LL),
                   *(struct CSession **)this,
                   *((struct VAR **)this + 18),
                   2u,
                   (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
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
                      (VAR *)(*((_QWORD *)this + 18) + 48LL),
                      *(struct CSession **)this,
                      (struct VAR *)(*((_QWORD *)this + 18) + 24LL),
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
        v440 = VAR::PvarCutHeap((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( (unsigned int)VAR::FCanCastToObj(v440) )
        {
          v146 = (VAR *)(*((_QWORD *)this + 18) + 24LL);
          if ( v440 != v146
            || (v147 = CScriptRuntime::GetGcAlloc(this),
                TypeProto = VAR::MoveToHeap((VARIANTARG *)v146, v147),
                TypeProto >= 0) )
          {
            v148 = VAR::PvarCutHeap(*((VAR **)this + 18));
            v149 = v148;
            v440 = v148;
            v150 = *(unsigned __int16 *)v148;
            if ( v150 == 3 || (v151 = v150 - 5) == 0 )
            {
              v280 = (VARIANTARG *)*((_QWORD *)this + 18);
              if ( v148 != (VAR *)v280
                || (v281 = CScriptRuntime::GetGcAlloc(this), TypeProto = VAR::MoveToHeap(v280, v281), TypeProto >= 0) )
              {
                v149 = *(VAR **)(*((_QWORD *)this + 18) + 8LL);
                v440 = v149;
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
              TypeProto = ConvertToString(*(struct CSession **)this, &v440, *((struct VAR **)this + 18), 1);
              if ( TypeProto >= 0 )
              {
                v149 = v440;
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
        v440 = VAR::PvarCutHeap(*((VAR **)this + 18));
        if ( *(_WORD *)v440 != 3
          && *(_WORD *)v440 != 5
          && *(_WORD *)v440 != 8
          && *(_WORD *)v440 != 130
          && *(_WORD *)v440 != 143 )
        {
          TypeProto = ConvertToString(*(struct CSession **)this, &v440, *((struct VAR **)this + 18), 1);
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
          v300 = VAR::InvokeDispName(v90, *(struct CSession **)this, 2u, v90, 0, 0);
LABEL_471:
          TypeProto = v300;
          if ( v300 >= 0 )
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
            v297 = *((_QWORD *)this + 36);
            v298 = *(__int64 (__fastcall **)(__int64, struct SYM *, _QWORD, __int64, _QWORD))(*(_QWORD *)v297 + 128LL);
            v299 = SYM::InitFromSymbol((SYM *)&v448, *(const unsigned __int16 **)(v67 + 40));
            v120 = v298(v297, v299, 0, v67, 0);
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
        if ( TypeProto != -2147352319 && (int)CScriptRuntime::ConstructErrorObject(this, (struct VAR *)&v450) >= 0 )
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)this + 1208LL));
          if ( *(_QWORD *)this != -1208 )
          {
            VAR::GetStdVar((VAR *)&v450, (struct tagVARIANT *)(*(_QWORD *)this + 1208LL));
            if ( (int)CSession::CanHandleException(*(CSession **)this) >= 0 )
              goto LABEL_37;
            if ( TypeProto == -2147352319
              || !(unsigned int)CSession::FReportError(*(CSession **)this)
              || !(unsigned int)CScriptRuntime::FResumeFromRuntimeError(this, &TypeProto, 1) )
            {
              goto LABEL_9;
            }
LABEL_23:
            v5 = v479;
            continue;
          }
        }
LABEL_9:
        if ( TypeProto < 0 )
          TypeProto = CSession::ReportError(*(CSession **)this, TypeProto);
LABEL_850:
        CSession::StepOutComplete(*(CSession **)this, *((_DWORD *)this + 8));
        *((_DWORD *)this + 76) &= ~2u;
        TLS_NoDestructor::Close((TLS_NoDestructor *)v514);
        GCRootStack::Pop((GCRootStack *)(v508 + 236));
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
              v183 = SYM::InitFromSymbol((SYM *)&v448, *(const unsigned __int16 **)(v72 + 16));
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
        v348 = *((_QWORD *)this + 18);
        v349 = v348 - 24;
        *((_QWORD *)this + 18) = v348 - 24;
        *(_OWORD *)v349 = *(_OWORD *)v348;
        *(_QWORD *)(v349 + 16) = *(_QWORD *)(v348 + 16);
        goto LABEL_22;
      case 48:
        v378 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v379 = (char *)*((_QWORD *)this + 18);
        v380 = 24 * v378;
        v381 = &v379[-24 * v378];
        *((_QWORD *)this + 18) = v381;
        memcpy_0(v381, v379, v380);
        goto LABEL_22;
      case 49:
        v409 = *(unsigned __int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v410 = *((_QWORD *)this + 18);
        v409 *= 3;
        *(_OWORD *)(v410 + 8 * v409) = *(_OWORD *)v410;
        *(_QWORD *)(v410 + 8 * v409 + 16) = *(_QWORD *)(v410 + 16);
        goto LABEL_22;
      case 50:
        v237 = *(int *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        TypeProto = CSession::GetTypeProto(*(CSession **)this, 0, (struct VAR *)&v450);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = ArrayObj::Create(
                      &v441,
                      *(struct CSession **)this,
                      v237,
                      *((struct VAR **)this + 18),
                      (struct VAR *)&v450,
                      0,
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj((VAR *)&v450, *(struct CSession **)this, v441);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v441 + 16LL))(v441);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v238 = *((_QWORD *)this + 18) + 24 * v237;
        *((_QWORD *)this + 18) = v238;
        v238 -= 24;
        *((_QWORD *)this + 18) = v238;
        *(_OWORD *)v238 = v450;
        *(_QWORD *)(v238 + 16) = v451;
        goto LABEL_22;
      case 51:
        TypeProto = CSession::GetTypeProto(*(CSession **)this, 5, (struct VAR *)&v450);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = NameTbl::Create(&v441, *(struct CSession **)this, (struct VAR *)&v450, 0, 0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj((VAR *)&v450, *(struct CSession **)this, v441);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v441 + 16LL))(v441);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v226 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v226;
        *(_OWORD *)v226 = v450;
        *(_QWORD *)(v226 + 16) = v451;
        goto LABEL_22;
      case 52:
        v218 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v219 = VAR::PvarCutAll((VAR *)(*((_QWORD *)this + 18) + 24LL));
        if ( !(unsigned int)VAR::IsJsObj(v219, &v441) )
          goto LABEL_181;
        v220 = *(__int64 (__fastcall **)(struct NameTbl *, struct SYM *, __int64))(*(_QWORD *)v441 + 272LL);
        v221 = *((_QWORD *)this + 18);
        v222 = SYM::InitFromSymbol((SYM *)&v448, v218);
        Value = v220(v441, v222, v221);
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
        v231 = (double *)*((_QWORD *)this + 18);
LABEL_381:
        VAR::SetNumber((VAR *)v231, v231[1] + 1.0);
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
          v305 = *((_QWORD *)this + 20) + **((unsigned int **)this + 19);
          *((_QWORD *)this + 19) = v305;
          *((_QWORD *)this + 26) = v305;
          v306 = *((_QWORD *)this + 18) + 24LL;
          *((_QWORD *)this + 18) = v306;
          *((_QWORD *)this + 25) = v306;
          goto LABEL_22;
        }
        v343 = *((_QWORD *)this + 18) + 24LL;
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
        v302 = (VAR *)*((_QWORD *)this + 18);
        v303 = VAR::FTrue(v302);
        VAR::SetBool(v302, v303 == 0);
        goto LABEL_22;
      case 64:
        v300 = CScriptRuntime::TypeOf(this);
        goto LABEL_471;
      case 65:
        v300 = CScriptRuntime::Delete(this);
        goto LABEL_471;
      case 66:
        **((_WORD **)this + 18) = 0;
        goto LABEL_22;
      case 67:
        v304 = (struct VAR *)*((_QWORD *)this + 18);
        if ( ((*(_WORD *)v304 - 3) & 0xFFFD) == 0 )
          goto LABEL_22;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v304, v304, 5, 1);
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
          v253 = *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) < *((_DWORD *)v13 + 2);
          v204 = (VAR *)(v13 + 3);
LABEL_363:
          VAR::SetBool(v204, v253);
          goto LABEL_19;
        }
        v458 = 0;
        v459 = 0;
        if ( v14 == 5 && *(_WORD *)v13 == 5 )
          goto LABEL_14;
        Value = VAR::GetValue((VAR *)(v13 + 3), *(struct CSession **)this, &v458, (struct VAR *)(v13 + 3), 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v458 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue((VAR *)v13, *(struct CSession **)this, &v459, (struct VAR *)v13, 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v459 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v458) && (unsigned int)VAR::FBstr(v459) )
        {
          v15 = (unsigned int)StrComp(
                                *(struct CSession **)this,
                                *((unsigned __int16 **)v458 + 1),
                                *((unsigned __int16 **)v459 + 1)) >> 31;
          goto LABEL_17;
        }
        if ( !(unsigned int)ConvertToScalarCore(v458, (struct VAR *)(v13 + 3), 5) )
          goto LABEL_844;
        if ( !(unsigned int)ConvertToScalarCore(v459, (struct VAR *)v13, 5) )
          goto LABEL_140;
LABEL_14:
        if ( (unsigned int)FNan(v13[4]) || (unsigned int)FNan(v13[1]) )
          goto LABEL_269;
        v15 = 0;
        LOBYTE(v15) = v13[1] > v13[4];
        goto LABEL_17;
      case 71:
        v277 = (double *)*((_QWORD *)this + 18);
        v279 = *((_WORD *)v277 + 12);
        if ( v279 == 3 && *(_WORD *)v277 == 3 )
        {
          VAR::SetBool((VAR *)(v277 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) <= *((_DWORD *)v277 + 2));
LABEL_19:
          v17 = *((_QWORD *)this + 18);
LABEL_20:
          v18 = v17 + 24;
          goto LABEL_21;
        }
        v462 = 0;
        v463 = 0;
        if ( v279 == 5 && *(_WORD *)v277 == 5 )
          goto LABEL_556;
        Value = VAR::GetValue((VAR *)(v277 + 3), *(struct CSession **)this, &v462, (struct VAR *)(v277 + 3), 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v462 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue((VAR *)v277, *(struct CSession **)this, &v463, (struct VAR *)v277, 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v463 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v462) && (unsigned int)VAR::FBstr(v463) )
        {
          v431 = StrComp(*(struct CSession **)this, *((unsigned __int16 **)v462 + 1), *((unsigned __int16 **)v463 + 1));
          VAR::SetBool((VAR *)(v277 + 3), v431 <= 0);
          Value = 0;
          goto LABEL_18;
        }
        if ( !(unsigned int)ConvertToScalarCore(v462, (struct VAR *)(v277 + 3), 5) )
        {
          v89 = (struct VAR *)(v277 + 3);
          goto LABEL_786;
        }
        if ( !(unsigned int)ConvertToScalarCore(v463, (struct VAR *)v277, 5) )
        {
          v89 = (struct VAR *)v277;
          goto LABEL_786;
        }
LABEL_556:
        if ( !(unsigned int)FNan(v277[4]) && !(unsigned int)FNan(v277[1]) )
        {
          VAR::SetBool((VAR *)(v277 + 3), v277[1] >= v277[4]);
          Value = 0;
          goto LABEL_18;
        }
        goto LABEL_798;
      case 72:
        v13 = (double *)*((_QWORD *)this + 18);
        v252 = *((_WORD *)v13 + 12);
        if ( v252 == 3 && *(_WORD *)v13 == 3 )
        {
          VAR::SetBool((VAR *)(v13 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) > *((_DWORD *)v13 + 2));
          goto LABEL_19;
        }
        v460 = 0;
        v461 = 0;
        if ( v252 == 5 && *(_WORD *)v13 == 5 )
          goto LABEL_536;
        Value = VAR::GetValue((VAR *)(v13 + 3), *(struct CSession **)this, &v460, (struct VAR *)(v13 + 3), 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v460 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue((VAR *)v13, *(struct CSession **)this, &v461, (struct VAR *)v13, 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v461 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v460) && (unsigned int)VAR::FBstr(v461) )
        {
          v15 = (int)StrComp(
                       *(struct CSession **)this,
                       *((unsigned __int16 **)v460 + 1),
                       *((unsigned __int16 **)v461 + 1)) > 0;
          goto LABEL_17;
        }
        if ( !(unsigned int)ConvertToScalarCore(v460, (struct VAR *)(v13 + 3), 5) )
        {
LABEL_844:
          Value = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)(v13 + 3), 0, -1);
LABEL_18:
          TypeProto = Value;
          if ( Value >= 0 )
            goto LABEL_19;
          goto LABEL_36;
        }
        if ( (unsigned int)ConvertToScalarCore(v461, (struct VAR *)v13, 5) )
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
        v277 = (double *)*((_QWORD *)this + 18);
        v278 = *((_WORD *)v277 + 12);
        if ( v278 == 3 && *(_WORD *)v277 == 3 )
        {
          VAR::SetBool((VAR *)(v277 + 3), *(_DWORD *)(*((_QWORD *)this + 18) + 32LL) >= *((_DWORD *)v277 + 2));
          goto LABEL_19;
        }
        v464 = 0;
        v465 = 0;
        if ( v278 == 5 && *(_WORD *)v277 == 5 )
          goto LABEL_550;
        Value = VAR::GetValue((VAR *)(v277 + 3), *(struct CSession **)this, &v464, (struct VAR *)(v277 + 3), 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v464 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        Value = VAR::GetValue((VAR *)v277, *(struct CSession **)this, &v465, (struct VAR *)v277, 0x2000u);
        if ( Value < 0 )
          goto LABEL_18;
        if ( !v465 )
        {
          Value = -2146828281;
          goto LABEL_18;
        }
        if ( (unsigned int)VAR::FBstr(v464) && (unsigned int)VAR::FBstr(v465) )
        {
          v430 = StrComp(*(struct CSession **)this, *((unsigned __int16 **)v464 + 1), *((unsigned __int16 **)v465 + 1));
          VAR::SetBool((VAR *)(v277 + 3), v430 >= 0);
          Value = 0;
          goto LABEL_18;
        }
        if ( !(unsigned int)ConvertToScalarCore(v464, (struct VAR *)(v277 + 3), 5) )
        {
          v89 = (struct VAR *)(v277 + 3);
          goto LABEL_786;
        }
        if ( !(unsigned int)ConvertToScalarCore(v465, (struct VAR *)v277, 5) )
        {
          v89 = (struct VAR *)v277;
LABEL_786:
          Value = CSession::RecordHr(*(CSession **)this, -2146823287, v89, 0, -1);
          goto LABEL_18;
        }
LABEL_550:
        if ( (unsigned int)FNan(v277[4]) || (unsigned int)FNan(v277[1]) )
        {
LABEL_798:
          v324 = 0;
        }
        else
        {
          v324 = 0;
          LOBYTE(v324) = v277[4] >= v277[1];
        }
        VAR::SetBool((VAR *)(v277 + 3), v324);
        Value = 0;
        goto LABEL_18;
      case 74:
        v203 = *((_QWORD *)this + 18);
        v204 = (VAR *)(v203 + 24);
        if ( *(_WORD *)(v203 + 24) == 3 && *(_WORD *)v203 == 3 )
        {
LABEL_797:
          v253 = *(_DWORD *)(v203 + 32) == *(_DWORD *)(v203 + 8);
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
          v285 = *(_DWORD *)(v44 + 32);
          *(_DWORD *)(v44 + 32) = v285 + *(_DWORD *)(v44 + 8);
          v286 = *((_QWORD *)this + 18);
          v287 = *(_DWORD *)(v286 + 8);
          if ( *(_DWORD *)(v286 + 32) < v287 == (unsigned int)v285 >> 31 )
            goto LABEL_63;
          *(double *)(v286 + 32) = (double)v285 + (double)v287;
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
        v445 = 0;
        v442 = 0;
        IsAStringObj = VAR::IsAStringObj((VAR *)(v187 + 3));
        v189 = (VAR *)(v187 + 3);
        if ( IsAStringObj )
        {
          v190 = VAR::PvarCutHeap(v189);
          v445 = v190;
        }
        else
        {
          if ( (int)VAR::GetValue(v189, *(struct CSession **)this, &v445, (struct VAR *)(v187 + 3), 0) < 0 )
            goto LABEL_63;
          v190 = v445;
        }
        if ( !v190 )
          goto LABEL_63;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)v187) )
        {
          v191 = VAR::PvarCutHeap((VAR *)v187);
          v442 = v191;
        }
        else
        {
          if ( (int)VAR::GetValue((VAR *)v187, *(struct CSession **)this, &v442, (struct VAR *)v187, 0) < 0 )
            goto LABEL_63;
          v191 = v442;
        }
        if ( !v191 )
          goto LABEL_63;
        if ( (unsigned int)VAR::FStr(v445) )
        {
          if ( !(unsigned int)VAR::FStr(v442)
            && (int)ConvertToString(*(struct CSession **)this, &v442, (struct VAR *)v187, 0) < 0 )
          {
            goto LABEL_63;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v442) )
          {
            if ( !(unsigned int)ConvertToScalarCore(v445, (struct VAR *)(v187 + 3), 5) )
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)(v187 + 3), 0, -1);
              *((_QWORD *)this + 18) += 24LL;
              goto LABEL_22;
            }
            if ( !(unsigned int)ConvertToScalarCore(v442, (struct VAR *)v187, 5) )
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
          if ( (int)ConvertToString(*(struct CSession **)this, &v445, (struct VAR *)(v187 + 3), 0) < 0 )
            goto LABEL_63;
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)(v187 + 3), v445, v442);
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
          v301 = (struct VAR *)*((_QWORD *)this + 18);
          if ( *(_WORD *)v301 != 5 )
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v301, v301, 5, 1);
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
        v292 = (struct VAR *)(*((_QWORD *)this + 18) + 24LL);
        if ( *(_WORD *)v292 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v292, v292, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v293 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v293 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v293, v293, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v294 = (double *)*((_QWORD *)this + 18);
        v295 = CScriptRuntime::SafeDivide(this, v294[4], v294[1]);
        VAR::SetNumber((VAR *)(v294 + 3), v295);
        goto LABEL_19;
      case 83:
        v288 = (struct VAR *)(*((_QWORD *)this + 18) + 24LL);
        if ( *(_WORD *)v288 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v288, v288, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v289 = (struct VAR *)*((_QWORD *)this + 18);
        if ( *(_WORD *)v289 != 5 )
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v289, v289, 5, 1);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        v290 = (double *)*((_QWORD *)this + 18);
        v291 = DblMod(v290[4], v290[1]);
        VAR::SetNumber((VAR *)(v290 + 3), v291);
        goto LABEL_19;
      case 84:
        v192 = *(_DWORD *)v10;
        *((_QWORD *)this + 19) = v8 + 5;
        v193 = *(int *)(v8 + 5);
        *((_QWORD *)this + 19) = v8 + 9;
        v440 = (VAR *)(*((_QWORD *)this + 34) + 24 * v193);
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
                      &v441,
                      *((struct VAR **)this + 30),
                      *((struct VAR **)this + 11),
                      0);
        if ( TypeProto < 0 )
          goto LABEL_36;
        TypeProto = VAR::SetHeapJsObj(v440, *(struct CSession **)this, v441);
        if ( TypeProto < 0 )
          (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v441 + 16LL))(v441);
        if ( TypeProto < 0 )
          goto LABEL_36;
        *((_QWORD *)this + 18) -= 24LL;
        v194 = v440;
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
        v263 = *((_QWORD *)this + 18);
        v37 = *((_QWORD *)this + 14);
        *(_OWORD *)v37 = *(_OWORD *)v263;
        v38 = *(_QWORD *)(v263 + 16);
        goto LABEL_43;
      case 86:
        v79 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        if ( (*((_BYTE *)this + 80) & 1) == 0 )
          goto LABEL_301;
        SYM::InitFromSymbol((SYM *)&v448, v79);
        TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 37) + 160LL))(
                      *((_QWORD *)this + 37),
                      &v448,
                      &v517);
        if ( (unsigned int)FErr(TypeProto) )
          goto LABEL_36;
        if ( (unsigned int)FYes(TypeProto) )
        {
          (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 37) + 264LL))(
            *((_QWORD *)this + 37),
            &v448,
            *((_QWORD *)this + 18),
            0);
          goto LABEL_22;
        }
LABEL_301:
        v205 = 16 * ((*((_DWORD *)this + 20) & 1) == 0);
        v206 = *((_QWORD *)this + 37);
        v207 = *(__int64 (__fastcall **)(__int64, struct SYM *, _QWORD, __int64, _QWORD))(*(_QWORD *)v206 + 128LL);
        v208 = *((_QWORD *)this + 18);
        v209 = SYM::InitFromSymbol((SYM *)&v448, v79);
        TypeProto = v207(v206, v209, v205, v208, 0);
        if ( TypeProto >= 0 )
          goto LABEL_22;
        v4 = v478;
        goto LABEL_36;
      case 87:
        v115 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        v116 = VAR::PvarCutHeap(*((VAR **)this + 18));
        v117 = *(unsigned __int16 *)v116;
        if ( v117 != 9 && (v264 = v117 - 129) != 0 && (v265 = v264 - 5) != 0 && (v266 = v265 - 1) != 0 && v266 != 9
          || (v118 = (struct IDispatch *)*((_QWORD *)v116 + 1)) == 0 )
        {
          TypeProto = CSession::RecordHr(*(CSession **)this, -2146823281, *((struct VAR **)this + 18), 0, 0);
          goto LABEL_36;
        }
        v119 = *((_QWORD *)this + 18);
        if ( *(_WORD *)(v119 + 24) != 128
          || (v267 = *(_QWORD *)(v119 + 32), *(_WORD *)v267 != 129)
          || (v268 = *(struct NameTbl **)(v267 + 8)) == 0 )
        {
LABEL_181:
          TypeProto = CSession::RecordHr(*(CSession **)this, -2146828237, 0, 0, -1);
          goto LABEL_36;
        }
        Value = COleScript::RegisterEvtHandler(*((COleScript **)this + 1), v118, v115, v268);
        goto LABEL_18;
      case 88:
        v66 = (const unsigned __int16 *)(*(unsigned int *)v10 + *((_QWORD *)this + 22));
        *((_QWORD *)this + 19) = v8 + 5;
        SYM::InitFromSymbol((SYM *)&v448, v66);
        TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(**((_QWORD **)this + 37) + 160LL))(
                      *((_QWORD *)this + 37),
                      &v448,
                      &v517);
        if ( (unsigned int)FErr(TypeProto) )
          goto LABEL_36;
        if ( !(unsigned int)FYes(TypeProto) || (v517 & 3) != 0 )
        {
          TypeProto = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 37)
                                                                                            + 128LL))(
                        *((_QWORD *)this + 37),
                        &v448,
                        16 * (unsigned int)((*((_DWORD *)this + 20) & 1) == 0),
                        0,
                        0);
          if ( TypeProto < 0 )
            goto LABEL_36;
        }
        goto LABEL_22;
      case 89:
        v307 = v515;
        if ( v515 )
        {
          v308 = *((_QWORD *)this + 18);
          *(_OWORD *)v515 = *(_OWORD *)v308;
          *((_QWORD *)v307 + 2) = *(_QWORD *)(v308 + 16);
        }
        goto LABEL_514;
      case 91:
        goto LABEL_63;
      case 92:
        v364 = (struct VAR *)*((_QWORD *)this + 29);
        goto LABEL_637;
      case 93:
        if ( (unsigned int)VAR::IsIDispatch(*((VAR **)this + 18)) )
          goto LABEL_307;
        VarVal = ConvertToObject(*(struct CSession **)this, *((struct VAR **)this + 18), (struct VAR *)&v450, 0);
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
          v210 = *((_QWORD *)this + 18);
          *(_OWORD *)v210 = v450;
          *(_QWORD *)(v210 + 16) = v451;
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
        v344 = (VAR *)*((_QWORD *)this + 18);
        if ( *((VAR **)this + 30) != v344
          || !(unsigned int)VAR::IsIDispatch(v344) && **((_WORD **)this + 18)
          || *((_QWORD *)this + 30) == *((_QWORD *)this + 31) )
        {
          goto LABEL_848;
        }
        v345 = *((_QWORD *)this + 18);
        *((_QWORD *)this + 30) = *(_QWORD *)(v345 + 16);
        v18 = v345 + 24;
        goto LABEL_21;
      case 96:
        v347 = 1;
        goto LABEL_614;
      case 97:
        v347 = 0;
LABEL_614:
        v300 = CScriptRuntime::ForIn(this, v347);
        goto LABEL_471;
      case 98:
        goto LABEL_233;
      case 101:
        v282 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v282;
        *(_OWORD *)v282 = *(_OWORD *)(v282 + 48);
        *(_QWORD *)(v282 + 16) = *(_QWORD *)(v282 + 64);
        TypeProto = CScriptRuntime::CompareEquiv(this);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v283 = *((_QWORD *)this + 18);
        if ( *(_WORD *)(v283 + 32) )
        {
          v284 = v283 + 72;
          *((_QWORD *)this + 18) = v284;
          *((_QWORD *)this + 25) = v284;
          v125 = **((unsigned int **)this + 19);
          goto LABEL_191;
        }
        v343 = v283 + 48;
LABEL_596:
        *((_QWORD *)this + 18) = v343;
        *((_QWORD *)this + 19) += 4LL;
        goto LABEL_22;
      case 102:
        v366 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v366;
        *v366 = 0;
        if ( *(_DWORD *)(*(_QWORD *)this + 1232LL)
          || VariantCopyInd(*((VARIANT **)this + 18), (const VARIANTARG *)(*(_QWORD *)this + 1208LL)) < 0 )
        {
          goto LABEL_643;
        }
        if ( (int)VAR::Import(*((VAR **)this + 18), *(struct CSession **)this) < 0 )
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
        v354 = *((_QWORD *)this + 18);
        *((_QWORD *)this + 23) = *(_QWORD *)(v354 + 16);
        v18 = v354 + 24;
        goto LABEL_21;
      case 108:
        v351 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v351;
        *v351 = 141;
        v352 = (int *)*((_QWORD *)this + 19);
        v353 = *v352;
        *((_QWORD *)this + 19) = v352 + 1;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = v353;
        *(_QWORD *)(*((_QWORD *)this + 18) + 16LL) = *((_QWORD *)this + 23);
        *((_QWORD *)this + 23) = *((_QWORD *)this + 18);
        goto LABEL_22;
      case 109:
        v358 = *((_QWORD *)this + 18);
        if ( *(_WORD *)v358 == 142 )
        {
          *((_QWORD *)this + 25) = v358;
          v359 = *((_QWORD *)this + 20) + *(int *)(v358 + 8);
          *((_QWORD *)this + 19) = v359;
          *((_QWORD *)this + 26) = v359;
        }
        v17 = v358 + 24;
        *((_QWORD *)this + 18) = v358 + 24;
        goto LABEL_20;
      case 110:
        v314 = *((_QWORD *)this + 18);
        if ( *(_WORD *)v314 == 142 )
        {
          v17 = v314 + 24;
          *((_QWORD *)this + 18) = v17;
          goto LABEL_20;
        }
        v315 = *(int *)(v314 + 8);
        *(_WORD *)v314 = 142;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = *((_DWORD *)this + 38) - *((_DWORD *)this + 40);
        v54 = v315;
LABEL_67:
        *((_QWORD *)this + 25) = *((_QWORD *)this + 18);
        v55 = v54 + *((_QWORD *)this + 20);
        *((_QWORD *)this + 19) = v55;
        *((_QWORD *)this + 26) = v55;
        goto LABEL_22;
      case 111:
        v361 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v361;
        *v361 = 0;
        v362 = (_WORD *)(*((_QWORD *)this + 18) - 24LL);
        *((_QWORD *)this + 18) = v362;
        *v362 = 141;
        v363 = (_DWORD *)*((_QWORD *)this + 19);
        v196 = *v363;
        v197 = (char *)(v363 + 1);
LABEL_292:
        *((_QWORD *)this + 19) = v197;
        *(_DWORD *)(*((_QWORD *)this + 18) + 8LL) = v196;
        goto LABEL_22;
      case 112:
        v364 = v515;
LABEL_637:
        if ( v364 )
        {
          v365 = *((_QWORD *)this + 18);
          *(_OWORD *)v364 = *(_OWORD *)v365;
          *((_QWORD *)v364 + 2) = *(_QWORD *)(v365 + 16);
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
        v411 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v411;
        v412 = (VARIANTARG *)(*(_QWORD *)this + 1208LL);
        if ( *(_WORD *)v411 != v412->vt || *(_DWORD *)(v411 + 8) != *(_DWORD *)(*(_QWORD *)this + 1216LL) )
        {
          VariantClear(v412);
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
        v367 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v367 *= 3;
        *(_WORD *)(v3 + 8 * v367) = 11;
        *(_WORD *)(v3 + 8 * v367 + 8) = -1;
        goto LABEL_22;
      case 118:
        v360 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v360 *= 3;
        *(_WORD *)(v3 + 8 * v360) = 11;
        *(_WORD *)(v3 + 8 * v360 + 8) = 0;
        goto LABEL_22;
      case 119:
        v350 = 3LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)(v3 + 8 * v350) = 1;
        goto LABEL_22;
      case 120:
        v239 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v240 = 3 * v239;
        *(_WORD *)(v3 + 8 * v240) = 3;
        v241 = (char *)*((_QWORD *)this + 19);
        LODWORD(v239) = *v241;
        *((_QWORD *)this + 19) = v241 + 1;
        *(_DWORD *)(v3 + 8 * v240 + 8) = v239;
        goto LABEL_22;
      case 121:
        v382 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v383 = 3 * v382;
        *(_WORD *)(v3 + 8 * v383) = 3;
        v384 = (_DWORD *)*((_QWORD *)this + 19);
        LODWORD(v382) = *v384;
        *((_QWORD *)this + 19) = v384 + 1;
        *(_DWORD *)(v3 + 8 * v383 + 8) = v382;
        goto LABEL_22;
      case 122:
        v413 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v413 *= 3;
        *(_WORD *)(v3 + 8 * v413) = 5;
        v414 = (__int64 *)*((_QWORD *)this + 19);
        v415 = *v414;
        *((_QWORD *)this + 19) = v414 + 1;
        *(_QWORD *)(v3 + 8 * v413 + 8) = v415;
        goto LABEL_22;
      case 123:
        v355 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v356 = *(unsigned int *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 7;
        v357 = CScriptRuntime::GetGcAlloc(this);
        v440 = GcAlloc::PvarAlloc(v357);
        if ( v440 )
        {
          v432 = 3 * v355;
          *(_WORD *)(v3 + 8 * v432) = 128;
          *(_QWORD *)(v3 + 8 * v432 + 8) = v440;
          v130 = v356;
          goto LABEL_194;
        }
        TypeProto = -2147024882;
        goto LABEL_36;
      case 124:
        v416 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v416 *= 3;
        *(_WORD *)(v4 + 8 * v416) = 11;
        *(_WORD *)(v4 + 8 * v416 + 8) = -1;
        goto LABEL_22;
      case 125:
        v417 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v417 *= 3;
        *(_WORD *)(v4 + 8 * v417) = 11;
        *(_WORD *)(v4 + 8 * v417 + 8) = 0;
        goto LABEL_22;
      case 126:
        v418 = 3LL * *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        *(_WORD *)(v4 + 8 * v418) = 1;
        goto LABEL_22;
      case 127:
        v419 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v420 = 3 * v419;
        *(_WORD *)(v4 + 8 * v420) = 3;
        v421 = (char *)*((_QWORD *)this + 19);
        LODWORD(v419) = *v421;
        *((_QWORD *)this + 19) = v421 + 1;
        *(_DWORD *)(v4 + 8 * v420 + 8) = v419;
        goto LABEL_22;
      case 128:
        v422 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v423 = 3 * v422;
        *(_WORD *)(v4 + 8 * v423) = 3;
        v424 = (_DWORD *)*((_QWORD *)this + 19);
        LODWORD(v422) = *v424;
        *((_QWORD *)this + 19) = v424 + 1;
        *(_DWORD *)(v4 + 8 * v423 + 8) = v422;
        goto LABEL_22;
      case 129:
        v425 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v425 *= 3;
        *(_WORD *)(v4 + 8 * v425) = 5;
        v426 = (__int64 *)*((_QWORD *)this + 19);
        v427 = *v426;
        *((_QWORD *)this + 19) = v426 + 1;
        *(_QWORD *)(v4 + 8 * v425 + 8) = v427;
        goto LABEL_22;
      case 130:
        v385 = *(__int16 *)v10;
        *((_QWORD *)this + 19) = v8 + 3;
        v386 = *(unsigned int *)(v8 + 3);
        *((_QWORD *)this + 19) = v8 + 7;
        v387 = CScriptRuntime::GetGcAlloc(this);
        v440 = GcAlloc::PvarAlloc(v387);
        if ( v440 )
        {
          v436 = 3 * v385;
          *(_WORD *)(v4 + 8 * v436) = 128;
          *(_QWORD *)(v4 + 8 * v436 + 8) = v440;
          v130 = v386;
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
          v470 = *(_OWORD *)(v3 + 8 * v107);
          v471 = *(_QWORD *)(v3 + 8 * v107 + 16);
          v486 = *(unsigned int **)this;
          v485 = &v470;
          v487 = *((_QWORD *)v486 + 122);
          *((_QWORD *)v486 + 122) = &v485;
          v483 = *(unsigned int **)this;
          v482 = &v480;
          v484 = *((_QWORD *)v483 + 122);
          *((_QWORD *)v483 + 122) = &v482;
          v480 = 3;
          LODWORD(v481) = v106;
          v454 = 0;
          v455 = 0;
          v108 = VAR::GetValue((VAR *)&v470, *(struct CSession **)this, &v454, (struct VAR *)&v470, 0x2000u);
          if ( v108 >= 0 )
          {
            if ( v454 )
            {
              v108 = VAR::GetValue((VAR *)&v480, *(struct CSession **)this, &v455, (struct VAR *)&v480, 0x2000u);
              if ( v108 >= 0 )
              {
                if ( v455 )
                {
                  if ( (unsigned int)VAR::FBstr(v454) && (unsigned int)VAR::FBstr(v455) )
                  {
                    v109 = (unsigned int)StrComp(
                                           *(struct CSession **)this,
                                           *((unsigned __int16 **)v454 + 1),
                                           *((unsigned __int16 **)v455 + 1)) >> 31;
                  }
                  else
                  {
                    if ( !(unsigned int)ConvertToScalarCore(v454, (struct VAR *)&v470, 5) )
                    {
                      v108 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v470, 0, -1);
                      goto LABEL_173;
                    }
                    if ( !(unsigned int)ConvertToScalarCore(v455, (struct VAR *)&v480, 5) )
                    {
                      v108 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v480, 0, -1);
                      goto LABEL_173;
                    }
                    if ( (unsigned int)FNan(*((double *)&v470 + 1)) || (unsigned int)FNan(v481) )
                    {
                      v109 = 0;
                    }
                    else
                    {
                      v109 = 0;
                      LOBYTE(v109) = v481 > *((double *)&v470 + 1);
                    }
                  }
                  VAR::SetBool((VAR *)&v470, v109);
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
            GCRootStack::Pop((GCRootStack *)(v483 + 236));
            GCRootStack::Pop((GCRootStack *)(v486 + 236));
            goto LABEL_36;
          }
          v97 = WORD4(v470) == 0xFFFF;
          GCRootStack::Pop((GCRootStack *)(v483 + 236));
          v98 = v486;
LABEL_155:
          GCRootStack::Pop((GCRootStack *)(v98 + 236));
          goto LABEL_156;
        }
        v97 = *(_DWORD *)(v3 + 8 * v107 + 8) < v106;
        goto LABEL_156;
      case 132:
        v74 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v440 = v74;
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
            *((_DWORD *)v440 + 2) = v139 + v138;
          }
          else
          {
            *((double *)v440 + 1) = (double)v139 + (double)v138;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( (unsigned int)FVtIn(*(unsigned __int16 *)(v3 + 8 * v75), 0x2083Cu)
          && (unsigned int)FVtIn(*(unsigned __int16 *)(v3 + 8 * v76), 0x2083Cu) )
        {
          v496 = *(__m128i *)(v3 + 8 * v75);
          v497 = *(_QWORD *)(v3 + 8 * v75 + 16);
          v494 = *(_OWORD *)(v3 + 8 * v76);
          v495 = *(_QWORD *)(v3 + 8 * v76 + 16);
          if ( (unsigned __int16)_mm_cvtsi128_si32(v496) != 5 )
            ConvertToScalarCore((struct VAR *)&v496, (struct VAR *)&v496, 5);
          if ( (_WORD)v494 != 5 )
            ConvertToScalarCore((struct VAR *)&v494, (struct VAR *)&v494, 5);
          VAR::SetNumber(v440, *((double *)&v494 + 1) + *(double *)&v496.m128i_i64[1]);
          goto LABEL_22;
        }
        v472 = *(_OWORD *)(v3 + 8 * v76);
        v473 = *(_QWORD *)(v3 + 8 * v76 + 16);
        v466 = *(_OWORD *)(v3 + 8 * v75);
        v467 = *(_QWORD *)(v3 + 8 * v75 + 16);
        v502 = *(unsigned int **)this;
        v501 = &v472;
        v503 = *((_QWORD *)v502 + 122);
        *((_QWORD *)v502 + 122) = &v501;
        v499 = *(unsigned int **)this;
        v498 = &v466;
        v500 = *((_QWORD *)v499 + 122);
        *((_QWORD *)v499 + 122) = &v498;
        v446 = 0;
        v443 = 0;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v466) )
        {
          v77 = VAR::PvarCutHeap((VAR *)&v466);
          v446 = v77;
        }
        else
        {
          if ( (int)VAR::GetValue((VAR *)&v466, *(struct CSession **)this, &v446, (struct VAR *)&v466, 0) < 0 )
            goto LABEL_612;
          v77 = v446;
        }
        if ( !v77 )
          goto LABEL_612;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v472) )
        {
          v78 = VAR::PvarCutHeap((VAR *)&v472);
          v443 = v78;
        }
        else
        {
          if ( (int)VAR::GetValue((VAR *)&v472, *(struct CSession **)this, &v443, (struct VAR *)&v472, 0) < 0 )
            goto LABEL_612;
          v78 = v443;
        }
        if ( !v78 )
          goto LABEL_612;
        if ( (unsigned int)VAR::FStr(v446) )
        {
          if ( !(unsigned int)VAR::FStr(v443)
            && (int)ConvertToString(*(struct CSession **)this, &v443, (struct VAR *)&v472, 0) < 0 )
          {
            goto LABEL_612;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v443) )
          {
            if ( (unsigned int)ConvertToScalarCore(v446, (struct VAR *)&v466, 5) )
            {
              if ( (unsigned int)ConvertToScalarCore(v443, (struct VAR *)&v472, 5) )
                VAR::SetNumber((VAR *)&v466, *((double *)&v472 + 1) + *((double *)&v466 + 1));
              else
                CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v472, 0, -1);
            }
            else
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v466, 0, -1);
            }
            goto LABEL_612;
          }
          if ( (int)ConvertToString(*(struct CSession **)this, &v446, (struct VAR *)&v466, 0) < 0 )
          {
LABEL_612:
            v346 = v440;
            *(_OWORD *)v440 = v466;
            *((_QWORD *)v346 + 2) = v467;
            GCRootStack::Pop((GCRootStack *)(v499 + 236));
            GCRootStack::Pop((GCRootStack *)(v502 + 236));
            goto LABEL_22;
          }
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)&v466, v446, v443);
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
        v468 = *(_OWORD *)(v3 + 8 * v94);
        v469 = *(_QWORD *)(v3 + 8 * v94 + 16);
        v476 = *(_OWORD *)(v3 + 24 * v93);
        v477 = *(_QWORD *)(v3 + 24 * v93 + 16);
        v492 = *(unsigned int **)this;
        v491 = &v468;
        v493 = *((_QWORD *)v492 + 122);
        *((_QWORD *)v492 + 122) = &v491;
        v489 = *(unsigned int **)this;
        v488 = &v476;
        v490 = *((_QWORD *)v489 + 122);
        *((_QWORD *)v489 + 122) = &v488;
        v456 = 0;
        v457 = 0;
        if ( (_WORD)v468 == 5 && (_WORD)v476 == 5 )
          goto LABEL_149;
        v96 = VAR::GetValue((VAR *)&v468, *(struct CSession **)this, &v456, (struct VAR *)&v468, 0x2000u);
        if ( v96 < 0 )
          goto LABEL_153;
        if ( !v456 )
        {
          v96 = -2146828281;
          goto LABEL_153;
        }
        v96 = VAR::GetValue((VAR *)&v476, *(struct CSession **)this, &v457, (struct VAR *)&v476, 0x2000u);
        if ( v96 < 0 )
          goto LABEL_153;
        if ( !v457 )
        {
          v96 = -2146828281;
          goto LABEL_153;
        }
        if ( (unsigned int)VAR::FBstr(v456) && (unsigned int)VAR::FBstr(v457) )
        {
          v95 = (unsigned int)StrComp(
                                *(struct CSession **)this,
                                *((unsigned __int16 **)v456 + 1),
                                *((unsigned __int16 **)v457 + 1)) >> 31;
        }
        else
        {
          if ( !(unsigned int)ConvertToScalarCore(v456, (struct VAR *)&v468, 5) )
          {
            v96 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v468, 0, -1);
            goto LABEL_153;
          }
          if ( !(unsigned int)ConvertToScalarCore(v457, (struct VAR *)&v476, 5) )
          {
            v96 = CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v476, 0, -1);
            goto LABEL_153;
          }
LABEL_149:
          if ( (unsigned int)FNan(*((double *)&v468 + 1)) || (unsigned int)FNan(*((double *)&v476 + 1)) )
          {
            v95 = 0;
          }
          else
          {
            v95 = 0;
            LOBYTE(v95) = *((double *)&v476 + 1) > *((double *)&v468 + 1);
          }
        }
        VAR::SetBool((VAR *)&v468, v95);
        v96 = 0;
LABEL_153:
        TypeProto = v96;
        if ( v96 < 0 )
        {
          GCRootStack::Pop((GCRootStack *)(v489 + 236));
          GCRootStack::Pop((GCRootStack *)(v492 + 236));
          goto LABEL_36;
        }
        v97 = WORD4(v468) == 0xFFFF;
        GCRootStack::Pop((GCRootStack *)(v489 + 236));
        v98 = v492;
        goto LABEL_155;
      case 134:
        v229 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v229;
        v230 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v440 = v230;
        *(_OWORD *)v229 = *(_OWORD *)v230;
        *(_QWORD *)(v229 + 16) = *((_QWORD *)v230 + 2);
        v231 = (double *)v440;
        goto LABEL_328;
      case 135:
        v368 = *((_QWORD *)this + 18) - 24LL;
        *((_QWORD *)this + 18) = v368;
        v369 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v440 = v369;
        *(_OWORD *)v368 = *(_OWORD *)v369;
        *(_QWORD *)(v368 + 16) = *((_QWORD *)v369 + 2);
        v370 = v440;
        goto LABEL_658;
      case 136:
        v231 = (double *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v440 = (VAR *)v231;
LABEL_328:
        if ( *(_WORD *)v231 == 3 )
        {
          v232 = *((_DWORD *)v231 + 2);
          *((_DWORD *)v231 + 2) = v232 + 1;
          if ( *((_DWORD *)v440 + 2) < v232 )
          {
            *((double *)v440 + 1) = (double)v232 + 1.0;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v231 == 5 )
          goto LABEL_381;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v231, (struct VAR *)v231, 5, 1);
        if ( TypeProto >= 0 )
        {
          v231 = (double *)v440;
          goto LABEL_381;
        }
        goto LABEL_36;
      case 137:
        v370 = (VAR *)(v3 + 24LL * *(__int16 *)v10);
        *((_QWORD *)this + 19) = v8 + 3;
        v440 = v370;
LABEL_658:
        if ( *(_WORD *)v370 == 3 )
        {
          v371 = *((_DWORD *)v370 + 2);
          *((_DWORD *)v370 + 2) = v371 - 1;
          if ( *((_DWORD *)v440 + 2) > v371 )
          {
            *((double *)v440 + 1) = (double)v371 - 1.0;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v370 == 5 )
          goto LABEL_728;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v370, v370, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v370 = v440;
LABEL_728:
        VAR::SetNumber(v370, *((double *)v370 + 1) - 1.0);
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
        v440 = v59;
        if ( *(_WORD *)v59 == 3 )
        {
          v261 = *((_DWORD *)v59 + 2);
          *((_DWORD *)v59 + 2) = v261 + v57;
          if ( *((_DWORD *)v440 + 2) < v57 != (unsigned int)v261 >> 31 )
          {
            *((double *)v440 + 1) = (double)v261 + (double)v57;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( (unsigned int)FVtIn(*(unsigned __int16 *)v59, 0x2083Cu) )
        {
          v262 = (double *)v440;
          if ( *(_WORD *)v440 != 5 )
          {
            ConvertToScalarCore(v440, v440, 5);
            v262 = (double *)v440;
          }
          VAR::SetNumber((VAR *)v262, (double)v57 + v262[1]);
          goto LABEL_22;
        }
        v505 = *(unsigned int **)this;
        v504 = &v474;
        v506 = *((_QWORD *)v505 + 122);
        *((_QWORD *)v505 + 122) = &v504;
        v474 = 3;
        LODWORD(v475) = v57;
        v60 = (double *)v440;
        v447 = 0;
        v444 = 0;
        if ( (unsigned int)VAR::IsAStringObj(v440) )
        {
          v61 = VAR::PvarCutHeap((VAR *)v60);
          v447 = v61;
        }
        else
        {
          if ( (int)VAR::GetValue((VAR *)v60, *(struct CSession **)this, &v447, (struct VAR *)v60, 0) < 0 )
            goto LABEL_219;
          v61 = v447;
        }
        if ( !v61 )
          goto LABEL_219;
        if ( (unsigned int)VAR::IsAStringObj((VAR *)&v474) )
        {
          v62 = VAR::PvarCutHeap((VAR *)&v474);
          v444 = v62;
        }
        else
        {
          if ( (int)VAR::GetValue((VAR *)&v474, *(struct CSession **)this, &v444, (struct VAR *)&v474, 0) < 0 )
            goto LABEL_219;
          v62 = v444;
        }
        if ( !v62 )
          goto LABEL_219;
        if ( (unsigned int)VAR::FStr(v447) )
        {
          if ( !(unsigned int)VAR::FStr(v444)
            && (int)ConvertToString(*(struct CSession **)this, &v444, (struct VAR *)&v474, 0) < 0 )
          {
            goto LABEL_219;
          }
        }
        else
        {
          if ( !(unsigned int)VAR::FStr(v444) )
          {
            if ( (unsigned int)ConvertToScalarCore(v447, (struct VAR *)v60, 5) )
            {
              if ( (unsigned int)ConvertToScalarCore(v444, (struct VAR *)&v474, 5) )
                VAR::SetNumber((VAR *)v60, v475 + v60[1]);
              else
                CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)&v474, 0, -1);
            }
            else
            {
              CSession::RecordHr(*(CSession **)this, -2146823287, (struct VAR *)v60, 0, -1);
            }
            goto LABEL_219;
          }
          if ( (int)ConvertToString(*(struct CSession **)this, &v447, (struct VAR *)v60, 0) < 0 )
          {
LABEL_219:
            GCRootStack::Pop((GCRootStack *)(v505 + 236));
            goto LABEL_22;
          }
        }
        ConcatStrs(*(struct CSession **)this, (struct VAR *)v60, v447, v444);
        goto LABEL_219;
      case 140:
        v388 = (char)*v10;
        v389 = (__int16 *)(v8 + 2);
        goto LABEL_674;
      case 141:
        v388 = *(_DWORD *)v10;
        v389 = (__int16 *)(v8 + 5);
LABEL_674:
        *((_QWORD *)this + 19) = v389;
        v390 = (VAR *)(v3 + 24LL * *v389);
        *((_QWORD *)this + 19) = v389 + 1;
        v440 = v390;
        if ( *(_WORD *)v390 == 3 )
        {
          v391 = *((_DWORD *)v390 + 2);
          *((_DWORD *)v390 + 2) = v391 - v388;
          if ( *((_DWORD *)v440 + 2) < v391 != v388 > 0 )
          {
            *((double *)v440 + 1) = (double)v391 - (double)v388;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v390 == 5 )
          goto LABEL_733;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v390, v390, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v390 = v440;
LABEL_733:
        VAR::SetNumber(v390, *((double *)v390 + 1) - (double)v388);
        goto LABEL_22;
      case 142:
        v392 = (char)*v10;
        v393 = (__int16 *)(v8 + 2);
        goto LABEL_678;
      case 143:
        v392 = *(_DWORD *)v10;
        v393 = (__int16 *)(v8 + 5);
LABEL_678:
        *((_QWORD *)this + 19) = v393;
        v394 = (VAR *)(v3 + 24LL * *v393);
        *((_QWORD *)this + 19) = v393 + 1;
        v440 = v394;
        if ( *(_WORD *)v394 == 3 )
        {
          v395 = *((_DWORD *)v394 + 2);
          *((_DWORD *)v394 + 2) = v392 * v395;
          if ( (v392 ^ v395 ^ *((_DWORD *)v440 + 2)) < 0 || v395 && v392 != *((_DWORD *)v440 + 2) / v395 )
          {
            *((double *)v440 + 1) = (double)v395 * (double)v392;
            *(_WORD *)v440 = 5;
          }
          goto LABEL_22;
        }
        if ( *(_WORD *)v394 == 5 )
          goto LABEL_738;
        TypeProto = ConvertToScalar(*(struct CSession **)this, v394, v394, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v394 = v440;
LABEL_738:
        VAR::SetNumber(v394, (double)v392 * *((double *)v394 + 1));
        goto LABEL_22;
      case 144:
        v396 = (char)*v10;
        v397 = (__int16 *)(v8 + 2);
        goto LABEL_684;
      case 145:
        v396 = *(_DWORD *)v10;
        v397 = (__int16 *)(v8 + 5);
LABEL_684:
        *((_QWORD *)this + 19) = v397;
        v398 = (double *)(v3 + 24LL * *v397);
        *((_QWORD *)this + 19) = v397 + 1;
        v440 = (VAR *)v398;
        if ( *(_WORD *)v398 == 5 )
          goto LABEL_687;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v398, (struct VAR *)v398, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v398 = (double *)v440;
LABEL_687:
        v399 = CScriptRuntime::SafeDivide(this, v398[1], (double)v396);
        VAR::SetNumber(v440, v399);
        goto LABEL_22;
      case 146:
        v400 = (char)*v10;
        v401 = (__int16 *)(v8 + 2);
        goto LABEL_689;
      case 147:
        v400 = *(_DWORD *)v10;
        v401 = (__int16 *)(v8 + 5);
LABEL_689:
        *((_QWORD *)this + 19) = v401;
        v402 = (double *)(v3 + 24LL * *v401);
        *((_QWORD *)this + 19) = v401 + 1;
        v440 = (VAR *)v402;
        if ( *(_WORD *)v402 == 5 )
          goto LABEL_692;
        TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v402, (struct VAR *)v402, 5, 1);
        if ( TypeProto < 0 )
          goto LABEL_36;
        v402 = (double *)v440;
LABEL_692:
        v403 = DblMod(v402[1], (double)v400);
        VAR::SetNumber(v440, v403);
        goto LABEL_22;
      case 148:
        v325 = (char)*v10;
        v326 = (__int16 *)(v8 + 2);
        goto LABEL_560;
      case 149:
        v325 = *(_DWORD *)v10;
        v326 = (__int16 *)(v8 + 5);
LABEL_560:
        *((_QWORD *)this + 19) = v326;
        v327 = (VAR *)(v3 + 24LL * *v326);
        *((_QWORD *)this + 19) = v326 + 1;
        v440 = v327;
        if ( *(_WORD *)v327 == 3 )
        {
          *((_DWORD *)v327 + 2) &= v325;
        }
        else
        {
          if ( *(_WORD *)v327 == 5 )
          {
            *(_WORD *)v327 = 3;
            *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v327, v327, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v440 + 2) &= v325;
        }
        goto LABEL_22;
      case 150:
        v328 = (char)*v10;
        v329 = (__int16 *)(v8 + 2);
        goto LABEL_565;
      case 151:
        v328 = *(_DWORD *)v10;
        v329 = (__int16 *)(v8 + 5);
LABEL_565:
        *((_QWORD *)this + 19) = v329;
        v330 = (VAR *)(v3 + 24LL * *v329);
        *((_QWORD *)this + 19) = v329 + 1;
        v440 = v330;
        if ( *(_WORD *)v330 == 3 )
        {
          *((_DWORD *)v330 + 2) ^= v328;
        }
        else
        {
          if ( *(_WORD *)v330 == 5 )
          {
            *(_WORD *)v330 = 3;
            *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v330, v330, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v440 + 2) ^= v328;
        }
        goto LABEL_22;
      case 152:
        v331 = (char)*v10;
        v332 = (__int16 *)(v8 + 2);
        goto LABEL_570;
      case 153:
        v331 = *(_DWORD *)v10;
        v332 = (__int16 *)(v8 + 5);
LABEL_570:
        *((_QWORD *)this + 19) = v332;
        v333 = (VAR *)(v3 + 24LL * *v332);
        *((_QWORD *)this + 19) = v332 + 1;
        v440 = v333;
        if ( *(_WORD *)v333 == 3 )
        {
          *((_DWORD *)v333 + 2) |= v331;
        }
        else
        {
          if ( *(_WORD *)v333 == 5 )
          {
            *(_WORD *)v333 = 3;
            *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v333, v333, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v440 + 2) |= v331;
        }
        goto LABEL_22;
      case 154:
        LOBYTE(v334) = *v10;
        v335 = (__int16 *)(v8 + 2);
        goto LABEL_575;
      case 155:
        v334 = *(_DWORD *)v10;
        v335 = (__int16 *)(v8 + 5);
LABEL_575:
        *((_QWORD *)this + 19) = v335;
        v336 = v334 & 0x1F;
        v337 = (VAR *)(v3 + 24LL * *v335);
        *((_QWORD *)this + 19) = v335 + 1;
        v440 = v337;
        if ( *(_WORD *)v337 == 3 )
        {
          *((_DWORD *)v337 + 2) <<= v336;
        }
        else
        {
          if ( *(_WORD *)v337 == 5 )
          {
            *(_WORD *)v337 = 3;
            *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, v337, v337, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((_DWORD *)v440 + 2) <<= v336;
        }
        goto LABEL_22;
      case 156:
        LOBYTE(v338) = *v10;
        v339 = (__int16 *)(v8 + 2);
        goto LABEL_580;
      case 157:
        v338 = *(_DWORD *)v10;
        v339 = (__int16 *)(v8 + 5);
LABEL_580:
        *((_QWORD *)this + 19) = v339;
        v340 = v338 & 0x1F;
        v341 = (int *)(v3 + 24LL * *v339);
        *((_QWORD *)this + 19) = v339 + 1;
        v440 = (VAR *)v341;
        if ( *(_WORD *)v341 == 3 )
        {
          v341[2] >>= v340;
        }
        else
        {
          if ( *(_WORD *)v341 == 5 )
          {
            *(_WORD *)v341 = 3;
            *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
          }
          else
          {
            TypeProto = ConvertToScalar(*(struct CSession **)this, (struct VAR *)v341, (struct VAR *)v341, 3, 1);
            if ( TypeProto < 0 )
              goto LABEL_22;
          }
          *((int *)v440 + 2) >>= v340;
        }
        goto LABEL_22;
      case 158:
        LOBYTE(v404) = *v10;
        v405 = (__int16 *)(v8 + 2);
        goto LABEL_704;
      case 159:
        v404 = *(_DWORD *)v10;
        v405 = (__int16 *)(v8 + 5);
LABEL_704:
        *((_QWORD *)this + 19) = v405;
        v406 = v404 & 0x1F;
        v407 = (VAR *)(v3 + 24LL * *v405);
        *((_QWORD *)this + 19) = v405 + 1;
        v440 = v407;
        if ( *(_WORD *)v407 == 3 )
          goto LABEL_708;
        if ( *(_WORD *)v407 == 5 )
        {
          *(_WORD *)v407 = 3;
          *((_DWORD *)v440 + 2) = (int)*((double *)v440 + 1);
        }
        else
        {
          TypeProto = ConvertToScalar(*(struct CSession **)this, v407, v407, 3, 1);
          if ( TypeProto < 0 )
            goto LABEL_22;
        }
        v407 = v440;
LABEL_708:
        v408 = *((_DWORD *)v407 + 2);
        if ( v406 || v408 >= 0 )
        {
          *((_DWORD *)v407 + 2) = (unsigned int)v408 >> v406;
        }
        else
        {
          *((double *)v407 + 1) = (double)v408;
          *(_WORD *)v440 = 5;
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
0x180026230  mov     r11, rsp
0x180026233  mov     [r11+10h], rdx
0x180026237  mov     [r11+8], rcx
0x18002623b  push    rbx
0x18002623c  push    rsi
0x18002623d  push    rdi
0x18002623e  push    r12
0x180026240  push    r13
0x180026242  push    r14
0x180026244  push    r15
0x180026246  sub     rsp, 320h
0x18002624d  mov     r15, rcx
0x180026250  xor     r12d, r12d
0x180026253  mov     [r11+18h], r12d
0x180026257  mov     r13, [rcx+100h]
0x18002625e  mov     r14, [rcx+108h]
0x180026265  mov     [rsp+358h+var_1B0], r14
0x18002626d  xorps   xmm0, xmm0
0x180026270  xor     eax, eax
0x180026272  movups  [rsp+358h+var_2D8], xmm0
0x18002627a  mov     [r11-2C8h], rax
0x180026281  mov     [rsp+358h+var_318], r12
0x180026286  mov     [rsp+358h+var_310], r12
0x18002628b  mov     [r11+20h], r12d
0x18002628f  mov     [r11-2A4h], r12d
0x180026296  mov     rax, [rcx+38h]
0x18002629a  mov     rcx, [rax]
0x18002629d  mov     rsi, [rcx+38h]
0x1800262a1  mov     [rsp+358h+var_1A8], rsi
0x1800262a9  mov     rcx, [r15+90h]
0x1800262b0  mov     [r15+88h], rcx
0x1800262b7  mov     [r11-2A8h], r12d
0x1800262be  lea     rax, [r11+10h]
0x1800262c2  mov     [r15+160h], rax
0x1800262c9  lea     rax, [rsp+358h+var_308]
0x1800262ce  mov     [r15+158h], rax
0x1800262d5  mov     rax, [r15+0F8h]
0x1800262dc  mov     [r15+0F0h], rax
0x1800262e3  mov     rax, [r15+0A0h]
0x1800262ea  mov     [r15+98h], rax
0x1800262f1  mov     dword ptr [r15+0A8h], 0FFFFFFFFh
0x1800262fc  mov     dword ptr [r15+150h], 0FFFFFFFEh
0x180026307  mov     [r15+0C8h], rcx
0x18002630e  mov     [r15+0D0h], rax
0x180026315  test    rdx, rdx
0x180026318  jz      loc_18002BB31
0x18002631e  mov     [rdx], r12w
0x180026322  or      dword ptr [r15+130h], 2
0x18002632a  mov     r8, [r15]
0x18002632d  mov     r8, [r8+3D8h]; struct ThreadGlobals *
0x180026334  mov     rdx, [r15+8]; struct COleScript *
0x180026338  lea     rcx, [rsp+358h+var_58]; this
0x180026340  call    ??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@PEAVThreadGlobals@@@Z; TLS_NoDestructor::TLS_NoDestructor(COleScript *,ThreadGlobals *)
0x180026345  mov     word ptr [rsp+358h+var_2C0], r12w
0x18002634e  mov     rcx, [r15]
0x180026351  mov     [rsp+358h+var_A8], rcx
0x180026359  lea     rax, [rsp+358h+var_2C0]
0x180026361  mov     [rsp+358h+var_B0], rax
0x180026369  mov     rax, [rcx+3D0h]
0x180026370  mov     [rsp+358h+var_A0], rax
0x180026378  lea     rax, [rsp+358h+var_B0]
0x180026380  mov     [rcx+3D0h], rax
0x180026387  mov     r8d, 80h
0x18002638d  mov     r11d, 1
0x180026393  mov     r10d, 3
0x180026399  mov     ebx, 8Dh
0x18002639e  mov     edi, 5
0x1800263a3  lea     rdx, __ImageBase
0x1800263aa  nop     word ptr [rax+rax+00h]
0x1800263b0  mov     rax, [r15+98h]
0x1800263b7  movzx   ecx, byte ptr [rax]
0x1800263ba  lea     r9, [rax+1]
0x1800263be  mov     [r15+98h], r9
0x1800263c5  cmp     ecx, 9Fh; switch 160 cases
0x1800263cb  ja      def_1800263DB; jumptable 00000001800263DB default case
0x1800263d1  mov     ecx, ds:(jpt_1800263DB - 180000000h)[rdx+rcx*4]
0x1800263d8  add     rcx, rdx
0x1800263db  jmp     rcx; switch jump
0x1800263dd  movzx   ecx, byte ptr [r9]; jumptable 00000001800263DB case 3
0x1800263e1  lea     rax, [r9+1]
0x1800263e5  mov     [r15+98h], rax
0x1800263ec  mov     [r15+0A8h], ecx
0x1800263f3  mov     rcx, [r15]; this
0x1800263f6  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x1800263fb  test    eax, eax
0x1800263fd  jnz     loc_18002A1A5
0x180026403  mov     rcx, [r15+78h]
0x180026407  cmp     dword ptr [rcx+8], 0
0x18002640b  jnz     loc_1800278C5
0x180026411  mov     rcx, [r15]; this
0x180026414  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x180026419  mov     [rsp+358h+arg_10], eax
0x180026420  test    eax, eax
0x180026422  jns     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x180026428  mov     edx, [rsp+358h+arg_10]; int
0x18002642f  test    edx, edx
0x180026431  jns     loc_18002BAE1
0x180026437  mov     rcx, [r15]; this
0x18002643a  call    ?ReportError@CSession@@QEAAJJ@Z; CSession::ReportError(long)
0x18002643f  mov     [rsp+358h+arg_10], eax
0x180026446  jmp     loc_18002BAE1
0x18002644b  mov     rdi, [r15+90h]; jumptable 00000001800263DB case 70
0x180026452  movzx   eax, word ptr [rdi+18h]
0x180026456  cmp     r10w, ax
0x18002645a  jz      loc_180028BC2
0x180026460  mov     [rsp+358h+var_280], r12
0x180026468  mov     [rsp+358h+var_278], r12
0x180026470  mov     esi, 5
0x180026475  cmp     si, ax
0x180026478  jnz     loc_1800270DB
0x18002647e  cmp     si, [rdi]
0x180026481  jnz     loc_1800270DB
0x180026487  movsd   xmm0, qword ptr [rdi+20h]; double
0x18002648c  call    ?FNan@@YAHN@Z; FNan(double)
0x180026491  test    eax, eax
0x180026493  jnz     loc_1800280F2
0x180026499  movsd   xmm0, qword ptr [rdi+8]; double
0x18002649e  call    ?FNan@@YAHN@Z; FNan(double)
0x1800264a3  test    eax, eax
0x1800264a5  jnz     loc_1800280F2
0x1800264ab  mov     edx, r12d
0x1800264ae  movsd   xmm0, qword ptr [rdi+8]
0x1800264b3  comisd  xmm0, qword ptr [rdi+20h]
0x1800264b8  setnbe  dl; int
0x1800264bb  lea     rcx, [rdi+18h]; this
0x1800264bf  call    ?SetBool@VAR@@QEAAXH@Z; VAR::SetBool(int)
0x1800264c4  mov     eax, r12d
0x1800264c7  mov     [rsp+358h+arg_10], eax
0x1800264ce  test    eax, eax
0x1800264d0  js      loc_18002661D
0x1800264d6  mov     rax, [r15+90h]
0x1800264dd  add     rax, 18h
0x1800264e1  mov     [r15+90h], rax
0x1800264e8  mov     r14, [rsp+358h+var_1B0]; jumptable 00000001800263DB cases 0,2,99,100
0x1800264f0  mov     rsi, [rsp+358h+var_1A8]
0x1800264f8  jmp     loc_180026387
0x1800264fd  mov     ecx, [r9]; jumptable 00000001800263DB case 34
0x180026500  mov     rsi, [r15+0B0h]
0x180026507  add     rsi, rcx
0x18002650a  lea     rax, [r9+4]
0x18002650e  mov     [r15+98h], rax
0x180026515  mov     rcx, [r15+90h]; this
0x18002651c  cmp     r8w, [rcx]
0x180026520  jnz     loc_1800273D2
0x180026526  mov     rcx, [rcx+8]; this
0x18002652a  mov     [rsp+358h+var_318], rcx
0x18002652f  call    ?FCanCastToObj@VAR@@QEAAHXZ; VAR::FCanCastToObj(void)
0x180026534  test    eax, eax
0x180026536  jz      loc_1800290D8
0x18002653c  mov     rax, [r15+90h]
0x180026543  movups  xmm0, xmmword ptr [rax]
0x180026546  movaps  [rsp+358h+var_78], xmm0
0x18002654e  movsd   xmm1, qword ptr [rax+10h]
0x180026553  movsd   [rsp+358h+var_68], xmm1
0x18002655c  lea     rdx, [rsp+358h+var_78]
0x180026564  mov     rcx, r15
0x180026567  call    ?IsGlobalBasedAndCanOptimizeGlobalLookup@CScriptRuntime@@QEAA_NVVAR@@@Z; CScriptRuntime::IsGlobalBasedAndCanOptimizeGlobalLookup(VAR)
0x18002656c  test    al, al
0x18002656e  jnz     loc_180027A26
0x180026574  mov     rcx, [r15+90h]
0x18002657b  mov     rax, [rsp+358h+var_318]
0x180026580  mov     edx, 84h
0x180026585  mov     [rcx], dx
0x180026588  mov     [rcx+8], rax
0x18002658c  mov     [rcx+10h], rsi
0x180026590  jmp     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x180026595  mov     ecx, [r9]; jumptable 00000001800263DB case 28
0x180026598  mov     rdi, [r15+0B0h]
0x18002659f  add     rdi, rcx
0x1800265a2  lea     rax, [r9+4]
0x1800265a6  mov     [r15+98h], rax
0x1800265ad  add     qword ptr [r15+90h], 0FFFFFFFFFFFFFFE8h
0x1800265b5  mov     rcx, [r15+90h]
0x1800265bc  mov     [rcx], r12w
0x1800265c0  mov     rbx, [r15+90h]
0x1800265c7  mov     rdx, rdi; unsigned __int16 *
0x1800265ca  lea     rcx, [rsp+358h+var_2D8]; this
0x1800265d2  call    ?InitFromSymbol@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromSymbol(ushort const *)
0x1800265d7  xor     r9d, r9d; struct VAR *
0x1800265da  mov     r8, rbx; struct VAR *
0x1800265dd  mov     rdx, rax; struct SYM *
0x1800265e0  mov     rcx, r15; this
0x1800265e3  call    ?GetVarVal@CScriptRuntime@@AEAAJPEAUSYM@@PEAVVAR@@1@Z; CScriptRuntime::GetVarVal(SYM *,VAR *,VAR *)
0x1800265e8  mov     [rsp+358h+arg_10], eax
0x1800265ef  test    eax, eax
0x1800265f1  jns     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x1800265f7  cmp     eax, 86664004h
0x1800265fc  jz      short loc_18002661D
0x1800265fe  mov     r9, rdi; Src
0x180026601  xor     r8d, r8d; struct VAR *
0x180026604  mov     edx, eax; int
0x180026606  mov     dword ptr [rsp+358h+pvarg], 0FFFFFFFFh; int
0x18002660e  mov     rcx, [r15]; this
0x180026611  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x180026616  mov     [rsp+358h+arg_10], eax
0x18002661d  mov     edi, 1
0x180026622  cmp     [rsp+358h+arg_10], 80020102h
0x18002662d  jnz     loc_18002B769
0x180026633  mov     ebx, 8Dh
0x180026638  mov     rdx, [r15+0B8h]
0x18002663f  cmp     rdx, [r15+0C0h]
0x180026646  jz      loc_18002BAD6
0x18002664c  cmp     bx, [rdx]
0x18002664f  jnz     loc_180026428
0x180026655  mov     ebx, [r15+130h]
0x18002665c  mov     eax, ebx
0x18002665e  or      eax, 4
0x180026661  mov     [r15+130h], eax
0x180026668  mov     edx, [rdx+8]; int
0x18002666b  mov     rcx, r15; this
0x18002666e  call    ?SetNextStatement@CScriptRuntime@@QEAAJJ@Z; CScriptRuntime::SetNextStatement(long)
0x180026673  and     ebx, 0FFFFFFFCh
0x180026676  shl     ebx, 1Dh
0x180026679  sar     ebx, 1Dh
0x18002667c  mov     eax, ebx
0x18002667e  xor     eax, [r15+130h]
0x180026685  and     eax, 0FFFFFFFBh
0x180026688  xor     eax, ebx
0x18002668a  mov     [r15+130h], eax
0x180026691  mov     [rsp+358h+arg_10], r12d
0x180026699  jmp     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x18002669e  movzx   r8d, word ptr [r9]; jumptable 00000001800263DB case 39
0x1800266a2  lea     rax, [r9+2]
0x1800266a6  mov     [r15+98h], rax
0x1800266ad  mov     rdx, [r15+90h]
0x1800266b4  lea     rbx, [r8+r8*2]
0x1800266b8  lea     rcx, [rdx+rbx*8]; this
0x1800266bc  mov     [rsp+358h+var_318], rcx
0x1800266c1  mov     [rsp+358h+var_320], r12; struct VAR *
0x1800266c6  mov     [rsp+358h+var_328], rdx; struct VAR *
0x1800266cb  mov     dword ptr [rsp+358h+var_330], r8d; int
0x1800266d0  lea     rax, [rsp+358h+var_2C0]
0x1800266d8  mov     [rsp+358h+pvarg], rax; struct VAR *
0x1800266dd  mov     r9d, 4000h; unsigned int
0x1800266e3  xor     r8d, r8d; int
0x1800266e6  mov     rdx, [r15]; struct CSession *
0x1800266e9  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x1800266ee  mov     [rsp+358h+arg_10], eax
0x1800266f5  test    eax, eax
0x1800266f7  js      loc_18002661D
0x1800266fd  mov     rax, [r15+90h]
0x180026704  lea     rcx, [rax+rbx*8]
0x180026708  mov     [r15+90h], rcx
0x18002670f  movups  xmm0, [rsp+358h+var_2C0]
0x180026717  movups  xmmword ptr [rcx], xmm0
0x18002671a  movsd   xmm1, [rsp+358h+var_2B0]
0x180026723  movsd   qword ptr [rcx+10h], xmm1
0x180026728  jmp     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x18002672d  mov     rcx, [r15+90h]; jumptable 00000001800263DB case 57
0x180026734  call    ?FTrue@VAR@@QEAAHXZ; VAR::FTrue(void)
0x180026739  test    eax, eax
0x18002673b  jnz     loc_180026BD3
0x180026741  mov     rax, [r15+98h]
0x180026748  mov     edx, [rax]
0x18002674a  add     rdx, [r15+0A0h]
0x180026751  mov     [r15+98h], rdx
0x180026758  mov     [r15+0D0h], rdx
0x18002675f  add     qword ptr [r15+90h], 18h
0x180026767  mov     rax, [r15+90h]
0x18002676e  mov     [r15+0C8h], rax
0x180026775  jmp     loc_1800264E8; jumptable 00000001800263DB cases 0,2,99,100
0x18002677a  movzx   r11d, word ptr [r9]; jumptable 00000001800263DB case 35
0x18002677e  lea     rax, [r9+2]
0x180026782  mov     [r15+98h], rax
0x180026789  lea     rbx, [r11+r11*2]
0x18002678d  mov     rax, [r15+90h]
0x180026794  lea     rcx, [rax+rbx*8]; this
0x180026798  mov     [rsp+358h+var_318], rcx
0x18002679d  mov     eax, 400Ch
0x1800267a2  cmp     [rcx], ax
0x1800267a5  jz      loc_180027B16
0x1800267ab  mov     word ptr [rsp+358h+var_2C0], r12w
0x1800267b4  mov     rdx, [r15+98h]
0x1800267bb  lea     r8, [rsp+358h+var_2C0]
0x1800267c3  cmp     byte ptr [rdx], 42h ; 'B'
0x1800267c6  cmovz   r8, r12
0x1800267ca  mov     r9d, 3
0x1800267d0  test    r11w, r11w
0x1800267d4  mov     edi, 1
0x1800267d9  cmovz   r9d, edi; unsigned int
0x1800267dd  mov     [rsp+358h+var_320], r12; struct VAR *
0x1800267e2  mov     rax, [r15+90h]
0x1800267e9  mov     [rsp+358h+var_328], rax; struct VAR *
0x1800267ee  mov     dword ptr [rsp+358h+var_330], r11d; int
0x1800267f3  mov     [rsp+358h+pvarg], r8; struct VAR *
0x1800267f8  xor     r8d, r8d; int
0x1800267fb  mov     rdx, [r15]; struct CSession *
0x1800267fe  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x180026803  mov     [rsp+358h+arg_10], eax
0x18002680a  test    eax, eax
0x18002680c  jns     loc_1800266FD
0x180026812  jmp     loc_180026622
0x180026817  mov     rdx, [r15+90h]; jumptable 00000001800263DB case 79
0x18002681e  movzx   eax, word ptr [rdx+18h]
0x180026822  cmp     r10w, ax
0x180026826  jz      loc_180029488
0x18002682c  mov     ecx, eax; int
0x18002682e  mov     edx, 2083Ch; unsigned int
0x180026833  call    ?FVtIn@@YAHJK@Z; FVtIn(long,ulong)
0x180026838  test    eax, eax
  ... truncated ...
```
