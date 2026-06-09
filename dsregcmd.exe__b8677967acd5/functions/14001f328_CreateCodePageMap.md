# CreateCodePageMap

- ea: `0x14001f328`
- end: `0x140022180`
- name: `CreateCodePageMap`
- size: `11864`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400016d0`

## callees

- `0x1400017d4`
- `0x1400054e8`
- `0x140005c80`
- `0x1400061dc`
- `0x14001f008`
- `0x14001f328`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall CreateCodePageMap(volatile signed __int32 *a1)
{
  _QWORD *v1; // rax
  __int64 v2; // rcx
  volatile signed __int32 *v3; // rdx
  __int64 v4; // rcx
  volatile signed __int32 *v5; // rdx
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rdx
  __int64 v8; // rcx
  volatile signed __int32 *v9; // rdx
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rdx
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rdx
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rdx
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rdx
  __int64 v18; // rcx
  volatile signed __int32 *v19; // rdx
  __int64 v20; // rcx
  volatile signed __int32 *v21; // rdx
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rdx
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rdx
  __int64 v26; // rcx
  volatile signed __int32 *v27; // rdx
  __int64 v28; // rcx
  volatile signed __int32 *v29; // rdx
  __int64 v30; // rcx
  volatile signed __int32 *v31; // rdx
  __int64 v32; // rcx
  volatile signed __int32 *v33; // rdx
  __int64 v34; // rcx
  volatile signed __int32 *v35; // rdx
  __int64 v36; // rcx
  volatile signed __int32 *v37; // rdx
  __int64 v38; // rcx
  volatile signed __int32 *v39; // rdx
  __int64 v40; // rcx
  volatile signed __int32 *v41; // rdx
  __int64 v42; // rcx
  volatile signed __int32 *v43; // rdx
  __int64 v44; // rcx
  volatile signed __int32 *v45; // rdx
  __int64 v46; // rcx
  volatile signed __int32 *v47; // rdx
  __int64 v48; // rcx
  volatile signed __int32 *v49; // rdx
  __int64 v50; // rcx
  volatile signed __int32 *v51; // rdx
  __int64 v52; // rcx
  volatile signed __int32 *v53; // rdx
  __int64 v54; // rcx
  volatile signed __int32 *v55; // rdx
  __int64 v56; // rcx
  volatile signed __int32 *v57; // rdx
  __int64 v58; // rcx
  volatile signed __int32 *v59; // rdx
  __int64 v60; // rcx
  volatile signed __int32 *v61; // rdx
  __int64 v62; // rcx
  volatile signed __int32 *v63; // rdx
  __int64 v64; // rcx
  volatile signed __int32 *v65; // rdx
  __int64 v66; // rcx
  volatile signed __int32 *v67; // rdx
  __int64 v68; // rcx
  volatile signed __int32 *v69; // rdx
  __int64 v70; // rcx
  volatile signed __int32 *v71; // rdx
  __int64 v72; // rcx
  volatile signed __int32 *v73; // rdx
  __int64 v74; // rcx
  volatile signed __int32 *v75; // rdx
  __int64 v76; // rcx
  volatile signed __int32 *v77; // rdx
  __int64 v78; // rcx
  volatile signed __int32 *v79; // rdx
  __int64 v80; // rcx
  volatile signed __int32 *v81; // rdx
  __int64 v82; // rcx
  volatile signed __int32 *v83; // rdx
  __int64 v84; // rcx
  volatile signed __int32 *v85; // rdx
  __int64 v86; // rcx
  volatile signed __int32 *v87; // rdx
  __int64 v88; // rcx
  volatile signed __int32 *v89; // rdx
  __int64 v90; // rcx
  volatile signed __int32 *v91; // rdx
  __int64 v92; // rcx
  volatile signed __int32 *v93; // rdx
  __int64 v94; // rcx
  volatile signed __int32 *v95; // rdx
  __int64 v96; // rcx
  volatile signed __int32 *v97; // rdx
  __int64 v98; // rcx
  volatile signed __int32 *v99; // rdx
  __int64 v100; // rcx
  volatile signed __int32 *v101; // rdx
  __int64 v102; // rcx
  volatile signed __int32 *v103; // rdx
  __int64 v104; // rcx
  volatile signed __int32 *v105; // rdx
  __int64 v106; // rcx
  volatile signed __int32 *v107; // rdx
  __int64 v108; // rcx
  volatile signed __int32 *v109; // rdx
  __int64 v110; // rcx
  volatile signed __int32 *v111; // rdx
  __int64 v112; // rcx
  volatile signed __int32 *v113; // rdx
  __int64 v114; // rcx
  volatile signed __int32 *v115; // rdx
  __int64 v116; // rcx
  volatile signed __int32 *v117; // rdx
  __int64 v118; // rcx
  volatile signed __int32 *v119; // rdx
  __int64 v120; // rcx
  volatile signed __int32 *v121; // rdx
  __int64 v122; // rcx
  volatile signed __int32 *v123; // rdx
  __int64 v124; // rcx
  volatile signed __int32 *v125; // rdx
  __int64 v126; // rcx
  volatile signed __int32 *v127; // rdx
  __int64 v128; // rcx
  volatile signed __int32 *v129; // rdx
  __int64 v130; // rcx
  volatile signed __int32 *v131; // rdx
  __int64 v132; // rcx
  volatile signed __int32 *v133; // rdx
  __int64 v134; // rcx
  volatile signed __int32 *v135; // rdx
  __int64 v136; // rcx
  volatile signed __int32 *v137; // rdx
  __int64 v138; // rcx
  volatile signed __int32 *v139; // rdx
  __int64 v140; // rcx
  volatile signed __int32 *v141; // rdx
  __int64 v142; // rcx
  volatile signed __int32 *v143; // rdx
  __int64 v144; // rcx
  volatile signed __int32 *v145; // rdx
  __int64 v146; // rcx
  volatile signed __int32 *v147; // rdx
  __int64 v148; // rcx
  volatile signed __int32 *v149; // rdx
  __int64 v150; // rcx
  volatile signed __int32 *v151; // rdx
  __int64 v152; // rcx
  volatile signed __int32 *v153; // rdx
  __int64 v154; // rcx
  volatile signed __int32 *v155; // rdx
  __int64 v156; // rcx
  volatile signed __int32 *v157; // rdx
  __int64 v158; // rcx
  volatile signed __int32 *v159; // rdx
  __int64 v160; // rcx
  volatile signed __int32 *v161; // rdx
  __int64 v162; // rcx
  volatile signed __int32 *v163; // rdx
  __int64 v164; // rcx
  volatile signed __int32 *v165; // rdx
  __int64 v166; // rcx
  volatile signed __int32 *v167; // rdx
  __int64 v168; // rcx
  volatile signed __int32 *v169; // rdx
  __int64 v170; // rcx
  volatile signed __int32 *v171; // rdx
  __int64 v172; // rcx
  volatile signed __int32 *v173; // rdx
  __int64 v174; // rcx
  volatile signed __int32 *v175; // rdx
  __int64 v176; // rcx
  volatile signed __int32 *v177; // rdx
  __int64 v178; // rcx
  volatile signed __int32 *v179; // rdx
  __int64 v180; // rcx
  volatile signed __int32 *v181; // rdx
  __int64 v182; // rcx
  volatile signed __int32 *v183; // rdx
  __int64 v184; // rcx
  volatile signed __int32 *v185; // rdx
  __int64 v186; // rcx
  volatile signed __int32 *v187; // rdx
  __int64 v188; // rcx
  volatile signed __int32 *v189; // rdx
  __int64 v190; // rcx
  volatile signed __int32 *v191; // rdx
  __int64 v192; // rcx
  volatile signed __int32 *v193; // rdx
  __int64 v194; // rcx
  volatile signed __int32 *v195; // rdx
  __int64 v196; // rcx
  volatile signed __int32 *v197; // rdx
  __int64 v198; // rcx
  volatile signed __int32 *v199; // rdx
  __int64 v200; // rcx
  volatile signed __int32 *v201; // rdx
  __int64 v202; // rcx
  volatile signed __int32 *v203; // rdx
  __int64 v204; // rcx
  volatile signed __int32 *v205; // rdx
  __int64 v206; // rcx
  volatile signed __int32 *v207; // rdx
  __int64 v208; // rcx
  volatile signed __int32 *v209; // rdx
  __int64 v210; // rcx
  volatile signed __int32 *v211; // rdx
  __int64 v212; // rcx
  volatile signed __int32 *v213; // rdx
  __int64 v214; // rcx
  volatile signed __int32 *v215; // rdx
  __int64 v216; // rcx
  volatile signed __int32 *v217; // rdx
  __int64 v218; // rcx
  volatile signed __int32 *v219; // rdx
  __int64 v220; // rcx
  volatile signed __int32 *v221; // rdx
  __int64 v222; // rcx
  volatile signed __int32 *v223; // rdx
  __int64 v224; // rcx
  volatile signed __int32 *v225; // rdx
  __int64 v226; // rcx
  volatile signed __int32 *v227; // rdx
  __int64 v228; // rcx
  volatile signed __int32 *v229; // rdx
  __int64 v230; // rcx
  volatile signed __int32 *v231; // rdx
  __int64 v232; // rcx
  volatile signed __int32 *v233; // rdx
  __int64 v234; // rcx
  volatile signed __int32 *v235; // rdx
  __int64 v236; // rcx
  volatile signed __int32 *v237; // rdx
  __int64 v238; // rcx
  volatile signed __int32 *v239; // rdx
  __int64 v240; // rcx
  volatile signed __int32 *v241; // rdx
  __int64 v242; // rcx
  volatile signed __int32 *v243; // rdx
  __int64 v244; // rcx
  volatile signed __int32 *v245; // rdx
  __int64 v246; // rcx
  volatile signed __int32 *v247; // rdx
  __int64 v248; // rcx
  volatile signed __int32 *v249; // rdx
  __int64 v250; // rcx
  volatile signed __int32 *v251; // rdx
  __int64 v252; // rcx
  volatile signed __int32 *v253; // rdx
  __int64 v254; // rcx
  volatile signed __int32 *v255; // rdx
  __int64 v256; // rcx
  volatile signed __int32 *v257; // rdx
  __int64 v258; // rcx
  volatile signed __int32 *v259; // rdx
  __int64 v260; // rcx
  volatile signed __int32 *v261; // rdx
  __int64 v262; // rcx
  volatile signed __int32 *v263; // rdx
  __int64 v264; // rcx
  volatile signed __int32 *v265; // rdx
  __int64 v266; // rcx
  volatile signed __int32 *v267; // rdx
  __int64 v268; // rcx
  volatile signed __int32 *v269; // rdx
  __int64 v270; // rcx
  volatile signed __int32 *v271; // rdx
  __int64 v272; // rcx
  volatile signed __int32 *v273; // rdx
  __int64 v274; // rcx
  volatile signed __int32 *v275; // rdx
  __int64 v276; // rcx
  volatile signed __int32 *v277; // rdx
  __int64 v278; // rcx
  volatile signed __int32 *v279; // rdx
  __int64 v280; // rcx
  volatile signed __int32 *v281; // rdx
  volatile signed __int32 *v283; // [rsp+50h] [rbp+20h] BYREF
  __int64 *v284; // [rsp+58h] [rbp+28h]

  v283 = a1;
  v284 = &qword_140046070;
  qword_140046070 = 0;
  qword_140046078 = 0;
  v1 = operator new(0x30u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  qword_140046070 = (__int64)v1;
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm037") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm037", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v2,
               &v283) = 37;
  v3 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm437") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm437", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v4,
               &v283) = 437;
  v5 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm500") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm500", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v6,
               &v283) = 500;
  v7 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"asmo-708") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"asmo-708", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v8,
               &v283) = 708;
  v9 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"dos-720") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"dos-720", 7);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v10,
               &v283) = 720;
  v11 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm737") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm737", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v12,
               &v283) = 737;
  v13 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm775") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm775", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v14,
               &v283) = 775;
  v15 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm850") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm850", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v16,
               &v283) = 850;
  v17 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm852") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm852", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v18,
               &v283) = 852;
  v19 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm855") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm855", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v20,
               &v283) = 855;
  v21 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm857") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm857", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v22,
               &v283) = 857;
  v23 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm00858") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm00858", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v24,
               &v283) = 858;
  v25 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm860") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm860", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v26,
               &v283) = 860;
  v27 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm861") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm861", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v28,
               &v283) = 861;
  v29 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"dos-862") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"dos-862", 7);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v30,
               &v283) = 862;
  v31 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm863") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm863", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v32,
               &v283) = 863;
  v33 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 8LL))(*(_QWORD *)v33);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm864") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm864", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v34,
               &v283) = 864;
  v35 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm865") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm865", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v36,
               &v283) = 865;
  v37 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"cp866") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"cp866", 5);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v38,
               &v283) = 866;
  v39 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 8LL))(*(_QWORD *)v39);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm869") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm869", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v40,
               &v283) = 869;
  v41 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 8LL))(*(_QWORD *)v41);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm870") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm870", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v42,
               &v283) = 870;
  v43 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"windows-874") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"windows-874", 11);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v44,
               &v283) = 874;
  v45 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"cp875") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"cp875", 5);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v46,
               &v283) = 875;
  v47 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 8LL))(*(_QWORD *)v47);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"shift_jis") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"shift_jis", 9);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v48,
               &v283) = 932;
  v49 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v49 + 8LL))(*(_QWORD *)v49);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"gb2312") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"gb2312", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v50,
               &v283) = 936;
  v51 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ks_c_5601-1987") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ks_c_5601-1987", 14);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v52,
               &v283) = 949;
  v53 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"big5") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"big5", 4);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v54,
               &v283) = 950;
  v55 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 8LL))(*(_QWORD *)v55);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm1026") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm1026", 7);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v56,
               &v283) = 1026;
  v57 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v57 + 8LL))(*(_QWORD *)v57);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01047") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01047", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v58,
               &v283) = 1047;
  v59 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v59 + 8LL))(*(_QWORD *)v59);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01140") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01140", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v60,
               &v283) = 1140;
  v61 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v61 + 8LL))(*(_QWORD *)v61);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01141") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01141", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v62,
               &v283) = 1141;
  v63 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v63 + 8LL))(*(_QWORD *)v63);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01142") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01142", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v64,
               &v283) = 1142;
  v65 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v65 + 8LL))(*(_QWORD *)v65);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01143") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01143", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v66,
               &v283) = 1143;
  v67 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v67 + 8LL))(*(_QWORD *)v67);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01144") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01144", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v68,
               &v283) = 1144;
  v69 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 8LL))(*(_QWORD *)v69);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01145") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01145", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v70,
               &v283) = 1145;
  v71 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v71 + 8LL))(*(_QWORD *)v71);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01146") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01146", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v72,
               &v283) = 1146;
  v73 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v73 + 8LL))(*(_QWORD *)v73);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01147") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01147", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v74,
               &v283) = 1147;
  v75 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v75 + 8LL))(*(_QWORD *)v75);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01148") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01148", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v76,
               &v283) = 1148;
  v77 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v77 + 8LL))(*(_QWORD *)v77);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"ibm01149") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"ibm01149", 8);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v78,
               &v283) = 1149;
  v79 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v79 + 8LL))(*(_QWORD *)v79);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"utf-16") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"utf-16", 6);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v80,
               &v283) = 1200;
  v81 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v81 + 8LL))(*(_QWORD *)v81);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"unicodefffe") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"unicodefffe", 11);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v82,
               &v283) = 1201;
  v83 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v83 + 8LL))(*(_QWORD *)v83);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"windows-1250") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"windows-1250", 12);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v84,
               &v283) = 1250;
  v85 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v85 + 8LL))(*(_QWORD *)v85);
  v283 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v283,
          (__int64)L"windows-1251") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v283, L"windows-1251", 12);
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v86,
               &v283) = 1251;
  v87 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v87 + 8LL))(*(_QWORD *)v87);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1252");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v88,
               &v283) = 1252;
  v89 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v89 + 8LL))(*(_QWORD *)v89);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1253");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v90,
               &v283) = 1253;
  v91 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 8LL))(*(_QWORD *)v91);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1254");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v92,
               &v283) = 1254;
  v93 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v93 + 8LL))(*(_QWORD *)v93);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1255");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v94,
               &v283) = 1255;
  v95 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v95 + 8LL))(*(_QWORD *)v95);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1256");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v96,
               &v283) = 1256;
  v97 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v97 + 8LL))(*(_QWORD *)v97);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1257");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v98,
               &v283) = 1257;
  v99 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v99 + 8LL))(*(_QWORD *)v99);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"windows-1258");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v100,
               &v283) = 1258;
  v101 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v101 + 8LL))(*(_QWORD *)v101);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"johab");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v102,
               &v283) = 1361;
  v103 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v103 + 8LL))(*(_QWORD *)v103);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"macintosh");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v104,
               &v283) = 10000;
  v105 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v105 + 8LL))(*(_QWORD *)v105);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-japanese");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v106,
               &v283) = 10001;
  v107 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v107 + 8LL))(*(_QWORD *)v107);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-chinesetrad");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v108,
               &v283) = 10002;
  v109 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v109 + 8LL))(*(_QWORD *)v109);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-korean");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v110,
               &v283) = 10003;
  v111 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v111 + 8LL))(*(_QWORD *)v111);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-arabic");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v112,
               &v283) = 10004;
  v113 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v113 + 8LL))(*(_QWORD *)v113);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-hebrew");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v114,
               &v283) = 10005;
  v115 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v115 + 8LL))(*(_QWORD *)v115);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-greek");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v116,
               &v283) = 10006;
  v117 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v117 + 8LL))(*(_QWORD *)v117);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-cyrillic");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v118,
               &v283) = 10007;
  v119 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v119 + 8LL))(*(_QWORD *)v119);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-chinesesimp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v120,
               &v283) = 10008;
  v121 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v121 + 8LL))(*(_QWORD *)v121);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-romanian");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v122,
               &v283) = 10010;
  v123 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v123 + 8LL))(*(_QWORD *)v123);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-ukrainian");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v124,
               &v283) = 10017;
  v125 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v125 + 8LL))(*(_QWORD *)v125);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-thai");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v126,
               &v283) = 10021;
  v127 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v127 + 8LL))(*(_QWORD *)v127);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-ce");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v128,
               &v283) = 10029;
  v129 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v129 + 8LL))(*(_QWORD *)v129);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-icelandic");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v130,
               &v283) = 10079;
  v131 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v131 + 8LL))(*(_QWORD *)v131);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-turkish");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v132,
               &v283) = 10081;
  v133 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v133 + 8LL))(*(_QWORD *)v133);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-mac-croatian");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v134,
               &v283) = 10082;
  v135 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v135 + 8LL))(*(_QWORD *)v135);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"utf-32");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v136,
               &v283) = 12000;
  v137 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v137 + 8LL))(*(_QWORD *)v137);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"utf-32be");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v138,
               &v283) = 12001;
  v139 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v139 + 8LL))(*(_QWORD *)v139);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-chinese_cns");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v140,
               &v283) = 20000;
  v141 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v141 + 8LL))(*(_QWORD *)v141);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20001");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v142,
               &v283) = 20001;
  v143 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v143 + 8LL))(*(_QWORD *)v143);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x_chinese-eten");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v144,
               &v283) = 20002;
  v145 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v145 + 8LL))(*(_QWORD *)v145);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20003");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v146,
               &v283) = 20003;
  v147 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v147 + 8LL))(*(_QWORD *)v147);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20004");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v148,
               &v283) = 20004;
  v149 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v149 + 8LL))(*(_QWORD *)v149);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20005");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v150,
               &v283) = 20005;
  v151 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v151 + 8LL))(*(_QWORD *)v151);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-ia5");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v152,
               &v283) = 20105;
  v153 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v153 + 8LL))(*(_QWORD *)v153);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-ia5-german");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v154,
               &v283) = 20106;
  v155 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v155 + 8LL))(*(_QWORD *)v155);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-ia5-swedish");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v156,
               &v283) = 20107;
  v157 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v157 + 8LL))(*(_QWORD *)v157);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-ia5-norwegian");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v158,
               &v283) = 20108;
  v159 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v159 + 8LL))(*(_QWORD *)v159);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"us-ascii");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v160,
               &v283) = 20127;
  v161 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v161 + 8LL))(*(_QWORD *)v161);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20261");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v162,
               &v283) = 20261;
  v163 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v163 + 8LL))(*(_QWORD *)v163);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20269");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v164,
               &v283) = 20269;
  v165 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v165 + 8LL))(*(_QWORD *)v165);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm273");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v166,
               &v283) = 20273;
  v167 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v167 + 8LL))(*(_QWORD *)v167);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm277");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v168,
               &v283) = 20277;
  v169 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v169 + 8LL))(*(_QWORD *)v169);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm278");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v170,
               &v283) = 20278;
  v171 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v171 + 8LL))(*(_QWORD *)v171);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm280");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v172,
               &v283) = 20280;
  v173 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v173 + 8LL))(*(_QWORD *)v173);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm284");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v174,
               &v283) = 20284;
  v175 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v175 + 8LL))(*(_QWORD *)v175);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm285");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v176,
               &v283) = 20285;
  v177 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v177 + 8LL))(*(_QWORD *)v177);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm290");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v178,
               &v283) = 20290;
  v179 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v179 + 8LL))(*(_QWORD *)v179);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm297");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v180,
               &v283) = 20297;
  v181 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v181 + 8LL))(*(_QWORD *)v181);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm420");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v182,
               &v283) = 20420;
  v183 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v183 + 8LL))(*(_QWORD *)v183);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm423");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v184,
               &v283) = 20423;
  v185 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v185 + 8LL))(*(_QWORD *)v185);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm424");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v186,
               &v283) = 20424;
  v187 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v187 + 8LL))(*(_QWORD *)v187);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-ebcdic-koreanextended");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v188,
               &v283) = 20833;
  v189 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v189 + 8LL))(*(_QWORD *)v189);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm-thai");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v190,
               &v283) = 20838;
  v191 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v191 + 8LL))(*(_QWORD *)v191);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"koi8-r");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v192,
               &v283) = 20866;
  v193 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v193 + 8LL))(*(_QWORD *)v193);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm871");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v194,
               &v283) = 20871;
  v195 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v195 + 8LL))(*(_QWORD *)v195);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm880");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v196,
               &v283) = 20880;
  v197 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v197 + 8LL))(*(_QWORD *)v197);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm905");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v198,
               &v283) = 20905;
  v199 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v199 + 8LL))(*(_QWORD *)v199);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"ibm00924");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v200,
               &v283) = 20924;
  v201 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v201 + 8LL))(*(_QWORD *)v201);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"euc-jp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v202,
               &v283) = 20932;
  v203 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v203 + 8LL))(*(_QWORD *)v203);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20936");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v204,
               &v283) = 20936;
  v205 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v205 + 8LL))(*(_QWORD *)v205);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp20949");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v206,
               &v283) = 20949;
  v207 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v207 + 8LL))(*(_QWORD *)v207);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"cp1025");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v208,
               &v283) = 21025;
  v209 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v209 + 8LL))(*(_QWORD *)v209);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"koi8-u");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v210,
               &v283) = 21866;
  v211 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v211 + 8LL))(*(_QWORD *)v211);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-1");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v212,
               &v283) = 28591;
  v213 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v213 + 8LL))(*(_QWORD *)v213);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-2");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v214,
               &v283) = 28592;
  v215 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v215 + 8LL))(*(_QWORD *)v215);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-3");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v216,
               &v283) = 28593;
  v217 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v217 + 8LL))(*(_QWORD *)v217);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-4");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v218,
               &v283) = 28594;
  v219 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v219 + 8LL))(*(_QWORD *)v219);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-5");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v220,
               &v283) = 28595;
  v221 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v221 + 8LL))(*(_QWORD *)v221);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-6");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v222,
               &v283) = 28596;
  v223 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v223 + 8LL))(*(_QWORD *)v223);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-7");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v224,
               &v283) = 28597;
  v225 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v225 + 8LL))(*(_QWORD *)v225);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-8");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v226,
               &v283) = 28598;
  v227 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v227 + 8LL))(*(_QWORD *)v227);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-9");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v228,
               &v283) = 28599;
  v229 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v229 + 8LL))(*(_QWORD *)v229);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-13");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v230,
               &v283) = 28603;
  v231 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v231 + 8LL))(*(_QWORD *)v231);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-15");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v232,
               &v283) = 28605;
  v233 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v233 + 8LL))(*(_QWORD *)v233);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-europa");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v234,
               &v283) = 29001;
  v235 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v235 + 8LL))(*(_QWORD *)v235);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-8859-8-i");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v236,
               &v283) = 38598;
  v237 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v237 + 8LL))(*(_QWORD *)v237);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-2022-jp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v238,
               &v283) = 50220;
  v239 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v239 + 8LL))(*(_QWORD *)v239);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"csiso2022jp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v240,
               &v283) = 50221;
  v241 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v241 + 8LL))(*(_QWORD *)v241);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-2022-jp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v242,
               &v283) = 50222;
  v243 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v243 + 8LL))(*(_QWORD *)v243);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"iso-2022-kr");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v244,
               &v283) = 50225;
  v245 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v245 + 8LL))(*(_QWORD *)v245);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-cp50227");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v246,
               &v283) = 50227;
  v247 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v247 + 8LL))(*(_QWORD *)v247);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"euc-jp");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v248,
               &v283) = 51932;
  v249 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v249 + 8LL))(*(_QWORD *)v249);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"euc-cn");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v250,
               &v283) = 51936;
  v251 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v251 + 8LL))(*(_QWORD *)v251);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"euc-kr");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v252,
               &v283) = 51949;
  v253 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v253 + 8LL))(*(_QWORD *)v253);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"hz-gb-2312");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v254,
               &v283) = 52936;
  v255 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v255 + 8LL))(*(_QWORD *)v255);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"gb18030");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v256,
               &v283) = 54936;
  v257 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v257 + 8LL))(*(_QWORD *)v257);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-de");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v258,
               &v283) = 57002;
  v259 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v259 + 8LL))(*(_QWORD *)v259);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-be");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v260,
               &v283) = 57003;
  v261 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v261 + 8LL))(*(_QWORD *)v261);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-ta");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v262,
               &v283) = 57004;
  v263 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v263 + 8LL))(*(_QWORD *)v263);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-te");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v264,
               &v283) = 57005;
  v265 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v265 + 8LL))(*(_QWORD *)v265);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-as");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v266,
               &v283) = 57006;
  v267 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v267 + 8LL))(*(_QWORD *)v267);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-or");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v268,
               &v283) = 57007;
  v269 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v269 + 8LL))(*(_QWORD *)v269);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-ka");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v270,
               &v283) = 57008;
  v271 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v271 + 8LL))(*(_QWORD *)v271);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-ma");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v272,
               &v283) = 57009;
  v273 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v273 + 8LL))(*(_QWORD *)v273);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-gu");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v274,
               &v283) = 57010;
  v275 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v275 + 8LL))(*(_QWORD *)v275);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"x-iscii-pa");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v276,
               &v283) = 57011;
  v277 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v277 + 8LL))(*(_QWORD *)v277);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"utf-7");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v278,
               &v283) = 65000;
  v279 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v279 + 8LL))(*(_QWORD *)v279);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v283,
    (__int64)L"utf-8");
  *(_DWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int>::operator[](
               v280,
               &v283) = 65001;
  v281 = v283 - 6;
  if ( _InterlockedDecrement(v283 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v281 + 8LL))(*(_QWORD *)v281);
  return &qword_140046070;
}

```

