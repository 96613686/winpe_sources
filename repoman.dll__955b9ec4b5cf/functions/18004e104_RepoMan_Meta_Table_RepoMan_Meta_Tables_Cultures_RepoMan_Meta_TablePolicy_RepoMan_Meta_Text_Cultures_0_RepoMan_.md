# RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18004e104`
- end: `0x18004ee3e`
- name: `?CreateText@?$Table@VCultures@Tables@Meta@RepoMan@@V?$TablePolicy@UCultures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3386`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004bc80`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18004c00c`
- `0x18004e104`
- `0x180050d6c`
- `0x180050dd0`
- `0x180050ec8`
- `0x180055314`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e46a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e46a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6ec`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004e463`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004e6e5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004e463`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004e6e5`

## string_xrefs

- `0x18004e4b4`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18004e47d`: `CREATE TABLE IF NOT EXISTS `
- `0x18004ed9e`: `CREATE TABLE IF NOT EXISTS `
- `0x18004e583`: ` AS incoming, `
- `0x18004e9ba`: `REPLACE INTO `
- `0x18004ec02`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
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
  __int64 v17; // rax
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
  int v69; // ecx
  __int64 v70; // rax
  _QWORD *v71; // rdx
  __int64 v72; // rax
  __int64 v73; // rbx
  _QWORD *v74; // rax
  unsigned __int64 v75; // r8
  __int64 v76; // rax
  char v77; // bl
  void **v78; // rax
  __m128i v79; // xmm6
  __int128 *v80; // rdx
  __int64 v81; // rax
  int v82; // ebx
  int v83; // ecx
  _QWORD *v84; // r15
  __int64 v85; // rax
  unsigned __int64 v86; // r8
  int v87; // ecx
  __int64 v89; // rax
  __int64 v90; // rax
  int v91; // ecx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  void (__fastcall *v96)(_QWORD *, void **); // rbx
  int Reserved; // [rsp+28h] [rbp-E0h]
  __int64 v98; // [rsp+38h] [rbp-D0h]
  __int64 v99; // [rsp+38h] [rbp-D0h]
  __int64 *v100; // [rsp+40h] [rbp-C8h]
  _BYTE v101[16]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v102[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v103[128]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v104[13]; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v105; // [rsp+158h] [rbp+50h] BYREF
  __m128i v106; // [rsp+168h] [rbp+60h]
  void *v107[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v108; // [rsp+188h] [rbp+80h]
  _QWORD v109[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v110; // [rsp+1A8h] [rbp+A0h]
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v112; // [rsp+1C8h] [rbp+C0h]
  __int128 v113; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v114; // [rsp+1E8h] [rbp+E0h]
  _QWORD v115[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v116; // [rsp+208h] [rbp+100h]
  __int128 v117; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int64 v119; // [rsp+238h] [rbp+130h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  if ( a4 == 2048 )
  {
    v117 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v117) = 0;
    v119 = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v109);
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    v105 = 0x73657275746C7543uLL;
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v106.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v10,
      2050,
      (unsigned int)v109,
      (_DWORD)a1 + 448,
      (__int64)v101);
    v11 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" FROM ");
    v12 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v12 = (_QWORD *)v109[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, (__int64)v12, v110.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v109,
      (unsigned int)&v105,
      (__int64)v101);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" LEFT OUTER JOIN ");
    v15 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v15 = (__int128 *)v105;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v106.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v16, (__int64)" ON (");
    v17 = 0;
    v98 = 0;
    v100 = (__int64 *)a1[61];
    v18 = (__int64 *)a1[60];
    if ( v18 != v100 )
    {
      v19 = v18 + 7;
      do
      {
        if ( v17 )
          std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" AND ");
        v20 = &v105;
        if ( v106.m128i_i64[1] > 0xFuLL )
          v20 = (__int128 *)v105;
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v20,
                v106.m128i_u64[0]);
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
        v17 = ++v98;
        v18 += 8;
        v19 += 8;
      }
      while ( v18 != v100 );
    }
    v27 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)") WHERE ");
    v28 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v28 = (__int128 *)v105;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v106.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v112 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"culture_id";
    Block[1] = (void *)*(unsigned __int16 *)"id";
    BYTE2(Block[1]) = 0;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 0xAu);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    if ( v112.m128i_i64[1] > 0xFuLL )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(v112.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v115);
    v33 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v34 = v115;
    if ( v116.m128i_i64[1] > 0xFuLL )
      v34 = (_QWORD *)v115[0];
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, (__int64)v34, v116.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v35,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v36 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"INSERT INTO ");
    v37 = v115;
    if ( v116.m128i_i64[1] > 0xFuLL )
      v37 = (_QWORD *)v115[0];
    v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, (__int64)v37, v116.m128i_u64[0]);
    v39 = std::operator<<<std::char_traits<char>>(v38, (__int64)" SELECT ");
    v40 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v40 = (_QWORD *)v109[0];
    v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, (__int64)v40, v110.m128i_u64[0]);
    v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)".");
    v108 = _mm_load_si128((const __m128i *)&_xmm);
    v107[0] = *(void **)"culture_id";
    v107[1] = (void *)*(unsigned __int16 *)"id";
    BYTE2(v107[1]) = 0;
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v107, 0xAu);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v45 = (__int128 *)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v106.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v112 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"culture_id";
    Block[1] = (void *)*(unsigned __int16 *)"id";
    BYTE2(Block[1]) = 0;
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 0xAu);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v109[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v110.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v53 = (__int128 *)v105;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, v106.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v54, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v112 = v55;
    if ( v108.m128i_i64[1] > 0xFuLL )
    {
      v56 = v107[0];
      if ( (unsigned __int64)(v108.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v107[0] - 1);
        if ( (unsigned __int64)((char *)v107[0] - (char *)v56 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v56);
    }
    v57 = 0;
    v99 = 0;
    v58 = (__int64 *)a1[60];
    if ( v58 != (__int64 *)a1[61] )
    {
      v59 = v58 + 7;
      v60 = (__int64 *)a1[61];
      do
      {
        if ( v57 )
          std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" AND ");
        v61 = &v105;
        if ( v106.m128i_i64[1] > 0xFuLL )
          v61 = (__int128 *)v105;
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v61,
                v106.m128i_u64[0]);
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
        v57 = ++v99;
        v58 += 8;
        v59 += 8;
      }
      while ( v58 != v60 );
    }
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)") ");
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>::BuildText(
      v68,
      0,
      144,
      (unsigned int)v109,
      (__int64)&v105,
      (__int64)v101);
    RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>::BuildText(
      v69,
      1,
      784,
      (unsigned int)v109,
      Reserved,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
    v70 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v71 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v71 = (_QWORD *)v109[0];
    v72 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v70, (__int64)v71, v110.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v72, (__int64)";");
    std::stringbuf::str(v103, a2);
    std::string::_Tidy_deallocate(v115);
    v115[0] = 19937;
    v116 = v55;
    std::string::_Tidy_deallocate(&v105);
    *(_QWORD *)&v105 = 19937;
    v106 = v55;
    std::string::_Tidy_deallocate(v109);
    v109[0] = 19937;
    v110 = v55;
    std::string::_Tidy_deallocate(&v117);
    *(_QWORD *)&v117 = 19937;
    si128 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
    v104[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v73 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v107);
    v75 = v74[2];
    if ( v74[3] > 0xFu )
      v74 = (_QWORD *)*v74;
    v76 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v73, (__int64)v74, v75);
    std::operator<<<std::char_traits<char>>(v76, (__int64)";");
    std::string::_Tidy_deallocate(v107);
    std::stringbuf::str(v103, a2);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
    v104[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
    return a2;
  }
  v77 = 2;
  if ( a4 == 1 || a4 == 1024 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"CREATE TABLE IF NOT EXISTS ");
  }
  else
  {
    switch ( a4 )
    {
      case 2u:
        std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"REPLACE INTO ");
        goto LABEL_65;
      case 4u:
        v89 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"UPDATE ");
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Cultures");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v107 = 0;
        v108 = 0;
        std::string::_Construct<1,char const *>(v107, "Cultures", 8u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
          v91,
          4,
          (unsigned int)v107,
          (_DWORD)a1 + 448,
          (__int64)v101);
        std::string::_Tidy_deallocate(v107);
        std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x40u:
        v92 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Cultures");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Cultures");
        std::operator<<<std::char_traits<char>>(v95, (__int64)" WHERE ( rowid = ?1 );");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
    }
  }
  if ( a4 == 1 )
  {
    v96 = *(void (__fastcall **)(_QWORD *, void **))(*a1 + 8LL);
    *(_OWORD *)v107 = 0;
    v108 = 0;
    std::string::_Construct<1,char const *>(v107, "Cultures", 8u);
    v96(a1, v107);
    if ( v108.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v107, v107[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(v107, "Cultures", 8u);
  v78 = v107;
  v77 = 4;
LABEL_66:
  v113 = 0;
  v114 = 0;
  v113 = *(_OWORD *)v78;
  v114 = *((__m128i *)v78 + 1);
  *(_BYTE *)v78 = 0;
  v78[2] = 0;
  v78[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v107);
  }
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v112 = v79;
  }
  v80 = &v113;
  if ( v114.m128i_i64[1] > 0xFuLL )
    v80 = (__int128 *)v113;
  v81 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
          (__int64)v102,
          (__int64)v80,
          v114.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v81, (__int64)"(");
  v82 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
    v83,
    a4,
    (unsigned int)&v113,
    (_DWORD)a1 + 448,
    (__int64)v101);
  if ( a4 == 1 && a1[54] )
  {
    v84 = a1 + 52;
    v85 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" , ");
    v86 = v84[2];
    if ( v84[3] > 0xFu )
      v84 = (_QWORD *)*v84;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v85, (__int64)v84, v86);
  }
  std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)")");
  if ( a4 == 2 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" VALUES (");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v87,
      8,
      (unsigned int)&v113,
      v82,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
  std::stringbuf::str(v103, a2);
  std::string::_Tidy_deallocate(&v113);
  *(_QWORD *)&v113 = 19937;
  v114 = v79;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
  v104[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
  return a2;
}

```

