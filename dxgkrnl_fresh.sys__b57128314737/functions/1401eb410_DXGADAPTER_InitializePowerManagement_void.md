# DXGADAPTER::InitializePowerManagement(void)

- ea: `0x1401eb410`
- end: `0x1401ed902`
- name: `?InitializePowerManagement@DXGADAPTER@@AEAAJXZ`
- size: `9458`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1401c6fe0`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001a56c`
- `0x14001b5d8`
- `0x14001b9c0`
- `0x14001bffc`
- `0x14001d884`
- `0x14002eec0`
- `0x14002ff90`
- `0x140033d80`
- `0x1400347b8`
- `0x140068778`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1401e93fc`
- `0x1401eb410`
- `0x1401f75a8`
- `0x1401fe18c`
- `0x1402a139c`
- `0x14035fa08`
- `0x1403d5270`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1401ece7a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed42a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed637`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed721`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ece7a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed42a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed637`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ed721`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed203`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed6da`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed6f4`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed70e`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed203`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed6da`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed6f4`
- `ntoskrnl!KeInitializeEvent` at `0x1401ed70e`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401eb6dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401ec0dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401ec1d3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401eb6dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401ec0dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401ec1d3`
- `ntoskrnl!PoFxRegisterDevice` at `0x1401ed1a1`
- `ntoskrnl!PoFxRegisterDevice` at `0x1401ed1a1`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401ed224`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401ed224`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x1401ed6a0`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x1401ed6a0`
- `ntoskrnl!InitializeSListHead` at `0x1401ed745`
- `ntoskrnl!InitializeSListHead` at `0x1401ed745`
- `ntoskrnl!PsCreateSystemThread` at `0x1401ed7de`
- `ntoskrnl!PsCreateSystemThread` at `0x1401ed7de`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1401ed8bc`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1401ed8bc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ed76f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ed76f`
- `watchdog!WdLogSingleEntry4` at `0x1401ed07d`
- `watchdog!WdLogSingleEntry4` at `0x1401ed07d`
- `watchdog!WdLogSingleEntry2` at `0x1401ec2ec`
- `watchdog!WdLogSingleEntry2` at `0x1401ec880`
- `watchdog!WdLogSingleEntry2` at `0x1401eca37`
- `watchdog!WdLogSingleEntry2` at `0x1401eca9d`
- `watchdog!WdLogSingleEntry2` at `0x1401ecade`
- `watchdog!WdLogSingleEntry2` at `0x1401ecb45`
- `watchdog!WdLogSingleEntry2` at `0x1401ecb8b`
- `watchdog!WdLogSingleEntry2` at `0x1401ecc18`
- `watchdog!WdLogSingleEntry2` at `0x1401ecfe9`
- `watchdog!WdLogSingleEntry2` at `0x1401ed102`
- `watchdog!WdLogSingleEntry2` at `0x1401ed16b`
- `watchdog!WdLogSingleEntry2` at `0x1401ed7fc`
- `watchdog!WdLogSingleEntry2` at `0x1401ed85e`
- `watchdog!WdLogSingleEntry2` at `0x1401ec2ec`
- `watchdog!WdLogSingleEntry2` at `0x1401ec880`
- `watchdog!WdLogSingleEntry2` at `0x1401eca37`
- `watchdog!WdLogSingleEntry2` at `0x1401eca9d`
- `watchdog!WdLogSingleEntry2` at `0x1401ecade`
- `watchdog!WdLogSingleEntry2` at `0x1401ecb45`
- `watchdog!WdLogSingleEntry2` at `0x1401ecb8b`
- `watchdog!WdLogSingleEntry2` at `0x1401ecc18`
- `watchdog!WdLogSingleEntry2` at `0x1401ecfe9`
- `watchdog!WdLogSingleEntry2` at `0x1401ed102`
- `watchdog!WdLogSingleEntry2` at `0x1401ed16b`
- `watchdog!WdLogSingleEntry2` at `0x1401ed7fc`
- `watchdog!WdLogSingleEntry2` at `0x1401ed85e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401ecea3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401ecea3`
- `watchdog!WdLogSingleEntry3` at `0x1401ecbd1`
- `watchdog!WdLogSingleEntry3` at `0x1401ecf9d`
- `watchdog!WdLogSingleEntry3` at `0x1401ecbd1`
- `watchdog!WdLogSingleEntry3` at `0x1401ecf9d`
- `watchdog!WdLogSingleEntry0` at `0x1401eb47e`
- `watchdog!WdLogSingleEntry0` at `0x1401ec364`
- `watchdog!WdLogSingleEntry0` at `0x1401eb47e`
- `watchdog!WdLogSingleEntry0` at `0x1401ec364`
- `watchdog!WdLogSingleEntry1` at `0x1401ec392`
- `watchdog!WdLogSingleEntry1` at `0x1401ec426`
- `watchdog!WdLogSingleEntry1` at `0x1401ec49f`
- `watchdog!WdLogSingleEntry1` at `0x1401ec721`
- `watchdog!WdLogSingleEntry1` at `0x1401ec769`
- `watchdog!WdLogSingleEntry1` at `0x1401ec967`
- `watchdog!WdLogSingleEntry1` at `0x1401ec9c0`
- `watchdog!WdLogSingleEntry1` at `0x1401ec9e5`
- `watchdog!WdLogSingleEntry1` at `0x1401eca0a`
- `watchdog!WdLogSingleEntry1` at `0x1401ecb1a`
- `watchdog!WdLogSingleEntry1` at `0x1401ecd39`
- `watchdog!WdLogSingleEntry1` at `0x1401ed032`
- `watchdog!WdLogSingleEntry1` at `0x1401ed1bc`
- `watchdog!WdLogSingleEntry1` at `0x1401ec392`
- `watchdog!WdLogSingleEntry1` at `0x1401ec426`
- `watchdog!WdLogSingleEntry1` at `0x1401ec49f`
- `watchdog!WdLogSingleEntry1` at `0x1401ec721`
- `watchdog!WdLogSingleEntry1` at `0x1401ec769`
- `watchdog!WdLogSingleEntry1` at `0x1401ec967`
- `watchdog!WdLogSingleEntry1` at `0x1401ec9c0`
- `watchdog!WdLogSingleEntry1` at `0x1401ec9e5`
- `watchdog!WdLogSingleEntry1` at `0x1401eca0a`
- `watchdog!WdLogSingleEntry1` at `0x1401ecb1a`
- `watchdog!WdLogSingleEntry1` at `0x1401ecd39`
- `watchdog!WdLogSingleEntry1` at `0x1401ed032`
- `watchdog!WdLogSingleEntry1` at `0x1401ed1bc`

## string_xrefs

- `0x1401eb77a`: `DefaultExpectedResidency`
- `0x1401ec3a3`: `Miniport returned invalid number of power components:0x%I64x`
- `0x1401ec432`: `Adapter 0x%I64x: Out of memory allocating m_pPowerComponents`
- `0x1401ecc36`: `Miniport failed QueryAdapterInfo(DXGKQAITYPE_POWERCOMPONENTINFO). Component: 0x%I64x, Status: 0x%I64x`
- `0x1401ecbed`: `Miniport returned invalid number of F states for component:0x%I64x 0x%I64x`
- `0x1401ecba9`: `Reserved flags are not zero. Component:0x%I64x`
- `0x1401eca16`: `Power component ActiveInD3 flag can only be used with DXGK_POWER_COMPONENT_MEMORY and DXGK_POWER_COMPONENT_SHARED. Component:0x%I64x`
- `0x1401ec9f1`: `F state count must be 2 when the ActiveInD3 flag is set. Component:0x%I64x`
- `0x1401ec9cc`: `TransitionLatency for the F1 state must be 0 when the ActiveInD3 flag is set. Component:0x%I64x`
- `0x1401ec973`: `Provider count must be 0 when the ActiveInD3 flag is set. Component:0x%I64x`
- `0x1401ecb63`: `Invalid component ProviderCount. Component:0x%I64x`
- `0x1401ec775`: `F state count for the DXGK_POWER_COMPONENT_D3_TRANSITION component must be 1 or 2. Component:0x%I64x`
- `0x1401ecb26`: `DXGK_POWER_COMPONENT_MEMORY_REFRESH component is defined second time. Component:0x%I64x`
- `0x1401eca48`: `TransitionLatency and ResidencyRequirement must be zero for the F0 state. Component:0x%I64x`
- `0x1401ec891`: `NominalPower must not be zero for the F0 state. Component:0x%I64x`
- `0x1401ecaae`: `NominalPower must be decreasing for higher F states. Component:0x%I64x`
- `0x1401ecaef`: `TransitionLatency must be increasing for higher F states. Component:0x%I64x`
- `0x1401ed043`: `P-State StateCount cannot be larger than DXGK_MAX_P_STATES. Component:0x%I64x`
- `0x1401ed007`: `P-State cannot specify 0 operating frequency. Component:0x%I64x, P-State:0x%I64x`
- `0x1401ecfbb`: `P-States must have monotonically decreasing operating frequency. Component:0x%I64x, P-State1:0x%I64x, P-State2:0x%I64x`
- `0x1401ed808`: `InitializePowerManagement failed to create worker thread for display adapter:0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGADAPTER::InitializePowerManagement(DXGADAPTER *this, __int64 a2, __int64 a3)
{
  _BYTE *v3; // rbx
  bool v5; // cc
  int v6; // r8d
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // rsi
  unsigned int v10; // r13d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  unsigned int NumDifferentPhysicalAdapters; // r15d
  __int64 v15; // rax
  DXGADAPTER *v16; // rcx
  int AdapterInfo; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  const wchar_t *v21; // r9
  __int64 v22; // rax
  char *v23; // r14
  unsigned int v24; // ecx
  unsigned int v25; // ebx
  unsigned int v26; // eax
  __int64 v27; // r8
  unsigned int v28; // edx
  __int64 v29; // r15
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  int v33; // eax
  __int16 v34; // dx
  int v35; // ecx
  __int64 v36; // rsi
  __int64 v37; // rbx
  unsigned int v38; // eax
  int v39; // eax
  const wchar_t *v40; // r9
  void *v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r11
  unsigned int v44; // r9d
  unsigned int v45; // r10d
  unsigned int v46; // ecx
  unsigned __int64 v47; // r10
  unsigned __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  unsigned int v51; // edx
  unsigned int i; // r8d
  __int64 v53; // r10
  __int64 v54; // r9
  unsigned int v55; // edx
  __int64 j; // rax
  __int64 v57; // rbx
  int v58; // eax
  __int64 v59; // rsi
  int v60; // eax
  __int64 v61; // rax
  unsigned int k; // ecx
  __int64 v63; // rdx
  __int64 v64; // rax
  void *v65; // rcx
  unsigned int v66; // eax
  unsigned int v67; // edx
  __int64 v68; // r8
  __int64 v69; // r10
  __int64 v70; // rax
  unsigned int v71; // ebx
  __int64 v72; // r9
  unsigned int m; // ecx
  __int64 v74; // r10
  __int64 v75; // rsi
  unsigned int v76; // r11d
  __int64 v77; // r15
  __int64 v78; // rbx
  __int64 v79; // rbx
  __int64 v80; // rbx
  ADAPTER_RENDER *v81; // rcx
  int v82; // eax
  const wchar_t *v83; // r9
  ADAPTER_DISPLAY *v84; // rcx
  int v85; // eax
  __int64 v86; // r15
  const wchar_t *v87; // r9
  int v88; // eax
  ULONG TimeIncrement; // eax
  __int64 v90; // rcx
  unsigned __int64 v91; // r9
  __int64 v92; // rax
  unsigned __int64 v93; // rtt
  __int64 v94; // rdx
  __int64 v95; // rax
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 v103; // rax
  unsigned __int64 v104; // rtt
  __int64 v105; // rax
  unsigned __int64 v106; // rtt
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rax
  unsigned __int64 v110; // rtt
  __int64 v111; // rax
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rcx
  __int64 v117; // rax
  __int64 v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 v125; // rax
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rsi
  __int64 v130; // rbx
  __int64 v131; // rdx
  __int64 v132; // r15
  int v133; // ecx
  int v134; // ecx
  int v135; // ecx
  int v136; // ecx
  int v137; // ecx
  int v138; // ecx
  DXGADAPTER *v139; // rcx
  unsigned int v140; // edx
  unsigned __int64 v141; // r8
  DXGADAPTER **v142; // rcx
  __int64 v143; // rax
  DXGADAPTER **v144; // rcx
  unsigned __int64 v145; // rdx
  unsigned int v146; // r9d
  unsigned int n; // r8d
  unsigned __int64 v148; // rax
  unsigned int ii; // ecx
  unsigned int v150; // edx
  unsigned __int64 v151; // r8
  __int64 v152; // rcx
  __int64 v153; // rax
  __int64 v154; // r8
  __int64 v155; // rbx
  NTSTATUS v156; // eax
  int v157; // eax
  __int64 StartRoutine; // [rsp+28h] [rbp-D8h]
  char v159; // [rsp+50h] [rbp-B0h]
  int v160; // [rsp+54h] [rbp-ACh] BYREF
  int v161; // [rsp+58h] [rbp-A8h] BYREF
  int v162; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v163; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v164; // [rsp+68h] [rbp-98h] BYREF
  BOOL v165; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v166; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v167; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v168; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v169; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v170; // [rsp+80h] [rbp-80h]
  unsigned int v171; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v172; // [rsp+88h] [rbp-78h] BYREF
  void *v173; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v174; // [rsp+98h] [rbp-68h] BYREF
  int v175; // [rsp+9Ch] [rbp-64h] BYREF
  int v176; // [rsp+A0h] [rbp-60h] BYREF
  int v177; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v178; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v179; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v180; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v181; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v182; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v183; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v184; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v185; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v186; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v187; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v188; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v189; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned int v190; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v191; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int v192; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v193; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v194; // [rsp+E8h] [rbp-18h] BYREF
  int v195; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v196; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v197; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v198; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v199; // [rsp+FCh] [rbp-4h] BYREF
  unsigned int v200; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v201; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v202; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v203; // [rsp+10Ch] [rbp+Ch] BYREF
  int v204; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v205; // [rsp+114h] [rbp+14h] BYREF
  int v206; // [rsp+118h] [rbp+18h] BYREF
  int v207; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v208; // [rsp+120h] [rbp+20h] BYREF
  int v209; // [rsp+124h] [rbp+24h] BYREF
  int v210; // [rsp+128h] [rbp+28h] BYREF
  int v211; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v212; // [rsp+130h] [rbp+30h] BYREF
  int v213; // [rsp+134h] [rbp+34h] BYREF
  int v214; // [rsp+138h] [rbp+38h] BYREF
  int v215; // [rsp+13Ch] [rbp+3Ch] BYREF
  int v216; // [rsp+140h] [rbp+40h] BYREF
  int v217; // [rsp+144h] [rbp+44h] BYREF
  int v218; // [rsp+148h] [rbp+48h] BYREF
  int v219; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v220; // [rsp+150h] [rbp+50h] BYREF
  int v221; // [rsp+154h] [rbp+54h] BYREF
  int v222; // [rsp+158h] [rbp+58h] BYREF
  int v223; // [rsp+15Ch] [rbp+5Ch] BYREF
  int v224; // [rsp+160h] [rbp+60h] BYREF
  int v225; // [rsp+164h] [rbp+64h] BYREF
  int v226; // [rsp+168h] [rbp+68h] BYREF
  int v227; // [rsp+16Ch] [rbp+6Ch] BYREF
  int v228; // [rsp+170h] [rbp+70h] BYREF
  int v229; // [rsp+174h] [rbp+74h] BYREF
  int v230; // [rsp+178h] [rbp+78h] BYREF
  int v231; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v232; // [rsp+180h] [rbp+80h] BYREF
  int v233; // [rsp+184h] [rbp+84h] BYREF
  int v234; // [rsp+188h] [rbp+88h] BYREF
  int v235; // [rsp+18Ch] [rbp+8Ch] BYREF
  int v236; // [rsp+190h] [rbp+90h] BYREF
  int v237; // [rsp+194h] [rbp+94h] BYREF
  int v238; // [rsp+198h] [rbp+98h] BYREF
  int v239; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v240; // [rsp+1A0h] [rbp+A0h] BYREF
  int v241; // [rsp+1A4h] [rbp+A4h] BYREF
  int v242; // [rsp+1A8h] [rbp+A8h] BYREF
  int v243; // [rsp+1ACh] [rbp+ACh] BYREF
  __int64 v244; // [rsp+1B0h] [rbp+B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v246; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v247; // [rsp+218h] [rbp+118h]
  __int64 v248; // [rsp+220h] [rbp+120h] BYREF
  int v249; // [rsp+228h] [rbp+128h]
  const wchar_t *v250; // [rsp+230h] [rbp+130h]
  BOOL *v251; // [rsp+238h] [rbp+138h]
  int v252; // [rsp+240h] [rbp+140h]
  int *v253; // [rsp+248h] [rbp+148h]
  int v254; // [rsp+250h] [rbp+150h]
  __int64 v255; // [rsp+258h] [rbp+158h]
  int v256; // [rsp+260h] [rbp+160h]
  __int64 v257; // [rsp+268h] [rbp+168h]
  __int128 v258; // [rsp+270h] [rbp+170h]
  __int128 v259; // [rsp+280h] [rbp+180h]
  __int64 v260; // [rsp+290h] [rbp+190h] BYREF
  int v261; // [rsp+298h] [rbp+198h]
  const wchar_t *v262; // [rsp+2A0h] [rbp+1A0h]
  int *v263; // [rsp+2A8h] [rbp+1A8h]
  int v264; // [rsp+2B0h] [rbp+1B0h]
  int *v265; // [rsp+2B8h] [rbp+1B8h]
  int v266; // [rsp+2C0h] [rbp+1C0h]
  __int64 v267; // [rsp+2C8h] [rbp+1C8h]
  int v268; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v269; // [rsp+2D8h] [rbp+1D8h]
  int *v270; // [rsp+2E0h] [rbp+1E0h]
  int v271; // [rsp+2E8h] [rbp+1E8h]
  int *v272; // [rsp+2F0h] [rbp+1F0h]
  int v273; // [rsp+2F8h] [rbp+1F8h]
  __int64 v274; // [rsp+300h] [rbp+200h]
  int v275; // [rsp+308h] [rbp+208h]
  const wchar_t *v276; // [rsp+310h] [rbp+210h]
  unsigned int *v277; // [rsp+318h] [rbp+218h]
  int v278; // [rsp+320h] [rbp+220h]
  int *v279; // [rsp+328h] [rbp+228h]
  int v280; // [rsp+330h] [rbp+230h]
  __int64 v281; // [rsp+338h] [rbp+238h]
  int v282; // [rsp+340h] [rbp+240h]
  const wchar_t *v283; // [rsp+348h] [rbp+248h]
  unsigned int *v284; // [rsp+350h] [rbp+250h]
  int v285; // [rsp+358h] [rbp+258h]
  int *v286; // [rsp+360h] [rbp+260h]
  int v287; // [rsp+368h] [rbp+268h]
  __int64 v288; // [rsp+370h] [rbp+270h]
  int v289; // [rsp+378h] [rbp+278h]
  const wchar_t *v290; // [rsp+380h] [rbp+280h]
  unsigned int *v291; // [rsp+388h] [rbp+288h]
  int v292; // [rsp+390h] [rbp+290h]
  int *v293; // [rsp+398h] [rbp+298h]
  int v294; // [rsp+3A0h] [rbp+2A0h]
  __int64 v295; // [rsp+3A8h] [rbp+2A8h]
  int v296; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v297; // [rsp+3B8h] [rbp+2B8h]
  unsigned int *v298; // [rsp+3C0h] [rbp+2C0h]
  int v299; // [rsp+3C8h] [rbp+2C8h]
  int *v300; // [rsp+3D0h] [rbp+2D0h]
  int v301; // [rsp+3D8h] [rbp+2D8h]
  __int64 v302; // [rsp+3E0h] [rbp+2E0h]
  int v303; // [rsp+3E8h] [rbp+2E8h]
  const wchar_t *v304; // [rsp+3F0h] [rbp+2F0h]
  unsigned int *v305; // [rsp+3F8h] [rbp+2F8h]
  int v306; // [rsp+400h] [rbp+300h]
  int *v307; // [rsp+408h] [rbp+308h]
  int v308; // [rsp+410h] [rbp+310h]
  __int64 v309; // [rsp+418h] [rbp+318h]
  int v310; // [rsp+420h] [rbp+320h]
  const wchar_t *v311; // [rsp+428h] [rbp+328h]
  unsigned int *v312; // [rsp+430h] [rbp+330h]
  int v313; // [rsp+438h] [rbp+338h]
  int *v314; // [rsp+440h] [rbp+340h]
  int v315; // [rsp+448h] [rbp+348h]
  __int64 v316; // [rsp+450h] [rbp+350h]
  int v317; // [rsp+458h] [rbp+358h]
  const wchar_t *v318; // [rsp+460h] [rbp+360h]
  unsigned int *v319; // [rsp+468h] [rbp+368h]
  int v320; // [rsp+470h] [rbp+370h]
  int *v321; // [rsp+478h] [rbp+378h]
  int v322; // [rsp+480h] [rbp+380h]
  __int64 v323; // [rsp+488h] [rbp+388h]
  int v324; // [rsp+490h] [rbp+390h]
  const wchar_t *v325; // [rsp+498h] [rbp+398h]
  unsigned int *v326; // [rsp+4A0h] [rbp+3A0h]
  int v327; // [rsp+4A8h] [rbp+3A8h]
  int *v328; // [rsp+4B0h] [rbp+3B0h]
  int v329; // [rsp+4B8h] [rbp+3B8h]
  __int64 v330; // [rsp+4C0h] [rbp+3C0h]
  int v331; // [rsp+4C8h] [rbp+3C8h]
  const wchar_t *v332; // [rsp+4D0h] [rbp+3D0h]
  int *v333; // [rsp+4D8h] [rbp+3D8h]
  int v334; // [rsp+4E0h] [rbp+3E0h]
  int *v335; // [rsp+4E8h] [rbp+3E8h]
  int v336; // [rsp+4F0h] [rbp+3F0h]
  __int64 v337; // [rsp+4F8h] [rbp+3F8h]
  int v338; // [rsp+500h] [rbp+400h]
  const wchar_t *v339; // [rsp+508h] [rbp+408h]
  unsigned int *v340; // [rsp+510h] [rbp+410h]
  int v341; // [rsp+518h] [rbp+418h]
  int *v342; // [rsp+520h] [rbp+420h]
  int v343; // [rsp+528h] [rbp+428h]
  __int64 v344; // [rsp+530h] [rbp+430h]
  int v345; // [rsp+538h] [rbp+438h]
  const wchar_t *v346; // [rsp+540h] [rbp+440h]
  int *v347; // [rsp+548h] [rbp+448h]
  int v348; // [rsp+550h] [rbp+450h]
  int *v349; // [rsp+558h] [rbp+458h]
  int v350; // [rsp+560h] [rbp+460h]
  __int64 v351; // [rsp+568h] [rbp+468h]
  int v352; // [rsp+570h] [rbp+470h]
  const wchar_t *v353; // [rsp+578h] [rbp+478h]
  unsigned int *v354; // [rsp+580h] [rbp+480h]
  int v355; // [rsp+588h] [rbp+488h]
  int *v356; // [rsp+590h] [rbp+490h]
  int v357; // [rsp+598h] [rbp+498h]
  __int64 v358; // [rsp+5A0h] [rbp+4A0h]
  int v359; // [rsp+5A8h] [rbp+4A8h]
  const wchar_t *v360; // [rsp+5B0h] [rbp+4B0h]
  unsigned int *v361; // [rsp+5B8h] [rbp+4B8h]
  int v362; // [rsp+5C0h] [rbp+4C0h]
  int *v363; // [rsp+5C8h] [rbp+4C8h]
  int v364; // [rsp+5D0h] [rbp+4D0h]
  __int64 v365; // [rsp+5D8h] [rbp+4D8h]
  int v366; // [rsp+5E0h] [rbp+4E0h]
  const wchar_t *v367; // [rsp+5E8h] [rbp+4E8h]
  unsigned int *v368; // [rsp+5F0h] [rbp+4F0h]
  int v369; // [rsp+5F8h] [rbp+4F8h]
  int *v370; // [rsp+600h] [rbp+500h]
  int v371; // [rsp+608h] [rbp+508h]
  __int64 v372; // [rsp+610h] [rbp+510h]
  int v373; // [rsp+618h] [rbp+518h]
  const wchar_t *v374; // [rsp+620h] [rbp+520h]
  unsigned int *v375; // [rsp+628h] [rbp+528h]
  int v376; // [rsp+630h] [rbp+530h]
  int *v377; // [rsp+638h] [rbp+538h]
  int v378; // [rsp+640h] [rbp+540h]
  __int64 v379; // [rsp+648h] [rbp+548h]
  int v380; // [rsp+650h] [rbp+550h]
  const wchar_t *v381; // [rsp+658h] [rbp+558h]
  unsigned int *v382; // [rsp+660h] [rbp+560h]
  int v383; // [rsp+668h] [rbp+568h]
  int *v384; // [rsp+670h] [rbp+570h]
  int v385; // [rsp+678h] [rbp+578h]
  __int64 v386; // [rsp+680h] [rbp+580h]
  int v387; // [rsp+688h] [rbp+588h]
  const wchar_t *v388; // [rsp+690h] [rbp+590h]
  unsigned int *v389; // [rsp+698h] [rbp+598h]
  int v390; // [rsp+6A0h] [rbp+5A0h]
  int *v391; // [rsp+6A8h] [rbp+5A8h]
  int v392; // [rsp+6B0h] [rbp+5B0h]
  __int64 v393; // [rsp+6B8h] [rbp+5B8h]
  int v394; // [rsp+6C0h] [rbp+5C0h]
  const wchar_t *v395; // [rsp+6C8h] [rbp+5C8h]
  unsigned int *v396; // [rsp+6D0h] [rbp+5D0h]
  int v397; // [rsp+6D8h] [rbp+5D8h]
  int *v398; // [rsp+6E0h] [rbp+5E0h]
  int v399; // [rsp+6E8h] [rbp+5E8h]
  __int64 v400; // [rsp+6F0h] [rbp+5F0h]
  int v401; // [rsp+6F8h] [rbp+5F8h]
  const wchar_t *v402; // [rsp+700h] [rbp+600h]
  unsigned int *v403; // [rsp+708h] [rbp+608h]
  int v404; // [rsp+710h] [rbp+610h]
  int *v405; // [rsp+718h] [rbp+618h]
  int v406; // [rsp+720h] [rbp+620h]
  __int64 v407; // [rsp+728h] [rbp+628h]
  int v408; // [rsp+730h] [rbp+630h]
  const wchar_t *v409; // [rsp+738h] [rbp+638h]
  int *v410; // [rsp+740h] [rbp+640h]
  int v411; // [rsp+748h] [rbp+648h]
  int *v412; // [rsp+750h] [rbp+650h]
  int v413; // [rsp+758h] [rbp+658h]
  __int64 v414; // [rsp+760h] [rbp+660h]
  int v415; // [rsp+768h] [rbp+668h]
  const wchar_t *v416; // [rsp+770h] [rbp+670h]
  int *v417; // [rsp+778h] [rbp+678h]
  int v418; // [rsp+780h] [rbp+680h]
  int *v419; // [rsp+788h] [rbp+688h]
  int v420; // [rsp+790h] [rbp+690h]
  __int64 v421; // [rsp+798h] [rbp+698h]
  int v422; // [rsp+7A0h] [rbp+6A0h]
  const wchar_t *v423; // [rsp+7A8h] [rbp+6A8h]
  int *v424; // [rsp+7B0h] [rbp+6B0h]
  int v425; // [rsp+7B8h] [rbp+6B8h]
  int *v426; // [rsp+7C0h] [rbp+6C0h]
  int v427; // [rsp+7C8h] [rbp+6C8h]
  __int64 v428; // [rsp+7D0h] [rbp+6D0h]
  int v429; // [rsp+7D8h] [rbp+6D8h]
  const wchar_t *v430; // [rsp+7E0h] [rbp+6E0h]
  unsigned int *v431; // [rsp+7E8h] [rbp+6E8h]
  int v432; // [rsp+7F0h] [rbp+6F0h]
  int *v433; // [rsp+7F8h] [rbp+6F8h]
  int v434; // [rsp+800h] [rbp+700h]
  __int64 v435; // [rsp+808h] [rbp+708h]
  int v436; // [rsp+810h] [rbp+710h]
  const wchar_t *v437; // [rsp+818h] [rbp+718h]
  unsigned int *v438; // [rsp+820h] [rbp+720h]
  int v439; // [rsp+828h] [rbp+728h]
  int *v440; // [rsp+830h] [rbp+730h]
  int v441; // [rsp+838h] [rbp+738h]
  __int64 v442; // [rsp+840h] [rbp+740h]
  int v443; // [rsp+848h] [rbp+748h]
  const wchar_t *v444; // [rsp+850h] [rbp+750h]
  unsigned int *v445; // [rsp+858h] [rbp+758h]
  int v446; // [rsp+860h] [rbp+760h]
  int *v447; // [rsp+868h] [rbp+768h]
  int v448; // [rsp+870h] [rbp+770h]
  __int64 v449; // [rsp+878h] [rbp+778h]
  int v450; // [rsp+880h] [rbp+780h]
  const wchar_t *v451; // [rsp+888h] [rbp+788h]
  unsigned int *v452; // [rsp+890h] [rbp+790h]
  int v453; // [rsp+898h] [rbp+798h]
  int *v454; // [rsp+8A0h] [rbp+7A0h]
  int v455; // [rsp+8A8h] [rbp+7A8h]
  __int64 v456; // [rsp+8B0h] [rbp+7B0h]
  int v457; // [rsp+8B8h] [rbp+7B8h]
  const wchar_t *v458; // [rsp+8C0h] [rbp+7C0h]
  unsigned int *v459; // [rsp+8C8h] [rbp+7C8h]
  int v460; // [rsp+8D0h] [rbp+7D0h]
  int *v461; // [rsp+8D8h] [rbp+7D8h]
  int v462; // [rsp+8E0h] [rbp+7E0h]
  __int64 v463; // [rsp+8E8h] [rbp+7E8h]
  int v464; // [rsp+8F0h] [rbp+7F0h]
  const wchar_t *v465; // [rsp+8F8h] [rbp+7F8h]
  unsigned int *v466; // [rsp+900h] [rbp+800h]
  int v467; // [rsp+908h] [rbp+808h]
  int *v468; // [rsp+910h] [rbp+810h]
  int v469; // [rsp+918h] [rbp+818h]
  __int64 v470; // [rsp+920h] [rbp+820h]
  int v471; // [rsp+928h] [rbp+828h]
  const wchar_t *v472; // [rsp+930h] [rbp+830h]
  unsigned int *v473; // [rsp+938h] [rbp+838h]
  int v474; // [rsp+940h] [rbp+840h]
  int *v475; // [rsp+948h] [rbp+848h]
  int v476; // [rsp+950h] [rbp+850h]
  __int64 v477; // [rsp+958h] [rbp+858h]
  int v478; // [rsp+960h] [rbp+860h]
  const wchar_t *v479; // [rsp+968h] [rbp+868h]
  unsigned int *v480; // [rsp+970h] [rbp+870h]
  int v481; // [rsp+978h] [rbp+878h]
  int *v482; // [rsp+980h] [rbp+880h]
  int v483; // [rsp+988h] [rbp+888h]
  __int64 v484; // [rsp+990h] [rbp+890h]
  int v485; // [rsp+998h] [rbp+898h]
  const wchar_t *v486; // [rsp+9A0h] [rbp+8A0h]
  unsigned int *v487; // [rsp+9A8h] [rbp+8A8h]
  int v488; // [rsp+9B0h] [rbp+8B0h]
  int *v489; // [rsp+9B8h] [rbp+8B8h]
  int v490; // [rsp+9C0h] [rbp+8C0h]
  __int64 v491; // [rsp+9C8h] [rbp+8C8h]
  int v492; // [rsp+9D0h] [rbp+8D0h]
  const wchar_t *v493; // [rsp+9D8h] [rbp+8D8h]
  unsigned int *v494; // [rsp+9E0h] [rbp+8E0h]
  int v495; // [rsp+9E8h] [rbp+8E8h]
  int *v496; // [rsp+9F0h] [rbp+8F0h]
  int v497; // [rsp+9F8h] [rbp+8F8h]
  __int64 v498; // [rsp+A00h] [rbp+900h]
  int v499; // [rsp+A08h] [rbp+908h]
  const wchar_t *v500; // [rsp+A10h] [rbp+910h]
  unsigned int *v501; // [rsp+A18h] [rbp+918h]
  int v502; // [rsp+A20h] [rbp+920h]
  int *v503; // [rsp+A28h] [rbp+928h]
  int v504; // [rsp+A30h] [rbp+930h]
  __int64 v505; // [rsp+A38h] [rbp+938h]
  int v506; // [rsp+A40h] [rbp+940h]
  const wchar_t *v507; // [rsp+A48h] [rbp+948h]
  unsigned int *v508; // [rsp+A50h] [rbp+950h]
  int v509; // [rsp+A58h] [rbp+958h]
  int *v510; // [rsp+A60h] [rbp+960h]
  int v511; // [rsp+A68h] [rbp+968h]
  __int64 v512; // [rsp+A70h] [rbp+970h]
  int v513; // [rsp+A78h] [rbp+978h]
  const wchar_t *v514; // [rsp+A80h] [rbp+980h]
  unsigned int *v515; // [rsp+A88h] [rbp+988h]
  int v516; // [rsp+A90h] [rbp+990h]
  int *v517; // [rsp+A98h] [rbp+998h]
  int v518; // [rsp+AA0h] [rbp+9A0h]
  __int64 v519; // [rsp+AA8h] [rbp+9A8h]
  int v520; // [rsp+AB0h] [rbp+9B0h]
  const wchar_t *v521; // [rsp+AB8h] [rbp+9B8h]
  unsigned int *v522; // [rsp+AC0h] [rbp+9C0h]
  int v523; // [rsp+AC8h] [rbp+9C8h]
  int *v524; // [rsp+AD0h] [rbp+9D0h]
  int v525; // [rsp+AD8h] [rbp+9D8h]
  __int64 v526; // [rsp+AE0h] [rbp+9E0h]
  int v527; // [rsp+AE8h] [rbp+9E8h]
  const wchar_t *v528; // [rsp+AF0h] [rbp+9F0h]
  unsigned int *v529; // [rsp+AF8h] [rbp+9F8h]
  int v530; // [rsp+B00h] [rbp+A00h]
  int *v531; // [rsp+B08h] [rbp+A08h]
  int v532; // [rsp+B10h] [rbp+A10h]
  __int64 v533; // [rsp+B18h] [rbp+A18h]
  int v534; // [rsp+B20h] [rbp+A20h]
  __int64 v535; // [rsp+B28h] [rbp+A28h]
  __int128 v536; // [rsp+B30h] [rbp+A30h]
  __int128 v537; // [rsp+B40h] [rbp+A40h]
  _DWORD v538[64]; // [rsp+B50h] [rbp+A50h] BYREF
  unsigned __int16 v539[264]; // [rsp+C50h] [rbp+B50h] BYREF

  v3 = (char *)this + 3069;
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pt_EtwWriteTransfer(
      &DxgkControlGuid_Context,
      &Dxgk_PowerManagementSupport,
      a3,
      this,
      (unsigned __int8)*v3);
  if ( !*v3 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 4776;
    return 0;
  }
  v225 = 0;
  v242 = -1;
  v171 = -1;
  v243 = 2000;
  v208 = 35000;
  v180 = 35000;
  v172 = 2000;
  v210 = 50000;
  v183 = 50000;
  v211 = 100000;
  v184 = 100000;
  v216 = 300000;
  v202 = 300000;
  v217 = 17000;
  v201 = 17000;
  v212 = 200;
  v177 = 200;
  v213 = 200;
  v181 = 200;
  v215 = 100;
  v214 = 100;
  v218 = 25000;
  v203 = 25000;
  v220 = 300;
  v168 = 300;
  v221 = 700;
  v169 = 700;
  v222 = 900;
  v167 = 900;
  v223 = 500;
  v166 = 500;
  v229 = 140000;
  v190 = 140000;
  v230 = 200000;
  v192 = 200000;
  v231 = 250000;
  v193 = 250000;
  v232 = 250000;
  v194 = 250000;
  v209 = 2000;
  v182 = 2000;
  v219 = 2000;
  v185 = 2000;
  v233 = 10000;
  v187 = 10000;
  v206 = 80;
  v178 = 80;
  v207 = 15000;
  v179 = 15000;
  v224 = 3;
  v176 = 3;
  v204 = 0;
  v226 = 0;
  v175 = 0;
  v227 = 80;
  v186 = 80;
  v228 = 80000;
  v188 = 80000;
  v5 = *((_DWORD *)this + 783) < 2400;
  v234 = 60000;
  v189 = 60000;
  v235 = 60000;
  v191 = 60000;
  v237 = 30000;
  v196 = 30000;
  v240 = 30000;
  v199 = 30000;
  v241 = 80000;
  v205 = 80000;
  v236 = 15000;
  v200 = 15000;
  v238 = 80;
  v197 = 80;
  v239 = 15000;
  v198 = 15000;
  v195 = 1;
  v165 = 1;
  v160 = 1;
  v161 = 1;
  v164 = 0;
  v162 = 0;
  if ( v5 )
  {
    v250 = L"UseSelfRefreshVRAMInS3";
    v252 = 67108868;
    v248 = 0;
    v251 = &v165;
    v249 = 288;
    v253 = &v195;
    v254 = 4;
    v255 = 0;
    v256 = 0;
    v257 = 0;
    v258 = 0;
    v259 = 0;
    RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\Power", &v248, 0, 0);
  }
  else
  {
    v165 = (*((_DWORD *)this + 649) & 0x1000) == 0;
  }
  v260 = 0;
  v262 = L"EnableRuntimePowerManagement";
  v263 = &v161;
  v265 = &v160;
  v269 = L"DisableDevicePowerRequired";
  v270 = &v162;
  v272 = (int *)&v164;
  v276 = L"DefaultLatencyToleranceOther";
  v277 = &v171;
  v279 = &v242;
  v283 = L"DefaultExpectedResidency";
  v284 = &v172;
  v286 = &v243;
  v290 = L"DefaultLatencyToleranceIdle0";
  v291 = &v178;
  v293 = &v206;
  v297 = L"DefaultLatencyToleranceIdle1";
  v298 = &v179;
  v300 = &v207;
  v304 = L"DefaultLatencyToleranceNoContext";
  v305 = &v180;
  v307 = &v208;
  v311 = L"DefaultLatencyToleranceIdle0MonitorOff";
  v312 = &v182;
  v314 = &v209;
  v261 = 288;
  v264 = 67108868;
  v266 = 4;
  v267 = 0;
  v268 = 288;
  v271 = 67108868;
  v273 = 4;
  v274 = 0;
  v275 = 288;
  v278 = 67108868;
  v280 = 4;
  v281 = 0;
  v282 = 288;
  v285 = 67108868;
  v287 = 4;
  v288 = 0;
  v289 = 288;
  v292 = 67108868;
  v294 = 4;
  v295 = 0;
  v296 = 288;
  v299 = 67108868;
  v301 = 4;
  v302 = 0;
  v303 = 288;
  v306 = 67108868;
  v308 = 4;
  v309 = 0;
  v310 = 288;
  v313 = 67108868;
  v315 = 4;
  v316 = 0;
  v317 = 288;
  v318 = L"DefaultLatencyToleranceIdle1MonitorOff";
  v319 = &v183;
  v321 = &v210;
  v325 = L"DefaultLatencyToleranceNoContextMonitorOff";
  v326 = &v184;
  v328 = &v211;
  v332 = L"DefaultLatencyToleranceTimerPeriod";
  v333 = &v177;
  v335 = &v212;
  v339 = L"DefaultIdleThresholdIdle0";
  v340 = &v181;
  v342 = &v213;
  v346 = L"DefaultIdleThresholdIdle0MonitorOff";
  v347 = &v214;
  v349 = &v215;
  v353 = L"MonitorLatencyTolerance";
  v354 = &v202;
  v356 = &v216;
  v360 = L"MonitorRefreshLatencyTolerance";
  v361 = &v201;
  v363 = &v217;
  v367 = L"DefaultPowerNotRequiredTimeout";
  v368 = &v203;
  v370 = &v218;
  v320 = 67108868;
  v322 = 4;
  v323 = 0;
  v324 = 288;
  v327 = 67108868;
  v329 = 4;
  v330 = 0;
  v331 = 288;
  v334 = 67108868;
  v336 = 4;
  v337 = 0;
  v338 = 288;
  v341 = 67108868;
  v343 = 4;
  v344 = 0;
  v345 = 288;
  v348 = 67108868;
  v350 = 4;
  v351 = 0;
  v352 = 288;
  v355 = 67108868;
  v357 = 4;
  v358 = 0;
  v359 = 288;
  v362 = 67108868;
  v364 = 4;
  v365 = 0;
  v366 = 288;
  v369 = 67108868;
  v371 = 4;
  v372 = 0;
  v373 = 288;
  v376 = 67108868;
  v374 = L"DefaultActiveIdleThreshold";
  v375 = &v185;
  v377 = &v219;
  v381 = L"ulow";
  v382 = &v168;
  v384 = &v220;
  v388 = L"uhigh";
  v389 = &v169;
  v391 = &v221;
  v395 = L"uglitch";
  v396 = &v167;
  v398 = &v222;
  v402 = L"uideal";
  v403 = &v166;
  v405 = &v223;
  v409 = L"lowdebounce";
  v410 = &v176;
  v412 = &v224;
  v416 = L"EnablePODebounce";
  v417 = &v204;
  v419 = &v225;
  v423 = L"DisablePStateManagement";
  v424 = &v175;
  v426 = &v226;
  v378 = 4;
  v379 = 0;
  v380 = 288;
  v383 = 67108868;
  v385 = 4;
  v386 = 0;
  v387 = 288;
  v390 = 67108868;
  v392 = 4;
  v393 = 0;
  v394 = 288;
  v397 = 67108868;
  v399 = 4;
  v400 = 0;
  v401 = 288;
  v404 = 67108868;
  v406 = 4;
  v407 = 0;
  v408 = 288;
  v411 = 67108868;
  v413 = 4;
  v414 = 0;
  v415 = 288;
  v418 = 67108868;
  v420 = 4;
  v421 = 0;
  v422 = 288;
  v425 = 67108868;
  v427 = 4;
  v428 = 0;
  v429 = 288;
  v430 = L"DefaultD3TransitionLatencyActivelyUsed";
  v431 = &v186;
  v433 = &v227;
  v437 = L"DefaultD3TransitionLatencyIdleShortTime";
  v438 = &v188;
  v440 = &v228;
  v444 = L"DefaultD3TransitionLatencyIdleLongTime";
  v445 = &v190;
  v447 = &v229;
  v451 = L"DefaultD3TransitionLatencyIdleVeryLongTime";
  v452 = &v192;
  v454 = &v230;
  v458 = L"DefaultD3TransitionLatencyIdleNoContext";
  v459 = &v193;
  v461 = &v231;
  v465 = L"DefaultD3TransitionLatencyIdleMonitorOff";
  v466 = &v194;
  v468 = &v232;
  v472 = L"DefaultD3TransitionIdleShortTimeThreshold";
  v473 = &v187;
  v475 = &v233;
  v479 = L"DefaultD3TransitionIdleLongTimeThreshold";
  v480 = &v189;
  v482 = &v234;
  v486 = L"DefaultD3TransitionIdleVeryLongTimeThreshold";
  v432 = 67108868;
  v434 = 4;
  v435 = 0;
  v436 = 288;
  v439 = 67108868;
  v441 = 4;
  v442 = 0;
  v443 = 288;
  v446 = 67108868;
  v448 = 4;
  v449 = 0;
  v450 = 288;
  v453 = 67108868;
  v455 = 4;
  v456 = 0;
  v457 = 288;
  v460 = 67108868;
  v462 = 4;
  v463 = 0;
  v464 = 288;
  v467 = 67108868;
  v469 = 4;
  v470 = 0;
  v471 = 288;
  v474 = 67108868;
  v476 = 4;
  v477 = 0;
  v478 = 288;
  v481 = 67108868;
  v483 = 4;
  v484 = 0;
  v485 = 288;
  v488 = 67108868;
  v487 = &v191;
  v495 = 67108868;
  v489 = &v235;
  v502 = 67108868;
  v493 = L"DefaultLatencyToleranceMemory";
  v509 = 67108868;
  v494 = &v200;
  v516 = 67108868;
  v496 = &v236;
  v500 = L"DefaultLatencyToleranceMemoryNoContext";
  v501 = &v196;
  v503 = &v237;
  v507 = L"DefaultMemoryRefreshLatencyToleranceActivelyUsed";
  v508 = &v197;
  v510 = &v238;
  v514 = L"DefaultMemoryRefreshLatencyToleranceIdleShortTime";
  v515 = &v198;
  v517 = &v239;
  v521 = L"DefaultMemoryRefreshLatencyToleranceNoContext";
  v522 = &v199;
  v524 = &v240;
  v528 = L"DefaultMemoryRefreshLatencyToleranceMonitorOff";
  v529 = &v205;
  v523 = 67108868;
  v530 = 67108868;
  v531 = &v241;
  v490 = 4;
  v491 = 0;
  v492 = 288;
  v497 = 4;
  v498 = 0;
  v499 = 288;
  v504 = 4;
  v505 = 0;
  v506 = 288;
  v511 = 4;
  v512 = 0;
  v513 = 288;
  v518 = 4;
  v519 = 0;
  v520 = 288;
  v525 = 4;
  v526 = 0;
  v527 = 288;
  v532 = 4;
  v533 = 0;
  v534 = 0;
  v535 = 0;
  v536 = 0;
  v537 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v260, 0, 0);
  if ( *((int *)this + 783) < 2400 )
  {
    v7 = *((_QWORD *)this + 27);
    v173 = 0;
    if ( (int)DpiGetPnpRegistryKeyName(v7, 2, &v173) >= 0
      && (int)RtlStringCbCopyW(v539, 0x208u, *((const unsigned __int16 **)v173 + 1)) >= 0
      && (int)RtlStringCbCatW(v539, v8, L"\\DxgkSettings") >= 0 )
    {
      v248 = 0;
      v249 = 288;
      v250 = L"UseSelfRefreshVRAMInS3";
      v252 = 67108868;
      v251 = &v165;
      v254 = 4;
      v253 = &v195;
      v255 = 0;
      v256 = 0;
      v257 = 0;
      v258 = 0;
      v259 = 0;
      RtlQueryRegistryValuesEx(0, v539, &v248, 0, 0);
    }
  }
  if ( !v161 )
    return 0;
  LOBYTE(v9) = 0;
  v10 = 0;
  v11 = !v165;
  *((_BYTE *)this + 204) = v162 != 0;
  *((_BYTE *)this + 207) = !v11;
  v12 = *(_QWORD *)(*((_QWORD *)this + 27) + 64LL);
  v13 = *(_DWORD *)(*(_QWORD *)(v12 + 40) + 28LL);
  if ( v13 < 0x5019 )
    NumDifferentPhysicalAdapters = 1;
  else
    NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(this);
  v160 = NumDifferentPhysicalAdapters;
  LODWORD(v163) = 0;
  v15 = 0;
  while ( (unsigned int)v15 < NumDifferentPhysicalAdapters )
  {
    *(_QWORD *)&ObjectAttributes.Attributes = &v538[v15];
    memset(&ObjectAttributes, 0, 24);
    ObjectAttributes.Length = 6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(ObjectAttributes.SecurityDescriptor) = 4;
    if ( DXGADAPTER::IsDxgmms2(this) )
    {
      if ( v13 >= 0x5019 )
      {
        LODWORD(ObjectAttributes.ObjectName) = 4;
        ObjectAttributes.RootDirectory = &v163;
      }
    }
    AdapterInfo = DXGADAPTER::DdiQueryAdapterInfo(v16, (struct _DXGKARG_QUERYADAPTERINFO *)&ObjectAttributes);
    v9 = AdapterInfo;
    if ( AdapterInfo < 0 )
    {
      WdLogSingleEntry2(2, this, AdapterInfo);
      WdLogGlobalForLineNumber = 4973;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DdiQueryAdapterInfo failed. Adapter: 0x%p Status: 0x%I64x",
        (__int64)this,
        v9,
        0,
        0,
        0);
      return (unsigned int)v9;
    }
    v10 += v538[(unsigned int)v163];
    v15 = (unsigned int)(v163 + 1);
    LODWORD(v163) = v163 + 1;
  }
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(v12, (unsigned int)&Dxgk_PowerManagementComponents, v6, (_DWORD)this, v9, v10);
  if ( !v10 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 4988;
    return 0;
  }
  if ( v10 > 0xFFFF )
  {
    WdLogSingleEntry1(2, v10);
    WdLogGlobalForLineNumber = 4994;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Miniport returned invalid number of power components:0x%I64x",
      v10,
      0,
      0,
      0,
      0);
    LODWORD(v9) = -1073741811;
    goto LABEL_213;
  }
  *((_DWORD *)this + 874) = v10;
  v19 = 520LL * v10;
  if ( !is_mul_ok(v10, 0x208u) )
    v19 = -1;
  v20 = operator new[](v19, 1265072196, 64);
  *((_QWORD *)this + 419) = v20;
  if ( !v20 )
  {
    WdLogSingleEntry1(6, this);
    v21 = L"Adapter 0x%I64x: Out of memory allocating m_pPowerComponents";
    WdLogGlobalForLineNumber = 5004;
LABEL_36:
    DxgkLogInternalTriageEvent(0, 262145, -1, (_DWORD)v21, (__int64)this, 0, 0, 0, 0);
    LODWORD(v9) = -1073741801;
    goto LABEL_213;
  }
  v22 = operator new[](312 * v10 + 160, 1265072196, 256);
  v23 = (char *)v22;
  if ( !v22 )
  {
    WdLogSingleEntry1(6, this);
    v21 = L"Adapter 0x%I64x: Out of memory allocating pRegistrationInfo";
    WdLogGlobalForLineNumber = 5021;
    goto LABEL_36;
  }
  *(_DWORD *)v22 = 3;
  *(_QWORD *)(v22 + 8) = 2;
  v24 = 0;
  *(_DWORD *)(v22 + 96) = v10;
  *(_QWORD *)(v22 + 64) = DxgkPowerRuntimeDeviceDirectedPowerUpCallback;
  *(_QWORD *)(v22 + 88) = this;
  *(_QWORD *)(v22 + 72) = DxgkPowerRuntimeDeviceDirectedPowerDownCallback;
  v244 = v22 + 56LL * v10 + 104;
  *(_QWORD *)(v22 + 32) = DxgkPowerRuntimeComponentIdleStateCallback;
  v25 = 0;
  v170 = 0;
  *(_QWORD *)(v22 + 16) = DxgkPowerRuntimeComponentActiveCallback;
  *(_QWORD *)(v22 + 24) = DxgkPowerRuntimeComponentIdleCallback;
  *(_QWORD *)(v22 + 40) = DxgkPowerRuntimeDevicePowerRequiredCallback;
  *(_QWORD *)(v22 + 48) = DxgkPowerRuntimeDevicePowerNotRequiredCallback;
  *(_QWORD *)(v22 + 56) = DxgkPowerRuntimeControlCallback;
  v173 = (void *)(v22 + 56LL * v10 + 104 + 192LL * v10);
  v26 = 0;
  memset(&v246, 0, sizeof(v246));
  v162 = 0;
  v246.Type = DXGKQAITYPE_POWERCOMPONENTINFO;
  v246.InputDataSize = 4;
  v246.OutputDataSize = 336;
