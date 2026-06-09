# CDevice::LLOCompleteLayerConstruction(void)

- ea: `0x18008c850`
- end: `0x18008fb0c`
- name: `?LLOCompleteLayerConstruction@CDevice@@QEAAJXZ`
- size: `12988`
- prototype: `__int64 __fastcall(CDevice *__hidden this)`
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008c840`

## callees

- `0x180008ae0`
- `0x180009cc0`
- `0x180011080`
- `0x180012300`
- `0x1800147d0`
- `0x18001ddd4`
- `0x18001fbd0`
- `0x180021b90`
- `0x180022400`
- `0x1800226c0`
- `0x1800229a0`
- `0x18002ba98`
- `0x18002d174`
- `0x1800327d0`
- `0x180037290`
- `0x18003b830`
- `0x1800441f0`
- `0x180044234`
- `0x18004429c`
- `0x180046168`
- `0x18004e694`
- `0x1800526e8`
- `0x180054bd0`
- `0x1800587c0`
- `0x18005a574`
- `0x180061110`
- `0x18006b8e8`
- `0x18006c184`
- `0x18006c5c0`
- `0x180074d78`
- `0x180077e40`
- `0x1800792a0`
- `0x180081364`
- `0x18008a1f8`
- `0x18008c850`
- `0x18009743c`
- `0x18009d94c`
- `0x1800a3a68`
- `0x1800a5360`
- `0x1800a9d20`
- `0x1800aa920`
- `0x1800ac684`
- `0x1800ada0c`
- `0x1800b01a0`
- `0x1800c1208`
- `0x1800ca8ec`
- `0x1800d99a4`
- `0x1800dd664`
- `0x1801681e0`
- `0x1801cb010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18008daab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18008daab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d39d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d5f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d39d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d5f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18008de81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18008f0e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18008de81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18008f0e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18008f848`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18008f848`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008cba6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fa8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008cba6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fa8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008f01d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008fa2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008f01d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008fa2f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008cb05`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008cb05`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008fa17`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008fa17`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18008ca13`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18008cc11`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18008ca13`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18008cc11`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeShaderCaps` at `0x18008ca1d`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeShaderCaps` at `0x18008ca1d`

## string_xrefs

- `0x18008cb57`: `D3D11_3SDKLayers.dll`
- `0x18008fa10`: `D3DDriverVerifier.dll`
- `0x18008f533`: `Driver doesn't support compute on FL11`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CDevice::LLOCompleteLayerConstruction(CDevice *this)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // r15
  NDXGI::CUMDAdapter *v4; // r14
  int v5; // eax
  unsigned int v6; // eax
  _DWORD *v7; // rbx
  bool v8; // r9
  int AsyncComputeShaderCaps; // eax
  int v10; // r8d
  int v11; // edx
  bool v12; // r9
  HMODULE v13; // rbx
  bool v14; // r9
  bool v15; // r9
  int v16; // eax
  bool v17; // r9
  bool v18; // r9
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  unsigned __int8 v22; // al
  int Caps; // eax
  bool v24; // r9
  int *v25; // rbx
  int v26; // ebx
  unsigned __int8 v27; // dl
  int v28; // eax
  bool v29; // cl
  bool v30; // r9
  struct CContext **v31; // rsi
  int v32; // eax
  struct IErrorInfo *v33; // r8
  bool v34; // r9
  struct CContext *v35; // rsi
  int v36; // r14d
  void *v37; // rbx
  char *v38; // rax
  void (__fastcall *v39)(__int64, unsigned int *, _QWORD); // r12
  void (__fastcall *v40)(__int64, unsigned int *, _QWORD); // rax
  __int64 v41; // rbx
  char *v42; // rcx
  char *v43; // r9
  unsigned __int64 v44; // r14
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // r8
  __int64 v47; // rsi
  unsigned __int64 v48; // rax
  char *v49; // r15
  char *v50; // rax
  __int64 v51; // rdx
  void *v52; // rcx
  unsigned __int64 v53; // rdx
  unsigned __int64 v54; // rbx
  __int64 v55; // rsi
  int v56; // r14d
  void *v57; // rbx
  __int64 v58; // rax
  int *v59; // rax
  unsigned __int64 v60; // rbx
  SIZE_T v61; // rbx
  char *v62; // r12
  char *lpMinimumApplicationAddress; // rbx
  char **v64; // r8
  unsigned __int64 v65; // rdx
  const unsigned __int64 near *v66; // rdx
  char *v67; // r9
  _BYTE *v68; // r12
  __int64 v69; // r14
  char *v70; // r15
  char *v71; // rsi
  __int64 v72; // r10
  char *v73; // r14
  unsigned __int64 v74; // r12
  _QWORD *v75; // rdx
  char *i; // rax
  __int64 v77; // rax
  unsigned __int64 v78; // r14
  _QWORD *v79; // rax
  unsigned __int64 v80; // rsi
  unsigned __int64 v81; // rax
  unsigned __int64 v82; // r13
  unsigned __int64 v83; // r12
  _QWORD *v84; // rsi
  _QWORD *v85; // r15
  __int64 v86; // r8
  __int64 v87; // r9
  unsigned __int64 v88; // r11
  __int64 v89; // rdx
  __int64 j; // rcx
  __int64 k; // rax
  unsigned __int64 v92; // rcx
  unsigned __int64 v93; // r10
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r9
  __int64 m; // rax
  unsigned __int64 v99; // rcx
  __int64 v100; // rdx
  unsigned __int64 v101; // rcx
  float v102; // xmm0_4
  unsigned __int64 v103; // r14
  float v104; // xmm2_4
  float v105; // xmm0_4
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rax
  unsigned __int64 v108; // rcx
  _QWORD *v109; // rcx
  _QWORD *v110; // r8
  __int64 v111; // rcx
  __int64 v112; // rax
  _QWORD *v113; // rdx
  unsigned __int64 dwPageSize; // rax
  unsigned __int64 v115; // rcx
  __int64 n; // rdx
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 *v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  __int64 *v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // rcx
  __int64 v127; // rcx
  float *v128; // r8
  float v129; // xmm1_4
  _QWORD *v130; // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rcx
  __int64 v134; // rcx
  __int64 v135; // rdx
  __int64 v136; // rdx
  __int64 v137; // rbx
  __int64 v138; // rax
  int v139; // edx
  char v140; // cl
  bool v141; // r9
  __int64 v142; // rcx
  unsigned int v143; // r15d
  __int64 v144; // rbx
  unsigned int Format; // eax
  unsigned int v146; // r9d
  unsigned int v147; // r12d
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 RequirementsTable; // rax
  bool v151; // r9
  __int64 v152; // rcx
  __int64 v153; // rax
  unsigned int v154; // esi
  unsigned __int8 v155; // al
  __int64 v156; // rax
  __int64 v157; // rax
  _DWORD *FormatCastSet; // r14
  char v159; // r13
  __int64 v160; // rdx
  __int64 v161; // rax
  int v162; // r15d
  __int64 v163; // rax
  struct IErrorInfo *v164; // r8
  char v165; // r9
  __int64 v166; // rcx
  int v167; // ecx
  unsigned int ii; // esi
  unsigned __int8 v169; // al
  __int64 v170; // rax
  bool v171; // r9
  __int64 v172; // rax
  unsigned int v173; // esi
  __int64 v174; // rbx
  __int64 v175; // rax
  unsigned __int8 v176; // al
  NDXGI::CUMDAdapter *v177; // rsi
  int v178; // eax
  __int64 v179; // rbx
  __int64 v180; // r8
  void (__fastcall **v181)(__int64, GUID *, __int64); // rdx
  __int64 v182; // r8
  void (__fastcall **v183)(__int64, GUID *, __int64); // rdx
  int v184; // r13d
  __int64 v185; // r8
  int (__fastcall **v186)(__int64, GUID *, __int64); // r9
  unsigned __int8 v187; // al
  unsigned __int8 v188; // cl
  __int64 v189; // rax
  int v190; // eax
  int v191; // eax
  int v192; // eax
  int v193; // eax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // r8
  int v197; // eax
  _QWORD *v198; // rdx
  FARPROC ProcAddress; // rax
  unsigned __int8 v200; // dl
  int v201; // eax
  int v202; // eax
  char v203; // cl
  unsigned __int64 v204; // rcx
  unsigned __int64 v205; // rax
  unsigned int jj; // ebx
  int v207; // eax
  signed int v208; // eax
  bool v209; // r9
  unsigned int v210; // ecx
  unsigned __int64 *v212; // r8
  __int64 v213; // rdx
  __int64 v214; // rdx
  __int64 v215; // rax
  unsigned __int64 v216; // rcx
  unsigned __int64 v217; // rcx
  unsigned __int64 v218; // r11
  unsigned __int64 *v219; // rcx
  unsigned __int64 v220; // r10
  unsigned __int64 v221; // r11
  unsigned __int64 v222; // r10
  unsigned __int64 *v223; // rcx
  unsigned __int64 *v224; // r10
  unsigned __int64 v225; // rax
  unsigned __int64 v226; // rax
  unsigned __int64 v227; // rax
  unsigned __int64 v228; // r9
  unsigned __int64 v229; // rax
  unsigned __int64 v230; // rcx
  unsigned __int64 v231; // rax
  unsigned __int64 v232; // rax
  char *v233; // r12
  char *v234; // r13
  struct IErrorInfo *v235; // r8
  bool v236; // r9
  struct IErrorInfo *v237; // r8
  bool v238; // r9
  struct IErrorInfo *v239; // r8
  bool v240; // r9
  struct IErrorInfo *v241; // r8
  bool v242; // r9
  struct IErrorInfo *v243; // r8
  bool v244; // r9
  struct IErrorInfo *v245; // r8
  bool v246; // r9
  struct IErrorInfo *v247; // r8
  bool v248; // r9
  struct IErrorInfo *v249; // r8
  bool v250; // r9
  struct IErrorInfo *v251; // r8
  bool v252; // r9
  struct IErrorInfo *v253; // r8
  bool v254; // r9
  struct IErrorInfo *v255; // r8
  bool v256; // r9
  struct IErrorInfo *v257; // r8
  bool v258; // r9
  struct IErrorInfo *v259; // r8
  bool v260; // r9
  struct IErrorInfo *v261; // r8
  bool v262; // r9
  struct IErrorInfo *v263; // r8
  bool v264; // r9
  struct IErrorInfo *v265; // r8
  bool v266; // r9
  struct IErrorInfo *v267; // r8
  bool v268; // r9
  struct IErrorInfo *v269; // r8
  bool v270; // r9
  HMODULE LibraryA; // rax
  bool v272; // r9
  HMODULE v273; // rbx
  FARPROC v274; // rax
  struct IErrorInfo *v275; // r8
  bool v276; // r9
  unsigned int v277; // [rsp+40h] [rbp-5B8h] BYREF
  void *Src; // [rsp+48h] [rbp-5B0h] BYREF
  char v279; // [rsp+50h] [rbp-5A8h]
  NDXGI::CUMDAdapter *v280; // [rsp+58h] [rbp-5A0h] BYREF
  _DWORD *v281; // [rsp+60h] [rbp-598h] BYREF
  __int128 v282; // [rsp+68h] [rbp-590h] BYREF
  __int64 v283; // [rsp+78h] [rbp-580h]
  struct _SYSTEM_INFO v284; // [rsp+80h] [rbp-578h] BYREF
  unsigned __int64 v285; // [rsp+B0h] [rbp-548h] BYREF
  int v286; // [rsp+B8h] [rbp-540h] BYREF
  __int64 v287; // [rsp+C0h] [rbp-538h]
  int v288; // [rsp+C8h] [rbp-530h] BYREF
  __int64 v289; // [rsp+D0h] [rbp-528h]
  __int64 v290; // [rsp+D8h] [rbp-520h]
  __int128 v291; // [rsp+E0h] [rbp-518h] BYREF
  __int64 v292; // [rsp+F0h] [rbp-508h]
  __int64 v293; // [rsp+F8h] [rbp-500h]
  __int128 v294; // [rsp+100h] [rbp-4F8h] BYREF
  __int64 v295; // [rsp+110h] [rbp-4E8h]
  float v296; // [rsp+118h] [rbp-4E0h] BYREF
  _QWORD *v297; // [rsp+120h] [rbp-4D8h] BYREF
  __int64 v298; // [rsp+128h] [rbp-4D0h]
  __int128 v299; // [rsp+130h] [rbp-4C8h] BYREF
  __int64 v300; // [rsp+140h] [rbp-4B8h]
  __int64 v301; // [rsp+148h] [rbp-4B0h]
  __int64 v302; // [rsp+150h] [rbp-4A8h]
  char *v303; // [rsp+160h] [rbp-498h] BYREF
  void *v304; // [rsp+168h] [rbp-490h]
  struct CDevice *v305; // [rsp+170h] [rbp-488h] BYREF
  unsigned __int64 v306; // [rsp+178h] [rbp-480h]
  _QWORD *v307; // [rsp+180h] [rbp-478h]
  _QWORD v308[2]; // [rsp+188h] [rbp-470h] BYREF
  char v309[8]; // [rsp+198h] [rbp-460h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+1A0h] [rbp-458h] BYREF
  _BYTE v311[24]; // [rsp+1D0h] [rbp-428h] BYREF
  _BYTE v312[32]; // [rsp+1E8h] [rbp-410h] BYREF
  _BYTE v313[32]; // [rsp+208h] [rbp-3F0h] BYREF
  _BYTE v314[32]; // [rsp+228h] [rbp-3D0h] BYREF
  _BYTE v315[32]; // [rsp+248h] [rbp-3B0h] BYREF
  _BYTE v316[32]; // [rsp+268h] [rbp-390h] BYREF
  _BYTE v317[32]; // [rsp+288h] [rbp-370h] BYREF
  _BYTE v318[32]; // [rsp+2A8h] [rbp-350h] BYREF
  _BYTE v319[32]; // [rsp+2C8h] [rbp-330h] BYREF
  _BYTE v320[32]; // [rsp+2E8h] [rbp-310h] BYREF
  _BYTE v321[32]; // [rsp+308h] [rbp-2F0h] BYREF
  _BYTE v322[32]; // [rsp+328h] [rbp-2D0h] BYREF
  _BYTE v323[32]; // [rsp+348h] [rbp-2B0h] BYREF
  _BYTE v324[32]; // [rsp+368h] [rbp-290h] BYREF
  _BYTE v325[32]; // [rsp+388h] [rbp-270h] BYREF
  _BYTE v326[32]; // [rsp+3A8h] [rbp-250h] BYREF
  _BYTE v327[32]; // [rsp+3C8h] [rbp-230h] BYREF
  _BYTE v328[32]; // [rsp+3E8h] [rbp-210h] BYREF
  _BYTE v329[32]; // [rsp+408h] [rbp-1F0h] BYREF
  _BYTE v330[32]; // [rsp+428h] [rbp-1D0h] BYREF
  _BYTE v331[32]; // [rsp+448h] [rbp-1B0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+468h] [rbp-190h] BYREF
  _BYTE v333[32]; // [rsp+488h] [rbp-170h] BYREF
  __int128 v334; // [rsp+4A8h] [rbp-150h] BYREF
  _QWORD v335[2]; // [rsp+4B8h] [rbp-140h] BYREF
  __int128 v336; // [rsp+4C8h] [rbp-130h]
  __int64 v337; // [rsp+4D8h] [rbp-120h]
  __int64 v338; // [rsp+4E0h] [rbp-118h]
  int v339; // [rsp+4E8h] [rbp-110h]
  int v340; // [rsp+4ECh] [rbp-10Ch]
  _QWORD v341[7]; // [rsp+4F0h] [rbp-108h] BYREF
  _QWORD *v342; // [rsp+528h] [rbp-D0h]
  _DWORD v343[32]; // [rsp+530h] [rbp-C8h]

  v2 = (_QWORD *)((char *)this + 1232);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 31))(
    *((_QWORD *)this + 31),
    &GUID_00000040_1bbe_4d12_afbf_8fdf7e0a87c7,
    (char *)this + 1232);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 31))(
    *((_QWORD *)this + 31),
    &GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
    (char *)this + 1240);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 155) + 16LL))(*((_QWORD *)this + 155));
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 31))(
    *((_QWORD *)this + 31),
    &GUID_61386220_f959_44f3_bb21_1aaa84193d9c,
    (char *)this + 1248);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 156) + 16LL))(*((_QWORD *)this + 156));
  v3 = (_QWORD *)*((_QWORD *)this + 154);
  v307 = v3;
  v4 = (NDXGI::CUMDAdapter *)v3[12];
  v280 = v4;
  *((_BYTE *)this + 1132) = !NDXGI::CUMDAdapter::IsWARP(v4);
  *((_BYTE *)this + 1136) = *((_DWORD *)v4 + 18) == 3;
  *((_BYTE *)this + 1137) = (*(unsigned int (__fastcall **)(_QWORD *))(v3[2] + 328LL))(v3 + 2) != 0;
  if ( *((_BYTE *)this + 1112) < 4u )
    goto LABEL_36;
  if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 128, 0, (char *)this + 1292, 4) < 0 )
  {
    v6 = c_DefaultShaderCaps;
    goto LABEL_8;
  }
  v5 = *((_DWORD *)this + 323);
  if ( (v5 & 1) == 0
    || (*((_BYTE *)this + 1352) = 0, *((int *)this + 320) < 40960)
    || (*((_BYTE *)this + 1257) & 1) != 0 )
  {
    v6 = v5 & 0xFFFFFFF9;
LABEL_8:
    *((_DWORD *)this + 323) = v6;
  }
  v7 = (_DWORD *)((char *)this + 1268);
  if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 129, 0, (char *)this + 1268, 4) >= 0 )
  {
    if ( !(unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent()
      || !(unsigned int)XboxIsAsyncComputeOnlyDevice(*((unsigned int *)this + 315)) )
    {
      goto LABEL_15;
    }
    AsyncComputeShaderCaps = XboxGetAsyncComputeShaderCaps();
  }
  else
  {
    AsyncComputeShaderCaps = c_DefaultShaderCaps;
  }
  *v7 = AsyncComputeShaderCaps;
LABEL_15:
  v10 = *((_DWORD *)this + 320);
  if ( v10 >= 49152 )
  {
    if ( (*(_BYTE *)v7 & 0x20) == 0 )
    {
      CModule::RecordJournal(
        (CModule *)&g_Module,
        0x887A0020,
        "FL 12+ driver incorrectly does not report support for typed UAV load additional formats.",
        v8,
        1);
      _com_error::_com_error((_com_error *)pExceptionObject, -2005270496, v235, v236);
      throw (_com_error *)pExceptionObject;
    }
    if ( v10 >= 49408 )
    {
      if ( (*(_BYTE *)v7 & 0x40) == 0 )
      {
        CModule::RecordJournal(
          (CModule *)&g_Module,
          0x887A0020,
          "FL 12.1+ driver incorrectly does not report support for Raster Order Views (ROVs).",
          v8,
          1);
        _com_error::_com_error((_com_error *)v312, -2005270496, v237, v238);
        throw (_com_error *)v312;
      }
      goto LABEL_21;
    }
  }
  if ( v10 >= 45056 )
  {
LABEL_21:
    v11 = *v7;
    if ( (*v7 & 2) == 0 )
    {
      CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Driver doesn't support compute on FL11", v8, 1);
      _com_error::_com_error((_com_error *)v313, -2005270496, v239, v240);
      throw (_com_error *)v313;
    }
    goto LABEL_24;
  }
  *v7 &= ~1u;
  v11 = *v7;
LABEL_24:
  if ( (v11 & 8) != 0 )
  {
    if ( *((_BYTE *)this + 1112) > 6u
      || *((_BYTE *)this + 1112) == 6 && HIWORD(*(_DWORD *)(*(_QWORD *)(*v2 + 96LL) + 912LL)) )
    {
      if ( v10 >= 40960 )
      {
        CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "FL10 driver asked for DX9 shaders", v8, 1);
        _com_error::_com_error((_com_error *)v314, -2005270496, v243, v244);
        throw (_com_error *)v314;
      }
    }
    else
    {
      v11 &= ~8u;
      *v7 = v11;
    }
  }
  if ( (*((_BYTE *)this + 1260) & 0x40) != 0 )
  {
    if ( (v11 & 4) == 0 )
    {
      CModule::RecordJournal((CModule *)&g_Module, 0x887A0004, "Driver doesn't support shader debugging", v8, 1);
      _com_error::_com_error((_com_error *)v315, -2005270524, v241, v242);
      throw (_com_error *)v315;
    }
    if ( v10 < 40960
      && !NDXGI::CUMDAdapter::IsExplicitDriverType(*(NDXGI::CUMDAdapter **)(*v2 + 96LL), D3D_DRIVER_TYPE_WARP) )
    {
      CModule::RecordJournal((CModule *)&g_Module, 0x887A0004, "FL9 driver can't support shader debugging", v12, 1);
      _com_error::_com_error((_com_error *)v316, -2005270524, v245, v246);
      throw (_com_error *)v316;
    }
  }
