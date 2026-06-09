# RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x1800580c4`
- end: `0x180058da1`
- name: `?CreateText@?$Table@VApps@Tables@Meta@RepoMan@@V?$TablePolicy@UApps@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3293`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005613c`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x1800564c8`
- `0x1800580c4`
- `0x18005a9c8`
- `0x18005aa58`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180058411`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180058680`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180058411`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180058680`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005840a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180058679`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005840a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180058679`

## string_xrefs

- `0x18005845b`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x180058424`: `CREATE TABLE IF NOT EXISTS `
- `0x180058d00`: `CREATE TABLE IF NOT EXISTS `
- `0x180058522`: ` AS incoming, `
- `0x180058922`: `REPLACE INTO `
- `0x180058b69`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
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
  __m128i v103; // [rsp+168h] [rbp+60h]
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
  __int128 v114; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int128 v116; // [rsp+238h] [rbp+130h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v98);
  if ( a4 == 2048 )
  {
    v114 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v114) = 0;
    v116 = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v106);
    v102 = 0;
    v103 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)&v102, "Apps");
    v7 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v102;
    if ( v103.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v102;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v103.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v106,
      (unsigned int)&v102,
      (__int64)v98);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)" LEFT OUTER JOIN ");
    v15 = &v102;
    if ( v103.m128i_i64[1] > 0xFuLL )
      v15 = (__int128 *)v102;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v103.m128i_u64[0]);
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
        if ( v103.m128i_i64[1] > 0xFuLL )
          v20 = (__int128 *)v102;
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v20,
                v103.m128i_u64[0]);
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
    if ( v103.m128i_i64[1] > 0xFuLL )
      v28 = (__int128 *)v102;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v103.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    *(_OWORD *)Block = 0;
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)Block, "app_id");
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 6u);
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v112);
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
    *(_OWORD *)v104 = 0;
    v105 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v104, "app_id");
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v104, 6u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = &v102;
    if ( v103.m128i_i64[1] > 0xFuLL )
      v45 = (__int128 *)v102;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v103.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    *(_OWORD *)Block = 0;
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)Block, "app_id");
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 6u);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v106;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v106[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v107.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = &v102;
    if ( v103.m128i_i64[1] > 0xFuLL )
      v53 = (__int128 *)v102;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, v103.m128i_u64[0]);
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
        if ( v103.m128i_i64[1] > 0xFuLL )
          v61 = (__int128 *)v102;
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v99,
                (__int64)v61,
                v103.m128i_u64[0]);
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    v103 = v55;
    std::string::_Tidy_deallocate(v106);
    v106[0] = 19937;
    v107 = v55;
    std::string::_Tidy_deallocate(&v114);
    *(_QWORD *)&v114 = 19937;
    si128 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
    v101[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v72 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"DROP TABLE IF EXISTS ");
    v73 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v104);
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
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"Apps");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" SET ");
        *(_OWORD *)v104 = 0;
        v105 = 0;
        std::string::_Construct<1,char const *>(v104, "Apps", 4u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
        v92 = std::operator<<<std::char_traits<char>>(v91, (__int64)"Apps");
        std::operator<<<std::char_traits<char>>(v92, (__int64)";");
        std::stringbuf::str(v100, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
        v101[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v101);
        return a2;
      case 0x20u:
        v93 = std::operator<<<std::char_traits<char>>((__int64)v99, (__int64)"SELECT * FROM ");
        v94 = std::operator<<<std::char_traits<char>>(v93, (__int64)"Apps");
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
    std::string::_Construct<1,char const *>(v104, "Apps", 4u);
    v95(a1, v104);
    if ( v105.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v104, v104[0]);
  }
  else if ( a4 == 1024 )
  {
    v76 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    v77 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v104 = 0;
  v105 = 0;
  std::string::_Construct<1,char const *>(v104, "Apps", 4u);
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
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
0x1800580c4  mov     rax, rsp
0x1800580c7  mov     [rax+18h], rbx
0x1800580cb  mov     [rax+20h], rsi
0x1800580cf  push    rbp
0x1800580d0  push    r12
0x1800580d2  push    r13
0x1800580d4  push    r14
0x1800580d6  push    r15
0x1800580d8  lea     rbp, [rax-188h]
0x1800580df  sub     rsp, 260h
0x1800580e6  movaps  xmmword ptr [rax-38h], xmm6
0x1800580ea  mov     rax, cs:__security_cookie
0x1800580f1  xor     rax, rsp
0x1800580f4  mov     [rbp+180h+var_40], rax
0x1800580fb  movzx   esi, r9w
0x1800580ff  mov     r14, rdx
0x180058102  mov     r15, rcx
0x180058105  mov     qword ptr [rsp+280h+var_248], rdx
0x18005810a  xor     r13d, r13d
0x18005810d  mov     [rsp+280h+var_240], r13d
0x180058112  lea     rcx, [rsp+280h+var_230]
0x180058117  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18005811c  nop
0x18005811d  mov     eax, 800h
0x180058122  cmp     ax, si
0x180058125  jnz     loc_180058866
0x18005812b  xorps   xmm0, xmm0
0x18005812e  movups  [rbp+180h+var_70], xmm0
0x180058135  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18005813d  movdqu  [rbp+180h+var_60], xmm1
0x180058145  mov     byte ptr [rbp+180h+var_70], r13b
0x18005814c  movdqu  [rbp+180h+var_50], xmm0
0x180058154  lea     rcx, [rbp+180h+var_F0]
0x18005815b  call    ?IndexName@?$Table@VApps@Tables@Meta@RepoMan@@V?$TablePolicy@UApps@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x180058160  nop
0x180058161  xorps   xmm0, xmm0
0x180058164  movups  [rbp+180h+var_130], xmm0
0x180058168  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000004
0x180058170  movdqu  [rbp+180h+var_120], xmm1
0x180058175  mov     dword ptr [rbp+180h+var_130], 73707041h
0x18005817c  mov     byte ptr [rbp+180h+var_130+4], r13b
0x180058180  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x180058187  lea     rcx, [rsp+280h+var_220]
0x18005818c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058191  lea     rdx, [rbp+180h+var_130]
0x180058195  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x18005819a  cmova   rdx, qword ptr [rbp+180h+var_130]
0x18005819f  mov     r8, qword ptr [rbp+180h+var_120]
0x1800581a3  mov     rcx, rax
0x1800581a6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800581ab  lea     rdx, aSelectNull; " SELECT NULL"
0x1800581b2  mov     rcx, rax
0x1800581b5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800581ba  lea     r9, [r15+1C0h]
0x1800581c1  mov     edx, 802h
0x1800581c6  lea     rax, [rsp+280h+var_230]
0x1800581cb  mov     [rsp+280h+Reserved], rax
0x1800581d0  lea     r8, [rbp+180h+var_F0]
0x1800581d7  call    ?BuildText@?$RowType@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x1800581dc  lea     rdx, aFrom_0; " FROM "
0x1800581e3  lea     rcx, [rsp+280h+var_220]
0x1800581e8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800581ed  lea     rdx, [rbp+180h+var_F0]
0x1800581f4  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x1800581fc  cmova   rdx, [rbp+180h+var_F0]
0x180058204  mov     r8, qword ptr [rbp+180h+var_E0]
0x18005820b  mov     rcx, rax
0x18005820e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180058213  lea     edx, [r13+10h]
0x180058217  lea     rax, [rsp+280h+var_230]
0x18005821c  mov     [rsp+280h+Reserved], rax
0x180058221  lea     r9, [rbp+180h+var_130]
0x180058225  lea     r8, [rbp+180h+var_F0]
0x18005822c  call    ?BuildText@?$RowType@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180058231  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x180058238  lea     rcx, [rsp+280h+var_220]
0x18005823d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058242  lea     rdx, [rbp+180h+var_130]
0x180058246  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x18005824b  cmova   rdx, qword ptr [rbp+180h+var_130]
0x180058250  mov     r8, qword ptr [rbp+180h+var_120]
0x180058254  mov     rcx, rax
0x180058257  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005825c  lea     rdx, aOn; " ON ("
0x180058263  mov     rcx, rax
0x180058266  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005826b  mov     r12d, r13d
0x18005826e  mov     rax, [r15+1E8h]
0x180058275  mov     [rsp+280h+var_250], rax
0x18005827a  mov     rsi, [r15+1E0h]
0x180058281  lea     r13d, [r12+40h]
0x180058286  cmp     rsi, rax
0x180058289  jz      loc_180058329
0x18005828f  lea     rbx, [rsi+38h]
0x180058293  test    r12, r12
0x180058296  jz      short loc_1800582A9
0x180058298  lea     rdx, aAnd_1; " AND "
0x18005829f  lea     rcx, [rsp+280h+var_220]
0x1800582a4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800582a9  lea     rdx, [rbp+180h+var_130]
0x1800582ad  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x1800582b2  cmova   rdx, qword ptr [rbp+180h+var_130]
0x1800582b7  mov     r8, qword ptr [rbp+180h+var_120]
0x1800582bb  lea     rcx, [rsp+280h+var_220]
0x1800582c0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800582c5  lea     rdx, asc_1801D0CE8; "."
0x1800582cc  mov     rcx, rax
0x1800582cf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800582d4  mov     rdx, rsi
0x1800582d7  cmp     qword ptr [rbx-20h], 0Fh
0x1800582dc  jbe     short loc_1800582E1
0x1800582de  mov     rdx, [rsi]
0x1800582e1  mov     r8, [rbx-28h]
0x1800582e5  mov     rcx, rax
0x1800582e8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800582ed  lea     rdx, asc_1801D5B8C; " = "
0x1800582f4  mov     rcx, rax
0x1800582f7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800582fc  lea     rdx, [rbx-18h]
0x180058300  cmp     qword ptr [rbx], 0Fh
0x180058304  jbe     short loc_180058309
0x180058306  mov     rdx, [rdx]
0x180058309  mov     r8, [rbx-8]
0x18005830d  mov     rcx, rax
0x180058310  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180058315  inc     r12
0x180058318  add     rsi, r13
0x18005831b  add     rbx, r13
0x18005831e  cmp     rsi, [rsp+280h+var_250]
0x180058323  jnz     loc_180058293
0x180058329  lea     rdx, aWhere; ") WHERE "
0x180058330  lea     rcx, [rsp+280h+var_220]
0x180058335  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005833a  lea     rdx, [rbp+180h+var_130]
0x18005833e  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x180058343  cmova   rdx, qword ptr [rbp+180h+var_130]
0x180058348  mov     r8, qword ptr [rbp+180h+var_120]
0x18005834c  mov     rcx, rax
0x18005834f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180058354  lea     r12, asc_1801D0CE8; "."
0x18005835b  mov     rdx, r12
0x18005835e  mov     rcx, rax
0x180058361  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058366  mov     rcx, rax
0x180058369  xorps   xmm0, xmm0
0x18005836c  movups  xmmword ptr [rbp+180h+Block], xmm0
0x180058373  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000006
0x18005837b  movdqu  [rbp+180h+var_C0], xmm1
0x180058383  mov     eax, dword ptr cs:aAppId; "app_id"
0x180058389  mov     dword ptr [rbp+180h+Block], eax
0x18005838f  movzx   eax, word ptr cs:aAppId+4; "id"
0x180058396  mov     word ptr [rbp+180h+Block+4], ax
0x18005839d  xor     esi, esi
0x18005839f  mov     byte ptr [rbp+180h+Block+6], sil
0x1800583a6  lea     r8d, [rsi+6]
0x1800583aa  lea     rdx, [rbp+180h+Block]
0x1800583b1  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800583b6  lea     rdx, aIsNull; " IS NULL;"
0x1800583bd  mov     rcx, rax
0x1800583c0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800583c5  nop
0x1800583c6  mov     ebx, 1000h
0x1800583cb  mov     rax, qword ptr [rbp+180h+var_C0+8]
0x1800583d2  cmp     rax, 0Fh
0x1800583d6  jbe     short loc_180058417
0x1800583d8  mov     rcx, [rbp+180h+Block]; Block
0x1800583df  mov     rdx, rcx
0x1800583e2  inc     rax
0x1800583e5  cmp     rax, rbx
0x1800583e8  jb      short loc_180058411
0x1800583ea  mov     rcx, [rcx-8]
0x1800583ee  sub     rdx, rcx
0x1800583f1  lea     rax, [rdx-8]
0x1800583f5  cmp     rax, 1Fh
0x1800583f9  jbe     short loc_180058411
0x1800583fb  mov     [rsp+280h+Reserved], rsi; Reserved
0x180058400  xor     r9d, r9d; LineNo
0x180058403  xor     r8d, r8d; FileName
0x180058406  xor     edx, edx; FunctionName
0x180058408  xor     ecx, ecx; Expression
0x18005840a  call    cs:__imp__invoke_watson
0x180058411  call    cs:__imp_free
0x180058417  lea     rcx, [rbp+180h+var_90]
0x18005841e  call    ?MapName@?$Table@VApps@Tables@Meta@RepoMan@@V?$TablePolicy@UApps@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UApp_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UApps@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Apps,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Apps,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::App_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Apps,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Build_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Builds,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x180058423  nop
0x180058424  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18005842b  lea     rcx, [rsp+280h+var_220]
0x180058430  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058435  lea     rdx, [rbp+180h+var_90]
0x18005843c  cmp     qword ptr [rbp+180h+var_80+8], 0Fh
0x180058444  cmova   rdx, [rbp+180h+var_90]
0x18005844c  mov     r8, qword ptr [rbp+180h+var_80]
0x180058453  mov     rcx, rax
0x180058456  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005845b  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x180058462  mov     rcx, rax
0x180058465  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005846a  lea     rdx, aInsertInto; "INSERT INTO "
0x180058471  lea     rcx, [rsp+280h+var_220]
0x180058476  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005847b  lea     rdx, [rbp+180h+var_90]
0x180058482  cmp     qword ptr [rbp+180h+var_80+8], 0Fh
0x18005848a  cmova   rdx, [rbp+180h+var_90]
0x180058492  mov     r8, qword ptr [rbp+180h+var_80]
0x180058499  mov     rcx, rax
0x18005849c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800584a1  lea     rdx, aSelect; " SELECT "
0x1800584a8  mov     rcx, rax
0x1800584ab  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800584b0  lea     rdx, [rbp+180h+var_F0]
0x1800584b7  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x1800584bf  cmova   rdx, [rbp+180h+var_F0]
0x1800584c7  mov     r8, qword ptr [rbp+180h+var_E0]
0x1800584ce  mov     rcx, rax
0x1800584d1  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800584d6  mov     rdx, r12
0x1800584d9  mov     rcx, rax
0x1800584dc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800584e1  mov     rcx, rax
0x1800584e4  xorps   xmm0, xmm0
0x1800584e7  movups  xmmword ptr [rbp+180h+var_110], xmm0
0x1800584eb  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000006
0x1800584f3  movdqu  [rbp+180h+var_100], xmm1
0x1800584fb  mov     eax, dword ptr cs:aAppId; "app_id"
0x180058501  mov     dword ptr [rbp+180h+var_110], eax
0x180058504  movzx   eax, word ptr cs:aAppId+4; "id"
0x18005850b  mov     word ptr [rbp+180h+var_110+4], ax
0x18005850f  mov     byte ptr [rbp+180h+var_110+6], sil
0x180058513  mov     r8d, 6
0x180058519  lea     rdx, [rbp+180h+var_110]
0x18005851d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180058522  lea     rdx, aAsIncoming; " AS incoming, "
0x180058529  mov     rcx, rax
0x18005852c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058531  lea     rdx, [rbp+180h+var_130]
0x180058535  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x18005853a  cmova   rdx, qword ptr [rbp+180h+var_130]
0x18005853f  mov     r8, qword ptr [rbp+180h+var_120]
0x180058543  mov     rcx, rax
0x180058546  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005854b  mov     rdx, r12
0x18005854e  mov     rcx, rax
0x180058551  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058556  mov     rcx, rax
0x180058559  xorps   xmm0, xmm0
0x18005855c  movups  xmmword ptr [rbp+180h+Block], xmm0
0x180058563  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000006
0x18005856b  movdqu  [rbp+180h+var_C0], xmm1
0x180058573  mov     eax, dword ptr cs:aAppId; "app_id"
0x180058579  mov     dword ptr [rbp+180h+Block], eax
0x18005857f  movzx   eax, word ptr cs:aAppId+4; "id"
0x180058586  mov     word ptr [rbp+180h+Block+4], ax
0x18005858d  mov     byte ptr [rbp+180h+Block+6], sil
0x180058594  mov     r8d, 6
0x18005859a  lea     rdx, [rbp+180h+Block]
0x1800585a1  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800585a6  lea     rdx, aAsClientFrom; " AS client FROM "
0x1800585ad  mov     rcx, rax
0x1800585b0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800585b5  lea     rdx, [rbp+180h+var_F0]
0x1800585bc  cmp     qword ptr [rbp+180h+var_E0+8], 0Fh
0x1800585c4  cmova   rdx, [rbp+180h+var_F0]
0x1800585cc  mov     r8, qword ptr [rbp+180h+var_E0]
0x1800585d3  mov     rcx, rax
0x1800585d6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800585db  lea     rdx, aInnerJoin; " INNER JOIN "
0x1800585e2  mov     rcx, rax
0x1800585e5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800585ea  lea     rdx, [rbp+180h+var_130]
0x1800585ee  cmp     qword ptr [rbp+180h+var_120+8], 0Fh
0x1800585f3  cmova   rdx, qword ptr [rbp+180h+var_130]
0x1800585f8  mov     r8, qword ptr [rbp+180h+var_120]
0x1800585fc  mov     rcx, rax
0x1800585ff  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180058604  lea     rdx, aOn; " ON ("
0x18005860b  mov     rcx, rax
0x18005860e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180058613  nop
0x180058614  lea     rcx, [rbp+180h+Block]
0x18005861b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180058620  mov     r12d, 4DE1h
0x180058626  mov     [rbp+180h+Block], r12
0x18005862d  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x180058635  movdqu  [rbp+180h+var_C0], xmm6
0x18005863d  mov     rax, qword ptr [rbp+180h+var_100+8]
0x180058644  cmp     rax, 0Fh
0x180058648  jbe     short loc_180058686
0x18005864a  mov     rcx, [rbp+180h+var_110]; Block
0x18005864e  mov     rdx, rcx
0x180058651  inc     rax
0x180058654  cmp     rax, rbx
0x180058657  jb      short loc_180058680
0x180058659  mov     rcx, [rcx-8]
0x18005865d  sub     rdx, rcx
0x180058660  lea     rax, [rdx-8]
0x180058664  cmp     rax, 1Fh
0x180058668  jbe     short loc_180058680
0x18005866a  mov     [rsp+280h+Reserved], rsi; Reserved
0x18005866f  xor     r9d, r9d; LineNo
0x180058672  xor     r8d, r8d; FileName
  ... truncated ...
```
