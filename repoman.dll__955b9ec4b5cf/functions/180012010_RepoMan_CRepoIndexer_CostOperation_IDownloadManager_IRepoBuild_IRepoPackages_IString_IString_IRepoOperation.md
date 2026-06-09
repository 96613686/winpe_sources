# RepoMan::CRepoIndexer::CostOperation(IDownloadManager *,IRepoBuild *,IRepoPackages *,IString *,IString *,IRepoOperation * *)

- ea: `0x180012010`
- end: `0x180012b45`
- name: `?CostOperation@CRepoIndexer@RepoMan@@UEAAJPEAUIDownloadManager@@PEAUIRepoBuild@@PEAUIRepoPackages@@PEAUIString@@3PEAPEAUIRepoOperation@@@Z`
- size: `2869`
- prototype: `__int64 __fastcall(RepoMan::CRepoIndexer *__hidden this, struct IDownloadManager *, struct IRepoBuild *, struct IRepoPackages *, struct IString *, struct IString *, struct IRepoOperation **)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180002874`
- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008770`
- `0x18000b088`
- `0x180012010`
- `0x1800136dc`
- `0x180013b14`
- `0x180018188`
- `0x1800186b4`
- `0x180018b74`
- `0x180019374`
- `0x18001a978`
- `0x18001aa08`
- `0x18001bd40`
- `0x180024a68`
- `0x180024b44`
- `0x180026ee8`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x180031e14`
- `0x18018aed8`
- `0x180198f88`
- `0x18019a840`
- `0x18019a984`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001277e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001281a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001297c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800129d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180012a39`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180012aa3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001277e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001281a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001297c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800129d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180012a39`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180012aa3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012777`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012810`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800129cb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012a32`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012a9c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012777`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012810`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800129cb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012a32`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180012a9c`

## string_xrefs

- `0x1800126a4`: `tasks`
- `0x18001282e`: `Remove dupe file tasks2`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall RepoMan::CRepoIndexer::CostOperation(
        RepoMan::CRepoIndexer *this,
        struct IDownloadManager *a2,
        struct IRepoBuild *a3,
        struct IRepoPackages *a4,
        struct IString *a5,
        struct IString *a6,
        struct IRepoOperation **a7)
{
  struct IRepoOperation **v11; // r12
  RepoMan *v12; // rcx
  const char *v13; // r9
  RepoMan *v14; // rcx
  const char *v15; // r9
  RepoMan *v16; // rcx
  const char *v17; // r9
  __int64 v18; // rax
  unsigned int v19; // eax
  const char *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // r8
  __int64 v24; // rdx
  unsigned __int64 v25; // r8
  __int64 v26; // rax
  RepoMan *v27; // rcx
  const char *v28; // r9
  RepoMan *v29; // rcx
  const char *v30; // r9
  __int64 v31; // rax
  unsigned int v32; // eax
  const char *v33; // r9
  unsigned int v34; // eax
  const char *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rdx
  RepoMan *v41; // rcx
  const char *v42; // r9
  unsigned int v43; // eax
  const char *v44; // r9
  unsigned int v45; // eax
  const char *v46; // r9
  unsigned int v47; // eax
  __int64 v48; // rcx
  void *v49; // rcx
  __int64 v50; // rcx
  char *v51; // rbx
  char *v52; // r14
  __int64 v53; // rcx
  char *v54; // rcx
  struct IRepoOperation *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  void *v58; // rbx
  void *v59; // rcx
  __m128i v60; // xmm0
  void *v61; // rcx
  void *v62; // rcx
  __int64 v63; // rcx
  int v64; // r8d
  __int64 result; // rax
  __int64 v66; // [rsp+30h] [rbp-2D8h] BYREF
  int v67; // [rsp+38h] [rbp-2D0h] BYREF
  _QWORD v68[2]; // [rsp+40h] [rbp-2C8h] BYREF
  __int64 v69; // [rsp+50h] [rbp-2B8h] BYREF
  __int64 v70; // [rsp+58h] [rbp-2B0h] BYREF
  struct IRepoOperation *v71; // [rsp+60h] [rbp-2A8h] BYREF
  void *v72[2]; // [rsp+68h] [rbp-2A0h] BYREF
  __int64 *v73; // [rsp+78h] [rbp-290h]
  __int64 v74; // [rsp+80h] [rbp-288h] BYREF
  void *v75; // [rsp+88h] [rbp-280h] BYREF
  __int64 v76; // [rsp+90h] [rbp-278h] BYREF
  __int64 v77; // [rsp+98h] [rbp-270h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-268h] BYREF
  void *v79[2]; // [rsp+A8h] [rbp-260h] BYREF
  __int64 v80; // [rsp+B8h] [rbp-250h]
  char v81[16]; // [rsp+C0h] [rbp-248h] BYREF
  char v82[8]; // [rsp+D0h] [rbp-238h] BYREF
  char v83[128]; // [rsp+D8h] [rbp-230h] BYREF
  _QWORD v84[13]; // [rsp+158h] [rbp-1B0h] BYREF
  void *Block[2]; // [rsp+1C0h] [rbp-148h] BYREF
  __m128i si128; // [rsp+1D0h] [rbp-138h]
  void **v87; // [rsp+1E0h] [rbp-128h]
  __int64 *v88; // [rsp+1E8h] [rbp-120h]
  __int64 *v89; // [rsp+1F0h] [rbp-118h]
  void **v90; // [rsp+1F8h] [rbp-110h]
  void **v91; // [rsp+200h] [rbp-108h]
  void *v92[2]; // [rsp+208h] [rbp-100h] BYREF
  __m128i v93; // [rsp+218h] [rbp-F0h]
  void *v94[2]; // [rsp+228h] [rbp-E0h] BYREF
  __m128i v95; // [rsp+238h] [rbp-D0h]
  _QWORD v96[2]; // [rsp+250h] [rbp-B8h] BYREF
  int v97; // [rsp+260h] [rbp-A8h]
  __int64 v98; // [rsp+268h] [rbp-A0h]
  _QWORD *v99; // [rsp+288h] [rbp-80h]
  _BYTE v100[40]; // [rsp+290h] [rbp-78h] BYREF
  __int64 v101; // [rsp+2B8h] [rbp-50h]

  v11 = a7;
  RepoMan::Tracer::Tracer(v100, 2, "CRepoIndexer.CostOperation");
  try
  {
    if ( !a2 || !a3 || !a4 || !a5 || !a6 || !v11 || *v11 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        386,
        (unsigned int)"src\\repoman\\src\\repoman\\indexer.cpp",
        (unsigned int)"bad parameter",
        -2147024809,
        8);
    v76 = 0;
    v12 = (RepoMan *)((unsigned int (__fastcall *)(struct IDownloadManager *, __int64 *))a2->lpVtbl->Download)(a2, &v76);
    RepoMan::RaiseExceptionIfFailed(v12, 389, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v13);
    *(_OWORD *)v79 = 0;
    v80 = 0;
    v67 = 0;
    v14 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoPackages *, int *))(*(_QWORD *)a4 + 40LL))(a4, &v67);
    RepoMan::RaiseExceptionIfFailed(v14, 393, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v15);
    while ( v67 )
    {
      v68[0] = 0;
      v16 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoPackages *, _QWORD *))(*(_QWORD *)a4 + 32LL))(
                         a4,
                         v68);
      RepoMan::RaiseExceptionIfFailed(v16, 397, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v17);
      v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v68[0] + 24LL))(v68[0]);
      v66 = v18;
      if ( v79[1] == (void *)v80 )
      {
        std::vector<__int64>::_Emplace_reallocate<__int64 const &>(v79, v79[1], &v66);
      }
      else
      {
        *(_QWORD *)v79[1] = v18;
        v79[1] = (char *)v79[1] + 8;
      }
      v19 = (*(__int64 (__fastcall **)(struct IRepoPackages *, int *))(*(_QWORD *)a4 + 48LL))(a4, &v67);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v19, 399, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v20);
      v21 = v68[0];
      if ( v68[0] )
      {
        v68[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    v22 = *((_QWORD *)this + 9) + 1056LL;
    *(_OWORD *)v94 = 0;
    v95 = 0;
    v23 = *(_QWORD *)(v22 + 16);
    if ( *(_QWORD *)(v22 + 24) > 0xFu )
      v22 = *(_QWORD *)v22;
    std::string::_Construct<2,char const *>(v94, (_OWORD *)v22, v23);
    v24 = *((_QWORD *)this + 9) + 552LL;
    *(_OWORD *)v92 = 0;
    v93 = 0;
    v25 = *(_QWORD *)(v24 + 16);
    if ( *(_QWORD *)(v24 + 24) > 0xFu )
      v24 = *(_QWORD *)v24;
    std::string::_Construct<2,char const *>(v92, (_OWORD *)v24, v25);
    v70 = 0;
    v77 = (*(__int64 (__fastcall **)(struct IRepoBuild *))(*(_QWORD *)a3 + 24LL))(a3);
    v75 = 0;
    v26 = *((_QWORD *)this + 9);
    Block[0] = v94;
    Block[1] = &v76;
    si128.m128i_i64[0] = (__int64)&a5;
    si128.m128i_i64[1] = (__int64)&a6;
    v87 = &v75;
    v88 = &v77;
    v89 = &v70;
    v90 = v92;
    v91 = v79;
    sub_180018188(*(_QWORD *)(v26 + 13280), Block);
    v74 = 0;
    v27 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoBuild *, __int64 *))(*(_QWORD *)a3 + 32LL))(a3, &v74);
    RepoMan::RaiseExceptionIfFailed(v27, 434, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v28);
    v69 = 0;
    v29 = (RepoMan *)(*(unsigned int (__fastcall **)(RepoMan::CRepoIndexer *, __int64, __int64 *))(*(_QWORD *)this + 64LL))(
                       this,
                       v74,
                       &v69);
    RepoMan::RaiseExceptionIfFailed(v29, 436, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v30);
    v78 = 0;
    if ( v69 )
    {
      v32 = ((__int64 (__fastcall *)(struct IDownloadManager *))a2->lpVtbl[1].QueryInterface)(a2);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v32, 460, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v33);
      v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 24LL))(v69);
      v68[0] = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v69 + 56LL))(v69, v68);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v34, 463, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v35);
      v66 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v68[0] + 24LL))(v68[0]);
      v36 = *((_QWORD *)this + 9);
      Block[0] = &v70;
      Block[1] = &v78;
      si128.m128i_i64[0] = (__int64)this;
      si128.m128i_i64[1] = (__int64)&v66;
      v87 = (void **)&v77;
      sub_180018B74(*(_QWORD *)(v36 + 13280), Block);
      v37 = v68[0];
      if ( v68[0] )
      {
        v68[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
    else
    {
      v31 = *((_QWORD *)this + 9);
      v72[0] = &v70;
      v72[1] = this;
      v73 = &v77;
      sub_1800186B4(*(_QWORD *)(v31 + 13280), v72);
    }
    v38 = *(_QWORD *)(*((_QWORD *)this + 9) + 13280LL);
    v72[0] = this;
    v72[1] = &v70;
    v73 = &v78;
    sub_180019374(v38, v72);
    v66 = *((_QWORD *)this + 9);
    v68[0] = *(_QWORD *)(*((_QWORD *)this + 8) + 16LL);
    __((unsigned int)&v71, (unsigned int)v68, (unsigned int)&v66, (unsigned int)&v75, (__int64)this + 16);
    *(_OWORD *)v72 = 0;
    v73 = 0;
    v39 = *((_QWORD *)this + 9);
    v96[0] = ___7___Func_impl_no_alloc_V_lambda_1___1____ForEachRowIn_V__Query__0DO_UTasksForOperation_Text_Queries_Meta_RepoMan__V__InputType_U__Column_U__Value_UNumber_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan___J_Meta_RepoMan___45__Meta_RepoMan__AEA_J___Schema_VSchemaVersions_Tables_Meta_RepoMan__VFamilies_234_VArchitectures_234_VFlavors_234_VCultures_234_VAlgorithms_234_VBuilds_234_VMedia_234_VSKUs_234_VApps_234_VPackages_234_VDigests_234_VHashes_234_VDirectories_234_VPaths_234_VFiles_234_VBlocks_234_VBlockSource_234_VPatches_234_VPackagesToPaths_234_VPackagesToApps_234_VAppsToSKUs_234_VPackageSources_234_VOperations_234_VPackageTasks_234_VFileTasks_234__Meta_RepoMan__QEAA_AV__function___A6AXV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_std___Z_std__AEA_J_Z_XV__function___A6A_NAEAVgetstream_rows_query_sqlite3pp___Z_6__std__6B_;
    v96[1] = v70;
    v97 = 0;
    v98 = v39;
    v99 = v96;
    Block[0] = off_1801CFC70;
    Block[1] = this;
    si128.m128i_i64[0] = (__int64)v72;
    v90 = Block;
    std::_Func_class<void,std::function<bool (sqlite3pp::query::rows::getstream &)>>::operator()(v96, Block);
    if ( v99 )
    {
      v40 = v96;
      LOBYTE(v40) = v99 != v96;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v99 + 32LL))(v99, v40);
    }
    RepoMan::ComPtr<IRepoFileTasks>::Make<RepoMan::CRepoFileTasks,std::vector<RepoMan::ComPtr<IRepoFileTask>>>(v68, v72);
    if ( !*((_DWORD *)this + 21) )
    {
      v41 = (RepoMan *)((unsigned int (__fastcall *)(struct IDownloadManager *, struct IRepoOperation *, _QWORD))a2->lpVtbl[1].Release)(
                         a2,
                         v71,
                         v68[0]);
      RepoMan::RaiseExceptionIfFailed(v41, 758, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v42);
    }
    v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)v68[0] + 64LL))(
            v68[0],
            *((_QWORD *)this + 9),
            1);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v43, 762, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v44);
    v45 = (*(__int64 (__fastcall **)(struct IRepoOperation *, __int64, struct IDownloadManager *))(*(_QWORD *)v71 + 88LL))(
            v71,
            1,
            a2);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v45, 763, (int)"src\\repoman\\src\\repoman\\indexer.cpp", v46);
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LODWORD(Block[0]) = *(_DWORD *)"tasks";
    WORD2(Block[0]) = (unsigned __int8)aTasks[4];
    v47 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v68[0] + 56LL))(v68[0]);
    RepoMan::Logger::CreateValue((unsigned int)&v66, 3, 11, (unsigned int)Block, v47);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v101 + 48LL))(v101, &v66);
    v48 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
    }
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v49 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v49 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v49 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v49);
    }
    v50 = v68[0];
    if ( v68[0] )
    {
      v68[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = (char *)v72[0];
    if ( v72[0] )
    {
      v52 = (char *)v72[1];
      if ( v72[0] != v72[1] )
      {
        do
        {
          v53 = *(_QWORD *)v51;
          if ( *(_QWORD *)v51 )
          {
            *(_QWORD *)v51 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          }
          v51 += 8;
        }
        while ( v51 != v52 );
        v51 = (char *)v72[0];
      }
      v54 = v51;
      if ( (((char *)v73 - v51) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
      {
        v51 = (char *)*((_QWORD *)v51 - 1);
        if ( (unsigned __int64)(v54 - v51 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v51);
    }
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v81);
    std::operator<<<std::char_traits<char>>((__int64)v82, (__int64)"Remove dupe file tasks2");
    std::stringbuf::str(v83, Block);
    RepoMan::Logger::CreateValue((unsigned int)&v66, 1, 8, (unsigned int)Block, 0);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v84);
    v84[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v84);
    v68[0] = &v66;
    v68[1] = &v67;
    RepoMan::Logger::WriteEvent(1, v68);
    `eh vector destructor iterator'(
      &v66,
      8u,
      1u,
      RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
    RepoMan::CRepository::CacheOperation(*((_QWORD *)this + 8), &v71);
    v55 = v71;
    v71 = 0;
    *v11 = v55;
    v56 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v75;
    if ( v75 )
    {
      __1__tuple_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UInstallFolder_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UDownloadFolder_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UState_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23__std__QEAA_XZ(v75);
      free(v58);
    }
    v75 = (void *)19937;
    if ( v93.m128i_i64[1] > 0xFuLL )
    {
      v59 = v92[0];
      if ( (unsigned __int64)(v93.m128i_i64[1] + 1) >= 0x1000 )
      {
        v59 = (void *)*((_QWORD *)v92[0] - 1);
        if ( (unsigned __int64)((char *)v92[0] - (char *)v59 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v59);
    }
    v92[0] = (void *)19937;
    v60 = _mm_load_si128((const __m128i *)&_xmm);
    v93 = v60;
    if ( v95.m128i_i64[1] > 0xFuLL )
    {
      v61 = v94[0];
      if ( (unsigned __int64)(v95.m128i_i64[1] + 1) >= 0x1000 )
      {
        v61 = (void *)*((_QWORD *)v94[0] - 1);
        if ( (unsigned __int64)((char *)v94[0] - (char *)v61 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v61);
      v60 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v94[0] = (void *)19937;
    v95 = v60;
    v62 = v79[0];
    if ( v79[0] )
    {
      if ( ((v80 - (unsigned __int64)v79[0]) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
      {
        v62 = (void *)*((_QWORD *)v79[0] - 1);
        if ( (unsigned __int64)((char *)v79[0] - (char *)v62 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v62);
    }
    *(__m128i *)v79 = _mm_load_si128((const __m128i *)&_xmm);
    v80 = 19937;
    v63 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v100);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\indexer.cpp", (const char *)0x304, v64);
  }
  return result;
}

```

## disassembly

```asm
0x180012010  mov     r11, rsp
0x180012013  push    rbx
0x180012014  push    rsi
0x180012015  push    rdi
0x180012016  push    r12
0x180012018  push    r13
0x18001201a  push    r14
0x18001201c  push    r15
0x18001201e  sub     rsp, 2D0h
0x180012025  mov     rax, cs:__security_cookie
0x18001202c  xor     rax, rsp
0x18001202f  mov     [rsp+308h+var_48], rax
0x180012037  mov     rsi, r9
0x18001203a  mov     r15, r8
0x18001203d  mov     r14, rdx
0x180012040  mov     rdi, rcx
0x180012043  mov     r12, [rsp+308h+arg_30]
0x18001204b  xor     r13d, r13d
0x18001204e  lea     r8, aCrepoindexerCo; "CRepoIndexer.CostOperation"
0x180012055  lea     edx, [r13+2]
0x180012059  lea     rcx, [r11-78h]
0x18001205d  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x180012062  nop
0x180012063  test    r14, r14
0x180012066  jz      loc_180012B1D
0x18001206c  test    r15, r15
0x18001206f  jz      loc_180012B1D
0x180012075  test    rsi, rsi
0x180012078  jz      loc_180012B1D
0x18001207e  cmp     [rsp+308h+arg_20], r13
0x180012086  jz      loc_180012B1D
0x18001208c  cmp     [rsp+308h+arg_28], r13
0x180012094  jz      loc_180012B1D
0x18001209a  test    r12, r12
0x18001209d  jz      loc_180012B1D
0x1800120a3  cmp     [r12], r13
0x1800120a7  jnz     loc_180012B1D
0x1800120ad  mov     [rsp+308h+var_278], r13
0x1800120b5  mov     rax, [r14]
0x1800120b8  lea     rdx, [rsp+308h+var_278]
0x1800120c0  mov     rcx, r14
0x1800120c3  mov     rax, [rax+18h]
0x1800120c7  call    cs:__guard_dispatch_icall_fptr
0x1800120cd  mov     ecx, eax; this
0x1800120cf  lea     rbx, aSrcRepomanSrcR_20; "src\\repoman\\src\\repoman\\indexer.cpp"
0x1800120d6  mov     r8, rbx; int
0x1800120d9  mov     edx, 185h; int
0x1800120de  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800120e3  xorps   xmm0, xmm0
0x1800120e6  movdqu  xmmword ptr [rsp+308h+var_260], xmm0
0x1800120ef  mov     [rsp+308h+var_250], r13
0x1800120f7  mov     [rsp+308h+var_2D0], r13d
0x1800120fc  mov     rax, [rsi]
0x1800120ff  lea     rdx, [rsp+308h+var_2D0]
0x180012104  mov     rcx, rsi
0x180012107  mov     rax, [rax+28h]
0x18001210b  call    cs:__guard_dispatch_icall_fptr
0x180012111  mov     ecx, eax; this
0x180012113  mov     r8, rbx; int
0x180012116  mov     edx, 189h; int
0x18001211b  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180012120  cmp     [rsp+308h+var_2D0], r13d
0x180012125  jz      loc_1800121E7
0x18001212b  mov     [rsp+308h+var_2C8], r13
0x180012130  mov     rax, [rsi]
0x180012133  lea     rdx, [rsp+308h+var_2C8]
0x180012138  mov     rcx, rsi
0x18001213b  mov     rax, [rax+20h]
0x18001213f  call    cs:__guard_dispatch_icall_fptr
0x180012145  mov     ecx, eax; this
0x180012147  mov     r8, rbx; int
0x18001214a  mov     edx, 18Dh; int
0x18001214f  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180012154  mov     rcx, [rsp+308h+var_2C8]
0x180012159  mov     rax, [rcx]
0x18001215c  mov     rax, [rax+18h]
0x180012160  call    cs:__guard_dispatch_icall_fptr
0x180012166  mov     [rsp+308h+var_2D8], rax
0x18001216b  mov     rdx, [rsp+308h+var_260+8]
0x180012173  cmp     rdx, [rsp+308h+var_250]
0x18001217b  jz      short loc_18001218B
0x18001217d  mov     [rdx], rax
0x180012180  add     [rsp+308h+var_260+8], 8
0x180012189  jmp     short loc_18001219D
0x18001218b  lea     r8, [rsp+308h+var_2D8]
0x180012190  lea     rcx, [rsp+308h+var_260]
0x180012198  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x18001219d  mov     rax, [rsi]
0x1800121a0  lea     rdx, [rsp+308h+var_2D0]
0x1800121a5  mov     rcx, rsi
0x1800121a8  mov     rax, [rax+30h]
0x1800121ac  call    cs:__guard_dispatch_icall_fptr
0x1800121b2  mov     ecx, eax; this
0x1800121b4  mov     r8, rbx; int
0x1800121b7  mov     edx, 18Fh; int
0x1800121bc  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800121c1  nop
0x1800121c2  mov     rcx, [rsp+308h+var_2C8]
0x1800121c7  test    rcx, rcx
0x1800121ca  jz      loc_180012120
0x1800121d0  mov     [rsp+308h+var_2C8], r13
0x1800121d5  mov     rax, [rcx]
0x1800121d8  mov     rax, [rax+10h]
0x1800121dc  call    cs:__guard_dispatch_icall_fptr
0x1800121e2  jmp     loc_180012120
0x1800121e7  mov     rdx, [rdi+48h]
0x1800121eb  add     rdx, 420h
0x1800121f2  xorps   xmm0, xmm0
0x1800121f5  movups  xmmword ptr [rsp+308h+var_E0], xmm0
0x1800121fd  xorps   xmm1, xmm1
0x180012200  movdqu  [rsp+308h+var_D0], xmm1
0x180012209  mov     r8, [rdx+10h]
0x18001220d  cmp     qword ptr [rdx+18h], 0Fh
0x180012212  jbe     short loc_180012217
0x180012214  mov     rdx, [rdx]
0x180012217  lea     rcx, [rsp+308h+var_E0]
0x18001221f  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180012224  nop
0x180012225  mov     rdx, [rdi+48h]
0x180012229  add     rdx, 228h
0x180012230  xorps   xmm0, xmm0
0x180012233  movups  xmmword ptr [rsp+308h+var_100], xmm0
0x18001223b  xorps   xmm1, xmm1
0x18001223e  movdqu  [rsp+308h+var_F0], xmm1
0x180012247  mov     r8, [rdx+10h]
0x18001224b  cmp     qword ptr [rdx+18h], 0Fh
0x180012250  jbe     short loc_180012255
0x180012252  mov     rdx, [rdx]
0x180012255  lea     rcx, [rsp+308h+var_100]
0x18001225d  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180012262  nop
0x180012263  mov     [rsp+308h+var_2B0], r13
0x180012268  mov     rax, [r15]
0x18001226b  mov     rcx, r15
0x18001226e  mov     rax, [rax+18h]
0x180012272  call    cs:__guard_dispatch_icall_fptr
0x180012278  mov     [rsp+308h+var_270], rax
0x180012280  mov     [rsp+308h+var_280], r13
0x180012288  mov     rax, [rdi+48h]
0x18001228c  lea     rcx, [rsp+308h+var_E0]
0x180012294  mov     [rsp+308h+Block], rcx
0x18001229c  lea     rcx, [rsp+308h+var_278]
0x1800122a4  mov     [rsp+308h+Block+8], rcx
0x1800122ac  lea     rcx, [rsp+308h+arg_20]
0x1800122b4  mov     qword ptr [rsp+308h+var_138], rcx
0x1800122bc  lea     rcx, [rsp+308h+arg_28]
0x1800122c4  mov     qword ptr [rsp+308h+var_138+8], rcx
0x1800122cc  lea     rcx, [rsp+308h+var_280]
0x1800122d4  mov     [rsp+308h+var_128], rcx
0x1800122dc  lea     rcx, [rsp+308h+var_270]
0x1800122e4  mov     [rsp+308h+var_120], rcx
0x1800122ec  lea     rcx, [rsp+308h+var_2B0]
0x1800122f1  mov     [rsp+308h+var_118], rcx
0x1800122f9  lea     rcx, [rsp+308h+var_100]
0x180012301  mov     [rsp+308h+var_110], rcx
0x180012309  lea     rcx, [rsp+308h+var_260]
0x180012311  mov     [rsp+308h+var_108], rcx
0x180012319  lea     rdx, [rsp+308h+Block]
0x180012321  mov     rcx, [rax+33E0h]
0x180012328  call    sub_180018188
0x18001232d  mov     [rsp+308h+var_288], r13
0x180012335  mov     rax, [r15]
0x180012338  lea     rdx, [rsp+308h+var_288]
0x180012340  mov     rcx, r15
0x180012343  mov     rax, [rax+20h]
0x180012347  call    cs:__guard_dispatch_icall_fptr
0x18001234d  mov     ecx, eax; this
0x18001234f  mov     r8, rbx; int
0x180012352  mov     edx, 1B2h; int
0x180012357  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18001235c  mov     [rsp+308h+var_2B8], r13
0x180012361  mov     rax, [rdi]
0x180012364  lea     r8, [rsp+308h+var_2B8]
0x180012369  mov     rdx, [rsp+308h+var_288]
0x180012371  mov     rcx, rdi
0x180012374  mov     rax, [rax+40h]
0x180012378  call    cs:__guard_dispatch_icall_fptr
0x18001237e  mov     ecx, eax; this
0x180012380  mov     r8, rbx; int
0x180012383  mov     edx, 1B4h; int
0x180012388  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18001238d  mov     [rsp+308h+var_268], r13
0x180012395  mov     rdx, [rsp+308h+var_2B8]
0x18001239a  test    rdx, rdx
0x18001239d  jnz     short loc_1800123D5
0x18001239f  mov     rax, [rdi+48h]
0x1800123a3  lea     rcx, [rsp+308h+var_2B0]
0x1800123a8  mov     [rsp+308h+var_2A0], rcx
0x1800123ad  mov     [rsp+308h+var_2A0+8], rdi
0x1800123b2  lea     rcx, [rsp+308h+var_270]
0x1800123ba  mov     [rsp+308h+var_290], rcx
0x1800123bf  lea     rdx, [rsp+308h+var_2A0]
0x1800123c4  mov     rcx, [rax+33E0h]
0x1800123cb  call    sub_1800186B4
0x1800123d0  jmp     loc_1800124C7
0x1800123d5  mov     rax, [r14]
0x1800123d8  mov     rcx, r14
0x1800123db  mov     rax, [rax+20h]
0x1800123df  call    cs:__guard_dispatch_icall_fptr
0x1800123e5  mov     ecx, eax; this
0x1800123e7  mov     r8, rbx; int
0x1800123ea  mov     edx, 1CCh; int
0x1800123ef  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800123f4  mov     rcx, [rsp+308h+var_2B8]
0x1800123f9  mov     rax, [rcx]
0x1800123fc  mov     rax, [rax+18h]
0x180012400  call    cs:__guard_dispatch_icall_fptr
0x180012406  mov     [rsp+308h+var_268], rax
0x18001240e  mov     [rsp+308h+var_2C8], r13
0x180012413  mov     rcx, [rsp+308h+var_2B8]
0x180012418  mov     rax, [rcx]
0x18001241b  lea     rdx, [rsp+308h+var_2C8]
0x180012420  mov     rax, [rax+38h]
0x180012424  call    cs:__guard_dispatch_icall_fptr
0x18001242a  mov     ecx, eax; this
0x18001242c  mov     r8, rbx; int
0x18001242f  mov     edx, 1CFh; int
0x180012434  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180012439  mov     rcx, [rsp+308h+var_2C8]
0x18001243e  mov     rax, [rcx]
0x180012441  mov     rax, [rax+18h]
0x180012445  call    cs:__guard_dispatch_icall_fptr
0x18001244b  mov     [rsp+308h+var_2D8], rax
0x180012450  mov     rax, [rdi+48h]
0x180012454  lea     rcx, [rsp+308h+var_2B0]
0x180012459  mov     [rsp+308h+Block], rcx
0x180012461  lea     rcx, [rsp+308h+var_268]
0x180012469  mov     [rsp+308h+Block+8], rcx
0x180012471  mov     qword ptr [rsp+308h+var_138], rdi
0x180012479  lea     rcx, [rsp+308h+var_2D8]
0x18001247e  mov     qword ptr [rsp+308h+var_138+8], rcx
0x180012486  lea     rcx, [rsp+308h+var_270]
0x18001248e  mov     [rsp+308h+var_128], rcx
0x180012496  lea     rdx, [rsp+308h+Block]
0x18001249e  mov     rcx, [rax+33E0h]
0x1800124a5  call    sub_180018B74
0x1800124aa  nop
0x1800124ab  mov     rcx, [rsp+308h+var_2C8]
0x1800124b0  test    rcx, rcx
0x1800124b3  jz      short loc_1800124C7
0x1800124b5  mov     [rsp+308h+var_2C8], r13
0x1800124ba  mov     rax, [rcx]
0x1800124bd  mov     rax, [rax+10h]
0x1800124c1  call    cs:__guard_dispatch_icall_fptr
0x1800124c7  mov     rax, [rdi+48h]
0x1800124cb  mov     rcx, [rax+33E0h]
0x1800124d2  mov     [rsp+308h+var_2A0], rdi
0x1800124d7  lea     rax, [rsp+308h+var_2B0]
0x1800124dc  mov     [rsp+308h+var_2A0+8], rax
0x1800124e1  lea     rax, [rsp+308h+var_268]
0x1800124e9  mov     [rsp+308h+var_290], rax
0x1800124ee  lea     rdx, [rsp+308h+var_2A0]
0x1800124f3  call    sub_180019374
0x1800124f8  mov     rax, [rdi+48h]
0x1800124fc  mov     [rsp+308h+var_2D8], rax
0x180012501  mov     rax, [rdi+40h]
0x180012505  mov     rcx, [rax+10h]
0x180012509  mov     [rsp+308h+var_2C8], rcx
0x18001250e  lea     rax, [rdi+10h]
0x180012512  mov     [rsp+308h+Reserved], rax
0x180012517  lea     r9, [rsp+308h+var_280]
0x18001251f  lea     r8, [rsp+308h+var_2D8]
0x180012524  lea     rdx, [rsp+308h+var_2C8]
0x180012529  lea     rcx, [rsp+308h+var_2A8]
0x18001252e  call    ??@8d1d15e8437f4c607d7eb167448a7711@
0x180012533  nop
0x180012534  xorps   xmm0, xmm0
0x180012537  movdqu  xmmword ptr [rsp+308h+var_2A0], xmm0
0x18001253d  mov     [rsp+308h+var_290], r13
0x180012542  mov     rcx, [rdi+48h]
0x180012546  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???$ForEachRowIn@V?$Query@$0DO@UTasksForOperation@Text@Queries@Meta@RepoMan@@V?$InputType@U?$Column@U?$Value@UNumber@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@_J@Meta@RepoMan@@@45@@Meta@RepoMan@@AEA_J@?$Schema@VSchemaVersions@Tables@Meta@RepoMan@@VFamilies@234@VArchitectures@234@VFlavors@234@VCultures@234@VAlgorithms@234@VBuilds@234@VMedia@234@VSKUs@234@VApps@234@VPackages@234@VDigests@234@VHashes@234@VDirectories@234@VPaths@234@VFiles@234@VBlocks@234@VBlockSource@234@VPatches@234@VPackagesToPaths@234@VPackagesToApps@234@VAppsToSKUs@234@VPackageSources@234@VOperations@234@VPackageTasks@234@VFileTasks@234@@Meta@RepoMan@@QEAA?AV?$function@$$A6AXV?$function@$$A6A_NAEAVgetstream@rows@query@sqlite3pp@@@Z@std@@@Z@std@@AEA_J@Z@XV?$function@$$A6A_NAEAVgetstream@rows@query@sqlite3pp@@@Z@6@@std@@6B@; const std::_Func_impl_no_alloc<`RepoMan::Meta::Schema<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::Tables::Families,RepoMan::Meta::Tables::Architectures,RepoMan::Meta::Tables::Flavors,RepoMan::Meta::Tables::Cultures,RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::Tables::Builds,RepoMan::Meta::Tables::Media,RepoMan::Meta::Tables::SKUs,RepoMan::Meta::Tables::Apps,RepoMan::Meta::Tables::Packages,RepoMan::Meta::Tables::Digests,RepoMan::Meta::Tables::Hashes,RepoMan::Meta::Tables::Directories,RepoMan::Meta::Tables::Paths,RepoMan::Meta::Tables::Files,RepoMan::Meta::Tables::Blocks,RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::Tables::Patches,RepoMan::Meta::Tables::PackagesToPaths,RepoMan::Meta::Tables::PackagesToApps,RepoMan::Meta::Tables::AppsToSKUs,RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::Tables::Operations,RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::Tables::FileTasks>::ForEachRowIn<RepoMan::Meta::Query<62,RepoMan::Meta::Queries::Text::TasksForOperation,RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>>>,__int64 &>(__int64 &)'::`2'::_lambda_1_,void,std::function<bool (sqlite3pp::query::rows::getstream &)>>::`vftable'
0x18001254d  mov     [rsp+308h+var_B8], rax
0x180012555  mov     rax, [rsp+308h+var_2B0]
0x18001255a  mov     [rsp+308h+var_B0], rax
0x180012562  mov     [rsp+308h+var_A8], r13d
0x18001256a  mov     [rsp+308h+var_A0], rcx
0x180012572  lea     rax, [rsp+308h+var_B8]
0x18001257a  mov     [rsp+308h+var_80], rax
0x180012582  lea     rax, off_1801CFC70
0x180012589  mov     [rsp+308h+Block], rax
0x180012591  mov     [rsp+308h+Block+8], rdi
0x180012599  lea     rax, [rsp+308h+var_2A0]
0x18001259e  mov     qword ptr [rsp+308h+var_138], rax
0x1800125a6  lea     rax, [rsp+308h+Block]
0x1800125ae  mov     [rsp+308h+var_110], rax
0x1800125b6  lea     rdx, [rsp+308h+Block]
0x1800125be  lea     rcx, [rsp+308h+var_B8]
0x1800125c6  call    ??R?$_Func_class@XV?$function@$$A6A_NAEAVgetstream@rows@query@sqlite3pp@@@Z@std@@@std@@QEBAXV?$function@$$A6A_NAEAVgetstream@rows@query@sqlite3pp@@@Z@1@@Z; std::_Func_class<void,std::function<bool (sqlite3pp::query::rows::getstream &)>>::operator()(std::function<bool (sqlite3pp::query::rows::getstream &)>)
0x1800125cb  nop
0x1800125cc  mov     rcx, [rsp+308h+var_80]
0x1800125d4  test    rcx, rcx
0x1800125d7  jz      short loc_1800125F4
0x1800125d9  mov     rax, [rcx]
0x1800125dc  lea     rdx, [rsp+308h+var_B8]
0x1800125e4  cmp     rcx, rdx
0x1800125e7  setnz   dl
0x1800125ea  mov     rax, [rax+20h]
0x1800125ee  call    cs:__guard_dispatch_icall_fptr
0x1800125f4  lea     rdx, [rsp+308h+var_2A0]
0x1800125f9  lea     rcx, [rsp+308h+var_2C8]
  ... truncated ...
```
