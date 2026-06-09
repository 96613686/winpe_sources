# RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>> &,CommandFlags)

- ea: `0x180066674`
- end: `0x1800672f1`
- name: `?CreateText@?$Table@VBlockSource@Tables@Meta@RepoMan@@V?$TablePolicy@UBlockSource@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@23@W4CommandFlags@@@Z`
- size: `3197`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180064a5c`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x180064d90`
- `0x180066674`
- `0x180068894`
- `0x180068954`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180066b7a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180066be0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180066b7a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180066be0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180066b73`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180066bd9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180066b73`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180066bd9`

## string_xrefs

- `0x18006699b`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x180066964`: `CREATE TABLE IF NOT EXISTS `
- `0x18006724c`: `CREATE TABLE IF NOT EXISTS `
- `0x180066a50`: ` AS incoming, `
- `0x180066e68`: `REPLACE INTO `
- `0x1800670b0`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v7; // r12
  __int64 v8; // rax
  _BYTE *v9; // rdx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  int v14; // ecx
  __int64 v15; // rax
  _BYTE *v16; // rdx
  __int64 v17; // rax
  __int64 *v18; // rsi
  _QWORD *v19; // rbx
  _BYTE *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdx
  __int64 v27; // rax
  _BYTE *v28; // rdx
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
  _BYTE *v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  _QWORD *v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  _BYTE *v52; // rdx
  __int64 v53; // rax
  void *v54; // rcx
  __m128i v55; // xmm6
  void *v56; // rcx
  __int64 v57; // rax
  __int64 *v58; // rbx
  _QWORD *v59; // rsi
  __int64 *v60; // r15
  _BYTE *v61; // rdx
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
  _BYTE v102[10]; // [rsp+158h] [rbp+50h] BYREF
  int v103; // [rsp+162h] [rbp+5Ah]
  __int16 v104; // [rsp+166h] [rbp+5Eh]
  __m128i si128; // [rsp+168h] [rbp+60h]
  void *v106[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v107; // [rsp+188h] [rbp+80h]
  _QWORD v108[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v109; // [rsp+1A8h] [rbp+A0h]
  __int128 v110; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v111; // [rsp+1C8h] [rbp+C0h]
  void *Block[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v113; // [rsp+1E8h] [rbp+E0h]
  _QWORD v114[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v115; // [rsp+208h] [rbp+100h]

  v7 = 0;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(v108);
    v104 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v102, "BlockSourc", sizeof(v102));
    v103 = (unsigned __int8)aBlocksource[10];
    v8 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v9 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v9 = *(_BYTE **)v102;
    v10 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v8, (__int64)v9, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v10, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v11,
      2050,
      (unsigned int)v108,
      (_DWORD)a1 + 448,
      (__int64)v98);
    v12 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" FROM ");
    v13 = v108;
    if ( v109.m128i_i64[1] > 0xFuLL )
      v13 = (_QWORD *)v108[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, (__int64)v13, v109.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v14,
      16,
      (unsigned int)v108,
      (unsigned int)v102,
      (__int64)v98);
    v15 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" LEFT OUTER JOIN ");
    v16 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v16 = *(_BYTE **)v102;
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
          v20 = *(_BYTE **)v102;
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
      v28 = *(_BYTE **)v102;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, si128.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    *(_OWORD *)v106 = 0;
    v107 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v106, "id");
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)v106, 2u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    std::string::_Tidy_deallocate(v106);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(v114);
    v32 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v33 = v114;
    if ( v115.m128i_i64[1] > 0xFuLL )
      v33 = (_QWORD *)v114[0];
    v34 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v32, (__int64)v33, v115.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v34,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v35 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"INSERT INTO ");
    v36 = v114;
    if ( v115.m128i_i64[1] > 0xFuLL )
      v36 = (_QWORD *)v114[0];
    v37 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v35, (__int64)v36, v115.m128i_u64[0]);
    v38 = std::operator<<<std::char_traits<char>>(v37, (__int64)" SELECT ");
    v39 = v108;
    if ( v109.m128i_i64[1] > 0xFuLL )
      v39 = (_QWORD *)v108[0];
    v40 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v38, (__int64)v39, v109.m128i_u64[0]);
    v41 = std::operator<<<std::char_traits<char>>(v40, (__int64)".");
    *(_OWORD *)v106 = 0;
    v107 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v106, "id");
    v42 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v41, (__int64)v106, 2u);
    v43 = std::operator<<<std::char_traits<char>>(v42, (__int64)" AS incoming, ");
    v44 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v44 = *(_BYTE **)v102;
    v45 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v43, (__int64)v44, si128.m128i_u64[0]);
    v46 = std::operator<<<std::char_traits<char>>(v45, (__int64)".");
    *(_OWORD *)Block = 0;
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)Block, "id");
    v47 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, (__int64)Block, 2u);
    v48 = std::operator<<<std::char_traits<char>>(v47, (__int64)" AS client FROM ");
    v49 = v108;
    if ( v109.m128i_i64[1] > 0xFuLL )
      v49 = (_QWORD *)v108[0];
    v50 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v48, (__int64)v49, v109.m128i_u64[0]);
    v51 = std::operator<<<std::char_traits<char>>(v50, (__int64)" INNER JOIN ");
    v52 = v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v52 = *(_BYTE **)v102;
    v53 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v51, (__int64)v52, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v53, (__int64)" ON (");
    if ( v113.m128i_i64[1] > 0xFuLL )
    {
      v54 = Block[0];
      if ( (unsigned __int64)(v113.m128i_i64[1] + 1) >= 0x1000 )
      {
        v54 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v54 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v54);
    }
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v113 = v55;
    if ( v107.m128i_i64[1] > 0xFuLL )
    {
      v56 = v106[0];
      if ( (unsigned __int64)(v107.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v106[0] - 1);
        if ( (unsigned __int64)((char *)v106[0] - (char *)v56 - 8) > 0x1F )
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
          v61 = *(_BYTE **)v102;
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v68,
      16,
      (unsigned int)v108,
      (unsigned int)v102,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
    v69 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v70 = v108;
    if ( v109.m128i_i64[1] > 0xFuLL )
      v70 = (_QWORD *)v108[0];
    v71 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v69, (__int64)v70, v109.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v71, (__int64)";");
    std::stringbuf::str(v100, a2);
    std::string::_Tidy_deallocate(v114);
    v114[0] = 19937;
    v115 = v55;
    std::string::_Tidy_deallocate(v102);
    *(_QWORD *)v102 = 19937;
    si128 = v55;
    std::string::_Tidy_deallocate(v108);
    v108[0] = 19937;
    v109 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(v106);
    v74 = v73[2];
    if ( v73[3] > 0xFu )
      v73 = (_QWORD *)*v73;
    v75 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v72, (__int64)v73, v74);
    std::operator<<<std::char_traits<char>>(v75, (__int64)";");
    std::string::_Tidy_deallocate(v106);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"BlockSource");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v106 = 0;
        v107 = 0;
        std::string::_Construct<1,char const *>(v106, "BlockSource", 0xBu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
          v90,
          4,
          (unsigned int)v106,
          (_DWORD)a1 + 448,
          (__int64)v98);
        std::string::_Tidy_deallocate(v106);
        std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x40u:
        v91 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"BlockSource");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"BlockSource");
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
    *(_OWORD *)v106 = 0;
    v107 = 0;
    std::string::_Construct<1,char const *>(v106, "BlockSource", 0xBu);
    v95(a1, v106);
    if ( v107.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v106, v106[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v106 = 0;
  v107 = 0;
  std::string::_Construct<1,char const *>(v106, "BlockSource", 0xBu);
  v76 = v106;
  v77 = 4;
LABEL_66:
  v110 = 0;
  v111 = 0;
  v110 = *(_OWORD *)v76;
  v111 = *((__m128i *)v76 + 1);
  *(_BYTE *)v76 = 0;
  v76[2] = 0;
  v76[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v106);
  }
  v78 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v113 = v78;
  }
  v79 = &v110;
  if ( v111.m128i_i64[1] > 0xFuLL )
    v79 = (__int128 *)v110;
  v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v99, (__int64)v79, v111.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v80, (__int64)"(");
  v81 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
    v82,
    a4,
    (unsigned int)&v110,
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v86,
      8,
      (unsigned int)&v110,
      v81,
      (__int64)v98);
    std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)";");
  std::stringbuf::str(v100, a2);
  std::string::_Tidy_deallocate(&v110);
  *(_QWORD *)&v110 = 19937;
  v111 = v78;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  v101[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
  return a2;
}