## disassembly

```asm
0x14001f328  mov     [rsp-18h+arg_10], rbx
0x14001f32d  mov     [rsp-18h+arg_18], rsi
0x14001f332  mov     [rsp-18h+arg_0], rcx
0x14001f337  push    rbp
0x14001f338  push    r12
0x14001f33a  push    r14
0x14001f33c  mov     rbp, rsp
0x14001f33f  sub     rsp, 30h
0x14001f343  mov     [rbp+var_10], 0
0x14001f34a  lea     rax, qword_140046070
0x14001f351  mov     [rbp+arg_8], rax
0x14001f355  mov     cs:qword_140046070, 0
0x14001f360  mov     cs:qword_140046078, 0
0x14001f36b  mov     ecx, 30h ; '0'; Size
0x14001f370  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001f375  mov     [rax], rax
0x14001f378  mov     [rax+8], rax
0x14001f37c  mov     [rax+10h], rax
0x14001f380  mov     word ptr [rax+18h], 101h
0x14001f386  mov     cs:qword_140046070, rax
0x14001f38d  mov     [rbp+var_10], 1
0x14001f394  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f39b  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f3a2  mov     rcx, rsi
0x14001f3a5  mov     rax, [rax+18h]
0x14001f3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3ae  add     rax, 18h
0x14001f3b2  mov     [rbp+arg_0], rax
0x14001f3b6  lea     rdx, aIbm037; "ibm037"
0x14001f3bd  lea     rcx, [rbp+arg_0]
0x14001f3c1  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f3c6  mov     r14d, 6
0x14001f3cc  test    al, al
0x14001f3ce  jnz     short loc_14001F3E4
0x14001f3d0  mov     r8d, r14d
0x14001f3d3  lea     rdx, aIbm037; "ibm037"
0x14001f3da  lea     rcx, [rbp+arg_0]
0x14001f3de  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f3e3  nop
0x14001f3e4  lea     rdx, [rbp+arg_0]
0x14001f3e8  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f3ed  mov     dword ptr [rax], 25h ; '%'
0x14001f3f3  mov     rdx, [rbp+arg_0]
0x14001f3f7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f3fb  or      ebx, 0FFFFFFFFh
0x14001f3fe  mov     eax, ebx
0x14001f400  lock xadd [rdx+10h], eax
0x14001f405  add     eax, ebx
0x14001f407  test    eax, eax
0x14001f409  jg      short loc_14001F41A
0x14001f40b  mov     rcx, [rdx]
0x14001f40e  mov     rax, [rcx]
0x14001f411  mov     rax, [rax+8]
0x14001f415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f41a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f421  mov     rcx, rsi
0x14001f424  mov     rax, [rax+18h]
0x14001f428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f42d  add     rax, 18h
0x14001f431  mov     [rbp+arg_0], rax
0x14001f435  lea     rdx, aIbm437; "ibm437"
0x14001f43c  lea     rcx, [rbp+arg_0]
0x14001f440  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f445  test    al, al
0x14001f447  jnz     short loc_14001F45D
0x14001f449  mov     r8d, r14d
0x14001f44c  lea     rdx, aIbm437; "ibm437"
0x14001f453  lea     rcx, [rbp+arg_0]
0x14001f457  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f45c  nop
0x14001f45d  lea     rdx, [rbp+arg_0]
0x14001f461  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f466  mov     dword ptr [rax], 1B5h
0x14001f46c  mov     rdx, [rbp+arg_0]
0x14001f470  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f474  mov     eax, ebx
0x14001f476  lock xadd [rdx+10h], eax
0x14001f47b  add     eax, ebx
0x14001f47d  test    eax, eax
0x14001f47f  jg      short loc_14001F490
0x14001f481  mov     rcx, [rdx]
0x14001f484  mov     rax, [rcx]
0x14001f487  mov     rax, [rax+8]
0x14001f48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f490  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f497  mov     rcx, rsi
0x14001f49a  mov     rax, [rax+18h]
0x14001f49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f4a3  add     rax, 18h
0x14001f4a7  mov     [rbp+arg_0], rax
0x14001f4ab  lea     rdx, aIbm500; "ibm500"
0x14001f4b2  lea     rcx, [rbp+arg_0]
0x14001f4b6  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f4bb  test    al, al
0x14001f4bd  jnz     short loc_14001F4D3
0x14001f4bf  mov     r8d, r14d
0x14001f4c2  lea     rdx, aIbm500; "ibm500"
0x14001f4c9  lea     rcx, [rbp+arg_0]
0x14001f4cd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f4d2  nop
0x14001f4d3  lea     rdx, [rbp+arg_0]
0x14001f4d7  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f4dc  mov     dword ptr [rax], 1F4h
0x14001f4e2  mov     rdx, [rbp+arg_0]
0x14001f4e6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f4ea  mov     eax, ebx
0x14001f4ec  lock xadd [rdx+10h], eax
0x14001f4f1  add     eax, ebx
0x14001f4f3  test    eax, eax
0x14001f4f5  jg      short loc_14001F506
0x14001f4f7  mov     rcx, [rdx]
0x14001f4fa  mov     rax, [rcx]
0x14001f4fd  mov     rax, [rax+8]
0x14001f501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f506  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f50d  mov     rcx, rsi
0x14001f510  mov     rax, [rax+18h]
0x14001f514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f519  add     rax, 18h
0x14001f51d  mov     [rbp+arg_0], rax
0x14001f521  lea     rdx, aAsmo708; "asmo-708"
0x14001f528  lea     rcx, [rbp+arg_0]
0x14001f52c  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f531  mov     r12d, 8
0x14001f537  test    al, al
0x14001f539  jnz     short loc_14001F54F
0x14001f53b  mov     r8d, r12d
0x14001f53e  lea     rdx, aAsmo708; "asmo-708"
0x14001f545  lea     rcx, [rbp+arg_0]
0x14001f549  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f54e  nop
0x14001f54f  lea     rdx, [rbp+arg_0]
0x14001f553  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f558  mov     dword ptr [rax], 2C4h
0x14001f55e  mov     rdx, [rbp+arg_0]
0x14001f562  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f566  mov     eax, ebx
0x14001f568  lock xadd [rdx+10h], eax
0x14001f56d  add     eax, ebx
0x14001f56f  test    eax, eax
0x14001f571  jg      short loc_14001F582
0x14001f573  mov     rcx, [rdx]
0x14001f576  mov     rax, [rcx]
0x14001f579  mov     rax, [rax+8]
0x14001f57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f582  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f589  mov     rcx, rsi
0x14001f58c  mov     rax, [rax+18h]
0x14001f590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f595  add     rax, 18h
0x14001f599  mov     [rbp+arg_0], rax
0x14001f59d  lea     rdx, aDos720; "dos-720"
0x14001f5a4  lea     rcx, [rbp+arg_0]
0x14001f5a8  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f5ad  test    al, al
0x14001f5af  jnz     short loc_14001F5C8
0x14001f5b1  mov     r8d, 7
0x14001f5b7  lea     rdx, aDos720; "dos-720"
0x14001f5be  lea     rcx, [rbp+arg_0]
0x14001f5c2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f5c7  nop
0x14001f5c8  lea     rdx, [rbp+arg_0]
0x14001f5cc  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f5d1  mov     dword ptr [rax], 2D0h
0x14001f5d7  mov     rdx, [rbp+arg_0]
0x14001f5db  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f5df  mov     eax, ebx
0x14001f5e1  lock xadd [rdx+10h], eax
0x14001f5e6  add     eax, ebx
0x14001f5e8  test    eax, eax
0x14001f5ea  jg      short loc_14001F5FB
0x14001f5ec  mov     rcx, [rdx]
0x14001f5ef  mov     rax, [rcx]
0x14001f5f2  mov     rax, [rax+8]
0x14001f5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5fb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f602  mov     rcx, rsi
0x14001f605  mov     rax, [rax+18h]
0x14001f609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f60e  add     rax, 18h
0x14001f612  mov     [rbp+arg_0], rax
0x14001f616  lea     rdx, aIbm737; "ibm737"
0x14001f61d  lea     rcx, [rbp+arg_0]
0x14001f621  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f626  test    al, al
0x14001f628  jnz     short loc_14001F63E
0x14001f62a  mov     r8d, r14d
0x14001f62d  lea     rdx, aIbm737; "ibm737"
0x14001f634  lea     rcx, [rbp+arg_0]
0x14001f638  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f63d  nop
0x14001f63e  lea     rdx, [rbp+arg_0]
0x14001f642  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f647  mov     dword ptr [rax], 2E1h
0x14001f64d  mov     rdx, [rbp+arg_0]
0x14001f651  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f655  mov     eax, ebx
0x14001f657  lock xadd [rdx+10h], eax
0x14001f65c  add     eax, ebx
0x14001f65e  test    eax, eax
0x14001f660  jg      short loc_14001F671
0x14001f662  mov     rcx, [rdx]
0x14001f665  mov     rax, [rcx]
0x14001f668  mov     rax, [rax+8]
0x14001f66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f671  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f678  mov     rcx, rsi
0x14001f67b  mov     rax, [rax+18h]
0x14001f67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f684  add     rax, 18h
0x14001f688  mov     [rbp+arg_0], rax
0x14001f68c  lea     rdx, aIbm775; "ibm775"
0x14001f693  lea     rcx, [rbp+arg_0]
0x14001f697  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f69c  test    al, al
0x14001f69e  jnz     short loc_14001F6B4
0x14001f6a0  mov     r8d, r14d
0x14001f6a3  lea     rdx, aIbm775; "ibm775"
0x14001f6aa  lea     rcx, [rbp+arg_0]
0x14001f6ae  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f6b3  nop
0x14001f6b4  lea     rdx, [rbp+arg_0]
0x14001f6b8  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f6bd  mov     dword ptr [rax], 307h
0x14001f6c3  mov     rdx, [rbp+arg_0]
0x14001f6c7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f6cb  mov     eax, ebx
0x14001f6cd  lock xadd [rdx+10h], eax
0x14001f6d2  add     eax, ebx
0x14001f6d4  test    eax, eax
0x14001f6d6  jg      short loc_14001F6E7
0x14001f6d8  mov     rcx, [rdx]
0x14001f6db  mov     rax, [rcx]
0x14001f6de  mov     rax, [rax+8]
0x14001f6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f6ee  mov     rcx, rsi
0x14001f6f1  mov     rax, [rax+18h]
0x14001f6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6fa  add     rax, 18h
0x14001f6fe  mov     [rbp+arg_0], rax
0x14001f702  lea     rdx, aIbm850; "ibm850"
0x14001f709  lea     rcx, [rbp+arg_0]
0x14001f70d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f712  test    al, al
0x14001f714  jnz     short loc_14001F72A
0x14001f716  mov     r8d, r14d
0x14001f719  lea     rdx, aIbm850; "ibm850"
0x14001f720  lea     rcx, [rbp+arg_0]
0x14001f724  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f729  nop
0x14001f72a  lea     rdx, [rbp+arg_0]
0x14001f72e  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f733  mov     dword ptr [rax], 352h
0x14001f739  mov     rdx, [rbp+arg_0]
0x14001f73d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f741  mov     eax, ebx
0x14001f743  lock xadd [rdx+10h], eax
0x14001f748  add     eax, ebx
0x14001f74a  test    eax, eax
0x14001f74c  jg      short loc_14001F75D
0x14001f74e  mov     rcx, [rdx]
0x14001f751  mov     rax, [rcx]
0x14001f754  mov     rax, [rax+8]
0x14001f758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f75d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f764  mov     rcx, rsi
0x14001f767  mov     rax, [rax+18h]
0x14001f76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f770  add     rax, 18h
0x14001f774  mov     [rbp+arg_0], rax
0x14001f778  lea     rdx, aIbm852; "ibm852"
0x14001f77f  lea     rcx, [rbp+arg_0]
0x14001f783  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001f788  test    al, al
0x14001f78a  jnz     short loc_14001F7A0
0x14001f78c  mov     r8d, r14d
0x14001f78f  lea     rdx, aIbm852; "ibm852"
0x14001f796  lea     rcx, [rbp+arg_0]
0x14001f79a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f79f  nop
0x14001f7a0  lea     rdx, [rbp+arg_0]
0x14001f7a4  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@std@@@4@@std@@QEAAAEAH$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x14001f7a9  mov     dword ptr [rax], 354h
0x14001f7af  mov     rdx, [rbp+arg_0]
0x14001f7b3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001f7b7  mov     eax, ebx
0x14001f7b9  lock xadd [rdx+10h], eax
0x14001f7be  add     eax, ebx
0x14001f7c0  test    eax, eax
0x14001f7c2  jg      short loc_14001F7D3
0x14001f7c4  mov     rcx, [rdx]
0x14001f7c7  mov     rax, [rcx]
0x14001f7ca  mov     rax, [rax+8]
0x14001f7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f7d3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001f7da  mov     rcx, rsi
0x14001f7dd  mov     rax, [rax+18h]
0x14001f7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f7e6  add     rax, 18h
  ... truncated ...
```
