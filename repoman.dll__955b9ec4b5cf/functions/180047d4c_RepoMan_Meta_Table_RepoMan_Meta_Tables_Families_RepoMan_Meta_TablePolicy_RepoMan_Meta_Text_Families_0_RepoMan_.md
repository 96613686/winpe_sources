# RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x180047d4c`
- end: `0x180048a80`
- name: `?CreateText@?$Table@VFamilies@Tables@Meta@RepoMan@@V?$TablePolicy@UFamilies@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3380`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004412c`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x1800444b8`
- `0x180047d4c`
- `0x18004b130`
- `0x18004b194`
- `0x18004efac`
- `0x180050ec8`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800480b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004832e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800480b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004832e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800480a9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180048327`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800480a9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180048327`

## string_xrefs

- `0x1800480fa`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x1800480c3`: `CREATE TABLE IF NOT EXISTS `
- `0x1800489e0`: `CREATE TABLE IF NOT EXISTS `
- `0x1800481c7`: ` AS incoming, `
- `0x1800485fc`: `REPLACE INTO `
- `0x180048844`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v109);
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    v105 = 0x7365696C696D6146uLL;
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v8 = (__int128 *)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v106.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    Block[0] = *(void **)"family_id";
    Block[1] = (void *)(unsigned __int8)aFamilyId[8];
    BYTE1(Block[1]) = 0;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 9u);
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v115);
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
    v107[0] = *(void **)"family_id";
    v107[1] = (void *)(unsigned __int8)aFamilyId[8];
    BYTE1(v107[1]) = 0;
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v107, 9u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = &v105;
    if ( v106.m128i_i64[1] > 0xFuLL )
      v45 = (__int128 *)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v106.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v112 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"family_id";
    Block[1] = (void *)(unsigned __int8)aFamilyId[8];
    BYTE1(Block[1]) = 0;
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 9u);
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
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>::BuildText(
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
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v107);
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
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Families");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v107 = 0;
        v108 = 0;
        std::string::_Construct<1,char const *>(v107, "Families", 8u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Families");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Families");
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
    std::string::_Construct<1,char const *>(v107, "Families", 8u);
    v96(a1, v107);
    if ( v108.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v107, v107[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(v107, "Families", 8u);
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
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
0x180047d4c  mov     rax, rsp
0x180047d4f  mov     [rax+18h], rbx
0x180047d53  mov     [rax+20h], rsi
0x180047d57  push    rbp
0x180047d58  push    r12
0x180047d5a  push    r13
0x180047d5c  push    r14
0x180047d5e  push    r15
0x180047d60  lea     rbp, [rax-178h]
0x180047d67  sub     rsp, 250h
0x180047d6e  movaps  xmmword ptr [rax-38h], xmm6
0x180047d72  mov     rax, cs:__security_cookie
0x180047d79  xor     rax, rsp
0x180047d7c  mov     [rbp+170h+var_38], rax
0x180047d83  movzx   esi, r9w
0x180047d87  mov     r14, rdx
0x180047d8a  mov     r15, rcx
0x180047d8d  mov     [rsp+270h+var_238], rdx
0x180047d92  xor     r13d, r13d
0x180047d95  mov     [rsp+270h+var_230], r13d
0x180047d9a  lea     rcx, [rsp+270h+var_220]
0x180047d9f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180047da4  nop
0x180047da5  mov     eax, 800h
0x180047daa  cmp     ax, si
0x180047dad  jnz     loc_18004853F
0x180047db3  xorps   xmm0, xmm0
0x180047db6  movups  [rbp+170h+var_60], xmm0
0x180047dbd  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180047dc5  movdqu  [rbp+170h+var_50], xmm1
0x180047dcd  mov     byte ptr [rbp+170h+var_60], r13b
0x180047dd4  mov     [rbp+170h+var_40], r13
0x180047ddb  lea     rcx, [rbp+170h+var_E0]
0x180047de2  call    ?IndexName@?$Table@VFamilies@Tables@Meta@RepoMan@@V?$TablePolicy@UFamilies@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x180047de7  nop
0x180047de8  xorps   xmm0, xmm0
0x180047deb  movups  [rbp+170h+var_120], xmm0
0x180047def  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000008
0x180047df7  movdqu  [rbp+170h+var_110], xmm1
0x180047dfc  mov     rax, 7365696C696D6146h
0x180047e06  mov     qword ptr [rbp+170h+var_120], rax
0x180047e0a  mov     byte ptr [rbp+170h+var_120+8], r13b
0x180047e0e  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x180047e15  lea     rcx, [rsp+270h+var_210]
0x180047e1a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047e1f  lea     rdx, [rbp+170h+var_120]
0x180047e23  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180047e28  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180047e2d  mov     r8, qword ptr [rbp+170h+var_110]
0x180047e31  mov     rcx, rax
0x180047e34  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047e39  lea     rdx, aSelectNull; " SELECT NULL"
0x180047e40  mov     rcx, rax
0x180047e43  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047e48  lea     r9, [r15+1C0h]
0x180047e4f  mov     edx, 802h
0x180047e54  lea     rax, [rsp+270h+var_220]
0x180047e59  mov     [rsp+270h+Reserved], rax
0x180047e5e  lea     r8, [rbp+170h+var_E0]
0x180047e65  call    ?BuildText@?$RowType@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180047e6a  lea     rdx, aFrom_0; " FROM "
0x180047e71  lea     rcx, [rsp+270h+var_210]
0x180047e76  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047e7b  lea     rdx, [rbp+170h+var_E0]
0x180047e82  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x180047e8a  cmova   rdx, [rbp+170h+var_E0]
0x180047e92  mov     r8, qword ptr [rbp+170h+var_D0]
0x180047e99  mov     rcx, rax
0x180047e9c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047ea1  lea     edx, [r13+10h]
0x180047ea5  lea     rax, [rsp+270h+var_220]
0x180047eaa  mov     [rsp+270h+Reserved], rax
0x180047eaf  lea     r9, [rbp+170h+var_120]
0x180047eb3  lea     r8, [rbp+170h+var_E0]
0x180047eba  call    ?BuildText@?$RowType@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180047ebf  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x180047ec6  lea     rcx, [rsp+270h+var_210]
0x180047ecb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047ed0  lea     rdx, [rbp+170h+var_120]
0x180047ed4  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180047ed9  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180047ede  mov     r8, qword ptr [rbp+170h+var_110]
0x180047ee2  mov     rcx, rax
0x180047ee5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047eea  lea     rdx, aOn; " ON ("
0x180047ef1  mov     rcx, rax
0x180047ef4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047ef9  mov     eax, r13d
0x180047efc  mov     [rsp+270h+var_240], rax
0x180047f01  mov     rcx, [r15+1E8h]
0x180047f08  mov     [rsp+270h+var_238], rcx
0x180047f0d  mov     rsi, [r15+1E0h]
0x180047f14  lea     r12d, [r13+1]
0x180047f18  lea     r13d, [rax+40h]
0x180047f1c  cmp     rsi, rcx
0x180047f1f  jz      loc_180047FC9
0x180047f25  lea     rbx, [rsi+38h]
0x180047f29  test    rax, rax
0x180047f2c  jz      short loc_180047F3F
0x180047f2e  lea     rdx, aAnd_1; " AND "
0x180047f35  lea     rcx, [rsp+270h+var_210]
0x180047f3a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047f3f  lea     rdx, [rbp+170h+var_120]
0x180047f43  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180047f48  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180047f4d  mov     r8, qword ptr [rbp+170h+var_110]
0x180047f51  lea     rcx, [rsp+270h+var_210]
0x180047f56  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047f5b  lea     rdx, asc_1801D0CE8; "."
0x180047f62  mov     rcx, rax
0x180047f65  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047f6a  mov     rdx, rsi
0x180047f6d  cmp     qword ptr [rbx-20h], 0Fh
0x180047f72  jbe     short loc_180047F77
0x180047f74  mov     rdx, [rsi]
0x180047f77  mov     r8, [rbx-28h]
0x180047f7b  mov     rcx, rax
0x180047f7e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047f83  lea     rdx, asc_1801D5B8C; " = "
0x180047f8a  mov     rcx, rax
0x180047f8d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047f92  lea     rdx, [rbx-18h]
0x180047f96  cmp     qword ptr [rbx], 0Fh
0x180047f9a  jbe     short loc_180047F9F
0x180047f9c  mov     rdx, [rdx]
0x180047f9f  mov     r8, [rbx-8]
0x180047fa3  mov     rcx, rax
0x180047fa6  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047fab  mov     rax, [rsp+270h+var_240]
0x180047fb0  add     rax, r12
0x180047fb3  mov     [rsp+270h+var_240], rax
0x180047fb8  add     rsi, r13
0x180047fbb  add     rbx, r13
0x180047fbe  cmp     rsi, [rsp+270h+var_238]
0x180047fc3  jnz     loc_180047F29
0x180047fc9  lea     rdx, aWhere; ") WHERE "
0x180047fd0  lea     rcx, [rsp+270h+var_210]
0x180047fd5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180047fda  lea     rdx, [rbp+170h+var_120]
0x180047fde  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x180047fe3  cmova   rdx, qword ptr [rbp+170h+var_120]
0x180047fe8  mov     r8, qword ptr [rbp+170h+var_110]
0x180047fec  mov     rcx, rax
0x180047fef  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180047ff4  lea     rdx, asc_1801D0CE8; "."
0x180047ffb  mov     rcx, rax
0x180047ffe  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048003  mov     rcx, rax
0x180048006  xorps   xmm0, xmm0
0x180048009  movups  xmmword ptr [rbp+170h+Block], xmm0
0x180048010  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x180048018  movdqu  [rbp+170h+var_B0], xmm1
0x180048020  movsd   xmm0, qword ptr cs:aFamilyId; "family_id"
0x180048028  movsd   [rbp+170h+Block], xmm0
0x180048030  mov     al, byte ptr cs:aFamilyId+8; "d"
0x180048036  mov     byte ptr [rbp+170h+Block+8], al
0x18004803c  xor     esi, esi
0x18004803e  mov     byte ptr [rbp+170h+Block+9], sil
0x180048045  lea     r8d, [rsi+9]
0x180048049  lea     rdx, [rbp+170h+Block]
0x180048050  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180048055  lea     rdx, aIsNull; " IS NULL;"
0x18004805c  mov     rcx, rax
0x18004805f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048064  nop
0x180048065  mov     ebx, 1000h
0x18004806a  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x180048071  cmp     rax, 0Fh
0x180048075  jbe     short loc_1800480B6
0x180048077  mov     rcx, [rbp+170h+Block]; Block
0x18004807e  mov     rdx, rcx
0x180048081  inc     rax
0x180048084  cmp     rax, rbx
0x180048087  jb      short loc_1800480B0
0x180048089  mov     rcx, [rcx-8]
0x18004808d  sub     rdx, rcx
0x180048090  lea     rax, [rdx-8]
0x180048094  cmp     rax, 1Fh
0x180048098  jbe     short loc_1800480B0
0x18004809a  mov     [rsp+270h+Reserved], rsi; Reserved
0x18004809f  xor     r9d, r9d; LineNo
0x1800480a2  xor     r8d, r8d; FileName
0x1800480a5  xor     edx, edx; FunctionName
0x1800480a7  xor     ecx, ecx; Expression
0x1800480a9  call    cs:__imp__invoke_watson
0x1800480b0  call    cs:__imp_free
0x1800480b6  lea     rcx, [rbp+170h+var_80]
0x1800480bd  call    ?MapName@?$Table@VFamilies@Tables@Meta@RepoMan@@V?$TablePolicy@UFamilies@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFamily_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFamilies@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Families,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Families,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Family_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Families,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x1800480c2  nop
0x1800480c3  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x1800480ca  lea     rcx, [rsp+270h+var_210]
0x1800480cf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800480d4  lea     rdx, [rbp+170h+var_80]
0x1800480db  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x1800480e3  cmova   rdx, [rbp+170h+var_80]
0x1800480eb  mov     r8, qword ptr [rbp+170h+var_70]
0x1800480f2  mov     rcx, rax
0x1800480f5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800480fa  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x180048101  mov     rcx, rax
0x180048104  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048109  lea     rdx, aInsertInto; "INSERT INTO "
0x180048110  lea     rcx, [rsp+270h+var_210]
0x180048115  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004811a  lea     rdx, [rbp+170h+var_80]
0x180048121  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x180048129  cmova   rdx, [rbp+170h+var_80]
0x180048131  mov     r8, qword ptr [rbp+170h+var_70]
0x180048138  mov     rcx, rax
0x18004813b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180048140  lea     rdx, aSelect; " SELECT "
0x180048147  mov     rcx, rax
0x18004814a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004814f  lea     rdx, [rbp+170h+var_E0]
0x180048156  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004815e  cmova   rdx, [rbp+170h+var_E0]
0x180048166  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004816d  mov     rcx, rax
0x180048170  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180048175  lea     rdx, asc_1801D0CE8; "."
0x18004817c  mov     rcx, rax
0x18004817f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048184  mov     rcx, rax
0x180048187  xorps   xmm0, xmm0
0x18004818a  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18004818e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x180048196  movdqu  [rbp+170h+var_F0], xmm1
0x18004819e  movsd   xmm0, qword ptr cs:aFamilyId; "family_id"
0x1800481a6  movsd   [rbp+170h+var_100], xmm0
0x1800481ab  mov     al, byte ptr cs:aFamilyId+8; "d"
0x1800481b1  mov     byte ptr [rbp+170h+var_100+8], al
0x1800481b4  mov     byte ptr [rbp+170h+var_100+9], sil
0x1800481b8  mov     r8d, 9
0x1800481be  lea     rdx, [rbp+170h+var_100]
0x1800481c2  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800481c7  lea     rdx, aAsIncoming; " AS incoming, "
0x1800481ce  mov     rcx, rax
0x1800481d1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800481d6  lea     rdx, [rbp+170h+var_120]
0x1800481da  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x1800481df  cmova   rdx, qword ptr [rbp+170h+var_120]
0x1800481e4  mov     r8, qword ptr [rbp+170h+var_110]
0x1800481e8  mov     rcx, rax
0x1800481eb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800481f0  lea     rdx, asc_1801D0CE8; "."
0x1800481f7  mov     rcx, rax
0x1800481fa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800481ff  mov     rcx, rax
0x180048202  xorps   xmm0, xmm0
0x180048205  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004820c  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x180048214  movdqu  [rbp+170h+var_B0], xmm1
0x18004821c  movsd   xmm0, qword ptr cs:aFamilyId; "family_id"
0x180048224  movsd   [rbp+170h+Block], xmm0
0x18004822c  mov     al, byte ptr cs:aFamilyId+8; "d"
0x180048232  mov     byte ptr [rbp+170h+Block+8], al
0x180048238  mov     byte ptr [rbp+170h+Block+9], sil
0x18004823f  mov     r8d, 9
0x180048245  lea     rdx, [rbp+170h+Block]
0x18004824c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180048251  lea     rdx, aAsClientFrom; " AS client FROM "
0x180048258  mov     rcx, rax
0x18004825b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048260  lea     rdx, [rbp+170h+var_E0]
0x180048267  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004826f  cmova   rdx, [rbp+170h+var_E0]
0x180048277  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004827e  mov     rcx, rax
0x180048281  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180048286  lea     rdx, aInnerJoin; " INNER JOIN "
0x18004828d  mov     rcx, rax
0x180048290  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180048295  lea     rdx, [rbp+170h+var_120]
0x180048299  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004829e  cmova   rdx, qword ptr [rbp+170h+var_120]
0x1800482a3  mov     r8, qword ptr [rbp+170h+var_110]
0x1800482a7  mov     rcx, rax
0x1800482aa  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800482af  lea     rdx, aOn; " ON ("
0x1800482b6  mov     rcx, rax
0x1800482b9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800482be  nop
0x1800482bf  lea     rcx, [rbp+170h+Block]
0x1800482c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800482cb  mov     esi, 4DE1h
0x1800482d0  mov     [rbp+170h+Block], rsi
0x1800482d7  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x1800482df  movdqu  [rbp+170h+var_B0], xmm6
0x1800482e7  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x1800482ee  cmp     rax, 0Fh
0x1800482f2  jbe     short loc_180048334
0x1800482f4  mov     rcx, [rbp+170h+var_100]; Block
0x1800482f8  mov     rdx, rcx
0x1800482fb  inc     rax
0x1800482fe  cmp     rax, rbx
0x180048301  jb      short loc_18004832E
0x180048303  mov     rcx, [rcx-8]
0x180048307  sub     rdx, rcx
0x18004830a  lea     rax, [rdx-8]
0x18004830e  cmp     rax, 1Fh
  ... truncated ...
```