LABEL_40:
  v161 = v24;
  if ( v24 >= NumDifferentPhysicalAdapters )
  {
    if ( *((_DWORD *)this + 876) == -1 && !*((_BYTE *)this + 3792) )
      *((_QWORD *)this + 464) = 0;
    if ( *((int *)this + 783) < 1300 || !v25 || v175 )
      goto LABEL_152;
    if ( v168 > 0x3E8 || v169 > 0x3E8 || v167 > 0x3E8 || v166 > 0x3E8 || v168 >= v166 || v166 >= v169 || v169 >= v167 )
    {
      WdLogSingleEntry4(2, v168, v169);
      WdLogGlobalForLineNumber = 5322;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"P-State engine regkey validation error - low: 0x%I64x high: 0x%I64x glitch: 0x%I64x ideal: 0x%I64x",
        v168,
        v169,
        v167,
        v166,
        0);
      goto LABEL_98;
    }
    v49 = 248LL * v25;
    v246.Type = DXGKQAITYPE_POWERCOMPONENTPSTATEINFO;
    v246.OutputDataSize = 136;
    if ( !is_mul_ok(v25, 0xF8u) )
      v49 = -1;
    v50 = operator new[](v49, 1265072196, 64);
    *((_QWORD *)this + 569) = v50;
    *((_DWORD *)this + 1140) = v25;
    if ( !v50 )
    {
      WdLogSingleEntry1(6, this);
      WdLogGlobalForLineNumber = 5338;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Out of memory allocating m_NodePStateData",
        (__int64)this,
        0,
        0,
        0,
        0);
      LODWORD(v9) = -1073741801;
      goto LABEL_212;
    }
    v51 = 0;
    for ( i = 0; v51 < *((_DWORD *)this + 874); ++v51 )
    {
      v53 = *((_QWORD *)this + 419);
      v54 = 520LL * v51;
      if ( !*(_DWORD *)(v54 + v53 + 208) )
        *(_QWORD *)(v54 + v53 + 512) = *((_QWORD *)this + 569) + 248LL * i++;
    }
    v55 = 0;
    *((_DWORD *)this + 1192) = v167;
    *((_DWORD *)this + 1193) = v169;
    *((_DWORD *)this + 1194) = v168;
    *((_DWORD *)this + 1195) = v166;
    *((_DWORD *)this + 1196) = v176;
    for ( j = 0; ; j = v55 )
    {
      LODWORD(v163) = v55;
      if ( (unsigned int)j >= v10 )
        goto LABEL_138;
      v57 = *(_QWORD *)(520 * j + *((_QWORD *)this + 419) + 512);
      if ( v57 )
      {
        v246.pOutputData = *(void **)(520 * j + *((_QWORD *)this + 419) + 512);
        v246.pInputData = &v163;
        v58 = DXGADAPTER::DdiQueryAdapterInfo(this, &v246);
        v59 = v58;
        if ( v58 < 0 )
        {
          v61 = WdLogNewEntry5_WdTrace();
          *(_QWORD *)(v61 + 24) = (unsigned int)v163;
          *(_QWORD *)(v61 + 32) = v59;
          WdLogGlobalForLineNumber = 5388;
          for ( k = 0; k < *((_DWORD *)this + 874); ++k )
          {
            v63 = 520LL * k;
            v64 = *((_QWORD *)this + 419);
            if ( !*(_DWORD *)(v63 + v64 + 208) )
              *(_QWORD *)(v63 + v64 + 512) = 0;
          }
          v65 = (void *)*((_QWORD *)this + 569);
          *((_DWORD *)this + 1140) = 0;
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v65);
          *((_QWORD *)this + 569) = 0;
LABEL_138:
          v66 = *((_DWORD *)this + 1140);
          v67 = 0;
          v174 = v66;
          while ( v67 < v66 )
          {
            v68 = *((_QWORD *)this + 569);
            v69 = v67;
            v70 = 248LL * v67;
            v71 = *(_DWORD *)(v70 + v68);
            v72 = *(unsigned int *)(v70 + v68 + 144);
            if ( v71 > 0x20 )
            {
              v80 = *(unsigned int *)(v70 + v68 + 144);
              WdLogSingleEntry1(2, v80);
              WdLogGlobalForLineNumber = 5443;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"P-State StateCount cannot be larger than DXGK_MAX_P_STATES. Component:0x%I64x",
                v80,
                0,
                0,
                0,
                0);
              goto LABEL_98;
            }
            for ( m = 0; m < v71; ++m )
            {
              v74 = 62 * v69;
              v75 = m;
              v76 = *(_DWORD *)(v68 + 4 * (v74 + m) + 4);
              if ( !v76 )
              {
                v79 = *(unsigned int *)(v70 + v68 + 144);
                WdLogSingleEntry2(2, v72, m);
                WdLogGlobalForLineNumber = 5456;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"P-State cannot specify 0 operating frequency. Component:0x%I64x, P-State:0x%I64x",
                  v79,
                  v75,
                  0,
                  0,
                  0);
                goto LABEL_92;
              }
              if ( m )
              {
                v77 = m - 1;
                if ( v76 > *(_DWORD *)(v68 + 4 * (v74 + v77) + 4) )
                {
                  v78 = *(unsigned int *)(v70 + v68 + 144);
                  WdLogSingleEntry3(2, v72, m, m - 1);
                  WdLogGlobalForLineNumber = 5466;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"P-States must have monotonically decreasing operating frequency. Component:0x%I64x, P-"
                                   "State1:0x%I64x, P-State2:0x%I64x",
                    v78,
                    v75,
                    v77,
                    0,
                    0);
                  goto LABEL_92;
                }
              }
              v69 = v67;
            }
            v66 = v174;
            ++v67;
          }