LABEL_36:
  Src = 0;
  if ( InitOnceExecuteOnce(&InitOnce, CModule::InitOnceGetProcAddress, 0, &Context) )
  {
    if ( *(_QWORD *)Context )
    {
      if ( (*(unsigned int (__fastcall **)(const char *, void **))Context)("FeatureLevelLimit", &Src) )
      {
        if ( Src )
        {
          if ( !NDXGI::CUMDAdapter::IsExplicitDriverType(*(NDXGI::CUMDAdapter **)(*v2 + 96LL), D3D_DRIVER_TYPE_WARP) )
          {
            v13 = CModule::SDKLoadLibraryW((CModule *)&g_Module, L"D3D11_3SDKLayers.dll");
            v305 = (struct CDevice *)v13;
            if ( v13 )
            {
              CModule::RecordJournal((CModule *)&g_Module, 0, "Feature level limit imposed", v14, 1);
              *((_DWORD *)this + 322) = (_DWORD)Src;
              FreeLibrary(v13);
            }
          }
        }
      }
    }
  }
  if ( *((_BYTE *)this + 1112) < 5u )
  {
    *((_QWORD *)this + 162) = c_DefaultD3D11Options;
  }
  else if ( (unsigned int)HIDWORD(v3[11]) >= 0xB000F )
  {
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 131, 0, (char *)this + 1296, 8) >= 0 )
    {
      if ( (unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent()
        && (unsigned int)XboxIsAsyncComputeOnlyDevice(*((unsigned int *)this + 315)) )
      {
        *((_DWORD *)this + 324) = 1;
      }
    }
    else
    {
      *((_QWORD *)this + 162) = c_DefaultD3D11Options;
    }
    v16 = *((_DWORD *)this + 320);
    if ( v16 == 45312 )
    {
      if ( !*((_DWORD *)this + 324) )
      {
        CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "FL11.1 driver doesn't support logic ops", v15, 1);
        _com_error::_com_error((_com_error *)v317, -2005270496, v247, v248);
        throw (_com_error *)v317;
      }
    }
    else if ( v16 < 40960 )
    {
      *((_DWORD *)this + 324) = 0;
    }
  }
  if ( (unsigned __int8)(*((_BYTE *)this + 1112) - 2) > 2u )
  {
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 132, 0, (char *)this + 1304, 4) < 0 )
      *((_DWORD *)this + 326) = c_DefaultShaderCaps;
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 134, 0, (char *)this + 1308, 8) >= 0 )
    {
      v20 = *((_DWORD *)this + 327);
      if ( (v20 & 0xFFFFFFFC) != 0 || (v21 = *((_DWORD *)this + 328), (v21 & 0xFFFFFFFC) != 0) )
      {
        CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Min precision bad values", v17, 1);
        _com_error::_com_error((_com_error *)v320, -2005270496, v255, v256);
        throw (_com_error *)v320;
      }
      if ( *((int *)this + 320) <= 37632 )
      {
        if ( (v21 & 1) != 0 && (v20 & 1) == 0 || (v21 & 2) != 0 && (v20 & 2) == 0 )
        {
          CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Min precision for VS lower than PS", v17, 1);
          _com_error::_com_error((_com_error *)v319, -2005270496, v253, v254);
          throw (_com_error *)v319;
        }
      }
      else if ( v20 != v21 )
      {
        CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Min precision mismatch", v17, 1);
        _com_error::_com_error((_com_error *)v318, -2005270496, v251, v252);
        throw (_com_error *)v318;
      }
    }
    else
    {
      *(_QWORD *)((char *)this + 1308) = c_DefaultD3D11Options;
    }
  }
  if ( *((_BYTE *)this + 1112) < 6u || (unsigned int)HIDWORD(v3[11]) < 0xB0010 || *((int *)this + 320) < 45056 )
  {
    *((_DWORD *)this + 329) = c_DefaultShaderCaps;
  }
  else
  {
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 136, 0, (char *)this + 1316, 4) < 0 )
      *((_DWORD *)this + 329) = c_DefaultShaderCaps;
    v19 = *((_DWORD *)this + 329);
    if ( (v19 & 2) != 0 )
    {
      v19 |= 1u;
      *((_DWORD *)this + 329) = v19;
    }
    if ( (v19 & 4) != 0 )
    {
      v19 |= 3u;
      *((_DWORD *)this + 329) = v19;
    }
    if ( *((int *)this + 320) >= 49152 && (v19 & 2) == 0 && !*((_BYTE *)this + 1136) )
    {
      CModule::RecordJournal(
        (CModule *)&g_Module,
        0x887A0020,
        "FL12+ driver incorrectly did not report support for tiled resources tier 2+.",
        v18,
        1);
      _com_error::_com_error((_com_error *)v321, -2005270496, v249, v250);
      throw (_com_error *)v321;
    }
  }
  v22 = *((_BYTE *)this + 1112);
  if ( v22 < 7u || *((int *)this + 320) < 45312 )
  {
    *((_DWORD *)this + 330) = 0;
  }
  else
  {
    if ( v22 == 7
      && (unsigned __int16)(HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) - 5) <= 2u )
    {
      Src = 0;
      Caps = NDXGI::CUMDAdapter::GetCaps(v4, 143, 0, &Src, 8);
      v25 = (int *)((char *)this + 1320);
      *((_DWORD *)this + 330) = (_DWORD)Src;
    }
    else
    {
      v25 = (int *)((char *)this + 1320);
      Caps = NDXGI::CUMDAdapter::GetCaps(v4, 143, 0, (char *)this + 1320, 4);
    }
    if ( Caps >= 0 )
    {
      if ( *((int *)this + 320) >= 49408 && *v25 < 1 )
      {
        CModule::RecordJournal(
          (CModule *)&g_Module,
          0x887A0020,
          "FL12.1+ driver incorrectly did not report support for conservative rast tier 1+.",
          v24,
          1);
        _com_error::_com_error((_com_error *)v322, -2005270496, v257, v258);
        throw (_com_error *)v322;
      }
    }
    else
    {
      *v25 = 0;
    }
  }
  if ( *((_BYTE *)this + 1112) <= 7u && (*((_BYTE *)this + 1112) != 7 || HIWORD(*(_DWORD *)(v3[12] + 912LL)) < 7u)
    || (int)NDXGI::CUMDAdapter::GetCaps(v4, 152, 0, (char *)this + 1324, 4) < 0 )
  {
    *((_DWORD *)this + 331) = c_DefaultShaderCaps;
  }
  if ( *((_BYTE *)this + 1112) <= 7u && (*((_BYTE *)this + 1112) != 7 || !HIWORD(*(_DWORD *)(v3[12] + 912LL))) )
  {
    *(_QWORD *)((char *)this + 1140) = c_DefaultD3D11Options;
    *((_BYTE *)this + 1156) = 0;
    *((_DWORD *)this + 291) = 0;
    goto LABEL_134;
  }
  v26 = NDXGI::CUMDAdapter::GetCaps(v4, 145, 0, (char *)this + 1140, 8);
  if ( v26 < 0 )
    *(_QWORD *)((char *)this + 1140) = c_DefaultD3D11Options;
  if ( *((_BYTE *)this + 1136) || (v277 = 0, (int)NDXGI::CUMDAdapter::GetCaps(v4, 151, 0, &v277, 4) >= 0) && v277 )
    *((_BYTE *)this + 1139) = 1;
  *((_BYTE *)this + 1138) = 1;
  v27 = *((_BYTE *)this + 1112);
  if ( v27 <= 9u )
  {
    if ( v27 != 9 )
    {
      if ( v27 <= 7u && (v27 != 7 || HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) < 6u) )
      {
        Src = 0;
        if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 146, 0, &Src, 8) < 0 )
        {
          *((_BYTE *)this + 1156) = 0;
          *((_QWORD *)this + 145) = 0;
        }
        else
        {
          *((_BYTE *)this + 1156) = HIDWORD(Src) != 0;
          v28 = (int)Src;
          *((_DWORD *)this + 290) = (_DWORD)Src;
          *((_DWORD *)this + 291) = v28;
        }
        goto LABEL_134;
      }
      goto LABEL_115;
    }
    if ( HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) < 3u )
    {
LABEL_115:
      *(_QWORD *)&v334 = 0;
      DWORD2(v334) = 0;
      *((_BYTE *)this + 1168) = 0;
      if ( v27 > 7u || HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) >= 9u )
      {
        if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 154, 0, &v334, 12) >= 0 )
          *((_BYTE *)this + 1168) = 1;
        v26 = 0;
      }
      if ( !*((_BYTE *)this + 1168) )
        v26 = NDXGI::CUMDAdapter::GetCaps(v4, 149, 0, &v334, 12);
      if ( v26 < 0 )
      {
        *((_QWORD *)this + 145) = 0;
        *((_BYTE *)this + 1156) = 0;
      }
      else
      {
        v29 = DWORD2(v334) != 0;
        *((_QWORD *)this + 145) = v334;
        *((_BYTE *)this + 1156) = v29;
      }
      goto LABEL_134;
    }
  }
  v334 = 0;
  if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 156, 0, &v334, 16) < 0 )
  {
    CModule::RecordJournal(
      (CModule *)&g_Module,
      0x887A0020,
      "Driver failed GetCaps with D3DWDDM2_2DDICAPS_TEXTURE_LAYOUT and NULL pInfo.",
      v30,
      1);
    _com_error::_com_error((_com_error *)v323, -2005270496, v259, v260);
    throw (_com_error *)v323;
  }
  *((_BYTE *)this + 1156) = DWORD2(v334) != 0;
  *((_QWORD *)this + 145) = v334;
  *((_BYTE *)this + 1169) = HIDWORD(v334) != 0;
