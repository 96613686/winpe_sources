# DeviceEncryptionSupportLevel::SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)

- ea: `0x180018a58`
- end: `0x180022e8d`
- name: `?SLGetWindowsInformationDWORDWrapper@DeviceEncryptionSupportLevel@@CAJPEBGPEAK@Z`
- size: `42037`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017b2c`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800089f0`
- `0x18000b978`
- `0x180018a58`
- `0x1800295e4`
- `0x180029610`
- `0x18002965c`
- `0x18002969c`
- `0x1800296c8`
- `0x1800296f4`
- `0x180029720`
- `0x18002973c`
- `0x18002975c`
- `0x18002c224`
- `0x18002c23c`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180019296`
- `KERNEL32!GetCurrentProcess` at `0x180019296`
- `KERNEL32!GetProcessMitigationPolicy` at `0x1800192b0`
- `KERNEL32!GetProcessMitigationPolicy` at `0x1800192b0`
- `KERNEL32!LocalAlloc` at `0x180019312`
- `KERNEL32!LocalAlloc` at `0x180019312`
- `KERNEL32!FreeLibrary` at `0x180018e91`
- `KERNEL32!FreeLibrary` at `0x18001c813`
- `KERNEL32!FreeLibrary` at `0x18001ce1b`
- `KERNEL32!FreeLibrary` at `0x18001e451`
- `KERNEL32!FreeLibrary` at `0x18001f240`
- `KERNEL32!FreeLibrary` at `0x180020459`
- `KERNEL32!FreeLibrary` at `0x1800206f4`
- `KERNEL32!FreeLibrary` at `0x180022d9b`
- `KERNEL32!FreeLibrary` at `0x180018e91`
- `KERNEL32!FreeLibrary` at `0x18001c813`
- `KERNEL32!FreeLibrary` at `0x18001ce1b`
- `KERNEL32!FreeLibrary` at `0x18001e451`
- `KERNEL32!FreeLibrary` at `0x18001f240`
- `KERNEL32!FreeLibrary` at `0x180020459`
- `KERNEL32!FreeLibrary` at `0x1800206f4`
- `KERNEL32!FreeLibrary` at `0x180022d9b`
- `KERNEL32!GetProcAddress` at `0x180018fc3`
- `KERNEL32!GetProcAddress` at `0x18001b28f`
- `KERNEL32!GetProcAddress` at `0x18001c998`
- `KERNEL32!GetProcAddress` at `0x18001cf9d`
- `KERNEL32!GetProcAddress` at `0x1800205c1`
- `KERNEL32!GetProcAddress` at `0x180021d05`
- `KERNEL32!GetProcAddress` at `0x180018fc3`
- `KERNEL32!GetProcAddress` at `0x18001b28f`
- `KERNEL32!GetProcAddress` at `0x18001c998`
- `KERNEL32!GetProcAddress` at `0x18001cf9d`
- `KERNEL32!GetProcAddress` at `0x1800205c1`
- `KERNEL32!GetProcAddress` at `0x180021d05`
- `KERNEL32!GetModuleHandleExW` at `0x180018f20`
- `KERNEL32!GetModuleHandleExW` at `0x18001b243`
- `KERNEL32!GetModuleHandleExW` at `0x18001c8ce`
- `KERNEL32!GetModuleHandleExW` at `0x18001ced3`
- `KERNEL32!GetModuleHandleExW` at `0x180020505`
- `KERNEL32!GetModuleHandleExW` at `0x180021ccb`
- `KERNEL32!GetModuleHandleExW` at `0x180018f20`
- `KERNEL32!GetModuleHandleExW` at `0x18001b243`
- `KERNEL32!GetModuleHandleExW` at `0x18001c8ce`
- `KERNEL32!GetModuleHandleExW` at `0x18001ced3`
- `KERNEL32!GetModuleHandleExW` at `0x180020505`
- `KERNEL32!GetModuleHandleExW` at `0x180021ccb`
- `KERNEL32!HeapFree` at `0x180019026`
- `KERNEL32!HeapFree` at `0x180019832`
- `KERNEL32!HeapFree` at `0x180019853`
- `KERNEL32!HeapFree` at `0x18001986c`
- `KERNEL32!HeapFree` at `0x180019885`
- `KERNEL32!HeapFree` at `0x18001a25f`
- `KERNEL32!HeapFree` at `0x18001a961`
- `KERNEL32!HeapFree` at `0x18001a98f`
- `KERNEL32!HeapFree` at `0x18001a9bd`
- `KERNEL32!HeapFree` at `0x18001a9de`
- `KERNEL32!HeapFree` at `0x18001aa2b`
- `KERNEL32!HeapFree` at `0x18001aa5d`
- `KERNEL32!HeapFree` at `0x18001aa8a`
- `KERNEL32!HeapFree` at `0x18001aab7`
- `KERNEL32!HeapFree` at `0x18001aad8`
- `KERNEL32!HeapFree` at `0x18001abf1`
- `KERNEL32!HeapFree` at `0x18001ac1c`
- `KERNEL32!HeapFree` at `0x18001ac45`
- `KERNEL32!HeapFree` at `0x18001ac6e`
- `KERNEL32!HeapFree` at `0x18001ac8a`
- `KERNEL32!HeapFree` at `0x18001aca7`
- `KERNEL32!HeapFree` at `0x18001acc0`
- `KERNEL32!HeapFree` at `0x18001acea`
- `KERNEL32!HeapFree` at `0x18001ad0e`
- `KERNEL32!HeapFree` at `0x18001ad32`
- `KERNEL32!HeapFree` at `0x18001ad4e`
- `KERNEL32!HeapFree` at `0x18001ad6b`
- `KERNEL32!HeapFree` at `0x18001aefb`
- `KERNEL32!HeapFree` at `0x18001b660`
- `KERNEL32!HeapFree` at `0x18001b68c`
- `KERNEL32!HeapFree` at `0x18001b6b8`
- `KERNEL32!HeapFree` at `0x18001b6d9`
- `KERNEL32!HeapFree` at `0x18001b769`
- `KERNEL32!HeapFree` at `0x18001b796`
- `KERNEL32!HeapFree` at `0x18001b7c3`
- `KERNEL32!HeapFree` at `0x18001b7e4`
- `KERNEL32!HeapFree` at `0x18001ca09`
- `KERNEL32!HeapFree` at `0x18001d00e`
- `KERNEL32!HeapFree` at `0x18002062e`
- `KERNEL32!HeapFree` at `0x180020ef3`
- `KERNEL32!HeapFree` at `0x180021623`
- `KERNEL32!HeapFree` at `0x180021651`
- `KERNEL32!HeapFree` at `0x18002167f`
- `KERNEL32!HeapFree` at `0x1800216a0`
- `KERNEL32!HeapFree` at `0x1800216f5`
- `KERNEL32!HeapFree` at `0x180021727`
- `KERNEL32!HeapFree` at `0x180021754`
- `KERNEL32!HeapFree` at `0x180021781`
- `KERNEL32!HeapFree` at `0x1800217a2`
- `KERNEL32!HeapFree` at `0x1800219e1`
- `KERNEL32!HeapFree` at `0x1800220c9`
- `KERNEL32!HeapFree` at `0x1800220f6`
- `KERNEL32!HeapFree` at `0x180022123`
- `KERNEL32!HeapFree` at `0x180022146`
- `KERNEL32!HeapFree` at `0x1800221d7`
- `KERNEL32!HeapFree` at `0x180022204`
- `KERNEL32!HeapFree` at `0x180022231`
- `KERNEL32!HeapFree` at `0x180022252`
- `KERNEL32!HeapFree` at `0x180022a8f`
- `KERNEL32!HeapFree` at `0x180022ab8`
- `KERNEL32!HeapFree` at `0x180022adc`
- `KERNEL32!HeapFree` at `0x180022b00`
- `KERNEL32!HeapFree` at `0x180022b1c`
- `KERNEL32!HeapFree` at `0x180022b3c`
- `KERNEL32!HeapFree` at `0x180022b58`
- `KERNEL32!HeapFree` at `0x180022b85`
- `KERNEL32!HeapFree` at `0x180022ba9`
- `KERNEL32!HeapFree` at `0x180022bcd`
- `KERNEL32!HeapFree` at `0x180022be9`
- `KERNEL32!HeapFree` at `0x180022c05`
- `KERNEL32!HeapFree` at `0x180022cdb`
- `KERNEL32!HeapFree` at `0x180022cfb`
- `KERNEL32!HeapFree` at `0x180022d14`
- `KERNEL32!HeapFree` at `0x180022d30`
- `KERNEL32!HeapFree` at `0x180019026`
- `KERNEL32!HeapFree` at `0x180019832`
- `KERNEL32!HeapFree` at `0x180019853`
- `KERNEL32!HeapFree` at `0x18001986c`
- `KERNEL32!HeapFree` at `0x180019885`
- `KERNEL32!HeapFree` at `0x18001a25f`
- `KERNEL32!HeapFree` at `0x18001a961`
- `KERNEL32!HeapFree` at `0x18001a98f`
- `KERNEL32!HeapFree` at `0x18001a9bd`
- `KERNEL32!HeapFree` at `0x18001a9de`
- `KERNEL32!HeapFree` at `0x18001aa2b`
- `KERNEL32!HeapFree` at `0x18001aa5d`
- `KERNEL32!HeapFree` at `0x18001aa8a`
- `KERNEL32!HeapFree` at `0x18001aab7`
- `KERNEL32!HeapFree` at `0x18001aad8`
- `KERNEL32!HeapFree` at `0x18001abf1`
- `KERNEL32!HeapFree` at `0x18001ac1c`
- `KERNEL32!HeapFree` at `0x18001ac45`
- `KERNEL32!HeapFree` at `0x18001ac6e`
- `KERNEL32!HeapFree` at `0x18001ac8a`
- `KERNEL32!HeapFree` at `0x18001aca7`
- `KERNEL32!HeapFree` at `0x18001acc0`
- `KERNEL32!HeapFree` at `0x18001acea`
- `KERNEL32!HeapFree` at `0x18001ad0e`
- `KERNEL32!HeapFree` at `0x18001ad32`
- `KERNEL32!HeapFree` at `0x18001ad4e`
- `KERNEL32!HeapFree` at `0x18001ad6b`
- `KERNEL32!HeapFree` at `0x18001aefb`
- `KERNEL32!HeapFree` at `0x18001b660`
- `KERNEL32!HeapFree` at `0x18001b68c`
- `KERNEL32!HeapFree` at `0x18001b6b8`
- `KERNEL32!HeapFree` at `0x18001b6d9`
- `KERNEL32!HeapFree` at `0x18001b769`
- `KERNEL32!HeapFree` at `0x18001b796`
- `KERNEL32!HeapFree` at `0x18001b7c3`
- `KERNEL32!HeapFree` at `0x18001b7e4`
- `KERNEL32!HeapFree` at `0x18001ca09`
- `KERNEL32!HeapFree` at `0x18001d00e`
- `KERNEL32!HeapFree` at `0x18002062e`
- `KERNEL32!HeapFree` at `0x180020ef3`
- `KERNEL32!HeapFree` at `0x180021623`
- `KERNEL32!HeapFree` at `0x180021651`
- `KERNEL32!HeapFree` at `0x18002167f`
- `KERNEL32!HeapFree` at `0x1800216a0`
- `KERNEL32!HeapFree` at `0x1800216f5`
- `KERNEL32!HeapFree` at `0x180021727`
- `KERNEL32!HeapFree` at `0x180021754`
- `KERNEL32!HeapFree` at `0x180021781`
- `KERNEL32!HeapFree` at `0x1800217a2`
- `KERNEL32!HeapFree` at `0x1800219e1`
- `KERNEL32!HeapFree` at `0x1800220c9`
- `KERNEL32!HeapFree` at `0x1800220f6`
- `KERNEL32!HeapFree` at `0x180022123`
- `KERNEL32!HeapFree` at `0x180022146`
- `KERNEL32!HeapFree` at `0x1800221d7`
- `KERNEL32!HeapFree` at `0x180022204`
- `KERNEL32!HeapFree` at `0x180022231`
- `KERNEL32!HeapFree` at `0x180022252`
- `KERNEL32!HeapFree` at `0x180022a8f`
- `KERNEL32!HeapFree` at `0x180022ab8`
- `KERNEL32!HeapFree` at `0x180022adc`
- `KERNEL32!HeapFree` at `0x180022b00`
- `KERNEL32!HeapFree` at `0x180022b1c`
- `KERNEL32!HeapFree` at `0x180022b3c`
- `KERNEL32!HeapFree` at `0x180022b58`
- `KERNEL32!HeapFree` at `0x180022b85`
- `KERNEL32!HeapFree` at `0x180022ba9`
- `KERNEL32!HeapFree` at `0x180022bcd`
- `KERNEL32!HeapFree` at `0x180022be9`
- `KERNEL32!HeapFree` at `0x180022c05`
- `KERNEL32!HeapFree` at `0x180022cdb`
- `KERNEL32!HeapFree` at `0x180022cfb`
- `KERNEL32!HeapFree` at `0x180022d14`
- `KERNEL32!HeapFree` at `0x180022d30`
- `KERNEL32!HeapAlloc` at `0x180019364`
- `KERNEL32!HeapAlloc` at `0x180019421`
- `KERNEL32!HeapAlloc` at `0x18001969e`
- `KERNEL32!HeapAlloc` at `0x18001a1ab`
- `KERNEL32!HeapAlloc` at `0x18001a7b2`
- `KERNEL32!HeapAlloc` at `0x18001a816`

## string_xrefs

- `0x18001b228`: `ntdll.dll`
- `0x180021cb0`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionSupportLevel::SLGetWindowsInformationDWORDWrapper(
        const unsigned __int16 *a1,
        unsigned int *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  _BYTE *v4; // rax
  _BYTE *v5; // rdi
  __int64 *v6; // rsi
  _BYTE *v7; // r14
  int v8; // r12d
  int v9; // r13d
  int v10; // r10d
  int v11; // r8d
  __int64 v12; // r15
  int v13; // ecx
  int v14; // ebx
  int v15; // r11d
  int v16; // ebx
  int v17; // edx
  int v18; // r11d
  unsigned int v19; // r8d
  int v20; // r9d
  unsigned int v21; // edx
  int v22; // r10d
  int v23; // r8d
  unsigned int v24; // r9d
  int v25; // r10d
  int v26; // edx
  int v27; // r8d
  unsigned int v28; // r9d
  int v29; // edx
  int v30; // r8d
  unsigned int v31; // r10d
  unsigned int v32; // r8d
  int v33; // r9d
  int v34; // edx
  unsigned int v35; // r8d
  int v36; // r9d
  int v37; // edx
  int v38; // r8d
  unsigned int v39; // r9d
  int v40; // r10d
  int v41; // ecx
  unsigned __int64 v42; // rcx
  char v43; // al
  __int64 i; // rbx
  HMODULE v45; // rcx
  int v46; // r13d
  int v47; // ebx
  unsigned int v48; // r12d
  __int64 v49; // rbx
  HMODULE *v50; // r14
  _BYTE *v51; // rdi
  __int64 v52; // rax
  char *v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // r15d
  __int64 v56; // rsi
  __int64 (__fastcall *v57)(); // rax
  HANDLE v58; // rax
  const wchar_t *v59; // rsi
  const wchar_t *v60; // r14
  int v61; // r13d
  int v62; // r12d
  __int64 v63; // r15
  signed int LastError; // ebx
  bool v65; // sf
  __int64 v66; // r9
  void *j; // rdi
  void *v68; // r8
  __int64 (__fastcall *v69)(); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v71; // r15
  __int64 v72; // r9
  void *k; // rdi
  void *v74; // r8
  HANDLE CurrentProcess; // rax
  bool v76; // sf
  int v77; // edi
  HLOCAL v78; // rax
  _DWORD *v79; // rdi
  HANDLE ProcessHeap; // rax
  _OWORD *v81; // rax
  void *v82; // r12
  int v83; // r15d
  _QWORD *v84; // r13
  HANDLE v85; // rax
  int v86; // eax
  int v87; // ecx
  unsigned int v88; // r11d
  int v89; // eax
  unsigned int v90; // r11d
  int v91; // r9d
  int v92; // eax
  unsigned int v93; // r11d
  int v94; // r9d
  int v95; // eax
  size_t v96; // rdx
  int v97; // r9d
  int v98; // r11d
  int v99; // eax
  unsigned int v100; // r11d
  int v101; // eax
  unsigned int v102; // r11d
  int v103; // r9d
  int v104; // eax
  int v105; // r9d
  unsigned int v106; // ebx
  HANDLE v107; // rax
  _DWORD *v108; // rbx
  unsigned int v109; // r9d
  int v110; // r10d
  unsigned int v111; // r11d
  _DWORD *v112; // rax
  __int64 v113; // rbx
  unsigned int v114; // r10d
  void *v115; // rbx
  HANDLE v116; // rax
  HANDLE v117; // rax
  HANDLE v118; // rax
  HANDLE v119; // rax
  size_t v120; // r12
  DWORD ModuleFileNameW; // eax
  unsigned int *v122; // r9
  unsigned int i12; // ebx
  __int64 v124; // rdx
  __int64 v125; // r9
  unsigned int *v126; // r9
  unsigned int v127; // r11d
  unsigned int v128; // r10d
  unsigned int *v129; // r9
  unsigned int i13; // r11d
  __int64 v131; // rdx
  __int64 v132; // r9
  int v133; // r11d
  _DWORD *v134; // r9
  unsigned int *v135; // r9
  unsigned int v136; // r10d
  size_t v137; // rdx
  unsigned int i14; // r11d
  __int64 v139; // rdx
  __int64 v140; // r9
  int v141; // r11d
  _DWORD *v142; // r9
  LPCWSTR *v143; // rax
  LPCWSTR v144; // rcx
  STRSAFE_PCNZWCH v145; // rdi
  unsigned int v146; // r11d
  unsigned int *v147; // r9
  unsigned int i15; // ebx
  __int64 v149; // rdx
  __int64 v150; // r9
  _DWORD *v151; // r9
  __int64 v152; // r10
  void *v153; // rcx
  unsigned int *v154; // r9
  unsigned int v155; // r10d
  unsigned int i16; // r11d
  __int64 v157; // rdx
  __int64 v158; // r9
  int v159; // r11d
  _DWORD *v160; // r9
  _DWORD *v161; // rax
  int v162; // ecx
  unsigned int *v163; // r9
  unsigned int v164; // r10d
  unsigned int i20; // r11d
  __int64 v166; // rdx
  __int64 v167; // r9
  int v168; // r11d
  _DWORD *v169; // r9
  _DWORD *v170; // rax
  __int64 v171; // rcx
  unsigned int v172; // r9d
  int v173; // edi
  unsigned int v174; // r9d
  int v175; // r15d
  unsigned int v176; // eax
  unsigned int v177; // ebx
  HANDLE v178; // rax
  _DWORD *v179; // rbx
  unsigned int v180; // r10d
  size_t v181; // rcx
  HANDLE v182; // rax
  unsigned int *v183; // rbx
  _DWORD *v184; // rdi
  unsigned __int8 *v185; // r15
  void *v186; // rax
  unsigned int v187; // r9d
  size_t v188; // rdx
  SIZE_T v189; // r8
  unsigned __int8 v190; // al
  SIZE_T v191; // rcx
  unsigned __int8 *v192; // r11
  int v193; // edx
  int v194; // r10d
  int v195; // r14d
  int v196; // r8d
  unsigned int v197; // r10d
  unsigned int v198; // ecx
  unsigned int v199; // r11d
  _BYTE *v200; // r14
  char v201; // si
  unsigned int v202; // r10d
  SIZE_T v203; // r14
  int v204; // r13d
  _BYTE *v205; // r15
  int v206; // edi
  int v207; // eax
  int v208; // ebx
  int v209; // r11d
  int v210; // edx
  int v211; // r10d
  int v212; // r8d
  int v213; // r10d
  int v214; // r9d
  int v215; // r8d
  unsigned int v216; // edx
  int v217; // r9d
  int v218; // ecx
  int v219; // edx
  int v220; // r8d
  int v221; // r9d
  int v222; // edx
  unsigned int v223; // r8d
  unsigned int v224; // r9d
  int v225; // edx
  int v226; // r8d
  int v227; // r9d
  int v228; // edx
  int v229; // r8d
  int v230; // r10d
  int v231; // edx
  int v232; // r9d
  unsigned int v233; // r8d
  int v234; // r10d
  int v235; // edx
  HANDLE v236; // rax
  _DWORD *v237; // rax
  int v238; // r15d
  HANDLE v239; // rax
  void *v240; // rcx
  _DWORD *v241; // r15
  HANDLE v242; // rax
  _OWORD *v243; // rax
  HANDLE v244; // rax
  _QWORD *v245; // rax
  LPVOID v246; // rax
  HANDLE v247; // rax
  HANDLE v248; // rax
  HANDLE v249; // rax
  HANDLE v250; // rax
  HANDLE v251; // rax
  _QWORD *v252; // rax
  HANDLE v253; // rax
  HANDLE v254; // rax
  HANDLE v255; // rax
  HANDLE v256; // rax
  __int64 v257; // rdx
  unsigned int v258; // r9d
  int v259; // r15d
  __int64 v260; // rdx
  unsigned int v261; // r9d
  __int64 v262; // rdx
  unsigned int v263; // ebx
  HANDLE v264; // rax
  _DWORD *v265; // rax
  _DWORD *v266; // rcx
  LPVOID v267; // rax
  HANDLE v268; // rax
  HANDLE v269; // rax
  HANDLE v270; // rax
  HANDLE v271; // rax
  HANDLE v272; // rax
  void *v273; // rbx
  HANDLE v274; // rax
  HANDLE v275; // rax
  _QWORD *v276; // rbx
  void *v277; // rdi
  HANDLE v278; // rax
  void *v279; // rdi
  HANDLE v280; // rax
  void *v281; // rdi
  HANDLE v282; // rax
  HANDLE v283; // rax
  void *v284; // rbx
  HANDLE v285; // rax
  int v286; // eax
  void *v287; // rcx
  void *v288; // r9
  int v289; // r10d
  void *v290; // rcx
  unsigned int *v291; // r9
  void *v292; // rcx
  unsigned int *v293; // r9
  HANDLE v294; // rax
  int v295; // eax
  __int64 v296; // rcx
  void *v297; // r9
  unsigned int v298; // r11d
  _DWORD *v299; // rcx
  unsigned int v300; // r10d
  unsigned int v301; // r9d
  int v302; // r11d
  LPVOID v303; // rcx
  unsigned int v304; // ebx
  HANDLE v305; // rax
  _DWORD *v306; // rax
  unsigned int i18; // r9d
  unsigned int v308; // r11d
  int v309; // r9d
  int v310; // r11d
  unsigned int v311; // ecx
  unsigned int v312; // r9d
  signed int v313; // eax
  FARPROC v314; // rax
  int v315; // eax
  unsigned int v316; // r9d
  SIZE_T v317; // rbx
  int v318; // r11d
  int v319; // r15d
  int v320; // r9d
  int v321; // r9d
  int v322; // r9d
  SIZE_T v323; // r11
  unsigned int v324; // r11d
  int v325; // r9d
  int v326; // r9d
  unsigned int v327; // r10d
  int v328; // r9d
  int v329; // r10d
  int v330; // r11d
  HANDLE v331; // rax
  void *v332; // rax
  bool v333; // zf
  _QWORD *v334; // rcx
  HANDLE v335; // rax
  void *v336; // rcx
  HANDLE v337; // rax
  void *v338; // rcx
  void *v339; // rax
  SIZE_T v340; // rax
  unsigned int v341; // r15d
  HANDLE v342; // rax
  void *v343; // rcx
  _QWORD *v344; // rax
  HANDLE v345; // rax
  HANDLE v346; // rax
  HANDLE v347; // rax
  HANDLE v348; // rax
  SIZE_T *v349; // rdx
  unsigned int *v350; // rcx
  HANDLE v351; // rax
  HANDLE v352; // rax
  HANDLE v353; // rax
  HANDLE v354; // rax
  unsigned __int64 v355; // r15
  _BYTE *v356; // r11
  unsigned __int8 v357; // al
  unsigned int v358; // r8d
  int v359; // r10d
  unsigned int v360; // r9d
  int v361; // r14d
  unsigned __int8 *v362; // rsi
  int v363; // eax
  int v364; // r8d
  int v365; // r8d
  unsigned int v366; // r10d
  unsigned int v367; // ebx
  unsigned int v368; // ecx
  int v369; // edx
  char *v370; // r14
  char v371; // si
  SIZE_T v372; // rcx
  int v373; // r11d
  unsigned __int8 *v374; // rsi
  wchar_t *v375; // r15
  int v376; // r13d
  int v377; // r12d
  SIZE_T v378; // rax
  int v379; // ecx
  int v380; // edi
  int v381; // ebx
  int v382; // edi
  int v383; // edx
  int v384; // ebx
  unsigned int v385; // r8d
  int v386; // r9d
  unsigned int v387; // edx
  int v388; // r8d
  int v389; // r9d
  unsigned int v390; // edx
  int v391; // r8d
  int v392; // r10d
  int v393; // r11d
  unsigned int v394; // r9d
  int v395; // r8d
  unsigned int v396; // r9d
  int v397; // r10d
  int v398; // r11d
  int v399; // edx
  int v400; // r8d
  unsigned int v401; // r9d
  int v402; // edx
  int v403; // r10d
  int v404; // r8d
  unsigned int v405; // edx
  int v406; // r8d
  unsigned __int64 i19; // rcx
  int v408; // r15d
  void *v409; // r9
  void *v410; // r10
  _DWORD *v411; // r11
  int v412; // ecx
  __int64 v413; // rdx
  const void *v414; // rcx
  SIZE_T v415; // rcx
  void *v416; // r11
  void *v417; // r10
  void *v418; // r9
  SIZE_T v419; // r10
  __int64 v420; // r11
  SIZE_T v421; // r9
  unsigned int *v422; // r9
  unsigned __int64 v423; // r10
  unsigned int v424; // r11d
  __int64 v425; // rdx
  __int64 v426; // r9
  unsigned int v427; // edx
  void *v428; // r9
  HANDLE v429; // rax
  void *v430; // rcx
  int v431; // r9d
  unsigned int v432; // r10d
  __int64 v433; // r11
  int *v434; // r15
  unsigned int i17; // r9d
  unsigned int v436; // r10d
  int v437; // r9d
  int v438; // r9d
  __int64 v439; // r11
  size_t *v440; // rdx
  size_t v441; // rax
  LPVOID v442; // rcx
  unsigned int v443; // r9d
  unsigned int v444; // r10d
  int v445; // r9d
  int v446; // r9d
  __int64 v447; // r11
  int *v448; // rdx
  int v449; // eax
  LPVOID v450; // rcx
  int v451; // eax
  unsigned int v452; // r10d
  unsigned int v453; // r9d
  unsigned int *v454; // rcx
  unsigned int v455; // r9d
  unsigned int v456; // ebx
  int v457; // r9d
  int v458; // r9d
  _DWORD *v459; // rdx
  unsigned int v460; // r9d
  unsigned int *v461; // rcx
  unsigned int v462; // ebx
  int v463; // r9d
  int v464; // eax
  int v465; // r9d
  size_t v466; // r10
  const void *v467; // r11
  int *v468; // rcx
  int v469; // ecx
  __int64 v470; // rax
  unsigned int v471; // edi
  int v472; // eax
  const WCHAR *v473; // rax
  __int64 *v474; // r12
  WCHAR *v475; // rsi
  int v476; // edi
  int v477; // eax
  int v478; // r10d
  int v479; // r8d
  __int64 v480; // r14
  int v481; // ecx
  int v482; // ebx
  int v483; // r11d
  int v484; // ebx
  int v485; // edx
  int v486; // r11d
  unsigned int v487; // r8d
  int v488; // r9d
  unsigned int v489; // edx
  int v490; // r10d
  int v491; // r8d
  unsigned int v492; // r9d
  int v493; // r10d
  int v494; // edx
  int v495; // r8d
  unsigned int v496; // r9d
  int v497; // edx
  int v498; // r8d
  unsigned int v499; // r10d
  unsigned int v500; // r8d
  int v501; // r9d
  int v502; // edx
  unsigned int v503; // r8d
  int v504; // r9d
  int v505; // edx
  int v506; // r8d
  unsigned int v507; // r9d
  int v508; // r10d
  int v509; // ecx
  const WCHAR *v510; // r13
  unsigned __int64 v511; // rcx
  char v512; // al
  __int64 kk; // rbx
  HMODULE v514; // rcx
  int v515; // ebx
  __int64 v516; // rbx
  __int64 v517; // rax
  HMODULE *v518; // r12
  const WCHAR *v519; // r13
  LPVOID v520; // rcx
  __int64 v521; // rax
  char *v522; // rdx
  unsigned int v523; // edx
  unsigned int v524; // eax
  __int64 v525; // r12
  __int64 (__fastcall *v526)(); // rax
  WCHAR *v527; // r12
  HANDLE v528; // rax
  int v529; // eax
  const WCHAR *v530; // rax
  WCHAR *v531; // r14
  __int64 *v532; // r12
  int v533; // edi
  int v534; // eax
  int v535; // r9d
  int v536; // r8d
  __int64 v537; // rsi
  int v538; // ecx
  int v539; // ebx
  int v540; // r11d
  int v541; // ebx
  int v542; // edx
  int v543; // r11d
  unsigned int v544; // r8d
  int v545; // r9d
  unsigned int v546; // r10d
  int v547; // edx
  int v548; // r8d
  unsigned int v549; // r9d
  int v550; // r10d
  int v551; // edx
  int v552; // r8d
  unsigned int v553; // r9d
  int v554; // edx
  int v555; // r8d
  unsigned int v556; // r10d
  unsigned int v557; // r8d
  int v558; // r9d
  int v559; // edx
  unsigned int v560; // r8d
  int v561; // r9d
  int v562; // edx
  int v563; // r8d
  unsigned int v564; // r9d
  int v565; // edx
  int v566; // r8d
  char v567; // al
  unsigned __int64 v568; // rcx
  const WCHAR *v569; // r13
  __int64 mm; // rbx
  HMODULE v571; // rcx
  int v572; // ebx
  __int64 v573; // rbx
  __int64 v574; // rax
  HMODULE *v575; // r12
  const WCHAR *v576; // r13
  LPVOID v577; // rcx
  __int64 v578; // rax
  char *v579; // rdx
  unsigned int v580; // edx
  unsigned int v581; // eax
  __int64 v582; // r12
  __int64 (__fastcall *v583)(); // rax
  WCHAR *v584; // r12
  HANDLE v585; // rax
  signed int v586; // eax
  signed int v587; // ebx
  unsigned int v588; // r13d
  bool v589; // sf
  void *v590; // rax
  SIZE_T v591; // r12
  void *v592; // rax
  _DWORD *v593; // r13
  bool v594; // sf
  unsigned int i5; // esi
  __int64 v596; // rax
  unsigned int v597; // eax
  unsigned int v598; // r8d
  unsigned int i6; // edx
  __int64 v600; // rbx
  __int64 v601; // rcx
  const wchar_t *v602; // rcx
  __int64 i7; // rdx
  __int64 v604; // rax
  char *v605; // rax
  char *v606; // r12
  __int64 *v607; // rbx
  char *v608; // r13
  int v609; // esi
  int v610; // edi
  int v611; // r9d
  int v612; // edx
  __int64 v613; // r14
  int v614; // eax
  int v615; // r11d
  int v616; // r10d
  int v617; // r11d
  int v618; // ecx
  int v619; // r10d
  unsigned int v620; // edx
  int v621; // r8d
  unsigned int v622; // r9d
  int v623; // ecx
  int v624; // edx
  unsigned int v625; // r8d
  int v626; // r9d
  int v627; // ecx
  int v628; // edx
  unsigned int v629; // r8d
  int v630; // ecx
  int v631; // edx
  unsigned int v632; // r9d
  unsigned int v633; // edx
  int v634; // r8d
  int v635; // ecx
  unsigned int v636; // edx
  int v637; // r8d
  int v638; // ecx
  int v639; // edx
  unsigned int v640; // r8d
  int v641; // r9d
  int v642; // eax
  unsigned __int64 v643; // rax
  __m128 v644; // xmm1
  __int64 v645; // r13
  __m128 v646; // xmm0
  __m128 v647; // xmm0
  __m128 v648; // xmm1
  __m128 v649; // xmm1
  __m128 v650; // xmm1
  int v651; // r8d
  unsigned int v652; // edx
  unsigned int i8; // ecx
  __int64 v654; // rax
  void *v655; // rax
  void **v656; // r12
  unsigned int v657; // eax
  unsigned int v658; // ecx
  __int64 v659; // r13
  __int64 v660; // r9
  signed int v661; // eax
  void *v662; // rax
  __int64 v663; // r9
  signed int v664; // eax
  __int64 i9; // r13
  _BYTE *v666; // rax
  __int64 v667; // rcx
  __int64 i10; // rcx
  _BYTE *v669; // rax
  signed int v670; // eax
  int v671; // r13d
  unsigned int v672; // ebx
  const WCHAR *v673; // rax
  int v674; // eax
  __int64 v675; // rax
  bool v676; // sf
  const unsigned __int16 *v677; // rbx
  int v678; // eax
  __int64 v679; // rax
  bool v680; // sf
  unsigned int v681; // eax
  int v682; // eax
  unsigned int v683; // r12d
  void *v684; // rbx
  void *v685; // rbx
  __int64 v686; // rdx
  signed int v687; // eax
  int v688; // eax
  __int64 v689; // rax
  bool v690; // sf
  void *v691; // rbx
  __int64 v692; // r12
  unsigned int v693; // ebx
  int v694; // eax
  int v695; // r12d
  int v696; // ebx
  int v697; // r13d
  int v698; // r13d
  __int64 v699; // rax
  int v700; // edx
  int v701; // ecx
  int v702; // r13d
  __int64 v703; // rax
  int v704; // r13d
  int v705; // eax
  HMODULE v706; // rcx
  unsigned int v707; // ebx
  __int64 v708; // rax
  int v709; // edi
  int v710; // r12d
  LPVOID v711; // rbx
  int v712; // eax
  signed int v713; // r13d
  __int64 v714; // rax
  size_t v715; // rax
  size_t v716; // rbx
  __int64 v717; // rax
  signed int v718; // eax
  signed int v719; // edi
  void *v720; // rax
  __int64 (__fastcall *v721)(); // rbx
  __int64 v722; // rax
  int v723; // eax
  int v724; // r10d
  int v725; // r9d
  int v726; // r8d
  int v727; // ecx
  int v728; // edx
  int v729; // edi
  unsigned __int8 v730; // r14
  signed int v731; // esi
  const WCHAR *v732; // rdx
  const wchar_t *v733; // rax
  char v734; // r15
  signed int v735; // r9d
  char v736; // bl
  LPCWSTR v737; // r8
  const wchar_t *v738; // r10
  unsigned __int8 v739; // dl
  int v740; // r8d
  int v741; // r9d
  int v742; // edx
  int v743; // r8d
  int v744; // ecx
  LPVOID v745; // rbx
  __int64 v746; // rax
  size_t v747; // rax
  size_t v748; // r13
  LPVOID v749; // rbx
  signed int v750; // eax
  void *v751; // rax
  __int64 (__fastcall *v752)(); // rbx
  __int64 v753; // rax
  int v754; // r10d
  int v755; // r9d
  int v756; // r8d
  int v757; // ecx
  int v758; // r12d
  int v759; // ebx
  const wchar_t *v760; // rsi
  size_t v761; // rax
  char v762; // r13
  LPCWSTR v763; // r8
  char v764; // r14
  _BYTE *v765; // r10
  unsigned __int8 v766; // bl
  int v767; // r9d
  unsigned __int8 v768; // dl
  int v769; // r8d
  int v770; // r9d
  int v771; // edx
  int v772; // r8d
  int v773; // ecx
  LPVOID v774; // rbx
  LPVOID v775; // r12
  _BYTE *v776; // rax
  __int64 v777; // rcx
  __int64 nn; // rcx
  _BYTE *v779; // rax
  __int64 v780; // rcx
  __int64 i1; // rcx
  _BYTE *v782; // rcx
  __int64 v783; // rax
  __int64 v784; // rax
  int v785; // eax
  __int64 i2; // rbx
  HMODULE v787; // rcx
  int v788; // r13d
  int v789; // ebx
  size_t v790; // r12
  char v791; // al
  int v792; // edi
  int v793; // edx
  unsigned int v794; // r9d
  int v795; // ebx
  int v796; // ecx
  int v797; // r13d
  unsigned int v798; // eax
  void *v799; // rax
  LPVOID v800; // rax
  __int64 v801; // rax
  size_t v802; // rcx
  int v803; // eax
  int v804; // ebx
  signed int v805; // edi
  SIZE_T v806; // rax
  bool v807; // sf
  size_t v808; // rbx
  __int64 v809; // rax
  __int64 (__fastcall *v810)(); // rbx
  __int64 v811; // rax
  size_t v812; // rbx
  int v813; // eax
  int v814; // edx
  int v815; // r9d
  int v816; // r11d
  int v817; // r10d
  int v818; // ecx
  int v819; // r8d
  __int64 v820; // r8
  unsigned __int8 v821; // r14
  int v822; // esi
  const wchar_t *v823; // rbx
  size_t v824; // rax
  char v825; // r15
  int v826; // r9d
  char v827; // r13
  LPCWSTR v828; // r8
  _BYTE *v829; // r10
  unsigned __int8 v830; // dl
  int v831; // r8d
  int v832; // r9d
  int v833; // edx
  int v834; // r8d
  int v835; // ecx
  signed int v836; // edi
  LPVOID v837; // rbx
  __int64 v838; // rax
  SIZE_T v839; // rax
  bool v840; // sf
  size_t v841; // rbx
  void *v842; // rax
  __int64 (__fastcall *v843)(); // rbx
  __int64 v844; // rax
  size_t v845; // rbx
  int v846; // r9d
  int v847; // edx
  int v848; // r8d
  int v849; // ecx
  int v850; // r11d
  signed int v851; // esi
  const wchar_t *v852; // rdx
  size_t v853; // rax
  char v854; // bl
  LPCWSTR v855; // r8
  char v856; // r14
  _BYTE *v857; // r10
  unsigned __int8 v858; // r11
  signed int v859; // r9d
  unsigned __int8 v860; // dl
  int v861; // r8d
  int v862; // r9d
  int v863; // edx
  int v864; // r8d
  int v865; // ecx
  int v866; // eax
  _BYTE *v867; // rax
  int v868; // r8d
  _BYTE *v869; // r12
  __int64 *v870; // r14
  __int64 v871; // rax
  int v872; // r13d
  int v873; // esi
  int v874; // r10d
  int v875; // ecx
  int v876; // ebx
  int v877; // r11d
  int v878; // ebx
  int v879; // edx
  int v880; // r11d
  unsigned int v881; // r8d
  int v882; // r9d
  unsigned int v883; // edx
  int v884; // r10d
  int v885; // r8d
  unsigned int v886; // r9d
  int v887; // r10d
  int v888; // edx
  int v889; // r8d
  unsigned int v890; // r9d
  int v891; // edx
  int v892; // r8d
  unsigned int v893; // r10d
  unsigned int v894; // r8d
  int v895; // r9d
  int v896; // edx
  unsigned int v897; // r8d
  int v898; // r9d
  int v899; // edx
  int v900; // r8d
  unsigned int v901; // r9d
  int v902; // r10d
  int v903; // ecx
  const WCHAR *v904; // rdi
  unsigned __int64 v905; // rcx
  char v906; // al
  __int64 i3; // rbx
  HMODULE v908; // rcx
  int v909; // ebx
  unsigned int v910; // r12d
  __int64 v911; // rbx
  __int64 v912; // r12
  HMODULE *v913; // r13
  const WCHAR *v914; // rdi
  __int64 v915; // rax
  char *v916; // rdx
  unsigned int v917; // edx
  unsigned int v918; // eax
  int v919; // ecx
  __int64 v920; // r12
  __int64 (__fastcall *v921)(); // rax
  void *v922; // rdi
  HANDLE v923; // rax
  int v924; // eax
  __int64 i4; // rbx
  HMODULE v926; // rcx
  void *v927; // r13
  _DWORD *v928; // rdi
  HANDLE v929; // rax
  _OWORD *v930; // rax
  void *v931; // r12
  HANDLE v932; // rax
  _QWORD *v933; // rax
  void *v934; // rdi
  unsigned int v935; // r10d
  unsigned int v936; // r11d
  int v937; // eax
  unsigned int v938; // r10d
  unsigned int v939; // r11d
  int v940; // r9d
  int v941; // eax
  unsigned int v942; // r10d
  unsigned int v943; // r11d
  int v944; // r9d
  int v945; // eax
  int v946; // r9d
  unsigned int v947; // ebx
  HANDLE v948; // rax
  const WCHAR *v949; // rax
  WCHAR *v950; // rbx
  unsigned int v951; // r10d
  unsigned int v952; // r11d
  unsigned int *v953; // rax
  unsigned int v954; // ebx
  unsigned int v955; // r10d
  LPCWSTR v956; // r9
  unsigned int v957; // r11d
  unsigned int m; // ebx
  __int64 v959; // rdx
  __int64 v960; // r9
  unsigned int *v961; // r9
  unsigned int v962; // r11d
  size_t v963; // r8
  unsigned int v964; // r10d
  LPCWSTR v965; // r9
  unsigned int v966; // r11d
  __int64 v967; // rdx
  __int64 v968; // r9
  int v969; // r11d
  _DWORD *v970; // r9
  LPCWSTR v971; // r10
  unsigned int v972; // r9d
  unsigned int v973; // r10d
  unsigned int v974; // r11d
  __int64 v975; // rdx
  __int64 v976; // r10
  int v977; // r11d
  int v978; // eax
  _DWORD *v979; // r10
  _QWORD *v980; // rax
  LPVOID v981; // rcx
  __int64 v982; // rcx
  unsigned int v983; // r11d
  unsigned int v984; // r9d
  void *v985; // r11
  int v986; // edi
  int v987; // ecx
  void *v988; // r9
  unsigned int v989; // r10d
  unsigned int *v990; // r11
  unsigned int v991; // eax
  unsigned int v992; // ebx
  HANDLE v993; // rax
  char *v994; // rax
  char *v995; // rbx
  unsigned int v996; // r9d
  size_t v997; // rcx
  HANDLE v998; // rax
  int v999; // ecx
  unsigned int *v1000; // rbx
  unsigned int *v1001; // rdi
  unsigned __int8 v1002; // al
  SIZE_T v1003; // r8
  SIZE_T v1004; // r11
  const WCHAR *v1005; // r9
  unsigned int v1006; // r10d
  unsigned int v1007; // r14d
  int v1008; // esi
  int v1009; // ebx
  int v1010; // r8d
  unsigned int v1011; // r9d
  unsigned int v1012; // r8d
  int v1013; // ecx
  int v1014; // edx
  _BYTE *v1015; // rsi
  unsigned int v1016; // r14d
  char v1017; // di
  unsigned int v1018; // r9d
  LPCWSTR v1019; // r14
  SIZE_T v1020; // r12
  _BYTE *v1021; // rdi
  int v1022; // r13d
  int v1023; // r10d
  int v1024; // r15d
  int v1025; // eax
  int v1026; // ecx
  int v1027; // ebx
  int v1028; // r11d
  int v1029; // ebx
  int v1030; // r11d
  int v1031; // edx
  int v1032; // r9d
  int v1033; // r10d
  int v1034; // r8d
  int v1035; // r9d
  unsigned int v1036; // edx
  int v1037; // r8d
  int v1038; // ecx
  int v1039; // edx
  int v1040; // r8d
  int v1041; // r9d
  int v1042; // edx
  unsigned int v1043; // r8d
  unsigned int v1044; // r9d
  int v1045; // edx
  int v1046; // r8d
  int v1047; // r9d
  int v1048; // edx
  int v1049; // r8d
  int v1050; // r9d
  int v1051; // edx
  int v1052; // r8d
  unsigned int v1053; // r9d
  int v1054; // edx
  HANDLE v1055; // rax
  _DWORD *v1056; // rax
  void *v1057; // rsi
  unsigned int v1058; // esi
  HANDLE v1059; // rax
  void *v1060; // rax
  HANDLE v1061; // rax
  _OWORD *v1062; // rcx
  _DWORD *v1063; // rax
  HANDLE v1064; // rax
  _QWORD *v1065; // rax
  LPVOID v1066; // rax
  HANDLE v1067; // rax
  HANDLE v1068; // rax
  HANDLE v1069; // rax
  HANDLE v1070; // rax
  void *v1071; // rcx
  HANDLE v1072; // rax
  LPVOID v1073; // rax
  HANDLE v1074; // rax
  HANDLE v1075; // rax
  HANDLE v1076; // rax
  HANDLE v1077; // rax
  int v1078; // eax
  __int64 v1079; // rdx
  unsigned int v1080; // r9d
  __int64 v1081; // rdx
  unsigned int v1082; // r9d
  __int64 v1083; // rdx
  unsigned int v1084; // ebx
  HANDLE v1085; // rax
  _DWORD *v1086; // rax
  void *v1087; // rcx
  int v1088; // r9d
  LPVOID v1089; // rcx
  unsigned int *v1090; // r9
  LPVOID v1091; // rcx
  unsigned int *v1092; // r9
  int v1093; // eax
  HANDLE v1094; // rax
  int v1095; // eax
  int v1096; // r9d
  __int64 v1097; // rcx
  _DWORD *v1098; // rcx
  int n; // r10d
  unsigned int v1100; // r11d
  int v1101; // r10d
  size_t v1102; // rcx
  unsigned int ii; // r10d
  unsigned int v1104; // r11d
  int v1105; // r10d
  unsigned int v1106; // ecx
  unsigned int v1107; // r10d
  unsigned int v1108; // ebx
  HANDLE v1109; // rax
  unsigned int *v1110; // rax
  int v1111; // eax
  bool v1112; // sf
  FARPROC ProcAddress; // rax
  unsigned int v1114; // r9d
  void *v1115; // r14
  const WCHAR *v1116; // rbx
  int v1117; // ecx
  int v1118; // r9d
  int v1119; // r9d
  int v1120; // r9d
  SIZE_T v1121; // r11
  unsigned int v1122; // r11d
  int v1123; // r9d
  int v1124; // r9d
  unsigned int v1125; // r10d
  int v1126; // r9d
  int v1127; // r10d
  int v1128; // r11d
  HANDLE v1129; // rax
  _QWORD *v1130; // rax
  SIZE_T v1131; // rcx
  HANDLE v1132; // rax
  void *v1133; // rcx
  SIZE_T v1134; // rax
  HANDLE v1135; // rax
  void *v1136; // rcx
  const WCHAR *v1137; // rax
  HANDLE v1138; // rax
  void *v1139; // rcx
  void *v1140; // rcx
  HANDLE v1141; // rax
  HANDLE v1142; // rax
  HANDLE v1143; // rax
  HANDLE v1144; // rax
  LPVOID *v1145; // rdx
  unsigned int *v1146; // rax
  HANDLE v1147; // rax
  HANDLE v1148; // rax
  HANDLE v1149; // rax
  HANDLE v1150; // rax
  void *v1151; // rax
  _BYTE *v1152; // r9
  size_t v1153; // r10
  unsigned __int8 v1154; // al
  STRSAFE_PCNZWCH v1155; // r11
  int v1156; // r14d
  int v1157; // eax
  unsigned int v1158; // r10d
  int v1159; // ecx
  _BYTE *v1160; // rcx
  int v1161; // r8d
  unsigned int v1162; // edx
  unsigned int v1163; // r8d
  unsigned int v1164; // r11d
  unsigned int v1165; // ebx
  unsigned int v1166; // r10d
  int v1167; // r14d
  char v1168; // r9
  int v1169; // r11d
  int v1170; // r15d
  unsigned __int64 v1171; // r12
  _BYTE *v1172; // rsi
  int v1173; // r13d
  unsigned int v1174; // r10d
  unsigned __int8 *v1175; // rax
  int v1176; // ecx
  int v1177; // edi
  int v1178; // ebx
  int v1179; // edi
  int v1180; // edx
  int v1181; // ebx
  unsigned int v1182; // r8d
  int v1183; // r9d
  unsigned int v1184; // edx
  int v1185; // r8d
  int v1186; // r9d
  unsigned int v1187; // edx
  int v1188; // r8d
  int v1189; // r10d
  int v1190; // r11d
  unsigned int v1191; // r9d
  int v1192; // edx
  int v1193; // r8d
  unsigned int v1194; // r9d
  int v1195; // edx
  int v1196; // r8d
  int v1197; // r9d
  int v1198; // edx
  unsigned int v1199; // r8d
  int v1200; // r9d
  int v1201; // edx
  int v1202; // r8d
  unsigned int v1203; // r9d
  unsigned int v1204; // r11d
  int v1205; // edx
  int v1206; // r8d
  size_t jj; // rcx
  void *v1208; // r14
  int v1209; // ecx
  _DWORD *v1210; // r9
  int v1211; // r10d
  int v1212; // r10d
  unsigned int v1213; // r11d
  unsigned int v1214; // r10d
  size_t v1215; // r11
  size_t v1216; // r8
  const void *v1217; // r11
  STRSAFE_PCNZWCH v1218; // r10
  void *v1219; // r9
  LPCWSTR v1220; // r9
  SIZE_T v1221; // r9
  unsigned int *v1222; // r10
  __int64 v1223; // rdx
  __int64 v1224; // r10
  void *v1225; // r14
  HANDLE v1226; // rax
  size_t v1227; // rsi
  LPVOID v1228; // rax
  int v1229; // eax
  void *v1230; // rsi
  HANDLE v1231; // rax
  void *v1232; // rsi
  HANDLE v1233; // rax
  void *v1234; // rsi
  HANDLE v1235; // rax
  void *v1236; // rsi
  HANDLE v1237; // rax
  HANDLE v1238; // rax
  void *v1239; // rbx
  HANDLE v1240; // rax
  HANDLE v1241; // rax
  _QWORD *v1242; // rbx
  void *v1243; // rdi
  HANDLE v1244; // rax
  void *v1245; // rdi
  HANDLE v1246; // rax
  void *v1247; // rdi
  HANDLE v1248; // rax
  HANDLE v1249; // rax
  HANDLE v1250; // rax
  unsigned int v1251; // r9d
  unsigned int v1252; // r10d
  const WCHAR *v1253; // r11
  LPCWSTR v1254; // rcx
  size_t v1255; // rcx
  int v1256; // r9d
  __int64 v1257; // rbx
  unsigned int v1258; // r10d
  int v1259; // r9d
  void *v1260; // rbx
  HANDLE v1261; // rax
  HANDLE v1262; // rax
  HANDLE v1263; // rax
  HANDLE v1264; // rax
  unsigned int v1265; // edi
  int v1266; // eax
  __int64 i11; // rbx
  HMODULE v1268; // rcx
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v1271; // [rsp+68h] [rbp-98h] BYREF
  int v1272; // [rsp+6Ch] [rbp-94h] BYREF
  char v1273; // [rsp+70h] [rbp-90h]
  SIZE_T v1274; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1275; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v1276; // [rsp+88h] [rbp-78h]
  LPVOID v1277; // [rsp+90h] [rbp-70h]
  void *v1278; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v1279; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T v1280; // [rsp+A8h] [rbp-58h] BYREF
  size_t pcchLength; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpModuleName; // [rsp+B8h] [rbp-48h] BYREF
  void *v1283; // [rsp+C0h] [rbp-40h] BYREF
  size_t v1284; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v1285; // [rsp+D0h] [rbp-30h]
  SIZE_T Size; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v1287; // [rsp+E0h] [rbp-20h] BYREF
  void *v1288; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID v1289; // [rsp+F0h] [rbp-10h]
  STRSAFE_PCNZWCH psz; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v1291; // [rsp+100h] [rbp+0h]
  __int64 v1292; // [rsp+108h] [rbp+8h]
  SIZE_T v1293; // [rsp+110h] [rbp+10h]
  LPVOID Src[2]; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v1295; // [rsp+128h] [rbp+28h] BYREF
  _DWORD *v1296; // [rsp+130h] [rbp+30h] BYREF
  SIZE_T v1297; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v1298; // [rsp+140h] [rbp+40h]
  LPVOID v1299; // [rsp+148h] [rbp+48h]
  unsigned int v1300; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v1301; // [rsp+158h] [rbp+58h]
  size_t v1302[2]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v1303; // [rsp+170h] [rbp+70h] BYREF
  __int128 v1304; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v1305; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1306; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned int v1307; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1308; // [rsp+194h] [rbp+94h]
  __int128 v1309; // [rsp+198h] [rbp+98h]
  __int64 v1310; // [rsp+1A8h] [rbp+A8h]
  unsigned int v1311; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v1312; // [rsp+1B4h] [rbp+B4h] BYREF
  unsigned int v1313; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v1314; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned int v1315; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v1316; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1317; // [rsp+1C8h] [rbp+C8h] BYREF
  int v1318; // [rsp+1CCh] [rbp+CCh] BYREF
  LPVOID lpMem; // [rsp+1D0h] [rbp+D0h]
  _BYTE *v1320; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int *v1321; // [rsp+1E8h] [rbp+E8h] BYREF
  HMODULE phModule; // [rsp+1F0h] [rbp+F0h] BYREF
  HMODULE hModule; // [rsp+200h] [rbp+100h] BYREF
  __int128 v1324; // [rsp+208h] [rbp+108h] BYREF
  __int128 v1325; // [rsp+218h] [rbp+118h]
  __int128 v1326; // [rsp+228h] [rbp+128h] BYREF
  __int128 v1327; // [rsp+238h] [rbp+138h]
  __int64 v1328; // [rsp+248h] [rbp+148h] BYREF
  unsigned int *v1329; // [rsp+258h] [rbp+158h]
  __int64 v1330; // [rsp+260h] [rbp+160h] BYREF
  __int64 v1331; // [rsp+268h] [rbp+168h] BYREF
  __int64 v1332; // [rsp+270h] [rbp+170h] BYREF
  __int128 v1333; // [rsp+278h] [rbp+178h] BYREF
  __int64 v1334[17]; // [rsp+288h] [rbp+188h] BYREF
  _OWORD v1335[3]; // [rsp+310h] [rbp+210h] BYREF
  _QWORD v1336[20]; // [rsp+340h] [rbp+240h] BYREF
  int v1337; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v1338; // [rsp+3E4h] [rbp+2E4h]
  void *v1339; // [rsp+3E8h] [rbp+2E8h]
  void *v1340; // [rsp+3F0h] [rbp+2F0h]
  void *v1341; // [rsp+3F8h] [rbp+2F8h]
  const wchar_t *v1342; // [rsp+400h] [rbp+300h]
  const wchar_t *v1343; // [rsp+408h] [rbp+308h]
  __int64 v1344; // [rsp+410h] [rbp+310h]
  int v1345; // [rsp+418h] [rbp+318h]
  int v1346; // [rsp+41Ch] [rbp+31Ch] BYREF
  int v1347; // [rsp+420h] [rbp+320h]
  int v1348; // [rsp+424h] [rbp+324h]
  int v1349; // [rsp+428h] [rbp+328h]
  int v1350; // [rsp+42Ch] [rbp+32Ch] BYREF
  int v1351; // [rsp+430h] [rbp+330h]
  int v1352; // [rsp+434h] [rbp+334h]
  unsigned int v1353; // [rsp+438h] [rbp+338h]
  unsigned int v1354; // [rsp+43Ch] [rbp+33Ch] BYREF
  unsigned int v1355; // [rsp+440h] [rbp+340h]
  unsigned int v1356; // [rsp+444h] [rbp+344h]
  unsigned int v1357; // [rsp+448h] [rbp+348h]
  int v1358; // [rsp+450h] [rbp+350h] BYREF
  _DWORD v1359[3]; // [rsp+454h] [rbp+354h] BYREF
  __int16 v1360; // [rsp+462h] [rbp+362h]
  __int64 v1361; // [rsp+468h] [rbp+368h]
  int v1362; // [rsp+4C0h] [rbp+3C0h] BYREF
  _DWORD v1363[5]; // [rsp+4C4h] [rbp+3C4h] BYREF
  const wchar_t *v1364; // [rsp+4D8h] [rbp+3D8h]
  int v1365; // [rsp+530h] [rbp+430h] BYREF
  _DWORD v1366[5]; // [rsp+534h] [rbp+434h] BYREF
  size_t v1367; // [rsp+548h] [rbp+448h]
  int v1368; // [rsp+5A0h] [rbp+4A0h] BYREF
  _DWORD v1369[5]; // [rsp+5A4h] [rbp+4A4h] BYREF
  size_t v1370; // [rsp+5B8h] [rbp+4B8h]
  int v1371; // [rsp+610h] [rbp+510h] BYREF
  _DWORD v1372[5]; // [rsp+614h] [rbp+514h] BYREF
  size_t v1373; // [rsp+628h] [rbp+528h]
  int v1374; // [rsp+680h] [rbp+580h] BYREF
  char v1375[20]; // [rsp+684h] [rbp+584h] BYREF
  const WCHAR *v1376; // [rsp+698h] [rbp+598h]
  int v1377; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v1378[20]; // [rsp+6F4h] [rbp+5F4h] BYREF
  const WCHAR *v1379; // [rsp+708h] [rbp+608h]
  int v1380; // [rsp+760h] [rbp+660h] BYREF
  char v1381[20]; // [rsp+764h] [rbp+664h] BYREF
  const WCHAR *v1382; // [rsp+778h] [rbp+678h]
  int v1383; // [rsp+7D0h] [rbp+6D0h] BYREF
  char v1384[20]; // [rsp+7D4h] [rbp+6D4h] BYREF
  const WCHAR *v1385; // [rsp+7E8h] [rbp+6E8h]
  __int128 v1386; // [rsp+840h] [rbp+740h] BYREF
  __int128 v1387; // [rsp+850h] [rbp+750h] BYREF
  __int128 v1388; // [rsp+860h] [rbp+760h] BYREF
  __int128 v1389; // [rsp+870h] [rbp+770h] BYREF
  __int64 v1390; // [rsp+880h] [rbp+780h] BYREF
  int v1391; // [rsp+888h] [rbp+788h]
  int v1392; // [rsp+88Ch] [rbp+78Ch]
  _DWORD v1393[12]; // [rsp+890h] [rbp+790h] BYREF
  __int128 v1394; // [rsp+8C0h] [rbp+7C0h] BYREF
  __int128 v1395; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v1396; // [rsp+8E0h] [rbp+7E0h]
  __int128 v1397; // [rsp+8E8h] [rbp+7E8h] BYREF
  _OWORD v1398[2]; // [rsp+8F8h] [rbp+7F8h] BYREF
  __int128 v1399; // [rsp+918h] [rbp+818h] BYREF
  _OWORD v1400[2]; // [rsp+928h] [rbp+828h] BYREF
  __int128 v1401; // [rsp+948h] [rbp+848h] BYREF
  _OWORD v1402[2]; // [rsp+958h] [rbp+858h] BYREF
  __int128 v1403; // [rsp+978h] [rbp+878h] BYREF
  _OWORD v1404[2]; // [rsp+988h] [rbp+888h] BYREF
  __int128 v1405; // [rsp+9A8h] [rbp+8A8h] BYREF
  __int128 v1406; // [rsp+9B8h] [rbp+8B8h] BYREF
  __int64 v1407; // [rsp+9C8h] [rbp+8C8h]
  _OWORD v1408[2]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _DWORD v1409[6]; // [rsp+9F0h] [rbp+8F0h] BYREF
  char v1410; // [rsp+A0Ah] [rbp+90Ah]
  unsigned __int16 v1411[34]; // [rsp+A0Ch] [rbp+90Ch] BYREF
  _DWORD v1412[6]; // [rsp+A50h] [rbp+950h] BYREF
  char v1413; // [rsp+A6Ah] [rbp+96Ah]
  unsigned __int16 v1414[34]; // [rsp+A6Ch] [rbp+96Ch] BYREF
  _DWORD v1415[6]; // [rsp+AB0h] [rbp+9B0h] BYREF
  char v1416; // [rsp+ACAh] [rbp+9CAh]
  unsigned __int16 v1417[34]; // [rsp+ACCh] [rbp+9CCh] BYREF
  _BYTE v1418[68]; // [rsp+B10h] [rbp+A10h] BYREF
  __int16 v1419; // [rsp+B54h] [rbp+A54h]
  unsigned __int16 v1420; // [rsp+BB6h] [rbp+AB6h]
  int v1421; // [rsp+BBCh] [rbp+ABCh]
  int v1422; // [rsp+BC0h] [rbp+AC0h]
  int v1423; // [rsp+BF0h] [rbp+AF0h] BYREF
  __int128 v1424; // [rsp+BF8h] [rbp+AF8h]
  __int128 v1425; // [rsp+C08h] [rbp+B08h]
  __int128 v1426; // [rsp+C18h] [rbp+B18h]
  __int64 v1427; // [rsp+C28h] [rbp+B28h]
  _BYTE v1428[176]; // [rsp+C30h] [rbp+B30h] BYREF
  WCHAR Filename[264]; // [rsp+CE0h] [rbp+BE0h] BYREF

  psz = a1;
  v1329 = a2;
  v1321 = 0;
  if ( a1 && a2 )
  {
    v1271 = 0;
    v1303 = 0;
    while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
      ;
    v3 = dword_18003E488;
    v1300 = -1;
    if ( !dword_18003E488 )
    {
      v4 = MemoryAlloc(0x338u);
      v5 = v4;
      if ( !v4 )
        goto LABEL_14;
      v6 = qword_1800349B0;
      v7 = v4;
      v8 = 0;
      v9 = -1;
      v10 = 0;
      v11 = 0;
      v12 = 103;
      do
      {
        v13 = *((unsigned __int8 *)v6 + 1);
        v14 = *(unsigned __int8 *)v6;
        v15 = *((unsigned __int8 *)v6++ + 4);
        v16 = *((unsigned __int8 *)v6 - 5) | ((*((unsigned __int8 *)v6 - 6) | ((v13 | (v14 << 8)) << 8)) << 8);
        v17 = v11 ^ v16;
        v18 = *((unsigned __int8 *)v6 - 1)
            | ((*((unsigned __int8 *)v6 - 2) | ((*((unsigned __int8 *)v6 - 3) | (v15 << 8)) << 8)) << 8);
        v19 = v10 ^ v18 ^ v11 ^ v16 ^ 0xAC987321;
        v20 = v17 ^ (__ROR4__(v19, 22) + 4991 * __ROR4__(v19 + 1419157410, 27));
        v21 = v19 ^ (43881 * __ROR4__(v20 + 133239679, 9) - __ROR4__(v20, 30));
        v22 = v20 ^ (24670 * v21 - (v21 >> 13) - 123127970);
        v23 = v21 ^ (2033 * __ROR4__(v22 ^ 0xAB69, 26) - __ROR4__(v22, 30));
        v24 = v22 ^ (133239679 - (v23 ^ 0xAB69605E));
        v25 = v23 ^ (43881 * (v24 ^ 0x137F)) ^ __ROR4__(v24, 6);
        v26 = v24 ^ (__ROR4__(v25, 30) + 24670 * __ROR4__(v25 + 133239679, 15));
        v27 = v25 ^ (2033 * __ROR4__(v26 + 1419157410, 14) - __ROR4__(v26, 24));
        v28 = v26 ^ __ROR4__(v27, 10) ^ (4991 * __ROR4__(v27 ^ 0xAB69605E, 12));
        v29 = v27 ^ (v28 >> 10) ^ (43881 * (v28 ^ 0x7F1));
        v30 = v28 ^ (2033 * (__ROR4__(~v29, 5) + 24670));
        v31 = v30 ^ (((v29 ^ (v30 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v29 ^ (v30 - 2033) ^ 0xAB6967AF, 30));
        v32 = v29 ^ (v30 - 2033) ^ 0xAB69605E ^ (__ROR4__(v31, 25) + 43881 * __ROR4__(v31 - 133239679, 6));
        v33 = v31 ^ (24670 * (v32 ^ 0x137F) + __ROR4__(v32, 9));
        v34 = v32 ^ (__ROR4__(v33, 25) + 2033 * __ROR4__(v33 ^ 0xAB69, 27));
        v35 = v33 ^ v34 ^ 0xAC987321;
        v36 = v34 ^ (4991 * __ROR4__(v35, 3) - 219010071);
        v37 = v35 ^ (24670 * __ROR4__(v36 - 133239679, 1) - __ROR4__(v36, 6));
        v38 = v36 ^ (__ROR4__(v37, 18) + 2033 * __ROR4__(v37 - 1419157410, 29));
        v39 = v37 ^ (4991 * __ROR4__(v38 - 1419157410, 17) - __ROR4__(v38, 14));
        v40 = v38 ^ (v39 >> 3) ^ (43881 * (v39 ^ 0x605E));
        v41 = __ROR4__(v40, 30);
        v10 = v9 ^ v40;
        v9 = v18;
        v11 = v8 ^ v39 ^ v41 ^ (24670 * __ROR4__(v38 ^ (v39 >> 3) ^ (43881 * (v39 ^ 0x605E)) ^ 0x7F1137F, 28));
        v8 = v16;
        v7[3] = v11;
        v7[7] = v10;
        v7[2] = __ROR4__(v11, 8);
        v7[6] = __ROR4__(v10, 8);
        v7[1] = __ROR4__(v11, 16);
        v7[5] = __ROR4__(v10, 16);
        *v7 = __ROR4__(v11, 24);
        v7[4] = __ROR4__(v10, 24);
        v7 += 8;
        --v12;
      }
      while ( v12 );
      v42 = 0;
      v43 = 0;
      do
        v43 ^= v5[v42++];
      while ( v42 < 0x338 );
      if ( v43 != 64 )
      {
        MemoryFree(v5);
LABEL_14:
        for ( i = 0; i != 4; ++i )
        {
          v45 = (HMODULE)qword_18003DEB0[3 * i];
          if ( v45 )
            FreeLibrary(v45);
        }
        memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
        memcpy_0(off_18003D360, off_18002E370, 0x170u);
LABEL_47:
        _InterlockedExchange(&dword_18003E48C, 0);
        v59 = 0;
        Size = 0;
        v60 = 0;
        pcchLength = 0;
        v61 = 0;
        if ( NtCurrentPeb()->SessionId )
        {
          v62 = 0;
          v63 = off_18003D470[0]();
          if ( !v63 )
          {
LABEL_49:
            LastError = GetLastError();
            v65 = LastError < 0;
            if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
              v65 = LastError < 0;
            }
            if ( !v65 )
              LastError = -2147467259;
            goto LABEL_101;
          }
          v1315 = 0;
          v66 = 0;
          v1279 = 0;
          for ( j = 0; ; v1279 = j )
          {
            v68 = 0;
            if ( j )
              v68 = j;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, unsigned int *))off_18003D490[0])(
                   v63,
                   2,
                   v68,
                   v66,
                   &v1315) )
            {
              Size = (SIZE_T)j;
              LastError = 0;
              v59 = (const wchar_t *)j;
              goto LABEL_68;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( j )
              goto LABEL_63;
            j = MemoryAlloc(v1315);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1279);
            if ( !j )
            {
              LastError = -2147024882;
LABEL_68:
              v1279 = 0;
              goto LABEL_69;
            }
            v66 = v1315;
          }
          if ( !LastError )
          {
LABEL_63:
            LastError = -2147467259;
            goto LABEL_69;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_69:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1279);
          if ( LastError < 0 )
            goto LABEL_101;
          v69 = off_18003D488[0];
          CurrentThreadId = GetCurrentThreadId();
          v71 = ((__int64 (__fastcall *)(_QWORD))v69)(CurrentThreadId);
          if ( !v71 )
            goto LABEL_49;
          v1314 = 0;
          v72 = 0;
          v1279 = 0;
          for ( k = 0; ; v1279 = k )
          {
            v74 = 0;
            if ( k )
              v74 = k;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, unsigned int *))off_18003D490[0])(
                   v71,
                   2,
                   v74,
                   v72,
                   &v1314) )
            {
              pcchLength = (size_t)k;
              LastError = 0;
              v60 = (const wchar_t *)k;
              goto LABEL_85;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( k )
              goto LABEL_80;
            k = MemoryAlloc(v1314);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1279);
            if ( !k )
            {
              LastError = -2147024882;
LABEL_85:
              v1279 = 0;
              goto LABEL_86;
            }
            v72 = v1314;
          }
          if ( !LastError )
          {
LABEL_80:
            LastError = -2147467259;
            goto LABEL_86;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_86:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1279);
          if ( LastError < 0 )
          {
LABEL_101:
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Size);
            v77 = 0;
            if ( LastError >= 0 )
              v77 = v62;
            LODWORD(v1301) = v77;
            v78 = LocalAlloc(0x40u, 4u);
            SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1303, v78);
            lpMem = (LPVOID)v1303;
            if ( !v1303 )
            {
              v83 = -2147024882;
              v1265 = 0;
              goto LABEL_1571;
            }
            v1308 = 0;
            v79 = 0;
            *(_OWORD *)Src = 0;
            v1299 = 0;
            ProcessHeap = GetProcessHeap();
            v81 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
            LODWORD(v1280) = -805306345;
            v82 = v81;
            v83 = -1073741801;
            if ( !v81 )
            {
              v84 = 0;
              LODWORD(dwBytes) = -1073741801;
LABEL_136:
              v115 = Src[1];
              Src[0] = 0;
              if ( Src[1] )
              {
                v116 = GetProcessHeap();
                HeapFree(v116, 0, v115);
                Src[1] = 0;
              }
              if ( v79 )
              {
                v117 = GetProcessHeap();
                HeapFree(v117, 0, v79);
              }
              if ( v82 )
              {
                v118 = GetProcessHeap();
                HeapFree(v118, 0, v82);
              }
              if ( v84 )
              {
                v119 = GetProcessHeap();
                HeapFree(v119, 0, v84);
              }
              v120 = 0;
              if ( v83 >= 0 )
              {
                if ( !(_DWORD)v1301 )
                {
LABEL_1568:
                  v1265 = v1308;
                  v1321 = (unsigned int *)lpMem;
                  v1303 = 0;
                  goto LABEL_1571;
                }
                v1295 = 0;
                dword_18003DEA0 = v1301;
                ModuleFileNameW = GetModuleFileNameW(&_ImageBase, Filename, 0x104u);
                if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
                {
LABEL_1188:
                  SH<void *,SH_HANDLE>::Reset((CNgscbToken *)&v1295);
                  v1276 = 0;
                  *(_OWORD *)v1302 = 0;
                  v927 = 0;
                  v928 = 0;
                  v929 = GetProcessHeap();
                  v930 = HeapAlloc(v929, 8u, 0xA0u);
                  v931 = v930;
                  if ( !v930 )
                  {
                    v931 = 0;
LABEL_1560:
                    v1260 = (void *)v1302[1];
                    v1302[0] = 0;
                    if ( v1302[1] )
                    {
                      v1261 = GetProcessHeap();
                      HeapFree(v1261, 0, v1260);
                      v1302[1] = 0;
                    }
                    if ( v928 )
                    {
                      v1262 = GetProcessHeap();
                      HeapFree(v1262, 0, v928);
                    }
                    if ( v931 )
                    {
                      v1263 = GetProcessHeap();
                      HeapFree(v1263, 0, v931);
                    }
                    if ( v927 )
                    {
                      v1264 = GetProcessHeap();
                      HeapFree(v1264, 0, v927);
                    }
                    goto LABEL_1568;
                  }
                  *v930 = xmmword_18003DBE0;
                  v930[1] = xmmword_18003DBF0;
                  v930[2] = xmmword_18003DC00;
                  v930[3] = xmmword_18003DC10;
                  v930[4] = xmmword_18003DC20;
                  v930[5] = xmmword_18003DC30;
                  v930[6] = xmmword_18003DC40;
                  v930[7] = xmmword_18003DC50;
                  v930[8] = xmmword_18003DC60;
                  v930[9] = xmmword_18003DC70;
                  v932 = GetProcessHeap();
                  v933 = HeapAlloc(v932, 8u, 8u);
                  v934 = v933;
                  if ( v933 )
                  {
                    *v933 = qword_18003DB20;
                    v1295 = (LPVOID)__rdtsc();
                    v1272 = 0;
                    v1271 = 0;
                    if ( (int)RtlUIntAdd(4, 4, &v1271) < 0 )
                      goto LABEL_1558;
                    if ( (int)RtlUIntAdd(0, v1271, &v1272) < 0 )
                      goto LABEL_1558;
                    v1271 = v936;
                    if ( (int)RtlUIntAdd(v935, 160, &v1271) < 0 )
                      goto LABEL_1558;
                    v937 = RtlUIntAdd((unsigned int)v1272, v1271, &v1272);
                    if ( (v940 | v937) < 0 )
                      goto LABEL_1558;
                    v1271 = v939;
                    if ( (int)RtlUIntAdd(v938, 8, &v1271) < 0 )
                      goto LABEL_1558;
                    v941 = RtlUIntAdd((unsigned int)v1272, v1271, &v1272);
                    if ( (v944 | v941) < 0
                      || (v1271 = v943, (int)RtlUIntAdd(v942, 8, &v1271) < 0)
                      || (v945 = RtlUIntAdd((unsigned int)v1272, v1271, &v1272), (v946 | v945) < 0)
                      || (HIDWORD(v1302[0]) = v1272,
                          v947 = v1272,
                          v948 = GetProcessHeap(),
                          v949 = (const WCHAR *)HeapAlloc(v948, 8u, v947),
                          (v950 = (WCHAR *)v949) == 0) )
                    {
LABEL_1558:
                      v927 = v934;
                      goto LABEL_1559;
                    }
                    v1302[1] = (size_t)v949;
                    LODWORD(v1302[0]) = 0;
                    *(_QWORD *)((char *)&v1304 + 4) = 0;
                    lpModuleName = v949;
                    v927 = v934;
                    if ( (int)RtlULongLongAdd(v949, 4, (char *)&v1304 + 8) < 0
                      || (unsigned __int64)(v950 + 4) > v1302[1] + HIDWORD(v1302[0]) )
                    {
                      goto LABEL_1559;
                    }
                    v953 = (unsigned int *)*((_QWORD *)&v1304 + 1);
                    *(_DWORD *)v950 = v951;
                    v954 = v951;
                    *v953 = v951;
                    v955 = LODWORD(v1302[0]) + 1;
                    *(_QWORD *)((char *)&v1304 + 4) = 0;
                    ++LODWORD(v1302[0]);
                    if ( v931 )
                    {
                      if ( !v952 )
                        goto LABEL_1559;
                    }
                    else if ( v952 )
                    {
                      goto LABEL_1559;
                    }
                    v956 = (LPCWSTR)v1302[1];
                    if ( v1302[1] )
                    {
                      lpModuleName = (LPCWSTR)v1302[1];
                      for ( m = 0; m < v955; ++m )
                      {
                        v959 = *(unsigned int *)v956;
                        v1271 = 0;
                        if ( (int)RtlUIntAdd(4, v959, &v1271) < 0
                          || (int)RtlULongLongAdd(v960, v1271, &lpModuleName) < 0 )
                        {
                          goto LABEL_1559;
                        }
                        v956 = lpModuleName;
                      }
                      v954 = 4;
                      if ( (int)RtlULongLongAdd(v956, 4, (char *)&v1304 + 8) < 0 )
                        goto LABEL_1559;
                      v963 = v962;
                      if ( (unsigned __int64)v961 + v962 + 4 > v1302[1] + HIDWORD(v1302[0]) )
                        goto LABEL_1559;
                      *v961 = v962;
                      v957 = 0;
                      if ( v931 )
                      {
                        memcpy_0(*((void **)&v1304 + 1), v931, v963);
                        v957 = 0;
                      }
                    }
                    else
                    {
                      v1271 = 0;
                      if ( (int)RtlUIntAdd(v954, v952, &v1271) < 0
                        || (int)RtlUIntAdd(HIDWORD(v1302[0]), v1271, (char *)v1302 + 4) < 0 )
                      {
                        goto LABEL_1559;
                      }
                    }
                    v964 = LODWORD(v1302[0]) + 1;
                    *(_QWORD *)((char *)&v1304 + 4) = 0;
                    ++LODWORD(v1302[0]);
                    if ( v934 )
                    {
                      v965 = (LPCWSTR)v1302[1];
                      if ( v1302[1] )
                      {
                        lpModuleName = (LPCWSTR)v1302[1];
                        while ( v957 < v964 )
                        {
                          v967 = *(unsigned int *)v965;
                          v1271 = 0;
                          if ( (int)RtlUIntAdd(4, v967, &v1271) < 0
                            || (int)RtlULongLongAdd(v968, v1271, &lpModuleName) < 0 )
                          {
                            goto LABEL_1559;
                          }
                          v965 = lpModuleName;
                          v957 = v969 + 1;
                        }
                        if ( (int)RtlULongLongAdd(v965, 4, (char *)&v1304 + 8) < 0
                          || (unsigned __int64)(v970 + 3) > v1302[1] + HIDWORD(v1302[0]) )
                        {
                          goto LABEL_1559;
                        }
                        *v970 = 8;
                        memcpy_0(*((void **)&v1304 + 1), v934, 8u);
                        v966 = 0;
                      }
                      else
                      {
                        v1271 = v957;
                        if ( (int)RtlUIntAdd(v954, 8, &v1271) < 0
                          || (int)RtlUIntAdd(HIDWORD(v1302[0]), v1271, (char *)v1302 + 4) < 0 )
                        {
                          goto LABEL_1559;
                        }
                      }
                      v971 = (LPCWSTR)v1302[1];
                      v972 = LODWORD(v1302[0]) + 1;
                      *(_QWORD *)((char *)&v1304 + 4) = 0;
                      ++LODWORD(v1302[0]);
                      if ( v1302[1] )
                      {
                        lpModuleName = (LPCWSTR)v1302[1];
                        while ( v966 < v972 )
                        {
                          v975 = *(unsigned int *)v971;
                          v1271 = 0;
                          if ( (int)RtlUIntAdd(4, v975, &v1271) < 0
                            || (int)RtlULongLongAdd(v976, v1271, &lpModuleName) < 0 )
                          {
                            goto LABEL_1559;
                          }
                          v971 = lpModuleName;
                          v966 = v977 + 1;
                        }
                        v978 = RtlULongLongAdd(v971, 4, (char *)&v1304 + 8);
                        v974 = 0;
                        if ( v978 < 0 || (unsigned __int64)(v979 + 3) > v1302[1] + HIDWORD(v1302[0]) )
                          goto LABEL_1559;
                        v980 = (_QWORD *)*((_QWORD *)&v1304 + 1);
                        v981 = v1295;
                        *v979 = 8;
                        v973 = 4;
                        *v980 = v981;
                        ++LODWORD(v1302[0]);
                      }
                      else
                      {
                        v1271 = v966;
                        if ( (int)RtlUIntAdd(4, 8, &v1271) < 0
                          || (int)RtlUIntAdd(HIDWORD(v1302[0]), v1271, (char *)v1302 + 4) < 0 )
                        {
                          goto LABEL_1559;
                        }
                        ++LODWORD(v1302[0]);
                      }
                      v1271 = v974;
                      if ( (int)RtlUIntAdd(v973, v973, &v1271) >= 0 )
                      {
                        LODWORD(v1278) = v1271;
                        v1271 = v983;
                        if ( (int)RtlUIntAdd(v982, 8, &v1271) >= 0 && (int)RtlUIntAdd(v984, v1271, &v1278) >= 0 )
                        {
                          v986 = (int)v1278;
                          HIDWORD(dwBytes) = (_DWORD)v1278;
                          v1278 = v985;
                          LODWORD(v1298) = (_DWORD)v985;
                          v1295 = (LPVOID)__rdtsc();
                          v1306 = 8;
                          v987 = RtlUIntAdd(8, HIDWORD(v1302[0]), &v1306);
                          if ( v987 < 0 )
                          {
                            v1289 = v927;
                            v1275 = v931;
                          }
                          else
                          {
                            v991 = (v1306 + 7) & 0xFFFFFFF8;
                            if ( v991 < v1306 )
                              goto LABEL_1559;
                            v1306 = (v1306 + 7) & 0xFFFFFFF8;
                            v992 = v991;
                            v993 = GetProcessHeap();
                            v994 = (char *)HeapAlloc(v993, 8u, v992);
                            LODWORD(v990) = 0;
                            v995 = v994;
                            if ( !v994 )
                              goto LABEL_1543;
                            v1284 = (size_t)v994;
                            v1275 = v931;
                            v1289 = v927;
                            HIDWORD(dwBytes) = v986;
                            *(_DWORD *)v994 = v1302[0];
                            LODWORD(v1274) = RtlULongLongAdd(v994, 4, &v1284);
                            if ( (v1274 & 0x80000000) != 0LL
                              || (v997 = v1284,
                                  *(_DWORD *)v1284 = HIDWORD(v1302[0]),
                                  LODWORD(v1274) = RtlULongLongAdd(v997, v996, &v1284),
                                  (v1274 & 0x80000000) != 0LL) )
                            {
                              v1275 = v931;
                              v1289 = v927;
                              HIDWORD(dwBytes) = v986;
                              v998 = GetProcessHeap();
                              HeapFree(v998, 0, v995);
                              v988 = v1278;
                              v989 = (unsigned int)v1278;
                            }
                            else
                            {
                              *(_QWORD *)&v995[v1306 - 8] = v1295;
                              memcpy_0((void *)v1284, (const void *)v1302[1], HIDWORD(v1302[0]));
                              v989 = v1306;
                              v988 = v995;
                              v1278 = v995;
                            }
                            v987 = v1274;
                            v990 = 0;
                          }
                          v999 = v987 | 0x10000000;
                          v1297 = (SIZE_T)v990;
                          v1000 = v990;
                          v1288 = v990;
                          v1001 = v990;
                          v1291 = v990;
                          v1283 = v990;
                          if ( v999 < 0 )
                          {
                            v1115 = v990;
                            goto LABEL_1518;
                          }
                          if ( v988 )
                          {
                            Size = v989;
                            if ( !v989 || (v1284 = v989 + 8LL, (psz = (STRSAFE_PCNZWCH)MemoryAlloc(v1284)) == 0) )
                            {
                              v1230 = v1278;
                              v1115 = v1000;
                              LODWORD(v1280) = -805306367;
                              goto LABEL_1520;
                            }
                            v1002 = 0;
                            v1299 = 0;
                            v1003 = 0;
                            v1004 = Size;
                            v1273 = 0;
                            if ( Size )
                            {
                              do
                                v1002 ^= *((_BYTE *)v1278 + v1003++);
                              while ( v1003 < Size );
                              v1273 = v1002;
                            }
                            v1301 = 0xC81ECB17B1B54A58uLL;
                            lpModuleName = (LPCWSTR)v1278;
                            v1005 = (const WCHAR *)v1278;
                            pcchLength = (size_t)psz;
                            v1006 = Size & 7;
                            if ( (Size & 7) != 0 )
                            {
                              LODWORD(v1293) = 0;
                              LODWORD(v1292) = 0;
                              v1007 = 0;
                              v1008 = 0;
                              v1009 = 0;
                              do
                              {
                                v1010 = *(unsigned __int8 *)v1005;
                                v1005 = (const WCHAR *)((char *)v1005 + 1);
                                v1271 = 8 * v1007;
                                if ( v1007 >= 4 )
                                  v1008 |= v1010 << (56 - v1271);
                                else
                                  v1009 |= v1010 << (24 - v1271);
                                ++v1007;
                              }
                              while ( (int)v1007 < (int)v1006 );
                              v1002 = v1273;
                              LODWORD(v1293) = v1009;
                              v1000 = v1001;
                              LODWORD(v1292) = v1008;
                              lpModuleName = v1005;
                              v1289 = v927;
                              v1275 = v931;
                              LODWORD(v1277) = 0;
                              v1011 = v1008 ^ 0x42F6B18D;
                              v1012 = v1293 ^ 0xB17A307A;
                              v1013 = v1293 ^ 0xB17A307A;
                              v1014 = v1008 ^ 0x42F6B18D;
                              if ( (Size & 7) != 0 )
                              {
                                v1015 = (_BYTE *)pcchLength;
                                v1016 = (unsigned int)v1277;
                                do
                                {
                                  v1295 = v1015 + 1;
                                  if ( v1016 >= 4 )
                                  {
                                    v1014 = __ROR4__(v1014, 24);
                                    v1017 = v1014;
                                  }
                                  else
                                  {
                                    v1013 = __ROR4__(v1013, 24);
                                    v1017 = v1013;
                                  }
                                  *v1015 = v1017;
                                  ++v1016;
                                  v1015 = v1295;
                                }
                                while ( (int)v1016 < (int)v1006 );
                                pcchLength = (size_t)v1295;
                                v1001 = (unsigned int *)v1288;
                              }
                              if ( v1006 <= 4 )
                              {
                                v1018 = 0;
                                if ( v1006 < 4 )
                                  v1012 = v1012 >> (8 * (4 - v1006)) << (8 * (4 - v1006));
                              }
                              else
                              {
                                v1018 = v1011 >> (8 * (8 - v1006)) << (8 * (8 - v1006));
                              }
                            }
                            else
                            {
                              v1012 = 0;
                              LODWORD(v1293) = 0;
                              v1018 = -1;
                              LODWORD(v1292) = 0;
                            }
                            if ( v1004 >> 3 )
                            {
                              v1019 = lpModuleName;
                              v1020 = v1004 >> 3;
                              v1021 = (_BYTE *)pcchLength;
                              v1022 = v1293;
                              v1272 = 19032;
                              LODWORD(v1287) = WORD1(v1301);
                              v1303 = 0;
                              v1023 = HIDWORD(v1301);
                              LODWORD(v1277) = WORD2(v1301);
                              v1024 = WORD2(v1301);
                              LODWORD(v1274) = HIWORD(v1301);
                              v1025 = v1292;
                              do
                              {
                                v1026 = *((unsigned __int8 *)v1019 + 1);
                                v1027 = *(unsigned __int8 *)v1019;
                                v1028 = *((unsigned __int8 *)v1019 + 4);
                                v1019 += 4;
                                v1029 = *((unsigned __int8 *)v1019 - 5)
                                      | ((*((unsigned __int8 *)v1019 - 6) | ((v1026 | (v1027 << 8)) << 8)) << 8);
                                v1030 = *((unsigned __int8 *)v1019 - 1)
                                      | ((*((unsigned __int8 *)v1019 - 2)
                                        | ((*((unsigned __int8 *)v1019 - 3) | (v1028 << 8)) << 8)) << 8);
                                v1031 = v1018 ^ v1030;
                                v1032 = v1012 ^ v1029 ^ v1023 ^ ((v1018 ^ v1030) - v1272);
                                v1033 = v1031
                                      ^ (__ROR4__(v1032, 7) + WORD1(v1301) * __ROR4__(HIDWORD(v1301) ^ v1032, 15));
                                v1034 = v1032 ^ (v1024 * __ROR4__(v1033 - 1313519016, 9) - __ROR4__(v1033, 10));
                                v1035 = v1033 ^ (__ROR4__(v1034, 27) + HIWORD(v1301) * __ROR4__(v1024 ^ v1034, 28));
                                v1023 = HIDWORD(v1301);
                                v1036 = v1034 ^ (HIDWORD(v1301) - (v1035 ^ 0xB1B54A58));
                                v1037 = v1035 ^ (WORD1(v1301) * (v1036 - v1272) - (v1036 >> 6));
                                v1038 = v1036 ^ (v1272 * (v1024 ^ __ROR4__(v1037, 15)));
                                v1039 = v1037 ^ (v1024 * (v1274 + __ROR4__(~v1038, 3)));
                                v1040 = v1038 ^ (v1039 - v1272 - HIDWORD(v1301));
                                v1041 = v1039 ^ (v1287 * (v1274 ^ v1040)) ^ __ROR4__(v1040, 10);
                                v1042 = v1040 ^ __ROR4__(v1041, 3) ^ (v1024 * __ROR4__(v1272 ^ v1041, 26));
                                v1043 = v1041 ^ (v1272 * (__ROR4__(v1042, 15) - HIWORD(v1301)));
                                v1044 = v1042
                                      ^ (v1272 * (v1274 ^ v1043))
                                      ^ ((v1043 ^ (v1043 >> 14)) >> 1)
                                      ^ (v1272 * (((v1043 - v1024) >> 29) | (8 * (v1043 - v1024))));
                                v1045 = v1043 ^ (WORD1(v1301) * (v1044 - v1024) - (v1044 >> 13));
                                v1046 = v1044 ^ __ROR4__(v1045, 11) ^ (v1024 * __ROR4__(-1313519016 - v1045, 9));
                                v1047 = v1045 ^ (v1046 - HIWORD(v1301) + 1313519016);
                                v1048 = v1046 ^ (v1272 * (v1047 ^ WORD1(v1301)) - __ROR4__(v1047, 7));
                                v1049 = v1047
                                      ^ (WORD1(v1301) * __ROR4__(v1048 ^ HIWORD(v1301), 28) - __ROR4__(v1048, 16));
                                v1050 = v1048 ^ (__ROR4__(v1049, 4) + v1024 * __ROR4__(-1313519016 - v1049, 10));
                                v1051 = v1049 ^ __ROR4__(v1050, 9) ^ (HIWORD(v1301) * __ROR4__(v1050 + 1313519016, 4));
                                v1052 = v1050 ^ (v1272 * __ROR4__(v1051 ^ HIDWORD(v1301), 24) - __ROR4__(v1051, 30));
                                v1053 = v1051
                                      ^ (WORD1(v1301) * __ROR4__(HIDWORD(v1301) - v1052, 11) - __ROR4__(v1052, 12));
                                v1054 = v1052 ^ (v1053 >> 8) ^ (v1024 * (WORD1(v1301) ^ v1053));
                                v1012 = v1022 ^ v1054;
                                v1018 = v1025 ^ v1054 ^ HIDWORD(v1301) ^ v1053 ^ 0xB1B54A58;
                                v1021[3] = v1022 ^ v1054;
                                LOBYTE(v1038) = __ROR4__(v1022 ^ v1054, 8);
                                v1022 = v1029;
                                v1021[7] = v1018;
                                v1025 = v1030;
                                v1021[2] = v1038;
                                v1021[6] = __ROR4__(v1018, 8);
                                v1021[1] = __ROR4__(v1012, 16);
                                v1021[5] = __ROR4__(v1018, 16);
                                *v1021 = __ROR4__(v1012, 24);
                                v1021[4] = __ROR4__(v1018, 24);
                                v1021 += 8;
                                ++v1303;
                              }
                              while ( v1303 < v1020 );
                              v1001 = (unsigned int *)v1288;
                              v1002 = v1273;
                              v1000 = (unsigned int *)v1288;
                              v83 = dwBytes;
                              v931 = v1275;
                              v927 = v1289;
                              v1004 = Size;
                            }
                            *(_QWORD *)((char *)psz + v1004) = v1002;
                            v1055 = GetProcessHeap();
                            v1056 = HeapAlloc(v1055, 8u, 0x30u);
                            v1275 = v1056;
                            if ( !v1056 )
                            {
                              v1057 = v1278;
                              v1272 = -1073741801;
                              goto LABEL_1302;
                            }
                            v1058 = v1284;
                            *v1056 = v1284;
                            v1059 = GetProcessHeap();
                            v1060 = HeapAlloc(v1059, 8u, v1058);
                            v1057 = v1278;
                            if ( v1060 )
                            {
                              *((_QWORD *)v1275 + 1) = v1060;
                              memcpy_0(v1060, psz, (unsigned int)v1284);
                              *((_DWORD *)v1275 + 4) = 160;
                              v1061 = GetProcessHeap();
                              v1062 = HeapAlloc(v1061, 8u, 0xA0u);
                              v1063 = v1275;
                              if ( v1062 )
                              {
                                *((_QWORD *)v1275 + 3) = v1062;
                                *v1062 = xmmword_18003DB30;
                                v1062[1] = xmmword_18003DB40;
                                v1062[2] = xmmword_18003DB50;
                                v1062[3] = xmmword_18003DB60;
                                v1062[4] = xmmword_18003DB70;
                                v1062[5] = xmmword_18003DB80;
                                v1062[6] = xmmword_18003DB90;
                                v1062[7] = xmmword_18003DBA0;
                                v1062[8] = xmmword_18003DBB0;
                                v1062[9] = xmmword_18003DBC0;
                                v1063[8] = 8;
                                v1064 = GetProcessHeap();
                                v1065 = HeapAlloc(v1064, 8u, 8u);
                                if ( v1065 )
                                {
                                  v1071 = v1275;
                                  *((_QWORD *)v1275 + 5) = v1065;
                                  *v1065 = qword_18003DBD0;
                                  v1299 = v1071;
                                  v1272 = 0;
                                  v1278 = v1057;
                                  goto LABEL_1301;
                                }
                                v1063 = v1275;
                              }
                              v1275 = v1063;
                            }
                            v1066 = v1275;
                            v1272 = -1073741801;
                            v1278 = v1057;
                            v1295 = (LPVOID)*((_QWORD *)v1275 + 1);
                            if ( v1295 )
                            {
                              v1067 = GetProcessHeap();
                              HeapFree(v1067, 0, v1295);
                              v1066 = v1275;
                              *((_QWORD *)v1275 + 1) = 0;
                            }
                            v1295 = (LPVOID)*((_QWORD *)v1066 + 3);
                            if ( v1295 )
                            {
                              v1068 = GetProcessHeap();
                              HeapFree(v1068, 0, v1295);
                              v1066 = v1275;
                              *((_QWORD *)v1275 + 3) = 0;
                            }
                            v1295 = (LPVOID)*((_QWORD *)v1066 + 5);
                            if ( v1295 )
                            {
                              v1069 = GetProcessHeap();
                              HeapFree(v1069, 0, v1295);
                              *((_QWORD *)v1275 + 5) = 0;
                            }
                            v1070 = GetProcessHeap();
                            HeapFree(v1070, 0, v1275);
                            if ( v1272 < 0 )
                            {
LABEL_1302:
                              v1072 = GetProcessHeap();
                              HeapFree(v1072, 0, (LPVOID)psz);
                              v1073 = v1299;
                              LODWORD(v990) = 0;
                              if ( v1299 )
                              {
                                v1295 = (LPVOID)*((_QWORD *)v1299 + 1);
                                if ( v1295 )
                                {
                                  v1074 = GetProcessHeap();
                                  HeapFree(v1074, 0, v1295);
                                  v1073 = v1299;
                                  *((_QWORD *)v1299 + 1) = 0;
                                }
                                v1295 = (LPVOID)*((_QWORD *)v1073 + 3);
                                if ( v1295 )
                                {
                                  v1075 = GetProcessHeap();
                                  HeapFree(v1075, 0, v1295);
                                  v1073 = v1299;
                                  *((_QWORD *)v1299 + 3) = 0;
                                }
                                v1295 = (LPVOID)*((_QWORD *)v1073 + 5);
                                if ( v1295 )
                                {
                                  v1076 = GetProcessHeap();
                                  HeapFree(v1076, 0, v1295);
                                  *((_QWORD *)v1299 + 5) = 0;
                                }
                                v1077 = GetProcessHeap();
                                HeapFree(v1077, 0, v1299);
                                LODWORD(v990) = 0;
                              }
                              v1078 = v1272 | 0x10000000;
                              if ( v1272 < 0 )
                              {
                                v1278 = v1057;
                                goto LABEL_1335;
                              }
                              v1079 = *v1000;
                              v1271 = 0;
                              LODWORD(v1280) = 4;
                              v1272 = RtlUIntAdd(4, v1079, &v1280);
                              if ( v1272 < 0 )
                                goto LABEL_1329;
                              v1272 = RtlUIntAdd((unsigned int)v1280, v1080, &v1280);
                              if ( v1272 < 0
                                || (v1081 = v1000[4],
                                    lpModuleName = (LPCWSTR)(v1000 + 4),
                                    v1272 = RtlUIntAdd((unsigned int)v1280, v1081, &v1280),
                                    v1272 < 0)
                                || (v1272 = RtlUIntAdd((unsigned int)v1280, v1082, &v1280), v1272 < 0)
                                || (v1083 = v1000[8],
                                    pcchLength = (size_t)(v1000 + 8),
                                    v1272 = RtlUIntAdd((unsigned int)v1280, v1083, &v1280),
                                    v1272 < 0) )
                              {
LABEL_1329:
                                v1278 = v1057;
                              }
                              else
                              {
                                v1285 = v1000;
                                v1084 = v1280;
                                v1085 = GetProcessHeap();
                                v1086 = HeapAlloc(v1085, 8u, v1084);
                                v1000 = (unsigned int *)v1285;
                                LODWORD(v990) = 0;
                                v1289 = v1086;
                                if ( !v1086 )
                                {
LABEL_1317:
                                  LODWORD(v1280) = -805306345;
LABEL_1378:
                                  v1115 = v1283;
                                  goto LABEL_1519;
                                }
                                *v1086 = *(_DWORD *)v1285;
                                v1278 = v1057;
                                v1275 = v1086;
                                v1272 = RtlULongLongAdd(v1086, 4, &v1275);
                                if ( v1272 < 0 )
                                {
                                  HIDWORD(dwBytes) = v1088;
                                  v1289 = v1087;
                                }
                                else
                                {
                                  memcpy_0(v1275, *((const void **)v1000 + 1), *v1000);
                                  v1272 = RtlULongLongAdd(v1275, *v1000, &v1275);
                                  if ( v1272 >= 0 )
                                  {
                                    v1089 = v1275;
                                    *(_DWORD *)v1275 = *(_DWORD *)lpModuleName;
                                    v1272 = RtlULongLongAdd(v1089, 4, &v1275);
                                    if ( v1272 >= 0 )
                                    {
                                      memcpy_0(v1275, *((const void **)v1000 + 3), *v1090);
                                      v1272 = RtlULongLongAdd(v1275, *(unsigned int *)lpModuleName, &v1275);
                                      if ( v1272 >= 0 )
                                      {
                                        v1091 = v1275;
                                        *(_DWORD *)v1275 = *(_DWORD *)pcchLength;
                                        v1272 = RtlULongLongAdd(v1091, 4, &v1275);
                                        if ( v1272 >= 0 )
                                        {
                                          memcpy_0(v1275, *((const void **)v1000 + 5), *v1092);
                                          v1093 = RtlULongLongAdd(v1275, *(unsigned int *)pcchLength, &v1275);
                                          LODWORD(v990) = 0;
                                          v1272 = v1093;
                                          if ( v1093 >= 0 )
                                          {
                                            v1297 = (SIZE_T)v1289;
                                            v1271 = v1280;
LABEL_1331:
                                            v1078 = v1093 | 0x10000000;
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1312 = 8;
                                            v1095 = RtlUIntAdd(8, HIDWORD(dwBytes), &v1312);
                                            v1078 = v1096 | v1095;
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1097 = (v1312 + 7) & 0xFFFFFFF8;
                                            if ( (unsigned int)v1097 < v1312 )
                                            {
                                              v1078 = -1073741675;
LABEL_1335:
                                              LODWORD(v1280) = v1078;
                                              goto LABEL_1378;
                                            }
                                            v1317 = (v1312 + 7) & 0xFFFFFFF8;
                                            v1078 = RtlUIntAdd(v1097, 8, &v1317);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1098 = (_DWORD *)v1302[1];
                                            v1275 = v931;
                                            v1289 = v927;
                                            v1278 = v1057;
                                            v1285 = v1000;
                                            LODWORD(v1288) = (_DWORD)v990;
                                            if ( !v1302[1] )
                                              goto LABEL_1338;
                                            v1285 = v1000;
                                            v1278 = v1057;
                                            v1289 = v927;
                                            v1275 = v931;
                                            if ( LODWORD(v1302[0]) <= 1 )
                                              goto LABEL_1338;
                                            v1284 = v1302[1];
                                            for ( n = (int)v990; !n; n = v1101 + 1 )
                                            {
                                              v1078 = RtlULongLongAdd(v1098, 4, &v1284);
                                              if ( v1078 < 0 )
                                              {
LABEL_1361:
                                                LODWORD(v990) = 0;
                                                goto LABEL_1335;
                                              }
                                              v1078 = RtlULongLongAdd(v1284, v1100, &v1284);
                                              LODWORD(v990) = 0;
                                              if ( v1078 < 0 )
                                                goto LABEL_1335;
                                              v1098 = (_DWORD *)v1284;
                                            }
                                            LODWORD(v1277) = *v1098;
                                            v1078 = RtlULongLongAdd(v1098, 4, &v1284);
                                            LODWORD(v990) = 0;
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1102 = v1302[1];
                                            if ( !v1302[1] || LODWORD(v1302[0]) <= 2 )
                                            {
LABEL_1338:
                                              v1078 = -1073741811;
                                              goto LABEL_1335;
                                            }
                                            v1284 = v1302[1];
                                            for ( ii = 0; ii < 2; ii = v1105 + 1 )
                                            {
                                              v1078 = RtlULongLongAdd(v1102, 4, &v1284);
                                              if ( v1078 < 0 )
                                                goto LABEL_1361;
                                              v1078 = RtlULongLongAdd(v1284, v1104, &v1284);
                                              LODWORD(v990) = 0;
                                              if ( v1078 < 0 )
                                                goto LABEL_1335;
                                              v1102 = v1284;
                                            }
                                            v1078 = RtlULongLongAdd(v1102, 4, &v1284);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            LODWORD(v1288) = (_DWORD)v990;
                                            v1272 = 4;
                                            v1078 = RtlUIntAdd(4, v1317, &v1272);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1078 = RtlUIntAdd((unsigned int)v1272, v1106, &v1272);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1078 = RtlUIntAdd((unsigned int)v1272, (unsigned int)v1277, &v1272);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1078 = RtlUIntAdd((unsigned int)v1272, 4, &v1272);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            v1078 = RtlUIntAdd((unsigned int)v1272, v1107, &v1272);
                                            if ( v1078 < 0 )
                                              goto LABEL_1335;
                                            LODWORD(v1288) = v1272;
                                            if ( (unsigned int)v1272 > 0x400000 )
                                            {
                                              v1078 = -2147418113;
                                              goto LABEL_1335;
                                            }
                                            v1108 = v1272;
                                            v1109 = GetProcessHeap();
                                            v1110 = (unsigned int *)HeapAlloc(v1109, 8u, v1108);
                                            LODWORD(v990) = 0;
                                            v1001 = v1110;
                                            if ( !v1110 )
                                            {
                                              LODWORD(v1280) = -805306345;
                                              v1001 = 0;
LABEL_1377:
                                              v1000 = (unsigned int *)v1285;
                                              goto LABEL_1378;
                                            }
                                            hModule = 0;
                                            v1326 = 0;
                                            v1327 = 0;
                                            if ( !v1297 )
                                            {
                                              LODWORD(v1280) = -2147024809;
                                              goto LABEL_1377;
                                            }
                                            LODWORD(v1327) = v1271;
                                            *(_QWORD *)&v1326 = v1297;
                                            *(_QWORD *)((char *)&v1327 + 4) = (unsigned int)v1288;
                                            *((_QWORD *)&v1326 + 1) = v1110;
                                            if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                              && (ProcAddress = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                            {
                                              v1111 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                        134,
                                                        &v1326)
                                                    | 0x10000000;
                                              if ( v1111 >= 0 )
                                              {
                                                v1114 = DWORD1(v1327);
                                                LODWORD(v990) = 0;
                                                goto LABEL_1381;
                                              }
                                              LODWORD(v990) = 0;
                                            }
                                            else
                                            {
                                              v1111 = GetLastError();
                                              LODWORD(v990) = 0;
                                              v1112 = v1111 < 0;
                                              if ( v1111 > 0 )
                                              {
                                                v1111 = (unsigned __int16)v1111 | 0x80070000;
                                                v1112 = v1111 < 0;
                                              }
                                              if ( !v1112 )
                                              {
                                                LODWORD(v1280) = -2147467259;
                                                goto LABEL_1377;
                                              }
                                            }
                                            if ( v1111 == -805306333 )
                                            {
                                              LODWORD(v1280) = -2147024774;
                                              goto LABEL_1377;
                                            }
                                            if ( v1111 < 0 )
                                            {
                                              LODWORD(v1280) = v1111;
                                              goto LABEL_1377;
                                            }
                                            v1114 = (unsigned int)v1288;
LABEL_1381:
                                            HIDWORD(dwBytes) = 0;
                                            v1288 = v1001;
                                            if ( v1114 < 4 )
                                            {
LABEL_1382:
                                              LODWORD(v1280) = -805306306;
                                              goto LABEL_1377;
                                            }
                                            v1116 = (const WCHAR *)*v1001;
                                            LODWORD(v1277) = *v1001;
                                            v1117 = RtlULongLongAdd(v1001, 4, &v1288);
                                            if ( v1117 >= 0 )
                                            {
                                              v1117 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                              if ( v1117 >= 0 )
                                              {
                                                if ( v1118 - HIDWORD(dwBytes) < (unsigned int)v1116 )
                                                  goto LABEL_1382;
                                                pcchLength = (size_t)v1288;
                                                lpModuleName = v1116;
                                                v1117 = RtlULongLongAdd(v1288, (unsigned int)v1116, &v1288);
                                                if ( v1117 >= 0 )
                                                {
                                                  v1117 = RtlUIntAdd(
                                                            HIDWORD(dwBytes),
                                                            (unsigned int)v1116,
                                                            (char *)&dwBytes + 4);
                                                  if ( v1117 >= 0 )
                                                  {
                                                    if ( (unsigned int)(v1119 - HIDWORD(dwBytes)) < 4 )
                                                      goto LABEL_1382;
                                                    LODWORD(v1287) = *(_DWORD *)v1288;
                                                    v1117 = RtlULongLongAdd(v1288, 4, &v1288);
                                                    if ( v1117 >= 0 )
                                                    {
                                                      v1117 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                      if ( v1117 >= 0 )
                                                      {
                                                        if ( v1120 - HIDWORD(dwBytes) < (unsigned int)v1121 )
                                                        {
LABEL_1392:
                                                          v1000 = (unsigned int *)v1285;
                                                          LODWORD(v990) = 0;
                                                          v1115 = v1283;
                                                          LODWORD(v1280) = -805306306;
                                                          goto LABEL_1519;
                                                        }
                                                        psz = (STRSAFE_PCNZWCH)v1288;
                                                        Size = v1121;
                                                        v1117 = RtlULongLongAdd(v1288, v1121, &v1288);
                                                        if ( v1117 >= 0 )
                                                        {
                                                          v1117 = RtlUIntAdd(
                                                                    HIDWORD(dwBytes),
                                                                    v1122,
                                                                    (char *)&dwBytes + 4);
                                                          if ( v1117 >= 0 )
                                                          {
                                                            if ( (unsigned int)(v1123 - HIDWORD(dwBytes)) < 4 )
                                                              goto LABEL_1392;
                                                            v1271 = *(_DWORD *)v1288;
                                                            v1117 = RtlULongLongAdd(v1288, 4, &v1288);
                                                            if ( v1117 >= 0 )
                                                            {
                                                              v1117 = RtlUIntAdd(
                                                                        HIDWORD(dwBytes),
                                                                        4,
                                                                        (char *)&dwBytes + 4);
                                                              if ( v1117 >= 0 )
                                                              {
                                                                if ( v1124 - HIDWORD(dwBytes) < v1125 )
                                                                  goto LABEL_1392;
                                                                v1117 = RtlUIntAdd(
                                                                          HIDWORD(dwBytes),
                                                                          v1125,
                                                                          (char *)&dwBytes + 4);
                                                                if ( v1117 >= 0 )
                                                                {
                                                                  if ( v1126 != HIDWORD(dwBytes)
                                                                    || (unsigned int)(v1127 + v1128 + (_DWORD)v1116)
                                                                     + 12LL != v1126 )
                                                                  {
                                                                    goto LABEL_1392;
                                                                  }
                                                                  v1129 = GetProcessHeap();
                                                                  v1130 = HeapAlloc(v1129, 8u, 0x30u);
                                                                  v1000 = (unsigned int *)v1285;
                                                                  LODWORD(v990) = 0;
                                                                  v1274 = (SIZE_T)v1130;
                                                                  v1131 = (SIZE_T)v1130;
                                                                  if ( !v1130 )
                                                                  {
                                                                    v1291 = 0;
                                                                    goto LABEL_1317;
                                                                  }
                                                                  v1275 = v931;
                                                                  v1289 = v927;
                                                                  v1278 = v1057;
                                                                  v1279 = 0;
                                                                  if ( pcchLength )
                                                                  {
                                                                    *(_DWORD *)v1130 = (_DWORD)v1277;
                                                                    v1132 = GetProcessHeap();
                                                                    v1133 = HeapAlloc(v1132, 8u, (SIZE_T)lpModuleName);
                                                                    v1134 = v1274;
                                                                    if ( !v1133 )
                                                                    {
LABEL_1415:
                                                                      v1140 = *(void **)(v1134 + 8);
                                                                      v1272 = -1073741801;
                                                                      v1288 = v1001;
                                                                      v1295 = v1140;
                                                                      if ( v1140 )
                                                                      {
                                                                        v1141 = GetProcessHeap();
                                                                        HeapFree(v1141, 0, v1295);
                                                                        v1134 = v1274;
                                                                        *(_QWORD *)(v1274 + 8) = 0;
                                                                      }
                                                                      v1295 = *(LPVOID *)(v1134 + 24);
                                                                      if ( v1295 )
                                                                      {
                                                                        v1142 = GetProcessHeap();
                                                                        HeapFree(v1142, 0, v1295);
                                                                        v1134 = v1274;
                                                                        *(_QWORD *)(v1274 + 24) = 0;
                                                                      }
                                                                      v1295 = *(LPVOID *)(v1134 + 40);
                                                                      if ( v1295 )
                                                                      {
                                                                        v1143 = GetProcessHeap();
                                                                        HeapFree(v1143, 0, v1295);
                                                                        *(_QWORD *)(v1274 + 40) = 0;
                                                                      }
                                                                      v1144 = GetProcessHeap();
                                                                      HeapFree(v1144, 0, (LPVOID)v1274);
                                                                      v1145 = (LPVOID *)v1279;
                                                                      LODWORD(v990) = 0;
                                                                      goto LABEL_1425;
                                                                    }
                                                                    *(_QWORD *)(v1274 + 8) = v1133;
                                                                    v1272 = 0;
                                                                    memcpy_0(
                                                                      v1133,
                                                                      (const void *)pcchLength,
                                                                      (size_t)lpModuleName);
                                                                    v1131 = v1274;
                                                                    LODWORD(v990) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)v1130 = 0;
                                                                    v1130[1] = 0;
                                                                    v1272 = 0;
                                                                  }
                                                                  if ( psz )
                                                                  {
                                                                    *(_DWORD *)(v1131 + 16) = v1287;
                                                                    v1135 = GetProcessHeap();
                                                                    v1136 = HeapAlloc(v1135, 8u, Size);
                                                                    v1134 = v1274;
                                                                    if ( !v1136 )
                                                                    {
LABEL_1414:
                                                                      v1275 = v931;
                                                                      v1289 = v927;
                                                                      v1278 = v1057;
                                                                      v1285 = v1000;
                                                                      v1274 = v1134;
                                                                      goto LABEL_1415;
                                                                    }
                                                                    *(_QWORD *)(v1274 + 24) = v1136;
                                                                    v1272 = 0;
                                                                    memcpy_0(v1136, psz, Size);
                                                                    v1131 = v1274;
                                                                    LODWORD(v990) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v1131 + 16) = 0;
                                                                    *(_QWORD *)(v1131 + 24) = 0;
                                                                  }
                                                                  if ( v1288 )
                                                                  {
                                                                    v1137 = (const WCHAR *)v1271;
                                                                    *(_DWORD *)(v1131 + 32) = v1271;
                                                                    lpModuleName = v1137;
                                                                    v1138 = GetProcessHeap();
                                                                    v1139 = HeapAlloc(v1138, 8u, (SIZE_T)lpModuleName);
                                                                    v1134 = v1274;
                                                                    if ( !v1139 )
                                                                      goto LABEL_1414;
                                                                    *(_QWORD *)(v1274 + 40) = v1139;
                                                                    v1272 = 0;
                                                                    memcpy_0(v1139, v1288, (size_t)lpModuleName);
                                                                    v1131 = v1274;
                                                                    LODWORD(v990) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v1131 + 32) = 0;
                                                                    *(_QWORD *)(v1131 + 40) = 0;
                                                                  }
                                                                  v1145 = (LPVOID *)v1131;
                                                                  v1279 = (LPVOID)v1131;
                                                                  v1288 = v1001;
                                                                  v1285 = v1000;
                                                                  v1278 = v1057;
                                                                  v1289 = v927;
                                                                  v1275 = v931;
LABEL_1425:
                                                                  v1117 = v1272;
                                                                  if ( v1272 < 0 )
                                                                  {
                                                                    v1146 = 0;
                                                                    v1291 = 0;
                                                                    if ( v1145 )
                                                                    {
                                                                      v1295 = v1145[1];
                                                                      if ( v1295 )
                                                                      {
                                                                        v1147 = GetProcessHeap();
                                                                        HeapFree(v1147, 0, v1295);
                                                                        v1145 = (LPVOID *)v1279;
                                                                        *((_QWORD *)v1279 + 1) = 0;
                                                                      }
                                                                      v1295 = v1145[3];
                                                                      if ( v1295 )
                                                                      {
                                                                        v1148 = GetProcessHeap();
                                                                        HeapFree(v1148, 0, v1295);
                                                                        v1145 = (LPVOID *)v1279;
                                                                        *((_QWORD *)v1279 + 3) = 0;
                                                                      }
                                                                      v1295 = v1145[5];
                                                                      if ( v1295 )
                                                                      {
                                                                        v1149 = GetProcessHeap();
                                                                        HeapFree(v1149, 0, v1295);
                                                                        *((_QWORD *)v1279 + 5) = 0;
                                                                      }
                                                                      v1150 = GetProcessHeap();
                                                                      HeapFree(v1150, 0, v1279);
                                                                      v1117 = v1272;
                                                                      LODWORD(v990) = 0;
                                                                      v1146 = 0;
                                                                      v1291 = 0;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v1146 = (unsigned int *)v1145;
                                                                    v1291 = v1145;
                                                                  }
LABEL_1437:
                                                                  LODWORD(v1280) = v1117 | 0x10000000;
                                                                  if ( v1117 < 0 )
                                                                    goto LABEL_1378;
                                                                  if ( !v1146
                                                                    || (psz = (STRSAFE_PCNZWCH)*((_QWORD *)v1146 + 1)) == 0
                                                                    || *v1146 == (_DWORD)v990 )
                                                                  {
                                                                    v1115 = v1283;
                                                                    LODWORD(v1280) = -805306355;
LABEL_1470:
                                                                    v1000 = (unsigned int *)v1285;
                                                                    goto LABEL_1519;
                                                                  }
                                                                  v1284 = *v1146 - 8LL;
                                                                  v1151 = MemoryAlloc(v1284);
                                                                  LODWORD(v990) = 0;
                                                                  v1283 = v1151;
                                                                  v1152 = v1151;
                                                                  if ( !v1151 )
                                                                  {
LABEL_1469:
                                                                    LODWORD(v1280) = -805306367;
                                                                    v1115 = 0;
                                                                    goto LABEL_1470;
                                                                  }
                                                                  v1153 = v1284;
                                                                  v1154 = 0;
                                                                  v1155 = psz;
                                                                  v1273 = 0;
                                                                  lpModuleName = (LPCWSTR)(v1284 & 7);
                                                                  v1287 = 0x7F1137FAB69605ELL;
                                                                  pcchLength = (size_t)psz;
                                                                  Size = (SIZE_T)v1152;
                                                                  if ( (v1284 & 7) != 0 )
                                                                  {
                                                                    v1300 = 0;
                                                                    LODWORD(v1292) = 0;
                                                                    LODWORD(v1277) = 0;
                                                                    v1156 = 0;
                                                                    v1157 = 0;
                                                                    v1158 = 0;
                                                                    do
                                                                    {
                                                                      v1159 = *(unsigned __int8 *)v1155;
                                                                      v1155 = (STRSAFE_PCNZWCH)((char *)v1155 + 1);
                                                                      v1272 = v1159;
                                                                      v1271 = 8 * v1156;
                                                                      if ( (unsigned int)v1156 >= 4 )
                                                                      {
                                                                        v1272 <<= 56 - v1271;
                                                                        v1158 |= v1272;
                                                                      }
                                                                      else
                                                                      {
                                                                        v1272 <<= 24 - v1271;
                                                                        v1157 |= v1272;
                                                                      }
                                                                      ++v1156;
                                                                    }
                                                                    while ( v1156 < (int)lpModuleName );
                                                                    v83 = dwBytes;
                                                                    v1160 = v1152;
                                                                    LODWORD(v1292) = v1157;
                                                                    v1161 = v1157;
                                                                    v1154 = v1273;
                                                                    v1300 = v1158;
                                                                    v1153 = v1284;
                                                                    v1162 = (unsigned int)lpModuleName;
                                                                    pcchLength = (size_t)v1155;
                                                                    v1288 = v1001;
                                                                    v1285 = v1000;
                                                                    v1278 = v1057;
                                                                    v1289 = v927;
                                                                    v1275 = v931;
                                                                    v1163 = v1161 ^ 0x92F65A5;
                                                                    LODWORD(v1277) = 0;
                                                                    v1164 = v1300 ^ 0x699A899C;
                                                                    v1165 = v1163;
                                                                    if ( (_DWORD)lpModuleName )
                                                                    {
                                                                      v1166 = (unsigned int)v1277;
                                                                      v1167 = v1300 ^ 0x699A899C;
                                                                      do
                                                                      {
                                                                        v1295 = v1160 + 1;
                                                                        if ( v1166 >= 4 )
                                                                        {
                                                                          v1167 = __ROR4__(v1167, 24);
                                                                          v1168 = v1167;
                                                                        }
                                                                        else
                                                                        {
                                                                          v1165 = __ROR4__(v1165, 24);
                                                                          v1168 = v1165;
                                                                        }
                                                                        *v1160 = v1168;
                                                                        ++v1166;
                                                                        v1160 = v1295;
                                                                      }
                                                                      while ( (int)v1166 < (int)v1162 );
                                                                      v1154 = v1273;
                                                                      v1153 = v1284;
                                                                      Size = (SIZE_T)v1295;
                                                                      v1152 = v1283;
                                                                    }
                                                                    if ( v1162 <= 4 )
                                                                    {
                                                                      v1169 = 0;
                                                                      if ( v1162 < 4 )
                                                                        v1163 = v1163 >> (8 * (4 - v1162)) << (8 * (4 - v1162));
                                                                    }
                                                                    else
                                                                    {
                                                                      v1169 = v1164 >> (8 * (8 - v1162)) << (8 * (8 - v1162));
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    LODWORD(v1292) = 0;
                                                                    v1169 = 0;
                                                                    v1163 = 0;
                                                                  }
                                                                  if ( v1153 >> 3 )
                                                                  {
                                                                    v1170 = HIDWORD(v1287);
                                                                    v1171 = v1153 >> 3;
                                                                    v1172 = (_BYTE *)Size;
                                                                    v1173 = v1292;
                                                                    v1174 = WORD2(v1287);
                                                                    v1272 = 24670;
                                                                    v1175 = (unsigned __int8 *)pcchLength;
                                                                    v1271 = WORD2(v1287);
                                                                    lpModuleName = 0;
                                                                    do
                                                                    {
                                                                      v1176 = *v1175;
                                                                      v1177 = v1175[1];
                                                                      v1178 = v1175[4];
                                                                      v1175 += 8;
                                                                      v1179 = *(v1175 - 5)
                                                                            | ((*(v1175 - 6)
                                                                              | (((v1176 << 8) | v1177) << 8)) << 8);
                                                                      v1180 = v1163 ^ v1179;
                                                                      v1181 = *(v1175 - 1)
                                                                            | ((*(v1175 - 2)
                                                                              | ((*(v1175 - 3) | (v1178 << 8)) << 8)) << 8);
                                                                      v1182 = v1170
                                                                            ^ v1163
                                                                            ^ v1179
                                                                            ^ v1169
                                                                            ^ v1181
                                                                            ^ 0xAB69605E;
                                                                      v1183 = v1180
                                                                            ^ (__ROR4__(v1182, 22)
                                                                             + v1174 * __ROR4__(v1182 + 1419157410, 27));
                                                                      v1184 = v1182
                                                                            ^ (WORD1(v1287) * __ROR4__(v1170 + v1183, 9)
                                                                             - __ROR4__(v1183, 30));
                                                                      v1185 = v1183
                                                                            ^ (v1272 * (v1184 - v1174) - (v1184 >> 13));
                                                                      v1186 = v1184
                                                                            ^ (HIWORD(v1287)
                                                                             * __ROR4__(v1185 ^ WORD1(v1287), 26)
                                                                             - __ROR4__(v1185, 30));
                                                                      v1187 = v1185 ^ (v1170 - (v1186 ^ 0xAB69605E));
                                                                      v1188 = v1186
                                                                            ^ (WORD1(v1287) * (v1174 ^ v1187))
                                                                            ^ __ROR4__(v1187, 6);
                                                                      v1189 = v1187
                                                                            ^ (__ROR4__(v1188, 30)
                                                                             + v1272 * __ROR4__(v1170 + v1188, 15));
                                                                      v1190 = v1188
                                                                            ^ (HIWORD(v1287)
                                                                             * __ROR4__(v1189 + 1419157410, 14)
                                                                             - __ROR4__(v1189, 24));
                                                                      v1191 = v1189
                                                                            ^ __ROR4__(v1190, 10)
                                                                            ^ (v1271 * __ROR4__(v1190 ^ 0xAB69605E, 12));
                                                                      v1192 = v1190
                                                                            ^ (v1191 >> 10)
                                                                            ^ (WORD1(v1287) * (HIWORD(v1287) ^ v1191));
                                                                      v1193 = v1191
                                                                            ^ (HIWORD(v1287)
                                                                             * (v1272 + __ROR4__(~v1192, 5)));
                                                                      v1194 = v1192
                                                                            ^ (v1193 - HIWORD(v1287))
                                                                            ^ 0xAB69605E;
                                                                      v1174 = v1271;
                                                                      v1195 = v1193
                                                                            ^ ((v1194 >> 2)
                                                                             + v1271
                                                                             * __ROR4__(HIWORD(v1287) ^ v1194, 30));
                                                                      v1196 = v1194
                                                                            ^ (__ROR4__(v1195, 25)
                                                                             + WORD1(v1287) * __ROR4__(v1195 - v1170, 6));
                                                                      v1197 = v1195
                                                                            ^ (v1272 * (v1271 ^ v1196)
                                                                             + __ROR4__(v1196, 9));
                                                                      v1198 = v1196
                                                                            ^ (__ROR4__(v1197, 25)
                                                                             + HIWORD(v1287)
                                                                             * __ROR4__(v1197 ^ WORD1(v1287), 27));
                                                                      v1199 = v1197 ^ v1198 ^ v1170 ^ 0xAB69605E;
                                                                      v1200 = v1198
                                                                            ^ (v1271
                                                                             * (__ROR4__(v1199, 3) - WORD1(v1287)));
                                                                      v1201 = v1199
                                                                            ^ (v1272 * __ROR4__(v1200 - v1170, 1)
                                                                             - __ROR4__(v1200, 6));
                                                                      v1202 = v1200
                                                                            ^ (__ROR4__(v1201, 18)
                                                                             + HIWORD(v1287)
                                                                             * __ROR4__(v1201 - 1419157410, 29));
                                                                      v1203 = v1201
                                                                            ^ (v1271 * __ROR4__(v1202 - 1419157410, 17)
                                                                             - __ROR4__(v1202, 14));
                                                                      v1204 = v1300;
                                                                      v1300 = v1181;
                                                                      v1205 = v1202
                                                                            ^ (v1203 >> 3)
                                                                            ^ (WORD1(v1287) * (v1203 ^ v1272));
                                                                      v1169 = v1205 ^ v1204;
                                                                      v1206 = v1173
                                                                            ^ __ROR4__(v1205, 30)
                                                                            ^ (v1272 * __ROR4__(v1205 ^ v1170, 28));
                                                                      v1173 = v1179;
                                                                      v1163 = v1203 ^ v1206;
                                                                      v1172[3] = v1163;
                                                                      v1172[7] = v1169;
                                                                      v1172[2] = __ROR4__(v1163, 8);
                                                                      v1172[6] = __ROR4__(v1169, 8);
                                                                      v1172[1] = __ROR4__(v1163, 16);
                                                                      v1172[5] = __ROR4__(v1169, 16);
                                                                      *v1172 = __ROR4__(v1163, 24);
                                                                      v1172[4] = __ROR4__(v1169, 24);
                                                                      v1172 += 8;
                                                                      lpModuleName = (LPCWSTR)((char *)lpModuleName + 1);
                                                                    }
                                                                    while ( (unsigned __int64)lpModuleName < v1171 );
                                                                    v1154 = v1273;
                                                                    v83 = dwBytes;
                                                                    v931 = v1275;
                                                                    v927 = v1289;
                                                                    v1001 = (unsigned int *)v1288;
                                                                    v1057 = v1278;
                                                                    v1152 = v1283;
                                                                    v1153 = v1284;
                                                                  }
                                                                  LODWORD(v990) = 0;
                                                                  for ( jj = 0; jj < v1153; ++jj )
                                                                    v1154 ^= v1152[jj];
                                                                  if ( v1154 != *(_QWORD *)((char *)psz + v1153) )
                                                                  {
                                                                    MemoryFree(v1152);
                                                                    LODWORD(v990) = 0;
                                                                    goto LABEL_1469;
                                                                  }
                                                                  v1208 = v1291;
                                                                  v1000 = (unsigned int *)v1285;
                                                                  v1278 = v1057;
                                                                  v1300 = 0;
                                                                  v1284 = (size_t)v1152;
                                                                  if ( (unsigned int)v1153 < 4 )
                                                                  {
LABEL_1472:
                                                                    v1209 = -1073741762;
LABEL_1483:
                                                                    v1115 = v1283;
                                                                    v999 = v1209 | 0x10000000;
LABEL_1518:
                                                                    LODWORD(v1280) = v999;
LABEL_1519:
                                                                    v1230 = v1278;
                                                                    if ( !v1278 )
                                                                    {
LABEL_1521:
                                                                      if ( v1000 )
                                                                      {
                                                                        v1232 = (void *)*((_QWORD *)v1000 + 1);
                                                                        if ( v1232 )
                                                                        {
                                                                          v1233 = GetProcessHeap();
                                                                          HeapFree(v1233, 0, v1232);
                                                                          *((_QWORD *)v1000 + 1) = 0;
                                                                        }
                                                                        v1234 = (void *)*((_QWORD *)v1000 + 3);
                                                                        if ( v1234 )
                                                                        {
                                                                          v1235 = GetProcessHeap();
                                                                          HeapFree(v1235, 0, v1234);
                                                                          *((_QWORD *)v1000 + 3) = 0;
                                                                        }
                                                                        v1236 = (void *)*((_QWORD *)v1000 + 5);
                                                                        if ( v1236 )
                                                                        {
                                                                          v1237 = GetProcessHeap();
                                                                          HeapFree(v1237, 0, v1236);
                                                                          *((_QWORD *)v1000 + 5) = 0;
                                                                        }
                                                                        v1238 = GetProcessHeap();
                                                                        HeapFree(v1238, 0, v1000);
                                                                        LODWORD(v990) = 0;
                                                                      }
                                                                      v1239 = (void *)v1297;
                                                                      if ( v1297 )
                                                                      {
                                                                        v1240 = GetProcessHeap();
                                                                        HeapFree(v1240, 0, v1239);
                                                                        LODWORD(v990) = 0;
                                                                      }
                                                                      if ( v1001 )
                                                                      {
                                                                        v1241 = GetProcessHeap();
                                                                        HeapFree(v1241, 0, v1001);
                                                                        LODWORD(v990) = 0;
                                                                      }
                                                                      v1242 = v1291;
                                                                      if ( v1291 )
                                                                      {
                                                                        v1243 = (void *)*((_QWORD *)v1291 + 1);
                                                                        if ( v1243 )
                                                                        {
                                                                          v1244 = GetProcessHeap();
                                                                          HeapFree(v1244, 0, v1243);
                                                                          v1242[1] = 0;
                                                                        }
                                                                        v1245 = (void *)v1242[3];
                                                                        if ( v1245 )
                                                                        {
                                                                          v1246 = GetProcessHeap();
                                                                          HeapFree(v1246, 0, v1245);
                                                                          v1242[3] = 0;
                                                                        }
                                                                        v1247 = (void *)v1242[5];
                                                                        if ( v1247 )
                                                                        {
                                                                          v1248 = GetProcessHeap();
                                                                          HeapFree(v1248, 0, v1247);
                                                                          v1242[5] = 0;
                                                                        }
                                                                        v1249 = GetProcessHeap();
                                                                        HeapFree(v1249, 0, v1242);
                                                                        LODWORD(v990) = 0;
                                                                      }
                                                                      if ( v1115 )
                                                                      {
                                                                        v1250 = GetProcessHeap();
                                                                        HeapFree(v1250, 0, v1115);
                                                                        LODWORD(v990) = 0;
                                                                      }
LABEL_1543:
                                                                      if ( (int)v1280 >= (int)v990 )
                                                                      {
                                                                        v928 = v1276;
                                                                        if ( (_DWORD)v1298 )
                                                                        {
                                                                          if ( v1276 )
                                                                          {
                                                                            lpModuleName = (LPCWSTR)v1276;
                                                                            if ( (int)RtlULongLongAdd(
                                                                                        v1276,
                                                                                        4,
                                                                                        &lpModuleName) >= 0 )
                                                                            {
                                                                              v1254 = lpModuleName;
                                                                              if ( *v928 == (_DWORD)v1253 )
                                                                                v1254 = v1253;
                                                                              if ( *v928 == v1252
                                                                                && *(_DWORD *)v1254 >= (int)v1253
                                                                                && v1251 > 1 )
                                                                              {
                                                                                v1255 = (size_t)v928;
                                                                                v1256 = (int)v1253;
                                                                                v1284 = (size_t)v928;
                                                                                v1257 = v1252;
                                                                                while ( !v1256 )
                                                                                {
                                                                                  if ( (int)RtlULongLongAdd(
                                                                                              v1255,
                                                                                              v1257,
                                                                                              &v1284) < 0
                                                                                    || (int)RtlULongLongAdd(
                                                                                              v1284,
                                                                                              v1258,
                                                                                              &v1284) < 0 )
                                                                                  {
                                                                                    goto LABEL_1560;
                                                                                  }
                                                                                  v1255 = v1284;
                                                                                  v1256 = v1259 + 1;
                                                                                }
                                                                                RtlULongLongAdd(v1255, v1257, &v1284);
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                        goto LABEL_1560;
                                                                      }
                                                                      goto LABEL_1559;
                                                                    }
LABEL_1520:
                                                                    v1231 = GetProcessHeap();
                                                                    HeapFree(v1231, 0, v1230);
                                                                    LODWORD(v990) = 0;
                                                                    goto LABEL_1521;
                                                                  }
                                                                  v1209 = RtlULongLongAdd(v1152, 4, &v1284);
                                                                  if ( v1209 < 0
                                                                    || (v1209 = RtlUIntAdd(0, 4, &v1300), v1209 < 0) )
                                                                  {
LABEL_1482:
                                                                    v1283 = v1210;
                                                                    v1278 = v1057;
                                                                    v1291 = v1208;
                                                                    goto LABEL_1483;
                                                                  }
                                                                  if ( v1211 - v1300 < 4 )
                                                                  {
                                                                    v1209 = -1073741762;
                                                                    goto LABEL_1482;
                                                                  }
                                                                  LODWORD(v1277) = *(_DWORD *)v1284;
                                                                  v1209 = RtlULongLongAdd(v1284, 4, &v1284);
                                                                  if ( v1209 >= 0 )
                                                                  {
                                                                    v1209 = RtlUIntAdd(v1300, 4, &v1300);
                                                                    if ( v1209 >= 0 )
                                                                    {
                                                                      if ( v1212 - v1300 >= v1213 )
                                                                      {
                                                                        v1209 = RtlUIntAdd(v1300, v1213, &v1300);
                                                                        if ( v1209 < 0 )
                                                                          goto LABEL_1481;
                                                                        v1216 = v1215;
                                                                        pcchLength = v1215;
                                                                        v1217 = (const void *)v1284;
                                                                        if ( (unsigned __int64)v1210 + v1214 >= v1216 + v1284
                                                                          && (unsigned __int64)v1210
                                                                           + v1214
                                                                           - v1216
                                                                           - v1284 < 8 )
                                                                        {
                                                                          LODWORD(v1287) = *v1210;
                                                                          lpModuleName = 0;
                                                                          Size = 0;
                                                                          psz = 0;
                                                                          LODWORD(v1274) = 0;
                                                                          if ( v1284 )
                                                                          {
                                                                            v1209 = RtlULongLongAdd(
                                                                                      v1284,
                                                                                      pcchLength,
                                                                                      &lpModuleName);
                                                                            LODWORD(v1280) = v1209;
                                                                            v1283 = v1219;
                                                                            v1291 = v1208;
                                                                            v1278 = v1057;
                                                                            if ( v1209 < 0 )
                                                                            {
LABEL_1510:
                                                                              v1229 = (int)v1298;
LABEL_1511:
                                                                              LODWORD(v990) = 0;
                                                                              if ( v1209 < 0 || (_DWORD)v1287 == v1229 )
                                                                                goto LABEL_1483;
                                                                              goto LABEL_1472;
                                                                            }
                                                                            v1220 = lpModuleName;
                                                                            while ( v1218 < v1220 )
                                                                            {
                                                                              v1209 = RtlULongLongAdd(v1218, 4, &Size);
                                                                              if ( v1209 < 0 )
                                                                                goto LABEL_1510;
                                                                              if ( Size > v1221 )
                                                                                goto LABEL_1497;
                                                                              v1223 = *v1222;
                                                                              v1271 = 0;
                                                                              v1209 = RtlUIntAdd(4, v1223, &v1271);
                                                                              if ( v1209 < 0 )
                                                                                goto LABEL_1498;
                                                                              v1209 = RtlULongLongAdd(
                                                                                        v1224,
                                                                                        v1271,
                                                                                        &psz);
                                                                              LODWORD(v1280) = v1209;
                                                                              if ( v1209 < 0 )
                                                                                goto LABEL_1510;
                                                                              v1218 = psz;
                                                                              if ( psz > v1220 )
                                                                                goto LABEL_1497;
                                                                              LODWORD(v1274) = v1274 + 1;
                                                                            }
                                                                            if ( v1218 != v1220 )
                                                                            {
LABEL_1497:
                                                                              v1209 = -1073741811;
LABEL_1498:
                                                                              LODWORD(v990) = 0;
                                                                              goto LABEL_1483;
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            v1209 = 0;
                                                                            LODWORD(v1280) = 0;
                                                                            v1283 = v1210;
                                                                            v1291 = v1208;
                                                                            v1278 = v1057;
                                                                          }
                                                                          v1225 = 0;
                                                                          if ( (_DWORD)v1277 )
                                                                          {
                                                                            v1226 = GetProcessHeap();
                                                                            v1227 = pcchLength;
                                                                            v1228 = HeapAlloc(v1226, 8u, pcchLength);
                                                                            LODWORD(v990) = 0;
                                                                            v1225 = v1228;
                                                                            if ( !v1228 )
                                                                            {
                                                                              v1209 = -1073741801;
                                                                              goto LABEL_1483;
                                                                            }
                                                                            v1209 = 0;
                                                                            v1217 = (const void *)v1284;
                                                                            LODWORD(v1280) = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            v1227 = pcchLength;
                                                                          }
                                                                          if ( v1217 )
                                                                          {
                                                                            memcpy_0(v1225, v1217, v1227);
                                                                            v1209 = v1280;
                                                                          }
                                                                          v1229 = v1274;
                                                                          LODWORD(v1298) = v1274;
                                                                          v1276 = v1225;
                                                                          goto LABEL_1511;
                                                                        }
                                                                      }
                                                                      v1209 = -1073741762;
                                                                    }
                                                                  }
LABEL_1481:
                                                                  LODWORD(v990) = 0;
                                                                  goto LABEL_1482;
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                    LODWORD(v990) = 0;
                                                  }
                                                }
                                              }
                                            }
                                            v1000 = (unsigned int *)v1285;
                                            v1146 = (unsigned int *)v1291;
                                            v1288 = v1001;
                                            goto LABEL_1437;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v1278 = v1057;
                                v1094 = GetProcessHeap();
                                HeapFree(v1094, 0, v1289);
                                LODWORD(v990) = 0;
                              }
                              v1093 = v1272;
                              goto LABEL_1331;
                            }
LABEL_1301:
                            v1000 = (unsigned int *)v1299;
                            v1299 = 0;
                            goto LABEL_1302;
                          }
                        }
                      }
                    }
                  }
LABEL_1559:
                  v928 = v1276;
                  goto LABEL_1560;
                }
                v1279 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D458[0])(0, 0, 1027);
                if ( !v1279 )
                {
                  GetLastError();
                  goto LABEL_1188;
                }
                v470 = off_18003D3F8[0]();
                v471 = dword_18003DEA0;
                qword_18003E480 = v470;
                LODWORD(v1292) = dword_18003DEA0;
                memset_0(&v1337, 0, 0x70u);
                memset(v1393, 0, 44);
                v1309 = 0;
                while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                  ;
                v472 = dword_18003E488;
                if ( !dword_18003E488 )
                {
                  v473 = (const WCHAR *)MemoryAlloc(0x338u);
                  lpModuleName = v473;
                  if ( !v473 )
                    goto LABEL_601;
                  v474 = qword_1800349B0;
                  v475 = (WCHAR *)v473;
                  v476 = 0;
                  v477 = -1;
                  v478 = 0;
                  v479 = 0;
                  v480 = 103;
                  do
                  {
                    v481 = *((unsigned __int8 *)v474 + 1);
                    v482 = *(unsigned __int8 *)v474;
                    v483 = *((unsigned __int8 *)v474++ + 4);
                    v484 = *((unsigned __int8 *)v474 - 5)
                         | ((*((unsigned __int8 *)v474 - 6) | ((v481 | (v482 << 8)) << 8)) << 8);
                    v485 = v479 ^ v484;
                    v486 = *((unsigned __int8 *)v474 - 1)
                         | ((*((unsigned __int8 *)v474 - 2) | ((*((unsigned __int8 *)v474 - 3) | (v483 << 8)) << 8)) << 8);
                    v487 = v478 ^ v486 ^ v479 ^ v484 ^ 0xAC987321;
                    v488 = v485 ^ (__ROR4__(v487, 22) + 4991 * __ROR4__(v487 + 1419157410, 27));
                    v489 = v487 ^ (43881 * __ROR4__(v488 + 133239679, 9) - __ROR4__(v488, 30));
                    v490 = v488 ^ (24670 * v489 - (v489 >> 13) - 123127970);
                    v491 = v489 ^ (2033 * __ROR4__(v490 ^ 0xAB69, 26) - __ROR4__(v490, 30));
                    v492 = v490 ^ (133239679 - (v491 ^ 0xAB69605E));
                    v493 = v491 ^ (43881 * (v492 ^ 0x137F)) ^ __ROR4__(v492, 6);
                    v494 = v492 ^ (__ROR4__(v493, 30) + 24670 * __ROR4__(v493 + 133239679, 15));
                    v495 = v493 ^ (2033 * __ROR4__(v494 + 1419157410, 14) - __ROR4__(v494, 24));
                    v496 = v494 ^ __ROR4__(v495, 10) ^ (4991 * __ROR4__(v495 ^ 0xAB69605E, 12));
                    v497 = v495 ^ (v496 >> 10) ^ (43881 * (v496 ^ 0x7F1));
                    v498 = v496 ^ (2033 * (__ROR4__(~v497, 5) + 24670));
                    v499 = v498
                         ^ (((v497 ^ (v498 - 2033) ^ 0xAB69605E) >> 2)
                          + 4991 * __ROR4__(v497 ^ (v498 - 2033) ^ 0xAB6967AF, 30));
                    v500 = v497
                         ^ (v498 - 2033)
                         ^ 0xAB69605E
                         ^ (__ROR4__(v499, 25) + 43881 * __ROR4__(v499 - 133239679, 6));
                    v501 = v499 ^ (24670 * (v500 ^ 0x137F) + __ROR4__(v500, 9));
                    v502 = v500 ^ (__ROR4__(v501, 25) + 2033 * __ROR4__(v501 ^ 0xAB69, 27));
                    v503 = v501 ^ v502 ^ 0xAC987321;
                    v504 = v502 ^ (4991 * __ROR4__(v503, 3) - 219010071);
                    v505 = v503 ^ (24670 * __ROR4__(v504 - 133239679, 1) - __ROR4__(v504, 6));
                    v506 = v504 ^ (__ROR4__(v505, 18) + 2033 * __ROR4__(v505 - 1419157410, 29));
                    v507 = v505 ^ (4991 * __ROR4__(v506 - 1419157410, 17) - __ROR4__(v506, 14));
                    v508 = v506 ^ (v507 >> 3) ^ (43881 * (v507 ^ 0x605E));
                    v509 = __ROR4__(v508, 30);
                    v478 = v477 ^ v508;
                    v477 = v486;
                    v479 = v476
                         ^ v507
                         ^ v509
                         ^ (24670 * __ROR4__(v506 ^ (v507 >> 3) ^ (43881 * (v507 ^ 0x605E)) ^ 0x7F1137F, 28));
                    v476 = v484;
                    *((_BYTE *)v475 + 3) = v479;
                    *((_BYTE *)v475 + 7) = v478;
                    *((_BYTE *)v475 + 2) = __ROR4__(v479, 8);
                    *((_BYTE *)v475 + 6) = __ROR4__(v478, 8);
                    *((_BYTE *)v475 + 1) = __ROR4__(v479, 16);
                    *((_BYTE *)v475 + 5) = __ROR4__(v478, 16);
                    *(_BYTE *)v475 = __ROR4__(v479, 24);
                    *((_BYTE *)v475 + 4) = __ROR4__(v478, 24);
                    v475 += 4;
                    --v480;
                  }
                  while ( v480 );
                  v471 = v1292;
                  v120 = 0;
                  v510 = lpModuleName;
                  v511 = 0;
                  v512 = 0;
                  do
                    v512 ^= *((_BYTE *)lpModuleName + v511++);
                  while ( v511 < 0x338 );
                  if ( v512 != 64 )
                  {
                    MemoryFree((void *)lpModuleName);
LABEL_601:
                    for ( kk = 0; kk != 4; ++kk )
                    {
                      v514 = (HMODULE)qword_18003DEB0[3 * kk];
                      if ( v514 )
                        FreeLibrary(v514);
                    }
                    memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                    memcpy_0(off_18003D360, off_18002E370, 0x170u);
LABEL_634:
                    _InterlockedExchange(&dword_18003E48C, 0);
                    LODWORD(v1277) = 0;
                    v1289 = 0;
                    v1297 = 0;
                    WORD2(v1277) = 0;
                    while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                      ;
                    v529 = dword_18003E488;
                    if ( !dword_18003E488 )
                    {
                      v530 = (const WCHAR *)MemoryAlloc(0x338u);
                      lpModuleName = v530;
                      if ( !v530 )
                        goto LABEL_644;
                      v1273 = 0;
                      v531 = (WCHAR *)v530;
                      v532 = qword_1800349B0;
                      v533 = 0;
                      v534 = -1;
                      v535 = 0;
                      v536 = 0;
                      v537 = 103;
                      do
                      {
                        v538 = *(unsigned __int8 *)v532 << 8;
                        v539 = *((unsigned __int8 *)v532 + 1);
                        v540 = *((unsigned __int8 *)v532++ + 4);
                        v541 = *((unsigned __int8 *)v532 - 5)
                             | ((*((unsigned __int8 *)v532 - 6) | ((v538 | v539) << 8)) << 8);
                        v542 = v536 ^ v541;
                        v543 = *((unsigned __int8 *)v532 - 1)
                             | ((*((unsigned __int8 *)v532 - 2) | ((*((unsigned __int8 *)v532 - 3) | (v540 << 8)) << 8)) << 8);
                        v544 = v536 ^ v541 ^ v535 ^ v543 ^ 0xAC987321;
                        v545 = v542 ^ (__ROR4__(v544, 22) + 4991 * __ROR4__(v544 + 1419157410, 27));
                        v546 = v544 ^ (43881 * __ROR4__(v545 + 133239679, 9) - __ROR4__(v545, 30));
                        v547 = v545 ^ (24670 * v546 - (v546 >> 13) - 123127970);
                        v548 = v546 ^ (2033 * __ROR4__(v547 ^ 0xAB69, 26) - __ROR4__(v547, 30));
                        v549 = v547 ^ (133239679 - (v548 ^ 0xAB69605E));
                        v550 = v548 ^ (43881 * (v549 ^ 0x137F)) ^ __ROR4__(v549, 6);
                        v551 = v549 ^ (__ROR4__(v550, 30) + 24670 * __ROR4__(v550 + 133239679, 15));
                        v552 = v550 ^ (2033 * __ROR4__(v551 + 1419157410, 14) - __ROR4__(v551, 24));
                        v553 = v551 ^ __ROR4__(v552, 10) ^ (4991 * __ROR4__(v552 ^ 0xAB69605E, 12));
                        v554 = v552 ^ (v553 >> 10) ^ (43881 * (v553 ^ 0x7F1));
                        v555 = v553 ^ (2033 * (__ROR4__(~v554, 5) + 24670));
                        v556 = v555
                             ^ (((v554 ^ (v555 - 2033) ^ 0xAB69605E) >> 2)
                              + 4991 * __ROR4__(v554 ^ (v555 - 2033) ^ 0xAB6967AF, 30));
                        v557 = v554
                             ^ (v555 - 2033)
                             ^ 0xAB69605E
                             ^ (__ROR4__(v556, 25) + 43881 * __ROR4__(v556 - 133239679, 6));
                        v558 = v556 ^ (24670 * (v557 ^ 0x137F) + __ROR4__(v557, 9));
                        v559 = v557 ^ (__ROR4__(v558, 25) + 2033 * __ROR4__(v558 ^ 0xAB69, 27));
                        v560 = v558 ^ v559 ^ 0xAC987321;
                        v561 = v559 ^ (4991 * __ROR4__(v560, 3) - 219010071);
                        v562 = v560 ^ (24670 * __ROR4__(v561 - 133239679, 1) - __ROR4__(v561, 6));
                        v563 = v561 ^ (__ROR4__(v562, 18) + 2033 * __ROR4__(v562 - 1419157410, 29));
                        v564 = v562 ^ (4991 * __ROR4__(v563 - 1419157410, 17) - __ROR4__(v563, 14));
                        v565 = v563 ^ (v564 >> 3) ^ (43881 * (v564 ^ 0x605E));
                        v566 = v533 ^ __ROR4__(v565, 30) ^ (24670 * __ROR4__(v565 ^ 0x7F1137F, 28));
                        v533 = v541;
                        v536 = v564 ^ v566;
                        *((_BYTE *)v531 + 3) = v536;
                        v535 = v565 ^ v534;
                        *((_BYTE *)v531 + 7) = v565 ^ v534;
                        v534 = v543;
                        *((_BYTE *)v531 + 2) = __ROR4__(v536, 8);
                        *((_BYTE *)v531 + 6) = __ROR4__(v535, 8);
                        *((_BYTE *)v531 + 1) = __ROR4__(v536, 16);
                        *((_BYTE *)v531 + 5) = __ROR4__(v535, 16);
                        *(_BYTE *)v531 = __ROR4__(v536, 24);
                        *((_BYTE *)v531 + 4) = __ROR4__(v535, 24);
                        v531 += 4;
                        --v537;
                      }
                      while ( v537 );
                      v567 = v1273;
                      v120 = 0;
                      v471 = v1292;
                      v568 = 0;
                      v569 = lpModuleName;
                      do
                        v567 ^= *((_BYTE *)lpModuleName + v568++);
                      while ( v568 < 0x338 );
                      if ( v567 != 64 )
                      {
                        MemoryFree((void *)lpModuleName);
LABEL_644:
                        for ( mm = 0; mm != 4; ++mm )
                        {
                          v571 = (HMODULE)qword_18003DEB0[3 * mm];
                          if ( v571 )
                            FreeLibrary(v571);
                        }
                        memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                        memcpy_0(off_18003D360, off_18002E370, 0x170u);
LABEL_677:
                        _InterlockedExchange(&dword_18003E48C, 0);
                        memset_0(&v1337, 0, 0x70u);
                        LOWORD(v1277) = (v471 >> 4) & 0xF;
                        WORD1(v1277) = (v471 >> 8) & 0xF;
                        WORD2(v1277) = (v471 >> 12) & 0xF;
                        v1309 = 0;
                        v1275 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D458[0])(0, 0, 1027);
                        v1272 = 0xFFFFFF;
                        if ( !v1275 )
                        {
                          v586 = GetLastError();
                          v587 = v586;
                          if ( v586 > 0 )
                            v587 = (unsigned __int16)v586 | 0x80070000;
                          if ( v587 >= 0 )
                            v587 = -2147467259;
LABEL_884:
                          v704 = 1;
                          while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                            ;
                          v705 = dword_18003E488;
                          if ( dword_18003E488 > 0 )
                          {
                            --dword_18003E488;
                            if ( v705 == 1 )
                            {
                              do
                              {
                                v706 = (HMODULE)qword_18003DEB0[3 * v120];
                                if ( v706 )
                                  FreeLibrary(v706);
                                ++v120;
                              }
                              while ( v120 != 4 );
                              memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                              memcpy_0(off_18003D360, off_18002E370, 0x170u);
                            }
                          }
                          _InterlockedExchange(&dword_18003E48C, 0);
                          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1297);
                          if ( v587 < 0 )
                          {
LABEL_992:
                            v776 = v1339;
                            if ( v1339 )
                            {
                              v777 = -1;
                              do
                                ++v777;
                              while ( *((_WORD *)v1339 + v777) );
                              for ( nn = 2 * v777 + 2; nn; --nn )
                                *v776++ = 0;
                              MemoryFree(v1339);
                              v1339 = 0;
                            }
                            v779 = v1340;
                            if ( v1340 )
                            {
                              v780 = -1;
                              do
                                ++v780;
                              while ( *((_WORD *)v1340 + v780) );
                              for ( i1 = 2 * v780 + 2; i1; --i1 )
                                *v779++ = 0;
                              MemoryFree(v1340);
                              v1340 = 0;
                            }
                            v782 = v1341;
                            if ( v1341 )
                            {
                              v783 = -1;
                              do
                                ++v783;
                              while ( *((_WORD *)v1341 + v783) );
                              v784 = 2 * v783 + 2;
                              if ( v784 )
                              {
                                do
                                {
                                  *v782++ = 0;
                                  --v784;
                                }
                                while ( v784 );
                                v782 = v1341;
                              }
                              MemoryFree(v782);
                              v1341 = 0;
                            }
                            if ( v1342 )
                            {
                              off_18003D398[0]();
                              v1342 = 0;
                            }
                            if ( v1343 )
                            {
                              off_18003D398[0]();
                              v1343 = 0;
                            }
                            if ( v1344 )
                            {
                              off_18003D398[0]();
                              v1344 = 0;
                            }
                            while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                              ;
                            v785 = dword_18003E488;
                            if ( dword_18003E488 > 0 )
                            {
                              --dword_18003E488;
                              if ( v785 == 1 )
                              {
                                for ( i2 = 0; i2 != 4; ++i2 )
                                {
                                  v787 = (HMODULE)qword_18003DEB0[3 * i2];
                                  if ( v787 )
                                    FreeLibrary(v787);
                                }
                                memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                                memcpy_0(off_18003D360, off_18002E370, 0x170u);
                              }
                            }
                            _InterlockedExchange(&dword_18003E48C, 0);
                            v788 = dword_18003DEA0;
                            v789 = qword_18003E480;
                            LODWORD(v1276) = dword_18003DEA0;
                            v790 = (unsigned int)off_18003D3F8[0]() - v789;
                            pcchLength = v790;
                            v1423 = 0;
                            v1424 = 0;
                            v1427 = 0;
                            v1425 = 0;
                            v1426 = 0;
                            while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                              ;
                            v866 = dword_18003E488;
                            if ( !dword_18003E488 )
                            {
                              v867 = MemoryAlloc(0x338u);
                              v868 = 0;
                              *(_QWORD *)&v1304 = v867;
                              if ( !v867 )
                                goto LABEL_1145;
                              v869 = v867;
                              v870 = qword_1800349B0;
                              v871 = 103;
                              v872 = 0;
                              v873 = -1;
                              v874 = 0;
                              do
                              {
                                v875 = *((unsigned __int8 *)v870 + 1);
                                v876 = *(unsigned __int8 *)v870;
                                v877 = *((unsigned __int8 *)v870++ + 4);
                                v878 = *((unsigned __int8 *)v870 - 5)
                                     | ((*((unsigned __int8 *)v870 - 6) | ((v875 | (v876 << 8)) << 8)) << 8);
                                v879 = v868 ^ v878;
                                v880 = *((unsigned __int8 *)v870 - 1)
                                     | ((*((unsigned __int8 *)v870 - 2)
                                       | ((*((unsigned __int8 *)v870 - 3) | (v877 << 8)) << 8)) << 8);
                                v881 = v874 ^ v880 ^ v868 ^ v878 ^ 0xAC987321;
                                v882 = v879 ^ (__ROR4__(v881, 22) + 4991 * __ROR4__(v881 + 1419157410, 27));
                                v883 = v881 ^ (43881 * __ROR4__(v882 + 133239679, 9) - __ROR4__(v882, 30));
                                v884 = v882 ^ (24670 * v883 - (v883 >> 13) - 123127970);
                                v885 = v883 ^ (2033 * __ROR4__(v884 ^ 0xAB69, 26) - __ROR4__(v884, 30));
                                v886 = v884 ^ (133239679 - (v885 ^ 0xAB69605E));
                                v887 = v885 ^ (43881 * (v886 ^ 0x137F)) ^ __ROR4__(v886, 6);
                                v888 = v886 ^ (__ROR4__(v887, 30) + 24670 * __ROR4__(v887 + 133239679, 15));
                                v889 = v887 ^ (2033 * __ROR4__(v888 + 1419157410, 14) - __ROR4__(v888, 24));
                                v890 = v888 ^ __ROR4__(v889, 10) ^ (4991 * __ROR4__(v889 ^ 0xAB69605E, 12));
                                v891 = v889 ^ (v890 >> 10) ^ (43881 * (v890 ^ 0x7F1));
                                v892 = v890 ^ (2033 * (__ROR4__(~v891, 5) + 24670));
                                v893 = v892
                                     ^ (((v891 ^ (v892 - 2033) ^ 0xAB69605E) >> 2)
                                      + 4991 * __ROR4__(v891 ^ (v892 - 2033) ^ 0xAB6967AF, 30));
                                v894 = v891
                                     ^ (v892 - 2033)
                                     ^ 0xAB69605E
                                     ^ (__ROR4__(v893, 25) + 43881 * __ROR4__(v893 - 133239679, 6));
                                v895 = v893 ^ (24670 * (v894 ^ 0x137F) + __ROR4__(v894, 9));
                                v896 = v894 ^ (__ROR4__(v895, 25) + 2033 * __ROR4__(v895 ^ 0xAB69, 27));
                                v897 = v895 ^ v896 ^ 0xAC987321;
                                v898 = v896 ^ (4991 * __ROR4__(v897, 3) - 219010071);
                                v899 = v897 ^ (24670 * __ROR4__(v898 - 133239679, 1) - __ROR4__(v898, 6));
                                v900 = v898 ^ (__ROR4__(v899, 18) + 2033 * __ROR4__(v899 - 1419157410, 29));
                                v901 = v899 ^ (4991 * __ROR4__(v900 - 1419157410, 17) - __ROR4__(v900, 14));
                                v902 = v900 ^ (v901 >> 3) ^ (43881 * (v901 ^ 0x605E));
                                v903 = __ROR4__(v902, 30);
                                v874 = v873 ^ v902;
                                v873 = v880;
                                v868 = v872
                                     ^ v901
                                     ^ v903
                                     ^ (24670 * __ROR4__(v900 ^ (v901 >> 3) ^ (43881 * (v901 ^ 0x605E)) ^ 0x7F1137F, 28));
                                v872 = v878;
                                v869[3] = v868;
                                v869[7] = v874;
                                v869[2] = __ROR4__(v868, 8);
                                v869[6] = __ROR4__(v874, 8);
                                v869[1] = __ROR4__(v868, 16);
                                v869[5] = __ROR4__(v874, 16);
                                *v869 = __ROR4__(v868, 24);
                                v869[4] = __ROR4__(v874, 24);
                                v869 += 8;
                                --v871;
                              }
                              while ( v871 );
                              v904 = (const WCHAR *)v1304;
                              v905 = 0;
                              v906 = 0;
                              do
                                v906 ^= *(_BYTE *)(v1304 + v905++);
                              while ( v905 < 0x338 );
                              if ( v906 != 64 )
                              {
                                MemoryFree((void *)v1304);
LABEL_1144:
                                v788 = (int)v1276;
                                LODWORD(v790) = pcchLength;
LABEL_1145:
                                for ( i3 = 0; i3 != 4; ++i3 )
                                {
                                  v908 = (HMODULE)qword_18003DEB0[3 * i3];
                                  if ( v908 )
                                    FreeLibrary(v908);
                                }
                                memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                                memcpy_0(off_18003D360, off_18002E370, 0x170u);
                                goto LABEL_1178;
                              }
                              LODWORD(v1274) = 0;
                              LODWORD(v1278) = 0;
                              *(_BYTE *)(v1304 + 823) = 0;
                              v909 = 0;
                              v910 = 0;
                              memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                              *(_QWORD *)&v1304 = v904;
                              while ( *(_BYTE *)v904 )
                              {
                                v911 = -1;
                                do
                                  ++v911;
                                while ( v904[v911] );
                                v912 = 3LL * v910;
                                v913 = (HMODULE *)&qword_18003DEB0[v912];
                                if ( !GetModuleHandleExW(0, v904, v913) )
                                {
                                  v909 = -1073741702;
                                  break;
                                }
                                v914 = &v904[v911];
                                if ( *(_WORD *)*v913 == 23117
                                  && (v915 = *((int *)*v913 + 15), (unsigned int)v915 < 0x10000000)
                                  && (v916 = (char *)*v913 + v915, v916 >= (char *)*v913)
                                  && *(_DWORD *)v916 == 17744 )
                                {
                                  if ( ((*((_WORD *)v916 + 12) - 267) & 0xFEFF) != 0 )
                                  {
                                    v909 = -1073741811;
                                  }
                                  else
                                  {
                                    *(__int64 *)((char *)&qword_18003DEB0[v912 + 1] + 4) = *((_QWORD *)v916 + 17);
                                    v909 = 0;
                                    LODWORD(qword_18003DEB0[v912 + 1]) = *((_DWORD *)v916 + 20);
                                  }
                                }
                                else
                                {
                                  v909 = -1073741701;
                                }
                                v917 = *(_DWORD *)(v914 + 1);
                                v918 = 0;
                                v919 = v1274;
                                v904 = v914 + 3;
                                LODWORD(v1277) = v917;
                                while ( 1 )
                                {
                                  v1271 = v918;
                                  if ( v918 >= v917 )
                                    break;
                                  v920 = -1;
                                  do
                                    ++v920;
                                  while ( *((_BYTE *)v904 + v920) );
                                  if ( v909 >= 0 )
                                  {
                                    v921 = GetProcAddress(*v913, (LPCSTR)v904);
                                    if ( !v921 )
                                      goto LABEL_1173;
                                    v919 = v1274;
                                    v917 = (unsigned int)v1277;
                                    off_18003D360[(unsigned int)v1274] = v921;
                                    v918 = v1271;
                                  }
                                  ++v919;
                                  v904 = (const WCHAR *)((char *)v904 + v920 + 1);
                                  LODWORD(v1274) = v919;
                                  ++v918;
                                }
                                v910 = (_DWORD)v1278 + 1;
                                LODWORD(v1278) = (_DWORD)v1278 + 1;
                              }
LABEL_1173:
                              v922 = (void *)v1304;
                              if ( (_QWORD)v1304 )
                              {
                                v923 = GetProcessHeap();
                                HeapFree(v923, 0, v922);
                              }
                              if ( v909 < 0 )
                                goto LABEL_1144;
                              v866 = dword_18003E488;
                              LODWORD(v790) = pcchLength;
                              v788 = (int)v1276;
                            }
                            dword_18003E488 = v866 + 1;
LABEL_1178:
                            _InterlockedExchange(&dword_18003E48C, 0);
                            LODWORD(v1424) = v790;
                            v1423 = 1;
                            LODWORD(v1425) = -1721306479;
                            DWORD2(v1424) = 1;
                            LODWORD(v1426) = 1;
                            DWORD2(v1425) = 1;
                            LODWORD(v1427) = v788;
                            DWORD2(v1426) = 1;
                            ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_18003D430)(0, 8225, 4, &v1423);
                            while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                              ;
                            v924 = dword_18003E488;
                            if ( dword_18003E488 > 0 )
                            {
                              --dword_18003E488;
                              if ( v924 == 1 )
                              {
                                for ( i4 = 0; i4 != 4; ++i4 )
                                {
                                  v926 = (HMODULE)qword_18003DEB0[3 * i4];
                                  if ( v926 )
                                    FreeLibrary(v926);
                                }
                                memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                                memcpy_0(off_18003D360, off_18002E370, 0x170u);
                              }
                            }
                            _InterlockedExchange(&dword_18003E48C, 0);
                            ((void (__fastcall *)(_QWORD, LPVOID))off_18003D4C0[0])(0, v1279);
                            goto LABEL_1188;
                          }
                          v707 = v1309;
                          Size = 0;
                          lpModuleName = (LPCWSTR)v1309;
                          v1358 = 0;
                          memset_0(v1359, 0, 0x64u);
                          v708 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3B0[0])(v1279, 7);
                          if ( v708
                            && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                 v708,
                                 104,
                                 &v1358) )
                          {
                            if ( v1360 != 32 || !v1361 || v1359[0] <= 0 || v1359[1] <= 0 )
                              v704 = 0;
                            v709 = v471 & 0xF;
                            v710 = v709;
                            if ( v704 )
                            {
LABEL_904:
                              ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18003D4B0)(
                                &v1346,
                                v707,
                                HIDWORD(lpModuleName));
                              ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18003D4B0)(
                                &v1350,
                                v707,
                                HIDWORD(lpModuleName));
                              if ( v709 == 1 )
                                Size = ((__int64 (__fastcall *)(_QWORD))off_18003D388[0])(v1338 == 0 ? 0xB26720 : 0);
LABEL_906:
                              v711 = v1279;
                              LODWORD(v1277) = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3E0[0])(v1279, 1);
                              v712 = 2064;
                              if ( v1337 )
                                v712 = 133138;
                              LODWORD(v1298) = v712;
                              if ( v704 )
                              {
                                v713 = 0;
                                v1362 = 0;
                                memset_0(v1363, 0, 0x64u);
                                v1374 = 0;
                                memset_0(v1375, 0, 0x64u);
                                v1284 = (size_t)v1339;
                                memset(v1398, 0, 28);
                                v1397 = 0;
                                v1386 = 0;
                                if ( !v1339 )
                                  goto LABEL_990;
                                v1271 = v1338;
                                v1297 = (SIZE_T)v1342;
                                v714 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3B0[0])(v711, 7);
                                if ( v714 )
                                {
                                  if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                         v714,
                                         104,
                                         &v1362) )
                                  {
                                    LODWORD(v1274) = v1363[0];
                                    psz = v1364;
                                    v713 = 0;
                                    LODWORD(v1276) = v1363[1];
                                  }
                                  else
                                  {
                                    psz = 0;
                                    LODWORD(v1276) = 0;
                                    LODWORD(v1274) = 0;
                                  }
                                  v715 = ((__int64 (__fastcall *)(LPVOID))off_18003D370[0])(v711);
                                  pcchLength = v715;
                                  v716 = v715;
                                  if ( v715 )
                                  {
                                    DWORD1(v1397) = v1348 - v1346;
                                    DWORD2(v1397) = v1347 - v1349;
                                    v1330 = 0;
                                    memset(v1398, 0, 28);
                                    LODWORD(v1397) = 40;
                                    HIDWORD(v1397) = 2097153;
                                    v717 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18003D378[0])(
                                             v715,
                                             &v1397,
                                             0,
                                             &v1330,
                                             0,
                                             0);
                                    v1303 = v717;
                                    if ( v717 )
                                    {
                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                             v717,
                                             104,
                                             &v1374) )
                                      {
                                        lpModuleName = v1376;
                                      }
                                      else
                                      {
                                        lpModuleName = 0;
                                      }
                                      DWORD2(v1386) = v1348 - v1346;
                                      HIDWORD(v1386) = v1349 - v1347;
                                      ((void (__fastcall *)(size_t, unsigned __int64))off_18003D3D8[0])(v716, v1303);
                                      ((void (__fastcall *)(size_t, __int64))off_18003D3E0[0])(v716, 1);
                                      v720 = (void *)((__int64 (__fastcall *)(size_t, SIZE_T))off_18003D3D8[0])(
                                                       v716,
                                                       v1297);
                                      v721 = off_18003D448[0];
                                      v1289 = v720;
                                      v722 = ((__int64 (__fastcall *)(_QWORD))off_18003D3D0[0])(0);
                                      ((void (__fastcall *)(size_t, __int128 *, __int64))v721)(pcchLength, &v1386, v722);
                                      v716 = pcchLength;
                                      ((void (__fastcall *)(size_t, size_t, __int64, __int128 *, _DWORD, _QWORD))off_18003D438[0])(
                                        pcchLength,
                                        v1284,
                                        0xFFFFFFFFLL,
                                        &v1386,
                                        (_DWORD)v1298,
                                        0);
                                      if ( v709 == 1 )
                                      {
                                        if ( v1271 )
                                          v723 = ((__int64 (__fastcall *)(__int64))off_18003D478[0])(8);
                                        else
                                          v723 = 0xFFFFFF;
                                      }
                                      else
                                      {
                                        v723 = -5723992;
                                      }
                                      v724 = 0;
                                      v725 = -v1346;
                                      LODWORD(v1288) = v723;
                                      v726 = 0;
                                      if ( v1346 >= 0 )
                                      {
                                        v724 = v1346;
                                        v725 = 0;
                                      }
                                      v727 = -v1347;
                                      if ( v1347 >= 0 )
                                      {
                                        v726 = v1347;
                                        v727 = 0;
                                      }
                                      v728 = DWORD2(v1386) - v725;
                                      if ( DWORD2(v1386) - v725 >= (int)v1274 - v724 )
                                        v728 = v1274 - v724;
                                      v1271 = v728;
                                      v729 = HIDWORD(v1386) - v727;
                                      if ( HIDWORD(v1386) - v727 >= (int)v1276 - v726 )
                                        v729 = (_DWORD)v1276 - v726;
                                      LODWORD(v1283) = v729;
                                      if ( v728 > 0 && v729 > 0 )
                                      {
                                        v730 = (unsigned __int8)v1288;
                                        v731 = v1271;
                                        LODWORD(v1276) = 0;
                                        v732 = &lpModuleName[2 * v725 + 2 * (__int64)(DWORD2(v1386) * v727)];
                                        v1297 = (SIZE_T)v732;
                                        v733 = &psz[2 * v724 + 2 * (__int64)((int)v1274 * v726)];
                                        LODWORD(v1278) = (unsigned int)v1288 >> 8;
                                        LODWORD(v1285) = (unsigned int)v1288 >> 16;
                                        v1284 = 4LL * SDWORD2(v1386);
                                        v1275 = (LPVOID)(4LL * (int)v1274);
                                        psz = v733;
                                        do
                                        {
                                          v734 = (char)v1278;
                                          v735 = 0;
                                          v736 = (char)v1285;
                                          v737 = v732;
                                          lpModuleName = v732;
                                          v738 = v733;
                                          LODWORD(v1274) = 0;
                                          do
                                          {
                                            v739 = ~(unsigned __int8)((*(unsigned __int8 *)v737
                                                                     + *((unsigned __int8 *)v737 + 2)
                                                                     + 2 * (unsigned int)*((unsigned __int8 *)v737 + 1)) >> 2);
                                            if ( (unsigned __int8)((*(unsigned __int8 *)v737
                                                                  + *((unsigned __int8 *)v737 + 2)
                                                                  + 2 * (unsigned int)*((unsigned __int8 *)v737 + 1)) >> 2) != 0xFF )
                                            {
                                              v740 = *((unsigned __int8 *)v738 + 2);
                                              v741 = v739;
                                              v742 = (int)((unsigned __int64)(2155905153LL * v739 * (v730 - v740)) >> 32) >> 7;
                                              *((_BYTE *)v738 + 2) = v740 + (v742 < 0) + v742;
                                              *((_BYTE *)v738 + 1) -= v741 * (v734 - *((_BYTE *)v738 + 1));
                                              *(_BYTE *)v738 -= v741 * (v736 - *(_BYTE *)v738);
                                              v743 = *((unsigned __int8 *)v738 + 3);
                                              v744 = v741 * (255 - v743);
                                              v735 = v1274;
                                              LOBYTE(v742) = v743 + v744 / 255;
                                              v737 = lpModuleName;
                                              *((_BYTE *)v738 + 3) = v742;
                                            }
                                            ++v735;
                                            v737 += 2;
                                            LODWORD(v1274) = v735;
                                            v738 += 2;
                                            lpModuleName = v737;
                                          }
                                          while ( v735 < v731 );
                                          v732 = (const WCHAR *)(v1284 + v1297);
                                          v733 = (STRSAFE_PCNZWCH)((char *)psz + (_QWORD)v1275);
                                          v1297 += v1284;
                                          psz = (STRSAFE_PCNZWCH)((char *)psz + (_QWORD)v1275);
                                          LODWORD(v1276) = (_DWORD)v1276 + 1;
                                        }
                                        while ( (int)v1276 < (int)v1283 );
                                        v83 = dwBytes;
                                        v716 = pcchLength;
                                      }
                                      ((void (__fastcall *)(unsigned __int64))off_18003D398[0])(v1303);
                                      v719 = 0;
                                      if ( v1289 )
                                        ((void (__fastcall *)(size_t, LPVOID))off_18003D3D8[0])(v716, v1289);
                                    }
                                    else
                                    {
                                      v718 = GetLastError();
                                      v719 = 0;
                                      v713 = v718;
                                      if ( v718 > 0 )
                                        v713 = (unsigned __int16)v718 | 0x80070000;
                                      if ( v713 >= 0 )
                                        v713 = -2147467259;
                                    }
                                    ((void (__fastcall *)(size_t))off_18003D390[0])(v716);
                                    if ( v713 < 0 )
                                      goto LABEL_990;
                                    v1365 = 0;
                                    memset_0(v1366, 0, 0x64u);
                                    v1377 = 0;
                                    memset_0(v1378, 0, 0x64u);
                                    v1297 = (SIZE_T)v1340;
                                    memset(v1400, 0, 28);
                                    v1399 = 0;
                                    v1389 = 0;
                                    if ( !v1340 )
                                      goto LABEL_990;
                                    v745 = v1279;
                                    v1271 = v1338;
                                    psz = v1343;
                                    v746 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3B0[0])(v1279, 7);
                                    if ( v746 )
                                    {
                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                             v746,
                                             104,
                                             &v1365) )
                                      {
                                        LODWORD(v1274) = v1366[0];
                                        pcchLength = v1367;
                                        v745 = v1279;
                                        LODWORD(v1276) = v1366[1];
                                      }
                                      else
                                      {
                                        pcchLength = 0;
                                        LODWORD(v1276) = 0;
                                        LODWORD(v1274) = 0;
                                      }
                                      v747 = ((__int64 (__fastcall *)(LPVOID))off_18003D370[0])(v745);
                                      v1284 = v747;
                                      v748 = v747;
                                      if ( v747 )
                                      {
                                        DWORD1(v1399) = v1352 - v1350;
                                        DWORD2(v1399) = v1351 - v1353;
                                        v1331 = 0;
                                        memset(v1400, 0, 28);
                                        LODWORD(v1399) = 40;
                                        HIDWORD(v1399) = 2097153;
                                        v1275 = (LPVOID)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18003D378[0])(
                                                          v747,
                                                          &v1399,
                                                          0,
                                                          &v1331,
                                                          0,
                                                          0);
                                        v749 = v1275;
                                        if ( v1275 )
                                        {
                                          if ( ((unsigned int (__fastcall *)(LPVOID, __int64, int *))off_18003D3C8[0])(
                                                 v1275,
                                                 104,
                                                 &v1377) )
                                          {
                                            lpModuleName = v1379;
                                          }
                                          else
                                          {
                                            lpModuleName = 0;
                                          }
                                          DWORD2(v1389) = v1352 - v1350;
                                          HIDWORD(v1389) = v1353 - v1351;
                                          ((void (__fastcall *)(size_t, LPVOID))off_18003D3D8[0])(v748, v749);
                                          ((void (__fastcall *)(size_t, __int64))off_18003D3E0[0])(v748, 1);
                                          v751 = (void *)((__int64 (__fastcall *)(size_t, STRSAFE_PCNZWCH))off_18003D3D8[0])(
                                                           v748,
                                                           psz);
                                          v752 = off_18003D448[0];
                                          v1289 = v751;
                                          v753 = ((__int64 (__fastcall *)(_QWORD))off_18003D3D0[0])(0);
                                          ((void (__fastcall *)(size_t, __int128 *, __int64))v752)(v748, &v1389, v753);
                                          ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_18003D438[0])(
                                            v748,
                                            v1297,
                                            0xFFFFFFFFLL,
                                            &v1389,
                                            (_DWORD)v1298,
                                            0);
                                          if ( v710 == 1 )
                                          {
                                            if ( v1271 )
                                              v1272 = ((__int64 (__fastcall *)(__int64))off_18003D478[0])(8);
                                          }
                                          else
                                          {
                                            v1272 = -5723992;
                                          }
                                          v754 = 0;
                                          v755 = -v1350;
                                          v756 = 0;
                                          if ( v1350 >= 0 )
                                          {
                                            v754 = v1350;
                                            v755 = 0;
                                          }
                                          v757 = -v1351;
                                          if ( v1351 >= 0 )
                                          {
                                            v757 = 0;
                                            v756 = v1351;
                                          }
                                          v758 = DWORD2(v1389) - v755;
                                          if ( DWORD2(v1389) - v755 >= (int)v1274 - v754 )
                                            v758 = v1274 - v754;
                                          v759 = HIDWORD(v1389) - v757;
                                          if ( HIDWORD(v1389) - v757 >= (int)v1276 - v756 )
                                            v759 = (_DWORD)v1276 - v756;
                                          LODWORD(v1285) = v759;
                                          if ( v758 > 0 && v759 > 0 )
                                          {
                                            LODWORD(v1276) = 0;
                                            v760 = &lpModuleName[2 * v755 + 2 * (__int64)(DWORD2(v1389) * v757)];
                                            psz = v760;
                                            v761 = pcchLength + 4 * (v754 + (__int64)((int)v1274 * v756));
                                            v1271 = (unsigned int)v1272 >> 8;
                                            LODWORD(v1278) = HIWORD(v1272);
                                            v1297 = 4LL * SDWORD2(v1389);
                                            v1303 = 4LL * (int)v1274;
                                            pcchLength = v761;
                                            do
                                            {
                                              v762 = v1271;
                                              v763 = v760;
                                              v764 = (char)v1278;
                                              v765 = (_BYTE *)v761;
                                              v766 = v1272;
                                              v767 = 0;
                                              lpModuleName = v760;
                                              LODWORD(v1274) = 0;
                                              do
                                              {
                                                v768 = ~(unsigned __int8)((*(unsigned __int8 *)v763
                                                                         + *((unsigned __int8 *)v763 + 2)
                                                                         + 2
                                                                         * (unsigned int)*((unsigned __int8 *)v763 + 1)) >> 2);
                                                if ( (unsigned __int8)((*(unsigned __int8 *)v763
                                                                      + *((unsigned __int8 *)v763 + 2)
                                                                      + 2 * (unsigned int)*((unsigned __int8 *)v763 + 1)) >> 2) != 0xFF )
                                                {
                                                  v769 = (unsigned __int8)v765[2];
                                                  v770 = v768;
                                                  v771 = (int)((unsigned __int64)(2155905153LL * v768 * (v766 - v769)) >> 32) >> 7;
                                                  v765[2] = v769 + (v771 < 0) + v771;
                                                  v765[1] -= v770 * (v762 - v765[1]);
                                                  *v765 -= v770 * (v764 - *v765);
                                                  v772 = (unsigned __int8)v765[3];
                                                  v773 = v770 * (255 - v772);
                                                  v767 = v1274;
                                                  LOBYTE(v771) = v772 + v773 / 255;
                                                  v763 = lpModuleName;
                                                  v765[3] = v771;
                                                }
                                                v763 += 2;
                                                ++v767;
                                                v765 += 4;
                                                lpModuleName = v763;
                                                LODWORD(v1274) = v767;
                                              }
                                              while ( v767 < v758 );
                                              v760 = (STRSAFE_PCNZWCH)((char *)psz + v1297);
                                              v761 = v1303 + pcchLength;
                                              psz = (STRSAFE_PCNZWCH)((char *)psz + v1297);
                                              pcchLength += v1303;
                                              LODWORD(v1276) = (_DWORD)v1276 + 1;
                                            }
                                            while ( (int)v1276 < (int)v1285 );
                                            v83 = dwBytes;
                                            v748 = v1284;
                                          }
                                          ((void (__fastcall *)(LPVOID))off_18003D398[0])(v1275);
                                          if ( v1289 )
                                            ((void (__fastcall *)(size_t, LPVOID))off_18003D3D8[0])(v748, v1289);
                                        }
                                        else
                                        {
                                          v750 = GetLastError();
                                          v719 = v750;
                                          if ( v750 > 0 )
                                            v719 = (unsigned __int16)v750 | 0x80070000;
                                          if ( v719 >= 0 )
                                            v719 = -2147467259;
                                        }
                                        ((void (__fastcall *)(size_t))off_18003D390[0])(v748);
                                        if ( v719 < 0 )
                                          goto LABEL_990;
                                        v1289 = 0;
                                        v774 = 0;
                                        v775 = v1279;
LABEL_1133:
                                        ((void (__fastcall *)(LPVOID, _QWORD))off_18003D3E0[0])(
                                          v775,
                                          (unsigned int)v1277);
                                        if ( !v774 )
                                        {
LABEL_1048:
                                          v800 = v1289;
                                          if ( !v1289 )
                                            goto LABEL_990;
                                          goto LABEL_1049;
                                        }
LABEL_1047:
                                        ((void (__fastcall *)(LPVOID))off_18003D398[0])(v774);
                                        goto LABEL_1048;
                                      }
                                    }
                                  }
                                }
LABEL_989:
                                GetLastError();
                                goto LABEL_990;
                              }
                              if ( v1338 || (v791 = -64, v710 == 1) )
                                v791 = -1;
                              BYTE2(v1299) = v791;
                              LOWORD(v1299) = 0;
                              BYTE3(v1299) = 1;
                              v1289 = (LPVOID)((__int64 (__fastcall *)(LPVOID))off_18003D370[0])(v711);
                              if ( !v1289 )
                                goto LABEL_989;
                              if ( v710 == 1 )
                              {
                                v792 = 0;
                                LODWORD(v1283) = 0;
                                v793 = v1352 - v1350;
                                if ( v1352 - v1350 <= v1348 - v1346 )
                                  v793 = v1348 - v1346;
                                v794 = v1353 - v1347;
                                LODWORD(v1288) = v793;
                                LODWORD(v1301) = v1353 - v1347;
                                if ( v1337 )
                                {
                                  v795 = v1346 + v793 - v1348;
                                  LODWORD(v1291) = v795;
                                  v796 = v793 + v1350 - v1352;
                                }
                                else
                                {
                                  v795 = 0;
                                  LODWORD(v1291) = 0;
                                  v796 = 0;
                                }
                                HIDWORD(dwBytes) = v796;
                                v797 = v1351 - v1347;
                                LODWORD(v1292) = v1348 + v795 - v1346;
                                LODWORD(v1285) = v1349 - v1347;
                                LODWORD(v1293) = v796 + v1352 - v1350;
                                v798 = v1353 - v1347;
                              }
                              else
                              {
                                v793 = DWORD2(v1309);
                                v794 = HIDWORD(v1309);
                                v795 = v1346;
                                v792 = v1347;
                                v797 = v1351;
                                LODWORD(v1292) = v1348;
                                HIDWORD(dwBytes) = v1350;
                                LODWORD(v1293) = v1352;
                                v798 = v1353;
                                LODWORD(v1301) = HIDWORD(v1309);
                                LODWORD(v1288) = DWORD2(v1309);
                                LODWORD(v1291) = v1346;
                                LODWORD(v1283) = v1347;
                                LODWORD(v1285) = v1349;
                              }
                              v1393[2] = -v794;
                              LODWORD(v1274) = v798;
                              v1332 = 0;
                              v1393[1] = v793;
                              v1271 = v797;
                              memset(&v1393[4], 0, 28);
                              v1393[0] = 40;
                              v1393[3] = 2097153;
                              v799 = (void *)((__int64 (__fastcall *)(LPVOID, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_18003D378[0])(
                                               v1289,
                                               v1393,
                                               0,
                                               &v1332,
                                               0,
                                               0);
                              v1275 = v799;
                              if ( !v799 )
                              {
                                GetLastError();
                                v800 = v1289;
LABEL_1049:
                                ((void (__fastcall *)(LPVOID))off_18003D390[0])(v800);
LABEL_990:
                                if ( Size )
                                  ((void (__fastcall *)(SIZE_T))off_18003D398[0])(Size);
                                goto LABEL_992;
                              }
                              ((void (__fastcall *)(LPVOID, void *))off_18003D3D8[0])(v1289, v799);
                              if ( v710 == 1 && Size )
                              {
                                v1390 = 0;
                                v1391 = (int)v1288;
                                v1392 = v1301;
                                ((void (__fastcall *)(LPVOID, __int64 *))off_18003D448[0])(v1289, &v1390);
                              }
                              v1368 = 0;
                              memset_0(v1369, 0, 0x64u);
                              v1380 = 0;
                              memset_0(v1381, 0, 0x64u);
                              v1303 = (unsigned __int64)v1339;
                              memset(v1402, 0, 28);
                              v1401 = 0;
                              v1387 = 0;
                              if ( v1339 )
                              {
                                LODWORD(v1287) = v1338;
                                psz = v1342;
                                v801 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3B0[0])(v1289, 7);
                                if ( !v801 )
                                  goto LABEL_1045;
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                       v801,
                                       104,
                                       &v1368) )
                                {
                                  pcchLength = v1370;
                                  LODWORD(v1276) = v1369[0];
                                  LODWORD(v1278) = v1369[1];
                                }
                                else
                                {
                                  pcchLength = 0;
                                  LODWORD(v1278) = 0;
                                  LODWORD(v1276) = 0;
                                }
                                v802 = ((__int64 (__fastcall *)(LPVOID))off_18003D370[0])(v1289);
                                v1284 = v802;
                                if ( !v802 )
                                  goto LABEL_1045;
                                v1334[0] = 0;
                                v803 = v1292 - v795;
                                LODWORD(v1401) = 40;
                                v804 = (int)v1285;
                                DWORD2(v1401) = v792 - (_DWORD)v1285;
                                v805 = 0;
                                LODWORD(v1292) = v803;
                                DWORD1(v1401) = v803;
                                memset(v1402, 0, 28);
                                HIDWORD(v1401) = 2097153;
                                v806 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18003D378[0])(
                                         v802,
                                         &v1401,
                                         0,
                                         v1334,
                                         0,
                                         0);
                                v1297 = v806;
                                if ( v806 )
                                {
                                  if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_18003D3C8[0])(
                                         v806,
                                         104,
                                         &v1380) )
                                  {
                                    lpModuleName = v1382;
                                  }
                                  else
                                  {
                                    lpModuleName = 0;
                                  }
                                  HIDWORD(v1387) = v804 - (_DWORD)v1283;
                                  v808 = v1284;
                                  DWORD2(v1387) = v1292;
                                  ((void (__fastcall *)(size_t, SIZE_T))off_18003D3D8[0])(v1284, v1297);
                                  ((void (__fastcall *)(size_t, __int64))off_18003D3E0[0])(v808, 1);
                                  v809 = ((__int64 (__fastcall *)(size_t, STRSAFE_PCNZWCH))off_18003D3D8[0])(v808, psz);
                                  v810 = off_18003D448[0];
                                  *(_QWORD *)&v1304 = v809;
                                  v811 = ((__int64 (__fastcall *)(_QWORD))off_18003D3D0[0])(0);
                                  ((void (__fastcall *)(size_t, __int128 *, __int64))v810)(v1284, &v1387, v811);
                                  v812 = v1284;
                                  ((void (__fastcall *)(size_t, unsigned __int64, __int64, __int128 *, _DWORD, _QWORD))off_18003D438[0])(
                                    v1284,
                                    v1303,
                                    0xFFFFFFFFLL,
                                    &v1387,
                                    (_DWORD)v1298,
                                    0);
                                  if ( v710 == 1 )
                                  {
                                    if ( (_DWORD)v1287 )
                                      v813 = ((__int64 (__fastcall *)(__int64))off_18003D478[0])(8);
                                    else
                                      v813 = 0xFFFFFF;
                                  }
                                  else
                                  {
                                    v813 = -5723992;
                                  }
                                  v814 = (int)v1283;
                                  v815 = -(int)v1291;
                                  LODWORD(v1292) = v813;
                                  v816 = 0;
                                  if ( (int)v1291 >= 0 )
                                  {
                                    v815 = 0;
                                    v816 = (int)v1291;
                                  }
                                  if ( (int)v1283 >= 0 )
                                  {
                                    v817 = 0;
                                  }
                                  else
                                  {
                                    v817 = -(int)v1283;
                                    v814 = 0;
                                  }
                                  v818 = DWORD2(v1387) - v815;
                                  if ( DWORD2(v1387) - v815 >= (int)v1276 - v816 )
                                    v818 = (_DWORD)v1276 - v816;
                                  LODWORD(v1287) = v818;
                                  v819 = HIDWORD(v1387) - v817;
                                  if ( HIDWORD(v1387) - v817 >= (int)v1278 - v814 )
                                    v819 = (_DWORD)v1278 - v814;
                                  LODWORD(v1291) = v819;
                                  if ( v818 > 0 && v819 > 0 )
                                  {
                                    v820 = (int)v1276;
                                    v821 = v1292;
                                    v822 = v1287;
                                    LODWORD(v1285) = 0;
                                    v823 = &lpModuleName[2 * v815 + 2 * (__int64)(DWORD2(v1387) * v817)];
                                    psz = v823;
                                    v824 = pcchLength + 4 * (v816 + (__int64)((int)v1276 * v814));
                                    LODWORD(v1276) = (unsigned int)v1292 >> 8;
                                    LODWORD(v1283) = WORD1(v1292);
                                    v1303 = 4LL * SDWORD2(v1387);
                                    v1292 = 4 * v820;
                                    pcchLength = v824;
                                    do
                                    {
                                      v825 = (char)v1276;
                                      v826 = 0;
                                      v827 = (char)v1283;
                                      v828 = v823;
                                      LODWORD(v1278) = 0;
                                      v829 = (_BYTE *)v824;
                                      lpModuleName = v823;
                                      do
                                      {
                                        v830 = ~(unsigned __int8)((*(unsigned __int8 *)v828
                                                                 + *((unsigned __int8 *)v828 + 2)
                                                                 + 2 * (unsigned int)*((unsigned __int8 *)v828 + 1)) >> 2);
                                        if ( (unsigned __int8)((*(unsigned __int8 *)v828
                                                              + *((unsigned __int8 *)v828 + 2)
                                                              + 2 * (unsigned int)*((unsigned __int8 *)v828 + 1)) >> 2) != 0xFF )
                                        {
                                          v831 = (unsigned __int8)v829[2];
                                          v832 = v830;
                                          v833 = (int)((unsigned __int64)(2155905153LL * v830 * (v821 - v831)) >> 32) >> 7;
                                          v829[2] = v831 + (v833 < 0) + v833;
                                          v829[1] -= v832 * (v825 - v829[1]);
                                          *v829 -= v832 * (v827 - *v829);
                                          v834 = (unsigned __int8)v829[3];
                                          v835 = v832 * (255 - v834);
                                          v826 = (int)v1278;
                                          LOBYTE(v833) = v834 + v835 / 255;
                                          v828 = lpModuleName;
                                          v829[3] = v833;
                                        }
                                        ++v826;
                                        v828 += 2;
                                        LODWORD(v1278) = v826;
                                        v829 += 4;
                                        lpModuleName = v828;
                                      }
                                      while ( v826 < v822 );
                                      v823 = (STRSAFE_PCNZWCH)((char *)psz + v1303);
                                      v824 = v1292 + pcchLength;
                                      psz = (STRSAFE_PCNZWCH)((char *)psz + v1303);
                                      pcchLength += v1292;
                                      LODWORD(v1285) = (_DWORD)v1285 + 1;
                                    }
                                    while ( (int)v1285 < (int)v1291 );
                                    v83 = dwBytes;
                                    v797 = v1271;
                                    v812 = v1284;
                                  }
                                  ((void (__fastcall *)(SIZE_T))off_18003D398[0])(v1297);
                                  if ( (_QWORD)v1304 )
                                    ((void (__fastcall *)(size_t, _QWORD))off_18003D3D8[0])(v812, v1304);
                                }
                                else
                                {
                                  v805 = GetLastError();
                                  v807 = v805 < 0;
                                  if ( v805 > 0 )
                                  {
                                    v805 = (unsigned __int16)v805 | 0x80070000;
                                    v807 = v805 < 0;
                                  }
                                  if ( !v807 )
                                    v805 = -2147467259;
                                }
                                ((void (__fastcall *)(size_t))off_18003D390[0])(v1284);
                                if ( v805 < 0 )
                                  goto LABEL_1046;
                                v836 = 0;
                                v1371 = 0;
                                memset_0(v1372, 0, 0x64u);
                                v1383 = 0;
                                memset_0(v1384, 0, 0x64u);
                                psz = (STRSAFE_PCNZWCH)v1340;
                                memset(v1404, 0, 28);
                                v1403 = 0;
                                v1388 = 0;
                                if ( !v1340 )
                                  goto LABEL_1046;
                                v837 = v1289;
                                LODWORD(v1287) = v1338;
                                *(_QWORD *)&v1304 = v1343;
                                v838 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3B0[0])(v1289, 7);
                                if ( !v838 )
                                  goto LABEL_1045;
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18003D3C8[0])(
                                       v838,
                                       104,
                                       &v1371) )
                                {
                                  v1271 = v1372[0];
                                  pcchLength = v1373;
                                  v836 = 0;
                                  LODWORD(v1278) = v1372[1];
                                }
                                else
                                {
                                  pcchLength = 0;
                                  LODWORD(v1278) = 0;
                                  v1271 = 0;
                                }
                                v1284 = ((__int64 (__fastcall *)(LPVOID))off_18003D370[0])(v837);
                                if ( v1284 )
                                {
                                  LODWORD(v1293) = v1293 - HIDWORD(dwBytes);
                                  DWORD1(v1403) = v1293;
                                  DWORD2(v1403) = v797 - v1274;
                                  v1328 = 0;
                                  memset(v1404, 0, 28);
                                  LODWORD(v1403) = 40;
                                  HIDWORD(v1403) = 2097153;
                                  v839 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18003D378[0])(
                                           v1284,
                                           &v1403,
                                           0,
                                           &v1328,
                                           0,
                                           0);
                                  v1297 = v839;
                                  if ( v839 )
                                  {
                                    if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_18003D3C8[0])(
                                           v839,
                                           104,
                                           &v1383) )
                                    {
                                      lpModuleName = v1385;
                                    }
                                    else
                                    {
                                      lpModuleName = 0;
                                    }
                                    v841 = v1284;
                                    DWORD2(v1388) = v1293;
                                    HIDWORD(v1388) = v1274 - v797;
                                    ((void (__fastcall *)(size_t, SIZE_T))off_18003D3D8[0])(v1284, v1297);
                                    ((void (__fastcall *)(size_t, __int64))off_18003D3E0[0])(v841, 1);
                                    v842 = (void *)((__int64 (__fastcall *)(size_t, _QWORD))off_18003D3D8[0])(
                                                     v841,
                                                     v1304);
                                    v843 = off_18003D448[0];
                                    v1283 = v842;
                                    v844 = ((__int64 (__fastcall *)(_QWORD))off_18003D3D0[0])(0);
                                    ((void (__fastcall *)(size_t, __int128 *, __int64))v843)(v1284, &v1388, v844);
                                    v845 = v1284;
                                    ((void (__fastcall *)(size_t, STRSAFE_PCNZWCH, __int64, __int128 *, _DWORD, _QWORD))off_18003D438[0])(
                                      v1284,
                                      psz,
                                      0xFFFFFFFFLL,
                                      &v1388,
                                      (_DWORD)v1298,
                                      0);
                                    if ( v710 == 1 )
                                    {
                                      if ( (_DWORD)v1287 )
                                        v1272 = ((__int64 (__fastcall *)(__int64))off_18003D478[0])(8);
                                    }
                                    else
                                    {
                                      v1272 = -5723992;
                                    }
                                    v846 = 0;
                                    v847 = -HIDWORD(dwBytes);
                                    if ( (dwBytes & 0x8000000000000000uLL) == 0LL )
                                    {
                                      v847 = 0;
                                      v846 = HIDWORD(dwBytes);
                                    }
                                    if ( v797 >= 0 )
                                    {
                                      v848 = 0;
                                    }
                                    else
                                    {
                                      v848 = -v797;
                                      v797 = 0;
                                    }
                                    v849 = DWORD2(v1388) - v847;
                                    if ( DWORD2(v1388) - v847 >= (int)(v1271 - v846) )
                                      v849 = v1271 - v846;
                                    LODWORD(v1287) = v849;
                                    v850 = HIDWORD(v1388) - v848;
                                    if ( HIDWORD(v1388) - v848 >= (int)v1278 - v797 )
                                      v850 = (_DWORD)v1278 - v797;
                                    LODWORD(v1276) = v850;
                                    if ( v849 > 0 && v850 > 0 )
                                    {
                                      v851 = v1287;
                                      LODWORD(v1278) = 0;
                                      v852 = &lpModuleName[2 * v847 + 2 * (__int64)(DWORD2(v1388) * v848)];
                                      psz = v852;
                                      v853 = pcchLength + 4 * (v846 + (__int64)(int)(v1271 * v797));
                                      LODWORD(v1285) = (unsigned int)v1272 >> 8;
                                      LODWORD(v1274) = HIWORD(v1272);
                                      *(_QWORD *)&v1304 = 4LL * SDWORD2(v1388);
                                      v1303 = 4LL * (int)v1271;
                                      pcchLength = v853;
                                      do
                                      {
                                        v854 = (char)v1285;
                                        v855 = v852;
                                        v856 = v1274;
                                        v857 = (_BYTE *)v853;
                                        v858 = v1272;
                                        v859 = 0;
                                        lpModuleName = v852;
                                        v1271 = 0;
                                        do
                                        {
                                          v860 = ~(unsigned __int8)((*(unsigned __int8 *)v855
                                                                   + *((unsigned __int8 *)v855 + 2)
                                                                   + 2 * (unsigned int)*((unsigned __int8 *)v855 + 1)) >> 2);
                                          if ( (unsigned __int8)((*(unsigned __int8 *)v855
                                                                + *((unsigned __int8 *)v855 + 2)
                                                                + 2 * (unsigned int)*((unsigned __int8 *)v855 + 1)) >> 2) != 0xFF )
                                          {
                                            v861 = (unsigned __int8)v857[2];
                                            v862 = v860;
                                            v863 = (int)((unsigned __int64)(2155905153LL * v860 * (v858 - v861)) >> 32) >> 7;
                                            v857[2] = v861 + (v863 < 0) + v863;
                                            v857[1] -= v862 * (v854 - v857[1]);
                                            *v857 -= v862 * (v856 - *v857);
                                            v864 = (unsigned __int8)v857[3];
                                            v865 = v862 * (255 - v864);
                                            v859 = v1271;
                                            LOBYTE(v863) = v864 + v865 / 255;
                                            v855 = lpModuleName;
                                            v857[3] = v863;
                                          }
                                          ++v859;
                                          v855 += 2;
                                          v1271 = v859;
                                          v857 += 4;
                                          lpModuleName = v855;
                                        }
                                        while ( v859 < v851 );
                                        v852 = (STRSAFE_PCNZWCH)((char *)psz + v1304);
                                        v853 = v1303 + pcchLength;
                                        psz = (STRSAFE_PCNZWCH)((char *)psz + v1304);
                                        pcchLength += v1303;
                                        LODWORD(v1278) = (_DWORD)v1278 + 1;
                                      }
                                      while ( (int)v1278 < (int)v1276 );
                                      v83 = dwBytes;
                                      v845 = v1284;
                                    }
                                    ((void (__fastcall *)(SIZE_T))off_18003D398[0])(v1297);
                                    if ( v1283 )
                                      ((void (__fastcall *)(size_t, void *))off_18003D3D8[0])(v845, v1283);
                                    v837 = v1289;
                                  }
                                  else
                                  {
                                    v836 = GetLastError();
                                    v840 = v836 < 0;
                                    if ( v836 > 0 )
                                    {
                                      v836 = (unsigned __int16)v836 | 0x80070000;
                                      v840 = v836 < 0;
                                    }
                                    if ( !v840 )
                                      v836 = -2147467259;
                                  }
                                  ((void (__fastcall *)(size_t))off_18003D390[0])(v1284);
                                  if ( v836 >= 0 )
                                  {
                                    v333 = v710 == 1;
                                    v775 = v1279;
                                    if ( v333 )
                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, int))off_18003D360[0])(
                                        v1279,
                                        (unsigned int)v1346,
                                        (unsigned int)v1347,
                                        (unsigned int)v1288,
                                        v1301,
                                        v837,
                                        0,
                                        0,
                                        13369376);
                                    else
                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))off_18003D3A0[0])(
                                        v1279,
                                        (unsigned int)v1309,
                                        DWORD1(v1309),
                                        (unsigned int)v1288,
                                        v1301,
                                        v837,
                                        0,
                                        0,
                                        (_DWORD)v1288,
                                        v1301,
                                        (_DWORD)v1299);
                                    v774 = v1275;
                                    goto LABEL_1133;
                                  }
                                }
                                else
                                {
LABEL_1045:
                                  GetLastError();
                                }
                              }
LABEL_1046:
                              v774 = v1275;
                              goto LABEL_1047;
                            }
                          }
                          else
                          {
                            v704 = 0;
                            v710 = v471 & 0xF;
                            v709 = v710;
                          }
                          if ( v709 != 1 )
                            goto LABEL_906;
                          goto LABEL_904;
                        }
                        v587 = 0;
                        pcchLength = 0;
                        lpModuleName = 0;
                        LODWORD(v1274) = 0;
                        v1320 = 0;
                        v1284 = 0;
                        v588 = 0;
                        Size = 0;
                        memset(v1335, 0, sizeof(v1335));
                        v1305 = 0;
                        v1287 = 0;
                        v1311 = 0;
                        if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_18003D400[0])(
                                8,
                                &v1305,
                                0,
                                &v1311) )
                        {
                          v587 = GetLastError();
                          v589 = v587 < 0;
                          if ( v587 > 0 )
                          {
                            v587 = (unsigned __int16)v587 | 0x80070000;
                            v589 = v587 < 0;
                          }
                          if ( !v589 )
                            v587 = -2147467259;
                          goto LABEL_707;
                        }
                        v590 = MemoryAlloc(2LL * v1311);
                        SP<unsigned long,SP_MEM<unsigned long>>::operator=(&Size, v590);
                        v591 = Size;
                        if ( Size )
                        {
                          v592 = MemoryAlloc(4LL * (v1305 + 1));
                          SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1287, v592);
                          v593 = (_DWORD *)v1287;
                          if ( v1287 )
                          {
                            if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, SIZE_T, unsigned int *))off_18003D400[0])(
                                   8,
                                   &v1305,
                                   v591,
                                   &v1311) )
                            {
                              if ( v1305 )
                              {
                                for ( i5 = 0; i5 < v1305; ++i5 )
                                {
                                  *v593 = ((__int64 (__fastcall *)(SIZE_T, _QWORD))off_18003D410[0])(v591, 0);
                                  v596 = -1;
                                  do
                                    ++v596;
                                  while ( *(_WORD *)(v591 + 2 * v596) );
                                  ++v593;
                                  v591 += 2 * v596 + 2;
                                }
                                LOBYTE(v471) = v1292;
                              }
                              v120 = v1287;
                              *v593 = 1033;
                              v588 = v1305 + 1;
                              v1287 = 0;
                              lpModuleName = (LPCWSTR)v120;
LABEL_707:
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1287);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Size);
                              if ( v587 < 0 )
                              {
                                Size = 0;
                                psz = 0;
                                pcchLength = 0;
                                goto LABEL_773;
                              }
                              v597 = 0;
                              v598 = 0;
                              LODWORD(v1288) = 0;
                              if ( v588 )
                              {
                                while ( 2 )
                                {
                                  for ( i6 = 0; i6 < 0x26; ++i6 )
                                  {
                                    if ( *(_DWORD *)(v120 + 4LL * v598) == dword_180034880[i6] )
                                    {
                                      v597 = i6;
                                      LODWORD(v1288) = i6;
                                      goto LABEL_715;
                                    }
                                  }
                                  if ( ++v598 < v588 )
                                    continue;
                                  break;
                                }
                                v597 = 0;
                              }
LABEL_715:
                              v600 = v597;
                              LODWORD(v1276) = 0;
                              v601 = (unsigned int)dword_180034880[v597];
                              memset(v1408, 0, sizeof(v1408));
                              if ( ((unsigned int (__fastcall *)(__int64, _BYTE *, __int64))off_18003D408[0])(
                                     v601,
                                     v1428,
                                     85)
                                && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_18003D3F0[0])(
                                     v1428,
                                     88,
                                     v1408,
                                     16) > 0 )
                              {
                                LODWORD(v1276) = (HIDWORD(v1408[0]) >> 27) & 1;
                              }
                              memset_0(v1336, 0, 0x98u);
                              v602 = L"Segoe UI Light";
                              for ( i7 = 0; i7 != 19; ++i7 )
                              {
                                v1336[i7] = v602;
                                v604 = -1;
                                do
                                  ++v604;
                                while ( v602[v604] );
                                v602 += v604 + 1;
                              }
                              Size = v1336[*((unsigned __int8 *)qword_180034920 + 3 * v600)];
                              psz = (STRSAFE_PCNZWCH)v1336[*((unsigned __int8 *)qword_180034920 + 3 * v600 + 1)];
                              pcchLength = v1336[*((unsigned __int8 *)qword_180034920 + 3 * v600 + 2)];
                              v605 = (char *)MemoryAlloc(0x1C90u);
                              v606 = v605;
                              if ( !v605 )
                              {
                                v587 = -2147024882;
LABEL_773:
                                v645 = 0;
LABEL_774:
                                v656 = (void **)v1289;
                                goto LABEL_775;
                              }
                              v607 = qword_180032BE0;
                              v608 = v605;
                              v609 = 0;
                              v610 = -1;
                              v611 = 0;
                              v612 = 0;
                              v613 = 914;
                              do
                              {
                                v614 = *((unsigned __int8 *)v607 + 1);
                                v615 = *(unsigned __int8 *)v607;
                                v616 = *((unsigned __int8 *)v607++ + 4);
                                v617 = *((unsigned __int8 *)v607 - 5)
                                     | ((*((unsigned __int8 *)v607 - 6) | ((v614 | (v615 << 8)) << 8)) << 8);
                                v618 = v612 ^ v617;
                                v619 = *((unsigned __int8 *)v607 - 1)
                                     | ((*((unsigned __int8 *)v607 - 2)
                                       | ((*((unsigned __int8 *)v607 - 3) | (v616 << 8)) << 8)) << 8);
                                v620 = v612 ^ v617 ^ v611 ^ v619 ^ 0xAC987321;
                                v621 = v618 ^ (__ROR4__(v620, 22) + 4991 * __ROR4__(v620 + 1419157410, 27));
                                v622 = v620 ^ (43881 * __ROR4__(v621 + 133239679, 9) - __ROR4__(v621, 30));
                                v623 = v621 ^ (24670 * v622 - (v622 >> 13) - 123127970);
                                v624 = v622 ^ (2033 * __ROR4__(v623 ^ 0xAB69, 26) - __ROR4__(v623, 30));
                                v625 = v623 ^ (133239679 - (v624 ^ 0xAB69605E));
                                v626 = v624 ^ (43881 * (v625 ^ 0x137F)) ^ __ROR4__(v625, 6);
                                v627 = v625 ^ (__ROR4__(v626, 30) + 24670 * __ROR4__(v626 + 133239679, 15));
                                v628 = v626 ^ (2033 * __ROR4__(v627 + 1419157410, 14) - __ROR4__(v627, 24));
                                v629 = v627 ^ __ROR4__(v628, 10) ^ (4991 * __ROR4__(v628 ^ 0xAB69605E, 12));
                                v630 = v628 ^ (v629 >> 10) ^ (43881 * (v629 ^ 0x7F1));
                                v631 = v629 ^ (2033 * (__ROR4__(~v630, 5) + 24670));
                                v632 = v631
                                     ^ (((v630 ^ (v631 - 2033) ^ 0xAB69605E) >> 2)
                                      + 4991 * __ROR4__(v630 ^ (v631 - 2033) ^ 0xAB6967AF, 30));
                                v633 = v630
                                     ^ (v631 - 2033)
                                     ^ 0xAB69605E
                                     ^ (__ROR4__(v632, 25) + 43881 * __ROR4__(v632 - 133239679, 6));
                                v634 = v632 ^ (24670 * (v633 ^ 0x137F) + __ROR4__(v633, 9));
                                v635 = v633 ^ (__ROR4__(v634, 25) + 2033 * __ROR4__(v634 ^ 0xAB69, 27));
                                v636 = v634 ^ v635 ^ 0xAC987321;
                                v637 = v635 ^ (4991 * __ROR4__(v636, 3) - 219010071);
                                v638 = v636 ^ (24670 * __ROR4__(v637 - 133239679, 1) - __ROR4__(v637, 6));
                                v639 = v637 ^ (__ROR4__(v638, 18) + 2033 * __ROR4__(v638 - 1419157410, 29));
                                v640 = v638 ^ (4991 * __ROR4__(v639 - 1419157410, 17) - __ROR4__(v639, 14));
                                v641 = v639 ^ (v640 >> 3) ^ (43881 * (v640 ^ 0x605E));
                                v642 = __ROR4__(v641, 30);
                                v611 = v610 ^ v641;
                                v610 = v619;
                                v612 = v609
                                     ^ v640
                                     ^ v642
                                     ^ (24670 * __ROR4__(v639 ^ (v640 >> 3) ^ (43881 * (v640 ^ 0x605E)) ^ 0x7F1137F, 28));
                                v609 = v617;
                                v608[3] = v612;
                                v608[7] = v611;
                                v608[2] = __ROR4__(v612, 8);
                                v608[6] = __ROR4__(v611, 8);
                                v608[1] = __ROR4__(v612, 16);
                                v608[5] = __ROR4__(v611, 16);
                                *v608 = __ROR4__(v612, 24);
                                v608[4] = __ROR4__(v611, 24);
                                v608 += 8;
                                --v613;
                              }
                              while ( v613 );
                              LOBYTE(v471) = v1292;
                              v643 = 0;
                              v644 = 0;
                              v645 = 7312;
                              do
                              {
                                v646 = (__m128)_mm_loadu_si128((const __m128i *)&v606[v643]);
                                v643 += 16LL;
                                v647 = _mm_xor_ps(v646, v644);
                                v644 = v647;
                              }
                              while ( v643 < 0x1C90 );
                              v648 = _mm_xor_ps(v647, (__m128)_mm_srli_si128((__m128i)v647, 8));
                              v649 = _mm_xor_ps(v648, (__m128)_mm_srli_si128((__m128i)v648, 4));
                              v650 = _mm_xor_ps(v649, (__m128)_mm_srli_si128((__m128i)v649, 2));
                              if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                 v650,
                                                                                 (__m128)_mm_srli_si128(
                                                                                           (__m128i)v650,
                                                                                           1))) != 127 )
                              {
                                MemoryFree(v606);
                                v587 = -1073425151;
                                goto LABEL_773;
                              }
                              v651 = (int)v1288;
                              v587 = 0;
                              v1320 = v606;
                              v652 = 0;
                              v1310 = 7312;
                              do
                              {
                                for ( i8 = 0; i8 < 0x26; ++i8 )
                                {
                                  if ( v651 == i8 )
                                    *((_QWORD *)v1335 + v652) = v606;
                                  v654 = -1;
                                  do
                                    ++v654;
                                  while ( v606[v654] );
                                  v606 += v654 + 1;
                                }
                                ++v652;
                              }
                              while ( v652 < 6 );
                              v655 = MemoryAlloc(0x18u);
                              SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1284, v655);
                              v656 = (void **)v1284;
                              if ( v1284 )
                              {
                                v657 = 0;
                                *(_OWORD *)v1284 = 0;
                                v656[2] = 0;
                                while ( 2 )
                                {
                                  LODWORD(v1274) = v657;
                                  if ( v657 >= 3 )
                                  {
                                    v645 = v1310;
                                    v1337 = (int)v1276;
                                    v1284 = 0;
                                    v1297 = (SIZE_T)v656;
LABEL_775:
                                    v669 = v1320;
                                    if ( v1320 && v645 )
                                    {
                                      do
                                      {
                                        *v669++ = 0;
                                        --v645;
                                      }
                                      while ( v645 );
                                    }
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1284);
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1320);
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&lpModuleName);
                                    if ( v587 < 0 )
                                      goto LABEL_882;
                                    v1339 = *v656;
                                    v1340 = v656[1];
                                    v1341 = v656[2];
                                    v1333 = 0;
                                    LODWORD(v1333) = 16;
                                    v120 = 0;
                                    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_18003D4C8)(
                                                          66,
                                                          0,
                                                          &v1333,
                                                          0) )
                                    {
                                      v670 = GetLastError();
                                      v587 = v670;
                                      if ( v670 > 0 )
                                        v587 = (unsigned __int16)v670 | 0x80070000;
                                      v1338 = 0;
                                      if ( v587 >= 0 )
                                        v587 = -2147467259;
                                      goto LABEL_883;
                                    }
                                    v671 = v471 & 0xF;
                                    v1338 = BYTE4(v1333) & 1;
                                    LODWORD(v1298) = 42;
                                    if ( v671 == 1 )
                                    {
                                      LODWORD(v1292) = 42;
                                    }
                                    else
                                    {
                                      if ( (v471 & 0xF) != 2 )
                                      {
                                        if ( (v471 & 0xF) == 3 )
                                        {
                                          LODWORD(v1292) = 225;
                                          LODWORD(v1293) = 225;
                                        }
                                        else
                                        {
                                          LODWORD(v1292) = 0;
                                          LODWORD(v1293) = 0;
                                        }
                                        goto LABEL_793;
                                      }
                                      LODWORD(v1292) = 15;
                                    }
                                    LODWORD(v1293) = 11;
LABEL_793:
                                    memset_0(v1418, 0, 0xDCu);
                                    v1419 = 220;
                                    if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_18003D440[0])(
                                           0,
                                           0xFFFFFFFFLL,
                                           v1418) )
                                    {
                                      v672 = v1420;
                                      LODWORD(v120) = v1421;
                                      LODWORD(v1274) = v1422;
                                      if ( v1420 < 0x60u )
                                        v672 = 96;
                                    }
                                    else
                                    {
                                      LODWORD(v1274) = 0;
                                      v672 = 96;
                                    }
                                    HIDWORD(dwBytes) = v672;
                                    v673 = (const WCHAR *)pcchLength;
                                    if ( v671 == 1 )
                                      v673 = (const WCHAR *)Size;
                                    lpModuleName = v673;
                                    memset_0(v1409, 0, 0x5Cu);
                                    v1303 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D458[0])(
                                              0,
                                              0,
                                              1027);
                                    if ( !v1303 )
                                      goto LABEL_848;
                                    v674 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                             (unsigned int)v1292,
                                             v672,
                                             72);
                                    v1409[4] = 400;
                                    v1409[0] = -v674;
                                    v1410 = 5;
                                    StringCchCopyW(v1411, 0x20u, lpModuleName);
                                    v675 = ((__int64 (__fastcall *)(_DWORD *))off_18003D380[0])(v1409);
                                    if ( v675 )
                                    {
                                      v587 = 0;
                                      v1342 = (const wchar_t *)v675;
                                    }
                                    else
                                    {
                                      v587 = GetLastError();
                                      v676 = v587 < 0;
                                      if ( v587 > 0 )
                                      {
                                        v587 = (unsigned __int16)v587 | 0x80070000;
                                        v676 = v587 < 0;
                                      }
                                      if ( !v676 )
                                        v587 = -2147467259;
                                    }
                                    ((void (__fastcall *)(_QWORD, unsigned __int64))off_18003D4C0[0])(0, v1303);
                                    if ( v587 < 0 )
                                      goto LABEL_882;
                                    v677 = (const unsigned __int16 *)pcchLength;
                                    if ( v671 == 1 )
                                      v677 = (const unsigned __int16 *)Size;
                                    memset_0(v1412, 0, 0x5Cu);
                                    lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D458[0])(
                                                              0,
                                                              0,
                                                              1027);
                                    if ( !lpModuleName )
                                      goto LABEL_848;
                                    v678 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                             (unsigned int)v1293,
                                             HIDWORD(dwBytes),
                                             72);
                                    v1412[4] = 400;
                                    v1412[0] = -v678;
                                    v1413 = 5;
                                    StringCchCopyW(v1414, 0x20u, v677);
                                    v679 = ((__int64 (__fastcall *)(_DWORD *))off_18003D380[0])(v1412);
                                    if ( v679 )
                                    {
                                      v587 = 0;
                                      v1343 = (const wchar_t *)v679;
                                    }
                                    else
                                    {
                                      v587 = GetLastError();
                                      v680 = v587 < 0;
                                      if ( v587 > 0 )
                                      {
                                        v587 = (unsigned __int16)v587 | 0x80070000;
                                        v680 = v587 < 0;
                                      }
                                      if ( !v680 )
                                        v587 = -2147467259;
                                    }
                                    ((void (__fastcall *)(_QWORD, LPCWSTR))off_18003D4C0[0])(0, lpModuleName);
                                    if ( v587 < 0 )
                                      goto LABEL_882;
                                    if ( v671 != 1 )
                                    {
                                      if ( v671 == 2 )
                                      {
                                        LODWORD(v120) = (int)v120 / 4;
                                        goto LABEL_825;
                                      }
                                      if ( v671 != 3 )
                                      {
                                        LODWORD(v120) = 0;
LABEL_825:
                                        v681 = 0;
                                        goto LABEL_827;
                                      }
                                    }
                                    v681 = v1274;
LABEL_827:
                                    *((_QWORD *)&v1309 + 1) = __PAIR64__(v681, v120);
                                    if ( v671 == 1 )
                                    {
                                      v682 = 150;
                                      LODWORD(v1292) = 32;
                                    }
                                    else
                                    {
                                      v682 = 0;
                                      if ( (unsigned int)(v671 - 2) < 2 )
                                      {
                                        LODWORD(v1298) = 0;
                                        LODWORD(v1292) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v1292) = 0;
                                        LODWORD(v1298) = 0;
                                      }
                                    }
                                    LODWORD(v1288) = v682;
                                    v683 = v120 - v682;
                                    v684 = v1339;
                                    v1352 = v683;
                                    v1348 = v683;
                                    lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(LPVOID, const wchar_t *, _QWORD))off_18003D3D8[0])(
                                                              v1275,
                                                              v1342,
                                                              0);
                                    v1271 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, int *, int, _QWORD))off_18003D438[0])(
                                              v1275,
                                              v684,
                                              0xFFFFFFFFLL,
                                              &v1346,
                                              3152,
                                              0);
                                    v587 = v1271 != 0 ? 0 : 0x80004005;
                                    if ( lpModuleName )
                                      ((void (__fastcall *)(LPVOID, LPCWSTR))off_18003D3D8[0])(v1275, lpModuleName);
                                    if ( v1271 )
                                    {
                                      v685 = v1340;
                                      lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(LPVOID, const wchar_t *))off_18003D3D8[0])(
                                                                v1275,
                                                                v1343);
                                      v1271 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, int *, int, _QWORD))off_18003D438[0])(
                                                v1275,
                                                v685,
                                                0xFFFFFFFFLL,
                                                &v1350,
                                                3152,
                                                0);
                                      v587 = v1271 != 0 ? 0 : 0x80004005;
                                      if ( lpModuleName )
                                        ((void (__fastcall *)(LPVOID, LPCWSTR))off_18003D3D8[0])(v1275, lpModuleName);
                                      if ( v1271 )
                                      {
                                        if ( v671 == 2 || v671 == 3 )
                                        {
                                          v683 = v1352;
                                          if ( v1348 > v1352 )
                                            v683 = v1348;
                                        }
                                        v587 = 0;
                                        if ( v1337 )
                                        {
                                          ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18003D4B0)(
                                            &v1346,
                                            v683 - v1348,
                                            (unsigned int)v1298);
                                          v686 = v683 - v1352;
                                        }
                                        else
                                        {
                                          ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18003D4B0)(
                                            &v1346,
                                            (unsigned int)v1288,
                                            (unsigned int)v1298);
                                          v686 = (unsigned int)v1288;
                                        }
                                        ((void (__fastcall *)(int *, __int64, _QWORD))off_18003D4B0)(
                                          &v1350,
                                          v686,
                                          (unsigned int)(v1349 + v1292));
                                        if ( (unsigned int)(v671 - 2) <= 1 )
                                        {
                                          *((_QWORD *)&v1309 + 1) = __PAIR64__(v1353, v683);
                                          v1345 = -5723992;
                                          goto LABEL_868;
                                        }
                                        if ( v671 != 1 )
                                          goto LABEL_868;
                                        v1345 = 0xFFFFFF;
                                        memset_0(v1415, 0, 0x5Cu);
                                        lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D458[0])(
                                                                  0,
                                                                  0,
                                                                  1027);
                                        if ( !lpModuleName )
                                        {
LABEL_848:
                                          v687 = GetLastError();
                                          v120 = 0;
                                          v587 = v687;
                                          if ( v687 > 0 )
                                            v587 = (unsigned __int16)v687 | 0x80070000;
                                          if ( v587 >= 0 )
                                            v587 = -2147467259;
                                          goto LABEL_883;
                                        }
                                        v688 = ((__int64 (__fastcall *)(__int64, _QWORD))off_18003D418[0])(
                                                 11,
                                                 HIDWORD(dwBytes));
                                        v1415[4] = 400;
                                        v1415[0] = -v688;
                                        v1416 = 5;
                                        StringCchCopyW(v1417, 0x20u, psz);
                                        v689 = ((__int64 (__fastcall *)(_DWORD *))off_18003D380[0])(v1415);
                                        if ( v689 )
                                        {
                                          v1344 = v689;
                                        }
                                        else
                                        {
                                          v587 = GetLastError();
                                          v690 = v587 < 0;
                                          if ( v587 > 0 )
                                          {
                                            v587 = (unsigned __int16)v587 | 0x80070000;
                                            v690 = v587 < 0;
                                          }
                                          if ( !v690 )
                                            v587 = -2147467259;
                                        }
                                        ((void (__fastcall *)(_QWORD, LPCWSTR))off_18003D4C0[0])(0, lpModuleName);
                                        if ( v587 >= 0 )
                                        {
                                          v691 = v1341;
                                          v1356 = v683;
                                          v692 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18003D3D8[0])(
                                                   v1275,
                                                   v1344);
                                          v1271 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, unsigned int *, int, _QWORD))off_18003D438[0])(
                                                    v1275,
                                                    v691,
                                                    0xFFFFFFFFLL,
                                                    &v1354,
                                                    1120,
                                                    0);
                                          v587 = v1271 == 0 ? 0x80004005 : 0;
                                          if ( v692 )
                                            ((void (__fastcall *)(LPVOID, __int64))off_18003D3D8[0])(v1275, v692);
                                          v120 = 0;
                                          if ( !v1271 )
                                            goto LABEL_883;
                                          v693 = HIDWORD(dwBytes);
                                          v694 = v1356 + 24;
                                          v1357 = 32;
                                          if ( (int)(v1356 + 24) < 90 )
                                            v694 = 90;
                                          v1356 = v694;
                                          v1354 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                                    v1354,
                                                    HIDWORD(dwBytes),
                                                    96);
                                          v1355 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                                    v1355,
                                                    v693,
                                                    96);
                                          v1356 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                                    v1356,
                                                    v693,
                                                    96);
                                          v1357 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18003D418[0])(
                                                    v1357,
                                                    v693,
                                                    96);
                                          off_18003D4B0();
LABEL_868:
                                          v695 = HIDWORD(v1309);
                                          v696 = DWORD2(v1309);
                                          v697 = v671 - 1;
                                          if ( !v697 )
                                          {
                                            v120 = 0;
                                            *(_QWORD *)&v1309 = 0;
                                            goto LABEL_875;
                                          }
                                          v698 = v697 - 1;
                                          if ( v698 )
                                          {
                                            if ( v698 != 1 )
                                              goto LABEL_874;
                                            v1407 = 0;
                                            v1405 = 0;
                                            v1406 = 0;
                                            v699 = ((__int64 (__fastcall *)(_QWORD, __int64))off_18003D4A8[0])(0, 1);
                                            LODWORD(v1405) = 40;
                                            if ( !((unsigned int (__fastcall *)(__int64, __int128 *))off_18003D468[0])(
                                                    v699,
                                                    &v1405) )
                                              goto LABEL_874;
                                            ((void (__fastcall *)(_QWORD, char *))off_18003D4A0[0])(
                                              0,
                                              (char *)&v1406 + 4);
                                            ((void (__fastcall *)(_QWORD, char *))off_18003D4A0[0])(
                                              0,
                                              (char *)&v1406 + 12);
                                            v700 = 50 * (HIDWORD(v1406) - v696) / 100;
                                            v701 = 50 * (v1407 - v695);
                                          }
                                          else
                                          {
                                            v702 = v1337;
                                            v1396 = 0;
                                            v1394 = 0;
                                            v1395 = 0;
                                            v703 = ((__int64 (__fastcall *)(_QWORD, __int64))off_18003D4A8[0])(0, 1);
                                            LODWORD(v1394) = 40;
                                            if ( !((unsigned int (__fastcall *)(__int64, __int128 *))off_18003D468[0])(
                                                    v703,
                                                    &v1394) )
                                              goto LABEL_874;
                                            ((void (__fastcall *)(_QWORD, char *))off_18003D4A0[0])(
                                              0,
                                              (char *)&v1395 + 4);
                                            ((void (__fastcall *)(_QWORD, char *))off_18003D4A0[0])(
                                              0,
                                              (char *)&v1395 + 12);
                                            if ( v702 )
                                              v700 = DWORD1(v1395) + 5 * HIDWORD(v1395) / 100;
                                            else
                                              v700 = 95 * (HIDWORD(v1395) - v696) / 100;
                                            v701 = 95 * (v1396 - v695);
                                          }
                                          LODWORD(v1309) = v700;
                                          DWORD1(v1309) = v701 / 100;
LABEL_874:
                                          v120 = 0;
LABEL_875:
                                          v587 = 0;
LABEL_883:
                                          ((void (__fastcall *)(_QWORD, LPVOID))off_18003D4C0[0])(0, v1275);
                                          goto LABEL_884;
                                        }
                                      }
                                    }
LABEL_882:
                                    v120 = 0;
                                    goto LABEL_883;
                                  }
                                  v658 = 0;
                                  v1303 = v657;
                                  while ( 1 )
                                  {
                                    if ( v658 >= 6 )
                                      goto LABEL_753;
                                    if ( *((_WORD *)&v1277 + v657) == word_180034998[v658] )
                                      break;
                                    ++v658;
                                  }
                                  v659 = *((_QWORD *)v1335 + v658);
                                  v660 = -1;
                                  do
                                    ++v660;
                                  while ( *(_BYTE *)(v660 + v659) );
                                  v661 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_18003D420[0])(
                                           65001,
                                           0,
                                           v659,
                                           (unsigned int)(v660 + 1),
                                           0,
                                           0);
                                  v1271 = v661;
                                  if ( !v661 )
                                    goto LABEL_754;
                                  v662 = MemoryAlloc(2LL * v661);
                                  v656[v1303] = v662;
                                  if ( v662 )
                                  {
                                    v663 = -1;
                                    do
                                      ++v663;
                                    while ( *(_BYTE *)(v663 + v659) );
                                    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, _QWORD, void *, unsigned int))off_18003D420[0])(
                                           65001,
                                           0,
                                           v659,
                                           (unsigned int)(v663 + 1),
                                           v662,
                                           v1271) )
                                    {
LABEL_753:
                                      v657 = v1274 + 1;
                                      continue;
                                    }
LABEL_754:
                                    v664 = GetLastError();
                                    v587 = v664;
                                    if ( v664 > 0 )
                                      v587 = (unsigned __int16)v664 | 0x80070000;
                                    v645 = v1310;
                                    if ( v587 >= 0 )
                                      v587 = -2147467259;
                                    goto LABEL_761;
                                  }
                                  break;
                                }
                                v645 = v1310;
                              }
                              v587 = -2147024882;
LABEL_761:
                              if ( v656 )
                              {
                                for ( i9 = 0; i9 != 3; ++i9 )
                                {
                                  v666 = v656[i9];
                                  if ( v666 )
                                  {
                                    v667 = -1;
                                    do
                                      ++v667;
                                    while ( *(_WORD *)&v666[2 * v667] );
                                    for ( i10 = 2 * v667 + 2; i10; --i10 )
                                      *v666++ = 0;
                                    MemoryFree(v656[i9]);
                                  }
                                }
                                v645 = v1310;
                              }
                              goto LABEL_774;
                            }
                            v587 = GetLastError();
                            v594 = v587 < 0;
                            if ( v587 > 0 )
                            {
                              v587 = (unsigned __int16)v587 | 0x80070000;
                              v594 = v587 < 0;
                            }
                            v588 = v1274;
                            if ( !v594 )
                              v587 = -2147467259;
LABEL_706:
                            v120 = pcchLength;
                            goto LABEL_707;
                          }
                          v588 = v1274;
                        }
                        v587 = -2147024882;
                        goto LABEL_706;
                      }
                      LODWORD(v1288) = 0;
                      v572 = 0;
                      LODWORD(v1276) = 0;
                      *((_BYTE *)lpModuleName + 823) = 0;
                      memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                      lpModuleName = v569;
                      while ( *(_BYTE *)v569 )
                      {
                        v573 = -1;
                        do
                          ++v573;
                        while ( v569[v573] );
                        v574 = 3LL * (unsigned int)v120;
                        v575 = (HMODULE *)&qword_18003DEB0[3 * (unsigned int)v120];
                        v1275 = (LPVOID)v574;
                        if ( !GetModuleHandleExW(0, v569, v575) )
                        {
                          v572 = -1073741702;
                          break;
                        }
                        v576 = &v569[v573];
                        if ( *(_WORD *)*v575 == 23117
                          && (v578 = *((int *)*v575 + 15), (unsigned int)v578 < 0x10000000)
                          && (v579 = (char *)*v575 + v578, v579 >= (char *)*v575)
                          && *(_DWORD *)v579 == 17744 )
                        {
                          v577 = v1275;
                          if ( ((*((_WORD *)v579 + 12) - 267) & 0xFEFF) != 0 )
                          {
                            v572 = -1073741811;
                          }
                          else
                          {
                            v572 = 0;
                            *(__int64 *)((char *)&qword_18003DEB0[(_QWORD)v1275 + 1] + 4) = *((_QWORD *)v579 + 17);
                            LODWORD(qword_18003DEB0[(_QWORD)v577 + 1]) = *((_DWORD *)v579 + 20);
                          }
                        }
                        else
                        {
                          v577 = v1275;
                          v572 = -1073741701;
                        }
                        v580 = *(_DWORD *)(v576 + 1);
                        v581 = 0;
                        v1271 = v580;
                        v569 = v576 + 3;
                        while ( 1 )
                        {
                          LODWORD(v1274) = v581;
                          if ( v581 >= v580 )
                            break;
                          v582 = -1;
                          do
                            ++v582;
                          while ( *((_BYTE *)v569 + v582) );
                          if ( v572 >= 0 )
                          {
                            v583 = GetProcAddress((HMODULE)qword_18003DEB0[(_QWORD)v577], (LPCSTR)v569);
                            if ( !v583 )
                              goto LABEL_672;
                            off_18003D360[(unsigned int)v1288] = v583;
                            v581 = v1274;
                            v580 = v1271;
                          }
                          LODWORD(v1288) = (_DWORD)v1288 + 1;
                          v577 = v1275;
                          v569 = (const WCHAR *)((char *)v569 + v582 + 1);
                          ++v581;
                        }
                        LODWORD(v120) = (_DWORD)v1276 + 1;
                        LODWORD(v1276) = (_DWORD)v1276 + 1;
                      }
LABEL_672:
                      v584 = (WCHAR *)lpModuleName;
                      if ( lpModuleName )
                      {
                        v585 = GetProcessHeap();
                        HeapFree(v585, 0, v584);
                      }
                      v120 = 0;
                      if ( v572 < 0 )
                        goto LABEL_644;
                      v529 = dword_18003E488;
                    }
                    dword_18003E488 = v529 + 1;
                    goto LABEL_677;
                  }
                  LODWORD(v1288) = 0;
                  v515 = 0;
                  LODWORD(v1276) = 0;
                  *((_BYTE *)lpModuleName + 823) = 0;
                  memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                  lpModuleName = v510;
                  while ( *(_BYTE *)v510 )
                  {
                    v516 = -1;
                    do
                      ++v516;
                    while ( v510[v516] );
                    v517 = 3LL * (unsigned int)v120;
                    v518 = (HMODULE *)&qword_18003DEB0[3 * (unsigned int)v120];
                    v1275 = (LPVOID)v517;
                    if ( !GetModuleHandleExW(0, v510, v518) )
                    {
                      v515 = -1073741702;
                      break;
                    }
                    v519 = &v510[v516];
                    if ( *(_WORD *)*v518 == 23117
                      && (v521 = *((int *)*v518 + 15), (unsigned int)v521 < 0x10000000)
                      && (v522 = (char *)*v518 + v521, v522 >= (char *)*v518)
                      && *(_DWORD *)v522 == 17744 )
                    {
                      v520 = v1275;
                      if ( ((*((_WORD *)v522 + 12) - 267) & 0xFEFF) != 0 )
                      {
                        v515 = -1073741811;
                      }
                      else
                      {
                        v515 = 0;
                        *(__int64 *)((char *)&qword_18003DEB0[(_QWORD)v1275 + 1] + 4) = *((_QWORD *)v522 + 17);
                        LODWORD(qword_18003DEB0[(_QWORD)v520 + 1]) = *((_DWORD *)v522 + 20);
                      }
                    }
                    else
                    {
                      v520 = v1275;
                      v515 = -1073741701;
                    }
                    v523 = *(_DWORD *)(v519 + 1);
                    v524 = 0;
                    v1271 = v523;
                    v510 = v519 + 3;
                    while ( 1 )
                    {
                      LODWORD(v1274) = v524;
                      if ( v524 >= v523 )
                        break;
                      v525 = -1;
                      do
                        ++v525;
                      while ( *((_BYTE *)v510 + v525) );
                      if ( v515 >= 0 )
                      {
                        v526 = GetProcAddress((HMODULE)qword_18003DEB0[(_QWORD)v520], (LPCSTR)v510);
                        if ( !v526 )
                          goto LABEL_629;
                        off_18003D360[(unsigned int)v1288] = v526;
                        v524 = v1274;
                        v523 = v1271;
                      }
                      LODWORD(v1288) = (_DWORD)v1288 + 1;
                      v520 = v1275;
                      v510 = (const WCHAR *)((char *)v510 + v525 + 1);
                      ++v524;
                    }
                    LODWORD(v120) = (_DWORD)v1276 + 1;
                    LODWORD(v1276) = (_DWORD)v1276 + 1;
                  }
LABEL_629:
                  v527 = (WCHAR *)lpModuleName;
                  if ( lpModuleName )
                  {
                    v528 = GetProcessHeap();
                    HeapFree(v528, 0, v527);
                  }
                  v120 = 0;
                  if ( v515 < 0 )
                    goto LABEL_601;
                  v472 = dword_18003E488;
                }
                dword_18003E488 = v472 + 1;
                goto LABEL_634;
              }
              v1265 = v1271;
LABEL_1571:
              while ( _InterlockedCompareExchange(&dword_18003E48C, 1, 0) )
                ;
              v1266 = dword_18003E488;
              if ( dword_18003E488 > 0 )
              {
                --dword_18003E488;
                if ( v1266 == 1 )
                {
                  for ( i11 = 0; i11 != 4; ++i11 )
                  {
                    v1268 = (HMODULE)qword_18003DEB0[3 * i11];
                    if ( v1268 )
                      FreeLibrary(v1268);
                  }
                  memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
                  memcpy_0(off_18003D360, off_18002E370, 0x170u);
                }
              }
              _InterlockedExchange(&dword_18003E48C, 0);
              SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1303);
              if ( v83 >= 0 )
              {
                if ( v1265 == 4 )
                {
                  v2 = 0;
                  *v1329 = *v1321;
                  goto LABEL_1591;
                }
              }
              else
              {
                switch ( v83 )
                {
                  case -805306316:
                    v2 = -1073418222;
                    goto LABEL_1591;
                  case -805306139:
                  case -1073425151:
                    v2 = -1073418201;
                    goto LABEL_1591;
                  case -805306306:
                    v2 = -1073418200;
                    goto LABEL_1591;
                }
                v2 = v83;
                if ( v83 != -2147024774 )
                  goto LABEL_1591;
              }
              v2 = -1073418210;
              goto LABEL_1591;
            }
            *v81 = xmmword_18003DBE0;
            v81[1] = xmmword_18003DBF0;
            v81[2] = xmmword_18003DC00;
            v81[3] = xmmword_18003DC10;
            v81[4] = xmmword_18003DC20;
            v81[5] = xmmword_18003DC30;
            v81[6] = xmmword_18003DC40;
            v81[7] = xmmword_18003DC50;
            v81[8] = xmmword_18003DC60;
            v81[9] = xmmword_18003DC70;
            v85 = GetProcessHeap();
            v84 = HeapAlloc(v85, 8u, 8u);
            if ( !v84 )
            {
              LODWORD(dwBytes) = -1073741801;
              v84 = 0;
              goto LABEL_136;
            }
            *v84 = qword_18003DB20;
            lpModuleName = (LPCWSTR)__rdtsc();
            LODWORD(v1274) = 0;
            dwBytes = (unsigned int)RtlUIntAdd(4, 4, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v86 = RtlUIntAdd(0, (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v86 | 0x10000000;
            LODWORD(dwBytes) = v86 | 0x10000000;
            if ( v86 < 0 )
              goto LABEL_136;
            LODWORD(v1274) = v87;
            LODWORD(dwBytes) = RtlUIntAdd(v88, 160, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v89 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v91 | v89;
            LODWORD(dwBytes) = v91 | v89;
            if ( (v91 | v89) < 0 )
              goto LABEL_136;
            LODWORD(v1274) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v90, 8, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v92 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v94 | v92;
            LODWORD(dwBytes) = v94 | v92;
            if ( (v94 | v92) < 0 )
              goto LABEL_136;
            LODWORD(v1274) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v93, 8, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v95 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v97 | v95;
            LODWORD(dwBytes) = v97 | v95;
            if ( (v97 | v95) < 0 )
              goto LABEL_136;
            pcchLength = 0;
            if ( StringCchLengthW(psz, v96, &pcchLength) < 0 )
            {
              v83 = -1073741762;
LABEL_341:
              LODWORD(dwBytes) = v83;
              goto LABEL_136;
            }
            LODWORD(v1274) = v98;
            LODWORD(dwBytes) = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v99 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v99 | 0x10000000;
            LODWORD(dwBytes) = v99 | 0x10000000;
            if ( v99 < 0 )
              goto LABEL_136;
            LODWORD(v1274) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v100, v100, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v101 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v103 | v101;
            LODWORD(dwBytes) = v103 | v101;
            if ( (v103 | v101) < 0 )
              goto LABEL_136;
            LODWORD(v1274) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v102, v102, &v1274);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_136;
            v104 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
            v83 = v105 | v104;
            LODWORD(dwBytes) = v105 | v104;
            if ( (v105 | v104) < 0 )
              goto LABEL_136;
            HIDWORD(Src[0]) = HIDWORD(dwBytes);
            v106 = HIDWORD(dwBytes);
            v107 = GetProcessHeap();
            v108 = HeapAlloc(v107, 8u, v106);
            if ( !v108 )
            {
              v83 = -1073741801;
              goto LABEL_341;
            }
            LODWORD(v1296) = 0;
            v1295 = 0;
            v1272 = 0;
            Src[1] = v108;
            LODWORD(Src[0]) = 0;
            pcchLength = (size_t)v108;
            LODWORD(dwBytes) = RtlULongLongAdd(v108, 4, &v1296);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_132;
            if ( v108 + 2 <= (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
            {
              v112 = v1296;
              *v108 = v109;
              v113 = v109;
              *v112 = v110;
              v114 = LODWORD(Src[0]) + 1;
              LODWORD(v1296) = 0;
              ++LODWORD(Src[0]);
              v1295 = 0;
              if ( v82 )
              {
                if ( !v111 )
                  goto LABEL_130;
              }
              else if ( v111 )
              {
LABEL_130:
                v83 = -1073741811;
LABEL_131:
                LODWORD(dwBytes) = v83;
LABEL_132:
                v79 = v1299;
                goto LABEL_133;
              }
              v122 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i12 = 0; i12 < v114; ++i12 )
                {
                  v124 = *v122;
                  LODWORD(v1274) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd(4, v124, &v1274);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  LODWORD(dwBytes) = RtlULongLongAdd(v125, (unsigned int)v1274, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  v122 = (unsigned int *)pcchLength;
                }
                v113 = 4;
                LODWORD(dwBytes) = RtlULongLongAdd(v122, 4, &v1296);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                if ( (char *)v126 + v127 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
                  goto LABEL_163;
                *v126 = v127;
                if ( v82 )
                  memcpy_0(v1296, v82, v127);
              }
              else
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, v111, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
              }
              v128 = LODWORD(Src[0]) + 1;
              LODWORD(v1296) = 0;
              ++LODWORD(Src[0]);
              v1295 = 0;
              v129 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i13 = 0; i13 < v128; i13 = v133 + 1 )
                {
                  v131 = *v129;
                  LODWORD(v1274) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, v131, &v1274);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  LODWORD(dwBytes) = RtlULongLongAdd(v132, (unsigned int)v1274, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  v129 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v129, v113, &v1296);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                if ( v134 + 3 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_163;
                *v134 = 8;
                memcpy_0(v1296, v84, 8u);
              }
              else
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, 8, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
              }
              v135 = (unsigned int *)Src[1];
              v136 = LODWORD(Src[0]) + 1;
              LODWORD(v1296) = 0;
              ++LODWORD(Src[0]);
              v1295 = 0;
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i14 = 0; i14 < v136; i14 = v141 + 1 )
                {
                  v139 = *v135;
                  LODWORD(v1274) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, v139, &v1274);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  LODWORD(dwBytes) = RtlULongLongAdd(v140, (unsigned int)v1274, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  v135 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v135, v113, &v1296);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                if ( v142 + 3 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_163;
                v143 = (LPCWSTR *)v1296;
                v144 = lpModuleName;
                *v142 = 8;
                *v143 = v144;
              }
              else
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, 8, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
              }
              v1284 = 0;
              v145 = psz;
              ++LODWORD(Src[0]);
              if ( StringCchLengthW(psz, v137, &v1284) < 0 )
              {
                v83 = -1073741762;
                goto LABEL_131;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v1284, 1, &v1284);
              v83 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_132;
              LODWORD(v1296) = 0;
              v1295 = 0;
              if ( !(2 * (_DWORD)v1284) )
                goto LABEL_130;
              v147 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i15 = 0; i15 < v146; ++i15 )
                {
                  v149 = *v147;
                  LODWORD(v1274) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd(4, v149, &v1274);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  LODWORD(dwBytes) = RtlULongLongAdd(v150, (unsigned int)v1274, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  v147 = (unsigned int *)pcchLength;
                }
                v113 = 4;
                LODWORD(dwBytes) = RtlULongLongAdd(v147, 4, &v1296);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                if ( (char *)v151 + v152 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
                  goto LABEL_163;
                v153 = v1296;
                *v151 = v152;
                memcpy_0(v153, v145, (unsigned int)v152);
              }
              else
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)(2 * v1284), &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
              }
              v154 = (unsigned int *)Src[1];
              v155 = LODWORD(Src[0]) + 1;
              LODWORD(v1296) = 0;
              ++LODWORD(Src[0]);
              v1295 = 0;
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i16 = 0; i16 < v155; i16 = v159 + 1 )
                {
                  v157 = *v154;
                  LODWORD(v1274) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, v157, &v1274);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  LODWORD(dwBytes) = RtlULongLongAdd(v158, (unsigned int)v1274, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_132;
                  v154 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v154, v113, &v1296);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                if ( v160 + 2 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_163;
                v161 = v1296;
                v162 = v1301;
                *v160 = v113;
                *v161 = v162;
              }
              else
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
              }
              v163 = (unsigned int *)Src[1];
              v164 = LODWORD(Src[0]) + 1;
              LODWORD(v1296) = 0;
              ++LODWORD(Src[0]);
              v1295 = 0;
              if ( !Src[1] )
              {
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1274, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
LABEL_230:
                ++LODWORD(Src[0]);
                LODWORD(v1274) = 0;
                v83 = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                HIDWORD(dwBytes) = v1274;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd(v171, 8, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v83 = RtlUIntAdd(v172, (unsigned int)v1274, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, (unsigned int)v113, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1274, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_132;
                v173 = HIDWORD(dwBytes);
                LODWORD(v1292) = 0;
                v1277 = 0;
                pcchLength = __rdtsc();
                v1307 = 8;
                LODWORD(v1278) = 0;
                v175 = RtlUIntAdd(8, HIDWORD(Src[0]), &v1307);
                if ( v175 < 0 )
                {
                  v1275 = v84;
                  v1289 = v82;
                }
                else
                {
                  v176 = (v1307 + 7) & 0xFFFFFFF8;
                  if ( v176 < v1307 )
                  {
                    v83 = -805306219;
LABEL_244:
                    LODWORD(dwBytes) = v83;
LABEL_245:
                    v79 = v1299;
                    goto LABEL_136;
                  }
                  v1307 = (v1307 + 7) & 0xFFFFFFF8;
                  v177 = v176;
                  v178 = GetProcessHeap();
                  v179 = HeapAlloc(v178, 8u, v177);
                  if ( !v179 )
                  {
                    v83 = -805306345;
                    LODWORD(dwBytes) = -805306345;
LABEL_338:
                    if ( v83 < 0 )
                      goto LABEL_245;
                    v79 = v1299;
                    if ( !(_DWORD)v1292 )
                    {
LABEL_340:
                      v83 = -1073425151;
                      goto LABEL_341;
                    }
                    if ( !v1299 )
                      goto LABEL_548;
                    pcchLength = (size_t)v1299;
                    LODWORD(dwBytes) = RtlULongLongAdd(v1299, 4, &pcchLength);
                    v83 = dwBytes;
                    if ( (dwBytes & 0x80000000) != 0LL )
                      goto LABEL_133;
                    v434 = (int *)pcchLength;
                    if ( !*v79 )
                      v434 = 0;
                    if ( *v79 == (_DWORD)v433 )
                    {
                      v83 = *v434;
                      LODWORD(dwBytes) = v83;
                      if ( v83 == -805306333 )
                      {
                        v1272 = -2147024774;
                      }
                      else
                      {
                        v1272 = v83;
                        if ( v83 != -2147024774 && v83 < 0 )
                          goto LABEL_136;
                      }
                      if ( v431 != 6 )
                        goto LABEL_340;
                      v1279 = v430;
                      for ( i17 = 0; i17 < v432; i17 = v437 + 1 )
                      {
                        LODWORD(dwBytes) = RtlULongLongAdd(v430, v433, &v1279);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_133;
                        LODWORD(dwBytes) = RtlULongLongAdd(v1279, v436, &v1279);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_133;
                        v430 = v1279;
                        v432 = 1;
                      }
                      LODWORD(dwBytes) = RtlULongLongAdd(v430, v433, &v1279);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_133;
                      v440 = (size_t *)v1279;
                      if ( !v438 )
                        v440 = 0;
                      if ( v438 == 8 )
                      {
                        if ( !v79 )
                        {
LABEL_548:
                          v83 = -1073741811;
LABEL_574:
                          LODWORD(dwBytes) = v83;
                          goto LABEL_133;
                        }
                        v441 = *v440;
                        v442 = v79;
                        v1279 = v79;
                        v443 = 0;
                        pcchLength = v441;
                        while ( v443 < 2 )
                        {
                          LODWORD(dwBytes) = RtlULongLongAdd(v442, v439, &v1279);
                          v83 = dwBytes;
                          if ( (dwBytes & 0x80000000) != 0LL )
                            goto LABEL_133;
                          LODWORD(dwBytes) = RtlULongLongAdd(v1279, v444, &v1279);
                          v83 = dwBytes;
                          if ( (dwBytes & 0x80000000) != 0LL )
                            goto LABEL_133;
                          v442 = v1279;
                          v443 = v445 + 1;
                        }
                        LODWORD(dwBytes) = RtlULongLongAdd(v442, v439, &v1279);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_133;
                        v448 = (int *)v1279;
                        if ( !v446 )
                          v448 = 0;
                        if ( v446 == (_DWORD)v447 )
                        {
                          v449 = *v448;
                          v450 = v79;
                          v1279 = v79;
                          LODWORD(v1278) = v449;
                          while ( 1 )
                          {
                            v451 = RtlULongLongAdd(v450, v447, &v1279);
                            LODWORD(dwBytes) = v451;
                            v83 = v451;
                            if ( v453 >= 3 )
                              break;
                            if ( v451 < 0 )
                              goto LABEL_133;
                            LODWORD(dwBytes) = RtlULongLongAdd(v1279, v452, &v1279);
                            v83 = dwBytes;
                            if ( (dwBytes & 0x80000000) != 0LL )
                              goto LABEL_133;
                            v450 = v1279;
                          }
                          if ( v451 >= 0 )
                          {
                            v454 = v79;
                            v455 = 0;
                            v1279 = v79;
                            while ( v455 < 4 )
                            {
                              v456 = *v454;
                              LODWORD(dwBytes) = RtlULongLongAdd(v454, 4, &v1279);
                              v83 = dwBytes;
                              if ( (dwBytes & 0x80000000) != 0LL )
                                goto LABEL_133;
                              LODWORD(dwBytes) = RtlULongLongAdd(v1279, v456, &v1279);
                              v83 = dwBytes;
                              if ( (dwBytes & 0x80000000) != 0LL )
                                goto LABEL_133;
                              v454 = (unsigned int *)v1279;
                              v455 = v457 + 1;
                            }
                            LODWORD(dwBytes) = RtlULongLongAdd(v454, 4, &v1279);
                            v83 = dwBytes;
                            if ( (dwBytes & 0x80000000) == 0LL )
                            {
                              v459 = v1279;
                              if ( !v458 )
                                v459 = 0;
                              if ( v458 == 4 )
                              {
                                v460 = 0;
                                v461 = v79;
                                LODWORD(v1285) = *v459;
                                v1279 = v79;
                                while ( v460 < 5 )
                                {
                                  v462 = *v461;
                                  LODWORD(dwBytes) = RtlULongLongAdd(v461, 4, &v1279);
                                  v83 = dwBytes;
                                  if ( (dwBytes & 0x80000000) != 0LL )
                                    goto LABEL_136;
                                  LODWORD(dwBytes) = RtlULongLongAdd(v1279, v462, &v1279);
                                  v83 = dwBytes;
                                  if ( (dwBytes & 0x80000000) != 0LL )
                                    goto LABEL_136;
                                  v461 = (unsigned int *)v1279;
                                  v460 = v463 + 1;
                                }
                                v464 = RtlULongLongAdd(v461, 4, &v1279);
                                LODWORD(dwBytes) = v464;
                                v83 = v464;
                                if ( v464 < 0 )
                                {
                                  LODWORD(dwBytes) = v464;
                                  goto LABEL_136;
                                }
                                v468 = (int *)v1279;
                                if ( !v465 )
                                  v468 = 0;
                                if ( v465 != 4 )
                                {
                                  v83 = -1073741789;
                                  goto LABEL_341;
                                }
                                if ( lpModuleName == (LPCWSTR)pcchLength )
                                {
                                  v469 = *v468;
                                  v1308 = (unsigned int)v1278;
                                  LODWORD(v1301) = v469;
                                  if ( (unsigned int)v1285 > 4 || (unsigned int)v466 > 4 )
                                  {
                                    v83 = -2147024774;
                                    goto LABEL_341;
                                  }
                                  memcpy_0(lpMem, v467, v466);
LABEL_134:
                                  if ( v1272 )
                                  {
                                    v83 = v1272;
                                    LODWORD(dwBytes) = v1272;
                                  }
                                  goto LABEL_136;
                                }
                                goto LABEL_340;
                              }
                              goto LABEL_573;
                            }
                          }
LABEL_133:
                          if ( v83 < 0 )
                            goto LABEL_136;
                          goto LABEL_134;
                        }
                      }
                    }
LABEL_573:
                    v83 = -1073741789;
                    goto LABEL_574;
                  }
                  v1289 = v82;
                  v1275 = v84;
                  HIDWORD(dwBytes) = v173;
                  v1284 = (size_t)v179;
                  *v179 = Src[0];
                  v175 = RtlULongLongAdd(v179, 4, &v1284);
                  if ( v175 < 0
                    || (v181 = v1284,
                        *(_DWORD *)v1284 = HIDWORD(Src[0]),
                        v175 = RtlULongLongAdd(v181, v180, &v1284),
                        v175 < 0) )
                  {
                    v1289 = v82;
                    v1275 = v84;
                    HIDWORD(dwBytes) = v173;
                    v182 = GetProcessHeap();
                    HeapFree(v182, 0, v179);
                    v174 = (unsigned int)v1278;
                  }
                  else
                  {
                    *(_QWORD *)((char *)v179 + v1307 - 8) = pcchLength;
                    memcpy_0((void *)v1284, Src[1], HIDWORD(Src[0]));
                    v174 = v1307;
                    v1277 = v179;
                  }
                }
                v83 = v175 | 0x10000000;
                pcchLength = 0;
                LODWORD(dwBytes) = v83;
                v183 = 0;
                v184 = 0;
                v1285 = 0;
                v1276 = 0;
                v1291 = 0;
                if ( v83 < 0 )
                  goto LABEL_313;
                v185 = (unsigned __int8 *)v1277;
                if ( !v1277 )
                {
                  v83 = -805306355;
                  goto LABEL_244;
                }
                v1297 = v174;
                if ( !v174
                  || (psz = (STRSAFE_PCNZWCH)(v174 + 8LL),
                      v186 = MemoryAlloc((unsigned __int64)psz),
                      v187 = 0,
                      Size = (SIZE_T)v186,
                      (v188 = (size_t)v186) == 0) )
                {
                  v83 = -805306367;
                  LODWORD(dwBytes) = -805306367;
                  goto LABEL_315;
                }
                v189 = v1297;
                v190 = 0;
                v1298 = 0;
                v191 = 0;
                v1273 = 0;
                if ( v1297 )
                {
                  do
                    v190 ^= v185[v191++];
                  while ( v191 < v1297 );
                  v1273 = v190;
                }
                v1284 = v188;
                v192 = v185;
                v1283 = (void *)0xC81ECB17B1B54A58LL;
                v1279 = v185;
                v193 = v1297 & 7;
                if ( (v1297 & 7) != 0 )
                {
                  LODWORD(v1288) = 0;
                  LODWORD(dwBytes) = 0;
                  v194 = 0;
                  v195 = 0;
                  do
                  {
                    v196 = *v192++;
                    LODWORD(v1274) = 8 * v187;
                    if ( v187 >= 4 )
                      v194 |= v196 << (56 - v1274);
                    else
                      v195 |= v196 << (24 - v1274);
                    ++v187;
                  }
                  while ( (int)v187 < v193 );
                  v189 = v1297;
                  LODWORD(dwBytes) = v195;
                  LODWORD(v1288) = v194;
                  v1279 = v192;
                  v1277 = v185;
                  v1275 = v84;
                  v1289 = v82;
                  LODWORD(v1293) = 0;
                  v187 = v195 ^ 0xB17A307A;
                  v197 = v194 ^ 0x42F6B18D;
                  v198 = v195 ^ 0xB17A307A;
                  v199 = v197;
                  if ( (v1297 & 7) != 0 )
                  {
                    v200 = (_BYTE *)v1284;
                    do
                    {
                      v1284 = (size_t)(v200 + 1);
                      if ( (unsigned int)v1293 >= 4 )
                      {
                        v199 = __ROR4__(v199, 24);
                        v201 = v199;
                      }
                      else
                      {
                        v198 = __ROR4__(v198, 24);
                        v201 = v198;
                      }
                      LODWORD(v1293) = v1293 + 1;
                      *v200 = v201;
                      v200 = (_BYTE *)v1284;
                    }
                    while ( (int)v1293 < v193 );
                  }
                  if ( (unsigned int)v193 <= 4 )
                  {
                    v202 = 0;
                    if ( (unsigned int)v193 < 4 )
                      v187 = v187 >> (8 * (4 - v193)) << (8 * (4 - v193));
                  }
                  else
                  {
                    v202 = v197 >> (8 * (8 - v193)) << (8 * (8 - v193));
                  }
                  v192 = (unsigned __int8 *)v1279;
                }
                else
                {
                  v202 = -1;
                  LODWORD(dwBytes) = 0;
                  LODWORD(v1288) = 0;
                }
                if ( v189 >> 3 )
                {
                  v203 = v189 >> 3;
                  v204 = WORD2(v1283);
                  v205 = (_BYTE *)v1284;
                  v206 = (int)v1288;
                  LODWORD(v1278) = WORD1(v1283);
                  v207 = dwBytes;
                  v1274 = 0;
                  do
                  {
                    v208 = v192[3] | ((v192[2] | (((*v192 << 8) | v192[1]) << 8)) << 8);
                    v209 = *((unsigned __int8 *)v1279 + 7)
                         | ((*((unsigned __int8 *)v1279 + 6) | ((*((unsigned __int8 *)v1279 + 5) | (v192[4] << 8)) << 8)) << 8);
                    v1279 = (char *)v1279 + 8;
                    v210 = v202 ^ v209;
                    v211 = v187 ^ v208 ^ ((v202 ^ v209) - 19032);
                    v212 = v211 ^ HIDWORD(v1283);
                    v213 = v210 ^ (__ROR4__(v211 ^ HIDWORD(v1283), 7) + WORD1(v1283) * __ROR4__(v211, 15));
                    v214 = v212 ^ (v204 * __ROR4__(v213 - 1313519016, 9) - __ROR4__(v213, 10));
                    v215 = v213 ^ (__ROR4__(v214, 27) + HIWORD(v1283) * __ROR4__(v214 ^ v204, 28));
                    v216 = v214 ^ (HIDWORD(v1283) - (v215 ^ 0xB1B54A58));
                    v217 = v215 ^ (WORD1(v1283) * (v216 - 19032) - (v216 >> 6));
                    v218 = v216 ^ (19032 * (v204 ^ __ROR4__(v217, 15)));
                    v219 = v217 ^ (v204 * (HIWORD(v1283) + __ROR4__(~v218, 3)));
                    v220 = v218 ^ (v219 - 19032 - HIDWORD(v1283));
                    v221 = v219 ^ ((_DWORD)v1278 * (v220 ^ HIWORD(v1283))) ^ __ROR4__(v220, 10);
                    v222 = v220 ^ __ROR4__(v221, 3) ^ (v204 * __ROR4__(v221 ^ 0x4A58, 26));
                    v223 = v221 ^ (19032 * (__ROR4__(v222, 15) - HIWORD(v1283)));
                    v224 = v222
                         ^ (19032 * (v223 ^ HIWORD(v1283)))
                         ^ ((v223 ^ (v223 >> 14)) >> 1)
                         ^ (19032 * ((8 * (v223 - v204)) | ((v223 - v204) >> 29)));
                    v225 = v223 ^ (WORD1(v1283) * (v224 - v204) - (v224 >> 13));
                    v226 = v224 ^ __ROR4__(v225, 11) ^ (v204 * __ROR4__(-1313519016 - v225, 9));
                    v227 = v225 ^ (v226 - HIWORD(v1283) + 1313519016);
                    v228 = v226 ^ (19032 * (v227 ^ WORD1(v1283)) - __ROR4__(v227, 7));
                    v229 = v227 ^ (WORD1(v1283) * __ROR4__(v228 ^ HIWORD(v1283), 28) - __ROR4__(v228, 16));
                    v230 = v228 ^ (__ROR4__(v229, 4) + v204 * __ROR4__(-1313519016 - v229, 10));
                    v231 = v229 ^ __ROR4__(v230, 9) ^ (HIWORD(v1283) * __ROR4__(v230 + 1313519016, 4));
                    v232 = v230 ^ (19032 * __ROR4__(HIDWORD(v1283) ^ v231, 24) - __ROR4__(v231, 30));
                    v233 = v231 ^ (WORD1(v1283) * __ROR4__(HIDWORD(v1283) - v232, 11) - __ROR4__(v232, 12));
                    v234 = v206 ^ v233 ^ HIDWORD(v1283);
                    v206 = v209;
                    v192 = (unsigned __int8 *)v1279;
                    v235 = v232 ^ (v233 >> 8) ^ (v204 * (v233 ^ WORD1(v1283)));
                    v187 = v235 ^ v207;
                    v205[3] = v235 ^ v207;
                    v202 = v235 ^ v234 ^ 0xB1B54A58;
                    v205[7] = v202;
                    LOBYTE(v218) = __ROR4__(v235 ^ v207, 8);
                    v207 = v208;
                    v205[2] = v218;
                    v205[6] = __ROR4__(v202, 8);
                    v205[1] = __ROR4__(v187, 16);
                    v205[5] = __ROR4__(v202, 16);
                    *v205 = __ROR4__(v187, 24);
                    v205[4] = __ROR4__(v202, 24);
                    v205 += 8;
                    ++v1274;
                  }
                  while ( v1274 < v203 );
                  v184 = v1285;
                  v190 = v1273;
                  v183 = (unsigned int *)v1285;
                  v82 = v1289;
                  v84 = v1275;
                  v185 = (unsigned __int8 *)v1277;
                  v189 = v1297;
                }
                *(_QWORD *)(Size + v189) = v190;
                v236 = GetProcessHeap();
                v237 = HeapAlloc(v236, 8u, 0x30u);
                v1275 = v237;
                if ( v237 )
                {
                  *v237 = (_DWORD)psz;
                  v239 = GetProcessHeap();
                  v240 = HeapAlloc(v239, 8u, (unsigned int)psz);
                  if ( !v240 )
                    goto LABEL_288;
                  v1277 = v185;
                  v241 = v1275;
                  *((_QWORD *)v1275 + 1) = v240;
                  memcpy_0(v240, (const void *)Size, (unsigned int)psz);
                  v241[4] = 160;
                  v242 = GetProcessHeap();
                  v243 = HeapAlloc(v242, 8u, 0xA0u);
                  if ( !v243 )
                    goto LABEL_288;
                  *((_QWORD *)v241 + 3) = v243;
                  *v243 = xmmword_18003DB30;
                  v243[1] = xmmword_18003DB40;
                  v243[2] = xmmword_18003DB50;
                  v243[3] = xmmword_18003DB60;
                  v243[4] = xmmword_18003DB70;
                  v243[5] = xmmword_18003DB80;
                  v243[6] = xmmword_18003DB90;
                  v243[7] = xmmword_18003DBA0;
                  v243[8] = xmmword_18003DBB0;
                  v243[9] = xmmword_18003DBC0;
                  v241[8] = 8;
                  v244 = GetProcessHeap();
                  v245 = HeapAlloc(v244, 8u, 8u);
                  if ( v245 )
                  {
                    *((_QWORD *)v241 + 5) = v245;
                    *v245 = qword_18003DBD0;
                    v1298 = v241;
                    v238 = 0;
                    v183 = (unsigned int *)v1298;
                    v1298 = 0;
                  }
                  else
                  {
LABEL_288:
                    v238 = -1073741801;
                    v246 = v1275;
                    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v1275 + 1);
                    if ( psz )
                    {
                      v247 = GetProcessHeap();
                      HeapFree(v247, 0, (LPVOID)psz);
                      v246 = v1275;
                      *((_QWORD *)v1275 + 1) = 0;
                    }
                    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v246 + 3);
                    if ( psz )
                    {
                      v248 = GetProcessHeap();
                      HeapFree(v248, 0, (LPVOID)psz);
                      v246 = v1275;
                      *((_QWORD *)v1275 + 3) = 0;
                    }
                    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v246 + 5);
                    if ( psz )
                    {
                      v249 = GetProcessHeap();
                      HeapFree(v249, 0, (LPVOID)psz);
                      *((_QWORD *)v1275 + 5) = 0;
                    }
                    v250 = GetProcessHeap();
                    HeapFree(v250, 0, v1275);
                  }
                }
                else
                {
                  v238 = -1073741801;
                }
                v251 = GetProcessHeap();
                HeapFree(v251, 0, (LPVOID)Size);
                v252 = v1298;
                if ( v1298 )
                {
                  Size = *((_QWORD *)v1298 + 1);
                  if ( Size )
                  {
                    v253 = GetProcessHeap();
                    HeapFree(v253, 0, (LPVOID)Size);
                    v252 = v1298;
                    *((_QWORD *)v1298 + 1) = 0;
                  }
                  Size = v252[3];
                  if ( Size )
                  {
                    v254 = GetProcessHeap();
                    HeapFree(v254, 0, (LPVOID)Size);
                    v252 = v1298;
                    *((_QWORD *)v1298 + 3) = 0;
                  }
                  Size = v252[5];
                  if ( Size )
                  {
                    v255 = GetProcessHeap();
                    HeapFree(v255, 0, (LPVOID)Size);
                    *((_QWORD *)v1298 + 5) = 0;
                  }
                  v256 = GetProcessHeap();
                  HeapFree(v256, 0, v1298);
                }
                v83 = v238 | 0x10000000;
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                {
                  v267 = v1277;
LABEL_314:
                  if ( !v267 )
                  {
LABEL_316:
                    if ( v183 )
                    {
                      Size = *((_QWORD *)v183 + 1);
                      if ( Size )
                      {
                        v269 = GetProcessHeap();
                        HeapFree(v269, 0, (LPVOID)Size);
                        *((_QWORD *)v183 + 1) = 0;
                      }
                      Size = *((_QWORD *)v183 + 3);
                      if ( Size )
                      {
                        v270 = GetProcessHeap();
                        HeapFree(v270, 0, (LPVOID)Size);
                        *((_QWORD *)v183 + 3) = 0;
                      }
                      Size = *((_QWORD *)v183 + 5);
                      if ( Size )
                      {
                        v271 = GetProcessHeap();
                        HeapFree(v271, 0, (LPVOID)Size);
                        *((_QWORD *)v183 + 5) = 0;
                      }
                      v272 = GetProcessHeap();
                      HeapFree(v272, 0, v183);
                    }
                    v273 = (void *)pcchLength;
                    if ( pcchLength )
                    {
                      v274 = GetProcessHeap();
                      HeapFree(v274, 0, v273);
                    }
                    if ( v184 )
                    {
                      v275 = GetProcessHeap();
                      HeapFree(v275, 0, v184);
                    }
                    v276 = v1276;
                    if ( v1276 )
                    {
                      v277 = (void *)*((_QWORD *)v1276 + 1);
                      if ( v277 )
                      {
                        v278 = GetProcessHeap();
                        HeapFree(v278, 0, v277);
                        v276[1] = 0;
                      }
                      v279 = (void *)v276[3];
                      if ( v279 )
                      {
                        v280 = GetProcessHeap();
                        HeapFree(v280, 0, v279);
                        v276[3] = 0;
                      }
                      v281 = (void *)v276[5];
                      if ( v281 )
                      {
                        v282 = GetProcessHeap();
                        HeapFree(v282, 0, v281);
                        v276[5] = 0;
                      }
                      v283 = GetProcessHeap();
                      HeapFree(v283, 0, v276);
                    }
                    v284 = v1291;
                    if ( v1291 )
                    {
                      v285 = GetProcessHeap();
                      HeapFree(v285, 0, v284);
                    }
                    goto LABEL_338;
                  }
LABEL_315:
                  v268 = GetProcessHeap();
                  HeapFree(v268, 0, v1277);
                  goto LABEL_316;
                }
                v257 = *v183;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = 4;
                v259 = RtlUIntAdd(4, v257, &dwBytes);
                if ( v259 >= 0 )
                {
                  v259 = RtlUIntAdd((unsigned int)dwBytes, v258, &dwBytes);
                  if ( v259 >= 0 )
                  {
                    v260 = v183[4];
                    Size = (SIZE_T)(v183 + 4);
                    v259 = RtlUIntAdd((unsigned int)dwBytes, v260, &dwBytes);
                    if ( v259 >= 0 )
                    {
                      v259 = RtlUIntAdd((unsigned int)dwBytes, v261, &dwBytes);
                      if ( v259 >= 0 )
                      {
                        v262 = v183[8];
                        psz = (STRSAFE_PCNZWCH)(v183 + 8);
                        v259 = RtlUIntAdd((unsigned int)dwBytes, v262, &dwBytes);
                        if ( v259 >= 0 )
                        {
                          v1287 = (__int64)v183;
                          v263 = dwBytes;
                          v264 = GetProcessHeap();
                          v265 = HeapAlloc(v264, 8u, v263);
                          v183 = (unsigned int *)v1287;
                          v266 = v265;
                          v1275 = v265;
                          if ( !v265 )
                          {
                            v83 = -805306345;
LABEL_312:
                            LODWORD(dwBytes) = v83;
LABEL_313:
                            v267 = v1277;
                            goto LABEL_314;
                          }
                          v286 = *(_DWORD *)v1287;
                          v1278 = v266;
                          *v266 = v286;
                          v259 = RtlULongLongAdd(v266, 4, &v1278);
                          if ( v259 < 0 )
                          {
                            v1277 = v288;
                            HIDWORD(dwBytes) = v289;
                            v1275 = v287;
                          }
                          else
                          {
                            memcpy_0(v1278, *((const void **)v183 + 1), *v183);
                            v259 = RtlULongLongAdd(v1278, *v183, &v1278);
                            if ( v259 >= 0 )
                            {
                              v290 = v1278;
                              *(_DWORD *)v1278 = *(_DWORD *)Size;
                              v259 = RtlULongLongAdd(v290, 4, &v1278);
                              if ( v259 >= 0 )
                              {
                                memcpy_0(v1278, *((const void **)v183 + 3), *v291);
                                v259 = RtlULongLongAdd(v1278, *(unsigned int *)Size, &v1278);
                                if ( v259 >= 0 )
                                {
                                  v292 = v1278;
                                  *(_DWORD *)v1278 = *(_DWORD *)psz;
                                  v259 = RtlULongLongAdd(v292, 4, &v1278);
                                  if ( v259 >= 0 )
                                  {
                                    memcpy_0(v1278, *((const void **)v183 + 5), *v293);
                                    v259 = RtlULongLongAdd(v1278, *(unsigned int *)psz, &v1278);
                                    if ( v259 >= 0 )
                                    {
                                      pcchLength = (size_t)v1275;
                                      LODWORD(v1274) = dwBytes;
                                      goto LABEL_353;
                                    }
                                  }
                                }
                              }
                            }
                          }
                          v294 = GetProcessHeap();
                          HeapFree(v294, 0, v1275);
                        }
                      }
                    }
                  }
                }
LABEL_353:
                v83 = v259 | 0x10000000;
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_313;
                v1313 = 8;
                v295 = RtlUIntAdd(8, HIDWORD(dwBytes), &v1313);
                v83 = v295 | 0x10000000;
                LODWORD(dwBytes) = v295 | 0x10000000;
                if ( v295 < 0 )
                  goto LABEL_313;
                v296 = (v1313 + 7) & 0xFFFFFFF8;
                if ( (unsigned int)v296 < v1313 )
                {
                  v83 = -1073741675;
                  goto LABEL_312;
                }
                v1316 = (v1313 + 7) & 0xFFFFFFF8;
                LODWORD(dwBytes) = RtlUIntAdd(v296, 8, &v1316);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_313;
                v299 = Src[1];
                v300 = v298;
                v1289 = v82;
                v1275 = v84;
                v1277 = v297;
                v1287 = (__int64)v183;
                LODWORD(v1293) = v298;
                if ( Src[1] )
                {
                  v1287 = (__int64)v183;
                  v1277 = v297;
                  v1275 = v84;
                  v1289 = v82;
                  if ( LODWORD(Src[0]) > 1 )
                  {
                    v1279 = Src[1];
                    while ( !v298 )
                    {
                      LODWORD(dwBytes) = RtlULongLongAdd(v299, 4, &v1279);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_368;
                      LODWORD(dwBytes) = RtlULongLongAdd(v1279, v301, &v1279);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_368;
                      v299 = v1279;
                      v298 = v302 + 1;
                    }
                    LODWORD(v1278) = *v299;
                    LODWORD(dwBytes) = RtlULongLongAdd(v299, 4, &v1279);
                    v83 = dwBytes;
                    if ( (dwBytes & 0x80000000) != 0LL )
                      goto LABEL_368;
                    v303 = Src[1];
                    if ( Src[1] && LODWORD(Src[0]) > 2 )
                    {
                      v1279 = Src[1];
                      for ( i18 = 0; i18 < 2; i18 = v309 + 1 )
                      {
                        LODWORD(dwBytes) = RtlULongLongAdd(v303, 4, &v1279);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_368;
                        LODWORD(dwBytes) = RtlULongLongAdd(v1279, v308, &v1279);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_368;
                        v303 = v1279;
                      }
                      LODWORD(dwBytes) = RtlULongLongAdd(v303, 4, &v1279);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) == 0LL )
                      {
                        LODWORD(v1293) = v310;
                        HIDWORD(dwBytes) = 4;
                        LODWORD(dwBytes) = RtlUIntAdd(4, v1316, (char *)&dwBytes + 4);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_386;
                        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v311, (char *)&dwBytes + 4);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1278, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL)
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL)
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v312, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL) )
                        {
LABEL_386:
                          if ( v83 < 0 )
                            goto LABEL_313;
                        }
                        else
                        {
                          v300 = HIDWORD(dwBytes);
                          LODWORD(v1293) = HIDWORD(dwBytes);
                        }
                        if ( v300 > 0x400000 )
                        {
                          v83 = -2147418113;
                          goto LABEL_312;
                        }
LABEL_369:
                        v304 = v300;
                        v305 = GetProcessHeap();
                        v306 = HeapAlloc(v305, 8u, v304);
                        v184 = v306;
                        if ( !v306 )
                        {
                          v83 = -805306345;
                          v184 = 0;
LABEL_371:
                          LODWORD(dwBytes) = v83;
LABEL_372:
                          v183 = (unsigned int *)v1287;
                          goto LABEL_313;
                        }
                        phModule = 0;
                        v1324 = 0;
                        v1325 = 0;
                        if ( !pcchLength )
                        {
                          v83 = -2147024809;
                          goto LABEL_371;
                        }
                        LODWORD(v1325) = v1274;
                        *(_QWORD *)&v1324 = pcchLength;
                        *(_QWORD *)((char *)&v1325 + 4) = (unsigned int)v1293;
                        *((_QWORD *)&v1324 + 1) = v306;
                        if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                          && (v314 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                        {
                          v315 = ((__int64 (__fastcall *)(__int64, __int128 *))v314)(134, &v1324);
                          v83 = v315 | 0x10000000;
                          LODWORD(dwBytes) = v315 | 0x10000000;
                          if ( v315 >= 0 )
                          {
                            v316 = DWORD1(v1325);
                            goto LABEL_403;
                          }
                        }
                        else
                        {
                          v313 = GetLastError();
                          LODWORD(dwBytes) = v313;
                          v83 = v313;
                          if ( v313 > 0 )
                          {
                            v83 = (unsigned __int16)v313 | 0x80070000;
                            LODWORD(dwBytes) = v83;
                          }
                          if ( v83 >= 0 )
                          {
                            v83 = -2147467259;
                            goto LABEL_371;
                          }
                        }
                        if ( v83 == -805306333 )
                        {
                          v83 = -2147024774;
                          goto LABEL_371;
                        }
                        if ( v83 < 0 )
                          goto LABEL_372;
                        v316 = v1293;
LABEL_403:
                        HIDWORD(dwBytes) = 0;
                        v1283 = v184;
                        if ( v316 < 4 )
                        {
LABEL_404:
                          v83 = -805306306;
                          goto LABEL_371;
                        }
                        v317 = (unsigned int)*v184;
                        LODWORD(v1278) = *v184;
                        v319 = RtlULongLongAdd(v184, 4, &v1283);
                        if ( v319 >= 0 )
                        {
                          v319 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                          if ( v319 >= 0 )
                          {
                            if ( v320 - HIDWORD(dwBytes) < (unsigned int)v317 )
                              goto LABEL_404;
                            psz = (STRSAFE_PCNZWCH)v1283;
                            Size = v317;
                            v319 = RtlULongLongAdd(v1283, (unsigned int)v317, &v1283);
                            if ( v319 >= 0 )
                            {
                              v319 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v317, (char *)&dwBytes + 4);
                              if ( v319 >= 0 )
                              {
                                if ( (unsigned int)(v321 - HIDWORD(dwBytes)) < 4 )
                                  goto LABEL_404;
                                LODWORD(v1285) = *(_DWORD *)v1283;
                                v319 = RtlULongLongAdd(v1283, 4, &v1283);
                                if ( v319 >= 0 )
                                {
                                  v319 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                  if ( v319 >= 0 )
                                  {
                                    if ( v322 - HIDWORD(dwBytes) < (unsigned int)v323 )
                                      goto LABEL_404;
                                    v1284 = (size_t)v1283;
                                    v1297 = v323;
                                    v319 = RtlULongLongAdd(v1283, (unsigned int)v323, &v1283);
                                    if ( v319 >= 0 )
                                    {
                                      v319 = RtlUIntAdd(HIDWORD(dwBytes), v324, (char *)&dwBytes + 4);
                                      if ( v319 >= 0 )
                                      {
                                        if ( (unsigned int)(v325 - HIDWORD(dwBytes)) < 4 )
                                          goto LABEL_404;
                                        LODWORD(v1274) = *(_DWORD *)v1283;
                                        v319 = RtlULongLongAdd(v1283, 4, &v1283);
                                        if ( v319 >= 0 )
                                        {
                                          v319 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                          if ( v319 >= 0 )
                                          {
                                            if ( v326 - HIDWORD(dwBytes) < v327 )
                                              goto LABEL_404;
                                            v319 = RtlUIntAdd(HIDWORD(dwBytes), v327, (char *)&dwBytes + 4);
                                            if ( v319 >= 0 )
                                            {
                                              if ( v328 != HIDWORD(dwBytes)
                                                || (unsigned int)(v317 + v329 + v330) + 12LL != v328 )
                                              {
                                                goto LABEL_404;
                                              }
                                              v331 = GetProcessHeap();
                                              v332 = HeapAlloc(v331, 8u, 0x30u);
                                              v183 = (unsigned int *)v1287;
                                              v318 = 0;
                                              v333 = v332 == 0;
                                              v1276 = v332;
                                              v334 = v332;
                                              v267 = v1277;
                                              if ( v333 )
                                              {
                                                v83 = -805306345;
                                                v1276 = 0;
                                                LODWORD(dwBytes) = -805306345;
                                                goto LABEL_314;
                                              }
                                              v1289 = v82;
                                              v1275 = v84;
                                              v1279 = 0;
                                              if ( psz )
                                              {
                                                *(_DWORD *)v334 = (_DWORD)v1278;
                                                v335 = GetProcessHeap();
                                                v336 = HeapAlloc(v335, 8u, Size);
                                                if ( !v336 )
                                                {
LABEL_436:
                                                  v344 = v1276;
                                                  v319 = -1073741801;
                                                  v1285 = v184;
                                                  Size = *((_QWORD *)v1276 + 1);
                                                  if ( Size )
                                                  {
                                                    v345 = GetProcessHeap();
                                                    HeapFree(v345, 0, (LPVOID)Size);
                                                    v344 = v1276;
                                                    *((_QWORD *)v1276 + 1) = 0;
                                                  }
                                                  Size = v344[3];
                                                  if ( Size )
                                                  {
                                                    v346 = GetProcessHeap();
                                                    HeapFree(v346, 0, (LPVOID)Size);
                                                    v344 = v1276;
                                                    *((_QWORD *)v1276 + 3) = 0;
                                                  }
                                                  Size = v344[5];
                                                  if ( Size )
                                                  {
                                                    v347 = GetProcessHeap();
                                                    HeapFree(v347, 0, (LPVOID)Size);
                                                    *((_QWORD *)v1276 + 5) = 0;
                                                  }
                                                  v348 = GetProcessHeap();
                                                  HeapFree(v348, 0, v1276);
                                                  v349 = (SIZE_T *)v1279;
                                                  v318 = 0;
                                                  goto LABEL_446;
                                                }
                                                *((_QWORD *)v1276 + 1) = v336;
                                                v319 = 0;
                                                memcpy_0(v336, psz, Size);
                                                v334 = v1276;
                                                v318 = 0;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v334 = 0;
                                                v319 = 0;
                                                v334[1] = 0;
                                              }
                                              if ( v1284 )
                                              {
                                                *((_DWORD *)v334 + 4) = (_DWORD)v1285;
                                                v337 = GetProcessHeap();
                                                v338 = HeapAlloc(v337, 8u, v1297);
                                                v339 = v1276;
                                                if ( !v338 )
                                                {
LABEL_435:
                                                  v1276 = v339;
                                                  v1289 = v82;
                                                  v1275 = v84;
                                                  v1287 = (__int64)v183;
                                                  goto LABEL_436;
                                                }
                                                *((_QWORD *)v1276 + 3) = v338;
                                                v319 = 0;
                                                memcpy_0(v338, (const void *)v1284, v1297);
                                                v334 = v1276;
                                                v318 = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v334 + 4) = 0;
                                                v334[3] = 0;
                                              }
                                              if ( v1283 )
                                              {
                                                v340 = (unsigned int)v1274;
                                                *((_DWORD *)v334 + 8) = v1274;
                                                v341 = v340;
                                                Size = v340;
                                                v342 = GetProcessHeap();
                                                v343 = HeapAlloc(v342, 8u, v341);
                                                v339 = v1276;
                                                if ( !v343 )
                                                  goto LABEL_435;
                                                *((_QWORD *)v1276 + 5) = v343;
                                                v319 = 0;
                                                memcpy_0(v343, v1283, Size);
                                                v334 = v1276;
                                                v318 = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v334 + 8) = 0;
                                                v334[5] = 0;
                                              }
                                              v349 = v334;
                                              v1279 = v334;
                                              v1285 = v184;
                                              v1287 = (__int64)v183;
                                              v1275 = v84;
                                              v1289 = v82;
LABEL_446:
                                              if ( v319 < 0 )
                                              {
                                                v350 = 0;
                                                v1276 = 0;
                                                if ( v349 )
                                                {
                                                  Size = v349[1];
                                                  if ( Size )
                                                  {
                                                    v351 = GetProcessHeap();
                                                    HeapFree(v351, 0, (LPVOID)Size);
                                                    v349 = (SIZE_T *)v1279;
                                                    *((_QWORD *)v1279 + 1) = 0;
                                                  }
                                                  Size = v349[3];
                                                  if ( Size )
                                                  {
                                                    v352 = GetProcessHeap();
                                                    HeapFree(v352, 0, (LPVOID)Size);
                                                    v349 = (SIZE_T *)v1279;
                                                    *((_QWORD *)v1279 + 3) = 0;
                                                  }
                                                  Size = v349[5];
                                                  if ( Size )
                                                  {
                                                    v353 = GetProcessHeap();
                                                    HeapFree(v353, 0, (LPVOID)Size);
                                                    *((_QWORD *)v1279 + 5) = 0;
                                                  }
                                                  v354 = GetProcessHeap();
                                                  HeapFree(v354, 0, v1279);
                                                  v318 = 0;
                                                  v350 = 0;
                                                  v1276 = 0;
                                                }
                                              }
                                              else
                                              {
                                                v350 = (unsigned int *)v349;
                                                v1276 = v349;
                                              }
LABEL_458:
                                              v83 = v319 | 0x10000000;
                                              LODWORD(dwBytes) = v83;
                                              if ( v83 < 0 )
                                                goto LABEL_313;
                                              if ( !v350 || (v1284 = *((_QWORD *)v350 + 1)) == 0 || *v350 == v318 )
                                              {
                                                v83 = -805306355;
                                                goto LABEL_371;
                                              }
                                              v355 = *v350 - 8LL;
                                              v1283 = (void *)v355;
                                              v1291 = MemoryAlloc(v355);
                                              v356 = v1291;
                                              if ( !v1291 )
                                              {
LABEL_489:
                                                v83 = -805306367;
                                                v1291 = 0;
                                                goto LABEL_371;
                                              }
                                              v1273 = 0;
                                              v357 = 0;
                                              v1278 = (void *)0x7F1137FAB69605ELL;
                                              v358 = 0;
                                              Size = v1284;
                                              v359 = 0;
                                              psz = (STRSAFE_PCNZWCH)v1291;
                                              LODWORD(v1293) = 0;
                                              v360 = v355 & 7;
                                              if ( (v355 & 7) != 0 )
                                              {
                                                LODWORD(v1298) = 0;
                                                v361 = 0;
                                                v362 = (unsigned __int8 *)Size;
                                                v363 = 0;
                                                do
                                                {
                                                  v364 = *v362++;
                                                  LODWORD(v1274) = 8 * v359;
                                                  if ( (unsigned int)v359 >= 4 )
                                                    v361 |= v364 << (56 - v1274);
                                                  else
                                                    v363 |= v364 << (24 - v1274);
                                                  ++v359;
                                                }
                                                while ( v359 < (int)v360 );
                                                v355 = (unsigned __int64)v1283;
                                                LODWORD(v1293) = v363;
                                                v365 = v363;
                                                v357 = v1273;
                                                LODWORD(v1298) = v361;
                                                Size = (SIZE_T)v362;
                                                v1285 = v184;
                                                v1287 = (__int64)v183;
                                                v1275 = v84;
                                                v1289 = v82;
                                                v358 = v365 ^ 0x92F65A5;
                                                v366 = v361 ^ 0x699A899C;
                                                v367 = 0;
                                                v368 = v358;
                                                v369 = v361 ^ 0x699A899C;
                                                if ( v360 )
                                                {
                                                  v370 = (char *)v1291;
                                                  do
                                                  {
                                                    psz = (STRSAFE_PCNZWCH)(v370 + 1);
                                                    if ( v367 >= 4 )
                                                    {
                                                      v369 = __ROR4__(v369, 24);
                                                      v371 = v369;
                                                    }
                                                    else
                                                    {
                                                      v368 = __ROR4__(v368, 24);
                                                      v371 = v368;
                                                    }
                                                    *v370 = v371;
                                                    ++v367;
                                                    v370 = (char *)psz;
                                                  }
                                                  while ( (int)v367 < (int)v360 );
                                                }
                                                if ( v360 <= 4 )
                                                {
                                                  v359 = 0;
                                                  if ( v360 < 4 )
                                                    v358 = v358 >> (8 * (4 - v360)) << (8 * (4 - v360));
                                                }
                                                else
                                                {
                                                  v359 = v366 >> (8 * (8 - v360)) << (8 * (8 - v360));
                                                }
                                              }
                                              else
                                              {
                                                LODWORD(v1298) = -1;
                                              }
                                              v372 = v355 >> 3;
                                              if ( v355 >> 3 )
                                              {
                                                v373 = HIDWORD(v1278);
                                                v374 = (unsigned __int8 *)Size;
                                                v375 = (wchar_t *)psz;
                                                v376 = (int)v1298;
                                                v377 = v1293;
                                                HIDWORD(dwBytes) = WORD2(v1278);
                                                LODWORD(dwBytes) = 24670;
                                                v378 = v372;
                                                v1297 = 0;
                                                do
                                                {
                                                  v379 = v374[1];
                                                  v380 = *v374;
                                                  v381 = v374[4];
                                                  v374 += 8;
                                                  v382 = *(v374 - 5)
                                                       | ((*(v374 - 6) | ((v379 | (v380 << 8)) << 8)) << 8);
                                                  v383 = v358 ^ v382;
                                                  v384 = *(v374 - 1)
                                                       | ((*(v374 - 2) | ((*(v374 - 3) | (v381 << 8)) << 8)) << 8);
                                                  v385 = v359 ^ v384 ^ v373 ^ v358 ^ v382 ^ 0xAB69605E;
                                                  v386 = v383
                                                       ^ (__ROR4__(v385, 22)
                                                        + HIDWORD(dwBytes) * __ROR4__(v385 + 1419157410, 27));
                                                  v387 = v385
                                                       ^ (WORD1(v1278) * __ROR4__(v386 + v373, 9) - __ROR4__(v386, 30));
                                                  v388 = v386 ^ (dwBytes * (v387 - HIDWORD(dwBytes)) - (v387 >> 13));
                                                  v389 = v387
                                                       ^ (HIWORD(v1278) * __ROR4__(WORD1(v1278) ^ v388, 26)
                                                        - __ROR4__(v388, 30));
                                                  v390 = v388 ^ (v373 - (v389 ^ 0xAB69605E));
                                                  v391 = v389
                                                       ^ (WORD1(v1278) * (HIDWORD(dwBytes) ^ v390))
                                                       ^ __ROR4__(v390, 6);
                                                  v392 = v390
                                                       ^ (__ROR4__(v391, 30) + dwBytes * __ROR4__(v391 + v373, 15));
                                                  v393 = v391
                                                       ^ (HIWORD(v1278) * __ROR4__(v392 + 1419157410, 14)
                                                        - __ROR4__(v392, 24));
                                                  v394 = v392
                                                       ^ __ROR4__(v393, 10)
                                                       ^ (HIDWORD(dwBytes) * __ROR4__(v393 ^ 0xAB69605E, 12));
                                                  v395 = v394
                                                       ^ (HIWORD(v1278)
                                                        * (dwBytes
                                                         + __ROR4__(
                                                             ~(v393
                                                             ^ (v394 >> 10)
                                                             ^ (WORD1(v1278) * (HIWORD(v1278) ^ v394))),
                                                             5)));
                                                  v396 = v393
                                                       ^ (v394 >> 10)
                                                       ^ (WORD1(v1278) * (HIWORD(v1278) ^ v394))
                                                       ^ (v395 - HIWORD(v1278))
                                                       ^ 0xAB69605E;
                                                  v397 = v395
                                                       ^ ((v396 >> 2)
                                                        + HIDWORD(dwBytes) * __ROR4__(HIWORD(v1278) ^ v396, 30));
                                                  v398 = v396
                                                       ^ (__ROR4__(v397, 25)
                                                        + WORD1(v1278) * __ROR4__(v397 - HIDWORD(v1278), 6));
                                                  v399 = v397
                                                       ^ (dwBytes * (HIDWORD(dwBytes) ^ v398) + __ROR4__(v398, 9));
                                                  v400 = v398
                                                       ^ (__ROR4__(v399, 25)
                                                        + HIWORD(v1278) * __ROR4__(WORD1(v1278) ^ v399, 27));
                                                  v373 = HIDWORD(v1278);
                                                  v401 = HIDWORD(v1278) ^ v399 ^ v400 ^ 0xAB69605E;
                                                  v402 = v400 ^ (HIDWORD(dwBytes) * (__ROR4__(v401, 3) - WORD1(v1278)));
                                                  v403 = v401
                                                       ^ (dwBytes * __ROR4__(v402 - HIDWORD(v1278), 1)
                                                        - __ROR4__(v402, 6));
                                                  v404 = v402
                                                       ^ (__ROR4__(v403, 18)
                                                        + HIWORD(v1278) * __ROR4__(v403 - 1419157410, 29));
                                                  v405 = v403
                                                       ^ (HIDWORD(dwBytes) * __ROR4__(v404 - 1419157410, 17)
                                                        - __ROR4__(v404, 14));
                                                  v406 = v404 ^ (v405 >> 3) ^ (WORD1(v1278) * (dwBytes ^ v405));
                                                  v359 = v376 ^ v406;
                                                  v376 = v384;
                                                  v358 = v377
                                                       ^ v405
                                                       ^ __ROR4__(v406, 30)
                                                       ^ (dwBytes * __ROR4__(HIDWORD(v1278) ^ v406, 28));
                                                  v377 = v382;
                                                  *((_BYTE *)v375 + 3) = v358;
                                                  *((_BYTE *)v375 + 7) = v359;
                                                  *((_BYTE *)v375 + 2) = __ROR4__(v358, 8);
                                                  *((_BYTE *)v375 + 6) = __ROR4__(v359, 8);
                                                  *((_BYTE *)v375 + 1) = __ROR4__(v358, 16);
                                                  *((_BYTE *)v375 + 5) = __ROR4__(v359, 16);
                                                  *(_BYTE *)v375 = __ROR4__(v358, 24);
                                                  *((_BYTE *)v375 + 4) = __ROR4__(v359, 24);
                                                  v375 += 4;
                                                  ++v1297;
                                                }
                                                while ( v1297 < v378 );
                                                v357 = v1273;
                                                v82 = v1289;
                                                v84 = v1275;
                                                v184 = v1285;
                                                v356 = v1291;
                                                v355 = (unsigned __int64)v1283;
                                              }
                                              for ( i19 = 0; i19 < v355; ++i19 )
                                                v357 ^= v356[i19];
                                              if ( v357 != *(_QWORD *)(v355 + v1284) )
                                              {
                                                MemoryFree(v356);
                                                goto LABEL_489;
                                              }
                                              v183 = (unsigned int *)v1287;
                                              HIDWORD(dwBytes) = 0;
                                              v1279 = v356;
                                              if ( (unsigned int)v355 < 4 )
                                                goto LABEL_491;
                                              v408 = RtlULongLongAdd(v356, 4, &v1279);
                                              if ( v408 >= 0 )
                                              {
                                                v408 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                                if ( v408 >= 0 )
                                                {
                                                  v413 = (unsigned int)(v412 + 4);
                                                  if ( (int)v1283 - HIDWORD(dwBytes) < (unsigned int)v413 )
                                                    goto LABEL_523;
                                                  LODWORD(v1293) = *(_DWORD *)v1279;
                                                  v408 = RtlULongLongAdd(v1279, v413, &v1279);
                                                  if ( v408 < 0 )
                                                    goto LABEL_524;
                                                  v408 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                  if ( v408 < 0 )
                                                    goto LABEL_524;
                                                  if ( (int)v1283 - HIDWORD(dwBytes) < (unsigned int)v1293 )
                                                    goto LABEL_523;
                                                  v408 = RtlUIntAdd(
                                                           HIDWORD(dwBytes),
                                                           (unsigned int)v1293,
                                                           (char *)&dwBytes + 4);
                                                  if ( v408 >= 0 )
                                                  {
                                                    if ( (char *)v411 + (unsigned int)v1283 >= (char *)v1279
                                                                                             + (unsigned int)v1293 )
                                                    {
                                                      v414 = v1279;
                                                      if ( (unsigned int)v1283
                                                         + (char *)v411
                                                         - (_BYTE *)v1279
                                                         - (unsigned __int64)(unsigned int)v1293 < 8 )
                                                      {
                                                        LODWORD(v1278) = *v411;
                                                        Size = 0;
                                                        psz = 0;
                                                        v1297 = 0;
                                                        LODWORD(v1288) = 0;
                                                        if ( v1279 )
                                                        {
                                                          v408 = RtlULongLongAdd(v1279, (unsigned int)v1293, &Size);
                                                          v1291 = v416;
                                                          v1276 = v417;
                                                          v1277 = v418;
                                                          if ( v408 < 0 )
                                                            goto LABEL_525;
                                                          v419 = Size;
                                                          v420 = 4;
                                                          v421 = v415;
                                                          while ( v421 < v419 )
                                                          {
                                                            v408 = RtlULongLongAdd(v421, v420, &psz);
                                                            if ( v408 < 0 )
                                                              goto LABEL_525;
                                                            if ( (unsigned __int64)psz > v423 )
                                                              goto LABEL_511;
                                                            v425 = *v422;
                                                            LODWORD(v1274) = 0;
                                                            v408 = RtlUIntAdd(v424, v425, &v1274);
                                                            if ( v408 < 0 )
                                                              goto LABEL_525;
                                                            v408 = RtlULongLongAdd(v426, (unsigned int)v1274, &v1297);
                                                            if ( v408 < 0 )
                                                              goto LABEL_525;
                                                            v421 = v1297;
                                                            if ( v1297 > v419 )
                                                              goto LABEL_511;
                                                            LODWORD(v1288) = (_DWORD)v1288 + 1;
                                                          }
                                                          if ( v421 != v419 )
                                                          {
LABEL_511:
                                                            v408 = -1073741811;
                                                            goto LABEL_525;
                                                          }
                                                          v414 = v1279;
                                                        }
                                                        else
                                                        {
                                                          v408 = 0;
                                                          v1291 = v411;
                                                          v1276 = v410;
                                                          v1277 = v409;
                                                        }
                                                        v427 = v1293;
                                                        v428 = 0;
                                                        Size = 0;
                                                        if ( (_DWORD)v1293 )
                                                        {
                                                          v429 = GetProcessHeap();
                                                          v428 = HeapAlloc(v429, 8u, (unsigned int)v1293);
                                                          Size = (SIZE_T)v428;
                                                          if ( !v428 )
                                                          {
                                                            v408 = -1073741801;
                                                            goto LABEL_525;
                                                          }
                                                          v414 = v1279;
                                                          v408 = 0;
                                                          v427 = v1293;
                                                        }
                                                        if ( v414 )
                                                          memcpy_0(v428, v414, v427);
                                                        v1299 = (LPVOID)Size;
                                                        LODWORD(v1292) = (_DWORD)v1288;
                                                        if ( (_DWORD)v1278 == (_DWORD)v1288 )
                                                          goto LABEL_525;
LABEL_491:
                                                        v408 = -1073741762;
LABEL_525:
                                                        v83 = v408 | 0x10000000;
                                                        goto LABEL_312;
                                                      }
                                                    }
LABEL_523:
                                                    v408 = -1073741762;
                                                  }
                                                }
                                              }
LABEL_524:
                                              v1291 = v411;
                                              v1277 = v409;
                                              v1276 = v410;
                                              goto LABEL_525;
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v318 = 0;
                              }
                            }
                          }
                        }
                        v183 = (unsigned int *)v1287;
                        v350 = (unsigned int *)v1276;
                        v1285 = v184;
                        goto LABEL_458;
                      }
LABEL_368:
                      if ( v83 < 0 )
                        goto LABEL_313;
                      goto LABEL_369;
                    }
                  }
                }
                v83 = -1073741811;
                LODWORD(dwBytes) = -1073741811;
                goto LABEL_368;
              }
              pcchLength = (size_t)Src[1];
              for ( i20 = 0; i20 < v164; i20 = v168 + 1 )
              {
                v166 = *v163;
                LODWORD(v1274) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v113, v166, &v1274);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                LODWORD(dwBytes) = RtlULongLongAdd(v167, (unsigned int)v1274, &pcchLength);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_132;
                v163 = (unsigned int *)pcchLength;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v163, v113, &v1296);
              v83 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_132;
              if ( v169 + 2 <= (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
              {
                v170 = v1296;
                *v169 = v113;
                *v170 = v113;
                goto LABEL_230;
              }
            }
LABEL_163:
            v83 = -1073741789;
            goto LABEL_131;
          }
          if ( v59 && !wcscmp_0(v59, L"WinSta0") && v60 && !wcscmp_0(v60, L"Default") )
          {
            v1318 = 0;
            CurrentProcess = GetCurrentProcess();
            if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1318) )
            {
              LastError = GetLastError();
              v76 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v76 = LastError < 0;
              }
              if ( !v76 )
                LastError = -2147467259;
              goto LABEL_101;
            }
            if ( (v1318 & 0xF) == 0 )
              v61 = 1;
          }
        }
        else
        {
          LastError = 0;
        }
        v62 = v61;
        goto LABEL_101;
      }
      v5[823] = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      memset_0(qword_18003DEB0, 0, sizeof(qword_18003DEB0));
      lpMem = v5;
      while ( *v5 )
      {
        v49 = -1;
        do
          ++v49;
        while ( *(_WORD *)&v5[2 * v49] );
        v50 = (HMODULE *)&qword_18003DEB0[3 * v48];
        if ( !GetModuleHandleExW(0, (LPCWSTR)v5, v50) )
        {
          v47 = -1073741702;
          break;
        }
        v51 = &v5[2 * v49];
        if ( *(_WORD *)*v50 == 23117
          && (v52 = *((int *)*v50 + 15), (unsigned int)v52 < 0x10000000)
          && (v53 = (char *)*v50 + v52, v53 >= (char *)*v50)
          && *(_DWORD *)v53 == 17744 )
        {
          if ( ((*((_WORD *)v53 + 12) - 267) & 0xFEFF) != 0 )
          {
            v47 = -1073741811;
          }
          else
          {
            v47 = 0;
            *(__int64 *)((char *)&qword_18003DEB0[3 * v48 + 1] + 4) = *((_QWORD *)v53 + 17);
            LODWORD(qword_18003DEB0[3 * v48 + 1]) = *((_DWORD *)v53 + 20);
          }
        }
        else
        {
          v47 = -1073741701;
        }
        v54 = *(_DWORD *)(v51 + 2);
        v55 = 0;
        LODWORD(v1278) = v54;
        v5 = v51 + 6;
        while ( v55 < v54 )
        {
          v56 = -1;
          do
            ++v56;
          while ( v5[v56] );
          if ( v47 >= 0 )
          {
            v57 = GetProcAddress(*v50, v5);
            if ( !v57 )
              goto LABEL_42;
            off_18003D360[v46] = v57;
            v54 = (unsigned int)v1278;
          }
          ++v46;
          v5 += v56 + 1;
          ++v55;
        }
        ++v48;
      }
LABEL_42:
      if ( lpMem )
      {
        v58 = GetProcessHeap();
        HeapFree(v58, 0, lpMem);
      }
      if ( v47 < 0 )
        goto LABEL_14;
      v3 = dword_18003E488;
    }
    dword_18003E488 = v3 + 1;
    goto LABEL_47;
  }
  v2 = -2147024809;
LABEL_1591:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1321);
  return v2;
}

```

