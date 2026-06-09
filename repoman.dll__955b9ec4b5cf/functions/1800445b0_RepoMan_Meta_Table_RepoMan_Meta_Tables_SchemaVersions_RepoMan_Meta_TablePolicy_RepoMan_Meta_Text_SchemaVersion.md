# RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::CreateText(RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &,CommandFlags)

- ea: `0x1800445b0`
- end: `0x1800452e3`
- name: `?CreateText@?$Table@VSchemaVersions@Tables@Meta@RepoMan@@V?$TablePolicy@USchemaVersions@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@34@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$RowType@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@23@W4CommandFlags@@@Z`
- size: `3379`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f538`

## callees

- `0x180008574`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x180027e50`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18003a240`
- `0x18003f8d0`
- `0x1800445b0`
- `0x180048a80`
- `0x180048c2c`
- `0x180198f88`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180044938`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180044bab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180044938`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180044bab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180044931`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180044ba4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180044931`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180044ba4`

## string_xrefs

- `0x180044982`: `(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));`
- `0x18004494b`: `CREATE TABLE IF NOT EXISTS `
- `0x18004523d`: `CREATE TABLE IF NOT EXISTS `
- `0x180044a4b`: ` AS incoming, `
- `0x180044e53`: `REPLACE INTO `
- `0x18004509e`: `UPDATE `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::CreateText(
        _QWORD *a1,
        __int64 a2,
        int a3,
        unsigned __int16 a4)
{
  int v5; // r13d
  __int64 v8; // r12
  __int64 v9; // rax
  _BYTE *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rax
  _BYTE *v15; // rdx
  __int64 v16; // rax
  __int64 *v17; // rsi
  _QWORD *v18; // rbx
  _BYTE *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rdx
  __int64 v26; // rax
  _BYTE *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  void *v31; // rcx
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
  __m128i v54; // xmm6
  void *v55; // rcx
  __int64 v56; // rax
  __int64 *v57; // rbx
  _QWORD *v58; // rsi
  __int64 *v59; // r15
  _BYTE *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rax
  _QWORD *v66; // rdx
  __int64 v67; // rax
  _QWORD *v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rbx
  _QWORD *v71; // rax
  unsigned __int64 v72; // r8
  __int64 v73; // rax
  void **v74; // rax
  char v75; // bl
  __m128i v76; // xmm6
  __int128 *v77; // rdx
  __int64 v78; // rax
  int v79; // ebx
  _QWORD *v80; // r15
  __int64 v81; // rax
  unsigned __int64 v82; // r8
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  void (__fastcall *v90)(_QWORD *, void **); // rbx
  __int64 *v91; // [rsp+38h] [rbp-D0h]
  __int64 v92; // [rsp+38h] [rbp-D0h]
  __int64 v94; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v95[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v96[128]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v97[13]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v98[12]; // [rsp+158h] [rbp+50h] BYREF
  int v99; // [rsp+164h] [rbp+5Ch]
  __m128i v100; // [rsp+168h] [rbp+60h]
  void *v101[2]; // [rsp+178h] [rbp+70h] BYREF
  __m128i v102; // [rsp+188h] [rbp+80h]
  _QWORD v103[2]; // [rsp+198h] [rbp+90h] BYREF
  __m128i v104; // [rsp+1A8h] [rbp+A0h]
  void *Block[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __m128i v106; // [rsp+1C8h] [rbp+C0h]
  __int128 v107; // [rsp+1D8h] [rbp+D0h] BYREF
  __m128i v108; // [rsp+1E8h] [rbp+E0h]
  _QWORD v109[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __m128i v110; // [rsp+208h] [rbp+100h]
  __int128 v111; // [rsp+218h] [rbp+110h] BYREF
  __m128i si128; // [rsp+228h] [rbp+120h]
  __int128 v113; // [rsp+238h] [rbp+130h]

  v5 = a3;
  v8 = 0;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v94);
  if ( a4 == 2048 )
  {
    v111 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v111) = 0;
    v113 = 0u;
    RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(v103);
    v100 = _mm_load_si128((const __m128i *)&_xmm);
    qmemcpy(v98, "SchemaVersio", sizeof(v98));
    v99 = *(unsigned __int16 *)"ns";
    v9 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" INSERT OR IGNORE INTO ");
    v10 = v98;
    if ( v100.m128i_i64[1] > 0xFuLL )
      v10 = *(_BYTE **)v98;
    v11 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v9, (__int64)v10, v100.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v11, (__int64)" SELECT NULL");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      (unsigned int)&v111,
      2050,
      (unsigned int)v103,
      (_DWORD)a1 + 448,
      (__int64)&v94);
    v12 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" FROM ");
    v13 = v103;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v13 = (_QWORD *)v103[0];
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, (__int64)v13, v104.m128i_u64[0]);
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      (unsigned int)&v111,
      16,
      (unsigned int)v103,
      (unsigned int)v98,
      (__int64)&v94);
    v14 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" LEFT OUTER JOIN ");
    v15 = v98;
    if ( v100.m128i_i64[1] > 0xFuLL )
      v15 = *(_BYTE **)v98;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)v15, v100.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v16, (__int64)" ON (");
    v91 = (__int64 *)a1[61];
    v17 = (__int64 *)a1[60];
    if ( v17 != v91 )
    {
      v18 = v17 + 7;
      do
      {
        if ( v8 )
          std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" AND ");
        v19 = v98;
        if ( v100.m128i_i64[1] > 0xFuLL )
          v19 = *(_BYTE **)v98;
        v20 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v95,
                (__int64)v19,
                v100.m128i_u64[0]);
        v21 = std::operator<<<std::char_traits<char>>(v20, (__int64)".");
        v22 = (__int64)v17;
        if ( *(v18 - 4) > 0xFu )
          v22 = *v17;
        v23 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v21, v22, *(v18 - 5));
        v24 = std::operator<<<std::char_traits<char>>(v23, (__int64)" = ");
        v25 = v18 - 3;
        if ( *v18 > 0xFu )
          v25 = (_QWORD *)*v25;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v24, (__int64)v25, *(v18 - 1));
        ++v8;
        v17 += 8;
        v18 += 8;
      }
      while ( v17 != v91 );
    }
    v26 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)") WHERE ");
    v27 = v98;
    if ( v100.m128i_i64[1] > 0xFuLL )
      v27 = *(_BYTE **)v98;
    v28 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v26, (__int64)v27, v100.m128i_u64[0]);
    v29 = std::operator<<<std::char_traits<char>>(v28, (__int64)".");
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"schema_id";
    Block[1] = (void *)(unsigned __int8)aSchemaId[8];
    BYTE1(Block[1]) = 0;
    v30 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v29, (__int64)Block, 9u);
    std::operator<<<std::char_traits<char>>(v30, (__int64)" IS NULL;");
    if ( v106.m128i_i64[1] > 0xFuLL )
    {
      v31 = Block[0];
      if ( (unsigned __int64)(v106.m128i_i64[1] + 1) >= 0x1000 )
      {
        v31 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v31 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v31);
    }
    RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v109);
    v32 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"CREATE TABLE IF NOT EXISTS ");
    v33 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v33 = (_QWORD *)v109[0];
    v34 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v32, (__int64)v33, v110.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(
      v34,
      (__int64)"(incoming INTEGER PRIMARY KEY, client INTEGER NOT NULL, UNIQUE (incoming, client));");
    v35 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"INSERT INTO ");
    v36 = v109;
    if ( v110.m128i_i64[1] > 0xFuLL )
      v36 = (_QWORD *)v109[0];
    v37 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v35, (__int64)v36, v110.m128i_u64[0]);
    v38 = std::operator<<<std::char_traits<char>>(v37, (__int64)" SELECT ");
    v39 = v103;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v39 = (_QWORD *)v103[0];
    v40 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v38, (__int64)v39, v104.m128i_u64[0]);
    v41 = std::operator<<<std::char_traits<char>>(v40, (__int64)".");
    v102 = _mm_load_si128((const __m128i *)&_xmm);
    v101[0] = *(void **)"schema_id";
    v101[1] = (void *)(unsigned __int8)aSchemaId[8];
    BYTE1(v101[1]) = 0;
    v42 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v41, (__int64)v101, 9u);
    v43 = std::operator<<<std::char_traits<char>>(v42, (__int64)" AS incoming, ");
    v44 = v98;
    if ( v100.m128i_i64[1] > 0xFuLL )
      v44 = *(_BYTE **)v98;
    v45 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v43, (__int64)v44, v100.m128i_u64[0]);
    v46 = std::operator<<<std::char_traits<char>>(v45, (__int64)".");
    v106 = _mm_load_si128((const __m128i *)&_xmm);
    Block[0] = *(void **)"schema_id";
    Block[1] = (void *)(unsigned __int8)aSchemaId[8];
    BYTE1(Block[1]) = 0;
    v47 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, (__int64)Block, 9u);
    v48 = std::operator<<<std::char_traits<char>>(v47, (__int64)" AS client FROM ");
    v49 = v103;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v49 = (_QWORD *)v103[0];
    v50 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v48, (__int64)v49, v104.m128i_u64[0]);
    v51 = std::operator<<<std::char_traits<char>>(v50, (__int64)" INNER JOIN ");
    v52 = v98;
    if ( v100.m128i_i64[1] > 0xFuLL )
      v52 = *(_BYTE **)v98;
    v53 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v51, (__int64)v52, v100.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v53, (__int64)" ON (");
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    v106 = v54;
    if ( v102.m128i_i64[1] > 0xFuLL )
    {
      v55 = v101[0];
      if ( (unsigned __int64)(v102.m128i_i64[1] + 1) >= 0x1000 )
      {
        v55 = (void *)*((_QWORD *)v101[0] - 1);
        if ( (unsigned __int64)((char *)v101[0] - (char *)v55 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v55);
    }
    v56 = 0;
    v92 = 0;
    v57 = (__int64 *)a1[60];
    if ( v57 != (__int64 *)a1[61] )
    {
      v58 = v57 + 7;
      v59 = (__int64 *)a1[61];
      do
      {
        if ( v56 )
          std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" AND ");
        v60 = v98;
        if ( v100.m128i_i64[1] > 0xFuLL )
          v60 = *(_BYTE **)v98;
        v61 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(
                (__int64)v95,
                (__int64)v60,
                v100.m128i_u64[0]);
        v62 = std::operator<<<std::char_traits<char>>(v61, (__int64)".");
        v63 = (__int64)v57;
        if ( *(v58 - 4) > 0xFu )
          v63 = *v57;
        v64 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v62, v63, *(v58 - 5));
        v65 = std::operator<<<std::char_traits<char>>(v64, (__int64)" = ");
        v66 = v58 - 3;
        if ( *v58 > 0xFu )
          v66 = (_QWORD *)*v66;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v65, (__int64)v66, *(v58 - 1));
        v56 = ++v92;
        v57 += 8;
        v58 += 8;
      }
      while ( v57 != v59 );
    }
    std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)") ");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      (unsigned int)&v111,
      16,
      (unsigned int)v103,
      (unsigned int)v98,
      (__int64)&v94);
    std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)";");
    v67 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"DROP TABLE IF EXISTS ");
    v68 = v103;
    if ( v104.m128i_i64[1] > 0xFuLL )
      v68 = (_QWORD *)v103[0];
    v69 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v67, (__int64)v68, v104.m128i_u64[0]);
    std::operator<<<std::char_traits<char>>(v69, (__int64)";");
    std::stringbuf::str(v96, a2);
    std::string::_Tidy_deallocate(v109);
    v109[0] = 19937;
    v110 = v54;
    std::string::_Tidy_deallocate(v98);
    *(_QWORD *)v98 = 19937;
    v100 = v54;
    std::string::_Tidy_deallocate(v103);
    v103[0] = 19937;
    v104 = v54;
    std::string::_Tidy_deallocate(&v111);
    *(_QWORD *)&v111 = 19937;
    si128 = v54;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
    v97[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
    return a2;
  }
  if ( a4 == 4096 )
  {
    v70 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"DROP TABLE IF EXISTS ");
    v71 = (_QWORD *)RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(v101);
    v72 = v71[2];
    if ( v71[3] > 0xFu )
      v71 = (_QWORD *)*v71;
    v73 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v70, (__int64)v71, v72);
    std::operator<<<std::char_traits<char>>(v73, (__int64)";");
    std::string::_Tidy_deallocate(v101);
    std::stringbuf::str(v96, a2);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
    v97[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
    return a2;
  }
  if ( a4 == 1 || a4 == 1024 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"CREATE TABLE IF NOT EXISTS ");
  }
  else
  {
    switch ( a4 )
    {
      case 2u:
        std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"REPLACE INTO ");
        goto LABEL_65;
      case 4u:
        v84 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"UPDATE ");
        v85 = std::operator<<<std::char_traits<char>>(v84, (__int64)"SchemaVersions");
        std::operator<<<std::char_traits<char>>(v85, (__int64)" SET ");
        *(_OWORD *)v101 = 0;
        v102 = 0;
        std::string::_Construct<1,char const *>(v101, "SchemaVersions", 0xEu);
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
          v5,
          4,
          (unsigned int)v101,
          (_DWORD)a1 + 448,
          (__int64)&v94);
        std::string::_Tidy_deallocate(v101);
        std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"WHERE rowid = ?1;");
        std::stringbuf::str(v96, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
        v97[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
        return a2;
      case 0x40u:
        v86 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"SELECT * FROM ");
        v87 = std::operator<<<std::char_traits<char>>(v86, (__int64)"SchemaVersions");
        std::operator<<<std::char_traits<char>>(v87, (__int64)";");
        std::stringbuf::str(v96, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
        v97[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
        return a2;
      case 0x20u:
        v88 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)"SELECT * FROM ");
        v89 = std::operator<<<std::char_traits<char>>(v88, (__int64)"SchemaVersions");
        std::operator<<<std::char_traits<char>>(v89, (__int64)" WHERE ( rowid = ?1 );");
        std::stringbuf::str(v96, a2);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
        v97[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
        return a2;
    }
    v5 = a3;
  }
  if ( a4 == 1 )
  {
    v90 = *(void (__fastcall **)(_QWORD *, void **))(*a1 + 8LL);
    *(_OWORD *)v101 = 0;
    v102 = 0;
    std::string::_Construct<1,char const *>(v101, "SchemaVersions", 0xEu);
    v90(a1, v101);
    if ( v102.m128i_i64[1] > 0xFuLL )
      std::string::_Deallocate_for_capacity(v101, v101[0]);
  }
  else if ( a4 == 1024 )
  {
    v74 = (void **)RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(Block);
    v75 = 2;
    goto LABEL_66;
  }