```

## disassembly

```asm
0x180066674  mov     rax, rsp
0x180066677  mov     [rax+18h], rbx
0x18006667b  mov     [rax+20h], rsi
0x18006667f  push    rbp
0x180066680  push    r12
0x180066682  push    r13
0x180066684  push    r14
0x180066686  push    r15
0x180066688  lea     rbp, [rax-158h]
0x18006668f  sub     rsp, 230h
0x180066696  movaps  xmmword ptr [rax-38h], xmm6
0x18006669a  mov     rax, cs:__security_cookie
0x1800666a1  xor     rax, rsp
0x1800666a4  mov     [rbp+150h+var_40], rax
0x1800666ab  movzx   esi, r9w
0x1800666af  mov     r14, rdx
0x1800666b2  mov     r15, rcx
0x1800666b5  mov     qword ptr [rsp+250h+var_218], rdx
0x1800666ba  xor     r12d, r12d
0x1800666bd  mov     [rsp+250h+var_210], r12d
0x1800666c2  lea     rcx, [rsp+250h+var_200]
0x1800666c7  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800666cc  nop
0x1800666cd  mov     eax, 800h
0x1800666d2  cmp     ax, si
0x1800666d5  jnz     loc_180066DAB
0x1800666db  lea     rcx, [rbp+150h+var_C0]
0x1800666e2  call    ?IndexName@?$Table@VBlockSource@Tables@Meta@RepoMan@@V?$TablePolicy@UBlockSource@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(void)
0x1800666e7  nop
0x1800666e8  xorps   xmm0, xmm0
0x1800666eb  movups  [rbp+150h+var_100], xmm0
0x1800666ef  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000b
0x1800666f7  movdqu  [rbp+150h+var_F0], xmm1
0x1800666fc  movsd   xmm0, qword ptr cs:aBlocksource; "BlockSource"
0x180066704  movsd   qword ptr [rbp+150h+var_100], xmm0
0x180066709  movzx   eax, word ptr cs:aBlocksource+8; "rce"
0x180066710  mov     word ptr [rbp+150h+var_100+8], ax
0x180066714  mov     al, byte ptr cs:aBlocksource+0Ah; "e"
0x18006671a  mov     byte ptr [rbp+150h+var_100+0Ah], al
0x18006671d  mov     byte ptr [rbp+150h+var_100+0Bh], r12b
0x180066721  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x180066728  lea     rcx, [rsp+250h+var_1F0]
0x18006672d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066732  lea     rdx, [rbp+150h+var_100]
0x180066736  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006673b  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180066740  mov     r8, qword ptr [rbp+150h+var_F0]
0x180066744  mov     rcx, rax
0x180066747  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006674c  lea     rdx, aSelectNull; " SELECT NULL"
0x180066753  mov     rcx, rax
0x180066756  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006675b  lea     r9, [r15+1C0h]
0x180066762  mov     edx, 802h
0x180066767  lea     rax, [rsp+250h+var_200]
0x18006676c  mov     [rsp+250h+Reserved], rax
0x180066771  lea     r8, [rbp+150h+var_C0]
0x180066778  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18006677d  lea     rdx, aFrom_0; " FROM "
0x180066784  lea     rcx, [rsp+250h+var_1F0]
0x180066789  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006678e  lea     rdx, [rbp+150h+var_C0]
0x180066795  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x18006679d  cmova   rdx, [rbp+150h+var_C0]
0x1800667a5  mov     r8, qword ptr [rbp+150h+var_B0]
0x1800667ac  mov     rcx, rax
0x1800667af  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800667b4  lea     edx, [r12+10h]
0x1800667b9  lea     rax, [rsp+250h+var_200]
0x1800667be  mov     [rsp+250h+Reserved], rax
0x1800667c3  lea     r9, [rbp+150h+var_100]
0x1800667c7  lea     r8, [rbp+150h+var_C0]
0x1800667ce  call    ?BuildText@?$RowType@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x1800667d3  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x1800667da  lea     rcx, [rsp+250h+var_1F0]
0x1800667df  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800667e4  lea     rdx, [rbp+150h+var_100]
0x1800667e8  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x1800667ed  cmova   rdx, qword ptr [rbp+150h+var_100]
0x1800667f2  mov     r8, qword ptr [rbp+150h+var_F0]
0x1800667f6  mov     rcx, rax
0x1800667f9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800667fe  lea     rdx, aOn; " ON ("
0x180066805  mov     rcx, rax
0x180066808  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006680d  mov     rax, [r15+1E8h]
0x180066814  mov     [rsp+250h+var_220], rax
0x180066819  mov     rsi, [r15+1E0h]
0x180066820  lea     r13d, [r12+40h]
0x180066825  cmp     rsi, rax
0x180066828  jz      loc_1800668C8
0x18006682e  lea     rbx, [rsi+38h]
0x180066832  test    r12, r12
0x180066835  jz      short loc_180066848
0x180066837  lea     rdx, aAnd_1; " AND "
0x18006683e  lea     rcx, [rsp+250h+var_1F0]
0x180066843  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066848  lea     rdx, [rbp+150h+var_100]
0x18006684c  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180066851  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180066856  mov     r8, qword ptr [rbp+150h+var_F0]
0x18006685a  lea     rcx, [rsp+250h+var_1F0]
0x18006685f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066864  lea     rdx, asc_1801D0CE8; "."
0x18006686b  mov     rcx, rax
0x18006686e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066873  mov     rdx, rsi
0x180066876  cmp     qword ptr [rbx-20h], 0Fh
0x18006687b  jbe     short loc_180066880
0x18006687d  mov     rdx, [rsi]
0x180066880  mov     r8, [rbx-28h]
0x180066884  mov     rcx, rax
0x180066887  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006688c  lea     rdx, asc_1801D5B8C; " = "
0x180066893  mov     rcx, rax
0x180066896  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006689b  lea     rdx, [rbx-18h]
0x18006689f  cmp     qword ptr [rbx], 0Fh
0x1800668a3  jbe     short loc_1800668A8
0x1800668a5  mov     rdx, [rdx]
0x1800668a8  mov     r8, [rbx-8]
0x1800668ac  mov     rcx, rax
0x1800668af  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800668b4  inc     r12
0x1800668b7  add     rsi, r13
0x1800668ba  add     rbx, r13
0x1800668bd  cmp     rsi, [rsp+250h+var_220]
0x1800668c2  jnz     loc_180066832
0x1800668c8  lea     rdx, aWhere; ") WHERE "
0x1800668cf  lea     rcx, [rsp+250h+var_1F0]
0x1800668d4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800668d9  lea     rdx, [rbp+150h+var_100]
0x1800668dd  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x1800668e2  cmova   rdx, qword ptr [rbp+150h+var_100]
0x1800668e7  mov     r8, qword ptr [rbp+150h+var_F0]
0x1800668eb  mov     rcx, rax
0x1800668ee  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800668f3  lea     r12, asc_1801D0CE8; "."
0x1800668fa  mov     rdx, r12
0x1800668fd  mov     rcx, rax
0x180066900  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066905  nop
0x180066906  xorps   xmm0, xmm0
0x180066909  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x18006690d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180066915  movdqu  [rbp+150h+var_D0], xmm1
0x18006691d  mov     esi, 6469h
0x180066922  mov     word ptr [rbp+150h+var_E0], si
0x180066926  mov     byte ptr [rbp+150h+var_E0+2], 0
0x18006692a  mov     ebx, 2
0x18006692f  mov     r8d, ebx
0x180066932  lea     rdx, [rbp+150h+var_E0]
0x180066936  mov     rcx, rax
0x180066939  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006693e  lea     rdx, aIsNull; " IS NULL;"
0x180066945  mov     rcx, rax
0x180066948  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006694d  nop
0x18006694e  lea     rcx, [rbp+150h+var_E0]
0x180066952  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180066957  lea     rcx, [rbp+150h+var_60]
0x18006695e  call    ?MapName@?$Table@VBlockSource@Tables@Meta@RepoMan@@V?$TablePolicy@UBlockSource@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UId@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UNull@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::BlockSource,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Null,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(void)
0x180066963  nop
0x180066964  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18006696b  lea     rcx, [rsp+250h+var_1F0]
0x180066970  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066975  lea     rdx, [rbp+150h+var_60]
0x18006697c  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x180066984  cmova   rdx, [rbp+150h+var_60]
0x18006698c  mov     r8, qword ptr [rbp+150h+var_50]
0x180066993  mov     rcx, rax
0x180066996  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006699b  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x1800669a2  mov     rcx, rax
0x1800669a5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800669aa  lea     rdx, aInsertInto; "INSERT INTO "
0x1800669b1  lea     rcx, [rsp+250h+var_1F0]
0x1800669b6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800669bb  lea     rdx, [rbp+150h+var_60]
0x1800669c2  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x1800669ca  cmova   rdx, [rbp+150h+var_60]
0x1800669d2  mov     r8, qword ptr [rbp+150h+var_50]
0x1800669d9  mov     rcx, rax
0x1800669dc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800669e1  lea     rdx, aSelect; " SELECT "
0x1800669e8  mov     rcx, rax
0x1800669eb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800669f0  lea     rdx, [rbp+150h+var_C0]
0x1800669f7  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x1800669ff  cmova   rdx, [rbp+150h+var_C0]
0x180066a07  mov     r8, qword ptr [rbp+150h+var_B0]
0x180066a0e  mov     rcx, rax
0x180066a11  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066a16  mov     rdx, r12
0x180066a19  mov     rcx, rax
0x180066a1c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066a21  nop
0x180066a22  xorps   xmm0, xmm0
0x180066a25  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180066a29  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180066a31  movdqu  [rbp+150h+var_D0], xmm1
0x180066a39  mov     word ptr [rbp+150h+var_E0], si
0x180066a3d  mov     byte ptr [rbp+150h+var_E0+2], 0
0x180066a41  mov     r8d, ebx
0x180066a44  lea     rdx, [rbp+150h+var_E0]
0x180066a48  mov     rcx, rax
0x180066a4b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066a50  lea     rdx, aAsIncoming; " AS incoming, "
0x180066a57  mov     rcx, rax
0x180066a5a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066a5f  lea     rdx, [rbp+150h+var_100]
0x180066a63  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180066a68  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180066a6d  mov     r8, qword ptr [rbp+150h+var_F0]
0x180066a71  mov     rcx, rax
0x180066a74  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066a79  mov     rdx, r12
0x180066a7c  mov     rcx, rax
0x180066a7f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066a84  nop
0x180066a85  xorps   xmm0, xmm0
0x180066a88  movups  xmmword ptr [rbp+150h+Block], xmm0
0x180066a8f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000002
0x180066a97  movdqu  [rbp+150h+var_70], xmm1
0x180066a9f  mov     word ptr [rbp+150h+Block], si
0x180066aa6  xor     esi, esi
0x180066aa8  mov     byte ptr [rbp+150h+Block+2], sil
0x180066aaf  mov     r8d, ebx
0x180066ab2  lea     rdx, [rbp+150h+Block]
0x180066ab9  mov     rcx, rax
0x180066abc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066ac1  lea     rdx, aAsClientFrom; " AS client FROM "
0x180066ac8  mov     rcx, rax
0x180066acb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066ad0  lea     rdx, [rbp+150h+var_C0]
0x180066ad7  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180066adf  cmova   rdx, [rbp+150h+var_C0]
0x180066ae7  mov     r8, qword ptr [rbp+150h+var_B0]
0x180066aee  mov     rcx, rax
0x180066af1  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066af6  lea     rdx, aInnerJoin; " INNER JOIN "
0x180066afd  mov     rcx, rax
0x180066b00  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066b05  lea     rdx, [rbp+150h+var_100]
0x180066b09  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180066b0e  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180066b13  mov     r8, qword ptr [rbp+150h+var_F0]
0x180066b17  mov     rcx, rax
0x180066b1a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180066b1f  lea     rdx, aOn; " ON ("
0x180066b26  mov     rcx, rax
0x180066b29  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180066b2e  nop
0x180066b2f  mov     ebx, 1000h
0x180066b34  mov     rax, qword ptr [rbp+150h+var_70+8]
0x180066b3b  cmp     rax, 0Fh
0x180066b3f  jbe     short loc_180066B80
0x180066b41  mov     rcx, [rbp+150h+Block]; Block
0x180066b48  mov     rdx, rcx
0x180066b4b  inc     rax
0x180066b4e  cmp     rax, rbx
0x180066b51  jb      short loc_180066B7A
0x180066b53  mov     rcx, [rcx-8]
0x180066b57  sub     rdx, rcx
0x180066b5a  lea     rax, [rdx-8]
0x180066b5e  cmp     rax, 1Fh
0x180066b62  jbe     short loc_180066B7A
0x180066b64  mov     [rsp+250h+Reserved], rsi; Reserved
0x180066b69  xor     r9d, r9d; LineNo
0x180066b6c  xor     r8d, r8d; FileName
0x180066b6f  xor     edx, edx; FunctionName
0x180066b71  xor     ecx, ecx; Expression
0x180066b73  call    cs:__imp__invoke_watson
0x180066b7a  call    cs:__imp_free
0x180066b80  mov     r12d, 4DE1h
0x180066b86  mov     [rbp+150h+Block], r12
0x180066b8d  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x180066b95  movdqu  [rbp+150h+var_70], xmm6
0x180066b9d  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x180066ba4  cmp     rax, 0Fh
0x180066ba8  jbe     short loc_180066BE6
0x180066baa  mov     rcx, [rbp+150h+var_E0]; Block
0x180066bae  mov     rdx, rcx
0x180066bb1  inc     rax
0x180066bb4  cmp     rax, rbx
0x180066bb7  jb      short loc_180066BE0
0x180066bb9  mov     rcx, [rcx-8]
0x180066bbd  sub     rdx, rcx
0x180066bc0  lea     rax, [rdx-8]
0x180066bc4  cmp     rax, 1Fh
0x180066bc8  jbe     short loc_180066BE0
0x180066bca  mov     [rsp+250h+Reserved], rsi; Reserved
0x180066bcf  xor     r9d, r9d; LineNo
0x180066bd2  xor     r8d, r8d; FileName
0x180066bd5  xor     edx, edx; FunctionName
0x180066bd7  xor     ecx, ecx; Expression
0x180066bd9  call    cs:__imp__invoke_watson
0x180066be0  call    cs:__imp_free
0x180066be6  mov     rax, rsi
0x180066be9  mov     [rsp+250h+var_220], rax
  ... truncated ...
```