## disassembly

```asm
0x180018a58  mov     [rsp-8+arg_10], rbx
0x180018a5d  push    rbp
0x180018a5e  push    rsi
0x180018a5f  push    rdi
0x180018a60  push    r12
0x180018a62  push    r13
0x180018a64  push    r14
0x180018a66  push    r15
0x180018a68  lea     rbp, [rsp-0E00h]
0x180018a70  sub     rsp, 0F00h
0x180018a77  mov     rax, cs:__security_cookie
0x180018a7e  xor     rax, rsp
0x180018a81  mov     [rbp+0E30h+var_40], rax
0x180018a88  mov     rax, rcx
0x180018a8b  mov     [rbp+0E30h+psz], rcx
0x180018a8f  xor     ecx, ecx
0x180018a91  mov     [rbp+0E30h+var_CD8], rdx
0x180018a98  mov     [rbp+0E30h+var_D48], rcx
0x180018a9f  test    rax, rax
0x180018aa2  jnz     short loc_180018AAE
0x180018aa4  mov     ebx, 80070057h
0x180018aa9  jmp     loc_180022E55
0x180018aae  xor     eax, eax
0x180018ab0  test    rdx, rdx
0x180018ab3  jz      short loc_180018AA4
0x180018ab5  mov     [rsp+0F30h+var_EC8], eax
0x180018ab9  lea     r14d, [rax+1]
0x180018abd  mov     [rbp+0E30h+var_DC0], rax
0x180018ac1  jmp     short loc_180018AC5
0x180018ac3  xor     eax, eax
0x180018ac5  lock cmpxchg cs:dword_18003E48C, r14d
0x180018ace  jnz     short loc_180018AC3
0x180018ad0  mov     eax, cs:dword_18003E488
0x180018ad6  lea     r15, qword_18003DEB0
0x180018add  or      ebx, 0FFFFFFFFh
0x180018ae0  lea     r13, off_18003D360
0x180018ae7  mov     [rbp+0E30h+var_DE0], ebx
0x180018aea  mov     esi, 4
0x180018aef  lea     r12d, [rsi+5Ch]
0x180018af3  test    eax, eax
0x180018af5  jnz     loc_18001903A
0x180018afb  mov     ecx, 338h; unsigned __int64
0x180018b00  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180018b05  mov     rdi, rax
0x180018b08  test    rax, rax
0x180018b0b  jz      loc_180018E82
0x180018b11  xor     ecx, ecx
0x180018b13  lea     rsi, qword_1800349B0
0x180018b1a  mov     r14, rax
0x180018b1d  mov     r12d, ecx
0x180018b20  mov     r13d, ebx
0x180018b23  mov     r10d, ecx
0x180018b26  mov     r8d, ecx
0x180018b29  mov     eax, 0AB69605Eh
0x180018b2e  lea     r15d, [rcx+67h]
0x180018b32  movzx   ecx, byte ptr [rsi+1]
0x180018b36  movzx   ebx, byte ptr [rsi]
0x180018b39  movzx   r11d, byte ptr [rsi+4]
0x180018b3e  lea     rsi, [rsi+8]
0x180018b42  shl     ebx, 8
0x180018b45  or      ebx, ecx
0x180018b47  shl     r11d, 8
0x180018b4b  movzx   ecx, byte ptr [rsi-6]
0x180018b4f  shl     ebx, 8
0x180018b52  or      ebx, ecx
0x180018b54  movzx   ecx, byte ptr [rsi-5]
0x180018b58  shl     ebx, 8
0x180018b5b  or      ebx, ecx
0x180018b5d  movzx   ecx, byte ptr [rsi-3]
0x180018b61  or      r11d, ecx
0x180018b64  mov     edx, ebx
0x180018b66  movzx   ecx, byte ptr [rsi-2]
0x180018b6a  xor     edx, r8d
0x180018b6d  mov     r8d, edx
0x180018b70  shl     r11d, 8
0x180018b74  or      r11d, ecx
0x180018b77  movzx   ecx, byte ptr [rsi-1]
0x180018b7b  shl     r11d, 8
0x180018b7f  or      r11d, ecx
0x180018b82  xor     r8d, r11d
0x180018b85  xor     r8d, r10d
0x180018b88  xor     r8d, 0AC987321h
0x180018b8f  lea     ecx, [r8+54969FA2h]
0x180018b96  ror     ecx, 1Bh
0x180018b99  imul    r9d, ecx, 137Fh
0x180018ba0  mov     ecx, r8d
0x180018ba3  ror     ecx, 16h
0x180018ba6  add     r9d, ecx
0x180018ba9  xor     r9d, edx
0x180018bac  lea     ecx, [r9+7F1137Fh]
0x180018bb3  ror     ecx, 9
0x180018bb6  imul    edx, ecx, 0AB69h
0x180018bbc  mov     ecx, r9d
0x180018bbf  ror     ecx, 1Eh
0x180018bc2  sub     edx, ecx
0x180018bc4  xor     edx, r8d
0x180018bc7  imul    r10d, edx, 605Eh
0x180018bce  mov     ecx, edx
0x180018bd0  shr     ecx, 0Dh
0x180018bd3  sub     r10d, ecx
0x180018bd6  sub     r10d, 756C8A2h
0x180018bdd  xor     r10d, r9d
0x180018be0  mov     r9d, 7F1137Fh
0x180018be6  mov     ecx, r10d
0x180018be9  xor     ecx, 0AB69h
0x180018bef  ror     ecx, 1Ah
0x180018bf2  imul    r8d, ecx, 7F1h
0x180018bf9  mov     ecx, r10d
0x180018bfc  ror     ecx, 1Eh
0x180018bff  sub     r8d, ecx
0x180018c02  xor     r8d, edx
0x180018c05  mov     ecx, r8d
0x180018c08  xor     ecx, eax
0x180018c0a  sub     r9d, ecx
0x180018c0d  xor     r9d, r10d
0x180018c10  mov     ecx, r9d
0x180018c13  mov     r10d, r9d
0x180018c16  xor     ecx, 137Fh
0x180018c1c  ror     r10d, 6
0x180018c20  imul    edx, ecx, 0AB69h
0x180018c26  xor     r10d, edx
0x180018c29  xor     r10d, r8d
0x180018c2c  lea     ecx, [r10+7F1137Fh]
0x180018c33  ror     ecx, 0Fh
0x180018c36  imul    edx, ecx, 605Eh
0x180018c3c  mov     ecx, r10d
0x180018c3f  ror     ecx, 1Eh
0x180018c42  add     edx, ecx
0x180018c44  xor     edx, r9d
0x180018c47  lea     ecx, [rdx+54969FA2h]
0x180018c4d  ror     ecx, 0Eh
0x180018c50  imul    r8d, ecx, 7F1h
0x180018c57  mov     ecx, edx
0x180018c59  ror     ecx, 18h
0x180018c5c  sub     r8d, ecx
0x180018c5f  xor     r8d, r10d
0x180018c62  mov     ecx, r8d
0x180018c65  mov     r10d, 7F1h
0x180018c6b  xor     ecx, eax
0x180018c6d  ror     ecx, 0Ch
0x180018c70  imul    r9d, ecx, 137Fh
0x180018c77  mov     ecx, r8d
0x180018c7a  ror     ecx, 0Ah
0x180018c7d  xor     r9d, ecx
0x180018c80  xor     r9d, edx
0x180018c83  mov     ecx, r9d
0x180018c86  xor     ecx, r10d
0x180018c89  imul    edx, ecx, 0AB69h
0x180018c8f  mov     ecx, r9d
0x180018c92  shr     ecx, 0Ah
0x180018c95  xor     edx, ecx
0x180018c97  xor     edx, r8d
0x180018c9a  mov     ecx, edx
0x180018c9c  not     ecx
0x180018c9e  ror     ecx, 5
0x180018ca1  add     ecx, 605Eh
0x180018ca7  imul    r8d, ecx, 7F1h
0x180018cae  xor     r8d, r9d
0x180018cb1  lea     r9d, [r8-7F1h]
0x180018cb8  xor     r9d, edx
0x180018cbb  xor     r9d, eax
0x180018cbe  mov     ecx, r9d
0x180018cc1  xor     ecx, r10d
0x180018cc4  ror     ecx, 1Eh
0x180018cc7  imul    r10d, ecx, 137Fh
0x180018cce  mov     ecx, r9d
0x180018cd1  shr     ecx, 2
0x180018cd4  add     r10d, ecx
0x180018cd7  xor     r10d, r8d
0x180018cda  lea     ecx, [r10-7F1137Fh]
0x180018ce1  ror     ecx, 6
0x180018ce4  imul    r8d, ecx, 0AB69h
0x180018ceb  mov     ecx, r10d
0x180018cee  ror     ecx, 19h
0x180018cf1  add     r8d, ecx
0x180018cf4  xor     r8d, r9d
0x180018cf7  mov     ecx, r8d
0x180018cfa  mov     r9d, r8d
0x180018cfd  xor     ecx, 137Fh
0x180018d03  ror     r9d, 9
0x180018d07  imul    edx, ecx, 605Eh
0x180018d0d  add     r9d, edx
0x180018d10  xor     r9d, r10d
0x180018d13  mov     ecx, r9d
0x180018d16  xor     ecx, 0AB69h
0x180018d1c  ror     ecx, 1Bh
0x180018d1f  imul    edx, ecx, 7F1h
0x180018d25  mov     ecx, r9d
0x180018d28  ror     ecx, 19h
0x180018d2b  add     edx, ecx
0x180018d2d  xor     edx, r8d
0x180018d30  mov     r8d, edx
0x180018d33  xor     r8d, r9d
0x180018d36  xor     r8d, 0AC987321h
0x180018d3d  mov     ecx, r8d
0x180018d40  ror     ecx, 3
0x180018d43  imul    r9d, ecx, 137Fh
0x180018d4a  sub     r9d, 0D0DD417h
0x180018d51  xor     r9d, edx
0x180018d54  lea     ecx, [r9-7F1137Fh]
0x180018d5b  ror     ecx, 1
0x180018d5d  imul    edx, ecx, 605Eh
0x180018d63  mov     ecx, r9d
0x180018d66  ror     ecx, 6
0x180018d69  sub     edx, ecx
0x180018d6b  xor     edx, r8d
0x180018d6e  lea     ecx, [rdx-54969FA2h]
0x180018d74  ror     ecx, 1Dh
0x180018d77  imul    r8d, ecx, 7F1h
0x180018d7e  mov     ecx, edx
0x180018d80  ror     ecx, 12h
0x180018d83  add     r8d, ecx
0x180018d86  xor     r8d, r9d
0x180018d89  lea     ecx, [r8-54969FA2h]
0x180018d90  ror     ecx, 11h
0x180018d93  imul    r9d, ecx, 137Fh
0x180018d9a  mov     ecx, r8d
0x180018d9d  ror     ecx, 0Eh
0x180018da0  sub     r9d, ecx
0x180018da3  xor     r9d, edx
0x180018da6  mov     ecx, r9d
0x180018da9  xor     ecx, 605Eh
0x180018daf  imul    r10d, ecx, 0AB69h
0x180018db6  mov     ecx, r9d
0x180018db9  shr     ecx, 3
0x180018dbc  xor     r10d, ecx
0x180018dbf  xor     r10d, r8d
0x180018dc2  mov     ecx, r10d
0x180018dc5  xor     ecx, 7F1137Fh
0x180018dcb  ror     ecx, 1Ch
0x180018dce  imul    r8d, ecx, 605Eh
0x180018dd5  mov     ecx, r10d
0x180018dd8  ror     ecx, 1Eh
0x180018ddb  xor     r10d, r13d
0x180018dde  mov     r13d, r11d
0x180018de1  xor     r8d, ecx
0x180018de4  xor     r8d, r9d
0x180018de7  xor     r8d, r12d
0x180018dea  mov     r12d, ebx
0x180018ded  mov     [r14+3], r8b
0x180018df1  mov     ecx, r8d
0x180018df4  ror     ecx, 8
0x180018df7  mov     [r14+7], r10b
0x180018dfb  mov     [r14+2], cl
0x180018dff  mov     ecx, r10d
0x180018e02  ror     ecx, 8
0x180018e05  mov     [r14+6], cl
0x180018e09  mov     ecx, r8d
0x180018e0c  ror     ecx, 10h
0x180018e0f  mov     [r14+1], cl
0x180018e13  mov     ecx, r10d
0x180018e16  ror     ecx, 10h
0x180018e19  mov     [r14+5], cl
0x180018e1d  mov     ecx, r8d
0x180018e20  ror     ecx, 18h
0x180018e23  mov     [r14], cl
0x180018e26  mov     ecx, r10d
0x180018e29  ror     ecx, 18h
0x180018e2c  mov     [r14+4], cl
0x180018e30  lea     r14, [r14+8]
0x180018e34  sub     r15, 1
0x180018e38  jnz     loc_180018B32
0x180018e3e  xor     ecx, ecx
0x180018e40  lea     r14d, [r15+1]
0x180018e44  mov     al, cl
0x180018e46  xor     al, [rdi+rcx]
0x180018e49  add     rcx, r14
0x180018e4c  cmp     rcx, 338h
0x180018e53  jb      short loc_180018E46
0x180018e55  movzx   ecx, al
0x180018e58  cmp     rcx, cs:qword_180034CE8
0x180018e5f  jz      short loc_180018EC6
0x180018e61  mov     rcx, rdi; void *
0x180018e64  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180018e69  mov     r12d, 60h ; '`'
0x180018e6f  lea     r13, off_18003D360
0x180018e76  lea     r15, qword_18003DEB0
0x180018e7d  lea     esi, [r12-5Ch]
0x180018e82  xor     ebx, ebx
0x180018e84  lea     rax, [rbx+rbx*2]
0x180018e88  mov     rcx, [r15+rax*8]; hLibModule
0x180018e8c  test    rcx, rcx
0x180018e8f  jz      short loc_180018E97
0x180018e91  call    cs:__imp_FreeLibrary
0x180018e97  add     rbx, r14
0x180018e9a  cmp     rbx, rsi
0x180018e9d  jnz     short loc_180018E84
0x180018e9f  mov     r8, r12; Size
0x180018ea2  xor     edx, edx; Val
0x180018ea4  mov     rcx, r15; void *
0x180018ea7  call    memset_0
0x180018eac  mov     r8d, 170h; Size
0x180018eb2  lea     rdx, off_18002E370; Src
0x180018eb9  mov     rcx, r13; void *
0x180018ebc  call    memcpy_0
0x180018ec1  jmp     loc_180019043
0x180018ec6  xor     eax, eax
0x180018ec8  lea     rcx, qword_18003DEB0; void *
0x180018ecf  xor     edx, edx; Val
0x180018ed1  mov     [rdi+337h], al
  ... truncated ...
```