LABEL_134:
  *(_OWORD *)((char *)this + 1336) = c_DefaultD3D11JpegOptions;
  if ( *((_BYTE *)this + 1112) > 9u
    || *((_BYTE *)this + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) >= 2u )
  {
    v277 = 0;
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v4, 155, 0, &v277, 4) >= 0 )
    {
      if ( v277 )
        *((_BYTE *)this + 1170) = 1;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11ShaderAccessRestrictedResource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D11ShaderAccessRestrictedResource>::GetImpl'::`2'::impl)
    && (*((_BYTE *)this + 1112) > 0x16u
     || *((_BYTE *)this + 1112) == 22 && HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)))
    && (int)NDXGI::CUMDAdapter::GetCaps(v4, 158, 0, (char *)this + 1328, 4) < 0 )
  {
    *((_DWORD *)this + 332) = 0;
  }
  NDXGI::CUMDAdapter::GetFenceSupport(
    *(NDXGI::CUMDAdapter **)(*((_QWORD *)this + 154) + 96LL),
    (bool *)this + 1713,
    (bool *)this + 1714);
  v340 = 0;
  v335[0] = 0;
  v335[1] = 0;
  v336 = 0;
  v337 = 0;
  v338 = 0;
  v339 = *((_DWORD *)this + 321);
  v31 = (struct CContext **)((char *)this + 1080);
  v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, _QWORD, GUID *, char *))(**((_QWORD **)this + 31)
                                                                                              + 72LL))(
          *((_QWORD *)this + 31),
          18,
          v335,
          56,
          0,
          &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7,
          (char *)this + 1080);
  if ( v32 < 0 )
  {
    *v31 = 0;
    _com_error::_com_error((_com_error *)v324, v32, v33, v34);
    throw (_com_error *)v324;
  }
  *((_DWORD *)this + 315) &= 0x7FFEFFFu;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v31 + 19) + 24LL))(*((_QWORD *)*v31 + 19));
  (*(void (__fastcall **)(struct CContext *))(*(_QWORD *)*v31 + 16LL))(*v31);
  CDDISync::CSingleThreadedLowFreqLock::CSingleThreadedLowFreqLock((CDDISync::CSingleThreadedLowFreqLock *)&v305, *v31);
  v282 = 0;
  v283 = 0;
  v277 = 0;
  v35 = *v31;
  *(_QWORD *)&v284.dwOemId = v35;
  v36 = *((_DWORD *)v35 + 922);
  LODWORD(v284.lpMinimumApplicationAddress) = v36;
  v37 = *(void **)((char *)v35 + 3692);
  *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4) = v37;
  *((_DWORD *)v35 + 922) = GetCurrentThreadId();
  *((_BYTE *)v35 + 3692) = 0;
  *(_WORD *)((char *)v35 + 3693) = *(_WORD *)((char *)&v287 + 1);
  *((_BYTE *)v35 + 3695) = BYTE3(v287);
  *((_DWORD *)v35 + 924) = 0;
  if ( *((_BYTE *)v35 + 39276) )
    v38 = (char *)*((_QWORD *)v35 + 4958);
  else
    v38 = (char *)v35 + 1480;
  v39 = (void (__fastcall *)(__int64, unsigned int *, _QWORD))&SWDC_Context::DDI_CheckDeferredContextHandleSizes_IC;
  if ( (*((_BYTE *)this + 1292) & 4) != 0 )
    v40 = (void (__fastcall *)(__int64, unsigned int *, _QWORD))*((_QWORD *)v38 + 116);
  else
    v40 = (void (__fastcall *)(__int64, unsigned int *, _QWORD))&SWDC_Context::DDI_CheckDeferredContextHandleSizes_IC;
  v40(*((_QWORD *)this + 135) + 40768LL, &v277, 0);
  *((_DWORD *)v35 + 922) = v36;
  *(_QWORD *)((char *)v35 + 3692) = v37;
  v41 = v277;
  v42 = (char *)*((_QWORD *)&v282 + 1);
  v43 = (char *)v282;
  v44 = (__int64)(*((_QWORD *)&v282 + 1) - v282) >> 4;
  if ( v277 >= v44 )
  {
    if ( v277 <= v44 )
      goto LABEL_183;
    v45 = (v283 - (__int64)v282) >> 4;
    if ( v277 <= v45 )
    {
      v54 = v277 - v44;
      if ( v54 )
      {
        do
        {
          *(_OWORD *)v42 = 0;
          v42 += 16;
          --v54;
        }
        while ( v54 );
        v43 = (char *)v282;
      }
      goto LABEL_182;
    }
    v46 = v45 >> 1;
    v47 = 0xFFFFFFFFFFFFFFFLL;
    if ( v45 <= 0xFFFFFFFFFFFFFFFLL - (v45 >> 1) )
    {
      if ( v46 + v45 >= v277 )
      {
        if ( v46 + v45 > 0xFFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v47 = v46 + v45;
      }
      else
      {
        v47 = v277;
      }
      v48 = 16 * v47;
      if ( !(16 * v47) )
      {
        v49 = 0;
LABEL_169:
        v50 = &v49[16 * v44];
        v51 = v41 - v44;
        if ( v41 != v44 )
        {
          do
          {
            *(_OWORD *)v50 = 0;
            v50 += 16;
            --v51;
          }
          while ( v51 );
          v42 = (char *)*((_QWORD *)&v282 + 1);
          v43 = (char *)v282;
        }
        std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
          v43,
          v42,
          v49);
        v52 = (void *)v282;
        if ( (_QWORD)v282 )
        {
          v53 = (v283 - v282) & 0xFFFFFFFFFFFFFFF0uLL;
          if ( v53 >= 0x1000 )
          {
            if ( (unsigned __int64)(v282 - *(_QWORD *)(v282 - 8) - 8) > 0x1F )
              __fastfail(5u);
            LODWORD(v53) = v53 + 39;
            v52 = *(void **)(v282 - 8);
          }
          SmallDDIElLayout::operator delete(v52, v53);
        }
        v43 = v49;
        *(_QWORD *)&v282 = v49;
        v42 = &v49[16 * v41];
        v283 = (__int64)&v49[16 * v47];
        goto LABEL_182;
      }
      if ( v48 < 0x1000 )
      {
        v49 = (char *)operator new(16 * v47);
        goto LABEL_168;
      }
    }
    else
    {
      v48 = -16;
    }
    v49 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v48);
LABEL_168:
    v42 = (char *)*((_QWORD *)&v282 + 1);
    v43 = (char *)v282;
    goto LABEL_169;
  }
  v42 = (char *)(v282 + 16LL * v277);
LABEL_182:
  *((_QWORD *)&v282 + 1) = v42;