LABEL_152:
          v81 = (ADAPTER_RENDER *)*((_QWORD *)this + 407);
          *((_DWORD *)this + 946) = v177;
          if ( v81 )
          {
            v82 = ADAPTER_RENDER::InitializePowerManagement(v81);
            v9 = v82;
            if ( v82 < 0 )
            {
              WdLogSingleEntry2(2, v82, 7);
              WdLogGlobalForLineNumber = 5482;
              v83 = L"InitializePowerManagement failed for render adapter:0x%I64x";
              StartRoutine = 7;
LABEL_155:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v83, v9, StartRoutine, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v84 = (ADAPTER_DISPLAY *)*((_QWORD *)this + 406);
          if ( v84 )
          {
            v85 = ADAPTER_DISPLAY::InitializePowerManagement(v84);
            v9 = v85;
            if ( v85 < 0 )
            {
              v86 = 8;
              WdLogSingleEntry2(2, v85, 8);
              WdLogGlobalForLineNumber = 5492;
              v87 = L"InitializePowerManagement failed for display adapter:0x%I64x";
LABEL_211:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v87, v9, v86, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v88 = PoFxRegisterDevice(*((_QWORD *)this + 27), v23, (char *)this + 3360);
          v9 = v88;
          if ( v88 < 0 )
          {
            WdLogSingleEntry1(2, v88);
            WdLogGlobalForLineNumber = 5500;
            v83 = L"PoFxRegisterDevice failed with status:0x%I64x";
            StartRoutine = 0;
            goto LABEL_155;
          }
          KeInitializeEvent((PRKEVENT)((char *)this + 3520), SynchronizationEvent, 0);
          *((_QWORD *)this + 476) = (char *)this + 3800;
          *((_QWORD *)this + 475) = (char *)this + 3800;
          *((_BYTE *)this + 3788) = 0;
          TimeIncrement = KeQueryTimeIncrement();
          v90 = v178;
          v91 = TimeIncrement;
          *((_QWORD *)this + 446) = 0;
          *((_QWORD *)this + 448) = 0;
          *((_QWORD *)this + 452) = 0;
          *((_QWORD *)this + 454) = 0;
          *((_QWORD *)this + 443) = 10 * v90;
          v92 = v180;
          *((_QWORD *)this + 445) = 10LL * v179;
          v93 = 10000LL * v181;
          *((_QWORD *)this + 447) = 10 * v92;
          v94 = (unsigned int)(v93 / v91);
          v95 = v182;
          *((_QWORD *)this + 444) = v94;
          *((_QWORD *)this + 450) = v94;
          v96 = 5 * v95;
          v97 = v183;
          *((_QWORD *)this + 449) = 2 * v96;
          v98 = 5 * v97;
          v99 = v184;
          *((_QWORD *)this + 451) = 2 * v98;
          v100 = 5 * v99;
          v101 = v185;
          *((_QWORD *)this + 453) = 2 * v100;
          *((_QWORD *)this + 455) = (char *)this + 3544;
          v102 = 5 * v101;
          v103 = v186;
          *((_QWORD *)this + 487) = 2 * v102;
          v104 = 10000LL * v187;
          *((_QWORD *)this + 456) = 10 * v103;
          v105 = v188;
          *((_QWORD *)this + 457) = (unsigned int)(v104 / v91);
          v106 = 10000LL * v189;
          *((_QWORD *)this + 458) = 10 * v105;
          v107 = v190;
          *((_QWORD *)this + 459) = (unsigned int)(v106 / v91);
          v108 = 5 * v107;
          v109 = 10000LL * v191;
          *((_QWORD *)this + 460) = 2 * v108;
          v110 = v109;
          v111 = v192;
          *((_QWORD *)this + 461) = (unsigned int)(v110 / v91);
          *((_QWORD *)this + 463) = 0;
          v159 = 0;
          v112 = 5 * v111;
          v113 = v193;
          *((_QWORD *)this + 462) = 2 * v112;
          v114 = 5 * v113;
          v115 = v194;
          *((_QWORD *)this + 465) = 2 * v114;
          v116 = 5 * v115;
          v117 = v200;
          *((_QWORD *)this + 466) = 2 * v116;
          v118 = 5 * v117;
          v119 = v196;
          *((_QWORD *)this + 467) = 2 * v118;
          v120 = 5 * v119;
          v121 = v197;
          *((_QWORD *)this + 468) = 2 * v120;
          v122 = 5 * v121;
          v123 = v198;
          *((_QWORD *)this + 469) = 2 * v122;
          v124 = 5 * v123;
          v125 = v199;
          *((_QWORD *)this + 470) = 2 * v124;
          v126 = 5 * v125;
          v127 = v205;
          *((_QWORD *)this + 471) = 2 * v126;
          *((_QWORD *)this + 472) = 10 * v127;
          *((_QWORD *)this + 481) = (char *)this + 3840;
          *((_QWORD *)this + 480) = (char *)this + 3840;
          KeInitializeSpinLock((PKSPIN_LOCK)this + 486);
          v128 = 0;
          v160 = 0;
          while ( 2 )
          {
            v129 = *((_QWORD *)this + 419);
            v130 = 520 * v128;
            v131 = 520 * v128 + v129 + 424;
            *(_BYTE *)(520 * v128 + v129 + 356) = 1;
            v132 = 520 * v128 + v129;
            *(_OWORD *)v131 = 0;
            v133 = *(_DWORD *)(v132 + 208);
            if ( v133 )
            {
              v134 = v133 - 1;
              if ( v134 )
              {
                v135 = v134 - 1;
                if ( v135 )
                {
                  v136 = v135 - 1;
                  if ( v136 )
                  {
                    v137 = v136 - 1;
                    if ( v137 )
                    {
                      v138 = v137 - 2;
                      if ( v138 )
                      {
                        if ( v138 == 1 )
                        {
                          v159 = 1;
                          if ( (*(_DWORD *)(v130 + v129 + 216) & 0x10) != 0 )
                          {
                            *(_BYTE *)(v130 + v129 + 360) = 1;
                            *(_BYTE *)(v130 + v129 + 356) = 0;
                            *(_DWORD *)(v130 + v129 + 344) = 1;
                          }
                        }
                        else
                        {
                          v139 = this;
                          v140 = *(_DWORD *)(v130 + v129 + 4);
                          if ( v171 == -1 )
                            v141 = -1;
                          else
                            v141 = 10LL * v171;
LABEL_171:
                          DXGADAPTER::SetPowerComponentLatencyCB(v139, v140, v141);
                        }
                      }
                    }
                  }
                  else
                  {
                    v142 = (DXGADAPTER **)*((_QWORD *)this + 483);
                    if ( *v142 != (DXGADAPTER *)((char *)this + 3856) )
                      goto LABEL_208;
                    *(_QWORD *)v131 = (char *)this + 3856;
                    *(_QWORD *)(v131 + 8) = v142;
                    *v142 = (DXGADAPTER *)v131;
                    *((_QWORD *)this + 483) = v131;
                    if ( (*(_DWORD *)(v130 + v129 + 216) & 0x10) != 0 )
                      *(_BYTE *)(v130 + v129 + 360) = 1;
                  }
LABEL_192:
                  if ( v172 == -1 )
                    v151 = -1;
                  else
                    v151 = 10000LL * v172;
                  DXGADAPTER::SetPowerComponentResidencyCB(this, *(_DWORD *)(v130 + v129 + 4), v151);
                  KeInitializeSpinLock((PKSPIN_LOCK)(v130 + v129 + 504));
                  if ( *(_DWORD *)(v132 + 8) <= 1u || (v152 = *(_QWORD *)(v130 + v129 + 48), v152 == -1) )
                  {
                    v153 = *((_QWORD *)this + 487);
                  }
                  else
                  {
                    v153 = *((_QWORD *)this + 487);
                    if ( v152 > v153 )
                      v153 = *(_QWORD *)(v130 + v129 + 48);
                  }
                  *(_QWORD *)(v130 + v129 + 496) = v153;
                  v128 = (unsigned int)(v160 + 1);
                  v160 = v128;
                  if ( (unsigned int)v128 >= v10 )
                  {
                    DXGADAPTER::UpdateLatencyTolerances(this);
                    PoFxSetDeviceIdleTimeout(*((_QWORD *)this + 420), 10LL * v203);
                    if ( *((_DWORD *)this + 105) == 1297040209 && *((_DWORD *)this + 716) == 4608 )
                    {
                      KeInitializeEvent((PRKEVENT)((char *)this + 4040), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4064), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4088), SynchronizationEvent, 0);
                      KeInitializeSpinLock((PKSPIN_LOCK)this + 514);
                      *((_QWORD *)this + 517) = (char *)this + 4128;
                      *((_QWORD *)this + 516) = (char *)this + 4128;
                      InitializeSListHead((PSLIST_HEADER)this + 259);
                      v155 = 0;
                      v86 = 8;
                      do
                        ExpInterlockedPushEntrySList((PSLIST_HEADER)this + 259, (PSLIST_ENTRY)this + 2 * v155++ + 261);
                      while ( v155 != 8 );
                      *(_QWORD *)&ObjectAttributes.Length = 48;
                      *(_QWORD *)&ObjectAttributes.Attributes = 512;
                      ObjectAttributes.RootDirectory = 0;
                      ObjectAttributes.ObjectName = 0;
                      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                      v156 = PsCreateSystemThread(
                               (PHANDLE)this + 520,
                               0x1FFFFFu,
                               &ObjectAttributes,
                               0,
                               0,
                               DXGADAPTER::PowerRuntimeComponentIdleStateCallbackThread,
                               this);
                      v9 = v156;
                      if ( v156 < 0 )
                      {
                        WdLogSingleEntry2(2, v156, 8);
                        v87 = L"InitializePowerManagement failed to create worker thread for display adapter:0x%I64x";
                        WdLogGlobalForLineNumber = 5752;
                        goto LABEL_211;
                      }
                    }
                    LOBYTE(v154) = v159;
                    v157 = DpiEnablePowerManagement(*((_QWORD *)this + 27), *((_QWORD *)this + 420), v154);
                    v9 = v157;
                    if ( v157 < 0 )
                    {
                      DXGADAPTER::DestroySerializeFStateTransitWorker(this);
                      v86 = 9;
                      WdLogSingleEntry2(2, v9, 9);
                      v87 = L"Port power management enable failed:0x%I64x";
                      WdLogGlobalForLineNumber = 5767;
                      goto LABEL_211;
                    }
                    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v23);
                    return 0;
                  }
                  continue;
                }
                v143 = v201;
              }
              else
              {
                v143 = v202;
              }
              v140 = *(_DWORD *)(v130 + v129 + 4);
              v141 = 10 * v143;
              v139 = this;
              goto LABEL_171;
            }
            break;
          }
          *(_BYTE *)(v130 + v129 + 357) = 1;
          v144 = (DXGADAPTER **)*((_QWORD *)this + 485);
          if ( *v144 != (DXGADAPTER *)((char *)this + 3872) )
LABEL_208:
            __fastfail(3u);
          *(_QWORD *)v131 = (char *)this + 3872;
          *(_QWORD *)(v131 + 8) = v144;
          *v144 = (DXGADAPTER *)v131;
          *((_QWORD *)this + 485) = v131;
          v145 = 0;
          v146 = *(_DWORD *)(v132 + 8);
          for ( n = 1; n < v146; v145 = v148 )
          {
            v148 = *(_QWORD *)(v132 + 24LL * n + 16);
            if ( v145 >= v148 )
              v148 = v145;
            ++n;
          }
          *(_DWORD *)(v130 + v129 + 388) = 1;
          for ( ii = 0; ; ++ii )
          {
            if ( ii >= 2 )
              goto LABEL_191;
            if ( *((_QWORD *)this + 2 * ii + 443) >= v145 )
              break;
          }
          *(_DWORD *)(v130 + v129 + 388) = ii;
LABEL_191:
          v150 = *(_DWORD *)(v130 + v129 + 4);
          *(_DWORD *)(v130 + v129 + 384) = 2;
          DXGADAPTER::SetPowerComponentLatencyCB(this, v150, *(_QWORD *)(*((_QWORD *)this + 455) + 32LL));
          ++*((_DWORD *)this + 878);
          goto LABEL_192;
        }
        v60 = v163;
        *(_QWORD *)(v57 + 136) = this;
        *(_DWORD *)(v57 + 144) = v60;
        *(_QWORD *)(v57 + 152) = v57;
        KeInitializeSpinLock((PKSPIN_LOCK)(v57 + 160));
        *(_DWORD *)(v57 + 244) = -1;
        *(_BYTE *)(v57 + 240) = 0;
        v55 = v163;
      }
      ++v55;
    }
  }
  v27 = v24;
  v28 = 0;
  v247 = v24;
  *((_WORD *)this + v24 + 1684) = v26;
  while ( 1 )
  {
    v164 = v28;
    if ( v28 >= v538[v27] )
    {
      NumDifferentPhysicalAdapters = v160;
      ++v24;
      goto LABEL_40;
    }
    v29 = v26;
    v30 = v24;
    v31 = *((_QWORD *)this + 419) + 8LL;
    v32 = 520 * v29;
    v174 = v28 + (v30 << 16);
    v246.pInputData = &v174;
    v246.pOutputData = (void *)(520 * v29 + v31);
    v163 = 520 * v29;
    v33 = DXGADAPTER::DdiQueryAdapterInfo(this, &v246);
    v9 = v33;
    if ( v33 < 0 )
    {
      WdLogSingleEntry2(2, v29, v33);
      WdLogGlobalForLineNumber = 5088;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport failed QueryAdapterInfo(DXGKQAITYPE_POWERCOMPONENTINFO). Component: 0x%I64x, Status: 0x%I64x",
        v29,
        v9,
        0,
        0,
        0);
      goto LABEL_212;
    }
    v34 = v164;
    v35 = v162;
    v36 = 56 * v29;
    *(_DWORD *)(v32 + *((_QWORD *)this + 419)) = v162;
    *(_WORD *)(v32 + *((_QWORD *)this + 419) + 4) = v34;
    *(_WORD *)(v32 + *((_QWORD *)this + 419) + 6) = v161;
    v37 = *((_QWORD *)this + 419) + v32;
    *(_DWORD *)&v23[56 * v29 + 132] = *(_DWORD *)(v37 + 8);
    if ( (unsigned int)(*(_DWORD *)(v37 + 8) - 1) > 7 )
    {
      WdLogSingleEntry3(2, v29, *(unsigned int *)(v37 + 8), 0);
      WdLogGlobalForLineNumber = 5102;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport returned invalid number of F states for component:0x%I64x 0x%I64x",
        v29,
        *(unsigned int *)(v37 + 8),
        0,
        0,
        0);
      goto LABEL_92;
    }
    *(_OWORD *)&v23[v36 + 104] = *(_OWORD *)(v37 + 220);
    *(_BYTE *)(v37 + 275) = 0;
    v38 = *(_DWORD *)(v37 + 216);
    if ( v38 >= 0x20 )
    {
      WdLogSingleEntry2(2, v29, 2);
      WdLogGlobalForLineNumber = 5116;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Reserved flags are not zero. Component:0x%I64x",
        v29,
        2,
        0,
        0,
        0);
      goto LABEL_92;
    }
    if ( (v38 & 4) != 0 )
      *(_QWORD *)&v23[v36 + 120] |= 1uLL;
    if ( !v204 )
      *(_QWORD *)&v23[v36 + 120] |= 2uLL;
    if ( (*(_DWORD *)(v37 + 216) & 0x10) != 0 )
    {
      if ( ((*(_DWORD *)(v37 + 208) - 3) & 0xFFFFFFFB) != 0 )
      {
        WdLogSingleEntry1(2, v29);
        v40 = L"Power component ActiveInD3 flag can only be used with DXGK_POWER_COMPONENT_MEMORY and DXGK_POWER_COMPONENT"
               "_SHARED. Component:0x%I64x";
        WdLogGlobalForLineNumber = 5135;
      }
      else if ( *(_DWORD *)(v37 + 8) == 2 )
      {
        if ( *(_QWORD *)(v37 + 40) )
        {
          WdLogSingleEntry1(2, v29);
          v40 = L"TransitionLatency for the F1 state must be 0 when the ActiveInD3 flag is set. Component:0x%I64x";
          WdLogGlobalForLineNumber = 5147;
        }
        else
        {
          if ( !*(_DWORD *)(v37 + 276) )
            goto LABEL_55;
          WdLogSingleEntry1(2, v29);
          v40 = L"Provider count must be 0 when the ActiveInD3 flag is set. Component:0x%I64x";
          WdLogGlobalForLineNumber = 5153;
        }
      }
      else
      {
        WdLogSingleEntry1(2, v29);
        v40 = L"F state count must be 2 when the ActiveInD3 flag is set. Component:0x%I64x";
        WdLogGlobalForLineNumber = 5141;
      }
LABEL_91:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v40, v29, 0, 0, 0, 0);
LABEL_92:
      LODWORD(v9) = -1073741811;
      goto LABEL_212;
    }
