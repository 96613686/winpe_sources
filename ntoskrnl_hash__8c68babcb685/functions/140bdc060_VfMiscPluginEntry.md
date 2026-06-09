# VfMiscPluginEntry

- ea: `0x140bdc060`
- end: `0x140bdcd40`
- name: `VfMiscPluginEntry`
- size: `3296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x14053fcf0`
- `0x14063a0ac`
- `0x14064219c`
- `0x1406dc8c0`
- `0x140bd91f4`
- `0x140bdc060`
- `0x140bdec04`

## string_xrefs

- `0x140bdc18f`: `ExInitializeNPagedLookasideList`
- `0x140bdc1b0`: `ExInitializePagedLookasideList`
- `0x140bdc1da`: `ExDeletePagedLookasideList`
- `0x140bdc27b`: `ExDeleteNPagedLookasideList`
- `0x140bdc16e`: `ExInitializeLookasideListEx`
- `0x140bdc58f`: `KeRemoveQueueDpc`
- `0x140bdc369`: `ObGetObjectSecurity`
- `0x140bdc297`: `ExDeleteLookasideListEx`
- `0x140bdca86`: `ExReleaseResourceForThreadLite`
- `0x140bdc780`: `ExDeleteResourceLite`

## pseudocode

```c
__int64 VfMiscPluginEntry()
{
  int v0; // edi
  int v1; // eax
  volatile __int32 *v2; // rcx
  int v3; // eax
  volatile __int32 *v4; // rcx
  const char *v6; // [rsp+20h] [rbp-E0h] BYREF
  int v7; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall *v8)(); // [rsp+30h] [rbp-D0h]
  __int64 v9; // [rsp+38h] [rbp-C8h]
  const char *v10; // [rsp+40h] [rbp-C0h]
  int v11; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall *v12)(); // [rsp+50h] [rbp-B0h]
  __int64 v13; // [rsp+58h] [rbp-A8h]
  const char *v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v16)(); // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  const char *v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v20)(); // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  const char *v22; // [rsp+A0h] [rbp-60h]
  int v23; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v24)(); // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  const char *v26; // [rsp+C0h] [rbp-40h]
  int v27; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v28)(); // [rsp+D0h] [rbp-30h]
  __int64 v29; // [rsp+D8h] [rbp-28h]
  const char *v30; // [rsp+E0h] [rbp-20h]
  int v31; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v32)(); // [rsp+F0h] [rbp-10h]
  __int64 v33; // [rsp+F8h] [rbp-8h]
  const char *v34; // [rsp+100h] [rbp+0h]
  int v35; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v36)(); // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  const char *v38; // [rsp+120h] [rbp+20h]
  int v39; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v40)(); // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  const char *v42; // [rsp+140h] [rbp+40h]
  int v43; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v44)(); // [rsp+150h] [rbp+50h]
  __int64 (__fastcall *v45)(); // [rsp+158h] [rbp+58h]
  const char *v46; // [rsp+160h] [rbp+60h]
  int v47; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v48)(); // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v49)(); // [rsp+178h] [rbp+78h]
  const char *v50; // [rsp+180h] [rbp+80h]
  int v51; // [rsp+188h] [rbp+88h]
  __int64 (__fastcall *v52)(); // [rsp+190h] [rbp+90h]
  __int64 (__fastcall *v53)(); // [rsp+198h] [rbp+98h]
  const char *v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v56)(); // [rsp+1B0h] [rbp+B0h]
  __int64 v57; // [rsp+1B8h] [rbp+B8h]
  const char *v58; // [rsp+1C0h] [rbp+C0h]
  int v59; // [rsp+1C8h] [rbp+C8h]
  __int64 (__fastcall *v60)(); // [rsp+1D0h] [rbp+D0h]
  __int64 v61; // [rsp+1D8h] [rbp+D8h]
  const char *v62; // [rsp+1E0h] [rbp+E0h]
  int v63; // [rsp+1E8h] [rbp+E8h]
  __int64 (__fastcall *v64)(); // [rsp+1F0h] [rbp+F0h]
  __int64 v65; // [rsp+1F8h] [rbp+F8h]
  const char *v66; // [rsp+200h] [rbp+100h]
  int v67; // [rsp+208h] [rbp+108h]
  __int64 (__fastcall *v68)(); // [rsp+210h] [rbp+110h]
  __int64 v69; // [rsp+218h] [rbp+118h]
  const char *v70; // [rsp+220h] [rbp+120h]
  int v71; // [rsp+228h] [rbp+128h]
  __int64 v72; // [rsp+230h] [rbp+130h]
  __int64 (__fastcall *v73)(); // [rsp+238h] [rbp+138h]
  const char *v74; // [rsp+240h] [rbp+140h]
  int v75; // [rsp+248h] [rbp+148h]
  __int64 (__fastcall *v76)(); // [rsp+250h] [rbp+150h]
  __int64 (__fastcall *v77)(); // [rsp+258h] [rbp+158h]
  const char *v78; // [rsp+260h] [rbp+160h]
  int v79; // [rsp+268h] [rbp+168h]
  __int64 (__fastcall *v80)(); // [rsp+270h] [rbp+170h]
  __int64 v81; // [rsp+278h] [rbp+178h]
  const char *v82; // [rsp+280h] [rbp+180h]
  int v83; // [rsp+288h] [rbp+188h]
  __int64 (__fastcall *v84)(); // [rsp+290h] [rbp+190h]
  __int64 v85; // [rsp+298h] [rbp+198h]
  const char *v86; // [rsp+2A0h] [rbp+1A0h]
  int v87; // [rsp+2A8h] [rbp+1A8h]
  __int64 (__fastcall *v88)(); // [rsp+2B0h] [rbp+1B0h]
  __int64 v89; // [rsp+2B8h] [rbp+1B8h]
  const char *v90; // [rsp+2C0h] [rbp+1C0h]
  int v91; // [rsp+2C8h] [rbp+1C8h]
  __int64 (__fastcall *v92)(); // [rsp+2D0h] [rbp+1D0h]
  __int64 v93; // [rsp+2D8h] [rbp+1D8h]
  const char *v94; // [rsp+2E0h] [rbp+1E0h]
  int v95; // [rsp+2E8h] [rbp+1E8h]
  __int64 (__fastcall *v96)(); // [rsp+2F0h] [rbp+1F0h]
  __int64 v97; // [rsp+2F8h] [rbp+1F8h]
  const char *v98; // [rsp+300h] [rbp+200h]
  int v99; // [rsp+308h] [rbp+208h]
  __int64 (__fastcall *v100)(); // [rsp+310h] [rbp+210h]
  __int64 v101; // [rsp+318h] [rbp+218h]
  const char *v102; // [rsp+320h] [rbp+220h]
  int v103; // [rsp+328h] [rbp+228h]
  __int64 (__fastcall *v104)(); // [rsp+330h] [rbp+230h]
  __int64 v105; // [rsp+338h] [rbp+238h]
  const char *v106; // [rsp+340h] [rbp+240h]
  int v107; // [rsp+348h] [rbp+248h]
  __int64 (__fastcall *v108)(); // [rsp+350h] [rbp+250h]
  __int64 v109; // [rsp+358h] [rbp+258h]
  const char *v110; // [rsp+360h] [rbp+260h]
  int v111; // [rsp+368h] [rbp+268h]
  __int64 (__fastcall *v112)(); // [rsp+370h] [rbp+270h]
  __int64 v113; // [rsp+378h] [rbp+278h]
  const char *v114; // [rsp+380h] [rbp+280h]
  int v115; // [rsp+388h] [rbp+288h]
  __int64 (__fastcall *v116)(); // [rsp+390h] [rbp+290h]
  __int64 v117; // [rsp+398h] [rbp+298h]
  const char *v118; // [rsp+3A0h] [rbp+2A0h]
  int v119; // [rsp+3A8h] [rbp+2A8h]
  __int64 (__fastcall *v120)(); // [rsp+3B0h] [rbp+2B0h]
  __int64 v121; // [rsp+3B8h] [rbp+2B8h]
  const char *v122; // [rsp+3C0h] [rbp+2C0h]
  int v123; // [rsp+3C8h] [rbp+2C8h]
  __int64 (__fastcall *v124)(); // [rsp+3D0h] [rbp+2D0h]
  __int64 v125; // [rsp+3D8h] [rbp+2D8h]
  const char *v126; // [rsp+3E0h] [rbp+2E0h]
  int v127; // [rsp+3E8h] [rbp+2E8h]
  __int64 (__fastcall *v128)(); // [rsp+3F0h] [rbp+2F0h]
  __int64 v129; // [rsp+3F8h] [rbp+2F8h]
  const char *v130; // [rsp+400h] [rbp+300h]
  int v131; // [rsp+408h] [rbp+308h]
  __int64 (__fastcall *v132)(); // [rsp+410h] [rbp+310h]
  __int64 v133; // [rsp+418h] [rbp+318h]
  const char *v134; // [rsp+420h] [rbp+320h]
  int v135; // [rsp+428h] [rbp+328h]
  __int64 (__fastcall *v136)(); // [rsp+430h] [rbp+330h]
  __int64 v137; // [rsp+438h] [rbp+338h]
  const char *v138; // [rsp+440h] [rbp+340h]
  int v139; // [rsp+448h] [rbp+348h]
  __int64 (__fastcall *v140)(); // [rsp+450h] [rbp+350h]
  __int64 v141; // [rsp+458h] [rbp+358h]
  const char *v142; // [rsp+460h] [rbp+360h]
  int v143; // [rsp+468h] [rbp+368h]
  __int64 (__fastcall *v144)(); // [rsp+470h] [rbp+370h]
  __int64 v145; // [rsp+478h] [rbp+378h]
  const char *v146; // [rsp+480h] [rbp+380h]
  int v147; // [rsp+488h] [rbp+388h]
  __int64 (__fastcall *v148)(); // [rsp+490h] [rbp+390h]
  __int64 v149; // [rsp+498h] [rbp+398h]
  const char *v150; // [rsp+4A0h] [rbp+3A0h]
  int v151; // [rsp+4A8h] [rbp+3A8h]
  __int64 (__fastcall *v152)(); // [rsp+4B0h] [rbp+3B0h]
  __int64 v153; // [rsp+4B8h] [rbp+3B8h]
  const char *v154; // [rsp+4C0h] [rbp+3C0h]
  int v155; // [rsp+4C8h] [rbp+3C8h]
  __int64 (__fastcall *v156)(); // [rsp+4D0h] [rbp+3D0h]
  __int64 v157; // [rsp+4D8h] [rbp+3D8h]
  const char *v158; // [rsp+4E0h] [rbp+3E0h]
  int v159; // [rsp+4E8h] [rbp+3E8h]
  __int64 (__fastcall *v160)(); // [rsp+4F0h] [rbp+3F0h]
  __int64 v161; // [rsp+4F8h] [rbp+3F8h]
  const char *v162; // [rsp+500h] [rbp+400h]
  int v163; // [rsp+508h] [rbp+408h]
  __int64 (__fastcall *v164)(); // [rsp+510h] [rbp+410h]
  __int64 v165; // [rsp+518h] [rbp+418h]
  const char *v166; // [rsp+520h] [rbp+420h]
  int v167; // [rsp+528h] [rbp+428h]
  __int64 (__fastcall *v168)(); // [rsp+530h] [rbp+430h]
  __int64 v169; // [rsp+538h] [rbp+438h]
  const char *v170; // [rsp+540h] [rbp+440h]
  int v171; // [rsp+548h] [rbp+448h]
  __int64 (__fastcall *v172)(); // [rsp+550h] [rbp+450h]
  __int64 (__fastcall *v173)(); // [rsp+558h] [rbp+458h]
  const char *v174; // [rsp+560h] [rbp+460h]
  int v175; // [rsp+568h] [rbp+468h]
  __int64 (__fastcall *v176)(); // [rsp+570h] [rbp+470h]
  __int64 (__fastcall *v177)(); // [rsp+578h] [rbp+478h]
  const char *v178; // [rsp+580h] [rbp+480h]
  int v179; // [rsp+588h] [rbp+488h]
  __int64 (__fastcall *v180)(); // [rsp+590h] [rbp+490h]
  __int64 v181; // [rsp+598h] [rbp+498h]
  const char *v182; // [rsp+5A0h] [rbp+4A0h]
  int v183; // [rsp+5A8h] [rbp+4A8h]
  __int64 (__fastcall *v184)(); // [rsp+5B0h] [rbp+4B0h]
  __int64 v185; // [rsp+5B8h] [rbp+4B8h]
  const char *v186; // [rsp+5C0h] [rbp+4C0h]
  int v187; // [rsp+5C8h] [rbp+4C8h]
  __int64 (__fastcall *v188)(); // [rsp+5D0h] [rbp+4D0h]
  __int64 v189; // [rsp+5D8h] [rbp+4D8h]
  const char *v190; // [rsp+5E0h] [rbp+4E0h]
  int v191; // [rsp+5E8h] [rbp+4E8h]
  __int64 (__fastcall *v192)(); // [rsp+5F0h] [rbp+4F0h]
  __int64 v193; // [rsp+5F8h] [rbp+4F8h]
  const char *v194; // [rsp+600h] [rbp+500h]
  int v195; // [rsp+608h] [rbp+508h]
  __int64 (__fastcall *v196)(); // [rsp+610h] [rbp+510h]
  __int64 v197; // [rsp+618h] [rbp+518h]
  const char *v198; // [rsp+620h] [rbp+520h]
  int v199; // [rsp+628h] [rbp+528h]
  __int64 (__fastcall *v200)(); // [rsp+630h] [rbp+530h]
  __int64 v201; // [rsp+638h] [rbp+538h]
  const char *v202; // [rsp+640h] [rbp+540h]
  int v203; // [rsp+648h] [rbp+548h]
  __int64 (__fastcall *v204)(); // [rsp+650h] [rbp+550h]
  __int64 v205; // [rsp+658h] [rbp+558h]
  const char *v206; // [rsp+660h] [rbp+560h]
  int v207; // [rsp+668h] [rbp+568h]
  __int64 (__fastcall *v208)(); // [rsp+670h] [rbp+570h]
  __int64 v209; // [rsp+678h] [rbp+578h]
  const char *v210; // [rsp+680h] [rbp+580h]
  int v211; // [rsp+688h] [rbp+588h]
  __int64 (__fastcall *v212)(); // [rsp+690h] [rbp+590h]
  __int64 v213; // [rsp+698h] [rbp+598h]
  const char *v214; // [rsp+6A0h] [rbp+5A0h]
  int v215; // [rsp+6A8h] [rbp+5A8h]
  __int64 (__fastcall *v216)(); // [rsp+6B0h] [rbp+5B0h]
  __int64 v217; // [rsp+6B8h] [rbp+5B8h]
  const char *v218; // [rsp+6C0h] [rbp+5C0h]
  int v219; // [rsp+6C8h] [rbp+5C8h]
  __int64 (__fastcall *v220)(); // [rsp+6D0h] [rbp+5D0h]
  __int64 (__fastcall *v221)(); // [rsp+6D8h] [rbp+5D8h]
  const char *v222; // [rsp+6E0h] [rbp+5E0h]
  int v223; // [rsp+6E8h] [rbp+5E8h]
  __int64 (__fastcall *v224)(); // [rsp+6F0h] [rbp+5F0h]
  __int64 v225; // [rsp+6F8h] [rbp+5F8h]
  const char *v226; // [rsp+700h] [rbp+600h]
  int v227; // [rsp+708h] [rbp+608h]
  __int64 (__fastcall *v228)(); // [rsp+710h] [rbp+610h]
  __int64 v229; // [rsp+718h] [rbp+618h]
  const char *v230; // [rsp+720h] [rbp+620h]
  int v231; // [rsp+728h] [rbp+628h]
  __int64 (__fastcall *v232)(); // [rsp+730h] [rbp+630h]
  __int64 v233; // [rsp+738h] [rbp+638h]
  const char *v234; // [rsp+740h] [rbp+640h]
  int v235; // [rsp+748h] [rbp+648h]
  __int64 (__fastcall *v236)(); // [rsp+750h] [rbp+650h]
  __int64 v237; // [rsp+758h] [rbp+658h]
  const char *v238; // [rsp+760h] [rbp+660h]
  int v239; // [rsp+768h] [rbp+668h]
  __int64 (__fastcall *v240)(); // [rsp+770h] [rbp+670h]
  __int64 v241; // [rsp+778h] [rbp+678h]
  const char *v242; // [rsp+780h] [rbp+680h]
  int v243; // [rsp+788h] [rbp+688h]
  __int64 (__fastcall *v244)(); // [rsp+790h] [rbp+690h]
  __int64 v245; // [rsp+798h] [rbp+698h]
  const char *v246; // [rsp+7A0h] [rbp+6A0h]
  int v247; // [rsp+7A8h] [rbp+6A8h]
  __int64 (__fastcall *v248)(); // [rsp+7B0h] [rbp+6B0h]
  __int64 v249; // [rsp+7B8h] [rbp+6B8h]
  const char *v250; // [rsp+7C0h] [rbp+6C0h]
  int v251; // [rsp+7C8h] [rbp+6C8h]
  __int64 (__fastcall *v252)(); // [rsp+7D0h] [rbp+6D0h]
  __int64 v253; // [rsp+7D8h] [rbp+6D8h]
  const char *v254; // [rsp+7E0h] [rbp+6E0h]
  int v255; // [rsp+7E8h] [rbp+6E8h]
  __int64 (__fastcall *v256)(); // [rsp+7F0h] [rbp+6F0h]
  __int64 v257; // [rsp+7F8h] [rbp+6F8h]
  const char *v258; // [rsp+800h] [rbp+700h]
  int v259; // [rsp+808h] [rbp+708h]
  __int64 (__fastcall *v260)(); // [rsp+810h] [rbp+710h]
  __int64 v261; // [rsp+818h] [rbp+718h]
  const char *v262; // [rsp+820h] [rbp+720h]
  int v263; // [rsp+828h] [rbp+728h]
  __int64 (__fastcall *v264)(); // [rsp+830h] [rbp+730h]
  __int64 v265; // [rsp+838h] [rbp+738h]
  const char *v266; // [rsp+840h] [rbp+740h]
  int v267; // [rsp+848h] [rbp+748h]
  __int64 (__fastcall *v268)(); // [rsp+850h] [rbp+750h]
  __int64 v269; // [rsp+858h] [rbp+758h]
  const char *v270; // [rsp+860h] [rbp+760h]
  int v271; // [rsp+868h] [rbp+768h]
  __int64 (__fastcall *v272)(); // [rsp+870h] [rbp+770h]
  __int64 v273; // [rsp+878h] [rbp+778h]
  const char *v274; // [rsp+880h] [rbp+780h]
  int v275; // [rsp+888h] [rbp+788h]
  __int64 (__fastcall *v276)(); // [rsp+890h] [rbp+790h]
  __int64 v277; // [rsp+898h] [rbp+798h]
  const char *v278; // [rsp+8A0h] [rbp+7A0h]
  int v279; // [rsp+8A8h] [rbp+7A8h]
  __int64 v280; // [rsp+8B0h] [rbp+7B0h]
  __int64 v281; // [rsp+8B8h] [rbp+7B8h]
  const char *v282; // [rsp+8C0h] [rbp+7C0h]
  int v283; // [rsp+8C8h] [rbp+7C8h]
  __int64 v284; // [rsp+8D0h] [rbp+7D0h]
  __int64 v285; // [rsp+8D8h] [rbp+7D8h]

  v7 = 238;
  v9 = 0;
  qword_140EF2048 = (__int64)VfMiscPluginUnload;
  v6 = "MmAllocateContiguousMemory";
  v8 = VfMiscMmAllocateContiguousMemory_Entry;
  v10 = "MmAllocateContiguousMemoryEx";
  v12 = VfMiscMmAllocateContiguousMemoryEx_Entry;
  v14 = "KeReleaseQueuedSpinLock";
  v16 = VfMiscKeReleaseQueuedSpinLock_Entry;
  v18 = "KeInitializeEvent";
  v20 = VfMiscKeInitializeEvent_Entry;
  v22 = "KeInitializeMutant";
  v24 = VfMiscKeInitializeMutant_Entry;
  v26 = "KeInitializeMutex";
  v28 = VfMiscKeInitializeMutant_Entry;
  v30 = "KeInitializeTimerEx";
  v32 = VfMiscKeInitializeTimerEx_Entry;
  v34 = "KeWaitForSingleObject";
  v36 = VfMiscKeWaitForSingleObject_Entry;
  v38 = "KeWaitForMultipleObjects";
  v40 = VfMiscKeWaitForMultipleObjects_Entry;
  v42 = "ExInitializeLookasideListEx";
  v44 = VfMiscExInitializeLookasideListEx_Entry;
  v45 = VfMiscExInitializePagedLookasideList_Exit;
  v46 = "ExInitializeNPagedLookasideList";
  v48 = VfMiscExInitializeNPagedLookasideList_Entry;
  v49 = VfMiscExInitializePagedLookasideList_Exit;
  v50 = "ExInitializePagedLookasideList";
  v52 = VfMiscExInitializeNPagedLookasideList_Entry;
  v53 = VfMiscExInitializePagedLookasideList_Exit;
  v54 = "ExDeletePagedLookasideList";
  v11 = 237;
  v13 = 0;
  v15 = 260;
  v17 = 0;
  v19 = 284;
  v21 = 0;
  v23 = 283;
  v25 = 0;
  v27 = 282;
  v29 = 0;
  v31 = 279;
  v33 = 0;
  v35 = 240;
  v37 = 0;
  v39 = 241;
  v41 = 0;
  v43 = 399;
  v47 = 398;
  v51 = 397;
  v55 = 408;
  v57 = 0;
  v56 = VfMiscExDeleteLookasideListEx_Entry;
  v58 = "ExDeleteNPagedLookasideList";
  v60 = VfMiscExDeleteLookasideListEx_Entry;
  v62 = "ExDeleteLookasideListEx";
  v64 = VfMiscExDeleteLookasideListEx_Entry;
  v66 = "ObReferenceObjectByPointer";
  v68 = VfMiscObReferenceObjectByPointer_Entry;
  v70 = "ObReferenceObjectByHandle";
  v73 = VfMiscObReferenceObjectByHandle_Exit;
  v74 = "ObfReferenceObject";
  v76 = VfMiscObfDereferenceObject_Entry;
  v77 = VfMiscObfReferenceObject_Exit;
  v78 = "ObfReferenceObjectWithTag";
  v80 = VfMiscObfReferenceObjectWithTag_Entry;
  v82 = "ObfDereferenceObject";
  v84 = VfMiscObfDereferenceObject_Entry;
  v86 = "ObfDereferenceObjectWithTag";
  v88 = VfMiscObfReferenceObjectWithTag_Entry;
  v90 = "ObGetObjectSecurity";
  v92 = VfMiscObGetObjectSecurity_Entry;
  v94 = "ObReferenceObjectByPointerWithTag";
  v96 = VfMiscObReferenceObjectByPointerWithTag_Entry;
  v98 = "KeReleaseSpinLock";
  v100 = VfMiscKeReleaseSpinLock_Entry;
  v102 = "KeAcquireSpinLockAtDpcLevel";
  v104 = VfMiscObfDereferenceObject_Entry;
  v106 = "KeReleaseSpinLockFromDpcLevel";
  v108 = VfMiscObfDereferenceObject_Entry;
  v59 = 409;
  v61 = 0;
  v63 = 410;
  v65 = 0;
  v67 = 201;
  v69 = 0;
  v71 = 202;
  v72 = 0;
  v75 = 196;
  v79 = 195;
  v81 = 0;
  v83 = 198;
  v85 = 0;
  v87 = 197;
  v89 = 0;
  v91 = 203;
  v93 = 0;
  v95 = 200;
  v97 = 0;
  v99 = 259;
  v101 = 0;
  v103 = 293;
  v105 = 0;
  v107 = 258;
  v109 = 0;
  v110 = "KeAcquireSpinLockRaiseToDpc";
  v112 = VfMiscKeAcquireSpinLockRaiseToDpc_Entry;
  v114 = "IoConnectInterrupt";
  v116 = ViSpIoAllocateIrp_Exit;
  v118 = "IoDisconnectInterrupt";
  v120 = ViSpIoAllocateIrp_Exit;
  v122 = "IoConnectInterruptEx";
  v124 = ViSpIoAllocateIrp_Exit;
  v126 = "IoDisconnectInterruptEx";
  v128 = ViSpIoAllocateIrp_Exit;
  v130 = "KeReleaseMutex";
  v132 = VfMiscKeReleaseMutant_Entry;
  v134 = "KeInsertQueueDpc";
  v136 = VfMiscKeInsertQueueDpc_Entry;
  v138 = "KeRemoveQueueDpc";
  v140 = VfMiscKeRemoveQueueDpc_Entry;
  v142 = "KeTryToAcquireSpinLockAtDpcLevel";
  v144 = VfMiscKeTryToAcquireSpinLockAtDpcLevel_Entry;
  v146 = "KeTryToAcquireInStackQueuedSpinLockAtDpcLevel";
  v148 = VfMiscKeTryToAcquireInStackQueuedSpinLockAtDpcLevel_Entry;
  v150 = "KeAcquireInStackQueuedSpinLockAtDpcLevel";
  v152 = VfMiscKeAcquireInStackQueuedSpinLockAtDpcLevel_Entry;
  v154 = "KeAcquireInStackQueuedSpinLockForDpc";
  v156 = VfMiscKeAcquireInStackQueuedSpinLockForDpc_Entry;
  v158 = "KeSetEvent";
  v160 = VfMiscKeSetEvent_Entry;
  v162 = "IoFreeMdl";
  v111 = 292;
  v113 = 0;
  v115 = 358;
  v117 = 0;
  v119 = 343;
  v121 = 0;
  v123 = 357;
  v125 = 0;
  v127 = 342;
  v129 = 0;
  v131 = 261;
  v133 = 0;
  v135 = 276;
  v137 = 0;
  v139 = 254;
  v141 = 0;
  v143 = 242;
  v145 = 0;
  v147 = 245;
  v149 = 0;
  v151 = 298;
  v153 = 0;
  v155 = 297;
  v157 = 0;
  v159 = 250;
  v161 = 0;
  v163 = 339;
  v164 = VfMiscIoFreeMdl_Entry;
  v166 = "IoInitializeWorkItem";
  v168 = VfMiscIoInitializeWorkItem_Entry;
  v170 = "ExInitializeResourceLite";
  v172 = VfMiscExInitializeResourceLite_Entry;
  v173 = VfMiscExInitializeResourceLite_Exit;
  v174 = "ExDeleteResourceLite";
  v176 = VfMiscExDeleteResourceLite_Entry;
  v177 = VfMiscExDeleteResourceLite_Exit;
  v178 = "ExReleaseFastMutex";
  v180 = VfMiscExReleaseFastMutex_Entry;
  v182 = "ExAcquireFastMutexUnsafe";
  v184 = VfMiscExAcquireFastMutexUnsafe_Entry;
  v186 = "ExReleaseFastMutexUnsafe";
  v188 = VfMiscExReleaseFastMutexUnsafe_Entry;
  v190 = "ExfAcquirePushLockExclusive";
  v192 = VfMiscExfAcquirePushLockExclusive_Entry;
  v194 = "ExfAcquirePushLockShared";
  v196 = VfMiscExfAcquirePushLockExclusive_Entry;
  v198 = "ExfTryAcquirePushLockShared";
  v200 = VfMiscExfAcquirePushLockExclusive_Entry;
  v202 = "ExfReleasePushLock";
  v204 = VfMiscExfReleasePushLockShared_Entry;
  v206 = "ExfTryToWakePushLock";
  v208 = VfMiscExfReleasePushLockShared_Entry;
  v210 = "ExfReleasePushLockShared";
  v212 = VfMiscExfReleasePushLockShared_Entry;
  v214 = "MmUnmapLockedPages";
  v165 = 0;
  v167 = 328;
  v169 = 0;
  v171 = 396;
  v175 = 407;
  v179 = 390;
  v181 = 0;
  v183 = 424;
  v185 = 0;
  v187 = 389;
  v189 = 0;
  v191 = 380;
  v193 = 0;
  v195 = 379;
  v197 = 0;
  v199 = 376;
  v201 = 0;
  v203 = 378;
  v205 = 0;
  v207 = 375;
  v209 = 0;
  v211 = 377;
  v213 = 0;
  v215 = 210;
  v217 = 0;
  v216 = VfMiscMmUnmapLockedPages_Entry;
  v218 = "MmBuildMdlForNonPagedPool";
  v220 = VfMiscMmBuildMdlForNonPagedPool_Entry;
  v221 = VfMiscMmBuildMdlForNonPagedPool_Exit;
  v222 = "ExAcquireResourceExclusiveLite";
  v224 = VfMiscExAcquireSharedWaitForExclusive_Entry;
  v226 = "ExAcquireResourceSharedLite";
  v228 = VfMiscExAcquireSharedWaitForExclusive_Entry;
  v230 = "ExAcquireSharedStarveExclusive";
  v232 = VfMiscExAcquireSharedWaitForExclusive_Entry;
  v234 = "ExAcquireSharedWaitForExclusive";
  v236 = VfMiscExAcquireSharedWaitForExclusive_Entry;
  v238 = "ExReleaseResourceLite";
  v240 = VfMiscExReleaseResourceLite_Entry;
  v242 = "ExReleaseResourceAndLeaveCriticalRegion";
  v244 = VfMiscExReleaseResourceLite_Entry;
  v246 = "ExReleaseResourceAndLeavePriorityRegion";
  v248 = VfMiscExReleaseResourceLite_Entry;
  v250 = "ExReleaseResourceForThreadLite";
  v252 = VfMiscExReleaseResourceForThreadLite_Entry;
  v254 = "KeSynchronizeExecution";
  v256 = VfMiscKeSynchronizeExecution_Entry;
  v258 = "KeReleaseInStackQueuedSpinLock";
  v260 = VfMiscKeReleaseInStackQueuedSpinLock_Entry;
  v262 = "KeReleaseMutant";
  v264 = VfMiscKeReleaseMutant_Entry;
  v266 = "KeInitializeSemaphore";
  v268 = VfMiscKeInitializeSemaphore_Entry;
  v219 = 228;
  v223 = 423;
  v225 = 0;
  v227 = 422;
  v229 = 0;
  v231 = 421;
  v233 = 0;
  v235 = 420;
  v237 = 0;
  v239 = 385;
  v241 = 0;
  v243 = 388;
  v245 = 0;
  v247 = 387;
  v249 = 0;
  v251 = 386;
  v253 = 0;
  v255 = 247;
  v257 = 0;
  v259 = 265;
  v261 = 0;
  v263 = 262;
  v265 = 0;
  v267 = 281;
  v269 = 0;
  v270 = "KeReleaseInStackQueuedSpinLockFromDpcLevel";
  v271 = 263;
  v272 = VfMiscKeReleaseInStackQueuedSpinLockFromDpcLevel_Entry;
  v273 = 0;
  v274 = "KeReleaseInStackQueuedSpinLockForDpc";
  v275 = 264;
  v276 = VfMiscKeReleaseInStackQueuedSpinLockFromDpcLevel_Entry;
  v277 = 0;
  v278 = "MmUnlockPages";
  v282 = "MmUnmapIoSpace";
  v279 = 212;
  v280 = 0;
  v281 = 0;
  v283 = 211;
  v284 = 0;
  v285 = 0;
  v0 = DifRegisterPlugin((__int64)&v6, 0x46u, 0xBu, (__int64)&ViMiscSetting);
  if ( v0 >= 0 )
  {
    v1 = VfAvlInitializeTree(ViLookasideAvl, 96, 0, ViRemLockDelayFreeAvlNode);
    v2 = &ViLookasideInitialized;
    if ( v1 < 0 )
      v2 = &ViLookasideAllocationFailures;
    _InterlockedExchange(v2, 1);
    v3 = VfAvlInitializeTree(&ViResourceAvl, 104, 0, ViRemLockDelayFreeAvlNode);
    v4 = &ViResourceInitialized;
    if ( v3 < 0 )
      v4 = &ViResourceNotTracked;
    _InterlockedExchange(v4, 1);
    if ( !(unsigned __int8)DifIsPluginRunningWithoutReboot() )
      VfCtxInit();
    VfSettingsApplyMiscellaneousChecks();
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140bdc060  push    rbp
0x140bdc062  push    rbx
0x140bdc063  push    rsi
0x140bdc064  push    rdi
0x140bdc065  lea     rbp, [rsp-7F8h]
0x140bdc06d  sub     rsp, 8F8h
0x140bdc074  mov     rax, cs:__security_cookie
0x140bdc07b  xor     rax, rsp
0x140bdc07e  mov     [rbp+810h+var_30], rax
0x140bdc085  xor     esi, esi
0x140bdc087  mov     [rsp+910h+var_8E8], 0EEh
0x140bdc08f  lea     rax, VfMiscPluginUnload
0x140bdc096  mov     [rsp+910h+var_8D8], rsi
0x140bdc09b  mov     cs:qword_140EF2048, rax
0x140bdc0a2  lea     rax, aMmallocatecont_2; "MmAllocateContiguousMemory"
0x140bdc0a9  mov     [rsp+910h+var_8F0], rax
0x140bdc0ae  lea     rax, VfMiscMmAllocateContiguousMemory_Entry
0x140bdc0b5  mov     [rsp+910h+var_8E0], rax
0x140bdc0ba  lea     rax, aMmallocatecont_1; "MmAllocateContiguousMemoryEx"
0x140bdc0c1  mov     [rsp+910h+var_8D0], rax
0x140bdc0c6  lea     rax, VfMiscMmAllocateContiguousMemoryEx_Entry
0x140bdc0cd  mov     [rsp+910h+var_8C0], rax
0x140bdc0d2  lea     rax, aKereleasequeue_0; "KeReleaseQueuedSpinLock"
0x140bdc0d9  mov     [rsp+910h+var_8B0], rax
0x140bdc0de  lea     rax, VfMiscKeReleaseQueuedSpinLock_Entry
0x140bdc0e5  mov     [rsp+910h+var_8A0], rax
0x140bdc0ea  lea     rax, aKeinitializeev_0; "KeInitializeEvent"
0x140bdc0f1  mov     [rbp+810h+var_890], rax
0x140bdc0f5  lea     rax, VfMiscKeInitializeEvent_Entry
0x140bdc0fc  mov     [rbp+810h+var_880], rax
0x140bdc100  lea     rax, aKeinitializemu_1; "KeInitializeMutant"
0x140bdc107  mov     [rbp+810h+var_870], rax
0x140bdc10b  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bdc112  mov     [rbp+810h+var_860], rax
0x140bdc116  lea     rax, aKeinitializemu_2; "KeInitializeMutex"
0x140bdc11d  mov     [rbp+810h+var_850], rax
0x140bdc121  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bdc128  mov     [rbp+810h+var_840], rax
0x140bdc12c  lea     rax, aKeinitializeti_1; "KeInitializeTimerEx"
0x140bdc133  mov     [rbp+810h+var_830], rax
0x140bdc137  lea     rax, VfMiscKeInitializeTimerEx_Entry
0x140bdc13e  mov     [rbp+810h+var_820], rax
0x140bdc142  lea     rax, aKewaitforsingl; "KeWaitForSingleObject"
0x140bdc149  mov     [rbp+810h+var_810], rax
0x140bdc14d  lea     rax, VfMiscKeWaitForSingleObject_Entry
0x140bdc154  mov     [rbp+810h+var_800], rax
0x140bdc158  lea     rax, aKewaitformulti; "KeWaitForMultipleObjects"
0x140bdc15f  mov     [rbp+810h+var_7F0], rax
0x140bdc163  lea     rax, VfMiscKeWaitForMultipleObjects_Entry
0x140bdc16a  mov     [rbp+810h+var_7E0], rax
0x140bdc16e  lea     rax, aExinitializelo_0; "ExInitializeLookasideListEx"
0x140bdc175  mov     [rbp+810h+var_7D0], rax
0x140bdc179  lea     rax, VfMiscExInitializeLookasideListEx_Entry
0x140bdc180  mov     [rbp+810h+var_7C0], rax
0x140bdc184  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc18b  mov     [rbp+810h+var_7B8], rax
0x140bdc18f  lea     rax, aExinitializenp; "ExInitializeNPagedLookasideList"
0x140bdc196  mov     [rbp+810h+var_7B0], rax
0x140bdc19a  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bdc1a1  mov     [rbp+810h+var_7A0], rax
0x140bdc1a5  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc1ac  mov     [rbp+810h+var_798], rax
0x140bdc1b0  lea     rax, aExinitializepa_0; "ExInitializePagedLookasideList"
0x140bdc1b7  mov     [rbp+810h+var_790], rax
0x140bdc1be  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bdc1c5  mov     [rbp+810h+var_780], rax
0x140bdc1cc  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc1d3  mov     [rbp+810h+var_778], rax
0x140bdc1da  lea     rax, aExdeletepagedl_0; "ExDeletePagedLookasideList"
0x140bdc1e1  mov     [rbp+810h+var_770], rax
0x140bdc1e8  mov     [rsp+910h+var_8C8], 0EDh
0x140bdc1f0  mov     [rsp+910h+var_8B8], rsi
0x140bdc1f5  mov     [rsp+910h+var_8A8], 104h
0x140bdc1fd  mov     [rsp+910h+var_898], rsi
0x140bdc202  mov     [rbp+810h+var_888], 11Ch
0x140bdc209  mov     [rbp+810h+var_878], rsi
0x140bdc20d  mov     [rbp+810h+var_868], 11Bh
0x140bdc214  mov     [rbp+810h+var_858], rsi
0x140bdc218  mov     [rbp+810h+var_848], 11Ah
0x140bdc21f  mov     [rbp+810h+var_838], rsi
0x140bdc223  mov     [rbp+810h+var_828], 117h
0x140bdc22a  mov     [rbp+810h+var_818], rsi
0x140bdc22e  mov     [rbp+810h+var_808], 0F0h
0x140bdc235  mov     [rbp+810h+var_7F8], rsi
0x140bdc239  mov     [rbp+810h+var_7E8], 0F1h
0x140bdc240  mov     [rbp+810h+var_7D8], rsi
0x140bdc244  mov     [rbp+810h+var_7C8], 18Fh
0x140bdc24b  mov     [rbp+810h+var_7A8], 18Eh
0x140bdc252  mov     [rbp+810h+var_788], 18Dh
0x140bdc25c  mov     [rbp+810h+var_768], 198h
0x140bdc266  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc26d  mov     [rbp+810h+var_758], rsi
0x140bdc274  mov     [rbp+810h+var_760], rax
0x140bdc27b  lea     rax, aExdeletenpaged_0; "ExDeleteNPagedLookasideList"
0x140bdc282  mov     [rbp+810h+var_750], rax
0x140bdc289  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc290  mov     [rbp+810h+var_740], rax
0x140bdc297  lea     rax, aExdeletelookas_0; "ExDeleteLookasideListEx"
0x140bdc29e  mov     [rbp+810h+var_730], rax
0x140bdc2a5  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc2ac  mov     [rbp+810h+var_720], rax
0x140bdc2b3  lea     rax, aObreferenceobj_5; "ObReferenceObjectByPointer"
0x140bdc2ba  mov     [rbp+810h+var_710], rax
0x140bdc2c1  lea     rax, VfMiscObReferenceObjectByPointer_Entry
0x140bdc2c8  mov     [rbp+810h+var_700], rax
0x140bdc2cf  lea     rax, aObreferenceobj_1; "ObReferenceObjectByHandle"
0x140bdc2d6  mov     [rbp+810h+var_6F0], rax
0x140bdc2dd  lea     rax, VfMiscObReferenceObjectByHandle_Exit
0x140bdc2e4  mov     [rbp+810h+var_6D8], rax
0x140bdc2eb  lea     rax, aObfreferenceob_0; "ObfReferenceObject"
0x140bdc2f2  mov     [rbp+810h+var_6D0], rax
0x140bdc2f9  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc300  mov     [rbp+810h+var_6C0], rax
0x140bdc307  lea     rax, VfMiscObfReferenceObject_Exit
0x140bdc30e  mov     [rbp+810h+var_6B8], rax
0x140bdc315  lea     rax, aObfreferenceob; "ObfReferenceObjectWithTag"
0x140bdc31c  mov     [rbp+810h+var_6B0], rax
0x140bdc323  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bdc32a  mov     [rbp+810h+var_6A0], rax
0x140bdc331  lea     rax, aObfdereference_0; "ObfDereferenceObject"
0x140bdc338  mov     [rbp+810h+var_690], rax
0x140bdc33f  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc346  mov     [rbp+810h+var_680], rax
0x140bdc34d  lea     rax, aObfdereference_2; "ObfDereferenceObjectWithTag"
0x140bdc354  mov     [rbp+810h+var_670], rax
0x140bdc35b  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bdc362  mov     [rbp+810h+var_660], rax
0x140bdc369  lea     rax, aObgetobjectsec_0; "ObGetObjectSecurity"
0x140bdc370  mov     [rbp+810h+var_650], rax
0x140bdc377  lea     rax, VfMiscObGetObjectSecurity_Entry
0x140bdc37e  mov     [rbp+810h+var_640], rax
0x140bdc385  lea     rax, aObreferenceobj; "ObReferenceObjectByPointerWithTag"
0x140bdc38c  mov     [rbp+810h+var_630], rax
0x140bdc393  lea     rax, VfMiscObReferenceObjectByPointerWithTag_Entry
0x140bdc39a  mov     [rbp+810h+var_620], rax
0x140bdc3a1  lea     rax, aKereleasespinl_1; "KeReleaseSpinLock"
0x140bdc3a8  mov     [rbp+810h+var_610], rax
0x140bdc3af  lea     rax, VfMiscKeReleaseSpinLock_Entry
0x140bdc3b6  mov     [rbp+810h+var_600], rax
0x140bdc3bd  lea     rax, aKeacquirespinl_4; "KeAcquireSpinLockAtDpcLevel"
0x140bdc3c4  mov     [rbp+810h+var_5F0], rax
0x140bdc3cb  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc3d2  mov     [rbp+810h+var_5E0], rax
0x140bdc3d9  lea     rax, aKereleasespinl_2; "KeReleaseSpinLockFromDpcLevel"
0x140bdc3e0  mov     [rbp+810h+var_5D0], rax
0x140bdc3e7  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc3ee  mov     [rbp+810h+var_5C0], rax
0x140bdc3f5  mov     [rbp+810h+var_748], 199h
0x140bdc3ff  mov     [rbp+810h+var_738], rsi
0x140bdc406  mov     [rbp+810h+var_728], 19Ah
0x140bdc410  mov     [rbp+810h+var_718], rsi
0x140bdc417  mov     [rbp+810h+var_708], 0C9h
0x140bdc421  mov     [rbp+810h+var_6F8], rsi
0x140bdc428  mov     [rbp+810h+var_6E8], 0CAh
0x140bdc432  mov     [rbp+810h+var_6E0], rsi
0x140bdc439  mov     [rbp+810h+var_6C8], 0C4h
0x140bdc443  mov     [rbp+810h+var_6A8], 0C3h
0x140bdc44d  mov     [rbp+810h+var_698], rsi
0x140bdc454  mov     [rbp+810h+var_688], 0C6h
0x140bdc45e  mov     [rbp+810h+var_678], rsi
0x140bdc465  mov     [rbp+810h+var_668], 0C5h
0x140bdc46f  mov     [rbp+810h+var_658], rsi
0x140bdc476  mov     [rbp+810h+var_648], 0CBh
0x140bdc480  mov     [rbp+810h+var_638], rsi
0x140bdc487  mov     [rbp+810h+var_628], 0C8h
0x140bdc491  mov     [rbp+810h+var_618], rsi
0x140bdc498  mov     [rbp+810h+var_608], 103h
0x140bdc4a2  mov     [rbp+810h+var_5F8], rsi
0x140bdc4a9  mov     [rbp+810h+var_5E8], 125h
0x140bdc4b3  mov     [rbp+810h+var_5D8], rsi
0x140bdc4ba  mov     [rbp+810h+var_5C8], 102h
0x140bdc4c4  lea     rax, aKeacquirespinl_2; "KeAcquireSpinLockRaiseToDpc"
0x140bdc4cb  mov     [rbp+810h+var_5B8], rsi
0x140bdc4d2  mov     [rbp+810h+var_5B0], rax
0x140bdc4d9  lea     rax, VfMiscKeAcquireSpinLockRaiseToDpc_Entry
0x140bdc4e0  mov     [rbp+810h+var_5A0], rax
0x140bdc4e7  lea     rax, aIoconnectinter; "IoConnectInterrupt"
0x140bdc4ee  mov     [rbp+810h+var_590], rax
0x140bdc4f5  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc4fc  mov     [rbp+810h+var_580], rax
0x140bdc503  lea     rax, aIodisconnectin_1; "IoDisconnectInterrupt"
0x140bdc50a  mov     [rbp+810h+var_570], rax
0x140bdc511  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc518  mov     [rbp+810h+var_560], rax
0x140bdc51f  lea     rax, aIoconnectinter_2; "IoConnectInterruptEx"
0x140bdc526  mov     [rbp+810h+var_550], rax
0x140bdc52d  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc534  mov     [rbp+810h+var_540], rax
0x140bdc53b  lea     rax, aIodisconnectin_0; "IoDisconnectInterruptEx"
0x140bdc542  mov     [rbp+810h+var_530], rax
0x140bdc549  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc550  mov     [rbp+810h+var_520], rax
0x140bdc557  lea     rax, aKereleasemutex_0; "KeReleaseMutex"
0x140bdc55e  mov     [rbp+810h+var_510], rax
0x140bdc565  lea     rax, VfMiscKeReleaseMutant_Entry
0x140bdc56c  mov     [rbp+810h+var_500], rax
0x140bdc573  lea     rax, aKeinsertqueued; "KeInsertQueueDpc"
0x140bdc57a  mov     [rbp+810h+var_4F0], rax
0x140bdc581  lea     rax, VfMiscKeInsertQueueDpc_Entry
0x140bdc588  mov     [rbp+810h+var_4E0], rax
0x140bdc58f  lea     rax, aKeremovequeued; "KeRemoveQueueDpc"
0x140bdc596  mov     [rbp+810h+var_4D0], rax
0x140bdc59d  lea     rax, VfMiscKeRemoveQueueDpc_Entry
0x140bdc5a4  mov     [rbp+810h+var_4C0], rax
0x140bdc5ab  lea     rax, aKetrytoacquire_5; "KeTryToAcquireSpinLockAtDpcLevel"
0x140bdc5b2  mov     [rbp+810h+var_4B0], rax
0x140bdc5b9  lea     rax, VfMiscKeTryToAcquireSpinLockAtDpcLevel_Entry
0x140bdc5c0  mov     [rbp+810h+var_4A0], rax
0x140bdc5c7  lea     rax, aKetrytoacquire_4; "KeTryToAcquireInStackQueuedSpinLockAtDp"...
0x140bdc5ce  mov     [rbp+810h+var_490], rax
0x140bdc5d5  lea     rax, VfMiscKeTryToAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bdc5dc  mov     [rbp+810h+var_480], rax
0x140bdc5e3  lea     rax, aKeacquireinsta_6; "KeAcquireInStackQueuedSpinLockAtDpcLeve"...
0x140bdc5ea  mov     [rbp+810h+var_470], rax
0x140bdc5f1  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bdc5f8  mov     [rbp+810h+var_460], rax
0x140bdc5ff  lea     rax, aKeacquireinsta_5; "KeAcquireInStackQueuedSpinLockForDpc"
0x140bdc606  mov     [rbp+810h+var_450], rax
0x140bdc60d  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockForDpc_Entry
0x140bdc614  mov     [rbp+810h+var_440], rax
0x140bdc61b  lea     rax, aKesetevent_0; "KeSetEvent"
0x140bdc622  mov     [rbp+810h+var_430], rax
0x140bdc629  lea     rax, VfMiscKeSetEvent_Entry
0x140bdc630  mov     [rbp+810h+var_420], rax
0x140bdc637  lea     rax, aIofreemdl_0; "IoFreeMdl"
0x140bdc63e  mov     [rbp+810h+var_410], rax
0x140bdc645  mov     [rbp+810h+var_5A8], 124h
0x140bdc64f  mov     [rbp+810h+var_598], rsi
0x140bdc656  mov     [rbp+810h+var_588], 166h
0x140bdc660  mov     [rbp+810h+var_578], rsi
0x140bdc667  mov     [rbp+810h+var_568], 157h
0x140bdc671  mov     [rbp+810h+var_558], rsi
0x140bdc678  mov     [rbp+810h+var_548], 165h
0x140bdc682  mov     [rbp+810h+var_538], rsi
0x140bdc689  mov     [rbp+810h+var_528], 156h
0x140bdc693  mov     [rbp+810h+var_518], rsi
0x140bdc69a  mov     [rbp+810h+var_508], 105h
0x140bdc6a4  mov     [rbp+810h+var_4F8], rsi
0x140bdc6ab  mov     [rbp+810h+var_4E8], 114h
0x140bdc6b5  mov     [rbp+810h+var_4D8], rsi
0x140bdc6bc  mov     [rbp+810h+var_4C8], 0FEh
0x140bdc6c6  mov     [rbp+810h+var_4B8], rsi
0x140bdc6cd  mov     [rbp+810h+var_4A8], 0F2h
0x140bdc6d7  mov     [rbp+810h+var_498], rsi
0x140bdc6de  mov     [rbp+810h+var_488], 0F5h
0x140bdc6e8  mov     [rbp+810h+var_478], rsi
0x140bdc6ef  mov     [rbp+810h+var_468], 12Ah
0x140bdc6f9  mov     [rbp+810h+var_458], rsi
0x140bdc700  mov     [rbp+810h+var_448], 129h
0x140bdc70a  mov     [rbp+810h+var_438], rsi
0x140bdc711  mov     [rbp+810h+var_428], 0FAh
0x140bdc71b  mov     [rbp+810h+var_418], rsi
0x140bdc722  lea     rax, VfMiscIoFreeMdl_Entry
0x140bdc729  mov     [rbp+810h+var_408], 153h
0x140bdc733  mov     [rbp+810h+var_400], rax
0x140bdc73a  lea     rax, aIoinitializewo; "IoInitializeWorkItem"
0x140bdc741  mov     [rbp+810h+var_3F0], rax
0x140bdc748  lea     rax, VfMiscIoInitializeWorkItem_Entry
0x140bdc74f  mov     [rbp+810h+var_3E0], rax
0x140bdc756  lea     rax, aExinitializere_0; "ExInitializeResourceLite"
0x140bdc75d  mov     [rbp+810h+var_3D0], rax
0x140bdc764  lea     rax, VfMiscExInitializeResourceLite_Entry
0x140bdc76b  mov     [rbp+810h+var_3C0], rax
0x140bdc772  lea     rax, VfMiscExInitializeResourceLite_Exit
0x140bdc779  mov     [rbp+810h+var_3B8], rax
0x140bdc780  lea     rax, aExdeleteresour; "ExDeleteResourceLite"
0x140bdc787  mov     [rbp+810h+var_3B0], rax
0x140bdc78e  lea     rax, VfMiscExDeleteResourceLite_Entry
0x140bdc795  mov     [rbp+810h+var_3A0], rax
0x140bdc79c  lea     rax, VfMiscExDeleteResourceLite_Exit
0x140bdc7a3  mov     [rbp+810h+var_398], rax
0x140bdc7aa  lea     rax, aExreleasefastm_1; "ExReleaseFastMutex"
0x140bdc7b1  mov     [rbp+810h+var_390], rax
0x140bdc7b8  lea     rax, VfMiscExReleaseFastMutex_Entry
0x140bdc7bf  mov     [rbp+810h+var_380], rax
0x140bdc7c6  lea     rax, aExacquirefastm; "ExAcquireFastMutexUnsafe"
0x140bdc7cd  mov     [rbp+810h+var_370], rax
0x140bdc7d4  lea     rax, VfMiscExAcquireFastMutexUnsafe_Entry
0x140bdc7db  mov     [rbp+810h+var_360], rax
0x140bdc7e2  lea     rax, aExreleasefastm_0; "ExReleaseFastMutexUnsafe"
0x140bdc7e9  mov     [rbp+810h+var_350], rax
0x140bdc7f0  lea     rax, VfMiscExReleaseFastMutexUnsafe_Entry
0x140bdc7f7  mov     [rbp+810h+var_340], rax
0x140bdc7fe  lea     rax, aExfacquirepush; "ExfAcquirePushLockExclusive"
0x140bdc805  mov     [rbp+810h+var_330], rax
0x140bdc80c  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc813  mov     [rbp+810h+var_320], rax
0x140bdc81a  lea     rax, aExfacquirepush_1; "ExfAcquirePushLockShared"
0x140bdc821  mov     [rbp+810h+var_310], rax
0x140bdc828  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc82f  mov     [rbp+810h+var_300], rax
0x140bdc836  lea     rax, aExftryacquirep_0; "ExfTryAcquirePushLockShared"
0x140bdc83d  mov     [rbp+810h+var_2F0], rax
0x140bdc844  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc84b  mov     [rbp+810h+var_2E0], rax
0x140bdc852  lea     rax, aExfreleasepush_1; "ExfReleasePushLock"
0x140bdc859  mov     [rbp+810h+var_2D0], rax
0x140bdc860  lea     rax, VfMiscExfReleasePushLockShared_Entry
0x140bdc867  mov     [rbp+810h+var_2C0], rax
0x140bdc86e  lea     rax, aExftrytowakepu; "ExfTryToWakePushLock"
  ... truncated ...
```
