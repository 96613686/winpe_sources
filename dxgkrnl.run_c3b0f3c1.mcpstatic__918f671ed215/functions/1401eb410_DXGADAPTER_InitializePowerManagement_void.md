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
  __int64 v8; // rdx
  __int64 v9; // rsi
  unsigned int v10; // r13d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  unsigned int NumDifferentPhysicalAdapters; // r15d
  __int64 v15; // rax
  DXGADAPTER *v16; // rcx
  __int64 v17; // r8
  int AdapterInfo; // eax
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  const wchar_t *v22; // r9
  __int64 v23; // rax
  char *v24; // r14
  unsigned int v25; // ecx
  unsigned int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // edx
  __int64 v30; // r15
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rbx
  int v34; // eax
  __int16 v35; // dx
  int v36; // ecx
  __int64 v37; // rsi
  __int64 v38; // rbx
  unsigned int v39; // eax
  int v40; // eax
  const wchar_t *v41; // r9
  void *v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r11
  unsigned int v45; // r9d
  unsigned int v46; // r10d
  unsigned int v47; // ecx
  unsigned __int64 v48; // r10
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // edx
  __int64 i; // r8
  __int64 v54; // r10
  __int64 v55; // r9
  unsigned int v56; // edx
  __int64 j; // rax
  __int64 v58; // rbx
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rsi
  int v62; // eax
  __int64 v63; // rax
  unsigned int k; // ecx
  __int64 v65; // rdx
  __int64 v66; // rax
  void *v67; // rcx
  unsigned int v68; // eax
  unsigned int v69; // edx
  __int64 v70; // r8
  __int64 v71; // r10
  __int64 v72; // rax
  unsigned int v73; // ebx
  __int64 v74; // r9
  unsigned int m; // ecx
  __int64 v76; // r10
  __int64 v77; // rsi
  unsigned int v78; // r11d
  __int64 v79; // r15
  __int64 v80; // rbx
  __int64 v81; // rbx
  __int64 v82; // rbx
  ADAPTER_RENDER *v83; // rcx
  int v84; // eax
  const wchar_t *v85; // r9
  ADAPTER_DISPLAY *v86; // rcx
  int v87; // eax
  __int64 v88; // r15
  const wchar_t *v89; // r9
  int v90; // eax
  ULONG TimeIncrement; // eax
  __int64 v92; // rcx
  unsigned __int64 v93; // r9
  __int64 v94; // rax
  unsigned __int64 v95; // rtt
  __int64 v96; // rdx
  __int64 v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rax
  unsigned __int64 v106; // rtt
  __int64 v107; // rax
  unsigned __int64 v108; // rtt
  __int64 v109; // rax
  __int64 v110; // rcx
  __int64 v111; // rax
  unsigned __int64 v112; // rtt
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
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rsi
  __int64 v132; // rbx
  __int64 v133; // rdx
  __int64 v134; // r15
  int v135; // ecx
  int v136; // ecx
  int v137; // ecx
  int v138; // ecx
  int v139; // ecx
  int v140; // ecx
  DXGADAPTER *v141; // rcx
  unsigned int v142; // edx
  unsigned __int64 v143; // r8
  DXGADAPTER **v144; // rcx
  __int64 v145; // rax
  DXGADAPTER **v146; // rcx
  unsigned __int64 v147; // rdx
  unsigned int v148; // r9d
  unsigned int n; // r8d
  unsigned __int64 v150; // rax
  unsigned int ii; // ecx
  unsigned int v152; // edx
  unsigned __int64 v153; // r8
  __int64 v154; // rcx
  __int64 v155; // rax
  __int64 v156; // r8
  __int64 v157; // rbx
  NTSTATUS v158; // eax
  int v159; // eax
  __int64 StartRoutine; // [rsp+28h] [rbp-D8h]
  char v161; // [rsp+50h] [rbp-B0h]
  int v162; // [rsp+54h] [rbp-ACh] BYREF
  int v163; // [rsp+58h] [rbp-A8h] BYREF
  int v164; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v165; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v166; // [rsp+68h] [rbp-98h] BYREF
  BOOL v167; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v168; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v169; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v170; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v171; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v172; // [rsp+80h] [rbp-80h]
  unsigned int v173; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v174; // [rsp+88h] [rbp-78h] BYREF
  void *v175; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v176; // [rsp+98h] [rbp-68h] BYREF
  int v177; // [rsp+9Ch] [rbp-64h] BYREF
  int v178; // [rsp+A0h] [rbp-60h] BYREF
  int v179; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v180; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v181; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v182; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v183; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v184; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v185; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v186; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v187; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v188; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v189; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v190; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v191; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned int v192; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v193; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int v194; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v195; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v196; // [rsp+E8h] [rbp-18h] BYREF
  int v197; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v198; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v199; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v200; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v201; // [rsp+FCh] [rbp-4h] BYREF
  unsigned int v202; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v203; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v204; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v205; // [rsp+10Ch] [rbp+Ch] BYREF
  int v206; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v207; // [rsp+114h] [rbp+14h] BYREF
  int v208; // [rsp+118h] [rbp+18h] BYREF
  int v209; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v210; // [rsp+120h] [rbp+20h] BYREF
  int v211; // [rsp+124h] [rbp+24h] BYREF
  int v212; // [rsp+128h] [rbp+28h] BYREF
  int v213; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v214; // [rsp+130h] [rbp+30h] BYREF
  int v215; // [rsp+134h] [rbp+34h] BYREF
  int v216; // [rsp+138h] [rbp+38h] BYREF
  int v217; // [rsp+13Ch] [rbp+3Ch] BYREF
  int v218; // [rsp+140h] [rbp+40h] BYREF
  int v219; // [rsp+144h] [rbp+44h] BYREF
  int v220; // [rsp+148h] [rbp+48h] BYREF
  int v221; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v222; // [rsp+150h] [rbp+50h] BYREF
  int v223; // [rsp+154h] [rbp+54h] BYREF
  int v224; // [rsp+158h] [rbp+58h] BYREF
  int v225; // [rsp+15Ch] [rbp+5Ch] BYREF
  int v226; // [rsp+160h] [rbp+60h] BYREF
  int v227; // [rsp+164h] [rbp+64h] BYREF
  int v228; // [rsp+168h] [rbp+68h] BYREF
  int v229; // [rsp+16Ch] [rbp+6Ch] BYREF
  int v230; // [rsp+170h] [rbp+70h] BYREF
  int v231; // [rsp+174h] [rbp+74h] BYREF
  int v232; // [rsp+178h] [rbp+78h] BYREF
  int v233; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v234; // [rsp+180h] [rbp+80h] BYREF
  int v235; // [rsp+184h] [rbp+84h] BYREF
  int v236; // [rsp+188h] [rbp+88h] BYREF
  int v237; // [rsp+18Ch] [rbp+8Ch] BYREF
  int v238; // [rsp+190h] [rbp+90h] BYREF
  int v239; // [rsp+194h] [rbp+94h] BYREF
  int v240; // [rsp+198h] [rbp+98h] BYREF
  int v241; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v242; // [rsp+1A0h] [rbp+A0h] BYREF
  int v243; // [rsp+1A4h] [rbp+A4h] BYREF
  int v244; // [rsp+1A8h] [rbp+A8h] BYREF
  int v245; // [rsp+1ACh] [rbp+ACh] BYREF
  __int64 v246; // [rsp+1B0h] [rbp+B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v248; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v249; // [rsp+218h] [rbp+118h]
  __int64 v250; // [rsp+220h] [rbp+120h] BYREF
  int v251; // [rsp+228h] [rbp+128h]
  const wchar_t *v252; // [rsp+230h] [rbp+130h]
  BOOL *v253; // [rsp+238h] [rbp+138h]
  int v254; // [rsp+240h] [rbp+140h]
  int *v255; // [rsp+248h] [rbp+148h]
  int v256; // [rsp+250h] [rbp+150h]
  __int64 v257; // [rsp+258h] [rbp+158h]
  int v258; // [rsp+260h] [rbp+160h]
  __int64 v259; // [rsp+268h] [rbp+168h]
  __int128 v260; // [rsp+270h] [rbp+170h]
  __int128 v261; // [rsp+280h] [rbp+180h]
  __int64 v262; // [rsp+290h] [rbp+190h] BYREF
  int v263; // [rsp+298h] [rbp+198h]
  const wchar_t *v264; // [rsp+2A0h] [rbp+1A0h]
  int *v265; // [rsp+2A8h] [rbp+1A8h]
  int v266; // [rsp+2B0h] [rbp+1B0h]
  int *v267; // [rsp+2B8h] [rbp+1B8h]
  int v268; // [rsp+2C0h] [rbp+1C0h]
  __int64 v269; // [rsp+2C8h] [rbp+1C8h]
  int v270; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v271; // [rsp+2D8h] [rbp+1D8h]
  int *v272; // [rsp+2E0h] [rbp+1E0h]
  int v273; // [rsp+2E8h] [rbp+1E8h]
  int *v274; // [rsp+2F0h] [rbp+1F0h]
  int v275; // [rsp+2F8h] [rbp+1F8h]
  __int64 v276; // [rsp+300h] [rbp+200h]
  int v277; // [rsp+308h] [rbp+208h]
  const wchar_t *v278; // [rsp+310h] [rbp+210h]
  unsigned int *v279; // [rsp+318h] [rbp+218h]
  int v280; // [rsp+320h] [rbp+220h]
  int *v281; // [rsp+328h] [rbp+228h]
  int v282; // [rsp+330h] [rbp+230h]
  __int64 v283; // [rsp+338h] [rbp+238h]
  int v284; // [rsp+340h] [rbp+240h]
  const wchar_t *v285; // [rsp+348h] [rbp+248h]
  unsigned int *v286; // [rsp+350h] [rbp+250h]
  int v287; // [rsp+358h] [rbp+258h]
  int *v288; // [rsp+360h] [rbp+260h]
  int v289; // [rsp+368h] [rbp+268h]
  __int64 v290; // [rsp+370h] [rbp+270h]
  int v291; // [rsp+378h] [rbp+278h]
  const wchar_t *v292; // [rsp+380h] [rbp+280h]
  unsigned int *v293; // [rsp+388h] [rbp+288h]
  int v294; // [rsp+390h] [rbp+290h]
  int *v295; // [rsp+398h] [rbp+298h]
  int v296; // [rsp+3A0h] [rbp+2A0h]
  __int64 v297; // [rsp+3A8h] [rbp+2A8h]
  int v298; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v299; // [rsp+3B8h] [rbp+2B8h]
  unsigned int *v300; // [rsp+3C0h] [rbp+2C0h]
  int v301; // [rsp+3C8h] [rbp+2C8h]
  int *v302; // [rsp+3D0h] [rbp+2D0h]
  int v303; // [rsp+3D8h] [rbp+2D8h]
  __int64 v304; // [rsp+3E0h] [rbp+2E0h]
  int v305; // [rsp+3E8h] [rbp+2E8h]
  const wchar_t *v306; // [rsp+3F0h] [rbp+2F0h]
  unsigned int *v307; // [rsp+3F8h] [rbp+2F8h]
  int v308; // [rsp+400h] [rbp+300h]
  int *v309; // [rsp+408h] [rbp+308h]
  int v310; // [rsp+410h] [rbp+310h]
  __int64 v311; // [rsp+418h] [rbp+318h]
  int v312; // [rsp+420h] [rbp+320h]
  const wchar_t *v313; // [rsp+428h] [rbp+328h]
  unsigned int *v314; // [rsp+430h] [rbp+330h]
  int v315; // [rsp+438h] [rbp+338h]
  int *v316; // [rsp+440h] [rbp+340h]
  int v317; // [rsp+448h] [rbp+348h]
  __int64 v318; // [rsp+450h] [rbp+350h]
  int v319; // [rsp+458h] [rbp+358h]
  const wchar_t *v320; // [rsp+460h] [rbp+360h]
  unsigned int *v321; // [rsp+468h] [rbp+368h]
  int v322; // [rsp+470h] [rbp+370h]
  int *v323; // [rsp+478h] [rbp+378h]
  int v324; // [rsp+480h] [rbp+380h]
  __int64 v325; // [rsp+488h] [rbp+388h]
  int v326; // [rsp+490h] [rbp+390h]
  const wchar_t *v327; // [rsp+498h] [rbp+398h]
  unsigned int *v328; // [rsp+4A0h] [rbp+3A0h]
  int v329; // [rsp+4A8h] [rbp+3A8h]
  int *v330; // [rsp+4B0h] [rbp+3B0h]
  int v331; // [rsp+4B8h] [rbp+3B8h]
  __int64 v332; // [rsp+4C0h] [rbp+3C0h]
  int v333; // [rsp+4C8h] [rbp+3C8h]
  const wchar_t *v334; // [rsp+4D0h] [rbp+3D0h]
  int *v335; // [rsp+4D8h] [rbp+3D8h]
  int v336; // [rsp+4E0h] [rbp+3E0h]
  int *v337; // [rsp+4E8h] [rbp+3E8h]
  int v338; // [rsp+4F0h] [rbp+3F0h]
  __int64 v339; // [rsp+4F8h] [rbp+3F8h]
  int v340; // [rsp+500h] [rbp+400h]
  const wchar_t *v341; // [rsp+508h] [rbp+408h]
  unsigned int *v342; // [rsp+510h] [rbp+410h]
  int v343; // [rsp+518h] [rbp+418h]
  int *v344; // [rsp+520h] [rbp+420h]
  int v345; // [rsp+528h] [rbp+428h]
  __int64 v346; // [rsp+530h] [rbp+430h]
  int v347; // [rsp+538h] [rbp+438h]
  const wchar_t *v348; // [rsp+540h] [rbp+440h]
  int *v349; // [rsp+548h] [rbp+448h]
  int v350; // [rsp+550h] [rbp+450h]
  int *v351; // [rsp+558h] [rbp+458h]
  int v352; // [rsp+560h] [rbp+460h]
  __int64 v353; // [rsp+568h] [rbp+468h]
  int v354; // [rsp+570h] [rbp+470h]
  const wchar_t *v355; // [rsp+578h] [rbp+478h]
  unsigned int *v356; // [rsp+580h] [rbp+480h]
  int v357; // [rsp+588h] [rbp+488h]
  int *v358; // [rsp+590h] [rbp+490h]
  int v359; // [rsp+598h] [rbp+498h]
  __int64 v360; // [rsp+5A0h] [rbp+4A0h]
  int v361; // [rsp+5A8h] [rbp+4A8h]
  const wchar_t *v362; // [rsp+5B0h] [rbp+4B0h]
  unsigned int *v363; // [rsp+5B8h] [rbp+4B8h]
  int v364; // [rsp+5C0h] [rbp+4C0h]
  int *v365; // [rsp+5C8h] [rbp+4C8h]
  int v366; // [rsp+5D0h] [rbp+4D0h]
  __int64 v367; // [rsp+5D8h] [rbp+4D8h]
  int v368; // [rsp+5E0h] [rbp+4E0h]
  const wchar_t *v369; // [rsp+5E8h] [rbp+4E8h]
  unsigned int *v370; // [rsp+5F0h] [rbp+4F0h]
  int v371; // [rsp+5F8h] [rbp+4F8h]
  int *v372; // [rsp+600h] [rbp+500h]
  int v373; // [rsp+608h] [rbp+508h]
  __int64 v374; // [rsp+610h] [rbp+510h]
  int v375; // [rsp+618h] [rbp+518h]
  const wchar_t *v376; // [rsp+620h] [rbp+520h]
  unsigned int *v377; // [rsp+628h] [rbp+528h]
  int v378; // [rsp+630h] [rbp+530h]
  int *v379; // [rsp+638h] [rbp+538h]
  int v380; // [rsp+640h] [rbp+540h]
  __int64 v381; // [rsp+648h] [rbp+548h]
  int v382; // [rsp+650h] [rbp+550h]
  const wchar_t *v383; // [rsp+658h] [rbp+558h]
  unsigned int *v384; // [rsp+660h] [rbp+560h]
  int v385; // [rsp+668h] [rbp+568h]
  int *v386; // [rsp+670h] [rbp+570h]
  int v387; // [rsp+678h] [rbp+578h]
  __int64 v388; // [rsp+680h] [rbp+580h]
  int v389; // [rsp+688h] [rbp+588h]
  const wchar_t *v390; // [rsp+690h] [rbp+590h]
  unsigned int *v391; // [rsp+698h] [rbp+598h]
  int v392; // [rsp+6A0h] [rbp+5A0h]
  int *v393; // [rsp+6A8h] [rbp+5A8h]
  int v394; // [rsp+6B0h] [rbp+5B0h]
  __int64 v395; // [rsp+6B8h] [rbp+5B8h]
  int v396; // [rsp+6C0h] [rbp+5C0h]
  const wchar_t *v397; // [rsp+6C8h] [rbp+5C8h]
  unsigned int *v398; // [rsp+6D0h] [rbp+5D0h]
  int v399; // [rsp+6D8h] [rbp+5D8h]
  int *v400; // [rsp+6E0h] [rbp+5E0h]
  int v401; // [rsp+6E8h] [rbp+5E8h]
  __int64 v402; // [rsp+6F0h] [rbp+5F0h]
  int v403; // [rsp+6F8h] [rbp+5F8h]
  const wchar_t *v404; // [rsp+700h] [rbp+600h]
  unsigned int *v405; // [rsp+708h] [rbp+608h]
  int v406; // [rsp+710h] [rbp+610h]
  int *v407; // [rsp+718h] [rbp+618h]
  int v408; // [rsp+720h] [rbp+620h]
  __int64 v409; // [rsp+728h] [rbp+628h]
  int v410; // [rsp+730h] [rbp+630h]
  const wchar_t *v411; // [rsp+738h] [rbp+638h]
  int *v412; // [rsp+740h] [rbp+640h]
  int v413; // [rsp+748h] [rbp+648h]
  int *v414; // [rsp+750h] [rbp+650h]
  int v415; // [rsp+758h] [rbp+658h]
  __int64 v416; // [rsp+760h] [rbp+660h]
  int v417; // [rsp+768h] [rbp+668h]
  const wchar_t *v418; // [rsp+770h] [rbp+670h]
  int *v419; // [rsp+778h] [rbp+678h]
  int v420; // [rsp+780h] [rbp+680h]
  int *v421; // [rsp+788h] [rbp+688h]
  int v422; // [rsp+790h] [rbp+690h]
  __int64 v423; // [rsp+798h] [rbp+698h]
  int v424; // [rsp+7A0h] [rbp+6A0h]
  const wchar_t *v425; // [rsp+7A8h] [rbp+6A8h]
  int *v426; // [rsp+7B0h] [rbp+6B0h]
  int v427; // [rsp+7B8h] [rbp+6B8h]
  int *v428; // [rsp+7C0h] [rbp+6C0h]
  int v429; // [rsp+7C8h] [rbp+6C8h]
  __int64 v430; // [rsp+7D0h] [rbp+6D0h]
  int v431; // [rsp+7D8h] [rbp+6D8h]
  const wchar_t *v432; // [rsp+7E0h] [rbp+6E0h]
  unsigned int *v433; // [rsp+7E8h] [rbp+6E8h]
  int v434; // [rsp+7F0h] [rbp+6F0h]
  int *v435; // [rsp+7F8h] [rbp+6F8h]
  int v436; // [rsp+800h] [rbp+700h]
  __int64 v437; // [rsp+808h] [rbp+708h]
  int v438; // [rsp+810h] [rbp+710h]
  const wchar_t *v439; // [rsp+818h] [rbp+718h]
  unsigned int *v440; // [rsp+820h] [rbp+720h]
  int v441; // [rsp+828h] [rbp+728h]
  int *v442; // [rsp+830h] [rbp+730h]
  int v443; // [rsp+838h] [rbp+738h]
  __int64 v444; // [rsp+840h] [rbp+740h]
  int v445; // [rsp+848h] [rbp+748h]
  const wchar_t *v446; // [rsp+850h] [rbp+750h]
  unsigned int *v447; // [rsp+858h] [rbp+758h]
  int v448; // [rsp+860h] [rbp+760h]
  int *v449; // [rsp+868h] [rbp+768h]
  int v450; // [rsp+870h] [rbp+770h]
  __int64 v451; // [rsp+878h] [rbp+778h]
  int v452; // [rsp+880h] [rbp+780h]
  const wchar_t *v453; // [rsp+888h] [rbp+788h]
  unsigned int *v454; // [rsp+890h] [rbp+790h]
  int v455; // [rsp+898h] [rbp+798h]
  int *v456; // [rsp+8A0h] [rbp+7A0h]
  int v457; // [rsp+8A8h] [rbp+7A8h]
  __int64 v458; // [rsp+8B0h] [rbp+7B0h]
  int v459; // [rsp+8B8h] [rbp+7B8h]
  const wchar_t *v460; // [rsp+8C0h] [rbp+7C0h]
  unsigned int *v461; // [rsp+8C8h] [rbp+7C8h]
  int v462; // [rsp+8D0h] [rbp+7D0h]
  int *v463; // [rsp+8D8h] [rbp+7D8h]
  int v464; // [rsp+8E0h] [rbp+7E0h]
  __int64 v465; // [rsp+8E8h] [rbp+7E8h]
  int v466; // [rsp+8F0h] [rbp+7F0h]
  const wchar_t *v467; // [rsp+8F8h] [rbp+7F8h]
  unsigned int *v468; // [rsp+900h] [rbp+800h]
  int v469; // [rsp+908h] [rbp+808h]
  int *v470; // [rsp+910h] [rbp+810h]
  int v471; // [rsp+918h] [rbp+818h]
  __int64 v472; // [rsp+920h] [rbp+820h]
  int v473; // [rsp+928h] [rbp+828h]
  const wchar_t *v474; // [rsp+930h] [rbp+830h]
  unsigned int *v475; // [rsp+938h] [rbp+838h]
  int v476; // [rsp+940h] [rbp+840h]
  int *v477; // [rsp+948h] [rbp+848h]
  int v478; // [rsp+950h] [rbp+850h]
  __int64 v479; // [rsp+958h] [rbp+858h]
  int v480; // [rsp+960h] [rbp+860h]
  const wchar_t *v481; // [rsp+968h] [rbp+868h]
  unsigned int *v482; // [rsp+970h] [rbp+870h]
  int v483; // [rsp+978h] [rbp+878h]
  int *v484; // [rsp+980h] [rbp+880h]
  int v485; // [rsp+988h] [rbp+888h]
  __int64 v486; // [rsp+990h] [rbp+890h]
  int v487; // [rsp+998h] [rbp+898h]
  const wchar_t *v488; // [rsp+9A0h] [rbp+8A0h]
  unsigned int *v489; // [rsp+9A8h] [rbp+8A8h]
  int v490; // [rsp+9B0h] [rbp+8B0h]
  int *v491; // [rsp+9B8h] [rbp+8B8h]
  int v492; // [rsp+9C0h] [rbp+8C0h]
  __int64 v493; // [rsp+9C8h] [rbp+8C8h]
  int v494; // [rsp+9D0h] [rbp+8D0h]
  const wchar_t *v495; // [rsp+9D8h] [rbp+8D8h]
  unsigned int *v496; // [rsp+9E0h] [rbp+8E0h]
  int v497; // [rsp+9E8h] [rbp+8E8h]
  int *v498; // [rsp+9F0h] [rbp+8F0h]
  int v499; // [rsp+9F8h] [rbp+8F8h]
  __int64 v500; // [rsp+A00h] [rbp+900h]
  int v501; // [rsp+A08h] [rbp+908h]
  const wchar_t *v502; // [rsp+A10h] [rbp+910h]
  unsigned int *v503; // [rsp+A18h] [rbp+918h]
  int v504; // [rsp+A20h] [rbp+920h]
  int *v505; // [rsp+A28h] [rbp+928h]
  int v506; // [rsp+A30h] [rbp+930h]
  __int64 v507; // [rsp+A38h] [rbp+938h]
  int v508; // [rsp+A40h] [rbp+940h]
  const wchar_t *v509; // [rsp+A48h] [rbp+948h]
  unsigned int *v510; // [rsp+A50h] [rbp+950h]
  int v511; // [rsp+A58h] [rbp+958h]
  int *v512; // [rsp+A60h] [rbp+960h]
  int v513; // [rsp+A68h] [rbp+968h]
  __int64 v514; // [rsp+A70h] [rbp+970h]
  int v515; // [rsp+A78h] [rbp+978h]
  const wchar_t *v516; // [rsp+A80h] [rbp+980h]
  unsigned int *v517; // [rsp+A88h] [rbp+988h]
  int v518; // [rsp+A90h] [rbp+990h]
  int *v519; // [rsp+A98h] [rbp+998h]
  int v520; // [rsp+AA0h] [rbp+9A0h]
  __int64 v521; // [rsp+AA8h] [rbp+9A8h]
  int v522; // [rsp+AB0h] [rbp+9B0h]
  const wchar_t *v523; // [rsp+AB8h] [rbp+9B8h]
  unsigned int *v524; // [rsp+AC0h] [rbp+9C0h]
  int v525; // [rsp+AC8h] [rbp+9C8h]
  int *v526; // [rsp+AD0h] [rbp+9D0h]
  int v527; // [rsp+AD8h] [rbp+9D8h]
  __int64 v528; // [rsp+AE0h] [rbp+9E0h]
  int v529; // [rsp+AE8h] [rbp+9E8h]
  const wchar_t *v530; // [rsp+AF0h] [rbp+9F0h]
  unsigned int *v531; // [rsp+AF8h] [rbp+9F8h]
  int v532; // [rsp+B00h] [rbp+A00h]
  int *v533; // [rsp+B08h] [rbp+A08h]
  int v534; // [rsp+B10h] [rbp+A10h]
  __int64 v535; // [rsp+B18h] [rbp+A18h]
  int v536; // [rsp+B20h] [rbp+A20h]
  __int64 v537; // [rsp+B28h] [rbp+A28h]
  __int128 v538; // [rsp+B30h] [rbp+A30h]
  __int128 v539; // [rsp+B40h] [rbp+A40h]
  _DWORD v540[64]; // [rsp+B50h] [rbp+A50h] BYREF
  unsigned __int16 v541[264]; // [rsp+C50h] [rbp+B50h] BYREF

  v3 = (char *)this + 3069;
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pt_EtwWriteTransfer(
      &DxgkControlGuid_Context,
      Dxgk_PowerManagementSupport,
      a3,
      this,
      (unsigned __int8)*v3);
  if ( !*v3 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 4776;
    return 0;
  }
  v227 = 0;
  v244 = -1;
  v173 = -1;
  v245 = 2000;
  v210 = 35000;
  v182 = 35000;
  v174 = 2000;
  v212 = 50000;
  v185 = 50000;
  v213 = 100000;
  v186 = 100000;
  v218 = 300000;
  v204 = 300000;
  v219 = 17000;
  v203 = 17000;
  v214 = 200;
  v179 = 200;
  v215 = 200;
  v183 = 200;
  v217 = 100;
  v216 = 100;
  v220 = 25000;
  v205 = 25000;
  v222 = 300;
  v170 = 300;
  v223 = 700;
  v171 = 700;
  v224 = 900;
  v169 = 900;
  v225 = 500;
  v168 = 500;
  v231 = 140000;
  v192 = 140000;
  v232 = 200000;
  v194 = 200000;
  v233 = 250000;
  v195 = 250000;
  v234 = 250000;
  v196 = 250000;
  v211 = 2000;
  v184 = 2000;
  v221 = 2000;
  v187 = 2000;
  v235 = 10000;
  v189 = 10000;
  v208 = 80;
  v180 = 80;
  v209 = 15000;
  v181 = 15000;
  v226 = 3;
  v178 = 3;
  v206 = 0;
  v228 = 0;
  v177 = 0;
  v229 = 80;
  v188 = 80;
  v230 = 80000;
  v190 = 80000;
  v5 = *((_DWORD *)this + 783) < 2400;
  v236 = 60000;
  v191 = 60000;
  v237 = 60000;
  v193 = 60000;
  v239 = 30000;
  v198 = 30000;
  v242 = 30000;
  v201 = 30000;
  v243 = 80000;
  v207 = 80000;
  v238 = 15000;
  v202 = 15000;
  v240 = 80;
  v199 = 80;
  v241 = 15000;
  v200 = 15000;
  v197 = 1;
  v167 = 1;
  v162 = 1;
  v163 = 1;
  v166 = 0;
  v164 = 0;
  if ( v5 )
  {
    v252 = L"UseSelfRefreshVRAMInS3";
    v254 = 67108868;
    v250 = 0;
    v253 = &v167;
    v251 = 288;
    v255 = &v197;
    v256 = 4;
    v257 = 0;
    v258 = 0;
    v259 = 0;
    v260 = 0;
    v261 = 0;
    RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\Power", &v250);
  }
  else
  {
    v167 = (*((_DWORD *)this + 649) & 0x1000) == 0;
  }
  v262 = 0;
  v264 = L"EnableRuntimePowerManagement";
  v265 = &v163;
  v267 = &v162;
  v271 = L"DisableDevicePowerRequired";
  v272 = &v164;
  v274 = (int *)&v166;
  v278 = L"DefaultLatencyToleranceOther";
  v279 = &v173;
  v281 = &v244;
  v285 = L"DefaultExpectedResidency";
  v286 = &v174;
  v288 = &v245;
  v292 = L"DefaultLatencyToleranceIdle0";
  v293 = &v180;
  v295 = &v208;
  v299 = L"DefaultLatencyToleranceIdle1";
  v300 = &v181;
  v302 = &v209;
  v306 = L"DefaultLatencyToleranceNoContext";
  v307 = &v182;
  v309 = &v210;
  v313 = L"DefaultLatencyToleranceIdle0MonitorOff";
  v314 = &v184;
  v316 = &v211;
  v263 = 288;
  v266 = 67108868;
  v268 = 4;
  v269 = 0;
  v270 = 288;
  v273 = 67108868;
  v275 = 4;
  v276 = 0;
  v277 = 288;
  v280 = 67108868;
  v282 = 4;
  v283 = 0;
  v284 = 288;
  v287 = 67108868;
  v289 = 4;
  v290 = 0;
  v291 = 288;
  v294 = 67108868;
  v296 = 4;
  v297 = 0;
  v298 = 288;
  v301 = 67108868;
  v303 = 4;
  v304 = 0;
  v305 = 288;
  v308 = 67108868;
  v310 = 4;
  v311 = 0;
  v312 = 288;
  v315 = 67108868;
  v317 = 4;
  v318 = 0;
  v319 = 288;
  v320 = L"DefaultLatencyToleranceIdle1MonitorOff";
  v321 = &v185;
  v323 = &v212;
  v327 = L"DefaultLatencyToleranceNoContextMonitorOff";
  v328 = &v186;
  v330 = &v213;
  v334 = L"DefaultLatencyToleranceTimerPeriod";
  v335 = &v179;
  v337 = &v214;
  v341 = L"DefaultIdleThresholdIdle0";
  v342 = &v183;
  v344 = &v215;
  v348 = L"DefaultIdleThresholdIdle0MonitorOff";
  v349 = &v216;
  v351 = &v217;
  v355 = L"MonitorLatencyTolerance";
  v356 = &v204;
  v358 = &v218;
  v362 = L"MonitorRefreshLatencyTolerance";
  v363 = &v203;
  v365 = &v219;
  v369 = L"DefaultPowerNotRequiredTimeout";
  v370 = &v205;
  v372 = &v220;
  v322 = 67108868;
  v324 = 4;
  v325 = 0;
  v326 = 288;
  v329 = 67108868;
  v331 = 4;
  v332 = 0;
  v333 = 288;
  v336 = 67108868;
  v338 = 4;
  v339 = 0;
  v340 = 288;
  v343 = 67108868;
  v345 = 4;
  v346 = 0;
  v347 = 288;
  v350 = 67108868;
  v352 = 4;
  v353 = 0;
  v354 = 288;
  v357 = 67108868;
  v359 = 4;
  v360 = 0;
  v361 = 288;
  v364 = 67108868;
  v366 = 4;
  v367 = 0;
  v368 = 288;
  v371 = 67108868;
  v373 = 4;
  v374 = 0;
  v375 = 288;
  v378 = 67108868;
  v376 = L"DefaultActiveIdleThreshold";
  v377 = &v187;
  v379 = &v221;
  v383 = L"ulow";
  v384 = &v170;
  v386 = &v222;
  v390 = L"uhigh";
  v391 = &v171;
  v393 = &v223;
  v397 = L"uglitch";
  v398 = &v169;
  v400 = &v224;
  v404 = L"uideal";
  v405 = &v168;
  v407 = &v225;
  v411 = L"lowdebounce";
  v412 = &v178;
  v414 = &v226;
  v418 = L"EnablePODebounce";
  v419 = &v206;
  v421 = &v227;
  v425 = L"DisablePStateManagement";
  v426 = &v177;
  v428 = &v228;
  v380 = 4;
  v381 = 0;
  v382 = 288;
  v385 = 67108868;
  v387 = 4;
  v388 = 0;
  v389 = 288;
  v392 = 67108868;
  v394 = 4;
  v395 = 0;
  v396 = 288;
  v399 = 67108868;
  v401 = 4;
  v402 = 0;
  v403 = 288;
  v406 = 67108868;
  v408 = 4;
  v409 = 0;
  v410 = 288;
  v413 = 67108868;
  v415 = 4;
  v416 = 0;
  v417 = 288;
  v420 = 67108868;
  v422 = 4;
  v423 = 0;
  v424 = 288;
  v427 = 67108868;
  v429 = 4;
  v430 = 0;
  v431 = 288;
  v432 = L"DefaultD3TransitionLatencyActivelyUsed";
  v433 = &v188;
  v435 = &v229;
  v439 = L"DefaultD3TransitionLatencyIdleShortTime";
  v440 = &v190;
  v442 = &v230;
  v446 = L"DefaultD3TransitionLatencyIdleLongTime";
  v447 = &v192;
  v449 = &v231;
  v453 = L"DefaultD3TransitionLatencyIdleVeryLongTime";
  v454 = &v194;
  v456 = &v232;
  v460 = L"DefaultD3TransitionLatencyIdleNoContext";
  v461 = &v195;
  v463 = &v233;
  v467 = L"DefaultD3TransitionLatencyIdleMonitorOff";
  v468 = &v196;
  v470 = &v234;
  v474 = L"DefaultD3TransitionIdleShortTimeThreshold";
  v475 = &v189;
  v477 = &v235;
  v481 = L"DefaultD3TransitionIdleLongTimeThreshold";
  v482 = &v191;
  v484 = &v236;
  v488 = L"DefaultD3TransitionIdleVeryLongTimeThreshold";
  v434 = 67108868;
  v436 = 4;
  v437 = 0;
  v438 = 288;
  v441 = 67108868;
  v443 = 4;
  v444 = 0;
  v445 = 288;
  v448 = 67108868;
  v450 = 4;
  v451 = 0;
  v452 = 288;
  v455 = 67108868;
  v457 = 4;
  v458 = 0;
  v459 = 288;
  v462 = 67108868;
  v464 = 4;
  v465 = 0;
  v466 = 288;
  v469 = 67108868;
  v471 = 4;
  v472 = 0;
  v473 = 288;
  v476 = 67108868;
  v478 = 4;
  v479 = 0;
  v480 = 288;
  v483 = 67108868;
  v485 = 4;
  v486 = 0;
  v487 = 288;
  v490 = 67108868;
  v489 = &v193;
  v497 = 67108868;
  v491 = &v237;
  v504 = 67108868;
  v495 = L"DefaultLatencyToleranceMemory";
  v511 = 67108868;
  v496 = &v202;
  v518 = 67108868;
  v498 = &v238;
  v502 = L"DefaultLatencyToleranceMemoryNoContext";
  v503 = &v198;
  v505 = &v239;
  v509 = L"DefaultMemoryRefreshLatencyToleranceActivelyUsed";
  v510 = &v199;
  v512 = &v240;
  v516 = L"DefaultMemoryRefreshLatencyToleranceIdleShortTime";
  v517 = &v200;
  v519 = &v241;
  v523 = L"DefaultMemoryRefreshLatencyToleranceNoContext";
  v524 = &v201;
  v526 = &v242;
  v530 = L"DefaultMemoryRefreshLatencyToleranceMonitorOff";
  v531 = &v207;
  v525 = 67108868;
  v532 = 67108868;
  v533 = &v243;
  v492 = 4;
  v493 = 0;
  v494 = 288;
  v499 = 4;
  v500 = 0;
  v501 = 288;
  v506 = 4;
  v507 = 0;
  v508 = 288;
  v513 = 4;
  v514 = 0;
  v515 = 288;
  v520 = 4;
  v521 = 0;
  v522 = 288;
  v527 = 4;
  v528 = 0;
  v529 = 288;
  v534 = 4;
  v535 = 0;
  v536 = 0;
  v537 = 0;
  v538 = 0;
  v539 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v262);
  if ( *((int *)this + 783) < 2400 )
  {
    v7 = *((_QWORD *)this + 27);
    v175 = 0;
    if ( (int)DpiGetPnpRegistryKeyName(v7, 2, &v175) >= 0
      && (int)RtlStringCbCopyW(v541, 0x208u, *((unsigned __int16 **)v175 + 1)) >= 0
      && (int)RtlStringCbCatW(v541, v8, L"\\DxgkSettings") >= 0 )
    {
      v250 = 0;
      v251 = 288;
      v252 = L"UseSelfRefreshVRAMInS3";
      v254 = 67108868;
      v253 = &v167;
      v256 = 4;
      v255 = &v197;
      v257 = 0;
      v258 = 0;
      v259 = 0;
      v260 = 0;
      v261 = 0;
      RtlQueryRegistryValuesEx(0, v541, &v250);
    }
  }
  if ( !v163 )
    return 0;
  LOBYTE(v9) = 0;
  v10 = 0;
  v11 = !v167;
  *((_BYTE *)this + 204) = v164 != 0;
  *((_BYTE *)this + 207) = !v11;
  v12 = *(_QWORD *)(*((_QWORD *)this + 27) + 64LL);
  v13 = *(_DWORD *)(*(_QWORD *)(v12 + 40) + 28LL);
  if ( v13 < 0x5019 )
    NumDifferentPhysicalAdapters = 1;
  else
    NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(this);
  v162 = NumDifferentPhysicalAdapters;
  LODWORD(v165) = 0;
  v15 = 0;
  while ( (unsigned int)v15 < NumDifferentPhysicalAdapters )
  {
    *(_QWORD *)&ObjectAttributes.Attributes = &v540[v15];
    memset(&ObjectAttributes, 0, 24);
    ObjectAttributes.Length = 6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(ObjectAttributes.SecurityDescriptor) = 4;
    if ( DXGADAPTER::IsDxgmms2(this) )
    {
      if ( v13 >= 0x5019 )
      {
        LODWORD(ObjectAttributes.ObjectName) = 4;
        ObjectAttributes.RootDirectory = &v165;
      }
    }
    AdapterInfo = DXGADAPTER::DdiQueryAdapterInfo(v16, (struct _DXGKARG_QUERYADAPTERINFO *)&ObjectAttributes, v17);
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
    v10 += v540[(unsigned int)v165];
    v15 = (unsigned int)(v165 + 1);
    LODWORD(v165) = v165 + 1;
  }
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pqq_EtwWriteTransfer(v12, (unsigned int)Dxgk_PowerManagementComponents, v6, (_DWORD)this, v9, v10);
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
  v20 = 520LL * v10;
  if ( !is_mul_ok(v10, 0x208u) )
    v20 = -1;
  v21 = operator new[](v20, 0x4B677844u, 64);
  *((_QWORD *)this + 419) = v21;
  if ( !v21 )
  {
    WdLogSingleEntry1(6, this);
    v22 = L"Adapter 0x%I64x: Out of memory allocating m_pPowerComponents";
    WdLogGlobalForLineNumber = 5004;
LABEL_36:
    DxgkLogInternalTriageEvent(0, 262145, -1, (_DWORD)v22, (__int64)this, 0, 0, 0, 0);
    LODWORD(v9) = -1073741801;
    goto LABEL_213;
  }
  v23 = operator new[](312 * v10 + 160, 0x4B677844u, 256);
  v24 = (char *)v23;
  if ( !v23 )
  {
    WdLogSingleEntry1(6, this);
    v22 = L"Adapter 0x%I64x: Out of memory allocating pRegistrationInfo";
    WdLogGlobalForLineNumber = 5021;
    goto LABEL_36;
  }
  *(_DWORD *)v23 = 3;
  *(_QWORD *)(v23 + 8) = 2;
  v25 = 0;
  *(_DWORD *)(v23 + 96) = v10;
  *(_QWORD *)(v23 + 64) = DxgkPowerRuntimeDeviceDirectedPowerUpCallback;
  *(_QWORD *)(v23 + 88) = this;
  *(_QWORD *)(v23 + 72) = DxgkPowerRuntimeDeviceDirectedPowerDownCallback;
  v246 = v23 + 56LL * v10 + 104;
  *(_QWORD *)(v23 + 32) = DxgkPowerRuntimeComponentIdleStateCallback;
  v26 = 0;
  v172 = 0;
  *(_QWORD *)(v23 + 16) = DxgkPowerRuntimeComponentActiveCallback;
  *(_QWORD *)(v23 + 24) = DxgkPowerRuntimeComponentIdleCallback;
  *(_QWORD *)(v23 + 40) = DxgkPowerRuntimeDevicePowerRequiredCallback;
  *(_QWORD *)(v23 + 48) = DxgkPowerRuntimeDevicePowerNotRequiredCallback;
  *(_QWORD *)(v23 + 56) = DxgkPowerRuntimeControlCallback;
  v175 = (void *)(v23 + 56LL * v10 + 104 + 192LL * v10);
  v27 = 0;
  memset(&v248, 0, sizeof(v248));
  v164 = 0;
  v248.Type = DXGKQAITYPE_POWERCOMPONENTINFO;
  v248.InputDataSize = 4;
  v248.OutputDataSize = 336;
