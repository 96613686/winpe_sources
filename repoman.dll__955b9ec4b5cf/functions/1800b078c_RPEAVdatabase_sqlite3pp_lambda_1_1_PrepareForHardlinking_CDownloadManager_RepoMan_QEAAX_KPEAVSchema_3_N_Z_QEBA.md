# ??$?RPEAVdatabase@sqlite3pp@@@_lambda_1_@?1??PrepareForHardlinking@CDownloadManager@RepoMan@@QEAAX_KPEAVSchema@3@_N@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z

- ea: `0x1800b078c`
- end: `0x1800b0f78`
- name: `??$?RPEAVdatabase@sqlite3pp@@@_lambda_1_@?1??PrepareForHardlinking@CDownloadManager@RepoMan@@QEAAX_KPEAVSchema@3@_N@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z`
- size: `2028`
- prototype: `void __fastcall(_QWORD *, struct sqlite3pp::database *)`
- caller_count: `1`
- callee_count: `36`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b06c4`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x1800136dc`
- `0x180013b14`
- `0x18001b1ec`
- `0x180024c38`
- `0x180024d6c`
- `0x180024de8`
- `0x1800255cc`
- `0x1800257a8`
- `0x18002854c`
- `0x18002e6a4`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18002ff54`
- `0x1800b078c`
- `0x1800b2e18`
- `0x1800b57fc`
- `0x1800b59cc`
- `0x1800b7850`
- `0x1800b9e2c`
- `0x1800ddca8`
- `0x1800ddcbc`
- `0x1800ddccc`
- `0x1800ddce0`
- `0x1800ddd4c`
- `0x1800dddcc`
- `0x1800ddea0`
- `0x1800ddf18`
- `0x1800dfffc`
- `0x180108d50`
- `0x1801094f0`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b096e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b096e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b0c3f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b0cbc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b0c3f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b0cbc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b0c38`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b0cb5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b0c38`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b0cb5`

## string_xrefs

