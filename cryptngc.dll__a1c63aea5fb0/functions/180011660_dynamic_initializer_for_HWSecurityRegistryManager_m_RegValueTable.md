# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__

- ea: `0x180011660`
- end: `0x1800158da`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__`
- size: `17018`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e60`
- `0x180001ec0`
- `0x180002060`
- `0x180002500`
- `0x180002a2c`
- `0x1800046e0`
- `0x180004720`
- `0x18000edb0`
- `0x18000f1d0`
- `0x18000f220`
- `0x18002d190`
- `0x18002dfd0`
- `0x18002e1f4`
- `0x180046c70`
- `0x180046ce0`

## string_xrefs

- `0x1800138ae`: `MaintenanceTaskComplete`
- `0x180012019`: `EkCertRescheduleTaskFailureStep`
- `0x1800116a3`: `ActiveDirectoryBackupSrkPub`
- `0x180014ee5`: `TaskReadyForAttestation`
- `0x180013041`: `FasrCustomBootPathReasons`
- `0x180014f30`: `TaskReadyForStorage`
- `0x180011e1a`: `EkCertPath`
- `0x1800151dc`: `WindowsAikCheckCreateResult`
- `0x180014db5`: `TaskFirmwareVersion`
- `0x180014e4d`: `TaskManufacturerId`
- `0x180012316`: `EkCertsInstalledFromNV`
- `0x180012f53`: `FasrCustomBootPath`
- `0x180014118`: `IntermediateCertsInstalledFromNV`
- `0x180012417`: `EkCreatePersistResult`
- `0x180014e02`: `TaskInformationFlags`
- `0x1800150f7`: `WBCLPath`
- `0x180014e98`: `TaskOsBuildNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=330
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__()
{
  __int128 *v0; // rdx
  __int128 *v1; // rdx
  __int128 *v2; // rdx
  __int128 *v3; // rdx
  __int128 *v4; // rdx
  __int128 *v5; // rdx
  __int128 *v6; // rdx
  __int128 *v7; // rdx
  __int128 *v8; // rdx
  __int128 *v9; // rdx
  __int128 *v10; // rdx
  __int128 *v11; // rdx
  __int128 *v12; // rdx
  __int128 *v13; // rdx
  __int128 *v14; // rdx
  __int128 *v15; // rdx
  __int128 *v16; // rdx
  __int128 *v17; // rdx
  __int128 *v18; // rdx
  __int128 *v19; // rdx
  __int128 *v20; // rdx
  __int128 *v21; // rdx
  __int128 *v22; // rdx
  __int128 *v23; // rdx
  __int128 *v24; // rdx
  __int128 *v25; // rdx
  __int128 *v26; // rdx
  __int128 *v27; // rdx
  __int128 *v28; // rdx
  __int128 *v29; // rdx
  __int128 *v30; // rdx
  __int128 *v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // rax
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // r8
  __int64 v80; // rdx
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // rax
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // rax
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rax
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // rax
  __int64 v100; // r8
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // r8
  __int64 v104; // rdx
  __int64 v105; // rax
  __int64 v106; // r8
  __int64 v107; // rdx
  __int64 v108; // rax
  __int64 v109; // r8
  __int64 v110; // rdx
  __int64 v111; // rax
  __int64 v112; // r8
  __int64 v113; // rdx
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // rdx
  __int64 v117; // rax
  __int64 v118; // r8
  __int64 v119; // rdx
  __int64 v120; // rax
  __int64 v121; // r8
  __int64 v122; // rdx
  __int64 v123; // rax
  __int64 v124; // r8
  __int64 v125; // rdx
  __int64 v126; // rax
  __int64 v127; // r8
  __int64 v128; // rdx
  __int64 v129; // rax
  __int64 v130; // r8
  __int64 v131; // rdx
  __int64 v132; // rax
  __int64 v133; // r8
  __int64 v134; // rdx
  __int64 v135; // rax
  __int64 v136; // r8
  __int64 v137; // rdx
  __int64 v138; // rax
  __int64 v139; // r8
  __int64 v140; // rdx
  __int64 v141; // rax
  __int64 v142; // r8
  __int64 v143; // rdx
  __int64 v144; // rax
  __int64 v145; // r8
  __int64 v146; // rdx
  __int64 v147; // rax
  __int64 v148; // r8
  __int64 v149; // rdx
  __int64 v150; // rax
  __int64 v151; // r8
  __int64 v152; // rdx
  __int64 v153; // rax
  __int64 v154; // r8
  __int64 v155; // rdx
  __int64 v156; // rax
  __int64 v157; // r8
  __int64 v158; // rdx
  __int64 v159; // rax
  __int64 v160; // r8
  __int64 v161; // rdx
  __int64 v162; // rax
  __int64 v163; // r8
  __int64 v164; // rdx
  __int64 v165; // rax
  __int64 v166; // r8
  __int64 v167; // rdx
  __int64 v168; // rax
  __int64 v169; // r8
  __int64 v170; // rdx
  __int64 v171; // rax
  __int64 v172; // r8
  __int64 v173; // rdx
  __int64 v174; // rax
  __int64 v175; // r8
  __int64 v176; // rdx
  __int64 v177; // rax
  __int64 v178; // r8
  __int64 v179; // rdx
  __int64 v180; // rax
  __int64 v181; // r8
  __int64 v182; // rdx
  __int64 v183; // rax
  __int64 v184; // r8
  __int64 v185; // rdx
  __int64 v186; // rax
  __int64 v187; // r8
  __int64 v188; // rdx
  __int64 v189; // rax
  __int64 v190; // r8
  __int64 v191; // rdx
  __int64 v192; // rax
  __int64 v193; // r8
  __int64 v194; // rdx
  __int64 v195; // rax
  __int64 v196; // r8
  __int64 v197; // rdx
  __int64 v198; // rax
  __int64 v199; // r8
  __int64 v200; // rdx
  __int64 v201; // rax
  __int64 v202; // r8
  __int64 v203; // rdx
  __int64 v204; // rax
  __int64 v205; // r8
  __int64 v206; // rdx
  __int64 v207; // rax
  __int64 v208; // r8
  __int64 v209; // rdx
  __int64 v210; // rax
  __int64 v211; // r8
  __int64 v212; // rdx
  __int64 v213; // rax
  __int64 v214; // r8
  __int64 v215; // rdx
  __int64 v216; // rax
  __int64 v217; // r8
  __int64 v218; // rdx
  __int64 v219; // rax
  __int64 v220; // r8
  __int64 v221; // rdx
  __int64 v222; // rax
  __int64 v223; // r8
  __int64 v224; // rdx
  __int64 v225; // rax
  __int64 v226; // r8
  __int64 v227; // rdx
  __int64 v228; // rax
  __int64 v229; // r8
  __int64 v230; // rdx
  __int64 v231; // rax
  __int64 v232; // r8
  __int64 v233; // rdx
  __int64 v234; // rax
  __int64 v235; // r8
  __int64 v236; // rdx
  __int64 v237; // rax
  __int64 v238; // r8
  __int64 v239; // rdx
  __int64 v240; // rax
  __int64 v241; // r8
  __int64 v242; // rdx
  __int64 v243; // rax
  __int64 v244; // r8
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rax
  __int64 v248; // rax
  __int64 v249; // rax
  __int64 v250; // rax
  __int64 v251; // rax
  __int64 v252; // rax
  __int64 v253; // rax
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rax
  __int64 v260; // rax
  __int64 v261; // rax
  __int64 v262; // rax
  __int64 v263; // rax
  __int64 v264; // rax
  __int64 v265; // rax
  __int64 v266; // rax
  __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rax
  __int64 v277; // rax
  __int64 v278; // rax
  __int64 v279; // rax
  __int64 v280; // rax
  __int64 v281; // rax
  __int64 v282; // rax
  __int64 v283; // rax
  __int64 v284; // rax
  __int64 v285; // rax
  __int64 v286; // rcx
  __int128 v288; // [rsp+20h] [rbp-E0h] BYREF
  int v289; // [rsp+30h] [rbp-D0h] BYREF
  int v290; // [rsp+34h] [rbp-CCh] BYREF
  int v291; // [rsp+38h] [rbp-C8h] BYREF
  int v292; // [rsp+3Ch] [rbp-C4h] BYREF
  int v293; // [rsp+40h] [rbp-C0h] BYREF
  int v294; // [rsp+44h] [rbp-BCh] BYREF
  int v295; // [rsp+48h] [rbp-B8h] BYREF
  int v296; // [rsp+4Ch] [rbp-B4h] BYREF
  int v297; // [rsp+50h] [rbp-B0h] BYREF
  int v298; // [rsp+54h] [rbp-ACh] BYREF
  int v299; // [rsp+58h] [rbp-A8h] BYREF
  int v300; // [rsp+5Ch] [rbp-A4h] BYREF
  int v301; // [rsp+60h] [rbp-A0h] BYREF
  int v302; // [rsp+64h] [rbp-9Ch] BYREF
  int v303; // [rsp+68h] [rbp-98h] BYREF
  int v304; // [rsp+6Ch] [rbp-94h] BYREF
  int v305; // [rsp+70h] [rbp-90h] BYREF
  int v306; // [rsp+74h] [rbp-8Ch] BYREF
  int v307; // [rsp+78h] [rbp-88h] BYREF
  int v308; // [rsp+7Ch] [rbp-84h] BYREF
  int v309; // [rsp+80h] [rbp-80h] BYREF
  int v310; // [rsp+84h] [rbp-7Ch] BYREF
  int v311; // [rsp+88h] [rbp-78h] BYREF
  int v312; // [rsp+8Ch] [rbp-74h] BYREF
  int v313; // [rsp+90h] [rbp-70h] BYREF
  int v314; // [rsp+94h] [rbp-6Ch] BYREF
  int v315; // [rsp+98h] [rbp-68h] BYREF
  int v316; // [rsp+9Ch] [rbp-64h] BYREF
  int v317; // [rsp+A0h] [rbp-60h] BYREF
  int v318; // [rsp+A4h] [rbp-5Ch] BYREF
  int v319; // [rsp+A8h] [rbp-58h] BYREF
  int v320; // [rsp+ACh] [rbp-54h] BYREF
  int v321; // [rsp+B0h] [rbp-50h] BYREF
  int v322; // [rsp+B4h] [rbp-4Ch] BYREF
  int v323; // [rsp+B8h] [rbp-48h] BYREF
  int v324; // [rsp+BCh] [rbp-44h] BYREF
  int v325; // [rsp+C0h] [rbp-40h] BYREF
  int v326; // [rsp+C4h] [rbp-3Ch] BYREF
  int v327; // [rsp+C8h] [rbp-38h] BYREF
  int v328; // [rsp+CCh] [rbp-34h] BYREF
  int v329; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v330; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v331; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v332; // [rsp+F0h] [rbp-10h]
  __int128 v333; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v334; // [rsp+108h] [rbp+8h]
  unsigned __int64 v335; // [rsp+110h] [rbp+10h]
  __int128 v336; // [rsp+118h] [rbp+18h] BYREF
  __int64 v337; // [rsp+128h] [rbp+28h]
  unsigned __int64 v338; // [rsp+130h] [rbp+30h]
  __int128 v339; // [rsp+138h] [rbp+38h] BYREF
  __int64 v340; // [rsp+148h] [rbp+48h]
  unsigned __int64 v341; // [rsp+150h] [rbp+50h]
  __int128 v342; // [rsp+158h] [rbp+58h] BYREF
  __int64 v343; // [rsp+168h] [rbp+68h]
  unsigned __int64 v344; // [rsp+170h] [rbp+70h]
  __int128 v345; // [rsp+178h] [rbp+78h] BYREF
  __int64 v346; // [rsp+188h] [rbp+88h]
  unsigned __int64 v347; // [rsp+190h] [rbp+90h]
  __int128 v348; // [rsp+198h] [rbp+98h] BYREF
  __int64 v349; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v350; // [rsp+1B0h] [rbp+B0h]
  __int128 v351; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v352; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 v353; // [rsp+1D0h] [rbp+D0h]
  __int128 v354; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v355; // [rsp+1E8h] [rbp+E8h]
  unsigned __int64 v356; // [rsp+1F0h] [rbp+F0h]
  __int128 v357; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v358; // [rsp+208h] [rbp+108h]
  unsigned __int64 v359; // [rsp+210h] [rbp+110h]
  __int128 v360; // [rsp+218h] [rbp+118h] BYREF
  __int64 v361; // [rsp+228h] [rbp+128h]
  unsigned __int64 v362; // [rsp+230h] [rbp+130h]
  __int128 v363; // [rsp+238h] [rbp+138h] BYREF
  __int64 v364; // [rsp+248h] [rbp+148h]
  unsigned __int64 v365; // [rsp+250h] [rbp+150h]
  __int128 v366; // [rsp+258h] [rbp+158h] BYREF
  __int64 v367; // [rsp+268h] [rbp+168h]
  unsigned __int64 v368; // [rsp+270h] [rbp+170h]
  __int128 v369; // [rsp+278h] [rbp+178h] BYREF
  __int64 v370; // [rsp+288h] [rbp+188h]
  unsigned __int64 v371; // [rsp+290h] [rbp+190h]
  __int128 v372; // [rsp+298h] [rbp+198h] BYREF
  __int64 v373; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int64 v374; // [rsp+2B0h] [rbp+1B0h]
  __int128 v375; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v376; // [rsp+2C8h] [rbp+1C8h]
  unsigned __int64 v377; // [rsp+2D0h] [rbp+1D0h]
  __int128 v378; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v379; // [rsp+2E8h] [rbp+1E8h]
  __int64 v380; // [rsp+2F0h] [rbp+1F0h]
  __int128 v381; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v382; // [rsp+308h] [rbp+208h]
  __int64 v383; // [rsp+310h] [rbp+210h]
  __int128 v384; // [rsp+318h] [rbp+218h] BYREF
  __int64 v385; // [rsp+328h] [rbp+228h]
  __int64 v386; // [rsp+330h] [rbp+230h]
  __int128 v387; // [rsp+338h] [rbp+238h] BYREF
  __int64 v388; // [rsp+348h] [rbp+248h]
  __int64 v389; // [rsp+350h] [rbp+250h]
  __int128 v390; // [rsp+358h] [rbp+258h] BYREF
  __int64 v391; // [rsp+368h] [rbp+268h]
  __int64 v392; // [rsp+370h] [rbp+270h]
  __int128 v393; // [rsp+378h] [rbp+278h] BYREF
  __int64 v394; // [rsp+388h] [rbp+288h]
  __int64 v395; // [rsp+390h] [rbp+290h]
  __int128 v396; // [rsp+398h] [rbp+298h] BYREF
  __int64 v397; // [rsp+3A8h] [rbp+2A8h]
  __int64 v398; // [rsp+3B0h] [rbp+2B0h]
  __int128 v399; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int64 v400; // [rsp+3C8h] [rbp+2C8h]
  __int64 v401; // [rsp+3D0h] [rbp+2D0h]
  __int128 v402; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v403; // [rsp+3E8h] [rbp+2E8h]
  __int64 v404; // [rsp+3F0h] [rbp+2F0h]
  __int128 v405; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v406; // [rsp+408h] [rbp+308h]
  __int64 v407; // [rsp+410h] [rbp+310h]
  __int128 v408; // [rsp+418h] [rbp+318h] BYREF
  __int64 v409; // [rsp+428h] [rbp+328h]
  __int64 v410; // [rsp+430h] [rbp+330h]
  __int128 v411; // [rsp+438h] [rbp+338h] BYREF
  __int64 v412; // [rsp+448h] [rbp+348h]
  __int64 v413; // [rsp+450h] [rbp+350h]
  __int128 v414; // [rsp+458h] [rbp+358h] BYREF
  __int64 v415; // [rsp+468h] [rbp+368h]
  __int64 v416; // [rsp+470h] [rbp+370h]
  __int128 v417; // [rsp+478h] [rbp+378h] BYREF
  __int64 v418; // [rsp+488h] [rbp+388h]
  __int64 v419; // [rsp+490h] [rbp+390h]
  __int128 v420; // [rsp+498h] [rbp+398h] BYREF
  __int64 v421; // [rsp+4A8h] [rbp+3A8h]
  __int64 v422; // [rsp+4B0h] [rbp+3B0h]
  __int128 v423; // [rsp+4B8h] [rbp+3B8h] BYREF
  __int64 v424; // [rsp+4C8h] [rbp+3C8h]
  __int64 v425; // [rsp+4D0h] [rbp+3D0h]
  __int128 v426; // [rsp+4D8h] [rbp+3D8h] BYREF
  __int64 v427; // [rsp+4E8h] [rbp+3E8h]
  __int64 v428; // [rsp+4F0h] [rbp+3F0h]
  __int128 v429; // [rsp+4F8h] [rbp+3F8h] BYREF
  __int64 v430; // [rsp+508h] [rbp+408h]
  __int64 v431; // [rsp+510h] [rbp+410h]
  __int128 v432; // [rsp+518h] [rbp+418h] BYREF
  __int64 v433; // [rsp+528h] [rbp+428h]
  __int64 v434; // [rsp+530h] [rbp+430h]
  __int128 v435; // [rsp+538h] [rbp+438h] BYREF
  __int64 v436; // [rsp+548h] [rbp+448h]
  __int64 v437; // [rsp+550h] [rbp+450h]
  __int128 v438; // [rsp+558h] [rbp+458h] BYREF
  __int64 v439; // [rsp+568h] [rbp+468h]
  __int64 v440; // [rsp+570h] [rbp+470h]
  __int128 v441; // [rsp+578h] [rbp+478h] BYREF
  __int64 v442; // [rsp+588h] [rbp+488h]
  __int64 v443; // [rsp+590h] [rbp+490h]
  __int128 v444; // [rsp+598h] [rbp+498h] BYREF
  __int64 v445; // [rsp+5A8h] [rbp+4A8h]
  __int64 v446; // [rsp+5B0h] [rbp+4B0h]
  __int128 v447; // [rsp+5B8h] [rbp+4B8h] BYREF
  __int64 v448; // [rsp+5C8h] [rbp+4C8h]
  __int64 v449; // [rsp+5D0h] [rbp+4D0h]
  __int128 v450; // [rsp+5D8h] [rbp+4D8h] BYREF
  __int64 v451; // [rsp+5E8h] [rbp+4E8h]
  __int64 v452; // [rsp+5F0h] [rbp+4F0h]
  __int128 v453; // [rsp+5F8h] [rbp+4F8h] BYREF
  __int64 v454; // [rsp+608h] [rbp+508h]
  __int64 v455; // [rsp+610h] [rbp+510h]
  __int128 v456; // [rsp+618h] [rbp+518h] BYREF
  __int64 v457; // [rsp+628h] [rbp+528h]
  __int64 v458; // [rsp+630h] [rbp+530h]
  __int128 v459; // [rsp+638h] [rbp+538h] BYREF
  __int64 v460; // [rsp+648h] [rbp+548h]
  __int64 v461; // [rsp+650h] [rbp+550h]
  __int128 v462; // [rsp+658h] [rbp+558h] BYREF
  __int64 v463; // [rsp+668h] [rbp+568h]
  __int64 v464; // [rsp+670h] [rbp+570h]
  __int128 v465; // [rsp+678h] [rbp+578h] BYREF
  __int64 v466; // [rsp+688h] [rbp+588h]
  __int64 v467; // [rsp+690h] [rbp+590h]
  __int128 v468; // [rsp+698h] [rbp+598h] BYREF
  __int64 v469; // [rsp+6A8h] [rbp+5A8h]
  __int64 v470; // [rsp+6B0h] [rbp+5B0h]
  __int128 v471; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v472; // [rsp+6C8h] [rbp+5C8h]
  __int64 v473; // [rsp+6D0h] [rbp+5D0h]
  __int128 v474; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v475; // [rsp+6E8h] [rbp+5E8h]
  __int64 v476; // [rsp+6F0h] [rbp+5F0h]
  __int128 v477; // [rsp+6F8h] [rbp+5F8h] BYREF
  __int64 v478; // [rsp+708h] [rbp+608h]
  __int64 v479; // [rsp+710h] [rbp+610h]
  __int128 v480; // [rsp+718h] [rbp+618h] BYREF
  __int64 v481; // [rsp+728h] [rbp+628h]
  __int64 v482; // [rsp+730h] [rbp+630h]
  __int128 v483; // [rsp+738h] [rbp+638h] BYREF
  __int64 v484; // [rsp+748h] [rbp+648h]
  __int64 v485; // [rsp+750h] [rbp+650h]
  _BYTE v486[16]; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v487[32]; // [rsp+768h] [rbp+668h] BYREF
  _BYTE v488[32]; // [rsp+788h] [rbp+688h] BYREF
  _BYTE v489[32]; // [rsp+7A8h] [rbp+6A8h] BYREF
  _BYTE v490[32]; // [rsp+7C8h] [rbp+6C8h] BYREF
  _BYTE v491[32]; // [rsp+7E8h] [rbp+6E8h] BYREF
  _BYTE v492[32]; // [rsp+808h] [rbp+708h] BYREF
  _BYTE v493[32]; // [rsp+828h] [rbp+728h] BYREF
  _BYTE v494[32]; // [rsp+848h] [rbp+748h] BYREF
  _BYTE v495[32]; // [rsp+868h] [rbp+768h] BYREF
  _BYTE v496[32]; // [rsp+888h] [rbp+788h] BYREF
  _BYTE v497[32]; // [rsp+8A8h] [rbp+7A8h] BYREF
  _BYTE v498[32]; // [rsp+8C8h] [rbp+7C8h] BYREF
  _BYTE v499[32]; // [rsp+8E8h] [rbp+7E8h] BYREF
  _BYTE v500[32]; // [rsp+908h] [rbp+808h] BYREF
  _BYTE v501[32]; // [rsp+928h] [rbp+828h] BYREF
  _BYTE v502[32]; // [rsp+948h] [rbp+848h] BYREF
  _BYTE v503[32]; // [rsp+968h] [rbp+868h] BYREF
  _BYTE v504[32]; // [rsp+988h] [rbp+888h] BYREF
  _BYTE v505[32]; // [rsp+9A8h] [rbp+8A8h] BYREF
  _BYTE v506[32]; // [rsp+9C8h] [rbp+8C8h] BYREF
  _BYTE v507[32]; // [rsp+9E8h] [rbp+8E8h] BYREF
  _BYTE v508[32]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v509[32]; // [rsp+A28h] [rbp+928h] BYREF
  _BYTE v510[32]; // [rsp+A48h] [rbp+948h] BYREF
  _BYTE v511[32]; // [rsp+A68h] [rbp+968h] BYREF
  _BYTE v512[32]; // [rsp+A88h] [rbp+988h] BYREF
  _BYTE v513[32]; // [rsp+AA8h] [rbp+9A8h] BYREF
  _BYTE v514[32]; // [rsp+AC8h] [rbp+9C8h] BYREF
  _BYTE v515[32]; // [rsp+AE8h] [rbp+9E8h] BYREF
  _BYTE v516[32]; // [rsp+B08h] [rbp+A08h] BYREF
  _BYTE v517[32]; // [rsp+B28h] [rbp+A28h] BYREF
  _BYTE v518[32]; // [rsp+B48h] [rbp+A48h] BYREF
  _BYTE v519[32]; // [rsp+B68h] [rbp+A68h] BYREF
  _BYTE v520[32]; // [rsp+B88h] [rbp+A88h] BYREF
  _BYTE v521[32]; // [rsp+BA8h] [rbp+AA8h] BYREF
  _BYTE v522[32]; // [rsp+BC8h] [rbp+AC8h] BYREF
  _BYTE v523[32]; // [rsp+BE8h] [rbp+AE8h] BYREF
  _BYTE v524[32]; // [rsp+C08h] [rbp+B08h] BYREF
  _BYTE v525[32]; // [rsp+C28h] [rbp+B28h] BYREF
  _BYTE v526[32]; // [rsp+C48h] [rbp+B48h] BYREF
  _BYTE v527[32]; // [rsp+C68h] [rbp+B68h] BYREF
  int v528; // [rsp+C88h] [rbp+B88h] BYREF
  __int128 v529; // [rsp+C90h] [rbp+B90h] BYREF
  __int128 v530; // [rsp+CA0h] [rbp+BA0h]
  int v531; // [rsp+CB0h] [rbp+BB0h]
  int v532; // [rsp+CB8h] [rbp+BB8h] BYREF
  __int128 v533; // [rsp+CC0h] [rbp+BC0h] BYREF
  __int128 v534; // [rsp+CD0h] [rbp+BD0h]
  int v535; // [rsp+CE0h] [rbp+BE0h]
  int v536; // [rsp+CE8h] [rbp+BE8h] BYREF
  __int128 v537; // [rsp+CF0h] [rbp+BF0h] BYREF
  __int128 v538; // [rsp+D00h] [rbp+C00h]
  int v539; // [rsp+D10h] [rbp+C10h]
  int v540; // [rsp+D18h] [rbp+C18h] BYREF
  __int128 v541; // [rsp+D20h] [rbp+C20h] BYREF
  __int128 v542; // [rsp+D30h] [rbp+C30h]
  int v543; // [rsp+D40h] [rbp+C40h]
  int v544; // [rsp+D48h] [rbp+C48h] BYREF
  __int128 v545; // [rsp+D50h] [rbp+C50h] BYREF
  __int128 v546; // [rsp+D60h] [rbp+C60h]
  int v547; // [rsp+D70h] [rbp+C70h]
  int v548; // [rsp+D78h] [rbp+C78h] BYREF
  __int128 v549; // [rsp+D80h] [rbp+C80h] BYREF
  __int128 v550; // [rsp+D90h] [rbp+C90h]
  int v551; // [rsp+DA0h] [rbp+CA0h]
  int v552; // [rsp+DA8h] [rbp+CA8h] BYREF
  __int128 v553; // [rsp+DB0h] [rbp+CB0h] BYREF
  __int128 v554; // [rsp+DC0h] [rbp+CC0h]
  int v555; // [rsp+DD0h] [rbp+CD0h]
  int v556; // [rsp+DD8h] [rbp+CD8h] BYREF
  __int128 v557; // [rsp+DE0h] [rbp+CE0h] BYREF
  __int128 v558; // [rsp+DF0h] [rbp+CF0h]
  int v559; // [rsp+E00h] [rbp+D00h]
  int v560; // [rsp+E08h] [rbp+D08h] BYREF
  __int128 v561; // [rsp+E10h] [rbp+D10h] BYREF
  __int128 v562; // [rsp+E20h] [rbp+D20h]
  int v563; // [rsp+E30h] [rbp+D30h]
  int v564; // [rsp+E38h] [rbp+D38h] BYREF
  __int128 v565; // [rsp+E40h] [rbp+D40h] BYREF
  __int128 v566; // [rsp+E50h] [rbp+D50h]
  int v567; // [rsp+E60h] [rbp+D60h]
  int v568; // [rsp+E68h] [rbp+D68h] BYREF
  __int128 v569; // [rsp+E70h] [rbp+D70h] BYREF
  __int128 v570; // [rsp+E80h] [rbp+D80h]
  int v571; // [rsp+E90h] [rbp+D90h]
  int v572; // [rsp+E98h] [rbp+D98h] BYREF
  __int128 v573; // [rsp+EA0h] [rbp+DA0h] BYREF
  __int128 v574; // [rsp+EB0h] [rbp+DB0h]
  int v575; // [rsp+EC0h] [rbp+DC0h]
  int v576; // [rsp+EC8h] [rbp+DC8h] BYREF
  __int128 v577; // [rsp+ED0h] [rbp+DD0h] BYREF
  __int128 v578; // [rsp+EE0h] [rbp+DE0h]
  int v579; // [rsp+EF0h] [rbp+DF0h]
  int v580; // [rsp+EF8h] [rbp+DF8h] BYREF
  __int128 v581; // [rsp+F00h] [rbp+E00h] BYREF
  __int128 v582; // [rsp+F10h] [rbp+E10h]
  int v583; // [rsp+F20h] [rbp+E20h]
  int v584; // [rsp+F28h] [rbp+E28h] BYREF
  __int128 v585; // [rsp+F30h] [rbp+E30h] BYREF
  __int128 v586; // [rsp+F40h] [rbp+E40h]
  int v587; // [rsp+F50h] [rbp+E50h]
  int v588; // [rsp+F58h] [rbp+E58h] BYREF
  __int128 v589; // [rsp+F60h] [rbp+E60h] BYREF
  __int128 v590; // [rsp+F70h] [rbp+E70h]
  int v591; // [rsp+F80h] [rbp+E80h]
  int v592; // [rsp+F88h] [rbp+E88h] BYREF
  __int128 v593; // [rsp+F90h] [rbp+E90h] BYREF
  __int128 v594; // [rsp+FA0h] [rbp+EA0h]
  int v595; // [rsp+FB0h] [rbp+EB0h]
  int v596; // [rsp+FB8h] [rbp+EB8h] BYREF
  __int128 v597; // [rsp+FC0h] [rbp+EC0h] BYREF
  __int128 v598; // [rsp+FD0h] [rbp+ED0h]
  int v599; // [rsp+FE0h] [rbp+EE0h]
  int v600; // [rsp+FE8h] [rbp+EE8h] BYREF
  __int128 v601; // [rsp+FF0h] [rbp+EF0h] BYREF
  __int128 v602; // [rsp+1000h] [rbp+F00h]
  int v603; // [rsp+1010h] [rbp+F10h]
  int v604; // [rsp+1018h] [rbp+F18h] BYREF
  __int128 v605; // [rsp+1020h] [rbp+F20h] BYREF
  __int128 v606; // [rsp+1030h] [rbp+F30h]
  int v607; // [rsp+1040h] [rbp+F40h]
  int v608; // [rsp+1048h] [rbp+F48h] BYREF
  __int128 v609; // [rsp+1050h] [rbp+F50h] BYREF
  __int128 v610; // [rsp+1060h] [rbp+F60h]
  int v611; // [rsp+1070h] [rbp+F70h]
  int v612; // [rsp+1078h] [rbp+F78h] BYREF
  __int128 v613; // [rsp+1080h] [rbp+F80h] BYREF
  __int128 v614; // [rsp+1090h] [rbp+F90h]
  int v615; // [rsp+10A0h] [rbp+FA0h]
  int v616; // [rsp+10A8h] [rbp+FA8h] BYREF
  __int128 v617; // [rsp+10B0h] [rbp+FB0h] BYREF
  __int128 v618; // [rsp+10C0h] [rbp+FC0h]
  int v619; // [rsp+10D0h] [rbp+FD0h]
  int v620; // [rsp+10D8h] [rbp+FD8h] BYREF
  __int128 v621; // [rsp+10E0h] [rbp+FE0h] BYREF
  __int128 v622; // [rsp+10F0h] [rbp+FF0h]
  int v623; // [rsp+1100h] [rbp+1000h]
  int v624; // [rsp+1108h] [rbp+1008h] BYREF
  __int128 v625; // [rsp+1110h] [rbp+1010h] BYREF
  __int128 v626; // [rsp+1120h] [rbp+1020h]
  int v627; // [rsp+1130h] [rbp+1030h]
  int v628; // [rsp+1138h] [rbp+1038h] BYREF
  __int128 v629; // [rsp+1140h] [rbp+1040h] BYREF
  __int128 v630; // [rsp+1150h] [rbp+1050h]
  int v631; // [rsp+1160h] [rbp+1060h]
  int v632; // [rsp+1168h] [rbp+1068h] BYREF
  __int128 v633; // [rsp+1170h] [rbp+1070h] BYREF
  __int128 v634; // [rsp+1180h] [rbp+1080h]
  int v635; // [rsp+1190h] [rbp+1090h]
  int v636; // [rsp+1198h] [rbp+1098h] BYREF
  __int128 v637; // [rsp+11A0h] [rbp+10A0h] BYREF
  __int128 v638; // [rsp+11B0h] [rbp+10B0h]
  int v639; // [rsp+11C0h] [rbp+10C0h]
  int v640; // [rsp+11C8h] [rbp+10C8h] BYREF
  __int128 v641; // [rsp+11D0h] [rbp+10D0h] BYREF
  __int128 v642; // [rsp+11E0h] [rbp+10E0h]
  int v643; // [rsp+11F0h] [rbp+10F0h]
  int v644; // [rsp+11F8h] [rbp+10F8h] BYREF
  __int128 v645; // [rsp+1200h] [rbp+1100h] BYREF
  __int128 v646; // [rsp+1210h] [rbp+1110h]
  int v647; // [rsp+1220h] [rbp+1120h]
  int v648; // [rsp+1228h] [rbp+1128h] BYREF
  __int128 v649; // [rsp+1230h] [rbp+1130h] BYREF
  __int128 v650; // [rsp+1240h] [rbp+1140h]
  int v651; // [rsp+1250h] [rbp+1150h]
  int v652; // [rsp+1258h] [rbp+1158h] BYREF
  __int128 v653; // [rsp+1260h] [rbp+1160h] BYREF
  __int128 v654; // [rsp+1270h] [rbp+1170h]
  int v655; // [rsp+1280h] [rbp+1180h]
  int v656; // [rsp+1288h] [rbp+1188h] BYREF
  __int128 v657; // [rsp+1290h] [rbp+1190h] BYREF
  __int128 v658; // [rsp+12A0h] [rbp+11A0h]
  int v659; // [rsp+12B0h] [rbp+11B0h]
  int v660; // [rsp+12B8h] [rbp+11B8h] BYREF
  __int128 v661; // [rsp+12C0h] [rbp+11C0h] BYREF
  __int128 v662; // [rsp+12D0h] [rbp+11D0h]
  int v663; // [rsp+12E0h] [rbp+11E0h]
  int v664; // [rsp+12E8h] [rbp+11E8h] BYREF
  __int128 v665; // [rsp+12F0h] [rbp+11F0h] BYREF
  __int128 v666; // [rsp+1300h] [rbp+1200h]
  int v667; // [rsp+1310h] [rbp+1210h]
  int v668; // [rsp+1318h] [rbp+1218h] BYREF
  __int128 v669; // [rsp+1320h] [rbp+1220h] BYREF
  __int128 v670; // [rsp+1330h] [rbp+1230h]
  int v671; // [rsp+1340h] [rbp+1240h]
  int v672; // [rsp+1348h] [rbp+1248h] BYREF
  __int128 v673; // [rsp+1350h] [rbp+1250h] BYREF
  __int128 v674; // [rsp+1360h] [rbp+1260h]
  int v675; // [rsp+1370h] [rbp+1270h]
  int v676; // [rsp+1378h] [rbp+1278h] BYREF
  __int128 v677; // [rsp+1380h] [rbp+1280h] BYREF
  __int128 v678; // [rsp+1390h] [rbp+1290h]
  int v679; // [rsp+13A0h] [rbp+12A0h]
  int v680; // [rsp+13A8h] [rbp+12A8h] BYREF
  __int128 v681; // [rsp+13B0h] [rbp+12B0h] BYREF
  __int128 v682; // [rsp+13C0h] [rbp+12C0h]
  int v683; // [rsp+13D0h] [rbp+12D0h]
  int v684; // [rsp+13D8h] [rbp+12D8h] BYREF
  __int128 v685; // [rsp+13E0h] [rbp+12E0h] BYREF
  __int128 v686; // [rsp+13F0h] [rbp+12F0h]
  int v687; // [rsp+1400h] [rbp+1300h]
  int v688; // [rsp+1408h] [rbp+1308h] BYREF
  __int128 v689; // [rsp+1410h] [rbp+1310h] BYREF
  __int128 v690; // [rsp+1420h] [rbp+1320h]
  int v691; // [rsp+1430h] [rbp+1330h]
  int v692; // [rsp+1438h] [rbp+1338h] BYREF
  __int128 v693; // [rsp+1440h] [rbp+1340h] BYREF
  __int128 v694; // [rsp+1450h] [rbp+1350h]
  int v695; // [rsp+1460h] [rbp+1360h]
  int v696; // [rsp+1468h] [rbp+1368h] BYREF
  __int128 v697; // [rsp+1470h] [rbp+1370h] BYREF
  __int128 v698; // [rsp+1480h] [rbp+1380h]
  int v699; // [rsp+1490h] [rbp+1390h]
  int v700; // [rsp+1498h] [rbp+1398h] BYREF
  __int128 v701; // [rsp+14A0h] [rbp+13A0h] BYREF
  __int128 v702; // [rsp+14B0h] [rbp+13B0h]
  int v703; // [rsp+14C0h] [rbp+13C0h]
  int v704; // [rsp+14C8h] [rbp+13C8h] BYREF
  __int128 v705; // [rsp+14D0h] [rbp+13D0h] BYREF
  __int128 v706; // [rsp+14E0h] [rbp+13E0h]
  int v707; // [rsp+14F0h] [rbp+13F0h]
  int v708; // [rsp+14F8h] [rbp+13F8h] BYREF
  __int128 v709; // [rsp+1500h] [rbp+1400h] BYREF
  __int128 v710; // [rsp+1510h] [rbp+1410h]
  int v711; // [rsp+1520h] [rbp+1420h]
  int v712; // [rsp+1528h] [rbp+1428h] BYREF
  __int128 v713; // [rsp+1530h] [rbp+1430h] BYREF
  __int128 v714; // [rsp+1540h] [rbp+1440h]
  int v715; // [rsp+1550h] [rbp+1450h]
  int v716; // [rsp+1558h] [rbp+1458h] BYREF
  __int128 v717; // [rsp+1560h] [rbp+1460h] BYREF
  __int128 v718; // [rsp+1570h] [rbp+1470h]
  int v719; // [rsp+1580h] [rbp+1480h]
  int v720; // [rsp+1588h] [rbp+1488h] BYREF
  __int128 v721; // [rsp+1590h] [rbp+1490h] BYREF
  __int128 v722; // [rsp+15A0h] [rbp+14A0h]
  int v723; // [rsp+15B0h] [rbp+14B0h]
  int v724; // [rsp+15B8h] [rbp+14B8h] BYREF
  __int128 v725; // [rsp+15C0h] [rbp+14C0h] BYREF
  __int128 v726; // [rsp+15D0h] [rbp+14D0h]
  int v727; // [rsp+15E0h] [rbp+14E0h]
  int v728; // [rsp+15E8h] [rbp+14E8h] BYREF
  __int128 v729; // [rsp+15F0h] [rbp+14F0h] BYREF
  __int128 v730; // [rsp+1600h] [rbp+1500h]
  int v731; // [rsp+1610h] [rbp+1510h]
  int v732; // [rsp+1618h] [rbp+1518h] BYREF
  _OWORD v733[2]; // [rsp+1620h] [rbp+1520h] BYREF
  int v734; // [rsp+1640h] [rbp+1540h]
  _DWORD v735[4]; // [rsp+1650h] [rbp+1550h] BYREF
  _OWORD v736[2]; // [rsp+1660h] [rbp+1560h] BYREF
  int v737; // [rsp+1680h] [rbp+1580h]
  int v738; // [rsp+1688h] [rbp+1588h]
  int v739; // [rsp+1690h] [rbp+1590h]
  __int128 v740; // [rsp+1698h] [rbp+1598h] BYREF
  __int64 v741; // [rsp+16A8h] [rbp+15A8h]
  __int64 v742; // [rsp+16B0h] [rbp+15B0h]
  int v743; // [rsp+16B8h] [rbp+15B8h]
  int v744; // [rsp+16C0h] [rbp+15C0h]
  int v745; // [rsp+16C8h] [rbp+15C8h]
  _OWORD v746[2]; // [rsp+16D0h] [rbp+15D0h] BYREF
  int v747; // [rsp+16F0h] [rbp+15F0h]
  int v748; // [rsp+16F8h] [rbp+15F8h]
  int v749; // [rsp+1700h] [rbp+1600h]
  __int128 v750; // [rsp+1708h] [rbp+1608h] BYREF
  __int64 v751; // [rsp+1718h] [rbp+1618h]
  __int64 v752; // [rsp+1720h] [rbp+1620h]
  int v753; // [rsp+1728h] [rbp+1628h]
  int v754; // [rsp+1730h] [rbp+1630h]
  int v755; // [rsp+1738h] [rbp+1638h]
  _OWORD v756[2]; // [rsp+1740h] [rbp+1640h] BYREF
  int v757; // [rsp+1760h] [rbp+1660h]
  int v758; // [rsp+1768h] [rbp+1668h]
  int v759; // [rsp+1770h] [rbp+1670h]
  __int128 v760; // [rsp+1778h] [rbp+1678h] BYREF
  __int64 v761; // [rsp+1788h] [rbp+1688h]
  __int64 v762; // [rsp+1790h] [rbp+1690h]
  int v763; // [rsp+1798h] [rbp+1698h]
  int v764; // [rsp+17A0h] [rbp+16A0h]
  int v765; // [rsp+17A8h] [rbp+16A8h]
  _OWORD v766[2]; // [rsp+17B0h] [rbp+16B0h] BYREF
  int v767; // [rsp+17D0h] [rbp+16D0h]
  int v768; // [rsp+17D8h] [rbp+16D8h]
  int v769; // [rsp+17E0h] [rbp+16E0h]
  __int128 v770; // [rsp+17E8h] [rbp+16E8h] BYREF
  __int64 v771; // [rsp+17F8h] [rbp+16F8h]
  __int64 v772; // [rsp+1800h] [rbp+1700h]
  int v773; // [rsp+1808h] [rbp+1708h]
  int v774; // [rsp+1810h] [rbp+1710h]
  int v775; // [rsp+1818h] [rbp+1718h]
  _OWORD v776[2]; // [rsp+1820h] [rbp+1720h] BYREF
  int v777; // [rsp+1840h] [rbp+1740h]
  int v778; // [rsp+1848h] [rbp+1748h]
  int v779; // [rsp+1850h] [rbp+1750h]
  __int128 v780; // [rsp+1858h] [rbp+1758h] BYREF
  __int64 v781; // [rsp+1868h] [rbp+1768h]
  __int64 v782; // [rsp+1870h] [rbp+1770h]
  int v783; // [rsp+1878h] [rbp+1778h]
  int v784; // [rsp+1880h] [rbp+1780h]
  int v785; // [rsp+1888h] [rbp+1788h]
  _OWORD v786[2]; // [rsp+1890h] [rbp+1790h] BYREF
  int v787; // [rsp+18B0h] [rbp+17B0h]
  int v788; // [rsp+18B8h] [rbp+17B8h]
  int v789; // [rsp+18C0h] [rbp+17C0h]
  __int128 v790; // [rsp+18C8h] [rbp+17C8h] BYREF
  __int64 v791; // [rsp+18D8h] [rbp+17D8h]
  __int64 v792; // [rsp+18E0h] [rbp+17E0h]
  int v793; // [rsp+18E8h] [rbp+17E8h]
  int v794; // [rsp+18F0h] [rbp+17F0h]
  int v795; // [rsp+18F8h] [rbp+17F8h]
  _OWORD v796[2]; // [rsp+1900h] [rbp+1800h] BYREF
  int v797; // [rsp+1920h] [rbp+1820h]
  int v798; // [rsp+1928h] [rbp+1828h]
  int v799; // [rsp+1930h] [rbp+1830h]
  __int128 v800; // [rsp+1938h] [rbp+1838h] BYREF
  __int64 v801; // [rsp+1948h] [rbp+1848h]
  __int64 v802; // [rsp+1950h] [rbp+1850h]
  int v803; // [rsp+1958h] [rbp+1858h]
  int v804; // [rsp+1960h] [rbp+1860h]
  int v805; // [rsp+1968h] [rbp+1868h]
  _OWORD v806[2]; // [rsp+1970h] [rbp+1870h] BYREF
  int v807; // [rsp+1990h] [rbp+1890h]
  int v808; // [rsp+1998h] [rbp+1898h]
  int v809; // [rsp+19A0h] [rbp+18A0h]
  __int128 v810; // [rsp+19A8h] [rbp+18A8h] BYREF
  __int64 v811; // [rsp+19B8h] [rbp+18B8h]
  __int64 v812; // [rsp+19C0h] [rbp+18C0h]
  int v813; // [rsp+19C8h] [rbp+18C8h]
  int v814; // [rsp+19D0h] [rbp+18D0h]
  int v815; // [rsp+19D8h] [rbp+18D8h]
  _OWORD v816[2]; // [rsp+19E0h] [rbp+18E0h] BYREF
  int v817; // [rsp+1A00h] [rbp+1900h]
  int v818; // [rsp+1A08h] [rbp+1908h]
  int v819; // [rsp+1A10h] [rbp+1910h]
  __int128 v820; // [rsp+1A18h] [rbp+1918h] BYREF
  __int64 v821; // [rsp+1A28h] [rbp+1928h]
  __int64 v822; // [rsp+1A30h] [rbp+1930h]
  int v823; // [rsp+1A38h] [rbp+1938h]
  int v824; // [rsp+1A40h] [rbp+1940h]
  int v825; // [rsp+1A48h] [rbp+1948h]
  _OWORD v826[2]; // [rsp+1A50h] [rbp+1950h] BYREF
  int v827; // [rsp+1A70h] [rbp+1970h]
  int v828; // [rsp+1A78h] [rbp+1978h]
  int v829; // [rsp+1A80h] [rbp+1980h]
  __int128 v830; // [rsp+1A88h] [rbp+1988h] BYREF
  __int64 v831; // [rsp+1A98h] [rbp+1998h]
  __int64 v832; // [rsp+1AA0h] [rbp+19A0h]
  int v833; // [rsp+1AA8h] [rbp+19A8h]
  int v834; // [rsp+1AB0h] [rbp+19B0h]
  int v835; // [rsp+1AB8h] [rbp+19B8h]
  _OWORD v836[2]; // [rsp+1AC0h] [rbp+19C0h] BYREF
  int v837; // [rsp+1AE0h] [rbp+19E0h]
  int v838; // [rsp+1AE8h] [rbp+19E8h]
  int v839; // [rsp+1AF0h] [rbp+19F0h]
  __int128 v840; // [rsp+1AF8h] [rbp+19F8h] BYREF
  __int64 v841; // [rsp+1B08h] [rbp+1A08h]
  __int64 v842; // [rsp+1B10h] [rbp+1A10h]
  int v843; // [rsp+1B18h] [rbp+1A18h]
  int v844; // [rsp+1B20h] [rbp+1A20h]
  int v845; // [rsp+1B28h] [rbp+1A28h]
  _OWORD v846[2]; // [rsp+1B30h] [rbp+1A30h] BYREF
  int v847; // [rsp+1B50h] [rbp+1A50h]
  int v848; // [rsp+1B58h] [rbp+1A58h]
  int v849; // [rsp+1B60h] [rbp+1A60h]
  __int128 v850; // [rsp+1B68h] [rbp+1A68h] BYREF
  __int64 v851; // [rsp+1B78h] [rbp+1A78h]
  __int64 v852; // [rsp+1B80h] [rbp+1A80h]
  int v853; // [rsp+1B88h] [rbp+1A88h]
  int v854; // [rsp+1B90h] [rbp+1A90h]
  int v855; // [rsp+1B98h] [rbp+1A98h]
  _OWORD v856[2]; // [rsp+1BA0h] [rbp+1AA0h] BYREF
  int v857; // [rsp+1BC0h] [rbp+1AC0h]
  int v858; // [rsp+1BC8h] [rbp+1AC8h]
  int v859; // [rsp+1BD0h] [rbp+1AD0h]
  __int128 v860; // [rsp+1BD8h] [rbp+1AD8h] BYREF
  __int64 v861; // [rsp+1BE8h] [rbp+1AE8h]
  __int64 v862; // [rsp+1BF0h] [rbp+1AF0h]
  int v863; // [rsp+1BF8h] [rbp+1AF8h]
  int v864; // [rsp+1C00h] [rbp+1B00h]
  int v865; // [rsp+1C08h] [rbp+1B08h]
  _OWORD v866[2]; // [rsp+1C10h] [rbp+1B10h] BYREF
  int v867; // [rsp+1C30h] [rbp+1B30h]
  int v868; // [rsp+1C38h] [rbp+1B38h]
  int v869; // [rsp+1C40h] [rbp+1B40h]
  __int128 v870; // [rsp+1C48h] [rbp+1B48h] BYREF
  __int64 v871; // [rsp+1C58h] [rbp+1B58h]
  __int64 v872; // [rsp+1C60h] [rbp+1B60h]
  int v873; // [rsp+1C68h] [rbp+1B68h]
  int v874; // [rsp+1C70h] [rbp+1B70h]
  int v875; // [rsp+1C78h] [rbp+1B78h]
  _OWORD v876[2]; // [rsp+1C80h] [rbp+1B80h] BYREF
  int v877; // [rsp+1CA0h] [rbp+1BA0h]
  int v878; // [rsp+1CA8h] [rbp+1BA8h]
  int v879; // [rsp+1CB0h] [rbp+1BB0h]
  __int128 v880; // [rsp+1CB8h] [rbp+1BB8h] BYREF
  __int64 v881; // [rsp+1CC8h] [rbp+1BC8h]
  __int64 v882; // [rsp+1CD0h] [rbp+1BD0h]
  int v883; // [rsp+1CD8h] [rbp+1BD8h]
  int v884; // [rsp+1CE0h] [rbp+1BE0h]
  int v885; // [rsp+1CE8h] [rbp+1BE8h]
  _OWORD v886[2]; // [rsp+1CF0h] [rbp+1BF0h] BYREF
  int v887; // [rsp+1D10h] [rbp+1C10h]
  int v888; // [rsp+1D18h] [rbp+1C18h]
  int v889; // [rsp+1D20h] [rbp+1C20h]
  __int128 v890; // [rsp+1D28h] [rbp+1C28h] BYREF
  __int64 v891; // [rsp+1D38h] [rbp+1C38h]
  __int64 v892; // [rsp+1D40h] [rbp+1C40h]
  int v893; // [rsp+1D48h] [rbp+1C48h]
  int v894; // [rsp+1D50h] [rbp+1C50h]
  int v895; // [rsp+1D58h] [rbp+1C58h]
  _OWORD v896[2]; // [rsp+1D60h] [rbp+1C60h] BYREF
  int v897; // [rsp+1D80h] [rbp+1C80h]
  int v898; // [rsp+1D88h] [rbp+1C88h]
  int v899; // [rsp+1D90h] [rbp+1C90h]
  __int128 v900; // [rsp+1D98h] [rbp+1C98h] BYREF
  __int64 v901; // [rsp+1DA8h] [rbp+1CA8h]
  __int64 v902; // [rsp+1DB0h] [rbp+1CB0h]
  int v903; // [rsp+1DB8h] [rbp+1CB8h]
  int v904; // [rsp+1DC0h] [rbp+1CC0h]
  int v905; // [rsp+1DC8h] [rbp+1CC8h]
  _OWORD v906[2]; // [rsp+1DD0h] [rbp+1CD0h] BYREF
  int v907; // [rsp+1DF0h] [rbp+1CF0h]
  int v908; // [rsp+1DF8h] [rbp+1CF8h]
  int v909; // [rsp+1E00h] [rbp+1D00h]
  __int128 v910; // [rsp+1E08h] [rbp+1D08h] BYREF
  __int64 v911; // [rsp+1E18h] [rbp+1D18h]
  __int64 v912; // [rsp+1E20h] [rbp+1D20h]
  int v913; // [rsp+1E28h] [rbp+1D28h]
  int v914; // [rsp+1E30h] [rbp+1D30h]
  int v915; // [rsp+1E38h] [rbp+1D38h]
  _OWORD v916[2]; // [rsp+1E40h] [rbp+1D40h] BYREF
  int v917; // [rsp+1E60h] [rbp+1D60h]
  int v918; // [rsp+1E68h] [rbp+1D68h]
  int v919; // [rsp+1E70h] [rbp+1D70h]
  __int128 v920; // [rsp+1E78h] [rbp+1D78h] BYREF
  __int64 v921; // [rsp+1E88h] [rbp+1D88h]
  __int64 v922; // [rsp+1E90h] [rbp+1D90h]
  int v923; // [rsp+1E98h] [rbp+1D98h]
  int v924; // [rsp+1EA0h] [rbp+1DA0h]
  int v925; // [rsp+1EA8h] [rbp+1DA8h]
  _OWORD v926[2]; // [rsp+1EB0h] [rbp+1DB0h] BYREF
  int v927; // [rsp+1ED0h] [rbp+1DD0h]
  int v928; // [rsp+1ED8h] [rbp+1DD8h]
  int v929; // [rsp+1EE0h] [rbp+1DE0h]
  __int128 v930; // [rsp+1EE8h] [rbp+1DE8h] BYREF
  __int64 v931; // [rsp+1EF8h] [rbp+1DF8h]
  __int64 v932; // [rsp+1F00h] [rbp+1E00h]
  int v933; // [rsp+1F08h] [rbp+1E08h]
  int v934; // [rsp+1F10h] [rbp+1E10h]
  int v935; // [rsp+1F18h] [rbp+1E18h]
  _OWORD v936[2]; // [rsp+1F20h] [rbp+1E20h] BYREF
  int v937; // [rsp+1F40h] [rbp+1E40h]
  int v938; // [rsp+1F48h] [rbp+1E48h]
  int v939; // [rsp+1F50h] [rbp+1E50h]
  __int128 v940; // [rsp+1F58h] [rbp+1E58h] BYREF
  __int64 v941; // [rsp+1F68h] [rbp+1E68h]
  __int64 v942; // [rsp+1F70h] [rbp+1E70h]
  int v943; // [rsp+1F78h] [rbp+1E78h]
  int v944; // [rsp+1F80h] [rbp+1E80h]
  int v945; // [rsp+1F88h] [rbp+1E88h]
  _OWORD v946[2]; // [rsp+1F90h] [rbp+1E90h] BYREF
  int v947; // [rsp+1FB0h] [rbp+1EB0h]
  int v948; // [rsp+1FB8h] [rbp+1EB8h]
  int v949; // [rsp+1FC0h] [rbp+1EC0h]
  __int128 v950; // [rsp+1FC8h] [rbp+1EC8h] BYREF
  __int64 v951; // [rsp+1FD8h] [rbp+1ED8h]
  __int64 v952; // [rsp+1FE0h] [rbp+1EE0h]
  int v953; // [rsp+1FE8h] [rbp+1EE8h]
  int v954; // [rsp+1FF0h] [rbp+1EF0h]
  int v955; // [rsp+1FF8h] [rbp+1EF8h]
  _OWORD v956[2]; // [rsp+2000h] [rbp+1F00h] BYREF
  int v957; // [rsp+2020h] [rbp+1F20h]
  int v958; // [rsp+2028h] [rbp+1F28h]
  int v959; // [rsp+2030h] [rbp+1F30h]
  __int128 v960; // [rsp+2038h] [rbp+1F38h] BYREF
  __int64 v961; // [rsp+2048h] [rbp+1F48h]
  __int64 v962; // [rsp+2050h] [rbp+1F50h]
  int v963; // [rsp+2058h] [rbp+1F58h]
  int v964; // [rsp+2060h] [rbp+1F60h]
  int v965; // [rsp+2068h] [rbp+1F68h]
  _OWORD v966[2]; // [rsp+2070h] [rbp+1F70h] BYREF
  int v967; // [rsp+2090h] [rbp+1F90h]
  int v968; // [rsp+2098h] [rbp+1F98h]
  int v969; // [rsp+20A0h] [rbp+1FA0h]
  __int128 v970; // [rsp+20A8h] [rbp+1FA8h] BYREF
  __int64 v971; // [rsp+20B8h] [rbp+1FB8h]
  __int64 v972; // [rsp+20C0h] [rbp+1FC0h]
  int v973; // [rsp+20C8h] [rbp+1FC8h]
  int v974; // [rsp+20D0h] [rbp+1FD0h]
  int v975; // [rsp+20D8h] [rbp+1FD8h]
  _OWORD v976[2]; // [rsp+20E0h] [rbp+1FE0h] BYREF
  int v977; // [rsp+2100h] [rbp+2000h]
  int v978; // [rsp+2108h] [rbp+2008h]
  int v979; // [rsp+2110h] [rbp+2010h]
  __int128 v980; // [rsp+2118h] [rbp+2018h] BYREF
  __int64 v981; // [rsp+2128h] [rbp+2028h]
  __int64 v982; // [rsp+2130h] [rbp+2030h]
  int v983; // [rsp+2138h] [rbp+2038h]
  int v984; // [rsp+2140h] [rbp+2040h]
  int v985; // [rsp+2148h] [rbp+2048h]
  _OWORD v986[2]; // [rsp+2150h] [rbp+2050h] BYREF
  int v987; // [rsp+2170h] [rbp+2070h]
  int v988; // [rsp+2178h] [rbp+2078h]
  _BYTE v989[48]; // [rsp+2180h] [rbp+2080h] BYREF
  _BYTE v990[56]; // [rsp+21B0h] [rbp+20B0h] BYREF
  _BYTE v991[56]; // [rsp+21E8h] [rbp+20E8h] BYREF
  _BYTE v992[56]; // [rsp+2220h] [rbp+2120h] BYREF
  _BYTE v993[56]; // [rsp+2258h] [rbp+2158h] BYREF
  _BYTE v994[56]; // [rsp+2290h] [rbp+2190h] BYREF
  _BYTE v995[56]; // [rsp+22C8h] [rbp+21C8h] BYREF
  _BYTE v996[56]; // [rsp+2300h] [rbp+2200h] BYREF
  _BYTE v997[56]; // [rsp+2338h] [rbp+2238h] BYREF
  _BYTE v998[56]; // [rsp+2370h] [rbp+2270h] BYREF
  _BYTE v999[56]; // [rsp+23A8h] [rbp+22A8h] BYREF
  _BYTE v1000[56]; // [rsp+23E0h] [rbp+22E0h] BYREF
  _BYTE v1001[56]; // [rsp+2418h] [rbp+2318h] BYREF
  _BYTE v1002[56]; // [rsp+2450h] [rbp+2350h] BYREF
  _BYTE v1003[56]; // [rsp+2488h] [rbp+2388h] BYREF
  _BYTE v1004[56]; // [rsp+24C0h] [rbp+23C0h] BYREF
  _BYTE v1005[56]; // [rsp+24F8h] [rbp+23F8h] BYREF
  _BYTE v1006[56]; // [rsp+2530h] [rbp+2430h] BYREF
  _BYTE v1007[56]; // [rsp+2568h] [rbp+2468h] BYREF
  _BYTE v1008[56]; // [rsp+25A0h] [rbp+24A0h] BYREF
  _BYTE v1009[56]; // [rsp+25D8h] [rbp+24D8h] BYREF
  _BYTE v1010[56]; // [rsp+2610h] [rbp+2510h] BYREF
  _BYTE v1011[56]; // [rsp+2648h] [rbp+2548h] BYREF
  _BYTE v1012[56]; // [rsp+2680h] [rbp+2580h] BYREF
  _BYTE v1013[56]; // [rsp+26B8h] [rbp+25B8h] BYREF
  _BYTE v1014[56]; // [rsp+26F0h] [rbp+25F0h] BYREF
  _BYTE v1015[56]; // [rsp+2728h] [rbp+2628h] BYREF
  _BYTE v1016[56]; // [rsp+2760h] [rbp+2660h] BYREF
  _BYTE v1017[56]; // [rsp+2798h] [rbp+2698h] BYREF
  _BYTE v1018[56]; // [rsp+27D0h] [rbp+26D0h] BYREF
  _BYTE v1019[56]; // [rsp+2808h] [rbp+2708h] BYREF
  _BYTE v1020[56]; // [rsp+2840h] [rbp+2740h] BYREF
  _BYTE v1021[56]; // [rsp+2878h] [rbp+2778h] BYREF
  _BYTE v1022[56]; // [rsp+28B0h] [rbp+27B0h] BYREF
  _BYTE v1023[56]; // [rsp+28E8h] [rbp+27E8h] BYREF
  _BYTE v1024[56]; // [rsp+2920h] [rbp+2820h] BYREF
  _BYTE v1025[56]; // [rsp+2958h] [rbp+2858h] BYREF
  _BYTE v1026[56]; // [rsp+2990h] [rbp+2890h] BYREF
  _BYTE v1027[56]; // [rsp+29C8h] [rbp+28C8h] BYREF
  _BYTE v1028[56]; // [rsp+2A00h] [rbp+2900h] BYREF
  _BYTE v1029[56]; // [rsp+2A38h] [rbp+2938h] BYREF
  _BYTE v1030[56]; // [rsp+2A70h] [rbp+2970h] BYREF
  _BYTE v1031[8]; // [rsp+2AA8h] [rbp+29A8h] BYREF
  _BYTE v1032[48]; // [rsp+2AB0h] [rbp+29B0h] BYREF
  _BYTE v1033[48]; // [rsp+2AE0h] [rbp+29E0h] BYREF
  _BYTE v1034[48]; // [rsp+2B10h] [rbp+2A10h] BYREF
  _BYTE v1035[48]; // [rsp+2B40h] [rbp+2A40h] BYREF
  _BYTE v1036[48]; // [rsp+2B70h] [rbp+2A70h] BYREF
  _BYTE v1037[48]; // [rsp+2BA0h] [rbp+2AA0h] BYREF
  _BYTE v1038[48]; // [rsp+2BD0h] [rbp+2AD0h] BYREF
  _BYTE v1039[48]; // [rsp+2C00h] [rbp+2B00h] BYREF
  _BYTE v1040[48]; // [rsp+2C30h] [rbp+2B30h] BYREF
  _BYTE v1041[48]; // [rsp+2C60h] [rbp+2B60h] BYREF
  _BYTE v1042[48]; // [rsp+2C90h] [rbp+2B90h] BYREF
  _BYTE v1043[48]; // [rsp+2CC0h] [rbp+2BC0h] BYREF
  _BYTE v1044[48]; // [rsp+2CF0h] [rbp+2BF0h] BYREF
  _BYTE v1045[48]; // [rsp+2D20h] [rbp+2C20h] BYREF
  _BYTE v1046[48]; // [rsp+2D50h] [rbp+2C50h] BYREF
  _BYTE v1047[48]; // [rsp+2D80h] [rbp+2C80h] BYREF
  _BYTE v1048[48]; // [rsp+2DB0h] [rbp+2CB0h] BYREF
  _BYTE v1049[48]; // [rsp+2DE0h] [rbp+2CE0h] BYREF
  _BYTE v1050[48]; // [rsp+2E10h] [rbp+2D10h] BYREF
  _BYTE v1051[48]; // [rsp+2E40h] [rbp+2D40h] BYREF
  _BYTE v1052[48]; // [rsp+2E70h] [rbp+2D70h] BYREF
  _BYTE v1053[48]; // [rsp+2EA0h] [rbp+2DA0h] BYREF
  _BYTE v1054[48]; // [rsp+2ED0h] [rbp+2DD0h] BYREF
  _BYTE v1055[48]; // [rsp+2F00h] [rbp+2E00h] BYREF
  _BYTE v1056[48]; // [rsp+2F30h] [rbp+2E30h] BYREF
  _BYTE v1057[48]; // [rsp+2F60h] [rbp+2E60h] BYREF
  _BYTE v1058[48]; // [rsp+2F90h] [rbp+2E90h] BYREF
  _BYTE v1059[48]; // [rsp+2FC0h] [rbp+2EC0h] BYREF
  _BYTE v1060[48]; // [rsp+2FF0h] [rbp+2EF0h] BYREF
  _BYTE v1061[48]; // [rsp+3020h] [rbp+2F20h] BYREF
  _BYTE v1062[48]; // [rsp+3050h] [rbp+2F50h] BYREF
  _BYTE v1063[48]; // [rsp+3080h] [rbp+2F80h] BYREF
  _BYTE v1064[48]; // [rsp+30B0h] [rbp+2FB0h] BYREF
  _BYTE v1065[48]; // [rsp+30E0h] [rbp+2FE0h] BYREF
  _BYTE v1066[48]; // [rsp+3110h] [rbp+3010h] BYREF
  _BYTE v1067[48]; // [rsp+3140h] [rbp+3040h] BYREF
  _BYTE v1068[48]; // [rsp+3170h] [rbp+3070h] BYREF
  _BYTE v1069[48]; // [rsp+31A0h] [rbp+30A0h] BYREF
  _BYTE v1070[48]; // [rsp+31D0h] [rbp+30D0h] BYREF
  _BYTE v1071[48]; // [rsp+3200h] [rbp+3100h] BYREF
  _BYTE v1072[48]; // [rsp+3230h] [rbp+3130h] BYREF

  v333 = 0;
  v334 = 0;
  v335 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v333, L"ActiveDirectoryBackupSrkPub", 27);
  *(_QWORD *)&v288 = &v333;
  v588 = 5;
  v589 = 0;
  v590 = 0;
  v0 = &v333;
  if ( v335 > 7 )
    v0 = (__int128 *)v333;
  std::wstring::_Construct<2,unsigned short const *>(&v589, v0, v334);
  v591 = 3;
  std::wstring::~wstring(&v333);
  v735[0] = 0;
  v735[2] = v588;
  memset(v736, 0, sizeof(v736));
  v1 = &v589;
  if ( *((_QWORD *)&v590 + 1) > 7u )
    v1 = (__int128 *)v589;
  std::wstring::_Construct<2,unsigned short const *>(v736, v1, v590);
  v737 = v591;
  v336 = 0;
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v336, L"AIKCertAcquiredExpired", 22);
  *(_QWORD *)&v288 = &v336;
  v584 = 4;
  v585 = 0;
  v586 = 0;
  v2 = &v336;
  if ( v338 > 7 )
    v2 = (__int128 *)v336;
  std::wstring::_Construct<2,unsigned short const *>(&v585, v2, v337);
  v587 = 4;
  std::wstring::~wstring(&v336);
  v738 = 1;
  v739 = v584;
  v740 = 0;
  v741 = 0;
  v742 = 0;
  v3 = &v585;
  if ( *((_QWORD *)&v586 + 1) > 7u )
    v3 = (__int128 *)v585;
  std::wstring::_Construct<2,unsigned short const *>(&v740, v3, v586);
  v743 = v587;
  v339 = 0;
  v340 = 0;
  v341 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v339, L"AIKEnrollmentErrorCode", 22);
  *(_QWORD *)&v288 = &v339;
  v580 = 4;
  v581 = 0;
  v582 = 0;
  v4 = &v339;
  if ( v341 > 7 )
    v4 = (__int128 *)v339;
  std::wstring::_Construct<2,unsigned short const *>(&v581, v4, v340);
  v583 = 4;
  std::wstring::~wstring(&v339);
  v744 = 2;
  v745 = v580;
  memset(v746, 0, sizeof(v746));
  v5 = &v581;
  if ( *((_QWORD *)&v582 + 1) > 7u )
    v5 = (__int128 *)v581;
  std::wstring::_Construct<2,unsigned short const *>(v746, v5, v582);
  v747 = v583;
  v342 = 0;
  v343 = 0;
  v344 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v342, L"ClearReason", 11);
  *(_QWORD *)&v288 = &v342;
  v576 = 3;
  v577 = 0;
  v578 = 0;
  v6 = &v342;
  if ( v344 > 7 )
    v6 = (__int128 *)v342;
  std::wstring::_Construct<2,unsigned short const *>(&v577, v6, v343);
  v579 = 1;
  std::wstring::~wstring(&v342);
  v748 = 3;
  v749 = v576;
  v750 = 0;
  v751 = 0;
  v752 = 0;
  v7 = &v577;
  if ( *((_QWORD *)&v578 + 1) > 7u )
    v7 = (__int128 *)v577;
  std::wstring::_Construct<2,unsigned short const *>(&v750, v7, v578);
  v753 = v579;
  v345 = 0;
  v346 = 0;
  v347 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v345, L"EkCertCorrelationId", 19);
  *(_QWORD *)&v288 = &v345;
  v572 = 9;
  v573 = 0;
  v574 = 0;
  v8 = &v345;
  if ( v347 > 7 )
    v8 = (__int128 *)v345;
  std::wstring::_Construct<2,unsigned short const *>(&v573, v8, v346);
  v575 = 1;
  std::wstring::~wstring(&v345);
  v754 = 12;
  v755 = v572;
  memset(v756, 0, sizeof(v756));
  v9 = &v573;
  if ( *((_QWORD *)&v574 + 1) > 7u )
    v9 = (__int128 *)v573;
  std::wstring::_Construct<2,unsigned short const *>(v756, v9, v574);
  v757 = v575;
  v348 = 0;
  v349 = 0;
  v350 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v348, L"EkCertNvFailureStep", 19);
  *(_QWORD *)&v288 = &v348;
  v568 = 9;
  v569 = 0;
  v570 = 0;
  v10 = &v348;
  if ( v350 > 7 )
    v10 = (__int128 *)v348;
  std::wstring::_Construct<2,unsigned short const *>(&v569, v10, v349);
  v571 = 4;
  std::wstring::~wstring(&v348);
  v758 = 13;
  v759 = v568;
  v760 = 0;
  v761 = 0;
  v762 = 0;
  v11 = &v569;
  if ( *((_QWORD *)&v570 + 1) > 7u )
    v11 = (__int128 *)v569;
  std::wstring::_Construct<2,unsigned short const *>(&v760, v11, v570);
  v763 = v571;
  v351 = 0;
  v352 = 0;
  v353 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v351, L"EkCertFetchSupport", 18);
  *(_QWORD *)&v288 = &v351;
  v564 = 9;
  v565 = 0;
  v566 = 0;
  v12 = &v351;
  if ( v353 > 7 )
    v12 = (__int128 *)v351;
  std::wstring::_Construct<2,unsigned short const *>(&v565, v12, v352);
  v567 = 4;
  std::wstring::~wstring(&v351);
  v764 = 14;
  v765 = v564;
  memset(v766, 0, sizeof(v766));
  v13 = &v565;
  if ( *((_QWORD *)&v566 + 1) > 7u )
    v13 = (__int128 *)v565;
  std::wstring::_Construct<2,unsigned short const *>(v766, v13, v566);
  v767 = v567;
  v354 = 0;
  v355 = 0;
  v356 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v354, L"EkCertIndex", 11);
  *(_QWORD *)&v288 = &v354;
  v560 = 9;
  v561 = 0;
  v562 = 0;
  v14 = &v354;
  if ( v356 > 7 )
    v14 = (__int128 *)v354;
  std::wstring::_Construct<2,unsigned short const *>(&v561, v14, v355);
  v563 = 4;
  std::wstring::~wstring(&v354);
  v768 = 15;
  v769 = v560;
  v770 = 0;
  v771 = 0;
  v772 = 0;
  v15 = &v561;
  if ( *((_QWORD *)&v562 + 1) > 7u )
    v15 = (__int128 *)v561;
  std::wstring::_Construct<2,unsigned short const *>(&v770, v15, v562);
  v773 = v563;
  v357 = 0;
  v358 = 0;
  v359 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v357, L"EkCertPath", 10);
  *(_QWORD *)&v288 = &v357;
  v556 = 9;
  v557 = 0;
  v558 = 0;
  v16 = &v357;
  if ( v359 > 7 )
    v16 = (__int128 *)v357;
  std::wstring::_Construct<2,unsigned short const *>(&v557, v16, v358);
  v559 = 4;
  std::wstring::~wstring(&v357);
  v774 = 16;
  v775 = v556;
  memset(v776, 0, sizeof(v776));
  v17 = &v557;
  if ( *((_QWORD *)&v558 + 1) > 7u )
    v17 = (__int128 *)v557;
  std::wstring::_Construct<2,unsigned short const *>(v776, v17, v558);
  v777 = v559;
  v360 = 0;
  v361 = 0;
  v362 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v360, L"EkCertProvisionResult", 21);
  *(_QWORD *)&v288 = &v360;
  v552 = 9;
  v553 = 0;
  v554 = 0;
  v18 = &v360;
  if ( v362 > 7 )
    v18 = (__int128 *)v360;
  std::wstring::_Construct<2,unsigned short const *>(&v553, v18, v361);
  v555 = 4;
  std::wstring::~wstring(&v360);
  v778 = 17;
  v779 = v552;
  v780 = 0;
  v781 = 0;
  v782 = 0;
  v19 = &v553;
  if ( *((_QWORD *)&v554 + 1) > 7u )
    v19 = (__int128 *)v553;
  std::wstring::_Construct<2,unsigned short const *>(&v780, v19, v554);
  v783 = v555;
  v363 = 0;
  v364 = 0;
  v365 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v363, L"EkCertRescheduleTaskFailureStep", 31);
  *(_QWORD *)&v288 = &v363;
  v548 = 9;
  v549 = 0;
  v550 = 0;
  v20 = &v363;
  if ( v365 > 7 )
    v20 = (__int128 *)v363;
  std::wstring::_Construct<2,unsigned short const *>(&v549, v20, v364);
  v551 = 4;
  std::wstring::~wstring(&v363);
  v784 = 18;
  v785 = v548;
  memset(v786, 0, sizeof(v786));
  v21 = &v549;
  if ( *((_QWORD *)&v550 + 1) > 7u )
    v21 = (__int128 *)v549;
  std::wstring::_Construct<2,unsigned short const *>(v786, v21, v550);
  v787 = v551;
  v366 = 0;
  v367 = 0;
  v368 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v366, L"EkCertRetrieveCertFailureStep", 29);
  *(_QWORD *)&v288 = &v366;
  v544 = 9;
  v545 = 0;
  v546 = 0;
  v22 = &v366;
  if ( v368 > 7 )
    v22 = (__int128 *)v366;
  std::wstring::_Construct<2,unsigned short const *>(&v545, v22, v367);
  v547 = 4;
  std::wstring::~wstring(&v366);
  v788 = 19;
  v789 = v544;
  v790 = 0;
  v791 = 0;
  v792 = 0;
  v23 = &v545;
  if ( *((_QWORD *)&v546 + 1) > 7u )
    v23 = (__int128 *)v545;
  std::wstring::_Construct<2,unsigned short const *>(&v790, v23, v546);
  v793 = v547;
  v369 = 0;
  v370 = 0;
  v371 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v369, L"EkCertsCleanedUp", 16);
  *(_QWORD *)&v288 = &v369;
  v540 = 9;
  v541 = 0;
  v542 = 0;
  v24 = &v369;
  if ( v371 > 7 )
    v24 = (__int128 *)v369;
  std::wstring::_Construct<2,unsigned short const *>(&v541, v24, v370);
  v543 = 4;
  std::wstring::~wstring(&v369);
  v794 = 20;
  v795 = v540;
  memset(v796, 0, sizeof(v796));
  v25 = &v541;
  if ( *((_QWORD *)&v542 + 1) > 7u )
    v25 = (__int128 *)v541;
  std::wstring::_Construct<2,unsigned short const *>(v796, v25, v542);
  v797 = v543;
  v372 = 0;
  v373 = 0;
  v374 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v372, L"EkCertsInstalledFromNV", 22);
  *(_QWORD *)&v288 = &v372;
  v536 = 9;
  v537 = 0;
  v538 = 0;
  v26 = &v372;
  if ( v374 > 7 )
    v26 = (__int128 *)v372;
  std::wstring::_Construct<2,unsigned short const *>(&v537, v26, v373);
  v539 = 4;
  std::wstring::~wstring(&v372);
  v798 = 21;
  v799 = v536;
  v800 = 0;
  v801 = 0;
  v802 = 0;
  v27 = &v537;
  if ( *((_QWORD *)&v538 + 1) > 7u )
    v27 = (__int128 *)v537;
  std::wstring::_Construct<2,unsigned short const *>(&v800, v27, v538);
  v803 = v539;
  v375 = 0;
  v376 = 0;
  v377 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v375, L"EkCreatePersistResult", 21);
  *(_QWORD *)&v288 = &v375;
  v532 = 9;
  v533 = 0;
  v534 = 0;
  v28 = &v375;
  if ( v377 > 7 )
    v28 = (__int128 *)v375;
  std::wstring::_Construct<2,unsigned short const *>(&v533, v28, v376);
  v535 = 4;
  std::wstring::~wstring(&v375);
  v804 = 22;
  v805 = v532;
  memset(v806, 0, sizeof(v806));
  v29 = &v533;
  if ( *((_QWORD *)&v534 + 1) > 7u )
    v29 = (__int128 *)v533;
  std::wstring::_Construct<2,unsigned short const *>(v806, v29, v534);
  v807 = v535;
  v330 = 0;
  v331 = 0;
  v332 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v330, L"EKCorrelationId", 15);
  *(_QWORD *)&v288 = &v330;
  v528 = 6;
  v529 = 0;
  v530 = 0;
  v30 = &v330;
  if ( v332 > 7 )
    v30 = (__int128 *)v330;
  std::wstring::_Construct<2,unsigned short const *>(&v529, v30, v331);
  v531 = 1;
  std::wstring::~wstring(&v330);
  v808 = 4;
  v809 = v528;
  v810 = 0;
  v811 = 0;
  v812 = 0;
  v31 = &v529;
  if ( *((_QWORD *)&v530 + 1) > 7u )
    v31 = (__int128 *)v529;
  std::wstring::_Construct<2,unsigned short const *>(&v810, v31, v530);
  v813 = v531;
  v381 = 0;
  v382 = 0;
  v383 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v381, L"EkFirstTimeout", 14);
  v728 = 6;
  v729 = 0;
  v730 = 0;
  v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v381, v32, v382);
  std::wstring::_Construct<2,unsigned short const *>(&v729, v33, v34);
  v731 = 4;
  std::wstring::~wstring(&v381);
  v814 = 5;
  v815 = v728;
  memset(v816, 0, sizeof(v816));
  v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v729, v35, v730);
  std::wstring::_Construct<2,unsigned short const *>(v816, v36, v37);
  v817 = v731;
  v384 = 0;
  v385 = 0;
  v386 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v384, L"EkMaxTries", 10);
  v724 = 6;
  v725 = 0;
  v726 = 0;
  v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v384, v38, v385);
  std::wstring::_Construct<2,unsigned short const *>(&v725, v39, v40);
  v727 = 4;
  std::wstring::~wstring(&v384);
  v818 = 6;
  v819 = v724;
  v820 = 0;
  v821 = 0;
  v822 = 0;
  v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v725, v41, v726);
  std::wstring::_Construct<2,unsigned short const *>(&v820, v42, v43);
  v823 = v727;
  v387 = 0;
  v388 = 0;
  v389 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v387, L"EkNoFetch", 9);
  v720 = 6;
  v721 = 0;
  v722 = 0;
  v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v387, v44, v388);
  std::wstring::_Construct<2,unsigned short const *>(&v721, v45, v46);
  v723 = 4;
  std::wstring::~wstring(&v387);
  v824 = 7;
  v825 = v720;
  memset(v826, 0, sizeof(v826));
  v48 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v721, v47, v722);
  std::wstring::_Construct<2,unsigned short const *>(v826, v48, v49);
  v827 = v723;
  v390 = 0;
  v391 = 0;
  v392 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v390, L"EKNonce", 7);
  v716 = 6;
  v717 = 0;
  v718 = 0;
  v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v390, v50, v391);
  std::wstring::_Construct<2,unsigned short const *>(&v717, v51, v52);
  v719 = 3;
  std::wstring::~wstring(&v390);
  v828 = 8;
  v829 = v716;
  v830 = 0;
  v831 = 0;
  v832 = 0;
  v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v717, v53, v718);
  std::wstring::_Construct<2,unsigned short const *>(&v830, v54, v55);
  v833 = v719;
  v393 = 0;
  v394 = 0;
  v395 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v393, L"EkPub", 5);
  v712 = 6;
  v713 = 0;
  v714 = 0;
  v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v393, v56, v394);
  std::wstring::_Construct<2,unsigned short const *>(&v713, v57, v58);
  v715 = 3;
  std::wstring::~wstring(&v393);
  v834 = 9;
  v835 = v712;
  memset(v836, 0, sizeof(v836));
  v60 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v713, v59, v714);
  std::wstring::_Construct<2,unsigned short const *>(v836, v60, v61);
  v837 = v715;
  v396 = 0;
  v397 = 0;
  v398 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v396, L"EkRetryLast", 11);
  v708 = 6;
  v709 = 0;
  v710 = 0;
  v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v396, v62, v397);
  std::wstring::_Construct<2,unsigned short const *>(&v709, v63, v64);
  v711 = 11;
  std::wstring::~wstring(&v396);
  v838 = 10;
  v839 = v708;
  v840 = 0;
  v841 = 0;
  v842 = 0;
  v66 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v709, v65, v710);
  std::wstring::_Construct<2,unsigned short const *>(&v840, v66, v67);
  v843 = v711;
  v399 = 0;
  v400 = 0;
  v401 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v399, L"EkTries", 7);
  v704 = 6;
  v705 = 0;
  v706 = 0;
  v69 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v399, v68, v400);
  std::wstring::_Construct<2,unsigned short const *>(&v705, v69, v70);
  v707 = 4;
  std::wstring::~wstring(&v399);
  v844 = 11;
  v845 = v704;
  memset(v846, 0, sizeof(v846));
  v72 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v705, v71, v706);
  std::wstring::_Construct<2,unsigned short const *>(v846, v72, v73);
  v847 = v707;
  v402 = 0;
  v403 = 0;
  v404 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v402, L"EnableInterruptSupport", 22);
  v700 = 1;
  v701 = 0;
  v702 = 0;
  v75 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v402, v74, v403);
  std::wstring::_Construct<2,unsigned short const *>(&v701, v75, v76);
  v703 = 4;
  std::wstring::~wstring(&v402);
  v848 = 23;
  v849 = v700;
  v850 = 0;
  v851 = 0;
  v852 = 0;
  v78 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v701, v77, v702);
  std::wstring::_Construct<2,unsigned short const *>(&v850, v78, v79);
  v853 = v703;
  v405 = 0;
  v406 = 0;
  v407 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v405, L"EndorsementAuth", 15);
  v696 = 6;
  v697 = 0;
  v698 = 0;
  v81 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v405, v80, v406);
  std::wstring::_Construct<2,unsigned short const *>(&v697, v81, v82);
  v699 = 1;
  std::wstring::~wstring(&v405);
  v854 = 24;
  v855 = v696;
  memset(v856, 0, sizeof(v856));
  v84 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v697, v83, v698);
  std::wstring::_Construct<2,unsigned short const *>(v856, v84, v85);
  v857 = v699;
  v408 = 0;
  v409 = 0;
  v410 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v408, L"FasrCapable", 11);
  v692 = 8;
  v693 = 0;
  v694 = 0;
  v87 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v408, v86, v409);
  std::wstring::_Construct<2,unsigned short const *>(&v693, v87, v88);
  v695 = 4;
  std::wstring::~wstring(&v408);
  v858 = 27;
  v859 = v692;
  v860 = 0;
  v861 = 0;
  v862 = 0;
  v90 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v693, v89, v694);
  std::wstring::_Construct<2,unsigned short const *>(&v860, v90, v91);
  v863 = v695;
  v411 = 0;
  v412 = 0;
  v413 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v411, L"FasrCustomBootPath", 18);
  v688 = 8;
  v689 = 0;
  v690 = 0;
  v93 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v411, v92, v412);
  std::wstring::_Construct<2,unsigned short const *>(&v689, v93, v94);
  v691 = 4;
  std::wstring::~wstring(&v411);
  v864 = 28;
  v865 = v688;
  memset(v866, 0, sizeof(v866));
  v96 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v689, v95, v690);
  std::wstring::_Construct<2,unsigned short const *>(v866, v96, v97);
  v867 = v691;
  v414 = 0;
  v415 = 0;
  v416 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v414, L"FasrCustomBootPathReasons", 25);
  v684 = 8;
  v685 = 0;
  v686 = 0;
  v99 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v414, v98, v415);
  std::wstring::_Construct<2,unsigned short const *>(&v685, v99, v100);
  v687 = 1;
  std::wstring::~wstring(&v414);
  v868 = 29;
  v869 = v684;
  v870 = 0;
  v871 = 0;
  v872 = 0;
  v102 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v685, v101, v686);
  std::wstring::_Construct<2,unsigned short const *>(&v870, v102, v103);
  v873 = v687;
  v417 = 0;
  v418 = 0;
  v419 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v417, L"FasrFwVersion", 13);
  v680 = 8;
  v681 = 0;
  v682 = 0;
  v105 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v417, v104, v418);
  std::wstring::_Construct<2,unsigned short const *>(&v681, v105, v106);
  v683 = 1;
  std::wstring::~wstring(&v417);
  v874 = 30;
  v875 = v680;
  memset(v876, 0, sizeof(v876));
  v108 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v681, v107, v682);
  std::wstring::_Construct<2,unsigned short const *>(v876, v108, v109);
  v877 = v683;
  v420 = 0;
  v421 = 0;
  v422 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v420, L"FasrProdImage", 13);
  v676 = 8;
  v677 = 0;
  v678 = 0;
  v111 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v420, v110, v421);
  std::wstring::_Construct<2,unsigned short const *>(&v677, v111, v112);
  v679 = 4;
  std::wstring::~wstring(&v420);
  v878 = 31;
  v879 = v676;
  v880 = 0;
  v881 = 0;
  v882 = 0;
  v114 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v677, v113, v678);
  std::wstring::_Construct<2,unsigned short const *>(&v880, v114, v115);
  v883 = v679;
  v423 = 0;
  v424 = 0;
  v425 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v423, L"TcgSecureBootValue", 18);
  v672 = 8;
  v673 = 0;
  v674 = 0;
  v117 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v423, v116, v424);
  std::wstring::_Construct<2,unsigned short const *>(&v673, v117, v118);
  v675 = 4;
  std::wstring::~wstring(&v423);
  v884 = 34;
  v885 = v672;
  memset(v886, 0, sizeof(v886));
  v120 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v673, v119, v674);
  std::wstring::_Construct<2,unsigned short const *>(v886, v120, v121);
  v887 = v675;
  v426 = 0;
  v427 = 0;
  v428 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v426, L"TcgHvciStatus", 13);
  v668 = 8;
  v669 = 0;
  v670 = 0;
  v123 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v426, v122, v427);
  std::wstring::_Construct<2,unsigned short const *>(&v669, v123, v124);
  v671 = 11;
  std::wstring::~wstring(&v426);
  v888 = 33;
  v889 = v668;
  v890 = 0;
  v891 = 0;
  v892 = 0;
  v126 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v669, v125, v670);
  std::wstring::_Construct<2,unsigned short const *>(&v890, v126, v127);
  v893 = v671;
  v429 = 0;
  v430 = 0;
  v431 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v429, L"TcgSmmIsolationLevel", 20);
  v664 = 8;
  v665 = 0;
  v666 = 0;
  v129 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v429, v128, v430);
  std::wstring::_Construct<2,unsigned short const *>(&v665, v129, v130);
  v667 = 4;
  std::wstring::~wstring(&v429);
  v894 = 35;
  v895 = v664;
  memset(v896, 0, sizeof(v896));
  v132 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v665, v131, v666);
  std::wstring::_Construct<2,unsigned short const *>(v896, v132, v133);
  v897 = v667;
  v432 = 0;
  v433 = 0;
  v434 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v432, L"TcgDrtmEnabled", 14);
  v660 = 8;
  v661 = 0;
  v662 = 0;
  v135 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v432, v134, v433);
  std::wstring::_Construct<2,unsigned short const *>(&v661, v135, v136);
  v663 = 4;
  std::wstring::~wstring(&v432);
  v898 = 32;
  v899 = v660;
  v900 = 0;
  v901 = 0;
  v902 = 0;
  v138 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v661, v137, v662);
  std::wstring::_Construct<2,unsigned short const *>(&v900, v138, v139);
  v903 = v663;
  v435 = 0;
  v436 = 0;
  v437 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v435, L"EkCertificatePresent", 20);
  v656 = 8;
  v657 = 0;
  v658 = 0;
  v141 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v435, v140, v436);
  std::wstring::_Construct<2,unsigned short const *>(&v657, v141, v142);
  v659 = 4;
  std::wstring::~wstring(&v435);
  v904 = 25;
  v905 = v656;
  memset(v906, 0, sizeof(v906));
  v144 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v657, v143, v658);
  std::wstring::_Construct<2,unsigned short const *>(v906, v144, v145);
  v907 = v659;
  v438 = 0;
  v439 = 0;
  v440 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v438, L"EccEkCertificatePresent", 23);
  v652 = 8;
  v653 = 0;
  v654 = 0;
  v147 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v438, v146, v439);
  std::wstring::_Construct<2,unsigned short const *>(&v653, v147, v148);
  v655 = 4;
  std::wstring::~wstring(&v438);
  v908 = 26;
  v909 = v652;
  v910 = 0;
  v911 = 0;
  v912 = 0;
  v150 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v653, v149, v654);
  std::wstring::_Construct<2,unsigned short const *>(&v910, v150, v151);
  v913 = v655;
  v441 = 0;
  v442 = 0;
  v443 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v441, L"MaintenanceTaskComplete", 23);
  v648 = 8;
  v649 = 0;
  v650 = 0;
  v153 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v441, v152, v442);
  std::wstring::_Construct<2,unsigned short const *>(&v649, v153, v154);
  v651 = 4;
  std::wstring::~wstring(&v441);
  v914 = 36;
  v915 = v648;
  memset(v916, 0, sizeof(v916));
  v156 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v649, v155, v650);
  std::wstring::_Construct<2,unsigned short const *>(v916, v156, v157);
  v917 = v651;
  v444 = 0;
  v445 = 0;
  v446 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v444, L"OwnerAuthEndorsementPresent", 27);
  v644 = 8;
  v645 = 0;
  v646 = 0;
  v159 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v444, v158, v445);
  std::wstring::_Construct<2,unsigned short const *>(&v645, v159, v160);
  v647 = 4;
  std::wstring::~wstring(&v444);
  v918 = 37;
  v919 = v644;
  v920 = 0;
  v921 = 0;
  v922 = 0;
  v162 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v645, v161, v646);
  std::wstring::_Construct<2,unsigned short const *>(&v920, v162, v163);
  v923 = v647;
  v447 = 0;
  v448 = 0;
  v449 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v447, L"PCR7BindingState", 16);
  v640 = 8;
  v641 = 0;
  v642 = 0;
  v165 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v447, v164, v448);
  std::wstring::_Construct<2,unsigned short const *>(&v641, v165, v166);
  v643 = 4;
  std::wstring::~wstring(&v447);
  v924 = 38;
  v925 = v640;
  memset(v926, 0, sizeof(v926));
  v168 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v641, v167, v642);
  std::wstring::_Construct<2,unsigned short const *>(v926, v168, v169);
  v927 = v643;
  v450 = 0;
  v451 = 0;
  v452 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v450, L"TpmProvisionFailedSteps", 23);
  v636 = 8;
  v637 = 0;
  v638 = 0;
  v171 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v450, v170, v451);
  std::wstring::_Construct<2,unsigned short const *>(&v637, v171, v172);
  v639 = 4;
  std::wstring::~wstring(&v450);
  v928 = 39;
  v929 = v636;
  v930 = 0;
  v931 = 0;
  v932 = 0;
  v174 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v637, v173, v638);
  std::wstring::_Construct<2,unsigned short const *>(&v930, v174, v175);
  v933 = v639;
  v453 = 0;
  v454 = 0;
  v455 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v453, L"TpmProvisionHresult", 19);
  v632 = 8;
  v633 = 0;
  v634 = 0;
  v177 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v453, v176, v454);
  std::wstring::_Construct<2,unsigned short const *>(&v633, v177, v178);
  v635 = 4;
  std::wstring::~wstring(&v453);
  v934 = 40;
  v935 = v632;
  memset(v936, 0, sizeof(v936));
  v180 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v633, v179, v634);
  std::wstring::_Construct<2,unsigned short const *>(v936, v180, v181);
  v937 = v635;
  v456 = 0;
  v457 = 0;
  v458 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v456, L"HASEndpoint", 11);
  v628 = 7;
  v629 = 0;
  v630 = 0;
  v183 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v456, v182, v457);
  std::wstring::_Construct<2,unsigned short const *>(&v629, v183, v184);
  v631 = 1;
  std::wstring::~wstring(&v456);
  v938 = 41;
  v939 = v628;
  v940 = 0;
  v941 = 0;
  v942 = 0;
  v186 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v629, v185, v630);
  std::wstring::_Construct<2,unsigned short const *>(&v940, v186, v187);
  v943 = v631;
  v459 = 0;
  v460 = 0;
  v461 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v459, L"EnrollmentID", 12);
  v624 = 7;
  v625 = 0;
  v626 = 0;
  v189 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v459, v188, v460);
  std::wstring::_Construct<2,unsigned short const *>(&v625, v189, v190);
  v627 = 1;
  std::wstring::~wstring(&v459);
  v944 = 42;
  v945 = v624;
  memset(v946, 0, sizeof(v946));
  v192 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v625, v191, v626);
  std::wstring::_Construct<2,unsigned short const *>(v946, v192, v193);
  v947 = v627;
  v462 = 0;
  v463 = 0;
  v464 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v462, L"SignedHealthCert", 16);
  v620 = 7;
  v621 = 0;
  v622 = 0;
  v195 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v462, v194, v463);
  std::wstring::_Construct<2,unsigned short const *>(&v621, v195, v196);
  v623 = 3;
  std::wstring::~wstring(&v462);
  v948 = 43;
  v949 = v620;
  v950 = 0;
  v951 = 0;
  v952 = 0;
  v198 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v621, v197, v622);
  std::wstring::_Construct<2,unsigned short const *>(&v950, v198, v199);
  v953 = v623;
  v465 = 0;
  v466 = 0;
  v467 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v465, L"Status", 6);
  v616 = 7;
  v617 = 0;
  v618 = 0;
  v201 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v465, v200, v466);
  std::wstring::_Construct<2,unsigned short const *>(&v617, v201, v202);
  v619 = 4;
  std::wstring::~wstring(&v465);
  v954 = 44;
  v955 = v616;
  memset(v956, 0, sizeof(v956));
  v204 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v617, v203, v618);
  std::wstring::_Construct<2,unsigned short const *>(v956, v204, v205);
  v957 = v619;
  v468 = 0;
  v469 = 0;
  v470 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v468, L"IntermediateCertsInstalledFromNV", 32);
  v612 = 9;
  v613 = 0;
  v614 = 0;
  v207 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v468, v206, v469);
  std::wstring::_Construct<2,unsigned short const *>(&v613, v207, v208);
  v615 = 4;
  std::wstring::~wstring(&v468);
  v958 = 45;
  v959 = v612;
  v960 = 0;
  v961 = 0;
  v962 = 0;
  v210 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v613, v209, v614);
  std::wstring::_Construct<2,unsigned short const *>(&v960, v210, v211);
  v963 = v615;
  v471 = 0;
  v472 = 0;
  v473 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v471, L"IsActiveZeroExhaust", 19);
  v608 = 4;
  v609 = 0;
  v610 = 0;
  v213 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v471, v212, v472);
  std::wstring::_Construct<2,unsigned short const *>(&v609, v213, v214);
  v611 = 4;
  std::wstring::~wstring(&v471);
  v964 = 46;
  v965 = v608;
  memset(v966, 0, sizeof(v966));
  v216 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v609, v215, v610);
  std::wstring::_Construct<2,unsigned short const *>(v966, v216, v217);
  v967 = v611;
  v474 = 0;
  v475 = 0;
  v476 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v474, L"LastAuthLevel", 13);
  v604 = 5;
  v605 = 0;
  v606 = 0;
  v219 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v474, v218, v475);
  std::wstring::_Construct<2,unsigned short const *>(&v605, v219, v220);
  v607 = 4;
  std::wstring::~wstring(&v474);
  v968 = 47;
  v969 = v604;
  v970 = 0;
  v971 = 0;
  v972 = 0;
  v222 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v605, v221, v606);
  std::wstring::_Construct<2,unsigned short const *>(&v970, v222, v223);
  v973 = v607;
  v477 = 0;
  v478 = 0;
  v479 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v477, L"LastEccEKCertStoreCount", 23);
  v600 = 3;
  v601 = 0;
  v602 = 0;
  v225 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v477, v224, v478);
  std::wstring::_Construct<2,unsigned short const *>(&v601, v225, v226);
  v603 = 4;
  std::wstring::~wstring(&v477);
  v974 = 48;
  v975 = v600;
  memset(v976, 0, sizeof(v976));
  v228 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v601, v227, v602);
  std::wstring::_Construct<2,unsigned short const *>(v976, v228, v229);
  v977 = v603;
  v480 = 0;
  v481 = 0;
  v482 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v480, L"LastEkPub", 9);
  v596 = 3;
  v597 = 0;
  v598 = 0;
  v231 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v480, v230, v481);
  std::wstring::_Construct<2,unsigned short const *>(&v597, v231, v232);
  v599 = 3;
  std::wstring::~wstring(&v480);
  v978 = 49;
  v979 = v596;
  v980 = 0;
  v981 = 0;
  v982 = 0;
  v234 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v597, v233, v598);
  std::wstring::_Construct<2,unsigned short const *>(&v980, v234, v235);
  v983 = v599;
  v483 = 0;
  v484 = 0;
  v485 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v483, L"LastPPIRequest", 14);
  v592 = 4;
  v593 = 0;
  v594 = 0;
  v237 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v483, v236, v484);
  std::wstring::_Construct<2,unsigned short const *>(&v593, v237, v238);
  v595 = 4;
  std::wstring::~wstring(&v483);
  v984 = 50;
  v985 = v592;
  memset(v986, 0, sizeof(v986));
  v240 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v593, v239, v594);
  std::wstring::_Construct<2,unsigned short const *>(v986, v240, v241);
  v987 = v595;
  v378 = 0;
  v379 = 0;
  v380 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v378, L"LastPPIResponseHandled", 22);
  *(_QWORD *)&v288 = &v378;
  v732 = 5;
  memset(v733, 0, sizeof(v733));
  v243 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v378, v242, v379);
  std::wstring::_Construct<2,unsigned short const *>(v733, v243, v244);
  v734 = 4;
  std::wstring::~wstring(&v378);
  v988 = 51;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v989,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)&v732);
  v245 = std::wstring::wstring(v487, L"LastRsaEKCertStoreCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1071, 3, v245, 4);
  v319 = 52;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v990,
    &v319,
    v1071);
  v246 = std::wstring::wstring(v488, L"LastRsaEkCertThumbprint");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1070, 3, v246, 1);
  v289 = 53;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v991,
    &v289,
    v1070);
  v247 = std::wstring::wstring(v489, L"LastTPMProvisionedBootId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1069, 3, v247, 4);
  v290 = 54;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v992,
    &v290,
    v1069);
  v248 = std::wstring::wstring(v490, L"LastTPMProvisionedTime");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1068, 3, v248, 11);
  v291 = 55;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v993,
    &v291,
    v1068);
  v249 = std::wstring::wstring(v491, L"LockoutHash");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1067, 5, v249, 1);
  v292 = 56;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v994,
    &v292,
    v1067);
  v250 = std::wstring::wstring(v492, L"NoAutoProvision");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1066, 4, v250, 4);
  v293 = 57;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v995,
    &v293,
    v1066);
  v251 = std::wstring::wstring(v493, L"NoOOBECheck");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1065, 4, v251, 4);
  v294 = 58;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v996,
    &v294,
    v1065);
  v252 = std::wstring::wstring(v494, L"NoResourceVirtualizationOnNextReboot");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1064, 5, v252, 4);
  v295 = 59;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v997,
    &v295,
    v1064);
  v253 = std::wstring::wstring(v495, L"UseNullDerivedOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1063, 4, v253, 4);
  v296 = 60;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v998,
    &v296,
    v1063);
  v254 = std::wstring::wstring(v496, L"UseNullDerivedOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1062, 0, v254, 4);
  v297 = 61;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v999,
    &v297,
    v1062);
  v255 = std::wstring::wstring(v497, L"OsBootCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1061, 1, v255, 4);
  v298 = 62;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1000,
    &v298,
    v1061);
  v256 = std::wstring::wstring(v498, L"OsResumeCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1060, 15, v256, 4);
  v299 = 63;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1001,
    &v299,
    v1060);
  v257 = std::wstring::wstring(v499, L"OSManagedAuthLevel");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1059, 0, v257, 4);
  v300 = 64;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1002,
    &v300,
    v1059);
  v258 = std::wstring::wstring(v500, L"OverrideEkCertIndex");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1058, 6, v258, 4);
  v301 = 65;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1003,
    &v301,
    v1058);
  v259 = std::wstring::wstring(v501, L"OwnerAuthFull");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1057, 5, v259, 1);
  v302 = 66;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1004,
    &v302,
    v1057);
  v260 = std::wstring::wstring(v502, L"OwnerAuthNew");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1056, 5, v260, 1);
  v303 = 67;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1005,
    &v303,
    v1056);
  v261 = std::wstring::wstring(v503, L"OwnerAuthStatus");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1055, 5, v261, 4);
  v304 = 68;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1006,
    &v304,
    v1055);
  v262 = std::wstring::wstring(v504, L"PlatformLogRetention");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1054, 1, v262, 4);
  v305 = 69;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1007,
    &v305,
    v1054);
  v263 = std::wstring::wstring(v505, L"PreAttHCFileError");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1053, 8, v263, 4);
  v306 = 70;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1008,
    &v306,
    v1053);
  v264 = std::wstring::wstring(v506, L"RsaPssSaltLengthType");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1052, 4, v264, 4);
  v307 = 77;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1009,
    &v307,
    v1052);
  v265 = std::wstring::wstring(v507, L"SRKPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1051, 5, v265, 3);
  v308 = 78;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1010,
    &v308,
    v1051);
  v266 = std::wstring::wstring(v508, L"TaskFirmwareVersion");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1050, 4, v266, 1);
  v309 = 71;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1011,
    &v309,
    v1050);
  v267 = std::wstring::wstring(v509, L"TaskInformationFlags");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1049, 4, v267, 4);
  v310 = 72;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1012,
    &v310,
    v1049);
  v268 = std::wstring::wstring(v510, L"TaskManufacturerId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1048, 4, v268, 4);
  v311 = 73;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1013,
    &v311,
    v1048);
  v269 = std::wstring::wstring(v511, L"TaskOsBuildNumber");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1047, 4, v269, 1);
  v312 = 74;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1014,
    &v312,
    v1047);
  v270 = std::wstring::wstring(v512, L"TaskReadyForAttestation");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1046, 4, v270, 4);
  v313 = 75;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1015,
    &v313,
    v1046);
  v271 = std::wstring::wstring(v513, L"TaskReadyForStorage");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1045, 4, v271, 4);
  v314 = 76;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1016,
    &v314,
    v1045);
  v272 = std::wstring::wstring(v514, L"StorageOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1072, 5, v272, 1);
  v315 = 79;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1017,
    &v315,
    v1072);
  v273 = std::wstring::wstring(v515, L"TotalTPMProvisioningCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1044, 3, v273, 4);
  v316 = 80;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1018,
    &v316,
    v1044);
  v274 = std::wstring::wstring(v516, L"TpmBackedDeviceID");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1043, 4, v274, 4);
  v317 = 81;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1019,
    &v317,
    v1043);
  v275 = std::wstring::wstring(v517, L"TPMCleared");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1042, 5, v275, 4);
  v318 = 82;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1020,
    &v318,
    v1042);
  v276 = std::wstring::wstring(v518, L"UseLegacyDictionaryAttackParameters");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1041, 0, v276, 4);
  v324 = 83;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1021,
    &v324,
    v1041);
  v277 = std::wstring::wstring(v519, L"WBCLPath");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1040, 1, v277, 1);
  v320 = 84;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1022,
    &v320,
    v1040);
  v278 = std::wstring::wstring(v520, L"Windows AIK");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1039, 2, v278, 3);
  v321 = 85;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1023,
    &v321,
    v1039);
  v279 = std::wstring::wstring(v521, L"WindowsAIKBinding");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1038, 4, v279, 3);
  v322 = 86;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1024,
    &v322,
    v1038);
  v280 = std::wstring::wstring(v522, L"WindowsAikCheckCreateResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1037, 9, v280, 4);
  v323 = 87;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1025,
    &v323,
    v1037);
  v281 = std::wstring::wstring(v523, L"WindowsAikCorrelationId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1036, 9, v281, 1);
  v328 = 88;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1026,
    &v328,
    v1036);
  v282 = std::wstring::wstring(v524, L"WindowsAikEnrollReason");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1035, 9, v282, 4);
  v325 = 89;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1027,
    &v325,
    v1035);
  v283 = std::wstring::wstring(v525, L"WindowsAikEnrollResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1034, 9, v283, 4);
  v326 = 90;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1028,
    &v326,
    v1034);
  v284 = std::wstring::wstring(v526, L"WindowsAIKHash");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1033, 4, v284, 3);
  v327 = 91;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1029,
    &v327,
    v1033);
  v285 = std::wstring::wstring(v527, L"WindowsAIKPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(v1032, 4, v285, 3);
  v329 = 92;
  std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>(
    v1030,
    &v329,
    v1032);
  v288 = *(_OWORD *)std::initializer_list<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>::initializer_list<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>(
                      v486,
                      v735,
                      v1031);
  std::map<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry>::map<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry>(
    v286,
    &v288);
  `eh vector destructor iterator'(
    v735,
    0x38u,
    0x5Du,
    std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::~pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1032);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1033);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1034);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1035);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1036);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1037);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1038);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1039);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1040);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1041);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1042);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1043);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1044);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1072);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1045);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1046);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1047);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1048);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1049);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1050);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1051);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1052);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1053);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1054);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1055);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1056);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1057);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1058);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1059);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1060);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1061);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1062);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1063);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1064);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1065);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1066);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1067);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1068);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1069);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1070);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)v1071);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v732);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v592);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v596);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v600);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v604);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v608);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v612);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v616);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v620);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v624);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v628);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v632);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v636);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v640);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v644);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v648);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v652);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v656);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v660);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v664);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v668);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v672);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v676);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v680);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v684);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v688);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v692);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v696);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v700);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v704);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v708);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v712);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v716);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v720);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v724);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v728);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v528);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v532);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v536);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v540);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v544);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v548);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v552);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v556);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v560);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v564);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v568);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v572);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v576);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v580);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v584);
  HWSecurityRegistryManager::RegistryValueEntry::~RegistryValueEntry((HWSecurityRegistryManager::RegistryValueEntry *)&v588);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegValueTable__);
}

