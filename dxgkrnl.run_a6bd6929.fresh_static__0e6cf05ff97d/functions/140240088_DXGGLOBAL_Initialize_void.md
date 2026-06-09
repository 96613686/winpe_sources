# DXGGLOBAL::Initialize(void)

- ea: `0x140240088`
- end: `0x140241567`
- name: `?Initialize@DXGGLOBAL@@QEAAJXZ`
- size: `5343`
- prototype: `__int64 __fastcall(DXGGLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14023ec74`

## callees

- `0x1400091f0`
- `0x14001b9c0`
- `0x14002e2e0`
- `0x140070c5c`
- `0x1400752ac`
- `0x14007d544`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140219d18`
- `0x14023ed70`
- `0x140240088`
- `0x140241570`
- `0x140242720`
- `0x14024648c`
- `0x14024a454`
- `0x140259fa0`
- `0x140266a34`
- `0x1403b6104`
- `0x1403f9ee8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140241313`
- `ntoskrnl!KeInitializeSpinLock` at `0x14024143c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140241313`
- `ntoskrnl!KeInitializeSpinLock` at `0x14024143c`
- `ntoskrnl!KeInitializeTimer` at `0x14024133a`
- `ntoskrnl!KeInitializeTimer` at `0x14024133a`
- `ntoskrnl!KeInitializeDpc` at `0x140241357`
- `ntoskrnl!KeInitializeDpc` at `0x140241357`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140240c35`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140240c35`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402403b1`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402403b1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140240211`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1402402b4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140240414`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14024047b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140240211`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1402402b4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140240414`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14024047b`
- `ntoskrnl!ZwPowerInformation` at `0x14024137a`
- `ntoskrnl!ZwPowerInformation` at `0x14024137a`
- `ntoskrnl!PsInitialSystemProcess` at `0x140241212`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1402400e5`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1402401af`
- `ntoskrnl!MmMapViewOfSection` at `0x140240177`
- `ntoskrnl!MmMapViewOfSection` at `0x1402401d9`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140240185`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1402401e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140240193`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402401f5`
- `ntoskrnl!RtlInitializeBitMap` at `0x140241176`
- `ntoskrnl!RtlInitializeBitMap` at `0x14024119e`
- `ntoskrnl!RtlInitializeBitMap` at `0x140241176`
- `ntoskrnl!RtlInitializeBitMap` at `0x14024119e`
- `ntoskrnl!ZwAllocateVirtualMemoryEx` at `0x14024015b`
- `ntoskrnl!ZwAllocateVirtualMemoryEx` at `0x1402401bd`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140240169`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1402401cb`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402401a1`
- `ntoskrnl!MmUnmapLockedPages` at `0x140240203`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14024146c`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1402414da`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14024146c`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1402414da`
- `watchdog!WdLogSingleEntry2` at `0x14024022e`
- `watchdog!WdLogSingleEntry2` at `0x1402402d2`
- `watchdog!WdLogSingleEntry2` at `0x140240396`
- `watchdog!WdLogSingleEntry2` at `0x1402403cf`
- `watchdog!WdLogSingleEntry2` at `0x14024022e`
- `watchdog!WdLogSingleEntry2` at `0x1402402d2`
- `watchdog!WdLogSingleEntry2` at `0x140240396`
- `watchdog!WdLogSingleEntry2` at `0x1402403cf`
- `watchdog!WdLogSingleEntry3` at `0x140240434`
- `watchdog!WdLogSingleEntry3` at `0x14024049b`
- `watchdog!WdLogSingleEntry3` at `0x140240434`
- `watchdog!WdLogSingleEntry3` at `0x14024049b`
- `watchdog!WdLogSingleEntry0` at `0x1402410a1`
- `watchdog!WdLogSingleEntry0` at `0x140241129`
- `watchdog!WdLogSingleEntry0` at `0x1402411cf`
- `watchdog!WdLogSingleEntry0` at `0x140241221`
- `watchdog!WdLogSingleEntry0` at `0x1402412d0`
- `watchdog!WdLogSingleEntry0` at `0x1402410a1`
- `watchdog!WdLogSingleEntry0` at `0x140241129`
- `watchdog!WdLogSingleEntry0` at `0x1402411cf`
- `watchdog!WdLogSingleEntry0` at `0x140241221`
- `watchdog!WdLogSingleEntry0` at `0x1402412d0`
- `watchdog!WdLogSingleEntry1` at `0x140240317`
- `watchdog!WdLogSingleEntry1` at `0x140240ea2`
- `watchdog!WdLogSingleEntry1` at `0x140240fe3`
- `watchdog!WdLogSingleEntry1` at `0x14024102e`
- `watchdog!WdLogSingleEntry1` at `0x140241395`
- `watchdog!WdLogSingleEntry1` at `0x140241487`
- `watchdog!WdLogSingleEntry1` at `0x1402414f5`
- `watchdog!WdLogSingleEntry1` at `0x140240317`
- `watchdog!WdLogSingleEntry1` at `0x140240ea2`
- `watchdog!WdLogSingleEntry1` at `0x140240fe3`
- `watchdog!WdLogSingleEntry1` at `0x14024102e`
- `watchdog!WdLogSingleEntry1` at `0x140241395`
- `watchdog!WdLogSingleEntry1` at `0x140241487`
- `watchdog!WdLogSingleEntry1` at `0x1402414f5`

## string_xrefs

- `0x14024023a`: `DXGGlobal 0x%I64x: Unable to initialize the lookaside list for lock order tracker, returning 0x%I64x`
- `0x140240d90`: `\REGISTRY\MACHINE\System\ControlSet001\Control\Terminal Server\WinStations`
- `0x1402412e1`: `Failed to Qdc cache.`
- `0x140241232`: `PsInitialSystemProcess == m_pSystemDxgProcess->GetEProcess()`

## pseudocode

```c
__int64 __fastcall DXGGLOBAL::Initialize(DXGGLOBAL *this)
{
  __int64 v1; // rdi
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  NTSTATUS v6; // eax
  __int64 v7; // r14
  const wchar_t *v8; // r9
  NTSTATUS v10; // eax
  struct _ERESOURCE *v11; // rax
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  unsigned __int8 v16; // r9
  int v17; // ecx
  int v18; // r8d
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int DxgkSharedObjectTypes; // eax
  unsigned int v23; // ecx
  unsigned int v24; // edx
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  DXGSESSIONMGR *v30; // rax
  DXGSESSIONMGR *v31; // rax
  int v32; // ecx
  __int64 v33; // rbx
  __int64 v34; // rax
  ULONG *v35; // rax
  __int64 v36; // rax
  _BYTE *v37; // rbx
  NTSTATUS v38; // eax
  __int64 v39; // rbx
  NTSTATUS v40; // eax
  NTSTATUS v41; // eax
  __int64 v42; // rdi
  char OutputBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v45; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v49; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v51; // [rsp+70h] [rbp-90h] BYREF
  int v52; // [rsp+74h] [rbp-8Ch] BYREF
  int v53; // [rsp+78h] [rbp-88h] BYREF
  int v54; // [rsp+7Ch] [rbp-84h] BYREF
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch] BYREF
  int v57; // [rsp+88h] [rbp-78h] BYREF
  int v58; // [rsp+8Ch] [rbp-74h] BYREF
  int v59; // [rsp+90h] [rbp-70h] BYREF
  int v60; // [rsp+94h] [rbp-6Ch] BYREF
  int v61; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+9Ch] [rbp-64h] BYREF
  int v63; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v64; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v65; // [rsp+A8h] [rbp-58h] BYREF
  int v66; // [rsp+ACh] [rbp-54h] BYREF
  int v67; // [rsp+B0h] [rbp-50h] BYREF
  int v68; // [rsp+B4h] [rbp-4Ch] BYREF
  int v69; // [rsp+B8h] [rbp-48h] BYREF
  int v70; // [rsp+BCh] [rbp-44h] BYREF
  int v71; // [rsp+C0h] [rbp-40h] BYREF
  int v72; // [rsp+C4h] [rbp-3Ch] BYREF
  int v73; // [rsp+C8h] [rbp-38h] BYREF
  int v74; // [rsp+CCh] [rbp-34h] BYREF
  int v75; // [rsp+D0h] [rbp-30h] BYREF
  int v76; // [rsp+D4h] [rbp-2Ch] BYREF
  int v77; // [rsp+D8h] [rbp-28h] BYREF
  int v78; // [rsp+DCh] [rbp-24h] BYREF
  int v79; // [rsp+E0h] [rbp-20h] BYREF
  int v80; // [rsp+E4h] [rbp-1Ch] BYREF
  struct _UNICODE_STRING v81; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v82; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v83; // [rsp+108h] [rbp+8h] BYREF
  __int64 v84; // [rsp+110h] [rbp+10h] BYREF
  int v85; // [rsp+118h] [rbp+18h]
  const wchar_t *v86; // [rsp+120h] [rbp+20h]
  unsigned int *v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+130h] [rbp+30h]
  __int64 *v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+140h] [rbp+40h]
  __int64 v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+150h] [rbp+50h]
  const wchar_t *v93; // [rsp+158h] [rbp+58h]
  int *v94; // [rsp+160h] [rbp+60h]
  int v95; // [rsp+168h] [rbp+68h]
  int *v96; // [rsp+170h] [rbp+70h]
  int v97; // [rsp+178h] [rbp+78h]
  __int64 v98; // [rsp+180h] [rbp+80h]
  int v99; // [rsp+188h] [rbp+88h]
  const wchar_t *v100; // [rsp+190h] [rbp+90h]
  unsigned int *v101; // [rsp+198h] [rbp+98h]
  int v102; // [rsp+1A0h] [rbp+A0h]
  int *v103; // [rsp+1A8h] [rbp+A8h]
  int v104; // [rsp+1B0h] [rbp+B0h]
  __int64 v105; // [rsp+1B8h] [rbp+B8h]
  int v106; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v107; // [rsp+1C8h] [rbp+C8h]
  unsigned int *v108; // [rsp+1D0h] [rbp+D0h]
  int v109; // [rsp+1D8h] [rbp+D8h]
  int *v110; // [rsp+1E0h] [rbp+E0h]
  int v111; // [rsp+1E8h] [rbp+E8h]
  __int64 v112; // [rsp+1F0h] [rbp+F0h]
  int v113; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v114; // [rsp+200h] [rbp+100h]
  int *v115; // [rsp+208h] [rbp+108h]
  int v116; // [rsp+210h] [rbp+110h]
  int *v117; // [rsp+218h] [rbp+118h]
  int v118; // [rsp+220h] [rbp+120h]
  __int64 v119; // [rsp+228h] [rbp+128h]
  int v120; // [rsp+230h] [rbp+130h]
  const wchar_t *v121; // [rsp+238h] [rbp+138h]
  int *v122; // [rsp+240h] [rbp+140h]
  int v123; // [rsp+248h] [rbp+148h]
  int *v124; // [rsp+250h] [rbp+150h]
  int v125; // [rsp+258h] [rbp+158h]
  __int64 v126; // [rsp+260h] [rbp+160h]
  int v127; // [rsp+268h] [rbp+168h]
  const wchar_t *v128; // [rsp+270h] [rbp+170h]
  int *v129; // [rsp+278h] [rbp+178h]
  int v130; // [rsp+280h] [rbp+180h]
  int *v131; // [rsp+288h] [rbp+188h]
  int v132; // [rsp+290h] [rbp+190h]
  __int64 v133; // [rsp+298h] [rbp+198h]
  int v134; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v135; // [rsp+2A8h] [rbp+1A8h]
  int *v136; // [rsp+2B0h] [rbp+1B0h]
  int v137; // [rsp+2B8h] [rbp+1B8h]
  int *v138; // [rsp+2C0h] [rbp+1C0h]
  int v139; // [rsp+2C8h] [rbp+1C8h]
  __int64 v140; // [rsp+2D0h] [rbp+1D0h]
  int v141; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v142; // [rsp+2E0h] [rbp+1E0h]
  int *v143; // [rsp+2E8h] [rbp+1E8h]
  int v144; // [rsp+2F0h] [rbp+1F0h]
  int *v145; // [rsp+2F8h] [rbp+1F8h]
  int v146; // [rsp+300h] [rbp+200h]
  __int64 v147; // [rsp+308h] [rbp+208h]
  int v148; // [rsp+310h] [rbp+210h]
  const wchar_t *v149; // [rsp+318h] [rbp+218h]
  int *v150; // [rsp+320h] [rbp+220h]
  int v151; // [rsp+328h] [rbp+228h]
  int *v152; // [rsp+330h] [rbp+230h]
  int v153; // [rsp+338h] [rbp+238h]
  __int64 v154; // [rsp+340h] [rbp+240h]
  int v155; // [rsp+348h] [rbp+248h]
  const wchar_t *v156; // [rsp+350h] [rbp+250h]
  unsigned int *v157; // [rsp+358h] [rbp+258h]
  int v158; // [rsp+360h] [rbp+260h]
  int *v159; // [rsp+368h] [rbp+268h]
  int v160; // [rsp+370h] [rbp+270h]
  __int64 v161; // [rsp+378h] [rbp+278h]
  int v162; // [rsp+380h] [rbp+280h]
  const wchar_t *v163; // [rsp+388h] [rbp+288h]
  unsigned int *v164; // [rsp+390h] [rbp+290h]
  int v165; // [rsp+398h] [rbp+298h]
  unsigned int *v166; // [rsp+3A0h] [rbp+2A0h]
  int v167; // [rsp+3A8h] [rbp+2A8h]
  __int64 v168; // [rsp+3B0h] [rbp+2B0h]
  int v169; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v170; // [rsp+3C0h] [rbp+2C0h]
  unsigned int *v171; // [rsp+3C8h] [rbp+2C8h]
  int v172; // [rsp+3D0h] [rbp+2D0h]
  int *v173; // [rsp+3D8h] [rbp+2D8h]
  int v174; // [rsp+3E0h] [rbp+2E0h]
  __int64 v175; // [rsp+3E8h] [rbp+2E8h]
  int v176; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v177; // [rsp+3F8h] [rbp+2F8h]
  unsigned int *v178; // [rsp+400h] [rbp+300h]
  int v179; // [rsp+408h] [rbp+308h]
  int *v180; // [rsp+410h] [rbp+310h]
  int v181; // [rsp+418h] [rbp+318h]
  __int64 v182; // [rsp+420h] [rbp+320h]
  int v183; // [rsp+428h] [rbp+328h]
  const wchar_t *v184; // [rsp+430h] [rbp+330h]
  unsigned int *v185; // [rsp+438h] [rbp+338h]
  int v186; // [rsp+440h] [rbp+340h]
  int *v187; // [rsp+448h] [rbp+348h]
  int v188; // [rsp+450h] [rbp+350h]
  __int64 v189; // [rsp+458h] [rbp+358h]
  int v190; // [rsp+460h] [rbp+360h]
  const wchar_t *v191; // [rsp+468h] [rbp+368h]
  int *v192; // [rsp+470h] [rbp+370h]
  int v193; // [rsp+478h] [rbp+378h]
  int *v194; // [rsp+480h] [rbp+380h]
  int v195; // [rsp+488h] [rbp+388h]
  __int64 v196; // [rsp+490h] [rbp+390h]
  int v197; // [rsp+498h] [rbp+398h]
  const wchar_t *v198; // [rsp+4A0h] [rbp+3A0h]
  int *v199; // [rsp+4A8h] [rbp+3A8h]
  int v200; // [rsp+4B0h] [rbp+3B0h]
  int *v201; // [rsp+4B8h] [rbp+3B8h]
  int v202; // [rsp+4C0h] [rbp+3C0h]
  __int64 v203; // [rsp+4C8h] [rbp+3C8h]
  int v204; // [rsp+4D0h] [rbp+3D0h]
  const wchar_t *v205; // [rsp+4D8h] [rbp+3D8h]
  unsigned int *v206; // [rsp+4E0h] [rbp+3E0h]
  int v207; // [rsp+4E8h] [rbp+3E8h]
  __int64 v208; // [rsp+4F0h] [rbp+3F0h]
  int v209; // [rsp+4F8h] [rbp+3F8h]
  __int64 v210; // [rsp+500h] [rbp+400h]
  int v211; // [rsp+508h] [rbp+408h]
  const wchar_t *v212; // [rsp+510h] [rbp+410h]
  unsigned int *v213; // [rsp+518h] [rbp+418h]
  int v214; // [rsp+520h] [rbp+420h]
  __int64 v215; // [rsp+528h] [rbp+428h]
  int v216; // [rsp+530h] [rbp+430h]
  __int64 v217; // [rsp+538h] [rbp+438h]
  int v218; // [rsp+540h] [rbp+440h]
  const wchar_t *v219; // [rsp+548h] [rbp+448h]
  unsigned int *v220; // [rsp+550h] [rbp+450h]
  int v221; // [rsp+558h] [rbp+458h]
  __int64 v222; // [rsp+560h] [rbp+460h]
  int v223; // [rsp+568h] [rbp+468h]
  __int64 v224; // [rsp+570h] [rbp+470h]
  int v225; // [rsp+578h] [rbp+478h]
  const wchar_t *v226; // [rsp+580h] [rbp+480h]
  unsigned int *v227; // [rsp+588h] [rbp+488h]
  int v228; // [rsp+590h] [rbp+490h]
  __int64 v229; // [rsp+598h] [rbp+498h]
  int v230; // [rsp+5A0h] [rbp+4A0h]
  __int64 v231; // [rsp+5A8h] [rbp+4A8h]
  int v232; // [rsp+5B0h] [rbp+4B0h]
  const wchar_t *v233; // [rsp+5B8h] [rbp+4B8h]
  unsigned int *v234; // [rsp+5C0h] [rbp+4C0h]
  int v235; // [rsp+5C8h] [rbp+4C8h]
  __int64 v236; // [rsp+5D0h] [rbp+4D0h]
  int v237; // [rsp+5D8h] [rbp+4D8h]
  __int64 v238; // [rsp+5E0h] [rbp+4E0h]
  int v239; // [rsp+5E8h] [rbp+4E8h]
  const wchar_t *v240; // [rsp+5F0h] [rbp+4F0h]
  unsigned int *v241; // [rsp+5F8h] [rbp+4F8h]
  int v242; // [rsp+600h] [rbp+500h]
  __int64 v243; // [rsp+608h] [rbp+508h]
  int v244; // [rsp+610h] [rbp+510h]
  __int64 v245; // [rsp+618h] [rbp+518h]
  int v246; // [rsp+620h] [rbp+520h]
  const wchar_t *v247; // [rsp+628h] [rbp+528h]
  int *v248; // [rsp+630h] [rbp+530h]
  int v249; // [rsp+638h] [rbp+538h]
  __int64 v250; // [rsp+640h] [rbp+540h]
  int v251; // [rsp+648h] [rbp+548h]
  __int64 v252; // [rsp+650h] [rbp+550h]
  int v253; // [rsp+658h] [rbp+558h]
  const wchar_t *v254; // [rsp+660h] [rbp+560h]
  int *v255; // [rsp+668h] [rbp+568h]
  int v256; // [rsp+670h] [rbp+570h]
  __int64 v257; // [rsp+678h] [rbp+578h]
  int v258; // [rsp+680h] [rbp+580h]
  __int64 v259; // [rsp+688h] [rbp+588h]
  int v260; // [rsp+690h] [rbp+590h]
  const wchar_t *v261; // [rsp+698h] [rbp+598h]
  int *v262; // [rsp+6A0h] [rbp+5A0h]
  int v263; // [rsp+6A8h] [rbp+5A8h]
  __int64 v264; // [rsp+6B0h] [rbp+5B0h]
  int v265; // [rsp+6B8h] [rbp+5B8h]
  __int64 v266; // [rsp+6C0h] [rbp+5C0h]
  int v267; // [rsp+6C8h] [rbp+5C8h]
  __int64 v268; // [rsp+6D0h] [rbp+5D0h]
  __int128 v269; // [rsp+6D8h] [rbp+5D8h]
  __int128 v270; // [rsp+6E8h] [rbp+5E8h]
  _BYTE v271[96]; // [rsp+700h] [rbp+600h] BYREF
  __int128 v272; // [rsp+760h] [rbp+660h]
  __int128 v273; // [rsp+770h] [rbp+670h]
  _OWORD v274[2]; // [rsp+780h] [rbp+680h]
  _OWORD v275[2]; // [rsp+7A0h] [rbp+6A0h] BYREF
  wchar_t v276; // [rsp+7C0h] [rbp+6C0h]

  v1 = *(_QWORD *)&DXGGLOBAL::m_pGlobal;
  memset(v271, 0, 0x58u);
  v2 = *(_OWORD *)&v271[16];
  *(_OWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 64LL) = *(_OWORD *)v271;
  v3 = *(_OWORD *)&v271[32];
  *(_OWORD *)(v1 + 80) = v2;
  v4 = *(_OWORD *)&v271[48];
  *(_OWORD *)(v1 + 96) = v3;
  v5 = *(_OWORD *)&v271[64];
  *(_OWORD *)(v1 + 112) = v4;
  *(_QWORD *)&v4 = *(_QWORD *)&v271[80];
  *(_OWORD *)(v1 + 128) = v5;
  *(_QWORD *)(v1 + 144) = v4;
  g_WindowsSubsystem = ZwAllocateVirtualMemory;
  qword_140162C80 = ZwAllocateVirtualMemoryEx;
  qword_140162C88 = (__int64)ZwFreeVirtualMemory;
  qword_140162C90 = MmMapViewOfSection;
  qword_140162C98 = MmUnmapViewOfSection;
  qword_140162CA0 = (__int64)MmMapLockedPagesSpecifyCache;
  qword_140162CA8 = (__int64)MmUnmapLockedPages;
  g_WslSubsystem = ZwAllocateVirtualMemory;
  qword_140162C40 = ZwAllocateVirtualMemoryEx;
  qword_140162C48 = (__int64)ZwFreeVirtualMemory;
  qword_140162C50 = MmMapViewOfSection;
  qword_140162C58 = MmUnmapViewOfSection;
  qword_140162C60 = (__int64)MmMapLockedPagesSpecifyCache;
  qword_140162C68 = (__int64)MmUnmapLockedPages;
  v6 = ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v1 + 305456), 0, 0, (POOL_TYPE)512, 0, 0x10u, 0x4B677844u, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    WdLogSingleEntry2(2, v1, v6);
    v8 = L"DXGGlobal 0x%I64x: Unable to initialize the lookaside list for lock order tracker, returning 0x%I64x";
    WdLogGlobalForLineNumber = 1830;
