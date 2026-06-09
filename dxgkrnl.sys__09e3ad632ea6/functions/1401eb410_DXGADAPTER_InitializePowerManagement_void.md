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
  __int64 v17; // r8
  int AdapterInfo; // eax
  __int64 v20; // rax
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
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // edx
  __int64 i; // r8
  __int64 v54; // r10
  __int64 v55; // r9
  unsigned int v56; // edx
  __int64 j; // rax
  __int64 v58; // rbx
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rsi
  int v63; // eax
  __int64 v64; // rax
  unsigned int k; // ecx
  __int64 v66; // rdx
  __int64 v67; // rax
  void *v68; // rcx
  unsigned int v69; // eax
  unsigned int v70; // edx
  __int64 v71; // r8
  __int64 v72; // r10
  __int64 v73; // rax
  unsigned int v74; // ebx
  __int64 v75; // r9
  unsigned int m; // ecx
  __int64 v77; // r10
  __int64 v78; // rsi
  unsigned int v79; // r11d
  __int64 v80; // r15
  __int64 v81; // rbx
  __int64 v82; // rbx
  __int64 v83; // rbx
  ADAPTER_RENDER *v84; // rcx
  int v85; // eax
  const wchar_t *v86; // r9
  ADAPTER_DISPLAY *v87; // rcx
  int v88; // eax
  __int64 v89; // r15
  const wchar_t *v90; // r9
  int v91; // eax
  ULONG TimeIncrement; // eax
  __int64 v93; // rcx
  unsigned __int64 v94; // r9
  __int64 v95; // rax
  unsigned __int64 v96; // rtt
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rcx
  __int64 v106; // rax
  unsigned __int64 v107; // rtt
  __int64 v108; // rax
  unsigned __int64 v109; // rtt
  __int64 v110; // rax
  __int64 v111; // rcx
  __int64 v112; // rax
  unsigned __int64 v113; // rtt
  __int64 v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rcx
  __int64 v120; // rax
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rcx
  __int64 v124; // rax
  __int64 v125; // rcx
  __int64 v126; // rax
  __int64 v127; // rcx
  __int64 v128; // rax
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rsi
  __int64 v133; // rbx
  __int64 v134; // rdx
  __int64 v135; // r15
  int v136; // ecx
  int v137; // ecx
  int v138; // ecx
  int v139; // ecx
  int v140; // ecx
  int v141; // ecx
  DXGADAPTER *v142; // rcx
  unsigned int v143; // edx
  unsigned __int64 v144; // r8
  DXGADAPTER **v145; // rcx
  __int64 v146; // rax
  DXGADAPTER **v147; // rcx
  unsigned __int64 v148; // rdx
  unsigned int v149; // r9d
  unsigned int n; // r8d
  unsigned __int64 v151; // rax
  unsigned int ii; // ecx
  unsigned int v153; // edx
  unsigned __int64 v154; // r8
  __int64 v155; // rcx
  __int64 v156; // rax
  __int64 v157; // r8
  __int64 v158; // rbx
  NTSTATUS v159; // eax
  int v160; // eax
  __int64 StartRoutine; // [rsp+28h] [rbp-D8h]
  char v162; // [rsp+50h] [rbp-B0h]
  int v163; // [rsp+54h] [rbp-ACh] BYREF
  int v164; // [rsp+58h] [rbp-A8h] BYREF
  int v165; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v166; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v167; // [rsp+68h] [rbp-98h] BYREF
  BOOL v168; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v169; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v170; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v171; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v172; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v173; // [rsp+80h] [rbp-80h]
  unsigned int v174; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v175; // [rsp+88h] [rbp-78h] BYREF
  void *v176; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v177; // [rsp+98h] [rbp-68h] BYREF
  int v178; // [rsp+9Ch] [rbp-64h] BYREF
  int v179; // [rsp+A0h] [rbp-60h] BYREF
  int v180; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v181; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v182; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v183; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v184; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v185; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v186; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v187; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v188; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v189; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v190; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v191; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v192; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned int v193; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v194; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int v195; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v196; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v197; // [rsp+E8h] [rbp-18h] BYREF
  int v198; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v199; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v200; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v201; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v202; // [rsp+FCh] [rbp-4h] BYREF
  unsigned int v203; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v204; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v205; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v206; // [rsp+10Ch] [rbp+Ch] BYREF
  int v207; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v208; // [rsp+114h] [rbp+14h] BYREF
  int v209; // [rsp+118h] [rbp+18h] BYREF
  int v210; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v211; // [rsp+120h] [rbp+20h] BYREF
  int v212; // [rsp+124h] [rbp+24h] BYREF
  int v213; // [rsp+128h] [rbp+28h] BYREF
  int v214; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v215; // [rsp+130h] [rbp+30h] BYREF
  int v216; // [rsp+134h] [rbp+34h] BYREF
  int v217; // [rsp+138h] [rbp+38h] BYREF
  int v218; // [rsp+13Ch] [rbp+3Ch] BYREF
  int v219; // [rsp+140h] [rbp+40h] BYREF
  int v220; // [rsp+144h] [rbp+44h] BYREF
  int v221; // [rsp+148h] [rbp+48h] BYREF
  int v222; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v223; // [rsp+150h] [rbp+50h] BYREF
  int v224; // [rsp+154h] [rbp+54h] BYREF
  int v225; // [rsp+158h] [rbp+58h] BYREF
  int v226; // [rsp+15Ch] [rbp+5Ch] BYREF
  int v227; // [rsp+160h] [rbp+60h] BYREF
  int v228; // [rsp+164h] [rbp+64h] BYREF
  int v229; // [rsp+168h] [rbp+68h] BYREF
  int v230; // [rsp+16Ch] [rbp+6Ch] BYREF
  int v231; // [rsp+170h] [rbp+70h] BYREF
  int v232; // [rsp+174h] [rbp+74h] BYREF
  int v233; // [rsp+178h] [rbp+78h] BYREF
  int v234; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v235; // [rsp+180h] [rbp+80h] BYREF
  int v236; // [rsp+184h] [rbp+84h] BYREF
  int v237; // [rsp+188h] [rbp+88h] BYREF
  int v238; // [rsp+18Ch] [rbp+8Ch] BYREF
  int v239; // [rsp+190h] [rbp+90h] BYREF
  int v240; // [rsp+194h] [rbp+94h] BYREF
  int v241; // [rsp+198h] [rbp+98h] BYREF
  int v242; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v243; // [rsp+1A0h] [rbp+A0h] BYREF
  int v244; // [rsp+1A4h] [rbp+A4h] BYREF
  int v245; // [rsp+1A8h] [rbp+A8h] BYREF
  int v246; // [rsp+1ACh] [rbp+ACh] BYREF
  __int64 v247; // [rsp+1B0h] [rbp+B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v249; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v250; // [rsp+218h] [rbp+118h]
  __int64 v251; // [rsp+220h] [rbp+120h] BYREF
  int v252; // [rsp+228h] [rbp+128h]
  const wchar_t *v253; // [rsp+230h] [rbp+130h]
  BOOL *v254; // [rsp+238h] [rbp+138h]
  int v255; // [rsp+240h] [rbp+140h]
  int *v256; // [rsp+248h] [rbp+148h]
  int v257; // [rsp+250h] [rbp+150h]
  __int64 v258; // [rsp+258h] [rbp+158h]
  int v259; // [rsp+260h] [rbp+160h]
  __int64 v260; // [rsp+268h] [rbp+168h]
  __int128 v261; // [rsp+270h] [rbp+170h]
  __int128 v262; // [rsp+280h] [rbp+180h]
  __int64 v263; // [rsp+290h] [rbp+190h] BYREF
  int v264; // [rsp+298h] [rbp+198h]
  const wchar_t *v265; // [rsp+2A0h] [rbp+1A0h]
  int *v266; // [rsp+2A8h] [rbp+1A8h]
  int v267; // [rsp+2B0h] [rbp+1B0h]
  int *v268; // [rsp+2B8h] [rbp+1B8h]
  int v269; // [rsp+2C0h] [rbp+1C0h]
  __int64 v270; // [rsp+2C8h] [rbp+1C8h]
  int v271; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v272; // [rsp+2D8h] [rbp+1D8h]
  int *v273; // [rsp+2E0h] [rbp+1E0h]
  int v274; // [rsp+2E8h] [rbp+1E8h]
  int *v275; // [rsp+2F0h] [rbp+1F0h]
  int v276; // [rsp+2F8h] [rbp+1F8h]
  __int64 v277; // [rsp+300h] [rbp+200h]
  int v278; // [rsp+308h] [rbp+208h]
  const wchar_t *v279; // [rsp+310h] [rbp+210h]
  unsigned int *v280; // [rsp+318h] [rbp+218h]
  int v281; // [rsp+320h] [rbp+220h]
  int *v282; // [rsp+328h] [rbp+228h]
  int v283; // [rsp+330h] [rbp+230h]
  __int64 v284; // [rsp+338h] [rbp+238h]
  int v285; // [rsp+340h] [rbp+240h]
  const wchar_t *v286; // [rsp+348h] [rbp+248h]
  unsigned int *v287; // [rsp+350h] [rbp+250h]
  int v288; // [rsp+358h] [rbp+258h]
  int *v289; // [rsp+360h] [rbp+260h]
  int v290; // [rsp+368h] [rbp+268h]
  __int64 v291; // [rsp+370h] [rbp+270h]
  int v292; // [rsp+378h] [rbp+278h]
  const wchar_t *v293; // [rsp+380h] [rbp+280h]
  unsigned int *v294; // [rsp+388h] [rbp+288h]
  int v295; // [rsp+390h] [rbp+290h]
  int *v296; // [rsp+398h] [rbp+298h]
  int v297; // [rsp+3A0h] [rbp+2A0h]
  __int64 v298; // [rsp+3A8h] [rbp+2A8h]
  int v299; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v300; // [rsp+3B8h] [rbp+2B8h]
  unsigned int *v301; // [rsp+3C0h] [rbp+2C0h]
  int v302; // [rsp+3C8h] [rbp+2C8h]
  int *v303; // [rsp+3D0h] [rbp+2D0h]
  int v304; // [rsp+3D8h] [rbp+2D8h]
  __int64 v305; // [rsp+3E0h] [rbp+2E0h]
  int v306; // [rsp+3E8h] [rbp+2E8h]
  const wchar_t *v307; // [rsp+3F0h] [rbp+2F0h]
  unsigned int *v308; // [rsp+3F8h] [rbp+2F8h]
  int v309; // [rsp+400h] [rbp+300h]
  int *v310; // [rsp+408h] [rbp+308h]
  int v311; // [rsp+410h] [rbp+310h]
  __int64 v312; // [rsp+418h] [rbp+318h]
  int v313; // [rsp+420h] [rbp+320h]
  const wchar_t *v314; // [rsp+428h] [rbp+328h]
  unsigned int *v315; // [rsp+430h] [rbp+330h]
  int v316; // [rsp+438h] [rbp+338h]
  int *v317; // [rsp+440h] [rbp+340h]
  int v318; // [rsp+448h] [rbp+348h]
  __int64 v319; // [rsp+450h] [rbp+350h]
  int v320; // [rsp+458h] [rbp+358h]
  const wchar_t *v321; // [rsp+460h] [rbp+360h]
  unsigned int *v322; // [rsp+468h] [rbp+368h]
  int v323; // [rsp+470h] [rbp+370h]
  int *v324; // [rsp+478h] [rbp+378h]
  int v325; // [rsp+480h] [rbp+380h]
  __int64 v326; // [rsp+488h] [rbp+388h]
  int v327; // [rsp+490h] [rbp+390h]
  const wchar_t *v328; // [rsp+498h] [rbp+398h]
  unsigned int *v329; // [rsp+4A0h] [rbp+3A0h]
  int v330; // [rsp+4A8h] [rbp+3A8h]
  int *v331; // [rsp+4B0h] [rbp+3B0h]
  int v332; // [rsp+4B8h] [rbp+3B8h]
  __int64 v333; // [rsp+4C0h] [rbp+3C0h]
  int v334; // [rsp+4C8h] [rbp+3C8h]
  const wchar_t *v335; // [rsp+4D0h] [rbp+3D0h]
  int *v336; // [rsp+4D8h] [rbp+3D8h]
  int v337; // [rsp+4E0h] [rbp+3E0h]
  int *v338; // [rsp+4E8h] [rbp+3E8h]
  int v339; // [rsp+4F0h] [rbp+3F0h]
  __int64 v340; // [rsp+4F8h] [rbp+3F8h]
  int v341; // [rsp+500h] [rbp+400h]
  const wchar_t *v342; // [rsp+508h] [rbp+408h]
  unsigned int *v343; // [rsp+510h] [rbp+410h]
  int v344; // [rsp+518h] [rbp+418h]
  int *v345; // [rsp+520h] [rbp+420h]
  int v346; // [rsp+528h] [rbp+428h]
  __int64 v347; // [rsp+530h] [rbp+430h]
  int v348; // [rsp+538h] [rbp+438h]
  const wchar_t *v349; // [rsp+540h] [rbp+440h]
  int *v350; // [rsp+548h] [rbp+448h]
  int v351; // [rsp+550h] [rbp+450h]
  int *v352; // [rsp+558h] [rbp+458h]
  int v353; // [rsp+560h] [rbp+460h]
  __int64 v354; // [rsp+568h] [rbp+468h]
  int v355; // [rsp+570h] [rbp+470h]
  const wchar_t *v356; // [rsp+578h] [rbp+478h]
  unsigned int *v357; // [rsp+580h] [rbp+480h]
  int v358; // [rsp+588h] [rbp+488h]
  int *v359; // [rsp+590h] [rbp+490h]
  int v360; // [rsp+598h] [rbp+498h]
  __int64 v361; // [rsp+5A0h] [rbp+4A0h]
  int v362; // [rsp+5A8h] [rbp+4A8h]
  const wchar_t *v363; // [rsp+5B0h] [rbp+4B0h]
  unsigned int *v364; // [rsp+5B8h] [rbp+4B8h]
  int v365; // [rsp+5C0h] [rbp+4C0h]
  int *v366; // [rsp+5C8h] [rbp+4C8h]
  int v367; // [rsp+5D0h] [rbp+4D0h]
  __int64 v368; // [rsp+5D8h] [rbp+4D8h]
  int v369; // [rsp+5E0h] [rbp+4E0h]
  const wchar_t *v370; // [rsp+5E8h] [rbp+4E8h]
  unsigned int *v371; // [rsp+5F0h] [rbp+4F0h]
  int v372; // [rsp+5F8h] [rbp+4F8h]
  int *v373; // [rsp+600h] [rbp+500h]
  int v374; // [rsp+608h] [rbp+508h]
  __int64 v375; // [rsp+610h] [rbp+510h]
  int v376; // [rsp+618h] [rbp+518h]
  const wchar_t *v377; // [rsp+620h] [rbp+520h]
  unsigned int *v378; // [rsp+628h] [rbp+528h]
  int v379; // [rsp+630h] [rbp+530h]
  int *v380; // [rsp+638h] [rbp+538h]
  int v381; // [rsp+640h] [rbp+540h]
  __int64 v382; // [rsp+648h] [rbp+548h]
  int v383; // [rsp+650h] [rbp+550h]
  const wchar_t *v384; // [rsp+658h] [rbp+558h]
  unsigned int *v385; // [rsp+660h] [rbp+560h]
  int v386; // [rsp+668h] [rbp+568h]
  int *v387; // [rsp+670h] [rbp+570h]
  int v388; // [rsp+678h] [rbp+578h]
  __int64 v389; // [rsp+680h] [rbp+580h]
  int v390; // [rsp+688h] [rbp+588h]
  const wchar_t *v391; // [rsp+690h] [rbp+590h]
  unsigned int *v392; // [rsp+698h] [rbp+598h]
  int v393; // [rsp+6A0h] [rbp+5A0h]
  int *v394; // [rsp+6A8h] [rbp+5A8h]
  int v395; // [rsp+6B0h] [rbp+5B0h]
  __int64 v396; // [rsp+6B8h] [rbp+5B8h]
  int v397; // [rsp+6C0h] [rbp+5C0h]
  const wchar_t *v398; // [rsp+6C8h] [rbp+5C8h]
  unsigned int *v399; // [rsp+6D0h] [rbp+5D0h]
  int v400; // [rsp+6D8h] [rbp+5D8h]
  int *v401; // [rsp+6E0h] [rbp+5E0h]
  int v402; // [rsp+6E8h] [rbp+5E8h]
  __int64 v403; // [rsp+6F0h] [rbp+5F0h]
  int v404; // [rsp+6F8h] [rbp+5F8h]
  const wchar_t *v405; // [rsp+700h] [rbp+600h]
  unsigned int *v406; // [rsp+708h] [rbp+608h]
  int v407; // [rsp+710h] [rbp+610h]
  int *v408; // [rsp+718h] [rbp+618h]
  int v409; // [rsp+720h] [rbp+620h]
  __int64 v410; // [rsp+728h] [rbp+628h]
  int v411; // [rsp+730h] [rbp+630h]
  const wchar_t *v412; // [rsp+738h] [rbp+638h]
  int *v413; // [rsp+740h] [rbp+640h]
  int v414; // [rsp+748h] [rbp+648h]
  int *v415; // [rsp+750h] [rbp+650h]
  int v416; // [rsp+758h] [rbp+658h]
  __int64 v417; // [rsp+760h] [rbp+660h]
  int v418; // [rsp+768h] [rbp+668h]
  const wchar_t *v419; // [rsp+770h] [rbp+670h]
  int *v420; // [rsp+778h] [rbp+678h]
  int v421; // [rsp+780h] [rbp+680h]
  int *v422; // [rsp+788h] [rbp+688h]
  int v423; // [rsp+790h] [rbp+690h]
  __int64 v424; // [rsp+798h] [rbp+698h]
  int v425; // [rsp+7A0h] [rbp+6A0h]
  const wchar_t *v426; // [rsp+7A8h] [rbp+6A8h]
  int *v427; // [rsp+7B0h] [rbp+6B0h]
  int v428; // [rsp+7B8h] [rbp+6B8h]
  int *v429; // [rsp+7C0h] [rbp+6C0h]
  int v430; // [rsp+7C8h] [rbp+6C8h]
  __int64 v431; // [rsp+7D0h] [rbp+6D0h]
  int v432; // [rsp+7D8h] [rbp+6D8h]
  const wchar_t *v433; // [rsp+7E0h] [rbp+6E0h]
  unsigned int *v434; // [rsp+7E8h] [rbp+6E8h]
  int v435; // [rsp+7F0h] [rbp+6F0h]
  int *v436; // [rsp+7F8h] [rbp+6F8h]
  int v437; // [rsp+800h] [rbp+700h]
  __int64 v438; // [rsp+808h] [rbp+708h]
  int v439; // [rsp+810h] [rbp+710h]
  const wchar_t *v440; // [rsp+818h] [rbp+718h]
  unsigned int *v441; // [rsp+820h] [rbp+720h]
  int v442; // [rsp+828h] [rbp+728h]
  int *v443; // [rsp+830h] [rbp+730h]
  int v444; // [rsp+838h] [rbp+738h]
  __int64 v445; // [rsp+840h] [rbp+740h]
  int v446; // [rsp+848h] [rbp+748h]
  const wchar_t *v447; // [rsp+850h] [rbp+750h]
  unsigned int *v448; // [rsp+858h] [rbp+758h]
  int v449; // [rsp+860h] [rbp+760h]
  int *v450; // [rsp+868h] [rbp+768h]
  int v451; // [rsp+870h] [rbp+770h]
  __int64 v452; // [rsp+878h] [rbp+778h]
  int v453; // [rsp+880h] [rbp+780h]
  const wchar_t *v454; // [rsp+888h] [rbp+788h]
  unsigned int *v455; // [rsp+890h] [rbp+790h]
  int v456; // [rsp+898h] [rbp+798h]
  int *v457; // [rsp+8A0h] [rbp+7A0h]
  int v458; // [rsp+8A8h] [rbp+7A8h]
  __int64 v459; // [rsp+8B0h] [rbp+7B0h]
  int v460; // [rsp+8B8h] [rbp+7B8h]
  const wchar_t *v461; // [rsp+8C0h] [rbp+7C0h]
  unsigned int *v462; // [rsp+8C8h] [rbp+7C8h]
  int v463; // [rsp+8D0h] [rbp+7D0h]
  int *v464; // [rsp+8D8h] [rbp+7D8h]
  int v465; // [rsp+8E0h] [rbp+7E0h]
  __int64 v466; // [rsp+8E8h] [rbp+7E8h]
  int v467; // [rsp+8F0h] [rbp+7F0h]
  const wchar_t *v468; // [rsp+8F8h] [rbp+7F8h]
  unsigned int *v469; // [rsp+900h] [rbp+800h]
  int v470; // [rsp+908h] [rbp+808h]
  int *v471; // [rsp+910h] [rbp+810h]
  int v472; // [rsp+918h] [rbp+818h]
  __int64 v473; // [rsp+920h] [rbp+820h]
  int v474; // [rsp+928h] [rbp+828h]
  const wchar_t *v475; // [rsp+930h] [rbp+830h]
  unsigned int *v476; // [rsp+938h] [rbp+838h]
  int v477; // [rsp+940h] [rbp+840h]
  int *v478; // [rsp+948h] [rbp+848h]
  int v479; // [rsp+950h] [rbp+850h]
  __int64 v480; // [rsp+958h] [rbp+858h]
  int v481; // [rsp+960h] [rbp+860h]
  const wchar_t *v482; // [rsp+968h] [rbp+868h]
  unsigned int *v483; // [rsp+970h] [rbp+870h]
  int v484; // [rsp+978h] [rbp+878h]
  int *v485; // [rsp+980h] [rbp+880h]
  int v486; // [rsp+988h] [rbp+888h]
  __int64 v487; // [rsp+990h] [rbp+890h]
  int v488; // [rsp+998h] [rbp+898h]
  const wchar_t *v489; // [rsp+9A0h] [rbp+8A0h]
  unsigned int *v490; // [rsp+9A8h] [rbp+8A8h]
  int v491; // [rsp+9B0h] [rbp+8B0h]
  int *v492; // [rsp+9B8h] [rbp+8B8h]
  int v493; // [rsp+9C0h] [rbp+8C0h]
  __int64 v494; // [rsp+9C8h] [rbp+8C8h]
  int v495; // [rsp+9D0h] [rbp+8D0h]
  const wchar_t *v496; // [rsp+9D8h] [rbp+8D8h]
  unsigned int *v497; // [rsp+9E0h] [rbp+8E0h]
  int v498; // [rsp+9E8h] [rbp+8E8h]
  int *v499; // [rsp+9F0h] [rbp+8F0h]
  int v500; // [rsp+9F8h] [rbp+8F8h]
  __int64 v501; // [rsp+A00h] [rbp+900h]
  int v502; // [rsp+A08h] [rbp+908h]
  const wchar_t *v503; // [rsp+A10h] [rbp+910h]
  unsigned int *v504; // [rsp+A18h] [rbp+918h]
  int v505; // [rsp+A20h] [rbp+920h]
  int *v506; // [rsp+A28h] [rbp+928h]
  int v507; // [rsp+A30h] [rbp+930h]
  __int64 v508; // [rsp+A38h] [rbp+938h]
  int v509; // [rsp+A40h] [rbp+940h]
  const wchar_t *v510; // [rsp+A48h] [rbp+948h]
  unsigned int *v511; // [rsp+A50h] [rbp+950h]
  int v512; // [rsp+A58h] [rbp+958h]
  int *v513; // [rsp+A60h] [rbp+960h]
  int v514; // [rsp+A68h] [rbp+968h]
  __int64 v515; // [rsp+A70h] [rbp+970h]
  int v516; // [rsp+A78h] [rbp+978h]
  const wchar_t *v517; // [rsp+A80h] [rbp+980h]
  unsigned int *v518; // [rsp+A88h] [rbp+988h]
  int v519; // [rsp+A90h] [rbp+990h]
  int *v520; // [rsp+A98h] [rbp+998h]
  int v521; // [rsp+AA0h] [rbp+9A0h]
  __int64 v522; // [rsp+AA8h] [rbp+9A8h]
  int v523; // [rsp+AB0h] [rbp+9B0h]
  const wchar_t *v524; // [rsp+AB8h] [rbp+9B8h]
  unsigned int *v525; // [rsp+AC0h] [rbp+9C0h]
  int v526; // [rsp+AC8h] [rbp+9C8h]
  int *v527; // [rsp+AD0h] [rbp+9D0h]
  int v528; // [rsp+AD8h] [rbp+9D8h]
  __int64 v529; // [rsp+AE0h] [rbp+9E0h]
  int v530; // [rsp+AE8h] [rbp+9E8h]
  const wchar_t *v531; // [rsp+AF0h] [rbp+9F0h]
  unsigned int *v532; // [rsp+AF8h] [rbp+9F8h]
  int v533; // [rsp+B00h] [rbp+A00h]
  int *v534; // [rsp+B08h] [rbp+A08h]
  int v535; // [rsp+B10h] [rbp+A10h]
  __int64 v536; // [rsp+B18h] [rbp+A18h]
  int v537; // [rsp+B20h] [rbp+A20h]
  __int64 v538; // [rsp+B28h] [rbp+A28h]
  __int128 v539; // [rsp+B30h] [rbp+A30h]
  __int128 v540; // [rsp+B40h] [rbp+A40h]
  _DWORD v541[64]; // [rsp+B50h] [rbp+A50h] BYREF
  unsigned __int16 v542[264]; // [rsp+C50h] [rbp+B50h] BYREF

  v3 = (char *)this + 3069;
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_PowerManagementSupport, a3, this);
  if ( !*v3 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 4776;
    return 0;
  }
  v228 = 0;
  v245 = -1;
  v174 = -1;
  v246 = 2000;
  v211 = 35000;
  v183 = 35000;
  v175 = 2000;
  v213 = 50000;
  v186 = 50000;
  v214 = 100000;
  v187 = 100000;
  v219 = 300000;
  v205 = 300000;
  v220 = 17000;
  v204 = 17000;
  v215 = 200;
  v180 = 200;
  v216 = 200;
  v184 = 200;
  v218 = 100;
  v217 = 100;
  v221 = 25000;
  v206 = 25000;
  v223 = 300;
  v171 = 300;
  v224 = 700;
  v172 = 700;
  v225 = 900;
  v170 = 900;
  v226 = 500;
  v169 = 500;
  v232 = 140000;
  v193 = 140000;
  v233 = 200000;
  v195 = 200000;
  v234 = 250000;
  v196 = 250000;
  v235 = 250000;
  v197 = 250000;
  v212 = 2000;
  v185 = 2000;
  v222 = 2000;
  v188 = 2000;
  v236 = 10000;
  v190 = 10000;
  v209 = 80;
  v181 = 80;
  v210 = 15000;
  v182 = 15000;
  v227 = 3;
  v179 = 3;
  v207 = 0;
  v229 = 0;
  v178 = 0;
  v230 = 80;
  v189 = 80;
  v231 = 80000;
  v191 = 80000;
  v5 = *((_DWORD *)this + 783) < 2400;
  v237 = 60000;
  v192 = 60000;
  v238 = 60000;
  v194 = 60000;
  v240 = 30000;
  v199 = 30000;
  v243 = 30000;
  v202 = 30000;
  v244 = 80000;
  v208 = 80000;
  v239 = 15000;
  v203 = 15000;
  v241 = 80;
  v200 = 80;
  v242 = 15000;
  v201 = 15000;
  v198 = 1;
  v168 = 1;
  v163 = 1;
  v164 = 1;
  v167 = 0;
  v165 = 0;
  if ( v5 )
  {
    v253 = L"UseSelfRefreshVRAMInS3";
    v255 = 67108868;
    v251 = 0;
    v254 = &v168;
    v252 = 288;
    v256 = &v198;
    v257 = 4;
    v258 = 0;
    v259 = 0;
    v260 = 0;
    v261 = 0;
    v262 = 0;
    RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\Power", &v251, 0, 0);
  }
  else
  {
    v168 = (*((_DWORD *)this + 649) & 0x1000) == 0;
  }
  v263 = 0;
  v265 = L"EnableRuntimePowerManagement";
  v266 = &v164;
  v268 = &v163;
  v272 = L"DisableDevicePowerRequired";
  v273 = &v165;
  v275 = (int *)&v167;
  v279 = L"DefaultLatencyToleranceOther";
  v280 = &v174;
  v282 = &v245;
  v286 = L"DefaultExpectedResidency";
  v287 = &v175;
  v289 = &v246;
  v293 = L"DefaultLatencyToleranceIdle0";
  v294 = &v181;
  v296 = &v209;
  v300 = L"DefaultLatencyToleranceIdle1";
  v301 = &v182;
  v303 = &v210;
  v307 = L"DefaultLatencyToleranceNoContext";
  v308 = &v183;
  v310 = &v211;
  v314 = L"DefaultLatencyToleranceIdle0MonitorOff";
  v315 = &v185;
  v317 = &v212;
  v264 = 288;
  v267 = 67108868;
  v269 = 4;
  v270 = 0;
  v271 = 288;
  v274 = 67108868;
  v276 = 4;
  v277 = 0;
  v278 = 288;
  v281 = 67108868;
  v283 = 4;
  v284 = 0;
  v285 = 288;
  v288 = 67108868;
  v290 = 4;
  v291 = 0;
  v292 = 288;
  v295 = 67108868;
  v297 = 4;
  v298 = 0;
  v299 = 288;
  v302 = 67108868;
  v304 = 4;
  v305 = 0;
  v306 = 288;
  v309 = 67108868;
  v311 = 4;
  v312 = 0;
  v313 = 288;
  v316 = 67108868;
  v318 = 4;
  v319 = 0;
  v320 = 288;
  v321 = L"DefaultLatencyToleranceIdle1MonitorOff";
  v322 = &v186;
  v324 = &v213;
  v328 = L"DefaultLatencyToleranceNoContextMonitorOff";
  v329 = &v187;
  v331 = &v214;
  v335 = L"DefaultLatencyToleranceTimerPeriod";
  v336 = &v180;
  v338 = &v215;
  v342 = L"DefaultIdleThresholdIdle0";
  v343 = &v184;
  v345 = &v216;
  v349 = L"DefaultIdleThresholdIdle0MonitorOff";
  v350 = &v217;
  v352 = &v218;
  v356 = L"MonitorLatencyTolerance";
  v357 = &v205;
  v359 = &v219;
  v363 = L"MonitorRefreshLatencyTolerance";
  v364 = &v204;
  v366 = &v220;
  v370 = L"DefaultPowerNotRequiredTimeout";
  v371 = &v206;
  v373 = &v221;
  v323 = 67108868;
  v325 = 4;
  v326 = 0;
  v327 = 288;
  v330 = 67108868;
  v332 = 4;
  v333 = 0;
  v334 = 288;
  v337 = 67108868;
  v339 = 4;
  v340 = 0;
  v341 = 288;
  v344 = 67108868;
  v346 = 4;
  v347 = 0;
  v348 = 288;
  v351 = 67108868;
  v353 = 4;
  v354 = 0;
  v355 = 288;
  v358 = 67108868;
  v360 = 4;
  v361 = 0;
  v362 = 288;
  v365 = 67108868;
  v367 = 4;
  v368 = 0;
  v369 = 288;
  v372 = 67108868;
  v374 = 4;
  v375 = 0;
  v376 = 288;
  v379 = 67108868;
  v377 = L"DefaultActiveIdleThreshold";
  v378 = &v188;
  v380 = &v222;
  v384 = L"ulow";
  v385 = &v171;
  v387 = &v223;
  v391 = L"uhigh";
  v392 = &v172;
  v394 = &v224;
  v398 = L"uglitch";
  v399 = &v170;
  v401 = &v225;
  v405 = L"uideal";
  v406 = &v169;
  v408 = &v226;
  v412 = L"lowdebounce";
  v413 = &v179;
  v415 = &v227;
  v419 = L"EnablePODebounce";
  v420 = &v207;
  v422 = &v228;
  v426 = L"DisablePStateManagement";
  v427 = &v178;
  v429 = &v229;
  v381 = 4;
  v382 = 0;
  v383 = 288;
  v386 = 67108868;
  v388 = 4;
  v389 = 0;
  v390 = 288;
  v393 = 67108868;
  v395 = 4;
  v396 = 0;
  v397 = 288;
  v400 = 67108868;
  v402 = 4;
  v403 = 0;
  v404 = 288;
  v407 = 67108868;
  v409 = 4;
  v410 = 0;
  v411 = 288;
  v414 = 67108868;
  v416 = 4;
  v417 = 0;
  v418 = 288;
  v421 = 67108868;
  v423 = 4;
  v424 = 0;
  v425 = 288;
  v428 = 67108868;
  v430 = 4;
  v431 = 0;
  v432 = 288;
  v433 = L"DefaultD3TransitionLatencyActivelyUsed";
  v434 = &v189;
  v436 = &v230;
  v440 = L"DefaultD3TransitionLatencyIdleShortTime";
  v441 = &v191;
  v443 = &v231;
  v447 = L"DefaultD3TransitionLatencyIdleLongTime";
  v448 = &v193;
  v450 = &v232;
  v454 = L"DefaultD3TransitionLatencyIdleVeryLongTime";
  v455 = &v195;
  v457 = &v233;
  v461 = L"DefaultD3TransitionLatencyIdleNoContext";
  v462 = &v196;
  v464 = &v234;
  v468 = L"DefaultD3TransitionLatencyIdleMonitorOff";
  v469 = &v197;
  v471 = &v235;
  v475 = L"DefaultD3TransitionIdleShortTimeThreshold";
  v476 = &v190;
  v478 = &v236;
  v482 = L"DefaultD3TransitionIdleLongTimeThreshold";
  v483 = &v192;
  v485 = &v237;
  v489 = L"DefaultD3TransitionIdleVeryLongTimeThreshold";
  v435 = 67108868;
  v437 = 4;
  v438 = 0;
  v439 = 288;
  v442 = 67108868;
  v444 = 4;
  v445 = 0;
  v446 = 288;
  v449 = 67108868;
  v451 = 4;
  v452 = 0;
  v453 = 288;
  v456 = 67108868;
  v458 = 4;
  v459 = 0;
  v460 = 288;
  v463 = 67108868;
  v465 = 4;
  v466 = 0;
  v467 = 288;
  v470 = 67108868;
  v472 = 4;
  v473 = 0;
  v474 = 288;
  v477 = 67108868;
  v479 = 4;
  v480 = 0;
  v481 = 288;
  v484 = 67108868;
  v486 = 4;
  v487 = 0;
  v488 = 288;
  v491 = 67108868;
  v490 = &v194;
  v498 = 67108868;
  v492 = &v238;
  v505 = 67108868;
  v496 = L"DefaultLatencyToleranceMemory";
  v512 = 67108868;
  v497 = &v203;
  v519 = 67108868;
  v499 = &v239;
  v503 = L"DefaultLatencyToleranceMemoryNoContext";
  v504 = &v199;
  v506 = &v240;
  v510 = L"DefaultMemoryRefreshLatencyToleranceActivelyUsed";
  v511 = &v200;
  v513 = &v241;
  v517 = L"DefaultMemoryRefreshLatencyToleranceIdleShortTime";
  v518 = &v201;
  v520 = &v242;
  v524 = L"DefaultMemoryRefreshLatencyToleranceNoContext";
  v525 = &v202;
  v527 = &v243;
  v531 = L"DefaultMemoryRefreshLatencyToleranceMonitorOff";
  v532 = &v208;
  v526 = 67108868;
  v533 = 67108868;
  v534 = &v244;
  v493 = 4;
  v494 = 0;
  v495 = 288;
  v500 = 4;
  v501 = 0;
  v502 = 288;
  v507 = 4;
  v508 = 0;
  v509 = 288;
  v514 = 4;
  v515 = 0;
  v516 = 288;
  v521 = 4;
  v522 = 0;
  v523 = 288;
  v528 = 4;
  v529 = 0;
  v530 = 288;
  v535 = 4;
  v536 = 0;
  v537 = 0;
  v538 = 0;
  v539 = 0;
  v540 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v263, 0, 0);
  if ( *((int *)this + 783) < 2400 )
  {
    v7 = *((_QWORD *)this + 27);
    v176 = 0;
    if ( (int)DpiGetPnpRegistryKeyName(v7, 2, &v176) >= 0
      && (int)RtlStringCbCopyW(v542, 0x208u, *((const unsigned __int16 **)v176 + 1)) >= 0
      && (int)RtlStringCbCatW(v542, v8, L"\\DxgkSettings") >= 0 )
    {
      v251 = 0;
      v252 = 288;
      v253 = L"UseSelfRefreshVRAMInS3";
      v255 = 67108868;
      v254 = &v168;
      v257 = 4;
      v256 = &v198;
      v258 = 0;
      v259 = 0;
      v260 = 0;
      v261 = 0;
      v262 = 0;
      RtlQueryRegistryValuesEx(0, v542, &v251, 0, 0);
    }
  }
  if ( !v164 )
    return 0;
  LOBYTE(v9) = 0;
  v10 = 0;
  v11 = !v168;
  *((_BYTE *)this + 204) = v165 != 0;
  *((_BYTE *)this + 207) = !v11;
  v12 = *(_QWORD *)(*((_QWORD *)this + 27) + 64LL);
  v13 = *(_DWORD *)(*(_QWORD *)(v12 + 40) + 28LL);
  if ( v13 < 0x5019 )
    NumDifferentPhysicalAdapters = 1;
  else
    NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(this);
  v163 = NumDifferentPhysicalAdapters;
  LODWORD(v166) = 0;
  v15 = 0;
  while ( (unsigned int)v15 < NumDifferentPhysicalAdapters )
  {
    *(_QWORD *)&ObjectAttributes.Attributes = &v541[v15];
    memset(&ObjectAttributes, 0, 24);
    ObjectAttributes.Length = 6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(ObjectAttributes.SecurityDescriptor) = 4;
    if ( DXGADAPTER::IsDxgmms2(this) && v13 >= 0x5019 )
    {
      LODWORD(ObjectAttributes.ObjectName) = 4;
      ObjectAttributes.RootDirectory = &v166;
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
    v10 += v541[(unsigned int)v166];
    v15 = (unsigned int)(v166 + 1);
    LODWORD(v166) = v166 + 1;
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
  v21 = operator new[](v20, 1265072196, 64);
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
  v23 = operator new[](312 * v10 + 160, 1265072196, 256);
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
  v247 = v23 + 56LL * v10 + 104;
  *(_QWORD *)(v23 + 32) = DxgkPowerRuntimeComponentIdleStateCallback;
  v26 = 0;
  v173 = 0;
  *(_QWORD *)(v23 + 16) = DxgkPowerRuntimeComponentActiveCallback;
  *(_QWORD *)(v23 + 24) = DxgkPowerRuntimeComponentIdleCallback;
  *(_QWORD *)(v23 + 40) = DxgkPowerRuntimeDevicePowerRequiredCallback;
  *(_QWORD *)(v23 + 48) = DxgkPowerRuntimeDevicePowerNotRequiredCallback;
  *(_QWORD *)(v23 + 56) = DxgkPowerRuntimeControlCallback;
  v176 = (void *)(v23 + 56LL * v10 + 104 + 192LL * v10);
  v27 = 0;
  memset(&v249, 0, sizeof(v249));
  v165 = 0;
  v249.Type = DXGKQAITYPE_POWERCOMPONENTINFO;
  v249.InputDataSize = 4;
  v249.OutputDataSize = 336;
LABEL_40:
  v164 = v25;
  if ( v25 >= NumDifferentPhysicalAdapters )
  {
    if ( *((_DWORD *)this + 876) == -1 && !*((_BYTE *)this + 3792) )
      *((_QWORD *)this + 464) = 0;
    if ( *((int *)this + 783) < 1300 || !v26 || v178 )
      goto LABEL_152;
    if ( v171 > 0x3E8 || v172 > 0x3E8 || v170 > 0x3E8 || v169 > 0x3E8 || v171 >= v169 || v169 >= v172 || v172 >= v170 )
    {
      WdLogSingleEntry4(2, v171);
      WdLogGlobalForLineNumber = 5322;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"P-State engine regkey validation error - low: 0x%I64x high: 0x%I64x glitch: 0x%I64x ideal: 0x%I64x",
        v171,
        v172,
        v170,
        v169,
        0);
      goto LABEL_98;
    }
    v50 = 248LL * v26;
    v249.Type = DXGKQAITYPE_POWERCOMPONENTPSTATEINFO;
    v249.OutputDataSize = 136;
    if ( !is_mul_ok(v26, 0xF8u) )
      v50 = -1;
    v51 = operator new[](v50, 1265072196, 64);
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
    *((_DWORD *)this + 1192) = v170;
    *((_DWORD *)this + 1193) = v172;
    *((_DWORD *)this + 1194) = v171;
    *((_DWORD *)this + 1195) = v169;
    *((_DWORD *)this + 1196) = v179;
    for ( j = 0; ; j = v56 )
    {
      LODWORD(v166) = v56;
      if ( (unsigned int)j >= v10 )
        goto LABEL_138;
      v58 = *(_QWORD *)(520 * j + *((_QWORD *)this + 419) + 512);
      if ( v58 )
      {
        v249.pOutputData = *(void **)(520 * j + *((_QWORD *)this + 419) + 512);
        v249.pInputData = &v166;
        v59 = DXGADAPTER::DdiQueryAdapterInfo(this, &v249, i);
        v62 = v59;
        if ( v59 < 0 )
        {
          v64 = WdLogNewEntry5_WdTrace(v61, v60);
          *(_QWORD *)(v64 + 24) = (unsigned int)v166;
          *(_QWORD *)(v64 + 32) = v62;
          WdLogGlobalForLineNumber = 5388;
          for ( k = 0; k < *((_DWORD *)this + 874); ++k )
          {
            v66 = 520LL * k;
            v67 = *((_QWORD *)this + 419);
            if ( !*(_DWORD *)(v66 + v67 + 208) )
              *(_QWORD *)(v66 + v67 + 512) = 0;
          }
          v68 = (void *)*((_QWORD *)this + 569);
          *((_DWORD *)this + 1140) = 0;
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v68);
          *((_QWORD *)this + 569) = 0;
LABEL_138:
          v69 = *((_DWORD *)this + 1140);
          v70 = 0;
          v177 = v69;
          while ( v70 < v69 )
          {
            v71 = *((_QWORD *)this + 569);
            v72 = v70;
            v73 = 248LL * v70;
            v74 = *(_DWORD *)(v73 + v71);
            v75 = *(unsigned int *)(v73 + v71 + 144);
            if ( v74 > 0x20 )
            {
              v83 = *(unsigned int *)(v73 + v71 + 144);
              WdLogSingleEntry1(2, v83);
              WdLogGlobalForLineNumber = 5443;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"P-State StateCount cannot be larger than DXGK_MAX_P_STATES. Component:0x%I64x",
                v83,
                0,
                0,
                0,
                0);
              goto LABEL_98;
            }
            for ( m = 0; m < v74; ++m )
            {
              v77 = 62 * v72;
              v78 = m;
              v79 = *(_DWORD *)(v71 + 4 * (v77 + m) + 4);
              if ( !v79 )
              {
                v82 = *(unsigned int *)(v73 + v71 + 144);
                WdLogSingleEntry2(2, v75, m);
                WdLogGlobalForLineNumber = 5456;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"P-State cannot specify 0 operating frequency. Component:0x%I64x, P-State:0x%I64x",
                  v82,
                  v78,
                  0,
                  0,
                  0);
                goto LABEL_92;
              }
              if ( m )
              {
                v80 = m - 1;
                if ( v79 > *(_DWORD *)(v71 + 4 * (v77 + v80) + 4) )
                {
                  v81 = *(unsigned int *)(v73 + v71 + 144);
                  WdLogSingleEntry3(2, v75, m, m - 1);
                  WdLogGlobalForLineNumber = 5466;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"P-States must have monotonically decreasing operating frequency. Component:0x%I64x, P-"
                                   "State1:0x%I64x, P-State2:0x%I64x",
                    v81,
                    v78,
                    v80,
                    0,
                    0);
                  goto LABEL_92;
                }
              }
              v72 = v70;
            }
            v69 = v177;
            ++v70;
          }
LABEL_152:
          v84 = (ADAPTER_RENDER *)*((_QWORD *)this + 407);
          *((_DWORD *)this + 946) = v180;
          if ( v84 )
          {
            v85 = ADAPTER_RENDER::InitializePowerManagement(v84);
            v9 = v85;
            if ( v85 < 0 )
            {
              WdLogSingleEntry2(2, v85, 7);
              WdLogGlobalForLineNumber = 5482;
              v86 = L"InitializePowerManagement failed for render adapter:0x%I64x";
              StartRoutine = 7;
LABEL_155:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v86, v9, StartRoutine, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v87 = (ADAPTER_DISPLAY *)*((_QWORD *)this + 406);
          if ( v87 )
          {
            v88 = ADAPTER_DISPLAY::InitializePowerManagement(v87);
            v9 = v88;
            if ( v88 < 0 )
            {
              v89 = 8;
              WdLogSingleEntry2(2, v88, 8);
              WdLogGlobalForLineNumber = 5492;
              v90 = L"InitializePowerManagement failed for display adapter:0x%I64x";
LABEL_211:
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v90, v9, v89, 0, 0, 0);
              goto LABEL_212;
            }
          }
          v91 = PoFxRegisterDevice(*((_QWORD *)this + 27), v24, (char *)this + 3360);
          v9 = v91;
          if ( v91 < 0 )
          {
            WdLogSingleEntry1(2, v91);
            WdLogGlobalForLineNumber = 5500;
            v86 = L"PoFxRegisterDevice failed with status:0x%I64x";
            StartRoutine = 0;
            goto LABEL_155;
          }
          KeInitializeEvent((PRKEVENT)((char *)this + 3520), SynchronizationEvent, 0);
          *((_QWORD *)this + 476) = (char *)this + 3800;
          *((_QWORD *)this + 475) = (char *)this + 3800;
          *((_BYTE *)this + 3788) = 0;
          TimeIncrement = KeQueryTimeIncrement();
          v93 = v181;
          v94 = TimeIncrement;
          *((_QWORD *)this + 446) = 0;
          *((_QWORD *)this + 448) = 0;
          *((_QWORD *)this + 452) = 0;
          *((_QWORD *)this + 454) = 0;
          *((_QWORD *)this + 443) = 10 * v93;
          v95 = v183;
          *((_QWORD *)this + 445) = 10LL * v182;
          v96 = 10000LL * v184;
          *((_QWORD *)this + 447) = 10 * v95;
          v97 = (unsigned int)(v96 / v94);
          v98 = v185;
          *((_QWORD *)this + 444) = v97;
          *((_QWORD *)this + 450) = v97;
          v99 = 5 * v98;
          v100 = v186;
          *((_QWORD *)this + 449) = 2 * v99;
          v101 = 5 * v100;
          v102 = v187;
          *((_QWORD *)this + 451) = 2 * v101;
          v103 = 5 * v102;
          v104 = v188;
          *((_QWORD *)this + 453) = 2 * v103;
          *((_QWORD *)this + 455) = (char *)this + 3544;
          v105 = 5 * v104;
          v106 = v189;
          *((_QWORD *)this + 487) = 2 * v105;
          v107 = 10000LL * v190;
          *((_QWORD *)this + 456) = 10 * v106;
          v108 = v191;
          *((_QWORD *)this + 457) = (unsigned int)(v107 / v94);
          v109 = 10000LL * v192;
          *((_QWORD *)this + 458) = 10 * v108;
          v110 = v193;
          *((_QWORD *)this + 459) = (unsigned int)(v109 / v94);
          v111 = 5 * v110;
          v112 = 10000LL * v194;
          *((_QWORD *)this + 460) = 2 * v111;
          v113 = v112;
          v114 = v195;
          *((_QWORD *)this + 461) = (unsigned int)(v113 / v94);
          *((_QWORD *)this + 463) = 0;
          v162 = 0;
          v115 = 5 * v114;
          v116 = v196;
          *((_QWORD *)this + 462) = 2 * v115;
          v117 = 5 * v116;
          v118 = v197;
          *((_QWORD *)this + 465) = 2 * v117;
          v119 = 5 * v118;
          v120 = v203;
          *((_QWORD *)this + 466) = 2 * v119;
          v121 = 5 * v120;
          v122 = v199;
          *((_QWORD *)this + 467) = 2 * v121;
          v123 = 5 * v122;
          v124 = v200;
          *((_QWORD *)this + 468) = 2 * v123;
          v125 = 5 * v124;
          v126 = v201;
          *((_QWORD *)this + 469) = 2 * v125;
          v127 = 5 * v126;
          v128 = v202;
          *((_QWORD *)this + 470) = 2 * v127;
          v129 = 5 * v128;
          v130 = v208;
          *((_QWORD *)this + 471) = 2 * v129;
          *((_QWORD *)this + 472) = 10 * v130;
          *((_QWORD *)this + 481) = (char *)this + 3840;
          *((_QWORD *)this + 480) = (char *)this + 3840;
          KeInitializeSpinLock((PKSPIN_LOCK)this + 486);
          v131 = 0;
          v163 = 0;
          while ( 2 )
          {
            v132 = *((_QWORD *)this + 419);
            v133 = 520 * v131;
            v134 = 520 * v131 + v132 + 424;
            *(_BYTE *)(520 * v131 + v132 + 356) = 1;
            v135 = 520 * v131 + v132;
            *(_OWORD *)v134 = 0;
            v136 = *(_DWORD *)(v135 + 208);
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
                    v140 = v139 - 1;
                    if ( v140 )
                    {
                      v141 = v140 - 2;
                      if ( v141 )
                      {
                        if ( v141 == 1 )
                        {
                          v162 = 1;
                          if ( (*(_DWORD *)(v133 + v132 + 216) & 0x10) != 0 )
                          {
                            *(_BYTE *)(v133 + v132 + 360) = 1;
                            *(_BYTE *)(v133 + v132 + 356) = 0;
                            *(_DWORD *)(v133 + v132 + 344) = 1;
                          }
                        }
                        else
                        {
                          v142 = this;
                          v143 = *(_DWORD *)(v133 + v132 + 4);
                          if ( v174 == -1 )
                            v144 = -1;
                          else
                            v144 = 10LL * v174;
LABEL_171:
                          DXGADAPTER::SetPowerComponentLatencyCB(v142, v143, v144);
                        }
                      }
                    }
                  }
                  else
                  {
                    v145 = (DXGADAPTER **)*((_QWORD *)this + 483);
                    if ( *v145 != (DXGADAPTER *)((char *)this + 3856) )
                      goto LABEL_208;
                    *(_QWORD *)v134 = (char *)this + 3856;
                    *(_QWORD *)(v134 + 8) = v145;
                    *v145 = (DXGADAPTER *)v134;
                    *((_QWORD *)this + 483) = v134;
                    if ( (*(_DWORD *)(v133 + v132 + 216) & 0x10) != 0 )
                      *(_BYTE *)(v133 + v132 + 360) = 1;
                  }
LABEL_192:
                  if ( v175 == -1 )
                    v154 = -1;
                  else
                    v154 = 10000LL * v175;
                  DXGADAPTER::SetPowerComponentResidencyCB(this, *(_DWORD *)(v133 + v132 + 4), v154);
                  KeInitializeSpinLock((PKSPIN_LOCK)(v133 + v132 + 504));
                  if ( *(_DWORD *)(v135 + 8) <= 1u || (v155 = *(_QWORD *)(v133 + v132 + 48), v155 == -1) )
                  {
                    v156 = *((_QWORD *)this + 487);
                  }
                  else
                  {
                    v156 = *((_QWORD *)this + 487);
                    if ( v155 > v156 )
                      v156 = *(_QWORD *)(v133 + v132 + 48);
                  }
                  *(_QWORD *)(v133 + v132 + 496) = v156;
                  v131 = (unsigned int)(v163 + 1);
                  v163 = v131;
                  if ( (unsigned int)v131 >= v10 )
                  {
                    DXGADAPTER::UpdateLatencyTolerances(this);
                    PoFxSetDeviceIdleTimeout(*((_QWORD *)this + 420), 10LL * v206);
                    if ( *((_DWORD *)this + 105) == 1297040209 && *((_DWORD *)this + 716) == 4608 )
                    {
                      KeInitializeEvent((PRKEVENT)((char *)this + 4040), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4064), SynchronizationEvent, 0);
                      KeInitializeEvent((PRKEVENT)((char *)this + 4088), SynchronizationEvent, 0);
                      KeInitializeSpinLock((PKSPIN_LOCK)this + 514);
                      *((_QWORD *)this + 517) = (char *)this + 4128;
                      *((_QWORD *)this + 516) = (char *)this + 4128;
                      InitializeSListHead((PSLIST_HEADER)this + 259);
                      v158 = 0;
                      v89 = 8;
                      do
                        ExpInterlockedPushEntrySList((PSLIST_HEADER)this + 259, (PSLIST_ENTRY)this + 2 * v158++ + 261);
                      while ( v158 != 8 );
                      *(_QWORD *)&ObjectAttributes.Length = 48;
                      *(_QWORD *)&ObjectAttributes.Attributes = 512;
                      ObjectAttributes.RootDirectory = 0;
                      ObjectAttributes.ObjectName = 0;
                      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                      v159 = PsCreateSystemThread(
                               (PHANDLE)this + 520,
                               0x1FFFFFu,
                               &ObjectAttributes,
                               0,
                               0,
                               DXGADAPTER::PowerRuntimeComponentIdleStateCallbackThread,
                               this);
                      v9 = v159;
                      if ( v159 < 0 )
                      {
                        WdLogSingleEntry2(2, v159, 8);
                        v90 = L"InitializePowerManagement failed to create worker thread for display adapter:0x%I64x";
                        WdLogGlobalForLineNumber = 5752;
                        goto LABEL_211;
                      }
                    }
                    LOBYTE(v157) = v162;
                    v160 = DpiEnablePowerManagement(*((_QWORD *)this + 27), *((_QWORD *)this + 420), v157);
                    v9 = v160;
                    if ( v160 < 0 )
                    {
                      DXGADAPTER::DestroySerializeFStateTransitWorker(this);
                      v89 = 9;
                      WdLogSingleEntry2(2, v9, 9);
                      v90 = L"Port power management enable failed:0x%I64x";
                      WdLogGlobalForLineNumber = 5767;
                      goto LABEL_211;
                    }
                    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v24);
                    return 0;
                  }
                  continue;
                }
                v146 = v204;
              }
              else
              {
                v146 = v205;
              }
              v143 = *(_DWORD *)(v133 + v132 + 4);
              v144 = 10 * v146;
              v142 = this;
              goto LABEL_171;
            }
            break;
          }
          *(_BYTE *)(v133 + v132 + 357) = 1;
          v147 = (DXGADAPTER **)*((_QWORD *)this + 485);
          if ( *v147 != (DXGADAPTER *)((char *)this + 3872) )