LABEL_40:
  v163 = v25;
  if ( v25 >= NumDifferentPhysicalAdapters )
  {
    if ( *((_DWORD *)this + 876) == -1 && !*((_BYTE *)this + 3792) )
      *((_QWORD *)this + 464) = 0;
    if ( *((int *)this + 783) < 1300 || !v26 || v177 )
      goto LABEL_152;
    if ( v170 > 0x3E8 || v171 > 0x3E8 || v169 > 0x3E8 || v168 > 0x3E8 || v170 >= v168 || v168 >= v171 || v171 >= v169 )
    {
      WdLogSingleEntry4(2, v170, v171, v169, v168);
      WdLogGlobalForLineNumber = 5322;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"P-State engine regkey validation error - low: 0x%I64x high: 0x%I64x glitch: 0x%I64x ideal: 0x%I64x",
        v170,
        v171,
        v169,
        v168,
        0);
      goto LABEL_98;
    }
    v50 = 248LL * v26;
    v248.Type = DXGKQAITYPE_POWERCOMPONENTPSTATEINFO;
    v248.OutputDataSize = 136;
    if ( !is_mul_ok(v26, 0xF8u) )
      v50 = -1;
    v51 = operator new[](v50, 0x4B677844u, 64);
    *((_QWORD *)this + 569) = v51;
    *((_DWORD *)this + 1140) = v26;
    if ( !v51 )
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
    v52 = 0;
    for ( i = 0; v52 < *((_DWORD *)this + 874); ++v52 )
    {
      v54 = *((_QWORD *)this + 419);
      v55 = 520LL * v52;
      if ( !*(_DWORD *)(v55 + v54 + 208) )
      {
        *(_QWORD *)(v55 + v54 + 512) = *((_QWORD *)this + 569) + 248LL * (unsigned int)i;
        i = (unsigned int)(i + 1);
      }
    }
    v56 = 0;
    *((_DWORD *)this + 1192) = v169;
    *((_DWORD *)this + 1193) = v171;
    *((_DWORD *)this + 1194) = v170;
    *((_DWORD *)this + 1195) = v168;
    *((_DWORD *)this + 1196) = v178;
    for ( j = 0; ; j = v56 )
    {
      LODWORD(v165) = v56;
      if ( (unsigned int)j >= v10 )
        goto LABEL_138;
      v58 = *(_QWORD *)(520 * j + *((_QWORD *)this + 419) + 512);
      if ( v58 )
      {
        v248.pOutputData = *(void **)(520 * j + *((_QWORD *)this + 419) + 512);
        v248.pInputData = &v165;
        v59 = DXGADAPTER::DdiQueryAdapterInfo(this, &v248, i);
        v61 = v59;
        if ( v59 < 0 )
        {
          v63 = WdLogNewEntry5_WdTrace(v60);
          *(_QWORD *)(v63 + 24) = (unsigned int)v165;
          *(_QWORD *)(v63 + 32) = v61;
          WdLogGlobalForLineNumber = 5388;
          for ( k = 0; k < *((_DWORD *)this + 874); ++k )
          {
            v65 = 520LL * k;
            v66 = *((_QWORD *)this + 419);
            if ( !*(_DWORD *)(v65 + v66 + 208) )
              *(_QWORD *)(v65 + v66 + 512) = 0;
          }
          v67 = (void *)*((_QWORD *)this + 569);
          *((_DWORD *)this + 1140) = 0;
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v67);
          *((_QWORD *)this + 569) = 0;
LABEL_138:
          v68 = *((_DWORD *)this + 1140);
          v69 = 0;
          v176 = v68;
          while ( v69 < v68 )
          {
            v70 = *((_QWORD *)this + 569);
            v71 = v69;
            v72 = 248LL * v69;
            v73 = *(_DWORD *)(v72 + v70);
            v74 = *(unsigned int *)(v72 + v70 + 144);
            if ( v73 > 0x20 )
            {
              v82 = *(unsigned int *)(v72 + v70 + 144);
              WdLogSingleEntry1(2, v82);
              WdLogGlobalForLineNumber = 5443;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"P-State StateCount cannot be larger than DXGK_MAX_P_STATES. Component:0x%I64x",
                v82,
                0,
                0,
                0,
                0);
              goto LABEL_98;
            }
            for ( m = 0; m < v73; ++m )
            {
              v76 = 62 * v71;
              v77 = m;
              v78 = *(_DWORD *)(v70 + 4 * (v76 + m) + 4);
              if ( !v78 )
              {
                v81 = *(unsigned int *)(v72 + v70 + 144);
                WdLogSingleEntry2(2, v74, m);
                WdLogGlobalForLineNumber = 5456;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"P-State cannot specify 0 operating frequency. Component:0x%I64x, P-State:0x%I64x",
                  v81,
                  v77,
                  0,
                  0,
                  0);
                goto LABEL_92;
              }
              if ( m )
              {
                v79 = m - 1;
                if ( v78 > *(_DWORD *)(v70 + 4 * (v76 + v79) + 4) )
                {
                  v80 = *(unsigned int *)(v72 + v70 + 144);
                  WdLogSingleEntry3(2, v74, m, m - 1);
                  WdLogGlobalForLineNumber = 5466;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"P-States must have monotonically decreasing operating frequency. Component:0x%I64x, P-"
                                   "State1:0x%I64x, P-State2:0x%I64x",
                    v80,
                    v77,
                    v79,
                    0,
                    0);
                  goto LABEL_92;
                }
              }
              v71 = v69;
            }
            v68 = v176;
            ++v69;
          }
