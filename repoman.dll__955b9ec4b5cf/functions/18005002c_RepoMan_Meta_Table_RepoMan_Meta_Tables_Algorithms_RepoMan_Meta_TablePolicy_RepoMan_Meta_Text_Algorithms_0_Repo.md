# RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18005002c`
- end: `0x180050d6a`
- name: `?CreateText@?$Table@VAlgorithms@Tables@Meta@RepoMan@@V?$TablePolicy@UAlgorithms@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3390`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004dc78`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18004e004`
- `0x18005002c`
- `0x180050ec8`
- `0x180053140`
- `0x1800531a4`
- `0x18005746c`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005039a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180050618`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005039a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180050618`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050393`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050611`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050393`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050611`

## string_xrefs

- `0x1800503e4`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x1800503ad`: `CREATE TABLE IF NOT EXISTS `
- `0x180050cca`: `CREATE TABLE IF NOT EXISTS `
- `0x1800504b1`: ` AS incoming, `
- `0x1800508e6`: `REPLACE INTO `
- `0x180050b2e`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  int v13; // ecx
  __int64 v14; // rax
  __int64 *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 *v18; // rsi
  _QWORD *v19; // rbx
  __int64 *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdx
  __int64 v27; // rax
  __int64 *v28; // rdx
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
  __int64 *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 *v53; // rdx
  __int64 v54; // rax
  __m128i v55; // xmm6
  void *v56; // rcx
  __int64 v57; // rax
  __int64 *v58; // rbx
  _QWORD *v59; // rsi
  __int64 *v60; // r15
  __int64 *v61; // rdx
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
  __int64 v105; // [rsp+158h] [rbp+50h] BYREF
  __int64 v106; // [rsp+160h] [rbp+58h]
  __m128i v107; // [rsp+168h] [rbp+60h]
  void *v108[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v109; // [rsp+188h] [rbp+80h]
  _QWORD v110[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v111; // [rsp+1A8h] [rbp+A0h]
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v113; // [rsp+1C8h] [rbp+C0h]
  __int128 v114; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v115; // [rsp+1E8h] [rbp+E0h]
  _QWORD v116[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v117; // [rsp+208h] [rbp+100h]
  __int128 v118; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int64 v120; // [rsp+238h] [rbp+130h]

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v101);
  if ( a4 == 2048 )
  {
    v118 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v118) = 0;
    v120 = 0;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v110);
    v107 = _mm_load_si128((const __m128i *)&_xmm);
    v105 = *(_QWORD *)"Algorithms";
    v106 = *(unsigned __int16 *)"ms";
    BYTE2(v106) = 0;
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v8 = (__int64 *)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v107.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v10,
      2050,
      (unsigned int)v110,
      (_DWORD)a1 + 448,
      (__int64)v101);
    v11 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" FROM ");
    v12 = v110;
    if ( v111.m128i_i64[1] > 0xFuLL )
      v12 = (_QWORD *)v110[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v11, (__int64)v12, v111.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v110,
      (unsigned int)&v105,
      (__int64)v101);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" LEFT OUTER JOIN ");
    v15 = &v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v15 = (__int64 *)v105;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v107.m128i_u64[0]);
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
        if ( v107.m128i_i64[1] > 0xFuLL )
          v20 = (__int64 *)v105;
        v21 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v20,
                v107.m128i_u64[0]);
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
    if ( v107.m128i_i64[1] > 0xFuLL )
      v28 = (__int64 *)v105;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v107.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"algorithm_id";
    Block[1] = (void *)*(unsigned int *)"m_id";
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 0xCu);
    std::operator<<<std::char_traits<char>>(v31, (__int64)" IS NULL;");
    if ( v113.m128i_i64[1] > 0xFuLL )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(v113.m128i_i64[1] + 1) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v32);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v116);
    v33 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v34 = v116;
    if ( v117.m128i_i64[1] > 0xFuLL )
      v34 = (_QWORD *)v116[0];
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, (__int64)v34, v117.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v35,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v36 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"INSERT INTO ");
    v37 = v116;
    if ( v117.m128i_i64[1] > 0xFuLL )
      v37 = (_QWORD *)v116[0];
    v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, (__int64)v37, v117.m128i_u64[0]);
    v39 = std::operator<<<std::char_traits<char>>(v38, (__int64)" SELECT ");
    v40 = v110;
    if ( v111.m128i_i64[1] > 0xFuLL )
      v40 = (_QWORD *)v110[0];
    v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, (__int64)v40, v111.m128i_u64[0]);
    v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)".");
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    v108[0] = *(void **)"algorithm_id";
    v108[1] = (void *)*(unsigned int *)"m_id";
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v108, 0xCu);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = &v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v45 = (__int64 *)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v107.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"algorithm_id";
    Block[1] = (void *)*(unsigned int *)"m_id";
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 0xCu);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v110;
    if ( v111.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v110[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v111.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = &v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v53 = (__int64 *)v105;
    v54 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v52, (__int64)v53, v107.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v54, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v55 = _mm_load_si128((const __m128i *)&_xmm);
    v113 = v55;
    if ( v109.m128i_i64[1] > 0xFuLL )
    {
      v56 = v108[0];
      if ( (unsigned __int64)(v109.m128i_i64[1] + 1) >= 0x1000 )
      {
        v56 = (void *)*((_QWORD *)v108[0] - 1);
        if ( (unsigned __int64)((char *)v108[0] - (char *)v56 - 8) > 0x1F )
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
        if ( v107.m128i_i64[1] > 0xFuLL )
          v61 = (__int64 *)v105;
        v62 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v102,
                (__int64)v61,
                v107.m128i_u64[0]);
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
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>::BuildText(
      v68,
      0,
      144,
      (unsigned int)v110,
      (__int64)&v105,
      (__int64)v101);
    RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>::BuildText(
      v69,
      1,
      784,
      (unsigned int)v110,
      Reserved,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
    v70 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v71 = v110;
    if ( v111.m128i_i64[1] > 0xFuLL )
      v71 = (_QWORD *)v110[0];
    v72 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v70, (__int64)v71, v111.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v72, (__int64)";");
    std::stringbuf::str(v103, a2);
    std::string::_Tidy_deallocate(v116);
    v116[0] = 19937;
    v117 = v55;
    std::string::_Tidy_deallocate(&v105);
    v105 = 19937;
    v107 = v55;
    std::string::_Tidy_deallocate(v110);
    v110[0] = 19937;
    v111 = v55;
    std::string::_Tidy_deallocate(&v118);
    *(_QWORD *)&v118 = 19937;
    si128 = v55;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
    v104[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v73 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"DROP TABLE IF EXISTS ");
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v108);
    v75 = v74[2];
    if ( v74[3] > 0xFu )
      v74 = (_QWORD *)*v74;
    v76 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v73, (__int64)v74, v75);
    std::operator<<<std::char_traits<char>>(v76, (__int64)";");
    std::string::_Tidy_deallocate(v108);
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
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Algorithms");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v108 = 0;
        v109 = 0;
        std::string::_Construct<1,char const *>(v108, "Algorithms", 0xAu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
          v91,
          4,
          (unsigned int)v108,
          (_DWORD)a1 + 448,
          (__int64)v101);
        std::string::_Tidy_deallocate(v108);
        std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x40u:
        v92 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Algorithms");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Algorithms");
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
    *(_OWORD *)v108 = 0;
    v109 = 0;
    std::string::_Construct<1,char const *>(v108, "Algorithms", 0xAu);
    v96(a1, v108);
    if ( v109.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v108, v108[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v108 = 0;
  v109 = 0;
  std::string::_Construct<1,char const *>(v108, "Algorithms", 0xAu);
  v78 = v108;
  v77 = 4;
LABEL_66:
  v114 = 0;
  v115 = 0;
  v114 = *(_OWORD *)v78;
  v115 = *((__m128i *)v78 + 1);
  *(_BYTE *)v78 = 0;
  v78[2] = 0;
  v78[3] = (void *)15;
  if ( (v77 & 4) != 0 )
  {
    v77 &= ~4u;
    std::string::_Tidy_deallocate(v108);
  }
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v77 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v113 = v79;
  }
  v80 = &v114;
  if ( v115.m128i_i64[1] > 0xFuLL )
    v80 = (__int128 *)v114;
  v81 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
          (__int64)v102,
          (__int64)v80,
          v115.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v81, (__int64)"(");
  v82 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
    v83,
    a4,
    (unsigned int)&v114,
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v87,
      8,
      (unsigned int)&v114,
      v82,
      (__int64)v101);
    std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)";");
  std::stringbuf::str(v103, a2);
  std::string::_Tidy_deallocate(&v114);
  *(_QWORD *)&v114 = 19937;
  v115 = v79;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
  v104[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
  return a2;
}

```