LABEL_183:
  v277 = (v42 - v43) >> 4;
  v55 = *((_QWORD *)this + 135);
  *(_QWORD *)&v284.dwOemId = v55;
  v56 = *(_DWORD *)(v55 + 3688);
  LODWORD(v284.lpMinimumApplicationAddress) = v56;
  v57 = *(void **)(v55 + 3692);
  *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4) = v57;
  *(_DWORD *)(v55 + 3688) = GetCurrentThreadId();
  *(_BYTE *)(v55 + 3692) = 0;
  *(_WORD *)(v55 + 3693) = *(_WORD *)((char *)&v287 + 1);
  *(_BYTE *)(v55 + 3695) = BYTE3(v287);
  *(_DWORD *)(v55 + 3696) = 0;
  if ( *(_BYTE *)(v55 + 39276) )
    v58 = *(_QWORD *)(v55 + 39664);
  else
    v58 = v55 + 1480;
  if ( (*((_BYTE *)this + 1292) & 4) != 0 )
    v39 = *(void (__fastcall **)(__int64, unsigned int *, _QWORD))(v58 + 928);
  v39(*((_QWORD *)this + 135) + 40768LL, &v277, v282);
  if ( v277 < (unsigned __int64)((__int64)(*((_QWORD *)&v282 + 1) - v282) >> 4) )
    *((_QWORD *)&v282 + 1) = v282 + 16LL * v277;
  *(_DWORD *)(v55 + 3688) = v56;
  *(_QWORD *)(v55 + 3692) = v57;
  v308[0] = 24;
  v308[1] = 16;
  v59 = (int *)v282;
  memset(&v284, 0, 24);
  v287 = 0;
  v60 = ((__int64)(*((_QWORD *)&v282 + 1) - v282) >> 4) + 2;
  if ( (__int64)(*((_QWORD *)&v282 + 1) - v282) >> 4 == -2 )
  {
    lpMinimumApplicationAddress = (char *)v284.lpMinimumApplicationAddress;
    v62 = *(char **)&v284.dwOemId;
    Src = *(void **)&v284.dwOemId;
  }
  else
  {
    if ( v60 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<CDestructionNotifier::CallbackRecord>::_Xlength();
    v61 = 8 * v60;
    if ( v61 )
    {
      if ( v61 < 0x1000 )
        v62 = (char *)operator new(v61);
      else
        v62 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v61);
      Src = v62;
    }
    else
    {
      v62 = 0;
      Src = 0;
    }
    *(_QWORD *)&v284.dwOemId = v62;
    v287 = (__int64)&v62[v61];
    v284.lpMaximumApplicationAddress = &v62[v61];
    std::_Zero_range<unsigned __int64 *>(v62, &v62[v61]);
    lpMinimumApplicationAddress = &v62[v61];
    v284.lpMinimumApplicationAddress = lpMinimumApplicationAddress;
    v59 = (int *)v282;
  }
  v64 = (char **)v62;
  while ( v59 != *((int **)&v282 + 1) )
  {
    v65 = *v59;
    if ( v65 >= 0x14 )
    {
      OutputDebugStringA("D3D11: Driver internal error - invalid handle type returned.");
      _com_error::_com_error((_com_error *)v325, -2005270496, v261, v262);
      throw (_com_error *)v325;
    }
    v66 = (&c_aAPICLSSizes)[v65];
    v67 = (char *)v66 + *((_QWORD *)v59 + 1);
    if ( v67 < (char *)v66 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)v311);
      throw (std::bad_alloc *)v311;
    }
    *v64++ = v67;
    v59 += 4;
  }
  std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
    v308,
    v309,
    v64);
  v68 = Src;
  v69 = (lpMinimumApplicationAddress - (_BYTE *)Src) >> 3;
  v70 = lpMinimumApplicationAddress;
  v71 = (char *)Src;
  while ( 1 )
  {
    v72 = (v70 - v71) >> 3;
    if ( v72 <= 32 )
    {
      if ( v71 != v70 )
      {
        v73 = v71 + 8;
        if ( v71 + 8 != v70 )
        {
          do
          {
            v74 = *(_QWORD *)v73;
            v75 = v73;
            if ( *(_QWORD *)v73 >= *(_QWORD *)v71 )
            {
              for ( i = v73; ; v75 = i )
              {
                i -= 8;
                if ( v74 >= *(_QWORD *)i )
                  break;
                *v75 = *(_QWORD *)i;
              }
              *v75 = v74;
            }
            else
            {
              std::_Copy_backward_memmove<SmallDDIElLayout::SmallDDIInputEl *,SmallDDIElLayout::SmallDDIInputEl *>(v71);
              *(_QWORD *)v71 = v74;
            }
            v73 += 8;
          }
          while ( v73 != v70 );
          v68 = Src;
        }
      }
      goto LABEL_217;
    }
    if ( v69 <= 0 )
      break;
    v212 = (unsigned __int64 *)&v71[8 * ((v70 - v71) >> 4)];
    v213 = (v70 - 8 - v71) >> 3;
    if ( v213 <= 40 )
    {
      v231 = *v212;
      if ( *v212 < *(_QWORD *)v71 )
      {
        *v212 = *(_QWORD *)v71;
        *(_QWORD *)v71 = v231;
      }
      v232 = *((_QWORD *)v70 - 1);
      if ( v232 < *v212 )
      {
        *((_QWORD *)v70 - 1) = *v212;
        *v212 = v232;
        if ( v232 < *(_QWORD *)v71 )
        {
          *v212 = *(_QWORD *)v71;
          *(_QWORD *)v71 = v232;
        }
      }
    }
    else
    {
      v214 = (v213 + 1) >> 3;
      v215 = 8 * v214;
      v216 = *(_QWORD *)&v71[8 * v214];
      if ( v216 < *(_QWORD *)v71 )
      {
        *(_QWORD *)&v71[8 * v214] = *(_QWORD *)v71;
        *(_QWORD *)v71 = v216;
      }
      v217 = *(_QWORD *)&v71[16 * v214];
      v218 = *(_QWORD *)&v71[8 * v214];
      if ( v217 < v218 )
      {
        *(_QWORD *)&v71[16 * v214] = v218;
        *(_QWORD *)&v71[8 * v214] = v217;
        if ( v217 < *(_QWORD *)v71 )
        {
          *(_QWORD *)&v71[8 * v214] = *(_QWORD *)v71;
          *(_QWORD *)v71 = v217;
        }
      }
      v219 = &v212[v215 / 0xFFFFFFFFFFFFFFF8uLL];
      v220 = *v212;
      v221 = v212[-v214];
      if ( *v212 < v221 )
      {
        *v212 = v221;
        *v219 = v220;
      }
      v222 = v212[(unsigned __int64)v215 / 8];
      if ( v222 < *v212 )
      {
        v212[(unsigned __int64)v215 / 8] = *v212;
        *v212 = v222;
        if ( v222 < *v219 )
        {
          *v212 = *v219;
          *v219 = v222;
        }
      }
      v223 = (unsigned __int64 *)&v70[-8 * v214 - 8];
      v224 = (unsigned __int64 *)&v70[-16 * v214 - 8];
      v225 = *v223;
      if ( *v223 < *v224 )
      {
        *v223 = *v224;
        *v224 = v225;
      }
      v226 = *((_QWORD *)v70 - 1);
      if ( v226 < *v223 )
      {
        *((_QWORD *)v70 - 1) = *v223;
        *v223 = v226;
        if ( v226 < *v224 )
        {
          *v223 = *v224;
          *v224 = v226;
        }
      }
      v227 = *(_QWORD *)&v71[8 * v214];
      v228 = *v212;
      if ( *v212 < v227 )
      {
        *v212 = v227;
        *(_QWORD *)&v71[8 * v214] = v228;
      }
      v229 = *v223;
      if ( *v223 < *v212 )
      {
        *v223 = *v212;
        *v212 = v229;
        v230 = *(_QWORD *)&v71[8 * v214];
        if ( v229 < v230 )
        {
          *v212 = v230;
          *(_QWORD *)&v71[8 * v214] = v229;
        }
      }
    }
    std::_Partition_by_pivot_unchecked<CAsynchronous<ID3D11Asynchronous> * *,std::less<void>>(&v303, v71, v212, v70);
    v69 = (v69 >> 2) + (v69 >> 1);
    v233 = (char *)v304;
    v234 = v303;
    if ( (__int64)((v303 - v71) & 0xFFFFFFFFFFFFFFF8uLL) >= (__int64)((v70 - (_BYTE *)v304) & 0xFFFFFFFFFFFFFFF8uLL) )
    {
      std::_Sort_unchecked<unsigned __int64 *,std::less<void>>(v304);
      v70 = v234;
    }
    else
    {
      std::_Sort_unchecked<unsigned __int64 *,std::less<void>>(v71);
      v71 = v233;
    }
    v68 = Src;
  }
  v86 = (v70 - v71) >> 4;
  if ( v86 > 0 )
  {
    v87 = (v72 - 1) >> 1;
    do
    {
      --v86;
      v88 = *(_QWORD *)&v71[8 * v86];
      v89 = v86;
      for ( j = v86; j < v87; v89 = j )
      {
        j = 2 * j + 2;
        if ( *(_QWORD *)&v71[8 * j] < *(_QWORD *)&v71[8 * j - 8] )
          --j;
        *(_QWORD *)&v71[8 * v89] = *(_QWORD *)&v71[8 * j];
      }
      if ( j == v87 && (v72 & 1) == 0 )
      {
        *(_QWORD *)&v71[8 * v89] = *(_QWORD *)&v71[8 * v72 - 8];
        v89 = v72 - 1;
      }
      for ( k = (v89 - 1) >> 1; v86 < v89; k = (k - 1) >> 1 )
      {
        v92 = *(_QWORD *)&v71[8 * k];
        if ( v92 >= v88 )
          break;
        *(_QWORD *)&v71[8 * v89] = v92;
        v89 = k;
      }
      *(_QWORD *)&v71[8 * v89] = v88;
    }
    while ( v86 > 0 );
  }
  do
  {
    if ( (__int64)((v70 - v71) & 0xFFFFFFFFFFFFFFF8uLL) >= 16 )
    {
      v93 = *((_QWORD *)v70 - 1);
      *((_QWORD *)v70 - 1) = *(_QWORD *)v71;
      v94 = (v70 - 8 - v71) >> 3;
      v95 = 0;
      v96 = 0;
      v97 = (v94 - 1) >> 1;
      if ( v97 > 0 )
      {
        do
        {
          v96 = 2 * v96 + 2;
          if ( *(_QWORD *)&v71[8 * v96] < *(_QWORD *)&v71[8 * v96 - 8] )
            --v96;
          *(_QWORD *)&v71[8 * v95] = *(_QWORD *)&v71[8 * v96];
          v95 = v96;
        }
        while ( v96 < v97 );
      }
      if ( v96 == v97 && (v94 & 1) == 0 )
      {
        *(_QWORD *)&v71[8 * v95] = *(_QWORD *)&v71[8 * v94 - 8];
        v95 = v94 - 1;
      }
      for ( m = (v95 - 1) >> 1; v95 > 0; m = (m - 1) >> 1 )
      {
        v99 = *(_QWORD *)&v71[8 * m];
        if ( v99 >= v93 )
          break;
        *(_QWORD *)&v71[8 * v95] = v99;
        v95 = m;
      }
      *(_QWORD *)&v71[8 * v95] = v93;
    }
    v70 -= 8;
  }
  while ( (__int64)((v70 - v71) & 0xFFFFFFFFFFFFFFF8uLL) >= 16 );