LABEL_55:
    if ( *(_DWORD *)(v37 + 276) > 0x10u )
    {
      WdLogSingleEntry2(2, v29, 3);
      WdLogGlobalForLineNumber = 5161;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid component ProviderCount. Component:0x%I64x",
        v29,
        3,
        0,
        0,
        0);
      goto LABEL_92;
    }
    v39 = *(_DWORD *)(v37 + 208);
    if ( v39 == 4 )
    {
      if ( *((_DWORD *)this + 876) == -1 )
      {
        *((_DWORD *)this + 876) = v35;
        goto LABEL_66;
      }
      WdLogSingleEntry1(2, v29);
      v40 = L"DXGK_POWER_COMPONENT_MEMORY_REFRESH component is defined second time. Component:0x%I64x";
      WdLogGlobalForLineNumber = 5201;
      goto LABEL_91;
    }
    if ( v39 == 6 )
    {
      if ( *((_DWORD *)this + 875) != -1 )
      {
        WdLogSingleEntry1(3, v29);
        WdLogGlobalForLineNumber = 5175;
        goto LABEL_66;
      }
      *((_DWORD *)this + 875) = v35;
      *((_QWORD *)this + 464) = *((_QWORD *)this + 419) + v163;
      if ( *(_DWORD *)(v37 + 8) == 2 )
      {
        *((_BYTE *)this + 3792) = 1;
        goto LABEL_66;
      }
      if ( *(_DWORD *)(v37 + 8) <= 2u )
        goto LABEL_66;
      WdLogSingleEntry1(2, v29);
      v40 = L"F state count for the DXGK_POWER_COMPONENT_D3_TRANSITION component must be 1 or 2. Component:0x%I64x";
      WdLogGlobalForLineNumber = 5191;
      goto LABEL_91;
    }