## disassembly

```asm
0x18004e104  mov     rax, rsp
0x18004e107  mov     [rax+18h], rbx
0x18004e10b  mov     [rax+20h], rsi
0x18004e10f  push    rbp
0x18004e110  push    r12
0x18004e112  push    r13
0x18004e114  push    r14
0x18004e116  push    r15
0x18004e118  lea     rbp, [rax-178h]
0x18004e11f  sub     rsp, 250h
0x18004e126  movaps  xmmword ptr [rax-38h], xmm6
0x18004e12a  mov     rax, cs:__security_cookie
0x18004e131  xor     rax, rsp
0x18004e134  mov     [rbp+170h+var_38], rax
0x18004e13b  movzx   esi, r9w
0x18004e13f  mov     r14, rdx
0x18004e142  mov     r15, rcx
0x18004e145  mov     [rsp+270h+var_238], rdx
0x18004e14a  xor     r13d, r13d
0x18004e14d  mov     [rsp+270h+var_230], r13d
0x18004e152  lea     rcx, [rsp+270h+var_220]
0x18004e157  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18004e15c  nop
0x18004e15d  mov     eax, 800h
0x18004e162  cmp     ax, si
0x18004e165  jnz     loc_18004E8FD
0x18004e16b  xorps   xmm0, xmm0
0x18004e16e  movups  [rbp+170h+var_60], xmm0
0x18004e175  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18004e17d  movdqu  [rbp+170h+var_50], xmm1
0x18004e185  mov     byte ptr [rbp+170h+var_60], r13b
0x18004e18c  mov     [rbp+170h+var_40], r13
0x18004e193  lea     rcx, [rbp+170h+var_E0]
0x18004e19a  call    ?IndexName@?$Table@VCultures@Tables@Meta@RepoMan@@V?$TablePolicy@UCultures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x18004e19f  nop
0x18004e1a0  xorps   xmm0, xmm0
0x18004e1a3  movups  [rbp+170h+var_120], xmm0
0x18004e1a7  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000008
0x18004e1af  movdqu  [rbp+170h+var_110], xmm1
0x18004e1b4  mov     rax, 73657275746C7543h
0x18004e1be  mov     qword ptr [rbp+170h+var_120], rax
0x18004e1c2  mov     byte ptr [rbp+170h+var_120+8], r13b
0x18004e1c6  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18004e1cd  lea     rcx, [rsp+270h+var_210]
0x18004e1d2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e1d7  lea     rdx, [rbp+170h+var_120]
0x18004e1db  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e1e0  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e1e5  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e1e9  mov     rcx, rax
0x18004e1ec  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e1f1  lea     rdx, aSelectNull; " SELECT NULL"
0x18004e1f8  mov     rcx, rax
0x18004e1fb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e200  lea     r9, [r15+1C0h]
0x18004e207  mov     edx, 802h
0x18004e20c  lea     rax, [rsp+270h+var_220]
0x18004e211  mov     [rsp+270h+Reserved], rax
0x18004e216  lea     r8, [rbp+170h+var_E0]
0x18004e21d  call    ?BuildText@?$RowType@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004e222  lea     rdx, aFrom_0; " FROM "
0x18004e229  lea     rcx, [rsp+270h+var_210]
0x18004e22e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e233  lea     rdx, [rbp+170h+var_E0]
0x18004e23a  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004e242  cmova   rdx, [rbp+170h+var_E0]
0x18004e24a  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004e251  mov     rcx, rax
0x18004e254  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e259  lea     edx, [r13+10h]
0x18004e25d  lea     rax, [rsp+270h+var_220]
0x18004e262  mov     [rsp+270h+Reserved], rax
0x18004e267  lea     r9, [rbp+170h+var_120]
0x18004e26b  lea     r8, [rbp+170h+var_E0]
0x18004e272  call    ?BuildText@?$RowType@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004e277  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18004e27e  lea     rcx, [rsp+270h+var_210]
0x18004e283  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e288  lea     rdx, [rbp+170h+var_120]
0x18004e28c  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e291  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e296  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e29a  mov     rcx, rax
0x18004e29d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e2a2  lea     rdx, aOn; " ON ("
0x18004e2a9  mov     rcx, rax
0x18004e2ac  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e2b1  mov     eax, r13d
0x18004e2b4  mov     [rsp+270h+var_240], rax
0x18004e2b9  mov     rcx, [r15+1E8h]
0x18004e2c0  mov     [rsp+270h+var_238], rcx
0x18004e2c5  mov     rsi, [r15+1E0h]
0x18004e2cc  lea     r12d, [r13+1]
0x18004e2d0  lea     r13d, [rax+40h]
0x18004e2d4  cmp     rsi, rcx
0x18004e2d7  jz      loc_18004E381
0x18004e2dd  lea     rbx, [rsi+38h]
0x18004e2e1  test    rax, rax
0x18004e2e4  jz      short loc_18004E2F7
0x18004e2e6  lea     rdx, aAnd_1; " AND "
0x18004e2ed  lea     rcx, [rsp+270h+var_210]
0x18004e2f2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e2f7  lea     rdx, [rbp+170h+var_120]
0x18004e2fb  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e300  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e305  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e309  lea     rcx, [rsp+270h+var_210]
0x18004e30e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e313  lea     rdx, asc_1801D0CE8; "."
0x18004e31a  mov     rcx, rax
0x18004e31d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e322  mov     rdx, rsi
0x18004e325  cmp     qword ptr [rbx-20h], 0Fh
0x18004e32a  jbe     short loc_18004E32F
0x18004e32c  mov     rdx, [rsi]
0x18004e32f  mov     r8, [rbx-28h]
0x18004e333  mov     rcx, rax
0x18004e336  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e33b  lea     rdx, asc_1801D5B8C; " = "
0x18004e342  mov     rcx, rax
0x18004e345  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e34a  lea     rdx, [rbx-18h]
0x18004e34e  cmp     qword ptr [rbx], 0Fh
0x18004e352  jbe     short loc_18004E357
0x18004e354  mov     rdx, [rdx]
0x18004e357  mov     r8, [rbx-8]
0x18004e35b  mov     rcx, rax
0x18004e35e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e363  mov     rax, [rsp+270h+var_240]
0x18004e368  add     rax, r12
0x18004e36b  mov     [rsp+270h+var_240], rax
0x18004e370  add     rsi, r13
0x18004e373  add     rbx, r13
0x18004e376  cmp     rsi, [rsp+270h+var_238]
0x18004e37b  jnz     loc_18004E2E1
0x18004e381  lea     rdx, aWhere; ") WHERE "
0x18004e388  lea     rcx, [rsp+270h+var_210]
0x18004e38d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e392  lea     rdx, [rbp+170h+var_120]
0x18004e396  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e39b  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e3a0  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e3a4  mov     rcx, rax
0x18004e3a7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e3ac  lea     rdx, asc_1801D0CE8; "."
0x18004e3b3  mov     rcx, rax
0x18004e3b6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e3bb  mov     rcx, rax
0x18004e3be  xorps   xmm0, xmm0
0x18004e3c1  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004e3c8  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000a
0x18004e3d0  movdqu  [rbp+170h+var_B0], xmm1
0x18004e3d8  movsd   xmm0, qword ptr cs:aCultureId; "culture_id"
0x18004e3e0  movsd   [rbp+170h+Block], xmm0
0x18004e3e8  movzx   eax, word ptr cs:aCultureId+8; "id"
0x18004e3ef  mov     word ptr [rbp+170h+Block+8], ax
0x18004e3f6  xor     esi, esi
0x18004e3f8  mov     byte ptr [rbp+170h+Block+0Ah], sil
0x18004e3ff  lea     r8d, [rsi+0Ah]
0x18004e403  lea     rdx, [rbp+170h+Block]
0x18004e40a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e40f  lea     rdx, aIsNull; " IS NULL;"
0x18004e416  mov     rcx, rax
0x18004e419  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e41e  nop
0x18004e41f  mov     ebx, 1000h
0x18004e424  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18004e42b  cmp     rax, 0Fh
0x18004e42f  jbe     short loc_18004E470
0x18004e431  mov     rcx, [rbp+170h+Block]; Block
0x18004e438  mov     rdx, rcx
0x18004e43b  inc     rax
0x18004e43e  cmp     rax, rbx
0x18004e441  jb      short loc_18004E46A
0x18004e443  mov     rcx, [rcx-8]
0x18004e447  sub     rdx, rcx
0x18004e44a  lea     rax, [rdx-8]
0x18004e44e  cmp     rax, 1Fh
0x18004e452  jbe     short loc_18004E46A
0x18004e454  mov     [rsp+270h+Reserved], rsi; Reserved
0x18004e459  xor     r9d, r9d; LineNo
0x18004e45c  xor     r8d, r8d; FileName
0x18004e45f  xor     edx, edx; FunctionName
0x18004e461  xor     ecx, ecx; Expression
0x18004e463  call    cs:__imp__invoke_watson
0x18004e46a  call    cs:__imp_free
0x18004e470  lea     rcx, [rbp+170h+var_80]
0x18004e477  call    ?MapName@?$Table@VCultures@Tables@Meta@RepoMan@@V?$TablePolicy@UCultures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Cultures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Cultures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Culture_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Cultures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x18004e47c  nop
0x18004e47d  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18004e484  lea     rcx, [rsp+270h+var_210]
0x18004e489  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e48e  lea     rdx, [rbp+170h+var_80]
0x18004e495  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004e49d  cmova   rdx, [rbp+170h+var_80]
0x18004e4a5  mov     r8, qword ptr [rbp+170h+var_70]
0x18004e4ac  mov     rcx, rax
0x18004e4af  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e4b4  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x18004e4bb  mov     rcx, rax
0x18004e4be  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e4c3  lea     rdx, aInsertInto; "INSERT INTO "
0x18004e4ca  lea     rcx, [rsp+270h+var_210]
0x18004e4cf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e4d4  lea     rdx, [rbp+170h+var_80]
0x18004e4db  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004e4e3  cmova   rdx, [rbp+170h+var_80]
0x18004e4eb  mov     r8, qword ptr [rbp+170h+var_70]
0x18004e4f2  mov     rcx, rax
0x18004e4f5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e4fa  lea     rdx, aSelect; " SELECT "
0x18004e501  mov     rcx, rax
0x18004e504  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e509  lea     rdx, [rbp+170h+var_E0]
0x18004e510  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004e518  cmova   rdx, [rbp+170h+var_E0]
0x18004e520  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004e527  mov     rcx, rax
0x18004e52a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e52f  lea     rdx, asc_1801D0CE8; "."
0x18004e536  mov     rcx, rax
0x18004e539  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e53e  mov     rcx, rax
0x18004e541  xorps   xmm0, xmm0
0x18004e544  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18004e548  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000a
0x18004e550  movdqu  [rbp+170h+var_F0], xmm1
0x18004e558  movsd   xmm0, qword ptr cs:aCultureId; "culture_id"
0x18004e560  movsd   [rbp+170h+var_100], xmm0
0x18004e565  movzx   eax, word ptr cs:aCultureId+8; "id"
0x18004e56c  mov     word ptr [rbp+170h+var_100+8], ax
0x18004e570  mov     byte ptr [rbp+170h+var_100+0Ah], sil
0x18004e574  mov     r8d, 0Ah
0x18004e57a  lea     rdx, [rbp+170h+var_100]
0x18004e57e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e583  lea     rdx, aAsIncoming; " AS incoming, "
0x18004e58a  mov     rcx, rax
0x18004e58d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e592  lea     rdx, [rbp+170h+var_120]
0x18004e596  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e59b  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e5a0  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e5a4  mov     rcx, rax
0x18004e5a7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e5ac  lea     rdx, asc_1801D0CE8; "."
0x18004e5b3  mov     rcx, rax
0x18004e5b6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e5bb  mov     rcx, rax
0x18004e5be  xorps   xmm0, xmm0
0x18004e5c1  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004e5c8  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000a
0x18004e5d0  movdqu  [rbp+170h+var_B0], xmm1
0x18004e5d8  movsd   xmm0, qword ptr cs:aCultureId; "culture_id"
0x18004e5e0  movsd   [rbp+170h+Block], xmm0
0x18004e5e8  movzx   eax, word ptr cs:aCultureId+8; "id"
0x18004e5ef  mov     word ptr [rbp+170h+Block+8], ax
0x18004e5f6  mov     byte ptr [rbp+170h+Block+0Ah], sil
0x18004e5fd  mov     r8d, 0Ah
0x18004e603  lea     rdx, [rbp+170h+Block]
0x18004e60a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e60f  lea     rdx, aAsClientFrom; " AS client FROM "
0x18004e616  mov     rcx, rax
0x18004e619  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e61e  lea     rdx, [rbp+170h+var_E0]
0x18004e625  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004e62d  cmova   rdx, [rbp+170h+var_E0]
0x18004e635  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004e63c  mov     rcx, rax
0x18004e63f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e644  lea     rdx, aInnerJoin; " INNER JOIN "
0x18004e64b  mov     rcx, rax
0x18004e64e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e653  lea     rdx, [rbp+170h+var_120]
0x18004e657  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004e65c  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004e661  mov     r8, qword ptr [rbp+170h+var_110]
0x18004e665  mov     rcx, rax
0x18004e668  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004e66d  lea     rdx, aOn; " ON ("
0x18004e674  mov     rcx, rax
0x18004e677  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004e67c  nop
0x18004e67d  lea     rcx, [rbp+170h+Block]
0x18004e684  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004e689  mov     esi, 4DE1h
0x18004e68e  mov     [rbp+170h+Block], rsi
0x18004e695  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18004e69d  movdqu  [rbp+170h+var_B0], xmm6
0x18004e6a5  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x18004e6ac  cmp     rax, 0Fh
0x18004e6b0  jbe     short loc_18004E6F2
0x18004e6b2  mov     rcx, [rbp+170h+var_100]; Block
0x18004e6b6  mov     rdx, rcx
0x18004e6b9  inc     rax
0x18004e6bc  cmp     rax, rbx
0x18004e6bf  jb      short loc_18004E6EC
0x18004e6c1  mov     rcx, [rcx-8]
0x18004e6c5  sub     rdx, rcx
0x18004e6c8  lea     rax, [rdx-8]
0x18004e6cc  cmp     rax, 1Fh
  ... truncated ...
```