LABEL_217:
  v77 = std::_Unique_vectorized<unsigned __int64>(v68, lpMinimumApplicationAddress);
  if ( (char *)v77 != lpMinimumApplicationAddress )
  {
    lpMinimumApplicationAddress = (char *)std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
                                            lpMinimumApplicationAddress,
                                            lpMinimumApplicationAddress,
                                            v77);
    v284.lpMinimumApplicationAddress = lpMinimumApplicationAddress;
  }
  v78 = (lpMinimumApplicationAddress - v68) >> 3;
  v306 = v78;
  v289 = 0;
  v290 = 0;
  v291 = 0;
  v292 = 0;
  v293 = 0;
  v294 = 0;
  v295 = 0;
  v281 = &v296;
  v296 = 0.0;
  v297 = 0;
  v298 = 0;
  v79 = operator new(0x20u);
  *v79 = v79;
  v79[1] = v79;
  v297 = v79;
  v299 = 0;
  v300 = 0;
  v301 = 7;
  v302 = 8;
  v296 = 1.0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,CCLSAllocator::ID>>>>>>::_Assign_grow(
    &v299,
    16,
    v79);
  v80 = 0;
  v81 = 0;
  while ( 1 )
  {
    v285 = v81;
    v281 = (_DWORD *)v80;
    if ( v81 >= v78 )
      break;
    v82 = (*(_QWORD *)&v68[8 * v81] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    _mm_lfence();
    v83 = 0x100000001B3LL
        * (HIBYTE(v82)
         ^ (0x100000001B3LL
          * (BYTE6(v82)
           ^ (0x100000001B3LL
            * (BYTE5(v82)
             ^ (0x100000001B3LL
              * (BYTE4(v82)
               ^ (0x100000001B3LL
                * (BYTE3(v82)
                 ^ (0x100000001B3LL
                  * (BYTE2(v82)
                   ^ (0x100000001B3LL * (BYTE1(v82) ^ (0x100000001B3LL * ((unsigned __int8)v82 ^ 0xCBF29CE484222325uLL)))))))))))))));
    v84 = *(_QWORD **)(v299 + 16 * (v83 & v301) + 8);
    v85 = v297;
    if ( v84 == v297 )
    {
LABEL_225:
      if ( v298 == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("unordered_map/set too long");
      v303 = (char *)&v297;
      v304 = 0;
      v84 = operator new(0x20u);
      v304 = v84;
      v84[2] = v82;
      *((_DWORD *)v84 + 7) = -1;
      v100 = v298;
      v101 = v298 + 1;
      if ( v298 + 1 < 0 )
        v102 = (float)(int)(v101 & 1 | (v101 >> 1)) + (float)(int)(v101 & 1 | (v101 >> 1));
      else
        v102 = (float)(int)v101;
      v103 = v302;
      if ( v302 < 0 )
        v104 = (float)(v302 & 1 | (unsigned int)((unsigned __int64)v302 >> 1))
             + (float)(v302 & 1 | (unsigned int)((unsigned __int64)v302 >> 1));
      else
        v104 = (float)(int)v302;
      if ( (float)(v102 / v104) > v296 )
      {
        v105 = o_ceilf_0(v102 / v296);
        v106 = 0;
        if ( v105 >= 9.223372e18 )
        {
          v105 = v105 - 9.223372e18;
          if ( v105 < 9.223372e18 )
            v106 = 0x8000000000000000uLL;
        }
        v107 = v106 + (unsigned int)(int)v105;
        v108 = 8;
        if ( v107 > 8 )
          v108 = v107;
        if ( v103 < v108 )
        {
          if ( v103 >= 0x200 || (v103 *= 8LL, v103 < v108) )
            v103 = v108;
        }
        std::_Hash<std::_Umap_traits<unsigned __int64,CCLSAllocator::ID,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,CCLSAllocator::ID>>,0>>::_Forced_rehash(
          &v296,
          v103);
        v109 = *(_QWORD **)(v299 + 16 * (v83 & v301) + 8);
        v85 = v297;
        if ( v109 != v297 )
        {
          while ( v84[2] != v109[2] )
          {
            if ( v109 == *(_QWORD **)(v299 + 16 * (v83 & v301)) )
            {
              v85 = v109;
              goto LABEL_277;
            }
            v109 = (_QWORD *)v109[1];
          }
          v85 = (_QWORD *)*v109;
        }
LABEL_277:
        v100 = v298;
      }
      v304 = 0;
      v110 = (_QWORD *)v85[1];
      v298 = v100 + 1;
      *v84 = v85;
      v84[1] = v110;
      *v110 = v84;
      v85[1] = v84;
      v111 = v299;
      v112 = 2 * (v83 & v301);
      v113 = *(_QWORD **)(v299 + 16 * (v83 & v301));
      if ( v113 == v297 )
      {
        *(_QWORD *)(v299 + 16 * (v83 & v301)) = v84;
        goto LABEL_283;
      }
      if ( v113 == v85 )
      {
        *(_QWORD *)(v299 + 16 * (v83 & v301)) = v84;
      }
      else if ( *(_QWORD **)(v299 + 16 * (v83 & v301) + 8) == v110 )
      {
LABEL_283:
        *(_QWORD *)(v111 + 8 * v112 + 8) = v84;
      }
      v78 = v306;
      goto LABEL_285;
    }
    while ( v82 != v84[2] )
    {
      if ( v84 == *(_QWORD **)(v299 + 16 * (v83 & v301)) )
      {
        v85 = v84;
        goto LABEL_225;
      }
      v84 = (_QWORD *)v84[1];
    }
LABEL_285:
    *((_DWORD *)v84 + 7) = -1;
    v80 = (unsigned __int64)v281;
    if ( (unsigned __int64)v281 <= v82 )
      v80 = v82;
    v81 = v285 + 1;
    v68 = Src;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwPageSize = SystemInfo.dwPageSize;
  if ( v80 >= SystemInfo.dwPageSize )
    dwPageSize = v80;
  v115 = 1;
  for ( n = 0; v115 < dwPageSize; ++n )
    v115 *= 2LL;
  v117 = *((_QWORD *)this + 380);
  *((_QWORD *)this + 380) = n;
  v289 = v117;
  v118 = *((_QWORD *)this + 381);
  *((_QWORD *)this + 381) = v115 >> 3;
  v290 = v118;
  v119 = (__int64 *)((char *)this + 3056);
  if ( (__int128 *)((char *)this + 3056) != &v291 )
  {
    v120 = *v119;
    *v119 = v291;
    *(_QWORD *)&v291 = v120;
    v121 = *((_QWORD *)this + 383);
    *((_QWORD *)this + 383) = *((_QWORD *)&v291 + 1);
    *((_QWORD *)&v291 + 1) = v121;
    v122 = *((_QWORD *)this + 384);
    *((_QWORD *)this + 384) = v292;
    v292 = v122;
    v123 = *((_QWORD *)this + 385);
    *((_QWORD *)this + 385) = v293;
    v293 = v123;
  }
  v124 = (__int64 *)((char *)this + 3088);
  if ( (__int128 *)((char *)this + 3088) != &v294 )
  {
    v125 = *v124;
    *v124 = v294;
    *(_QWORD *)&v294 = v125;
    v126 = *((_QWORD *)this + 387);
    *((_QWORD *)this + 387) = *((_QWORD *)&v294 + 1);
    *((_QWORD *)&v294 + 1) = v126;
    v127 = *((_QWORD *)this + 388);
    *((_QWORD *)this + 388) = v295;
    v295 = v127;
  }
  v128 = (float *)((char *)this + 3112);
  if ( (float *)((char *)this + 3112) != &v296 )
  {
    v129 = *v128;
    *v128 = v296;
    v296 = v129;
    v130 = (_QWORD *)*((_QWORD *)this + 390);
    *((_QWORD *)this + 390) = v297;
    v297 = v130;
    v131 = *((_QWORD *)this + 391);
    *((_QWORD *)this + 391) = v298;
    v298 = v131;
    v132 = *((_QWORD *)this + 392);
    *((_QWORD *)this + 392) = v299;
    *(_QWORD *)&v299 = v132;
    v133 = *((_QWORD *)this + 393);
    *((_QWORD *)this + 393) = *((_QWORD *)&v299 + 1);
    *((_QWORD *)&v299 + 1) = v133;
    v134 = *((_QWORD *)this + 394);
    *((_QWORD *)this + 394) = v300;
    v300 = v134;
    v135 = *((_QWORD *)this + 395);
    *((_QWORD *)this + 395) = v301;
    v301 = v135;
    v136 = *((_QWORD *)this + 396);
    *((_QWORD *)this + 396) = v302;
    v302 = v136;
  }
  CCLSAllocator::Allocate((char *)this + 3040, &v334, *((_QWORD *)lpMinimumApplicationAddress - 1));
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(&v296);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,CPrivateData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,CPrivateData>>>>>>(&v294);
  std::vector<unsigned int>::_Tidy(&v291);
  if ( v68 )
    std::_Deallocate<16>(v68, (v287 - (_QWORD)v68) & 0xFFFFFFFFFFFFFFF8uLL);
  if ( (_QWORD)v282 )
  {
    std::_Deallocate<16>(v282, (v283 - v282) & 0xFFFFFFFFFFFFFFF0uLL);
    v282 = 0;
    v283 = 0;
  }
  DDIContextST::DDIContextST(&v284, *((_QWORD *)this + 135), 0);
  *(_QWORD *)&v334 = 0;
  DWORD2(v334) = 0;
  v137 = *(_QWORD *)&v284.dwOemId;
  if ( *(_BYTE *)(*(_QWORD *)&v284.dwOemId + 39276LL) )
    v138 = *(_QWORD *)(*(_QWORD *)&v284.dwOemId + 39664LL);
  else
    v138 = *(_QWORD *)&v284.dwOemId + 1480LL;
  (*(void (__fastcall **)(__int64, __int128 *))(v138 + 776))(*((_QWORD *)this + 135) + 40768LL, &v334);
  v139 = v334;
  if ( (int)v334 < 0x40000000 )
    v139 = 0;
  LODWORD(v334) = v139;
  v140 = BYTE8(v334);
  if ( BYTE8(v334) >= 4u )
  {
    v140 = 4;
  }
  else if ( BYTE8(v334) <= 1u )
  {
    v140 = 1;
  }
  BYTE8(v334) = v140;
  *((_DWORD *)this + 304) = v139;
  *((_DWORD *)this + 305) = DWORD1(v334);
  *((_BYTE *)this + 1224) = v140;
  *(_DWORD *)(v137 + 3688) = v284.lpMinimumApplicationAddress;
  *(_QWORD *)(v137 + 3692) = *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4);
  if ( *((int *)this + 320) < 40960 )
    *((_DWORD *)this + 325) = 0;
  if ( *((_DWORD *)this + 325) )
  {
    DDIContextST::DDIContextST(&v284, *((_QWORD *)this + 135), 0);
    v142 = *(_QWORD *)&v284.dwOemId;
    if ( !*(_QWORD *)(*(_QWORD *)&v284.dwOemId + 2688LL) )
    {
      CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "pfnAssignDebugBinary is null, but expected", v141, 1);
      _com_error::_com_error((_com_error *)v326, -2005270496, v263, v264);
      throw (_com_error *)v326;
    }
    *(_DWORD *)(*(_QWORD *)&v284.dwOemId + 3688LL) = v284.lpMinimumApplicationAddress;
    *(_QWORD *)(v142 + 3692) = *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4);
  }
  if ( *((int *)this + 320) >= 40960 )
  {
    DDIContextST::DDIContextST(&v284, *((_QWORD *)this + 135), 0);
    v143 = 0;
    LODWORD(Src) = 0;
    v144 = *(_QWORD *)&v284.dwOemId;
    while ( 1 )
    {
      Format = CD3D11FormatHelper::GetFormat(v143, *((unsigned int *)this + 320), *((unsigned int *)this + 279));
      v147 = Format;
      if ( Format == -1 )
        break;
      if ( (unsigned __int8)CD3D11FormatHelper::APIFormatExists(Format, v146) )
      {
        v148 = 0xFFFFFFFFLL;
        if ( v147 < 0xC0 )
          v148 = v147;
        if ( (dword_1801D8618[10 * v148] & 0x1800) == 0x1000 )
        {
          LODWORD(v285) = 0;
          if ( *(_BYTE *)(v144 + 39276) )
            v149 = *(_QWORD *)(v144 + 39664);
          else
            v149 = v144 + 1480;
          (*(void (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(v149 + 760))(
            *((_QWORD *)this + 135) + 40768LL,
            v147,
            &v285);
          RequirementsTable = CD3D11FormatHelper::GetRequirementsTable(
                                *((unsigned int *)this + 320),
                                *((unsigned int *)this + 279));
          v152 = 0xFFFFFFFFLL;
          if ( v147 < 0xC0 )
            v152 = v147;
          if ( (v285 & 8) != 0 && (*(_DWORD *)(RequirementsTable + 12 * v152 + 4) & 0x3000) == 0x3000 )
          {
            v153 = 0xFFFFFFFFLL;
            if ( v147 < 0xC0 )
              v153 = v147;
            if ( (dword_1801D8618[10 * v153] & 0x400) != 0 )
            {
              CModule::RecordJournal(
                (CModule *)&g_Module,
                0x887A0020,
                "Driver claimed MSAA support when it shouldn't",
                v151,
                1);
              _com_error::_com_error((_com_error *)v331, -2005270496, v265, v266);
              throw (_com_error *)v331;
            }
          }
          v154 = 2;
          while ( v154 < 0x20 )
          {
            v277 = 0;
            v155 = *((_BYTE *)this + 1112);
            if ( v155 >= 6u || v155 == 1 )
            {
              if ( *(_BYTE *)(v144 + 39276) )
                v157 = *(_QWORD *)(v144 + 39664);
              else
                v157 = v144 + 1480;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int *))(v157 + 768))(
                *((_QWORD *)this + 135) + 40768LL,
                v147,
                v154,
                0,
                &v277);
              v343[v154++] = v277;
            }
            else
            {
              if ( *(_BYTE *)(v144 + 39276) )
                v156 = *(_QWORD *)(v144 + 39664);
              else
                v156 = v144 + 1480;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(v156 + 768))(
                *((_QWORD *)this + 135) + 40768LL,
                v147,
                v154,
                &v277);
              v343[v154++] = v277;
            }
          }
          FormatCastSet = (_DWORD *)CD3D11FormatHelper::GetFormatCastSet(
                                      v147,
                                      *((unsigned int *)this + 320),
                                      *((unsigned int *)this + 279));
          v159 = 0;
          v279 = 0;
          while ( 2 )
          {
            v160 = (unsigned int)*FormatCastSet;
            if ( !(_DWORD)v160 )
            {
              v143 = (unsigned int)Src;
              break;
            }
            if ( (_DWORD)v160 != v147 )
            {
              LODWORD(v281) = 0;
              if ( *(_BYTE *)(v144 + 39276) )
                v161 = *(_QWORD *)(v144 + 39664);
              else
                v161 = v144 + 1480;
              (*(void (__fastcall **)(__int64, __int64, _DWORD **))(v161 + 760))(
                *((_QWORD *)this + 135) + 40768LL,
                v160,
                &v281);
              v162 = (unsigned __int8)v281 & 8;
              v163 = CD3D11FormatHelper::GetRequirementsTable(
                       *((unsigned int *)this + 320),
                       *((unsigned int *)this + 279));
              v166 = 0xFFFFFFFFLL;
              if ( *FormatCastSet < 0xC0u )
                v166 = (unsigned int)*FormatCastSet;
              v167 = (int)(*(_DWORD *)(v163 + 12 * v166 + 4) << 18) >> 30;
              if ( v162 )
              {
                if ( v167 == -1 )
                {
                  _com_error::_com_error((_com_error *)v327, -2005270496, v164, v165);
                  throw (_com_error *)v327;
                }
LABEL_359:
                if ( v279 )
                {
                  if ( v159 != v165 )
                  {
                    _com_error::_com_error((_com_error *)v328, -2005270496, v164, v165);
                    throw (_com_error *)v328;
                  }
                }
                else
                {
                  v159 = v165;
                  v279 = 1;
                }
              }
              else if ( v167 != -1 )
              {
                goto LABEL_359;
              }
              for ( ii = 2; ii < 0x20; ++ii )
              {
                v277 = 0;
                v169 = *((_BYTE *)this + 1112);
                if ( v169 >= 6u || v169 == 1 )
                {
                  if ( *(_BYTE *)(v144 + 39276) )
                    v172 = *(_QWORD *)(v144 + 39664);
                  else
                    v172 = v144 + 1480;
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int *))(v172 + 768))(
                    *((_QWORD *)this + 135) + 40768LL,
                    (unsigned int)*FormatCastSet,
                    ii,
                    0,
                    &v277);
                }
                else
                {
                  if ( *(_BYTE *)(v144 + 39276) )
                    v170 = *(_QWORD *)(v144 + 39664);
                  else
                    v170 = v144 + 1480;
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(v170 + 768))(
                    *((_QWORD *)this + 135) + 40768LL,
                    (unsigned int)*FormatCastSet,
                    ii,
                    &v277);
                }
                if ( v162 )
                {
                  if ( v277 != v343[ii] )
                  {
                    CModule::RecordJournal(
                      (CModule *)&g_Module,
                      0x887A0020,
                      "MSAA quality for parent != child",
                      v171,
                      1);
                    _com_error::_com_error((_com_error *)v329, -2005270496, v267, v268);
                    throw (_com_error *)v329;
                  }
                }
                else if ( v277 )
                {
                  CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "MSAA quality reported to be 0", v171, 1);
                  _com_error::_com_error((_com_error *)v330, -2005270496, v269, v270);
                  throw (_com_error *)v330;
                }
              }
            }
            ++FormatCastSet;
            continue;
          }
        }
      }
      LODWORD(Src) = ++v143;
    }
    *(_DWORD *)(v144 + 3688) = v284.lpMinimumApplicationAddress;
    *(_QWORD *)(v144 + 3692) = *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4);
  }
  if ( (*((_BYTE *)this + 1268) & 0x20) != 0 )
  {
    *((_BYTE *)this + 1272) = 1;
  }
  else
  {
    DDIContextST::DDIContextST(&v284, *((_QWORD *)this + 135), 0);
    v287 = 0x3E00000032LL;
    v173 = 0;
    v174 = *(_QWORD *)&v284.dwOemId;
    while ( v173 < 2 )
    {
      LODWORD(Src) = 0;
      if ( *(_BYTE *)(v174 + 39276) )
        v175 = *(_QWORD *)(v174 + 39664);
      else
        v175 = v174 + 1480;
      (*(void (__fastcall **)(__int64, _QWORD, void **))(v175 + 760))(
        *((_QWORD *)this + 135) + 40768LL,
        *((unsigned int *)&v287 + v173),
        &Src);
      if ( ((unsigned int)Src & 0x20000) != 0 )
      {
        *((_BYTE *)this + 1272) = 1;
        break;
      }
      ++v173;
    }
    *(_DWORD *)(v174 + 3688) = v284.lpMinimumApplicationAddress;
    *(_QWORD *)(v174 + 3692) = *(LPVOID *)((char *)&v284.lpMinimumApplicationAddress + 4);
  }
  if ( v305 )
    CDDISync::CSingleThreadedLowFreqLock::Leave(v305);
  v176 = *((_BYTE *)this + 1112);
  if ( v176 >= 2u )
  {
    *((_DWORD *)this + 282) |= 1u;
    if ( *((_BYTE *)this + 1136) )
    {
      v179 = *((_QWORD *)this + 135) + 40768LL;
      v285 = 0;
      v180 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v285);
      (*v181)(v179, &GUID_de18ef3a_2089_4936_a3f3_ec787ac6a40d, v180);
      switch ( (*(unsigned int (__fastcall **)(unsigned __int64))(*(_QWORD *)v285 + 32LL))(v285) )
      {
        case 3u:
          *((_DWORD *)this + 279) = 4;
          *((_DWORD *)this + 281) = 4;
          break;
        case 4u:
          *((_DWORD *)this + 279) = 4;
          *((_DWORD *)this + 281) = 5;
          break;
        case 5u:
          *((_DWORD *)this + 279) = 4;
          *((_DWORD *)this + 281) = 6;
          break;
        case 6u:
          *((_DWORD *)this + 279) = 7;
          *((_DWORD *)this + 281) = 7;
          break;
        case 7u:
          *((_DWORD *)this + 279) = 8;
          *((_DWORD *)this + 281) = 8;
          break;
        case 8u:
          *((_DWORD *)this + 279) = 8;
          *((_DWORD *)this + 281) = 9;
          break;
        case 9u:
          *((_DWORD *)this + 279) = 8;
          *((_DWORD *)this + 281) = 10;
          break;
        case 0xAu:
          Src = 0;
          v182 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&Src);
          (*v183)(v179, &GUID_189819f1_1db6_4b57_be54_1821339b85f7, v182);
          *(_QWORD *)&v334 = 0;
          DWORD2(v334) = 0;
          if ( (*(int (__fastcall **)(void *, __int64, __int128 *, __int64))(*(_QWORD *)Src + 104LL))(
                 Src,
                 23,
                 &v334,
                 12) < 0
            || SDWORD1(v334) < 2 )
          {
            v184 = 8;
          }
          else
          {
            v184 = 9;
          }
          *((_DWORD *)this + 279) = v184;
          if ( Src )
            (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
          *((_DWORD *)this + 281) = 11;
          break;
        case 0xBu:
          *((_DWORD *)this + 279) = 9;
          *((_DWORD *)this + 281) = 12;
          break;
        case 0xCu:
          *((_DWORD *)this + 279) = 9;
          *((_DWORD *)this + 281) = 13;
          break;
        case 0xDu:
          *((_DWORD *)this + 279) = 9;
          *((_DWORD *)this + 281) = 14;
          break;
        case 0xEu:
          *((_DWORD *)this + 281) = 15;
          goto LABEL_428;
        default:
          *((_DWORD *)this + 281) = 16;
LABEL_428:
          *((_DWORD *)this + 279) = 10;
          break;
      }
      v281 = 0;
      v185 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v281);
      if ( (*v186)(v179, &GUID_189819f1_1db6_4b57_be54_1821339b85f7, v185) >= 0 )
      {
        LODWORD(Src) = 98;
        (*(void (__fastcall **)(_DWORD *, __int64, void **, __int64))(*(_QWORD *)v281 + 104LL))(v281, 7, &Src, 4);
        *((_BYTE *)this + 1171) = (int)Src >= 96;
      }
      if ( v281 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v281 + 16LL))(v281);
      if ( v285 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v285 + 16LL))(v285);
    }
    else if ( *((int *)this + 279) >= 1 )
    {
      *((_DWORD *)this + 281) = 1;
      if ( v176 < 0x16u )
      {
        if ( v176 < 0x15u )
        {
          if ( v176 < 0x14u )
          {
            if ( v176 < 0x13u )
            {
              if ( v176 < 0x12u )
              {
                if ( v176 < 0x10u )
                {
                  if ( v176 < 0xFu )
                  {
                    if ( v176 < 0xEu )
                    {
                      v187 = *((_BYTE *)this + 1112);
                      if ( v187 < 0xCu )
                      {
                        if ( v187 < 0xBu )
                        {
                          if ( v187 < 9u )
                          {
                            if ( v187 < 8u )
                            {
                              if ( v187 < 7u )
                              {
                                if ( v187 < 6u )
                                {
                                  if ( v187 >= 5u )
                                    *((_DWORD *)this + 281) = 2;
                                }
                                else
                                {
                                  *((_DWORD *)this + 281) = 3;
                                }
                              }
                              else
                              {
                                *((_DWORD *)this + 281) = 4;
                              }
                            }
                            else
                            {
                              *((_DWORD *)this + 281) = 5;
                            }
                          }
                          else
                          {
                            *((_DWORD *)this + 281) = 6;
                          }
                        }
                        else
                        {
                          *((_DWORD *)this + 281) = 7;
                        }
                      }
                      else
                      {
                        *((_DWORD *)this + 281) = 8;
                      }
                    }
                    else
                    {
                      *((_DWORD *)this + 281) = 9;
                    }
                  }
                  else
                  {
                    *((_DWORD *)this + 281) = 10;
                  }
                }
                else
                {
                  *((_DWORD *)this + 281) = 11;
                }
              }
              else
              {
                *((_DWORD *)this + 281) = 12;
              }
            }
            else
            {
              *((_DWORD *)this + 281) = 13;
            }
          }
          else
          {
            *((_DWORD *)this + 281) = 14;
          }
        }
        else
        {
          *((_DWORD *)this + 281) = 15;
        }
      }
      else
      {
        *((_DWORD *)this + 281) = 16;
      }
    }
    v177 = v280;
  }
  else
  {
    *((_BYTE *)this + 1257) |= 8u;
    LODWORD(Src) = 0;
    v177 = v280;
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v280, 133, 0, &Src, 4) >= 0 )
    {
      if ( (unsigned int)Src >= 0x5000 )
      {
        *((_DWORD *)this + 281) = 4;
        *((_DWORD *)this + 282) |= 1u;
        *((_BYTE *)this + 1257) &= ~8u;
        *((_DWORD *)this + 279) = 4;
        goto LABEL_468;
      }
      if ( (unsigned int)Src >= 0x4000 )
      {
        *((_DWORD *)this + 281) = 3;
        *((_DWORD *)this + 282) |= 1u;
        *((_BYTE *)this + 1257) &= ~8u;
        *((_DWORD *)this + 279) = 3;
        goto LABEL_468;
      }
      if ( (unsigned int)Src >= 0x3001 )
      {
        *((_DWORD *)this + 281) = 2;
        *((_DWORD *)this + 279) = 2;
        goto LABEL_468;
      }
    }
    *((_DWORD *)this + 279) = 2;
    v284.lpMaximumApplicationAddress = (LPVOID)4;
    v284.dwOemId = *((_DWORD *)v177 + 24);
    v284.dwPageSize = 13;
    LODWORD(v281) = 0;
    v284.lpMinimumApplicationAddress = &v281;
    v178 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
             *((_QWORD *)v177 + 38),
             "QueryAdapterInfo (DRIVERVERSION)",
             &v284);
    if ( (int)NDXGI::CUMDAdapter::NTStatusToHResult(v178) >= 0 && (int)v281 > 1000 )
      *((_DWORD *)this + 281) = 1;
  }
