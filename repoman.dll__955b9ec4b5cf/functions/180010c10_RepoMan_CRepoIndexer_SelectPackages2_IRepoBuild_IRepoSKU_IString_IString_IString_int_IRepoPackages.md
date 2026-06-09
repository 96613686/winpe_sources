# RepoMan::CRepoIndexer::SelectPackages2(IRepoBuild *,IRepoSKU *,IString *,IString *,IString *,int,IRepoPackages * *)

- ea: `0x180010c10`
- end: `0x180011d38`
- name: `?SelectPackages2@CRepoIndexer@RepoMan@@UEAAJPEAUIRepoBuild@@PEAUIRepoSKU@@PEAUIString@@22HPEAPEAUIRepoPackages@@@Z`
- size: `4392`
- prototype: `__int64 __fastcall(RepoMan::CRepoIndexer *__hidden this, struct IRepoBuild *, struct IRepoSKU *, struct IString *, struct IString *, struct IString *, char, struct IRepoPackages **)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008574`
- `0x180008770`
- `0x180010c10`
- `0x180013b14`
- `0x180017530`
- `0x180017630`
- `0x180017704`
- `0x180018018`
- `0x18001ac20`
- `0x18001bd40`
- `0x1800244d0`
- `0x1800247fc`
- `0x1800248b4`
- `0x18002bf14`
- `0x18002e0a8`
- `0x18002f940`
- `0x18002f9b0`
- `0x180031120`
- `0x18003a240`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b53c`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180011084`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800111a0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800119a9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180011084`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800111a0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800119a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800110dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800113fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180011b35`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180011b46`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800110dc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800113fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180011b35`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180011b46`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800113f3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800113f3`

## string_xrefs

- `0x180011cf5`: `undefined name or URI for build`
- `0x180011caf`: `unable to form URI for cells in distribution`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall RepoMan::CRepoIndexer::SelectPackages2(
        RepoMan::CRepoIndexer *this,
        struct IRepoBuild *a2,
        struct IRepoSKU *a3,
        struct IString *a4,
        struct IString *a5,
        struct IString *a6,
        char a7,
        struct IRepoPackages **a8)
{
  struct IRepoPackages **v12; // r15
  RepoMan *v13; // rcx
  const char *v14; // r9
  int v15; // edx
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  size_t v20; // r8
  __int64 *v21; // rdx
  int v22; // r14d
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rax
  __m128i si128; // xmm6
  _BYTE *v27; // rax
  size_t v28; // r8
  _BYTE *v29; // rax
  size_t v30; // r8
  __int64 *v31; // rdx
  unsigned int v32; // r14d
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rbx
  __m128i v38; // xmm7
  __m128i v39; // xmm8
  _QWORD *v40; // rdi
  void *v41; // rcx
  _QWORD *v42; // rax
  __int64 *v43; // rbx
  struct IRepoBuild *v44; // rdi
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 **v48; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  bool v51; // r12
  __int64 v52; // rcx
  void *v53; // rcx
  RepoMan::CRepoIndexer *v54; // rsi
  RepoMan *v55; // rcx
  const char *v56; // r9
  __int64 v57; // rax
  _QWORD *v58; // rdx
  __int64 v59; // rdi
  __int64 *v60; // rbx
  _OWORD *v61; // rdx
  void **v62; // rdx
  RepoMan *v63; // rcx
  const char *v64; // r9
  RepoMan *v65; // rcx
  const char *v66; // r9
  void **v67; // r9
  unsigned int v68; // eax
  const char *v69; // r9
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 **v72; // rax
  __int64 *k; // rax
  __int64 *m; // rcx
  RepoMan *v75; // rcx
  const char *v76; // r9
  __int64 v77; // rsi
  __int64 (__fastcall *v78)(__int64); // rdi
  __int64 v79; // rbx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 *v83; // rbx
  RepoMan::CRepoIndexer *v84; // rsi
  __int64 v85; // rdi
  int v86; // r14d
  _DWORD *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  void **v90; // rdx
  __int64 **v91; // rax
  __int64 *n; // rax
  __int64 *ii; // rcx
  struct IRepoPackages **v94; // rax
  struct IRepoPackages *v95; // rcx
  RepoMan::CRepoIndexer *v96; // rcx
  void *v97; // rcx
  _QWORD *v98; // rbx
  void *v99; // rcx
  __int64 v100; // rcx
  int v101; // r8d
  __int64 result; // rax
  __int64 v103; // [rsp+30h] [rbp-2C8h] BYREF
  __int64 v104; // [rsp+38h] [rbp-2C0h] BYREF
  void *v105[2]; // [rsp+40h] [rbp-2B8h] BYREF
  __int64 v106; // [rsp+50h] [rbp-2A8h] BYREF
  __int64 v107; // [rsp+58h] [rbp-2A0h] BYREF
  __int64 v108; // [rsp+60h] [rbp-298h] BYREF
  RepoMan::CRepoIndexer *v109; // [rsp+68h] [rbp-290h] BYREF
  __int64 v110; // [rsp+70h] [rbp-288h] BYREF
  _DWORD *v111; // [rsp+78h] [rbp-280h] BYREF
  __int64 v112; // [rsp+80h] [rbp-278h] BYREF
  __m128i v113; // [rsp+88h] [rbp-270h] BYREF
  __int64 v114; // [rsp+98h] [rbp-260h]
  __m128i v115; // [rsp+A0h] [rbp-258h] BYREF
  __int64 v116; // [rsp+B0h] [rbp-248h]
  struct IRepoBuild *v117; // [rsp+B8h] [rbp-240h]
  __m128i v118; // [rsp+C0h] [rbp-238h] BYREF
  __int64 v119; // [rsp+D0h] [rbp-228h]
  __m128i v120; // [rsp+D8h] [rbp-220h] BYREF
  __int64 v121; // [rsp+E8h] [rbp-210h]
  __int64 v122; // [rsp+F0h] [rbp-208h] BYREF
  __int64 v123; // [rsp+F8h] [rbp-200h] BYREF
  struct IRepoPackages **v124; // [rsp+100h] [rbp-1F8h]
  __m128i v125; // [rsp+110h] [rbp-1E8h] BYREF
  __int64 v126; // [rsp+120h] [rbp-1D8h]
  void *Block[2]; // [rsp+128h] [rbp-1D0h] BYREF
  __m128i v128; // [rsp+138h] [rbp-1C0h]
  _BYTE v129[24]; // [rsp+148h] [rbp-1B0h] BYREF
  unsigned __int64 v130; // [rsp+160h] [rbp-198h]
  CHAR MultiByteStr[16]; // [rsp+168h] [rbp-190h] BYREF
  __m128i v132; // [rsp+178h] [rbp-180h]
  __int64 *v133; // [rsp+188h] [rbp-170h]
  char *v134; // [rsp+190h] [rbp-168h]
  void **v135; // [rsp+198h] [rbp-160h]
  CHAR *v136; // [rsp+1A0h] [rbp-158h]
  __int128 v137; // [rsp+1A8h] [rbp-150h] BYREF
  __int64 v138; // [rsp+1B8h] [rbp-140h]
  unsigned __int64 v139; // [rsp+1C0h] [rbp-138h]
  _QWORD v140[3]; // [rsp+1D0h] [rbp-128h] BYREF
  int v141; // [rsp+1E8h] [rbp-110h]
  __int64 v142; // [rsp+1F0h] [rbp-108h]
  _QWORD *v143; // [rsp+208h] [rbp-F0h]
  _QWORD v144[2]; // [rsp+210h] [rbp-E8h] BYREF
  int v145; // [rsp+220h] [rbp-D8h]
  __int64 v146; // [rsp+228h] [rbp-D0h]
  _QWORD *v147; // [rsp+248h] [rbp-B0h]
  _BYTE v148[40]; // [rsp+250h] [rbp-A8h] BYREF
  __int64 v149; // [rsp+278h] [rbp-80h]