LABEL_65:
  *(_OWORD *)v101 = 0;
  v102 = 0;
  std::string::_Construct<1,char const *>(v101, "SchemaVersions", 0xEu);
  v74 = v101;
  v75 = 4;
LABEL_66:
  v107 = 0;
  v108 = 0;
  v107 = *(_OWORD *)v74;
  v108 = *((__m128i *)v74 + 1);
  *(_BYTE *)v74 = 0;
  v74[2] = 0;
  v74[3] = (void *)15;
  if ( (v75 & 4) != 0 )
  {
    v75 &= ~4u;
    std::string::_Tidy_deallocate(v101);
  }
  v76 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (v75 & 2) != 0 )
  {
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    v106 = v76;
  }
  v77 = &v107;
  if ( v108.m128i_i64[1] > 0xFuLL )
    v77 = (__int128 *)v107;
  v78 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>((__int64)v95, (__int64)v77, v108.m128i_u64[0]);
  std::operator<<<std::char_traits<char>>(v78, (__int64)"(");
  v79 = (_DWORD)a1 + 448;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
    v5,
    a4,
    (unsigned int)&v107,
    (_DWORD)a1 + 448,
    (__int64)&v94);
  if ( a4 == 1 && a1[54] )
  {
    v80 = a1 + 52;
    v81 = std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" , ");
    v82 = v80[2];
    if ( v80[3] > 0xFu )
      v80 = (_QWORD *)*v80;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v81, (__int64)v80, v82);
  }
  std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)")");
  if ( a4 == 2 )
  {
    std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)" VALUES (");
    RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(
      v5,
      8,
      (unsigned int)&v107,
      v79,
      (__int64)&v94);
    std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)")");
  }
  std::operator<<<std::char_traits<char>>((__int64)v95, (__int64)";");
  std::stringbuf::str(v96, a2);
  std::string::_Tidy_deallocate(&v107);
  *(_QWORD *)&v107 = 19937;
  v108 = v76;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v97);
  v97[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v97);
  return a2;
}