- `0x1800b07c4`: `CDownloadManager.PrepareForHardlinking`
- `0x1800b087b`: ` AND size > 0 GROUP BY FileTasks.hash_id)`
- `0x1800b0845`: ` AND hash_id in (SELECT hash_id FROM (SELECT count() AS count, FileTasks.hash_id FROM FileTasks JOIN Hashes on Hashes.hash_id = FileTasks.hash_id JOIN Digests on Digests.digest_id = Hashes.digest_id WHERE Digests.Digest not like 'pseudoDigest' AND operation_id = `
- `0x1800b0f59`: `failed to reserve sufficient memory to prepare hardlink partitions.`
- `0x1800b07f0`: `UPDATE FileTasks SET HardLinkFlags = `
- `0x1800b0cc2`: `UPDATE FileTasks SET HardLinkFlags = `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall `RepoMan::CDownloadManager::PrepareForHardlinking'::`2'::_lambda_1_::operator()<sqlite3pp::database *>(
        _QWORD *a1,
        struct sqlite3pp::database *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const char *v16; // rdx
  __int64 v17; // rax
  const char *v18; // r8
  int v19; // eax
  int v20; // ecx
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // r15
  __int64 v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rax
  char v29; // di
  __int64 *v30; // rdx
  __int64 v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r9
  __int64 *v37; // rbx
  _QWORD *v38; // rdx
  __int64 v39; // rax
  __int64 **v40; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  const char *v43; // r8
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  unsigned int v47; // ebx
  const char *v48; // rax
  int v49; // eax
  unsigned int v50; // ebx
  const char *v51; // rax
  char v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v55; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h] BYREF
  int v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  char v60[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h]
  char v62[24]; // [rsp+90h] [rbp-70h] BYREF
  sqlite3pp::statement *v63; // [rsp+A8h] [rbp-58h]
  char v64[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v65[128]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v66[13]; // [rsp+138h] [rbp+38h] BYREF
  char v67[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  void *Block[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __m128i si128; // [rsp+1C0h] [rbp+C0h]
  char *v70[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __m128i v71; // [rsp+1E0h] [rbp+E0h]
  char *v72[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __m128i v73; // [rsp+200h] [rbp+100h]
  _BYTE v74[40]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v75; // [rsp+238h] [rbp+138h]

  RepoMan::Tracer::Tracer(v74, 2, "CDownloadManager.PrepareForHardlinking");
  v4 = *((_BYTE *)a1 + 16) != 0 ? 3 : 0;
  std::ostringstream::ostringstream(v64);
  v5 = std::operator<<<std::char_traits<char>>((__int64)v64, (__int64)"UPDATE FileTasks SET HardLinkFlags = ");
  v6 = std::ostream::operator<<(v5, v4 + 1);
  v7 = std::operator<<<std::char_traits<char>>(v6, (__int64)" WHERE operation_id=");
  v8 = std::ostream::operator<<(v7, *a1);
  v9 = std::operator<<<std::char_traits<char>>(v8, (__int64)" AND State = ");
  v10 = std::ostream::operator<<(v9, 1);
  v11 = std::operator<<<std::char_traits<char>>(
          v10,
          (__int64)" AND hash_id in (SELECT hash_id FROM (SELECT count() AS count, FileTasks.hash_id FROM FileTasks JOIN "
                   "Hashes on Hashes.hash_id = FileTasks.hash_id JOIN Digests on Digests.digest_id = Hashes.digest_id WHE"
                   "RE Digests.Digest not like 'pseudoDigest' AND operation_id = ");
  v12 = std::ostream::operator<<(v11, *a1);
  v13 = std::operator<<<std::char_traits<char>>(v12, (__int64)" AND Disposition & ");
  v14 = std::ostream::operator<<(v13, 14);
  v15 = std::operator<<<std::char_traits<char>>(v14, (__int64)" AND size > 0 GROUP BY FileTasks.hash_id)");
  v16 = " ";
  if ( *((_BYTE *)a1 + 16) )
    v16 = " WHERE count > 1";
  v17 = std::operator<<<std::char_traits<char>>(v15, (__int64)v16);
  std::operator<<<std::char_traits<char>>(v17, (__int64)");");
  std::stringbuf::str(v65, v70);
  v18 = (const char *)v70;
  if ( v71.m128i_i64[1] > 0xFuLL )
    v18 = v70[0];
  sqlite3pp::statement::statement((sqlite3pp::statement *)v60, a2, v18);
  v19 = sqlite3_step(v61);
  v20 = 0;
  if ( v19 != 101 )
    v20 = v19;
  if ( v20 )
  {
    if ( v20 == 14 )
      v49 = sqlite3pp::database::open_error_code(a2);
    else
      v49 = sqlite3pp::database::extended_error_code(a2);
    v50 = v49 - 2063532032;
    v51 = sqlite3pp::database::error_msg(a2);
    RepoMan::RaiseException<RepoMan::Exception,long>(1168, "src\\repoman\\src\\repoman\\DownloadManagers.hpp", v51, v50);
  }
  if ( *((_BYTE *)a1 + 16) )
  {
    v56 = 0;
    v21 = malloc(0x40u);
    v22 = v21;
    if ( !v21 )
      std::_Xbad_alloc();
    *v21 = v21;
    v21[1] = v21;
    v21[2] = v21;
    *((_WORD *)v21 + 12) = 257;
    v55 = v21;
    v54 = 4;
    RepoMan::Meta::Schema<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::Tables::Families,RepoMan::Meta::Tables::Architectures,RepoMan::Meta::Tables::Flavors,RepoMan::Meta::Tables::Cultures,RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::Tables::Builds,RepoMan::Meta::Tables::Media,RepoMan::Meta::Tables::SKUs,RepoMan::Meta::Tables::Apps,RepoMan::Meta::Tables::Packages,RepoMan::Meta::Tables::Digests,RepoMan::Meta::Tables::Hashes,RepoMan::Meta::Tables::Directories,RepoMan::Meta::Tables::Paths,RepoMan::Meta::Tables::Files,RepoMan::Meta::Tables::Blocks,RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::Tables::Patches,RepoMan::Meta::Tables::PackagesToPaths,RepoMan::Meta::Tables::PackagesToApps,RepoMan::Meta::Tables::AppsToSKUs,RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::Tables::Operations,RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::Tables::FileTasks>::GetQuery<RepoMan::Meta::Query<43,RepoMan::Meta::Queries::Text::PartitionedDuplicates,RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>>>,unsigned __int64 const &,__int64>(
      a1[1],
      v62,
      a2,
      a1,
      &v54);
    sqlite3pp::query::begin(v63, &v57);
    while ( v58 != 101 )
    {
      v23 = *(_QWORD *)(v57 + 8);
      v24 = sqlite3_column_int64(v23, 2);
      v25 = sqlite3_column_int64(v23, 1);
      v26 = sqlite3_column_int64(v23, 0);
      v59 = v26;
      v54 = v25;
      v53 = v24;
      if ( v22 == v55 || v22[4] != v26 )
      {
        v27 = (__int64 *)v55[1];
        v22 = v55;
        while ( !*((_BYTE *)v27 + 25) )
        {
          if ( v27[4] >= v26 )
            v22 = v27;
          else
            v27 += 2;
          v27 = (__int64 *)*v27;
        }
        if ( *((_BYTE *)v22 + 25) || v26 < v22[4] )
          v22 = v55;
        if ( v22 == v55 )
        {
          *(_OWORD *)Block = 0;
          si128.m128i_i64[0] = 0;
          v28 = std::_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>::emplace<__int64 &,std::vector<std::pair<__int64,__int64>>>(
                  &v55,
                  v67,
                  &v59,
                  Block);
          v22 = *(_QWORD **)v28;
          v29 = *(_BYTE *)(v28 + 8);
          std::vector<_REPO_RANGE>::~vector<_REPO_RANGE>(Block);
          if ( !v29 )
            RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
              1192,
              (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
              (unsigned int)"failed to reserve sufficient memory to prepare hardlink partitions.",
              -2147024882,
              8);
          v25 = v54;
        }
      }
      v30 = (__int64 *)v22[6];
      if ( v30 == (__int64 *)v22[7] )
      {
        std::vector<std::pair<__int64,__int64>>::_Emplace_reallocate<__int64 &,__int64 &>(v22 + 5, v30, &v54, &v53);
      }
      else
      {
        *v30 = v25;
        v30[1] = v53;
        v22[6] += 16LL;
      }
      sqlite3pp::query::query_iterator::operator++(&v57);
    }
    if ( v56 )
    {
      *(_OWORD *)Block = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy((char *)Block, "groups");
      RepoMan::Logger::CreateValue((unsigned int)&v53, 3, 11, (unsigned int)Block, v56);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 48LL))(v75, &v53);
      v31 = v53;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      }
      if ( si128.m128i_i64[1] > 0xFuLL )
      {
        v32 = Block[0];
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v32 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v32);
      }
      *(_OWORD *)Block = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(Block[0]) = 0;
      std::ostringstream::str(v64, Block);
      if ( si128.m128i_i64[1] > 0xFuLL )
      {
        v33 = Block[0];
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v33 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v33 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v33);
      }
      v34 = std::operator<<<std::char_traits<char>>((__int64)v64, (__int64)"UPDATE FileTasks SET HardLinkFlags = ");
      v35 = std::ostream::operator<<(v34, 2);
      std::operator<<<std::char_traits<char>>(v35, (__int64)" WHERE id in (");
      v37 = (__int64 *)*v55;
      while ( !*((_BYTE *)v37 + 25) )
      {
        LOBYTE(v36) = v52;
        ____Sort_unchecked_PEAU__pair__J_J_std__V_lambda_1___1_____RPEAVdatabase_sqlite3pp___3_1__PrepareForHardlinking_CDownloadManager_RepoMan__QEAAX_KPEAVSchema_6__N_Z_QEBA_A_PPEAVdatabase_sqlite3pp___Z__std__YAXPEAU__pair__J_J_0_0_JV_lambda_1___1_____RPEAVdatabase_sqlite3pp___2_1__PrepareForHardlinking_CDownloadManager_RepoMan__QEAAX_KPEAVSchema_5__N_Z_QEBA_A_PPEAVdatabase_sqlite3pp___Z__Z(
          v37[5],
          v37[6],
          (v37[6] - v37[5]) >> 4,
          v36);
        v38 = (_QWORD *)v37[5];
        if ( !((v37[6] - (__int64)v38) >> 4) )
          std::vector<RepoMan::ComPtr<IRepoFile>>::_Xrange();
        v39 = std::ostream::operator<<(v64, *v38);
        std::operator<<<std::char_traits<char>>(v39, (__int64)",");
        v40 = (__int64 **)v37[2];
        if ( *((_BYTE *)v40 + 25) )
        {
          for ( i = (__int64 *)v37[1]; !*((_BYTE *)i + 25) && v37 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v37 = i;
          v37 = i;
        }
        else
        {
          v37 = (__int64 *)v37[2];
          for ( j = *v40; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v37 = j;
        }
      }
      std::ostream::seekp(v64);
      std::operator<<<std::char_traits<char>>((__int64)v64, (__int64)");");
      std::stringbuf::str(v65, v72);
      v43 = (const char *)v72;
      if ( v73.m128i_i64[1] > 0xFuLL )
        v43 = v72[0];
      sqlite3pp::statement::statement((sqlite3pp::statement *)Block, a2, v43);
      v44 = sqlite3_step(Block[1]);
      v45 = 0;
      if ( v44 != 101 )
        v45 = v44;
      if ( v45 )
      {
        if ( v45 == 14 )
          v46 = sqlite3pp::database::open_error_code(a2);
        else
          v46 = sqlite3pp::database::extended_error_code(a2);
        v47 = v46 - 2063532032;
        v48 = sqlite3pp::database::error_msg(a2);
        RepoMan::RaiseException<RepoMan::Exception,long>(
          1224,
          "src\\repoman\\src\\repoman\\DownloadManagers.hpp",
          v48,
          v47);
      }
      sqlite3pp::statement::~statement((sqlite3pp::statement *)Block);
      std::string::_Tidy_deallocate(v72);
      v72[0] = (char *)19937;
      v73 = _mm_load_si128((const __m128i *)&_xmm);
      sqlite3pp::statement::reset_and_clear_bindings(v63);
      std::_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>::~_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>(&v55);
      sqlite3pp::statement::~statement((sqlite3pp::statement *)v60);
      std::string::_Tidy_deallocate(v70);
      v70[0] = (char *)19937;
      v71 = _mm_load_si128((const __m128i *)&_xmm);
      std::ostringstream::~ostringstream(v66);
      v66[0] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)v66);
    }
    else
    {
      sqlite3pp::statement::reset_and_clear_bindings(v63);
      std::_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>::~_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>(&v55);
      sqlite3pp::statement::~statement((sqlite3pp::statement *)v60);
      std::string::_Tidy_deallocate(v70);
      v70[0] = (char *)19937;
      v71 = _mm_load_si128((const __m128i *)&_xmm);
      std::ostringstream::~ostringstream(v66);
      v66[0] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)v66);
    }
  }
  else
  {
    sqlite3pp::statement::~statement((sqlite3pp::statement *)v60);
    std::string::_Tidy_deallocate(v70);
    v70[0] = (char *)19937;
    v71 = _mm_load_si128((const __m128i *)&_xmm);
    std::ostringstream::~ostringstream(v66);
    v66[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v66);
  }
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v74);
}