LABEL_152:
          v83 = (ADAPTER_RENDER *)*((_QWORD *)this + 407);
          *((_DWORD *)this + 946) = v179;
          if ( v83 )
          {
            v84 = ADAPTER_RENDER::InitializePowerManagement(v83);
            v9 = v84;
            if ( v84 < 0 )
            {
              WdLogSingleEntry2(2, v84, 7);
              WdLogGlobalForLineNumber = 5482;
              v85 = L"InitializePowerManagement failed for render adapter:0x%I64x";
              StartRoutine = 7;
LABEL_155:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v85, v9, StartRoutine, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v86 = (ADAPTER_DISPLAY *)*((_QWORD *)this + 406);
          if ( v86 )
          {
            v87 = ADAPTER_DISPLAY::InitializePowerManagement(v86);
            v9 = v87;
            if ( v87 < 0 )
            {
              v88 = 8;
              WdLogSingleEntry2(2, v87, 8);
              WdLogGlobalForLineNumber = 5492;
              v89 = L"InitializePowerManagement failed for display adapter:0x%I64x";
LABEL_211:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v89, v9, v88, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v90 = PoFxRegisterDevice(*((_QWORD *)this + 27), v24, (char *)this + 3360);
          v9 = v90;
          if ( v90 < 0 )
          {
            WdLogSingleEntry1(2, v90);
            WdLogGlobalForLineNumber = 5500;
            v85 = L"PoFxRegisterDevice failed with status:0x%I64x";
            StartRoutine = 0;
            goto LABEL_155;
          }
          KeInitializeEvent((PRKEVENT)((char *)this + 3520), SynchronizationEvent, 0);
          *((_QWORD *)this + 476) = (char *)this + 3800;
          *((_QWORD *)this + 475) = (char *)this + 3800;
          *((_BYTE *)this + 3788) = 0;
          TimeIncrement = KeQueryTimeIncrement();
          v92 = v180;
          v93 = TimeIncrement;
          *((_QWORD *)this + 446) = 0;
          *((_QWORD *)this + 448) = 0;
          *((_QWORD *)this + 452) = 0;
          *((_QWORD *)this + 454) = 0;
          *((_QWORD *)this + 443) = 10 * v92;
          v94 = v182;
          *((_QWORD *)this + 445) = 10LL * v181;
          v95 = 10000LL * v183;
          *((_QWORD *)this + 447) = 10 * v94;
          v96 = (unsigned int)(v95 / v93);
          v97 = v184;
          *((_QWORD *)this + 444) = v96;
          *((_QWORD *)this + 450) = v96;
          v98 = 5 * v97;
          v99 = v185;
          *((_QWORD *)this + 449) = 2 * v98;
          v100 = 5 * v99;
          v101 = v186;
          *((_QWORD *)this + 451) = 2 * v100;
          v102 = 5 * v101;
          v103 = v187;
          *((_QWORD *)this + 453) = 2 * v102;
          *((_QWORD *)this + 455) = (char *)this + 3544;
          v104 = 5 * v103;
          v105 = v188;
          *((_QWORD *)this + 487) = 2 * v104;
          v106 = 10000LL * v189;
          *((_QWORD *)this + 456) = 10 * v105;
          v107 = v190;
          *((_QWORD *)this + 457) = (unsigned int)(v106 / v93);
          v108 = 10000LL * v191;
          *((_QWORD *)this + 458) = 10 * v107;
          v109 = v192;
          *((_QWORD *)this + 459) = (unsigned int)(v108 / v93);
          v110 = 5 * v109;
          v111 = 10000LL * v193;
          *((_QWORD *)this + 460) = 2 * v110;
          v112 = v111;
          v113 = v194;
          *((_QWORD *)this + 461) = (unsigned int)(v112 / v93);
          *((_QWORD *)this + 463) = 0;
          v161 = 0;
          v114 = 5 * v113;
          v115 = v195;
          *((_QWORD *)this + 462) = 2 * v114;
          v116 = 5 * v115;
          v117 = v196;
          *((_QWORD *)this + 465) = 2 * v116;
          v118 = 5 * v117;
          v119 = v202;
          *((_QWORD *)this + 466) = 2 * v118;
          v120 = 5 * v119;
          v121 = v198;
          *((_QWORD *)this + 467) = 2 * v120;
          v122 = 5 * v121;
          v123 = v199;
          *((_QWORD *)this + 468) = 2 * v122;
          v124 = 5 * v123;
          v125 = v200;
          *((_QWORD *)this + 469) = 2 * v124;
          v126 = 5 * v125;
          v127 = v201;
          *((_QWORD *)this + 470) = 2 * v126;
          v128 = 5 * v127;
          v129 = v207;
          *((_QWORD *)this + 471) = 2 * v128;
          *((_QWORD *)this + 472) = 10 * v129;
          *((_QWORD *)this + 481) = (char *)this + 3840;
          *((_QWORD *)this + 480) = (char *)this + 3840;
          KeInitializeSpinLock((PKSPIN_LOCK)this + 486);
          v130 = 0;
          v162 = 0;
          while ( 2 )
          {
            v131 = *((_QWORD *)this + 419);
            v132 = 520 * v130;
            v133 = 520 * v130 + v131 + 424;
            *(_BYTE *)(520 * v130 + v131 + 356) = 1;
            v134 = 520 * v130 + v131;
            *(_OWORD *)v133 = 0;
            v135 = *(_DWORD *)(v134 + 208);
            if ( v135 )
            {
              v136 = v135 - 1;
              if ( v136 )
              {
                v137 = v136 - 1;
                if ( v137 )
                {
                  v138 = v137 - 1;
                  if ( v138 )
                  {
                    v139 = v138 - 1;
                    if ( v139 )
                    {
                      v140 = v139 - 2;
                      if ( v140 )
                      {
                        if ( v140 == 1 )
                        {
                          v161 = 1;
                          if ( (*(_DWORD *)(v132 + v131 + 216) & 0x10) != 0 )
                          {
                            *(_BYTE *)(v132 + v131 + 360) = 1;
                            *(_BYTE *)(v132 + v131 + 356) = 0;
                            *(_DWORD *)(v132 + v131 + 344) = 1;
                          }
                        }
                        else
                        {
                          v141 = this;
                          v142 = *(_DWORD *)(v132 + v131 + 4);
                          if ( v173 == -1 )
                            v143 = -1;
                          else
                            v143 = 10LL * v173;
LABEL_171:
                          DXGADAPTER::SetPowerComponentLatencyCB(v141, v142, v143);
                        }
                      }
                    }
                  }
                  else
                  {
                    v144 = (DXGADAPTER **)*((_QWORD *)this + 483);
                    if ( *v144 != (DXGADAPTER *)((char *)this + 3856) )
                      goto LABEL_208;
                    *(_QWORD *)v133 = (char *)this + 3856;
                    *(_QWORD *)(v133 + 8) = v144;
                    *v144 = (DXGADAPTER *)v133;
                    *((_QWORD *)this + 483) = v133;
                    if ( (*(_DWORD *)(v132 + v131 + 216) & 0x10) != 0 )
                      *(_BYTE *)(v132 + v131 + 360) = 1;
                  }
LABEL_192:
                  if ( v174 == -1 )
                    v153 = -1;
                  else
                    v153 = 10000LL * v174;
                  DXGADAPTER::SetPowerComponentResidencyCB(this, *(_DWORD *)(v132 + v131 + 4), v153);
                  KeInitializeSpinLock((PKSPIN_LOCK)(v132 + v131 + 504));
                  if ( *(_DWORD *)(v134 + 8) <= 1u || (v154 = *(_QWORD *)(v132 + v131 + 48), v154 == -1) )
                  {
                    v155 = *((_QWORD *)this + 487);
                  }
                  else
                  {
                    v155 = *((_QWORD *)this + 487);
                    if ( v154 > v155 )
                      v155 = *(_QWORD *)(v132 + v131 + 48);
                  }
                  *(_QWORD *)(v132 + v131 + 496) = v155;
                  v130 = (unsigned int)(v162 + 1);
                  v162 = v130;
                  if ( (unsigned int)v130 >= v10 )
                  {
                    DXGADAPTER::UpdateLatencyTolerances(this);
                    PoFxSetDeviceIdleTimeout(*((_QWORD *)this + 420), 10LL * v205);
                    if ( *((_DWORD *)this + 105) == 1297040209 && *((_DWORD *)this + 716) == 4608 )
                    {
                      KeInitializeEvent((PRKEVENT)((char *)this + 4040), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4064), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4088), SynchronizationEvent, 0);
                      KeInitializeSpinLock((PKSPIN_LOCK)this + 514);
                      *((_QWORD *)this + 517) = (char *)this + 4128;
                      *((_QWORD *)this + 516) = (char *)this + 4128;
                      InitializeSListHead((PSLIST_HEADER)this + 259);
                      v157 = 0;
                      v88 = 8;
                      do
                        ExpInterlockedPushEntrySList((PSLIST_HEADER)this + 259, (PSLIST_ENTRY)this + 2 * v157++ + 261);
                      while ( v157 != 8 );
                      *(_QWORD *)&ObjectAttributes.Length = 48;
                      *(_QWORD *)&ObjectAttributes.Attributes = 512;
                      ObjectAttributes.RootDirectory = 0;
                      ObjectAttributes.ObjectName = 0;
                      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                      v158 = PsCreateSystemThread(
                               (PHANDLE)this + 520,
                               0x1FFFFFu,
                               &ObjectAttributes,
                               0,
                               0,
                               DXGADAPTER::PowerRuntimeComponentIdleStateCallbackThread,
                               this);
                      v9 = v158;
                      if ( v158 < 0 )
                      {
                        WdLogSingleEntry2(2, v158, 8);
                        v89 = L"InitializePowerManagement failed to create worker thread for display adapter:0x%I64x";
                        WdLogGlobalForLineNumber = 5752;
                        goto LABEL_211;
                      }
                    }
                    LOBYTE(v156) = v161;
                    v159 = DpiEnablePowerManagement(*((_QWORD *)this + 27), *((_QWORD *)this + 420), v156);
                    v9 = v159;
                    if ( v159 < 0 )
                    {
                      DXGADAPTER::DestroySerializeFStateTransitWorker(this);
                      v88 = 9;
                      WdLogSingleEntry2(2, v9, 9);
                      v89 = L"Port power management enable failed:0x%I64x";
                      WdLogGlobalForLineNumber = 5767;
                      goto LABEL_211;
                    }
                    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v24);
                    return 0;
                  }
                  continue;
                }
                v145 = v203;
              }
              else
              {
                v145 = v204;
              }
              v142 = *(_DWORD *)(v132 + v131 + 4);
              v143 = 10 * v145;
              v141 = this;
              goto LABEL_171;
            }
            break;
          }
          *(_BYTE *)(v132 + v131 + 357) = 1;
          v146 = (DXGADAPTER **)*((_QWORD *)this + 485);
          if ( *v146 != (DXGADAPTER *)((char *)this + 3872) )
LABEL_208:
            __fastfail(3u);
          *(_QWORD *)v133 = (char *)this + 3872;
          *(_QWORD *)(v133 + 8) = v146;
          *v146 = (DXGADAPTER *)v133;
          *((_QWORD *)this + 485) = v133;
          v147 = 0;
          v148 = *(_DWORD *)(v134 + 8);
          for ( n = 1; n < v148; v147 = v150 )
          {
            v150 = *(_QWORD *)(v134 + 24LL * n + 16);
            if ( v147 >= v150 )
              v150 = v147;
            ++n;
          }
          *(_DWORD *)(v132 + v131 + 388) = 1;
          for ( ii = 0; ; ++ii )
          {
            if ( ii >= 2 )
              goto LABEL_191;
            if ( *((_QWORD *)this + 2 * ii + 443) >= v147 )
              break;
          }
          *(_DWORD *)(v132 + v131 + 388) = ii;
LABEL_191:
          v152 = *(_DWORD *)(v132 + v131 + 4);
          *(_DWORD *)(v132 + v131 + 384) = 2;
          DXGADAPTER::SetPowerComponentLatencyCB(this, v152, *(_QWORD *)(*((_QWORD *)this + 455) + 32LL));
          ++*((_DWORD *)this + 878);
          goto LABEL_192;
        }
        v62 = v165;
        *(_QWORD *)(v58 + 136) = this;
        *(_DWORD *)(v58 + 144) = v62;
        *(_QWORD *)(v58 + 152) = v58;
        KeInitializeSpinLock((PKSPIN_LOCK)(v58 + 160));
        *(_DWORD *)(v58 + 244) = -1;
        *(_BYTE *)(v58 + 240) = 0;
        v56 = v165;
      }
      ++v56;
    }
  }
  v28 = v25;
  v29 = 0;
  v249 = v25;
  *((_WORD *)this + v25 + 1684) = v27;
  while ( 1 )
  {
    v166 = v29;
    if ( v29 >= v540[v28] )
    {
      NumDifferentPhysicalAdapters = v162;
      ++v25;
      goto LABEL_40;
    }
    v30 = v27;
    v31 = v25;
    v32 = *((_QWORD *)this + 419) + 8LL;
    v33 = 520 * v30;
    v176 = v29 + (v31 << 16);
    v248.pInputData = &v176;
    v248.pOutputData = (void *)(520 * v30 + v32);
    v165 = 520 * v30;
    v34 = DXGADAPTER::DdiQueryAdapterInfo(this, &v248, v28);
    v9 = v34;
    if ( v34 < 0 )
    {
      WdLogSingleEntry2(2, v30, v34);
      WdLogGlobalForLineNumber = 5088;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport failed QueryAdapterInfo(DXGKQAITYPE_POWERCOMPONENTINFO). Component: 0x%I64x, Status: 0x%I64x",
        v30,
        v9,
        0,
        0,
        0);
      goto LABEL_212;
    }
    v35 = v166;
    v36 = v164;
    v37 = 56 * v30;
    *(_DWORD *)(v33 + *((_QWORD *)this + 419)) = v164;
    *(_WORD *)(v33 + *((_QWORD *)this + 419) + 4) = v35;
    *(_WORD *)(v33 + *((_QWORD *)this + 419) + 6) = v163;
    v38 = *((_QWORD *)this + 419) + v33;
    *(_DWORD *)&v24[56 * v30 + 132] = *(_DWORD *)(v38 + 8);
    if ( (unsigned int)(*(_DWORD *)(v38 + 8) - 1) > 7 )
    {
      WdLogSingleEntry3(2, v30, *(unsigned int *)(v38 + 8), 0);
      WdLogGlobalForLineNumber = 5102;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport returned invalid number of F states for component:0x%I64x 0x%I64x",
        v30,
        *(unsigned int *)(v38 + 8),
        0,
        0,
        0);
      goto LABEL_92;
    }
    *(_OWORD *)&v24[v37 + 104] = *(_OWORD *)(v38 + 220);
    *(_BYTE *)(v38 + 275) = 0;
    v39 = *(_DWORD *)(v38 + 216);
    if ( v39 >= 0x20 )
    {
      WdLogSingleEntry2(2, v30, 2);
      WdLogGlobalForLineNumber = 5116;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Reserved flags are not zero. Component:0x%I64x",
        v30,
        2,
        0,
        0,
        0);
      goto LABEL_92;
    }
    if ( (v39 & 4) != 0 )
      *(_QWORD *)&v24[v37 + 120] |= 1uLL;
    if ( !v206 )
      *(_QWORD *)&v24[v37 + 120] |= 2uLL;
    if ( (*(_DWORD *)(v38 + 216) & 0x10) != 0 )
    {
      if ( ((*(_DWORD *)(v38 + 208) - 3) & 0xFFFFFFFB) != 0 )
      {
        WdLogSingleEntry1(2, v30);
        v41 = L"Power component ActiveInD3 flag can only be used with DXGK_POWER_COMPONENT_MEMORY and DXGK_POWER_COMPONENT"
               "_SHARED. Component:0x%I64x";
        WdLogGlobalForLineNumber = 5135;
      }
      else if ( *(_DWORD *)(v38 + 8) == 2 )
      {
        if ( *(_QWORD *)(v38 + 40) )
        {
          WdLogSingleEntry1(2, v30);
          v41 = L"TransitionLatency for the F1 state must be 0 when the ActiveInD3 flag is set. Component:0x%I64x";
          WdLogGlobalForLineNumber = 5147;
        }
        else
        {
          if ( !*(_DWORD *)(v38 + 276) )
            goto LABEL_55;
          WdLogSingleEntry1(2, v30);
          v41 = L"Provider count must be 0 when the ActiveInD3 flag is set. Component:0x%I64x";
          WdLogGlobalForLineNumber = 5153;
        }
      }
      else
      {
        WdLogSingleEntry1(2, v30);
        v41 = L"F state count must be 2 when the ActiveInD3 flag is set. Component:0x%I64x";
        WdLogGlobalForLineNumber = 5141;
      }
LABEL_91:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v41, v30, 0, 0, 0, 0);
LABEL_92:
      LODWORD(v9) = -1073741811;
      goto LABEL_212;
    }