LABEL_66:
    v41 = v173;
    *(_DWORD *)&v23[v36 + 144] = *(_DWORD *)(v37 + 276);
    memmove(v41, (const void *)(v37 + 280), 4LL * *(unsigned int *)(v37 + 276));
    v42 = v244;
    *(_QWORD *)&v23[v36 + 152] = v173;
    v43 = *(unsigned int *)(v37 + 276);
    *(_QWORD *)&v23[v36 + 136] = v42;
    v44 = 0;
LABEL_67:
    if ( v44 < *(_DWORD *)(v37 + 8) )
      break;
    v11 = *(_DWORD *)(v37 + 208) == 0;
    v25 = v170;
    v173 = (char *)v173 + 4 * v43;
    if ( v11 )
      v25 = ++v170;
    v24 = v161;
    v28 = v164 + 1;
    v27 = v247;
    v26 = ++v162;
  }
  *(_QWORD *)v42 = *(_QWORD *)(v37 + 24LL * v44 + 16);
  *(_QWORD *)(v42 + 8) = *(_QWORD *)(v37 + 24LL * v44 + 24);
  *(_DWORD *)(v42 + 16) = *(_DWORD *)(v37 + 24LL * v44 + 32);
  if ( *(_QWORD *)(v37 + 24LL * v44 + 16) == -1 )
    *(_QWORD *)v42 = -1;
  if ( *(_QWORD *)(v37 + 24LL * v44 + 24) == -1 )
    *(_QWORD *)(v42 + 8) = -1;
  if ( *(_DWORD *)(v37 + 24LL * v44 + 32) == -1 )
    *(_DWORD *)(v42 + 16) = -1;
  if ( v44 )
  {
    v45 = *(_DWORD *)(v37 + 24LL * v44 + 32);
    if ( v45 != -1 )
    {
      v46 = *(_DWORD *)(v37 + 24 * (v44 - 1 + 1LL) + 8);
      if ( v46 != -1 && v45 > v46 )
      {
        WdLogSingleEntry2(2, v29, 5);
        WdLogGlobalForLineNumber = 5265;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"NominalPower must be decreasing for higher F states. Component:0x%I64x",
          v29,
          5,
          0,
          0,
          0);
        goto LABEL_98;
      }
    }
    v47 = *(_QWORD *)(v37 + 24LL * v44 + 16);
    if ( v47 != -1 )
    {
      v48 = *(_QWORD *)(v37 + 24LL * (v44 - 1) + 16);
      if ( v48 != -1 && v47 < v48 )
      {
        WdLogSingleEntry2(2, v29, 6);
        WdLogGlobalForLineNumber = 5273;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"TransitionLatency must be increasing for higher F states. Component:0x%I64x",
          v29,
          6,
          0,
          0,
          0);
        goto LABEL_98;
      }
    }
