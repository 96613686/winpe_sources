# RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18004c104`
- end: `0x18004ce48`
- name: `?CreateText@?$Table@VFlavors@Tables@Meta@RepoMan@@V?$TablePolicy@UFlavors@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3396`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180049f38`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18004a2c4`
- `0x18004c104`
- `0x18004ee40`
- `0x18004eea4`
- `0x180050ec8`
- `0x1800532a4`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004c478`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004c6f6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004c478`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004c6f6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004c471`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004c6ef`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004c471`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004c6ef`

## string_xrefs

- `0x18004c4c2`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18004c48b`: `CREATE TABLE IF NOT EXISTS `
- `0x18004cda8`: `CREATE TABLE IF NOT EXISTS `
- `0x18004c58f`: ` AS incoming, `
- `0x18004c9c4`: `REPLACE INTO `
- `0x18004cc0c`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v7; // rax
  _BYTE *v8; // rdx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  int v13; // ecx
  __int64 v14; // rax
  _BYTE *v15; // rdx
  __int64 v16; // rax
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
  _BYTE *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  _BYTE *v53; // rdx
  __int64 v54; // rax
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
  _BYTE v105[14]; // [rsp+158h] [rbp+50h] BYREF
  __int16 v106; // [rsp+166h] [rbp+5Eh]
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v110);
    v106 = 0;
    v107 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v105, "Flavor", 6);
    *(_QWORD *)&v105[6] = (unsigned __int8)aFlavors[6];
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v8 = *(_BYTE **)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v107.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v13,
      16,
      (unsigned int)v110,
      (unsigned int)v105,
      (__int64)v101);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" LEFT OUTER JOIN ");
    v15 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v15 = *(_BYTE **)v105;
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
        v20 = v105;
        if ( v107.m128i_i64[1] > 0xFuLL )
          v20 = *(_BYTE **)v105;
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
    v28 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v28 = *(_BYTE **)v105;
    v29 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v27, (__int64)v28, v107.m128i_u64[0]);
    v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)".");
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"flavor_id";
    Block[1] = (void *)(unsigned __int8)aFlavorId[8];
    BYTE1(Block[1]) = 0;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 9u);
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v116);
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
    v108[0] = *(void **)"flavor_id";
    v108[1] = (void *)(unsigned __int8)aFlavorId[8];
    BYTE1(v108[1]) = 0;
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v108, 9u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v45 = *(_BYTE **)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v107.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"flavor_id";
    Block[1] = (void *)(unsigned __int8)aFlavorId[8];
    BYTE1(Block[1]) = 0;
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 9u);
    v49 = std::operator<<<std::char_traits<char>>(v48, (__int64)" AS client FROM ");
    v50 = v110;
    if ( v111.m128i_i64[1] > 0xFuLL )
      v50 = (_QWORD *)v110[0];
    v51 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v49, (__int64)v50, v111.m128i_u64[0]);
    v52 = std::operator<<<std::char_traits<char>>(v51, (__int64)" INNER JOIN ");
    v53 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v53 = *(_BYTE **)v105;
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
        v61 = v105;
        if ( v107.m128i_i64[1] > 0xFuLL )
          v61 = *(_BYTE **)v105;
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
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>::BuildText(
      v68,
      0,
      144,
      (unsigned int)v110,
      (__int64)v105,
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
    std::string::_Tidy_deallocate(v105);
    *(_QWORD *)v105 = 19937;
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
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v108);
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
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Flavors");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v108 = 0;
        v109 = 0;
        std::string::_Construct<1,char const *>(v108, "Flavors", 7u);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Flavors");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Flavors");
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
    std::string::_Construct<1,char const *>(v108, "Flavors", 7u);
    v96(a1, v108);
    if ( v109.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v108, v108[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v108 = 0;
  v109 = 0;
  std::string::_Construct<1,char const *>(v108, "Flavors", 7u);
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
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
0x18004c104  mov     rax, rsp
0x18004c107  mov     [rax+18h], rbx
0x18004c10b  mov     [rax+20h], rsi
0x18004c10f  push    rbp
0x18004c110  push    r12
0x18004c112  push    r13
0x18004c114  push    r14
0x18004c116  push    r15
0x18004c118  lea     rbp, [rax-178h]
0x18004c11f  sub     rsp, 250h
0x18004c126  movaps  xmmword ptr [rax-38h], xmm6
0x18004c12a  mov     rax, cs:__security_cookie
0x18004c131  xor     rax, rsp
0x18004c134  mov     [rbp+170h+var_38], rax
0x18004c13b  movzx   esi, r9w
0x18004c13f  mov     r14, rdx
0x18004c142  mov     r15, rcx
0x18004c145  mov     [rsp+270h+var_238], rdx
0x18004c14a  xor     r13d, r13d
0x18004c14d  mov     [rsp+270h+var_230], r13d
0x18004c152  lea     rcx, [rsp+270h+var_220]
0x18004c157  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18004c15c  nop
0x18004c15d  mov     eax, 800h
0x18004c162  cmp     ax, si
0x18004c165  jnz     loc_18004C907
0x18004c16b  xorps   xmm0, xmm0
0x18004c16e  movups  [rbp+170h+var_60], xmm0
0x18004c175  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18004c17d  movdqu  [rbp+170h+var_50], xmm1
0x18004c185  mov     byte ptr [rbp+170h+var_60], r13b
0x18004c18c  mov     [rbp+170h+var_40], r13
0x18004c193  lea     rcx, [rbp+170h+var_E0]
0x18004c19a  call    ?IndexName@?$Table@VFlavors@Tables@Meta@RepoMan@@V?$TablePolicy@UFlavors@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x18004c19f  nop
0x18004c1a0  xorps   xmm0, xmm0
0x18004c1a3  movups  [rbp+170h+var_120], xmm0
0x18004c1a7  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x18004c1af  movdqu  [rbp+170h+var_110], xmm1
0x18004c1b4  mov     rax, qword ptr cs:aFlavors; "Flavors"
0x18004c1bb  mov     dword ptr [rbp+170h+var_120], eax
0x18004c1be  movzx   eax, word ptr cs:aFlavors+4; "ors"
0x18004c1c5  mov     word ptr [rbp+170h+var_120+4], ax
0x18004c1c9  mov     al, byte ptr cs:aFlavors+6; "s"
0x18004c1cf  mov     byte ptr [rbp+170h+var_120+6], al
0x18004c1d2  mov     byte ptr [rbp+170h+var_120+7], r13b
0x18004c1d6  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18004c1dd  lea     rcx, [rsp+270h+var_210]
0x18004c1e2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c1e7  lea     rdx, [rbp+170h+var_120]
0x18004c1eb  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c1f0  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c1f5  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c1f9  mov     rcx, rax
0x18004c1fc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c201  lea     rdx, aSelectNull; " SELECT NULL"
0x18004c208  mov     rcx, rax
0x18004c20b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c210  lea     r9, [r15+1C0h]
0x18004c217  mov     edx, 802h
0x18004c21c  lea     rax, [rsp+270h+var_220]
0x18004c221  mov     [rsp+270h+Reserved], rax
0x18004c226  lea     r8, [rbp+170h+var_E0]
0x18004c22d  call    ?BuildText@?$RowType@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004c232  lea     rdx, aFrom_0; " FROM "
0x18004c239  lea     rcx, [rsp+270h+var_210]
0x18004c23e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c243  lea     rdx, [rbp+170h+var_E0]
0x18004c24a  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004c252  cmova   rdx, [rbp+170h+var_E0]
0x18004c25a  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004c261  mov     rcx, rax
0x18004c264  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c269  lea     edx, [r13+10h]
0x18004c26d  lea     rax, [rsp+270h+var_220]
0x18004c272  mov     [rsp+270h+Reserved], rax
0x18004c277  lea     r9, [rbp+170h+var_120]
0x18004c27b  lea     r8, [rbp+170h+var_E0]
0x18004c282  call    ?BuildText@?$RowType@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004c287  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18004c28e  lea     rcx, [rsp+270h+var_210]
0x18004c293  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c298  lea     rdx, [rbp+170h+var_120]
0x18004c29c  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c2a1  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c2a6  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c2aa  mov     rcx, rax
0x18004c2ad  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c2b2  lea     rdx, aOn; " ON ("
0x18004c2b9  mov     rcx, rax
0x18004c2bc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c2c1  mov     eax, r13d
0x18004c2c4  mov     [rsp+270h+var_240], rax
0x18004c2c9  mov     rcx, [r15+1E8h]
0x18004c2d0  mov     [rsp+270h+var_238], rcx
0x18004c2d5  mov     rsi, [r15+1E0h]
0x18004c2dc  lea     r12d, [r13+1]
0x18004c2e0  lea     r13d, [rax+40h]
0x18004c2e4  cmp     rsi, rcx
0x18004c2e7  jz      loc_18004C391
0x18004c2ed  lea     rbx, [rsi+38h]
0x18004c2f1  test    rax, rax
0x18004c2f4  jz      short loc_18004C307
0x18004c2f6  lea     rdx, aAnd_1; " AND "
0x18004c2fd  lea     rcx, [rsp+270h+var_210]
0x18004c302  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c307  lea     rdx, [rbp+170h+var_120]
0x18004c30b  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c310  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c315  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c319  lea     rcx, [rsp+270h+var_210]
0x18004c31e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c323  lea     rdx, asc_1801D0CE8; "."
0x18004c32a  mov     rcx, rax
0x18004c32d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c332  mov     rdx, rsi
0x18004c335  cmp     qword ptr [rbx-20h], 0Fh
0x18004c33a  jbe     short loc_18004C33F
0x18004c33c  mov     rdx, [rsi]
0x18004c33f  mov     r8, [rbx-28h]
0x18004c343  mov     rcx, rax
0x18004c346  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c34b  lea     rdx, asc_1801D5B8C; " = "
0x18004c352  mov     rcx, rax
0x18004c355  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c35a  lea     rdx, [rbx-18h]
0x18004c35e  cmp     qword ptr [rbx], 0Fh
0x18004c362  jbe     short loc_18004C367
0x18004c364  mov     rdx, [rdx]
0x18004c367  mov     r8, [rbx-8]
0x18004c36b  mov     rcx, rax
0x18004c36e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c373  mov     rax, [rsp+270h+var_240]
0x18004c378  add     rax, r12
0x18004c37b  mov     [rsp+270h+var_240], rax
0x18004c380  add     rsi, r13
0x18004c383  add     rbx, r13
0x18004c386  cmp     rsi, [rsp+270h+var_238]
0x18004c38b  jnz     loc_18004C2F1
0x18004c391  lea     rdx, aWhere; ") WHERE "
0x18004c398  lea     rcx, [rsp+270h+var_210]
0x18004c39d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c3a2  lea     rdx, [rbp+170h+var_120]
0x18004c3a6  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c3ab  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c3b0  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c3b4  mov     rcx, rax
0x18004c3b7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c3bc  lea     rdx, asc_1801D0CE8; "."
0x18004c3c3  mov     rcx, rax
0x18004c3c6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c3cb  mov     rcx, rax
0x18004c3ce  xorps   xmm0, xmm0
0x18004c3d1  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004c3d8  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18004c3e0  movdqu  [rbp+170h+var_B0], xmm1
0x18004c3e8  movsd   xmm0, qword ptr cs:aFlavorId; "flavor_id"
0x18004c3f0  movsd   [rbp+170h+Block], xmm0
0x18004c3f8  mov     al, byte ptr cs:aFlavorId+8; "d"
0x18004c3fe  mov     byte ptr [rbp+170h+Block+8], al
0x18004c404  xor     esi, esi
0x18004c406  mov     byte ptr [rbp+170h+Block+9], sil
0x18004c40d  lea     r8d, [rsi+9]
0x18004c411  lea     rdx, [rbp+170h+Block]
0x18004c418  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c41d  lea     rdx, aIsNull; " IS NULL;"
0x18004c424  mov     rcx, rax
0x18004c427  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c42c  nop
0x18004c42d  mov     ebx, 1000h
0x18004c432  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18004c439  cmp     rax, 0Fh
0x18004c43d  jbe     short loc_18004C47E
0x18004c43f  mov     rcx, [rbp+170h+Block]; Block
0x18004c446  mov     rdx, rcx
0x18004c449  inc     rax
0x18004c44c  cmp     rax, rbx
0x18004c44f  jb      short loc_18004C478
0x18004c451  mov     rcx, [rcx-8]
0x18004c455  sub     rdx, rcx
0x18004c458  lea     rax, [rdx-8]
0x18004c45c  cmp     rax, 1Fh
0x18004c460  jbe     short loc_18004C478
0x18004c462  mov     [rsp+270h+Reserved], rsi; Reserved
0x18004c467  xor     r9d, r9d; LineNo
0x18004c46a  xor     r8d, r8d; FileName
0x18004c46d  xor     edx, edx; FunctionName
0x18004c46f  xor     ecx, ecx; Expression
0x18004c471  call    cs:__imp__invoke_watson
0x18004c478  call    cs:__imp_free
0x18004c47e  lea     rcx, [rbp+170h+var_80]
0x18004c485  call    ?MapName@?$Table@VFlavors@Tables@Meta@RepoMan@@V?$TablePolicy@UFlavors@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UFlavor_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UFlavors@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Flavors,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Flavors,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Flavor_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Flavors,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x18004c48a  nop
0x18004c48b  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18004c492  lea     rcx, [rsp+270h+var_210]
0x18004c497  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c49c  lea     rdx, [rbp+170h+var_80]
0x18004c4a3  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004c4ab  cmova   rdx, [rbp+170h+var_80]
0x18004c4b3  mov     r8, qword ptr [rbp+170h+var_70]
0x18004c4ba  mov     rcx, rax
0x18004c4bd  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c4c2  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x18004c4c9  mov     rcx, rax
0x18004c4cc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c4d1  lea     rdx, aInsertInto; "INSERT INTO "
0x18004c4d8  lea     rcx, [rsp+270h+var_210]
0x18004c4dd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c4e2  lea     rdx, [rbp+170h+var_80]
0x18004c4e9  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004c4f1  cmova   rdx, [rbp+170h+var_80]
0x18004c4f9  mov     r8, qword ptr [rbp+170h+var_70]
0x18004c500  mov     rcx, rax
0x18004c503  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c508  lea     rdx, aSelect; " SELECT "
0x18004c50f  mov     rcx, rax
0x18004c512  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c517  lea     rdx, [rbp+170h+var_E0]
0x18004c51e  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004c526  cmova   rdx, [rbp+170h+var_E0]
0x18004c52e  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004c535  mov     rcx, rax
0x18004c538  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c53d  lea     rdx, asc_1801D0CE8; "."
0x18004c544  mov     rcx, rax
0x18004c547  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c54c  mov     rcx, rax
0x18004c54f  xorps   xmm0, xmm0
0x18004c552  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18004c556  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18004c55e  movdqu  [rbp+170h+var_F0], xmm1
0x18004c566  movsd   xmm0, qword ptr cs:aFlavorId; "flavor_id"
0x18004c56e  movsd   [rbp+170h+var_100], xmm0
0x18004c573  mov     al, byte ptr cs:aFlavorId+8; "d"
0x18004c579  mov     byte ptr [rbp+170h+var_100+8], al
0x18004c57c  mov     byte ptr [rbp+170h+var_100+9], sil
0x18004c580  mov     r8d, 9
0x18004c586  lea     rdx, [rbp+170h+var_100]
0x18004c58a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c58f  lea     rdx, aAsIncoming; " AS incoming, "
0x18004c596  mov     rcx, rax
0x18004c599  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c59e  lea     rdx, [rbp+170h+var_120]
0x18004c5a2  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c5a7  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c5ac  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c5b0  mov     rcx, rax
0x18004c5b3  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c5b8  lea     rdx, asc_1801D0CE8; "."
0x18004c5bf  mov     rcx, rax
0x18004c5c2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c5c7  mov     rcx, rax
0x18004c5ca  xorps   xmm0, xmm0
0x18004c5cd  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004c5d4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x18004c5dc  movdqu  [rbp+170h+var_B0], xmm1
0x18004c5e4  movsd   xmm0, qword ptr cs:aFlavorId; "flavor_id"
0x18004c5ec  movsd   [rbp+170h+Block], xmm0
0x18004c5f4  mov     al, byte ptr cs:aFlavorId+8; "d"
0x18004c5fa  mov     byte ptr [rbp+170h+Block+8], al
0x18004c600  mov     byte ptr [rbp+170h+Block+9], sil
0x18004c607  mov     r8d, 9
0x18004c60d  lea     rdx, [rbp+170h+Block]
0x18004c614  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c619  lea     rdx, aAsClientFrom; " AS client FROM "
0x18004c620  mov     rcx, rax
0x18004c623  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c628  lea     rdx, [rbp+170h+var_E0]
0x18004c62f  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004c637  cmova   rdx, [rbp+170h+var_E0]
0x18004c63f  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004c646  mov     rcx, rax
0x18004c649  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c64e  lea     rdx, aInnerJoin; " INNER JOIN "
0x18004c655  mov     rcx, rax
0x18004c658  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c65d  lea     rdx, [rbp+170h+var_120]
0x18004c661  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004c666  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004c66b  mov     r8, qword ptr [rbp+170h+var_110]
0x18004c66f  mov     rcx, rax
0x18004c672  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004c677  lea     rdx, aOn; " ON ("
0x18004c67e  mov     rcx, rax
0x18004c681  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004c686  nop
0x18004c687  lea     rcx, [rbp+170h+Block]
0x18004c68e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c693  mov     esi, 4DE1h
0x18004c698  mov     [rbp+170h+Block], rsi
0x18004c69f  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18004c6a7  movdqu  [rbp+170h+var_B0], xmm6
0x18004c6af  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x18004c6b6  cmp     rax, 0Fh
0x18004c6ba  jbe     short loc_18004C6FC
0x18004c6bc  mov     rcx, [rbp+170h+var_100]; Block
0x18004c6c0  mov     rdx, rcx
0x18004c6c3  inc     rax
0x18004c6c6  cmp     rax, rbx
0x18004c6c9  jb      short loc_18004C6F6
  ... truncated ...
```