LABEL_55:
    if ( *(_DWORD *)(v38 + 276) > 0x10u )
    {
      WdLogSingleEntry2(2, v30, 3);
      WdLogGlobalForLineNumber = 5161;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid component ProviderCount. Component:0x%I64x",
        v30,
        3,
        0,
        0,
        0);
      goto LABEL_92;
    }
    v40 = *(_DWORD *)(v38 + 208);
    if ( v40 == 4 )
    {
      if ( *((_DWORD *)this + 876) == -1 )
      {
        *((_DWORD *)this + 876) = v36;
        goto LABEL_66;
      }
      WdLogSingleEntry1(2, v30);
      v41 = L"DXGK_POWER_COMPONENT_MEMORY_REFRESH component is defined second time. Component:0x%I64x";
      WdLogGlobalForLineNumber = 5201;
      goto LABEL_91;
    }
    if ( v40 == 6 )
    {
      if ( *((_DWORD *)this + 875) != -1 )
      {
        WdLogSingleEntry1(3, v30);
        WdLogGlobalForLineNumber = 5175;
        goto LABEL_66;
      }
      *((_DWORD *)this + 875) = v36;
      *((_QWORD *)this + 464) = *((_QWORD *)this + 419) + v165;
      if ( *(_DWORD *)(v38 + 8) == 2 )
      {
        *((_BYTE *)this + 3792) = 1;
        goto LABEL_66;
      }
      if ( *(_DWORD *)(v38 + 8) <= 2u )
        goto LABEL_66;
      WdLogSingleEntry1(2, v30);
      v41 = L"F state count for the DXGK_POWER_COMPONENT_D3_TRANSITION component must be 1 or 2. Component:0x%I64x";
      WdLogGlobalForLineNumber = 5191;
      goto LABEL_91;
    }
