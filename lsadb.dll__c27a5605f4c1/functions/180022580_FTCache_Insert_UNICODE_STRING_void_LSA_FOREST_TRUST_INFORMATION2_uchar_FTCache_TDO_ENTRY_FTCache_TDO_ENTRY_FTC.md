# FTCache::Insert(_UNICODE_STRING *,void *,_LSA_FOREST_TRUST_INFORMATION2 *,uchar,FTCache::TDO_ENTRY *,FTCache::TDO_ENTRY * *,FTCache::CONFLICT_PAIR * *,ulong *)

- ea: `0x180022580`
- end: `0x180024ccb`
- name: `?Insert@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@EPEAUTDO_ENTRY@1@PEAPEAU41@PEAPEAUCONFLICT_PAIR@1@PEAK@Z`
- size: `10059`
- prototype: `int(FTCache *__hidden this, struct _UNICODE_STRING *, void *, struct _LSA_FOREST_TRUST_INFORMATION2 *, unsigned __int8, struct FTCache::TDO_ENTRY *, struct FTCache::TDO_ENTRY **, struct FTCache::CONFLICT_PAIR **, unsigned int *)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025ba8`
- `0x180028510`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x180020b10`
- `0x180021840`
- `0x180021a68`
- `0x180021aa8`
- `0x180021ad4`
- `0x180022278`
- `0x180022580`
- `0x180024fb8`
- `0x180029d44`
- `0x18002ae5c`
- `0x18002b394`
- `0x18002bac4`
- `0x18002be58`
- `0x18002c094`
- `0x18002c0f8`
- `0x1800372f4`
- `0x18003acd0`
- `0x18003ad30`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022904`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022904`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022ce9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022d80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022efe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022f23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002351c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002359f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002392e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022ce9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022d80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022efe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022f23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002351c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002359f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002392e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024275`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024275`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022673`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800229bf`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800229dc`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022fdb`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022ff2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180023015`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800237fe`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180023bda`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002433a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800243dc`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024892`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024aad`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022673`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800229bf`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800229dc`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022fdb`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180022ff2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180023015`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800237fe`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180023bda`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002433a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800243dc`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024892`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024aad`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18002279e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180022acc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180022c7b`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180023102`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800232cd`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800234ab`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800238dc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180023cbe`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18002279e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180022acc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180022c7b`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180023102`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800232cd`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800234ab`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800238dc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180023cbe`
- `ntdll!RtlCopySid` at `0x1800228f2`
- `ntdll!RtlCopySid` at `0x180022ed0`
- `ntdll!RtlCopySid` at `0x1800230e8`
- `ntdll!RtlCopySid` at `0x1800237a0`
- `ntdll!RtlCopySid` at `0x1800228f2`
- `ntdll!RtlCopySid` at `0x180022ed0`
- `ntdll!RtlCopySid` at `0x1800230e8`
- `ntdll!RtlCopySid` at `0x1800237a0`
- `ntdll!RtlLengthSid` at `0x1800228a2`
- `ntdll!RtlLengthSid` at `0x1800229a3`
- `ntdll!RtlLengthSid` at `0x180022fc0`
- `ntdll!RtlLengthSid` at `0x1800228a2`
- `ntdll!RtlLengthSid` at `0x1800229a3`
- `ntdll!RtlLengthSid` at `0x180022fc0`
- `ntdll!RtlValidSid` at `0x180022992`
- `ntdll!RtlValidSid` at `0x180022faa`
- `ntdll!RtlValidSid` at `0x180022992`
- `ntdll!RtlValidSid` at `0x180022faa`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180022ddc`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180022dff`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023603`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023632`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023651`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002429d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180022ddc`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180022dff`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023603`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023632`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023651`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002429d`

## pseudocode

