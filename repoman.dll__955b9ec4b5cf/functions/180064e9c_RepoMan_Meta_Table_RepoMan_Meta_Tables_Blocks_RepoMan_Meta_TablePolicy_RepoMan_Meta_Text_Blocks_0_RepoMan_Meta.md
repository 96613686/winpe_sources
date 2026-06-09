# RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>> &,CommandFlags)

- ea: `0x180064e9c`
- end: `0x180065b0b`
- name: `?CreateText@?$Table@VBlocks@Tables@Meta@RepoMan@@V?$TablePolicy@UBlocks@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@23@W4CommandFlags@@@Z`
- size: `3183`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180062c58`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x180062f8c`
- `0x180064e9c`
- `0x1800672f4`
- `0x1800673b4`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800653a2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006540c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800653a2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006540c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006539b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180065405`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006539b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180065405`

## string_xrefs

- `0x1800651bd`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x180065186`: `CREATE TABLE IF NOT EXISTS `
- `0x180065a6b`: `CREATE TABLE IF NOT EXISTS `
- `0x180065276`: ` AS incoming, `
- `0x180065698`: `REPLACE INTO `
- `0x1800658df`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v7; // rax
  __int128 *v8; // rdx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  int v13; // ecx
  __int64 v14; // rax
  __int128 *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r12
  __int64 *v18; // rsi
  _QWORD *v19; // rbx
  __int128 *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdx
  __int64 v27; // rax
  __int128 *v28; // rdx
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
  __int128 *v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  _QWORD *v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  __int128 *v52; // rdx
  __int64 v53; // rax
  void *v54; // rcx
  __m128i v55; // xmm6
  void *v56; // rcx
  __int64 v57; // rax
  __int64 *v58; // rbx
  _QWORD *v59; // rsi
  __int64 *v60; // r15
  __int128 *v61; // rdx
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
  __int128 v102; // [rsp+158h] [rbp+50h] BYREF
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

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(v106);
    v102 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)&v102, "Blocks");
    v7 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v102;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v10,
      2050,
      (unsigned int)v106,
      (_DWORD)a1 + 448,
      (__int64)v98);
    v11 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" FROM ");
    v12 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v12 = (_QWORD *)v106[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, (__int64)v12, v107.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v13,
      16,
      (unsigned int)v106,
      (unsigned int)&v102,
      (__int64)v98);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" LEFT OUTER JOIN ");
    v15 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v15 = (__int128 *)v102;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v16, (__int64)" ON (");
    v17 = 0;
    v96 = (__int64 *)a1[61];
    v18 = (__int64 *)a1[60];
    if ( v18 != v96 )
    {
      v19 = v18 + 7;
      do
      {
        if ( v17 )
          std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" AND ");
        v20 = &v102;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v20 = (__int128 *)v102;
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
        ++v17;
        v18 += 8;
        v19 += 8;
      }
      while ( v18 != v96 );
    }
    v27 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)") WHERE ");
    v28 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v28 = (__int128 *)v102;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, si128.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v104[1] = 0;
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    v104[0] = (void *)0x64695F6B636F6C62LL;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)v104, 8u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    std::string::_Tidy_deallocate(v104);
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(v112);
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
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    v104[0] = (void *)0x64695F6B636F6C62LL;
    v104[1] = 0;
    v42 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v41, (__int64)v104, 8u);
    v43 = std::operator<<<std::char_traits<char>>(v42, (__int64)" AS incoming, ");
    v44 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v44 = (__int128 *)v102;
    v45 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v43, (__int64)v44, si128.m128i_u64[0]);
    v46 = std::operator<<<std::char_traits<char>>(v45, (__int64)".");
    v111 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = (void *)0x64695F6B636F6C62LL;
    Block[1] = 0;
    v47 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, (__int64)Block, 8u);
    v48 = std::operator<<<std::char_traits<char>>(v47, (__int64)" AS client FROM ");
    v49 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v49 = (_QWORD *)v106[0];
    v50 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v48, (__int64)v49, v107.m128i_u64[0]);
    v51 = std::operator<<<std::char_traits<char>>(v50, (__int64)" INNER JOIN ");
    v52 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v52 = (__int128 *)v102;
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
        v61 = &v102;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v61 = (__int128 *)v102;
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
      v68,
      16,
      (unsigned int)v106,
      (unsigned int)&v102,
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
    std::string::_Tidy_deallocate(&v102);
    *(_QWORD *)&v102 = 19937;
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
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(v104);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"Blocks");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v104 = 0;
        v105 = 0;
        std::string::_Construct<1,char const *>(v104, "Blocks", 6u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
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
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"Blocks");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"Blocks");
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
    std::string::_Construct<1,char const *>(v104, "Blocks", 6u);
    v95(a1, v104);
    if ( v105.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v104, v104[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v104 = 0;
  v105 = 0;
  std::string::_Construct<1,char const *>(v104, "Blocks", 6u);
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
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(
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
0x180064e9c  mov     rax, rsp
0x180064e9f  mov     [rax+18h], rbx
0x180064ea3  mov     [rax+20h], rsi
0x180064ea7  push    rbp
0x180064ea8  push    r12
0x180064eaa  push    r13
0x180064eac  push    r14
0x180064eae  push    r15
0x180064eb0  lea     rbp, [rax-158h]
0x180064eb7  sub     rsp, 230h
0x180064ebe  movaps  xmmword ptr [rax-38h], xmm6
0x180064ec2  mov     rax, cs:__security_cookie
0x180064ec9  xor     rax, rsp
0x180064ecc  mov     [rbp+150h+var_40], rax
0x180064ed3  movzx   esi, r9w
0x180064ed7  mov     r14, rdx
0x180064eda  mov     r15, rcx
0x180064edd  mov     qword ptr [rsp+250h+var_218], rdx
0x180064ee2  xor     r13d, r13d
0x180064ee5  mov     [rsp+250h+var_210], r13d
0x180064eea  lea     rcx, [rsp+250h+var_200]
0x180064eef  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180064ef4  nop
0x180064ef5  mov     eax, 800h
0x180064efa  cmp     ax, si
0x180064efd  jnz     loc_1800655D6
0x180064f03  lea     rcx, [rbp+150h+var_C0]
0x180064f0a  call    ?IndexName@?$Table@VBlocks@Tables@Meta@RepoMan@@V?$TablePolicy@UBlocks@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::IndexName(void)
0x180064f0f  nop
0x180064f10  xorps   xmm0, xmm0
0x180064f13  movups  [rbp+150h+var_100], xmm0
0x180064f17  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000006
0x180064f1f  movdqu  [rbp+150h+var_F0], xmm1
0x180064f24  mov     eax, dword ptr cs:aBlocks; "Blocks"
0x180064f2a  mov     dword ptr [rbp+150h+var_100], eax
0x180064f2d  movzx   eax, word ptr cs:aBlocks+4; "ks"
0x180064f34  mov     word ptr [rbp+150h+var_100+4], ax
0x180064f38  mov     byte ptr [rbp+150h+var_100+6], r13b
0x180064f3c  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x180064f43  lea     rcx, [rsp+250h+var_1F0]
0x180064f48  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180064f4d  lea     rdx, [rbp+150h+var_100]
0x180064f51  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180064f56  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180064f5b  mov     r8, qword ptr [rbp+150h+var_F0]
0x180064f5f  mov     rcx, rax
0x180064f62  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180064f67  lea     rdx, aSelectNull; " SELECT NULL"
0x180064f6e  mov     rcx, rax
0x180064f71  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180064f76  lea     r9, [r15+1C0h]
0x180064f7d  mov     edx, 802h
0x180064f82  lea     rax, [rsp+250h+var_200]
0x180064f87  mov     [rsp+250h+Reserved], rax
0x180064f8c  lea     r8, [rbp+150h+var_C0]
0x180064f93  call    ?BuildText@?$RowType@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180064f98  lea     rdx, aFrom_0; " FROM "
0x180064f9f  lea     rcx, [rsp+250h+var_1F0]
0x180064fa4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180064fa9  lea     rdx, [rbp+150h+var_C0]
0x180064fb0  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180064fb8  cmova   rdx, [rbp+150h+var_C0]
0x180064fc0  mov     r8, qword ptr [rbp+150h+var_B0]
0x180064fc7  mov     rcx, rax
0x180064fca  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180064fcf  lea     edx, [r13+10h]
0x180064fd3  lea     rax, [rsp+250h+var_200]
0x180064fd8  mov     [rsp+250h+Reserved], rax
0x180064fdd  lea     r9, [rbp+150h+var_100]
0x180064fe1  lea     r8, [rbp+150h+var_C0]
0x180064fe8  call    ?BuildText@?$RowType@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180064fed  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x180064ff4  lea     rcx, [rsp+250h+var_1F0]
0x180064ff9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180064ffe  lea     rdx, [rbp+150h+var_100]
0x180065002  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180065007  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18006500c  mov     r8, qword ptr [rbp+150h+var_F0]
0x180065010  mov     rcx, rax
0x180065013  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065018  lea     rdx, aOn; " ON ("
0x18006501f  mov     rcx, rax
0x180065022  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065027  mov     r12d, r13d
0x18006502a  mov     rax, [r15+1E8h]
0x180065031  mov     [rsp+250h+var_220], rax
0x180065036  mov     rsi, [r15+1E0h]
0x18006503d  lea     r13d, [r12+40h]
0x180065042  cmp     rsi, rax
0x180065045  jz      loc_1800650E5
0x18006504b  lea     rbx, [rsi+38h]
0x18006504f  test    r12, r12
0x180065052  jz      short loc_180065065
0x180065054  lea     rdx, aAnd_1; " AND "
0x18006505b  lea     rcx, [rsp+250h+var_1F0]
0x180065060  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065065  lea     rdx, [rbp+150h+var_100]
0x180065069  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006506e  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180065073  mov     r8, qword ptr [rbp+150h+var_F0]
0x180065077  lea     rcx, [rsp+250h+var_1F0]
0x18006507c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065081  lea     rdx, asc_1801D0CE8; "."
0x180065088  mov     rcx, rax
0x18006508b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065090  mov     rdx, rsi
0x180065093  cmp     qword ptr [rbx-20h], 0Fh
0x180065098  jbe     short loc_18006509D
0x18006509a  mov     rdx, [rsi]
0x18006509d  mov     r8, [rbx-28h]
0x1800650a1  mov     rcx, rax
0x1800650a4  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800650a9  lea     rdx, asc_1801D5B8C; " = "
0x1800650b0  mov     rcx, rax
0x1800650b3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800650b8  lea     rdx, [rbx-18h]
0x1800650bc  cmp     qword ptr [rbx], 0Fh
0x1800650c0  jbe     short loc_1800650C5
0x1800650c2  mov     rdx, [rdx]
0x1800650c5  mov     r8, [rbx-8]
0x1800650c9  mov     rcx, rax
0x1800650cc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800650d1  inc     r12
0x1800650d4  add     rsi, r13
0x1800650d7  add     rbx, r13
0x1800650da  cmp     rsi, [rsp+250h+var_220]
0x1800650df  jnz     loc_18006504F
0x1800650e5  lea     rdx, aWhere; ") WHERE "
0x1800650ec  lea     rcx, [rsp+250h+var_1F0]
0x1800650f1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800650f6  lea     rdx, [rbp+150h+var_100]
0x1800650fa  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x1800650ff  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180065104  mov     r8, qword ptr [rbp+150h+var_F0]
0x180065108  mov     rcx, rax
0x18006510b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065110  lea     rdx, asc_1801D0CE8; "."
0x180065117  mov     rcx, rax
0x18006511a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006511f  nop
0x180065120  xorps   xmm0, xmm0
0x180065123  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x180065127  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000008
0x18006512f  movdqu  [rbp+150h+var_D0], xmm1
0x180065137  mov     rbx, 64695F6B636F6C62h
0x180065141  mov     [rbp+150h+var_E0], rbx
0x180065145  xor     r12d, r12d
0x180065148  mov     byte ptr [rbp+150h+var_E0+8], r12b
0x18006514c  lea     esi, [r12+8]
0x180065151  mov     r8d, esi
0x180065154  lea     rdx, [rbp+150h+var_E0]
0x180065158  mov     rcx, rax
0x18006515b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065160  lea     rdx, aIsNull; " IS NULL;"
0x180065167  mov     rcx, rax
0x18006516a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006516f  nop
0x180065170  lea     rcx, [rbp+150h+var_E0]
0x180065174  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065179  lea     rcx, [rbp+150h+var_60]
0x180065180  call    ?MapName@?$Table@VBlocks@Tables@Meta@RepoMan@@V?$TablePolicy@UBlocks@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UBlock_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBlocks@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UFile_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFiles@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UHash_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UHashes@234@UB@Alias@34@@Meta@RepoMan@@_J@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Blocks,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Blocks,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Block_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Blocks,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::File_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Files,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Hash_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Hashes,RepoMan::Meta::Alias::B>,__int64>>::MapName(void)
0x180065185  nop
0x180065186  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18006518d  lea     rcx, [rsp+250h+var_1F0]
0x180065192  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065197  lea     rdx, [rbp+150h+var_60]
0x18006519e  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x1800651a6  cmova   rdx, [rbp+150h+var_60]
0x1800651ae  mov     r8, qword ptr [rbp+150h+var_50]
0x1800651b5  mov     rcx, rax
0x1800651b8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800651bd  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x1800651c4  mov     rcx, rax
0x1800651c7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800651cc  lea     rdx, aInsertInto; "INSERT INTO "
0x1800651d3  lea     rcx, [rsp+250h+var_1F0]
0x1800651d8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800651dd  lea     rdx, [rbp+150h+var_60]
0x1800651e4  cmp     qword ptr [rbp+150h+var_50+8], 0Fh
0x1800651ec  cmova   rdx, [rbp+150h+var_60]
0x1800651f4  mov     r8, qword ptr [rbp+150h+var_50]
0x1800651fb  mov     rcx, rax
0x1800651fe  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065203  lea     rdx, aSelect; " SELECT "
0x18006520a  mov     rcx, rax
0x18006520d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065212  lea     rdx, [rbp+150h+var_C0]
0x180065219  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180065221  cmova   rdx, [rbp+150h+var_C0]
0x180065229  mov     r8, qword ptr [rbp+150h+var_B0]
0x180065230  mov     rcx, rax
0x180065233  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065238  lea     rdx, asc_1801D0CE8; "."
0x18006523f  mov     rcx, rax
0x180065242  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065247  nop
0x180065248  xorps   xmm0, xmm0
0x18006524b  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x18006524f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000008
0x180065257  movdqu  [rbp+150h+var_D0], xmm1
0x18006525f  mov     [rbp+150h+var_E0], rbx
0x180065263  mov     byte ptr [rbp+150h+var_E0+8], r12b
0x180065267  mov     r8d, esi
0x18006526a  lea     rdx, [rbp+150h+var_E0]
0x18006526e  mov     rcx, rax
0x180065271  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065276  lea     rdx, aAsIncoming; " AS incoming, "
0x18006527d  mov     rcx, rax
0x180065280  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065285  lea     rdx, [rbp+150h+var_100]
0x180065289  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x18006528e  cmova   rdx, qword ptr [rbp+150h+var_100]
0x180065293  mov     r8, qword ptr [rbp+150h+var_F0]
0x180065297  mov     rcx, rax
0x18006529a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006529f  lea     rdx, asc_1801D0CE8; "."
0x1800652a6  mov     rcx, rax
0x1800652a9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800652ae  nop
0x1800652af  xorps   xmm0, xmm0
0x1800652b2  movups  xmmword ptr [rbp+150h+Block], xmm0
0x1800652b9  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000008
0x1800652c1  movdqu  [rbp+150h+var_70], xmm1
0x1800652c9  mov     [rbp+150h+Block], rbx
0x1800652d0  mov     byte ptr [rbp+150h+Block+8], r12b
0x1800652d7  mov     r8d, esi
0x1800652da  lea     rdx, [rbp+150h+Block]
0x1800652e1  mov     rcx, rax
0x1800652e4  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800652e9  lea     rdx, aAsClientFrom; " AS client FROM "
0x1800652f0  mov     rcx, rax
0x1800652f3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800652f8  lea     rdx, [rbp+150h+var_C0]
0x1800652ff  cmp     qword ptr [rbp+150h+var_B0+8], 0Fh
0x180065307  cmova   rdx, [rbp+150h+var_C0]
0x18006530f  mov     r8, qword ptr [rbp+150h+var_B0]
0x180065316  mov     rcx, rax
0x180065319  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006531e  lea     rdx, aInnerJoin; " INNER JOIN "
0x180065325  mov     rcx, rax
0x180065328  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006532d  lea     rdx, [rbp+150h+var_100]
0x180065331  cmp     qword ptr [rbp+150h+var_F0+8], 0Fh
0x180065336  cmova   rdx, qword ptr [rbp+150h+var_100]
0x18006533b  mov     r8, qword ptr [rbp+150h+var_F0]
0x18006533f  mov     rcx, rax
0x180065342  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180065347  lea     rdx, aOn; " ON ("
0x18006534e  mov     rcx, rax
0x180065351  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180065356  nop
0x180065357  mov     ebx, 1000h
0x18006535c  mov     rax, qword ptr [rbp+150h+var_70+8]
0x180065363  cmp     rax, 0Fh
0x180065367  jbe     short loc_1800653A8
0x180065369  mov     rcx, [rbp+150h+Block]; Block
0x180065370  mov     rdx, rcx
0x180065373  inc     rax
0x180065376  cmp     rax, rbx
0x180065379  jb      short loc_1800653A2
0x18006537b  mov     rcx, [rcx-8]
0x18006537f  sub     rdx, rcx
0x180065382  lea     rax, [rdx-8]
0x180065386  cmp     rax, 1Fh
0x18006538a  jbe     short loc_1800653A2
0x18006538c  mov     [rsp+250h+Reserved], r12; Reserved
0x180065391  xor     r9d, r9d; LineNo
0x180065394  xor     r8d, r8d; FileName
0x180065397  xor     edx, edx; FunctionName
0x180065399  xor     ecx, ecx; Expression
0x18006539b  call    cs:__imp__invoke_watson
0x1800653a2  call    cs:__imp_free
0x1800653a8  mov     r12d, 4DE1h
0x1800653ae  mov     [rbp+150h+Block], r12
0x1800653b5  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800653bd  movdqu  [rbp+150h+var_70], xmm6
0x1800653c5  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x1800653cc  cmp     rax, 0Fh
0x1800653d0  jbe     short loc_180065412
0x1800653d2  mov     rcx, [rbp+150h+var_E0]; Block
0x1800653d6  mov     rdx, rcx
0x1800653d9  inc     rax
0x1800653dc  cmp     rax, rbx
0x1800653df  jb      short loc_18006540C
0x1800653e1  mov     rcx, [rcx-8]
0x1800653e5  sub     rdx, rcx
0x1800653e8  lea     rax, [rdx-8]
0x1800653ec  cmp     rax, 1Fh
0x1800653f0  jbe     short loc_18006540C
0x1800653f2  mov     [rsp+250h+Reserved], 0; Reserved
0x1800653fb  xor     r9d, r9d; LineNo
0x1800653fe  xor     r8d, r8d; FileName
0x180065401  xor     edx, edx; FunctionName
0x180065403  xor     ecx, ecx; Expression
0x180065405  call    cs:__imp__invoke_watson
0x18006540c  call    cs:__imp_free
0x180065412  xor     eax, eax
0x180065414  mov     [rsp+250h+var_220], rax
0x180065419  mov     rcx, [r15+1E8h]
0x180065420  mov     rbx, [r15+1E0h]
  ... truncated ...
```