```

## disassembly

```asm
0x180011660  mov     [rsp-8+arg_0], rbx
0x180011665  push    rbp
0x180011666  lea     rbp, [rsp-3170h]
0x18001166e  mov     eax, 3270h
0x180011673  call    _alloca_probe
0x180011678  sub     rsp, rax
0x18001167b  mov     rax, cs:__security_cookie
0x180011682  xor     rax, rsp
0x180011685  mov     [rbp+3170h+var_10], rax
0x18001168c  xorps   xmm0, xmm0
0x18001168f  movups  [rbp+3170h+var_3178], xmm0
0x180011693  xor     ebx, ebx
0x180011695  mov     [rbp+3170h+var_3168], rbx
0x180011699  mov     [rbp+3170h+var_3160], rbx
0x18001169d  mov     r8d, 1Bh
0x1800116a3  lea     rdx, aActivedirector; "ActiveDirectoryBackupSrkPub"
0x1800116aa  lea     rcx, [rbp+3170h+var_3178]
0x1800116ae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800116b3  lea     rax, [rbp+3170h+var_3178]
0x1800116b7  mov     qword ptr [rsp+3270h+var_3250], rax
0x1800116bc  mov     [rbp+3170h+var_2318], 5
0x1800116c6  xorps   xmm0, xmm0
0x1800116c9  movups  [rbp+3170h+var_2310], xmm0
0x1800116d0  xorps   xmm1, xmm1
0x1800116d3  movdqu  [rbp+3170h+var_2300], xmm1
0x1800116db  lea     rdx, [rbp+3170h+var_3178]
0x1800116df  cmp     [rbp+3170h+var_3160], 7
0x1800116e4  cmova   rdx, qword ptr [rbp+3170h+var_3178]
0x1800116e9  mov     r8, [rbp+3170h+var_3168]
0x1800116ed  lea     rcx, [rbp+3170h+var_2310]
0x1800116f4  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800116f9  mov     [rbp+3170h+var_22F0], 3
0x180011703  lea     rcx, [rbp+3170h+var_3178]
0x180011707  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001170c  nop
0x18001170d  mov     [rbp+3170h+var_1C20], ebx
0x180011713  mov     eax, [rbp+3170h+var_2318]
0x180011719  mov     [rbp+3170h+var_1C18], eax
0x18001171f  xorps   xmm0, xmm0
0x180011722  movups  [rbp+3170h+var_1C10], xmm0
0x180011729  xorps   xmm1, xmm1
0x18001172c  movdqa  [rbp+3170h+var_1C00], xmm1
0x180011734  lea     rdx, [rbp+3170h+var_2310]
0x18001173b  cmp     qword ptr [rbp+3170h+var_2300+8], 7
0x180011743  cmova   rdx, qword ptr [rbp+3170h+var_2310]
0x18001174b  mov     r8, qword ptr [rbp+3170h+var_2300]
0x180011752  lea     rcx, [rbp+3170h+var_1C10]
0x180011759  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001175e  mov     eax, [rbp+3170h+var_22F0]
0x180011764  mov     [rbp+3170h+var_1BF0], eax
0x18001176a  xorps   xmm0, xmm0
0x18001176d  movups  [rbp+3170h+var_3158], xmm0
0x180011771  mov     [rbp+3170h+var_3148], rbx
0x180011775  mov     [rbp+3170h+var_3140], rbx
0x180011779  mov     r8d, 16h
0x18001177f  lea     rdx, aAikcertacquire; "AIKCertAcquiredExpired"
0x180011786  lea     rcx, [rbp+3170h+var_3158]
0x18001178a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001178f  lea     rax, [rbp+3170h+var_3158]
0x180011793  mov     qword ptr [rsp+3270h+var_3250], rax
0x180011798  mov     [rbp+3170h+var_2348], 4
0x1800117a2  xorps   xmm0, xmm0
0x1800117a5  movups  [rbp+3170h+var_2340], xmm0
0x1800117ac  xorps   xmm1, xmm1
0x1800117af  movdqu  [rbp+3170h+var_2330], xmm1
0x1800117b7  lea     rdx, [rbp+3170h+var_3158]
0x1800117bb  cmp     [rbp+3170h+var_3140], 7
0x1800117c0  cmova   rdx, qword ptr [rbp+3170h+var_3158]
0x1800117c5  mov     r8, [rbp+3170h+var_3148]
0x1800117c9  lea     rcx, [rbp+3170h+var_2340]
0x1800117d0  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800117d5  mov     [rbp+3170h+var_2320], 4
0x1800117df  lea     rcx, [rbp+3170h+var_3158]
0x1800117e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800117e8  nop
0x1800117e9  mov     [rbp+3170h+var_1BE8], 1
0x1800117f3  mov     eax, [rbp+3170h+var_2348]
0x1800117f9  mov     [rbp+3170h+var_1BE0], eax
0x1800117ff  xorps   xmm0, xmm0
0x180011802  movups  [rbp+3170h+var_1BD8], xmm0
0x180011809  mov     [rbp+3170h+var_1BC8], rbx
0x180011810  mov     [rbp+3170h+var_1BC0], rbx
0x180011817  lea     rdx, [rbp+3170h+var_2340]
0x18001181e  cmp     qword ptr [rbp+3170h+var_2330+8], 7
0x180011826  cmova   rdx, qword ptr [rbp+3170h+var_2340]
0x18001182e  mov     r8, qword ptr [rbp+3170h+var_2330]
0x180011835  lea     rcx, [rbp+3170h+var_1BD8]
0x18001183c  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011841  mov     eax, [rbp+3170h+var_2320]
0x180011847  mov     [rbp+3170h+var_1BB8], eax
0x18001184d  xorps   xmm0, xmm0
0x180011850  movups  [rbp+3170h+var_3138], xmm0
0x180011854  mov     [rbp+3170h+var_3128], rbx
0x180011858  mov     [rbp+3170h+var_3120], rbx
0x18001185c  mov     r8d, 16h
0x180011862  lea     rdx, aAikenrollmente; "AIKEnrollmentErrorCode"
0x180011869  lea     rcx, [rbp+3170h+var_3138]
0x18001186d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011872  lea     rax, [rbp+3170h+var_3138]
0x180011876  mov     qword ptr [rsp+3270h+var_3250], rax
0x18001187b  mov     [rbp+3170h+var_2378], 4
0x180011885  xorps   xmm0, xmm0
0x180011888  movups  [rbp+3170h+var_2370], xmm0
0x18001188f  xorps   xmm1, xmm1
0x180011892  movdqu  [rbp+3170h+var_2360], xmm1
0x18001189a  lea     rdx, [rbp+3170h+var_3138]
0x18001189e  cmp     [rbp+3170h+var_3120], 7
0x1800118a3  cmova   rdx, qword ptr [rbp+3170h+var_3138]
0x1800118a8  mov     r8, [rbp+3170h+var_3128]
0x1800118ac  lea     rcx, [rbp+3170h+var_2370]
0x1800118b3  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800118b8  mov     [rbp+3170h+var_2350], 4
0x1800118c2  lea     rcx, [rbp+3170h+var_3138]
0x1800118c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800118cb  nop
0x1800118cc  mov     [rbp+3170h+var_1BB0], 2
0x1800118d6  mov     eax, [rbp+3170h+var_2378]
0x1800118dc  mov     [rbp+3170h+var_1BA8], eax
0x1800118e2  xorps   xmm0, xmm0
0x1800118e5  movups  [rbp+3170h+var_1BA0], xmm0
0x1800118ec  xorps   xmm1, xmm1
0x1800118ef  movdqa  [rbp+3170h+var_1B90], xmm1
0x1800118f7  lea     rdx, [rbp+3170h+var_2370]
0x1800118fe  cmp     qword ptr [rbp+3170h+var_2360+8], 7
0x180011906  cmova   rdx, qword ptr [rbp+3170h+var_2370]
0x18001190e  mov     r8, qword ptr [rbp+3170h+var_2360]
0x180011915  lea     rcx, [rbp+3170h+var_1BA0]
0x18001191c  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011921  mov     eax, [rbp+3170h+var_2350]
0x180011927  mov     [rbp+3170h+var_1B80], eax
0x18001192d  xorps   xmm0, xmm0
0x180011930  movups  [rbp+3170h+var_3118], xmm0
0x180011934  mov     [rbp+3170h+var_3108], rbx
0x180011938  mov     [rbp+3170h+var_3100], rbx
0x18001193c  mov     r8d, 0Bh
0x180011942  lea     rdx, aClearreason; "ClearReason"
0x180011949  lea     rcx, [rbp+3170h+var_3118]
0x18001194d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011952  lea     rax, [rbp+3170h+var_3118]
0x180011956  mov     qword ptr [rsp+3270h+var_3250], rax
0x18001195b  mov     [rbp+3170h+var_23A8], 3
0x180011965  xorps   xmm0, xmm0
0x180011968  movups  [rbp+3170h+var_23A0], xmm0
0x18001196f  xorps   xmm1, xmm1
0x180011972  movdqu  [rbp+3170h+var_2390], xmm1
0x18001197a  lea     rdx, [rbp+3170h+var_3118]
0x18001197e  cmp     [rbp+3170h+var_3100], 7
0x180011983  cmova   rdx, qword ptr [rbp+3170h+var_3118]
0x180011988  mov     r8, [rbp+3170h+var_3108]
0x18001198c  lea     rcx, [rbp+3170h+var_23A0]
0x180011993  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011998  mov     [rbp+3170h+var_2380], 1
0x1800119a2  lea     rcx, [rbp+3170h+var_3118]
0x1800119a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800119ab  nop
0x1800119ac  mov     [rbp+3170h+var_1B78], 3
0x1800119b6  mov     eax, [rbp+3170h+var_23A8]
0x1800119bc  mov     [rbp+3170h+var_1B70], eax
0x1800119c2  xorps   xmm0, xmm0
0x1800119c5  movups  [rbp+3170h+var_1B68], xmm0
0x1800119cc  mov     [rbp+3170h+var_1B58], rbx
0x1800119d3  mov     [rbp+3170h+var_1B50], rbx
0x1800119da  lea     rdx, [rbp+3170h+var_23A0]
0x1800119e1  cmp     qword ptr [rbp+3170h+var_2390+8], 7
0x1800119e9  cmova   rdx, qword ptr [rbp+3170h+var_23A0]
0x1800119f1  mov     r8, qword ptr [rbp+3170h+var_2390]
0x1800119f8  lea     rcx, [rbp+3170h+var_1B68]
0x1800119ff  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011a04  mov     eax, [rbp+3170h+var_2380]
0x180011a0a  mov     [rbp+3170h+var_1B48], eax
0x180011a10  xorps   xmm0, xmm0
0x180011a13  movups  [rbp+3170h+var_30F8], xmm0
0x180011a17  mov     [rbp+3170h+var_30E8], rbx
0x180011a1e  mov     [rbp+3170h+var_30E0], rbx
0x180011a25  mov     r8d, 13h
0x180011a2b  lea     rdx, aEkcertcorrelat; "EkCertCorrelationId"
0x180011a32  lea     rcx, [rbp+3170h+var_30F8]
0x180011a36  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011a3b  lea     rax, [rbp+3170h+var_30F8]
0x180011a3f  mov     qword ptr [rsp+3270h+var_3250], rax
0x180011a44  mov     [rbp+3170h+var_23D8], 9
0x180011a4e  xorps   xmm0, xmm0
0x180011a51  movups  [rbp+3170h+var_23D0], xmm0
0x180011a58  xorps   xmm1, xmm1
0x180011a5b  movdqu  [rbp+3170h+var_23C0], xmm1
0x180011a63  lea     rdx, [rbp+3170h+var_30F8]
0x180011a67  cmp     [rbp+3170h+var_30E0], 7
0x180011a6f  cmova   rdx, qword ptr [rbp+3170h+var_30F8]
0x180011a74  mov     r8, [rbp+3170h+var_30E8]
0x180011a7b  lea     rcx, [rbp+3170h+var_23D0]
0x180011a82  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011a87  mov     [rbp+3170h+var_23B0], 1
0x180011a91  lea     rcx, [rbp+3170h+var_30F8]
0x180011a95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011a9a  nop
0x180011a9b  mov     [rbp+3170h+var_1B40], 0Ch
0x180011aa5  mov     eax, [rbp+3170h+var_23D8]
0x180011aab  mov     [rbp+3170h+var_1B38], eax
0x180011ab1  xorps   xmm0, xmm0
0x180011ab4  movups  [rbp+3170h+var_1B30], xmm0
0x180011abb  xorps   xmm1, xmm1
0x180011abe  movdqa  [rbp+3170h+var_1B20], xmm1
0x180011ac6  lea     rdx, [rbp+3170h+var_23D0]
0x180011acd  cmp     qword ptr [rbp+3170h+var_23C0+8], 7
0x180011ad5  cmova   rdx, qword ptr [rbp+3170h+var_23D0]
0x180011add  mov     r8, qword ptr [rbp+3170h+var_23C0]
0x180011ae4  lea     rcx, [rbp+3170h+var_1B30]
0x180011aeb  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011af0  mov     eax, [rbp+3170h+var_23B0]
0x180011af6  mov     [rbp+3170h+var_1B10], eax
0x180011afc  xorps   xmm0, xmm0
0x180011aff  movups  [rbp+3170h+var_30D8], xmm0
0x180011b06  mov     [rbp+3170h+var_30C8], rbx
0x180011b0d  mov     [rbp+3170h+var_30C0], rbx
0x180011b14  mov     r8d, 13h
0x180011b1a  lea     rdx, aEkcertnvfailur; "EkCertNvFailureStep"
0x180011b21  lea     rcx, [rbp+3170h+var_30D8]
0x180011b28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011b2d  lea     rax, [rbp+3170h+var_30D8]
0x180011b34  mov     qword ptr [rsp+3270h+var_3250], rax
0x180011b39  mov     [rbp+3170h+var_2408], 9
0x180011b43  xorps   xmm0, xmm0
0x180011b46  movups  [rbp+3170h+var_2400], xmm0
0x180011b4d  xorps   xmm1, xmm1
0x180011b50  movdqu  [rbp+3170h+var_23F0], xmm1
0x180011b58  lea     rdx, [rbp+3170h+var_30D8]
0x180011b5f  cmp     [rbp+3170h+var_30C0], 7
0x180011b67  cmova   rdx, qword ptr [rbp+3170h+var_30D8]
0x180011b6f  mov     r8, [rbp+3170h+var_30C8]
0x180011b76  lea     rcx, [rbp+3170h+var_2400]
0x180011b7d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011b82  mov     [rbp+3170h+var_23E0], 4
0x180011b8c  lea     rcx, [rbp+3170h+var_30D8]
0x180011b93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b98  nop
0x180011b99  mov     [rbp+3170h+var_1B08], 0Dh
0x180011ba3  mov     eax, [rbp+3170h+var_2408]
0x180011ba9  mov     [rbp+3170h+var_1B00], eax
0x180011baf  xorps   xmm0, xmm0
0x180011bb2  movups  [rbp+3170h+var_1AF8], xmm0
0x180011bb9  mov     [rbp+3170h+var_1AE8], rbx
0x180011bc0  mov     [rbp+3170h+var_1AE0], rbx
0x180011bc7  lea     rdx, [rbp+3170h+var_2400]
0x180011bce  cmp     qword ptr [rbp+3170h+var_23F0+8], 7
0x180011bd6  cmova   rdx, qword ptr [rbp+3170h+var_2400]
0x180011bde  mov     r8, qword ptr [rbp+3170h+var_23F0]
0x180011be5  lea     rcx, [rbp+3170h+var_1AF8]
0x180011bec  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011bf1  mov     eax, [rbp+3170h+var_23E0]
0x180011bf7  mov     [rbp+3170h+var_1AD8], eax
0x180011bfd  xorps   xmm0, xmm0
0x180011c00  movups  [rbp+3170h+var_30B8], xmm0
0x180011c07  mov     [rbp+3170h+var_30A8], rbx
0x180011c0e  mov     [rbp+3170h+var_30A0], rbx
0x180011c15  mov     r8d, 12h
0x180011c1b  lea     rdx, aEkcertfetchsup; "EkCertFetchSupport"
0x180011c22  lea     rcx, [rbp+3170h+var_30B8]
0x180011c29  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011c2e  lea     rax, [rbp+3170h+var_30B8]
0x180011c35  mov     qword ptr [rsp+3270h+var_3250], rax
0x180011c3a  mov     [rbp+3170h+var_2438], 9
0x180011c44  xorps   xmm0, xmm0
0x180011c47  movups  [rbp+3170h+var_2430], xmm0
0x180011c4e  xorps   xmm1, xmm1
0x180011c51  movdqu  [rbp+3170h+var_2420], xmm1
0x180011c59  lea     rdx, [rbp+3170h+var_30B8]
0x180011c60  cmp     [rbp+3170h+var_30A0], 7
0x180011c68  cmova   rdx, qword ptr [rbp+3170h+var_30B8]
0x180011c70  mov     r8, [rbp+3170h+var_30A8]
0x180011c77  lea     rcx, [rbp+3170h+var_2430]
0x180011c7e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011c83  mov     [rbp+3170h+var_2410], 4
0x180011c8d  lea     rcx, [rbp+3170h+var_30B8]
0x180011c94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c99  nop
0x180011c9a  mov     [rbp+3170h+var_1AD0], 0Eh
0x180011ca4  mov     eax, [rbp+3170h+var_2438]
0x180011caa  mov     [rbp+3170h+var_1AC8], eax
0x180011cb0  xorps   xmm0, xmm0
0x180011cb3  movups  [rbp+3170h+var_1AC0], xmm0
0x180011cba  xorps   xmm1, xmm1
0x180011cbd  movdqa  [rbp+3170h+var_1AB0], xmm1
0x180011cc5  lea     rdx, [rbp+3170h+var_2430]
0x180011ccc  cmp     qword ptr [rbp+3170h+var_2420+8], 7
0x180011cd4  cmova   rdx, qword ptr [rbp+3170h+var_2430]
0x180011cdc  mov     r8, qword ptr [rbp+3170h+var_2420]
0x180011ce3  lea     rcx, [rbp+3170h+var_1AC0]
0x180011cea  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011cef  mov     eax, [rbp+3170h+var_2410]
0x180011cf5  mov     [rbp+3170h+var_1AA0], eax
0x180011cfb  xorps   xmm0, xmm0
0x180011cfe  movups  [rbp+3170h+var_3098], xmm0
0x180011d05  mov     [rbp+3170h+var_3088], rbx
0x180011d0c  mov     [rbp+3170h+var_3080], rbx
0x180011d13  mov     r8d, 0Bh
0x180011d19  lea     rdx, aEkcertindex; "EkCertIndex"
0x180011d20  lea     rcx, [rbp+3170h+var_3098]
0x180011d27  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011d2c  lea     rax, [rbp+3170h+var_3098]
0x180011d33  mov     qword ptr [rsp+3270h+var_3250], rax
  ... truncated ...
```
