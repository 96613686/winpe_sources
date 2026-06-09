# RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>> &,CommandFlags)

- ea: `0x1800613e4`
- end: `0x180062106`
- name: `?CreateText@?$Table@VPaths@Tables@Meta@RepoMan@@V?$TablePolicy@UPaths@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@23@@23@W4CommandFlags@@@Z`
- size: `3362`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005f278`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18005f614`
- `0x1800613e4`
- `0x180063e38`
- `0x180063ef0`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061765`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800619eb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061765`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800619eb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006175e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800619e4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006175e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800619e4`

## string_xrefs

- `0x1800616ca`: `path_id`
- `0x18006184f`: `path_id`
- `0x1800618d1`: `path_id`
- `0x1800614b1`: `Paths`
- `0x180061c66`: `Paths`
- `0x1800617af`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x180061778`: `CREATE TABLE IF NOT EXISTS `
- `0x180062066`: `CREATE TABLE IF NOT EXISTS `
- `0x180061880`: ` AS incoming, `
- `0x180061c93`: `REPLACE INTO `
- `0x180061eda`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::CreateText(
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
  void *v32; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  _QWORD *v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int128 *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int128 *v53; // rdx
  __int64 v54; // rax
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
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v109; // [rsp+1C8h] [rbp+C0h]
  __int128 v110; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v111; // [rsp+1E8h] [rbp+E0h]
  _QWORD v112[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v113; // [rsp+208h] [rbp+100h]
  __int64 v114; // [rsp+218h] [rbp+110h]
  __int128 v115; // [rsp+220h] [rbp+118h] BYREF
  _OWORD v116[2]; // [rsp+230h] [rbp+128h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    v114 = 0;
    v115 = 0;
    v116[0] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v115) = 0;
    v116[1] = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::IndexName(v106);
    v102 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LODWORD(v102) = *(_DWORD *)"Paths";
    WORD2(v102) = (unsigned __int8)aPaths[4];
    v7 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v102;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
    HIWORD(Block[1]) = 0;
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(Block, "path_i", 6);
    *(void **)((char *)Block + 6) = (void *)(unsigned __int8)aPathId[6];
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 7u);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    if ( v109.m128i_i64[1] > 0xFuLL )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(v109.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::MapName(v112);
    v33 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v34 = v112;
    if ( v113.m128i_i64[1] > 0xFuLL )
      v34 = (_QWORD *)v112[0];
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, (__int64)v34, v113.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v35,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v36 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"INSERT INTO ");
    v37 = v112;
    if ( v113.m128i_i64[1] > 0xFuLL )
      v37 = (_QWORD *)v112[0];
    v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, (__int64)v37, v113.m128i_u64[0]);
    v39 = std::operator<<<std::char_traits<char>>(v38, (__int64)" SELECT ");
    v40 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v40 = (_QWORD *)v106[0];
    v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, (__int64)v40, v107.m128i_u64[0]);
    v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)".");
    HIWORD(v104[1]) = 0;
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v104, "path_i", 6);
    *(void **)((char *)v104 + 6) = (void *)(unsigned __int8)aPathId[6];
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v104, 7u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v45 = (__int128 *)v102;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, si128.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    HIWORD(Block[1]) = 0;
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(Block, "path_i", 6);
    *(void **)((char *)Block + 6) = (void *)(unsigned __int8)aPathId[6];
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 7u);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v106[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v107.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = &v102;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v53 = (__int128 *)v102;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, si128.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v54, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v109 = v55;
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
    std::string::_Tidy_deallocate(&v115);
    *(_QWORD *)&v115 = 19937;
    v116[0] = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::MapName(v104);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"Paths");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v104 = 0;
        v105 = 0;
        std::string::_Construct<1,char const *>(v104, "Paths", 5u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"Paths");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"Paths");
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
    std::string::_Construct<1,char const *>(v104, "Paths", 5u);
    v95(a1, v104);
    if ( v105.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v104, v104[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v104 = 0;
  v105 = 0;
  std::string::_Construct<1,char const *>(v104, "Paths", 5u);
  v76 = v104;
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
    std::string::_Tidy_deallocate(v104);
  }
  v78 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v109 = v78;
  }
  v79 = &v110;
  if ( v111.m128i_i64[1] > 0xFuLL )
    v79 = (__int128 *)v110;
  v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v99, (__int64)v79, v111.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v80, (__int64)"(");
  v81 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(
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
0x1800613e4  mov     rax, rsp
0x1800613e7  mov     [rax+18h], rbx
0x1800613eb  mov     [rax+20h], rsi
0x1800613ef  push    rbp
0x1800613f0  push    r12
0x1800613f2  push    r13
0x1800613f4  push    r14
0x1800613f6  push    r15
0x1800613f8  lea     rbp, [rax-188h]
0x1800613ff  sub     rsp, 260h
0x180061406  movaps  xmmword ptr [rax-38h], xmm6
0x18006140a  mov     rax, cs:__security_cookie
0x180061411  xor     rax, rsp
0x180061414  mov     [rbp+180h+var_38], rax
0x18006141b  movzx   esi, r9w
0x18006141f  mov     r14, rdx
0x180061422  mov     r15, rcx
0x180061425  mov     qword ptr [rsp+280h+var_248], rdx
0x18006142a  xor     r13d, r13d
0x18006142d  mov     [rsp+280h+var_240], r13d
0x180061432  lea     rcx, [rsp+280h+var_230]
0x180061437  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18006143c  nop
0x18006143d  mov     eax, 800h
0x180061442  cmp     ax, si
0x180061445  jnz     loc_180061BD1
0x18006144b  xorps   xmm0, xmm0
0x18006144e  movups  [rbp+180h+var_70], xmm0
0x180061455  movups  [rbp+180h+var_60], xmm0
0x18006145c  movups  xmmword ptr [rbp+180h+var_50], xmm0
0x180061463  mov     dword ptr [rbp+180h+var_70], r13d
0x18006146a  movups  [rbp+180h+var_70+8], xmm0
0x180061471  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180061479  movdqu  [rbp+180h+var_60+8], xmm1
0x180061481  mov     byte ptr [rbp+180h+var_70+8], r13b
0x180061488  movdqu  xmmword ptr [rbp+180h+var_50+8], xmm0
0x180061490  lea     rcx, [rbp+180h+var_F0]
0x180061497  call    ?IndexName@?$Table@VPaths@Tables@Meta@RepoMan@@V?$TablePolicy@UPaths@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::IndexName(void)
0x18006149c  nop
0x18006149d  xorps   xmm0, xmm0
0x1800614a0  movups  [rbp+180h+var_130], xmm0
0x1800614a4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000005
0x1800614ac  movdqu  [rbp+180h+var_120], xmm1
0x1800614b1  mov     eax, dword ptr cs:aPaths; "Paths"
0x1800614b7  mov     dword ptr [rbp+180h+var_130], eax
0x1800614ba  mov     al, byte ptr cs:aPaths+4; "s"
0x1800614c0  mov     byte ptr [rbp+180h+var_130+4], al
0x1800614c3  mov     byte ptr [rbp+180h+var_130+5], r13b
0x1800614c7  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x1800614ce  lea     rcx, [rsp+280h+var_220]
0x1800614d3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800614d8  lea     rdx, [rbp+180h+var_130]
0x1800614dc  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x1800614e1  cmova   rdx, qword ptr [rbp+180h+var_130]
0x1800614e6  mov     r8, qword ptr [rbp+180h+var_120]
0x1800614ea  mov     rcx, rax
0x1800614ed  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800614f2  lea     rdx, aSelectNull; " SELECT NULL"
0x1800614f9  mov     rcx, rax
0x1800614fc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061501  lea     r9, [r15+1C0h]
0x180061508  mov     edx, 802h
0x18006150d  lea     rax, [rsp+280h+var_230]
0x180061512  mov     [rsp+280h+Reserved], rax
0x180061517  lea     r8, [rbp+180h+var_F0]
0x18006151e  call    ?BuildText@?$RowType@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180061523  lea     rdx, aFrom_0; " FROM "
0x18006152a  lea     rcx, [rsp+280h+var_220]
0x18006152f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061534  lea     rdx, [rbp+180h+var_F0]
0x18006153b  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x180061543  cmova   rdx, [rbp+180h+var_F0]
0x18006154b  mov     r8, qword ptr [rbp+180h+var_E0]
0x180061552  mov     rcx, rax
0x180061555  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006155a  lea     edx, [r13+10h]
0x18006155e  lea     rax, [rsp+280h+var_230]
0x180061563  mov     [rsp+280h+Reserved], rax
0x180061568  lea     r9, [rbp+180h+var_130]
0x18006156c  lea     r8, [rbp+180h+var_F0]
0x180061573  call    ?BuildText@?$RowType@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180061578  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18006157f  lea     rcx, [rsp+280h+var_220]
0x180061584  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061589  lea     rdx, [rbp+180h+var_130]
0x18006158d  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x180061592  cmova   rdx, qword ptr [rbp+180h+var_130]
0x180061597  mov     r8, qword ptr [rbp+180h+var_120]
0x18006159b  mov     rcx, rax
0x18006159e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800615a3  lea     rdx, aOn; " ON ("
0x1800615aa  mov     rcx, rax
0x1800615ad  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800615b2  mov     r12d, r13d
0x1800615b5  mov     rax, [r15+1E8h]
0x1800615bc  mov     [rsp+280h+var_250], rax
0x1800615c1  mov     rsi, [r15+1E0h]
0x1800615c8  lea     r13d, [r12+40h]
0x1800615cd  cmp     rsi, rax
0x1800615d0  jz      loc_180061670
0x1800615d6  lea     rbx, [rsi+38h]
0x1800615da  test    r12, r12
0x1800615dd  jz      short loc_1800615F0
0x1800615df  lea     rdx, aAnd_1; " AND "
0x1800615e6  lea     rcx, [rsp+280h+var_220]
0x1800615eb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800615f0  lea     rdx, [rbp+180h+var_130]
0x1800615f4  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x1800615f9  cmova   rdx, qword ptr [rbp+180h+var_130]
0x1800615fe  mov     r8, qword ptr [rbp+180h+var_120]
0x180061602  lea     rcx, [rsp+280h+var_220]
0x180061607  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006160c  lea     rdx, asc_1801D0CE8; "."
0x180061613  mov     rcx, rax
0x180061616  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006161b  mov     rdx, rsi
0x18006161e  cmp     qword ptr [rbx-20h], 0Fh
0x180061623  jbe     short loc_180061628
0x180061625  mov     rdx, [rsi]
0x180061628  mov     r8, [rbx-28h]
0x18006162c  mov     rcx, rax
0x18006162f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180061634  lea     rdx, asc_1801D5B8C; " = "
0x18006163b  mov     rcx, rax
0x18006163e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061643  lea     rdx, [rbx-18h]
0x180061647  cmp     qword ptr [rbx], 0Fh
0x18006164b  jbe     short loc_180061650
0x18006164d  mov     rdx, [rdx]
0x180061650  mov     r8, [rbx-8]
0x180061654  mov     rcx, rax
0x180061657  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006165c  inc     r12
0x18006165f  add     rsi, r13
0x180061662  add     rbx, r13
0x180061665  cmp     rsi, [rsp+280h+var_250]
0x18006166a  jnz     loc_1800615DA
0x180061670  lea     rdx, aWhere; ") WHERE "
0x180061677  lea     rcx, [rsp+280h+var_220]
0x18006167c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061681  lea     rdx, [rbp+180h+var_130]
0x180061685  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x18006168a  cmova   rdx, qword ptr [rbp+180h+var_130]
0x18006168f  mov     r8, qword ptr [rbp+180h+var_120]
0x180061693  mov     rcx, rax
0x180061696  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006169b  lea     r12, asc_1801D0CE8; "."
0x1800616a2  mov     rdx, r12
0x1800616a5  mov     rcx, rax
0x1800616a8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800616ad  mov     rcx, rax
0x1800616b0  xorps   xmm0, xmm0
0x1800616b3  movups  xmmword ptr [rbp+180h+Block], xmm0
0x1800616ba  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x1800616c2  movdqu  [rbp+180h+var_C0], xmm1
0x1800616ca  mov     rax, qword ptr cs:aPathId; "path_id"
0x1800616d1  mov     dword ptr [rbp+180h+Block], eax
0x1800616d7  movzx   eax, word ptr cs:aPathId+4; "_id"
0x1800616de  mov     word ptr [rbp+180h+Block+4], ax
0x1800616e5  mov     al, byte ptr cs:aPathId+6; "d"
0x1800616eb  mov     byte ptr [rbp+180h+Block+6], al
0x1800616f1  xor     esi, esi
0x1800616f3  mov     byte ptr [rbp+180h+Block+7], sil
0x1800616fa  lea     r8d, [rsi+7]
0x1800616fe  lea     rdx, [rbp+180h+Block]
0x180061705  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006170a  lea     rdx, aIsNull; " IS NULL;"
0x180061711  mov     rcx, rax
0x180061714  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061719  nop
0x18006171a  mov     ebx, 1000h
0x18006171f  mov     rax, qword ptr [rbp+180h+var_C0+8]
0x180061726  cmp     rax, 0Fh
0x18006172a  jbe     short loc_18006176B
0x18006172c  mov     rcx, [rbp+180h+Block]; Block
0x180061733  mov     rdx, rcx
0x180061736  inc     rax
0x180061739  cmp     rax, rbx
0x18006173c  jb      short loc_180061765
0x18006173e  mov     rcx, [rcx-8]
0x180061742  sub     rdx, rcx
0x180061745  lea     rax, [rdx-8]
0x180061749  cmp     rax, 1Fh
0x18006174d  jbe     short loc_180061765
0x18006174f  mov     [rsp+280h+Reserved], rsi; Reserved
0x180061754  xor     r9d, r9d; LineNo
0x180061757  xor     r8d, r8d; FileName
0x18006175a  xor     edx, edx; FunctionName
0x18006175c  xor     ecx, ecx; Expression
0x18006175e  call    cs:__imp__invoke_watson
0x180061765  call    cs:__imp_free
0x18006176b  lea     rcx, [rbp+180h+var_90]
0x180061772  call    ?MapName@?$Table@VPaths@Tables@Meta@RepoMan@@V?$TablePolicy@UPaths@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UPath_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@U?$Column@U?$Value@UTags@Text@Meta@RepoMan@@UInt@Types@34@UDefault0@Constraints@34@@Meta@RepoMan@@H@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Paths,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Paths,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Path_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Tags,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::Default0>,int>>::MapName(void)
0x180061777  nop
0x180061778  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18006177f  lea     rcx, [rsp+280h+var_220]
0x180061784  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061789  lea     rdx, [rbp+180h+var_90]
0x180061790  cmp     qword ptr [rbp+180h+var_80+8], 0Fh
0x180061798  cmova   rdx, [rbp+180h+var_90]
0x1800617a0  mov     r8, qword ptr [rbp+180h+var_80]
0x1800617a7  mov     rcx, rax
0x1800617aa  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800617af  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x1800617b6  mov     rcx, rax
0x1800617b9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800617be  lea     rdx, aInsertInto; "INSERT INTO "
0x1800617c5  lea     rcx, [rsp+280h+var_220]
0x1800617ca  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800617cf  lea     rdx, [rbp+180h+var_90]
0x1800617d6  cmp     qword ptr [rbp+180h+var_80+8], 0Fh
0x1800617de  cmova   rdx, [rbp+180h+var_90]
0x1800617e6  mov     r8, qword ptr [rbp+180h+var_80]
0x1800617ed  mov     rcx, rax
0x1800617f0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800617f5  lea     rdx, aSelect; " SELECT "
0x1800617fc  mov     rcx, rax
0x1800617ff  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061804  lea     rdx, [rbp+180h+var_F0]
0x18006180b  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x180061813  cmova   rdx, [rbp+180h+var_F0]
0x18006181b  mov     r8, qword ptr [rbp+180h+var_E0]
0x180061822  mov     rcx, rax
0x180061825  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006182a  mov     rdx, r12
0x18006182d  mov     rcx, rax
0x180061830  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061835  mov     rcx, rax
0x180061838  xorps   xmm0, xmm0
0x18006183b  movups  xmmword ptr [rbp+180h+var_110], xmm0
0x18006183f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x180061847  movdqu  [rbp+180h+var_100], xmm1
0x18006184f  mov     rax, qword ptr cs:aPathId; "path_id"
0x180061856  mov     dword ptr [rbp+180h+var_110], eax
0x180061859  movzx   eax, word ptr cs:aPathId+4; "_id"
0x180061860  mov     word ptr [rbp+180h+var_110+4], ax
0x180061864  mov     al, byte ptr cs:aPathId+6; "d"
0x18006186a  mov     byte ptr [rbp+180h+var_110+6], al
0x18006186d  mov     byte ptr [rbp+180h+var_110+7], sil
0x180061871  mov     r8d, 7
0x180061877  lea     rdx, [rbp+180h+var_110]
0x18006187b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180061880  lea     rdx, aAsIncoming; " AS incoming, "
0x180061887  mov     rcx, rax
0x18006188a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006188f  lea     rdx, [rbp+180h+var_130]
0x180061893  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x180061898  cmova   rdx, qword ptr [rbp+180h+var_130]
0x18006189d  mov     r8, qword ptr [rbp+180h+var_120]
0x1800618a1  mov     rcx, rax
0x1800618a4  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800618a9  mov     rdx, r12
0x1800618ac  mov     rcx, rax
0x1800618af  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800618b4  mov     rcx, rax
0x1800618b7  xorps   xmm0, xmm0
0x1800618ba  movups  xmmword ptr [rbp+180h+Block], xmm0
0x1800618c1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x1800618c9  movdqu  [rbp+180h+var_C0], xmm1
0x1800618d1  mov     rax, qword ptr cs:aPathId; "path_id"
0x1800618d8  mov     dword ptr [rbp+180h+Block], eax
0x1800618de  movzx   eax, word ptr cs:aPathId+4; "_id"
0x1800618e5  mov     word ptr [rbp+180h+Block+4], ax
0x1800618ec  mov     al, byte ptr cs:aPathId+6; "d"
0x1800618f2  mov     byte ptr [rbp+180h+Block+6], al
0x1800618f8  mov     byte ptr [rbp+180h+Block+7], sil
0x1800618ff  mov     r8d, 7
0x180061905  lea     rdx, [rbp+180h+Block]
0x18006190c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180061911  lea     rdx, aAsClientFrom; " AS client FROM "
0x180061918  mov     rcx, rax
0x18006191b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061920  lea     rdx, [rbp+180h+var_F0]
0x180061927  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x18006192f  cmova   rdx, [rbp+180h+var_F0]
0x180061937  mov     r8, qword ptr [rbp+180h+var_E0]
0x18006193e  mov     rcx, rax
0x180061941  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180061946  lea     rdx, aInnerJoin; " INNER JOIN "
0x18006194d  mov     rcx, rax
0x180061950  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180061955  lea     rdx, [rbp+180h+var_130]
0x180061959  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x18006195e  cmova   rdx, qword ptr [rbp+180h+var_130]
0x180061963  mov     r8, qword ptr [rbp+180h+var_120]
0x180061967  mov     rcx, rax
0x18006196a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18006196f  lea     rdx, aOn; " ON ("
0x180061976  mov     rcx, rax
0x180061979  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18006197e  nop
0x18006197f  lea     rcx, [rbp+180h+Block]
0x180061986  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006198b  mov     r12d, 4DE1h
0x180061991  mov     [rbp+180h+Block], r12
0x180061998  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800619a0  movdqu  [rbp+180h+var_C0], xmm6
0x1800619a8  mov     rax, qword ptr [rbp+180h+var_100+8]
0x1800619af  cmp     rax, 0Fh
0x1800619b3  jbe     short loc_1800619F1
  ... truncated ...
```
