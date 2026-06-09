# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(PPID const &,ulong,_MP_KNOWN_PROCESS_TYPE,wchar_t const *,bool,wchar_t const *,wchar_t const *,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo const &,DlpAppGroupInfo const &,bool,EndpointDlp::Client::ExtendedAttributes const &,bool)

- ea: `0x180034800`
- end: `0x180036c15`
- name: `?AddFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@KW4_MP_KNOWN_PROCESS_TYPE@@PEB_W_N22AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KKPEAUDlpAction@@AEBUMpDlpPolicyTraceInfo@3@AEBUDlpAppGroupInfo@@3AEBUExtendedAttributes@Client@EndpointDlp@@3@Z`
- size: `9237`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, char, __int64, __int64, __int64, int, int, __int64, __int64, __int64, char, __int64, char)`
- caller_count: `1`
- callee_count: `84`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032970`

## callees

- `0x18001c6ac`
- `0x18001d980`
- `0x180020180`
- `0x180020288`
- `0x18002082c`
- `0x1800210c4`
- `0x180024ac0`
- `0x180028a10`
- `0x180028d80`
- `0x18002a3a0`
- `0x18002bda4`
- `0x18002c990`
- `0x18002cc9c`
- `0x18002d71c`
- `0x18002d7f4`
- `0x18002da48`
- `0x18002e760`
- `0x18002e9f0`
- `0x1800318b0`
- `0x1800330a8`
- `0x180034420`
- `0x180034770`
- `0x180034800`
- `0x1800376e0`
- `0x180037754`
- `0x180037afc`
- `0x1800399c0`
- `0x18003a074`
- `0x180041368`
- `0x180041b98`
- `0x180041e58`
- `0x180042c6c`
- `0x180042d98`
- `0x18004b3bc`
- `0x18004bc88`
- `0x18004c028`
- `0x18004c04c`
- `0x18004d26c`
- `0x18004d480`
- `0x18004e000`
- `0x1800553b4`
- `0x18005da68`
- `0x18006ad2c`
- `0x18006b2fc`
- `0x18006b350`
- `0x18006b4c8`
- `0x18006b500`
- `0x18006bb8c`
- `0x18006c3c0`
- `0x18006c458`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180034ce4`
- `KERNEL32!CompareStringOrdinal` at `0x1800350d9`
- `KERNEL32!CompareStringOrdinal` at `0x180034ce4`
- `KERNEL32!CompareStringOrdinal` at `0x1800350d9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180034b7f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180034b7f`
- `KERNEL32!CompareFileTime` at `0x180034a99`
- `KERNEL32!CompareFileTime` at `0x180034a99`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(
        _QWORD *a1,
        __int64 a2,
        int a3,
        int a4,
        _WORD *Src,
        char a6,
        wchar_t *a7,
        std::_Ref_count_base *a8,
        struct RealtimeProtection::FileUniqueId *a9,
        int a10,
        unsigned int a11,
        __int64 a12,
        void *a13,
        void *a14,
        char a15,
        __int64 a16,
        char a17)
{
  FILETIME *v17; // r8
  _QWORD *v18; // r9
  char v19; // cl
  FILETIME v20; // xmm6_8
  float *v21; // r13
  __int64 v22; // rdi
  unsigned __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // r15
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbx
  float *v30; // r14
  __int64 v31; // r12
  __int64 v32; // rax
  __int64 v33; // rcx
  FILETIME *v34; // r13
  FILETIME v35; // r15
  FILETIME *v36; // rbx
  FILETIME *v37; // rcx
  FILETIME *v38; // r15
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // r14
  FILETIME *v41; // r12
  size_t v42; // rbx
  bool *v43; // r9
  wchar_t *v44; // r12
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rsi
  __int64 v47; // rcx
  WCHAR *v48; // r14
  size_t v49; // rbx
  LPCWCH *v50; // rdx
  float *v51; // r14
  __int64 v52; // rcx
  __int64 v53; // rsi
  __int64 v54; // rax
  FILETIME v55; // rcx
  _QWORD *inserted; // r13
  _QWORD *v57; // rbx
  _QWORD *v58; // rbx
  const WCHAR *v59; // r8
  const WCHAR *v60; // rcx
  unsigned __int64 v61; // r13
  __int64 v62; // rcx
  __int64 v63; // rcx
  char *v64; // r12
  size_t v65; // rbx
  size_t v66; // rbx
  char *v67; // r13
  __int64 v68; // rdx
  float v69; // xmm0_4
  __int64 v70; // rcx
  float v71; // xmm1_4
  __int64 v72; // rsi
  LPCWCH *v73; // r14
  unsigned __int64 v74; // rbx
  __int64 v75; // rcx
  unsigned __int64 v76; // r9
  void **v77; // rsi
  void **v78; // r10
  void **v79; // rcx
  void **v80; // r14
  void **v81; // rbx
  void **v82; // rdx
  unsigned __int64 i; // rcx
  const struct std::nothrow_t *v84; // rdx
  __int64 v85; // rcx
  char *v86; // rsi
  char *v87; // rbx
  char *v88; // rbx
  const WCHAR *v89; // r8
  const WCHAR *v90; // rcx
  __int64 v91; // rdx
  _QWORD *v92; // rdx
  __int64 v93; // rax
  __int64 v94; // rcx
  char *v95; // r8
  void **v96; // rbx
  unsigned __int64 v97; // rdx
  const struct std::nothrow_t *v98; // rdx
  void *v99; // rcx
  int v100; // eax
  std::_Ref_count_base *v101; // rdx
  char *v102; // rcx
  struct RealtimeProtection::FileUniqueId *v103; // r13
  char *v104; // rbx
  __int64 Instance; // rax
  __int64 v106; // r10
  __m128i v107; // xmm6
  volatile signed __int32 *v108; // rbx
  std::_Ref_count_base *v109; // r15
  std::_Ref_count_base *v110; // rdi
  __int64 v111; // r14
  unsigned __int64 v112; // xmm0_8
  int v113; // r15d
  __int64 v114; // r9
  FILETIME *v115; // r14
  PVOID *v116; // rcx
  char v117; // bl
  _DWORD *v118; // rdx
  __int64 v119; // r8
  _WORD **v120; // r9
  _WORD *v121; // rax
  _QWORD *v122; // r14
  _QWORD *v123; // rdi
  unsigned __int64 v124; // rbx
  unsigned __int64 v125; // r15
  char *v126; // r12
  size_t v127; // rbx
  _QWORD *v128; // rdi
  void *v129; // r12
  unsigned __int64 v130; // rbx
  unsigned __int64 v131; // r14
  char *v132; // r15
  size_t v133; // rbx
  _QWORD *v134; // rdi
  unsigned __int64 v135; // rbx
  char *v136; // r12
  unsigned __int64 v137; // r14
  char *v138; // r15
  size_t v139; // rbx
  _WORD *v140; // rdi
  _QWORD *v141; // r14
  unsigned __int64 v142; // rbx
  unsigned __int64 v143; // r15
  char *v144; // r12
  size_t v145; // rbx
  char *v146; // rdi
  _QWORD *v147; // r14
  unsigned __int64 v148; // rbx
  unsigned __int64 v149; // r15
  char *v150; // r12
  size_t v151; // rbx
  __int64 v152; // rcx
  volatile signed __int32 *v153; // rbx
  char v154; // di
  char v155; // al
  __m128i v156; // xmm0
  FILETIME *v157; // rdi
  bool v158; // al
  void *v159; // rdx
  WCHAR *v160; // rcx
  void *v161; // rdx
  WCHAR *v162; // rcx
  unsigned int v163; // edi
  unsigned __int64 v165; // r13
  unsigned __int64 v166; // rcx
  __int64 v167; // rcx
  char *v168; // r12
  size_t v169; // rbx
  unsigned __int64 v170; // r13
  unsigned __int64 v171; // rcx
  __int64 v172; // rcx
  char *v173; // r15
  size_t v174; // rbx
  unsigned __int64 v175; // r13
  unsigned __int64 v176; // rcx
  __int64 v177; // rcx
  char *v178; // r15
  size_t v179; // rbx
  unsigned __int64 v180; // r13
  unsigned __int64 v181; // rcx
  __int64 v182; // rcx
  char *v183; // r12
  size_t v184; // rbx
  __int64 v185; // r13
  __int64 v186; // rdx
  __int64 v187; // rcx
  char *v188; // r12
  size_t v189; // rbx
  const struct std::nothrow_t *v190; // rdx
  void *v191; // rcx
  char v192; // al
  char *v193; // rbx
  __int64 v194; // rax
  char *v195; // rbx
  __int64 v196; // rax
  __int64 updated; // rax
  std::_Ref_count_base *v198; // rbx
  __int64 v199; // rdi
  int Ea; // edi
  __int64 v201; // r10
  __m128i v202; // xmm6
  __m128i v203; // xmm7
  std::_Ref_count_base *v204; // rbx
  __int64 v205; // r14
  unsigned __int64 v206; // xmm0_8
  volatile signed __int32 *v207; // xmm0_8
  int v208; // r15d
  __int64 v209; // r9
  char *v210; // rcx
  char *v211; // rbx
  __int64 v212; // rax
  _QWORD *v213; // rdi
  __int64 v214; // rax
  _QWORD *v215; // rax
  __int64 v216; // rax
  const struct RealtimeProtection::FileUniqueId *v217; // rax
  int v218; // eax
  FILETIME *v219; // rax
  FILETIME *v220; // r13
  FILETIME *v221; // rcx
  __int64 v222; // rdx
  float v223; // xmm0_4
  __int64 v224; // rcx
  float v225; // xmm1_4
  FILETIME **v226; // rdx
  __int64 v227; // rax
  __int64 v228; // rcx
  __int64 v229; // r8
  __int64 v230; // rax
  _QWORD *v231; // r13
  __int64 v232; // r12
  __int64 v233; // rdx
  __int64 v234; // rcx
  __int64 v235; // rax
  __int64 v236; // r10
  __int64 v237; // r10
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 size_of; // rax
  __int64 v241; // rdx
  float v242; // xmm0_4
  __int64 v243; // rcx
  float v244; // xmm1_4
  __int64 *v245; // rdx
  __int64 v246; // rax
  __int64 v247; // rcx
  __int64 v248; // r8
  __int64 v249; // rax
  __int64 v250; // rdx
  __int64 v251; // rdx
  __int64 v252; // rax
  __int64 v253; // rax
  int v254; // eax
  __int64 v255; // rax
  __int64 v256; // r8
  __int64 v257; // r10
  __int64 v258; // rax
  int v259; // eax
  _QWORD *v260; // rcx
  __int64 v261; // rdx
  int RmsLabelInfo; // eax
  unsigned int j; // r9d
  int v264; // r9d
  _QWORD *v265; // rbx
  __int64 v266; // rax
  unsigned int v267; // [rsp+30h] [rbp-1F8h]
  unsigned __int64 v268; // [rsp+38h] [rbp-1F0h] BYREF
  std::_Ref_count_base *v269[2]; // [rsp+40h] [rbp-1E8h] BYREF
  FILETIME *v270; // [rsp+50h] [rbp-1D8h]
  void *v271; // [rsp+58h] [rbp-1D0h] BYREF
  void *v272; // [rsp+60h] [rbp-1C8h] BYREF
  FILETIME *lpFileTime1; // [rsp+68h] [rbp-1C0h]
  _QWORD *v274; // [rsp+70h] [rbp-1B8h]
  __int64 v275; // [rsp+78h] [rbp-1B0h]
  int v276; // [rsp+80h] [rbp-1A8h]
  struct RealtimeProtection::FileUniqueId *v277; // [rsp+88h] [rbp-1A0h] BYREF
  __m128i v278; // [rsp+90h] [rbp-198h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-188h]
  __int64 v280; // [rsp+A8h] [rbp-180h]
  wchar_t v281; // [rsp+B8h] [rbp-170h] BYREF
  void *v282[2]; // [rsp+C0h] [rbp-168h] BYREF
  __m128i v283; // [rsp+D0h] [rbp-158h] BYREF
  LPCWCH v284[2]; // [rsp+F0h] [rbp-138h] BYREF
  __m128i v285; // [rsp+100h] [rbp-128h]
  void *v286[2]; // [rsp+110h] [rbp-118h] BYREF
  __m128i si128; // [rsp+120h] [rbp-108h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+130h] [rbp-F8h] BYREF
  LPCWCH lpString1[2]; // [rsp+138h] [rbp-F0h] BYREF
  __m128i v290; // [rsp+148h] [rbp-E0h]
  void *v291; // [rsp+158h] [rbp-D0h] BYREF
  char v292[8]; // [rsp+160h] [rbp-C8h] BYREF
  __m128i v293; // [rsp+168h] [rbp-C0h]
  __int128 v294; // [rsp+178h] [rbp-B0h] BYREF
  __m128i v295; // [rsp+188h] [rbp-A0h]
  char v296; // [rsp+198h] [rbp-90h]
  _BYTE v297[32]; // [rsp+1A0h] [rbp-88h] BYREF
  char v298; // [rsp+1C0h] [rbp-68h]

  v276 = a4;
  LODWORD(v268) = a3;
  v17 = (FILETIME *)a2;
  lpFileTime1 = (FILETIME *)a2;
  v18 = a1;
  v274 = a1;
  v271 = a13;
  String1 = a7;
  v269[0] = a8;
  v277 = a9;
  v280 = a12;
  v272 = a14;
  v278.m128i_i64[0] = a16;
  v19 = *(_BYTE *)(a16 + 64);
  if ( v19 && (v267 = *(_DWORD *)(a16 + 48)) != 0 || (v267 = 0, v19) && *(_DWORD *)(a16 + 48) )
    v275 = *(_QWORD *)(a16 + 56);
  else
    v275 = 0;
  v20 = *(FILETIME *)a2;
  LODWORD(v282[0]) = *(_DWORD *)(a2 + 8);
  v21 = (float *)(v18 + 17);
  _mm_lfence();
  v22 = 0xCBF29CE484222325uLL;
  v23 = 0x100000001B3LL
      * (*(unsigned __int8 *)(a2 + 11)
       ^ (0x100000001B3LL
        * (*(unsigned __int8 *)(a2 + 10)
         ^ (0x100000001B3LL
          * (*(unsigned __int8 *)(a2 + 9) ^ (0x100000001B3LL * (*(unsigned __int8 *)(a2 + 8) ^ 0xCBF29CE484222325uLL)))))));
  v24 = v18[20];
  v25 = *(_QWORD *)(v24 + 16 * (v23 & v18[23]) + 8);
  v26 = v18[18];
  if ( v25 == v26 )
  {
LABEL_389:
    if ( v18[19] == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v283.m128i_i64[0] = (__int64)(v18 + 18);
    size_of = std::_Get_size_of_n<32>(1);
    v25 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v283.m128i_i64[1] = v25;
    *(_DWORD *)(v25 + 16) = lpFileTime1[1].dwLowDateTime;
    *(_QWORD *)(v25 + 20) = 0;
    *(_DWORD *)(v25 + 28) = 0;
    v18 = v274;
    v241 = v274[19] + 1LL;
    if ( v241 < 0 )
      v242 = (float)(v241 & 1 | (unsigned int)((unsigned __int64)v241 >> 1))
           + (float)(v241 & 1 | (unsigned int)((unsigned __int64)v241 >> 1));
    else
      v242 = (float)(int)v241;
    v243 = *((_QWORD *)v21 + 7);
    if ( v243 < 0 )
    {
      v249 = *((_QWORD *)v21 + 7) & 1LL | ((unsigned __int64)v243 >> 1);
      v244 = (float)(int)v249 + (float)(int)v249;
    }
    else
    {
      v244 = (float)(int)v243;
    }
    if ( (float)(v242 / v244) > *v21 )
    {
      v250 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(v21);
      std::_Hash<std::_Umap_traits<unsigned int,std::wstring,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Forced_rehash(
        v21,
        v250);
      v26 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,PPID,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,PPID>>,0>>::_Find_last<unsigned long>(
                         v21,
                         &v283,
                         v25 + 16,
                         v23);
      v18 = v274;
    }
    v245 = *(__int64 **)(v26 + 8);
    ++v18[19];
    *(_QWORD *)v25 = v26;
    *(_QWORD *)(v25 + 8) = v245;
    *v245 = v25;
    *(_QWORD *)(v26 + 8) = v25;
    v246 = 2 * (v23 & *((_QWORD *)v21 + 6));
    v247 = *((_QWORD *)v21 + 3);
    v248 = *(_QWORD *)(v247 + 16 * (v23 & *((_QWORD *)v21 + 6)));
    if ( v248 == *((_QWORD *)v21 + 1) )
    {
      *(_QWORD *)(v247 + 16 * (v23 & *((_QWORD *)v21 + 6))) = v25;
    }
    else
    {
      if ( v248 == v26 )
      {
        *(_QWORD *)(v247 + 16 * (v23 & *((_QWORD *)v21 + 6))) = v25;
        goto LABEL_11;
      }
      if ( *(__int64 **)(v247 + 16 * (v23 & *((_QWORD *)v21 + 6)) + 8) != v245 )
        goto LABEL_11;
    }
    *(_QWORD *)(v247 + 8 * v246 + 8) = v25;
LABEL_11:
    v17 = lpFileTime1;
    goto LABEL_12;
  }
  v27 = *(_QWORD *)(v24 + 16 * (v23 & v18[23]));
  while ( *(_DWORD *)(a2 + 8) != *(_DWORD *)(v25 + 16) )
  {
    if ( v25 == v27 )
    {
      v26 = v25;
      goto LABEL_389;
    }
    v25 = *(_QWORD *)(v25 + 8);
  }
LABEL_12:
  *(FILETIME *)(v25 + 20) = v20;
  *(_DWORD *)(v25 + 28) = v282[0];
  _mm_lfence();
  v28 = v18[36];
  v29 = *(_QWORD *)(v28
                  + 16
                  * (v18[39]
                   & (0x100000001B3LL
                    * (HIBYTE(v17[1].dwLowDateTime)
                     ^ (0x100000001B3LL
                      * (BYTE2(v17[1].dwLowDateTime)
                       ^ (0x100000001B3LL
                        * (BYTE1(v17[1].dwLowDateTime)
                         ^ (0x100000001B3LL * (LOBYTE(v17[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))))
                  + 8);
  if ( v29 == v18[34] )
  {
LABEL_13:
    v29 = 0;
  }
  else
  {
    while ( v17[1].dwLowDateTime != *(_DWORD *)(v29 + 16) )
    {
      if ( v29 == *(_QWORD *)(v28
                            + 16
                            * (v18[39]
                             & (0x100000001B3LL
                              * (HIBYTE(v17[1].dwLowDateTime)
                               ^ (0x100000001B3LL
                                * (BYTE2(v17[1].dwLowDateTime)
                                 ^ (0x100000001B3LL
                                  * (BYTE1(v17[1].dwLowDateTime)
                                   ^ (0x100000001B3LL * (LOBYTE(v17[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))))) )
        goto LABEL_13;
      v29 = *(_QWORD *)(v29 + 8);
    }
  }
  if ( v29
    && v29 != v18[34]
    && (*(_DWORD *)(v29 + 32) != v17->dwHighDateTime || *(_DWORD *)(v29 + 28) != v17->dwLowDateTime) )
  {
    v231 = v18 + 25;
    v232 = std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(
             2
           * (v18[39]
            & (0x100000001B3LL
             * (HIBYTE(v17[1].dwLowDateTime)
              ^ (0x100000001B3LL
               * (BYTE2(v17[1].dwLowDateTime)
                ^ (0x100000001B3LL
                 * (BYTE1(v17[1].dwLowDateTime)
                  ^ (0x100000001B3LL * (LOBYTE(v17[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL))))))))),
             v29 + 28);
    v233 = *(_QWORD *)(std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                         v231,
                         &v283,
                         v29 + 28,
                         v232)
                     + 8);
    if ( v233 )
    {
      std::_Hash<std::_Umap_traits<unsigned long,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>>>,0>>::_Erase_bucket(
        v231,
        v233,
        v232 & v231[6]);
      std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(v231 + 1);
    }
    v235 = std::_Uhash_compare<enum DlpActionType,std::hash<enum DlpActionType>,std::equal_to<enum DlpActionType>>::operator()<enum DlpActionType>(
             v234,
             v29 + 16);
    std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(
      v236 + 264,
      v29,
      *(_QWORD *)(v236 + 312) & v235);
    std::list<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(v237 + 272);
    v18 = v274;
  }
  v30 = (float *)(v18 + 25);
  LODWORD(v282[0]) = 0;
  MpHashCrc32(v282, 12);
  v31 = LODWORD(v282[0]);
  v32 = 2 * (LODWORD(v282[0]) & *((_QWORD *)v30 + 6));
  v33 = *((_QWORD *)v30 + 3);
  v34 = *(FILETIME **)(v33 + 16 * (LODWORD(v282[0]) & *((_QWORD *)v30 + 6)) + 8);
  v270 = v34;
  v35 = (FILETIME)*((_QWORD *)v30 + 1);
  if ( v34 != *(FILETIME **)&v35 )
  {
    v36 = *(FILETIME **)(v33 + 8 * v32);
    v37 = lpFileTime1;
    while ( 1 )
    {
      if ( v37[1].dwLowDateTime == v34[3].dwLowDateTime )
      {
        if ( !CompareFileTime(v37, v34 + 2) )
          goto LABEL_24;
        v37 = lpFileTime1;
      }
      if ( v34 == v36 )
        break;
      v34 = (FILETIME *)v34[1];
      v270 = v34;
    }
    v35 = (FILETIME)v34;
  }
  if ( v274[27] == 0x41041041041041LL )
    std::_Xlength_error("unordered_map/set too long");
  v283 = (__m128i)(unsigned __int64)(v30 + 2);
  v219 = (FILETIME *)operator new(0x3F0u);
  v270 = v219;
  v283.m128i_i64[1] = (__int64)v219;
  v220 = v219 + 2;
  v221 = lpFileTime1;
  v219[2] = *lpFileTime1;
  v219[3].dwLowDateTime = v221[1].dwLowDateTime;
  memset(&v219[4], 0, 0x3D0u);
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor::ProcessEnforcementDescriptor((RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *)&v220[2]);
  v222 = v274[27] + 1LL;
  if ( v222 < 0 )
    v223 = (float)(v222 & 1 | (unsigned int)((unsigned __int64)v222 >> 1))
         + (float)(v222 & 1 | (unsigned int)((unsigned __int64)v222 >> 1));
  else
    v223 = (float)(int)v222;
  v224 = *((_QWORD *)v30 + 7);
  if ( v224 < 0 )
  {
    v238 = *((_QWORD *)v30 + 7) & 1LL | ((unsigned __int64)v224 >> 1);
    v225 = (float)(int)v238 + (float)(int)v238;
  }
  else
  {
    v225 = (float)(int)v224;
  }
  if ( (float)(v223 / v225) > *v30 )
  {
    v251 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(v30);
    std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo>>,0>>::_Forced_rehash(
      v30,
      v251);
    v35 = *(FILETIME *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                         v30,
                         &v283,
                         v220,
                         v31);
  }
  v226 = *(FILETIME ***)(*(_QWORD *)&v35 + 8LL);
  ++v274[27];
  v34 = v270;
  *v270 = v35;
  v34[1] = (FILETIME)v226;
  *v226 = v34;
  *(_QWORD *)(*(_QWORD *)&v35 + 8LL) = v34;
  v227 = 2 * (v31 & *((_QWORD *)v30 + 6));
  v228 = *((_QWORD *)v30 + 3);
  v229 = *(_QWORD *)(v228 + 16 * (v31 & *((_QWORD *)v30 + 6)));
  if ( v229 == *((_QWORD *)v30 + 1) )
  {
    *(_QWORD *)(v228 + 16 * (v31 & *((_QWORD *)v30 + 6))) = v34;
LABEL_341:
    *(_QWORD *)(v228 + 8 * v227 + 8) = v34;
    goto LABEL_24;
  }
  if ( v229 == v35 )
  {
    *(_QWORD *)(v228 + 16 * (v31 & *((_QWORD *)v30 + 6))) = v34;
  }
  else if ( *(FILETIME ***)(v228 + 16 * (v31 & *((_QWORD *)v30 + 6)) + 8) == v226 )
  {
    goto LABEL_341;
  }
LABEL_24:
  v38 = v34 + 12;
  v39 = -1;
  do
    ++v39;
  while ( Src[v39] );
  v40 = (unsigned __int64)v34[15];
  if ( v39 > v40 )
  {
    if ( v39 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    v61 = v39 | 7;
    if ( (v39 | 7) > 0x7FFFFFFFFFFFFFFELL || (v62 = v40 >> 1, v40 > 0x7FFFFFFFFFFFFFFELL - (v40 >> 1)) )
    {
      v61 = 0x7FFFFFFFFFFFFFFELL;
      v63 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      if ( v61 < v62 + v40 )
        v61 = v62 + v40;
      v63 = v61 + 1;
      if ( v61 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v64 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v63);
    _mm_lfence();
    v38[2] = (FILETIME)v39;
    v38[3] = (FILETIME)v61;
    v65 = 2 * v39;
    memmove(v64, Src, v65);
    *(_WORD *)&v64[v65] = 0;
    if ( v40 > 7 )
    {
      _mm_lfence();
      ((void (__fastcall *)(_QWORD, _QWORD))std::_Deallocate<16>)(*v38, 2 * v40 + 2);
    }
    v34 = v270;
    *v38 = (FILETIME)v64;
  }
  else
  {
    _mm_lfence();
    v41 = v34 + 12;
    if ( v40 > 7 )
      v41 = (FILETIME *)*v38;
    v34[14] = (FILETIME)v39;
    v42 = 2 * v39;
    memmove(v41, Src, v42);
    *(_WORD *)((char *)&v41->dwLowDateTime + v42) = 0;
  }
  LOBYTE(v34[21].dwHighDateTime) = a6;
  v34[20].dwLowDateTime = v276;
  BYTE4(v268) = 1;
  *(_QWORD *)&v34[20].dwHighDateTime = v268;
  LOBYTE(v281) = 0;
  v44 = String1;
  CommonUtil::UtilIsNetworkPath(String1, &v281, 0, v43);
  if ( (_BYTE)v281 )
    LOBYTE(v34[83].dwLowDateTime) = 1;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_OWORD *)v284 = 0;
  v285 = 0;
  v45 = -1;
  do
    ++v45;
  while ( v44[v45] );
  if ( v45 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v45 <= 7 )
  {
    _mm_lfence();
    v285.m128i_i64[0] = v45;
    v285.m128i_i64[1] = 7;
    v66 = 2 * v45;
    memmove(v284, v44, v66);
    *(_WORD *)((char *)v284 + v66) = 0;
  }
  else
  {
    v46 = v45 | 7;
    if ( (v45 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v46 = 0x7FFFFFFFFFFFFFFELL;
      v47 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      if ( v46 < 0xA )
        v46 = 10;
      v47 = v46 + 1;
      if ( v46 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v48 = (WCHAR *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v47);
    _mm_lfence();
    v284[0] = v48;
    v285.m128i_i64[0] = v45;
    v285.m128i_i64[1] = v46;
    v49 = v45;
    memmove(v48, v44, v49 * 2);
    v48[v49] = 0;
  }
  v50 = v284;
  if ( v285.m128i_i64[1] > 7uLL )
    v50 = (LPCWCH *)v284[0];
  RealtimeProtection::DlpUtils::GetFileExtensions(lpString1, v50);
  v51 = (float *)&v34[22];
  v53 = std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(
          v52,
          lpString1);
  v54 = 2 * (v53 & *(_QWORD *)&v34[28]);
  v55 = v34[25];
  inserted = *(_QWORD **)(*(_QWORD *)&v55 + 16 * (v53 & *(_QWORD *)&v34[28]) + 8);
  v57 = (_QWORD *)v270[23];
  if ( inserted == v57 )
  {
LABEL_64:
    if ( *(_QWORD *)&v270[24] == 0x249249249249249LL )
      std::_Xlength_error("unordered_map/set too long");
    v283 = (__m128i)(unsigned __int64)&v270[23];
    v67 = (char *)operator new(0x70u);
    v283.m128i_i64[1] = (__int64)v67;
    v268 = (unsigned __int64)lpString1;
    ____0V__tuple_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___std__V__tuple___V_1__0A___Z_S___pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__unordered_map_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UFileEnforcementDescriptor_DlpProcessStateCache_DlpProcessCache_RealtimeProtection__UCaseInsensitiveHasher_DlpUtils_6_UCStrOrdinalCompEqual_86_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UFileEnforcementDescriptor_DlpProcessStateCache_DlpProcessCache_RealtimeProtection___std___2__2__std__AEAA_AEAV__tuple_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v67 + 16,
      &v268);
    v68 = *(_QWORD *)&v270[24] + 1LL;
    if ( v68 < 0 )
      v69 = (float)(v68 & 1 | (unsigned int)((unsigned __int64)v68 >> 1))
          + (float)(v68 & 1 | (unsigned int)((unsigned __int64)v68 >> 1));
    else
      v69 = (float)(int)v68;
    v70 = (__int64)v270[29];
    if ( v70 < 0 )
    {
      v239 = *(_QWORD *)&v270[29] & 1LL | ((unsigned __int64)v70 >> 1);
      v71 = (float)(int)v239 + (float)(int)v239;
    }
    else
    {
      v71 = (float)(int)v70;
    }
    if ( (float)(v69 / v71) > *v51 )
    {
      v252 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(v51);
      std::_Hash<std::_Umap_traits<std::wstring,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>,0>>::_Forced_rehash(
        v51,
        v252);
      v57 = *(_QWORD **)std::_Hash<std::_Umap_traits<std::wstring,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>,0>>::_Find_last<std::wstring>(
                          v51,
                          &v283,
                          v67 + 16,
                          v53);
    }
    inserted = (_QWORD *)std::_Hash<std::_Uset_traits<Dlp::BrowserCache::HostInfo,std::_Uhash_compare<Dlp::BrowserCache::HostInfo,Dlp::BrowserCache::HostInfoHasher,std::equal_to<Dlp::BrowserCache::HostInfo>>,std::allocator<Dlp::BrowserCache::HostInfo>,0>>::_Insert_new_node_before(
                           v51,
                           v53,
                           v57,
                           v67);
  }
  else
  {
    v58 = *(_QWORD **)(*(_QWORD *)&v55 + 8 * v54);
    while ( 1 )
    {
      v59 = (const WCHAR *)(inserted + 2);
      if ( inserted[5] > 7u )
        v59 = *(const WCHAR **)v59;
      v60 = (const WCHAR *)lpString1;
      if ( v290.m128i_i64[1] > 7uLL )
        v60 = lpString1[0];
      if ( CompareStringOrdinal(v60, -1, v59, -1, 1) == 2 )
        break;
      if ( inserted == v58 )
      {
        v57 = inserted;
        goto LABEL_64;
      }
      inserted = (_QWORD *)inserted[1];
    }
  }
  *(_OWORD *)v286 = 0;
  si128 = 0;
  v72 = v285.m128i_i64[0];
  v73 = v284;
  if ( v285.m128i_i64[1] > 7uLL )
    v73 = (LPCWCH *)v284[0];
  if ( v285.m128i_i64[0] > 0x7FFFFFFFFFFFFFFEuLL )
    std::_Xlength_error("string too long");
  if ( v285.m128i_i64[0] <= 7uLL )
  {
    si128.m128i_i64[0] = v285.m128i_i64[0];
    v76 = 7;
    si128.m128i_i64[1] = 7;
    *(_OWORD *)v286 = *(_OWORD *)v73;
  }
  else
  {
    v74 = v285.m128i_i64[0] | 7;
    if ( (v285.m128i_i64[0] | 7uLL) > 0x7FFFFFFFFFFFFFFELL )
    {
      v74 = 0x7FFFFFFFFFFFFFFELL;
      v75 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      if ( v74 < 0xA )
        v74 = 10;
      v75 = v74 + 1;
      if ( v74 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v286[0] = (void *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v75);
    si128.m128i_i64[0] = v72;
    si128.m128i_i64[1] = v74;
    memmove(v286[0], v73, 2 * v72 + 2);
    v76 = si128.m128i_u64[1];
  }
  v77 = v286;
  v78 = (void **)v286[0];
  if ( v76 > 7 )
    v77 = (void **)v286[0];
  v79 = v286;
  if ( v76 > 7 )
    v79 = (void **)v286[0];
  v80 = (void **)((char *)v79 + 2 * si128.m128i_i64[0]);
  v81 = v286;
  if ( v76 > 7 )
    v81 = (void **)v286[0];
  while ( v81 != v80 )
  {
    *(_WORD *)v77 = towlower(*(_WORD *)v81);
    v81 = (void **)((char *)v81 + 2);
    v77 = (void **)((char *)v77 + 2);
    v76 = si128.m128i_u64[1];
    v78 = (void **)v286[0];
  }
  v82 = v286;
  if ( v76 > 7 )
    v82 = v78;
  for ( i = 0; i < 2 * si128.m128i_i64[0]; ++i )
    v22 = 0x100000001B3LL * (*((unsigned __int8 *)v82 + i) ^ (unsigned __int64)v22);
  if ( v76 > 7 )
  {
    v84 = (const struct std::nothrow_t *)(2 * v76 + 2);
    v268 = (unsigned __int64)v84;
    v282[0] = v78;
    if ( (unsigned __int64)v84 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v282, &v268);
      v84 = (const struct std::nothrow_t *)v268;
      v78 = (void **)v282[0];
    }
    operator delete(v78, v84);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v286[0]) = 0;
  v85 = inserted[9];
  v86 = *(char **)(v85 + 16 * (v22 & inserted[12]) + 8);
  v87 = (char *)inserted[7];
  if ( v86 == v87 )
  {
LABEL_106:
    if ( inserted[8] == 0x6EB3E45306EB3ELL )
      std::_Xlength_error("unordered_map/set too long");
    v283 = (__m128i)(unsigned __int64)(inserted + 7);
    v86 = (char *)operator new(0x250u);
    v283.m128i_i64[1] = (__int64)v86;
    v268 = (unsigned __int64)v284;
    ____0AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____Z__V___pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UFileEnforcementDescriptor_DlpProcessStateCache_DlpProcessCache_RealtimeProtection___std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___1_V__tuple___V_1__Z(
      v86 + 16,
      v91,
      &v268);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<std::wstring,enum DlpEnforcementLevel,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum DlpEnforcementLevel>>,0>>::_Check_rehash_required_1(inserted + 6) )
    {
      v253 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(inserted + 6);
      std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::_Forced_rehash(
        inserted + 6,
        v253);
      v87 = *(char **)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                        inserted + 6,
                        &v283,
                        v86 + 16,
                        v22);
    }
    v92 = (_QWORD *)*((_QWORD *)v87 + 1);
    ++inserted[8];
    *(_QWORD *)v86 = v87;
    *((_QWORD *)v86 + 1) = v92;
    *v92 = v86;
    *((_QWORD *)v87 + 1) = v86;
    v93 = 2 * (v22 & inserted[12]);
    v94 = inserted[9];
    v95 = *(char **)(v94 + 16 * (v22 & inserted[12]));
    if ( v95 == (char *)inserted[7] )
    {
      *(_QWORD *)(v94 + 16 * (v22 & inserted[12])) = v86;
    }
    else
    {
      if ( v95 == v87 )
      {
        *(_QWORD *)(v94 + 16 * (v22 & inserted[12])) = v86;
        goto LABEL_113;
      }
      if ( *(_QWORD **)(v94 + 16 * (v22 & inserted[12]) + 8) != v92 )
        goto LABEL_113;
    }
    *(_QWORD *)(v94 + 8 * v93 + 8) = v86;
    goto LABEL_113;
  }
  v88 = *(char **)(v85 + 16 * (v22 & inserted[12]));
  while ( 1 )
  {
    v89 = (const WCHAR *)(v86 + 16);
    if ( *((_QWORD *)v86 + 5) > 7u )
      v89 = *(const WCHAR **)v89;
    v90 = (const WCHAR *)v284;
    if ( v285.m128i_i64[1] > 7uLL )
      v90 = v284[0];
    if ( CompareStringOrdinal(v90, -1, v89, -1, 1) == 2 )
      break;
    if ( v86 == v88 )
    {
      v87 = v86;
      goto LABEL_106;
    }
    v86 = (char *)*((_QWORD *)v86 + 1);
  }
LABEL_113:
  v96 = (void **)(v86 + 56);
  if ( v86 + 56 != (char *)v284 )
  {
    v97 = *((_QWORD *)v86 + 10);
    if ( v97 > 7 )
    {
      v98 = (const struct std::nothrow_t *)(2 * v97 + 2);
      v268 = (unsigned __int64)v98;
      v99 = *v96;
      v282[0] = *v96;
      if ( (unsigned __int64)v98 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(v282, &v268);
        v98 = (const struct std::nothrow_t *)v268;
        v99 = v282[0];
      }
      operator delete(v99, v98);
    }
    *((_QWORD *)v86 + 9) = 0;
    *((_QWORD *)v86 + 10) = 7;
    *(_WORD *)v96 = 0;
    *(_OWORD *)v96 = *(_OWORD *)v284;
    *(__m128i *)(v86 + 72) = v285;
    v285 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v284[0]) = 0;
  }
  v100 = *((_DWORD *)v86 + 12);
  if ( !v100 )
  {
    *((_DWORD *)v86 + 12) = 1;
    *((struct _FILETIME *)v86 + 61) = SystemTimeAsFileTime;
    v101 = v269[0];
    if ( v269[0] )
    {
      v86[53] = 1;
      std::wstring::assign(v86 + 88, v101);
    }
    v102 = v86 + 288;
    v103 = v277;
    if ( *((_BYTE *)v277 + 64) )
      std::_Optional_construct_base<RealtimeProtection::FileUniqueId>::_Assign<RealtimeProtection::FileUniqueId const &>(
        v102,
        v277);
    else
      std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::reset(v102);
    anonymous_namespace_::GetInstance();
    if ( *((_BYTE *)v103 + 64) )
      v104 = (char *)v103 + 24;
    else
      v104 = v86 + 56;
    Instance = anonymous_namespace_::GetInstance();
    *((_QWORD *)v86 + 59) = anonymous_namespace_::DlpFileEaCacheImpl::AddEa(Instance, v104, v267, v275);
    v106 = v278.m128i_i64[0];
    if ( *(_BYTE *)(v278.m128i_i64[0] + 40) )
    {
      std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
        &v283,
        v278.m128i_i64[0] + 24);
      v107 = _mm_load_si128(&v283);
    }
    else
    {
      v107 = 0;
      v283 = 0;
    }
    if ( *(_BYTE *)(v106 + 16) )
    {
      v230 = *(_QWORD *)(v106 + 8);
      if ( v230 )
        _InterlockedIncrement((volatile signed __int32 *)(v230 + 8));
      v108 = *(volatile signed __int32 **)(v106 + 8);
      v109 = *(std::_Ref_count_base **)v106;
    }
    else
    {
      v108 = 0;
      v109 = 0;
    }
    Lock_shared_ptr_spin_lock();
    v110 = qword_1803139B0;
    if ( qword_1803139B0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_1803139B0 + 2);
      v110 = qword_1803139B0;
    }
    v111 = qword_1803139A8;
    Unlock_shared_ptr_spin_lock();
    if ( v111 )
    {
      anonymous_namespace_::DlpFileSourceDataCacheImpl::GetFileKey(&v291, v103, v86 + 56);
      v112 = _mm_srli_si128(v107, 8).m128i_u64[0];
      if ( v112 )
        _InterlockedIncrement((volatile signed __int32 *)(v112 + 8));
      v278 = v107;
      if ( v108 )
        _InterlockedIncrement(v108 + 2);
      v269[0] = v109;
      v269[1] = (std::_Ref_count_base *)v108;
      v113 = anonymous_namespace_::DlpFileSourceDataCacheImpl::AddEa(v111, &v291, v269, &v278);
      LODWORD(v282[0]) = v113;
      if ( v293.m128i_i64[1] > 7uLL )
      {
        v190 = (const struct std::nothrow_t *)(2 * v293.m128i_i64[1] + 2);
        v268 = (unsigned __int64)v190;
        v191 = v291;
        v277 = (struct RealtimeProtection::FileUniqueId *)v291;
        if ( (unsigned __int64)v190 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&v277, &v268);
          v190 = (const struct std::nothrow_t *)v268;
          v191 = v277;
        }
        operator delete(v191, v190);
      }
      v293 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v291) = 0;
      if ( v110 )
        std::_Ref_count_base::_Decref(v110);
      if ( v108 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v108);
      std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(&v283);
      v114 = (unsigned int)v113;
      if ( v113 >= 0 )
        goto LABEL_143;
    }
    else
    {
      if ( v110 )
        std::_Ref_count_base::_Decref(v110);
      if ( v108 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v108);
      std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(&v283);
      v114 = 2147483662LL;
      LODWORD(v282[0]) = -2147483634;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v114);
    goto LABEL_143;
  }
  *((_DWORD *)v86 + 12) = v100 + 1;
  *((struct _FILETIME *)v86 + 61) = SystemTimeAsFileTime;
  v103 = v277;
  v192 = *((_BYTE *)v277 + 64);
  if ( v86[352] )
  {
    if ( !v192 || *((_QWORD *)v86 + 38) == *((_QWORD *)v277 + 2) )
      goto LABEL_267;
  }
  else if ( !v192 )
  {
    goto LABEL_267;
  }
  RealtimeProtection::DlpFileEaCache::RemoveEa(v86 + 288, v86 + 56);
  v254 = RealtimeProtection::DlpFileSourceDataCache::RemoveEa(v86 + 288, v86 + 56);
  if ( v254 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      (unsigned int)v254);
  std::optional<RealtimeProtection::FileUniqueId>::operator=(v86 + 288, v103);
LABEL_267:
  anonymous_namespace_::GetInstance();
  if ( *((_BYTE *)v103 + 64) )
    v193 = (char *)v103 + 24;
  else
    v193 = v86 + 56;
  v194 = anonymous_namespace_::GetInstance();
  anonymous_namespace_::DlpFileEaCacheImpl::GetEa(v194, &v291, v193);
  if ( v293.m128i_i8[8] )
  {
    anonymous_namespace_::GetInstance();
    if ( *((_BYTE *)v103 + 64) )
      v195 = (char *)v103 + 24;
    else
      v195 = v86 + 56;
    v196 = anonymous_namespace_::GetInstance();
    updated = anonymous_namespace_::DlpFileEaCacheImpl::UpdateEa(v196, v195, v267, v275);
  }
  else
  {
    v210 = v86 + 288;
    if ( *((_BYTE *)v103 + 64) )
      std::_Optional_construct_base<RealtimeProtection::FileUniqueId>::_Assign<RealtimeProtection::FileUniqueId const &>(
        v210,
        v103);
    else
      std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::reset(v210);
    anonymous_namespace_::GetInstance();
    if ( *((_BYTE *)v103 + 64) )
      v211 = (char *)v103 + 24;
    else
      v211 = v86 + 56;
    v212 = anonymous_namespace_::GetInstance();
    updated = anonymous_namespace_::DlpFileEaCacheImpl::AddEa(v212, v211, v267, v275);
  }
  *((_QWORD *)v86 + 59) = updated;
  v298 = 0;
  Lock_shared_ptr_spin_lock();
  v198 = qword_1803139B0;
  if ( qword_1803139B0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_1803139B0 + 2);
    v198 = qword_1803139B0;
  }
  v199 = qword_1803139A8;
  Unlock_shared_ptr_spin_lock();
  if ( !v199 )
  {
    if ( v198 )
      std::_Ref_count_base::_Decref(v198);
    Ea = -2147483634;
    goto LABEL_418;
  }
  anonymous_namespace_::DlpFileSourceDataCacheImpl::GetFileKey(&v283, v103, v86 + 56);
  Ea = anonymous_namespace_::DlpFileSourceDataCacheImpl::GetEa(v199, &v283, v297);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v283);
  if ( v198 )
    std::_Ref_count_base::_Decref(v198);
  if ( Ea < 0 )
  {
LABEL_418:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
        (unsigned int)Ea);
  }
  v201 = v278.m128i_i64[0];
  if ( !v298 )
  {
    v255 = std::optional<std::shared_ptr<EndpointDlp::Client::ApplicationSourceData> const>::value_or<std::nullptr_t>(
             v278.m128i_i64[0] + 24,
             &v283);
    v258 = std::optional<std::shared_ptr<EndpointDlp::Client::MarkOfTheWebData> const>::value_or<std::nullptr_t>(
             v257,
             &v278,
             v256,
             v255);
    v259 = RealtimeProtection::DlpFileSourceDataCache::AddEa(v103, v86 + 56, v258);
    LODWORD(v282[0]) = v259;
    if ( v259 >= 0 )
      goto LABEL_296;
    v260 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_296;
    v261 = 17;
    v209 = (unsigned int)v259;
    goto LABEL_434;
  }
  if ( *(_BYTE *)(v278.m128i_i64[0] + 40) )
  {
    std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
      &v283,
      v278.m128i_i64[0] + 24);
    v202 = _mm_load_si128(&v283);
  }
  else
  {
    v202 = 0;
    v283 = 0;
  }
  if ( *(_BYTE *)(v201 + 16) )
  {
    std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
      v269,
      v201);
    v203 = _mm_load_si128((const __m128i *)v269);
  }
  else
  {
    v203 = 0;
    *(_OWORD *)v269 = 0;
  }
  Lock_shared_ptr_spin_lock();
  v204 = qword_1803139B0;
  if ( qword_1803139B0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_1803139B0 + 2);
    v204 = qword_1803139B0;
  }
  v205 = qword_1803139A8;
  Unlock_shared_ptr_spin_lock();
  if ( v205 )
  {
    anonymous_namespace_::DlpFileSourceDataCacheImpl::GetFileKey(&v294, v103, v86 + 56);
    v206 = _mm_srli_si128(v202, 8).m128i_u64[0];
    if ( v206 )
      _InterlockedIncrement((volatile signed __int32 *)(v206 + 8));
    *(__m128i *)v269 = v202;
    v207 = (volatile signed __int32 *)_mm_srli_si128(v203, 8).m128i_u64[0];
    if ( v207 )
      _InterlockedIncrement(v207 + 2);
    v278 = v203;
    v208 = anonymous_namespace_::DlpFileSourceDataCacheImpl::UpdateEa(v205, &v294, &v278, v269);
    LODWORD(v282[0]) = v208;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v294);
    if ( v204 )
      std::_Ref_count_base::_Decref(v204);
    if ( v207 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v207);
    std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(&v283);
    v209 = (unsigned int)v208;
    if ( v208 >= 0 )
      goto LABEL_296;
  }
  else
  {
    if ( v204 )
      std::_Ref_count_base::_Decref(v204);
    if ( v269[1] )
      std::_Ref_count_base::_Decref(v269[1]);
    std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(&v283);
    v209 = 2147483662LL;
    LODWORD(v282[0]) = -2147483634;
  }
  v260 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v261 = 18;
LABEL_434:
    WPP_SF_d(v260[2], v261, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v209);
  }
LABEL_296:
  if ( v298 )
    RealtimeProtection::DlpFileSourceDataCache::FileEaInfo::~FileEaInfo((RealtimeProtection::DlpFileSourceDataCache::FileEaInfo *)v297);
  if ( v293.m128i_i8[8] )
    std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v292);
LABEL_143:
  v115 = lpFileTime1;
  Dlp::RecentFilesCache::AddItem(v103, (_DWORD)v86 + 56, (int)lpFileTime1, v276);
  if ( !*((_BYTE *)v103 + 64) )
    goto LABEL_144;
  v213 = v274;
  v214 = std::optional<RealtimeProtection::FileUniqueId>::value(v103);
  v215 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                     v213 + 69,
                     &v283,
                     v214);
  v216 = std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
           *v215 + 80LL,
           v269,
           v115);
  ++*(_DWORD *)(*(_QWORD *)v216 + 28LL);
  v217 = (const struct RealtimeProtection::FileUniqueId *)std::optional<RealtimeProtection::FileUniqueId>::value(v103);
  v218 = RealtimeProtection::DlpQuarantineEngine::UpdateQuarantineItemProtectionStatus(
           (RealtimeProtection::DlpQuarantineEngine *)(v213 + 77),
           v217,
           1);
  LODWORD(v282[0]) = v218;
  if ( v218 < 0 )
  {
    v116 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
        (unsigned int)v218);
      v116 = (PVOID *)WPP_GLOBAL_Control;
    }
    LODWORD(v282[0]) = 0;
  }
  else
  {
LABEL_144:
    v116 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v116 != &WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 0x10) != 0 )
    WPP_SF_DSd((TRACEHANDLE)v116[2], (__int64)String1, *((_DWORD *)v86 + 12));
  v117 = 0;
  if ( a11 )
  {
    v118 = (_DWORD *)(v280 + 4);
    v119 = a11;
    do
    {
      *(_DWORD *)&v86[4 * *(v118 - 1) + 184] = *v118;
      if ( !v117 )
        v117 = *v118 != 0;
      v118 += 2;
      --v119;
    }
    while ( v119 );
  }
  v120 = (_WORD **)(v86 + 512);
  v121 = v86 + 512;
  if ( *((_QWORD *)v86 + 67) > 7u )
    v121 = *v120;
  *((_QWORD *)v86 + 66) = 0;
  *v121 = 0;
  *((_QWORD *)v86 + 68) = 0;
  if ( a17 )
  {
    RmsLabelInfo = EndpointDlp::Client::GetRmsLabelInfo(v275, v267, (int)v86 + 56, (_DWORD)v120, (__int64)(v86 + 544));
    LODWORD(v282[0]) = RmsLabelInfo;
    if ( RmsLabelInfo < 0 )
    {
      if ( RmsLabelInfo != -2147023728
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          (unsigned int)RmsLabelInfo);
      }
      LODWORD(v282[0]) = 0;
    }
    v117 |= *((_QWORD *)v86 + 66) != 0;
  }
  v86[364] = v117;
  v122 = (char *)v271 + 32;
  v123 = v86 + 256;
  if ( v86 + 256 != (char *)v271 + 32 )
  {
    v124 = *((_QWORD *)v271 + 6);
    if ( *((_QWORD *)v271 + 7) > 7u )
      v122 = (_QWORD *)*v122;
    v125 = *((_QWORD *)v86 + 35);
    if ( v124 > v125 )
    {
      if ( v124 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      v165 = v124 | 7;
      if ( (v124 | 7) > 0x7FFFFFFFFFFFFFFELL || (v166 = v125 >> 1, v125 > 0x7FFFFFFFFFFFFFFELL - (v125 >> 1)) )
      {
        v165 = 0x7FFFFFFFFFFFFFFELL;
        v167 = 0x7FFFFFFFFFFFFFFFLL;
      }
      else
      {
        if ( v165 < v125 + v166 )
          v165 = v125 + v166;
        v167 = v165 + 1;
        if ( v165 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      _mm_lfence();
      v168 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v167);
      *((_QWORD *)v86 + 34) = v124;
      *((_QWORD *)v86 + 35) = v165;
      v169 = 2 * v124;
      memmove(v168, v122, v169);
      *(_WORD *)&v168[v169] = 0;
      if ( v125 > 7 )
      {
        _mm_lfence();
        std::_Deallocate<16>(*v123, 2 * v125 + 2);
      }
      *v123 = v168;
    }
    else
    {
      v126 = v86 + 256;
      if ( v125 > 7 )
        v126 = (char *)*v123;
      *((_QWORD *)v86 + 34) = v124;
      v127 = 2 * v124;
      memmove(v126, v122, v127);
      *(_WORD *)&v126[v127] = 0;
    }
  }
  v128 = v86 + 224;
  v129 = v271;
  if ( v86 + 224 != v271 )
  {
    v130 = *((_QWORD *)v271 + 2);
    if ( *((_QWORD *)v271 + 3) > 7u )
      v129 = *(void **)v271;
    v131 = *((_QWORD *)v86 + 31);
    if ( v130 > v131 )
    {
      if ( v130 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      v170 = v130 | 7;
      if ( (v130 | 7) > 0x7FFFFFFFFFFFFFFELL || (v171 = v131 >> 1, v131 > 0x7FFFFFFFFFFFFFFELL - (v131 >> 1)) )
      {
        v170 = 0x7FFFFFFFFFFFFFFELL;
        v172 = 0x7FFFFFFFFFFFFFFFLL;
      }
      else
      {
        if ( v170 < v131 + v171 )
          v170 = v131 + v171;
        v172 = v170 + 1;
        if ( v170 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      _mm_lfence();
      v173 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v172);
      *((_QWORD *)v86 + 30) = v130;
      *((_QWORD *)v86 + 31) = v170;
      v174 = 2 * v130;
      memmove(v173, v129, v174);
      *(_WORD *)&v173[v174] = 0;
      if ( v131 > 7 )
      {
        _mm_lfence();
        std::_Deallocate<16>(*v128, 2 * v131 + 2);
      }
      *v128 = v173;
    }
    else
    {
      v132 = v86 + 224;
      if ( v131 > 7 )
        v132 = (char *)*v128;
      *((_QWORD *)v86 + 30) = v130;
      v133 = 2 * v130;
      memmove(v132, v129, v133);
      *(_WORD *)&v132[v133] = 0;
    }
  }
  v134 = v86 + 368;
  v135 = -1;
  v136 = (char *)v272;
  do
    ++v135;
  while ( *((_WORD *)v272 + v135) );
  v137 = *((_QWORD *)v86 + 49);
  if ( v135 > v137 )
  {
    if ( v135 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    v175 = v135 | 7;
    if ( (v135 | 7) > 0x7FFFFFFFFFFFFFFELL || (v176 = v137 >> 1, v137 > 0x7FFFFFFFFFFFFFFELL - (v137 >> 1)) )
    {
      v175 = 0x7FFFFFFFFFFFFFFELL;
      v177 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      if ( v175 < v137 + v176 )
        v175 = v137 + v176;
      v177 = v175 + 1;
      if ( v175 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v178 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v177);
    _mm_lfence();
    *((_QWORD *)v86 + 48) = v135;
    *((_QWORD *)v86 + 49) = v175;
    v179 = 2 * v135;
    memmove(v178, v136, v179);
    *(_WORD *)&v178[v179] = 0;
    if ( v137 > 7 )
    {
      _mm_lfence();
      std::_Deallocate<16>(*v134, 2 * v137 + 2);
    }
    *v134 = v178;
  }
  else
  {
    _mm_lfence();
    v138 = v86 + 368;
    if ( v137 > 7 )
      v138 = (char *)*v134;
    *((_QWORD *)v86 + 48) = v135;
    v139 = 2 * v135;
    memmove(v138, v136, v139);
    *(_WORD *)&v138[v139] = 0;
  }
  v140 = v136 + 146;
  v141 = v86 + 400;
  v142 = -1;
  do
    ++v142;
  while ( v140[v142] );
  v143 = *((_QWORD *)v86 + 53);
  if ( v142 > v143 )
  {
    if ( v142 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    v180 = v142 | 7;
    if ( (v142 | 7) > 0x7FFFFFFFFFFFFFFELL || (v181 = v143 >> 1, v143 > 0x7FFFFFFFFFFFFFFELL - (v143 >> 1)) )
    {
      v180 = 0x7FFFFFFFFFFFFFFELL;
      v182 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      if ( v180 < v143 + v181 )
        v180 = v143 + v181;
      v182 = v180 + 1;
      if ( v180 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v183 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v182);
    _mm_lfence();
    *((_QWORD *)v86 + 52) = v142;
    *((_QWORD *)v86 + 53) = v180;
    v184 = 2 * v142;
    memmove(v183, v140, v184);
    *(_WORD *)&v183[v184] = 0;
    if ( v143 > 7 )
    {
      _mm_lfence();
      std::_Deallocate<16>(*v141, 2 * v143 + 2);
    }
    *v141 = v183;
  }
  else
  {
    _mm_lfence();
    v144 = v86 + 400;
    if ( v143 > 7 )
      v144 = (char *)*v141;
    *((_QWORD *)v86 + 52) = v142;
    v145 = 2 * v142;
    memmove(v144, v140, v145);
    *(_WORD *)&v144[v145] = 0;
  }
  v146 = (char *)v272;
  v147 = v86 + 432;
  v148 = -1;
  do
    ++v148;
  while ( *((_WORD *)v272 + v148 + 202) );
  v149 = *((_QWORD *)v86 + 57);
  if ( v148 > v149 )
  {
    v185 = 0x7FFFFFFFFFFFFFFELL;
    if ( v148 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( (v148 | 7) > 0x7FFFFFFFFFFFFFFELL || (v186 = v149 >> 1, v149 > 0x7FFFFFFFFFFFFFFELL - (v149 >> 1)) )
    {
      v187 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      v185 = v148 | 7;
      if ( (v148 | 7) < v186 + v149 )
        v185 = v186 + v149;
      v187 = v185 + 1;
      if ( (unsigned __int64)(v185 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
    }
    _mm_lfence();
    v188 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v187);
    _mm_lfence();
    *((_QWORD *)v86 + 56) = v148;
    *((_QWORD *)v86 + 57) = v185;
    v189 = 2 * v148;
    memmove(v188, v146 + 404, v189);
    *(_WORD *)&v188[v189] = 0;
    if ( v149 > 7 )
    {
      _mm_lfence();
      std::_Deallocate<16>(*v147, 2 * v149 + 2);
    }
    *v147 = v188;
  }
  else
  {
    _mm_lfence();
    v150 = v86 + 432;
    if ( v149 > 7 )
      v150 = (char *)*v147;
    *((_QWORD *)v86 + 56) = v148;
    v151 = 2 * v148;
    memmove(v150, v146 + 404, v151);
    *(_WORD *)&v150[v151] = 0;
  }
  v86[464] = a15;
  *((_DWORD *)v86 + 90) = a10;
  v152 = (__int64)(v86 + 256);
  if ( *((_QWORD *)v86 + 35) > 7u )
    v152 = *((_QWORD *)v86 + 32);
  v283.m128i_i64[0] = v152;
  v283.m128i_i64[1] = *((_QWORD *)v86 + 34);
  if ( dword_1803142AC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 108LL) )
  {
    Init_thread_header(&dword_1803142AC);
    if ( dword_1803142AC == -1 )
    {
      *(_OWORD *)&xmmword_1803142B0 = 0;
      std::make_shared<EndpointDlp::endpointDlpImpl,>();
      atexit(EndpointDlp::endpointDlpImpl::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_1803142AC);
    }
  }
  v153 = (volatile signed __int32 *)*(&xmmword_1803142B0 + 1);
  if ( *(&xmmword_1803142B0 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&xmmword_1803142B0 + 1) + 2);
    v153 = (volatile signed __int32 *)*(&xmmword_1803142B0 + 1);
  }
  v154 = EndpointDlp::endpointDlpImpl::CheckRuleIdIsJitCandidateOrFallback(xmmword_1803142B0, 1, &v283);
  if ( v153 && _InterlockedExchangeAdd(v153 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v153)(v153);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v153);
  }
  v86[465] = v154;
  if ( (Dlp::FeatureControl::GetValue(144) & 1) == 0 )
    goto LABEL_200;
  v283 = 0;
  EndpointDlp::ExtendedAttribute::GetLabelIdOnFile((unsigned int)&v294, v275, v267, (_DWORD)v86 + 56, (__int64)&v283);
  v155 = v86[584];
  if ( v296 )
  {
    if ( !v155 )
    {
      *(_OWORD *)(v86 + 552) = v294;
      *(__m128i *)(v86 + 568) = v295;
      v156 = _mm_load_si128((const __m128i *)&_xmm);
      v295 = v156;
      LOWORD(v294) = 0;
      v86[584] = 1;
      goto LABEL_198;
    }
    std::wstring::operator=(v86 + 552, &v294);
  }
  else
  {
    if ( !v155 )
      goto LABEL_200;
    std::wstring::`scalar deleting destructor'(v86 + 552);
    v86[584] = 0;
  }
  v156 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_198:
  if ( v296 )
  {
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v294);
LABEL_200:
    v156 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v157 = v270;
  v158 = LOBYTE(v270[86].dwLowDateTime) || v86[465];
  LOBYTE(v270[86].dwLowDateTime) = v158;
  if ( LOBYTE(v157[111].dwLowDateTime) )
  {
    for ( j = 0; j < 0xA; j = v264 + 1 )
    {
      if ( (unsigned __int8)RealtimeProtection::DlpUtils::IsEnforcementLevelSupersedes(
                              *(unsigned int *)&v86[4 * j + 184],
                              *(&v157[95].dwLowDateTime + j)) )
      {
        std::_Optional_destruct_base<RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DlpRecallCache,0>::reset(&v157[87]);
        v265 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v266 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v157[12]);
          WPP_SF_S(v265[2], 104, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v266);
        }
        break;
      }
    }
    v156 = _mm_load_si128((const __m128i *)&_xmm);
  }
  if ( v290.m128i_i64[1] > 7uLL )
  {
    v159 = (void *)(2 * v290.m128i_i64[1] + 2);
    v272 = v159;
    v160 = (WCHAR *)lpString1[0];
    v271 = (void *)lpString1[0];
    if ( (unsigned __int64)v159 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v271, (unsigned __int64 *)&v272);
      v159 = v272;
      v160 = (WCHAR *)v271;
    }
    operator delete(v160, (const struct std::nothrow_t *)v159);
    v156 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v290 = v156;
  LOWORD(lpString1[0]) = 0;
  if ( v285.m128i_i64[1] > 7uLL )
  {
    v161 = (void *)(2 * v285.m128i_i64[1] + 2);
    v272 = v161;
    v162 = (WCHAR *)v284[0];
    v271 = (void *)v284[0];
    if ( (unsigned __int64)v161 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v271, (unsigned __int64 *)&v272);
      v161 = v272;
      v162 = (WCHAR *)v271;
    }
    operator delete(v162, (const struct std::nothrow_t *)v161);
  }
  v163 = (unsigned int)v282[0];
  if ( SLODWORD(v282[0]) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      LODWORD(v282[0]));
  }
  return v163;
}