  v117 = a2;
  v109 = this;
  v12 = a8;
  v124 = a8;
  LODWORD(v104) = 0;
  RepoMan::Tracer::Tracer(v148, 1, "CRepoIndexer.SelectPackages2");
  try
  {
    if ( !a2 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        160,
        (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
        (unsigned int)"Select packages - invalid build",
        -2147024809,
        8);
    if ( !a3 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        161,
        (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
        (unsigned int)"Select packages - invalid sku.",
        -2147024809,
        8);
    if ( !a4 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        162,
        (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
        (unsigned int)"Select packages - invalid culture.",
        -2147024809,
        8);
    if ( !v12 || *v12 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        163,
        (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
        (unsigned int)"Select packages - invalid packages.",
        -2147024809,
        8);
    v112 = 0;
    v13 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoSKU *, __int64 *))(*(_QWORD *)a3 + 32LL))(a3, &v112);
    RepoMan::RaiseExceptionIfFailed(v13, 166, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v14);
    v107 = (*(__int64 (__fastcall **)(struct IString *))(*(_QWORD *)a4 + 24LL))(a4);
    v106 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v112 + 24LL))(v112);
    v17 = RepoMan::Logger::Message<char const (&)[21],char const *,char const (&)[13],char const *>(
            (unsigned int)&v103,
            v15,
            (unsigned int)&v106,
            v16,
            (__int64)&v107);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v149 + 48LL))(v149, v17);
    v18 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    }
    v108 = *((_QWORD *)this + 9);
    v122 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)a2 + 24LL))(a2);
    v123 = (*(__int64 (__fastcall **)(struct IRepoSKU *))(*(_QWORD *)a3 + 24LL))(a3);
    if ( a5 )
    {
      v19 = (_BYTE *)(*(__int64 (__fastcall **)(struct IString *))(*(_QWORD *)a5 + 24LL))(a5);
      *(_OWORD *)MultiByteStr = 0;
      v132 = 0;
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      std::string::_Construct<1,char const *>(MultiByteStr, v19, v20);
      v21 = (__int64 *)sub_180017630(&v113, MultiByteStr);
      v22 = 3;
      v23 = *v21;
    }
    else
    {
      *(_OWORD *)&v129[8] = 0;
      v21 = (__int64 *)v129;
      v22 = 4;
      v23 = 0;
    }
    v24 = v21[2];
    v21[2] = 0;
    v25 = v21[1];
    v21[1] = 0;
    *v21 = 0;
    v120.m128i_i64[0] = v23;
    v120.m128i_i64[1] = v25;
    v121 = v24;
    if ( (v22 & 4) != 0 )
    {
      v22 &= ~4u;
      std::vector<std::string>::_Tidy(v129);
    }
    if ( (v22 & 2) != 0 )
    {
      v22 &= ~2u;
      std::vector<std::string>::_Tidy(&v113);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v113 = si128;
      v114 = 19937;
    }
    else
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    if ( (v22 & 1) != 0 )
    {
      v22 &= ~1u;
      std::string::_Tidy_deallocate(MultiByteStr);
    }
    v27 = (_BYTE *)(*(__int64 (__fastcall **)(struct IString *))(*(_QWORD *)a4 + 24LL))(a4);
    *(_OWORD *)Block = 0;
    v128 = 0;
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    std::string::_Construct<1,char const *>(Block, v27, v28);
    sub_180017630(&v125, Block);
    if ( v128.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(Block, Block[0]);
    if ( a6 )
    {
      v29 = (_BYTE *)(*(__int64 (__fastcall **)(struct IString *))(*(_QWORD *)a6 + 24LL))(a6);
      *(_OWORD *)MultiByteStr = 0;
      v132 = 0;
      v30 = -1;
      do
        ++v30;
      while ( v29[v30] );
      std::string::_Construct<1,char const *>(MultiByteStr, v29, v30);
      v31 = (__int64 *)sub_180017630(&v113, MultiByteStr);
      v32 = v22 | 0x18;
      v33 = *v31;
    }
    else
    {
      *(_OWORD *)&v129[8] = 0;
      v31 = (__int64 *)v129;
      v32 = v22 | 0x20;
      v33 = 0;
    }
    v34 = v31[2];
    v31[2] = 0;
    v35 = v31[1];
    v31[1] = 0;
    *v31 = 0;
    v118.m128i_i64[0] = v33;
    v118.m128i_i64[1] = v35;
    v119 = v34;
    if ( (v32 & 0x20) != 0 )
    {
      v32 &= ~0x20u;
      std::vector<std::string>::_Tidy(v129);
    }
    if ( (v32 & 0x10) != 0 )
    {
      v32 &= ~0x10u;
      std::vector<std::string>::_Tidy(&v113);
      v113 = si128;
      v114 = 19937;
    }
    if ( (v32 & 8) != 0 )
    {
      v32 &= ~8u;
      std::string::_Tidy_deallocate(MultiByteStr);
    }
    *(_OWORD *)v105 = 0;
    v36 = malloc(0x28u);
    v37 = v36;
    if ( !v36 )
      std::_Xbad_alloc();
    *v36 = v36;
    v36[1] = v36;
    v36[2] = v36;
    *((_WORD *)v36 + 12) = 257;
    v105[0] = v36;
    v38 = _mm_load_si128((const __m128i *)&_xmm);
    v39 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v40 = (_QWORD *)v37[1];
      while ( !*((_BYTE *)v40 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *>>>(
          v105,
          v105,
          v40[2]);
        v41 = v40;
        v40 = (_QWORD *)*v40;
        free(v41);
      }
      v37[1] = v37;
      *v37 = v37;
      v37[2] = v37;
      v105[1] = 0;
      *(_QWORD *)MultiByteStr = &v120;
      *(_QWORD *)&MultiByteStr[8] = &v108;
      v132.m128i_i64[0] = (__int64)&v122;
      v132.m128i_i64[1] = (__int64)&v125;
      v133 = &v123;
      v134 = &a7;
      v135 = v105;
      v136 = (CHAR *)&v118;
      sub_180017704(*(_QWORD *)(v108 + 13280), MultiByteStr);
      v113 = 0u;
      v42 = malloc(0x40u);
      if ( !v42 )
        std::_Xbad_alloc();
      *v42 = v42;
      v42[1] = v42;
      v42[2] = v42;
      *((_WORD *)v42 + 12) = 257;
      v113.m128i_i64[0] = (__int64)v42;
      v43 = *(__int64 **)v105[0];
      v44 = v117;
      while ( !*((_BYTE *)v43 + 25) )
      {
        v45 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v44 + 24LL))(v44);
        v46 = v43[4];
        v140[0] = ___7___Func_impl_no_alloc_V_lambda_1___1____ForEachRowIn_V__Query__0DG_URequiredMediaSourceForPackage_Text_Queries_Meta_RepoMan__V__InputType_U__Column_U__Value_UNumber_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan___J_Meta_RepoMan__U123__45__Meta_RepoMan___KAEB_J___Schema_VSchemaVersions_Tables_Meta_RepoMan__VFamilies_234_VArchitectures_234_VFlavors_234_VCultures_234_VAlgorithms_234_VBuilds_234_VMedia_234_VSKUs_234_VApps_234_VPackages_234_VDigests_234_VHashes_234_VDirectories_234_VPaths_234_VFiles_234_VBlocks_234_VBlockSource_234_VPatches_234_VPackagesToPaths_234_VPackagesToApps_234_VAppsToSKUs_234_VPackageSources_234_VOperations_234_VPackageTasks_234_VFileTasks_234__Meta_RepoMan__QEAA_AV__function___A6AXV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_std___Z_std____QEA_KAEB_J_Z_XV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_6__std__6B_;
        v140[1] = v46;
        v140[2] = v45;
        v141 = 0;
        v142 = v108;
        v143 = v140;
        *(_QWORD *)MultiByteStr = off_1801CFDA8;
        *(_QWORD *)&MultiByteStr[8] = &v113;
        v136 = MultiByteStr;
        std::_Func_class<void,std::function<bool (sqlite3pp::query::rows::getstream &)>>::operator()(v140, MultiByteStr);
        if ( v143 )
        {
          LOBYTE(v47) = v143 != v140;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v143 + 32LL))(v143, v47);
        }
        v48 = (__int64 **)v43[2];
        if ( *((_BYTE *)v48 + 25) )
        {
          for ( i = (__int64 *)v43[1]; !*((_BYTE *)i + 25) && v43 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v43 = i;
          v43 = i;
        }
        else
        {
          v43 = (__int64 *)v43[2];
          for ( j = *v48; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v43 = j;
        }
      }
      v51 = v113.m128i_i64[1] != 0;
      if ( v113.m128i_i64[1] )
      {
        v128 = v39;
        qmemcpy(Block, "required cel", 12);
        HIDWORD(Block[1]) = *(unsigned __int16 *)"ls";
        RepoMan::Logger::CreateValue((unsigned int)&v103, 3, 11, (unsigned int)Block, v113.m128i_i64[1]);
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v149 + 48LL))(v149, &v103);
        v52 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
        }
        if ( v128.m128i_i64[1] > 0xFuLL )
        {
          v53 = Block[0];
          if ( (unsigned __int64)(v128.m128i_i64[1] + 1) >= 0x1000 )
          {
            v53 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v53 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v53);
        }
        v107 = 0;
        v54 = v109;
        v55 = (RepoMan *)(*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)v109 + 8) + 16LL)
                                                                           + 72LL))(
                           *(_QWORD *)(*((_QWORD *)v109 + 8) + 16LL),
                           &v107);
        RepoMan::RaiseExceptionIfFailed(v55, 282, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v56);
        v137 = 0;
        v138 = 0;
        v139 = 15;
        LOBYTE(v137) = 0;
        memset(v129, 0, sizeof(v129));
        v130 = 15;
        v129[0] = 0;
        v57 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v44 + 24LL))(v44);
        v144[0] = ___7___Func_impl_no_alloc_V_lambda_1___1____ForEachRowIn_V__Query__0BL_UIndexedMediaURIForBuild_Text_Queries_Meta_RepoMan__V__InputType_U__Column_U__Value_UNumber_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan___J_Meta_RepoMan___45__Meta_RepoMan___K___Schema_VSchemaVersions_Tables_Meta_RepoMan__VFamilies_234_VArchitectures_234_VFlavors_234_VCultures_234_VAlgorithms_234_VBuilds_234_VMedia_234_VSKUs_234_VApps_234_VPackages_234_VDigests_234_VHashes_234_VDirectories_234_VPaths_234_VFiles_234_VBlocks_234_VBlockSource_234_VPatches_234_VPackagesToPaths_234_VPackagesToApps_234_VAppsToSKUs_234_VPackageSources_234_VOperations_234_VPackageTasks_234_VFileTasks_234__Meta_RepoMan__QEAA_AV__function___A6AXV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_std___Z_std____QEA_K_Z_XV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_6__std__6B_;
        v144[1] = v57;
        v145 = 0;
        v146 = v108;
        v147 = v144;
        *(_QWORD *)MultiByteStr = off_1801CFAB8;
        *(_QWORD *)&MultiByteStr[8] = &v137;
        v132.m128i_i64[0] = (__int64)v129;
        v136 = MultiByteStr;
        std::_Func_class<void,std::function<bool (sqlite3pp::query::rows::getstream &)>>::operator()(v144, MultiByteStr);
        if ( v147 )
        {
          v58 = v144;
          LOBYTE(v58) = v147 != v144;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v147 + 32LL))(v147, v58);
        }
        if ( !v138 || !*(_QWORD *)&v129[16] )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            289,
            (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
            (unsigned int)"undefined name or URI for build",
            -1941503486,
            8);
        v59 = std::string::rfind(v129, &v137);
        if ( v59 == -1 )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            292,
            (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
            (unsigned int)"unable to form URI for cells in distribution",
            -1941503391,
            8);
        v60 = *(__int64 **)v113.m128i_i64[0];
        while ( !*((_BYTE *)v60 + 25) )
        {
          *(_OWORD *)MultiByteStr = 0;
          v132 = 0;
          v61 = v129;
          if ( v130 > 0xF )
            v61 = *(_OWORD **)v129;
          std::string::_Construct<2,char const *>(MultiByteStr, v61, *(unsigned __int64 *)&v129[16]);
          std::string::replace(MultiByteStr, v59, v138, v60 + 4);
          RepoMan::utf8_to_wstring((LPWSTR)Block, MultiByteStr);
          v110 = 0;
          v62 = Block;
          if ( v128.m128i_i64[1] > 7uLL )
            v62 = (void **)Block[0];
          v63 = (RepoMan *)(*(unsigned int (__fastcall **)(_QWORD, void **, __int64 *))(**(_QWORD **)(*((_QWORD *)v54 + 8) + 16LL)
                                                                                      + 40LL))(
                             *(_QWORD *)(*((_QWORD *)v54 + 8) + 16LL),
                             v62,
                             &v110);
          RepoMan::RaiseExceptionIfFailed(v63, 300, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v64);
          v104 = 0;
          v65 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v107 + 32LL))(
                             v107,
                             v110,
                             &v104);
          RepoMan::RaiseExceptionIfFailed(v65, 302, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v66);
          v67 = Block;
          if ( v128.m128i_i64[1] > 7uLL )
            v67 = (void **)Block[0];
          v68 = (*(__int64 (__fastcall **)(RepoMan::CRepoIndexer *, __int64, _QWORD, void **))(*(_QWORD *)v54 + 88LL))(
                  v54,
                  v104,
                  *((unsigned int *)v54 + 20),
                  v67);
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v68, 303, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v69);
          v70 = v104;
          if ( v104 )
          {
            v104 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
          }
          v71 = v110;
          if ( v110 )
          {
            v110 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
          }
          std::wstring::_Tidy_deallocate(Block);
          Block[0] = (void *)19937;
          v128 = v38;
          std::string::_Tidy_deallocate(MultiByteStr);
          v72 = (__int64 **)v60[2];
          if ( *((_BYTE *)v72 + 25) )
          {
            for ( k = (__int64 *)v60[1]; !*((_BYTE *)k + 25) && v60 == (__int64 *)k[2]; k = (__int64 *)k[1] )
              v60 = k;
            v60 = k;
          }
          else
          {
            v60 = (__int64 *)v60[2];
            for ( m = *v72; !*((_BYTE *)m + 25); m = (__int64 *)*m )
              v60 = m;
          }
        }
        v106 = 0;
        v75 = (RepoMan *)(*(unsigned int (__fastcall **)(RepoMan::CRepoIndexer *, __int64 *))(*(_QWORD *)v54 + 40LL))(
                           v54,
                           &v106);
        RepoMan::RaiseExceptionIfFailed(v75, 307, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v76);
        v77 = v106;
        v78 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 24LL);
        v79 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)v117 + 24LL))(v117);
        if ( v78(v77) != v79 )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            308,
            (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
            (unsigned int)"cellular packages build mismatch",
            -1941503390,
            8);
        v80 = v106;
        if ( v106 )
        {
          v106 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        }
        if ( v130 > 0xF )
          std::string::_Deallocate_for_capacity(v129, *(_QWORD *)v129);
        *(_QWORD *)v129 = 19937;
        *(_QWORD *)&v129[16] = 0;
        v130 = 31;
        if ( v139 > 0xF )
          std::string::_Deallocate_for_capacity(&v137, v137);
        *(_QWORD *)&v137 = 19937;
        v138 = 0;
        v139 = 31;
        v81 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        }
      }
      std::_Tree<std::_Tset_traits<RepoMan::Legacy::Descriptor::Package,std::less<RepoMan::Legacy::Descriptor::Package>,std::allocator<RepoMan::Legacy::Descriptor::Package>,0>>::~_Tree<std::_Tset_traits<RepoMan::Legacy::Descriptor::Package,std::less<RepoMan::Legacy::Descriptor::Package>,std::allocator<RepoMan::Legacy::Descriptor::Package>,0>>(&v113);
      if ( !v51 )
        break;
      v37 = v105[0];
    }
    v132 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(MultiByteStr, "packages");
    MultiByteStr[9] = 0;
    *(_WORD *)&MultiByteStr[10] = 0;
    *(_DWORD *)&MultiByteStr[12] = 0;
    RepoMan::Logger::CreateValue((unsigned int)&v103, 3, 11, (unsigned int)MultiByteStr, (__int64)v105[1]);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v149 + 48LL))(v149, &v103);
    v82 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
    }
    std::string::_Tidy_deallocate(MultiByteStr);
    v115 = 0;
    v116 = 0;
    v83 = *(__int64 **)v105[0];
    v84 = v109;
    while ( !*((_BYTE *)v83 + 25) )
    {
      v85 = *(_QWORD *)(*((_QWORD *)v84 + 8) + 16LL);
      v111 = 0;
      v86 = v32 | 0x40;
      LODWORD(v104) = v86;
      v87 = malloc(0x40u);
      if ( !v87 )
        std::_Xbad_alloc();
      v88 = v83[4];
      v89 = v108;
      v87[6] = 1;
      *((_QWORD *)v87 + 7) = 0;
      *(_QWORD *)v87 = &RepoMan::CRepoPackage::`vftable';
      *((_QWORD *)v87 + 1) = &RepoMan::CRepoPackage::`vftable'{for `IRepoPackageInternal'};
      *((_QWORD *)v87 + 2) = &RepoMan::CRepoPackage::`vftable'{for `RepoMan::QIHelper<IRepoInternalChannel>'};
      *((_QWORD *)v87 + 5) = v89;
      *((_QWORD *)v87 + 6) = v88;
      *((_QWORD *)v87 + 4) = v85;
      v111 = v87;
      v90 = (void **)v115.m128i_i64[1];
      if ( v115.m128i_i64[1] == v116 )
      {
        std::vector<RepoMan::ComPtr<IRepoMedia>>::_Emplace_reallocate<RepoMan::ComPtr<IRepoMedia>>(
          (unsigned __int64 *)&v115,
          (_QWORD *)v115.m128i_i64[1],
          &v111);
        v87 = v111;
      }
      else
      {
        *(_QWORD *)v115.m128i_i64[1] = 0;
        if ( v90 != (void **)&v111 )
        {
          *v90 = v87;
          v87 = 0;
        }
        v115.m128i_i64[1] += 8;
      }
      v32 = v86 & 0xFFFFFFBF;
      if ( v87 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v87 + 16LL))(v87);
      v91 = (__int64 **)v83[2];
      if ( *((_BYTE *)v91 + 25) )
      {
        for ( n = (__int64 *)v83[1]; !*((_BYTE *)n + 25) && v83 == (__int64 *)n[2]; n = (__int64 *)n[1] )
          v83 = n;
        v83 = n;
      }
      else
      {
        v83 = (__int64 *)v83[2];
        for ( ii = *v91; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
          v83 = ii;
      }
    }
    v94 = (struct IRepoPackages **)RepoMan::ComPtr<IRepoPackages>::Make<RepoMan::CRepoPackages,std::vector<RepoMan::ComPtr<IRepoPackage>>>(
                                     &v109,
                                     &v115);
    v95 = *v94;
    *v94 = 0;
    *v124 = v95;
    v96 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(RepoMan::CRepoIndexer *))(*(_QWORD *)v96 + 16LL))(v96);
    }
    std::vector<RepoMan::ComPtr<IRepoFileTask>>::_Tidy(&v115);
    v115 = si128;
    v116 = 19937;
    v97 = v105[0];
    v98 = (_QWORD *)*((_QWORD *)v105[0] + 1);
    if ( !*((_BYTE *)v98 + 25) )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *>>>(
          v105,
          v105,
          v98[2]);
        v99 = v98;
        v98 = (_QWORD *)*v98;
        free(v99);
      }
      while ( !*((_BYTE *)v98 + 25) );
      v97 = v105[0];
    }
    free(v97);
    *(__m128i *)v105 = _mm_load_si128((const __m128i *)&_xmm);
    std::vector<std::string>::_Tidy(&v118);
    v118 = si128;
    v119 = 19937;
    std::vector<std::string>::_Tidy(&v125);
    v125 = si128;
    v126 = 19937;
    std::vector<std::string>::_Tidy(&v120);
    v120 = si128;
    v121 = 19937;
    v100 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v148);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\indexer.cpp", (const char *)0x142, v101);
  }
  return result;
}