LABEL_468:
  CDevice::FeatureLevelCreated(this, *((enum D3D_FEATURE_LEVEL *)this + 321));
  v188 = *((_BYTE *)this + 1112);
  if ( v188 < 2u && !*((_BYTE *)this + 1133) )
  {
    *((_DWORD *)this + 282) &= ~1u;
    if ( *((int *)this + 279) <= 3 )
      *((_DWORD *)this + 279) = 2;
  }
  *((_DWORD *)this + 280) = *((_DWORD *)this + 279);
  if ( (*((_BYTE *)this + 1257) & 4) != 0 )
    *((_DWORD *)this + 279) = 0;
  if ( v188 > 6u )
    goto LABEL_480;
  if ( v188 != 6 )
    goto LABEL_479;
  if ( !HIWORD(*(_DWORD *)(v307[12] + 912LL)) )
    goto LABEL_484;
  v189 = *((_QWORD *)this + 135);
  if ( !*(_QWORD *)(v189 + 2776) )
    goto LABEL_484;
  if ( *(_QWORD *)(v189 + 2784) )
  {
LABEL_480:
    if ( (int)NDXGI::CUMDAdapter::GetCaps(v177, 137, 0, (char *)this + 1332, 4) >= 0 )
    {
      if ( (*((_BYTE *)this + 1332) & 2) != 0 )
        *(_DWORD *)(*((_QWORD *)this + 154) + 912LL) |= 0x40u;
    }
    else
    {
      *((_DWORD *)this + 333) = 0;
    }
    goto LABEL_484;
  }
LABEL_479:
  if ( *((_BYTE *)this + 1112) == 1 )
    goto LABEL_480;