LABEL_85:
    v42 += 24;
    v244 = v42;
    ++v44;
    goto LABEL_67;
  }
  if ( ((*(_QWORD *)(v37 + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    && ((*(_QWORD *)(v37 + 24) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !*(_DWORD *)(v37 + 32) )
    {
      WdLogSingleEntry2(2, v29, 4);
      WdLogGlobalForLineNumber = 5254;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NominalPower must not be zero for the F0 state. Component:0x%I64x",
        v29,
        4,
        0,
        0,
        0);
      goto LABEL_98;
    }
    goto LABEL_85;
  }
  WdLogSingleEntry2(2, v29, 3);
  WdLogGlobalForLineNumber = 5248;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"TransitionLatency and ResidencyRequirement must be zero for the F0 state. Component:0x%I64x",
    v29,
    3,
    0,
    0,
    0);
LABEL_98:
  LODWORD(v9) = -1073741811;
LABEL_212:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v23);
LABEL_213:
  if ( *((_QWORD *)this + 420) )
  {
    PoFxUnregisterDevice();
    *((_QWORD *)this + 420) = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1401eb410  push    rbp
0x1401eb412  push    rbx
0x1401eb413  push    rsi
0x1401eb414  push    rdi
0x1401eb415  push    r12
0x1401eb417  push    r13
0x1401eb419  push    r14
0x1401eb41b  push    r15
0x1401eb41d  lea     rbp, [rsp-0D78h]
0x1401eb425  sub     rsp, 0E78h
0x1401eb42c  mov     rax, cs:__security_cookie
0x1401eb433  xor     rax, rsp
0x1401eb436  mov     [rbp+0DB0h+var_50], rax
0x1401eb43d  mov     esi, 2
0x1401eb442  lea     rbx, [rcx+0BFDh]
0x1401eb449  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1401eb450  mov     rdi, rcx
0x1401eb453  jz      short loc_1401EB472
0x1401eb455  movzx   eax, byte ptr [rbx]
0x1401eb458  lea     rdx, Dxgk_PowerManagementSupport
0x1401eb45f  mov     r9, rcx
0x1401eb462  mov     dword ptr [rsp+0EB0h+ClientId], eax
0x1401eb466  lea     rcx, DxgkControlGuid_Context
0x1401eb46d  call    McTemplateK0pt_EtwWriteTransfer
0x1401eb472  xor     r15d, r15d
0x1401eb475  cmp     [rbx], r15b
0x1401eb478  jnz     short loc_1401EB499
0x1401eb47a  lea     ecx, [r15+3]
0x1401eb47e  call    cs:__imp_WdLogSingleEntry0
0x1401eb485  nop     dword ptr [rax+rax+00h]
0x1401eb48a  mov     cs:WdLogGlobalForLineNumber, 12A8h
0x1401eb494  jmp     loc_1401ED8DC
0x1401eb499  or      eax, 0FFFFFFFFh
0x1401eb49c  mov     [rbp+0DB0h+var_D4C], r15d
0x1401eb4a0  mov     [rbp+0DB0h+var_D08], eax
0x1401eb4a6  mov     r8d, 50h ; 'P'
0x1401eb4ac  mov     [rbp+0DB0h+var_E2C], eax
0x1401eb4af  mov     ecx, 7D0h
0x1401eb4b4  mov     eax, 88B8h
0x1401eb4b9  mov     [rbp+0DB0h+var_D04], ecx
0x1401eb4bf  mov     [rbp+0DB0h+var_D90], eax
0x1401eb4c2  mov     edx, 3A98h
0x1401eb4c7  mov     [rbp+0DB0h+var_E00], eax
0x1401eb4ca  lea     r12d, [r8-4Dh]
0x1401eb4ce  mov     eax, 0C350h
0x1401eb4d3  mov     [rbp+0DB0h+var_E28], ecx
0x1401eb4d6  mov     [rbp+0DB0h+var_D88], eax
0x1401eb4d9  mov     [rbp+0DB0h+var_DF4], eax
0x1401eb4dc  mov     eax, 186A0h
0x1401eb4e1  mov     [rbp+0DB0h+var_D84], eax
0x1401eb4e4  mov     [rbp+0DB0h+var_DF0], eax
0x1401eb4e7  mov     eax, 493E0h
0x1401eb4ec  mov     [rbp+0DB0h+var_D70], eax
0x1401eb4ef  mov     [rbp+0DB0h+var_DA8], eax
0x1401eb4f2  mov     eax, 4268h
0x1401eb4f7  mov     [rbp+0DB0h+var_D6C], eax
0x1401eb4fa  mov     [rbp+0DB0h+var_DAC], eax
0x1401eb4fd  lea     eax, [r8+78h]
0x1401eb501  mov     [rbp+0DB0h+var_D80], eax
0x1401eb504  mov     [rbp+0DB0h+var_E0C], eax
0x1401eb507  mov     [rbp+0DB0h+var_D7C], eax
0x1401eb50a  mov     [rbp+0DB0h+var_DFC], eax
0x1401eb50d  lea     eax, [r8+14h]
0x1401eb511  mov     [rbp+0DB0h+var_D74], eax
0x1401eb514  mov     [rbp+0DB0h+var_D78], eax
0x1401eb517  mov     eax, 61A8h
0x1401eb51c  mov     [rbp+0DB0h+var_D68], eax
0x1401eb51f  mov     [rbp+0DB0h+var_DA4], eax
0x1401eb522  mov     eax, 12Ch
0x1401eb527  mov     [rbp+0DB0h+var_D60], eax
0x1401eb52a  mov     [rsp+0EB0h+var_E38], eax
0x1401eb52e  mov     eax, 2BCh
0x1401eb533  mov     [rbp+0DB0h+var_D5C], eax
0x1401eb536  mov     [rsp+0EB0h+var_E34], eax
0x1401eb53a  mov     eax, 384h
0x1401eb53f  mov     [rbp+0DB0h+var_D58], eax
0x1401eb542  mov     [rsp+0EB0h+var_E3C], eax
0x1401eb546  mov     eax, 1F4h
0x1401eb54b  mov     [rbp+0DB0h+var_D54], eax
0x1401eb54e  mov     [rsp+0EB0h+var_E40], eax
0x1401eb552  mov     eax, 222E0h
0x1401eb557  mov     [rbp+0DB0h+var_D3C], eax
0x1401eb55a  mov     [rbp+0DB0h+var_DD8], eax
0x1401eb55d  mov     eax, 30D40h
0x1401eb562  mov     [rbp+0DB0h+var_D38], eax
0x1401eb565  mov     [rbp+0DB0h+var_DD0], eax
0x1401eb568  mov     eax, 3D090h
0x1401eb56d  mov     [rbp+0DB0h+var_D34], eax
0x1401eb570  mov     [rbp+0DB0h+var_DCC], eax
0x1401eb573  mov     [rbp+0DB0h+var_D30], eax
0x1401eb579  mov     [rbp+0DB0h+var_DC8], eax
0x1401eb57c  mov     eax, 2710h
0x1401eb581  mov     [rbp+0DB0h+var_D8C], ecx
0x1401eb584  mov     [rbp+0DB0h+var_DF8], ecx
0x1401eb587  mov     [rbp+0DB0h+var_D64], ecx
0x1401eb58a  mov     [rbp+0DB0h+var_DEC], ecx
0x1401eb58d  mov     ecx, 13880h
0x1401eb592  mov     [rbp+0DB0h+var_D2C], eax
0x1401eb598  mov     [rbp+0DB0h+var_DE4], eax
0x1401eb59b  mov     eax, 0EA60h
0x1401eb5a0  mov     [rbp+0DB0h+var_D98], r8d
0x1401eb5a4  mov     [rbp+0DB0h+var_E08], r8d
0x1401eb5a8  mov     [rbp+0DB0h+var_D94], edx
0x1401eb5ab  mov     [rbp+0DB0h+var_E04], edx
0x1401eb5ae  mov     [rbp+0DB0h+var_D50], r12d
0x1401eb5b2  mov     [rbp+0DB0h+var_E10], r12d
0x1401eb5b6  mov     [rbp+0DB0h+var_DA0], r15d
0x1401eb5ba  mov     [rbp+0DB0h+var_D48], r15d
0x1401eb5be  mov     [rbp+0DB0h+var_E14], r15d
0x1401eb5c2  mov     [rbp+0DB0h+var_D44], r8d
0x1401eb5c6  mov     [rbp+0DB0h+var_DE8], r8d
0x1401eb5ca  mov     [rbp+0DB0h+var_D40], ecx
0x1401eb5cd  mov     [rbp+0DB0h+var_DE0], ecx
0x1401eb5d0  cmp     dword ptr [rdi+0C3Ch], 960h
0x1401eb5da  lea     r14d, [r8-4Fh]
0x1401eb5de  mov     [rbp+0DB0h+var_D28], eax
0x1401eb5e4  lea     ebx, [r8-4Ch]
0x1401eb5e8  mov     [rbp+0DB0h+var_DDC], eax
0x1401eb5eb  mov     r13d, 120h
0x1401eb5f1  mov     [rbp+0DB0h+var_D24], eax
0x1401eb5f7  mov     [rbp+0DB0h+var_DD4], eax
0x1401eb5fa  mov     eax, 7530h
0x1401eb5ff  mov     [rbp+0DB0h+var_D1C], eax
0x1401eb605  mov     [rbp+0DB0h+var_DC0], eax
0x1401eb608  mov     [rbp+0DB0h+var_D10], eax
0x1401eb60e  mov     [rbp+0DB0h+var_DB4], eax
0x1401eb611  lea     rax, aUseselfrefresh; "UseSelfRefreshVRAMInS3"
0x1401eb618  mov     [rbp+0DB0h+var_D0C], ecx
0x1401eb61e  mov     [rbp+0DB0h+var_D9C], ecx
0x1401eb621  mov     ecx, 4000004h
0x1401eb626  mov     [rbp+0DB0h+var_D20], edx
0x1401eb62c  mov     [rbp+0DB0h+var_DB0], edx
0x1401eb62f  mov     [rbp+0DB0h+var_D18], r8d
0x1401eb636  mov     [rbp+0DB0h+var_DBC], r8d
0x1401eb63a  mov     [rbp+0DB0h+var_D14], edx
0x1401eb640  mov     [rbp+0DB0h+var_DB8], edx
0x1401eb643  mov     [rbp+0DB0h+var_DC4], r14d
0x1401eb647  mov     [rsp+0EB0h+var_E44], r14d
0x1401eb64c  mov     [rsp+0EB0h+var_E5C], r14d
0x1401eb651  mov     [rsp+0EB0h+var_E58], r14d
0x1401eb656  mov     [rsp+0EB0h+var_E48], r15d
0x1401eb65b  mov     [rsp+0EB0h+var_E54], r15d
0x1401eb660  jge     loc_1401EB6EF
0x1401eb666  mov     [rbp+0DB0h+var_C80], rax
0x1401eb66d  lea     r8, [rbp+0DB0h+var_C90]
0x1401eb674  xorps   xmm0, xmm0
0x1401eb677  mov     [rbp+0DB0h+var_C70], ecx
0x1401eb67d  lea     rax, [rsp+0EB0h+var_E44]
0x1401eb682  mov     [rbp+0DB0h+var_C90], r15
0x1401eb689  mov     [rbp+0DB0h+var_C78], rax
0x1401eb690  lea     rdx, aGraphicsdriver_7; "GraphicsDrivers\\Power"
0x1401eb697  lea     rax, [rbp+0DB0h+var_DC4]
0x1401eb69b  mov     [rbp+0DB0h+var_C88], r13d
0x1401eb6a2  xor     r9d, r9d
0x1401eb6a5  mov     [rbp+0DB0h+var_C68], rax
0x1401eb6ac  mov     ecx, esi
0x1401eb6ae  mov     [rbp+0DB0h+var_C60], ebx
0x1401eb6b4  mov     [rbp+0DB0h+var_C58], r15
0x1401eb6bb  mov     [rbp+0DB0h+var_C50], r15d
0x1401eb6c2  mov     [rbp+0DB0h+var_C48], r15
0x1401eb6c9  movups  [rbp+0DB0h+var_C40], xmm0
0x1401eb6d0  mov     [rsp+0EB0h+ClientId], r15
0x1401eb6d5  movups  [rbp+0DB0h+var_C30], xmm0
0x1401eb6dc  call    cs:__imp_RtlQueryRegistryValuesEx
0x1401eb6e3  nop     dword ptr [rax+rax+00h]
0x1401eb6e8  mov     ecx, 4000004h
0x1401eb6ed  jmp     short loc_1401EB700
0x1401eb6ef  test    dword ptr [rdi+0A24h], 1000h
0x1401eb6f9  jz      short loc_1401EB700
0x1401eb6fb  mov     [rsp+0EB0h+var_E44], r15d
0x1401eb700  lea     rax, aEnableruntimep; "EnableRuntimePowerManagement"
0x1401eb707  mov     [rbp+0DB0h+var_C20], r15
0x1401eb70e  mov     [rbp+0DB0h+var_C10], rax
0x1401eb715  lea     rax, [rsp+0EB0h+var_E58]
0x1401eb71a  mov     [rbp+0DB0h+var_C08], rax
0x1401eb721  lea     rax, [rsp+0EB0h+var_E5C]
0x1401eb726  mov     [rbp+0DB0h+var_BF8], rax
0x1401eb72d  lea     rax, aDisabledevicep; "DisableDevicePowerRequired"
0x1401eb734  mov     [rbp+0DB0h+var_BD8], rax
0x1401eb73b  lea     rax, [rsp+0EB0h+var_E54]
0x1401eb740  mov     [rbp+0DB0h+var_BD0], rax
0x1401eb747  lea     rax, [rsp+0EB0h+var_E48]
0x1401eb74c  mov     [rbp+0DB0h+var_BC0], rax
0x1401eb753  lea     rax, aDefaultlatency_3; "DefaultLatencyToleranceOther"
0x1401eb75a  mov     [rbp+0DB0h+var_BA0], rax
0x1401eb761  lea     rax, [rbp+0DB0h+var_E2C]
0x1401eb765  mov     [rbp+0DB0h+var_B98], rax
0x1401eb76c  lea     rax, [rbp+0DB0h+var_D08]
0x1401eb773  mov     [rbp+0DB0h+var_B88], rax
0x1401eb77a  lea     rax, aDefaultexpecte; "DefaultExpectedResidency"
0x1401eb781  mov     [rbp+0DB0h+var_B68], rax
0x1401eb788  lea     rax, [rbp+0DB0h+var_E28]
0x1401eb78c  mov     [rbp+0DB0h+var_B60], rax
0x1401eb793  lea     rax, [rbp+0DB0h+var_D04]
0x1401eb79a  mov     [rbp+0DB0h+var_B50], rax
0x1401eb7a1  lea     rax, aDefaultlatency; "DefaultLatencyToleranceIdle0"
0x1401eb7a8  mov     [rbp+0DB0h+var_B30], rax
0x1401eb7af  lea     rax, [rbp+0DB0h+var_E08]
0x1401eb7b3  mov     [rbp+0DB0h+var_B28], rax
0x1401eb7ba  lea     rax, [rbp+0DB0h+var_D98]
0x1401eb7be  mov     [rbp+0DB0h+var_B18], rax
0x1401eb7c5  lea     rax, aDefaultlatency_0; "DefaultLatencyToleranceIdle1"
0x1401eb7cc  mov     [rbp+0DB0h+var_AF8], rax
0x1401eb7d3  lea     rax, [rbp+0DB0h+var_E04]
0x1401eb7d7  mov     [rbp+0DB0h+var_AF0], rax
0x1401eb7de  lea     rax, [rbp+0DB0h+var_D94]
0x1401eb7e2  mov     [rbp+0DB0h+var_AE0], rax
0x1401eb7e9  lea     rax, aDefaultlatency_4; "DefaultLatencyToleranceNoContext"
0x1401eb7f0  mov     [rbp+0DB0h+var_AC0], rax
0x1401eb7f7  lea     rax, [rbp+0DB0h+var_E00]
0x1401eb7fb  mov     [rbp+0DB0h+var_AB8], rax
0x1401eb802  lea     rax, [rbp+0DB0h+var_D90]
0x1401eb806  mov     [rbp+0DB0h+var_AA8], rax
0x1401eb80d  lea     rax, aDefaultlatency_5; "DefaultLatencyToleranceIdle0MonitorOff"
0x1401eb814  mov     [rbp+0DB0h+var_A88], rax
0x1401eb81b  lea     rax, [rbp+0DB0h+var_DF8]
0x1401eb81f  mov     [rbp+0DB0h+var_A80], rax
0x1401eb826  lea     rax, [rbp+0DB0h+var_D8C]
0x1401eb82a  mov     [rbp+0DB0h+var_A70], rax
0x1401eb831  mov     [rbp+0DB0h+var_C18], r13d
0x1401eb838  mov     [rbp+0DB0h+var_C00], ecx
0x1401eb83e  mov     [rbp+0DB0h+var_BF0], ebx
0x1401eb844  mov     [rbp+0DB0h+var_BE8], r15
0x1401eb84b  mov     [rbp+0DB0h+var_BE0], r13d
0x1401eb852  mov     [rbp+0DB0h+var_BC8], ecx
0x1401eb858  mov     [rbp+0DB0h+var_BB8], ebx
0x1401eb85e  mov     [rbp+0DB0h+var_BB0], r15
0x1401eb865  mov     [rbp+0DB0h+var_BA8], r13d
0x1401eb86c  mov     [rbp+0DB0h+var_B90], ecx
0x1401eb872  mov     [rbp+0DB0h+var_B80], ebx
0x1401eb878  mov     [rbp+0DB0h+var_B78], r15
0x1401eb87f  mov     [rbp+0DB0h+var_B70], r13d
0x1401eb886  mov     [rbp+0DB0h+var_B58], ecx
0x1401eb88c  mov     [rbp+0DB0h+var_B48], ebx
0x1401eb892  mov     [rbp+0DB0h+var_B40], r15
0x1401eb899  mov     [rbp+0DB0h+var_B38], r13d
0x1401eb8a0  mov     [rbp+0DB0h+var_B20], ecx
0x1401eb8a6  mov     [rbp+0DB0h+var_B10], ebx
0x1401eb8ac  mov     [rbp+0DB0h+var_B08], r15
0x1401eb8b3  mov     [rbp+0DB0h+var_B00], r13d
0x1401eb8ba  mov     [rbp+0DB0h+var_AE8], ecx
0x1401eb8c0  mov     [rbp+0DB0h+var_AD8], ebx
0x1401eb8c6  mov     [rbp+0DB0h+var_AD0], r15
0x1401eb8cd  mov     [rbp+0DB0h+var_AC8], r13d
0x1401eb8d4  mov     [rbp+0DB0h+var_AB0], ecx
0x1401eb8da  mov     [rbp+0DB0h+var_AA0], ebx
0x1401eb8e0  mov     [rbp+0DB0h+var_A98], r15
0x1401eb8e7  mov     [rbp+0DB0h+var_A90], r13d
0x1401eb8ee  mov     [rbp+0DB0h+var_A78], ecx
0x1401eb8f4  mov     [rbp+0DB0h+var_A68], ebx
0x1401eb8fa  mov     [rbp+0DB0h+var_A60], r15
0x1401eb901  lea     rax, aDefaultlatency_8; "DefaultLatencyToleranceIdle1MonitorOff"
0x1401eb908  mov     [rbp+0DB0h+var_A58], r13d
0x1401eb90f  mov     [rbp+0DB0h+var_A50], rax
0x1401eb916  lea     rax, [rbp+0DB0h+var_DF4]
0x1401eb91a  mov     [rbp+0DB0h+var_A48], rax
0x1401eb921  lea     rax, [rbp+0DB0h+var_D88]
0x1401eb925  mov     [rbp+0DB0h+var_A38], rax
0x1401eb92c  lea     rax, aDefaultlatency_2; "DefaultLatencyToleranceNoContextMonitor"...
0x1401eb933  mov     [rbp+0DB0h+var_A18], rax
0x1401eb93a  lea     rax, [rbp+0DB0h+var_DF0]
0x1401eb93e  mov     [rbp+0DB0h+var_A10], rax
0x1401eb945  lea     rax, [rbp+0DB0h+var_D84]
0x1401eb949  mov     [rbp+0DB0h+var_A00], rax
0x1401eb950  lea     rax, aDefaultlatency_7; "DefaultLatencyToleranceTimerPeriod"
0x1401eb957  mov     [rbp+0DB0h+var_9E0], rax
0x1401eb95e  lea     rax, [rbp+0DB0h+var_E0C]
0x1401eb962  mov     [rbp+0DB0h+var_9D8], rax
0x1401eb969  lea     rax, [rbp+0DB0h+var_D80]
0x1401eb96d  mov     [rbp+0DB0h+var_9C8], rax
0x1401eb974  lea     rax, aDefaultidlethr; "DefaultIdleThresholdIdle0"
0x1401eb97b  mov     [rbp+0DB0h+var_9A8], rax
0x1401eb982  lea     rax, [rbp+0DB0h+var_DFC]
0x1401eb986  mov     [rbp+0DB0h+var_9A0], rax
0x1401eb98d  lea     rax, [rbp+0DB0h+var_D7C]
0x1401eb991  mov     [rbp+0DB0h+var_990], rax
0x1401eb998  lea     rax, aDefaultidlethr_0; "DefaultIdleThresholdIdle0MonitorOff"
0x1401eb99f  mov     [rbp+0DB0h+var_970], rax
0x1401eb9a6  lea     rax, [rbp+0DB0h+var_D78]
0x1401eb9aa  mov     [rbp+0DB0h+var_968], rax
0x1401eb9b1  lea     rax, [rbp+0DB0h+var_D74]
0x1401eb9b5  mov     [rbp+0DB0h+var_958], rax
0x1401eb9bc  lea     rax, aMonitorlatency; "MonitorLatencyTolerance"
0x1401eb9c3  mov     [rbp+0DB0h+var_938], rax
0x1401eb9ca  lea     rax, [rbp+0DB0h+var_DA8]
0x1401eb9ce  mov     [rbp+0DB0h+var_930], rax
0x1401eb9d5  lea     rax, [rbp+0DB0h+var_D70]
0x1401eb9d9  mov     [rbp+0DB0h+var_920], rax
0x1401eb9e0  lea     rax, aMonitorrefresh; "MonitorRefreshLatencyTolerance"
0x1401eb9e7  mov     [rbp+0DB0h+var_900], rax
0x1401eb9ee  lea     rax, [rbp+0DB0h+var_DAC]
0x1401eb9f2  mov     [rbp+0DB0h+var_8F8], rax
0x1401eb9f9  lea     rax, [rbp+0DB0h+var_D6C]
0x1401eb9fd  mov     [rbp+0DB0h+var_8E8], rax
0x1401eba04  lea     rax, aDefaultpowerno; "DefaultPowerNotRequiredTimeout"
0x1401eba0b  mov     [rbp+0DB0h+var_8C8], rax
0x1401eba12  lea     rax, [rbp+0DB0h+var_DA4]
0x1401eba16  mov     [rbp+0DB0h+var_8C0], rax
0x1401eba1d  lea     rax, [rbp+0DB0h+var_D68]
0x1401eba21  mov     [rbp+0DB0h+var_8B0], rax
  ... truncated ...
```