```

## disassembly

```asm
0x1800b078c  mov     [rsp-8+arg_10], rbx
0x1800b0791  mov     [rsp-8+arg_18], rsi
0x1800b0796  push    rbp
0x1800b0797  push    rdi
0x1800b0798  push    r13
0x1800b079a  push    r14
0x1800b079c  push    r15
0x1800b079e  lea     rbp, [rsp-150h]
0x1800b07a6  sub     rsp, 250h
0x1800b07ad  mov     rax, cs:__security_cookie
0x1800b07b4  xor     rax, rsp
0x1800b07b7  mov     [rbp+170h+var_30], rax
0x1800b07be  mov     r14, rdx
0x1800b07c1  mov     rdi, rcx
0x1800b07c4  lea     r8, aCdownloadmanag_8; "CDownloadManager.PrepareForHardlinking"
0x1800b07cb  mov     edx, 2
0x1800b07d0  lea     rcx, [rbp+170h+var_60]
0x1800b07d7  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800b07dc  mov     al, [rdi+10h]
0x1800b07df  neg     al
0x1800b07e1  sbb     rbx, rbx
0x1800b07e4  and     ebx, 3
0x1800b07e7  lea     rcx, [rbp+170h+var_1C0]
0x1800b07eb  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b07f0  lea     rdx, aUpdateFiletask; "UPDATE FileTasks SET HardLinkFlags = "
0x1800b07f7  lea     rcx, [rbp+170h+var_1C0]
0x1800b07fb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b0800  lea     rdx, [rbx+1]
0x1800b0804  mov     rcx, rax
0x1800b0807  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z; std::ostream::operator<<(__int64)
0x1800b080c  mov     rcx, rax
0x1800b080f  lea     rdx, aWhereOperation; " WHERE operation_id="
0x1800b0816  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b081b  mov     rdx, [rdi]
0x1800b081e  mov     rcx, rax
0x1800b0821  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x1800b0826  mov     rcx, rax
0x1800b0829  lea     rdx, aAndState; " AND State = "
0x1800b0830  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b0835  mov     edx, 1
0x1800b083a  mov     rcx, rax
0x1800b083d  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z; std::ostream::operator<<(__int64)
0x1800b0842  mov     rcx, rax
0x1800b0845  lea     rdx, aAndHashIdInSel; " AND hash_id in (SELECT hash_id FROM (S"...
0x1800b084c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b0851  mov     rdx, [rdi]
0x1800b0854  mov     rcx, rax
0x1800b0857  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x1800b085c  mov     rcx, rax
0x1800b085f  lea     rdx, aAndDisposition; " AND Disposition & "
0x1800b0866  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b086b  mov     edx, 0Eh
0x1800b0870  mov     rcx, rax
0x1800b0873  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z; std::ostream::operator<<(__int64)
0x1800b0878  mov     rcx, rax
0x1800b087b  lea     rdx, aAndSize0GroupB; " AND size > 0 GROUP BY FileTasks.hash_i"...
0x1800b0882  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b0887  lea     rcx, aWhereCount1; " WHERE count > 1"
0x1800b088e  lea     rdx, asc_1801D0D08; " "
0x1800b0895  xor     r13d, r13d
0x1800b0898  cmp     [rdi+10h], r13b
0x1800b089c  cmovnz  rdx, rcx
0x1800b08a0  mov     rcx, rax
0x1800b08a3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b08a8  mov     rcx, rax
0x1800b08ab  lea     rdx, asc_1801DEBB4; ");"
0x1800b08b2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b08b7  lea     rdx, [rbp+170h+var_A0]
0x1800b08be  lea     rcx, [rbp+170h+var_1B8]
0x1800b08c2  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b08c7  lea     r8, [rbp+170h+var_A0]
0x1800b08ce  cmp     [rbp+170h+var_88], 0Fh
0x1800b08d6  cmova   r8, [rbp+170h+var_A0]; char *
0x1800b08de  mov     rdx, r14; struct sqlite3pp::database *
0x1800b08e1  lea     rcx, [rsp+270h+var_200]; this
0x1800b08e6  call    ??0statement@sqlite3pp@@IEAA@AEAVdatabase@1@PEBD@Z; sqlite3pp::statement::statement(sqlite3pp::database &,char const *)
0x1800b08eb  nop
0x1800b08ec  mov     rcx, [rsp+270h+var_1F8]
0x1800b08f1  call    sqlite3_step
0x1800b08f6  nop
0x1800b08f7  mov     ecx, r13d
0x1800b08fa  cmp     eax, 65h ; 'e'
0x1800b08fd  cmovnz  ecx, eax
0x1800b0900  test    ecx, ecx
0x1800b0902  jnz     loc_1800B0F0B
0x1800b0908  cmp     [rdi+10h], r13b
0x1800b090c  jnz     short loc_1800B0964
0x1800b090e  lea     rcx, [rsp+270h+var_200]; this
0x1800b0913  call    ??1statement@sqlite3pp@@IEAA@XZ; sqlite3pp::statement::~statement(void)
0x1800b0918  lea     rcx, [rbp+170h+var_A0]
0x1800b091f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b0924  mov     ebx, 4DE1h
0x1800b0929  mov     [rbp+170h+var_A0], rbx
0x1800b0930  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800b0938  movdqu  xmmword ptr [rbp+0E0h], xmm0
0x1800b0940  lea     rcx, [rbp+170h+var_138]
0x1800b0944  call    ??1?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::ostringstream::~ostringstream(void)
0x1800b0949  nop
0x1800b094a  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800b0951  mov     [rbp+170h+var_138], rax
0x1800b0955  lea     rcx, [rbp+170h+var_138]; this
0x1800b0959  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x1800b095e  nop
0x1800b095f  jmp     loc_1800B0E99
0x1800b0964  mov     [rsp+270h+var_220], r13
0x1800b0969  mov     ecx, 40h ; '@'; Size
0x1800b096e  call    cs:__imp_malloc
0x1800b0974  mov     rbx, rax
0x1800b0977  test    rax, rax
0x1800b097a  jz      loc_1800B0F45
0x1800b0980  mov     [rax], rax
0x1800b0983  mov     [rax+8], rax
0x1800b0987  mov     [rax+10h], rax
0x1800b098b  mov     word ptr [rax+18h], 101h
0x1800b0991  mov     [rsp+270h+var_228], rax
0x1800b0996  mov     [rsp+270h+var_230], 4
0x1800b099f  lea     rax, [rsp+270h+var_230]
0x1800b09a4  mov     [rsp+270h+Reserved], rax
0x1800b09a9  mov     r9, rdi
0x1800b09ac  mov     r8, r14
0x1800b09af  lea     rdx, [rbp+170h+var_1E0]
0x1800b09b3  mov     rcx, [rdi+8]
0x1800b09b7  call    ??$GetQuery@V?$Query@$0CL@UPartitionedDuplicates@Text@Queries@Meta@RepoMan@@V?$InputType@U?$Column@U?$Value@UNumber@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U123@@45@@Meta@RepoMan@@AEB_K_J@?$Schema@VSchemaVersions@Tables@Meta@RepoMan@@VFamilies@234@VArchitectures@234@VFlavors@234@VCultures@234@VAlgorithms@234@VBuilds@234@VMedia@234@VSKUs@234@VApps@234@VPackages@234@VDigests@234@VHashes@234@VDirectories@234@VPaths@234@VFiles@234@VBlocks@234@VBlockSource@234@VPatches@234@VPackagesToPaths@234@VPackagesToApps@234@VAppsToSKUs@234@VPackageSources@234@VOperations@234@VPackageTasks@234@VFileTasks@234@@Meta@RepoMan@@QEAA?AV?$Query@$0CL@UPartitionedDuplicates@Text@Queries@Meta@RepoMan@@V?$InputType@U?$Column@U?$Value@UNumber@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U123@@45@@12@PEAVdatabase@sqlite3pp@@AEB_K$$QEA_J@Z; RepoMan::Meta::Schema<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::Tables::Families,RepoMan::Meta::Tables::Architectures,RepoMan::Meta::Tables::Flavors,RepoMan::Meta::Tables::Cultures,RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::Tables::Builds,RepoMan::Meta::Tables::Media,RepoMan::Meta::Tables::SKUs,RepoMan::Meta::Tables::Apps,RepoMan::Meta::Tables::Packages,RepoMan::Meta::Tables::Digests,RepoMan::Meta::Tables::Hashes,RepoMan::Meta::Tables::Directories,RepoMan::Meta::Tables::Paths,RepoMan::Meta::Tables::Files,RepoMan::Meta::Tables::Blocks,RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::Tables::Patches,RepoMan::Meta::Tables::PackagesToPaths,RepoMan::Meta::Tables::PackagesToApps,RepoMan::Meta::Tables::AppsToSKUs,RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::Tables::Operations,RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::Tables::FileTasks>::GetQuery<RepoMan::Meta::Query<43,RepoMan::Meta::Queries::Text::PartitionedDuplicates,RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>>>,unsigned __int64 const &,__int64>(sqlite3pp::database *,unsigned __int64 const &,__int64 &&)
0x1800b09bc  lea     rdx, [rsp+270h+var_218]
0x1800b09c1  mov     rcx, [rbp+170h+var_1C8]
0x1800b09c5  call    ?begin@query@sqlite3pp@@QEAA?AVquery_iterator@12@XZ; sqlite3pp::query::begin(void)
0x1800b09ca  jmp     loc_1800B0AE5
0x1800b09cf  mov     rax, [rsp+270h+var_218]
0x1800b09d4  mov     rsi, [rax+8]
0x1800b09d8  mov     edx, 2
0x1800b09dd  mov     rcx, rsi
0x1800b09e0  call    sqlite3_column_int64
0x1800b09e5  mov     rdi, rax
0x1800b09e8  mov     edx, 1
0x1800b09ed  mov     rcx, rsi
0x1800b09f0  call    sqlite3_column_int64
0x1800b09f5  mov     r15, rax
0x1800b09f8  xor     edx, edx
0x1800b09fa  mov     rcx, rsi
0x1800b09fd  call    sqlite3_column_int64
0x1800b0a02  nop
0x1800b0a03  mov     [rsp+270h+var_208], rax
0x1800b0a08  mov     [rsp+270h+var_230], r15
0x1800b0a0d  mov     [rsp+270h+var_238], rdi
0x1800b0a12  mov     rdx, [rsp+270h+var_228]
0x1800b0a17  cmp     rbx, rdx
0x1800b0a1a  jz      short loc_1800B0A26
0x1800b0a1c  cmp     [rbx+20h], rax
0x1800b0a20  jz      loc_1800B0AAB
0x1800b0a26  mov     rcx, [rdx+8]
0x1800b0a2a  mov     rbx, rdx
0x1800b0a2d  jmp     short loc_1800B0A41
0x1800b0a2f  cmp     [rcx+20h], rax
0x1800b0a33  jge     short loc_1800B0A3B
0x1800b0a35  add     rcx, 10h
0x1800b0a39  jmp     short loc_1800B0A3E
0x1800b0a3b  mov     rbx, rcx
0x1800b0a3e  mov     rcx, [rcx]
0x1800b0a41  cmp     [rcx+19h], r13b
0x1800b0a45  jz      short loc_1800B0A2F
0x1800b0a47  cmp     [rbx+19h], r13b
0x1800b0a4b  jnz     short loc_1800B0A53
0x1800b0a4d  cmp     rax, [rbx+20h]
0x1800b0a51  jge     short loc_1800B0A56
0x1800b0a53  mov     rbx, rdx
0x1800b0a56  cmp     rbx, rdx
0x1800b0a59  jnz     short loc_1800B0AAB
0x1800b0a5b  xorps   xmm0, xmm0
0x1800b0a5e  movdqu  xmmword ptr [rbp+170h+Block], xmm0
0x1800b0a66  mov     qword ptr [rbp+170h+var_B0], r13
0x1800b0a6d  lea     r9, [rbp+170h+Block]
0x1800b0a74  lea     r8, [rsp+270h+var_208]
0x1800b0a79  lea     rdx, [rbp+170h+var_D0]
0x1800b0a80  lea     rcx, [rsp+270h+var_228]
0x1800b0a85  call    ??$emplace@AEA_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@@?$_Tree@V?$_Tmap_traits@_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@@std@@@std@@@std@@@std@@_N@1@AEA_J$$QEAV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>::emplace<__int64 &,std::vector<std::pair<__int64,__int64>>>(__int64 &,std::vector<std::pair<__int64,__int64>> &&)
0x1800b0a8a  mov     rbx, [rax]
0x1800b0a8d  mov     dil, [rax+8]
0x1800b0a91  lea     rcx, [rbp+170h+Block]
0x1800b0a98  call    ??1?$vector@U_REPO_RANGE@@V?$allocator@U_REPO_RANGE@@@std@@@std@@QEAA@XZ; std::vector<_REPO_RANGE>::~vector<_REPO_RANGE>(void)
0x1800b0a9d  test    dil, dil
0x1800b0aa0  jz      loc_1800B0F4B
0x1800b0aa6  mov     r15, [rsp+270h+var_230]
0x1800b0aab  lea     rcx, [rbx+28h]
0x1800b0aaf  mov     rdx, [rcx+8]
0x1800b0ab3  cmp     rdx, [rcx+10h]
0x1800b0ab7  jz      short loc_1800B0ACC
0x1800b0ab9  mov     [rdx], r15
0x1800b0abc  mov     rax, [rsp+270h+var_238]
0x1800b0ac1  mov     [rdx+8], rax
0x1800b0ac5  add     qword ptr [rcx+8], 10h
0x1800b0aca  jmp     short loc_1800B0ADB
0x1800b0acc  lea     r9, [rsp+270h+var_238]
0x1800b0ad1  lea     r8, [rsp+270h+var_230]
0x1800b0ad6  call    ??$_Emplace_reallocate@AEA_JAEA_J@?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@AEAAPEAU?$pair@_J_J@1@QEAU21@AEA_J1@Z; std::vector<std::pair<__int64,__int64>>::_Emplace_reallocate<__int64 &,__int64 &>(std::pair<__int64,__int64> * const,__int64 &,__int64 &)
0x1800b0adb  lea     rcx, [rsp+270h+var_218]
0x1800b0ae0  call    ??Equery_iterator@query@sqlite3pp@@QEAAAEAV012@XZ; sqlite3pp::query::query_iterator::operator++(void)
0x1800b0ae5  cmp     [rsp+270h+var_210], 65h ; 'e'
0x1800b0aea  jnz     loc_1800B09CF
0x1800b0af0  mov     rdx, [rsp+270h+var_220]
0x1800b0af5  test    rdx, rdx
0x1800b0af8  jnz     short loc_1800B0B63
0x1800b0afa  mov     rcx, [rbp+170h+var_1C8]; this
0x1800b0afe  call    ?reset_and_clear_bindings@statement@sqlite3pp@@QEAAHXZ; sqlite3pp::statement::reset_and_clear_bindings(void)
0x1800b0b03  lea     rcx, [rsp+270h+var_228]
0x1800b0b08  call    ??1?$_Tree@V?$_Tmap_traits@_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$vector@U?$pair@_J_J@std@@V?$allocator@U?$pair@_J_J@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>::~_Tree<std::_Tmap_traits<__int64,std::vector<std::pair<__int64,__int64>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<std::pair<__int64,__int64>>>>,0>>(void)
0x1800b0b0d  lea     rcx, [rsp+270h+var_200]; this
0x1800b0b12  call    ??1statement@sqlite3pp@@IEAA@XZ; sqlite3pp::statement::~statement(void)
0x1800b0b17  lea     rcx, [rbp+170h+var_A0]
0x1800b0b1e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b0b23  mov     ebx, 4DE1h
0x1800b0b28  mov     [rbp+170h+var_A0], rbx
0x1800b0b2f  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800b0b37  movdqu  xmmword ptr [rbp+0E0h], xmm0
0x1800b0b3f  lea     rcx, [rbp+170h+var_138]
0x1800b0b43  call    ??1?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::ostringstream::~ostringstream(void)
0x1800b0b48  nop
0x1800b0b49  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800b0b50  mov     [rbp+170h+var_138], rax
0x1800b0b54  lea     rcx, [rbp+170h+var_138]; this
0x1800b0b58  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x1800b0b5d  nop
0x1800b0b5e  jmp     loc_1800B0E99
0x1800b0b63  xorps   xmm0, xmm0
0x1800b0b66  movups  xmmword ptr [rbp+170h+Block], xmm0
0x1800b0b6d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000006
0x1800b0b75  movdqu  [rbp+170h+var_B0], xmm1
0x1800b0b7d  mov     eax, dword ptr cs:aGroups; "groups"
0x1800b0b83  mov     dword ptr [rbp+170h+Block], eax
0x1800b0b89  movzx   eax, word ptr cs:aGroups+4; "ps"
0x1800b0b90  mov     word ptr [rbp+170h+Block+4], ax
0x1800b0b97  mov     byte ptr [rbp+170h+Block+6], r13b
0x1800b0b9e  mov     [rsp+270h+Reserved], rdx
0x1800b0ba3  lea     r9, [rbp+170h+Block]
0x1800b0baa  mov     edx, 3
0x1800b0baf  lea     r8d, [rdx+8]
0x1800b0bb3  lea     rcx, [rsp+270h+var_238]
0x1800b0bb8  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800b0bbd  mov     rcx, [rbp+170h+var_38]
0x1800b0bc4  mov     rax, [rcx]
0x1800b0bc7  lea     rdx, [rsp+270h+var_238]
0x1800b0bcc  mov     rax, [rax+30h]
0x1800b0bd0  call    cs:__guard_dispatch_icall_fptr
0x1800b0bd6  nop
0x1800b0bd7  mov     rcx, [rsp+270h+var_238]
0x1800b0bdc  test    rcx, rcx
0x1800b0bdf  jz      short loc_1800B0BF4
0x1800b0be1  mov     [rsp+270h+var_238], r13
0x1800b0be6  mov     rax, [rcx]
0x1800b0be9  mov     rax, [rax+8]
0x1800b0bed  call    cs:__guard_dispatch_icall_fptr
0x1800b0bf3  nop
0x1800b0bf4  mov     ebx, 1000h
0x1800b0bf9  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x1800b0c00  cmp     rax, 0Fh
0x1800b0c04  jbe     short loc_1800B0C45
0x1800b0c06  mov     rcx, [rbp+170h+Block]; Block
0x1800b0c0d  mov     rdx, rcx
0x1800b0c10  inc     rax
0x1800b0c13  cmp     rax, rbx
0x1800b0c16  jb      short loc_1800B0C3F
0x1800b0c18  mov     rcx, [rcx-8]
0x1800b0c1c  sub     rdx, rcx
0x1800b0c1f  lea     rax, [rdx-8]
0x1800b0c23  cmp     rax, 1Fh
0x1800b0c27  jbe     short loc_1800B0C3F
0x1800b0c29  mov     [rsp+270h+Reserved], r13; Reserved
0x1800b0c2e  xor     r9d, r9d; LineNo
0x1800b0c31  xor     r8d, r8d; FileName
0x1800b0c34  xor     edx, edx; FunctionName
0x1800b0c36  xor     ecx, ecx; Expression
0x1800b0c38  call    cs:__imp__invoke_watson
0x1800b0c3f  call    cs:__imp_free
0x1800b0c45  xorps   xmm0, xmm0
0x1800b0c48  movups  xmmword ptr [rbp+170h+Block], xmm0
0x1800b0c4f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800b0c57  movdqu  [rbp+170h+var_B0], xmm1
0x1800b0c5f  mov     byte ptr [rbp+170h+Block], r13b
0x1800b0c66  lea     rdx, [rbp+170h+Block]
0x1800b0c6d  lea     rcx, [rbp+170h+var_1C0]
0x1800b0c71  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::ostringstream::str(std::string &&)
0x1800b0c76  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x1800b0c7d  cmp     rax, 0Fh
0x1800b0c81  jbe     short loc_1800B0CC2
0x1800b0c83  mov     rcx, [rbp+170h+Block]; Block
0x1800b0c8a  mov     rdx, rcx
0x1800b0c8d  inc     rax
0x1800b0c90  cmp     rax, rbx
0x1800b0c93  jb      short loc_1800B0CBC
0x1800b0c95  mov     rcx, [rcx-8]
0x1800b0c99  sub     rdx, rcx
0x1800b0c9c  lea     rax, [rdx-8]
0x1800b0ca0  cmp     rax, 1Fh
0x1800b0ca4  jbe     short loc_1800B0CBC
0x1800b0ca6  mov     [rsp+270h+Reserved], r13; Reserved
0x1800b0cab  xor     r9d, r9d; LineNo
0x1800b0cae  xor     r8d, r8d; FileName
0x1800b0cb1  xor     edx, edx; FunctionName
0x1800b0cb3  xor     ecx, ecx; Expression
0x1800b0cb5  call    cs:__imp__invoke_watson
0x1800b0cbc  call    cs:__imp_free
  ... truncated ...
```