```

## disassembly

```asm
0x180034800  mov     rax, rsp
0x180034803  push    rbx
0x180034804  push    rsi
0x180034805  push    rdi
0x180034806  push    r12
0x180034808  push    r13
0x18003480a  push    r14
0x18003480c  push    r15
0x18003480e  sub     rsp, 1F0h
0x180034815  movaps  xmmword ptr [rax-48h], xmm6
0x180034819  movaps  xmmword ptr [rax-58h], xmm7
0x18003481d  mov     rax, cs:__security_cookie
0x180034824  xor     rax, rsp
0x180034827  mov     [rsp+228h+var_60], rax
0x18003482f  mov     [rsp+228h+var_1A8], r9d
0x180034837  mov     dword ptr [rsp+228h+var_1F0], r8d
0x18003483c  mov     r8, rdx
0x18003483f  mov     [rsp+228h+lpFileTime1], rdx
0x180034844  mov     r9, rcx
0x180034847  mov     [rsp+228h+var_1B8], rcx
0x18003484c  mov     rax, [rsp+228h+arg_60]
0x180034854  mov     [rsp+228h+var_1D0], rax
0x180034859  mov     rsi, [rsp+228h+Src]
0x180034861  mov     rax, [rsp+228h+arg_30]
0x180034869  mov     [rsp+228h+String1], rax
0x180034871  mov     rax, [rsp+228h+arg_38]
0x180034879  mov     [rsp+228h+var_1E8], rax
0x18003487e  mov     rax, [rsp+228h+arg_40]
0x180034886  mov     [rsp+228h+var_1A0], rax
0x18003488e  mov     rax, [rsp+228h+arg_58]
0x180034896  mov     [rsp+228h+var_180], rax
0x18003489e  mov     rdi, [rsp+228h+arg_68]
0x1800348a6  mov     [rsp+228h+var_1C8], rdi
0x1800348ab  mov     rdx, [rsp+228h+arg_78]
0x1800348b3  mov     qword ptr [rsp+228h+var_198], rdx
0x1800348bb  xor     r11d, r11d
0x1800348be  movzx   ecx, byte ptr [rdx+40h]
0x1800348c2  test    cl, cl
0x1800348c4  jnz     loc_180036267
0x1800348ca  mov     [rsp+228h+var_1F8], r11d
0x1800348cf  test    cl, cl
0x1800348d1  jnz     loc_180036287
0x1800348d7  mov     [rsp+228h+var_1B0], r11
0x1800348dc  movsd   xmm6, qword ptr [r8]
0x1800348e1  mov     eax, [r8+8]
0x1800348e5  mov     dword ptr [rsp+228h+var_168], eax
0x1800348ec  lea     r13, [r9+88h]
0x1800348f3  lfence
0x1800348f6  movzx   r14d, byte ptr [r8+8]
0x1800348fb  mov     rdi, 0CBF29CE484222325h
0x180034905  xor     r14, rdi
0x180034908  mov     rdx, 100000001B3h
0x180034912  imul    r14, rdx
0x180034916  movzx   eax, byte ptr [r8+9]
0x18003491b  xor     r14, rax
0x18003491e  imul    r14, rdx
0x180034922  movzx   eax, byte ptr [r8+0Ah]
0x180034927  xor     r14, rax
0x18003492a  imul    r14, rdx
0x18003492e  movzx   eax, byte ptr [r8+0Bh]
0x180034933  xor     r14, rax
0x180034936  imul    r14, rdx
0x18003493a  mov     rax, [r13+30h]
0x18003493e  and     rax, r14
0x180034941  add     rax, rax
0x180034944  mov     rcx, [r13+18h]
0x180034948  mov     rbx, [rcx+rax*8+8]
0x18003494d  mov     r15, [r13+8]
0x180034951  cmp     rbx, r15
0x180034954  jz      loc_1800366D7
0x18003495a  mov     rcx, [rcx+rax*8]
0x18003495e  mov     eax, [rbx+10h]
0x180034961  cmp     [r8+8], eax
0x180034965  jz      short loc_180034991
0x180034967  cmp     rbx, rcx
0x18003496a  jz      loc_1800366D4
0x180034970  mov     rbx, [rbx+8]
0x180034974  jmp     short loc_18003495E
0x180034976  mov     [rcx+rax*8], rbx
0x18003497a  mov     [rcx+rax*8+8], rbx
0x18003497f  mov     r8, [rsp+228h+lpFileTime1]
0x180034984  mov     rdx, 100000001B3h
0x18003498e  xor     r11d, r11d
0x180034991  movsd   qword ptr [rbx+14h], xmm6
0x180034996  mov     eax, dword ptr [rsp+228h+var_168]
0x18003499d  mov     [rbx+1Ch], eax
0x1800349a0  lfence
0x1800349a3  movzx   ecx, byte ptr [r8+8]
0x1800349a8  xor     rcx, rdi
0x1800349ab  imul    rcx, rdx
0x1800349af  movzx   eax, byte ptr [r8+9]
0x1800349b4  xor     rcx, rax
0x1800349b7  imul    rcx, rdx
0x1800349bb  movzx   eax, byte ptr [r8+0Ah]
0x1800349c0  xor     rcx, rax
0x1800349c3  imul    rcx, rdx
0x1800349c7  movzx   eax, byte ptr [r8+0Bh]
0x1800349cc  xor     rcx, rax
0x1800349cf  imul    rcx, rdx
0x1800349d3  and     rcx, [r9+138h]
0x1800349da  add     rcx, rcx
0x1800349dd  mov     rax, [r9+120h]
0x1800349e4  mov     rbx, [rax+rcx*8+8]
0x1800349e9  cmp     rbx, [r9+110h]
0x1800349f0  jnz     loc_180034A79
0x1800349f6  mov     rbx, r11
0x1800349f9  test    rbx, rbx
0x1800349fc  jnz     loc_1800363C9
0x180034a02  lea     r14, [r9+0C8h]
0x180034a09  mov     dword ptr [rsp+228h+var_168], r11d
0x180034a11  mov     edx, 0Ch
0x180034a16  lea     rcx, [rsp+228h+var_168]
0x180034a1e  call    MpHashCrc32
0x180034a23  mov     r12d, dword ptr [rsp+228h+var_168]
0x180034a2b  mov     rax, [r14+30h]
0x180034a2f  and     rax, r12
0x180034a32  add     rax, rax
0x180034a35  mov     rcx, [r14+18h]
0x180034a39  mov     r13, [rcx+rax*8+8]
0x180034a3e  mov     [rsp+228h+var_1D8], r13
0x180034a43  mov     r15, [r14+8]
0x180034a47  cmp     r13, r15
0x180034a4a  jz      loc_18003615F
0x180034a50  mov     rbx, [rcx+rax*8]
0x180034a54  mov     rcx, [rsp+228h+lpFileTime1]; lpFileTime1
0x180034a59  lea     rdx, [r13+10h]; lpFileTime2
0x180034a5d  mov     eax, [rdx+8]
0x180034a60  cmp     [rcx+8], eax
0x180034a63  jz      short loc_180034A99
0x180034a65  cmp     r13, rbx
0x180034a68  jz      loc_18003615C
0x180034a6e  mov     r13, [r13+8]
0x180034a72  mov     [rsp+228h+var_1D8], r13
0x180034a77  jmp     short loc_180034A59
0x180034a79  mov     rdx, [rax+rcx*8]
0x180034a7d  mov     eax, [rbx+10h]
0x180034a80  cmp     [r8+8], eax
0x180034a84  jz      loc_1800349F9
0x180034a8a  cmp     rbx, rdx
0x180034a8d  jz      loc_1800349F6
0x180034a93  mov     rbx, [rbx+8]
0x180034a97  jmp     short loc_180034A7D
0x180034a99  call    cs:__imp_CompareFileTime
0x180034a9f  test    eax, eax
0x180034aa1  jnz     loc_180036732
0x180034aa7  lea     r15, [r13+60h]
0x180034aab  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180034ab2  inc     rbx
0x180034ab5  cmp     word ptr [rsi+rbx*2], 0
0x180034aba  jnz     short loc_180034AB2
0x180034abc  mov     r14, [r15+18h]
0x180034ac0  cmp     rbx, r14
0x180034ac3  ja      loc_180034D02
0x180034ac9  lfence
0x180034acc  mov     r12, r15
0x180034acf  cmp     r14, 7
0x180034ad3  jbe     short loc_180034AD8
0x180034ad5  mov     r12, [r15]
0x180034ad8  mov     [r15+10h], rbx
0x180034adc  add     rbx, rbx
0x180034adf  mov     r8, rbx; Size
0x180034ae2  mov     rdx, rsi; Src
0x180034ae5  mov     rcx, r12; void *
0x180034ae8  call    memmove
0x180034aed  xor     esi, esi
0x180034aef  mov     [rbx+r12], si
0x180034af4  mov     r14, 7FFFFFFFFFFFFFFEh
0x180034afe  mov     r15, 7FFFFFFFFFFFFFFFh
0x180034b08  movzx   eax, [rsp+228h+arg_28]
0x180034b10  mov     [r13+0ACh], al
0x180034b17  mov     eax, [rsp+228h+var_1A8]
0x180034b1e  mov     [r13+0A0h], eax
0x180034b25  mov     eax, dword ptr [rsp+228h+var_1F0]
0x180034b29  mov     dword ptr [rsp+228h+var_1F0], eax
0x180034b2d  mov     byte ptr [rsp+228h+var_1F0+4], 1
0x180034b32  mov     rax, [rsp+228h+var_1F0]
0x180034b37  mov     [r13+0A4h], rax
0x180034b3e  mov     byte ptr [rsp+228h+var_170], 0
0x180034b46  xor     r8d, r8d; bool *
0x180034b49  lea     rdx, [rsp+228h+var_170]; wchar_t *
0x180034b51  mov     r12, [rsp+228h+String1]
0x180034b59  mov     rcx, r12; String1
0x180034b5c  call    ?UtilIsNetworkPath@CommonUtil@@YAJPEB_WPEA_N1@Z; CommonUtil::UtilIsNetworkPath(wchar_t const *,bool *,bool *)
0x180034b61  cmp     byte ptr [rsp+228h+var_170], 0
0x180034b69  jnz     loc_180036772
0x180034b6f  mov     qword ptr [rsp+228h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180034b77  lea     rcx, [rsp+228h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034b7f  call    cs:__imp_GetSystemTimeAsFileTime
0x180034b85  xorps   xmm0, xmm0
0x180034b88  movups  xmmword ptr [rsp+228h+var_138], xmm0
0x180034b90  xorps   xmm1, xmm1
0x180034b93  movdqu  [rsp+228h+var_128], xmm1
0x180034b9c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180034ba3  inc     rbx
0x180034ba6  cmp     word ptr [r12+rbx*2], 0
0x180034bac  jnz     short loc_180034BA3
0x180034bae  cmp     rbx, r14
0x180034bb1  ja      loc_18003677F
0x180034bb7  cmp     rbx, 7
0x180034bbb  jbe     loc_180034DA4
0x180034bc1  mov     rsi, rbx
0x180034bc4  or      rsi, 7
0x180034bc8  cmp     rsi, r14
0x180034bcb  ja      loc_180034DF0
0x180034bd1  mov     r15d, 0Ah
0x180034bd7  cmp     rsi, r15
0x180034bda  cmovb   rsi, r15
0x180034bde  lea     rcx, [rsi+1]
0x180034be2  mov     rax, 7FFFFFFFFFFFFFFFh
0x180034bec  cmp     rcx, rax
0x180034bef  ja      loc_18003678B
0x180034bf5  lfence
0x180034bf8  add     rcx, rcx
0x180034bfb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180034c00  mov     r14, rax
0x180034c03  lfence
0x180034c06  mov     [rsp+228h+var_138], rax
0x180034c0e  mov     qword ptr [rsp+228h+var_128], rbx
0x180034c16  mov     qword ptr [rsp+228h+var_128+8], rsi
0x180034c1e  add     rbx, rbx
0x180034c21  mov     r8, rbx; Size
0x180034c24  mov     rdx, r12; Src
0x180034c27  mov     rcx, rax; void *
0x180034c2a  call    memmove
0x180034c2f  xor     eax, eax
0x180034c31  mov     [r14+rbx], ax
0x180034c36  lea     rdx, [rsp+228h+var_138]
0x180034c3e  cmp     qword ptr [rsp+228h+var_128+8], 7
0x180034c47  cmova   rdx, [rsp+228h+var_138]
0x180034c50  lea     rcx, [rsp+228h+lpString1]
0x180034c58  call    ?GetFileExtensions@DlpUtils@RealtimeProtection@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; RealtimeProtection::DlpUtils::GetFileExtensions(wchar_t const *)
0x180034c5d  nop
0x180034c5e  lea     r14, [r13+0B0h]
0x180034c65  lea     rdx, [rsp+228h+lpString1]
0x180034c6d  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(std::wstring const &)
0x180034c72  mov     rsi, rax
0x180034c75  mov     rax, [r13+0E0h]
0x180034c7c  and     rax, rsi
0x180034c7f  add     rax, rax
0x180034c82  mov     rcx, [r13+0C8h]
0x180034c89  mov     r13, [rcx+rax*8+8]
0x180034c8e  mov     r12, [rsp+228h+var_1D8]
0x180034c93  mov     rbx, [r12+0B8h]
0x180034c9b  cmp     r13, rbx
0x180034c9e  jz      loc_180034E01
0x180034ca4  mov     rbx, [rcx+rax*8]
0x180034ca8  lea     r8, [r13+10h]
0x180034cac  cmp     qword ptr [r13+28h], 7
0x180034cb1  jbe     short loc_180034CB6
0x180034cb3  mov     r8, [r8]; lpString2
0x180034cb6  lea     rcx, [rsp+228h+lpString1]
0x180034cbe  cmp     [rsp+228h+var_D8], 7
0x180034cc7  cmova   rcx, [rsp+228h+lpString1]; lpString1
0x180034cd0  mov     [rsp+228h+bIgnoreCase], 1; bIgnoreCase
0x180034cd8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180034cdf  mov     r9d, eax; cchCount2
0x180034ce2  mov     edx, eax; cchCount1
0x180034ce4  call    cs:__imp_CompareStringOrdinal
0x180034cea  cmp     eax, 2
0x180034ced  jz      loc_180034EBC
0x180034cf3  cmp     r13, rbx
0x180034cf6  jz      loc_180036791
0x180034cfc  mov     r13, [r13+8]
0x180034d00  jmp     short loc_180034CA8
0x180034d02  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180034d0c  cmp     rbx, rdx
0x180034d0f  ja      loc_180034DE4
0x180034d15  mov     r13, rbx
0x180034d18  or      r13, 7
0x180034d1c  cmp     r13, rdx
0x180034d1f  ja      loc_1800360E1
0x180034d25  mov     rcx, r14
0x180034d28  shr     rcx, 1
0x180034d2b  mov     rax, rdx
0x180034d2e  sub     rax, rcx
0x180034d31  cmp     r14, rax
0x180034d34  ja      loc_1800360E1
0x180034d3a  lea     rax, [rcx+r14]
0x180034d3e  cmp     r13, rax
0x180034d41  cmovb   r13, rax
0x180034d45  lea     rcx, [r13+1]
0x180034d49  mov     rax, 7FFFFFFFFFFFFFFFh
0x180034d53  cmp     rcx, rax
0x180034d56  ja      loc_18003676D
0x180034d5c  lfence
0x180034d5f  add     rcx, rcx
0x180034d62  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180034d67  mov     r12, rax
0x180034d6a  lfence
0x180034d6d  mov     [r15+10h], rbx
0x180034d71  mov     [r15+18h], r13
0x180034d75  add     rbx, rbx
0x180034d78  mov     r8, rbx; Size
0x180034d7b  mov     rdx, rsi; Src
0x180034d7e  mov     rcx, rax; void *
0x180034d81  call    memmove
0x180034d86  xor     esi, esi
0x180034d88  mov     [r12+rbx], si
0x180034d8d  cmp     r14, 7
0x180034d91  ja      loc_1800362EB
  ... truncated ...
```