LABEL_208:
            __fastfail(3u);
          *(_QWORD *)v134 = (char *)this + 3872;
          *(_QWORD *)(v134 + 8) = v147;
          *v147 = (DXGADAPTER *)v134;
          *((_QWORD *)this + 485) = v134;
          v148 = 0;
          v149 = *(_DWORD *)(v135 + 8);
          for ( n = 1; n < v149; v148 = v151 )
          {
            v151 = *(_QWORD *)(v135 + 24LL * n + 16);
            if ( v148 >= v151 )
              v151 = v148;
            ++n;
          }
          *(_DWORD *)(v133 + v132 + 388) = 1;
          for ( ii = 0; ; ++ii )
          {
            if ( ii >= 2 )
              goto LABEL_191;
            if ( *((_QWORD *)this + 2 * ii + 443) >= v148 )
              break;
          }
          *(_DWORD *)(v133 + v132 + 388) = ii;
LABEL_191:
          v153 = *(_DWORD *)(v133 + v132 + 4);
          *(_DWORD *)(v133 + v132 + 384) = 2;
          DXGADAPTER::SetPowerComponentLatencyCB(this, v153, *(_QWORD *)(*((_QWORD *)this + 455) + 32LL));
          ++*((_DWORD *)this + 878);
          goto LABEL_192;
        }
        v63 = v166;
        *(_QWORD *)(v58 + 136) = this;
        *(_DWORD *)(v58 + 144) = v63;
        *(_QWORD *)(v58 + 152) = v58;
        KeInitializeSpinLock((PKSPIN_LOCK)(v58 + 160));
        *(_DWORD *)(v58 + 244) = -1;
        *(_BYTE *)(v58 + 240) = 0;
        v56 = v166;
      }
      ++v56;
    }
  }
  v28 = v25;
  v29 = 0;
  v250 = v25;
  *((_WORD *)this + v25 + 1684) = v27;
  while ( 1 )
  {
    v167 = v29;
    if ( v29 >= v541[v28] )
    {
      NumDifferentPhysicalAdapters = v163;
      ++v25;
      goto LABEL_40;
    }
    v30 = v27;
    v31 = v25;
    v32 = *((_QWORD *)this + 419) + 8LL;
    v33 = 520 * v30;
    v177 = v29 + (v31 << 16);
    v249.pInputData = &v177;
    v249.pOutputData = (void *)(520 * v30 + v32);
    v166 = 520 * v30;
    v34 = DXGADAPTER::DdiQueryAdapterInfo(this, &v249, v28);
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
    v35 = v167;
    v36 = v165;
    v37 = 56 * v30;
    *(_DWORD *)(v33 + *((_QWORD *)this + 419)) = v165;
    *(_WORD *)(v33 + *((_QWORD *)this + 419) + 4) = v35;
    *(_WORD *)(v33 + *((_QWORD *)this + 419) + 6) = v164;
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
    if ( !v207 )
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
      *((_QWORD *)this + 464) = *((_QWORD *)this + 419) + v166;
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
    v42 = v176;
    *(_DWORD *)&v24[v37 + 144] = *(_DWORD *)(v38 + 276);
    memmove(v42, (const void *)(v38 + 280), 4LL * *(unsigned int *)(v38 + 276));
    v43 = v247;
    *(_QWORD *)&v24[v37 + 152] = v176;
    v44 = *(unsigned int *)(v38 + 276);
    *(_QWORD *)&v24[v37 + 136] = v43;
    v45 = 0;
LABEL_67:
    if ( v45 < *(_DWORD *)(v38 + 8) )
      break;
    v11 = *(_DWORD *)(v38 + 208) == 0;
    v26 = v173;
    v176 = (char *)v176 + 4 * v44;
    if ( v11 )
      v26 = ++v173;
    v25 = v164;
    v29 = v167 + 1;
    v28 = v250;
    v27 = ++v165;
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
    v247 = v43;
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
