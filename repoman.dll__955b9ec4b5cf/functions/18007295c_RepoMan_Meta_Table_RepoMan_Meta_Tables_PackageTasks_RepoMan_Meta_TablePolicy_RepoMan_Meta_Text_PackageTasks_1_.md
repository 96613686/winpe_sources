# RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>> &,CommandFlags)

- ea: `0x18007295c`
- end: `0x1800735ce`
- name: `?CreateText@?$Table@VPackageTasks@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageTasks@Text@Meta@RepoMan@@$00@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@23@W4CommandFlags@@@Z`
- size: `3186`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180070fe0`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x180071338`
- `0x18007295c`
- `0x180074884`
- `0x180074918`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180072e57`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180072ebd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180072e57`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180072ebd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180072e50`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180072eb6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180072e50`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180072eb6`

## string_xrefs

- `0x1800729e4`: `PackageTasks`
- `0x18007316f`: `PackageTasks`
- `0x18007339e`: `PackageTasks`
- `0x1800733d5`: `PackageTasks`
- `0x18007346e`: `PackageTasks`
- `0x1800734d9`: `PackageTasks`
- `0x18007356b`: `PackageTasks`
- `0x180072c78`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x180072c41`: `CREATE TABLE IF NOT EXISTS `
- `0x180073529`: `CREATE TABLE IF NOT EXISTS `
- `0x180072d2d`: ` AS incoming, `
- `0x180073145`: `REPLACE INTO `
- `0x18007338d`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v7; // r12
  __int64 v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  int v14; // ecx
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 *v18; // rsi
  _QWORD *v19; // rbx
  _QWORD *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdx
  __int64 v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  _QWORD *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  _QWORD *v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  _QWORD *v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rdx
  __int64 v53; // rax
  void *v54; // rcx
  __m128i v55; // xmm6
  void *v56; // rcx
  __int64 v57; // rax
  __int64 *v58; // rbx
  _QWORD *v59; // rsi
  __int64 *v60; // r15
  _QWORD *v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rax
  _QWORD *v67; // rdx
  int v68; // ecx
  __int64 v69; // rax
  _QWORD *v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rbx
  _QWORD *v73; // rax
  unsigned __int64 v74; // r8
  __int64 v75; // rax
  void **v76; // rax
  char v77; // bl
  __m128i v78; // xmm6
  __int128 *v79; // rdx
  __int64 v80; // rax
  int v81; // ebx
  int v82; // ecx
  _QWORD *v83; // r15
  __int64 v84; // rax
  unsigned __int64 v85; // r8
  int v86; // ecx
  __int64 v88; // rax
  __int64 v89; // rax
  int v90; // ecx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  void (__fastcall *v95)(_QWORD *, void **); // rbx
  __int64 *v96; // [rsp+38h] [rbp-D0h]
  __int64 v97; // [rsp+38h] [rbp-D0h]
  _BYTE v98[16]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v99[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v100[128]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v101[13]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v102[2]; // [rsp+158h] [rbp+50h] BYREF
  __m128i si128; // [rsp+168h] [rbp+60h]
  void *v104[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v105; // [rsp+188h] [rbp+80h]
  _QWORD v106[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v107; // [rsp+1A8h] [rbp+A0h]
  __int128 v108; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v109; // [rsp+1C8h] [rbp+C0h]
  void *Block[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v111; // [rsp+1E8h] [rbp+E0h]
  _QWORD v112[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v113; // [rsp+208h] [rbp+100h]

  v7 = 0;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::IndexName(v106);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v102[0] = *(_QWORD *)"PackageTasks";
    v102[1] = *(unsigned int *)"asks";
    v8 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v9 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v9 = (_QWORD *)v102[0];
    v10 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v8, (__int64)v9, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v10, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v11,
      2050,
      (unsigned int)v106,
      (_DWORD)a1 + 448,
      (__int64)v98);
    v12 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" FROM ");
    v13 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v13 = (_QWORD *)v106[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, (__int64)v13, v107.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v14,
      16,
      (unsigned int)v106,
      (unsigned int)v102,
      (__int64)v98);
    v15 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" LEFT OUTER JOIN ");
    v16 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v16 = (_QWORD *)v102[0];
    v17 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v15, (__int64)v16, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v17, (__int64)" ON (");
    v96 = (__int64 *)a1[61];
    v18 = (__int64 *)a1[60];
    if ( v18 != v96 )
    {
      v19 = v18 + 7;
      do
      {
        if ( v7 )
          std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" AND ");
        v20 = v102;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v20 = (_QWORD *)v102[0];
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v20,
                si128.m128i_u64[0]);
        v22 = std::operator<<<std::char_traits<char>>(v21, (__int64)".");
        v23 = (__int64)v18;
        if ( *(v19 - 4) > 0xFu )
          v23 = *v18;
        v24 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v22, v23, *(v19 - 5));
        v25 = std::operator<<<std::char_traits<char>>(v24, (__int64)" = ");
        v26 = v19 - 3;
        if ( *v19 > 0xFu )
          v26 = (_QWORD *)*v26;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v25, (__int64)v26, *(v19 - 1));
        ++v7;
        v18 += 8;
        v19 += 8;
      }
      while ( v18 != v96 );
    }
    v27 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)") WHERE ");
    v28 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v28 = (_QWORD *)v102[0];
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, si128.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    *(_OWORD *)v104 = 0;
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v104, "id");
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)v104, 2u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    std::string::_Tidy_deallocate(v104);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::MapName(v112);
    v32 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v33 = v112;
    if ( v113.m128i_i64[1] > 0xFuLL )
      v33 = (_QWORD *)v112[0];
    v34 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v32, (__int64)v33, v113.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v34,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v35 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"INSERT INTO ");
    v36 = v112;
    if ( v113.m128i_i64[1] > 0xFuLL )
      v36 = (_QWORD *)v112[0];
    v37 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v35, (__int64)v36, v113.m128i_u64[0]);
    v38 = std::operator<<<std::char_traits<char>>(v37, (__int64)" SELECT ");
    v39 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v39 = (_QWORD *)v106[0];
    v40 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v38, (__int64)v39, v107.m128i_u64[0]);
    v41 = std::operator<<<std::char_traits<char>>(v40, (__int64)".");
    *(_OWORD *)v104 = 0;
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v104, "id");
    v42 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v41, (__int64)v104, 2u);
    v43 = std::operator<<<std::char_traits<char>>(v42, (__int64)" AS incoming, ");
    v44 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v44 = (_QWORD *)v102[0];
    v45 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v43, (__int64)v44, si128.m128i_u64[0]);
    v46 = std::operator<<<std::char_traits<char>>(v45, (__int64)".");
    *(_OWORD *)Block = 0;
    v111 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)Block, "id");
    v47 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, (__int64)Block, 2u);
    v48 = std::operator<<<std::char_traits<char>>(v47, (__int64)" AS client FROM ");
    v49 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v49 = (_QWORD *)v106[0];
    v50 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v48, (__int64)v49, v107.m128i_u64[0]);
    v51 = std::operator<<<std::char_traits<char>>(v50, (__int64)" INNER JOIN ");
    v52 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v52 = (_QWORD *)v102[0];
    v53 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v51, (__int64)v52, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v53, (__int64)" ON (");
    if ( v111.m128i_i64[1] > 0xFuLL )
    {
      v54 = Block[0];
      if ( (unsigned __int64)(v111.m128i_i64[1] + 1) >= 0x1000 )
      {
        v54 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v54 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v54);
    }
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v111 = v55;
    if ( v105.m128i_i64[1] > 0xFuLL )
    {
      v56 = v104[0];
      if ( (unsigned __int64)(v105.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v104[0] - 1);
        if ( (unsigned __int64)((char *)v104[0] - (char *)v56 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v56);
    }
    v57 = 0;
    v97 = 0;
    v58 = (__int64 *)a1[60];
    if ( v58 != (__int64 *)a1[61] )
    {
      v59 = v58 + 7;
      v60 = (__int64 *)a1[61];
      do
      {
        if ( v57 )
          std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" AND ");
        v61 = v102;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v61 = (_QWORD *)v102[0];
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v61,
                si128.m128i_u64[0]);
        v63 = std::operator<<<std::char_traits<char>>(v62, (__int64)".");
        v64 = (__int64)v58;
        if ( *(v59 - 4) > 0xFu )
          v64 = *v58;
        v65 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v63, v64, *(v59 - 5));
        v66 = std::operator<<<std::char_traits<char>>(v65, (__int64)" = ");
        v67 = v59 - 3;
        if ( *v59 > 0xFu )
          v67 = (_QWORD *)*v67;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v66, (__int64)v67, *(v59 - 1));
        v57 = ++v97;
        v58 += 8;
        v59 += 8;
      }
      while ( v58 != v60 );
    }
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)") ");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v68,
      16,
      (unsigned int)v106,
      (unsigned int)v102,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
    v69 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v70 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v70 = (_QWORD *)v106[0];
    v71 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v69, (__int64)v70, v107.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v71, (__int64)";");
    std::stringbuf::str(v100, a2);
    std::string::_Tidy_deallocate(v112);
    v112[0] = 19937;
    v113 = v55;
    std::string::_Tidy_deallocate(v102);
    v102[0] = 19937;
    si128 = v55;
    std::string::_Tidy_deallocate(v106);
    v106[0] = 19937;
    v107 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::MapName(v104);
    v74 = v73[2];
    if ( v73[3] > 0xFu )
      v73 = (_QWORD *)*v73;
    v75 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v72, (__int64)v73, v74);
    std::operator<<<std::char_traits<char>>(v75, (__int64)";");
    std::string::_Tidy_deallocate(v104);
    std::stringbuf::str(v100, a2);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 1 || a4 == 1024 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
  }
  else
  {
    switch ( a4 )
    {
      case 2u:
        std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"REPLACE INTO ");
        goto LABEL_65;
      case 4u:
        v88 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"UPDATE ");
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"PackageTasks");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v104 = 0;
        v105 = 0;
        std::string::_Construct<1,char const *>(v104, "PackageTasks", 0xCu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
          v90,
          4,
          (unsigned int)v104,
          (_DWORD)a1 + 448,
          (__int64)v98);
        std::string::_Tidy_deallocate(v104);
        std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x40u:
        v91 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"PackageTasks");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"PackageTasks");
        std::operator<<<std::char_traits<char>>(v94, (__int64)" WHERE ( rowid = ?1 );");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
    }
  }
  if ( a4 == 1 )
  {
    v95 = *(void (__fastcall **)(_QWORD *, void **))(*a1 + 8LL);
    *(_OWORD *)v104 = 0;
    v105 = 0;
    std::string::_Construct<1,char const *>(v104, "PackageTasks", 0xCu);
    v95(a1, v104);
    if ( v105.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v104, v104[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v104 = 0;
  v105 = 0;
  std::string::_Construct<1,char const *>(v104, "PackageTasks", 0xCu);
  v76 = v104;
  v77 = 4;
LABEL_66:
  v108 = 0;
  v109 = 0;
  v108 = *(_OWORD *)v76;
  v109 = *((__m128i *)v76 + 1);
  *(_BYTE *)v76 = 0;
  v76[2] = 0;
  v76[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v104);
  }
  v78 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v111 = v78;
  }
  v79 = &v108;
  if ( v109.m128i_i64[1] > 0xFuLL )
    v79 = (__int128 *)v108;
  v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v99, (__int64)v79, v109.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v80, (__int64)"(");
  v81 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
    v82,
    a4,
    (unsigned int)&v108,
    (_DWORD)a1 + 448,
    (__int64)v98);
  if ( a4 == 1 && a1[54] )
  {
    v83 = a1 + 52;
    v84 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" , ");
    v85 = v83[2];
    if ( v83[3] > 0xFu )
      v83 = (_QWORD *)*v83;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v84, (__int64)v83, v85);
  }
  std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)")");
  if ( a4 == 2 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" VALUES (");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(
      v86,
      8,
      (unsigned int)&v108,
      v81,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
  std::stringbuf::str(v100, a2);
  std::string::_Tidy_deallocate(&v108);
  *(_QWORD *)&v108 = 19937;
  v109 = v78;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  v101[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
  return a2;
}

```

## disassembly

```asm
0x18007295c  mov     rax, rsp
0x18007295f  mov     [rax+18h], rbx
0x180072963  mov     [rax+20h], rsi
0x180072967  push    rbp
0x180072968  push    r12
0x18007296a  push    r13
0x18007296c  push    r14
0x18007296e  push    r15
0x180072970  lea     rbp, [rax-158h]
0x180072977  sub     rsp, 230h
0x18007297e  movaps  xmmword ptr [rax-38h], xmm6
0x180072982  mov     rax, cs:__security_cookie
0x180072989  xor     rax, rsp
0x18007298c  mov     [rbp+150h+var_40], rax
0x180072993  movzx   esi, r9w
0x180072997  mov     r14, rdx
0x18007299a  mov     r15, rcx
0x18007299d  mov     qword ptr [rsp+250h+var_218], rdx
0x1800729a2  xor     r12d, r12d
0x1800729a5  mov     [rsp+250h+var_210], r12d
0x1800729aa  lea     rcx, [rsp+250h+var_200]
0x1800729af  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800729b4  nop
0x1800729b5  mov     eax, 800h
0x1800729ba  cmp     ax, si
0x1800729bd  jnz     loc_180073088
0x1800729c3  lea     rcx, [rbp+150h+var_C0]
0x1800729ca  call    ?IndexName@?$Table@VPackageTasks@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageTasks@Text@Meta@RepoMan@@$00@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::IndexName(void)
0x1800729cf  nop
0x1800729d0  xorps   xmm0, xmm0
0x1800729d3  movups  [rbp+150h+var_100], xmm0
0x1800729d7  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x1800729df  movdqu  [rbp+150h+var_F0], xmm1
0x1800729e4  movsd   xmm0, qword ptr cs:aPackagetasks; "PackageTasks"
0x1800729ec  movsd   qword ptr [rbp+150h+var_100], xmm0
0x1800729f1  mov     eax, dword ptr cs:aPackagetasks+8; "asks"
0x1800729f7  mov     dword ptr [rbp+150h+var_100+8], eax
0x1800729fa  mov     byte ptr [rbp+150h+var_100+0Ch], r12b
0x1800729fe  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x180072a05  lea     rcx, [rsp+250h+var_1F0]
0x180072a0a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072a0f  lea     rdx, [rbp+150h+var_100]
0x180072a13  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072a18  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072a1d  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072a21  mov     rcx, rax
0x180072a24  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072a29  lea     rdx, aSelectNull; " SELECT NULL"
0x180072a30  mov     rcx, rax
0x180072a33  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072a38  lea     r9, [r15+1C0h]
0x180072a3f  mov     edx, 802h
0x180072a44  lea     rax, [rsp+250h+var_200]
0x180072a49  mov     [rsp+250h+Reserved], rax
0x180072a4e  lea     r8, [rbp+150h+var_C0]
0x180072a55  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180072a5a  lea     rdx, aFrom_0; " FROM "
0x180072a61  lea     rcx, [rsp+250h+var_1F0]
0x180072a66  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072a6b  lea     rdx, [rbp+150h+var_C0]
0x180072a72  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180072a7a  cmova   rdx, [rbp+150h+var_C0]
0x180072a82  mov     r8, qword ptr [rbp+150h+var_B0]
0x180072a89  mov     rcx, rax
0x180072a8c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072a91  lea     edx, [r12+10h]
0x180072a96  lea     rax, [rsp+250h+var_200]
0x180072a9b  mov     [rsp+250h+Reserved], rax
0x180072aa0  lea     r9, [rbp+150h+var_100]
0x180072aa4  lea     r8, [rbp+150h+var_C0]
0x180072aab  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180072ab0  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x180072ab7  lea     rcx, [rsp+250h+var_1F0]
0x180072abc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072ac1  lea     rdx, [rbp+150h+var_100]
0x180072ac5  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072aca  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072acf  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072ad3  mov     rcx, rax
0x180072ad6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072adb  lea     rdx, aOn; " ON ("
0x180072ae2  mov     rcx, rax
0x180072ae5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072aea  mov     rax, [r15+1E8h]
0x180072af1  mov     [rsp+250h+var_220], rax
0x180072af6  mov     rsi, [r15+1E0h]
0x180072afd  lea     r13d, [r12+40h]
0x180072b02  cmp     rsi, rax
0x180072b05  jz      loc_180072BA5
0x180072b0b  lea     rbx, [rsi+38h]
0x180072b0f  test    r12, r12
0x180072b12  jz      short loc_180072B25
0x180072b14  lea     rdx, aAnd_1; " AND "
0x180072b1b  lea     rcx, [rsp+250h+var_1F0]
0x180072b20  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072b25  lea     rdx, [rbp+150h+var_100]
0x180072b29  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072b2e  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072b33  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072b37  lea     rcx, [rsp+250h+var_1F0]
0x180072b3c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072b41  lea     rdx, asc_1801D0CE8; "."
0x180072b48  mov     rcx, rax
0x180072b4b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072b50  mov     rdx, rsi
0x180072b53  cmp     qword ptr [rbx-20h], 0Fh
0x180072b58  jbe     short loc_180072B5D
0x180072b5a  mov     rdx, [rsi]
0x180072b5d  mov     r8, [rbx-28h]
0x180072b61  mov     rcx, rax
0x180072b64  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072b69  lea     rdx, asc_1801D5B8C; " = "
0x180072b70  mov     rcx, rax
0x180072b73  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072b78  lea     rdx, [rbx-18h]
0x180072b7c  cmp     qword ptr [rbx], 0Fh
0x180072b80  jbe     short loc_180072B85
0x180072b82  mov     rdx, [rdx]
0x180072b85  mov     r8, [rbx-8]
0x180072b89  mov     rcx, rax
0x180072b8c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072b91  inc     r12
0x180072b94  add     rsi, r13
0x180072b97  add     rbx, r13
0x180072b9a  cmp     rsi, [rsp+250h+var_220]
0x180072b9f  jnz     loc_180072B0F
0x180072ba5  lea     rdx, aWhere; ") WHERE "
0x180072bac  lea     rcx, [rsp+250h+var_1F0]
0x180072bb1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072bb6  lea     rdx, [rbp+150h+var_100]
0x180072bba  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072bbf  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072bc4  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072bc8  mov     rcx, rax
0x180072bcb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072bd0  lea     r12, asc_1801D0CE8; "."
0x180072bd7  mov     rdx, r12
0x180072bda  mov     rcx, rax
0x180072bdd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072be2  nop
0x180072be3  xorps   xmm0, xmm0
0x180072be6  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180072bea  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180072bf2  movdqu  [rbp+150h+var_D0], xmm1
0x180072bfa  mov     esi, 6469h
0x180072bff  mov     word ptr [rbp+150h+var_E0], si
0x180072c03  mov     byte ptr [rbp+150h+var_E0+2], 0
0x180072c07  mov     ebx, 2
0x180072c0c  mov     r8d, ebx
0x180072c0f  lea     rdx, [rbp+150h+var_E0]
0x180072c13  mov     rcx, rax
0x180072c16  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072c1b  lea     rdx, aIsNull; " IS NULL;"
0x180072c22  mov     rcx, rax
0x180072c25  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072c2a  nop
0x180072c2b  lea     rcx, [rbp+150h+var_E0]
0x180072c2f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180072c34  lea     rcx, [rbp+150h+var_60]
0x180072c3b  call    ?MapName@?$Table@VPackageTasks@Tables@Meta@RepoMan@@V?$TablePolicy@UPackageTasks@Text@Meta@RepoMan@@$00@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UOperation_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UOperations@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UPackage_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPackages@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::PackageTasks,1>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Operation_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Operations,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Package_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Packages,RepoMan::Meta::Alias::None>,__int64>>::MapName(void)
0x180072c40  nop
0x180072c41  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x180072c48  lea     rcx, [rsp+250h+var_1F0]
0x180072c4d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072c52  lea     rdx, [rbp+150h+var_60]
0x180072c59  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x180072c61  cmova   rdx, [rbp+150h+var_60]
0x180072c69  mov     r8, qword ptr [rbp+150h+var_50]
0x180072c70  mov     rcx, rax
0x180072c73  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072c78  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x180072c7f  mov     rcx, rax
0x180072c82  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072c87  lea     rdx, aInsertInto; "INSERT INTO "
0x180072c8e  lea     rcx, [rsp+250h+var_1F0]
0x180072c93  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072c98  lea     rdx, [rbp+150h+var_60]
0x180072c9f  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x180072ca7  cmova   rdx, [rbp+150h+var_60]
0x180072caf  mov     r8, qword ptr [rbp+150h+var_50]
0x180072cb6  mov     rcx, rax
0x180072cb9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072cbe  lea     rdx, aSelect; " SELECT "
0x180072cc5  mov     rcx, rax
0x180072cc8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072ccd  lea     rdx, [rbp+150h+var_C0]
0x180072cd4  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180072cdc  cmova   rdx, [rbp+150h+var_C0]
0x180072ce4  mov     r8, qword ptr [rbp+150h+var_B0]
0x180072ceb  mov     rcx, rax
0x180072cee  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072cf3  mov     rdx, r12
0x180072cf6  mov     rcx, rax
0x180072cf9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072cfe  nop
0x180072cff  xorps   xmm0, xmm0
0x180072d02  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180072d06  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180072d0e  movdqu  [rbp+150h+var_D0], xmm1
0x180072d16  mov     word ptr [rbp+150h+var_E0], si
0x180072d1a  mov     byte ptr [rbp+150h+var_E0+2], 0
0x180072d1e  mov     r8d, ebx
0x180072d21  lea     rdx, [rbp+150h+var_E0]
0x180072d25  mov     rcx, rax
0x180072d28  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072d2d  lea     rdx, aAsIncoming; " AS incoming, "
0x180072d34  mov     rcx, rax
0x180072d37  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072d3c  lea     rdx, [rbp+150h+var_100]
0x180072d40  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072d45  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072d4a  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072d4e  mov     rcx, rax
0x180072d51  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072d56  mov     rdx, r12
0x180072d59  mov     rcx, rax
0x180072d5c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072d61  nop
0x180072d62  xorps   xmm0, xmm0
0x180072d65  movups  xmmword ptr [rbp+150h+Block], xmm0
0x180072d6c  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180072d74  movdqu  [rbp+150h+var_70], xmm1
0x180072d7c  mov     word ptr [rbp+150h+Block], si
0x180072d83  xor     esi, esi
0x180072d85  mov     byte ptr [rbp+150h+Block+2], sil
0x180072d8c  mov     r8d, ebx
0x180072d8f  lea     rdx, [rbp+150h+Block]
0x180072d96  mov     rcx, rax
0x180072d99  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072d9e  lea     rdx, aAsClientFrom; " AS client FROM "
0x180072da5  mov     rcx, rax
0x180072da8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072dad  lea     rdx, [rbp+150h+var_C0]
0x180072db4  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180072dbc  cmova   rdx, [rbp+150h+var_C0]
0x180072dc4  mov     r8, qword ptr [rbp+150h+var_B0]
0x180072dcb  mov     rcx, rax
0x180072dce  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072dd3  lea     rdx, aInnerJoin; " INNER JOIN "
0x180072dda  mov     rcx, rax
0x180072ddd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072de2  lea     rdx, [rbp+150h+var_100]
0x180072de6  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180072deb  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180072df0  mov     r8, qword ptr [rbp+150h+var_F0]
0x180072df4  mov     rcx, rax
0x180072df7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180072dfc  lea     rdx, aOn; " ON ("
0x180072e03  mov     rcx, rax
0x180072e06  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180072e0b  nop
0x180072e0c  mov     ebx, 1000h
0x180072e11  mov     rax, qword ptr [rbp+150h+var_70+8]
0x180072e18  cmp     rax, 0Fh
0x180072e1c  jbe     short loc_180072E5D
0x180072e1e  mov     rcx, [rbp+150h+Block]; Block
0x180072e25  mov     rdx, rcx
0x180072e28  inc     rax
0x180072e2b  cmp     rax, rbx
0x180072e2e  jb      short loc_180072E57
0x180072e30  mov     rcx, [rcx-8]
0x180072e34  sub     rdx, rcx
0x180072e37  lea     rax, [rdx-8]
0x180072e3b  cmp     rax, 1Fh
0x180072e3f  jbe     short loc_180072E57
0x180072e41  mov     [rsp+250h+Reserved], rsi; Reserved
0x180072e46  xor     r9d, r9d; LineNo
0x180072e49  xor     r8d, r8d; FileName
0x180072e4c  xor     edx, edx; FunctionName
0x180072e4e  xor     ecx, ecx; Expression
0x180072e50  call    cs:__imp__invoke_watson
0x180072e57  call    cs:__imp_free
0x180072e5d  mov     r12d, 4DE1h
0x180072e63  mov     [rbp+150h+Block], r12
0x180072e6a  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x180072e72  movdqu  [rbp+150h+var_70], xmm6
0x180072e7a  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x180072e81  cmp     rax, 0Fh
0x180072e85  jbe     short loc_180072EC3
0x180072e87  mov     rcx, [rbp+150h+var_E0]; Block
0x180072e8b  mov     rdx, rcx
0x180072e8e  inc     rax
0x180072e91  cmp     rax, rbx
0x180072e94  jb      short loc_180072EBD
0x180072e96  mov     rcx, [rcx-8]
0x180072e9a  sub     rdx, rcx
0x180072e9d  lea     rax, [rdx-8]
0x180072ea1  cmp     rax, 1Fh
0x180072ea5  jbe     short loc_180072EBD
0x180072ea7  mov     [rsp+250h+Reserved], rsi; Reserved
0x180072eac  xor     r9d, r9d; LineNo
0x180072eaf  xor     r8d, r8d; FileName
0x180072eb2  xor     edx, edx; FunctionName
0x180072eb4  xor     ecx, ecx; Expression
0x180072eb6  call    cs:__imp__invoke_watson
0x180072ebd  call    cs:__imp_free
0x180072ec3  mov     rax, rsi
0x180072ec6  mov     [rsp+250h+var_220], rax
0x180072ecb  mov     rcx, [r15+1E8h]
0x180072ed2  mov     rbx, [r15+1E0h]
  ... truncated ...
```