LABEL_484:
  v286 = 0;
  v284.lpMaximumApplicationAddress = (LPVOID)4;
  v284.dwOemId = *((_DWORD *)v177 + 24);
  v284.dwPageSize = 77;
  v284.lpMinimumApplicationAddress = &v286;
  CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
    *((_QWORD *)v177 + 38),
    "QueryAdapterInfo (KMTQAITYPE_WDDM_3_0_CAPS)",
    &v284);
  v288 = 0;
  v284.lpMaximumApplicationAddress = (LPVOID)4;
  v284.dwOemId = *((_DWORD *)v177 + 24);
  v284.dwPageSize = 13;
  v284.lpMinimumApplicationAddress = &v288;
  v190 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
           *((_QWORD *)v177 + 38),
           "QueryAdapterInfo (KMTQAITYPE_DRIVERVERSION)",
           &v284);
  v191 = NDXGI::CUMDAdapter::NTStatusToHResult(v190);
  ThrowFailure(v191);
  if ( v288 >= 2700
    && (v286 & 8) != 0
    && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 940LL) != 4098 || v288 >= 3100) )
  {
    *((_BYTE *)this + 1265) = 1;
  }
  CContext::UpdateMarkerModeIfChanged(*((CContext **)this + 135));
  LODWORD(Src) = 0;
  v284.dwOemId = *((_DWORD *)v177 + 24);
  v284.dwPageSize = 30;
  v284.lpMinimumApplicationAddress = &Src;
  v284.lpMaximumApplicationAddress = (LPVOID)4;
  v192 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
           *((_QWORD *)v177 + 38),
           "QueryAdapterInfo (KMTQAITYPE_PHYSICALADAPTERCOUNT)",
           &v284);
  v193 = NDXGI::CUMDAdapter::NTStatusToHResult(v192);
  ThrowFailure(v193);
  *((_DWORD *)this + 339) = (_DWORD)Src;
  *((_BYTE *)this + 1712) = 0;
  LODWORD(Src) = 0;
  v284.dwOemId = *((_DWORD *)v177 + 24);
  v284.dwPageSize = 57;
  v284.lpMinimumApplicationAddress = &Src;
  v284.lpMaximumApplicationAddress = (LPVOID)4;
  if ( (int)CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
              *((_QWORD *)v177 + 38),
              "QueryAdapterInfo (KMTQAITYPE_PHYSICALADAPTERCOUNT)",
              &v284) >= 0 )
    *((_BYTE *)this + 1712) = ((unsigned __int8)Src & 0x80) != 0;
  *((_QWORD *)this + 213) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 932LL);
  v342 = 0;
  if ( NDXGI::CResource::SupportsDeviceBitmapGdiInterop((CDevice *)((char *)this + 3768)) )
  {
    v341[0] = off_1801DEE30;
    v341[1] = this;
    v341[2] = v177;
    v342 = v341;
  }
  v197 = CShaderCacheAdapter::Init(
           v195,
           v194,
           *(_QWORD *)(*(_QWORD *)(v196 + 96) + 80LL),
           *((unsigned int *)this + 339),
           v341);
  ThrowFailure(v197);
  if ( v342 )
  {
    v198 = v341;
    LOBYTE(v198) = v342 != v341;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v342 + 32LL))(v342, v198);
  }
  CDevice::CreateDefaults(this);
  CContext::InitializeDefaults(*((CContext **)this + 135));
  if ( NDXGI::CUMDAdapter::IsWARP(v177) && !*((_BYTE *)this + 1136) )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)v177 + 10), (LPCSTR)0xC7);
    *((_QWORD *)this + 458) = ProcAddress;
    if ( ProcAddress )
      *((_BYTE *)this + 1688) = 1;
    *((_DWORD *)this + 282) |= 1u;
  }
  v200 = *((_BYTE *)this + 1112);
  if ( v200 < 6u && *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 940LL) == 1297040209 )
    *((_DWORD *)this + 282) |= 2u;
  if ( v200 >= 7u )
  {
    v277 = 0;
    LODWORD(v282) = *((_DWORD *)v177 + 24);
    DWORD1(v282) = 24;
    *((_QWORD *)&v282 + 1) = &v277;
    v283 = 4;
    v201 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
             *((_QWORD *)v177 + 38),
             "QueryAdapterInfo (KMTQAITYPE_WDDM_2_0_CAPS)",
             &v282);
    v202 = NDXGI::CUMDAdapter::NTStatusToHResult(v201);
    ThrowFailure(v202);
    v203 = v277;
    if ( (v277 & 4) != 0 )
    {
      memset(&v284, 0, sizeof(v284));
      GetSystemInfo(&v284);
      _BitScanReverse64(&v204, (char *)v284.lpMaximumApplicationAddress - (char *)v284.lpMinimumApplicationAddress);
      *((_DWORD *)this + 288) = v204;
      LODWORD(v205) = ++*((_DWORD *)this + 288);
      v203 = v277;
    }
    else
    {
      LODWORD(v205) = 64;
      *((_DWORD *)this + 288) = 64;
    }
    if ( (v203 & 2) != 0 )
    {
      for ( jj = 0; jj < *((_DWORD *)this + 339); ++jj )
      {
        LODWORD(v334) = jj;
        *(_QWORD *)((char *)&v334 + 4) = 0;
        v284.dwOemId = *((_DWORD *)v177 + 24);
        v284.dwPageSize = 34;
        v284.lpMinimumApplicationAddress = &v334;
        v284.lpMaximumApplicationAddress = (LPVOID)12;
        v282 = *(_OWORD *)&v284.dwOemId;
        v283 = 12;
        v207 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
                 *((_QWORD *)v177 + 38),
                 "QueryAdapterInfo (KMTQAITYPE_QUERY_GPUMMU_CAPS)",
                 &v282);
        if ( (int)NDXGI::CUMDAdapter::NTStatusToHResult(v207) < 0 )
        {
          *(struct D3D11_FEATURE_DATA_GPU_VIRTUAL_ADDRESS_SUPPORT *)((char *)this + 1148) = c_DefaultGPUVACaps;
          v205 = HIDWORD(*(unsigned __int64 *)&c_DefaultGPUVACaps);
          break;
        }
        LODWORD(v205) = *((_DWORD *)this + 288);
        if ( DWORD2(v334) < (unsigned int)v205 )
          LODWORD(v205) = DWORD2(v334);
        *((_DWORD *)this + 288) = v205;
      }
    }
    *((_DWORD *)this + 287) = v205;
    if ( *((_BYTE *)this + 1112) > 7u
      || *((_BYTE *)this + 1112) == 7 && HIWORD(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 96LL) + 912LL)) >= 9u )
    {
      LODWORD(Src) = 0;
      v208 = NDXGI::CUMDAdapter::GetCaps(v177, 153, 0, &Src, 4);
      if ( v208 >= 0 )
      {
        if ( !(_DWORD)Src )
        {
          CModule::RecordJournal(
            (CModule *)&g_Module,
            0x887A0020,
            "Driver set MaxGPUVirtualAddressBitsPerResource to 0.\n",
            v209,
            1);
          LibraryA = LoadLibraryA("D3DDriverVerifier.dll");
          v273 = LibraryA;
          if ( LibraryA )
          {
            v274 = GetProcAddress(LibraryA, "RetrieveVerifierInterface");
            if ( v274 )
            {
              v280 = 0;
              ((void (__fastcall *)(GUID *, NDXGI::CUMDAdapter **))v274)(&IID_ID3DDriverVerifier1, &v280);
              if ( v280 )
              {
                (*(void (__fastcall **)(NDXGI::CUMDAdapter *, char *, __int64, _QWORD, const char *))(*(_QWORD *)v280 + 64LL))(
                  v280,
                  (char *)this + 16,
                  1,
                  0,
                  "Driver set MaxGPUVirtualAddressBitsPerResource to 0.\n");
                (*(void (__fastcall **)(NDXGI::CUMDAdapter *))(*(_QWORD *)v280 + 16LL))(v280);
              }
            }
            FreeLibrary(v273);
          }
          CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "MaxGPUVirtualAddressBitsPerResource error", v272, 1);
          _com_error::_com_error((_com_error *)v333, -2005270496, v275, v276);
          throw (_com_error *)v333;
        }
        v210 = *((_DWORD *)this + 287);
        if ( (unsigned int)Src < v210 )
          v210 = (unsigned int)Src;
        *((_DWORD *)this + 287) = v210;
      }
      else
      {
        CModule::RecordJournal((CModule *)&g_Module, v208, "GetCaps (D3DWDDM2_0DDICAPS_GPUVA_CAPS)", v209, 1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008c850  mov     [rsp+arg_8], rbx
0x18008c855  mov     [rsp+arg_10], rsi
0x18008c85a  push    rdi
0x18008c85b  push    r12
0x18008c85d  push    r13
0x18008c85f  push    r14
0x18008c861  push    r15
0x18008c863  sub     rsp, 5D0h
0x18008c86a  movaps  [rsp+5F8h+var_38], xmm6
0x18008c872  mov     rax, cs:__security_cookie
0x18008c879  xor     rax, rsp
0x18008c87c  mov     [rsp+5F8h+var_48], rax
0x18008c884  mov     rdi, rcx
0x18008c887  mov     rcx, [rcx+0F8h]
0x18008c88e  lea     rsi, [rdi+4D0h]
0x18008c895  mov     rax, [rcx]
0x18008c898  mov     r8, rsi
0x18008c89b  lea     rdx, _GUID_00000040_1bbe_4d12_afbf_8fdf7e0a87c7
0x18008c8a2  mov     rax, [rax]
0x18008c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8aa  mov     rcx, [rsi]
0x18008c8ad  mov     rax, [rcx]
0x18008c8b0  mov     rax, [rax+10h]
0x18008c8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8b9  mov     rcx, [rdi+0F8h]
0x18008c8c0  mov     rax, [rcx]
0x18008c8c3  lea     r8, [rdi+4D8h]
0x18008c8ca  lea     rdx, _GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140
0x18008c8d1  mov     rax, [rax]
0x18008c8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8d9  mov     rcx, [rdi+4D8h]
0x18008c8e0  mov     rax, [rcx]
0x18008c8e3  mov     rax, [rax+10h]
0x18008c8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8ec  mov     rcx, [rdi+0F8h]
0x18008c8f3  mov     rax, [rcx]
0x18008c8f6  lea     r8, [rdi+4E0h]
0x18008c8fd  lea     rdx, _GUID_61386220_f959_44f3_bb21_1aaa84193d9c
0x18008c904  mov     rax, [rax]
0x18008c907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c90c  mov     rcx, [rdi+4E0h]
0x18008c913  mov     rax, [rcx]
0x18008c916  mov     rax, [rax+10h]
0x18008c91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c91f  mov     r15, [rsi]
0x18008c922  mov     [rsp+5F8h+var_478], r15
0x18008c92a  mov     r14, [r15+60h]
0x18008c92e  mov     [rsp+5F8h+var_5A0], r14
0x18008c933  mov     rcx, r14; this
0x18008c936  call    ?IsWARP@CUMDAdapter@NDXGI@@QEBA_NXZ; NDXGI::CUMDAdapter::IsWARP(void)
0x18008c93b  xor     al, 1
0x18008c93d  mov     [rdi+46Ch], al
0x18008c943  cmp     dword ptr [r14+48h], 3
0x18008c948  setz    al
0x18008c94b  mov     [rdi+470h], al
0x18008c951  lea     rcx, [r15+10h]
0x18008c955  mov     rax, [rcx]
0x18008c958  mov     rax, [rax+148h]
0x18008c95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c964  test    eax, eax
0x18008c966  setnz   al
0x18008c969  mov     [rdi+471h], al
0x18008c96f  cmp     byte ptr [rdi+458h], 4
0x18008c976  jb      loc_18008CAE5
0x18008c97c  mov     dword ptr [rsp+5F8h+var_5D8], 4
0x18008c984  lea     r9, [rdi+50Ch]
0x18008c98b  xor     r8d, r8d
0x18008c98e  mov     edx, 80h
0x18008c993  mov     rcx, r14
0x18008c996  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008c99b  test    eax, eax
0x18008c99d  js      short loc_18008C9CA
0x18008c99f  mov     eax, [rdi+50Ch]
0x18008c9a5  test    al, 1
0x18008c9a7  jz      short loc_18008C9C5
0x18008c9a9  mov     byte ptr [rdi+548h], 0
0x18008c9b0  cmp     dword ptr [rdi+500h], 0A000h
0x18008c9ba  jl      short loc_18008C9C5
0x18008c9bc  test    byte ptr [rdi+4E9h], 1
0x18008c9c3  jz      short loc_18008C9D6
0x18008c9c5  and     eax, 0FFFFFFF9h
0x18008c9c8  jmp     short loc_18008C9D0
0x18008c9ca  mov     eax, cs:?c_DefaultShaderCaps@@3UD3D11DDI_SHADER_CAPS@@B; D3D11DDI_SHADER_CAPS const c_DefaultShaderCaps
0x18008c9d0  mov     [rdi+50Ch], eax
0x18008c9d6  lea     rbx, [rdi+4F4h]
0x18008c9dd  mov     dword ptr [rsp+5F8h+var_5D8], 4
0x18008c9e5  mov     r9, rbx
0x18008c9e8  xor     r8d, r8d
0x18008c9eb  mov     edx, 81h
0x18008c9f0  mov     rcx, r14
0x18008c9f3  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008c9f8  test    eax, eax
0x18008c9fa  jns     short loc_18008CA04
0x18008c9fc  mov     eax, cs:?c_DefaultShaderCaps@@3UD3D11DDI_SHADER_CAPS@@B; D3D11DDI_SHADER_CAPS const c_DefaultShaderCaps
0x18008ca02  jmp     short loc_18008CA23
0x18008ca04  call    IsXboxIsAsyncComputeOnlyDevicePresent
0x18008ca09  test    al, al
0x18008ca0b  jz      short loc_18008CA25
0x18008ca0d  mov     ecx, [rdi+4ECh]
0x18008ca13  call    cs:__imp_XboxIsAsyncComputeOnlyDevice
0x18008ca19  test    eax, eax
0x18008ca1b  jz      short loc_18008CA25
0x18008ca1d  call    cs:__imp_XboxGetAsyncComputeShaderCaps
0x18008ca23  mov     [rbx], eax
0x18008ca25  mov     r8d, [rdi+500h]
0x18008ca2c  cmp     r8d, 0C000h
0x18008ca33  jl      short loc_18008CA52
0x18008ca35  test    byte ptr [rbx], 20h
0x18008ca38  jz      loc_18008F4A8
0x18008ca3e  cmp     r8d, 0C100h
0x18008ca45  jl      short loc_18008CA52
0x18008ca47  test    byte ptr [rbx], 40h
0x18008ca4a  jz      loc_18008F4EB
0x18008ca50  jmp     short loc_18008CA5B
0x18008ca52  cmp     r8d, 0B000h
0x18008ca59  jl      short loc_18008CA6F
0x18008ca5b  mov     edx, [rbx]
0x18008ca5d  test    dl, 2
0x18008ca60  jz      loc_18008F52E
0x18008ca66  cmp     r8d, 0B000h
0x18008ca6d  jge     short loc_18008CA74
0x18008ca6f  and     dword ptr [rbx], 0FFFFFFFEh
0x18008ca72  mov     edx, [rbx]
0x18008ca74  test    dl, 8
0x18008ca77  jz      short loc_18008CAA0
0x18008ca79  cmp     byte ptr [rdi+458h], 6
0x18008ca80  ja      short loc_18008CAB4
0x18008ca82  jnz     short loc_18008CA9B
0x18008ca84  mov     rax, [rsi]
0x18008ca87  mov     rcx, [rax+60h]
0x18008ca8b  mov     eax, [rcx+390h]
0x18008ca91  shr     rax, 10h
0x18008ca95  cmp     ax, 1
0x18008ca99  jnb     short loc_18008CAB4
0x18008ca9b  and     edx, 0FFFFFFF7h
0x18008ca9e  mov     [rbx], edx
0x18008caa0  test    byte ptr [rdi+4ECh], 40h
0x18008caa7  jz      short loc_18008CAE5
0x18008caa9  test    dl, 4
0x18008caac  jz      loc_18008F571
0x18008cab2  jmp     short loc_18008CAC3
0x18008cab4  cmp     r8d, 0A000h
0x18008cabb  jge     loc_18008F5B4
0x18008cac1  jmp     short loc_18008CAA0
0x18008cac3  cmp     r8d, 0A000h
0x18008caca  jge     short loc_18008CAE5
0x18008cacc  mov     rcx, [rsi]
0x18008cacf  mov     edx, 5; enum D3D_DRIVER_TYPE
0x18008cad4  mov     rcx, [rcx+60h]; this
0x18008cad8  call    ?IsExplicitDriverType@CUMDAdapter@NDXGI@@QEBA_NW4D3D_DRIVER_TYPE@@@Z; NDXGI::CUMDAdapter::IsExplicitDriverType(D3D_DRIVER_TYPE)
0x18008cadd  test    al, al
0x18008cadf  jz      loc_18008F5F7
0x18008cae5  xor     r12d, r12d
0x18008cae8  mov     [rsp+5F8h+Src], r12
0x18008caed  lea     r9, Context; Context
0x18008caf4  xor     r8d, r8d; Parameter
0x18008caf7  lea     rdx, ?InitOnceGetProcAddress@CModule@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18008cafe  lea     rcx, InitOnce; InitOnce
0x18008cb05  call    cs:__imp_InitOnceExecuteOnce
0x18008cb0b  test    eax, eax
0x18008cb0d  jz      loc_18008CBAC
0x18008cb13  mov     rax, cs:Context
0x18008cb1a  mov     rax, [rax]
0x18008cb1d  test    rax, rax
0x18008cb20  jz      loc_18008CBAC
0x18008cb26  lea     rdx, [rsp+5F8h+Src]
0x18008cb2b  lea     rcx, aFeaturelevelli; "FeatureLevelLimit"
0x18008cb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb37  test    eax, eax
0x18008cb39  jz      short loc_18008CBAC
0x18008cb3b  cmp     [rsp+5F8h+Src], r12
0x18008cb40  jz      short loc_18008CBAC
0x18008cb42  mov     rcx, [rsi]
0x18008cb45  mov     edx, 5; enum D3D_DRIVER_TYPE
0x18008cb4a  mov     rcx, [rcx+60h]; this
0x18008cb4e  call    ?IsExplicitDriverType@CUMDAdapter@NDXGI@@QEBA_NW4D3D_DRIVER_TYPE@@@Z; NDXGI::CUMDAdapter::IsExplicitDriverType(D3D_DRIVER_TYPE)
0x18008cb53  test    al, al
0x18008cb55  jnz     short loc_18008CBAC
0x18008cb57  lea     rdx, aD3d113sdklayer; "D3D11_3SDKLayers.dll"
0x18008cb5e  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18008cb65  call    ?SDKLoadLibraryW@CModule@@QEAAPEAUHINSTANCE__@@PEBG@Z; CModule::SDKLoadLibraryW(ushort const *)
0x18008cb6a  mov     rbx, rax
0x18008cb6d  mov     [rsp+5F8h+var_488], rax
0x18008cb75  test    rax, rax
0x18008cb78  jz      short loc_18008CB9E
0x18008cb7a  mov     [rsp+5F8h+var_5D8], 1; bool
0x18008cb7f  lea     r8, aFeatureLevelLi; "Feature level limit imposed"
0x18008cb86  xor     edx, edx; unsigned int
0x18008cb88  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18008cb8f  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x18008cb94  mov     ecx, dword ptr [rsp+5F8h+Src]
0x18008cb98  mov     [rdi+508h], ecx
0x18008cb9e  test    rbx, rbx
0x18008cba1  jz      short loc_18008CBAC
0x18008cba3  mov     rcx, rbx; hLibModule
0x18008cba6  call    cs:__imp_FreeLibrary
0x18008cbac  mov     r13d, 8
0x18008cbb2  cmp     byte ptr [rdi+458h], 5
0x18008cbb9  jb      loc_18008CC51
0x18008cbbf  mov     rax, [r15+58h]
0x18008cbc3  shr     rax, 20h
0x18008cbc7  cmp     eax, 0B000Fh
0x18008cbcc  jb      loc_18008CC5F
0x18008cbd2  mov     dword ptr [rsp+5F8h+var_5D8], r13d
0x18008cbd7  lea     r9, [rdi+510h]
0x18008cbde  xor     r8d, r8d
0x18008cbe1  mov     edx, 83h
0x18008cbe6  mov     rcx, r14
0x18008cbe9  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008cbee  test    eax, eax
0x18008cbf0  jns     short loc_18008CC02
0x18008cbf2  mov     rax, cs:?c_DefaultD3D11Options@@3UD3D11_1DDI_D3D11_OPTIONS_DATA@@B; D3D11_1DDI_D3D11_OPTIONS_DATA const c_DefaultD3D11Options
0x18008cbf9  mov     [rdi+510h], rax
0x18008cc00  jmp     short loc_18008CC25
0x18008cc02  call    IsXboxIsAsyncComputeOnlyDevicePresent
0x18008cc07  test    al, al
0x18008cc09  jz      short loc_18008CC25
0x18008cc0b  mov     ecx, [rdi+4ECh]
0x18008cc11  call    cs:__imp_XboxIsAsyncComputeOnlyDevice
0x18008cc17  test    eax, eax
0x18008cc19  jz      short loc_18008CC25
0x18008cc1b  mov     dword ptr [rdi+510h], 1
0x18008cc25  mov     eax, [rdi+500h]
0x18008cc2b  cmp     eax, 0B100h
0x18008cc30  jnz     short loc_18008CC41
0x18008cc32  cmp     dword ptr [rdi+510h], 0
0x18008cc39  jz      loc_18008F63A
0x18008cc3f  jmp     short loc_18008CC5F
0x18008cc41  cmp     eax, 0A000h
0x18008cc46  jge     short loc_18008CC5F
0x18008cc48  mov     [rdi+510h], r12d
0x18008cc4f  jmp     short loc_18008CC5F
0x18008cc51  mov     rax, cs:?c_DefaultD3D11Options@@3UD3D11_1DDI_D3D11_OPTIONS_DATA@@B; D3D11_1DDI_D3D11_OPTIONS_DATA const c_DefaultD3D11Options
0x18008cc58  mov     [rdi+510h], rax
0x18008cc5f  movzx   eax, byte ptr [rdi+458h]
0x18008cc66  sub     al, 2
0x18008cc68  cmp     al, 2
0x18008cc6a  jbe     short loc_18008CCCD
0x18008cc6c  mov     dword ptr [rsp+5F8h+var_5D8], 4
0x18008cc74  lea     r9, [rdi+518h]
0x18008cc7b  xor     r8d, r8d
0x18008cc7e  mov     edx, 84h
0x18008cc83  mov     rcx, r14
0x18008cc86  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008cc8b  test    eax, eax
0x18008cc8d  jns     short loc_18008CC9B
0x18008cc8f  mov     eax, cs:?c_DefaultShaderCaps@@3UD3D11DDI_SHADER_CAPS@@B; D3D11DDI_SHADER_CAPS const c_DefaultShaderCaps
0x18008cc95  mov     [rdi+518h], eax
0x18008cc9b  mov     dword ptr [rsp+5F8h+var_5D8], r13d
0x18008cca0  lea     r9, [rdi+51Ch]
0x18008cca7  xor     r8d, r8d
0x18008ccaa  mov     edx, 86h
0x18008ccaf  mov     rcx, r14
0x18008ccb2  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008ccb7  test    eax, eax
0x18008ccb9  jns     loc_18008CD6B
0x18008ccbf  mov     rax, cs:?c_DefaultD3D11Options@@3UD3D11_1DDI_D3D11_OPTIONS_DATA@@B; D3D11_1DDI_D3D11_OPTIONS_DATA const c_DefaultD3D11Options
0x18008ccc6  mov     [rdi+51Ch], rax
0x18008cccd  cmp     byte ptr [rdi+458h], 6
0x18008ccd4  jb      loc_18008CDCA
0x18008ccda  mov     rax, [r15+58h]
0x18008ccde  shr     rax, 20h
0x18008cce2  cmp     eax, 0B0010h
0x18008cce7  jb      loc_18008CDCA
0x18008cced  cmp     dword ptr [rdi+500h], 0B000h
0x18008ccf7  jl      loc_18008CDCA
0x18008ccfd  mov     dword ptr [rsp+5F8h+var_5D8], 4
0x18008cd05  lea     r9, [rdi+524h]
0x18008cd0c  xor     r8d, r8d
0x18008cd0f  mov     edx, 88h
0x18008cd14  mov     rcx, r14
0x18008cd17  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18008cd1c  test    eax, eax
0x18008cd1e  jns     short loc_18008CD2C
0x18008cd20  mov     eax, cs:?c_DefaultShaderCaps@@3UD3D11DDI_SHADER_CAPS@@B; D3D11DDI_SHADER_CAPS const c_DefaultShaderCaps
0x18008cd26  mov     [rdi+524h], eax
0x18008cd2c  mov     eax, [rdi+524h]
0x18008cd32  test    al, 2
0x18008cd34  jz      short loc_18008CD3F
0x18008cd36  or      eax, 1
0x18008cd39  mov     [rdi+524h], eax
0x18008cd3f  test    al, 4
0x18008cd41  jz      short loc_18008CD4C
0x18008cd43  or      eax, 3
0x18008cd46  mov     [rdi+524h], eax
0x18008cd4c  cmp     dword ptr [rdi+500h], 0C000h
0x18008cd56  jl      short loc_18008CDD6
0x18008cd58  test    al, 2
0x18008cd5a  jnz     short loc_18008CDD6
0x18008cd5c  cmp     byte ptr [rdi+470h], 0
0x18008cd63  jz      loc_18008F67D
0x18008cd69  jmp     short loc_18008CDD6
0x18008cd6b  mov     ecx, [rdi+51Ch]
0x18008cd71  test    ecx, 0FFFFFFFCh
0x18008cd77  jnz     loc_18008F746
0x18008cd7d  mov     eax, [rdi+520h]
0x18008cd83  test    eax, 0FFFFFFFCh
0x18008cd88  jnz     loc_18008F746
0x18008cd8e  cmp     dword ptr [rdi+500h], 9300h
0x18008cd98  jle     short loc_18008CDA7
  ... truncated ...
```
