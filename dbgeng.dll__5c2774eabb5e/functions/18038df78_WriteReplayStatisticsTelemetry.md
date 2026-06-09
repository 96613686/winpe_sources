# WriteReplayStatisticsTelemetry

- ea: `0x18038df78`
- end: `0x18039437f`
- name: `WriteReplayStatisticsTelemetry`
- size: `25607`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bfa2c`

## callees

- `0x1800010d0`
- `0x18000110c`
- `0x180001768`
- `0x18000182c`
- `0x18000191c`
- `0x1800cdadc`
- `0x180159910`
- `0x1801b8c2c`
- `0x18038df78`
- `0x18041b530`

## string_xrefs

- `0x18038e83c`: `ForwardFastReplayEventTimesThread`
- `0x18038ef86`: `ForwardScheduledReplayTime`
- `0x18038f32b`: `ForwardScheduledReplayEventTimesMemoryWatchpoint`
- `0x18038f462`: `ForwardScheduledReplayEventTimesPositionWatchpoint`
- `0x18038f0bd`: `ForwardScheduledReplaySegmentsExecuted`
- `0x18038f1f4`: `ForwardScheduledReplayStepsExecuted`
- `0x18038f807`: `ForwardScheduledReplayEventTimesThread`
- `0x18038f93e`: `ForwardScheduledReplayEventTimesStepCount`
- `0x18038f599`: `ForwardScheduledReplayEventTimesException`
- `0x18038f6d0`: `ForwardScheduledReplayEventTimesGap`
- `0x18038fce3`: `ForwardScheduledReplayEventTimesInterrupted`
- `0x18038fe1a`: `ForwardScheduledReplayEventTimesError`
- `0x18038fa75`: `ForwardScheduledReplayEventTimesPosition`
- `0x18038fbac`: `ForwardScheduledReplayEventTimesProcess`
- `0x180390641`: `ForwardSegmentExecutionEventTimesThread`
- `0x180391761`: `BackwardFastReplayEventTimesThread`
- `0x180391fcb`: `BackwardScheduledReplayTime`
- `0x180392400`: `BackwardScheduledReplayEventTimesMemoryWatchpoint`
- `0x180392567`: `BackwardScheduledReplayEventTimesPositionWatchpoint`
- `0x180392132`: `BackwardScheduledReplaySegmentsExecuted`
- `0x180392299`: `BackwardScheduledReplayStepsExecuted`
- `0x18039299c`: `BackwardScheduledReplayEventTimesThread`
- `0x180392b03`: `BackwardScheduledReplayEventTimesStepCount`
- `0x1803926ce`: `BackwardScheduledReplayEventTimesException`
- `0x180392835`: `BackwardScheduledReplayEventTimesGap`
- `0x180392f38`: `BackwardScheduledReplayEventTimesInterrupted`
- `0x18039309f`: `BackwardScheduledReplayEventTimesError`
- `0x180392c6a`: `BackwardScheduledReplayEventTimesPosition`
- `0x180392dd1`: `BackwardScheduledReplayEventTimesProcess`
- `0x180393a70`: `BackwardSegmentExecutionEventTimesThread`

## pseudocode

```c
void __fastcall WriteReplayStatisticsTelemetry(__int64 *a1)
{
  __int64 *v1; // rdi
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rbx
  const char *v72; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+68h] [rbp-98h] BYREF
  __int64 v74; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h] BYREF
  __int64 v76; // [rsp+80h] [rbp-80h] BYREF
  __int64 v77; // [rsp+88h] [rbp-78h] BYREF
  __int64 v78; // [rsp+90h] [rbp-70h] BYREF
  const char *v79; // [rsp+98h] [rbp-68h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v82; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  const char *v86; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v88; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v90; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v91; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v92; // [rsp+100h] [rbp+0h] BYREF
  const char *v93; // [rsp+108h] [rbp+8h] BYREF
  __int64 v94; // [rsp+110h] [rbp+10h] BYREF
  __int64 v95; // [rsp+118h] [rbp+18h] BYREF
  __int64 v96; // [rsp+120h] [rbp+20h] BYREF
  __int64 v97; // [rsp+128h] [rbp+28h] BYREF
  __int64 v98; // [rsp+130h] [rbp+30h] BYREF
  __int64 v99; // [rsp+138h] [rbp+38h] BYREF
  const char *v100; // [rsp+140h] [rbp+40h] BYREF
  __int64 v101; // [rsp+148h] [rbp+48h] BYREF
  __int64 v102; // [rsp+150h] [rbp+50h] BYREF
  __int64 v103; // [rsp+158h] [rbp+58h] BYREF
  __int64 v104; // [rsp+160h] [rbp+60h] BYREF
  __int64 v105; // [rsp+168h] [rbp+68h] BYREF
  __int64 v106; // [rsp+170h] [rbp+70h] BYREF
  const char *v107; // [rsp+178h] [rbp+78h] BYREF
  __int64 v108; // [rsp+180h] [rbp+80h] BYREF
  __int64 v109; // [rsp+188h] [rbp+88h] BYREF
  __int64 v110; // [rsp+190h] [rbp+90h] BYREF
  __int64 v111; // [rsp+198h] [rbp+98h] BYREF
  __int64 v112; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v113; // [rsp+1A8h] [rbp+A8h] BYREF
  const char *v114; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v115; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v116; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v117; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v118; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v119; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v120; // [rsp+1E0h] [rbp+E0h] BYREF
  const char *v121; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v122; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v123; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v124; // [rsp+200h] [rbp+100h] BYREF
  __int64 v125; // [rsp+208h] [rbp+108h] BYREF
  __int64 v126; // [rsp+210h] [rbp+110h] BYREF
  __int64 v127; // [rsp+218h] [rbp+118h] BYREF
  const char *v128; // [rsp+220h] [rbp+120h] BYREF
  __int64 v129; // [rsp+228h] [rbp+128h] BYREF
  __int64 v130; // [rsp+230h] [rbp+130h] BYREF
  __int64 v131; // [rsp+238h] [rbp+138h] BYREF
  __int64 v132; // [rsp+240h] [rbp+140h] BYREF
  __int64 v133; // [rsp+248h] [rbp+148h] BYREF
  __int64 v134; // [rsp+250h] [rbp+150h] BYREF
  const char *v135; // [rsp+258h] [rbp+158h] BYREF
  __int64 v136; // [rsp+260h] [rbp+160h] BYREF
  __int64 v137; // [rsp+268h] [rbp+168h] BYREF
  __int64 v138; // [rsp+270h] [rbp+170h] BYREF
  __int64 v139; // [rsp+278h] [rbp+178h] BYREF
  __int64 v140; // [rsp+280h] [rbp+180h] BYREF
  __int64 v141; // [rsp+288h] [rbp+188h] BYREF
  const char *v142; // [rsp+290h] [rbp+190h] BYREF
  __int64 v143; // [rsp+298h] [rbp+198h] BYREF
  __int64 v144; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v145; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v146; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v147; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v148; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v149; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v150; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v151; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v152; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v153; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v154; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v155; // [rsp+2F8h] [rbp+1F8h] BYREF
  const char *v156; // [rsp+300h] [rbp+200h] BYREF
  __int64 v157; // [rsp+308h] [rbp+208h] BYREF
  __int64 v158; // [rsp+310h] [rbp+210h] BYREF
  __int64 v159; // [rsp+318h] [rbp+218h] BYREF
  __int64 v160; // [rsp+320h] [rbp+220h] BYREF
  __int64 v161; // [rsp+328h] [rbp+228h] BYREF
  __int64 v162; // [rsp+330h] [rbp+230h] BYREF
  const char *v163; // [rsp+338h] [rbp+238h] BYREF
  __int64 v164; // [rsp+340h] [rbp+240h] BYREF
  __int64 v165; // [rsp+348h] [rbp+248h] BYREF
  __int64 v166; // [rsp+350h] [rbp+250h] BYREF
  __int64 v167; // [rsp+358h] [rbp+258h] BYREF
  __int64 v168; // [rsp+360h] [rbp+260h] BYREF
  __int64 v169; // [rsp+368h] [rbp+268h] BYREF
  const char *v170; // [rsp+370h] [rbp+270h] BYREF
  __int64 v171; // [rsp+378h] [rbp+278h] BYREF
  __int64 v172; // [rsp+380h] [rbp+280h] BYREF
  __int64 v173; // [rsp+388h] [rbp+288h] BYREF
  __int64 v174; // [rsp+390h] [rbp+290h] BYREF
  __int64 v175; // [rsp+398h] [rbp+298h] BYREF
  __int64 v176; // [rsp+3A0h] [rbp+2A0h] BYREF
  const char *v177; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int64 v178; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v179; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int64 v180; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v181; // [rsp+3C8h] [rbp+2C8h] BYREF
  __int64 v182; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v183; // [rsp+3D8h] [rbp+2D8h] BYREF
  const char *v184; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int64 v185; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v186; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v187; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v188; // [rsp+400h] [rbp+300h] BYREF
  __int64 v189; // [rsp+408h] [rbp+308h] BYREF
  __int64 v190; // [rsp+410h] [rbp+310h] BYREF
  const char *v191; // [rsp+418h] [rbp+318h] BYREF
  __int64 v192; // [rsp+420h] [rbp+320h] BYREF
  __int64 v193; // [rsp+428h] [rbp+328h] BYREF
  __int64 v194; // [rsp+430h] [rbp+330h] BYREF
  __int64 v195; // [rsp+438h] [rbp+338h] BYREF
  __int64 v196; // [rsp+440h] [rbp+340h] BYREF
  __int64 v197; // [rsp+448h] [rbp+348h] BYREF
  const char *v198; // [rsp+450h] [rbp+350h] BYREF
  __int64 v199; // [rsp+458h] [rbp+358h] BYREF
  __int64 v200; // [rsp+460h] [rbp+360h] BYREF
  __int64 v201; // [rsp+468h] [rbp+368h] BYREF
  __int64 v202; // [rsp+470h] [rbp+370h] BYREF
  __int64 v203; // [rsp+478h] [rbp+378h] BYREF
  __int64 v204; // [rsp+480h] [rbp+380h] BYREF
  const char *v205; // [rsp+488h] [rbp+388h] BYREF
  __int64 v206; // [rsp+490h] [rbp+390h] BYREF
  __int64 v207; // [rsp+498h] [rbp+398h] BYREF
  __int64 v208; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v209; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int64 v210; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v211; // [rsp+4B8h] [rbp+3B8h] BYREF
  const char *v212; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v213; // [rsp+4C8h] [rbp+3C8h] BYREF
  __int64 v214; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v215; // [rsp+4D8h] [rbp+3D8h] BYREF
  __int64 v216; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v217; // [rsp+4E8h] [rbp+3E8h] BYREF
  __int64 v218; // [rsp+4F0h] [rbp+3F0h] BYREF
  const char *v219; // [rsp+4F8h] [rbp+3F8h] BYREF
  __int64 v220; // [rsp+500h] [rbp+400h] BYREF
  __int64 v221; // [rsp+508h] [rbp+408h] BYREF
  __int64 v222; // [rsp+510h] [rbp+410h] BYREF
  __int64 v223; // [rsp+518h] [rbp+418h] BYREF
  __int64 v224; // [rsp+520h] [rbp+420h] BYREF
  __int64 v225; // [rsp+528h] [rbp+428h] BYREF
  const char *v226; // [rsp+530h] [rbp+430h] BYREF
  __int64 v227; // [rsp+538h] [rbp+438h] BYREF
  __int64 v228; // [rsp+540h] [rbp+440h] BYREF
  __int64 v229; // [rsp+548h] [rbp+448h] BYREF
  __int64 v230; // [rsp+550h] [rbp+450h] BYREF
  __int64 v231; // [rsp+558h] [rbp+458h] BYREF
  __int64 v232; // [rsp+560h] [rbp+460h] BYREF
  const char *v233; // [rsp+568h] [rbp+468h] BYREF
  __int64 v234; // [rsp+570h] [rbp+470h] BYREF
  __int64 v235; // [rsp+578h] [rbp+478h] BYREF
  __int64 v236; // [rsp+580h] [rbp+480h] BYREF
  __int64 v237; // [rsp+588h] [rbp+488h] BYREF
  __int64 v238; // [rsp+590h] [rbp+490h] BYREF
  __int64 v239; // [rsp+598h] [rbp+498h] BYREF
  const char *v240; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v241; // [rsp+5A8h] [rbp+4A8h] BYREF
  __int64 v242; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v243; // [rsp+5B8h] [rbp+4B8h] BYREF
  __int64 v244; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int64 v245; // [rsp+5C8h] [rbp+4C8h] BYREF
  __int64 v246; // [rsp+5D0h] [rbp+4D0h] BYREF
  const char *v247; // [rsp+5D8h] [rbp+4D8h] BYREF
  __int64 v248; // [rsp+5E0h] [rbp+4E0h] BYREF
  __int64 v249; // [rsp+5E8h] [rbp+4E8h] BYREF
  __int64 v250; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v251; // [rsp+5F8h] [rbp+4F8h] BYREF
  __int64 v252; // [rsp+600h] [rbp+500h] BYREF
  __int64 v253; // [rsp+608h] [rbp+508h] BYREF
  const char *v254; // [rsp+610h] [rbp+510h] BYREF
  __int64 v255; // [rsp+618h] [rbp+518h] BYREF
  __int64 v256; // [rsp+620h] [rbp+520h] BYREF
  __int64 v257; // [rsp+628h] [rbp+528h] BYREF
  __int64 v258; // [rsp+630h] [rbp+530h] BYREF
  __int64 v259; // [rsp+638h] [rbp+538h] BYREF
  __int64 v260; // [rsp+640h] [rbp+540h] BYREF
  const char *v261; // [rsp+648h] [rbp+548h] BYREF
  __int64 v262; // [rsp+650h] [rbp+550h] BYREF
  __int64 v263; // [rsp+658h] [rbp+558h] BYREF
  __int64 v264; // [rsp+660h] [rbp+560h] BYREF
  __int64 v265; // [rsp+668h] [rbp+568h] BYREF
  __int64 v266; // [rsp+670h] [rbp+570h] BYREF
  __int64 v267; // [rsp+678h] [rbp+578h] BYREF
  const char *v268; // [rsp+680h] [rbp+580h] BYREF
  __int64 v269; // [rsp+688h] [rbp+588h] BYREF
  __int64 v270; // [rsp+690h] [rbp+590h] BYREF
  __int64 v271; // [rsp+698h] [rbp+598h] BYREF
  __int64 v272; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int64 v273; // [rsp+6A8h] [rbp+5A8h] BYREF
  __int64 v274; // [rsp+6B0h] [rbp+5B0h] BYREF
  const char *v275; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v276; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int64 v277; // [rsp+6C8h] [rbp+5C8h] BYREF
  __int64 v278; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v279; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v280; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int64 v281; // [rsp+6E8h] [rbp+5E8h] BYREF
  const char *v282; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v283; // [rsp+6F8h] [rbp+5F8h] BYREF
  __int64 v284; // [rsp+700h] [rbp+600h] BYREF
  __int64 v285; // [rsp+708h] [rbp+608h] BYREF
  __int64 v286; // [rsp+710h] [rbp+610h] BYREF
  __int64 v287; // [rsp+718h] [rbp+618h] BYREF
  __int64 v288; // [rsp+720h] [rbp+620h] BYREF
  const char *v289; // [rsp+728h] [rbp+628h] BYREF
  __int64 v290; // [rsp+730h] [rbp+630h] BYREF
  __int64 v291; // [rsp+738h] [rbp+638h] BYREF
  __int64 v292; // [rsp+740h] [rbp+640h] BYREF
  __int64 v293; // [rsp+748h] [rbp+648h] BYREF
  __int64 v294; // [rsp+750h] [rbp+650h] BYREF
  __int64 v295; // [rsp+758h] [rbp+658h] BYREF
  const char *v296; // [rsp+760h] [rbp+660h] BYREF
  __int64 v297; // [rsp+768h] [rbp+668h] BYREF
  __int64 v298; // [rsp+770h] [rbp+670h] BYREF
  __int64 v299; // [rsp+778h] [rbp+678h] BYREF
  __int64 v300; // [rsp+780h] [rbp+680h] BYREF
  __int64 v301; // [rsp+788h] [rbp+688h] BYREF
  __int64 v302; // [rsp+790h] [rbp+690h] BYREF
  const char *v303; // [rsp+798h] [rbp+698h] BYREF
  __int64 v304; // [rsp+7A0h] [rbp+6A0h] BYREF
  __int64 v305; // [rsp+7A8h] [rbp+6A8h] BYREF
  __int64 v306; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int64 v307; // [rsp+7B8h] [rbp+6B8h] BYREF
  __int64 v308; // [rsp+7C0h] [rbp+6C0h] BYREF
  __int64 v309; // [rsp+7C8h] [rbp+6C8h] BYREF
  const char *v310; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v311; // [rsp+7D8h] [rbp+6D8h] BYREF
  __int64 v312; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int64 v313; // [rsp+7E8h] [rbp+6E8h] BYREF
  __int64 v314; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v315; // [rsp+7F8h] [rbp+6F8h] BYREF
  __int64 v316; // [rsp+800h] [rbp+700h] BYREF
  const char *v317; // [rsp+808h] [rbp+708h] BYREF
  __int64 v318; // [rsp+810h] [rbp+710h] BYREF
  __int64 v319; // [rsp+818h] [rbp+718h] BYREF
  __int64 v320; // [rsp+820h] [rbp+720h] BYREF
  __int64 v321; // [rsp+828h] [rbp+728h] BYREF
  __int64 v322; // [rsp+830h] [rbp+730h] BYREF
  __int64 v323; // [rsp+838h] [rbp+738h] BYREF
  const char *v324; // [rsp+840h] [rbp+740h] BYREF
  __int64 v325; // [rsp+848h] [rbp+748h] BYREF
  __int64 v326; // [rsp+850h] [rbp+750h] BYREF
  __int64 v327; // [rsp+858h] [rbp+758h] BYREF
  __int64 v328; // [rsp+860h] [rbp+760h] BYREF
  __int64 v329; // [rsp+868h] [rbp+768h] BYREF
  __int64 v330; // [rsp+870h] [rbp+770h] BYREF
  const char *v331; // [rsp+878h] [rbp+778h] BYREF
  __int64 v332; // [rsp+880h] [rbp+780h] BYREF
  __int64 v333; // [rsp+888h] [rbp+788h] BYREF
  __int64 v334; // [rsp+890h] [rbp+790h] BYREF
  __int64 v335; // [rsp+898h] [rbp+798h] BYREF
  __int64 v336; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int64 v337; // [rsp+8A8h] [rbp+7A8h] BYREF
  const char *v338; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v339; // [rsp+8B8h] [rbp+7B8h] BYREF
  __int64 v340; // [rsp+8C0h] [rbp+7C0h] BYREF
  const char *v341; // [rsp+8C8h] [rbp+7C8h] BYREF
  __int64 v342; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v343; // [rsp+8D8h] [rbp+7D8h] BYREF
  const char *v344; // [rsp+8E0h] [rbp+7E0h] BYREF
  __int64 v345; // [rsp+8E8h] [rbp+7E8h] BYREF
  __int64 v346; // [rsp+8F0h] [rbp+7F0h] BYREF
  __int64 v347; // [rsp+8F8h] [rbp+7F8h] BYREF
  __int64 v348; // [rsp+900h] [rbp+800h] BYREF
  __int64 v349; // [rsp+908h] [rbp+808h] BYREF
  __int64 v350; // [rsp+910h] [rbp+810h] BYREF
  const char *v351; // [rsp+918h] [rbp+818h] BYREF
  __int64 v352; // [rsp+920h] [rbp+820h] BYREF
  __int64 v353; // [rsp+928h] [rbp+828h] BYREF
  __int64 v354; // [rsp+930h] [rbp+830h] BYREF
  __int64 v355; // [rsp+938h] [rbp+838h] BYREF
  __int64 v356; // [rsp+940h] [rbp+840h] BYREF
  __int64 v357; // [rsp+948h] [rbp+848h] BYREF
  const char *v358; // [rsp+950h] [rbp+850h] BYREF
  __int64 v359; // [rsp+958h] [rbp+858h] BYREF
  __int64 v360; // [rsp+960h] [rbp+860h] BYREF
  __int64 v361; // [rsp+968h] [rbp+868h] BYREF
  __int64 v362; // [rsp+970h] [rbp+870h] BYREF
  __int64 v363; // [rsp+978h] [rbp+878h] BYREF
  __int64 v364; // [rsp+980h] [rbp+880h] BYREF
  const char *v365; // [rsp+988h] [rbp+888h] BYREF
  __int64 v366; // [rsp+990h] [rbp+890h] BYREF
  __int64 v367; // [rsp+998h] [rbp+898h] BYREF
  __int64 v368; // [rsp+9A0h] [rbp+8A0h] BYREF
  _BYTE v369[8]; // [rsp+9A8h] [rbp+8A8h] BYREF
  _BYTE v370[8]; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v371[8]; // [rsp+9B8h] [rbp+8B8h] BYREF
  _BYTE v372[8]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v373[8]; // [rsp+9C8h] [rbp+8C8h] BYREF
  _BYTE v374[8]; // [rsp+9D0h] [rbp+8D0h] BYREF
  __int64 v375; // [rsp+9D8h] [rbp+8D8h] BYREF
  __int64 v376; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v377[8]; // [rsp+9E8h] [rbp+8E8h] BYREF
  _BYTE v378[8]; // [rsp+9F0h] [rbp+8F0h] BYREF
  _BYTE v379[8]; // [rsp+9F8h] [rbp+8F8h] BYREF
  _BYTE v380[8]; // [rsp+A00h] [rbp+900h] BYREF
  _BYTE v381[8]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v382[8]; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v383; // [rsp+A18h] [rbp+918h] BYREF
  __int64 v384; // [rsp+A20h] [rbp+920h] BYREF
  _BYTE v385[8]; // [rsp+A28h] [rbp+928h] BYREF
  _BYTE v386[8]; // [rsp+A30h] [rbp+930h] BYREF
  _BYTE v387[8]; // [rsp+A38h] [rbp+938h] BYREF
  _BYTE v388[8]; // [rsp+A40h] [rbp+940h] BYREF
  _BYTE v389[8]; // [rsp+A48h] [rbp+948h] BYREF
  _BYTE v390[8]; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v391; // [rsp+A58h] [rbp+958h] BYREF
  __int64 v392; // [rsp+A60h] [rbp+960h] BYREF
  _BYTE v393[8]; // [rsp+A68h] [rbp+968h] BYREF
  _BYTE v394[8]; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v395[8]; // [rsp+A78h] [rbp+978h] BYREF
  _BYTE v396[8]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v397[8]; // [rsp+A88h] [rbp+988h] BYREF
  _BYTE v398[8]; // [rsp+A90h] [rbp+990h] BYREF
  __int64 v399; // [rsp+A98h] [rbp+998h] BYREF
  __int64 v400; // [rsp+AA0h] [rbp+9A0h] BYREF
  _BYTE v401[8]; // [rsp+AA8h] [rbp+9A8h] BYREF
  _BYTE v402[8]; // [rsp+AB0h] [rbp+9B0h] BYREF
  _BYTE v403[8]; // [rsp+AB8h] [rbp+9B8h] BYREF
  _BYTE v404[8]; // [rsp+AC0h] [rbp+9C0h] BYREF
  _BYTE v405[8]; // [rsp+AC8h] [rbp+9C8h] BYREF
  _BYTE v406[8]; // [rsp+AD0h] [rbp+9D0h] BYREF
  __int64 v407; // [rsp+AD8h] [rbp+9D8h] BYREF
  __int64 v408; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v409[8]; // [rsp+AE8h] [rbp+9E8h] BYREF
  _BYTE v410[8]; // [rsp+AF0h] [rbp+9F0h] BYREF
  _BYTE v411[8]; // [rsp+AF8h] [rbp+9F8h] BYREF
  _BYTE v412[8]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v413[8]; // [rsp+B08h] [rbp+A08h] BYREF
  _BYTE v414[8]; // [rsp+B10h] [rbp+A10h] BYREF
  __int64 v415; // [rsp+B18h] [rbp+A18h] BYREF
  __int64 v416; // [rsp+B20h] [rbp+A20h] BYREF
  _BYTE v417[8]; // [rsp+B28h] [rbp+A28h] BYREF
  _BYTE v418[8]; // [rsp+B30h] [rbp+A30h] BYREF
  _BYTE v419[8]; // [rsp+B38h] [rbp+A38h] BYREF
  _BYTE v420[8]; // [rsp+B40h] [rbp+A40h] BYREF
  _BYTE v421[8]; // [rsp+B48h] [rbp+A48h] BYREF
  _BYTE v422[8]; // [rsp+B50h] [rbp+A50h] BYREF
  __int64 v423; // [rsp+B58h] [rbp+A58h] BYREF
  __int64 v424; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v425[8]; // [rsp+B68h] [rbp+A68h] BYREF
  _BYTE v426[8]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v427[8]; // [rsp+B78h] [rbp+A78h] BYREF
  _BYTE v428[8]; // [rsp+B80h] [rbp+A80h] BYREF
  _BYTE v429[8]; // [rsp+B88h] [rbp+A88h] BYREF
  _BYTE v430[8]; // [rsp+B90h] [rbp+A90h] BYREF
  __int64 v431; // [rsp+B98h] [rbp+A98h] BYREF
  __int64 v432; // [rsp+BA0h] [rbp+AA0h] BYREF
  _BYTE v433[8]; // [rsp+BA8h] [rbp+AA8h] BYREF
  _BYTE v434[8]; // [rsp+BB0h] [rbp+AB0h] BYREF
  _BYTE v435[8]; // [rsp+BB8h] [rbp+AB8h] BYREF
  _BYTE v436[8]; // [rsp+BC0h] [rbp+AC0h] BYREF
  _BYTE v437[8]; // [rsp+BC8h] [rbp+AC8h] BYREF
  _BYTE v438[8]; // [rsp+BD0h] [rbp+AD0h] BYREF
  __int64 v439; // [rsp+BD8h] [rbp+AD8h] BYREF
  __int64 v440; // [rsp+BE0h] [rbp+AE0h] BYREF
  _BYTE v441[8]; // [rsp+BE8h] [rbp+AE8h] BYREF
  _BYTE v442[8]; // [rsp+BF0h] [rbp+AF0h] BYREF
  _BYTE v443[8]; // [rsp+BF8h] [rbp+AF8h] BYREF
  _BYTE v444[8]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v445[8]; // [rsp+C08h] [rbp+B08h] BYREF
  _BYTE v446[8]; // [rsp+C10h] [rbp+B10h] BYREF
  __int64 v447; // [rsp+C18h] [rbp+B18h] BYREF
  __int64 v448; // [rsp+C20h] [rbp+B20h] BYREF
  _BYTE v449[8]; // [rsp+C28h] [rbp+B28h] BYREF
  _BYTE v450[8]; // [rsp+C30h] [rbp+B30h] BYREF
  _BYTE v451[8]; // [rsp+C38h] [rbp+B38h] BYREF
  _BYTE v452[8]; // [rsp+C40h] [rbp+B40h] BYREF
  _BYTE v453[8]; // [rsp+C48h] [rbp+B48h] BYREF
  _BYTE v454[8]; // [rsp+C50h] [rbp+B50h] BYREF
  __int64 v455; // [rsp+C58h] [rbp+B58h] BYREF
  __int64 v456; // [rsp+C60h] [rbp+B60h] BYREF
  _BYTE v457[8]; // [rsp+C68h] [rbp+B68h] BYREF
  _BYTE v458[8]; // [rsp+C70h] [rbp+B70h] BYREF
  _BYTE v459[8]; // [rsp+C78h] [rbp+B78h] BYREF
  _BYTE v460[8]; // [rsp+C80h] [rbp+B80h] BYREF
  _BYTE v461[8]; // [rsp+C88h] [rbp+B88h] BYREF
  _BYTE v462[8]; // [rsp+C90h] [rbp+B90h] BYREF
  __int64 v463; // [rsp+C98h] [rbp+B98h] BYREF
  __int64 v464; // [rsp+CA0h] [rbp+BA0h] BYREF
  _BYTE v465[8]; // [rsp+CA8h] [rbp+BA8h] BYREF
  _BYTE v466[8]; // [rsp+CB0h] [rbp+BB0h] BYREF
  _BYTE v467[8]; // [rsp+CB8h] [rbp+BB8h] BYREF
  _BYTE v468[8]; // [rsp+CC0h] [rbp+BC0h] BYREF
  _BYTE v469[8]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v470[8]; // [rsp+CD0h] [rbp+BD0h] BYREF
  __int64 v471; // [rsp+CD8h] [rbp+BD8h] BYREF
  __int64 v472; // [rsp+CE0h] [rbp+BE0h] BYREF
  _BYTE v473[8]; // [rsp+CE8h] [rbp+BE8h] BYREF
  _BYTE v474[8]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v475[8]; // [rsp+CF8h] [rbp+BF8h] BYREF
  _BYTE v476[8]; // [rsp+D00h] [rbp+C00h] BYREF
  _BYTE v477[8]; // [rsp+D08h] [rbp+C08h] BYREF
  _BYTE v478[8]; // [rsp+D10h] [rbp+C10h] BYREF
  __int64 v479; // [rsp+D18h] [rbp+C18h] BYREF
  __int64 v480; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v481[8]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v482[8]; // [rsp+D30h] [rbp+C30h] BYREF
  _BYTE v483[8]; // [rsp+D38h] [rbp+C38h] BYREF
  _BYTE v484[8]; // [rsp+D40h] [rbp+C40h] BYREF
  _BYTE v485[8]; // [rsp+D48h] [rbp+C48h] BYREF
  _BYTE v486[8]; // [rsp+D50h] [rbp+C50h] BYREF
  __int64 v487; // [rsp+D58h] [rbp+C58h] BYREF
  __int64 v488; // [rsp+D60h] [rbp+C60h] BYREF
  _BYTE v489[8]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v490[8]; // [rsp+D70h] [rbp+C70h] BYREF
  _BYTE v491[8]; // [rsp+D78h] [rbp+C78h] BYREF
  _BYTE v492[8]; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v493[8]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v494[8]; // [rsp+D90h] [rbp+C90h] BYREF
  __int64 v495; // [rsp+D98h] [rbp+C98h] BYREF
  __int64 v496; // [rsp+DA0h] [rbp+CA0h] BYREF
  _BYTE v497[8]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v498[8]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v499[8]; // [rsp+DB8h] [rbp+CB8h] BYREF
  _BYTE v500[8]; // [rsp+DC0h] [rbp+CC0h] BYREF
  _BYTE v501[8]; // [rsp+DC8h] [rbp+CC8h] BYREF
  _BYTE v502[8]; // [rsp+DD0h] [rbp+CD0h] BYREF
  __int64 v503; // [rsp+DD8h] [rbp+CD8h] BYREF
  __int64 v504; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v505[8]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v506[8]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _BYTE v507[8]; // [rsp+DF8h] [rbp+CF8h] BYREF
  _BYTE v508[8]; // [rsp+E00h] [rbp+D00h] BYREF
  _BYTE v509[8]; // [rsp+E08h] [rbp+D08h] BYREF
  _BYTE v510[8]; // [rsp+E10h] [rbp+D10h] BYREF
  __int64 v511; // [rsp+E18h] [rbp+D18h] BYREF
  __int64 v512; // [rsp+E20h] [rbp+D20h] BYREF
  _BYTE v513[8]; // [rsp+E28h] [rbp+D28h] BYREF
  _BYTE v514[8]; // [rsp+E30h] [rbp+D30h] BYREF
  _BYTE v515[8]; // [rsp+E38h] [rbp+D38h] BYREF
  _BYTE v516[8]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v517[8]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v518[8]; // [rsp+E50h] [rbp+D50h] BYREF
  __int64 v519; // [rsp+E58h] [rbp+D58h] BYREF
  __int64 v520; // [rsp+E60h] [rbp+D60h] BYREF
  _BYTE v521[8]; // [rsp+E68h] [rbp+D68h] BYREF
  _BYTE v522[8]; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v523[8]; // [rsp+E78h] [rbp+D78h] BYREF
  _BYTE v524[8]; // [rsp+E80h] [rbp+D80h] BYREF
  _BYTE v525[8]; // [rsp+E88h] [rbp+D88h] BYREF
  _BYTE v526[8]; // [rsp+E90h] [rbp+D90h] BYREF
  __int64 v527; // [rsp+E98h] [rbp+D98h] BYREF
  __int64 v528; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v529[8]; // [rsp+EA8h] [rbp+DA8h] BYREF
  _BYTE v530[8]; // [rsp+EB0h] [rbp+DB0h] BYREF
  _BYTE v531[8]; // [rsp+EB8h] [rbp+DB8h] BYREF
  _BYTE v532[8]; // [rsp+EC0h] [rbp+DC0h] BYREF
  _BYTE v533[8]; // [rsp+EC8h] [rbp+DC8h] BYREF
  _BYTE v534[8]; // [rsp+ED0h] [rbp+DD0h] BYREF
  __int64 v535; // [rsp+ED8h] [rbp+DD8h] BYREF
  __int64 v536; // [rsp+EE0h] [rbp+DE0h] BYREF
  _BYTE v537[8]; // [rsp+EE8h] [rbp+DE8h] BYREF
  _BYTE v538[8]; // [rsp+EF0h] [rbp+DF0h] BYREF
  _BYTE v539[8]; // [rsp+EF8h] [rbp+DF8h] BYREF
  _BYTE v540[8]; // [rsp+F00h] [rbp+E00h] BYREF
  _BYTE v541[8]; // [rsp+F08h] [rbp+E08h] BYREF
  _BYTE v542[8]; // [rsp+F10h] [rbp+E10h] BYREF
  __int64 v543; // [rsp+F18h] [rbp+E18h] BYREF
  __int64 v544; // [rsp+F20h] [rbp+E20h] BYREF
  _BYTE v545[8]; // [rsp+F28h] [rbp+E28h] BYREF
  _BYTE v546[8]; // [rsp+F30h] [rbp+E30h] BYREF
  _BYTE v547[8]; // [rsp+F38h] [rbp+E38h] BYREF
  _BYTE v548[8]; // [rsp+F40h] [rbp+E40h] BYREF
  _BYTE v549[8]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v550[8]; // [rsp+F50h] [rbp+E50h] BYREF
  __int64 v551; // [rsp+F58h] [rbp+E58h] BYREF
  __int64 v552; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v553[8]; // [rsp+F68h] [rbp+E68h] BYREF
  _BYTE v554[8]; // [rsp+F70h] [rbp+E70h] BYREF
  _BYTE v555[8]; // [rsp+F78h] [rbp+E78h] BYREF
  _BYTE v556[8]; // [rsp+F80h] [rbp+E80h] BYREF
  _BYTE v557[8]; // [rsp+F88h] [rbp+E88h] BYREF
  _BYTE v558[8]; // [rsp+F90h] [rbp+E90h] BYREF
  __int64 v559; // [rsp+F98h] [rbp+E98h] BYREF
  __int64 v560; // [rsp+FA0h] [rbp+EA0h] BYREF
  _BYTE v561[8]; // [rsp+FA8h] [rbp+EA8h] BYREF
  _BYTE v562[8]; // [rsp+FB0h] [rbp+EB0h] BYREF
  _BYTE v563[8]; // [rsp+FB8h] [rbp+EB8h] BYREF
  _BYTE v564[8]; // [rsp+FC0h] [rbp+EC0h] BYREF
  _BYTE v565[8]; // [rsp+FC8h] [rbp+EC8h] BYREF
  _BYTE v566[8]; // [rsp+FD0h] [rbp+ED0h] BYREF
  __int64 v567; // [rsp+FD8h] [rbp+ED8h] BYREF
  __int64 v568; // [rsp+FE0h] [rbp+EE0h] BYREF
  _BYTE v569[8]; // [rsp+FE8h] [rbp+EE8h] BYREF
  _BYTE v570[8]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v571[8]; // [rsp+FF8h] [rbp+EF8h] BYREF
  _BYTE v572[8]; // [rsp+1000h] [rbp+F00h] BYREF
  _BYTE v573[8]; // [rsp+1008h] [rbp+F08h] BYREF
  _BYTE v574[8]; // [rsp+1010h] [rbp+F10h] BYREF
  __int64 v575; // [rsp+1018h] [rbp+F18h] BYREF
  __int64 v576; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v577[8]; // [rsp+1028h] [rbp+F28h] BYREF
  _BYTE v578[8]; // [rsp+1030h] [rbp+F30h] BYREF
  _BYTE v579[8]; // [rsp+1038h] [rbp+F38h] BYREF
  _BYTE v580[8]; // [rsp+1040h] [rbp+F40h] BYREF
  _BYTE v581[8]; // [rsp+1048h] [rbp+F48h] BYREF
  _BYTE v582[8]; // [rsp+1050h] [rbp+F50h] BYREF
  __int64 v583; // [rsp+1058h] [rbp+F58h] BYREF
  __int64 v584; // [rsp+1060h] [rbp+F60h] BYREF
  _BYTE v585[8]; // [rsp+1068h] [rbp+F68h] BYREF
  _BYTE v586[8]; // [rsp+1070h] [rbp+F70h] BYREF
  _BYTE v587[8]; // [rsp+1078h] [rbp+F78h] BYREF
  _BYTE v588[8]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v589[8]; // [rsp+1088h] [rbp+F88h] BYREF
  _BYTE v590[8]; // [rsp+1090h] [rbp+F90h] BYREF
  __int64 v591; // [rsp+1098h] [rbp+F98h] BYREF
  __int64 v592; // [rsp+10A0h] [rbp+FA0h] BYREF
  _BYTE v593[8]; // [rsp+10A8h] [rbp+FA8h] BYREF
  _BYTE v594[8]; // [rsp+10B0h] [rbp+FB0h] BYREF
  _BYTE v595[8]; // [rsp+10B8h] [rbp+FB8h] BYREF
  _BYTE v596[8]; // [rsp+10C0h] [rbp+FC0h] BYREF
  _BYTE v597[8]; // [rsp+10C8h] [rbp+FC8h] BYREF
  _BYTE v598[8]; // [rsp+10D0h] [rbp+FD0h] BYREF
  __int64 v599; // [rsp+10D8h] [rbp+FD8h] BYREF
  __int64 v600; // [rsp+10E0h] [rbp+FE0h] BYREF
  _BYTE v601[8]; // [rsp+10E8h] [rbp+FE8h] BYREF
  _BYTE v602[8]; // [rsp+10F0h] [rbp+FF0h] BYREF
  _BYTE v603[8]; // [rsp+10F8h] [rbp+FF8h] BYREF
  _BYTE v604[8]; // [rsp+1100h] [rbp+1000h] BYREF
  _BYTE v605[8]; // [rsp+1108h] [rbp+1008h] BYREF
  _BYTE v606[8]; // [rsp+1110h] [rbp+1010h] BYREF
  __int64 v607; // [rsp+1118h] [rbp+1018h] BYREF
  __int64 v608; // [rsp+1120h] [rbp+1020h] BYREF
  _BYTE v609[8]; // [rsp+1128h] [rbp+1028h] BYREF
  _BYTE v610[8]; // [rsp+1130h] [rbp+1030h] BYREF
  _BYTE v611[8]; // [rsp+1138h] [rbp+1038h] BYREF
  _BYTE v612[8]; // [rsp+1140h] [rbp+1040h] BYREF
  _BYTE v613[8]; // [rsp+1148h] [rbp+1048h] BYREF
  _BYTE v614[8]; // [rsp+1150h] [rbp+1050h] BYREF
  __int64 v615; // [rsp+1158h] [rbp+1058h] BYREF
  __int64 v616; // [rsp+1160h] [rbp+1060h] BYREF
  _BYTE v617[8]; // [rsp+1168h] [rbp+1068h] BYREF
  _BYTE v618[8]; // [rsp+1170h] [rbp+1070h] BYREF
  _BYTE v619[8]; // [rsp+1178h] [rbp+1078h] BYREF
  _BYTE v620[8]; // [rsp+1180h] [rbp+1080h] BYREF
  _BYTE v621[8]; // [rsp+1188h] [rbp+1088h] BYREF
  _BYTE v622[8]; // [rsp+1190h] [rbp+1090h] BYREF
  __int64 v623; // [rsp+1198h] [rbp+1098h] BYREF
  __int64 v624; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v625[8]; // [rsp+11A8h] [rbp+10A8h] BYREF
  _BYTE v626[8]; // [rsp+11B0h] [rbp+10B0h] BYREF
  _BYTE v627[8]; // [rsp+11B8h] [rbp+10B8h] BYREF
  _BYTE v628[8]; // [rsp+11C0h] [rbp+10C0h] BYREF
  _BYTE v629[8]; // [rsp+11C8h] [rbp+10C8h] BYREF
  _BYTE v630[8]; // [rsp+11D0h] [rbp+10D0h] BYREF
  __int64 v631; // [rsp+11D8h] [rbp+10D8h] BYREF
  __int64 v632; // [rsp+11E0h] [rbp+10E0h] BYREF
  _BYTE v633[8]; // [rsp+11E8h] [rbp+10E8h] BYREF
  _BYTE v634[8]; // [rsp+11F0h] [rbp+10F0h] BYREF
  _BYTE v635[8]; // [rsp+11F8h] [rbp+10F8h] BYREF
  _BYTE v636[8]; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v637[8]; // [rsp+1208h] [rbp+1108h] BYREF
  _BYTE v638[8]; // [rsp+1210h] [rbp+1110h] BYREF
  __int64 v639; // [rsp+1218h] [rbp+1118h] BYREF
  __int64 v640; // [rsp+1220h] [rbp+1120h] BYREF
  _BYTE v641[8]; // [rsp+1228h] [rbp+1128h] BYREF
  _BYTE v642[8]; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v643[8]; // [rsp+1238h] [rbp+1138h] BYREF
  _BYTE v644[8]; // [rsp+1240h] [rbp+1140h] BYREF
  _BYTE v645[8]; // [rsp+1248h] [rbp+1148h] BYREF
  _BYTE v646[8]; // [rsp+1250h] [rbp+1150h] BYREF
  _BYTE v647[8]; // [rsp+1258h] [rbp+1158h] BYREF
  _BYTE v648[8]; // [rsp+1260h] [rbp+1160h] BYREF
  _BYTE v649[8]; // [rsp+1268h] [rbp+1168h] BYREF
  _BYTE v650[8]; // [rsp+1270h] [rbp+1170h] BYREF
  _BYTE v651[8]; // [rsp+1278h] [rbp+1178h] BYREF
  _BYTE v652[8]; // [rsp+1280h] [rbp+1180h] BYREF
  _BYTE v653[8]; // [rsp+1288h] [rbp+1188h] BYREF
  _BYTE v654[8]; // [rsp+1290h] [rbp+1190h] BYREF
  _BYTE v655[8]; // [rsp+1298h] [rbp+1198h] BYREF
  _BYTE v656[8]; // [rsp+12A0h] [rbp+11A0h] BYREF
  _BYTE v657[8]; // [rsp+12A8h] [rbp+11A8h] BYREF
  _BYTE v658[8]; // [rsp+12B0h] [rbp+11B0h] BYREF
  _BYTE v659[8]; // [rsp+12B8h] [rbp+11B8h] BYREF
  _BYTE v660[8]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v661[8]; // [rsp+12C8h] [rbp+11C8h] BYREF
  _BYTE v662[8]; // [rsp+12D0h] [rbp+11D0h] BYREF
  _BYTE v663[8]; // [rsp+12D8h] [rbp+11D8h] BYREF
  _BYTE v664[8]; // [rsp+12E0h] [rbp+11E0h] BYREF
  _BYTE v665[8]; // [rsp+12E8h] [rbp+11E8h] BYREF
  _BYTE v666[8]; // [rsp+12F0h] [rbp+11F0h] BYREF
  _BYTE v667[8]; // [rsp+12F8h] [rbp+11F8h] BYREF
  _BYTE v668[8]; // [rsp+1300h] [rbp+1200h] BYREF
  _BYTE v669[8]; // [rsp+1308h] [rbp+1208h] BYREF
  _BYTE v670[8]; // [rsp+1310h] [rbp+1210h] BYREF
  _BYTE v671[8]; // [rsp+1318h] [rbp+1218h] BYREF
  _BYTE v672[8]; // [rsp+1320h] [rbp+1220h] BYREF
  _BYTE v673[8]; // [rsp+1328h] [rbp+1228h] BYREF
  _BYTE v674[8]; // [rsp+1330h] [rbp+1230h] BYREF
  _BYTE v675[8]; // [rsp+1338h] [rbp+1238h] BYREF
  _BYTE v676[8]; // [rsp+1340h] [rbp+1240h] BYREF
  _BYTE v677[8]; // [rsp+1348h] [rbp+1248h] BYREF
  _BYTE v678[8]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v679[8]; // [rsp+1358h] [rbp+1258h] BYREF
  _BYTE v680[8]; // [rsp+1360h] [rbp+1260h] BYREF
  _BYTE v681[56]; // [rsp+1368h] [rbp+1268h] BYREF
  __int64 v682; // [rsp+13B0h] [rbp+12B0h] BYREF
  const char *v683; // [rsp+13B8h] [rbp+12B8h] BYREF
  __int64 v684; // [rsp+13C0h] [rbp+12C0h] BYREF
  __int64 v685; // [rsp+13C8h] [rbp+12C8h] BYREF

  v1 = a1;
  if ( *a1 )
  {
    ((void (*)(void))DbgTelemetryToolsImplicitRegisterProviderCheck)();
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v682 = *v1;
              v684 = 0x2000000;
              v683 = "ForwardCallCount";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D3730,
                0,
                0,
                (__int64)&v684,
                (__int64)&v683,
                (__int64)&v682);
            }
          }
        }
      }
    }
  }
  if ( v1[1] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v685 = v1[1];
              v73 = 0x2000000;
              v72 = "ForwardSingleStepCount";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D3778,
                0,
                0,
                (__int64)&v73,
                (__int64)&v72,
                (__int64)&v685);
            }
          }
        }
      }
    }
  }
  if ( v1[2] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v74 = v1[6];
              v75 = v1[5];
              v76 = v1[4];
              v77 = v1[3];
              v78 = v1[2];
              v79 = "ForwardTotalReplayTime";
              v80 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D35DA,
                0,
                0,
                (__int64)&v80,
                (__int64)&v79,
                (__int64)&v78,
                (__int64)&v77,
                (__int64)&v76,
                (__int64)&v75,
                (__int64)&v74);
            }
          }
        }
      }
    }
  }
  if ( v1[7] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v81 = v1[11];
              v82 = v1[10];
              v83 = v1[9];
              v84 = v1[8];
              v85 = v1[7];
              v86 = "ForwardFastReplayTime";
              v87 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D3568,
                0,
                0,
                (__int64)&v87,
                (__int64)&v86,
                (__int64)&v85,
                (__int64)&v84,
                (__int64)&v83,
                (__int64)&v82,
                (__int64)&v81);
            }
          }
        }
      }
    }
  }
  if ( v1[12] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v88 = v1[16];
              v89 = v1[15];
              v90 = v1[14];
              v91 = v1[13];
              v92 = v1[12];
              v93 = "ForwardFastReplayEventTimesMemoryWatchpoint";
              v94 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D36BE,
                0,
                0,
                (__int64)&v94,
                (__int64)&v93,
                (__int64)&v92,
                (__int64)&v91,
                (__int64)&v90,
                (__int64)&v89,
                (__int64)&v88);
            }
          }
        }
      }
    }
  }
  if ( v1[17] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v95 = v1[21];
              v96 = v1[20];
              v97 = v1[19];
              v98 = v1[18];
              v99 = v1[17];
              v100 = "ForwardFastReplayEventTimesPositionWatchpoint";
              v101 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D364C,
                0,
                0,
                (__int64)&v101,
                (__int64)&v100,
                (__int64)&v99,
                (__int64)&v98,
                (__int64)&v97,
                (__int64)&v96,
                (__int64)&v95);
            }
          }
        }
      }
    }
  }
  if ( v1[22] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v102 = v1[26];
              v103 = v1[25];
              v104 = v1[24];
              v105 = v1[23];
              v106 = v1[22];
              v107 = "ForwardFastReplayEventTimesException";
              v108 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D3412,
                0,
                0,
                (__int64)&v108,
                (__int64)&v107,
                (__int64)&v106,
                (__int64)&v105,
                (__int64)&v104,
                (__int64)&v103,
                (__int64)&v102);
            }
          }
        }
      }
    }
  }
  if ( v1[27] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v109 = v1[31];
              v110 = v1[30];
              v111 = v1[29];
              v112 = v1[28];
              v113 = v1[27];
              v114 = "ForwardFastReplayEventTimesGap";
              v115 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D33A0,
                0,
                0,
                (__int64)&v115,
                (__int64)&v114,
                (__int64)&v113,
                (__int64)&v112,
                (__int64)&v111,
                (__int64)&v110,
                (__int64)&v109);
            }
          }
        }
      }
    }
  }
  if ( v1[32] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v116 = v1[36];
              v117 = v1[35];
              v118 = v1[34];
              v119 = v1[33];
              v120 = v1[32];
              v121 = "ForwardFastReplayEventTimesThread";
              v122 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D34F6,
                0,
                0,
                (__int64)&v122,
                (__int64)&v121,
                (__int64)&v120,
                (__int64)&v119,
                (__int64)&v118,
                (__int64)&v117,
                (__int64)&v116);
            }
          }
        }
      }
    }
  }
  if ( v1[37] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v123 = v1[41];
              v124 = v1[40];
              v125 = v1[39];
              v126 = v1[38];
              v127 = v1[37];
              v128 = "ForwardFastReplayEventTimesStepCount";
              v129 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D3484,
                0,
                0,
                (__int64)&v129,
                (__int64)&v128,
                (__int64)&v127,
                (__int64)&v126,
                (__int64)&v125,
                (__int64)&v124,
                (__int64)&v123);
            }
          }
        }
      }
    }
  }
  if ( v1[42] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v130 = v1[46];
              v131 = v1[45];
              v132 = v1[44];
              v133 = v1[43];
              v134 = v1[42];
              v135 = "ForwardFastReplayEventTimesPosition";
              v136 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D324A,
                0,
                0,
                (__int64)&v136,
                (__int64)&v135,
                (__int64)&v134,
                (__int64)&v133,
                (__int64)&v132,
                (__int64)&v131,
                (__int64)&v130);
            }
          }
        }
      }
    }
  }
  if ( v1[47] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v137 = v1[51];
              v138 = v1[50];
              v139 = v1[49];
              v140 = v1[48];
              v141 = v1[47];
              v142 = "ForwardFastReplayEventTimesProcess";
              v143 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D31D8,
                0,
                0,
                (__int64)&v143,
                (__int64)&v142,
                (__int64)&v141,
                (__int64)&v140,
                (__int64)&v139,
                (__int64)&v138,
                (__int64)&v137);
            }
          }
        }
      }
    }
  }
  if ( v1[52] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v144 = v1[56];
              v145 = v1[55];
              v146 = v1[54];
              v147 = v1[53];
              v148 = v1[52];
              v149 = "ForwardFastReplayEventTimesInterrupted";
              v150 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D332E,
                0,
                0,
                (__int64)&v150,
                (__int64)&v149,
                (__int64)&v148,
                (__int64)&v147,
                (__int64)&v146,
                (__int64)&v145,
                (__int64)&v144);
            }
          }
        }
      }
    }
  }
  if ( v1[57] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v151 = v1[61];
              v152 = v1[60];
              v153 = v1[59];
              v154 = v1[58];
              v155 = v1[57];
              v156 = "ForwardFastReplayEventTimesError";
              v157 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D32BC,
                0,
                0,
                (__int64)&v157,
                (__int64)&v156,
                (__int64)&v155,
                (__int64)&v154,
                (__int64)&v153,
                (__int64)&v152,
                (__int64)&v151);
            }
          }
        }
      }
    }
  }
  if ( v1[62] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v158 = v1[66];
              v159 = v1[65];
              v160 = v1[64];
              v161 = v1[63];
              v162 = v1[62];
              v163 = "ForwardScheduledReplayTime";
              v164 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D3082,
                0,
                0,
                (__int64)&v164,
                (__int64)&v163,
                (__int64)&v162,
                (__int64)&v161,
                (__int64)&v160,
                (__int64)&v159,
                (__int64)&v158);
            }
          }
        }
      }
    }
  }
  if ( v1[67] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v165 = v1[71];
              v166 = v1[70];
              v167 = v1[69];
              v168 = v1[68];
              v169 = v1[67];
              v170 = "ForwardScheduledReplaySegmentsExecuted";
              v171 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D3010,
                0,
                0,
                (__int64)&v171,
                (__int64)&v170,
                (__int64)&v169,
                (__int64)&v168,
                (__int64)&v167,
                (__int64)&v166,
                (__int64)&v165);
            }
          }
        }
      }
    }
  }
  if ( v1[72] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v172 = v1[76];
              v173 = v1[75];
              v174 = v1[74];
              v175 = v1[73];
              v176 = v1[72];
              v177 = "ForwardScheduledReplayStepsExecuted";
              v178 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D3166,
                0,
                0,
                (__int64)&v178,
                (__int64)&v177,
                (__int64)&v176,
                (__int64)&v175,
                (__int64)&v174,
                (__int64)&v173,
                (__int64)&v172);
            }
          }
        }
      }
    }
  }
  if ( v1[77] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v179 = v1[81];
              v180 = v1[80];
              v181 = v1[79];
              v182 = v1[78];
              v183 = v1[77];
              v184 = "ForwardScheduledReplayEventTimesMemoryWatchpoint";
              v185 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D30F4,
                0,
                0,
                (__int64)&v185,
                (__int64)&v184,
                (__int64)&v183,
                (__int64)&v182,
                (__int64)&v181,
                (__int64)&v180,
                (__int64)&v179);
            }
          }
        }
      }
    }
  }
  if ( v1[82] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v186 = v1[86];
              v187 = v1[85];
              v188 = v1[84];
              v189 = v1[83];
              v190 = v1[82];
              v191 = "ForwardScheduledReplayEventTimesPositionWatchpoint";
              v192 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D2EBA,
                0,
                0,
                (__int64)&v192,
                (__int64)&v191,
                (__int64)&v190,
                (__int64)&v189,
                (__int64)&v188,
                (__int64)&v187,
                (__int64)&v186);
            }
          }
        }
      }
    }
  }
  if ( v1[87] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v193 = v1[91];
              v194 = v1[90];
              v195 = v1[89];
              v196 = v1[88];
              v197 = v1[87];
              v198 = "ForwardScheduledReplayEventTimesException";
              v199 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D2E48,
                0,
                0,
                (__int64)&v199,
                (__int64)&v198,
                (__int64)&v197,
                (__int64)&v196,
                (__int64)&v195,
                (__int64)&v194,
                (__int64)&v193);
            }
          }
        }
      }
    }
  }
  if ( v1[92] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v200 = v1[96];
              v201 = v1[95];
              v202 = v1[94];
              v203 = v1[93];
              v204 = v1[92];
              v205 = "ForwardScheduledReplayEventTimesGap";
              v206 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D2F9E,
                0,
                0,
                (__int64)&v206,
                (__int64)&v205,
                (__int64)&v204,
                (__int64)&v203,
                (__int64)&v202,
                (__int64)&v201,
                (__int64)&v200);
            }
          }
        }
      }
    }
  }
  if ( v1[97] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v207 = v1[101];
              v208 = v1[100];
              v209 = v1[99];
              v210 = v1[98];
              v211 = v1[97];
              v212 = "ForwardScheduledReplayEventTimesThread";
              v213 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D2F2C,
                0,
                0,
                (__int64)&v213,
                (__int64)&v212,
                (__int64)&v211,
                (__int64)&v210,
                (__int64)&v209,
                (__int64)&v208,
                (__int64)&v207);
            }
          }
        }
      }
    }
  }
  if ( v1[102] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v214 = v1[106];
              v215 = v1[105];
              v216 = v1[104];
              v217 = v1[103];
              v218 = v1[102];
              v219 = "ForwardScheduledReplayEventTimesStepCount";
              v220 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D2CF2,
                0,
                0,
                (__int64)&v220,
                (__int64)&v219,
                (__int64)&v218,
                (__int64)&v217,
                (__int64)&v216,
                (__int64)&v215,
                (__int64)&v214);
            }
          }
        }
      }
    }
  }
  if ( v1[107] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v221 = v1[111];
              v222 = v1[110];
              v223 = v1[109];
              v224 = v1[108];
              v225 = v1[107];
              v226 = "ForwardScheduledReplayEventTimesPosition";
              v227 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D2C80,
                0,
                0,
                (__int64)&v227,
                (__int64)&v226,
                (__int64)&v225,
                (__int64)&v224,
                (__int64)&v223,
                (__int64)&v222,
                (__int64)&v221);
            }
          }
        }
      }
    }
  }
  if ( v1[112] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v228 = v1[116];
              v229 = v1[115];
              v230 = v1[114];
              v231 = v1[113];
              v232 = v1[112];
              v233 = "ForwardScheduledReplayEventTimesProcess";
              v234 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D2DD6,
                0,
                0,
                (__int64)&v234,
                (__int64)&v233,
                (__int64)&v232,
                (__int64)&v231,
                (__int64)&v230,
                (__int64)&v229,
                (__int64)&v228);
            }
          }
        }
      }
    }
  }
  if ( v1[117] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v235 = v1[121];
              v236 = v1[120];
              v237 = v1[119];
              v238 = v1[118];
              v239 = v1[117];
              v240 = "ForwardScheduledReplayEventTimesInterrupted";
              v241 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&dword_1806D2D64,
                0,
                0,
                (__int64)&v241,
                (__int64)&v240,
                (__int64)&v239,
                (__int64)&v238,
                (__int64)&v237,
                (__int64)&v236,
                (__int64)&v235);
            }
          }
        }
      }
    }
  }
  if ( v1[122] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v242 = v1[126];
              v243 = v1[125];
              v244 = v1[124];
              v245 = v1[123];
              v246 = v1[122];
              v247 = "ForwardScheduledReplayEventTimesError";
              v248 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)word_1806D2B2A,
                0,
                0,
                (__int64)&v248,
                (__int64)&v247,
                (__int64)&v246,
                (__int64)&v245,
                (__int64)&v244,
                (__int64)&v243,
                (__int64)&v242);
            }
          }
        }
      }
    }
  }
  if ( v1[127] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v249 = v1[131];
              v250 = v1[130];
              v251 = v1[129];
              v252 = v1[128];
              v253 = v1[127];
              v254 = "ForwardSegmentExecutionTime";
              v255 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&unk_1806D2AB8,
                0,
                0,
                (__int64)&v255,
                (__int64)&v254,
                (__int64)&v253,
                (__int64)&v252,
                (__int64)&v251,
                (__int64)&v250,
                (__int64)&v249);
            }
          }
        }
      }
    }
  }
  if ( v1[132] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( dword_18079C700 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) )
        {
          if ( (unsigned int)dword_18079C700 > 5 )
          {
            a1 = (__int64 *)qword_18079C718;
            if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
            {
              v256 = v1[136];
              v257 = v1[135];
              v258 = v1[134];
              v259 = v1[133];
              v260 = v1[132];
              v261 = "ForwardSegmentExecutionStepsExecuted";
              v262 = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_18079C700,
                (unsigned int)&word_1806D2C0E,
                0,
                0,
                (__int64)&v262,
                (__int64)&v261,
                (__int64)&v260,
                (__int64)&v259,
                (__int64)&v258,
                (__int64)&v257,
                (__int64)&v256);
            }
          }
        }
      }
    }
  }
  if ( v1[137] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v263 = v1[141];
          v264 = v1[140];
          v265 = v1[139];
          v266 = v1[138];
          v267 = v1[137];
          v268 = "ForwardSegmentExecutionEventTimesMemoryWatchpoint";
          v269 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&dword_1806D2B9C,
            0,
            0,
            (__int64)&v269,
            (__int64)&v268,
            (__int64)&v267,
            (__int64)&v266,
            (__int64)&v265,
            (__int64)&v264,
            (__int64)&v263);
        }
      }
    }
  }
  if ( v1[142] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v270 = v1[146];
          v271 = v1[145];
          v272 = v1[144];
          v273 = v1[143];
          v274 = v1[142];
          v275 = "ForwardSegmentExecutionEventTimesPositionWatchpoint";
          v276 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)word_1806D2962,
            0,
            0,
            (__int64)&v276,
            (__int64)&v275,
            (__int64)&v274,
            (__int64)&v273,
            (__int64)&v272,
            (__int64)&v271,
            (__int64)&v270);
        }
      }
    }
  }
  if ( v1[147] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v277 = v1[151];
          v278 = v1[150];
          v279 = v1[149];
          v280 = v1[148];
          v281 = v1[147];
          v282 = "ForwardSegmentExecutionEventTimesException";
          v283 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&unk_1806D28F0,
            0,
            0,
            (__int64)&v283,
            (__int64)&v282,
            (__int64)&v281,
            (__int64)&v280,
            (__int64)&v279,
            (__int64)&v278,
            (__int64)&v277);
        }
      }
    }
  }
  if ( v1[152] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v284 = v1[156];
          v285 = v1[155];
          v286 = v1[154];
          v287 = v1[153];
          v288 = v1[152];
          v289 = "ForwardSegmentExecutionEventTimesGap";
          v290 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&word_1806D2A46,
            0,
            0,
            (__int64)&v290,
            (__int64)&v289,
            (__int64)&v288,
            (__int64)&v287,
            (__int64)&v286,
            (__int64)&v285,
            (__int64)&v284);
        }
      }
    }
  }
  if ( v1[157] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v291 = v1[161];
          v292 = v1[160];
          v293 = v1[159];
          v294 = v1[158];
          v295 = v1[157];
          v296 = "ForwardSegmentExecutionEventTimesThread";
          v297 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&dword_1806D29D4,
            0,
            0,
            (__int64)&v297,
            (__int64)&v296,
            (__int64)&v295,
            (__int64)&v294,
            (__int64)&v293,
            (__int64)&v292,
            (__int64)&v291);
        }
      }
    }
  }
  if ( v1[162] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v298 = v1[166];
          v299 = v1[165];
          v300 = v1[164];
          v301 = v1[163];
          v302 = v1[162];
          v303 = "ForwardSegmentExecutionEventTimesStepCount";
          v304 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)word_1806D279A,
            0,
            0,
            (__int64)&v304,
            (__int64)&v303,
            (__int64)&v302,
            (__int64)&v301,
            (__int64)&v300,
            (__int64)&v299,
            (__int64)&v298);
        }
      }
    }
  }
  if ( v1[167] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v305 = v1[171];
          v306 = v1[170];
          v307 = v1[169];
          v308 = v1[168];
          v309 = v1[167];
          v310 = "ForwardSegmentExecutionEventTimesPosition";
          v311 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&unk_1806D2728,
            0,
            0,
            (__int64)&v311,
            (__int64)&v310,
            (__int64)&v309,
            (__int64)&v308,
            (__int64)&v307,
            (__int64)&v306,
            (__int64)&v305);
        }
      }
    }
  }
  if ( v1[172] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v312 = v1[176];
          v313 = v1[175];
          v314 = v1[174];
          v315 = v1[173];
          v316 = v1[172];
          v317 = "ForwardSegmentExecutionEventTimesProcess";
          v318 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&word_1806D287E,
            0,
            0,
            (__int64)&v318,
            (__int64)&v317,
            (__int64)&v316,
            (__int64)&v315,
            (__int64)&v314,
            (__int64)&v313,
            (__int64)&v312);
        }
      }
    }
  }
  if ( v1[177] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v319 = v1[181];
          v320 = v1[180];
          v321 = v1[179];
          v322 = v1[178];
          v323 = v1[177];
          v324 = "ForwardSegmentExecutionEventTimesInterrupted";
          v325 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&dword_1806D280C,
            0,
            0,
            (__int64)&v325,
            (__int64)&v324,
            (__int64)&v323,
            (__int64)&v322,
            (__int64)&v321,
            (__int64)&v320,
            (__int64)&v319);
        }
      }
    }
  }
  if ( v1[182] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v326 = v1[186];
          v327 = v1[185];
          v328 = v1[184];
          v329 = v1[183];
          v330 = v1[182];
          v331 = "ForwardSegmentExecutionEventTimesError";
          v332 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&word_1806D2626,
            0,
            0,
            (__int64)&v332,
            (__int64)&v331,
            (__int64)&v330,
            (__int64)&v329,
            (__int64)&v328,
            (__int64)&v327,
            (__int64)&v326);
        }
      }
    }
  }
  if ( v1[187] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v333 = v1[191];
          v334 = v1[190];
          v335 = v1[189];
          v336 = v1[188];
          v337 = v1[187];
          v338 = "ForwardRepositionTime";
          v339 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&dword_1806D25B4,
            0,
            0,
            (__int64)&v339,
            (__int64)&v338,
            (__int64)&v337,
            (__int64)&v336,
            (__int64)&v335,
            (__int64)&v334,
            (__int64)&v333);
        }
      }
    }
  }
  if ( v1[192] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v340 = v1[192];
          v342 = 0x2000000;
          v341 = "BackwardCallCount";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&unk_1806D26E0,
            0,
            0,
            (__int64)&v342,
            (__int64)&v341,
            (__int64)&v340);
        }
      }
    }
  }
  if ( v1[193] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v343 = v1[193];
          v345 = 0x2000000;
          v344 = "BackwardSingleStepCount";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&unk_1806D2698,
            0,
            0,
            (__int64)&v345,
            (__int64)&v344,
            (__int64)&v343);
        }
      }
    }
  }
  if ( v1[194] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v346 = v1[198];
          v347 = v1[197];
          v348 = v1[196];
          v349 = v1[195];
          v350 = v1[194];
          v351 = "BackwardTotalReplayTime";
          v352 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&word_1806D245E,
            0,
            0,
            (__int64)&v352,
            (__int64)&v351,
            (__int64)&v350,
            (__int64)&v349,
            (__int64)&v348,
            (__int64)&v347,
            (__int64)&v346);
        }
      }
    }
  }
  if ( v1[199] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v353 = v1[203];
          v354 = v1[202];
          v355 = v1[201];
          v356 = v1[200];
          v357 = v1[199];
          v358 = "BackwardFastReplayTime";
          v359 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&dword_1806D23EC,
            0,
            0,
            (__int64)&v359,
            (__int64)&v358,
            (__int64)&v357,
            (__int64)&v356,
            (__int64)&v355,
            (__int64)&v354,
            (__int64)&v353);
        }
      }
    }
  }
  if ( v1[204] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( `GlobalTelemetryState'::`2'::s_isTelemetryEnabled )
    {
      if ( (unsigned int)dword_18079C700 >= 6 )
      {
        a1 = (__int64 *)qword_18079C718;
        if ( (qword_18079C710 & 0x400000000000LL) != 0 && (qword_18079C718 & 0x400000000000LL) == qword_18079C718 )
        {
          v360 = v1[208];
          v361 = v1[207];
          v362 = v1[206];
          v363 = v1[205];
          v364 = v1[204];
          v365 = "BackwardFastReplayEventTimesMemoryWatchpoint";
          v366 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)word_1806D2542,
            0,
            0,
            (__int64)&v366,
            (__int64)&v365,
            (__int64)&v364,
            (__int64)&v363,
            (__int64)&v362,
            (__int64)&v361,
            (__int64)&v360);
        }
      }
    }
  }
  if ( v1[209] )
  {
    DbgTelemetryToolsImplicitRegisterProviderCheck(a1);
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v369,
          v1 + 213);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v370,
          v1 + 212);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v371,
          v1 + 211);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v372,
          v1 + 210);
        v367 = v1[209];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v373,
          &v367);
        v2 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
               v647,
               "BackwardFastReplayEventTimesPositionWatchpoint");
        v368 = 0x2000000;
        v3 = v2;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v374,
          &v368);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D24D0,
          0,
          0,
          (__int64)v374,
          v3,
          (__int64)v373,
          (__int64)v372,
          (__int64)v371,
          (__int64)v370,
          (__int64)v369);
      }
    }
  }
  if ( v1[214] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v377,
          v1 + 218);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v378,
          v1 + 217);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v379,
          v1 + 216);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v380,
          v1 + 215);
        v375 = v1[214];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v381,
          &v375);
        v4 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
               v648,
               "BackwardFastReplayEventTimesException");
        v376 = 0x2000000;
        v5 = v4;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v382,
          &v376);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D2296,
          0,
          0,
          (__int64)v382,
          v5,
          (__int64)v381,
          (__int64)v380,
          (__int64)v379,
          (__int64)v378,
          (__int64)v377);
      }
    }
  }
  if ( v1[219] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v385,
          v1 + 223);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v386,
          v1 + 222);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v387,
          v1 + 221);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v388,
          v1 + 220);
        v383 = v1[219];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v389,
          &v383);
        v6 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
               v649,
               "BackwardFastReplayEventTimesGap");
        v384 = 0x2000000;
        v7 = v6;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v390,
          &v384);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D2224,
          0,
          0,
          (__int64)v390,
          v7,
          (__int64)v389,
          (__int64)v388,
          (__int64)v387,
          (__int64)v386,
          (__int64)v385);
      }
    }
  }
  if ( v1[224] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v393,
          v1 + 228);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v394,
          v1 + 227);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v395,
          v1 + 226);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v396,
          v1 + 225);
        v391 = v1[224];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v397,
          &v391);
        v8 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
               v650,
               "BackwardFastReplayEventTimesThread");
        v392 = 0x2000000;
        v9 = v8;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v398,
          &v392);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D237A,
          0,
          0,
          (__int64)v398,
          v9,
          (__int64)v397,
          (__int64)v396,
          (__int64)v395,
          (__int64)v394,
          (__int64)v393);
      }
    }
  }
  if ( v1[229] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v401,
          v1 + 233);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v402,
          v1 + 232);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v403,
          v1 + 231);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v404,
          v1 + 230);
        v399 = v1[229];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v405,
          &v399);
        v10 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v651,
                "BackwardFastReplayEventTimesStepCount");
        v400 = 0x2000000;
        v11 = v10;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v406,
          &v400);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D2308,
          0,
          0,
          (__int64)v406,
          v11,
          (__int64)v405,
          (__int64)v404,
          (__int64)v403,
          (__int64)v402,
          (__int64)v401);
      }
    }
  }
  if ( v1[234] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v409,
          v1 + 238);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v410,
          v1 + 237);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v411,
          v1 + 236);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v412,
          v1 + 235);
        v407 = v1[234];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v413,
          &v407);
        v12 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v652,
                "BackwardFastReplayEventTimesPosition");
        v408 = 0x2000000;
        v13 = v12;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v414,
          &v408);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D20CE,
          0,
          0,
          (__int64)v414,
          v13,
          (__int64)v413,
          (__int64)v412,
          (__int64)v411,
          (__int64)v410,
          (__int64)v409);
      }
    }
  }
  if ( v1[239] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v417,
          v1 + 243);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v418,
          v1 + 242);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v419,
          v1 + 241);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v420,
          v1 + 240);
        v415 = v1[239];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v421,
          &v415);
        v14 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v653,
                "BackwardFastReplayEventTimesProcess");
        v416 = 0x2000000;
        v15 = v14;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v422,
          &v416);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D205C,
          0,
          0,
          (__int64)v422,
          v15,
          (__int64)v421,
          (__int64)v420,
          (__int64)v419,
          (__int64)v418,
          (__int64)v417);
      }
    }
  }
  if ( v1[244] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v425,
          v1 + 248);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v426,
          v1 + 247);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v427,
          v1 + 246);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v428,
          v1 + 245);
        v423 = v1[244];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v429,
          &v423);
        v16 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v654,
                "BackwardFastReplayEventTimesInterrupted");
        v424 = 0x2000000;
        v17 = v16;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v430,
          &v424);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D21B2,
          0,
          0,
          (__int64)v430,
          v17,
          (__int64)v429,
          (__int64)v428,
          (__int64)v427,
          (__int64)v426,
          (__int64)v425);
      }
    }
  }
  if ( v1[249] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v433,
          v1 + 253);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v434,
          v1 + 252);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v435,
          v1 + 251);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v436,
          v1 + 250);
        v431 = v1[249];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v437,
          &v431);
        v18 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v655,
                "BackwardFastReplayEventTimesError");
        v432 = 0x2000000;
        v19 = v18;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v438,
          &v432);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D2140,
          0,
          0,
          (__int64)v438,
          v19,
          (__int64)v437,
          (__int64)v436,
          (__int64)v435,
          (__int64)v434,
          (__int64)v433);
      }
    }
  }
  if ( v1[254] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v441,
          v1 + 258);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v442,
          v1 + 257);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v443,
          v1 + 256);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v444,
          v1 + 255);
        v439 = v1[254];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v445,
          &v439);
        v20 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v656,
                "BackwardScheduledReplayTime");
        v440 = 0x2000000;
        v21 = v20;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v446,
          &v440);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D1F06,
          0,
          0,
          (__int64)v446,
          v21,
          (__int64)v445,
          (__int64)v444,
          (__int64)v443,
          (__int64)v442,
          (__int64)v441);
      }
    }
  }
  if ( v1[259] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v449,
          v1 + 263);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v450,
          v1 + 262);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v451,
          v1 + 261);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v452,
          v1 + 260);
        v447 = v1[259];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v453,
          &v447);
        v22 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v657,
                "BackwardScheduledReplaySegmentsExecuted");
        v448 = 0x2000000;
        v23 = v22;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v454,
          &v448);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D1E94,
          0,
          0,
          (__int64)v454,
          v23,
          (__int64)v453,
          (__int64)v452,
          (__int64)v451,
          (__int64)v450,
          (__int64)v449);
      }
    }
  }
  if ( v1[264] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v457,
          v1 + 268);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v458,
          v1 + 267);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v459,
          v1 + 266);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v460,
          v1 + 265);
        v455 = v1[264];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v461,
          &v455);
        v24 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v658,
                "BackwardScheduledReplayStepsExecuted");
        v456 = 0x2000000;
        v25 = v24;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v462,
          &v456);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D1FEA,
          0,
          0,
          (__int64)v462,
          v25,
          (__int64)v461,
          (__int64)v460,
          (__int64)v459,
          (__int64)v458,
          (__int64)v457);
      }
    }
  }
  if ( v1[269] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v465,
          v1 + 273);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v466,
          v1 + 272);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v467,
          v1 + 271);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v468,
          v1 + 270);
        v463 = v1[269];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v469,
          &v463);
        v26 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v659,
                "BackwardScheduledReplayEventTimesMemoryWatchpoint");
        v464 = 0x2000000;
        v27 = v26;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v470,
          &v464);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1F78,
          0,
          0,
          (__int64)v470,
          v27,
          (__int64)v469,
          (__int64)v468,
          (__int64)v467,
          (__int64)v466,
          (__int64)v465);
      }
    }
  }
  if ( v1[274] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v473,
          v1 + 278);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v474,
          v1 + 277);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v475,
          v1 + 276);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v476,
          v1 + 275);
        v471 = v1[274];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v477,
          &v471);
        v28 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v660,
                "BackwardScheduledReplayEventTimesPositionWatchpoint");
        v472 = 0x2000000;
        v29 = v28;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v478,
          &v472);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D1D3E,
          0,
          0,
          (__int64)v478,
          v29,
          (__int64)v477,
          (__int64)v476,
          (__int64)v475,
          (__int64)v474,
          (__int64)v473);
      }
    }
  }
  if ( v1[279] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v481,
          v1 + 283);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v482,
          v1 + 282);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v483,
          v1 + 281);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v484,
          v1 + 280);
        v479 = v1[279];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v485,
          &v479);
        v30 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v661,
                "BackwardScheduledReplayEventTimesException");
        v480 = 0x2000000;
        v31 = v30;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v486,
          &v480);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D1CCC,
          0,
          0,
          (__int64)v486,
          v31,
          (__int64)v485,
          (__int64)v484,
          (__int64)v483,
          (__int64)v482,
          (__int64)v481);
      }
    }
  }
  if ( v1[284] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v489,
          v1 + 288);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v490,
          v1 + 287);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v491,
          v1 + 286);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v492,
          v1 + 285);
        v487 = v1[284];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v493,
          &v487);
        v32 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v662,
                "BackwardScheduledReplayEventTimesGap");
        v488 = 0x2000000;
        v33 = v32;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v494,
          &v488);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D1E22,
          0,
          0,
          (__int64)v494,
          v33,
          (__int64)v493,
          (__int64)v492,
          (__int64)v491,
          (__int64)v490,
          (__int64)v489);
      }
    }
  }
  if ( v1[289] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v497,
          v1 + 293);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v498,
          v1 + 292);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v499,
          v1 + 291);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v500,
          v1 + 290);
        v495 = v1[289];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v501,
          &v495);
        v34 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v663,
                "BackwardScheduledReplayEventTimesThread");
        v496 = 0x2000000;
        v35 = v34;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v502,
          &v496);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1DB0,
          0,
          0,
          (__int64)v502,
          v35,
          (__int64)v501,
          (__int64)v500,
          (__int64)v499,
          (__int64)v498,
          (__int64)v497);
      }
    }
  }
  if ( v1[294] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v505,
          v1 + 298);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v506,
          v1 + 297);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v507,
          v1 + 296);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v508,
          v1 + 295);
        v503 = v1[294];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v509,
          &v503);
        v36 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v664,
                "BackwardScheduledReplayEventTimesStepCount");
        v504 = 0x2000000;
        v37 = v36;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v510,
          &v504);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D1B76,
          0,
          0,
          (__int64)v510,
          v37,
          (__int64)v509,
          (__int64)v508,
          (__int64)v507,
          (__int64)v506,
          (__int64)v505);
      }
    }
  }
  if ( v1[299] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v513,
          v1 + 303);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v514,
          v1 + 302);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v515,
          v1 + 301);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v516,
          v1 + 300);
        v511 = v1[299];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v517,
          &v511);
        v38 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v665,
                "BackwardScheduledReplayEventTimesPosition");
        v512 = 0x2000000;
        v39 = v38;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v518,
          &v512);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D1B04,
          0,
          0,
          (__int64)v518,
          v39,
          (__int64)v517,
          (__int64)v516,
          (__int64)v515,
          (__int64)v514,
          (__int64)v513);
      }
    }
  }
  if ( v1[304] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v521,
          v1 + 308);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v522,
          v1 + 307);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v523,
          v1 + 306);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v524,
          v1 + 305);
        v519 = v1[304];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v525,
          &v519);
        v40 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v666,
                "BackwardScheduledReplayEventTimesProcess");
        v520 = 0x2000000;
        v41 = v40;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v526,
          &v520);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D1C5A,
          0,
          0,
          (__int64)v526,
          v41,
          (__int64)v525,
          (__int64)v524,
          (__int64)v523,
          (__int64)v522,
          (__int64)v521);
      }
    }
  }
  if ( v1[309] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v529,
          v1 + 313);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v530,
          v1 + 312);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v531,
          v1 + 311);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v532,
          v1 + 310);
        v527 = v1[309];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v533,
          &v527);
        v42 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v667,
                "BackwardScheduledReplayEventTimesInterrupted");
        v528 = 0x2000000;
        v43 = v42;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v534,
          &v528);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1BE8,
          0,
          0,
          (__int64)v534,
          v43,
          (__int64)v533,
          (__int64)v532,
          (__int64)v531,
          (__int64)v530,
          (__int64)v529);
      }
    }
  }
  if ( v1[314] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v537,
          v1 + 318);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v538,
          v1 + 317);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v539,
          v1 + 316);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v540,
          v1 + 315);
        v535 = v1[314];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v541,
          &v535);
        v44 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v668,
                "BackwardScheduledReplayEventTimesError");
        v536 = 0x2000000;
        v45 = v44;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v542,
          &v536);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D19AE,
          0,
          0,
          (__int64)v542,
          v45,
          (__int64)v541,
          (__int64)v540,
          (__int64)v539,
          (__int64)v538,
          (__int64)v537);
      }
    }
  }
  if ( v1[319] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v545,
          v1 + 323);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v546,
          v1 + 322);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v547,
          v1 + 321);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v548,
          v1 + 320);
        v543 = v1[319];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v549,
          &v543);
        v46 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v669,
                "BackwardSegmentExecutionTime");
        v544 = 0x2000000;
        v47 = v46;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v550,
          &v544);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D193C,
          0,
          0,
          (__int64)v550,
          v47,
          (__int64)v549,
          (__int64)v548,
          (__int64)v547,
          (__int64)v546,
          (__int64)v545);
      }
    }
  }
  if ( v1[324] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v553,
          v1 + 328);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v554,
          v1 + 327);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v555,
          v1 + 326);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v556,
          v1 + 325);
        v551 = v1[324];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v557,
          &v551);
        v48 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v670,
                "BackwardSegmentExecutionStepsExecuted");
        v552 = 0x2000000;
        v49 = v48;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v558,
          &v552);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D1A92,
          0,
          0,
          (__int64)v558,
          v49,
          (__int64)v557,
          (__int64)v556,
          (__int64)v555,
          (__int64)v554,
          (__int64)v553);
      }
    }
  }
  if ( v1[329] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v561,
          v1 + 333);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v562,
          v1 + 332);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v563,
          v1 + 331);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v564,
          v1 + 330);
        v559 = v1[329];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v565,
          &v559);
        v50 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v671,
                "BackwardSegmentExecutionEventTimesMemoryWatchpoint");
        v560 = 0x2000000;
        v51 = v50;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v566,
          &v560);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1A20,
          0,
          0,
          (__int64)v566,
          v51,
          (__int64)v565,
          (__int64)v564,
          (__int64)v563,
          (__int64)v562,
          (__int64)v561);
      }
    }
  }
  if ( v1[334] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v569,
          v1 + 338);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v570,
          v1 + 337);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v571,
          v1 + 336);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v572,
          v1 + 335);
        v567 = v1[334];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v573,
          &v567);
        v52 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v672,
                "BackwardSegmentExecutionEventTimesPositionWatchpoint");
        v568 = 0x2000000;
        v53 = v52;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v574,
          &v568);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D17E6,
          0,
          0,
          (__int64)v574,
          v53,
          (__int64)v573,
          (__int64)v572,
          (__int64)v571,
          (__int64)v570,
          (__int64)v569);
      }
    }
  }
  if ( v1[339] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v577,
          v1 + 343);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v578,
          v1 + 342);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v579,
          v1 + 341);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v580,
          v1 + 340);
        v575 = v1[339];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v581,
          &v575);
        v54 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v673,
                "BackwardSegmentExecutionEventTimesException");
        v576 = 0x2000000;
        v55 = v54;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v582,
          &v576);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D1774,
          0,
          0,
          (__int64)v582,
          v55,
          (__int64)v581,
          (__int64)v580,
          (__int64)v579,
          (__int64)v578,
          (__int64)v577);
      }
    }
  }
  if ( v1[344] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v585,
          v1 + 348);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v586,
          v1 + 347);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v587,
          v1 + 346);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v588,
          v1 + 345);
        v583 = v1[344];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v589,
          &v583);
        v56 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v674,
                "BackwardSegmentExecutionEventTimesGap");
        v584 = 0x2000000;
        v57 = v56;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v590,
          &v584);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D18CA,
          0,
          0,
          (__int64)v590,
          v57,
          (__int64)v589,
          (__int64)v588,
          (__int64)v587,
          (__int64)v586,
          (__int64)v585);
      }
    }
  }
  if ( v1[349] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v593,
          v1 + 353);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v594,
          v1 + 352);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v595,
          v1 + 351);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v596,
          v1 + 350);
        v591 = v1[349];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v597,
          &v591);
        v58 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v675,
                "BackwardSegmentExecutionEventTimesThread");
        v592 = 0x2000000;
        v59 = v58;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v598,
          &v592);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1858,
          0,
          0,
          (__int64)v598,
          v59,
          (__int64)v597,
          (__int64)v596,
          (__int64)v595,
          (__int64)v594,
          (__int64)v593);
      }
    }
  }
  if ( v1[354] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v601,
          v1 + 358);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v602,
          v1 + 357);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v603,
          v1 + 356);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v604,
          v1 + 355);
        v599 = v1[354];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v605,
          &v599);
        v60 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v676,
                "BackwardSegmentExecutionEventTimesStepCount");
        v600 = 0x2000000;
        v61 = v60;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v606,
          &v600);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&word_1806D161E,
          0,
          0,
          (__int64)v606,
          v61,
          (__int64)v605,
          (__int64)v604,
          (__int64)v603,
          (__int64)v602,
          (__int64)v601);
      }
    }
  }
  if ( v1[359] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v609,
          v1 + 363);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v610,
          v1 + 362);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v611,
          v1 + 361);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v612,
          v1 + 360);
        v607 = v1[359];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v613,
          &v607);
        v62 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v677,
                "BackwardSegmentExecutionEventTimesPosition");
        v608 = 0x2000000;
        v63 = v62;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v614,
          &v608);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&dword_1806D15AC,
          0,
          0,
          (__int64)v614,
          v63,
          (__int64)v613,
          (__int64)v612,
          (__int64)v611,
          (__int64)v610,
          (__int64)v609);
      }
    }
  }
  if ( v1[364] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v617,
          v1 + 368);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v618,
          v1 + 367);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v619,
          v1 + 366);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v620,
          v1 + 365);
        v615 = v1[364];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v621,
          &v615);
        v64 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v678,
                "BackwardSegmentExecutionEventTimesProcess");
        v616 = 0x2000000;
        v65 = v64;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v622,
          &v616);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D1702,
          0,
          0,
          (__int64)v622,
          v65,
          (__int64)v621,
          (__int64)v620,
          (__int64)v619,
          (__int64)v618,
          (__int64)v617);
      }
    }
  }
  if ( v1[369] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v625,
          v1 + 373);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v626,
          v1 + 372);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v627,
          v1 + 371);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v628,
          v1 + 370);
        v623 = v1[369];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v629,
          &v623);
        v66 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v679,
                "BackwardSegmentExecutionEventTimesInterrupted");
        v624 = 0x2000000;
        v67 = v66;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v630,
          &v624);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)&unk_1806D1690,
          0,
          0,
          (__int64)v630,
          v67,
          (__int64)v629,
          (__int64)v628,
          (__int64)v627,
          (__int64)v626,
          (__int64)v625);
      }
    }
  }
  if ( v1[374] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0)
        && (unsigned int)dword_18079C700 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
      {
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v633,
          v1 + 378);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v634,
          v1 + 377);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v635,
          v1 + 376);
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v636,
          v1 + 375);
        v631 = v1[374];
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v637,
          &v631);
        v68 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                v680,
                "BackwardSegmentExecutionEventTimesError");
        v632 = 0x2000000;
        v69 = v68;
        wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
          v638,
          &v632);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18079C700,
          (unsigned int)word_1806D153A,
          0,
          0,
          (__int64)v638,
          v69,
          (__int64)v637,
          (__int64)v636,
          (__int64)v635,
          (__int64)v634,
          (__int64)v633);
      }
    }
  }
  if ( v1[379] )
  {
    DbgToolsImplicitRegisterProviderCheck();
    if ( (unsigned int)TelemetryEnabled() )
    {
      if ( dword_18079C700 && (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0) && (unsigned int)dword_18079C700 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18079C700, 0x400000000000LL) )
        {
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v641,
            v1 + 383);
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v642,
            v1 + 382);
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v643,
            v1 + 381);
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v644,
            v1 + 380);
          v639 = v1[379];
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v645,
            &v639);
          v70 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(
                  v681,
                  "BackwardRepositionTime");
          v640 = 0x2000000;
          v71 = v70;
          wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            v646,
            &v640);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_18079C700,
            (unsigned int)&unk_1806D14C8,
            0,
            0,
            (__int64)v646,
            v71,
            (__int64)v645,
            (__int64)v644,
            (__int64)v643,
            (__int64)v642,
            (__int64)v641);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18038df78  push    rbp