```c
__int64 __fastcall FTCache::Insert(
        FTCache *this,
        struct _UNICODE_STRING *a2,
        void *a3,
        struct _LSA_FOREST_TRUST_INFORMATION2 *a4,
        char a5,
        struct FTCache::TDO_ENTRY *a6,
        struct FTCache::TDO_ENTRY **a7,
        struct FTCache::CONFLICT_PAIR **a8,
        unsigned int *a9)
{
  FTCache *v12; // r14
  struct FTCache::TDO_ENTRY *v13; // r13
  FTCache **v14; // rbx
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  _DWORD *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  __int64 **v25; // r14
  __int64 ***v26; // r15
  ULONG v27; // ebx
  HLOCAL v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  struct _LSA_FOREST_TRUST_INFORMATION2 *v31; // rax
  unsigned int v32; // edi
  __int64 v33; // rax
  __int64 v34; // r15
  __int64 v35; // r9
  void *v36; // rdi
  char v37; // r14
  FTCache *v38; // r12
  __int64 v39; // rdi
  __int64 v40; // rdx
  _QWORD *v41; // r8
  _QWORD *v42; // r13
  _QWORD *v43; // r15
  int v44; // r12d
  FTCache **v45; // rdi
  __int64 v46; // r12
  unsigned __int64 v47; // rcx
  __int64 v48; // rcx
  unsigned __int64 v49; // rcx
  void *v50; // rsp
  void *v51; // rsp
  _DWORD *v52; // rax
  const UNICODE_STRING *v53; // rdx
  CLONG v54; // r8d
  FTCache *v55; // r12
  struct FTCache::TDO_ENTRY *v56; // rdx
  char v57; // r12
  FTCache **v58; // rdi
  unsigned __int64 v59; // r15
  unsigned __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned __int64 v62; // rcx
  void *v63; // rsp
  void *v64; // rsp
  _DWORD *v65; // rax
  _QWORD *v66; // rcx
  __int64 v67; // rdx
  _QWORD *v68; // rax
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  const UNICODE_STRING *v71; // rdx
  _QWORD *v72; // rax
  _QWORD *v73; // rdi
  _QWORD *i; // rax
  PSID v75; // r14
  HLOCAL v76; // rax
  __int64 v77; // rdi
  FTCache *v78; // r14
  _QWORD *v79; // rcx
  __int64 v80; // rax
  _QWORD *v81; // rcx
  __int64 v82; // rdx
  _QWORD *v83; // rax
  _QWORD *v84; // rcx
  __int64 v85; // rdx
  _DWORD *v86; // r12
  struct _FILETIME v87; // rax
  _DWORD *v88; // rdi
  unsigned int v89; // eax
  HLOCAL v90; // rax
  _QWORD *v91; // rcx
  __int64 v92; // rax
  void *v93; // rcx
  void *v94; // r13
  char v95; // di
  void *v96; // r14
  ULONG v97; // r15d
  _QWORD *v98; // r12
  __int64 v99; // rdx
  _QWORD *v100; // r14
  _QWORD *v101; // r13
  FTCache **v102; // rdi
  __int64 v103; // r15
  unsigned __int64 v104; // rcx
  __int64 v105; // rcx
  unsigned __int64 v106; // rcx
  void *v107; // rsp
  void *v108; // rsp
  _DWORD *v109; // rax
  ULONG v110; // ecx
  _QWORD *v111; // rax
  struct FTCache::TDO_ENTRY *v112; // rdx
  char v113; // r15
  FTCache **v114; // rdi
  unsigned __int64 v115; // r15
  unsigned __int64 v116; // rcx
  __int64 v117; // rcx
  unsigned __int64 v118; // rcx
  void *v119; // rsp
  void *v120; // rsp
  _DWORD *v121; // rax
  _QWORD *v122; // rcx
  __int64 v123; // rdx
  __int64 v124; // rdx
  _QWORD *v125; // r14
  char v126; // r15
  UNICODE_STRING *v127; // r13
  FTCache **v128; // rdi
  unsigned __int64 v129; // r15
  unsigned __int64 v130; // rcx
  __int64 v131; // rcx
  unsigned __int64 v132; // rcx
  void *v133; // rsp
  void *v134; // rsp
  _DWORD *v135; // rax
  _QWORD *v136; // rax
  _QWORD *v137; // rdi
  _QWORD *v138; // rax
  HLOCAL v139; // rax
  FTCache *v140; // rdi
  _QWORD *v141; // rcx
  __int64 v142; // rax
  _QWORD *v143; // rcx
  __int64 v144; // rdx
  char *v145; // r14
  _QWORD *v146; // rcx
  __int64 v147; // rdx
  _QWORD *v148; // rax
  _QWORD *v149; // rcx
  __int64 v150; // rdx
  _DWORD *v151; // r15
  struct _FILETIME v152; // rax
  void *v153; // rdx
  ULONG v154; // ecx
  char *v155; // rax
  __int64 v156; // rdx
  _QWORD *v157; // r14
  FTCache **v158; // rdi
  unsigned __int64 v159; // r15
  unsigned __int64 v160; // rcx
  __int64 v161; // rcx
  unsigned __int64 v162; // rcx
  void *v163; // rsp
  void *v164; // rsp
  _DWORD *v165; // rax
  _QWORD *v166; // rcx
  _QWORD *v167; // rdx
  __int64 v168; // rax
  _QWORD *v169; // rdx
  __int64 v170; // r8
  struct _FILETIME v171; // rax
  _QWORD *v172; // rcx
  _QWORD *j; // rax
  _QWORD *v174; // r8
  UNICODE_STRING v175; // xmm0
  FTCache **v176; // r15
  __int64 v177; // rdx
  unsigned __int16 v178; // r13
  FTCache **v179; // r12
  size_t v180; // r14
  size_t v181; // rcx
  size_t v182; // rdi
  __int64 v183; // rax
  void *v184; // rsp
  _DWORD *v185; // rax
  __int64 v186; // rdx
  size_t v187; // rcx
  __int64 v188; // rax
  void *v189; // rsp
  _DWORD *v190; // rax
  FTCache *v191; // rdi
  ULONG v192; // r14d
  struct _RTL_AVL_TABLE *v193; // r11
  FTCache *v194; // rax
  __int64 v195; // rdx
  __int64 v196; // r13
  FTCache **v197; // rdi
  unsigned int v198; // eax
  unsigned __int64 v199; // r14
  unsigned __int64 v200; // rcx
  __int64 v201; // rcx
  unsigned __int64 v202; // rcx
  void *v203; // rsp
  void *v204; // rsp
  _DWORD *v205; // rax
  FTCache *v206; // rcx
  _QWORD *v207; // rax
  _QWORD *v208; // rdx
  _QWORD *v209; // rcx
  _QWORD *v210; // rax
  FTCache *v211; // rax
  FTCache **v212; // rdx
  __int16 v213; // r9
  FTCache *v214; // rcx
  __int64 v215; // rcx
  __int64 v216; // rdx
  _QWORD *v217; // rax
  struct _FILETIME *v218; // rdx
  struct _FILETIME v219; // rax
  unsigned int v220; // ecx
  FTCache *v221; // rax
  unsigned int dwLowDateTime; // edx
  FTCache::TLN_ENTRY *v223; // rcx
  __int64 *k; // rbx
  _QWORD *v225; // rcx
  __int64 v226; // rdx
  _QWORD *v227; // rcx
  __int64 v228; // rdx
  _QWORD *v229; // rcx
  __int64 v230; // rdx
  _QWORD *v231; // rcx
  __int64 v232; // rdx
  _QWORD *v233; // rcx
  __int64 v234; // rdx
  FTCache **v235; // r14
  unsigned __int16 v236; // di
  _QWORD *v237; // rcx
  __int64 v238; // rdx
  _QWORD *v239; // rcx
  __int64 v240; // rdx
  FTCache *v241; // rax
  FTCache **v242; // r8
  FTCache **v243; // rcx
  __int64 v244; // rax
  __int64 v245; // r8
  _QWORD *v246; // rcx
  __int64 v247; // rcx
  FTCache *v248; // rdx
  _QWORD *v249; // rax
  _QWORD *v250; // rdx
  _QWORD *m; // rax
  _QWORD *v252; // rcx
  __int64 **n; // rbx
  _QWORD *v254; // rax
  _QWORD *v255; // rdx
  _QWORD *ii; // rax
  __int64 *v257; // rcx
  char *v258; // r14
  char *v259; // r13
  FTCache::TLN_ENTRY *v260; // rcx
  _QWORD **v261; // rax
  _QWORD *v262; // r12
  _QWORD *v263; // rdi
  __int64 v264; // rbx
  __int64 v265; // r15
  _QWORD *v266; // rbx
  _QWORD *v267; // rcx
  __int64 v268; // rdx
  char *jj; // r15
  int v270; // eax
  struct FTCache::TDO_ENTRY *v271; // rbx
  char *v272; // rdi
  char *v273; // r13
  _QWORD *v274; // rcx
  __int64 v275; // rdx
  __int64 v276; // rax
  FTCache::TLN_ENTRY *v277; // rcx
  _QWORD **v278; // rax
  _QWORD *v279; // r14
  _QWORD *v280; // r15
  __int64 v281; // rax
  FTCache::TLN_ENTRY *v282; // rcx
  _QWORD *v283; // rax
  _QWORD *v284; // r12
  _QWORD *v285; // r14
  _QWORD *v286; // r15
  __int64 v287; // rax
  FTCache::TLN_ENTRY *v288; // rcx
  _QWORD *v289; // rdx
  _QWORD *v290; // rax
  _QWORD *v291; // r15
  _QWORD *v292; // r14
  __int64 v293; // rax
  FTCache::TLN_ENTRY *v294; // rcx
  int v295; // eax
  _QWORD *v296; // rax
  _QWORD *v297; // r12
  _QWORD *v298; // r14
  _QWORD *v299; // r15
  __int64 v300; // rax
  FTCache::TLN_ENTRY *v301; // rcx
  _BYTE v303[32]; // [rsp+0h] [rbp-40h] BYREF
  int v304; // [rsp+40h] [rbp+0h] BYREF
  FTCache *v305; // [rsp+48h] [rbp+8h] BYREF
  struct FTCache::TDO_ENTRY *inserted; // [rsp+50h] [rbp+10h]
  unsigned int v307; // [rsp+58h] [rbp+18h]
  char v308; // [rsp+5Ch] [rbp+1Ch]
  SIZE_T uBytes; // [rsp+60h] [rbp+20h]
  ULONG DestinationSidLength; // [rsp+68h] [rbp+28h]
  __int64 v311; // [rsp+70h] [rbp+30h]
  PVOID Buffer; // [rsp+78h] [rbp+38h]
  PSID Sid; // [rsp+80h] [rbp+40h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp+48h] BYREF
  PSID SourceSid; // [rsp+98h] [rbp+58h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp+60h] BYREF
  struct _LSA_FOREST_TRUST_INFORMATION2 *v317; // [rsp+B0h] [rbp+70h]
  FTCache **v318; // [rsp+B8h] [rbp+78h]
  _QWORD *v319; // [rsp+C0h] [rbp+80h]
  _QWORD *v320; // [rsp+C8h] [rbp+88h]

  v317 = a4;
  SystemTimeAsFileTime = 0;
  if ( a2 && a4 && a7 && a6 && a8 && a9 )
  {
    v12 = g_FTCache;
    v305 = g_FTCache;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Zdl(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, *(_DWORD *)a4, a5);
    memset_0(a6, 0, 0x60u);
    *a8 = 0;
    *a9 = 0;
    LsaDbLogFTInfo2(a4);
    inserted = (struct FTCache::TDO_ENTRY *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v12 + 8), a2);
    v13 = inserted;
    if ( inserted )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, a2);
      if ( *((_BYTE *)inserted + 92) != a5 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
        v24 = -1073741811;
LABEL_263:
        inserted = 0;
LABEL_264:
        if ( *a8 )
        {
          LocalFree(*a8);
          *a8 = 0;
          *a9 = 0;
        }
        goto LABEL_638;
      }
      FTCache::CopyTdoEntry(a6, inserted);
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, a2);
      v14 = 0;
      v15 = (unsigned int)a2->Length + 98;
      if ( v15 > g_ulMaxStackAllocSize )
        goto LABEL_19;
      v16 = v15 + g_ulAdditionalProbeSize + 8;
      if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16, 0) )
        goto LABEL_19;
      v17 = v15 + 23;
      if ( v15 + 23 <= v15 + 8 )
        v17 = 0xFFFFFFFFFFFFFF0LL;
      v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
      v19 = alloca(v18);
      v20 = alloca(v18);
      v14 = (FTCache **)&v304;
      if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v14 = &v305) == 0) )
      {
LABEL_19:
        if ( v15 + 8 >= v15 )
        {
          v21 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, _QWORD))g_pfnAllocate)(v15 + 8, 0);
          if ( !v21 )
          {
LABEL_23:
            v22 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            {
LABEL_26:
              v24 = -1073741670;
              goto LABEL_264;
            }
            v23 = 76;
LABEL_25:
            WPP_SF_(v22[2], v23, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
            goto LABEL_26;
          }
          *v21 = 1885431112;
          v14 = (FTCache **)(v21 + 2);
        }
        if ( !v14 )
          goto LABEL_23;
      }
      *((_DWORD *)v14 + 22) = 0;
      v14[2] = 0;
      FtcCopyUnicodeString((PUNICODE_STRING)v14, a2, (unsigned __int16 *)v14 + 47);
      inserted = (struct FTCache::TDO_ENTRY *)RtlInsertElementGenericTableAvl(
                                                (PRTL_AVL_TABLE)((char *)v305 + 8),
                                                v14,
                                                v15,
                                                0);
      v13 = inserted;
      if ( *((_DWORD *)v14 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      if ( !v13 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_26;
        v23 = 77;
        goto LABEL_25;
      }
      ++FTCache::sm_TdoEntries;
      *((_QWORD *)v13 + 1) = (char *)v13 + 94;
    }
    *((_DWORD *)v13 + 22) = 0;
    v319 = (_QWORD *)((char *)v13 + 56);
    v25 = (__int64 **)((char *)v13 + 24);
    *((_QWORD *)v13 + 8) = (char *)v13 + 56;
    *((_QWORD *)v13 + 7) = (char *)v13 + 56;
    *((_BYTE *)v13 + 92) = a5;
    v26 = (__int64 ***)((char *)v13 + 40);
    *((_QWORD *)v13 + 10) = (char *)v13 + 72;
    *((_QWORD *)v13 + 9) = (char *)v13 + 72;
    v318 = (FTCache **)((char *)v13 + 24);
    *((_QWORD *)v13 + 4) = (char *)v13 + 24;
    *((_QWORD *)v13 + 3) = (char *)v13 + 24;
    v320 = (_QWORD *)((char *)v13 + 40);
    *((_QWORD *)v13 + 6) = (char *)v13 + 40;
    *((_QWORD *)v13 + 5) = (char *)v13 + 40;
    if ( a3 )
    {
      v27 = RtlLengthSid(a3);
      v28 = LocalAlloc(0x40u, v27);
      *((_QWORD *)v13 + 2) = v28;
      if ( !v28 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v30 = 80;
          goto LABEL_44;
        }
        goto LABEL_45;
      }
      RtlCopySid(v27, v28, a3);
    }
    else
    {
      *((_QWORD *)v13 + 2) = 0;
    }
    v24 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v31 = v317;
    v32 = 0;
    v307 = 0;
    if ( *(_DWORD *)v317 )
    {
LABEL_49:
      v33 = *((_QWORD *)v31 + 1);
      BYTE1(v304) = 0;
      v34 = *(_QWORD *)(v33 + 8LL * v32);
      v311 = v34;
      v35 = *(unsigned int *)(v34 + 4);
      if ( !(_DWORD)v35 )
      {
        v175 = *(UNICODE_STRING *)(v34 + 16);
        v176 = 0;
        SourceString = v175;
        v178 = DnsNameComponents(&SourceString);
        LOWORD(uBytes) = v178;
        v179 = 0;
        v180 = 8LL * v178;
        if ( !v180 )
          goto LABEL_318;
        if ( v180 > g_ulMaxStackAllocSize )
          goto LABEL_318;
        v181 = v180 + g_ulAdditionalProbeSize + 8;
        if ( v181 < v180 || !(unsigned int)VerifyStackAvailable(v181, v177) )
          goto LABEL_318;
        v182 = v180 + 8;
        v183 = v180 + 23;
        if ( v180 + 23 <= v180 + 8 )
          v183 = 0xFFFFFFFFFFFFFF0LL;
        v184 = alloca(v183 & 0xFFFFFFFFFFFFFFF0uLL);
        v179 = (FTCache **)&v304;
        if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v179 = &v305) == 0) )
        {
LABEL_318:
          v182 = v180 + 8;
          if ( v180 + 8 >= v180 )
          {
            v185 = (_DWORD *)((__int64 (__fastcall *)(size_t))g_pfnAllocate)(v180 + 8);
            v179 = (FTCache **)v185;
            if ( v185 )
            {
              *v185 = 1885431112;
              v179 = (FTCache **)(v185 + 2);
            }
          }
        }
        if ( !v179 )
        {
          v239 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v240 = 81;
LABEL_448:
            WPP_SF_(v239[2], v240, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          }
LABEL_449:
          v24 = -1073741670;
          v235 = 0;
          v236 = 0;
          if ( v178 )
            goto LABEL_450;
          goto LABEL_462;
        }
        memset_0(v179, 0, v180);
        v176 = 0;
        if ( !v180 )
          goto LABEL_655;
        if ( v180 > g_ulMaxStackAllocSize )
          goto LABEL_655;
        v187 = v180 + g_ulAdditionalProbeSize + 8;
        if ( v187 < v180 || !(unsigned int)VerifyStackAvailable(v187, v186) )
          goto LABEL_655;
        v182 = v180 + 8;
        v188 = v180 + 23;
        if ( v180 + 23 <= v180 + 8 )
          v188 = 0xFFFFFFFFFFFFFF0LL;
        v189 = alloca(v188 & 0xFFFFFFFFFFFFFFF0uLL);
        v176 = (FTCache **)&v304;
        if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v176 = &v305) == 0) )
        {
LABEL_655:
          if ( v182 >= v180 )
          {
            v190 = (_DWORD *)((__int64 (__fastcall *)(size_t))g_pfnAllocate)(v182);
            v176 = (FTCache **)v190;
            if ( v190 )
            {
              *v190 = 1885431112;
              v176 = (FTCache **)(v190 + 2);
            }
          }
        }
        if ( !v176 )
        {
          v239 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v240 = 82;
            goto LABEL_448;
          }
          goto LABEL_449;
        }
        v191 = 0;
        SourceSid = 0;
        memset_0(v176, 0, v180);
        DestinationSidLength = 0;
        v192 = 0;
        if ( !v178 )
          goto LABEL_377;
        v193 = (struct _RTL_AVL_TABLE *)((char *)v305 + 112);
        for ( Sid = (char *)v305 + 112; ; v193 = (struct _RTL_AVL_TABLE *)Sid )
        {
          if ( (_WORD)v192 )
            NextDnsComponent(&SourceString);
          v194 = (FTCache *)RtlLookupElementGenericTableAvl(v193, &SourceString);
          v196 = (unsigned __int16)v192;
          v179[(unsigned __int16)v192] = v194;
          if ( v194 )
          {
            v208 = (_QWORD *)((char *)v194 + 24);
            BYTE1(v304) = 0;
            v209 = (_QWORD *)*((_QWORD *)v194 + 3);
            if ( v209 != (_QWORD *)((char *)v194 + 24) )
            {
              while ( 1 )
              {
                v210 = v209 - 2;
                if ( (struct FTCache::TDO_ENTRY *)v209[4] == inserted )
                {
                  if ( *((_BYTE *)v210 + 40) )
                  {
                    v237 = WPP_GLOBAL_Control;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                      goto LABEL_441;
                    v238 = 85;
                    goto LABEL_440;
                  }
                  if ( !v210[7] )
                  {
                    if ( v191 )
                    {
                      v237 = WPP_GLOBAL_Control;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                        goto LABEL_441;
                      v238 = 87;
LABEL_440:
                      WPP_SF_(v237[2], v238, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                      goto LABEL_441;
                    }
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, 0, v307, v210);
                    BYTE1(v304) = 1;
LABEL_377:
                    if ( *((_DWORD *)v179 - 2) == 1885431112 )
                      ((void (*)(void))g_pfnFree)();
                    if ( *((_DWORD *)v176 - 2) == 1885431112 )
                      ((void (*)(void))g_pfnFree)();
LABEL_381:
                    if ( BYTE1(v304) )
                    {
                      v13 = inserted;
                      v32 = v307;
                    }
                    else
                    {
LABEL_382:
                      v13 = inserted;
LABEL_383:
                      v32 = v307;
LABEL_384:
                      ++*((_DWORD *)v13 + 22);
                    }
LABEL_386:
                    v31 = v317;
                    v307 = ++v32;
                    if ( v32 >= *(_DWORD *)v317 )
                    {
                      v25 = (__int64 **)((char *)v13 + 24);
                      v26 = (__int64 ***)((char *)v13 + 40);
                      goto LABEL_388;
                    }
                    goto LABEL_49;
                  }
                  if ( !v191 )
                  {
                    v237 = WPP_GLOBAL_Control;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      v238 = 86;
                      goto LABEL_440;
                    }
LABEL_441:
                    v24 = -1073741811;
LABEL_433:
                    v178 = uBytes;
                    v235 = v176;
                    v236 = 0;
                    do
                    {
LABEL_450:
                      if ( v176 )
                      {
                        v241 = v235[v236];
                        if ( v241 )
                        {
                          v242 = *(FTCache ***)v241;
                          --FTCache::sm_TlnEntries;
                          if ( v242[1] != v241 )
                            goto LABEL_468;
                          v243 = (FTCache **)*((_QWORD *)v241 + 1);
                          if ( *v243 != v241 )
                            goto LABEL_468;
                          *v243 = (FTCache *)v242;
                          v242[1] = (FTCache *)v243;
                          v244 = (__int64)v235[v236] + 16;
                          v245 = *(_QWORD *)v244;
                          if ( *(_QWORD *)(*(_QWORD *)v244 + 8LL) != v244 )
                            goto LABEL_468;
                          v246 = (_QWORD *)*((_QWORD *)v235[v236] + 3);
                          if ( *v246 != v244 )
                            goto LABEL_468;
                          *v246 = v245;
                          *(_QWORD *)(v245 + 8) = v246;
                          v247 = *((_QWORD *)v235[v236] + 8);
                          --*(_DWORD *)(v247 + 16);
                          LocalFree(v235[v236]);
                        }
                      }
                      if ( v179 )
                      {
                        v248 = v179[v236];
                        if ( v248 )
                        {
                          if ( !*((_DWORD *)v248 + 4) )
                          {
                            RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 112), v248);
                            --FTCache::sm_TlnKeys;
                          }
                        }
                      }
                      ++v236;
                    }
                    while ( v236 < v178 );
LABEL_462:
                    if ( v179 && *((_DWORD *)v179 - 2) == 1885431112 )
                      ((void (*)(void))g_pfnFree)();
                    if ( v176 && *((_DWORD *)v176 - 2) == 1885431112 )
                      ((void (*)(void))g_pfnFree)();
                    goto LABEL_259;
                  }
                }
                v209 = (_QWORD *)*v209;
                if ( v209 == v208 )
                  goto LABEL_360;
              }
            }
          }
          else
          {
            v197 = 0;
            v198 = SourceString.Length + 42;
            v199 = v198;
            LODWORD(Buffer) = v198;
            if ( v198 > (unsigned __int64)g_ulMaxStackAllocSize )
              goto LABEL_349;
            v200 = v198 + g_ulAdditionalProbeSize + 8;
            if ( v200 < v198 || !(unsigned int)VerifyStackAvailable(v200, v195) )
              goto LABEL_349;
            v201 = v199 + 23;
            if ( v199 + 23 <= v199 + 8 )
              v201 = 0xFFFFFFFFFFFFFF0LL;
            v202 = v201 & 0xFFFFFFFFFFFFFFF0uLL;
            v203 = alloca(v202);
            v204 = alloca(v202);
            v197 = (FTCache **)&v304;
            if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v197 = &v305) == 0) )
            {
LABEL_349:
              if ( v199 + 8 >= v199 )
              {
                v205 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD))g_pfnAllocate)(
                                   v199 + 8,
                                   v195,
                                   0);
                if ( !v205 )
                  goto LABEL_429;
                *v205 = 1885431112;
                v197 = (FTCache **)(v205 + 2);
              }
              if ( !v197 )
              {
LABEL_429:
                v233 = WPP_GLOBAL_Control;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v234 = 83;
                  goto LABEL_431;
                }
LABEL_432:
                v24 = -1073741670;
                goto LABEL_433;
              }
            }
            *((_DWORD *)v197 + 4) = 0;
            FtcCopyUnicodeString((PUNICODE_STRING)v197, &SourceString, (unsigned __int16 *)v197 + 20);
            v179[v196] = (FTCache *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)Sid, v197, (CLONG)Buffer, 0);
            if ( *((_DWORD *)v197 - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
            v206 = v179[v196];
            if ( !v206 )
            {
              v233 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v234 = 84;
                goto LABEL_431;
              }
              goto LABEL_432;
            }
            ++FTCache::sm_TlnKeys;
            v191 = (FTCache *)SourceSid;
            v192 = DestinationSidLength;
            *((_QWORD *)v206 + 1) = (char *)v206 + 40;
            v207 = (_QWORD *)((char *)v179[v196] + 24);
            v207[1] = v207;
            *v207 = v207;
LABEL_360:
            BYTE1(v304) = 0;
          }
          v211 = (FTCache *)LocalAlloc(0x40u, 0x50u);
          v176[v196] = v211;
          if ( !v211 )
          {
            v233 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v234 = 89;
LABEL_431:
              WPP_SF_(v233[2], v234, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
            }
            goto LABEL_432;
          }
          v212 = v318;
          v213 = 1;
          ++FTCache::sm_TlnEntries;
          v214 = *v318;
          if ( *((FTCache ***)*v318 + 1) != v318 )
            goto LABEL_468;
          *(_QWORD *)v211 = v214;
          *((_QWORD *)v211 + 1) = v212;
          *((_QWORD *)v214 + 1) = v211;
          *v212 = v211;
          ++*((_DWORD *)v179[v196] + 4);
          v215 = (__int64)v179[v196] + 24;
          v216 = *(_QWORD *)v215;
          if ( *(_QWORD *)(*(_QWORD *)v215 + 8LL) != v215 )
            goto LABEL_468;
          v217 = (_QWORD *)((char *)v176[v196] + 16);
          v217[1] = v215;
          *v217 = v216;
          *(_QWORD *)(v216 + 8) = v217;
          v218 = (struct _FILETIME *)v311;
          *(_QWORD *)v215 = v217;
          if ( v218[1].dwLowDateTime || (v219 = SystemTimeAsFileTime, v218[1].dwHighDateTime) )
            v219 = v218[1];
          *((struct _FILETIME *)v176[v196] + 4) = v219;
          v220 = v307;
          *((_BYTE *)v176[v196] + 40) = 0;
          *((_DWORD *)v176[v196] + 11) = v220;
          *((_QWORD *)v176[v196] + 6) = inserted;
          *((_QWORD *)v176[v196] + 7) = v191;
          *((_QWORD *)v176[v196] + 8) = v179[v196];
          v221 = v176[v196];
          dwLowDateTime = v218->dwLowDateTime;
          if ( *((_BYTE *)v221 + 40) || (v223 = (FTCache::TLN_ENTRY *)*((_QWORD *)v221 + 7)) == 0 )
            *((_DWORD *)v221 + 18) = dwLowDateTime;
          else
            FTCache::TLN_ENTRY::SetFlags(v223, dwLowDateTime);
          v191 = v176[v196];
          LOWORD(v192) = v213 + v192;
          SourceSid = v191;
          DestinationSidLength = v192;
          if ( (unsigned __int16)v192 >= (unsigned __int16)uBytes )
            goto LABEL_377;
        }
      }
      if ( (_DWORD)v35 != 1 )
      {
        if ( (_DWORD)v35 != 2 )
        {
          if ( (_DWORD)v35 != 3 )
          {
            if ( (_DWORD)v35 != 4 )
            {
              v24 = -1073741811;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  119,
                  &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
                  v35);
              goto LABEL_260;
            }
            v36 = *(void **)(v34 + 16);
            SourceSid = v36;
            if ( !*(_WORD *)(v34 + 40) || (v37 = 1, !*(_QWORD *)(v34 + 48)) )
              v37 = 0;
            LOBYTE(v304) = v37;
            LODWORD(uBytes) = 0;
            if ( v36 )
            {
              if ( RtlValidSid(v36) )
              {
                LODWORD(uBytes) = RtlLengthSid(v36);
                goto LABEL_60;
              }
              v225 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v226 = 108;
                goto LABEL_391;
              }
              goto LABEL_392;
            }
LABEL_60:
            v38 = v305;
            v39 = v34;
            v42 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 528), (PVOID)(v34 + 24));
            if ( v37 )
              v43 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v38 + 632), (PVOID)(v34 + 40));
            else
              v43 = 0;
            if ( !v42 )
            {
              v44 = *(unsigned __int16 *)(v39 + 24);
              v45 = 0;
              v46 = (unsigned int)(v44 + 42);
              if ( (unsigned int)v46 <= (unsigned __int64)g_ulMaxStackAllocSize )
              {
                v47 = (unsigned int)v46 + g_ulAdditionalProbeSize + 8;
                if ( v47 >= (unsigned int)v46 )
                {
                  if ( (unsigned int)VerifyStackAvailable(v47, v40) )
                  {
                    v48 = v46 + 23;
                    if ( v46 + 23 <= (unsigned __int64)(v46 + 8) )
                      v48 = 0xFFFFFFFFFFFFFF0LL;
                    v49 = v48 & 0xFFFFFFFFFFFFFFF0uLL;
                    v50 = alloca(v49);
                    v51 = alloca(v49);
                    v45 = (FTCache **)&v304;
                    if ( v303 != (_BYTE *)-64LL )
                    {
                      v304 = 1801679955;
                      v45 = &v305;
                      if ( &v305 )
                        goto LABEL_75;
                    }
                  }
                }
              }
              if ( v46 + 8 < (unsigned __int64)(unsigned int)v46 )
                goto LABEL_74;
              v52 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, _QWORD *, _QWORD))g_pfnAllocate)(
                                v46 + 8,
                                v40,
                                v41,
                                0);
              if ( v52 )
              {
                *v52 = 1885431112;
                v45 = (FTCache **)(v52 + 2);
LABEL_74:
                if ( v45 )
                {
LABEL_75:
                  v53 = (const UNICODE_STRING *)(v311 + 24);
                  *((_DWORD *)v45 + 4) = 0;
                  FtcCopyUnicodeString((PUNICODE_STRING)v45, v53, (unsigned __int16 *)v45 + 20);
                  v54 = v46;
                  v55 = v305;
                  v42 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 528), v45, v54, 0);
                  if ( *((_DWORD *)v45 - 2) == 1885431112 )
                    ((void (*)(void))g_pfnFree)();
                  if ( !v42 )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        110,
                        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                    v24 = -1073741670;
                    goto LABEL_647;
                  }
                  ++FTCache::sm_ScannerDnsNameKeys;
                  v37 = v304;
                  v42[1] = v42 + 5;
                  v42[4] = v42 + 3;
                  v42[3] = v42 + 3;
                  BYTE2(v304) = 1;
                  goto LABEL_79;
                }
              }
              v227 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v228 = 109;
                goto LABEL_398;
              }
LABEL_399:
              v24 = -1073741670;
              goto LABEL_259;
            }
            BYTE2(v304) = 0;
            v68 = (_QWORD *)v42[3];
            if ( v68 != v42 + 3 )
            {
              v56 = inserted;
              while ( 1 )
              {
                v41 = v68 - 2;
                if ( (struct FTCache::TDO_ENTRY *)v68[7] == inserted )
                  break;
                v68 = (_QWORD *)*v68;
                if ( v68 == v42 + 3 )
                  goto LABEL_80;
              }
              v69 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v70 = 111;
                goto LABEL_181;
              }
              goto LABEL_182;
            }
LABEL_79:
            v56 = inserted;
LABEL_80:
            v57 = 0;
            if ( v37 )
            {
              if ( !v43 )
              {
                v58 = 0;
                v59 = (unsigned int)*(unsigned __int16 *)(v311 + 40) + 42;
                if ( v59 > g_ulMaxStackAllocSize )
                  goto LABEL_656;
                v60 = v59 + g_ulAdditionalProbeSize + 8;
                if ( v60 < v59 || !(unsigned int)VerifyStackAvailable(v60, v56) )
                  goto LABEL_656;
                v61 = v59 + 23;
                if ( v59 + 23 <= v59 + 8 )
                  v61 = 0xFFFFFFFFFFFFFF0LL;
                v62 = v61 & 0xFFFFFFFFFFFFFFF0uLL;
                v63 = alloca(v62);
                v64 = alloca(v62);
                v58 = (FTCache **)&v304;
                if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v58 = &v305) == 0) )
                {
LABEL_656:
                  if ( v59 + 8 < v59 )
                    goto LABEL_92;
                  v65 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, struct FTCache::TDO_ENTRY *, _QWORD *, _QWORD))g_pfnAllocate)(
                                    v59 + 8,
                                    v56,
                                    v41,
                                    0);
                  if ( !v65 )
                    goto LABEL_93;
                  *v65 = 1885431112;
                  v58 = (FTCache **)(v65 + 2);
LABEL_92:
                  if ( !v58 )
                  {
LABEL_93:
                    v66 = WPP_GLOBAL_Control;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      v67 = 112;
                      goto LABEL_95;
                    }
LABEL_126:
                    v24 = -1073741670;
LABEL_127:
                    v77 = v311;
                    v78 = v305;
                    if ( BYTE2(v304) )
                    {
                      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 528), (PVOID)(v311 + 24));
                      --FTCache::sm_ScannerDnsNameKeys;
                    }
                    if ( v57 )
                    {
                      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v78 + 632), (PVOID)(v77 + 40));
                      --FTCache::sm_ScannerNetbiosNameKeys;
                    }
LABEL_258:
                    if ( v24 < 0 )
                      goto LABEL_259;
                    goto LABEL_381;
                  }
                }
                v71 = (const UNICODE_STRING *)(v311 + 40);
                *((_DWORD *)v58 + 4) = 0;
                FtcCopyUnicodeString((PUNICODE_STRING)v58, v71, (unsigned __int16 *)v58 + 20);
                v43 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 632), v58, v59, 0);
                if ( *((_DWORD *)v58 - 2) == 1885431112 )
                  ((void (*)(void))g_pfnFree)();
                if ( !v43 )
                {
                  v66 = WPP_GLOBAL_Control;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                    goto LABEL_126;
                  v67 = 113;
                  goto LABEL_95;
                }
                v43[1] = v43 + 5;
                ++FTCache::sm_ScannerNetbiosNameKeys;
                v57 = 1;
                v43[4] = v43 + 3;
                v43[3] = v43 + 3;
LABEL_109:
                v72 = LocalAlloc(0x40u, 0x68u);
                v73 = v72;
                if ( !v72 )
                {
                  v66 = WPP_GLOBAL_Control;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                    goto LABEL_126;
                  v67 = 115;
LABEL_95:
                  WPP_SF_(v66[2], v67, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                  goto LABEL_126;
                }
                memset_0(v72, 0, 0x68u);
                v75 = SourceSid;
                if ( SourceSid )
                {
                  v76 = LocalAlloc(0x40u, (unsigned int)uBytes);
                  v73[8] = v76;
                  if ( !v76 )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        116,
                        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                    LocalFree(v73);
                    goto LABEL_126;
                  }
                }
                v79 = v319;
                ++FTCache::sm_ScannerInfoEntries;
                v80 = *v319;
                if ( *(_QWORD **)(*v319 + 8LL) == v319 )
                {
                  v73[1] = v319;
                  *v73 = v80;
                  *(_QWORD *)(v80 + 8) = v73;
                  *v79 = v73;
                  v81 = v42 + 3;
                  ++*((_DWORD *)v42 + 4);
                  v82 = v42[3];
                  if ( *(_QWORD **)(v82 + 8) == v42 + 3 )
                  {
                    v73[2] = v82;
                    v73[3] = v81;
                    *(_QWORD *)(v82 + 8) = v73 + 2;
                    *v81 = v73 + 2;
                    v83 = v73 + 4;
                    if ( !(_BYTE)v304 )
                    {
                      v73[5] = v83;
                      *v83 = v83;
LABEL_137:
                      v86 = (_DWORD *)v311;
                      if ( *(_DWORD *)(v311 + 8) || (v87 = SystemTimeAsFileTime, *(_DWORD *)(v311 + 12)) )
                        v87 = *(struct _FILETIME *)(v311 + 8);
                      v73[6] = v87;
                      *((_DWORD *)v73 + 14) = v307;
                      if ( v75 )
                        RtlCopySid(uBytes, (PSID)v73[8], v75);
                      v73[9] = inserted;
                      v73[10] = v42;
                      v73[11] = v43;
                      *((_DWORD *)v73 + 24) = *v86;
                      goto LABEL_382;
                    }
                    ++*((_DWORD *)v43 + 4);
                    v84 = v43 + 3;
                    v85 = v43[3];
                    if ( *(_QWORD **)(v85 + 8) == v43 + 3 )
                    {
                      *v83 = v85;
                      v73[5] = v84;
                      *(_QWORD *)(v85 + 8) = v83;
                      *v84 = v83;
                      goto LABEL_137;
                    }
                  }
                }
                goto LABEL_468;
              }
            }
            else if ( !v43 )
            {
              goto LABEL_109;
            }
            for ( i = (_QWORD *)v43[3]; ; i = (_QWORD *)*i )
            {
              if ( i == v43 + 3 )
                goto LABEL_109;
              if ( (struct FTCache::TDO_ENTRY *)i[5] == v56 )
                break;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, i - 4, v307, i - 4);
            BYTE1(v304) = 1;
            goto LABEL_127;
          }
          v88 = LocalAlloc(0x40u, 0x38u);
          if ( v88 )
          {
            v89 = *(_DWORD *)(v34 + 16);
            v88[8] = v89;
            if ( !v89 )
            {
              *((_QWORD *)v88 + 5) = 0;
LABEL_148:
              ++FTCache::sm_BinaryEntries;
              v91 = (_QWORD *)((char *)v13 + 72);
              v92 = *((_QWORD *)v13 + 9);
              if ( *(struct FTCache::TDO_ENTRY **)(v92 + 8) == (struct FTCache::TDO_ENTRY *)((char *)v13 + 72) )
              {
                *(_QWORD *)v88 = v92;
                *((_QWORD *)v88 + 1) = v91;
                *(_QWORD *)(v92 + 8) = v88;
                *v91 = v88;
                v88[6] = *(_DWORD *)(v34 + 4);
                v88[12] = *(_DWORD *)v34;
                goto LABEL_383;
              }
              goto LABEL_468;
            }
            v90 = LocalAlloc(0x40u, v89);
            *((_QWORD *)v88 + 5) = v90;
            if ( v90 )
            {
              memcpy_0(v90, *(const void **)(v34 + 24), (unsigned int)v88[8]);
              goto LABEL_148;
            }
            LocalFree(v88);
            v29 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v30 = 118;
              goto LABEL_44;
            }
          }
          else
          {
            v29 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v30 = 117;
LABEL_44:
              WPP_SF_(v29[2], v30, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
            }
          }
LABEL_45:
          v24 = -1073741670;
          goto LABEL_260;
        }
        v93 = *(void **)(v34 + 16);
        v94 = (void *)(v34 + 40);
        Sid = v93;
        Buffer = (PVOID)(v34 + 40);
        if ( !*(_WORD *)(v34 + 40) || (v95 = 1, !*(_QWORD *)(v34 + 48)) )
          v95 = 0;
        BYTE2(v304) = v95;
        if ( !RtlValidSid(v93) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          v24 = -1073741811;
          goto LABEL_259;
        }
        v96 = (void *)(v34 + 24);
        DestinationSidLength = RtlLengthSid(Sid);
        v97 = DestinationSidLength;
        v98 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 216), &Sid);
        SourceSid = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 320), v96);
        v100 = SourceSid;
        if ( v95 )
          v101 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 424), v94);
        else
          v101 = 0;
        if ( v98 )
        {
          v308 = 0;
          v111 = (_QWORD *)v98[2];
          if ( v111 != v98 + 2 )
          {
            v112 = inserted;
            while ( 1 )
            {
              v41 = v111 - 2;
              if ( (struct FTCache::TDO_ENTRY *)v111[9] == inserted )
                break;
              v111 = (_QWORD *)*v111;
              if ( v111 == v98 + 2 )
                goto LABEL_184;
            }
            v69 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v70 = 99;
LABEL_181:
              WPP_SF_dq(v69[2], v70, v41, v307, v41);
            }
LABEL_182:
            BYTE1(v304) = 1;
            goto LABEL_258;
          }
LABEL_183:
          v112 = inserted;
LABEL_184:
          LOBYTE(uBytes) = 0;
          v113 = 0;
          LOBYTE(v304) = 0;
          if ( v100 )
          {
            v136 = (_QWORD *)v100[3];
            if ( v136 != v100 + 3 )
            {
              while ( (struct FTCache::TDO_ENTRY *)v136[7] != v112 )
              {
                v136 = (_QWORD *)*v136;
                if ( v136 == v100 + 3 )
                  goto LABEL_205;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v136 - 4, v307, v136 - 4);
              BYTE1(v304) = 1;
              goto LABEL_251;
            }
          }
          else
          {
            v114 = 0;
            v115 = (unsigned int)*(unsigned __int16 *)(v311 + 24) + 42;
            if ( v115 > g_ulMaxStackAllocSize )
              goto LABEL_192;
            v116 = v115 + g_ulAdditionalProbeSize + 8;
            if ( v116 < v115 || !(unsigned int)VerifyStackAvailable(v116, v112) )
              goto LABEL_192;
            v117 = v115 + 23;
            if ( v115 + 23 <= v115 + 8 )
              v117 = 0xFFFFFFFFFFFFFF0LL;
            v118 = v117 & 0xFFFFFFFFFFFFFFF0uLL;
            v119 = alloca(v118);
            v120 = alloca(v118);
            v114 = (FTCache **)&v304;
            if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v114 = &v305) == 0) )
            {
LABEL_192:
              if ( v115 + 8 >= v115 )
              {
                v121 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, struct FTCache::TDO_ENTRY *))g_pfnAllocate)(
                                   v115 + 8,
                                   v112);
                if ( !v121 )
                  goto LABEL_196;
                *v121 = 1885431112;
                v114 = (FTCache **)(v121 + 2);
              }
              if ( !v114 )
              {
LABEL_196:
                v122 = WPP_GLOBAL_Control;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v123 = 100;
LABEL_198:
                  WPP_SF_(v122[2], v123, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                  goto LABEL_249;
                }
                goto LABEL_249;
              }
            }
            v124 = v311;
            *((_DWORD *)v114 + 4) = 0;
            FtcCopyUnicodeString((PUNICODE_STRING)v114, (PCUNICODE_STRING)(v124 + 24), (unsigned __int16 *)v114 + 20);
            SourceSid = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 320), v114, v115, 0);
            v125 = SourceSid;
            if ( *((_DWORD *)v114 - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
            if ( !v125 )
            {
              v122 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_249;
              v123 = 101;
              goto LABEL_198;
            }
            ++FTCache::sm_DnsNameKeys;
            v125[1] = v125 + 5;
            v125[4] = v125 + 3;
            v125[3] = v125 + 3;
            LOBYTE(uBytes) = 1;
          }
LABEL_205:
          v126 = BYTE2(v304);
          if ( BYTE2(v304) )
          {
            if ( !v101 )
            {
              v127 = (UNICODE_STRING *)Buffer;
              v128 = 0;
              v129 = (unsigned int)*(unsigned __int16 *)Buffer + 42;
              if ( v129 > g_ulMaxStackAllocSize )
                goto LABEL_214;
              v130 = v129 + g_ulAdditionalProbeSize + 8;
              if ( v130 < v129 || !(unsigned int)VerifyStackAvailable(v130, v112) )
                goto LABEL_214;
              v131 = v129 + 23;
              if ( v129 + 23 <= v129 + 8 )
                v131 = 0xFFFFFFFFFFFFFF0LL;
              v132 = v131 & 0xFFFFFFFFFFFFFFF0uLL;
              v133 = alloca(v132);
              v134 = alloca(v132);
              v128 = (FTCache **)&v304;
              if ( v303 == (_BYTE *)-64LL || (v304 = 1801679955, (v128 = &v305) == 0) )
              {
LABEL_214:
                if ( v129 + 8 >= v129 )
                {
                  v135 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, struct FTCache::TDO_ENTRY *, _QWORD))g_pfnAllocate)(
                                     v129 + 8,
                                     v112,
                                     0);
                  if ( !v135 )
                  {
LABEL_218:
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        103,
                        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                    v113 = v304;
                    v24 = -1073741670;
                    goto LABEL_252;
                  }
                  *v135 = 1885431112;
                  v128 = (FTCache **)(v135 + 2);
                }
                if ( !v128 )
                  goto LABEL_218;
              }
              *((_DWORD *)v128 + 4) = 0;
              FtcCopyUnicodeString((PUNICODE_STRING)v128, v127, (unsigned __int16 *)v128 + 20);
              v101 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 424), v128, v129, 0);
              if ( *((_DWORD *)v128 - 2) == 1885431112 )
                ((void (*)(void))g_pfnFree)();
              if ( !v101 )
              {
                v122 = WPP_GLOBAL_Control;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_249;
                v123 = 104;
                goto LABEL_198;
              }
              v126 = BYTE2(v304);
              v101[1] = v101 + 5;
              ++FTCache::sm_NetbiosNameKeys;
              LOBYTE(v304) = 1;
              v101[4] = v101 + 3;
              v101[3] = v101 + 3;
LABEL_234:
              v137 = LocalAlloc(0x40u, 0x88u);
              if ( v137 )
              {
                v139 = LocalAlloc(0x40u, DestinationSidLength);
                v137[10] = v139;
                if ( v139 )
                {
                  v141 = v320;
                  ++FTCache::sm_DomainInfoEntries;
                  v142 = *v320;
                  if ( *(_QWORD **)(*v320 + 8LL) == v320 )
                  {
                    v137[1] = v320;
                    *v137 = v142;
                    *(_QWORD *)(v142 + 8) = v137;
                    *v141 = v137;
                    v143 = v98 + 2;
                    ++*((_DWORD *)v98 + 2);
                    v144 = v98[2];
                    if ( *(_QWORD **)(v144 + 8) == v98 + 2 )
                    {
                      v145 = (char *)SourceSid;
                      v137[3] = v143;
                      v137[2] = v144;
                      *(_QWORD *)(v144 + 8) = v137 + 2;
                      *v143 = v137 + 2;
                      v146 = v145 + 24;
                      ++*((_DWORD *)v145 + 4);
                      v147 = *((_QWORD *)v145 + 3);
                      if ( *(char **)(v147 + 8) == v145 + 24 )
                      {
                        v137[4] = v147;
                        v137[5] = v146;
                        *(_QWORD *)(v147 + 8) = v137 + 4;
                        *v146 = v137 + 4;
                        v148 = v137 + 6;
                        if ( v126 )
                        {
                          ++*((_DWORD *)v101 + 4);
                          v149 = v101 + 3;
                          v150 = v101[3];
                          if ( *(_QWORD **)(v150 + 8) != v101 + 3 )
                            goto LABEL_468;
                          *v148 = v150;
                          v137[7] = v149;
                          *(_QWORD *)(v150 + 8) = v148;
                          *v149 = v148;
                        }
                        else
                        {
                          v137[7] = v148;
                          *v148 = v148;
                        }
                        v151 = (_DWORD *)v311;
                        if ( *(_DWORD *)(v311 + 8) || (v152 = SystemTimeAsFileTime, *(_DWORD *)(v311 + 12)) )
                          v152 = *(struct _FILETIME *)(v311 + 8);
                        v153 = (void *)v137[10];
                        v154 = DestinationSidLength;
                        v137[8] = v152;
                        *((_DWORD *)v137 + 18) = v307;
                        RtlCopySid(v154, v153, Sid);
                        v137[11] = inserted;
                        v137[12] = 0;
                        v137[13] = v98;
                        v137[14] = v145;
                        v137[15] = v101;
                        *((_DWORD *)v137 + 32) = *v151;
                        goto LABEL_382;
                      }
                    }
                  }
LABEL_468:
                  __fastfail(3u);
                }
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
                LocalFree(v137);
                goto LABEL_249;
              }
              v122 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v123 = 106;
                goto LABEL_198;
              }
LABEL_249:
              v24 = -1073741670;
LABEL_250:
              v113 = v304;
LABEL_251:
              v127 = (UNICODE_STRING *)Buffer;
LABEL_252:
              v140 = v305;
              if ( v308 )
              {
                RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 216), &Sid);
                --FTCache::sm_SidKeys;
              }
              if ( (_BYTE)uBytes )
              {
                RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v140 + 320), (PVOID)(v311 + 24));
                --FTCache::sm_DnsNameKeys;
              }
              if ( v113 )
              {
                RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v140 + 424), v127);
                --FTCache::sm_NetbiosNameKeys;
              }
              goto LABEL_258;
            }
          }
          else if ( !v101 )
          {
            goto LABEL_234;
          }
          v138 = (_QWORD *)v101[3];
          if ( v138 != v101 + 3 )
          {
            while ( (struct FTCache::TDO_ENTRY *)v138[5] != inserted )
            {
              v138 = (_QWORD *)*v138;
              if ( v138 == v101 + 3 )
                goto LABEL_234;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, v138 - 6, v307, v138 - 6);
            BYTE1(v304) = 1;
            goto LABEL_250;
          }
          goto LABEL_234;
        }
        v102 = 0;
        v103 = v97 + 32;
        if ( (_DWORD)v103 )
        {
          if ( (unsigned int)v103 <= (unsigned __int64)g_ulMaxStackAllocSize )
          {
            v104 = (unsigned int)v103 + g_ulAdditionalProbeSize + 8;
            if ( v104 >= (unsigned int)v103 )
            {
              if ( (unsigned int)VerifyStackAvailable(v104, v99) )
              {
                v105 = v103 + 23;
                if ( v103 + 23 <= (unsigned __int64)(v103 + 8) )
                  v105 = 0xFFFFFFFFFFFFFF0LL;
                v106 = v105 & 0xFFFFFFFFFFFFFFF0uLL;
                v107 = alloca(v106);
                v108 = alloca(v106);
                v102 = (FTCache **)&v304;
                if ( v303 != (_BYTE *)-64LL )
                {
                  v304 = 1801679955;
                  v102 = &v305;
                  if ( &v305 )
                    goto LABEL_170;
                }
              }
            }
          }
        }
        if ( v103 + 8 >= (unsigned __int64)(unsigned int)v103 )
        {
          v109 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(v103 + 8, v99, 0);
          if ( !v109 )
            goto LABEL_408;
          *v109 = 1885431112;
          v102 = (FTCache **)(v109 + 2);
        }
        if ( v102 )
        {
LABEL_170:
          v110 = DestinationSidLength;
          *v102 = (FTCache *)(v102 + 4);
          *((_DWORD *)v102 + 2) = 0;
          RtlCopySid(v110, v102 + 4, Sid);
          v98 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 216), v102, v103, 0);
          if ( *((_DWORD *)v102 - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          if ( v98 )
          {
            v100 = SourceSid;
            *v98 = v98 + 4;
            ++FTCache::sm_SidKeys;
            v98[3] = v98 + 2;
            v98[2] = v98 + 2;
            v308 = 1;
            goto LABEL_183;
          }
          v227 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_399;
          v228 = 98;
LABEL_398:
          WPP_SF_(v227[2], v228, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          goto LABEL_399;
        }
LABEL_408:
        v227 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_399;
        v228 = 97;
        goto LABEL_398;
      }
      SourceString = *(UNICODE_STRING *)(v34 + 16);
      if ( DnsNameComponents(&SourceString) <= 1u )
      {
        v225 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v226 = 90;
LABEL_391:
          WPP_SF_(v225[2], v226, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
        }
LABEL_392:
        v24 = -1073741811;
        goto LABEL_260;
      }
      v55 = v305;
      v155 = (char *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 112), &SourceString);
      v157 = v155;
      if ( v155 )
      {
        v172 = v155 + 24;
        for ( j = (_QWORD *)*((_QWORD *)v155 + 3); ; j = (_QWORD *)*j )
        {
          if ( j == v172 )
            goto LABEL_294;
          v174 = j - 2;
          if ( (struct FTCache::TDO_ENTRY *)j[4] == v13 )
            break;
        }
        if ( *((_BYTE *)v174 + 40) != 1 )
        {
          v231 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v232 = 93;
            goto LABEL_421;
          }
          goto LABEL_422;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, v174, v32, j - 2);
        goto LABEL_386;
      }
      v158 = 0;
      v159 = (unsigned int)SourceString.Length + 42;
      if ( v159 <= g_ulMaxStackAllocSize )
      {
        v160 = v159 + g_ulAdditionalProbeSize + 8;
        if ( v160 >= v159 )
        {
          if ( (unsigned int)VerifyStackAvailable(v160, v156) )
          {
            v161 = v159 + 23;
            if ( v159 + 23 <= v159 + 8 )
              v161 = 0xFFFFFFFFFFFFFF0LL;
            v162 = v161 & 0xFFFFFFFFFFFFFFF0uLL;
            v163 = alloca(v162);
            v164 = alloca(v162);
            v158 = (FTCache **)&v304;
            if ( v303 != (_BYTE *)-64LL )
            {
              v304 = 1801679955;
              v158 = &v305;
              if ( &v305 )
                goto LABEL_290;
            }
          }
        }
      }
      if ( v159 + 8 >= v159 )
      {
        v165 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD))g_pfnAllocate)(v159 + 8, v156, 0);
        if ( !v165 )
          goto LABEL_415;
        *v165 = 1885431112;
        v158 = (FTCache **)(v165 + 2);
      }
      if ( v158 )
      {
LABEL_290:
        *((_DWORD *)v158 + 4) = 0;
        FtcCopyUnicodeString((PUNICODE_STRING)v158, &SourceString, (unsigned __int16 *)v158 + 20);
        v157 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v55 + 112), v158, v159, 0);
        if ( *((_DWORD *)v158 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        if ( v157 )
        {
          ++FTCache::sm_TlnKeys;
          v34 = v311;
          v32 = v307;
          v157[1] = v157 + 5;
          v157[4] = v157 + 3;
          v157[3] = v157 + 3;
LABEL_294:
          v166 = LocalAlloc(0x40u, 0x50u);
          if ( v166 )
          {
            v167 = (_QWORD *)((char *)v13 + 24);
            v168 = *((_QWORD *)v13 + 3);
            ++FTCache::sm_TlnEntries;
            if ( *(struct FTCache::TDO_ENTRY **)(v168 + 8) == (struct FTCache::TDO_ENTRY *)((char *)v13 + 24) )
            {
              v166[1] = v167;
              *v166 = v168;
              *(_QWORD *)(v168 + 8) = v166;
              *v167 = v166;
              v169 = v157 + 3;
              ++*((_DWORD *)v157 + 4);
              v170 = v157[3];
              if ( *(_QWORD **)(v170 + 8) == v157 + 3 )
              {
                v166[2] = v170;
                v166[3] = v169;
                *(_QWORD *)(v170 + 8) = v166 + 2;
                *v169 = v166 + 2;
                v166[7] = 0;
                *((_BYTE *)v166 + 40) = 1;
                *((_DWORD *)v166 + 11) = v32;
                v166[6] = v13;
                v166[8] = v157;
                *((_DWORD *)v166 + 18) = *(_DWORD *)v34;
                if ( *(_DWORD *)(v34 + 8) || *(_DWORD *)(v34 + 12) )
                  v171 = *(struct _FILETIME *)(v34 + 8);
                else
                  v171 = SystemTimeAsFileTime;
                v166[4] = v171;
                goto LABEL_384;
              }
            }
            goto LABEL_468;
          }
          v229 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v230 = 95;
            goto LABEL_417;
          }
LABEL_418:
          v24 = -1073741670;
          goto LABEL_261;
        }
        v229 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_418;
        v230 = 92;
LABEL_417:
        WPP_SF_(v229[2], v230, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
        goto LABEL_418;
      }
LABEL_415:
      v229 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_418;
      v230 = 91;
      goto LABEL_417;
    }
LABEL_388:
    for ( k = *v25; k != (__int64 *)v25; k = (__int64 *)*k )
    {
      if ( *((_BYTE *)k + 40) )
      {
        SourceString = *(UNICODE_STRING *)k[8];
        NextDnsComponent(&SourceString);
        v55 = v305;
        while ( SourceString.Length )
        {
          v249 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v55 + 112), &SourceString);
          if ( v249 )
          {
            v250 = v249 + 3;
            for ( m = (_QWORD *)v249[3]; m != v250; m = (_QWORD *)*m )
            {
              v252 = m - 2;
              if ( (struct FTCache::TDO_ENTRY *)m[4] == v13 && !*((_BYTE *)v252 + 40) && !v252[7] )
              {
                k[7] = (__int64)v252;
                break;
              }
            }
            if ( k[7] )
              goto LABEL_484;
          }
          NextDnsComponent(&SourceString);
        }
        if ( !k[7] )
        {
          v231 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v232 = 120;
            goto LABEL_421;
          }
LABEL_422:
          v24 = -1073741811;
          goto LABEL_261;
        }
      }
LABEL_484:
      ;
    }
    for ( n = *v26; n != (__int64 **)v26; n = (__int64 **)*n )
    {
      v55 = v305;
      SourceString = *(UNICODE_STRING *)n[14];
      if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)SourceString) )
      {
        while ( 1 )
        {
          v254 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v55 + 112), &SourceString);
          if ( v254 )
          {
            v255 = v254 + 3;
            for ( ii = (_QWORD *)v254[3]; ii != v255; ii = (_QWORD *)*ii )
            {
              v257 = ii - 2;
              if ( (struct FTCache::TDO_ENTRY *)ii[4] == v13 && !*((_BYTE *)v257 + 40) && !v257[7] )
              {
                n[12] = v257;
                break;
              }
            }
            if ( n[12] )
              break;
          }
          NextDnsComponent(&SourceString);
          if ( !SourceString.Length )
            goto LABEL_501;
        }
      }
      else
      {
LABEL_501:
        if ( !n[12] && ((_DWORD)n[16] & 1) == 0 )
        {
          v231 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v232 = 121;
LABEL_421:
            WPP_SF_(v231[2], v232, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          }
          goto LABEL_422;
        }
      }
    }
    v258 = (char *)*((_QWORD *)v13 + 3);
    v259 = (char *)v13 + 24;
    while ( 1 )
    {
      if ( v258 == v259 )
      {
        v271 = inserted;
        v272 = (char *)*((_QWORD *)inserted + 5);
        v273 = (char *)inserted + 40;
        while ( 1 )
        {
          if ( v272 == v273 )
          {
            v24 = 0;
LABEL_638:
            *a7 = inserted;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                136,
                &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
                (unsigned int)v24);
            return (unsigned int)v24;
          }
          v276 = *((_QWORD *)v272 + 12);
          if ( v276 )
          {
            if ( !*(_BYTE *)(v276 + 40) )
            {
              v277 = *(FTCache::TLN_ENTRY **)(v276 + 56);
              if ( v277 )
              {
                if ( !FTCache::TLN_ENTRY::Enabled(v277) )
                  goto LABEL_635;
              }
              else if ( *(_WORD *)(v276 + 72) )
              {
                goto LABEL_635;
              }
              if ( !FTCache::TDO_ENTRY::Excludes(
                      *((FTCache::TDO_ENTRY **)v272 + 11),
                      *((const struct _UNICODE_STRING **)v272 + 14)) )
                break;
            }
          }
LABEL_635:
          v272 = *(char **)v272;
        }
        if ( (v272[128] & 3) != 0 )
        {
LABEL_598:
          v55 = v305;
          goto LABEL_599;
        }
        v278 = (_QWORD **)(*((_QWORD *)v272 + 13) + 16LL);
        v279 = *v278;
        while ( 1 )
        {
          if ( v279 == v278 )
          {
            v55 = v305;
            v283 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v305 + 424), *((PVOID *)v272 + 14));
            if ( v283 )
            {
              v284 = v283 + 3;
              v285 = (_QWORD *)v283[3];
              while ( 1 )
              {
                if ( v285 == v284 )
                  goto LABEL_598;
                v286 = v285 - 6;
                v287 = v285[6];
                if ( v287
                  && (struct FTCache::TDO_ENTRY *)v286[11] != v271
                  && (struct FTCache::TDO_ENTRY *)v286[11] != a6
                  && (v286[16] & 0xF) == 0
                  && !*(_BYTE *)(v287 + 40) )
                {
                  v288 = *(FTCache::TLN_ENTRY **)(v287 + 56);
                  if ( v288 )
                  {
                    if ( !FTCache::TLN_ENTRY::Enabled(v288) )
                      goto LABEL_597;
                  }
                  else if ( *(_WORD *)(v287 + 72) )
                  {
                    goto LABEL_597;
                  }
                  v270 = FTCache::AddConflictPair(
                           a8,
                           a9,
                           ForestTrustDomainInfo,
                           v272,
                           2u,
                           ForestTrustDomainInfo,
                           v285 - 6,
                           8u);
                  v24 = v270;
                  if ( v270 < 0 )
                  {
                    v274 = WPP_GLOBAL_Control;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      v275 = 130;
                      goto LABEL_557;
                    }
                    goto LABEL_259;
                  }
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, 0, v272, *((_DWORD *)v272 + 18), v285 - 6);
                }
LABEL_597:
                v285 = (_QWORD *)*v285;
                v271 = inserted;
              }
            }
LABEL_599:
            v289 = (_QWORD *)*((_QWORD *)v272 + 15);
            if ( !v289 || (v272[128] & 0xF) != 0 )
              goto LABEL_634;
            v290 = v289 + 3;
            v291 = (_QWORD *)v289[3];
            while ( 2 )
            {
              if ( v291 == v290 )
              {
                v296 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v55 + 320), v289);
                if ( v296 )
                {
                  v297 = v296 + 3;
                  v298 = (_QWORD *)v296[3];
                  if ( v298 != v296 + 3 )
                  {
                    while ( 1 )
                    {
                      v271 = inserted;
                      v299 = v298 - 4;
                      v300 = v298[8];
                      if ( !v300
                        || (struct FTCache::TDO_ENTRY *)v299[11] == inserted
                        || (struct FTCache::TDO_ENTRY *)v299[11] == a6
                        || (v299[16] & 3) != 0
                        || *(_BYTE *)(v300 + 40) )
                      {
                        goto LABEL_632;
                      }
                      v301 = *(FTCache::TLN_ENTRY **)(v300 + 56);
                      if ( v301 )
                      {
                        if ( !FTCache::TLN_ENTRY::Enabled(v301) )
                          goto LABEL_632;
                      }
                      else if ( *(_WORD *)(v300 + 72) )
                      {
                        goto LABEL_632;
                      }
                      v270 = FTCache::AddConflictPair(
                               a8,
                               a9,
                               ForestTrustDomainInfo,
                               v272,
                               8u,
                               ForestTrustDomainInfo,
                               v298 - 4,
                               2u);
                      v24 = v270;
                      if ( v270 < 0 )
                      {
                        v274 = WPP_GLOBAL_Control;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        {
                          v275 = 134;
LABEL_557:
                          WPP_SF_d(v274[2], v275, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v270);
                        }
LABEL_259:
                        v13 = inserted;
LABEL_260:
                        v55 = v305;
LABEL_261:
                        if ( v13 )
                        {
                          FTCache::RollbackChanges(v55, v13, a6);
                          goto LABEL_263;
                        }
                        goto LABEL_264;
                      }
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, 0, v272, *((_DWORD *)v272 + 18), v298 - 4);
                      v271 = inserted;
LABEL_632:
                      v298 = (_QWORD *)*v298;
                      if ( v298 == v297 )
                        goto LABEL_635;
                    }
                  }
                }
LABEL_634:
                v271 = inserted;
                goto LABEL_635;
              }
              v292 = v291 - 6;
              v293 = v291[6];
              if ( v293
                && (struct FTCache::TDO_ENTRY *)v292[11] != inserted
                && (struct FTCache::TDO_ENTRY *)v292[11] != a6
                && (v292[16] & 0xF) == 0
                && v292[15]
                && !*(_BYTE *)(v293 + 40) )
              {
                v294 = *(FTCache::TLN_ENTRY **)(v293 + 56);
                if ( v294 )
                {
                  if ( FTCache::TLN_ENTRY::Enabled(v294) )
                  {
LABEL_612:
                    v295 = FTCache::AddConflictPair(
                             a8,
                             a9,
                             ForestTrustDomainInfo,
                             v272,
                             8u,
                             ForestTrustDomainInfo,
                             v291 - 6,
                             8u);
                    v24 = v295;
                    if ( v295 < 0 )
                    {
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          132,
                          &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
                          (unsigned int)v295);
LABEL_647:
                      v13 = inserted;
                      goto LABEL_261;
                    }
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, 0, v272, *((_DWORD *)v272 + 18), v291 - 6);
                  }
                }
                else if ( !*(_WORD *)(v293 + 72) )
                {
                  goto LABEL_612;
                }
              }
              v289 = (_QWORD *)*((_QWORD *)v272 + 15);
              v291 = (_QWORD *)*v291;
              v290 = v289 + 3;
              continue;
            }
          }
          v280 = v279 - 2;
          v281 = v279[10];
          if ( v281
            && (struct FTCache::TDO_ENTRY *)v280[11] != v271
            && (struct FTCache::TDO_ENTRY *)v280[11] != a6
            && (v280[16] & 3) == 0
            && !*(_BYTE *)(v281 + 40) )
          {
            v282 = *(FTCache::TLN_ENTRY **)(v281 + 56);
            if ( v282 )
            {
              if ( !FTCache::TLN_ENTRY::Enabled(v282) )
                goto LABEL_580;
            }
            else if ( *(_WORD *)(v281 + 72) )
            {
              goto LABEL_580;
            }
            v270 = FTCache::AddConflictPair(
                     a8,
                     a9,
                     ForestTrustDomainInfo,
                     v272,
                     2u,
                     ForestTrustDomainInfo,
                     v279 - 2,
                     2u);
            v24 = v270;
            if ( v270 < 0 )
            {
              v274 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v275 = 128;
                goto LABEL_557;
              }
              goto LABEL_259;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, 0, v272, *((_DWORD *)v272 + 18), v279 - 2);
            v271 = inserted;
          }
LABEL_580:
          v279 = (_QWORD *)*v279;
          v278 = (_QWORD **)(*((_QWORD *)v272 + 13) + 16LL);
        }
      }
      if ( !v258[40] )
      {
        v260 = (FTCache::TLN_ENTRY *)*((_QWORD *)v258 + 7);
        if ( !v260 )
        {
          if ( *((_WORD *)v258 + 36) )
            goto LABEL_552;
LABEL_513:
          v261 = (_QWORD **)(*((_QWORD *)v258 + 8) + 24LL);
          v262 = *v261;
          while ( 2 )
          {
            if ( v262 == v261 )
              goto LABEL_552;
            v263 = v262 - 2;
            if ( (struct FTCache::TDO_ENTRY *)v262[4] != inserted
              && (struct FTCache::TDO_ENTRY *)v263[6] != a6
              && !*((_BYTE *)v263 + 40) )
            {
              v264 = v263[7];
              if ( v264 )
              {
                if ( FTCache::TLN_ENTRY::Enabled((FTCache::TLN_ENTRY *)v263[7]) )
                  goto LABEL_521;
              }
              else if ( !*((_WORD *)v263 + 36) )
              {
LABEL_521:
                v265 = *((_QWORD *)v258 + 7);
                if ( v265 )
                {
                  if ( !v264 )
                  {
                    while ( !FTCache::TDO_ENTRY::Excludes(
                               (FTCache::TDO_ENTRY *)v263[6],
                               *(const struct _UNICODE_STRING **)(v265 + 64)) )
                    {
                      v265 = *(_QWORD *)(v265 + 56);
                      if ( !v265 )
                      {
                        v266 = v262 - 2;
                        v267 = WPP_GLOBAL_Control;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                          goto LABEL_535;
                        v268 = 124;
                        goto LABEL_534;
                      }
                    }
                  }
                }
                else if ( v264 )
                {
                  while ( !FTCache::TDO_ENTRY::Excludes(
                             *((FTCache::TDO_ENTRY **)v258 + 6),
                             *(const struct _UNICODE_STRING **)(v264 + 64)) )
                  {
                    v264 = *(_QWORD *)(v264 + 56);
                    if ( !v264 )
                    {
                      v266 = v262 - 2;
                      v267 = WPP_GLOBAL_Control;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                        goto LABEL_535;
                      v268 = 123;
                      goto LABEL_534;
                    }
                  }
                }
                else
                {
                  v266 = v262 - 2;
                  v267 = WPP_GLOBAL_Control;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    v268 = 122;
LABEL_534:
                    WPP_SF_qq(v267[2], v268, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v258, v262 - 2);
                  }
LABEL_535:
                  if ( (*((_QWORD *)v258 + 7) || v263[7])
                    && (*(_BYTE *)(*((_QWORD *)v258 + 6) + 92LL) || *(_BYTE *)(v263[6] + 92LL)) )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_qq(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        125,
                        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
                        v258,
                        v262 - 2);
                  }
                  else if ( v266 )
                  {
                    for ( jj = v258; *((_QWORD *)jj + 7); jj = (char *)*((_QWORD *)jj + 7) )
                      ;
                    while ( v263[7] )
                      v263 = (_QWORD *)v263[7];
                    v270 = FTCache::AddConflictPair(
                             a8,
                             a9,
                             ForestTrustTopLevelName,
                             jj,
                             4u,
                             ForestTrustTopLevelName,
                             v263,
                             4u);
                    v24 = v270;
                    if ( v270 < 0 )
                    {
                      v274 = WPP_GLOBAL_Control;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        v275 = 126;
                        goto LABEL_557;
                      }
                      goto LABEL_259;
                    }
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, 0, jj, *((_DWORD *)jj + 11), v263);
                  }
                }
              }
            }
            v262 = (_QWORD *)*v262;
            v261 = (_QWORD **)(*((_QWORD *)v258 + 8) + 24LL);
            continue;
          }
        }
        if ( FTCache::TLN_ENTRY::Enabled(v260) )
          goto LABEL_513;
      }
LABEL_552:
      v258 = *(char **)v258;
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180022580  push    rbp
0x180022582  push    rbx
0x180022583  push    rsi
0x180022584  push    rdi
0x180022585  push    r12
0x180022587  push    r13
0x180022589  push    r14
0x18002258b  push    r15
0x18002258d  sub     rsp, 0E8h
0x180022594  lea     rbp, [rsp+40h]
0x180022599  mov     rax, cs:__security_cookie
0x1800225a0  xor     rax, rbp
0x1800225a3  mov     [rbp+0E0h+var_50], rax
0x1800225aa  xor     eax, eax
0x1800225ac  mov     rbx, r9
0x1800225af  mov     [rbp+0E0h+var_70], rbx
0x1800225b3  mov     r12, r8
0x1800225b6  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800225ba  mov     rdi, rdx
0x1800225bd  test    rdx, rdx
0x1800225c0  jz      loc_180024C7E
0x1800225c6  test    rbx, rbx
0x1800225c9  jz      loc_180024C7E
0x1800225cf  cmp     [rbp+0E0h+arg_30], rax
0x1800225d6  jz      loc_180024C7E
0x1800225dc  mov     r13, [rbp+0E0h+arg_28]
0x1800225e3  test    r13, r13
0x1800225e6  jz      loc_180024C7E
0x1800225ec  cmp     [rbp+0E0h+arg_38], rax
0x1800225f3  jz      loc_180024C7E
0x1800225f9  cmp     [rbp+0E0h+arg_40], rax
0x180022600  jz      loc_180024C7E
0x180022606  mov     r14, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x18002260d  mov     [rbp+0E0h+var_D8], r14
0x180022611  mov     rcx, cs:WPP_GLOBAL_Control
0x180022618  lea     esi, [rax+8]
0x18002261b  movzx   r15d, [rbp+0E0h+arg_20]
0x180022623  test    [rcx+1Ch], sil
0x180022627  jz      short loc_180022641
0x180022629  mov     eax, [r9]
0x18002262c  mov     r9, rdx
0x18002262f  mov     rcx, [rcx+10h]
0x180022633  mov     [rsp+120h+var_F8], r15d
0x180022638  mov     [rsp+120h+var_100], eax
0x18002263c  call    WPP_SF_Zdl
0x180022641  xor     edx, edx; Val
0x180022643  mov     rcx, r13; void *
0x180022646  lea     r8d, [rdx+60h]; Size
0x18002264a  call    memset_0
0x18002264f  mov     rax, [rbp+0E0h+arg_38]
0x180022656  xor     ecx, ecx
0x180022658  mov     [rax], rcx
0x18002265b  mov     rax, [rbp+0E0h+arg_40]
0x180022662  mov     [rax], ecx
0x180022664  mov     rcx, rbx; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x180022667  call    ?LsaDbLogFTInfo2@@YAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbLogFTInfo2(_LSA_FOREST_TRUST_INFORMATION2 *)
0x18002266c  lea     rcx, [r14+8]; Table
0x180022670  mov     rdx, rdi; Buffer
0x180022673  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180022679  xor     edx, edx
0x18002267b  mov     [rbp+0E0h+var_D0], rax
0x18002267f  mov     r13, rax
0x180022682  test    rax, rax
0x180022685  jnz     loc_1800227EC
0x18002268b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022692  test    [rcx+1Ch], sil
0x180022696  jz      short loc_1800226B0
0x180022698  mov     rcx, [rcx+10h]
0x18002269c  lea     edx, [rax+4Bh]
0x18002269f  mov     r9, rdi
0x1800226a2  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800226a9  call    WPP_SF_Z
0x1800226ae  xor     edx, edx
0x1800226b0  movzx   r13d, word ptr [rdi]
0x1800226b4  mov     rbx, rdx
0x1800226b7  add     r13d, 62h ; 'b'
0x1800226bb  mov     r14d, r13d
0x1800226be  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800226c5  ja      short loc_18002271F
0x1800226c7  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800226ce  add     rcx, rsi
0x1800226d1  add     rcx, r14
0x1800226d4  cmp     rcx, r14
0x1800226d7  jb      short loc_18002271F
0x1800226d9  call    VerifyStackAvailable
0x1800226de  xor     edx, edx
0x1800226e0  test    eax, eax
0x1800226e2  jz      short loc_18002271F
0x1800226e4  lea     rax, [r13+8]
0x1800226e8  lea     rcx, [rax+0Fh]
0x1800226ec  cmp     rcx, rax
0x1800226ef  ja      short loc_1800226FB
0x1800226f1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800226fb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800226ff  mov     rax, rcx
0x180022702  call    _alloca_probe
0x180022707  sub     rsp, rcx
0x18002270a  lea     rbx, [rsp+120h+var_E0]
0x18002270f  test    rbx, rbx
0x180022712  jz      short loc_18002271F
0x180022714  mov     dword ptr [rbx], 6B637453h
0x18002271a  add     rbx, rsi
0x18002271d  jnz     short loc_180022778
0x18002271f  lea     rcx, [r13+8]
0x180022723  cmp     rcx, r14
0x180022726  jb      short loc_180022747
0x180022728  mov     rax, cs:g_pfnAllocate
0x18002272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022734  xor     edx, edx
0x180022736  mov     rbx, rax
0x180022739  test    rax, rax
0x18002273c  jz      short loc_18002274C
0x18002273e  mov     dword ptr [rax], 70616548h
0x180022744  add     rbx, rsi
0x180022747  test    rbx, rbx
0x18002274a  jnz     short loc_180022778
0x18002274c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022753  test    [rcx+1Ch], sil
0x180022757  jz      short loc_18002276E
0x180022759  mov     edx, 4Ch ; 'L'
0x18002275e  mov     rcx, [rcx+10h]
0x180022762  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180022769  call    WPP_SF_
0x18002276e  mov     ebx, 0C000009Ah
0x180022773  jmp     loc_18002368F
0x180022778  mov     [rbx+58h], edx
0x18002277b  lea     r8, [rbx+5Eh]; unsigned __int16 *
0x18002277f  mov     [rbx+10h], rdx
0x180022783  mov     rcx, rbx; DestinationString
0x180022786  mov     rdx, rdi; SourceString
0x180022789  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002278e  mov     rcx, [rbp+0E0h+var_D8]
0x180022792  xor     r9d, r9d; NewElement
0x180022795  add     rcx, rsi; Table
0x180022798  mov     r8d, r13d; BufferSize
0x18002279b  mov     rdx, rbx; Buffer
0x18002279e  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800227a4  lea     rcx, [rbx-8]
0x1800227a8  mov     [rbp+0E0h+var_D0], rax
0x1800227ac  cmp     dword ptr [rcx], 70616548h
0x1800227b2  mov     r13, rax
0x1800227b5  jnz     short loc_1800227C3
0x1800227b7  mov     rax, cs:g_pfnFree
0x1800227be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227c3  xor     edi, edi
0x1800227c5  test    r13, r13
0x1800227c8  jnz     short loc_1800227DC
0x1800227ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227d1  test    [rcx+1Ch], sil
0x1800227d5  jz      short loc_18002276E
0x1800227d7  lea     edx, [rdi+4Dh]
0x1800227da  jmp     short loc_18002275E
0x1800227dc  inc     cs:?sm_TdoEntries@FTCache@@0KA; ulong FTCache::sm_TdoEntries
0x1800227e2  lea     rax, [r13+5Eh]
0x1800227e6  mov     [r13+8], rax
0x1800227ea  jmp     short loc_180022854
0x1800227ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227f3  test    [rcx+1Ch], sil
0x1800227f7  jz      short loc_180022811
0x1800227f9  mov     rcx, [rcx+10h]
0x1800227fd  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180022804  mov     edx, 4Eh ; 'N'
0x180022809  mov     r9, rdi
0x18002280c  call    WPP_SF_Z
0x180022811  cmp     [r13+5Ch], r15b
0x180022815  jz      short loc_180022843
0x180022817  mov     rcx, cs:WPP_GLOBAL_Control
0x18002281e  test    [rcx+1Ch], sil
0x180022822  jz      short loc_180022839
0x180022824  mov     rcx, [rcx+10h]
0x180022828  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002282f  mov     edx, 4Fh ; 'O'
0x180022834  call    WPP_SF_
0x180022839  mov     ebx, 0C000000Dh
0x18002283e  jmp     loc_180023688
0x180022843  mov     rcx, [rbp+0E0h+arg_28]; struct FTCache::TDO_ENTRY *
0x18002284a  mov     rdx, r13; struct FTCache::TDO_ENTRY *
0x18002284d  call    ?CopyTdoEntry@FTCache@@CAXPEAUTDO_ENTRY@1@0@Z; FTCache::CopyTdoEntry(FTCache::TDO_ENTRY *,FTCache::TDO_ENTRY *)
0x180022852  xor     edi, edi
0x180022854  mov     [r13+58h], edi
0x180022858  lea     rax, [r13+38h]
0x18002285c  mov     [rbp+0E0h+var_60], rax
0x180022863  lea     r14, [r13+18h]
0x180022867  mov     [rax+8], rax
0x18002286b  mov     [rax], rax
0x18002286e  lea     rax, [r13+48h]
0x180022872  mov     [r13+5Ch], r15b
0x180022876  lea     r15, [r13+28h]
0x18002287a  mov     [rax+8], rax
0x18002287e  mov     [rax], rax
0x180022881  mov     [rbp+0E0h+var_68], r14
0x180022885  mov     [r14+8], r14
0x180022889  mov     [r14], r14
0x18002288c  mov     [rbp+0E0h+var_58], r15
0x180022893  mov     [r15+8], r15
0x180022897  mov     [r15], r15
0x18002289a  test    r12, r12
0x18002289d  jz      short loc_1800228FA
0x18002289f  mov     rcx, r12; Sid
0x1800228a2  call    cs:__imp_RtlLengthSid
0x1800228a8  mov     edx, eax; uBytes
0x1800228aa  mov     ecx, 40h ; '@'; uFlags
0x1800228af  mov     ebx, eax
0x1800228b1  call    cs:__imp_LocalAlloc
0x1800228b7  mov     [r13+10h], rax
0x1800228bb  test    rax, rax
0x1800228be  jnz     short loc_1800228EA
0x1800228c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228c7  test    [rcx+1Ch], sil
0x1800228cb  jz      short loc_1800228E0
0x1800228cd  lea     edx, [rax+50h]
0x1800228d0  mov     rcx, [rcx+10h]
0x1800228d4  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800228db  call    WPP_SF_
0x1800228e0  mov     ebx, 0C000009Ah
0x1800228e5  jmp     loc_18002366D
0x1800228ea  mov     r8, r12; SourceSid
0x1800228ed  mov     rdx, rax; DestinationSid
0x1800228f0  mov     ecx, ebx; DestinationSidLength
0x1800228f2  call    cs:__imp_RtlCopySid
0x1800228f8  jmp     short loc_1800228FE
0x1800228fa  mov     [r13+10h], rdi
0x1800228fe  lea     rcx, [rbp+0E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022902  mov     ebx, edi
0x180022904  call    cs:__imp_GetSystemTimeAsFileTime
0x18002290a  mov     rax, [rbp+0E0h+var_70]
0x18002290e  xor     r8d, r8d
0x180022911  mov     edi, r8d
0x180022914  mov     [rbp+0E0h+var_C8], r8d
0x180022918  cmp     [rax], r8d
0x18002291b  jbe     loc_180023F00
0x180022921  mov     rax, [rax+8]
0x180022925  mov     ecx, edi
0x180022927  mov     [rbp+0E0h+var_DF], r8b
0x18002292b  mov     r15, [rax+rcx*8]
0x18002292f  mov     [rbp+0E0h+var_B0], r15
0x180022933  mov     r9d, [r15+4]
0x180022937  mov     ecx, r9d
0x18002293a  test    r9d, r9d
0x18002293d  jz      loc_180023A25
0x180022943  sub     ecx, 1
0x180022946  jz      loc_1800237D0
0x18002294c  sub     ecx, 1
0x18002294f  jz      loc_180022F83
0x180022955  sub     ecx, 1
0x180022958  jz      loc_180022EF2
0x18002295e  cmp     ecx, 1
0x180022961  jnz     loc_180023F8C
0x180022967  mov     rdi, [r15+10h]
0x18002296b  mov     [rbp+0E0h+SourceSid], rdi
0x18002296f  cmp     [r15+28h], r8w
0x180022974  jbe     short loc_18002297F
0x180022976  mov     r14b, cl
0x180022979  cmp     [r15+30h], r8
0x18002297d  jnz     short loc_180022982
0x18002297f  mov     r14b, r8b
0x180022982  mov     [rbp+0E0h+var_E0], r14b
0x180022986  mov     dword ptr [rbp+0E0h+uBytes], r8d
0x18002298a  test    rdi, rdi
0x18002298d  jz      short loc_1800229AC
0x18002298f  mov     rcx, rdi; Sid
0x180022992  call    cs:__imp_RtlValidSid
0x180022998  test    al, al
0x18002299a  jz      loc_180023F08
0x1800229a0  mov     rcx, rdi; Sid
0x1800229a3  call    cs:__imp_RtlLengthSid
0x1800229a9  mov     dword ptr [rbp+0E0h+uBytes], eax
0x1800229ac  mov     r12, [rbp+0E0h+var_D8]
0x1800229b0  lea     rdx, [r15+18h]; Buffer
0x1800229b4  mov     rdi, r15
0x1800229b7  lea     rcx, [r12+210h]; Table
0x1800229bf  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800229c5  xor     r9d, r9d
0x1800229c8  mov     r13, rax
0x1800229cb  test    r14b, r14b
0x1800229ce  jz      short loc_1800229EA
0x1800229d0  lea     rcx, [r12+278h]; Table
0x1800229d8  lea     rdx, [r15+28h]; Buffer
0x1800229dc  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800229e2  mov     r15, rax
0x1800229e5  xor     r9d, r9d
0x1800229e8  jmp     short loc_1800229ED
0x1800229ea  mov     r15, r9
0x1800229ed  test    r13, r13
0x1800229f0  jnz     loc_180022C05
0x1800229f6  movzx   r12d, word ptr [rdi+18h]
0x1800229fb  mov     rdi, r9
0x1800229fe  add     r12d, 2Ah ; '*'
0x180022a02  mov     r14d, r12d
0x180022a05  cmp     r14, cs:g_ulMaxStackAllocSize
0x180022a0c  ja      short loc_180022A68
0x180022a0e  mov     rcx, cs:g_ulAdditionalProbeSize
0x180022a15  add     rcx, rsi
0x180022a18  add     rcx, r14
0x180022a1b  cmp     rcx, r14
0x180022a1e  jb      short loc_180022A68
0x180022a20  call    VerifyStackAvailable
0x180022a25  xor     r9d, r9d
0x180022a28  test    eax, eax
0x180022a2a  jz      short loc_180022A68
  ... truncated ...
```