```

## disassembly

```asm
0x1800445b0  mov     rax, rsp
0x1800445b3  push    rbp
0x1800445b4  push    rbx
0x1800445b5  push    rsi
0x1800445b6  push    r12
0x1800445b8  push    r13
0x1800445ba  push    r14
0x1800445bc  push    r15
0x1800445be  lea     rbp, [rax-198h]
0x1800445c5  sub     rsp, 260h
0x1800445cc  movaps  xmmword ptr [rax-48h], xmm6
0x1800445d0  mov     rax, cs:__security_cookie
0x1800445d7  xor     rax, rsp
0x1800445da  mov     [rbp+190h+var_50], rax
0x1800445e1  movzx   esi, r9w
0x1800445e5  mov     r13, r8
0x1800445e8  mov     qword ptr [rsp+290h+var_258], r8
0x1800445ed  mov     r14, rdx
0x1800445f0  mov     r15, rcx
0x1800445f3  mov     [rsp+290h+var_260], rdx
0x1800445f8  xor     r12d, r12d
0x1800445fb  mov     [rsp+40h], r12d
0x180044600  lea     rcx, [rsp+50h]
0x180044605  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18004460a  nop
0x18004460b  mov     eax, 800h
0x180044610  cmp     ax, si
0x180044613  jnz     loc_180044D98
0x180044619  xorps   xmm0, xmm0
0x18004461c  xorps   xmm1, xmm1
0x18004461f  movdqu  [rbp+190h+var_60], xmm1
0x180044627  movups  [rbp+190h+var_80], xmm0
0x18004462e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180044636  movdqu  [rbp+190h+var_70], xmm1
0x18004463e  mov     byte ptr [rbp+190h+var_80], r12b
0x180044645  mov     dword ptr [rbp+190h+var_60], r12d
0x18004464c  mov     qword ptr [rbp+190h+var_60+8], r12
0x180044653  lea     rcx, [rbp+190h+var_100]
0x18004465a  call    ?IndexName@?$Table@VSchemaVersions@Tables@Meta@RepoMan@@V?$TablePolicy@USchemaVersions@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@34@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::IndexName(void)
0x18004465f  nop
0x180044660  xorps   xmm0, xmm0
0x180044663  movups  [rbp+190h+var_140], xmm0
0x180044667  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000e
0x18004466f  movdqu  [rbp+190h+var_130], xmm1
0x180044674  movsd   xmm0, qword ptr cs:aSchemaversions; "SchemaVersions"
0x18004467c  movsd   qword ptr [rbp+190h+var_140], xmm0
0x180044681  mov     eax, dword ptr cs:aSchemaversions+8; "rsions"
0x180044687  mov     dword ptr [rbp+190h+var_140+8], eax
0x18004468a  movzx   eax, word ptr cs:aSchemaversions+0Ch; "ns"
0x180044691  mov     word ptr [rbp+190h+var_140+0Ch], ax
0x180044695  mov     byte ptr [rbp+190h+var_140+0Eh], r12b
0x180044699  lea     rdx, aInsertOrIgnore; " INSERT OR IGNORE INTO "
0x1800446a0  lea     rcx, [rsp+290h+var_230]
0x1800446a5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800446aa  lea     rdx, [rbp+190h+var_140]
0x1800446ae  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x1800446b3  cmova   rdx, qword ptr [rbp+190h+var_140]
0x1800446b8  mov     r8, qword ptr [rbp+190h+var_130]
0x1800446bc  mov     rcx, rax
0x1800446bf  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800446c4  lea     rdx, aSelectNull; " SELECT NULL"
0x1800446cb  mov     rcx, rax
0x1800446ce  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800446d3  lea     r9, [r15+1C0h]
0x1800446da  mov     edx, 802h
0x1800446df  lea     rax, [rsp+50h]
0x1800446e4  mov     [rsp+20h], rax
0x1800446e9  lea     r8, [rbp+190h+var_100]
0x1800446f0  lea     rcx, [rbp+190h+var_80]
0x1800446f7  call    ?BuildText@?$RowType@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x1800446fc  lea     rdx, aFrom_0; " FROM "
0x180044703  lea     rcx, [rsp+290h+var_230]
0x180044708  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004470d  lea     rdx, [rbp+190h+var_100]
0x180044714  cmp     qword ptr [rbp+190h+var_F0+8], 0Fh
0x18004471c  cmova   rdx, [rbp+190h+var_100]
0x180044724  mov     r8, qword ptr [rbp+190h+var_F0]
0x18004472b  mov     rcx, rax
0x18004472e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044733  lea     edx, [r12+10h]
0x180044738  lea     rax, [rsp+50h]
0x18004473d  mov     [rsp+20h], rax
0x180044742  lea     r9, [rbp+190h+var_140]
0x180044746  lea     r8, [rbp+190h+var_100]
0x18004474d  lea     rcx, [rbp+190h+var_80]
0x180044754  call    ?BuildText@?$RowType@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAAXW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::BuildText(CommandFlags,std::string const &,std::string const &,std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &)
0x180044759  lea     rdx, aLeftOuterJoin; " LEFT OUTER JOIN "
0x180044760  lea     rcx, [rsp+290h+var_230]
0x180044765  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004476a  lea     rdx, [rbp+190h+var_140]
0x18004476e  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x180044773  cmova   rdx, qword ptr [rbp+190h+var_140]
0x180044778  mov     r8, qword ptr [rbp+190h+var_130]
0x18004477c  mov     rcx, rax
0x18004477f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044784  lea     rdx, aOn; " ON ("
0x18004478b  mov     rcx, rax
0x18004478e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044793  mov     rax, [r15+1E8h]
0x18004479a  mov     [rsp+290h+var_260], rax
0x18004479f  mov     rsi, [r15+1E0h]
0x1800447a6  lea     r13d, [r12+40h]
0x1800447ab  cmp     rsi, rax
0x1800447ae  jz      loc_18004484E
0x1800447b4  lea     rbx, [rsi+38h]
0x1800447b8  test    r12, r12
0x1800447bb  jz      short loc_1800447CE
0x1800447bd  lea     rdx, aAnd_1; " AND "
0x1800447c4  lea     rcx, [rsp+290h+var_230]
0x1800447c9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800447ce  lea     rdx, [rbp+190h+var_140]
0x1800447d2  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x1800447d7  cmova   rdx, qword ptr [rbp+190h+var_140]
0x1800447dc  mov     r8, qword ptr [rbp+190h+var_130]
0x1800447e0  lea     rcx, [rsp+290h+var_230]
0x1800447e5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800447ea  lea     rdx, asc_1801D0CE8; "."
0x1800447f1  mov     rcx, rax
0x1800447f4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800447f9  mov     rdx, rsi
0x1800447fc  cmp     qword ptr [rbx-20h], 0Fh
0x180044801  jbe     short loc_180044806
0x180044803  mov     rdx, [rsi]
0x180044806  mov     r8, [rbx-28h]
0x18004480a  mov     rcx, rax
0x18004480d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044812  lea     rdx, asc_1801D5B8C; " = "
0x180044819  mov     rcx, rax
0x18004481c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044821  lea     rdx, [rbx-18h]
0x180044825  cmp     qword ptr [rbx], 0Fh
0x180044829  jbe     short loc_18004482E
0x18004482b  mov     rdx, [rdx]
0x18004482e  mov     r8, [rbx-8]
0x180044832  mov     rcx, rax
0x180044835  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18004483a  inc     r12
0x18004483d  add     rsi, r13
0x180044840  add     rbx, r13
0x180044843  cmp     rsi, [rsp+290h+var_260]
0x180044848  jnz     loc_1800447B8
0x18004484e  lea     rdx, aWhere; ") WHERE "
0x180044855  lea     rcx, [rsp+290h+var_230]
0x18004485a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004485f  lea     rdx, [rbp+190h+var_140]
0x180044863  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x180044868  cmova   rdx, qword ptr [rbp+190h+var_140]
0x18004486d  mov     r8, qword ptr [rbp+190h+var_130]
0x180044871  mov     rcx, rax
0x180044874  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044879  lea     r12, asc_1801D0CE8; "."
0x180044880  mov     rdx, r12
0x180044883  mov     rcx, rax
0x180044886  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004488b  mov     rcx, rax
0x18004488e  xorps   xmm0, xmm0
0x180044891  movups  xmmword ptr [rbp+190h+Block], xmm0
0x180044898  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x1800448a0  movdqu  [rbp+190h+var_D0], xmm1
0x1800448a8  movsd   xmm0, qword ptr cs:aSchemaId; "schema_id"
0x1800448b0  movsd   [rbp+190h+Block], xmm0
0x1800448b8  mov     al, byte ptr cs:aSchemaId+8; "d"
0x1800448be  mov     byte ptr [rbp+190h+Block+8], al
0x1800448c4  xor     esi, esi
0x1800448c6  mov     byte ptr [rbp+190h+Block+9], sil
0x1800448cd  lea     r8d, [rsi+9]
0x1800448d1  lea     rdx, [rbp+190h+Block]
0x1800448d8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800448dd  lea     rdx, aIsNull; " IS NULL;"
0x1800448e4  mov     rcx, rax
0x1800448e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800448ec  nop
0x1800448ed  mov     ebx, 1000h
0x1800448f2  mov     rax, qword ptr [rbp+190h+var_D0+8]
0x1800448f9  cmp     rax, 0Fh
0x1800448fd  jbe     short loc_18004493E
0x1800448ff  mov     rcx, [rbp+190h+Block]; Block
0x180044906  mov     rdx, rcx
0x180044909  inc     rax
0x18004490c  cmp     rax, rbx
0x18004490f  jb      short loc_180044938
0x180044911  mov     rcx, [rcx-8]
0x180044915  sub     rdx, rcx
0x180044918  lea     rax, [rdx-8]
0x18004491c  cmp     rax, 1Fh
0x180044920  jbe     short loc_180044938
0x180044922  mov     [rsp+20h], rsi; Reserved
0x180044927  xor     r9d, r9d; LineNo
0x18004492a  xor     r8d, r8d; FileName
0x18004492d  xor     edx, edx; FunctionName
0x18004492f  xor     ecx, ecx; Expression
0x180044931  call    cs:__imp__invoke_watson
0x180044938  call    cs:__imp_free
0x18004493e  lea     rcx, [rbp+190h+var_A0]
0x180044945  call    ?MapName@?$Table@VSchemaVersions@Tables@Meta@RepoMan@@V?$TablePolicy@USchemaVersions@Text@Meta@RepoMan@@$0A@@34@U?$Column@U?$Key@USchema_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@U1234@UNone@Alias@34@@Meta@RepoMan@@_J@34@U?$Column@U?$Value@USchemaVersion@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@34@U?$Column@U?$Value@UGitSHA1@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Table<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::TablePolicy<RepoMan::Meta::Text::SchemaVersions,0>,RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Schema_Id,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::SchemaVersion,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::GitSHA1,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::MapName(void)
0x18004494a  nop
0x18004494b  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x180044952  lea     rcx, [rsp+290h+var_230]
0x180044957  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18004495c  lea     rdx, [rbp+190h+var_A0]
0x180044963  cmp     qword ptr [rbp+190h+var_90+8], 0Fh
0x18004496b  cmova   rdx, [rbp+190h+var_A0]
0x180044973  mov     r8, qword ptr [rbp+190h+var_90]
0x18004497a  mov     rcx, rax
0x18004497d  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044982  lea     rdx, aIncomingIntege; "(incoming INTEGER PRIMARY KEY, client I"...
0x180044989  mov     rcx, rax
0x18004498c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044991  lea     rdx, aInsertInto; "INSERT INTO "
0x180044998  lea     rcx, [rsp+290h+var_230]
0x18004499d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800449a2  lea     rdx, [rbp+190h+var_A0]
0x1800449a9  cmp     qword ptr [rbp+190h+var_90+8], 0Fh
0x1800449b1  cmova   rdx, [rbp+190h+var_A0]
0x1800449b9  mov     r8, qword ptr [rbp+190h+var_90]
0x1800449c0  mov     rcx, rax
0x1800449c3  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800449c8  lea     rdx, aSelect; " SELECT "
0x1800449cf  mov     rcx, rax
0x1800449d2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800449d7  lea     rdx, [rbp+190h+var_100]
0x1800449de  cmp     qword ptr [rbp+190h+var_F0+8], 0Fh
0x1800449e6  cmova   rdx, [rbp+190h+var_100]
0x1800449ee  mov     r8, qword ptr [rbp+190h+var_F0]
0x1800449f5  mov     rcx, rax
0x1800449f8  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800449fd  mov     rdx, r12
0x180044a00  mov     rcx, rax
0x180044a03  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044a08  mov     rcx, rax
0x180044a0b  xorps   xmm0, xmm0
0x180044a0e  movups  xmmword ptr [rbp+190h+var_120], xmm0
0x180044a12  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x180044a1a  movdqu  [rbp+190h+var_110], xmm1
0x180044a22  movsd   xmm0, qword ptr cs:aSchemaId; "schema_id"
0x180044a2a  movsd   [rbp+190h+var_120], xmm0
0x180044a2f  mov     al, byte ptr cs:aSchemaId+8; "d"
0x180044a35  mov     byte ptr [rbp+190h+var_120+8], al
0x180044a38  mov     byte ptr [rbp+190h+var_120+9], sil
0x180044a3c  mov     r8d, 9
0x180044a42  lea     rdx, [rbp+190h+var_120]
0x180044a46  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044a4b  lea     rdx, aAsIncoming; " AS incoming, "
0x180044a52  mov     rcx, rax
0x180044a55  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044a5a  lea     rdx, [rbp+190h+var_140]
0x180044a5e  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x180044a63  cmova   rdx, qword ptr [rbp+190h+var_140]
0x180044a68  mov     r8, qword ptr [rbp+190h+var_130]
0x180044a6c  mov     rcx, rax
0x180044a6f  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044a74  mov     rdx, r12
0x180044a77  mov     rcx, rax
0x180044a7a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044a7f  mov     rcx, rax
0x180044a82  xorps   xmm0, xmm0
0x180044a85  movups  xmmword ptr [rbp+190h+Block], xmm0
0x180044a8c  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000009
0x180044a94  movdqu  [rbp+190h+var_D0], xmm1
0x180044a9c  movsd   xmm0, qword ptr cs:aSchemaId; "schema_id"
0x180044aa4  movsd   [rbp+190h+Block], xmm0
0x180044aac  mov     al, byte ptr cs:aSchemaId+8; "d"
0x180044ab2  mov     byte ptr [rbp+190h+Block+8], al
0x180044ab8  mov     byte ptr [rbp+190h+Block+9], sil
0x180044abf  mov     r8d, 9
0x180044ac5  lea     rdx, [rbp+190h+Block]
0x180044acc  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044ad1  lea     rdx, aAsClientFrom; " AS client FROM "
0x180044ad8  mov     rcx, rax
0x180044adb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044ae0  lea     rdx, [rbp+190h+var_100]
0x180044ae7  cmp     qword ptr [rbp+190h+var_F0+8], 0Fh
0x180044aef  cmova   rdx, [rbp+190h+var_100]
0x180044af7  mov     r8, qword ptr [rbp+190h+var_F0]
0x180044afe  mov     rcx, rax
0x180044b01  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044b06  lea     rdx, aInnerJoin; " INNER JOIN "
0x180044b0d  mov     rcx, rax
0x180044b10  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044b15  lea     rdx, [rbp+190h+var_140]
0x180044b19  cmp     qword ptr [rbp+190h+var_130+8], 0Fh
0x180044b1e  cmova   rdx, qword ptr [rbp+190h+var_140]
0x180044b23  mov     r8, qword ptr [rbp+190h+var_130]
0x180044b27  mov     rcx, rax
0x180044b2a  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180044b2f  lea     rdx, aOn; " ON ("
0x180044b36  mov     rcx, rax
0x180044b39  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180044b3e  nop
0x180044b3f  lea     rcx, [rbp+190h+Block]
0x180044b46  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180044b4b  mov     r12d, 4DE1h
0x180044b51  mov     [rbp+190h+Block], r12
0x180044b58  movdqa  xmm6, cs:__xmm@000000000000001f0000000000000000
0x180044b60  movdqu  [rbp+190h+var_D0], xmm6
0x180044b68  mov     rax, qword ptr [rbp+190h+var_110+8]
0x180044b6f  cmp     rax, 0Fh
0x180044b73  jbe     short loc_180044BB1
0x180044b75  mov     rcx, [rbp+190h+var_120]; Block
0x180044b79  mov     rdx, rcx
  ... truncated ...
```