LABEL_3:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v8, v1, v7, 0, 0, 0);
    return (unsigned int)v7;
  }
  *(_BYTE *)(v1 + 305440) = 1;
  v10 = ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v1 + 160), 0, 0, (POOL_TYPE)512, 0, 0xA0u, 0x576B7844u, 0);
  v7 = v10;
  if ( v10 < 0 )
  {
    WdLogSingleEntry2(2, v1, v10);
    v8 = L"DXGGlobal 0x%I64x: Unable to initialize m_VmBusPacketWorkItemList, returning 0x%I64x";
    WdLogGlobalForLineNumber = 1842;
    goto LABEL_3;
  }
  *(_BYTE *)(v1 + 1363) = 1;
  if ( !HMGRTABLE::ExpandTable((HMGRTABLE *)(v1 + 344)) )
  {
    WdLogSingleEntry1(6, -1073741801);
    WdLogGlobalForLineNumber = 1854;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed the initial shared resource handle table expansion, returning 0x%I64x",
      -1073741801,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v11 = (struct _ERESOURCE *)operator new(104, 1265072196, 64);
  *(_QWORD *)(v1 + 608) = v11;
  if ( !v11 )
  {
    WdLogSingleEntry2(3, v1, -1073741801);
    WdLogGlobalForLineNumber = 1867;
    return 3221225495LL;
  }
  v12 = ExInitializeResourceLite(v11);
  v13 = v12;
  if ( v12 < 0 )
  {
    WdLogSingleEntry2(3, v1, v12);
    WdLogGlobalForLineNumber = 1877;
    return v13;
  }
  v14 = ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v1 + 1152), 0, 0, PagedPool, 0, 0x5F8u, 0x4B677844u, 0);
  v13 = v14;
  if ( v14 < 0 )
  {
    WdLogSingleEntry3(3, v1, v14, 0);
    WdLogGlobalForLineNumber = 1886;
    return v13;
  }
  *(_BYTE *)(v1 + 1361) = 1;
  v15 = ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v1 + 1248), 0, 0, PagedPool, 0, 0x5E0u, 0x4B677844u, 0);
  v13 = v15;
  if ( v15 < 0 )
  {
    WdLogSingleEntry3(3, v1, v15, 0);
    WdLogGlobalForLineNumber = 1896;
    return v13;
  }
  v16 = g_bSkuSupportMultipleUsers;
  *(_BYTE *)(v1 + 1362) = 1;
  v83 = 0x4000000;
  v51 = 0;
  v67 = 0;
  v52 = 0;
  v68 = 1;
  v50 = 0;
  v69 = 32;
  v49 = 0;
  v54 = 0;
  v70 = 0;
  v71 = 0;
  v55 = 0;
  v56 = 0;
  v72 = 0;
  v73 = 0;
  v57 = 0;
  v74 = 0;
  v58 = 0;
  v75 = 0;
  v53 = 0;
  v61 = 0;
  v63 = 0;
  if ( v16 )
    v17 = g_IsInternalReleaseOrDbg != 0 ? 0x100000 : 0x80000;
  else
    v17 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x10000;
  v76 = v17;
  if ( v16 )
    v18 = g_IsInternalReleaseOrDbg != 0 ? 8 : 4;
  else
    v18 = 2;
  v65 = v18;
  if ( v16 )
    v19 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x10000;
  else
    v19 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x4000;
  v77 = v19;
  v45 = v19;
  v78 = 300;
  v47 = 300;
  v44 = v17;
  v66 = 1;
  v46 = v18;
  v48 = 1;
  v79 = 5000;
  v59 = 0;
  v80 = 15000;
  v60 = 0;
  v62 = *(_DWORD *)(v1 + 305944);
  v86 = L"TerminationListSizeLimit";
  v87 = &v51;
  v89 = &v83;
  v93 = L"ValidateWDDMCaps";
  v94 = &v52;
  v96 = &v67;
  v100 = L"WDDM2LockManagement";
  v101 = &v50;
  v103 = &v68;
  v107 = L"MaximumAdapterCount";
  v108 = &v49;
  v110 = &v69;
  v114 = L"InvestigationDebugParameter";
  v115 = &v54;
  v117 = &v70;
  v121 = L"EnableIgnoreWin32ProcessStatus";
  v122 = &v55;
  v124 = &v71;
  v128 = L"EnableHMDTestMode";
  v84 = 0;
  v85 = 288;
  v88 = 67108868;
  v90 = 4;
  v91 = 0;
  v92 = 288;
  v95 = 67108868;
  v97 = 4;
  v98 = 0;
  v99 = 288;
  v102 = 67108868;
  v104 = 4;
  v105 = 0;
  v106 = 288;
  v109 = 67108868;
  v111 = 4;
  v112 = 0;
  v113 = 288;
  v116 = 67108868;
  v118 = 4;
  v119 = 0;
  v120 = 288;
  v123 = 67108868;
  v125 = 4;
  v126 = 0;
  v127 = 288;
  v130 = 67108868;
  v129 = &v56;
  v131 = &v72;
  v135 = L"PreserveFirmwareMode";
  v136 = &v57;
  v138 = &v73;
  v142 = L"PreventFullscreenWireFormatChange";
  v143 = &v58;
  v145 = &v74;
  v149 = L"EnableFuzzing";
  v150 = &v53;
  v152 = &v75;
  v156 = L"InternalDiagnosticsBufferSize";
  v157 = &v44;
  v159 = &v76;
  v163 = L"InternalDiagnosticsBufferMultiplier";
  v164 = &v46;
  v166 = &v65;
  v170 = L"ExternalDiagnosticsBufferSize";
  v171 = &v45;
  v173 = &v77;
  v177 = L"ExternalDiagnosticsBufferMultiplier";
  v178 = &v48;
  v180 = &v66;
  v184 = L"DiagnosticsBufferExpansionTime";
  v132 = 4;
  v133 = 0;
  v134 = 288;
  v137 = 67108868;
  v139 = 4;
  v140 = 0;
  v141 = 288;
  v144 = 67108868;
  v146 = 4;
  v147 = 0;
  v148 = 288;
  v151 = 67108868;
  v153 = 4;
  v154 = 0;
  v155 = 288;
  v158 = 67108868;
  v160 = 4;
  v161 = 0;
  v162 = 288;
  v165 = 67108868;
  v167 = 4;
  v168 = 0;
  v169 = 288;
  v172 = 67108868;
  v174 = 4;
  v175 = 0;
  v176 = 288;
  v179 = 67108868;
  v181 = 4;
  v182 = 0;
  v183 = 288;
  v185 = &v47;
  v187 = &v78;
  v191 = L"RapidHpdTimeoutInMilliseconds";
  v192 = &v59;
  v194 = &v79;
  v198 = L"RapidHpdMaxChainInMilliseconds";
  v199 = &v60;
  v201 = &v80;
  v205 = L"ForceUsb4MonitorSupport";
  v206 = &g_bDbgForceUsb4MonitorSupport;
  v212 = L"Usb4MonitorTargetId";
  v213 = &g_DbgUsb4MonitorTargetId;
  v219 = L"Usb4MonitorDpcdUSB4_Driver_ID";
  v220 = &g_DbgUsb4MonitorDpcdUSB4_Driver_ID;
  v226 = L"Usb4MonitorDpcdDP_IN_Adapter_Number";
  v227 = &g_DbgUsb4MonitorDpcdDP_IN_Adapter_Number;
  v233 = L"Usb4MonitorPowerOnDelayInSeconds";
  v234 = &g_DbgUsb4MonitorPowerOnDelayInSeconds;
  v240 = L"TreatUsb4MonitorAsNormal";
  v241 = &g_bDbgTreatUsb4MonitorAsNormal;
  v186 = 67108868;
  v188 = 4;
  v189 = 0;
  v190 = 288;
  v193 = 67108868;
  v195 = 4;
  v196 = 0;
  v197 = 288;
  v200 = 67108868;
  v202 = 4;
  v203 = 0;
  v204 = 288;
  v207 = 67108868;
  v208 = 0;
  v209 = 0;
  v210 = 0;
  v211 = 288;
  v214 = 67108868;
  v215 = 0;
  v216 = 0;
  v217 = 0;
  v218 = 288;
  v221 = 67108868;
  v222 = 0;
  v223 = 0;
  v224 = 0;
  v225 = 288;
  v228 = 67108868;
  v229 = 0;
  v230 = 0;
  v231 = 0;
  v232 = 288;
  v235 = 67108868;
  v236 = 0;
  v237 = 0;
  v238 = 0;
  v239 = 288;
  v242 = 67108868;
  v243 = 0;
  v244 = 0;
  v245 = 0;
  v246 = 288;
  v249 = 67108868;
  v253 = 288;
  v247 = L"AllowAdvancedEtwLogging";
  v256 = 67108868;
  v248 = &v61;
  v260 = 288;
  v254 = L"NodeUsageTelemetryTimerInterval";
  v263 = 67108868;
  v255 = &v62;
  v250 = 0;
  v261 = L"NativeFenceDebugTest";
  v262 = &v63;
  v251 = 0;
  v252 = 0;
  v257 = 0;
  v258 = 0;
  v259 = 0;
  v264 = 0;
  v265 = 0;
  v266 = 0;
  v267 = 0;
  v268 = 0;
  v269 = 0;
  v270 = 0;
  if ( (int)RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v84, 0, 0) < 0 )
  {
    *(_QWORD *)(v1 + 920) = 0x4000000;
    *(_DWORD *)(v1 + 1380) = 32;
    *(_BYTE *)(v1 + 928) = 0;
    *(_DWORD *)(v1 + 1376) = 1;
    *(_DWORD *)(v1 + 1664) = 0;
    *(_DWORD *)(v1 + 1680) = 0;
  }
  else
  {
    *(_QWORD *)(v1 + 920) = v51;
    *(_BYTE *)(v1 + 928) = v52 != 0;
    *(_BYTE *)(v1 + 304898) = v53 != 0;
    v20 = 1;
    if ( v50 < 2 )
      v20 = v50;
    *(_DWORD *)(v1 + 1376) = v20;
    v21 = v49;
    if ( v49 >= 4 )
    {
      if ( v49 > 0x400 )
      {
        v21 = 1024;
        v49 = 1024;
      }
    }
    else
    {
      v21 = 4;
      v49 = 4;
    }
    *(_DWORD *)(v1 + 1380) = v21;
    *(_DWORD *)(v1 + 1664) = v54;
    *(_DWORD *)(v1 + 1680) = v55;
    *(_BYTE *)(v1 + 304897) = v56 == 1;
    *(_BYTE *)(v1 + 304952) = v57 != 0;
    *(_BYTE *)(v1 + 304953) = v58 != 0;
    if ( v59 )
      *(_DWORD *)(v1 + 305664) = v59;
    if ( v60 )
      *(_DWORD *)(v1 + 305668) = v60;
    if ( !g_IsInternalRelease && !g_OSTestSigningEnabled )
    {
      g_bDbgForceUsb4MonitorSupport = 0;
      g_bDbgTreatUsb4MonitorAsNormal = 0;
      g_DbgUsb4MonitorPowerOnDelayInSeconds = 0;
    }
    *(_BYTE *)(v1 + 305736) = v61 != 0;
    *(_DWORD *)(v1 + 305944) = v62;
    DXGGLOBAL::SetNodeUsageTelemetryTimer((DXGGLOBAL *)v1);
    *(_BYTE *)(v1 + 305952) = v63 != 0;
  }
  *(_DWORD *)(v1 + 912) = 0;
  *(_OWORD *)v271 = *(_OWORD *)L"\\REGISTRY\\MACHINE\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  v64 = 0;
  *(_OWORD *)&v271[32] = *(_OWORD *)L"E\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  *(_QWORD *)&v82.Length = 9830548;
  *(_OWORD *)&v271[16] = *(_OWORD *)L"Y\\MACHINE\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  *(_QWORD *)&v81.Length = 2228256;
  *(_OWORD *)&v271[64] = *(_OWORD *)L"Set001\\Control\\Terminal Server\\WinStations";
  *(_OWORD *)&v271[48] = *(_OWORD *)L"\\ControlSet001\\Control\\Terminal Server\\WinStations";
  v272 = *(_OWORD *)L"erminal Server\\WinStations";
  v274[0] = *(_OWORD *)L"inStations";
  *(_QWORD *)((char *)v274 + 14) = *(_QWORD *)L"ons";
  v82.Buffer = (wchar_t *)v271;
  *(_OWORD *)&v271[80] = *(_OWORD *)L"ontrol\\Terminal Server\\WinStations";
  v276 = aDwmframeinterv[16];
  v273 = *(_OWORD *)L"Server\\WinStations";
  v81.Buffer = (wchar_t *)v275;
  v275[0] = *(_OWORD *)L"DWMFRAMEINTERVAL";
  v275[1] = *(_OWORD *)L"INTERVAL";
  if ( ReadRegistryDwordKeyValue(&v82, &v81, &v64) >= 0 && v64 )
    *(_DWORD *)(v1 + 305216) = v64;
  DxgkSharedObjectTypes = CreateDxgkSharedObjectTypes();
  v13 = DxgkSharedObjectTypes;
  if ( DxgkSharedObjectTypes < 0 )
  {
    WdLogSingleEntry1(3, DxgkSharedObjectTypes);
    WdLogGlobalForLineNumber = 2179;
    return v13;
  }
  v23 = v46;
  if ( !v46 || ((v46 - 1) & v46) != 0 )
  {
    v23 = v65;
    v46 = v65;
  }
  v24 = v48;
  if ( !v48 || ((v48 - 1) & v48) != 0 )
  {
    v24 = v66;
    v48 = v66;
  }
  if ( !g_OSTestSigningEnabled )
  {
    if ( v44 < 0x1000 || v44 * v23 > 0x1000000 )
    {
      v44 = 0x1000000;
      v46 = 1;
    }
    if ( v45 < 0x1000 || v45 * v24 > 0x1000000 )
    {
      v45 = 0x1000000;
      v48 = 1;
    }
  }
  if ( v47 > 0xE10 )
    v47 = 3600;
  v25 = (-(__int64)(g_IsInternalReleaseOrDbg != 0) & 0xFFFFFFFFFFFFFF40uLL) + 256;
  v26 = operator new(112, 1265072196, v25);
  if ( v26 )
    v27 = DXGDIAGNOSTICS::DXGDIAGNOSTICS(v26, v44, v46, v25, v47);
  else
    v27 = 0;
  *(_QWORD *)(v1 + 968) = v27;
  v28 = operator new(112, 1265072196, v25);
  if ( v28 )
    v29 = DXGDIAGNOSTICS::DXGDIAGNOSTICS(v28, v45, v48, v25, v47);
  else
    v29 = 0;
  *(_QWORD *)(v1 + 976) = v29;
  if ( !*(_QWORD *)(v1 + 968) )
  {
    WdLogSingleEntry1(6, v44);
    WdLogGlobalForLineNumber = 2233;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for internal diagnostics buffers (SmallInternalDiagnosticsSize = 0x%I64x).",
      v44,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  if ( !v29 )
  {
    WdLogSingleEntry1(6, v45);
    WdLogGlobalForLineNumber = 2239;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for external diagnostics buffers (SmallExternalDiagnosticsSize = 0x%I64x).",
      v45,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v30 = (DXGSESSIONMGR *)operator new(448, 1265072196, 64);
  if ( v30 )
    v31 = DXGSESSIONMGR::DXGSESSIONMGR(v30);
  else
    v31 = 0;
  *(_QWORD *)(v1 + 984) = v31;
  if ( !v31 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 2246;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for dxgkrnl session manager.",
      2246,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v32 = *(_DWORD *)(v1 + 1380);
  v33 = (unsigned int)(v32 + 31) >> 5;
  v34 = 4LL * ((unsigned int)v33 + ((unsigned int)(1055 - v32) >> 5));
  if ( !is_mul_ok((unsigned int)v33 + ((unsigned int)(1055 - v32) >> 5), 4u) )
    v34 = -1;
  v35 = (ULONG *)operator new[](v34, 1265072196, 256);
  *(_QWORD *)(v1 + 904) = v35;
  if ( !v35 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 2255;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for dxgkrnl adapter ordinal bits.",
      2255,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  RtlInitializeBitMap((PRTL_BITMAP)(v1 + 872), v35, *(_DWORD *)(v1 + 1380));
  RtlInitializeBitMap((PRTL_BITMAP)(v1 + 888), (PULONG)(*(_QWORD *)(v1 + 904) + 4 * v33), 1024 - *(_DWORD *)(v1 + 1380));
  if ( DXGPROCESS::CreateDxgProcess((struct DXGPROCESS **)(v1 + 1384), 0, 0, 0, 0) < 0 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 2269;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for system process.",
      2269,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  if ( PsInitialSystemProcess != *(PEPROCESS *)(*(_QWORD *)(v1 + 1384) + 56LL) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2272;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"PsInitialSystemProcess == m_pSystemDxgProcess->GetEProcess()",
      2272,
      0,
      0,
      0,
      0);
  }
  v36 = operator new(640, 1265072196, 256);
  v37 = (_BYTE *)v36;
  if ( v36 )
  {
    *(_BYTE *)v36 = 1;
    *(_QWORD *)(v36 + 16) = 0;
    *(_QWORD *)(v36 + 24) = 0;
    *(_QWORD *)(v36 + 32) = 0;
    *(_DWORD *)(v36 + 40) = 0;
    *(_DWORD *)(v36 + 44) = 69;
    *(_DWORD *)(v36 + 48) = 1;
    *(_DWORD *)(v36 + 632) = 0;
    memset((void *)(v36 + 56), 0, 0x240u);
    *v37 = 0;
  }
  else
  {
    v37 = 0;
  }
  *(_QWORD *)(v1 + 1480) = v37;
  if ( !v37 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 2277;
    DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to Qdc cache.", 2277, 0, 0, 0, 0);
    return 3221225495LL;
  }
  KeInitializeSpinLock(&qword_140162B90);
  DXGVALIDATION::InitializeBootSettings((DXGVALIDATION *)(v1 + 1668));
  DXGGLOBAL::CsExitInitiatedWnfSubscription((DXGGLOBAL *)v1);
  KeInitializeTimer((PKTIMER)(v1 + 1920));
  KeInitializeDpc((PRKDPC)(v1 + 1984), CsExitInitiatedReleaseComponentReferences, (PVOID)v1);
  OutputBuffer[0] = 0;
  v38 = ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
  if ( v38 >= 0 )
  {
    if ( OutputBuffer[0] )
      DXGGLOBAL::SubscribeWNFForCSAccounting((DXGGLOBAL *)v1);
  }
  else
  {
    v39 = v38;
    WdLogSingleEntry1(2, v38);
    WdLogGlobalForLineNumber = 2314;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to get the platformInformation. Status : 0x%I64x",
      v39,
      0,
      0,
      0,
      0);
  }
  *(_QWORD *)(v1 + 2072) = v1;
  *(_QWORD *)(v1 + 2064) = CsExitInitiatedReleaseComponentReferencesPassiveLevel;
  *(_QWORD *)(v1 + 2048) = 0;
  DXGGLOBAL::InitializeResourceManagerSid((DXGGLOBAL *)v1);
  *(_DWORD *)(v1 + 304884) &= ~1u;
  *(_DWORD *)(v1 + 304872) = 10;
  *(_DWORD *)(v1 + 304876) = 50;
  *(_DWORD *)(v1 + 304880) = 30;
  KeInitializeSpinLock((PKSPIN_LOCK)(v1 + 1768));
  DisplayDiagnostics::Initialize((PVOID)(v1 + 305024));
  v40 = PoRegisterPowerSettingCallback(
          0,
          &GUID_ADVANCED_COLOR_QUALITY_BIAS,
          DXGGLOBAL::AdvancedColorPowerSettingsCallback,
          (PVOID)v1,
          0);
  v7 = v40;
  if ( v40 < 0 )
  {
    WdLogSingleEntry1(2, v40);
    WdLogGlobalForLineNumber = 2351;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"PoRegisterPowerSettingCallback for GUID_HDR_DISPLAY_QUALITY_BIAS failed with status:0x%I64x",
      v7,
      0,
      0,
      0,
      0);
    return (unsigned int)v7;
  }
  v41 = PoRegisterPowerSettingCallback(0, &GUID_ACDC_POWER_SOURCE, DXGGLOBAL::AcDcPowerSourceCallback, (PVOID)v1, 0);
  v42 = v41;
  if ( v41 >= 0 )
    return RegisterDxgKernelProcessExtensions();
  WdLogSingleEntry1(2, v41);
  WdLogGlobalForLineNumber = 2361;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"PoRegisterPowerSettingCallback for GUID_ACDC_POWER_SOURCE failed with status:0x%I64x",
    v42,
    0,
    0,
    0,
    0);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x140240088  push    rbp
0x14024008a  push    rbx
0x14024008b  push    rdi
0x14024008c  push    r12
0x14024008e  push    r13
0x140240090  push    r14
0x140240092  push    r15
0x140240094  lea     rbp, [rsp-6D0h]
0x14024009c  sub     rsp, 7D0h
0x1402400a3  mov     rax, cs:__security_cookie
0x1402400aa  xor     rax, rsp
0x1402400ad  mov     [rbp+700h+var_38], rax
0x1402400b4  mov     rdi, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1402400bb  lea     rcx, [rbp+700h+var_100]; void *
0x1402400c2  xor     edx, edx; Val
0x1402400c4  lea     r8d, [rdx+58h]; Size
0x1402400c8  call    memset
0x1402400cd  movaps  xmm0, [rbp+700h+var_100]
0x1402400d4  lea     rcx, [rdi+4A930h]; Lookaside
0x1402400db  movaps  xmm1, [rbp+700h+var_F0]
0x1402400e2  xor     r15d, r15d
0x1402400e5  mov     rax, cs:__imp_ZwAllocateVirtualMemory
0x1402400ec  mov     r13d, 4B677844h
0x1402400f2  movups  xmmword ptr [rdi+40h], xmm0
0x1402400f6  mov     ebx, 200h
0x1402400fb  mov     [rsp+800h+Depth], r15w; Depth
0x140240101  movaps  xmm0, [rbp+700h+var_E0]
0x140240108  mov     r9d, ebx; PoolType
0x14024010b  movups  xmmword ptr [rdi+50h], xmm1
0x14024010f  xor     r8d, r8d; Free
0x140240112  mov     [rsp+800h+Tag], r13d; Tag
0x140240117  movaps  xmm1, [rbp+700h+var_D0]
0x14024011e  xor     edx, edx; Allocate
0x140240120  movups  xmmword ptr [rdi+60h], xmm0
0x140240124  mov     [rsp+800h+Size], 10h; Size
0x14024012d  movaps  xmm0, [rbp+700h+var_C0]
0x140240134  movups  xmmword ptr [rdi+70h], xmm1
0x140240138  mov     [rsp+800h+Flags], r15d; Flags
0x14024013d  movsd   xmm1, qword ptr [rbp+700h+var_B0]
0x140240145  movups  xmmword ptr [rdi+80h], xmm0
0x14024014c  movsd   qword ptr [rdi+90h], xmm1
0x140240154  mov     cs:?g_WindowsSubsystem@@3UDXGK_VIRTUAL_MEMORY_INTERFACE@@A, rax; DXGK_VIRTUAL_MEMORY_INTERFACE g_WindowsSubsystem
0x14024015b  mov     rax, cs:__imp_ZwAllocateVirtualMemoryEx
0x140240162  mov     cs:qword_140162C80, rax
0x140240169  mov     rax, cs:__imp_ZwFreeVirtualMemory
0x140240170  mov     cs:qword_140162C88, rax
0x140240177  mov     rax, cs:__imp_MmMapViewOfSection
0x14024017e  mov     cs:qword_140162C90, rax
0x140240185  mov     rax, cs:__imp_MmUnmapViewOfSection
0x14024018c  mov     cs:qword_140162C98, rax
0x140240193  mov     rax, cs:__imp_MmMapLockedPagesSpecifyCache
0x14024019a  mov     cs:qword_140162CA0, rax
0x1402401a1  mov     rax, cs:__imp_MmUnmapLockedPages
0x1402401a8  mov     cs:qword_140162CA8, rax
0x1402401af  mov     rax, cs:__imp_ZwAllocateVirtualMemory
0x1402401b6  mov     cs:?g_WslSubsystem@@3UDXGK_VIRTUAL_MEMORY_INTERFACE@@A, rax; DXGK_VIRTUAL_MEMORY_INTERFACE g_WslSubsystem
0x1402401bd  mov     rax, cs:__imp_ZwAllocateVirtualMemoryEx
0x1402401c4  mov     cs:qword_140162C40, rax
0x1402401cb  mov     rax, cs:__imp_ZwFreeVirtualMemory
0x1402401d2  mov     cs:qword_140162C48, rax
0x1402401d9  mov     rax, cs:__imp_MmMapViewOfSection
0x1402401e0  mov     cs:qword_140162C50, rax
0x1402401e7  mov     rax, cs:__imp_MmUnmapViewOfSection
0x1402401ee  mov     cs:qword_140162C58, rax
0x1402401f5  mov     rax, cs:__imp_MmMapLockedPagesSpecifyCache
0x1402401fc  mov     cs:qword_140162C60, rax
0x140240203  mov     rax, cs:__imp_MmUnmapLockedPages
0x14024020a  mov     cs:qword_140162C68, rax
0x140240211  call    cs:__imp_ExInitializeLookasideListEx
0x140240218  nop     dword ptr [rax+rax+00h]
0x14024021d  movsxd  r14, eax
0x140240220  test    eax, eax
0x140240222  jns     short loc_14024027C
0x140240224  mov     r8, r14
0x140240227  lea     ecx, [r15+2]
0x14024022b  mov     rdx, rdi
0x14024022e  call    cs:__imp_WdLogSingleEntry2
0x140240235  nop     dword ptr [rax+rax+00h]
0x14024023a  lea     r9, aDxgglobal0xI64; "DXGGlobal 0x%I64x: Unable to initialize"...
0x140240241  mov     cs:WdLogGlobalForLineNumber, 726h
0x14024024b  mov     [rsp+800h+var_7C0], r15
0x140240250  mov     qword ptr [rsp+800h+Depth], r15
0x140240255  mov     qword ptr [rsp+800h+Tag], r15
0x14024025a  mov     [rsp+800h+Size], r14
0x14024025f  mov     qword ptr [rsp+800h+Flags], rdi
0x140240264  or      r8d, 0FFFFFFFFh
0x140240268  mov     edx, 40000h
0x14024026d  xor     ecx, ecx
0x14024026f  call    DxgkLogInternalTriageEvent
0x140240274  mov     eax, r14d
0x140240277  jmp     loc_140241544
0x14024027c  mov     [rsp+800h+Depth], r15w; Depth
0x140240282  lea     rcx, [rdi+0A0h]; Lookaside
0x140240289  mov     [rsp+800h+Tag], 576B7844h; Tag
0x140240291  mov     r12d, 1
0x140240297  mov     [rsp+800h+Size], 0A0h; Size
0x1402402a0  mov     r9d, ebx; PoolType
0x1402402a3  xor     r8d, r8d; Free
0x1402402a6  mov     [rsp+800h+Flags], r15d; Flags
0x1402402ab  xor     edx, edx; Allocate
0x1402402ad  mov     [rdi+4A920h], r12b
0x1402402b4  call    cs:__imp_ExInitializeLookasideListEx
0x1402402bb  nop     dword ptr [rax+rax+00h]
0x1402402c0  movsxd  r14, eax
0x1402402c3  test    eax, eax
0x1402402c5  jns     short loc_1402402F4
0x1402402c7  mov     r8, r14
0x1402402ca  lea     ecx, [r12+1]
0x1402402cf  mov     rdx, rdi
0x1402402d2  call    cs:__imp_WdLogSingleEntry2
0x1402402d9  nop     dword ptr [rax+rax+00h]
0x1402402de  lea     r9, aDxgglobal0xI64_0; "DXGGlobal 0x%I64x: Unable to initialize"...
0x1402402e5  mov     cs:WdLogGlobalForLineNumber, 732h
0x1402402ef  jmp     loc_14024024B
0x1402402f4  lea     rcx, [rdi+158h]; this
0x1402402fb  mov     [rdi+553h], r12b
0x140240302  call    ?ExpandTable@HMGRTABLE@@QEAAEXZ; HMGRTABLE::ExpandTable(void)
0x140240307  test    al, al
0x140240309  jnz     short loc_14024036B
0x14024030b  mov     rdx, 0FFFFFFFFC0000017h
0x140240312  mov     ecx, 6
0x140240317  call    cs:__imp_WdLogSingleEntry1
0x14024031e  nop     dword ptr [rax+rax+00h]
0x140240323  mov     [rsp+800h+var_7C0], r15
0x140240328  lea     r9, aFailedTheIniti; "Failed the initial shared resource hand"...
0x14024032f  mov     qword ptr [rsp+800h+Depth], r15
0x140240334  mov     qword ptr [rsp+800h+Tag], r15
0x140240339  mov     [rsp+800h+Size], r15
0x14024033e  mov     qword ptr [rsp+800h+Flags], 0FFFFFFFFC0000017h
0x140240347  mov     cs:WdLogGlobalForLineNumber, 73Eh
0x140240351  or      r8d, 0FFFFFFFFh
0x140240355  mov     edx, 40001h
0x14024035a  xor     ecx, ecx
0x14024035c  call    DxgkLogInternalTriageEvent
0x140240361  mov     eax, 0C0000017h
0x140240366  jmp     loc_140241544
0x14024036b  mov     r8d, 40h ; '@'
0x140240371  mov     edx, r13d
0x140240374  lea     ecx, [r8+28h]
0x140240378  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14024037d  mov     [rdi+260h], rax
0x140240384  test    rax, rax
0x140240387  jnz     short loc_1402403AE
0x140240389  mov     r8, 0FFFFFFFFC0000017h
0x140240390  lea     ecx, [rax+3]
0x140240393  mov     rdx, rdi
0x140240396  call    cs:__imp_WdLogSingleEntry2
0x14024039d  nop     dword ptr [rax+rax+00h]
0x1402403a2  mov     cs:WdLogGlobalForLineNumber, 74Bh
0x1402403ac  jmp     short loc_140240361
0x1402403ae  mov     rcx, rax; Resource
0x1402403b1  call    cs:__imp_ExInitializeResourceLite
0x1402403b8  nop     dword ptr [rax+rax+00h]
0x1402403bd  movsxd  rbx, eax
0x1402403c0  test    eax, eax
0x1402403c2  jns     short loc_1402403EC
0x1402403c4  mov     r8, rbx
0x1402403c7  mov     rdx, rdi
0x1402403ca  mov     ecx, 3
0x1402403cf  call    cs:__imp_WdLogSingleEntry2
0x1402403d6  nop     dword ptr [rax+rax+00h]
0x1402403db  mov     cs:WdLogGlobalForLineNumber, 755h
0x1402403e5  mov     eax, ebx
0x1402403e7  jmp     loc_140241544
0x1402403ec  mov     [rsp+800h+Depth], r15w; Depth
0x1402403f2  lea     rcx, [rdi+480h]; Lookaside
0x1402403f9  mov     [rsp+800h+Tag], r13d; Tag
0x1402403fe  mov     r9d, r12d; PoolType
0x140240401  mov     [rsp+800h+Size], 5F8h; Size
0x14024040a  xor     r8d, r8d; Free
0x14024040d  xor     edx, edx; Allocate
0x14024040f  mov     [rsp+800h+Flags], r15d; Flags
0x140240414  call    cs:__imp_ExInitializeLookasideListEx
0x14024041b  nop     dword ptr [rax+rax+00h]
0x140240420  movsxd  rbx, eax
0x140240423  test    eax, eax
0x140240425  jns     short loc_14024044C
0x140240427  xor     r9d, r9d
0x14024042a  mov     r8, rbx
0x14024042d  mov     rdx, rdi
0x140240430  lea     ecx, [r9+3]
0x140240434  call    cs:__imp_WdLogSingleEntry3
0x14024043b  nop     dword ptr [rax+rax+00h]
0x140240440  mov     cs:WdLogGlobalForLineNumber, 75Eh
0x14024044a  jmp     short loc_1402403E5
0x14024044c  mov     [rsp+800h+Depth], r15w; Depth
0x140240452  lea     rcx, [rdi+4E0h]; Lookaside
0x140240459  mov     [rsp+800h+Tag], r13d; Tag
0x14024045e  mov     r9d, r12d; PoolType
0x140240461  mov     [rsp+800h+Size], 5E0h; Size
0x14024046a  xor     r8d, r8d; Free
0x14024046d  xor     edx, edx; Allocate
0x14024046f  mov     [rsp+800h+Flags], r15d; Flags
0x140240474  mov     [rdi+551h], r12b
0x14024047b  call    cs:__imp_ExInitializeLookasideListEx
0x140240482  nop     dword ptr [rax+rax+00h]
0x140240487  movsxd  rbx, eax
0x14024048a  test    eax, eax
0x14024048c  jns     short loc_1402404B6
0x14024048e  xor     r9d, r9d
0x140240491  mov     r8, rbx
0x140240494  mov     rdx, rdi
0x140240497  lea     ecx, [r9+3]
0x14024049b  call    cs:__imp_WdLogSingleEntry3
0x1402404a2  nop     dword ptr [rax+rax+00h]
0x1402404a7  mov     cs:WdLogGlobalForLineNumber, 768h
0x1402404b1  jmp     loc_1402403E5
0x1402404b6  mov     r9b, cs:?g_bSkuSupportMultipleUsers@@3EA; uchar g_bSkuSupportMultipleUsers
0x1402404bd  mov     r10d, 70000h
0x1402404c3  mov     [rdi+552h], r12b
0x1402404ca  mov     r11d, 10000h
0x1402404d0  mov     dl, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1402404d6  mov     [rbp+700h+var_6F8], 4000000h
0x1402404de  mov     al, dl
0x1402404e0  mov     [rsp+800h+var_790], r15d
0x1402404e5  mov     [rbp+700h+var_750], r15d
0x1402404e9  mov     [rsp+800h+var_78C], r15d
0x1402404ee  mov     [rbp+700h+var_74C], r12d
0x1402404f2  mov     [rsp+800h+var_794], r15d
0x1402404f7  mov     [rbp+700h+var_748], 20h ; ' '
0x1402404fe  mov     [rsp+800h+var_798], r15d
0x140240503  mov     [rsp+800h+var_784], r15d
0x140240508  mov     [rbp+700h+var_744], r15d
0x14024050c  mov     [rbp+700h+var_740], r15d
0x140240510  mov     [rbp+700h+var_780], r15d
0x140240514  mov     [rbp+700h+var_77C], r15d
0x140240518  mov     [rbp+700h+var_73C], r15d
0x14024051c  mov     [rbp+700h+var_738], r15d
0x140240520  mov     [rbp+700h+var_778], r15d
0x140240524  mov     [rbp+700h+var_734], r15d
0x140240528  mov     [rbp+700h+var_774], r15d
0x14024052c  mov     [rbp+700h+var_730], r15d
0x140240530  mov     [rsp+800h+var_788], r15d
0x140240535  mov     [rbp+700h+var_768], r15d
0x140240539  mov     [rbp+700h+var_760], r15d
0x14024053d  test    r9b, r9b
0x140240540  jz      short loc_140240551
0x140240542  neg     al
0x140240544  mov     eax, 80000h
0x140240549  sbb     ecx, ecx
0x14024054b  and     ecx, eax
0x14024054d  add     ecx, eax
0x14024054f  jmp     short loc_14024055B
0x140240551  neg     al
0x140240553  sbb     ecx, ecx
0x140240555  and     ecx, r10d
0x140240558  add     ecx, r11d
0x14024055b  mov     [rbp+700h+var_72C], ecx
0x14024055e  mov     ebx, 4
0x140240563  test    r9b, r9b
0x140240566  jz      short loc_140240577
0x140240568  mov     al, dl
0x14024056a  neg     al
0x14024056c  sbb     r8d, r8d
0x14024056f  and     r8d, ebx
0x140240572  add     r8d, ebx
0x140240575  jmp     short loc_14024057D
0x140240577  mov     r8d, 2
0x14024057d  mov     [rbp+700h+var_758], r8d
0x140240581  test    r9b, r9b
0x140240584  jz      short loc_140240592
0x140240586  neg     dl
0x140240588  sbb     eax, eax
0x14024058a  and     eax, r10d
0x14024058d  add     eax, r11d
0x140240590  jmp     short loc_1402405A0
0x140240592  neg     dl
0x140240594  sbb     eax, eax
0x140240596  and     eax, 7C000h
0x14024059b  add     eax, 4000h
0x1402405a0  mov     [rbp+700h+var_728], eax
0x1402405a3  mov     edx, 12Ch
0x1402405a8  mov     [rsp+800h+var_7A8], eax
0x1402405ac  mov     [rbp+700h+var_724], edx
0x1402405af  mov     [rsp+800h+var_7A0], edx
0x1402405b3  mov     edx, 120h
0x1402405b8  mov     [rsp+800h+var_7AC], ecx
0x1402405bc  mov     ecx, 4000004h
0x1402405c1  mov     [rbp+700h+var_754], r12d
0x1402405c5  mov     [rsp+800h+var_7A4], r8d
0x1402405ca  mov     [rsp+800h+var_79C], r12d
0x1402405cf  mov     [rbp+700h+var_720], 1388h
0x1402405d6  mov     [rbp+700h+var_770], r15d
0x1402405da  mov     [rbp+700h+var_71C], 3A98h
0x1402405e1  mov     [rbp+700h+var_76C], r15d
0x1402405e5  mov     eax, [rdi+4AB18h]
0x1402405eb  mov     [rbp+700h+var_764], eax
0x1402405ee  lea     rax, aTerminationlis; "TerminationListSizeLimit"
0x1402405f5  mov     [rbp+700h+var_6E0], rax
0x1402405f9  lea     rax, [rsp+800h+var_790]
0x1402405fe  mov     [rbp+700h+var_6D8], rax
0x140240602  lea     rax, [rbp+700h+var_6F8]
0x140240606  mov     [rbp+700h+var_6C8], rax
0x14024060a  lea     rax, aValidatewddmca; "ValidateWDDMCaps"
0x140240611  mov     [rbp+700h+var_6A8], rax
0x140240615  lea     rax, [rsp+800h+var_78C]
0x14024061a  mov     [rbp+700h+var_6A0], rax
0x14024061e  lea     rax, [rbp+700h+var_750]
0x140240622  mov     [rbp+700h+var_690], rax
0x140240626  lea     rax, aWddm2lockmanag; "WDDM2LockManagement"
  ... truncated ...
```