LABEL_66:
    v42 = v175;
    *(_DWORD *)&v24[v37 + 144] = *(_DWORD *)(v38 + 276);
    memmove(v42, (const void *)(v38 + 280), 4LL * *(unsigned int *)(v38 + 276));
    v43 = v246;
    *(_QWORD *)&v24[v37 + 152] = v175;
    v44 = *(unsigned int *)(v38 + 276);
    *(_QWORD *)&v24[v37 + 136] = v43;
    v45 = 0;
LABEL_67:
    if ( v45 < *(_DWORD *)(v38 + 8) )
      break;
    v11 = *(_DWORD *)(v38 + 208) == 0;
    v26 = v172;
    v175 = (char *)v175 + 4 * v44;
    if ( v11 )
      v26 = ++v172;
    v25 = v163;
    v29 = v166 + 1;
    v28 = v249;
    v27 = ++v164;
  }
  *(_QWORD *)v43 = *(_QWORD *)(v38 + 24LL * v45 + 16);
  *(_QWORD *)(v43 + 8) = *(_QWORD *)(v38 + 24LL * v45 + 24);
  *(_DWORD *)(v43 + 16) = *(_DWORD *)(v38 + 24LL * v45 + 32);
  if ( *(_QWORD *)(v38 + 24LL * v45 + 16) == -1 )
    *(_QWORD *)v43 = -1;
  if ( *(_QWORD *)(v38 + 24LL * v45 + 24) == -1 )
    *(_QWORD *)(v43 + 8) = -1;
  if ( *(_DWORD *)(v38 + 24LL * v45 + 32) == -1 )
    *(_DWORD *)(v43 + 16) = -1;
  if ( v45 )
  {
    v46 = *(_DWORD *)(v38 + 24LL * v45 + 32);
    if ( v46 != -1 )
    {
      v47 = *(_DWORD *)(v38 + 24 * (v45 - 1 + 1LL) + 8);
      if ( v47 != -1 && v46 > v47 )
      {
        WdLogSingleEntry2(2, v30, 5);
        WdLogGlobalForLineNumber = 5265;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"NominalPower must be decreasing for higher F states. Component:0x%I64x",
          v30,
          5,
          0,
          0,
          0);
        goto LABEL_98;
      }
    }
    v48 = *(_QWORD *)(v38 + 24LL * v45 + 16);
    if ( v48 != -1 )
    {
      v49 = *(_QWORD *)(v38 + 24LL * (v45 - 1) + 16);
      if ( v49 != -1 && v48 < v49 )
      {
        WdLogSingleEntry2(2, v30, 6);
        WdLogGlobalForLineNumber = 5273;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"TransitionLatency must be increasing for higher F states. Component:0x%I64x",
          v30,
          6,
          0,
          0,
          0);
        goto LABEL_98;
      }
    }
LABEL_85:
    v43 += 24;
    v246 = v43;
    ++v45;
    goto LABEL_67;
  }
  if ( ((*(_QWORD *)(v38 + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    && ((*(_QWORD *)(v38 + 24) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !*(_DWORD *)(v38 + 32) )
    {
      WdLogSingleEntry2(2, v30, 4);
      WdLogGlobalForLineNumber = 5254;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NominalPower must not be zero for the F0 state. Component:0x%I64x",
        v30,
        4,
        0,
        0,
        0);
      goto LABEL_98;
    }
    goto LABEL_85;
  }
  WdLogSingleEntry2(2, v30, 3);
  WdLogGlobalForLineNumber = 5248;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"TransitionLatency and ResidencyRequirement must be zero for the F0 state. Component:0x%I64x",
    v30,
    3,
    0,
    0,
    0);
LABEL_98:
  LODWORD(v9) = -1073741811;
LABEL_212:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v24);
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