0x18038df7a  push    rbx
0x18038df7b  push    rsi
0x18038df7c  push    rdi
0x18038df7d  push    r12
0x18038df7f  push    r14
0x18038df81  push    r15
0x18038df83  lea     rbp, [rsp-1270h]
0x18038df8b  mov     eax, 1370h
0x18038df90  call    _alloca_probe
0x18038df95  sub     rsp, rax
0x18038df98  xor     esi, esi
0x18038df9a  lea     r14, dword_18079C700
0x18038dfa1  mov     rdi, rcx
0x18038dfa4  mov     rbx, 400000000000h
0x18038dfae  mov     r12d, 2000000h
0x18038dfb4  lea     r15d, [rsi+5]
0x18038dfb8  cmp     [rcx], rsi
0x18038dfbb  jz      loc_18038E073
0x18038dfc1  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038dfc6  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038dfcc  jz      loc_18038E073
0x18038dfd2  mov     eax, cs:dword_18079C700
0x18038dfd8  test    eax, eax
0x18038dfda  jz      loc_18038E073
0x18038dfe0  xor     edx, edx
0x18038dfe2  mov     rcx, r14
0x18038dfe5  call    _tlgKeywordOn
0x18038dfea  test    al, al
0x18038dfec  jz      loc_18038E073
0x18038dff2  mov     eax, cs:dword_18079C700
0x18038dff8  cmp     eax, r15d
0x18038dffb  jbe     short loc_18038E073
0x18038dffd  mov     rcx, cs:qword_18079C718
0x18038e004  mov     rax, cs:qword_18079C710
0x18038e00b  test    rbx, rax
0x18038e00e  jz      short loc_18038E073
0x18038e010  mov     rax, rcx
0x18038e013  and     rax, rbx
0x18038e016  cmp     rax, rcx
0x18038e019  jnz     short loc_18038E073
0x18038e01b  mov     rax, [rdi]
0x18038e01e  lea     rdx, unk_1806D3730
0x18038e025  mov     [rbp+12A0h+arg_0], rax
0x18038e02c  xor     r9d, r9d
0x18038e02f  lea     rax, aForwardcallcou; "ForwardCallCount"
0x18038e036  mov     [rbp+12A0h+arg_10], r12
0x18038e03d  mov     [rbp+12A0h+arg_8], rax
0x18038e044  xor     r8d, r8d
0x18038e047  lea     rax, [rbp+12A0h+arg_0]
0x18038e04e  mov     rcx, r14
0x18038e051  mov     [rsp+13A0h+var_1370], rax
0x18038e056  lea     rax, [rbp+12A0h+arg_8]
0x18038e05d  mov     [rsp+13A0h+var_1378], rax
0x18038e062  lea     rax, [rbp+12A0h+arg_10]
0x18038e069  mov     [rsp+13A0h+var_1380], rax
0x18038e06e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18038e073  cmp     [rdi+8], rsi
0x18038e077  jz      loc_18038E124
0x18038e07d  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038e082  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038e088  jz      loc_18038E124
0x18038e08e  mov     eax, cs:dword_18079C700
0x18038e094  test    eax, eax
0x18038e096  jz      loc_18038E124
0x18038e09c  xor     edx, edx
0x18038e09e  mov     rcx, r14
0x18038e0a1  call    _tlgKeywordOn
0x18038e0a6  test    al, al
0x18038e0a8  jz      short loc_18038E124
0x18038e0aa  mov     eax, cs:dword_18079C700
0x18038e0b0  cmp     eax, r15d
0x18038e0b3  jbe     short loc_18038E124
0x18038e0b5  mov     rcx, cs:qword_18079C718
0x18038e0bc  mov     rax, cs:qword_18079C710
0x18038e0c3  test    rbx, rax
0x18038e0c6  jz      short loc_18038E124
0x18038e0c8  mov     rax, rcx
0x18038e0cb  and     rax, rbx
0x18038e0ce  cmp     rax, rcx
0x18038e0d1  jnz     short loc_18038E124
0x18038e0d3  mov     rax, [rdi+8]
0x18038e0d7  lea     rdx, unk_1806D3778
0x18038e0de  mov     [rbp+12A0h+arg_18], rax
0x18038e0e5  xor     r9d, r9d
0x18038e0e8  lea     rax, aForwardsingles; "ForwardSingleStepCount"
0x18038e0ef  mov     [rsp+13A0h+var_1338], r12
0x18038e0f4  mov     [rsp+13A0h+var_1340], rax
0x18038e0f9  xor     r8d, r8d
0x18038e0fc  lea     rax, [rbp+12A0h+arg_18]
0x18038e103  mov     rcx, r14
0x18038e106  mov     [rsp+13A0h+var_1370], rax
0x18038e10b  lea     rax, [rsp+13A0h+var_1340]
0x18038e110  mov     [rsp+13A0h+var_1378], rax
0x18038e115  lea     rax, [rsp+13A0h+var_1338]
0x18038e11a  mov     [rsp+13A0h+var_1380], rax
0x18038e11f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18038e124  cmp     [rdi+10h], rsi
0x18038e128  jz      loc_18038E223
0x18038e12e  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038e133  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038e139  jz      loc_18038E223
0x18038e13f  mov     eax, cs:dword_18079C700
0x18038e145  test    eax, eax
0x18038e147  jz      loc_18038E223
0x18038e14d  xor     edx, edx
0x18038e14f  mov     rcx, r14
0x18038e152  call    _tlgKeywordOn
0x18038e157  test    al, al
0x18038e159  jz      loc_18038E223
0x18038e15f  mov     eax, cs:dword_18079C700
0x18038e165  cmp     eax, r15d
0x18038e168  jbe     loc_18038E223
0x18038e16e  mov     rcx, cs:qword_18079C718
0x18038e175  mov     rax, cs:qword_18079C710
0x18038e17c  test    rbx, rax
0x18038e17f  jz      loc_18038E223
0x18038e185  mov     rax, rcx
0x18038e188  and     rax, rbx
0x18038e18b  cmp     rax, rcx
0x18038e18e  jnz     loc_18038E223
0x18038e194  mov     rax, [rdi+30h]
0x18038e198  lea     rdx, word_1806D35DA
0x18038e19f  mov     [rsp+13A0h+var_1330], rax
0x18038e1a4  xor     r9d, r9d
0x18038e1a7  mov     rax, [rdi+28h]
0x18038e1ab  xor     r8d, r8d
0x18038e1ae  mov     [rsp+13A0h+var_1328], rax
0x18038e1b3  mov     rcx, r14
0x18038e1b6  mov     rax, [rdi+20h]
0x18038e1ba  mov     [rbp+12A0h+var_1320], rax
0x18038e1be  mov     rax, [rdi+18h]
0x18038e1c2  mov     [rbp+12A0h+var_1318], rax
0x18038e1c6  mov     rax, [rdi+10h]
0x18038e1ca  mov     [rbp+12A0h+var_1310], rax
0x18038e1ce  lea     rax, aForwardtotalre; "ForwardTotalReplayTime"
0x18038e1d5  mov     [rbp+12A0h+var_1308], rax
0x18038e1d9  lea     rax, [rsp+13A0h+var_1330]
0x18038e1de  mov     [rsp+13A0h+var_1350], rax
0x18038e1e3  lea     rax, [rsp+13A0h+var_1328]
0x18038e1e8  mov     [rsp+13A0h+var_1358], rax
0x18038e1ed  lea     rax, [rbp+12A0h+var_1320]
0x18038e1f1  mov     [rsp+13A0h+var_1360], rax
0x18038e1f6  lea     rax, [rbp+12A0h+var_1318]
0x18038e1fa  mov     [rsp+13A0h+var_1368], rax
0x18038e1ff  lea     rax, [rbp+12A0h+var_1310]
0x18038e203  mov     [rsp+13A0h+var_1370], rax
0x18038e208  lea     rax, [rbp+12A0h+var_1308]
0x18038e20c  mov     [rsp+13A0h+var_1378], rax
0x18038e211  lea     rax, [rbp+12A0h+var_1300]
0x18038e215  mov     [rsp+13A0h+var_1380], rax
0x18038e21a  mov     [rbp+12A0h+var_1300], r12
0x18038e21e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18038e223  cmp     [rdi+38h], rsi
0x18038e227  jz      loc_18038E31E
0x18038e22d  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038e232  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038e238  jz      loc_18038E31E
0x18038e23e  mov     eax, cs:dword_18079C700
0x18038e244  test    eax, eax
0x18038e246  jz      loc_18038E31E
0x18038e24c  xor     edx, edx
0x18038e24e  mov     rcx, r14
0x18038e251  call    _tlgKeywordOn
0x18038e256  test    al, al
0x18038e258  jz      loc_18038E31E
0x18038e25e  mov     eax, cs:dword_18079C700
0x18038e264  cmp     eax, r15d
0x18038e267  jbe     loc_18038E31E
0x18038e26d  mov     rcx, cs:qword_18079C718
0x18038e274  mov     rax, cs:qword_18079C710
0x18038e27b  test    rbx, rax
0x18038e27e  jz      loc_18038E31E
0x18038e284  mov     rax, rcx
0x18038e287  and     rax, rbx
0x18038e28a  cmp     rax, rcx
0x18038e28d  jnz     loc_18038E31E
0x18038e293  mov     rax, [rdi+58h]
0x18038e297  lea     rdx, unk_1806D3568
0x18038e29e  mov     [rbp+12A0h+var_12F8], rax
0x18038e2a2  xor     r9d, r9d
0x18038e2a5  mov     rax, [rdi+50h]
0x18038e2a9  xor     r8d, r8d
0x18038e2ac  mov     [rbp+12A0h+var_12F0], rax
0x18038e2b0  mov     rcx, r14
0x18038e2b3  mov     rax, [rdi+48h]
0x18038e2b7  mov     [rbp+12A0h+var_12E8], rax
0x18038e2bb  mov     rax, [rdi+40h]
0x18038e2bf  mov     [rbp+12A0h+var_12E0], rax
0x18038e2c3  mov     rax, [rdi+38h]
0x18038e2c7  mov     [rbp+12A0h+var_12D8], rax
0x18038e2cb  lea     rax, aForwardfastrep_6; "ForwardFastReplayTime"
0x18038e2d2  mov     [rbp+12A0h+var_12D0], rax
0x18038e2d6  lea     rax, [rbp+12A0h+var_12F8]
0x18038e2da  mov     [rsp+13A0h+var_1350], rax
0x18038e2df  lea     rax, [rbp+12A0h+var_12F0]
0x18038e2e3  mov     [rsp+13A0h+var_1358], rax
0x18038e2e8  lea     rax, [rbp+12A0h+var_12E8]
0x18038e2ec  mov     [rsp+13A0h+var_1360], rax
0x18038e2f1  lea     rax, [rbp+12A0h+var_12E0]
0x18038e2f5  mov     [rsp+13A0h+var_1368], rax
0x18038e2fa  lea     rax, [rbp+12A0h+var_12D8]
0x18038e2fe  mov     [rsp+13A0h+var_1370], rax
0x18038e303  lea     rax, [rbp+12A0h+var_12D0]
0x18038e307  mov     [rsp+13A0h+var_1378], rax
0x18038e30c  lea     rax, [rbp+12A0h+var_12C8]
0x18038e310  mov     [rsp+13A0h+var_1380], rax
0x18038e315  mov     [rbp+12A0h+var_12C8], r12
0x18038e319  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18038e31e  cmp     [rdi+60h], rsi
0x18038e322  jz      loc_18038E41C
0x18038e328  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038e32d  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038e333  jz      loc_18038E41C
0x18038e339  mov     eax, cs:dword_18079C700
0x18038e33f  test    eax, eax
0x18038e341  jz      loc_18038E41C
0x18038e347  xor     edx, edx
0x18038e349  mov     rcx, r14
0x18038e34c  call    _tlgKeywordOn
0x18038e351  test    al, al
0x18038e353  jz      loc_18038E41C
0x18038e359  mov     eax, cs:dword_18079C700
0x18038e35f  cmp     eax, r15d
0x18038e362  jbe     loc_18038E41C
0x18038e368  mov     rcx, cs:qword_18079C718
0x18038e36f  mov     rax, cs:qword_18079C710
0x18038e376  test    rbx, rax
0x18038e379  jz      loc_18038E41C
0x18038e37f  mov     rax, rcx
0x18038e382  and     rax, rbx
0x18038e385  cmp     rax, rcx
0x18038e388  jnz     loc_18038E41C
0x18038e38e  mov     rax, [rdi+80h]
0x18038e395  lea     rdx, word_1806D36BE
0x18038e39c  mov     [rbp+12A0h+var_12C0], rax
0x18038e3a0  xor     r9d, r9d
0x18038e3a3  mov     rax, [rdi+78h]
0x18038e3a7  xor     r8d, r8d
0x18038e3aa  mov     [rbp+12A0h+var_12B8], rax
0x18038e3ae  mov     rcx, r14
0x18038e3b1  mov     rax, [rdi+70h]
0x18038e3b5  mov     [rbp+12A0h+var_12B0], rax
0x18038e3b9  mov     rax, [rdi+68h]
0x18038e3bd  mov     [rbp+12A0h+var_12A8], rax
0x18038e3c1  mov     rax, [rdi+60h]
0x18038e3c5  mov     [rbp+12A0h+var_12A0], rax
0x18038e3c9  lea     rax, aForwardfastrep_9; "ForwardFastReplayEventTimesMemoryWatchp"...
0x18038e3d0  mov     [rbp+12A0h+var_1298], rax
0x18038e3d4  lea     rax, [rbp+12A0h+var_12C0]
0x18038e3d8  mov     [rsp+13A0h+var_1350], rax
0x18038e3dd  lea     rax, [rbp+12A0h+var_12B8]
0x18038e3e1  mov     [rsp+13A0h+var_1358], rax
0x18038e3e6  lea     rax, [rbp+12A0h+var_12B0]
0x18038e3ea  mov     [rsp+13A0h+var_1360], rax
0x18038e3ef  lea     rax, [rbp+12A0h+var_12A8]
0x18038e3f3  mov     [rsp+13A0h+var_1368], rax
0x18038e3f8  lea     rax, [rbp+12A0h+var_12A0]
0x18038e3fc  mov     [rsp+13A0h+var_1370], rax
0x18038e401  lea     rax, [rbp+12A0h+var_1298]
0x18038e405  mov     [rsp+13A0h+var_1378], rax
0x18038e40a  lea     rax, [rbp+12A0h+var_1290]
0x18038e40e  mov     [rsp+13A0h+var_1380], rax
0x18038e413  mov     [rbp+12A0h+var_1290], r12
0x18038e417  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_DbgToolsSafe_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18038e41c  cmp     [rdi+88h], rsi
0x18038e423  jz      loc_18038E529
0x18038e429  call    DbgTelemetryToolsImplicitRegisterProviderCheck
0x18038e42e  cmp     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, esi; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x18038e434  jz      loc_18038E529
0x18038e43a  mov     eax, cs:dword_18079C700
0x18038e440  test    eax, eax
0x18038e442  jz      loc_18038E529
0x18038e448  xor     edx, edx
0x18038e44a  mov     rcx, r14
0x18038e44d  call    _tlgKeywordOn
0x18038e452  test    al, al
0x18038e454  jz      loc_18038E529
0x18038e45a  mov     eax, cs:dword_18079C700
0x18038e460  cmp     eax, r15d
0x18038e463  jbe     loc_18038E529
0x18038e469  mov     rcx, cs:qword_18079C718
0x18038e470  mov     rax, cs:qword_18079C710
0x18038e477  test    rbx, rax
0x18038e47a  jz      loc_18038E529
0x18038e480  mov     rax, rcx
0x18038e483  and     rax, rbx
0x18038e486  cmp     rax, rcx
0x18038e489  jnz     loc_18038E529
0x18038e48f  mov     rax, [rdi+0A8h]
0x18038e496  lea     rdx, dword_1806D364C
0x18038e49d  mov     [rbp+12A0h+var_1288], rax
0x18038e4a1  xor     r9d, r9d
0x18038e4a4  mov     rax, [rdi+0A0h]
0x18038e4ab  xor     r8d, r8d
0x18038e4ae  mov     [rbp+12A0h+var_1280], rax
0x18038e4b2  mov     rcx, r14
0x18038e4b5  mov     rax, [rdi+98h]
0x18038e4bc  mov     [rbp+12A0h+var_1278], rax
0x18038e4c0  mov     rax, [rdi+90h]
  ... truncated ...
```
