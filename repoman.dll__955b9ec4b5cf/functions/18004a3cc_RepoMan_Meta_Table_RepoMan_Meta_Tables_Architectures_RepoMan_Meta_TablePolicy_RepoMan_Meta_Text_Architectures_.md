# RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x18004a3cc`
- end: `0x18004b12f`
- name: `?CreateText@?$Table@VArchitectures@Tables@Meta@RepoMan@@V?$TablePolicy@UArchitectures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3427`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800478c0`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x180047c4c`
- `0x18004a3cc`
- `0x18004ce48`
- `0x18004ceac`
- `0x180050ec8`
- `0x180051050`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004a74c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004a9dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004a74c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004a9dd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004a745`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004a9d6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004a745`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004a9d6`

## string_xrefs

- `0x18004a796`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18004a75f`: `CREATE TABLE IF NOT EXISTS `
- `0x18004b08f`: `CREATE TABLE IF NOT EXISTS `
- `0x18004a86b`: ` AS incoming, `
- `0x18004acab`: `REPLACE INTO `
- `0x18004aef3`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
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
  _BYTE v105[12]; // [rsp+158h] [rbp+50h] BYREF
  int v106; // [rsp+164h] [rbp+5Ch]
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v110);
    v107 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v105, "Architecture", sizeof(v105));
    v106 = (unsigned __int8)aArchitectures[12];
    v7 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)" INSERT OR IGNORE INTO ");
    v8 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v8 = *(_BYTE **)v105;
    v9 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v7, (__int64)v8, v107.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v9, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    HIWORD(Block[1]) = 0;
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(Block, "arch_i", 6);
    *(void **)((char *)Block + 6) = (void *)(unsigned __int8)aArchId[6];
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, (__int64)Block, 7u);
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
    RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v116);
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
    HIWORD(v108[1]) = 0;
    v109 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v108, "arch_i", 6);
    *(void **)((char *)v108 + 6) = (void *)(unsigned __int8)aArchId[6];
    v43 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v42, (__int64)v108, 7u);
    v44 = std::operator<<<std::char_traits<char>>(v43, (__int64)" AS incoming, ");
    v45 = v105;
    if ( v107.m128i_i64[1] > 0xFuLL )
      v45 = *(_BYTE **)v105;
    v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, (__int64)v45, v107.m128i_u64[0]);
    v47 = std::operator<<<std::char_traits<char>>(v46, (__int64)".");
    HIWORD(Block[1]) = 0;
    v113 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(Block, "arch_i", 6);
    *(void **)((char *)Block + 6) = (void *)(unsigned __int8)aArchId[6];
    v48 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v47, (__int64)Block, 7u);
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
    RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>::BuildText(
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
    v74 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v108);
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
        v90 = std::operator<<<std::char_traits<char>>(v89, (__int64)"Architectures");
        std::operator<<<std::char_traits<char>>(v90, (__int64)" SET ");
        *(_OWORD *)v108 = 0;
        v109 = 0;
        std::string::_Construct<1,char const *>(v108, "Architectures", 0xDu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
        v93 = std::operator<<<std::char_traits<char>>(v92, (__int64)"Architectures");
        std::operator<<<std::char_traits<char>>(v93, (__int64)";");
        std::stringbuf::str(v103, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v104);
        v104[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v104);
        return a2;
      case 0x20u:
        v94 = std::operator<<<std::char_traits<char>>((__int64)v102, (__int64)"SELECT * FROM ");
        v95 = std::operator<<<std::char_traits<char>>(v94, (__int64)"Architectures");
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
    std::string::_Construct<1,char const *>(v108, "Architectures", 0xDu);
    v96(a1, v108);
    if ( v109.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v108, v108[0]);
  }
  else if ( a4 == 1024 )
  {
    v78 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v108 = 0;
  v109 = 0;
  std::string::_Construct<1,char const *>(v108, "Architectures", 0xDu);
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
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
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
0x18004a3cc  mov     rax, rsp
0x18004a3cf  mov     [rax+18h], rbx
0x18004a3d3  mov     [rax+20h], rsi
0x18004a3d7  push    rbp
0x18004a3d8  push    r12
0x18004a3da  push    r13
0x18004a3dc  push    r14
0x18004a3de  push    r15
0x18004a3e0  lea     rbp, [rax-178h]
0x18004a3e7  sub     rsp, 250h
0x18004a3ee  movaps  xmmword ptr [rax-38h], xmm6
0x18004a3f2  mov     rax, cs:__security_cookie
0x18004a3f9  xor     rax, rsp
0x18004a3fc  mov     [rbp+170h+var_38], rax
0x18004a403  movzx   esi, r9w
0x18004a407  mov     r14, rdx
0x18004a40a  mov     r15, rcx
0x18004a40d  mov     [rsp+270h+var_238], rdx
0x18004a412  xor     r13d, r13d
0x18004a415  mov     [rsp+270h+var_230], r13d
0x18004a41a  lea     rcx, [rsp+270h+var_220]
0x18004a41f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18004a424  nop
0x18004a425  mov     eax, 800h
0x18004a42a  cmp     ax, si
0x18004a42d  jnz     loc_18004ABEE
0x18004a433  xorps   xmm0, xmm0
0x18004a436  movups  [rbp+170h+var_60], xmm0
0x18004a43d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18004a445  movdqu  [rbp+170h+var_50], xmm1
0x18004a44d  mov     byte ptr [rbp+170h+var_60], r13b
0x18004a454  mov     [rbp+170h+var_40], r13
0x18004a45b  lea     rcx, [rbp+170h+var_E0]
0x18004a462  call    ?IndexName@?$Table@VArchitectures@Tables@Meta@RepoMan@@V?$TablePolicy@UArchitectures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x18004a467  nop
0x18004a468  xorps   xmm0, xmm0
0x18004a46b  movups  [rbp+170h+var_120], xmm0
0x18004a46f  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000d
0x18004a477  movdqu  [rbp+170h+var_110], xmm1
0x18004a47c  movsd   xmm0, qword ptr cs:aArchitectures; "Architectures"
0x18004a484  movsd   qword ptr [rbp+170h+var_120], xmm0
0x18004a489  mov     eax, dword ptr cs:aArchitectures+8; "tures"
0x18004a48f  mov     dword ptr [rbp+170h+var_120+8], eax
0x18004a492  mov     al, byte ptr cs:aArchitectures+0Ch; "s"
0x18004a498  mov     byte ptr [rbp+170h+var_120+0Ch], al
0x18004a49b  mov     byte ptr [rbp+170h+var_120+0Dh], r13b
0x18004a49f  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x18004a4a6  lea     rcx, [rsp+270h+var_210]
0x18004a4ab  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a4b0  lea     rdx, [rbp+170h+var_120]
0x18004a4b4  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a4b9  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a4be  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a4c2  mov     rcx, rax
0x18004a4c5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a4ca  lea     rdx, aSelectNull; " SELECT NULL"
0x18004a4d1  mov     rcx, rax
0x18004a4d4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a4d9  lea     r9, [r15+1C0h]
0x18004a4e0  mov     edx, 802h
0x18004a4e5  lea     rax, [rsp+270h+var_220]
0x18004a4ea  mov     [rsp+270h+Reserved], rax
0x18004a4ef  lea     r8, [rbp+170h+var_E0]
0x18004a4f6  call    ?BuildText@?$RowType@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004a4fb  lea     rdx, aFrom_0; " FROM "
0x18004a502  lea     rcx, [rsp+270h+var_210]
0x18004a507  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a50c  lea     rdx, [rbp+170h+var_E0]
0x18004a513  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004a51b  cmova   rdx, [rbp+170h+var_E0]
0x18004a523  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004a52a  mov     rcx, rax
0x18004a52d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a532  lea     edx, [r13+10h]
0x18004a536  lea     rax, [rsp+270h+var_220]
0x18004a53b  mov     [rsp+270h+Reserved], rax
0x18004a540  lea     r9, [rbp+170h+var_120]
0x18004a544  lea     r8, [rbp+170h+var_E0]
0x18004a54b  call    ?BuildText@?$RowType@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x18004a550  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x18004a557  lea     rcx, [rsp+270h+var_210]
0x18004a55c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a561  lea     rdx, [rbp+170h+var_120]
0x18004a565  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a56a  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a56f  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a573  mov     rcx, rax
0x18004a576  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a57b  lea     rdx, aOn; " ON ("
0x18004a582  mov     rcx, rax
0x18004a585  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a58a  mov     eax, r13d
0x18004a58d  mov     [rsp+270h+var_240], rax
0x18004a592  mov     rcx, [r15+1E8h]
0x18004a599  mov     [rsp+270h+var_238], rcx
0x18004a59e  mov     rsi, [r15+1E0h]
0x18004a5a5  lea     r12d, [r13+1]
0x18004a5a9  lea     r13d, [rax+40h]
0x18004a5ad  cmp     rsi, rcx
0x18004a5b0  jz      loc_18004A65A
0x18004a5b6  lea     rbx, [rsi+38h]
0x18004a5ba  test    rax, rax
0x18004a5bd  jz      short loc_18004A5D0
0x18004a5bf  lea     rdx, aAnd_1; " AND "
0x18004a5c6  lea     rcx, [rsp+270h+var_210]
0x18004a5cb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a5d0  lea     rdx, [rbp+170h+var_120]
0x18004a5d4  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a5d9  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a5de  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a5e2  lea     rcx, [rsp+270h+var_210]
0x18004a5e7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a5ec  lea     rdx, asc_1801D0CE8; "."
0x18004a5f3  mov     rcx, rax
0x18004a5f6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a5fb  mov     rdx, rsi
0x18004a5fe  cmp     qword ptr [rbx-20h], 0Fh
0x18004a603  jbe     short loc_18004A608
0x18004a605  mov     rdx, [rsi]
0x18004a608  mov     r8, [rbx-28h]
0x18004a60c  mov     rcx, rax
0x18004a60f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a614  lea     rdx, asc_1801D5B8C; " = "
0x18004a61b  mov     rcx, rax
0x18004a61e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a623  lea     rdx, [rbx-18h]
0x18004a627  cmp     qword ptr [rbx], 0Fh
0x18004a62b  jbe     short loc_18004A630
0x18004a62d  mov     rdx, [rdx]
0x18004a630  mov     r8, [rbx-8]
0x18004a634  mov     rcx, rax
0x18004a637  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a63c  mov     rax, [rsp+270h+var_240]
0x18004a641  add     rax, r12
0x18004a644  mov     [rsp+270h+var_240], rax
0x18004a649  add     rsi, r13
0x18004a64c  add     rbx, r13
0x18004a64f  cmp     rsi, [rsp+270h+var_238]
0x18004a654  jnz     loc_18004A5BA
0x18004a65a  lea     rdx, aWhere; ") WHERE "
0x18004a661  lea     rcx, [rsp+270h+var_210]
0x18004a666  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a66b  lea     rdx, [rbp+170h+var_120]
0x18004a66f  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a674  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a679  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a67d  mov     rcx, rax
0x18004a680  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a685  lea     rdx, asc_1801D0CE8; "."
0x18004a68c  mov     rcx, rax
0x18004a68f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a694  mov     rcx, rax
0x18004a697  xorps   xmm0, xmm0
0x18004a69a  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004a6a1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x18004a6a9  movdqu  [rbp+170h+var_B0], xmm1
0x18004a6b1  mov     rax, qword ptr cs:aArchId; "arch_id"
0x18004a6b8  mov     dword ptr [rbp+170h+Block], eax
0x18004a6be  movzx   eax, word ptr cs:aArchId+4; "_id"
0x18004a6c5  mov     word ptr [rbp+170h+Block+4], ax
0x18004a6cc  mov     al, byte ptr cs:aArchId+6; "d"
0x18004a6d2  mov     byte ptr [rbp+170h+Block+6], al
0x18004a6d8  xor     esi, esi
0x18004a6da  mov     byte ptr [rbp+170h+Block+7], sil
0x18004a6e1  lea     r8d, [rsi+7]
0x18004a6e5  lea     rdx, [rbp+170h+Block]
0x18004a6ec  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a6f1  lea     rdx, aIsNull; " IS NULL;"
0x18004a6f8  mov     rcx, rax
0x18004a6fb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a700  nop
0x18004a701  mov     ebx, 1000h
0x18004a706  mov     rax, qword ptr [rbp+170h+var_B0+8]
0x18004a70d  cmp     rax, 0Fh
0x18004a711  jbe     short loc_18004A752
0x18004a713  mov     rcx, [rbp+170h+Block]; Block
0x18004a71a  mov     rdx, rcx
0x18004a71d  inc     rax
0x18004a720  cmp     rax, rbx
0x18004a723  jb      short loc_18004A74C
0x18004a725  mov     rcx, [rcx-8]
0x18004a729  sub     rdx, rcx
0x18004a72c  lea     rax, [rdx-8]
0x18004a730  cmp     rax, 1Fh
0x18004a734  jbe     short loc_18004A74C
0x18004a736  mov     [rsp+270h+Reserved], rsi; Reserved
0x18004a73b  xor     r9d, r9d; LineNo
0x18004a73e  xor     r8d, r8d; FileName
0x18004a741  xor     edx, edx; FunctionName
0x18004a743  xor     ecx, ecx; Expression
0x18004a745  call    cs:__imp__invoke_watson
0x18004a74c  call    cs:__imp_free
0x18004a752  lea     rcx, [rbp+170h+var_80]
0x18004a759  call    ?MapName@?$Table@VArchitectures@Tables@Meta@RepoMan@@V?$TablePolicy@UArchitectures@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@UArch_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UArchitectures@234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::Architectures,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::Architectures,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Arch_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Architectures,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x18004a75e  nop
0x18004a75f  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x18004a766  lea     rcx, [rsp+270h+var_210]
0x18004a76b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a770  lea     rdx, [rbp+170h+var_80]
0x18004a777  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004a77f  cmova   rdx, [rbp+170h+var_80]
0x18004a787  mov     r8, qword ptr [rbp+170h+var_70]
0x18004a78e  mov     rcx, rax
0x18004a791  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a796  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x18004a79d  mov     rcx, rax
0x18004a7a0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a7a5  lea     rdx, aInsertInto; "INSERT INTO "
0x18004a7ac  lea     rcx, [rsp+270h+var_210]
0x18004a7b1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a7b6  lea     rdx, [rbp+170h+var_80]
0x18004a7bd  cmp     qword ptr [rbp+170h+var_70+8], 0Fh
0x18004a7c5  cmova   rdx, [rbp+170h+var_80]
0x18004a7cd  mov     r8, qword ptr [rbp+170h+var_70]
0x18004a7d4  mov     rcx, rax
0x18004a7d7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a7dc  lea     rdx, aSelect; " SELECT "
0x18004a7e3  mov     rcx, rax
0x18004a7e6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a7eb  lea     rdx, [rbp+170h+var_E0]
0x18004a7f2  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004a7fa  cmova   rdx, [rbp+170h+var_E0]
0x18004a802  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004a809  mov     rcx, rax
0x18004a80c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a811  lea     rdx, asc_1801D0CE8; "."
0x18004a818  mov     rcx, rax
0x18004a81b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a820  mov     rcx, rax
0x18004a823  xorps   xmm0, xmm0
0x18004a826  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18004a82a  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x18004a832  movdqu  [rbp+170h+var_F0], xmm1
0x18004a83a  mov     rax, qword ptr cs:aArchId; "arch_id"
0x18004a841  mov     dword ptr [rbp+170h+var_100], eax
0x18004a844  movzx   eax, word ptr cs:aArchId+4; "_id"
0x18004a84b  mov     word ptr [rbp+170h+var_100+4], ax
0x18004a84f  mov     al, byte ptr cs:aArchId+6; "d"
0x18004a855  mov     byte ptr [rbp+170h+var_100+6], al
0x18004a858  mov     byte ptr [rbp+170h+var_100+7], sil
0x18004a85c  mov     r8d, 7
0x18004a862  lea     rdx, [rbp+170h+var_100]
0x18004a866  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a86b  lea     rdx, aAsIncoming; " AS incoming, "
0x18004a872  mov     rcx, rax
0x18004a875  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a87a  lea     rdx, [rbp+170h+var_120]
0x18004a87e  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a883  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a888  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a88c  mov     rcx, rax
0x18004a88f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a894  lea     rdx, asc_1801D0CE8; "."
0x18004a89b  mov     rcx, rax
0x18004a89e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a8a3  mov     rcx, rax
0x18004a8a6  xorps   xmm0, xmm0
0x18004a8a9  movups  xmmword ptr [rbp+170h+Block], xmm0
0x18004a8b0  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000007
0x18004a8b8  movdqu  [rbp+170h+var_B0], xmm1
0x18004a8c0  mov     rax, qword ptr cs:aArchId; "arch_id"
0x18004a8c7  mov     dword ptr [rbp+170h+Block], eax
0x18004a8cd  movzx   eax, word ptr cs:aArchId+4; "_id"
0x18004a8d4  mov     word ptr [rbp+170h+Block+4], ax
0x18004a8db  mov     al, byte ptr cs:aArchId+6; "d"
0x18004a8e1  mov     byte ptr [rbp+170h+Block+6], al
0x18004a8e7  mov     byte ptr [rbp+170h+Block+7], sil
0x18004a8ee  mov     r8d, 7
0x18004a8f4  lea     rdx, [rbp+170h+Block]
0x18004a8fb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a900  lea     rdx, aAsClientFrom; " AS client FROM "
0x18004a907  mov     rcx, rax
0x18004a90a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a90f  lea     rdx, [rbp+170h+var_E0]
0x18004a916  cmp     qword ptr [rbp+170h+var_D0+8], 0Fh
0x18004a91e  cmova   rdx, [rbp+170h+var_E0]
0x18004a926  mov     r8, qword ptr [rbp+170h+var_D0]
0x18004a92d  mov     rcx, rax
0x18004a930  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a935  lea     rdx, aInnerJoin; " INNER JOIN "
0x18004a93c  mov     rcx, rax
0x18004a93f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a944  lea     rdx, [rbp+170h+var_120]
0x18004a948  cmp     qword ptr [rbp+170h+var_110+8], 0Fh
0x18004a94d  cmova   rdx, qword ptr [rbp+170h+var_120]
0x18004a952  mov     r8, qword ptr [rbp+170h+var_110]
0x18004a956  mov     rcx, rax
0x18004a959  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004a95e  lea     rdx, aOn; " ON ("
0x18004a965  mov     rcx, rax
0x18004a968  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004a96d  nop
0x18004a96e  lea     rcx, [rbp+170h+Block]
0x18004a975  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004a97a  mov     esi, 4DE1h
0x18004a97f  mov     [rbp+170h+Block], rsi
0x18004a986  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x18004a98e  movdqu  [rbp+170h+var_B0], xmm6
0x18004a996  mov     rax, qword ptr [rbp+170h+var_F0+8]
0x18004a99d  cmp     rax, 0Fh
  ... truncated ...
```