```

## disassembly

```asm
0x180010c10  mov     rax, rsp
0x180010c13  push    rbx
0x180010c14  push    rsi
0x180010c15  push    rdi
0x180010c16  push    r12
0x180010c18  push    r13
0x180010c1a  push    r14
0x180010c1c  push    r15
0x180010c1e  sub     rsp, 2C0h
0x180010c25  movaps  xmmword ptr [rax-48h], xmm6
0x180010c29  movaps  xmmword ptr [rax-58h], xmm7
0x180010c2d  movaps  xmmword ptr [rax-68h], xmm8
0x180010c32  mov     rax, cs:__security_cookie
0x180010c39  xor     rax, rsp
0x180010c3c  mov     [rsp+2F8h+var_78], rax
0x180010c44  mov     rdi, r9
0x180010c47  mov     rbx, r8
0x180010c4a  mov     r14, rdx
0x180010c4d  mov     [rsp+2F8h+var_240], rdx
0x180010c55  mov     r13, rcx
0x180010c58  mov     [rsp+2F8h+var_290], rcx
0x180010c5d  mov     rsi, [rsp+2F8h+arg_20]
0x180010c65  mov     r12, [rsp+2F8h+arg_28]
0x180010c6d  mov     r15, [rsp+2F8h+arg_38]
0x180010c75  mov     [rsp+2F8h+var_1F8], r15
0x180010c7d  mov     dword ptr [rsp+2F8h+var_2C0], 0
0x180010c85  lea     r8, aCrepoindexerSe; "CRepoIndexer.SelectPackages2"
0x180010c8c  mov     edx, 1
0x180010c91  lea     rcx, [rsp+2F8h+var_A8]
0x180010c99  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x180010c9e  nop
0x180010c9f  test    r14, r14
0x180010ca2  jz      loc_180011C22
0x180010ca8  test    rbx, rbx
0x180010cab  jz      loc_180011C48
0x180010cb1  test    rdi, rdi
0x180010cb4  jz      loc_180011C6E
0x180010cba  test    r15, r15
0x180010cbd  jz      loc_180011D10
0x180010cc3  cmp     qword ptr [r15], 0
0x180010cc7  jnz     loc_180011D10
0x180010ccd  mov     [rsp+2F8h+var_278], 0
0x180010cd9  mov     rax, [rbx]
0x180010cdc  lea     rdx, [rsp+2F8h+var_278]
0x180010ce4  mov     rcx, rbx
0x180010ce7  mov     rax, [rax+20h]
0x180010ceb  call    cs:__guard_dispatch_icall_fptr
0x180010cf1  mov     ecx, eax; this
0x180010cf3  lea     r15, aSrcRepomanSrcR_20; "src\\repoman\\src\\repoman\\indexer.cpp"
0x180010cfa  mov     r8, r15; int
0x180010cfd  mov     edx, 0A6h; int
0x180010d02  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180010d07  mov     rax, [rdi]
0x180010d0a  mov     rcx, rdi
0x180010d0d  mov     rax, [rax+18h]
0x180010d11  call    cs:__guard_dispatch_icall_fptr
0x180010d17  mov     [rsp+2F8h+var_2A0], rax
0x180010d1c  mov     rcx, [rsp+2F8h+var_278]
0x180010d24  mov     rax, [rcx]
0x180010d27  mov     rax, [rax+18h]
0x180010d2b  call    cs:__guard_dispatch_icall_fptr
0x180010d31  mov     [rsp+2F8h+var_2A8], rax
0x180010d36  lea     rax, [rsp+2F8h+var_2A0]
0x180010d3b  mov     [rsp+2F8h+Reserved], rax
0x180010d40  lea     r8, [rsp+2F8h+var_2A8]
0x180010d45  lea     rcx, [rsp+2F8h+var_2C8]
0x180010d4a  call    ??$Message@AEAY0BF@$$CBDPEBDAEAY0N@$$CBDPEBD@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@1@AEAY0BF@$$CBD$$QEAPEBDAEAY0N@$$CBD1@Z; RepoMan::Logger::Message<char const (&)[21],char const *,char const (&)[13],char const *>(char const (&)[21],char const * &&,char const (&)[13],char const * &&)
0x180010d4f  mov     rdx, rax
0x180010d52  mov     r8, [rsp+2F8h+var_80]
0x180010d5a  mov     rcx, [r8]
0x180010d5d  mov     rax, [rcx+30h]
0x180010d61  mov     rcx, r8
0x180010d64  call    cs:__guard_dispatch_icall_fptr
0x180010d6a  nop
0x180010d6b  mov     rcx, [rsp+2F8h+var_2C8]
0x180010d70  test    rcx, rcx
0x180010d73  jz      short loc_180010D8C
0x180010d75  mov     [rsp+2F8h+var_2C8], 0
0x180010d7e  mov     rax, [rcx]
0x180010d81  mov     rax, [rax+8]
0x180010d85  call    cs:__guard_dispatch_icall_fptr
0x180010d8b  nop
0x180010d8c  mov     rax, [r13+48h]
0x180010d90  mov     [rsp+2F8h+var_298], rax
0x180010d95  mov     rax, [r14]
0x180010d98  mov     rcx, r14
0x180010d9b  mov     rax, [rax+18h]
0x180010d9f  call    cs:__guard_dispatch_icall_fptr
0x180010da5  mov     [rsp+2F8h+var_208], rax
0x180010dad  mov     rax, [rbx]
0x180010db0  mov     rcx, rbx
0x180010db3  mov     rax, [rax+18h]
0x180010db7  call    cs:__guard_dispatch_icall_fptr
0x180010dbd  mov     [rsp+2F8h+var_200], rax
0x180010dc5  test    rsi, rsi
0x180010dc8  jz      short loc_180010E34
0x180010dca  mov     rax, [rsi]
0x180010dcd  mov     rcx, rsi
0x180010dd0  mov     rax, [rax+18h]
0x180010dd4  call    cs:__guard_dispatch_icall_fptr
0x180010dda  xorps   xmm0, xmm0
0x180010ddd  movups  xmmword ptr [rsp+2F8h+MultiByteStr], xmm0
0x180010de5  xorps   xmm1, xmm1
0x180010de8  movdqu  [rsp+2F8h+var_180], xmm1
0x180010df1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010df5  xor     esi, esi
0x180010df7  inc     r8
0x180010dfa  cmp     [rax+r8], sil
0x180010dfe  jnz     short loc_180010DF7
0x180010e00  mov     rdx, rax
0x180010e03  lea     rcx, [rsp+2F8h+MultiByteStr]
0x180010e0b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180010e10  nop
0x180010e11  lea     rdx, [rsp+2F8h+MultiByteStr]
0x180010e19  lea     rcx, [rsp+2F8h+var_270]
0x180010e21  call    sub_180017630
0x180010e26  mov     rdx, rax
0x180010e29  mov     r14d, 3
0x180010e2f  mov     r8, [rax]
0x180010e32  jmp     short loc_180010E51
0x180010e34  xorps   xmm0, xmm0
0x180010e37  movdqu  [rsp+2F8h+var_1B0+8], xmm0
0x180010e40  lea     rdx, [rsp+2F8h+var_1B0]
0x180010e48  xor     esi, esi
0x180010e4a  lea     r14d, [rsi+4]
0x180010e4e  mov     r8d, esi
0x180010e51  mov     rcx, [rdx+10h]
0x180010e55  mov     [rdx+10h], rsi
0x180010e59  mov     rax, [rdx+8]
0x180010e5d  mov     [rdx+8], rsi
0x180010e61  mov     [rdx], rsi
0x180010e64  mov     qword ptr [rsp+2F8h+var_220], r8
0x180010e6c  mov     qword ptr [rsp+2F8h+var_220+8], rax
0x180010e74  mov     [rsp+2F8h+var_210], rcx
0x180010e7c  test    r14b, 4
0x180010e80  jz      short loc_180010E93
0x180010e82  and     r14d, 0FFFFFFFBh
0x180010e86  lea     rcx, [rsp+2F8h+var_1B0]
0x180010e8e  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180010e93  test    r14b, 2
0x180010e97  jz      short loc_180010ECB
0x180010e99  and     r14d, 0FFFFFFFDh
0x180010e9d  lea     rcx, [rsp+2F8h+var_270]
0x180010ea5  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180010eaa  movdqa  xmm6, cs:__xmm@0000000000004de10000000000004de1
0x180010eb2  movdqu  [rsp+2F8h+var_270], xmm6
0x180010ebb  mov     r13d, 4DE1h
0x180010ec1  mov     [rsp+2F8h+var_260], r13
0x180010ec9  jmp     short loc_180010ED9
0x180010ecb  mov     r13d, 4DE1h
0x180010ed1  movdqa  xmm6, cs:__xmm@0000000000004de10000000000004de1
0x180010ed9  test    r14b, 1
0x180010edd  jz      short loc_180010EF0
0x180010edf  and     r14d, 0FFFFFFFEh
0x180010ee3  lea     rcx, [rsp+2F8h+MultiByteStr]
0x180010eeb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010ef0  mov     rax, [rdi]
0x180010ef3  mov     rcx, rdi
0x180010ef6  mov     rax, [rax+18h]
0x180010efa  call    cs:__guard_dispatch_icall_fptr
0x180010f00  xorps   xmm0, xmm0
0x180010f03  movups  xmmword ptr [rsp+2F8h+Block], xmm0
0x180010f0b  xorps   xmm1, xmm1
0x180010f0e  movdqu  [rsp+2F8h+var_1C0], xmm1
0x180010f17  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010f1b  inc     r8
0x180010f1e  cmp     [rax+r8], sil
0x180010f22  jnz     short loc_180010F1B
0x180010f24  mov     rdx, rax
0x180010f27  lea     rcx, [rsp+2F8h+Block]
0x180010f2f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180010f34  nop
0x180010f35  lea     rdx, [rsp+2F8h+Block]
0x180010f3d  lea     rcx, [rsp+2F8h+var_1E8]
0x180010f45  call    sub_180017630
0x180010f4a  nop
0x180010f4b  mov     r8, qword ptr [rsp+2F8h+var_1C0+8]
0x180010f53  cmp     r8, 0Fh
0x180010f57  jbe     short loc_180010F6E
0x180010f59  mov     rdx, [rsp+2F8h+Block]
0x180010f61  lea     rcx, [rsp+2F8h+Block]
0x180010f69  call    ?_Deallocate_for_capacity@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CAXAEAV?$allocator@D@2@QEAD_K@Z; std::string::_Deallocate_for_capacity(std::allocator<char> &,char * const,unsigned __int64)
0x180010f6e  test    r12, r12
0x180010f71  jz      short loc_180010FDA
0x180010f73  mov     rax, [r12]
0x180010f77  mov     rcx, r12
0x180010f7a  mov     rax, [rax+18h]
0x180010f7e  call    cs:__guard_dispatch_icall_fptr
0x180010f84  xorps   xmm0, xmm0
0x180010f87  movups  xmmword ptr [rsp+2F8h+MultiByteStr], xmm0
0x180010f8f  xorps   xmm1, xmm1
0x180010f92  movdqu  [rsp+2F8h+var_180], xmm1
0x180010f9b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010f9f  inc     r8
0x180010fa2  cmp     [rax+r8], sil
0x180010fa6  jnz     short loc_180010F9F
0x180010fa8  mov     rdx, rax
0x180010fab  lea     rcx, [rsp+2F8h+MultiByteStr]
0x180010fb3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180010fb8  nop
0x180010fb9  lea     rdx, [rsp+2F8h+MultiByteStr]
0x180010fc1  lea     rcx, [rsp+2F8h+var_270]
0x180010fc9  call    sub_180017630
0x180010fce  mov     rdx, rax
0x180010fd1  or      r14d, 18h
0x180010fd5  mov     r8, [rax]
0x180010fd8  jmp     short loc_180010FF5
0x180010fda  xorps   xmm0, xmm0
0x180010fdd  movdqu  [rsp+2F8h+var_1B0+8], xmm0
0x180010fe6  lea     rdx, [rsp+2F8h+var_1B0]
0x180010fee  or      r14d, 20h
0x180010ff2  mov     r8, rsi
0x180010ff5  mov     rcx, [rdx+10h]
0x180010ff9  mov     [rdx+10h], rsi
0x180010ffd  mov     rax, [rdx+8]
0x180011001  mov     [rdx+8], rsi
0x180011005  mov     [rdx], rsi
0x180011008  mov     qword ptr [rsp+2F8h+var_238], r8
0x180011010  mov     qword ptr [rsp+2F8h+var_238+8], rax
0x180011018  mov     [rsp+2F8h+var_228], rcx
0x180011020  test    r14b, 20h
0x180011024  jz      short loc_180011037
0x180011026  and     r14d, 0FFFFFFDFh
0x18001102a  lea     rcx, [rsp+2F8h+var_1B0]
0x180011032  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180011037  test    r14b, 10h
0x18001103b  jz      short loc_18001105F
0x18001103d  and     r14d, 0FFFFFFEFh
0x180011041  lea     rcx, [rsp+2F8h+var_270]
0x180011049  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18001104e  movdqu  [rsp+2F8h+var_270], xmm6
0x180011057  mov     [rsp+2F8h+var_260], r13
0x18001105f  test    r14b, 8
0x180011063  jz      short loc_180011076
0x180011065  and     r14d, 0FFFFFFF7h
0x180011069  lea     rcx, [rsp+2F8h+MultiByteStr]
0x180011071  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180011076  xorps   xmm0, xmm0
0x180011079  movdqu  xmmword ptr [rsp+2F8h+var_2B8], xmm0
0x18001107f  mov     ecx, 28h ; '('; Size
0x180011084  call    cs:__imp_malloc
0x18001108a  mov     rbx, rax
0x18001108d  test    rax, rax
0x180011090  jz      loc_180011C95
0x180011096  mov     [rax], rax
0x180011099  mov     [rax+8], rax
0x18001109d  mov     [rax+10h], rax
0x1800110a1  mov     word ptr [rax+18h], 101h
0x1800110a7  mov     [rsp+2F8h+var_2B8], rax
0x1800110ac  movdqa  xmm7, cs:__xmm@000000000000000f0000000000000000
0x1800110b4  movdqa  xmm8, cs:__xmm@000000000000000f000000000000000e
0x1800110bd  mov     rdi, [rbx+8]
0x1800110c1  jmp     short loc_1800110E2
0x1800110c3  mov     r8, [rdi+10h]
0x1800110c7  lea     rdx, [rsp+2F8h+var_2B8]
0x1800110cc  lea     rcx, [rsp+2F8h+var_2B8]
0x1800110d1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *>> &,std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *> *)
0x1800110d6  mov     rcx, rdi; Block
0x1800110d9  mov     rdi, [rdi]
0x1800110dc  call    cs:__imp_free
0x1800110e2  cmp     [rdi+19h], sil
0x1800110e6  jz      short loc_1800110C3
0x1800110e8  mov     [rbx+8], rbx
0x1800110ec  mov     [rbx], rbx
0x1800110ef  mov     [rbx+10h], rbx
0x1800110f3  mov     [rsp+2F8h+var_2B8+8], rsi
0x1800110f8  mov     rax, [rsp+2F8h+var_298]
0x1800110fd  lea     rcx, [rsp+2F8h+var_220]
0x180011105  mov     qword ptr [rsp+2F8h+MultiByteStr], rcx
0x18001110d  lea     rcx, [rsp+2F8h+var_298]
0x180011112  mov     qword ptr [rsp+2F8h+MultiByteStr+8], rcx
0x18001111a  lea     rcx, [rsp+2F8h+var_208]
0x180011122  mov     qword ptr [rsp+2F8h+var_180], rcx
0x18001112a  lea     rcx, [rsp+2F8h+var_1E8]
0x180011132  mov     qword ptr [rsp+2F8h+var_180+8], rcx
0x18001113a  lea     rcx, [rsp+2F8h+var_200]
0x180011142  mov     [rsp+2F8h+var_170], rcx
0x18001114a  lea     rcx, [rsp+2F8h+arg_30]
0x180011152  mov     [rsp+2F8h+var_168], rcx
0x18001115a  lea     rcx, [rsp+2F8h+var_2B8]
0x18001115f  mov     [rsp+2F8h+var_160], rcx
0x180011167  lea     rcx, [rsp+2F8h+var_238]
0x18001116f  mov     [rsp+2F8h+var_158], rcx
0x180011177  lea     rdx, [rsp+2F8h+MultiByteStr]
0x18001117f  mov     rcx, [rax+33E0h]
0x180011186  call    sub_180017704
0x18001118b  mov     qword ptr [rsp+2F8h+var_270], rsi
0x180011193  mov     qword ptr [rsp+2F8h+var_270+8], rsi
0x18001119b  mov     ecx, 40h ; '@'; Size
0x1800111a0  call    cs:__imp_malloc
0x1800111a6  test    rax, rax
0x1800111a9  jz      loc_180011C9B
0x1800111af  mov     [rax], rax
0x1800111b2  mov     [rax+8], rax
0x1800111b6  mov     [rax+10h], rax
0x1800111ba  mov     word ptr [rax+18h], 101h
0x1800111c0  mov     qword ptr [rsp+2F8h+var_270], rax
0x1800111c8  mov     rbx, [rsp+2F8h+var_2B8]
0x1800111cd  mov     rbx, [rbx]
0x1800111d0  mov     rdi, [rsp+2F8h+var_240]
  ... truncated ...
```