## disassembly

```asm
0x18005002c  mov     rax, rsp
0x18005002f  mov     [rax+18h], rbx
0x180050033  mov     [rax+20h], rsi
0x180050037  push    rbp
0x180050038  push    r12
0x18005003a  push    r13
0x18005003c  push    r14
0x18005003e  push    r15
0x180050040  lea     rbp, [rax-178h]
0x180050047  sub     rsp, 250h
0x18005004e  movaps  xmmword ptr [rax-38h], xmm6
0x180050052  mov     rax, cs:__security_cookie
0x180050059  xor     rax, rsp
0x18005005c  mov     [rbp+170h+var_38], rax
0x180050063  movzx   esi, r9w
0x180050067  mov     r14, rdx
0x18005006a  mov     r15, rcx
0x18005006d  mov     [rsp+270h+var_238], rdx
0x180050072  xor     r13d, r13d
0x180050075  mov     [rsp+270h+var_230], r13d
0x18005007a  lea     rcx, [rsp+270h+var_220]
0x18005007f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180050084  nop
0x180050085  mov     eax, 800h
0x18005008a  cmp     ax, si
0x18005008d  jnz     loc_180050829
0x180050093  xorps   xmm0, xmm0
0x180050096  movups  [rbp+170h+var_60], xmm0
0x18005009d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800500a5  movdqu  [rbp+170h+var_50], xmm1
0x1800500ad  mov     byte ptr [rbp+170h+var_60], r13b
0x1800500b4  mov     [rbp+170h+var_40], r13
0x1800500bb  lea     rcx, [rbp+170h+var_E0]
0x1800500c2  call    ?IndexName@?$Table@VAlgorithms@Tables@Meta@RepoMan@@V?$TablePolicy@UAlgorithms@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x1800500c7  nop
0x1800500c8  xorps   xmm0, xmm0
0x1800500cb  movups  [rbp+170h+var_120], xmm0
0x1800500cf  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000a
0x1800500d7  movdqu  [rbp+170h+var_110], xmm1
0x1800500dc  movsd   xmm0, qword ptr cs:aAlgorithms; "Algorithms"
0x1800500e4  movsd   qword ptr [rbp+170h+var_120], xmm0
0x1800500e9  movzx   eax, word ptr cs:aAlgorithms+8; "ms"
0x1800500f0  mov     word ptr [rbp+170h+var_120+8], ax
0x1800500f4  mov     byte ptr [rbp+170h+var_120+0Ah], r13b
0x1800500f8  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x1800500ff  lea     rcx, [rsp+270h+var_210]
0x180050104  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050109  lea     rdx, [rbp+170h+var_120]
0x18005010d  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180050112  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180050117  mov     r8, qword ptr [rbp+170h+var_110]
0x18005011b  mov     rcx, rax
0x18005011e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180050123  lea     rdx, aSelectNull; " SELECT NULL"
0x18005012a  mov     rcx, rax
0x18005012d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050132  lea     r9, [r15+1C0h]
0x180050139  mov     edx, 802h
0x18005013e  lea     rax, [rsp+270h+var_220]
0x180050143  mov     [rsp+270h+Reserved], rax
0x180050148  lea     r8, [rbp+170h+var_E0]
0x18005014f  call    ?BuildText@?$RowType@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180050154  lea     rdx, aFrom_0; " FROM "
0x18005015b  lea     rcx, [rsp+270h+var_210]
0x180050160  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050165  lea     rdx, [rbp+170h+var_E0]
0x18005016c  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x180050174  cmova   rdx, [rbp+170h+var_E0]
0x18005017c  mov     r8, qword ptr [rbp+170h+var_D0]
0x180050183  mov     rcx, rax
0x180050186  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005018b  lea     edx, [r13+10h]
0x18005018f  lea     rax, [rsp+270h+var_220]
0x180050194  mov     [rsp+270h+Reserved], rax
0x180050199  lea     r9, [rbp+170h+var_120]
0x18005019d  lea     r8, [rbp+170h+var_E0]
0x1800501a4  call    ?BuildText@?$RowType@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x1800501a9  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x1800501b0  lea     rcx, [rsp+270h+var_210]
0x1800501b5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800501ba  lea     rdx, [rbp+170h+var_120]
0x1800501be  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x1800501c3  cmova   rdx, qword ptr [rbp+170h+var_120]
0x1800501c8  mov     r8, qword ptr [rbp+170h+var_110]
0x1800501cc  mov     rcx, rax
0x1800501cf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800501d4  lea     rdx, aOn; " ON ("
0x1800501db  mov     rcx, rax
0x1800501de  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800501e3  mov     eax, r13d
0x1800501e6  mov     [rsp+270h+var_240], rax
0x1800501eb  mov     rcx, [r15+1E8h]
0x1800501f2  mov     [rsp+270h+var_238], rcx
0x1800501f7  mov     rsi, [r15+1E0h]
0x1800501fe  lea     r12d, [r13+1]
0x180050202  lea     r13d, [rax+40h]
0x180050206  cmp     rsi, rcx
0x180050209  jz      loc_1800502B3
0x18005020f  lea     rbx, [rsi+38h]
0x180050213  test    rax, rax
0x180050216  jz      short loc_180050229
0x180050218  lea     rdx, aAnd_1; " AND "
0x18005021f  lea     rcx, [rsp+270h+var_210]
0x180050224  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050229  lea     rdx, [rbp+170h+var_120]
0x18005022d  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180050232  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180050237  mov     r8, qword ptr [rbp+170h+var_110]
0x18005023b  lea     rcx, [rsp+270h+var_210]
0x180050240  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180050245  lea     rdx, asc_1801D0CE8; "."
0x18005024c  mov     rcx, rax
0x18005024f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050254  mov     rdx, rsi
0x180050257  cmp     qword ptr [rbx-20h], 0Fh
0x18005025c  jbe     short loc_180050261
0x18005025e  mov     rdx, [rsi]
0x180050261  mov     r8, [rbx-28h]
0x180050265  mov     rcx, rax
0x180050268  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005026d  lea     rdx, asc_1801D5B8C; " = "
0x180050274  mov     rcx, rax
0x180050277  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005027c  lea     rdx, [rbx-18h]
0x180050280  cmp     qword ptr [rbx], 0Fh
0x180050284  jbe     short loc_180050289
0x180050286  mov     rdx, [rdx]
0x180050289  mov     r8, [rbx-8]
0x18005028d  mov     rcx, rax
0x180050290  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180050295  mov     rax, [rsp+270h+var_240]
0x18005029a  add     rax, r12
0x18005029d  mov     [rsp+270h+var_240], rax
0x1800502a2  add     rsi, r13
0x1800502a5  add     rbx, r13
0x1800502a8  cmp     rsi, [rsp+270h+var_238]
0x1800502ad  jnz     loc_180050213
0x1800502b3  lea     rdx, aWhere; ") WHERE "
0x1800502ba  lea     rcx, [rsp+270h+var_210]
0x1800502bf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800502c4  lea     rdx, [rbp+170h+var_120]
0x1800502c8  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x1800502cd  cmova   rdx, qword ptr [rbp+170h+var_120]
0x1800502d2  mov     r8, qword ptr [rbp+170h+var_110]
0x1800502d6  mov     rcx, rax
0x1800502d9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800502de  lea     rdx, asc_1801D0CE8; "."
0x1800502e5  mov     rcx, rax
0x1800502e8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800502ed  mov     rcx, rax
0x1800502f0  xorps   xmm0, xmm0
0x1800502f3  movups  xmmword ptr [rbp+170h+Block], xmm0
0x1800502fa  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x180050302  movdqu  [rbp+170h+var_B0], xmm1
0x18005030a  movsd   xmm0, qword ptr cs:aAlgorithmId; "algorithm_id"
0x180050312  movsd   [rbp+170h+Block], xmm0
0x18005031a  mov     eax, dword ptr cs:aAlgorithmId+8; "m_id"
0x180050320  mov     dword ptr [rbp+170h+Block+8], eax
0x180050326  xor     esi, esi
0x180050328  mov     byte ptr [rbp+170h+Block+0Ch], sil
0x18005032f  lea     r8d, [rsi+0Ch]
0x180050333  lea     rdx, [rbp+170h+Block]
0x18005033a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005033f  lea     rdx, aIsNull; " IS NULL;"
0x180050346  mov     rcx, rax
0x180050349  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005034e  nop
0x18005034f  mov     ebx, 1000h
0x180050354  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18005035b  cmp     rax, 0Fh
0x18005035f  jbe     short loc_1800503A0
0x180050361  mov     rcx, [rbp+170h+Block]; Block
0x180050368  mov     rdx, rcx
0x18005036b  inc     rax
0x18005036e  cmp     rax, rbx
0x180050371  jb      short loc_18005039A
0x180050373  mov     rcx, [rcx-8]
0x180050377  sub     rdx, rcx
0x18005037a  lea     rax, [rdx-8]
0x18005037e  cmp     rax, 1Fh
0x180050382  jbe     short loc_18005039A
0x180050384  mov     [rsp+270h+Reserved], rsi; Reserved
0x180050389  xor     r9d, r9d; LineNo
0x18005038c  xor     r8d, r8d; FileName
0x18005038f  xor     edx, edx; FunctionName
0x180050391  xor     ecx, ecx; Expression
0x180050393  call    cs:__imp__invoke_watson
0x18005039a  call    cs:__imp_free
0x1800503a0  lea     rcx, [rbp+170h+var_80]
0x1800503a7  call    ?MapName@?$Table@VAlgorithms@Tables@Meta@RepoMan@@V?$TablePolicy@UAlgorithms@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UAlgorithm_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UAlgorithms@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Algorithms,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Algorithm_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Algorithms,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x1800503ac  nop
0x1800503ad  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x1800503b4  lea     rcx, [rsp+270h+var_210]
0x1800503b9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800503be  lea     rdx, [rbp+170h+var_80]
0x1800503c5  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x1800503cd  cmova   rdx, [rbp+170h+var_80]
0x1800503d5  mov     r8, qword ptr [rbp+170h+var_70]
0x1800503dc  mov     rcx, rax
0x1800503df  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800503e4  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x1800503eb  mov     rcx, rax
0x1800503ee  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800503f3  lea     rdx, aInsertInto; "INSERT INTO "
0x1800503fa  lea     rcx, [rsp+270h+var_210]
0x1800503ff  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050404  lea     rdx, [rbp+170h+var_80]
0x18005040b  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x180050413  cmova   rdx, [rbp+170h+var_80]
0x18005041b  mov     r8, qword ptr [rbp+170h+var_70]
0x180050422  mov     rcx, rax
0x180050425  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005042a  lea     rdx, aSelect; " SELECT "
0x180050431  mov     rcx, rax
0x180050434  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180050439  lea     rdx, [rbp+170h+var_E0]
0x180050440  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x180050448  cmova   rdx, [rbp+170h+var_E0]
0x180050450  mov     r8, qword ptr [rbp+170h+var_D0]
0x180050457  mov     rcx, rax
0x18005045a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005045f  lea     rdx, asc_1801D0CE8; "."
0x180050466  mov     rcx, rax
0x180050469  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005046e  mov     rcx, rax
0x180050471  xorps   xmm0, xmm0
0x180050474  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x180050478  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x180050480  movdqu  [rbp+170h+var_F0], xmm1
0x180050488  movsd   xmm0, qword ptr cs:aAlgorithmId; "algorithm_id"
0x180050490  movsd   [rbp+170h+var_100], xmm0
0x180050495  mov     eax, dword ptr cs:aAlgorithmId+8; "m_id"
0x18005049b  mov     dword ptr [rbp+170h+var_100+8], eax
0x18005049e  mov     byte ptr [rbp+170h+var_100+0Ch], sil
0x1800504a2  mov     r8d, 0Ch
0x1800504a8  lea     rdx, [rbp+170h+var_100]
0x1800504ac  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800504b1  lea     rdx, aAsIncoming; " AS incoming, "
0x1800504b8  mov     rcx, rax
0x1800504bb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800504c0  lea     rdx, [rbp+170h+var_120]
0x1800504c4  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x1800504c9  cmova   rdx, qword ptr [rbp+170h+var_120]
0x1800504ce  mov     r8, qword ptr [rbp+170h+var_110]
0x1800504d2  mov     rcx, rax
0x1800504d5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800504da  lea     rdx, asc_1801D0CE8; "."
0x1800504e1  mov     rcx, rax
0x1800504e4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800504e9  mov     rcx, rax
0x1800504ec  xorps   xmm0, xmm0
0x1800504ef  movups  xmmword ptr [rbp+170h+Block], xmm0
0x1800504f6  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000c
0x1800504fe  movdqu  [rbp+170h+var_B0], xmm1
0x180050506  movsd   xmm0, qword ptr cs:aAlgorithmId; "algorithm_id"
0x18005050e  movsd   [rbp+170h+Block], xmm0
0x180050516  mov     eax, dword ptr cs:aAlgorithmId+8; "m_id"
0x18005051c  mov     dword ptr [rbp+170h+Block+8], eax
0x180050522  mov     byte ptr [rbp+170h+Block+0Ch], sil
0x180050529  mov     r8d, 0Ch
0x18005052f  lea     rdx, [rbp+170h+Block]
0x180050536  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18005053b  lea     rdx, aAsClientFrom; " AS client FROM "
0x180050542  mov     rcx, rax
0x180050545  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005054a  lea     rdx, [rbp+170h+var_E0]
0x180050551  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x180050559  cmova   rdx, [rbp+170h+var_E0]
0x180050561  mov     r8, qword ptr [rbp+170h+var_D0]
0x180050568  mov     rcx, rax
0x18005056b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180050570  lea     rdx, aInnerJoin; " INNER JOIN "
0x180050577  mov     rcx, rax
0x18005057a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18005057f  lea     rdx, [rbp+170h+var_120]
0x180050583  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180050588  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18005058d  mov     r8, qword ptr [rbp+170h+var_110]
0x180050591  mov     rcx, rax
0x180050594  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180050599  lea     rdx, aOn; " ON ("
0x1800505a0  mov     rcx, rax
0x1800505a3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800505a8  nop
0x1800505a9  lea     rcx, [rbp+170h+Block]
0x1800505b0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800505b5  mov     esi, 4DE1h
0x1800505ba  mov     [rbp+170h+Block], rsi
0x1800505c1  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800505c9  movdqu  [rbp+170h+var_B0], xmm6
0x1800505d1  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x1800505d8  cmp     rax, 0Fh
0x1800505dc  jbe     short loc_18005061E
0x1800505de  mov     rcx, [rbp+170h+var_100]; Block
0x1800505e2  mov     rdx, rcx
0x1800505e5  inc     rax
0x1800505e8  cmp     rax, rbx
0x1800505eb  jb      short loc_180050618
0x1800505ed  mov     rcx, [rcx-8]
0x1800505f1  sub     rdx, rcx
  ... truncated ...
```
