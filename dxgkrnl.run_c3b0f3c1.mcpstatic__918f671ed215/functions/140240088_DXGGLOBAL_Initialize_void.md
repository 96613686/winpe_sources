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
  __int64 v22; // rcx
  int DxgkSharedObjectTypes; // eax
  unsigned int v24; // ecx
  unsigned int v25; // edx
  unsigned __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  DXGSESSIONMGR *v31; // rax
  DXGSESSIONMGR *v32; // rax
  int v33; // ecx
  __int64 v34; // rbx
  unsigned __int64 v35; // rax
  ULONG *v36; // rax
  __int64 v37; // rax
  _BYTE *v38; // rbx
  NTSTATUS v39; // eax
  __int64 v40; // rbx
  NTSTATUS v41; // eax
  NTSTATUS v42; // eax
  __int64 v43; // rdi
  ULONG Flags[2]; // [rsp+20h] [rbp-E0h]
  char OutputBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v48; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v50; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v51; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v52; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+74h] [rbp-8Ch] BYREF
  int v55; // [rsp+78h] [rbp-88h] BYREF
  int v56; // [rsp+7Ch] [rbp-84h] BYREF
  int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch] BYREF
  int v59; // [rsp+88h] [rbp-78h] BYREF
  int v60; // [rsp+8Ch] [rbp-74h] BYREF
  int v61; // [rsp+90h] [rbp-70h] BYREF
  int v62; // [rsp+94h] [rbp-6Ch] BYREF
  int v63; // [rsp+98h] [rbp-68h] BYREF
  int v64; // [rsp+9Ch] [rbp-64h] BYREF
  int v65; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v66; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v67; // [rsp+A8h] [rbp-58h] BYREF
  int v68; // [rsp+ACh] [rbp-54h] BYREF
  int v69; // [rsp+B0h] [rbp-50h] BYREF
  int v70; // [rsp+B4h] [rbp-4Ch] BYREF
  int v71; // [rsp+B8h] [rbp-48h] BYREF
  int v72; // [rsp+BCh] [rbp-44h] BYREF
  int v73; // [rsp+C0h] [rbp-40h] BYREF
  int v74; // [rsp+C4h] [rbp-3Ch] BYREF
  int v75; // [rsp+C8h] [rbp-38h] BYREF
  int v76; // [rsp+CCh] [rbp-34h] BYREF
  int v77; // [rsp+D0h] [rbp-30h] BYREF
  int v78; // [rsp+D4h] [rbp-2Ch] BYREF
  int v79; // [rsp+D8h] [rbp-28h] BYREF
  int v80; // [rsp+DCh] [rbp-24h] BYREF
  int v81; // [rsp+E0h] [rbp-20h] BYREF
  int v82; // [rsp+E4h] [rbp-1Ch] BYREF
  struct _UNICODE_STRING v83; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v84; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v85; // [rsp+108h] [rbp+8h] BYREF
  __int64 v86; // [rsp+110h] [rbp+10h] BYREF
  int v87; // [rsp+118h] [rbp+18h]
  const wchar_t *v88; // [rsp+120h] [rbp+20h]
  unsigned int *v89; // [rsp+128h] [rbp+28h]
  int v90; // [rsp+130h] [rbp+30h]
  __int64 *v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+150h] [rbp+50h]
  const wchar_t *v95; // [rsp+158h] [rbp+58h]
  int *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int *v98; // [rsp+170h] [rbp+70h]
  int v99; // [rsp+178h] [rbp+78h]
  __int64 v100; // [rsp+180h] [rbp+80h]
  int v101; // [rsp+188h] [rbp+88h]
  const wchar_t *v102; // [rsp+190h] [rbp+90h]
  unsigned int *v103; // [rsp+198h] [rbp+98h]
  int v104; // [rsp+1A0h] [rbp+A0h]
  int *v105; // [rsp+1A8h] [rbp+A8h]
  int v106; // [rsp+1B0h] [rbp+B0h]
  __int64 v107; // [rsp+1B8h] [rbp+B8h]
  int v108; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v109; // [rsp+1C8h] [rbp+C8h]
  unsigned int *v110; // [rsp+1D0h] [rbp+D0h]
  int v111; // [rsp+1D8h] [rbp+D8h]
  int *v112; // [rsp+1E0h] [rbp+E0h]
  int v113; // [rsp+1E8h] [rbp+E8h]
  __int64 v114; // [rsp+1F0h] [rbp+F0h]
  int v115; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v116; // [rsp+200h] [rbp+100h]
  int *v117; // [rsp+208h] [rbp+108h]
  int v118; // [rsp+210h] [rbp+110h]
  int *v119; // [rsp+218h] [rbp+118h]
  int v120; // [rsp+220h] [rbp+120h]
  __int64 v121; // [rsp+228h] [rbp+128h]
  int v122; // [rsp+230h] [rbp+130h]
  const wchar_t *v123; // [rsp+238h] [rbp+138h]
  int *v124; // [rsp+240h] [rbp+140h]
  int v125; // [rsp+248h] [rbp+148h]
  int *v126; // [rsp+250h] [rbp+150h]
  int v127; // [rsp+258h] [rbp+158h]
  __int64 v128; // [rsp+260h] [rbp+160h]
  int v129; // [rsp+268h] [rbp+168h]
  const wchar_t *v130; // [rsp+270h] [rbp+170h]
  int *v131; // [rsp+278h] [rbp+178h]
  int v132; // [rsp+280h] [rbp+180h]
  int *v133; // [rsp+288h] [rbp+188h]
  int v134; // [rsp+290h] [rbp+190h]
  __int64 v135; // [rsp+298h] [rbp+198h]
  int v136; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v137; // [rsp+2A8h] [rbp+1A8h]
  int *v138; // [rsp+2B0h] [rbp+1B0h]
  int v139; // [rsp+2B8h] [rbp+1B8h]
  int *v140; // [rsp+2C0h] [rbp+1C0h]
  int v141; // [rsp+2C8h] [rbp+1C8h]
  __int64 v142; // [rsp+2D0h] [rbp+1D0h]
  int v143; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v144; // [rsp+2E0h] [rbp+1E0h]
  int *v145; // [rsp+2E8h] [rbp+1E8h]
  int v146; // [rsp+2F0h] [rbp+1F0h]
  int *v147; // [rsp+2F8h] [rbp+1F8h]
  int v148; // [rsp+300h] [rbp+200h]
  __int64 v149; // [rsp+308h] [rbp+208h]
  int v150; // [rsp+310h] [rbp+210h]
  const wchar_t *v151; // [rsp+318h] [rbp+218h]
  int *v152; // [rsp+320h] [rbp+220h]
  int v153; // [rsp+328h] [rbp+228h]
  int *v154; // [rsp+330h] [rbp+230h]
  int v155; // [rsp+338h] [rbp+238h]
  __int64 v156; // [rsp+340h] [rbp+240h]
  int v157; // [rsp+348h] [rbp+248h]
  const wchar_t *v158; // [rsp+350h] [rbp+250h]
  unsigned int *v159; // [rsp+358h] [rbp+258h]
  int v160; // [rsp+360h] [rbp+260h]
  int *v161; // [rsp+368h] [rbp+268h]
  int v162; // [rsp+370h] [rbp+270h]
  __int64 v163; // [rsp+378h] [rbp+278h]
  int v164; // [rsp+380h] [rbp+280h]
  const wchar_t *v165; // [rsp+388h] [rbp+288h]
  unsigned int *v166; // [rsp+390h] [rbp+290h]
  int v167; // [rsp+398h] [rbp+298h]
  unsigned int *v168; // [rsp+3A0h] [rbp+2A0h]
  int v169; // [rsp+3A8h] [rbp+2A8h]
  __int64 v170; // [rsp+3B0h] [rbp+2B0h]
  int v171; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v172; // [rsp+3C0h] [rbp+2C0h]
  unsigned int *v173; // [rsp+3C8h] [rbp+2C8h]
  int v174; // [rsp+3D0h] [rbp+2D0h]
  int *v175; // [rsp+3D8h] [rbp+2D8h]
  int v176; // [rsp+3E0h] [rbp+2E0h]
  __int64 v177; // [rsp+3E8h] [rbp+2E8h]
  int v178; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v179; // [rsp+3F8h] [rbp+2F8h]
  unsigned int *v180; // [rsp+400h] [rbp+300h]
  int v181; // [rsp+408h] [rbp+308h]
  int *v182; // [rsp+410h] [rbp+310h]
  int v183; // [rsp+418h] [rbp+318h]
  __int64 v184; // [rsp+420h] [rbp+320h]
  int v185; // [rsp+428h] [rbp+328h]
  const wchar_t *v186; // [rsp+430h] [rbp+330h]
  unsigned int *v187; // [rsp+438h] [rbp+338h]
  int v188; // [rsp+440h] [rbp+340h]
  int *v189; // [rsp+448h] [rbp+348h]
  int v190; // [rsp+450h] [rbp+350h]
  __int64 v191; // [rsp+458h] [rbp+358h]
  int v192; // [rsp+460h] [rbp+360h]
  const wchar_t *v193; // [rsp+468h] [rbp+368h]
  int *v194; // [rsp+470h] [rbp+370h]
  int v195; // [rsp+478h] [rbp+378h]
  int *v196; // [rsp+480h] [rbp+380h]
  int v197; // [rsp+488h] [rbp+388h]
  __int64 v198; // [rsp+490h] [rbp+390h]
  int v199; // [rsp+498h] [rbp+398h]
  const wchar_t *v200; // [rsp+4A0h] [rbp+3A0h]
  int *v201; // [rsp+4A8h] [rbp+3A8h]
  int v202; // [rsp+4B0h] [rbp+3B0h]
  int *v203; // [rsp+4B8h] [rbp+3B8h]
  int v204; // [rsp+4C0h] [rbp+3C0h]
  __int64 v205; // [rsp+4C8h] [rbp+3C8h]
  int v206; // [rsp+4D0h] [rbp+3D0h]
  const wchar_t *v207; // [rsp+4D8h] [rbp+3D8h]
  unsigned int *v208; // [rsp+4E0h] [rbp+3E0h]
  int v209; // [rsp+4E8h] [rbp+3E8h]
  __int64 v210; // [rsp+4F0h] [rbp+3F0h]
  int v211; // [rsp+4F8h] [rbp+3F8h]
  __int64 v212; // [rsp+500h] [rbp+400h]
  int v213; // [rsp+508h] [rbp+408h]
  const wchar_t *v214; // [rsp+510h] [rbp+410h]
  unsigned int *v215; // [rsp+518h] [rbp+418h]
  int v216; // [rsp+520h] [rbp+420h]
  __int64 v217; // [rsp+528h] [rbp+428h]
  int v218; // [rsp+530h] [rbp+430h]
  __int64 v219; // [rsp+538h] [rbp+438h]
  int v220; // [rsp+540h] [rbp+440h]
  const wchar_t *v221; // [rsp+548h] [rbp+448h]
  unsigned int *v222; // [rsp+550h] [rbp+450h]
  int v223; // [rsp+558h] [rbp+458h]
  __int64 v224; // [rsp+560h] [rbp+460h]
  int v225; // [rsp+568h] [rbp+468h]
  __int64 v226; // [rsp+570h] [rbp+470h]
  int v227; // [rsp+578h] [rbp+478h]
  const wchar_t *v228; // [rsp+580h] [rbp+480h]
  unsigned int *v229; // [rsp+588h] [rbp+488h]
  int v230; // [rsp+590h] [rbp+490h]
  __int64 v231; // [rsp+598h] [rbp+498h]
  int v232; // [rsp+5A0h] [rbp+4A0h]
  __int64 v233; // [rsp+5A8h] [rbp+4A8h]
  int v234; // [rsp+5B0h] [rbp+4B0h]
  const wchar_t *v235; // [rsp+5B8h] [rbp+4B8h]
  unsigned int *v236; // [rsp+5C0h] [rbp+4C0h]
  int v237; // [rsp+5C8h] [rbp+4C8h]
  __int64 v238; // [rsp+5D0h] [rbp+4D0h]
  int v239; // [rsp+5D8h] [rbp+4D8h]
  __int64 v240; // [rsp+5E0h] [rbp+4E0h]
  int v241; // [rsp+5E8h] [rbp+4E8h]
  const wchar_t *v242; // [rsp+5F0h] [rbp+4F0h]
  unsigned int *v243; // [rsp+5F8h] [rbp+4F8h]
  int v244; // [rsp+600h] [rbp+500h]
  __int64 v245; // [rsp+608h] [rbp+508h]
  int v246; // [rsp+610h] [rbp+510h]
  __int64 v247; // [rsp+618h] [rbp+518h]
  int v248; // [rsp+620h] [rbp+520h]
  const wchar_t *v249; // [rsp+628h] [rbp+528h]
  int *v250; // [rsp+630h] [rbp+530h]
  int v251; // [rsp+638h] [rbp+538h]
  __int64 v252; // [rsp+640h] [rbp+540h]
  int v253; // [rsp+648h] [rbp+548h]
  __int64 v254; // [rsp+650h] [rbp+550h]
  int v255; // [rsp+658h] [rbp+558h]
  const wchar_t *v256; // [rsp+660h] [rbp+560h]
  int *v257; // [rsp+668h] [rbp+568h]
  int v258; // [rsp+670h] [rbp+570h]
  __int64 v259; // [rsp+678h] [rbp+578h]
  int v260; // [rsp+680h] [rbp+580h]
  __int64 v261; // [rsp+688h] [rbp+588h]
  int v262; // [rsp+690h] [rbp+590h]
  const wchar_t *v263; // [rsp+698h] [rbp+598h]
  int *v264; // [rsp+6A0h] [rbp+5A0h]
  int v265; // [rsp+6A8h] [rbp+5A8h]
  __int64 v266; // [rsp+6B0h] [rbp+5B0h]
  int v267; // [rsp+6B8h] [rbp+5B8h]
  __int64 v268; // [rsp+6C0h] [rbp+5C0h]
  int v269; // [rsp+6C8h] [rbp+5C8h]
  __int64 v270; // [rsp+6D0h] [rbp+5D0h]
  __int128 v271; // [rsp+6D8h] [rbp+5D8h]
  __int128 v272; // [rsp+6E8h] [rbp+5E8h]
  _BYTE v273[96]; // [rsp+700h] [rbp+600h] BYREF
  __int128 v274; // [rsp+760h] [rbp+660h]
  __int128 v275; // [rsp+770h] [rbp+670h]
  _OWORD v276[2]; // [rsp+780h] [rbp+680h]
  _OWORD v277[2]; // [rsp+7A0h] [rbp+6A0h] BYREF
  wchar_t v278; // [rsp+7C0h] [rbp+6C0h]

  v1 = *(_QWORD *)&DXGGLOBAL::m_pGlobal;
  memset(v273, 0, 0x58u);
  v2 = *(_OWORD *)&v273[16];
  *(_OWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 64LL) = *(_OWORD *)v273;
  v3 = *(_OWORD *)&v273[32];
  *(_OWORD *)(v1 + 80) = v2;
  v4 = *(_OWORD *)&v273[48];
  *(_OWORD *)(v1 + 96) = v3;
  v5 = *(_OWORD *)&v273[64];
  *(_OWORD *)(v1 + 112) = v4;
  *(_QWORD *)&v4 = *(_QWORD *)&v273[80];
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
  v85 = 0x4000000;
  v53 = 0;
  v69 = 0;
  v54 = 0;
  v70 = 1;
  v52 = 0;
  v71 = 32;
  v51 = 0;
  v56 = 0;
  v72 = 0;
  v73 = 0;
  v57 = 0;
  v58 = 0;
  v74 = 0;
  v75 = 0;
  v59 = 0;
  v76 = 0;
  v60 = 0;
  v77 = 0;
  v55 = 0;
  v63 = 0;
  v65 = 0;
  if ( v16 )
    v17 = g_IsInternalReleaseOrDbg != 0 ? 0x100000 : 0x80000;
  else
    v17 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x10000;
  v78 = v17;
  if ( v16 )
    v18 = g_IsInternalReleaseOrDbg != 0 ? 8 : 4;
  else
    v18 = 2;
  v67 = v18;
  if ( v16 )
    v19 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x10000;
  else
    v19 = g_IsInternalReleaseOrDbg != 0 ? 0x80000 : 0x4000;
  v79 = v19;
  v47 = v19;
  v80 = 300;
  v49 = 300;
  v46 = v17;
  v68 = 1;
  v48 = v18;
  v50 = 1;
  v81 = 5000;
  v61 = 0;
  v82 = 15000;
  v62 = 0;
  v64 = *(_DWORD *)(v1 + 305944);
  v88 = L"TerminationListSizeLimit";
  v89 = &v53;
  v91 = &v85;
  v95 = L"ValidateWDDMCaps";
  v96 = &v54;
  v98 = &v69;
  v102 = L"WDDM2LockManagement";
  v103 = &v52;
  v105 = &v70;
  v109 = L"MaximumAdapterCount";
  v110 = &v51;
  v112 = &v71;
  v116 = L"InvestigationDebugParameter";
  v117 = &v56;
  v119 = &v72;
  v123 = L"EnableIgnoreWin32ProcessStatus";
  v124 = &v57;
  v126 = &v73;
  v130 = L"EnableHMDTestMode";
  v86 = 0;
  v87 = 288;
  v90 = 67108868;
  v92 = 4;
  v93 = 0;
  v94 = 288;
  v97 = 67108868;
  v99 = 4;
  v100 = 0;
  v101 = 288;
  v104 = 67108868;
  v106 = 4;
  v107 = 0;
  v108 = 288;
  v111 = 67108868;
  v113 = 4;
  v114 = 0;
  v115 = 288;
  v118 = 67108868;
  v120 = 4;
  v121 = 0;
  v122 = 288;
  v125 = 67108868;
  v127 = 4;
  v128 = 0;
  v129 = 288;
  v132 = 67108868;
  v131 = &v58;
  v133 = &v74;
  v137 = L"PreserveFirmwareMode";
  v138 = &v59;
  v140 = &v75;
  v144 = L"PreventFullscreenWireFormatChange";
  v145 = &v60;
  v147 = &v76;
  v151 = L"EnableFuzzing";
  v152 = &v55;
  v154 = &v77;
  v158 = L"InternalDiagnosticsBufferSize";
  v159 = &v46;
  v161 = &v78;
  v165 = L"InternalDiagnosticsBufferMultiplier";
  v166 = &v48;
  v168 = &v67;
  v172 = L"ExternalDiagnosticsBufferSize";
  v173 = &v47;
  v175 = &v79;
  v179 = L"ExternalDiagnosticsBufferMultiplier";
  v180 = &v50;
  v182 = &v68;
  v186 = L"DiagnosticsBufferExpansionTime";
  v134 = 4;
  v135 = 0;
  v136 = 288;
  v139 = 67108868;
  v141 = 4;
  v142 = 0;
  v143 = 288;
  v146 = 67108868;
  v148 = 4;
  v149 = 0;
  v150 = 288;
  v153 = 67108868;
  v155 = 4;
  v156 = 0;
  v157 = 288;
  v160 = 67108868;
  v162 = 4;
  v163 = 0;
  v164 = 288;
  v167 = 67108868;
  v169 = 4;
  v170 = 0;
  v171 = 288;
  v174 = 67108868;
  v176 = 4;
  v177 = 0;
  v178 = 288;
  v181 = 67108868;
  v183 = 4;
  v184 = 0;
  v185 = 288;
  v187 = &v49;
  v189 = &v80;
  v193 = L"RapidHpdTimeoutInMilliseconds";
  v194 = &v61;
  v196 = &v81;
  v200 = L"RapidHpdMaxChainInMilliseconds";
  v201 = &v62;
  v203 = &v82;
  v207 = L"ForceUsb4MonitorSupport";
  v208 = &g_bDbgForceUsb4MonitorSupport;
  v214 = L"Usb4MonitorTargetId";
  v215 = &g_DbgUsb4MonitorTargetId;
  v221 = L"Usb4MonitorDpcdUSB4_Driver_ID";
  v222 = &g_DbgUsb4MonitorDpcdUSB4_Driver_ID;
  v228 = L"Usb4MonitorDpcdDP_IN_Adapter_Number";
  v229 = &g_DbgUsb4MonitorDpcdDP_IN_Adapter_Number;
  v235 = L"Usb4MonitorPowerOnDelayInSeconds";
  v236 = &g_DbgUsb4MonitorPowerOnDelayInSeconds;
  v242 = L"TreatUsb4MonitorAsNormal";
  v243 = &g_bDbgTreatUsb4MonitorAsNormal;
  v188 = 67108868;
  v190 = 4;
  v191 = 0;
  v192 = 288;
  v195 = 67108868;
  v197 = 4;
  v198 = 0;
  v199 = 288;
  v202 = 67108868;
  v204 = 4;
  v205 = 0;
  v206 = 288;
  v209 = 67108868;
  v210 = 0;
  v211 = 0;
  v212 = 0;
  v213 = 288;
  v216 = 67108868;
  v217 = 0;
  v218 = 0;
  v219 = 0;
  v220 = 288;
  v223 = 67108868;
  v224 = 0;
  v225 = 0;
  v226 = 0;
  v227 = 288;
  v230 = 67108868;
  v231 = 0;
  v232 = 0;
  v233 = 0;
  v234 = 288;
  v237 = 67108868;
  v238 = 0;
  v239 = 0;
  v240 = 0;
  v241 = 288;
  v244 = 67108868;
  v245 = 0;
  v246 = 0;
  v247 = 0;
  v248 = 288;
  v251 = 67108868;
  v255 = 288;
  v249 = L"AllowAdvancedEtwLogging";
  v258 = 67108868;
  v250 = &v63;
  v262 = 288;
  v256 = L"NodeUsageTelemetryTimerInterval";
  v265 = 67108868;
  v257 = &v64;
  v252 = 0;
  v263 = L"NativeFenceDebugTest";
  v264 = &v65;
  v253 = 0;
  v254 = 0;
  v259 = 0;
  v260 = 0;
  v261 = 0;
  v266 = 0;
  v267 = 0;
  v268 = 0;
  v269 = 0;
  v270 = 0;
  v271 = 0;
  Flags[1] = 0;
  v272 = 0;
  if ( (int)RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v86) < 0 )
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
    *(_QWORD *)(v1 + 920) = v53;
    *(_BYTE *)(v1 + 928) = v54 != 0;
    *(_BYTE *)(v1 + 304898) = v55 != 0;
    v20 = 1;
    if ( v52 < 2 )
      v20 = v52;
    *(_DWORD *)(v1 + 1376) = v20;
    v21 = v51;
    if ( v51 >= 4 )
    {
      if ( v51 > 0x400 )
      {
        v21 = 1024;
        v51 = 1024;
      }
    }
    else
    {
      v21 = 4;
      v51 = 4;
    }
    *(_DWORD *)(v1 + 1380) = v21;
    *(_DWORD *)(v1 + 1664) = v56;
    *(_DWORD *)(v1 + 1680) = v57;
    *(_BYTE *)(v1 + 304897) = v58 == 1;
    *(_BYTE *)(v1 + 304952) = v59 != 0;
    *(_BYTE *)(v1 + 304953) = v60 != 0;
    if ( v61 )
      *(_DWORD *)(v1 + 305664) = v61;
    if ( v62 )
      *(_DWORD *)(v1 + 305668) = v62;
    if ( !g_IsInternalRelease && !g_OSTestSigningEnabled )
    {
      g_bDbgForceUsb4MonitorSupport = 0;
      g_bDbgTreatUsb4MonitorAsNormal = 0;
      g_DbgUsb4MonitorPowerOnDelayInSeconds = 0;
    }
    *(_BYTE *)(v1 + 305736) = v63 != 0;
    *(_DWORD *)(v1 + 305944) = v64;
    DXGGLOBAL::SetNodeUsageTelemetryTimer((DXGGLOBAL *)v1);
    *(_BYTE *)(v1 + 305952) = v65 != 0;
  }
  *(_DWORD *)(v1 + 912) = 0;
  *(_OWORD *)v273 = *(_OWORD *)L"\\REGISTRY\\MACHINE\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  v66 = 0;
  *(_OWORD *)&v273[32] = *(_OWORD *)L"E\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  *(_QWORD *)&v84.Length = 9830548;
  *(_OWORD *)&v273[16] = *(_OWORD *)L"Y\\MACHINE\\System\\ControlSet001\\Control\\Terminal Server\\WinStations";
  *(_QWORD *)&v83.Length = 2228256;
  *(_OWORD *)&v273[64] = *(_OWORD *)L"Set001\\Control\\Terminal Server\\WinStations";
  *(_OWORD *)&v273[48] = *(_OWORD *)L"\\ControlSet001\\Control\\Terminal Server\\WinStations";
  v274 = *(_OWORD *)L"erminal Server\\WinStations";
  v276[0] = *(_OWORD *)L"inStations";
  *(_QWORD *)((char *)v276 + 14) = *(_QWORD *)L"ons";
  v84.Buffer = (wchar_t *)v273;
  *(_OWORD *)&v273[80] = *(_OWORD *)L"ontrol\\Terminal Server\\WinStations";
  v278 = aDwmframeinterv[16];
  v275 = *(_OWORD *)L"Server\\WinStations";
  v83.Buffer = (wchar_t *)v277;
  v277[0] = *(_OWORD *)L"DWMFRAMEINTERVAL";
  v277[1] = *(_OWORD *)L"INTERVAL";
  if ( ReadRegistryDwordKeyValue(&v84, &v83, &v66) >= 0 && v66 )
    *(_DWORD *)(v1 + 305216) = v66;
  DxgkSharedObjectTypes = CreateDxgkSharedObjectTypes(v22);
  v13 = DxgkSharedObjectTypes;
  if ( DxgkSharedObjectTypes < 0 )
  {
    WdLogSingleEntry1(3, DxgkSharedObjectTypes);
    WdLogGlobalForLineNumber = 2179;
    return v13;
  }
  v24 = v48;
  if ( !v48 || ((v48 - 1) & v48) != 0 )
  {
    v24 = v67;
    v48 = v67;
  }
  v25 = v50;
  if ( !v50 || ((v50 - 1) & v50) != 0 )
  {
    v25 = v68;
    v50 = v68;
  }
  if ( !g_OSTestSigningEnabled )
  {
    if ( v46 < 0x1000 || v46 * v24 > 0x1000000 )
    {
      v46 = 0x1000000;
      v48 = 1;
    }
    if ( v47 < 0x1000 || v47 * v25 > 0x1000000 )
    {
      v47 = 0x1000000;
      v50 = 1;
    }
  }
  if ( v49 > 0xE10 )
    v49 = 3600;
  v26 = (-(__int64)(g_IsInternalReleaseOrDbg != 0) & 0xFFFFFFFFFFFFFF40uLL) + 256;
  v27 = operator new(112, 1265072196, v26);
  if ( v27 )
    v28 = DXGDIAGNOSTICS::DXGDIAGNOSTICS(v27, v46, v48, v26, v49);
  else
    v28 = 0;
  *(_QWORD *)(v1 + 968) = v28;
  v29 = operator new(112, 1265072196, v26);
  if ( v29 )
  {
    Flags[0] = v49;
    v30 = DXGDIAGNOSTICS::DXGDIAGNOSTICS(v29, v47, v50, v26, *(_QWORD *)Flags);
  }
  else
  {
    v30 = 0;
  }
  *(_QWORD *)(v1 + 976) = v30;
  if ( !*(_QWORD *)(v1 + 968) )
  {
    WdLogSingleEntry1(6, v46);
    WdLogGlobalForLineNumber = 2233;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for internal diagnostics buffers (SmallInternalDiagnosticsSize = 0x%I64x).",
      v46,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  if ( !v30 )
  {
    WdLogSingleEntry1(6, v47);
    WdLogGlobalForLineNumber = 2239;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for external diagnostics buffers (SmallExternalDiagnosticsSize = 0x%I64x).",
      v47,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v31 = (DXGSESSIONMGR *)operator new(448, 1265072196, 64);
  if ( v31 )
    v32 = DXGSESSIONMGR::DXGSESSIONMGR(v31);
  else
    v32 = 0;
  *(_QWORD *)(v1 + 984) = v32;
  if ( !v32 )
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
  v33 = *(_DWORD *)(v1 + 1380);
  v34 = (unsigned int)(v33 + 31) >> 5;
  v35 = 4LL * ((unsigned int)v34 + ((unsigned int)(1055 - v33) >> 5));
  if ( !is_mul_ok((unsigned int)v34 + ((unsigned int)(1055 - v33) >> 5), 4u) )
    v35 = -1;
  v36 = (ULONG *)operator new[](v35, 0x4B677844u, 256);
  *(_QWORD *)(v1 + 904) = v36;
  if ( !v36 )
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
  RtlInitializeBitMap((PRTL_BITMAP)(v1 + 872), v36, *(_DWORD *)(v1 + 1380));
  RtlInitializeBitMap((PRTL_BITMAP)(v1 + 888), (PULONG)(*(_QWORD *)(v1 + 904) + 4 * v34), 1024 - *(_DWORD *)(v1 + 1380));
  if ( (int)DXGPROCESS::CreateDxgProcess((struct DXGPROCESS **)(v1 + 1384), 0, 0, 0, 0) < 0 )
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
  v37 = operator new(640, 1265072196, 256);
  v38 = (_BYTE *)v37;
  if ( v37 )
  {
    *(_BYTE *)v37 = 1;
    *(_QWORD *)(v37 + 16) = 0;
    *(_QWORD *)(v37 + 24) = 0;
    *(_QWORD *)(v37 + 32) = 0;
    *(_DWORD *)(v37 + 40) = 0;
    *(_DWORD *)(v37 + 44) = 69;
    *(_DWORD *)(v37 + 48) = 1;
    *(_DWORD *)(v37 + 632) = 0;
    memset((void *)(v37 + 56), 0, 0x240u);
    *v38 = 0;
  }
  else
  {
    v38 = 0;
  }
  *(_QWORD *)(v1 + 1480) = v38;
  if ( !v38 )
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
  v39 = ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
  if ( v39 >= 0 )
  {
    if ( OutputBuffer[0] )
      DXGGLOBAL::SubscribeWNFForCSAccounting((DXGGLOBAL *)v1);
  }
  else
  {
    v40 = v39;
    WdLogSingleEntry1(2, v39);
    WdLogGlobalForLineNumber = 2314;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to get the platformInformation. Status : 0x%I64x",
      v40,
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
  v41 = PoRegisterPowerSettingCallback(
          0,
          &GUID_ADVANCED_COLOR_QUALITY_BIAS,
          DXGGLOBAL::AdvancedColorPowerSettingsCallback,
          (PVOID)v1,
          0);
  v7 = v41;
  if ( v41 < 0 )
  {
    WdLogSingleEntry1(2, v41);
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
  v42 = PoRegisterPowerSettingCallback(0, &GUID_ACDC_POWER_SOURCE, DXGGLOBAL::AcDcPowerSourceCallback, (PVOID)v1, 0);
  v43 = v42;
  if ( v42 >= 0 )
    return RegisterDxgKernelProcessExtensions();
  WdLogSingleEntry1(2, v42);
  WdLogGlobalForLineNumber = 2361;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"PoRegisterPowerSettingCallback for GUID_ACDC_POWER_SOURCE failed with status:0x%I64x",
    v43,
    0,
    0,
    0,
    0);
  return (unsigned int)v43;
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
